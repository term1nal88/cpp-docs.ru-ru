---
title: Класс extreme_value_distribution | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- random/std::extreme_value_distribution
- random/std::extreme_value_distribution::reset
- random/std::extreme_value_distribution::a
- random/std::extreme_value_distribution::b
- random/std::extreme_value_distribution::param
- random/std::extreme_value_distribution::min
- random/std::extreme_value_distribution::max
- random/std::extreme_value_distribution::operator()
- random/std::extreme_value_distribution::param_type
- random/std::extreme_value_distribution::param_type::a
- random/std::extreme_value_distribution::param_type::b
- random/std::extreme_value_distribution::param_type::operator==
- random/std::extreme_value_distribution::param_type::operator!=
dev_langs:
- C++
helpviewer_keywords:
- std::extreme_value_distribution [C++]
- std::extreme_value_distribution [C++], reset
- std::extreme_value_distribution [C++], a
- std::extreme_value_distribution [C++], b
- std::extreme_value_distribution [C++], param
- std::extreme_value_distribution [C++], min
- std::extreme_value_distribution [C++], max
- std::extreme_value_distribution [C++], param_type
- std::extreme_value_distribution [C++], param_type
ms.assetid: a0cd8370-0a54-4e26-9388-8b9678fb57da
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 10c93374a1ed9ed4fa875c78310d9ffa34406b83
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44100849"
---
# <a name="extremevaluedistribution-class"></a>Класс extreme_value_distribution

Формирует распределение экстремальных значений.

## <a name="syntax"></a>Синтаксис

```cpp
template<class RealType = double>
class extreme_value_distribution
   {
public:
   // types
   typedef RealType result_type;
   struct param_type;

   // constructor and reset functions
   explicit extreme_value_distribution(result_type a = 0.0, result_type b = 1.0);
   explicit extreme_value_distribution(const param_type& parm);
   void reset();

   // generating functions
   template <class URNG>
   result_type operator()(URNG& gen);
   template <class URNG>
   result_type operator()(URNG& gen, const param_type& parm);

   // property functions
   result_type a() const;
   result_type b() const;
   param_type param() const;
   void param(const param_type& parm);
   result_type min() const;
   result_type max() const;
   };
```

### <a name="parameters"></a>Параметры

*RealType*<br/>
По умолчанию используется тип результат с плавающей запятой, **двойные**. Возможные типы см. в разделе [\<random>](../standard-library/random.md).

*РГСЧ*<br/>
Механизм генератора случайных чисел. Возможные типы см. в разделе [\<random>](../standard-library/random.md).

## <a name="remarks"></a>Примечания

Класс шаблона описывает распределение, которое формирует значения указанного пользователем с плавающей запятой типа или типа **двойные** Если тип не указан, распределенные в соответствии с распределением экстремальных значений. В следующей таблице представлены ссылки на статьи об отдельных членах.

