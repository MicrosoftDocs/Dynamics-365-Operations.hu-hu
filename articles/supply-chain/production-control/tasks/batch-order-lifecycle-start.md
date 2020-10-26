---
title: Kötegelt rendelések életciklusa a létrehozástól az indításig
description: Ez az eljárás bemutatja egy kötegrendelés életciklusának első felét.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdTableListPage, ProdTableCreate, ProdBOM, PmfProdCoBy, ProdParmCostEstimation, ProdCalcTrans, ProdParmRelease, ProdSchedule, ProdRouteJob, ProdParmStartUp, ProdJournalTransBOM, ProdJournalTransRoute
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e57cd9254185b73f544e8ff4f7658cf743b672f2
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/10/2020
ms.locfileid: "3981304"
---
# <a name="batch-order-lifecycle-from-create-to-start"></a><span data-ttu-id="8d75c-103">Kötegelt rendelések életciklusa a létrehozástól az indításig</span><span class="sxs-lookup"><span data-stu-id="8d75c-103">Batch order lifecycle from create to start</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="8d75c-104">Ez az eljárás bemutatja egy kötegrendelés életciklusának első felét.</span><span class="sxs-lookup"><span data-stu-id="8d75c-104">This procedure takes you through the first part of the life cycle of a batch order.</span></span>

<span data-ttu-id="8d75c-105">A létrehozástól, költségbecsléstől a termelési feladatok ütemezésén keresztül a kötegrendelés tényleges indulásáig.</span><span class="sxs-lookup"><span data-stu-id="8d75c-105">From creation, cost estimation, and over production job scheduling to the actual start of a batch order.</span></span>



<span data-ttu-id="8d75c-106">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="8d75c-106">The demo data company used to create this procedure is USMF.</span></span> 



<span data-ttu-id="8d75c-107">Az eljárás végrehajtásának előfeltétele egy másik adathalmaz esetént, egy kiadott termék egy aktív receptúrával és útvonalverzióval.</span><span class="sxs-lookup"><span data-stu-id="8d75c-107">The prerequisites for running the procedure with another dataset are a released product with an active formula and route version.</span></span>


## <a name="create-a-batch-order"></a><span data-ttu-id="8d75c-108">Kötegrendelés létrehozása</span><span class="sxs-lookup"><span data-stu-id="8d75c-108">Create a batch order</span></span>
1. <span data-ttu-id="8d75c-109">Válassza a Minden termelési rendelés lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8d75c-109">Go to All production orders.</span></span>
2. <span data-ttu-id="8d75c-110">Kattintson az Új kötegrendelés elemre.</span><span class="sxs-lookup"><span data-stu-id="8d75c-110">Click New batch order.</span></span>
3. <span data-ttu-id="8d75c-111">Az Elemszám mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="8d75c-111">In the Item number field, enter or select a value.</span></span>
4. <span data-ttu-id="8d75c-112">Kattintson az Új > lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8d75c-112">Click Create.</span></span>
5. <span data-ttu-id="8d75c-113">A gyorsszűrő használatával keresse meg azokat a rekordokat, ahol a Termelés mezőben a „b” érték szerepel.</span><span class="sxs-lookup"><span data-stu-id="8d75c-113">Use the Quick Filter to filter on the Production field with a value of 'b'.</span></span>

## <a name="view-production-formula-and-expected-co-products"></a><span data-ttu-id="8d75c-114">Termelési receptúra és a várható társtermékek megtekintése</span><span class="sxs-lookup"><span data-stu-id="8d75c-114">View production formula and expected co-products</span></span>
1. <span data-ttu-id="8d75c-115">A Művelet panelen kattintson a Termelési rendelés elemre.</span><span class="sxs-lookup"><span data-stu-id="8d75c-115">On the Action Pane, click Production order.</span></span>
2. <span data-ttu-id="8d75c-116">Kattintson a Receptúra elemre.</span><span class="sxs-lookup"><span data-stu-id="8d75c-116">Click Formula.</span></span>
3. <span data-ttu-id="8d75c-117">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="8d75c-117">Close the page.</span></span>
4. <span data-ttu-id="8d75c-118">Kattintson a Társtermékek elemre.</span><span class="sxs-lookup"><span data-stu-id="8d75c-118">Click Co-products.</span></span>
5. <span data-ttu-id="8d75c-119">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="8d75c-119">Close the page.</span></span>

## <a name="estimate-the-batch-order"></a><span data-ttu-id="8d75c-120">Kötegrendelés becslése</span><span class="sxs-lookup"><span data-stu-id="8d75c-120">Estimate the batch order</span></span>
1. <span data-ttu-id="8d75c-121">Kattintson a Becslés elemre.</span><span class="sxs-lookup"><span data-stu-id="8d75c-121">Click Estimate.</span></span>
2. <span data-ttu-id="8d75c-122">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="8d75c-122">Click OK.</span></span>
3. <span data-ttu-id="8d75c-123">A Művelet panelen kattintson a Költségkezelés elemre.</span><span class="sxs-lookup"><span data-stu-id="8d75c-123">On the Action Pane, click Manage costs.</span></span>
4. <span data-ttu-id="8d75c-124">Kattintson a Számítás részleteinek megjelenítése elemre.</span><span class="sxs-lookup"><span data-stu-id="8d75c-124">Click View calculation details.</span></span>
5. <span data-ttu-id="8d75c-125">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="8d75c-125">Close the page.</span></span>

