---
title: Integráció külső gyártásvégrehajtási rendszerekkel
description: Ez a témakör bemutatja, hogy hogyan integrálhatja a Microsoftot egy külső Dynamics 365 Supply Chain Management gyártásvégrehajtási rendszerrel (MES).
author: t-benebo
ms.date: 10/01/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-10-01
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: 43814023474d44b8c95bae087c7b6a4d52d21471
ms.sourcegitcommit: 7cbd53617af179a0de74aae30c149edc95e86684
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/06/2021
ms.locfileid: "7891926"
---
# <a name="integrate-with-third-party-manufacturing-execution-systems"></a>Integráció külső gyártásvégrehajtási rendszerekkel

[!include [banner](../includes/banner.md)]

Egyes gyártó szervezetek, amelyek a Microsoft natív funkcióit használják a Dynamics 365-ben, gépekre, berendezésekre és személyzetre vonatkozó gyártási Dynamics 365 Supply Chain Management tevékenységeik szabályozására. Azonban más gyártó szervezetek, különösen azok, amelyek gyártási követelményei magas szintűek, egy harmadik fél gyártás-végrehajtási rendszerét (MES) használják helyette. A szervezetek például egy harmadik féltől származó MES-megoldást választhatnak, mivel ez például a iparágra szabott.

Az integrált megoldásban az adatcsere teljesen automatizált, és a közel valós időben történik. Emiatt az adatok mindkét rendszerben naprakészek maradnak, és nem szükséges manuális adatbevitel. Ha például az anyagfelhasználás regisztrálva van a MES rendszerből, az integráció biztosítja, hogy ugyanaz a felhasználás is regisztrálva lesz a Dynamics 365-ben. Ennek megfelelően a többi fontos folyamat, például a tervezés és az értékesítés, naprakész készletrekordok érhetők el.

A megoldás lehetővé teszi, hogy az ellátásilánc-kezelő felhasználók gyorsabban, egyszerűbben és könnyebben integrálják az ellátásilánc-kezelő felhasználókat a külső MES-ekkel. A következő funkciókat kínálja:

- A kulcsgyártási végrehajtási folyamatokat [támogató üzleti események és interfészek](#processes-available-for-mes-integration)
- Egy központosított irányítópult, amely nyomon követheti az eseményfeldolgozási előzményeket, és elháríthatja és kijavíthatja a sikertelen folyamatokat.

A következő ábra az integrált megoldásban cserélt üzleti események, folyamatok és üzenetek egy jellemző gyűjteményét mutatja be.

![Tipikus integrációs helyzet.](media/3p-mes-scenario.png "Tipikus integrációs helyzet.")

## <a name="turn-on-the-mes-integration-feature"></a>A MES-integráció funkció bekapcsolása

A funkció használata előtt be kell azt kapcsolnia saját rendszerében. A rendszergazdák használhatják a [funkciókezelési](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) beállításokat a funkció állapotának ellenőrzéséhez, és bekapcsolásához. A **Funkció kezelése** munkaterületen a funkció a következő módon van listázva:

- **Modul:** *Gyártásvezérlés*
- **Funkciónév:** *Gyártás-végrehajtási rendszer integrációja*

## <a name="processes-available-for-mes-integration"></a>MES-integrációhoz elérhető folyamatok

Az alábbi folyamatok bármelyikét engedélyezheti integrációra.

| Feldolgozás neve | Leírás |
|---|---|
| Termelési rendelések kiadása és a termelési rendelés állapotváltozási üzleti eseményei | Ez a folyamat olyan üzleti eseményt biztosít, amelyet a MES figyelhet, hogy információkat kap a termelni szükséges termelési rendelésekről. A termelési rendeléshez kapcsolódó hivatkozási adatokat várhatóan megosztják az Ellátásilánc-kezelés és a MES között nyitott adat protokollal (OData) vagy adatentitásokkal. |
| Termelési rendelés indítása | Ez a folyamat a MES használatával elindított termelési rendelésekről nyújt információkat az ellátásilánc-kezeléshez. Gondoskodik arról, hogy mindkét rendszer naprakészen legyen minden gyártási tevékenységről. |
| Termelt vagy selejtes mennyiség jelentése | Ez a folyamat az ellátásilánc-kezeléshez információt nyújt a termelési feladattal kapcsolatban a MES segítségével jelentett helyes és hibás mennyiségekről. Gondoskodik arról, hogy az üzemvezetők naprakészen tekintsenek a termelési tervek folyamatáról. |
| Anyagfelhasználás jelentése | Ez a folyamat az ellátásilánc-kezeléshez információt nyújt a MES számára a felhasznált anyagok mennyiségével kapcsolatban. Naprakész készletrekordokat tesz elérhetővé más fontos folyamatok, például a tervezés és az értékesítés számára. |
| A művelet felhasznált időének jelentése | Ez a folyamat információt nyújt az ellátásilánc-kezelésnek arról az időről, amely egy adott művelethez szükséges. |
| Termelési rendelés befejezése | Ez a folyamat tájékoztatja az ellátásilánc-kezelőt, hogy a MES frissítette a termelési rendelést a végleges *állapotára.* Ez az állapot azt jelzi, hogy a termelési rendelésen nem készül több mennyiség. |

## <a name="monitor-incoming-messages"></a>Bejövő üzenetek figyelése

A rendszerbe beérkező üzenetek figyelése érdekében nyissa meg **a Gyártásvégrehajtási rendszerek integrációs** lapját. Itt megtekintheti, feldolgozhatja és elháríthatja a problémákat.

## <a name="call-the-api"></a>Az API hívása

A MES integrációs API hívásához küldjön egy kérést a `POST` következő végpont URL-címének:

`/api/services/SysMessageServices/SysMessageService/SendMessage`

A küldött kérés törzsének a következő példához hasonlónak kell lennie. A, `_companyId` és `_messageType` a szükséges értékek `_messageContent` cseréje. Az API által támogatott különféle üzenettípusokról és a tartalom megtervezéseről a következő szakaszban található tájékoztatás.

```json
{
    "_companyId": "USMF",
    "_messageQueue": "JmgMES3P",
    "_messageType": "ProdProductionOrderReportFinished",
    "_messageContent":
    "{\"ProductionOrderNumber\": \"P000123\", \"ReportFinishedLines\": [{\"ItemNumber\": \"A0001\", \"ReportedGoodQuantity\": 10, \"ReportAsFinishedDate\": \"2021-01-01\"}]}"
}
```

## <a name="api-message-types-and-content"></a>API-üzenettípusok és -tartalom

Ez a szakasz leírja az egyes üzenettípusokat, amelyek a MES integrációs API-n keresztül át cserélhetők.

### <a name="start-production-order-message"></a>Termelési rendelés üzenetének kezdete

A termelési *rendelés* indítási üzenetének `_messageType` értéke `ProdProductionOrderStart`: Az alábbi táblázat bemutatja az üzenet által támogatott mezőket.

| Mezőnév | Állapot | Típus |
|---|---|---|
| `ProductionOrderNumber` | Kötelező | Sztring |
| `StartedQuantity` | Választható | Valós |
| `StartedDate` | Választható | Dátum |
| `AutomaticBOMConsumptionRule` | Választható | Enum (FlushingPrincip \| mindig \| soha) |

### <a name="report-as-finished-message"></a>Készként jelentés üzenete

A *készként jelentés* üzenetében `_messageType` ez az `ProdProductionOrderReportFinished` érték. Az alábbi táblázat bemutatja az üzenet által támogatott mezőket.

| Mezőnév | Állapot | Típus |
|---|---|---|
| `ProductionOrderNumber` | Kötelező | Sztring |
| `ReportFinishedLines` | Kötelező | A következő táblában leírt rakományt tartalmazó sorok (legalább egy) listája |

Az alábbi táblázat bemutatja azokat a mezőket, amelyek az üzenet szakaszának egyes sorait `ReportFinishedLines``ProdProductionOrderReportFinished` támogatják.

| Mezőnév | Állapot | Típus |
|---|---|---|
| `LineNumber` | Választható | Valós |
| `ItemNumber` | Választható | Sztring|
| `ProductionType` | Választható | Enum (MainItem \| receptúra \| Co_Product \| By_Product \|\| Nincs), extensible |
| `ReportedErrorQuantity` | Választható | Valós|
| `ReportedGoodQuantity` | Választható | Valós|
| `ReportedErrorCatchWeightQuantity` | Választható | Valós |
| `ReportedGoodCatchWeightQuantity` | Választható | Valós |
| `AcceptError` | Választható |Logikai |
| `ErrorCause` | Választható | Enum (Nincs \| material \| Machine \| OperatingStaff), extensible |
| `ExecutedDateTime` | Választható | DateTime |
| `ReportAsFinishedDate` | Választható | Dátum |
| `AutomaticBOMConsumptionRule` | Választható | Enum (FlushingPrincip \| mindig \| soha) |
| `AutomaticRouteConsumptionRule` | Választható |Enum (RouteDependent \| mindig \| soha) |
| `RespectFlushingPrincipleDuringOverproduction` | Választható | Logikai |
| `ProductionJournalNameId` | Választható | Sztring |
| `PickingListProductionJournalNameId` | Választható | Sztring|
| `RouteCardProductionJournalNameId` | Választható | Sztring |
| `FromOperationNumber` | Választható | Egész|
| `ToOperationNumber` | Választható | Egész|
| `InventoryLotId` | Választható | Sztring |
| `BaseValue` | Választható | Sztring |
| `EndJob` | Választható | Logikai |
| `EndPickingList` | Választható | Logikai |
| `EndRouteCard` | Választható | Logikai |
| `PostNow` | Választható | Logikai |
| `AutoUpdate` | Választható | Logikai |
| `ProductColorId` | Választható | Sztring|
| `ProductConfigurationId` | Választható | Sztring |
| `ProductSizeId` | Választható | Sztring |
| `ProductStyleId` | Választható | Sztring |
| `ProductVersionId` | Választható | Sztring |
| `ItemBatchNumber` | Választható | Sztring |
| `ProductSerialNumber` | Választható | Sztring |
| `LicensePlateNumber` | Választható | Sztring |
| `InventoryStatusId` | Választható | Sztring |
| `ProductionWarehouseId` | Választható | Sztring |
| `ProductionSiteId` | Választható | Sztring |
| `ProductionWarehouseLocationId` | Választható | Sztring |
| `InventoryDimension1` és `InventoryDimension12` között | Választható | Sztring |

A 12 extensible dimenziót (keresztül) testre kell szabni, `InventoryDimension1``InventoryDimension12` és nem mindig használatosak. A dimenziókkal kapcsolatos további tudnivalókat [lásd: Új készletdimenziók hozzáadása](../../fin-ops-core/dev-itpro/extensibility/inventory-dimensions.md) kiterjesztéssel.

### <a name="material-consumption-picking-list-message"></a>Anyagfelhasználási (kitárolási lista) üzenet

Az *anyagfelhasználási (kitárolási lista) üzenet* értéke `_messageType``ProdProductionOrderPickingList`: Az alábbi táblázat bemutatja az üzenet által támogatott mezőket.

| Mezőnév | Állapot | Típus |
|---|---|---|
| `ProductionOrderNumber` | Kötelező | Sztring |
| `JournalNameId` | Választható | Sztring |
| `PickingListLines` | Kötelező | A következő táblában leírt rakományt tartalmazó sorok (legalább egy) listája |

Az alábbi táblázat bemutatja azokat a mezőket, amelyek az üzenet szakaszának egyes sorait `PickingListLines``ProdProductionOrderPickingList` támogatják.

| Mezőnév | Állapot | Típus |
|---|---|---|
| `ItemNumber` | Kötelező | Sztring |
| `ConsumptionBOMQuantity` | Választható | Valós |
| `ProposalBOMQuantity` | Választható | Valós |
| `ScrapBOMQuantity` | Választható | Valós |
| `BOMUnitSymbol` | Választható | Sztring |
| `ConsumptionInventoryQuantity` | Választható | Valós |
| `ProposalInventoryQuantity` | Választható | Valós |
| `ConsumptionCatchWeightQuantity` | Választható | Valós |
| `ProposalCatchWeightQuantity` | Választható | Valós |
| `ConsumptionDate` | Választható | Dátum |
| `OperationNumber` | Választható | Egész |
| `LineNumber` | Választható | Valós |
| `PositionNumber` | Választható | Sztring |
| `IsConsumptionEnded` | Választható | Logikai |
| `ErrorCause` | Választható | Enum (Nincs \| material \| Machine \| OperatingStaff), extensible |

### <a name="time-used-for-operation-route-card-message"></a>Művelethez (útvonalkártya) küldött üzenethez felhasznált idő

A *művelet (útvonalkártya) üzenetében a következő*`_messageType` érték áll `ProdProductionOrderRouteCard` be: Az alábbi táblázat bemutatja az üzenet által támogatott mezőket.

| Mezőnév | Állapot | Típus |
|---|---|---|
| `ProductionOrderNumber` | Kötelező | Sztring |
| `JournalNameId` | Választható | Sztring |
| `RouteCardLines` | Kötelező | A következő táblában leírt rakományt tartalmazó sorok (legalább egy) listája |

Az alábbi táblázat bemutatja azokat a mezőket, amelyek az üzenet szakaszának egyes sorait `RouteCardLines``ProdProductionOrderRouteCard` támogatják.

| Mezőnév | Állapot | Típus |
|---|---|---|
| `OperationNumber` | Kötelező | Egész |
| `OperationPriority` | Választható | Enum (elsődleges \| másodlagos1 \|\| másodlagos2... \| Másodlagos20) |
| `OperationId` | Választható | Sztring |
| `OperationsResourceId` | Választható | Sztring |
| `Worker` | Választható | Sztring |
| `HoursRouteCostCategoryId` | Választható | Sztring |
| `QuantityRouteCostCategoryId` | Választható | Sztring |
| `HourlyRate` | Választható | Valós |
| `Hours` | Választható | Valós |
| `GoodQuantity` | Választható | Valós |
| `ErrorQuantity` | Választható | Valós |
| `CatchWeightGoodQuantity` | Választható | Valós |
| `CatchWeightErrorQuantity` | Választható | Valós |
| `QuantityPrice` | Választható | Valós |
| `ProcessingPercentage` | Választható | Valós |
| `ConsumptionDate` | Választható | Dátum |
| `TaskType` | Választható | Enum (QueueBefore \|\| beállítási folyamat \| átfedésben \| van a szállítási \| várólistaAfter \| terhelése) |
| `ErrorCause` | Választható | Enum (Nincs \| material \| Machine \| OperatingStaff), extensible |
| `OperationCompleted` | Választható | Logikai |
| `BOMConsumption` | Választható | Logikai |
| `ReportAsFinished` | Választható | Logikai |

### <a name="end-production-order-message"></a>Termelési rendelés üzenetének vége

A termelési *rendelés záró* üzenetének értéke `_messageType``ProdProductionOrderEnd`: Az alábbi táblázat bemutatja az üzenet által támogatott mezőket.

| Mezőnév | Állapot | Típus |
|---|---|---|
| `ProductionOrderNumber` | Kötelező | Sztring |
| `ExecutedDateTime` | Választható | DateTime |
| `EndedDate` | Választható | Dátum |
| `UseTimeAndAttendanceCost` | Választható | Logikai |
| `AutoReportAsFinished` | Választható | Logikai |
| `AutoUpdate` | Választható | Logikai |

## <a name="receive-feedback-about-the-state-of-a-message"></a>Visszajelzés fogadása egy üzenet állapotáról

Miután a MES elküldte az üzenetet az ellátásilánc-kezelésnek, az ellátásilánc-kezelésnek vissza kell küldenie az üzenet állapotára vonatkozó visszajelzést. Néhány példa olyan esetekre, amelyekben fontos lehet ez a viselkedés:

- Nincs olyan személy, aki felelős a MES-integráció folyamatos felügyeletéért.
- A MES-integráció felügyeletéért felelős személyt e-mailben értesíteni kell, ha egy üzenet sikertelen, és tudják, hogy meg kell intézkedéseketük.
- A MES-nek egy hibaüzenetet kell mutatnia, amely tájékoztatja az üzemben kezelőt vagy az informatikai részlegtől, hogy lépéseket kell- e küldeniük.
- A MES-nek újra kellszámoznia a rendelés ütemezését, miután hibaüzenetet kapott (például mert egy termelési rendelést nem sikerült elindítani).

Ilyen esetekben az Ellátásilánc-kezelés általános figyelmeztetési szolgáltatása használható. A normál figyelmeztetések hogyan működnek, az alábbi forrásokban található tájékoztatás:

- Súgótémakör: [Figyelmeztetések – áttekintés](../../fin-ops-core/fin-ops/get-started/alerts-overview.md)
- Video: [Figyelmeztetési szabály beállításai a következőben: Dynamics 365 for Finance and Operations](https://www.youtube.com/watch?v=cpzimwOjicM&ab_channel=MicrosoftDynamics365)

Beállíthatja például az alábbi figyelmeztetéseket, hogy visszajelzést ad az üzenetek állapotáról:

- Az üzenet sikertelen küldése esetén használt üzleti esemény ("Külső küldés") *létrehozása*.
- Értesítés és e-mail küldése az rendszergazdának vagy a termelés felelősének.
