---
title: A feldolgozási kanbanfeladat előkészítése, amikor az anyagok nem elérhetők a munkacellához
description: Ez az eljárás a kanbanfeladat folyamatának előkészítését mutatja be, amikor egyes anyagok nem érhetőek el a munkacellához, és így a raktárból kell anyagokat választani.
author: ChristianRytt
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanBoardWorkCell
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: df0396a1d00e61ad82e52fc07779e239cd811ab8
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4994091"
---
# <a name="prepare-a-process-kanban-job-when-materials-are-not-available-for-the-work-cell"></a>A feldolgozási kanbanfeladat előkészítése, amikor az anyagok nem elérhetők a munkacellához

[!include [banner](../../includes/banner.md)]

Ez az eljárás a kanbanfeladat folyamatának előkészítését mutatja be, amikor egyes anyagok nem érhetőek el a munkacellához, és így a raktárból kell anyagokat választani. Az „A feldolgozási kanbanfeladat előkészítése, amikor az anyagok elérhetők” eljárás előfeltétel, ha ilyen eljárást akar létrehozni. Ezt az eljárást a gépkezelő használja. Ez az eljárás az USMF bemutatócéget használja.

1. Ugorjon a Gyártásvezérlés > Kanban > Kanbantábla feldolgozási feladatokhoz lehetőségre.
2. A Munkacella mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
3. A listában kattintson a kijelölt sorban lévő hivatkozásra.
    * Jelölje ki az 1250 munkacellát.  
4. Keresse meg és jelölje ki a kívánt rekordot a listán.
    * Válassza ki a 000356 kanbant.  
5. Keresse meg és jelölje ki a kívánt rekordot a listán.
    * Szüntesse meg a 4. sor kijelölését a listában, jelölje ki a 4. sort, ha nem végezte el az „A feldolgozási kanbanfeladat előkészítése, amikor az anyagok elérhetők” feladatot.  
6. Bontsa ki a Kitárolási lista részt.
    * A Nem található bejegyzés ikon az ellátási állapotnál azt jelzi, hogy a P0002 cikk 48 egyedi egysége hiányzik a munkacellából.  

## <a name="transfer-materials-to-work-cell"></a>Anyagok átvitele a munkacellába
1. Bontsa ki az Átviteli feladatok részt.
2. A Gyorsszűrő használatával szűrjön rá a P0002 értékű Cikkszám mezőkre.
3. Keresse meg és jelölje ki a kívánt rekordot a listán.
4. Kattintson a Start elemre.
    * Az áthelyezés folyamatban.  
5. Kattintson a Befejezés gombra.
    * A P0002 cikk most már elérhető a kanbanfeladat kitárolási listájában. Ez azt jelenti, hogy elkészíthetjük a kanbant a szükséges anyagokkal.  
6. Kattintson az Előkészítés lehetőségre.
    * Figyelje meg, hogy a Feladat állapotának ikonja jelzi, ha a feladat elkészült.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]