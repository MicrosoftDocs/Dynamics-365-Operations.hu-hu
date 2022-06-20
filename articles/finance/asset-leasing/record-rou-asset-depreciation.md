---
title: Használatijog-eszköz értékcsökkenésének rögzítése (előzetes verzió)
description: Ez a cikk bemutatja, hogyan lehet naplóbejegyzést létrehozni a szervezet mérlegében elismert bérleti bérletek amortizációja során.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeaseAssetSchedule
audience: Application User
ms.reviewer: kfend
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 93e521cf409af4c01d625f27bdd7a7564e471bd9
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8903276"
---
# <a name="record-right-of-use-asset-depreciation-preview"></a>Használatijog-eszköz értékcsökkenésének rögzítése (előzetes verzió)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]


A szervezet mérlegében elismert lízingek esetében a használatijog-eszközt (ROU) havi rendszerességgel kell elszámolni. Ez a cikk bemutatja, hogyan lehet létrehozni a naplóbejegyzést az amortizációhoz. Az amortizáció megterheli a költség főkönyvi számlát, és jóváírja a halmozott értékcsökkenési főkönyvi számlát a feladási profil és a lízingtípus beállítása alapján. Ezek a bejegyzések minden lízinghez létrehozhatók, vagy több lízinghez is létrehozhatók a kötegnapló funkció használatával.

## <a name="asset-depreciation-schedule"></a>Eszköz-értékcsökkenési ütemezés

