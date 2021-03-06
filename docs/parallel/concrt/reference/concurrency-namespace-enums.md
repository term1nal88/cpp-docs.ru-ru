---
title: перечисления пространства имен Concurrency | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CONCRT/concurrency::Agents_EventType
- CONCRT/concurrency::Concrt_TraceFlags
- CONCRT/concurrency::CriticalRegionType
- CONCRT/concurrency::PolicyElementKey
- CONCRT/concurrency::SchedulerType
- CONCRT/concurrency::SwitchingProxyState
- CONCRT/concurrency::WinRTInitializationType
- CONCRT/concurrency::join_type
- CONCRT/concurrency::message_status Enumeration
dev_langs:
- C++
ms.assetid: a40e3b2d-ad21-4229-9880-2cfa84f7ab8f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 49ae12184189996561717874833d6cdf3f30e159
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50078849"
---
# <a name="concurrency-namespace-enums"></a>перечисления пространства имен Concurrency

||||
|-|-|-|
|[Agents_EventType](#agents_eventtype)|[ConcRT_EventType](#concrt_eventtype)|[Concrt_TraceFlags](#concrt_traceflags)|
|[CriticalRegionType](#criticalregiontype)|[DynamicProgressFeedbackType](#dynamicprogressfeedbacktype)|[PolicyElementKey](#policyelementkey)|
|[SchedulerType](#schedulertype)|[SchedulingProtocolType](#schedulingprotocoltype)|[SwitchingProxyState](#switchingproxystate)|
|[WinRTInitializationType](#winrtinitializationtype)|[agent_status](#agent_status)|[join_type](#join_type)|
|[message_status](#message_status)|[task_group_status](#task_group_status)|

##  <a name="agent_status"></a>  Перечисление agent_status

Допустимые состояния для объекта `agent`.

```
enum agent_status;
```

### <a name="values"></a>Значения

|Имя|Описание|
|----------|-----------------|
|`agent_canceled`|Объект `agent` отменен.|
|`agent_created`|`agent` Был создан, но не запущена.|
|`agent_done`|`agent` Завершился без отмены.|
|`agent_runnable`|`agent` К работе, но не введен его `run` метод.|
|`agent_started`|`agent` Запущена.|

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [асинхронных агентов](../../../parallel/concrt/asynchronous-agents.md).

### <a name="requirements"></a>Требования

**Заголовок:** concrt.h

##  <a name="agents_eventtype"></a>  Перечисление Agents_EventType

Типы событий, которые можно отслеживать с помощью функции трассировки, предоставляемой библиотекой агентов.

```
enum Agents_EventType;
```

### <a name="values"></a>Значения

|Имя|Описание|
|----------|-----------------|
|`AGENTS_EVENT_CREATE`|Тип события, который представляет создание объекта|
|`AGENTS_EVENT_DESTROY`|Тип события, который представляет удаление объекта|
|`AGENTS_EVENT_END`|Тип события, который представляет завершение некоторой обработки|
|`AGENTS_EVENT_LINK`|Тип события, который представляет связывание блоков сообщений|
|`AGENTS_EVENT_NAME`|Тип события, который представляет имя для объекта|
|`AGENTS_EVENT_SCHEDULE`|Тип события, который представляет расписание процесса|
|`AGENTS_EVENT_START`|Тип события, который представляет запуск некоторой обработки|
|`AGENTS_EVENT_UNLINK`|Тип события, который представляет отвязку блоков сообщений|

### <a name="requirements"></a>Требования

**Заголовок:** concrt.h

##  <a name="concrt_eventtype"></a>  Перечисление ConcRT_EventType

Типы событий, которые можно отслеживать с помощью функций трассировки, обеспечиваемых средой выполнения с параллелизмом.

```
enum ConcRT_EventType;
```

### <a name="values"></a>Значения

|Имя|Описание|
|----------|-----------------|
|`CONCRT_EVENT_ATTACH`|Тип события, который представляет процесс присоединения к планировщику.|
|`CONCRT_EVENT_BLOCK`|Тип события, который представляет акт блокировки контекста.|
|`CONCRT_EVENT_DETACH`|Тип события, который представляет акт отсоединения от планировщика.|
|`CONCRT_EVENT_END`|Тип события, отмечающий начало пары событий начала и окончания.|
|`CONCRT_EVENT_GENERIC`|Тип события, используемые для различных событий.|
|`CONCRT_EVENT_IDLE`|Тип события, который представляет акт контекста, переходящих в состояние простоя.|
|`CONCRT_EVENT_START`|Тип события, отмечающий начало пары событий начала и окончания.|
|`CONCRT_EVENT_UNBLOCK`|Тип события, который представляет акт разблокирования контекста.|
|`CONCRT_EVENT_YIELD`|Тип события, который представляет акт выдачи контекста.|

### <a name="requirements"></a>Требования

**Заголовок:** concrt.h **пространство имен:** параллелизма

##  <a name="concrt_traceflags"></a>  Перечисление Concrt_TraceFlags

Флажки трассировки для типов событий

```
enum Concrt_TraceFlags;
```

### <a name="values"></a>Значения

|Имя|Описание|
|----------|-----------------|
|`AgentEventFlag`||
|`AllEventsFlag`||
|`ContextEventFlag`||
|`PPLEventFlag`||
|`ResourceManagerEventFlag`||
|`SchedulerEventFlag`||
|`VirtualProcessorEventFlag`||

### <a name="requirements"></a>Требования

**Заголовок:** concrt.h

##  <a name="criticalregiontype"></a>  Перечисление CriticalRegionType

Тип критической области, внутри которой находится контекст.

```
enum CriticalRegionType;
```

### <a name="values"></a>Значения

|Имя|Описание|
|----------|-----------------|
|`InsideCriticalRegion`|Указывает, что контекст внутри критической области. Внутри критической области, асинхронные приостановки скрыты от планировщика. Такая приостановка может возникать, диспетчер ресурсов будет ожидать к запуску и просто возобновите ее вместо повторного вызова планировщика потока. Все блокировки, сделанные внутри такой области должна быть получена с особой осторожностью.|
|`InsideHyperCriticalRegion`|Указывает, что контекст внутри hyper критической области. При использовании внутри hyper критической области, синхронные и асинхронные приостановки скрыты от планировщика. Такая приостановка или блокировки происходит, диспетчер ресурсов будет ожидать к запуску и просто возобновите ее вместо повторного вызова планировщика потока. Блокировки, сделанные внутри такой области, никогда не должны использоваться совместно с код, выполняемый вне такие области. Это приведет к непредсказуемым взаимоблокировки.|
|`OutsideCriticalRegion`|Указывает, что контекст вне любой критической области.|

### <a name="requirements"></a>Требования

**Заголовок:** concrtrm.h

##  <a name="dynamicprogressfeedbacktype"></a>  Перечисление DynamicProgressFeedbackType

Используется политикой `DynamicProgressFeedback` для описания того, будет ли к ресурсам планировщика применена повторная балансировка в соответствии со статистическими данными, полученными из планировщика, или только на основе перехода виртуальных процессоров в состояние бездействия и из него через вызовы методов `Activate` и `Deactivate` для интерфейса `IVirtualProcessorRoot`. Дополнительные сведения о доступных политиках планировщиков см. в разделе [PolicyElementKey](concurrency-namespace-enums.md).

```
enum DynamicProgressFeedbackType;
```

### <a name="values"></a>Значения

|Имя|Описание|
|----------|-----------------|
|`ProgressFeedbackDisabled`|Планировщик не выполняет сбор сведений о ходе выполнения. Перераспределения выполняется на основе исключительно на уровне подписки базовой аппаратный поток. Дополнительные сведения об уровнях подписки см. в разделе [IExecutionResource::CurrentSubscriptionLevel](IExecutionResource-structure.md).<br /><br /> Это значение зарезервировано для использования средой выполнения.|
|`ProgressFeedbackEnabled`|Планировщик собирает сведения о ходе выполнения и передает его в диспетчер ресурсов. Диспетчер ресурсов будет использовать эти статистические данные для балансировки ресурсов от имени планировщика в дополнение к базовой аппаратный поток уровня подписки. Дополнительные сведения об уровнях подписки см. в разделе [IExecutionResource::CurrentSubscriptionLevel](IExecutionResource-structure.md).|
##  <a name="join_type"></a>  Перечисление join_type

Тип блока обмена сообщениями `join`.

```
enum join_type;
```

### <a name="values"></a>Значения

|Имя|Описание|
|----------|-----------------|
|`greedy`|"Жадные" `join` блоков обмена сообщениями немедленно принять сообщение после распространения. Это более эффективно, но имеет возможность для live с блокировкой, в зависимости от конфигурации сети.|
|`non_greedy`|Нежадный `join` блоков обмена сообщениями отложенных сообщений и попробуйте и использовать их, когда все поступили. Они гарантированно будут работать, но медленнее.|

### <a name="requirements"></a>Требования

**Заголовок:** agents.h

##  <a name="message_status"></a>  Перечисление message_status

Допустимые ответы на предложение объекта `message` блоку.

```
enum message_status;
```

### <a name="values"></a>Значения

|Имя|Описание|
|----------|-----------------|
|`accepted`|Целевой объект принял сообщение.|
|`declined`|Целевой объект не приняла сообщение.|
|`missed`|Целевой объект попытался принять сообщение, но оно было больше не доступно.|
|`postponed`|Целевой объект отложил сообщение.|

### <a name="requirements"></a>Требования

**Заголовок:** agents.h

##  <a name="policyelementkey"></a>  Перечисление PolicyElementKey

Ключи политики, описывающие аспекты поведения планировщика. Каждый элемент политики описан с помощью пары «ключ — значение». Дополнительные сведения о политиках планировщика и их влиянии на планировщики см. в разделе [планировщик](../../../parallel/concrt/task-scheduler-concurrency-runtime.md).

```
enum PolicyElementKey;
```

### <a name="values"></a>Значения

|Имя|Описание|
|----------|-----------------|
|`ContextPriority`|Приоритет потока операционной системы каждого контекста в планировщике. Если этот ключ будет присвоено значение `INHERIT_THREAD_PRIORITY` контекстов в планировщике наследуют приоритет потока, создавшего планировщик.<br /><br /> Допустимые значения: одно из допустимых значений для Windows `SetThreadPriority` функции и специальные значения `INHERIT_THREAD_PRIORITY`<br /><br /> Значение по умолчанию: `THREAD_PRIORITY_NORMAL`|
|`ContextStackSize`|Размер зарезервированного стека для каждого контекста в планировщике в килобайтах.<br /><br /> Допустимые значения: положительные целые числа<br /><br /> Значение по умолчанию: `0`, указывающее, что использовать процесса по умолчанию размер стека.|
|`DynamicProgressFeedback`|Определяет, будет ли сделано ресурсы для планировщика согласно статистическим сведениям, собранным из планировщика или только в зависимости от уровня подписки базовых аппаратных потоков. Дополнительные сведения см. в разделе [DynamicProgressFeedbackType](#dynamicprogressfeedbacktype).<br /><br /> Допустимые значения: членом `DynamicProgressFeedbackType` перечисления, либо `ProgressFeedbackEnabled` или `ProgressFeedbackDisabled`<br /><br /> Значение по умолчанию: `ProgressFeedbackEnabled`|
|`LocalContextCacheSize`|Когда `SchedulingProtocol` ключ политики будет присвоено значение `EnhanceScheduleGroupLocality`, этот параметр указывает максимальное количество работоспособных контекстов, которые разрешено кэшировать на локальных очередей виртуальный процессор в. Таких контекстов обычно выполняются в порядке (LIFO) последнего in-first-out виртуального процессора, которая привела к запуску. Обратите внимание, что данный параметр политики не то, когда `SchedulingProtocol` ключа будет присвоено значение `EnhanceForwardProgress`.<br /><br /> Допустимые значения: неотрицательными целыми числами<br /><br /> Значение по умолчанию: `8`|
|`MaxConcurrency`|Максимальный уровень параллелизма, необходимый в планировщике. Диспетчер ресурсов будет пытаться поначалу это количество виртуальных процессоров. Специальное значение [MaxExecutionResources](concurrency-namespace-constants1.md#maxexecutionresources) указывает, что нужный уровень параллельности совпадает количество аппаратных потоков на компьютере. Если значение, заданное для `MinConcurrency` больше, чем количество аппаратных потоков на компьютере и `MaxConcurrency` указывается как `MaxExecutionResources`, значение `MaxConcurrency` вызывается для сопоставления, заданный для `MinConcurrency`.<br /><br /> Допустимые значения: положительные целые числа и специальные значения `MaxExecutionResources`<br /><br /> Значение по умолчанию: `MaxExecutionResources`|
|`MaxPolicyElementKey`|Максимальный ключ элемента политики. Не допустимый ключ элемента.|
|`MinConcurrency`|Минимальный уровень параллелизма, которые предоставляются диспетчером ресурсов планировщику. Число виртуальных процессоров, назначенных планировщику никогда не перейдем меньше минимального. Специальное значение [MaxExecutionResources](concurrency-namespace-constants1.md#maxexecutionresources) указывает, что минимальный уровень параллелизма является такой же, как количество аппаратных потоков на компьютере. Если значение, заданное для `MaxConcurrency` меньше, чем количество аппаратных потоков на компьютере и `MinConcurrency` указывается как `MaxExecutionResources`, значение `MinConcurrency` уменьшается в соответствии с того, которое задано для `MaxConcurrency`.<br /><br /> Допустимые значения: неотрицательными целыми числами и специальное значение `MaxExecutionResources`. Обратите внимание, что для политик планировщика, используемых для создания планировщиков исполняющей среды с параллелизмом, значение `0` недопустимо.<br /><br /> Значение по умолчанию: `1`|
|`SchedulerKind`|Тип потоков, которые будет использовать планировщик для базовых контекстов выполнения. Дополнительные сведения см. в разделе [SchedulerType](#schedulertype).<br /><br /> Допустимые значения: элемент перечисления `SchedulerType`, например `ThreadScheduler`<br /><br /> Значение по умолчанию: `ThreadScheduler`. Это преобразует в Win32 потоки во всех операционных системах.|
|`SchedulingProtocol`|Описывает, какой алгоритм планирования будет использоваться в планировщике. Дополнительные сведения см. в разделе [SchedulingProtocolType](#schedulingprotocoltype).<br /><br /> Допустимые значения: членом `SchedulingProtocolType` перечисления, либо `EnhanceScheduleGroupLocality` или `EnhanceForwardProgress`<br /><br /> Значение по умолчанию: `EnhanceScheduleGroupLocality`|
|`TargetOversubscriptionFactor`|Под вопросом число виртуальных процессоров на аппаратном потоке. Коэффициент переподписки целевого объекта при необходимости может быть увеличен диспетчером ресурсов для обеспечения `MaxConcurrency` аппаратными потоками на компьютере.<br /><br /> Допустимые значения: положительные целые числа<br /><br /> Значение по умолчанию: `1`|
|`WinRTInitialization`||

### <a name="requirements"></a>Требования

**Заголовок:** concrt.h

##  <a name="schedulertype"></a>  Перечисление SchedulerType

Используется политикой `SchedulerKind` для описания типа потоков, которые должен использовать планировщик для базовых контекстов выполнения. Дополнительные сведения о доступных политиках планировщиков см. в разделе [PolicyElementKey](concurrency-namespace-enums.md).

```
enum SchedulerType;
```

### <a name="values"></a>Значения

|Имя|Описание|
|----------|-----------------|
|`ThreadScheduler`|Указывает явного запроса регулярных потоков Win32.|
|`UmsThreadDefault`|Планируемые потоки в режиме пользователя (UMS) не поддерживаются в среде выполнения с параллелизмом в Visual Studio 2013. Использование `UmsThreadDefault` в качестве значения для политики `SchedulerType` не приведет к ошибке. Однако, планировщик, созданный с помощью этой политики, по умолчанию будет настроен на использование потоков Win32.|

### <a name="requirements"></a>Требования

**Заголовок:** concrt.h

##  <a name="schedulingprotocoltype"></a>  Перечисление SchedulingProtocolType

Используется политикой `SchedulingProtocol` для описания того, какой алгоритм планирования будет использоваться для планировщика. Дополнительные сведения о доступных политиках планировщиков см. в разделе [PolicyElementKey](concurrency-namespace-enums.md).

```
enum SchedulingProtocolType;
```

### <a name="values"></a>Значения

|Имя|Описание|
|----------|-----------------|
|`EnhanceForwardProgress`|Планировщик предпочитает циклический перебор по группам расписаний после выполнения каждой задачи. Разблокированные контексты обычно планируются образом первый in-first-out (FIFO). Виртуальные процессоры не кэшируют разблокированные контексты.|
|`EnhanceScheduleGroupLocality`|Планировщик предпочитает продолжать работать над задачами в пределах текущей группы расписаний, прежде чем перейти к другой. Разблокированные контексты кэшируются на виртуальный процессор и обычно планируются образом последнего in-first-out (LIFO) виртуальный процессор, который их разблокировал.|

### <a name="requirements"></a>Требования

**Заголовок:** concrt.h

##  <a name="switchingproxystate"></a>  Перечисление SwitchingProxyState

Используется для обозначения состояния прокси-потока, когда он выполняет совместное переключение контекста на другой прокси-поток.

```
enum SwitchingProxyState;
```

### <a name="values"></a>Значения

|Имя|Описание|
|----------|-----------------|
|`Blocking`|Указывает, что вызывающий поток блокируется и должны быть исключительно владеет участник до повторного запуска впоследствии и выполнения других действий.|
|`Idle`|Указывает, что вызывающий поток больше не используется планировщик и возвращается к Resource Manager. Контекст, который был отправлен больше не может использоваться диспетчером ресурсов.|
|`Nesting`|Указывает, что вызывающий поток вложен дочерний планировщик и от вызывающего требуется для присоединения к другому планировщику.|

### <a name="remarks"></a>Примечания

Параметр типа `SwitchingProxyState` передается в метод `IThreadProxy::SwitchTo` для указания того, как обрабатывать прокси-поток, который выполняет вызов Resource Manager.

Дополнительные сведения об использовании этого типа см. в разделе [IThreadProxy::SwitchTo](ithreadproxy-structure.md#switchto).

##  <a name="task_group_status"></a>  Перечисление task_group_status

Описывает состояние выполнения объекта `task_group` или `structured_task_group`. Значение этого типа возвращается многочисленными методами, которые ожидают выполнения задач, запланированных для завершения группой задач.

```
enum task_group_status;
```

### <a name="values"></a>Значения

|Имя|Описание|
|----------|-----------------|
|`canceled`|Объект `task_group` или `structured_task_group` отменен. Одна или несколько задач, возможно, не были выполнены.|
|`completed`|Задачи, поставленные в очередь объекта `task_group` или `structured_task_group`, завершены успешно.|
|`not_complete`|Задачи, поставленные в очередь объекта `task_group`, не завершены. Обратите внимание, что это значение в настоящее время не возвращается исполняющей средой с параллелизмом.|

### <a name="requirements"></a>Требования

**Заголовок:** pplinterface.h

##  <a name="winrtinitializationtype"></a>  Перечисление WinRTInitializationType

Используется политикой `WinRTInitialization` для описания того, будет ли среда выполнения Windows инициализирована в потоках планировщика для приложения, которое работает в операционных системах Windows с версии 8 или выше, и каким образом это будет выполняться. Дополнительные сведения о доступных политиках планировщиков см. в разделе [PolicyElementKey](concurrency-namespace-enums.md).

```
enum WinRTInitializationType;
```

### <a name="values"></a>Значения

|Имя|Описание|
|----------|-----------------|
|`DoNotInitializeWinRT`|Когда приложение выполняется в операционной системе Windows версии 8 и выше, потоки в планировщике не инициализируют среду выполнения Windows.|
|`InitializeWinRTAsMTA`|Когда приложение выполняется в операционной системе Windows версии 8 или выше, каждый поток в планировщике инициализирует среду выполнения Windows и объявляет, что это часть многопотокового подразделения.|

## <a name="requirements"></a>Требования

**Заголовок:** concrt.h

## <a name="see-also"></a>См. также

[Пространство имен concurrency](concurrency-namespace.md)
