---
title: Tervezett áttárolás
description: Ez a témakör a tervezett speciális áttárolást mutatja be, ahol a rendeléshez szükséges készletmennyiség a fogadástól vagy létrehozástól egyenesen a megfelelő kimenő vagy előkészítő területre irányul. A program a bejövő forrásból származó összes fennmaradó készletet a megfelelő tárolóhelyre irányítja a rendszeres elraktározási folyamaton keresztül.
author: Mirzaab
manager: tfehr
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: ae805d9aac790a1a58478cf54d033ce758c5eca3
ms.sourcegitcommit: a7a7303004620d2e9cef0642b16d89163911dbb4
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/01/2020
ms.locfileid: "3530098"
---
# <a name="planned-cross-docking"></a>Tervezett áttárolás

[!include [banner](../includes/banner.md)]

Ez a témakör a speciális tervezett áttárolást mutatja be. Az áttárolás egy raktározási folyamat, ahol a rendeléshez szükséges készletmennyiség a fogadástól vagy létrehozástól egyenesen a megfelelő kimenő vagy előkészítő területre irányul. A program a bejövő forrásból származó összes fennmaradó készletet a megfelelő tárolóhelyre irányítja a rendszeres elraktározási folyamaton keresztül.

Az áttárolás segítségével a dolgozók kihagyhatják a bejövő elraktározást és a készlet kimenő kitárolását, amely már ki van jelölve egy kimenő rendeléshez. Ezért a készlettel való tényleges munkavégzés száma ahol lehet minimalizálásra kerül. Ezenkívül, mivel kevesebb az interakció a rendszerrel, nagyobb idő- és területmegtakarítás érhető el a raktárban.

Az áttárolás futtatása előtt a felhasználónak konfigurálnia kell egy új áttárolási sablont, ahol az ellátási forrás és az áttárolás egyéb követelményhalmazai meg vannak határozva. A kimenő rendelés létrehozásakor a sort egy olyan bejövő rendeléssel szemben kell megjelölni, amely ugyanazt a tételt tartalmazza.

A bejövő rendelés bevételezése idején az áttárolási beállítás automatikusan azonosítja az áttárolási igényt, és létrehozza a szükséges mennyiséghez tartozó áthelyezési munkát a helyutasítás beállításai alapján.

> [!NOTE]
> A készlettranzakciók **nem** frissülnek, ha az áttárolási munka érvénytelenítve van, még akkor sem, ha a raktárkezelési paraméterekben be van kapcsolva a beállítás ehhez a tulajdonsághoz.

## <a name="turn-on-the-planned-cross-docking-feature"></a>A tervezett áttárolási funkció bekapcsolása

A speciális tervezett áttárolás használata előtt be kell kapcsolni azt a rendszerben. A rendszergazdák használhatják a [Funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) munkaterületet a funkció állapotának ellenőrzéséhez, és szükség esetén bekapcsolásához. A funkció a következő módon jelenik meg:

- **Modul:** *Raktárkezelés*
- **Funkció neve:** *Tervezett áttárolás*

## <a name="setup"></a>Beállítás

### <a name="regenerate-load-posting-methods"></a>A terhelésfeladási metódusok újragenerálása

A tervezett áttárolás a rakományok feladási módjaként történik. A funkció bekapcsolását követően újra létre kell hoznia a metódusokat.

1. Nyissa meg a **Raktárkezelés \> Beállítás \> Terhelésfeladási metódusok** lehetőséget.
1. A Művelet ablaktáblán válassza ki a **Metódusok újragenerálása** elemet.

    Amikor a regenerálás befejeződött, olyan metódust kell látnia, amelynél a **Metódus neve** értéke *planCrossDocking*.

1. Zárja be a lapot.

### <a name="create-a-cross-docking-template"></a>Áttárolási sablon létrehozása

