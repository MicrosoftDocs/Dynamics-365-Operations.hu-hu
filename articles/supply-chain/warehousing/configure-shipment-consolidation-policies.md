---
title: Szállítmánykonszolidációs irányelvek konfigurálása
description: Ez a cikk bemutatja az alapértelmezett és az egyéni szállítmánykonszolidáció irányelveinek beállítását.
author: Mirzaab
ms.date: 09/07/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSShipConsolidationPolicy, WHSShipConsolidationWorkbench, WHSFilterGroupTable, TMSMode, WHSShipmentConsolidation, WHSFilterGenerallyAvail
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: 10.0.3
ms.openlocfilehash: 0312d425d2ebc5311e894030423a916b90f1881a
ms.sourcegitcommit: 3d7ae22401b376d2899840b561575e8d5c55658c
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/08/2022
ms.locfileid: "9427982"
---
# <a name="configure-shipment-consolidation-policies"></a>Szállítmánykonszolidációs irányelvek konfigurálása

[!include [banner](../includes/banner.md)]

A szállítmánykonszolidációs irányelveket használó szállítmánykonszolidációs folyamat lehetővé teszi az automatizált szállítmánykonszolidálást a raktárba történő automatikus és manuális kiadáskor. Miután bekapcsolta ezt a funkciót, konfigurálnia kell a kezdeti irányelveket. Ha nincsenek beállítva irányelvek, akkor minden értékesítési sor egyetlen rakománysorral rendelkező, külön szállítmányt hoz létre.

Az ebben a cikkben ismertetett helyzetek bemutatják, hogyan lehet beállítani az alapértelmezett és az egyéni szállítmánykonszolidáció irányelveit.

> [!WARNING]
> Ha olyan Microsoft Dynamics 365 Supply Chain Management rendszert frissít, amelyben már használja az örökölt szállítmánykonszolidáció funkciót, a konszolidáció leállhat a vártnak megfelelően, hacsak nem követi az itt kapott tambóliaot.
>
> Az ellátásilánc-kezelés olyan *telepítéseinél*, ahol ki van kapcsolva a Szállítmánykonszolidáció irányelvei funkció, **az** egyes raktárakba való kiadáskor a Szállítmányok konszolidálása beállításával engedélyezheti a szállítmánykonszolidációt. Ez a funkció a 10.0.29-es verziótól kötelező. Ha be van kapcsolva, **a** konszolidált szállítmány a raktárba való kiadáskor beállítás nem látható, *és* a funkció helyére az ebben a cikkben ismertetett szállítmánykonszolidációi irányelvek állnak. Minden egyes irányelv konszolidálási szabályokat állapít meg, és egy lekérdezéssel határozza meg, hogy az irányelv hol érvényes. Amikor először bekapcsolja a funkciót, **a Szállítmánykonszolidáció irányelvei lapon nem határoz meg szállítmánykonszolidációs házirendet**. Ha nincsenek megadva irányelvek, a rendszer az örökölt viselkedést használja. Ennek megfelelően minden meglévő raktár továbbra is **tartsa** be a konszolidált szállítmányt a raktárba való kiadáskor, annak ellenére, hogy ez a beállítás már nem látható. Miután azonban már legalább egy szállítmánykonszolidációi házirendet létrehozott, **a** szállítmány konszolidálása a raktárba való kiadáskor már nem lesz hatással, és a konszolidálási funkciókat teljes egészében a házirend vezérli.
>
> Miután legalább egy szállítmánykonszolidációra vonatkozó házirendet meghatározott, a rendszer a rendelés raktárba való kiszállításakor ellenőrzi a konszolidációs irányelveket. A rendszer az irányelvek **irányelvsorrend-értéke által meghatározott rangsorolás alapján dolgozza fel az irányelveket**. Az első olyan házirendet alkalmazza, amelyben a lekérdezés megfelel az új rendelésnek. Ha egyetlen lekérdezés sem felel meg a rendelésnek, minden rendelési sor külön szállítmányt hoz létre, amely egyetlen rakománysort hoz létre. Ezért javasoljuk, hogy tartalékként hozzon létre egy alapértelmezett házirendet, amely rendelésszám szerint minden raktárra és csoportra érvényes. Adja meg ennek a tartalék házirendnek **a** legmagasabb sorszámértékét, hogy a feldolgozás utolsóként essen.
>
> Az örökölt viselkedést olyan házirend létrehozása szükséges, amely nem rendelésszám szerint van csoportosítva, és olyan lekérdezési feltételekkel rendelkezik, amelyek minden vonatkozó raktárat tartalmaznak.

