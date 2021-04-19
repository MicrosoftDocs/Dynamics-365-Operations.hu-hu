---
title: Lean manufacturing gyártási folyamattevékenységek létrehozása
description: Hozzon létre folyamattevékenységet a lean manufacturing számára.
author: cvocph
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LeanProductionFlow, PlanActivity, PlanActivityWizard, LeanWorkCellLookup, InventLocationIdLookup, PlanActivityDetails, KanbanJobPickingListPart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 46d6b7696d606333a170eaa1c06b9e0503ae1e02
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5829018"
---
# <a name="create-process-activities-for-lean-manufacturing"></a><span data-ttu-id="d344a-103">Lean manufacturing gyártási folyamattevékenységek létrehozása</span><span class="sxs-lookup"><span data-stu-id="d344a-103">Create process activities for lean manufacturing</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="d344a-104">Hozzon létre folyamattevékenységet a lean manufacturing számára.</span><span class="sxs-lookup"><span data-stu-id="d344a-104">Create a process activity for lean manufacturing.</span></span> 

<span data-ttu-id="d344a-105">Előfeltételek:</span><span class="sxs-lookup"><span data-stu-id="d344a-105">Prerequisites:</span></span> 

1. <span data-ttu-id="d344a-106">Létre kell hozni a termelési folyamatot és a nem aktív verziót.</span><span class="sxs-lookup"><span data-stu-id="d344a-106">A production flow and version that is not active must be created.</span></span>

2. <span data-ttu-id="d344a-107">Munkacellát kell létrehozni.</span><span class="sxs-lookup"><span data-stu-id="d344a-107">A work cell must be created.</span></span>


## <a name="find-the-production-flow-version"></a><span data-ttu-id="d344a-108">Termelési folyamat verziójának megkeresése</span><span class="sxs-lookup"><span data-stu-id="d344a-108">Find the production flow version</span></span>
1. <span data-ttu-id="d344a-109">Ugrás a Gyártásvezérléshez > Beállítás > Lean típusú termelési folyamat > Termelési folyamatok lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d344a-109">Go to Production control > Setup > Lean production flow > Production flows.</span></span>
2. <span data-ttu-id="d344a-110">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="d344a-110">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="d344a-111">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="d344a-111">In the list, click the link in the selected row.</span></span>

## <a name="create-a-new-activity"></a><span data-ttu-id="d344a-112">Új tevékenység létrehozása</span><span class="sxs-lookup"><span data-stu-id="d344a-112">Create a new activity</span></span>
1. <span data-ttu-id="d344a-113">Kattintson a Tevékenységek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d344a-113">Click Activities.</span></span>
    * <span data-ttu-id="d344a-114">Győződjön meg arról, hogy a kiválasztott termelési folyamat rendelkezik vázlatverzióval, és válassza ki azt a verziót.</span><span class="sxs-lookup"><span data-stu-id="d344a-114">Ensure that the selected production flow has a version in draft and select that version.</span></span>  
2. <span data-ttu-id="d344a-115">Kattintson az Új tervezett tevékenység létrehozása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d344a-115">Click Create new plan activity.</span></span>
3. <span data-ttu-id="d344a-116">Kattintson a Tovább gombra.</span><span class="sxs-lookup"><span data-stu-id="d344a-116">Click Next.</span></span>
4. <span data-ttu-id="d344a-117">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="d344a-117">In the Name field, type a value.</span></span>
5. <span data-ttu-id="d344a-118">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="d344a-118">In the Name field, type a value.</span></span>
    * <span data-ttu-id="d344a-119">Vegye figyelembe, hogy az adott termelési folyamat nevének egyedinek kell lennie minden verzióban.</span><span class="sxs-lookup"><span data-stu-id="d344a-119">Note that the name must be unique for a given production flow for all versions.</span></span>  
