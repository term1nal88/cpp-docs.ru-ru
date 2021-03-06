---
title: Общие рекомендации в среде выполнения с параллелизмом | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Concurrency Runtime, general best practices
ms.assetid: ce5c784c-051e-44a6-be84-8b3e1139c18b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3b998048db9f604ebda24d03eddc7e296519abb7
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46392909"
---
# <a name="general-best-practices-in-the-concurrency-runtime"></a>Общие рекомендации в среде выполнения с параллелизмом

В этом документе описываются рекомендации, относящиеся к различным областям среды выполнения с параллелизмом.

##  <a name="top"></a> Разделы

Этот документ содержит следующие разделы.

- [Используйте конструкции совместной синхронизации, если это возможно](#synchronization)

- [Избегайте продолжительных задач, которые не уступают](#yield)

- [Использование превышения лимита подписки для операций смещения, блокирующие или иметь высокую задержку](#oversubscription)

- [Использование функции управления одновременно используемую память, когда это возможно](#memory)

- [Используйте RAII для управления временем существования объектов параллелизма](#raii)

- [Не создавайте объекты параллелизма в глобальной области видимости](#global-scope)

- [Не используйте параллельные объекты в сегментах общих данных](#shared-data)

##  <a name="synchronization"></a> Используйте конструкции совместной синхронизации, если это возможно

Среда выполнения с параллелизмом предоставляет многие конструкции параллельно безопасно, не требующие внешнему объекту синхронизации. Например [concurrency::concurrent_vector](../../parallel/concrt/reference/concurrent-vector-class.md) класс предоставляет параллелизма добавления и доступа к операциям элемент. Тем не менее для случаев, когда вам требуется монопольный доступ к ресурсу, среда выполнения предоставляет [concurrency::critical_section](../../parallel/concrt/reference/critical-section-class.md), [concurrency::reader_writer_lock](../../parallel/concrt/reference/reader-writer-lock-class.md), и [параллелизма :: событий](../../parallel/concrt/reference/event-class.md) классы. Поведение этих типов совместно; Таким образом планировщик можно перераспределить ресурсы для другого контекста обработки, пока первая задача ожидает получения данных. По возможности используйте эти типы синхронизации, а не другие механизмы, как они предоставляются в Windows API, которые могут работать совместно. Дополнительные сведения об этих типах синхронизации и пример кода см. в разделе [структуры данных синхронизации](../../parallel/concrt/synchronization-data-structures.md) и [Сравнение структур данных синхронизации с Windows API](../../parallel/concrt/comparing-synchronization-data-structures-to-the-windows-api.md).

[[В начало](#top)]

##  <a name="yield"></a> Избегайте продолжительных задач, которые не уступают

Поскольку планировщик заданий работает совместно, он не поддерживает распределение ресурсов между задачами. Таким образом задачи могут запускаться другие задачи. Несмотря на то, что это приемлемо, в некоторых случаях, в других случаях это может привести к взаимоблокировке или истощению ресурсов.

В следующем примере выполняется несколько задач, чем количество выделенных ресурсов обработки. Первая задача не уступает планировщик задач, и поэтому вторая задача не запускается до завершения первой задачи.

[!code-cpp[concrt-cooperative-tasks#1](../../parallel/concrt/codesnippet/cpp/general-best-practices-in-the-concurrency-runtime_1.cpp)]

В этом примере выводятся следующие данные:

1: 250000000 1: 500000000 1: 750000000 1: 1000000000 2: 250000000 2: 500000000 2: 750000000 2: 1000000000

Существует несколько способов включения взаимодействия между двумя задачами. Один из способов — передачу планировщик заданий в длительных задач. В следующем примере изменяется `task` функция, вызываемая [Concurrency::Context:: yield](reference/context-class.md#yield) метод уступающего выполнение планировщику задач, чтобы могла запуститься другая задача.

[!code-cpp[concrt-cooperative-tasks#2](../../parallel/concrt/codesnippet/cpp/general-best-practices-in-the-concurrency-runtime_2.cpp)]

В этом примере выводятся следующие данные:

```Output
1: 250000000
2: 250000000
1: 500000000
2: 500000000
1: 750000000
2: 750000000
1: 1000000000
2: 1000000000
```

`Context::Yield` Метод возвращает только другой активный поток в планировщике, к которому принадлежит текущий поток, упрощенная задача или другой поток операционной системы. Этот метод не уступает работе, запланировано выполнение [concurrency::task_group](reference/task-group-class.md) или [concurrency::structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md) объекта, но еще не началась.

Существуют другие способы обеспечить совместную работу длительно выполняемых задач. Можно разделить большие задачи на меньшие подзадачи. Можно также включить превышение лимита подписки во время продолжительной операции. Превышение лимита подписки позволяет создать больше потоков, чем количество доступных аппаратных потоков. Превышение лимита подписки особенно полезна в случаях, когда провайдер связана с большими задержками, например, чтение данных с диска или из сетевого подключения. Дополнительные сведения об упрощенных задач и превышение лимита подписки см. в разделе [планировщик](../../parallel/concrt/task-scheduler-concurrency-runtime.md).

[[В начало](#top)]

##  <a name="oversubscription"></a> Использование превышения лимита подписки для операций смещения, блокирующие или иметь высокую задержку

Среда выполнения с параллелизмом предоставляет примитивы синхронизации, такие как [concurrency::critical_section](../../parallel/concrt/reference/critical-section-class.md), позволяющие задачам выполнять совместную блокировку и уступать друг с другом. Когда одна задача совместно блокирует либо передачу, планировщик можно перераспределить ресурсы для другого контекста обработки, пока первая задача ожидает получения данных.

Бывают случаи, в которых нельзя использовать механизм кооперативной блокировки, предоставляемый средой выполнения с параллелизмом. Например внешнюю библиотеку, используемом использовать другой механизм синхронизации. Еще один пример — выполнение операции, которая может иметь большой объем задержки, например, при использовании Windows API `ReadFile` функция для чтения данных из сетевого подключения. В этих случаях превышение лимита подписки можно включить другие задачи, чтобы выполнить во время простоя другой задачи. Превышение лимита подписки позволяет создать больше потоков, чем количество доступных аппаратных потоков.

Рассмотрим следующую функцию, `download`, который загружает из файла по заданному URL-АДРЕСУ. В этом примере используется [Concurrency::Context:: Oversubscribe](reference/context-class.md#oversubscribe) метод, чтобы временно увеличить количество активных потоков.

[!code-cpp[concrt-download-oversubscription#4](../../parallel/concrt/codesnippet/cpp/general-best-practices-in-the-concurrency-runtime_3.cpp)]

Так как `GetHttpFile` функция выполняет операцию с возможностью задержек, превышение лимита подписки можно включить другие задачи, как текущая задача ожидает получения данных. Полную версию этого примера, см. в разделе [как: использование превышения лимита подписки для смещения задержки](../../parallel/concrt/how-to-use-oversubscription-to-offset-latency.md).

[[В начало](#top)]

##  <a name="memory"></a> Использование функции управления одновременно используемую память, когда это возможно

Использование функции управления памятью, [concurrency::Alloc](reference/concurrency-namespace-functions.md#alloc) и [concurrency::Free](reference/concurrency-namespace-functions.md#free), при наличии детализированными задачами, постоянно выделяющими небольшие объекты с коротким временем существования. Среда выполнения с параллелизмом содержит отдельный кэш памяти для каждого выполняющегося потока. `Alloc` И `Free` функции выделяют и освобождают память из этих кэшей без использования блокировки или барьеры памяти.

Дополнительные сведения о эти функции управления памятью, см. в разделе [планировщик](../../parallel/concrt/task-scheduler-concurrency-runtime.md). Пример, использующий эти функции, см. в разделе [как: используйте Alloc и Free для повышения производительности памяти](../../parallel/concrt/how-to-use-alloc-and-free-to-improve-memory-performance.md).

[[В начало](#top)]

##  <a name="raii"></a> Используйте RAII для управления временем существования объектов параллелизма

Среда выполнения с параллелизмом использует обработку исключений для реализации функции, такие как отмены. Таким образом можно напишите код, безопасный в отношении исключений, когда вызов среды выполнения или другую библиотеку, которая вызывает среду выполнения.

*Получение ресурса есть инициализация* шаблон (RAII) — один из способов безопасного управления временем жизни объекта параллелизма в данной области. В разделе шаблон RAII структуру данных выделена в стеке. Что инициализирует структуры данных, или получает ресурса при его создании и уничтожает или освобождает ресурс, при уничтожении структуре данных. Шаблон RAII гарантирует, что деструктор вызывается до выхода из внешней области видимости. Этот шаблон полезен, если функция содержит несколько `return` инструкций. Этот шаблон также помогает писать безопасный в отношении исключений код. Когда `throw` инструкция вызывает стека, деструктор для объекта RAII; таким образом, ресурс всегда правильно удаляется или выпуска.

Среда выполнения определяет несколько классов, использующих шаблон RAII, например, [Concurrency::critical_section:: scoped_lock](../../parallel/concrt/reference/critical-section-class.md#critical_section__scoped_lock_class) и [Concurrency::reader_writer_lock:: scoped_lock](reference/reader-writer-lock-class.md#scoped_lock_class). Эти вспомогательные классы называются *блокировками с областью*. Эти классы обеспечивают несколько преимуществ при работе с [concurrency::critical_section](../../parallel/concrt/reference/critical-section-class.md) или [concurrency::reader_writer_lock](../../parallel/concrt/reference/reader-writer-lock-class.md) объектов. Конструктор этих классов получает доступ к заданной `critical_section` или `reader_writer_lock` объекта; деструктор выпуски доступ к этому объекту. Так как блокировка с областью освобождает доступ к своему объекту взаимного исключения автоматически, когда он будет уничтожен, вам не требуется разблокировать вручную базовый объект.

Рассмотрим следующий класс `account`, который определяется внешней библиотеки и не может быть изменен.

[!code-cpp[concrt-account-transactions#1](../../parallel/concrt/codesnippet/cpp/general-best-practices-in-the-concurrency-runtime_4.h)]

В следующем примере выполняется несколько транзакций на `account` объекта в параллельном режиме. В примере используется `critical_section` объект для синхронизации доступа к `account` объекта, так как `account` класс не является безопасным в режиме параллелизма. Каждая параллельная операция использует `critical_section::scoped_lock` объекта, чтобы гарантировать, что `critical_section` объект разблокируется, когда операция успешно или неуспешно. Если баланс счета является отрицательным, `withdraw` происходит сбой операции путем создания исключения.

[!code-cpp[concrt-account-transactions#2](../../parallel/concrt/codesnippet/cpp/general-best-practices-in-the-concurrency-runtime_5.cpp)]

В этом примере получается следующий результат:

```Output
Balance before deposit: 1924
Balance after deposit: 2924
Balance before withdrawal: 2924
Balance after withdrawal: -76
Balance before withdrawal: -76
Error details:
    negative balance: -76
```

Дополнительные примеры, использующих шаблон RAII для управления временем существования объектов параллелизма, см. в разделе [Пошаговое руководство: удаление задач из потока пользовательского интерфейса](../../parallel/concrt/walkthrough-removing-work-from-a-user-interface-thread.md), [как: использование класса Context для реализации совместной Семафор](../../parallel/concrt/how-to-use-the-context-class-to-implement-a-cooperative-semaphore.md), и [как: использование лимита подписки для задержек](../../parallel/concrt/how-to-use-oversubscription-to-offset-latency.md).

[[В начало](#top)]

##  <a name="global-scope"></a> Не создавайте объекты параллелизма в глобальной области видимости

При создании объекта параллелизма в глобальной области в приложении могут возникнуть такие проблемы, как взаимоблокировка или нарушение прав доступа к памяти.

Например, при создании объекта исполняющей среды с параллелизмом среда создает планировщик по умолчанию, если он еще не создан. Объект среды выполнения, созданный при конструировании глобального объекта, соответственно вызовет то, что среда выполнения создаст этот планировщик по умолчанию. Однако этот процесс принимает внутреннюю блокировку, которая может помешать инициализации других объектов, поддерживающих инфраструктуру исполняющей среды с параллелизмом. Эта внутренняя блокировка может потребоваться другому, еще не инициализированному, объекту инфраструктуры, и поэтому может привести к возникновению взаимоблокировки в приложении.

В следующем примере показано создание глобального [concurrency::Scheduler](../../parallel/concrt/reference/scheduler-class.md) объекта. Эта схема применяется не только к классу `Scheduler`, но и ко всем остальным типам, предоставленным исполняющей средой с параллелизмом. Рекомендуется не использовать эту схему, поскольку она может привести к неожиданному поведению в приложении.

[!code-cpp[concrt-global-scheduler#1](../../parallel/concrt/codesnippet/cpp/general-best-practices-in-the-concurrency-runtime_6.cpp)]

Примеры правильного способа создания `Scheduler` объектов, см. в разделе [планировщик](../../parallel/concrt/task-scheduler-concurrency-runtime.md).

[[В начало](#top)]

##  <a name="shared-data"></a> Не используйте параллельные объекты в сегментах общих данных

Среда выполнения с параллелизмом не поддерживает использование параллельных объектов в разделе общих данных, например, раздел данных, в котором создается путем [data_seg](../../preprocessor/data-seg.md) `#pragma` директива. Среда выполнения поместить объект параллелизма, который совместно используется процессами в состоянии несовместимой или недействительным.

[[В начало](#top)]

## <a name="see-also"></a>См. также

[Рекомендации по работе со средой выполнения с параллелизмом](../../parallel/concrt/concurrency-runtime-best-practices.md)<br/>
[Библиотека параллельных шаблонов (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)<br/>
[Библиотека асинхронных агентов](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[Планировщик задач](../../parallel/concrt/task-scheduler-concurrency-runtime.md)<br/>
[Структуры данных синхронизации](../../parallel/concrt/synchronization-data-structures.md)<br/>
[Сравнение структур данных синхронизации с интерфейсом Windows API](../../parallel/concrt/comparing-synchronization-data-structures-to-the-windows-api.md)<br/>
[Практическое руководство. Использование функций Alloc и Free для повышения производительности операций с памятью](../../parallel/concrt/how-to-use-alloc-and-free-to-improve-memory-performance.md)<br/>
[Практическое руководство. Использование лимита подписки для устранения задержек](../../parallel/concrt/how-to-use-oversubscription-to-offset-latency.md)<br/>
[Практическое руководство. Использование класса Context для реализации семафора, поддерживающего параллельный доступ](../../parallel/concrt/how-to-use-the-context-class-to-implement-a-cooperative-semaphore.md)<br/>
[Пошаговое руководство. Удаление задач из потока пользовательского интерфейса](../../parallel/concrt/walkthrough-removing-work-from-a-user-interface-thread.md)<br/>
[Рекомендации по работе с библиотекой параллельных шаблонов](../../parallel/concrt/best-practices-in-the-parallel-patterns-library.md)<br/>
[Рекомендации по работе с библиотекой асинхронных агентов](../../parallel/concrt/best-practices-in-the-asynchronous-agents-library.md)
