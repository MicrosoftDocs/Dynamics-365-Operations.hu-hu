--- 
title: "Rögzített mennyiségű kanbanszabály létrehozása gyártáshoz"
description: "Ez az eljárás a rögzített gyártású kanbanszabály létrehozására koncentrál az átalakítási tevékenységek elindításához egy munkacellában, lean környezetben."
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
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: a4ee8161803fc64e254b165ab8b8baac5dbaf0a2
ms.contentlocale: hu-hu
ms.lasthandoff: 04/13/2018

---
# <a name="create-a-fixed-quantity-kanban-rule-for-manufacturing"></a><span data-ttu-id="be589-103">Rögzített mennyiségű kanbanszabály létrehozása gyártáshoz</span><span class="sxs-lookup"><span data-stu-id="be589-103">Create a fixed quantity kanban rule for manufacturing</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="be589-104">Ez az eljárás a rögzített gyártású kanbanszabály létrehozására koncentrál az átalakítási tevékenységek elindításához egy munkacellában, lean környezetben.</span><span class="sxs-lookup"><span data-stu-id="be589-104">This procedure focuses on the setup needed to create a fixed manufacturing kanban rule for triggering transforming activities, at a work cell, in a lean environment.</span></span> <span data-ttu-id="be589-105">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="be589-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="be589-106">Ez az eljárás a Folyamatmérnök vagy az Érték-előállítási vezető munkáját segíti, mert ők készítik elő az új vagy módosított termék termelését.</span><span class="sxs-lookup"><span data-stu-id="be589-106">This procedure is intended for the Process Engineer or the Value Stream Manager, as they prepare production of a new or modified product.</span></span>


## <a name="create-new-kanban-rule"></a><span data-ttu-id="be589-107">Új kanbanszabály létrehozása</span><span class="sxs-lookup"><span data-stu-id="be589-107">Create new kanban rule</span></span>
1. <span data-ttu-id="be589-108">Ugorjon a Kanbanszabályokhoz.</span><span class="sxs-lookup"><span data-stu-id="be589-108">Go to Kanban rules.</span></span>
2. <span data-ttu-id="be589-109">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="be589-109">Click New.</span></span>
    * <span data-ttu-id="be589-110">Az alapértelmezett típus a Gyártás és a Feltöltési stratégia Rögzített.</span><span class="sxs-lookup"><span data-stu-id="be589-110">Notice that the default Type is Manufacturing and Replenishment strategy is Fixed.</span></span> <span data-ttu-id="be589-111">Ezeket a paramétereket nem kell megváltoztatnia.</span><span class="sxs-lookup"><span data-stu-id="be589-111">You do not have to change these parameters.</span></span>  
3. <span data-ttu-id="be589-112">Az Első tervezési tevékenység mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="be589-112">In the First plan activity field, enter or select a value.</span></span>
    * <span data-ttu-id="be589-113">Ez a tevékenység megtörténik kanbanok esetén a jelen kanbanszabály alapján.</span><span class="sxs-lookup"><span data-stu-id="be589-113">This is the activity that will be performed for kanbans created based on this kanban rule.</span></span>  <span data-ttu-id="be589-114">Válassza ki a „SpeakerTestAndPackaging” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="be589-114">Select 'SpeakerTestAndPackaging'.</span></span>  
4. <span data-ttu-id="be589-115">A Részletek szakasz kibontása.</span><span class="sxs-lookup"><span data-stu-id="be589-115">Expand the Details section.</span></span>
5. <span data-ttu-id="be589-116">A Termék mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="be589-116">In the Product field, enter or select a value.</span></span>
    * <span data-ttu-id="be589-117">Válassza az L0050 lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="be589-117">Select L0050.</span></span>  
6. <span data-ttu-id="be589-118">A Mértékegység mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="be589-118">In the Unit of measure field, enter or select a value.</span></span>
    * <span data-ttu-id="be589-119">Válassza ki a perceket.</span><span class="sxs-lookup"><span data-stu-id="be589-119">Select minutes.</span></span>  
7. <span data-ttu-id="be589-120">Adjon meg egy számot az Átfutási idő mezőben.</span><span class="sxs-lookup"><span data-stu-id="be589-120">In the Lead time field, enter a number.</span></span>
    * <span data-ttu-id="be589-121">Adja meg az 5 értéket.</span><span class="sxs-lookup"><span data-stu-id="be589-121">Enter 5.</span></span>  

