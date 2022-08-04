---
title: A Human Resources kiépítése
description: Ez a cikk bemutatja egy új termelési környezet létesítését a Microsoft számára Dynamics 365 Human Resources.
author: twheeloc
ms.date: 01/07/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 6fc44b52e2f7662fc6be609562cec903a8755d1b
ms.sourcegitcommit: 1401d66b6b64c590ca1f8f339d622e922920cf15
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/20/2022
ms.locfileid: "9178503"
---
# <a name="provision-human-resources"></a>A Human Resources kiépítése

_**Érvényes:** Emberi erőforrások a különálló infrastruktúrán_ 

> [!NOTE]
> 2022 június elején az Emberi erőforrások környezeteket csak a pénzügyek és műveletek alkalmazás-infrastruktúráira lehet telepíteni. A további tudnivalókat lásd [az Emberi erőforrások biztosítása a pénzügyi és a műveleti infrastruktúra területén](hr-admin-setup-provision-fo.md).

Ez a cikk bemutatja egy új termelési környezet létesítését a Microsoft számára Dynamics 365 Human Resources. 

## <a name="prerequisites"></a>Előfeltételek

Mielőtt elkezdené egy új termelési környezet biztosítását, a következő előfeltételeknek kell teljesülniük:

- Ön a humánerőforrás-szolgáltatást felhőalapú megoldásszolgáltatói (CSP) vagy vállalati architektúra (EA) megállapodáson keresztül vásárolta meg. Ha rendelkezik meglévő Microsoft Dynamics 365-licenccel, amely már tartalmazza a Human Resources szolgáltatási konstrukciót, és nem tudja elvégezni a cikkben szereplő lépéseket, forduljon a támogatási szolgálathoz.

