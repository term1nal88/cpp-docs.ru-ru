---
title: Ошибка компилятора C3371 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3371
dev_langs:
- C++
helpviewer_keywords:
- C3371
ms.assetid: f7ecf1aa-ed0a-4f73-81e5-62cf98f88ea1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a6156f305ce49266366ffc42504232614c6987eb
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46081836"
---
# <a name="compiler-error-c3371"></a>Ошибка компилятора C3371

idl_module: здесь допускается только свойство "name"

Использование[idl_module](../../windows/idl-module.md) непосредственно в объявлении функции не может иметь никакие параметры, кроме имени.

В следующем примере возникает ошибка C3371:

```
// C3371.cpp
[idl_module(name="Name", dllname="Some.dll")];
[idl_module(name="Name", helpstring="Some help")]   // C3371
int f1();
// try
// [idl_module(name="Name")]
// int f1();

int main()
{
}
```