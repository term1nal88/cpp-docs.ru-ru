---
title: Ошибка компилятора C2886 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2886
dev_langs:
- C++
helpviewer_keywords:
- C2886
ms.assetid: c01588a1-484c-4dc9-a3f1-f900c6e44543
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 271ee8341cb5faa033d3fb5ec3238f36975c3531
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46023583"
---
# <a name="compiler-error-c2886"></a>Ошибка компилятора C2886

«класс::идентификатор»: символ не может использоваться в с помощью объявление члена

Объект `using` объявлении используется символ, например имя пространства имен. Объект `using` объявления предназначены для объявления членов базового класса.

Следующий пример приводит к возникновению ошибки C2886:

```
// C2886.cpp
// compile with: /c
namespace Z {
    int i;
}

class B {
protected:
    int i;
};

class D : public B {
    // Error: Z is a namespace
    using Z::i;   // C2886

    // OK: B is a base class
    using B::i;
};
```