- A globális rendszergazda bejelentkezett a [Microsoft Dynamics Lifecycle Services](https://lcs.dynamics.com) (LCS) szolgáltatásba, és létrehozott egy új humánerőforrás-projektet. 

## <a name="provision-a-human-resources-trial-environment"></a>Az Emberi erőforrások próbakörnyezetének kiépítése

>[!NOTE]
> 2022. április elején az Emberi erőforrások próbakörnyezete nem lesz elérhető a különálló alkalmazásban. A pénzügyi és műveletalkalmazásokban az emberi erőforrásokkal kapcsolatos képességek értékelése iránt érdeklődő potenciális vevők ezt az ingyenes 30 napos próbaidőszak segítségével, a bemutató adataival együtt megtenni. A Dynamics 365 Pénzügy az emberi erőforrások azon képességeit fogja tartalmazni, amelyek a pénzügyi infrastruktúra számára a különálló alkalmazás egyesítése révén biztosítanak majd szolgáltatásokat. A további tudnivalókat lásd az EMBERI-szolgáltatások [egyesítése és a vevőknek nyújtott képességek egyesítésével kapcsolatban](https://cloudblogs.microsoft.com/dynamics365/it/2021/09/15/merging-of-hr-offerings-brings-capabilities-together-for-customers). A Dynamics 365 Pénzügy teszteléssel kapcsolatos további tudnivalókat lásd a lépésenként [útmutatóban](../fin-ops-core/fin-ops/get-started/before-you-buy.md). 


Az első üzenetkészlet vagy termelési környezet létesítása előtt szükség lehet egy Emberi erőforrások próbakörnyezet építésére, hogy érvényes legyen az [Emberi erőforrások próbakörnyezet](https://go.microsoft.com/fwlink/p/?LinkId=2115962) Emberi erőforrások szolgáltatás. A próbakörnyezetek olyan kitalált adatokat tartalmaznak, amelyek segítségével biztonságosan fel lehet fedezni a programot. Bár a próbakörnyezetek tulajdonosa az a felhasználó, aki kérte pket, más felhasználók is meghívhatók a Human Resources környezet rendszergazdai felületén keresztül. 

A próbakörnyezetekkel lehet kiértékelni az emberi erőforrásokkal kapcsolatban szükséges funkciókat az olyan személyek esetében, akik még nem férnek hozzá az Emberi erőforrások környezethez. Ha próbakörnyezetet létesít, és a hitelesített felhasználónak már van hozzáférése egy vagy több meglévő Human Resources környezethez, a rendszer átirányítja a felhasználót a meglévő környezetre vagy a környezetek listájára.

A próbaverzió környezetet nem úgy tervezték, hogy termelési környezetekben használják őket. Csak a 30 napos próbaidőszakra korlátozódnak. Amikor lejár a próbaidőszak, törlődik a környezet és az benne bennelévő összes adat, és nem állítható helyre. A környezet nem konvertálhatóboxvá vagy termelési környezetké. Regisztrálhat egy új próbakörnyezetre, miután lejárt a meglévő környezet.

Az Emberi erőforrások próbakörnyezet létrehozásakor a bérlőn egy Power Apps próbakörnyezet is létrejön, és kapcsolódik a Emberi erőforrások környezethez. A "TestDrive" nevű Power Apps környezetben ugyanaz a próbaidőszak, mint az Emberi erőforrások környezetben.

> [!NOTE]
> Az Emberi erőforrások próbakörnyezet kiépítése sikertelen lesz, ha a hitelesített felhasználónak nincs engedélye a Power Apps próbakörnyezetek létrehozására. A felhasználónak szerepelnie kell abban a felhasználói csoportban, amely próbakörnyezetet hozhat létre a Power Platform felügyeleti központban. A további tudnivalókat lásd: [Annak szabályozása, hogy ki hozhat létre és kezelhet környezeteket a Power Platform felügyeleti központban](/power-platform/admin/control-environment-creation).

## <a name="plan-human-resources-environments"></a>A Human Resources-környezetek megtervezése

Az első Human Resources-környezet létrehozása előtt gondosan tervezze meg a projekt környezeti szükségleteit. A Human Resources alap-előfizetése két környezetet foglal magában: egy éles környezetet és egy tesztkörnyezetet. A projekt összetettségétől függően előfordulhat, hogy a projekttevékenységek támogatásához további üzenetkészlet-környezeteket kell megvásárolni. 

További környezetekre vonatkozó megfontolások:

- **Adatáttelepítés**: adatáttelepítési tevékenységek, amelyek lehetővé teszik, hogy a beérkezett üzenetek környezetét tesztelési célokra használják a projektben. A további környezetek lehetővé teszik az adatáttelepítési tevékenységek folytatását úgy, hogy a tesztelés és a konfigurálás ezzel egyidejűleg egy másik környezetben történik.
- **Integráció**: konfigurálja és tesztelje az integrációkat, amelyekbe beletartozhat a natív integráció, például a Ceridian Dayforce vagy az egyéni integráció.
- **Képzés**: Lehet, hogy egy olyan külön környezetre van szükség, amely a képzési adatok készletével van beállítva, hogy az alkalmazottakat az új rendszer használatára képezni tudja. 
- **Többfáziss projekt**: A projekt kezdeti indulása után tervezett projektfázis konfigurációjának, adatáttelepítésének, tesztelésének és egyéb tevékenységeinek támogatása.

 > [!IMPORTANT]
 > Környezetének átgondolása során a következőket javasoljuk:
 > - Használja a gyártási környezetet a projekt során GOLD konfigurációs környezetként. Ez azért fontos, mert a tesztkörnyezetet nem lehet éles környezetbe másolni. Éppen ezért éles környezetben az ARANY környezet az éles környezet, és az ilyen környezetben fogja elvégezni az átállási tevékenységeket.</br></br>
 > - Használja a homokozót vagy egy másik környezetet egy próbaváltás elvégzésére az üzembe helyezés előtt. Ezt úgy teheti meg, hogy frissíti az ARANY konfigurációval rendelkező éles környezetet a tesztkörnyezetbe.</br></br>
 > - Készítsen részletes átadási ellenőrző listát, amely tartalmazza a végleges adatoknak a termelési környezetbe történő átviteléhez szükséges adatcsomagokat az éles átállás során.</br></br>
 > - Használja a tesztkörnyezetét a projekt során TESZT-környezetként. Ha további környezetekre van szükség, a szervezet további költségért meg tudja vásárolni őket.</br></br>

## <a name="create-an-lcs-project"></a>LCS-projekt létrehozása

Az LCS-nek a Human Resources kezelésére való használatához előbb egy LCS-projektet kell létrehozni.

1. Jelentkezzen be az [LCS](https://lcs.dynamics.com/Logon/Index)-be azzal a fiókkal, amelyet a Human Resources szolgáltatásra való feliratkozáshoz használt.

   > [!NOTE]
   > A sikeres üzembe helyezés érdekében az Emberi erőforrások környezet építéséhez használt fiókot hozzá kell rendelni vagy a **Rendszergazda** vagy a **Rendszer testre szabó** szerepkörhöz, amely az Emberi erőforrások Power Apps környezethez hozzá van rendelve. A biztonsági szerepköröknek a Power Platform rendszerben a felhasználókhoz való hozzárendeléséről további információkat a következő témakörben talál: [Felhasználói biztonság konfigurálása az erőforrásokhoz](/power-platform/admin/database-security).

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
    > Az Emberi erőforrások példánytípus nem módosítható egyszer beállítva. Folytatás előtt győződjön meg arról, hogy a helyes példánytípus van kiválasztva.</br></br>
    > A Human Resources példánytípus eltér a Microsoft Power Apps környezet Power Apps Felügyeleti központjában beállítható példánytípusától.
    
3. Válassza a **Demó adatok felvétele** opciót, ha azt szeretné, hogy a környezet tartalmazza ugyanazt a demó adathalmazt, amelyet a humánerőforrás kísérleti környezetben használnak. A bemutatóadat hosszú távú bemutató vagy képzési környezetben előnyös, de éles környezetben soha nem szabad használni. Az első telepítés esetén kell ezt a lehetőséget kiválasztania. Meglévő telepítés később nem frissíthető.

4. A Human Resources szolgáltatást mindig Microsoft Power Apps környezetbe kell létesíteni annak érdekében, hogy biztosítsa a Power Apps integrációját és bővíthetőségét. Olvassa el a témakör „Power Apps környezet kiválasztása” című cikkét a folytatás előtt. Ha még nem rendelkezik Power Apps környezettel, válassza a Környezetek kezelése LCS-ben lehetőséget, vagy látogasson el a Power Apps adminisztrációs központjába. Kövesse a [Power Apps környezet](/powerapps/administrator/create-environment) létrehozása részben leírt lépéseket.

5. Válassza ki azt a környezetet, amelybe létesíteni szeretné a Human Resources szolgáltatást.

6. Válassza az **Igen** lehetőséget a feltételek elfogadásához és a telepítés megkezdéséhez.

   Az új környezet megjelenik a bal oldali navigációs panelen látható környezetek listájában. Nem elindíthatja azonban a **környezetet addig, amíg a telepítés nincs telepítve**. Ez a folyamat jellemzően csak pár percig tart. Ha a létesítés folyamata sikertelen, forduljon a támogatási szolgálathoz.

7. Válassza a **Bejelentkezés a Human Resources szolgáltatásba** lehetőséget az új környezet használatához.

    > [!NOTE]
    > Ha még nem hagyta jóvá a végső követelményeket, a Human Resources tesztpéldányát telepítheti a projektben. Ezután ezt a példányt használhatja a megoldás tesztelésére mindaddig, amíg alá nem ír. Ha az új környezet teszteléshez használja, ismételje meg ezt az eljárást, hogy létrehozzon egy éles környezetet.

## <a name="select-a-power-apps-environment"></a>Power Apps-környezet kiválasztása

Az Human Resources adatainak használatát a Power Apps eszközökkel integrálhatja és bővítheti. Információ a Power Apps-környezetekről, beleértve a környezeti hatásköröket, a környezethez való hozzáférést, valamint a környezet létrehozását és kiválasztását: [Power Apps-környezetek bejelentése](https://powerapps.microsoft.com/blog/powerapps-environments/). 

Kövesse az alábbi útmutatást, amikor azt állapítja meg, hogy melyik Power Apps környezetbe kell telepíteni a Human Resources szolgáltatást: 

1. Válassza a **Környezetek kezelése** lehetőséget az LCS-ben. Közvetlenül a Power Apps felügyeleti központ oldalra is léphet, ahol megtekintheti a meglévő környezeteket, és új környezeteket hozhat létre.

2. Egyetlen Human Resources környezet van egyetlen Power Apps környezethez rendelve.

3. A Power Apps környezet tartalmazza a Human Resources szolgáltatást a megfelelő Power Apps, Power Automate és Dataverse alkalmazásokkal együtt. Ha a Power Apps környezetet törlik, törlődnek a benne lévő alkalmazások is. Human Resources környezet létesítésekor **Próba** vagy **Termelési** környezetek létesíthetők. Válassza ki a környezet típusát a környezet későbbi használata alapján. 

4. Az adatintegrációs és tesztelési stratégiákat figyelembe kell venni, például: védőfal, UAT vagy termelés. Javasoljuk, hogy vegye figyelembe a telepítés különböző következményeit, mert nem könnyű a későbbiekben megváltoztatni a Power Apps környezethez hozzárendelt Human Resources környezetet.

5. A következő Power Apps környezetek nem használhatók a humánerőforráshoz. Ezeket a rendszer az LCS-en belül kiszűri a kiválasztások listájából:
 
    - **Alapértelmezett Power Apps-környezetek** – noha a bérlők automatikusan egy alapértelmezett Power Apps-környezettel rendelkeznek, nem ajánlott ezeket használni a Human Resources szolgáltatással. A bérlő minden felhasználója hozzáférhet a Power Apps-környezethez, és véletlenül a termelési adatok sérülését okozhatja a Power Apps vagy Power Automate-integrációkkal történő tesztelés és felfedezés révén.
   
    - **Próbakörnyezetek** – ezek a környezetek lejárati dátummal jönnek létre. A lejárat után a program automatikusan eltávolítja az Ön környezetét és a benne található összes Human Resources-példányt.
   
    - **Nem támogatott földrajzi területek** - A környezetnek támogatott földrajzi területnek kell lennie. A további tudnivalókat lásd: [Támogatott földrajzi területek](hr-admin-setup-provision.md#supported-geographies).

6. A Human Resources és a Power Apps környezet integrálásához használható kettős írási képességek csak akkor használhatók, ha a **Dynamics 365 alkalmazások engedélyezése** beállítás van kiválasztva a környezetben. A további tudnivalókat lásd [a Kétírásos honlapon](../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-home-page.md).

    > [!NOTE]
    > A Power Apps környezet létrehozásakor ki kell választani a **Dynamics 365-alkalmazások engedélyezése** beállítást. Ha a telepítéskor nem választja ki ezt a lehetőséget, nem használhatja a Kettős írás lehetőséget a Dynamics 365 Human Resources és a Power Apps környezet adatainak integrálására, és nem telepíthet Dynamics 365-alkalmazásokat, például a Dynamics 365 Sales és Field Service alkalmazásokat a környezetbe. Ez a beállítás nem visszavonható. 
    > -  Az Emberi erőforrások nem támogatják a kapcsolt példány megváltoztatását Dataverse, ha már telepítve van az Emberi erőforrások szolgáltatás. </br></br>
    > További tudnivalókat a Power Platform dokumentációs webhely [Fontos szempontok új környezet létrehozásakor](/power-platform/admin/create-environment#some-important-considerations-when-creating-a-new-environment) részében talál.  

7. Miután meghatározta a használandó a helyes környezetet, folytathatja a létesítési folyamat. 

### <a name="supported-geographies"></a>Támogatott földrajzi területek

Az Emberi erőforrások jelenleg a következő földrajzi területeket támogatja:

- Amerikai Egyesült Államok
- Európa
- Egyesült Királyság
- Ausztrália
- Kanada
- Ázsia 

Az Emberi erőforrások környezet létrehozásakor ki kell választania a Power Apps környezetet, hogy társíthassa az Emberi erőforrások környezethez. Az Emberi erőforrások környezet ezzel egy időben létesített Azure földrajzi területe megegyezik a kiválasztott Power Apps környezettel. Az Emberi erőforrások környezetét és az adatbázis fizikai helyét kiválaszthatja, az emberi erőforrások Power Apps környezethez társításakor a földrajzi terület kijelölésével.

Kiválaszthatja azt az Azure *földrajzi területet*, amelyben a környezet felül van vizsgálva, de nem tudja meghatározni az adott Azure *régiót*. Az automatizálás határozza meg a földrajzi terület adott régióját, amelyben a környezet a terheléselosztás és a teljesítmény optimalizálása érdekében lett létrehozva. Az Azure földrajzi területekre és régiókra vonatkozó információkat az [Azure földrajzi területek](https://azure.microsoft.com/global-infrastructure/geographies) dokumentációjában találja.

Az Emberi erőforrások környezet adatai mindig abban az Azure földrajzi területben találhatók, amelyben létre lettek hozva. Azonban nem mindig lesz ugyanabban az Azure-régióban. A természeti erőforrások vészhelyreállítás céljából az adatok másolva lesznek mind az elsődleges Azure-régióba, mind a földrajzi régió másodlagos feladatátvételi régiójába.

 > [!NOTE]
 > Az Emberi erőforrások környezet egy Azure-régióból történő áttelepítése nem támogatott.

## <a name="grant-access-to-the-environment"></a>Hozzáférés biztosítása a környezethez

Alapértelmezés szerint a környezetet csak az a globális rendszergazda érheti el, aki létrehozta. Az alkalmazás további felhasználóinak kifejezett módon engedélyezni kell a hozzáférést. Fel kell vennie a felhasználókat, és hozzájuk kell rendelnie a megfelelő szerepköröket a Human Resources környezetben. További tudnivalókért lásd: [Új felhasználók létrehozása](/dynamics365/unified-operations/dev-itpro/sysadmin/tasks/create-new-users) és [Felhasználók hozzárendelése biztonsági szerepkörökhöz](/dynamics365/unified-operations/dev-itpro/sysadmin/tasks/assign-users-security-roles). 


[!INCLUDE[footer-include](../includes/footer-banner.md)]

