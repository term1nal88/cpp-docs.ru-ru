---
title: средства извлечения _variant_t | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _variant_t.operatordouble
- operatorlong
- _variant_t::operator_bstr_t
- operatordouble
- _variant_t.operatorCY
- operatorCY
- _variant_t::operatorCY
- _variant_t::operatordouble
- operatorfloat
- operatorBYTE
- _variant_t.operatorDECIMAL
- _variant_t::operatorlong
- operatorIDispatch
- _variant_t.operatorBYTE
- operatorDECIMAL
- _variant_t.operator_bstr_t
- _variant_t::operatorDECIMAL
- _variant_t.operatorIUnknown
- _variant_t.operatorlong
- _variant_t::operatorIDispatch
- _variant_t::operatorIUnknown
- operatorIUnknown
- _variant_t.operatorbool
- _variant_t::operatorBYTE
- _variant_t.operatorfloat
- operator_bstr_t
- _variant_t::operatorbool
- operatorshort
- _variant_t::operatorshort
- _variant_t::operatorfloat
- _variant_t.operatorIDispatch
- _variant_t.operatorshort
dev_langs:
- C++
helpviewer_keywords:
- extractors, _variant_t class
- operator CY
- operator IDispatch
- operator SHORT
- operator double
- operator long
- operator _bstr_t
- operator DECIMAL
- operator float
- operator bool
- operator BYTE
- operator IUnknown
ms.assetid: 33c1782f-045a-4673-9619-1d750efc83a9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6a9d4e13a4b7382d15e601eba16a5a12edd2d00f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46034152"
---
# <a name="variantt-extractors"></a>Средства извлечения _variant_t

**Блок, относящийся только к системам Microsoft**

Извлечение данных из инкапсулированного `VARIANT` объекта.

## <a name="syntax"></a>Синтаксис

```
operator short( ) const; 
operator long( ) const; 
operator float( ) const; 
operator double( ) const; 
operator CY( ) const; 
operator _bstr_t( ) const; 
operator IDispatch*( ) const; 
operator bool( ) const; 
operator IUnknown*( ) const; 
operator DECIMAL( ) const; 
operator BYTE( ) const;
operator VARIANT() const throw();
operator char() const;
operator unsigned short() const;
operator unsigned long() const;
operator int() const;
operator unsigned int() const;
operator __int64() const;
operator unsigned __int64() const;
```

## <a name="remarks"></a>Примечания

Извлечение необработанных данных из инкапсулированного объекта `VARIANT`. Если `VARIANT` еще не соответствующего типа, `VariantChangeType` используется попытки преобразования, и в случае сбоя, создается ошибка:

- **Operator short ()** извлекает **короткие** целочисленное значение.

- **Operator long ()** извлекает **long** целочисленное значение.

- **operator float ()** извлекает **float** числовое значение.

- **Operator double ()** извлекает **двойные** целочисленное значение.

- **Operator CY ()** извлекает `CY` объекта.

- **Operator bool ()** извлекает **bool** значение.

- **Operator DECIMAL ()** извлекает `DECIMAL` значение.

- **Operator BYTE ()** извлекает `BYTE` значение.

- **Operator () _bstr_t** извлекает строку, инкапсулированную в `_bstr_t` объекта.

- **IDispatch-оператор\*()** извлекает указатель на disp-интерфейса из инкапсулированного объекта `VARIANT`. `AddRef` вызывается для результирующего указателя, поэтому следует вызвать метод `Release` освободит его.

- **Operator IUnknown\*()** извлекает указатель на интерфейс COM из инкапсулированного объекта `VARIANT`. `AddRef` вызывается для результирующего указателя, поэтому следует вызвать метод `Release` освободит его.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Класс _variant_t](../cpp/variant-t-class.md)