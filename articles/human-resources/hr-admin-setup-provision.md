---
title: Human Resources környezet létesítése
description: ''
author: andreabichsel
manager: AnnBe
ms.date: 02/18/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: f105144047c64fc8e9d42da8d7525a8cc3912c33
ms.sourcegitcommit: 0dace221e8874021dd212271567666f717d39793
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/19/2020
ms.locfileid: "3071614"
---
# <a name="provision-human-resources"></a>Human Resources környezet létesítése

Ez a cikk végigvezeti Önt az új termelési környezet létesítésén a Microsoft Dynamics 365 Human Resources számára. Ez a cikk feltételezi, hogy a Human Resources rendszert felhőalapú szolgáltatón (CSP) keresztül vagy vállalati architektúra (EA) megállapodás részeként vásárolta. Ha rendelkezik meglévő Microsoft Dynamics 365-licenccel, amely már tartalmazza a Human Resources szolgáltatási konstrukciót, és nem tudja elvégezni a cikkben szereplő lépéseket, forduljon a támogatási szolgálathoz.

Első lépésként a globális rendszergazdának be kell jelentkeznie a [Microsoft Dynamics Lifecycle Services](https://lcs.dynamics.com) (LCS) szolgáltatásba, és létre kell hoznia egy új Human Resources projektet. Ha licencelési probléma nem akadályozza meg a Human Resources létesítését, a támogatás vagy a Dynamics Service Engineering (DSE) képviselőinek segítségére nincsen szükség.

## <a name="create-an-lcs-project"></a>LCS-projekt létrehozása

Az LCS-nek a Human Resources kezelésére való használatához előbb egy LCS-projektet kell létrehozni.

1. Jelentkezzen be az [LCS](https://lcs.dynamics.com/Logon/Index)-be azzal a fiókkal, amelyet a Human Resources szolgáltatásra való feliratkozáshoz használt.

2. Válassza ki a pluszjelet (**+**) projekt létrehozásához.

3. Válassza a **Microsoft Dynamics 365 Human Resources** terméknévként és termékverzióként.

4. A **Dynamics 365 Human Resources** frissítési módszertan kiválasztása.

5. Válassza a **Létrehozása** lehetőséget.

A Human Resources használatának megkezdésével kapcsolatos tudnivalókhoz lásd az új projektben létrehozott **Human Resources** módszertant. Miután elkészült a projekt létrehozásával, hajtsa végre a következő eljárást a Human Resources környezetének létesítéséhez.

## <a name="provision-a-human-resources-project"></a>Human Resources-projekt létesítése

Miután létrehozott egy LCS-projektet, elvégezheti a Human Resources létesítését a környezetben.

1. Az LCS-projektben válassza a **Human Resources alkalmazás kezelése** csempét.

2. Azt jelzi, hogy ez a Human Resources tesztkörnyezete-e vagy a termelési példánya. A korai előzetes funkciók elérhetők lehetnek a Védőfalpéldányokban, a korai visszajelzések és tesztelés érdekében.
   
    > [!NOTE]
    > A Talent példány típusát a beállítás után nem lehet módosítani. Folytatás előtt győződjön meg arról, hogy a helyes példánytípus van kiválasztva.</br></br>
    > A Human Resources példánytípus eltér a Microsoft Power Apps környezet Power Apps Felügyeleti központjában beállítható példánytípusától.
    
3. Válassza ki a **Demó adatokat tartalmaz** beállítást, ha azt szeretné, hogy a környezet ugyanazokat a demóadatokat tartalmazza, mint amelyeket a Human Resources tesztverzióiban használt. Ez hosszú távú bemutató vagy képzési környezetben előnyös, de éles környezetben soha nem szabad használni.  Megjegyzés: az első telepítés esetén kell ezt a lehetőséget kiválasztania. Meglévő telepítés később nem frissíthető.

4. A Human Resources szolgáltatást mindig Microsoft Power Apps környezetbe kell létesíteni annak érdekében, hogy biztosítsa a Power Apps integrációját és bővíthetőségét. Olvassa el a témakör „Power Apps környezet kiválasztása” című cikkét a folytatás előtt. Ha még nem rendelkezik Power Apps környezettel, válassza a Környezetek kezelése LCS-ben lehetőséget, vagy látogasson el a Power Apps adminisztrációs központjába. Kövesse a [Power Apps környezet](https://docs.microsoft.com/powerapps/administrator/create-environment) létrehozása részben leírt lépéseket.

5. Válassza ki azt a környezetet, amelybe létesíteni szeretné a Human Resources szolgáltatást.

6. Válassza az **Igen** lehetőséget a feltételek elfogadásához és a telepítés megkezdéséhez.

   Az új környezet megjelenik a bal oldali navigációs panelen látható környezetek listájában. Azonban a környezet nem indítható el mindaddig, amíg a telepítés állapota nem frissül **Telepítve** értékre. Ez a folyamat jellemzően csak pár percig tart. Ha a jogosultságkezelés folyamata sikertelen, kérje az Ügyfélszolgálat segítségét.

7. Válassza a **Bejelentkezés a Human Resources szolgáltatásba** lehetőséget az új környezet használatához.

    > [!NOTE]
    > Ha még nem hagyta jóvá a végső követelményeket, a Human Resources tesztpéldányát telepítheti a projektben. Ezután ezt a példányt használhatja a megoldás tesztelésére mindaddig, amíg alá nem ír. Ha az új környezet teszteléshez használja, ismételje meg ezt az eljárást, hogy létrehozzon egy éles környezetet.

    > Mivel csak két LCS környezet van engedélyezve a Human Resources-előfizetés részeként, vegye fontolóra egy ingyenes, 60 napos [Human Resources próbakörnyezet igénybevételét](https://dynamics.microsoft.com/talent/overview/). Bár a próbakörnyezetek tulajdonosa az a felhasználó, aki kérte pket, más felhasználók is meghívhatók a Human Resources környezet rendszergazdai felületén keresztül. A próbakörnyezetek olyan kitalált adatokat tartalmaznak, amelyek segítségével biztonságosan fel lehet fedezni a programot. Nem úgy tervezték, hogy termelési környezetekben használják őket. Kérjük, vegye figyelembe, hogy amikor a próbakörnyezet 60 nap elteltével lejár, a benne lévő minden adat törlődik, és azok nem is állíthatók helyre. Regisztrálhat egy új próbakörnyezetre, miután lejárt a meglévő környezet.

## <a name="select-a-power-apps-environment"></a>Power Apps-környezet kiválasztása

A Human Resources és a Power Apps környezetei közötti integrációval integrálhatja és kiterjesztheti a Human Resources adatainak használatát a Power Apps-eszközökkel. A Power Apps környezetek céljának megértése nem csak a Human Resources kiterjesztésére szolgáló alkalmazások felépítésében segít, hanem a helyes környezet kiválasztásában is segít a Human Resources létesítésekor. Információ a Power Apps-környezetekről, beleértve a környezeti hatásköröket, a környezethez való hozzáférést, valamint a környezet létrehozását és kiválasztását: [Power Apps-környezetek bejelentése](https://powerapps.microsoft.com/blog/powerapps-environments/). 

Kövesse az alábbi útmutatást, amikor azt állapítja meg, hogy melyik Power Apps környezetbe kell telepíteni a Human Resources szolgáltatást: 

1. Az LCS-ben válassza a **Környezetek kezelése** lehetőséget, vagy lépjen közvetlenül a Power Apps adminisztrációs központjába, ahol megtekintheti a meglévő környezeteket és új környezeteket hozhat létre.

2. Egyetlen Human Resources környezet van egyetlen Power Apps környezethez rendelve.

3. A Power Apps környezet tartalmazza a Human Resources szolgáltatást a megfelelő Power Apps, Power Automate és Common Data Service alkalmazásokkal együtt. Ha a Power Apps környezetet törlik, törlődnek a benne lévő alkalmazások is. Human Resources környezet létesítésekor **Próba** vagy **Termelési** környezetek létesíthetők. Válassza ki a környezet típusát a környezet későbbi használata alapján. 

4. Az adatintegrációs és tesztelési stratégiákat figyelembe kell venni, például: védőfal, UAT vagy termelés. Javasoljuk, hogy vegye figyelembe a telepítés különböző következményeit, mert nem könnyű a későbbiekben megváltoztatni a Power Apps környezethez hozzárendelt Human Resources környezetet.

5. A következő Power Apps környezetek a Human Resources esetében nem használhatók, és ki lesznek szűrve a kiválasztási listából a LCS portálon belül:
 
    - **Alapértelmezett Power Apps környezetek** – Bár minden bérlő számára automatikusan megtörténik az alapértelmezett Power Apps környezet létesítése, nem javasoljuk velük a Human Resources használatát, hiszen minden bérlő felhasználónak hozzáférése van a Power Apps környezethez, és a Power Apps vagy Power Automate integrációk tesztelése és feltérképezése során véletlenül kárt tehetnek termelési adatokban.
   
    - **Tesztkörnyezetek** – Ezek a környezetek lejárati idővel kerülnek létrehozásra, és ezután lejárnak, ami automatikusan eltávolítja a környezetet és az abban található összes Human Resources példányt.
   
    - **Nem támogatott régiók** – Jelenleg a Human Resources csak a következő régiókban támogatott: Egyesült Államok, Európa, Egyesült Királyság és Ausztrália, Kanada és Ázsia.
  
6. Miután meghatározta a használandó a helyes környezetet, folytathatja a létesítési folyamat. 
 
## <a name="grant-access-to-the-environment"></a>Hozzáférés biztosítása a környezethez

Alapértelmezés szerint a környezetet csak az a globális rendszergazda érheti el, aki létrehozta. Az alkalmazás további felhasználóinak azonban kifejezett módon engedélyezni kell a hozzáférést. Ha hozzáférést szeretne adni, fel kell vennie a felhasználókat, és hozzájuk kell rendelnie a megfelelő szerepköröket a Human Resources környezetben. A Human Resources szolgáltatást telepítő globális rendszergazdának el kell indítania az Attract és az Onboard alkalmazást is ahhoz, hogy befejezze az inicializálást, és engedélyezze a hozzáférést más bérlő felhasználók számára is.  Amíg erre nem kerül sor, más felhasználók nem tudják elérni az Attract és Onboard alkalmazást, és hozzáférési hibákra vonatkozó üzeneteket fognak kapni. További tudnivalókért lásd: [Új felhasználók létrehozása](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/sysadmin/tasks/create-new-users) és [Felhasználók hozzárendelése biztonsági szerepkörökhöz](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/sysadmin/tasks/assign-users-security-roles). 
