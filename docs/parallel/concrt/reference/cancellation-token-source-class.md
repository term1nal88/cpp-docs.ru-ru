---
title: Класс cancellation_token_source | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- cancellation_token_source
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token_source
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token_source::cancellation_token_source
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token_source::cancel
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token_source::create_linked_source
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token_source::get_token
dev_langs:
- C++
helpviewer_keywords:
- cancellation_token_source class
ms.assetid: 3548b1a0-12b0-4334-95db-4bf57141c066
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 03bf785ddd5885558045f0394870e114b81e0cfe
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46400462"
---
# <a name="cancellationtokensource-class"></a>Класс cancellation_token_source

Класс `cancellation_token_source` представляет возможность отмены некоторой отменяемой операции.

## <a name="syntax"></a>Синтаксис

```
class cancellation_token_source;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[cancellation_token_source](#ctor)|Перегружен. Создает новый `cancellation_token_source`. Источник можно использовать, чтобы сигнализировать об отмене некоторой отменяемой операции.|
|[~ cancellation_token_source деструктор](#dtor)||

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[Отмена](#cancel)|Отменяет токен. Любой элемент `task_group`, `structured_task_group` или `task`, который использует этот токен, будет отменен при этом вызове и создаст исключение в следующей точке прерывания.|
|[create_linked_source](#create_linked_source)|Перегружен. Создает `cancellation_token_source`, который отменяется при отмене предоставленного токена.|
|[get_token](#get_token)|Возвращает токен отмены, связанный с данным источником. Возвращенный токен можно опрашивать на предмет отмены или предоставить обратный вызов, если и когда произойдет отмена.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[оператор!=](#operator_neq)||
|[оператор=](#operator_eq)||
|[оператор==](#operator_eq_eq)||

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`cancellation_token_source`

## <a name="requirements"></a>Требования

**Заголовок:** pplcancellation_token.h

**Пространство имен:** concurrency

##  <a name="dtor"></a> ~cancellation_token_source

```
~cancellation_token_source();
```

##  <a name="cancel"></a> Отмена

Отменяет токен. Любой элемент `task_group`, `structured_task_group` или `task`, который использует этот токен, будет отменен при этом вызове и создаст исключение в следующей точке прерывания.

```
void cancel() const;
```

##  <a name="ctor"></a> cancellation_token_source

Создает новый `cancellation_token_source`. Источник можно использовать, чтобы сигнализировать об отмене некоторой отменяемой операции.

```
cancellation_token_source();

cancellation_token_source(const cancellation_token_source& _Src);

cancellation_token_source(cancellation_token_source&& _Src);
```

### <a name="parameters"></a>Параметры

*_Src*<br/>
Объект для копирования или перемещения.

##  <a name="create_linked_source"></a> create_linked_source

Создает `cancellation_token_source`, который отменяется при отмене предоставленного токена.

```
static cancellation_token_source create_linked_source(
    cancellation_token& _Src);

template<typename _Iter>
static cancellation_token_source create_linked_source(_Iter _Begin, _Iter _End);
```

### <a name="parameters"></a>Параметры

*_Iter*<br/>
Тип итератора.

*_Src*<br/>
Токен, отмена которого приведет к отмене возвращаемого источника токена. Обратите внимание, что возвращаемый источник токена также можно отменить независимо от источника, содержащегося в этом параметре.

*Н_ачать*<br/>
Итератор стандартной библиотеки C++, соответствующий началу диапазона токенов, которые требуется прослушивать на предмет отмены.

*_Окончания*<br/>
Итератор стандартной библиотеки C++, соответствующий концу диапазона токенов, которые требуется прослушивать на предмет отмены.

### <a name="return-value"></a>Возвращаемое значение

`cancellation_token_source`, который отменяется при отмене токена, предоставляемого параметром `_Src`.

##  <a name="get_token"></a> get_token

Возвращает токен отмены, связанный с данным источником. Возвращенный токен можно опрашивать на предмет отмены или предоставить обратный вызов, если и когда произойдет отмена.

```
cancellation_token get_token() const;
```

### <a name="return-value"></a>Возвращаемое значение

Токен отмены, связанный с этим источником.

##  <a name="operator_neq"></a> оператор! =

```
bool operator!= (const cancellation_token_source& _Src) const;
```

### <a name="parameters"></a>Параметры

*_Src*<br/>
Операнд.

### <a name="return-value"></a>Возвращаемое значение

##  <a name="operator_eq"></a> оператор =

```
cancellation_token_source& operator= (const cancellation_token_source& _Src);

cancellation_token_source& operator= (cancellation_token_source&& _Src);
```

### <a name="parameters"></a>Параметры

*_Src*<br/>
Операнд.

### <a name="return-value"></a>Возвращаемое значение

##  <a name="operator_eq_eq"></a> оператор ==

```
bool operator== (const cancellation_token_source& _Src) const;
```

### <a name="parameters"></a>Параметры

*_Src*<br/>
Операнд.

### <a name="return-value"></a>Возвращаемое значение

## <a name="see-also"></a>См. также

[Пространство имен concurrency](concurrency-namespace.md)
