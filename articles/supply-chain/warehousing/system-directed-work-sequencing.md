---
title: Rendszer által irányított munka sorrendbe állítása
description: Ez a témakör a rendszer által irányított munka sorrendbe állítással kapcsolatban tartalmaz tájékoztatást. Ez a funkció lehetővé teszi a rendszer által a felhasználóknak a végrehajtásra bemutatott munkarendelések rendezését és szűrését. Ez olyan esetekben hasznos, amikor további feltételek szükségesek a raktári kitárolási folyamat vezetéséhez.
author: Mirzaab
manager: tfehr
ms.date: 07/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFSystemDirectedWorkSequenceQuery, WHSLocDirTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-03
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 7db884a5cd62e1f44a2a86316fde6bf2d11a3376
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5239134"
---
# <a name="system-directed-work-sequencing"></a>Rendszer által irányított munka sorrendbe állítása

[!include [banner](../includes/banner.md)]

A rendszer által irányított munka sorrendbe állítás lehetővé teszi a rendszer által a felhasználóknak a végrehajtásra bemutatott munkarendelések rendezését és szűrését. Ez olyan esetekben hasznos, amikor további feltételek szükségesek (például a szállítás időpontja, a kitárolási zóna, a hely profilja, illetve a különböző feltételek kombinációja) a raktár kitárolási folyamatának vezetéséhez.

Ez a funkció kiterjeszti a rendszer által irányított kitárolási funkciót egy rendszer által irányított lekérdezési rendelés hozzáadásával, ahol a felhasználók megadhatnak egy sorrendet és egy vagy több lekérdezést, amely minden létrehozott munkarendelést értékelni fog. Csak olyan munkarendelések kerülnek rögzítésre és megjelenítésre, amelyek megfelelnek a mobileszköz menüelemének beállításában meghatározott feltételeknek.

Ez a funkció lehetővé teszi a raktári kitárolási folyamatok további optimalizálását, mivel meghatározza a megadott feltételeknek megfelelő munkarendeléseket, hozzárendeli őket a megfelelő mobileszköz-menüelemhez, majd bemutatja őket egy dolgozónak egy meghatározott szakértelmi készlet, kitárolási eszköz vagy egyéb követelmény alapján.

> [!NOTE]
> Ha különböző feltételek szükségesek, akkor több mobileszköz-menüelemet kell használni.

## <a name="turn-on-the-organization-wide-system-directed-work-sequencing-feature"></a>Kapcsolja be a Szervezeti szintű rendszer által irányított munka sorrendbe állítása funkciót

A rendszer által irányított munka sorrendbe állításának használata előtt be kell kapcsolni azt a rendszerben. A rendszergazdák használhatják a [Funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) munkaterületet a funkció állapotának ellenőrzéséhez, és szükség esetén bekapcsolásához. A funkció a következő módon jelenik meg:

- **Modul:** *Raktárkezelés*
- **Szolgáltatás neve:** *Szervezeti szintű rendszer által irányított munka sorrendbe állítása*

## <a name="setup"></a>Beállítás

### <a name="make-demo-data-available"></a>A bemutató adatok elérhetővé tétele

Ha ezt a forgatókönyvet az ebben a témakörben megadott mintaadatok és értékek alapján kívánja elvégezni, akkor egy olyan rendszeren kell dolgoznia, amelynél a szokásos demóadatok telepítve vannak. Ezenkívül ki kell választania az **USMF** jogi személyt. A forgatókönyv az *51*-es raktárt használja a demóadatokból.

> [!IMPORTANT]
> Mielőtt kiadja a rendeléseket a raktárba, győződjön meg arról, hogy a kitárolási helyek elegendő készlettel rendelkeznek a rendelések minden cikkéhez.
>
> Az alapértelmezett USMF-adatoknak támogatniuk kell ezt a forgatókönyvet. Ha nem demóadatokat használ, a **Helyutasítás** beállítás áttekintésével ismerje meg, hogy melyik kitárolási helyeket használja a rendszer az értékesítési rendelések kitároláshoz. Ha módosítania kell a készletet, akkor manuális mozgásokat hozhat létre, felhasználhatja a feltöltést, vagy bármilyen egyéb folyamatot alkalmazhat.

### <a name="set-up-a-mobile-device-menu-item"></a>Mobileszköz-menüelem beállítása

