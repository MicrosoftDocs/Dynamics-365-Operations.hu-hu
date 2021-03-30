---
title: A feldolgozási kanbanfeladat előkészítése, amikor az anyagok nem elérhetők a munkacellához
description: Ez az eljárás a kanbanfeladat folyamatának előkészítését mutatja be, amikor egyes anyagok nem érhetőek el a munkacellához, és így a raktárból kell anyagokat választani.
author: ChristianRytt
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanBoardWorkCell
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 742ac97c4b730d3552f532c53409ef54320b263a
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5204568"
---
# <a name="prepare-a-process-kanban-job-when-materials-are-not-available-for-the-work-cell"></a><span data-ttu-id="4f839-103">A feldolgozási kanbanfeladat előkészítése, amikor az anyagok nem elérhetők a munkacellához</span><span class="sxs-lookup"><span data-stu-id="4f839-103">Prepare a process kanban job when materials are not available for the work cell</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="4f839-104">Ez az eljárás a kanbanfeladat folyamatának előkészítését mutatja be, amikor egyes anyagok nem érhetőek el a munkacellához, és így a raktárból kell anyagokat választani.</span><span class="sxs-lookup"><span data-stu-id="4f839-104">This procedure focuses on preparing a process kanban job when some materials are not available for the work cell, therefore it's necessary to pick materials from the warehouse.</span></span> <span data-ttu-id="4f839-105">Az „A feldolgozási kanbanfeladat előkészítése, amikor az anyagok elérhetők” eljárás előfeltétel, ha ilyen eljárást akar létrehozni.</span><span class="sxs-lookup"><span data-stu-id="4f839-105">The procedure "Prepare a process kanban job when materials are available" is a prerequisite for creating this procedure.</span></span> <span data-ttu-id="4f839-106">Ezt az eljárást a gépkezelő használja.</span><span class="sxs-lookup"><span data-stu-id="4f839-106">This procedure is intended for the machine operator.</span></span> <span data-ttu-id="4f839-107">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="4f839-107">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="4f839-108">Ugorjon a Gyártásvezérlés > Kanban > Kanbantábla feldolgozási feladatokhoz lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4f839-108">Go to Production control > Kanban > Kanban board for process jobs.</span></span>
2. <span data-ttu-id="4f839-109">A Munkacella mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="4f839-109">In the Work cell field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="4f839-110">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="4f839-110">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="4f839-111">Jelölje ki az 1250 munkacellát.</span><span class="sxs-lookup"><span data-stu-id="4f839-111">Select work cell 1250.</span></span>  
4. <span data-ttu-id="4f839-112">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="4f839-112">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="4f839-113">Válassza ki a 000356 kanbant.</span><span class="sxs-lookup"><span data-stu-id="4f839-113">Select Kanban 000356.</span></span>  
5. <span data-ttu-id="4f839-114">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="4f839-114">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="4f839-115">Szüntesse meg a 4. sor kijelölését a listában,</span><span class="sxs-lookup"><span data-stu-id="4f839-115">In the list, deselect row 4.</span></span> <span data-ttu-id="4f839-116">jelölje ki a 4. sort, ha nem végezte el az „A feldolgozási kanbanfeladat előkészítése, amikor az anyagok elérhetők” feladatot.</span><span class="sxs-lookup"><span data-stu-id="4f839-116">or Select row 4 if you haven't completed the task "Prepare a process kanban job when materials are available."</span></span>  
6. <span data-ttu-id="4f839-117">Bontsa ki a Kitárolási lista részt.</span><span class="sxs-lookup"><span data-stu-id="4f839-117">Toggle the expansion of the Picking list section.</span></span>
    * <span data-ttu-id="4f839-118">A Nem található bejegyzés ikon az ellátási állapotnál azt jelzi, hogy a P0002 cikk 48 egyedi egysége hiányzik a munkacellából.</span><span class="sxs-lookup"><span data-stu-id="4f839-118">The No entry icon in the supply status indicates that 48 ea of item P0002 are missing for the work cell.</span></span>  

## <a name="transfer-materials-to-work-cell"></a><span data-ttu-id="4f839-119">Anyagok átvitele a munkacellába</span><span class="sxs-lookup"><span data-stu-id="4f839-119">Transfer materials to work cell</span></span>
1. <span data-ttu-id="4f839-120">Bontsa ki az Átviteli feladatok részt.</span><span class="sxs-lookup"><span data-stu-id="4f839-120">Toggle the expansion of the Transfer jobs section.</span></span>
2. <span data-ttu-id="4f839-121">A Gyorsszűrő használatával szűrjön rá a P0002 értékű Cikkszám mezőkre.</span><span class="sxs-lookup"><span data-stu-id="4f839-121">Use the Quick Filter to filter on the Item number field with a value of 'P0002'.</span></span>
3. <span data-ttu-id="4f839-122">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="4f839-122">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="4f839-123">Kattintson a Start elemre.</span><span class="sxs-lookup"><span data-stu-id="4f839-123">Click Start.</span></span>
    * <span data-ttu-id="4f839-124">Az áthelyezés folyamatban.</span><span class="sxs-lookup"><span data-stu-id="4f839-124">Transfer is in progress.</span></span>  
5. <span data-ttu-id="4f839-125">Kattintson a Befejezés gombra.</span><span class="sxs-lookup"><span data-stu-id="4f839-125">Click Complete.</span></span>
    * <span data-ttu-id="4f839-126">A P0002 cikk most már elérhető a kanbanfeladat kitárolási listájában.</span><span class="sxs-lookup"><span data-stu-id="4f839-126">Item P0002 is now available in the picking list for the kanban job.</span></span> <span data-ttu-id="4f839-127">Ez azt jelenti, hogy elkészíthetjük a kanbant a szükséges anyagokkal.</span><span class="sxs-lookup"><span data-stu-id="4f839-127">This means that we can prepare the kanban with all the needed materials.</span></span>  
6. <span data-ttu-id="4f839-128">Kattintson az Előkészítés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4f839-128">Click Prepare.</span></span>
    * <span data-ttu-id="4f839-129">Figyelje meg, hogy a Feladat állapotának ikonja jelzi, ha a feladat elkészült.</span><span class="sxs-lookup"><span data-stu-id="4f839-129">Notice that an icon in the Job status indicates that the job is now ready.</span></span>  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]