--- 
title: "Termelési feladatok sorrendje a folyamatszerű gyártáshoz"
description: "Ez az eljárásban példaként festék termékeket használ, hogy bemutassa, hogy hogyan lehet a szín és a csomag méretének prioritása szerint a tervezett rendeléseket rendezni."
author: ChristianRytt
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
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: a25a4575ca1600b07b2dac5949c8775bcd162650
ms.contentlocale: hu-hu
ms.lasthandoff: 08/29/2017

---
# <a name="sequence-production-jobs-for-process-manufacturing"></a><span data-ttu-id="1e5c1-103">Termelési feladatok sorrendje a folyamatszerű gyártáshoz</span><span class="sxs-lookup"><span data-stu-id="1e5c1-103">Sequence production jobs for process manufacturing</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="1e5c1-104">Ez az eljárásban példaként festék termékeket használ, hogy bemutassa, hogy hogyan lehet a szín és a csomag méretének prioritása szerint a tervezett rendeléseket rendezni.</span><span class="sxs-lookup"><span data-stu-id="1e5c1-104">This procedure uses paint products as an example to show how to sequence planned orders according to the priority of color and package size.</span></span> <span data-ttu-id="1e5c1-105">Ez az eljárás az USPI bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="1e5c1-105">The demo data company used to create this procedure is USPI.</span></span> <span data-ttu-id="1e5c1-106">Ezt az eljárást a termeléstervező használja.</span><span class="sxs-lookup"><span data-stu-id="1e5c1-106">This procedure is intended for the production planner.</span></span>


## <a name="run-master-planning-for-uspi"></a><span data-ttu-id="1e5c1-107">Az Alaptervezés futtatása az USPI-re vonatkozóan</span><span class="sxs-lookup"><span data-stu-id="1e5c1-107">Run master planning for USPI</span></span>
1. <span data-ttu-id="1e5c1-108">Ugorjon az Alaptervezés > Alaptervezés > Futtatás > Alaptervezés pontra.</span><span class="sxs-lookup"><span data-stu-id="1e5c1-108">Go to Master planning > Master planning > Run > Master planning.</span></span>
2. <span data-ttu-id="1e5c1-109">Az Alapterv mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="1e5c1-109">In the Master plan field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="1e5c1-110">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="1e5c1-110">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="1e5c1-111">MasterPlan kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="1e5c1-111">Select MasterPlan.</span></span>  
4. <span data-ttu-id="1e5c1-112">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="1e5c1-112">Click OK.</span></span>
    * <span data-ttu-id="1e5c1-113">Ez indítja el az Alaptervezést a sorozat folyamatával együtt.</span><span class="sxs-lookup"><span data-stu-id="1e5c1-113">This starts Master Planning, including the sequence process.</span></span> <span data-ttu-id="1e5c1-114">Ez a folyamat néhány percig is eltarthat.</span><span class="sxs-lookup"><span data-stu-id="1e5c1-114">This process can take a few minutes.</span></span>  

## <a name="view-planned-orders-for-the-paint-products"></a><span data-ttu-id="1e5c1-115">A festék termékek tervezett rendeléseinek megtekintése</span><span class="sxs-lookup"><span data-stu-id="1e5c1-115">View planned orders for the paint products</span></span>
1. <span data-ttu-id="1e5c1-116">Ugorjon az Alaptervezés > Alaptervezés > Tervezett rendelések pontra.</span><span class="sxs-lookup"><span data-stu-id="1e5c1-116">Go to Master planning > Master planning > Planned orders.</span></span>
2. <span data-ttu-id="1e5c1-117">Bontsa ki a Cikk részletei adatterületet.</span><span class="sxs-lookup"><span data-stu-id="1e5c1-117">Expand the Item details FactBox.</span></span>
3. <span data-ttu-id="1e5c1-118">Bontsa ki az Ütemezés részletei adatterületet.</span><span class="sxs-lookup"><span data-stu-id="1e5c1-118">Expand the Schedule details FactBox.</span></span>
4. <span data-ttu-id="1e5c1-119">A Konstrukció mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="1e5c1-119">In the Plan field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="1e5c1-120">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="1e5c1-120">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="1e5c1-121">MasterPlan kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="1e5c1-121">Select MasterPlan.</span></span>  
6. <span data-ttu-id="1e5c1-122">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="1e5c1-122">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="1e5c1-123">A Gyorsszűrő használatával szűrjön rá a P300 értékű Cikkszám mezőkre.</span><span class="sxs-lookup"><span data-stu-id="1e5c1-123">Use the Quick Filter to filter on the Item number field with a value of 'P300'.</span></span>
    * <span data-ttu-id="1e5c1-124">Oldja fel a jobbra görgetéshez a rendelési dátum és a szállítási dátum megtekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="1e5c1-124">Unlock to scroll to the right to see the order date and delivery date.</span></span> <span data-ttu-id="1e5c1-125">Vegye figyelembe, hogy ezek a cikkek egy Mai rendelési dátummal rendelkeznek és a tervezett megrendelések szállítási dátumai nincsenek rendezve a szín és a csomag méret prioritása után, ahogyan ez a termék nevében látható.</span><span class="sxs-lookup"><span data-stu-id="1e5c1-125">Notice that these items have an order date of Today and the delivery dates for the planned orders are not sequenced after the priority of color and package size, as shown in the product name.</span></span> <span data-ttu-id="1e5c1-126">Egy cikkszám fölé viheti a mutatót a termék nevének és prioritásának megtekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="1e5c1-126">You can hover over an item number to see the product name and priority.</span></span>  

