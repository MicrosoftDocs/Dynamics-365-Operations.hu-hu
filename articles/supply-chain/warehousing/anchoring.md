---
title: Horgonyzás
description: Ez a témakör bemutatja a lehorgonyzás engedélyezését és használatát.
author: GalynaFedorova
ms.date: 07/29/2021
ms.topic: article
ms.search.form: WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2021-07-29
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 8a0fa849f07f0cc0a41a663fc97b5aba927700b1
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8903811"
---
# <a name="anchoring"></a>Horgonyzás

[!include [banner](../includes/banner.md)]

Ez a cikk a lehorgonyozás folyamatának részletes adatait tartalmazza. Leírja a szükséges konfigurációt, valamint azt a logikát, amely akkor fut, amikor egy raktári dolgozó megváltoztatja vagy az előkészítő helyet, vagy a berakodási helyet.

A horgonyozás funkcióval felülbírálható az előkészítési vagy berakodási hely. A rendszer ezután minden nyitott berakodást az új bekészítési vagy berakodási helyre irányít.

Ez a funkció lehetővé teszi, hogy a dolgozók hatékonyabbak legyenek az áruk szállítása során. Íme néhány példa:

- Egy dolgozónak az 1. megrendelés cikkeit az 1. tároló előkészítő helyére kell tennie, de nem tudja elvégezni ezt a műveletet, mert egy előző rakományt a rendszer még nem törölt az adott helyről. Ahelyett, hogy arra várna, hogy az 1. tároló előkészítési helye felszabaduljon, a dolgozó dönthet úgy, hogy inkább a 2. tároló előkészítési helyét használja. Tehát a dolgozó felülírja a javasolt előkészítési helyet. A munka fennmaradó cikkeinek betárolási helyét a rendszer ekkor a 2. tároló előkészítési helyére frissíti.
- Egy dolgozónak, akinek több kitárolást kell végrehajtania ugyanahhoz a szállításhoz, meg lehet bizonyosodni arról, hogy minden berakodott cikk ugyanazon a helyen van összegyűjtve. Emiatt kevesebb idő szükséges a cikkek teherautóra rakodásához.

A mobileszköz menüelemekkel való lehorgonyzás a **Horgony** lehetőséggel konfigurálható. Ha ezt a lehetőséget *Igen* értékre állítja, a **Horgonyzó** mezőben meg kell adnia, hogy szállítmány vagy terhelés alapján szeretne horgonyozni. Ha a **Horgonyzó** mezőt *Szállítás* értékre állítja, a további nyitott berakodások az új helyre módosulnak a szállítmány esetében. Ha a *Berakodás* értékre állítja, a további nyitott berakodások az új helyre módosulnak a rakomány esetében.

> [!IMPORTANT]
> Az ezt követő nyitott berakodások helye csak az azonos munkasablonsorból létrehozott munkasorok esetén változik meg. Más szóval a rendszer lehorgonyozza az azonos munkasablonsorból származó rakodási sorokat.

Ez a témakör a lehorgonyzás működését mutatja be. A forgatókönyv során értékesítési rendelések készletét hozza létre, és mindegyiket kiadja a raktárba. Ezt követően felülbírálja a javasolt előkészítő helyet, és ellenőrzi, hogy az összes berakodási munka az új helyre van-e irányítva.

## <a name="scenario-prerequisite-make-demo-data-available"></a>Forgatókönyv előfeltétele: Bemutatóadatok elérhetővé tétele

A jelen cikkváltozat a Microsoft szabványos bemutatóadatában található értékekre és rekordokra hivatkozik Dynamics 365 Supply Chain Management. Ha azt szeretné, hogy az itt megadott értékeket használja a feladatok végrehajtásához, akkor győződjön meg róla, hogy olyan környezetben dolgozik, ahol a bemutatóadatokat telepítették, és a jogi személy beállítása legyen *USMF*.

## <a name="scenario-setup"></a>Eset beállítása

Mielőtt végighaladna a példaforgatókönyvön a horgonyzást engedélyezni kell a kapcsolódó mobileszköz menüelemhez.

### <a name="set-up-a-mobile-device-menu-item-to-enable-anchoring"></a>Mobileszköz-menüelem beállítása a bevételezett horgonyzáshoz

A következő lépések szerint engedélyezheti a mobileszköz menüelemének horgonyzását.