6. <span data-ttu-id="d344a-120">Adjon meg egy számot az Folyamatmennyiség mezőben.</span><span class="sxs-lookup"><span data-stu-id="d344a-120">In the Process quantity field, enter a number.</span></span>
    * <span data-ttu-id="d344a-121">Vegye figyelembe, hogy a feldolgozott feladatmennyiségtől függetlenül a munkaköltség kiszámításakor ez a feladatonkénti minimum mennyiség.</span><span class="sxs-lookup"><span data-stu-id="d344a-121">Note that no matter what job quantity will be processed, this is the minimum quantity per job to calculate the labor cost.</span></span> <span data-ttu-id="d344a-122">Ha a feladatmennyiségek eltérnek ettől a mennyiségtől, munkaköltség-eltérés keletkezik.</span><span class="sxs-lookup"><span data-stu-id="d344a-122">If job quantities deviate from this quantity, labor cost variance will be created.</span></span>  
7. <span data-ttu-id="d344a-123">Kattintson a Tovább gombra.</span><span class="sxs-lookup"><span data-stu-id="d344a-123">Click Next.</span></span>

## <a name="select-the-work-cell"></a><span data-ttu-id="d344a-124">A munkacella kiválasztása</span><span class="sxs-lookup"><span data-stu-id="d344a-124">Select the work cell</span></span>
1. <span data-ttu-id="d344a-125">A Munkacella mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="d344a-125">In the Work cell field, click the drop-down button to open the lookup.</span></span>
2. <span data-ttu-id="d344a-126">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="d344a-126">In the list, click the link in the selected row.</span></span>

## <a name="define-the-inventory-updates"></a><span data-ttu-id="d344a-127">A készletfrissítések meghatározása</span><span class="sxs-lookup"><span data-stu-id="d344a-127">Define the inventory updates</span></span>
1. <span data-ttu-id="d344a-128">Jelölje be vagy törölje a jelet az Aktuális bevételezés frissítése jelölőnégyzetből.</span><span class="sxs-lookup"><span data-stu-id="d344a-128">Select or clear the Update on hand receipt check box.</span></span>
    * <span data-ttu-id="d344a-129">Ha az Elérhető frissítése = Nem, úgy is meghatározhatja a tevékenységet, hogy félkész terméket kapjon (a művelet nem éri el a következő anyagjegyzékszintet).</span><span class="sxs-lookup"><span data-stu-id="d344a-129">If Update On hand = No, you can define the activity to receive a semi-finished product (the activity does not reach the next BOM level).</span></span>    <span data-ttu-id="d344a-130">Félkész termékek felhasználását is kiválaszthatja.</span><span class="sxs-lookup"><span data-stu-id="d344a-130">You can also select to consume semi-finished products.</span></span>  

## <a name="define-the-picking-activities"></a><span data-ttu-id="d344a-131">A kitárolási tevékenységek meghatározása</span><span class="sxs-lookup"><span data-stu-id="d344a-131">Define the picking activities</span></span>
1. <span data-ttu-id="d344a-132">Kattintson a Tovább gombra.</span><span class="sxs-lookup"><span data-stu-id="d344a-132">Click Next.</span></span>
2. <span data-ttu-id="d344a-133">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="d344a-133">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="d344a-134">Az alapértelmezett kitárolási tevékenység a kiválasztott munkacella bemeneti helyére kerül létrehozásra.</span><span class="sxs-lookup"><span data-stu-id="d344a-134">A default picking activity is created for the input location of the selected work cell.</span></span>  
3. <span data-ttu-id="d344a-135">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="d344a-135">Click Add.</span></span>
    * <span data-ttu-id="d344a-136">Létrehozhat további kitárolási tevékenységet az egyes termékekre, amelyek nincsenek előkészítve a munkacella bemeneti tevékenységénél.</span><span class="sxs-lookup"><span data-stu-id="d344a-136">You can create additional picking activities for specific products, that are not staged at the work cell input activity.</span></span>  
4. <span data-ttu-id="d344a-137">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="d344a-137">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="d344a-138">A cikkmezőbe írjon egy értéket.</span><span class="sxs-lookup"><span data-stu-id="d344a-138">In the Item number field, type a value.</span></span>
6. <span data-ttu-id="d344a-139">A Raktár mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="d344a-139">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="d344a-140">Ezzel a meghatározással a tevékenység során felhasznált anyagok az alapértelmezett bemeneti raktárból és helyről származnak, kivéve a második kitárolási tevékenységben meghatározott cikk.</span><span class="sxs-lookup"><span data-stu-id="d344a-140">With this definition, all materials consumed in the activity are picked from the default input warehouse and location except the item that is defined in the second picking activity.</span></span> <span data-ttu-id="d344a-141">Ez a cikk egy másik raktárból és helyről kerül kitárolásra.</span><span class="sxs-lookup"><span data-stu-id="d344a-141">This item will be picked from a different warehouse and location.</span></span>  
7. <span data-ttu-id="d344a-142">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="d344a-142">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="d344a-143">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="d344a-143">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="d344a-144">Jelölje be vagy törölje a jelet a Selejt regisztrálása jelölőnégyzetből.</span><span class="sxs-lookup"><span data-stu-id="d344a-144">Select or clear the Register scrap check box.</span></span>
10. <span data-ttu-id="d344a-145">Kattintson a Tovább gombra.</span><span class="sxs-lookup"><span data-stu-id="d344a-145">Click Next.</span></span>

