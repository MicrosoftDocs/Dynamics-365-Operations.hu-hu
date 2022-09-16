---
title: A gép állapotának esete
description: Ez a cikk a gép állapotának esetét írja le, amelynek segítségével az akkumulátoradatok segítségével nyomon követheti a berendezések rendelkezésre állását.
author: johanhoffmann
ms.date: 09/02/2022
ms.topic: article
ms.search.form: IoTIntCoreScenarioManagement, IoTIntCoreNotification, IoTIntMfgResourceStatusConfiguration, IoTIntMfgResourceStatus
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2022-09-02
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: 1f2b424dccf1963a7917059d412b5df7937496ee
ms.sourcegitcommit: 3d7ae22401b376d2899840b561575e8d5c55658c
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/08/2022
ms.locfileid: "9428975"
---
# <a name="the-machine-status-scenario"></a>A gép állapotának esete

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

A *gépek állapotára* vonatkozó helyzet lehetővé teszi az adatlapadatok használatát a berendezések rendelkezésre állásának figyelése érdekében. Ha beállít egy jelzőt, amely akkor küld jelzést, ha egy gép erőforrás termelési feladata kimenetet hoz létre, de egy megadott időintervallumon belül nem érkezik rádiójel, a felettes irányítópultján megjelenik egy értesítés.

## <a name="scenario-dependencies"></a>Eset függőségei

A *gépi állapot* eset a következő függőségeket tartalmazza:

- Az értesítések csak akkor indíthatóak el, ha egy leképezett számítógépen folyamatban van egy termelési feladat.
- A részből való *jelre való jelet* átvitelre kell a Hubba küldeni.

## <a name="prepare-demo-data-for-the-machine-status-scenario"></a>Bemutatóadatok előkészítése a gépi állapot esethez

Ha bemutatórendszert szeretne használni a gép állapotának tesztelésére, használja azt a rendszert, amelyben telepítve vannak a bemutatóadatok, *válassza ki az USMF* jogi személyt (vállalat), és készítse elő a [további](../../fin-ops-core/fin-ops/get-started/demo-data.md) bemutatóadatokat az ebben a *szakaszban* leírt módon. Ha saját telefonokat és adatokat használ, kihagyhatja ezt a szakaszt.

### <a name="set-up-a-sensor-simulator"></a>Szimulátor beállítása

Ha fizikai eszköz használata nélkül szeretné megpróbálni ezt az esetet, beállítható egy szimulátor, amely generálja a szükséges jelzéseket. További tájékoztatás: [Szimulált mérőmérő beállítása teszteléshez](sdi-set-up-simulated-sensor.md).

### <a name="verify-that-resource-3118-is-used-for-product-p0111"></a>Ellenőrizze, hogy a 3118-as erőforrást használják-e a P0111 termékhez.

Meg lesz adva és ütemezve lesz a termelési rendelés. Emiatt egy termelési feladat ki van adva *a 3118-as erőforrásnak (* 2018-*2018*). A következő lépések szerint ellenőrizze *, hogy a bemutatóadatok között a 3118-as* *erőforrást használják-e a P0111* termékhez.

1. Kattintson a **Termékinformációk kezelése \> Termékek \> Kiadott termékek** lehetőségre.
1. Annak a terméknek a megkeresása és kiválasztása **, ahol a Cikkszám** mező beállítása *P0111*.
1. A Munkaablak Mérnöki **lapján**, a **Nézet csoportban** válassza az Útvonal **lehetőséget**.
1. Az Útvonal **lapon**, **az** oldal alján található Áttekintés lapon válassza ki azt a sort, **ahol a Műveletszám.** *mező 30-ra van állítva*.
1. A lap **alján** található Erőforrásigények lapon ellenőrizze, *hogy a művelethez legyen-e társítva a 3118-as* erőforrás (*Besz*. vágási gép).

### <a name="create-and-release-a-production-order-for-product-p0111"></a>P0111 termékre vonatkozó termelési rendelés létrehozása és kiadása

A következő lépések szerint hozhat létre és ad ki termelési rendelést a *P0111 termékhez*.

1. Ugrás a **Gyártásvezérlés \> Termelési rendelések \> Minden termelési rendelés** lehetőségre.
1. A Minden termelési **rendelés** lapon, a munkaablakban válassza az Új kötegrendelés lehetőséget.**·**
1. A Köteg **létrehozása párbeszédpanelen** állítsa be a következő értékeket:

    - **Cikkszám:** *P0111*
    - **Mennyiség:** *10*

1. Válassza a **Létrehozás** lehetőséget a rendelés létrehozásához és a Minden termelési **rendelés laphoz való visszatéréshez**.
1. A Szűrő **mezőben** kereshet olyan termelési rendeléseket, **amelyekben a Cikkszám** *mező beállítása P0111*. Ezután keresse meg és válassza ki az előbb létrehozott termelési rendelést.
1. A Műveleti ablaktáblán a **Termelési rendelés** lapon a **Folyamat** csoportban válassza a **Becslés** lehetőséget.
1. A Becslés **párbeszédpanelen** kattintson **az OK** gombra a becslés futtatásához.
1. A Munkaablak Termelési rendelés lap **Folyamatcsoportjában** **válassza a Kiadás** lehetőséget **.**
1. A Kiadás **párbeszédpanelen** jegyezze fel az előbb létrehozott kötegrendelés számát.
1. A **rendelés kiadáshoz kattintson az OK** gombra.

