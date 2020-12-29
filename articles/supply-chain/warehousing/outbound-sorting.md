---
title: Kimenő rendezés
description: Ez a témakör a kimenő rendezéssel kapcsolatban tartalmaz információkat. Ez a funkció megkönnyíti a kis tárolók kezelését, és segíti a raktári dolgozóknak a raklap-kapacitás jobb rendezését a kamionban.
author: Mirzaab
manager: tfehr
ms.date: 07/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSPack, WHSOutboundSortTemplate, WHSOutboundSortPositionAssignments, WHSLocationType, WHSLoactionProfile
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-15
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: 84c4ec83ed16762e6c3c1a22425cf60e5b3ae8da
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/16/2020
ms.locfileid: "4429938"
---
# <a name="outbound-sorting"></a>Kimenő rendezés

[!include [banner](../includes/banner.md)]

Ez a funkció megkönnyíti a kis tárolók kezelését, és segíti a raktári dolgozóknak a raklap-kapacitás jobb rendezését a kamionban. Ha a kimenő rendezést használja, akkor a csomagolt tárolókat a megfelelő raklapra rendezheti, miután áthaladtak a csomagolóállomáson. A csomagolási hierarchiát is létre lehet hozni.

Ez a funkció lehetővé teszi raklapok összeállítását a csomagolási funkcióval csomagolt tárolókból. A tároló nem lesz elküldve a végső szállítási helyre, mivel az eredeti csomagolási folyamatban van. Helyette a dolgozók le tudják zárni a tárolót, és át lehet helyezni egy rendezés típusú helyre. Ezután a konténereket a pozíciókra rendezhetik, amelyek mindegyikének van egy azonosítótáblája (AT). Miután a tárolók rendezése megtörtént, a munka létrehozható úgy, hogy az egész azonosítótáblát elküldje a végső szállítási dokknak vagy fázishelyeknek a helyutasítások vagy a saját követelményei alapján. Ezenkívül a rendezési pozíció lezárásának művelete azonnal áthelyezheti a készletet a végső szállítási helyre, és kitárolhatja a rendelésbe.

## <a name="turn-on-the-outbound-sorting-feature"></a>A Kimenő rendezés funkció bekapcsolása

A funkció használata előtt be kell azt kapcsolnia saját rendszerében. A rendszergazdák használhatják a [Funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) munkaterületet a funkció állapotának ellenőrzéséhez, és szükség esetén bekapcsolásához. A funkció a következő módon jelenik meg:

- **Modul:** *Raktárkezelés*
- **Szolgáltatás neve:** *Kimenő rendezés*

## <a name="setup"></a>Beállítás

Ehhez a helyzethez normál **USMF** demóadatokat és a *62-es* raktárat kell használni. A következő alszakaszokban ismertetett beállításokat is végre kell hajtania.

### <a name="set-up-a-wave-template"></a>Állítsa be a hullámsablon lehetőséget

Ez a beállítás automatikusan feldolgozza a hullámot és létrehozza a munkát, valahányszor egy sor kiadásra kerül a raktárba.

1. Ugorjon a **Raktárkezelés \> Beállítás \> Hullámok \> Hullámsablonok** pontra.
1. A sablonban válassza ki a **62-es raktárat**.
1. Győződjön meg arról , hogy az **Általános** gyorslapon a **Hullám feldolgozása a raktárba történő kiadáskor** beállítás értéke *Igen* legyen.

### <a name="set-up-a-worker"></a>Dolgozó beállítása

A csomagoló állomás helynek számít. Azok a raktári dolgozók, akik bejelentkeznek a csomagolóállomáson, csak az adott csomagolási helyen tervezett szállítmányokat és tárolókat láthatják, és csak azokon dolgoznak. Azt a felhasználót, aki bejelentkezik a Microsoft Dynamics 365-be dolgozóként kell beállítani a Raktárkezelés modulban. Ha a felhasználó neve nem jelenik meg a dolgozó felhasználók listájában, a következő eljárással adja hozzá.

> [!NOTE]
> A lépések feltételezik, hogy a felhasználó már létezik a rendszerben, és a **Humán erőforrás** modulban alkalmazottként vagy dolgozóként van társítva.

1. Ugrás a **Raktárkezelés \> Beállítás \> Dolgozó** elemre.
1. Válassza az **Új** lehetőséget.
1. A **Dolgozó** mezőben válassza ki a célfelhasználót az alkalmazottak listájából.
1. Válassza ki a **Kiválasztás** lehetőséget.
1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.
1. A **Felhasználók** gyorslap **Új** elemét választva, hozzon létre egy mobileszköz-fiókot, majd állítsa be a következő értékeket:

    - **Felhasználó azonosítója:** Adjon meg egy egyedi azonosítót.
    - **Felhasználónév:** Adja meg az azonosító nevét.
    - **Alapértelmezett raktár:** *62*
    - **Menü neve:** *Fő*

1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.
1. Megjelenik a **Jelszó beállítása** párbeszédpanel, amelyen létrehozhatja azt az egyszerű jelszót, amellyel a felhasználó bejelentkezhet a mobilalkalmazásba. Adja meg az alábbi értékeket:

    - **Jelszó:** Adjon meg egy egyszerű jelszót.
    - **Jelszó megerősítése:** Adja meg újra ugyanazt a jelszót.

1. Válassza ki a **Jelszó beállítása** opciót.

    A Műveletközpont értesítése tájékoztatja arról, hogy a jelszó be van állítva a létrehozott felhasználóhoz.

### <a name="create-a-location-type"></a>Helytípus létrehozása

1. Ugorjon a **Raktárkezelés \> Beállítás \> Raktár \> Helytípusok** pontra.
1. A műveleti ablaktáblán válassza az **Új** parancsot egy helytípus létrehozásához, és állítsa be a következő értékeket hozzá:

    - **Hely típusa:** *SORT*
    - **Leírás:** *Rendezés*

1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.

### <a name="set-up-warehouse-management-parameters"></a>Raktárkezelési paraméterek beállítása

1. Lépjen a **Raktárkezelés \> Beállítás \> Raktárkezelési paraméterek** részre.
1. Az **Általános** lap **Helytípusok** gyorslapján állítsa be a **Rendezési hely típusa** mezőt *SORT* értékre.
1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.

