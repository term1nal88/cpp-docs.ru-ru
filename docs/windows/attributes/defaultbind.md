---
title: defaultbind (атрибут COM C++) | Документация Майкрософт
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.defaultbind
dev_langs:
- C++
helpviewer_keywords:
- defaultbind attribute
ms.assetid: b20a8437-24e6-4b6d-a2df-09fe5e1006e0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 89fb592a29fec5198ee96b25319e194eeaffa91f
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50063605"
---
# <a name="defaultbind"></a>defaultbind

Указывает единственное свойство, представляющим объект наилучшим образом.

## <a name="syntax"></a>Синтаксис

```cpp
[defaultbind]
```

## <a name="remarks"></a>Примечания

**Defaultbind** атрибут C++ имеет ту же функциональность, что [defaultbind](/windows/desktop/Midl/defaultbind) описании атрибута MIDL.

## <a name="example"></a>Пример

См. в примере [bindable](bindable.md) пример демонстрирует использование **defaultbind**.

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|Метод интерфейса|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Нет|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты метода](method-attributes.md)<br/>
[Атрибуты элементов данных](data-member-attributes.md)<br/>
[displaybind](displaybind.md)<br/>
[immediatebind](immediatebind.md)<br/>
[requestedit](requestedit.md)