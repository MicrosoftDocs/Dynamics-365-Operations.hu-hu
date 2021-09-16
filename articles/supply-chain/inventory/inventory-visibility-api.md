---
title: Készletláthatóság nyilvános API-jai
description: Ez a témakör a Készletláthatóság által biztosított nyilvános API-kat ismerteti.
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
ms.openlocfilehash: 0aca5838ff6d7c9c4d881698be1e2da2e0e1c02e
ms.sourcegitcommit: b9c2798aa994e1526d1c50726f807e6335885e1a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/13/2021
ms.locfileid: "7343632"
---
# <a name="inventory-visibility-public-apis"></a>Készletláthatóság nyilvános API-jai

[!include [banner](../includes/banner.md)]
[!INCLUDE [cc-data-platform-banner](../../includes/cc-data-platform-banner.md)]

Ez a témakör a Készletláthatóság által biztosított nyilvános API-kat ismerteti.

A Készlet láthatósága bővítmény nyilvános REST API-ja az integráció több konkrét végpontját mutatja be. Négy fő interakciótípust támogat:

- A bővítmény aktuális készletmódosításainak külső rendszerből történő feladása
- Készleten lévő készletmennyiségek beállítása vagy felülbírálása az add-inben egy külső rendszerből
- Foglalási események elküldése a bővítménybe egy külső rendszerből
- Aktuális rendelkezésre álló mennyiségek lekérdezése külső rendszerből

A következő táblázat a jelenleg elérhető API-kat sorolja fel:

