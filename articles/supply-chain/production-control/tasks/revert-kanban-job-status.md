---
title: Kanbanfeladat állapotának visszaállítása
description: Ez az eljárás egy helytelen kanbanfeladat-állapot visszaállítására irányul.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanBoardWorkCell, KanbanJobStatusUpdate
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 44c9ce805826779ba682561779653d61905fcd8d
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/01/2019
ms.locfileid: "1838511"
---
# <a name="revert-kanban-job-status"></a><span data-ttu-id="8f97d-103">Kanbanfeladat állapotának visszaállítása</span><span class="sxs-lookup"><span data-stu-id="8f97d-103">Revert kanban job status</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="8f97d-104">Ez az eljárás egy helytelen kanbanfeladat-állapot visszaállítására irányul.</span><span class="sxs-lookup"><span data-stu-id="8f97d-104">This procedure focuses on reverting an incorrect kanban job status.</span></span> <span data-ttu-id="8f97d-105">Ez abban az esetben hasznos, ha egy hiba folytán a gépkezelő rossz feladatot frissít vagy rossz állapotot állít be.</span><span class="sxs-lookup"><span data-stu-id="8f97d-105">This is useful in case the machine operator updates the wrong job, or sets the wrong status by mistake.</span></span> <span data-ttu-id="8f97d-106">Ebben az eljárásban a kanbanfeladat egy hiba folytán előkészítettként lett rögzítve, ez az állapot kerül visszaállításra.</span><span class="sxs-lookup"><span data-stu-id="8f97d-106">In this procedure, a kanban job is registered as prepared by mistake, and the status is reverted.</span></span> <span data-ttu-id="8f97d-107">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="8f97d-107">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="8f97d-108">Ez az eljárás egy lean manufacturing vállalatban dolgozó művezető vagy gépkezelő számára javasolt.</span><span class="sxs-lookup"><span data-stu-id="8f97d-108">This procedure is intended for the shop supervisor or machine operator working in a lean manufacturing company.</span></span>


## <a name="open-process-board-for-the-work-cell"></a><span data-ttu-id="8f97d-109">Nyissa meg a munkacella feldolgozási tábláját</span><span class="sxs-lookup"><span data-stu-id="8f97d-109">Open process board for the work cell</span></span>
1. <span data-ttu-id="8f97d-110">Ugorjon a feldolgozási feladatok kanbantáblájára.</span><span class="sxs-lookup"><span data-stu-id="8f97d-110">Go to Kanban board for process jobs.</span></span>
2. <span data-ttu-id="8f97d-111">A Munkacella mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="8f97d-111">In the Work cell field, enter or select a value.</span></span>
    * <span data-ttu-id="8f97d-112">Jelölje ki az 1260 munkacellát.</span><span class="sxs-lookup"><span data-stu-id="8f97d-112">Select work cell 1260.</span></span>  

## <a name="prepare-kanban-job"></a><span data-ttu-id="8f97d-113">Kanbanfeladat előkészítése</span><span class="sxs-lookup"><span data-stu-id="8f97d-113">Prepare kanban job</span></span>
1. <span data-ttu-id="8f97d-114">Kattintson az Előkészítés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8f97d-114">Click Prepare.</span></span>
    * <span data-ttu-id="8f97d-115">Ha nem tud az Előkészítés gombra kattint, mert az beszűrkített, győződjön meg arról, hogy a kijelölt kanbanfeladat állapota tervezett, amelyet az üres kanban ikon mutat.</span><span class="sxs-lookup"><span data-stu-id="8f97d-115">If you can't click Prepare because it is grayed out, make sure that the selected kanban job has status Planned, which is indicated by the empty kanban icon.</span></span> <span data-ttu-id="8f97d-116">Ha az Előkészítés sikertelen, győződjön meg arról, hogy elérhető-e az összes anyag a kitárolási listában.</span><span class="sxs-lookup"><span data-stu-id="8f97d-116">If Prepare fails, make sure that all materials in the Picking list are available.</span></span>  
2. <span data-ttu-id="8f97d-117">Válassza ki a listában az előkészített feladatot.</span><span class="sxs-lookup"><span data-stu-id="8f97d-117">In the list, select the prepared job.</span></span>
    * <span data-ttu-id="8f97d-118">Válassza ki az első, most elkészített feladatot.</span><span class="sxs-lookup"><span data-stu-id="8f97d-118">Select the first job that you have just prepared.</span></span>  
    * <span data-ttu-id="8f97d-119">Figyelje meg, hogy a feladat előkészített állapotba került, amelyet a kanban ikonjában megjelenő háromszög jelez.</span><span class="sxs-lookup"><span data-stu-id="8f97d-119">Notice that the jobs status is prepared, which is indicated with a triangle inside the kanban icon.</span></span>  

