---
title: Az eszköz karbantartási forgatókönyve
description: Ez a témakör ismerteti az eszköz-karbantartási helyzetet, amelynek segítségével az eszközadatok segítségével olyan számlálórekordokat lehet létrehozni, amelyek egy gépi eszköz használatát követik nyomon.
author: johanhoffmann
ms.date: 09/02/2022
ms.topic: article
ms.search.form: IoTIntCoreScenarioManagement, IoTIntCoreScenarioConfigurationWizardV2, EntAssetCounter
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2022-09-02
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: 2d103406118be4385177b678de424df12af69c2e
ms.sourcegitcommit: 3e04f7e4bc0c29c936dc177d5fa11761a58e9a02
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/18/2022
ms.locfileid: "9689400"
---
# <a name="the-asset-maintenance-scenario"></a>Az eszköz karbantartási forgatókönyve

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]
<!-- KFM: Preview until further notice -->

Az *eszköz-karbantartási* helyzet lehetővé teszi az adatkezelő adatok használatát számlálórekordok létrehozásához. A számlálórekordok egy gépi eszköz használatát követik nyomon, és bemenetként használatosak a gépi eszközök karbantartási ütemezésének létrehozásához.

## <a name="video-instructions"></a>Video-utasítások

Az alábbi videofelvétel bemutatja, hogyan lehet beállítani és ki lehet próbálja ki a tárgyi eszközök karbantartási esetét a normál bemutatóadatok [segítségével](../../fin-ops-core/fin-ops/get-started/demo-data.md). A cikk többi szakasza ugyanazt az utasítást adja meg szöveg alapú formátumban.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE58aRW]

## <a name="prepare-demo-data-for-the-asset-maintenance-scenario"></a>Bemutatóadatok előkészítése az eszköz-karbantartási esethez

Ha bemutatórendszert szeretne használni az eszköz-karbantartási helyzet tesztelésére, használja azt a rendszert, amelyben telepítve vannak a bemutatóadatok, *válassza ki az USMF* jogi személyt (vállalat), és készítse elő a [további](../../fin-ops-core/fin-ops/get-started/demo-data.md) bemutatóadatokat az ebben a *szakaszban* leírt módon. Ha saját telefonokat és adatokat használ, kihagyhatja ezt a szakaszt.

Ebben a szakaszban példaként *beállíthatja az AK-101 tárgyi eszközt, amely a Légi eszköz* bemutatóadatok között található. Ezután látható, hogy várható-e várható karbantartás a várható karbantartási munkáról, amely azt jelzi, hogy hány órája fut a légi eszköz. Egy karbantartási tervet is beállít, ahol a légi jármű karbantartására minden 10 000 órában szükség van.

### <a name="set-up-a-sensor-simulator"></a>Szimulátor beállítása

Ha fizikai eszköz használata nélkül szeretné megpróbálni ezt az esetet, beállítható egy szimulátor, amely generálja a szükséges jelzéseket. További tájékoztatás: [Szimulált mérőmérő beállítása teszteléshez](sdi-set-up-simulated-sensor.md).

### <a name="create-an-asset-counter-to-track-production-hours"></a>Eszközszámláló létrehozása a termelési órák nyomon követéséhez

A következő lépések szerint hozhat létre eszközszámlálót a termelési órák nyomon követésére.

1. Nyissa meg az **Eszközkezelés \> Beállítás \> Eszköztípusok \> Számlálók** lehetőséget.
1. Számláló létrehozásához válassza a munkaablak **Új** lehetőséget.
1. A fejlécben állítsa be a következő értékeket:

    - **Számláló:** *ProductionHr*
    - **Név:** *termelési idő*

1. Az **Általános** gyorslapon állítsa be a következő értékeket:

    - **Egység:** *hr*
    - **Frissítés:** *Manuális*
    - **Összesítés összesen:** *összeg*

1. Válassza a **Sor hozzáadása gombra** az Eszköztípusok **gyorsgombra vonatkozó gombra.**
1. Az új sorban állítsa a **Tárgyi eszköz típusa** mezőt a Légi eszköz *értékeként*.

### <a name="create-a-maintenance-plan-for-the-asset"></a>Karbantartási terv létrehozása az eszközhöz

A következő lépések szerint hozhat létre karbantartási tervet az eszközhöz.

1. Ugrás az Eszközkezelés **beállítása megelőző \>\> karbantartási tervéhez \>**.
1. A munkaablakban válassza az Új lehetőséget **karbantartási** terv létrehozásához.
1. A fejlécben állítsa be a következő értékeket:

    - **Karbantartási terv:** *AirKnife*
    - **Név:** *Légitervtervek*

1. A **Részletek** gyorslapon állítsa be a következő értékeket:

    - **Terv dátuma:** Adja meg a mai dátumot.
    - **Aktív:** *Igen*

1. A Sorok **gyorspultban** válassza az Eszközszámláló **sor** hozzáadása lehetőséget, ha sort szeretne hozzáadni a rácshoz. Ezután állítsa be a következő értékeket:

    - **Munkarendelés leírása:** *légi karbantartás*
    - **Karbantartási feladat típusa:** *Megelőző*
    - **Intervallumtípus: Az** *utolsó munkarendelésből ismétlődve*
    - **Időszak gyakorisága:** *10000*
    - **Számláló:** *ProductionHr*

