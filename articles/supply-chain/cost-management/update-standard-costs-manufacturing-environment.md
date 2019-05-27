---
title: Az elszámolóár frissítése gyártási környezetben
description: A cikk az elszámolóárak gyártási környezetben történő frissítésének útmutatását tartalmazza.
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CostingVersion, InventStdCostConv
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 79663
ms.assetid: 3a7c3d13-8dbc-442d-a281-ac0ebe99ec83
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fccfcec3d74bd13aa1b6511ebd37ee1454d1b47b
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1563043"
---
# <a name="update-standard-costs-in-a-manufacturing-environment"></a><span data-ttu-id="86ca2-103">Az elszámolóár frissítése gyártási környezetben</span><span class="sxs-lookup"><span data-stu-id="86ca2-103">Update standard costs in a manufacturing environment</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="86ca2-104">A cikk az elszámolóárak gyártási környezetben történő frissítésének útmutatását tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="86ca2-104">This article provides guidance about how to update standard costs in a manufacturing environment.</span></span> 

<span data-ttu-id="86ca2-105">A frissítések visszajelzést adhatnak az új cikkekről, költségkategóriákról vagy közvetett költségszámítási képletekről.</span><span class="sxs-lookup"><span data-stu-id="86ca2-105">Updates can reflect new items, cost categories, or indirect cost calculation formulas.</span></span> <span data-ttu-id="86ca2-106">Visszatükrözhetik a korrekciókat és a költségváltozásokat.</span><span class="sxs-lookup"><span data-stu-id="86ca2-106">They can also reflect corrections and cost changes.</span></span> <span data-ttu-id="86ca2-107">A frissítés típusa kihatással van az önköltségi árak frissítéséhez szükséges lépésekre, amint azt az alábbi esetek bemutatják:</span><span class="sxs-lookup"><span data-stu-id="86ca2-107">The type of update affects the steps that you must complete to update standard costs, as illustrated in the following cases:</span></span>

-   <span data-ttu-id="86ca2-108">A várható önköltségiár-változások megadása az alapanyagoknál, majd a megfelelő dátumnál a cikkek költségrekordjainak átállítása **Aktív** állapotra.</span><span class="sxs-lookup"><span data-stu-id="86ca2-108">Enter expected standard cost changes for purchased items, and then change the status of the item cost records to **Active** on the appropriate date.</span></span> <span data-ttu-id="86ca2-109">Azonban nem számolják újra az alapanyagokat felhasználó termékek költségeit.</span><span class="sxs-lookup"><span data-stu-id="86ca2-109">However, don't recalculate the costs of manufactured items that use the purchased items.</span></span>
-   <span data-ttu-id="86ca2-110">Egy új alapanyag önköltségi árának megadása, de nem történik meg az olyan termékek költségeinek újraszámítása, amelyek olyan anyagjegyzék-verzióval rendelkeznek, amelyben összetevőként szerepel az új alapanyag.</span><span class="sxs-lookup"><span data-stu-id="86ca2-110">Enter standard costs for a new purchased item, but don't recalculate the costs of manufactured items that have a bill of materials (BOM) version that contains the new purchased item as a component.</span></span>
-   <span data-ttu-id="86ca2-111">Egy alapanyag költségének helyesbítése vagy megváltoztatása, vagy egy alapanyag költségcsoportjának megváltoztatása, és a termékek költségeinek újraszámítása egy olyan anyagjegyzék-verzióval rendelkezik, amelyben az alapanyag összetevőként szerepel.</span><span class="sxs-lookup"><span data-stu-id="86ca2-111">Correct or change the cost of a purchased item, or change the cost group that is assigned to a purchased item, and calculate the cost for all manufactured items that have a BOM version that contains the purchased item as a component.</span></span>
-   <span data-ttu-id="86ca2-112">Egy költségkategóriához tartozó költség megváltoztatása, és az összes olyan gyártott cikk, amely egy olyan útvonalverzióval rendelkezik, amely ezt a költségkategóriát használó útvonalműveleteket tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="86ca2-112">Change the cost for a cost category, and calculate the cost for all manufactured items that have a route version that contains routing operations that use the cost category.</span></span>
-   <span data-ttu-id="86ca2-113">Az útvonalműveletekhez rendelt költségkategóriák vagy a költségkategóriákhoz rendelt költségcsoport megváltoztatása.</span><span class="sxs-lookup"><span data-stu-id="86ca2-113">Change the cost categories that are assigned to routing operations or the cost group that is assigned to cost categories.</span></span> <span data-ttu-id="86ca2-114">Számítsa ki az összes gyártott cikkre vonatkozó költséget, amely rendelkezik egy olyan útvonalverzióval, amelyben szerepelnek a költségkategóriákat használó útvonalműveletek.</span><span class="sxs-lookup"><span data-stu-id="86ca2-114">Then calculate the cost for all manufactured items that have a route version that contains routing operations that use the cost category.</span></span>
-   <span data-ttu-id="86ca2-115">Egy közvetett költségszámítási képlet megváltoztatása, és a változtatás által érintett termékek költségeinek újraszámítása.</span><span class="sxs-lookup"><span data-stu-id="86ca2-115">Change an indirect cost calculation formula, and calculate the cost for all manufactured items that are affected by the change.</span></span>
-   <span data-ttu-id="86ca2-116">Egy termékgyártási hely megváltoztatása vagy hozzáadása, és a cikk helyi gyártási költségének kiszámítása.</span><span class="sxs-lookup"><span data-stu-id="86ca2-116">Change or add a manufacturing site for a manufactured item, and calculate the item's manufactured cost for the site.</span></span>
-   <span data-ttu-id="86ca2-117">Számítsa ki vagy számítsa újra a gyártott termékre vonatkozó költséget, számítsa újra az összes olyan gyártott termékre vonatkozó költséget, amely rendelkezik olyan anyagjegyzék-verzióval, amely a gyártott termékeket összetevőkként tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="86ca2-117">Calculate, or recalculate, the cost for a manufactured item, and recalculate the cost for all manufactured items that have a BOM version that contains the manufactured item as a component.</span></span>
-   <span data-ttu-id="86ca2-118">Számítsa ki az új gyártott termék költségeit, annak meghatározott, jóváhagyott és aktív anyagjegyzék és útvonal-információi alapján.</span><span class="sxs-lookup"><span data-stu-id="86ca2-118">Calculate costs for a new manufactured item, based on its defined, approved, and active BOM and route information.</span></span>

<span data-ttu-id="86ca2-119">Minden egyes eset gondos odafigyelést igényel, amikor az önköltségi árak frissítésére kerül sor.</span><span class="sxs-lookup"><span data-stu-id="86ca2-119">Each case requires careful consideration about how to update standard costs.</span></span>



