---
title: Ошибка компилятора C2823 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2823
dev_langs:
- C++
helpviewer_keywords:
- C2823
ms.assetid: 982b1b35-1a7c-456e-b711-f80cfe2d571e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 09b8284626a6af6851147dc36b67e25b76f8eb01
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46069525"
---
# <a name="compiler-error-c2823"></a>Ошибка компилятора C2823

> шаблон typedef не допускается

Шаблоны не допускаются в `typedef` определений.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2823 и показан один из способов ее устранения:

```cpp
// C2823.cpp
template<class T>
typedef struct x {
   T i;   // C2823 can't use T, specify data type and delete template
   int i;   // OK
} x1;
```