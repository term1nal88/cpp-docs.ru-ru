---
title: Вызовы функций | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- function calls, C functions
- functions [C], calling
- function calls, about function calls
- function calls
ms.assetid: 2cfa897d-3874-4820-933c-e624f75d1712
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cd62a5a4d2ef4c4b2337557b9eb6a37533167dc0
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46016927"
---
# <a name="function-calls"></a>Вызовы функций

*Вызовом функции* называется выражение, которое передает функции управление и аргументы (если они есть). Такие выражения имеют следующую форму:

*expression* (*expression-list*<sub>opt</sub>)

где *expression* — это имя функции или выражение, результатом которого является адрес функции, а *expression-list* содержит список выражений, разделенных запятыми. Значения этих выражений являются аргументами, которые передаются функции. Если функция не возвращает значения, то при ее объявлении необходимо указать, что она возвращает тип `void`.

Если объявление указывается до вызова функции, однако информация о ее параметрах не приводится, то для любых необъявленных аргументов выполняются обычные арифметические преобразования.

> [!NOTE]
>  Выражения в списке аргументов функции могут оцениваться в любом порядке, поэтому аргументы, значения которых могут изменяться в качестве побочного эффекта других аргументов, имеют неопределенные значения. Точка следования, определяемая оператором вызова функции, гарантирует только то, что все побочные эффекты в списке аргументов будут оценены до того, как управление будет передано вызванной функции. (Обратите внимание, что порядок, в котором аргументы отправляются в стек, — это отдельная тема.) Дополнительные сведения см. в разделе [Точки следования](../c-language/c-sequence-points.md).

Единственное требование к любому вызову функции заключается в том, что выражение перед скобками должно иметь своим результатом адрес функции. Это означает, что функцию можно вызвать любым выражением, значением которого является указатель функции.

## <a name="example"></a>Пример

В следующем примере представлен вызов функций, совершаемый из оператора `switch`:

```
int main()
{
    /* Function prototypes */

    long lift( int ), step( int ), drop( int );
    void work( int number, long (*function)(int i) );

    int select, count;
    .
    .
    .
    select = 1;
    switch( select )
    {
        case 1: work( count, lift );
                break;

        case 2: work( count, step );
                break;

        case 3: work( count, drop );
                /* Fall through to next case */
        default:
                break;
    }
}

/* Function definition */

void work( int number, long (*function)(int i) )
{
    int i;
    long j;

    for ( i = j = 0; i < number; i++ )
            j += ( *function )( i );
}
```

В этом примере вызов функции располагается в функции `main`:

```
work( count, lift );
```

Он передает функции `count` целочисленную переменную `lift`, а также адрес функции `work`. Обратите внимание, что адрес функции передается просто в виде идентификатора функции, поскольку он равен выражению указателя. Чтобы идентификатор функции можно было использовать таким образом, функцию необходимо объявить и определить до того, как будет использован идентификатор; в противном случае идентификатор не будет распознан. В этом случае прототип функции `work` задан в начале функции `main`.

Параметр `function` в функции `work` объявлен как указатель на функцию, принимающую один аргумент типа `int` и возвращающую значение типа **long**. Скобки вокруг имени параметра являются обязательными. Без них это объявление будет означать, что функция возвращает указатель на значение типа **long**.

Функция `work` вызывает выбранную функцию из цикла **for**, используя следующий формат вызова:

```
( *function )( i );
```

Вызываемой функции передается один аргумент, `i`:

## <a name="see-also"></a>См. также

[Функции](../c-language/functions-c.md)