--- 
title: "A feldolgozási kanbanfeladat előkészítése, amikor az anyagok nem elérhetők a munkacellához"
description: "Ez az eljárás a kanbanfeladat folyamatának előkészítését mutatja be, amikor egyes anyagok nem érhetőek el a munkacellához, és így a raktárból kell anyagokat választani."
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
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 5a47af6910a9686e74ab6d1069dd02079e60cb8a
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="prepare-a-process-kanban-job-when-materials-are-not-available-for-the-work-cell"></a><span data-ttu-id="303a1-103">A feldolgozási kanbanfeladat előkészítése, amikor az anyagok nem elérhetők a munkacellához</span><span class="sxs-lookup"><span data-stu-id="303a1-103">Prepare a process kanban job when materials are not available for the work cell</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="303a1-104">Ez az eljárás a kanbanfeladat folyamatának előkészítését mutatja be, amikor egyes anyagok nem érhetőek el a munkacellához, és így a raktárból kell anyagokat választani.</span><span class="sxs-lookup"><span data-stu-id="303a1-104">This procedure focuses on preparing a process kanban job when some materials are not available for the work cell, therefore it's necessary to pick materials from the warehouse.</span></span> <span data-ttu-id="303a1-105">Az „A feldolgozási kanbanfeladat előkészítése, amikor az anyagok elérhetők” eljárás előfeltétel, ha ilyen eljárást akar létrehozni.</span><span class="sxs-lookup"><span data-stu-id="303a1-105">The procedure "Prepare a process kanban job when materials are available" is a prerequisite for creating this procedure.</span></span> <span data-ttu-id="303a1-106">Ezt az eljárást a gépkezelő használja.</span><span class="sxs-lookup"><span data-stu-id="303a1-106">This procedure is intended for the machine operator.</span></span> <span data-ttu-id="303a1-107">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="303a1-107">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="303a1-108">Ugorjon a Gyártásvezérlés > Kanban > Kanbantábla feldolgozási feladatokhoz lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="303a1-108">Go to Production control > Kanban > Kanban board for process jobs.</span></span>
2. <span data-ttu-id="303a1-109">A Munkacella mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="303a1-109">In the Work cell field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="303a1-110">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="303a1-110">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="303a1-111">Jelölje ki az 1250 munkacellát.</span><span class="sxs-lookup"><span data-stu-id="303a1-111">Select work cell 1250.</span></span>  
4. <span data-ttu-id="303a1-112">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="303a1-112">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="303a1-113">Válassza ki a 000356 kanbant.</span><span class="sxs-lookup"><span data-stu-id="303a1-113">Select Kanban 000356.</span></span>  
5. <span data-ttu-id="303a1-114">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="303a1-114">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="303a1-115">Szüntesse meg a 4. sor kijelölését a listában,</span><span class="sxs-lookup"><span data-stu-id="303a1-115">In the list, deselect row 4.</span></span> <span data-ttu-id="303a1-116">jelölje ki a 4. sort, ha nem végezte el az „A feldolgozási kanbanfeladat előkészítése, amikor az anyagok elérhetők” feladatot.</span><span class="sxs-lookup"><span data-stu-id="303a1-116">or Select row 4 if you haven't completed the task "Prepare a process kanban job when materials are available."</span></span>  
6. <span data-ttu-id="303a1-117">Bontsa ki a Kitárolási lista részt.</span><span class="sxs-lookup"><span data-stu-id="303a1-117">Toggle the expansion of the Picking list section.</span></span>
    * <span data-ttu-id="303a1-118">A Nem található bejegyzés ikon az ellátási állapotnál azt jelzi, hogy a P0002 cikk 48 egyedi egysége hiányzik a munkacellából.</span><span class="sxs-lookup"><span data-stu-id="303a1-118">The No entry icon in the supply status indicates that 48 ea of item P0002 are missing for the work cell.</span></span>  

## <a name="transfer-materials-to-work-cell"></a><span data-ttu-id="303a1-119">Anyagok átvitele a munkacellába</span><span class="sxs-lookup"><span data-stu-id="303a1-119">Transfer materials to work cell</span></span>
1. <span data-ttu-id="303a1-120">Bontsa ki az Átviteli feladatok részt.</span><span class="sxs-lookup"><span data-stu-id="303a1-120">Toggle the expansion of the Transfer jobs section.</span></span>
2. <span data-ttu-id="303a1-121">A Gyorsszűrő használatával szűrjön rá a P0002 értékű Cikkszám mezőkre.</span><span class="sxs-lookup"><span data-stu-id="303a1-121">Use the Quick Filter to filter on the Item number field with a value of 'P0002'.</span></span>
3. <span data-ttu-id="303a1-122">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="303a1-122">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="303a1-123">Kattintson a Start elemre.</span><span class="sxs-lookup"><span data-stu-id="303a1-123">Click Start.</span></span>
    * <span data-ttu-id="303a1-124">Az áthelyezés folyamatban.</span><span class="sxs-lookup"><span data-stu-id="303a1-124">Transfer is in progress.</span></span>  
5. <span data-ttu-id="303a1-125">Kattintson a Befejezés gombra.</span><span class="sxs-lookup"><span data-stu-id="303a1-125">Click Complete.</span></span>
    * <span data-ttu-id="303a1-126">A P0002 cikk most már elérhető a kanbanfeladat kitárolási listájában.</span><span class="sxs-lookup"><span data-stu-id="303a1-126">Item P0002 is now available in the picking list for the kanban job.</span></span> <span data-ttu-id="303a1-127">Ez azt jelenti, hogy elkészíthetjük a kanbant a szükséges anyagokkal.</span><span class="sxs-lookup"><span data-stu-id="303a1-127">This means that we can prepare the kanban with all the needed materials.</span></span>  
6. <span data-ttu-id="303a1-128">Kattintson az Előkészítés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="303a1-128">Click Prepare.</span></span>
    * <span data-ttu-id="303a1-129">Figyelje meg, hogy a Feladat állapotának ikonja jelzi, ha a feladat elkészült.</span><span class="sxs-lookup"><span data-stu-id="303a1-129">Notice that an icon in the Job status indicates that the job is now ready.</span></span>  


