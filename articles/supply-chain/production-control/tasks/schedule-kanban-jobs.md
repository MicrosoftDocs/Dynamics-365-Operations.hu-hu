---
title: Kanbanfeladatok ütemezése
description: Ez az eljárás egy adott munkacellához tartozó kanbanfeladatok ütemezési folyamatával foglalkozik.
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanJobSchedulingListPage, KanbanPeriodCapacityPart, SysLookupMultiSelectGrid, KanbanBoardScheduleJobForward
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5170fecf0190591d74f45d35fecc4472e7f5e900
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "359543"
---
# <a name="schedule-kanban-jobs"></a><span data-ttu-id="83c30-103">Kanbanfeladatok ütemezése</span><span class="sxs-lookup"><span data-stu-id="83c30-103">Schedule kanban jobs</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="83c30-104">Ez az eljárás egy adott munkacellához tartozó kanbanfeladatok ütemezési folyamatával foglalkozik.</span><span class="sxs-lookup"><span data-stu-id="83c30-104">This procedure focuses on scheduling process kanban jobs for a specific work cell.</span></span> <span data-ttu-id="83c30-105">Az „A feldolgozási kanbanfeladat előkészítése, amikor az anyagok nem elérhetők” eljárás előfeltétel, ha ilyen eljárást akar létrehozni.</span><span class="sxs-lookup"><span data-stu-id="83c30-105">The procedure "Prepare a process kanban job when materials are not available" is a prerequisite for creating this procedure.</span></span> <span data-ttu-id="83c30-106">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="83c30-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="83c30-107">Ez a feladat a kanbanokkal dolgozó üzemirányítási felügyelő és termeléstervező munkáját segíti.</span><span class="sxs-lookup"><span data-stu-id="83c30-107">This task is intended for the shop floor supervisor and production planner working with kanbans.</span></span>


## <a name="select-kanban-jobs-for-a-work-cell"></a><span data-ttu-id="83c30-108">Kanbanfeladatok kiválasztása munkacellához</span><span class="sxs-lookup"><span data-stu-id="83c30-108">Select kanban jobs for a work cell</span></span>
1. <span data-ttu-id="83c30-109">Ugorjon a Gyártásvezérlés > Kanban > Kanbanfeladat ütemezése lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="83c30-109">Go to Production control > Kanban > Kanban job scheduling.</span></span>
2. <span data-ttu-id="83c30-110">Bontsa ki az Időszak kapacitása adatterületet</span><span class="sxs-lookup"><span data-stu-id="83c30-110">Expand the Period capacity fact box</span></span>
    * <span data-ttu-id="83c30-111">Bontsa ki a Kanban adatterületet.</span><span class="sxs-lookup"><span data-stu-id="83c30-111">Expand the Kanban FactBox.</span></span>  
3. <span data-ttu-id="83c30-112">A Munkacella mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="83c30-112">In the Work cell field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="83c30-113">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="83c30-113">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="83c30-114">Jelölje ki az 1250 munkacellát.</span><span class="sxs-lookup"><span data-stu-id="83c30-114">Select work cell 1250.</span></span> <span data-ttu-id="83c30-115">Ez szűri a nézetet, így csak az 1250 munkacella munkái jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="83c30-115">This will filter the view to display only the jobs for work cell 1250.</span></span>  
5. <span data-ttu-id="83c30-116">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="83c30-116">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="83c30-117">Kattintson a Kiválasztás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="83c30-117">Click Select.</span></span>

## <a name="schedule-a-kanban-job-in-the-first-available-period"></a><span data-ttu-id="83c30-118">Kanbanfeladat ütemezése az első elérhető időszakra</span><span class="sxs-lookup"><span data-stu-id="83c30-118">Schedule a kanban job in the first available period</span></span>
1. <span data-ttu-id="83c30-119">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="83c30-119">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="83c30-120">Válassza ki a lista első sorát, amely Nem tervezett állapottal rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="83c30-120">Select the first row in the list that has the Not planned status.</span></span> <span data-ttu-id="83c30-121">A Feladatállapot mező pontozott ikonja a nem tervezett állapotra utal.</span><span class="sxs-lookup"><span data-stu-id="83c30-121">The dotted icon in the Job status field indicates not planned.</span></span>  
2. <span data-ttu-id="83c30-122">Kattintson az üzemezés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="83c30-122">Click Schedule.</span></span>
    * <span data-ttu-id="83c30-123">Ez a kanbanfeladatot az első elérhető időszakra ütemezi.</span><span class="sxs-lookup"><span data-stu-id="83c30-123">This will schedule the kanban job in the first available period.</span></span>  
    * <span data-ttu-id="83c30-124">A kanbanfeladat a lista végére került, mert a mától kezdődő időszakhoz lett hozzáadva.</span><span class="sxs-lookup"><span data-stu-id="83c30-124">Notice that the kanban job is moved to the end of the list because it has been added to the period starting from today.</span></span>  
    * <span data-ttu-id="83c30-125">Ha a mától induló időszak teljesen le van foglalva, a feladat átkerül az első elérhető időszakra.</span><span class="sxs-lookup"><span data-stu-id="83c30-125">If the period starting from today is fully booked, the job will be moved to the first available period.</span></span>  

