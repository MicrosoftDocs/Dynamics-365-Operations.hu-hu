---
title: "Az elszámolóár frissítéseinek kezelése"
description: "Az elszámolóár adatainak frissítése két eltérő megközelítés használatával kezelhető - ezek az „egyverziós” megközelítés és a „kétverziós” megközelítés."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CostingVersion
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 69992
ms.assetid: 468de7af-c7b5-4345-bd5a-ba3aa5a900cc
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: d1d498b1a843415e106c90330dd661b78bc2865e
ms.contentlocale: hu-hu
ms.lasthandoff: 05/25/2017

---

# <a name="manage-standard-cost-updates"></a>Az elszámolóár frissítéseinek kezelése

[!include[banner](../includes/banner.md)]


Az elszámolóár adatainak frissítése két eltérő megközelítés használatával kezelhető - ezek az „egyverziós” megközelítés és a „kétverziós” megközelítés. 

Az „egyverziós” megközelítés egy költségszámítási verziót használ, amely tartalmazza az összes költségrekordot. Ezek a rekordok tartalmazzák az eredeti költségeket és az összes költségfrissítést.
A „kétverziós” megközelítés egy eredeti költségrekordokat tartalmazó és egy második, az összes költségfrissítési rekordot tartalmazó verziót használ. A „kétverziós” megközelítés elsődleges előnye a különálló költségszámítási verzióban lévő költségfrissítések letisztult ábrázolása és követése, az eredeti költségszámítási verziót érintő kihatástól mentesen. A „kétverziós” megközelítés alkalmas a többszörösen növekményes frissítések megkülönböztetésére, amelynél minden egyes növekményes frissítés egy külön költségszámítási verzióval rendelkezik, amely tartalmazza a növekményes költségrekordokat. **Példa** A következő példa bemutatja, hogyan használhatók az egyverziós és kétverziós megközelítések az elszámolóárak frissítésére gyári környezetben. Például olyan frissítések, amelyek új cikkekre vagy a hibajavításokra vonatkoznak. Tegyük fel, hogy egy költségszámítási verzió az aktuális évre vonatkozó elszámolóárakat képviseli. Ennek a verziónak az azonosítója 2016-STD. A 2016-STD verzió tartalmazza az aktuális aktív költségeket az összes cikkre. Tartalmazza továbbá az összes útvonallal összefüggő költségkategóriát és többletköltség-számítási képletet, amelyek a 2016. év kezdetén ismertek voltak. A 2016-STD az eredeti költségszámítási verzió.
-   **Egyverziós megközelítés a költségadatok frissítésére** – Az egyverziós megközelítésben az eredeti költségszámítási verzió (2016-STD) tartalmazza az összes költségrekordot. A költségfrissítések 2016-STD-be lesznek feljegyezve, és a „Folyamatban” értékre vannak állítva. A függő költségeket manuálisan lehet megadni az újonnan beszerzett cikkekhez, vagy ki lehet őket számolni egy gyártott cikk esetében, hogy tükrözzék a javításokat. Az „egyverziós” megközelítés használata esetén az Anyagjegyzék-számítások nem igényelnek tartalék adatforrást, mert az összes aktív költség szerepel a költségszámítási verzióban. A függő költségek aktiválása után az eredeti költségszámítási verzió (2016-STD) megint tartalmazni fogja az összes aktuálisan aktív költséget.
-   **Kétverziós megközelítés a költségadatok frissítésénél** − A „kétverziós” megközelítés egy további költségszámítási verziót igényel, amely tartalmazza a költségfrissítéseket. Ennek a verziónak az azonosítója 2016-STD-CHANGES. A költségfrissítések a 2016 STD-módosításokban lesznek rögzítve, és „Folyamatban” értékre vannak állítva. A „kétverziós” megközelítésben a függő költségek Anyagjegyzék-számításai a gyártott cikkek esetében egy tartalék adatforrást igényelnek. Ennek oka az, hogy a 2016 STD-CHANGES további költségszámítási verzió a költségadatoknak csak egy részét tartalmazza. A tartalék kifejezhető aktív költségekként vagy pedig 2016 STD költségszámítási verzióként, mivel mindkettő azonosítja a költségadatot, amikor az nincs benne a 2016-STD-módosításokban. Miután a függő költségek aktívvá válnak, a 2016-STD-CHANGES költségszámítási verzió tartalmazni fogja azokat a jelenlegi aktív költségeket, amelyek a frissítéseket tükrözik, míg az eredeti 2016-STD költségszámítás verzió érintetlenül fog maradni. Két verziós megközelítés használata esetén az eredeti költségszámítási verzió zároló irányelveit be kell állítani a frissítések megakadályozása érdekében. A további költségszámítási verzióhoz is azonos blokkolási szabályokat kell beállítani, a megadott kezdődátum és a frissítések engedélyezése érdekében szelektíven használt gátoló szabályok kivételével. A megadott „kezdő” dátumot frissíteni kell minden egyes változásköteggel, hogy tükrözze az ütemezett aktiválás dátumát.

Ez a példa egy további költségszámítási verziót használt a 2016-os év frissítéseinek kezelésére. Egynél több költségszámítási verzió használható, minden frissítési köteg esetében külön verzióként. Több mint egy további költségszámítás használata esetén a tartalékot aktív költségekként kell megadni, mert az aktív költségek több költségszámítási verzióban oszlanak el.






