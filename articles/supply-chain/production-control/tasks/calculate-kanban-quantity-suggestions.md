---
title: Kanbanmennyiség-javaslatok kiszámítása
description: Ez a folyamat a kanbanméret és -mennyiség egy adott kanbanszabályhoz történő optimalizálására irányul a kanbanmennyiség-számítás használatával.
author: ChristianRytt
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 540dd32c5da5859ef5e69f55d6806eada90bc840
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1558194"
---
# <a name="calculate-kanban-quantity-suggestions"></a><span data-ttu-id="524d5-103">Kanbanmennyiség-javaslatok kiszámítása</span><span class="sxs-lookup"><span data-stu-id="524d5-103">Calculate kanban quantity suggestions</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="524d5-104">Ez a folyamat a kanbanméret és -mennyiség egy adott kanbanszabályhoz történő optimalizálására irányul a kanbanmennyiség-számítás használatával.</span><span class="sxs-lookup"><span data-stu-id="524d5-104">This procedure focuses on optimizing the kanban size and quantities for a specific kanban rule by using the kanban quantity calculation.</span></span> <span data-ttu-id="524d5-105">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="524d5-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="524d5-106">Ez az eljárás az érték-előállítási folyamat vezetője számára készült.</span><span class="sxs-lookup"><span data-stu-id="524d5-106">This procedure is intended for the value stream manager.</span></span> <span data-ttu-id="524d5-107">Előfeltétele az Új kanban mennyiségszámítási irányelv hozzáadása a kanbanszabályhoz eljárás elvégzése.</span><span class="sxs-lookup"><span data-stu-id="524d5-107">It is a prerequisite that you have completed the procedure Add a new kanban quantity calculation policy to a kanban rule.</span></span>


## <a name="create-a-kanban-quantity-calculation"></a><span data-ttu-id="524d5-108">Kanbanmennyiség-számítás létrehozása</span><span class="sxs-lookup"><span data-stu-id="524d5-108">Create a kanban quantity calculation</span></span>
1. <span data-ttu-id="524d5-109">Ugorjon a Gyártásvezérlés > Időszakos feladatok > Kanbanmennyiség-számítás > Kanbanmennyiség kiszámítása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="524d5-109">Go to Production control > Periodic tasks > Kanban quantity calculation > Calculate kanban quantity.</span></span>
2. <span data-ttu-id="524d5-110">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="524d5-110">Click New.</span></span>
3. <span data-ttu-id="524d5-111">A Név mezőbe írja be a „Speaker2016” szöveget.</span><span class="sxs-lookup"><span data-stu-id="524d5-111">In the Name field, type 'Speaker2016'.</span></span>
4. <span data-ttu-id="524d5-112">A Név mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="524d5-112">In the Name field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="524d5-113">Válassza ki a létrehozott irányelvet az Új kanban mennyiségszámítási irányelv hozzáadása a kanbanszabályhoz eljárásban.</span><span class="sxs-lookup"><span data-stu-id="524d5-113">Select the policy that you have created in the procedure Add a new kanban quantity calculation policy to a kanban rule.</span></span> <span data-ttu-id="524d5-114">Például, Speaker2016.</span><span class="sxs-lookup"><span data-stu-id="524d5-114">For example, Speaker2016.</span></span>  
5. <span data-ttu-id="524d5-115">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="524d5-115">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="524d5-116">A Szabály aktiválási dátuma mezőben következőképpen adja meg a dátumot és az időt „2012-12-17T08:00:00”.</span><span class="sxs-lookup"><span data-stu-id="524d5-116">In the Rule active as of date field, set the date and time to '2012-12-17T08:00:00'.</span></span>
    * <span data-ttu-id="524d5-117">Ez a dátum szolgál a kanbanmennyiség számításába bevont rögzített kanbanszabályok meghatározásának alapjául.</span><span class="sxs-lookup"><span data-stu-id="524d5-117">This date serves as the basis for determining which fixed kanban rules are included in the kanban quantity calculation.</span></span>  
7. <span data-ttu-id="524d5-118">A Teljesített igény időszakának kezdő dátuma mezőben következőképpen adja meg a dátumot és az időt „2012-11-17T09:00:00”.</span><span class="sxs-lookup"><span data-stu-id="524d5-118">In the Fulfilled demand period start date field, set the date and time to '2012-11-17T09:00:00'.</span></span>
    * <span data-ttu-id="524d5-119">Az a dátum, amikortól a múltbeli igénytranzakciók bekerülnek a kanbanmennyiség számításába.</span><span class="sxs-lookup"><span data-stu-id="524d5-119">The date from when past demand transactions are included to calculate the kanban quantity.</span></span>  
