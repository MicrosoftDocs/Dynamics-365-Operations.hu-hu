---
title: Készlet láthatósága bővítmény
description: Ez a témakör a Készlet láthatósága bővítmény telepítését és konfigurálását ismerteti a Dynamics 365 Supply Chain Management rendszerhez.
author: chuzheng
manager: tfehr
ms.date: 10/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-10-26
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 2976153a6a7e4b4130e8f7673ed128945aeabf65
ms.sourcegitcommit: 03c2e1717b31e4c17ee7bb9004d2ba8cf379a036
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/24/2020
ms.locfileid: "4625065"
---
# <a name="inventory-visibility-add-in"></a>Készlet láthatósága bővítmény

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

A Készlet láthatósága bővítmény egy független és jól méretezhető mikroszolgáltatás, amely lehetővé teszi a valós idejű aktuális készletkövetést, így globális képet nyújt a készlet láthatóságáról.

Az aktuális készlethez kapcsolódó összes információt a rendszer közel valós időben exportálja a szolgáltatásba alacsony szintű SQL-integráció révén. A külső rendszerek RESTful API-kon keresztül érik el a szolgáltatást, hogy aktuális információkat kérdezzenek le adott dimenziókészletekről, így lekérve a rendelkezésre álló aktuális pozíciók listáját.

A Készlet láthatósága egy mikroszolgáltatás, amely a Common Data Service rendszerre épül, ami azt jelenti, hogy bővítheti Power Apps alkalmazások készítésével és Power BI alkalmazásával, hogy személyre szabott funkciókat biztosítson, amelyek megfelelnek az üzleti követelményeknek. Lehetőség van az index frissítésére is a készletlekérdezésekhez.

A Készlet láthatósága olyan konfigurációs beállításokat biztosít, amelyek lehetővé teszik, hogy több külső gyártótól származó rendszerrel integrálódjon. Támogatja a szabványosított készletdimenziót, a testreszabott bővíthetőséget és a szabványosított, konfigurálható számított mennyiségeket.

Ez a témakör azt ismerteti, hogyan telepítheti és konfigurálhatja az Készlet láthatósága bővítményt a Dynamics 365 Supply Chain Management rendszerhez, és hogyan használhatja az alkalmazásprogramozási felületét (API).

## <a name="install-the-inventory-visibility-add-in"></a>A Készlet láthatósága bővítmény telepítése

Telepítenie kell a Készlet láthatósága bővítményt a Microsoft Dynamics Lifecycle Services (LCS) használatával. Az LCS egy együttműködési portál, amely egy környezetet és rendszeresen frissített szolgáltatások készletét biztosítja, amelyek segítenek a Dynamics 365 Finance and Operations-alkalmazások alkalmazás-életciklusának kezelésében.

További tudnivalókért lásd: [Lifecycle Services-erőforrások](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/lcs).

### <a name="prerequisites"></a>Előfeltételek

A Készlet láthatósága bővítmény telepítése előtt a következőket kell tennie:

- Szerezzen be egy LCS-megvalósítási projektet legalább egy üzembe helyezett környezettel.
- Hozza létre az ajánlat bétakulcsait az LCS-ben.
- Engedélyezze a felhasználójának szóló ajánlat bétakulcsait az LCS-ben.
- Lépjen kapcsolatba a Microsoft Készlet láthatósága termékcsapatával, és adja meg a környezeti azonosítót, ahol telepíteni szeretné a Készlet láthatósága bővítményt.

Ha bármilyen kérdése van ezekkel az előfeltételekkel kapcsolatban, kérjük, forduljon a Készlet láthatósága termékcsapatához.

### <a name="install-the-add-in"></a><a name="install-add-in"></a>Telepítse a bővítményt

A Készlet láthatósága bővítmény telepítéséhez a következőket kell tennie:

1. Jelentkezzen be a [Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index) portálra.
1. A kezdőlapon válassza ki azt a projektet, amelyben a környezet telepítve van.
1. A projekt oldalon jelölje ki azt a környezetet, amelyben telepíteni szeretné a bővítményt.
1. A környezet oldalon görgessen lefelé, amíg meg nem jelenik a **Környezeti bővítmények** szakasz. Ha a szakasz nem látható, ellenőrizze, hogy az előfeltétel-bétakulcsok teljes mértékben fel lettek-e dolgozva.
1. A **Környezeti bővítmények** szakaszban válassza az **Új bővítmény telepítése** lehetőséget.
    ![A környezeti oldal az LCS-ben](media/inventory-visibility-environment.png "A környezeti oldal az LCS-ben")