## <a name="sequence-planned-orders-for-paint"></a><span data-ttu-id="1e5c1-127">A szekventált tervezett rendelések a festésre vonatkozóan</span><span class="sxs-lookup"><span data-stu-id="1e5c1-127">Sequence planned orders for paint</span></span>
1. <span data-ttu-id="1e5c1-128">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="1e5c1-128">Close the page.</span></span>
2. <span data-ttu-id="1e5c1-129">Ugorjon az Alaptervezési > Alaptervezés > Szekventált tervezett rendelések pontra.</span><span class="sxs-lookup"><span data-stu-id="1e5c1-129">Go to Master planning > Master planning > Sequenced planned orders.</span></span>
3. <span data-ttu-id="1e5c1-130">Bontsa ki a Cikk részletei adatterületet.</span><span class="sxs-lookup"><span data-stu-id="1e5c1-130">Expand the Item details FactBox.</span></span>
4. <span data-ttu-id="1e5c1-131">Bontsa ki az Ütemezés részletei adatterületet.</span><span class="sxs-lookup"><span data-stu-id="1e5c1-131">Expand the Schedule details FactBox.</span></span>
    * <span data-ttu-id="1e5c1-132">Megjegyzés: Itt láthatja, hogy a tervezett rendelések kezdő dátumát/idejét a szín és a csomag méretének megfelelően egy 28 napos időszakon belül rendezték.</span><span class="sxs-lookup"><span data-stu-id="1e5c1-132">Note: Here you see that the Start date/time for the planned orders are sequenced according to color and package size within a bucket period of 28 days.</span></span> <span data-ttu-id="1e5c1-133">A Kampány mezőben egy számmal határozták meg ezeket az időszakokat.</span><span class="sxs-lookup"><span data-stu-id="1e5c1-133">These periods are defined by a number in the field Campaign.</span></span> <span data-ttu-id="1e5c1-134">A szekventált tervezett rendelés forma szokásos tervezett rendelési képernyőként működik, és a termeléstervező itt erősheti meg a tervezett rendeléseket.</span><span class="sxs-lookup"><span data-stu-id="1e5c1-134">The sequenced planned order form acts like the typical planned order form, and the production planner can firm the planned orders here.</span></span>  
5. <span data-ttu-id="1e5c1-135">Az összes sor megjelölése.</span><span class="sxs-lookup"><span data-stu-id="1e5c1-135">Mark all rows.</span></span>
6. <span data-ttu-id="1e5c1-136">Kattintson az Elfogadás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="1e5c1-136">Click Accept.</span></span>
    * <span data-ttu-id="1e5c1-137">Ez az eljárás a tervezett rendeléseket vagy az Elhalasztás vagy az Előleg kijelölt sorozatművelettel frissíti.</span><span class="sxs-lookup"><span data-stu-id="1e5c1-137">This will update the planned orders with the selected sequence action of either Postpone or Advance.</span></span>  

## <a name="verify-the-sequence-of-the-planned-orders"></a><span data-ttu-id="1e5c1-138">Ellenőrizze a tervezett rendelések sorrendjét</span><span class="sxs-lookup"><span data-stu-id="1e5c1-138">Verify the sequence of the planned orders</span></span>
1. <span data-ttu-id="1e5c1-139">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="1e5c1-139">Close the page.</span></span>
2. <span data-ttu-id="1e5c1-140">Ugorjon az Alaptervezés > Alaptervezés > Tervezett rendelések pontra.</span><span class="sxs-lookup"><span data-stu-id="1e5c1-140">Go to Master planning > Master planning > Planned orders.</span></span>
3. <span data-ttu-id="1e5c1-141">Bontsa ki a Cikk részletei adatterületet.</span><span class="sxs-lookup"><span data-stu-id="1e5c1-141">Expand the Item details FactBox.</span></span>
4. <span data-ttu-id="1e5c1-142">Bontsa ki az Ütemezés részletei adatterületet.</span><span class="sxs-lookup"><span data-stu-id="1e5c1-142">Expand the Schedule details FactBox.</span></span>
5. <span data-ttu-id="1e5c1-143">A Konstrukció mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="1e5c1-143">In the Plan field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="1e5c1-144">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="1e5c1-144">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="1e5c1-145">MasterPlan kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="1e5c1-145">Select MasterPlan.</span></span>  
7. <span data-ttu-id="1e5c1-146">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="1e5c1-146">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="1e5c1-147">A Gyorsszűrő használatával szűrjön rá a P300 értékű Cikkszám mezőkre.</span><span class="sxs-lookup"><span data-stu-id="1e5c1-147">Use the Quick Filter to filter on the Item number field with a value of 'P300'.</span></span>
    * <span data-ttu-id="1e5c1-148">Vegye figyelembe, hogy a rendelések rendezése már a szín vagy a méret prioritása szerint megtörtént és a tervezett rendelések a lehető legkorábbi rendelési- és szállítási dátum napján elkezdődtek.</span><span class="sxs-lookup"><span data-stu-id="1e5c1-148">Notice that the orders now are sequenced according to the priority of color and size and the planned orders start at the earliest order date and delivery date.</span></span> <span data-ttu-id="1e5c1-149">Ellenőrizze a Rendelési dátum oszlopát vagy a Kezdő dátumot az Ütemezés részletei FactBoxban.</span><span class="sxs-lookup"><span data-stu-id="1e5c1-149">Validate the Order date column or the Start date in the Schedule details FactBbox.</span></span>  


