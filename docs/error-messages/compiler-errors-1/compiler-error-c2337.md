---
title: Ошибка компилятора C2337 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2337
dev_langs:
- C++
helpviewer_keywords:
- C2337
ms.assetid: eccc9178-a15e-42cd-bbd0-3cea7cf2d55b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f1b3ed1193d7a5c81e84a152bd01a26bfd04bab0
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46105522"
---
# <a name="compiler-error-c2337"></a>Ошибка компилятора C2337

"имя_атрибута": атрибут не найден

Используется атрибут, который не поддерживается в этой версии Visual C++.

Следующий пример приводит к возникновению ошибки C2337:

```
// C2337.cpp
// compile with: /c
[emitidl];
[module(name="x")];
[grasshopper]   // C2337, not a supported attribute
class a{};
```