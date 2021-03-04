---
title: Kanbanfeldolgozási feladatok végrehajtása
description: Ezzel az eljárás a kanbanfeldolgozási feladatok végrehajtására szolgál.
author: ChristianRytt
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanBoardWorkCell, KanbanJobStatusUpdate
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a1c32b577007c400f3528a110436eb97aaabefe2
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4429565"
---
# <a name="execute-kanban-process-jobs"></a>Kanbanfeldolgozási feladatok végrehajtása

[!include [banner](../../includes/banner.md)]

Ezzel az eljárás a kanbanfeldolgozási feladatok végrehajtására szolgál. A program az első feladatot a várt mennyiségi eredménnyel és hibák nélkül végezte el. A második feladat hibákkal fejeződött be. Ez az eljárás az USMF bemutatócéget használja. Ezt az eljárást a gépkezelő használja.


## <a name="select-a-kanban-job"></a>Válasszon ki egy kanban feladatot.
1. Ugorjon a Gyártásvezérlés > Kanban > Kanbantábla feldolgozási feladatokhoz lehetőségre.
2. A Munkacella mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
3. Kattintson az 1250 Erőforráscsoporttal ellátott sorra. Ez végzi el a Feladatok lista szűrését a csak az 1250-es munkacellára vonatkozó feladatok megtekintéséhez.
    * Jelölje be a Tervezett feladat állapotú sort.  

## <a name="complete-a-job-with-expected-quantity"></a>Végezze el a feladatot a várt mennyiséggel
1. Bontsa ki vagy zárja be a Részletek szakaszt.
    * Ez a szakasz a kártyaszámmal, a cikkszámmal, a megrendelt mennyiséggel és a tevékenység nevével kapcsolatos fontos információkat jeleníti meg.  
2. Bontsa ki vagy zárja be a Termelési útmutatások szakaszt.
    * Ez a szakasz a tevékenységre vonatkozó termelési útmutatásokat jeleníti meg. Ezek az utasítások szöveg, kép, rajz és egyéb dokumentum formátumban jelenhetnek meg.  
3. Kattintson a Start elemre.
    * Válasszon ki egy olyan feladatot, amely nem fejeződött be. A feladat állapota mezőben lévő Állapot ikonok használatával tekintse meg a feladat állapotát.      
4. Kattintson a Befejezés gombra.
    * A rendszer a feladatot a várható minőségi eredménnyel fejezte meg.  

## <a name="complete-a-job-with-errors"></a>A feladat hibákkal történő elvégzése
1. Kattintson a Start elemre.
    * A feladat befejezése után a rendszer automatikusan kijelöli a következő feladatot a listában. Ez az oka annak, hogy az Indítás elemre történő kattintás előtt nem kell kiválasztani a feladatot.  
2. A Művelet panelen kattintson a Gyártás elemre.
3. Kattintson a Végrehajtás (részletek) lehetőségre.
4. A listában jelölje meg a kiválasztott sort.
5. Adjon meg egy számot a Hibás mennyiség mezőben.
6. Adjon meg egy számot a Hibátlan mennyiség mezőben.
7. Kattintson az OK gombra.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]