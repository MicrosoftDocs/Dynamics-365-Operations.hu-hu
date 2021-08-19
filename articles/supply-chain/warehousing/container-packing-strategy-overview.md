---
title: Tárolócsomagolási stratégiák
description: Ez a témakör leírja a tárolócsomagolási stratégiák közötti különbségeket, és példákat mutat be.
author: GalynaFedorova
ms.date: 06/11/2021
ms.topic: article
ms.search.form: WHSWaveTemplateTable, InventLocationIdLookup, WHSContainerType, WHSContainerGroup, WHSContainerizationTable, WHSContainerizationBreak, WHSCreateContainerBreak, WHSContainerStructure, WHSContainerTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: intro-internal
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-06-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 4158fa93d9e424e796c038d0c907ea155868440bfcb79666c3e13fa997d4834b
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6774729"
---
# <a name="container-packing-strategies"></a>Tárolócsomagolási stratégiák

A *konténercsomagolási stratégia* olyan stratégia, amin a tárolók közötti cikkallokációk definiálhatók. Ez a témakör bemutatja a *Csomagolás az összes nyitott tárolóba* és a *Csomagolás csak az aktuális tárolóba* stratégiák közötti különbségeket.

- **Csomagolás az összes nyitott tárolóba** – A rendszernek ellenőriznie kell az összes olyan nyitott tárolót, amely már létre lett hozva a tároló-létrehozási ciklus során, hogy a cikk biztosan elférjen valamelyikben. A rendszer a csomagolás során mindegyik cikknél ellenőrzi, hogy befér-e valamelyik korábban létrehozott tárolóba. Ha a cikk nem fér bele egy meglévő tárolóba, a rendszer létrehoz egy új tárolót, és addig folytatja a csomagolást, amíg be nem fejeződik a teljes rendelés csomagolása.

    Például *n* megrendelt cikk esetén tárolóra kell helyezni a tárolót. Ebben a esetben a rendszer minden alkalommal, amikor olyan cikket dlgoz fel, amely nem fér bele egy meglévő tárolóba sem, összesen (\[(*n* – 1) × (*n* + 1)\] ÷ 2) ellenőrzi, hogy a cikk a meglévő tárolókban megfelelő-e.

- **Csomagolás csak az aktuális tárolóba** – A rendszernek csak a legutóbb létrehozott tárolót kell ellenőriznie, hogy az elem biztosan beleférjen. A rendszer a csomagolás során mindegyik cikknél ellenőrzi, hogy befér-e a legutóbb létrehozott tárolóba. Ha a cikk nem fér bele a meglévő tárolóba, a rendszer létrehoz egy új tárolót, és addig folytatja a csomagolást, amíg be nem fejeződik a teljes rendelés csomagolása.

    Például *n* megrendelt cikk esetén tárolóra kell helyezni a tárolót. Ebben a esetben a rendszer összesen (*n*–1) alkalommal ellenőrzi, hogy a cikk belefér-e a tárolókba.

## <a name="example-of-the-flow-for-container-packing-strategies"></a>Példa a tárolócsomagolási stratégiák folyamatára

A következő elemeket állíthata be a tároláshoz.

| Tétel | Fizikai dimenziók (szélesség × mélység × magasság) | Betűvastagság |
|---|---|---|
| HDMI-kábel 6 ' | 1×1×1 | 1 |
| HDMI-kábel 12 ' | 2×1×1 | 1 |
| HDMI-kábel 18 ' | 3×1×1 | 2 |

Beállíthatja következő dobozot is, amelyet a csomagoláshoz használnak.

| Tároló | Fizikai dimenziók (hosszúság × szélesség × magasság) | Betűvastagság | Térfogat |
|---|---|---|---|
| Közepes doboz | 6×3×2 | 10 | 100 |

Végül beállíthat egy rendelést, amely a következő termékeket és mennyiségeket tartalmazza.

| Értékesítésirendelés-sor | Mennyiség |
|---|---|
| HDMI-kábel 12 ' | 9 |
| HDMI-kábel 18 ' | 8 |
| HDMI-kábel 6 ' | 13 |

A következő táblázat összefoglalja, hogy hogyan működik a tárolás, amikor a *Csomagolás az összes nyitott tárolóba* vonatkozó stratégiában használja, és amikor a *Csomagolás csak az aktuális tárolóba* vonatkozó stratégiában használja.

