---
title: A termékminőségi forgatókönyv
description: Ez a cikk a termékminőségi helyzetről nyújt tájékoztatást. Ez az eset egy mérőszám alapján határozza meg a termékköteség minőségét, és figyelmeztetést generál, ha egy mérték kívül esik egy meghatározott küszöbértéken.
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
ms.openlocfilehash: c0f1c57251234921779f67faf61d47cdde119e64
ms.sourcegitcommit: 3e04f7e4bc0c29c936dc177d5fa11761a58e9a02
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/18/2022
ms.locfileid: "9690048"
---
# <a name="the-product-quality-scenario"></a>A termékminőségi forgatókönyv

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]
<!-- KFM: Preview until further notice -->

A termékminőségi *helyzetben* egy biztonsági eszköz van beállítva a termékkötey minőségének az üzletben való mérésére. Ha egy mérték kívül esik a termék meghatározott küszöbértékén, a felettes irányítópultján megjelenik egy értesítés. Például egy mérőeszköz a termelési sorból kiálló élelmiszertermék üzemének az 5000000000000000000000000000000 értékről származik. Ha a mérték kívül esik a termékre vonatkozó figyelmeztetés minimális vagy maximális értékán, akkor a rendszer figyelmeztetést küld.

## <a name="scenario-dependencies"></a>Eset függőségei

A *termékminőségi* helyzet a következő függőségeket tartalmazza:

- Csak akkor jelenik meg figyelmeztetés, ha egy termelési rendelés egy leképezett számítógépen fut, és a gép olyan terméket gyárt, amely rendelkezik hozzárendelt kötegattribútummal.
- A kötegattribútumot jelképező jelet kell küldeni az IoT-központnak egy kötelező egyedi tulajdonságnévvel.

## <a name="prepare-demo-data-for-the-product-quality-scenario"></a>Bemutatóadatok előkészítése a termékminőségi helyzethez

Ha bemutatórendszert szeretne használni a termékminőségi helyzet tesztelésére, használja azt a rendszert, amelyben telepítve vannak a bemutatóadatok, *válassza ki az USMF* jogi személyt (vállalat), és készítse elő a [további](../../fin-ops-core/fin-ops/get-started/demo-data.md) bemutatóadatokat az ebben a *szakaszban* leírt módon. Ha saját telefonokat és adatokat használ, kihagyhatja ezt a szakaszt.

Ebben a szakaszban lehet beállítani *a bemutató adatokat, hogy a kiadott P0111* termék (*Összetett* eset) *használhatók a termékminőségi helyzethez*. Ebben az esetben a rendszer nyomon követi, hogy az egy tulajdonság által mért kötegattribútum-érték kívül esik-e a termékhez társított kötegattribútum meghatározott küszöbértékén.

### <a name="set-up-a-sensor-simulator"></a>Szimulátor beállítása

Ha fizikai eszköz használata nélkül szeretné megpróbálni ezt az esetet, beállítható egy szimulátor, amely generálja a szükséges jelzéseket. További tájékoztatás: [Szimulált mérőmérő beállítása teszteléshez](sdi-set-up-simulated-sensor.md).

### <a name="associate-a-batch-attribute-and-resource-with-product-p0111"></a>Kötegattribútum és erőforrás társítása a P0111 termékhez

A következő lépések szerint társíthatja a kötegattribútumokat a P0111 *termékhez (* Összetett *eset),* és ellenőrizze, hogy hozzá van-e használva a *3118-as erőforrás (* *3118-as* vágási gép).

1. Kattintson a **Termékinformációk kezelése \> Termékek \> Kiadott termékek** lehetőségre.
1. Annak a terméknek a megkeresása és kiválasztása **, ahol a Cikkszám** mező beállítása *P0111*.
1. A Munkaablak Készlet kezelése **lapján** **·**, a Kötegattribútumok csoportban válassza a Termékspecifikus **lehetőséget**.
1. Termékspecifikus **kötegattribútum** létrehozásához válassza **az Új** lehetőséget a Termékspecifikus lapon.
1. A fejlécben állítsa be a következő mezőket:

    - **Attribútumkód** – válassza ki a figyelni kívánt attribútumok hatókörét (*tábla*, *csoport* vagy *mind*). Erre az esetre a Tábla lehetőséget *kell választani*, mert a rendszer mindig egyetlen attribútumot figyel.
    - **Attribútumkapcsolat** – annak az attribútumnak *a kiválasztása, amely a termékminőségi eset* figyelése során lesz használva. Ebben a példában válassza *a Felfokozás* lehetőséget, amely egy olyan attribútum, amely része a normál bemutatóadatoknak.

1. Adja meg **az** Értékek **gyorsjelentésben** **a Minimum és a Maximum** mezőkben, hogy az attribútumnak milyen elfogadható értékeket kell jelentenie ahhoz, hogy a minőségi ellenőrzésen megfeleltessen. Ha a jelentésekben a tartományon kívül található érték található, akkor a rendszer minőségi megszegésként azonosítja. A gyorscsoport többi mezője nem függ a termékminőségi *helyzettől*. A jelenlegi alapértelmezett értékek a bemutatóadatokból vannak. Ezért hagyja a kívánt elemet, **·** **·** *és zárja be a Termékspecifikus lapot, hogy visszatérjen a P0111 cikk Kiadott termék részletei oldalára.*
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

## <a name="set-up-the-product-quality-scenario"></a>Termékminőségi eset beállítása

A következő lépések szerint állítsa be a *termékminőségi helyzetet* az Ellátásilánc-kezelés eszközben.

