---
title: Ошибка компилятора C3628 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3628
dev_langs:
- C++
helpviewer_keywords:
- C3628
ms.assetid: 0ff5a4a4-fcc9-47a0-a4d8-8af9cf2815f6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9a65dc33c5381b063c3adb01072e930075108649
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46037376"
---
# <a name="compiler-error-c3628"></a>Ошибка компилятора C3628

«базовый класс»: управляемый или WinRTclasses поддерживают только открытое наследование

Была предпринята попытка использовать управляемый или WinRT классов как [частного](../../cpp/private-cpp.md) или [защищенные](../../cpp/protected-cpp.md) базового класса. Управляемого массива или класса WinRT может использоваться только как базовый класс с [открытый](../../cpp/public-cpp.md) доступа.

В следующем примере показано возникновение ошибки C3628 и приводятся сведения по ее устранению.

```
// C3628a.cpp
// compile with: /clr
ref class B {
};

ref class D : private B {   // C3628

// The following line resolves the error.
// ref class D : public B {
};

int main() {
}
```
