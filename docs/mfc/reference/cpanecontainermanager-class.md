---
title: Класс CPaneContainerManager | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CPaneContainerManager
- AFXPANECONTAINERMANAGER/CPaneContainerManager
- AFXPANECONTAINERMANAGER/CPaneContainerManager::AddPane
- AFXPANECONTAINERMANAGER/CPaneContainerManager::AddPaneContainerManager
- AFXPANECONTAINERMANAGER/CPaneContainerManager::AddPaneContainerManagerToDockablePane
- AFXPANECONTAINERMANAGER/CPaneContainerManager::AddPanesToList
- AFXPANECONTAINERMANAGER/CPaneContainerManager::AddPaneToList
- AFXPANECONTAINERMANAGER/CPaneContainerManager::AddPaneToRecentPaneContainer
- AFXPANECONTAINERMANAGER/CPaneContainerManager::CalcRects
- AFXPANECONTAINERMANAGER/CPaneContainerManager::CanBeAttached
- AFXPANECONTAINERMANAGER/CPaneContainerManager::CheckAndRemoveNonValidPane
- AFXPANECONTAINERMANAGER/CPaneContainerManager::CheckForMiniFrameAndCaption
- AFXPANECONTAINERMANAGER/CPaneContainerManager::Create
- AFXPANECONTAINERMANAGER/CPaneContainerManager::DoesAllowDynInsertBefore
- AFXPANECONTAINERMANAGER/CPaneContainerManager::DoesContainFloatingPane
- AFXPANECONTAINERMANAGER/CPaneContainerManager::EnableGrippers
- AFXPANECONTAINERMANAGER/CPaneContainerManager::FindPaneContainer
- AFXPANECONTAINERMANAGER/CPaneContainerManager::FindTabbedPane
- AFXPANECONTAINERMANAGER/CPaneContainerManager::GetAvailableSpace
- AFXPANECONTAINERMANAGER/CPaneContainerManager::GetDefaultPaneDivider
- AFXPANECONTAINERMANAGER/CPaneContainerManager::GetDockSiteFrameWnd
- AFXPANECONTAINERMANAGER/CPaneContainerManager::GetFirstPane
- AFXPANECONTAINERMANAGER/CPaneContainerManager::GetFirstVisiblePane
- AFXPANECONTAINERMANAGER/CPaneContainerManager::GetMinMaxOffset
- AFXPANECONTAINERMANAGER/CPaneContainerManager::GetMinSize
- AFXPANECONTAINERMANAGER/CPaneContainerManager::GetNodeCount
- AFXPANECONTAINERMANAGER/CPaneContainerManager::GetPaneContainerRTC
- AFXPANECONTAINERMANAGER/CPaneContainerManager::GetPaneCount
- AFXPANECONTAINERMANAGER/CPaneContainerManager::GetTotalRefCount
- AFXPANECONTAINERMANAGER/CPaneContainerManager::GetVisiblePaneCount
- AFXPANECONTAINERMANAGER/CPaneContainerManager::GetWindowRect
- AFXPANECONTAINERMANAGER/CPaneContainerManager::HideAll
- AFXPANECONTAINERMANAGER/CPaneContainerManager::InsertPane
- AFXPANECONTAINERMANAGER/CPaneContainerManager::IsAutoHideMode
- AFXPANECONTAINERMANAGER/CPaneContainerManager::IsEmpty
- AFXPANECONTAINERMANAGER/CPaneContainerManager::IsRootPaneContainerVisible
- AFXPANECONTAINERMANAGER/CPaneContainerManager::NotifyPaneDivider
- AFXPANECONTAINERMANAGER/CPaneContainerManager::OnPaneDividerMove
- AFXPANECONTAINERMANAGER/CPaneContainerManager::OnShowPane
- AFXPANECONTAINERMANAGER/CPaneContainerManager::PaneFromPoint
- AFXPANECONTAINERMANAGER/CPaneContainerManager::ReleaseEmptyPaneContainers
- AFXPANECONTAINERMANAGER/CPaneContainerManager::RemoveAllPanesAndPaneDividers
- AFXPANECONTAINERMANAGER/CPaneContainerManager::RemoveNonValidPanes
- AFXPANECONTAINERMANAGER/CPaneContainerManager::RemovePaneDivider
- AFXPANECONTAINERMANAGER/CPaneContainerManager::RemovePaneFromPaneContainer
- AFXPANECONTAINERMANAGER/CPaneContainerManager::ReplacePane
- AFXPANECONTAINERMANAGER/CPaneContainerManager::ResizePaneContainers
- AFXPANECONTAINERMANAGER/CPaneContainerManager::Serialize
- AFXPANECONTAINERMANAGER/CPaneContainerManager::SetDefaultPaneDividerForPanes
- AFXPANECONTAINERMANAGER/CPaneContainerManager::SetPaneContainerRTC
- AFXPANECONTAINERMANAGER/CPaneContainerManager::SetResizeMode
- AFXPANECONTAINERMANAGER/CPaneContainerManager::StoreRecentDockSiteInfo
dev_langs:
- C++
helpviewer_keywords:
- CPaneContainerManager [MFC], AddPane
- CPaneContainerManager [MFC], AddPaneContainerManager
- CPaneContainerManager [MFC], AddPaneContainerManagerToDockablePane
- CPaneContainerManager [MFC], AddPanesToList
- CPaneContainerManager [MFC], AddPaneToList
- CPaneContainerManager [MFC], AddPaneToRecentPaneContainer
- CPaneContainerManager [MFC], CalcRects
- CPaneContainerManager [MFC], CanBeAttached
- CPaneContainerManager [MFC], CheckAndRemoveNonValidPane
- CPaneContainerManager [MFC], CheckForMiniFrameAndCaption
- CPaneContainerManager [MFC], Create
- CPaneContainerManager [MFC], DoesAllowDynInsertBefore
- CPaneContainerManager [MFC], DoesContainFloatingPane
- CPaneContainerManager [MFC], EnableGrippers
- CPaneContainerManager [MFC], FindPaneContainer
- CPaneContainerManager [MFC], FindTabbedPane
- CPaneContainerManager [MFC], GetAvailableSpace
- CPaneContainerManager [MFC], GetDefaultPaneDivider
- CPaneContainerManager [MFC], GetDockSiteFrameWnd
- CPaneContainerManager [MFC], GetFirstPane
- CPaneContainerManager [MFC], GetFirstVisiblePane
- CPaneContainerManager [MFC], GetMinMaxOffset
- CPaneContainerManager [MFC], GetMinSize
- CPaneContainerManager [MFC], GetNodeCount
- CPaneContainerManager [MFC], GetPaneContainerRTC
- CPaneContainerManager [MFC], GetPaneCount
- CPaneContainerManager [MFC], GetTotalRefCount
- CPaneContainerManager [MFC], GetVisiblePaneCount
- CPaneContainerManager [MFC], GetWindowRect
- CPaneContainerManager [MFC], HideAll
- CPaneContainerManager [MFC], InsertPane
- CPaneContainerManager [MFC], IsAutoHideMode
- CPaneContainerManager [MFC], IsEmpty
- CPaneContainerManager [MFC], IsRootPaneContainerVisible
- CPaneContainerManager [MFC], NotifyPaneDivider
- CPaneContainerManager [MFC], OnPaneDividerMove
- CPaneContainerManager [MFC], OnShowPane
- CPaneContainerManager [MFC], PaneFromPoint
- CPaneContainerManager [MFC], ReleaseEmptyPaneContainers
- CPaneContainerManager [MFC], RemoveAllPanesAndPaneDividers
- CPaneContainerManager [MFC], RemoveNonValidPanes
- CPaneContainerManager [MFC], RemovePaneDivider
- CPaneContainerManager [MFC], RemovePaneFromPaneContainer
- CPaneContainerManager [MFC], ReplacePane
- CPaneContainerManager [MFC], ResizePaneContainers
- CPaneContainerManager [MFC], Serialize
- CPaneContainerManager [MFC], SetDefaultPaneDividerForPanes
- CPaneContainerManager [MFC], SetPaneContainerRTC
- CPaneContainerManager [MFC], SetResizeMode
- CPaneContainerManager [MFC], StoreRecentDockSiteInfo
ms.assetid: 3d974c15-a62f-4648-bb5b-cc31ab7950af
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d5037db54fbc758534e32ae6877e6ce2d23e3cc5
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50070612"
---
# <a name="cpanecontainermanager-class"></a>Класс CPaneContainerManager

