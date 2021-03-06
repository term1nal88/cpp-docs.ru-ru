---
title: 'Практическое: построение изолированных приложений, использующих компоненты СОМ | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- isolated applications [C++]
ms.assetid: 04587547-1174-44ab-bd99-1292358fba20
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6d2acabb6a5e9c35029b346097a66eaf1311826c
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45704032"
---
# <a name="how-to-build-isolated-applications-to-consume-com-components"></a>Практическое руководство. Построение изолированных приложений, использующих компоненты СОМ

Изолированные приложения — приложения, которые встроены в программу манифестов. Можно создать изолированных приложений, использующих компоненты СОМ.

### <a name="to-add-com-references-to-manifests-of-isolated-applications"></a>Чтобы добавить COM-ссылок в манифесты изолированных приложений

1. Откройте страницы свойств проекта изолированного приложения.

1. Разверните **свойства конфигурации** узел, а затем разверните **инструмент манифеста** узла.

1. Выберите **изолированная модель COM** страницу свойств, а затем задайте **имя файла компонента** имя COM-компонента, который будет в изолированном приложении.

1. Нажмите кнопку **ОК**.

### <a name="to-build-manifests-into-isolated-applications"></a>Для создания манифестов в изолированные приложения

1. Откройте страницы свойств проекта изолированного приложения.

1. Разверните **свойства конфигурации** узел, а затем разверните **инструмент манифеста** узла.

1. Выберите **входные и выходные данные** страницу свойств, а затем задайте **внедренный манифест** равным **Да**.

1. Нажмите кнопку **ОК**.

1. Постройте решение.

## <a name="see-also"></a>См. также

[Изолированные приложения](/windows/desktop/SbsCs/isolated-applications)<br/>
[О сборках Side-by-Side](/windows/desktop/SbsCs/about-side-by-side-assemblies-)