| Csomagolás minden nyitott tárolóba | Csomagolás az aktuális tárolóba |
|---|---|
| <p>HDMI-kábel 12':</p><ol><li>Új tárolótípus létrehozása, CONT0001.</li><li>Tegyen 9 ea-t a CONT0001 tárolóba.</li></ol> | <p>HDMI-kábel 12':</p><ol><li>Új tárolótípus létrehozása, CONT0001.</li><li>Tegyen 9 ea-t a CONT0001 tárolóba.</li></ol> |
| <p>HDMI-kábel 18':</p><ol><li>Ellenőrizze, hogy a cikk elfér-e a CONT0001 tárolóban.</li><li>Új tárolótípus létrehozása, CONT0002.</li><li>Tegyen 5 ea-t a CONT0002 tárolóba.</li><li>Új tárolótípus létrehozása, CONT0003.</li><li>Tegyen 3 ea-t a CONT0003 tárolóba.</li></ol> | <p>HDMI-kábel 18':</p><ol><li>Ellenőrizze, hogy a cikk elfér-e a CONT0001 tárolóban.</li><li>Új tárolótípus létrehozása, CONT0002.</li><li>Tegyen 5 ea-t a CONT0002 tárolóba.</li><li>Új tárolótípus létrehozása, CONT0003.</li><li>Tegyen 3 ea-t a CONT0003 tárolóba.</li></ol> |
| <p>HDMI-kábel 6':</p><ol><li>Ellenőrizze, hogy a cikk elfér-e a CONT0001 tárolóban.</li><li>Tegyen 1 ea-t a CONT0001 tárolóba.</li><li>Ellenőrizze, hogy a cikk elfér-e a CONT0002 tárolóban.</li><li>Ellenőrizze, hogy a cikk elfér-e a CONT0003 tárolóban.</li><li>Tegyen 4 ea-t a CONT0003 tárolóba.</li><li>Új tárolótípus létrehozása, CONT0004.</li><li>Tegyen 8 ea-t a CONT0004 tárolóba.</li></ol> | <p>HDMI-kábel 6':</p><ol><li>Ellenőrizze, hogy a cikk elfér-e a CONT0003 tárolóban.</li><li>Tegyen 4 ea-t a CONT0003 tárolóba.</li><li>Új tárolótípus létrehozása, CONT0004.</li><li>Tegyen 9 ea-t a CONT0004 tárolóba.</li></ol> |

## <a name="example-scenario-pack-single-orders-per-container"></a>Példa erre: Egy rendelés csomagolása tárolónként

Ez a szakasz egy olyan helyzetet mutatja be, amelyben a rendszer úgy van beállítva, hogy több rendelést egyetlen szállítmányba vonja össze. Ennek megfelelően a tárolás az értékesítési rendelésből történik, hogy a több terméket tartalmazó rendeléseket a saját tárolóiba csomagolják.

Ezzel a funkcióval olyan helyzetek kezelhetők, amikor minden egyes tárolóba csak egy értékesítési rendelést kell csomagolni, hogy az elosztási központ teljes tárolókat tudja kitárolni a kiskereskedelmi üzletek között. A kiskereskedelmi helyzeteken kívül (rendelés kiskereskedelmi üzletenként és egy elosztási központhoz történő szállítás áttárolásra) ez a módszer a lean ellátási láncban (az egy időben történő termelési sorra vonatkozó értékesítési rendeléseknél) is használatos.

Ez az eset azt mutatja be, hogyan lehet csökkenteni a csomagolás során kiértékelt tárolók számát a *Csomagolás csak az aktuális tárolóba* vonatkozó stratégia használatával.

### <a name="prerequisites"></a>Előfeltételek

#### <a name="turn-on-the-consolidate-shipments-feature-in-your-system"></a>A Szállítmányok konszolidálása funkció bekapcsolása a rendszerben

Ez az eset a *Szállítmányok konszolidálása* funkciót használja. Ha ez a funkció még nem érhető el a rendszerben, akkor be kell kapcsolnia azt a [Funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) segítségével.

#### <a name="make-demo-data-available"></a>A bemutató adatok elérhetővé tétele

