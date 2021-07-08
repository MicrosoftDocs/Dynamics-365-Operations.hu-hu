---
title: A szállítókód nem engedélyezett adott termékhez és dátumhoz
description: Ha egy tervezett rendelést meg szeretne határozni, vagy ha sort ad hozzá egy beszerzési rendeléshez, akkor olyan hibaüzenet jelenik meg, amely szerint a szállítókód nincs engedélyezve egy termékhez és dátumhoz.
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPO_ReqTransPoMarkFirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: e6b1189e4fedfdb029f4b4503f0635133df9d87e
ms.sourcegitcommit: 18ca2df785e9656fdd4e8c0734eca2b2624fda10
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/22/2021
ms.locfileid: "6294095"
---
# <a name="vendor-code-isnt-authorized-for-a-specific-product-and-date"></a>A szállítókód nem engedélyezett adott termékhez és dátumhoz

Hibakód: SYP4881415

## <a name="symptoms"></a>Tünetek

Amikor tervezett rendelést próbál megerősíteni, illetve sort próbál hozzáadni egy beszerzési rendeléshez, a következő hibaüzenetet kapja:

> A(z) %1 szállítói kód nincs engedélyezve %2 esetében a következőn: %3.

## <a name="cause"></a>Ok

A hiba oka, hogy az **Engedélyezett szállítók ellenőrzési módszere** mező értéke az adott terméknél *Csak figyelmeztetés* vagy *Nem megengedett*, és a szállító számára jelenleg nem engedélyezett az adott termék biztosítása.

## <a name="resolution"></a>Megoldás

A probléma megoldásához vagy tiltsa le a vonatkozó termék szállítói ellenőrzését, vagy hagyja jóvá a szállítót.

A következő lépésekkel tilthatja le a szállítói ellenőrzést egy adott terméknél.

1. Kattintson a **Termékinformációk kezelése \> Termékek \> Kiadott termékek** lehetőségre.
1. Nyissa mega releváns terméket.
1. A **Vásárlás** gyorslapon módosítsa úgy az **Engedélyezett szállítók ellenőrzési módszere** mező értékét, hogy ne *Csak figyelmeztetés* vagy *Nem megengedett* legyen.

A következő lépésekkel hagyhat jóvá egy szállítót egy adott terméknél.

1. Kattintson a **Termékinformációk kezelése \> Termékek \> Kiadott termékek** lehetőségre.
1. Nyissa meg a releváns cikket.
1. A Művelet panel **Vásárlás** lapján lévő **Engedélyezett szállító** csoportban válassza a **Beállítás** lehetőséget.
1. Az **Engedélyezett szállító** listaoldalon adjon hozzá egy sort a rácshoz, majd állítsa be hozzá a következő értékeket:

    - **Szállító** – az aktuális termékhez jóváhagyni kívánt szállító kiválasztása.
    - **Hatályba lépési dátum** – az első olyan dátum kiválasztása, ahelyhez jóváhagyja a szállítót.
    - **Lejárati dátum** – az utolsó olyan dátum kiválasztása, ahelyhez jóváhagyja a szállítót.

További információk: [A meghatározott termékek szállítójának jóváhagyása](/dynamics365/supply-chain/procurement/tasks/approve-vendors-specific-products.md).
