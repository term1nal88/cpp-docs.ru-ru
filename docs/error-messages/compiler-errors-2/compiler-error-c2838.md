---
title: Ошибка компилятора C2838 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2838
dev_langs:
- C++
helpviewer_keywords:
- C2838
ms.assetid: 176b2ad6-7a84-4019-b97e-328866054457
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c5607df86a44174536f58242c5c0a98f7fe5e7dc
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46045280"
---
# <a name="compiler-error-c2838"></a>Ошибка компилятора C2838

«член»: Недопустимое полное имя в объявлении члена

Класс, структура или объединение использует полное доменное имя для повторного объявления члена другого класса, структуры или объединения.

Следующий пример приводит к возникновению ошибки C2838:

```
// C2838.cpp
// compile with: /c
class Bellini {
public:
    void Norma();
};

class Bottesini {
   Bellini::Norma();  // C2838
};
```