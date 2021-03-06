---
title: 1.3 модель выполнения | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 85ae8bc4-5bf0-45e0-a45f-02de9adaf716
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c284563a47d21abc9a1dacf045238449d64205d5
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46394014"
---
# <a name="13-execution-model"></a>1.3 Модель выполнения

OpenMP использует модель ветвления слияния параллельного выполнения. Несмотря на то, что эта модель ветвления соединения, можно использовать для решения различных проблем, отчасти предназначена для крупных приложений на основе массива. OpenMP предназначен для поддержки программ, которые будут выполняться правильно оба как параллельных программ (нескольких потоков выполнения и полная библиотека поддержки OpenMP) и программ последовательных (директивы игнорируются и простую библиотеку заглушки OpenMP). Тем не менее возможно и разрешено разработать программу, которая работает неправильно последовательного исполнения. Кроме того различные степени параллелизма может привести различных числовых результатов из-за изменений в ассоциации числовых операций. Например сокращения последовательной сложения может иметь другой шаблон Добавление ассоциации, чем параллельной редукции. Эти различные ассоциации может повлиять на результаты сложения с плавающей запятой.

Программа, написанная с помощью API OpenMP C/C++ начинает выполнение как один поток выполнения, вызываемую *освоить потоке*. Главный поток выполняет в область с последовательной, пока не будет обнаружен первый параллельной конструкции. В API OpenMP C/C++ **параллельных** директива составляет параллельной конструкции. При обнаружении параллельной конструкции, основной поток создает группу потоков, а master становится основной группы. Каждый поток в группе выполняет инструкции в динамических степень параллельной области, за исключением конструкции совместной работы. Конструкции совместной работы, которые необходимо получить всем потокам в группе в том же порядке, а операторы внутри блоку структурированных выполняются по одному или нескольким из потоков. Барьер, который содержится в разрешении в конце конструкции совместной работы без `nowait` предложение выполняется всеми потоками в группе.

Если поток изменяет общий объект, оно влияет не только среды выполнения, но также те из других потоков в программе. Изменение гарантированно завершенной, с точки зрения одного из других потоков, на следующем этапе последовательности (как определено в базовый язык), только в том случае, если объект объявляется как volatile. В противном случае изменение гарантированно завершения после сначала изменение потока, и затем (или одновременно) потоков, сталкиваются **flush** директивы, указывающий объект (явно или неявно). Обратите внимание, что при **flush** директивы, которые неявно выражены другие директивы OpenMP не достаточно обеспечить нужный порядок побочные эффекты, это программист должен предоставить дополнительные, явные  **Очистить** директивы.

После завершения параллельной конструкции потоки в группе синхронизации в неявных барьера, и только главный поток продолжает выполнение. Любое количество параллельные конструкции можно указать в одной программе. Таким образом программа может создать вилку и присоединить много раз во время выполнения.

API OpenMP C/C++ позволяют программистам использовать директивы в функции, вызываемые из параллельные конструкции. Директивы, которые не отображаются в лексической области параллельные конструкции, но могут находиться в области динамической называются *потерянные* директивы. Потерянные директивы предоставляет программистам возможность выполнения основной части своих программах параллельно с выводом минимального объема изменений для последовательной программы. Благодаря этой функции пользователей можно создавать параллельные конструкции на верхних уровнях дерева вызовов программы, а использовать директивы для управления выполнением в любом из вызываемые функции.

Несинхронизированные вызовы для языков C и C++ выходных данных функции, записывающие в тот же файл может привести к выходных данных, в котором данные, записанные разными потоками отображается в порядке недетерминированные. Аналогичным образом несинхронизированных вызовы входных данных функции, выполняющие чтение из одного файла может читать данные в недетерминированные заказа. Несинхронизированные использования операций ввода-вывода, таким образом, чтобы каждый поток обращается к другой файл, имела тот же результат, как последовательное выполнение функций ввода-вывода.