1. Ugorjon a **Raktárkezelés \> Beállítás \> Munka \> Áttárolási sablonok** helyre.
1. Jelölje be a műveleti ablakban az **Új** lehetőséget az új sablon létrehozásához.
1. A fejlécben állítsa be a következő értékeket:

    - **Sorozat:** *1*

        Ez a mező határozza meg, hogy milyen sorrendben kell kiértékelni a sablonokat a képernyőn.

    - **Áttárolási sablon azonosítója:** *51*
    - **Leírás:** *Raktár 51*
    - **Igénykiadási irányelv:** *Beszerzési nyugta előtt*
    - **Raktár:** *51*

1. A **Tervezés** gyorslapon beállíthatja a sablon működését. Adja meg az alábbi értékeket:

    - **Igény követelményei:** *Nincs*

        Ez a mező az igénykészlet követelményeit határozza meg. Ha a kiadást megelőzően a szükségletet a készlethez kell kapcsolni, jelölje be a *Jelölés* lehetőséget. Ha az igényt a kiadás előtt rendeléssel le kell foglalni a készletből, válassza a *Rendelés foglalása* lehetőséget.

    - **Keresés típusa:** *Szállítmány helyei*

        Ez a mező határozza meg, hogy az áttárolási munka a szállítmány előkészítési/rakodási helyeit használja-e, illetve hogy a helyet tartalmazó irányelveket kell-e használni a saját előkészítési/rakodási helyek megtalálására.

    - **Munkasablon:** Hagyja üresen ezt a mezőt.

        Ez a mező határozza meg, hogy milyen munkasablont kell használni az áttárolási munka létrehozásakor.

    - **Újraérvényesítés készlet fogadásakor:** *Nem*

        Ez a beállítás határozza meg, hogy a készletet a bevételezés során újra kell-e érvényesíteni. Ha ez a beállítás *Igen* értékre van állítva, akkor mind a maximális idő ablak, mind a lejárati napok tartománya be van jelölve.

    - **Ellenőrzési időablak:** *Igen*

        Ez a beállítás határozza meg, hogy ki kell-e értékelni a maximális időablakot a beszerzési forrás kiválasztása alkalmával. Ha ez a beállítás *Igen* értékre van állítva, akkor elérhetővé válnak a maximális és a minimális időablakhoz kapcsolódó mezők.

    - **Maximális időablak:** *5*

        Ez a mező meghatározza a készlet beérkezése és az igény távozása közötti maximális megengedett időtartamot.

    - **Maximális időablak egysége:** *Nap*
    - **Minimális időablak:** *0*

        Ez a mező meghatározza a készlet beérkezése és az igény távozása közötti minimális megengedett időtartamot.

    - **Minimális időablak egysége:** *Nap*
    - **Lejárati napok tartománya:** *0*

        *Első lejárat első ki (FEFO) feltételek:* Ez a mező azt határozza meg, hogy legfeljebb hány nap lehet a jelenleg a raktárban található először lejáró köteg lejárati dátuma és a bevételezési kötegben lejárati dátuma között.

1. A **Beszerzési források** gyorslapon meghatározhatja, hogy milyen típusú készlet érvényes ehhez a sablonhoz. Válassza az **Új** lehetőséget, majd állítsa be a következő értékeket:

    - **Sorszám:** *1*
    - **Beszerzési forrás:** *Beszerzési rendelés*

### <a name="create-a-work-class"></a>Munkaosztály létrehozása

1. Ugorjon a **Raktárkezelés \> Beállítás \> Munka \> Munkaosztályok** pontra.
1. Jelölje be a műveleti ablakban az **Új** lehetőséget a munkaosztály létrehozásához.
1. Adja meg az alábbi értékeket:

    - **Munkaosztály azonosítója:** *CrossDock*
    - **Leírás:** *Áttárolás*
    - **Munkarendelés típusa:** *Áttárolás*

### <a name="create-a-work-template"></a>Munkasablon létrehozása

1. Lépjen a **Raktárkezelés \> Beállítás \> Munka \> Munkasablonok** elemre.
1. A **Munka rendeléstípusa** mezőben válassza ki az *Áttárolás* elemet.
1. A Művelet panelen válassza az **Új** lehetőséget egy sor hozzáadásához az **Áttekintés** laphoz.
1. Az új sorban állítsa be a következő értékeket:

    - **Sorszám:** *1*
    - **Munkasablon:** *51 Áttárolás*
    - **Munkasablon leríása:** *51 Áttárolás*

