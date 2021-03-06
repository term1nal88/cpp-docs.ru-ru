---
title: Как блоки Catch, вычисляется (C++) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- try-catch keyword [C++], catchable types
- catch keyword [C++], types of catch handlers
- C++ exception handling, catch handlers
- exception handling, catching and deleting exceptions
- types [C++], exception handling
ms.assetid: 202dbf07-8ace-4b3b-b3ae-4b45c275e0b4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fe86770692554551b88e1aef9bbddc509e21f0f0
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46039443"
---
# <a name="how-catch-blocks-are-evaluated-c"></a>Проверка блоков Catch (C++)

C++ позволяет создавать исключения любого типа, хотя обычно рекомендуется создавать типы, производные от std::exception. Может быть перехвачено исключение C++ **catch** обработчик, который указывает тот же тип, как исключение, или обработчиком, который способен перехватывать любой тип исключения.

Если созданное исключение имеет тип класса, у которого имеется один или несколько базовых классов, то его могут перехватывать обработчики, которые принимают базовые классы (и ссылки на базовые классы) этого типа исключения. Обратите внимание, что если исключение перехватывается по ссылке, то оно привязывается к самому объекту исключения; в противном случае обрабатывается его копия (как и в случае с аргументами функции).

Если создается исключение, он может перехватываться следующие виды **catch** обработчиков:

- Обработчик, который может принимать любой тип данных (синтаксис с многоточием).

- Обработчик, который принимает тот же тип, что объект исключения; Поскольку это копия, **const** и **volatile** модификаторы учитываются.

- Обработчик, который принимает ссылку на тот же тип, что и у объекта исключения.

- Обработчик, который принимает ссылку на **const** или **volatile** форме тот же тип, что объект исключения.

- Обработчик, который принимает базовый класс того же типа, что и объект исключения; Поскольку это копия, **const** и **volatile** модификаторы учитываются. **Catch** обработчик для базового класса не должен предшествовать **catch** обработчик для производного класса.

- Обработчик, который принимает ссылку на базовый класс того же типа, что и у объекта исключения.

- Обработчик, который принимает ссылку на **const** или **volatile** формы базового класса в тот же тип, что объект исключения.

- Обработчик, который принимает указатель, в который можно преобразовать созданный объект указателя при помощи стандартных правил преобразования указателей.

Порядок, в котором **catch** располагаются обработчики имеет большое значение, так как обработчики для заданного **попробуйте** блок проверяются в порядке их отображения. Например, ошибкой будет поместить обработчик для базового класса перед обработчиком для производного класса. После соответствующего **catch** обработчик найден, последующие обработчики не проверяются. В результате многоточие **catch** обработчик должен быть последним обработчиком для его **попробуйте** блока. Пример:

```cpp
// ...
try
{
    // ...
}
catch( ... )
{
    // Handle exception here.
}
// Error: the next two handlers are never examined.
catch( const char * str )
{
    cout << "Caught exception: " << str << endl;
}
catch( CExcptClass E )
{
    // Handle CExcptClass exception here.
}
```

В этом примере кнопку с многоточием **catch** это единственный обработчик, который проверяется.

## <a name="see-also"></a>См. также

[Обработка исключений С++](../cpp/cpp-exception-handling.md)