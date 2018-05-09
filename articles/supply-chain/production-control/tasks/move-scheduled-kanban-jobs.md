--- 
title: "Beütemezett kanbanfeladatok mozgatása"
description: "Ez az eljárás a tervezett kanbanfeldolgozási feladatok másik időszakra történő áthelyezésével foglalkozik."
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
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: ae6ea66f0e0ce03008882e59140ad7a0d89f0e30
ms.contentlocale: hu-hu
ms.lasthandoff: 05/08/2018

---
# <a name="move-scheduled-kanban-jobs"></a><span data-ttu-id="0b881-103">Beütemezett kanbanfeladatok mozgatása</span><span class="sxs-lookup"><span data-stu-id="0b881-103">Move scheduled kanban jobs</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="0b881-104">Ez az eljárás a tervezett kanbanfeldolgozási feladatok másik időszakra történő áthelyezésével foglalkozik.</span><span class="sxs-lookup"><span data-stu-id="0b881-104">This procedure focuses on moving planned process kanban jobs to a different period.</span></span> <span data-ttu-id="0b881-105">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="0b881-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="0b881-106">Ez az eljárás a kanbanokkal dolgozó üzemirányítási felügyelő vagy termeléstervező munkáját segíti.</span><span class="sxs-lookup"><span data-stu-id="0b881-106">This procedure is intended for the shop floor supervisor or production planner working with kanbans.</span></span>


## <a name="select-scheduled-kanban-jobs"></a><span data-ttu-id="0b881-107">Beütemezett kanbanfeladatok kiválasztása</span><span class="sxs-lookup"><span data-stu-id="0b881-107">Select scheduled kanban jobs</span></span>
1. <span data-ttu-id="0b881-108">Gå til Produktionsstyring > Kanban > Tidsplanlægning af kanban-job.</span><span class="sxs-lookup"><span data-stu-id="0b881-108">Gå til Produktionsstyring > Kanban > Tidsplanlægning af kanban-job.</span></span>
2. <span data-ttu-id="0b881-109">!MtCMR!A Munkacella mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="0b881-109">!MtCMR!In the Work cell field, click the drop-down button to open the lookup.</span></span> <span data-ttu-id="0b881-110">áçêìõý !</span><span class="sxs-lookup"><span data-stu-id="0b881-110">áçêìõý !</span></span>
3. <span data-ttu-id="0b881-111">Markér den valgte række på listen.</span><span class="sxs-lookup"><span data-stu-id="0b881-111">Markér den valgte række på listen.</span></span>
    * <span data-ttu-id="0b881-112">Jelölje ki az 1250 munkacellát.</span><span class="sxs-lookup"><span data-stu-id="0b881-112">Select work cell 1250.</span></span>  
4. <span data-ttu-id="0b881-113">Klik på Select.</span><span class="sxs-lookup"><span data-stu-id="0b881-113">Klik på Select.</span></span>
5. <span data-ttu-id="0b881-114">Vælg 'Planlagt' i feltet Display job status.</span><span class="sxs-lookup"><span data-stu-id="0b881-114">Vælg 'Planlagt' i feltet Display job status.</span></span>
    * <span data-ttu-id="0b881-115">Ez úgy szűri a feladatok listáját, hogy csak az ütemezett kanbanfeladatok jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="0b881-115">This filters the job list to display only the scheduled kanban jobs.</span></span>  

## <a name="move-kanban-jobs-to-a-different-period"></a><span data-ttu-id="0b881-116">Kanbanfeladatok áthelyezése egy másik tervezési időszakba</span><span class="sxs-lookup"><span data-stu-id="0b881-116">Move kanban jobs to a different period</span></span>
1. <span data-ttu-id="0b881-117">Find og vælg den ønskede post på listen.</span><span class="sxs-lookup"><span data-stu-id="0b881-117">Find og vælg den ønskede post på listen.</span></span>
    * <span data-ttu-id="0b881-118">Válasszon egy olyan feladatot, amelynek állapota Tervezett feladat, például a Tervezett időszakban 2012. december 20-ra tervezett feladatot.</span><span class="sxs-lookup"><span data-stu-id="0b881-118">Select a job that has the Planned job status, for example, a job scheduled on December 20, 2012  in the Planned period field.</span></span> <span data-ttu-id="0b881-119">Majd helyezze át a feladatot az előző időszakba.</span><span class="sxs-lookup"><span data-stu-id="0b881-119">Then move the job to the previous period.</span></span>  
