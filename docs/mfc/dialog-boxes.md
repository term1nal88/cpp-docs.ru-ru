---
title: Диалоговые окна | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- modeless dialog boxes [MFC], MFC dialog boxes
- MFC, dialog boxes
- modal dialog boxes [MFC], MFC dialog boxes
- CDialog class [MFC], MFC dialog boxes
- MFC dialog boxes
ms.assetid: e4feea1a-8360-4ccb-9b84-507f1ccd9ef3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f26f5cad47815c25602eba836a482e6f6cecc85d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46424941"
---
# <a name="dialog-boxes"></a>Диалоговые окна

Приложения для Windows часто связываются с пользователем с помощью диалоговых окон. Класс [CDialog](../mfc/reference/cdialog-class.md) предоставляет интерфейс для управления диалоговым окнам, редактор диалоговых окон Visual C++ позволяет легко проектировать диалоговым окнам и создавать свои ресурсы шаблона диалогового окна и мастеры кода упрощают процесс инициализации и Проверка элементов управления в диалоговом окне и сбора значений, введенных пользователем.

Диалоговые окна содержат элементы управления, включая:

- Стандартные элементы управления Windows такие как изменение поля, кнопок, списков, поля со списком, элементов управления древовидного типа, список элементов управления и индикаторы выполнения.

- Элементы управления ActiveX.

- Определяемые владельцем элементы управления: элементы управления, которые вы несете ответственность за рисование в диалоговом окне.

Большинство диалоговых окна являются модальными, который пользователь должен закрыть диалоговое окно, прежде чем использовать любой другой части программы. Но можно создать немодальные диалоговые окна, которые позволяют пользователям работать с другими окнами при открытом диалоговом окне. MFC поддерживает оба вида диалоговое окно с классом `CDialog`. Элементы управления размещаются и управляются с помощью ресурса шаблона диалогового окна, созданные с помощью [редактор диалоговых окон](../windows/dialog-editor.md).

[Вкладки свойств](../mfc/property-sheets-mfc.md), также известный как вкладку диалоговые окна, диалоговые окна, которые содержат «страниц» различных диалоговых элементов управления. Каждая страница имеет «вкладки» в верхней папке. Щелкнув вкладку помещает эту страницу на передний план диалогового окна.

## <a name="what-do-you-want-to-know-more-about"></a>Выберите для получения дополнительных сведений

- [Пример. Отображение диалогового окна через команду меню](../mfc/example-displaying-a-dialog-box-via-a-menu-command.md)

- [Компоненты диалоговых окон в платформе](../mfc/dialog-box-components-in-the-framework.md)

- [Модальные и немодальные диалоговые окна](../mfc/modal-and-modeless-dialog-boxes.md)

- [Вкладки свойств и страницы свойств](../mfc/property-sheets-and-property-pages-mfc.md) в диалоговом окне

- [Создание ресурса диалогового окна](../mfc/creating-the-dialog-resource.md)

- [Создание класса диалогового окна с помощью мастеров кода](../mfc/creating-a-dialog-class-with-code-wizards.md)

- [Жизненный цикл диалогового окна](../mfc/life-cycle-of-a-dialog-box.md)

- [Обмен данными диалоговых окон (DDX) и проверки (DDV)](../mfc/dialog-data-exchange-and-validation.md)

- [Типобезопасный доступ к элементам управления в диалоговом окне](../mfc/type-safe-access-to-controls-in-a-dialog-box.md)

- [Сопоставление сообщений Windows с классом](../mfc/mapping-windows-messages-to-your-class.md)

- [Часто переопределяемые функции-члены](../mfc/commonly-overridden-member-functions.md)

- [Часто добавляемые функции-члены](../mfc/commonly-added-member-functions.md)

- [Классы общих диалоговых окон](../mfc/common-dialog-classes.md)

- [Диалоговые окна в OLE](../mfc/dialog-boxes-in-ole.md)

- Создание приложения, пользовательский интерфейс которого является диалоговым окном: см. в разделе [CMNCTRL1](../visual-cpp-samples.md) или [CMNCTRL2](../visual-cpp-samples.md) образец программ. Мастер приложений предоставляет также этот параметр.

- [Примеры](../mfc/dialog-sample-list.md)

## <a name="see-also"></a>См. также

[Элементы пользовательского интерфейса](../mfc/user-interface-elements-mfc.md)
