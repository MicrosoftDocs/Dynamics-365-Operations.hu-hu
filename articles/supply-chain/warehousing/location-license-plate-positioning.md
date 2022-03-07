---
title: Hely és azonosítótábla pozicionálása
description: Az azonosítótábla elhelyezésével megtekintheti, hogy hol található az azonosítótábla egy több raklapos helyen, például olyan helyen, amely dupla mélységű raklapállványt használ.
author: Mirzaab
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLicensePlate, WHSLocationProfile, WHSLocDirTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 1235f8fa64fbc87a4c22f4dcf0e9ddd4b4565b76
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/06/2021
ms.locfileid: "6359763"
---
# <a name="location-license-plate-positioning"></a>Hely és azonosítótábla pozicionálása

[!include [banner](../includes/banner.md)]

Az azonosítótábla elhelyezésével megtekintheti, hogy hol található az azonosítótábla egy több raklapos helyen, például olyan helyen, amely dupla mélységű raklapállványt használ.

A szolgáltatás sorozatszámot ad minden olyan azonosítótáblához, amely tárolási helyre kerül. Ez a sorozatszám az azonosítótáblák rendezésére szolgál a tárolási helyen. Ennélfogva a funkció intelligens módon támogatja azokat a helyzeteket, amelyekben a vevők gravitációs állványrendszert használnak, és a kitárolás céljából ismerniük kell, hogy az azonosítótáblák közül melyik van elöl.

Ez a témakör azt mutatja be, hogyan lehet beállítani és használni a szolgáltatást.

## <a name="turn-on-the-location-license-plate-positioning-feature"></a>A helyazonosító tábla elhelyezési funkciójának bekapcsolása

Az azonosítótábla-elhelyezés használata előtt a funkciót be kall kapcsolni a rendszerében. A rendszergazdák használhatják a [Funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) munkaterületet a funkció állapotának ellenőrzéséhez, és szükség esetén bekapcsolásához. A funkció a következő módon jelenik meg:

- **Modul:** *Raktárkezelés*
- **Funkció neve:** *Helyazonosító tábla elhelyezése*

## <a name="example-scenario"></a>Példaforgatókönyv

### <a name="make-sample-data-available"></a>A mintaadatok elérhetővé tétele

Ha ezt a forgatókönyvet az itt javasolt mintaadatok és értékek alapján kívánja elvégezni, akkor egy olyan rendszeren kell dolgoznia, amelynél a mintaadatok telepítve vannak. Emellett az **USMF** jogi személyt is ki kell választani a kezdés előtt.

### <a name="set-up-the-feature-for-this-scenario"></a>A funkció beállítása ehhez a helyzethez

Hajtsa végre a következő lépéseket az ebben a témakörben bemutatott *Helyazonosító tábla elhelyezése* funkció beállításához.

#### <a name="location-profiles"></a>Helyprofilok

A funkciót minden olyan hely helyprofiljában be kell kapcsolni, ahol használatban lesz.

1. Ugorjon a **Raktárkezelés \> Beállítás \> Raktár \> Helyprofilok** pontra.
1. A bal oldali ablaktáblán a helyprofilok listáján válassza a **BULK-06** értéket.
1. Az **Általános** gyorslapon két új beállítás van hozzáadva a funkció által. Adja meg az alábbi értékeket:

    - **Azonosítótábla-elhelyezés engedélyezése:** *Igen*

        Ha ez a beállítás *Igen* értékre van állítva, akkor a rendszer az azonosítótábla pozícióját fogja fenntartani a helyhez tartozó azonosítótábla esetében.

    - **Mobileszköz azonosítótábla-helyének megjelenítése:** *Igen*

        Ha ez a beállítás *Igen* értékre van állítva, akkor az azonosítótábla helye jelenik meg a mobileszköz-felhasználók számára a módosítás és a leltározás során. Ez a beállítás csak akkor módosítható, ha a funkció be van kapcsolva.

1. Válassza a **Mentés** lehetőséget.

#### <a name="location-directives"></a>Helyutasítások