### <a name="set-up-a-location-profile"></a>Helyprofil beállítása

1. Ugorjon a **Raktárkezelés \> Beállítás \> Raktár \> Helyprofilok** pontra.
1. A Műveleti ablaktáblán kattintson az **Új** elemre.
1. A fejlécben állítsa be a következő értékeket:

    - **Helyprofil azonosítója:** *Rendezés*
    - **Név:** *Rendezés*

1. Az **Általános** gyorslapon állítsa be a következő értékeket:

    - **Hely formátuma:** *ASRB* (folyosó, állvány, polc és rekesz)
    - **Hely típusa:** *SORT*
    - **Azonosítótábla-követés használata:** *Igen*
    - **Vegyes cikkek engedélyezése:** *Igen* (a beállítás *Igen* értékre állítása esetén a **Vegyes készlet kötegek engedélyezése** beállítás automatikusan *Igen* értékre van állítva, és nem lehet függetlenül módosítani.)

1. Válassza a **Mentés** lehetőséget.

### <a name="set-up-a-location"></a>Hely beállítása

1. Ugorjon a **Raktárkezelés \> Beállítás \> Raktár \> Helyek pontra**.
1. A fejlécben törölje a jelet az **Ellenőrző számjegyek létrehozása a helyhez** jelölőnégyzetből.
1. A műveleti ablaktáblán válassza az **Új** parancsot egy hely létrehozásához, és állítsa be a következő értékeket hozzá:

    - **Raktár:** *62*
    - **Hely:** *SORT*
    - **Helyprofil azonosítója:** *SORTING*

1. Válassza a **Mentés** lehetőséget.

### <a name="set-up-an-outbound-sorting-template"></a>Kimenő rendezési sablon beállítása

A kimenő rendezési sablon határozza meg, hogy a munka a rendezési hely alapján jön-e létre, és hogy a rendezés kézzel vagy automatikusan történik-e.

Ehhez a forgatókönyvhöz létrehoz egy kimenő rendezési sablont, amely a raklapok összekészítéséhez szükséges a csomagolási állomás után.

1. Ugorjon a **Raktárkezelés \> Beállítás \> Csomagolás \> Kimenő rendezési sablonok** helyre.
1. A Műveleti ablaktáblán kattintson az **Új** elemre.
1. Az új sablon fejlécében adja meg a következő értékeket:

    - **Kimenő rendezési sablon azonosítója:** *AutoWork*
    - **Leírás:** *Automatikus munkalétrehozás*
    - **Kimenő rendezési sablon típusa:** *Tároló*
    - **Raktár:** *62*
    - **Hely:** *SORT*

1. Az **Általános** gyorslapon állítsa be a következő értékeket:

    - **Rendezés ellenőrzés:** *Pozíció beolvasása*
    - **Munka létrehozása a pozíció lezárásakor:** *Igen*

        Ha ennek a beállításnak az értéke *Igen* akkor munka jön létre, amikor a pozíció le van zárva, hogy a készletet a végső szállítási helyre mozgassák. Ha *Nem* értékre van állítva, akkor a készletet azonnal kitárolják a rendeléshez a pozíció lezárásakor.

    - **Pozíció hozzárendelése:** *Automatikus*

        Ha a mező értéke *Manuális* akkor a felhasználónak mindig meg kell adnia, a készlet melyik pozíciójához kell rendezni. Ha értéke *Automatikus*, akkor a rendszer automatikusan egy pozícióhoz irányítja a készletet, ha lehetséges, a rendezési sablontörések alapján.

1. Válassza a **Mentés** parancsot, hogy a **Lekérdezés szerkesztése** gomb elérhető legyen a Műveleti panelen.
1. A műveleti ablaktáblán válassza a **Lekérdezés szerkesztése** lehetőséget.
1. A lekérdezés-szerkesztőben, a **Rendezés** lapon adjon hozzá egy sort a következő értékekkel:

    - **Tábla:** *Szállítmányok*
    - **Származtatott tábla:** *Szállítmányok*
    - **Mező:** *Szállítmányozói szolgáltatás*

        Amikor kiválasztotta ezt az értéket, a következő üzenet jelenhet meg: „A Szállítmányozói szolgáltatás nem egy indexmező. Szeretne rendezést hozzáadni?” Válassza ki az **Igen** lehetőséget.

    - **Keresés iránya:** *Növekvő*

1. Válassza ki az **OK** lehetőséget.
1. A következő üzenet jelenhet meg: „A csoportosítás alaphelyzetbe kerül, folytatja?” Válassza ki az **Igen** lehetőséget.

    Elérhetővé válik a **A kimenő rendezési sablonok szünetei** gomb a műveleti panelen.

1. A műveleti ablaktáblán válassza ki a **Kimenő rendezési sablon szünetekei** lehetőséget.
1. Az **Kimenő rendezési kritérium** párbeszédpanelen adja meg a következő értékeket:

    - **Hivatkozási tábla neve:** *Szállítmányok*
    - **Hivatkozási mező neve:** *Szállítmányozó szolgáltatás*
    - **Csoportosítás mező szerint:** Jelölje be ezt a jelölőnégyzetet, ha a szállításokat szállítmányozó szolgáltatás szerint szeretné csoportosítani.

1. Az **OK** gombra kattintva mentse a beállításokat, és zárja be a párbeszédpanelt.

### <a name="set-up-container-packing-policies"></a>Konténerek csomagolási házirendjeinek beállítása

1. Ugorjon a **Raktárkezelés \> Beállítás \> Tárolók \> Tárolócsomagolási házirendek** pontra.
1. A Műveleti ablaktáblán kattintson az **Új** elemre.
1. Az új házirend fejlécében adja meg a következő értékeket:

    - **Konténer csomagolási irányelve:** *Rendezés*
    - **Leírás:** *Rendezés*

1. Az **Áttekintés** gyorslapon állítsa be a következő értékeket:

    - **Raktár:** *62*
    - **A rendezés alapértelmezett helye:** *SORT*
    - **Tömegegység:** *kg*
    - **Tároló záró irányelve:** *Automatikus kiadás*
    - **Tároló felszabadítási irányelve:** *Tároló hozzárendelése a kimenő rendezési pozícióhoz*

