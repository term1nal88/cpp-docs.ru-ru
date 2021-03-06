---
title: Интерпретация сложных деклараторов | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- complex declarators
- interpreting complex declarators
ms.assetid: dd5b7019-c86d-4645-a5cc-21f834de6f4a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6fc5b831d00c83569bc01a5580f511d126fb97bf
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46083110"
---
# <a name="interpreting-more-complex-declarators"></a>Интерпретация сложных деклараторов

Любой декларатор можно заключить в круглые скобки, чтобы указать конкретную интерпретацию "сложного декларатора". Сложный декларатор представляет собой идентификатор с более чем одним модификатором массива, указателя или функции. К одному идентификатору можно применять различные сочетания модификаторов массива, указателя или функции. Обычно для упрощения объявлений можно использовать определения `typedef`. См. статью [Объявления Typedef](../c-language/typedef-declarations.md).

При интерпретации сложных деклараторов квадратные и круглые скобки (т. е., модификаторы справа от идентификатора) имеют приоритет над звездочками (т. е., модификаторами слева от идентификатора). Квадратные и круглые скобки имеют одинаковый приоритет и задают связывание слева направо. После полной интерпретации декларатора на последнем шаге производится применение спецификатора типа. С помощью круглых скобок можно переопределить порядок связи по умолчанию и принудительно задать определенную интерпретацию. Однако не допускается использование скобок непосредственно вокруг имени идентификатора. Это может быть ошибочно истолковано как список параметров.

Простым способом интерпретации сложных деклараторов является чтение "изнутри наружу", с помощью следующих 4 шагов:

1. Начните с идентификатора и найдите ближайшие квадратные или круглые скобки справа от него (если есть).

1. Интерпретируйте эти квадратные или круглые скобки, затем найдите звездочку слева.

1. Если на каком-либо шаге обнаружится правая круглая скобка, перейдите назад и примените правила 1 и 2 ко всему выражению в круглых скобках.

1. Примените спецификатор типа.

    ```
    char *( *(*var)() )[10];
     ^   ^  ^ ^ ^   ^    ^
     7   6  4 2 1   3    5
    ```

В этом примере шаги пронумерованы по порядку и интерпретируются следующим образом:

1. Идентификатор `var` объявлен как

1. указатель на

1. функцию, возвращающую

1. указатель на

1. массив из 10 элементов, которые являются

1. указателями на

1. значения типа `char`.

## <a name="examples"></a>Примеры

В следующих примерах приведены другие сложные объявления и показано, как круглые скобки могут влиять на значение объявления.

```
int *var[5]; /* Array of pointers to int values */
```

Модификатор массива имеет более высокий приоритет, чем модификатор указателя, поэтому переменная `var` объявляется как массив. Модификатор указателя применяется к типу элементов массива; следовательно, элементы массива являются указателями на значения `int`.

```
int (*var)[5]; /* Pointer to array of int values */
```

В этом объявлении переменной `var` скобки обеспечивают модификатору указателя более высокий приоритет, чем у модификатора массива, и переменная `var` объявляется как указатель на массив из 5 значений `int`.

```
long *var( long, long ); /* Function returning pointer to long */
```

Модификаторы функции также имеют более высокий приоритет, чем модификаторы указателя, поэтому в этом объявлении `var` переменная `var` объявляется как функция, возвращающая указатель на значение **long**. В соответствии с объявлением функция принимает два значения **long** в качестве аргументов.

```
long (*var)( long, long ); /* Pointer to function returning long */
```

Этот пример аналогичен предыдущему. Скобки отдают модификатору указателя более высокий приоритет, чем у модификатора функции, и переменная `var` объявляется как указатель на функцию, возвращающую значение **long**. Как и ранее, эта функция принимает два аргумента типа **long**.

```
struct both       /* Array of pointers to functions */
{                 /*   returning structures         */
    int a;
    char b;
} ( *var[5] )( struct both, struct both );
```

Элементы массива не могут быть функциями, но это объявление показывает, как объявить массив указателей на функции. В данном примере переменная `var` объявляется как массив из 5 указателей на функции, возвращающие структуры с двумя членами. В качестве аргументов для функций объявлены две структуры с тем же типом структуры, `both`. Обратите внимание, что скобки вокруг `*var[5]` обязательны. Без них объявление было бы недопустимой попыткой объявить массив функций, как показано ниже:

```
/* ILLEGAL */
struct both *var[5](struct both, struct both);
```

Следующий оператор объявляет массив указателей.

```
unsigned int *(* const *name[5][10] ) ( void );
```

Массив `name` содержит 50 элементов, организованных в многомерный массив. Элементы являются указателями на указатель, представляющий собой константу. Этот постоянный указатель указывает на функцию, которая не имеет параметров и возвращает указатель на тип без знака.

В следующем примере показана функция, возвращающая указатель на массив из трех значений **double**.

```
double ( *var( double (*)[3] ) )[3];
```

В этом объявлении функция возвращает указатель на массив, поскольку функции не могут возвращать массивы. Здесь переменная `var` объявлена как функция, возвращающая указатель на массив из трех значений **double**. Функция `var` принимает один аргумент. Аргумент, как и возвращаемое значение, является указателем на массив из трех значений **double**. Тип аргумента задан сложным абстрактным декларатором *abstract-declarator*. Скобки вокруг звездочки в типе аргумента обязательны. Без них аргумент будет иметь тип массива из трех указателей на значения **double**. Обсуждение и примеры абстрактных деклараторов см. в статье [Абстрактные деклараторы](../c-language/c-abstract-declarators.md).

```
union sign         /* Array of arrays of pointers */
{                  /* to pointers to unions       */
     int x;
     unsigned y;
} **var[5][5];
```

Как показано в приведенном выше примере, указатель может указывать на другой указатель, и массив может содержать элементы, являющиеся массивами. Здесь переменная `var` представляет собой массив из 5 элементов. Каждый элемент представляет собой 5-элементный массив указателей на объединения с двумя членами.

```
union sign *(*var[5])[5]; /* Array of pointers to arrays
                             of pointers to unions        */
```

В этом примере показано, как круглые скобки изменяют значение объявления. В этом примере переменная `var` является 5-элементным массивом указателей на 5-элементные массивы указателей на объединения. Примеры применения `typedef` для исключения сложных объявлений см. в статье [Объявления Typedef](../c-language/typedef-declarations.md).

## <a name="see-also"></a>См. также

[Объявления и типы](../c-language/declarations-and-types.md)
