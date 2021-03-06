---
title: Серверные классы OLE | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.ole
dev_langs:
- C++
helpviewer_keywords:
- OLE server applications [MFC], server classes
- OLE server documents
- COM components, classes [MFC]
- component classes [MFC]
ms.assetid: 8e9b67a2-c0ff-479c-a8d6-19b36c5e6fc6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9994cdadb0ca2924a3ac773752ae40f3a750b74f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46442894"
---
# <a name="ole-server-classes"></a>Серверные классы OLE

Эти классы используются серверными приложениями. Серверные документы являются производными от `COleServerDoc` , а не из `CDocument`. Обратите внимание, что поскольку `COleServerDoc` является производным от `COleLinkingDoc`, серверные документы также может быть контейнеров, которые поддерживают связывание.

`COleServerItem` Класс представляет документ или фрагмент документа, могут быть внедрены в другом документе или связанного.

`COleIPFrameWnd` и `COleResizeBar` поддерживает редактирование на месте, когда объект находится в контейнере, и `COleTemplateServer` поддерживает создание пары "документ представление", поэтому можно изменить объекты OLE из других приложений.

[COleServerDoc](../mfc/reference/coleserverdoc-class.md)<br/>
Используется как базовый класс для классов документа серверного приложения. `COleServerDoc` объекты предоставляют основная часть поддержки сервера при взаимодействии с `COleServerItem` объектов. Возможность визуального редактирования обеспечивается с помощью архитектуры document/view библиотеки классов.

[CDocItem](../mfc/reference/cdocitem-class.md)<br/>
Абстрактный базовый класс для `COleClientItem` и `COleServerItem`. Объекты классов, производные от `CDocItem` представляют частей документов.

[COleServerItem](../mfc/reference/coleserveritem-class.md)<br/>
Используется для представления интерфейса OLE, который `COleServerDoc` элементов. Есть обычно `COleServerDoc` объект, представляющий внедренной частью документа. На серверах, которые поддерживают ссылки на части документов, может существовать множество `COleServerItem` объектов, каждый из которых представляет ссылку на часть документа.

[COleIPFrameWnd](../mfc/reference/coleipframewnd-class.md)<br/>
Предоставляет окна фрейма для представления, при редактировании серверного документа в месте.

[COleResizeBar](../mfc/reference/coleresizebar-class.md)<br/>
Предоставляет стандартный пользовательский интерфейс для изменения размеров на месте. Объекты этого класса всегда используются совместно с `COleIPFrameWnd` объектов.

[COleTemplateServer](../mfc/reference/coletemplateserver-class.md)<br/>
Используется для создания документов с помощью архитектуры document/view платформы. Объект `COleTemplateServer` объект делегирует большинство операций на связанный с ним `CDocTemplate` объекта.

[COleException](../mfc/reference/coleexception-class.md)<br/>
Исключение, полученный в результате ошибки во время обработки OLE. Этот класс используется, контейнеры и серверы.

## <a name="see-also"></a>См. также

[Общие сведения о классе](../mfc/class-library-overview.md)

