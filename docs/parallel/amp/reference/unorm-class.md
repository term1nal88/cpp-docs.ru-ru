---
title: Класс unorm | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-amp
ms.topic: reference
f1_keywords:
- unorm
- AMP_SHORT_VECTORS/unorm
- AMP_SHORT_VECTORS/Concurrency::graphics::unorm Constructor
dev_langs:
- C++
ms.assetid: bc30bd20-6452-4d5f-9158-3b11c4c16ed2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 131a928c5943ab9bf4dcc327b044d76e5646ede7
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46377387"
---
# <a name="unorm-class"></a>Класс unorm

Представляет число unorm. Каждый элемент — это число с плавающей запятой в диапазоне [0, 0f, 1.0f].

## <a name="syntax"></a>Синтаксис

```
class unorm;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Конструктор unorm](#ctor)|Перегружен. Конструктор по умолчанию. Инициализируйте 0, 0f.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|unorm::operator--||
|unorm::operator число с плавающей запятой|Оператор преобразования. Преобразуйте unorm число с плавающей запятой.|
|unorm::operator * =||
|unorm::operator / =||
|unorm::operator ++||
|unorm::operator +=||
|unorm::operator =||
|unorm::operator-=||

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`unorm`

## <a name="requirements"></a>Требования

**Заголовок:** amp_short_vectors.h

**Пространство имен:** Concurrency::graphics

##  <a name="ctor"></a> unorm

Конструктор по умолчанию. Инициализируйте 0, 0f.

```
unorm(
    void) restrict(amp,
    cpu);

explicit unorm(
    float _V) restrict(amp,
    cpu);

explicit unorm(
    unsigned int _V) restrict(amp,
    cpu);

explicit unorm(
    int _V) restrict(amp,
    cpu);

explicit unorm(
    double _V) restrict(amp,
    cpu);

unorm(
    const unorm& _Other) restrict(amp,
    cpu);

inline explicit unorm(
    const norm& _Other) restrict(amp,
    cpu);
```

### <a name="parameters"></a>Параметры

*_V*<br/>
Значение, используемое для инициализации.

*_Другое*<br/>
Норма объект, используемый для инициализации.

## <a name="see-also"></a>См. также

[Пространство имен Concurrency::graphics](concurrency-graphics-namespace.md)