`CPaneContainerManager` Класс управляет хранением и отображением текущего макета закрепления.
Для получения дополнительных сведений см. в разделе исходном коде, расположенном в **VC\\atlmfc\\src\\mfc** папке установки Visual Studio.

## <a name="syntax"></a>Синтаксис

```
class CPaneContainerManager : public CObject
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CPaneContainerManager::AddPane](#addpane)||
|[CPaneContainerManager::AddPaneContainerManager](#addpanecontainermanager)||
|[CPaneContainerManager::AddPaneContainerManagerToDockablePane](#addpanecontainermanagertodockablepane)||
|[CPaneContainerManager::AddPanesToList](#addpanestolist)||
|[CPaneContainerManager::AddPaneToList](#addpanetolist)||
|[CPaneContainerManager::AddPaneToRecentPaneContainer](#addpanetorecentpanecontainer)||
|[CPaneContainerManager::CalcRects](#calcrects)||
|[CPaneContainerManager::CanBeAttached](#canbeattached)||
|[CPaneContainerManager::CheckAndRemoveNonValidPane](#checkandremovenonvalidpane)||
|[CPaneContainerManager::CheckForMiniFrameAndCaption](#checkforminiframeandcaption)||
|[CPaneContainerManager::Create](#create)||
|[CPaneContainerManager::DoesAllowDynInsertBefore](#doesallowdyninsertbefore)||
|[CPaneContainerManager::DoesContainFloatingPane](#doescontainfloatingpane)||
|[CPaneContainerManager::EnableGrippers](#enablegrippers)||
|[CPaneContainerManager::FindPaneContainer](#findpanecontainer)||
|[CPaneContainerManager::FindTabbedPane](#findtabbedpane)||
|[CPaneContainerManager::GetAvailableSpace](#getavailablespace)||
|[CPaneContainerManager::GetDefaultPaneDivider](#getdefaultpanedivider)||
|[CPaneContainerManager::GetDockSiteFrameWnd](#getdocksiteframewnd)||
|[CPaneContainerManager::GetFirstPane](#getfirstpane)||
|[CPaneContainerManager::GetFirstVisiblePane](#getfirstvisiblepane)||
|[CPaneContainerManager::GetMinMaxOffset](#getminmaxoffset)||
|[CPaneContainerManager::GetMinSize](#getminsize)||
|[CPaneContainerManager::GetNodeCount](#getnodecount)||
|[CPaneContainerManager::GetPaneContainerRTC](#getpanecontainerrtc)||
|[CPaneContainerManager::GetPaneCount](#getpanecount)||
|[CPaneContainerManager::GetTotalRefCount](#gettotalrefcount)||
|[CPaneContainerManager::GetVisiblePaneCount](#getvisiblepanecount)||
|[CPaneContainerManager::GetWindowRect](#getwindowrect)||
|[CPaneContainerManager::HideAll](#hideall)||
|[CPaneContainerManager::InsertPane](#insertpane)||
|[CPaneContainerManager::IsAutoHideMode](#isautohidemode)||
|[CPaneContainerManager::IsEmpty](#isempty)||
|[CPaneContainerManager::IsRootPaneContainerVisible](#isrootpanecontainervisible)||
|[CPaneContainerManager::NotifyPaneDivider](#notifypanedivider)||
|[CPaneContainerManager::OnPaneDividerMove](#onpanedividermove)||
|[CPaneContainerManager::OnShowPane](#onshowpane)||
|[CPaneContainerManager::PaneFromPoint](#panefrompoint)||
|[CPaneContainerManager::ReleaseEmptyPaneContainers](#releaseemptypanecontainers)||
|[CPaneContainerManager::RemoveAllPanesAndPaneDividers](#removeallpanesandpanedividers)||
|[CPaneContainerManager::RemoveNonValidPanes](#removenonvalidpanes)||
|[CPaneContainerManager::RemovePaneDivider](#removepanedivider)||
|[CPaneContainerManager::RemovePaneFromPaneContainer](#removepanefrompanecontainer)||
|[CPaneContainerManager::ReplacePane](#replacepane)||
|[CPaneContainerManager::ResizePaneContainers](#resizepanecontainers)||
|[CPaneContainerManager::Serialize](#serialize)|Считывает этот объект из архива или записывает в него. (Переопределяет [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize).)|
|[CPaneContainerManager::SetDefaultPaneDividerForPanes](#setdefaultpanedividerforpanes)||
|[CPaneContainerManager::SetPaneContainerRTC](#setpanecontainerrtc)||
|[CPaneContainerManager::SetResizeMode](#setresizemode)||
|[CPaneContainerManager::StoreRecentDockSiteInfo](#storerecentdocksiteinfo)||

### <a name="remarks"></a>Примечания

Платформа автоматически создает экземпляры `CPaneContainerManager` объектов и внедряет их либо в [класс CPaneDivider](../../mfc/reference/cpanedivider-class.md) объектов или в [класс CMultiPaneFrameWnd](../../mfc/reference/cmultipaneframewnd-class.md) объектов.

`CPaneContainerManager` Класс хранит указатель на корень двоичного дерева, построенного из [CPaneContainer](../../mfc/reference/cpanecontainer-class.md) объектов.

## <a name="example"></a>Пример

В следующем примере показано, как получить ссылку на `CPaneContainerManager` объекта. Этот фрагмент кода является частью [задать размер области пример](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_SetPaneSize#5](../../mfc/reference/codesnippet/cpp/cpanecontainermanager-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CPaneContainerManager](../../mfc/reference/cpanecontainermanager-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxpanecontainermanager.h

##  <a name="addpane"></a>  CPaneContainerManager::AddPane

```
virtual void AddPane(CDockablePane* pControlBarToAdd);
```

### <a name="parameters"></a>Параметры

[in] *pControlBarToAdd*<br/>

### <a name="remarks"></a>Примечания

##  <a name="addpanecontainermanager"></a>  CPaneContainerManager::AddPaneContainerManager

```
virtual BOOL AddPaneContainerManager(
    CPaneContainerManager& srcManager,
    BOOL bOuterEdge);

