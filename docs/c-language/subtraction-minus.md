---
title: Вычитание (-) | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- operators [C], subtraction
- subtraction operator, syntax
ms.assetid: 9cacba7d-20b3-4372-8a63-ba5d8ee64177
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8b09683592ca7fe897c8477a17c14fbc72d11f7e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46079964"
---
# <a name="subtraction--"></a>Вычитание (-)

Оператор вычитания (**-**) вычитает второй операнд из первого. Оба операнда могут быть целочисленными типами или типами с плавающей запятой либо один операнд может быть указателем, а второй — целым числом.

При вычитании двух указателей разница преобразуется в целочисленное значение со знаком путем деления разницы на размер значения типа, к которому обращаются указатели. Размер целочисленного значения определяется типом **ptrdiff_t** в стандартном включаемом файле STDDEF.H. Результат представляет собой число позиций памяти данного типа, расположенных между двумя адресами. Результат гарантировано имеет значение только для двух элементов одного массива, как описано в разделе [Арифметические операции с указателями](../c-language/pointer-arithmetic.md).

Если целочисленное значение вычитается из значения указателя, оператор вычитания преобразует целочисленное значение (*i*) путем его умножения на размер значения, к которому обращается указатель. После преобразования значение целого числа представляет позиции памяти *i*, где каждая позиция имеет длину, заданную типом указателя. Если преобразованное целочисленное значение вычесть из значения указателя, будут получены позиции *i* адреса памяти, расположенные до исходного адреса. Новый указатель указывает на значение типа, к которому обращается исходное значение указателя.

## <a name="see-also"></a>См. также

[Аддитивные операторы в C](../c-language/c-additive-operators.md)