1. A **Mentés** gombra kattintva elérhetővé válik a **Munkasablon részletei** gyorslap.
1. A **Munkasablon részletei** gyorslapon válassza az **Új** parancsot, és adjon hozzá egy sort a rácshoz.
1. Az új sorban állítsa be a következő értékeket:

    - **Munka típusa:** *Kitárolás*
    - **Munkaosztály azonosítója:** *CrossDock*

1. Válassza ki az **Új** lehetőséget egy további sor hozzáadásához, és állítsa be a következő értékeket:

    - **Munka típusa:** *Eltárolás*
    - **Munkaosztály azonosítója:** *CrossDock*

1. Válassza a **Mentés** lehetőséget, és győződjön meg arról, hogy az **Érvényes** jelölőnégyzet be van jelölve az *51 Áttárolás* sablonhoz.

> [!NOTE]
> A *Kitárolás* és a *Betárolás* munkatípusok munkaosztályainak azonosnak kell lennie.

### <a name="create-location-directives"></a>Helyutasítások létrehozása

1. Ugrás a **Raktárkezelés \> Beállítás \> Helyutasítások** elemre.
1. A bal oldali ablaktáblában állítsa a **Munkarendelés típusa** mezőt az *Áttárolás* értékre.
1. A Művelet panelen válassza az **Új** lehetőséget, majd állítsa be a következő értékeket:

    - **Sorszám:** *1*
    - **Név:** *51 Áttárolási betárolás*
    - **Munka típusa:** *Eltárolás*
    - **Telephely:** *5*
    - **Raktár:** *51*

1. A **Mentés** gombra kattintva elérhetővé válik a **Sorok** gyorslap.
1. A **Sorok** gyorslapon válassza az **Új** parancsot, ha egy sort szeretne hozzáadni a rácshoz.
1. Az új sorban állítsa be a következő értékeket:

    - **Kezdő mennyiség:** *1*
    - **Záró mennyiség:** *1000000*

1. A **Mentés** gombra kattintva elérhetővé válik a **Helyutasítási műveletek** gyorslap.
1. A **Helyutasítások műveletei** gyorslapon válassza az **Új** parancsot, ha egy sort szeretne hozzáadni a rácshoz.
1. Az új sorban állítsa be a következő értékeket:

    - **Név:** *Baydoor*
    - **Rögzített hely használata:** *Rögzített és nem rögzített helyek*

1. A **Mentés** gombra kattintva teheti elérhetővé a **Lekérdezés szerkesztése** gombot a **Helyutasítások műveletei** eszköztáron.
1. A lekérdezéstervező szerkesztéséhez válassza a **Lekérdezés szerkesztése** parancsot.
1. Győződjön meg arról, hogy a **Tartomány** lapon a következő két sor konfigurálva van:

    - 1. sor:

        - **Tábla:** *Helyek*
        - **Származtatott tábla:** *Helyek*
        - **Mező:** *Raktár*
        - **Feltételek:** *51*

    - 2. sor:

        - **Tábla:** *Helyek*
        - **Származtatott tábla:** *Helyek*
        - **Mező:** *Hely*
        - **Feltételek:** *Baydoor*

1. Az lekérdezésszerkesztő bezárásához kattintson az **OK** lehetőségre.

### <a name="create-a-mobile-device-menu-item"></a>Mobileszköz-menüpont létrehozása

1. Lépjen a **Raktárkezelés \> Beállítás \> Mobileszköz \> Mobileszköz-menüelemek** részre.
1. A bal oldali ablaktáblán látható menüelemek listájában válassza a **Beszerzés eltárolása** elemet.
1. Válassza ki a **Szerkesztés** opciót.
1. A **Munkaosztályok** gyorslapon válassza az **Új** parancsot, ha egy sort szeretne hozzáadni a rácshoz.
1. Az új sorban állítsa be a következő értékeket:

    - **Munkaosztály azonosítója:** *CrossDock*
    - **Munkarendelés típusa:** *Áttárolás*

