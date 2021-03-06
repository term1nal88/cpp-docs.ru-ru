---
title: __unaligned | Документация Майкрософт
ms.custom: ''
ms.date: 10/10/2018
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __unaligned_cpp
- __unaligned
- _unaligned
dev_langs:
- C++
helpviewer_keywords:
- __unaligned keyword [C++]
ms.assetid: 0cd83aad-1840-47e3-ad33-59bfcbe6375b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 444bc3372b22676cacb3ee89b9c0ad92000cedcc
ms.sourcegitcommit: 8480f16893f09911f08a58caf684405404f7ac8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/12/2018
ms.locfileid: "49161222"
---
# <a name="unaligned"></a>__unaligned

**Системам Microsoft**. При объявлении указателя с **__unaligned** модификатор, компилятор предполагает, что указатель обращается к данным, не выровнен. Следовательно соответствующих платформе код создается для обработки операций чтения невыровненных и записывает через указатель.

## <a name="remarks"></a>Примечания

Этот модификатор описывает выравнивание данных, указывает указатель; предполагается, что сам указатель быть выровнены.

Необходимость **__unaligned** ключевое слово зависит от платформы и среды. Неспособность соответствующим образом пометить данных может привести к сбоям оборудования и заканчивая снижения производительности. **__Unaligned** модификатор не является допустимым для x86 платформы.

Для совместимости с предыдущими версиями **_unaligned** является синонимом **__unaligned** Если параметр компилятора [/Za \(отключить расширения языка)](../build/reference/za-ze-disable-language-extensions.md) указывается.

Дополнительные сведения о выравнивании см. в разделах:

- [align](../cpp/align-cpp.md)

- [Оператор __alignof](../cpp/alignof-operator.md)

- [pack](../preprocessor/pack.md)

- [/Zp (выравнивание члена структуры)](../build/reference/zp-struct-member-alignment.md)

- [Примеры выравнивания структуры](../build/examples-of-structure-alignment.md)

## <a name="see-also"></a>См. также

[Ключевые слова](../cpp/keywords-cpp.md)