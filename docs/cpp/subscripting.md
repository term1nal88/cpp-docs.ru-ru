---
title: Подписи пропущена | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- subscript operator [C++], overloaded
- arrays [C++], subscripting
- subscripting [C++]
- operators [C++], overloading
- operator overloading [C++], examples
- subscript operator
ms.assetid: eb151281-6733-401d-9787-39ab6754c62c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d3586e942f10a00c1d9e94aac62d18f5b6b96707
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46117690"
---
# <a name="subscripting"></a>Индексация ;

Оператор индекса (**[]**), например оператор вызова функции, считается бинарным оператором. Оператор индекса должен быть нестатической функцией-членом, которая принимает один аргумент. Этот аргумент может быть любого типа и определяет требуемый индекс массива.

## <a name="example"></a>Пример

Следующий пример демонстрирует, как создать вектор типа **int** котором реализована проверка границ:

```cpp
// subscripting.cpp
// compile with: /EHsc
#include <iostream>

using namespace std;
class IntVector {
public:
   IntVector( int cElements );
   ~IntVector() { delete [] _iElements; }
   int& operator[](int nSubscript);
private:
   int *_iElements;
   int _iUpperBound;
};

// Construct an IntVector.
IntVector::IntVector( int cElements ) {
   _iElements = new int[cElements];
   _iUpperBound = cElements;
}

// Subscript operator for IntVector.
int& IntVector::operator[](int nSubscript) {
   static int iErr = -1;

   if( nSubscript >= 0 && nSubscript < _iUpperBound )
      return _iElements[nSubscript];
   else {
      clog << "Array bounds violation." << endl;
      return iErr;
   }
}

// Test the IntVector class.
int main() {
   IntVector v( 10 );
   int i;

   for( i = 0; i <= 10; ++i )
      v[i] = i;

   v[3] = v[9];

   for ( i = 0; i <= 10; ++i )
      cout << "Element: [" << i << "] = " << v[i] << endl;
}
```

```Output
Array bounds violation.
Element: [0] = 0
Element: [1] = 1
Element: [2] = 2
Element: [3] = 9
Element: [4] = 4
Element: [5] = 5
Element: [6] = 6
Element: [7] = 7
Element: [8] = 8
Element: [9] = 9
Array bounds violation.
Element: [10] = 10
```

## <a name="comments"></a>Комментарии

Когда `i` достигается значение 10 в предыдущей программе **operator []** обнаруживает, что выхода за допустимые границы индекса используется и выдает предупреждение об ошибке.

Обратите внимание, что функция **operator []** возвращает ссылочный тип. В результате она является значением l-value, что позволяет использовать выражения с индексами с любой стороны операторов присваивания.

## <a name="see-also"></a>См. также

[Перегрузка операторов](../cpp/operator-overloading.md)