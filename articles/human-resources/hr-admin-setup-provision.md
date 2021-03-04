---
title: Emberi erőforrások létesítése
description: Ez a cikk végigvezeti Önt az új termelési környezet létesítésén a Microsoft Dynamics 365 Human Resources számára.
author: andreabichsel
manager: AnnBe
ms.date: 04/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 106976edfa2bd7efba41887d5e8f4243b56e7b2f
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/17/2020
ms.locfileid: "4527792"
---
# <a name="provision-human-resources"></a>Emberi erőforrások létesítése

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

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

2. Azt jelzi, hogy ez a környezet a Human Resources tesztkörnyezete-e vagy a termelési példánya. A korai előzetes funkciók elérhetők lehetnek a Védőfalpéldányokban, a korai visszajelzések és tesztelés érdekében.
   
    > [!NOTE]
    > A Human Resources példány típusát a beállítás után nem lehet módosítani. Folytatás előtt győződjön meg arról, hogy a helyes példánytípus van kiválasztva.</br></br>
    > A Human Resources példánytípus eltér a Microsoft Power Apps környezet Power Apps Felügyeleti központjában beállítható példánytípusától.
    
3. Válassza ki a **Demó adatokat tartalmaz** beállítást, ha azt szeretné, hogy a környezet ugyanazokat a demóadatokat tartalmazza, mint amelyeket a Human Resources tesztverzióiban használt. A bemutatóadat hosszú távú bemutató vagy képzési környezetben előnyös, de éles környezetben soha nem szabad használni. Az első telepítés esetén kell ezt a lehetőséget kiválasztania. Meglévő telepítés később nem frissíthető.

