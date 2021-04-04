---
title: Beütemezett kanbanfeladatok mozgatása
description: Ez az eljárás a tervezett kanbanfeldolgozási feladatok másik időszakra történő áthelyezésével foglalkozik.
author: ChristianRytt
manager: tfehr
ms.date: 11/07/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanJobSchedulingListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2b945cdfa3e013c213e718962499831df126f09b
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5259746"
---
# <a name="move-scheduled-kanban-jobs"></a><span data-ttu-id="88270-103">Beütemezett kanbanfeladatok mozgatása</span><span class="sxs-lookup"><span data-stu-id="88270-103">Move scheduled kanban jobs</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="88270-104">Ez az eljárás a tervezett kanbanfeldolgozási feladatok másik időszakra történő áthelyezésével foglalkozik.</span><span class="sxs-lookup"><span data-stu-id="88270-104">This procedure focuses on moving planned process kanban jobs to a different period.</span></span> <span data-ttu-id="88270-105">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="88270-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="88270-106">Ez az eljárás a kanbanokkal dolgozó üzemirányítási felügyelő vagy termeléstervező munkáját segíti.</span><span class="sxs-lookup"><span data-stu-id="88270-106">This procedure is intended for the shop floor supervisor or production planner working with kanbans.</span></span>

## <a name="select-scheduled-kanban-jobs"></a><span data-ttu-id="88270-107">Válasszon ki ütemezett kanbanfeladatokat.</span><span class="sxs-lookup"><span data-stu-id="88270-107">Select scheduled kanban jobs.</span></span> 

1. <span data-ttu-id="88270-108">Ugorjon a **Gyártásvezérlés > Kanban > Kanbanfeladat ütemezése** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="88270-108">Go to **Production control > Kanban > Kanban job scheduling**.</span></span> 

2. <span data-ttu-id="88270-109">A **Munkacella** mezőben kattintson a legördülő menüre a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="88270-109">In the **Work cell** field, click the drop-down button to open the lookup.</span></span> 

3. <span data-ttu-id="88270-110">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="88270-110">In the list, mark the selected row.</span></span> 
   - <span data-ttu-id="88270-111">Jelölje ki az 1250 munkacellát.</span><span class="sxs-lookup"><span data-stu-id="88270-111">Select work cell 1250.</span></span> 
4. <span data-ttu-id="88270-112">Kattintson a **Kiválasztás** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="88270-112">Click **Select**.</span></span> 

5. <span data-ttu-id="88270-113">A **Feladatállapot megjelenítése** mezőben válassza ki az **Ütemezett** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="88270-113">In the **Display job status** field, select **Scheduled**.</span></span> <span data-ttu-id="88270-114">Ez úgy szűri a feladatok listáját, hogy csak az ütemezett kanbanfeladatok jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="88270-114">This filters the job list to display only the scheduled kanban jobs.</span></span> 

## <a name="move-kanban-jobs-to-a-different-period"></a><span data-ttu-id="88270-115">Kanbanfeladatok áthelyezése egy másik tervezési időszakba.</span><span class="sxs-lookup"><span data-stu-id="88270-115">Move kanban jobs to a different period.</span></span> 

1. <span data-ttu-id="88270-116">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="88270-116">In the list, find and select the desired record.</span></span> <span data-ttu-id="88270-117">Válasszon egy olyan feladatot, amelynek állapota **Tervezett feladat**, például a **Tervezett időszak** mezőben 2012. december 20-ra tervezett feladatot.</span><span class="sxs-lookup"><span data-stu-id="88270-117">Select a job that has the **Planned job** status, for example, a job scheduled on December 20, 2012 in the **Planned period** field.</span></span> <span data-ttu-id="88270-118">Majd helyezze át a feladatot az előző időszakba.</span><span class="sxs-lookup"><span data-stu-id="88270-118">Then move the job to the previous period.</span></span> 

2. <span data-ttu-id="88270-119">Kattintson az **Előző időszak** elemre.</span><span class="sxs-lookup"><span data-stu-id="88270-119">Click **Previous period**.</span></span> 

3. <span data-ttu-id="88270-120">Kattintson a **Vége** gombra, amellyel a feladat átkerül az előző időszak feladatlistájának végére, mint utolsó feladat.</span><span class="sxs-lookup"><span data-stu-id="88270-120">Click **End** to move the job to the end of the job list as the last job in the previous period.</span></span> 

4. <span data-ttu-id="88270-121">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="88270-121">In the list, find and select the desired record.</span></span> <span data-ttu-id="88270-122">Válasszon egy olyan feladatot, amelynek állapota **Tervezett feladat**, például a **Tervezett időszak** mezőben 2012. december 18-ra tervezett feladatot.</span><span class="sxs-lookup"><span data-stu-id="88270-122">Select a job that has the **Planned job** status, for example, a job scheduled on December 18, 2012 in the **Planned period** field.</span></span> <span data-ttu-id="88270-123">Majd helyezze át a feladatot az következő időszakba.</span><span class="sxs-lookup"><span data-stu-id="88270-123">Then move the job to the next period.</span></span> 

5. <span data-ttu-id="88270-124">Kattintson a **Következő időszak** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="88270-124">Click **Next period**.</span></span> 

6. <span data-ttu-id="88270-125">Kattintson a **Kezdete** gombra, amellyel a feladat átkerül a feladatlista elejére, mint az előző időszak első feladata.</span><span class="sxs-lookup"><span data-stu-id="88270-125">Click **Start** to move the job to the start of the job list as the first job in the previous period.</span></span> 

## <a name="move-a-job-within-a-period"></a><span data-ttu-id="88270-126">Egy feladat áthelyezése időszakon belül.</span><span class="sxs-lookup"><span data-stu-id="88270-126">Move a job within a period.</span></span> 

1. <span data-ttu-id="88270-127">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="88270-127">In the list, find and select the desired record.</span></span> <span data-ttu-id="88270-128">Válasszon egy olyan feladatot, amelynek állapota Tervezett feladat, például a **Tervezett időszak** mezőben 2012. december 19-ra tervezett második feladatot.</span><span class="sxs-lookup"><span data-stu-id="88270-128">Select a job that has the Planned job status, for example, the second job scheduled on December 19, 2012 in the **Planned period** field.</span></span> <span data-ttu-id="88270-129">Majd helyezze át a feladatot az előző időszakon belül.</span><span class="sxs-lookup"><span data-stu-id="88270-129">Then move the job within the planned period.</span></span> 

2. <span data-ttu-id="88270-130">Kattintson az **Előre** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="88270-130">Click **Forward**.</span></span> <span data-ttu-id="88270-131">Figyelje meg, hogy a feladat egy sorral lentebb került a listán.</span><span class="sxs-lookup"><span data-stu-id="88270-131">Notice that the job is moved one line down on the list.</span></span> 

3. <span data-ttu-id="88270-132">Kattintson a **Vissza** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="88270-132">Click **Backward**.</span></span> <span data-ttu-id="88270-133">Figyelje meg, hogy a feladat egy sorral fentebb került a listán.</span><span class="sxs-lookup"><span data-stu-id="88270-133">Notice that the job is moved one line up on the list.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]