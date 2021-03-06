---
title: Операторы ATL | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- operators [ATL]
ms.assetid: 58ccd252-2869-45ee-8a5c-3ca40ee7f8a2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0741cd65924a2c968153333aa1a557c31f429d45
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46039781"
---
# <a name="atl-operators"></a>Операторы ATL

В этом разделе содержатся разделы справки по для глобальных операторов ATL.

|Оператор|Описание|
|--------------|-----------------|
|[оператор ==](#operator_eq_eq)|Сравнивает два `CSid` объектов или `SID` структур на предмет равенства.|
|[оператор! =](#operator_neq)|Сравнивает два `CSid` объектов или `SID` структур на предмет их неравенства.|
|[оператор <](#operator_lt)|Проверяет `CSid` объекта или `SID` структура слева от оператора меньше, чем `CSid` объекта или `SID` структура справа (для совместимости стандартной библиотеки C++).|
|[оператор >](#operator_gt)|Проверяет `CSid` объекта или `SID` структуры слева от оператора больше, чем `CSid` объекта или `SID` структура справа (для совместимости стандартной библиотеки C++).|
|[оператор < =](#operator_lt__eq)|Проверяет `CSid` объекта или `SID` структуры слева от оператора меньше или равно `CSid` объекта или `SID` структура справа (для совместимости стандартной библиотеки C++).|
|[оператор > =](#operator_gt__eq)|Проверяет `CSid` объекта или `SID` структуры слева от оператора больше или равно `CSid` объекта или `SID` структура справа (для совместимости стандартной библиотеки C++).|

## <a name="requirements"></a>Требования

**Заголовок:** atlsecurity.h.

##  <a name="operator_eq_eq"></a>  оператор ==

Сравнивает `CSid` объектов или `SID` структуры (идентификатором безопасности) на предмет равенства.

```
bool operator==(const CSid& lhs, const CSid& rhs) throw();
```

### <a name="parameters"></a>Параметры

*lhs*<br/>
Первый `CSid` объекта или `SID` сравниваемая структура.

*правая часть*<br/>
Второй `CSid` объекта или `SID` сравниваемая структура.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если объекты равны, значение FALSE, если они не равны.

##  <a name="operator_neq"></a>  оператор! =

Сравнивает `CSid` объектов или `SID` структуры (идентификатором безопасности) на предмет их неравенства.

```
bool operator==(const CSid& lhs, const CSid& rhs) throw();
```

### <a name="parameters"></a>Параметры

*lhs*<br/>
Первый `CSid` объекта или `SID` сравниваемая структура.

*правая часть*<br/>
Второй `CSid` объекта или `SID` сравниваемая структура.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если объекты не равны, значение FALSE, если они равны.

##  <a name="operator_lt"></a>  оператор <

Проверяет `CSid` объекта или `SID` структура слева от оператора меньше, чем `CSid` объекта или `SID` структура справа (для совместимости стандартной библиотеки C++).

```
bool operator<(const CSid& lhs, const CSid& rhs) throw();
```

### <a name="parameters"></a>Параметры

*lhs*<br/>
Первый `CSid` объекта или `SID` сравниваемая структура.

*правая часть*<br/>
Второй `CSid` объекта или `SID` сравниваемая структура.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если адрес *lhs* объект меньше, чем адрес *rhs* объект, значение FALSE в противном случае.

### <a name="remarks"></a>Примечания

Этот оператор действует в адрес `CSid` объекта или `SID` структуры, а также реализации для обеспечения совместимости с классами коллекцию стандартной библиотеки C++.

##  <a name="operator_gt"></a>  оператор >

Проверяет `CSid` объекта или `SID` структуры слева от оператора больше, чем `CSid` объекта или `SID` структура справа (для совместимости стандартной библиотеки C++).

```
bool operator<(const CSid& lhs, const CSid& rhs) throw();
```

### <a name="parameters"></a>Параметры

*lhs*<br/>
Первый `CSid` объекта или `SID` сравниваемая структура.

*правая часть*<br/>
Второй `CSid` объекта или `SID` сравниваемая структура.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если адрес *lhs* больше, чем адрес *rhs*, и FALSE в противном случае.

### <a name="remarks"></a>Примечания

Этот оператор действует в адрес `CSid` объекта или `SID` структуры, а также реализации для обеспечения совместимости с классами коллекцию стандартной библиотеки C++.

##  <a name="operator_lt__eq"></a>  оператор < =

Проверяет `CSid` объекта или `SID` структуры слева от оператора меньше или равно `CSid` объекта или `SID` структура справа (для совместимости стандартной библиотеки C++).

```
bool operator<(const CSid& lhs, const CSid& rhs) throw();
```

### <a name="parameters"></a>Параметры

*lhs*<br/>
Первый `CSid` объекта или `SID` сравниваемая структура.

*правая часть*<br/>
Второй `CSid` объекта или `SID` сравниваемая структура.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если адрес *lhs* меньше или равно адрес *rhs*, и FALSE в противном случае.

### <a name="remarks"></a>Примечания

Этот оператор действует в адрес `CSid` объекта или `SID` структуры, а также реализации для обеспечения совместимости с классами коллекцию стандартной библиотеки C++.

##  <a name="operator_gt__eq"></a>  оператор > =

Проверяет `CSid` объекта или `SID` структуры слева от оператора больше или равно `CSid` объекта или `SID` структура справа (для совместимости стандартной библиотеки C++).

```
bool operator<(const CSid& lhs, const CSid& rhs) throw();
```

### <a name="parameters"></a>Параметры

*lhs*<br/>
Первый `CSid` объекта или `SID` сравниваемая структура.

*правая часть*<br/>
Второй `CSid` объекта или `SID` сравниваемая структура.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если адрес *lhs* больше или равно адрес *rhs*, и FALSE в противном случае.

### <a name="remarks"></a>Примечания

Этот оператор действует в адрес `CSid` объекта или `SID` структуры, а также реализации для обеспечения совместимости с классами коллекцию стандартной библиотеки C++.

