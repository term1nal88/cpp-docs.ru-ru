---
title: Диагностические сообщения ассемблера ARM | Документация Майкрософт
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- A2193
- A2196
- A2202
- A2513
- A2557
- A4228
- A4508
- A4509
helpviewer_keywords:
- A2193
- A2196
- A2202
- A2513
- A2557
- A4228
- A4508
- A4509
dev_langs:
- C++
ms.assetid: 52b38267-6023-4bdc-a0ef-863362f48eec
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 765a2c842d9e3714edd3303d3536efe603bd9c2c
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43684850"
---
# <a name="arm-assembler-diagnostic-messages"></a>Диагностические сообщения ассемблера ARM

Ассемблер Microsoft ARM (*armasm*) выдает диагностики предупреждения и ошибки при их обнаружении. В этой статье приведены наиболее часто встречающиеся сообщения.

## <a name="syntax"></a>Синтаксис

> <em>Имя файла</em>**(**<em>номер строки</em>**):** \[ **ошибка**|**предупреждение** ] **Объект**<em>номер</em>**:** *сообщения*

## <a name="diagnostic-messages---errors"></a>Диагностические сообщения - ошибки

> A2193: Эта инструкция приводит к непредсказуемому поведению

Архитектура ARM не может гарантировать, что происходит при выполнении этой команды.  Дополнительные сведения о формах и четко определенные инструкции по, обратитесь к [справочное руководство по архитектуре ARM](http://go.microsoft.com/fwlink/p/?linkid=246464).

```asm
    ADD r0, r8, pc         ; A2193: this instruction generates unpredictable behavior
```

> A2196: инструкция не может быть закодирован в 16 бит

Заданную инструкцию, не может быть закодирован как инструкция по 16-разрядное бегунка.  Укажите 32-разрядных инструкций или переупорядочивать код для приведения целевой метке в диапазоне 16-разрядных инструкций.

Ассемблер может попытаться кодирование ветвь в 16 бит и со следующей ошибкой, несмотря на то, что можно было кодировать 32-разрядного ветвления. Эту проблему можно решить с помощью `.W` описатель явным образом пометить ветви с 32-разрядной архитектурой.

```asm
    ADD.N r0, r1, r2      ; A2196: instruction cannot be encoded in 16 bits

    B.W label             ; OK
    B.N label             ; A2196: instruction cannot be encoded in 16 bits
    SPACE 10000
label
```

> A2202: Синтаксис инструкции по Pre-UAL, не допускается в регионе THUMB

Код Thumb необходимо использовать синтаксис единого языка ассемблера (UAL).  Старый синтаксис не будет приниматься

```asm
    ADDEQS r0, r1         ; A2202: Pre-UAL instruction syntax not allowed in THUMB region
    ADDSEQ r0, r1         ; OK
```

> A2513: Поворот должна быть четной

В режиме ARM есть альтернативный синтаксис для указания константы.  Вместо написания `#<const>`, можно написать `#<byte>,#<rot>`, который представляет значение константы, полученное путем поворот значение `<byte>` вправо на `<rot>`.  При использовании этого синтаксиса, необходимо убедиться в значение `<rot>` даже.

```asm
    MOV r0, #4, #2       ; OK
    MOV r0, #4, #1       ; A2513: Rotation must be even
```

> A2557: Неверное число байтов для обратной записи

В структуре NEON загружать и хранить инструкции (`VLDn`, `VSTn`), есть альтернативный синтаксис для указания обратной записи к базовым регистром.  Вместо размещения восклицательный знак (!) после адреса, можно указать непосредственного значения, которое указывает на смещение, добавляемое к базовым регистром.  Если вы используете этот синтаксис, необходимо указать точное число байтов, которые были загружены или хранимой инструкцией.

```asm
    VLD1.8 {d0-d3}, [r0]!         ; OK
    VLD1.8 {d0-d3}, [r0], #32     ; OK
    VLD1.8 {d0-d3}, [r0], #100    ; A2557: Incorrect number of bytes to write back
```

## <a name="diagnostic-messages---warnings"></a>Диагностические сообщения - предупреждения

> A4228: Значение выравнивания превышает выравнивания области; выравнивание не гарантируется

Выравнивание, который указан в `ALIGN` директива больше, чем выравнивание включающего `AREA`.  В результате ассемблер не может гарантировать, что `ALIGN` директива будет учитываться.

Чтобы устранить эту проблему, можно указать на `AREA` директива `ALIGN` атрибут, который равен или больше, чем требуемое выравнивание.

```asm
AREA |.myarea1|
ALIGN 8           ; A4228: Alignment value exceeds AREA alignment; alignment not guaranteed

AREA |.myarea2|,ALIGN=3
ALIGN 8           ; OK
```

> A4508: Использование этой константы повернутый устарел

В режиме ARM есть альтернативный синтаксис для указания константы.  Вместо написания `#<const>`, можно написать `#<byte>,#<rot>`, который представляет значение константы, полученное путем поворот значение `<byte>` вправо на `<rot>`.  В некоторых контекстах ARM устаревшим использование этих повернутый констант. В этом случае использовать базовые `#<const>` синтаксис вместо этого.

```asm
    ANDS r0, r0, #1                ; OK
    ANDS r0, r0, #4, #2            ; A4508: Use of this rotated constant is deprecated
```

> A4509: Эта форма условной инструкции является устаревшим

Эта форма условной инструкции с ARM в архитектуре ARMv8 является устаревшим. Рекомендуется изменить код, чтобы использовать условные ветви. Чтобы увидеть, какие условной инструкции по-прежнему поддерживаются, обратитесь к [справочное руководство по архитектуре ARM](http://go.microsoft.com/fwlink/p/?linkid=246464).

Это предупреждение не создается при **- oldit** использовать параметр командной строки.

```asm
    ADDEQ r0, r1, r8              ; A4509: This form of conditional instruction is deprecated
```

## <a name="see-also"></a>См. также

[Справочник по командной строке ассемблера ARM](../../assembler/arm/arm-assembler-command-line-reference.md)<br/>
[Директивы ассемблера ARM](../../assembler/arm/arm-assembler-directives.md)<br/>
