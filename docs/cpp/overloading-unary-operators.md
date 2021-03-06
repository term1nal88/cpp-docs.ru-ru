---
title: Перегрузка унарных операторов | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- unary operators [C++], plus
- increment operators [C++], overloaded
- unary operators [C++], minus
- operators [C++], unary
- redefinable unary operators [C++]
- unary operators [C++]
- pointer dereference operator overloading
- plus operator
ms.assetid: 7683ef08-42a4-4283-928f-d3dd4f3ab4c0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f737e262d39b99c2c33b7c91bc3d1e234a9f47db
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46018630"
---
# <a name="overloading-unary-operators"></a>Перегрузка унарных операторов

Перегрузке могут быть подвергнуты следующие унарные операторы.

1. `!` ([логическое не](../cpp/logical-negation-operator-exclpt.md))

1. `&` ([взятия адреса](../cpp/address-of-operator-amp.md))

1. `~` ([дополнение до единицы](../cpp/one-s-complement-operator-tilde.md))

1. `*` ([разыменование указателя](../cpp/indirection-operator-star.md))

1. `+` ([унарный плюс](../cpp/additive-operators-plus-and.md))

1. `-` ([Унарное отрицание](../cpp/additive-operators-plus-and.md))

1. `++` ([приращения](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md))

1. `--` ([уменьшения](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md))

9. операторы преобразования

Постфиксного инкремента и декремента (`++` и `--`) рассматриваются отдельно в [увеличения и уменьшения](../cpp/increment-and-decrement-operator-overloading-cpp.md).

Операторы преобразования также обсуждаются в отдельном разделе; см. в разделе [заданных пользователем преобразований типа](../cpp/user-defined-type-conversions-cpp.md).

Следующие правила распространяются на все остальные унарные операторы. Чтобы объявить функцию унарного оператора как нестатический член, необходимо объявить ее в форме

> *возвращаемый тип* **оператор** *op* **)**

где *ret-type* является возвращаемым типом и *op* один из операторов, перечисленных в предыдущей таблице.

Чтобы объявить функцию унарного оператора как глобальную функцию, необходимо объявить ее в форме

> *возвращаемый тип* **оператор** *op* **(** *arg* **)**

где *ret-type* и *op* соответствуют описанию для функций-членов операторов и *arg* является аргументом типа класса, на которой выполняются операции.

> [!NOTE]
>  Не существует ограничения на типы возвращаемого значения унарных операторов. Например, логическому НЕ (`!`) имеет смысл возвращать целочисленное значение, однако это не реализовано принудительно.

## <a name="see-also"></a>См. также

[Перегрузка операторов](../cpp/operator-overloading.md)