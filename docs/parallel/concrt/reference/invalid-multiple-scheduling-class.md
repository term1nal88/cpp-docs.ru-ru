---
title: Класс invalid_multiple_scheduling | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- invalid_multiple_scheduling
- CONCRT/concurrency::invalid_multiple_scheduling
- CONCRT/concurrency::invalid_multiple_scheduling::invalid_multiple_scheduling
dev_langs:
- C++
helpviewer_keywords:
- invalid_multiple_scheduling class
ms.assetid: e9a47cb7-a778-4df7-92b0-3752119fd4c7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 71898449447595db5df66ce619c423d62f2410be
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46384924"
---
# <a name="invalidmultiplescheduling-class"></a>Класс invalid_multiple_scheduling

Этот класс описывает исключение, создаваемое, если объект `task_handle` запланирован несколько раз с помощью метода `run` объекта `task_group` или `structured_task_group` без промежуточных вызовов любого из методов `wait` или `run_and_wait`.

## <a name="syntax"></a>Синтаксис

```
class invalid_multiple_scheduling : public std::exception;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[invalid_multiple_scheduling](#ctor)|Перегружен. Создает объект `invalid_multiple_scheduling`.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`exception`

`invalid_multiple_scheduling`

## <a name="requirements"></a>Требования

**Заголовок:** concrt.h

**Пространство имен:** concurrency

##  <a name="ctor"></a> invalid_multiple_scheduling

Создает объект `invalid_multiple_scheduling`.

```
explicit _CRTIMP invalid_multiple_scheduling(_In_z_ const char* _Message) throw();

invalid_multiple_scheduling() throw();
```

### <a name="parameters"></a>Параметры

*_Message*<br/>
Описательное сообщение об ошибке.

## <a name="see-also"></a>См. также

[Пространство имен concurrency](concurrency-namespace.md)<br/>
[Класс task_handle](task-handle-class.md)<br/>
[Класс task_group](task-group-class.md)<br/>
[run](task-group-class.md)<br/>
[wait](task-group-class.md)<br/>
[run_and_wait](task-group-class.md)<br/>
[Класс structured_task_group](structured-task-group-class.md)
