---
title: Anyagok átvitele kanbanfeladattal
description: Ez az eljárás egy anyagszállításra használt visszavonási kanbanfeladattal foglalkozik.
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanBoardTransferJob
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a2db7b9fb960beb5b4a851aabb9f28a0f9e3d3da
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "367432"
---
# <a name="transfer-materials-with-kanban-jobs"></a><span data-ttu-id="b7a51-103">Anyagok átvitele kanbanfeladattal</span><span class="sxs-lookup"><span data-stu-id="b7a51-103">Transfer materials with kanban jobs</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="b7a51-104">Ez az eljárás egy anyagszállításra használt visszavonási kanbanfeladattal foglalkozik.</span><span class="sxs-lookup"><span data-stu-id="b7a51-104">This procedure focuses on executing a withdrawal kanban job to transfer materials.</span></span> <span data-ttu-id="b7a51-105">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="b7a51-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="b7a51-106">Ezt az eljárást a raktári dolgozó használja.</span><span class="sxs-lookup"><span data-stu-id="b7a51-106">This procedure is intended for the warehouse worker.</span></span>


## <a name="display-transfer-jobs"></a><span data-ttu-id="b7a51-107">Átviteli feladatok megjelenítése</span><span class="sxs-lookup"><span data-stu-id="b7a51-107">Display transfer jobs</span></span>
1. <span data-ttu-id="b7a51-108">Ugorjon a Gyártásvezérlés > Kanban > Kanbantábla oldalra a szállítási feladatokért.</span><span class="sxs-lookup"><span data-stu-id="b7a51-108">Go to Production control > Kanban > Kanban board for transfer jobs.</span></span>
2. <span data-ttu-id="b7a51-109">Nyissa meg vagy zárja be a Szűrők szekciót.</span><span class="sxs-lookup"><span data-stu-id="b7a51-109">Expand or collapse the Filters section.</span></span>
    * <span data-ttu-id="b7a51-110">A Szűrők részben megadhatja, hogy mely munkákat szeretné látni a Termelési folyamat, Tevékenység neve Raktárból és helyből, valamint a Raktárba és helyre szűrők használatával.</span><span class="sxs-lookup"><span data-stu-id="b7a51-110">In the Filters section, you can specify what jobs you want to see by filtering on Production flow, Activity name, From warehouse and location, and To warehouse and location.</span></span>  
3. <span data-ttu-id="b7a51-111">A Raktárból mezőbe írja be a „11” értéket.</span><span class="sxs-lookup"><span data-stu-id="b7a51-111">In the From warehouse field, type '11'.</span></span>
4. <span data-ttu-id="b7a51-112">A Helyszínre mezőbe írja be a „12” értéket.</span><span class="sxs-lookup"><span data-stu-id="b7a51-112">In the To location field, type '12'.</span></span>

## <a name="start-a-transfer-job"></a><span data-ttu-id="b7a51-113">Áthelyezési feladat indítása</span><span class="sxs-lookup"><span data-stu-id="b7a51-113">Start a transfer job</span></span>
1. <span data-ttu-id="b7a51-114">A listában törölje a sorok esetleges kijelölését.</span><span class="sxs-lookup"><span data-stu-id="b7a51-114">In the list, deselect the selected row - if any.</span></span>
2. <span data-ttu-id="b7a51-115">Jelölje ki az 4. sort a listában.</span><span class="sxs-lookup"><span data-stu-id="b7a51-115">In the list, select row 4.</span></span>
    * <span data-ttu-id="b7a51-116">Válassza ki az első, Nem tervezett állapotú feladatot.</span><span class="sxs-lookup"><span data-stu-id="b7a51-116">Select the first job with status Not planned.</span></span> <span data-ttu-id="b7a51-117">Győződjön meg róla, hogy csak ez a feladat van kiválasztva.</span><span class="sxs-lookup"><span data-stu-id="b7a51-117">Make sure this is the only job selected.</span></span>  
3. <span data-ttu-id="b7a51-118">Kattintson a Start elemre.</span><span class="sxs-lookup"><span data-stu-id="b7a51-118">Click Start.</span></span>
    * <span data-ttu-id="b7a51-119">Ne feledje, hogy egy ikon jelzi a feladat megkezdését.</span><span class="sxs-lookup"><span data-stu-id="b7a51-119">Notice that an icon indicates that the job is started.</span></span>  

