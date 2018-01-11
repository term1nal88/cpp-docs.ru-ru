---
title: "Ограничения для значений символов | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.editors.symbol.restrictions.value
dev_langs: C++
helpviewer_keywords:
- symbols, value restrictions
- restrictions, symbol values
ms.assetid: 32467ec3-690b-4cd0-a4d0-7d189a3296cb
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5f2188d6904274fabce0f8626fa2f440ac324ff5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="symbol-value-restrictions"></a>Ограничения для символьных значений
Значением символа может быть любое целое число, указанное в обычном для директив препроцессора #define формате. Ниже приведены примеры значений символов.  
  
```  
18  
4001  
0x0012  
-3456  
```  
  
 Значения символов для ресурсов (сочетаний клавиш, растровых изображений, курсоров, диалоговых окон, значков, меню, таблиц строк и сведений о версии) должны быть десятичными числами в диапазоне от 0 до 32 767 (шестнадцатеричные числа не допускаются). Значения символов для частей ресурсов (элементов управления диалоговых окон или отдельных строк в таблице строк) могут быть в диапазоне от 0 до 65 534 или в диапазоне от –32 768 до 32 767.  
  
 Символы ресурсов являются 16-разрядными числами. Их можно вводить как со знаком, так и без знака, однако внутри системы они используются как целые числа без знака. Поэтому отрицательные числа будут приведены к соответствующим положительным значениям.  
  
 Ниже приведены некоторые ограничения значений символов.  
  
-   Среда разработки Visual Studio и MFC используют определенные диапазоны чисел для специальных целей. Все числа с установленным старшим разрядом (от –32 768 до –1 или от 32 768 до 65 534 в зависимости от знака) зарезервированы MFC.  
  
-   Нельзя определить значение символа, используя другие строки символов. Например, не поддерживается следующее определение символа:  
  
    ```  
    #define IDC_MYEDIT  IDC_OTHEREDIT  //not supported  
    ```  
  
-   В качестве определений значений нельзя использовать макросы препроцессора с аргументами. Пример:  
  
    ```  
    #define   IDD_ABOUT  ID(7) //not supported  
    ```  
  
     не является допустимым выражением независимо от того, какое `ID` принимает значение во время компиляции.  
  
-   У приложения может быть существующий файл, содержащий символы, определенные с помощью выражений. Дополнительные сведения о включении символов как символов только для чтения см. в разделе [использование общих (только для чтения) или вычисляемых символов](../windows/including-shared-read-only-or-calculated-symbols.md).  
  
 Дополнительные сведения о диапазонах чисел см. в разделе [TN023: стандартные ресурсы MFC](../mfc/tn023-standard-mfc-resources.md).  
  

  
## <a name="requirements"></a>Требования  
 Win32  
  
## <a name="see-also"></a>См. также  
 [Изменение числового значения символа](../windows/changing-a-symbol-s-numeric-value.md)   
 [Ограничения для имен символов](../windows/symbol-name-restrictions.md)   
 [Стандартные идентификаторы символов](../windows/predefined-symbol-ids.md)