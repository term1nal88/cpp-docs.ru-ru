---
title: 'Затраченное время: Классы автоматизации | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- adding dates
- calculating dates and times
- dates, calculating intervals
- elapsed time, calculating in Automation
- Automation classes, elapsed time
- time, elapsed
- intervals, date and time
- calculations, date and time
ms.assetid: 26b34b37-c10e-4b91-82c3-1dc5ffb5361f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d8f36c48cf654379e9db3a99c2404732dca30f63
ms.sourcegitcommit: 997e6b7d336cddb388bb6e9e56527725fcaa0624
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/08/2018
ms.locfileid: "48860326"
---
# <a name="elapsed-time-automation-classes"></a>Затраченное время: Классы автоматизации

Эта процедура демонстрирует для вычисления разницы между двумя `CTime` объектов и получите `CTimeSpan` результат.

## <a name="to-calculate-elapsed-time"></a>Для вычисления истекшего времени

1. Создайте две `COleDateTime` объектов.

1. Задать один из `COleDateTime` объектов на текущий момент времени.

1. Для выполнения некоторых много времени задачи.

1. Задать другие `COleDateTime` объекта на текущий момент времени.

1. Использовать разницу между двумя значениями времени.

   [!code-cpp[NVC_ATLMFC_Utilities#178](../atl-mfc-shared/codesnippet/cpp/elapsed-time-automation-classes_1.cpp)]

## <a name="see-also"></a>См. также

[Дата и время. Поддержка автоматизации](../atl-mfc-shared/date-and-time-automation-support.md)