1. Lépjen a **Raktárkezelés \> Beállítás \> Mobileszköz \> Mobileszköz-menüelemek** részre.
1. A mobileszköz-menüelemek listáján válassza az **Értékesítési kitárolás – rendszer** elemet. A szükséges menüelemnek már léteznie kell. 
1. Erősítse meg a következő beállításokat:

    - Az **Általános** gyorslapon az **Irányító** mezőt *Rendszer által irányított* értékre kell beállítani.
    - A **Munkaosztályok** gyorslap a következő beállításokat jeleníti meg.

        | Munkaosztály azonosítója | Munkarendelés típusa |
        |---|---|
        | Értékesítés | Értékesítési rendelés |
        | SO kitárolás | Értékesítési rendelés |

1. A Művelet panelen válassza ki a **Rendszer által irányított munka sorrendbe állítás lekérdezései** lehetőséget.
1. Válassza ki a **Szerkesztés** opciót.
1. Törölje a meglévő sort, majd az **Igen** gombra kattintva hagyja jóvá a műveletet.
1. Jelölje be a műveleti ablakban az **Új** lehetőséget az új sor létrehozásához.
1. Az új sorban állítsa be a következő értékeket:

    - **Sorszám:** *1*
    - **Leírás mező:** *20-nál kisebb munkamennyiség és csökkenő*

1. Válassza a **Mentés** lehetőséget.
1. A műveleti ablaktáblán válassza a **Lekérdezés szerkesztése** lehetőséget.
1. Az **illesztések** lapon bontsa ki az illesztési hierarchiát a **Munkasorok** tábla megjelenítéséhez.
1. Válassza ki a **Munkasorok** tábla illesztését.
1. Válassza a **Táblaillesztés hozzáadása** lehetőséget.
1. A megjelenő listában keresse meg és válassza ki azt a sort, amelynél a következő beállítások szerepelnek:

    - **Illesztési mód:** *n:1*
    - **Kapcsolat:** *Helyek (hely)*

1. Válassza ki a **Kiválasztás** lehetőséget.

    A helyek hozzáadásra kerülnek a tábla illesztéséhez.

1. A **Rendezés** lapon válassza a **Hozzáadás** lehetőséget új sor hozzáadásához.
1. Az új sorban állítsa be a következő értékeket:

    - **Táblázat:** *Munkasorok*
    - **Származtatott tábla:** *Munkasorok*
    - **Mező:** *Munkamennyiség* (a megjelenő üzenetablakban válassza az **Igen** lehetőséget, ha hozzá szeretné adni a rendezést ehhez a mezőhöz.)
    - **Keresés iránya:** *Csökkenő*

1. Válassza ki a **Tartomány** lapot.

    Ha csak meghatározott munkafeltételek szerepelhetnek a sorrendbe állításban, akkor megadhatja őket a **Tartomány** lapon. Ebben a példában csak azokat a munkát szeretné belefoglalni, amelyeknél a mennyiség 20 ea-nál kevesebb (a legalacsonyabb mértékegység).

    Figyelje meg, hogy egyes sorok már szerepelnek. Ezeket a sorokat nem szabad eltávolítani.

1. Sor hozzáadásához válassza a **Hozzáadás** lehetőséget.
1. Az új sorban állítsa be a következő értékeket:

    - **Táblázat:** *Munkasorok*
    - **Származtatott tábla:** *Munkasorok*
    - **Mező:** *Készlet munkamennyisége*
    - **Feltételek:** *\<20* (kisebb, mint 20)

1. További sor hozzáadásához válassza a **Hozzáadás** lehetőséget.
1. Az új sorban állítsa be a következő értékeket:

    - **Táblázat:** *Munkasorok*
    - **Származtatott tábla:** *Munkasorok*
    - **Mező:** *Munkatípus*
    - **Feltételek:** *Kitárolás*

1. További sor hozzáadásához válassza a **Hozzáadás** lehetőséget.
1. Az új sorban állítsa be a következő értékeket:

    - **Tábla:** *Helyek*
    - **Származtatott tábla:** *Helyek*
    - **Mező:** *Hely profilazonosítója*
    - **Feltételek:** *!FOKOZAT*

        > [!IMPORTANT]
        > Ügyeljen arra, hogy a felkiáltójel (*!*) szerepeljen a *FOKOZAT* előtt.

1. Az **OK** gombra kattintva mentse és zárja be a lekérdezést.
1. Válassza a **Mentés** lehetőséget.
1. Zárja be az oldalt, és térjen vissza a **Mobileszköz menüpontjai** oldalra.

