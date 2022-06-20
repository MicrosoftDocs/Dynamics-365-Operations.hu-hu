---
title: Értékesítési és átmozgatási rendeléseknél az előírtnál nagyobb mennyiségek kitárolása
description: Ez a cikk bemutatja, hogyan lehet engedélyezni a túltárolást az értékesítési és áttárolási rendelésekhez.
author: GalynaFedorova
ms.date: 07/06/2021
ms.topic: article
ms.search.form: WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2021-07-06
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: b8bbc7d532f910edfb442831d6c906f253dee06c
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8897284"
---
# <a name="over-picking-for-sales-orders-and-transfer-orders"></a>Értékesítési és átmozgatási rendeléseknél az előírtnál nagyobb mennyiségek kitárolása

[!include [banner](../includes/banner.md)]

Ez a cikk egy olyan helyzetet mutat be, amely bemutatja, hogyan lehet engedélyezni egy adott dolgozó vagy az összes dolgozó számára a túl-ki válogatásokat. Az előírtnál nagyobb mennyiség kitárolása folyamat lehetővé teszi a kitárolás során szabályozott túlzott kitárolást.

A raktári előírtnál nagyobb mennyiségű kitárolás egyszerű fogalom. A rendszer lehetővé teszi a dolgozók számára, hogy a rendelésben megadottnál több elemet tároljanak ki. Ennek ellenére figyelembe veszi az átviteli rendelés vagy értékesítési rendelés sorszinten beállított túlszállítási korlátot. Ha túllépik ezt a határértéket, a Warehouse Management alkalmazás értesíti a dolgozókat, hogy túllépik a túlszállítási korlátot.

Az előírtnál nagyobb mennyiség kitárolása funkció minimálisra csökkenti a karbantartást, és a beállítás rugalmas marad. Egy vagy több mobileszköz menüpontot is meghatározhat, és csak egy része esetén engedélyezi a túltárolást. A kiválasztott dolgozókat úgy is meg lehet az értékesítési és átmozgatási rendelések előírtnál nagyobb mennyiség kitárolásában, hogy nem kell módosítani a menüelemeket. Ehelyett a megfelelő dolgozói beállításoknál be lehet kapcsolni egyik vagy mindkét képességet.

A előírtnál nagyobb mennyiség kitárolása funkció segítségével a dolgozók időt és munkát takaríthatnak meg, amikor cikkeket válogatnak és szállítanak. A funkció például lehetővé teszi a dolgozók számára a következő feladatok elvégzését:

- A kitárolás vagy a szállítás során a méretcsökkenés kompenzációja.
- A kitárolási folyamat során ne kelljen kicsomagolni néhány csomagolóanyagot.
- A cikkek szállítás közbeni sérülésének kompenzációja.
- Mennyiség vagy mértékegység eltérés a szállítás során.
- A mennyiségek felosztásának minimalizálása az azonosítótáblákon.
- Elkerülhető az alapanyaghulladék és a drága anyagok hiánya.
- A kitárolás utáni kitárolási mennyiség mérése (például teherautók tömegmérésével).

> [!IMPORTANT]
> A előírtnál nagyobb mennyiség kitárolása funkció csak az értékesítési rendelések és az átviteli rendelések kitárolására és feldolgozására vonatkozik. A feltöltés nem támogatja az előírtnál nagyobb mennyiség kitárolását. A feltöltési munka futtatásakor a rendszer nem engedélyezi a felhasználók számára az előírtnál nagyobb mennyiség kitárolását.

Ez a cikk bemutatja, hogy hogyan lehet beállítani és használni a túl válogatás funkciót.

## <a name="scenario-prerequisite-make-demo-data-available"></a>Forgatókönyv előfeltétele: Bemutatóadatok elérhetővé tétele

A jelen cikkváltozat a Microsoft szabványos bemutatóadatában található értékekre és rekordokra hivatkozik Dynamics 365 Supply Chain Management. Ha azt szeretné, hogy az itt megadott értékeket használja a feladatok végrehajtásához, akkor győződjön meg róla, hogy olyan környezetben dolgozik, ahol a bemutatóadatokat telepítették, és a jogi személy beállítása legyen *USMF*.

## <a name="scenario-setup"></a>Eset beállítása

Mielőtt végighaladna a példaforgatókönyvön és az előírtnál nagyobb mennyiség kitárolását engedélyezni kell mind a megfelelő dolgozóra, mind a kapcsolódó menüelemre.

### <a name="set-up-a-worker-to-allow-for-over-picking"></a>Dolgozó beállítása az előírtnál nagyobb mennyiség kitárolásához

