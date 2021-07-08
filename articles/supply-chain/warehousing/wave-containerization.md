---
title: Tárolóra bontás
description: Ez a témakör azt mutatja be, hogyan automatizálhatja a szállítmányok tárolóra bontását. Az automatikus tárolóra bontási folyamat a hullám feldolgozásakor létrehozza a tárolókat és a kitárolási munkát.
author: Mirzaab
ms.date: 03/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSWaveTemplateTable, InventLocationIdLookup, WHSContainerType, WHSContainerGroup, WHSContainerizationTable, WHSContainerizationBreak, WHSCreateContainerBreak, WHSContainerStructure, WHSContainerTable, WHSContainerizatonHistory, WHSContainerPackingPolicyChange, WHSManifestShipmentContainers, WHSAllowedContainerTypeGroup, WHSPostMethod, WHSContainerCreateDialog, WHSContainerCloseDiag, WHSContainer
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-03-08
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: 88e38989e3d3e46d0c43779659bc6ea2e29f08e2
ms.sourcegitcommit: 8e846b52763f90d2232ec7d427839f4722570bce
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/22/2021
ms.locfileid: "6292737"
---
# <a name="containerization"></a>Tárolóra bontás

[!include [banner](../includes/banner.md)]

Ez a témakör azt mutatja be, hogyan automatizálhatja a szállítmányok tárolóra bontását. Az automatikus tárolóra bontási folyamat a hullám feldolgozásakor létrehozza a tárolókat és a kitárolási munkát.

A tárolóra bontási folyamat beállításához kövesse az alábbi lépéseket:

- **Tároló típusa** – A tárolók fizikai jellemzőinek meghatározása. A tárolótípusokkal csomagolhatja be a készletcikkeket egy adott típusú és méretű csomagolóegységbe, például dobozba vagy raklapba.
- **Tárolócsoportok** – Csoportok létrehozása hasonló tárolótípusokból. Egy tárolócsoport tartalmazhat például hasonló méretű tárolótípusokat. A tárolócsoport határozza meg, milyen sorrendben csomagolja a rendszer a tárolókat, és hány százalékban tölti fel az egyes tárolókat.
- **Tárolóépítési sablon** – Olyan sablonok létrehozása, amelyek meghatározzák a tárolóra bontás szabályait. Példa: készletkeverési szabályok és egyéb csomagolási stratégiák.
- **Hullámsablonok** – Egy vagy több hullámsablon beálllítása a kitározási munkák létrehozásához vagy a tárolóra bontáshoz.

## <a name="create-wave-templates-for-containerization"></a>Hullámsablonok létrehozása a tárolóra bontáshoz

Egy vagy több szállítási hullámsablont kell felállítania a tárolóra bontáshoz. A hullámsablonok feltételei határozzák meg az alábbiakat:

- Hogyan dolgozza fel a rendszer a hullámokat. Ez történhet manuálisan vagy automatikusan is.
- Hogyan jön létre a kitárolási munka. Ezt a hullámmódszerek határozzák meg. A hullámsablonnak tartalmaznia kell a **tárolóra bontás** módszert.
- Hogyan kerülnek összerendezésre a cikkek vagy a felosztási sorok egy hullámmal.

További tájékoztatás: [Hullámsablonok](wave-templates.md).

## <a name="create-container-types"></a>Új tárolótípusok létrehozása

A tárolótípusok használatával a tárolók leírását hozhatja létre, beleértve például a méretek maximális értékét vagy a terhelési kapacitást. Egy tárolóra bontott hullám feldolgozása során a rendszer a megadott tárolótípus-információk alapján hozza létre a tárolókat.

Tárolótípus beállításához kövesse az alábbi lépéseket:

1. Ugorjon a **Raktárkezelés** \> **Beállítás** \> **Tárolók** \> **Tárolótípusok** pontra.
1. Válassza ki az **Új** lehetőséget egy új tárolótípus létrehozásához.
1. Adjon meg a tárolótípus számára egy egyedi azonosítót, valamint leírást.
1. A **Tárasúly** mezőben adja meg a tároló valós vagy becsült önsúlyát.
1. A **Maximum súly** mezőben adja meg a tárolóba helyezhető maximális súlyt.
1. A **Tárolóra bontás maximális térfogata**, **Tárolóra bontás maximális hossza**, **Tárolóra bontás maximális szélessége** és a **Tárolóra bontás maximális magassága** mezőkben adja meg a tároló fizikai dimenzióit.

    > [!NOTE]
    > A hosszúság és a szélesség felcserélhetők egymással. Ez azt jelenti, hogy a cikkek szükség szerint elforgathatók oldalirányban, vagy az X tengely mentén. Ha például a tároló 2 láb hosszú és 1 láb széles, akkor módosíthatja a hosszúság értékét 1 lábra, a szélességet pedig 2 lábra. Ez ugyanakkor nincs hatással a tároló magasságára. A függőleges elforgatáshoz nem változtathatja meg a magasság értékét.

1. Az attribútumok mezőiben adjon meg egyedi attribútumértékeket a tároló számára. Az attribútumok olyan egyedi értékek, melyek segítségével a cikkeket egyébként nem elérhető érték alapján lehet szűrni vagy rendezni. Ha például egy adott vevő számára szeretne cikkeket becsomagolni, akkor létrehozhat egy attribútumot a vevő nevével. Ezeket az attribútumtípusokat az **Tárolóattribútumok** oldalon hozhatja létre.

## <a name="create-container-groups"></a>Tárolócsoportok létrehozása

A tárolótípusokat logikai alapon csoportokba vonhatja össze. Minden egyes csoportra vonatkozóan határozza meg azt a sorrendet, amelyben a tárolók feltöltését elvégzi és a tárolók százalékát a kitöltéshez. A rendszer a cikk méretének dimenziói alapján határozza meg, hogy elfér-e a tárolóban. Az alkalmazás azt a tárolót használja, amely legközelebb áll a kérdéses cikk méretéhez. Ha egy csoportban több tárolótípus is van, akkor érdemes őket méretsorrendbe rendezni, úgy, hogy a legnagyobb tároló legyen a lista tetején 1-es számmal, a legkisebb pedig az utolsó.

Tárolócsport beállításához kövesse az alábbi lépéseket:

1. Ugorjon a **Raktárkezelés** \> **Beállítás** \> **Tárolók** \> **Tárolócsoportok** pontra.
1. Válassza ki az **Új** lehetőséget egy új tárolócsoport létrehozásához.
1. Adjon meg a tárolócsoport számára egy egyedi azonosítót, valamint leírást.
1. A **Részletek** gyorslapon kattintson az **Új** gombra, amellyel új tárolótípust adhat hozzá a csoporthoz.
1. Adjon meg egy tárolótípust a **Tárolótípus** mezőben.
1. Válassza a **Mozgatás felfelé** vagy **Mozgatás lefelé** lehetőséget a sorrend megadásához, amiben a tárolótípusokat csomagolják.

## <a name="create-container-build-templates"></a>Tárolóépítési sablonok létrehozása

Saját döntése alapján állíthatja be a tárolóra bontási folyamat szabályait, például a készletkeverési szabályokat és az egyéb csomagolási stratégiákat. Például beállíthat egy olyan szabályt, amely alapján a dolgozók nem csomagolhatnak egyazon tárolóba több különböző vevő értékesítési rendeléseit képviselő felosztási sorokat.

Tárolóépítési sablon beállításához kövesse az alábbi lépéseket.

1. Ugorjon a **Raktárkezelés** \> **Beállítás** \> **Tárolók** \> **Tárolóépítési sablon** pontra.
1. Új tárolóépítési sablon létrehozása.
1. A **Tárolóra bontás neve** és a **Sorszám** mezőkben adja meg rendre a tárolóépítési sablon nevét és a felosztási sorokhoz társított rendelést.

    > [!NOTE]
    > A rendszer az első olyan sablont fogja használni, amelynek feltételeit a felosztási sor teljesíti. Ezért javasoljuk, hogy a legspecifikusabb feltételekkel kialakított sablont helyezze a lista elejére. Minél enyhébbek a feltételek, annál valószínűbb, hogy egy felosztási sor megfelel a feltételeknek. Így viszont egyes esetekben nem a megfelelő tárolóhoz rendeződnek hozzá a sorok. Ha szükséges, a sablonok sorrendjének átrendezéséhez válassza a **Mozgatás felfelé** vagy **Mozgatás lefelé** lehetőséget.