1. Lépjen a **Raktárkezelés \> Beállítás \> Mobileszköz \> Mobileszköz-menüelemek** részre.
1. A lista ablaktáblán válassza ki az *Értékesítési kitárolás* nevű rekordot. Ha nincs ilyen nevű rekord, hozza létre. Erősítse meg vagy állítsa be a következő értékeket a rekordhoz:

    - **Menüpont neve:** *Értékesítési kitárolás*
    - **Cím:** *Értékesítési kitárolás*
    - **Mód:** *Munka*
    - **Meglévő munka használata:** *Igen*
    - **Irányítja:** *Felhasználó által irányított*
    - **Horgonyzás:** *Igen*

        Ezen beállítás hatására a rendszer az értékesítési kitárolás során több munkarendeléssort fog horgonyozni.

    - **Horgonyzó**: *Rakomány*

        Ez a beállítás a rendszerben rakomány szerinti horgonyzást okoz.

    - **Cél azonosítótábla felülbírálata:** *Igen*
    - **Az azonosító tábla felülbírálata berakodáskor:** *Igen*
    - **A munka zárolva tartása a felhasználó által:** *Igen*
    - **Az előírtnál nagyobb mennyiség kitárolásának engedélyezése:** *Igen*

### <a name="set-up-a-work-template-to-enable-staging"></a>Munkasablon beállítása az előkészítés engedélyezéséhez

A következő lépések szerint konfigurálhatja a munkasablont az előkészítés engedélyezéséhez. Ez a konfiguráció azt a forgatókönyvet támogatja, amikor egy dolgozó egy rendelés cikkét egy előkészítési helyre helyezi.

1. Lépjen a **Raktárkezelés \> Beállítás \> Munka \> Munkasablonok** elemre.
1. A **Munkarendelés típusa** mezőben válassza ki az *Értékesítési rendelések* elemet.
1. A rácsban válassza ki a **61 SO Állapotsor** munkasablont.
1. A **Munkasablon részletei** szakaszban győződjön meg arról, hogy léteznek a következő sorok, és konfigurálva vannak az itt látható módon:

    - 1. sor:

        - **Munka típusa:** *Kitárolás*
        - **Kötelező:** Kiválasztva (= *Igen*)
        - **Munkaosztály azonosítója:** *SO Pick*

    - 2. sor:

        - **Munka típusa:** *Eltárolás*
        - **Kötelező:** Kiválasztva (= *Igen*)
        - **Irányelvkód:** *Előkészítés*
        - **Munkaosztály azonosítója:** *SO Pick*

    - 3. sor:

        - **Munka típusa:** *Kitárolás*
        - **Kötelező:** Kiválasztva (= *Igen*)
        - **Munka leállítása:** *Igen*
        - **Munkaosztály azonosítója:** *SO rakodás*

    - 4. sor:

        - **Munka típusa:** *Eltárolás*
        - **Kötelező:** Kiválasztva (= *Igen*)
        - **Irányelvkód:** *Raktárajtó*
        - **Munkaosztály azonosítója:** *SO rakodás*

1. A műveleti ablaktáblán válassza a **Lekérdezés szerkesztése** lehetőséget a lekérdezésszerkesztő megnyitásához.
1. Győződjön meg arról, hogy a **Tartomány** lapon a következő két sor jelen van:

    - **Tábla:** *Ideiglenes munkatranzakciók*
    - **Származtatott tábla:** *Ideiglenes munkatranzakciók*
    - **Mező:** *Raktár*
    - **Feltételek:** *61*

1. Győződjön meg arról, hogy a **Rendezés** lapon a következő két sor jelen van:

    - **Tábla:** *Ideiglenes munkatranzakciók*
    - **Származtatott tábla:** *Ideiglenes munkatranzakciók*
    - **Mező:** *Szállítmány azonosítója*
    - **Keresés iránya:** *Növekvő*

1. Az **OK** gombra kattintva alkalmazza a beállításokat, és zárja be a lekérdezésszerkesztőt. Fogadja el a módosításokat, ha a rendszer kéri.
1. A Műveleti ablaktáblán kattintson a **Munkafejléc-törések** elemre.
1. Ügyeljen arra, hogy a **Csoportosítás ezen mező szerint** jelölőnégyzet be legyen jelölve abban a sorban, amelyen a **Mezőnév** mező be van állítva a *szállítmány azonosítójára*.

### <a name="set-up-license-plates-locations-and-inventory"></a>Az azonosítótáblák, helyek és készlet beállítása

Az értékesítési rendelések és szállítmányok létrehozása előtt meg kell győződnie arról, hogy léteznek a szükséges helyek, azonosítótáblák és készlet.

1. Menjen a **Raktárkezelés \> Beállítások \> Raktár \> Azonosítótáblák** helyre, és hozzon létre két azonosítótáblát:

    - MyLP1
    - MyLP2

