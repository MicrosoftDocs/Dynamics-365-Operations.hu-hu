---
title: "Talent üzembe helyezése"
description: "Ez a témakör végigvezeti Önt az új környezet létesítésén a Microsoft Dynamics 365 for Talent számára."
author: rschloma
manager: AnnBe
ms.date: 09/27/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: 17271
ms.assetid: ba1ad49d-8232-400e-b11f-525423506a3f
ms.search.region: Global
ms.author: rschloma
ms.search.validFrom: 2017-11-20
ms.dyn365.ops.version: Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: c5d4fb53939d88fcb1bd83d70bc361ed9879f298
ms.openlocfilehash: d28ca1f9cf2bef73dc687a85592056cccc767da5
ms.contentlocale: hu-hu
ms.lasthandoff: 10/01/2018

---
# <a name="provision-talent"></a>Talent üzembe helyezése

[!include [banner](includes/banner.md)]

Ez a témakör végigvezeti Önt az új termelési környezet létesítésén a Microsoft Dynamics 365 for Talent számára. Ez a témakör feltételezi, hogy a Talent rendszert felhőalapú szolgáltatón (CSP) keresztül vagy vállalati architektúra (EA) megállapodás részeként vásárolta. Ha rendelkezik már meglévő Microsoft Dynamics 365 licenccel, amely már tartalmazza a Talent szolgáltatástervet, és nem tudja elvégezni a témakörben szereplő lépéseket, forduljon a támogatási szolgálathoz.

