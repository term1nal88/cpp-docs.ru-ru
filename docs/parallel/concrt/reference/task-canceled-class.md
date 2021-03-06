---
title: Класс task_canceled | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- task_canceled
- CONCRT/concurrency::task_canceled
- CONCRT/concurrency::task_canceled::task_canceled
dev_langs:
- C++
helpviewer_keywords:
- task_canceled class
ms.assetid: c3f0b234-2cc1-435f-a48e-995f45b190be
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: da18db2f2dde145c565b6309d9b27cdbcc0744cf
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46437668"
---
# <a name="taskcanceled-class"></a>Класс task_canceled

Этот класс описывает исключение, которое создается уровнем задач PPL для принудительной отмены текущей задачи. Он также создается методом `get()` метод [задачи](/visualstudio/extensibility/debugger/task-class-internal-members), для отмененной задачи.

## <a name="syntax"></a>Синтаксис

```
class task_canceled : public std::exception;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[task_canceled](#ctor)|Перегружен. Создает объект `task_canceled`.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`exception`

`task_canceled`

## <a name="requirements"></a>Требования

**Заголовок:** concrt.h

**Пространство имен:** concurrency

##  <a name="ctor"></a> task_canceled

Создает объект `task_canceled`.

```
explicit _CRTIMP task_canceled(_In_z_ const char* _Message) throw();

task_canceled() throw();
```

### <a name="parameters"></a>Параметры

*_Message*<br/>
Описательное сообщение об ошибке.

## <a name="see-also"></a>См. также

[Пространство имен concurrency](concurrency-namespace.md)
