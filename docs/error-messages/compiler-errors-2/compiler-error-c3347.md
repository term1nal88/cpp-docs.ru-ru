---
title: Ошибка компилятора C3347 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3347
dev_langs:
- C++
helpviewer_keywords:
- C3347
ms.assetid: e939ad29-0b78-4681-9618-9bdae5675cee
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 824d2e787ae613636c20c0cc79ae3167431a8fe7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46015732"
---
# <a name="compiler-error-c3347"></a>Ошибка компилятора C3347

"arg": обязательный аргумент не указан в атрибуте "idl_module"

Обязательный аргумент не передан в атрибут [idl_module](../../windows/idl-module.md) .

Следующий пример приводит к возникновению ошибки C3347:

```
// C3347.cpp
// compile with: /c
[module(name="xx")];

[idl_module(dllname="x")];    // C3347
// try the following line instead
// [idl_module(name="test", dllname="x")];
```