| Elérési út | Metódus | Leírás |
|---|---|---|
| /api/environment/{environmentId}/onhand | Feladás | [Egy kézben lévő változtatási esemény létrehozása](#create-one-onhand-change-event) |
| /api/környezet/{environmentId}/onhand/bulk | Feladás | [Több változási esemény létrehozása](#create-multiple-onhand-change-events) |
| /api/environment/{environmentId}/setonhand/{inventorySystem}/bulk | Feladás | [Készleten lévő mennyiségek beállítása/felülbírálása](#set-onhand-quantities) |
| /api/környezet/{environmentId}/onhand/reserve | Feladás | [Egy foglalási esemény létrehozása](#create-one-reservation-event) |
| /api/environment/{environmentId}/onhand/reserve/bulk | Feladás | [Több foglalási esemény létrehozása](#create-multiple-reservation-events) |
| /api/environment/{environmentId}/onhand/indexquery | Beolvasás | [Lekérdezés a post módszer használatával](#query-with-post-method) |
| /api/environment/{environmentId}/onhand/indexquery | Feladás | [Lekérdezés a get módszer használatával](#query-with-get-method) |

A Microsoft biztosít egy out-of-box *Postman* kérésgyűjteményt. Ezt a gyűjteményt a következő megosztott link segítségével importálhatja a *Postman* szoftverébe: <https://www.getpostman.com/collections/90bd57f36a789e1f8d4c>.

## <a name="find-the-endpoint-according-to-your-lifecycle-services-environment"></a>A Lifecycle Services környezetének megfelelő végpont megkeresése

A Készletláthatóság mikroszolgáltatás a Microsoft Azure Service Fabric rendszerben kerül telepítésre, több földrajzi területen és több régióban. Jelenleg nincs olyan központi végpont, amely automatikusan átirányítaná a kérést a megfelelő földrajzi területre és régióra. Ezért az információkat a következő minta segítségével kell URL-címé állítani:

`https://inventoryservice.<RegionShortName>-il<IsLandNumber>.gateway.prod.island.powerapps.com`

A régió rövid neve a Microsoft Dynamics Lifecycle Services (LCS) környezetben található. Az alábbi táblázat a jelenleg elérhető régiókat sorolja fel.

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
| Dél-UK | suk |
| Nyugat-UK | wuk |

A sziget száma az a hely, ahol az LCS-környezetet a Service Fabricon telepítették. Jelenleg nincs mód arra, hogy ezt az információt a felhasználói oldalról megkapjuk.

A Microsoft egy felhasználói felületet (UI) épített be a Power Apps rendszerbe, hogy a mikroszolgáltatás teljes végpontját megismerhesse. További információért lásd: [A szolgáltatás végpontjának keresése](inventory-visibility-power-platform.md#get-service-endpoint).

## <a name="authentication"></a><a name="inventory-visibility-authentication"></a>Hitelesítés

A platform biztonsági tokenje a készlet láthatóság nyilvános API hívására szolgál. Emiatt az Azure AD-alkalmazás használatával létre kell hozni egy _Azure Active Directory (Azure AD) tokent_. Ezt követően az Azure AD-tokent kell ahhoz használnia, hogy a _hozzáférési tokent_ be tudja szerezni a biztonsági szolgáltatásból.

A biztonsági szolgáltatási token megszerzéséhez kövesse az alábbi lépéseket.

1. Jelentkezzen be az Azure portálra, és keresse meg a `clientId` és a `clientSecret` értékeket a Dynamics 365 Supply Chain Management alkalmazáshoz.
1. A Azure AD token (`aadToken`) lekérése egy HTTP-kérelem elküldésével, amely a következő tulajdonságokkal rendelkezik:

    - **URL:** `https://login.microsoftonline.com/${aadTenantId}/oauth2/token`
    - **Módszer:** `GET`
    - **Törzstartalom (űrlapadatok):**

        | Kulcs | Érték |
        |---|---|
        | ügyfél azonosítója | ${aadAppId} |
        | titkos ügyfélkód | ${aadAppSecret} |
        | engedélyezési típus | ügyfél_azonosító adatai |
        | erőforrás | 0cdb527f-a8d1-4bf8-9436-b352c68682b2 |

    Válaszként egy Azure AD tokent (`aadToken`) kell kapnia. Az alábbi példához hasonlóan jelenik meg.

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

1. Fogalmazzon meg egy JavaScript Object Notation (JSON) kérést, amely hasonlít a következő példára.

    ```json
    {
        "grant_type": "client_credentials",
        "client_assertion_type": "aad_app",
        "client_assertion": "{Your_AADToken}",
        "scope": "https://inventoryservice.operations365.dynamics.com/.default",
        "context": "5dbf6cc8-255e-4de2-8a25-2101cd5649b4",
        "context_type": "finops-env"
    }
    ```

    Vegye figyelembe az alábbiakat:

    - A `client_assertion` értéknek az előző lépésben kapott Azure AD tokennek (`aadToken`) kell lennie.
    - A `context` érték az a környezetazonosító, ahová telepíteni szeretné a bővítményt.
    - Az összes többi értéket állítsa be a példában látható módon.

1. Küldjön el egy HTTP-kérelmet, amely a következő tulajdonságokkal rendelkezik:

    - **URL:** `https://securityservice.operations365.dynamics.com/token`
    - **Módszer:** `POST`
    - **HTTP fejléc:** tartalmazza az API verzióját. (A kulcs a `Api-Version`, az érték pedig a `1.0`.)
    - **Törzstartalom:** Tartalmazza az előző lépésben létrehozott JSON-kérést.

    Válaszként egy hozzáférési tokent (`access_token`) kell kapnia. Ezt a tokent kell használnia a Készletláthatóság API hívásához. Íme, egy példa.

    ```json
    {
        "access_token": "{Returned_Token}",
        "token_type": "bearer",
        "expires_in": 3600
    }
    ```

A későbbi szakaszokban a `$access_token` címet fogja használni az utolsó lépésben lekért token ábrázolására.

## <a name="create-on-hand-change-events"></a><a name="create-onhand-change-event"></a>Kézben lévő változtatási események létrehozása

Két API áll rendelkezésre a kézben lévő változási események létrehozásához:

- Egy rekord létrehozása `/api/environment/{environmentId}/onhand`
- Több rekord létrehozása `/api/environment/{environmentId}/onhand/bulk`

A következő táblázat összefoglalja a JSON-törzs egyes mezőinek jelentését.

| Mezőazonosító | Leírás |
|---|---|
| `id` | A megadott módosítási esemény egyedi azonosítója. Ez az azonosító biztosítja, hogy ha a szolgáltatással való kommunikáció meghiúsul a feladás során, a rendszer ne számolja kétszer ugyanazt az eseményt, ha újra beküldi. |
| `organizationId` | Az eseményhez kapcsolódó szervezet azonosítója. Ez az érték a Supply Chain Managementtben egy szervezet vagy adatterület azonosítójához van hozzárendelve. |
| `productId` | A termék azonosítója. |
| `quantities` | Az a mennyiség, amellyel a készleten lévő mennyiséget módosítani kell. Például, ha 10 új könyv kerül a polcra, ez az érték `quantities:{ shelf:{ received: 10 }}` lesz. Ha három könyvet levesznek a polcról vagy eladnak, ez az érték `quantities:{ shelf:{ sold: 3 }}` lesz. |
| `dimensionDataSource` | A kiküldetés-változtatási eseményben és a lekérdezésben használt dimenziók adatforrása. Az adatforrás megadása esetén a megadott adatforrás egyéni dimenzióit is használhatja. A Készletláthatóság a dimenziókonfiguráció segítségével leképezheti az egyéni dimenziókat az általános alapértelmezett dimenziókhoz. Ha nincs megadva `dimensionDataSource` érték, akkor csak az általános [alapméreteket](inventory-visibility-configuration.md#data-source-configuration-dimension) használhatja lekérdezéseiben. |
| `dimensions` | Dinamikus kulcs-érték pár. Az értékek a Supply Chain Management néhány dimenziójához vannak rendelve. Azonban egyéni dimenziókat is hozzáadhat (például _Forrás_), hogy jelezze, hogy az esemény a Supply Chain Managementtből vagy egy külső rendszerből származik. |

### <a name="create-one-on-hand-change-event"></a><a name="create-one-onhand-change-event"></a>Egy kézben lévő változtatási esemény létrehozása

Ez az API egyetlen kézben lévő változási eseményt hoz létre.

```txt
Path:
    /api/environment/{environmentId}/onhand
Method:
    Post
Headers:
    Api-Version="1.0"
    Authorization="Bearer $access_token"
ContentType:
    application/json
Body:
    {
        id: string,
        organizationId: string,
        productId: string,
        dimensionDataSource: string, # Optional
        dimensions: {
            [key:string]: string,
        },
        quantities: {
            [dataSourceName:string]: {
                [key:string]: number,
            },
        },
    }
```

A következő példa a törzs tartalmának mintáját mutatja. Ebben a mintában a *póló* termékhez egy módosítási eseményt küld. Ez az esemény az értékesítési pont (POS) rendszerből származik, és a vásárló egy piros pólót vitt vissza az üzletbe. Ez az esemény a *póló* termék mennyiségét 1-gyel növeli.

```json
{
    "id": "123456",
    "organizationId": "usmf",
    "productId": "T-shirt",
    "dimensionDataSource": "pos",
    "dimensions": {
        "ColorId": "Red"
    },
    "quantities": {
        "pos": {
            "inbound": 1
        }
    }
}
```

A következő példa a `dimensionDataSource` nélküli törzstartalom mintáját mutatja.

```json
{
    "id": "123456",
    "organizationId": "usmf",
    "productId": "T-shirt",
    "dimensions": {
        "ColorId": "Red",
        "SiteId": "1",
        "LocationId": "11"
    },
    "quantities": {
        "pos": {
            "inbound": 1
        }
    }
}
```

### <a name="create-multiple-change-events"></a><a name="create-multiple-onhand-change-events"></a>Több változási esemény létrehozása

Ez az API egyszerre több rekordot is létrehozhat. Az egyetlen különbség az API és az [egyszeri esemény API](#create-one-onhand-change-event) között a `Path` és a `Body` értékek. Ehhez az API-hoz a `Body` egy rekordtömböt biztosít.

```txt
Path:
    /api/environment/{environmentId}/onhand/bulk
Method:
    Post
Headers:
    Api-Version="1.0"
    Authorization="Bearer $access_token"
ContentType:
    application/json
Body:
    [
        {
            id: string,
            organizationId: string,
            productId: string,
            dimensionDataSource: string, # Optional
            dimensions: {
                [key:string]: string,
            },
            quantities: {
                [dataSourceName:string]: {
                    [key:string]: number,
                },
            },
        },
        ...
    ]
```

A következő példa a törzs tartalmának mintáját mutatja.

```json
[
    {
        "id": "123456",
        "organizationId": "usmf",
        "productId": "T-shirt",
        "dimensionDataSource": "pos",
        "dimensions": {
            "PosMachineId&quot;: &quot;0001"
        },
        "quantities": {
            "pos": { "inbound": 1 }
        }
    },
    {
        "id": "654321",
        "organizationId": "usmf",
        "productId": "@PRODUCT1",
        "dimensionDataSource": "pos",
        "dimensions": {
            "PosMachineId&quot;: &quot;0001"
        },
        "quantities": {
            "pos": { "outbound": 3 }
        }
    }
]
```

## <a name="setoverride-on-hand-quantities"></a><a name="set-onhand-quantities"></a>Készleten lévő mennyiségek beállítása/felülbírálása

A _Set on-hand_ API felülírja a megadott termék aktuális adatait.

```txt
Path:
    /api/environment/{environmentId}/setonhand/{inventorySystem}/bulk
Method:
    Post
Headers:
    Api-Version="1.0"
    Authorization="Bearer $access_token"
ContentType:
    application/json
Body:
    [
        {
            id: string,
            organizationId: string,
            productId: string,
            dimensionDataSource: string, # Optional
            dimensions: {
                [key:string]: string,
            },
            quantities: {
                [dataSourceName:string]: {
                    [key:string]: number,
                },
            },
            modifiedDateTimeUTC: datetime,
        },
        ...
    ]
```

A következő példa a törzs tartalmának mintáját mutatja. Ennek az API-nak a viselkedése eltér a témakör korábbi, a [Kézi változási események létrehozása](#create-onhand-change-event) című szakaszában leírt API-k viselkedésétől. Ebben a mintában a *póló* termék mennyisége 1 lesz.

```json
[
    {
        "id": "123456",
        "organizationId": "usmf",
        "productId": "T-shirt",
        "dimensionDataSource": "pos",
        "dimensions": {
            "PosMachineId": "0001"
        },
        "quantities": {
            "pos": {
                "inbound": 1
            }
        }
    }
]
```

## <a name="create-reservation-events"></a>Foglalási események létrehozása

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]

A *Foglalási* API használatához meg kell nyitnia a foglalási funkciót, és ki kell töltenie a foglalási konfigurációt. További információért lásd: [Foglalási konfiguráció (opcionális)](inventory-visibility-configuration.md#reservation-configuration).

### <a name="create-one-reservation-event"></a><a name="create-one-reservation-event"></a>Egy foglalási esemény létrehozása

```txt
Path:
    /api/environment/{environmentId}/onhand/reserve
Method:
    Post
Headers:
    Api-Version="1.0"
    Authorization="Bearer $access_token"
ContentType:
    application/json
Body:
    {
        id: string,
        organizationId: string,
        productId: string,
        dimensionDataSource: string,
        dimensions: {
            [key:string]: string,
        },
        quantityDataSource: string, # optional
        quantities: {
            [dataSourceName:string]: {
                [key:string]: number,
            },
        },
        modifier: string,
        quantity: number,
        ifCheckAvailForReserv: boolean,
    }
```

A következő példa a törzs tartalmának mintáját mutatja.

```json
{
    "id": "reserve-0",
    "organizationId": "usmf",
    "productId": "T-shirt",
    "quantity": 1,
    "quantityDataSource": "iv",
    "modifier": "softreservordered",
    "ifCheckAvailForReserv": true,
    "dimensions": {
        "SiteId": "1",
        "LocationId": "11",
        "ColorId": "Red",
        "SizeId&quot;: &quot;Small"
    }
}
```

### <a name="create-multiple-reservation-events"></a><a name="create-multiple-reservation-events"></a>Több foglalási esemény létrehozása

Ez az API az [egyszeri esemény API](#create-one-reservation-event) tömeges változata.

```txt
Path:
    /api/environment/{environmentId}/onhand/reserve/bulk
Method:
    Post
Headers:
    Api-Version="1.0"
    Authorization="Bearer $access_token"
ContentType:
    application/json
Body:
    [
        {
            id: string,
            organizationId: string,
            productId: string,
            dimensionDataSource: string,
            dimensions: {
                [key:string]: string,
            },
            quantityDataSource: string, # optional
            quantities: {
                [dataSourceName:string]: {
                    [key:string]: number,
                },
            },
            modifier: string,
            quantity: number,
            ifCheckAvailForReserv: boolean,
        },
        ...
    ]
```

## <a name="query-on-hand"></a>Készleten lévő lekérdezés

A _Query on-hand_ API a termékek aktuális készletadatainak lekérdezésére szolgál.

### <a name="query-by-using-the-post-method"></a><a name="query-with-post-method"></a>Lekérdezés a post módszer használatával

```txt
Path:
    /api/environment/{environmentId}/onhand/indexquery
Method:
    Post
Headers:
    Api-Version="1.0"
    Authorization="Bearer $access_token"
ContentType:
    application/json
Body:
    {
        organizationId: string,
        filters: {
            [dimensionKey:string]: string[],
        },
        groupByValues: string[],
        returnNegative: boolean,
    }
```

A következő példa a törzs tartalmának mintáját mutatja.

```json
{
    "dimensionDataSource": "pos",
    "filters": {
        "organizationId": ["usmf"],
        "productId": ["T-shirt"],
        "ColorId": ["Red"]
    },
    "groupByValues": ["ColorId", "SizeId"],
    "returnNegative": true
}
```

### <a name="query-by-using-the-get-method"></a><a name="query-with-get-method"></a>Lekérdezés a get módszer használatával

```txt
Path:
    /api/environment/{environmentId}/onhand/indexquery
Method:
    Get
Headers:
    Api-Version="1.0"
    Authorization="Bearer $access_token"
ContentType:
    application/json
Query(Url Parameters):
    groupBy
    returnNegative
    [Filters]
```

Íme egy minta URL-cím. Ez a get-kérés pontosan megegyezik a korábban megadott post-mintával.

```txt
/api/environment/{environmentId}/onhand/indexquery?organizationId=usmf&productId=T-shirt&ColorId=Red&groupBy=ColorId,SizeId&returnNegative=true
```

[!INCLUDE[footer-include](../../includes/footer-banner.md)]