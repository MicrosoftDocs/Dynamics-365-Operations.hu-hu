---
title: "Költségvetés-tervezési adatfelosztás"
description: "A cikk ismerteti a Microsoft Dynamics 365 for Finance and Operations rendszerben elérhető különféle felosztási módszereket, és bemutatja azok használatát."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BudgetPlanningConfiguration
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 15191
ms.assetid: 89a918e8-59a4-4711-a2e9-b41989ddd0f1
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 20dd11ad8b632de279855c1641f7bdeddb33cb4b
ms.contentlocale: hu-hu
ms.lasthandoff: 05/08/2018

---

# <a name="budget-planning-data-allocation"></a><span data-ttu-id="dfde4-103">Költségvetés-tervezés – adatok megadása</span><span class="sxs-lookup"><span data-stu-id="dfde4-103">Budget planning data allocation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="dfde4-104">A cikk ismerteti a Microsoft Dynamics 365 for Finance and Operations rendszerben elérhető különféle felosztási módszereket, és bemutatja azok használatát.</span><span class="sxs-lookup"><span data-stu-id="dfde4-104">This article describes the various allocation methods that are available in Microsoft Dynamics 365 for Finance and Operations and how they can be used.</span></span>  

<span data-ttu-id="dfde4-105">A költségvetési tervben számos módon eloszthatja az adatokat a tervezett összegek pontos megjelenítése érdekében.</span><span class="sxs-lookup"><span data-stu-id="dfde4-105">You can distribute the data in a budget plan in a number of ways to accurately portray the projected amounts.</span></span>

## <a name="allocation-methods"></a><span data-ttu-id="dfde4-106">Felosztási mód</span><span class="sxs-lookup"><span data-stu-id="dfde4-106">Allocation methods</span></span>
<span data-ttu-id="dfde4-107">Háromféle felosztási móddal (időszakok közötti felosztás, felosztás dimenziókra és főkönyvi felosztási szabályok használata) hozhat létre sorokat a költségvetésben; ezek az azonos költségvetési tervben lévő sorokra épülnek.</span><span class="sxs-lookup"><span data-stu-id="dfde4-107">Three allocation methods (Allocate across periods, Allocate to dimensions, and Use ledger allocation rules) can create budget plan lines that are based on lines in the same budget plan.</span></span> <span data-ttu-id="dfde4-108">Más költségvetési tervekben a költségvetésiterv-sorokat három másik módon (összesítés, felosztás és másolás a költségvetési tervből) hozhatja létre.</span><span class="sxs-lookup"><span data-stu-id="dfde4-108">Three other methods (Aggregate, Distribute, and Copy from budget plan) can create budget plan lines in other budget plans.</span></span> <span data-ttu-id="dfde4-109">Mind a hat felosztási mód esetén Ön határozza meg a felosztási célváltozatot.</span><span class="sxs-lookup"><span data-stu-id="dfde4-109">For all six allocation methods, you specify the destination scenario.</span></span> <span data-ttu-id="dfde4-110">A célváltozat megegyezhet a forrásváltozattal, de el is térhet attól.</span><span class="sxs-lookup"><span data-stu-id="dfde4-110">The destination scenario can be either the same as the source scenario or different from the source scenario.</span></span> <span data-ttu-id="dfde4-111">Ezenkívül megadhatja, hogy az új sorokat a rendszer hozzárendelje a költségvetési tervhez, vagy cserélje az aktuális sorokat.</span><span class="sxs-lookup"><span data-stu-id="dfde4-111">Additionally, you can specify whether new lines are appended to the budget plan or replace the current lines in the budget plan.</span></span>