virtual BOOL AddPaneContainerManager(
    CDockablePane* pTargetControlBar,
    DWORD dwAlignment,
    CPaneContainerManager& srcManager,
    BOOL bCopy);
```

### <a name="parameters"></a>Параметры

[in] *srcManager*<br/>
[in] *bOuterEdge*<br/>
[in] *pTargetControlBar*<br/>
[in] *dwAlignment*<br/>
[in] *bCopy*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="addpanecontainermanagertodockablepane"></a>  CPaneContainerManager::AddPaneContainerManagerToDockablePane

```
virtual BOOL AddPaneContainerManagerToDockablePane(
    CDockablePane* pTargetControlBar,
    CPaneContainerManager& srcManager);
```

### <a name="parameters"></a>Параметры

[in] *pTargetControlBar*<br/>
[in] *srcManager*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="addpanestolist"></a>  CPaneContainerManager::AddPanesToList

```
void AddPanesToList(
    CObList* plstControlBars,
    CObList* plstSliders);
```

### <a name="parameters"></a>Параметры

[in] *plstControlBars*<br/>
[in] *plstSliders*<br/>

### <a name="remarks"></a>Примечания

##  <a name="addpanetolist"></a>  CPaneContainerManager::AddPaneToList

```
void AddPaneToList(CDockablePane* pControlBarToAdd);
```

### <a name="parameters"></a>Параметры

[in] *pControlBarToAdd*<br/>

### <a name="remarks"></a>Примечания

##  <a name="addpanetorecentpanecontainer"></a>  CPaneContainerManager::AddPaneToRecentPaneContainer

```
virtual CDockablePane* AddPaneToRecentPaneContainer(
    CDockablePane* pBarToAdd,
    CPaneContainer* pRecentContainer);
