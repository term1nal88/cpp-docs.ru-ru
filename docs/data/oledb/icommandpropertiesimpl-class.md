---
title: Класс ICommandPropertiesImpl | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ICommandPropertiesImpl
- ATL.ICommandPropertiesImpl
- ATL::ICommandPropertiesImpl
- ICommandPropertiesImpl::GetProperties
- ICommandPropertiesImpl.GetProperties
- GetProperties
- ICommandPropertiesImpl.SetProperties
- ICommandPropertiesImpl::SetProperties
- SetProperties
dev_langs:
- C++
helpviewer_keywords:
- ICommandPropertiesImpl class
- GetProperties method
- SetProperties method
ms.assetid: b3cf6aea-527e-4f0d-96e0-669178b021a2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 40c1648131db04ed1629da453a16112debf6e6be
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50053601"
---
# <a name="icommandpropertiesimpl-class"></a>Класс ICommandPropertiesImpl

Предоставляет реализацию [ICommandProperties](/previous-versions/windows/desktop/ms723044) интерфейс.

## <a name="syntax"></a>Синтаксис

```cpp
template <class T, class PropClass = T>
class ATL_NO_VTABLE ICommandPropertiesImpl
   : public ICommandProperties, public CUtlProps<PropClass>
```

### <a name="parameters"></a>Параметры

*T*<br/>
Класс, производный от

*PropClass*<br/>
Класс свойств.

## <a name="requirements"></a>Требования

**Заголовок:** atldb.h

## <a name="members"></a>Участники

### <a name="interface-methods"></a>Методы интерфейса

|||
|-|-|
|[GetProperties](#getproperties)|Возвращает список свойств в группе свойств набора строк, в настоящее время запрашиваются для набора строк.|
|[SetProperties](#setproperties)|Задает свойства в группе свойств набора строк.|

## <a name="remarks"></a>Примечания

Это обязательно на команды. Реализация предоставляется с определением статическую функцию [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md) макрос.

## <a name="getproperties"></a> ICommandPropertiesImpl::GetProperties

Возвращает все наборы запрошенного свойства, с помощью команды сопоставление свойств.

### <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD(GetProperties)(const ULONG cPropertyIDSets, 
   const DBPROPIDSET rgPropertyIDSets[], 
   ULONG * pcPropertySets, 
   DBPROPSET ** prgPropertySets);
```

#### <a name="parameters"></a>Параметры

См. в разделе [ICommandProperties::GetProperties](/previous-versions/windows/desktop/ms723119) в *справочнике программиста OLE DB*.

### <a name="remarks"></a>Примечания

См. раздел [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md).

## <a name="setproperties"></a> ICommandPropertiesImpl::SetProperties

Задает свойства для объекта команды.

### <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD(SetProperties)(ULONG cPropertySets, 
   DBPROPSET rgPropertySets[]);
```

#### <a name="parameters"></a>Параметры

См. в разделе [ICommandProperties::SetProperties](/previous-versions/windows/desktop/ms711497) в *справочнике программиста OLE DB*.

## <a name="see-also"></a>См. также

[Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)