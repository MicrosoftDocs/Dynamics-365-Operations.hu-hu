---
title: Készlet rendelkezésre állása kettős írásban
description: Ez a témakör a készlet rendelkezésre állásának ellenőrzéséről a kettős írásban tartalmaz tájékoztatást.
author: RamaKrishnamoorthy
ms.date: 05/26/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-05-26
ms.openlocfilehash: 175e1cc568ed027feee39eabfd9f08de6fe7f4b4
ms.sourcegitcommit: f65bde9ab0bf4c12a3250e7c9b2abb1555cd7931
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/13/2021
ms.locfileid: "6542637"
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

Finance and Operations alkalmazások | Customer Engagement alkalmazások     | Leírás
---|---|---
[Aktuális bejegyzések CDS-készlete](mapping-reference.md#145) | msdyn_inventoryonhandentries |
[CDS-készlet aktuális kérelmei](mapping-reference.md#147) | msdyn_inventoryonhandrequests |

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
