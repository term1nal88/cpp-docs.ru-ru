---
title: Synclockt-класс | Документация Майкрософт
ms.custom: ''
ms.date: 10/03/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT::IsLocked
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT::sync_
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT::SyncLockT
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT::~SyncLockT
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT::Unlock
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::Wrappers::Details::SyncLockT class
- Microsoft::WRL::Wrappers::Details::SyncLockT::IsLocked method
- Microsoft::WRL::Wrappers::Details::SyncLockT::sync_ data member
- Microsoft::WRL::Wrappers::Details::SyncLockT::SyncLockT, constructor
- Microsoft::WRL::Wrappers::Details::SyncLockT::~SyncLockT, destructor
- Microsoft::WRL::Wrappers::Details::SyncLockT::Unlock method
ms.assetid: a967f6f7-3555-43d1-b210-2bb65d63d15e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a97b164d2ee7f5f5a6cc771d1ebec699f705cc80
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50053168"
---
# <a name="synclockt-class"></a>SyncLockT - класс

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

## <a name="syntax"></a>Синтаксис

```cpp
template <typename SyncTraits>
class SyncLockT;
```

### <a name="parameters"></a>Параметры

*SyncTraits*<br/>
Тип, который может стать владельцем ресурса.

## <a name="remarks"></a>Примечания

Представляет тип, который может занять монопольного или общее владение ресурсом.

`SyncLockT` Класс используется, например, чтобы реализовать [SRWLock](../windows/srwlock-class.md) класса.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

Имя                                      | Описание
----------------------------------------- | ----------------------------------------------------
[SyncLockT::SyncLockT](#synclockt)        | Инициализирует новый экземпляр класса `SyncLockT`.
[SyncLockT:: ~ SyncLockT](#tilde-synclockt) | Отменяет инициализацию экземпляра `SyncLockT` класса.

### <a name="protected-constructors"></a>Защищенные конструкторы

Имя                               | Описание
---------------------------------- | ----------------------------------------------------
[SyncLockT::SyncLockT](#synclockt) | Инициализирует новый экземпляр класса `SyncLockT`.

### <a name="public-methods"></a>Открытые методы

Имя                             | Описание
-------------------------------- | --------------------------------------------------------------------------------------------------------------
[SyncLockT::IsLocked](#islocked) | Указывает ли текущий `SyncLockT` объекта, которому принадлежит ресурс, то есть, `SyncLockT` объект *заблокирован*.
[SyncLockT::Unlock](#unlock)     | Управление ресурсы, удерживаемые текущим `SyncLockT` объекта, если таковые имеются.

### <a name="protected-data-members"></a>Защищенные члены данных

name                      | Описание
------------------------- | -------------------------------------------------------------------
[SyncLockT::sync_](#sync) | Удерживает базовый ресурс, представленный `SyncLockT` класса.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`SyncLockT`

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft::WRL::Wrappers::Details

## <a name="tilde-synclockt"></a>SyncLockT:: ~ SyncLockT

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

```cpp
~SyncLockT();
```

### <a name="remarks"></a>Примечания

Отменяет инициализацию экземпляра `SyncLockT` класса.

Этот деструктор также разблокирует текущего `SyncLockT` экземпляра.

## <a name="islocked"></a>SyncLockT::IsLocked

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

```cpp
bool IsLocked() const;
```

### <a name="return-value"></a>Возвращаемое значение

**значение true,** Если `SyncLockT` объектов заблокирован; в противном случае — значение **false**.

### <a name="remarks"></a>Примечания

Указывает ли текущий `SyncLockT` объекта, которому принадлежит ресурс, то есть, `SyncLockT` объект *заблокирован*.

## <a name="sync"></a>SyncLockT::sync_

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

```cpp
typename SyncTraits::Type sync_;
```

### <a name="remarks"></a>Примечания

Удерживает базовый ресурс, представленный `SyncLockT` класса.

## <a name="synclockt"></a>SyncLockT::SyncLockT

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

```cpp
SyncLockT(
   _Inout_ SyncLockT&& other
);

explicit SyncLockT(
   typename SyncTraits::Type sync = SyncTraits::GetInvalidValue()
);
```

### <a name="parameters"></a>Параметры

*other*<br/>
Ссылка rvalue на другой `SyncLockT` объекта.

*sync*<br/>
Ссылка на другой `SyncLockWithStatusT` объекта.

### <a name="remarks"></a>Примечания

Инициализирует новый экземпляр класса `SyncLockT`.

Первый конструктор инициализирует текущий `SyncLockT` из другого объекта `SyncLockT` объекта, указанного параметром *других*и затем недействительными другой `SyncLockT` объекта. Второй конструктор является `protected`и инициализирует текущий `SyncLockT` объекта в недопустимом состоянии.

## <a name="unlock"></a>SyncLockT::Unlock

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

```cpp
void Unlock();
```

### <a name="remarks"></a>Примечания

Управление ресурсы, удерживаемые текущим `SyncLockT` объекта, если таковые имеются.
