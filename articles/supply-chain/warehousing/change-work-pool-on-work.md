---
title: Munkagyűjtő módosítása a munkán
description: Ez a témakör azt mutatja be, hogy hogyan lehet módosítani a Munkagyűjtő módosítása gombot a munkaelemekhez a meglévő munka munkagyűjtőjének módosításához.
author: mirzaab
manager: tfehr
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWorkPool,WHSWorkTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: global
ms.author: mirzaab
ms.search.validFrom: 2020-07-16
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 66d110c3235e8a87b64bf160bdad8524fad6abe5
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "5001149"
---
# <a name="change-work-pool-on-work"></a>Munkagyűjtő módosítása a munkán

[!include [banner](../includes/banner.md)]

Munkagyűjtők segítségével a munkát csoportokba rendezheti. Például létrehozhat egy munkagyűjtőt, hogy osztályozza azt a munkát, amelyet egy adott raktárhelyen történik.

A *Munka munkagyűjtőjének módosítása* funkció hozzáadja a **Munkagyűjtő módosítása** gombot a munkaelemek műveleti ablaktáblájához. Így a raktárkezelők egyszerűen módosíthatják a meglévő munka munkagyűjtőjét. Ez a funkció lehetővé teszi a vezetők gyors reagálását a raktári üzem szintjén, és javítja a változó helyzetekhez való alkalmazkodás képességét, valamint a munka másik munkagyűjtőbe történő áthelyezését.

## <a name="turn-on-the-change-work-pool-on-work-feature"></a>A Munkagyűjtő módosítása a munkán funkció bekapcsolása

Mielőtt elkezdené a funkció beállítását vagy használatát, győződjön meg arról, hogy az elérhető a rendszerben. A rendszergazdák használhatják a [funkciókezelési](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) beállításokat a funkció állapotának ellenőrzéséhez, és szükség esetén bekapcsolásához. A **Funkció kezelése** munkaterületen a funkció a következő módon van listázva:

- **Modul:** *Raktárkezelés*
- **Funkció neve:** *Munkagyűjtő módosítása a munkán*

## <a name="set-up-the-change-work-pool-on-work-feature"></a>A Munkagyűjtő módosítása a munkán funkció beállítása

Ez a funkció csak akkor használható, ha be van állítva néhány munkagyűjtő. A munkasablonokat úgy is be lehet állítani, hogy automatikusan társítson egy gyűjtőt. Ha szeretne végighaladni a jelen témakörben később megadott példákon, állítsa be a rendszert az ebben a szakaszban ismertetett módon.

### <a name="set-up-work-pools"></a>Munkagyűjtők beállítása

A munkagyűjtők a munkatételek típus szerinti rendszerezését teszik lehetővé. Ha a *Munkagyűjtő módosítása a munkán* funkcióban szeretne dolgozni, legalább két munkagyűjtőnek elérhetőnek kell lennie. A Munkagyűjtő megtekintéséhez és hozzáadásához kövesse az alábbi lépéseket.

1. Ugorjon a **Raktárkezelés \> Beállítás \> Munka \> Munkagyűjtők** pontra.
1. Ha az **USMF** vállalattól származó demóadatokkal dolgozik , és a jelen témakörben később elvégzi a példát, vegyen fel két olyan munkagyűjtőt, amelyeknek a következő beállításai vannak:

    - 1. munkagyűjtő:

        - **Munkagyűjtő azonosítója:** *Webshop*
        - **Leírás:** *Webáruház*

    - 2. munkagyűjtő:

        - **Munkagyűjtő azonosítója:** *CallCenter*
        - **Leírás:** *Hívásközpont*

1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.

### <a name="set-up-work-templates"></a>Munkasablonok beállítása

A munkasablonok mindegyikéhez beállíthat egy alapértelmezett munkagyűjtőt, ha szükséges. Minden megfelelő sablonhoz társítani kell egy munkagyűjtőt a **munkagyűjtő azonosítója** oszlopban. Ebben az esetben az adott sablon használatával létrejövő összes munkaelem automatikusan örökli a hozzárendelt munkagyűjtőt. Ha az **USMF** vállalattól származó demóadatokkal dolgozik , és a jelen témakörben később elvégzi a példát, kövesse az alábbi lépéseket.

1. Lépjen a **Raktárkezelés \> Beállítás \> Munka \> Munkasablonok** elemre.
1. A műveleti ablaktáblán válassza ki a **Szerkesztés** parancsot, hogy a lapot szerkesztési módba helyezze.
1. A következő értékek beállításával módosítsa a sablont:

    - **Munkasablon:** *62 Kitárolástól csomagolásig*
    - **Munkagyűjtő azonosítója:** *Webshop*

1. Válassza a **Mentés** lehetőséget.

## <a name="example-scenario"></a>Példaforgatókönyv

Ez a példa azt mutatja be, hogyan lehet módosítani egy meglévő munkaelem feldolgozási folyamát a munkagyűjtők megváltoztatásával. A program a **USMF** vállalattól származó demóadatokat, valamint a korábban a témakörben korábban javasolt beállításokat használja.

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