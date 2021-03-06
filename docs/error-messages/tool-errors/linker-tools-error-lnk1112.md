---
title: Ошибка средств компоновщика LNK1112 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1112
dev_langs:
- C++
helpviewer_keywords:
- LNK1112
ms.assetid: 425793d8-37e6-4072-9b6e-c3d4e9c12562
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e08e8dae82675d9503575d543edfcaa2c96275e9
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2018
ms.locfileid: "42539702"
---
# <a name="linker-tools-error-lnk1112"></a>Ошибка средств компоновщика LNK1112

> Тип компьютера модуля "*тип1*«противоречит типу целевого компьютера»*тип2*"

## <a name="remarks"></a>Примечания

Объектные файлы, указанные как входные, скомпилированы для разных типов компьютеров.

Например, при попытке связать объектный файл, скомпилированный с помощью **/clr** , и объектный файл, скомпилированный с помощью **/clr:pure** (тип компьютера CEE), компоновщик создаст ошибку LNK1112. **/CLR: pure** параметр компилятора в Visual Studio 2015 не рекомендуется и не поддерживается в Visual Studio 2017.

Аналогично Если создать один модуль с x64 компилятора и другой модуль с помощью x86 компилятор и попытаться связать их, компоновщик создаст ошибку LNK1112.

Возможные причины этой ошибки: при разработке 64-разрядного приложения не установлен один из 64-разрядных компиляторов Visual C++. В этом случае 64-разрядные конфигурации будут недоступны. Чтобы устранить эту проблему, запустите установщик для Visual Studio и установите недостающие компоненты C++.

Эта ошибка также может возникать при изменении **активной конфигурации решения** в **диспетчере конфигураций** и последующей попытке построения проекта до удаления промежуточных файлов проекта. Чтобы устранить эту ошибку, выберите в меню **Сборка** пункт **Перестроить решение** . Можно также выбрать в меню **Сборка** пункт **Очистить решение** , а затем выполнить сборку решения.

## <a name="see-also"></a>См. также

- [Ошибки и предупреждения средств компоновщика](../../error-messages/tool-errors/linker-tools-errors-and-warnings.md)