8. <span data-ttu-id="524d5-120">A Teljesített igény időszakának záró dátuma mezőben következőképpen adja meg a dátumot és az időt „2012-12-17T07:59:59”.</span><span class="sxs-lookup"><span data-stu-id="524d5-120">In the Fulfilled demand period end date field, set the date and time to '2012-12-17T07:59:59'.</span></span>
    * <span data-ttu-id="524d5-121">Az a dátum, ameddig a múltbeli igénytranzakciók bekerülnek a kanbanmennyiség számításába.</span><span class="sxs-lookup"><span data-stu-id="524d5-121">The date until when past demand transactions are included to calculate the kanban quantity.</span></span>  
9. <span data-ttu-id="524d5-122">Az Igényidőszak kezdő dátuma mezőben következőképpen adja meg a dátumot és az időt „2012-12-17T08:00:00”.</span><span class="sxs-lookup"><span data-stu-id="524d5-122">In the Demand period start date field, set the date and time to '2012-12-17T08:00:00'.</span></span>
    * <span data-ttu-id="524d5-123">Az a dátum, amikortól az aktuális igénytranzakciók bekerülnek a rögzített kanbanmennyiség számításába.</span><span class="sxs-lookup"><span data-stu-id="524d5-123">The date from when current demand transactions are included to calculate the kanban quantity.</span></span>  
10. <span data-ttu-id="524d5-124">Az Igényidőszak záró dátuma mezőben következőképpen adja meg a dátumot és az időt „2013-01-16T07:59:59”.</span><span class="sxs-lookup"><span data-stu-id="524d5-124">In the Demand period end date field, set the date and time to '2013-01-16T07:59:59'.</span></span>
    * <span data-ttu-id="524d5-125">Az a dátum, ameddig az aktuális igénytranzakciók bekerülnek a kanbanmennyiség számításába.</span><span class="sxs-lookup"><span data-stu-id="524d5-125">The date until when current demand transactions are included to calculate the kanban quantity.</span></span>  

## <a name="generate-kanban-quantity-proposal"></a><span data-ttu-id="524d5-126">Kanbanmennyiség-javaslat generálása</span><span class="sxs-lookup"><span data-stu-id="524d5-126">Generate kanban quantity proposal</span></span>
1. <span data-ttu-id="524d5-127">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="524d5-127">Click Save.</span></span>
2. <span data-ttu-id="524d5-128">Kattintson a Létrehozás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="524d5-128">Click Generate.</span></span>
    * <span data-ttu-id="524d5-129">Ez létrehoz egy kanbanmennyiségi javaslatsort a 000020 kanbanszabályhoz.</span><span class="sxs-lookup"><span data-stu-id="524d5-129">This generates a kanban quantity proposal line for the kanban rule 000020.</span></span>  

## <a name="run-kanban-quantity-calculation"></a><span data-ttu-id="524d5-130">Kanbanmennyiség-számítás futtatása</span><span class="sxs-lookup"><span data-stu-id="524d5-130">Run kanban quantity calculation</span></span>
1. <span data-ttu-id="524d5-131">Kattintson a Számítás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="524d5-131">Click Calculate.</span></span>
    * <span data-ttu-id="524d5-132">Ez számítja ki a kanbanmennyiség-javaslatot.</span><span class="sxs-lookup"><span data-stu-id="524d5-132">This calculates the kanban quantity proposal.</span></span>  
2. <span data-ttu-id="524d5-133">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="524d5-133">Click OK.</span></span>
3. <span data-ttu-id="524d5-134">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="524d5-134">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="524d5-135">Ne feledje, hogy a javasolt kanbanmennyiség a 2.</span><span class="sxs-lookup"><span data-stu-id="524d5-135">Notice the suggested kanban quantity is 2.</span></span>  

## <a name="change-product-quantity-and-calculate-again"></a><span data-ttu-id="524d5-136">Termékmennyiség módosítása és számítás újbóli elvégzése</span><span class="sxs-lookup"><span data-stu-id="524d5-136">Change product quantity and calculate again</span></span>
1. <span data-ttu-id="524d5-137">Állítsa a Termékmennyiséget az „5” értékre.</span><span class="sxs-lookup"><span data-stu-id="524d5-137">Set Product quantity to '5'.</span></span>
2. <span data-ttu-id="524d5-138">Kattintson a Számítás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="524d5-138">Click Calculate.</span></span>
3. <span data-ttu-id="524d5-139">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="524d5-139">Click OK.</span></span>
    * <span data-ttu-id="524d5-140">Ne feledje, hogy 5-ös kanbanmennyiségnél a javasolt kanbanmennyiség 4-re változik.</span><span class="sxs-lookup"><span data-stu-id="524d5-140">Notice that with a kanban quantity of 5, the suggestion is changed to a kanban quantity of 4.</span></span>  
    * <span data-ttu-id="524d5-141">Ennek oka az, hogy alacsonyabb termékmennyiség esetén több kanbanbra van szükség az igény teljesítésére.</span><span class="sxs-lookup"><span data-stu-id="524d5-141">This is caused by the fact that with a lower product quantity, we need more kanbans to fulfill the demand.</span></span>  