1. Válassza a **Mentés** lehetőséget.

## <a name="scenario"></a>Forgatókönyv

### <a name="create-a-purchase-order"></a>Beszerzési rendelés létrehozása

A következő lépések szerint hozzon létre egy beszerzési rendelést a beszerzés forrásaként.

1. Menjen a **Beszerzés és forrás \> Beszerzési rendelés \> Összes beszerzési rendelés** pontra.
1. A Műveleti ablaktáblán kattintson az **Új** elemre.
1. Az **Beszerzési rendelés létrehozása** párbeszédpanelen adja meg a következő értékeket:

    - **Szállítói számla:** *104*
    - **Raktár:** *51*

1. Az **OK** gombra kattintva jegyezze fel a rendelés számát.
1. A program új sort ad hozzá a **Beszerzési rendelés sorai** gyorslaphoz. Ezen a soron állítsa be a következő értékeket:

    - **Cikkszám:** *A0001*
    - **Mennyiség:** *5*

### <a name="create-a-sales-order"></a>Értékesítési rendelés létrehozása

A következő lépések szerint hozzon létre egy értékesítési rendelést a kereslet forrásaként.

1. Ugorjon az **Értékesítés és marketing \> Értékesítési rendelések \> Minden értékesítési rendelés** pontra.
1. A Műveleti ablaktáblán kattintson az **Új** elemre.
1. Az **Értékesítési rendelés létrehozása** párbeszédpanelen adja meg a következő értékeket:

    - **Vevőkód** *US-002*
    - **Raktár:** *51*

1. Válassza ki az **OK** lehetőséget.
1. A program új sort ad hozzá az **Értékesítési rendelés sorai** gyorslaphoz. Ezen a soron állítsa be a következő értékeket:

    - **Cikkszám:** *A0001*
    - **Mennyiség:** *3*

### <a name="create-planned-cross-docking"></a>Tervezett áttárolás létrehozása

Hajtsa végre az alábbi lépéseket az értékesítési rendelés tervezett áttárolásának létrehozásához.

1. Válassza ki az imént létrehozott értékesítési rendelés **Értékesítési rendelés részletei** oldalán, a Művelet ablaktábla **Raktár** lapjának **Műveletek** csoportjában válassza a **Kiadás a raktárba** parancsot.

    A raktári kiadási művelet létrehozza az értékesítési rendelés sorának szállítmányát és terhelési sorát, és megpróbálja lefoglalni a készletet.
    
    Tájékoztató üzenetet kap. A következő figyelmeztető üzenet is megjelenik: „Nem jött létre munka a(z) XXXX. hullámhoz. A részleteket lásd a munkakészítési előzmények naplójában.” Ez a viselkedés várható, mert nincs készlet a raktárban.

1. Az **Értékesítési rendelés sorai** gyorslap **Raktár** menüjében válassza a **Szállítás részletes adatai** lehetőséget.

    Megjelenik a **Szállítmány adatai** oldal, és az értékesítési rendeléshez létrehozott szállítmányt jeleníti meg.

1. A **Terhelési sorok** gyorslapon figyelje meg, hogy a **Tervezett áttárolási mennyiség** mező értéke *3*. Mivel a raktárban nem állt rendelkezésre készlet, de az áttárolási sablonban megadott időablakon belül egy érvényes beszerzési forrás fog megérkezni, a program létrehozta az áttárolási mennyiséget.
1. A **Terhelési sorok** gyorslapon válassza a **Tervezett áttárolás** lehetőséget, hogy megtekintse a létrehozott áttárolási részleteket.

## <a name="process-the-cross-docking"></a>Áttárolás feldolgozása

### <a name="purchase-order-receiving-on-the-warehousing-mobile-app"></a>Beszerzési rendelés fogadása a raktározási mobilalkalmazásban

A rendszer az 5 mennyiséget a beszerzési rendelésből a fogadó helyre fogja bevételezni, és két munkát hoz létre.

