---
title: Ошибка компилятора C2249 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2249
dev_langs:
- C++
helpviewer_keywords:
- C2249
ms.assetid: bdd6697c-e04b-49b9-8e40-d9eb6d74f2b6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cb9c73ca311b767d9fdb50dd55a832cf8fcc2a4b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46089896"
---
# <a name="compiler-error-c2249"></a>Ошибка компилятора C2249

«член»: нет доступного пути к члену, объявленному в виртуальном базовом «class»

`member` Наследуется из закрытого `virtual` базового класса или структуры.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2249.

```
// C2249.cpp
class A {
private:
   void privFunc( void ) {};
public:
   void pubFunc( void ) {};
};

class B : virtual public A {} b;

int main() {
   b.privFunc();    // C2249, private member of A
   b.pubFunc();    // OK
}
```

## <a name="example"></a>Пример

C2249 также может возникать при попытке назначить поток из стандартной библиотеки C++ в другой поток.  Следующий пример приводит к возникновению ошибки C2249.

```
// C2249_2.cpp
#include <iostream>
using namespace std;
int main() {
   cout = cerr;   // C2249
   #define cout cerr;   // OK
}
```