---
title: A Készlet láthatósága bővítmény telepítése
description: Ez a témakör a Microsoft Dynamics 365 Supply Chain Management készlet láthatósági kiegészítőjének telepítését ismerteti.
author: yufeihuang
ms.date: 08/02/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: b2b85f533a3318701ed08857b899cf9bdd103863
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7474820"
---
# <a name="install-and-set-up-inventory-visibility"></a>Készletláthatóság telepítése és beállítása

[!include [banner](../includes/banner.md)]
[!INCLUDE [cc-data-platform-banner](../../includes/cc-data-platform-banner.md)]

Ez a témakör a Microsoft Dynamics 365 Supply Chain Management készlet láthatósági kiegészítőjének telepítését ismerteti.

A Készletláthatóság kiegészítő telepítéséhez a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatást kell használnia. Az LCS egy olyan együttműködési portál, amely olyan környezetet és rendszeresen frissített szolgáltatásokat biztosít, amelyek segítenek a pénzügyi és üzemeltetési alkalmazások életciklusának kezelésében.

További tudnivalókért lásd: [Lifecycle Services-erőforrások](../../fin-ops-core/dev-itpro/lifecycle-services/lcs.md).

## <a name="inventory-visibility-prerequisites"></a>Készletláthatóság előfeltételei

A Készletláthatóság telepítése előtt a következő feladatokat kell elvégeznie:

- Szerezzen be egy LCS megvalósítási projektet, ahol legalább egy környezetet telepítettek.
- Győződjön meg arról, hogy a bővítmények beállításának előfeltételei teljesültek. Az előfeltételekkel kapcsolatos információkért lásd: [Add-inek áttekintése](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md). A Készlet láthatósága nem igényel kettős írású csatolást.
- A következő szükséges fájlok beszerzéséhez lépjen kapcsolatba a Készletláthatóság termékcsapattal a [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) címen:

    - `InventoryServiceApplication.PackageDeployer.zip`
    - `Inventory Visibility Integration.zip` (ha a Supply Chain Management által futtatott verzió korábbi, mint a 10.0.18)

> [!NOTE]
> A jelenleg támogatott országok és régiók közé tartozik Kanada (CCA, ECA), az Egyesült Államok (WUS, EUS), az Európai Unió (NEU, WEU), az Egyesült Királyság (SUK, WUK), Ausztrália (EAU, SEAU), Japán (EJP, WJP) és Brazília (SBR, SCUS).

Ha bármilyen kérdése van ezekkel az előfeltételekkel kapcsolatban, forduljon a Készletláthatóság termékcsapatához.

## <a name="set-up-dataverse"></a><a name="setup-microsoft-dataverse"></a>Dataverse beállítása

A Dataverse úgy történő beállításához, hogy az Készletláthatóság csomaggal együtt használható legyen, használja a csomagtelepítő eszközt az Készletláthatóság csomag telepítéséhez. A következő alfejezetek az egyes feladatok elvégzését ismertetik.

> [!NOTE]
> Jelenleg csak az LCS használatával létrehozott Dataverse környezetek támogatottak. Ha a Dataverse környezetet más módon hozták létre (például a Power Apps admin center használatával), és ha az az Ön Supply Chain Management környezetéhez kapcsolódik, akkor először a Készletláthatóság termékcsapattal kell felvennie a kapcsolatot a hozzárendelési probléma megoldása érdekében. Ezután telepítheti a Készletláthatóság funkciót.

### <a name="migrate-from-an-old-version-of-the-dataverse-solution"></a>A Dataverse megoldás régi verziójáról történő migráció

Ha a Dataverse megoldás régebbi verzióját telepítette, a következő utasításokkal frissítheti verzióját. Két eset van:

