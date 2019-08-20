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
ms.openlocfilehash: b0018bafd731ac7a0d74a41869251a2897d553de
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/01/2019
ms.locfileid: "1838559"
---
# <a name="remove-a-kanban-job-from-the-schedule"></a><span data-ttu-id="8b1bd-103">A kanbanfeladat eltávolítása az ütemezésből</span><span class="sxs-lookup"><span data-stu-id="8b1bd-103">Remove a kanban job from the schedule</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="8b1bd-104">Ez az eljárás a tervezett kanbanfeldolgozási feladatot ütemezésből való eltávolításával foglalkozik, ahol a feladatállapotot Nem tervezettre fordítják vissza.</span><span class="sxs-lookup"><span data-stu-id="8b1bd-104">This procedure focuses on removing a planned process kanban job from the schedule by reverting the job status to Not planned.</span></span> <span data-ttu-id="8b1bd-105">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="8b1bd-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="8b1bd-106">Ez az eljárás az üzemirányítási felügyelő vagy termeléstervező munkáját segíti.</span><span class="sxs-lookup"><span data-stu-id="8b1bd-106">This procedure is intended for the shop floor supervisor or production planner.</span></span>


## <a name="find-a-planned-kanban-job"></a><span data-ttu-id="8b1bd-107">Keressen egy tervezett kanbanfeladatot</span><span class="sxs-lookup"><span data-stu-id="8b1bd-107">Find a planned kanban job</span></span>
1. <span data-ttu-id="8b1bd-108">Ugorjon a Gyártásvezérlés > Kanban > Kanbanfeladat ütemezése lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8b1bd-108">Go to Production control > Kanban > Kanban job scheduling.</span></span>
2. <span data-ttu-id="8b1bd-109">A Munkacella mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="8b1bd-109">In the Work cell field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="8b1bd-110">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="8b1bd-110">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="8b1bd-111">Jelölje ki az 1250 munkacellát.</span><span class="sxs-lookup"><span data-stu-id="8b1bd-111">Select work cell 1250.</span></span>  
4. <span data-ttu-id="8b1bd-112">Kattintson a Kiválasztás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8b1bd-112">Click Select.</span></span>
5. <span data-ttu-id="8b1bd-113">A Feladatállapot megjelenítése mezőben válassza ki az „Ütemezett” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8b1bd-113">In the Display job status field, select 'Scheduled'.</span></span>

## <a name="remove-the-planned-kanban-job-from-the-schedule"></a><span data-ttu-id="8b1bd-114">A tervezett kanbanfeladat eltávolítása az ütemezésből</span><span class="sxs-lookup"><span data-stu-id="8b1bd-114">Remove the planned kanban job from the schedule</span></span>
1. <span data-ttu-id="8b1bd-115">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="8b1bd-115">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="8b1bd-116">Válasszon egy feladatot, amely Tervezett állapotú, például egy feladatot 2012. december 19-ről.</span><span class="sxs-lookup"><span data-stu-id="8b1bd-116">Select a job that has the Planned status, for example, a job from December 19, 2012.</span></span>  
2. <span data-ttu-id="8b1bd-117">A Művelet panelen kattintson a Terv elemre.</span><span class="sxs-lookup"><span data-stu-id="8b1bd-117">On the Action Pane, click Plan.</span></span>
3. <span data-ttu-id="8b1bd-118">Kattintson a Feladatállapot visszaállítása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8b1bd-118">Click Revert job status.</span></span>
4. <span data-ttu-id="8b1bd-119">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="8b1bd-119">Click OK.</span></span>
    * <span data-ttu-id="8b1bd-120">Az aktuális feladat állapota így „Tervezett” helyett „Nem tervezett” állapotúra vált, és eltűnik a feldolgozási tábláról.</span><span class="sxs-lookup"><span data-stu-id="8b1bd-120">This will revert the current job status from 'Planned' to 'Not planned' and remove it from the process board.</span></span>   

