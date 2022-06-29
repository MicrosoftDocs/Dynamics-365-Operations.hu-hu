---
title: Halasztás feladási módjai
description: Ez a témakör a bevétel- és költség halasztások halasztás-feladási módjai közötti különbségeket írja le az előfizetéses számlázásban.
author: JodiChristiansen
ms.date: 6/10/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-11-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: c66ed1c38251140dd798c39797873ceb5f7121a4
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/15/2022
ms.locfileid: "9017474"
---
# <a name="deferral-posting-methods"></a>Halasztás feladási módjai

Ez a témakör a bevétel- és költség halasztások halasztás-feladási módjai közötti különbségeket írja le az előfizetéses számlázásban.

A Bevételi **és kiadási halasztások** **·** **paraméterei oldalon a halasztás feladási módja a mérleg és az eredmény**. Az ebben a példában lévő példában le lehet magyarázni a két módszer közötti különbségeket, valamint az egyik módszer vagy a másik használatának okait.

A **mérleg módszere** csak két számlát használ. Ennek megfelelően a program kisebb beállításokat is érintett. Az **eredmény módszerhez** a tranzakció típusától függően két további számla is van: **·** **a** bevételek, az engedmények és a költségek kezdeti elszámolása és elszámolása. Ezek a számlák a Halasztások **alapértelmezései** lapon vannak beállítva (**Előfizetéses \> számlázás – Bevétel és költség halasztások \> beállítása**). Bár a példa a halasztott bevételre fókuszál, ugyanezt a fogalmat lehet alkalmazni a halasztott engedményekkel és a halasztott költségekkel.

## <a name="example"></a>Példa

Az 1. értékesítési számlán összesen $3,000 bevétele van. A következő táblázatok az értékesítési számla feladott felosztását mutatják.

**Mérleg módszere**

| Típus | Számla | Terhelés | Jóváírás|
|---|---|---|---|
| Terhelés | Kinnlevőségek | 3,000.00 | |
| Jóváírás | Halasztott bevétel | | 3,000.00 |

**Eredmény módja**

| Típus | Számla | Terhelés | Jóváírás |
|---|---|---|---|
| Terhelés | Kinnlevőségek | 3,000.00 | |
| Terhelés | Árbevétel-elismert ellenszámla | 3,000.00 | |
| Jóváírás | Halasztott bevétel | | 3,000.00 |
| Jóváírás | Kezdeti bevétel-kimutatás | | 3,000.00 |

A 2. értékesítési számlán összesen $2,000 és nincs halasztott bevétele.

| Típus | Számla | Összeg |
|---|---|---|
| Terhelés | Kinnlevőségek | 3,000.00 |
| Jóváírás | Bevétel | 3,000.00 |

**Az 1. és a 2. értékesítési számla mérleg-metódusának összesítései kombinálva**

| Számla | Terhelés | Jóváírás |
|---|---|---|
| Kinnlevőségek | 5,000.00 | |
| Bevétel | | 2,000.00 |
| Halasztott bevétel | | 3,000.00 |

A mérleg **módszer** használata esetén nem lehet olyan könnyen látni egy időszak bruttó bevételét. A bevétel egy részét a halasztott **bevételi számlára könyveli** a rendszer. Ne feledje, hogy a bevételeket minden időszakban elismerve több tartozik és követel tételek vannak a Halasztott **bevétel számlán**. Egy adott időszak bruttó bevétele vegyes lesz a bevétel-kimutatás ins/outs kimutatásával.

**Az 1. és a 2. értékesítési számla eredmény-számítási módszerének összesítései kombinálva**

| Számla | Terhelés | Jóváírás |
|---|---|---|
| Kinnlevőségek | 5,000.00 | |
| Bevétel | | 5,000.00 |
| Bevétel ellentételezése | 3,000.00 | |
| Halasztott bevétel | | 3,000.00 |

Minden bevétel az eredmény bevételi számlára **kerül**. Ezt követően a halasztott bevétel átkerül az eredménykiegyenlből a mérlegbe. A bruttó bevétel könnyen látható, mivel mindent felad a bevételi **számlára**. A bruttó bevétel egy része azonban halasztva van. Emiatt átkerül a **Halasztott** bevételi számlára, és később ismeri fel.

Az **Eredmény** **·** **módszerrel** a Bevételszámla és a Bevétel ellenszámlán $5,000 a halasztott nettó bevételt és a halasztott nettó bevételt $2,000. Bár az eredmény **módszer** egyszerűbbé teszi a jelentéskészítést, több számlát is be lehet állítani.
