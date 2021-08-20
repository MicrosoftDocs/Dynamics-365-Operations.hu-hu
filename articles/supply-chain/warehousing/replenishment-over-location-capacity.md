---
title: Feltöltés a hely kapacitása alapján
description: Ez a témakör a hely kapacitásainak feltöltésével kapcsolatban tartalmaz tájékoztatást. Ez a funkció lehetővé tesz minden olyan feltöltési munkát, amely a nap létrehozásához szükséges, illetve a feltöltési munka elérhetőségét kezeli annak érdekében, hogy a kitárolási hely ne fogyjon ki a készletből, és ne haladja meg a kapacitást sem.
author: mirzaab
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSReplenishmentTemplates, WHSLocationLimit
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-16
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: d337c9ab01f86fa7f1b2cbd80674ccf6783f637b98cd26c838a6e44e287b2c7e
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6744606"
---
# <a name="replenishment-over-location-capacity"></a>Feltöltés a hely kapacitása alapján

[!include [banner](../includes/banner.md)]

Néhány nagy vagy korlátozott hellyel rendelkező raktárnak egy adott cikkből nagyobb mennyiséget kell szállítania, mint amennyi a kitárolási helyen el fog férni. A *Feltöltés a hely kapacitása alapján* funkció lehetővé tesz minden olyan feltöltési munkát, amely a nap létrehozásához szükséges, illetve a feltöltési munka elérhetőségét kezeli annak érdekében, hogy a kitárolási hely ne fogyjon ki a készletből, és ne haladja meg a kapacitást sem.

Ez a funkció több feltöltési munka létrehozását teszi lehetővé, mint amennyi egy helyen elfér, és a hely megtelése esetén blokkolja a feltöltési munka befejezését. Mivel a kitárolási helyen lévő készlet egy konfigurálható küszöbérték alá esik, több feltöltési munka is elérhetővé válik.

## <a name="turn-on-the-replenishment-over-location-capacity-feature"></a>Kapcsolja be a Feltöltés a hely kapacitása alapján funkciót

A funkció elérhetővé tétele érdekében kapcsolja be a [funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) modulban a következő szolgáltatásokat (ebben a sorrendben):

1. Szervezeti szintű munkazárolás
1. Feltöltés a hely kapacitása alapján

## <a name="set-up-the-feature-for-the-example-scenario"></a>A funkció beállítása a példaforgatókönyvhöz

Ez a szakasz iránymutatásokat és egy példát mutat be azzal kapcsolatban, hogy hogyan kell beállítani ezt a funkciót, illetve hogyan kell előkészíteni mintaadatokat a témakörben később bemutatott példaforgatókönyvben.

### <a name="enable-sample-data"></a>Mintaadatok engedélyezése

