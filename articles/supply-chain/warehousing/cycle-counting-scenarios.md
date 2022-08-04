---
title: Ciklikus leltározás példa esetek
description: Ez a témakör a Microsoft ciklikus leltározási funkcióit tárja fel Dynamics 365 Supply Chain Management.
author: GalynaFedorova
ms.date: 06/08/2021
ms.topic: article
ms.search.form: WHSCycleCountPlan, WHSCycleCountPlanListPage, WHSCycleCountThreshold, WHSWorkTableListPage, SalesShipmentDeviation, WHSRFMenuItemCycleCount, WHSWorkLineCycleCount
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2021-06-08
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 4f6f3f2db6efcc4d4d6ae3d278751a230fca9a64
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/29/2022
ms.locfileid: "9068596"
---
# <a name="cycle-counting-example-scenarios"></a>Ciklikus leltározás példa esetek

[!include [banner](../includes/banner.md)]

Ez a témakör a Microsoft ciklikus leltározási funkcióit tárja fel Dynamics 365 Supply Chain Management. Először a meglévő Supply Chain Management környezet követelményeit írja le. Ezután bemutatja a ciklikus leltározás konfigurálást, és leírja az összes ciklikus leltározási fokozatot. Ha befejezte, jól kell ismernie a ciklikus leltározást, például irányított ciklikus leltározást, számlálást, azonnali ciklikus leltározást, ciklikus leltározási küszöbértékeket és ciklikus leltározási terveket.

## <a name="prerequisites"></a>Előfeltételek

### <a name="make-demo-data-available"></a>A bemutató adatok elérhetővé tétele

A cikk minden egyes esete az Ellátásilánc-kezelés szabványos bemutató adataiban található értékekre és rekordokra hivatkozik. Ha azt szeretné, hogy az itt megadott értékeket használja a forgatókönyvek végrehajtásához, akkor győződjön meg róla, hogy olyan környezetben dolgozik, ahol a bemutatóadatokat telepítették, és a jogi személy (vállalat) beállítása legyen **USMF**.

### <a name="turn-on-support-for-the-warehouse-management-mobile-app"></a>A Warehouse Management mobilalkalmazás támogatásának bekapcsolása

A Raktárkezelés mobilalkalmazás *használatához be kell kapcsolva lennie a rendszerben az új raktári alkalmazás felhasználói beállításainak,* ikonjainak és lépéscímének. A 10.0.25-ös ellátásilánc-kezelésben ez a funkció kötelező, és nem lehet kikapcsolni. Ha 10,0,25-ösnél régebbi verziót futtat, *akkor a rendszergazdák a Funkciókezelés munkaterület új raktári alkalmazás funkciójának Felhasználói beállításai,*[ikonjai](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) és lépéscímei alapján kapcsolhatják be és kapcsolhat ki a funkciót.

### <a name="prepare-demo-data-for-the-scenarios"></a><a name= "prepare-demo-data"></a>Bemutatóadatok előkészítése az esetekhez

A következő lépések szerint győződjön meg arról, hogy az esetekhez szükséges bemutatóadatok elérhetők a rendszer USMF vállalatában. Hozza létre a hiányzó rekordokat és értékeket.

1. Ugrás a **Raktárkezelés \> Beállítás \> Dolgozó** elemre.
1. Az ablakban válassza ki **Julia Funderburkot**.
1. A **Felhasználók** gyorsététi csoportban válassza ki azt a sort, amely a következő értékeket tartalmazza. Ha egy meglévő sor sem rendelkezik ezekkel az értékekkel, hozza létre.

    - **Felhasználóazonosító:** *61*
    - **Felhasználónév:** *WH61*
    - **Alapértelmezett raktár:** *61*
    - **Menü neve:** *Fő*

1. A **Munka** gyorsábra a *61*-es felhasználóhoz a következő értékeket állítsa be, ha még nincsenek beállítva:

    - **Van ciklikusleltár-felügyelő:** *Nem*
    - **Maximális százalékarány korlátja:** *0*
    - **Maximális mennyiségi korlát:** *0*
    - **Maximális értékhatár:** *0*

