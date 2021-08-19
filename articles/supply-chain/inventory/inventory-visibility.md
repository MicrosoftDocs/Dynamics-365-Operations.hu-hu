---
title: Készlet láthatósága bővítmény
description: Ez a témakör a Készlet láthatósága bővítmény telepítését és konfigurálását ismerteti a Dynamics 365 Supply Chain Management rendszerhez.
author: sherry-zheng
ms.date: 10/26/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-10-26
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 8faae53f66c069c53609dee72fa30ca18a22c9eb8a86b4669c745c00976af34d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6742704"
---
# <a name="inventory-visibility-add-in"></a>Készlet láthatósága bővítmény

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]
[!INCLUDE [cc-data-platform-banner](../../includes/cc-data-platform-banner.md)]

A Készlet láthatósága bővítmény egy független és jól méretezhető mikroszolgáltatás, amely lehetővé teszi a valós idejű aktuális készletkövetést, így globális képet nyújt a készlet láthatóságáról.

Az aktuális készlethez kapcsolódó összes információt a rendszer közel valós időben exportálja a szolgáltatásba alacsony szintű SQL-integráció révén. A külső rendszerek RESTful API-kon keresztül érik el a szolgáltatást, hogy aktuális információkat kérdezzenek le adott dimenziókészletekről, így lekérve a rendelkezésre álló aktuális pozíciók listáját.

A Készlet láthatósága egy mikroszolgáltatás, amely a Microsoft Dataverse rendszerre épül, ami azt jelenti, hogy bővítheti Power Apps alkalmazások készítésével és Power BI alkalmazásával, hogy személyre szabott funkciókat biztosítson, amelyek megfelelnek az üzleti követelményeknek. Lehetőség van az index frissítésére is a készletlekérdezésekhez.

A Készlet láthatósága olyan konfigurációs beállításokat biztosít, amelyek lehetővé teszik, hogy több külső gyártótól származó rendszerrel integrálódjon. Támogatja a szabványosított készletdimenziót, a testreszabott bővíthetőséget és a szabványosított, konfigurálható számított mennyiségeket.

Ez a témakör azt ismerteti, hogyan telepítheti és konfigurálhatja az Készlet láthatósága bővítményt a Dynamics 365 Supply Chain Management rendszerhez, és hogyan használhatja az alkalmazásprogramozási felületét (API).

## <a name="install-the-inventory-visibility-add-in"></a>A Készlet láthatósága bővítmény telepítése

Telepítenie kell a Készlet láthatósága bővítményt a Microsoft Dynamics Lifecycle Services (LCS) használatával. Az LCS egy együttműködési portál, amely egy környezetet és rendszeresen frissített szolgáltatások készletét biztosítja, amelyek segítenek a Dynamics 365 Finance and Operations-alkalmazások alkalmazás-életciklusának kezelésében.

További tudnivalókért lásd: [Lifecycle Services-erőforrások](../../fin-ops-core/dev-itpro/lifecycle-services/lcs.md).

### <a name="inventory-visibility-add-in-prerequisites"></a>Készletláthatósági bővítmény előfeltételei

A Készlet láthatósága bővítmény telepítése előtt a következőket kell tennie:

- Szerezzen be egy LCS-megvalósítási projektet legalább egy üzembe helyezett környezettel.
- Győződjön meg arról, hogy be vannak fejezve a [Bővítmények áttekintése](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md) részben megadott bővítmények beállításának előfeltételei. A Készlet láthatósága nem igényel kettős írású csatolást.
- Lépjen kapcsolatba a Készlet láthatósági csapatával [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) a következő három szükséges fájl beszerzéséhez:
  - `Inventory Visibility Dataverse Solution.zip`
  - `Inventory Visibility Configuration Trigger.zip`
  - `Inventory Visibility Integration.zip` (ha a Supply Chain Management által futtatott verzió korábbi, mint a 10.0.18)
- Másik lehetőségként lépjen kapcsolatba a Készlet láthatósági csapatával [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) a Package Deployer-csomagok beszerzéséhez. Ezeket a csomagokat egy hivatalos Package Deployer eszköz használhatja.
  - `InventoryServiceBase.PackageDeployer.zip`
  - `InventoryServiceApplication.PackageDeployer.zip` (ez a csomag tartalmazza a `InventoryServiceBase` csomag összes módosítását, valamint további felhasználói felületi alkalmazáskomponenseket)
