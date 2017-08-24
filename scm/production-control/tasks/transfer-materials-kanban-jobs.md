--- 
title: "Anyagok átvitele kanbanfeladatokkal (csak 2016. február)"
description: "Ez az eljárás egy anyagszállításra használt visszavonási kanbanfeladattal foglalkozik."
author: ChristianRytt
manager: AnnBe
ms.date: 02/07/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9b947a02be981155053e33a4ef20e19bf2a194a5
ms.openlocfilehash: 72403aa502cadf2a727bdd67ad8cd612dafd502b
ms.contentlocale: hu-hu
ms.lasthandoff: 07/27/2017

---
# <a name="transfer-materials-with-kanban-jobs-february-2016-only"></a>Anyagok átvitele kanbanfeladatokkal (csak 2016. február)

[!include[task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás egy anyagszállításra használt visszavonási kanbanfeladattal foglalkozik. Ez az eljárás az USMF bemutatócéget használja. Ezt az eljárást a raktári dolgozó használja.


## <a name="display-transfer-jobs"></a>Átviteli feladatok megjelenítése
1. Ugorjon a Gyártásvezérlés > Kanban > Kanbantábla oldalra a szállítási feladatokért.
2. Nyissa meg vagy zárja be a Szűrők szekciót.
    * A Szűrők részben megadhatja, hogy mely munkákat szeretné látni a Termelési folyamat, Tevékenység neve Raktárból és helyből, valamint a Raktárba és helyre szűrők használatával.  
3. A Raktárból mezőbe írja be a „11” értéket.
4. A Helyszínre mezőbe írja be a „12” értéket.

## <a name="start-a-transfer-job"></a>Áthelyezési feladat indítása
1. A listában törölje a sorok esetleges kijelölését.
2. Jelölje ki az 4. sort a listában.
    * Válassza ki az első, Nem tervezett állapotú feladatot. Győződjön meg róla, hogy csak ez a feladat van kiválasztva.  
3. Kattintson a Start elemre.
    * Ne feledje, hogy egy ikon jelzi a feladat megkezdését.  

## <a name="select-a-second-transfer-job-and-change-quantity"></a>Egy második áthelyezési feladat kiválasztása és a mennyiség módosítása
1. Keresse meg és jelölje ki a kívánt rekordot a listán.
    * Több feladatot is kiválaszthat, de egyelőre válassza ki az 5. sort.  
2. Keresse meg és jelölje ki a kívánt rekordot a listán.
    * Győződjön meg róla, hogy csak az előző lépés feladata van kiválasztva. Törölje a többi feladat kiválasztását.  
3. Ne feledje a Feladatmennyiség mezőben megadott értéket, később még szüksége lesz rá
4. Állítsa a Feladatmennyiséget a „30” értékre.
    * Figyelje meg a figyelmeztetést! 30 átvitele nem engedélyezett. A kanbanszabály beállítása szerint csak az eredeti mennyiséget lehet átvinni.  
5. Használja a Feladatmennyiség mezőben korábban megjegyzett értéket.
    * Állítsa a Feladatmennyiséget az előző értékre.  

## <a name="start-the-second-transfer-job"></a>Második áthelyezési feladat elindítása
1. Kattintson a Start elemre.
    * Ez megkezdi az 5. sorban található feladat átvitelét.  

## <a name="complete-both-transfer-jobs"></a>Mindkét áthelyezési feladat befejezése
1. Jelölje ki az 4. sort a listában.
    * Most két átviteli feladat van kiválasztva a 4. és az 5. sorban.  
2. Kattintson a Befejezés gombra.
    * Ez mindkét feladat átvitelét befejezi.  


