---
title: "Termelési rendelés költségbecslése"
description: "A cikk a termelési költségbecsléssel kapcsolatos információkról nyújt tájékoztatást. A termelési költségbecslések az előrevetített anyag- és kapacitásfelhasználás költségeivel kapcsolatos információkról nyújt információkat, amelyek a cikkek tervezett rendelésben megadott mennyiségeinek termelésekor merülnek fel."
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BOMCalcTrans, InventCostTrans, ProdCalcTrans, ProdTableJour, ProdTableListPage
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 80633
ms.assetid: b4625d10-c852-4fda-b718-79df458de0d4
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: fe938a0b728205da56aa006583c6be7a44537ff4
ms.contentlocale: hu-hu
ms.lasthandoff: 05/08/2018

---

# <a name="production-order-cost-estimation"></a><span data-ttu-id="62df0-104">Termelési rendelés költségbecslése</span><span class="sxs-lookup"><span data-stu-id="62df0-104">Production order cost estimation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="62df0-105">A cikk a termelési költségbecsléssel kapcsolatos információkról nyújt tájékoztatást.</span><span class="sxs-lookup"><span data-stu-id="62df0-105">This article provides information about production cost estimation.</span></span> <span data-ttu-id="62df0-106">A termelési költségbecslések az előrevetített anyag- és kapacitásfelhasználás költségeivel kapcsolatos információkról nyújt információkat, amelyek a cikkek tervezett rendelésben megadott mennyiségeinek termelésekor merülnek fel.</span><span class="sxs-lookup"><span data-stu-id="62df0-106">Production cost estimation provides the projected material and capacity consumption costs of producing an item in the planned production order quantity.</span></span> 

<span data-ttu-id="62df0-107">Miután létrehozta a termelési rendelés, meg kell becsülnie a termelési költségeik.</span><span class="sxs-lookup"><span data-stu-id="62df0-107">After you create a production order, you must estimate production costs.</span></span> <span data-ttu-id="62df0-108">A cél a cikk és a termelési ütemezésre vonatkozó útvonal-felhasználás megbecslése, mert ezek a becslések képezik a későbbi ütemezés és a termelési folyamatok alapját.</span><span class="sxs-lookup"><span data-stu-id="62df0-108">The purpose is to estimate item and route consumption for the production process, because these estimates are used as the basis for subsequent scheduling and production processes.</span></span>

## <a name="production-cost-estimation"></a><span data-ttu-id="62df0-109">Termelés költségbecslése</span><span class="sxs-lookup"><span data-stu-id="62df0-109">Production cost estimation</span></span>
<span data-ttu-id="62df0-110">A termelési költségek becslései a következő adatokon alapulnak:</span><span class="sxs-lookup"><span data-stu-id="62df0-110">Estimates of production costs are based on the following information:</span></span>

-   <span data-ttu-id="62df0-111">A termelési rendelés mennyisége</span><span class="sxs-lookup"><span data-stu-id="62df0-111">The quantity on the production order</span></span>
-   <span data-ttu-id="62df0-112">A termelési anyagjegyzékek (BOM) összetevői</span><span class="sxs-lookup"><span data-stu-id="62df0-112">The components on the production bills of materials (BOMs)</span></span>
-   <span data-ttu-id="62df0-113">Az útvonalműveletek a termelési útvonalon</span><span class="sxs-lookup"><span data-stu-id="62df0-113">The routing operations in the production route</span></span>
-   <span data-ttu-id="62df0-114">Az összetevőkre és műveletekre vonatkozó közvetett költségek</span><span class="sxs-lookup"><span data-stu-id="62df0-114">The indirect costs that apply to the components and operations</span></span>
-   <span data-ttu-id="62df0-115">Aktív költségek adatai a kiszámításának dátumaként</span><span class="sxs-lookup"><span data-stu-id="62df0-115">The active cost data as of the calculation date</span></span>

<span data-ttu-id="62df0-116">Ha a termelési anyagjegyzékben egy álsor cikk szerepel, a számítások jelzik az álsor összetevőit és útvonalműveleteit.</span><span class="sxs-lookup"><span data-stu-id="62df0-116">If there is a phantom line item on the production BOMs, the calculations reflect the phantom’s components and route operations.</span></span> <span data-ttu-id="62df0-117">Alkalmazhat feladatbecslést a becsült költségek újraszámítására annak érdekében, hogy azok frissített adatokat tükrözzenek.</span><span class="sxs-lookup"><span data-stu-id="62df0-117">You can use the estimation task to recalculate estimated costs so that they reflect updated information.</span></span> <span data-ttu-id="62df0-118">Például a frissített adat lehet a termelési rendelésben szereplő mennyiségre vonatkozó változó, a termelési anyagjegyzék összetevő, a termelési útvonal útvonalműveleteiben szereplő termelési útvonal, az összetevőkre és műveletekre vonatkozó közvetett költség vagy az újraszámítási dátumként megjelenő aktív költség adat.</span><span class="sxs-lookup"><span data-stu-id="62df0-118">For example, the updated information might be changes to the quantity on the production order, the components on the production BOMs, the routing operations in the production route, the indirect costs that apply to these components and operations, or the active cost data as of the recalculation date.</span></span> <span data-ttu-id="62df0-119">A becsültköltség-számítások a költség + árrés módszeren alapuló termelési cikk eladási árát is javasolják.</span><span class="sxs-lookup"><span data-stu-id="62df0-119">The calculations of estimated cost also suggest a sales price for the production item, based on a cost-plus-markup approach.</span></span> <span data-ttu-id="62df0-120">A becsültköltség-számítások igény szerint vonatkozhatnak hivatkozási rendelésekre is, amelyek a termelési rendeléshez kapcsolódó többi termelési rendeléseket tükrözik.</span><span class="sxs-lookup"><span data-stu-id="62df0-120">The calculations of estimated cost can optionally apply to reference orders that reflect other production orders that are linked to the production order.</span></span>