```

### <a name="parameters"></a>Параметры

[in] *pBarToAdd*<br/>
[in] *pRecentContainer*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="calcrects"></a>  CPaneContainerManager::CalcRects

```
void CalcRects(
    CRect& rectOriginal,
    CRect& rectInserted,
    CRect& rectSlider,
    DWORD& dwSliderStyle,
    DWORD dwAlignment,
    CSize sizeMinOriginal,
    CSize sizeMinInserted);
```

### <a name="parameters"></a>Параметры

[in] *rectOriginal*<br/>
[in] *rectInserted*<br/>
[in] *rectSlider*<br/>
[in] *dwSliderStyle*<br/>
[in] *dwAlignment*<br/>
[in] *sizeMinOriginal*<br/>
[in] *sizeMinInserted*<br/>

### <a name="remarks"></a>Примечания

##  <a name="canbeattached"></a>  CPaneContainerManager::CanBeAttached

```
virtual BOOL CanBeAttached() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="checkandremovenonvalidpane"></a>  CPaneContainerManager::CheckAndRemoveNonValidPane

```
BOOL CheckAndRemoveNonValidPane(CWnd* pWnd);
```

### <a name="parameters"></a>Параметры

[in] *pWnd*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="checkforminiframeandcaption"></a>  CPaneContainerManager::CheckForMiniFrameAndCaption

