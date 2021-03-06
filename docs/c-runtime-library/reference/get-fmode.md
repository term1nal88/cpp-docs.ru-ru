---
title: _get_fmode | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _get_fmode
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- get_fmode
- _get_fmode
dev_langs:
- C++
helpviewer_keywords:
- _get_fmode function
- file translation [C++], default mode
- get_fmode function
ms.assetid: 22ea70e2-b9b5-422d-b514-64f4beaea45c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a28909e5e848712305fb28e8ac4d46180f8948cf
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32398306"
---
# <a name="getfmode"></a>_get_fmode

Получает режим преобразования файла по умолчанию для операций файлового ввода-вывода.

## <a name="syntax"></a>Синтаксис

```C
errno_t _get_fmode( 
   int * pmode 
);
```

### <a name="parameters"></a>Параметры

*pmode*<br/>
Указатель на целое число для заполнения текущий режим по умолчанию: **_O_TEXT** или **_O_BINARY**.

## <a name="return-value"></a>Возвращаемое значение

Возвращает нуль в случае успеха или код ошибки в случае ошибки. Если *pmode* — **NULL**, вызывается обработчик недопустимого параметра, как описано в [проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, **errno** равно **EINVAL** и функция возвращает **EINVAL**.

## <a name="remarks"></a>Примечания

Функция возвращает значение [_fmode](../../c-runtime-library/fmode.md) глобальной переменной. Эта переменная определяет режим преобразования файла по умолчанию для обоих низкого уровня и поток операций файлового ввода-вывода, таких как **_open**, **_pipe**, **fopen**, и [ freopen](freopen-wfreopen.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|Необязательный заголовок|
|-------------|---------------------|---------------------|
|**_get_fmode**|\<stdlib.h>|\<fcntl.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

См. пример в разделе [_set_fmode](set-fmode.md).

## <a name="see-also"></a>См. также

[_fmode](../../c-runtime-library/fmode.md)<br/>
[_set_fmode](set-fmode.md)<br/>
[_setmode](setmode.md)<br/>
[Файловый ввод-вывод в текстовом и двоичном режиме](../../c-runtime-library/text-and-binary-mode-file-i-o.md)<br/>
