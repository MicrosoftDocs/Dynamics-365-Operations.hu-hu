---
title: Rendszer által irányított fürtkitárolás
description: Ez a témakör áttekintést nyújt a rendszer által fürtkitárolásról a Microsoft Dynamics 365 Supply Chain Management alkalmazásban.
author: Mirzaab
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSWorkCluster, WHSClusterProfile
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-12-31
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 3c474705e5260f4be62bc59d8d1d84a1ba597b6f96eafd8f673cc110285fc597
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6772352"
---
# <a name="system-directed-cluster-picking"></a>Rendszer által irányított fürtkitárolás

[!include [banner](../includes/banner.md)]

A fürtkitárolás egy darabkitárolási folyamat, amely lehetővé teszi, hogy egy időben több rendelést is kitároljunk, és kivételezési fürtökhöz csoportosítsuk őket. Ezután csak egyszer kell felkeresnie a kivételezési helyet. Ez a funkció általában kis megrendelés kivételezéshez vagy esetmennyiségnél kisebb mennyiségekre használható.

Ha be van állítva a rendszer által irányított fürtkitárolás, a rendszer által létrehozott fürt alapján munkafejléceket is lehet fürtben kitárolni. A rendszer legfeljebb a fürtprofilban megadott számú pozíciókhoz tárolja ki fürtben a rendeléseket. Ezért a fürt manuális létrehozása nélkül egyszerre több rendelést is kitárolhat.

A rendszer által irányított fürtkitárolás alternatívát kínál a fürt kézi felépítéséhez, ahol fürtprofilt használnak a fürt létrehozásához. A fürtprofilban több, beállítással kapcsolatos sort kell definiálni a használata előtt:

- A **Pozíciók száma** a fürtre kerülő rendelések számára vonatkozik. Ezért, hogy megfelel a táskák számának.
- A **Fürt felbontása** meghatározza, hogy mikor kell felbontani a fürtöt.
- A **Fürtazonosító előállítása** határozza meg, hogy a rendszer létrehozza-e a fürtazonosítót, vagy a felhasználó adja-e meg azt.
- A **Rendezés ellenőrzési típusa** meghatározza, hogy szükség van-e pozícióellenőrzésre.

A rendszer által irányított fürtkitároláshoz egy új mobileszköz-menüelem használatos. A **fürtprofil azonosítóját** meg kell adni a kiválasztott **Irányítja** beállítás számára. Ezenfelül a rendszer által irányított munkasorozat-lekérdezés csoportosíthatja a rendeléseket a vállalatra jellemző feltételek alapján. Ezért a munkarendelések hozzárendelését tovább optimalizálhatja a rendszer által irányított munkasorozat-lekérdezés testreszabott rendezési feltételeinek megadásával.

A rendszer által irányított fürtkitárolás engedélyezése esetén a raktári dolgozók számára olyan fürt jelenik meg, amelyben a kitárolási rendeléseket eleve hozzárendelték a fürtpozíciókhoz. Ezért a dolgozók több munkához is kitárolhatják a cikkeket, és ehhez csak egyszer kell felkeresniük a kitárolási helyet. A rendszer által irányított fürtkitároláshoz tartozó kitárolási folyamat megegyezik a felhasználó által irányított fürtkitárolási folyamattal.

## <a name="enable-the-system-directed-cluster-picking-feature"></a>A rendszer által irányított fürtkitárolási funkció engedélyezése

A funkció használata előtt engedélyeznie kell a saját rendszerében. A rendszergazdák használhatják a [funkciókezelési](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) oldalt a funkció állapotának ellenőrzéséhez, és szükség esetén engedélyezéséhez. Itt a funkció a következőként szerepel:

- **Modul:** Raktárkezelés
- **Funkció neve:** A rendszer által irányított fürtkitárolás

Ennek a funkciónak szüksége van egy függő funkció engedélyezésére. A függő funkció a következő:

- **Modul:** Raktárkezelés
- **Szolgáltatás neve** – Szervezeti szintű rendszer által irányított munka sorrendbe állítása

## <a name="set-up-system-directed-cluster-picking"></a>Rendszer által irányított fürtkitárolás beállítása

### <a name="create-cluster-profiles"></a>Fürtprofilok létrehozása

A fürtprofilok vezérlik, hogyan hozza létre a rendszer az egyes fürtöket. Ha különböző fürtökre van szükség, akkor minden mobileszköz-menüelemhez egy másik fürtprofilt kell létrehozni.

