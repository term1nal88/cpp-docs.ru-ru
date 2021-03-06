---
title: Класс ISupportErrorInfoImpl | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- ISupportErrorInfoImpl
- ATLCOM/ATL::ISupportErrorInfoImpl
- ATLCOM/ATL::ISupportErrorInfoImpl::InterfaceSupportsErrorInfo
dev_langs:
- C++
helpviewer_keywords:
- ISupportErrorInfo ATL implementation
- ISupportErrorInfoImpl class
- error information, ATL
ms.assetid: e33a4b11-a123-41cf-bcea-7b19743902af
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1a6d5ec8a7cd93d9e7e3628ef1e07f94cb169a7a
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50053491"
---
# <a name="isupporterrorinfoimpl-class"></a>Класс ISupportErrorInfoImpl

Этот класс предоставляет реализацию по умолчанию [ISupportErrorInfo интерфейс](/previous-versions/windows/desktop/api/oaidl/nn-oaidl-isupporterrorinfo) и может использоваться, когда только один интерфейс выдает ошибки для объекта.

> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
template<const IID* piid>
class ATL_NO_VTABLE ISupportErrorInfoImpl
   : public ISupportErrorInfo
```

#### <a name="parameters"></a>Параметры

*piid*<br/>
Указатель на идентификатор IID интерфейса, поддерживающего [IErrorInfo](/previous-versions/windows/desktop/api/oaidl/nn-oaidl-ierrorinfo).

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[ISupportErrorInfoImpl::InterfaceSupportsErrorInfo](#interfacesupportserrorinfo)|Указывает, определяется ли интерфейс `riid` поддерживает [IErrorInfo](/previous-versions/windows/desktop/api/oaidl/nn-oaidl-ierrorinfo) интерфейс.|

## <a name="remarks"></a>Примечания

[ISupportErrorInfo интерфейс](/previous-versions/windows/desktop/api/oaidl/nn-oaidl-isupporterrorinfo) гарантирует, что сведения об ошибке могут быть возвращены клиенту. Объекты, использующие `IErrorInfo` должен реализовывать `ISupportErrorInfo`.

Класс `ISupportErrorInfoImpl` предоставляет реализацию по умолчанию `ISupportErrorInfo` и может использоваться, когда только один интерфейс выдает ошибки для объекта. Пример:

[!code-cpp[NVC_ATL_COM#48](../../atl/codesnippet/cpp/isupporterrorinfoimpl-class_1.h)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`ISupportErrorInfo`

`ISupportErrorInfoImpl`

## <a name="requirements"></a>Требования

**Заголовок:** atlcom.h

##  <a name="interfacesupportserrorinfo"></a>  ISupportErrorInfoImpl::InterfaceSupportsErrorInfo

Указывает, определяется ли интерфейс `riid` поддерживает [IErrorInfo](/previous-versions/windows/desktop/api/oaidl/nn-oaidl-ierrorinfo) интерфейс.

```
STDMETHOD(InterfaceSupportsErrorInfo)(REFIID riid);
```

### <a name="remarks"></a>Примечания

См. в разделе [ISupportErrorInfo::InterfaceSupportsErrorInfo](/previous-versions/windows/desktop/api/oaidl/nf-oaidl-isupporterrorinfo-interfacesupportserrorinfo) в Windows SDK.

##  <a name="getsize"></a>  IThreadPoolConfig::GetSize

Вызовите этот метод, чтобы получить число потоков в пуле.

```
STDMETHOD(GetSize)(int* pnNumThreads);
```

### <a name="parameters"></a>Параметры

*pnNumThreads*<br/>
[out] Адрес переменной, которая, в случае успешного выполнения получает количество потоков в пуле.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#134](../../atl/codesnippet/cpp/isupporterrorinfoimpl-class_2.cpp)]

##  <a name="gettimeout"></a>  IThreadPoolConfig::GetTimeout

Вызовите этот метод, чтобы получить максимальное время в миллисекундах, пул потоков будет ожидать поток для завершения работы.

```
STDMETHOD(GetTimeout)(DWORD* pdwMaxWait);
```

### <a name="parameters"></a>Параметры

*pdwMaxWait*<br/>
[out] Адрес переменной, которая, в случае успешного выполнения Получает максимальное время в миллисекундах, пул потоков будет ожидать поток для завершения работы.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

### <a name="example"></a>Пример

См. в разделе [IThreadPoolConfig::GetSize](#getsize).

##  <a name="setsize"></a>  IThreadPoolConfig::SetSize

Вызовите этот метод, чтобы задать количество потоков в пуле.

```
STDMETHOD(SetSize)int nNumThreads);
```

### <a name="parameters"></a>Параметры

*nNumThreads*<br/>
Запрашиваемое количество потоков в пуле.

Если *nNumThreads* является отрицательным, его абсолютное значение будет умножена на число процессоров в компьютере для получения общего числа потоков.

Если *nNumThreads* равен нулю, ATLS_DEFAULT_THREADSPERPROC будет умножена на число процессоров в компьютере для получения общего числа потоков.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

### <a name="example"></a>Пример

См. в разделе [IThreadPoolConfig::GetSize](#getsize).

##  <a name="settimeout"></a>  IThreadPoolConfig::SetTimeout

Вызовите этот метод, чтобы задать максимальное время в миллисекундах, пул потоков будет ожидать поток для завершения работы.

```
STDMETHOD(SetTimeout)(DWORD dwMaxWait);
```

### <a name="parameters"></a>Параметры

*dwMaxWait*<br/>
Запрошенное максимальное время в миллисекундах, пул потоков будет ожидать поток для завершения работы.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

### <a name="example"></a>Пример

См. в разделе [IThreadPoolConfig::GetSize](#getsize).

## <a name="see-also"></a>См. также

[Общие сведения о классе](../../atl/atl-class-overview.md)