1. Ugorjon a **Raktárkezelés \> Beállítás \> Munka \> Munkagyűjtők** pontra.
1. A munkagyűjtőket arra használhatja, hogy elkülönítse a raktári munkákat a munka típusa alapján (ebben az esetben a ciklikus leltározási munka). Győződjön meg róla, hogy létezik olyan rekord, amely a következő beállításokkal rendelkezik:

    - **Munkagyűjtő azonosítója:** *CycleCount*
    - **Leírás:** *Ciklikus léltár*

1. Lépjen a **Raktárkezelés \> Beállítás \> Mobileszköz \> Mobileszköz-menüelemek** részre.
1. A lista ablaktáblán válassza ki a *Ciklikus leltár* nevű rekordot. Ha nincs ilyen nevű rekord, hozza létre. Erősítse meg vagy állítsa be a következő értékeket a rekordhoz:

    - **Menüelem neve:** *Ciklikus leltár*
    - **Cím:** *Ciklikus leltár irányított*
    - **Mód:** *Munka*
    - **Meglévő munka használata:** *Igen*
    - **Irányítja:** *Rendszer által irányított* (ez az érték azt jelzi, hogy a Supply Chain Management egy ciklikus leltározási munkaazonosítót rendel a dolgozóhoz.)
    - **Készletállapot megjelenítése:** *Igen*

1. A Művelet ablaktáblán válassza ki a **Ciklikus leltározása** lehetőségre.
1. A **Mobileszköz ciklikus leltározása** párbeszédpanelen erősítse meg vagy állítsa be a következő értékeket:

    - **Cikkszám megjelenítése:** *Igen*
    - **Azonosítótábla kijelzése:** *Igen*
    - **Kísérletek száma:** *1*

1. Az **OK** gombbal zárja be a párbeszédpanelt.
1. A lista ablaktáblán válassza ki a *Ciklikus leltár nélküli* nevű rekordot. Ha nincs ilyen nevű rekord, hozza létre. Erősítse meg vagy állítsa be a következő értékeket a rekordhoz:

    - **Menüelem neve:** *Ciklikus leltár nélküli*
    - **Cím:** *Ciklikus leltár nélküli*
    - **Mód:** *Munka*
    - **Meglévő munka használata:** *Igen*
    - **Irányítja:** *Ciklikus leltározás csoportosítása* (A dolgozó csoportosíthatja az adott helyhez, zónához vagy munkagyűjtőhöz rendelt ciklikus leltári munkák azonosítóit.)

1. A Művelet ablaktáblán válassza ki a **Ciklikus leltározása** lehetőségre.
1. A **Mobileszköz ciklikus leltározása** párbeszédpanelen erősítse meg vagy állítsa be a következő értékeket:

    - **Cikkszám megjelenítése:** *Nem*
    - **Azonosítótábla kijelzése:** *Nem*
    - **Kísérletek száma:** *0*

1. Az **OK** gombbal zárja be a párbeszédpanelt.
1. A lista ablaktáblán válassza ki az *Eseti leltár* nevű rekordot. Ha nincs ilyen nevű rekord, hozza létre. Erősítse meg vagy állítsa be a következő értékeket a rekordhoz:

    - **Menüpont neve:** *Eseti leltár*
    - **Cím:** *Eseti leltár*
    - **Mód:** *Munka*
    - **Meglévő munka használata:** *Nem*
    - **Munkalétrehozási folyamat** *Eseti ciklikus leltár* (A dolgozó ciklikus leltározási munka létrehozása nélkül is bármikor megszámolhatja a raktárhelyen lévő cikkeket. Az eseti ciklikus leltározás végrehajtásához egy helyen, a dolgozó megadja a hely azonosítóját.)

1. Lépjen a **Raktárkezelés \> Beállítás \> Mobileszköz \> Mobileszköz menü** elemre.
1. A lista ablaktáblán válassza ki a *Készlet* nevű rekordot. Ha nincs ilyen nevű rekord, hozza létre. Győződjön meg arról, hogy a következő ciklikus leltár menüpontok jelennek meg a **Menüstruktúra** oszlopában:

    - Ciklikus leltározás
    - Cím: Ciklikus leltár nélküli
    - Eseti leltározás

