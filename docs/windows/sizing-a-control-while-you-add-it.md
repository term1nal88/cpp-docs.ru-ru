---
title: Изменение размера элемента управления при его добавлении | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- dialog box controls [C++], size
- controls [C++], sizing
ms.assetid: 06b1dd2b-0ba1-4e1f-adc3-cb73679f765e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e60803ec9696e541376aa8530cb4c01d32b9e569
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46418866"
---
# <a name="sizing-a-control-while-you-add-it"></a>Изменение размера элемента управления при его добавлении

### <a name="to-size-a-control-while-you-add-it"></a>Чтобы изменить размер элемента управления при его добавлении

1. Выберите элемент управления в [окно панели элементов](/visualstudio/ide/reference/toolbox).

2. Поместите курсор (которая отображается как перекрестие) место верхнего левого угла нового элемента управления в диалоговом окне.

3. Щелкните и удерживайте кнопку мыши, чтобы закрепить в левом верхнем углу элемента управления в диалоговом окне, а затем перетащите курсор вправо и вниз до нужного размера элемента управления.

   > [!NOTE]
   > Фактически можно привязать любой из четырех углов рисуемого элемента управления. Эта процедура в качестве примера использован верхнего левого угла.

4. Отпустите кнопку мыши. В диалоговом окне, в заданный размер сопоставляет элемент управления.

   > [!TIP]
   > Можно изменить размер элемента управления после перетаскивания диалоговом окне, перемещая маркеры на границы элемента управления. Дополнительные сведения см. в разделе [изменения размера отдельных элементов управления](../windows/sizing-individual-controls.md).

Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в приложениях для настольных систем](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework*. Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях, см. в разделе [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Требования

Win32

## <a name="see-also"></a>См. также

[Элементы управления в диалоговых окнах](../windows/controls-in-dialog-boxes.md)<br/>
[Добавление обработчиков событий для элементов управления диалоговых окон](../windows/adding-event-handlers-for-dialog-box-controls.md)<br/>
[Элементы управления "Диалоговое окно" и типы переменных](../ide/dialog-box-controls-and-variable-types.md)