## <a name="view-the-estimated-costs"></a><span data-ttu-id="62df0-121">A becsült költségek megtekintése</span><span class="sxs-lookup"><span data-stu-id="62df0-121">View the estimated costs</span></span>
<span data-ttu-id="62df0-122">Becslés futtatása után megtekintheti az eredményeket az **Árkalkuláció** lapon.</span><span class="sxs-lookup"><span data-stu-id="62df0-122">After you run estimation, you can view the results on the **Price calculation** page.</span></span> <span data-ttu-id="62df0-123">A becslés következő értékeket számítja ki:</span><span class="sxs-lookup"><span data-stu-id="62df0-123">The estimation calculates the following values:</span></span>

-   <span data-ttu-id="62df0-124">**Termelési költség** – A termelési költség a becslés legfelső sora.</span><span class="sxs-lookup"><span data-stu-id="62df0-124">**Production cost** – The production cost is the top line of the estimate.</span></span> <span data-ttu-id="62df0-125">Megjeleníti a termelési rendelés lefuttatásának teljes költségét és a termelés teljes eladási árát.</span><span class="sxs-lookup"><span data-stu-id="62df0-125">It shows the complete cost of running the production order and the total sales price for the production.</span></span> <span data-ttu-id="62df0-126">Ez az érték a becslésben szereplő összes költségsor összege.</span><span class="sxs-lookup"><span data-stu-id="62df0-126">It's the sum of all the cost lines on the estimate.</span></span>
-   <span data-ttu-id="62df0-127">**Útvonal vagy erőforrás költségek** – Az Útvonal vagy az erőforrás költségek a termelési műveletek költségei.</span><span class="sxs-lookup"><span data-stu-id="62df0-127">**Route or resource costs** – Route or resource costs are the costs for the production operations.</span></span> <span data-ttu-id="62df0-128">Az elemek költségét, csak úgy mint a beállítási időt, a lefutási időt és a többletköltséget tartalmazzák.</span><span class="sxs-lookup"><span data-stu-id="62df0-128">They include the cost of elements such as setup time, run time, and overhead.</span></span>
-   <span data-ttu-id="62df0-129">**Anyagköltségek** – Az Anyagköltségek a cikkek előállításához szükséges anyagjegyzék-összetevők költségei és árai.</span><span class="sxs-lookup"><span data-stu-id="62df0-129">**Material costs** – Material costs are the costs and prices of the BOM components that are required in order to produce the item.</span></span> <span data-ttu-id="62df0-130">Ezeket a költségeket korábban létrehozták és rögzítették a rendszerben.</span><span class="sxs-lookup"><span data-stu-id="62df0-130">These costs have previously been established and entered into the system.</span></span>

## <a name="other-uses-of-cost-estimation"></a><span data-ttu-id="62df0-131">A költségbecslések egyéb felhasználási területei</span><span class="sxs-lookup"><span data-stu-id="62df0-131">Other uses of cost estimation</span></span>
<span data-ttu-id="62df0-132">A Költségbecslés a következő adatokat is tartalmazza:</span><span class="sxs-lookup"><span data-stu-id="62df0-132">A cost estimate also provides the following information:</span></span>

-   <span data-ttu-id="62df0-133">Megalapozott árajánlatok</span><span class="sxs-lookup"><span data-stu-id="62df0-133">Meaningful price quotations</span></span>
-   <span data-ttu-id="62df0-134">A rendelés nyereségességére vonatkozó becslések</span><span class="sxs-lookup"><span data-stu-id="62df0-134">Estimates of the profitability of the order</span></span>
-   <span data-ttu-id="62df0-135">Becslések a nyersanyag-felhasználásra vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="62df0-135">Estimates of raw material usage</span></span>
-   <span data-ttu-id="62df0-136">A korábbi termelésekből származó költségadatok összehasonlítása</span><span class="sxs-lookup"><span data-stu-id="62df0-136">Comparisons of cost information from previous productions</span></span>
-   <span data-ttu-id="62df0-137">Költségvetési és előrejelzési adatok.</span><span class="sxs-lookup"><span data-stu-id="62df0-137">Budget and forecasting information</span></span>
-   <span data-ttu-id="62df0-138">Az adott költségszint fenntartásához szükséges termelési mennyiség becslései.</span><span class="sxs-lookup"><span data-stu-id="62df0-138">Estimates of the production size that is required in order to maintain a particular cost</span></span>





