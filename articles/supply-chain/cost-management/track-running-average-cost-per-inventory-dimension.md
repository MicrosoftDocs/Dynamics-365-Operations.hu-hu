---
title: Mozgóátlagon alapuló önköltségi ár követése készletdimenziónként
description: Egy készletdimenzió-csoport minden készletcikkhez hozzá van kapcsolva. Ezért a cikk mozgóátlagon alapuló önköltségi árának számítása ennek megfelelően a pénzügyileg követett készletdimenziók beállításán alapul.
author: JennySong-SH
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventOnhandItem
audience: Application User
ms.reviewer: kamaybac
ms.custom: 75053
ms.assetid: 68cc00f4-0f7a-4a7d-be90-8f2e0d0563d3
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yanansong
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 186109774dbb2795911305ec0bb5b29c7a7a72d9
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/03/2022
ms.locfileid: "8669715"
---
# <a name="track-running-average-cost-per-inventory-dimension"></a>Mozgóátlagon alapuló önköltségi ár követése készletdimenziónként

[!include [banner](../includes/banner.md)]

Egy készletdimenzió-csoport minden készletcikkhez hozzá van kapcsolva. Ezért a cikk mozgóátlagon alapuló önköltségi árának számítása ennek megfelelően a pénzügyileg követett készletdimenziók beállításán alapul.

A készletdimenzióknak három típusa van: termék-, tárolási és nyomonkövetési. A készletdimenziók tartalmazzák a konfiguráció, a méret és a szín adatait. A termékdimenziókat minden esetben pénzügyileg nyomon követi a rendszer. A tárolási és nyomonkövetési dimenziók tartalmazzák a telephely, a raktár, a hely, a készletállapot, az azonosítótábla, a kötegszám, és a sorozatszám adatait. Ki lehet választani, hogy mely tárolási és nyomonkövetési dimenzióhoz történjen pénzügyi nyomon követés. 

**1. példa** 

Ha a cikkhez tartozó tárolási dimenzió-csoport raktár szerint van pénzügyileg nyomon követve, a mozgóátlagon alapuló önköltségi ár számítása raktáranként történik. A következő beszerzési rendelések számlázása történt meg:

-   2 darabos beszerzési rendelés számlázása a GW raktárhoz 10,00 USD önköltségi áron történt.
-   3 darabos beszerzési rendelés számlázása a GW raktárhoz 12,00 USD önköltségi áron történt.
-   5 darabos beszerzési rendelés számlázása az MW raktárhoz 15,00 USD önköltségi áron történt.

A GW raktárhoz a mozgóátlagon alapuló önköltségi ár 11,20 USD, és az MW raktárhoz a mozgóátlagon alapuló önköltségi ár 15,00 USD. A GW raktárhoz értékesítésirendelés-számlájának feladása. A készlet értéke és az eladott áruk beszerzési értéke (a készletzárás lefuttatása előtt, és a jelölés nélkül) 11,20 USD. Az MW raktárhoz egy további értékesítési rendelés feladása. A készlet értéke és az eladott áruk beszerzési értéke (a készletzárás lefuttatása előtt, és a jelölés nélkül) 15,00 USD. 

**2. példa** , ha a tárolásidimenzió-csoport, amelyhez a cikk kapcsolódik pénzügyileg nyomon van követve a raktár által, és a nyomon követési dimenziócsoport pénzügyileg nyomon van követve kötegszám szerint, a mozgóátlagon alapuló önköltségi ár minden egyes köteghez ki lesz számolva. 

**Megjegyzés:** Minden esetben ajánlott az önköltségi ár megtekintése az összes nyomon követett pénzügyi dimenzió esetében. A következő beszerzési rendelések számlázása történt meg:

-   2 darabos beszerzési rendelés számlázása a GW raktárhoz és az AAA adaghoz 10,00 USD önköltségi áron történt.
-   3 darabos beszerzési rendelés számlázása a GW raktárhoz és az AAA adaghoz 12,00 USD önköltségi áron történt.
-   2 darabos beszerzési rendelés számlázása a GW raktárhoz és az BBB adaghoz 15,00 USD önköltségi áron történt.

A GW raktárhoz és az AAA adaghoz a mozgóátlagon alapuló önköltségi ár 11,20 USD, és a GW raktárhoz és a BBB adaghoz a mozgóátlagon alapuló önköltségi ár 15,00 USD.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]