---
title: Строка, управление данными | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- Unicode, string objects
ms.assetid: 0b53a542-eeb1-4108-9ada-6700645b6f8f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d6b54bfbf614ca7e3d1c34c4924c545c5f46ed4e
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43763725"
---
# <a name="string-data-management"></a>Управление строковыми данными

Visual C++ предоставляет несколько способов управления строковыми данными.

- [Манипуляции со строками](../c-runtime-library/string-manipulation-crt.md) для работы со строками нулевым байтом в стиле C

- Функции Win32 API для управления строками

- Класс MFC [класс CStringT](../atl-mfc-shared/reference/cstringt-class.md), который предоставляет гибкий, размер которой можно изменять строковых объектов

- Класс [класс CStringT](../atl-mfc-shared/reference/cstringt-class.md), который предоставляет объект строка независимый от MFC с ту же функциональность, что `CString`

Практически все программы работы со строковыми данными. MFC `CString` класс часто является лучшим решением для обработки гибкие строк. Начиная с версии 7.0, `CString` может использоваться в программы MFC или независимый от MFC. Библиотеки времени выполнения и `CString` поддержки строк, содержащих многобайтовая кодировка (расширенный), как и в программировании Юникода и MBCS.

В этой статье описаны общего назначения службы, библиотека классов предоставляет связанные с строками. В этой статье рассматриваются:

- [Юникод и MBCS предоставляют переносимости](#_core_unicode_and_mbcs_provide_portability)

- [CStrings и указатели const char](#_core_cstrings_and_const_char_pointers)

- [Подсчет ссылок CString](#_core_cstring_reference_counting)

[Класс CStringT](../atl-mfc-shared/reference/cstringt-class.md) класс обеспечивает поддержку операции со строками. Он предназначен для замены и расширения функциональности, обычно предоставляемые пакетом строка библиотеки времени выполнения C. `CString` Класс предоставляет функции-члены и операторы для обработки упрощенный строки, аналогичные используемым в Basic. Класс также предоставляет конструкторы и операторы для конструирования, назначение и сравнение `CString`s и standard C++ строковые типы данных. Так как `CString` не является производным от `CObject`, можно использовать `CString` объектов независимо от большинства из Microsoft Foundation Class Library (MFC).

`CString` объекты следуют «value семантики.» Объект `CString` представляет уникальное значение. Можно рассматривать `CString` виде фактические строки, а не как указатель на строку.

Объект `CString` объект представляет собой последовательность из переменное число символов. `CString` объекты могут рассматриваться как массивы символов.

##  <a name="_core_unicode_and_mbcs_provide_portability"></a> Юникод и многобайтовая Кодировка предоставляют переносимости

С MFC версии 3.0 и более поздних, MFC, включая `CString`, предусмотрена поддержка Юникода и многобайтовой кодировки (MBCS). Эта поддержка упрощает написание переносимые приложения, что можно создать для символов Юникода или ANSI. Для включения этой мобильности каждый символ в `CString` объект имеет тип TCHAR, который определен как `wchar_t` Если определяется _UNICODE символ при построении приложения или как `char` в противном случае. Объект `wchar_t` символ имеет размер 16 бит. MBCS включена, при построении с _MBCS символов, которые определены. Классами MFC построен с использованием символа _MBCS (для библиотек NAFX) или определяется _UNICODE символ (для библиотек UAFX).

> [!NOTE]
>  `CString` Примерах в этом и сопутствующие статей на строки правильный формат для переносимости с помощью макрос _T, который преобразует строковые литералы Юникода строковых литералов:

`L"literal string"`

> [!NOTE]
>  который компилятор обрабатывает как строка Юникода. Например, приведенный ниже код

[!code-cpp[NVC_ATLMFC_Utilities#187](../atl-mfc-shared/codesnippet/cpp/string-data-management_1.cpp)]

> [!NOTE]
>  переводится как строка Юникода, если определяется _UNICODE, так и в строку ANSI, если это не так. Дополнительные сведения см. в статье [многобайтовых кодировку (MBCS) поддержка Юникода и](../atl-mfc-shared/unicode-and-multibyte-character-set-mbcs-support.md).

Объект `CString` объект может хранить до INT_MAX (2 147 483 647) символов. Тип данных TCHAR используется для получения или задания отдельных символов внутри `CString` объекта. В отличие от массивов знаков `CString` класс имеет возможность распределения встроенной памяти. Это позволяет `CString` объектов автоматически увеличиваться по мере необходимости (то есть не нужно беспокоиться о растет `CString` объекта в соответствии с более длинные строки).

##  <a name="_core_cstrings_and_const_char_pointers"></a> CStrings и указатели const char

Объект `CString` объект также может действовать как строковый литерал стиля C ( `PCXSTR`, который является таким же, как **const char** <strong>\*</strong> if не в Юникоде). [CSimpleStringT::operator PCXSTR](../atl-mfc-shared/reference/csimplestringt-class.md#operator_pcxstr) оператор преобразования позволяет `CString` объектов должен быть замещен свободно указателей символов в вызовах функций. **CString (LPCWSTR** `pszSrc` **)** конструктор позволяет указателей символов должен быть замещен `CString` объектов.

Попытки не сверток `CString` объектов. Если два `CString` объектов содержащий `Chicago`, например символы в `Chicago` хранятся в двух местах. (Это может оказаться true будущих версий MFC, поэтому не следует полагаться на него.)

> [!NOTE]
>  Используйте [CSimpleStringT::GetBuffer](../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer) и [CSimpleStringT::ReleaseBuffer](../atl-mfc-shared/reference/csimplestringt-class.md#releasebuffer) для функций-членов для прямого доступа к `CString` как неконстантный указатель на символ.

> [!NOTE]
>  Используйте [CStringT::AllocSysString](../atl-mfc-shared/reference/cstringt-class.md#allocsysstring) и [CStringT::SetSysString](../atl-mfc-shared/reference/cstringt-class.md#setsysstring) функции-члены для выделения и задания объектов BSTR, используемых в автоматизация (ранее известная как OLE-автоматизация).

> [!NOTE]
>  Где это возможно, следует выделить `CString` объекты в кадре, а не в куче. Это экономит память и упрощает передачи параметров.

`CString` Класс не реализуется как класс коллекции библиотеки классов Microsoft Foundation, хотя `CString` объектов определенно могут храниться как элементы в коллекции.

##  <a name="_core_cstring_reference_counting"></a> Подсчет ссылок CString

Начиная с версии 4.0, MFC при [класс CStringT](../atl-mfc-shared/reference/cstringt-class.md) копируются объекты, MFC увеличивает счетчик ссылок, а не копировать данные. Это делает передача параметров по значению и возвращение `CString` объекты по значению более эффективным. Эти операции вызывают конструктор копии для вызова, иногда несколько раз. Приращение счетчика ссылок снизить эту нагрузку для этих стандартных операций и с помощью `CString` более привлекательным вариантом.

Так как каждая копия вышел из строя, счетчик ссылок в исходном объекте, уменьшается. Исходный `CString` объекта не уничтожается, пока ее счетчику ссылок уменьшается до нуля.

Можно использовать `CString` функции-члены [CSimpleStringT::LockBuffer](../atl-mfc-shared/reference/csimplestringt-class.md#lockbuffer) и [CSimpleStringT::UnlockBuffer](../atl-mfc-shared/reference/csimplestringt-class.md#unlockbuffer) для отключения или включения подсчета ссылок.

## <a name="see-also"></a>См. также

[Общие разделы по MFC](../mfc/general-mfc-topics.md)

