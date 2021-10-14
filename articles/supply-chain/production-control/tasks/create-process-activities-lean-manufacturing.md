---
title: Lean manufacturing gyártási folyamattevékenységek létrehozása
description: Hozzon létre folyamattevékenységet a lean manufacturing számára.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LeanProductionFlow, PlanActivity, PlanActivityWizard, LeanWorkCellLookup, InventLocationIdLookup, PlanActivityDetails, KanbanJobPickingListPart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 214e54cc93379948e4c25b3b28d835bbbbd40b72
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/29/2021
ms.locfileid: "7570153"
---
# <a name="create-process-activities-for-lean-manufacturing"></a>Lean manufacturing gyártási folyamattevékenységek létrehozása

[!include [banner](../../includes/banner.md)]

Hozzon létre folyamattevékenységet a lean manufacturing számára. 

Előfeltételek: 

1. Létre kell hozni a termelési folyamatot és a nem aktív verziót.

2. Munkacellát kell létrehozni.


## <a name="find-the-production-flow-version"></a>Termelési folyamat verziójának megkeresése
1. Ugrás a Gyártásvezérléshez > Beállítás > Lean típusú termelési folyamat > Termelési folyamatok lehetőségre.
2. Keresse meg és jelölje ki a kívánt rekordot a listán.
3. A listában kattintson a kijelölt sorban lévő hivatkozásra.

## <a name="create-a-new-activity"></a>Új tevékenység létrehozása
1. Kattintson a Tevékenységek lehetőségre.
    * Győződjön meg arról, hogy a kiválasztott termelési folyamat rendelkezik vázlatverzióval, és válassza ki azt a verziót.  
2. Kattintson az Új tervezett tevékenység létrehozása lehetőségre.
3. Kattintson a Tovább gombra.
4. Írjon be egy értéket a Név mezőbe.
5. Írjon be egy értéket a Név mezőbe.
    * Vegye figyelembe, hogy az adott termelési folyamat nevének egyedinek kell lennie minden verzióban.  
6. Adjon meg egy számot az Folyamatmennyiség mezőben.
    * Vegye figyelembe, hogy a feldolgozott feladatmennyiségtől függetlenül a munkaköltség kiszámításakor ez a feladatonkénti minimum mennyiség. Ha a feladatmennyiségek eltérnek ettől a mennyiségtől, munkaköltség-eltérés keletkezik.  
7. Kattintson a Tovább gombra.

## <a name="select-the-work-cell"></a>A munkacella kiválasztása
1. A Munkacella mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
2. A listában kattintson a kijelölt sorban lévő hivatkozásra.

## <a name="define-the-inventory-updates"></a>A készletfrissítések meghatározása
1. Jelölje be vagy törölje a jelet az Aktuális bevételezés frissítése jelölőnégyzetből.
    * Ha az Elérhető frissítése = Nem, úgy is meghatározhatja a tevékenységet, hogy félkész terméket kapjon (a művelet nem éri el a következő anyagjegyzékszintet).    Félkész termékek felhasználását is kiválaszthatja.  

## <a name="define-the-picking-activities"></a>A kitárolási tevékenységek meghatározása
1. Kattintson a Tovább gombra.
2. A listában jelölje meg a kiválasztott sort.
    * Az alapértelmezett kitárolási tevékenység a kiválasztott munkacella bemeneti helyére kerül létrehozásra.  
3. Kattintson a Hozzáadás gombra.
    * Létrehozhat további kitárolási tevékenységet az egyes termékekre, amelyek nincsenek előkészítve a munkacella bemeneti tevékenységénél.  
4. Keresse meg és jelölje ki a kívánt rekordot a listán.
5. A cikkmezőbe írjon egy értéket.
6. A Raktár mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
    * Ezzel a meghatározással a tevékenység során felhasznált anyagok az alapértelmezett bemeneti raktárból és helyről származnak, kivéve a második kitárolási tevékenységben meghatározott cikk. Ez a cikk egy másik raktárból és helyről kerül kitárolásra.  
7. Keresse meg és jelölje ki a kívánt rekordot a listán.
8. A listában kattintson a kijelölt sorban lévő hivatkozásra.
9. Jelölje be vagy törölje a jelet a Selejt regisztrálása jelölőnégyzetből.
10. Kattintson a Tovább gombra.

## <a name="define-the-activity-times"></a>A tevékenységi idők meghatározása
1. Keresse meg és jelölje ki a kívánt rekordot a listán.
    * A Futásidő meghatározását meg kell adni. A Futásidő a költségek és a kanbanfeladatok átfutási idejének kiszámítására szolgál. A futásidő nem a kapacitásterhelés és a felhasználás kiszámítására szolgál, ezt a ciklusidő számítja ki a termelésifolyamat-verzió feladat segítségével.  
2. Adjon meg egy számot az Idő mezőben.
3. Írjon be egy értéket a Mértékegység mezőbe.
4. Válasszon ki egy időegységet.
5. Adjon meg egy számot a Mennyiségenként mezőben.
6. Keresse meg és jelölje ki a kívánt rekordot a listán.
    * A várakozási idő nem kötelező.  
7. Adjon meg egy számot az Idő mezőben.
8. Írjon be egy értéket a Mértékegység mezőbe.
9. Válasszon ki egy időegységet.
10. Adjon meg egy számot a Mennyiségenként mezőben.
11. Kattintson a Tovább gombra.
12. Kattintson a Finish gombra.
13. Zárja be a lapot.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]