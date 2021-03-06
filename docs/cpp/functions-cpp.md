---
title: Функции (C++) | Документация Майкрософт
ms.custom: ''
ms.date: 01/25/2018
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- defaults, arguments
- function definitions
- function definitions, about function definitions
- default arguments
- declarators, functions
ms.assetid: 33ba01d5-75b5-48d2-8eab-5483ac7d2274
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 24eded7bac023bd2291e0c574012f72ba86b6bcf
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50053803"
---
# <a name="functions-c"></a>Функции (C++)

Функции — это блоки кода, выполняющие определенные операции. Если требуется, функция может определять входные параметры, позволяющие вызывающим объектам передавать ей аргументы. При необходимости функция также может возвращать значение как выходное. Функции полезны для инкапсуляции основных операций в едином блоке, который может многократно использоваться. В идеальном случае имя этого блока должно четко описывать назначение функции. Следующая функция принимает два целых числа от вызывающего объекта и возвращает их сумму. *a* и *b* являются *параметры* типа **int**.

```cpp
int sum(int a, int b)
{
    return a + b;
}
```

Эту функцию можно вызывать, или *вызывается*, из любого количества адресов в программе. Значения, которые передаются в функцию *аргументы*, типы которых должны быть совместимы с типами параметров в определении функции.

```cpp
int main()
{
    int i = sum(10, 32);
    int j = sum(i, 66);
    cout << "The value of j is" << j << endl; // 108
}
```

Длина функции практически не ограничена, однако для максимальной эффективности кода целесообразно использовать функции, каждая из которых выполняет одиночную, четко определенную задачу. Сложные алгоритмы лучше разбивать на более короткие и простые для понимания функции, если это возможно.

Функции, определенные в области видимости класса, называются функциями-членами. В C++, в отличие от других языков, функции можно также определять в области видимости пространства имен (включая неявное глобальное пространство имен). Такие функции называются *свободные функции* или *не являющиеся членами функции*; они широко используются в стандартной библиотеке.

Функции могут быть *перегружены*, что означает разные версии функции могут совместно использовать тем же именем, если они отличаются по количество или типы формальных параметров. Дополнительные сведения см. в разделе [перегрузка функций](../cpp/function-overloading.md).

## <a name="parts-of-a-function-declaration"></a>Части объявления функции

Функции, как минимум *объявление* состоит из возвращаемого типа, имя функции и список параметров (может быть пустым), а также необязательные ключевые слова, которые предоставляют дополнительные инструкции компилятору. Следующий пример — объявление функции:

```cpp
int sum(int a, int b);
```

Определение функции включает объявления, плюс *текст*, который является весь код между фигурными скобками:

```cpp
int sum(int a, int b)
{
    return a + b;
}
```

Объявление функции, за которым следует точка с запятой, может многократно встречаться в разных местах кода программы. Оно необходимо перед любыми вызовами этой функции в каждой записи преобразования. По правилу одного определения, определение функции должно фигурировать в коде программы лишь один раз.

При объявлении функции необходимо указать:

1. Возвращаемый тип, который задает тип значения, возвращаемого значения, или **void** Если значение не возвращается. В C ++ 11 **автоматически** является допустимым типом возвращаемого значения, которое предписывает компилятору логически распознавать тип с оператором return. Тип decltype (auto) также используется в C++14. Дополнительные сведения см. в подразделе "Выведение возвращаемых типов" ниже.

1. Имя функции, которое должно начинаться с буквы или символа подчеркивания и не должно содержать пробелов. В стандартной библиотеке со знака подчеркивания обычно начинаются имена закрытых функций-членов или функций, не являющихся членами и не предназначенных для использования в вашем коде.

1. Список параметров, заключенный в скобки. В этом списке через запятую указывается нужное (возможно, нулевое) число параметров, задающих тип и, при необходимости, локальное имя, по которому к значениям можно получить доступ в теле функции.

Необязательные элементы объявления функции:

