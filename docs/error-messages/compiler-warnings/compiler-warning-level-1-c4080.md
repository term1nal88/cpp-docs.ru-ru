---
title: Предупреждение компилятора (уровень 1) C4080 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4080
dev_langs:
- C++
helpviewer_keywords:
- C4080
ms.assetid: 964fb3f4-b9fd-450b-aa23-35cece126172
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 08ec1b7c65342ece3a7aebae673fce9a0d19b7a6
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46074712"
---
# <a name="compiler-warning-level-1-c4080"></a>Предупреждение компилятора (уровень 1) C4080

Требуется идентификатор для имени сегмента; имеется "символ"

Имя сегмента в [#pragma alloc_text](../../preprocessor/alloc-text.md) должно быть строкой или идентификатором. Компилятор игнорирует директиву pragma, если не удается найти допустимый идентификатор.

При компиляции следующего примера будет выдано предупреждение C4080:

```
// C4080.cpp
// compile with: /W1
extern "C" void func(void);

#pragma alloc_text()   // C4080

// try this line to resolve the warning
// #pragma alloc_text("mysection", func)

int main() {
}

void func(void) {
}
```