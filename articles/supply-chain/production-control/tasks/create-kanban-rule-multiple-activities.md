--- 
title: "Kanbanszabály létrehozása több tevékenységhez"
description: "Ez az eljárás bemutatja, hogy hogyan hozhat létre olyan kanbanszabályt, amely a termelési folyamatból származó többféle tevékenységet tartalmaz."
author: ChristianRytt
manager: AnnBe
ms.date: 08/24/2016
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
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: d6d0c50da3124553124b65f6ba0e1c5ed35e8613
ms.contentlocale: hu-hu
ms.lasthandoff: 08/29/2017

---
# <a name="create-a-kanban-rule-for-multiple-activities"></a><span data-ttu-id="12483-103">Kanbanszabály létrehozása több tevékenységhez</span><span class="sxs-lookup"><span data-stu-id="12483-103">Create a kanban rule for multiple activities</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="12483-104">Ez az eljárás bemutatja, hogy hogyan hozhat létre olyan kanbanszabályt, amely a termelési folyamatból származó többféle tevékenységet tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="12483-104">This procedure shows how to create a kanban rule that includes multiple activities from a production flow.</span></span> <span data-ttu-id="12483-105">A feladat létrehozásához az USMF bemutató vállalatot használtuk példaként.</span><span class="sxs-lookup"><span data-stu-id="12483-105">The demo data company used to create this task is USMF.</span></span> <span data-ttu-id="12483-106">Ez a feladat a folyamatmérnök vagy az érték-előállítási vezető munkáját segíti, mivel ők készítik elő az új vagy módosított termékek termelését a lean környezetben.</span><span class="sxs-lookup"><span data-stu-id="12483-106">This task is intended for the process engineer or the value stream manager, as they prepare production of a new or modified product in a lean environment.</span></span>


## <a name="create-a-new-kanban-rule"></a><span data-ttu-id="12483-107">Új kanbanszabály létrehozása</span><span class="sxs-lookup"><span data-stu-id="12483-107">Create a new kanban rule</span></span>
1. <span data-ttu-id="12483-108">Ugorjon a Termékinformációk kezelése > A lean manufacturing > Kanbanszabályok lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="12483-108">Go to Product information management > Lean manufacturing > Kanban rules.</span></span>
2. <span data-ttu-id="12483-109">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="12483-109">Click New.</span></span>
3. <span data-ttu-id="12483-110">A Feltöltési stratégia mezőben válassza ki az „Ütemezve” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="12483-110">In the Replenishment strategy field, select 'Scheduled'.</span></span>
4. <span data-ttu-id="12483-111">Az Első tervezési tevékenység mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="12483-111">In the First plan activity field, enter or select a value.</span></span>
    * <span data-ttu-id="12483-112">Válassza ki a SpeakerAssemblyAndPolish lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="12483-112">Select SpeakerAssemblyAndPolish.</span></span>  
5. <span data-ttu-id="12483-113">Jelölje be a Több tevékenység jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="12483-113">Select the Multiple activities check box.</span></span>
    * <span data-ttu-id="12483-114">A cél az, hogy a kanbanszabály több, mint egy tevékenységet tartalmazzon.</span><span class="sxs-lookup"><span data-stu-id="12483-114">The purpose is to include more than one activity in the kanban rule.</span></span> <span data-ttu-id="12483-115">A termelési folyamatban útvonalat választ az utolsó tervezett tevékenység kiválasztásakor.</span><span class="sxs-lookup"><span data-stu-id="12483-115">You choose a path in the production flow when you select the last plan activity.</span></span>  
