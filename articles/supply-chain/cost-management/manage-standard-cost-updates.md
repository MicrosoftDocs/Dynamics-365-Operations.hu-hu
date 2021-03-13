---
title: Az elszámolóár frissítéseinek kezelése
description: Az elszámolóár adatainak frissítése két eltérő megközelítés használatával kezelhető - ezek az „egyverziós” megközelítés vagy a „kétverziós” megközelítés.
author: AndersGirke
manager: tfehr
ms.date: 01/15/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CostingVersion, InventItemPrice
audience: Application User
ms.reviewer: kamaybac
ms.custom: 69992
ms.assetid: 468de7af-c7b5-4345-bd5a-ba3aa5a900cc
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 166d12d707deabc59f7613a5016851b30fcc42d8
ms.sourcegitcommit: 41baf654a2553cfe5c715feb9cc03e48cfc12598
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/19/2021
ms.locfileid: "5024670"
---
# <a name="manage-standard-cost-updates"></a>Az elszámolóár frissítéseinek kezelése

[!include [banner](../includes/banner.md)]

Az elszámolóár adatainak frissítése két eltérő megközelítés használatával kezelhető - ezek az „egyverziós” megközelítés vagy a „kétverziós” megközelítés.

Az „egyverziós” megközelítés egy költségszámítási verziót használ, amely tartalmazza az összes költségrekordot. Ezek a rekordok tartalmazzák az eredeti költségeket és az összes költségfrissítést.

A „kétverziós” megközelítés egy eredeti költségrekordokat tartalmazó és egy második, az összes költségfrissítési rekordot tartalmazó verziót használ. A „kétverziós” megközelítés elsődleges előnye a különálló költségszámítási verzióban lévő költségfrissítések letisztult ábrázolása és követése, az eredeti költségszámítási verziót érintő kihatástól mentesen. A „kétverziós” megközelítés alkalmas a többszörösen növekményes frissítések megkülönböztetésére, amelynél minden egyes növekményes frissítés egy külön költségszámítási verzióval rendelkezik, amely tartalmazza a növekményes költségrekordokat.

## <a name="example"></a>Példa

A következő példa bemutatja, hogyan használhatók az egyverziós és kétverziós megközelítések az elszámolóárak frissítésére gyári környezetben. Például olyan frissítések, amelyek új cikkekre vagy a hibajavításokra vonatkoznak. Tegyük fel, hogy egy költségszámítási verzió az aktuális évre vonatkozó elszámolóárakat képviseli. Ennek a verziónak az azonosítója 2020-STD. A 2020-STD verzió tartalmazza az aktuális aktív költségeket az összes cikkre. Tartalmazza továbbá az összes útvonallal összefüggő költségkategóriát és többletköltség-számítási képletet, amelyek a 2020. év kezdetén ismertek voltak. A 2020-STD az eredeti költségszámítási verzió.