1. Válassza a **Mentés** lehetőséget.

### <a name="set-up-packing-profiles"></a>Csomagolási profilok beállítása

Hozzon létre egy új csomagolási profilt, amelyet a rendezési funkcióval együtt használni fog.

1. Ugorjon a **Raktárkezelés \> Beállítás \> Csomagolás \> Csomagolási profilok** pontra.
1. A műveleti ablaktáblán válassza az **Új** parancsot egy sor létrehozásához, és állítsa be a következő értékeket hozzá:

    - **Csomagolási profil azonosítója:** *Rendezés*
    - **Leírás:** *Rendezés*
    - **Konténer csomagolási irányelve:** *Rendezés*
    - **Tároló-azonosító mód:** *Automatikus*
    - **Tároló típusa:** *Nagyméretű doboz*
    - **Tároló automatikus létrehozása a tároló lezárásakor:** Törölve (= *Nem*)

1. Válassza a **Mentés** lehetőséget.

### <a name="set-up-work-classes"></a>Munkaosztályok beállítása

A rendezéssel együtt használt munkaosztály beállítása.

1. Ugorjon a **Raktárkezelés \> Beállítás \> Munka \> Munkaosztályok** pontra.
1. A műveleti ablaktáblán válassza az **Új** parancsot egy munkaosztály létrehozásához a rendeléshez, és állítsa be a következő értékeket hozzá:

    - **Munkaosztály azonosítója:** *Rendezés*
    - **Leírás:** *Rendezés*
    - **Munkarendelés típusa:** *Rendezett készletkitárolás*

1. Válassza a **Mentés** lehetőséget.

### <a name="set-up-mobile-device-menu-items"></a>Mobileszköz-menüelemek beállítása

#### <a name="set-up-a-new-pallet-menu-item"></a>Új raklap menüelem beállítása

Hozzon létre egy mobileszköz menüelemet, amely a rendezés során felépíti a raklapokat.

1. Lépjen a **Raktárkezelés \> Beállítás \> Mobileszköz \> Mobileszköz-menüelemek** részre.
1. A Műveleti ablaktáblán kattintson az **Új** elemre.
1. A fejlécben állítsa be a következő értékeket:

    - **Menüelem neve:** *Raklap-összeállítás*
    - **Cím:** *Raklap-összeállítás*
    - **Mód:** *Közvetett*
    - **Meglévő munka használata:** *Nem*

1. Az **Általános** gyorslapon állítsa be a következő értékeket:

    - **Tevékenységkód:** *Kimenő rendezés*

        Ha ez a mező *Kimenő rendezés* értékre van állítva, akkor a **Kimenő rendezési sablon azonosítója** mező jelenik meg.

    - **Folyamat-útmutató használata:** *Igen*

        Ha a **Tevékenységkódja** mező a *Kimenő rendezés* értékre van állítva , akkor ez a beállítás automatikusan *Igen* értékre van állítva.

    - **Kimenő rendezési sablon azonosítója:** *AutoWork*

1. Válassza a **Mentés** lehetőséget.

#### <a name="set-up-a-new-loading-menu-item"></a>Új rakodási menüelem beállítása

Ezután hozzon létre egy menüelemet, amely lehetővé teszi, hogy a felhasználók a kiválasztott készletcikkeket áthelyezzék a szállítási helyre.

1. Lépjen a **Raktárkezelés \> Beállítás \> Mobileszköz \> Mobileszköz-menüelemek** részre.
1. A Műveleti ablaktáblán kattintson az **Új** elemre.
1. A fejlécben állítsa be a következő értékeket:

    - **Menüelem neve:** *Rakomány rendezésből*
    - **Cím:** *Rakomány rendezésből*
    - **Mód:** *Munka*
    - **Meglévő munka használata:** *Igen*

1. Az **Általános** gyorslapon az **Irányító** mezőt *Felhasználó által irányított* értékre kell beállítani.
1. Válassza a **Munkaosztályok** gyorslap **Új** elemét, majd állítsa be a következő értékeket:

    - **Munkaosztály azonosítója:** *SORT*
    - **Munkarendelés típusa:** *Rendezett készletkitárolás*

1. Válassza a **Mentés** lehetőséget.

### <a name="set-up-the-mobile-device-menu"></a>A Mobileszköz-menü beállítása

Ezután az új menüelemeket fel kell venni a mobileszköz menüjébe.

1. Lépjen a **Raktárkezelés \> Beállítás \> Mobileszköz \> Mobileszköz menü** elemre.
1. Válassza ki a **Kimenő** menüt.
1. A műveleti ablaktáblán válassza a **Szerkesztés** lehetőséget.
1. A **Választható menük és menüelemek** oszlopban keresse meg és válassza ki a **Raklap-összeállítás** lehetőséget.
1. Válassza a jobbra mutató nyilat a **Raklap-összeállítás** áthelyezéséhez a **Menü struktúrája** oszlopba.
1. A fel és a le nyílgombokkal helyezheti a **Raklap összeállítása** menü elemet a mobileszköz menü kívánt pozíciójába.
1. Válassza a **Mentés** lehetőséget.
1. Ennek az eljárásnak a megismétlésével adja hozzá a **Rakomány rendezésből** menü elemet a **Kimenő** menübe.

### <a name="set-up-location-directives"></a>Helyutasítások beállítása

A *helyutasítások* olyan szabályok, amik segítik a kitárolási és betárolási helyek meghatározását, készletmozgatás esetében. Ekkor létre kell hoznia egy szabályt a rendezési munka kezeléséhez.

#### <a name="set-up-a-single-sku-directive"></a>Egyetlen Termékváltozatirányelv beállítása

1. Ugrás a **Raktárkezelés \> Beállítás \> Helyutasítások** elemre.
1. A bal oldali ablaktáblában módosítsa a **Munkarendelés típusa** mezőt *Rendezett készletkitárolás* értékre.
1. A Műveleti ablaktáblán kattintson az **Új** elemre.
1. A fejlécben állítsa be a következő értékeket:

    - **Sorozat:** *1*
    - **Név:** *Baydoor*