## <a name="update-kanban-rule"></a><span data-ttu-id="524d5-142">Kanbanszabály frissítése</span><span class="sxs-lookup"><span data-stu-id="524d5-142">Update kanban rule</span></span>
1. <span data-ttu-id="524d5-143">A Szabály hatályba lépési dátuma mezőben adjon meg egy dátumot és időpontot.</span><span class="sxs-lookup"><span data-stu-id="524d5-143">In the Rule effective date field, enter a date and time.</span></span>
    * <span data-ttu-id="524d5-144">Állítsa a „Szabály aktiválási dátuma” értéket egy jövőbeli dátumra.</span><span class="sxs-lookup"><span data-stu-id="524d5-144">Set the 'Rule active as of date' to a date in the future.</span></span> <span data-ttu-id="524d5-145">Például a mai dátum + egy év.</span><span class="sxs-lookup"><span data-stu-id="524d5-145">For example, today + one year.</span></span>  
2. <span data-ttu-id="524d5-146">Kattintson a Módosítás gombra.</span><span class="sxs-lookup"><span data-stu-id="524d5-146">Click Update.</span></span>
3. <span data-ttu-id="524d5-147">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="524d5-147">Click OK.</span></span>
4. <span data-ttu-id="524d5-148">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="524d5-148">Close the page.</span></span>

## <a name="validate-change-on-kanban-rule"></a><span data-ttu-id="524d5-149">Kanbanszabály módosításának ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="524d5-149">Validate change on kanban rule</span></span>
1. <span data-ttu-id="524d5-150">Ugorjon a Termékinformációk kezelése > A lean manufacturing > Kanbanszabályok lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="524d5-150">Go to Product information management > Lean manufacturing > Kanban rules.</span></span>
2. <span data-ttu-id="524d5-151">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="524d5-151">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="524d5-152">Válassza ki az előző alfeladatban létrehozott kanbanszabályt.</span><span class="sxs-lookup"><span data-stu-id="524d5-152">Select the kanban rule that was created in the previous sub-task.</span></span> <span data-ttu-id="524d5-153">Ez lesz az első kanbanszabály a számok szerint rendezett listában.</span><span class="sxs-lookup"><span data-stu-id="524d5-153">This should be the first kanban rule in the list sorted by number.</span></span>  
3. <span data-ttu-id="524d5-154">Bontsa ki a Részletek részt.</span><span class="sxs-lookup"><span data-stu-id="524d5-154">Toggle the expansion of the Details section.</span></span>
    * <span data-ttu-id="524d5-155">Ne feledkezzenek meg az érvénybe lépési dátumról, amely azt jelzi, hogy a szabály nem aktiválódik az adott dátumig.</span><span class="sxs-lookup"><span data-stu-id="524d5-155">Notice the effective date, which means that this rule is not activated until this date.</span></span>  
4. <span data-ttu-id="524d5-156">Bontsa ki a Mennyiségek részt.</span><span class="sxs-lookup"><span data-stu-id="524d5-156">Toggle the expansion of the Quantities section.</span></span>
    * <span data-ttu-id="524d5-157">Ne feledje, hogy ez a kanbanmennyiség-számítás során megadott alapértelmezett mennyiség.</span><span class="sxs-lookup"><span data-stu-id="524d5-157">Notice this is the default quantity that you entered on the kanban quantity calculation.</span></span>  
    * <span data-ttu-id="524d5-158">Ne feledje, hogy ez a rögzített 4-es kanbanmennyiség a kanbanmennyiség-számításból.</span><span class="sxs-lookup"><span data-stu-id="524d5-158">Notice this is the fixed kanban quantity of 4 from the kanban quantity calculation.</span></span>  
5. <span data-ttu-id="524d5-159">Kattintson a ListPanel fülre.</span><span class="sxs-lookup"><span data-stu-id="524d5-159">Click the ListPanel tab.</span></span>

