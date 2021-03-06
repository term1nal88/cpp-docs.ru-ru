---
title: Класс COleDropSource | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleDropSource
- AFXOLE/COleDropSource
- AFXOLE/COleDropSource::COleDropSource
- AFXOLE/COleDropSource::GiveFeedback
- AFXOLE/COleDropSource::OnBeginDrag
- AFXOLE/COleDropSource::QueryContinueDrag
dev_langs:
- C++
helpviewer_keywords:
- COleDropSource [MFC], COleDropSource
- COleDropSource [MFC], GiveFeedback
- COleDropSource [MFC], OnBeginDrag
- COleDropSource [MFC], QueryContinueDrag
ms.assetid: d3eecc5f-a70b-4a01-b705-7d2c098ebe17
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cb12135a0fbffdeba55130bced80c2f23c365caa
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50052360"
---
# <a name="coledropsource-class"></a>Класс COleDropSource

Разрешает передачу данных можно перетаскивать в качестве целевого объекта перетаскивания.

## <a name="syntax"></a>Синтаксис

```
class COleDropSource : public CCmdTarget
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[COleDropSource::COleDropSource](#coledropsource)|Создает объект `COleDropSource`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[COleDropSource::GiveFeedback](#givefeedback)|Изменяет курсор во время операции перетаскивания и вставки.|
|[COleDropSource::OnBeginDrag](#onbegindrag)|Обрабатывает захват мыши во время операции перетаскивания и вставки.|
|[COleDropSource::QueryContinueDrag](#querycontinuedrag)|Проверяет, является ли перетаскивания должно продолжаться.|

## <a name="remarks"></a>Примечания

[COleDropTarget](../../mfc/reference/coledroptarget-class.md) класс обрабатывает принимающей часть операции перетаскивания и вставки. `COleDropSource` Объект отвечает за определение, когда начинается операция перетаскивания, обратная связь во время операции перетаскивания и определение, когда заканчивается операция перетаскивания.

Чтобы использовать `COleDropSource` объекта, просто вызовите конструктор. Это упрощает процесс определения, какие события, например, щелчок мыши начать операцию перетаскивания с помощью [COleDataSource::DoDragDrop](../../mfc/reference/coledatasource-class.md#dodragdrop), [COleClientItem::DoDragDrop](../../mfc/reference/coleclientitem-class.md#dodragdrop), или [ COleServerItem::DoDragDrop](../../mfc/reference/coleserveritem-class.md#dodragdrop) функции. Эти функции создаст `COleDropSource` объект. Может возникнуть необходимость изменить поведение по умолчанию `COleDropSource` переопределяемые функции. Эти функции-члены будут вызываться в нужное время платформой.

Дополнительные сведения об операциях перетаскивания и вставки через интерфейсы OLE, см. в статье [Drag and Drop (OLE)](../../mfc/drag-and-drop-ole.md).

Дополнительные сведения см. в разделе [IDropSource](/windows/desktop/api/oleidl/nn-oleidl-idropsource) в пакете Windows SDK.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`COleDropSource`

## <a name="requirements"></a>Требования

**Заголовок:** afxole.h

##  <a name="coledropsource"></a>  COleDropSource::COleDropSource

Создает объект `COleDropSource`.

```
COleDropSource();
```

##  <a name="givefeedback"></a>  COleDropSource::GiveFeedback

Вызывается структурой после вызова метода [COleDropTarget::OnDragOver](../../mfc/reference/coledroptarget-class.md#ondragover) или [COleDropTarget::DragEnter](../../mfc/reference/coledroptarget-class.md#ondragenter).

```
virtual SCODE GiveFeedback(DROPEFFECT dropEffect);
```

### <a name="parameters"></a>Параметры

*dropEffect*<br/>
Эффект, который вы хотите отобразить для пользователя, обычно о том, что произойдет при перетаскивании на этом этапе с помощью выбранных данных. Как правило, это значение, возвращаемое в последний вызов к [CView::OnDragEnter](../../mfc/reference/cview-class.md#ondragenter) или [CView::OnDragOver](../../mfc/reference/cview-class.md#ondragover). Это может быть один или несколько из следующих:

- Не сможет достичь DROPEFFECT_NONE объект перетаскивания.

- DROPEFFECT_COPY, операция копирования будет выполнена.

- Выполняется операция перемещения объект DROPEFFECT_MOVE.

- Будет установлено DROPEFFECT_LINK ссылку по почте из перенесенных данных с исходными данными.

- Операция прокрутки перетащите объект DROPEFFECT_SCROLL о или происходит в целевом объекте.

### <a name="return-value"></a>Возвращаемое значение

Возвращает DRAGDROP_S_USEDEFAULTCURSORS, если перетаскивание выполняется, значение NOERROR, если это не так.

### <a name="remarks"></a>Примечания

Переопределите эту функцию для предоставления отзывов о что произойдет при перетаскивании на этом этапе. Реализация по умолчанию использует курсоры по умолчанию OLE. Дополнительные сведения об операциях перетаскивания и вставки через интерфейсы OLE, см. в статье [Drag and Drop (OLE)](../../mfc/drag-and-drop-ole.md).

Дополнительные сведения см. в разделе [IDropSource::GiveFeedback](/windows/desktop/api/oleidl/nf-oleidl-idropsource-givefeedback), [IDropTarget::DragOver](/windows/desktop/api/oleidl/nf-oleidl-idroptarget-dragover), и [IDropTarget::DragEnter](/windows/desktop/api/oleidl/nf-oleidl-idroptarget-dragenter) в пакете Windows SDK.

##  <a name="onbegindrag"></a>  COleDropSource::OnBeginDrag

Вызывается структурой при возникновении события, может начать операцию перетаскивания, например нажатие левой кнопки мыши.

```
virtual BOOL OnBeginDrag(CWnd* pWnd);
```

### <a name="parameters"></a>Параметры

*pWnd*<br/>
Указывает на окно, содержащее выбранные данные.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если перетаскивание может, в противном случае 0.

### <a name="remarks"></a>Примечания

Переопределите эту функцию, если вы хотите изменить способ запуска перетаскивания процесса. Реализация по умолчанию захватывает мышь и остается в режиме перетаскивания, пока пользователь нажимает кнопку мыши влево или вправо, или достигает ESC, после чего он освобождает мышь.

##  <a name="querycontinuedrag"></a>  COleDropSource::QueryContinueDrag

После начала перетаскивания, эта функция вызывается несколько раз платформой пока не будет отменена или завершена операция перетаскивания.

```
virtual SCODE QueryContinueDrag(
    BOOL bEscapePressed,
    DWORD dwKeyState);
