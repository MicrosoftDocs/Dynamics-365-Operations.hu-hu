---
title: "A Microsoft Dynamics 365 for Talent létesítése"
description: "Ez a témakör végigvezeti Önt az új környezet létesítésén a Microsoft Dynamics 365 for Talent számára."
author: rschloma
manager: AnnBe
ms.date: 11/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Talent
ms.custom: 17271
ms.assetid: ba1ad49d-8232-400e-b11f-525423506a3f
ms.search.region: Global
ms.author: rschloma
ms.search.validFrom: 2017-11-20
ms.dyn365.ops.version: Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: b4b54e97bdebc158adc3bc6d57a6661cd536f5fb
ms.contentlocale: hu-hu
ms.lasthandoff: 04/13/2018

---
# <a name="provision-microsoft-dynamics-365-for-talent"></a>A Microsoft Dynamics 365 for Talent létesítése

[!INCLUDE [banner](includes/banner.md)]

Ez a témakör végigvezeti Önt az új termelési környezet létesítésén a Microsoft Dynamics 365 for Talent számára. Ez a témakör feltételezi, hogy a Talent rendszert felhőalapú szolgáltatón (CSP) keresztül vagy vállalati architektúra (EA) megállapodás részeként vásárolta. Ha rendelkezik már meglévő Microsoft Dynamics 365 licenccel, amely már tartalmazza a Talent szolgáltatástervet, és nem tudja elvégezni a témakörben szereplő lépéseket, forduljon a támogatási szolgálathoz.