1. A **Helyutasítások** gyorslapon állítsa be a következő értékeket:

    - **Munka típusa:** *Eltárolás*
    - **Telephely:** *6*
    - **Raktár:** *62*
    - **Több termékváltozat:** *Nem*

1. A **Mentés** gombra kattintva elérhetővé válik a **Sorok** gyorslap az eszköztáron.
1. Válassza a **Sorok** gyorslap **Új** elemét, majd állítsa be a következő értékeket az új soron: Az összes többi mezőben hagyja meg az alapértelmezett értékeket.

    - **Sorozat:** *1*
    - **Kezdet:** *0*
    - **Befejezés:** *1 000 000*

1. A **Mentés** gombra kattintva elérhetővé válik a **Helyutasítási műveletek** gyorslap az eszközsoron.
1. Válassza a **Helyutasítás-műveletek** gyorslap **Új** elemét, majd állítsa be a következő értékeket az új soron: Az összes többi mezőben hagyja meg az alapértelmezett értékeket.

    - **Sorozat:** *1*
    - **Név:** *Baydoor*

1. Válassza a **Mentés** lehetőséget.
1. A **Helyutasítás műveletei** gyorslapon válassza a **Lekérdezés szerkesztése** lehetőséget.
1. A lekérdezési szerkesztő **Tartomány** lapján keresse meg azt a sort, amelynél a **Mező** mező értéke *Hely*. Ennek a sornak a **Feltételek** mezőjét állítsa *Baydoor* értékre.
1. Az **OK** gombra kattintva mentse a beállításokat, és zárja be a lekérdezésszerkesztőt.

#### <a name="set-up-a-multiple-sku-directive"></a>Egyetlen több termékváltozatirányelv beállítása

1. Ugrás a **Raktárkezelés \> Beállítás \> Helyutasítások** elemre.
1. A bal oldali ablaktáblában módosítsa a **Munkarendelés típusa** mezőt *Rendezett készletkitárolás* értékre.
1. A Műveleti ablaktáblán kattintson az **Új** elemre.
1. A fejlécben állítsa be a következő értékeket:

    - **Sorozat:** *2*
    - **Név:** *Baydoor Multi*

1. A **Helyutasítások** gyorslapon állítsa be a következő értékeket:

    - **Munka típusa:** *Eltárolás*
    - **Telephely:** *6*
    - **Raktár:** *62*
    - **Több termékváltozat:** *Igen*

1. A **Mentés** gombra kattintva elérhetővé válik a **Sorok** gyorslap az eszköztáron.
1. Válassza a **Sorok** gyorslap **Új** elemét, majd állítsa be a következő értékeket az új soron: Az összes többi mezőben hagyja meg az alapértelmezett értékeket.

    - **Sorozat:** *1*
    - **Kezdet:** *0*
    - **Befejezés:** *1 000 000*

1. A **Mentés** gombra kattintva elérhetővé válik a **Helyutasítási műveletek** gyorslap az eszközsoron.
1. Válassza a **Helyutasítás-műveletek** gyorslap **Új** elemét, majd állítsa be a következő értékeket az új soron: Az összes többi mezőben hagyja meg az alapértelmezett értékeket.

    - **Sorozat:** *1*
    - **Név:** *Baydoor Multi*

1. Válassza a **Mentés** lehetőséget.
1. A **Helyutasítás műveletei** gyorslapon válassza a **Lekérdezés szerkesztése** lehetőséget.
1. A lekérdezési szerkesztő **Tartomány** lapján keresse meg azt a sort, amelynél a **Mező** mező értéke *Hely*. Ennek a sornak a **Feltételek** mezőjét állítsa *Baydoor* értékre.
1. Az **OK** gombra kattintva mentse a beállításokat, és zárja be a lekérdezésszerkesztőt.

### <a name="set-up-work-templates"></a>Munkasablonok beállítása

1. Lépjen a **Raktárkezelés \> Beállítás \> Munka \> Munkasablonok** elemre.
1. Módosítsa a **Munkarendelés típusa** mezőt *Rendezett készletkitárolás* értékre.
1. Jelölje be a műveleti ablakban az **Új** lehetőséget a munkasablon létrehozásához.
1. Az **Áttekintés** lapon állítsa be a következő értékeket:

    - **Sorozat:** *1*
    - **Munkasablon:** *Rendezés*
    - **Munkasablon leírása:** *Rendezés*

1. A **Mentés** gombra kattintva elérhetővé válik a **Munkasablon részletei** gyorslap.
1. A **Munkasablon részletei** gyorslapon válassza az **Új** parancsot egy sor hozzáadásához, majd állítsa be a következő értékeket hozzá:

    - **Munka típusa:** *Kitárolás*
    - **Munkaosztály azonosítója:** *SORT*

1. Válassza ismét az **Új** lehetőséget egy második sor hozzáadásához, és állítsa be a következő értékeket hozzá:

    - **Munka típusa:** *Eltárolás*
    - **Munkaosztály azonosítója:** *SORT*

1. Válassza a **Mentés** lehetőséget.

## <a name="scenario"></a>Forgatókönyv

Ez a forgatókönyv egy olyan állapotot szimulál, amikor a csomagolt tárolókat a szállítmányozói szolgáltatástól függően automatikusan különböző pozíciókra (raklapokra) kell rendezni. Miután a rakomány minden cikkét becsomagolták, és a cím szerint rendezték, a raklapok a raktárajtóhoz kerülnek.

### <a name="create-sales-orders-and-picking-work"></a>Értékesítési rendelések és kitárolási munka létrehozása

#### <a name="create-sales-order-1"></a>1. értékesítési rendelés létrehozása

1. Ugorjon az **Értékesítés és marketing \> Értékesítési rendelések \> Minden értékesítési rendelés** pontra.
1. A Műveleti ablaktáblán kattintson az **Új** elemre.
1. Az **Értékesítési rendelés létrehozása** párbeszédpanelen adja meg a következő értékeket:

    - **Vevőkód** *US-005*
    - **Raktár:** *62*

1. Az **OK** gombbal zárja be a párbeszédpanelt.

    A program megnyitja az új értékesítési rendelést.