## <a name="select-a-second-transfer-job-and-change-quantity"></a><span data-ttu-id="b7a51-120">Egy második áthelyezési feladat kiválasztása és a mennyiség módosítása</span><span class="sxs-lookup"><span data-stu-id="b7a51-120">Select a second transfer job and change quantity</span></span>
1. <span data-ttu-id="b7a51-121">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="b7a51-121">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="b7a51-122">Több feladatot is kiválaszthat, de egyelőre válassza ki az 5. sort.</span><span class="sxs-lookup"><span data-stu-id="b7a51-122">You can have multiple jobs selected, but for now select row 5.</span></span>  
2. <span data-ttu-id="b7a51-123">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="b7a51-123">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="b7a51-124">Győződjön meg róla, hogy csak az előző lépés feladata van kiválasztva.</span><span class="sxs-lookup"><span data-stu-id="b7a51-124">Make sure the job in the previous step is the only one selected.</span></span> <span data-ttu-id="b7a51-125">Törölje a többi feladat kiválasztását.</span><span class="sxs-lookup"><span data-stu-id="b7a51-125">Deselect all other jobs.</span></span>  
3. <span data-ttu-id="b7a51-126">Ne feledje a Feladatmennyiség mezőben megadott értéket, később még szüksége lesz rá</span><span class="sxs-lookup"><span data-stu-id="b7a51-126">Note the value in the Job quantity field to reference later</span></span>
4. <span data-ttu-id="b7a51-127">Állítsa a Feladatmennyiséget a „30” értékre.</span><span class="sxs-lookup"><span data-stu-id="b7a51-127">Set Job quantity to '30'.</span></span>
    * <span data-ttu-id="b7a51-128">Figyelje meg a figyelmeztetést!</span><span class="sxs-lookup"><span data-stu-id="b7a51-128">Notice the warning!</span></span> <span data-ttu-id="b7a51-129">30 átvitele nem engedélyezett.</span><span class="sxs-lookup"><span data-stu-id="b7a51-129">You are not allowed to transfer 30.</span></span> <span data-ttu-id="b7a51-130">A kanbanszabály beállítása szerint csak az eredeti mennyiséget lehet átvinni.</span><span class="sxs-lookup"><span data-stu-id="b7a51-130">According to the setup of the kanban rule, you can only transfer the original quantity.</span></span>  
5. <span data-ttu-id="b7a51-131">Használja a Feladatmennyiség mezőben korábban megjegyzett értéket.</span><span class="sxs-lookup"><span data-stu-id="b7a51-131">Use the value noted previously in the Job quantity field</span></span>
    * <span data-ttu-id="b7a51-132">Állítsa a Feladatmennyiséget az előző értékre.</span><span class="sxs-lookup"><span data-stu-id="b7a51-132">Set the Job quantity to the previous value.</span></span>  

## <a name="start-the-second-transfer-job"></a><span data-ttu-id="b7a51-133">Második áthelyezési feladat elindítása</span><span class="sxs-lookup"><span data-stu-id="b7a51-133">Start the second transfer job</span></span>
1. <span data-ttu-id="b7a51-134">Kattintson a Start elemre.</span><span class="sxs-lookup"><span data-stu-id="b7a51-134">Click Start.</span></span>
    * <span data-ttu-id="b7a51-135">Ez megkezdi az 5. sorban található feladat átvitelét.</span><span class="sxs-lookup"><span data-stu-id="b7a51-135">This will start the transfer of the job in row 5.</span></span>  

## <a name="complete-both-transfer-jobs"></a><span data-ttu-id="b7a51-136">Mindkét áthelyezési feladat befejezése</span><span class="sxs-lookup"><span data-stu-id="b7a51-136">Complete both transfer jobs</span></span>
1. <span data-ttu-id="b7a51-137">Jelölje ki az 4. sort a listában.</span><span class="sxs-lookup"><span data-stu-id="b7a51-137">In the list, select row 4.</span></span>
    * <span data-ttu-id="b7a51-138">Most két átviteli feladat van kiválasztva a 4. és az 5. sorban.</span><span class="sxs-lookup"><span data-stu-id="b7a51-138">Now two transfer jobs are selected on row 4 and row 5.</span></span>  
2. <span data-ttu-id="b7a51-139">Kattintson a Befejezés gombra.</span><span class="sxs-lookup"><span data-stu-id="b7a51-139">Click Complete.</span></span>
    * <span data-ttu-id="b7a51-140">Ez mindkét feladat átvitelét befejezi.</span><span class="sxs-lookup"><span data-stu-id="b7a51-140">This will complete the transfer of both jobs.</span></span>  

