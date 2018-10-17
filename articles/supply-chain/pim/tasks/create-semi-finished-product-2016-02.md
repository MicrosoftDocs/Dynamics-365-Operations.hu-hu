--- 
title: "Félkész termék létrehozása (2016. február)"
description: "Ez a feladat egy félkész termék létrehozására szolgál."
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResProductDetailsExtended, EcoResProductCreate, InventItemOrderSetup, InventItemPrice
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 9caeae552471eed1cb1d8630f387ca31107fcece
ms.contentlocale: hu-hu
ms.lasthandoff: 09/14/2018

---
# <a name="create-a-semi-finished-product-february-2016"></a><span data-ttu-id="43426-103">Félkész termék létrehozása (2016. február)</span><span class="sxs-lookup"><span data-stu-id="43426-103">Create a semi-finished product (February 2016)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="43426-104">Ez a feladat egy félkész termék létrehozására szolgál.</span><span class="sxs-lookup"><span data-stu-id="43426-104">This task focuses on creating a semi-finished product.</span></span> <span data-ttu-id="43426-105">Ez az anyagjegyzék-számítási sorozat második feladata.</span><span class="sxs-lookup"><span data-stu-id="43426-105">It is the second task in the BOM calculation series.</span></span> <span data-ttu-id="43426-106">A feladat létrehozásához az USMF bemutató vállalatot használtuk példaként.</span><span class="sxs-lookup"><span data-stu-id="43426-106">The demo data company used to create this task is USMF.</span></span>

1. <span data-ttu-id="43426-107">Kattintson a Termékinformációk kezelése > Termékek > Kiadott termékek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="43426-107">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="43426-108">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="43426-108">Click New.</span></span>
3. <span data-ttu-id="43426-109">Írjon be egy értéket a Termékszám mezőbe.</span><span class="sxs-lookup"><span data-stu-id="43426-109">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="43426-110">Ehhez a példához írja be a következőt: BOM_2.</span><span class="sxs-lookup"><span data-stu-id="43426-110">For this example, type BOM_2.</span></span>  
4. <span data-ttu-id="43426-111">Az Elem modellcsoport mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="43426-111">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="43426-112">Válassza az STD lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="43426-112">Select STD.</span></span> <span data-ttu-id="43426-113">Az STD az elszámolóár rövidítése, és a költségszámításokkal dolgozva ez a leggyakrabban használt modell.</span><span class="sxs-lookup"><span data-stu-id="43426-113">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
5. <span data-ttu-id="43426-114">Az Elemcsoport mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="43426-114">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="43426-115">Válassza például a következőt: Audió.</span><span class="sxs-lookup"><span data-stu-id="43426-115">For example, select Audio.</span></span> <span data-ttu-id="43426-116">Nincs hatással a költségszámításokra.</span><span class="sxs-lookup"><span data-stu-id="43426-116">This has no impact on cost calculations.</span></span>  
6. <span data-ttu-id="43426-117">A Tárolási dimenzió mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="43426-117">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="43426-118">SiteWH kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="43426-118">Select SiteWH.</span></span> <span data-ttu-id="43426-119">A példához csak a helyet és a raktárat használjuk.</span><span class="sxs-lookup"><span data-stu-id="43426-119">Only Site and Warehouse will be used for this example.</span></span>  
7. <span data-ttu-id="43426-120">A Nyomon követési dimenzió mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="43426-120">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="43426-121">A nyomon követési dimenziókat nem használjuk ennél a példánál, válassza a Nincs lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="43426-121">Tracking dimensions will not be used for this example, select None.</span></span>  
8. <span data-ttu-id="43426-122">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="43426-122">Click OK.</span></span>
9. <span data-ttu-id="43426-123">A Művelet panelen kattintson a Készletkezelés elemre.</span><span class="sxs-lookup"><span data-stu-id="43426-123">On the Action Pane, click Manage inventory.</span></span>
10. <span data-ttu-id="43426-124">Kattintson az Alapértelmezett rendelésbeállítások elemre.</span><span class="sxs-lookup"><span data-stu-id="43426-124">Click Default order settings.</span></span>
11. <span data-ttu-id="43426-125">Az Alapértelmezett rendelés típusa mezőben válassza ki a „Termelés” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="43426-125">In the Default order type field, select 'Production'.</span></span>
    * <span data-ttu-id="43426-126">Mivel ez egy félkész termék, amely gyártásba kerül, válassza a Termelés lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="43426-126">Because this is a semi-finished product that will be produced, select Production.</span></span>  
