---
title: A mennyiség nem csökkenthető értékesítési rendelés visszavonásakor
description: A mennyiség nem csökkenthető értékesítési rendelés visszavonásakor.
author: hja-ms
ms.date: 5/17/2021
ms.topic: troubleshooting
ms.search.form: SalesTable_SalesCancelOrder, SalesTableListPage_SalesCancelOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: hja
ms.search.validFrom: 2021-05-17
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 1a2cc9c9fd3d085508fc652bc9ee0a352d869dee
ms.sourcegitcommit: a02d3d64c899f8554b74342d5a1856d824bf1abe
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/11/2021
ms.locfileid: "6230836"
---
# <a name="the-quantity-cant-be-reduced-when-a-sales-order-is-canceled"></a>A mennyiség nem csökkenthető értékesítési rendelés visszavonásakor

Hibakód: SYS138831

## <a name="symptoms"></a>Tünetek

A rendszer a következő hibaüzenetet jeleníti meg:

> A mennyiség nem csökkenthető. A rendelésben szereplő készlettranzakciók száma túl alacsony, mert a mennyiségre vagy annak egy részére kimeneti rendelés vagy termelési rendelés hivatkozik, vagy más tranzakciókkal van megjelölve.

## <a name="cause"></a>Ok

Ha van munka egy értékesítési rendeléshez van társítva, akkor az értékesítési rendelés nem törölhető, amíg a munka nincs érvénytelenítve és visszavonva. Ez a követelmény akkor is érvényes, ha az értékesítési rendeléshez társított munka le van zárva.

## <a name="resolution"></a>Megoldás

A probléma javításához végezze el a következő feladatok egyikét:

1. Nyitott munka visszavonása.
1. Törölje a rakományt.
1. A kitárolt mennyiség csökkentése.

### <a name="cancel-open-work"></a>Nyitott munka visszavonása

Nyitott munka megszakításához kövesse az alábbi lépéseket.

1. Menjen a **Raktárkezelés \> Időszakos feladatok \> Tisztítás \> Munka megszakítása** menühöz.
1. A **Munkaazonosító** mezőben adja meg annak a munkának az azonosítóját, amelyről törölni szeretne, és amelynek jelenleg **Munkaállapot** értéke *Nyitott*, *Folyamatban*, *Megszakítva*, *Kombinálva* vagy *Lezárva*.
1. Válassza ki az **OK** lehetőséget.
1. Válassza az **Igen** lehetőséget a munka megszakításához.

### <a name="delete-the-load"></a>Törölje a terhelést

A terhelés törléséhez kövesse az alábbi lépéseket.

1. Ugorjon az **Értékesítés és marketing \> Értékesítési rendelések \> Minden értékesítési rendelés** pontra.
1. Nyissa meg a megfelelő értékesítési rendelést.
1. Az **Értékesítési rendelés sorai** gyorslapon válassza ki a **Raktár \> Munka részletes adatai** lehetőséget.
1. A **Munka** lapon a Művelet ablaktábla **Munka** lapjának **Munka** csoportjában válassza a **Munka visszavonása** elemet.
1. Győződjön meg arról, hogy a **Munka állapota** mezője *Érvénytelenve* beállítású.
1. Zárja be a **Munka** oldalt.
1. Az értékesítési rendelés részleteit tartalmazó lap **Értékesítésirendelés-sorok** gyorslapján válassza a **Raktár \> Rakomány részletei** lehetőséget.
1. A Műveletpanelen válassza ezután a **Törlés** elemet.
1. Válassza az **Igen** lehetőséget a rakomány törlésének megerősítéséhez.
1. Zárja be a **Rakomány** oldalt.

### <a name="reduce-the-picked-quantity"></a>A kitárolt mennyiség csökkentése

A ki nem választott mennyiség csökkentéséhez kövesse ezeket a lépéseket a munka visszavonása után.

1. Ugorjon az **Értékesítés és marketing \> Értékesítési rendelések \> Minden értékesítési rendelés** pontra.
1. Nyissa meg a megfelelő értékesítési rendelést.
1. Az **Értékesítésirendelés-sorok** gyorslapon válassza az eszköztáron a **Sor frissítése \> Kitárolás** lehetőséget.
1. Válassza ki a **Kitárolás** oldalon a **Tranzakciók** szakaszban a **Kiadás állapota** mezőben beállítása *Kitárolva*.
1. A **Tranzakciók** szakaszban válassza a **Kitárolási sor hozzáadása** lehetőséget az eszköztárról.
1. A **Kitárolási sorok** szakaszban válassza az **Összes kitárolás megerősítése** lehetőséget az eszköztárról.
1. Zárja be a **Kitárolás** oldalt.
1. Az értékesítési rendelés részletei oldal műveleti ablaktábláján, az **Értékesítési rendelés** lapon, a **Karbantartás** csoportban válassza ki az **Érvénytelenítés** lehetőséget.
1. Válassza az **Igen** lehetőséget az értékesítési rendelés érvénytelenítéséhez.
