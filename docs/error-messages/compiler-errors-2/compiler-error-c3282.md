---
title: Ошибка компилятора C3282 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3282
dev_langs:
- C++
helpviewer_keywords:
- C3282
ms.assetid: bac2ac89-c360-4c24-bb81-c20c62ece9ba
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: da6d4fd30d109f78949a3ec53e0d46d6a9de7dc9
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46056902"
---
# <a name="compiler-error-c3282"></a>Ошибка компилятора C3282

универсальный параметр, списки появляются только в управляемые или WinRTclasses, структурах или функциях

Список универсальных параметров был использован неправильно.  Дополнительные сведения см. в статье [Универсальные шаблоны](../../windows/generics-cpp-component-extensions.md).

## <a name="example"></a>Пример

В следующем примере показано возникновение ошибки C3282 и приводятся сведения по ее устранению.

```
// C3282.cpp
// compile with: /clr /c
generic <typename T> int x;   // C3282

ref struct GC0 {
   generic <typename T> int x;   // C3282
};

// OK
generic <typename T>
ref class M {};
```