2. <span data-ttu-id="0b881-120">Klik på Previous period.</span><span class="sxs-lookup"><span data-stu-id="0b881-120">Klik på Previous period.</span></span>
3. <span data-ttu-id="0b881-121">Klik på End.</span><span class="sxs-lookup"><span data-stu-id="0b881-121">Klik på End.</span></span>
    * <span data-ttu-id="0b881-122">Ezzel a feladat átkerül az előző időszak feladatlistájának végére.</span><span class="sxs-lookup"><span data-stu-id="0b881-122">This will move the job to the end of the job list as the last job in the previous period.</span></span>  
4. <span data-ttu-id="0b881-123">Find og vælg den ønskede post på listen.</span><span class="sxs-lookup"><span data-stu-id="0b881-123">Find og vælg den ønskede post på listen.</span></span>
    * <span data-ttu-id="0b881-124">Válasszon egy olyan feladatot, amelynek állapota Tervezett feladat, például a Tervezett időszakban 2012. december 18-ra tervezett feladatot.</span><span class="sxs-lookup"><span data-stu-id="0b881-124">Select a job that has the Planned job status, for example, a job scheduled on December 18, 2012 in the Planned period field.</span></span> <span data-ttu-id="0b881-125">Majd helyezze át a feladatot az következő időszakba.</span><span class="sxs-lookup"><span data-stu-id="0b881-125">Then move the job to the next period.</span></span>  
5. <span data-ttu-id="0b881-126">Klik på Next period.</span><span class="sxs-lookup"><span data-stu-id="0b881-126">Klik på Next period.</span></span>
6. <span data-ttu-id="0b881-127">Klik på Start.</span><span class="sxs-lookup"><span data-stu-id="0b881-127">Klik på Start.</span></span>
    * <span data-ttu-id="0b881-128">Ezzel a feladat átkerül az előző időszak feladatlistájának elejére.</span><span class="sxs-lookup"><span data-stu-id="0b881-128">This will move the job to the start of the job list as the first job in the previous period.</span></span>  

## <a name="task-move-a-job-within-a-period"></a><span data-ttu-id="0b881-129">Feladat: Egy feladat áthelyezése időszakon belül</span><span class="sxs-lookup"><span data-stu-id="0b881-129">Task: Move a job within a period</span></span>
1. <span data-ttu-id="0b881-130">Find og vælg den ønskede post på listen.</span><span class="sxs-lookup"><span data-stu-id="0b881-130">Find og vælg den ønskede post på listen.</span></span>
    * <span data-ttu-id="0b881-131">Válasszon egy olyan feladatot, amelynek állapota Tervezett feladat, például a Tervezett időszakban 2012. december 19-ra tervezett feladatot.</span><span class="sxs-lookup"><span data-stu-id="0b881-131">Select a job that has the Planned job status, for example, the second job scheduled on December 19, 2012 in the Planned period field.</span></span> <span data-ttu-id="0b881-132">Majd helyezze át a feladatot az előző időszakon belül.</span><span class="sxs-lookup"><span data-stu-id="0b881-132">Then move the job within the planned period.</span></span>  
2. <span data-ttu-id="0b881-133">Klik på Forward.</span><span class="sxs-lookup"><span data-stu-id="0b881-133">Klik på Forward.</span></span>
    * <span data-ttu-id="0b881-134">Figyelje meg, hogy a feladat egy sorral lentebb került a listán.</span><span class="sxs-lookup"><span data-stu-id="0b881-134">Notice that the job is moved one line down on the list.</span></span>  
3. <span data-ttu-id="0b881-135">Klik på Backward.</span><span class="sxs-lookup"><span data-stu-id="0b881-135">Klik på Backward.</span></span>
    * <span data-ttu-id="0b881-136">Figyelje meg, hogy a feladat egy sorral fentebb került a listán.</span><span class="sxs-lookup"><span data-stu-id="0b881-136">Notice that the job is moved one line up on the list.</span></span>  