Ez a forgatókönyv olyan értékekre és rekordokra hivatkozik, amelyek szerepelnek a Microsoft Dynamics 365 Supply Chain Management szabványos bemutató adataiban. Ha azt szeretné, hogy az itt megadott értékeket használja a feladatok végrehajtásához, akkor győződjön meg róla, hogy olyan környezetben dolgozik, ahol a bemutatóadatokat telepítették, és a jogi személy beállítása legyen **USMF**.

### <a name="inspect-or-create-container-types"></a>Tárolótípusok vizsgálata vagy létrehozása

A tárolótípusok vizsgálatához vagy szükség esetén új tárolótípusok létrehozásához hajtsa végre ezeket a lépéseket.

1. Ugorjon a **Warehouse Management** \> **Beállítás** \> **Tárolók** \> **Tárolótípusok** pontra.
1. Győződjön meg róla, hogy a következő tárolótípusok mindegyike elérhető a bemutató adataiban. Tárolótípusok szerkesztése és létrehozása a szükségesek szerint.

    - 1. tárolótípus:

        - **Tárolótípus kódja:** *Nagyméretű doboz*
        - **Leírás:** *Nagy doboz*
        - **Maximális nettó súly:** *100*
        - **Térfogat:** *400*
        - **Hossz:** *4*
        - **Szélesség:** *10*
        - **Magasság:** *10*

    - 2. tárolótípus:

        - **Tárolótípus kódja:** *Közepes méretű doboz*
        - **Leírás:** *Közepes doboz*
        - **Maximális nettó súly:** *50*
        - **Térfogat:** *200*
        - **Hossz:** *2*
        - **Szélesség:** *10*
        - **Magasság:** *10*

    - 3. tárolótípus:

        - **Tárolótípus kódja:** *Kisméretű doboz*
        - **Leírás:** *Kis doboz*
        - **Maximális nettó súly:** *20*
        - **Térfogat:** *100*
        - **Hossz:** *1*
        - **Szélesség:** *10*
        - **Magasság:** *10*

### <a name="inspect-or-create-container-groups"></a>Tárolócsoportok vizsgálata vagy létrehozása

A tárolócsoportok vizsgálatához vagy szükség esetén új tárolócsoportok létrehozásához hajtsa végre ezeket a lépéseket.

1. Ugorjon a **Raktárkezelés** \> **Beállítás** \> **Tárolók** \> **Tárolócsoportok** pontra.
1. Győződjön meg róla, hogy a következő tárolócsoportok mindegyike elérhető a bemutató adataiban. Ha nem érhető el, a létrehozáshoz válassza az **Új** gombot.

    - **Tárolócsoport azonosítója:** *Dobozok*
    - **Leírás:** *Dobozméretek*

1. A *Dobozok* tárolócsoport **Részletek** gyorscsoportján ellenőrizze, hogy léteznek-e a következő sorok. Ha nem, az **Új** gombbal hozzáadhatja azokat.

    - 1. sor:

        - **Sorszám:** *1*
        - **Tároló típusa:** *Nagyméretű doboz*
        - **Tároló százalékos kihasználtsága:** *100*

    - 2. sor:

        - **Sorszám:** *2*
        - **Tárolótípus:** *Közepes méretű doboz*
        - **Tároló százalékos kihasználtsága:** *100*

    - 3. sor:

        - **Sorszám:** *3*
        - **Tárolótípus:** *Kisméretű doboz*
        - **Tároló százalékos kihasználtsága:** *100*

### <a name="create-a-new-container-build-template"></a>Új tárolóépítési sablon létrehozása

Új tárolóépítési sablon létrehozásához kövesse az alábbi lépéseket.

1. Ugorjon a **Raktárkezelés** \> **Beállítás** \> **Tárolók** \> **Tárolóépítési sablon** pontra.
1. Válassza az **Új** lehetőséget, ha olyan tárolóépítési sablont hoz létre, amely a következő beállításokat tartalmazza:

    - **Sorszám:** *1*
    - **Tárolósablon azonosítója:** *Doboz*
    - **Tárolócsoport azonosítója:** *Dobozok*
    - **Alap lekérdezéstípusok:** *Értékesítési felosztási sor*
    - **Hullámlépés kódja:** *234*
    - **Kiválsztás engedélyezése:** *Igen*
    - **Tároló csomagolási stratégiája:** *Csomagolás csak az aktuális tárolóba*
    - **Csomagolás az irányelvegység szerint:** *Nem*

