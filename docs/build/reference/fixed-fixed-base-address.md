---
title: — Фиксированный (фиксированный базовый адрес) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /fixed
- VC.Project.VCLinkerTool.FixedBaseAddress
dev_langs:
- C++
helpviewer_keywords:
- preferred base address for loading program
- /FIXED linker option
- -FIXED linker option
- FIXED linker option
ms.assetid: 929bba5e-b7d8-40ed-943e-056aa3710fc5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 697f6ccfd98059175311cd04e4e82038877b2110
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45723402"
---
# <a name="fixed-fixed-base-address"></a>/FIXED (фиксированный базовый адрес)

```
/FIXED[:NO]
```

## <a name="remarks"></a>Примечания

Указывает операционной системе загружать программу только по ее предпочтительному базовому адресу. Если предпочтительный базовый адрес недоступен, операционная система не загружается файл. Дополнительные сведения см. в разделе [Параметр /Base (базовый адрес)](../../build/reference/base-base-address.md).

Компоновщике значение по умолчанию для библиотеки DLL, а параметр/FIXED — по умолчанию для любого другого типа проекта.

Если указан параметр/fixed, LINK не создает в программе секцию перемещения. Во время выполнения Если операционная система не может загрузить программу по указанному адресу, он выводит сообщение об ошибке и программа не загружается.

Укажите компоновщике для создания в программе секцию перемещения.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [Работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Выберите **компоновщика** папки.

1. Выберите **командной строки** страницу свойств.

1. Введите имя параметра и задав в **Дополнительные параметры** поле.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также

[Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)<br/>
[Параметры компоновщика](../../build/reference/linker-options.md)