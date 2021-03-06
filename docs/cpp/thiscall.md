---
title: __thiscall | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __thiscall
- __thiscall_cpp
dev_langs:
- C++
helpviewer_keywords:
- __thiscall keyword [C++]
ms.assetid: a6a22dd2-0101-4885-b33b-22f6057965df
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: af20b6d406b0e2119df04d5348c554b3405e8597
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46103377"
---
# <a name="thiscall"></a>__thiscall

**Блок, относящийся только к системам Microsoft**

**__Thiscall** соглашения о вызове используется для функций-членов и по умолчанию соглашение о вызове используемых функций-членов C++, которые не используют переменные аргументы. В разделе **__thiscall**, вызываемый объект очищает стек, что невозможно для `vararg` функции. Аргументы помещаются в стек справа налево, с помощью **это** указателя передается через регистр ECX, а не на стеке, x86 архитектуры.

Одна из причин для использования **__thiscall** в классах, чьи функции-члены используйте `__clrcall` по умолчанию. В этом случае можно использовать **__thiscall** чтобы отдельных член функции можно вызывать из машинного кода.

При компиляции с параметром [/CLR: pure](../build/reference/clr-common-language-runtime-compilation.md), все функции и указатели функций являются `__clrcall` Если не указано иное. **/CLR: pure** и **/CLR: safe** параметры компилятора признаны устаревшими в Visual Studio 2015 и не поддерживается в Visual Studio 2017.

В предыдущих выпусках Visual C++ 2005 **__thiscall** соглашение о вызовах нельзя указывать явным образом в программе, поскольку **__thiscall** не являлось ключевым словом.

`vararg` Использование функции-члены **__cdecl** соглашение о вызовах. Все аргументы функции передаются в стеке, с помощью **это** указатель, помещаемый в стек последнего

Поскольку это соглашение о вызовах применяется только к C++, схема оформления имени C отсутствует.

В ARM и x64 машин, **__thiscall** принимается и игнорируется компилятором.

Если используется внестрочное определение нестатической функции класса, то модификатор соглашения о вызовах не должен быть задан во внестрочном определении. То есть для нестатических методов-членов считается, что соглашение о вызовах, указанное во время объявления, было сделано в точке определения.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Передача аргументов и соглашения об именовании](../cpp/argument-passing-and-naming-conventions.md)