---
title: Панель инструментов (редактор C++ изображений для значков) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.bitmap
- vc.editors.icon
dev_langs:
- C++
helpviewer_keywords:
- Graphics toolbar
- Image editor [C++], toolbar
- Image editor [C++], Option selector
- Properties window
- Option selector, Image editor
ms.assetid: a0af4209-6273-4106-a7c1-0edecc9b5755
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ed6639bdf86a54689834c6eda03a3b6ec4dd171d
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50063852"
---
# <a name="toolbar-c-image-editor-for-icons"></a>Панель инструментов (редактор C++ изображений для значков)

**Редактор изображений** инструментов содержит инструменты для рисования, рисования, ввода текста, стирания и управлении представлениями. Он также содержит селектора параметр, с помощью которого можно выбрать параметры для каждого инструмента. Например можно выбрать из различных кисти, масштаб увеличения и стили линий.

> [!NOTE]
> Все инструменты, доступные в **редактор изображений** инструментов также доступны из **изображение** меню (в разделе **средства** команду).

![Панель инструментов редактора изображений](../mfc/media/vcimageeditortoolbar.gif "vcImageEditorToolbar") панель инструментов редактора изображений

Для использования **редактор изображений** инструментов и **параметр** селектора, щелкните инструмент или параметра, возникает необходимость.

> [!TIP]
> Всплывающие подсказки отображаются при наведении курсора на кнопку панели инструментов. Эти советы помогут определить назначение каждой кнопки.

С помощью **параметр** селектор, можно указать ширину линии, кисть штриха и т.д. Значок на **параметр** выбора переключателя изменяется в зависимости от того, какое средство выбора.

![Рисование&#45;селектор фигуры на панели инструментов редактора изображений](../mfc/media/vcimageeditortoolbaroptionselector.gif "vcImageEditorToolbarOptionSelector") селектор параметров на панели инструментов редактора изображений

Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в приложениях для настольных систем](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework*. Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях, см. в разделе [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Требования

Нет

## <a name="see-also"></a>См. также

[Отображение или скрытие панели инструментов](displaying-or-hiding-the-toolbar-image-editor-for-icons.md)<br/>
[Сочетания клавиш](../windows/accelerator-keys-image-editor-for-icons.md)<br/>
[Редактор изображений для значков](../windows/image-editor-for-icons.md)