1. Ugrás a **Raktárkezelés \> Beállítás \> Helyutasítások** elemre.
1. A bal oldali ablaktáblában győződjön meg arról, hogy a **Munkarendelés típusa** mező *Értékesítési rendelések* értékre van-e beállítva.
1. Az irányelvek listáiban válassza a **61 SO kitárolási rendelés** elemet.
1. A műveleti ablaktáblán válassza a **Szerkesztés** lehetőséget.
1. A **Sorok** gyorslapon válassza ki azt a sort, amelynél a **Sorozatszám** értéke *2*.
1. A **Helyutasítás műveletei** gyorslapon válassza ki azt a sort, amely a *Kitárolás raklapnál kevesebbhez* (ennek kell az egyedüli sornak lennie) **Név** értékkel rendelkezik, és módosítsa a **Sorszám** beállítás a *2* értékre.
1. Válassza ki a rács fölötti **Új** lehetőséget, és hozzon létre egy új sort egy helyutasítási művelethez.
1. Az új sorban állítsa be a következő értékeket:

    - **Sorszám:** *1*
    - **Név:** *1. kitárolási hely*

1. Az új sort továbbra is kijelölve, válassza a rács fölötti **Lekérdezés szerkesztése** elemet.
1. A lekérdezéstervezőben válassza az **Illesztések** lapot.
1. Bontsa ki a **Helyek** táblájának illesztéseit a **Készletdimenziók** táblával való kapcsolat megjelenítéséhez.
1. Bontsa ki a **Készletdimenziók** táblájának illesztését az **Aktuális készlet** táblával való kapcsolat megjelenítéséhez.
1. Válassza ki a **Készletdimenziók** lehetőséget, majd a , majd válassza a **Táblaillesztés hozzáadása** lehetőséget.
1. A megjelenő táblák listáján, a **Kapcsolat** oszlopban válassza ki az **Azonosítótábla (Azonosítótábla)** lehetőséget. Ezután válassza a **Kiválasztás** lehetőséget **Azonosítótábla** hozzáadásához a **Készletdimenziók** táblaillesztéshez.
1. Miközben az **Azonosítótábla** továbbra is be van jelölve, válassza a **Táblaillesztés hozzáadása** lehetőséget.
1. A megjelenő táblák listáján, a **Kapcsolat** oszlopban válassza ki a **Helyazonosító tábla elhelyezése (Azonosítótábla)** lehetőséget. Ezután válassza a **Kiválasztás** lehetőséget **Helyazonosító tábla elhelyezése** elem hozzáadásához a **Készletdimenziók** táblaillesztéshez.

    ![Táblaillesztések.](media/LpTableJoin.png "Táblaillesztések")

1. Az **OK** lehetőséget kiválasztva erősítse meg a frissített összekapcsolt táblákat, és zárja be a lekérdezésszerkesztőt.
1. A **Helyutasítások műveletei** gyorslapon válassza ismét a **Lekérdezés szerkesztése** lehetőséget a lekérdezésszerkesztő ismételt megnyitásához.
1. A **Tartomány** lapon válassza a **Hozzáadás** lehetőséget sor hozzáadásához a rácshoz.
1. Az új sorban állítsa be a következő értékeket:

    - **Táblázat:** *Helyazonosító tábla elhelyezése*
    - **Származtatott tábla:** *Helyazonosító tábla elhelyezése*
    - **Mező:** *LP pozíció*
    - **Feltételek:** *1*

    ![Új tartomány.](media/LpPositionCriteria.png "Új tartomány")

1. Az **OK** gombra kattintva erősítse meg a változtatásokat, és zárja be a lekérdezésszerkesztőt.

### <a name="set-up-sample-data-for-this-scenario"></a>A mintaadatok beállítása ehhez a helyzethez

Ennél a helyzetnél a felhasználónak be kell jelentkeznie a raktározási mobilalkalmazásba egy olyan dolgozóval, aki a *61*-es raktárhoz be van állítva munkavégzéshez. A felhasználónak is végre kell hajtania a tranzakciókat.

Mivel a *Helyazonosító tábla elhelyezése* funkció új azonosítót ad hozzá az azonosítótábla helyhez egy adott helyen, először létre kell hoznia néhány adatot a forgatókönyv támogatásához.

