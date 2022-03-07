---
title: Frissítési ütközés, ha a készletellenőrzési módszer elszámolóáras vagy mozgóátlag
description: Frissítési ütközés történik, ha a készletellenőrző módszer elszámolóáras vagy mozgóátlag
author: AndersGirke
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: InventAgingStorage, InventAgingStorageChart, InventAgingStorageDetails, InventValueProcess, InventValueReportSetup, InventClosing
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 920d20d19843ce0cac678c5426c00ec99aa61c61
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476582"
---
# <a name="an-update-conflict-occurs-when-the-inventory-valuation-method-is-either-standard-cost-or-moving-average"></a>Frissítési ütközés történik, ha a készletellenőrző módszer elszámolóáras vagy mozgóátlag

## <a name="symptoms"></a>Tünetek

Ha párhuzamosan ad fel olyan dokumentumokat, mint a készletnaplók, a beszerzési rendelési számlák vagy az értékesítési rendelés számlái a skálázhatóság és a teljesítmény érdekében, hibaüzenetet kaphat egy frissítési ütközésről, és előfordulhat, hogy néhány dokumentum nem lesz feladva. Ez a hiba akkor fordulha elő, ha a készletellenőrző módszer *elszámolóáras* vagy *mozgóátlag*. Mindkét módszer végleges költségszámítási módszer. Más szóval a végső költséget a feladáskor határozzák meg.

Ha a *Mozgóátlag* módszert használja, akkor a hibaüzenet hasonló ehhez a példához:

> Az arányos költségszámítás után nem várható xx.xx készletérték

Ha az *Elszámolóáras* módszert használja, akkor a hibaüzenet hasonló ehhez a példához:

> Az elszámolóár nem egyezik meg a frissítés utáni pénzügyi készletértékkel. Érték = xx.xx, mennyiség = yy.yy, elszámolóár = zz.zz

## <a name="workaround"></a>Megkerülő megoldás

Amíg a Microsoft nem ad ki megoldást a probléma kiküszöbölésére, a hibák elkerüléséhez vagy csökkentéséhez fontolja meg a következő megoldások használatát:

- Adja fel újra a sikertelen dokumentumokat.
- Hozzon létre olyan dokumentumokat, amelyekhez kevesebb sor tartozik.
- Kerülje a decimális értékeket az elszámolóárban. Próbálja meg meghatározni az elszámolóárat úgy, hogy az **Ár mennyisége** mező *1-re* van állítva. Ha *1*-nél több **Ármennyiség** értéket kell megadnia, próbálja meg minimálisra csökkenteni a tizedesjegyek számát az elszámolóáron. (Ideális esetben kevesebb mint két tizedesjegynek kell lennie.) Például ne definiálja az olyan elszámolóár-beállításokat, mint például **Ár** = *10* és **Ármennyiség** = *3*, mivel a készletegység elszámolóárát 3.333333 értékben fogják létrehozni (ahol a tizedesérték ismétlődik).
- A dokumentumok többsége esetében lehetőleg ne legyen több olyan sor, amely a termék- és pénzügyi készletdimenziók ugyanazon kombinációját tartalmazza.
- Csökkentse a párhuzamos futások mértékét. (Ebben az esetben a rendszer gyorsabb lehet, mert kevesebb frissítési ütközés és újraküldés fordulhat elő.)
