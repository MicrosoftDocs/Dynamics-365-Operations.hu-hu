---
title: A Warehouse Management mobilalkalmazás előléptetett mezőinek konfigurálása
description: Ez a témakör azt ismerteti, hogyan lehet konkrét információkat előléptetni és kiemelni a Raktárkezelés mobilalkalmazás feladatfolyamatának lépéseinél.
author: Mirzaab
ms.date: 08/09/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-10-15
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: 3451b1aec525cd0738af558b183f8676d20294a0
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/23/2022
ms.locfileid: "9336065"
---
# <a name="configure-promoted-fields-for-steps-in-the-warehouse-management-mobile-app"></a>A Warehouse Management mobilalkalmazás előléptetett mezőinek konfigurálása

[!include [banner](../includes/banner.md)]

> [!IMPORTANT]
> Az ebben a cikkben leírt funkciók csak az új Raktárkezelés mobilalkalmazásra vonatkoznak. Ezek nem érintik a régi raktár alkalmazást, amely már elavult.

Ez a témakör azt ismerteti, hogyan lehet konkrét információkat előléptetni és kiemelni a Raktárkezelés mobilalkalmazás feladatfolyamatának lépéseinél. Ez a képesség segítséget nyújt a dolgozók figyelmének a legfontosabb mezőkre irányításában, miközben egy folyamat során dolgoznak. Minden egyes lépésnél, minden folyamatban a rendszergazdák kiválaszthatják, hogy mely mezőket kell előléptetni, és melyik mezőket kell kiemelni.

## <a name="enable-promoted-fields-in-your-system"></a>Előléptetett mezők engedélyezése a rendszerben

Ha az Ellátásilánc-kezelés 10.0.28-as vagy korábbi verzióját futtatja, akkor a többi előléptetett mező beállítása előtt végre kell hoznia az alábbi eljárást, hogy engedélyezze a szükséges funkciókat, és generálja a szükséges mezőneveket a Raktárkezelés mobilalkalmazásban. Ha az Ellátásilánc-kezelés 10.0.29-es vagy újabb verziója fut, a funkciók kötelezőek, és nem lehet kikapcsolni, ezért ezt az eljárást kihagyhatja.

1. Lépjen a **Rendszerfelügyelet \> Munkaterületek \> Funkciókezelés** részre. (Lásd: [Funkciókezelés –](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) áttekintés a lapról való további tájékoztatásért.)
1. Győződjön meg arról, hogy a *Raktár alkalmazás lépéséhez* funkció be van kapcsolva a rendszeren. Ez a funkció előfeltétele a *Raktári alkalmazásban előléptetett mezők* funkciónak. Az Ellátásilánc-kezelés 10.0.29-es verziója szerint kötelező, és nem lehet kikapcsolni. A *Raktári alkalmazás lépésutasítások* funkciójával kapcsolatos további információkért lásd: [Lépéscímek és utasítások testreszabása a Warehouse Management mobilalkalmazáshoz](mobile-app-titles-instructions.md).
1. Győződjön meg róla, hogy a *Raktári alkalmazás által támogatott mezők* szolgáltatás be van kapcsolva a rendszeren. Ez az ebben a cikkben leírt funkció. Az Ellátásilánc-kezelés 10.0.29-es verziója szerint kötelező, és nem lehet kikapcsolni.
1. Frissítse a Warehouse Management mobilalkalmazás mezőneveit a **Raktárkezelés \> Beállítás \> Mobileszköz \> Raktári alkalmazás mezőnevei** helyen és válassza az **Alapértelmezett beállítás létrehozása** lehetőséget. Ismételje meg ezt a lépést minden olyan jogi személynél (vállalatnál), ahol a Raktárkezelés mobilalkalmazást használja. ovábbi információ: [A Raktárkezelés mobilalkalmazás mezőinek konfigurálása](configure-app-field-names-priorities-warehouse.md).

## <a name="configure-promoted-fields-from-a-menu-specific-override"></a>Előléptetett mezők konfigurálása menüspecifikus felülbírálásból

Az alábbi eljárással állíthat be előléptetett mezőket.

1. Menüspecifikus felülbírálás létrehozása a megfelelő menühöz és lépéshez a [A Warehouse Management mobilalkalmazás lépéscímeinek és utasításainak testreszabása](mobile-app-titles-instructions.md) című témakörben leírtak szerint.
1. Keresse meg a **Lépésazonosító** és a **Menüelem neve** értékek azon kombinációját, amelyet szerkeszteni szeretne, majd jelölje ki az értéket a **Lépésazonosító** oszlopban.
1. A megjelenő oldalon, az **Előléptetett mezők kiválasztása** gyorslapon válassza az eszköztár **Mezők kijelölése** lehetőséget.
1. Az **Előléptetett mezők** párbeszédpanelen válassza ki azokat a mezőket, amelyeket elő szeretne léptetni. A kijelölt mezőke közül akár kettőt is kiemelhet. A kijelölt mezők félkövér betűkkel jelennek meg a Warehouse Management mobilalkalmazásban. A mezők kiválasztása után fontolja meg, hogy egyes képernyők csak ahhoz elég nagyok csak a legfelső egy vagy két előléptetett mező lesz látható. A beállítások használatát bemutatja egy példa, amely a cikk későbbi forgatókönyvében olvasható.

    > [!NOTE]
    > Az **Elérhető mezők** listája csak a menüelemben megjeleníthető mezőkre korlátozódik. Azonban, más tényezők (például cikkösszetétel) határozzák meg, hogy egy mező ténylegesen megjelenik-e a Warehouse Management mobilalkalmazásban. Ha beállította az előléptetett mezőket, csak a kiválasztott mezők jelennek meg a Warehouse Management mobilalkalmazás főoldalán. Ugyanakkor a dolgozók továbbra is megtekinthetik a további mezőket a részleteket lapon.

1. A beállítások alkalmazásához kattintson az **OK** gombra. A kijelölt mezők megjelenik az **Előléptetett mezők kiválasztása** gyorslapon.

## <a name="example-scenario"></a>Példaforgatókönyv

### <a name="enable-sample-data"></a>Mintaadatok engedélyezése

Ahhoz, hogy a megadott mintarekordokat és értékeket használni tudja az eseten, olyan rendszert kell használnia, ahol telepítve vannak a [szabványos bemutatóadatok](../../fin-ops-core/fin-ops/get-started/demo-data.md). Az **USMF** jogi személyt is ki kell választani a kezdés előtt.

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
