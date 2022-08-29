---
title: Helyutasítás – készletkitárolás korosítása
description: Ez a cikk bemutatja, hogy hogyan lehet elsőként be, elsőként ki (FIFO) és utolsóként be, elsőként ki (LIFO) hely irányelvstratégiát használni kitároláskor.
author: Mirzaab
ms.date: 08/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLocationProfile,WHSWorkTable,WHSWaveTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-15
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 4ed1308ea36b731b156b518182846b60a59528d5
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/23/2022
ms.locfileid: "9335615"
---
# <a name="location-directive-inventory-picking-aging"></a>Helyutasítás – készletkitárolás korosítása

[!include [banner](../includes/banner.md)]

Ez a cikk bemutatja, hogy hogyan lehet elsőként be, elsőként ki (FIFO) és utolsóként be, elsőként ki (LIFO) hely irányelvstratégiát használni kitároláskor. Ezek a stratégiák együtt működnek a raktáraknak a raktárba történő első beérkezése alkalmával nyilvántartott korosítási dátumokkal együtt. A *Helyutasítás – készletkitárolás korosítása* szolgáltatása a hely dátumát használja a korosítás megállapításához. A *Raktár helyállapota* funkció a helyen érvényes dátumot az azonosítótábla dátuma alapján frissíti.

A FIFO-és LIFO-stratégiákkal mind a kötegelt nyomon követett cikkek, mind a nem kötegelt követett cikkek szállíthatók a készlet raktárba érkezésének dátuma alapján. Ez a funkció különösen a nem kötegelt nyomon követett készletekben hasznos, ahol a lejárati dátum nem használható a rendezéshez.

A készlet első beérkezése vagy a raktárban való létrehozása alkalmával a rendszer frissíti a megfelelő azonosítótábla-nyilvántartást, így az aktuális dátum a korosítási dátumként jelenik meg. Ezt a dátumot használják a helyutasítás-stratégiák, hogy megállapítsák a raktár legrégebbi vagy legújabb készletét. Ha a készletet azonosítótábla által nem követett helyre helyezi át, akkor a helyszín maga frissítve lesz a korosítási adatokkal, és ezeket az információkat a fogják használni a stratégiák.

## <a name="turn-on-the-feature"></a>A funkció bekapcsolása

A funkció elérhetővé tétele érdekében kapcsolja a [funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) modulban a következő szolgáltatásokat ebben a sorrendben:

1. *Raktár helyének állapota* (a 10.0.29-es verziónál ez a funkció kötelező, és nem lehet kikapcsolni. További tájékoztatás: Raktári [hely állapota](warehouse-location-status.md).)
1. *Helyutasítás – készletkitárolás korosítása*

## <a name="feature-requirements"></a>Funkció követelmények

Ennek a funkció a használatához be kell állítania a **Helyállapot engedélyezése** beállítást *Igen* értékre a készlet tárolásához használt minden [helyprofilhoz](tasks/create-location-profile.md). Ha meg szeretné adni ezt a beállítást egy hely profilhoz, nyissa meg a **Raktárkezelés \> Beállítás \> Raktár \> Helyprofilok** menüpontot, és válassza ki a helyprofilt. A beállítást az **Általános** gyorslapon találhatja meg.

## <a name="feature-scenarios"></a>Funkció-forgatókönyvek

Ez a szakasz példákkal mutatja be, hogyan lehet beállítani és használni a FIFO- és LIFO-stratégiákat.

> [!TIP]
> Ez a szakasz két forgatókönyvet tartalmaz: az egyet a FIFO-ra, egyet pedig a LIFO számára. A bemutatott eljárás feltételezi, hogy mindkét forgatókönyvet sorrendben végzi el. Javasoljuk, hogy mindkét esetet végezze el, így megtapasztalhatja a két stratégia közötti különbségeket.

### <a name="make-sample-data-available"></a>A mintaadatok elérhetővé tétele

Ha ezeket a forgatókönyveket az itt megadott mintaadatok és értékek alapján kívánja elvégezni, akkor egy olyan rendszert kell használnia amelynél a szokásos [demóadatok](../../fin-ops-core/fin-ops/get-started/demo-data.md) telepítve vannak. Emellett az **USMF** jogi személyt is ki kell választani a kezdés előtt.

Ezeket a forgatókönyveket a gyártási rendszer használata során a funkció használatához útmutatásként is használhatja. Ebben az esetben azonban az itt leírt mindegyik beállítás esetében be kell helyettesítenie a saját értékeit.

### <a name="set-up-the-scenarios"></a><a name="demo-set-up"></a>Forgatókönyvek beállítása

A demo adatokhoz beállítás és készletkorrekciók szükségesek a helyzetek támogatásához. A következő lépések végrehajtásával hozza létre azokat a leltározási adatokat, amelyek szükségesek ahhoz, a FIFO-és LIFO-forgatókönyvek elvégzéséhez.

