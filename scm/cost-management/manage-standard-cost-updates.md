---
title: "Elszámolóár frissítések kezelése"
description: "Elszámolóár-adatok frissítése két különböző megközelítés - egy verziójú megközelítés és a két verziójú megközelítés segítségével kezelhető."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: CostingVersion
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 69992
ms.assetid: 468de7af-c7b5-4345-bd5a-ba3aa5a900cc
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 7e0f0817ff37c82ed98a51f10bcdde7e785a19a3
ms.lasthandoff: 03/31/2017


---

# <a name="manage-standard-cost-updates"></a>Elszámolóár frissítések kezelése

Elszámolóár-adatok frissítése két különböző megközelítés - egy verziójú megközelítés és a két verziójú megközelítés segítségével kezelhető. 

Az „egyverziós” megközelítés egy költségszámítási verziót használ, amely tartalmazza az összes költségrekordot. Ezek a rekordok tartalmazzák az eredeti költségeket és az összes költségfrissítést.
A „kétverziós” megközelítés egy eredeti költségrekordokat tartalmazó és egy második, az összes költségfrissítési rekordot tartalmazó verziót használ. A „kétverziós” megközelítés elsődleges előnye a különálló költségszámítási verzióban lévő költségfrissítések letisztult ábrázolása és követése, az eredeti költségszámítási verziót érintő kihatástól mentesen. A „kétverziós” megközelítés alkalmas a többszörösen növekményes frissítések megkülönböztetésére, amelynél minden egyes növekményes frissítés egy külön költségszámítási verzióval rendelkezik, amely tartalmazza a növekményes költségrekordokat. **Példa** A következő példa bemutatja, hogyan használhatók az egyverziós és kétverziós megközelítések az elszámolóárak frissítésére gyári környezetben. Például olyan frissítések, amelyek új cikkekre vagy a hibajavításokra vonatkoznak. Tegyük fel, hogy egy költségszámítási verzió az aktuális évre vonatkozó elszámolóárakat képviseli. Ennek a verziónak az azonosítója 2016-STD. A 2016-STD verzió tartalmazza az aktuális aktív költségeket az összes cikkre. Tartalmaz továbbá minden kapcsolódó útválasztás költségkategóriák és általános számítási képletek 2016 év elején volt ismert. 2016-STD van az eredeti költségszámítási verzióban.
-   **Egyverziós megközelítés a költségadatok frissítésére** – Az egyverziós megközelítésben az eredeti költségszámítási verzió (2016-STD) tartalmazza az összes költségrekordot. Költség-frissítések 2016-STD kell elszámolni, és vannak beállítva, hogy állapota "függő"állapotúra. A függőben lévő költségeket manuálisan megadott új beszerzett cikkek, vagy helyesbítések megfelelően gyártott cikkhez számítható. Egy verziójú megközelítés használatakor az Anyagjegyzék-számítások nem szükséges tartalék adatforrások mert minden aktív költségek tartalmazzák a költségszámítási verzióban. A függő költségek aktiválása után az eredeti költségszámítási verzió (2016-STD) megint tartalmazni fogja az összes aktuálisan aktív költséget.
-   **Kétverziós megközelítés a költségadatok frissítésénél** − A „kétverziós” megközelítés egy további költségszámítási verziót igényel, amely tartalmazza a költségfrissítéseket. Ennek a verziónak az azonosítója 2016-STD-CHANGES. A költségfrissítések a 2016 STD-módosításokban lesznek rögzítve, és „Folyamatban” értékre vannak állítva. A „kétverziós” megközelítésben a függő költségek Anyagjegyzék-számításai a gyártott cikkek esetében egy tartalék adatforrást igényelnek. Ennek oka az, hogy a 2016 STD-CHANGES további költségszámítási verzió a költségadatoknak csak egy részét tartalmazza. A tartalék kifejezhető aktív költségekként vagy pedig 2016 STD költségszámítási verzióként, mivel mindkettő azonosítja a költségadatot, amikor az nincs benne a 2016-STD-módosításokban. Miután a függő költségek aktívvá válnak, a 2016-STD-CHANGES költségszámítási verzió tartalmazni fogja azokat a jelenlegi aktív költségeket, amelyek a frissítéseket tükrözik, míg az eredeti 2016-STD költségszámítás verzió érintetlenül fog maradni. Két verziós megközelítés használata esetén az eredeti költségszámítási verzió zároló irányelveit be kell állítani a frissítések megakadályozása érdekében. A további költségszámítási verzióhoz is azonos blokkolási szabályokat kell beállítani, a megadott kezdődátum és a frissítések engedélyezése érdekében szelektíven használt gátoló szabályok kivételével. A megadott „kezdő” dátumot frissíteni kell minden egyes változásköteggel, hogy tükrözze az ütemezett aktiválás dátumát.

Ez a példa egy további költségszámítási verzió egész évben 2016 frissítéseinek kezelésére használják. Egynél több további költségszámítási verzió például külön frissítések minden tétel esetében használható. Több mint egy további költségszámítás használata esetén a tartalékot aktív költségekként kell megadni, mert az aktív költségek több költségszámítási verzióban oszlanak el.




