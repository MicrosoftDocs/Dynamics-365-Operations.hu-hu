--- 
title: "Lean manufacturing gyártási átviteli tevékenységek létrehozása"
description: "Hozzon létre átmozgatási tevékenységet lean manufacturinghez."
author: cvocph
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: e5f28b26cee2501f1294cd34a495ee925e6b1ba8
ms.contentlocale: hu-hu
ms.lasthandoff: 08/29/2017

---
# <a name="create-transfer-activities-for-lean-manufacturing"></a><span data-ttu-id="08fa8-103">Lean manufacturing gyártási átviteli tevékenységek létrehozása</span><span class="sxs-lookup"><span data-stu-id="08fa8-103">Create transfer activities for lean manufacturing</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="08fa8-104">Hozzon létre átmozgatási tevékenységet lean manufacturinghez.</span><span class="sxs-lookup"><span data-stu-id="08fa8-104">Create a transfer activity for lean manufacturing.</span></span> 

<span data-ttu-id="08fa8-105">Előfeltételek:</span><span class="sxs-lookup"><span data-stu-id="08fa8-105">Prerequisites:</span></span> 

1. <span data-ttu-id="08fa8-106">Létre kell hozni a termelési folyamatot és a nem aktív verziót.</span><span class="sxs-lookup"><span data-stu-id="08fa8-106">A production flow and version that is not active must be created.</span></span>

2. <span data-ttu-id="08fa8-107">Létre kell hozni a kiindulási és a célraktár helyét.</span><span class="sxs-lookup"><span data-stu-id="08fa8-107">The from and to warehouse and locations must be created.</span></span> <span data-ttu-id="08fa8-108">A feltöltő vagy a feltöltött munkacellát is létre lehet hozni.</span><span class="sxs-lookup"><span data-stu-id="08fa8-108">Optionally, the replenishing or the replenished work cell should be created.</span></span>


## <a name="find-the-production-flow-version"></a><span data-ttu-id="08fa8-109">Termelési folyamat verziójának megkeresése</span><span class="sxs-lookup"><span data-stu-id="08fa8-109">Find the production flow version</span></span>
1. <span data-ttu-id="08fa8-110">Ugrás a Gyártásvezérléshez > Beállítás > Lean típusú termelési folyamat > Termelési folyamatok lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="08fa8-110">Go to Production control > Setup > Lean production flow > Production flows.</span></span>
2. <span data-ttu-id="08fa8-111">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="08fa8-111">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="08fa8-112">Vegye figyelembe, hogy a termelési folyamatnak verzióval kell rendelkeznie a várlat állapotban.</span><span class="sxs-lookup"><span data-stu-id="08fa8-112">Note that the production flow must have a version in draft status.</span></span>  
3. <span data-ttu-id="08fa8-113">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="08fa8-113">In the list, click the link in the selected row.</span></span>

## <a name="create-a-new-activity"></a><span data-ttu-id="08fa8-114">Új tevékenység létrehozása</span><span class="sxs-lookup"><span data-stu-id="08fa8-114">Create a new activity</span></span>
1. <span data-ttu-id="08fa8-115">Kattintson a Tevékenységek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="08fa8-115">Click Activities.</span></span>
    * <span data-ttu-id="08fa8-116">Győződjön meg arról, hogy a kiválasztott termelési folyamat rendelkezik vázlatverzióval, és válassza ki azt a verziót.</span><span class="sxs-lookup"><span data-stu-id="08fa8-116">Ensure that the selected production flow has a version in draft and select that version.</span></span>  
2. <span data-ttu-id="08fa8-117">Kattintson az Új tervezett tevékenység létrehozása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="08fa8-117">Click Create new plan activity.</span></span>
3. <span data-ttu-id="08fa8-118">Kattintson a Tovább gombra.</span><span class="sxs-lookup"><span data-stu-id="08fa8-118">Click Next.</span></span>
4. <span data-ttu-id="08fa8-119">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="08fa8-119">In the Name field, type a value.</span></span>
5. <span data-ttu-id="08fa8-120">A Tevékenységtípus mezőben válassza ki az „Átmozgatás” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="08fa8-120">In the Activity type field, select 'Transfer'.</span></span>
6. <span data-ttu-id="08fa8-121">Adjon meg egy számot az Folyamatmennyiség mezőben.</span><span class="sxs-lookup"><span data-stu-id="08fa8-121">In the Process quantity field, enter a number.</span></span>
7. <span data-ttu-id="08fa8-122">Kattintson a Tovább gombra.</span><span class="sxs-lookup"><span data-stu-id="08fa8-122">Click Next.</span></span>

