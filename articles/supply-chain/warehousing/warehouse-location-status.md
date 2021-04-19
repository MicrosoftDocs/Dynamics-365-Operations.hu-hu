---
title: Raktár helyállapota
description: Ez a témakör áttekintést nyújt a Raktár helyállapota funkcióról.
author: Mirzaab
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLocationProfile,WHSLocation
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: 4f31fd424760aa677df9235e53dc4af20cc2ea94
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5837345"
---
# <a name="warehouse-location-status"></a>Raktár helyállapota

[!include [banner](../includes/banner.md)]

A Microsoft Dynamics 365 Supply Chain Management számos olyan helymezőt tartalmaz, amellyel rugalmasan kezelheti és tarthatja karban a helyeket. A helyutasítás lekérdezésben beillesztheti a hely állapotát a raktári folyamat pontosabb ellenőrzésére.

A **Helyek** lapon a következő négy mező követi nyomon a hely aktuális állapotára vonatkozó információkat. Ezeknél a mezőknél a raktári vezetők áttekintést kaphatnak a raktári helyek állapotáról. Lehetővé teszik a speciális jelentéskészítést és szűrést is.

- **Cikkszám** – Az a cikk, amely jelenleg a helyen van. Ha a hely több cikket tartalmaz, akkor ez a mező üres.
- **Utolsó tevékenység dátuma és időpontja** – A helyen végrehajtott legutóbbi raktári tranzakció időbélyegzője.
- **Korosítási dátum** – Az a dátum, amikor a helyen található készletet bevitték a raktárba. Ezt az értéket az azonosítótábla korosítási dátuma alapján számítja ki a program. Ez az azonosítótábla által nyomon követett helyek esetében pontos, de lehet, hogy nem pontos a nem azonosítótábla által nyomon követett helyek esetében.
- **Hely állapota** – A hely állapota. Négy lehetséges érték van:

    - **Meghatározatlan** – A helyprofil nem képes nyomon követni az állapotot. Ezért az aktuális állapot ismeretlen.
    - **Üres** – Jelenleg nincs készletet a helyen.
    - **Kitárolás** – Kimenő tranzakciókat hajtottak végre a helyen a legutóbbi üres állapot óta.
    - **Tárolás** – Csak bemenő tranzakciókat hajtottak végre a helyen a legutóbbi üres állapot óta.

## <a name="turn-on-the-warehouse-location-status-feature"></a>A Raktár helyállapota funkció bekapcsolása

A *Raktár helyállapota* funkciót használata előtt be kell kapcsolni a rendszerben. A rendszergazdák használhatják a [funkciókezelési](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) beállításokat a funkció állapotának ellenőrzéséhez, és szükség esetén bekapcsolásához. A **Funkció kezelése** munkaterületen a funkció a következő módon van listázva:

- **Modul:** *Raktárkezelés*
- **Funkció neve:** *Raktár helyállapota*

## <a name="set-up-warehouse-location-status"></a>A Raktár helyállapotának beállítása

### <a name="prepare-the-sample-data-that-is-required-for-the-example-scenario"></a>Készítse elő a példaesethez szükséges mintaadatokat

Mielőtt elkezdené a munkafolyamatot, aktiválni kell a mintaadatokat, és be kell állítania a szolgáltatást az ebben a szakaszban ismertetett módon. A példahelyzet végrehajtásához a Raktárkezelés mobilalkalmazást vagy a böngésző alapú emulátort kell használni. Az itt megadott lépések a Raktárkezelés mobilalkalmazást használják. A böngészőalapú emulátor lépései hasonlóak.

#### <a name="use-the-usmf-legal-entity"></a>Az USMF jogi személy használata

Ha ezt a példaforgatókönyvet az itt megadott mintaadatok és értékek alapján kívánja elvégezni, akkor egy olyan rendszert kell használnia amelynél a szokásos [demóadatok](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) telepítve vannak. Emellett az **USMF** jogi személyt is ki kell választani a kezdés előtt.