1. Kattintson a **Raktárkezelés \> Beállítás \> Mobileszköz \> Fürtprofilok** elemre.
2. Válassza az **Új** lehetőséget.
3. A **Fürtprofil azonosítója** mezőbe írja be a **2 pozíció** értéket.
4. A **Név** mezőbe írja be a **2. pozíció** értéket.
5. Adja meg a következő adatokat az **Általános** gyorslapon:

    - **Fürtazonosító létrehozása** – Válassza az **Igen** lehetőséget. Ez a beállítás határozza meg, hogy a rendszer automatikusan hozza-e létre a fürtazonosítót, vagy hogy a felhasználó hozza-e létre azt a kitárolás kezdetén. 
    - **Beosztások aktiválása** - Válassza az **Igen** lehetőséget. Ez a beállítás határozza meg, hogy a pozíciónevek automatikusan létrejönnek-e a pozíciónév beállítása alapján. Ha ez az opció **Nem** értékre van beállítva, akkor a pozíció azonosítótábla-azonosítója kerül felhasználásra.
    - **Pozíciók száma** – Írja be a **2** értéket. Ez a mező határozza meg, hogy a fürt legfeljebb hány pozícióval rendelkezhet (vagyis a dobozok, táskák és egyebek maximális számát).
    - **Pozíció neve:** – Válassza a **Numerikus** értéket, hogy a pozíciók egymást követő számok használatával legyenek elnevezve. Ha a **Betűrendben** beállítást jelöli ki, a rendszer a pozíciókat ábécérendben nevezi el.
    - **Fürt felbontása ennél** – Válassza a **Betárolás** lehetőséget. Ez a mező határozza meg, hogy mikor legyen felbontva a fürt. 
    - **Rendezés ellenőrzési típusa** – Válassza a **Pozíció beolvasása** lehetőséget. Ez a mező határozza meg, hogy a betárolási lépés ellenőrzésre került-e.
        
6. A **Fürtrendezés** gyorslapon új sor létrehozásával és a következő információk megadásával definiálhat rendezési feltételeket:

    - **Sorszám** – Válassza ki az **1** elemet. Ez a mező azt a sorozatot határozza meg, amely szerint a rendszer rendez. Az érték bevitele automatikus, de szükség esetén módosítható.
    - **Mező neve** – Írja be a **WMSLocationId** értéket. Ez a mező határozza meg azt a mezőt, amelyet a sor a rendezési feltételként használ.
    - **Rendezés** – Válassza a **Növekvő** értéket. Ez a mező határozza meg, hogy a rendezés növekvő vagy csökkenő sorrendben történjen-e.

### <a name="create-a-mobile-device-menu-item"></a>Mobileszköz-menüpont létrehozása

Ha új mobileszköz-menüelemet szeretne létrehozni a rendszer által irányított fürt kitárolása céljából, és csatolni kívánja a fürtprofil azonosítóját a mobileszköz menüelemhez, kövesse az alábbi lépéseket.

1. Ugrás a **Raktárkezelés > Beállítás > Mobileszköz > Mobileszköz menü elemek** lehetőségre.
1. Válassza az **Új** lehetőséget.
1. Adja meg a következő adatokat a fejléc szakaszban:
    - **Menüelem neve** – SD-fürt
    - **Cím** – SD-fürt
    - **Mód** – Munka
    - **Meglévő munka használata** – Igen

1. Adja meg a következő adatokat az **Általános** gyorslapon:
    - **Irányítja** – Rendszer által irányított fürtkitárolás
    - **Azonosítótábla létrehozása** – Igen
    - **Fürtprofil azonosítója** – 2. pozíció

1. A **Munkaosztályok** gyorslapon a következő mezők beállításával állíthatja be a mobileszköz menüelemének érvényes munkaosztályát:
    - **Munkaosztály azonosítója** – Értékesítés
    - **Munkarendelés típusa** – Értékesítési rendelések

1. A **mobileszköz menü cikkek** műveleti paneljén válassza ki a **rendszer által irányított munkaszekvencia-lekérdezéseket**, majd kövesse az alábbi lépéseket az új rendszer által irányított munkaszekvencia-lekérdezés megadásához:
    - A műveleti ablaktáblán válassza ki az **Új** elemet.
    - **Sorszám** – 1
    - **Leírás** – Munkaprioritás – Munka azonosítója

1. A műveleti ablaktáblán válassza a **Lekérdezés szerkesztése** lehetőséget
1. Lépjen a **Rendezés** lapra
1. Új sor hozzáadásához kattintson a **Hozzáadás** gombra, majd írja be a következőt:
    - **Táblázat** – Munka
    - **Származtatott tábla** – Munka
    - **Mező** – Munka prioritása
    - **Keresés iránya** – Csökkenő