## <a name="select-the-work-cells"></a><span data-ttu-id="08fa8-123">Munkacellák kiválasztása</span><span class="sxs-lookup"><span data-stu-id="08fa8-123">Select the Work cells</span></span>
1. <span data-ttu-id="08fa8-124">A Feltöltés mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="08fa8-124">In the Replenishing field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="08fa8-125">Ha a munkacella kimeneti helyét az átmozgatási tevékenység forráshelyéül szeretné használni, válasszon ki egy munkacellát.</span><span class="sxs-lookup"><span data-stu-id="08fa8-125">To use the work cell output location as the from location in the transfer activity, select a work cell.</span></span> <span data-ttu-id="08fa8-126">Ugyanezt feltöltött munkacellával is megteheti, amely így beállítja az átmozgatási tevékenység célhelyét.</span><span class="sxs-lookup"><span data-stu-id="08fa8-126">The same can be done with the replenished work cell, which sets the target location of the transfer activity.</span></span>  
2. <span data-ttu-id="08fa8-127">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="08fa8-127">In the list, click the link in the selected row.</span></span>

## <a name="define-the-inventory-updates"></a><span data-ttu-id="08fa8-128">A készletfrissítések meghatározása</span><span class="sxs-lookup"><span data-stu-id="08fa8-128">Define the inventory updates</span></span>
1. <span data-ttu-id="08fa8-129">Válasszon egy lehetőséget a Terméktípus mezőben.</span><span class="sxs-lookup"><span data-stu-id="08fa8-129">In the Product type field, select an option.</span></span>
    * <span data-ttu-id="08fa8-130">Megjegyzés: Az átmozgatás nem változtatja meg a termék típusát.</span><span class="sxs-lookup"><span data-stu-id="08fa8-130">Note that a transfer does not change the type of product.</span></span> <span data-ttu-id="08fa8-131">Átmozgathat kész és félkész termékeket (átmozgatás egy termelési folyamat két tevékenysége és esetleg egy kanbanfolyamat között).</span><span class="sxs-lookup"><span data-stu-id="08fa8-131">You can transfer finished products or semi-finished products (transfer between two activities of a production flow and possibly a kanban flow).</span></span>     <span data-ttu-id="08fa8-132">Kész termékek átmozgatása esetén meghatározhatja, hogy a kitárolás és az eredmények fogadása készlettranzakcióban történjen.</span><span class="sxs-lookup"><span data-stu-id="08fa8-132">When transferring finished products, you can select if picking or receiving results in an inventory transaction.</span></span>  

## <a name="define-the-transfer-locations"></a><span data-ttu-id="08fa8-133">Átmozgatás helyének meghatározása</span><span class="sxs-lookup"><span data-stu-id="08fa8-133">Define the transfer locations</span></span>
1. <span data-ttu-id="08fa8-134">Kattintson a Tovább gombra.</span><span class="sxs-lookup"><span data-stu-id="08fa8-134">Click Next.</span></span>
2. <span data-ttu-id="08fa8-135">A Raktár mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="08fa8-135">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="08fa8-136">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="08fa8-136">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="08fa8-137">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="08fa8-137">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="08fa8-138">A Hely mezőben kattintson a legördülő gombra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="08fa8-138">In the Location field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="08fa8-139">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="08fa8-139">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="08fa8-140">A Szállította mezőben válassza ki a „Szállító” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="08fa8-140">In the Freighted by field, select 'Shipper'.</span></span>
    * <span data-ttu-id="08fa8-141">A lehetőségek a következők: Szállító – a szállítási raktárt üzemeltető szervezet, Címzett – a fogadó raktárt üzemeltető szervezet, Szállítmányozó – harmadik fél szállító.</span><span class="sxs-lookup"><span data-stu-id="08fa8-141">Options include: Shipper - the organization operating the shipping warehouse, Recipient -  the organization operating the receiving warehouse, Carrier - a third party vendor.</span></span> <span data-ttu-id="08fa8-142">Ha az üzemeltető szervezet szállító, az átmozgatási tevékenység alvállalkozói szerződést igényel.</span><span class="sxs-lookup"><span data-stu-id="08fa8-142">If the operating organization is a vendor, the transfer activity requires a subcontracting agreement.</span></span>  
