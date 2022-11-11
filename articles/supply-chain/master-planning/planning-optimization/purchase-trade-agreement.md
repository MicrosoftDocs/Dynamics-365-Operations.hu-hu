---
title: Alaptervezés a beszerzésre vonatkozó kereskedelmi megállapodásokkal
description: Ez a témakör azt írja le, hogyan találhatja meg az alaptervezés a tervezett rendelések szállítóját és/vagy átfutási idejét a beszerzési kereskedelmi megállapodásokban található legjobb ár vagy átfutási idő alapján.
author: t-benebo
ms.date: 08/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2020-05-29
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: c36827738b13d5ca71da910d32e8877c1a408f62
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/03/2022
ms.locfileid: "9740985"
---
# <a name="master-planning-with-purchase-trade-agreements"></a>Alaptervezés a beszerzésre vonatkozó kereskedelmi megállapodásokkal

[!include [banner](../../includes/banner.md)]

Ez a témakör azt írja le, hogyan találhatja meg az alaptervezés a tervezett rendelés szállítóját és/vagy átfutási idejét, az adott termékhez meghatározott valamennyi beszerzési kereskedelmi megállapodás között megtalálható legjobb ár vagy átfutási idő alapján.

## <a name="turn-the-purchase-trade-agreements-for-planning-optimization-feature-on-or-off"></a>A Beszerzés – kereskedelmi megállapodások tervezési optimalizálási funkció be- és kikapcsolása

A funkció használatához be kell kapcsolva lennie a rendszeren. Az Ellátásilánc-kezelés 10.0.29-es verziója szerint a funkció kötelező, és nem lehet kikapcsolni. Ha 10,0,29-esnél régebbi verziót futtat, *·*[akkor](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) a rendszergazdák be- vagy kikapcsolhatják ezt a funkciót, ha a Szolgáltatáskezelés munkaterületén keresi a Beszerzés – tervezési optimalizálási funkciót.

## <a name="prepare-your-system-to-evaluate-purchase-trade-agreements-during-master-planning"></a>A rendszer előkészítése a beszerzési kereskedelmi megállapodások értékelésére az alaptervezés során

A következő lépések szerint konfigurálhatja úgy a rendszert, hogy a beszerzési kereskedelmi megállapodásokat kiértékelő alaptervezést alkalmazza.

1. Ugorjon az **Alaptervezés \> Beállítás \> Alaptervezés paraméterei** pontra. A **Tervezett rendelések** lap **Szállító** szakaszában adja meg a következő értékeket:

    - **Kereskedelmi megállapodás keresése** – Ezt a lehetőséget állítsa **Igen** értékre a beszerzési kereskedelmi megállapodások alaptervezésbe való befoglalásához.
    - **Keresési feltétel** – Válassza ki azt a tényezőt, amellyel rangsorolni kívánja az egyes beszerzési kereskedelmi megállapodásokat: **minimális átfutási idő** vagy **legalacsonyabb egységár**.

1. Nyissa meg a **Beszerzés és forrás \> Beállítás \> Árak és engedmények \> Ár/engedmény aktiválása** elemet, és győződjön meg arról, hogy a **Szállító** beállítás **Igen** értékre van állítva.
1. Nyissa meg a **Termékinformáció-kezelés \> Beállítás \> Dimenzió- és változatcsoportok \> Tárolásidimenzió-csoportok** elemet, és válassza ki azt a tárolásidimenzió-csoportot, amely azokra a termékekre vonatkozik, amelyekre nézve az alaptervezésnek ki kell értékelnie a beszerzési kereskedelmi megállapodásokat. Győződjön meg róla, hogy a csoport minden megfelelő tárolási dimenziója be van pipálva a **Beszerzési árakra** oszlopban. Ismételje meg ezt a lépést minden egyéb releváns tárolásidimenzió-csoportra.

## <a name="prepare-a-released-product-to-evaluate-purchase-trade-agreements-during-master-planning"></a>A kiadott termék előkészítése a beszerzési kereskedelmi megállapodások értékelésére az alaptervezés során

Miután a rendszer készen áll az előző szakaszban ismertetett módon, kövesse az alábbi lépéseket, és győződjön meg arról, hogy az ehhez a szolgáltatáshoz használni kívánt valamennyi termék helyesen van-e beállítva.

1. Kattintson ide: **Termékinformációk kezelése \> Termékek \> Kiadott termékek**, és nyisson meg egy cél terméket.
1. Győződjön meg arról, hogy a **Beszerzés** gyorslapon nem rendel hozzá szállítót a **Szállító** mezőben.
1. A Műveleti ablakmodulon a **Terv** lapon, a **Fedezet** csoportban válassza a **Cikkfedezet** lehetőséget a kiválasztott termék **Cikkfedezet** lapjának megnyitásához. Ellenőrizze a következő beállításokat:

    - Az **Általános** lapon beállíthatja a szállítói felülírásokat. Ha azt szeretné, hogy az alaptervezés a beszerzési kereskedelmi megállapodások használatával jelöljön ki egy szállítót, **akkor** a Szállítói felülbírálásokat meg kell akadályozni a Meghatározott beállítás használata jelölőnégyzet törlésével.
    - Az **Átfutási idő** lapon beállíthatja az átfutási idők felülbírálását. Ha azt szeretné, hogy az alaptervezés beszerzési kereskedelmi megállapodásokkal válassza ki az átfutási időket, meg kell akadályozni az átfutási idő felülbírálatát. Törölje a jelet a jelölőnégyzetből minden olyan átfutásiidő-típusnál, amelyet ki szeretne választani a beszerzési kereskedelmi megállapodások használatával (**Beszerzés**, **Termelés** és/vagy **Átvitel**).