#### <a name="set-up-location-profiles"></a>Helyprofilok beállítása

A példaforgatókönyvhöz két helyprofilt kell előkészíteni.

1. Ugorjon a **Raktárkezelés \> Beállítás \> Raktár \> Helyprofilok** pontra.
1. Válassza ki a **Szerkesztés** parancsot, hogy a lapot szerkesztési módba helyezze.
1. Jelölje ki az **ÖMLESZTETT-06** profilt.
1. Az **Általános** gyorslapon állítsa be a következő értékeket:

    - **Cikk engedélyezése a helyen:** Állítsa a beállítás értékét _Igen_ értékre.
    - **Hely tevékenységi dátumának és időpontjának engedélyezése:** Ezt a beállítást állítsa _Igen_ értékre.
    - **Helyállapot engedélyezése:** Állítsa a beállítás értékét _Igen_ értékre.

    Ezek a beállítások határozzák meg, hogy a hely hivatkozási mezői aktívak-e.

1. Ismételje meg a 3–4. lépést a **KITÁROLÁS-06** profil esetében.

> [!NOTE]
> Ha a hely profiljának paraméterei (**Cikk engedélyezése helyen**, **Helytevékenység engedélyezése**, **Helyállapot engedélyezése**) *Igen* értékre vannak állítva , akkor a rendszer azonnal frissíti a megfelelő helyeket *A raktár helyállapotának konzisztencia-ellenőrzése* feladatának végrehajtásával.

### <a name="scenario"></a>Forgatókönyv

1. Menjen a **Beszerzés és forrás \> Beszerzési rendelés \> Összes beszerzési rendelés** pontra.
1. Válassza az **Új** lehetőséget.
1. Válassza a **Beszerzési rendelés létrehozása** párbeszédpanel **Szállító** gyorslapjának **Szállítói számla** mezőjében a *104* értéket.
1. Az **Általános** gyorslap **Raktár** mezőjében válassza ki a *61* értéket.
1. Válassza ki az **OK** lehetőséget.
1. A program megnyitja az új beszerzési rendelést (PO). Tartalmaz egy üres sort a **Beszerzési rendelés sorai** rácsban. Ezen a soron állítsa be a következő értékeket:

    - **Cikkszám:** _A0002_
    - **Mennyiség:** _5_

1. A Műveleti ablaktáblán, a **Beszerzés** lapon a **Műveletek** csoportban kattintson a **Megerősítés** elemre a beszerzési rendelés megerősítéséhez.
1. A mobileszközön lépjen a **Bejövő \> Beszerzés fogadása** elemre.
1. Válassza ki a **PONUM** mezőt, majd adja meg a PO számát, és erősítse meg.
1. Válassza ki a **CIKK** mezőt, majd adja meg cikkszámként az *A0002* értéket, és erősítse meg.
1. A **MENNYISÉG** oldalon írja be az *5* értéket mennyiségként, majd erősítse meg.

    A mennyiséget a következő módok egyikén adhatja meg:

    - Numerikus érték hozzáadásához vagy kivonásához válassza a pluszjelet (**+**) vagy a mínuszjelet (**–**) tartalmazó gombot.
    - Válassza a pluszjel (**+**) és a mínusz jel (**–**) gomb között látható üres mezőt a számbillentyűzet megnyitásához.

