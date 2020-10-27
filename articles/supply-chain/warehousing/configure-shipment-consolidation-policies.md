---
title: Szállítmánykonszolidációs irányelvek konfigurálása
description: Ez a témakör azt mutatja be, hogyan lehet beállítani alapértelmezett és egyéni szállítmányok konszolidációs irányelveit.
author: GarmMSFT
manager: tfehr
ms.date: 05/12/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSShipConsolidationPolicy, WHSShipConsolidationWorkbench
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: 10.0.3
ms.openlocfilehash: 4df62d7b2c8b0463ca6e9564e167f9060e811a24
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/10/2020
ms.locfileid: "3975416"
---
# <a name="configure-shipment-consolidation-policies"></a>Szállítmánykonszolidációs irányelvek konfigurálása

[!include [banner](../includes/banner.md)]

A szállítmánykonszolidációs irányelveket használó szállítmánykonszolidációs folyamat lehetővé teszi az automatizált szállítmánykonszolidálást a raktárba történő automatikus és manuális kiadáskor. Miután bekapcsolta ezt a funkciót, konfigurálnia kell a kezdeti irányelveket. Ha nincsenek beállítva irányelvek, akkor minden értékesítési sor egyetlen rakománysorral rendelkező, külön szállítmányt hoz létre.

Az ebben a témakörben ismertetett forgatókönyvek mutatják be az alapértelmezett és az egyéni szállítmánykonszolidációs irányelvek beállítását.

## <a name="turn-on-the-shipment-consolidation-policies-feature"></a>A szállítmánykonszolidációs irányelvek funkció bekapcsolása

