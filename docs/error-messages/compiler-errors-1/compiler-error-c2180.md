---
title: Ошибка компилятора C2180 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2180
dev_langs:
- C++
helpviewer_keywords:
- C2180
ms.assetid: ea71b39e-b977-48a7-b7bd-af68ef5e263b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9c74912b92162cbfcada3630ed6a6845b67045d0
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46084150"
---
# <a name="compiler-error-c2180"></a>Ошибка компилятора C2180

управляющее выражение имеет тип type

Управляющее выражение в `if`, `while`, `for` или инструкция `do` — это выражение, приведенное к `void`. Чтобы устранить эту проблему, измените управляющее выражение на то, что создает `bool` или тип, который можно преобразовать в `bool`.

Следующий пример приводит к возникновению ошибки C2180:

```
// C2180.c

int main() {
   while ((void)1)   // C2180
      return 1;
   while (1)         // OK
      return 0;
}
```