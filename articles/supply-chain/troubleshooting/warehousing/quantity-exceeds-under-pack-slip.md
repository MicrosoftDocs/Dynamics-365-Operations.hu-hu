---
title: A szállítólevél létrehozása során a mennyiség meghaladja a szállítási hiány arányát
description: A szállítólevél létrehozásakor a kimenő rakomány olyan mennyiséget tartalmaz, amely meghaladja a szállítási hiány százalékos arányát.
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
ms.openlocfilehash: ae02846c0ec937ebaff440dc5272a135e16c8aa7355ecc303929e760a54b6627
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6760298"
---
# <a name="quantity-exceeds-under-delivery-percentage-during-packing-slip-generation"></a>A szállítólevél létrehozása során a mennyiség meghaladja a szállítási hiány arányát

Hibakód: SYS24921

## <a name="symptoms"></a>Tünetek

A szállítólevél létrehozásakor a kimenő rakomány olyan mennyiséget tartalmaz, amely meghaladja a szállítási hiány százalékos arányát.

Amikor megpróbál létrehozni egy szállítólevelet, a rendszer a következő hibaüzenetet jeleníti meg:

> A sor alulszállítása %1 százalék, de csak %2 százalékos alulszállítás megengedett.

Ennek megfelelően nem hozható létre szállítólevél a rakományhoz.

## <a name="cause"></a>Ok

A rakomány vagy a szállítmány kiválasztott mennyisége kisebb, mint a megrendelt mennyiség, és a szállítási hiány százalékos tartományán kívül esik.

## <a name="resolution"></a>Megoldás

A rakomány vagy a szállítmány jelenlegi állapotában nem hozható létre szállítólevél. A probléma javításához végezze el a következő feladatok egyikét:

- Korrigálja a szállítási hiány százalékos értékét.
- Sztornírozzon, és végezzen kiigazításokat.

### <a name="adjust-the-under-delivery-percentage"></a>Korrigálja a szállítási hiány százalékos értékét

Az alábbi módon korrigálja a szállítási hiány százalékos értékét.

1. Lépjen a **Kinnlevőségek \> Rendelések \> Minden rendelés** részre.
1. Válassza ki azt az értékesítési rendelést, amelynél nem tud szállítólevelet feladni a rakományhoz.
1. Az  **Értékesítési rendelés sorai** lapon válassza ki az értékesítési rendelésnek azt a sorát, amely meghaladja a szállítási hiány százalékos arányát.
1. A  **Sor részletei** lapon válassza ki a **Szállítás** lehetőséget.
1. A **Szállítási hiány** mezőben állítson be olyan, nagyobb százalékértéket, amely megfelelő a rakománymennyiséggel szemben kitárolt mennyiségnek; így a rendszer létre tudja hozni a szállítólevelet.

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