1. Ugrás a Gyártásvezérlés **beállításához \>\> – Adatintelligencia-esetek \>**
1. A Termékminőségi **eset mezőben** válassza **a Konfigurálás** lehetőséget, hogy megnyíljön az eset beállítási varázslója.
1. Az Új **lapon** jelölje be az **Új** gombra, ha hozzá szeretne adni egy bővítményt a rácshoz. Ezután állítsa be a következő mezőket:

    - **Mérőazonosító** – adja meg a használatbanlott eszköz azonosítóját. (Ha a Pi Azure Azure online szimulátort használja, és a következőben leírtak szerint [beállította: Szimulált készlet beállítása teszteléshez](sdi-set-up-simulated-sensor.md), adja meg a Minőség *beállítását*.)
    - **Mérő leírása** – adja meg a mérő leírását.

1. Ismételje meg az előző lépést minden további, most hozzáadni kívánt mérővel. Bármikor vissza lehet jönni, és további fogatokat lehet hozzáadni.
1. Válassza ki **Következő** lehetőséget.
1. Az üzleti **rekord megfeleltetési** lapján **, a Társítások szakaszban** válassza ki a rekordot az előbb hozzáadott valamelyik hőmérséklethez.
1. Az Üzleti rekord **megfeleltetése** szakaszban válassza az Új **lehetőséget**, ha sort szeretne hozzáadni a rácshoz.
1. Az új sorban az Üzleti rekordtípus **mezőnek** automatikusan *Az erőforrások (WrkCtrTable) beállítását kell beállítani*. Az Üzleti **rekord** mező beállítása arra az erőforrásra, amely a kiválasztott biztonsági figyelőt használja figyelésként. (Ha a korábban ebben a cikkben létrehozott bemutató adatokat használja, *állítsa 3118-ra (Vágó vágógép*).)
1. Közvetlenül az előző lépésben hozzáadott sor üzleti rekordtípusának kiválasztása után a program automatikusan hozzáad egy második sort a rácshoz. Ebben a sorban az **Üzleti rekordtípus** *mezőt Kötegattribútumok (PdsBatchAttrib) típusúra kell beállítani*. Az Üzleti **rekord mező** beállítása arra a kötegattribútumra, amely a kijelölt biztonsági figyelőt használja figyelésként. (Ha a korábban ebben a cikkben létrehozott bemutató adatokat használja, állítsa be a következőre: *Aránya, százalékos arány*)
1. Válassza ki **Következő** lehetőséget.
1. Válassza ki **a hozzáadni kívánt** fogatot a rácshoz az Aktiváló eszköz lapon, majd válassza ki az Aktiválás **lehetőséget**. A rácsban aktivált mindegyik aktivált eszközhöz megjelenik egy pipa az Aktív **oszlopban**.
1. Válassza a **Befejezés** lehetőséget.

## <a name="work-with-the-product-quality-scenario"></a>A termékminőségi eset használata

### <a name="view-product-quality-data-on-the-resource-status-page"></a>Termékminőségi adatok megtekintése az Erőforrás állapota lapon

Az Erőforrás **állapotlapon** a felettesek figyelhetik az egyes gépekhez hozzárendelt készülékkel jelzett termékminőségi jel időrendját. A következő lépések szerint konfigurálhatja az időrendet.

1. Ugrás a Gyártásvezérlés **\> Gyártás-végrehajtási erőforrás \> állapotára**
1. A Konfigurálás **párbeszédpanelen** állítsa be a következő mezőket:

    - **Erőforrás** – válassza ki a figyelni kívánt erőforrásokat. (Ha a bemutatóadatokon dolgozik, válassza a *3118-as lehetőséget*.)
    - **1. idősorozat** – a következő formátumú rekord (metrikus kulcs) kiválasztása: *ProductQuality:&lt; JobId&gt;:&lt; AttributeName&gt;*
    - **Megjelenített név** – adja meg a kötegattribútum *értékeit*.

A következő ábra az **Erőforrás** állapotlapon mutatja be a termékminőségi adatokat, ha az érték az elfogadható értékek tartományán belül van.

![Termékminőségi adatok az Erőforrás állapotlapon, ha az érték a tartományban van.](media/sdi-product-quality-in-range.png "Termékminőségi adatok az Erőforrás állapotlapon, ha az érték a tartományban van")

A következő ábra a termékminőségi adatokra vonatkozó példát mutat be, ha tartományon kívül található érték észlelhető.

![Termékminőségi adatok az Erőforrás állapotlapon, ha tartományon kívüli értéket észlel a rendszer.](media/sdi-product-quality-out-of-range.png "Termékminőségi adatok az Erőforrás állapotlapon tartományon kívüli érték észlelhető")

### <a name="view-product-quality-data-on-the-notifications-page"></a>Termékminőségi adatok megtekintése az Értesítések lapon

Az Értesítések **lapon a felettesek** megtekinthetik azt az értesítést, amely akkor jön létre, amikor a mérőszám egy olyan kötegattribútum-értéket értékel, amely kívül esik a kötegattribútum meghatározott küszöbértékén. Minden értesítés áttekintést nyújt a kimaradás által érintett termelési feladatról, és lehetőséget ad az érintett feladat másik erőforráshoz való hozzárendelésére.

Az Értesítés lap megnyitásához nyissa meg a Gyártásvezérlés **lekérdezései** **\>\> és jelentései lapot.\>**

Az alábbi ábra a termékminőségi értesítések egy példáját mutatja be.

![Példa termékminőségi értesítésre.](media/sdi-product-quality-notification.png "Példa termékminőségi értesítésekre")
