---
title: A tényleges frissített mennyiség tizedes kerekítése helytelen
description: Csomagolási bizonylat létrehozásakor a kimenő terhelés olyan mennyiséget tartalmaz, amely nem egyezik meg az egységben meghatározott tizedes pontossággal.
author: GalynaFedorova
ms.date: 5/31/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadPlanningListPage_WHSSalesPackingSlipPost, WHSLoadTable_WHSSalesPackingSlipPost
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 1e63440834f516879aa8ad711bd789e62b0ee993
ms.sourcegitcommit: e6437d994c3be0c5bb4a9263af3aa8351020d83a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/14/2021
ms.locfileid: "6248785"
---
# <a name="decimal-rounding-of-the-physical-updating-quantity-is-incorrect"></a>A tényleges frissített mennyiség tizedes kerekítése helytelen

Hibakód: SYS19589

## <a name="symptoms"></a>Tünetek

Csomagolási bizonylat létrehozásakor a kimenő terhelés olyan mennyiséget tartalmaz, amely nem egyezik meg az egységben meghatározott tizedes pontossággal.

Amikor megpróbál létrehozni egy szállítólevelet, a rendszer a következő hibaüzenetet jeleníti meg:

> A tényleges módosító mennyiség tizedes kerekítése a(z) %1 egységben helytelen.

Ennek megfelelően nem hozható létre szállítólevél a rakományhoz.

## <a name="cause"></a>Ok

A rendszer kiértékeli, hogy a szállítási mennyiség tizedes kerekítése megfelel-e a szállítási egységnél megadott tizedes pontosságnak. Ha a rendszer a megadott tizedesjegyre kerekítve találja meg a szállítási mennyiséget, és úgy találja, hogy a kerekített szállítási mennyiség nem felel meg a tényleges szállítási mennyiségnek, nem generálhatja a csomagjegyzéket. Ez a probléma például akkor fordulhat elő, ha az értékesítési mennyiség 1,75 kilogramm (kg), de a tizedes pontosság *1*.

## <a name="resolution"></a>Megoldás

A rakomány vagy a szállítmány jelenlegi állapotában nem hozható létre szállítólevél. A probléma javításához végezze el a következő feladatok egyikét:

- Tekintse át a terhelési sorokat, és végezze el a beállításokat annak biztosítására, hogy a mennyiséget tisztán lehet számolni tizedesjegyek és egyéb kerekítési kérdések nélkül.
- Tekintse át a rakománysorokat, és hajtsa végre a szükséges módosításokat, hogy az egység és a mennyiség igazodjon az egység tizedes pontosságához.

### <a name="review-your-load-lines-and-make-adjustments-to-ensure-that-the-quantity-can-be-cleanly-converted-without-decimal-numbers-and-any-other-rounding-issues"></a>Tekintse át a terhelési sorokat, és végezze el a beállításokat annak biztosítására, hogy a mennyiséget tisztán lehet számolni tizedesjegyek és egyéb kerekítési kérdések nélkül

A következő eljárással tekintse át a terhelési sorokat, és végezze el a beállításokat annak biztosítása érdekében, hogy a mennyiség tisztán átváltható legyen tizedesjegyek és egyéb kerekítési problémák nélkül.

1. Lépjen a **Raktárkezelés \> Rakományok \> Minden rakomány** elemhez.
1. Válassza ki azt a rakományt, amelyhez nem hozható létre a szállítólevél.
1. A Művelet panel  **Szállítás és fogadás** lapján lévő  **Sztornírozás** csoportban válassza a  **Szállítmány visszaigazolásának sztornírozása** lehetőséget.
1. A  **Rakománysorok** lapon válassza ki annak a cikknek rakománysorát, amely a hibát okozza.
1. A kiválasztott mennyiség beállításához válassza a **Kitárolt mennyiség csökkentése** lehetőséget.
1. A  **Sor részletei** lapon válassza ki a **Rendelés** lehetőséget.
1. A **Mennyiség** mezőben állítsa be a kitárolt mennyiség értékét (azaz a **Munka létrehozott mennyisége** mező értékét), hogy a szállítólevél létrehozása elvégezhető legyen.

### <a name="review-your-load-lines-and-make-adjustments-to-ensure-that-the-unit-and-quantity-are-aligned-with-the-decimal-precision-of-the-unit"></a>Tekintse át a rakománysorokat, és hajtsa végre a szükséges módosításokat, hogy az egység és a mennyiség igazodjon az egység tizedes pontosságához

Az alábbi módon tekintse át a rakománysorokat, és hajtsa végre a szükséges módosításokat, hogy az egység és a mennyiség igazodjon az egység tizedes pontosságához.

1. Lépjen a **Raktárkezelés \> Rakományok \> Minden rakomány** elemhez.
1. Válassza ki azt a rakományt, amelyhez nem hozható létre a szállítólevél.
1. A **Rakománysorok** gyorslapon válassza ki annak a cikknek rakománysorát, amely a hibát okozza. Jegyezze fel a **Mennyiség** és az **Egység** mező értékét.
1. Lépjen a **Szervezetadminisztráció \> Egységek \> Egységek** részre.
1. Válassza ki azt az egységet, amelyhez nem hozható létre a szállítólevél.
1. Szükség szerint módosítsa a **Tizedes pontosság** mező értékét.
