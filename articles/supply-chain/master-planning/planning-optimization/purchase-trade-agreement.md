---
title: Alaptervezés a beszerzésre vonatkozó kereskedelmi megállapodásokkal
description: Ez a témakör azt mutatja be, hogyan lehet megkeresni a tervezett rendelés szállítói és/vagy átfutási idejét a beszerzési kereskedelmi megállapodásokban található legjobb ár vagy átfutási idő alapján.
author: t-benebo
ms.date: 06/29/2020
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
ms.openlocfilehash: cb790836042506ed6676ee7edbd8bba58191519b
ms.sourcegitcommit: ad1afc6893a8dc32d1363395666b0fe1d50e983a
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/23/2022
ms.locfileid: "8468413"
---
# <a name="master-planning-with-purchase-trade-agreements"></a>Alaptervezés a beszerzésre vonatkozó kereskedelmi megállapodásokkal

[!include [banner](../../includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet megkeresni a tervezett rendelés szállítói és/vagy átfutási idejét az adott projekthez megadott beszerzési kereskedelmi megállapodásokban található legjobb ár vagy átfutási idő alapján.

## <a name="turn-on-the-purchase-trade-agreements-for-planning-optimization-feature"></a>A beszerzési kereskedelmi megállapodások bekapcsolása a tervezés optimalizálása funkcióhoz

A funkció használata előtt be kell azt kapcsolnia saját rendszerében. A rendszergazdák használhatják a [Funkciókezelés](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) munkaterületet a funkció állapotának ellenőrzéséhez, és szükség esetén bekapcsolásához. A funkció a következő módon jelenik meg:

- **Modul:** *Alaptervezés modul*
- **Funkció neve:** *A beszerzési kereskedelmi megállapodások bekapcsolása a tervezés optimalizálása funkcióhoz*

## <a name="prepare-your-system-to-evaluate-purchase-trade-agreements-during-master-planning"></a>A rendszer előkészítése a beszerzési kereskedelmi megállapodások értékelésére az alaptervezés során

A következő lépések végrehajtásával konfigurálhatja a rendszert úgy, hogy a beszerzési kereskedelmi megállapodásokat kiértékelő tervezési optimalizációt alkalmazzon.

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

    - Az **Általános** lapon beállíthatja a szállítói felülírásokat. Ha azt szeretné, hogy a tervezés optimalizálása a beszerzési kereskedelmi megállapodások segítségével válassza ki a szállítót, akkor a szállítói felülbírálást meg kell akadályoznia a **Specifikus beállítások használata** jelölőnégyzet bejelölésének megszüntetésével.
    - Az **Átfutási idő** lapon beállíthatja az átfutási idők felülbírálását. Ha azt szeretné, hogy a tervezés optimalizálása a beszerzési kereskedelmi megállapodások segítségével adja meg az átfutási időket, akkor az átfutási idő felülbírálását meg kell előznie. Törölje a jelet a jelölőnégyzetből minden olyan átfutásiidő-típusnál, amelyet ki szeretne választani a beszerzési kereskedelmi megállapodások használatával (**Beszerzés**, **Termelés** és/vagy **Átvitel**).

1. Zárja be a **Cikkfedezet** lapot, hogy visszatérjen a kiválasztott termékkel kapcsolatos részletek lapjához.
1. A műveleti ablak **Terv** lapjának **Előrejelzés** csoportjában válassza az **Ellátási előrejelzés** elemet az **Ellátási előrejelzés** lap megnyitásához. Győződjön meg róla, hogy az itt látható sor nem tartalmaz értéket a **Szállítói számla** oszlopában.
1. Zárja be a **Ellátási előrejelzés** lapot, hogy visszatérjen a kiválasztott termékkel kapcsolatos részletek lapjához.
1. A Művelet ablaktábla **Beszerzés** lapjának **Kereskedelmi megállapodások** csoportjában válassza a **Kereskedelmi megállapodások megtekintése** elemet. Győződjön meg róla, hogy minden megfelelő beszerzési kereskedelmi megállapodás szerepel a listán. Győződjön meg arról is, hogy az **Átfutási idő figyelmen kívül hagyása** beállítás **Nem** értékre van állítva minden olyan megállapodás esetében, amelynél az adott szerződéshez megadott átfutási időt használni szeretné a tervezés optimalizálása során.
1. A Műveleti ablakmodulon a **Terv** lapon, a **Rendelésbeállítások** csoportban válassza a **Alapértelmezett rendelésbeállítások** lehetőséget a kiválasztott termék **Alapértelmezett rendelésbeállítások** lapjának megnyitásához. A **Beszerzési rendelés** gyorslapon tekintse meg a **Beszerzési átfutási idő** mező értékét. Ha nincs meghatározva a cikkfedezeti átfutási idő felülbírálása, akkor a tervezés optimalizálása ezt az értéket fogja használni, amikor olyan kereskedelmi megállapodásokat jelöl ki, amelyeknél az **Átfutási idő figyelmen kívül hagyása** beállítás **Igen** értékre van állítva. Ennek megfelelően módosítania kell ezt az értéket a szükséges módon.
1. Ismételje meg az eljárást minden érintett termék esetén.

> [!NOTE]
> A több pénznemű beszerzési kereskedelmi megállapodások tervezésének optimalizálása. Amikor a **Legalacsonyabb egységár** beállítás használatával keres kereskedelmi megállapodást, a rendszer figyelembe veszi a különböző pénznemekkel rendelkező kereskedelmi megállapodási sorokat, amennyiben a kereskedelmi megállapodási sor pénzneméhez és a jogi személy könyvelési pénzneméhez meg lett határozva egy árfolyam. Ellenkező esetben a rendszer figyelmen kívül hagyja a kereskedelmi megállapodás sorát, és hibaüzenetet jelenik meg az alaptervezés során. Emiatt az alaptervezés minden olyan beszerzési kereskedelmi megállapodási sor adatát tartalmazni fogja, amelyekben az árak átválthatók a könyvelési pénznemre. Fontos megjegyezni, hogy a kerekítési szabályokat nem veszik figyelembe a kereskedelmi megállapodás sorárának átalakítása során.

## <a name="examples-of-how-planning-optimization-finds-vendor-and-lead-times"></a>A példák arra, ahogy a tervezés optimalizálása a szállítói és az átfutási időket észleli

A következő táblázat bemutatja, hogy a kiadott termék és a hozzájuk kapcsolódó beszerzési kereskedelmi megállapodások különböző beállításai hogy befolyásolják a létrejövő tervezett beszerzési rendeléshez tartozó értékeket. A két jobb szélső oszlop **félkövér** értékei a tervezés optimalizálása képernyőn kiválasztott értékek. A többi oszlop **_félkövér és dőlt_** értékei az egyes sorokhoz létrejövő értékeket létrehozó beállítások.

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

[Beszerzési szerződések](../../procurement/purchase-agreements.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