<span data-ttu-id="dfde4-112">[![AllocateAcrossPeriods](./media/allocateacrossperiods-300x259.png)](./media/allocateacrossperiods.png)
**Időszakok közötti felosztás** – A költségvetési terv sorait a költségvetési forrás tervváltozatából időszaki felosztókategória segítségével oszthatja fel a célváltozat pénzügyi időszakai között.</span><span class="sxs-lookup"><span data-stu-id="dfde4-112">[![AllocateAcrossPeriods](./media/allocateacrossperiods-300x259.png)](./media/allocateacrossperiods.png)
**Allocate across periods** – A period allocation category is used to allocate the budget plan lines from the source budget plan scenario across periods in the destination scenario.</span></span> <span data-ttu-id="dfde4-113">A forrásösszeget a rendszer több sorhoz is hozzárendeli a célváltozatban az időszaki felosztókategóriában meghatározott százalék és dátumon szerint.</span><span class="sxs-lookup"><span data-stu-id="dfde4-113">The source amount is assigned to multiple lines in the destination scenario, based on the percentage and date that are defined in the period allocation category.</span></span>         

<span data-ttu-id="dfde4-114">[![AllocateToDimensions](./media/allocatetodimensions.jpg)](./media/allocatetodimensions.jpg)
**Felosztás dimenziókra** – A költségvetési terv sorai a költségvetési forrás tervváltozatából a célváltozat pénzügyi sorai között kerülnek felosztásra a kiválasztott költségvetés-felosztási feltételben meghatározott százalékok és pénzügyi dimenziók alapján.</span><span class="sxs-lookup"><span data-stu-id="dfde4-114">[![AllocateToDimensions](./media/allocatetodimensions.jpg)](./media/allocatetodimensions.jpg)
**Allocate to dimensions** – The budget plan lines are allocated from the source budget planning scenario to one or more lines in the destination scenario, based on the percentages and financial dimensions that are defined in a selected budget allocation term.</span></span>           

<span data-ttu-id="dfde4-115">![AggregateChart](./media/aggregatechart-300x230.png)
**Összesítés** – A költségvetési terv sorai a szülő költségvetési terv költségvetési forrás tervváltozatából a társított (gyermek) költségvetési terv célváltozatában kerülnek összesítésre.</span><span class="sxs-lookup"><span data-stu-id="dfde4-115">![AggregateChart](./media/aggregatechart-300x230.png)
**Aggregate** – The budget plan lines are aggregated from the source budget plan scenario in the associated (child) budget plans to the destination scenario in the parent budget plan.</span></span> <span data-ttu-id="dfde4-116">Ezzel a módszerrel a szervezet alsóbb szintjein elkészített költségvetési összegek magasabb szinten is konszolidálhatók.</span><span class="sxs-lookup"><span data-stu-id="dfde4-116">This method enables budget amounts that are prepared at a lower level in the organization to be consolidated at a higher level.</span></span>          

<span data-ttu-id="dfde4-117">[![DistributeChart](./media/distributechart-300x230.png)](./media/distributechart.png)
**Felosztás** – A költségvetési terv sorai a szülő költségvetési terv költségvetési forrás tervváltozatából kerülnek felosztásra a társított (gyermek) költségvetési tervek célváltozatával a társított tervek szervezetének pénzügyi dimenziói alapján.</span><span class="sxs-lookup"><span data-stu-id="dfde4-117">[![DistributeChart](./media/distributechart-300x230.png)](./media/distributechart.png)
**Distribute** – The budget plan lines are distributed from the source budget planning scenario in the parent budget plan to the destination scenario in the associated (child) budget plans, based on the financial dimensions of the organization units of the associated plans.</span></span> <span data-ttu-id="dfde4-118">Ezzel a módszerrel a szervezet magasabb szintjén elkészített költségvetési összegeket lokalizáltabb ellenőrzésre terjesztheti szét.</span><span class="sxs-lookup"><span data-stu-id="dfde4-118">This method enables budget amounts that are prepared at a higher level in the organization to be spread out for more localized review.</span></span>           

<span data-ttu-id="dfde4-119">[![LedgerAllocationRules](./media/ledgerallocationrules-300x202.png)](./media/ledgerallocationrules.png)
**Főkönyvi felosztási szabályok használata** – A költségvetési terv sorai a forrás költségvetési tervváltozat soraiból a kiválasztott főkönyvi felosztásszabály alapján a cél költségvetési tervváltozatba kerülnek felosztásra.</span><span class="sxs-lookup"><span data-stu-id="dfde4-119">[![LedgerAllocationRules](./media/ledgerallocationrules-300x202.png)](./media/ledgerallocationrules.png)
**Use ledger allocation rules** – The budget plan lines are distributed from the source budget planning scenario to the destination scenario, based on the ledger allocation rule that is selected.</span></span> 

