---
title: Параметры для CStatusBarCtrl | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CStatusBarCtrl
dev_langs:
- C++
helpviewer_keywords:
- status bar controls [MFC], settings
- CStatusBarCtrl class [MFC], settings
ms.assetid: adeba0c3-17f3-435c-b140-a57845e9ce49
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2411659e6ae33fe9ce81d508d3e7c206b1e5b113
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46440034"
---
# <a name="settings-for-the-cstatusbarctrl"></a>Параметры для CStatusBarCtrl

По умолчанию [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md) — окно состояния в нижней части родительского окна, но вы можете указать стиль CCS_TOP, чтобы они появились в верхней части клиентской области родительского окна.

Вы можете указать стиль SBARS_SIZEGRIP, чтобы включить захват для изменения размера в правом конце `CStatusBarCtrl` окном состояния. Захват регулировки размера аналогичен рамкой для изменения размера; он представляет собой прямоугольную область, в который пользователь может щелкните и перетащите для изменения размеров родительского окна.

> [!NOTE]
>  Если объединить стили CCS_TOP и SBARS_SIZEGRIP захвата для изменения размера не работает, несмотря на то, что система отображает его в окне состояния.

Процедура окна для окна состояния автоматически задает первоначальный размер и положение окна элемента управления. Ширина равна, совпадает с клиентской области родительского окна. Высота основана на основе метрик шрифта, выбранного в окне состояния контекста устройства и ширину границы окна.

Процедура окна автоматически изменяет размер окна состояния при каждом получении сообщения WM_SIZE. Как правило, при изменении размера родительского окна, родительский WM_SIZE сообщение передается в окне состояния.

Можно задать минимальную высоту области рисования окно состояния путем вызова [SetMinHeight](../mfc/reference/cstatusbarctrl-class.md#setminheight), указав минимальную высоту в пикселях. Область рисования не включает границы окна.

Получите значения ширины границы окна состояния путем вызова метода [GetBorders](../mfc/reference/cstatusbarctrl-class.md#getborders). Эта функция-член содержит указатель на массив с тремя элементами, получающий ширины горизонтальной границы, вертикальной границы и границы между прямоугольниками.

## <a name="see-also"></a>См. также

[Использование CStatusBarCtrl](../mfc/using-cstatusbarctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)

