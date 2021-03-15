---
title: Cikk-konszolidáció – hely kihasználtsága
description: Ez a témakör olyan funkcióról tartalmaz információkat, amely megkönnyítik a raktárvezetők számára hogy megtekintsék és szűrje a raktáraknak a raktáron belüli térfogat-kihasználását. A menedzserek kiválaszthatnak helyeket, és a cikkek konszolidálásához közvetlenül a cikk-összesítés lapon hozhatnak létre készletmozgatási munkát, és így jobban ki tudják használni a raktári helyet.
author: Mirzaab
manager: tfehr
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSPhysDimUOM, WHSMovementType, WHSItemConsolidationForm, WHSRFMenu, WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-16
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 6edabc51981d8935672b44e53b453cfbaca9031b
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "5004652"
---
# <a name="item-consolidation---location-utilization"></a>Cikk-konszolidáció – hely kihasználtsága

[!include [banner](../includes/banner.md)]

Ez a témakör olyan funkcióról tartalmaz információkat, amely megkönnyítik a raktárvezetők számára hogy megtekintsék és szűrje a raktáraknak a raktáron belüli térfogat-kihasználását. A menedzserek kiválaszthatnak helyeket, és a cikkek konszolidálásához közvetlenül a **Cikk-konszolidáció** lapon hozhatnak létre készletmozgatási munkát, és így jobban ki tudják használni a raktári helyet.

## <a name="turn-on-the-features"></a>A funkciók bekapcsolása

Az ebben a témakörben ismertetett szolgáltatások használata előtt be kell kapcsolni azokat a rendszerben. A rendszergazdák használhatják a [Funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) munkaterületet e funkciók állapotának ellenőrzéséhez, és szükség esetén a bekapcsolásához. A következő szolgáltatásokat kapcsolja be a listán szereplő sorrendben. (Mindkét funkció a **Raktárkezelés** modulhoz tartozik.)

1. Raktár helyállapota
2. Cikk-konszolidáció helyének kihasználtsága

## <a name="warehouse-location-status"></a>Raktár helyállapota

A *Raktár helyállapota* funkció négy új mezőt ad hozzá a **Helyek** oldalhoz a hely aktuális állapotával kapcsolatos további információk nyomon követése céljából:

- **Cikkszám** – Az a cikk, amely jelenleg a helyen van. Ha a hely több cikket tartalmaz, akkor ez a mező üres lesz.
- **Utolsó tevékenység dátuma és időpontja** – A helyen végrehajtott legutóbbi raktári tranzakció időbélyegzője.
- **Korosítási dátum** – Az a dátum, amikor a helyen található készletet bevitték a raktárba. Ezt az dátumot az azonosítótábla korosítási dátuma alapján számítja ki a program. Ugyan ez a dátum az azonosítótábla által nyomon követett helyek esetében pontos, de lehet, hogy nem pontos a nem azonosítótábla által nyomon követett helyek esetében.
- **Hely állapota** – A hely állapota. Négy érték érhető el:

    - **Meghatározatlan** – A helyprofil nem követi nyomon az állapotot. Ezért az aktuális állapot ismeretlen.
    - **Üres** – Jelenleg nincs készletet a helyen.
    - **Kitárolás** – Kimenő tranzakciókat hajtottak végre a helyen a legutóbbi üres állapot után.
    - **Tárolás** – Csak bemenő tranzakciókat hajtottak végre a hellyel szemben a legutóbbi üres állapot óta.

Ezeknél a mezőknél a raktári vezetők jobb áttekintést kaphatnak a raktári helyek állapotáról. Lehetővé teszik az összetettebb jelentéskészítést és szűrést is.

## <a name="set-up-item-consolidation-and-location-utilization"></a>Cikk-konszolidáció és helykihasználtság beállítása