1. Hagyja jóvá az *A0002* cikkszám és az *5* mennyiség kiválasztását. A „Munka befejezve” üzenet jelenik meg a lap alján.
1. Válassza ki a jobb felső sarokban látható Menü gombot (más néven hamburger vagy a hamburgergomb), majd válassza a **Mégse** lehetőséget a **Beszerzés fogadása** lehetőségből való kilépéshez, és a **Bejövő** menühöz való visszatéréshez.
1. A beszerzési rendelés lapon válassza ki **Munka részletei** elemet a **Beszerzési rendelés sorai** rács felett.
1. Az **Általános** lapon figyelje meg a létrehozott **Munkaazonosító** és **Cél azonosítótábla-azonosító** értékeket.
1. A **Sorok** szakaszban figyelje meg a **Hely** értékeket a *Kitárolás* és a *Betárolás* munkatípusok esetében.
1. A mobileszközön lépjen a **Bejövő \> Beszerzés elraktározása** elemre.
1. Válassza ki az **AZONOSÍTÓ** mezőt, majd adja meg a munkaazonosítót, és erősítse meg.
1. A *Kitárolás* bejegyzés befejezéséhez ismételten hagyja jóvá.
1. Válassza ki a Menü gombot a lap jobb felső sarkában, majd válassza a **Kész** lehetőséget a *Kitárolás* munka befejezéséhez.
1. Jegyezze fel az Eltárolás helyét, és erősítse meg. A „Munka befejezve” üzenet jelenik meg a lap alján.
1. Jelölje be a jobb felső sarokban látható menü gombot, majd a **Mégse** gombra kattintva lépjen ki **Beszerzés elraktározása** lehetőségből, és térjen vissza a **Bejövő** menübe.
1. A **Vissza** gombot kiválasztva térjen vissza a főmenübe.
1. A Dynamics 365 Supply Chain Management alkalmazásban lépjen a **Raktárkezelés \> Beállítás \> Raktár \> Helyek** pontra.
1. Szűrjön **Hely** alapján, és adja meg az eltárolás helyét a beszerzési rendelés munkájából. A következő eredményeket kell látnia:

    - A **Hely állapota** oszlop a *Tárolás* egy értékét jeleníti meg, mivel a legutóbbi tranzakció ezen a helyen eltárolás volt.
    - A **Cikkszám** oszlop az *A0002* értékét jeleníti meg, mivel a cikk beérkezett és a helyre került.
    - A **Legutóbbi tevékenység dátuma és időpontja** oszlop azt a dátumot és időbélyegzőt jeleníti meg, amikor a munkát a helyen befejezték.

1. A mobileszközön lépjen a **Minőség \> Mozgás** helyre.
1. Válassza ki a **LOC/LP** mezőt, és adja meg az előző lépésben feljegyzett helyet.
1. Erősítse meg a megjelenített adatokat. Jegyezze fel a létrejövő azonosítótáblát.
1. A **Cél információk** képernyőn válassza ki a **LOC/LP** mezőt, és adja meg a *06A07R2S1B* értéket, a cikk áthelyezésének célhelyeként.
1. A **Cél információk** képernyőn hagyja jóvá az **LP** értékét (a cél azonosítótábla azonosítója), amely automatikusan létrejön. A „Munka befejezve” üzenet jelenik meg a lap alján.
1. Jelölje be a jobb felső sarokban látható menü gombot, majd a **Mégse** gombra kattintva lépjen ki a **Mozgás** lehetőségből, és térjen vissza a **Minőségkezelés** menübe.
1. A **Vissza** gombot kiválasztva térjen vissza a főmenübe.
1. A Dynamics 365 Supply Chain Management alkalmazásban lépjen a **Raktárkezelés \> Beállítás \> Raktár \> Helyek** pontra.
1. Frissítse a **Helyek** oldalt, és tekintse meg újra az eredeti eltárolás helyét. Figyelje meg, hogy a **Helyállapot** mező most *Üres* értékre van állítva, és a **Cikkszám** oszlop üres.
1. Tekintse meg a *06A07R2S1B* helyhez tartozó rekordot, és figyelje meg, hogy az **Állapot** érték *Tárolás* értékre módosult, és frissültek a **Cikkszám** és az **Utolsó tevékenység dátuma és időpontja** mezők.
1. Ugorjon az **Értékesítés és marketing \> Értékesítési rendelések \> Minden értékesítési rendelés** pontra.
1. Válassza az **Új** lehetőséget.
1. Az **Értékesítési rendelés létrehozása** párbeszédpanelen, a **Vevői számla** mezőben válassza ki azt az *US-002* értéket.
1. A **Raktár** mezőben válassza ki az *61* értéket.
1. Válassza ki az **OK** lehetőséget.
1. A program megnyitja az új értékesítési rendelést. Tartalmaz egy üres sort az **Értékesítési rendelés sorai** rácsban. Ezen a soron állítsa be a következő értékeket:

    - **Cikkszám:** _A0002_
    - **Mennyiség:** _1_

