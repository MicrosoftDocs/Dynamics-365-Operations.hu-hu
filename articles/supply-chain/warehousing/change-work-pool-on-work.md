---
title: Munkagyűjtő módosítása a munkán
description: Ez a cikk bemutatja, hogy hogyan módosíthatja a meglévő munka munkakészletét a Munkakészlet módosítása gombbal.
author: Mirzaab
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSWorkPool,WHSWorkTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: global
ms.author: mirzaab
ms.search.validFrom: 2020-07-16
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 817b45e8f5af957801a0af04e50acf20ba16c26d
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8900622"
---
# <a name="change-work-pool-on-work"></a>Munkagyűjtő módosítása a munkán

[!include [banner](../includes/banner.md)]

Munkagyűjtők segítségével a munkát csoportokba rendezheti. Például létrehozhat egy munkagyűjtőt, hogy osztályozza azt a munkát, amelyet egy adott raktárhelyen történik.

A *Munka munkagyűjtőjének módosítása* funkció hozzáadja a **Munkagyűjtő módosítása** gombot a munkaelemek műveleti ablaktáblájához. Így a raktárkezelők egyszerűen módosíthatják a meglévő munka munkagyűjtőjét. Ez a funkció lehetővé teszi a vezetők gyors reagálását a raktári üzem szintjén, és javítja a változó helyzetekhez való alkalmazkodás képességét, valamint a munka másik munkagyűjtőbe történő áthelyezését.

## <a name="turn-the-change-work-pool-on-work-feature-on-or-off"></a>A Munkakészlet módosítása munka szolgáltatás be- és kikapcsolása

A 10.0.25-ös ellátásilánc-kezelésben ez a funkció kötelező, és nem lehet kikapcsolni. Ha 10.0.25-ösnél régebbi verziót futtat, *·*[akkor](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) a rendszergazdák be- vagy kikapcsolhatja ezt a funkciót, ha a Szolgáltatáskezelési munkaterület Munkakészlet módosítása szolgáltatását keresi.

## <a name="set-up-the-change-work-pool-on-work-feature"></a>A Munkagyűjtő módosítása a munkán funkció beállítása

Ez a funkció csak akkor használható, ha be van állítva néhány munkagyűjtő. A munkasablonokat úgy is be lehet állítani, hogy automatikusan társítson egy gyűjtőt. Ha a cikk későbbi részében ismertetett példaesetben kíván dolgozni, állítsa be a rendszert az ebben a szakaszban leírt módon.

### <a name="set-up-work-pools"></a>Munkagyűjtők beállítása

A munkagyűjtők a munkatételek típus szerinti rendszerezését teszik lehetővé. Ha a *Munkagyűjtő módosítása a munkán* funkcióban szeretne dolgozni, legalább két munkagyűjtőnek elérhetőnek kell lennie. A Munkagyűjtő megtekintéséhez és hozzáadásához kövesse az alábbi lépéseket.

1. Ugorjon a **Raktárkezelés \> Beállítás \> Munka \> Munkagyűjtők** pontra.
1. Ha az **USMF** vállalat bemutató adataival dolgozik, és a példában később végig szeretne menni a példán, két olyan munkakészletet adjon hozzá, amelyek a következő beállításokkal:

    - 1. munkagyűjtő:

        - **Munkagyűjtő azonosítója:** *Webshop*
        - **Leírás:** *Webáruház*

    - 2. munkagyűjtő:

        - **Munkagyűjtő azonosítója:** *CallCenter*
        - **Leírás:** *Hívásközpont*

1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.

### <a name="set-up-work-templates"></a>Munkasablonok beállítása

A munkasablonok mindegyikéhez beállíthat egy alapértelmezett munkagyűjtőt, ha szükséges. Minden megfelelő sablonhoz társítani kell egy munkagyűjtőt a **munkagyűjtő azonosítója** oszlopban. Ebben az esetben az adott sablon használatával létrejövő összes munkaelem automatikusan örökli a hozzárendelt munkagyűjtőt. Ha az **USMF** vállalat bemutató adataival dolgozik, és a cikk későbbi példaadatán dolgozik, kövesse ezeket a lépéseket.

1. Lépjen a **Raktárkezelés \> Beállítás \> Munka \> Munkasablonok** elemre.
1. A műveleti ablaktáblán válassza ki a **Szerkesztés** parancsot, hogy a lapot szerkesztési módba helyezze.
1. A következő értékek beállításával módosítsa a sablont:

    - **Munkasablon:** *62 Kitárolástól csomagolásig*
    - **Munkagyűjtő azonosítója:** *Webshop*

1. Válassza a **Mentés** lehetőséget.

## <a name="example-scenario"></a>Példaforgatókönyv

Ez a példa azt mutatja be, hogyan lehet módosítani egy meglévő munkaelem feldolgozási folyamát a munkagyűjtők megváltoztatásával. Az USMF **vállalat** bemutató adatait, valamint a cikk korábban ajánlott beállításait használja.

### <a name="create-a-sales-order-and-release-it-to-the-warehouse"></a>Értékesítési rendelés létrehozása és kiadása a raktárba

1. Győződjön meg róla, hogy elegendő aktuális készlet van a *A0001* és *A0002* cikkekből a *62*. raktárban. Nyissa meg a következőt: **Készletkezelés \> Lekérdezések és jelentések \> Aktuális lista**, és szerkessze az alábbiak szerint a szűrőket:

    - A **Raktár** érték *62* értékkel kezdődik.
    - A **Cikkszám** értéke vagy *A001* vagy *A002*.

    A demóadatnak egyenként 10 darabnak kell lennie.

    Ezután létre kell hoznia egy értékesítési rendelést.

