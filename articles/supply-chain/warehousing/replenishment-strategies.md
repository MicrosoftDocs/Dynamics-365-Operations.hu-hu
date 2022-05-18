---
title: Feltöltési stratégiák
description: Ez a témakör a feltöltési stratégiákról tartalmaz tájékoztatást, és bemutatja, hogyan lehet használni a Feltöltési stratégia mezőt a hullám igényfeltöltési sablon soraiban a feltöltés mód kiválasztásához.
author: Mirzaab
ms.date: 10/29/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-10-29
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 1aa48f231c5d98a22fa989fb6e6996b972be9089
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/03/2022
ms.locfileid: "8669880"
---
# <a name="replenishment-strategies"></a>Feltöltési stratégiák

[!include [banner](../includes/banner.md)]

A **Feltöltési sablonok** lapon megadott sablonok között szerepelnek a hullám igényfeltöltési sablon sorai, amelyek segítségével kiválaszthatja a feltöltés módját. Minden sorban szerepel egy **Feltöltési stratégia** mező.

A *Hullám igénymennyiségi* stratégia az alapértelmezett stratégia. Ez az a feltöltési stratégia, amelyet a **Feltöltési stratégia** mező bevezetése előtt alkalmaztak. A feltöltési helyutasításokkal megkeresheti azokat a helyeket, amelyeket fel lehet tölteni. Ezt követően feltölti ezeket a helyeket mindaddig, amíg az igény ki nem lesz elégítve.

A *Maximális helykapacitási* stratégia néhány új funkciót mutat be. A *Hullám igénymennyiségi* stratégiához hasonlóan ez a stratégia a feltöltési helyutasításokar használja a feltöltésre használható helyek megtalálására, majd ezeket a helyeket addig tölti fel, amíg az igény ki nem lesz elégítve. Különbözik a *Hullám igénymennyiségi* stratégiától, mivel a program az összes feltöltött helyet az adott hely készletezési korlátainak megfelelően tölti fel a maximális kapacitásnak megfelelően. A *Maximális helykapacitási* stratégia megpróbálja létrehozni a szükséges mennyiséget, plusz némi extrát, hogy kitöltse a feltöltendő helyeket. Bizonyos esetekben azonban előfordulhat, hogy ez a kísérlet nem sikerül. Előfordulhat például, hogy az ömlesztett helyek nem rendelkeznek elegendő készlettel a további mennyiség fedezéséhez. Ezekben az esetekben a rendszer észleli a hibát, és megpróbálja helyreállítani.

A főszezon egy példa arra a helyzetre, amikor a *Maximális helykapacitási* stratégia előnyös a *Hullám igénymennyiségi* stratégiához. Főszezonban előfordulhat, hogy egyes cikkeket nagy mennyiségben értékesítenek. Ezért előfordulhat, hogy a lehető legnagyobb mértékben fel kell töltenie a megfelelő kitárolási helyeket a feltöltéshez létrehozott munkaazonosítók számának csökkentéséhez.

> [!IMPORTANT]
> Ahhoz, hogy teljes mértékben kihasználja a *Maximális helykapacitási* stratégiát, újra meg kell határoznia a megfelelő helyekre vonatkozó készletezési korlátokat. Ellenkező esetben ez a stratégia ugyanúgy működik, mint a *Hullám igénymennyiségi* stratégia.

## <a name="turn-on-the-replenish-to-max-based-on-stocking-limits-feature"></a>A Feltöltés maximumig a készletezési korlátok funkció alapján bekapcsolása

A funkció használata előtt be kell azt kapcsolnia saját rendszerében. A rendszergazdák használhatják a [Funkciókezelési](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) munkaterület ezen funkció állapotának ellenőrzéséhez, és szükség esetén bekapcsolásához. A funkció a következő módon jelenik meg:

- **Modul:** *Raktárkezelés*
- **Funkció neve:** *Feltöltés maximumig a készletezési korlátok funkció alapján*

## <a name="set-up-replenishment-strategies"></a>Feltöltési stratégiák beállítása

A sablonok eléréséhez menjen a: **Raktárkezelés \> Beállítás \> Feltöltés \> Feltöltési sablonok** lehetőségre. Az **Áttekintés** részben válassza ki vagy hozzon létre egy olyan hullám igényfeltöltési sablont, amelynél a **Feltöltési típus** mező a *Hullámigény* lehetőségre van állítva. Ezt követően állítsa be a feltöltési sablon sorait a **Feltöltési sablon részletei** szakaszba. A **Feltöltési stratégia** mezőben válassza ki a használni kívánt feltöltési stratégiát mindegyik sorhoz.

![Feltöltési sablonok oldal.](media/ReplenTempWaveDmdMaxLocCap.png "Feltöltési sablonok oldal")

Ha a **Feltöltési stratégia** oszlop nem jelenik meg a **Feltöltési sablon részletei** szakasz rácsában, győződjön meg arról, hogy a funkció be van kapcsolva, és a kijelölt feltöltési sablonnak a feltöltési típusa *Hullámigény*.

> [!NOTE]
> A *Hullám igénymennyiségi* stratégia az alapértelmezett stratégia. Éppen ezért csak akkor kell frissítenie a feltöltési sablon sorait, ha helyette használni szeretné a *Maximális helykapacitási* stratégiát.

