---
title: 2.6.5 директива flush | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: a2ec5f74-9c37-424a-8376-47ab4a5829a2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d67453b636d50fcb78092318ebb76f5192817548
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46442738"
---
# <a name="265-flush-directive"></a>2.6.5 Директива flush

**Flush** директивы, явных или подразумеваемых, указывается точка «между потоками» последовательности, по которому необходимо убедиться, что все потоки в группе имеют согласованное представление определенных объектов (указан ниже) в реализации объем памяти. Это означает, что выполнены предыдущие оценки выражения, ссылающиеся на эти объекты, и последующие вычисления еще не начато. Например компиляторы необходимо восстановить значения объектов из регистров в памяти и оборудования может потребоваться очистить буферы записи в память и перезагрузить значений объектов из памяти.

Синтаксис **flush** директива выглядит следующим образом:

```
#pragma omp flush [(variable-list)]  new-line
```

Если объекты, которые требуется синхронизация всех назначается в переменных, а затем эти переменные можно указать в необязательном *списка переменной*. При наличии в указатель *списка переменной*, очищается сам указатель, не объект указателя ссылается.

Объект **flush** директив без *списка переменной* синхронизируется с автоматическую длительность хранения всех общих объектов, кроме недоступные объекты. (Это может оказать большие затраты, чем **flush** с *списка переменной*.) Объект **flush** директив без *списка переменной* подразумевается для следующие директивы:

- `barrier`

- На вход и выход из **критические**

- На вход и выход из `ordered`

- На вход и выход из **параллельных**

- AT выхода из **для**

- AT выхода из **разделы**

- AT выхода из **единый**

- На вход и выход из **параллельных для**

- На вход и выход из **параллельных разделов**

Если не подразумевается директива `nowait` присутствует предложение. Следует отметить, что **flush** директива не подразумевается для любого из следующих:

- При входе **для**

- Запись или выход из **master**

- При входе **разделы**

- При входе **единый**

Ссылка, которая обращается к значению объекта с типом с квалификатором volatile ведет себя так, как если бы **flush** директива, указав этот объект в предыдущей точке последовательности. Ссылка, которая изменяет значение объекта с типом с квалификатором volatile ведет себя так, как если бы **flush** директива, указав этот объект в точку следующей последовательности.

Обратите внимание, что поскольку **flush** директива не поддерживает инструкцию языка C, как часть его синтаксис, существуют некоторые ограничения на его размещения в программе. См. в разделе [приложении C](../../parallel/openmp/c-openmp-c-and-cpp-grammar.md) для формальная грамматика. В примере ниже показаны эти ограничения.

```
/* ERROR - The flush directive cannot be the immediate
*          substatement of an if statement.
*/
if (x!=0)
   #pragma omp flush (x)
...

/* OK - The flush directive is enclosed in a
*      compound statement
*/
if (x!=0) {
   #pragma omp flush (x)
}
```

Ограничения для **flush** директива таковы:

- Переменная, указанная в **flush** директива не должен иметь ссылочный тип.