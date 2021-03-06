---
title: Рекомендации по обработке ввода вывода | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- I/O [MFC], about I/O
- file-based I/O options
- I/O [MFC]
- I/O [MFC], options
- I/O [MFC], file-based options
ms.assetid: d664b175-3b4a-40c3-b14b-39de6b12e419
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5a8d0d2c7e560338bbef5cbe432c325385734c56
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46385031"
---
# <a name="recommendations-for-handling-inputoutput"></a>Рекомендации по обработке ввода-вывода

Использование файловых операций ввода-вывода или не зависит от того, как отвечать на вопросы в следующее дерево принятия решений:

**Основные данные в приложении, находятся на диске в файле**

- Да, основные данные находятся в файл на диске:

     **Приложение весь файл целиком в память на открытие файла на чтение и запись файла целиком обратно на диск сохранения файла**

   - Да: Это вариант по умолчанию для документов MFC. Используйте `CDocument` сериализации.

   - Нет: Это обычно происходит на основе транзакций обновления файла. Можно обновить файл на основе каждой транзакции, не `CDocument` сериализации.

- Нет, основные данные не размещается на диске в файле:

     **Данные размещены в источнике данных ODBC**

   - Да, данные находятся в источник данных ODBC:

         Use MFC's database support. The standard MFC implementation for this case includes a `CDatabase` object, as discussed in the article [MFC: Using Database Classes with Documents and Views](../data/mfc-using-database-classes-with-documents-and-views.md). The application might also read and write an auxiliary file — the purpose of the application wizard "both a database view and file support" option. In this case, you'd use serialization for the auxiliary file.

   - Нет, данные не размещается в источник данных ODBC.

         Examples of this case: the data resides in a non-ODBC DBMS; the data is read via some other mechanism, such as OLE or DDE.

         In such cases, you won't use serialization, and your application won't have Open and Save menu items. You might still want to use a `CDocument` as a home base, just as an MFC ODBC application uses the document to store `CRecordset` objects. But you won't use the framework's default File Open/Save document serialization.

Для поддержки открытия, сохранения и сохранить в виде команд в меню "файл", платформа предоставляет сериализации документа. Сериализация считывает и записывает данные, включая объекты, производные от класса `CObject`, в постоянном хранилище, обычно файл на диске. Сериализации прост в использовании и обслуживает многие из вашим потребностям, но может быть нежелательным во многих приложениях доступ к данным. Доступ к данным приложений обычно обновляются данные на основе каждой транзакции. Они обновляются записей, затронутых транзакции, а не чтение и запись файла данных в целом за один раз.

Сведения о сериализации см. в разделе [сериализации](../mfc/serialization-in-mfc.md).

## <a name="see-also"></a>См. также

[Сериализация. Сериализация или Ввод/вывод баз данных](../mfc/serialization-serialization-vs-database-input-output.md)