||||
|-|-|-|
|[extreme_value_distribution](#extreme_value_distribution)|`extreme_value_distribution::a`|`extreme_value_distribution::param`|
|`extreme_value_distribution::operator()`|`extreme_value_distribution::b`|[param_type](#param_type)|

Функции свойств `a()` и `b()` возвращают соответствующие значения для хранимых параметров распределения `a` и `b`.

Дополнительные сведения о классах распределения и их членах см. в разделе [\<random>](../standard-library/random.md).

Дополнительные сведения о распределении экстремальных значений см. в статье [Распределение экстремальных значений](http://go.microsoft.com/fwlink/p/?linkid=401110) на веб-сайте Wolfram MathWorld.

## <a name="example"></a>Пример

```cpp
// compile with: /EHsc /W4
#include <random>
#include <iostream>
#include <iomanip>
#include <string>
#include <map>

void test(const double a, const double b, const int s) {

    // uncomment to use a non-deterministic generator
    //    std::random_device gen;

    std::mt19937 gen(1701);

    std::extreme_value_distribution<> distr(a, b);

    std::cout << std::endl;
    std::cout << "min() == " << distr.min() << std::endl;
    std::cout << "max() == " << distr.max() << std::endl;
    std::cout << "a() == " << std::fixed << std::setw(11) << std::setprecision(10) << distr.a() << std::endl;
    std::cout << "b() == " << std::fixed << std::setw(11) << std::setprecision(10) << distr.b() << std::endl;

    // generate the distribution as a histogram
    std::map<double, int> histogram;
    for (int i = 0; i < s; ++i) {
        ++histogram[distr(gen)];
    }

    // print results
    std::cout << "Distribution for " << s << " samples:" << std::endl;
    int counter = 0;
    for (const auto& elem : histogram) {
        std::cout << std::fixed << std::setw(11) << ++counter << ": "
            << std::setw(14) << std::setprecision(10) << elem.first << std::endl;
    }
    std::cout << std::endl;
}

int main()
{
    double a_dist = 0.0;
    double b_dist = 1;

    int samples = 10;

    std::cout << "Use CTRL-Z to bypass data entry and run using default values." << std::endl;
    std::cout << "Enter a floating point value for the \'a\' distribution parameter: ";
    std::cin >> a_dist;
    std::cout << "Enter a floating point value for the \'b\' distribution parameter (must be greater than zero): ";
    std::cin >> b_dist;
    std::cout << "Enter an integer value for the sample count: ";
    std::cin >> samples;

    test(a_dist, b_dist, samples);
}
```

```Output
Use CTRL-Z to bypass data entry and run using default values.
Enter a floating point value for the 'a' distribution parameter: 0
Enter a floating point value for the 'b' distribution parameter (must be greater than zero): 1
Enter an integer value for the sample count: 10

min() == -1.79769e+308
max() == 1.79769e+308
a() == 0.0000000000
b() == 1.0000000000
Distribution for 10 samples:
    1: -0.8813940331
    2: -0.7698972281
    3: 0.2951258007
    4: 0.3110450734
    5: 0.4210546820
    6: 0.4210688771
    7: 0.4598857960
    8: 1.3155194200
    9: 1.5379170046
    10: 2.0568757061
```

## <a name="requirements"></a>Требования

**Заголовок:** \<random>

**Пространство имен:** std

## <a name="extreme_value_distribution"></a>  extreme_value_distribution::extreme_value_distribution

Формирует распределение.

```cpp
explicit extreme_value_distribution(result_type a_value = 0.0, result_type b_value = 1.0);
explicit extreme_value_distribution(const param_type& parm);
```

### <a name="parameters"></a>Параметры

*a_value*<br/>
Параметр распределения `a`.

*b_value*<br/>
Параметр распределения `b`.

*parm*<br/>
Структура `param_type`, используемая для формирования распределения.

### <a name="remarks"></a>Примечания

**Предусловие:** `0.0 < b`

Первый конструктор создает объект, хранимое значение `a` которого содержит значение *a_value*, а значение `b` содержит значение *b_value*.

Второй конструктор создает объект, хранимые параметры которого инициализируются из *parm*. Вы можете получить и задать текущие параметры существующего распределения, вызвав функцию-член `param()`.

## <a name="param_type"></a>  extreme_value_distribution::param_type

Сохраняет параметры распределения.

```cpp
struct param_type {
   typedef extreme_value_distribution<result_type> distribution_type;
   param_type(result_type a_value = 0.0, result_type b_value = 1.0);
   result_type a() const;
   result_type b() const;

   bool operator==(const param_type& right) const;
   bool operator!=(const param_type& right) const;
   };
```

### <a name="parameters"></a>Параметры

*a_value*<br/>
Параметр распределения `a`.

*b_value*<br/>
Параметр распределения `b`.

*right*<br/>
Объект `param_type`, который требуется сравнить с данным объектом.

### <a name="remarks"></a>Примечания

**Предусловие:** `0.0 < b`

Эту структуру можно передать конструктору класса распределения во время создания экземпляра, функции-члену `param()` для установки хранимых параметров существующего распределения и `operator()` для использования вместо хранимых параметров.

## <a name="see-also"></a>См. также

[\<random>](../standard-library/random.md)<br/>