```
virtual BOOL CheckForMiniFrameAndCaption(
    CPoint point,
    CDockablePane** ppTargetControlBar);
```

### <a name="parameters"></a>Параметры

[in] *точки*<br/>
[in] *ppTargetControlBar*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="create"></a>  CPaneContainerManager::Create

```
virtual BOOL Create(
    CWnd* pParentWnd,
    CPaneDivider* pDefaultSlider,
    CRuntimeClass* pContainerRTC = NULL);
```

### <a name="parameters"></a>Параметры

[in] *pParentWnd*<br/>
[in] *pDefaultSlider*<br/>
[in] *pContainerRTC*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="doesallowdyninsertbefore"></a>  CPaneContainerManager::DoesAllowDynInsertBefore

```
virtual BOOL DoesAllowDynInsertBefore() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="doescontainfloatingpane"></a>  CPaneContainerManager::DoesContainFloatingPane

```
virtual BOOL DoesContainFloatingPane();
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="enablegrippers"></a>  CPaneContainerManager::EnableGrippers

```
virtual void EnableGrippers(BOOL bEnable);
```

### <a name="parameters"></a>Параметры

[in] *bEnable*<br/>

### <a name="remarks"></a>Примечания

##  <a name="findpanecontainer"></a>  CPaneContainerManager::FindPaneContainer

```
virtual CPaneContainer* FindPaneContainer(
    CDockablePane* pBar,
    BOOL& bLeftBar);
```

### <a name="parameters"></a>Параметры

[in] *pBar*<br/>
[in] *bLeftBar*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="findtabbedpane"></a>  CPaneContainerManager::FindTabbedPane

```
CDockablePane* FindTabbedPane(UINT nID);
```

### <a name="parameters"></a>Параметры

[in] *nID*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="getavailablespace"></a>  CPaneContainerManager::GetAvailableSpace

```
virtual void GetAvailableSpace(CRect& rect) const;
```

### <a name="parameters"></a>Параметры

[in] *rect*<br/>

### <a name="remarks"></a>Примечания

##  <a name="getdefaultpanedivider"></a>  CPaneContainerManager::GetDefaultPaneDivider

```
CPaneDivider* GetDefaultPaneDivider() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="getdocksiteframewnd"></a>  CPaneContainerManager::GetDockSiteFrameWnd

```
virtual CWnd* GetDockSiteFrameWnd();
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="getfirstpane"></a>  CPaneContainerManager::GetFirstPane