1. Ugorjon az **Értékesítés és marketing \> Értékesítési rendelések \> Minden értékesítési rendelés** pontra.
1. A Műveleti ablaktáblán kattintson az **Új** elemre.
1. Az **Értékesítési rendelés létrehozása** párbeszédpanelen adja meg a következő értékeket:

    - **Vevőkód** *US-007*
    - **Raktár:** *62*

1. Válassza az **OK** gombot a beszerzési rendelés létrehozásához és a párbeszédpanel bezárásához.
1. A program megnyitja az új értékesítési rendelést. Tartalmaznia kell egy új, üres sort az **Értékesítési rendelés sorai** gyorslap rácsán. Ezen a soron állítsa be a következő értékeket:

    - **Cikkszám:** *A0001*
    - **Mennyiség:** *2*

1. A rács feletti **Készlet** menüben válassza ki a **Foglalás** pontot.
1. A **Foglalás** oldalon, a műveleti panelen válassza az **Adag foglalása** elemet a készlet foglalásához.
1. Zárja be a lapot.
1. Az **Értékesítési rendelés sorai** gyorslapon válassza ki a **Sor hozzáadása** lehetőséget, ha másik sort szeretne hozzáadni az értékesítési rendeléshez. Ezen a soron állítsa be a következő értékeket:

    - **Cikkszám:** *A0002*
    - **Mennyiség:** *2*

1. A rács feletti **Készlet** menüben válassza ki a **Foglalás** pontot.
1. A **Foglalás** oldalon, a műveleti panelen válassza az **Adag foglalása** elemet a készlet foglalásához.
1. Zárja be a lapot.
1. Válassza ki a művelet ablaktáblán a **Raktár** lapon a **Kiadás raktárba** lehetőséget.
1. Olyan tájékoztató üzenetek érkeznek, amelyek az adott kiadásból létrehozott hullámazonosítót és szállítási azonosítót jelenítik meg. Jegyezze fel a hullámazonosítót.

### <a name="review-the-outbound-wave"></a>A kimenő hullám felülvizsgálata

1. Ugorjon a **Raktárkezelés \> Kimenő hullámok \> Szállítmányhullámok \> Minden hullám** menübe.
1. A rácsban keresse meg azt a hullámazonosítót, amelyet az értékesítési rendelés kiadásával hoztak létre.
1. A részletek megtekintéséhez válassza ki a hullámazonosítót.
1. A **Hullámsorok** gyorslapon győződjön meg róla, hogy az értékesítési rendeléshez meg van jelenítve a szállítási azonosító.

    > [!TIP]
    > Ha a **Hullám feldolgozása a raktárba történő kiadáskor** beállítás értéke *Nem* a szállítási hullámsablon beállításaiban, manuálisan kell feldolgoznia a hullámot úgy, hogy a munka létrehozásához a műveleti ablaktábla **Hullám** lapjáról a **Feldolgozás** elemet választja.

1. Győződjön meg róla, hogy a hullám feldolgozása megtörtént. Ez a feldolgozás létrehozza a szükséges munkát.

### <a name="view-work-details-and-change-the-work-pool"></a>Munka részleteinek megtekintése és a munkagyűjtők módosítása

A **munkarészletek** lapon megtekintheti a létrehozott munkát, és kezelheti a munkagyűjtőt.

1. Ugorjon a **Raktárkezelés \> Munka \> Munka részletei** pontra.
1. Válassza ki az imént létrehozott munka sorát. A **Rendelésszám** oszlop megmutatja az értékesítési rendelés számát.

    A **munkagyűjtő azonosítója** mező a munkasablonban beállított munkagyűjtői azonosítóra lesz beállítva.

    > [!TIP]
    > Ha nem látja a **munkagyűjtő azonosítója** mezőt, adja hozzá az oszlopot a rácshoz, majd frissítse a lapot.

1. Ha módosítani szeretné a munkaazonosítóhoz társított munkagyűjtőt, akkor a műveleti ablaktábla **Munka** lapján válassza a **Munkagyűjtő-azonosító módosítása** elemet.
1. A **Munkagyűjtő módosítása** párbeszédablakban a **Paraméterek** gyorslap **Munkagyűjtő-azonosító** mezőjében válassza a *CallCenter* értéket.
1. A módosítás alkalmazásához kattintson az **OK** gombra.
1. Figyelje meg, hogy a **munkagyűjtő-azonosító** mező értéke most módosult *CallCenter* értékre.

> [!IMPORTANT]
> Ha megjelenik a **Munkagyűjtő módosítása** párbeszédpanel, előfordulhat, hogy a **Munkagyűjtő-azonosító** mező alapértelmezés szerint üres. Ha a mező üres, ha az **OK** gombra kattint a módosítások alkalmazásához, akkor a munkagyűjtőt teljes egészében eltávolítja a program a munkából.
>
> A munkagyűjtők váltásán kívül ezzel az eljárással munkagyűjtőt adhat hozzá a munkaelemekhez, amelyek nem rendelkeznek eggyel, vagy egy munkagyűjtőt távolíthat el az összes olyan munkaelemből, amely rendelkezik egy értékkel.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]