> [!IMPORTANT]
> A jelen témakörben leírt [első forgatókönyvben](#scenario-1) először beállít egy raktárat, hogy az a korábbi szállítmánykonszolidációs funkciót használja. Ezután elérhetővé teszi a szállítmánykonszolidációs irányelveket. Ily módon a frissítési forgatókönyv működését megtapasztalhatja. Ha az első forgatókönyv végigvezetéséhez bemutató környezetet tervez használni, ne kapcsolja be a funkciót a forgatókönyv elvégzése előtt.

A *Szállítmánykonszolidációs irányelvek* funkció használata előtt először be kell kapcsolnia rendszerében. A rendszergazdák használhatják a [funkciókezelési](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) beállításokat a funkció állapotának ellenőrzéséhez, és bekapcsolásához. A **Funkció kezelése** munkaterületen a funkció a következő módon van listázva:

- **Modul:** *Raktárkezelés*
- **Funkció neve:** *Szállítmány konszolidálása*

## <a name="make-demo-data-available"></a>A bemutató adatok elérhetővé tétele

Az ebben a témakörben szereplő minden egyes forgatókönyv olyan értékekre és rekordokra hivatkozik, amelyek szerepelnek a Microsoft Dynamics 365 Supply Chain Management szolgáltatáshoz biztosított standard bemutatóadatokban. Ha azt szeretné, hogy az itt megadott értékeket használja a feladatok végrehajtásához, akkor győződjön meg róla, hogy olyan környezetben dolgozik, ahol a bemutatóadatokat telepítették, és a jogi személy beállítása legyen **USMF** .

## <a name="scenario-1-configure-default-shipment-consolidation-policies"></a><a name="scenario-1"></a>1. forgatókönyv: Alapértelmezett szállítmánykonszolidációs irányelvek konfigurálása

Két olyan eset van, amikor konfigurálnia kell az alapértelmezett irányelvek minimális számát a *Szállítmánykonszolidációs irányelvek* funkció bekapcsolása után:

- Olyan környezetet frissít, amely már tartalmaz adatokat.
- Teljesen új környezetet állít be.

### <a name="upgrade-an-environment-where-warehouses-are-already-configured-for-cross-order-consolidation"></a>Olyan környezet frissítése, amelyben a raktárak már be vannak állítva a rendelésközi konszolidáláshoz

Az eljárás indításakor ki kell kapcsolnia a *Szállítmánykonszolidációs irányelvek* funkciót, olyan környezet szimulálása érdekében, ahol már használatban van az alapvető rendelésközi konszolidálás funkció. Ezt követően a funkciókezelés segítségével bekapcsolhatja a funkciót, így megismerheti, hogy a frissítés után hogyan kell szállítmánykonszolidációs irányelveket beállítani.

Kövesse az alábbi lépéseket az alapértelmezett szállítmánykonszolidációs irányelvek beállításához olyan környezetben, ahol a raktárakat már konfigurálták a rendelésközi konszolidációhoz.

1. Ugorjon a **Raktárkezelés \> Beállítás \> Raktár \> Raktárak** pontra.
1. A listán keresse meg és nyissa meg a kívánt raktári rekordot (például raktár *24* az **USMF** bemutatóadatokban).
1. A műveleti ablaktáblán válassza a **Szerkesztés** lehetőséget.
1. A **Raktár** gyorslapon állítsa be a **Szállítmány konszolidálása a raktárnak való kiadáskor** beállítást *Igen* értékre.
1. Ismételje meg a 2–4. lépést az összes többi raktárhoz, ahol szükség van a konszolidációra.
1. Zárja be a lapot.
1. A [funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) használatával kapcsolja be a *Szállítmánykonszolidációs irányelvek* funkciót. A **Funkciókezelés** munkaterületen a funkció neve *Szállítmány konszolidálása* .
1. Nyissa meg a **Raktárkezelés \> Beállítás \> Kiadás raktárnak \> Szállítmánykonszolidációs irányelvek** pontot. Előfordulhat, hogy frissítenie kell a böngészőt, hogy az új **szállítmánykonszolidációs irányelvek** menüelemet a funkció bekapcsolása után láthassa.
1. A műveleti ablaktáblán válassza az **Alapértelmezett beállítás létrehozása** elemet a következő irányelvek létrehozásához:

    - Az *Értékesítési rendelések* irányelvtípushoz tartozó **CrossOrder** irányelv (feltéve, hogy legalább egy raktárat már beállítottak a korábbi konszolidációs funkció használatához)
    - **Alapértelmezett** irányelv az *Értékesítési rendelés* irányelvtípushoz
    - **Alapértelmezett** irányelv az *Átviteli probléma* irányelvtípushoz
    - Az *Átviteli probléma* irányelvtípushoz tartozó **CrossOrder** irányelv (feltéve, hogy legalább egy raktárat már beállítottak a korábbi konszolidációs funkció használatához)

    > [!NOTE]
    > - Mindkét **CrossOrder** irányelv ugyanazt a mezőkészletet veszi figyelembe, mint a korábbi logika, kivéve a rendelésszámhoz tartozó mező. (Ez a mező a sorok szállítmányokba történő konszolidálására szolgál, olyan tényezők alapján, mint a raktár, a szállítási mód és a cím.)
    > - Mindkét **Alapértelmezett** irányelv ugyanazt a mezőkészletet veszi figyelembe, mint a korábbi logika, beleértve a rendelésszámhoz tartozó mezőt is. (Ez a mező a sorok szállítmányokba történő konszolidálására szolgál, olyan tényezők alapján, mint a rendelésszám, a raktár, a szállítási mód és a cím.)

1. Válassza ki az *Értékesítési rendelés* irányelvtípushoz tartozó **CrossOrder** irányelvet, majd a műveleti ablaktáblán válassza a **Lekérdezés szerkesztése** elemet.
1. A lekérdezéstervező párbeszédpanelen figyelje meg, hogy azok a raktárak szerepelnek a listán, amelyeknél a **Szállítmány konszolidálása a raktárnak való kiadáskor** beállítás értéke *Igen* . Ezért a lekérdezésben szerepelnek.

### <a name="create-default-policies-for-a-new-environment"></a>Új környezet alapértelmezett irányelveinek létrehozása

Kövesse az alábbi lépéseket az alapértelmezett szállítmánykonszolidációs irányelvek beállításához egy teljesen új környezetben.

1. A [funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) használatával kapcsolja be a *Szállítmánykonszolidációs irányelvek* , ha még nem kapcsolta be. A **Funkciókezelés** munkaterületen a funkció neve *Szállítmány konszolidálása* .
1. Nyissa meg a **Raktárkezelés \> Beállítás \> Kiadás raktárnak \> Szállítmánykonszolidációs irányelvek** pontot.
1. A műveleti ablaktáblán válassza az **Alapértelmezett beállítás létrehozása** elemet a következő irányelvek létrehozásához:

    - **Alapértelmezett** irányelv az *Értékesítési rendelés* irányelvtípushoz
    - **Alapértelmezett** irányelv az *Átviteli probléma* irányelvtípushoz

    > [!NOTE]
    > Mindkét **Alapértelmezett** irányelv ugyanazt a mezőkészletet veszi figyelembe, mint a korábbi logika, beleértve a rendelésszámhoz tartozó mezőt is. (Ez a mező a sorok szállítmányokba történő konszolidálására szolgál, olyan tényezők alapján, mint a rendelésszám, a raktár, a szállítási mód és a cím.)

## <a name="scenario-2-configure-custom-shipment-consolidation-policies"></a>2. forgatókönyv: Egyéni szállítmánykonszolidációs irányelvek konfigurálása

Ez a példa azt mutatja be, hogyan lehet beállítani az egyéni szállítmánykonszolidációs irányelveket. Az egyéni irányelvek olyan összetett üzleti követelményeket támogatnak, amelyeknél több feltétel is függ a szállítmányok konszolidálástól. A forgatókönyvben szereplő valamennyi példairányelv esetében az üzleti eset rövid leírása szerepel. Ezeket a példairányelveket olyan sorrendben kell beállítani, amely biztosítja a lekérdezések piramisszerű értékelését. (Más szóval a legtöbb feltételnek megfelelő irányelveket a legmagasabb prioritással kell értékelni.)

### <a name="turn-on-the-feature-and-prepare-master-data-for-this-scenario"></a>A funkció bekapcsolása és alapadatok előkészítése ehhez a forgatókönyvhöz

Mielőtt végighaladhatna a jelen forgatókönyv gyakorlatain, be kell kapcsolni a funkciót, és elő kell készíteni a szűrés elvégzéséhez szükséges alapadatokat a következő alszakaszokban leírtak szerint. (Ezek az előkövetelmények a [Példaforgatókönyvek a szállítmánykonszolidációs irányelvek használatához](#example-scenarios) című listában szereplő forgatókönyvekre is vonatkoznak.)

#### <a name="turn-on-the-feature-and-create-the-default-policies"></a>A funkció bekapcsolása és az alapértelmezett irányelvek létrehozása

Ha még nem kapcsolta be, akkor a funkciókezelés segítségével kapcsolja be a funkciót, és hozza létre az alapértelmezett konszolidációs irányelveket, amelyek az [1. forgatókönyvben](#scenario-1) szerepelnek.

#### <a name="create-two-new-product-filter-codes"></a>Két új termékszűrési kód létrehozása

1. Nyissa meg a **Raktárkezelés \> Beállítás \> Termékszűrők \> Termékszűrők** pontot, és adjon hozzá két termékszűrőt:

    - 1. termékszűrő:

        - **Szűrőkód:** *Gyúlékony*
        - **Szűrő címe:** *4. kód*

    - 2. termékszűrő:

        - **Szűrőkód:** *Robbanásveszélyes*
        - **Szűrő címe:** *4. kód*

1. Kattintson a **Termékinformációk kezelése \> Termékek \> Kiadott termékek** lehetőségre.
1. Nyissa meg a *M9200* cikkszámmal rendelkező terméket. (A kiválasztott terméknek engedélyezve kell lennie a speciális raktár \[WMS\] folyamataihoz, és az adott terméknek előzetesen engedélyezve kell lennie a WMS-folyamatokban az **USMF** bemutatóadatokban.)
1. A **Raktár** gyorslapon állítsa be a **4. kód** mező értékét *Gyúlékony* értékre.
1. Zárja be a lapot.
1. Nyissa meg a *M9201* cikkszámmal rendelkező terméket. (Ez a termék a WMS-folyamatok számára is előzetesen engedélyezve van a következőben: **USMF** bemutatóadatok.)
1. A **Raktár** gyorslapon állítsa be a **4. kód** mező értékét *Robbanásveszélyes* értékre.
1. Zárja be a lapot.

#### <a name="create-a-new-transportation-mode-of-delivery"></a>Új szállítási mód létrehozása

1. Ugorjon a **Szállításkezelés \> Beállítás \> Szállítmányozók \> Mód** lehetőségre.
1. Hozzon létre egy szállítási módot, amelyet a konszolidációs lekérdezésekben használ majd, és nevezze el *Légitársaság* néven.
1. Ugorjon a **Szállításkezelés \> Beállítás \> Szállítmányozók \> Szállítmányozók** lehetőségre.
1. Hozzon létre egy olyan szállítmányozót, amelynek beállításai a következők:

    - **Szállítmányozó:** *Légitársaság*
    - **Név:** *Légitársaság*
    - **Mód:** *Légitársaság*

1. A **Szolgáltatások** gyorslapon az új szállítmányozónál adjon hozzá egy sort, amely a következő beállításokkal rendelkezik:

    - **Szállítmányozói szolgáltatás:** *Légi*
    - **Szállítási mód:** *Légi*

1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.

    > [!NOTE]
    > Amikor menti az új szállítót, a rendszer az új sor **Szállítási mód** mezőjének beállítását a **Szolgáltatások** rácsban automatikusan *Légitá-Légi* értékre állítja. Amikor egy értékesítési rendeléshez a *Légitá-Légi* szállítási módot használja, a rendszer a kapcsolódó szállítmányokhoz a *Légitársaságok* szállítási módot használja.

#### <a name="create-an-order-pool"></a>Rendelésgyűjtő létrehozása

1. Ugorjon az **Értékesítés és marketing \> Beállítás \> Értékesítési rendelések \> Rendelésgyűjtők** lehetőségre.
1. Hozzon létre egy olyan rendelési gyűjtőt, amely a konszolidációs lekérdezéshez lesz használva. A rendelési gyűjtőnek a következő beállításokat kell tartalmaznia:

    - **Gyűjtő:** Adjon meg egy egész számot, amelyet még nem használ másik gyűjtő.
    - **Név:** *ShipCons*

1. Lépjen az **Értékesítés és marketing \> Vevők \> Összes vevő** menüpontba.
1. Nyissa meg az *US-003* számlaszámú vevőt.
1. Az **Értékesítési rendelés alapértelmezett értékei** gyorslapon állítsa az **Értékesítési rendelés gyűjtője** mezőt az imént létrehozott rendelésgyűjtőre.
1. Zárja be a lapot, majd ismételje meg a 4–5. lépést az *US-004* számlaszámú vevővel.

### <a name="create-example-policy-1"></a>1. példairányelv létrehozása

Ebben a példában létrehozza a *Vevő+mód* irányelvet, amely a következő üzleti esetben használatos:

- Az irányelv egy specifikus vevői számlát ( *US-001* ) és specifikus szállítási módot ( *Légitá-Légi* ) fog lekérdezni.
- A nyitott szállítmányok konszolidálása ki van kapcsolva.
- A konszolidáció rendelésazonosítónként történik. (Más szóval külön szállítmányok jönnek létre rendelésenként, raktáranként stb.)

Kövesse az alábbi lépéseket az üzleti esethez tartozó szállítmánykonszolidációs irányelv létrehozásához.

1. Nyissa meg a **Raktárkezelés \> Beállítás \> Kiadás raktárnak \> Szállítmánykonszolidációs irányelvek** pontot.
1. Az **Irányelvtípus** mezőt állítsa *Értékesítési rendelések* értékre.
1. A műveleti ablaktáblán válassza az **új** lehetőséget, ha a következő beállításokat tartalmazó irányelvet szeretné létrehozni:

    - **Irányelv neve:** *CustomerMode*
    - **Irányelv leírása:** *Vevői számla és szállítási mód*

1. Hagyja a **Konszolidációt nyitott szállítmányokkal** beállítást *Nem* értéken.
1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.
1. A **Konszolidációs mezők** gyorslapon a **Fennmaradó mezők** listában válassza ki a sort, ahol a **Mező neve** mező beállítása *Szállítási mód* .
1. Válassza a **Hozzáadás** gombot ![Jobbra nyíl](media/forward-button.png) a mező **Kiválasztott mezők** listára történő átmozgatásához.
1. A műveleti ablaktáblán válassza a **Lekérdezés szerkesztése** lehetőséget.
1. A lekérdezéstervező párbeszédablakában a **Tartomány** lapon levő rácsban keresse meg a sort, ahol a **Mező** mező beállítása *Vevői számla* , és állítsa az adott sor **Feltételek** mezőjének értékét: *US-001* .
1. A **Hozzáadás** gombbal adjon hozzá egy sort a rácshoz a következő beállításokkal:

    - **Tábla:** *Rendeléssorok*
    - **Származtatott tábla:** *Rendeléssorok*
    - **Mező:** *Szállítási mód*
    - **Feltételek:** *Légitá-Légi*

1. Az **OK** gombbal zárja be a párbeszédpanelt.

> [!NOTE]
> Ennél az üzleti esetnél az *US-001* vevőhöz tartozó rendelési sorok, amelyek szállítási módja *Légitá-Légi* , nem lesznek rendelések között konszolidálva. Ezt az irányelvet először sorrendben kell használni, olyan esetekben, ahol az összes többi szállítási módhoz tartozó szállítmányok konszolidálva vannak ehhez a vevőhöz.

### <a name="create-example-policy-2"></a>2. példairányelv létrehozása

Ebben a példában létrehozza a *Veszélyes áruk* irányelvet, amely a következő üzleti esetben használatos:

- Az irányelv egy specifikus szűrőkódot ( *veszélyes* ) és specifikus szállítási módot ( *Légitá-Légi* ) fog lekérdezni.
- A nyitott szállítmányok konszolidálása be van kapcsolva.
- A konszolidáció rendeléseken át történik. (Más szóval külön szállítmányok jönnek létre számlánként, raktáronként stb., de csak a lekérdezésben megadott cikkcsoporton belül.)

Kövesse az alábbi lépéseket az üzleti esethez tartozó szállítmánykonszolidációs irányelv létrehozásához.

1. Nyissa meg a **Raktárkezelés \> Beállítás \> Kiadás raktárnak \> Szállítmánykonszolidációs irányelvek** pontot.
1. Az **Irányelvtípus** mezőt állítsa *Értékesítési rendelések* értékre.
1. A műveleti ablaktáblán válassza az **új** lehetőséget, ha a következő beállításokat tartalmazó irányelvet szeretné létrehozni:

    - **Irányelv neve:** *Cikktípus*
    - **Irányelv leírása:** *Azonos típusú cikkek konszolidálása a rendelések között*

1. Állítsa a **Konszolidáció nyitott szállítmányokkal** beállítást *Igen* értékre.
1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.
1. A **Konszolidációs mezők** gyorslapon a **Fennmaradó mezők** listában válassza ki a sort, ahol a **Mező neve** mező beállítása *Szállítási mód* .
1. Válassza a **Hozzáadás** gombot ![Jobbra nyíl](media/forward-button.png) a mező **Kiválasztott mezők** listára történő átmozgatásához.
1. A műveleti ablaktáblán válassza a **Lekérdezés szerkesztése** lehetőséget.
1. A lekérdezéstervező párbeszédablakban az **Illesztések** lapon bontsa ki és válassza ki a fában a **Táblák \> Rakomány részletei** elemet.
1. Válassza a **Táblaillesztés hozzáadása** lehetőséget.
1. A megjelenő kapcsolatok rácsában keresse meg és válassza ki azt a sort, ahol a **kapcsolat** mező beállítása *Raktári cikkszám (cikkszám)* , majd válassza a **Kiválasztás** elemet. 
1. A **Tartomány** lapon a **Hozzáadás** gombbal adjon hozzá egy sort a rácshoz a következő beállításokkal:

    - **Tábla:** *Raktári cikkszám*
    - **Származtatott tábla:** *Raktári cikkszám*
    - **Mező:** *4. kód*
    - **Feltételek:** *Gyúlékony*

1. Az **OK** gombbal zárja be a párbeszédpanelt.

> [!NOTE]
> Ebben az üzleti esetben az összes olyan sor, amelyben a cikkek specifikus szűrőkóddal rendelkeznek (azaz a szűrőkód, ahol a **4. kód** mező beállítása *Gyúlékony* ), konszolidálva lesz az ugyanolyan típusú másik cikkekkel a rendelések között. Ha ugyanahhoz a számlához, raktárhoz és cikkcsoporthoz nyitott szállítmány tartozik, az új sorok hozzákapcsolódnak.

### <a name="create-example-policy-3"></a>3. példairányelv létrehozása

Ebben a példában létrehozza a *Vevői követelmények* irányelvet, amely a következő üzleti esetben használatos:

- Az irányelv egy specifikus vevői számlát fog lekérdezni.
- A nyitott szállítmányok konszolidálása be van kapcsolva.
- A konszolidáció a rendelések között történik, de a vevői igényléseken alapul. (Más szóval a rendszer több rendelést szállítmányokba csoportosít, ugyanazona vevői igénylési szám és raktár alapján.)

Kövesse az alábbi lépéseket az üzleti esethez tartozó szállítmánykonszolidációs irányelv létrehozásához.

1. Nyissa meg a **Raktárkezelés \> Beállítás \> Kiadás raktárnak \> Szállítmánykonszolidációs irányelvek** pontot.
1. Az **Irányelvtípus** mezőt állítsa *Értékesítési rendelések* értékre.
1. A műveleti ablaktáblán válassza az **új** lehetőséget, ha a következő beállításokat tartalmazó irányelvet szeretné létrehozni:

    - **Irányelv neve:** *CustomerOrderNo*
    - **Irányelv leírása:** *Sorok konszolidálása vevői beszerzési rendelés alapján*

1. Állítsa a **Konszolidáció nyitott szállítmányokkal** beállítást *Igen* értékre.
1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.
1. A **Konszolidációs mezők** gyorslapon a **Fennmaradó mezők** listában válassza ki a sort, ahol a **Mező neve** mező beállítása *Vevői igénylés* .
1. Válassza a **Hozzáadás** gombot ![Jobbra nyíl](media/forward-button.png) a mező **Kiválasztott mezők** listára történő átmozgatásához.
1. A **Fennmaradó mezők** listában válassza ki a sort, ahol a **Mező neve** mező beállítása *Szállítási mód* .
1. Válassza a **Hozzáadás** gombot ![Jobbra nyíl](media/forward-button.png) a mező **Kiválasztott mezők** listára történő átmozgatásához.
1. A műveleti ablaktáblán válassza a **Lekérdezés szerkesztése** lehetőséget.
1. A lekérdezéstervező párbeszédablakában a **Tartomány** lapon keresse meg a sort, ahol a **Mező** mező beállítása *Vevői számla* , és állítsa az adott sor **Feltételek** mezőjének értékét: *US-001* .
1. Az **OK** gombbal zárja be a párbeszédpanelt.

> [!NOTE]
> Ennél az üzleti esetben az összes olyan sor, ahol az értékesítési rendelések ugyanazzal a vevői igénylési számmal rendelkeznek, egy szállítmányba lesznek konszolidálva, az értékesítési rendelés számától függetlenül. (A vevői igénylés számát a rendszer a vevői beszerzési rendelés \[PO\] számaként használja.) Ha ugyanahhoz a számlához, raktárhoz és vevői igényléshez nyitott szállítmány tartozik, az új sorok ehhez kapcsolódnak. Ez az irányelv akkor használatos, ha a vevő további rendelési sorokat küld egy napon belül többször ugyanazzal a beszerzési rendelési számmal, és szeretné, ha az összes sort egy szállítmányba csoportosítanák. (Más szóval egy fuvarlevél és egy szállítólevél lesz.)

### <a name="create-example-policy-4"></a>4. példairányelv létrehozása

Ebben a példában létrehozza a *Konszolidációt engedélyező vevők* irányelvet, amely a következő üzleti esetben használatos:

- Az irányelv egy specifikus rendelésgyűjtőt fog lekérdezni az olyan vevők beazonosítása céljából, akik konszolidált szállítmányokat fogadnak.
- A nyitott szállítmányok konszolidálása ki van kapcsolva.
- A konszolidáció a rendelések között történik az alapértelmezett CrossOrder irányelv által kijelölt mezők használatával (a korábbi **Szállítmány konszolidálása a raktárnak való kiadáskor** jelölőnégyzet replikálásához ).

- Egy értékesítési rendelés szabályának felülbírálásához másik rendelési gyűjtőt kell kiválasztania.

Kövesse az alábbi lépéseket az üzleti esethez tartozó szállítmánykonszolidációs irányelv létrehozásához.

1. Nyissa meg a **Raktárkezelés \> Beállítás \> Kiadás raktárnak \> Szállítmánykonszolidációs irányelvek** pontot.
1. Az **Irányelvtípus** mezőt állítsa *Értékesítési rendelések* értékre.
1. A műveleti ablaktáblán válassza az **új** lehetőséget, ha a következő beállításokat tartalmazó irányelvet szeretné létrehozni:

    - **Irányelv neve:** *Rendelési gyűjtő*
    - **Irányelv leírása:** *Rendelési gyűjtőn alapuló rendelések közötti konszolidáció*

1. Hagyja a **Konszolidációt nyitott szállítmányokkal** beállítást *Nem* értéken.
1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.
1. A **Konszolidációs mezők** gyorslapon a **Fennmaradó mezők** listában válassza ki a sort, ahol a **Mező neve** mező beállítása *Szállítási mód* .
1. Válassza a **Hozzáadás** gombot ![Jobbra nyíl](media/forward-button.png) a mező **Kiválasztott mezők** listára történő átmozgatásához.
1. A műveleti ablaktáblán válassza a **Lekérdezés szerkesztése** lehetőséget.
1. A lekérdezésszerkesztő párbeszédablak **Tartomány** lapján a **Hozzáadás** gombbal adjon hozzá egy sort a rácshoz a következő beállításokkal:

    - **Tábla:** *Értékesítési rendelések*
    - **Származtatott tábla:** *Értékesítési rendelések*
    - **Mező:** *Gyűjtő*
    - **Feltételek:** *ShipCons*

1. Az **OK** gombbal zárja be a párbeszédpanelt.

> [!NOTE]
> Ennél az üzleti esetnél az összes olyan sor, ahol az értékesítési rendelések ugyanahhoz a rendelési gyűjtőhöz tartoznak, egy szállítmányba lesznek konszolidálva az ugyanahhoz a számlához, raktárhoz és szállítási módhoz tartozó értékesítési rendelések között. A rendelésgyűjtő helyett bármely másik mezőt is használhatja a vevők csoportjának megkülönböztetésére, és alapértelmezett módon használhatja az értékesítési rendelés fejlécét. Ez a módszer akkor használható, ha a vevő (nem a raktár) a konszolidáció szükségességét igényli. (A korábbi konszolidációs logikában a raktár kezdeményezte a konszolidáció szükségességét.)

### <a name="create-example-policy-5"></a>5. példairányelv létrehozása

Ebben a példában létrehozza a *Konszolidációt engedélyező raktárak* irányelvet, amely a következő üzleti esetben használatos:

- Az irányelv egy specifikus rendelésgyűjtőt fog lekérdezni az olyan raktárak beazonosítása céljából, akik képesek szállítmányok konszolidálására.
- A nyitott szállítmányok konszolidálása ki van kapcsolva.
- A konszolidáció a rendelések között történik az alapértelmezett CrossOrder irányelv által kijelölt mezők használatával (a korábbi **Szállítmány konszolidálása a raktárnak való kiadáskor** jelölőnégyzet replikálásához ).

Leggyakrabban ezt az üzleti esetet meg lehet oldani, ha az [1. forgatókönyvben](#scenario-1) létrehozott alapértelmezett irányelveket használja. Azonban manuálisan is létrehozhat hasonló irányelveket az alábbi lépések követésével.

1. Nyissa meg a **Raktárkezelés \> Beállítás \> Kiadás raktárnak \> Szállítmánykonszolidációs irányelvek** pontot.
1. Az **Irányelvtípus** mezőt állítsa *Értékesítési rendelések* értékre.
1. A műveleti ablaktáblán válassza az **új** lehetőséget, ha a következő beállításokat tartalmazó irányelvet szeretné létrehozni:

    - **Irányelv neve:** *Rendelésközi*
    - **Irányelv leírása:** *Rendelésközi konszolidáció meghatározott raktáraknál*

1. Hagyja a **Konszolidációt nyitott szállítmányokkal** beállítást *Nem* értéken.
1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.
1. A **Konszolidációs mezők** gyorslapon a **Fennmaradó mezők** mezőben válassza ki a sort, ahol a **Mező neve** mező beállítása *Szállítási mód* .
1. Válassza a **Hozzáadás** gombot ![Jobbra nyíl](media/forward-button.png) a mező **Kiválasztott mezők** listára történő átmozgatásához.
1. A műveleti ablaktáblán válassza a **Lekérdezés szerkesztése** lehetőséget.
1. A lekérdezéstervező párbeszédablakában a **Tartomány** lapon keresse meg a sort, ahol a **Mező** mező beállítása *Raktár* , és állítsa az adott sor **Feltételek** mezőjének értékét: *61, 63* .
1. Az **OK** gombbal zárja be a párbeszédpanelt.

### <a name="set-the-order"></a>Sorrend beállítása

Miután létrehozta az összes irányelvet, létre kell hoznia azt a sorrendet, amelyben alkalmazzák őket. Ha egy piramisszerű megközelítést szeretne használni, ahol a legtöbb feltételnek megfelelő irányelvek értékelése a legmagasabb prioritást jelenti, hajtsa végre az alábbi lépéseket.

1. Nyissa meg a **Raktárkezelés \> Beállítás \> Kiadás raktárnak \> Szállítmánykonszolidációs irányelvek** pontot.
1. Az **Irányelvtípus** mezőt állítsa *Értékesítési rendelések* értékre.
1. Válassza ki a bal oldali oszlopban felsorolt összes irányelvet, majd a műveleti ablaktáblán a **Mozgatás felfelé** és **Mozgatás lefelé** gombokkal rendezze az irányelveket a következő sorrendbe:

    1. CustomerMode
    1. Cikk típusa
    1. CustomerOrderNo
    1. Rendelésgyűjtő
    1. Rendelésközi
    1. Alapértelmezett

## <a name="example-scenarios-of-how-to-use-shipment-consolidation-policies"></a><a name="example-scenarios"></a> Példa a szállítmányok konszolidációs irányelveinek használatára

A következő forgatókönyvek azt mutatják be, hogyan lehet használni a témakör olvasása közben létrehozott szállítmánykonszolidációs irányelveket. Minden egyes forgatókönyv végigvezeti egy szállítmánykonszolidációs irányelveket használó szállítmánykonszolidációs folyamaton a raktárba történő automatikus vagy manuális kiadáskor:

- 1. forgatókönyv: [Szállítmányok konszolidálása a raktárba történő kiadáskor Értékesítési rendelések automatikus kiadása funkció használatával](../warehousing/consolidate-shipments-automatic.md)
- 2. forgatókönyv: [Szállítmányok konszolidálása, amikor a szállítmánykonszolidációs irányelv felülírásra kerül a Kiadástól a raktárba lapról](../warehousing/consolidate-shipments-release-to-warehouse-override.md)
- 3. forgatókönyv: [Szállítmányok konszolidálása a Kiadás a raktárba lehetőség használatával a Rakománytervező munkaterület oldalról](../warehousing/consolidate-shipments-load-planning-workbench.md)
- 4. forgatókönyv: [Szállítmányok konszolidálása a szállítmánykonszolidációs munkaterület használatával](../warehousing/consolidate-shipments-manual-workbench.md)
- 5. forgatókönyv: [Szállítmányok manuális konszolidálása a szállítmányok konszolidálása oldal használatával](../warehousing/consolidate-shipments-manual-form.md)


## <a name="additional-resources"></a>További erőforrások

- [Szállítmánykonszolidációs irányelvek](about-shipment-consolidation-policies.md)