A következő az általános eljárás, amely egy dolgozót úgy konfigurálhat, hogy az értékesítési rendelések és az átviteli rendelések esetén külön engedélyezze az előírtnál nagyobb mennyiség kitárolását. Ez a konfiguráció szabályozza, hogy melyik kitárolási dolgozó használhatja az előírtnál nagyobb mennyiség kitárolását, valamint azt, hogy a dolgozó az átviteli és az értékesítési rendelésekhez is képes-e az előírtnál nagyobb mennyiség kitárolására.

1. Ugrás a **Raktárkezelés \> Beállítás \> Dolgozó** elemre.
1. Az ablakban válassza ki **Julia Funderburkot**.
1. A **Felhasználók** gyorsététi csoportban válassza ki azt a sort, amely a következő értékeket tartalmazza. Ha egy meglévő sor sem rendelkezik ezekkel az értékekkel, hozza létre.

    - **Felhasználóazonosító:** *24*
    - **Felhasználónév:** *WH 24*
    - **Alapértelmezett raktár:** *24*
    - **Menü neve:** *Fő*

1. A **Munka** gyorsábra a *24*-es felhasználóhoz a következő értékeket állítsa be, ha még nincsenek beállítva:

    - **Előírtnál nagyobb mennyiség kitárolás értékesítési rendelésekhez:** *Igen*
    - **Az előírtnál nagyobb mennyiség kitárolásának engedélyezése átviteli rendelésekhez:** *Igen*

### <a name="set-up-a-mobile-device-menu-item-to-allow-for-over-picking"></a>Mobileszköz-menüelem beállítása az előírtnál nagyobb mennyiség kitárolásának engedélyezéséhez

Az előírtnál nagyobb mennyiség kitárolás engedélyezésére a mobileszköz menüelem konfigurálásához szükséges általános eljárás. Attól függően, hogy milyen üzleti követelmények vonatkoznak a mobileszköz menüt használó dolgozó engedélyszintjére, előfordulhat, hogy bizonyos paraméterek ki- vagy bekapcsolva vannak.

1. Lépjen a **Raktárkezelés \> Beállítás \> Mobileszköz \> Mobileszköz-menüelemek** részre.
1. A lista ablaktáblán válassza ki az *Értékesítési kitárolás* nevű rekordot. Ha nincs ilyen nevű rekord, hozza létre. Erősítse meg vagy állítsa be a következő értékeket a rekordhoz:

    - **Menüpont neve:** *Értékesítési kitárolás*
    - **Cím:** *Értékesítési kitárolás*
    - **Mód:** *Munka*
    - **Meglévő munka használata:** *Igen*
    - **Irányítja:** *Felhasználó által irányított*
    - **Cél azonosítótábla felülbírálata:** *Igen*
    - **Az azonosító tábla felülbírálata berakodáskor:** *Igen*
    - **A munka zárolva tartása a felhasználó által:** *Igen*
    - **Az előírtnál nagyobb mennyiség kitárolásának engedélyezése:** *Igen*

> [!IMPORTANT]
> Miután a dolgozóra és a mobileszköz menüelemére vonatkozó paraméterek is engedélyezve vannak, az előírtnál nagyobb mennyiség kitárolás csak a mobileszközön keresztül feldolgozható.

## <a name="example-scenario"></a>Példaforgatókönyv

Az előfeltételek, a dolgozók beállítása és a menüelem beállítása után készen áll a funkció használatára.

### <a name="create-a-sales-order-that-allows-for-overdelivery"></a>Túlszállítást lehetővé tévő értékesítési rendelés létrehozása

1. Ugorjon az **Értékesítés és marketing \> Értékesítési rendelések \> Minden értékesítési rendelés** pontra.
1. Válassza az **Új** elemet új értékesítési rendelés létrehozásához.
1. Az **Értékesítési rendelés létrehozása** párbeszédpanelen adja meg a következő értékeket:

    - **Vevőkód** *US-001*
    - **Raktár:** *24*

1. Válassza ki az **OK** lehetőséget.
1. A program megnyitja az új értékesítési rendelést. Az **Értékesítésirendelés-sorok** gyorslapon adjon hozzá egy sort, amely a következő beállításokat tartalmazza:

    - **Cikkszám:** *A0001*
    - **Mennyiség:** *10*

1. A **Sor részletei** gyorslap **Szállítás** lapján állítsa be a **Túlszállítás** mezőt *10* értékre.
1. Az **Értékesítési rendelés sorai** gyorslapon válassza a **Készlet \> Foglalás** lehetőséget.
1. A **Foglalás** oldalon, a műveleti panelen válassza az **Adag foglalása** elemet a készlet foglalásához.
1. Zárja be a **Foglalás** képernyőt.
1. Válassza ki a művelet ablaktáblán a **Raktár** lapon a **Kiadás raktárba** lehetőséget.

