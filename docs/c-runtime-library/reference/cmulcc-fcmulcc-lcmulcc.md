---
title: _Cmulcc _FCmulcc, _LCmulcc | Документы Microsoft
ms.custom: ''
ms.date: 03/30/2018
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
apiname:
- _Cmulcc
- _FCmulcc
- _LCmulcc
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
- api-ms-win-crt-math-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _Cmulcc
- _FCmulcc
- _LCmulcc
- complex/_Cmulcc
- complex/_FCmulcc
- complex/_LCmulcc
dev_langs:
- C++
helpviewer_keywords:
- _Cmulcc function
- _FCmulcc function
- _LCmulcc function
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f1c4290c7e1f7a1ec917f2b2a197f787d28b9cd9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32394988"
---
# <a name="cmulcc-fcmulcc-lcmulcc"></a>_Cmulcc _FCmulcc, _LCmulcc

Умножает два комплексных числа.

## <a name="syntax"></a>Синтаксис

```C
_Dcomplex _Cmulcc( _Dcomplex x, _Dcomplex y );
_Fcomplex _FCmulcc( _Fcomplex x, _Fcomplex y );
_Lcomplex _LCmulcc( _Lcomplex x, _Lcomplex y );
```

### <a name="parameters"></a>Параметры

*x*<br/>
Один из операндов сложный для умножения.

*y*<br/>
Другие сложные операнд для умножения.

## <a name="return-value"></a>Возвращаемое значение

Объект **_Dcomplex**, **_Fcomplex**, или **_Lcomplex** структуру, которая представляет сложный продукт комплексных чисел *x* и *y*.

## <a name="remarks"></a>Примечания

Так как встроенные арифметические операторы работают в реализации корпорацией Майкрософт, сложные типы **_Cmulcc**, **_FCmulcc**, и **_LCmulcc** функции Упростите умножения сложных типов.

## <a name="requirements"></a>Требования

|Подпрограмма|Заголовок C|Заголовок C++|
|-------------|--------------|------------------|
|**_Cmulcc**, **_FCmulcc**, **_LCmulcc**|\<complex.h>|\<complex.h>|

Эти функции зависят от корпорации Майкрософт. Типы **_Dcomplex**, **_Fcomplex**, и **_Lcomplex** , характерные для Майкрософт эквиваленты нереализованные C99 собственные типы **двойные _Complex** , **float _Complex**, и **long double _Complex**соответственно. Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Алфавитный указатель функций](crt-alphabetical-function-reference.md)<br/>
[_Cbuild, _FCbuild, _LCbuild](cbuild-fcbuild-lcbuild.md)<br/>
[_Cmulcr, _FCmulcr, _LCmulcr](cmulcr-fcmulcr-lcmulcr.md)<br/>
[norm, normf, norml](norm-normf-norml1.md)<br/>
[cproj, cprojf, cprojl](cproj-cprojf-cprojl.md)<br/>
[conj, conjf, conjl](conj-conjf-conjl.md)<br/>
[creal, crealf, creall](creal-crealf-creall.md)<br/>
[cimag, cimagf, cimagl](cimag-cimagf-cimagl.md)<br/>
[carg, cargf, cargl](carg-cargf-cargl.md)<br/>
[cabs, cabsf, cabsl](cabs-cabsf-cabsl.md)<br/>