1. Amíg az új sablon sora még ki van választva, válassza ki a **Lekérdezés szerkesztése** lehetőséget a Műveleti panelen.
1. Megjelenik egy szabványos lekérdezésszerkesztő párbeszédpanelje. A **Rendezés** lapon válassza a **Hozzáadást** egy sort hozzáadásához a rácshoz a következő beállításokkal:

    - **Tábla:** *Ideiglenes munkatranzakciók*
    - **Származtatott tábla:** *Ideiglenes munkatranzakciók*
    - **Mező:** *Rendelés száma*
    - **Keresés iránya:** *Növekvő*

    > [!IMPORTANT]
    > A többi nyitott tároló túlárazásának elkerülése érdekében, illetve a folyamat felgyorsítása érdekében egyszerre egy tárolót ellenőriz, a rendelésszámok szerint történő rendezésen kívül a *Csomagolás csak az aktuális tárolóba* stratégia használható. Ez a kombináció munkaszünetként fog működni egy munkasablonon.

1. Az lekérdezésszerkesztő párbeszédablak bezárásához kattintson az **OK** lehetőségre.
1. Amíg az új sablon sora még ki van választva, válassza ki a **Tárolóvegyesítési megszorítások** lehetőséget a Műveleti panelen.

    Ezzel olyan megszorítást fog hozzáadni, amely egyetlen rendelés cikkét egyetlen tárolóba helyezi. A más rendelésből származó cikkek külön tárolóba lesznek ásva.

1. Válassza az **Új** lehetőséget, ha olyan vegyítési megszorításokat hoz létre, amely a következő beállításokat tartalmazza:

    - **Tábla:** *Értékesítési rendelések*
    - **Mező kiválasztása:** *SalesId* (A mező *Értékesítési rendelésként* jelenik meg a rácsban.)

1. A megszorítás hozzáadásához kattintson az **OK** lehetőségre.
1. Zárja be a lapot.

### <a name="set-up-a-wave-template-for-containerization"></a>Hullámsablon beálllítása a tárolóra bontáshoz

Hullámsablon beállításához kövesse az alábbi lépéseket.

1. Ugorjon a **Raktárkezelés \> Beállítás \> Hullámok \> Hullámsablonok** pontra.
1. A listatáblában állítsa a **Hullámsablon típusa** mezőt a *Szállítás* értékre.
1. Válassz a **63 tárolóra bontás** sablont a listában.
1. A műveleti ablaktáblán válassza a **Szerkesztés** lehetőséget.
1. A **Módok** gyorslapon, a **Kiválasztott módok** oszlopban keresse meg a következő sort:

    - **Metódus neve:** *tárolóra bontás*
    - **Név:** *Tárolóra bontás*

1. Ehhez a sorhoz állítsa a **Hullámlépés kód** mezőt a *234* lehetőségre.

### <a name="set-up-a-work-template"></a>Munkasablon beállítása

Munkasablon beállításához kövesse az alábbi lépéseket.

1. Lépjen a **Raktárkezelés \> Beállítás \> Munka \> Munkasablonok** elemre.
1. A **Munkarendelés típusa** mező beállítása a *Beszerzési rendelések* értékre.
1. Az **Áttekintés** rácsban keresse meg és válassza ki azt munkasablont, amelyet konténerenként egyes megrendelések csomagolásához kell használni. Ehhez a helyzethez válassza az **63 Kitárolás tárolóhoz** sablont.
1. A műveleti ablaktáblán válassza a **Lekérdezés szerkesztése** lehetőséget.
1. Megjelenik egy szabványos lekérdezésszerkesztő párbeszédpanelje. A **Rendezés** lapon adja meg a következő sorok beállításait:

    - 1. sor:

        - **Tábla:** *Ideiglenes munkatranzakciók*
        - **Származtatott tábla:** *Ideiglenes munkatranzakciók*
        - **Mező:** *Szállítmány azonosítója*
        - **Keresés iránya:** *Növekvő*

    - 2. sor:

        - **Tábla:** *Ideiglenes munkatranzakciók*
        - **Származtatott tábla:** *Ideiglenes munkatranzakciók*
        - **Mező:** *Rendelés száma*
        - **Keresés iránya:** *Növekvő*

    - 3. sor:

        - **Tábla:** *Ideiglenes munkatranzakciók*
        - **Származtatott tábla:** *Ideiglenes munkatranzakciók*
        - **Mező:** *Tároló azonosítója*
        - **Keresés iránya:** *Növekvő*

