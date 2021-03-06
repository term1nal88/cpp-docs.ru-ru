---
title: Предупреждение компилятора (уровень 1) C4350 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4350
dev_langs:
- C++
helpviewer_keywords:
- C4350
ms.assetid: 4cc8ed67-64c4-4da5-a7a5-a639232baa23
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5ad49a7471be257fa0c22f66fa1bb2bbea049194
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46096695"
---
# <a name="compiler-warning-level-1-c4350"></a>Предупреждение компилятора (уровень 1) C4350

изменение поведения: "член 1" был вызван вместо "член 2"

Rvalue не может быть привязан к неконстантная ссылка. В версиях Visual C++ до Visual Studio 2003 можно было выполнить привязку к неконстантная ссылка в прямой инициализации rvalue. Этот код выводит предупреждение.

Для обеспечения обратной совместимости по-прежнему можно выполнять привязку значений rvalue к ссылкам на отличный от const, но стандартные преобразования являются предпочтительными, когда это возможно.

Это предупреждение представляет изменение поведения компилятора Visual C++ .NET 2002. Если параметр включен, это предупреждение может быть выведено для правильный код. Например, она может иметь при использовании **std::auto_ptr** шаблона класса.

Если это предупреждение появляется, проверьте код ли это зависит от значения rvalue привязки для константной ссылки. Добавление константную ссылку или предоставления дополнительной перегрузки константной может устранить проблему.

Это предупреждение отключено по умолчанию. Дополнительные сведения см. в разделе [Compiler Warnings That Are Off by Default](../../preprocessor/compiler-warnings-that-are-off-by-default.md).

Следующий пример приводит к возникновению ошибки C4350:

```cpp
// C4350.cpp
// compile with: /W1
#pragma warning (default : 4350)
class A {};

class B
{
public:
   B(B&){}
   // try the following instead:
   // B(const B&){}

   B(A){}
   operator A(){ return A();}
};

B source() { return A(); }

int main()
{
   B ap(source());   // C4350
}
```