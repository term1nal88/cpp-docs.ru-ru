---
title: Модификаторы, используемые Microsoft | Документация Майкрософт
ms.custom: ''
ms.date: 08/16/2018
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 22c7178c-f854-47fa-9de6-07d23fda58e1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b845ccb24d6d7a93767ec3c3219562c1c87bf81f
ms.sourcegitcommit: a738519aa491a493a8f213971354356c0e6a5f3a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/05/2018
ms.locfileid: "48820250"
---
# <a name="microsoft-specific-modifiers"></a>Модификаторы, используемые в системах Майкрософт

В этом разделе описываются специальные расширения Microsoft для C++ в следующих аспектах языка:

- [Базовые адреса](based-addressing.md), способ использования указатель как базовый, из которого могут быть смещены других указателей

- [О вызовах функций](calling-conventions.md)

- Расширенные атрибуты классов хранения, объявленные с [__declspec](declspec.md) ключевое слово

- [__W64](w64.md) ключевое слово

## <a name="microsoft-specific-keywords"></a>Ключевые слова для систем Microsoft

Многие ключевые слова для систем Microsoft позволяют изменять деклараторы, чтобы создавать производные типы. Дополнительные сведения о деклараторах см. в разделе [деклараторы](overview-of-declarators.md).

|Ключевое слово|Значение|Позволяют создавать производные типы?|
|-------------|-------------|---------------------------------|
|[__based](based-grammar.md)|Указанное после него имя объявляет 32-разрядное смещение относительно 32-разрядной базы, содержащейся в объявлении.|Да|
|[__cdecl](cdecl.md)|В указанном после него имени используются соглашения об именовании и вызовах языка C.|Да|
|[__declspec](declspec.md)|Указанное после него имя задает атрибут класса хранения для систем Microsoft.|Нет|
|[__fastcall](fastcall.md)|Указанное после него имя объявляет функцию, в которой аргументы передаются не через стек, а через регистры (если они доступны).|Да|
|[__restrict](extension-restrict.md)|Аналогично ключевому слову __declspec ([ограничить](restrict.md)), но предназначено для переменных.|Нет|
|[__stdcall](stdcall.md)|Указанное после него имя задает функцию, в которой соблюдается стандартное соглашение о вызовах.|Да|
|[__w64](w64.md)|Указывает, что в 64-разрядном компиляторе тип данных имеет больший размер.|Нет|
|[__unaligned](unaligned.md)|Указывает, что указатель на тип или другие данные не выровнен.|Нет|
|[__vectorcall](vectorcall.md)|Указанное после него имя объявляет функцию, в которой аргументы передаются не через стек, а через регистры (если они доступны), включая регистры SSE.|Да|

## <a name="see-also"></a>См. также

[Справочник по языку C++](cpp-language-reference.md)