## <a name="set-quantities"></a><span data-ttu-id="be589-122">Mennyiségek beállítása</span><span class="sxs-lookup"><span data-stu-id="be589-122">Set quantities</span></span>
1. <span data-ttu-id="be589-123">Bontsa ki a Mennyiségek szakaszt.</span><span class="sxs-lookup"><span data-stu-id="be589-123">Expand the Quantities section.</span></span>
2. <span data-ttu-id="be589-124">Állítsa az Alapértelmezett mennyiséget a „10” értékre.</span><span class="sxs-lookup"><span data-stu-id="be589-124">Set Default quantity to '10'.</span></span>
    * <span data-ttu-id="be589-125">Ez a mennyiség átkerül az összes kanbanba.</span><span class="sxs-lookup"><span data-stu-id="be589-125">This is the quantity that will be transferred for each kanban.</span></span>  
3. <span data-ttu-id="be589-126">Jelölje be a Termékmennyiségi különbözet jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="be589-126">Select the Product quantity variance check box.</span></span>
    * <span data-ttu-id="be589-127">Ezzel a kiválasztott kanbanok az alapértelmezett értéktől eltérően fejeződnek be.</span><span class="sxs-lookup"><span data-stu-id="be589-127">With this, selected kanbans can be completed with a variance from the default quantity.</span></span>  <span data-ttu-id="be589-128">Ha a kanbanokat 8–12 közötti értékkel kívánja befejezni, állítsa mindkét különbözetet 2-re.</span><span class="sxs-lookup"><span data-stu-id="be589-128">To allow kanbans to be completed with a quantity from 8 to 12, set both variances to 2.</span></span>  
4. <span data-ttu-id="be589-129">Állítsa az alábbi Eltérést „2” értékre.</span><span class="sxs-lookup"><span data-stu-id="be589-129">Set Variance below to '2'.</span></span>
    * <span data-ttu-id="be589-130">Így a befejezés 10 - 2 =8 értékig lehetséges.</span><span class="sxs-lookup"><span data-stu-id="be589-130">This will allow completing down to 10 - 2 = 8</span></span>  
5. <span data-ttu-id="be589-131">Állítsa a fenti Eltérést „2” értékre.</span><span class="sxs-lookup"><span data-stu-id="be589-131">Set Variance above to '2'.</span></span>
    * <span data-ttu-id="be589-132">Így a befejezés 10 + 2 =12 értékig lehetséges.</span><span class="sxs-lookup"><span data-stu-id="be589-132">This will allow completing up to 10 + 2 = 12</span></span>  
6. <span data-ttu-id="be589-133">Adjon meg egy számot a Rögzített kanbanmennyiség mezőben.</span><span class="sxs-lookup"><span data-stu-id="be589-133">In the Fixed kanban quantity field, enter a number.</span></span>
    * <span data-ttu-id="be589-134">Ez az aktív kanbanok mennyisége.</span><span class="sxs-lookup"><span data-stu-id="be589-134">This is the amount of kanbans that should be active.</span></span> <span data-ttu-id="be589-135">Ebben az esetben 5 kanban van, melyek mindegyike 10-et dolgoz fel.</span><span class="sxs-lookup"><span data-stu-id="be589-135">In this case, 5 kanbans processing 10 each.</span></span>  
7. <span data-ttu-id="be589-136">A Minimális figyelmeztetési határ mezőben adja meg a „2” értéket.</span><span class="sxs-lookup"><span data-stu-id="be589-136">In the Alert boundary minimum field, enter '2'.</span></span>
    * <span data-ttu-id="be589-137">Ennek segítségével nyomon követik azon teljes kanbanok minimum mennyiségét, amelyeknek a célhelyen kellene lenni.</span><span class="sxs-lookup"><span data-stu-id="be589-137">Used to keep track of the minimum amount of full kanbans that should be at the destination.</span></span> <span data-ttu-id="be589-138">Például ezt használják a kanbanmennyiség ellenőrzésére.</span><span class="sxs-lookup"><span data-stu-id="be589-138">For example, this is used on the kanban quantity overview.</span></span>  