8. <span data-ttu-id="08fa8-143">Kattintson a Tovább gombra.</span><span class="sxs-lookup"><span data-stu-id="08fa8-143">Click Next.</span></span>

## <a name="define-the-activity-times"></a><span data-ttu-id="08fa8-144">A tevékenységi idők meghatározása</span><span class="sxs-lookup"><span data-stu-id="08fa8-144">Define the activity times</span></span>
1. <span data-ttu-id="08fa8-145">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="08fa8-145">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="08fa8-146">A Futásidő meghatározását meg kell adni.</span><span class="sxs-lookup"><span data-stu-id="08fa8-146">The definition of a Runtime is required.</span></span> <span data-ttu-id="08fa8-147">A Futásidő a költség és a kanbanfeladatok átfutási idejének kiszámítására szolgál.</span><span class="sxs-lookup"><span data-stu-id="08fa8-147">The Runtime is used to calculate cost and the throughput times of the kanban jobs.</span></span> <span data-ttu-id="08fa8-148">A futásidő nem a kapacitásterhelés és a felhasználás kiszámítására szolgál, ezt a ciklusidő számítja ki a termelésifolyamat-verzió feladat segítségével.</span><span class="sxs-lookup"><span data-stu-id="08fa8-148">Runtimes are not used to calculate capacity load and consumption, which is calculated by cycle time, derived from the production flow version task.</span></span>  
2. <span data-ttu-id="08fa8-149">Adjon meg egy számot az Idő mezőben.</span><span class="sxs-lookup"><span data-stu-id="08fa8-149">In the Time field, enter a number.</span></span>
3. <span data-ttu-id="08fa8-150">Írjon be egy értéket a Mértékegység mezőbe.</span><span class="sxs-lookup"><span data-stu-id="08fa8-150">In the Unit field, type a value.</span></span>
4. <span data-ttu-id="08fa8-151">Válasszon ki egy időegységet.</span><span class="sxs-lookup"><span data-stu-id="08fa8-151">Select the Time unit.</span></span>
5. <span data-ttu-id="08fa8-152">Adjon meg egy számot a Mennyiségenként mezőben.</span><span class="sxs-lookup"><span data-stu-id="08fa8-152">In the Per quantity field, enter a number.</span></span>
6. <span data-ttu-id="08fa8-153">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="08fa8-153">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="08fa8-154">A várakozási idő nem kötelező.</span><span class="sxs-lookup"><span data-stu-id="08fa8-154">Queue times are optional.</span></span>  
7. <span data-ttu-id="08fa8-155">Adjon meg egy számot az Idő mezőben.</span><span class="sxs-lookup"><span data-stu-id="08fa8-155">In the Time field, enter a number.</span></span>
8. <span data-ttu-id="08fa8-156">Írjon be egy értéket a Mértékegység mezőbe.</span><span class="sxs-lookup"><span data-stu-id="08fa8-156">In the Unit field, type a value.</span></span>
9. <span data-ttu-id="08fa8-157">Válasszon ki egy időegységet.</span><span class="sxs-lookup"><span data-stu-id="08fa8-157">Select the Time unit.</span></span>
10. <span data-ttu-id="08fa8-158">Adjon meg egy számot a Mennyiségenként mezőben.</span><span class="sxs-lookup"><span data-stu-id="08fa8-158">In the Per quantity field, enter a number.</span></span>
11. <span data-ttu-id="08fa8-159">Kattintson a Tovább gombra.</span><span class="sxs-lookup"><span data-stu-id="08fa8-159">Click Next.</span></span>
12. <span data-ttu-id="08fa8-160">Kattintson a Finish gombra.</span><span class="sxs-lookup"><span data-stu-id="08fa8-160">Click Finish.</span></span>
13. <span data-ttu-id="08fa8-161">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="08fa8-161">Close the page.</span></span>