## <a name="define-the-activity-times"></a><span data-ttu-id="d344a-146">A tevékenységi idők meghatározása</span><span class="sxs-lookup"><span data-stu-id="d344a-146">Define the activity times</span></span>
1. <span data-ttu-id="d344a-147">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="d344a-147">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="d344a-148">A Futásidő meghatározását meg kell adni.</span><span class="sxs-lookup"><span data-stu-id="d344a-148">The definition of a Runtime is required.</span></span> <span data-ttu-id="d344a-149">A Futásidő a költségek és a kanbanfeladatok átfutási idejének kiszámítására szolgál.</span><span class="sxs-lookup"><span data-stu-id="d344a-149">The Runtime is used to calculate costs and the throughput times of the kanban jobs.</span></span> <span data-ttu-id="d344a-150">A futásidő nem a kapacitásterhelés és a felhasználás kiszámítására szolgál, ezt a ciklusidő számítja ki a termelésifolyamat-verzió feladat segítségével.</span><span class="sxs-lookup"><span data-stu-id="d344a-150">Runtimes are not used to calculate capacity load and consumption, this is calculated by cycle time, derived from the production flow version task.</span></span>  
2. <span data-ttu-id="d344a-151">Adjon meg egy számot az Idő mezőben.</span><span class="sxs-lookup"><span data-stu-id="d344a-151">In the Time field, enter a number.</span></span>
3. <span data-ttu-id="d344a-152">Írjon be egy értéket a Mértékegység mezőbe.</span><span class="sxs-lookup"><span data-stu-id="d344a-152">In the Unit field, type a value.</span></span>
4. <span data-ttu-id="d344a-153">Válasszon ki egy időegységet.</span><span class="sxs-lookup"><span data-stu-id="d344a-153">Select the Time unit.</span></span>
5. <span data-ttu-id="d344a-154">Adjon meg egy számot a Mennyiségenként mezőben.</span><span class="sxs-lookup"><span data-stu-id="d344a-154">In the Per quantity field, enter a number.</span></span>
6. <span data-ttu-id="d344a-155">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="d344a-155">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="d344a-156">A várakozási idő nem kötelező.</span><span class="sxs-lookup"><span data-stu-id="d344a-156">Queue times are optional.</span></span>  
7. <span data-ttu-id="d344a-157">Adjon meg egy számot az Idő mezőben.</span><span class="sxs-lookup"><span data-stu-id="d344a-157">In the Time field, enter a number.</span></span>
8. <span data-ttu-id="d344a-158">Írjon be egy értéket a Mértékegység mezőbe.</span><span class="sxs-lookup"><span data-stu-id="d344a-158">In the Unit field, type a value.</span></span>
9. <span data-ttu-id="d344a-159">Válasszon ki egy időegységet.</span><span class="sxs-lookup"><span data-stu-id="d344a-159">Select the Time unit.</span></span>
10. <span data-ttu-id="d344a-160">Adjon meg egy számot a Mennyiségenként mezőben.</span><span class="sxs-lookup"><span data-stu-id="d344a-160">In the Per quantity field, enter a number.</span></span>
11. <span data-ttu-id="d344a-161">Kattintson a Tovább gombra.</span><span class="sxs-lookup"><span data-stu-id="d344a-161">Click Next.</span></span>
12. <span data-ttu-id="d344a-162">Kattintson a Finish gombra.</span><span class="sxs-lookup"><span data-stu-id="d344a-162">Click Finish.</span></span>
13. <span data-ttu-id="d344a-163">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="d344a-163">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]