1. Zárja be a **Cikkfedezet** lapot, hogy visszatérjen a kiválasztott termékkel kapcsolatos részletek lapjához.
1. A műveleti ablak **Terv** lapjának **Előrejelzés** csoportjában válassza az **Ellátási előrejelzés** elemet az **Ellátási előrejelzés** lap megnyitásához. Győződjön meg róla, hogy az itt látható sor nem tartalmaz értéket a **Szállítói számla** oszlopában.
1. Zárja be a **Ellátási előrejelzés** lapot, hogy visszatérjen a kiválasztott termékkel kapcsolatos részletek lapjához.
1. A Művelet ablaktábla **Beszerzés** lapjának **Kereskedelmi megállapodások** csoportjában válassza a **Kereskedelmi megállapodások megtekintése** elemet. Győződjön meg róla, hogy minden megfelelő beszerzési kereskedelmi megállapodás szerepel a listán. Ügyeljen arra is, **hogy az** **Átfutási** idő figyelmen kívül hagyása beállítás minden olyan szerződéshez, ahol az alaptervezés az adott szerződéshez megadott átfutási időt használja.
1. A Műveleti ablakmodulon a **Terv** lapon, a **Rendelésbeállítások** csoportban válassza a **Alapértelmezett rendelésbeállítások** lehetőséget a kiválasztott termék **Alapértelmezett rendelésbeállítások** lapjának megnyitásához. A **Beszerzési rendelés** gyorslapon tekintse meg a **Beszerzési átfutási idő** mező értékét. Ha nincs megadva a cikkfedezet átfutási ideje felülbírálása, **·** **az alaptervezés ezt az értéket használja, amikor olyan kereskedelmi megállapodásokat jelöl ki, amelyeknél az Átfutási idő figyelmen kívül hagyása beállítás Igen értékre van állítva.** Ennek megfelelően módosítania kell ezt az értéket a szükséges módon.
1. Ismételje meg az eljárást minden érintett termék esetén.

> [!NOTE]
> Az alaptervezés támogatja a több pénznemből álló beszerzési kereskedelmi megállapodásokat. Amikor a **Legalacsonyabb egységár** beállítás használatával keres kereskedelmi megállapodást, a rendszer figyelembe veszi a különböző pénznemekkel rendelkező kereskedelmi megállapodási sorokat, amennyiben a kereskedelmi megállapodási sor pénzneméhez és a jogi személy könyvelési pénzneméhez meg lett határozva egy árfolyam. Ellenkező esetben a rendszer figyelmen kívül hagyja a kereskedelmi megállapodás sorát, és hibaüzenetet jelenik meg az alaptervezés során. Emiatt az alaptervezés minden olyan beszerzési kereskedelmi megállapodási sor adatát tartalmazni fogja, amelyekben az árak átválthatók a könyvelési pénznemre. Fontos megjegyezni, hogy a kerekítési szabályokat nem veszik figyelembe a kereskedelmi megállapodás sorárának átalakítása során.

## <a name="examples-of-how-master-planning-finds-vendor-and-lead-times"></a>Példák az alaptervezés szállítói és átfutási időkre vonatkozó megkeresii

A következő táblázat bemutatja, hogy a kiadott termék és a hozzájuk kapcsolódó beszerzési kereskedelmi megállapodások különböző beállításai hogy befolyásolják a létrejövő tervezett beszerzési rendeléshez tartozó értékeket. A **két** jobboldali oszlopban félkövér értékek jelentik az alaptervezés által kiválasztott értékeket. A többi oszlop **_félkövér és dőlt_** értékei az egyes sorokhoz létrejövő értékeket létrehozó beállítások.

| Kibocsátott termék: Szállító | Alapértelmezett rendelési beállítás: Átfutási idő | Cikkfedezeti tétel: Szállító felülbírálása | Cikkfedezeti tétel: Átfutási idő felülbírálása | Kereskedelmi megállapodás: Szállító | Kereskedelmi megállapodás: Átfutási idő | Kereskedelmi megállapodás: Átfutási idő figyelmen kívül hagyása | Létrejövő szállító | Létrejövő átfutási idő |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| ***US001** _ | _*_1_*_ | Nem | Nem | US003 | 3 | Nem | _ *US001** | **1** |
| US001 | 1 | ***Igen: US002** _ | _*_Igen: 2_*_ | US003 | 3 | Nem | _ *US002** | **2** |
| *(Üres)* | 1 | Nem | Nem | ***US003** _ | _*_3_*_ | Nem | _ *US003** | **3** |
| *(Üres)* | ***1** _ | Nem | Nem | _*_US003_*_ | 3 | Igen | _ *US003** | **1** |
| *(Üres)* | ***1** _ | _*_Igen: US002_*_ | Nem | US003 | 3 | Nem | _ *US002** | **1** |
| *(Üres)* | ***1** _ | _*_Igen: US002_*_ | Nem | US003 | 3 | Nem | _ *US002** | **1** |
| *(Üres)* | 1 | Nem | Igen: 2 | ***US003** _ | _*_3_*_ | Nem | _ *US003** | **3** |
| *(Üres)* | 1 | Nem | ***Igen: 2** _ | _*_US003_*_ | 3 | Igen | _ *US003** | **2** |

## <a name="additional-resources"></a>További erőforrások

- [Beszerzési szerződések](../../procurement/purchase-agreements.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