Első lépésként a globális rendszergazdának be kell jelentkeznie a [Microsoft Dynamics Lifecycle Services](http://lcs.dynamics.com) (LCS) szolgáltatásba, és létre kell hoznia egy új Talent projektet. Hacsak licencelési probléma meg nem akadályozza a Talent létesítését, a Támogatás vagy a Dynamics Service Engineering (DSE) képviselőinek segítségére nincsen szkség.

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
3. Ha még nem rendelkezik PowerApps környezettel, kövesse a jelen témakör "Új PowerApps-környezet létrehozása (ha szükséges)" szakaszának lépéseit a folytatás előtt.

    > [!NOTE]
    > A meglévő környezetek megtekintéséhez vagy új környezetek létrehozásához a Talentet létesítő bérlő adminisztrátort hozzá kell rendelni a PowerApps P2 licenchez. Ha szervezete nem rendelkezik PowerApps P2 licenccel, kaphat egyet a CSP-től vagy a [PowerApps árképzési lapon](https://powerapps.microsoft.com/en-us/pricing/).

4. Válassza a **Hozzáadás** elemet, majd válassza ki a környezetet, amelybe létesíteni kívánja a Talent rendszert.
5. Válassza az **Igen** lehetőséget a feltételek elfogadásához és a telepítés megkezdéséhez.

    Az új környezet megjelenik a bal oldali navigációs panelen látható környezetek listájában. Azonban a környezet nem indítható el mindaddig, amíg a telepítés állapota nem frissül **Telepítve** értékre. Ez a folyamat jellemzően csak pár percig tart. Ha a jogosultságkezelés folyamata sikertelen, kérje az Ügyfélszolgálat segítségét.

6. Válassza a **Bejelentkezés a Talent rendszerbe** az új környezet használatához.

> [!NOTE]
> Ha még nem írta alá a végső követelményeket, a Talent tesztpéldányát telepítheti a projektben. Ezután ezt a példányt használhatja a megoldás tesztelésére mindaddig, amíg alá nem ír. Ha az új környezet teszteléshez használja, ismételje meg ezt az eljárást, hogy létrehozzon egy éles környezetet.

> [!NOTE]
> Az LCS-n keresztül alkalmazott Talent-környezetek nem tartalmaznak olyan demóadatokat, amelyeknek a konfigurálása HR-feladatokra történ volna, illetve amelyek a Talent-környezetre lennének specifikusak. Ha olyan környezetet szeretne, amely demóadatokat is tartalmaz, akkor javasoljuk, hogy regisztráljon egy 60 napos [Talent-próbakörnyezetre](https://dynamics.microsoft.com/en-us/talent/overview/). Bár a próbakörnyezetek tulajdonosa az a felhasználó, aki kérte pket, más felhasználók is meghívhatók az Alapvető HR környezet rendszergazdai felületén keresztül. A próbakörnyezetek olyan kitalált adatokat tartalmaznak, amelyek segítségével biztonságosan fel lehet fedezni a programot. Nem úgy tervezték, hogy termelési környezetekben használják őket. Kérjük, vegye figyelembe, hogy amikor a próbakörnyezet 60 nap elteltével lejár, a benne lévő összes adat törlődik, és azok nem is állíthatók helyre. Regisztrálhat egy új próbakörnyezetre, miután lejárt a meglévő környezet.

## <a name="select-a-powerapps-environment"></a>Válasszon PowerApps környezetet

A Talent és PowerApps környezetek közötti integrációval integrálhatja és kiterjesztheti a Talent-adatok használatát a PowerApps-eszközökkel. A PowerApps környezetek céljának megértése nem csak a Talent kiterjesztésére szolgáló alkalmazások felépítésében segít, hanem a helyes környezet kiválasztásában is a Talent létesítésekor. Információ a PowerApps-környezetekről, beleértve a környezeti hatásköröket, a környezethez való hozzáférést, valamint a környezet létrehozását és kiválasztását: [PowerApps-környezetek bejelentése](https://powerapps.microsoft.com/en-us/blog/powerapps-environments/). 

Kövesse az alábbi útmutatást, amikor azt állapítja meg, hogy mely PowerApps környezetbe kell telepíteni a Talent alkalmazást: 
1. Az LCS-ben válassza a Környezetek kezelése lehetőséget, vagy lépjen közvetlenül a PowerApps adminisztrációs központjába, ahol megtekintheti a meglévő környezeteket és új környezeteket hozhat létre.
2. Egyetlen Talent-környezet van egyetlen PowerApps-környezethez rendelve.
3. A PowerApps környezet „tartalmazza” a Talent alkalmazást a megfelelő PowerApps, Flow és CDS alkalmazásokkal együtt. Ha a PowerApps környezetet törlik, törlődnek a benne lévő alkalmazások is.
4. Az adatintegrációs és tesztelési stratégiákat figyelembe kell venni, például: védőfal, UAT, termelés. Ezért javasoljuk, hogy vegye figyelembe a telepítés különböző következményeit, mert nem könnyű a későbbiekben megváltoztatni a PowerApps-környezethez leképzett Talent környezetet.
5. A következő PowerApps környezetek a Talent esetében nem használhatók, és ki lesznek szűrve a kiválasztási listából a LCS portálon belül:
 
    **CD 2.0 környezetek:** A CDS 2.0-t 2018. március 21-én jelenik meg; azonban a Talent még nem támogatja a CDS 2.0-at. Bár megtekinthet és létrehozhat CD 2.0 adatbázisokat a PowerApps Admin központban, ezek nem lesznek használhatók a Talent alkalmazásban. A CDS 2.0 környezetek használatának lehetősége a Talent telepítésekben egy későbbi időpontban lesz elérhető.
   
   > [!Note]
   > A CDS 1.0 és 2.0 környezetek megkülönböztetésére a felügyeleti portálon, jelöljön ki egy környezetet, és nézze meg a **Részletek** elemet. Az összes CD 2.0-s környezetben szerepel az „Ezeket a beállításokat a Dynamics 365 felügyeleti központban kezelheti” tájékoztatás, hivatkozás egy példányverzióra, és nincs Adatbázis lap. 
 
   **Alapértelmezett PowerApps környezetek** Bár minden bérlő számára automatikusan megtörténik az alapértelmezett PowerApps környezet létesítése, nem javasoljuk velük a Talent használatát, hiszen minden bérlő felhasználónak hozzáférése van a PowerApps környezethez, és a PowerApps vagy Flow integrációk tesztelése és feltérképezése során véletlenül kárt tehetnek termelési adatokban.
   
   <strong>Tesztkörnyezetek</strong> A „TestDrive – alias@domain” névvel rendelkező környezetek 60 napos lejárati idővel kerülnek létrehozásra, és ezután lejárnak, ami automatikusan eltávolítja a környezetet.
   
   **Nem támogatott régiók** Jelenleg a Talent csak az alábbi területeken támogatott: Egyesült Államok, Európa és Ausztrália.
  
6. Nincs konkrét végrehajtandó művelet, miután megadta a helyes használandó környezetet. Folytassa a létesítési folyamatot. 
 
## <a name="create-a-new-powerapps-environment-if-required"></a>Új PowerApps-környezet létrehozása (ha szükséges)

Futtasson PowerShell-parancsfájlt, hogy új PowerApps környezetet hozzon létre a Talent számára a PowerApps Plan 2 licenccel rendelkező bérlő adminisztrátorával összefüggésben. A parancsfájl automatizálja az alábbi lépéseket:


 + PowerApps-környezet létrehozása
 + CD 1.0 adatbázis létrehozása
 + Törölje az összes mintaadatot a CDS 1.0 adatbázisban


Hajtsa végre az alábbi utasításokat a parancsfájl futtatásához:

1. Töltse le a ProvisionCDSEnvironment.zip fájlt a következő helyről: [ProvisionCDSEnvironment-parancsfájlok](https://go.microsoft.com/fwlink/?linkid=870436)  

2. Bontsa ki a ProvisionCDSEnviroinment.zip fájl teljes tartalmát egy mappába.

3. Futtassa a Windows PowerShell vagy a Windows PowerShell ISE programot rendszergazdaként.

   Keresse fel a [Végrehajtási házirend beállítása](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.security/set-executionpolicy?view=powershell-6) témakört, amelyben bővebben olvashat a végrehajtási házirend beállításáról úgy, hogy futhassanak parancsfájlok.
  
4. A PowerShell alkalmazáson belül keresse meg azt a mappát, ahová kicsomagolta a fájlokat, és futtassa a következő parancsot, az értékek cseréjével az alábbiak szerint:
 
   ```.\ProvisionCDSEnvironment -EnvironmentName MyNewEnvironment -Location YourLocation```

    
   **MyNewEnvironment**-et le kell cserélni a környezet nevére. Ez a név az LCS portálon fog megjelenni, és akkor lesz látható, amikor a felhasználók kiválasztják a használandó Talent-környezetet. 

   **YourLocation** helyettesíteni kell a Talent egyik támogatott régiójával: unitedsates, europe, australia. 

   **– Részletes:** opcionális, és részletes információt biztosít, amely elküldhető a támogatásnak problémák esetén.

5. Folytassa a létesítési folyamatot.
 


## <a name="grant-access-to-the-environment"></a>Hozzáférés biztosítása a környezethez
Alapértelmezés szerint a környezetet csak az a globális rendszergazda érheti el, aki létrehozta. Az alkalmazás további felhasználóinak azonban kifejezett módon engedélyezni kell a hozzáférést. Ha hozzáférést szeretne adni, [fel kell vennie a felhasználókat](../dev-itpro/sysadmin/tasks/create-new-users.md), és [hozzájuk kell rendelnie a megfelelő szerepköröket](../dev-itpro/sysadmin/tasks/assign-users-security-roles.md) az Alapvető HR környezetben. emellett hozzá kell adni ezeket a felhasználókat a PowerApps-környezethez, hogy hozzáférhessenek az Attract és az Onboard alkalmazásokhoz. Az eljárás részletei itt láthatók. Ha segítségre van szüksége a következő lépésekkel kapcsolatban, olvassa el [A PowerApps adminisztrációs központjának bemutatása](https://powerapps.microsoft.com/en-us/blog/introducing-admin-center-for-powerapps/) című blogbejegyzést.

Ezt az eljárást az a globális rendszergazda hajtja végre, aki a Talent környezetet telepítette.

1. Nyissa meg a [PowerApps adminisztrációs központját](https://preview.admin.powerapps.com/environments).
2. Jelölje be a megfelelő környezeteket.
3. A **Biztonság** lapon adja hozzá a szükséges felhasználókat a **Környezetkészítő** szerepkörhöz.

    Ne feledje, hogy a felhasználók a PowerApps környezethez történő manuális hozzáadásának ezen utolsó lépése ideiglenes. Végül automatikusan fog végbemenni, amikor megtörténik a felhasználók hozzáadása az Alapvető HR környezetben.

