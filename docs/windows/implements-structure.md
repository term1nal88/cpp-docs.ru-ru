---
title: Реализует структуру | Документация Майкрософт
ms.custom: ''
ms.date: 10/03/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Implements
- implements/Microsoft::WRL::Implements::CanCastTo
- implements/Microsoft::WRL::Implements::CastToUnknown
- implements/Microsoft::WRL::Implements::FillArrayWithIid
- implements/Microsoft::WRL::Implements::IidCount
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::Implements structure
- Microsoft::WRL::Implements::CanCastTo method
- Microsoft::WRL::Implements::CastToUnknown method
- Microsoft::WRL::Implements::FillArrayWithIid method
- Microsoft::WRL::Implements::IidCount method
ms.assetid: 29b13e90-34d4-4a0b-babd-5187c9eb0c36
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: cc993dc1ebe0c5f1ab11409fcecee9b6cdefdaae
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "48788778"
---
# <a name="implements-structure"></a>Implements - структура

Реализует `QueryInterface` и `GetIid` для указанных интерфейсов.

## <a name="syntax"></a>Синтаксис

```cpp
template <
    typename I0,
    typename I1 = Details::Nil,
    typename I2 = Details::Nil,
    typename I3 = Details::Nil,
    typename I4 = Details::Nil,
    typename I5 = Details::Nil,
    typename I6 = Details::Nil,
    typename I7 = Details::Nil,
    typename I8 = Details::Nil,
    typename I9 = Details::Nil
>
struct __declspec(novtable) Implements :
    Details::ImplementsHelper<
        RuntimeClassFlags<WinRt>,
        typename Details::InterfaceListHelper<
            I0, I1, I2, I3, I4, I5, I6, I7, I8, I9
        >::TypeT
    >,
    Details::ImplementsBase;

template <
    int flags,
    typename I0,
    typename I1,
    typename I2,
    typename I3,
    typename I4,
    typename I5,
    typename I6,
    typename I7,
    typename I8
>
struct __declspec(novtable) Implements<
        RuntimeClassFlags<flags>,
        I0, I1, I2, I3, I4, I5, I6, I7, I8> :
    Details::ImplementsHelper<
        RuntimeClassFlags<flags>,
        typename Details::InterfaceListHelper<
            I0, I1, I2, I3, I4, I5, I6, I7, I8
        >::TypeT
    >,
    Details::ImplementsBase;
```

### <a name="parameters"></a>Параметры

*I0*<br/>
Идентификатор нулевого интерфейса. (Обязательный)

*I1*<br/>
Идентификатор первого интерфейса. (Необязательный параметр).

*I2*<br/>
Идентификатор второго интерфейса. (Необязательный параметр).

*I3*<br/>
Идентификатор третьего интерфейса. (Необязательный параметр).

*I4*<br/>
Идентификатор четвертого интерфейса. (Необязательный параметр).

*I5*<br/>
Идентификатор пятого интерфейса. (Необязательный параметр).

*I6*<br/>
Идентификатор шестого интерфейса. (Необязательный параметр).

*I7*<br/>
Идентификатор седьмого интерфейса. (Необязательный параметр).

*I8*<br/>
Идентификатор восьмого интерфейса. (Необязательный параметр).

*I9*<br/>
Идентификатор девятого интерфейса. (Необязательный параметр).

*flags*<br/>
Флаги конфигурации для класса. Один или несколько [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) перечисления, которые указаны в [RuntimeClassFlags](../windows/runtimeclassflags-structure.md) структуры.

## <a name="remarks"></a>Примечания

Является производным от списка указанных интерфейсов и реализует вспомогательные шаблоны для `QueryInterface` и `GetIid`.

Каждый *I0* через *I9* параметр интерфейса должен быть производным от `IUnknown`, `IInspectable`, или [ChainInterfaces](../windows/chaininterfaces-structure.md) шаблона. *Флаги* параметр определяет, создается ли поддержка для `IUnknown` или `IInspectable`.

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

| Имя        | Описание                               |
| ----------- | ----------------------------------------- |
| `ClassFlags`| Синоним для `RuntimeClassFlags<WinRt>`. |

### <a name="protected-methods"></a>Защищенные методы

| Имя                                              | Описание                                                                                                   |
| ------------------------------------------------- | ------------------------------------------------------------------------------------------------------------- |
| [Implements::CanCastTo](#cancastto)               | Возвращает указатель на указанный интерфейс.                                                                    |
| [Implements::CastToUnknown](#casttounknown)       | Возвращает указатель на базовый `IUnknown` интерфейс.                                                        |
| [Implements::FillArrayWithIid](#fillarraywithiid) | Вставляет идентификатор интерфейса, заданный текущим параметром шаблона признаками в указанный элемент массива. |

### <a name="protected-constants"></a>Защищенные константы

| name                              | Описание                                    |
| --------------------------------- | ---------------------------------------------- |
| [Implements::IidCount](#iidcount) | Содержит число идентификаторов реализованного интерфейса. |

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`I0`

`ChainInterfaces`

`I0`

`ImplementsBase`

`ImplementsHelper`

`Implements`

## <a name="requirements"></a>Требования

**Заголовок:** implements.h

**Пространство имен:** Microsoft::WRL

## <a name="cancastto"></a>Implements::CanCastTo

Возвращает указатель на указанный интерфейс.

```cpp
__forceinline HRESULT CanCastTo(
   REFIID riid,
   _Deref_out_ void **ppv
);
```

### <a name="parameters"></a>Параметры

*riid*<br/>
Ссылку на идентификатор интерфейса.

*ppv*<br/>
Если в случае успешного выполнения указатель на интерфейс, заданный *riid*.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если выполнение прошло успешно; в противном случае — значение HRESULT, указывающее ошибку, например E_NOINTERFACE.

### <a name="remarks"></a>Примечания

Это внутренняя вспомогательная функция, которая выполняет операцию QueryInterface.

## <a name="casttounknown"></a>Implements::CastToUnknown

Возвращает указатель на базовый `IUnknown` интерфейс.

```cpp
__forceinline IUnknown* CastToUnknown();
```

### <a name="return-value"></a>Возвращаемое значение

Эта операция выполняется успешно и всегда возвращает `IUnknown` указатель.

### <a name="remarks"></a>Примечания

Внутренняя вспомогательная функция.

## <a name="fillarraywithiid"></a>Implements::FillArrayWithIid

Вставляет идентификатор интерфейса, заданный текущим параметром шаблона признаками в указанный элемент массива.

```cpp
__forceinline static void FillArrayWithIid(
   unsigned long &index,
   _In_ IID* iids
);
```

### <a name="parameters"></a>Параметры

*Индекс*<br/>
Отсчитываемый от нуля индекс, указывающий начальный элемент массива для этой операции. По завершении этой операции *индекс* увеличивается на 1.

*идентификаторы IID*<br/>
Массив типа IID.

### <a name="remarks"></a>Примечания

Внутренняя вспомогательная функция.

## <a name="iidcount"></a>Implements::IidCount

Содержит число идентификаторов реализованного интерфейса.

```cpp
static const unsigned long IidCount;
```
