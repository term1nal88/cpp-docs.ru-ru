---
title: Создание сценариев для регистратор ATL | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- scripting, registry scripting
- ATL, registry
- registrar scripts [ATL]
- scripts, Registrar scripts
- scripts, creating
ms.assetid: cbd5024b-8061-4a71-be65-7fee90374a35
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: abffe3c8d0a107c48c3a14a9bf584122229ad3b7
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43767264"
---
# <a name="creating-registrar-scripts"></a>Creating Registrar Scripts

Сценарий регистратора доступ на основе данных, а не на основе API, в системный реестр. Доступ на основе данных обычно эффективнее, так как он принимает только одну или две строки в сценарии, чтобы добавить раздел в реестр.

[Мастер элементов управления ATL](../atl/reference/atl-control-wizard.md) автоматически создает скрипт регистрации для COM-сервер. Этот сценарий можно найти в RGS-файл, связанный с объектом.

Обработчик скриптов регистратор ATL обрабатывает скрипта регистратора во время выполнения. ATL автоматически вызывает обработчик скриптов во время установки сервера.

В этой статье рассматриваются следующие темы, связанные с скрипты регистратора:

- [Основные сведения о синтаксисе формы Бэкуса-Наура (BNF)](../atl/understanding-backus-nauer-form-bnf-syntax.md)

- [Основные сведения о деревьях синтаксического анализа](../atl/understanding-parse-trees.md)

- [Примеры скриптов реестра](../atl/registry-scripting-examples.md)

- [Использование подстановочных параметров (препроцессор регистратора)](../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md)

- [Вызов скриптов](../atl/invoking-scripts.md)

## <a name="see-also"></a>См. также

[Компонент реестра (регистратор)](../atl/atl-registry-component-registrar.md)