1. Az **Értékesítési rendelés sorai** gyorslap **Készlet** menüjében válassza a **Foglalás** lehetőséget.
1. A **Foglalás** oldalon válassza ki a **Készlet foglalása** elemet a rendelési sor lefoglalásához. Ezután válassza a **Bezárás** gombot (**X**) a jobb felső sarokban az oldal bezárásához.
1. Válassza ki a művelet ablaktáblán a **Raktár** lapon a **Műveletek** csoportjának **Kiadás raktárba** parancsát.
1. Az **Értékesítési rendelés sorai** szakasz **Raktár** menüjében válassza a **Munka részletei** lehetőséget.
1. Másolja a létrehozott **Munkaazonosító** értéket.
1. A mobileszközön nyissa meg a **Kimenő \> Ertékesítési kitárolás** lehetőséget.
1. Válassza ki az **AZONOSÍTÓ** mezőt, majd adja meg a korábban másolt munkaazonosítót, és erősítse meg.
1. Az **Értékesítési rendelések: Kitárolás** lapon a **LOC** mező a kitárolási helyet javasolja a korábban létrehozott eltárolási helyként. Jegyezze fel a helyet.
1. Válassza ki a **LOC** mezőt, majd adja meg a helyet, és erősítse meg.
1. Válassza ki az **LP** mezőt, írja be azt az azonosítótáblát, amelyről a Mozgás tevékenység során feljegyzést készített, majd hagyja jóvá.
1. Válassza ki a **Cikk** mezőt, majd adja meg cikkszámként az *A0002* értéket, és erősítse meg.
1. A **MENNYISÉG** oldalon írja be az *1* értéket mennyiségként, majd erősítse meg.

    A mennyiséget a következő módok egyikén adhatja meg:

    - Numerikus érték hozzáadásához vagy kivonásához válassza a pluszjelet (**+**) vagy a mínuszjelet (**–**) tartalmazó gombot.
    - Válassza a pluszjel (**+**) és a mínusz jel (**–**) gomb között látható üres mezőt a számbillentyűzet megnyitásához.

1. Válassza ki a **CÉL LP** mezőt, adjon meg egy felhasználó által definiált cél azonosítótábla-azonosítót, majd hagyja jóvá.
1. A kitárolási munka befejezéséhez ismételten hagyja jóvá. A „Munka befejezve” üzenet jelenik meg a lap alján.
1. Jelölje be a jobb felső sarokban látható Menü gombot, majd a **Mégse** gombra kattintva fejezze be a kitárolási tevékenységet, és térjen vissza a **Kimenő** menübe.
1. A Dynamics 365 Supply Chain Management alkalmazásban lépjen a **Raktárkezelés \> Beállítás \> Raktár \> Helyek** pontra.
1. Szűrjön **Hely** alapján, és adja meg a kitárolási helyet az értékesítési rendelés munkájából.
1. Figyelje meg, hogy annak a helynek a **Helyállapot** mezője, ahonnan az értékesítési rendelési munka a kitárolást végezte, most *Kitárolás folyamatban* értékre van beállítva, és a **Legutóbbi tevékenység dátuma és időpontja** frissült.

> [!NOTE]
> A hely mezőit csak a raktári tranzakciók frissítik. Ha a készletet napló vagy más nem WHS-folyamatok segítségével helyezi át, a mezők nem frissülnek.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]