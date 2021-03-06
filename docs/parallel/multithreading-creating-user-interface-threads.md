---
title: 'Многопоточность: Создание потоков пользовательского интерфейса MFC | Документация Майкрософт'
ms.custom: ''
ms.date: 08/27/2018
ms.technology:
- cpp-parallel
ms.topic: conceptual
f1_keywords:
- CREATE_SUSPENDED
- SECURITY_ATTRIBUTES
dev_langs:
- C++
helpviewer_keywords:
- multithreading [C++], user interface threads
- threading [C++], creating threads
- threading [C++], user interface threads
- user interface threads [C++]
- threading [MFC], user interface threads
ms.assetid: 446925c1-db59-46ea-ae5b-d5ae5d5b91d8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 06158f50364320c96223d5627386a059761baa77
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46416322"
---
# <a name="multithreading-creating-mfc-user-interface-threads"></a>Многопоточность: Создание потоков пользовательского интерфейса в MFC

Поток пользовательского интерфейса обычно используется для обработки ввода и реагировать на события пользователя независимо от потоков, выполняющих другие части приложения. Основной поток приложения (в вашей `CWinApp`-производного класса) создается и запускается автоматически. В этом разделе описываются действия, необходимые для создания пользовательского интерфейса дополнительных потоков.

Первое, что необходимо сделать при создании потока пользовательского интерфейса — это производный от класса [CWinThread](../mfc/reference/cwinthread-class.md). Должна быть объявлена и реализовать это с помощью [DECLARE_DYNCREATE](../mfc/reference/run-time-object-model-services.md#declare_dyncreate) и [IMPLEMENT_DYNCREATE](../mfc/reference/run-time-object-model-services.md#implement_dyncreate) макросы. Этот класс необходимо переопределить некоторые функции и можно переопределить другими пользователями. Эти функции и какие действия следует они представлены в следующей таблице.

### <a name="functions-to-override-when-creating-a-user-interface-thread"></a>Переопределяемые функции при создании потока пользовательского интерфейса

|Функция|Цель|
|--------------|-------------|
|[ExitInstance](../mfc/reference/cwinthread-class.md#exitinstance)|Выполните очистку после завершения потока. Обычно переопределяется.|
|[InitInstance](../mfc/reference/cwinthread-class.md#initinstance)|Выполните инициализацию экземпляра для потока. Необходимо переопределить.|
|[OnIdle](../mfc/reference/cwinthread-class.md#onidle)|Выполните обработку времени простоя определенного потока. Обычно не переопределяется.|
|[PreTranslateMessage](../mfc/reference/cwinthread-class.md#pretranslatemessage)|Фильтровать сообщения перед их отправкой к `TranslateMessage` и `DispatchMessage`. Обычно не переопределяется.|
|[ProcessWndProcException](../mfc/reference/cwinthread-class.md#processwndprocexception)|Перехват необработанных исключений выданных потока сообщением или обработчиками команд. Обычно не переопределяется.|
|[Выполнить](../mfc/reference/cwinthread-class.md#run)|Функции управления для потока. Содержит конвейер сообщений. Переопределяется редко.|

MFC предоставляет две версии `AfxBeginThread` через перегрузку параметра: один, можно создать только рабочих потоков и, который может создаваться пользовательского интерфейса и рабочие потоки. Чтобы запустить поток пользовательского интерфейса, вызовите вторую перегрузку [AfxBeginThread](../mfc/reference/application-information-and-management.md#afxbeginthread), указав следующие сведения:

- [RUNTIME_CLASS](../mfc/reference/run-time-object-model-services.md#runtime_class) класса, производного от `CWinThread`.

- (Необязательно) Уровень желаемый приоритет. Значение по умолчанию используется обычный приоритет. Дополнительные сведения о доступных уровнях приоритета см. в разделе [SetThreadPriority](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-setthreadpriority) в пакете Windows SDK.

- (Необязательно) Желаемый размер стека для потока. По умолчанию используется тот же размер стека, что и для создания потока.

- (Необязательно) CREATE_SUSPENDED, если необходимо создать в приостановленном состоянии потока. По умолчанию равно 0 или запустите потока в обычном режиме.

- (Необязательно) Желаемые атрибуты безопасности. По умолчанию используется тот же уровень доступа как родительского потока. Дополнительные сведения о формате информации о безопасности см. в разделе [SECURITY_ATTRIBUTES](https://msdn.microsoft.com/library/windows/desktop/aa379560) в пакете Windows SDK.

`AfxBeginThread` выполняет большую часть работы. Она создает новый объект класса, инициализирует его с информацией, вы предоставляете и вызовы [функцию CWinThread::CreateThread](../mfc/reference/cwinthread-class.md#createthread) для запуска выполнения потока. Проверки выполняются на протяжении процедуры, чтобы убедиться в том, что все объекты, освобожденные должным образом вызывать любую часть создания.

## <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения

- [Многопоточность. Завершение потоков](multithreading-terminating-threads.md)

- [Многопоточность. Создание рабочих потоков](multithreading-creating-worker-threads.md)

- [Процессы и потоки](/windows/desktop/ProcThread/processes-and-threads)

## <a name="see-also"></a>См. также

[Реализация многопоточности на языке C++ с помощью классов MFC](multithreading-with-cpp-and-mfc.md)