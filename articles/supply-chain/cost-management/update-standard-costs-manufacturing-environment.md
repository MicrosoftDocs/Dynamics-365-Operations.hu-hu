---
title: Az elszámolóár frissítése gyártási környezetben
description: A cikk az elszámolóárak gyártási környezetben történő frissítésének útmutatását tartalmazza.
author: JennySong-SH
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CostingVersion, InventStdCostConv
audience: Application User
ms.reviewer: kamaybac
ms.custom: 79663
ms.assetid: 3a7c3d13-8dbc-442d-a281-ac0ebe99ec83
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yanansong
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8acbcb79fa45ea2f225775068e0d061a44cba1f7
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/03/2022
ms.locfileid: "8675235"
---
# <a name="update-standard-costs-in-a-manufacturing-environment"></a>Az elszámolóár frissítése gyártási környezetben

[!include [banner](../includes/banner.md)]

A cikk az elszámolóárak gyártási környezetben történő frissítésének útmutatását tartalmazza. 

A frissítések visszajelzést adhatnak az új cikkekről, költségkategóriákról vagy közvetett költségszámítási képletekről. Visszatükrözhetik a korrekciókat és a költségváltozásokat. A frissítés típusa kihatással van az önköltségi árak frissítéséhez szükséges lépésekre, amint azt az alábbi esetek bemutatják:

-   A várható önköltségiár-változások megadása az alapanyagoknál, majd a megfelelő dátumnál a cikkek költségrekordjainak átállítása **Aktív** állapotra. Azonban nem számolják újra az alapanyagokat felhasználó termékek költségeit.
-   Egy új alapanyag önköltségi árának megadása, de nem történik meg az olyan termékek költségeinek újraszámítása, amelyek olyan anyagjegyzék-verzióval rendelkeznek, amelyben összetevőként szerepel az új alapanyag.
-   Egy alapanyag költségének helyesbítése vagy megváltoztatása, vagy egy alapanyag költségcsoportjának megváltoztatása, és a termékek költségeinek újraszámítása egy olyan anyagjegyzék-verzióval rendelkezik, amelyben az alapanyag összetevőként szerepel.
-   Egy költségkategóriához tartozó költség megváltoztatása, és az összes olyan gyártott cikk, amely egy olyan útvonalverzióval rendelkezik, amely ezt a költségkategóriát használó útvonalműveleteket tartalmazza.
-   Az útvonalműveletekhez rendelt költségkategóriák vagy a költségkategóriákhoz rendelt költségcsoport megváltoztatása. Számítsa ki az összes gyártott cikkre vonatkozó költséget, amely rendelkezik egy olyan útvonalverzióval, amelyben szerepelnek a költségkategóriákat használó útvonalműveletek.
-   Egy közvetett költségszámítási képlet megváltoztatása, és a változtatás által érintett termékek költségeinek újraszámítása.
-   Egy termékgyártási hely megváltoztatása vagy hozzáadása, és a cikk helyi gyártási költségének kiszámítása.
-   Számítsa ki vagy számítsa újra a gyártott termékre vonatkozó költséget, számítsa újra az összes olyan gyártott termékre vonatkozó költséget, amely rendelkezik olyan anyagjegyzék-verzióval, amely a gyártott termékeket összetevőkként tartalmazza.
-   Számítsa ki az új gyártott termék költségeit, annak meghatározott, jóváhagyott és aktív anyagjegyzék és útvonal-információi alapján.

Minden egyes eset gondos odafigyelést igényel, amikor az önköltségi árak frissítésére kerül sor.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]