### <a name="configure-the-production-floor-execution-interface"></a><a name="config-pfe"></a>A termelési üzem végrehajtási felületének konfigurálása

A termelés-végrehajtási felület használatával lehet *elindítani az előző szakasz P0111* cikkszámához ütemezett és kiadott feladatot. A következő lépések szerint konfigurálhatja a termelési emelet végrehajtási felületét.

1. Lépjen a **Gyártásvezérlés \> Gyártásvégrehajtás \> Termelési üzem végrehajtásának konfigurálása** részre.
1. Ha még nem beállította a felületet, megjelenik egy bejelentkezési lap. Adja meg a hitelesítési adatait.
1. Az üdvözlő oldalon válassza a Konfigurálás **eszköz** konfigurálása **varázslót**.
1. Az Eszköz **konfigurálása – 1. lépés – Konfigurációs lap** kiválasztása, az Alapértelmezett konfiguráció *kiválasztása*.
1. Válassza ki **Következő** lehetőséget.
1. Az Eszköz **konfigurálása – 2. lépés – A** **termelési terület lapon állítsa az Erőforrás** *mezőt a 3118-asra*.
1. Válassza ki az **OK** lehetőséget.

### <a name="enable-the-search-option-in-the-production-floor-execution-interface"></a><a name="enable-pfe-search"></a> A keresési beállítás engedélyezése a termelési emelet végrehajtási felületén

Ha egyszerűbbé szeretné tenni a korábban kiadott termelési rendelés termelési feladatának megkeresét, kövesse ezeket a lépéseket, ha engedélyezni szeretné a keresési beállítást a termelési emelet végrehajtási felületén.

1. Lépjen a **Gyártásvezérlés \> Beállítás \> Gyártásvégrehajtás \> termelési üzem végrehajtásának konfigurálása** részre.
1. Az alapértelmezett *konfiguráció* kiválasztása.
1. A műveleti ablaktáblán válassza a **Szerkesztés** lehetőséget.
1. Az Általános **gyors** gyorsgombon állítsa **a Keresés engedélyezése** lehetőséget Igen *beállításra*.
1. Zárja be a lapot.

### <a name="start-the-first-job-in-the-batch-order"></a>A kötegrendelés első feladatának kezdése

A következő lépések szerint indítható el a 3118-as erőforrásra *ütemezett feladat*.

1. Lépjen a **Gyártásvezérlés \> Gyártásvégrehajtás \> Termelési üzem végrehajtásának konfigurálása** részre.
1. Írja be a **123**-as azonosítót *a Belépőkártya-azonosító mezőbe*. Ezután válassza ki a **bejelentkezést**.
1. Ha távolléti ok miatt kéri a rendszer, válassza ki a távolléti kártyák valamelyikét, majd válassza az **OK gombra**.
1. A Keresés **mezőbe** írja be azt a kötegrendelésszámot, amelyről korábban megjegyzést készített. Ezután válassza a Visszáru **kulcsot**.
1. Válassza ki a rendelést, majd válassza a Feladat kezdete **lehetőséget**.
1. A Feladat **kezdete párbeszédpanelen** válassza az Indítás **lehetőséget**.

## <a name="set-up-the-machine-status-scenario"></a>Gépi állapot eset beállítása

A következő lépések szerint állíthatja be a gép állapotát *az* Ellátásilánc-kezelés eszközben.

1. Ugrás a Gyártásvezérlés **beállításához \>\> – Adatintelligencia-esetek \>**
1. A Gép állapota **eset** mezőben válassza **a Konfigurálás** lehetőséget, hogy megnyíljön az eset beállítási varázslója.
1. Az Új **lapon** jelölje be az **Új** gombra, ha hozzá szeretne adni egy bővítményt a rácshoz. Ezután állítsa be a következő mezőket:

    - **Mérőazonosító** – adja meg a használatbanlott eszköz azonosítóját. (Ha a Pi Azure Azure online szimulátort használja, és a következőben leírtak szerint [beállította: Szimulált készlet beállítása teszteléshez](sdi-set-up-simulated-sensor.md), adja meg a *MachineStatus-t*.)
    - **Mérő leírása** – adja meg a mérő leírását.