1. Váltson a **Fejléc** nézetre.
1. A **Szállítás** gyorslapon a **Szállítás** szakaszban adja meg a következő értékeket:

    - **Szállítmányozó:** *Légitársaság*
    - **Szállítmányozói szolgáltatás:** *Légi*

1. Váltson a **Sorok** nézetre.
1. Az **Értékesítésirendelés-sor** gyorslapon válassza a **Sor hozzáadása** lehetőséget, ha nem ad hozzá új sort a program, és adja meg a következőt:
1. A következő értékeket állítsa be az új rendeléssorhoz:

    - **Cikkszám:** *A0001*
    - **Mennyiség:** *2*

1. Miközben az **Értékesítésirendelés-sorok** gyorslapján az új rendelési sor továbbra is be van jelölve, akkor a rács fölötti **Készlet** menüben válassza a **Foglalás** elemet.
1. A **Foglalás** oldalon válassza ki az **Adag foglalása** lehetőséget, hogy lefoglalja a kiválasztott sor teljes mennyiségét a raktárban.
1. Zárja be a **Foglalás** lapot, hogy visszatérjen az értékesítési rendeléshez.
1. Válassza ki a művelet ablaktáblán a **Raktár** lapon a **Műveletek** csoportjának **Kiadás raktárba** parancsát.
1. Egy tájékoztató üzenet jelenik meg, amely a rendelés szállítmányát és hullámát jeleníti meg. Jegyezze fel a hullám azonosítószámát és a szállítmány azonosítószámait.

#### <a name="sales-order-2"></a>2. értékesítési rendelés

1. Ugorjon az **Értékesítés és marketing \> Értékesítési rendelések \> Minden értékesítési rendelés** pontra.
1. A Műveleti ablaktáblán kattintson az **Új** elemre.
1. Az **Értékesítési rendelés létrehozása** párbeszédpanelen adja meg a következő értékeket:

    - **Vevőkód** *US-006*
    - **Raktár:** *62*

1. Az **OK** gombbal zárja be a párbeszédpanelt.
1. A program megnyitja az új értékesítési rendelést. Tartalmaznia kell egy új, üres sort az **Értékesítési rendelés sorai** gyorslap rácsán. A következő értékeket állítsa be ehhez a rendeléssorhoz:

    - **Cikk:** *A0001*
    - **Mennyiség:** *1*

1. A **Sor részletei** gyorslap **Szállítás** lapján állítsa be a **Szállítási mód** mezőt *Flowe-STD* értékre.
1. Válassza az **Értékesítési rendelés sorai** gyorslap **Sor hozzáadása** elemét, majd állítsa be a következő értékeket a második értékesítési soron:

    - **Cikk:** *A0002*
    - **Mennyiség:** *1*

1. A **Sor részletei** gyorslap **Szállítás** lapján módosítsa a **Szállítási mód** mezőt *Air C-Air* értékre.
1. Az **Értékesítési rendelés sorai** gyorslapon válassza az első rendeléssort. Majd a rács feletti **Készlet** menüben válassza ki a **Foglalás** pontot.
1. A **Foglalás** oldalon válassza ki az **Adag foglalása** lehetőséget, hogy lefoglalja a kiválasztott sor teljes mennyiségét a raktárban.
1. Zárja be a **Foglalás** lapot, hogy visszatérjen az értékesítési rendeléshez.
1. Az **Értékesítési rendelés sorai** gyorslapon válassza a második rendeléssort. Majd a rács feletti **Készlet** menüben válassza ki a **Foglalás** pontot.
1. A **Foglalás** oldalon válassza ki az **Adag foglalása** lehetőséget, hogy lefoglalja a kiválasztott sor teljes mennyiségét a raktárban.
1. Zárja be a **Foglalás** lapot, hogy visszatérjen az értékesítési rendeléshez.
1. Válassza ki a művelet ablaktáblán a **Raktár** lapon a **Műveletek** csoportjának **Kiadás raktárba** parancsát.
1. Egy tájékoztató üzenet jelenik meg, amely a rendelés szállítmányát és hullámát jeleníti meg. Figyelje meg, hogy az értékesítési rendelés soraiban két hullám-azonosító és két szállítási azonosító lett létrehozva egy-egy az egyes értékesítésirendelés-sorokhoz.

#### <a name="get-the-work-ids-from-the-work-details"></a>Munkaazonosítók beolvasása a munka részleteiből

1. Ugorjon a **Raktárkezelés \> Munka \> Munka részletei** pontra.
1. A lapon az értékesítési rendelésekből létrehozott munkaazonosítók láthatók. Használja a hullámazonosítókat és szállítmányazonosítókat az értékesítési rendelésekből, amelyeket létrehozott az egyes hullámok és szállítmányok munkaazonosítójának megkereséséhez. Jegyezze fel ezeket a munkaazonosítókat, mert a következő lépésekben szüksége lesz rájuk. Figyelje meg, hogy a második értékesítési rendeléshez két munkaazonosító jött létre. Ha különböző cikkek kitárolása különböző helyekről történik, akkor külön szavas azonosítók jönnek létre.

### <a name="pick-items-for-the-sales-orders"></a>Cikkek kitárolása az értékesítési rendelésekhez

Végezze el a létrehozott munkát úgy, hogy a mobileszköz segítségével áthelyezi a cikkeket a csomagolási állomásra.

1. A mobileszközön jelentkezzen be a *62-es* raktárba a forgatókönyvhöz létrehozott felhasználói azonosító (vagy egy meglévő demóadat-felhasználó) használatával.
1. Válassza a főmenü **Kimenő** elemét.
1. Válassza a **Kimenő** menü **Értékesítési kitárolás** elemét.
1. Az **Azonosító** mezőbe írja be az 1. értékesítési rendeléshez létrehozott munkaazonosítót.
1. Válassza ki az **OK** lehetőséget.
1. Az **Értékesítési rendelések – Kitárolás** oldalon adja meg az 1. értékesítési rendeléshez létrehozott azonosítótáblát. Figyelje meg, hogy a kitárolási hely (*bulk-001*), a cikk (*A0001*) és a mennyiség (*2 db*) jelenik meg.
1. Válassza ki az **OK** lehetőséget.
1. Tekintse át a **Beszerzési rendelések – Betárolás** oldalon látható információkat. A **Hely** mezőnek jeleznie kell, hogy a kitárolt cikkek a *Csomagolás* helyre mennek.
1. Válassza ki az **OK** lehetőséget.

    A **Munkaazonosító/azonosítótábla azonosítójának beolvasása** lapon egy „Elvégzett munka” üzenet jelenik meg, amely azt jelzi, hogy az 1. értékesítési rendelés munkaazonosítóját befejezték.

    Most kitárolhatja a 2. értékesítési rendelést.

