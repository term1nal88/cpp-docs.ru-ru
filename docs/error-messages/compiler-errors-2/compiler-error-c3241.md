---
title: Ошибка компилятора C3241 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3241
dev_langs:
- C++
helpviewer_keywords:
- C3241
ms.assetid: 2ca14879-bba0-4a23-b22a-72cfff92d6a4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6f78346c91d7f103d1392081a90d982f3d99b493
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46020242"
---
# <a name="compiler-error-c3241"></a>Ошибка компилятора C3241

«метод»: этот метод не был создан «интерфейс»

При явном переопределении функции, сигнатура функции должно совпадать объявление для переопределяемой функции.

Следующий пример приводит к возникновению ошибки C3241:

```
// C3241.cpp
#pragma warning(disable:4199)

__interface IX12A {
   void mf();
};

__interface IX12B {
   void mf(int);
};

class CX12 : public IX12A, public IX12B { // C3241
   void IX12A::mf(int);
};
```