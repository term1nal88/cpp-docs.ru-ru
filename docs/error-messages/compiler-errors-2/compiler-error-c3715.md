---
title: Ошибка компилятора C3715 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3715
dev_langs:
- C++
helpviewer_keywords:
- C3715
ms.assetid: ee5dce88-ddc4-4bdb-9464-47467ce1674f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 63ae3486b4db21a3aa241d5ebdbbfa0cdc6806f2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46026560"
---
# <a name="compiler-error-c3715"></a>Ошибка компилятора C3715

«указатель»: должен быть указателем на «class»

Задан указатель в [__hook](../../cpp/hook.md) или [__unhook](../../cpp/unhook.md) , не указывающий на допустимый класс. Чтобы устранить эту ошибку, убедитесь, что ваш `__hook` и `__unhook` вызовы задают указатели на допустимых классов.