## <a name="release-the-batch-order"></a><span data-ttu-id="8d75c-126">Kötegrendelés kiadása</span><span class="sxs-lookup"><span data-stu-id="8d75c-126">Release the batch order</span></span>
1. <span data-ttu-id="8d75c-127">A Művelet panelen kattintson a Termelési rendelés elemre.</span><span class="sxs-lookup"><span data-stu-id="8d75c-127">On the Action Pane, click Production order.</span></span>
2. <span data-ttu-id="8d75c-128">Kattintson a Kiadás elemre.</span><span class="sxs-lookup"><span data-stu-id="8d75c-128">Click Release.</span></span>
3. <span data-ttu-id="8d75c-129">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="8d75c-129">Click OK.</span></span>

## <a name="schedule-production-jobs"></a><span data-ttu-id="8d75c-130">Termelési feladatok ütemezése</span><span class="sxs-lookup"><span data-stu-id="8d75c-130">Schedule production jobs</span></span>
1. <span data-ttu-id="8d75c-131">A Művelet panelen kattintson az Ütemezés elemre.</span><span class="sxs-lookup"><span data-stu-id="8d75c-131">On the Action Pane, click Schedule.</span></span>
2. <span data-ttu-id="8d75c-132">Kattintson a Feladatok ütemezése lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8d75c-132">Click Schedule jobs.</span></span>
3. <span data-ttu-id="8d75c-133">Válassza a Nem lehetőséget a Véges kapacitás mezőben.</span><span class="sxs-lookup"><span data-stu-id="8d75c-133">Select No in the Finite capacity field.</span></span>
4. <span data-ttu-id="8d75c-134">Válassza a Nem lehetőséget a Véges anyag mezőben.</span><span class="sxs-lookup"><span data-stu-id="8d75c-134">Select No in the Finite material field.</span></span>
5. <span data-ttu-id="8d75c-135">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="8d75c-135">Click OK.</span></span>
6. <span data-ttu-id="8d75c-136">A Művelet panelen kattintson a Termelési rendelés elemre.</span><span class="sxs-lookup"><span data-stu-id="8d75c-136">On the Action Pane, click Production order.</span></span>
7. <span data-ttu-id="8d75c-137">Kattintson a Minden feladat elemre.</span><span class="sxs-lookup"><span data-stu-id="8d75c-137">Click All jobs.</span></span>
8. <span data-ttu-id="8d75c-138">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="8d75c-138">Close the page.</span></span>

## <a name="start-the-batch-order"></a><span data-ttu-id="8d75c-139">Kötegrendelés indítása</span><span class="sxs-lookup"><span data-stu-id="8d75c-139">Start the batch order</span></span>
1. <span data-ttu-id="8d75c-140">Kattintson a Start elemre.</span><span class="sxs-lookup"><span data-stu-id="8d75c-140">Click Start.</span></span>
2. <span data-ttu-id="8d75c-141">Kattintson az Általános fülre.</span><span class="sxs-lookup"><span data-stu-id="8d75c-141">Click the General tab.</span></span>
3. <span data-ttu-id="8d75c-142">Válassza a Nem lehetőséget a Kitárolási lista feladása most mezőben.</span><span class="sxs-lookup"><span data-stu-id="8d75c-142">Select No in the Post picking list now field.</span></span>
4. <span data-ttu-id="8d75c-143">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="8d75c-143">Click OK.</span></span>
5. <span data-ttu-id="8d75c-144">A Művelet panelen kattintson a Nézet elemre.</span><span class="sxs-lookup"><span data-stu-id="8d75c-144">On the Action Pane, click View.</span></span>
6. <span data-ttu-id="8d75c-145">Kattintson a Kitárolási lista elemre.</span><span class="sxs-lookup"><span data-stu-id="8d75c-145">Click Picking list.</span></span>
7. <span data-ttu-id="8d75c-146">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="8d75c-146">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="8d75c-147">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="8d75c-147">Close the page.</span></span>
9. <span data-ttu-id="8d75c-148">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="8d75c-148">Close the page.</span></span>
10. <span data-ttu-id="8d75c-149">Kattintson az Útvonalkártya elemre.</span><span class="sxs-lookup"><span data-stu-id="8d75c-149">Click Route card.</span></span>
11. <span data-ttu-id="8d75c-150">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="8d75c-150">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="8d75c-151">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="8d75c-151">Close the page.</span></span>
13. <span data-ttu-id="8d75c-152">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="8d75c-152">Close the page.</span></span>

