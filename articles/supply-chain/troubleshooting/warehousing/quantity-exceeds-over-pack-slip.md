---
title: A szállítólevél létrehozása során a mennyiség meghaladja a túlszállítás arányát
description: A szállítólevél létrehozásakor a kimenő rakomány olyan mennyiséget tartalmaz, amely meghaladja a túlszállítás százalékos arányát.
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
ms.openlocfilehash: 1106322cc3772c1b671b7fa82fb74039c028ba35
ms.sourcegitcommit: e6437d994c3be0c5bb4a9263af3aa8351020d83a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/14/2021
ms.locfileid: "6249112"
---
# <a name="quantity-exceeds-over-delivery-percentage-during-packing-slip-generation"></a>A szállítólevél létrehozása során a mennyiség meghaladja a túlszállítás arányát

Hibakód: SYS24920

## <a name="symptoms"></a>Tünetek

A szállítólevél létrehozásakor a kimenő rakomány olyan mennyiséget tartalmaz, amely meghaladja a túlszállítás százalékos arányát.

Amikor megpróbál létrehozni egy szállítólevelet, a rendszer a következő hibaüzenetet jeleníti meg:

> A sor túlszállítása %1 százalék, de csak %2 százalékos túlszállítás megengedett.

Ennek megfelelően nem hozható létre szállítólevél a rakományhoz.

## <a name="cause"></a>Ok

A rakomány vagy a szállítmány kiválasztott mennyisége nagyobb, mint a megrendelt mennyiség, és a túlszállítás százalékos tartományán kívül esik.

## <a name="resolution"></a>Megoldás

A rakomány vagy a szállítmány jelenlegi állapotában nem hozható létre szállítólevél. A probléma javításához végezze el a következő feladatok egyikét:

- Korrigálja a rakománysor mennyiségét.
- Korrigálja a túlszállítás százalékos értékét.
- Sztornírozzon, és végezzen kiigazításokat.

### <a name="adjust-the-load-line-quantity"></a>Korrigálja a rakománysor mennyiségét

Az alábbi módon korrigálja a rakománysor mennyiségét.

1. Lépjen a **Raktárkezelés \> Rakományok \> Minden rakomány** elemhez.
1. Válassza ki azt a rakományt, amelyhez nem hozható létre a szállítólevél.
1. A Művelet panel  **Szállítás és fogadás** lapján lévő  **Sztornírozás** csoportban válassza a  **Szállítmány visszaigazolásának sztornírozása** lehetőséget.
1. A  **Rakománysorok** lapon válassza ki annak a cikknek rakománysorát, amely meghaladja a túlszállítás százalékos arányát.
1. A kiválasztott mennyiség beállításához válassza a **Kitárolt mennyiség csökkentése** lehetőséget.
1. A  **Sor részletei** lapon válassza ki a **Rendelés** lehetőséget.
1. A **Mennyiség** mezőben állítsa be a kitárolt mennyiség értékét (azaz a **Munka létrehozott mennyisége** mező értékét), hogy a szállítólevél létrehozása elvégezhető legyen.

### <a name="adjust-the-over-delivery-percentage"></a>Korrigálja a túlszállítás százalékos értékét

Az alábbi módon korrigálja a túlszállítás százalékos értékét.

1. Lépjen a **Kinnlevőségek \> Rendelések \> Minden rendelés** részre.
1. Válassza ki azt az értékesítési rendelést, amelynél nem tud szállítólevelet feladni a rakományhoz.
1. Az  **Értékesítési rendelés sorai** lapon válassza ki az értékesítési rendelésnek azt a sorát, amely meghaladja a túlszállítás százalékos arányát.
1. A  **Sor részletei** lapon válassza ki a **Szállítás** lehetőséget.
1. A **Túlszállítás** mezőben állítson be olyan, nagyobb százalékértéket, amely megfelelő a rakománymennyiséggel szemben kitárolt mennyiségnek; így a rendszer létre tudja hozni a szállítólevelet.

### <a name="reverse-and-make-adjustments"></a>Sztornírozzon, és végezzen kiigazításokat

A rakományhoz feladott minden részletet (például a szállítólevelet, a szállítás visszaigazolását, a munkát) sztornírozzon, helyesbítse az értékesítési rendelést, adja ki újra a rendelést a raktárba, és zárja le a szállítási folyamatot.

Az alábbi módon érvénytelenítse a szállítólevelet.

1. Lépjen a **Raktárkezelés \> Rakományok \> Minden rakomány** elemhez.
1. A Művelet panel  **Szállítás és fogadás** lapján lévő  **Sztornírozás** csoportban válassza a  **Szállítólevelek érvénytelenítése** lehetőséget.

Az alábbi módon sztornírozza a szállítmányok visszaigazolását.

1. Lépjen a **Raktárkezelés \> Rakományok \> Minden rakomány** elemhez.
1. A Művelet panel  **Szállítás és fogadás** lapján lévő  **Sztornírozás** csoportban válassza a  **Szállítmány visszaigazolásának sztornírozása** lehetőséget.

A munkák az alábbi módon sztornírozahtók.

1. Lépjen a **Raktárkezelés \> Rakományok \> Minden rakomány** elemhez.
1. A Művelet ablaktábla  **Rakományok** lapjának  **Munka** csoportjában válassza a  **Munka sztornírozása** elemet.