```

### <a name="parameters"></a>Параметры

*bEscapePressed*<br/>
Указывает, была ли нажата клавиша ESC с момента последнего вызова `COleDropSource::QueryContinueDrag`.

*dwKeyState*<br/>
Содержит состояние управляющих клавиш на клавиатуре. Это представляет собой сочетание любое количество следующих: MK_CONTROL, MK_SHIFT, MK_ALT, MK_LBUTTON, MK_MBUTTON и MK_RBUTTON.

### <a name="return-value"></a>Возвращаемое значение

DRAGDROP_S_CANCEL, если клавиша ESC или правой кнопки мыши нажатии, или оставить кнопку вызывается перед перетаскиванием начинается. DRAGDROP_S_DROP, если должна быть выполнена операция перетаскивания. Значение S_OK, в противном случае.

### <a name="remarks"></a>Примечания

Переопределение, эта функция, если вы хотите изменить точку, в которой перетаскивание отменена или перетаскивания возникает.

Реализация по умолчанию инициирует раскрывающегося или отменяет перетаскивание следующим образом. Он отменяет операцию перетаскивания при нажатии клавиши ESC или правую кнопку мыши. При возникновении левой кнопки мыши после начала перетаскивания инициирует операцию перетаскивания. В противном случае возвращается значение s_ок и выполняет дополнительные операции не.

Так как эта функция вызывается часто, ее следует оптимизировать насколько это возможно.

## <a name="see-also"></a>См. также

[Пример MFC HIERSVR](../../visual-cpp-samples.md)<br/>
[Пример MFC OCLIENT](../../visual-cpp-samples.md)<br/>
[Класс CCmdTarget](../../mfc/reference/ccmdtarget-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)