1. Az lekérdezésszerkesztő párbeszédablak bezárásához kattintson az **OK** lehetőségre.
1. A következő üzenet jelenik meg: „A csoportosítás alaphelyzetbe kerül, folytatja?” A folytatáshoz kattintson az **Igen** gombra.
1. Amíg a **63 Kitárolás tárolóhoz** sablon ki van választva, jelölje ki a **Munkafejléc-szüneteket** a Munkaablakban.

    Ezzel a beállítások alkalmazásával megszakítja a munkát, hogy a rendelés minden tárolója egy munkarendeléshez kapcsolódjön.

1. Jelölje be a **Csoportosítás a mező szerint** jelölőnégyzetet a **Munkafejléc-törések** lap (**Szállítmányazonosító**, **Rendelésszám** és **Tárolóazonosító**) minden sorában.
1. Zárja be a lapot.

### <a name="set-up-shipment-consolidation-policies"></a>Szállítmánykonszolidációs irányelvek beállítása

A szállítási konszolidáció irányelvének beállításához kövesse ezeket a lépéseket.

1. Nyissa meg a **Raktárkezelés \> Beállítás \> Kiadás raktárnak \> Szállítmánykonszolidációs irányelvek** pontot.
1. A listatáblában állítsa át az **Irányelv típusa** mezőt *Értékesítési rendelések* értékre.
1. Válassza ki az **Alapértelmezett** irányelveket a listából.
1. A műveleti ablaktáblán válassza a **Szerkesztés** lehetőséget.
1. A **Konszolidációs mezők** gyorslapon a **Kiválasztott mezők** listában válassza ki a sort, ahol a **Mező neve** mező beállítása *Rendelési szám*.
1. Válassza az **Eltávolítás** gombot a ![a balra nyíllal.](media/backward-button.png) hogy a mezőt a **Hátralévő mezők** listába helyezze át.
1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.

### <a name="set-up-physical-dimensions-for-the-product"></a>Állítsa be a termék fizikai méreteit

Az ilyen helyzetekben használt termékek fizikai dimenzióinak beállítását a következő lépések szerint hajtsa végre.

1. Kattintson a **Termékinformációk kezelése \> Termékek \> Kiadott termékek** lehetőségre.
1. Annak a terméknek a kiválasztása, ahol a **Cikkszám** mező beállítása *A0001*.
1. A Műveleti panelen, a **Készletkezelés lapon** a **Raktár** csoportban válassza ki a **Tényleges dimenziók** lehetőséget.
1. A **Fizikai dimenziók** lapon a következő sort kell látnia a rácsban:

    - **Egység:** *db*
    - **Bruttó tömeg:** *3,00*
    - **Szélesség:** *2,00*
    - **Mélység:** *2,00*
    - **Magasság:** *4,00*
    - **Térfogat:** *16,00*

1. Zárja be a lapot.
1. Annak a terméknek a kiválasztása, ahol a **Cikkszám** mező beállítása *A0002*.
1. A Műveleti panelen, a **Készletkezelés lapon** a **Raktár** csoportban válassza ki a **Tényleges dimenziók** lehetőséget.
1. A **Fizikai dimenziók** lapon a következő sort kell látnia a rácsban:

    - **Egység:** *db*
    - **Bruttó tömeg:** *4,00*
    - **Szélesség:** *3,00*
    - **Mélység:** *1,00*
    - **Magasság:** *3,00*
    - **Térfogat:** *9,00*

### <a name="create-sales-order-1"></a>1. értékesítési rendelés létrehozása

Értékesítési rendelés létrehozásához kövesse az alábbi lépéseket.

1. Ugorjon az **Értékesítés és marketing \> Értékesítési rendelések \> Minden értékesítési rendelés** pontra.
1. A Műveleti ablaktáblán kattintson az **Új** elemre.
1. Megjelenik egy párbeszédpanel az új értékesítési rendelések létrehozásához. Adja meg az alábbi értékeket:

    - **Vevőkód** *US-001*
    - **Raktár:** *63*