- Kövesse az itt megadott utasításokat: [Rövid útmutató: Alkalmazások regisztrálása a Microsoft Identity platformmal](/azure/active-directory/develop/quickstart-register-app), hogy regisztráljon egy alkalmazást, és adjon hozzá egy ügyféltitkot az AAD-hez az Azure-előfizetés alatt.
  - [Alkalmazás regisztrálása](/azure/active-directory/develop/quickstart-register-app)
  - [Titkos ügyfélkód hozzáadása](/azure/active-directory/develop/quickstart-register-app#add-a-certificate)
  - Az **Alkalmazás(ügyfél) azonosítója**, az **ügyfél titkos azonosítója** és a **bérlőazonosító** a következő lépésekben lesz használva.

> [!NOTE]
> A jelenleg támogatott országok és régiók: Kanada, az Egyesült Államok és az Európai Unió (EU).

Ha bármilyen kérdése van ezekkel az előfeltételekkel kapcsolatban, kérjük, forduljon a Készlet láthatósága termékcsapatához.

### <a name="set-up-dataverse"></a><a name="setup-microsoft-dataverse"></a>Dataverse beállítása

A Dataverse beállításához a Készlet láthatósága használatához először elő kell készítenie az előfeltételeket, majd el kell döntenie, hogy a Package Deployer eszközzel vagy a megoldások manuális importálásával szeretne-e beállítani Dataverse-t (nem kell mindkettőt megtennie). Majd telepítse a Készlet láthatósága bővítményt. A következő alfejezetek ismertetik az egyes feladatok elvégzésének módját.

#### <a name="prepare-dataverse-prerequisites"></a>A Dataverse-előfeltételek előkészítése

A Dataverse beállításának megkezdése előtt adjon hozzá egy szolgáltatásnevet a bérlőhöz az alábbiak szerint:

1. Telepítse az Azure AD PowerShell modul v2 verzióját az [Azure Active Directory PowerShell for Graph telepítése](/powershell/azure/active-directory/install-adv2) részben leírtak szerint.

1. Futtassa a következő PowerShell-parancsot:

    ```powershell
    Connect-AzureAD # (open a sign in window and sign in as a tenant user)
    
    New-AzureADServicePrincipal -AppId "3022308a-b9bd-4a18-b8ac-2ddedb2075e1" -DisplayName "d365-scm-inventoryservice"
    ```

#### <a name="set-up-dataverse-using-the-package-deployer-tool"></a>A Dataverse beállítása a Package Deployer-eszközzel

Miután rendelkezik az előfeltételekkel, használja a következő eljárást, ha inkább a Package Deployer eszközzel szeretne beállítani a Dataverse-t. A megoldás manuális importálásának részleteiről lásd a következő részt (ne tegye mindkettőt).

1. Fejlesztői eszközök telepítése az [Eszközök letöltése a NuGet-ből](/dynamics365/customerengagement/on-premises/developer/download-tools-nuget) rész alapján.

1. Az üzleti igények alapján válassza ki a `InventoryServiceBase` vagy az `InventoryServiceApplication` csomagot.

1. Importálja a megoldásokat:
    1. Az `InventoryServiceBase`-csomag esetében:
        - Csomagolja ki: `InventoryServiceBase.PackageDeployer.zip`
        - Keresse meg az `InventoryServiceBase` mappát, `[Content_Types].xml`-fájl `Microsoft.Dynamics.InventoryServiceBase.PackageExtension.dll`-fájl `Microsoft.Dynamics.InventoryServiceBase.PackageExtension.dll.config`-fájl és `Microsoft.Dynamics.InventoryServiceBase.PackageExtension.dll.config`-fájl. 
        - Másolja ezeket a mappákat és fájlokat a `.\Tools\PackageDeployment` könyvtárba, amely a fejlesztői eszközök telepítésekor jött létre.
    1. Az `InventoryServiceApplication`-csomag esetében:
        - Csomagolja ki: `InventoryServiceApplication.PackageDeployer.zip`
        - Keresse meg az `InventoryServiceApplication` mappát, `[Content_Types].xml`-fájl `Microsoft.Dynamics.InventoryServiceApplication.PackageExtension.dll`-fájl `Microsoft.Dynamics.InventoryServiceApplication.PackageExtension.dll.config`-fájl és `Microsoft.Dynamics.InventoryServiceApplication.PackageExtension.dll.config`-fájl.
        - Másolja ezeket a mappákat és fájlokat a `.\Tools\PackageDeployment` könyvtárba, amely a fejlesztői eszközök telepítésekor jött létre.
    1. Végrehajtás: `.\Tools\PackageDeployment\PackageDeployer.exe`. Kövesse a képernyőn megjelenő utasításokat a megoldások importálásához.

1. Biztonsági szerepkör hozzárendelése az alkalmazásfelhasználóhoz.
    1. Nyissa meg a Dataverse környezete URL-címét.
    1. Lépjen a **Speciális beállítás \> Rendszer \> Biztonság \> Felhasználók** beállításához, és keresse meg a **# InventoryVisibility** nevű felhasználót.
    1. Válassza a **Szerepkör hozzárendelése**, majd a **Rendszergazda** lehetőséget. Ha van **Common Data Service-felhasználó** nevű szerepkör, válassza ki azt is.

#### <a name="set-up-dataverse-manually-by-importing-solutions"></a>A Dataverse manuális beállítása megoldások importálásával

Miután rendelkezik az előfeltételekkel, használja a következő eljárást, ha inkább a magoldások manuális importálásával szeretne beállítani a Dataverse-t. A Package Deployer eszköz használatáról az előző részben talál részletes információkat (ne tegye mindkettőt).

1. Hozzon létre egy alkalmazásfelhasználót a Készlet láthatósága számára a Dataverse rendszerben:

    1. Nyissa meg a Dataverse környezete URL-címét.
    1. Lépjen a **Speciális beállítások \> Rendszer \> Biztonság \> Felhasználók** lehetőségre, és hozzon létre egy alkalmazásfelhasználót. A nézet menü használatával módosítsa az oldal nézetét az **Alkalmazásfelhasználók** lehetőségre.
    1. Válassza az **Új** lehetőséget. Állítsa az alkalmazásazonosítót a *3022308a-b9bd-4a18-b8ac-2ddedb2075e1* értékre. (Az objektumazonosító azonnal betöltődik, amint menti a módosításokat.) A nevet testreszabhatja. Például a *Készlet láthatósága* értékre módosíthatja. Amikor elkészült, válassza a **Mentés** elemet.
    1. Válassza a **Szerepkör hozzárendelése**, majd a **Rendszergazda** lehetőséget. Ha van **Common Data Service-felhasználó** nevű szerepkör, válassza ki azt is.

    További tudnivalókért lásd: [Alkalmazásfelhasználó létrehozása](/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user).

1. Ha a Dataverse alapértelmezett nyelve nem az **angol**:

    1. Ugrás ide: **Speciális beállítások \> Adminisztráció \> Nyelvek**.
    1. Válassza az **Angol (LanguageCode=1033)**, és az **Alkalmaz** lehetőséget.

1. Importálja az `Inventory Visibility Dataverse Solution.zip` fájlt, amely a Dataverse-konfigurációhoz kapcsolódó entitásokat és Power Apps-alkalmazásokat tartalmazza:

    1. Lépjen a **Megoldások** oldalra.
    1. Válassza az **Importálás** lehetőséget.

1. A konfigurációfrissítés indító folyamatának importálása:

    1. Lépjen a Microsoft Flow oldalra.
    1. Győződjön meg róla, hogy az elnevezett *Dataverse (örökölt)* kapcsolat létezik. (Ha nem létezik, hozza létre.)
    1. Importálja az `Inventory Visibility Configuration Trigger.zip` fájlt. Importálás után az eseményindító a **Saját folyamatok** alatt jelenik meg.
    1. Inicializálja a következő négy változót a környezeti adatok alapján:

        - Azure-bérlő azonosítója
        - Azure-alkalmazásügyfél azonosítója
        - Azure-alkalmazásügyfél titkos kódja
        - Készletláthatósági végpont

            Erről a változóról a témakör későbbi, [A készlet láthatóságának beállítása](#setup-inventory-visibility-integration) című szakasza nyújt további tájékoztatást.

        ![Konfiguráció eseményindítója.](media/configuration-trigger.png "Konfiguráció eseményindítója")

    1. Válassza a **Bekapcsolás** lehetőséget.

### <a name="install-the-add-in"></a><a name="install-add-in"></a>Telepítse a bővítményt

A Készlet láthatósága bővítmény telepítéséhez a következőket kell tennie:

1. Jelentkezzen be a [Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index) portálra.
1. A kezdőlapon válassza ki azt a projektet, amelyben a környezet telepítve van.
1. A projekt oldalon jelölje ki azt a környezetet, amelyben telepíteni szeretné a bővítményt.
1. A környezeti oldalon görgessen lefelé, amíg meg nem látja a **Környezeti bővítmények** szakaszt a **Power Platform-integráció** szakaszban, ahol a Dataverse-környezet neve található.
1. A **Környezeti bővítmények** szakaszban válassza az **Új bővítmény telepítése** lehetőséget.

    ![A környezeti oldal az LCS-ben.](media/inventory-visibility-environment.png "A környezeti oldal az LCS-ben")

1. Válassza az **Új bővítmény telepítése** hivatkozást. Megnyílik az elérhető bővítmények listája.
1. A listában válassza a **Készletláthatóság** elemet.
1. Adja meg a környezet alábbi mezőinek értékeit:

    - **AAD-alkalmazás (ügyfél) azonosítója**
    - **AAD bérlő azonosítója**

    ![Hozzáadás a beállítási lapon.](media/inventory-visibility-setup.png "Hozzáadás a beállítási lapon")

1. Fogadja el a feltételeket az **Általános Szerződési feltételek** jelölőnégyzet bejelölésével.
1. Válassza a **Telepítés** parancsot. A bővítmény állapota **Telepítés** értékkel jelenik meg. Ha befejeződött, frissítse a lapot, hogy lássa, ahogy a **Telepített** állapotra változik.

### <a name="uninstall-the-add-in"></a><a name="uninstall-add-in"></a>A bővítmény eltávolítása

A bővítmény eltávolításához válassza az **Eltávolítás** lehetőséget. Az LCS frissítésekor a Készlet láthatósága bővítmény törlődik. Az eltávolítási folyamat eltávolítja a bővítmény regisztrációját, és elindít egy feladatot a szolgáltatásban tárolt összes üzleti adat törléséhez.

## <a name="consume-on-hand-inventory-data-from-supply-chain-management"></a>Az aktuális készlet adatainak felhasználása a Supply Chain Management alkalmazásból

### <a name="deploy-the-inventory-visibility-integration-package"></a><a name="deploy-inventory-visibility-package"></a>A Készlet láthatósága integrációs csomag központi telepítése

Ha a Supply Chain Management 10.0.17-es vagy korábbi verziója fut, a csomagfájl beszerzéséért forduljon a Készlet láthatósága támogatási csapathoz az [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) címen. Ezután telepítse a csomagot az LCS-be.

> [!NOTE]
> Ha a telepítés során nem egyező verziók fordulnak elő, manuálisan kell importálnia az X++ projektet a fejlesztői környezetbe. Ezt követően hozza létre a telepíthető csomagot a fejlesztői környezetben, és telepítse az éles környezetben.
> 
> A kód része a Supply Chain Management 10.0.18-as verziójának. Ha azt a verziót vagy egy későbbi verziót futtat, nem szükséges a telepítés.

Győződjön meg arról, hogy az alábbi funkciók be vannak kapcsolva a Supply Chain Management-környezetben. (Alapértelmezés szerint be vannak kapcsolva.)

| Funkció leírása | Kódverzió | Osztály váltása |
|---|---|---|
| Készletdimenziók használatának engedélyezése vagy letiltása az InventSum táblán | 10.0.11 | InventUseDimOfInventSumToggle |
| Készletdimenziók használatának engedélyezése vagy letiltása az InventSumDelta táblán | 10.0.12 | InventUseDimOfInventSumDeltaToggle |

### <a name="set-up-inventory-visibility-integration"></a><a name="setup-inventory-visibility-integration"></a>Készletláthatósági integráció beállítása

1. A Supply Chain Management alkalmazásban nyissa meg a **[Szolgáltatáskezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)** munkaterületet, és kapcsolja be a **Készlet láthatósági integrációja** funkciót.
1. Lépjen a **Készletkezelés \> Beállítás \> Készlet láthatósági integrációjának paraméterei** lehetőségre, és adja meg annak a környezetnek az URL-címét, ahol a Készlet láthatóságát futtatja.

    Keresse meg az LCS-környezet Azure-régióját, majd adja meg az URL-címet. Az URL-cím a következő képernyőt tartalmazza:

    `https://inventoryservice.<RegionShortName>-il301.gateway.prod.island.powerapps.com`

    Ha például Európában van, a környezete a következő URL-címek valamelyikét fogja tartalmazni:

    - `https://inventoryservice.neu-il301.gateway.prod.island.powerapps.com`
    - `https://inventoryservice.weu-il301.gateway.prod.island.powerapps.com`

    Jelenleg a következő régiók állnak rendelkezésre.

    | Azure-régió | Régió rövid neve |
    |---|---|
    | Kelet-Ausztrália | eau |
    | Délkelet-Ausztrália | seau |
    | Közép-Kanada | cca |
    | Kelet-Kanada | eca |
    | Észak-Európa | neu |
    | Nyugat-Európa | weu |
    | USA keleti régiója | eus |
    | USA nyugati régiója | wus |

1. Lépjen a **Készletkezelés \> Időszakos \> Készlet láthatósági integrációja** elemre, és engedélyezze a feladatot. A rendszer a Supply Chain Management minden készletváltozási eseményét feladja a Készlet láthatósága számára.

## <a name="the-inventory-visibility-add-in-public-api"></a><a name="inventory-visibility-public-api"></a>A Készlet láthatósága bővítmény nyilvános API-je

A Készlet láthatósága bővítmény nyilvános REST API-ja az integráció több konkrét végpontját mutatja be. Három fő interakciós típust támogat:

- A bővítmény aktuális készletmódosításainak külső rendszerből történő feladása
- Aktuális rendelkezésre álló mennyiségek lekérdezése külső rendszerből
- Automatikus szinkronizálás a Supply Chain Management aktuális készletével

Az automatikus szinkronizálás nem része a nyilvános API-nak. Ehelyett a rendszer a háttérben kezeli olyan környezetekben, ahol engedélyezve van a Készlet láthatósága bővítmény.

### <a name="authentication"></a><a name="inventory-visibility-authentication"></a>Hitelesítés

A platform biztonsági tokenje a Készlet láthatósága bővítmény hívására használatos. Emiatt az Azure AD-alkalmazás használatával létre kell hozni egy *Azure Active Directory (Azure AD) tokent*. Ezt követően az Azure AD-tokent kell ahhoz használnia, hogy a *hozzáférési tokent* be tudja szerezni a biztonsági szolgáltatásból.

Biztonsági szolgáltatás jogkivonatának beszerzéséhez tegye a következőket:

1. Jelentkezzen be az Azure Portal webhelyre, és használja a `clientId` és `clientSecret` keresésére a Supply Chain Management alkalmazáshoz.
1. Azure Active Directory kód beolvasása (`aadToken`) a következő tulajdonságokkal rendelkező HTTP-kérés beküldésével:
    - **URL-cím** - `https://login.microsoftonline.com/${aadTenantId}/oauth2/token`
    - **Metódus** - `GET`
    - **Levél tartalma (űrlapadatok)**:

        | kulcs | érték |
        | --- | --- |
        | ügyfél azonosítója | ${aadAppId} |
        | titkos ügyfélkód | ${aadAppSecret} |
        | engedélyezési típus | ügyfél_azonosító adatai |
        | erőforrás | 0cdb527f-a8d1-4bf8-9436-b352c68682b2 |
1. Válaszként egy `aadToken` kódot kell kapnia, amelynek a következő példához kell hasonlítania.

    ```json
    {
        "token_type": "Bearer",
        "expires_in": "3599",
        "ext_expires_in": "3599",
        "expires_on": "1610466645",
        "not_before": "1610462745",
        "resource": "0cdb527f-a8d1-4bf8-9436-b352c68682b2",
        "access_token": "eyJ0eX...8WQ"
    }
    ```

1. Fogalmazzon meg egy olyan JSON-kérést, amely hasonlít a következőkre:

    ```json
    {
        "grant_type": "client_credentials",
        "client_assertion_type":"aad_app",
        "client_assertion": "{Your_AADToken}",
        "scope":"https://inventoryservice.operations365.dynamics.com/.default",
        "context": "5dbf6cc8-255e-4de2-8a25-2101cd5649b4",
        "context_type": "finops-env"
    }
    ```

    Ahol:
    - A `client_assertion` értéknek az előző lépésben kapott `aadToken` értéknek kell lennie.
    - A `context` érték az a környezetazonosító, ahová telepíteni szeretné a bővítményt.
    - Állítsa be az összes többi értéket a példában látható módon.

1. HTTP-kérés küldése a következő tulajdonságokkal:
    - **URL-cím** - `https://securityservice.operations365.dynamics.com/token`
    - **Metódus** - `POST`
    - **HTTP-fejléc** – tartalmazza az API-verziót (a kulcs `Api-Version` és az érték: `1.0`)
    - **Levél tartalma** – foglalja bele az előző lépésben létrehozott JSON-kérelmet.

1. Kap egy `access_token` elemet válaszul. Ez az, amire szüksége van, mint tulajdonosi jogkivonat, hogy meghívja meg a Készlet láthatósága API-t. Íme, egy példa.

    ```json
    {
        "access_token": "{Returned_Token}",
        "token_type": "bearer",
        "expires_in": 1200
    }
    ```

### <a name="sample-request"></a><a name="inventory-visibility-sample-request"></a>Mintakérés

Referenciaként itt van egy minta HTTP-kérés, használhat a kérés elküldésére bármilyen eszközt vagy kódolási nyelvet, például ``Postman``.

```json
# Url
# replace {RegionShortName} and {EnvironmentId} with your value
https://inventoryservice.{RegionShortName}-il301.gateway.prod.island.powerapps.com/api/environment/{EnvironmentId}/onhand

# Method
Post

# Header
# replace {access_token} with the one get from security service
Api-version: "1.0"
Content-Type: "application/json"
Authorization: "Bearer {access_token}"

# Body
{
    "id": "id-bike-0001",
    "organizationId": "usmf",
    "productId": "Bike",
    "quantities": {
        "pos": {
            "inbound": 5
        }  
    },
    "dimensions": {
        "SizeId": "Small",
        "ColorId": "Red",
        "SiteId": "1",
        "LocationId": "11"
    }
}
```

### <a name="configure-the-inventory-visibility-api"></a><a name="inventory-visibility-configuration"></a>A Készlet láthatósága API konfigurálása

A szolgáltatás használata előtt ki kell töltenie az alábbi alszakaszokban ismertetett konfigurációkat. A konfiguráció a környezet részleteitől függően változhat. Ez elsősorban négy részből áll:

- [Particionálás](#partitioning)
- [Dimenziókonfigurációk](#dimension-configurations)
- [Indexelés](#indexing)
- [Egyéni mérés](#custom-measurement)

#### <a name="partitioning"></a>Particionálás

A particionálás jelentősen befolyásolhatja a Készlet láthatósága API teljesítményét. Célszerű olyan sémát definiálni, amely lehetővé teszi az adatok kis csoportjait, miközben továbbra is lehetővé teszi az értelmezhető adatlekérdezéseket.

Az `organizationId` (`dataAreaId` a Supply Chain Management esetében) mindig a particionálás része lesz, és alapértelmezés szerint a Készlet láthatósága dimenziók szerinti particionálásra van beállítva *Telephely + Hely* szerint. Ez azt jelenti, hogy a szolgáltatást mindig le kell kérdezni ezekkel a szűrőkön definiált dimenziókkal.

> [!NOTE]
> A *Telephely* és a *Hely* két általános alapértelmezett dimenzió a Készlet láthatóságában. A Supply Chain Managementben ezeket a dimenziók *Telephely* (`InventSiteId`) és *Raktár* (`InventLocationId`) néven szerepelnek

### <a name="dimension-configurations"></a>Dimenziókonfigurációk

A Készlet láthatósága az általános alapértelmezett dimenziók listáját tartalmazza a több forrásrendszer integrációjának engedélyezéséhez.

Az alábbi táblázat azokat a készletdimenziókat sorolja fel, amelyek a Készlet láthatósága alapértelmezett dimenziónevei lesznek.

| Dimenzió típusa | Dimenzió neve |
|---|---|
| Termék | `ColorId` |
| Termék | `SizeId` |
| Termék | `StyleId` |
| Termék | `ConfigId` |
| Nyomon követés | `BatchId` |
| Nyomon követés | `SerialId` |
| Helyszín | `LocationId` |
| Helyszín | `SiteId` |
| Készlet állapota | `StatusId` |
| Raktárspecifikus | `WMSLocationId` |
| Raktárspecifikus | `WMSPalletId` |
| Raktárspecifikus | `LicensePlateId` |

> [!NOTE]
> Az előző táblában felsorolt dimenziótípus csak tájékoztató jellegű. A dimenziótípust nem kell definiálnia a Készlet láthatósága bővítményben.

Ha létezik egyéni dimenzió, és a Készlet láthatósága által felhasznált alapértelmezett értékre kell áramlania, az **Egyéni dimenzió** nevét a Készlet láthatóságában konfigurálhatja.

A külső rendszerek RESTful API-kon keresztül férnek hozzá a Készlet láthatóságához, amelyek lehetővé teszik az adott dimenziókészletek aktuális információinak lekérdezését. Az integrációhoz a Készlet láthatósága lehetővé teszi a *külső csatorna adatforrásának* és a forrásdimenziónak a Készlet láthatósága *céldimenzióihoz* való konfigurálását.

A céldimenzióknak a következők egyikének kell lenniük:

- Alapértelmezett dimenziók a Készlet láthatóságában
- Egyéni dimenziók

A dimenziókonfiguráció célja a dimenziókra irányuló lekérdezések és a dimenziókkal való feladási esemény többrendszeres integrációjának szabványosítása.

#### <a name="indexing"></a>Indexelés

Az aktuális készlet lekérdezése a legtöbb alkalommal nem csak a legmagasabb "teljes" szinten lesz, de előfordulhat, hogy a készletdimenziók alapján összesítve szeretné látni az eredményeket.

A Készlet láthatósága rugalmasságot biztosít azáltal, hogy lehetővé teszi az indexek beállítását, amelyek a dimenzión vagy a dimenziók kombinációján alapulnak.

> [!NOTE]
> Jelenleg csak legfeljebb öt indexet konfigurálhat. Alaposan meg kell fontolnia, hogy melyik dimenziót vagy dimenziókombinációt fogja használni a megvalósítás előtt annak érdekében, hogy megfeleljen az üzleti igényeinek. Ha például a következőképpen szeretne lekérdezni a termékeket:

- Az összesített termék lekérdezése a *Szín* és *Méret* dimenziókkal.
- Bizonyos esetekben csak a termék összesített értékét szeretné lekérdezni.

Két indexet kell definiálni a következőképpen:

- `["ColorId", "SizeId"]`
- `[]`

Az üres zárójel a partíción belül termékazonosító alapján összesít.

Az indexelés határozza meg, hogyan csoportosíthatja az eredményeket a `groupBy` lekérdezési beállítás alapján. Ebben az esetben, ha nem határoz meg `groupBy` értékeket, `productid` szerinti összegeket kap. Ellenkező esetben, ha a `groupBy` a `groupBy=ColorId&groupBy=SizeId` értékkel van megadva, a rendszer a különböző szín- és méretkombinációk alapján több sort ad vissza.

A lekérdezési feltételt a kérelem törzsébe teheti.

Itt egy példa a termék szín- és méretkombinációját tartalmazó lekérdezésre.

```json
{
    "filters": {
        "OrganizationId": ["usmf"],
        "ProductId": ["MyProduct1", "MyProduct2"],
        "LocationId": ["21"],
        "SiteId": ["2"],
        "ColorId": ["Red"]
    },
    "groupByValues": [
        "SizeId",
        "ColorId"
    ],
    "returnNegative": true
}
```

A `filters` mezőhöz jelenleg csak `ProductId` támogat több értéket. Ha `ProductId` üres a tömb, a rendszer az összes terméket lekérdezi.

#### <a name="custom-measurement"></a>Egyéni mérés

Az alapértelmezett mértékmennyiségek a Supply Chain Management alkalmazsáshoz kapcsolódnak. Előfordulhat azonban, hogy olyan mennyiséget szeretne, amely az alapértelmezett mértékek kombinációjából áll. Ehhez egyéni mennyiségek konfigurációját kell megadni, amely az aktuáliskészlet-lekérdezések kimenetéhez lesz hozzáadva.

A funkció segítségével egyszerűen meghatározhat egy sor olyan mért értéket, amelyet hozzá kell adni, és/vagy egy sor olyan mért értéket, amelyet ki kell vonni az egyéni mérések kialakításához.

Például a következő lekérdezési feltétel esetén az egyéni mértékegységet úgy kell konfigurálni, mint a `MyCustomAvailableforReservation` elemet, hogy a felhasználó rendszer felhasználja a mennyiséget.

```json
[
    {
        "productId": "MyProduct",
        "dimensions": {
            "colorid": "Red"
        },
        "quantities": {
            "mypos": {
                "outbound": 20.0,
                "inbound": 80.0
            },
            "fno": {
                "availphysical": 100.0,
                "orderedintotal": 50.0,
                "orderedreserved": 10.0
            },
            "exterchannel": {
                "received": 90.0,
                "scheduled": 30.0,
                "issued": 60.0,
                "reserved": 40.0
            }
        }
    }
]

```



| Felhasználó rendszer | Számított mértékek | Adatforrás | Módosító | Módosítószámítási típus |
|---|---|---|---|---|
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `availphysical` | Hozzáadás |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedintotal` | Hozzáadás |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedreserved` | Kivonás |
| `CustomChannel` | `MyCustomAvailableforReservation` | `mypos` | `inbound` | Hozzáadás |
| `CustomChannel` | `MyCustomAvailableforReservation` | `mypos` | `outbound` | Kivonás |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `received` | Hozzáadás |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `scheduled` | Hozzáadás |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `issued` | Kivonás |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `reserved` | Kivonás |

Ezzel az egyéni mérték mennyiség lekérdezése a következő kimenetet fogja visszaadni.

```json
[
    {
        "productId": "MyProduct",
        "dimensions": {
            "colorid": "Red"
        },
        "quantities": {
            "mypos": {
                "outbound": 20.0,
                "inbound": 80.0
            },
            "fno": {
                "availphysical": 100.0,
                "orderedintotal": 50.0,
                "orderedreserved": 10.0
            },
            "exterchannel": {
                "received": 90.0,
                "scheduled": 30.0,
                "issued": 60.0,
                "reserved": 40.0
            },
            "CustomChannel": {
                "MyCustomAvailableforReservation": 220.0
            }
        }
    }
]
```

A `MyCustomAvailableforReservation` kimenet az egyéni mértékek számítási beállításán alapul, a következők szerint:  
 *100 + 50 + 80 + 90 + 30 &ndash; 10 &ndash; 20 &ndash; 60 &ndash; 40 = 220*

### <a name="posting-on-hand-changes"></a>Aktuális készletváltoztatások feladása

A pontos URL-cím, amelyre az esemény feladása történik, a földrajzi régiótól függ. Ez a következő formát veszi fel:

`https://{serviceURL}/api/environment/{environmentId}/onhand`

Ha hitelesítve van, ez az URL-cím együtt használható a HTTP `POST`-metódussal, amellyel a tényleges módosítási eseményeket elküldheti a szolgáltatásnak.

Speciális fejléc használatos a Dynamics 365-szolgáltatásokkal történő kommunikációra HTTP-kérések révén, megjelölve a Supply Chain Management-példány környezeti azonosítóját, amely az adatokhoz van kapcsolva. Példa:

`x-ms-environment-id: 2db79622-f97a-4d64-9844-d12efed41796`

#### <a name="posting-on-hand-changes-query-example-1"></a>Az aktuális készleten elvégzett módosításlekérdezések küldése – 1. példa

Ez a példa egy olyan esetet mutat be, amelyben a dimenzió konfigurációját be kell állítania a Power Appsben.

A dimenzió-hozzárendelés konfigurálásához használja a következő lekérdezést a Power Appsben:

```json
{
    "PosSizeId": "SizeId",
    "PosColorId": "ColorId",
    "PosSiteId": "SiteId",
    "PosLocationId": "LocationId"
}
```

Itt megadhatja a `dimensionDataSource` elemet és a lekérdezésekben használt egyéni dimenziókat. A rendszer automatikusan átváltja az egyéni dimenziókat az alapdimenziókra.

```json
{
    "id": "demo-test-00007",
    "organizationId": "usmf",
    "productId": "MyProduct",
    "quantities": {
        "pos": {
            "Outbound": 1
        }
    },
    "dimensionDataSource": "pos",
    "dimensions": {
        "PosSizeId": "Large",
        "PosColorId": "Red",
        "PosSiteId": "2",
        "PosLocationId": "21"
    }
}
```

#### <a name="posting-on-hand-changes-query-example-2"></a>Az aktuális készleten elvégzett módosításlekérdezések küldése – 2. példa

Ez a példa egy olyan esetet mutat be, amikor nincs beállítva hozzárendelés a dimenziókonfigurációhoz a Power Appsben, így a feladásnak is az alapdimenziókat kell használnia. Minden dimenziónak alapdimenziónak kell lennie, ha a `dimensionDataSource` mező null, üres vagy szóköz.

```json
{
    "id": "demo-test-00007",
    "organizationId": "usmf",
    "productId": "MyProduct",
    "quantities": {
        "pos": {
            "Outbound": 1
        }
    },
    "dimensions": {
        "SizeId": "Large",
        "ColorId": "Red",
        "SiteId": "2",
        "LocationId": "21"
    }
}
```

#### <a name="json-document-field-properties"></a>JSON-dokumentummező tulajdonságai

A JSON-lekérdezés korábban megadott példáiban szereplő mezők a következő táblázatban látható tulajdonságokkal rendelkeznek.

| Mezőazonosító | Leírás |
|---|---|
| `id` | A megadott módosítási esemény egyedi azonosítója. Ez az azonosító annak biztosítására szolgál, hogy ha a szolgáltatással folytatott kommunikáció nem sikerül a feladás során, akkor az esemény újraküldése nem eredményezi azt, hogy a rendszer kétszer számolja ugyanazt az eseményt. |
| `organizationId` | Az eseményhez kapcsolt szervezet azonosítója. Ez a leképezés a Supply Chain Management-szervezetekre vagy az adatterület-azonosítóra vonatkozik. |
| `productId` | A kérdéses termék azonosítója. |
| `quantity` | Az a mennyiség, amellyel az aktuális készletet módosítani kell. Ha például 10 új bagel került fel egy polcra, ez az érték 10 lesz. Ha 3 bagelt eltávolítanak a polcról vagy eladnak, akkor ez az érték – 3. |
| `dimensionDataSource` | A feladási módosítási eseményben és lekérdezésben használt dimenziók adatforrása. Az adatforrás megadása esetén a megadott adatforrás egyéni dimenzióit is használhatja. A dimenzió konfigurálása során a Készlet láthatósága az egyéni dimenziókat az általános alapértelmezett dimenziókra tudja leképezni. Ha a `dimensionDataSource` nincs megadva, akkor a lekérdezésekben csak az általános alapértelmezett dimenziókat használhatja.   |
| `dimensions` | A kulcs/érték párok dinamikus csoportja. Ezek a Supply Chain Management néhány dimenziójára kerülnek leképezésre, de hozzáadhat egyéni dimenziókat is (például *Forrás*), amely jelezheti, hogy az esemény a Supply Chain Managementből vagy egy külső rendszerből származik. |

### <a name="querying-current-on-hand"></a>Aktuális készlet lekérdezése

Az aktuális készlet lekérdezésének végpontja hasonló URL-címmel rendelkezik:

`https://{serviceURL}/api/environment/{environmentId}/onhand/indexquery`

A rendszer lekérdezi a HTTP `POST` metódussal.

#### <a name="current-on-hand-query-example-1"></a>Aktuális készleten lévő lekérdezés – 1. példa

Ez a példa egy olyan esetet mutat be, amelyben a dimenzió konfigurációját már végrehajtották a Power Appsben.

A dimenzió-hozzárendelés konfigurálásához használja a következő lekérdezést a Power Appsben:

```json
{
    "PosSizeId": "SizeId",
    "PosColorId": "ColorId",
    "PosSiteId": "SiteId",
    "PosLocationId": "LocationId"
}
```

Itt megadhatja a `dimensionDataSource` elemet és a lekérdezésekben használt egyéni dimenziókat. A rendszer automatikusan átváltja az egyéni dimenziókat az alapdimenziókra. Megadhatja a `DimensionDataSource` értéket a `filters` számára, és megadhatja az egyéni dimenziókat mind a `filters` és a `groupByValues` esetében. A rendszer automatikusan átváltja az egyéni dimenziókat az alapdimenziókra.

```json
{
    "filters": {
        "OrganizationId": ["usmf"],
        "ProductId": ["MyProduct"],
        "DimensionDataSource": ["Pos"],
        "PosLocationId": ["21"],
        "PosSiteId": ["2"],
        "PosColorId": ["Red"]
    },
    "groupByValues": [
        "PosSizeId",
        "PosColorId"
    ],
    "returnNegative": true
}
```

#### <a name="current-on-hand-query-example-2"></a>Aktuális készleten lévő lekérdezés – 2. példa

Ez a példa egy olyan esetet mutat be, amikor nincs beállítva hozzárendelés a dimenziókonfigurációhoz a Power Appsben, így a feladásnak is az alapdimenziókat kell használnia. Minden dimenziónak alapdimenziónak kell lennie, ha a `dimensionDataSource` mező a `filters` alatt null, üres vagy szóköz.

```json
{
    "filters": {
        "OrganizationId": ["usmf"],
        "ProductId": ["MyProduct"],
        "LocationId": ["21"],
        "SiteId": ["2"],
        "ColorId": ["Red"]
    },
    "groupByValues": [
        "SizeId",
        "ColorId"
    ],
    "returnNegative": true
}
```

#### <a name="example-return-result"></a>Példa visszatérési eredményre

Az előző példákban megjelenített lekérdezések a következőhöz hasonló eredményt adhatnak vissza.

```json
[
    {
        "productId": "MyProduct",
        "dimensions": {
            "colorid": "Red"
        },
        "quantities": {
            "mypos": {
                "outbound": 20.0,
                "inbound": 80.0
            },
            "fno": {
                "availphysical": 100.0,
                "orderedintotal": 50.0,
                "orderedreserved": 10.0
            },
            "exterchannel": {
                "received": 90.0,
                "scheduled": 30.0,
                "issued": 60.0,
                "reserved": 40.0
            },
            "CustomChannel": {
                "MyCustomAvailableforReservation": 220.0
            }
        }
    }
]
```

Ne felejtse el, hogy a mennyiségek mezői a mértékek és a hozzájuk kapcsolódó értékek jegyzékeként vannak strukturálva.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
