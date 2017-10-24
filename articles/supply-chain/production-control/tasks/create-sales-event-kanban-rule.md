--- 
title: "Az értékesítési esemény kanbanszabályának létrehozása"
description: "Ez az eljárás egy olyan kanbanszabály létrehozásához szükséges beállításokkal foglalkozik, amely az értékesítési rendelés létrehozásakor aktiválódik."
author: ChristianRytt
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: f1f66157b2e74ad1b490e10112cbc121ac9826fb
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-sales-event-kanban-rule"></a><span data-ttu-id="64bf0-103">Az értékesítési esemény kanbanszabályának létrehozása</span><span class="sxs-lookup"><span data-stu-id="64bf0-103">Create a sales event kanban rule</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="64bf0-104">Ez az eljárás egy olyan kanbanszabály létrehozásához szükséges beállításokkal foglalkozik, amely az értékesítési rendelés létrehozásakor aktiválódik.</span><span class="sxs-lookup"><span data-stu-id="64bf0-104">This procedure focuses on the setup needed to create a kanban rule that is triggered during sales order creation.</span></span> <span data-ttu-id="64bf0-105">Az esemény kanbanszabály eleget tesz azoknak a követelményeknek, amelyek az értékesítési rendelés soraiból származnak.</span><span class="sxs-lookup"><span data-stu-id="64bf0-105">The event kanban rule replenishes requirements that originate from sales order lines.</span></span> <span data-ttu-id="64bf0-106">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="64bf0-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="64bf0-107">Ez az eljárás a folyamatmérnök vagy az érték-előállítási vezető munkáját segíti, mert ők készítik elő az új vagy módosított termék termelését.</span><span class="sxs-lookup"><span data-stu-id="64bf0-107">It is intended for the process engineer or the value stream manager as they prepare production of a new or modified product.</span></span>




## <a name="create-a-new-kanban-rule"></a><span data-ttu-id="64bf0-108">Új kanbanszabály létrehozása</span><span class="sxs-lookup"><span data-stu-id="64bf0-108">Create a new kanban rule</span></span>
1. <span data-ttu-id="64bf0-109">Ugorjon a Kanbanszabályokhoz.</span><span class="sxs-lookup"><span data-stu-id="64bf0-109">Go to Kanban rules.</span></span>
2. <span data-ttu-id="64bf0-110">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="64bf0-110">Click New.</span></span>
3. <span data-ttu-id="64bf0-111">A Feltöltési stratégia mezőben válassza az „Esemény” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="64bf0-111">In the Replenishment strategy field, select 'Event'.</span></span>
    * <span data-ttu-id="64bf0-112">Az Esemény kiválasztása azt jelenti, hogy a kanbanszabályt egy esemény indítja el, például az értékesítési rendelés sor létrehozása.</span><span class="sxs-lookup"><span data-stu-id="64bf0-112">Selecting Event means that the kanban rule is triggered by an event, for example, creation of a sales order line.</span></span>   <span data-ttu-id="64bf0-113">Ez olyan területekre érvényes, ahol minden kanbanhoz adott igény tartozik.</span><span class="sxs-lookup"><span data-stu-id="64bf0-113">This is applied to areas where each kanban should cover a specific demand.</span></span>  
4. <span data-ttu-id="64bf0-114">Az Első tervezési tevékenység mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="64bf0-114">In the First plan activity field, enter or select a value.</span></span>
    * <span data-ttu-id="64bf0-115">Utolsó szerelvény kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="64bf0-115">Select Final assembly.</span></span>  
5. <span data-ttu-id="64bf0-116">A Részletek szakasz kibontása.</span><span class="sxs-lookup"><span data-stu-id="64bf0-116">Expand the Details section.</span></span>
6. <span data-ttu-id="64bf0-117">A Termék mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="64bf0-117">In the Product field, enter or select a value.</span></span>
    * <span data-ttu-id="64bf0-118">Válassza az L0050 lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="64bf0-118">Select L0050.</span></span>  

## <a name="define-an-event"></a><span data-ttu-id="64bf0-119">Határozzon meg egy eseményt</span><span class="sxs-lookup"><span data-stu-id="64bf0-119">Define an event</span></span>
1. <span data-ttu-id="64bf0-120">Bontsa ki a Események szakaszt.</span><span class="sxs-lookup"><span data-stu-id="64bf0-120">Expand the Events section.</span></span>
2. <span data-ttu-id="64bf0-121">Az Értékesítési események mezőben válassza az „Automatikus” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="64bf0-121">In the Sales event field, select 'Automatic'.</span></span>
    * <span data-ttu-id="64bf0-122">Ha az Automatikus értékesítési eseményt választja ki, ez a kanbanszabály automatikusan aktiválódik, ha az értékesítési sor egyedül a termék és a bevételezés helyéve.</span><span class="sxs-lookup"><span data-stu-id="64bf0-122">By selecting the sales event Automatic, this kanban rule will be triggered automatically when a sales line matches the product and receipt location.</span></span> <span data-ttu-id="64bf0-123">Ebben az eljárásban ez az L0050 termék a 13-as raktárban.</span><span class="sxs-lookup"><span data-stu-id="64bf0-123">In this procedure, it is product L0050 on warehouse 13.</span></span>  
3. <span data-ttu-id="64bf0-124">A minimális eseménymennyiséget állítsa „50” értékre.</span><span class="sxs-lookup"><span data-stu-id="64bf0-124">Set Minimum event quantity to '50'.</span></span>
    * <span data-ttu-id="64bf0-125">Az 50 minimális eseménymennyiséggel ez a kanbanszabály csak 50 vagy nagyobb mennyiségű események esetén aktiválódik.</span><span class="sxs-lookup"><span data-stu-id="64bf0-125">With a minimum event quantity of 50, the kanban rule will only be triggered by events with a quantity of 50 or more.</span></span>  
