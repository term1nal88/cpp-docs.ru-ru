---
title: Функции &lt;forward_list&gt; | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- forward_list/std::swap
ms.assetid: 0d6bc656-7049-4651-a4bd-c9a805e47756
ms.openlocfilehash: 097dca5d26014696e218ff6439b81e1d0349b2c5
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2018
ms.locfileid: "38966323"
---
# <a name="ltforwardlistgt-functions"></a>Функции &lt;forward_list&gt;

||
|-|
|[swap](#swap)|

## <a name="swap"></a>  swap

Меняет местами элементы двух прямых списков.

```cpp
void swap(
    forward_list <Type, Allocator>& left,
    forward_list <Type, Allocator>& right);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание:|
|---------------|-----------------|
|*left*|Объект типа `forward_list`.|
|*right*|Объект типа `forward_list`.|

### <a name="remarks"></a>Примечания

Шаблонная функция выполняет `left.swap(right)`.

## <a name="see-also"></a>См. также

[<forward_list>](../standard-library/forward-list.md)<br/>
