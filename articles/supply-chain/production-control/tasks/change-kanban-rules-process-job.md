---
title: Kanbanszabályok módosítása egy feldolgozási feladat számára
description: Ez az eljárás egy adott kanbanhoz használt kanbanszabály módosítását tekinti át.
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanRules, KanbanRuleDuplicate, KanbanJobSchedulingListPage, LeanRuleReassignmentWizard, KanbanReassignRuleLookup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 38d9ff0a7d6aeb0a589fd6b9ab34b818c46644cc
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1554276"
---
# <a name="change-kanban-rules-for-a-process-job"></a><span data-ttu-id="9aa22-103">Kanbanszabályok módosítása egy feldolgozási feladat számára</span><span class="sxs-lookup"><span data-stu-id="9aa22-103">Change kanban rules for a process job</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="9aa22-104">Ez az eljárás egy adott kanbanhoz használt kanbanszabály módosítását tekinti át.</span><span class="sxs-lookup"><span data-stu-id="9aa22-104">This procedure focuses on changing the used kanban rule for a given kanban.</span></span> <span data-ttu-id="9aa22-105">Ez akkor hasznos, ha terhelési erőforrást szintez, vagy lebontás esetén.</span><span class="sxs-lookup"><span data-stu-id="9aa22-105">This is useful to level load resources or in case of breakdown.</span></span> <span data-ttu-id="9aa22-106">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="9aa22-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="9aa22-107">Ez az eljárás a Tervező számára hasznos, aki a lean manufacturing vállalatnál dolgozik, és az érték-előállítási folyamatért felelős.</span><span class="sxs-lookup"><span data-stu-id="9aa22-107">This procedure is intended for the planner, working at a lean manufacturing company, responsible for the value stream.</span></span>


## <a name="copy-kanban-rule"></a><span data-ttu-id="9aa22-108">Kanbanszabály másolása</span><span class="sxs-lookup"><span data-stu-id="9aa22-108">Copy kanban rule</span></span>
1. <span data-ttu-id="9aa22-109">Ugorjon a Kanbanszabályokhoz.</span><span class="sxs-lookup"><span data-stu-id="9aa22-109">Go to Kanban rules.</span></span>
2. <span data-ttu-id="9aa22-110">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="9aa22-110">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="9aa22-111">Válassza ki a 000022 esemény-kanbanszabályt az L0001 termékhez.</span><span class="sxs-lookup"><span data-stu-id="9aa22-111">Select Event Kanban rule 000022 for L0001.</span></span>  
3. <span data-ttu-id="9aa22-112">Kattintson a Kanbanszabály másolása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="9aa22-112">Click Duplicate kanban rule.</span></span>
4. <span data-ttu-id="9aa22-113">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="9aa22-113">Click OK.</span></span>

## <a name="change-kanban-rule"></a><span data-ttu-id="9aa22-114">Kanbanszabály módosítása</span><span class="sxs-lookup"><span data-stu-id="9aa22-114">Change kanban rule</span></span>
1. <span data-ttu-id="9aa22-115">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="9aa22-115">Close the page.</span></span>
2. <span data-ttu-id="9aa22-116">Ugrás ide: Kanbanfeladat ütemezése.</span><span class="sxs-lookup"><span data-stu-id="9aa22-116">Go to Kanban job scheduling.</span></span>
3. <span data-ttu-id="9aa22-117">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="9aa22-117">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="9aa22-118">Válassza ki a Kanban 000177 sorát.</span><span class="sxs-lookup"><span data-stu-id="9aa22-118">Select line with Kanban 000177.</span></span>  
4. <span data-ttu-id="9aa22-119">Kattintson az Alternatív kanbanszabály használata elemre.</span><span class="sxs-lookup"><span data-stu-id="9aa22-119">Click Use alternative kanban rule.</span></span>
5. <span data-ttu-id="9aa22-120">Kattintson a Tovább gombra.</span><span class="sxs-lookup"><span data-stu-id="9aa22-120">Click Next.</span></span>
6. <span data-ttu-id="9aa22-121">A Kanbanszabály mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="9aa22-121">In the Kanban rule field, enter or select a value.</span></span>
    * <span data-ttu-id="9aa22-122">Válassza ki a korábban létrehozott kanbanszabályt.</span><span class="sxs-lookup"><span data-stu-id="9aa22-122">Select the kanban rule that was created earlier.</span></span> <span data-ttu-id="9aa22-123">Ez a legnagyobb számmal rendelkező kanbanszabály.</span><span class="sxs-lookup"><span data-stu-id="9aa22-123">This is the kanban rule with the highest number.</span></span>  
7. <span data-ttu-id="9aa22-124">Kattintson a Finish gombra.</span><span class="sxs-lookup"><span data-stu-id="9aa22-124">Click Finish.</span></span>
    * <span data-ttu-id="9aa22-125">Most a kanbanfeladat már egy másik kanbanszabályt használ.</span><span class="sxs-lookup"><span data-stu-id="9aa22-125">Now the kanban job is using an another kanban rule.</span></span> <span data-ttu-id="9aa22-126">Ez hasznos lehet a terhelési munkacellák szintezéséhez.</span><span class="sxs-lookup"><span data-stu-id="9aa22-126">This can be useful to level load work cells.</span></span>  

