---
title: 'Клиенты автоматизации: Использование библиотек типов | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- MkTypLib
dev_langs:
- C++
helpviewer_keywords:
- clients, Automation
- dispatch class [MFC]
- Automation clients, type libraries
- type libraries, Automation clients
- ODL (Object Description Language)
- ODL files
- classes [MFC], dispatch
- MkTypLib tool
- .odl files
ms.assetid: d405bc47-118d-4786-b371-920d035b2047
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 001dfb29a5ac0f6d93b0715bd2b86ccd60e91259
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50054609"
---
# <a name="automation-clients-using-type-libraries"></a>Клиенты автоматизации. Использование библиотек типов

Клиенты автоматизации должны иметь сведения о свойствах и методах объектов сервера, если клиентами для управления объектами данных сервера. Свойства имеют типы данных; методы часто возвращаемые значения и принимать параметры. Клиенту требуется сведения о типах данных, все действия для статически привязки к типу объекта server.

Эти сведения о типах известными несколькими способами. Рекомендуется создать библиотеку типов.

Сведения о [MkTypLib](/windows/desktop/Midl/differences-between-midl-and-mktyplib), см. в Windows SDK.

Visual C++ можно прочитать файл библиотеки типов и создание диспетчеризации класса, производного от [COleDispatchDriver](../mfc/reference/coledispatchdriver-class.md). Объект этого класса имеет свойства и операции, неэффективным серверного объекта. Приложение вызывает этот объект свойства и операции, и наследует функциональные возможности `COleDispatchDriver` направляет эти вызовы системы OLE, который в свою очередь направляет их к серверному объекту.

Visual C++ автоматически сохраняет этот файл библиотеки типов для вас, если вы решили включить службы автоматизации, если проект был создан. Как часть каждой сборки будет собран с MkTypLib TLB-файлу.

### <a name="to-create-a-dispatch-class-from-a-type-library-tlb-file"></a>Для создания класса диспетчеризации из файла библиотеки типов (.tlb)

1. В представлении классов или обозревателе решений щелкните правой кнопкой мыши проект и нажмите кнопку **добавить** и нажмите кнопку **Добавление класса** в контекстном меню.

1. В **Добавление класса** выберите **Visual c + +/ MFC** папку в области слева. Выберите **класс MFC из TypeLib** значок на панели справа и нажмите кнопку **откройте**.

1. В **мастер добавления класса из библиотеки типов** диалоговом окне выберите библиотеку типов из **доступные библиотеки типов** стрелку раскрывающегося списка. **Интерфейсы** окне отображаются интерфейсы, доступные для выбранной библиотеки типов.

    > [!NOTE]
    >  Интерфейсы можно выбрать из более чем одной библиотеки типов.

   Выберите интерфейсы, дважды щелкните их или щелкните **добавить** кнопки. После этого, имена для диспетчеризации классов будет отображаться в **созданные классы** поле. Можно изменить имена классов в `Class` поле.

   **Файл** поле отображает файл, в котором будет объявлен класс. (можно изменить это имя файла). Также можно использовать кнопку обзора для выбора других файлов, если вы хотите получить сведения о заголовке и реализации, созданных в существующие файлы или в каталоге, отличном от каталога проекта.

    > [!NOTE]
    >  Все классы для выбранных интерфейсов диспетчеризации будет помещен в файл, указанный здесь. При желании интерфейсы, объявляемые в отдельном заголовки необходимо запустить этот мастер для каждого файла заголовка, который вы хотите создать.

    > [!NOTE]
    >  Некоторые сведения о библиотеке типов могут храниться в файлах с. БИБЛИОТЕКА DLL. OCX, или. Расширения файлов OLB.

1. Нажмите кнопку **Готово**.

   Мастер будет затем написать код для диспетчеризации классов с помощью указанного класса и имена файлов.

## <a name="see-also"></a>См. также

[Клиенты автоматизации](../mfc/automation-clients.md)