1. Jelentkezzen be a rendszerbe, ahová a demóadatok telepítve vannak, és válassza ki az **USMF** jogi személyt.
1. Ugorjon a **Raktárkezelés \> Beállítás \> Raktár \> Helyprofilok** pontra.
1. A műveleti ablaktáblán válassza a **Szerkesztés** lehetőséget.
1. A helyprofilok listáján válassza az **5. EMELET** elemet.
1. Az **Általános** gyorslapon állítsa a **Helyállapot engedélyezése** beállítást *Igen* értékre.
1. Válassza a **Mentés** lehetőséget.
1. Ugrás a **Raktárkezelés \> Beállítás \> Helyutasítások** elemre.
1. Az irányelvek listáiban válassza a **63 SO kitárolási tárolóra bontás** elemet.
1. Válassza ki a **Szerkesztés** parancsot, hogy a lapot szerkesztési módba helyezze.
1. A **Helyutasítás-műveletek** gyorslapon keresse meg azt a sort, amelynél a **Sorozatszám** mező értéke *1*, és kövesse az alábbi lépések egyikét:

    - Ha FIFO-esetet állít be, akkor módosítsa a **Stratégia** mező értékét a *FIFO-helykorosítás* értékére.
    - Ha LIFO-esetet állít be, akkor módosítsa a **Stratégia** mező értékét a *LIFO-helykorosítás* értékére.

1. A **Helyutasítás műveletei** gyorslapon válassza a **Lekérdezés szerkesztése** lehetőséget.
1. A lekérdezés párbeszédpanel **Tartomány** lapján válassza a **Hozzáadás** parancsot egy sor hozzáadásához, majd állítsa be a következő értékeket:

    - **Tábla:** *Helyek*
    - **Származtatott tábla:** *Helyek*
    - **Mező:** *Zóna azonosítója*
    - **Feltételek:** *Emelet*

1. Az **OK** gombra kattintva alkalmazza a beállításokat, és zárja be a lekérdezési párbeszédpanelt.
1. A helyutasítás módosításainak mentéséhez válassza a **Mentés** elemet.
1. Egy mobileszközön vagy a *Dynamics 365 Supply Chain Management – Raktározás* alkalmazásban számítógépén következő lépésekkel távolítsa el a meglévő készletet a raktári helyről, hogy támogassa a forgatókönyveket:

    1. Jelentkezzen be a mobileszközön az *63-as* raktárba a megfelelő felhasználói azonosító és jelszó használatával.
    1. Válassza a főmenü **Minőség** elemét.
    1. A **Minőségkezelés** menüben válassza a **Selejt** lehetőséget.
    1. A **Selejt** oldalon válassza a **HELY / AT** mezőt, majd írja be a *63\_1* értéket.
    1. Válassza az **Enter** vagy az **OK** lehetőséget.
    1. Erősítse meg a **Selejt** részleteit az **Igazítás ki** elemhez az **Enter** vagy az **OK** kiválasztásával.

    Amikor az azonosítótábla-készletet kiigazították, egy „Munka elvégezve” üzenet jelenik meg.

    Ezekkel a lépésekkel két helyen hagy készletet a demóadatokban. Mindegyik helynek eltérő a korosítási dátuma. Az *FL-001* hely korosítási dátuma 2017. április 15, és az *FL-002* hely korosítási dátuma 2017. január 29. Mindkét hely tartalmazza az *A0001* cikket.

    Ezeknek az adatoknak a megtekintéséhez nyissa meg a **Készletkezelés \> Lekérdezések és jelentések \> Aktuális lista** lehetőséget, majd szűrjön a *63*-as raktárra és az *A0001* cikkre. Azokban a sorokban, amelyeknél a **Hely** mező értéke *FL-001* vagy *FL-002*, jelöljön ki egy pozitív **Tényleges készlet** értéket tartalmazó sort , majd a műveleti ablaktáblán válassza ki a **Tranzakciók** lehetőséget. A **Tényleges dátum** mező azt a dátumot jeleníti meg, amely megfelel a korábban említett korosítási dátumok egyikének.

### <a name="scenario-1-set-up-and-use-fifo-location-aging"></a><a name="fifo-demo"></a>1. eset: FIFO-hely korosításának beállítása és használata

A FIFO-stratégia megtalálja azt a helyet, amely a legrégebbi korosítási dátumot tartalmazza, és a kitárolást a korosítási dátum alapján osztja el.

