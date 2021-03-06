---
title: Boolstruct-структура | Документация Майкрософт
ms.custom: ''
ms.date: 09/21/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::BoolStruct
- internal/Microsoft::WRL::Details::BoolStruct::Member
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::Details::BoolStruct structure
- Microsoft::WRL::Details::BoolStruct::Member data member
ms.assetid: 666eae78-e81d-4fb7-a9e4-1ba617d6d4cd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 74a292f2253d29730e8ee9104ea81308081c0496
ms.sourcegitcommit: 1d9bd38cacbc783fccd3884b7b92062161c91c84
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/03/2018
ms.locfileid: "48234272"
---
# <a name="boolstruct-structure"></a>BoolStruct - структура

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

## <a name="syntax"></a>Синтаксис

```cpp
struct BoolStruct;
```

## <a name="remarks"></a>Примечания

`BoolStruct` Структура определяет ли `ComPtr` управление временем существования объектов интерфейса. `BoolStruct` используется внутренним образом [BoolType()](../windows/comptr-operator-microsoft-wrl-details-booltype-operator.md) оператор.

## <a name="members"></a>Участники

### <a name="public-data-members"></a>Открытые члены данных

Имя                          | Описание
----------------------------- | ------------------------------------------------------------------------------------------------------------------
[BoolStruct::Member](#member) | Указывает, что [ComPtr](../windows/comptr-class.md) является, или не, управление временем существования объектов интерфейса.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`BoolStruct`

## <a name="requirements"></a>Требования

**Заголовок:** internal.h

**Пространство имен:** Microsoft::wrl:: Details

## <a name="member"></a>BoolStruct::Member

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

```cpp
int Member;
```

### <a name="remarks"></a>Примечания

Указывает, что [ComPtr](../windows/comptr-class.md) является, или не, управление временем существования объектов интерфейса.
