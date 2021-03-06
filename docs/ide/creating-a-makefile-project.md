---
title: Создание проекта Makefile на C++| Документация Майкрософт
ms.custom: ''
ms.date: 09/12/2018
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.appwiz.makefile.project
dev_langs:
- C++
helpviewer_keywords:
- Makefile projects, creating
- project files [C++], Makefile projects
ms.assetid: dd077af3-97a8-48fb-baaa-cf7e07ddef61
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a3360d2ed86d220bc59d6f09f582c71b48f7d78c
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46399487"
---
# <a name="creating-a-c-makefile-project"></a>Создание проекта Makefile на C++

Объект *makefile* представляет собой текстовый файл с инструкциями по компиляции и компоновке (или *сборке*) некоторого набора файлов исходного кода C++. Программа *make* считывает файл makefile и вызывает компилятор, компоновщик и другие программы для создания исполняемого файла. Реализация *make*, созданная корпорацией Майкрософт, носит имя **NMAKE**. (По умолчанию Visual Studio использует систему MSBuild на основе файлов .vcsproj, которые создаются через пункт меню **Файл | Создать | Проект**.)

Если у вас есть существующий проект Makefile, который вы хотите развивать и (или) отлаживать в интегрированной среде разработки Visual Studio, у вас есть следующие варианты.

- Создайте в Visual Studio проект Makefile, который использует существующий файл makefile для сборки кода в интегрированной среде разработки. (Вам будут доступны не все возможности интегрированной среды разработки, которые есть в собственном проекте MSBuild.) См. также раздел [о создании проекта Makefile](#create_a_makefile_project) ниже.
- Используйте мастер **создания нового проекта из существующих файлов кода**, чтобы создать собственный проект MSBuild из исходного кода. Дополнительные сведения см. в разделе [Практическое руководство. Создание проекта C++ из существующего кода](how-to-create-a-cpp-project-from-existing-code.md).
- **Visual Studio 2017 и более поздних версий**: используйте функцию **Открыть папку**, чтобы открыть файл makefile. Дополнительные сведения см. в статье [Open Folder projects in Visual C++](non-msbuild-projects.md) (Открытие папки проектов в Visual C++).

## <a name="a-namecreateamakefileproject-to-create-a-makefile-project-with-the-makefile-project-template"></a><a name="create_a_makefile_project"> Создание проекта Makefile с использованием шаблона проекта Makefile

В Visual Studio 2017 и более поздних версиях шаблон проекта Makefile доступен, если установлена рабочая нагрузка разработки классических приложений на C++.

Используйте мастер, чтобы указать команды и среду, используемые файлом makefile. Затем этот проект можно использовать для сборки кода в среде разработки Visual Studio.

По умолчанию проект makefile не отображает в обозревателе решений никаких файлов. Проект makefile задает параметры сборки, которые показаны на странице свойств проекта.

Выходной файл, который задается в проекте, не влияет на имя, которое формирует скрипт построения; он указывает только на намерения. Файл makefile по-прежнему управляет процессом сборки и указывает ее целевые объекты.

1. На начальной странице Visual Studio введите строку "makefile" в поле поиска **Новый проект**. Или же откройте диалоговое окно **Новый проект**, разверните узел **Visual C++** > **Общие** (Visual Studio 2015) или **Прочие** (Visual Studio 2017) и в области шаблонов выберите **Проект Makefile**, чтобы открыть мастер проектов.

1. На странице [Параметры приложения](../ide/application-settings-makefile-project-wizard.md) предоставьте сведения о команде, выводе, удалении и перестроении для отладочной и окончательной сборок.

1. Нажмите кнопку **Готово**, чтобы закрыть мастер и открыть вновь созданный проект в **обозревателе решений**.

На этой странице свойств можно просматривать и изменять свойства проекта. Сведения об отображении страницы свойств см. в разделе [Установка свойств проекта Visual C++](../ide/working-with-project-properties.md).

## <a name="see-also"></a>См. также

[Мастер проекта Makefile](../ide/makefile-project-wizard.md)<br/>
[Специальные символы в файле Makefile](../build/special-characters-in-a-makefile.md)<br/>
[Содержимое файла Makefile](../build/contents-of-a-makefile.md)<br/>
