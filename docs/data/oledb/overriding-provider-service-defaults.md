---
title: Переопределение поставщика по умолчанию | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- service providers [OLE DB]
- OLE DB services [OLE DB], overriding defaults
ms.assetid: 08e366c0-74d8-463b-93a6-d58a8dc195f8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 4cd51eaa06c8e9600b80d4a3cf6e192443105e65
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50072191"
---
# <a name="overriding-provider-service-defaults"></a>Переопределение используемых по умолчанию параметров службы поставщика

Значение реестра поставщика для OLEDB_SERVICES возвращается как значение по умолчанию для [DBPROP_INIT_OLEDBSERVICES, установить](/previous-versions/windows/desktop/ms716898) свойство инициализации на объекте источника данных.

Пока существует запись реестра, накапливаются объекты поставщика, и пользователь может переопределить поставщика по умолчанию для включенных служб, задав `DBPROP_INIT_OLEDBSERVICES` свойства до инициализации. Для включения или отключения определенной службы, пользователь обычно получает текущее значение `DBPROP_INIT_OLEDBSERVICES` свойства, задает или сбрасывает бит для конкретного свойства включить или отключить и свойство. `DBPROP_INIT_OLEDBSERVICES` можно задать непосредственно в OLE DB или в строке подключения, передаваемый ADO или `IDataInitialize::GetDatasource`. В следующей таблице перечислены соответствующие значения для включения или отключения отдельных служб.

|Службы по умолчанию включен|Значение свойства DBPROP_INIT_OLEDBSERVICES, установить|Значение в строке подключения|
|------------------------------|------------------------------------------------|--------------------------------|
|Все службы (по умолчанию)|`DBPROPVAL_OS_ENABLEALL`|«Службы OLE DB = -1;»|
|Все, за исключением и автоматического зачисления|`DBPROPVAL_OS_ENABLEALL &`<br /><br /> `~DBPROPVAL_OS_RESOURCEPOOLING &`<br /><br /> `~DBPROPVAL_OS_TXNENLISTMENT`|«Службы OLE DB = -4;»|
|Все, кроме клиентский курсор|`DBPROPVAL_OS_ENABLEALL &`<br /><br /> `~DBPROPVAL_OS_CLIENTCURSOR`|«Службы OLE DB = -5;»|
|Все, кроме пулов, автоматического зачисления и клиентских курсоров|`DBPROPVAL_OS_ENABLEALL &`<br /><br /> `~DBPROPVAL_OS_TXNENLISTMENT &`<br /><br /> `~DBPROPVAL_OS_CLIENTCURSOR`|«Службы OLE DB = -7;»|
|Нет служб|`~DBPROPVAL_OS_ENABLEALL`|«Службы OLE DB = 0;»|

Если запись реестра не существует для поставщика, диспетчеры компонентов не будет выполнять статистическую обработку объекты поставщика и службы не будет вызываться, даже если это явно запрошено пользователем.

## <a name="see-also"></a>См. также

[Создание пулов ресурсов](/previous-versions/windows/desktop/ms713655)<br/>
[Как потребители используют Создание пулов ресурсов](/previous-versions/windows/desktop/ms715907)<br/>
[Как поставщики эффективно работают с пулами ресурсов](/previous-versions/windows/desktop/ms714906)<br/>
[Включение и отключение служб OLE DB](../../data/oledb/enabling-and-disabling-ole-db-services.md)<br/>