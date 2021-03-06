---
title: Управляет неограниченные Rich Edit | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- bottomless rich edit controls
- rich edit controls [MFC], bottomless
- CRichEditCtrl class [MFC], bottomless
ms.assetid: 2877dd32-1e9a-4fd1-98c0-66dcbbeef1de
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9ce3922bfd1a86864886057a4457627547fe85e0
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46373359"
---
# <a name="bottomless-rich-edit-controls"></a>Элементы управления "Rich Edit" "без дна"

Приложения можно изменить размер элемента управления rich edit ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) при необходимости, так как это всегда совпадает с размером его содержимого. Элемент управления форматированным редактированием поддерживает данную так называемые «без дна» функцию, отправив своему родительскому окну [EN_REQUESTRESIZE](/windows/desktop/Controls/en-requestresize) уведомление при каждом изменении размера его содержимое.

При обработке **EN_REQUESTRESIZE** сообщение уведомления, приложения должны изменяться размеры элемента управления к измерениям в указанном [REQRESIZE](/windows/desktop/api/richedit/ns-richedit-_reqresize) структуры. Приложение также может перемещать данные рядом с элементом управления для размещения элемента управления изменение высоты. Чтобы изменить размер элемента управления, можно использовать `CWnd` функция [SetWindowPos](../mfc/reference/cwnd-class.md#setwindowpos).

Вы можете принудительно элементе управления "без дна rich edit" для отправки **EN_REQUESTRESIZE** сообщение уведомления с помощью [RequestResize](../mfc/reference/cricheditctrl-class.md#requestresize) функция-член. Это сообщение может быть полезно в [OnSize](../mfc/reference/cwnd-class.md#onsize) обработчика.

Для получения **EN_REQUESTRESIZE** сообщений уведомлений, необходимо включить уведомления с помощью `SetEventMask` функция-член.

## <a name="see-also"></a>См. также

[Использование CRichEditCtrl](../mfc/using-cricheditctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)