1. Menjen a **Raktárkezelés \> Beállítások \> Raktár \> Helyek** menübe, és hozza létre a következő helyeket, ha még nem létezik.

    | Raktár | Helyszín   | Hely profilazonosítója | Zóna azonosítója   |
    |-----------|------------|---------------------|-----------|
    | 61        | 06A01R2S1B | PICK-06             | SZINT     |
    | 61        | 06A01R3S1B | PICK-06             | SZINT     |
    | 61        | STAGE01    | ELŐKÉSZÍTÉS               | *(Üres)* |
    | 61        | STAGE02    | ELŐKÉSZÍTÉS               | *(Üres)* |
    | 61        | STAGE03    | ELŐKÉSZÍTÉS               | *(Üres)* |
    | 61        | STAGE04    | ELŐKÉSZÍTÉS               | *(Üres)* |

1. Ellenőrizze, hogy a következő készlet elérhető-e. Ha módosítania kell a készletet, akkor manuális mozgásokat hozhat létre, felhasználhatja a feltöltést, vagy bármilyen egyéb folyamatot alkalmazhat.

    | Cikkszám | Mennyiség | Raktár | Helyszín   | Azonosítótábla |
    |-------------|----------|-----------|------------|---------------|
    | A0001       | 100      | 61        | 06A01R2S1B | MyLP1         |
    | A0002       | 100      | 61        | 06A01R3S1B | MyLP2         |

### <a name="create-demand"></a>Igény létrehozása

A horgonyzás funkció kipróbálása előtt létre kell hoznia igényt. Ebben a forgatókönyvben három értékesítési rendelést hoz létre ugyanannak a vevőnek.

1. Ugorjon az **Értékesítés és marketing \> Értékesítési rendelések \> Minden értékesítési rendelés** pontra.
1. Az első értékesítési rendelés létrehozásához kattintson az **Új** elemre.
1. Az **Értékesítési rendelés létrehozása** párbeszédpanelen adja meg a következő értékeket:

    - **Vevőkód** *US-001*
    - **Raktár:** *61*

1. Válassza ki az **OK** lehetőséget.
1. A program megnyitja az új értékesítési rendelést. Tartalmaz egy üres sort az **Értékesítési rendelés sorai** gyorslapon. A következő értékeket állítsa be ehhez a sorhoz:

    - **Cikkszám:** *A0001*
    - **Mennyiség:** *1*

1. Az eszközsoron válassza a **Sor hozzáadása** lehetőséget egy második értékesítési rendelési sor hozzáadásához, és állítsa be a következő értékeket:

    - **Cikkszám:** *A0002*
    - **Mennyiség:** *1*

1. A következő lépéseket végezz el a rendelés minden értékesítési sorához, hogy készletet foglaljon azokhoz:

    1. Az **Értékesítési rendeléssorok** gyorslapon válasszon ki egy értékesítésirendelés-sort.
    1. Válassza az eszköztár **Készlet \> Foglalás** lehetőségét.
    1. A **Foglalás** lapon válassza ki az **Adag foglalása** elemet, majd zárja be az oldalt.
    1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.

1. A második értékesítési rendelés létrehozásához ismételje meg a 2–6. lépést. A következő értékeket állítsa be hozzá:

    - Az **Értékesítési rendelés létrehozása** párbeszédpanelen:

        - **Vevőkód** *US-001*
        - **Raktár:** *61*

    - 1. értékesítésirendelés-sorban:

        - **Cikkszám:** *A0001*
        - **Mennyiség:** *2*

    - 2. értékesítésirendelés-sorban:

        - **Cikkszám:** *A0002*
        - **Mennyiség:** *2*

1. Ismételje meg a 7. lépést a 2. értékesítési rendelés minden sorának foglalásához.
1. A harmadik értékesítési rendelés létrehozásához ismételje meg a 2–6. lépést. A következő értékeket állítsa be hozzá:

    - Az **Értékesítési rendelés létrehozása** párbeszédpanelen:

        - **Vevőkód** *US-001*
        - **Raktár:** *61*

    - 1. értékesítésirendelés-sorban:

        - **Cikkszám:** *A0001*
        - **Mennyiség:** *3*

    - 2. értékesítésirendelés-sorban:

        - **Cikkszám:** *A0002*
        - **Mennyiség:** *3*

1. Ismételje meg a 7. lépést a 3. értékesítési rendelés minden sorának foglalásához.

