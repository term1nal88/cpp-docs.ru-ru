---
title: Класс is_integral | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::is_integral
dev_langs:
- C++
helpviewer_keywords:
- is_integral class
- is_integral
ms.assetid: fe9279d0-4495-4e88-bf23-153cc6602397
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c44288c990f773984492f7c05b80423b17c1a37c
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44110582"
---
# <a name="isintegral-class"></a>Класс is_integral

Проверяет, является ли тип целочисленным.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Ty>
struct is_integral;
```

### <a name="parameters"></a>Параметры

*Ty*<br/>
Запрашиваемый тип.

## <a name="remarks"></a>Примечания

Экземпляр предиката типа содержит значение true, если тип *Ty* является одним из целочисленных типов или `cv-qualified` форму одного из целочисленных типов, в противном случае он содержит значение false.

Целочисленный тип данных является одним из **bool**, **char**, **unsigned char**, **автоматический char**, **wchar_t**, **короткие**, **unsigned short**, **int**, **unsigned int**, **long**и **unsigned long**. Кроме того, с помощью компиляторов, которые обеспечивают их, целочисленный тип данных может принимать одно из **long long**, **long long без знака**, **__int64**, и **unsigned __int64**.

## <a name="example"></a>Пример

```cpp
// std__type_traits__is_integral.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

struct trivial
    {
    int val;
    };

int main()
    {
    std::cout << "is_integral<trivial> == " << std::boolalpha
        << std::is_integral<trivial>::value << std::endl;
    std::cout << "is_integral<int> == " << std::boolalpha
        << std::is_integral<int>::value << std::endl;
    std::cout << "is_integral<float> == " << std::boolalpha
        << std::is_integral<float>::value << std::endl;

    return (0);
    }

```

```Output
is_integral<trivial> == false
is_integral<int> == true
is_integral<float> == false
```

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)<br/>
[Класс is_enum](../standard-library/is-enum-class.md)<br/>
[Класс is_floating_point](../standard-library/is-floating-point-class.md)<br/>
