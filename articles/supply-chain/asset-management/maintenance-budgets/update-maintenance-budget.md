---
title: Karbantartási költségvetések frissítése
description: Ez a témakör leírja, hogyan lehet karbantartási költségvetést frissíteni az Eszközkezelésben.
author: josaw1
manager: AnnBe
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 8f3b771319eeb602a371500fdc69c68f88afe341
ms.sourcegitcommit: d37fb09101c30858bcb975931b3d8f947d72017b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/10/2019
ms.locfileid: "2571737"
---
# <a name="update-maintenance-budgets"></a><span data-ttu-id="1dbfc-103">Karbantartási költségvetések frissítése</span><span class="sxs-lookup"><span data-stu-id="1dbfc-103">Update maintenance budgets</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="1dbfc-104">A **Karbantartási költségvetés sorai** oldalon látható az összes költségvetési sor, amelyet a **Karbantartási költségvetések** oldalon kiválasztott költségvetéshez hoztak létre.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-104">The **Maintenance budget lines** page shows all the budget lines that have been created for the budget that is selected on the **Maintenance budgets** page.</span></span> <span data-ttu-id="1dbfc-105">(További információ a [Karbantartási költségvetések létrehozása](create-maintenance-budget.md) című témakörben olvasható.) A karbantartási költségvetés sorainak újraszámítása és helyesbítése a karbantartási költségvetés jóváhagyása előtt történik.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-105">(For more information, see [Create maintenance budgets](create-maintenance-budget.md).) You can recalculate and adjust maintenance budget lines until the maintenance budget is approved.</span></span> <span data-ttu-id="1dbfc-106">A költségvetési időszak lejártát követően és a költségek az Eszközkezelés modulban való feladása után a költségvetési sorokat frissítheti a tényleges költségekkel.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-106">After the budget period has passed, and costs have been posted in Asset Management, you can also update the budget lines with actual costs.</span></span>

## <a name="recalculate-a-maintenance-budget"></a><span data-ttu-id="1dbfc-107">Karbantartási költségvetés újraszámítása</span><span class="sxs-lookup"><span data-stu-id="1dbfc-107">Recalculate a maintenance budget</span></span>

<span data-ttu-id="1dbfc-108">A karbantartási költségvetéseket a **Karbantartás költségvetési sorok** lapon lehet újraszámítani.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-108">You can recalculate a maintenance budget on the **Maintenance budget lines** page.</span></span> <span data-ttu-id="1dbfc-109">A karbantartási költségvetés újraszámításakor a program törli a meglévő költségvetési sorokat, és új számítást végez.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-109">When you recalculate a maintenance budget, the existing budget lines are deleted, and a new calculation is done.</span></span>

1. <span data-ttu-id="1dbfc-110">A **Karbantartási költségvetési sorok** lapon válassza az **Újraszámítás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-110">On the **Maintenance budget lines** page, select **Recalculate**.</span></span>
2. <span data-ttu-id="1dbfc-111">A **Költségvetés újraszámítása** párbeszédpanelen végezze el az új számításhoz szükséges módosításokat, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-111">In the **Recalculate budget** dialog box, make the required changes for the new calculation, and then select **OK**.</span></span>

<span data-ttu-id="1dbfc-112">Az új költségvetési sorok a beállított értékek alapján jönnek létre.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-112">New budget lines are created according to the values that you set.</span></span>

## <a name="adjust-budget-lines"></a><span data-ttu-id="1dbfc-113">Költségvetési sorok kiigazítása</span><span class="sxs-lookup"><span data-stu-id="1dbfc-113">Adjust budget lines</span></span>

<span data-ttu-id="1dbfc-114">A teljes karbantartási költségvetés újraszámítása helyett a költségvetési költségekkel kapcsolatos kiválasztott sorok is módosíthatók.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-114">Instead of recalculating the whole maintenance budget, you can adjust selected lines that are related to budget costs.</span></span>

1. <span data-ttu-id="1dbfc-115">A **Karbantartási költségvetési sorok** lapon válassza ki azokat a sorokat, amelyekhez módosítani szeretné a költségvetési költséget.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-115">On the **Maintenance budget lines** page, select the lines to update the budget cost for.</span></span>
2. <span data-ttu-id="1dbfc-116">Válassza ki a **Módosítás** parancsot.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-116">Select **Adjust**.</span></span>
3. <span data-ttu-id="1dbfc-117">Ha hozzá szeretne adni egy összeget a kiválasztott sorokhoz, válassza a **Költség hozzáadása** jelölőnégyzetet, majd adja meg az értéket az **Érték hozzáadása** mezőben.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-117">To add an amount to the selected lines, select the **Add cost** check box, and then enter the value in the **Add value** field.</span></span>
4. <span data-ttu-id="1dbfc-118">Ha a kiválasztott költségvetési sorokon a költségvetési sorokat egy szorzóval szeretné megszorozni, akkor válassza a **Költség megszorzása** jelölőnégyzetet, és adja meg a szorzót a **Szorzó értéke** mezőben.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-118">To multiply the budget cost on the selected budget lines by a factor, select the **Multiply cost** check box, and enter the factor in the **Multiply value** field.</span></span>

    <span data-ttu-id="1dbfc-119">Például, ha a **Szorzó értéke** mezőben megadja az **1,2** értéket, akkor a kiválasztott sorok költségvetési költségét 20%-kal növeli.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-119">For example, if you enter **1.2** in the **Multiply value** field, you increase the budget cost on the selected lines by 20 percent.</span></span> <span data-ttu-id="1dbfc-120">Ha a **0,7** értéket adja meg, akkor a költségvetési költséget a kiválasztott sorokban 30 százalékkal csökkenti.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-120">If you enter **0.7**, you reduce the budget cost on the selected lines by 30 percent.</span></span>