6. <span data-ttu-id="12483-116">Az Utolsó tervezési tevékenység mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="12483-116">In the Last plan activity field, enter or select a value.</span></span>
    * <span data-ttu-id="12483-117">Válassza ki a SpeakerTestAndPackaging lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="12483-117">Select SpeakerTestAndPackaging.</span></span> <span data-ttu-id="12483-118">Miután kiválasztotta az értéket, automatikusan megjelenik egy oldal.</span><span class="sxs-lookup"><span data-stu-id="12483-118">After you select the value, a page automatically opens.</span></span> <span data-ttu-id="12483-119">Válassza ki a kanbanfolyamat SpeakerAssemblyAndPolish > SpeakerTestAndPackaging lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="12483-119">Select the kanban flow SpeakerAssemblyAndPolish > SpeakerTestAndPackaging.</span></span> <span data-ttu-id="12483-120">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="12483-120">Click OK.</span></span>  
7. <span data-ttu-id="12483-121">A Részletek szakasz kibontása.</span><span class="sxs-lookup"><span data-stu-id="12483-121">Expand the Details section.</span></span>
8. <span data-ttu-id="12483-122">A Termék mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="12483-122">In the Product field, enter or select a value.</span></span>
    * <span data-ttu-id="12483-123">Válassza ki az L0006 elemet.</span><span class="sxs-lookup"><span data-stu-id="12483-123">Select Item L0006.</span></span>  

## <a name="create-kanban-and-view-jobs"></a><span data-ttu-id="12483-124">Kanban létrehozása és feladatok megtekintése</span><span class="sxs-lookup"><span data-stu-id="12483-124">Create kanban and view jobs</span></span>
1. <span data-ttu-id="12483-125">Bontsa ki a Kanbanok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="12483-125">Expand the Kanbans section.</span></span>
2. <span data-ttu-id="12483-126">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="12483-126">Click Add.</span></span>
3. <span data-ttu-id="12483-127">Írja be az „1” értéket az Új kanbanok száma mezőbe.</span><span class="sxs-lookup"><span data-stu-id="12483-127">In the Number of new kanbans field, enter '1'.</span></span>
    * <span data-ttu-id="12483-128">Ez egy kanbant hoz létre.</span><span class="sxs-lookup"><span data-stu-id="12483-128">This will create one kanban.</span></span>  
4. <span data-ttu-id="12483-129">Állítsa a Termékmennyiséget az „3” értékre.</span><span class="sxs-lookup"><span data-stu-id="12483-129">Set Product quantity to '3'.</span></span>
    * <span data-ttu-id="12483-130">A kanban 3 terméket dolgoz fel.</span><span class="sxs-lookup"><span data-stu-id="12483-130">Kanban will process 3 products.</span></span>  
5. <span data-ttu-id="12483-131">A Határidő dátuma/időpontja mezőben adjon meg egy dátumot és időpontot.</span><span class="sxs-lookup"><span data-stu-id="12483-131">In the Due date/time field, enter a date and time.</span></span>
    * <span data-ttu-id="12483-132">Az aktuális napot adhatja meg.</span><span class="sxs-lookup"><span data-stu-id="12483-132">You can enter Today.</span></span>  
6. <span data-ttu-id="12483-133">Kattintson a Létrehozás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="12483-133">Click Create.</span></span>
7. <span data-ttu-id="12483-134">Kattintson a Részletek gombra.</span><span class="sxs-lookup"><span data-stu-id="12483-134">Click Details.</span></span>
    * <span data-ttu-id="12483-135">Jegyezze meg, hogy a kanban a termelési folyamatból származó két feldolgozási feladattal rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="12483-135">Notice that the kanban has two process jobs from the production flow.</span></span> <span data-ttu-id="12483-136">Az első a SpeakerAssemblyAndPolish, és a második a SpeakerTestAndPackaging.</span><span class="sxs-lookup"><span data-stu-id="12483-136">The first one is SpeakerAssemblyAndPolish, and the second one is SpeakerTestAndPackaging.</span></span>  
    * <span data-ttu-id="12483-137">Ez az utolsó lépés!</span><span class="sxs-lookup"><span data-stu-id="12483-137">This is the last step!</span></span>  


