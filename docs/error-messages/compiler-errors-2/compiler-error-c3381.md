---
title: Ошибка компилятора C3381 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3381
dev_langs:
- C++
helpviewer_keywords:
- C3381
ms.assetid: d276c89f-8377-4cb6-a8d4-7770885f06c4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7bd6c1d641f7476d3c372939b948931a306e0f80
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46080718"
---
# <a name="compiler-error-c3381"></a>Ошибка компилятора C3381

«сборка»: спецификаторы доступа к сборке доступны только в коде, скомпилированном с параметром/CLR

Собственные типы могут быть отображены за пределами сборки, но можно указать только доступ к сборке для собственных типов в **/CLR** компиляции.

Дополнительные сведения см. в разделе [введите видимость](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility) и [/CLR (компиляция CLR)](../../build/reference/clr-common-language-runtime-compilation.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3381.

```
// C3381.cpp
// compile with: /c
public class A {};   // C3381
```