> [!NOTE]
> Ez a beállítás határozza meg a feltételt, amely a választható munkát a mobileszköz menüelembe történő betöltéséhez fogja használni. Ha több feltételsort ad hozzá a lekérdezéshez, akkor a rendszer először a legalacsonyabb sorszámú lekérdezési sort fogja használni. Más szóval az 1. sorszám összes támogatható munkáját kapja meg először a felhasználó, majd a 2. sorszám összes munkáját. Ezért ha egy meghatározott tartományt és rendezést együtt kell használni, akkor ugyanabban a rendszer által irányított munka sorrendbe állítási lekérdezésben kell megadni.
>
> Ez a beállítás rögzíti azokat a munkafolyamatokat, amelyeknek legalább egy sora van, ahol a mennyiség kevesebb, mint 20 ea. Ezért, ha a munka olyan sorral rendelkezik, ahol a mennyiség pontosan 20 ea vagy több, mint 20 ea, akkor érvényes, feltéve, hogy legalább egy olyan sor van, amelynél a mennyiség kevesebb, mint 20 ea.

### <a name="location-directives"></a>Helyutasítások

Ha az alapértelmezett Contoso-adatokat használja, akkor a helyutasítás művelethez tartozó lekérdezés nem fog változtatásokat igényelni. Azonban annak érdekében, hogy a szolgáltatás nem Contoso-környezetben történő alkalmazása esetén az értékesítési rendeléseken szereplő cikkeket a helyutasítások rögzítsék, új helyutasításokat kell létrehoznia. A beállítások ellenőrzéséhez a demókörnyezetben hajtsa végre az alábbi lépéseket.

1. Ugrás a **Raktárkezelés** \> **Beállítás** \> **Helyutasítások** elemre.
1. A **Munkarendelés típusa** mezőben válassza ki az *Értékesítési rendelések* elemet.
1. Válassza ki az *51 kitárolás* nevű helyutasítást.
1. A **Helyutasítás műveletei** gyorslapon válassza ki a **Kitárolás** művelet sorát.
1. Válassza ki a **Lekérdezés szerkesztése** lehetőséget a rács fölött.
1. Tekintse át a **Tartomány** lekérdezést.

    1. Keresse meg azt a sort, amelynél a **Mező** mező értéke *Hely*.
    2. Győződjön meg róla, hogy a **Feltételek** mező üres (azaz nincsenek korlátozások).

## <a name="scenario"></a>Forgatókönyv

### <a name="create-sales-order-picking-work"></a>Értékesítési rendelés kitárolási munkájának létrehozása

A rendszer által irányított kitárolás futtatása előtt létre kell hozni néhány kimenő munkát. Ehhez a helyzethez négy olyan értékesítési rendelést hoz létre, amelyek a megadott rendszer által irányított munka sorrendbe állítási lekérdezéseken alapulnak.

A program minden értékesítési rendeléshez lefoglalja a készletmennyiséget. Ezért a foglalt készletet nem lehet kivenni a raktárból más rendelésekhez a készletfoglalás (legalább részleges) visszavonásáig.

Ezt követően minden értékesítési rendelést kiad a raktárba, hogy létrehozza a kimenő munkát.

#### <a name="sales-order-1"></a>1. értékesítési rendelés

1. Ugorjon az **Értékesítés és marketing \> Értékesítési rendelések \> Minden értékesítési rendelés** pontra.
1. Jelölje be a műveleti ablakban az **Új** lehetőséget az 1. értékesítési rendelés létrehozásához.
1. Az **Értékesítési rendelés létrehozása** párbeszédpanelen adja meg a következő értékeket:

    - A **Vevő** szakaszban adja meg a **Vevőfiók** mezőt az *US-004* számára.
    - Az **Általános** szakaszban állítsa a **Raktár** mezőt az *51* értékre.

1. Az **OK** gombbal zárja be a párbeszédpanelt. Jegyezze fel az értékesítési rendelés számát.
1. Adjon hozzá egy sort az új értékesítési rendeléshez, és állítsa be a következő értékeket:

    - **Cikkszám:** *M9200*
    - **Mennyiség:** *20*

