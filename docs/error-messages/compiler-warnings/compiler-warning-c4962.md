---
title: Предупреждение компилятора C4962 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4962
dev_langs:
- C++
helpviewer_keywords:
- C4962
ms.assetid: 62b156fe-04e5-4a6e-9339-6ab148185f87
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: caff08744497936839e1021cef8fc86e0e8aa7e5
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46066262"
---
# <a name="compiler-warning-c4962"></a>Предупреждение компилятора C4962

"функция": оптимизация, зависимая от профиля, отключена, поскольку операции оптимизации приводят к несогласованности данных профиля

Функция не была скомпилирована с параметром /LTCG: PGO, так как данные count (profile) для этой функции были недостоверными. Повторите профилирование, чтобы повторно создать PGC-файл, который содержит недостоверные данные профиля для этой функции.

Это предупреждение отключено по умолчанию. Дополнительные сведения см. в разделе [Compiler Warnings That Are Off by Default](../../preprocessor/compiler-warnings-that-are-off-by-default.md).