5. <span data-ttu-id="1dbfc-121">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-121">Select **OK**.</span></span>

<span data-ttu-id="1dbfc-122">A kiválasztott költségvetési sorok a 3. és 4. lépésben beállított értékek alapján frissülnek.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-122">The selected budget lines are updated according to the values that you set in step 3 or 4.</span></span>

## <a name="update-actual-costs"></a><span data-ttu-id="1dbfc-123">Tényleges költségek frissítése</span><span class="sxs-lookup"><span data-stu-id="1dbfc-123">Update actual costs</span></span>

<span data-ttu-id="1dbfc-124">Miután a költségvetési sorokhoz tartozó dátumok lejártak, és a tényleges költségeket feladták az Eszközkezelésben, frissítheti a tényleges költségeket a karbantartási költségvetésen.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-124">After the dates on the budget lines have passed, and actual costs have been posted in Asset Management, you can update the actual costs on the maintenance budget.</span></span>

1. <span data-ttu-id="1dbfc-125">A **Karbantartási költségvetési sorok** lapon válassza a **Költség frissítése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-125">On the **Maintenance budget lines** page, select **Update cost**.</span></span>
2. <span data-ttu-id="1dbfc-126">A **Tényleges költség számítása** párbeszédpanelen válassza az **OK** gombot.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-126">In the **Calculate actual cost** dialog box, select **OK**.</span></span>

<span data-ttu-id="1dbfc-127">A rendszer frissíti a költségvetési sorok **Tényleges költség** mezőit, ha a tényleges költségeket feladták.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-127">The **Actual cost** fields on the budget lines are updated if actual costs have been posted.</span></span> <span data-ttu-id="1dbfc-128">Új költségvetési sorok jöhetnek létre, ha a költségvetés létrehozása óta új eszköztípusokat hoztak létre, és ha ezeket az eszköztípusokat olyan eszközökhöz használták, amelyekhez munkarendeléseket hoztak létre, és kapcsolódó költségeket adtak fel.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-128">New budget lines might be generated if new asset types have been created since you created the budget, and if those asset types have been used on assets that work orders have been created for and related costs have been posted for.</span></span> <span data-ttu-id="1dbfc-129">Az új költségvetési sorok csak a tényleges költségeket jelenítik meg, mivel a program nem számított költségvetési költséget.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-129">New budget lines show only actual costs, because no budget costs were calculated for them.</span></span>

> [!NOTE]
> <span data-ttu-id="1dbfc-130">Ha a tényleges költségeket megelőző, helyesbítő és befektetési költségekre bontva szeretné áttekinteni, ugyanarra az időszakra vonatkozóan számítást végezhet az **Eszköz költségkontrollja** oldalon.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-130">To see an overview of actual costs divided into preventive, corrective, and investment costs, you can do a calculation for the same period on the **Asset cost control** page.</span></span> 

## <a name="manually-add-budget-lines"></a><span data-ttu-id="1dbfc-131">Költségvetési sorok manuális hozzáadása</span><span class="sxs-lookup"><span data-stu-id="1dbfc-131">Manually add budget lines</span></span>

<span data-ttu-id="1dbfc-132">A **Karbantartási költségvetési sorok** lapon az új költségvetési sort manuálisan is hozzáadhatja, ha az **új** lehetőséget választja, majd elvégzi a megfelelő kiválasztásokat a soron.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-132">On the **Maintenance budget lines** page, you can manually add a new budget line by selecting **New** and then making selections on the line.</span></span> <span data-ttu-id="1dbfc-133">Néhány példa az olyan esetekre, amikor ez a megközelítés hasznos lehet:</span><span class="sxs-lookup"><span data-stu-id="1dbfc-133">Here are some examples of situations where this approach might be useful:</span></span>

- <span data-ttu-id="1dbfc-134">Ha tudja, hogy bizonyos eszközök felújítása jelenleg a tervezési fázisban van, de a kapcsolódó feladatok még nem lettek létrehozva az Eszközkezelés modulban.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-134">You know that refurbishment of some assets is currently in the planning phase, but related jobs haven't yet been created in Asset Management.</span></span> <span data-ttu-id="1dbfc-135">Azonban azt szeretné, hogy ezen feladatok költségvetési költségei szerepeljenek a karbantartási költségvetésben.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-135">However, you want budget costs for those jobs to be included in the maintenance budget.</span></span>
- <span data-ttu-id="1dbfc-136">Új eszközöket vagy eszköztípusokat hoztak létre, mióta létrehozta a karbantartási költségvetést, de ezekhez az eszközökhöz vagy eszköztípusokhoz még nem állították be a karbatartási terveket.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-136">New assets or asset types have been created since you made the maintenance budget, but maintenance plans haven't yet been set up on those assets or asset types.</span></span> <span data-ttu-id="1dbfc-137">Azonban azt szeretné, hogy ezen eszköztípusok költségvetési költségei szerepeljenek a karbantartási költségvetésben.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-137">However, you want budget costs for those asset types to be included in the maintenance budget.</span></span>
