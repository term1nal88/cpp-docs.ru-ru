---
title: Выбор и операции с записями | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- records, selecting
- record selection, MFC ODBC classes
- ODBC recordsets, selecting records
ms.assetid: 7f0b3a4a-9941-4475-a612-9ec8d15b7691
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 8cfbeaa1fac2fd9df707dfa9c16ec168d48fc215
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50078353"
---
# <a name="selecting-and-manipulating-records"></a>Выбор и операции с записями

Обычно при выборе записей из источника данных, используя SQL **ВЫБЕРИТЕ** инструкции, вы получаете результирующий набор, который представляет собой набор записей из таблицы или запроса. Классы базы данных используйте объект набора записей для выбора и получить доступ к результирующего набора. Это объект класса конкретного приложения, производного от класса [CRecordset](../../mfc/reference/crecordset-class.md). При определении класса набора записей, вами источника данных, чтобы связать его с помощью таблицы для использования и столбцы таблицы. Мастер приложений MFC или **Добавление класса** (как описано в разделе [Добавление потребителя ODBC MFC](../../mfc/reference/adding-an-mfc-odbc-consumer.md)) создает класс с подключением к определенному источнику данных. Мастер прописывает [GetDefaultSQL](../../mfc/reference/crecordset-class.md#getdefaultsql) функция-член класса `CRecordset` для получения имени таблицы. Дополнительные сведения об использовании мастера для создания классов набора записей, см. в разделе [Поддержка баз данных, мастер приложений MFC](../../mfc/reference/database-support-mfc-application-wizard.md) и [Добавление потребителя ODBC MFC](../../mfc/reference/adding-an-mfc-odbc-consumer.md).

С помощью [CRecordset](../../mfc/reference/crecordset-class.md) объекта во время выполнения, вы можете:

- Проверьте поля данных текущей записи.

- Фильтровать или сортировать набор записей.

- Настройка по умолчанию SQL **ВЫБЕРИТЕ** инструкции.

- Просмотрите выбранные записи.

- Добавление, обновление или удаление записей (если источник данных и набор записей являются обновляемыми).

- Проверить, разрешено ли выполнение обновления наборов записей и обновите содержимое набора записей.

После завершения использования объекта набора записей, закройте и удалите его. Дополнительные сведения о наборах см. в разделе [записей (ODBC)](../../data/odbc/recordset-odbc.md).

## <a name="see-also"></a>См. также

[ODBC и MFC](../../data/odbc/odbc-and-mfc.md)