1. Lépjen a **Raktárkezelés \> Beállítás \> Raktárkezelési paraméterek** részre.
1. A **Ciklikus leltározás** lapon állítsa be a következő értékeket:

    - **Ciklikus leltározás alapértelmezett helyesbítési típusa:** *Ciklikus leltározás* (ez a mező meghatározza a ciklikus leltározáskor feladott naplótípust.)
    - **Ciklikus leltározás alapértelmezett munkaosztály-azonosítója:** *CCount* (Ez a mező meghatározza a ciklikus leltározáshoz használt munkaosztályt.)
    - **Ciklikus leltározási munka alapértelmezett prioritása:** *50* (Ez a mező beállítja a ciklikus leltározási munka prioritását a raktár más típusú munkáihoz viszonyítva. Ha a megadottnál kisebb számot ad meg a többi típusú munkához megadott számoknál, növeli a ciklikus leltározási feladat prioritását.)

1. Ugorjon a **Warehouse Management \> Beállítás \> Készlet \> Kiigazítás-típusok** pontra.
1. A **Kiigazítási típusok** lap lehetővé teszi, hogy kódokat hozzon létre az esetleges ki- és bej helyesbítésekhez. Erősítse meg, hogy létezik olyan rekord, amely a következő beállításokkal rendelkezik:

    - **Készletkorrekció típusa:** *Ciklikus leltár*
    - **Leírás:** *Ciklikus léltár*
    - **Név:** *ICnt*

1. Ugorjon a **Warehouse Management \> Beállítás \> Raktár beállítás \> Raktárak** pontra.
1. A listaablakban válassza ki a *61-es raktárat*. Ha nincs ilyen nevű rekord, hozza létre.
1. A **Raktár** gyorslapon állítsa be a következő értékeket:

    - **Használja a raktárkezelési folyamatot:** *Igen* (Ez az érték engedélyezi a raktárat a raktárkezelési folyamatokhoz (WMS).)
    - **Az tábla ciklikus leltározás közbeni áthelyezésének engedélyezése:** *Igen* (Ez az érték lehetővé teszi a dolgozóknak, hogy a ciklikus leltár során áthelyezik az licenctáblákat.)

## <a name="scenario-1-guided-cycle-counting"></a>1. eset: Irányított ciklikus leltározás

Mielőtt irányított ciklikus leltározás történhet, létre kell hozni egy kis munkát. Ez a munka végigvezeti a hozzárendelt személyt a raktáron, a helytől a helyig, és végigvezeti a munkában beállított számláláson.

### <a name="create-cycle-counting-work-for-scenario-1"></a>Ciklikus leltározási munka létrehozása az 1. esethez

A következő lépések szerint hozhat létre ciklikus leltározási munkát a cikk helyére a *01A02R2S2B* (BULK-06) a *61.* raktárban.

1. Ugorjon a **Warehouse Management \> Ciklikus leltározás \> Ciklikus leltározási küszöbértékei menüpontra**.
1. A **Ciklikusszámlálási munka létrehozása hely szerint** párbeszédpanelen állítsa a **Munkakészlet azonosítója** mezőt *CycleCount beállításra*.
1. **A szerepeltetni kívánt rekordok** gyorslapján válassza a **szűrő** elemet.
1. A Lekérdezésszerkesztő párbeszédpanel **Tartomány** lapján hajtsa végre a következő lépéseket:

    - Ahhoz a sorhoz, amelyben a **Mező** mező *Raktárra* van állítva, állítsa a **Feltétel** mezőt *61*-re.
    - Ahhoz a sorhoz, amelyben a **Mező** mező *Helyre* van állítva, állítsa a **Feltétel** mezőt *01A02R2S2B*-re.