## <a name="set-up-the-asset-maintenance-scenario"></a>Eszköz-karbantartási eset beállítása

Az alábbi lépések szerint állíthatja be az eszköz-karbantartási *helyzetet* az Ellátásilánc-kezelés eszközkezelésben.

1. Menjen az Eszközkezelés **beállítása \>\> biztonsági adatintelligencia-esetekhez \>**.
1. Az Eszköz karbantartása **eset** mezőben válassza **a Konfigurálás** lehetőséget, hogy megnyíljön az eset beállítási varázslója.
1. Az Új **lapon** jelölje be az **Új** gombra, ha hozzá szeretne adni egy bővítményt a rácshoz. Ezután állítsa be a következő mezőket:

    - **Mérőazonosító** – adja meg a használatbanlott eszköz azonosítóját. (Ha a Pi Azure Azure online szimulátort használja, és a következőben leírtak szerint [beállította: Szimulált mérőeszköz beállítása teszteléshez](sdi-set-up-simulated-sensor.md), adja meg az *AssetMaintenance értékét*.)
    - **Mérő leírása** – adja meg a mérő leírását.

1. Ismételje meg az előző lépést minden további, most hozzáadni kívánt mérővel. Bármikor vissza lehet jönni, és további fogatokat lehet hozzáadni.
1. Válassza ki **Következő** lehetőséget.
1. Az üzleti **rekord megfeleltetési** lapján **, a Társítások szakaszban** válassza ki a rekordot az előbb hozzáadott valamelyik hőmérséklethez.
1. Az Üzleti rekord **megfeleltetése** szakaszban válassza az Új **lehetőséget**, ha sort szeretne hozzáadni a rácshoz.
1. Az új sorban az Üzleti **rekordtípus** *mező értékét automatikusan Tárgyi eszköz (EntAssetObjectTable)* értéknek kell beállítani. Az Üzleti **rekord** mező beállítása arra az erőforrásra, amely a kiválasztott biztonsági figyelőt használja figyelésként. (Ha a korábban ebben a cikkben létrehozott bemutató adatokat használja, állítsa be a következőre: *AK-101, AK-101 1. sor légi közlekedése*.)
1. Közvetlenül az előző lépésben hozzáadott sor üzleti rekordtípusának kiválasztása után a program automatikusan hozzáad egy második sort a rácshoz. Ebben a sorban az **Üzleti rekordtípus** *mezőt Számlálók (EntAssetCounterType) típusra kell állítani*. Állítsa be **az üzleti rekord** mezőjét arra az eszközszámlálóra, amely a kiválasztott biztonsági eszközből származó jelzés alapján frissít. (Ha a korábban ebben a cikkben létrehozott bemutató adatokat használja, állítsa be a következőre: *ProductionHr, Production hours*.)
1. Válassza ki **Következő** lehetőséget.
1. Válassza ki **a hozzáadni kívánt** fogatot a rácshoz az Aktiváló eszköz lapon, majd válassza ki az Aktiválás **lehetőséget**. A rácsban aktivált mindegyik aktivált eszközhöz megjelenik egy pipa az Aktív **oszlopban**.
1. Válassza a **Befejezés** lehetőséget.

## <a name="work-with-the-asset-maintenance-scenario"></a>Az eszköz-karbantartási eset karbantartása

### <a name="view-counter-values"></a>Számlálóértékek megtekintése

Az adatok elkészültét, valamint *az* eszköz-karbantartási helyzetet konfigurálva és aktiválva után láthatja, hogy hogyan szúrja be a rendszer az eszközszámláló rekordjait a konfigurálási adatok alapján.

1. Ugrás az **Eszközkezelés – \> Összes \> eszköz eszközhöz**
1. Keresse meg és válassza ki a vizsgálni kívánt eszközt. (Ha a korábban ebben a cikkben létrehozott bemutató adatokat használja, *válassza a AK-101*.)
1. **·** **·** **·** *Az AK-101 eszköz számlálórekordjainak lapját a Megelőző csoport Eszköz lapján, a Megelőző csoportban válassza ki a Számlálók gombra.*

> [!NOTE]
> A számlálórekordok alapértelmezés szerint három óránként lesznek beszúrva, ami azt jelenti, hogy a rendszer ezen az intervallumon belül összesíti az adatokat. Az intervallumot úgy módosíthatja, hogy szerkeszti a lekérdezést az Azure Stream Analytics összetevőben.

### <a name="generate-maintenance-work-orders"></a>Karbantartási munkarendelések létrehozása

Miután engedélyezi az eszköz-karbantartási *esetet*, és beállította a karbantartási tervet, futtathatja a karbantartási ütemezést a karbantartási munkarendelések generálása érdekében. A megelőző karbantartással kapcsolatos tudnivalókat [lásd a Megelőző karbantartás témakörben](../asset-management/preventive-and-reactive-maintenance/preventive-maintenance-overview.md).