#### <a name="spot-count-the-first-location"></a>Az első hely eseti leltározása

1. Nyissa meg a raktározási alkalmazást, és jelentkezzen be a *61*-es raktárba.
1. Lépjen a **Készlet \> Eseti leltár** lehetőségre.
1. Az **Eseti leltár** oldalon adja meg a **Hely** mezőt a *01A01R1S1B* értékkel.
1. Válassza ki az **OK** lehetőséget.

    A lap megjeleníti a megadott helyet. Ezenkívül a következő üzenet jelenik meg: „Hely kész, új LP vagy cikk hozzáadása?”

1. Válassza a **Frissítés** lehetőséget, ha egy leltárfelvételt szeretne hozzáadni a helyhez.
1. A **Ciklikus leltározás: Új LP vagy cikk hozzáadása** oldalon válassza ki a **Cikk** mezőt, majd írja be az *A0001* értéket.
1. Válassza ki az **OK** lehetőséget.
1. A **Ciklikus leltározás: Új LP vagy cikk hozzáadása** oldalon válassza ki az **LP** mezőt, majd írja be az *LP1001* (vagy a kiválasztott egyéb azonosítótábla) értékét.

    A **Ciklikus leltározás: Új LP vagy cikk hozzáadása** oldal megjeleníti az **1. azonosítótábla helye** értéket.

1. Válassza ki az **OK** lehetőséget.

    Ezután meg kell adnia az azonosítótáblán megszámlált cikkek mennyiségét.

1. Állítsa a **Mennyiség** mezőt *10* értékre.
1. Válassza ki az **OK** lehetőséget.

    A lap megjeleníti a megadott helyet. Ezenkívül a következő üzenet jelenik meg: „Hely kész, új LP vagy cikk hozzáadása?”

1. Válassza a **Frissítés** lehetőséget, ha egy további leltárfelvételt szeretne hozzáadni a helyhez.
1. A **Ciklikus leltározás: Új LP vagy cikk hozzáadása** oldalon válassza ki a **Cikk** mezőt, majd írja be az *A0002* értéket.
1. Válassza ki az **OK** lehetőséget.
1. A **Ciklikus leltározás: Új LP vagy cikk hozzáadása** oldalon válassza ki az **LP** mezőt, majd adja meg az *LP1002* (vagy bármely egyéb kiválasztott azonosítótábla, feltéve, hogy az eltér a korábban megadott azonosítótáblától) értékét.
1. Módosítsa az azonosítótábla pozícióját úgy, hogy az **LP hely** mező számára a *2* értéket állítja be.
1. Válassza ki az **OK** lehetőséget.
1. Adja meg az azonosítótáblán megszámolt cikk mennyiségét a **Mennyiség** mezőt *10* értékre állítva.
1. Válassza ki az **OK** lehetőséget.

    A lap megjeleníti a megadott helyet. Ezenkívül a következő üzenet jelenik meg: „Hely kész, új LP vagy cikk hozzáadása?”

1. Válassza ki az **OK** lehetőséget.

A munka ezzel befejeződött.

#### <a name="spot-count-the-second-location"></a>A második hely eseti leltározása

1. Az **Eseti leltár** oldalon adja meg a **Hely** mezőt a *01A01R1S2B* értékkel.
1. Válassza ki az **OK** lehetőséget.

    A lap megjeleníti a megadott helyet. Ezenkívül a következő üzenet jelenik meg: „Hely kész, új LP vagy cikk hozzáadása?”

1. Válassza a **Frissítés** lehetőséget, ha egy leltárfelvételt szeretne hozzáadni a helyhez.
1. A **Ciklikus leltározás: Új LP vagy cikk hozzáadása** oldalon válassza ki a **Cikk** mezőt, majd írja be az *A0002* értéket.
1. Válassza ki az **OK** lehetőséget.
1. A **Ciklikus leltározás: Új LP vagy cikk hozzáadása** oldalon válassza ki az **LP** mezőt, majd adja meg az *LP1003* (vagy bármely egyéb kiválasztott azonosítótábla, feltéve, hogy az eltér a korábbi eljárásban megadott mindkét azonosítótáblától) értékét.

    A **Ciklikus leltározás: Új LP vagy cikk hozzáadása** oldal megjeleníti az **1. azonosítótábla helye** értéket.

