---
title: Készlet rendelkezésre állása kettős írásban
description: Ez a témakör a készlet rendelkezésre állásának ellenőrzéséről a kettős írásban tartalmaz tájékoztatást.
author: yijialuan
manager: AnnBe
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: riluan
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-05-26
ms.openlocfilehash: 4d1022eec633bf0a9edb4d5b26982853cec836d7
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4453403"
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