```
virtual CBasePane* GetFirstPane() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="getfirstvisiblepane"></a>  CPaneContainerManager::GetFirstVisiblePane

```
virtual CWnd* GetFirstVisiblePane() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="getminmaxoffset"></a>  CPaneContainerManager::GetMinMaxOffset

```
virtual void GetMinMaxOffset(
    CPaneDivider* pSlider,
    int& nMinOffset,
    int& nMaxOffset,
    int& nStep);
```

### <a name="parameters"></a>Параметры

[in] *pSlider*<br/>
[in] *nMinOffset*<br/>
[in] *nMaxOffset*<br/>
[in] *nStep*<br/>

### <a name="remarks"></a>Примечания

##  <a name="getminsize"></a>  CPaneContainerManager::GetMinSize

```
virtual void GetMinSize(CSize& size);
```

### <a name="parameters"></a>Параметры

[in] *размер*<br/>

### <a name="remarks"></a>Примечания

##  <a name="getnodecount"></a>  CPaneContainerManager::GetNodeCount

```
int GetNodeCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="getpanecontainerrtc"></a>  CPaneContainerManager::GetPaneContainerRTC

```
CRuntimeClass* GetPaneContainerRTC() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="getpanecount"></a>  CPaneContainerManager::GetPaneCount

```
int GetPaneCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="gettotalrefcount"></a>  CPaneContainerManager::GetTotalRefCount

```
int GetTotalRefCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="getvisiblepanecount"></a>  CPaneContainerManager::GetVisiblePaneCount

```
virtual int GetVisiblePaneCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="getwindowrect"></a>  CPaneContainerManager::GetWindowRect

```
virtual void GetWindowRect(CRect& rect) const;
```

### <a name="parameters"></a>Параметры

[in] *rect*<br/>

### <a name="remarks"></a>Примечания

##  <a name="hideall"></a>  CPaneContainerManager::HideAll

```
virtual void HideAll();
```

### <a name="remarks"></a>Примечания

##  <a name="insertpane"></a>  CPaneContainerManager::InsertPane

```
virtual BOOL InsertPane(
    CDockablePane* pControlBarToInsert,
    CDockablePane* pTargetControlBar,
    DWORD dwAlignment,
    LPCRECT lpRect = NULL,
    AFX_DOCK_METHOD dockMethod = DM_UNKNOWN);
```

### <a name="parameters"></a>Параметры

[in] *pControlBarToInsert*<br/>
[in] *pTargetControlBar*<br/>
[in] *dwAlignment*<br/>
[in] *lpRect*<br/>
[in] *dockMethod*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="isautohidemode"></a>  CPaneContainerManager::IsAutoHideMode

```
BOOL IsAutoHideMode() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="isempty"></a>  CPaneContainerManager::IsEmpty

```
BOOL IsEmpty() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="isrootpanecontainervisible"></a>  CPaneContainerManager::IsRootPaneContainerVisible

```
virtual BOOL IsRootPaneContainerVisible() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="notifypanedivider"></a>  CPaneContainerManager::NotifyPaneDivider

```
void NotifyPaneDivider();
```

### <a name="remarks"></a>Примечания

##  <a name="onpanedividermove"></a>  CPaneContainerManager::OnPaneDividerMove

```
virtual int OnPaneDividerMove(
    CPaneDivider* pSlider,
    UINT uFlags,
    int nOffset,
    HDWP& hdwp);
```

### <a name="parameters"></a>Параметры

[in] *pSlider*<br/>
[in] *uFlags*<br/>
[in] *nOffset*<br/>
[in] *hdwp*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="onshowpane"></a>  CPaneContainerManager::OnShowPane

```
virtual BOOL OnShowPane(
    CDockablePane* pBar,
    BOOL bShow);
```

### <a name="parameters"></a>Параметры

[in] *pBar*<br/>
[in] *bShow*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="panefrompoint"></a>  CPaneContainerManager::PaneFromPoint

```
virtual CDockablePane* PaneFromPoint(
    CPoint point,
    int nSensitivity,
    BOOL bExactBar,
    BOOL& bIsTabArea,
    BOOL& bCaption);
```

