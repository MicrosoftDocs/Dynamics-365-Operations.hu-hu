---
title: Kanbanszabályok módosítása egy feldolgozási feladat számára
description: Ez az eljárás egy adott kanbanhoz használt kanbanszabály módosítását tekinti át.
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanRules, KanbanRuleDuplicate, KanbanJobSchedulingListPage, LeanRuleReassignmentWizard, KanbanReassignRuleLookup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 38d9ff0a7d6aeb0a589fd6b9ab34b818c46644cc
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "314946"
---
# <a name="change-kanban-rules-for-a-process-job"></a>Kanbanszabályok módosítása egy feldolgozási feladat számára

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás egy adott kanbanhoz használt kanbanszabály módosítását tekinti át. Ez akkor hasznos, ha terhelési erőforrást szintez, vagy lebontás esetén. Ez az eljárás az USMF bemutatócéget használja. Ez az eljárás a Tervező számára hasznos, aki a lean manufacturing vállalatnál dolgozik, és az érték-előállítási folyamatért felelős.


## <a name="copy-kanban-rule"></a>Kanbanszabály másolása
1. Ugorjon a Kanbanszabályokhoz.
2. Keresse meg és jelölje ki a kívánt rekordot a listán.
    * Válassza ki a 000022 esemény-kanbanszabályt az L0001 termékhez.  
3. Kattintson a Kanbanszabály másolása lehetőségre.
4. Kattintson az OK gombra.

## <a name="change-kanban-rule"></a>Kanbanszabály módosítása
1. Zárja be a lapot.
2. Ugrás ide: Kanbanfeladat ütemezése.
3. A listában jelölje meg a kiválasztott sort.
    * Válassza ki a Kanban 000177 sorát.  
4. Kattintson az Alternatív kanbanszabály használata elemre.
5. Kattintson a Tovább gombra.
6. A Kanbanszabály mezőben adjon meg vagy válasszon ki egy értéket.
    * Válassza ki a korábban létrehozott kanbanszabályt. Ez a legnagyobb számmal rendelkező kanbanszabály.  
7. Kattintson a Finish gombra.
    * Most a kanbanfeladat már egy másik kanbanszabályt használ. Ez hasznos lehet a terhelési munkacellák szintezéséhez.  

