---
title: Архитектуру представления документов | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CView class [MFC], view architecture
- CDocument class [MFC]
- MFC, views
- views [MFC], MFC document/view model
- document objects [MFC]
- document objects [MFC], MFC document/view model
- MFC, documents
- documents [MFC], MFC document/view model
- document objects [MFC], document/view architecture
ms.assetid: 6127768a-553f-462a-b01b-a5ee6068c81e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 42c56ddea19266251bb12c06f6423c278f14bd71
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46404559"
---
# <a name="documentview-architecture"></a>Архитектура "документ-представление"

По умолчанию мастер приложений MFC создает скелет приложения с помощью класса документов и класс представления. MFC разделяет управление данными в этих двух классов. Документ, сохраняет данные и управляет печать данных и координирует обновления нескольких представлений данных. Представление отображает данные и управляет взаимодействием пользователя с ним, включая выбора и редактирования.

В этой модели объекта документа MFC считывает и записывает данные в постоянное хранилище. Документ также может предоставлять интерфейс к данным, везде, где она находится (например, как в базе данных). Объект отдельное представление управляет отображением данных из визуализации данных в окне для выбора пользователя и редактирования данных. Представление получает отображение данных из документа и передает их обратно документа все изменения данных.

Хотя можно легко переопределить или игнорировать разделение документов и представлений, существует веских причин этой модели, в большинстве случаев. Самая важная — при необходимости несколько представлений одного документа, например электронной таблицы и представления диаграммы. Документ представление-модель позволяет объект отдельное представление представления каждого представления данных, а общий код на все представления (например, Вычислительное ядро) может находиться в документе. Документ также принимает задачи обновления всех представлений при каждом изменении данных.

Архитектуры документ/представление MFC позволяет легко поддерживать несколько представлений, несколько типов документов, окна разделителей и другие функции ценные пользовательского интерфейса.

Части платформы MFC, наиболее видимой для пользователя и вам, программист, — это документ и представление. Основная часть работы в разработке приложения с помощью платформы переходит в записи документа и представления классов. Описание этого семейства статьи:

- В рамках документов, представлений и их взаимодействие в платформе.

- Что необходимо сделать для их реализации.

В сердце документов и представлений приведены четыре основные классы.

[CDocument](../mfc/reference/cdocument-class.md) (или [COleDocument](../mfc/reference/coledocument-class.md)) класс поддерживает объекты, используемые для хранения и управления данных программы и обеспечивает базовую функциональность для классов определенной документов. Документ представляет единицу данных, которые обычно пользователь открывает с команду «Открыть» в меню "файл" и сохраняет с помощью команды "Сохранить" в меню "файл".

[CView](../mfc/reference/cview-class.md) (или один из многих производных от него) обеспечивает базовую функциональность для классов представления, определяемые программистом. Представление, прикрепляемые к документу и выступает в качестве посредника между документа и пользователем: представление выводит на экран изображение документа на экране и интерпретирует ввод данных пользователем как операции после документа. Представление также отображает изображение для печати и предварительного просмотра.

[CFrameWnd](../mfc/reference/cframewnd-class.md) (или один из его вариантов) поддерживает объекты, которые предоставляет рамку вокруг одно или несколько представлений документа.

[CDocTemplate](../mfc/reference/cdoctemplate-class.md) (или [CSingleDocTemplate](../mfc/reference/csingledoctemplate-class.md) или [CMultiDocTemplate](../mfc/reference/cmultidoctemplate-class.md)) поддерживает объект, который управления один или несколько существующих документов данного типа, а также создание правильного документ, представления и объекты окон фрейма для этого типа.

На рисунке показана связь между документа и его представлением.

![Представление является частью документа, который отображается](../mfc/media/vc379n1.gif "vc379n1") документа и представления

Реализация документов и представлений в библиотеке классов Отделяет сами данные из своего отображения и операции пользователя с данными. Все изменения данных осуществляется через класс документа. Представление вызывает этот интерфейс для доступа и обновления данных.

Документы, их связанные с ними представления и окна фрейма, frame представлений, создаваемые шаблон документа. Шаблон документа несет ответственность за создание и управление ими для всех документов типа одного документа.

## <a name="what-do-you-want-to-know-more-about"></a>Выберите для получения дополнительных сведений

- [Портрет архитектуры документ/представление](../mfc/a-portrait-of-the-document-view-architecture.md)

- [Преимущества архитектуры документ/представление](../mfc/advantages-of-the-document-view-architecture.md)

- [Классы документа и представления, созданные с помощью мастера приложений](../mfc/document-and-view-classes-created-by-the-mfc-application-wizard.md)

- [Альтернативы для архитектуры документ/представление](../mfc/alternatives-to-the-document-view-architecture.md)

- [Добавление нескольких представлений в один документ](../mfc/adding-multiple-views-to-a-single-document.md)

- [Использование документов](../mfc/using-documents.md)

- [Использование представлений](../mfc/using-views.md)

- [Множественные типы документов, представления и окна фреймов](../mfc/multiple-document-types-views-and-frame-windows.md)

- [Инициализация и очистка документов и представлений](../mfc/initializing-and-cleaning-up-documents-and-views.md)

- [Инициализировать добавления пользователя к классам & представление документа](../mfc/creating-new-documents-windows-and-views.md)

- [Использование классов базы данных с документами и представлениями](../data/mfc-using-database-classes-with-documents-and-views.md)

- [Использование классов базы данных без документов и представлений](../data/mfc-using-database-classes-without-documents-and-views.md)

- [Примеры](../visual-cpp-samples.md)

## <a name="see-also"></a>См. также

[Элементы пользовательского интерфейса](../mfc/user-interface-elements-mfc.md)<br/>
[Windows](../mfc/windows.md)<br/>
[Окна фрейма](../mfc/frame-windows.md)<br/>
[Шаблоны документов и процесс создания документов и представлений](../mfc/document-templates-and-the-document-view-creation-process.md)<br/>
[Создание документа или представления](../mfc/document-view-creation.md)<br/>
[Создание документов, окон и представлений](../mfc/creating-new-documents-windows-and-views.md)

