---
title: Leállított értékesítésirendelés-sor után nem könyvelhető szállítólevél
description: Leállított értékesítésirendelés-sorhoz nem könyvelhető szállítólevél
author: smithanataraj
ms.date: 03/07/2022
ms.topic: article
ms.search.form: WHSLoadTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mfp
ms.search.validFrom: 2022-03-07
ms.dyn365.ops.version: 10.0.26
ms.openlocfilehash: 115cfe79e075eb36f73203818acdbb5e31fc0bad
ms.sourcegitcommit: c0f7ee7f8837fec881e97b2a3f12e7f63cf96882
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/22/2022
ms.locfileid: "8462919"
---
# <a name="cant-post-packing-slip-for-a-stopped-a-sales-order-line"></a>Leállított értékesítésirendelés-sor után nem könyvelhető szállítólevél

Hibakód: SYS13203

## <a name="symptoms"></a>Tünetek

Amikor rakományra próbál szállítólevelet feladni, a rendszer a következő hibaüzenetet jeleníti meg:

> Nem lehet könyvelni a szállítólevelet, ha leállít egy értékesítésirendelés-sort a kimenő szállítólevél megerősítése után A mennyiség nem vehető fel.

## <a name="cause"></a>Ok

A kapcsolódó értékesítésirendelés-sorok közül egy vagy több leállítható, ami azt jelenti, hogy a rendszer megakadályozza az értékesítési rendelés további feldolgozását. Ez többek között azt jelenti, hogy a rendszer nem küld szállítólevelet a megrendeléshez.

Előfordulhat például, hogy egy felhasználó úgy döntött, hogy leállít egy vagy több rendeléssort, mert a vevő visszahívta és visszavonta a rendelését. Ha azonban a kimenő szállítólevelet már megerősítették, akkor az értékesítési rendelést tartalmazó szállítólevél már fizikailag elhagyta volna a raktárat, ami azt jelenti, hogy az értékesítésirendelés-sorok leállítása nem lesz hatással. Mivel a szállítmány fizikailag már nem állítható le, akár a sorokat is feloldhatja, hogy könyvelhesse a szállítólevelet. Ezután a visszavont megrendelést visszaküldésként kell kezelnie.

## <a name="resolution"></a>Megoldás

A szállítólevél könyveléséhez győződjön meg arról, hogy a megfelelő értékesítésirendelés-sorok egyike sem áll le az alábbi lépésekkel.

1. Ugrás a **Minden értékesítési rendelés \> értékesítés és marketing \> Az összes értékesítési rendelésre**.
1. Keresse meg és nyissa meg azt az értékesítési rendelést, amellyel problémái vannak.
1. Az **Értékesítési rendeléssorok** gyorslapon válasszon ki egy értékesítésirendelés-sort.
1. **A Sor részletei** gyorslapon nyissa meg az **Általános** lapot, és győződjön meg arról, hogy a **Leállított** mező értéke *Nem*.
1. Folytassa a munkát, amíg az összes releváns értékesítési sor már nem áll le.
1. Próbálja meg újra feladni a rakományhoz vagy az értékesítési rendeléshez tartozó szállítólevelet.
