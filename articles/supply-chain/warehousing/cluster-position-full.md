---
title: Fürtpozíció tele
description: Ez a témakör a Fürtpozíció tele funkcióról nyújt tájékoztatást. Ez a funkció a munkamegszakítási szabályok szigorúbb végrehajtását teszi lehetővé a fürtkitárolás használata esetén, mivel nagyobb hibahatárt tesz lehetővé a tárolók és rakományok térfogatkorlátai tekintetében.
author: Mirzaab
ms.date: 08/25/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSClusterProfile
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 2da0421bdb1496d51c807e51a26a980238886a42dfec167dac95611cc3df97bd
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6730034"
---
# <a name="cluster-position-full"></a>Fürtpozíció tele

[!include [banner](../includes/banner.md)]

A *Fürtpozíció tele* funkció a munkamegszakítási szabályok szigorúbb végrehajtását teszi lehetővé a fürtkitárolás használata esetén, mivel nagyobb hibahatárt tesz lehetővé a tárolók és rakományok térfogatkorlátai tekintetében. Gyakori, hogy a munkarendelés minden cikke nem fér el a kiválasztott tárolóban. A fürtkitárolást végző raktári dolgozók csak néhány lehetőséggel rendelkeznek ebben a helyzetben: vagy egy nagyobb tárolóra váltanak, vagy a felettesükkel keresnek másik megoldást.

Ez a funkció bevezeti a **Megtelt** gomb futtatásának lehetőségét a fürt egyik munkaegységén. A régebbi verziókban ez a lehetőség csak a szokásos rendeléskitároláskor volt elérhető, na fürtkitároláshoz nem. Ez a funkció azonban különbözik a szokásos **Megtelt** gombtól, amely a hátralévő munkát érvényteleníti. Nem javasolja, hogy a felhasználó adjon hozzá egy másik tárolót ugyanahhoz a fürthöz, és nem hoz létre automatikusan új munkát.

## <a name="turn-on-the-cluster-position-full-feature"></a>A Fürtpozíció tele funkció bekapcsolása

A funkció használata előtt be kell azt kapcsolnia saját rendszerében. A rendszergazdák használhatják a [funkciókezelési](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) beállításokat a funkció állapotának ellenőrzéséhez, és bekapcsolásához. A **Funkció kezelése** munkaterületen a funkció a következő módon van listázva:

- **Modul:** *Raktárkezelés*
- **Funkció neve:** *Fürtpozíció tele*

## <a name="setup"></a>Beállítás

Ez a szakasz iránymutatásokat tartalmaz, és egy példán bemutatja, hogyan lehet beállítani és használni a *Fürtpozíció tele* funkciót.

### <a name="make-sample-data-available"></a>A mintaadatok elérhetővé tétele

