---
title: Kötegelt rendelések életciklusa a létrehozástól az indításig
description: Ez az eljárás bemutatja egy kötegrendelés életciklusának első felét.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdTableListPage, ProdTableCreate, ProdBOM, PmfProdCoBy, ProdParmCostEstimation, ProdCalcTrans, ProdParmRelease, ProdSchedule, ProdRouteJob, ProdParmStartUp, ProdJournalTransBOM, ProdJournalTransRoute
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6484c1954ff4cc600938adb07b5384f1edce8bf7
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1545902"
---
# <a name="batch-order-lifecycle-from-create-to-start"></a><span data-ttu-id="a11be-103">Kötegelt rendelések életciklusa a létrehozástól az indításig</span><span class="sxs-lookup"><span data-stu-id="a11be-103">Batch order lifecycle from create to start</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="a11be-104">Ez az eljárás bemutatja egy kötegrendelés életciklusának első felét.</span><span class="sxs-lookup"><span data-stu-id="a11be-104">This procedure takes you through the first part of the life cycle of a batch order.</span></span>

<span data-ttu-id="a11be-105">A létrehozástól, költségbecsléstől a termelési feladatok ütemezésén keresztül a kötegrendelés tényleges indulásáig.</span><span class="sxs-lookup"><span data-stu-id="a11be-105">From creation, cost estimation, and over production job scheduling to the actual start of a batch order.</span></span>



<span data-ttu-id="a11be-106">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="a11be-106">The demo data company used to create this procedure is USMF.</span></span> 



<span data-ttu-id="a11be-107">Az eljárás végrehajtásának előfeltétele egy másik adathalmaz esetént, egy kiadott termék egy aktív receptúrával és útvonalverzióval.</span><span class="sxs-lookup"><span data-stu-id="a11be-107">The prerequisites for running the procedure with another dataset are a released product with an active formula and route version.</span></span>


## <a name="create-a-batch-order"></a><span data-ttu-id="a11be-108">Kötegrendelés létrehozása</span><span class="sxs-lookup"><span data-stu-id="a11be-108">Create a batch order</span></span>
1. <span data-ttu-id="a11be-109">Válassza a Minden termelési rendelés lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a11be-109">Go to All production orders.</span></span>
2. <span data-ttu-id="a11be-110">Kattintson az Új kötegrendelés elemre.</span><span class="sxs-lookup"><span data-stu-id="a11be-110">Click New batch order.</span></span>
3. <span data-ttu-id="a11be-111">Az Elemszám mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="a11be-111">In the Item number field, enter or select a value.</span></span>
4. <span data-ttu-id="a11be-112">Kattintson az Új > lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="a11be-112">Click Create.</span></span>
5. <span data-ttu-id="a11be-113">A gyorsszűrő használatával keresse meg azokat a rekordokat, ahol a Termelés mezőben a „b” érték szerepel.</span><span class="sxs-lookup"><span data-stu-id="a11be-113">Use the Quick Filter to filter on the Production field with a value of 'b'.</span></span>

## <a name="view-production-formula-and-expected-co-products"></a><span data-ttu-id="a11be-114">Termelési receptúra és a várható társtermékek megtekintése</span><span class="sxs-lookup"><span data-stu-id="a11be-114">View production formula and expected co-products</span></span>
1. <span data-ttu-id="a11be-115">A Művelet panelen kattintson a Termelési rendelés elemre.</span><span class="sxs-lookup"><span data-stu-id="a11be-115">On the Action Pane, click Production order.</span></span>
2. <span data-ttu-id="a11be-116">Kattintson a Receptúra elemre.</span><span class="sxs-lookup"><span data-stu-id="a11be-116">Click Formula.</span></span>
3. <span data-ttu-id="a11be-117">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="a11be-117">Close the page.</span></span>
4. <span data-ttu-id="a11be-118">Kattintson a Társtermékek elemre.</span><span class="sxs-lookup"><span data-stu-id="a11be-118">Click Co-products.</span></span>
5. <span data-ttu-id="a11be-119">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="a11be-119">Close the page.</span></span>

## <a name="estimate-the-batch-order"></a><span data-ttu-id="a11be-120">Kötegrendelés becslése</span><span class="sxs-lookup"><span data-stu-id="a11be-120">Estimate the batch order</span></span>
1. <span data-ttu-id="a11be-121">Kattintson a Becslés elemre.</span><span class="sxs-lookup"><span data-stu-id="a11be-121">Click Estimate.</span></span>
2. <span data-ttu-id="a11be-122">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="a11be-122">Click OK.</span></span>
3. <span data-ttu-id="a11be-123">A Művelet panelen kattintson a Költségkezelés elemre.</span><span class="sxs-lookup"><span data-stu-id="a11be-123">On the Action Pane, click Manage costs.</span></span>
4. <span data-ttu-id="a11be-124">Kattintson a Számítás részleteinek megjelenítése elemre.</span><span class="sxs-lookup"><span data-stu-id="a11be-124">Click View calculation details.</span></span>
5. <span data-ttu-id="a11be-125">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="a11be-125">Close the page.</span></span>

