---
title: Преобразование проектов из смешанного режима в чистый промежуточный язык | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- intermediate language, mixed-mode applications
- mixed-mode applications
- mixed-mode applications, intermediate language
- projects [C++], converting to intermediate language
ms.assetid: 855f9e3c-4f09-4bfe-8eab-a45f68292be9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 7f9cbfce7e04040f0e1618148a3c258f21bb84b8
ms.sourcegitcommit: 3a141cf07b5411d5f1fdf6cf67c4ce928cf389c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/11/2018
ms.locfileid: "49083467"
---
# <a name="converting-projects-from-mixed-mode-to-pure-intermediate-language"></a>Преобразование проектов из смешанного режима в чистый промежуточный язык

Все проекты Visual C++ CLR ссылки на библиотеки времени выполнения C по умолчанию. Следовательно эти проекты классифицируются как приложений в смешанном режиме, так как в них сочетаются машинный код с кодом, который предназначен для общеязыковой среды выполнения (управляемый код). При компиляции, они компилируются в промежуточный язык (IL), также известный как Microsoft промежуточного языка MSIL.

> [!IMPORTANT]
> Рекомендуется использовать Visual Studio 2015 и Visual Studio 2017 больше не поддерживает создание **/CLR: pure** или **/CLR: safe** код для приложения CLR. Если вам требуется чистого и безопасного сборок, рекомендуется перевести приложения на C#.

Если вы используете более раннюю версию набора инструментов компилятора Visual C++, который поддерживает **/CLR: pure** или **/CLR: safe**, эту процедуру можно использовать для преобразования кода в чистые MSIL-код:

### <a name="to-convert-your-mixed-mode-application-into-pure-intermediate-language"></a>Чтобы преобразовать приложение смешанного режима в чистый промежуточный язык

1. Удалите ссылки на [библиотек времени выполнения C](../c-runtime-library/crt-library-features.md) (CRT):

   1. В CPP-файл определения точку входа приложения, измените точку входа для `Main()`. С помощью `Main()` указывает, что проект ссылается на CRT.

   2. В обозревателе решений щелкните правой кнопкой мыши проект и выберите **свойства** в контекстном меню, чтобы открыть страницы свойств для вашего приложения.

   3. В **Дополнительно** страница свойств проекта для **компоновщика**выберите **точки входа** и введите **Main** в этом поле.

   4. Для консольных приложений в **системы** страница свойств проекта для **компоновщика**выберите **подсистемы** поле и измените его на **консоли (/ SUBSYSTEM:Console)**.

      > [!NOTE]
      > Необходимо задать это свойство для приложений Windows Forms, так как **подсистемы** полю присваивается **Windows (/ SUBSYSTEM: WINDOWS)** по умолчанию.

   5. В файле stdafx.h закомментируйте все `#include` инструкций. Например в консольных приложениях:

      ```cpp
      // #include <iostream>
      // #include <tchar.h>
      ```

       - или -

       Например в приложениях Windows Forms:

      ```cpp
      // #include <stdlib.h>
      // #include <malloc.h>
      // #include <memory.h>
      // #include <tchar.h>
      ```

   6. Для приложений Windows Forms, в Form1.cpp, закомментируйте `#include` инструкцию, которая ссылается на windows.h. Пример:

      ```cpp
      // #include <windows.h>
      ```

2. Добавьте следующий код в файле stdafx.h:

   ```cpp
   #ifndef __FLTUSED__
   #define __FLTUSED__
      extern "C" __declspec(selectany) int _fltused=1;
   #endif
   ```

3. Удалите все неуправляемые типы:

   Где это необходимо, замените неуправляемые типы ссылок на структуры из [системы](/dotnet/api/system) пространства имен. В следующей таблице перечислены распространенные управляемых типов.

   |Структура|Описание:|
   |---------------|-----------------|
   |[Boolean](/dotnet/api/system.boolean)|Представляет логическое значение.|
   |[Byte](/dotnet/api/system.byte)|Представляет 8-битовое целое число без знака.|
   |[Char](/dotnet/api/system.char)|Представляет символ Юникода.|
   |[DateTime](/dotnet/api/system.datetime.datetime.aspx)|Представляет текущее время, обычно выраженное как дата и время суток.|
   |[Decimal](/dotnet/api/system.decimal)|Представляет десятичное число.|
   |[Double](/dotnet/api/system.double)|Представляет число двойной точности с плавающей запятой.|
   |[Guid](/dotnet/api/system.guid)|Представляет глобальный уникальный идентификатор (GUID).|
   |[Int16](/dotnet/api/system.int16)|Представляет 16-разрядное целое число со знаком.|
   |[Int32](/dotnet/api/system.int32)|Представляет 32-разрядное целое число со знаком.|
   |[Int64](/dotnet/api/system.int64)|Представляет 64-разрядное целое число со знаком.|
   |[IntPtr](/dotnet/api/system.intptr)|Определяемый платформой тип, который используется для представления указателя или дескриптора.|
   |[SByte](/dotnet/api/system.byte.aspx)|Представляет 8-разрядное целое число со знаком.|
   |[Single](/dotnet/api/system.single.aspx)|Представляет число с плавающей запятой одиночной точности.|
   |[TimeSpan](/dotnet/api/system.timespan)|Представляет интервал времени.|
   |[UInt16](/dotnet/api/system.uint16)|Представляет 16-битовое целое число без знака.|
   |[UInt32](/dotnet/api/system.uint32)|Представляет 32-битовое целое число без знака.|
   |[UInt64](/dotnet/api/system.uint64)|Представляет 64-битовое целое число без знака.|
   |[UIntPtr](/dotnet/api/system.uintptr)|Определяемый платформой тип, который используется для представления указателя или дескриптора.|
   |[void](/dotnet/api/system.void)|Указывает метод, который не возвращает значений. то есть метод имеет тип возвращаемого значения void.|