12. <span data-ttu-id="43426-127">A Beszerzési hely mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="43426-127">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="43426-128">Ehhez a példához válassza ki a következőt: 1. hely.</span><span class="sxs-lookup"><span data-stu-id="43426-128">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="43426-129">A Készlethely mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="43426-129">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="43426-130">Ehhez a példához válassza ki a következőt: 1. hely.</span><span class="sxs-lookup"><span data-stu-id="43426-130">For this example, select Site 1.</span></span>  
14. <span data-ttu-id="43426-131">Az Értékesítési hely mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="43426-131">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="43426-132">Ehhez a példához válassza ki a következőt: 1. hely.</span><span class="sxs-lookup"><span data-stu-id="43426-132">For this example, select Site 1.</span></span>  
15. <span data-ttu-id="43426-133">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="43426-133">Close the page.</span></span>
16. <span data-ttu-id="43426-134">A Művelet panelen kattintson a Költségkezelés elemre.</span><span class="sxs-lookup"><span data-stu-id="43426-134">On the Action Pane, click Manage costs.</span></span>
17. <span data-ttu-id="43426-135">Kattintson a Cikk ára elemre.</span><span class="sxs-lookup"><span data-stu-id="43426-135">Click Item price.</span></span>
18. <span data-ttu-id="43426-136">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="43426-136">Click New.</span></span>
19. <span data-ttu-id="43426-137">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="43426-137">In the list, mark the selected row.</span></span>
20. <span data-ttu-id="43426-138">A Verzió mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="43426-138">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="43426-139">Ehhez a példához válassza ki a következőt: 10. verzió.</span><span class="sxs-lookup"><span data-stu-id="43426-139">For this example, select Version 10.</span></span>  
21. <span data-ttu-id="43426-140">A Hely mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="43426-140">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="43426-141">Ehhez a példához válassza ki a következőt: 1. hely.</span><span class="sxs-lookup"><span data-stu-id="43426-141">For this example, select Site 1.</span></span>  
22. <span data-ttu-id="43426-142">Állítsa az Árat „10”-re.</span><span class="sxs-lookup"><span data-stu-id="43426-142">Set Price to '10'.</span></span>
    * <span data-ttu-id="43426-143">Ebben a példában az önköltségi ár típusának adja meg a következőt: 10.</span><span class="sxs-lookup"><span data-stu-id="43426-143">For this example, type a cost price of 10.</span></span>  
23. <span data-ttu-id="43426-144">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="43426-144">Click Save.</span></span>
24. <span data-ttu-id="43426-145">Kattintson a Függő árak aktiválása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="43426-145">Click Activate pending price(s).</span></span>
25. <span data-ttu-id="43426-146">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="43426-146">Close the page.</span></span>
26. <span data-ttu-id="43426-147">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="43426-147">Close the page.</span></span>
27. <span data-ttu-id="43426-148">Kattintson a BOM_2 lehetőségre a megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="43426-148">Click BOM_2 to open it.</span></span>
28. <span data-ttu-id="43426-149">Bontsa ki a Költségkezelés szakaszt.</span><span class="sxs-lookup"><span data-stu-id="43426-149">Expand the Manage costs section.</span></span>
29. <span data-ttu-id="43426-150">A Költségcsoport mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="43426-150">In the Cost group field, enter or select a value.</span></span>
    * <span data-ttu-id="43426-151">Ehhez a példához válassza ki az M1 költségcsoport lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="43426-151">For this example, select Cost group M1.</span></span>  
30. <span data-ttu-id="43426-152">Használja a parancsikont a rekord mentéséhez.</span><span class="sxs-lookup"><span data-stu-id="43426-152">Use the shortcut for saving a record.</span></span>
31. <span data-ttu-id="43426-153">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="43426-153">Close the page.</span></span>