1. Válassza az **OK** gombot a beszerzési rendelés létrehozásához és a párbeszédpanel bezárásához.
1. A program megnyitja az új értékesítési rendelést. Az **Értékesítési rendelés sorai** gyorslapon adja hozzá a következő értékesítési sorokat:

    - 1. sor:

        - **Cikkszám:** *A0001*
        - **Mennyiség:** *2*

    - 2. sor:

        - **Cikkszám:** *A0002*
        - **Mennyiség:** *2*

1. Válassza ki az első sort, majd válassza a **Készlet \> Foglalás** lehetőséget.
1. A **Foglalás** lapon válassza ki az **Adag foglalása** elemet. Ezután zárja be az oldalt.
1. Ismételje meg az előző két lépést a második sorra.
1. Zárja be a lapot.

### <a name="create-sales-order-2"></a>2. értékesítési rendelés létrehozása

íegy második értékesítési rendelés létrehozásához kövesse az alábbi lépéseket.

1. Ugorjon az **Értékesítés és marketing \> Értékesítési rendelések \> Minden értékesítési rendelés** pontra.
1. A Műveleti ablaktáblán kattintson az **Új** elemre.
1. Megjelenik egy párbeszédpanel az új értékesítési rendelések létrehozásához. Adja meg az alábbi értékeket:

    - **Vevőkód** *US-001*
    - **Raktár:** *63*

1. Válassza az **OK** gombot a beszerzési rendelés létrehozásához és a párbeszédpanel bezárásához.
1. A program megnyitja az új értékesítési rendelést. Az **Értékesítési rendelés sorai** gyorslapon adja hozzá a következő értékesítési sorokat:

    - 1. sor:

        - **Cikkszám:** *A0001*
        - **Mennyiség:** *4*

    - 2. sor:

        - **Cikkszám:** *A0002*
        - **Mennyiség:** *4*

1. Válassza ki az első sort, majd válassza a **Készlet \> Foglalás** lehetőséget.
1. A **Foglalás** lapon válassza ki az **Adag foglalása** elemet. Ezután zárja be az oldalt.
1. Ismételje meg az előző két lépést a második sorra.
1. Zárja be a lapot.

### <a name="create-the-load"></a>Terhelés létrehozása

A következő lépések végrehajtásával terhelést hozhat létre az egyes rendeléskészletekhez, amelyeket ehhez az esethez készített, majd kiadhatja azt a raktárnak.

1. Ugorjon a **Raktárkezelés \> Rakományok \> Rakománytervező munkaterület** elemre.
1. Az **Értékesítési sorok** lapon megkeresheti és kiválaszthatja az adott esethez létrehozott rendeléskészletek értékesítési rendelési sorait.
1. A műveleti ablaktáblán a **Kínálat és kereslet** lapon, a **Hozzáadás** csoportban válassza az **Új rakományba** elemet. A kiválasztott rendeléssorok új rakományhoz adódnak hozzá.
1. A **Rakománysablon hozzárendelése** párbeszédablakban a **Rakománysablon azonosítója** mezőben válassza ki a rakománysablont, pl. a *40' Tároló* elemet.
1. Az **OK** gombbal zárja be a párbeszédpanelt.
1. A **Rakomány** szakaszban keresse meg és válassza ki az imént létrehozott rakományt.
1. Válassza a **Kiadás \> Raktárba való kiadás** lehetőséget.
1. A kiválasztott rakomány raktárba történő kiadásához nyomja meg a **Kiadás a raktárba** párbeszédablakon az **OK** gombot.

### <a name="verify-the-shipments-and-containers"></a>A szállítmányok és a tárolók ellenőrzése

Az alábbi eljárásokkal ellenőrizhetők a létrehozott szállítmányok. Használatával áttekinthető az esethez létrehozott rendelés, így biztosan meg tudja szerezni a várt eredményeket.

1. Lépjen a **Raktárkezelés \> Szállítmányok \> Minden szállítmány** elemhez.
1. Az előbb kiadott rakományhoz létrehozott szállítmány megkeresése és kiválasztása.
1. A Művelet ablakban a **Szállítás** lapon, válassza a **Tárolók megtekintése** elemet.
1. Győződjön meg arról, hogy az értékesítési rendelések cikkeit két különböző tárolóba rakták.

## <a name="additional-resources"></a>További erőforrások

- [Tárolóra bontás](wave-containerization.md)