A létrehozott első munkaazonosítónak van egy *Áttárolás* értékű **Munkarendelés típusa** eleme, amely az értékesítési rendeléshez van kapcsolva. A mennyiség 3, és a végső szállítási helyre van irányítva, így azonnal le lehet szállítani.

A létrehozott második munkaazonosítónak van egy *Beszerzési rendelések* értékű **Munkarendelés típusa** eleme, amely a beszerzési rendeléshez van kapcsolva. A fennmaradó 2 mennyiséget nem lehetett áttárolni, és a rendszer az elraktározásra irányítja.

1. Jelentkezzen be a *51*-es raktárban lévő felhasználóként a mobileszközön.
1. Lépjen a **Bejövő \> Beszerzés fogadása** elemre.
1. A **PONum** mezőbe adja meg a beszerzési rendelés számát.
1. Írja be az *5* értéket a **Mennyiség** mezőbe.
1. Válassza ki az **OK** lehetőséget.
1. A következő lapon adja meg a **Cikk** mező számára az *A0001* értéket.
1. Válassza ki az **OK** lehetőséget.
1. A következő oldalon hagyja jóvá a **PONum**, a **Cikk** és a **Mennyiség** értékét az **OK** gombra kattintva.

    A „Munka befejezve” üzenet jelenik meg.

1. A kilépéshez válassza a **Mégse** lehetőséget.

### <a name="put-away-to-cross-docking-and-bulk"></a>Elraktározás az áttároláshoz és az ömlesztetthez

Jelenleg mindkét munkaazonosítónak ugyanaz a cél azonosítótáblája. A következő lépések befejezéséhez be kell szereznie a munkaazonosítót és a cél azonosítótábla azonosítóját. Ezt az információt a beszerzési rendelés sorának és az értékesítési rendelés sorának munkaadataiból kaphatja meg. Alternatív megoldásként felkeresheti a **Raktárkezelés \> Munka \> Munka részletei** pontot, és szűrhet a munkára, ahol a **Raktár** értéke *51*.

1. A mobileszközön nyissa meg a **Bejövő \> Beszerzés eltárolása** lehetőséget, és írja be a cél azonosítótáblát a munkából.
1. Az **Azonosító** mezőbe írja be a cél azonosítótábla azonosítóját a munka részleteiből.

    Az áttárolási kitárolás oldalon megjeleníti a kitárolási helyet (*RECV*), a cél azonosítótáblát (*azonosítótábla*), a cikket (*A0001*) és a mennyiséget (*3*).

1. Válassza ki az **OK** lehetőséget.
1. A **Cél LP** mezőbe írja be annak az azonosítótábla-azonosítónak a cél azonosítótábláját, amelyet a szállítási helyen el kell helyezni (áttárolni). Tetszőleges azonosítótábla-azonosítót választhat.
1. Válassza ki az **OK** lehetőséget.
1. A következő oldalon az **Azonosító** mezőbe írja be a cél azonosítótábla azonosítóját.
1. Válassza ki az **OK** lehetőséget.
1. Erősítse meg a munkát a fennmaradó 2 mennyiség kitárolásához, majd kattintson az **OK** gombra.
1. A következő lapon válassza a **Kész** lehetőséget a kitárolási folyamat befejezéséhez, és az elraktározási folyamat megkezdéséhez.

    A mobilalkalmazás bemutatja a helyet és az azonosítótáblát, ahol a cikket el kell helyezni.

1. Az **OK** gombra kattintva erősítse meg az **Eltárolás** ömlesztett tárolóhelyet.
1. A következő lapon hagyja jóvá az **Eltárolás** áttárolást az **OK** gombra kattintva.

    A „Munka befejezve” üzenet jelenik meg.

1. A kilépéshez válassza a **Mégse** lehetőséget.

A következő ábra bemutatja, hogy hogyan jelenhet meg a teljesített áttárolási munka a Microsoft Dynamics 365 Supply Chain Management rendszerben.

![Áttárolási munka befejezve](media/PlannedCrossDockingWork.png "Áttárolási munka befejezve")
