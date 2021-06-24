---
title: Készlet rendelkezésre állása kettős írásban
description: Ez a témakör a készlet rendelkezésre állásának ellenőrzéséről a kettős írásban tartalmaz tájékoztatást.
author: RamaKrishnamoorthy
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-05-26
ms.openlocfilehash: 0fded78134b1427e6faea9656e1d3b02b467ae91
ms.sourcegitcommit: 74e47075eab2b0b28f82b0d57f439719847ecb01
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/07/2021
ms.locfileid: "6193407"
---
# <a name="inventory-availability-in-dual-write"></a>Készlet rendelkezésre állása kettős írásban

[!include [banner](../../includes/banner.md)]

A készlet elérhetőségét használva ellenőrizheti a készletet, mielőtt terméket ad hozzá az **Ajánlatok**, **Rendelések** vagy **Számlák** oldalakhoz a Microsoft Dynamics 365 Sales alkalmazásban. Például a készlet ellenőrzése és a teljesítés dátuma egy kulcsfeladat a [potenciális vevők készpénzre váltása](dual-write-prospect-to-cash.md) folyamatban.

Ha nincs elég készlete, megbecsülheti a várható szállítási dátumot az előrejelzett készletbevételezés és -kiadás alapján. Megtekintheti a termék ígérethez rendelkezésre áll információit is, ahol megtalálhatja az ígért mennyiséget az előre meghatározott időkorláton belül.

## <a name="on-hand-inventory"></a>Aktuális készlet

A Dynamics 365 Sales alkalmazásban egy új **Rendelkezésre álló készlet** gomb lett hozzáadva az **Ajánlatok**, **Rendelések** és **Számlák** űrlapjainak fejlécében. Amikor a gombra kattint, megjelenik egy párbeszédpanel, ahol megadhatja azt a vállalatot és terméket, amelynek az aktuális készletét ellenőrizni szeretné. Ez a párbeszédpanel ugyanazokat az adatokat jeleníti meg, mint az [Aktuális készlet](../../../../supply-chain/inventory/tasks/check-availability-stock.md).

A párbeszédpanel a Dynamics 365 Supply Chain Management készletadatait jeleníti meg. Ez az információ az alábbi mennyiségeket tartalmazza:

- Aktuális mennyiség
- Lefoglalt aktuális mennyiség
- Elérhető aktuális mennyiség
- Megrendelt mennyiség
- Rendelésben lévő mennyiség
- Lefoglalt rendelt mennyiség
- Teljes elérhető mennyiség

## <a name="atp-information"></a>Információk az ígérethez rendelkezésre álló készletről