1. Ha még nem tette meg, végezze el az ehhez az esethez szükséges [mintaadatok előkészítését](#demo-set-up).
1. Ugorjon az **Értékesítés és marketing \> Értékesítési rendelés \> Összes értékesítési rendelés** pontra.
1. Válassza az **Új** lehetőséget.
1. Az **Értékesítési rendelés létrehozása** párbeszédpanelen adja meg a következő értékeket:

    - A **Vevő** gyorslapon adja meg a **Vevőfiók** mezőt az *US-001* számára.
    - Az **Általános** gyorslap **Raktár** mezőjében állítsa be az *63* értéket.

1. Válassza az **OK** gombot a beszerzési rendelés létrehozásához és a párbeszédpanel bezárásához.
1. A program megnyitja az új értékesítési rendelést. Tartalmaz egy új, üres sort az **Értékesítési rendelés sorai** gyorslap rácsán. Ehhez a rendelési sorhoz állítsa be a **Cikkszám** mezőt *A0001* és a **Mennyiség** mezőt *1* értékre.
1. A rács feletti **Készlet** menüben válassza ki a **Foglalás** pontot.
1. A **Foglalás** oldalon válassza ki az **Adag foglalása** lehetőséget, hogy lefoglalja a cikk megrendelt mennyiségét ebből a készletből a kiválasztott raktárban.
1. Zárja be a **Foglalás** képernyőt.
1. Az **Értékesítési rendelés** oldalán a műveleti ablaktáblán a **Raktár** lapon a **Műveletek** csoportban válassza a **Kiadás raktárhoz** lehetőséget. Tájékoztató üzeneteket kap. A rendszer létrehoz egy szállítmányt, hozzáadja azt egy új terheléshez, és létrehozza a szükséges munkát.
1. Az **Értékesítésirendelés-sorok** gyorslap **Raktár** menüjében válassza ki a **Munka adatai** lehetőséget, és nyissa meg az ehhez az értékesítési rendeléshez létrehozott munkát. Figyelje meg, hogy a sorban, ahol a **Munkatípus** értéke *Kitárolás* egy **Hely** érték látható, ami *FL-002*. Ez a hely tartalmazza azt az azonosítótábla-típust, amelynek a legrégebbi a korosítási dátuma (FIFO).
1. Válassza a **Raktár \> Szállítmány adatai** lehetőséget.
1. Az **Általános** gyorslapon jegyezze fel a hullámazonosítót, hogy a 2. forgatókönyvben is használható legyen.

### <a name="scenario-2-set-up-and-use-lifo-location-aging"></a>2. forgatókönyv: LIFO-hely korosításának beállítása és használata

A LIFO-stratégia megtalálja azt a helyet, amely a legújabb korosítási dátumot tartalmazza, és a kitárolást a korosítási dátum alapján osztja el. A 2. forgatókönyvben szerkeszteni fogja az 1. eset (FIFO) beállítását, majd újra fel fogja használni az adott esethez létrehozott értékesítési rendelést és hullámot.

1. A forgatókönyv elkezdése előtt be kell állítania és el kell végeznie a teljes FIFO-esetet az [előző szakaszban](#fifo-demo) leírtak szerint. Ebben a helyzetben újra felhasználja a hullámot, és a legtöbb beállítást, amelyet ahhoz az esethez hozott létre.
1. Szerkessze a **63 kitárolási tárolóra bontás** helyutasítást, hogy a *LIFO helykorosítás* stratégiát használja, ahogy azt a [Forgatókönyvek beállítása](#demo-set-up) eljárás első része ismertette.

    Ezt követően módosítani fogja az 1. forgatókönyv szerinti értékesítési rendeléshez létrehozott hullámot, hogy az a *LIFO helykorosítás* stratégiát használja.

1. Ugorjon a **Raktárkezelés \> Kimenő hullámok \> Szállítmányhullámok \> Minden hullám** menübe.
1. Válassza ki, majd nyissa meg azt a hullámot, amely a FIFO-esethez létrehozott rendelést tartalmazza.
1. A művelet ablaktábla **Munka** lapján a **Mégse** gombra kattintva törölje a FIFO-esethez létrehozott munkát.
1. A Műveleti ablaktáblán a **Hullám** lapon a **Hullám** csoportban válassza a **Folyamat** lehetőséget.
1. Ha a feldolgozás elkészült műveleti ablaktábla **Hullám** lapján a **Kapcsolódó információ** csoportban válassza ki a **Munka** elemet a hullámhoz létrehozott munka megnyitásához.
1. A **Munka** lap **Áttekintés** lapján két sornak kell lennie. Válassza ki azt a sort, amelynél a **Munkállapot** mező értéke *Megnyitva*.
1. Figyelje meg, hogy a sorban, ahol a **Munkatípus** értéke *Kitárolás* egy **Hely** érték látható, ami *FL-001*. Ez a hely tartalmazza azt az azonosítótábla-típust, amelynek a legújabb a korosítási dátuma (LIFO).

Ezekben az esetekben megismerhette, hogy hogyan irányítja a helykorosítási stratégia a munkát arra készlethelyre a hol a legrégebbi készlet vagy a legújabb készlet van a kiválasztott stratégiától függően.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