## <a name="example-scenarios"></a>Példaforgatókönyvek

### <a name="example-1"></a>1. példa

Ebben a példában csak egy feltöltési sablon van, amelynek csak egy feltöltési sablonsora van.

Létrehoz egy értékesítési rendelést 130 darabnyi A0001-es cikkről. Mielőtt elküldené a rendelést a raktárba, a következő módon kell beállítani a raktárat:

- Csak egy ömlesztett tárolóhely van, és a rendelkezésre álló készlet 500 db.
- Három kitárolási hely van, amelyek mindegyikének 100 darabos készletezési korlátja van. (Ne felejtse el, hogy a készletezési korlátokat muszáj megadni a *Maximális helykapacitás* stratégiához.)
- A feltöltés elhelyezési helyek ugyanazok lesznek, mint az értékesítési kitárolási helyek.
- A feltöltési egység egy doboz (1 doboz = 20 db).

A rendelés időpontjában a következő készlet szerepel az értékesítési kitárolási helyeken:

- **Kitárolás-001:** 20 db (1 doboz)
- **Kitárolás-002:** 0 db
- **Kitárolás-003:** 0 db

A feltöltési stratégia kezdetben a *Hullám igénymennyiség* lehetőségre van állítva.

Miután elküldte az értékesítési rendelést a raktárnak, és a hullámfeldolgozás a hullámhoz fut, a következő feltöltési munkákat kapja:

- **Feltöltési munka 1:** Válasszon ki 4 dobozt az ömlesztett tárolóhelyről, majd helyezze őket a kitárolás-001 helyre.
- **Feltöltési munka 2:** Válasszon ki 2 dobozt az ömlesztett tárolóhelyről, majd helyezze őket a kitárolás-002 helyre.

Két feltöltési munkaazonosítót kap, mivel két helyet kell feltöltenie, és az összevont feltöltések nem támogatottak.

Ha a feltöltési stratégiát a *Maximális helykapacitás* lehetőségre állítja, akkor a következő feltöltési munkát kapja:

- **Feltöltési munka 1:** Válasszon ki 4 dobozt az ömlesztett tárolóhelyről, majd helyezze őket a kitárolás-001 helyre.
- **Feltöltési munka 2:** Válassza ki az 5 dobozt az ömlesztett tárolóhelyről, majd helyezze őket a kitárolás-002 helyre.

[![1. példa](media/ReplenTemp_example_1.png "1. példa")](media/ReplenTemp_example_1_large.png)

### <a name="example-2"></a>2. példa

Ez a példa azt mutatja meg, hogy mi történik, ha az ömlesztett tárolóhely nem rendelkezik elegendő készlettel a további mennyiség befogadásához. Ugyanazt a forgatókönyvet használja, mint az 1. példa, de az ömlesztett tárolóhelyhez 160 db (8 doboz) tartozik.

A *Hullám igénymennyiségi* stratégia ugyanazt a munkát hozza létre, mint az 1. példában.

Mivel azonban a *Maximális helykapacitás* stratégia megpróbálja létrehozni az 1. példában szereplő munkaazonosítókat, előfordulhat, hogy nem fog sikerülni. Ekkor a rendszer megkísérli a helyreállítást.

A helyutasításoknál a feltöltési kitárolás **Felosztás engedélyezése** lehetőségétől függően a következő két eredményt kaphatja:

- Ha a **Felosztás engedélyezése** lehetőség értéke *Igen*, akkor a következő feltöltési munka jön létre:

    - **Feltöltési munka 1:** Válasszon ki 4 dobozt az ömlesztett tárolóhelyről, majd helyezze őket a kitárolás-001 helyre.
    - **Feltöltési munka 2:** Válasszon ki 4 dobozt az ömlesztett tárolóhelyről, majd helyezze őket a kitárolás-002 helyre.

- Ha a **Felosztás engedélyezése** lehetőség értéke *Nem*, akkor a következő feltöltési munka jön létre:

    - **Feltöltési munka 1:** Válasszon ki 4 dobozt az ömlesztett tárolóhelyről, majd helyezze őket a kitárolás-001 helyre.
    - **Feltöltési munka 2:** Válasszon ki 2 dobozt az ömlesztett tárolóhelyről, majd helyezze őket a kitárolás-002 helyre.

Az eredmények a munka létrehozásakor rendelkezésre álló információktól függnek. Ha a helyutasításoknál a feltöltési kitárolás **Felosztás engedélyezése** lehetősége *Igen* értékre van állítva , akkor a 160 db-ot sikerült megtalálni. Tehát az adott mennyiséghez létrehozhatja a munkát. Ha azonban a **Felosztás engedélyezése** lehetőség *Nem* értékre van állítva, akkor nincs meg a 160 db. Mivel a feltölteni kívánt további mennyiség 3 doboz, ezért a többlet mennyiséget elhagyja, majd újra megpróbálja az eredeti mennyiséggel.

[![2. példa](media/ReplenTemp_example_2.png "2. példa")](media/ReplenTemp_example_2_large.png)

Ahhoz, hogy a maximális mennyiséget eljuttathassa a feltöltési helyekre, a **Felosztás engedélyezése** lehetőséget *Igen* értékre a helyutasításoknál a feltöltési kitároláshoz.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]