1. Válassza ki az **OK** lehetőséget.
1. Adja meg az azonosítótáblán megszámolt cikk mennyiségét a **Mennyiség** mezőt *10* értékre állítva.
1. Válassza ki az **OK** lehetőséget.

    A lap megjeleníti a megadott helyet. Ezenkívül a következő üzenet jelenik meg: „Hely kész, új LP vagy cikk hozzáadása?”

1. Válassza ki az **OK** lehetőséget.

A munka ezzel befejeződött.

#### <a name="work-details"></a>Munka részletes adatai

> [!NOTE]
> Az eseti leltár a mobilalkalmazásból ciklikus leltározási feladatot hoz létre a Microsoft Dynamics 365 alkalmazásban. A munka megköveteli, hogy a leltárt a program a készletbe történő feladás előtt elfogadja.

1. Jelentkezzen be a Dynamics 365 Supply Chain Management alkalmazásba.
1. Ugorjon a **Raktárkezelés \> Munka \> Munka részletei** pontra.
1. Az **Áttekintés** lapon keressük meg azokat a sorokat, amelyek a következő értékeket jelentik:

    - **Munkarendelés típusa:** *Ciklikus leltározás*
    - **Raktár:** *61*
    - **Munka állapota:** *Ellenőrzésre vár*

    Ezekhez a sorokhoz két munkaazonosítónak kellett létrejönnie. Mindkét munkaazonosító számát el kell fogadni.

1. A rácsban válassza ki a *Ciklikus leltározás* munkarendelés-típus első munkaazonosítóját.
1. A Művelet ablaktábla **Munka** lapjának **Munka** csoportjában válassza a **Ciklikus leltározás** elemet.

    Két sor látható, egy-egy a cikkek és az azonosítótábla számára. A **Megszámlált mennyiség**, a **Hely**, az **Azonosítótábla** és a **Cikk** mező értékeinek meg kell egyezniük a mobileszköz által létrehozott leltárbejegyzésekkel. Ha ezek a mezők nem láthatók, akkor válassza a **Dimenziók megjelenítése** lehetőséget a Művelet panelen a rácshoz való hozzáadásukhoz.

1. Válassza ki mindkét sort.
1. A Művelet ablaktáblán válassza ki a **Számlálás elfogadása** lehetőségre.
1. A „Feladás - Napló” üzenet jelenik meg. Válassza az **Üzenet részletei** lehetőséget a feladott napló számának megtekintéséhez.
1. Zárja be az üzenet részleteit.
1. Frissítse a **Munka** oldalt.

    A program lezárta az első munkaazonosítót, és már nem jelenik meg.

    > [!TIP]
    > Ha meg szeretné tekinteni a lezárt munkát, jelölje be a **Lezárt megjelenítése** jelölőnégyzetet a rács felett.

    Ezt követően elfogadja a *01A01R1S2B* helyen található azonosítótáblára vonatkozó munkát.

1. Az **Áttekintés** lapon válassza ki a *Ciklikus leltározás* munkarendelés-típus második munkaazonosítóját.
1. A Művelet ablaktábla **Munka** lapjának **Munka** csoportjában válassza a **Ciklikus leltározás** elemet.

    Egy sor jelenik meg a cikk és az azonosítótábla esetében. A **Megszámlált mennyiség**, a **Hely**, az **Azonosítótábla** és a **Cikk** mező értékeinek meg kell egyezniük a mobileszköz által létrehozott leltárbejegyzésekkel.

1. Jelölje ki a sort.
1. A Művelet ablaktáblán válassza ki a **Számlálás elfogadása** lehetőségre.
1. A „Feladás - Napló” üzenet jelenik meg. Válassza az **Üzenet részletei** lehetőséget a feladott napló számának megtekintéséhez.
1. Zárja be az üzenet részleteit.
1. Frissítse a **Munka** oldalt.

    A program lezárta a második munkaazonosítót, és már nem jelenik meg.

    > [!TIP]
    > Ha meg szeretné tekinteni a lezárt munkát, jelölje be a **Lezárt megjelenítése** jelölőnégyzetet a rács felett.

