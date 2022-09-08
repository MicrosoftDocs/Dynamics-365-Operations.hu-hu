---
title: Készletláthatóság nyilvános API-jai
description: Ez a témakör a készlet láthatósága által biztosított nyilvános API-król nyújt részletes információkat.
author: yufeihuang
ms.date: 12/09/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 14812fc201ba1038a78ea3317686dbe189ffa687
ms.sourcegitcommit: 07ed6f04dcf92a2154777333651fefe3206a817a
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2022
ms.locfileid: "9423595"
---
# <a name="inventory-visibility-public-apis"></a>Készletláthatóság nyilvános API-jai

[!include [banner](../includes/banner.md)]


Ez a témakör a készlet láthatósága által biztosított nyilvános API-król nyújt részletes információkat.

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
| /api/environment/{environmentId}/onhand/unreserve | Feladás | [Egy foglalási esemény sztorníroza](#reverse-one-reservation-event) |
| /api/environment/{environmentId}/onhand/unreserve/bulk | Feladás | [Több foglalási esemény sztornírozése](#reverse-multiple-reservation-events) |
| /api/environment/{environmentId}/onhand/changeschedule | Feladás | [Egy ütemezett, de még beütemelt időpontbani módosítás létrehozása](inventory-visibility-available-to-promise.md) |
| /api/environment/{environmentId}/onhand/changeschedule/bulk | Feladás | [Több ütemezett, ütemezett, de időpontban végrehajtott módosítás létrehozása](inventory-visibility-available-to-promise.md) |
| /api/environment/{environmentId}/onhand/indexquery | Feladás | [Lekérdezés a post módszer használatával](#query-with-post-method) |
| /api/environment/{environmentId}/onhand | Beolvasás | [Lekérdezés a get módszer használatával](#query-with-get-method) |
| /api/environment/{environmentId}/allocation/allocation/allocate | Feladás | [Egy felosztási esemény létrehozása](inventory-visibility-allocation.md#using-allocation-api) |
| /api/environment/{environmentId}/allocation/unallocate | Feladás | [Egy nem lefoglalt esemény létrehozása](inventory-visibility-allocation.md#using-allocation-api) |
| /api/environment/{environmentId}/allocation/reallocate | Feladás | [Egy újrafokosó esemény létrehozása](inventory-visibility-allocation.md#using-allocation-api) |
| /api/environment/{environmentId}/allocation/consume | Feladás | [Egy felhasznált esemény létrehozása](inventory-visibility-allocation.md#using-allocation-api) |
| /api/environment/{environmentId}/allocation/query | Feladás | [Lekérdezésfelosztás eredménye](inventory-visibility-allocation.md#using-allocation-api) |

> [!NOTE]
> Az elérési útvonal {environmentId} része a Microsoft Dynamics Lifecycle Services (LCS) környezetazonosítója.
> 
> A tömeges API legfeljebb 512 rekordot ad vissza minden kéréshez.

A Microsoft biztosít egy out-of-box *Postman* kérésgyűjteményt. Ezt a gyűjteményt a következő megosztott link segítségével importálhatja a *Postman* szoftverébe: <https://www.getpostman.com/collections/95a57891aff1c5f2a7c2>.

## <a name="find-the-endpoint-according-to-your-lifecycle-services-environment"></a>A Lifecycle Services környezetének megfelelő végpont megkeresése

A Készletláthatóság mikroszolgáltatás a Microsoft Azure Service Fabric rendszerben kerül telepítésre, több földrajzi területen és több régióban. Jelenleg nincs olyan központi végpont, amely automatikusan átirányítaná a kérést a megfelelő földrajzi területre és régióra. Ezért az információkat a következő minta segítségével kell URL-címé állítani:

`https://inventoryservice.<RegionShortName>-il<IsLandNumber>.gateway.prod.island.powerapps.com`

A régió rövid neve a Microsoft Dynamics Lifecycle Services (LCS) környezetben található. Az alábbi táblázat a jelenleg elérhető régiókat sorolja fel.

| Azure-régió        | Régió rövid neve |
| ------------------- | ----------------- |
| Kelet-Ausztrália      | eau               |
| Délkelet-Ausztrália | seau              |
| Közép-Kanada      | cca               |
| Kelet-Kanada         | eca               |
| Észak-Európa        | neu               |
| Nyugat-Európa         | weu               |
| USA keleti régiója             | eus               |
| USA nyugati régiója             | wus               |
| Dél-UK            | suk               |
| Nyugat-UK             | wuk               |
| Kelet-Japán          | ejp               |
| Nyugat-Japán          | wjp               |
| Dél-Brazília        | sbr               |
| USA déli középső régiója    | scus              |

A sziget száma az a hely, ahol az LCS-környezetet a Service Fabricon telepítették. Ezt az információt jelenleg nem lehet a felhasználói oldalról kihozni.

A Microsoft egy felhasználói felületet (UI) épített be a Power Apps rendszerbe, hogy a mikroszolgáltatás teljes végpontját megismerhesse. További információért lásd: [A szolgáltatás végpontjának keresése](inventory-visibility-configuration.md#get-service-endpoint).

## <a name="authentication"></a><a name="inventory-visibility-authentication"></a>Hitelesítés

A platform biztonsági tokenje a készlet láthatóság nyilvános API hívására szolgál. Ennek megfelelően az _alkalmazás használatával Azure Active Directory (Azure AD) jogkivonatot_ kell Azure AD létrehoznia. Ezt követően az Azure AD-tokent kell ahhoz használnia, hogy a _hozzáférési tokent_ be tudja szerezni a biztonsági szolgáltatásból.

A Microsoft biztosít egy gyári *Postman* jogkivonatlekérés-gyűjteményt. Ezt a gyűjteményt a következő megosztott link segítségével importálhatja a *Postman* szoftverébe: <https://www.getpostman.com/collections/496645018f96b3f0455e>.

A biztonsági szolgáltatási token megszerzéséhez kövesse az alábbi lépéseket.

1. Jelentkezzen be az Azure portálra, és keresse meg a `clientId` és a `clientSecret` értékeket a Dynamics 365 Supply Chain Management alkalmazáshoz.
1. A Azure AD token (`aadToken`) lekérése egy HTTP-kérelem elküldésével, amely a következő tulajdonságokkal rendelkezik:

   - **URL:**`https://login.microsoftonline.com/${aadTenantId}/oauth2/v2.0/token`
   - **Módszer:** `GET`
   - **Törzstartalom (űrlapadatok):**

     | Kulcs           | Érték                                            |
     | ------------- | -------------------------------------------------|
     | ügyfél azonosítója     | ${aadAppId}                                      |
     | titkos ügyfélkód | ${aadAppSecret}                                  |
     | engedélyezési típus    | ügyfél_azonosító adatai                               |
     | Hatókör         | 0cdb527f-a8d1-4bf8-9436-b352c68682b2/.default    |

   Válaszként egy Azure AD tokent (`aadToken`) kell kapnia. Az alábbi példához hasonlóan jelenik meg.

   ```json
   {
       "token_type": "Bearer",
       "expires_in": "3599",
       "ext_expires_in": "3599",
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
       "context": "{$LCS_environment_id}",
       "context_type": "finops-env"
   }
   ```

   Vegye figyelembe az alábbiakat:

   - A `client_assertion` értéknek az előző lépésben kapott Azure AD tokennek (`aadToken`) kell lennie.
   - A `context` érték az a LCS-környezetazonosító, ahová telepíteni szeretné a bővítményt.
   - Az összes többi értéket állítsa be a példában látható módon.

1. Hozzáférési jogkivonat (`access_token`) lekérése HTTP-kérelem elküldésével, amely a következő tulajdonságokkal rendelkezik:

   - **URL:** `https://securityservice.operations365.dynamics.com/token`
   - **Módszer:** `POST`
   - **HTTP fejléc:** tartalmazza az API verzióját. (A kulcs a `Api-Version`, az érték pedig a `1.0`.)
   - **Törzstartalom:** Tartalmazza az előző lépésben létrehozott JSON-kérést.

   Válaszként egy hozzáférési tokent (`access_token`) kell kapnia. Ezt a tokent kell használnia a Készletláthatóság API hívásához. Példa:

   ```json
   {
       "access_token": "{Returned_Token}",
       "token_type": "bearer",
       "expires_in": 3600
   }
   ```

> [!IMPORTANT]
> Amikor a *Postman* kérésgyűjteményt használja a Készlet láthatósága nyilvános API-k hívására, minden egyes kéréshez hozzá kell adni egy tulajdonosi jogkivonatot. A tulajdonosi jogkivonat megkeresése érdekében válassza az **Engedélyezés** lapot a kérés URL-címe alatt, jelölje és válassza ki a **Tulajdonosi jogkivonat** típust, és másolja át az utolsó lépésben beírt hozzáférési jogkivonatot. A cikk későbbi részei `$access_token` az utolsó lépésben bekérett tokent fogják képviselni.

## <a name="create-on-hand-change-events"></a><a name="create-onhand-change-event"></a>Kézben lévő változtatási események létrehozása

Két API áll rendelkezésre a kézben lévő változási események létrehozásához:

- Egy rekord létrehozása `/api/environment/{environmentId}/onhand`
- Több rekord létrehozása `/api/environment/{environmentId}/onhand/bulk`

A következő táblázat összefoglalja a JSON-törzs egyes mezőinek jelentését.

| Mezőazonosító | Leírás |
|---|---|
| `id` | A megadott módosítási esemény egyedi azonosítója. Ha szolgáltatáshiba miatt újraküldés történik, akkor ezt az azonosítót használja a rendszer annak biztosítására, hogy ugyanazt az eseményt ne számolják kétszer a rendszerben. |
| `organizationId` | Az eseményhez kapcsolódó szervezet azonosítója. Ez az érték a Supply Chain Managementtben egy szervezet vagy adatterület azonosítójához van hozzárendelve. |
| `productId` | A termék azonosítója. |
| `quantities` | Az a mennyiség, amellyel a készleten lévő mennyiséget módosítani kell. Például, ha 10 új könyv kerül a polcra, ez az érték `quantities:{ shelf:{ received: 10 }}` lesz. Ha három könyvet levesznek a polcról vagy eladnak, ez az érték `quantities:{ shelf:{ sold: 3 }}` lesz. |
| `dimensionDataSource` | A kiküldetés-változtatási eseményben és a lekérdezésben használt dimenziók adatforrása. Az adatforrás megadása esetén a megadott adatforrás egyéni dimenzióit is használhatja. A Készletláthatóság a dimenziókonfiguráció segítségével leképezheti az egyéni dimenziókat az általános alapértelmezett dimenziókhoz. Ha nincs megadva `dimensionDataSource` érték, akkor csak az általános [alapméreteket](inventory-visibility-configuration.md#data-source-configuration-dimension) használhatja lekérdezéseiben. |
| `dimensions` | Dinamikus kulcs-érték pár. Az értékek a Supply Chain Management néhány dimenziójához vannak rendelve. Azonban egyéni dimenziókat is hozzáadhat (például _Forrás_), hogy jelezze, hogy az esemény a Supply Chain Managementtből vagy egy külső rendszerből származik. |

> [!NOTE]
> A `siteId` és a `locationId` paraméterek építik fel a [partíciókonfigurációt](inventory-visibility-configuration.md#partition-configuration). Ezért ezeket a dimenziókban kell megadni a készletmódosítási események létrehozásakor, a készleten lévő mennyiségek beállításakor vagy felülbírálásakor, illetve a foglalási események létrehozásakor.

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
    "organizationId": "SCM_IV",
    "productId": "T-shirt",
    "dimensionDataSource": "pos",
    "dimensions": {
        "siteId": "iv_postman_site",
        "locationId": "iv_postman_location",
        "posMachineId": "0001",
        "colorId": "red"
    },
    "quantities": {
        "pos": {
            "inbound": 1
        }
    }
}
```

A következő példa a `dimensionDataSource` nélküli törzstartalom mintáját mutatja. Ebben az esetben a `dimensions` lesznek az [alapszintű dimenziók](inventory-visibility-configuration.md#data-source-configuration-dimension). Ha a `dimensionDataSource` be van állítva, a `dimensions` lehet adatforrás- vagy alapszintű dimenzió is.

```json
{
    "id": "123456",
    "organizationId": "SCM_IV",
    "productId": "iv_postman_product",
    "dimensions": {
        "siteId": "iv_postman_site",
        "locationId": "iv_postman_location",
        "colorId": "red"
    },
    "quantities": {
        "pos": {
            "inbound": 1
        }
    }
}
```

### <a name="create-multiple-change-events"></a><a name="create-multiple-onhand-change-events"></a>Több változási esemény létrehozása

Ez az API egyszerre több rekordot is létrehozhat. Az egyetlen különbség az API és az [egyszeri esemény API](#create-one-onhand-change-event) között a `Path` és a `Body` értékek. Ehhez az API-hoz a `Body` egy rekordtömböt biztosít. A rekordok maximális száma 512, ami azt jelenti, hogy az elérhető tömeges módosítási API egyszerre legfeljebb 512 módosítási eseményt támogathat.

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
        "organizationId": "SCM_IV",
        "productId": "iv_postman_product_1",
        "dimensionDataSource": "pos",
        "dimensions": {
            "posSiteId": "posSite1",
            "posLocationId": "posLocation1",
            "posMachineId&quot;: &quot;0001"
        },
        "quantities": {
            "pos": { "inbound": 1 }
        }
    },
    {
        "id": "654321",
        "organizationId": "SCM_IV",
        "productId": "iv_postman_product_2",
        "dimensions": {
            "siteId": "iv_postman_site",
            "locationId": "iv_postman_location",
            "colorId&quot;: &quot;black"
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

A következő példa a törzs tartalmának mintáját mutatja. Az API viselkedése eltér a cikk korábbi, Az elérhető változási események létrehozása című részében ismertetett API-k [viselkedéstől](#create-onhand-change-event). Ebben a mintában a *póló* termék mennyisége 1 lesz.

```json
[
    {
        "id": "123456",
        "organizationId": "SCM_IV",
        "productId": "T-shirt",
        "dimensionDataSource": "pos",
        "dimensions": {
            "posSiteId": "iv_postman_site",
            "posLocationId": "iv_postman_location",
            "posMachineId": "0001"
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

A Foglalás API használatához *be* kell kapcsolni a foglalási funkciót, és be kell fejeződnie a foglalási konfiguráció. További információért lásd: [Foglalási konfiguráció (opcionális)](inventory-visibility-configuration.md#reservation-configuration).

### <a name="create-one-reservation-event"></a><a name="create-one-reservation-event"></a>Egy foglalási esemény létrehozása

Különböző adatforrás-beállítások alapján is lehet foglalást indítani. Az ilyen típusú foglalások konfigurálása érdekében először adja meg az adatforrást a `dimensionDataSource` paraméterben. Ezután a `dimensions` paraméterben határozza meg a dimenziókat a céladatforrás dimenzióbeállításai szerint.

A foglalási API hívása esetén a foglalások érvényességének ellenőrzése a logikai `ifCheckAvailForReserv` paraméter megadásával szabályozható a kérelemtörzsben. A `True` érték azt jelenti, hogy ellenőrzés szükséges, míg a `False` érték azt, hogy az ellenőrzés nem kötelező. Az alapértelmezett érték a `True`.

Foglalás sztornírozása vagy a foglalás nélküli készletmennyiségek foglalása esetén állítsa a mennyiséget negatív értékre, `ifCheckAvailForReserv``False` és állítsa be a paramétert az ellenőrzés kihagyása céljából. Ugyanekhez egy külön, nem lefoglalásra szolgáló API is van. A különbség csak a két API meghívása szerint van így. Egy bizonyos foglalási esemény sztornírozható `reservationId`*a nem foglalási API használatával*. A további tudnivalókat lásd [_a Foglalatlan egy foglalási esemény szakaszban_](#reverse-reservation-events).

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
    "organizationId": "SCM_IV",
    "productId": "iv_postman_product",
    "quantity": 1,
    "quantityDataSource": "iv",
    "modifier": "softReservOrdered",
    "ifCheckAvailForReserv": true,
    "dimensions": {
        "siteId": "iv_postman_site",
        "locationId": "iv_postman_location",
        "colorId": "red",
        "sizeId&quot;: &quot;small"
    }
}
```

A következő példa bemutatja a sikeres választ.

```json
{
    "reservationId": "RESERVATION_ID",
    "id": "ohre~id-822-232959-524",
    "processingStatus": "success",
    "message": "",
    "statusCode": 200
}
``` 

### <a name="create-multiple-reservation-events"></a><a name="create-multiple-reservation-events"></a>Több foglalási esemény létrehozása

Ez az API az [egyszeri esemény API](#create-reservation-events) tömeges változata.

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

## <a name="reverse-reservation-events"></a>Foglalási események sztornírozése

A *Foglalási események sztornírozó műveleteként* a Unreserve [*API szolgál*](#create-reservation-events). Lehetőséget nyújt arra, hogy visszavonjon egy foglalási eseményt, amelyet `reservationId` a foglalási mennyiség meghatároz vagy csökkenti.

### <a name="reverse-one-reservation-event"></a><a name="reverse-one-reservation-event"></a> Egy foglalási esemény sztorníroza

Foglalás létrehozása esetén szerepelni fog a `reservationId` válasz törzse. Ahhoz, hogy törölve legyen a `reservationId` foglalás, ugyanazt meg kell adnia, `organizationId``dimensions` és ugyanezeket kell használni a foglalási API-híváshoz is. Végül adjon meg egy `OffsetQty` értéket, amely az előző foglalásból felszabadítható cikkek számát jelzi. A foglalás a megadott értéktől függően részben vagy teljesen sztornírozható `OffsetQty`. Ha például *100* egység cikk volt lefoglalva, megadhatja, `OffsetQty: 10`*hogy a kezdeti lefoglalt összegből 10-et* foglal le.

```txt
Path:
    /api/environment/{environmentId}/onhand/unreserve
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
        reservationId: string,
        dimensions: {
            [key:string]: string,
        },
        OffsetQty: number
    }
```

A következő kód a törzstartalomra vonatkozó példát mutat be.

```json
{
    "id": "unreserve-0",
    "organizationId": "SCM_IV",
    "reservationId": "RESERVATION_ID",
    "dimensions": {
        "siteid":"iv_postman_site",
        "locationid":"iv_postman_location",
        "ColorId": "red",
        "SizeId&quot;: &quot;small"
    },
    "OffsetQty": 1
}
```

A következő kód egy példát mutat be a sikeres válasz törzsére.

```json
{
    "reservationId": "RESERVATION_ID",
    "totalInvalidOffsetQtyByReservId": 0,
    "id": "ohoe~id-823-11744-883",
    "processingStatus": "success",
    "message": "",
    "statusCode": 200
}
```

> [!NOTE]
> Ha a válasz törzse kisebb `OffsetQty` vagy egyenlő a foglalási mennyiségnél, `processingStatus` az "*sikeres*" `totalInvalidOffsetQtyByReservId`*és 0 lesz*.
>
> Ha `OffsetQty` nagyobb, mint a lefoglalt összeg, akkor "`processingStatus` részleges *·*`totalInvalidOffsetQtyByReservId` mennyiség", `OffsetQty` és ez lesz a különbség és a lefoglalt összeg között.
>
>Ha például a *foglalás mennyisége 10*, `OffsetQty`*és az értéke 12*, `totalInvalidOffsetQtyByReservId`*akkor 2.*

### <a name="reverse-multiple-reservation-events"></a><a name="reverse-multiple-reservation-events"></a> Több foglalási esemény sztornírozése

Ez az API az [egyszeri esemény API](#reverse-one-reservation-event) tömeges változata.

```txt
Path:
    /api/environment/{environmentId}/onhand/unreserve/bulk
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
            reservationId: string,
            dimensions: {
                [key:string]: string,
            },
            OffsetQty: number
        }
        ...
    ]
```

## <a name="query-on-hand"></a>Készleten lévő lekérdezés

Az aktuális *készlet lekérdezési API-ja* segítségével lekérheti a termékek aktuális készletének adatait. Az API jelenleg legfeljebb 5000 `productID` különálló cikk érték alapján való lekérdezését támogatja. Az `siteID` egyes `locationID` lekérdezések több és több értéket is meg lehet adni. A maximális korlátot a következő egyenlet határozza meg:

*NumOf(SiteID) \* NumOf(LocationID) <= 100*.

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
        dimensionDataSource: string, # Optional
        filters: {
            organizationId: string[],
            productId: string[],
            siteId: string[],
            locationId: string[],
            [dimensionKey:string]: string[],
        },
        groupByValues: string[],
        returnNegative: boolean,
    }
```

A kérés törzsrészében a `dimensionDataSource` még mindig egy választható paraméter. Ha nincs beállítva, a `filters` értékek *alapszintű dimenzióként* lesznek kezelve. A `filters` paraméternek négy kötelező mezője van: `organizationId`, `productId`, `siteId` és `locationId`.

- `organizationId` Csak egy értéket tartalmazhat, de az továbbra is tömb.
- `productId` A(0) <a0/<a0/<a2/<a Ha ez egy üres tömb, a rendszer az összes terméket visszaküldi.
- A `siteId` és a `locationId` particionálásra használatosak a Készletláthatóságban. Egynél több `siteId` és `locationId` értéket is megadhat az *Készleten lévő lekérdezés* kérésben. Az aktuális verzióban meg kell adnia a `siteId` és a `locationId` értékeket is.

Javasoljuk, hogy a paraméter használatával `groupByValues` kövesse az indexelés konfigurációját. További információért lásd: [Termékindex-hierarchia konfigurálása](./inventory-visibility-configuration.md#index-configuration).

A `returnNegative` paraméter szabályozza, hogy az eredmények tartalmaznak-e negatív bejegyzéseket.

> [!NOTE]
> Ha engedélyezte a módosítás ütemezését és az ígérethez rendelkezésre álló funkciókat, `QueryATP` a lekérdezés tartalmazhatja a Logikai paramétert is, amely meghatározza, hogy a lekérdezés eredményei tartalmazzák-e az ígérethez rendelkezésre álló adatokat. A további tudnivalókat és [példákat lásd a Készlet láthatósága az aktuális készlet változásának ütemezésében, és ígérethez rendelkezésre áll](inventory-visibility-available-to-promise.md).

A következő példa a törzs tartalmának mintáját mutatja.

```json
{
    "dimensionDataSource": "pos",
    "filters": {
        "organizationId": ["SCM_IV"],
        "productId": ["iv_postman_product"],
        "siteId": ["iv_postman_site"],
        "locationId": ["iv_postman_location"],
        "colorId": ["red"]
    },
    "groupByValues": ["colorId", "sizeId"],
    "returnNegative": true
}
```

A következő példa bemutatja, hogyan lehet lekérdezni egy adott telephely és hely összes termékét.

```json
{
    "filters": {
        "organizationId": ["SCM_IV"],
        "productId": [],
        "siteId": ["iv_postman_site"],
        "locationId": ["iv_postman_location"],
    },
    "groupByValues": ["colorId", "sizeId"],
    "returnNegative": true
}
```

### <a name="query-by-using-the-get-method"></a><a name="query-with-get-method"></a>Lekérdezés a get módszer használatával

```txt
Path:
    /api/environment/{environmentId}/onhand
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

Ez egy minta bejedő URL-címe. Ez a get-kérés pontosan megegyezik a korábban megadott post-mintával.

```txt
/api/environment/{environmentId}/onhand?organizationId=SCM_IV&productId=iv_postman_product&siteId=iv_postman_site&locationId=iv_postman_location&colorId=red&groupBy=colorId,sizeId&returnNegative=true
```

## <a name="available-to-promise"></a>Ígérethez rendelkezésre áll

A készlet láthatóságának beállításával a jövőbeli aktuális készletváltozások ütemezését és az "Aktuális készletben rendelkezésre álló mennyiség számítását" is beállíthatja. Az ígérethez rendelkezésre álló cikk mennyisége, amely a következő időszakban ígérhető a vevőnek. Az ígérethez rendelkezésre álló mennyiség számítása nagy mértékben növelheti a rendelés teljesítésére való képességét. A funkció engedélyezéséről, valamint a készlet-láthatóság és a készlet láthatóságának az API-ja [között a funkció engedélyezése után való kapcsolatról a Készlet láthatósága](inventory-visibility-available-to-promise.md#api-urls) az aktuális készlet változási ütemezésében található, és a funkció ígérethez rendelkezésre áll.

## <a name="allocation"></a>Foglalás

A felosztáshoz kapcsolódó API-k a készlet [láthatósági felosztásában találhatók](inventory-visibility-allocation.md#using-allocation-api).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
