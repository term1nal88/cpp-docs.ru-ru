---
title: 'Практическое: используйте фильтр блок сообщений | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- message-block filters, using [Concurrency Runtime]
- using message-block filters [Concurrency Runtime]
ms.assetid: db6b99fb-288d-4477-96dc-b9751772ebb2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 93578f9d798e0c0bab0fe58a3211c20507dd99d4
ms.sourcegitcommit: 8480f16893f09911f08a58caf684405404f7ac8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/12/2018
ms.locfileid: "49162065"
---
# <a name="how-to-use-a-message-block-filter"></a>Практическое руководство. Использование фильтра блоков сообщений

В этом документе показано, как использовать функцию фильтрации, чтобы позволить блоку асинхронное сообщение для принятия или отклонения сообщения в зависимости от полезных данных сообщения.

При создании объекта блока сообщений, таких как [concurrency::unbounded_buffer](reference/unbounded-buffer-class.md), [concurrency::call](../../parallel/concrt/reference/call-class.md), или [concurrency::transformer](../../parallel/concrt/reference/transformer-class.md), можно указать *filter, функция* , определяет, принимает или отклоняет сообщение в блок сообщений. Функции фильтра — это позволяет гарантировать, что блок сообщений получать только определенные значения.

Функции фильтрации важны, так как они позволяют соединять блоки сообщений для создания *сети потоков данных*. В сети потока данных блоки сообщений управлять потоком данных, обработку только этих сообщений, соответствующих заданным критериям. Сравните это с моделью потока управления, где поток данных контролируется с помощью структур управления, такие как условные операторы, циклы и так далее.

Этот документ содержит простой пример того, как использовать фильтр сообщений. Дополнительные примеры использования фильтров сообщений и модели потока данных для подключения блоков сообщений см. в разделе [Пошаговое руководство: создание агента потоков данных](../../parallel/concrt/walkthrough-creating-a-dataflow-agent.md) и [Пошаговое руководство: создание сети обработки изображений](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md) .

## <a name="example"></a>Пример

Рассмотрим следующую функцию, `count_primes`, который иллюстрирует основное использование блока сообщений, который фильтрует входящие сообщения. Блок сообщений добавляет простые числа к [std::vector](../../standard-library/vector-class.md) объекта. `count_primes` Функция отправляет несколько чисел в блок сообщений, Получает выходные значения из блока сообщений и выводит эти простые числа в консоль.

[!code-cpp[concrt-primes-filter#1](../../parallel/concrt/codesnippet/cpp/how-to-use-a-message-block-filter_1.cpp)]

`transformer` Объект обрабатывает все входные значения; Однако он требует только простые числа. Несмотря на то, что приложение может быть записан, таким образом, чтобы отправитель отправляет только простые числа, не всегда известны требования получателя сообщения.

## <a name="example"></a>Пример

Следующая функция `count_primes_filter`, выполняет ту же задачу, что `count_primes` функции. Тем не менее `transformer` объект в этой версии использует функцию фильтрации, чтобы принять только простые числа. Функция, которая выполняет действие принимает только простые числа; Таким образом, его не требуется вызывать `is_prime` функции.

Так как `transformer` объект получает только простые числа, `transformer` может сам содержать простые числа. Другими словами `transformer` объект в этом примере не должен добавлять простые числа к `vector` объекта.

[!code-cpp[concrt-primes-filter#2](../../parallel/concrt/codesnippet/cpp/how-to-use-a-message-block-filter_2.cpp)]

`transformer` Объект теперь обрабатывает только простые числа. В предыдущем примере `transformer` объект обрабатывает все сообщения. Таким образом предыдущий пример должен получить одинаковое количество сообщений, которые оно отправляет. В этом примере используется результат [concurrency::send](reference/concurrency-namespace-functions.md#send) функцию, чтобы определить, сколько сообщений нужно получить от `transformer` объекта. `send` Возвращает **true** если буфер сообщений принимает сообщение и **false** когда буфер сообщений отклоняет сообщение. Таким образом сколько раз, что буфер сообщений принимает сообщение соответствует количество простых чисел.

## <a name="example"></a>Пример

Ниже приведен полный пример кода. Пример вызывает и `count_primes` функции и `count_primes_filter` функции.

[!code-cpp[concrt-primes-filter#3](../../parallel/concrt/codesnippet/cpp/how-to-use-a-message-block-filter_3.cpp)]

## <a name="compiling-the-code"></a>Компиляция кода

Скопируйте код примера и вставьте его в проект Visual Studio или вставьте его в файл с именем `primes-filter.cpp` и выполните следующую команду в окне командной строки Visual Studio.

**/ EHsc CL.exe primes-filter.cpp**

## <a name="robust-programming"></a>Отказоустойчивость

Функции фильтра может быть лямбда-функцию, указатель на функцию или объект функции. Каждая функция filter принимает одно из следующих форм:

```Output
bool (T)
bool (T const &)
```

Чтобы избежать ненужных операций копирования данных, используйте вторую форму при наличии Агрегатный тип, который передается по значению.

## <a name="see-also"></a>См. также

[Библиотека асинхронных агентов](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[Пошаговое руководство. Создание агента потоков данных](../../parallel/concrt/walkthrough-creating-a-dataflow-agent.md)<br/>
[Пошаговое руководство. Создание сети обработки изображений](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md)<br/>
[Класс transformer](../../parallel/concrt/reference/transformer-class.md)
