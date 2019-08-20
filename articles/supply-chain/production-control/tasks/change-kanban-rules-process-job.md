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
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c036f6aad79e33df6009913d1e21ff6176f22593
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/01/2019
ms.locfileid: "1843793"
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