1. A rács feletti **Készlet** menüben válassza ki a **Foglalás** pontot.
1. A **Foglalás** oldalon válassza ki a **Készlet foglalása** elemet a készlet lefoglalásához.
1. Zárja be a **Foglalás** képernyőt.
1. Válassza ki a művelet ablaktáblán a **Raktár** lapon a válassza a **Kiadás raktárba** parancsot munka létrehozásához a raktár számára.

    Olyan tájékoztató üzenetek érkeznek, amelyek az értékesítési rendeléshez létrehozott hullámazonosítókat és szállítási azonosítókat jelenítik meg.

#### <a name="sales-order-2"></a>2. értékesítési rendelés

1. Jelölje be a műveleti ablakban az **Új** lehetőséget a 2. értékesítési rendelés létrehozásához.
1. Az **Értékesítési rendelés létrehozása** párbeszédpanelen adja meg a következő értékeket:

    - **Vevőkód** *US-007*
    - **Raktár:** *51*

1. Az **OK** gombbal zárja be a párbeszédpanelt. Jegyezze fel az értékesítési rendelés számát.
1. Adjon hozzá egy sort az új értékesítési rendeléshez, és állítsa be a következő értékeket:

    - **Cikkszám:** *M9200*
    - **Mennyiség:** *5*

1. Válassza ki a **Sor hozzáadása** lehetőséget egy második sort hozzáadásához, és állítsa be a következő értékeket:

    - **Cikkszám:** *M9201*
    - **Mennyiség:** *1*

1. Készlet foglalása mindkét sorhoz.
1. Adja ki a rendeléseket a raktárba.

#### <a name="sales-order-3"></a>3. értékesítési rendelés

1. Jelölje be a műveleti ablakban az **Új** lehetőséget a 3. értékesítési rendelés létrehozásához.
1. Az **Értékesítési rendelés létrehozása** párbeszédpanelen adja meg a következő értékeket:

    - **Vevőkód** *US-009*
    - **Raktár:** *51*

1. Az **OK** gombbal zárja be a párbeszédpanelt. Jegyezze fel az értékesítési rendelés számát.
1. Adjon hozzá egy sort az új értékesítési rendeléshez, és állítsa be a következő értékeket:

    - **Cikkszám:** *M9200*
    - **Mennyiség:** *7*

1. Válassza ki a **Sor hozzáadása** lehetőséget egy második sort hozzáadásához, és állítsa be a következő értékeket:

    - **Cikkszám:** *M9202*
    - **Mennyiség:** *8*

1. Készlet foglalása mindkét sorhoz.
1. Adja ki a rendeléseket a raktárba.

#### <a name="sales-order-4"></a>4. értékesítési rendelés

1. Jelölje be a műveleti ablakban az **Új** lehetőséget a 4. értékesítési rendelés létrehozásához.
1. Az **Értékesítési rendelés létrehozása** párbeszédpanelen adja meg a következő értékeket:

    - **Vevőkód** *US-010*
    - **Raktár:** *51*

1. Az **OK** gombbal zárja be a párbeszédpanelt. Jegyezze fel az értékesítési rendelés számát.
1. Adjon hozzá egy sort az új értékesítési rendeléshez, és állítsa be a következő értékeket:

    - **Cikkszám:** *M9200*
    - **Mennyiség:** *25*

1. Válassza ki a **Sor hozzáadása** lehetőséget egy második sort hozzáadásához, és állítsa be a következő értékeket:

    - **Cikkszám:** *M9202*
    - **Mennyiség:** *10*

1. Készlet foglalása mindkét sorhoz.
1. Adja ki a rendeléseket a raktárba.

### <a name="get-work-ids-for-the-work-that-was-created"></a>Munkaazonosítók beolvasása a létrehozott munkához

1. Ugorjon a **Raktárkezelés \> Munka \> Munka részletei** pontra.
1. Szűrjön a **Raktár** mezőre úgy, hogy csak az *51*-es raktárban lévő munka jelenjen meg.
1. Négy munkaazonosítónak kellett létrejönnie. Jegyezze fel az egyes értékesítési rendelések munkaazonosítóját.

    | Értékesítési rendelés azonosítója | Munkaazonosító | Munkakészlet |
    |---|---|---|
    | 1. értékesítési rendelés | 1. munkaazonosító | 20 ea |
    | 2. értékesítési rendelés | 2. munkaazonosító | 6 ea (mindkét sor összege) |
    | 3. értékesítési rendelés | 3. munkaazonosító | 15 ea (mindkét sor összege) |
    | 4. értékesítési rendelés | 4. munkaazonosító | 35 ea (mindkét sor összege) |