8. <span data-ttu-id="be589-139">A Maximális figyelmeztetési határ mezőben adja meg a „4” értéket.</span><span class="sxs-lookup"><span data-stu-id="be589-139">In the Alert boundary maximum field, enter '4'.</span></span>
    * <span data-ttu-id="be589-140">Ennek segítségével nyomon követik azon teljes kanbanok maximum mennyiségét, amelyeknek a célhelyen kellene lenni.</span><span class="sxs-lookup"><span data-stu-id="be589-140">Used to keep track of the maximum amount of full kanbans that should be at the destination.</span></span> <span data-ttu-id="be589-141">Például ezt használják a kanbanmennyiség ellenőrzésére.</span><span class="sxs-lookup"><span data-stu-id="be589-141">For example, this is used on the kanban quantity overview.</span></span>  
9. <span data-ttu-id="be589-142">Az Automatikus tervezési mennyiség mezőben adja meg az „1” értéket.</span><span class="sxs-lookup"><span data-stu-id="be589-142">In the Automatic planning quantity field, enter '1'.</span></span>
    * <span data-ttu-id="be589-143">Ha ezt 1-re állítja, a kanbanok tervezése automatikusan történik.</span><span class="sxs-lookup"><span data-stu-id="be589-143">Setting this to 1 means that every kanban will be automatically planned.</span></span>   <span data-ttu-id="be589-144">Ha 3-at adnánk meg, a kanbanok tervezése nem történne meg, amíg 3 kanban tervezésre készen nem áll.</span><span class="sxs-lookup"><span data-stu-id="be589-144">If we entered 3, the kanbans would not be planned until 3 empty kanbans are ready for planning.</span></span> <span data-ttu-id="be589-145">Ennek segítségével csoportosítható a munka, és elkerülhető a túl sok beállítás.</span><span class="sxs-lookup"><span data-stu-id="be589-145">This is useful for grouping work and avoiding too much setup.</span></span>  

## <a name="create-kanbans"></a><span data-ttu-id="be589-146">Kanbanok létrehozása</span><span class="sxs-lookup"><span data-stu-id="be589-146">Create Kanbans</span></span>
1. <span data-ttu-id="be589-147">Bontsa ki a Kanbanok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="be589-147">Expand the Kanbans section.</span></span>
2. <span data-ttu-id="be589-148">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="be589-148">Click Save.</span></span>
    * <span data-ttu-id="be589-149">A kanbanszabályt a kanbanok létrehozása előtt el kell menteni.</span><span class="sxs-lookup"><span data-stu-id="be589-149">The kanban rule needs to be saved before kanbans can be created.</span></span>  
3. <span data-ttu-id="be589-150">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="be589-150">Click Add.</span></span>
    * <span data-ttu-id="be589-151">Vegye figyelembe, hogy nincsenek aktív kanbanok, ennek köszönhetően a javasolt „Új kanbanok száma” 5.</span><span class="sxs-lookup"><span data-stu-id="be589-151">Note that there are no active kanbans, due to this the suggested 'Number of new kanbans' are 5.</span></span> <span data-ttu-id="be589-152">Ez egyenlő a Rögzített kanbanmennyiséggel.</span><span class="sxs-lookup"><span data-stu-id="be589-152">This is equal to the 'Fixed kanban quantity'.</span></span>  
4. <span data-ttu-id="be589-153">Kattintson a Létrehozás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="be589-153">Click Create.</span></span>
    * <span data-ttu-id="be589-154">Ez 5 kanbant hoz létre.</span><span class="sxs-lookup"><span data-stu-id="be589-154">This will create 5 kanbans.</span></span>  
    * <span data-ttu-id="be589-155">Vegye figyelembe, hogy ehhez a gyártási kanbanszabályhoz 5 kanban, egyenként 10 került létrehozásra.</span><span class="sxs-lookup"><span data-stu-id="be589-155">Note that 5 kanbans, for 10 each, was created for this manufacturing kanban rule.</span></span> <span data-ttu-id="be589-156">Ez az eljárás utolsó lépése.</span><span class="sxs-lookup"><span data-stu-id="be589-156">This is the last step in this procedure.</span></span>  


