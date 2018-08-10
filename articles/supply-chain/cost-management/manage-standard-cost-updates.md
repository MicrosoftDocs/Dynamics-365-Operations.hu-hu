---
title: "Az elszámolóár frissítéseinek kezelése"
description: "Az elszámolóár adatainak frissítése két eltérő megközelítés használatával kezelhető - ezek az „egyverziós” megközelítés vagy a „kétverziós” megközelítés."
author: AndersGirke
manager: AnnBe
ms.date: 10/24/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CostingVersion
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 69992
ms.assetid: 468de7af-c7b5-4345-bd5a-ba3aa5a900cc
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: b64d9e53736fd3b81ee997ed28ccfa62ed7e9ce6
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="manage-standard-cost-updates"></a>Az elszámolóár frissítéseinek kezelése

[!include [banner](../includes/banner.md)]

Az elszámolóár adatainak frissítése két eltérő megközelítés használatával kezelhető - ezek az „egyverziós” megközelítés vagy a „kétverziós” megközelítés. 

Az „egyverziós” megközelítés egy költségszámítási verziót használ, amely tartalmazza az összes költségrekordot. Ezek a rekordok tartalmazzák az eredeti költségeket és az összes költségfrissítést.

A „kétverziós” megközelítés egy eredeti költségrekordokat tartalmazó és egy második, az összes költségfrissítési rekordot tartalmazó verziót használ. A „kétverziós” megközelítés elsődleges előnye a különálló költségszámítási verzióban lévő költségfrissítések letisztult ábrázolása és követése, az eredeti költségszámítási verziót érintő kihatástól mentesen. A „kétverziós” megközelítés alkalmas a többszörösen növekményes frissítések megkülönböztetésére, amelynél minden egyes növekményes frissítés egy külön költségszámítási verzióval rendelkezik, amely tartalmazza a növekményes költségrekordokat. 

**Példa** 

A következő példa bemutatja, hogyan használhatók az egyverziós és kétverziós megközelítések az elszámolóárak frissítésére gyári környezetben. Például olyan frissítések, amelyek új cikkekre vagy a hibajavításokra vonatkoznak. Tegyük fel, hogy egy költségszámítási verzió az aktuális évre vonatkozó elszámolóárakat képviseli. Ennek a verziónak az azonosítója 2016-STD. A 2016-STD verzió tartalmazza az aktuális aktív költségeket az összes cikkre. Tartalmazza továbbá az összes útvonallal összefüggő költségkategóriát és többletköltség-számítási képletet, amelyek a 2016. év kezdetén ismertek voltak. A 2016-STD az eredeti költségszámítási verzió.

-   **Egyverziós megközelítés a költségadatok frissítésére** – Az egyverziós megközelítésben az eredeti költségszámítási verzió (2016-STD) tartalmazza az összes költségrekordot. A költségfrissítések 2016-STD-be lesznek feljegyezve, és a „Folyamatban” értékre vannak állítva. A függő költségek kézzel is bevihetők az újonnan beszerzett cikkekhez, vagy kiszámíthatók egy gyártott cikkhez, hogy a kiigazításokat visszatükrözzék. Az „egyverziós” megközelítésű anyagjegyzék-számítások nem igényelnek tartalék adatforrást, mert az összes aktív költség a költségszámítási verzióba van belefoglalva. A függő költségek aktiválása után az eredeti költségszámítási verzió (2016-STD) megint tartalmazni fogja az összes aktuálisan aktív költséget.
-   **Kétverziós megközelítés a költségadatok frissítésénél** − A „kétverziós” megközelítés egy további költségszámítási verziót igényel, amely tartalmazza a költségfrissítéseket. Ennek a verziónak az azonosítója 2016-STD-CHANGES. A költségfrissítések 2016-STD-CHANGES-be lesznek feljegyezve, és a „Folyamatban” értékre vannak állítva. A kétverziós megközelítés esetében a gyártott cikkek függő költségeinek anyagjegyzék-számításai tartalék adatforrást igényelnek. Ennek oka az, hogy a 2016 STD-CHANGES további költségszámítási verzió a költségadatoknak csak egy részét tartalmazza. A tartalék kifejezhető aktív költségekként vagy pedig 2016 STD költségszámítási verzióként, mivel mindkettő azonosítja a költségadatot, amikor az nincs benne a 2016-STD-módosításokban. A függő költségek aktiválását követően a 2016 STD-módosítások költségszámítási verzió tartalmazni fogja az aktuális aktív költségeket, amelyek tükrözik a frissítéseket, míg az eredeti 2016-STD költségszámítási verzió változatlan lesz. A „kétverziós” megközelítés használatakor az eredeti költségszámítási verzió gátló szabályait kell beállítani a frissítések megakadályozására. A további költségszámítási verzióhoz is azonos blokkolási szabályokat kell beállítani, a megadott kezdődátum és a frissítések engedélyezése érdekében szelektíven használt gátoló szabályok kivételével. A megadott „kezdő” dátumot frissíteni kell minden egyes változásköteggel, hogy tükrözze az ütemezett aktiválás dátumát.

Ez a példa egy további költségszámítási verziót használt a 2016-os év frissítéseinek kezelésére. Egynél több költségszámítási verzió használható, minden frissítési köteg esetében külön verzióként. Több mint egy további költségszámítás használata esetén a tartalékot aktív költségekként kell megadni, mert az aktív költségek több költségszámítási verzióban oszlanak el.






