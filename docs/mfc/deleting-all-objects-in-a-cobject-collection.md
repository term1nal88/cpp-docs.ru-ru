---
title: Удаление всех объектов из коллекции CObject | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- objects [MFC], deleting in collections
- objects in CObject collections, deleting
- CObject class [MFC], deleting in collection
- collection classes [MFC], deleting all objects
- CObject class collection
- objects in CObject collections
- collection classes [MFC], shared objects
ms.assetid: 81d2c1d5-a0a5-46e1-8ab9-82b45cf7afd2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 986bc24c57f8692bfdd98194b9e58c9cee6817f6
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50067193"
---
# <a name="deleting-all-objects-in-a-cobject-collection"></a>удаление всех объектов из коллекции CObject

В этой статье объясняется, как для удаления всех объектов в коллекции (без удаления самого объекта коллекции).

Чтобы удалить все объекты в коллекцию `CObject`s (или объектов, производных от `CObject`), используется один из способов итерации, описанные в статье [доступ всех членов коллекции](../mfc/accessing-all-members-of-a-collection.md) для удаления каждого объекта в Включите.

> [!CAUTION]
>  Объекты в коллекциях можно использовать совместно. То есть Коллекция хранит указатель на объект, но другие части программы могут также иметь указатели на тот же объект. Будьте внимательны при удалении объекта, который является общим до завершения всех частей с помощью объекта.

В этой статье показано, как удалять объекты в:

- [Список](#_core_to_delete_all_objects_in_a_list_of_pointers_to_cobject)

- [Массив](#_core_to_delete_all_elements_in_an_array)

- [Карты](#_core_to_delete_all_elements_in_a_map)

#### <a name="_core_to_delete_all_objects_in_a_list_of_pointers_to_cobject"></a>  Чтобы удалить все объекты в список указателей на CObject

1. Используйте `GetHeadPosition` и `GetNext` для выполнения итерации по списку.

1. Используйте **удалить** оператор для удаления каждого объекта, в котором он находится в итерации.

1. Вызовите `RemoveAll` функцию для удаления всех элементов в списке, после удаления объектов, связанных с этими элементами.

В следующем примере показано, как удаление всех объектов из списка `CPerson` объектов. Каждый объект в списке является указатель на `CPerson` объект, который изначально был выделен в куче.

[!code-cpp[NVC_MFCCollections#17](../mfc/codesnippet/cpp/deleting-all-objects-in-a-cobject-collection_1.cpp)]

Последний вызов функции, `RemoveAll`, является функцией-членом списка, удаляет все элементы из списка. Функция-член `RemoveAt` Удаляет один элемент.

Обратите внимание на различие между удалением объекта элемента и удаления самого элемента. Удаление элемента из списка просто удаляет ссылку на объект списка. Объект по-прежнему существует в памяти. При удалении объекта, он прекращает свое существование, и освобождения памяти. Таким образом очень важно удалить элемент сразу после удаления этого элемента объекта, чтобы список не будет попытка получить доступ к объектам, которые больше не существуют.

#### <a name="_core_to_delete_all_elements_in_an_array"></a>  Чтобы удалить все элементы в массиве

1. Используйте `GetSize` и целочисленных значений индекс для перебора массива.

1. Используйте **удалить** оператор для удаления каждого элемента, в котором он находится в итерации.

1. Вызовите `RemoveAll` функции, чтобы удалить все элементы из массива, после они были удалены.

   Удаление всех элементов в массиве код выглядит следующим образом:

   [!code-cpp[NVC_MFCCollections#18](../mfc/codesnippet/cpp/deleting-all-objects-in-a-cobject-collection_2.cpp)]

В приведенном выше примере список так же, как можно `RemoveAll` для удаления всех элементов в массиве или `RemoveAt` для удаления отдельных элементов.

#### <a name="_core_to_delete_all_elements_in_a_map"></a> Для удаления всех элементов в сопоставлении

1. Используйте `GetStartPosition` и `GetNextAssoc` для перебора массива.

1. Используйте **удалить** оператор удалить ключ и/или значение для каждого элемента карты, так как встречается в итерации.

1. Вызовите `RemoveAll` функцию для удаления всех элементов из сопоставления, после они были удалены.

   Код для удаления всех элементов `CMap` коллекции выглядит следующим образом. Каждый элемент в сопоставлении имеет строку в качестве ключа и `CPerson` объекта (производного от `CObject`) как значение.

   [!code-cpp[NVC_MFCCollections#19](../mfc/codesnippet/cpp/deleting-all-objects-in-a-cobject-collection_3.cpp)]

Можно вызвать `RemoveAll` для удаления всех элементов в сопоставлении или `RemoveKey` для удаления отдельных элемента с указанным ключом.

## <a name="see-also"></a>См. также

[Доступ ко всем членам коллекции](../mfc/accessing-all-members-of-a-collection.md)