1. Az lekérdezésszerkesztő párbeszédablak bezárásához kattintson az **OK** lehetőségre.
1. A **Ciklikusszámlálási munka létrehozása hely szerint** párbeszédpanel bezárásához kattintson az **OK** gombra.

    Amikor befejeződött a munka-létrehozási folyamat, egy üzenet jelenik meg a Műveletközpontban.

1. Ugorjon a **Raktárkezelés \> Munka \> Munka részletei** pontra.
1. Az újonnan létrehozott munka megkereshető a **Munkakészlet azonosítója** oszlop szűrő beállításával, és megkereshetők a *CycleCount értékű* rekordok.

### <a name="do-cycle-counting-work-for-scenario-1"></a>Ciklikus leltározási munka működése az 1. esethez

Miután létrehozott egy ciklikus leltározási munkát, a raktárhelyen található cikkek számlálásával végezheti el a ciklikus leltározási munkát, majd mobileszközén rögzítheti az eredményt a Supply Chain Management rendszerbe. A következő lépések szerint hajtsa végre a ciklikus leltározási munkát a Warehouse Management mobilalkalmazásban.

1. Jelentkezzen be a Raktárkezelés mobilalkalmazásba [az](#prepare-demo-data) a munkafelhasználó, aki a cikk korábbi, Az esetek adatainak előkészítése szakaszban be van állítva. Ebben a példában a *felhasználó Neve Mindig Funderburk* *, és a 61-es raktárhoz van beállítva*. (Az USMF bemutatóadatok segítségével úgy jelentkezhet be, mint ez a munkafelhasználó, hogy a *61*-es felhasználóazonosítót, és *1*-et a jelszóként ad meg.)
1. Válassza a főmenü **Készlet** elemét.
1. Válassza a **Készlet** menü **Ciklikus leltár irányított** parancsát.
1. Válassza ki a **Mennyiség** mezőt, írja be a *9* értéket a számbillentyűzet használatával, majd jelölje be az **OK** (jelölőnégyzetet).
1. A rendszer arra számított, hogy ennek a cikknek, helynek és táblának a 10 darabját adja meg. Ezért újraszámlálást kéri a bizottság. Válassza ki a **Mennyiség** mezőt, írja be a *9* értéket ismét a számbillentyűzet használatával, majd jelölje be az **OK** (jelölőnégyzetet). A második kísérletre a rendszer elfogadja a megszámlálást.

    > [!NOTE]
    > Amikor a rendszer eltérést észlelt a várt tényleges mennyiség és a megadott mennyiség között, a rendszer második alkalommal is kérte, hogy számolja meg a számot, mert a **Ciklikus leltár irányított** által irányított mobileszköz menüpontnál a **Próbálkozások száma** mező *1*-re van állítva. A rendszer egy bizonyos cikkszámhoz és egy egyedi táblaszámhoz irányította, mert mind a **Cikkszám megjelenítése**, mind az **Tábla megjelenítése** beállítás *Igen* beállítás van megállítva a mobileszköz menüelemére.

1. Válassza az **OK** gombot (a pipa szimbólum gombja).

### <a name="review-the-cycle-counting-differences-for-scenario-1"></a>Tekintse át az 1. eset ciklikus leltározási eltéréseit

Kövesse az alábbi lépéseket a ciklikus leltározási különbségek áttekintéshez.

1. Visszatérés a Supply Chain Management alkalmazásba.
1. Ugorjon a **Raktárkezelés \> Munka \> Munka részletei** pontra.
1. Keresse meg és válassza ki a korábban megnézett ciklikus leltározási munkát. (Szűrő beállítása például a következőre: **Munkakészlet-azonosító** oszlop a *CycleCount* értékű rekordok megkeres érdekében.) Figyelje meg, hogy a **munka állapota** mező most *Ellenőrzésre vár* értékű.

    > [!NOTE]
    > Ahhoz a munkafelhasználói számlához, amely leltározási munkához használatos, a **Ciklikus leltár felügyelője** beállítás *Nem* értékre van állítva, és a **Maximális százalék**, a **Maximális mennyiségi korlát** és a **Maximális értékhatár mező értéke** *0* (nulla). Ebből következően a felhasználói jelentéseket manuálisan kell jóváhagyni, és a kapcsolódó munka **Munkaállapot** mezőjében *Ellenőrzésre vár* a rendszer. Ha a leszámolt érték az eltérési korlátokon belül van (a **Munkafelhasználók** lap **Maximális százalékkorlát** vagy **Maximális mennyiségi korlátozás** mezője szerint), vagy ha a **Ciklikus számlálás** felügyelője beállítás *Igen* értékre volt állítva a felhasználónál, a munka automatikusan le lett volna zárva.

1. A Művelet panelen a **Munka** lapon válassza a **Ciklikus leltározás** menüpontot.
1. A Művelet ablaktáblán válassza ki a **Számlálás elfogadása** lehetőségre.

    A különbözet feladása a szokásos leltárnapló használatával, egy új munkarendelés létrehozása után jön létre.

1. A **Ciklikus leltározási tranzakciók** lapon, a műveletpanelen válassza ki a **Származtatott munkát** a jóváhagyott eltéréshez létrehozott munka megkeres érdekében.

## <a name="scenario-2-blind-cycle-counting"></a>2. eset: Ciklikus leltározás nélküli

Ehhez az esethez az szükséges, hogy az 1. eset már be legyen fejezve a rendszerben.

### <a name="create-cycle-counting-work-for-scenario-2"></a>Ciklikus leltározási munka létrehozása az 2. esethez

Mielőtt ciklikus leltározás nélküli esemény történhet, létre kell hozni egy kis munkát. A következő lépések szerint hozhat létre ciklikus leltározási munkát a cikk helyére a *01A02R2S2B* (BULK-06) a *61.* raktárban.

1. Ugorjon a **Warehouse Management \> Ciklikus leltározás \> Ciklikus leltározási munka cikkenként** menüpontra.
1. A **Ciklikusszámlálási munka létrehozása cikk szerint** párbeszédpanelen állítsa a **Munkakészlet azonosítója** mezőt *CycleCount* beállításra.
1. **A szerepeltetni kívánt rekordok** gyorslapján válassza a **szűrő** elemet.
1. A lekérdezésszerkesztő párbeszédpanelen, a **Tartomány** lapon adjon hozzá három sort a következő beállításokkal.

    - 1. sor:

        - **Tábla:** *Cikkek*
        - **Mező:** *Cikkszám*
        - **Feltételek:** *L0101*

    - 2. sor:

        - **Tábla:** *Készletdimenziók lap*
        - **Mező:** *Raktár*
        - **Feltételek:** *61*

    - 3. sor:

        - **Tábla:** *Készletdimenziók lap*
        - **Mező:** *Hely*
        - **Feltételek:** *01A02R2S2B*

1. Az lekérdezésszerkesztő párbeszédablak bezárásához kattintson az **OK** lehetőségre.
1. A **Ciklikusszámlálási munka létrehozása cikk szerint** párbeszédpanel bezárásához kattintson az **OK** gombra.

    Ha befejeződött a munka-létrehozási folyamat, tájékoztató üzenet jelenik meg.

### <a name="do-cycle-counting-work-for-scenario-2"></a>Ciklikus leltározási munka működése az 2. esethez

A ciklikus leltározás munka létrehozása után a következő lépések szerint hajtsa végre a ciklikus leltározási munkát a Warehouse Management mobilalkalmazásban.

1. Jelentkezzen be a Raktárkezelés mobilalkalmazásba [az](#prepare-demo-data) a munkafelhasználó, aki a cikk korábbi, Az esetek adatainak előkészítése szakaszban be van állítva. Ebben a példában a *felhasználó Neve Mindig Funderburk* *, és a 61-es raktárhoz van beállítva*. (Az USMF bemutatóadatok segítségével úgy jelentkezhet be, mint ez a munkafelhasználó, hogy a *61*-es felhasználóazonosítót, és *1*-et a jelszóként ad meg.)
1. Válassza a főmenü **Készlet** elemét.
1. Válassza a **Készlet** menü **Ciklikus leltár nélküli** parancsát.
1. Válassza ki a **Zónaazonosító** mezőt, adja meg a *BULK06* mezőt, majd válassza az **OK** gombra (a pipagombra).
1. Válassza ki a **Cikk** mezőt, adja meg a *L0101* mezőt, majd válassza az **OK** gombra (a pipagombra).
1. Válassza ki a **Licenc azonosító** mezőt, adja meg az *LP\_BULK\_06\_01* mezőt, majd válassza az **OK** gombra (a pipagombra).
1. Válassza ki a **Mennyiség** mezőt, adja meg a *10* mezőt, majd válassza az **OK** gombra (a pipagombra).

    > [!NOTE]
    > Még ha a rendszer eltérést is észlelt a várt tényleges mennyiség és a beolvasott mennyiség között, a rendszer második alkalommal nem kérte, hogy számolja meg a számot, mert a **Ciklikus leltár nélküli** által irányított mobileszköz menüpontnál a **Próbálkozások száma** mező *0*-re (nullára) van állítva. A rendszer kérte a cikkszám és a táblaszámhoz beolvasását, mert mind a **Cikkszám megjelenítése**, mind a **Tábla megjelenítése** beállítás *nem* beállítás van megállítva a mobileszköz menüelemére.

1. Válassza az **OK** gombot (a pipa szimbólum gombja).

### <a name="review-the-cycle-counting-differences-for-scenario-2"></a>Tekintse át az 2. eset ciklikus leltározási eltéréseit

Kövesse az alábbi lépéseket a ciklikus leltározási különbségek áttekintéshez.

1. Visszatérés a Supply Chain Management alkalmazásba.
1. Menjen a **Warehouse Management \> Általános \> Munka \> Ciklikus leltározási munka ellenőrzése függőben** lehetőségre.
1. A Művelet panelen a **Munka** lapon válassza a **Ciklikus leltározás** menüpontot.
1. A Művelet ablaktáblán válassza ki a **Számlálás elutasítása** lehetőségre.

    Mivel a leltározási eltérést elutasították, a munka le van zárva.

## <a name="scenario-3-spot-cycle-counting"></a>3. eset: Eseti ciklikus leltározás

A tényleges készlet azt állítja, hogy az *L0101* cikkből tényleges készlet van a *01A02R2S2B* helyen. A raktári dolgozó a *01A02R2S1B* helyen van. Bár ennek a helynek üresnek kell lennie, megtelt. Ezért a raktári dolgozó azonnal leszámolja ezt a helyet.

### <a name="do-cycle-counting-work-for-scenario-3"></a>Ciklikus leltározási munka működése az 3. esethez

A következő lépések szerint hajtsa végre a ciklikus leltározási munkát a Warehouse Management mobilalkalmazásban.

1. Jelentkezzen be a Raktárkezelés mobilalkalmazásba [az](#prepare-demo-data) a munkafelhasználó, aki a cikk korábbi, Az esetek adatainak előkészítése szakaszban be van állítva. Ebben a példában a *felhasználó Neve Mindig Funderburk* *, és a 61-es raktárhoz van beállítva*. (Az USMF bemutatóadatok segítségével úgy jelentkezhet be, mint ez a munkafelhasználó, hogy a *61*-es felhasználóazonosítót, és *1*-et a jelszóként ad meg.)
1. Válassza a főmenü **Készlet** elemét.
1. Válassza a **Készlet** menü **Eseti leltározás** parancsát.
1. Válassza ki a **Hely** mezőt, adja meg a *01A02R2S1B* mezőt, majd válassza az **OK** gombra (a pipagombra).

    A rendszer azt észlelte, hogy üres a hely a Supply Chain Management szolgáltatásban.

1. Válassza az **Lp vagy a Cikk hozzáadása** lehetőséget.
1. Válassza ki a **Cikk** mezőt, adja meg a *L0101* mezőt, majd válassza az **OK** gombra (a pipagombra).
1. Válassza ki a **Licenc azonosító** mezőt, adja meg az *LP\_BULK\_06\_01* mezőt, majd válassza az **OK** gombra (a pipagombra).
1. Válassza ki a **Mennyiség** mezőt, adja meg a *9* mezőt, majd válassza az **OK** gombra (a pipagombra).

    Mivel a rendszer azt észleli, hogy a megadott tábla már elérhető a Supply Chain Management szolgáltatás egy másik helyén, az adott tábla az aktuális helyre fog átkerülni. A rendszer ezért kéri a mozgás megerősítését.

1. Válassza az **OK** gombot (a pipa szimbólum gombja).

### <a name="review-the-cycle-counting-differences-for-scenario-3"></a>Tekintse át az 3. eset ciklikus leltározási eltéréseit

Kövesse az alábbi lépéseket a leltározási eredmények áttekintéshez.

1. Visszatérés a Supply Chain Management alkalmazásba.
1. Ugorjon a **Warehouse Management \> Általános \> Munka részletei** pontra.
1. Jelölje be a Rács tetején található **Lezártak megjelenítése** jelölőnégyzetet.
1. Állítsa a **Munkarendelés típusa** oszlop szűrőjét *Készletmozgásra*.

    A rendszer automatikusan készletmozgásként észlelte ezt a leltárt. Ez a mozgás engedélyezett, mert az **Engedélyezési tábla a ciklikus leltározás közben** beállítás *Igen* beállítású a *61*-es raktárokhoz a **Raktárak** lapon.

## <a name="scenario-4-define-cycle-count-thresholds"></a>4. eset: Ciklikusszámlálási küszöbértékek definiálása

A ciklikus leltározási munka egyik módja a küszöbértékek használata. A ciklikus leltározás küszöbértéke azt jelzi, hogy a készleten lévő cikkek mennyiség vagy százalék korlátot. Ciklikus leltározási munkát automatikusan létrejön, amikor eléri a küszöbértéket.

Például 60 cikk van egy olyan helyen, amelynek ciklikus leltározási küszöbértéke 40. Egy értékesítési rendelés tranzakciója közben 25 cikket kitárolnak a helyről, majd betárolják egy előkészítő helyre. Mivel a cikkek új száma 35, és ez kisebb a küszöbérték mennyiségénél, a helyen automatikusan létrejön a ciklikus leltározási munka.

Kövesse ezeket a lépéseket a ciklikus leltározási küszöbök beállításához.

1. Ugorjon a **Warehouse Management \> Beállítás \> Ciklikus leltározás \> Ciklikus leltározási küszöbértékei** menüpontra.
1. A műveleti ablaktáblán válassza az **Új** parancsot egy küszöb létrehozásához, és állítsa be a következő értékeket hozzá:

    - **Ciklikus leltározási küszöbérték azonosítója:** *L0101*
    - **Leírás:** *L0101 küszöbérték*
    - **Küszöbérték mennyisége:** *2*
    - **Egység:** *ea*
    - **Küszöbérték a kapacitás százalékában:** *0,00*
    - **Ciklikus leltározási küszöbérték típusa:** *Mennyiség*
    - **Ciklikus számlálás feldolgozása azonnal:** *Igen*
    - **Ciklikus leltárok közötti napok:** *1*
    - **Munkagyűjtő azonosítója:** *CycleCount*

1. A Művelet ablaktáblán kattintson a **Cikkek kiválasztása** elemre.
1. A lekérdezésszerkesztő párbeszédpanel **Tartomány** lapján keresse meg azt a sort, amelynél a **Mező** mező értéke *Cikk száma*. Ennek a sornak a **Feltételek** mezőjét állítsa *L0101* értékre.
1. Az lekérdezésszerkesztő párbeszédablak bezárásához kattintson az **OK** lehetőségre.

    Most meghatározta az *L0101* cikk ciklikusszámlálási küszöbértékét.

A ciklikus leltározás bármely helyen létrejön az *L0101* cikkhez, ha az aktuális mennyiség 2-t kisebb, és a hely utolsó ciklikus leltározásának dátuma nem ma van.

## <a name="scenario-5-define-cycle-count-plans"></a>5. eset: Ciklikus leltározási tervek definiálása

A ciklikus leltározási tervek automatizálják a ciklikus leltározási munka létrehozását. Minden ciklikus leltározási tervhez külön cikk- és helylekérdezések is beállíthatók. A kötegelt feladat futtatásakor ciklikus leltározási munkát hoz létre minden helyhez, amely megfelel a cikkre és a helyre vonatkozó feltételeknek (a tervhez megadott maximális számú leltárig). Ciklikus leltározási munka létrehozása esetén a leltári munkasor tartalmazza a leltár számolandó helyével kapcsolatos információt. A helyhez társított aktuális készlet nincs zárolva. Ebből következően foglalásra és kimenő feldolgozásra is elérhető, még akkor is, ha van nyitott leltározási munka.

Kövesse ezeket a lépéseket a ciklikus leltározási terv beállításához.

1. Ugorjon a **Warehouse Management \> Beállítás \> Ciklikus leltározás \> Ciklikus leltározási tervek** lehetőségre.
1. A Művelet panelen válassza az **Új** lehetőséget egy sor rácshoz való hozzáadásához, majd állítsa be hozzá a következő értékeket:

    - **Ciklikus leltározási terv azonosítója:** *BULK06*
    - **Leírás:** *A BULK06 hely leltározása*
    - **Munkagyűjtő azonosítója:** *CycleCount*
    - **Ciklikus leltárok maximális száma:** *10*
    - **Ciklikus leltárok közötti napok:** *10*
    - **Üres helyek:** *Üresek kizárása*
    - **Munkasablon:** Hagyja üresen ezt a mezőt.

1. A Művelet ablaktáblán kattintson a **Helyek kiválasztása** elemre.
1. Megjelenik egy szabványos lekérdezésszerkesztő párbeszédpanelje. A **Tartomány** lapon adjon hozzá egy sort, mad állítsa be hozzá az alábbi értékeket:

    - **Tábla:** *Helyek*
    - **Mező:** *Zóna azonosítója*
    - **Feltételek:** *BULK06*

1. Az lekérdezésszerkesztő párbeszédablak bezárásához kattintson az **OK** lehetőségre.
1. A Művelet ablaktáblán válassza ki a **Ciklikus leltározási terv feldolgozása** lehetőséget.
1. Az **Ciklikus leltározási tervek** párbeszédablakban, a **Futtatás a háttérben** gyorslapon állítsa a **Kötegelt feldolgozás** beállítást *Igen* értékre.
1. **Ismétlődés** kiválasztása.
1. Az **Ismétlődés definiálása** párbeszédpanelen állítsa be a kötegelt feladatot úgy, hogy az azonnal elkezdődik, és minden percét lefutja, és ne legyen záró dátum.
1. Kattintson az **OK** gombra az **Ismétlődés meghatározása** párbeszédpanel bezárásához.
1. Kattintson az **OK** gombra a **Ciklikus leltározási tervek** párbeszédpanel bezárásához.

    Egy üzenet tájékoztatja arról, hogy a feladat felkerült a köteg várólistájára.

1. Menjen a **Warehouse Management \> Közös \> Ciklikus leltározási ütemezés** lehetőségre. A terv azonnal elkezdődik, és leltározási munkát hoz létre. Mivel a leltározási munka nem fejeződött be, az **Állapot** mező beállítása *Folyamatban* értékű. Egy perc múlva az **Összes ciklikus leltározás** oszlop értéke *1*-re módosul.

    > [!NOTE]
    > Nem jön létre ciklikus leltározási munka, ha a legutóbbi ciklikus leltár óta eltszámolás óta ennyi nap van beállítva a ciklikus leltározási terv a **Ciklikus leltározás közötti napok** mező számának beállításában. Ha például a **Ciklikus leltárok közötti napok** mező megadott beállítása *5*, a ciklikus leltározási munka ötnaponként készül. Azonban ha a ciklikus leltározási munka feldolgozása megtörténik a 3. napon, akkor a következő ciklikus leltározási munka öt nappal az utolsó ciklikus leltár után jön létre, a 8. napon.

1. A munkaablakban válassza a **Munka** lehetőséget a létrehozott leltári munka megtekintéséhez.