### <a name="use-the-load-planning-workbench-to-create-a-load-and-release-it-to-the-warehouse"></a>A rakománytervezési munkaterület használata a rakomány létrehozásához és kiadásához a raktárba

A következő lépések végrehajtásával terhelést hozhat létre az a rendelésekhez, amelyeket ehhez az esethez készített, majd kiadhatja azt a raktárnak.

1. Ugorjon a **Raktárkezelés \> Rakományok \> Rakománytervező munkaterület** elemre.
1. Az **Értékesítési sorok** lapon keresse meg és válassza ki az 1. és a 2. értékesítési rendelés összes értékesítésirendelés-sorát.
1. A műveleti ablaktáblán a **Kínálat és kereslet** lapon, a **Hozzáadás** csoportban válassza az **Új rakományba** elemet.
1. A **Rakománysablon hozzárendelése** párbeszédablakban a **Rakománysablon azonosítója** mezőben válassza ki a rakománysablont, pl. a *Normál rakománysablon* elemet.
1. Az **OK** gombbal zárja be a párbeszédpanelt.
1. A **Rakomány** szakaszban keresse meg és válassza ki a létrehozott rakományt.
1. Az eszközsoron válassza a **Kiadás \> Raktárba való kiadás** lehetőséget.
1. A kiválasztott rakomány raktárba történő kiadásához nyomja meg a **Rakomány kiadása a raktárba** párbeszédablakon az **OK** gombot.
1. Ugorjon a **Raktárkezelés \> Munka \> Minden munka** elemre a létrehozott munka megtekintéséhez. Két új munkaazonosító látható, egy-egy az egyes szállítmányokhoz. Minden munkaazonosítónak vannak kitárolási és betárolási sorai, amelyek a készletet a kitárolási helyekről az előkészítő helyre, illetve az előkészítő helyről az átmeneti helyre hozzák létre. Jegyezze fel a **Munkaazonosító** értékét az első szállítmányhoz, mert a következő eljárásban is szüksége lesz rá.

### <a name="sales-order-picking-to-the-staging-location-for-the-first-shipment"></a>Értékesítési rendelés kitárolása az első szállítmány előkészítő helyére

1. Jelentkezzen be az *61*-es raktárban lévő dolgozóként a Warehouse Management mobilalkalmazásba. (A normál demóadatokban _61_ felhasználó azonosító és az _1_ jelszó használatával jelentkezzen be.)
1. Válassza a főmenü **Kimenő** elemét.
1. Válassza a **Kimenő** menü **Értékesítési kitárolás** elemét.
1. Válassza ki az **Azonosító** mezőt, majd írja be a munkaazonosítót az első szállítmányhoz.
1. Hagyja jóvá a bejegyzést.
1. Az **LP** mezőben adja meg az első cikk (*MyLP1*) sorozatszámát.
1. Hagyja jóvá a bejegyzést.
1. A **Cél AT** mezőbe írjon be tetszőleges számot (a cél azonosítótáblák nem kell még léteznie).

    A feldolgozott hullámban létrehozott összes sort ugyanarra a cél azonosítótáblára tárolja ki.

1. Hagyja jóvá a bejegyzést.
1. Az **LP** mezőben adja meg a második cikk (*MyLP2*) sorozatszámát.
1. Hagyja jóvá a bejegyzést.

    Tegyük fel, hogy a dolgozó összegyűjtötte a rendelést, de amikor a munkában megadott előkészítő helyre jut, úgy találja, hogy a hely már foglalt. A dolgozó azonban láthatja, hogy egy másik közeli hely (*STAGE03)* is elérhető. Ezért az előkészítő hely módosítását kéri. Mivel engedélyezve van a horgonyzás funkció, a rendszer automatikusan frissíti ennek és az összes kapcsolódó munkának az előkészítési helyét.

1. Válassza a **Hely felülbírálása** lehetőséget a javasolt előkészítési hely felülbírálatához.
1. A **Munkakivételek** mezőjében adja meg a *Módosított előkészítési sávot*.
1. A **Hely** mezőben adjon meg egy új előkészítő helyet (*STAGE03*).
1. Hagyja jóvá a bejegyzést. A „Munka befejezve” üzenet jelenik meg.
1. Ugorjon a **Raktárkezelés \> Munka \> Minden munka** pontra.
1. Az első szállítmány munkaazonosítóját nyissa meg. Ellenőrizze, hogy az előkészítő hely frissítve lett-e a mobileszköz által meghatározott új helyre (*STAGE03*).
1. A második szállítmány munkaazonosítóját nyissa meg. A horgonyzás beállítása miatt ellenőrizze, hogy az előkészítő hely át lett-e állítva új előkészítő helyre (*STAGE03*).