## <a name="schedule-two-kanban-jobs-for-a-specific-day"></a><span data-ttu-id="83c30-126">Két kanbanfeladat ütemezése adott napra</span><span class="sxs-lookup"><span data-stu-id="83c30-126">Schedule two kanban jobs for a specific day</span></span>
1. <span data-ttu-id="83c30-127">Jelölje ki az 1. sort a listában.</span><span class="sxs-lookup"><span data-stu-id="83c30-127">In the list, select row 1.</span></span>
    * <span data-ttu-id="83c30-128">Azt látja, hogy az első sor a Feladatállapot mezőben a Nem tervezett állapottal rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="83c30-128">You should see that the first row has the Not planned status in the Job status field.</span></span>  
2. <span data-ttu-id="83c30-129">Jelölje ki az 2. sort a listában.</span><span class="sxs-lookup"><span data-stu-id="83c30-129">In the list, select row 2.</span></span>
    * <span data-ttu-id="83c30-130">A második sor a Nem tervezett állapottal rendelkezik a Feladatállapot mezőben.</span><span class="sxs-lookup"><span data-stu-id="83c30-130">You should see that the second row has the Not planned status in the Job status field.</span></span> <span data-ttu-id="83c30-131">Ezzel kiválasztotta az első két feladatot.</span><span class="sxs-lookup"><span data-stu-id="83c30-131">Now you have the first two jobs selected.</span></span>  
3. <span data-ttu-id="83c30-132">Az Ütemezés dátumtól gombra kattintva megnyithatja a legördülő párbeszédablakot.</span><span class="sxs-lookup"><span data-stu-id="83c30-132">Click Schedule from date to open the drop dialog.</span></span>
4. <span data-ttu-id="83c30-133">Jelölje be vagy törölje a jelölést a Kapacitáshiányra való reagálás felülbírálása négyzeten.</span><span class="sxs-lookup"><span data-stu-id="83c30-133">Check or uncheck the Override capacity shortage reaction box.</span></span>
    * <span data-ttu-id="83c30-134">Ezzel a beállítással felülírhatja az alapértelmezett kapacitáshiányra való reagálást.</span><span class="sxs-lookup"><span data-stu-id="83c30-134">This option allows you to override the default capacity shortage reaction.</span></span>  
5. <span data-ttu-id="83c30-135">A Kapacitáshiányra való reagálás mezőben válassza ki a „Hozzáadás a kért időszakhoz” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="83c30-135">In the Capacity shortage reaction field, select 'Add to the requested period'.</span></span>
    * <span data-ttu-id="83c30-136">Ez a lehetőség biztosítja, hogy a feladat a kért időszakhoz adódjon hozzá, függetlenül attól, hogy a munkacella túl van-e terhelve.</span><span class="sxs-lookup"><span data-stu-id="83c30-136">This option will ensure that the job is added to the requested period, regardless if the work cell might be overloaded.</span></span>  
6. <span data-ttu-id="83c30-137">Kattintson az üzemezés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="83c30-137">Click Schedule.</span></span>
    * <span data-ttu-id="83c30-138">Mindkét feladat a kívánt időszakhoz lett hozzáadva.</span><span class="sxs-lookup"><span data-stu-id="83c30-138">Notice that both jobs are added to the desired period.</span></span>  
    * <span data-ttu-id="83c30-139">A Kapacitási időszak szakaszban láthatja az egyes időszakok terhelését.</span><span class="sxs-lookup"><span data-stu-id="83c30-139">In the Period capacity section, you can see the load for each period.</span></span> <span data-ttu-id="83c30-140">A Felhasználás mező az időszak tervezett felhasználását mutatja.</span><span class="sxs-lookup"><span data-stu-id="83c30-140">The Consumption field shows the scheduled consumption in this period.</span></span> <span data-ttu-id="83c30-141">Ha az ütemezett felhasználás magasabb, mint az időszakban rendelkezésre álló kapacitás, a rendszer a túlterhelt felhasználást választja ki.</span><span class="sxs-lookup"><span data-stu-id="83c30-141">If the scheduled consumption is higher than the available capacity in this period, the overloaded consumption will be selected.</span></span>  

