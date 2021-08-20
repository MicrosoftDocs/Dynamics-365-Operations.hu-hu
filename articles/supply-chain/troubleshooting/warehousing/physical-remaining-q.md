---
title: Az egységben maradó fizikai mennyiség nem lehet nulla
description: Amikor szállítólevelet hoz létre, a hozzá megadott adatok nem nulla készletmennyiséget, hanem nulla értékesítési mennyiséget jelentenek.
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
ms.openlocfilehash: 187363db3030ee0741f0c7e7746295b88320162c156120112332bb78593bb673
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6744654"
---
# <a name="physical-remaining-quantity-in-the-unit-must-not-be-zero"></a>Az egységben maradó fizikai mennyiség nem lehet nulla

Hibakód: SYS19591

## <a name="symptoms"></a>Tünetek

Amikor szállítólevelet hoz létre, a hozzá megadott adatok nem nulla készletmennyiséget, hanem nulla értékesítési mennyiséget jelentenek.

Amikor megpróbálja létrehozni a szállítólevelet, a rendszer a következő hibaüzenetet jeleníti meg:

> A tényleges fennmaradó mennyiség a(z) %1 egységben nem lehet nulla.

Ennek megfelelően nem hozható létre szállítólevél a rakományhoz.

## <a name="cause"></a>Ok

A rendszer kiértékeli a készletegységben maradó fizikai mennyiséget, illetve a szállítási egységben maradó fizikai mennyiséget. Ha a rendszer azt állapítja meg, hogy a szállítási egységben maradó fizikai mennyiség 0 (nulla), de a készletegységben maradó fizikai mennyiség nem 0, akkor nem hozható létre a szállítólevél. Ez a probléma például akkor fordulhat elő, ha a cikk értékesítési egysége és készletegysége eltér, és az egységek közötti átváltás nem pontos.

## <a name="resolution"></a>Megoldás

A rakomány vagy a szállítmány jelenlegi állapotában nem hozható létre szállítólevél. A probléma javításához végezze el a következő feladatok egyikét:

- Ellenőrizze a rakomány sorait, és győződjön meg róla, hogy minden kapcsolódó munkát befejeztek a végleges kiszállítási helyen, és hogy a mennyiségek megegyeznek.
- Tekintse át a rakománysorokat, és hajtsa végre a szükséges módosításokat, hogy a mennyiség kerekítési problémák nélkül, tisztán átváltható legyen.
- Tekintse át a rakománysorokat, és hajtsa végre a szükséges módosításokat, hogy az egység és a mennyiség igazodjon az egység tizedes pontosságához.
- Győződjön meg arról, hogy a készlet mértékegysége kisebb, mint az értékesítési mértékegység.

### <a name="review-your-load-lines-and-make-sure-that-all-the-related-work-has-been-completed-at-the-final-shipping-location-and-that-the-quantities-match"></a>Ellenőrizze a rakomány sorait, és győződjön meg róla, hogy minden kapcsolódó munkát befejeztek a végleges kiszállítási helyen, és hogy a mennyiségek megegyeznek

Az alábbi módon ellenőrizze a rakomány sorait, és győződjön meg róla, hogy minden kapcsolódó munkát befejeztek a végleges kiszállítási helyen, és hogy a mennyiségek megegyeznek.

1. Lépjen a **Raktárkezelés \> Rakományok \> Minden rakomány** elemhez.
1. Válassza ki azt a rakományt, amelynél a szállítmányt nem lehet megerősíteni.
1. A **Rakománysorok** gyorslapon válassza ki a sor betöltése lehetőséget.
1. Jegyezze fel a **Munka létrehozott mennyisége** mező értékét.
1. A Művelet ablaktábla **Betöltések** lapjának **Kapcsolódó információk** csoportjában válassza a **Munka** elemet.
1. Ellenőrizze, hogy a munkát a végső kiszállítási helyen befejezték-e, és hogy a kitárolt munkamennyiség megegyezik-e a rakománysor létrehozott munkamennyiségével.
1. Ismételje meg ezt az eljárást minden rakománysorral annak érdekében, hogy minden feltétel teljesüljön.

### <a name="review-your-load-lines-and-make-adjustments-to-ensure-that-the-quantity-can-be-cleanly-converted-without-rounding-issues"></a>Tekintse át a rakománysorokat, és hajtsa végre a szükséges módosításokat, hogy a mennyiség kerekítési problémák nélkül, tisztán átváltható legyen

Az alábbi módon tekintse át a rakománysorokat, és hajtsa végre a szükséges módosításokat, hogy a mennyiség kerekítési problémák nélkül, tisztán átváltható legyen.

1. Lépjen a **Raktárkezelés \> Rakományok \> Minden rakomány** elemhez.
1. Válassza ki azt a rakományt, amelyhez nem hozható létre a szállítólevél.
1. A Művelet panel  **Szállítás és fogadás** lapján lévő  **Sztornírozás** csoportban válassza a  **Szállítmány visszaigazolásának sztornírozása** lehetőséget.
1. A  **Rakománysorok** lapon válassza ki annak a cikknek rakománysorát, amely meghaladja a felülszállítás százalékos arányát.
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

### <a name="make-sure-that-the-inventory-unit-of-measure-is-smaller-than-the-sales-unit-of-measure"></a>Győződjön meg arról, hogy a készlet mértékegysége kisebb, mint az értékesítési mértékegység

Győződjön meg arról, hogy a készlet mértékegysége kisebb, mint az értékesítési mértékegység. Fontolja meg, érdemes-e újrakonfigurálni a cikk mértékegységét.