4. <span data-ttu-id="64bf0-126">Bontsa ki a Termelési folyamat szakaszt.</span><span class="sxs-lookup"><span data-stu-id="64bf0-126">Expand the Production flow section.</span></span>
    * <span data-ttu-id="64bf0-127">Láthatja, hogy a Bevételezési hely a 13-as raktárban van.</span><span class="sxs-lookup"><span data-stu-id="64bf0-127">Notice that the Receipt location is warehouse 13.</span></span> <span data-ttu-id="64bf0-128">Ez azt jelenti, hogy ez a kanbanszabály ehhez a helyhez aktiválódik.</span><span class="sxs-lookup"><span data-stu-id="64bf0-128">This means that this kanban rule will be triggered for this location.</span></span>  
    * <span data-ttu-id="64bf0-129">Ebben a példában az L0050 termék értékesítési sora az 50 vagy annál nagyobb mennyiséggel a 13-as raktárban aktiválni fogja ezt a kanbanszabályt.</span><span class="sxs-lookup"><span data-stu-id="64bf0-129">In this example, a sales line for product L0050, with a quantity of 50 or more, on warehouse 13, will trigger this kanban rule.</span></span>  

## <a name="create-sales-line-to-trigger-event-kanban-rule"></a><span data-ttu-id="64bf0-130">A kanbanszabály aktiválásához hozzon létre értékesítési sort</span><span class="sxs-lookup"><span data-stu-id="64bf0-130">Create sales line to trigger event kanban rule</span></span>
1. <span data-ttu-id="64bf0-131">Ugrás az összes értékesítési rendelésre.</span><span class="sxs-lookup"><span data-stu-id="64bf0-131">Go to All sales orders.</span></span>
    * <span data-ttu-id="64bf0-132">A kanbanszabály mentésekor egy figyelmeztetés jelenik meg, ami arra utal, hogy a kanbanok valós időben, az értékesítési rendelés létrehozásakor jönnek létre.</span><span class="sxs-lookup"><span data-stu-id="64bf0-132">A warning is shown when the kanban rule is saved, which means that kanbans will be created in real-time during sales order creation.</span></span>  
2. <span data-ttu-id="64bf0-133">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="64bf0-133">Click New.</span></span>
3. <span data-ttu-id="64bf0-134">A Vevőszámla mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="64bf0-134">In the Customer account field, enter or select a value.</span></span>
    * <span data-ttu-id="64bf0-135">Válassza ki például az US-003-at.</span><span class="sxs-lookup"><span data-stu-id="64bf0-135">For example, select US-003.</span></span>  
4. <span data-ttu-id="64bf0-136">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="64bf0-136">Click OK.</span></span>
5. <span data-ttu-id="64bf0-137">A Cikkszám mezőbe írja be az „L0050” értéket.</span><span class="sxs-lookup"><span data-stu-id="64bf0-137">In the Item number field, type 'L0050'.</span></span>
6. <span data-ttu-id="64bf0-138">A Hely mezőbe írja be az „1” értéket.</span><span class="sxs-lookup"><span data-stu-id="64bf0-138">In the Site field, type '1'.</span></span>
    * <span data-ttu-id="64bf0-139">Válassza az 1 Helyet, mert a 13-as raktár az 1 Helyen van.</span><span class="sxs-lookup"><span data-stu-id="64bf0-139">Select Site 1 because Warehouse 13 is on Site 1.</span></span>  
7. <span data-ttu-id="64bf0-140">A Raktár mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="64bf0-140">In the Warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="64bf0-141">Állítsa be a 13-as raktárat.</span><span class="sxs-lookup"><span data-stu-id="64bf0-141">Set Warehouse to 13.</span></span>  
8. <span data-ttu-id="64bf0-142">Állítsa a mennyiséget 75 értékre.</span><span class="sxs-lookup"><span data-stu-id="64bf0-142">Set Quantity to '75'.</span></span>
    * <span data-ttu-id="64bf0-143">Írja be az 50-et vagy egy annál nagyobb mennyiséget, hogy a kanbanszabály aktiválódjon.</span><span class="sxs-lookup"><span data-stu-id="64bf0-143">Enter a quantity of 50 or greater, to trigger the created kanban rule.</span></span>  

## <a name="verify-that-kanban-is-created"></a><span data-ttu-id="64bf0-144">Győződjön meg róla, hogy a kanban létrehozása megtörtént</span><span class="sxs-lookup"><span data-stu-id="64bf0-144">Verify that kanban is created</span></span>
1. <span data-ttu-id="64bf0-145">Kattintson a Termék és készlet menüpontra.</span><span class="sxs-lookup"><span data-stu-id="64bf0-145">Click Product and supply.</span></span>
2. <span data-ttu-id="64bf0-146">Az igénykövetési fa megtekintése lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="64bf0-146">Click View pegging tree.</span></span>
    * <span data-ttu-id="64bf0-147">Figyelje meg, hogy a kanban mennyisége azonos az értékesítési sor létrehozásakor.</span><span class="sxs-lookup"><span data-stu-id="64bf0-147">Notice that a kanban with the same quantity as the sales line is created.</span></span> <span data-ttu-id="64bf0-148">Azt is láthatja, hogy az L0050 termeléséhez anyagi kiadásokra van szükség.</span><span class="sxs-lookup"><span data-stu-id="64bf0-148">You can also see the material issues needed to produce L0050.</span></span> <span data-ttu-id="64bf0-149">Ez az eljárás utolsó lépése.</span><span class="sxs-lookup"><span data-stu-id="64bf0-149">This is the last step in this procedure.</span></span>  

