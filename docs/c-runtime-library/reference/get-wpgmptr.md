---
title: _get_wpgmptr | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _get_wpgmptr
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- get_wpgmptr
- _get_wpgmptr
dev_langs:
- C++
helpviewer_keywords:
- _wpgmptr global variable
- get_wpgmptr function
- wpgmptr global variable
- _get_wpgmptr function
ms.assetid: a77cdd13-2303-4b7c-9a60-8debdbef2011
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9393351174477a4da43d0b3bd49e107430e68ece
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32398774"
---
# <a name="getwpgmptr"></a>_get_wpgmptr

Возвращает текущее значение **_wpgmptr** глобальной переменной.

## <a name="syntax"></a>Синтаксис

```C
errno_t _get_wpgmptr( 
   wchar_t **pValue 
);
```

### <a name="parameters"></a>Параметры

*pValue*<br/>
Указатель на строку для заполнения текущее значение **_wpgmptr** переменной.

## <a name="return-value"></a>Возвращаемое значение

Возвращает нуль в случае успеха или код ошибки в случае ошибки. Если *pValue* — **NULL**, вызывается обработчик недопустимого параметра, как описано в [проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эта функция задает **errno** для **EINVAL** и возвращает **EINVAL**.

## <a name="remarks"></a>Примечания

Вызывать только **_get_wpgmptr** Если программа содержит точку входа в Интернете, таких как **wmain()** или **wWinMain()**. **_Wpgmptr** глобальная переменная содержит полный путь к исполняемому файлу, связанному с процессом, в виде строки расширенных символов. Дополнительные сведения см. в разделе [_pgmptr _wpgmptr](../../c-runtime-library/pgmptr-wpgmptr.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_get_wpgmptr**|\<stdlib.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[_get_pgmptr](get-pgmptr.md)<br/>