Első lépésként a globális rendszergazdának be kell jelentkeznie a [Microsoft Dynamics Lifecycle Services](https://lcs.dynamics.com) (LCS) szolgáltatásba, és létre kell hoznia egy új Talent projektet. Hacsak licencelési probléma meg nem akadályozza a Talent létesítését, a Támogatás vagy a Dynamics Service Engineering (DSE) képviselőinek segítségére nincsen szkség.

## <a name="create-an-lcs-project"></a>LCS-projekt létrehozása
Az LCS a Talent kezelésére való használatához előbb egy LCS-projektet kell létrehozni.

1. Jelentkezzen be az [LCS](https://lcs.dynamics.com/Logon/Index)-be azzal a fiókkal, amelyet a Talentre való előfizetéshez használt.
2. Válassza ki a pluszjelet (**+**) projekt létrehozásához.
3. Válassza a **Microsoft Dynamics 365 for Talent** terméknévként és termékverzióként.
4. Válassza a **Dynamics 365 for Talent** módszert.
5. Válassza a **Létrehozása** lehetőséget.

A Talent használatának megkezdésével kapcsolatos tudnivalókhoz lásd az új projektben létrehozott **Talent** módszert. Miután elkészült a projekt létrehozása, hajtsa végre a következő eljárást a Talent környezetének létesítéséhez.

## <a name="provision-a-talent-project"></a>Talent-projekt létesítése
LCS-projekt létrehozása után a Talentet létesítheti egy környezetbe.

1. Az LCS-projektben válassza a **Talent alkalmazás kezelése** csempét.
2. A Talent létesítése mindig Microsoft PowerApps környezetbe történik PowerApps-integráció és a bővíthetőség érdekében. Olvassa el a témakör „PowerApps-környezet kiválasztása” című fejezetét a folytatás előtt. 

    > [!NOTE]
    > A meglévő környezetek megtekintéséhez vagy új környezetek létrehozásához a Talentet létesítő bérlő adminisztrátort hozzá kell rendelni a PowerApps P2 licenchez. Ha szervezete nem rendelkezik PowerApps P2 licenccel, kaphat egyet a CSP-től vagy a [PowerApps árképzési lapon](https://powerapps.microsoft.com/en-us/pricing/).

4. Válassza a **Hozzáadás** elemet, majd válassza ki a környezetet, amelybe létesíteni kívánja a Talent rendszert.
5. Válassza ki a "Demó adatokat tartalmaz" beállítást, ha azt szeretné, hogy a környezet ugyanazokat a bemutató adatokat tartalmazza, mint amelyeket a Talent tesztverziókban használtak.  Ez hosszú távú bemutató vagy képzési környezetben előnyös, de éles környezetben soha nem szabad használni.  Ne feledje, hogy a kezdeti telepítéskor ezt a beállítást kell kiválasztania, és a meglévő telepítést később már nem lehet frissíteni.
6. Válassza az **Igen** lehetőséget a feltételek elfogadásához és a telepítés megkezdéséhez.

    Az új környezet megjelenik a bal oldali navigációs panelen látható környezetek listájában. Azonban a környezet nem indítható el mindaddig, amíg a telepítés állapota nem frissül **Telepítve** értékre. Ez a folyamat jellemzően csak pár percig tart. Ha a jogosultságkezelés folyamata sikertelen, kérje az Ügyfélszolgálat segítségét.

7. Válassza a **Bejelentkezés a Talent rendszerbe** az új környezet használatához.

> [!NOTE]
> Ha még nem írta alá a végső követelményeket, a Talent tesztpéldányát telepítheti a projektben. Ezután ezt a példányt használhatja a megoldás tesztelésére mindaddig, amíg alá nem ír. Ha az új környezet teszteléshez használja, ismételje meg ezt az eljárást, hogy létrehozzon egy éles környezetet.

> [!NOTE]
> Mivel csak két LCS környezet van engedélyezve a Talent előfizetés részeként, vegye fontolóra egy ingyenes, 60 napos [Talent próba környezet igénybevételét](https://dynamics.microsoft.com/en-us/talent/overview/). Bár a próbakörnyezetek tulajdonosa az a felhasználó, aki kérte pket, más felhasználók is meghívhatók az Alapvető HR környezet rendszergazdai felületén keresztül. A próbakörnyezetek olyan kitalált adatokat tartalmaznak, amelyek segítségével biztonságosan fel lehet fedezni a programot. Nem úgy tervezték, hogy termelési környezetekben használják őket. Kérjük, vegye figyelembe, hogy amikor a próbakörnyezet 60 nap elteltével lejár, a benne lévő minden adat törlődik, és azok nem is állíthatók helyre. Regisztrálhat egy új próbakörnyezetre, miután lejárt a meglévő környezet.

## <a name="select-a-powerapps-environment"></a>Válasszon PowerApps környezetet

A Talent és PowerApps környezetek közötti integrációval integrálhatja és kiterjesztheti a Talent-adatok használatát a PowerApps-eszközökkel. A PowerApps környezetek céljának megértése nem csak a Talent kiterjesztésére szolgáló alkalmazások felépítésében segít, hanem a helyes környezet kiválasztásában is a Talent létesítésekor. Információ a PowerApps-környezetekről, beleértve a környezeti hatásköröket, a környezethez való hozzáférést, valamint a környezet létrehozását és kiválasztását: [PowerApps-környezetek bejelentése](https://powerapps.microsoft.com/en-us/blog/powerapps-environments/). 

Kövesse az alábbi útmutatást, amikor azt állapítja meg, hogy mely PowerApps környezetbe kell telepíteni a Talent alkalmazást: 
1. Az LCS-ben válassza a Környezetek kezelése lehetőséget, vagy lépjen közvetlenül a PowerApps adminisztrációs központjába, ahol megtekintheti a meglévő környezeteket és új környezeteket hozhat létre.
2. Egyetlen Talent-környezet van egyetlen PowerApps-környezethez rendelve.
3. A PowerApps környezet „tartalmazza” a Talent alkalmazást a megfelelő PowerApps, Flow és CDS alkalmazásokkal együtt. Ha a PowerApps környezetet törlik, törlődnek a benne lévő alkalmazások is.
4. Az adatintegrációs és tesztelési stratégiákat figyelembe kell venni, például: védőfal, UAT, termelés. Ezért javasoljuk, hogy vegye figyelembe a telepítés különböző következményeit, mert nem könnyű a későbbiekben megváltoztatni a PowerApps-környezethez leképzett Talent környezetet.
5. A következő PowerApps környezetek a Talent esetében nem használhatók, és ki lesznek szűrve a kiválasztási listából a LCS portálon belül:
 
   **Alapértelmezett PowerApps környezetek** Bár minden bérlő számára automatikusan megtörténik az alapértelmezett PowerApps környezet létesítése, nem javasoljuk velük a Talent használatát, hiszen minden bérlő felhasználónak hozzáférése van a PowerApps környezethez, és a PowerApps vagy Flow integrációk tesztelése és feltérképezése során véletlenül kárt tehetnek termelési adatokban.
   
   <strong>Tesztkörnyezetek</strong> A „TestDrive – alias@domain” névvel rendelkező környezetek 60 napos lejárati idővel kerülnek létrehozásra, és ezután lejárnak, ami automatikusan eltávolítja a környezetet.
   
   **Nem támogatott régiók** Jelenleg a Talent csak az alábbi területeken támogatott: Egyesült Államok, Európa és Ausztrália.
  
6. Nincs konkrét végrehajtandó művelet, miután megadta a helyes használandó környezetet. Folytassa a létesítési folyamatot. 
 
## <a name="grant-access-to-the-environment"></a>Hozzáférés biztosítása a környezethez
Alapértelmezés szerint a környezetet csak az a globális rendszergazda érheti el, aki létrehozta. Az alkalmazás további felhasználóinak azonban kifejezett módon engedélyezni kell a hozzáférést. Ha hozzáférést szeretne adni, [fel kell vennie a felhasználókat](https://docs.microsoft.com/en-us/dynamics365/unified-operations/dev-itpro/sysadmin/tasks/create-new-users), és [hozzájuk kell rendelnie a megfelelő szerepköröket](https://docs.microsoft.com/en-us/dynamics365/unified-operations/dev-itpro/sysadmin/tasks/assign-users-security-roles) az Alapvető HR környezetben. A Talent-et telepítő globális rendszergazdának el kell elindítania az Attract és az Onboard alkalmazást is ahhoz, hogy befejezze az inicializálást és engedélyezze a hozzáférést más bérlő felhasználók számára is.  Amíg erre nem kerül sor, más felhasználók nem tudják elérni az Attract és Onboard alkalmazást, és hozzáférési hibákra vonatkozó üzeneteket fognak kapni.