Mielőtt futtatná a folyamatot a mobileszközön, győződjön meg arról, hogy csak az imént létrehozott munka van *Nyitva* állapotban van az *51*-es raktár és az *Értékesítési rendelés* munkarendelés-típus esetében. Ellenkező esetben a teszt eredményei eltérőek lehetnek, mivel a rendszer által irányított kitárolás az összes alkalmas munkát tartalmazni fogja.

1. Lépjen a **Raktárkezelés \> Munka \> Kimenő \> Nyitott értékesítési munka** lehetőségre.
1. A **Nyitott értékesítési munka** rácsban szűrjön a **Raktár** mezőre úgy, hogy csak az *51*-es raktárban lévő munka jelenjen meg.
1. Győződjön meg róla, hogy csak a korábban létrehozott négy munkaazonosító jelenik meg.
1. Zárja be a **Munka** oldalt.

### <a name="mobile-device-flow-execution"></a>Mobileszköz folyamat végrehajtása

A beállítás alapján a rendszer a munkasorban szereplő legmagasabb mennyiségtől a legalacsonyabbig rendezett munkát fogja betölteni a felhasználó számára. Az összes sorban szereplő mennyiség kisebb lesz, mint 20 ea.

Ne feledje, hogy ez a beállítás rögzíti azokat a munkafolyamatokat, amelyeknek legalább egy sora van, ahol a mennyiség kevesebb, mint 20 ea. Ha tehát a munka rendelkezik egy másik sorral, ahol a mennyiség pontosan 20 ea vagy több, mint 20 ea, akkor is érvényes lesz.

#### <a name="mobile-app"></a>Mobilalkalmazás

1. Jelentkezzen be az *51*-es raktárban lévő felhasználóként a raktárkezelési alkalmazásba.
1. Lépjen a **Kimenő \> Értékesítési kitárolás – Rendszer** lehetőségre.

    Megjelenik a *4*. munkaazonosító kitárolási lépése. Ezt a munkaazonosítót először a rendszer által irányított lekérdezési rendelés beállítása miatt jelenik meg, ahol megadhatja, hogy a munkát csökkenő munkasormennyiség alapján kell sorba állítani.

1. Töltse ki a szükséges kitárolást és elhelyezést, és zárja be a munkaazonosítót.

    Ezután a *3.* munkaazonosító jelenik meg. Az egyik munkasora a sorban a következő a munkasor mennyisége alapján.

1. Töltse ki a kitárolást és elhelyezést, és zárja be a munkaazonosítót.

    Ezután a *2.* munkaazonosító jelenik meg. Ennek a munkának a kitárolási sora a következő a sorrendben.

1. Töltse ki a kitárolást és elhelyezést, és zárja be a munkaazonosítót.

    További munkának nem kell megjelennie. Az *1.* munkaazonosító nem jogosult ehhez a mobileszköz-menüelemhez, mert a lekérdezés azt határozza meg, hogy a munkafejlécek csak akkor vehetők figyelembe, ha a munkasorokban szereplő mennyiség kevesebb, mint 20 ea.

## <a name="tips"></a>Tippek

A rendszer által irányított munka sorrendbe állítás lekérdezések *inkluzívak*. Fontos, hogy néhány beállítás esetében ne feledkezzen meg erről. Például előfordulhat, hogy azt szeretné, hogy egy konkrét menüelem csak olyan munkát dolgozzon fel, ahol a munkaegység *ea*, és megadja ezt a korlátozást a lekérdezés **Tartomány** lapján. Ebben az esetben a dolgozó megkapja az összes olyan munkát, amelyben legalább egy munkasor az *ea* munkaegységgel van beállítva. Ennek megfelelően ez a munka olyan munkafolyamatot is tartalmazhat, amelyben a munkasorok nem az *ea* munkaegységgel rendelkeznek (például *doboz* vagy *raklap*). A lekérdezés csak akkor zár ki munkát, ha nincs olyan munkasor, ahol a munkaegység *ea* értékre van állítva.

Emiatt a forgatókönyv példájában a lekérdezés a *4.* munkaazonosítót is rögzítette. A létrehozásakor két sor lett hozzáadva: egy 25 ea-val, egy másik pedig 10 ea-val. A munka továbbra is megjelenik a felhasználó számára, mert legalább egy munkasornak 20 ea-nál kisebb a mennyisége.

A forgatókönyvtől függően megakadályozhatja ezt a viselkedést munkaszünetek segítségével.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]