Ha ezt a [példaforgatókönyvet](#example-scenario) az itt megadott mintaadatok és értékek alapján kívánja elvégezni, akkor egy olyan rendszert kell használnia amelynél a szokásos [bemutatóadatok](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) telepítve vannak. Emellett az **USMF** jogi személyt is ki kell választani a kezdés előtt.

### <a name="location-profile"></a>Helyprofil

A Feltöltés a kapacitás szerint funkció engedélyezése a hely profilja alapján.

1. Ugorjon a **Raktárkezelés \> Beállítás \> Raktár \> Helyek profiljai** pontra.
1. A bal oldali ablaktáblában válassza ki a **PICK-06** elemet.
1. A műveleti ablaktáblán válassza a **Szerkesztés** lehetőséget.
1. A **Feltöltés** gyorslapon állítsa be a következő értékeket:

    - **Hely kapacitásának meghaladása:** *Igen*

        Ha engedélyezve van, a hely maximális kapacitását túllépheti a feltöltési munka. Ez a **Feltöltés** gyorslap egyéb mezőit is engedélyezi.

    - **Munka elérhetőségi küszöbértékének típusa:** *Mennyiség*

        Ez a mező azt a módszert határozza meg, amellyel meghatározható, hogy mikor kell több munkát felszabadítani. A kiadást végezheti százalék, összeg vagy mennyiség szerint is:

        - *Százalék* – Akkor válassza ezt a lehetőséget, ha a rakodási korlátozásokon vagy a térfogatmérésen alapuló százalékos kapacitást kívánja használni. Ha ezt a lehetőséget választja, akkor engedélyezi a **Túlcsordulási százalék** mezőt, és letiltja a két mennyiséggel kapcsolatos mezőt, a **Túlcsordulási mennyiséget** és a **Túlcsordulási egység** lehetőséget.

            Ezt a lehetőséget akkor használja, ha a kitárolási helyek térfogatmérést használnak.

            Ha ez a beállítás be van jelölve, akkor állítsa a **Túlcsordulási százalék** mezőt arra a százalékos értékre, amelyen több feltöltési munka is rendelkezésre fog állni.

        - *Mennyiség* – Akkor válassza ezt a lehetőséget, ha az adott mennyiségi értéket kívánja használni. Ha ezt a lehetőséget választja, akkor letiltja a **Túlcsordulási százalék** mezőt, és engedélyezi a **Túlcsordulási mennyiséget** és a **Túlcsordulási egység** mezőket.

            Akkor használja ezt a beállítást, ha nem használ térfogatmérést a feltöltés alatt álló helyekhez, vagy ha olyan konzisztens mennyiségekkel rendelkezik, amelyekből több készletet szeretne a helyre vinni.

           Ha ez a beállítás be van jelölve, akkor állítsa a **Túlcsordulási mennyiség** és a **Túlcsordulási egység** mezőket annak a mennyiségnek és egységnek az értékére, amelyen több feltöltési munka fog rendelkezésre állni.

    - **Túlcsordulási mennyiség:** *0,65*

        Ez a mező határozza meg a hely túlcsordulásának mennyiségét.

        A munka rendelkezésre áll bármikor, amikor a hely aktuális mennyiségének összeg és munkamennyisége ez alatt az érték alatt van. A feltöltési munka azon része, amely meghaladja ezt az értéket, zárolva lesz, és manuálisan kell feloldani.

        A hely rakodási korlátait a munkamennyiség számításakor kell figyelembe venni.

    - **Túlcsordulási egység:** *PL*

        Ez a mező azt a egységet határozza meg, amely a túlcsordulási mennyiséghez van társítva.

        Ebben az esetben több feltöltési munka lesz elérhető, ha a hely eléri a 0,65 raklapot (PL).

    - **Túlcsordulási százalék**

        Ez a mező határozza meg a hely túlcsordulásának százalékát.

        A munka rendelkezésre áll bármikor, amikor a hely aktuális mennyiségének összeg és munkamennyisége ez alatt a százalék alatt van. A feltöltési munka azon százaléka, amely meghaladja ezt az értéket, zárolva lesz, és manuálisan kell feloldani.

        A hely rakodási korlátait a munkamennyiség százalékának számításakor kell figyelembe venni. Ha nincsenek meghatározva a hely készletezési korlátai, akkor a munkamennyiség százalékos értékét a program a mennyiség alapján határozza meg, ha mennyiségi megszorítások vannak meghatározva a hely profilján.

> [!IMPORTANT]
> Ha az **USMF** jogi személy bemutatóadatait használja, és korábban bekapcsolta a *Hely és azonosítótábla pozicionálása* funkciót, akkor ki kell kapcsolni az **Azonosítótábla pozicionálásának engedélyezésebeállítást** a **BULK-06** hely profiljánál, hogy a példaforgatókönyvben használt mobillépéseket végre tudja hajtani.

### <a name="wave-step-code"></a>Hullámlépés kódja

> [!NOTE]
> Ha az itt leírtak szerint szeretné beállítani a hullámlépés kódját, akkor először a [Funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) lehetőséget kell használnia a *Szervezeti szintű hullámlépéskód* nevű funkció bekapcsolásához.

1. Ugorjon a **Raktárkezelés \> Beállítás \> Hullámok \> Hullámlépéskódok** pontra.
1. Válassza az **Új** lehetőséget, és állítsa be a következő értékeket:

    - **Hullámlépés kódja:** *Feltöltés*
    - **Hullámlépés leírása:** *Feltöltés*
    - **Hullámlépés típusa:** *Feltöltés*

1. Válassza a **Mentés** lehetőséget.

### <a name="replenishment-template"></a>Feltöltési sablon

A feltöltési sablonokat olyan szabályok alkotják, amelyek megszabják, mikor és hogyan töltik fel a helyet.

1. Ugorjon a **Raktárkezelés \> Beállítás \> Feltöltés \> Feltöltési sablonok** pontra.
1. A műveleti ablaktáblán válassza a **Szerkesztés** lehetőséget.
1. Az **Áttekintés** szakaszban válassza ki azt a sort, amelyben a **Feltöltési sablon** mező *Igény feltöltése* lehetőségként van beállítva.
1. Adja meg az alábbi értékeket:

    - **Hullámlépés kódja:** *Feltöltés*
    - **A hullám keresletének engedélyezése nem foglalt mennyiségek használatához:** *Igen*

1. Válassza a **Mentés** lehetőséget.

### <a name="wave-template"></a>Hullámsablon

1. Ugorjon a **Raktárkezelés \> Beállítás \> Hullámok \> Hullámsablonok** pontra.
1. A bal oldali ablaktáblában állítsa a **Hullámsablon típusa** mezőt a *Szállítás* értékre.
1. Válassza ki a sablont a **61 Szállítás** listából.
1. A műveleti ablaktáblán válassza a **Szerkesztés** lehetőséget.
1. Adja meg az **Általános** gyorslap **Feltöltési munka kiadásának automatizálása** beállítását *Igen* értékre.

    Állítsa ezt a lehetőséget *Igen* értékre, hogy a rendszer automatiksuan létrehozza és kiadja az igényalapú feltöltési munkát. Hozzá kell adnia az újratöltési hullámmódszert a hullámsablonhoz, majd létrehozni egy **Hullámigény** típusú újratöltési sablont. **Feltöltési sablonok** lapjának feltöltési sablon beállítása. A feltöltési sablon beállításához a feltöltési módszert hozzá kell adnia a hullámsablonhoz.

1. A **Módok** gyorslapon, a **Kiválasztott módok** oszlopban keresse meg a következő sort:

    - **Mód neve:** *Feltöltés*
    - **Név:** *Feltöltés*

1. Ehhez a sorhoz állítsa a **Hullámlépés kód** mezőt a *Feltöltés* lehetőségre.
1. Válassza a **Mentés** lehetőséget.

## <a name="example-scenario"></a>Példaforgatókönyv

Miután elvégezte az összes korábban leírt mintaadatok elérhetővé tételét és beállítását, a forgatókönyvön keresztül kipróbálhatja a *Feltöltés a hely kapacitása alapján* funkciót. Az ebben a forgatókönyvben látható értékek feltételezik, hogy azokkal a szokásos bemutatóadatokkal dolgozik, amelyeket az **USMF** jogi személyt kiválasztott, és hogy előkészítette a témakör korábbi részében ismertetett mintarekordokat. Ez a forgatókönyv példaként is szolgál, amely megmutatja, hogyan használható a funkció az üzemelési beállításban.

### <a name="create-replenishment-work"></a>Feltöltési munka létrehozása

#### <a name="create-sales-order-1"></a>1. értékesítési rendelés létrehozása

1. Ugorjon az **Értékesítés és marketing \> Értékesítési rendelések \> Minden értékesítési rendelés** pontra.
1. A műveleti ablaktáblán kattintson az **Új** gombra az új értékesítési rendelés létrehozása párbeszédpanel megnyitásához.
1. A párbeszédpanelen adja meg a következő értékeket:

    - **Vevőkód** *US-007*
    - **Raktár:** *61*

1. Válassza az **OK** gombot a beszerzési rendelés létrehozásához és a párbeszédpanel bezárásához.
1. A program megnyitja az új értékesítési rendelést. Tartalmaz egy új, üres sort az **Értékesítési rendelés sorai** gyorslapon. Ezen a soron állítsa be a következő értékeket:

    - **Cikkszám:** *T0100*
    - **Mennyiség:** *40*

1. Az **Értékesítési rendelés sorai** gyorslapon válassza a **Készlet \> Foglalás** lehetőséget.
1. A **Foglalás** lapon válassza ki az **Adag foglalása** elemet.
1. Zárja be a lapot.
1. Válassza ki a művelet ablaktáblán a **Raktár** lapon a **Kiadás raktárba** lehetőséget.

    Olyan tájékoztató üzenetek érkeznek, amelyek az adott kiadásból létrehozott hullámazonosítókat és szállítási azonosítókat jeleníti meg. Egy feltöltési hullám is létrejön.

    Figyelmeztető üzenet jelenik meg, amely jelzi, hogy a(z) „XXXX munkaazonosító nem zárolható, mert befejezetlen feltöltési munkával rendelkezik".

#### <a name="create-sales-order-2"></a>2. értékesítési rendelés létrehozása

1. Az **Összes értékesítési rendelés** oldalon, a műveleti ablaktáblán kattintson az **Új** gombra az új értékesítési rendelés létrehozása párbeszédpanel megnyitásához.
1. A párbeszédpanelen adja meg a következő értéket:

    - **Vevőkód** *US-001*
    - **Raktár:** *61*

1. Válassza az **OK** gombot a beszerzési rendelés létrehozásához és a párbeszédpanel bezárásához.
1. A program megnyitja az új értékesítési rendelést. Tartalmaz egy új, üres sort az **Értékesítési rendelés sorai** gyorslapon. Ezen a soron állítsa be a következő értékeket:

    - **Cikkszám:** *T0100*
    - **Mennyiség:** *60*

1. Az **Értékesítési rendelés sorai** gyorslapon válassza a **Készlet \> Foglalás** lehetőséget.
1. A **Foglalás** lapon válassza ki az **Adag foglalása** elemet.
1. Zárja be a lapot.
1. Válassza ki a művelet ablaktáblán a **Raktár** lapon a **Kiadás raktárba** lehetőséget.

    Olyan tájékoztató üzenetek érkeznek, amelyek az adott kiadásból létrehozott hullámazonosítókat és szállítási azonosítókat jeleníti meg. Egy feltöltési hullám is létrejön.

    Figyelmeztető üzenet jelenik meg, amely jelzi, hogy a(z) „XXXX munkaazonosító nem zárolható, mert befejezetlen feltöltési munkával rendelkezik".

#### <a name="create-sales-order-3"></a>3. értékesítési rendelés létrehozása

1. Az **Összes értékesítési rendelés** oldalon, a műveleti ablaktáblán kattintson az **Új** gombra az új értékesítési rendelés létrehozása párbeszédpanel megnyitásához.
1. A párbeszédpanelen adja meg a következő értékeket:

    - **Vevőkód** *US-004*
    - **Raktár:** *61*

1. Válassza az **OK** gombot a beszerzési rendelés létrehozásához és a párbeszédpanel bezárásához.
1. A program megnyitja az új értékesítési rendelést. Tartalmaz egy új, üres sort az **Értékesítési rendelés sorai** gyorslapon. Ezen a soron állítsa be a következő értékeket:

    - **Cikkszám:** *T0100*
    - **Mennyiség:** *30*

1. Az **Értékesítési rendelés sorai** gyorslapon válassza a **Készlet \> Foglalás** lehetőséget.
1. A **Foglalás** lapon válassza ki az **Adag foglalása** elemet.
1. Zárja be a lapot.
1. Válassza ki a művelet ablaktáblán a **Raktár** lapon a **Kiadás raktárba** lehetőséget.

    Olyan tájékoztató üzenetek érkeznek, amelyek az adott kiadásból létrehozott hullámazonosítókat és szállítási azonosítókat jeleníti meg. Egy feltöltési hullám is létrejön.

    Figyelmeztető üzenet jelenik meg, amely jelzi, hogy a(z) „XXXX munkaazonosító nem zárolható, mert befejezetlen feltöltési munkával rendelkezik".

#### <a name="view-work-details"></a>Munka részletes adatainak megtekintése

1. Ugorjon a **Raktárkezelés \> Munka \> Munka részletei** pontra.
1. Az **Áttekintés** szakaszban szűrje a **Raktár** oszlopot a *61*-es raktár kereséséhez.
1. Ekkor látnia kell, hogy a három igény értékesítési rendeléshez hét munkaazonosító jött létre.

    - A hét munkaazonosító közül háromnak van *Feltöltés* értékű **Munkarendelés típus** lehetősége, négynek pedig *Munkarendelés* értékű **Munkarendelés típus** értéke.
    - Mind a három munkaazonosító, amelynek *Feltöltés* értékű a **Munkarendelés típus** lehetősége, ugyanazzal a *Kitárolás* és *Eltárolás* helyekkel rendelkeznek a **Sorok** szakaszban:

        - **Kitárolás:** *02A01R5S1B*
        - **Eltárolás:** *06A01R2S1B*

    - Az 1. értékesítési rendeléshez két munkaazonosító jött létre.

1. Jegyezze fel az értékesítési rendelések munkaazonosítóit.

A készleten lévő mennyiségtől függően a létrehozott munkamennyiségek kis mértékben különbözhetnek. Összességében azonban a létrehozott munkafejléceknek meg kell egyezniük ennek a forgatókönyvnek a példájával.

#### <a name="on-hand-inventory-license-plate-id"></a>Aktuális készlet-azonosítótábla azonosítója

Később ebben a forgatókönyvben a Raktárkezelés mobilalkalmazást (vagy egy emulátort) fog használni, ahol be kell azonosítania az azonosítótáblát, hogy befejezhesse a kitárolási és feltöltési forgatókönyveket.

A későbbiekben szükséges azonosítótábla-azonosítók megtalálásához, kövesse az alábbi lépéseket.

1. Menjen a **Készletkezelés \> Lekérdezések és jelentések \> Aktuális készletlista** lehetőségre.
1. A szűrő ablaktábla megnyitásához válassza ki a **Szűrők megjelenítése** gombot.
1. Adja meg az alábbi szűrési kritériumot a forgatókönyvhöz tartozó azonosítótábla beolvasásához. Használja az *így kezdődik* szűrőt.

    - **Cikkszám:** *T0100*
    - **Raktár:** *61*

1. Válassza az **Alkalmazás** lehetőséget.
1. A Műveleti ablaktáblán válassza a **Dimenziók** elemet.
1. A **Dimenziók megjelenítése** párbeszédpanel **Tárolási dimenziók** szakaszában válassza ki az összes értéket.
1. A **Tranzakciók** szakaszban válassza ki a **Cikkszám** és a **Mennyiség \<\> 0** lehetőséget.
1. Ha befejezte a munkát, az **OK** gombra kattintva zárja be a párbeszédpanelt.
1. Az **Aktuális** rács megjeleníti a *T0100* cikk egyes helyekhez tartozó azonosítótábla számait. Jegyezze fel az egyes helyeken található azonosítótáblákat, mivel később szüksége lesz ezekre az információkra.
1. Zárja be a lapot.

### <a name="process-steps"></a>Folyamat lépései

A raktárhely feltöltését az első két munkaazonosítónál fogja végrehajtani. A harmadik feltöltési munka során végzett munka mindaddig le lesz tiltva, amíg a kitárolási hely készletszintje nem éri el a küszöbértéket.

#### <a name="replenishment"></a>Feltöltés

1. Jelentkezzen be az *61*-es raktárban lévő felhasználóként a Raktárkezelés mobilalkalmazásba. (Írja be a felhasználói azonosítóhoz a *61*-et, a jelszóhoz pedig az *1*-et.)
1. Lépjen a **Készlet \> Feltöltés** lehetőségre.

    A program megkérdezi, hogy befejezi-e az első feltöltési munkát. Megjelenik a kiválasztható cikkszám, mennyiség, és hely.

1. Az **LP** mezőbe írja be a helyen található elemhez megjelenített azonosítótábla számát.
1. Válassza az **OK** gombot (pipa szimbólum).

    A rendszer létrehoz egy cél-azonosítótábla-számot az új azonosítótábla számára a kitárolt cikkhez.

1. Az érték megerősítséséhez kattintson az **OK** lehetőségre.

    A betárolási munka azt mutatja, hogy a felhasználónak a cél-azonosítótáblát a feltöltési helyre kell helyeznie. A *Betárolás* helynek **06A01R2S1B** kell lennie.

1. Erősítse meg a betárolás részleteit, és válassza az **OK** gombot.

    „Munka befejezve” üzenet jelenik meg, és a következő feltöltési kitárolási feladat részletei jelennek meg: a választható cikkszám, mennyiség és helyet. A kitárolási hely ugyanaz lesz, mint az első feltöltési hely. Ezért az azonosítótáblának ugyanaz lesz az azonosítótábla-azonosítója, mint az első feltöltési munkafeladaté.

1. A második munkafeladathoz tartozó feltöltési munka befejezéséhez ismételje meg a fenti lépéseket. A mennyiség és a cél azonosítótábla különbözni fog az első munkafeladat mennyiségétől és a cél azonosítótáblától.

A második feltöltési munka befejezése után a „Munka befejezve” üzenet jelenik meg. A mobileszköz arról is tájékoztatja, hogy nem érhető el a munka, még akkor is, ha a feltöltési munka továbbra is folyik. Ez a viselkedés akkor fordul elő, ha a feltöltési munka elérhetőségi állapota *Visszatartva*, és ezért **Zárolva** értékkel lesz megjelölve.

A *Visszatartva* állapotot az váltja ki, hogy a munkához társított kitárolási hely helyprofil **Túlcsordulási mennyiség** értéke *0,65 PL*. A két korábbi feltöltési munkafeladat majdnem túllépte a hely *T0100* cikkének túlcsordulási korlátját. (A cikk mértékegység-átváltása *1 PL = 100 ea*.) Ennélfogva a hátralévő feltöltési munka túllépné a hely túlcsordulási korlátját.

Addig, amíg a raktárból elég készletet ki nem tárolnak ahhoz, hogy a mobileszköz menücikk a munkakiadási küszöbérték alá kerüljön, a feltöltési munka továbbra is zárolva marad.

#### <a name="sales-order-pick"></a>Értékesítési rendelés kitárolása

Mielőtt befejezhetné a hátralévő feltöltési munkafeladatot, a kitárolási helyen a készletek olyan szintre kell csökkennie, hogy a hátralévő feltöltési munka feloldhatóvá váljon. Más szóval a raktárban lévő aktuális készlet mennyiségének és a feltöltési mennyiségnek az összege nem haladhatja meg a **Túlcsordulási mennyiség** értékét. Ha ez az összeg kevesebb, mint a túlcsorduló mennyiség, akkor feloldódik a hátralévő feltöltési munka.

1. Jelentkezzen be az *61*-es raktárban lévő felhasználóként a Raktárkezelés mobilalkalmazásba. (Írja be a felhasználói azonosítóhoz a *61*-et, a jelszóhoz pedig az *1*-et.)
1. Lépjen a **Kimenő \> Értékesítési kitárolás** lehetőségre.
1. Adja meg az 1. értékesítési rendelés első munkaazonosítóját.

    A **Munkarészletek** lapon tekintse át a korábban feljegyzett értékesítési rendelések munkaazonosítóit. Az itt megadott munkaazonosító egy 10 ea mennyiségre vonatkozó, két különböző helyről bejövő kitárolási munkát fog létrehozni.

1. Válassza ki az **OK** lehetőséget.

    Az **Értékesítési rendelések: Kitárolás** feladat lapon fogja megjeleníti az első helyhez kiválasztható cikkszámot, mennyiséget és helyet.

1. Az **LP** mezőbe írja be a helyen található elemhez megjelenített azonosítótábla számát.
1. Válassza az **OK** gombot (pipa szimbólum).

    Az **Értékesítési rendelések: Kitárolás** feladat lapon fogja megjeleníti a következő helyhez kiválasztható cikkszámot, mennyiséget és helyet.

1. Az **LP** mezőbe írja be a helyen található elemhez megjelenített azonosítótábla számát.
1. Válassza az **OK** gombot (pipa szimbólum).

    Az **Értékesítési rendelések: Eltárolás** lap utasítja, hogy tárolja el a befejezett kitárolási munkákat a kimenő előkészítési helyre.

1. Válassza ki az **OK** lehetőséget.

    A „Munka befejezve” üzenet jelenik meg.

1. Adja meg az 1. értékesítési rendelés második munkaazonosítóját.

    Ehhez a munkaazonosítóhoz csak egy kitárolási feladat tartozik.

1. Válassza ki az **OK** lehetőséget.

    Az **Értékesítési rendelések: Kitárolás** feladat lapon fogja megjeleníti a kiválasztható cikkszámot, mennyiséget és helyet.

1. Az **LP** mezőbe írja be a helyen található elemhez megjelenített azonosítótábla számát.

    A feltöltési munkafeladatok közül a meghatározott azonosítótábla lesz az egyik rendszer által előállított azonosítótábla. Annak érdekében, hogy rögzítse a helyes azonosítótábla-azonosítót, ellenőrizze a készletet a cikk, hely és mennyiség **Aktuális lista** lapján.

1. Válassza az **OK** gombot (pipa szimbólum).
1. Erősítse meg a kimenő előkészítési hely betárolási feladatának utasításait.
1. Válassza ki az **OK** lehetőséget.

    A „Munka befejezve” üzenet jelenik meg.

A 2. értékesítési rendelés zárolva van a kitárolásból, mert az ezzel összekapcsolt feltöltési feladat nem fejeződött be. Jelenleg még mindig van 30 ea mennyiség van a kitárolási helyen, és a 2. értékesítési rendelés feltöltési mennyisége 60 ea. Az aktuális készlet és a feltöltési készlet (90 ea) összege meghaladja a 0,65 PL (vagy 65 ea) túlcsordulási mennyiséget. A feltöltési munka befejezése előtt a 3. értékesítési rendelést ki kell választani.

1. Adja meg a 3. értékesítési rendelés munkaazonosítóját.

    Ehhez a munkaazonosítóhoz csak egy kitárolási feladat tartozik.

1. Válassza ki az **OK** lehetőséget.

    Az **Értékesítési rendelések: Kitárolás** feladat lapon fogja megjeleníti a kiválasztható cikkszámot, mennyiséget és helyet.

1. Az **LP** mezőbe írja be a helyen található elemhez megjelenített azonosítótábla számát.

    A feltöltési munkafeladatok közül a meghatározott azonosítótábla lesz az egyik rendszer által előállított azonosítótábla. Annak érdekében, hogy rögzítse a helyes azonosítótábla-azonosítót, ellenőrizze a készletet a cikk, hely és mennyiség **Aktuális lista** lapján.

1. Válassza az **OK** gombot (pipa szimbólum).
1. Erősítse meg a kimenő előkészítési hely betárolási feladatának utasításait.
1. Válassza ki az **OK** lehetőséget.

    A „Munka befejezve” üzenet jelenik meg.

Amint a kitárolási helyen található aktuális készlet és a feltöltési mennyiség összege már nem éri el a küszöböt, a hátralévő feltöltési munka feldolgozhatóvá válik.

Térjen vissza a **Munkarészletek** lapra, és figyelje meg, hogy a feltöltés utolsó részének feltöltési munka elérhetősége (2. értékesítési rendelés) *Nyitva* van-e, mivel már van elég hely a feltöltés elfogadásához.

A feltöltési munka most már feldolgozható a mobileszközön keresztül.

1. Lépjen a **Készlet \> Feltöltés** lehetőségre.

    A program megkérdezi, hogy befejezi-e a fennmaradó feltöltési munkát. Megjelenik a kiválasztható cikkszám, mennyiség, és hely.

1. Az **LP** mezőbe írja be a helyen található elemhez megjelenített azonosítótábla számát.
1. Válassza az **OK** gombot (pipa szimbólum).

    A rendszer létrehoz egy cél-azonosítótábla-számot az új azonosítótábla számára a kitárolt cikkhez.

1. Az érték megerősítséséhez kattintson az **OK** lehetőségre.

    A betárolási munka azt mutatja, hogy a felhasználónak a cél-azonosítótáblát a feltöltési helyre kell helyeznie. A *Betárolás* helynek **06A01R2S1B** kell lennie.

1. Erősítse meg a betárolás részleteit, és válassza az **OK** gombot.

    „Munka befejezve” és „Nem érhető el munka” üzenetek jelennek meg.

Most már kitárolhatja a 2. értékesítési rendelést. A zárolás feloldása akkor történik meg, amikor az értékesítési rendeléshez kapcsolódó feltöltési munka be lett fejezve.

1. Adja meg a 2. értékesítési rendelés munkaazonosítóját.

    Ehhez a munkaazonosítóhoz csak egy kitárolási feladat tartozik.

1. Válassza ki az **OK** lehetőséget.

    Az **Értékesítési rendelések: Kitárolás** feladat lapon fogja megjeleníti a kiválasztható cikkszámot, mennyiséget és helyet.

1. Az **LP** mezőbe írja be a helyen található elemhez megjelenített azonosítótábla számát.

    A feltöltési munkafeladatból a meghatározott azonosítótábla lesz a rendszer által előállított azonosítótábla. Annak érdekében, hogy rögzítse a helyes azonosítótábla-azonosítót, ellenőrizze a készletet a cikk, hely és mennyiség **Aktuális lista** lapján.

1. Válassza az **OK** gombot (pipa szimbólum).
1. Erősítse meg a kimenő előkészítési hely betárolási feladatának utasításait.
1. Válassza ki az **OK** lehetőséget.

    A „Munka befejezve” üzenet jelenik meg.

## <a name="notes-and-tips"></a>Megjegyzések és tippek

- Ez a funkció minden feltöltési típussal együtt használható: hullámigény, min/max, terhelési igény és időközökre bontás.
- Szükség szerint manuálisan is felülbírálhatja az egyes munkafejlécekhez tartozó feltöltési munka elérhetőségét a **Munkarészletek** lapon.
- Amikor a rendszer beállítja a feltöltési munka elérhetőségét, minden olyan készletet figyelembe veszi, amely már a helyen van a munka befejezése előtt
- Minden értékesítési rendelés munka egy adott feltöltési munkához kapcsolódik. Nincs kapcsolódó értékesítési munka elérhetőségi funkció.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]