1. `constexpr` — указывает, что возвращаемое значение функции является константой, значение которой может быть определено во время компиляции.

    ```cpp
    constexpr float exp(float x, int n)
    {
        return n == 0 ? 1 :
            n % 2 == 0 ? exp(x * x, n / 2) :
            exp(x * x, (n - 1) / 2) * x;
    };
    ```

1. Его спецификация компоновки **extern** или **статических**.

    ```cpp
    //Declare printf with C linkage.
    extern "C" int printf( const char *fmt, ... );

    ```

   Дополнительные сведения см. в разделе [программа и компоновка](../cpp/program-and-linkage-cpp.md).

1. **встроенный**, предписывающее компилятору команду заменять каждый вызов функции с код самой функции. Подстановка может улучшить эффективность кода в сценариях, где функция выполняется быстро и многократно вызывается во фрагментах, являющихся критическими для производительности программы.

    ```cpp
    inline double Account::GetBalance()
    {
        return balance;
    }
    ```

   Дополнительные сведения см. в разделе [встраиваемые функции](../cpp/inline-functions-cpp.md).

1. Объект `noexcept` выражение, которое указывает ли функция может создавать исключения. В следующем примере функция не вызывает исключение, если `is_pod` выражение, результатом которого является **true**.

    ```cpp
    #include <type_traits>

    template <typename T>
    T copy_object(T& obj) noexcept(std::is_pod<T>) {...}
    ```

   Дополнительные сведения см. в разделе [noexcept](../cpp/noexcept-cpp.md).

1. (Только функции-члены) Cv квалификаторы, которые определяют, является ли эта функция **const** или **volatile**.

1. (Только функции-члены) **виртуального**, `override`, или `final`. **виртуальный** указывает, что функция может быть переопределена в производном классе. `override` — означает, что функция в производном классе переопределяет виртуальную функцию. `final` — означает, что функция не может быть переопределена ни в одном из последующих производных классов. Дополнительные сведения см. в разделе [виртуальные функции](../cpp/virtual-functions.md).

1. (только функции-члены) **статический** применяется к члену функция означает, что функция не связана с любой экземпляры объектов класса.

