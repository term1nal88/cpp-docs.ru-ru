---
title: Запуск программы NMAKE | Документация Майкрософт
ms.custom: ''
ms.date: 09/05/2018
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- targets, building
- response files, NMAKE
- targets
- command files
- NMAKE program, targets
- NMAKE program, running
- command files, NMAKE
ms.assetid: 0421104d-8b7b-4bf3-86c1-928d9b7c1a8c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bdc9d89dbc0e77a8002cc34e5d010ee49d761da4
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45706697"
---
# <a name="running-nmake"></a>Запуск программы NMAKE

## <a name="syntax"></a>Синтаксис

> **NMAKE** [*параметр* ...] [*макросы* ...] [*целевых объектов* ...] [**\@**<em>commandfile</em> ...]

## <a name="remarks"></a>Примечания

Только указанные сборки NMAKE *целевых объектов* или, если он не задан, первый для целевых платформ в файле makefile. Первый целевой объект файла makefile может быть [псевдоцелью](../build/pseudotargets.md) , создающим другие целевые объекты. Программа NMAKE использует файлы makefile, указанный в параметре /F; Если /F не указан, используется файл Makefile в текущем каталоге. Если указан файл makefile, он использует правила вывода для построения командной строки *целевых объектов*.

*Commandfile* текстовый файл (или файл ответов) содержит входные данные командной строки. Другие входные данные могут указываться перед или после \@ *commandfile*. Путь разрешается. В *commandfile*, разрывы строк обрабатываются как пробелы. Определения макросов следует заключите в кавычки, если они содержат пробелы.

## <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения

[Параметры NMAKE](../build/nmake-options.md)

[Tools.ini и NMAKE](../build/tools-ini-and-nmake.md)

[Коды выхода из NMAKE](../build/exit-codes-from-nmake.md)

## <a name="see-also"></a>См. также

[Справочник по программе NMAKE](../build/nmake-reference.md)