> [!NOTE]
> A rendszer frissíti az új helyre az ugyanannak a munkasablonsornak az alapján létrehozott összes nyitott berakodott munkasornak azt a helyét, amelyek előkészítő helye ugyanez.

### <a name="use-the-load-planning-workbench-to-add-the-new-sales-order-to-the-existing-load"></a>A rakománytervezési munkaterület használatával adja hozzá az új értékesítési rendelést a meglévő rakományhoz

A következő lépések szerint adhatja hozzá a rendelést a rakományhoz, majd adhatja ki a raktárba.

1. Ugorjon a **Raktárkezelés \> Rakományok \> Rakománytervező munkaterület** elemre.
1. Az **Értékesítési sorok** lapon keresse meg és válassza ki a 3. értékesítési rendelés összes értékesítésirendelés-sorát.
1. A művelet ablaktábla **Kereslet és kínálat** lapján válassza a **Hozzáadás** csoportban a **Meglévő rakományhoz** lehetőséget, amellyel a kiválasztott rendelési sorokat meglévő rakományhoz adhatja.
1. Az **OK** gombbal zárja be a párbeszédpanelt.
1. A **Rakományok** szakaszban keresse meg és válassza ki a rakományt az előző lépésekből.
1. Válassza a **Kiadás \> Raktárba való kiadás** lehetőséget.
1. A kiválasztott rakomány raktárba történő kiadásához nyomja meg a **Rakomány kiadása a raktárba** párbeszédablakon az **OK** gombot.
1. Ugorjon a **Raktárkezelés \> Munka \> Minden munka** elemre a létrehozott munka megtekintéséhez. Jegyezze fel a **Munkaazonosító** értékét, mert a következő eljárásban is szüksége lesz rá.

### <a name="sales-order-picking-to-the-staging-location-for-the-third-shipment"></a>Értékesítési rendelés kitárolása a harmadik szállítmány előkészítő helyére

1. Jelentkezzen be a *61*-es raktárba felhasználóként a mobileszközön.
1. Válassza a főmenü **Kimenő** elemét.
1. Válassza a **Kimenő** menü **Értékesítési kitárolás** elemét.
1. Válassza ki az **Azonosító** mezőt, majd írja be a munkaazonosítót a harmadik szállítmányhoz.
1. Hagyja jóvá a bejegyzést.
1. Az **LP** mezőben adja meg az első cikk (*MyLP1*) sorozatszámát.
1. Hagyja jóvá a bejegyzést.
1. A **Cél AT** mezőbe írjon be tetszőleges számot (a cél azonosítótáblák nem kell még léteznie).
1. Hagyja jóvá a bejegyzést.
1. Az **LP** mezőben adja meg a második cikk (*MyLP2*) sorozatszámát.
1. Hagyja jóvá a bejegyzést.

    Az első rakománynál tegyük fel, hogy a dolgozó úgy találja, hogy a megadott előkészítési hely nem érhető el. Emiatt másik előkészítő helyet (*STAGE04*) szeretne használni.

1. Válassza a **Hely felülbírálása** lehetőséget a javasolt előkészítési hely felülbírálatához.
1. A **Munkakivételek** mezőjében adja meg a *Módosított előkészítési sávot*.
1. A **Hely** mezőben adjon meg egy új előkészítő helyet (*STAGE04*).
1. Hagyja jóvá a bejegyzést. A „Munka befejezve” üzenet jelenik meg.
1. Ugorjon a **Raktárkezelés \> Munka \> Minden munka** pontra.
1. Az első szállítmány munkaazonosítóját nyissa meg. Győződjön meg róla, hogy az előkészítő hely nem lett frissítve az új előkészítő helyre (*STAGE04*), mert a fennmaradó nyitott berakodási sor nem felel meg a befejezett be berakodási sor munkasablonsorának.
1. A második szállítmány munkaazonosítóját nyissa meg. Győződjön meg róla, hogy az előkészítő hely nem lett frissítve az új előkészítő helyre (*STAGE04*), mert a fennmaradó előkészítési hely nem felel meg a befejezett berakodási sor előkészítési helyének. Más szóval a befejezett berakodott munkasornak és a fennmaradó nyitott munkasornak különböző előkészítési helyei vannak, és ebben az esetben csak az azonos előkészítő helyekkel rendelkező sorok frissülnek.
1. A harmadik szállítmány munkaazonosítóját nyissa meg. Ellenőrizze, hogy az előkészítő hely át lett-e állítva új előkészítő helyre (*STAGE04*).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