Amikor a feloldás elkészült, olyan tájékoztató üzenetek érkeznek, amelyek az adott kiadásból létrehozott hullámazonosítót rakományazonosítót jelenítik meg.

### <a name="get-the-work-id-and-license-plate-number-for-the-new-order"></a>Kérje le az új rendelés munkaazonosítóját azonosítótáblájának számát

Amikor az értékesítési rendelést kiadta a raktárba, a rendszernek létre kell hoznia egy új munkaazonosítót, amelybe a kitárolt sor kerül. A munkaazonosító és az azonosítótábla-hozzárendelés megkereséséhez hajtsa végre az alábbi lépéseket.

1. Ugorjon a **Raktárkezelés \> Munka \> Munka részletei** pontra.
1. Az **Áttekintés** rácsban keresse meg az imént létrehozott két értékesítési rendelés **Rendelési szám** oszlopát. Jegyezze fel az ennek az értékesítési rendelésnek a kapcsolódó munkaazonosítóját.
1. Válassza ki az új értékesítési rendelés sorát a **Sorok** rácsban. Jegyezze fel azt a helyet, ahonnan a cikk kitárolása történik.
1. Menjen a **Készletkezelés \> Lekérdezések és jelentések \> Aktuális készletlista** lehetőségre.
1. A Műveleti ablaktáblán válassza a **Dimenziók** elemet.
1. Győződjön meg róla, hogy a **Dimenzió megjelenítése** párbeszédpanelen be van jelölve az **Azonosítótábla** a **Raktár** és a **Cikkszám** jelölőnégyzet, majd kattintson az **OK** gombra.
1. A **Szűrő** ablaktáblában adja meg a következő szűrőket:

    - **Cikkszám** – **egyike a következőknek** – *A0001*
    - **Raktár** – **így kezdődik** – *24*

1. Válassza az **Alkalmazás** lehetőséget.
1. Jegyezze fel a megjelenő **Azonosítótábla** értékeket.

### <a name="over-pick-the-order-by-using-the-warehouse-management-mobile-app"></a>A rendelés előírtnál nagyobb mennyiségben való kitárolása a Warehouse Management mobilalkalmazás segítségével

1. Jelentkezzen be az *24*-es raktárban lévő felhasználóként a Raktárkezelés mobilalkalmazásba.
1. Lépjen a **Kimenő \> Értékesítési kitárolás** lehetőségre.
1. A **Munkaazonosító vagy azonosítótábla** beolvasása mezőbe írja be az értékesítési rendeléshez létrehozott munkaazonosítót.
1. Jelölje be az **OK** lehetőséget (pipa szimbólum).
1. Válassza ki az **Előírtnál nagyobb mennyiség kitárolása** lehetőséget.
1. Állítsa a **Mennyiség kitárolása** mezőt *14* értékre.
1. Jelölje be az **OK** lehetőséget (pipa szimbólum).

    A **Előírtnál nagyobb mennyiség kitárolása** oldalon a következő üzenet jelenik meg: "A sor túlszállítása 40,00 százalék, de az engedélyezett túlszállítás csak 10,00 százalék." Ez az üzenet azt jelzi, hogy a megadott kitárolási mennyiség meghaladja a túlszállítási korlátot. Az értékesítésirendelés-sor túlszállítási korlátja 10 százalék. Tehát egy 10 mennyiségű adott mennyiséghez csak 1-gyel több elemet lehet kitárolni tehát összesen 11-et.

1. Állítsa a **Mennyiség kitárolása** mezőt *11* értékre.
1. Jelölje be az **OK** lehetőséget (pipa szimbólum).
1. Az **Azonosítótábla** mezőben adja meg azt az azonosítótáblát, amelyet feljegyzett az előző szakaszban.
1. A **Cél azonosítótábla** mezőben adja meg a cél azonosítótáblát. Figyelje meg, hogy a kitárolási hely (*FLOOR-001*), a cikk (*A0001*) és a mennyiség (*11 db*) jelenik meg.
1. Jelölje be az **OK** lehetőséget (pipa szimbólum).
1. Tekintse át a **Beszerzési rendelések – Betárolás** oldalon látható információkat. A **Hely** mezőnek jeleznie kell, hogy a kitárolt cikkek a *RAKTÁRAJTÓ* helyre mennek.
1. Jelölje be az **OK** lehetőséget (pipa szimbólum).

A **Munkaazonosító/azonosítótábla azonosítójának beolvasása** oldalon egy „Munka elvégezve” üzenet jelenik meg. Ez az üzenet azt jelzi, hogy befejeződött az értékesítési rendelés munkaazonosítója, és az előírtnál nagyobb kitárolási mennyiség nem haladja meg a 10 százalékos túlszállítási korlátot.