<span data-ttu-id="dfde4-120">[![CopyFromBudgetPlan](./media/copyfrombudgetplan-187x300.png)](./media/copyfrombudgetplan.png)
**Másolás a költségvetési tervből** – A Felosztási mód elosztása eljáráshoz hasonlóan a költségvetési terv sorainak létrehozása itt is a célban történik a kapcsolódó költségvetési terv sorai alapján.</span><span class="sxs-lookup"><span data-stu-id="dfde4-120">[![CopyFromBudgetPlan](./media/copyfrombudgetplan-187x300.png)](./media/copyfrombudgetplan.png)
**Copy from budget plan** – As in the Distribute allocation method, budget plan lines are created in the destination, based on lines in a related budget plan.</span></span> <span data-ttu-id="dfde4-121">Ehhez a módszerhez ugyanakkor a forrás költségvetési tervnek nem muszáj szülőnek lenni, de lehet magasabban a hierarchiában.</span><span class="sxs-lookup"><span data-stu-id="dfde4-121">However, for this method, the source budget plan doesn't have to be the parent but can be at any higher level in the budget plan hierarchy.</span></span> <span data-ttu-id="dfde4-122">Ez a felosztási mód akkor hasznos, ha a konszolidált összegeket eredetileg jóval magasabb szinten irányozták elő, és azokat át kell adni a szervezet alacsonyabb szintjeire is részletes ellenőrzésre és kiigazításra a magasabb szintű jóváhagyás előtt.</span><span class="sxs-lookup"><span data-stu-id="dfde4-122">This allocation method is useful if consolidated amounts are originally budgeted at a much higher level, and must be transferred to a lower level of the organization for detailed review and adjustment before they can receive upper-level approval.</span></span>          

## <a name="using-allocation-methods-in-a-budget-plan"></a><span data-ttu-id="dfde4-123">Felosztási módszerek használata a költségvetési tervben</span><span class="sxs-lookup"><span data-stu-id="dfde4-123">Using allocation methods in a budget plan</span></span>
<span data-ttu-id="dfde4-124">Ha felosztásokat szeretne végrehajtani a költségvetési terv lapon, válassza ki a felosztani kívánt sorokat, majd kattintson a **Költségvetés felosztása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="dfde4-124">To perform allocations on the budget plan page, select the lines to allocate, and then click **Allocate budget**.</span></span>

<span data-ttu-id="dfde4-125">[![AllocateBudgetButton](./media/allocatebudgetbutton-300x84.png)](./media/allocatebudgetbutton.png)</span><span class="sxs-lookup"><span data-stu-id="dfde4-125">[![AllocateBudgetButton](./media/allocatebudgetbutton-300x84.png)](./media/allocatebudgetbutton.png)</span></span> 

<span data-ttu-id="dfde4-126">Ezután válasszon egy felosztási módszert.</span><span class="sxs-lookup"><span data-stu-id="dfde4-126">Next, select an allocation method.</span></span> <span data-ttu-id="dfde4-127">A többi mezőt a rendszer ezután a kiválasztott módszer alapján állítja be.</span><span class="sxs-lookup"><span data-stu-id="dfde4-127">The remaining fields are then set, based on the method that you selected.</span></span> <span data-ttu-id="dfde4-128">Ezekben a mezőkben található a költségvetési terv adatainak forrása és célja, valamint egy beállítás, amellyel megadott tényezővel szorozhatja meg a forrást a célösszegek létrehozásakor a tömeges kiigazítás megkönnyítése érdekében.</span><span class="sxs-lookup"><span data-stu-id="dfde4-128">These fields include the source and destination of the budget plan data, and an option that lets you multiply the source by a specified factor when the destination amounts are created, to simplify bulk adjustment.</span></span> <span data-ttu-id="dfde4-129">Ezenfelül beállíthatja a **Hozzáfűzés tervhez** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="dfde4-129">You can also set the **Append to plan** option.</span></span> <span data-ttu-id="dfde4-130">A meglévő költségvetésiterv-sorok felülírásához válassza a **Nem**, azok megtartásához az **Igen** lehetőséget, majd adjon hozzá új sorokat a felosztott összegekhez.</span><span class="sxs-lookup"><span data-stu-id="dfde4-130">Select **No** to replace the existing budget plan lines, or select **Yes** to retain the existing budget plan lines and add new lines for the allocated amounts.</span></span>

