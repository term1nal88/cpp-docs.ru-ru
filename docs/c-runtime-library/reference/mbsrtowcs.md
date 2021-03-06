---
title: mbsrtowcs | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- mbsrtowcs
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
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- mbsrtowcs
dev_langs:
- C++
helpviewer_keywords:
- mbsrtowcs function
ms.assetid: f3a29de8-e36e-425b-a7fa-a258e6d7909d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ccb5bda16238888905678ffb3b6de01b93555ad0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32405436"
---
# <a name="mbsrtowcs"></a>mbsrtowcs

Преобразует строку многобайтовых символов в текущем языковом стандарте в соответствующую строку расширенных символов с возможностью перезапуска в середине многобайтового символа. Существует более безопасная версия этой функции; см. раздел [mbsrtowcs_s](mbsrtowcs-s.md).

## <a name="syntax"></a>Синтаксис

```C
size_t mbsrtowcs(
   wchar_t *wcstr,
   const char **mbstr,
   sizeof count,
   mbstate_t *mbstate
);
template <size_t size>
size_t mbsrtowcs(
   wchar_t (&wcstr)[size],
   const char **mbstr,
   sizeof count,
   mbstate_t *mbstate
); // C++ only
```

### <a name="parameters"></a>Параметры

*wcstr*<br/>
Адрес для сохранения результирующей преобразованной строки расширенных символов.

*mbstr*<br/>
Косвенный указатель на расположение преобразуемой строки многобайтовых символов.

*count*<br/>
Максимальное число символов (не байтов) для преобразования и сохранения в *wcstr*.

*mbstate*<br/>
Указатель на **mbstate_t** объект состояния преобразования. Если это значение является пустым указателем, используется статичный внутренний объект состояния преобразования. Так как внутренний **mbstate_t** объект не является потокобезопасным, мы рекомендуем всегда передавать собственный *mbstate* параметра.

## <a name="return-value"></a>Возвращаемое значение

Возвращает число успешно преобразованных символов без учета завершающего нуль-символа, если он есть. Возвращает (size_t)(-1), если произошла ошибка и задает **errno** значение EILSEQ.

## <a name="remarks"></a>Примечания

**Mbsrtowcs** функция преобразует строку многобайтовых символов, косвенно указывает *mbstr*, в расширенных символов, сохраненных в буфере, на который указывает *wcstr*, по используется состояние преобразования, содержащееся в *mbstate*. Преобразование продолжается для каждого символа до появления либо завершающий Многобайтовый нуль-символ, многобайтовая последовательность, не соответствует допустимому символу в текущем языковом стандарте встречается, до тех пор пока *число* символы были преобразованы. Если **mbsrtowcs** встречает Многобайтовый нуль-символ («\0») перед или после *число* символов, она преобразовывает его в 16-разрядный завершающий символ null и останавливается.

Таким образом, строка расширенных символов в *wcstr* завершается нуль символом только в том случае, если **mbsrtowcs** встречает Многобайтовый нуль-символ во время преобразования. Если последовательности, на который указывает *mbstr* и *wcstr* перекрываются, то поведение **mbsrtowcs** не определено. **mbsrtowcs** влияет категория LC_TYPE текущего языкового стандарта.

**Mbsrtowcs** функция отличается от [mbstowcs, _mbstowcs_l](mbstowcs-mbstowcs-l.md) возможностью перезапуска. Состояние преобразования хранится в *mbstate* для последующих вызовов тех же или других перезапускаемых функций. При смешанном использовании перезапускаемых и неперезапускаемых функций результаты становятся неопределенными.  Например, приложение должно использовать **mbsrlen** вместо **mbslen**, если в последующем вызове **mbsrtowcs** используется вместо **mbstowcs**.

Если *wcstr* не является указателем null, объект указателя, на который указывает *mbstr* присваивается указатель null, если преобразование останавливается из-за достижения завершающего нуль-символа. В противном случае ему назначается адрес позиции, следующей за последним преобразованным многобайтовым символом, если таковая имеется. Это позволяет продолжить преобразование с того же места при последующем вызове функции.

Если *wcstr* аргумент является указателем null, *число* аргумент учитывается и **mbsrtowcs** возвращает необходимый размер в расширенные символы для строки назначения. Если *mbstate* является пустым указателем, функция использует внутренний статический не многопоточное **mbstate_t** объект состояния преобразования. Если последовательность символов *mbstr* имеет соответствующие многобайтовые символьном представлении, возвращается значение -1 и **errno** равно **EILSEQ**.

Если *mbstr* вызывается является пустым указателем, обработчик недопустимого параметра, как описано в [проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эта функция задает **errno** для **EINVAL** и возвращает значение -1.

В C++ эта функция имеет шаблонную перегрузку, которая вызывает более новые и безопасные аналоги этой функции. Дополнительные сведения см. в разделе [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).

## <a name="exceptions"></a>Исключения

**Mbsrtowcs** функция является потокобезопасной, при условии, что ни одна из функций в текущем потоке вызывает **setlocale** до тех пор, пока выполняется данная функция и *mbstate* аргумент не является пустым указателем.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**mbsrtowcs**|\<wchar.h>|

## <a name="see-also"></a>См. также

[Преобразование данных](../../c-runtime-library/data-conversion.md)<br/>
[Языковой стандарт](../../c-runtime-library/locale.md)<br/>
[Интерпретация последовательностей многобайтовых символов](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[mbrtowc](mbrtowc.md)<br/>
[mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md)<br/>
[mbstowcs, _mbstowcs_l](mbstowcs-mbstowcs-l.md)<br/>
[mbsinit](mbsinit.md)<br/>
