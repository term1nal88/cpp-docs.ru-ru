---
title: Поддержка Юникода | Документация Майкрософт
ms.custom: ''
ms.date: 1/09/2018
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- globalization [C++], character sets
- portable data types [MFC]
- Unicode [C++]
- wide characters [C++], about wide characters
- character sets [C++], Unicode
- localization [C++], character sets
- Unicode [C++], installing support
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a4ed04c30eb71086f57cc9a782c320c06a301485
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46405038"
---
# <a name="support-for-unicode"></a>Поддержка Юникода

Юникод является стандартом, поддерживающим все кодировки, включая те, которые не могут быть представлены в длиной в один байт (т. е. Большинство из них). Если при написании программ для международного рынка, мы рекомендуем использовать либо Юникода или [многобайтовая кодировка](../text/support-for-multibyte-character-sets-mbcss.md) (MBCS), или код программы, поэтому вы можете создавать, указывая параметр.

Расширенный символ — это двухбайтовый многоязыковой код символа. Десятки тысяч символов, включающего в себя практически все символы, используемые в современных вычислительных системах по всему миру, включая технические символы и специальные символы публикации, могут быть представлены в соответствии со стандартом Юникода в виде одного расширенных символов, кодируемые командлетом с помощью UTF-16. Символы, которые не могут быть представлены как один расширенный символ могут быть представлены в пары Юникода с помощью суррогатная пара. Так как почти каждый символ, широко используемые представлен в кодировке UTF-16 в расширенный символ один 16 бит, их использование упрощает программирование с использованием международных кодировок. Расширенные символы в кодировке UTF-16LE (для прямой порядок байтов) являются собственного символьного формата для Windows.

Строка расширенных символов представляется как массив `wchar_t[]`, и на нее указывает указатель `wchar_t*`. Любой символ ASCII может быть представлен как расширенный символ путем добавления к нему префикса "L". Например L '\0' является завершающий нуль-символ во всей (16-разрядная версия). Подобным образом все строковые литералы, составленные из символов ASCII, могут быть представлены как строковые литералы из расширенных символов путем добавления к литералу ASCII префикса "L" (L"Hello").

Как правило, расширенные символы занимают больше памяти, чем многобайтовые символы, однако они обрабатываются быстрее. Кроме того только один языковой стандарт можно представить в многобайтовом кодировании одновременно, тогда как в мире все кодировки, представляются одновременно Юникод-представление.

Поддержка Юникода обеспечивается для всех компонентов платформы MFC. MFC обеспечивает поддержку Юникода с помощью переносимых макросов, как показано в следующей таблице.

## <a name="portable-data-types-in-mfc"></a>Типы переносимых данных в MFC

|Непереносимый тип данных|Макрос, которым он заменяется|
|-----------------------------|----------------------------|
|`char`, `wchar_t`|`_TCHAR`|
|`char*`, `LPSTR` (Тип данных Win32), `LPWSTR`|`LPTSTR`|
|`const char*`, `LPCSTR` (Тип данных Win32), `LPCWSTR`|`LPCTSTR`|

Класс `CString` использует `_TCHAR` качестве базового и предоставляет конструкторы и операторы, которые упрощают процесс преобразования. Большинство операций со строками Юникода может быть написано с помощью средств, которые используются для обработки кодировки Windows ANSI. Единственным отличием является то, что основной единицей операции является шестнадцатибитный символ, а не восьмибитный. В отличие от многобайтовых кодировок нет необходимости (и не следует) обрабатывать символы Юникода как два отдельных байта. Тем не менее, нужно иметь дело с возможностью один символ, представленный суррогатную пару расширенных символов. В общем случае не писать код, который предполагается, что длина строки является таким же, как количество символов, ли узкой или расширенной, что он содержит.

## <a name="what-do-you-want-to-do"></a>Выберите действие

- [Использовать MFC Юникода и многобайтовой кодировки (MBCS) поддержки](../atl-mfc-shared/unicode-and-multibyte-character-set-mbcs-support.md)

- [Использование Юникода в программе](../text/international-enabling.md)

- [Использование Юникода и многобайтовых Кодировок в программе](../text/internationalization-strategies.md)

- [Использование Юникода для создания многоязыковых программ](../text/unicode-programming-summary.md)

- [Узнайте о преимуществах Юникода](../text/benefits-of-character-set-portability.md)

- [Использование wmain для передачи аргументов в программу](../text/support-for-using-wmain.md)

- [Просмотреть сводку программировании Юникода](../text/unicode-programming-summary.md)

- [Дополнительные сведения об универсальных текстовых сопоставлений для обеспечения переносимости байтовый](../text/generic-text-mappings-in-tchar-h.md)

## <a name="see-also"></a>См. также

[Текст и строки](../text/text-and-strings-in-visual-cpp.md)<br/>
[Поддержка использования wmain](../text/support-for-using-wmain.md)