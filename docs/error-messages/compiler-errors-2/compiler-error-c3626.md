---
title: Ошибка компилятора C3626 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3626
dev_langs:
- C++
helpviewer_keywords:
- C3626
ms.assetid: 43926e2b-1ba9-4a43-9343-c58449cbb336
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ba6fb7c03c7c957999ca75e3946e4f78d290b78a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46094706"
---
# <a name="compiler-error-c3626"></a>Ошибка компилятора C3626

«ключевое_слово»: ключевое слово «__event» может использоваться только в интерфейсах COM, функции-члены и члены данных, которые являются указателями на делегаты

Ключевое слово был использован неправильно.

Следующий пример приводит к возникновению ошибки C3626:

```
// C3626.cpp
// compile with: /c
struct A {
   __event int i;   // C3626
// try the following line instead
// __event int i();
};
```