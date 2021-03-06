---
title: Управление элементом управления хода выполнения | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CProgressCtrl class [MFC], working with
- progress controls [MFC], manipulating
- CProgressCtrl class [MFC], manipulating
- controlling progress controls [MFC]
- CProgressCtrl class [MFC], using
ms.assetid: 9af561d1-980b-4003-a6da-ff79be15bf23
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9fe784dfd63ec5c27a3695df3e6bc42ae0de2f7f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46416777"
---
# <a name="manipulating-the-progress-control"></a>Управление элементом управления "Индикатор выполнения"

Существует три способа, чтобы изменить текущее положение элемента управления хода выполнения ([CProgressCtrl](../mfc/reference/cprogressctrl-class.md)).

- Можно изменить положение величину предустановленного инкремента.

- Положение может быть изменено произвольного размера.

- Положение можно изменить на конкретное значение.

### <a name="to-change-the-position-by-a-preset-amount"></a>Изменение положения предустановленного величину

1. Используйте [SetStep](../mfc/reference/cprogressctrl-class.md#setstep) функция-член для установки интервала инкремента. По умолчанию это значение равно 10. Как правило, это значение задается как один из первоначальных параметров для элемента управления. Значение шага может быть отрицательным.

1. Используйте [StepIt](../mfc/reference/cprogressctrl-class.md#stepit) функция-член увеличение позиции. В результате элемент управления получает команду перерисовать себя.

    > [!NOTE]
    >  `StepIt` вызовет перенос. Например, если диапазон 1 -100, этап 20 и положение 90, `StepIt` переместит позицию до 10.

### <a name="to-change-the-position-by-an-arbitrary-amount"></a>Чтобы изменить расположение, произвольного размера

1. Используйте [OffsetPos](../mfc/reference/cprogressctrl-class.md#offsetpos) функция-член для изменения положения. `OffsetPos` будет принимать отрицательные значения.

    > [!NOTE]
    >  `OffsetPos`, в отличие от `StepIt`, не будет служить оболочкой положение. Новое положение корректируется оставаться в пределах диапазона.

### <a name="to-change-the-position-to-a-specific-value"></a>Изменение положения определенное значение

1. Используйте [SetPos](../mfc/reference/cprogressctrl-class.md#setpos) функция-член для установки положения конкретное значение. При необходимости, новая позиция устанавливается в диапазоне.

Как правило элемент управления выполнения используется исключительно для выходных данных. Чтобы получить текущую позицию без указания нового значения, используйте [GetPos](../mfc/reference/cprogressctrl-class.md#getpos).

## <a name="see-also"></a>См. также

[Использование CProgressCtrl](../mfc/using-cprogressctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)

