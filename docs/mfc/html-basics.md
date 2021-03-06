---
title: Основы HTML | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- HTML [MFC], about HTML
ms.assetid: aab8ea9f-12d4-4bdd-a585-ac3124081a2a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dbe2c743f04e8fc8dc67947b9bd9d5560dd35182
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50052698"
---
# <a name="html-basics"></a>Основы HTML

Большинство браузеров поддерживает возможность проверки исходного кода HTML страницы, которые можно просматривать. При просмотре источника, вы увидите несколько HTML-теги (языка гипертекстовой разметки), заключенных в угловые скобки (<>), смешиваться с текстом.

Приведенные ниже использовать HTML-теги для создания простого веб-страницы. На этих шагах будет введите обычный текст в файл в блокноте, внести некоторые изменения, сохраните файл и перезагрузите страницу в браузере, чтобы увидеть изменения.

#### <a name="to-create-an-html-file"></a>Для создания HTML-файл

1. Откройте Блокнот или любого текстового редактора.

1. Из **файл** меню, выберите **New**.

1. Введите следующие строки:

```
<HTML>
<HEAD>
<TITLE>Top HTML Tags</TITLE>
</HEAD>
</HTML>
```

1. Из **файл** меню, выберите **Сохранить**и сохраните файл как c:\webpages\First.htm. Оставьте файл открытым в редакторе.

1. Перейдите в браузере, а также из **файл** меню, выберите **откройте**, или тип *file://C:/webpages/first.htm* в поле ввода URL-адрес в браузере. Вы должны увидеть пустую страницу с заголовок окна «Top HTML Tags».

   Обратите внимание, что теги являются парными и включаются в угловые скобки. Теги не учитывают регистр, но регистр часто используется для выполнения выделиться теги.

   Тег \<HTML > запускает документ и тега \<парными > завершает его. Завершение тегов (требуется не всегда) являются так же, как начальный тег, но также имеют косой черты (/) перед тегом. Должно быть пробелов между угловой скобки (<) и начало тега.

1. Перейдите обратно в блокноте, а также после  \< /HEAD > Строка, введите:

```
<BODY>
    HTML is swell.
    Life is good.
</BODY>
```

1. Из **файл** меню, выберите **Сохранить**.

1. Вернитесь в браузер и обновите страницу.

   Слова будут отображаться в клиентской области окна браузера. Обратите внимание на то, что возврат каретки учитывается. Если вы хотите иметь разрыв строки, необходимо включить `<BR>` тег после первой строки.

   Для всех шагов, следуйте, вставить текст в любом месте между \<текст > и  \< /BODY > для добавления в текст документа.

9. Добавление заголовка, который:

```
<H3>Here's the big picture</H3>
```

10. Добавление изображения, с помощью файла .gif, сохраненного в том же каталоге, что страницы:

```
<IMG src="yourfile.gif">
```

11. Добавление списка:

```
<UL>Make me an unordered list.
<LI>One programmer</LI>
<LI>Ten SDKs</LI>
<LI>Great Internet Apps</LI>
</UL>
```

12. Вместо этого номер списка, используйте пару \<OL > и \</OL > теги вместо \<UL > и \</UL > теги.

Что следует приступить к работе. Если вы видите отличная возможность веб-страницы, чтобы узнать как был создан с помощью проверки исходного кода HTML. Редакторы HTML, например Microsoft Front Page можно использовать для создания простых и дополнительных страниц.

Ниже приведен файл, который вы выполняли весь исходный код HTML.

```
<HTML>
<HEAD>
<TITLE>Top HTML Tags</TITLE>
</HEAD>
<BODY>
HTML is swell.<BR>
Life is good.
<H3>Here's the big picture</H3>
<IMG src="yourfile.gif">
<UL>Make me an unordered list.
<LI>One programmer</LI>
<LI>Ten SDKs</LI>
<LI>Great Internet Apps</LI>
</UL>
</BODY>
</HTML>
```

Полное описание тегов, атрибутов и расширения см. в спецификации языка (HTML):

[http://www.w3.org/pub/WWW/MarkUp/](http://www.w3.org/pub/www/markup/)

## <a name="see-also"></a>См. также

[Основы программирования для интернет-решений MFC](../mfc/mfc-internet-programming-basics.md)