1. Válassza az **Új bővítmény telepítése** hivatkozást. Megnyílik az elérhető bővítmények listája.
1. Válassza a **Készletszolgáltatás** elemet a listából. (Megjegyzés: ez most már lehet, hogy **Készlet láthatósága bővítmény a Dynamics 365 Supply Chain Management rendszerhez** néven szerepel.)
1. Adja meg a környezet alábbi mezőinek értékeit:

    - **AAD alkalmazás azonosítója**
    - **AAD bérlő azonosítója**

    ![Hozzáadás a beállítási lapon](media/inventory-visibility-setup.png "Hozzáadás a beállítási lapon")

1. Fogadja el a feltételeket az **Általános Szerződési feltételek** jelölőnégyzet bejelölésével.
1. Válassza a **Telepítés** parancsot. A bővítmény állapota **Telepítés** értékkel jelenik meg. Ha befejeződött, frissítse a lapot, hogy lássa, ahogy a **Telepített** állapotra változik.

### <a name="get-a-security-service-token"></a>Biztonsági szolgáltatás jogkivonatának beszerzése

Biztonsági szolgáltatás jogkivonatának beszerzéséhez tegye a következőket:

1. Szerezze meg az `aadToken` elemet, és hívja a végpontot: https://securityservice.operations365.dynamics.com/token.
1. Cserélje ki a `client_assertion` elemet az `aadToken` törzsében.
1. Cserélje le a kontextust a törzsben arra a környezetre, ahol a bővítményt telepíteni szeretné.
1. Cserélje ki a törzsben lévő hatókört a következőkre:

    - Az MCK hatóköre - "https://inventoryservice.operations365.dynamics.cn/.default"  
    (Az Azure Active Directory alkalmazásazonosítóját és bérlőazonosítóját az MCK-hoz a `appsettings.mck.json` tartalmazza.)
    - Az PROD hatóköre - "https://inventoryservice.operations365.dynamics.com/.default"  
    (Az Azure Active Directory alkalmazásazonosítóját és bérlőazonosítóját az PROD-hoz a `appsettings.prod.json` tartalmazza.)

    Az eredmény az alábbi példához hasonlóan jelenik meg.

    ```json
    {
        "grant_type": "client_credentials",
        "client_assertion_type":"aad_app",
        "client_assertion": "{**Your_AADToken**}",
        "scope":"**https://inventoryservice.operations365.dynamics.com/.default**",
        "context": "**5dbf6cc8-255e-4de2-8a25-2101cd5649b4**",
        "context_type": "finops-env"
    }
    ```

1. Kap egy `access_token` elemet válaszul. Ez az, amire szüksége van, mint tulajdonosi jogkivonat, hogy meghívja meg a Készlet láthatósága API-t. Íme, egy példa.

    ```json
    {
        "access_token": "{Returned_Token}",
        "token_type": "bearer",
        "expires_in": 1200
    }
    ```

### <a name="uninstall-the-add-in"></a>A bővítmény eltávolítása

A bővítmény eltávolításához válassza az **Eltávolítás** lehetőséget. Frissítse az LCS-t, és a Készlet láthatósága bővítmény törlődik. Az eltávolítási folyamat eltávolítja a bővítmény regisztrációját, és elindít egy feladatot a szolgáltatásban tárolt összes üzleti adat törléséhez.

## <a name="inventory-visibility-add-in-public-api"></a>Készlet láthatósága bővítmény nyilvános API

A Készlet láthatósága bővítmény nyilvános REST API-ja az integráció több konkrét végpontját mutatja be. Három fő interakciós típust támogat:

- A bővítmény aktuális módosításainak külső rendszerből történő feladása.
- Aktuális rendelkezésre álló mennyiségek lekérdezése külső rendszerből.
- Automatikus szinkronizálás a Supply Chain Management aktuális adataival.

Az automatikus szinkronizálás nem része a nyilvános API-nak, hanem a rendszer a háttérben kezeli azon környezetek esetében, amelyek engedélyezték a Készlet láthatósága bővítményt.

### <a name="authentication"></a>Hitelesítés

A platform biztonsági jogkivonata a Készlet láthatósága bővítmény hívására szolgál, ezért létre kell hoznia egy Azure Active Directory-jogkivonatot az Azure Active Directory alkalmazás használatával.

A biztonsági jogkivonat beszerzéséről a [Készlet láthatósága bővítmény telepítése](#install-add-in) című témakörben talál további információt.

### <a name="configure-the-inventory-visibility-api"></a>A Készlet láthatósága API konfigurálása

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

#### <a name="custom-measurement"></a>Egyéni mérés

Az alapértelmezett mértékegység-mennyiségek a Supply Chain Managementhez kötődnek, de előfordulhat, hogy egy olyan mennyiséget kell létrehozni, amely az alapértelmezett mértékegységek kombinációjából áll. Ehhez egyéni mennyiségek konfigurációját kell megadni, amely az aktuáliskészlet-lekérdezések kimenetéhez lesz hozzáadva.

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