---
title: A kiválasztott mennyiség nem elegendő a szállítólevél létrehozása során
description: Amikor szállítólevelet hoz létre, a kimenő rakomány olyan kiválasztott mennyiséget tartalmaz, amely nem egyezik a rakomány sorában lévő munkamennyiséggel.
author: GalynaFedorova
ms.date: 5/31/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadTable_WHSSalesPackingSlipPost,WHSLoadPlanningListPage_WHSSalesPackingSlipPost,WHSLoadPlanningWorkbench_WHSSalesPackingSlipPost
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 361b61690e9e16a690234ed9319478d864c743e7559746654e4868272de13524
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6716468"
---
# <a name="picked-quantity-isnt-sufficient-during-packing-slip-generation"></a>A kiválasztott mennyiség nem elegendő a szállítólevél létrehozása során

Hibakód: SYS54073

## <a name="symptoms"></a>Tünetek

Amikor szállítólevelet hoz létre, a kimenő rakomány olyan kiválasztott mennyiséget tartalmaz, amely nem egyezik a rakomány sorában lévő munkamennyiséggel.

Amikor megpróbál létrehozni egy szállítólevelet, a rendszer a következő hibaüzenetet jeleníti meg:

> Mivel %1 lett tárolva, nem frissíthető %2, ha a fennmaradónak %3 értékűnek kell lennie.

Ennek megfelelően nem hozható létre szállítólevél a rakományhoz.

## <a name="cause"></a>Ok

A szállítólevél nem hozható létre az adott állapotban, mert a következők valamelyike fennállhat:

- A kapcsolódó munkát még nem választották ki és nem helyezték át a végső szállítási helyre.
- A kitárolt munkamennyiség nem egyezik meg a rakománysor létrehozott munkamennyiségével.
- A rakománysorban lévő mennyiség, a munka létrehozott mennyisége és a kiválasztott mennyiség nem egyezik.

## <a name="resolution"></a>Megoldás

A rakomány vagy a szállítmány jelenlegi állapotában nem hozható létre szállítólevél. A probléma javításához végezze el a következő feladatok egyikét:

- Ellenőrizze a rakomány sorait, és győződjön meg róla, hogy minden kapcsolódó munkát befejeztek a végleges kiszállítási helyen, és hogy a mennyiségek megegyeznek.
- Korrigálja a rakománysor mennyiségét.
- Sztornírozza az összes kiválasztási regisztrációt, és hajtsa végre újra a kiválasztást.

### <a name="review-your-load-lines-and-make-sure-that-all-the-related-work-has-been-completed-at-the-final-shipping-location-and-that-the-quantities-match"></a>Ellenőrizze a rakomány sorait, és győződjön meg róla, hogy minden kapcsolódó munkát befejeztek a végleges kiszállítási helyen, és hogy a mennyiségek megegyeznek

Az alábbi módon ellenőrizze a rakomány sorait, és győződjön meg róla, hogy minden kapcsolódó munkát befejeztek a végleges kiszállítási helyen, és hogy a mennyiségek megegyeznek.

1. Lépjen a **Raktárkezelés \> Rakományok \> Minden rakomány** elemhez.
1. Válassza ki azt a rakományt, amelyhez nem hozható létre a szállítólevél.
1. A **Rakománysorok** gyorslapon válassza ki a sor betöltése lehetőséget.
1. Jegyezze fel a **Munka létrehozott mennyisége** mező értékét.
1. A Művelet ablaktábla **Betöltések** lapjának **Kapcsolódó információk** csoportjában válassza a **Munka** elemet.
1. Ellenőrizze, hogy a munkát a végső kiszállítási helyen befejezték-e, és hogy a kitárolt munkamennyiség megegyezik-e a rakománysor létrehozott munkamennyiségével.
1. Ismételje meg ezt az eljárást minden rakománysorral annak érdekében, hogy minden feltétel teljesüljön.

### <a name="adjust-the-load-line-quantity"></a>Korrigálja a rakománysor mennyiségét

Az alábbi módon korrigálja a rakománysor mennyiségét.

1. Lépjen a **Raktárkezelés \> Rakományok \> Minden rakomány** elemhez.
1. Válassza ki azt a rakományt, amelyhez nem hozható létre a szállítólevél.
1. A Művelet panel  **Szállítás és fogadás** lapján lévő  **Sztornírozás** csoportban válassza a  **Szállítmány visszaigazolásának sztornírozása** lehetőséget.
1. A  **Rakománysorok** lapon válassza ki annak a cikknek rakománysorát, amely a hibát okozza.
1. A kiválasztott mennyiség beállításához válassza a **Kitárolt mennyiség csökkentése** lehetőséget.
1. Állítsa be úgy a **Rakománysor csökkentése** mezőt, hogy tükrözze a terhelési sor módosításait.

### <a name="reverse-all-pick-registrations-and-redo-picking"></a>Sztornírozza az összes kiválasztási regisztrációt, és hajtsa végre újra a kiválasztást

A probléma azért fordulhat elő, mert valaki a regisztráció kiválasztását használta arra, hogy munka nélkül lezárja a rakomány sorát. Ebben az esetben sztornírozni kell a regisztráció kézi kiválasztását, és a kiválasztást a Warehouse Management mobilalkalmazással kell végrehajtani.

A regisztráció kiválasztásának sztornírozásához használja a következő eljárást.

1. Lépjen a **Kinnlevőségek \> Rendelések \> Minden rendelés** részre.
1. Válassza ki azt az értékesítési rendelést, amelynél nem tud szállítólevelet feladni a rakományhoz.
1. Az  **Értékesítési rendelés sorai** lapon válassza ki az értékesítési rendelési azon sorát, amelyhez a regisztráció kiválasztása történt.
1. Válassza a **Sor frissítése \> Kitárolás** lehetőséget a kiválasztás visszavonásához.
