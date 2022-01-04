---
title: A frissíteni próbált mennyiség meghaladja a kapott/leszállított mennyiséget.
description: Amikor szállítólevelet hoz létre, a kimenő rakomány olyan mennyiséget tartalmaz, amely meghaladja a kiválasztott és az értékesítési rendeléshez lefoglalt munkamennyiséget.
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
ms.openlocfilehash: ec5e0ac8dd097e5ebf016683fc5c17df7ecb2305
ms.sourcegitcommit: 008779c530798f563fe216810d34b2d56f2c8d3c
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/14/2021
ms.locfileid: "7920398"
---
# <a name="quantity-that-youre-trying-to-update-exceeds-the-receiveddelivered-quantity"></a>A frissíteni próbált mennyiség meghaladja a kapott/leszállított mennyiséget

Hibakód: SYS7676

## <a name="symptoms"></a>Tünetek

Amikor szállítólevelet hoz létre, a kimenő rakomány olyan mennyiséget tartalmaz, amely meghaladja a kiválasztott és az értékesítési rendeléshez lefoglalt munkamennyiséget.

Amikor megpróbál létrehozni egy szállítólevelet, a rendszer a következő hibaüzenetet jeleníti meg:

> A frissíteni kívánt mennyiség meghaladja a bevételezett/szállított mennyiséget.

Ennek megfelelően nem hozható létre szállítólevél a rakományhoz.

## <a name="cause"></a>Ok

A kitárolt munkamennyiség nem egyezik meg a rakománysor létrehozott munkamennyiségével. Ez a probléma például akkor fordulhat elő, ha a rakománysorban lévő mennyiség, a munka létrehozott mennyisége vagy a kiválasztott mennyiség nem pontos.

## <a name="resolution"></a>Megoldás

A rakomány vagy a szállítmány jelenlegi állapotában nem hozható létre szállítólevél. A probléma javításához végezze el a következő feladatok egyikét:

- Ellenőrizze a rakomány sorait, és győződjön meg róla, hogy minden kapcsolódó munkát befejeztek a végleges kiszállítási helyen, és hogy a mennyiségek megegyeznek.
- Korrigálja a rakománysor mennyiségét.
- Sztornírozza az összes kiválasztási regisztrációt, és hajtsa végre újra a kiválasztást.

### <a name="review-your-load-lines-and-make-sure-that-all-the-related-work-has-been-completed-at-the-final-shipping-location-and-that-the-quantities-match"></a>Ellenőrizze a rakomány sorait, és győződjön meg róla, hogy minden kapcsolódó munkát befejeztek a végleges kiszállítási helyen, és hogy a mennyiségek megegyeznek

Az alábbi módon ellenőrizze a rakomány sorait, és győződjön meg róla, hogy minden kapcsolódó munkát befejeztek a végleges kiszállítási helyen, és hogy a mennyiségek megegyeznek.

1. Lépjen a **Raktárkezelés \> Rakományok \> Minden rakomány** elemhez.
1. Válassza ki azt a rakományt, amelynél a szállítmányt nem lehet létrehozni.
1. A **Rakománysorok** gyorslapon válassza ki a sor betöltése lehetőséget.
1. Jegyezze fel a **Munka létrehozott mennyisége** mező értékét.
1. A Művelet ablaktábla **Betöltések** lapjának **Kapcsolódó információk** csoportjában válassza a **Munka** elemet.
1. Ellenőrizze, hogy a munkát a végső kiszállítási helyen befejezték-e, és hogy a kitárolt munkamennyiség megegyezik-e a rakománysor létrehozott munkamennyiségével.
1. Ismételje meg ezt az eljárást minden rakománysorral annak érdekében, hogy minden feltétel teljesüljön.

### <a name="adjust-the-load-line-quantity"></a>Korrigálja a rakománysor mennyiségét

Az alábbi módon korrigálja a rakománysor mennyiségét.

1. Lépjen a **Raktárkezelés \> Rakományok \> Minden rakomány** elemhez.
1. Válassza ki azt a rakományt, amelyhez nem hozható létre a szállítólevél.
1. A Művelet ablakTábla Szállítás és fogadás lap Sztornírozási csoportjában válassza a **Szállítmány** **·** **visszaigazolásának sztornírozására lehetőséget**.
1. A Rakománysorok lapon válassza ki a problémát okozó cikk **rakománysorát**.
1. A kiválasztott mennyiség beállításához válassza a **Kitárolt mennyiség csökkentése** lehetőséget.
1. Állítsa be úgy a **Rakománysor csökkentése** mezőt, hogy tükrözze a terhelési sor módosításait.

### <a name="reverse-all-pick-registrations-and-redo-picking"></a>Sztornírozza az összes kiválasztási regisztrációt, és hajtsa végre újra a kiválasztást

Ha valaki regisztráció kiválasztásával zárt be egy munka nélküli rakománysort, akkor a rakománysorban lévő mennyiség és a kiválasztott mennyiség eltérhet. Ebben az esetben sztornírozni kell a regisztráció kézi kiválasztását, és a kiválasztást a Warehouse Management mobilalkalmazással kell végrehajtani.

A regisztráció kiválasztásának sztornírozásához használja a következő eljárást.

1. Lépjen a **Kinnlevőségek \> Rendelések \> Minden rendelés** részre.
1. Válassza ki azt az értékesítési rendelést, amelynél nem tud szállítólevelet feladni a rakományhoz.
1. Az Értékesítésirendelés-sorok lapon válassza ki azt az értékesítésirendelés-sort, amelyről a **kiválasztó** regisztrációját végezték.
1. Válassza a **Sor frissítése \> Kitárolás** lehetőséget a kiválasztás visszavonásához.
