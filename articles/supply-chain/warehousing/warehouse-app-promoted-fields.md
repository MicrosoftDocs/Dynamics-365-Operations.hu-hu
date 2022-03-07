---
title: A Warehouse Management mobilalkalmazás előléptetett mezőinek konfigurálása
description: Ez a témakör azt ismerteti, hogyan lehet előléptetni vagy kiemelni bizonyos információkat bármelyik lépésben a Warehouse Management mobilalkalmazás feladatfolyamataiban.
author: MarkusFogelberg
ms.date: 10/15/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2021-10-15
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: 392fc4d7e4f423b38e8394fa25d2e42de913bfc6
ms.sourcegitcommit: 8c17717b800c2649af573851ab640368af299981
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/23/2021
ms.locfileid: "7860458"
---
# <a name="configure-promoted-fields-for-steps-in-the-warehouse-management-mobile-app"></a>A Warehouse Management mobilalkalmazás előléptetett mezőinek konfigurálása

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]
<!--KFM: Preview until GA with 10.0.23 -->

> [!IMPORTANT]
> Az ebben a témakörben ismertetett funkciók csak az új Warehouse Management mobilalkalmazásra vonatkoznak. Ezek nem érintik a régi raktár alkalmazást, amely már elavult.

Ez a témakör azt ismerteti, hogyan lehet előléptetni vagy kiemelni bizonyos információkat bármelyik lépésben a Warehouse Management mobilalkalmazás feladatfolyamataiban. Ez a képesség segítséget nyújt a dolgozók figyelmének a legfontosabb mezőkre irányításában, miközben egy folyamat során dolgoznak. Minden egyes lépésnél, minden folyamatban a rendszergazdák kiválaszthatják, hogy mely mezőket kell előléptetni, és melyik mezőket kell kiemelni.

## <a name="enable-promoted-fields-in-your-system"></a>Előléptetett mezők engedélyezése a rendszerben

Ahhoz, hogy előléptetett mezőket állítson be, az alábbi eljárást kell végrehajtania, hogy engedélyezze a szükséges funkciókat, és előállítsa a szükséges mezőneveket a Warehouse Management mobilalkalmazásban.

1. Lépjen a **Rendszerfelügyelet \> Munkaterületek \> Funkciókezelés** részre.
1. A [**Funkciókezelés** munkaterületen](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) engedélyezze a funkciót, amely a következő módon van listázva:

    - **Modul:** *Raktárkezelés*
    - **Funkció neve:** *Raktáralkalmazás lépésutasításai*

    A *Raktári alkalmazás lépésutasítások* funkciójával kapcsolatos további információkért lásd: [Lépéscímek és utasítások testreszabása a Warehouse Management mobilalkalmazáshoz](mobile-app-titles-instructions.md). Ez a funkció előfeltétele a *Raktári alkalmazásban előléptetett mezők* funkciónak.

1. Engedélyezze a felsorolt funkciót a következő módon:

    - **Modul:** *Raktárkezelés*
    - **Funkció neve:** *Raktári alkalmazásban előléptetett mezők*

    Ez a funkció az ebben a témakörben ismertetett funkció.

1. Frissítse a Warehouse Management mobilalkalmazás mezőneveit a **Raktárkezelés \> Beállítás \> Mobileszköz \> Raktári alkalmazás mezőnevei** helyen és válassza az **Alapértelmezett beállítás létrehozása** lehetőséget. ovábbi információ: [A Raktárkezelés mobilalkalmazás mezőinek konfigurálása](configure-app-field-names-priorities-warehouse.md).
1. Ismételje meg az előző lépést minden olyan jogi személynél (vállalatnál), ahol a Warehouse Management mobilalkalmazást használja.

## <a name="configure-promoted-fields-from-a-menu-specific-override"></a>Előléptetett mezők konfigurálása menüspecifikus felülbírálásból

Az alábbi eljárással állíthat be előléptetett mezőket.

1. Menüspecifikus felülbírálás létrehozása a megfelelő menühöz és lépéshez a [A Warehouse Management mobilalkalmazás lépéscímeinek és utasításainak testreszabása](mobile-app-titles-instructions.md) című témakörben leírtak szerint.
1. Keresse meg a **Lépésazonosító** és a **Menüelem neve** értékek azon kombinációját, amelyet szerkeszteni szeretne, majd jelölje ki az értéket a **Lépésazonosító** oszlopban.
1. A megjelenő oldalon, az **Előléptetett mezők kiválasztása** gyorslapon válassza az eszköztár **Mezők kijelölése** lehetőséget.
1. Az **Előléptetett mezők** párbeszédpanelen válassza ki azokat a mezőket, amelyeket elő szeretne léptetni. A kijelölt mezőke közül akár kettőt is kiemelhet. A kijelölt mezők félkövér betűkkel jelennek meg a Warehouse Management mobilalkalmazásban. A mezők kiválasztása után fontolja meg, hogy egyes képernyők csak ahhoz elég nagyok csak a legfelső egy vagy két előléptetett mező lesz látható. A beállítások használatával kapcsolatos példát lásd a témakör későbbi forgatókönyvében.

    > [!NOTE]
    > Az **Elérhető mezők** listája csak a menüelemben megjeleníthető mezőkre korlátozódik. Azonban, más tényezők (például cikkösszetétel) határozzák meg, hogy egy mező ténylegesen megjelenik-e a Warehouse Management mobilalkalmazásban. Ha beállította az előléptetett mezőket, csak a kiválasztott mezők jelennek meg a Warehouse Management mobilalkalmazás főoldalán. Ugyanakkor a dolgozók továbbra is megtekinthetik a további mezőket a részleteket lapon.