#### <a name="on-hand-by-location"></a>Aktuális készlet hely szerint

1. Nyissa meg a következőt: **Raktárkezelés \> Lekérdezések és jelentések \> Aktuális helyenként**.
1. Adja meg az alábbi értékeket:

    - **Telephely:** *6*
    - **Raktár:** *61*
    - **Frissítés helyek között:** *Igen*

1. Figyelje meg, hogy a *01A01R1S1B* hely kétféle azonosítótáblával rendelkezik:

    - **A0001**, ahol az **LP hely** mező értéke *1.*
    - **A0002**, ahol az **LP hely** mező értéke *2.*

1. Figyelje meg, hogy a *01A01R1S2B* hely egyféle azonosítótáblával rendelkezik:

    - **A0002**, ahol az **LP hely** mező értéke *1.*

### <a name="sales-order-scenario"></a>Értékesítési rendelés forgatókönyve

Most, hogy a *Helyazonosító tábla elhelyezése* funkció be van állítva, és a készlet már elő van készítve, létre kell hozni egy értékesítési rendelést, amely olyan kitárolási munkákat generál, amelyek a raktári dolgozót az *A0002* cikk készlethelyről való kitárolására utasítják, ahol a raklapazonosító az *1*. helyen található.

1. Ugorjon az **Értékesítés és marketing \> Értékesítési rendelések \> Minden értékesítési rendelés** pontra.
1. A Műveleti ablaktáblán kattintson az **Új** elemre.
1. Az **Értékesítési rendelés létrehozása** párbeszédpanelen adja meg a következő értékeket:

    - **Vevőkód** *US-004*
    - **Raktár:** *61*

1. Válassza ki az **OK** lehetőséget.
1. A program új sort ad hozzá a rácshoz az **Értékesítési rendelés sorai** gyorslapon. Az új sorban állítsa be a következő értékeket:

    - **Cikkszám:** *A0002*
    - **Mennyiség:** *1*

1. A rács feletti **Készlet** menüben válassza ki a **Foglalás** pontot.
1. A **Foglalás** oldalon, a műveleti panelen válassza az **Adag foglalása** elemet a rendelési sor készletének foglalásához.
1. Zárja be a **Foglalás** képernyőt.
1. Válassza ki a művelet ablaktáblán a **Raktár** lapon a **Műveletek** csoportjának **Kiadás raktárba** parancsát.

    Olyan tájékoztató üzenet érkezik, amelyek az értékesítési rendeléshez létrehozott hullámazonosítót és szállítási azonosítót jelenítik meg.

1. Az **Értékesítési rendelés sorai** gyorslap **Raktár** menüjében, a rács felett válassza a **Munka részletes adatai** lehetőséget.
1. Megjelenik a **Munka** oldal, és az értékesítési sorhoz létrehozott munkát jeleníti meg. Jegyezze fel a megjelenített munkaazonosítót.

### <a name="sales-picking-scenario"></a>Értékesítési kitárolási eset

1. Nyissa meg a mobilalkalmazást, és jelentkezzen be a *61*-es raktárba.
1. Lépjen a **Kimenő \> Értékesítési kitárolás** lehetőségre.
1. A **Munkaazonosító/azonosítótábla azonosítójának beolvasása** oldalon válassza ki az **Azonosító** mezőt, majd adja meg az értékesítési sor munkaazonosítóját.
1. Figyelje meg, hogy a kitárolási munka az *A0002* cikknek a *01A01R1S2B* helyről való kitárolására utasítja. Ez az utasítás akkor jelenik meg, ha az *A0002* cikk olyan azonosítótáblán van, amely az adott helyen az *1*. pozícióban szerepel.

    ![1. pozíció helye.](media/LocationLicensePlatePositioning.png "1. pozíció helye")

1. Adja meg a helyhez létrehozott azonosítótábla-azonosítót, majd kövesse a figyelmeztetéseket az értékesítési rendelés kitárolásához.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]