- **1. eset:** Ha a Dataverse oldalt manuálisan állította be a `Inventory Visibility Dataverse Solution_1_0_0_2_managed.zip` megoldás importálásával, kövesse az alábbi lépéseket:

    1. Töltse le a következő három fájlt:

        - `Inventory Visibility Dataverse Solution_1_0_0_3_managed.zip`
        - `InventoryServiceBase_managed.cab`
        - `InventoryServiceApplication.PackageDeployer.zip`

    1. Kézzel importálja a `Inventory Visibility Dataverse Solution_1_0_0_3_managed.zip` és a `InventoryServiceBase_managed.cab` címeket a Dataverse rendszerbe az alábbi lépésekkel:

        1. Nyissa meg a Dataverse környezete URL-címét.
        1. Nyissa meg a **Megoldások** oldalt.
        1. Válassza az **Importálás** lehetőséget.

    1. A `InventoryServiceApplication.PackageDeployer.zip` csomag telepítéséhez használja a csomagtelepítő eszközt. Az utasításokat lásd a [csomag telepítő eszköz használata a csomag telepítéséhez](#deploy-package) című részben, a témakör későbbi részében.

- **2. eset:** Ha a régebbi `.*PackageDeployer.zip` csomag telepítése előtt a Dataverse csomag telepítő eszközzel állította be a csomagot, töltse le a `InventoryServiceApplication.PackageDeployer.zip` rendszert, és végezze el a frissítést. Az utasításokat lásd a [Csomag telepítő eszköz használata a csomag telepítéséhez](#deploy-package) című szakaszban.

### <a name="use-the-package-deployer-tool-to-deploy-the-package"></a><a name="deploy-package"></a>A csomagtelepítő eszközzel telepítse a csomagot

1. Telepítse a fejlesztői eszközöket a következő pontban leírtak szerint: [Eszközök letöltése NuGet](/dynamics365/customerengagement/on-premises/developer/download-tools-nuget).
1. A következő lépésekkel oldja fel a Teams csoportból letöltött `InventoryServiceApplication.PackageDeployer.zip` fájl blokkolását:

    1. Jelölje ki és tartsa lenyomva (vagy kattintson a jobb gombbal a fájlra), majd válassza a **Tulajdonságok** lehetőséget.
    1. A **Tulajdonságok** párbeszédpanelen az **Általános** lapon keresse meg a **Biztonság** részt, válassza a **Blokkolás feloldása** lehetőséget és alkalmazza a módosítást. Ha az **Általános** lapon nincs **Biztonsági** szakasz, a fájl nincs blokkolva. Ebben az esetben lépjen tovább a következő lépésre.

    ![A letöltött fájl blokkolásának feloldása](media/unblock-file.png "A letöltött fájl blokkolásának feloldása")

1. Nyissa ki a `InventoryServiceApplication.PackageDeployer.zip` csomagot, hogy megtalálja a következő elemeket:

    - `InventoryServiceApplication`-mappa
    - `[Content_Types].xml`-fájl
    - `Microsoft.Dynamics.InventoryServiceApplication.PackageExtension.dll`-fájl

1. Másolja az egyes elemeket a `.\Tools\PackageDeployment` könyvtárba. (Ez a könyvtár a fejlesztői eszközök telepítésekor jött létre.)
1. Futtassa a `.\Tools\PackageDeployment\PackageDeployer.exe` rendszert, és kövesse a képernyőn megjelenő utasításokat a megoldások importálásához.

## <a name="install-the-inventory-visibility-add-in"></a><a name="install-add-in"></a>A Készlet láthatósága bővítmény telepítése

A bővítmény telepítése előtt regisztráljon egy alkalmazást, és adjon hozzá egy ügyféltitkot a Azure Active Directory (Azure AD) címre az Azure-előfizetése alatt. Útmutatásért lásd: [Alkalmazás regisztrálása](/azure/active-directory/develop/quickstart-register-app) és [Ügyféltitok hozzáadása](/azure/active-directory/develop/quickstart-register-app#add-a-certificate). Mindenképpen jegyezze fel az **Alkalmazás (ügyfél) azonosító**, az **Ügyféltitok** és a **Bérlő azonosító** értékeit, mert később szüksége lesz rájuk.

Miután regisztrált egy alkalmazást, és hozzáad egy ügyféltitkot a Azure AD rendszerhez, kövesse az alábbi lépéseket a Készletláthatóság kiegészítő telepítéséhez.

1. Bejelentkezés az [LCS](https://lcs.dynamics.com/Logon/Index) alkalmazásba.
1. A kezdőlapon válassza ki azt a projektet, amelyben a környezet telepítve van.
1. A projekt oldalon jelölje ki azt a környezetet, amelyben telepíteni szeretné a bővítményt.
1. A környezet oldalon görgessen lefelé, amíg meg nem találja a **Környezeti bővítmények** részt az **Power Platform integráció** szakaszban. Itt található a Dataverse környezet neve.
1. A **Környezeti bővítmények** szakaszban válassza az **Új bővítmény telepítése** lehetőséget.

    ![Környezeti oldal az LCS-ben](media/inventory-visibility-environment.png "Környezeti oldal az LCS-ben")

1. Válassza az **Új bővítmény telepítése** hivatkozást. Megjelenik az elérhető bővítmények listája.
1. A listában válassza a **Készletláthatóság** lehetőséget.
1. Állítsa be a következő mezőket a környezetének megfelelően:

    - **AAD alkalmazás (ügyfél) azonosítója** - Adja meg a korábban létrehozott és feljegyzett Azure AD alkalmazás azonosítóját.
    - **AAD bérlő azonosítója** - Adja meg a bérlő azonosítóját, amelyet korábban feljegyzett.

    ![Bővítményoldal beállítása](media/inventory-visibility-setup.png "Bővítményoldal beállítása")

1. Egyetért a feltételekkel a **Feltételek** jelölőnégyzet kiválasztásával.
1. Válassza a **Telepítés** parancsot. A bővítmény állapota a következő: **Telepítés**. Ha a telepítés befejeződött, frissítse az oldalt. Az állapotnak **Telepítettre** kell változnia.

> [!IMPORTANT]
> Ha több LCS-környezete van, mindegyik környezethez hozzon létre egy másik Azure AD alkalmazást. Ha ugyanazt az alkalmazásazonosítót és bérlőazonosítót használja a készlet láthatósági bővítményének különböző környezetekben való telepítéséhez, jogkivonat-probléma fog előfordulni a régebbi környezetekben. Csak az utolsó telepített bővítmény lesz érvényes.

## <a name="uninstall-the-inventory-visibility-add-in"></a><a name="uninstall-add-in"></a>A Készletláthatóság kiegészítő eltávolítása

A Készletláthatóság kiegészítő eltávolításához válassza az LCS oldalon az **Eltávolítás** lehetőséget. Az eltávolítási folyamat megszünteti a Készletláthatóság bővítményt, törli a bővítmény LCS-ből történő regisztrációját, és törli a Készletláthatóság bővítmény adatcache-ében tárolt ideiglenes adatokat. A Dataverse előfizetésben tárolt elsődleges készletadatok azonban nem törlődnek.

A Dataverse előfizetésen tárolt készletadatok eltávolításához nyissa meg a [Power Apps](https://make.powerapps.com), válassza a navigációs sávon a **Környezet** lehetőséget, és válassza ki az LCS-környezetéhez kapcsolt Dataverse környezetet. Ezután lépjen a **Megoldások** menüpontba, és törölje a következő öt megoldást:

- Horgonymegoldás a Dynamics 365 megoldásokban a készletláthatósági alkalmazáshoz
- Dynamics 365 FNO SCM Készletláthatósági alkalmazások megoldása
- Készletszolgáltatás konfigurációja
- Készletláthatóság önállóan
- Dynamics 365 FNO SCM készletláthatóság alapmegoldás

Miután törölte ezeket a megoldásokat, a táblázatokban tárolt adatok is törlődnek.

## <a name="set-up-inventory-visibility-in-supply-chain-management"></a><a name="setup-dynamics-scm"></a>Készletláthatóság beállítása a Supply Chain Management szolgáltatásban

### <a name="deploy-the-inventory-visibility-integration-package"></a><a name="deploy-inventory-visibility-package"></a>A Készlet láthatósága integrációs csomag központi telepítése

Ha a Supply Chain Management 10.0.17-es vagy korábbi verziója fut, a csomagfájl beszerzéséért forduljon a Készlet láthatósága támogatási csapathoz az [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) címen. Ezután telepítse a csomagot az LCS-be.

> [!NOTE]
> Ha a telepítés során nem egyező verziók fordulnak elő, manuálisan kell importálnia az X++ projektet a fejlesztői környezetbe. Ezt követően hozza létre a telepíthető csomagot a fejlesztői környezetben, és telepítse az éles környezetben.
>
> A kód része a Supply Chain Management 10.0.18-as verziójának. Ha azt a verziót vagy egy későbbi verziót futtat, nem szükséges a telepítés.

Győződjön meg arról, hogy az alábbi funkciók be vannak kapcsolva a Supply Chain Management-környezetben. (Alapértelmezés szerint be vannak kapcsolva.)

| Funkció leírása | Kódverzió | Osztály váltása |
|---|---|---|
| Készletdimenziók használatának engedélyezése vagy letiltása az InventSum táblán      | 10.0.11 | InventUseDimOfInventSumToggle      |
| Készletdimenziók használatának engedélyezése vagy letiltása az InventSumDelta táblán | 10.0.12 | InventUseDimOfInventSumDeltaToggle |

### <a name="set-up-inventory-visibility-integration"></a><a name="setup-inventory-visibility-integration"></a>Készletláthatósági integráció beállítása

Ha telepítette a bővítményt, a következő lépések alkalmazásával készítse elő a Supply Chain Management rendszert a bővítménnyel való munkára.

1. A Supply Chain Management alkalmazásban nyissa meg a **[Funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)** munkaterületet, és kapcsolja be a következő funkciókat:
    - *Készletláthatósági integráció* – Szükséges.
    - *Készletláthatósági integráció foglaláseltolása* – Ajánlott, de nem kötelező. A 10.0.22-es vagy újabb verzió szükséges. További információért lásd a [Készletláthatósági foglalások](inventory-visibility-reservations.md) című részt.

1. Menjen a **Készletgazdálkodás \> Beállítás \> Készletláthatósági integrációs paraméterek** menüpontba.
1. Nyissa meg az **Általános** lapot, és adja meg a következő beállításokat:
    - **Készletláthatósági végpont** – Adja meg annak a környezetnek az URL-címét, ahol a Készletláthatóságot futtatja. További információért lásd: [A szolgáltatás végpontjának keresése](inventory-visibility-configuration.md#get-service-endpoint).
    - **Rekordok maximális száma egy kérelemben** – Állítsa be az egy kérelembe foglalható rekordok maximális számát. 1000-nél kisebb vagy azzal egyenlő egész számot kell megadnia. Az alapértelmezett érték 512. Javasoljuk, hogy tartsa meg az alapértelmezett értéket, hacsak nem kapott ajánlást a Microsoft ügyfélszolgálatától, vagy más miatt biztos abban, hogy módosítania kell.

1. Ha engedélyezte a *Készletláthatósági integráció foglaláseltolása* funkciót, nyissa meg a **Foglaláseltolás** lapot, és végezze el a következő beállításokat:
    - **Foglalási eltolás engedélyezése** – A funkció engedélyezéséhez állítsa *Igen* értékre.
    - **Foglaláseltolás módosítója** – Válassza ki azt a készlettranzakció-állapotot, amely a készlet láthatósága alapján eltolja a foglalásokat. Ez a beállítás határozza meg azt a rendelésfeldolgozási szakaszt, amely az eltolásokat kiváltja. A szakasz nyomon követhető a megrendelés készlettranzakciós státusza alapján. A következők közül választhat:
        - *Megrendeléskor* - A *Tranzakciókor* státusz esetén a megrendelés létrehozásakor a megrendelés elküldi az ellentételezési kérelmet. Az eltolásmennyiség a létrehozott rendelés mennyisége lesz.
        - *Tartalékolás* - A *Megrendelt tartalékolás tranzakciós* státusz esetén a rendelés akkor küld beszámítási kérelmet, amikor lefoglalják, felveszik, feladják a csomagolólapot vagy kiszámlázzák. A kérés csak egyszer, az első lépésben aktiválódik, amikor az említett folyamat bekövetkezik. Az eltolás mennyisége az a mennyiség, amelynél a készlettranzakció állapota a *Megrendelt* állapotról *Lefoglalt rendeltre* (vagy későbbi állapotra) változott a megfelelő rendelési sorban.

1. Lépjen a **Készletkezelés \> Időszakos \> Készlet láthatósági integrációja** elemre, és engedélyezze a feladatot. A rendszer a Supply Chain Management minden készletváltozási eseményét feladja a Készlet láthatósága számára.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