## <a name="automating-allocations-during-a-workflow"></a><span data-ttu-id="dfde4-131">Felosztások automatizálása munkafolyamat során</span><span class="sxs-lookup"><span data-stu-id="dfde4-131">Automating allocations during a workflow</span></span>
<span data-ttu-id="dfde4-132">Egy hatékony funkciónak köszönhetően automatikusan elvégezheti a felosztások a költségvetés tervezési munkafolyamata részeként.</span><span class="sxs-lookup"><span data-stu-id="dfde4-132">One powerful feature enables allocations to be performed automatically as part of a budget planning workflow.</span></span> <span data-ttu-id="dfde4-133">Mikor a költségvetési terv halad a munkafolyamatban, megadott tervezési szakaszok esetén automatizált feladatok kezdeményezhetik a felosztást.</span><span class="sxs-lookup"><span data-stu-id="dfde4-133">As a budget plan moves through its workflow, automated tasks can invoke an allocation at a specified budget planning stage.</span></span> 

<span data-ttu-id="dfde4-134">Az automatikus felosztás beállításához először felosztási ütemezést kell létrehoznia a **Költségvetés-tervezési konfiguráció** oldalon.</span><span class="sxs-lookup"><span data-stu-id="dfde4-134">To set up automated allocation, you must first create an allocation schedule on the **Budget planning configuration** page.</span></span> <span data-ttu-id="dfde4-135">A felosztási ütemezés meghatározza az automatizált felosztás futtatása során használt felosztási módszert, valamint az egyes felosztási beállításokhoz tartozó értékeket (a leírásokért lásd az előző szakaszt).</span><span class="sxs-lookup"><span data-stu-id="dfde4-135">The allocation schedule defines the allocation method that will be used when the automated allocation is run, and the values of the various allocation options (see the previous section for descriptions).</span></span> 

<span data-ttu-id="dfde4-136">Ezután hozzon létre szakaszfelosztást a **Költségvetés-tervezési konfiguráció** oldalon.</span><span class="sxs-lookup"><span data-stu-id="dfde4-136">Next, you create a stage allocation on the **Budget planning configuration** page.</span></span> <span data-ttu-id="dfde4-137">A szakaszfelosztás felosztási ütemet rendel hozzá a költségvetés-tervezési munkafolyamathoz és szakaszhoz.</span><span class="sxs-lookup"><span data-stu-id="dfde4-137">The stage allocation assigns an allocation schedule to the budget planning workflow and stage.</span></span> 

<span data-ttu-id="dfde4-138">Végül hozzá kell adni egy automatizált feladatot a költségvetés-tervezési szakaszhoz a kívánt munkafolyamat-szakaszban.</span><span class="sxs-lookup"><span data-stu-id="dfde4-138">Finally, add an automated task for budget planning stage allocation at the desired workflow stage.</span></span> <span data-ttu-id="dfde4-139">A következő példában két költségvetés-tervezési szakaszfelosztás (pirossal jelölve) került a munkafolyamatba.</span><span class="sxs-lookup"><span data-stu-id="dfde4-139">In the following example, two budget planning stage allocations (outlined in red) have been inserted into the workflow.</span></span>

<span data-ttu-id="dfde4-140">[![BudgetPlanningStageAllocations](./media/budgetplanningstageallocations-300x300.png)](./media/budgetplanningstageallocations.png)</span><span class="sxs-lookup"><span data-stu-id="dfde4-140">[![BudgetPlanningStageAllocations](./media/budgetplanningstageallocations-300x300.png)](./media/budgetplanningstageallocations.png)</span></span>




