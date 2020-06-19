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
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: riluan
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-05-26
ms.openlocfilehash: dd0995eb8c70ed06cdc3c0f6a28b13b117297533
ms.sourcegitcommit: be7e4378c8122c6e7cfc4e7991efbdffee45e006
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2020
ms.locfileid: "3426982"
---
# <a name="inventory-availability"></a>Készlet elérhetősége

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

A készlet elérhetőségét használva ellenőrizheti a készletet, mielőtt terméket ad hozzá az **Ajánlatok**, **Rendelések** vagy **Számlák** űrlapokhoz a Dynamics 365 modellvezérelt alkalmazásaiban. Például a készlet ellenőrzése és a teljesítés dátuma egy kulcsfeladat a [potenciális vevők készpénzre váltása](dual-write-prospect-to-cash.md) folyamatban. Ha nincs elég készlete, megbecsülheti a várható szállítási dátumot az előrejelzett készletbevételezés és -kiadás alapján. Megtekintheti a termék ígérethez rendelkezésre áll információit is, ahol megtalálhatja az ígért mennyiséget az előre meghatározott időkorláton belül.

## <a name="on-hand-inventory"></a>Aktuális készlet 

A Dynamics 365 Sales **Ajánlatok**, **Rendelések** vagy **Számlák** űrlapjainak fejlécében egy új **Aktuális készlet** gomb jelenik meg. Amikor a gombra kattint, megjelenik egy párbeszédpanel, amelyen megadhatja azt a vállalatot és terméket, amelynek az aktuális készletét ellenőrizni szeretné. A rendszer a készletadatokat adja vissza a Dynamics 365 Supply Chain Management alkalmazásból, és ugyanazokat az információkat jeleníti meg, mint az [Aktuális készlet](../../../../supply-chain/inventory/tasks/check-availability-stock.md). Az adatok a következő mennyiségeket tartalmazzák:

- **Aktuális mennyiség**
- **Lefoglalt aktuális mennyiség**
- **Elérhető aktuális mennyiség**
- **Rendelt mennyiség**
- **Rendelésben lévő mennyiség**
- **Lefoglalt rendelt mennyiség**
- **Teljes elérhető mennyiség**

## <a name="atp-information"></a>Információk az ígérethez rendelkezésre álló készletről

A Dynamics 365 Sales **Ajánlatok**, **Rendelések** vagy **Számlák** űrlapjainak sorelemein egy új **Ígérethez rendelkezésre álló adatok** gomb jelenik meg. Amikor a gombra kattint, megjelenik egy párbeszédpanel, amelyen megadhatja a vállalatot, terméket, helyet, készletraktárat és rendelési mennyiséget. Az **Ígérethez rendelkezésre áll adatokat** adja vissza a Supply Chain Management alkalmazásból, és megjeleníti a [Rendelési ígéret](../../../../supply-chain/sales-marketing/delivery-dates-available-promise-calculations.md#atp-calculations) részben leírt beállításokat. Az adatok között szerepel az **Ígérethez rendelkezésre álló mennyiség**, **Bevételezett mennyiség**, **Kiadott mennyiség** és az **Aktuális készlet**.
