---
title: Ошибка компилятора C2808 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2808
dev_langs:
- C++
helpviewer_keywords:
- C2808
ms.assetid: 3d745102-d3b3-4735-a7d2-ad42d5bf3cfa
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e4d256fd07f717137f6afe890884f3c1f54944ec
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46055927"
---
# <a name="compiler-error-c2808"></a>Ошибка компилятора C2808

унарный оператор «оператор» имеет слишком много формальных параметров

Унарный оператор имеет недействительный список параметров.

Следующий пример приводит к возникновению ошибки C2808:

```
// C2808.cpp
// compile with: /c
class X {
public:
   X operator! ( X );   // C2808 nonvoid parameter list
   X operator! ( void );   // OK
};

```