## <a name="release-the-batch-order"></a><span data-ttu-id="a11be-126">Kötegrendelés kiadása</span><span class="sxs-lookup"><span data-stu-id="a11be-126">Release the batch order</span></span>
1. <span data-ttu-id="a11be-127">A Művelet panelen kattintson a Termelési rendelés elemre.</span><span class="sxs-lookup"><span data-stu-id="a11be-127">On the Action Pane, click Production order.</span></span>
2. <span data-ttu-id="a11be-128">Kattintson a Kiadás elemre.</span><span class="sxs-lookup"><span data-stu-id="a11be-128">Click Release.</span></span>
3. <span data-ttu-id="a11be-129">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="a11be-129">Click OK.</span></span>

## <a name="schedule-production-jobs"></a><span data-ttu-id="a11be-130">Termelési feladatok ütemezése</span><span class="sxs-lookup"><span data-stu-id="a11be-130">Schedule production jobs</span></span>
1. <span data-ttu-id="a11be-131">A Művelet panelen kattintson az Ütemezés elemre.</span><span class="sxs-lookup"><span data-stu-id="a11be-131">On the Action Pane, click Schedule.</span></span>
2. <span data-ttu-id="a11be-132">Kattintson a Feladatok ütemezése lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="a11be-132">Click Schedule jobs.</span></span>
3. <span data-ttu-id="a11be-133">Válassza a Nem lehetőséget a Véges kapacitás mezőben.</span><span class="sxs-lookup"><span data-stu-id="a11be-133">Select No in the Finite capacity field.</span></span>
4. <span data-ttu-id="a11be-134">Válassza a Nem lehetőséget a Véges anyag mezőben.</span><span class="sxs-lookup"><span data-stu-id="a11be-134">Select No in the Finite material field.</span></span>
5. <span data-ttu-id="a11be-135">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="a11be-135">Click OK.</span></span>
6. <span data-ttu-id="a11be-136">A Művelet panelen kattintson a Termelési rendelés elemre.</span><span class="sxs-lookup"><span data-stu-id="a11be-136">On the Action Pane, click Production order.</span></span>
7. <span data-ttu-id="a11be-137">Kattintson a Minden feladat elemre.</span><span class="sxs-lookup"><span data-stu-id="a11be-137">Click All jobs.</span></span>
8. <span data-ttu-id="a11be-138">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="a11be-138">Close the page.</span></span>

## <a name="start-the-batch-order"></a><span data-ttu-id="a11be-139">Kötegrendelés indítása</span><span class="sxs-lookup"><span data-stu-id="a11be-139">Start the batch order</span></span>
1. <span data-ttu-id="a11be-140">Kattintson a Start elemre.</span><span class="sxs-lookup"><span data-stu-id="a11be-140">Click Start.</span></span>
2. <span data-ttu-id="a11be-141">Kattintson az Általános fülre.</span><span class="sxs-lookup"><span data-stu-id="a11be-141">Click the General tab.</span></span>
3. <span data-ttu-id="a11be-142">Válassza a Nem lehetőséget a Kitárolási lista feladása most mezőben.</span><span class="sxs-lookup"><span data-stu-id="a11be-142">Select No in the Post picking list now field.</span></span>
4. <span data-ttu-id="a11be-143">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="a11be-143">Click OK.</span></span>
5. <span data-ttu-id="a11be-144">A Művelet panelen kattintson a Nézet elemre.</span><span class="sxs-lookup"><span data-stu-id="a11be-144">On the Action Pane, click View.</span></span>
6. <span data-ttu-id="a11be-145">Kattintson a Kitárolási lista elemre.</span><span class="sxs-lookup"><span data-stu-id="a11be-145">Click Picking list.</span></span>
7. <span data-ttu-id="a11be-146">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="a11be-146">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="a11be-147">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="a11be-147">Close the page.</span></span>
9. <span data-ttu-id="a11be-148">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="a11be-148">Close the page.</span></span>
10. <span data-ttu-id="a11be-149">Kattintson az Útvonalkártya elemre.</span><span class="sxs-lookup"><span data-stu-id="a11be-149">Click Route card.</span></span>
11. <span data-ttu-id="a11be-150">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="a11be-150">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="a11be-151">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="a11be-151">Close the page.</span></span>
13. <span data-ttu-id="a11be-152">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="a11be-152">Close the page.</span></span>