1. Ismételje meg az előző lépést minden további, most hozzáadni kívánt mérővel. Bármikor vissza lehet jönni, és további fogatokat lehet hozzáadni.
1. Válassza ki **Következő** lehetőséget.
1. Az üzleti **rekord megfeleltetési** lapján **, a Társítások szakaszban** válassza ki a rekordot az előbb hozzáadott valamelyik hőmérséklethez.
1. Az Üzleti rekord **megfeleltetése** szakaszban válassza az Új **lehetőséget**, ha sort szeretne hozzáadni a rácshoz.
1. Az új sorban állítsa be **az Üzleti** rekord mezőt arra az erőforrásra, amely a kiválasztott figyelőt használja figyelésként. (Ha a korábban ebben a cikkben létrehozott bemutató adatokat használja, *állítsa a mezőt a 3118- as (Műanyag vágási gép) beállításra*.)
1. Válassza ki **Következő** lehetőséget.
1. Adja meg a **gépi állapotküszöb** oldalon, *hogy* a rendszer meddig küldjön értesítést a gép állapotáról az utolsó részüzenet után. A küszöbérték kétféleképpen definiálhat:

    - **Alapértelmezett küszöbérték (perc)** – a mező beállítása az alapértelmezett küszöbérték meghatározására. Az érték ezt követően az összes **olyan erőforrásra érvényes lesz, ahol a gép nem válaszolóként való beállításának küszöbértéke (perc)** két percnél rövidebbre van állítva. A minimális érték *2* (perc).
    - **Küszöbérték annak meghatározásához, hogy a gép nem válaszol (perc)** – a rács minden olyan erőforrásához, amelynél nem szeretné használni az alapértelmezett küszöbértéket, írjon be egy felülbírálási értéket ebbe a mezőbe. Azok az erőforrások, amelyek **két perc vagy kevesebb küszöbérték használatára vannak beállítva, az Alapértelmezett küszöbérték (perc) beállítást használják** helyette.

    > [!NOTE]
    > Általában részmunkaidős jellel felügyelheti a *gép* állapotát. Ezért ellenőriznie kell, hogy az egyes géperőforrások küszöbértéke hosszabb-e, mint az egyes részek előállításához szükséges küszöb.

1. Válassza ki **Következő** lehetőséget.
1. Válassza ki **a hozzáadni kívánt** fogatot a rácshoz az Aktiváló eszköz lapon, majd válassza ki az Aktiválás **lehetőséget**. A rácsban aktivált mindegyik aktivált eszközhöz megjelenik egy pipa az Aktív **oszlopban**.
1. Válassza a **Befejezés** lehetőséget.

## <a name="work-with-the-machine-status-scenario"></a>A gépi állapot eset használható

Miután telepíti az akkumulátorokat, és konfigurálja az esetet, az Ellátásilánc-kezelés eszközben megtekintheti a gépállapot-eseményeket. Ez a szakasz bemutatja, hogy hol és hogyan lehet megtekinteni ezt az információt.

### <a name="view-machine-status-data-on-the-resource-status-page"></a>Gépi állapotadatok megtekintése az Erőforrás állapota lapon

Az Erőforrás **állapota** lapon a felettesek figyelhetik az *egyes* gép-erőforrásokhoz hozzárendelt kijelzőkből származó jel időrendját. A következő lépések szerint konfigurálhatja az időrendet.

1. Ugrás a Gyártásvezérlés **\> Gyártás-végrehajtási erőforrás \> állapotára**
1. A Konfigurálás **párbeszédpanelen** állítsa be a következő mezőket:

    - **Erőforrás** – válassza ki a figyelni kívánt erőforrásokat. (Ha a bemutatóadatokon dolgozik, válassza a *3118-as lehetőséget*.)
    - **1** . idősorozat – válassza ki azt a rekordot (metrikus kulcsot), amely a következő formátummal rendelkezik a nevéhez: *MachineReportingStatus:&lt; Biometrikus.&gt;*
    - **Megjelenített név** – adja meg az *alkatrészek jelét*.

A következő ábra a gépek állapotadatokat **ábrázolnak** az Erőforrás állapotlapján a szokásos művelet során.

![Gépállapotadatok az Erőforrás állapotlapon az alapművelet során.](media/sdi-resource-status-downtime-up.png "Gépállapotadatok az Erőforrás állapotlapon szokásos művelet közben")

A következő ábra a gép állapotára vonatkozó adatokat mutatja be, amikor leállás észlelhető.

![Gépállapotadatok az Erőforrás állapotlapon, ha leállás észlelhető.](media/sdi-resource-status-downtime-down.png "Gépállapotadatok az Erőforrás állapotlapon, ha leállás észlelhető")

### <a name="view-machine-status-on-the-notifications-page"></a>Gép állapotának megtekintése az Értesítések lapon

Az Értesítések **lapon** a felettesek megtekinthetik az olyan értesítéseket, amelyek akkor jönnek létre, ha túl sok idő telt el azóta, hogy a *riasztás utoljára part out jelzést* adott. Minden értesítés áttekintést nyújt a kimaradás által érintett termelési feladatról, és lehetőséget ad az érintett feladat másik erőforráshoz való hozzárendelésére.

Az Értesítés lap megnyitásához nyissa meg a Gyártásvezérlés **lekérdezései** **\>\> és jelentései lapot.\>**

A következő ábra a gépek állapotáról szóló értesítés egy példáját mutatja be.

![Példa gépi állapotértesítésre](media/sdi-resource-status-downtime-notification.png "Példa gépi állapotértesítésre")
