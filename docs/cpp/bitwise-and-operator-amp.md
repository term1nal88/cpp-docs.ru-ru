---
title: 'Оператор побитового и: &amp; | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- bitand
dev_langs:
- C++
helpviewer_keywords:
- AND operator
- bitwise operators [C++], AND operator
- '& operator [C++], bitwise operators'
ms.assetid: 76f40de3-c417-47b9-8a77-532f3fc990a5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a8967861ab6ac4e6b6fafd11eea22e67de339ea8
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46111385"
---
# <a name="bitwise-and-operator-amp"></a>Оператор побитового и: &amp;

## <a name="syntax"></a>Синтаксис

```
expression & expression
```

## <a name="remarks"></a>Примечания

Выражения могут представлять собой другие and-выражения или (в зависимости от упомянутых ниже типов ограничений) выражения равенства, выражения связей, выражения сложения, выражения умножения, выражения указателя на член, выражения приведения, унарные выражения, постфиксные выражения или основные выражения.

Побитовый оператор AND (**&**) сравнивает каждый бит первого операнда с соответствующим битом второго операнда. Если оба бита равны 1, соответствующий бит результата устанавливается равным единице. в противном случае — нулю.

Оба операнда оператора побитового И должны иметь целочисленный тип. Обычные арифметические преобразования, описанные в [стандартные преобразования](standard-conversions.md), применяются к операндам.

## <a name="operator-keyword-for-"></a>Ключевое слово оператора &

**Bitand** оператор является текстовым эквивалентом **&**. Существует два способа для доступа к **bitand** оператор в программах: включить файл заголовка `iso646.h`, или выполнить компиляцию с [/Za](../build/reference/za-ze-disable-language-extensions.md) параметр компилятора (отключить расширения языка).

## <a name="example"></a>Пример

```cpp
// expre_Bitwise_AND_Operator.cpp
// compile with: /EHsc
// Demonstrate bitwise AND
#include <iostream>
using namespace std;
int main() {
   unsigned short a = 0xFFFF;      // pattern 1111 ...
   unsigned short b = 0xAAAA;      // pattern 1010 ...

   cout  << hex << ( a & b ) << endl;   // prints "aaaa", pattern 1010 ...
}
```

## <a name="see-also"></a>См. также

[Встроенные операторы C++, приоритет и ассоциативность](cpp-built-in-operators-precedence-and-associativity.md)<br/>
[Встроенные операторы C++, приоритет и ассоциативность](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[Побитовые операторы в C](../c-language/c-bitwise-operators.md)