1. (Только для не являющегося статическим члена функции) Ref квалификатор, который указывает компилятору, какую перегрузку функции следует выбрать, если неявный объект-параметр (\*это) является ссылкой rvalue или ссылкой lvalue. Дополнительные сведения см. в разделе [перегрузка функций](function-overloading.md#ref-qualifiers).

На следующем рисунке показаны компоненты определения функции. Затененная область является телом функции.

![Части определения функции](../cpp/media/vc38ru1.gif "vc38RU1") части определения функции

## <a name="function-definitions"></a>Определения функций

Объект *определение функции* состоит из объявления и тело функции, заключенных в фигурные скобки, который содержит объявления переменных, операторы и выражения. В следующем примере показано определение функции при завершении:

```cpp
    int foo(int i, std::string s)
    {
       int value {i};
       MyClass mc;
       if(strcmp(s, "default") != 0)
       {
            value = mc.do_something(i);
       }
       return value;
    }
```

Переменные, объявленные в теле функции, называются локальными. Они исчезают из области видимости при выходе из функции, поэтому функция никогда не должна возвращать ссылку на локальную переменную.

```cpp
    MyClass& boom(int i, std::string s)
    {
       int value {i};
       MyClass mc;
       mc.Initialize(i,s);
       return mc;
    }
```

## <a name="const-and-constexpr-functions"></a>функции const и constexpr

Можно объявить функцию-член как **const** для указания, что функция не разрешено изменять значения членов данных в классе. Объявив функцию-член как **const**, позволяет компилятору обеспечить *const корректность*. Если кто-то по ошибке предпринимается попытка изменить объект, используя функцию, объявленную как **const**, возникает ошибка компилятора. Дополнительные сведения см. в разделе [const](const-cpp.md).

Объявите функцию как `constexpr` когда он выдает значение возможно можно определить во время компиляции. Функция constexpr обычно выполняется быстрее, чем базовые функции. Дополнительные сведения см. в разделе [constexpr](constexpr-cpp.md).

## <a name="function-templates"></a>Шаблоны функций

Шаблоны функций подобны шаблонам классов. Их задача заключается в создании конкретных функций на основе аргументов шаблонов. Во многих случаях шаблоны могут определять типы аргументов, поэтому их не требуется явно указывать.

```cpp
template<typename Lhs, typename Rhs>
auto Add2(const Lhs& lhs, const Rhs& rhs)
{
    return lhs + rhs;
}

auto a = Add2(3.13, 2.895); // a is a double
auto b = Add2(string{ "Hello" }, string{ " World" }); // b is a std::string
```

Дополнительные сведения см. в разделе [шаблонов функций](../cpp/function-templates.md)

## <a name="function-parameters-and-arguments"></a>Параметры и аргументы функций

У функции имеется список параметров, в котором через запятую перечислено необходимое (возможно, нулевое) число типов. Каждому параметру присваивается имя, по которому к нему можно получить доступ в теле функции. В шаблоне функции могут указываться дополнительные типы или значения параметров. Вызывающий объект передает аргументы, представляющие собой конкретные значения, типы которых совместимы со списком параметров.

По умолчанию аргументы передаются функции по значению, то есть функция получает копию передаваемого объекта. Копирование крупных объектов может быть ресурсозатратным и неоправданным. Чтобы аргументы для передачи по ссылке (в частности ссылки lvalue), добавьте параметр квантификатор ссылки:

```cpp
void DoSomething(std::string& input){...}
```

Если функция изменяет аргумент, передаваемый по ссылке, изменяется исходный объект, а не его локальная копия. Чтобы предотвратить изменение такого аргумента функцией, его следует определить как const&:

```cpp
void DoSomething(const std::string& input){...}
```

**C ++ 11:** для явной обработки аргументов, которые передаются по ссылке rvalue или ссылку lvalue, использовать двойной амперсанд на параметр чтобы указать универсальную ссылку:

```cpp
void DoSomething(const std::string&& input){...}
```

Функция, объявленная одним ключевым словом **void** в объявлении параметра списка не принимает аргументы, если ключевое слово **void** является первым и единственным членом списка объявления аргументов. Аргументы типа **void** в других местах списка создают ошибки. Пример:

```cpp

// OK same as GetTickCount()
long GetTickCount( void );
```

Обратите внимание, что, хотя и существует нельзя указывать **void** аргумент Кроме описанного здесь, типы, производные от типа **void** (например, указатели на **void** и массивы **void**) может находиться в любом месте списка объявления аргументов.

### <a name="default-arguments"></a>Аргументы по умолчанию

Последним параметрам в сигнатуре функции можно назначить аргумент по умолчанию, т. е. вызывающий объект сможет опустить аргумент при вызове функции, если не требуется указать какое-либо другое значение.

```cpp
int DoSomething(int num,
    string str,
    Allocator& alloc = defaultAllocator)
{ ... }

// OK both parameters are at end
int DoSomethingElse(int num,
    string str = string{ "Working" },
    Allocator& alloc = defaultAllocator)
{ ... }

// C2548: 'DoMore': missing default parameter for parameter 2
int DoMore(int num = 5, // Not a trailing parameter!
    string str,
    Allocator& = defaultAllocator)
{...}
```

Дополнительные сведения см. в разделе [аргументы по умолчанию](../cpp/default-arguments.md).

## <a name="function-return-types"></a>типов возвращаемых функциями значений;

Функция не может возвращать другие функции и встроенные массивы; Однако возможен возврат указателей на эти типы, или *лямбда-выражение*, создающий объект функции. За исключением того, в этих случаях функция может вернуть значение любого типа, который находится в области, или он не возвращать никакого значения, в этом случае возвращаемый тип — **void**.

### <a name="trailing-return-types"></a>Завершающие возвращаемые типы

"Обычные" типы возвращаемого значения расположены слева от сигнатуры функции. Объект *завершающего возвращаемого типа* находится в правой части подписи и предшествует оператор ->. Завершающие типы возвращаемого значения особенно полезны в шаблонах функций, когда тип возвращаемого значения зависит от параметров шаблона.

```cpp
template<typename Lhs, typename Rhs>
auto Add(const Lhs& lhs, const Rhs& rhs) -> decltype(lhs + rhs)
{
    return lhs + rhs;
}
```

Когда **автоматически** используется в сочетании с завершающим возвращаемым типом, он просто служит в качестве заполнителя для любого действия выражения decltype и сам по себе не выполняет выведение типа.

## <a name="function-local-variables"></a>Локальные переменные функции

Переменная, объявленная внутри тела другой функции, называется *локальной переменной* или просто *локального*. Нестатические локальные переменные видны только в теле функции. Если локальные переменные объявляются в стеке, они исчезают из области видимости при выходе из функции. При создании локальной переменной и ее возвращении по значению компилятор обычно выполняет оптимизацию возвращаемого значения, чтобы избежать ненужных операций копирования. Если локальная переменная возвращается по ссылке, компилятор выдаст предупреждение, поскольку любые попытки вызывающего объекта использовать эту ссылку произойдут после уничтожения локальной переменной.

В C++ локальные переменные можно объявлять как статические. Переменная является видимой только в теле функции, однако для всех экземпляров функции существует только одна копия переменной. Локальные статические объекты удаляются во время завершения, определенного директивой `atexit`. Если статический объект не был создан из-за того, что поток кода программы обошел соответствующее объявление, попытка уничтожения этого объект не предпринимается.

##  <a name="type_deduction"></a> Выведение возвращаемых типов (C ++ 14)

В C ++ 14, можно использовать **автоматически** можно указать компилятору вывести тип возвращаемого значения из тела функции без необходимости предоставления завершающего типа возвращаемого значения. Обратите внимание, что **автоматически** всегда выводит возврата по значению. Используйте `auto&&`, чтобы дать компилятору команду выведения ссылки.

В этом примере **автоматически** выведение как копии непостоянного значения суммы lhs и rhs.

```cpp
template<typename Lhs, typename Rhs>
auto Add2(const Lhs& lhs, const Rhs& rhs)
{
    return lhs + rhs; //returns a non-const object by value
}
```

Обратите внимание, что **автоматически** не сохраняет постоянность выводимого типа, он выводит. Для перенаправления, возвращаемое значение которой необходимо сохранить неизменность или привязанность (ref) аргументов функции, можно использовать **decltype(auto)** ключевое слово, которое использует **decltype** правила определения типов и сохраняет все сведения о типе. **decltype(AUTO)** может использоваться как обычное возвращаемое значение с левой стороны, или как завершающее возвращаемое значение.

Приведенный ниже (на основе кода [N3493](http://www.open-std.org/JTC1/SC22/WG21/docs/papers/2013/n3493.html)), показывает **decltype(auto)** , используемая для включения точную пересылку аргументов функции в тип возвращаемого значения, неизвестный до шаблон создать экземпляр.

```cpp
template<typename F, typename Tuple = tuple<T...>, int... I>
decltype(auto) apply_(F&& f, Tuple&& args, index_sequence<I...>)
{
    return std::forward<F>(f)(std::get<I>(std::forward<Tuple>(args))...);
}

template<typename F, typename Tuple = tuple<T...>,
    typename Indices = make_index_sequence<tuple_size<Tuple>::value >>
   decltype( auto)
    apply(F&& f, Tuple&& args)
{
    return apply_(std::forward<F>(f), std::forward<Tuple>(args), Indices());
}
}
```

## <a name="multi_val"></a> Возвращение нескольких значений из функции

Существует несколько способов для возврата более одного значения из функции:

1. Инкапсуляция значения в объект с именем класса или структуры. Требуется определение класса или структуры, чтобы быть видимым для вызывающего объекта:

    ```cpp
    #include <string>
    #include <iostream>

    using namespace std;

    struct S
    {
        string name;
        int num;
    };

    S g()
    {
        string t{ "hello" };
        int u{ 42 };
        return { t, u };
    }

    int main()
    {
        S s = g();
        cout << s.name << " " << s.num << endl;
        return 0;
    }
    ```

1. Возвращает объект std::tuple или std::pair:

    ```cpp
    #include <tuple>
    #include <string>
    #include <iostream>

    using namespace std;

    tuple<int, string, double> f()
    {
        int i{ 108 };
        string s{ "Some text" };
        double d{ .01 };
        return { i,s,d };
    }

    int main()
    {
        auto t = f();
        cout << get<0>(t) << " " << get<1>(t) << " " << get<2>(t) << endl;

        // --or--

        int myval;
        string myname;
        double mydecimal;
        tie(myval, myname, mydecimal) = f();
        cout << myval << " " << myname << " " << mydecimal << endl;

        return 0;
    }
    ```

1. **Visual Studio 2017 версии 15.3 и более поздние версии** (состав [/std: c ++ 17](../build/reference/std-specify-language-standard-version.md)): использование структурированной привязки. Преимуществом структурированные привязки является то, что, в которых хранятся возвращаемые значения инициализации переменных в то же время, в которой они объявлены, что в некоторых случаях может быть значительно эффективнее. В этом операторе--`auto[x, y, z] = f();`--квадратные скобки, вводят и инициализировать имена, которые находятся в области видимости блока всей функции.

    ```cpp
    #include <tuple>
    #include <string>
    #include <iostream>

    using namespace std;

    tuple<int, string, double> f()
    {
        int i{ 108 };
        string s{ "Some text" };
        double d{ .01 };
        return { i,s,d };
    }
    struct S
    {
        string name;
        int num;
    };

    S g()
    {
        string t{ "hello" };
        int u{ 42 };
        return { t, u };
    }

    int main()
    {
        auto[x, y, z] = f(); // init from tuple
        cout << x << " " << y << " " << z << endl;

        auto[a, b] = g(); // init from POD struct
        cout << a << " " << b << endl;
        return 0;
    }
    ```

1. Помимо использования самого возвращаемое значение, можно «вернуть» значения путем определения любое количество параметров для использования передаваемый по ссылке, чтобы ее можно изменить или инициализации значений объектов, которые вызывающий объект предоставляет. Дополнительные сведения см. в разделе [аргументы функции ссылочного типа](reference-type-function-arguments.md).

## <a name="function-pointers"></a>Указатели на функции

Как и в C, в C++ поддерживаются указатели на функции. Однако более типобезопасной альтернативой обычно служит использование объекта-функции.

Рекомендуется **typedef** могут использоваться для объявления псевдонима для типа указателя функции, если объявление функции, возвращающей тип указателя на функцию.  Пример

```cpp
typedef int (*fp)(int);
fp myFunction(char* s); // function returning function pointer
```

Если оно не используется, то правильный синтаксис объявления функции можно вывести из синтаксиса декларатора для указателя на функцию, заменив идентификатор (в приведенном выше примере — `fp`) на имя функции и список аргументов, как показано выше:

```cpp
int (*myFunction(char* s))(int);
```

Это объявление эквивалентно объявлению при помощи ключевого слова typedef, которое приводилось выше.

## <a name="see-also"></a>См. также

[Перегрузка функции](../cpp/function-overloading.md)<br/>
[Функции с переменными списками аргументов](../cpp/functions-with-variable-argument-lists-cpp.md)<br/>
[Явно используемые по умолчанию и удаленные функции](../cpp/explicitly-defaulted-and-deleted-functions.md)<br/>
[Поиск имен функций с зависимостью от аргументов (поиск Koenig)](../cpp/argument-dependent-name-koenig-lookup-on-functions.md)<br/>
[Аргументы по умолчанию](../cpp/default-arguments.md)<br/>
[Встраиваемые функции](../cpp/inline-functions-cpp.md)
