---
title: Предупреждение компилятора (уровни 2 и 3) C4008 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4008
dev_langs:
- C++
helpviewer_keywords:
- C4008
ms.assetid: fb45e535-cb68-4743-80e9-a6e34cfffeca
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bd052b8dd6a0b70dd90ca076d0085675b33dc621
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46091183"
---
# <a name="compiler-warning-levels-2-and-3-c4008"></a>Предупреждение компилятора (уровни 2 и 3) C4008

"идентификатор": атрибут "атрибут" игнорируется

Компилятор игнорировал атрибут `__fastcall`, **static**или **inline** для функции (предупреждение уровня 3) или данных (предупреждение уровня 2).

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Чтобы устранить ошибку, проверьте указанные ниже возможные причины ее возникновения.

1. Атрибут`__fastcall` с данными.

1. Атрибут**static** или **inline** с функцией **main** .