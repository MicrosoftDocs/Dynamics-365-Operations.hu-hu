--- 
title: "Félkész termék létrehozása (csak 2016. február)"
description: "Ez a feladat egy félkész termék létrehozására szolgál."
author: YuyuScheller
manager: AnnBe
ms.date: 02/07/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 1311e27b4080832c6e1aa2b879308f518d2ab001
ms.contentlocale: hu-hu
ms.lasthandoff: 04/13/2018

---
# <a name="create-a-semi-finished-product-february-2016-only"></a><span data-ttu-id="1a357-103">Félkész termék létrehozása (csak 2016. február)</span><span class="sxs-lookup"><span data-stu-id="1a357-103">Create a semi-finished product (February 2016 only)</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="1a357-104">Ez a feladat egy félkész termék létrehozására szolgál.</span><span class="sxs-lookup"><span data-stu-id="1a357-104">This task focuses on creating a semi-finished product.</span></span> <span data-ttu-id="1a357-105">Ez az anyagjegyzék-számítási sorozat második feladata.</span><span class="sxs-lookup"><span data-stu-id="1a357-105">It is the second task in the BOM calculation series.</span></span> <span data-ttu-id="1a357-106">A feladat létrehozásához az USMF bemutató vállalatot használtuk példaként.</span><span class="sxs-lookup"><span data-stu-id="1a357-106">The demo data company used to create this task is USMF.</span></span>

1. <span data-ttu-id="1a357-107">Kattintson a Termékinformációk kezelése > Termékek > Kiadott termékek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="1a357-107">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="1a357-108">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="1a357-108">Click New.</span></span>
3. <span data-ttu-id="1a357-109">Írjon be egy értéket a Termékszám mezőbe.</span><span class="sxs-lookup"><span data-stu-id="1a357-109">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="1a357-110">Ehhez a példához írja be a következőt: BOM_2.</span><span class="sxs-lookup"><span data-stu-id="1a357-110">For this example, type BOM_2.</span></span>  
4. <span data-ttu-id="1a357-111">Az Elem modellcsoport mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="1a357-111">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="1a357-112">Válassza az STD lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1a357-112">Select STD.</span></span> <span data-ttu-id="1a357-113">Az STD az elszámolóár rövidítése, és a költségszámításokkal dolgozva ez a leggyakrabban használt modell.</span><span class="sxs-lookup"><span data-stu-id="1a357-113">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
5. <span data-ttu-id="1a357-114">Az Elemcsoport mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="1a357-114">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="1a357-115">Válassza például a következőt: Audió.</span><span class="sxs-lookup"><span data-stu-id="1a357-115">For example, select Audio.</span></span> <span data-ttu-id="1a357-116">Nincs hatással a költségszámításokra.</span><span class="sxs-lookup"><span data-stu-id="1a357-116">This has no impact on cost calculations.</span></span>  
6. <span data-ttu-id="1a357-117">A Tárolási dimenzió mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="1a357-117">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="1a357-118">SiteWH kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="1a357-118">Select SiteWH.</span></span> <span data-ttu-id="1a357-119">A példához csak a helyet és a raktárat használjuk.</span><span class="sxs-lookup"><span data-stu-id="1a357-119">Only Site and Warehouse will be used for this example.</span></span>  
7. <span data-ttu-id="1a357-120">A Nyomon követési dimenzió mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="1a357-120">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="1a357-121">A nyomon követési dimenziókat nem használjuk ennél a példánál, válassza a Nincs lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1a357-121">Tracking dimensions will not be used for this example, select None.</span></span>  
8. <span data-ttu-id="1a357-122">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="1a357-122">Click OK.</span></span>
9. <span data-ttu-id="1a357-123">A Művelet panelen kattintson a Készletkezelés elemre.</span><span class="sxs-lookup"><span data-stu-id="1a357-123">On the Action Pane, click Manage inventory.</span></span>
10. <span data-ttu-id="1a357-124">Kattintson az Alapértelmezett rendelésbeállítások elemre.</span><span class="sxs-lookup"><span data-stu-id="1a357-124">Click Default order settings.</span></span>
11. <span data-ttu-id="1a357-125">Az Alapértelmezett rendelés típusa mezőben válassza ki a „Termelés” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1a357-125">In the Default order type field, select 'Production'.</span></span>
    * <span data-ttu-id="1a357-126">Mivel ez egy félkész termék, amely gyártásba kerül, válassza a Termelés lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1a357-126">Because this is a semi-finished product that will be produced, select Production.</span></span>  