## <a name="revert-the-status-of-the-prepared-kanban-job"></a><span data-ttu-id="8f97d-120">Az előkészített kanbanfeladat állapotának visszaállítása</span><span class="sxs-lookup"><span data-stu-id="8f97d-120">Revert the status of the prepared kanban job</span></span>
1. <span data-ttu-id="8f97d-121">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="8f97d-121">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="8f97d-122">Válassza ki az első elkészített feladatot.</span><span class="sxs-lookup"><span data-stu-id="8f97d-122">Select the first job that was prepared.</span></span>  
2. <span data-ttu-id="8f97d-123">A Művelet panelen kattintson a Gyártás elemre.</span><span class="sxs-lookup"><span data-stu-id="8f97d-123">On the Action Pane, click Manufacture.</span></span>
3. <span data-ttu-id="8f97d-124">Kattintson az Állapot visszaállítása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8f97d-124">Click Revert status.</span></span>
    * <span data-ttu-id="8f97d-125">Alternatív kanbanszabály abban az esetben alkalmazható, ha teljesülnek a következő feltételek: – A feltöltési stratégia a két szabály esetén megegyezik.</span><span class="sxs-lookup"><span data-stu-id="8f97d-125">You can use an alternative kanban rule when the following conditions are true:  - The replenishment strategy is the same for both rules.</span></span>  <span data-ttu-id="8f97d-126">- A termelési folyamat verziója a két szabály esetén megegyezik.</span><span class="sxs-lookup"><span data-stu-id="8f97d-126">- The version of the production flow is the same for both rules.</span></span>  <span data-ttu-id="8f97d-127">- A megadott termék a két szabály esetén megegyezik.</span><span class="sxs-lookup"><span data-stu-id="8f97d-127">- The product that is supplied is the same for both rules.</span></span>  <span data-ttu-id="8f97d-128">- A két szabály esetén meg kell egyeznie minden, a kanbanszabályok utolsó műveletére konfigurált lefelé irányuló tevékenységnek.</span><span class="sxs-lookup"><span data-stu-id="8f97d-128">- Any downstream activities that are configured for the last activity of the kanban rules must be the same for both rules.</span></span>  <span data-ttu-id="8f97d-129">- Mindkét szabály esetén ugyanazokat a megadott készletdimenziókat kell beállítani.</span><span class="sxs-lookup"><span data-stu-id="8f97d-129">- The same supplied inventory dimensions must be configured for both rules.</span></span>  <span data-ttu-id="8f97d-130">- Az anyagkezelési egység állapota legyen Nincs hozzárendelve.</span><span class="sxs-lookup"><span data-stu-id="8f97d-130">- The status of the handling unit must be Not assigned.</span></span>  <span data-ttu-id="8f97d-131">- Az eseménykanbanok konfigurációjának azonosnak kell lennie.</span><span class="sxs-lookup"><span data-stu-id="8f97d-131">- The configuration for event kanbans must be the same.</span></span>  
    * <span data-ttu-id="8f97d-132">Győződjön meg róla, hogy az új állapot: Tervezett.</span><span class="sxs-lookup"><span data-stu-id="8f97d-132">Ensure that the new status is Planned.</span></span>  
4. <span data-ttu-id="8f97d-133">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="8f97d-133">Click OK.</span></span>
5. <span data-ttu-id="8f97d-134">A listában szüntesse meg a kiválasztott sor megjelölését.</span><span class="sxs-lookup"><span data-stu-id="8f97d-134">In the list, unmark the selected row.</span></span>
    * <span data-ttu-id="8f97d-135">Válassza ki ugyanazt a feladatot.</span><span class="sxs-lookup"><span data-stu-id="8f97d-135">Select the same job.</span></span>  
    * <span data-ttu-id="8f97d-136">Figyelje meg, hogy a feladat visszaállt Tervezett állapotba, amelyet az üres kanban ikon jelez.</span><span class="sxs-lookup"><span data-stu-id="8f97d-136">Notice that the job status for the kanban job is reverted to Planned, which is indicated by an empty kanban icon.</span></span>  