1. Az **Azonosító** mezőbe írja be a 2. értékesítési rendeléshez létrehozott munkaazonosítót, ahol az 1. sor cikke *A0001*.
1. Válassza ki az **OK** lehetőséget.
1. Az **Értékesítési rendelések – Kitárolás** oldalon adja meg a cél azonosítótáblát. Figyelje meg, hogy a kitárolási hely (*bulk-001*), a cikk (*A0001*) és a mennyiség (*1 db*) jelenik meg.
1. Válassza ki az **OK** lehetőséget.
1. Tekintse át a **Beszerzési rendelések – Betárolás** oldalon látható információkat. A **Hely** mezőnek jeleznie kell, hogy a kitárolt cikkek a *Csomagolás* helyre mennek.
1. Válassza ki az **OK** lehetőséget.

    A **Munkaazonosító/azonosítótábla azonosítójának beolvasása** oldalon egy „Munka elvégezve” üzenet jelenik meg. Ez az üzenet azt jelzi, hogy a 2. értékesítési rendelés 1. sorának munkaazonosítója el lett végezve.

1. Az **Azonosító** mezőbe írja be a 2. értékesítési rendeléshez létrehozott munkaazonosítót, ahol az 2. sor cikke *A0002*.
1. Válassza ki az **OK** lehetőséget.
1. Az **Értékesítési rendelések – Kitárolás** oldalon adja meg a cél azonosítótáblát. Figyelje meg, hogy a kitárolási hely (*bulk-002*), a cikk (*A0001*) és a mennyiség (*1 db*) jelenik meg.
1. Válassza ki az **OK** lehetőséget.
1. Tekintse át a **Beszerzési rendelések – Betárolás** oldalon látható információkat. A **Hely** mezőnek jeleznie kell, hogy a kitárolt cikkek a *Csomagolás* helyre mennek.
1. Válassza ki az **OK** lehetőséget.

    A **Munkaazonosító/azonosítótábla azonosítójának beolvasása** oldalon egy „Munka elvégezve” üzenet jelenik meg. Ez az üzenet azt jelzi, hogy a 2. értékesítési rendelés 2. sorának munkaazonosítója el lett végezve.

### <a name="pack-sales-orders-into-containers"></a>Értékesítési rendelések csomagolása tárolókba

#### <a name="pack-sales-order-1-into-containers"></a>Az 1. értékesítési rendelés csomagolása tárolókba

1. Nyissa meg a **Raktárkezelés \> Csomagolási és tárolólétrehozás \> Csomagolás** menüt.

    Megjelenik a **Csomagolóállomás kiválasztása** párbeszédpanel. Alapértelmezés szerint a **Dolgozó** mezőt a korábban beállított dolgozó nevére kell állítani.

1. Állítsa be a következő értékeket az adott csomagolásai helyen tervezett szállítmányok és tárolók megtekintéséhez és az azokkal történő munkához:

    - **Telephely:** *6*
    - **Raktár:** *62*
    - **Hely:** *Csomag*
    - **Csomagolási profil azonosítója:** *Rendezés*

1. Az **OK** gombbal zárja be a párbeszédpanelt.
1. A **Csomag** lap **Azonosítótábla vagy szállítmány** mezőjébe írja be az 1. értékesítési rendelés cél azonosítótábláját. Ezután a billentyűzet **Tab** vagy **Enter** gombjával lépjen ki a mezőből.
1. A műveleti ablaktáblán kattintson az **Új tároló** elemre.
1. Fogadja el az alapértelmezett beállításokat, majd válassza az **OK** gombot. Jegyezze fel a tárolóazonosítót.
1. A **Cikkcsomagolás** gyorslapon állítsa be a következő értékeket:

    - **Mennyiség:** *1*
    - **Azonosító:** Cikk *A0001*

1. A műveleti ablaktáblán kattintson az **Tároló bezárása** elemre.
1. A **Tároló lezárása** párbeszédpanelen válassza a **Rendszertömeg beolvasása lehetőséget**, ha szeretné, hogy a rendszer frissítse a **Bruttó súly** mezőt.
1. Válassza ki az **OK** lehetőséget. A program áthelyezi a tárolót a *SORT* helyre, és készen áll a rendezésre.
1. Hozzon létre egy másik tárolót, és adja hozzá a második elemet az 1. értékesítési rendelés azonosítótáblájáról egy új tárolóhoz.
1. A műveleti ablaktáblán kattintson az **Új tároló** elemre.
1. Fogadja el az alapértelmezett beállításokat, majd válassza az **OK** gombot. Jegyezze fel a tárolóazonosítót.
1. A **Cikkcsomagolás** gyorslapon állítsa be a következő értékeket:

    - **Mennyiség:** *1*
    - **Azonosító:** Cikk *A0001*

1. A műveleti ablaktáblán kattintson az **Tároló bezárása** elemre.
1. A **Tároló lezárása** párbeszédpanelen válassza a **Rendszertömeg beolvasása lehetőséget**, ha szeretné, hogy a rendszer frissítse a **Bruttó súly** mezőt.
1. Válassza ki az **OK** lehetőséget. A program áthelyezi a tárolót a *SORT* helyre, és készen áll a rendezésre.

#### <a name="pack-sales-order-2-into-containers"></a>Az 2. értékesítési rendelés csomagolása tárolókba

