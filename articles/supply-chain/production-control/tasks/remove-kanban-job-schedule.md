---
title: A kanbanfeladat eltávolítása az ütemezésből
description: Ez az eljárás a tervezett kanbanfeldolgozási feladatot ütemezésből való eltávolításával foglalkozik, ahol a feladatállapotot Nem tervezettre fordítják vissza.
author: ChristianRytt
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanJobSchedulingListPage, SysLookupMultiSelectGrid, KanbanJobStatusUpdate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: eeedfad5f294f73097fc1b6a973d63125df72209227fc06470663665961af2d4
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6756919"
---
# <a name="remove-a-kanban-job-from-the-schedule"></a>A kanbanfeladat eltávolítása az ütemezésből

[!include [banner](../../includes/banner.md)]

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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]