1. Második sor hozzáadásához kattintson a **Hozzáadás** gombra, majd írja be a következőt:
    - **Táblázat** – Munka
    - **Származtatott tábla** – Munka
    - **Mező** – Munkaazonosító
    - **Keresés iránya** – Csökkenő

1. A rendszer most rendezni fogja a munkaazonosítókat a fürtben, először a munka prioritása, majd a munkaazonosító szerint.

### <a name="set-up-a-mobile-device-menu"></a>Mobileszköz-menü beállítása

1. Ugrás a **Raktárkezelés > Beállítás Mobileszköz > Mobileszköz menüre**.
1. A most létrehozott **SD-fürt** menüpontot hozzá kell adni a mobileszköz menühöz.
1. Válassza ki a **Kimenő** menüt.
1. A műveleti ablaktáblán válassza a **Szerkesztés** lehetőséget.
1. Görgessen addig, amíg meg nem találja az **SD-fürt** elemet.
1. Válassza ki az **SD-fürt** elemen, a program engedélyezi a **Menü struktúrájára** mutató nyilat.
1. A **nyíl** gombra kattintva mozgathatja az **SD-fürt** menüelemét a **Kimenő** menü struktúrájába.
1. Válassza ki az **SD-fürt** elemet a **menü szerkezete** listából, majd a **felfelé** vagy **lefelé** mutató nyilakra kattintva helyezze át a menüelemet a mobileszköz menü kívánt helyére.

## <a name="scenario"></a>Forgatókönyv

### <a name="create-picking-work"></a>Kitárolási munka létrehozása

A rendszer által irányított fürtkitárolás beállítása előtt alkalmas kimenő munkát kell létrehoznia. A korábban létrehozott fürtprofil két fürtpozíciót határoz meg. Ezért legalább két munkaazonosítót kell létrehoznia. Ebben a helyzetben két értékesítési rendelést hoz létre, készletet foglalhat le, felszabadítja az értékesítési rendeléseket a raktárba, majd manuálisan feldolgozza a hullámot.

1. Lépjen az **Értékesítés és marketing > Értékesítési rendelések > Minden értékesítési rendelés** menüpontra.
1. Az első értékesítési rendelés létrehozásához kattintson a Műveleti ablaktábla panelen az **Új** elemet.
    - Megjelenik az **Értékesítési rendelés létrehozása** menü, írja be a következő adatokat:
        - A **Vevő** gyorslapon adja meg ezt: **Vevői számla** - **USA-004**.
        - Adja meg az **Általános** gyorslapon: **Raktár** - **62**.
        - Válassza az **OK** gombot a menü bezárásához és az értékesítési rendelés létrehozásához.
    - Az **Értékesítésirendelés-sor** gyorslapon válassza a **Sor hozzáadása** lehetőséget, ha nem ad hozzá új sort a program, és adja meg a következőt:
        - **Cikkszám** – 0001
        - **Mennyiség** – 1
        - Második sor hozzáadásához válassza a **Sor hozzáadása** lehetőséget.
        - **Cikkszám** – A0002
        - **Mennyiség** – 3
    - Készlet foglalása az imént létrehozott sorokhoz.
        - **1. sor** kijelölése.
        - Az **Értékesítési rendelés sorai** műveleti panelen válassza a **Készlet**, majd a **Foglalás** elemet a listáról.
        - A **Foglalás** képernyőn válassza ki a **Készlet foglalása** elemet a készlet lefoglalásához.
        - Zárja be a **Foglalás** képernyőt, amikor a foglalás kész.
        - Hajtsa végre ezeket a lépéseket a **2. sorra** vonatkozó készlet foglalásához.
1. A második értékesítési rendelés létrehozásához kattintson a Műveleti ablaktábla panelen az **Új** elemet.
    - Megjelenik az **Értékesítési rendelés létrehozása** menü, írja be a következő adatokat:
        - A **Vevő** gyorslapon adja meg ezt: **Vevői számla** - **USA-005**.
        - Adja meg az **Általános** gyorslapon: **Raktár** - **62**.
        - Válassza az **OK** gombot a menü bezárásához és az értékesítési rendelés létrehozásához
    - Az **Értékesítésirendelés-sor** gyorslapon válassza a **Sor hozzáadása** lehetőséget, ha nem ad hozzá új sort a program, és adja meg a következő információt:
        - **Cikkszám** – 0001
        - **Mennyiség** – 4
        - Második sor hozzáadásához válassza a **Sor hozzáadása** lehetőséget.
        - **Cikkszám** – A0002
        - **Mennyiség** – 2
    - Készlet foglalása az imént létrehozott két sorhoz.
        - **1. sor** kijelölése.
        - Az **Értékesítési rendelés sorai** műveleti panelen válassza a **Készlet**, majd a **Foglalás** elemet a listáról.
        - A **Foglalás** képernyőn válassza ki a **Készlet foglalása** elemet a készlet lefoglalásához.
        - Zárja be a **Foglalás** képernyőt, amikor a foglalás kész.
        - Hajtsa végre ezeket a lépéseket a **2. sorra** vonatkozó készlet foglalásához.
    - Zárja be az értékesítési rendelést, és térjen vissza az **Összes értékesítési rendelés** listaoldalra.