Ez a szakasz bemutatja, hogyan kell előkészíteni a rendszert a cikk-konszolidáció és a helykihasználtság használatára. Az eljárások a mintaértékeket a szokásos demóadatokból használják. Ha azt tervezi, hogy a jelen témakörben később ismertetett példaforgatókönyvvel dolgozik, válassza ki a **USMF** jogi személyt (amely tartalmazza a standard demóadatokat), és hozza létre azokat a rekordokat, amelyeket ebben a szakaszban ismertetve vannak. Ha nem tervezi elvégezni a példaforgatókönyvet, akkor az itt megadott értékek példaként szolgálnak, hogy milyen típusú beállításokat kell végrehajtani a szolgáltatások használatához.

### <a name="released-product"></a>Kiadott termék

1. Kattintson a **Termékinformációk kezelése \> Termékek \> Kiadott termékek** lehetőségre.
1. A **Cikkszám** mezőben válassza ki az *M9201* elemet, majd nyissa meg a részletek lapot.
1. A Műveleti panelen, a **Készletkezelés lapon** a **Raktár** csoportban válassza ki a **Tényleges dimenziók** lehetőséget.
1. A **Tényleges méret** lap műveleti paneljén válassza ki az **Új** elemet.

    A program új sort ad hozzá a rácshoz. A **Cikkszám** mező előőre be van állítva.

1. Válassza ki az **Egység** mezőben az *ea* lehetőséget. A program automatikusan beállítja a sor fennmaradó mezőit.
1. Válassza a **Mentés** gombot, és zárja be az oldalt.

### <a name="location-profile"></a>Helyprofil

1. Ugorjon a **Raktárkezelés \> Beállítás \> Raktár \> Helyprofilok** pontra.
1. A helyprofilok listáján válassza az **5. EMELET** elemet.
1. A műveleti ablaktáblán válassza a **Szerkesztés** lehetőséget.
1. Győződjön meg arról , hogy az **Általános** gyorslapon a következő beállítások közül mindkettő az *Igen* értérek van beállítva:

    - Helyen levő cikk engedélyezése
    - Helyállapot engedélyezése

1. Válassza a **Mentés** lehetőséget.

    > [!IMPORTANT]
    > Ha a **Cikk engedélyezése helyen**, és a **Hely állapotának engedélyezése** beállítás már *Igen* értékre van állítva , ugorjon a **Dimenziók** gyorslap beállításával kapcsolatosa utasításokra a 10. lépésben. Ha a lehetőségek nem lettek volna beállítva *Igen* értékre , akkor a kézi beállítás után futtatnia kell a **Raktárkezelési modul** konzisztenciavizsgálatát. Ebben az esetben folytassa a következő lépéssel.

1. A konzisztencia-ellenőrzés futtatásához nyissa meg a **Rendszeradminisztráció \> Ismétlődő feladatok \> Adatbázis \> Konzisztenciaellenőrzés** lehetőségét.
1. Az **Konzisztenciaellenőrzés** párbeszédpanelen adja meg a következő értékeket:

    - **Modul:** *Raktárkezelés*
    - **Ellenőrzés/javítás:** *Ellenőrzés*
    - **Kezdő dátum:** hagyja üresen ezt a mezőt.
    - **A raktár helyállapotának konzisztencia-ellenőrzése:** Jelölje be ezt a jelölőnégyzetet.

