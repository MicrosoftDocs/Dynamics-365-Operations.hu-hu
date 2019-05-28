---
title: A kanbanfeladat eltávolítása az ütemezésből
description: Ez az eljárás a tervezett kanbanfeldolgozási feladatot ütemezésből való eltávolításával foglalkozik, ahol a feladatállapotot Nem tervezettre fordítják vissza.
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanJobSchedulingListPage, SysLookupMultiSelectGrid, KanbanJobStatusUpdate
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b4d994be5c6bb1edc6f0fc64494a19a5babf72ae
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1571974"
---
# <a name="remove-a-kanban-job-from-the-schedule"></a>A kanbanfeladat eltávolítása az ütemezésből

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás a tervezett kanbanfeldolgozási feladatot ütemezésből való eltávolításával foglalkozik, ahol a feladatállapotot Nem tervezettre fordítják vissza. Ez az eljárás az USMF bemutatócéget használja. Ez az eljárás az üzemirányítási felügyelő vagy termeléstervező munkáját segíti.


## <a name="find-a-planned-kanban-job"></a>Keressen egy tervezett kanbanfeladatot
1. Ugorjon a Gyártásvezérlés > Kanban > Kanbanfeladat ütemezése lehetőségre.
2. A Munkacella mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
3. A listában kattintson a kijelölt sorban lévő hivatkozásra.
    * Jelölje ki az 1250 munkacellát.  
4. Kattintson a Kiválasztás lehetőségre.
5. A Feladatállapot megjelenítése mezőben válassza ki az „Ütemezett” lehetőséget.

## <a name="remove-the-planned-kanban-job-from-the-schedule"></a>A tervezett kanbanfeladat eltávolítása az ütemezésből
1. Keresse meg és jelölje ki a kívánt rekordot a listán.
    * Válasszon egy feladatot, amely Tervezett állapotú, például egy feladatot 2012. december 19-ről.  
2. A Művelet panelen kattintson a Terv elemre.
3. Kattintson a Feladatállapot visszaállítása lehetőségre.
4. Kattintson az OK gombra.
    * Az aktuális feladat állapota így „Tervezett” helyett „Nem tervezett” állapotúra vált, és eltűnik a feldolgozási tábláról.   