1. A **Csomag** lap **Azonosítótábla vagy szállítmány** mezőjébe írja be a 2.. értékesítési rendelés első sorának cél azonosítótábláját. Ezután a billentyűzet **Tab** vagy **Enter** gombjával lépjen ki a mezőből.
1. A műveleti ablaktáblán kattintson az **Új tároló** elemre.
1. Fogadja el az alapértelmezett beállításokat, majd válassza az **OK** gombot. Jegyezze fel a tárolóazonosítót.
1. A **Cikkcsomagolás** gyorslapon állítsa be a következő értékeket:

    - **Mennyiség:** *1*
    - **Azonosító:** Cikk *A0001*

1. A műveleti ablaktáblán kattintson az **Tároló bezárása** elemre.
1. A **Tároló lezárása** párbeszédpanelen válassza a **Rendszertömeg beolvasása lehetőséget**, ha szeretné, hogy a rendszer frissítse a **Bruttó súly** mezőt.
1. Válassza ki az **OK** lehetőséget. A program áthelyezi a tárolót a *SORT* helyre, és készen áll a rendezésre.
1. Az **Azonosítótábla vagy szállítmány** mezőbe írja be a 2. értékesítési rendelés második sorának cél azonosítótábláját. Ezután a billentyűzet **Tab** vagy **Enter** gombjával lépjen ki a mezőből.
1. A műveleti ablaktáblán kattintson az **Új tároló** elemre.
1. Fogadja el az alapértelmezett beállításokat, majd válassza az **OK** gombot. Jegyezze fel a tárolóazonosítót.
1. A **Cikkcsomagolás** gyorslapon állítsa be a következő értékeket:

    - **Mennyiség:** *1*
    - **Azonosító mező:** Cikk *A0002*

1. A műveleti ablaktáblán kattintson az **Tároló bezárása** elemre.
1. A **Tároló lezárása** párbeszédpanelen válassza a **Rendszertömeg beolvasása lehetőséget**, ha szeretné, hogy a rendszer frissítse a **Bruttó súly** mezőt.
1. Válassza ki az **OK** lehetőséget. A program áthelyezi a tárolót a *SORT* helyre, és készen áll a rendezésre.

A tároló adatainak megtekintéséhez nyissa meg a **Raktárkezelés \> Csomagolás és tárolólétrehozás \> Tárolók** lehetőséget, és keresse meg a csomagolás során létrehozott tárolóazonosítókat.

### <a name="sort-the-containers"></a>A tárolók rendezése

> [!IMPORTANT]
> Amikor a mobilalkalmazás **Raklap összeállítása** menüjét megnyitja a kimenő rendszerezéshez, akkor egy **Teljes** feliratú gombot fog látni. *Ne használja a **Teljes** gombot a pozíció rendezéséhez vagy lezárásához.*
>
> A **Teljes** gomb alapértelmezésben elérhető, és nem lehet letiltani vagy eltávolítani a lapról. Ez a beállítás nem lehet a *Kimenő rendezés* funkcióhoz használni.

#### <a name="sort-the-first-container"></a>Az első tároló rendezése

1. A mobileszközön jelentkezzen be a *62-es* raktárba a forgatókönyvhöz létrehozott felhasználói azonosító (vagy egy meglévő demóadat-felhasználó) használatával.
1. Válassza a főmenü **Kimenő** elemét.
1. Válassza a **Kimenő** menü **Raklap összeállítása** elemét.
1. Az **Azonosítótábla/con** mezőbe írja be az 1. értékesítési rendeléshez társított tárolóazonosítót.
1. Válassza ki az **OK** lehetőséget.
1. Mivel jelenleg nem léteznek rendezési pozíciók, meg kell adnia egyet. A **Rendezési pozíció azonosítója** mezőbe írja be az *SP01* értéket.
1. Mivel jelenleg nincs azonosítótábla társítva az *SP01* rendezési pozícióhoz, meg kell adnia egy értéket. Az **Azonosítótábla** mezőben adja meg a *PLP01* értéket.
1. Válassza ki az **OK** lehetőséget.
1. Mivel a rendezési pozíció ellenőrzése be van kapcsolva, újra meg kell adnia a rendezési pozíció azonosítóját. A **Rendezési pozíció azonosítója** mezőbe írja be az *SP01* értéket.
1. Válassza ki az **OK** lehetőséget.

    A „Munka befejezve” üzenet jelenik meg.

> [!TIP]
> Ha meg szeretné tekinteni a rendezési pozíciót és a benne lévő azonosítótáblát nyissa meg a **Raktárkezelés \> Csomagolás és tárolólétrehozás \> Kimenő rendezésipozíció-hozzárendelések** lehetőséget.
>
> A **Kimenő rendezésipozíció-hozzárendelések** lap megjeleníti a jelenleg aktív összes rendezési pozíciót. A **Rendezésipozíció-tranzakciók** mező megjeleníti az egyes pozíciókhoz társított azonosítótáblákat és a rendezési pozícióban lévő tárolókat. Figyelje meg, hogy jelenleg egy rendezési beosztás létezik, és a **Rendezési pozíció feltételei** gyorslap a **Szállítmány – Szállítmányozói szolgáltatás – Légi** kritériumot jeleníti meg.

#### <a name="sort-the-remaining-containers"></a>A fennmaradó tárolók rendezése

1. A mobileszközön jelentkezzen be a *62-es* raktárba a forgatókönyvhöz létrehozott felhasználói azonosító (vagy egy meglévő demóadat-felhasználó) használatával.
1. Válassza a főmenü **Kimenő** elemét.
1. Válassza a **Kimenő** menü **Raklap összeállítása** elemét.
1. Az **Azonosítótábla/con** mezőbe írja be az 1. értékesítési rendeléshez társított második tárolóazonosítót.
1. Válassza ki az **OK** lehetőséget. Mivel a rendezési sablon automatikus rendezésre van beállítva, és létezik egy megfelelő kritériumokkal rendelkező rendezési pozíció, automatikusn át lesz irányítva a helyes rendezési pozícióhoz.
1. Válassza ki az **OK** lehetőséget.
1. Erősítse meg a rendezési pozíció azonosítóját, hogy jelezze, hogy a készlet a megfelelő helyen van. A **Rendezési pozíció azonosítója** mezőbe írja be az *SP01* értéket.
1. Válassza ki az **OK** lehetőséget.

    A munka az 1. értékesítési rendelés második tárolóján végezhető el. Ezután a fennmaradó tárolókat a 2. értékesítési rendelésből rendezzük.