1. Válassza ki az **OK** lehetőséget.

    > [!TIP]
    > Üzenet jelenik meg, ha a konzisztenciaellenőrzés befejeződött. Az üzenet megtekintéséhez nyissa meg a [Műveletközpontot](../../fin-ops-core/fin-ops/get-started/user-interface-elements.md#notifications). A részletek megjelenítéséhez kattintson az **Üzenet részletei** gombra.
    >
    > Ha a konzisztencia-ellenőrzés üzenete a következőt mondja: „Helytelen hely állapot információ található a (z) XXXX helyen az XX raktárban,” újra kell futtatnia a konzisztencia-ellenőrzést. Ez alkalommal állítsa be a **Ellenőrzés/javítás** mezőt *Hiba javítása* értékre. Tekintse meg az üzeneteket, hogy meggyőződjön arról, hogy a rendszer nem talált hibát.

1. Most be kell fejeznie a helyprofil beállítását. Térjen vissza a **Raktárkezelés \> Beállítások \> Raktár \> Helyprofilok** menübe, válassza ki az **5. EMELET** helyprofilt majd kattintson a műveleti panel **Szerkesztés** elemére.
1. Az **Dimenziók** gyorslapon állítsa be a következő értékeket:

    - **Térfogat-kihasználtság százalékos aránya:** *100*
    - **A készlethelyhez használt térfogat-meghatározási mód:** *Hely térfogatának használata*
    - **Hely tényleges magassága:** *10*
    - **Hely tényleges szélessége:** *10*
    - **Hely tényleges mélysége:** *10*
    - **Maximális súly:** *100*

1. Válassza a **Mentés** lehetőséget.

### <a name="mobile-device-menu-items"></a>Mobileszköz menüpontjai

1. Lépjen a **Raktárkezelés \> Beállítás \> Mobileszköz \> Mobileszköz-menüelemek** részre.
1. A művelet ablaktáblán válassza az **Új** parancsot a rendezéshez használandó menüelem létrehozásához.
1. A fejlécben állítsa be a következő értékeket:

    - **Menüelem neve:** *Korrigálás be*
    - **Cím:** *Korrigálás be*
    - **Mód:** *Munka*
    - **Meglévő munka használata:** *Nem*

1. Az **Általános** gyorslapon állítsa be a következő értékeket:

    - **Munkalétrehozási folyamat:** *Korrigálás be*
    - **Készlet-helyesbítési típusok:** *Korrigálás be*

1. Válassza a **Mentés** lehetőséget.

### <a name="mobile-device-menu"></a>Mobileszköz menü

1. Lépjen a **Raktárkezelés \> Beállítás \> Mobileszköz \> Mobileszköz menü** elemre.
1. A menük listáján válassza a **Készlet** elemet.
1. A műveleti ablaktáblán válassza a **Szerkesztés** lehetőséget.
1. A **Rendelkezésre álló menük és menüelemek** listájában keresse meg és válassza ki a **Korrigálás be** menüelemet.
1. Válassza a jobbra mutató nyilat a **Korrigálás be** áthelyezéséhez a **Menü struktúra** listába. Ily módon hozzáadja az új menüelemet a kijelölt menühöz.
1. Válassza a **Mentés** lehetőséget.

### <a name="movement-types"></a>Mozgástípusok

1. Ugorjon a **Raktárkezelés \> Beállítás \> Készlet \> Áthelyezés-típusok** pontra.
1. A Művelet panelen válassza az **Új** lehetőséget, majd állítsa be a következő értékeket:

    - **Áthelyezés típuskódja:** *KONSZOLIDÁCIÓ*
    - **Leírás:** *Helyek konszolidációja*
    - **Munkaosztály azonosítója:** *InvMov*

1. Válassza a **Mentés** lehetőséget.

## <a name="example-scenario"></a>Példaforgatókönyv

A következő eset egy mobileszköz raktári alkalmazásával végez készlet *korrigálást* a raktárban lévő két helyre.

### <a name="add-inventory-to-locations"></a>Készlet hozzáadása helyekhez

1. Jelentkezzen be a mobileszközbe olyan felhasználóként, aki a *51*. raktárban be van állítva.
1. Ugrás a **Készlet \> Korrigálás be** helyre.

    Ezt követően megadhatja az első helyhelyesbítést.

1. Válassza ki a **Helyesbítés be** feladatot, válassza ki a helyez, amelyhez elvégzi a készlethelyesbítést. A **HELY** mezőben válassza az *AT-001* elemet.
1. Hagyja jóvá a helyet.
1. Hozzon létre egy azonosító-azonosítót a helyhez adandó cikkhez. Az **Azonosítótábla** mezőben adja meg a *LP00101* értéket.
1. Az azonosítótábla jóváhagyása.
1. Az azonosítótáblához hozzáadandó elem megadása. Az **ITEM** mezőben adja meg a *M9201* értéket.
1. Erősítse meg a cikket.
1. Az azonosítótáblához hozzáadandó mennyiség megadása. A **MENNY** mezőben adja meg a *10* értéket.
1. Nyugtázza a mennyiséget.

    A „Munka befejezve” üzenet jelenik meg. Ezt követően megadhatja a második helyhelyesbítést.

1. Válassza ki a **Helyesbítés be** feladatot, válassza ki a helyez, amelyhez elvégzi a készlethelyesbítést. z **HELY** mezőben válassza az *AT-002* elemet.
1. Hagyja jóvá a helyet.
1. Hozzon létre egy azonosító-azonosítót a helyhez adandó cikkhez. Az **Azonosítótábla** mezőben adja meg a *LP00201* értéket.
1. Az azonosítótábla jóváhagyása.
1. Az azonosítótáblához hozzáadandó elem megadása. Az **ITEM** mezőben adja meg a *M9201* értéket.
1. Erősítse meg a cikket.
1. Az azonosítótáblához hozzáadandó mennyiség megadása. A **MENNY** mezőben adja meg a *15* értéket.
1. Nyugtázza a mennyiséget.

    A „Munka befejezve” üzenet jelenik meg.

1. Válassza ki a lap tetején látható Menü gombot (néha hamburgernek vagy a hamburgergombnak is nevezik), majd válassza ki a **Mégse** lehetőséget a **Korrekció itt:** feladatból való kilépéshez.

### <a name="consolidate-locations"></a>Helyek konszolidálása

1. Ugrás a **Raktárkezelés \> Ismétlődő feladatok \> Cikkek konszolidációja** helyre.
1. A fejlécben válassza ki azt a raktárt, amelybe a konszolidálást el szeretné végezni. A **Raktár** mezőben adja meg az *51* értéket.

    Egy rekord jelenik meg minden olyan helyen, ahol az *M9201* cikket helyesbítették. A **Kihasználtság százalékos aránya** oszlopa az egyes helyek térfogat szerinti kihasználtságát jeleníti meg.

1. A készlet konszolidálásához válassza ki az összes olyan helyet, amelyet konszolidálni kell, majd a műveleti ablaktáblán válassza ki a **Készlet konszolidálása** lehetőséget.
1. A **Készlet konszolidálása** párbeszédpanelen adja meg azt a helyet és áthelyezési típust, amelyet a készlet-áthelyezési munka létrehozásához kell használni. Adja meg az alábbi értékeket:

    - **Hely:** *AT-001*
    - **Áthelyezés típuskódja:** *KONSZOLIDÁCIÓ*

1. Válassza ki az **OK** lehetőséget.
1. Olyan tájékoztató üzenet érkezik, amely az adott kiadásból létrehozott áthelyezési munkát jeleníti meg. Jegyezze fel az áthelyezési munka azonosítóját.

### <a name="view-movement-work"></a>Áthelyezési munka megtekintése

1. Ugorjon a **Raktárkezelés \> Munka \> Munka részletei** pontra.
1. A létrehozott áthelyezési munka megtekintése. A készlet-konszolidáció áthelyezésimunka-azonosítójának használatával szűrhet vagy kereshet a munkarácson.

    Ebben a helyzetben egy létező, már készlettel rendelkező hely volt használva a készlet-konszolidáció helyének. Ennélfogva csak egy munkaazonosító jött létre.

    > [!NOTE]
   > A rendszer minden lépéshez létrehoz egy munkaazonosítót, amelyet végre kell hajtani. Ha olyan helyet ad meg, amely már tartalmaz készletet, csak egy munkaazonosító jön létre. Ha új helyet ad meg, akkor két munkaazonosító jön létre.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]