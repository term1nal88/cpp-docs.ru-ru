---
title: Встроенные функции _InterlockedExchangeAdd | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _InterlockedExchangeAdd64_nf
- _InterlockedExchangeAdd64_rel
- _InterlockedExchangeAdd16_rel
- _InterlockedExchangeAdd_acq
- _InterlockedExchangeAdd_nf
- _InterlockedExchangeAdd_rel
- _InterlockedExchangeAdd8_acq
- _InterlockedExchangeAdd16_nf
- _InterlockedExchangeAdd_acq_cpp
- _InterlockedExchangeAdd64_acq_cpp
- _InterlockedExchangeAdd16_acq
- _InterlockedExchangeAdd_HLERelease
- _InterlockedExchangeAdd64_cpp
- _InterlockedExchangeAdd64_HLERelease
- _InterlockedExchangeAdd64_acq
- _InterlockedExchangeAdd8
- _InterlockedExchangeAdd64
- _InterlockedExchangeAdd8_nf
- _InterlockedExchangeAdd16
- _InterlockedExchangeAdd64_rel_cpp
- _InterlockedExchangeAdd_cpp
- _InterlockedExchangeAdd8_rel
- _InterlockedExchangeAdd_HLEAcquire
- _InterlockedExchangeAdd64_HLEAcquire
- _InterlockedExchangeAdd
dev_langs:
- C++
helpviewer_keywords:
- _InterlockedExchangeAdd8_nf intrinsic
- InterlockedExchangeAdd64_acq intrinsic
- _InterlockedExchangeAdd8_acq intrinsic
- _InterlockedExchangeAdd64 intrinsic
- _InterlockedExchangeAdd intrinsic
- _InterlockedExchangeAdd8_rel intrinsic
- _InterlockedExchangeAdd_acq intrinsic
- _InterlockedExchangeAdd_HLEAcquire intrinsic
- _InterlockedExchangeAdd8 intrinsic
- _InterlockedExchangeAdd_rel intrinsic
- _InterlockedExchangeAdd64_HLERelease intrinsic
- _InterlockedExchangeAdd64_nf intrinsic
- InterlockedExchangeAdd_rel intrinsic
- InterlockedExchangeAdd intrinsic
- _InterlockedExchangeAdd_nf intrinsic
- _InterlockedExchangeAdd16_rel intrinsic
- InterlockedExchangeAdd_acq intrinsic
- _InterlockedExchangeAdd64_HLEAcquire intrinsic
- _InterlockedExchangeAdd16 intrinsic
- _InterlockedExchangeAdd64_acq intrinsic
- InterlockedExchangeAdd64_rel intrinsic
- _InterlockedExchangeAdd16_acq intrinsic
- InterlockedExchangeAdd64 intrinsic
- _InterlockedExchangeAdd_HLERelease intrinsic
- _InterlockedExchangeAdd16_nf intrinsic
- _InterlockedExchangeAdd64_rel intrinsic
ms.assetid: 25809e1f-9c60-4492-9f7c-0fb59c8d13d2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7ce2417af10ba5f76c1d4170e41e0c037b07419c
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46406013"
---
# <a name="interlockedexchangeadd-intrinsic-functions"></a>Встроенные функции _InterlockedExchangeAdd

**Блок, относящийся только к системам Microsoft**

Предоставляют встроенную поддержку компилятора для пакета SDK Windows Win32 [встроенные функции _InterlockedExchangeAdd](../intrinsics/interlockedexchangeadd-intrinsic-functions.md) функции.

## <a name="syntax"></a>Синтаксис

