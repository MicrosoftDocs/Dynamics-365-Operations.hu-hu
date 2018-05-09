--- 
title: "Kanbanfeldolgozási feladatok végrehajtása"
description: "Ezzel az eljárás a kanbanfeldolgozási feladatok végrehajtására szolgál."
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
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 4f0579e9bccdcf240d33bb7b936bd9f9f7619028
ms.contentlocale: hu-hu
ms.lasthandoff: 05/08/2018

---
# <a name="execute-kanban-process-jobs"></a><span data-ttu-id="a0fcf-103">Kanbanfeldolgozási feladatok végrehajtása</span><span class="sxs-lookup"><span data-stu-id="a0fcf-103">Execute kanban process jobs</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="a0fcf-104">Ezzel az eljárás a kanbanfeldolgozási feladatok végrehajtására szolgál.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-104">This procedure focuses on executing kanban process jobs.</span></span> <span data-ttu-id="a0fcf-105">A program az első feladatot a várt mennyiségi eredménnyel és hibák nélkül végezte el.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-105">The first job is completed with the expected quantity and has no errors.</span></span> <span data-ttu-id="a0fcf-106">A második feladat hibákkal fejeződött be.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-106">The second job is completed with errors.</span></span> <span data-ttu-id="a0fcf-107">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-107">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="a0fcf-108">Ezt az eljárást a gépkezelő használja.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-108">This procedure is intended for the machine operator.</span></span>


## <a name="select-a-kanban-job"></a><span data-ttu-id="a0fcf-109">Válasszon ki egy kanban feladatot.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-109">Select a kanban job</span></span>
1. <span data-ttu-id="a0fcf-110">Ugorjon a Gyártásvezérlés > Kanban > Kanbantábla feldolgozási feladatokhoz lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-110">Go to Production control > Kanban > Kanban board for process jobs.</span></span>
2. <span data-ttu-id="a0fcf-111">A Munkacella mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-111">In the Work cell field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="a0fcf-112">Kattintson az 1250 Erőforráscsoporttal ellátott sorra.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-112">Click the row with resource group 1250.</span></span> <span data-ttu-id="a0fcf-113">Ez végzi el a Feladatok lista szűrését a csak az 1250-es munkacellára vonatkozó feladatok megtekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-113">This filters the Jobs list to display only the jobs for work cell 1250.</span></span>
    * <span data-ttu-id="a0fcf-114">Jelölje be a Tervezett feladat állapotú sort.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-114">Mark the row that has the Planned job status.</span></span>  

## <a name="complete-a-job-with-expected-quantity"></a><span data-ttu-id="a0fcf-115">Végezze el a feladatot a várt mennyiséggel</span><span class="sxs-lookup"><span data-stu-id="a0fcf-115">Complete a job with expected quantity</span></span>
1. <span data-ttu-id="a0fcf-116">Bontsa ki vagy zárja be a Részletek szakaszt.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-116">Expand or collapse the Details section.</span></span>
    * <span data-ttu-id="a0fcf-117">Ez a szakasz a kártyaszámmal, a cikkszámmal, a megrendelt mennyiséggel és a tevékenység nevével kapcsolatos fontos információkat jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-117">This section displays important information about card number, item number, quantity ordered, and activity name.</span></span>  
2. <span data-ttu-id="a0fcf-118">Bontsa ki vagy zárja be a Termelési útmutatások szakaszt.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-118">Expand or collapse the Production instructions section.</span></span>
    * <span data-ttu-id="a0fcf-119">Ez a szakasz a tevékenységre vonatkozó termelési útmutatásokat jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-119">This section displays production instructions for the activity.</span></span> <span data-ttu-id="a0fcf-120">Ezek az utasítások szöveg, kép, rajz és egyéb dokumentum formátumban jelenhetnek meg.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-120">The instructions can be text, pictures, drawings, and other documents.</span></span>  
3. <span data-ttu-id="a0fcf-121">Kattintson a Start elemre.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-121">Click Start.</span></span>
    * <span data-ttu-id="a0fcf-122">Válasszon ki egy olyan feladatot, amely nem fejeződött be.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-122">Select a job that is not completed.</span></span> <span data-ttu-id="a0fcf-123">A feladat állapota mezőben lévő Állapot ikonok használatával tekintse meg a feladat állapotát.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-123">Use status icons in the Job status field to view job status.</span></span>      
4. <span data-ttu-id="a0fcf-124">Kattintson a Befejezés gombra.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-124">Click Complete.</span></span>
    * <span data-ttu-id="a0fcf-125">A rendszer a feladatot a várható minőségi eredménnyel fejezte meg.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-125">The job is completed with the expected quality.</span></span>  

## <a name="complete-a-job-with-errors"></a><span data-ttu-id="a0fcf-126">A feladat hibákkal történő elvégzése</span><span class="sxs-lookup"><span data-stu-id="a0fcf-126">Complete a job with errors</span></span>
1. <span data-ttu-id="a0fcf-127">Kattintson a Start elemre.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-127">Click Start.</span></span>
    * <span data-ttu-id="a0fcf-128">A feladat befejezése után a rendszer automatikusan kijelöli a következő feladatot a listában.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-128">When a job is completed, the next job on the list is selected automatically.</span></span> <span data-ttu-id="a0fcf-129">Ez az oka annak, hogy az Indítás elemre történő kattintás előtt nem kell kiválasztani a feladatot.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-129">This is why you don't need to select a job before you click Start.</span></span>  
2. <span data-ttu-id="a0fcf-130">A Művelet panelen kattintson a Gyártás elemre.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-130">On the Action Pane, click Manufacture.</span></span>
3. <span data-ttu-id="a0fcf-131">Kattintson a Végrehajtás (részletek) lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-131">Click Complete (details).</span></span>
4. <span data-ttu-id="a0fcf-132">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-132">In the list, mark the selected row.</span></span>
5. <span data-ttu-id="a0fcf-133">Adjon meg egy számot a Hibás mennyiség mezőben.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-133">In the Error quantity field, enter a number.</span></span>
6. <span data-ttu-id="a0fcf-134">Adjon meg egy számot a Hibátlan mennyiség mezőben.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-134">In the Good quantity field, enter a number.</span></span>
7. <span data-ttu-id="a0fcf-135">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-135">Click OK.</span></span>