4. A Human Resources szolgáltatást mindig Microsoft Power Apps környezetbe kell létesíteni annak érdekében, hogy biztosítsa a Power Apps integrációját és bővíthetőségét. Olvassa el a témakör „Power Apps környezet kiválasztása” című cikkét a folytatás előtt. Ha még nem rendelkezik Power Apps környezettel, válassza a Környezetek kezelése LCS-ben lehetőséget, vagy látogasson el a Power Apps adminisztrációs központjába. Kövesse a [Power Apps környezet](https://docs.microsoft.com/powerapps/administrator/create-environment) létrehozása részben leírt lépéseket.

5. Válassza ki azt a környezetet, amelybe létesíteni szeretné a Human Resources szolgáltatást.

6. Válassza az **Igen** lehetőséget a feltételek elfogadásához és a telepítés megkezdéséhez.

   Az új környezet megjelenik a bal oldali navigációs panelen látható környezetek listájában. Azonban a környezet nem indítható el mindaddig, amíg a telepítés állapota nem frissül **Telepítve** értékre. Ez a folyamat jellemzően csak pár percig tart. Ha a jogosultságkezelés folyamata sikertelen, kérje az Ügyfélszolgálat segítségét.

7. Válassza a **Bejelentkezés a Human Resources szolgáltatásba** lehetőséget az új környezet használatához.

    > [!NOTE]
    > Ha még nem hagyta jóvá a végső követelményeket, a Human Resources tesztpéldányát telepítheti a projektben. Ezután ezt a példányt használhatja a megoldás tesztelésére mindaddig, amíg alá nem ír. Ha az új környezet teszteléshez használja, ismételje meg ezt az eljárást, hogy létrehozzon egy éles környezetet.

    > Érdemes lehet kihasználni a 60 napos ingyenes [Human Resources próbakörnyezetet](https://go.microsoft.com/fwlink/p/?LinkId=2115962). Bár a próbakörnyezetek tulajdonosa az a felhasználó, aki kérte pket, más felhasználók is meghívhatók a Human Resources környezet rendszergazdai felületén keresztül. A próbakörnyezetek olyan kitalált adatokat tartalmaznak, amelyek segítségével biztonságosan fel lehet fedezni a programot. Nem úgy tervezték, hogy termelési környezetekben használják őket. Kérjük, vegye figyelembe, hogy amikor a próbakörnyezet 60 nap elteltével lejár, a benne lévő minden adat törlődik, és azok nem is állíthatók helyre. Regisztrálhat egy új próbakörnyezetre, miután lejárt a meglévő környezet.

## <a name="select-a-power-apps-environment"></a>Power Apps-környezet kiválasztása

Az Human Resources adatainak használatát a Power Apps eszközökkel integrálhatja és bővítheti. Információ a Power Apps-környezetekről, beleértve a környezeti hatásköröket, a környezethez való hozzáférést, valamint a környezet létrehozását és kiválasztását: [Power Apps-környezetek bejelentése](https://powerapps.microsoft.com/blog/powerapps-environments/). 

Kövesse az alábbi útmutatást, amikor azt állapítja meg, hogy melyik Power Apps környezetbe kell telepíteni a Human Resources szolgáltatást: 

1. Válassza a **Környezetek kezelése** lehetőséget az LCS-ben. Közvetlenül a Power Apps felügyeleti központ oldalra is léphet, ahol megtekintheti a meglévő környezeteket, és új környezeteket hozhat létre.

2. Egyetlen Human Resources környezet van egyetlen Power Apps környezethez rendelve.

3. A Power Apps környezet tartalmazza a Human Resources szolgáltatást a megfelelő Power Apps, Power Automate és Common Data Service alkalmazásokkal együtt. Ha a Power Apps környezetet törlik, törlődnek a benne lévő alkalmazások is. Human Resources környezet létesítésekor **Próba** vagy **Termelési** környezetek létesíthetők. Válassza ki a környezet típusát a környezet későbbi használata alapján. 

4. Az adatintegrációs és tesztelési stratégiákat figyelembe kell venni, például: védőfal, UAT vagy termelés. Javasoljuk, hogy vegye figyelembe a telepítés különböző következményeit, mert nem könnyű a későbbiekben megváltoztatni a Power Apps környezethez hozzárendelt Human Resources környezetet.

5. A következő Power Apps-környezetek nem használhatók a Human Resources szolgáltatáshoz. Ezeket a rendszer az LCS-en belül kiszűri a kiválasztások listájából:
 
    - **Alapértelmezett Power Apps-környezetek** – noha a bérlők automatikusan egy alapértelmezett Power Apps-környezettel rendelkeznek, nem ajánlott ezeket használni a Human Resources szolgáltatással. A bérlő minden felhasználója hozzáférhet a Power Apps-környezethez, és véletlenül a termelési adatok sérülését okozhatja a Power Apps vagy Power Automate-integrációkkal történő tesztelés és felfedezés révén.
   
    - **Próbakörnyezetek** – ezek a környezetek lejárati dátummal jönnek létre. A lejárat után a program automatikusan eltávolítja az Ön környezetét és a benne található összes Human Resources-példányt.
   
    - **Nem támogatott régiók** – Jelenleg a Human Resources csak a következő régiókban támogatott: Egyesült Államok, Európa, Egyesült Királyság, Ausztrália, Kanada és Ázsia.

    > [!NOTE]
    > A Human Resources környezetet ugyanabban a régióban kell létesíteni, amelyben a Power Apps környezet létesítése történt. A Human Resources környezet egy másik régióba történő áttelepítése nem támogatott.

6. Miután meghatározta a használandó a helyes környezetet, folytathatja a létesítési folyamat. 
 
## <a name="grant-access-to-the-environment"></a>Hozzáférés biztosítása a környezethez

Alapértelmezés szerint a környezetet csak az a globális rendszergazda érheti el, aki létrehozta. Az alkalmazás további felhasználóinak kifejezett módon engedélyezni kell a hozzáférést. Fel kell vennie a felhasználókat, és hozzájuk kell rendelnie a megfelelő szerepköröket a Human Resources környezetben. A Human Resources szolgáltatást telepítő globális rendszergazdának el kell indítania az Attract és az Onboard alkalmazást is ahhoz, hogy befejezze az inicializálást, és engedélyezze a hozzáférést más bérlő felhasználók számára is. Amíg erre nem kerül sor, más felhasználók nem tudják elérni az Attract és Onboard alkalmazást, és hozzáférési hibákra vonatkozó üzeneteket fognak kapni. További tudnivalókért lásd: [Új felhasználók létrehozása](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/sysadmin/tasks/create-new-users) és [Felhasználók hozzárendelése biztonsági szerepkörökhöz](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/sysadmin/tasks/assign-users-security-roles). 


[!INCLUDE[footer-include](../includes/footer-banner.md)]