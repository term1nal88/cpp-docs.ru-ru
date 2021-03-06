---
title: Функция CAtlServiceModuleT::Start | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
f1_keywords:
- CServiceModule.Start
- CServiceModule::Start
dev_langs:
- C++
helpviewer_keywords:
- Start method
ms.assetid: b5193a23-41bc-42d2-8d55-3eb43dc62238
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2b1edd5d01300324a8d24b41aa289f510cf078ae
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46021778"
---
# <a name="catlservicemoduletstart-function"></a>Функция CAtlServiceModuleT::Start

При запуске службы `_tWinMain` вызовы `CAtlServiceModuleT::WinMain`, который в свою очередь вызывает `CAtlServiceModuleT::Start`.

`CAtlServiceModuleT::Start` Задает массив `SERVICE_TABLE_ENTRY` структур, которые сопоставляются его функция запуска каждой службы. Этот массив передается в функцию Win32 API, [StartServiceCtrlDispatcher](/windows/desktop/api/winsvc/nf-winsvc-startservicectrldispatchera). В теории, один исполняемый ФАЙЛ может обрабатывать несколько служб, и массив может иметь несколько `SERVICE_TABLE_ENTRY` структуры. Тем не менее, в настоящее время это служба, созданный ATL поддерживает только одну службу в EXE-файла. Таким образом, массив содержит единственную запись, которая содержит имя службы и `_ServiceMain` как функцию запуска. `_ServiceMain` — Это статическая функция-член из `CAtlServiceModuleT` , вызывает функцию-член, `ServiceMain`.

> [!NOTE]
>  Сбой `StartServiceCtrlDispatcher` для подключения к службе управления manager (SCM), скорее всего, означает, что программа не выполняется как служба. В этом случае программа вызывает `CAtlServiceModuleT::Run` напрямую, чтобы программа может запускаться как локальный сервер. Дополнительные сведения о запуске программы как локального сервера, см. в разделе [упрощению](../atl/debugging-tips.md).

## <a name="see-also"></a>См. также

[Службы](../atl/atl-services.md)<br/>
[CAtlServiceModuleT::Start](../atl/reference/catlservicemodulet-class.md#start)