### <a name="parameters"></a>Параметры

[in] *точки*<br/>
[in] *nSensitivity*<br/>
[in] *bExactBar*<br/>
[in] *bIsTabArea*<br/>
[in] *bCaption*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="releaseemptypanecontainers"></a>  CPaneContainerManager::ReleaseEmptyPaneContainers

```
void ReleaseEmptyPaneContainers();
```

### <a name="remarks"></a>Примечания

##  <a name="removeallpanesandpanedividers"></a>  CPaneContainerManager::RemoveAllPanesAndPaneDividers

```
void RemoveAllPanesAndPaneDividers();
```

### <a name="remarks"></a>Примечания

##  <a name="removenonvalidpanes"></a>  CPaneContainerManager::RemoveNonValidPanes

```
void RemoveNonValidPanes();
```

### <a name="remarks"></a>Примечания

##  <a name="removepanedivider"></a>  CPaneContainerManager::RemovePaneDivider

```
virtual void RemovePaneDivider(CPaneDivider* pSlider);
```

### <a name="parameters"></a>Параметры

[in] *pSlider*<br/>

### <a name="remarks"></a>Примечания

##  <a name="removepanefrompanecontainer"></a>  CPaneContainerManager::RemovePaneFromPaneContainer

```
virtual BOOL RemovePaneFromPaneContainer(CDockablePane* pControlBar);
```

### <a name="parameters"></a>Параметры

[in] *pControlBar*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="replacepane"></a>  CPaneContainerManager::ReplacePane

```
virtual BOOL ReplacePane(
    CDockablePane* pBarOld,
    CDockablePane* pBarNew);
```

### <a name="parameters"></a>Параметры

[in] *pBarOld*<br/>
[in] *pBarNew*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="resizepanecontainers"></a>  CPaneContainerManager::ResizePaneContainers

```
virtual void ResizePaneContainers(
    UINT nSide,
    BOOL bExpand,
    int nOffset,
    HDWP& hdwp);

virtual void ResizePaneContainers(
    CRect rect,
    HDWP& hdwp);
```

### <a name="parameters"></a>Параметры

[in] *nSide*<br/>
[in] *bExpand*<br/>
[in] *nOffset*<br/>
[in] *hdwp*<br/>
[in] *rect*<br/>

### <a name="remarks"></a>Примечания

##  <a name="serialize"></a>  CPaneContainerManager::Serialize

```
void Serialize(CArchive& ar);
```

### <a name="parameters"></a>Параметры

[in] *ar*<br/>

### <a name="remarks"></a>Примечания

##  <a name="setdefaultpanedividerforpanes"></a>  CPaneContainerManager::SetDefaultPaneDividerForPanes

```
void SetDefaultPaneDividerForPanes(CPaneDivider* pSlider);
```

### <a name="parameters"></a>Параметры

[in] *pSlider*<br/>

### <a name="remarks"></a>Примечания

##  <a name="setpanecontainerrtc"></a>  CPaneContainerManager::SetPaneContainerRTC

```
void SetPaneContainerRTC(CRuntimeClass* pContainerRTC);
```

### <a name="parameters"></a>Параметры

[in] *pContainerRTC*<br/>

### <a name="remarks"></a>Примечания

##  <a name="setresizemode"></a>  CPaneContainerManager::SetResizeMode

```
virtual void SetResizeMode(BOOL bResize);
```

### <a name="parameters"></a>Параметры

[in] *bResize*<br/>

### <a name="remarks"></a>Примечания

##  <a name="storerecentdocksiteinfo"></a>  CPaneContainerManager::StoreRecentDockSiteInfo

```
virtual void StoreRecentDockSiteInfo(CDockablePane* pBar);
```

### <a name="parameters"></a>Параметры

[in] *pBar*<br/>

### <a name="remarks"></a>Примечания

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CObject](../../mfc/reference/cobject-class.md)<br/>
[Класс CPaneContainer](../../mfc/reference/cpanecontainer-class.md)<br/>
[Класс CPaneDivider](../../mfc/reference/cpanedivider-class.md)