## <a name="turn-on-the-shipment-consolidation-policies-feature"></a>A szállítmánykonszolidációs irányelvek funkció bekapcsolása

A Szállítmánykonszolidáció *irányelveinek* használatához be kell kapcsolva lennie a rendszeren. Az Ellátásilánc-kezelés 10.0.29-es verziója szerint a funkció kötelező, és nem lehet kikapcsolni. Ha 10.0.29-esnél régebbi verziót futtat, *·*[akkor](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) a rendszergazdák be- vagy kikapcsolhatják ezt a funkciót, ha a Szolgáltatáskezelés munkaterület Szállítmánykonszolidáció irányelveinek szolgáltatását keresi.

## <a name="set-up-your-initial-consolidation-policies"></a><a name="initial-policies"></a> Kezdeti konszolidációs irányelvek beállítása

Ha új rendszerrel vagy olyan rendszerrel dolgozik, amelynél az első alkalommal bekapcsolta a *Szállítmánykonszolidáció* irányelveit, a következő lépések szerint állítsa be a szállítmányok kezdeti konszolidációs irányelveit.

1. Nyissa meg a **Raktárkezelés \> Beállítás \> Kiadás raktárnak \> Szállítmánykonszolidációs irányelvek** pontot.
1. A műveleti ablaktáblán válassza az **Alapértelmezett beállítás létrehozása** elemet a következő irányelvek létrehozásához:

    - Az Értékesítési rendelések irányelvtípus *alapértelmezett* *nevű* irányelve.
    - Alapértelmezett nevű irányelv az *Átadás* kiadási *irányelvtípushoz*.
    - Egy CrossOrder *nevű* irányelv az *Átadás kiadási irányelvtípushoz*. (Ez a házirend csak akkor jön létre, ha legalább egy olyan raktára van, ahol az örökölt **A szállítmány konszolidálása a raktárba való kiadáskor** beállítás engedélyezve van.)
    - Az értékesítési rendelések irányelvtípusának *CrossOrder* *nevű* irányelve. (Ez a házirend csak akkor jön létre, ha legalább egy olyan raktára van, ahol az örökölt **A szállítmány konszolidálása a raktárba való kiadáskor** beállítás engedélyezve van.)

    > [!NOTE]
    > - Mindkét *CrossOrder irányelv* ugyanazt a mezőkészletet veszi figyelembe, mint a korábbi logikát. Ugyanakkor a rendelésszám mezőt is figyelembe veszi a program. (Ez a mező a sorok szállítmányokba történő konszolidálására szolgál, olyan tényezők alapján, mint a raktár, a szállítási mód és a cím.)
    > - Mindkét *alapértelmezett* irányelv ugyanazt a mezőkészletet veszi figyelembe, mint a korábbi logikát. Ugyanakkor a rendelésszám mezőt is figyelembe veszi a program. (Ez a mező a sorok szállítmányokba történő konszolidálására szolgál, olyan tényezők alapján, mint a rendelésszám, a raktár, a szállítási mód és a cím.)

1. Ha a rendszer CrossOrder-házirendet generált az értékesítési rendelések irányelvtípusára, válassza ki, *majd a műveletpanelen válassza ki a* Lekérdezés szerkesztése lehetőséget *.* **·** A lekérdezésszerkesztőben látható, **hogy** a raktárba való kiadáskor a Konszolidált szállítmány melyik raktár esetében volt engedélyezve korábban. Ennek megfelelően ez a házirend az ilyen raktárakra vonatkozó korábbi beállításokat is újra előveszi.
1. Az új alapértelmezett irányelvek testreszabása mezők hozzáadásával és törlésével, illetve a lekérdezések szerkesztésével. Ha szükséges, akár több új házirendet is hozzáadhat. A házirendek testreszabását és konfigurálését bemutató példákat a cikk későbbi példaesetében olvashatja.

## <a name="scenario-configure-custom-shipment-consolidation-policies"></a>Helyzet: Egyéni szállítmánykonszolidáció irányelveinek konfigurálása

Ez az eset egy olyan példát mutat be, amely bemutatja, hogyan lehet beállítani az egyéni szállítmánykonszolidáció irányelveit, majd a bemutató adatok segítségével tesztelni azokat. Az egyéni irányelvek olyan összetett üzleti követelményeket támogatnak, amelyeknél több feltétel is függ a szállítmányok konszolidálástól. A forgatókönyvben szereplő valamennyi példairányelv esetében az üzleti eset rövid leírása szerepel. Ezeket a példairányelveket olyan sorrendben kell beállítani, amely biztosítja a lekérdezések piramisszerű értékelését. (Más szóval a legtöbb feltételnek megfelelő irányelveket a legmagasabb prioritással kell értékelni.)

