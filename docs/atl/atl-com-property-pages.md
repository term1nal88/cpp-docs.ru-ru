---
title: Страницы свойств ATL COM | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- property pages, COM
- ATL COM objects
- COM property pages
- property pages, ATL
- COM objects, ATL
- ATL property pages
ms.assetid: 663c7caa-2e5e-4b5c-b8ea-fd434ceb1654
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 208c89cad441a1fae70f5532204ec7856459de7f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46095863"
---
# <a name="atl-com-property-pages"></a>Страницы свойств COM в ATL

Страницы свойств COM предоставляют пользовательский интерфейс для задания свойств (или вызова методов) одного или нескольких COM-объектов. Страницы свойств широко используются элементы управления ActiveX для обеспечения многофункциональных пользовательских интерфейсов, которые позволяют свойства элемента управления необходимо задать во время разработки.

Страницы свойств являются COM-объекты, реализующие [IPropertyPage](/windows/desktop/api/ocidl/nn-ocidl-ipropertypage) или [IPropertyPage2](/windows/desktop/api/ocidl/nn-ocidl-ipropertypage2) интерфейс. Эти интерфейсы предоставляют методы, позволяющие странице, сопоставленной с параметром `site` (объект COM, представляющий контейнер страницы) и ряд *объектов* (COM-объекты, методы которого будут вызываться в ответ на изменения произведенные пользователем страницы свойств). Контейнер свойств страницы несет ответственность за вызов методов в интерфейсе страницы свойств, которые указывают странице, чтобы показать или скрыть его пользовательский интерфейс и когда следует применить изменения, сделанные пользователем к нижележащим объектам.

Каждая страница свойств можно построить полностью независимо от объектов, свойства которого можно задать. Все, что страница свойств потребностей — понимание определенный интерфейс (или набора интерфейсов) и предоставляют пользовательский интерфейс для вызова методов в этом интерфейсе.

Дополнительные сведения см. в разделе [вкладки свойств и страницы свойств](/windows/desktop/com/property-sheets-and-property-pages) в пакете Windows SDK.

## <a name="in-this-section"></a>В этом разделе

[Указание страниц свойств](../atl/specifying-property-pages.md)<br/>
Действия по указание страниц свойств для элемента управления вы и показывает пример класса.

[Реализация страниц свойств](../atl/implementing-property-pages.md)<br/>
Приводятся инструкции по реализации страницы свойств, включая методы для переопределения. Описывается полный пример на основе образца программы ATLPages.

## <a name="related-sections"></a>Связанные разделы

[Пример ATLPages](../visual-cpp-samples.md)<br/>
Абстрактный пример ATLPages образец, который реализует свойство страницы с помощью `IPropertyPageImpl`.

[ATL](../atl/active-template-library-atl-concepts.md)<br/>
Ссылки на разделы о программировании с использованием библиотеки ATL.

## <a name="see-also"></a>См. также

[Основные понятия](../atl/active-template-library-atl-concepts.md)

