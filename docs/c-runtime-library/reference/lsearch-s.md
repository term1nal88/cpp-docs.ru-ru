---
title: _lsearch_s | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _lsearch_s
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
- api-ms-win-crt-utility-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _lsearch_s
- lsearch_s
dev_langs:
- C++
helpviewer_keywords:
- linear searching
- values, searching for
- keys, finding in arrays
- arrays [CRT], searching
- searching, linear
- _lsearch_s function
- lsearch_s function
ms.assetid: d2db0635-be7a-4799-8660-255f14450882
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 12315350b62673abb0a838f9d30830354c58da73
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32404202"
---
# <a name="lsearchs"></a>_lsearch_s

Выполняет линейный поиск значения. Версия функции [_lsearch](lsearch.md) с усовершенствованиями системы безопасности, описанными в разделе [Функции безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Синтаксис

```C
void *_lsearch_s(
   const void *key,
   void *base,
   unsigned int *num,
   size_t size,
   int (__cdecl *compare)(void *, const void *, const void *),
   void * context
);
```

### <a name="parameters"></a>Параметры

*key*<br/>
Искомый объект.

*base*<br/>
Указатель на начало массива, где будет производиться поиск.

*Номер*<br/>
Число элементов.

*size*<br/>
Размер каждого элемента в байтах.

*compare*<br/>
Указатель на подпрограмму сравнения. Второй параметр — это указатель на ключ для поиска. Третий параметр — это указатель на элемент массива, который будет сравниваться с ключом.

*Контекст*<br/>
Указатель на объект, доступ к которому может получить функция сравнения.

## <a name="return-value"></a>Возвращаемое значение

Если *ключ* найден, **_lsearch_s** возвращает указатель на элемент массива в *базового* , соответствующий *ключ*. Если *ключ* не найден, **_lsearch_s** возвращает указатель на вновь добавленный элемент в конец массива.

Если функции переданы недопустимые параметры, вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, **errno** равно **EINVAL** и функция возвращает **NULL**. Дополнительные сведения см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

### <a name="error-conditions"></a>Условия ошибок

|*key*|*base*|*compare*|*Номер*|*size*|**errno**|
|-----------|------------|---------------|-----------|------------|-------------|
|**NULL**|any|any|any|any|**EINVAL**|
|any|**NULL**|any|!= 0|any|**EINVAL**|
|any|any|any|any|нуль|**EINVAL**|
|any|any|**NULL**|любой|any|**EINVAL**|

## <a name="remarks"></a>Примечания

**_Lsearch_s** функция выполняет линейный поиск значения *ключ* массива *номер* элементов, каждый из *ширина* байт. В отличие от **bsearch_s**, **_lsearch_s** не требуется, чтобы массив был отсортирован. Если *ключ* не найден, затем **_lsearch_s** добавляет его в конец массива и увеличивает *номер*.

*Сравнения* функции — указатель на предоставляемую пользователем подпрограмму, которая сравнивает два элемента массива и возвращает значение, указывающее, их связь. *Сравнения* функция также принимает указатель на контекст в качестве первого аргумента. **_lsearch_s** вызовы *сравнения* один или несколько раз во время поиска, передавая указатели на два элемента массива при каждом вызове. *Сравнение* должна сравнивать элементы и возвращать либо ненулевое значение (то есть элементы различаются) или 0 (если элементы идентичны).

*Контекста* указатель может быть полезен, если структура которой производится поиск данных является частью объекта и *сравнения* функции требуется доступ к членам объекта. Например, код в *сравнения* функции может привести указатель void в соответствующий объект типа и доступа к членам этого объекта. Добавление *контекста* делает указатель **_lsearch_s** более надежное, поскольку дополнительного контекста может использоваться для предотвращения ошибок повторного входа, связанных с использованием статических переменных для предоставление доступа к данным *сравнения* функции.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_lsearch_s**|\<search.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Сортировка и поиск](../../c-runtime-library/searching-and-sorting.md)<br/>
[bsearch_s](bsearch-s.md)<br/>
[_lfind_s](lfind-s.md)<br/>
[_lsearch](lsearch.md)<br/>