- **Egyverziós megközelítés a költségadatok frissítésére** – Az egyverziós megközelítésben az eredeti költségszámítási verzió (2020-STD) tartalmazza az összes költségrekordot. A költségfrissítések 2020-STD-be lesznek feljegyezve, és a Folyamatban értékre vannak állítva. A függő költségek kézzel is bevihetők az újonnan beszerzett cikkekhez, vagy kiszámíthatók egy gyártott cikkhez, hogy a kiigazításokat visszatükrözzék. Az „egyverziós” megközelítésű anyagjegyzék-számítások nem igényelnek tartalék adatforrást, mert az összes aktív költség a költségszámítási verzióba van belefoglalva. A függő költségek aktiválása után az eredeti költségszámítási verzió (2020-STD) megint tartalmazni fogja az összes aktuálisan aktív költséget.
- **Kétverziós megközelítés a költségadatok frissítésénél** − A „kétverziós” megközelítés egy további költségszámítási verziót igényel, amely tartalmazza a költségfrissítéseket. Ennek a verziónak az azonosítója 2020-STD-CHANGES. A költségfrissítések 2020-STD-CHANGES-be lesznek feljegyezve, és a Folyamatban értékre vannak állítva. A kétverziós megközelítés esetében a gyártott cikkek függő költségeinek anyagjegyzék-számításai tartalék adatforrást igényelnek. Ennek oka az, hogy a 2020 STD-CHANGES további költségszámítási verzió a költségadatoknak csak egy részét tartalmazza. A tartalék kifejezhető aktív költségekként vagy pedig 2020 STD költségszámítási verzióként, mivel mindkettő azonosítja a költségadatot, amikor az nincs benne a 2020-STD-módosításokban. A függő költségek aktiválását követően a 2020 STD-módosítások költségszámítási verzió tartalmazni fogja az aktuális aktív költségeket, amelyek tükrözik a frissítéseket, míg az eredeti 2020-STD költségszámítási verzió változatlan marad. A „kétverziós” megközelítés használatakor az eredeti költségszámítási verzió gátló szabályait kell beállítani a frissítések megakadályozására. A további költségszámítási verzióhoz is azonos blokkolási szabályokat kell beállítani, a megadott kezdődátum és a frissítések engedélyezése érdekében szelektíven használt gátoló szabályok kivételével. A megadott „kezdő” dátumot frissíteni kell minden egyes változásköteggel, hogy tükrözze az ütemezett aktiválás dátumát.

Ez a példa egy további költségszámítási verziót használt a 2020-os év frissítéseinek kezelésére. Egynél több költségszámítási verzió használható, minden frissítési köteg esetében külön verzióként. Több mint egy további költségszámítás használata esetén a tartalékot aktív költségekként kell megadni, mert az aktív költségek több költségszámítási verzióban oszlanak el.

## <a name="financial-dimensions-for-the-standard-cost-revaluation"></a>Az elszámolóár átértékelésének pénzügyi dimenziói

Új elszámolóár aktiválása általában átértékelési a tényleges készlet értékét az elszámolóáras átértékelési tranzakciók alapján. A cikk pénzügyi dimenziói általában fel vannak adva a tranzakciókba. Ha azonban szabályozni szeretné, hogy a pénzügyi dimenziók feladása miként és hogyan történjen, a [funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) segítségével bekapcsolhatja *Az alapértelmezett pénzügyi dimenziók lehetőségei a készlet elszámolóárának átértékeléséhez* nevű funkciót. A funkció engedélyezése után kattintson a **Költségkezelés > Készletkönyvelési irányelvek beállítása > Paraméterek** parancsra, és állítsa a **Pénzügyi dimenziók eredete** új legördülő listát a következő értékek egyikére:

- **Nincs** – Az újraértékelési tranzakciókra nem lesznek pénzügyi dimenziók feladva. Ha a számlastruktúrája szükséges pénzügyi dimenzió, az átértékelési folyamat továbbra is fut, de pénzügyi dimenziók nélküli könyvelési tételeket hoz létre. Ebben az esetben a felhasználók először figyelmeztető üzenetet kapnak, hogy szükség esetén visszavonják az átértékelést.
- **Tábla** – A cikk pénzügyi dimenziói általában fel vannak adva az átértékelési tranzakciókba. Ez az alapértelmezett beállítás, és összhangban van az eredeti rendszer működésmóddal anélkül, hogy bekapcsolná *Az alapértelmezett pénzügyi dimenziók lehetőségei a készlet elszámolóárának átértékeléséhez* funkciót.
- **Feladás** – A Feladás opció azt jelenti, hogy az átértékelt tranzakció pénzügyi dimenziói lesznek feladva átértékelési tranzakcióra. Alapértelmezés szerint az eredeti tranzakció készletszámlájának pénzügyi dimenzióit fogja használni mind a készletszámla, mind az átértékelési számla számára.