1. A **Tárolócsoport azonosítója** mezőben válassza ki, melyik tárolócsoportból szereztne tárolókat létrehozni.
1. Az **Alaplekérdezés-típusok** mezőben adja meg a lekérdezéstípust, amely meghatározza a becsomagolni kívánt terméket és a szűrőlekérdezés alapját. Ehhez a következő lehetőségek állnak rendelkezésre:

      - **Értékesítési felosztás sora** – Értékesítési rendelésekhez létrehozott felosztási sorok becsomagolása.
      - **Átmozgatási felosztás sora** – Átmozgatási rendelésekhez létrehozott felosztási sorok becsomagolása.
      - **Tároló** – A tárolóra bontási folyamat által már korábban létrehozott tároló becsomatolása. Ezt használja például az egymásba ágyazódó tárolókhoz.

        > [!NOTE]
        > Egymásba ágyazódó tárolóknál megismételhetővé kell tennie a tárolóra bontási folyamatot. További tájékoztatás: [Hullámsablonok](wave-templates.md).

1. Az **Általános** gyorslap **Hullámlépéskód** mezőjében adja meg annak a hullámfolyamatnak az egyedi azonosítóját, amely összekapcsolja a tárolóépítési sablont egy hullámsablon lépéseivel.
1. A **Kitárolások szétosztásának engedélyezése** jelölőnégyzet bejelölésével a dolgozók egy adott munkarendelésből több különböző tárolóba is csomagolhatják a cikkeket. Ehhez az is szükséges, hogy a teljes mennyiség elférjen a tárolóban. A felosztási sor legnagyobb mértékegysége mindig használatban lesz.
1. A **Csomagolás egység szerint** mezőben megválaszthatja a tárolót jelképező mértékegységet. Így például jelezheti, hogy a tároló egy láda. Ha mértékegység alapján csomagolja a cikkeket, akkor nem határozhat meg tárolócsoportot, mert a mértékegység eleve maga a tároló.
1. A **Tárolócsomagolási stratégia** mezőben adja meg a használni kívánt csomagolási stratégiát. Ehhez a következő lehetőségek állnak rendelkezésre:

    > [!NOTE]
    > A stratégia csak értékesítési felosztási sorokra és átmozgatási felosztási sorokra vonatkozik.

      - **Csomagolás az összes nyitott tárolóba** – A rendszer kiértékeli, hogy a felosztási sor befér-e valamelyik, a tárolóra bontási ciklus során létrejött tárolóba.
      - **Csomagolás csak az aktuális tárolóba** – A rendszer csak azt vizsgálja meg, hogy a felosztási sor belefér-e a legutóbb létrehozott tárolóba.

    További információk és a tárolócsomagolási stratégiák használatára vonatkozó példák: [Tárolócsomagolási stratégiák](container-packing-strategy-overview.md).

1. A szabályok felállításához a felosztási sorok tárolóba való csomagolásához válassza a **Vegyítési logika felbontásai**. Például létrehozhat olyan szabályt, amely alapján a dolgozók két különböző tétel felosztási sorait is becsomagolhatják ugyanabba a tárolóba. Vegyítési szabály megadásához tegye a következőket:

    1. A **Vegyítési logika felbontásai** lapon válassza az **Új** lehetőséget.
    1. A **Tábla** mezőben válassza ki azt a táblát, amely tartalmazza a vegyítési logika felbontási feltételeként használni kívánt mezőt.
    1. A **Mezőkiválasztás** mezőben válassza ki azt a mezőt, amelyet a vegyítési logika felbontási feltételeként kíván használni.
    1. Ismételje ezeket a lépéseket mindaddig, amíg a vegyítési logika valamennyi felbontási feltételét megadta.

    > [!NOTE]
    > Vegyítési logika használata esetén javasolt, hogy a szűrési feltételek lekérdezésében ugyanazokat a mezőket használja a rendezéshez. Ez csökkenti a létrehozásra kerülő tárolók számát.