```
long _InterlockedExchangeAdd(
   long volatile * Addend,
   long Value
);
long _InterlockedExchangeAdd_acq(
   long volatile * Addend,
   long Value
);
long _InterlockedExchangeAdd_rel(
   long volatile * Addend,
   long Value
);
long _InterlockedExchangeAdd_nf(
   long volatile * Addend,
   long Value
);
long _InterlockedExchangeAdd_HLEAcquire(
   long volatile * Addend,
   long Value
);
long _InterlockedExchangeAdd_HLERelease(
   long volatile * Addend,
   long Value
);
char _InterlockedExchangeAdd8(
   char volatile * Addend,
   char Value
);
char _InterlockedExchangeAdd8_acq(
   char volatile * Addend,
   char Value
);
char _InterlockedExchangeAdd8_rel(
   char volatile * Addend,
   char Value
);
char _InterlockedExchangeAdd8_nf(
   char volatile * Addend,
   char Value
);
short _InterlockedExchangeAdd16(
   short volatile * Addend,
   short Value
);
short _InterlockedExchangeAdd16_acq(
   short volatile * Addend,
   short Value
);
short _InterlockedExchangeAdd16_rel(
   short volatile * Addend,
   short Value
);
short _InterlockedExchangeAdd16_nf(
   short volatile * Addend,
   short Value
);
__int64 _InterlockedExchangeAdd64(
   __int64 volatile * Addend,
   __int64 Value
);
__int64 _InterlockedExchangeAdd64_acq(
   __int64 volatile * Addend,
   __int64 Value
);
__int64 _InterlockedExchangeAdd64_rel(
   __int64 volatile * Addend,
   __int64 Value
);
__int64 _InterlockedExchangeAdd64_nf(
   __int64 volatile * Addend,
   __int64 Value
);
__int64 _InterlockedExchangeAdd64_HLEAcquire(
   __int64 volatile * Addend,
   __int64 Value
);
__int64 _InterlockedExchangeAdd64_HLERelease(
   __int64 volatile * Addend,
   __int64 Value
);

```

#### <a name="parameters"></a>Параметры

*Слагаемое*<br/>
[in, out] Значение для сложения; заменяется результатом сложения.

*Значение*<br/>
[in] Добавляемое значение.

## <a name="return-value"></a>Возвращаемое значение

Возвращает начальное значение переменной, на которую указывает параметр`Addend` .

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|Верхний колонтитул|
|---------------|------------------|------------|
|`_InterlockedExchangeAdd`, `_InterlockedExchangeAdd8`, `_InterlockedExchangeAdd16`, `_InterlockedExchangeAdd64`|x86, ARM, x64|\<Intrin.h >|
|`_InterlockedExchangeAdd_acq`, `_InterlockedExchangeAdd_rel`, `_InterlockedExchangeAdd_nf`, `_InterlockedExchangeAdd8_acq`, `_InterlockedExchangeAdd8_rel`, `_InterlockedExchangeAdd8_nf`,`_InterlockedExchangeAdd16_acq`, `_InterlockedExchangeAdd16_rel`, `_InterlockedExchangeAdd16_nf`, `_InterlockedExchangeAdd64_acq`, `_InterlockedExchangeAdd64_rel`, `_InterlockedExchangeAdd64_nf`|ARM|\<Intrin.h >|
|`_InterlockedExchangeAdd_HLEAcquire`, `_InterlockedExchangeAdd_HLERelease`, `_InterlockedExchangeAdd64_HLEAcquire`, `_InterlockedExchangeAdd64_HLErelease`|x86, x64|\<immintrin.h >|

## <a name="remarks"></a>Примечания

Существуют несколько вариантов `_InterlockedExchangeAdd`, они различаются в зависимости от типов данных, которые включают, и от того, используется ли семантика получения или освобождения конкретного процессора.

Функция `_InterlockedExchangeAdd` работает с 32-разрядными целыми значениями, `_InterlockedExchangeAdd8`работает с 8-разрядными целыми значениями, `_InterlockedExchangeAdd16` работает с 16-разрядными целыми значениями и `_InterlockedExchangeAdd64` работает с 64-разрядными целыми значениями.

На платформах ARM используйте встроенные функции с суффиксами `_acq` и `_rel`, если нужно получить и освободить семантику, например в начале и конце критической секции. Встроенные функции с суффиксом `_nf` («без границ») не действуют как барьер памяти.

На платформах Intel ®, поддерживающих инструкции Hardware Lock Elision (HLE), встроенные функции с суффиксами `_HLEAcquire` и `_HLERelease` включают подсказку процессору, как можно повысить производительность, устраняя шаг записи с блокировкой оборудования. Если эти встроенные функции вызываются на платформах, не поддерживающих HLE, подсказка игнорируется.

Эти процедуры доступны только как встроенные объекты. Таким образом, они являются встроенными ли или не [/Oi](../build/reference/oi-generate-intrinsic-functions.md) или [#pragma intrinsic](../preprocessor/intrinsic.md) используется. Невозможно использовать [#pragma function](../preprocessor/function-c-cpp.md) на этих встроенных функций.

## <a name="example"></a>Пример

Пример использования `_InterlockedExchangeAdd`, см. в разделе [_InterlockedDecrement](../intrinsics/interlockeddecrement-intrinsic-functions.md).

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)<br/>
[Конфликты с 32-разрядным (x86) компилятором](../build/conflicts-with-the-x86-compiler.md)