1. A beállítások alkalmazásához kattintson az **OK** gombra. A kijelölt mezők megjelenik az **Előléptetett mezők kiválasztása** gyorslapon.

## <a name="example-scenario"></a>Példaforgatókönyv

### <a name="enable-sample-data"></a>Mintaadatok engedélyezése

Ha ezt a forgatókönyvet az itt megadott mintaadatok és értékek alapján kívánja használni, akkor egy olyan rendszert kell használnia amelynél a szokásos demóadatok telepítve vannak. Az **USMF** jogi személyt is ki kell választani a kezdés előtt.

### <a name="configure-sales-picking-with-promoted-steps-on-the-license-plate-step"></a>Az értékesítési kitárolás konfigurálása előléptetett lépésekkel az azonostótábla lépésben

Ebben az eljárásban az **Értékesítési kitárolási** menüelem előléptetett és kiemelt mezőit állíthatja be az azonosítótábla lépésében.

1. Menjen a **Raktárkezelés \> Beállítás \> Mobileszköz \> Mobileszköz lépések** pontra.
1. Keresse meg a *LicensePlateId* nevű lépésazonosítót, és jelölje ki.
1. A Műveletpanelen válassza a **Lépéskonfiguráció hozzáadása** lehetőséget.
1. A legördülő párbeszédpanelen a **Menüelem** mezővel keresse meg és válassza az *Értékesítési kitárolás* lehetőséget.
1. Válassza ki az **OK** lehetőséget.
1. Megjelenik az imént létrehozott elterelés részletek lapja. Az **Előléptetett mezők kiválasztása** gyorslapon válassza az eszköztár **Mezők kijelölése** lehetőségét.
1. Az **Előléptetett mezők** párbeszédpanelen kiválaszthatja azokat a mezőket, amelyeket elő szeretne léptetni és ki szeretne emelni. Az **Elérhető mezők** listában keresse meg és válassza ki a következő mezőket, majd a gombokkal helyezze át őket a **Kiválasztott mezők** listájára:

    - Hely
    - Cikk
    - Terméknév
    - Készlet állapota

1. A felfelé nyíl és a lefelé nyíl gombokkal szabhatja testre a **Kijelölt mezők** lista mezőinek sorrendjét. A Warehouse Management mobilalkalmazásban a mezők az itt beállított sorrendben jelennek meg.
1. Válassza a **Hely** mezőt és válassza a **Kiemelés** lehetőséget.
1. A konfiguráció mentéséhez válassza az **OK** gombot.

### <a name="view-the-promoted-fields-in-the-warehouse-management-mobile-app"></a>A Warehouse Management mobilalkalmazás előléptetett mezőinek megtekintése

Ebben az eljárásban megnyitja a Warehouse Management mobilalkalmazást, és végigmegy a lépéseken, hogy megtekintse az előző művelet során előléptetett és kiemelt mezőket.

1. A Microsoft Dynamics 365 Supply Chain Management alkalmazásban hozzon létre egy értékesítési rendelést, amelynél szüksége lesz a kitárolás egy olyan helyről, amely azonosítótáblával van nyomon követve. Majd adja ki az értékesítési rendelést a raktárnak. Jegyezze fel a létrehozott munkaazonosítót.
1. Nyissa meg a Warehouse Management mobilalkalmazást és jelentkezzen be a 24-es raktárba. (A normál demóadatokban *24*-es felhasználó azonosító és az *1* jelszó használatával jelentkezzen be.)
1. Válassza a **Kimenő** menüt, majd válassza ki az **Értékesítési kitárolás** menüpontot.
1. Az 1. lépésben létrehozott munkaazonosító megadásához kövesse a képernyőn megjelenő adatbeviteli utasításokat.
1. Az **Azonosítótábla beolvasása** lépésnél láthatóak részletek lapon végrehajtott módosítások. A mezők az előléptetett mezőkhöz beállított sorrendben jelennek meg, a **Hely** mező pedig félkövér betűkkel jelenik meg.