### <a name="make-demo-data-available"></a>A bemutató adatok elérhetővé tétele

Ez az eset olyan értékeket és [rekordokat](../../fin-ops-core/fin-ops/get-started/demo-data.md) hivatkozik, amelyek az Ellátásilánc-kezelés szabványos bemutató adataiban szerepelnek. Ha azt szeretné, hogy az itt megadott értékeket használja a feladatok végrehajtásához, akkor győződjön meg róla, hogy olyan környezetben dolgozik, ahol a bemutatóadatokat telepítették, és a jogi személy beállítása legyen *USMF*.

### <a name="prepare-master-data-for-this-scenario"></a>Alapadatok előkészítése ehhez az esethez

Ahhoz, hogy végig tudja menni az ebben az esetben szükséges eseteket, elő kell készítenie a szűréshez szükséges alapadatokat, amint azt az alábbi alszakaszok ismertetik. (Ezek az előfeltételek azokra a forgatókönyvkere is vonatkoznak, amelyek fel vannak sorolva a [Példaforgatókönyvek a szállítmánykonszolidáció irányelveinek használatára](#example-scenarios) szakaszban.)

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
1. Zárja be a lapot, majd ismételje meg a 4–5. lépést a *US-004* partnerszámmal rendelkező vevőnél.

### <a name="create-example-policy-1"></a>1. példairányelv létrehozása

Ebben a példában létrehozza a *Vevő+mód* irányelvet, amely a következő üzleti esetben használatos:

- Az irányelv egy specifikus vevői számlát (*US-001*) és specifikus szállítási módot (*Légitá-Légi*) fog lekérdezni.
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
1. A **Konszolidációs mezők** gyorslapon a **Fennmaradó mezők** listában válassza ki a sort, ahol a **Mező neve** mező beállítása *Szállítási mód*.
1. Válassza a **Hozzáadás** gombot ![(a jobbra nyilat).](media/forward-button.png) hogy a mezőt a **Kijelölt mezők** listába helyezze át.
1. A műveleti ablaktáblán válassza a **Lekérdezés szerkesztése** lehetőséget.
1. A lekérdezéstervező párbeszédablakában a **Tartomány** lapon levő rácsban keresse meg a sort, ahol a **Mező** mező beállítása *Vevői számla*, és állítsa az adott sor **Feltételek** mezőjének értékét: *US-001*.
1. A **Hozzáadás** gombbal adjon hozzá egy sort a rácshoz a következő beállításokkal:

    - **Tábla:** *Rendeléssorok*
    - **Származtatott tábla:** *Rendeléssorok*
    - **Mező:** *Szállítási mód*
    - **Feltételek:** *Légitá-Légi*

1. Az **OK** gombbal zárja be a párbeszédpanelt.

> [!NOTE]
> Ennél az üzleti esetnél az *US-001* vevőhöz tartozó rendelési sorok, amelyek szállítási módja *Légitá-Légi*, nem lesznek rendelések között konszolidálva. Ezt az irányelvet először sorrendben kell használni, olyan esetekben, ahol az összes többi szállítási módhoz tartozó szállítmányok konszolidálva vannak ehhez a vevőhöz.

### <a name="create-example-policy-2"></a>2. példairányelv létrehozása

Ebben a példában létrehozza a *Veszélyes áruk* irányelvet, amely a következő üzleti esetben használatos:

- Az irányelv egy specifikus szűrőkódot (*veszélyes*) és specifikus szállítási módot (*Légitá-Légi*) fog lekérdezni.
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
1. A **Konszolidációs mezők** gyorslapon a **Fennmaradó mezők** listában válassza ki a sort, ahol a **Mező neve** mező beállítása *Szállítási mód*.
1. Válassza a **Hozzáadás** gombot ![(a jobbra nyilat).](media/forward-button.png) hogy a mezőt a **Kijelölt mezők** listába helyezze át.
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
> Ebben az üzleti esetben az összes olyan sor, amelyben a cikkek specifikus szűrőkóddal rendelkeznek (azaz a szűrőkód, ahol a **4. kód** mező beállítása *Gyúlékony*), konszolidálva lesz az ugyanolyan típusú másik cikkekkel a rendelések között. Ha ugyanahhoz a számlához, raktárhoz és cikkcsoporthoz nyitott szállítmány tartozik, az új sorok hozzákapcsolódnak.

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
1. A **Konszolidációs mezők** gyorslapon a **Fennmaradó mezők** listában válassza ki a sort, ahol a **Mező neve** mező beállítása *Vevői igénylés*.
1. Válassza a **Hozzáadás** gombot ![(a jobbra nyilat).](media/forward-button.png) hogy a mezőt a **Kijelölt mezők** listába helyezze át.
1. A **Fennmaradó mezők** listában válassza ki a sort, ahol a **Mező neve** mező beállítása *Szállítási mód*.
1. Válassza a **Hozzáadás** gombot ![(a jobbra nyilat).](media/forward-button.png) hogy a mezőt a **Kijelölt mezők** listába helyezze át.
1. A műveleti ablaktáblán válassza a **Lekérdezés szerkesztése** lehetőséget.
1. A lekérdezéstervező párbeszédablakában a **Tartomány** lapon keresse meg a sort, ahol a **Mező** mező beállítása *Vevői számla*, és állítsa az adott sor **Feltételek** mezőjének értékét: *US-001*.
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
1. A **Konszolidációs mezők** gyorslapon a **Fennmaradó mezők** listában válassza ki a sort, ahol a **Mező neve** mező beállítása *Szállítási mód*.
1. Válassza a **Hozzáadás** gombot ![(a jobbra nyilat).](media/forward-button.png) hogy a mezőt a **Kijelölt mezők** listába helyezze át.
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

Ez az üzleti eset általában [a kezdeti konszolidációs irányelvek beállítása során létrehozott alapértelmezett irányelvekkel foglalkozik](#initial-policies). Azonban manuálisan is létrehozhat hasonló irányelveket az alábbi lépések követésével.

1. Nyissa meg a **Raktárkezelés \> Beállítás \> Kiadás raktárnak \> Szállítmánykonszolidációs irányelvek** pontot.
1. Az **Irányelvtípus** mezőt állítsa *Értékesítési rendelések* értékre.
1. A műveleti ablaktáblán válassza az **új** lehetőséget, ha a következő beállításokat tartalmazó irányelvet szeretné létrehozni:

    - **Irányelv neve:** *Rendelésközi*
    - **Irányelv leírása:** *Rendelésközi konszolidáció meghatározott raktáraknál*

1. Hagyja a **Konszolidációt nyitott szállítmányokkal** beállítást *Nem* értéken.
1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.
1. A **Konszolidációs mezők** gyorslapon a **Fennmaradó mezők** mezőben válassza ki a sort, ahol a **Mező neve** mező beállítása *Szállítási mód*.
1. Válassza a **Hozzáadás** gombot ![(a jobbra nyilat).](media/forward-button.png) hogy a mezőt a **Kijelölt mezők** listába helyezze át.
1. A műveleti ablaktáblán válassza a **Lekérdezés szerkesztése** lehetőséget.
1. A lekérdezéstervező párbeszédablakában a **Tartomány** lapon keresse meg a sort, ahol a **Mező** mező beállítása *Raktár*, és állítsa az adott sor **Feltételek** mezőjének értékét: *61, 63*.
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

A következő esetek bemutatják, hogy hogyan használhatók a cikk elolvasása során létrehozott szállítmánykonszolidációi irányelvek. Minden egyes forgatókönyv végigvezeti egy szállítmánykonszolidációs irányelveket használó szállítmánykonszolidációs folyamaton a raktárba történő automatikus vagy manuális kiadáskor:

- 1. forgatókönyv: [Szállítmányok konszolidálása a raktárba történő kiadáskor Értékesítési rendelések automatikus kiadása funkció használatával](../warehousing/consolidate-shipments-automatic.md)
- 2. forgatókönyv: [Szállítmányok konszolidálása, amikor a szállítmánykonszolidációs irányelv felülírásra kerül a Kiadástól a raktárba lapról](../warehousing/consolidate-shipments-release-to-warehouse-override.md)
- 3. forgatókönyv: [Szállítmányok konszolidálása a Kiadás a raktárba lehetőség használatával a Rakománytervező munkaterület oldalról](../warehousing/consolidate-shipments-load-planning-workbench.md)
- 4. forgatókönyv: [Szállítmányok konszolidálása a szállítmánykonszolidációs munkaterület használatával](../warehousing/consolidate-shipments-manual-workbench.md)
- 5. forgatókönyv: [Szállítmányok manuális konszolidálása a szállítmányok konszolidálása oldal használatával](../warehousing/consolidate-shipments-manual-form.md)


## <a name="additional-resources"></a>További erőforrások

- [Szállítmánykonszolidáció irányelveinek áttekintése](about-shipment-consolidation-policies.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
