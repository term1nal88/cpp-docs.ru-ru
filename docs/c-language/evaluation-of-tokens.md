---
title: Оценка лексем | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- tokens, evaluating
ms.assetid: 28870b62-dff6-4644-8b75-d58f340b48d2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5d5c79ac043b2131df7a876f2de63922c45c9ead
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46035283"
---
# <a name="evaluation-of-tokens"></a>Оценка токенов

Когда компилятор интерпретирует токены, он включает в один токен максимально возможное количество символов, а затем переходит к следующему. Поэтому если токены не разделены пробельными символами, они могут интерпретироваться не так, как ожидается. Рассмотрим следующее выражение:

```
i+++j
```

В этом примере компилятор сначала извлекает максимально возможный оператор (`++`) из последовательности знаков "плюс", а затем обрабатывает последний знак "плюс" как оператор сложения (`+`). Таким образом, выражение интерпретируется как `(i++) + (j)`, а не как `(i) + (++j)`. Для того чтобы предотвратить неоднозначность и гарантировать правильное вычисление выражений, в подобных случаях рекомендуется использовать пробелы и скобки.

**Блок, относящийся только к системам Microsoft**

Компилятор C обрабатывает символ CTRL+Z как индикатор конца файла. Весь текст, расположенный после символа CTRL+Z, игнорируется.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Токены C](../c-language/c-tokens.md)