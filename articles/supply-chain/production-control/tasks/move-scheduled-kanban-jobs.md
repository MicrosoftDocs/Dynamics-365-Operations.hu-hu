---
title: Beütemezett kanbanfeladatok mozgatása
description: Ez az eljárás a tervezett kanbanfeldolgozási feladatok másik időszakra történő áthelyezésével foglalkozik.
author: ChristianRytt
manager: AnnBe
ms.date: 11/07/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanJobSchedulingListPage
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f791c9048ef6efe1585c991f998099cd1fc12df7
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1567426"
---
# <a name="move-scheduled-kanban-jobs"></a><span data-ttu-id="f85fb-103">Beütemezett kanbanfeladatok mozgatása</span><span class="sxs-lookup"><span data-stu-id="f85fb-103">Move scheduled kanban jobs</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f85fb-104">Ez az eljárás a tervezett kanbanfeldolgozási feladatok másik időszakra történő áthelyezésével foglalkozik.</span><span class="sxs-lookup"><span data-stu-id="f85fb-104">This procedure focuses on moving planned process kanban jobs to a different period.</span></span> <span data-ttu-id="f85fb-105">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="f85fb-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="f85fb-106">Ez az eljárás a kanbanokkal dolgozó üzemirányítási felügyelő vagy termeléstervező munkáját segíti.</span><span class="sxs-lookup"><span data-stu-id="f85fb-106">This procedure is intended for the shop floor supervisor or production planner working with kanbans.</span></span>

## <a name="select-scheduled-kanban-jobs"></a><span data-ttu-id="f85fb-107">Válasszon ki ütemezett kanbanfeladatokat.</span><span class="sxs-lookup"><span data-stu-id="f85fb-107">Select scheduled kanban jobs.</span></span> 

1. <span data-ttu-id="f85fb-108">Ugorjon a **Gyártásvezérlés > Kanban > Kanbanfeladat ütemezése** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="f85fb-108">Go to **Production control > Kanban > Kanban job scheduling**.</span></span> 

2. <span data-ttu-id="f85fb-109">A **Munkacella** mezőben kattintson a legördülő menüre a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="f85fb-109">In the **Work cell** field, click the drop-down button to open the lookup.</span></span> 

3. <span data-ttu-id="f85fb-110">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="f85fb-110">In the list, mark the selected row.</span></span> 
   - <span data-ttu-id="f85fb-111">Jelölje ki az 1250 munkacellát.</span><span class="sxs-lookup"><span data-stu-id="f85fb-111">Select work cell 1250.</span></span> 
4. <span data-ttu-id="f85fb-112">Kattintson a **Kiválasztás** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="f85fb-112">Click **Select**.</span></span> 

5. <span data-ttu-id="f85fb-113">A **Feladatállapot megjelenítése** mezőben válassza ki az **Ütemezett** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f85fb-113">In the **Display job status** field, select **Scheduled**.</span></span> <span data-ttu-id="f85fb-114">Ez úgy szűri a feladatok listáját, hogy csak az ütemezett kanbanfeladatok jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="f85fb-114">This filters the job list to display only the scheduled kanban jobs.</span></span> 

## <a name="move-kanban-jobs-to-a-different-period"></a><span data-ttu-id="f85fb-115">Kanbanfeladatok áthelyezése egy másik tervezési időszakba.</span><span class="sxs-lookup"><span data-stu-id="f85fb-115">Move kanban jobs to a different period.</span></span> 

1. <span data-ttu-id="f85fb-116">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="f85fb-116">In the list, find and select the desired record.</span></span> <span data-ttu-id="f85fb-117">Válasszon egy olyan feladatot, amelynek állapota **Tervezett feladat**, például a **Tervezett időszak** mezőben 2012. december 20-ra tervezett feladatot.</span><span class="sxs-lookup"><span data-stu-id="f85fb-117">Select a job that has the **Planned job** status, for example, a job scheduled on December 20, 2012 in the **Planned period** field.</span></span> <span data-ttu-id="f85fb-118">Majd helyezze át a feladatot az előző időszakba.</span><span class="sxs-lookup"><span data-stu-id="f85fb-118">Then move the job to the previous period.</span></span> 

2. <span data-ttu-id="f85fb-119">Kattintson az **Előző időszak** elemre.</span><span class="sxs-lookup"><span data-stu-id="f85fb-119">Click **Previous period**.</span></span> 

3. <span data-ttu-id="f85fb-120">Kattintson a **Vége** gombra, amellyel a feladat átkerül az előző időszak feladatlistájának végére, mint utolsó feladat.</span><span class="sxs-lookup"><span data-stu-id="f85fb-120">Click **End** to move the job to the end of the job list as the last job in the previous period.</span></span> 

4. <span data-ttu-id="f85fb-121">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="f85fb-121">In the list, find and select the desired record.</span></span> <span data-ttu-id="f85fb-122">Válasszon egy olyan feladatot, amelynek állapota **Tervezett feladat**, például a **Tervezett időszak** mezőben 2012. december 18-ra tervezett feladatot.</span><span class="sxs-lookup"><span data-stu-id="f85fb-122">Select a job that has the **Planned job** status, for example, a job scheduled on December 18, 2012 in the **Planned period** field.</span></span> <span data-ttu-id="f85fb-123">Majd helyezze át a feladatot az következő időszakba.</span><span class="sxs-lookup"><span data-stu-id="f85fb-123">Then move the job to the next period.</span></span> 

5. <span data-ttu-id="f85fb-124">Kattintson a **Következő időszak** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="f85fb-124">Click **Next period**.</span></span> 

6. <span data-ttu-id="f85fb-125">Kattintson a **Kezdete** gombra, amellyel a feladat átkerül a feladatlista elejére, mint az előző időszak első feladata.</span><span class="sxs-lookup"><span data-stu-id="f85fb-125">Click **Start** to move the job to the start of the job list as the first job in the previous period.</span></span> 

## <a name="move-a-job-within-a-period"></a><span data-ttu-id="f85fb-126">Egy feladat áthelyezése időszakon belül.</span><span class="sxs-lookup"><span data-stu-id="f85fb-126">Move a job within a period.</span></span> 

1. <span data-ttu-id="f85fb-127">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="f85fb-127">In the list, find and select the desired record.</span></span> <span data-ttu-id="f85fb-128">Válasszon egy olyan feladatot, amelynek állapota Tervezett feladat, például a **Tervezett időszak** mezőben 2012. december 19-ra tervezett második feladatot.</span><span class="sxs-lookup"><span data-stu-id="f85fb-128">Select a job that has the Planned job status, for example, the second job scheduled on December 19, 2012 in the **Planned period** field.</span></span> <span data-ttu-id="f85fb-129">Majd helyezze át a feladatot az előző időszakon belül.</span><span class="sxs-lookup"><span data-stu-id="f85fb-129">Then move the job within the planned period.</span></span> 

2. <span data-ttu-id="f85fb-130">Kattintson az **Előre** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="f85fb-130">Click **Forward**.</span></span> <span data-ttu-id="f85fb-131">Figyelje meg, hogy a feladat egy sorral lentebb került a listán.</span><span class="sxs-lookup"><span data-stu-id="f85fb-131">Notice that the job is moved one line down on the list.</span></span> 

3. <span data-ttu-id="f85fb-132">Kattintson a **Vissza** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="f85fb-132">Click **Backward**.</span></span> <span data-ttu-id="f85fb-133">Figyelje meg, hogy a feladat egy sorral fentebb került a listán.</span><span class="sxs-lookup"><span data-stu-id="f85fb-133">Notice that the job is moved one line up on the list.</span></span>
