---
title: "Az elszámolóár frissítése gyártási környezetben"
description: "A cikk az elszámolóárak gyártási környezetben történő frissítésének útmutatását tartalmazza."
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CostingVersion, InventStdCostConv
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 79663
ms.assetid: 3a7c3d13-8dbc-442d-a281-ac0ebe99ec83
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: b9ad13071c3e0c3a294e9d4413de160a58559640
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

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




