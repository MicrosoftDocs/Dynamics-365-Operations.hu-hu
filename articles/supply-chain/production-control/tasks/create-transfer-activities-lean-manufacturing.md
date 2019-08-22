---
title: Lean manufacturing gyártási átviteli tevékenységek létrehozása
description: Hozzon létre átmozgatási tevékenységet lean manufacturinghez.
author: cvocph
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LeanProductionFlow, PlanActivity, PlanActivityWizard, LeanWorkCellLookup, InventLocationIdLookup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 04cb0afa74cb95acf4007e9292f9fb88d4c86f87
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/01/2019
ms.locfileid: "1837734"
---
# <a name="create-transfer-activities-for-lean-manufacturing"></a>Lean manufacturing gyártási átviteli tevékenységek létrehozása

[!include [task guide banner](../../includes/task-guide-banner.md)]

Hozzon létre átmozgatási tevékenységet lean manufacturinghez. 

Előfeltételek: 

1. Létre kell hozni a termelési folyamatot és a nem aktív verziót.

2. Létre kell hozni a kiindulási és a célraktár helyét. A feltöltő vagy a feltöltött munkacellát is létre lehet hozni.


## <a name="find-the-production-flow-version"></a>Termelési folyamat verziójának megkeresése
1. Ugrás a Gyártásvezérléshez > Beállítás > Lean típusú termelési folyamat > Termelési folyamatok lehetőségre.
2. Keresse meg és jelölje ki a kívánt rekordot a listán.
    * Vegye figyelembe, hogy a termelési folyamatnak verzióval kell rendelkeznie a várlat állapotban.  
3. A listában kattintson a kijelölt sorban lévő hivatkozásra.

## <a name="create-a-new-activity"></a>Új tevékenység létrehozása
1. Kattintson a Tevékenységek lehetőségre.
    * Győződjön meg arról, hogy a kiválasztott termelési folyamat rendelkezik vázlatverzióval, és válassza ki azt a verziót.  
2. Kattintson az Új tervezett tevékenység létrehozása lehetőségre.
3. Kattintson a Tovább gombra.
4. Írjon be egy értéket a Név mezőbe.
5. A Tevékenységtípus mezőben válassza ki az „Átmozgatás” lehetőséget.
6. Adjon meg egy számot az Folyamatmennyiség mezőben.
7. Kattintson a Tovább gombra.

## <a name="select-the-work-cells"></a>Munkacellák kiválasztása
1. A Feltöltés mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
    * Ha a munkacella kimeneti helyét az átmozgatási tevékenység forráshelyéül szeretné használni, válasszon ki egy munkacellát. Ugyanezt feltöltött munkacellával is megteheti, amely így beállítja az átmozgatási tevékenység célhelyét.  
2. A listában kattintson a kijelölt sorban lévő hivatkozásra.

## <a name="define-the-inventory-updates"></a>A készletfrissítések meghatározása
1. Válasszon egy lehetőséget a Terméktípus mezőben.
    * Megjegyzés: Az átmozgatás nem változtatja meg a termék típusát. Átmozgathat kész és félkész termékeket (átmozgatás egy termelési folyamat két tevékenysége és esetleg egy kanbanfolyamat között).     Kész termékek átmozgatása esetén meghatározhatja, hogy a kitárolás és az eredmények fogadása készlettranzakcióban történjen.  

## <a name="define-the-transfer-locations"></a>Átmozgatás helyének meghatározása
1. Kattintson a Tovább gombra.
2. A Raktár mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
3. A kívánt rekord megkeresése és kijelölése a listán
4. A listában kattintson a kijelölt sorban lévő hivatkozásra.
5. A Hely mezőben kattintson a legördülő gombra a keresőlista megnyitásához.
6. A listában kattintson a kijelölt sorban lévő hivatkozásra.
7. A Szállította mezőben válassza ki a „Szállító” lehetőséget.
    * A lehetőségek a következők: Szállító – a szállítási raktárt üzemeltető szervezet, Címzett – a fogadó raktárt üzemeltető szervezet, Szállítmányozó – harmadik fél szállító. Ha az üzemeltető szervezet szállító, az átmozgatási tevékenység alvállalkozói szerződést igényel.  
8. Kattintson a Tovább gombra.

## <a name="define-the-activity-times"></a>A tevékenységi idők meghatározása
1. Keresse meg és jelölje ki a kívánt rekordot a listán.
    * A Futásidő meghatározását meg kell adni. A Futásidő a költség és a kanbanfeladatok átfutási idejének kiszámítására szolgál. A futásidő nem a kapacitásterhelés és a felhasználás kiszámítására szolgál, ezt a ciklusidő számítja ki a termelésifolyamat-verzió feladat segítségével.  
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

