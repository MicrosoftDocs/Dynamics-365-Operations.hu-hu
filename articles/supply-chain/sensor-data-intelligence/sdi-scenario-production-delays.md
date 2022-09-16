---
title: A termelés késleltetési esete
description: Ez a témakör leírja a termelés késleltetési esetét, amely figyelmeztetést generál, ha a termelés termelési teljesítmény egy meghatározott küszöbérték alá esik.
author: johanhoffmann
ms.date: 09/02/2022
ms.topic: article
ms.search.form: IoTIntCoreScenarioManagement, IoTIntCoreScenarioConfigurationWizardV2, IoTIntMfgResourceStatusConfiguration, IoTIntMfgResourceStatus
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2022-09-02
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: 073762581d84646ba12b570e57327b7cab8efd3b
ms.sourcegitcommit: 3d7ae22401b376d2899840b561575e8d5c55658c
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/08/2022
ms.locfileid: "9428976"
---
# <a name="the-production-delays-scenario"></a>A termelés késleltetési esete

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

A *termelési késleltetési eset* figyelmeztetést generál, ha a termelés termelési teljesítményére egy meghatározott küszöbérték alá esik. Ebben az esetben minden előállított *cikkhez* Microsoft Azure egy rész-/out jel küldik a Hubba. Dynamics 365 Supply Chain Management A rendelési késleltetés számítása a termelési rendelés futtatására ütemezett idő, a termelni szükséges cikkek száma, *a* feladat futásának ideje és a kapott részmennyiség alapján történik. Késleltetett értesítés jön létre, *ha a feladatra vonatkozó rész-/kijelzők* száma a küszöbérték alá esik.

## <a name="scenario-dependencies"></a>Eset függőségei

A *termelés késleltetése eset* a következő függőségeket tartalmazza:

- Egy termelési rendelésnek futnia kell egy leképezett gépen, hogy a figyelmeztetés aktiválva legyen.
- A csatlakoztatott *gép* alkatrészi jelét képviselő jelet el kell küldeni Az InternetKözpontnak, és egy egyedi tulajdonságnevet kell hozzárendelni.
- Egy UNIX időbélyegző tulajdonságnak, ahol az érték ezredmásodpercben (ms) van kifejezve, jelen kell lennie az Azure IoT Hub üzenetben.

## <a name="prepare-demo-data-for-the-product-delays-scenario"></a>Bemutatóadatok előkészítése a termékkéslelt esethez

Ha bemutatórendszert szeretne használni a termelés késleltetési helyzetének tesztelésére, használja azt a rendszert, amelyben telepítve vannak a bemutatóadatok, *válassza ki az USMF* jogi személyt (vállalat), és készítse elő a [további](../../fin-ops-core/fin-ops/get-started/demo-data.md) bemutatóadatokat az ebben a *szakaszban* leírt módon. Ha saját telefonokat és adatokat használ, kihagyhatja ezt a szakaszt.

### <a name="set-up-sensor-simulator"></a>Szimulátor beállítása

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

### <a name="configure-the-production-floor-execution-interface"></a>A termelési üzem végrehajtási felületének konfigurálása

Ha még nem tette meg, állítsa be a termelési emelet végrehajtási felületét úgy, *hogy a 3118-as erőforráshoz rendelt feladatokat mutassa (* 2018-as *illesztőgép*). Az útmutatás a következő szakaszokban található:

- [A termelési üzem végrehajtási felületének konfigurálása](sdi-scenario-equipment-downtime.md#config-pfe)
- [Keresési beállítás engedélyezése a termelési emelet végrehajtási felületén](sdi-scenario-equipment-downtime.md#enable-pfe-search)

### <a name="start-the-first-job-in-the-batch-order"></a>A kötegrendelés első feladatának kezdése

A következő lépések szerint indíthatja el a kötegelt rendelés első feladatát.

1. Lépjen a **Gyártásvezérlés \> Gyártásvégrehajtás \> Termelési üzem végrehajtásának konfigurálása** részre.
1. Írja be a **123**-as azonosítót *a Belépőkártya-azonosító mezőbe*. Ezután válassza ki a **bejelentkezést**.
1. Ha távolléti ok miatt kéri a rendszer, válassza ki a távolléti kártyák valamelyikét, majd válassza az **OK gombra**.
1. A Keresés **mezőbe** írja be azt a kötegrendelésszámot, amelyről korábban megjegyzést készített. Ezután válassza a Visszáru **kulcsot**.
1. Válassza ki a rendelést, majd válassza a Feladat kezdete **lehetőséget**.
1. A Feladat **kezdete párbeszédpanelen** válassza az Indítás **lehetőséget**.

## <a name="set-up-the-production-delays-scenario"></a>A termelés késleltetési esetének beállítása

A következő lépések szerint állíthatja *be a termelési késedelmes eseteket* az Ellátásilánc-kezelés eszközben.

1. Ugrás a Gyártásvezérlés **beállításához \>\> – Adatintelligencia-esetek \>**
1. A Termelés késleltetése **eset** mezőben válassza **a Konfigurálás** lehetőséget az eset beállítási varázslóának megnyitásához.
1. Az Új **lapon** jelölje be az **Új** gombra, ha hozzá szeretne adni egy bővítményt a rácshoz. Ezután állítsa be a következő mezőket:

    - **Mérőazonosító** – adja meg a használatbanlott eszköz azonosítóját. (Ha a Pi Azure Azure online szimulátort használja, és a következőben leírtak szerint [beállította: Szimulált készlet beállítása teszteléshez](sdi-set-up-simulated-sensor.md), adja meg a *ProductionDelay*.)
    - **Mérő leírása** – adja meg a mérő leírását.

1. Ismételje meg az előző lépést minden további, most hozzáadni kívánt mérővel. Bármikor vissza lehet jönni, és további fogatokat lehet hozzáadni.
1. Válassza ki **Következő** lehetőséget.
1. Az üzleti **rekord megfeleltetési** lapján **, a Társítások szakaszban** válassza ki a rekordot az előbb hozzáadott valamelyik hőmérséklethez.
1. Az Üzleti rekord **megfeleltetése** szakaszban válassza az Új **lehetőséget**, ha sort szeretne hozzáadni a rácshoz.
1. Az új sorban állítsa be az **üzleti** rekordot arra az erőforrásra, amely a kijelölt adattenre használ figyelésként. (Ha a korábban ebben a cikkben létrehozott bemutató adatokat használja, *állítsa 3118-ra (Vágó vágógép*).)
1. Válassza ki **Következő** lehetőséget.
1. A Termelés késleltetése **- küszöbérték** oldalon, ha a jelen cikk korábban létrehozott bemutató adatait használja, kövesse a következő lépéseket:

    1. Válassza ki **a Cikk-kapcsolat** oszlopfejlécet egy legördülő párbeszédpanel megnyitásához, amely az oszlop keresési szűrőit tartalmazza. Írja be *a P0111 mezőbe*, majd válassza az Alkalmaz **gombra.**
    2. Válassza ki azt a sort, **ahol a** Művelet mező beállítás Vágás */Kivágás*. Az Értesítési **küszöbérték beállítása késleltetésre (%)** mezőben azt a küszöbértéket (százalékban megállítva), amelynél az értesítést el kell küldeni.

1. Válassza ki **Következő** lehetőséget.
1. Válassza ki **a hozzáadni kívánt** fogatot a rácshoz az Aktiváló eszköz lapon, majd válassza ki az Aktiválás **lehetőséget**. A rácsban aktivált mindegyik aktivált eszközhöz megjelenik egy pipa az Aktív **oszlopban**.
1. Válassza a **Befejezés** lehetőséget.

## <a name="work-with-the-production-delays-scenario"></a>A termelési késleltetések eset használható

### <a name="view-production-delay-data-on-the-resource-status-page"></a>Termelés késleltetési adatainak megtekintése az Erőforrás állapota lapon

Az Erőforrás **állapota** lapon a felettesek figyelhetik az egyes gépekhez hozzárendelt készülékkel kapott jelzések időrendét. A következő lépések szerint konfigurálhatja az időrendet.

1. Ugrás a Gyártásvezérlés **\> Gyártás-végrehajtási erőforrás \> állapotára**
1. A Konfigurálás **párbeszédpanelen** állítsa be a következő mezőket:

    - **Erőforrás** – válassza ki a figyelni kívánt erőforrásokat. (Ha a bemutatóadatokon dolgozik, válassza a *3118-as lehetőséget*.)
    - **1** . idősorozat – válassza ki azt a rekordot (metrikus kulcsot), amely a következő formátumú a nevében: *ProductionJobDelayed:ActualQuantity:&lt; JobId&gt;*
    - **Megjelenített név** – adja meg az *alkatrészek jelét*.
