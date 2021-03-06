---
title: Изменение размера отдельных элементов управления | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Size to Content command
- size, controls
- text, autosizing controls to fit text
- controls [C++], sizing
ms.assetid: 14ccba02-7171-463a-a121-7018cf1e2e5a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9932b14b3d3afaa0afdff90c08ce44bf1f8648dc
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46373483"
---
# <a name="sizing-individual-controls"></a>Изменение размера отдельных элементов управления

Используйте маркеры размер элемента управления. Когда указатель находится на маркер, меняет форму для указания направления, в которых можно изменить размер элемента управления. Активные маркеры сплошной; Если маркер является пустой, не удается размеры элемента управления по этой оси.

Можно также изменить размер элемента управления, привязывая элемент управления к направляющим или полям или перемещая один привязанный элемент управления и руководство от другой.

### <a name="to-size-a-control"></a>Чтобы изменить размер элемента управления

1. Выберите элемент управления.

2. Перетащите маркеры изменения размера, чтобы изменить размер элемента управления:

   - Маркеры в верхней и сторон изменяют горизонтальный или вертикальный размер.

   - Маркеры в углах изменяют горизонтальный и вертикальный размер.

   > [!TIP]
   > Можно изменить размер элемента управления одного диалога единица (Единица) за раз, удерживая нажатой **Shift** ключа и используя **Стрелка вправо** и **стрелка вниз** ключи.

### <a name="to-automatically-size-a-control-to-fit-the-text-within-it"></a>Автоматическое изменение размера элемента управления в соответствии с текстом внутри него

1. Выберите **размер по содержимому** из **формат** меню.

\- или -

- Щелкните правой кнопкой мыши элемент управления и выберите **размер по содержимому** в контекстном меню.

Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в приложениях для настольных систем](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework*. Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях, см. в разделе [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Требования

Win32

## <a name="see-also"></a>См. также

[Элементы управления в диалоговых окнах](../windows/controls-in-dialog-boxes.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)