A Sales alkalmazásban az **Árajánlatok** , **Rendelések** és **Számlák** oldalain egy új, **ATP-információ** gombbal bővült a cikkek sora. Amikor ezt a gombot választja, megjelenik egy párbeszédpanel, amelyen megadhatja a vállalatot, terméket, helyet, készletraktárat és rendelési mennyiséget. Ez a párbeszédpanel ugyanolyan beállításokat tartalmaz, mint a [Rendelési ígéret](../../../../supply-chain/sales-marketing/delivery-dates-available-promise-calculations.md#atp-calculations).

A párbeszédpanel a Supply Chain Management „ígérethez rendelkezésre áll” adatait adja vissza. Ez az információ az alábbi mennyiségeket tartalmazza:

- Ígérethez rendelkezésre álló mennyiség
- Bevételezés mennyisége
- Kiadás mennyisége
- Aktuális mennyiség

## <a name="how-it-works"></a>Hogyan működik?

Ha az **Árajánlatok**, **Rendelések** vagy **Számlák** lapon az **Aktuális készlet** gombot választja, a rendszer élő, kettős írásos hívást küld az **Aktuális készlet** API-jának. Az API kiszámítja az adott termék aktuális készletét. A rendszer az eredményt az **InventCDSInventoryOnHandRequestEntity** és az **InventCDSInventoryOnHandEntryEntity** táblákban tárolja, majd Dataverse kettős írással írja. A funkció használatához a következő kettős írású leképezések futtatására van szükség. Hagyja ki a kezdeti szinkronizálást a leképezések futtatásakor.

- CDS aktuális készlettel kapcsolatos bejegyzések (msdyn_inventoryonhandentries)
- CDS aktuális készlettel kapcsolatos kérések (msdyn_inventoryonhandrequests)

## <a name="templates"></a>Sablonok
Az aktuális készletadatok közzététele érdekében a következő sablonok állnak rendelkezésre.

Finance and Operations-alkalmazásoknak | Customer Engagement alkalmazás | Leírás 
---|---|---
[Aktuális bejegyzések CDS-készlete](#145) | msdyn_inventoryonhandentries |
[CDS-készlet aktuális kérelmei](#147) | msdyn_inventoryonhandrequests |

[!include [banner](../../includes/dual-write-symbols.md)]

###  <a name="cds-inventory-on-hand-entries-msdyn_inventoryonhandentries"></a><a name="145"></a>CDS aktuális készlettel kapcsolatos bejegyzések (msdyn_inventoryonhandentries)

Ez a sablon szinkronizálja az adatokat az Finance and Operations alkalmazások és a(z) Dataverseközött.

Finance and Operations mező | Térkép típusa | Customer Engagement mező | Alapértelmezett érték
---|---|---|---
`REQUESTID` | = | `msdyn_request.msdyn_requestid` |
`INVENTORYSITEID` | = | `msdyn_inventorysite.msdyn_siteid` |
`INVENTORYWAREHOUSEID` | = | `msdyn_inventorywarehouse.msdyn_warehouseidentifier` |
`AVAILABLEONHANDQUANTITY` | > | `msdyn_availableonhandquantity` |
`AVAILABLEORDEREDQUANTITY` | > | `msdyn_availableorderedquantity` |
`ONHANDQUANTITY` | > | `msdyn_onhandquantity` |
`ONORDERQUANTITY` | > | `msdyn_onorderquantity` |
`ORDEREDQUANTITY` | > | `msdyn_orderedquantity` |
`RESERVEDONHANDQUANTITY` | > | `msdyn_reservedonhandquantity` |
`RESERVEDORDEREDQUANTITY` | > | `msdyn_reservedorderedquantity` |
`TOTALAVAILABLEQUANTITY` | > | `msdyn_totalavailablequantity` |
`ATPDATE` | = | `msdyn_atpdate` |
`ATPQUANTITY` | > | `msdyn_atpquantity` |
`PROJECTEDISSUEQUANTITY` | > | `msdyn_projectedissuequantity` |
`PROJECTEDONHANDQUANTITY` | > | `msdyn_projectedonhandquantity` |
`PROJECTEDRECEIPTQUANTITY` | > | `msdyn_projectedreceiptquantity` |
`ORDERQUANTITY` | > | `msdyn_orderquantity` |
`UNAVAILABLEONHANDQUANTITY` | > | `msdyn_unavailableonhandquantity` |

###  <a name="cds-inventory-on-hand-requests-msdyn_inventoryonhandrequests"></a><a name="147"></a>CDS aktuális készlettel kapcsolatos kérések (msdyn_inventoryonhandrequests)

Ez a sablon szinkronizálja az adatokat az Finance and Operations alkalmazások és a(z) Dataverseközött.

Finance and Operations mező | Térkép típusa | Customer Engagement mező | Alapértelmezett érték
---|---|---|---
`REQUESTID` | = | `msdyn_requestid` |
`PRODUCTNUMBER` | < | `msdyn_product.msdyn_productnumber` |
`ISATPCALCULATION` | << | `msdyn_isatpcalculation` |
`ORDERQUANTITY` | < | `msdyn_orderquantity` |
`INVENTORYSITEID` | < | `msdyn_inventorysite.msdyn_siteid` |
`INVENTORYWAREHOUSEID` | < | `msdyn_inventorywarehouse.msdyn_warehouseidentifier` |
`REFERENCENUMBER` | < | `msdyn_referencenumber` |
`LINECREATIONSEQUENCENUMBER` | < | `msdyn_linecreationsequencenumber` |






[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]