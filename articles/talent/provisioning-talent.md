---
title: Talent üzembe helyezése
description: Ez a témakör végigvezeti Önt az új környezet létesítésén a Microsoft Dynamics 365 Talent számára.
author: andreabichsel
manager: AnnBe
ms.date: 05/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: 17271
ms.assetid: ba1ad49d-8232-400e-b11f-525423506a3f
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2017-11-20
ms.dyn365.ops.version: Talent July 2017 update
ms.openlocfilehash: b705304788f47e4a5d2a9f1b2bf42a065428ea0f
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/06/2019
ms.locfileid: "2898133"
---
# <a name="provision-talent"></a>A Talent létesítése

Ez a témakör végigvezeti Önt az új termelési környezet létesítésén a Microsoft Dynamics 365 Talent számára. Ez a témakör feltételezi, hogy a Talent rendszert felhőalapú szolgáltatón (CSP) keresztül vagy vállalati architektúra (EA) megállapodás részeként vásárolta. Ha rendelkezik már meglévő Microsoft Dynamics 365 licenccel, amely már tartalmazza a Talent szolgáltatástervet, és nem tudja elvégezni a témakörben szereplő lépéseket, forduljon a támogatási szolgálathoz.

Első lépésként a globális rendszergazdának be kell jelentkeznie a [Microsoft Dynamics Lifecycle Services](https://lcs.dynamics.com) (LCS) szolgáltatásba, és létre kell hoznia egy új Talent projektet. Hacsak licencelési probléma meg nem akadályozza a Talent létesítését, a Támogatás vagy a Dynamics Service Engineering (DSE) képviselőinek segítségére nincsen szkség.

## <a name="create-an-lcs-project"></a>LCS-projekt létrehozása
Az LCS a Talent kezelésére való használatához előbb egy LCS-projektet kell létrehozni.

1. Jelentkezzen be az [LCS](https://lcs.dynamics.com/Logon/Index)-be azzal a fiókkal, amelyet a Talentre való előfizetéshez használt.
2. Válassza ki a pluszjelet (**+**) projekt létrehozásához.
3. Válassza a **Microsoft Dynamics 365 Talent** terméknévként és termékverzióként.
4. A **Dynamics 365 Talent** frissítési módszertan kiválasztása.
5. Válassza a **Létrehozása** lehetőséget.

A Talent használatának megkezdésével kapcsolatos tudnivalókhoz lásd az új projektben létrehozott **Talent** módszert. Miután elkészült a projekt létrehozása, hajtsa végre a következő eljárást a Talent környezetének létesítéséhez.

## <a name="provision-a-talent-project"></a>Talent-projekt létesítése
LCS-projekt létrehozása után a Talentet létesítheti egy környezetbe.

1. Az LCS-projektben válassza a **Talent alkalmazás kezelése** csempét.
2. Azt jelzi, hogy ez a Talent Védőfal- vagy termelési példánya. A korai előzetes funkciók elérhetők lehetnek a Védőfalpéldányokban, a korai visszajelzések és tesztelés érdekében. 
    > [!NOTE]
    > A Talent példánytípus eltér a Microsoft Power Apps-környezet Power Apps Felügyeleti központjában beállítható példánytípusától.
3. Válassza ki a **Demó adatokat tartalmaz** beállítást, ha azt szeretné, hogy a környezet ugyanazokat a demóadatokat tartalmazza, mint amelyeket a Talent tesztverziókban használtak. Ez hosszú távú bemutató vagy képzési környezetben előnyös, de éles környezetben soha nem szabad használni.  Megjegyzés: az első telepítés esetén kell ezt a lehetőséget kiválasztania. Meglévő telepítés később nem frissíthető.
4. A Talent alkalmazást mindig biztosítva van a Microsoft Power Apps környezetben annak érdekében, hogy biztosítsa a Power Apps integrációját és bővíthetőségét. Olvassa el a témakör „Power Apps-környezet kiválasztása” című fejezetét a folytatás előtt. Ha még nem rendelkezik Power Apps környezettel, válassza a Környezetek kezelése LCS-ben lehetőséget, vagy látogasson el a Power Apps adminisztrációs központjába. Kövesse a [Power Apps környezet](https://docs.microsoft.com/powerapps/administrator/create-environment) létrehozása részben leírt lépéseket.

    > [!NOTE]
    > A meglévő környezetek megtekintéséhez vagy új környezetek létrehozásához a Talentet létesítő bérlő adminisztrátort hozzá kell rendelni a Power Apps P2 licenchez. Ha szervezete nem rendelkezik Power Apps P2 licenccel, kaphat egyet a CSP-től vagy a [Power Apps árképzési lapon](https://powerapps.microsoft.com/pricing/).

5. Válassza ki azt a környezetet, amelybe telepíteni szeretné a Talent szolgáltatást.
6. Válassza az **Igen** lehetőséget a feltételek elfogadásához és a telepítés megkezdéséhez.

    Az új környezet megjelenik a bal oldali navigációs panelen látható környezetek listájában. Azonban a környezet nem indítható el mindaddig, amíg a telepítés állapota nem frissül **Telepítve** értékre. Ez a folyamat jellemzően csak pár percig tart. Ha a jogosultságkezelés folyamata sikertelen, kérje az Ügyfélszolgálat segítségét.

7. Válassza a **Bejelentkezés a Talent rendszerbe** az új környezet használatához.

    > [!NOTE]
    > Ha még nem írta alá a végső követelményeket, a Talent tesztpéldányát telepítheti a projektben. Ezután ezt a példányt használhatja a megoldás tesztelésére mindaddig, amíg alá nem ír. Ha az új környezet teszteléshez használja, ismételje meg ezt az eljárást, hogy létrehozzon egy éles környezetet.

    > Mivel csak két LCS környezet van engedélyezve a Talent előfizetés részeként, vegye fontolóra egy ingyenes, 60 napos [Talent próba környezet igénybevételét](https://dynamics.microsoft.com/talent/overview/). Bár a próbakörnyezetek tulajdonosa az a felhasználó, aki kérte pket, más felhasználók is meghívhatók az Alapvető HR környezet rendszergazdai felületén keresztül. A próbakörnyezetek olyan kitalált adatokat tartalmaznak, amelyek segítségével biztonságosan fel lehet fedezni a programot. Nem úgy tervezték, hogy termelési környezetekben használják őket. Kérjük, vegye figyelembe, hogy amikor a próbakörnyezet 60 nap elteltével lejár, a benne lévő minden adat törlődik, és azok nem is állíthatók helyre. Regisztrálhat egy új próbakörnyezetre, miután lejárt a meglévő környezet.

## <a name="select-a-power-apps-environment"></a>Power Apps-környezet kiválasztása

A Talent és Power Apps környezetek közötti integrációval integrálhatja és kiterjesztheti a Talent-adatok használatát a Power Apps-eszközökkel. A Power Apps környezetek céljának megértése nem csak a Talent kiterjesztésére szolgáló alkalmazások felépítésében segít, hanem a helyes környezet kiválasztásában is segít a Talent létesítésekor. Információ a Power Apps-környezetekről, beleértve a környezeti hatásköröket, a környezethez való hozzáférést, valamint a környezet létrehozását és kiválasztását: [Power Apps-környezetek bejelentése](https://powerapps.microsoft.com/blog/powerapps-environments/). 

Kövesse az alábbi útmutatást, amikor azt állapítja meg, hogy mely Power Apps környezetbe kell telepíteni a Talent alkalmazást: 

1. Az LCS-ben válassza a **Környezetek kezelése** lehetőséget, vagy lépjen közvetlenül a Power Apps adminisztrációs központjába, ahol megtekintheti a meglévő környezeteket és új környezeteket hozhat létre.
2. Egyetlen Talent-környezet van egyetlen Power Apps-környezethez rendelve.
3. A Power Apps-környezet tartalmazza a Talent alkalmazást a megfelelő Power Apps, Power Automate és Common Data Service alkalmazásokkal együtt. Ha a Power Apps környezetet törlik, törlődnek a benne lévő alkalmazások is. Talent környezet létesítésekor vagy **Próba** vagy **Termelési** környezetek létesíthetők. Válassza ki a környezet típusát a környezet későbbi használata alapján. 
4. Az adatintegrációs és tesztelési stratégiákat figyelembe kell venni, például: védőfal, UAT vagy termelés. Javasoljuk, hogy vegye figyelembe a telepítés különböző következményeit, mert nem könnyű a későbbiekben megváltoztatni a Power Apps-környezethez leképzett Talent környezetet.
5. A következő Power Apps környezetek a Talent esetében nem használhatók, és ki lesznek szűrve a kiválasztási listából a LCS portálon belül:
 
    - **Alapértelmezett Power Apps környezetek** – Bár minden bérlő számára automatikusan megtörténik az alapértelmezett Power Apps-környezet létesítése, nem javasoljuk velük a Talent használatát, hiszen minden bérlő felhasználónak hozzáférése van a Power Apps-környezethez, és a Power Apps vagy Power Automate-integrációk tesztelése és feltérképezése során véletlenül kárt tehetnek termelési adatokban.
   
    - **Tesztkörnyezetek** Ezek a környezetk lejárati idővel kerülnek létrehozásra, és ezután lejárnak, ami automatikusan eltávolítja a környezetet és minden abban található Talent példányt.
   
    - **Nem támogatott régiók** – Jelenleg a Talent csak az alábbi területeken támogatott: Egyesült Államok, Európa, Egyesült Királyság és Ausztrália, Kanada és Ázsia.
  
6. Miután meghatározta a használandó a helyes környezetet, folytathatja a létesítési folyamat. 
 
## <a name="grant-access-to-the-environment"></a>Hozzáférés biztosítása a környezethez
Alapértelmezés szerint a környezetet csak az a globális rendszergazda érheti el, aki létrehozta. Az alkalmazás további felhasználóinak azonban kifejezett módon engedélyezni kell a hozzáférést. Ha hozzáférést szeretne adni, fel kell vennie a felhasználókat, és hozzájuk kell rendelnie a megfelelő szerepköröket a Core HR környezetben. A Talent-et telepítő globális rendszergazdának el kell elindítania az Attract és az Onboard alkalmazást is ahhoz, hogy befejezze az inicializálást és engedélyezze a hozzáférést más bérlő felhasználók számára is.  Amíg erre nem kerül sor, más felhasználók nem tudják elérni az Attract és Onboard alkalmazást, és hozzáférési hibákra vonatkozó üzeneteket fognak kapni. További tudnivalókért lásd: [Új felhasználók létrehozása](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/sysadmin/tasks/create-new-users) és [Felhasználók hozzárendelése biztonsági szerepkörökhöz](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/sysadmin/tasks/assign-users-security-roles). 
