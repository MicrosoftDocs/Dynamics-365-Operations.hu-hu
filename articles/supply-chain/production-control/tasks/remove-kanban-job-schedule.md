---
title: A kanbanfeladat eltávolítása az ütemezésből
description: Ez az eljárás a tervezett kanbanfeldolgozási feladatot ütemezésből való eltávolításával foglalkozik, ahol a feladatállapotot Nem tervezettre fordítják vissza.
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanJobSchedulingListPage, SysLookupMultiSelectGrid, KanbanJobStatusUpdate
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4b2137268301beb85906bf7fb26c41f6eb09534c
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/18/2020
ms.locfileid: "3148919"
---
# <a name="remove-a-kanban-job-from-the-schedule"></a><span data-ttu-id="babcf-103">A kanbanfeladat eltávolítása az ütemezésből</span><span class="sxs-lookup"><span data-stu-id="babcf-103">Remove a kanban job from the schedule</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="babcf-104">Ez az eljárás a tervezett kanbanfeldolgozási feladatot ütemezésből való eltávolításával foglalkozik, ahol a feladatállapotot Nem tervezettre fordítják vissza.</span><span class="sxs-lookup"><span data-stu-id="babcf-104">This procedure focuses on removing a planned process kanban job from the schedule by reverting the job status to Not planned.</span></span> <span data-ttu-id="babcf-105">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="babcf-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="babcf-106">Ez az eljárás az üzemirányítási felügyelő vagy termeléstervező munkáját segíti.</span><span class="sxs-lookup"><span data-stu-id="babcf-106">This procedure is intended for the shop floor supervisor or production planner.</span></span>


## <a name="find-a-planned-kanban-job"></a><span data-ttu-id="babcf-107">Keressen egy tervezett kanbanfeladatot</span><span class="sxs-lookup"><span data-stu-id="babcf-107">Find a planned kanban job</span></span>
1. <span data-ttu-id="babcf-108">Ugorjon a Gyártásvezérlés > Kanban > Kanbanfeladat ütemezése lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="babcf-108">Go to Production control > Kanban > Kanban job scheduling.</span></span>
2. <span data-ttu-id="babcf-109">A Munkacella mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="babcf-109">In the Work cell field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="babcf-110">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="babcf-110">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="babcf-111">Jelölje ki az 1250 munkacellát.</span><span class="sxs-lookup"><span data-stu-id="babcf-111">Select work cell 1250.</span></span>  
4. <span data-ttu-id="babcf-112">Kattintson a Kiválasztás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="babcf-112">Click Select.</span></span>
5. <span data-ttu-id="babcf-113">A Feladatállapot megjelenítése mezőben válassza ki az „Ütemezett” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="babcf-113">In the Display job status field, select 'Scheduled'.</span></span>

## <a name="remove-the-planned-kanban-job-from-the-schedule"></a><span data-ttu-id="babcf-114">A tervezett kanbanfeladat eltávolítása az ütemezésből</span><span class="sxs-lookup"><span data-stu-id="babcf-114">Remove the planned kanban job from the schedule</span></span>
1. <span data-ttu-id="babcf-115">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="babcf-115">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="babcf-116">Válasszon egy feladatot, amely Tervezett állapotú, például egy feladatot 2012. december 19-ről.</span><span class="sxs-lookup"><span data-stu-id="babcf-116">Select a job that has the Planned status, for example, a job from December 19, 2012.</span></span>  
2. <span data-ttu-id="babcf-117">A Művelet panelen kattintson a Terv elemre.</span><span class="sxs-lookup"><span data-stu-id="babcf-117">On the Action Pane, click Plan.</span></span>
3. <span data-ttu-id="babcf-118">Kattintson a Feladatállapot visszaállítása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="babcf-118">Click Revert job status.</span></span>
4. <span data-ttu-id="babcf-119">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="babcf-119">Click OK.</span></span>
    * <span data-ttu-id="babcf-120">Az aktuális feladat állapota így „Tervezett” helyett „Nem tervezett” állapotúra vált, és eltűnik a feldolgozási tábláról.</span><span class="sxs-lookup"><span data-stu-id="babcf-120">This will revert the current job status from 'Planned' to 'Not planned' and remove it from the process board.</span></span>   