12. <span data-ttu-id="1a357-127">A Beszerzési hely mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="1a357-127">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="1a357-128">Ehhez a példához válassza ki a következőt: 1. hely.</span><span class="sxs-lookup"><span data-stu-id="1a357-128">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="1a357-129">A Készlethely mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="1a357-129">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="1a357-130">Ehhez a példához válassza ki a következőt: 1. hely.</span><span class="sxs-lookup"><span data-stu-id="1a357-130">For this example, select Site 1.</span></span>  
14. <span data-ttu-id="1a357-131">Az Értékesítési hely mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="1a357-131">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="1a357-132">Ehhez a példához válassza ki a következőt: 1. hely.</span><span class="sxs-lookup"><span data-stu-id="1a357-132">For this example, select Site 1.</span></span>  
15. <span data-ttu-id="1a357-133">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="1a357-133">Close the page.</span></span>
16. <span data-ttu-id="1a357-134">A Művelet panelen kattintson a Költségkezelés elemre.</span><span class="sxs-lookup"><span data-stu-id="1a357-134">On the Action Pane, click Manage costs.</span></span>
17. <span data-ttu-id="1a357-135">Kattintson a Cikk ára elemre.</span><span class="sxs-lookup"><span data-stu-id="1a357-135">Click Item price.</span></span>
18. <span data-ttu-id="1a357-136">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="1a357-136">Click New.</span></span>
19. <span data-ttu-id="1a357-137">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="1a357-137">In the list, mark the selected row.</span></span>
20. <span data-ttu-id="1a357-138">A Verzió mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="1a357-138">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="1a357-139">Ehhez a példához válassza ki a következőt: 10. verzió.</span><span class="sxs-lookup"><span data-stu-id="1a357-139">For this example, select Version 10.</span></span>  
21. <span data-ttu-id="1a357-140">A Hely mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="1a357-140">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="1a357-141">Ehhez a példához válassza ki a következőt: 1. hely.</span><span class="sxs-lookup"><span data-stu-id="1a357-141">For this example, select Site 1.</span></span>  
22. <span data-ttu-id="1a357-142">Állítsa az Árat „10”-re.</span><span class="sxs-lookup"><span data-stu-id="1a357-142">Set Price to '10'.</span></span>
    * <span data-ttu-id="1a357-143">Ebben a példában az önköltségi ár típusának adja meg a következőt: 10.</span><span class="sxs-lookup"><span data-stu-id="1a357-143">For this example, type a cost price of 10.</span></span>  
23. <span data-ttu-id="1a357-144">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="1a357-144">Click Save.</span></span>
24. <span data-ttu-id="1a357-145">Kattintson a Függő árak aktiválása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="1a357-145">Click Activate pending price(s).</span></span>
25. <span data-ttu-id="1a357-146">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="1a357-146">Close the page.</span></span>
26. <span data-ttu-id="1a357-147">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="1a357-147">Close the page.</span></span>
27. <span data-ttu-id="1a357-148">Kattintson a BOM_2 lehetőségre a megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="1a357-148">Click BOM_2 to open it.</span></span>
28. <span data-ttu-id="1a357-149">Bontsa ki a Költségkezelés szakaszt.</span><span class="sxs-lookup"><span data-stu-id="1a357-149">Expand the Manage costs section.</span></span>
29. <span data-ttu-id="1a357-150">A Költségcsoport mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="1a357-150">In the Cost group field, enter or select a value.</span></span>
    * <span data-ttu-id="1a357-151">Ehhez a példához válassza ki az M1 költségcsoport lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1a357-151">For this example, select Cost group M1.</span></span>  
30. <span data-ttu-id="1a357-152">Használja a parancsikont a rekord mentéséhez.</span><span class="sxs-lookup"><span data-stu-id="1a357-152">Use the shortcut for saving a record.</span></span>
31. <span data-ttu-id="1a357-153">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="1a357-153">Close the page.</span></span>


