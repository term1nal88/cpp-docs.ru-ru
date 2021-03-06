---
title: Включение классов (ATL) элементов управления | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.atl.controls.containment
dev_langs:
- C++
helpviewer_keywords:
- control containment classes
ms.assetid: e0812aee-c078-4ced-b967-247976552b9a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6c2fb505fd48aac41e49fcbe459fa0bc9c9a579f
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43756919"
---
# <a name="control-containment-classes"></a>Классы вложения элементов управления

Следующие классы поддерживают включения для размещения элементов управления:

- [CAxWindow](../atl/reference/caxwindow-class.md) предоставляет методы для работы с окном, в котором размещается элемент управления ActiveX.

- [CAxWindow2T](../atl/reference/caxwindow2t-class.md) содержит методы для работы окно, которое размещает элемент ActiveX, а также поддержку размещения Лицензированные элементы управления ActiveX.

- [IAxWinAmbientDispatch](../atl/reference/iaxwinambientdispatch-interface.md) вызывать методы на этом интерфейсе, чтобы задать свойства окружающей среды, доступные для размещаемого элемента управления.

- [IAxWinHostWindow](../atl/reference/iaxwinhostwindow-interface.md) вызывать методы на этом интерфейсе для создания и/или подключить элемент управления к объекту узла, или чтобы получить интерфейс из размещаемого элемента управления.

## <a name="related-articles"></a>Связанные статьи

[Часто задаваемые вопросы о вложении элементов управления ATL](../atl/atl-control-containment-faq.md)

## <a name="see-also"></a>См. также

[Общие сведения о классе](../atl/atl-class-overview.md)