Ha ezt a [példaforgatókönyvet](#example-scenario) az itt megadott mintaadatok és értékek alapján kívánja elvégezni, akkor egy olyan rendszert kell használnia amelynél a szokásos [bemutatóadatok](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) telepítve vannak. Emellett az **USMF** jogi személyt is ki kell választani a kezdés előtt.

A példaforgatókönyvet a gyártási rendszerben végzett munka során a funkció használatához útmutatásként is használhatja. Ebben az esetben azonban az itt leírt beállítás esetében be kell helyettesítenie a saját értékeit.

### <a name="cluster-profiles"></a>Fürtprofilok

Meg kell adnia, hogy a rendszer automatikusan generálja-e a fürtazonosítókat, hány pozíciót használ, amikor a fürtök megszakadnak, valamint a kitárolási munka sorrendjének és ellenőrzésének módját.

1. Kattintson a **Raktárkezelés \> Beállítás \> Mobileszköz \> Fürtprofilok** elemre.
1. A lista ablaktáblán válassza ki a **Fürt létrehozása** rekordot.
1. Az **Általános** gyorslapon ellenőrizze a következő értékeket:

    - **Fürtazonosító létrehozása:** *Igen*
    - **Pozíciók aktiválása:** *Igen*
    - **Pozíciók száma:** *2*
    - **Pozíció neve:** *Numerikus*
    - **Fürt felbontása ennél:** *Betárolás*
    - **Rendezés ellenőrzési típusa:** *Pozíció beolvasása*

1. A **Fürtrendezés** gyorslapon. A rácsnak üresnek kell lennie (azaz nem tartalmazhat sort).

### <a name="work-templates"></a>Munkasablonok

Definiálnia kell, hogyan jön létre a kitárolása munka a fürtkitároláshoz.

1. Lépjen a **Raktárkezelés \> Beállítás \> Munka \> Munkasablonok** elemre.
1. A lap tetején állítsa a **Munkarendelés típusa** mezőt az *Értékesítési rendelések* értékre.
1. Győződjön meg róla, hogy a bemutató adatok közül a következő munkasablonok szerepelnek a listában. Ha nem állnak rendelkezésre, akkor nem tudja elvégezni a forgatókönyvet.

    - 61 SO Állapor
    - 61 SO Fürt kitárolása

### <a name="location-directives"></a>Helyutasítások

Meg kell adnia, hogy a cikkek honnan lesznek kitárolva, és hová kerülnek.

1. Ugrás a **Raktárkezelés \> Beállítás \> Helyutasítások** elemre.
1. A listafejlécben állítsa át a **Munkarendelés típusa** mezőt *Értékesítési rendelések* értékre.
1. Győződjön meg róla, hogy a bemutató adatok közül a következő értékesítésirendelés-utasítások szerepelnek a listában. Ha nem állnak rendelkezésre, akkor nem tudja elvégezni a forgatókönyvet.

    - 61 Fürt kitárolása
    - 61 SO Kitárolása sorrendje

### <a name="mobile-device-menu-items"></a>Mobileszköz menüpontjai

A folyamatban lévő munkát, hogy fürtkitárolás által használandó mobileszköz menü elemeinek beállítása szükséges. A fürtök kitárolásához használható mobileszköz menüpontban be kell kapcsolni a **Munka felosztásának engedélyezése** paramétert, és az *SO kitárolás* munkaosztályt hozzá kell adni.

1. Lépjen a **Raktárkezelés \> Beállítás \> Mobileszköz \> Mobileszköz-menüelemek** részre.
1. A lista ablaktáblán válassza ki a **Fürtkitárolás létrehozása** rekordot.
1. A műveleti ablaktáblán válassza a **Szerkesztés** lehetőséget.
1. Az **Általános** gyorslapon állítsa be a következő értékeket:

    - **Elrendelte:** *Fürtkitárolás*
    - **Azonosítótábla létrehozása:** *Igen*
    - **Munka felosztásának engedélyezése:** *Igen*
    - **Fürt profil azonosítója:** *Fürt létrehozása*

    Az összes többi mezőben hagyja meg az alapértelmezett értéket.

1. A **Munkaosztályok** gyorslapon szükség szerint adja meg a következő két sort:

    - 1. sor (általában a demó adatokban szerepel):

        - **Munkaosztály azonosítója:** *Értékesítés* 
        - **Munkarendelés típusa:** *Értékesítési rendelések*

    - 2. sor (A demó adatokban valószínűleg nem szerepel):

        - **Munkaosztály azonosítója:** *SO Pick*
        - **Munkarendelés típusa:** *Értékesítési rendelések*

1. Nyissa meg a Műveleti panelen a **Munka visszaigazolásának beállítása** lehetőséget.
1. Válassza ki a **Szerkesztés** opciót.
1. Adja meg a következő értékeket a soron a rácsban.
    - **Munka típusa** - *Kitárolás*
    - **Termék visszaigazolása** - *Jelölje be a jelölőnégyzetet*

1. Válassza a műveleti ablaktábla **Mentés** elemét, majd zárja be a lapot.

## <a name="create-picking-work"></a>Kitárolási munka létrehozása

A fürtök kitárolásának elkezdése előtt létre kell hoznia egy kimenő munkát. A korábban létrehozott fürtprofil két fürtpozíciót határoz meg. Emiatt legalább két munkaazonosítót kell létrehozni az értékesítési rendelés kitárolásához. Ehhez a helyzethez tranzakciók történnek a *61-es* raktárban , és ezek az *L0101* és *T0100* cikkeket fogják használni. A demó adatoknak elég aktuális készlettel kell rendelkezniük ezekből a cikkekből. Győződjön meg róla, hogy elegendő készlet van a tranzakciók befejezéséhez.

### <a name="create-sales-order-1"></a>1. értékesítési rendelés létrehozása

1. Ugorjon az **Értékesítés és marketing \> Értékesítési rendelések \> Minden értékesítési rendelés** pontra.
1. Az 1. értékesítési rendelés létrehozásához kattintson az **Új** elemre.
1. Az **Értékesítési rendelés létrehozása** párbeszédpanelen adja meg a következő értékeket:

    - **Vevőkód** *US-010*
    - **Raktár:** *61*

1. Válassza ki az **OK** lehetőséget.
1. A program megnyitja az új értékesítési rendelést. Az **Értékesítésirendelés-sorok** gyorslapon adjon hozzá egy sort, amely a következő beállításokat tartalmazza:

    - **Cikkszám:** *T0100*
    - **Mennyiség:** *5*

1. A dátum a **Sor részletei** gyorslapon a **Szállítás** lapjának, a **Visszaigazolt szállítási dátum** mezőjében jelenik meg.
1. Az **Értékesítésirendelés-sorok** gyorslapon adjon hozzá egy második sort, amely a következő beállításokat tartalmazza:

    - **Cikkszám:** *L0101*
    - **Mennyiség:** *20*

1. A dátum a **Sor részletei** gyorslapon a **Szállítás** lapjának, a **Visszaigazolt szállítási dátum** mezőjében jelenik meg.
1. Minden újonnan hozzáadott sorhoz kövesse az alábbi lépéseket a készlet foglalásához:

    1. Válassza ki azt a sort, amelyet le szeretne foglalni.
    2. Az **Értékesítési rendelés sorai** gyorslapon válassza a **Készlet \> Foglalás** lehetőséget.
    3. A **Foglalás** oldalon, a műveleti panelen válassza az **Adag foglalása** elemet a készlet foglalásához.
    4. Zárja be a **Foglalás** képernyőt.

1. Válassza ki a művelet ablaktáblán a **Raktár** lapon a **Kiadás raktárba** lehetőséget.

    Amikor a feloldás elkészült, olyan tájékoztató üzenetek érkeznek, amelyek az adott kiadásból létrehozott hullámazonosítót rakományazonosítót jelenítik meg.

### <a name="create-sales-order-2"></a>2. értékesítési rendelés létrehozása

1. Ugorjon az **Értékesítés és marketing \> Értékesítési rendelések \> Minden értékesítési rendelés** pontra.
1. Az 2. értékesítési rendelés létrehozásához kattintson az **Új** elemre.
1. Az **Értékesítési rendelés létrehozása** párbeszédpanelen adja meg a következő értékeket:

    - **Vevőkód** *US-011*
    - **Raktár:** *61*

1. Válassza ki az **OK** lehetőséget.
1. A program megnyitja az új értékesítési rendelést. Az **Értékesítésirendelés-sorok** gyorslapon adjon hozzá egy sort, amely a következő beállításokat tartalmazza:

    - **Cikkszám:** *L0101*
    - **Mennyiség:** *20*

1. A dátum a **Sor részletei** gyorslapon a **Szállítás** lapjának, a **Visszaigazolt szállítási dátum** mezőjében jelenik meg.
1. Az **Értékesítésirendelés-sorok** gyorslapon adjon hozzá egy második sort, amely a következő beállításokat tartalmazza:

    - **Cikkszám:** *T0100*
    - **Mennyiség:** *2*

1. A dátum a **Sor részletei** gyorslapon a **Szállítás** lapjának, a **Visszaigazolt szállítási dátum** mezőjében jelenik meg.
1. Minden újonnan hozzáadott sorhoz kövesse az alábbi lépéseket a készlet foglalásához:

    1. Válassza ki azt a sort, amelyet le szeretne foglalni.
    2. Az **Értékesítési rendelés sorai** gyorslapon válassza a **Készlet \> Foglalás** lehetőséget.
    3. A **Foglalás** oldalon, a műveleti panelen válassza az **Adag foglalása** elemet a készlet foglalásához.
    4. Zárja be a **Foglalás** képernyőt.

1. Válassza ki a művelet ablaktáblán a **Raktár** lapon a **Kiadás raktárba** lehetőséget.

    Amikor a feloldás elkészült, olyan tájékoztató üzenetek érkeznek, amelyek az adott kiadásból létrehozott hullámazonosítót rakományazonosítót jelenítik meg.

### <a name="get-work-ids-and-license-plate-numbers"></a>Munkaazonosítók és azonosítótábla-számok beolvasása

Két munkaazonosítót kellett létrehozni, amelyek mindegyikében két kitárolási sor van. A munkaazonosítók és az azonosítótábla-hozzárendelések megkereséséhez hajtsa végre az alábbi lépéseket.

1. Ugorjon a **Raktárkezelés \> Munka \> Munka részletei** pontra.
1. Az **Áttekintés** rácsban keresse meg az imént létrehozott két értékesítési **Rendelési szám** oszlopát. Jegyezze fel az egyes értékesítési rendelések kapcsolódó munkaazonosítóját.
1. Válassza ki az egyes értékesítési rendelések sorát a **Sorok** rácsban. Jegyezze fel azt a helyet, ahonnan a cikkek kitárolása történik.
1. Menjen a **Készletkezelés \> Lekérdezések és jelentések \> Aktuális készletlista** lehetőségre.
1. A műveleti ablaktáblán kattintson a **Dimenziók** gombra a **Dimenziók megjelenítése** párbeszédpanel megnyitásához.
1. Győződjön meg róla, hogy be van jelölve az **Azonosítótábla** a **Raktár** és a **Cikkszám** jelölőnégyzet, majd kattintson az **OK** gombra.
1. A **Szűrő** ablaktáblában adja meg a következő szűrőket:

    - **Cikkszám** – **egyike a következőknek** – *L0101* és *T100*
    - **Raktár** – **így kezdődik** – *61*

1. Jegyezze fel a megjelenő **Azonosítótábla** értékeket.

## <a name="example-scenario"></a><a name="example-scenario"></a>Példaforgatókönyv

### <a name="mobile-device-flow-execution--work-confirmation-setup-for-the-product"></a>Mobileszköz-folyamat végrehajtása – A termékre vonatkozó munka-visszaigazolás beállítása

1. Jelentkezzen be az *61*-es raktárban lévő felhasználóként a Raktárkezelés mobilalkalmazásba.
1. Menjen a **Kimenő \> Fürtkitárolás létrehozása** helyre.

    Megjelenik a **Feladat: Munka hozzárendelése a fürthöz** lap.

1. Adja meg az 1. értékesítési rendelés munkaazonosítóját az 1. fürtcsoporthoz való hozzárendeléséhez.
1. Jelölje be az **OK** lehetőséget (pipa szimbólum).
1. Adja meg az 2. értékesítési rendelés munkaazonosítóját az 2. fürtcsoporthoz való hozzárendeléséhez.
1. Jelölje be az **OK** lehetőséget (pipa szimbólum).

    A **FELADAT: Fürtkitárolás létrehozása: kitárolás** oldal jelenik meg, és a *Item L0101 2 PL cikk* értéket jeleníti meg.

Mivel a fürtprofilban a pozíciók száma 2, a rendszer automatikusan átirányítja az első konszolidáló kitárolásához: két raklap (PL) az *L0101* cikkből.

A következő lépések során bármikor a **Részletek** lapon megtekintheti a feladattal kapcsolatos további adatokat, például a kitárolási helyet.

1. Állítsa a **CIKK** mezőt *L0101* értékre. Ez megerősíti a cikkszámot, amely szükséges ehhez a menüelemhez (ezt a beállítást korábban konfigurálta a **Munka-visszaigazolás beállítása** helyen a **Mobileszköz menüelem** oldalon, amikor létrehozta ezt a menüelemet).
1. Adja meg, hogy milyen azonosítótábla van társítva a cikkhez a kitárolás alatt álló helyen. Két raklapot fog kitárolni.
1. Állítsa az **LP** mezőt *LP\_KITÁROLÁS\_01* értékre.
1. Jelölje be az **OK** lehetőséget (pipa szimbólum).

    Megjelenik **FELADAT: Rendezés: Fürtkitárolás létrehozása** oldal. Itt rendezni fogja a két kitárolt raklapot egy kitárolási pozícióba. Ez a beosztás olyan ládát vagy tároló lehet, amely a kitárolt készlet értékesítési rendelés szerinti elkülönítésére szolgál.

1. A cikkhez (*L0101*) és mennyiséghez (*20* ea) megjelenített részletek megjelenítésem amelyek az 1-es pozícióba lesznek rendezve (az 1. értékesítési rendeléshez).
1. Állítsa a **POZÍCIÓ NA** mezőt *1* értékre.
1. Jelölje be az **OK** lehetőséget (pipa szimbólum).
1. A cikkhez (*L0101*) és mennyiséghez (*20* ea) megjelenített részletek megjelenítésem amelyek az 2-es pozícióba lesznek rendezve (az 2. értékesítési rendeléshez).
1. Állítsa a **POZÍCIÓ NA** mezőt *2* értékre.
1. Jelölje be az **OK** lehetőséget (pipa szimbólum).

    A **FELADAT: Fürtkitárolás létrehozása: kitárolás** oldal jelenik meg, és a *Item T0100 7 ea* értéket jeleníti meg.

Ebben az esetben az 1. pozíció nem fogadja el a cikkek teljes mennyiségét, amelyet ki kell tárolni az 1. értékesítési rendelés teljesítéséhez. A pozíciót telinek kell megjelölni. Ebben a helyzetben a második elem részleges kitárolását fogja elvégezni. A második cikk részben kitárolásra kerül az 1. pozícióban, és új munka jön létre, hogy kitárolja a rendelés teljesítéséhez szükséges maradék mennyiséget.

1. Válassza ki a lap tetején látható Menü gombot (néha hamburgernek vagy a hamburgergombnak is nevezik), majd válassza ki a **Pozíció tele** lehetőséget.
1. Azonosítsa a teli beosztást, és válassza az *1* értéket.
1. Jelölje be az **OK** lehetőséget (pipa szimbólum).
1. Adja meg a kitárolási mennyiséget, amely az 1. pozícióba továbbra is kitárolható. A rendszer meghatározhatja, hogy mely cikkszám van kitárolva.
1. Adja meg az *2* értéket.
1. Jelölje be az **OK** lehetőséget (pipa szimbólum).
1. A cikkszám jóváhagyása a fennmaradó cikkek kitárolásának a 2. pozícióba művelet befejezéséhez.
1. Állítsa a **CIKK** mezőt *T0100* értékre.
1. Jelölje be az **OK** lehetőséget (pipa szimbólum).
1. Adja meg azt az azonosítótáblát, amelyből az elem ki lesz tárolva, ehhez az **LP** mezőt *LPREPL04* értékre kell állítani.
1. Jelölje be az **OK** lehetőséget (pipa szimbólum).
1. A cikkhez (*T0100*) és mennyiséghez (*2* ea) megjelenített részletek megjelenítésem amelyek az 2-es pozícióba lesznek rendezve (az 2. értékesítési rendeléshez).
1. Állítsa a **POZÍCIÓ NA** mezőt *2* értékre.
1. Jelölje be az **OK** lehetőséget (pipa szimbólum).
1. A cikkhez (*T0100*) és mennyiséghez (*2* ea) megjelenített részletek megjelenítésem amelyek az 1-es pozícióba lesznek rendezve (az 1. értékesítési rendeléshez).
1. Állítsa a **POZÍCIÓ NA** mezőt *1* értékre.
1. Jelölje be az **OK** lehetőséget (pipa szimbólum).

    Megjelenik **FELADAT: Rendezés: Betárolás létrehozása** oldal.

Ebben a helyzetben a fürt kitárolása kész, és a felhasználó azt az utasítást kapja, hogy tárolja el a kitárolt cikkeket az 1. pozícióból és a 2. pozícióból a *STAGE01* előkészítő területre.

1. Tekintse át a lap adatait. Azt jelzi, hogy a *44* a teljes mennyiség, ami az előkészítési helyre kerül.
1. Jelölje be az **OK** lehetőséget (pipa szimbólum).

    Megjelenik a „Fürt befejezve” üzenet.

Ezután az **Értékesítési kitárolás** menüelemmel kitárolhatja a fennmaradó mennyiséget. Ezután az **Értékesítési rakodása** menüelemmel mozgathatja a cikkeket az előkészítési helyről a rakodási helyre.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]