1. Keresse meg a most létrehozott két értékesítési rendelést (előfordulhat, hogy frissítenie kell a lapot). A táblában jelölje be mindkét értékesítési rendelést a szakasz jelölőnégyzetének használatával.
    - A **Minden értékesítési rendelés** műveleti paneljén válassza a **Raktár** fület.
    - A **Műveletek** csoportban válassza a **Kiadás a raktárba lehetőséget**, ha mindkét értékesítési rendelést fel szeretné adni a raktárba.
1. Amikor a kiadás a raktárba folyamatba kész, a program tájékoztató üzenetet jelenít meg.
    - A program minden értékesítési rendeléshez létrehoz szállítmányt.
    - A program hullámot hoz létre, és mindkét szállítmányt a hullámhoz rendeli hozzá. Jegyezze fel a **hullámazonosítót**.
1. Ugorjon a **Raktárkezelés > Kimenő hullámok > Szállítmányhullámok > Minden hullám** menübe.
    - A **Minden hullám** listán keresse meg és válassza ki az előző lépésben létrehozott **hullámazonosítót**.
    - Válassza a **Hullám** lapot a műveleti ablakban.
    - A **hullám** csoportban válassza ki a **Feldolgozás** elemet a hullám feldolgozásához és a **Munka** létrehozásához.
    - A program a feldolgozás befejeződése esetén tájékoztató üzenetet hoz létre, jelezve, hogy a rendszer létrehozta a munkát, és feladta a hullámot.
1. **Nem kötelező:** Ugrás a **Raktárkezelés > Munka > Munkarészletek** elemre a létrehozott munka megtekintéséhez. Két különböző munkaazonosító jön létre. Minden munkaazonosítóhoz két kivételezési sor tartozik.

### <a name="run-the-mobile-device-flow"></a>Futtassa a mobileszközön a folyamatot

1. Jelentkezzen be a **62**-es raktárban lévő felhasználó számára a mobileszközön.
1. Válassza a **Főmenü** **Kimenő** elemét.
1. Válassza ki a **Kimenő** menüben az **SD-fürt** menüelemet a kitárolás kezdeményezéséhez.
    - Létrejön egy fürt, és a két korábban létrehozott munkaazonosító hozzá van csatolva. Ha kettőnél több munkaazonosítót hozott létre, csak az első kettő kerül hozzáadásra a fürthöz. Figyelje meg, hogy a munkaazonosítók növekvő sorrendben adódnak hozzá a fürthöz, ahogy a lekérdezési beállításnál megadta.

    > [!NOTE]
    > Az új fürt létrehozása csak akkor történik meg, ha korábban már elég további munkaazonosítót hoztak létre. Ellenkező esetben a következő üzenet jelenik meg: „A fürthöz nincs elegendő munka.”

    - Miután kiválasztotta a menüt, megjelenik az első kitárolási képernyő. A rendszer összesíti a két munkaazonosítóból az összes egyező kitárolási sort, és a kitárolási hely egyszeri meglátogatására utasítja, így egy kitárolással mindkét rendelést teljesítheti. Ez a folyamat ugyanúgy történik, mint a felhasználó által irányított fürtkitárolás folyamata.

1. Az **OK** gombra kattintva nyugtázza az első kitárolási helyet és a tételt.
    - A kitárolás mennyisége a fürt értékesítési rendeléseiben megjelenített cikkmennyiség összege lesz.
1. Adja meg a hely nevét (szám vagy betű) annak igazolására, hogy a helyhez kitárolt cikkmennyiség a megfelelő helyre került.
1. Ismételje meg ezt a folyamatot, amíg az összes cikkmennyiséget ki nem tárolta és a megfelelő pozícióba nem helyezte.
1. A mobileszköz utolsó lépés az, hogy a fürtöt a végleges helyre **Betároljuk**. Válassza ki az **OK** lehetőséget
    - Ha a betárolási művelet meg van erősítve, a fürt bezáródik és felbontásra kerül, a fürtprofilban lévő **Fürt felbontása ennél** mezőben beállított érték alapján. A munkaazonosítók szintén lezárásra kerülnek.
1. A mobileszközön a „Fürt befejezve” üzenet jelenik meg.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]