1. A **Lízing összegzése** lapon válasszon ki egy lízinget. Ezután válassza a **Könyvek \> Eszköz értékcsökkenési ütemezése** lehetőséget az **Eszköz értékcsökkenési ütemezése** lap megnyitásához.

    A ROU-eszköz értékcsökkenési költség naplóbejegyzése az **Értékcsökkenési költség** oszlopban szereplő összegen alapul. A standard [megfelelés könyvelésére vonatkozó útmutatásra vonatkozó példát a jelen cikk későbbi, a ROU tárgyieszköz-amortizációs](#calculation-of-rou-asset-amortization-expense-for-finance-leases) költségének kiszámítása című részében olvashatja.
    
2. Jelölje ki az értékcsökkenési időszakot, majd válassza a **Napló létrehozása** lehetőséget. Megjelenik egy üzenet arról szólt, hogy létrehozták az értékcsökkenés rögzítésére használt naplót.
3. Válassza a **Naplók \> Eszközlízing-naplók** lehetőséget az **Eszközlízing napló** lap megnyitásához, ahol megtekintheti a létrehozott értékcsökkenési költségnapló-bejegyzést.

   A rendszer bizonyos pénzügyi mezőket zárolja a szerkesztéstől, hogy megakadályozza a tranzakciók és az ütemtervek közötti eltéréseket. Néhány zárolt mező: **Számla**, **Összegek**, **Pénzügyi dimenziók**, **Pénznem** és **Tranzakciótípus**. Ezenkívül nem lesz lehetősége naplóbejegyzési sorokat hozzáadni vagy törölni az eszközlízing naplóbejegyzésekben, mivel ez eltéréseket okozhat az ütemezések és a tranzakciók között.

4. Jelölje ki a naplóbejegyzést, majd válassza a **Feladás** lehetőséget az értékcsökkenési tétel Főkönyvbe történő rögzítéséhez.

## <a name="calculation-of-rou-asset-amortization-expense-for-operating-leases"></a>A ROU-eszközamortizációs költség kiszámítása az operatív lízingek esetében

Az operatív lízing értékcsökkenési költségét a havi lineáris lízingköltség és a lízingkötelezettség havi kamatráfordítása közötti különbségként számítják ki, a Könyvelési standardok kodifikációs témaköre 842 (ASC 842) alapján, amely az Általánosan elfogadott könyvelési elvek az Egyesült Államokban (US GAAP) standardja. A rendszer az összes lízingdíjfizetés és a hónapokban meghatározott lízingfutamidő hányadosaként számítja ki a közvetlen lízingköltséget. (A lízingfizetések összege magában foglalja az előlegek, a kezdeti közvetlen költségek, a bontási költségek és a lízingösztönzők összegét.) Az alábbi táblázat egy működési lízing amortizációs költségére mutat egy példát.

### <a name="example-of-rou-asset-amortization-expense-for-operating-leases"></a>A ROU-eszközamortizációs költség példája az operatív lízingek esetében

| Mező                                          | Érték       |
|------------------------------------------------|-------------|
| Fizetés összege                                 | 1000       |
| Fizetés gyakorisága                              | Havi     |
| Lízingfutamidő (hónap)                            | 24          |
| Összes lízingdíjfizetés                           | 24,000      |
| Járulékos kamatláb                     | 5%          |
| Annuitás típusa                                   | Esedékes annuitás |
| Összetételi intervallum                           | Havi     |
| A jövőbeli minimális lízingdíjfizetés jelenértéke | 22,888.87   |

Ahogy azt korábban említettük, a rendszer az összes fizetés és a meghatározott lízingfutamidő hányadosaként számítja ki a közvetlen lízingköltséget. A rendszer automatikusan kiszámítja a havi kamatráfordítást a kötelezettség amortizációs ütemezésében. A kamatráfordítás kiszámítása az effektív kamatláb módszerrel történik. A rendszer a lineáris lízingköltséget használja az egyes havi kamatköltségek levonására. Az érték a ROU-eszköz csökkentésére szolgál.

| Hónap | Lineáris lízingköltség | Kamatköltség                        | ROU-eszközamortizációs ráfordítás kiszámítása |
|-------|--------------------------|-----------------------------------------|-----------------------------------------------|
| 1     | (24.000 ÷ 24) = 1.000,00 | (22.888,87 – 1.000) × (5% ÷ 12) = 91,20 | 1.000 – 91,20 = 908,80                        |
| 2     | (24.000 ÷ 24) = 1.000,00 | (21.980,08 – 1.000) × (5% ÷ 12) = 87,42 | 1.000 – 87,42 = 912,58                        |
| 3     | (24.000 ÷ 24) = 1.000,00 | (21.067,49 – 1.000) × (5% ÷ 12) = 83,62 | 1.000 – 83,62 = 916,39                        |

> [!NOTE]
> Az ASC 842 szerint az operatív lízing ROU-eszköz értéke lízingráfordításként van besorolva az eredménykimutatásban. A láthatóság érdekében az eszközlízing a tételt a ROU-eszköz értékcsökkenéseként írja le. A tartozás bejegyzést azonban egy operatív lízingköltség számlához kell rendelni, és a hiteltételt közvetlenül a ROU-eszközhöz kell hozzárendelni az operatív lízinghez. Mindazonáltal a lízingparaméterekben megadhatja, hogy a jóváírás tételeket a ROU-eszközök működő eszközeinek halmozott értékcsökkenési számlájára kell tenni.

Ha a bérlet üzemi bérleti díjnak van minősítve, a értékvesztés utáni havi értékcsökkenés számítása straight-line értékcsökkenéssel történik.

## <a name="calculation-of-rou-asset-amortization-expense-for-finance-leases"></a>A ROU-eszközamortizációs költség kiszámítása a pénzügyi lízingek esetében

A pénzügyi osztályozással rendelkező lízingek esetében a rendszer a ROU-eszközamortizációt lineárisan számítja ki. Ezért az értékcsökkenési költség minden hónapban azonos lesz.

A Nemzetközi pénzügyi jelentési standard 16 (IFRS 16) és ASC 842 szabványnak megfelelően az eszközt vagy a lízingfutamidő vagy az eszköz hasznos élettartama alatt amortizálják, attól függően, hogy melyik a kevesebb. Továbbá, ha a **Tulajdonjog átadása** paraméter be van kapcsolva a lízinghez, a lízing automatikusan amortizálódik az eszköz hasznos élettartama alatt.

### <a name="example-of-rou-asset-amortization-expense-for-finance-leases"></a>A ROU-eszközamortizációs költség példája az pénzügyi lízingek esetében

| Mező                                | Érték                                   |
|--------------------------------------|-----------------------------------------|
| Használatijog-eszköz nyitó egyenlege | 22,889.87                               |
| Lízingfutamidő (hónap)                  | 24                                      |
| Eszköz hasznos élettartama (hónap)           | 36                                      |
| Hónap                                | Használatijog-eszköz amortizációs költsége |
| 1                                    | 22.889,87 ÷ 24 = 953,74                 |
| 2                                    | 22.889,87 ÷ 24 = 953,74                 |
| 3                                    | 22.889,87 ÷ 24 = 953,74                 |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