1. Az **Azononsítótábla/Con** mezőbe írja be annak a tárolónak az azonosítóját, amelybe a 2. értékesítési rendelés *A0001* cikkét tartalmazza. Mivel a szállítmányozói szolgáltatás különbözik, a program kéri, hogy írjon be egy új rendezési pozíciót, és adjon hozzá egy azonosítótáblát ahhoz a pozícióhoz. Használja az *SP02* rendezési pozíciót és a *PLP02* azonosítótáblát.
1. Válassza ki az **OK** lehetőséget.
1. A rendezési pozíció jóváhagyásához írja be az *SP02* értéket a **Rendezési pozíció azonosítója** mezőbe.
1. Válassza ki az **OK** lehetőséget.

    A munka a tárolón fejeződik be.

1. Az **Azononsítótábla/Con** mezőbe írja be a megmaradt tárolónak az azonosítóját, amelybe a 2. értékesítési rendelés *A0002* cikkét tartalmazza. Mivel a szállítmányozói szolgáltatás ugyanaz, mint az 1. értékesítési rendelés szállítmányozói szolgáltatása, a rendszer a megfelelő feltételekkel rendelkező meglévő rendezési pozíciót jeleníti meg.
1. Válassza ki az **OK** lehetőséget.
1. A rendezési pozíció jóváhagyásához írja be az *SP01* értéket a **Rendezési pozíció azonosítója** mezőbe.
1. Válassza ki az **OK** lehetőséget.

    A munka a tárolón fejeződik be.

### <a name="close-the-outbound-sorting-positions"></a>A kimenő rendezési pozíciók lezárása

Ha minden készletet rendeztek, akkor a pozíciót a munka létrehozása előtt le kell zárni. A program létrehoz egy rendezett készletkitárolási-munkát, hogy a készletet a raktárajtóhoz vigye.

#### <a name="close-a-position-from-the-mobile-device"></a>Pozíció lezárása a mobileszközből

1. A mobileszközön jelentkezzen be a *62-es* raktárba a forgatókönyvhöz létrehozott felhasználói azonosító (vagy egy meglévő demóadat-felhasználó) használatával.
1. Válassza a főmenü **Kimenő** elemét.
1. Válassza a **Kimenő** menü **Raklap összeállítása** elemét.
1. Az **Azonosítótábla/Con** mezőbe írja be azt a tároló-azonosítót, amelyet az *SP01* rendezési pozícióhoz rendeltek.
1. Válassza ki az **OK** lehetőséget.
1. A következő üzenet jelenik meg: „A tároló már hozzá van rendelve az SP01 pozícióhoz. Lezárja a pozíciót?” Válassza **Bezárás** lehetőséget.

    A munka befejeződött.

#### <a name="close-a-position-from-outbound-sorting-position-assignments"></a>Pozíció lezárása a kimenő rendezési pozíció hozzárendeléseiből

1. Nyissa meg a **Raktárkezelés \> Csomagolás és tárolólétrehozás \> Kimenő rendezésipozíció-hozzárendelések** lehetőséget.
1. A bal oldali oszlopban válassza ki az **SP02** elemet. Ez a kimenő rendezési pozíció sora az, amelyet le fog zárni.
1. A műveleti ablaktáblán kattintson az **Pozíció lezárása** elemre. A rendezési pozíció rekordja le van zárva, és már nem jelenik meg.

    > [!TIP]
    > Ha minden lezárt pozíció rekordját meg szeretné jeleníteni, jelölje be a **Lezártak megjelenítése** jelölőnégyzetet.

### <a name="sorted-inventory-picking"></a>Sorba rendezett készletkitárolás

El kell végeznie a rendezett készlet kitárolási munkafolyamatát. Amikor ez befejeződött a készlet ki lesz tárolva az értékesítési rendeléshez. Ekkor minden egyéb raktári folyamat érvényes.

1. A mobileszközön jelentkezzen be a *62-es* raktárba a forgatókönyvhöz létrehozott felhasználói azonosító (vagy egy meglévő demóadat-felhasználó) használatával.
1. Válassza a főmenü **Kimenő** elemét.
1. Válassza a **Kimenő** menü **Rakomány rendezésből** elemét.
1. Adja meg a cél Azonosítótábla azonosítóját az első rendezési pozícióból, az *SP01*-ből. Állítsa az **Azonosító** mezőt *PLP01* értékre.
1. Válassza ki az **OK** lehetőséget.
1. A **Rendezett készlet kitárolása: kitárolás** lap megjeleníti a kitárolási munkát, amelyet el kell végezni. Válassza ki a *SORT* helyet, és a cél *PLP01* azonosítótáblát, amely több cikket és *3* mennyiséget tartalmaz.
1. Válassza ki az **OK** lehetőséget.
1. A **Rendezett készlet kitárolása: betárolás** lap megjeleníti a betárolási munkát, amelyet el kell végezni. Tároljon be a *Baydoor* helyre, és a cél *PLP01* azonosítótáblát, amely több cikket és *3* mennyiséget tartalmaz.
1. Válassza ki az **OK** lehetőséget.

    A munka befejeződött.

1. Adja meg a cél azonosítótábla azonosítóját a második rendezési pozícióból, az *SP02*-ből. Állítsa az **Azonosító** mezőt *PLP02* értékre.
1. Válassza ki az **OK** lehetőséget.
1. A **Rendezett készlet kitárolása: kitárolás** lap megjeleníti a kitárolási munkát, amelyet el kell végezni. Válassza ki a *SORT* helyet, és a cél *PLP02* azonosítótáblát, amely több cikket és *1* mennyiséget tartalmaz.
1. Válassza ki az **OK** lehetőséget.
1. A **Rendezett készlet kitárolása: betárolás** lap megjeleníti a betárolási munkát, amelyet el kell végezni. Tároljon be a *Baydoor* helyre, és a cél *PLP02* azonosítótáblát, amely több cikket és *1* mennyiséget tartalmaz.
1. Válassza ki az **OK** lehetőséget.

    A munka befejeződött.

Ekkortól minden egyéb raktári folyamat érvényes.
