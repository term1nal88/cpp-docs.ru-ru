---
title: Реализация точки подключения (Visual C++) | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Implement Connection Point Wizard [C++]
- connection points [C++], implementing
ms.assetid: 5b37e4f9-73c9-4bef-b26d-365bc0662260
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9bba7fdfd44b0a0a97a6d110d2a44b492e1ca449
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46429335"
---
# <a name="implementing-a-connection-point-visual-c"></a>Реализация точки подключения (Visual C++)

Чтобы реализовать точку подключения с помощью мастера реализации точки подключения, нужно создать проект как COM-приложение ATL или как приложение MFC с поддержкой ATL. Вы можете использовать [Мастер проектов ATL](../atl/reference/atl-project-wizard.md), чтобы создать приложение ATL, или [добавить объект ATL в свое приложение MFC](../mfc/reference/adding-atl-support-to-your-mfc-project.md), чтобы реализовать поддержку ATL для приложения MFC.

> [!NOTE]
>  Сведения о реализации точек подключения для проекта MFC см. в разделе [Точки подключения](../mfc/connection-points.md).

Создав проект для реализации точки подключения, нужно сначала добавить объект ATL. См. раздел [Добавление объектов и элементов управления в проект ATL](../atl/reference/adding-objects-and-controls-to-an-atl-project.md), где перечислены мастеры, добавляющие объекты в проект ATL.

> [!NOTE]
>  Мастер не поддерживает диалоговые окна ATL, XML-веб-службы, созданные с помощью сервера ATL, объекты производительности и счетчики производительности.

Обладающий возможностью подключения объект (который называется источником) может предоставлять точку подключения для каждого из своих исходящих интерфейсов. Каждый исходящий интерфейс может быть реализован клиентом для объекта (который называется приемником). Дополнительные сведения см. в разделе [Точки подключения ATL](../atl/atl-connection-points.md).

### <a name="to-implement-a-connection-point"></a>Реализация точки подключения

1. В представлении классов щелкните правой кнопкой мыши имя класса для объекта ATL.

1. Выберите пункт **Добавить** в контекстном меню и щелкните **Добавить точку подключения**, чтобы отобразить [Мастер реализации точки соединения](../ide/implement-connection-point-wizard.md).

1. Выберите реализуемые интерфейсы точки подключения в соответствующих библиотеках типов и нажмите кнопку **Готово**.

1. В представлении классов просмотрите прокси-классы, созданные для каждой точки подключения. Эти классы отображаются в виде CProxy*имя_интерфейса*\<T> и являются производными от [IConnectionPointImpl](../atl/reference/iconnectionpointimpl-class.md).

1. Дважды щелкните класс точки подключения, чтобы отобразить определение класса точки подключения.

   - Когда вы реализуете точку подключения для интерфейса собственного проекта, отображается следующее определение:

        ```
        template< class T >
        class CProxyInterfaceName :
           public IConnectionPointImpl< T, &IID_InterfaceName >
        {
        public:
        };
        ```

         If you implement a local interface, methods and properties appear in the class body.

   - Когда вы реализуете точку подключения для другого интерфейса, определение включает в себя методы этого интерфейса с префиксом `Fire_`.

## <a name="see-also"></a>См. также

[Добавление функциональных возможностей с помощью мастеров кода](../ide/adding-functionality-with-code-wizards-cpp.md)<br>
[Добавление точек подключения к объектам](../atl/adding-connection-points-to-an-object.md)