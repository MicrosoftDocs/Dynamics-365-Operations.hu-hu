---
title: Az Anyagjegyzéksor esemény kanbanszabályának létrehozása
description: Ez a feladat az esemény kanbanszabály létrehozásának beállítására szolgál a termelési Anyagjegyzék sorok ellátásának a vegyes lean és a klasszikus éles környezetben történő biztosítása érdekében.
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, InventItemIdLookupSimple, ProdTableListPage, ProdTableCreate, InventItemIdLookupPurchase, ProdTable, ProdBOM, ProdParmCostEstimation
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 82a4252548fd030f2a044436ff607da5125d2854
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1551929"
---
# <a name="create-a-bom-line-event-kanban-rule"></a><span data-ttu-id="16a43-103">Az Anyagjegyzéksor esemény kanbanszabályának létrehozása</span><span class="sxs-lookup"><span data-stu-id="16a43-103">Create a BOM line event kanban rule</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="16a43-104">Ez a feladat az esemény kanbanszabály létrehozásának beállítására szolgál a termelési Anyagjegyzék sorok ellátásának a vegyes lean és a klasszikus éles környezetben történő biztosítása érdekében.</span><span class="sxs-lookup"><span data-stu-id="16a43-104">This task focuses on the setup needed to create an event kanban rule to ensure supply for production BOM lines in a mixed lean and classic production environment.</span></span> <span data-ttu-id="16a43-105">A feladat létrehozásához az USMF bemutató vállalatot használtuk példaként.</span><span class="sxs-lookup"><span data-stu-id="16a43-105">The demo data company used to create this task is USMF.</span></span> <span data-ttu-id="16a43-106">Ez az feladat a Folyamatmérnök vagy az Érték-előállítási vezető munkáját segíti, mert ők készítik elő az új vagy a módosított termék termelését.</span><span class="sxs-lookup"><span data-stu-id="16a43-106">This task is intended for the process engineer or the value stream manager, as they prepare production of a new or modified product.</span></span>


## <a name="create-a-new-kanban-rule"></a><span data-ttu-id="16a43-107">Új kanbanszabály létrehozása</span><span class="sxs-lookup"><span data-stu-id="16a43-107">Create a new kanban rule</span></span>
1. <span data-ttu-id="16a43-108">Ugorjon a Gyártásvezérlés > Időszakos feladatok > Kanbanmennyiség-számítás > Kanbanszabályok pontra.</span><span class="sxs-lookup"><span data-stu-id="16a43-108">Go to Production control > Periodic tasks > Kanban quantity calculation > Kanban rules.</span></span>
2. <span data-ttu-id="16a43-109">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="16a43-109">Click New.</span></span>
3. <span data-ttu-id="16a43-110">A Típus mezőben válassza ki a „Terhelések” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="16a43-110">In the Type field, select 'Withdrawal'.</span></span>
    * <span data-ttu-id="16a43-111">A Levonás típusát az átvitel kanbanok létrehozására szolgál.</span><span class="sxs-lookup"><span data-stu-id="16a43-111">The Withdrawal type is used to create transfer kanbans.</span></span>  
4. <span data-ttu-id="16a43-112">A Feltöltési stratégia mezőben válassza az „Esemény” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="16a43-112">In the Replenishment strategy field, select 'Event'.</span></span>
    * <span data-ttu-id="16a43-113">A rendszer az Esemény stratégiát választja ki az eseményen alapuló kanbanok átvitelének létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="16a43-113">The Event strategy is selected to create the transfer of kanbans based on an event.</span></span> <span data-ttu-id="16a43-114">A feladat útmutató később ajánlott aktiválni a folyamatot a termelési rendelés becslésével.</span><span class="sxs-lookup"><span data-stu-id="16a43-114">Later in the task guide, we will trigger it by estimating a production order.</span></span>  
5. <span data-ttu-id="16a43-115">Az Első tervezési tevékenység mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="16a43-115">In the First plan activity field, enter or select a value.</span></span>
    * <span data-ttu-id="16a43-116">Adja meg vagy válassza ki a ReplenishSpeakerComponents lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="16a43-116">Enter or select ReplenishSpeakerComponents.</span></span> <span data-ttu-id="16a43-117">Ez az Átmozgatási tevékenység érkeztetési (kimenő) raktárral és 12-es hellyel rendelkezik, ami azt jelenti, hogy az anyagot a 12-es raktárba, a 12-es helyre helyezik át.</span><span class="sxs-lookup"><span data-stu-id="16a43-117">This transfer activity has receipt (output) warehouse and location 12, which means that material will be moved to location 12 in warehouse 12.</span></span>  
6. <span data-ttu-id="16a43-118">A Részletek szakasz kibontása.</span><span class="sxs-lookup"><span data-stu-id="16a43-118">Expand the Details section.</span></span>
7. <span data-ttu-id="16a43-119">A Termék mezőben adja meg vagy válassza ki az M0001 értéket.</span><span class="sxs-lookup"><span data-stu-id="16a43-119">In the Product field, enter or select M0001.</span></span>
8. <span data-ttu-id="16a43-120">Bontsa ki a Események szakaszt.</span><span class="sxs-lookup"><span data-stu-id="16a43-120">Expand the Events section.</span></span>
9. <span data-ttu-id="16a43-121">Az Anyagjegyzéksor-esemény mezőben válassza ki az „Automatikus” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="16a43-121">In the BOM line event field, select 'Automatic'.</span></span>
    * <span data-ttu-id="16a43-122">Az Anyagjegyzéksor esemény mező Automatikus módra van beállítva, a rendszer a kanbant a termelési rendelés anyagjegyzék soraihoz szükséges anyagok feltöltéséhez hozza létre.</span><span class="sxs-lookup"><span data-stu-id="16a43-122">With the BOM line event field set to Automatic, kanban will be created to fulfill material needs for production order BOM lines.</span></span>  
10. <span data-ttu-id="16a43-123">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="16a43-123">Close the page.</span></span>

## <a name="create-and-modify-a-new-production-order"></a><span data-ttu-id="16a43-124">Új termelési rendelés létrehozása és módosítása.</span><span class="sxs-lookup"><span data-stu-id="16a43-124">Create and modify a new production order</span></span>
1. <span data-ttu-id="16a43-125">Ugrás a Gyártásvezérlés > Termelési rendelések > Minden termelési rendelésre.</span><span class="sxs-lookup"><span data-stu-id="16a43-125">Go to Production control > Production orders > All production orders.</span></span>
2. <span data-ttu-id="16a43-126">Kattintson az Új termelési rendelés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="16a43-126">Click New production order.</span></span>
3. <span data-ttu-id="16a43-127">Az Elemszám mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="16a43-127">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="16a43-128">Adja meg vagy válassza ki az „L0001” értéket.</span><span class="sxs-lookup"><span data-stu-id="16a43-128">Enter or select 'L0001'.</span></span> <span data-ttu-id="16a43-129">Ajánlatos az L0001 cikket használni, mert az L0001 cikk anyagjegyzéke tartalmazza az M0001 cikket.</span><span class="sxs-lookup"><span data-stu-id="16a43-129">We use item L0001 because item M0001 is included in the BOM for item L0001.</span></span>  
4. <span data-ttu-id="16a43-130">Kattintson a Létrehozás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="16a43-130">Click Create.</span></span>
5. <span data-ttu-id="16a43-131">A listában kattintson az L0001-es sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="16a43-131">In the list, click the link in the row for L0001</span></span>
6. <span data-ttu-id="16a43-132">Kattintson az Anyagjegyzék elemre.</span><span class="sxs-lookup"><span data-stu-id="16a43-132">Click BOM.</span></span>
7. <span data-ttu-id="16a43-133">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="16a43-133">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="16a43-134">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="16a43-134">Click Edit.</span></span>
9. <span data-ttu-id="16a43-135">A Sor típusa mezőben válassza ki a „Rögzített készletek” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="16a43-135">In the Line type field, select 'Pegged supply'.</span></span>
    * <span data-ttu-id="16a43-136">A rendszer a rögzített készleteket választja ki a kanban ellátási létrehozásának elindításához.</span><span class="sxs-lookup"><span data-stu-id="16a43-136">Pegged supply is selected to trigger the supply creation of a kanban.</span></span>  
10. <span data-ttu-id="16a43-137">Válassza a Nem lehetőséget az Erőforrás-felhasználás mezőben.</span><span class="sxs-lookup"><span data-stu-id="16a43-137">Select No in the Resource consumption field.</span></span>
    * <span data-ttu-id="16a43-138">Az Erőforrás-felhasználás jelölőnégyzet törlése lehetővé teszi a raktár módosítását.</span><span class="sxs-lookup"><span data-stu-id="16a43-138">Clearing the check box of Resource consumption lets us change the warehouse.</span></span>  
11. <span data-ttu-id="16a43-139">Bontsa ki a Készletdimenziók szakaszt.</span><span class="sxs-lookup"><span data-stu-id="16a43-139">Expand the Inventory dimensions section.</span></span>
12. <span data-ttu-id="16a43-140">A Raktár mezőbe írja be a 12 értéket.</span><span class="sxs-lookup"><span data-stu-id="16a43-140">In the Warehouse field, type '12'.</span></span>
    * <span data-ttu-id="16a43-141">A Raktárt 12-es értékre állította be a rendszer, mert ez a visszavonási tevékenység kimeneti raktárat.</span><span class="sxs-lookup"><span data-stu-id="16a43-141">Warehouse is set to 12 because this is the output warehouse for the withdrawal activity.</span></span>  
13. <span data-ttu-id="16a43-142">Írja be a Hely mezőbe a „12” értéket.</span><span class="sxs-lookup"><span data-stu-id="16a43-142">In the Location field, type '12'.</span></span>
    * <span data-ttu-id="16a43-143">A Helyet 12-es értékre állította be a rendszer, mert ez a visszavonási tevékenység kimeneti helye.</span><span class="sxs-lookup"><span data-stu-id="16a43-143">Location is set to 12 because this is the output location of the withdrawal activity.</span></span>  
14. <span data-ttu-id="16a43-144">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="16a43-144">Close the page.</span></span>
15. <span data-ttu-id="16a43-145">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="16a43-145">Close the page.</span></span>

## <a name="estimate-the-production-order-and-view-the-kanban-created"></a><span data-ttu-id="16a43-146">A termelési rendelés becslése és a létrehozott kanban megtekintése</span><span class="sxs-lookup"><span data-stu-id="16a43-146">Estimate the production order and view the kanban created</span></span>
1. <span data-ttu-id="16a43-147">Kattintson a Becslés elemre.</span><span class="sxs-lookup"><span data-stu-id="16a43-147">Click Estimate.</span></span>
    * <span data-ttu-id="16a43-148">A termelési rendelés becslése a hozzárendelt kanban létrehozását indítja el az M0001 cikk beszerzéséhez.</span><span class="sxs-lookup"><span data-stu-id="16a43-148">Estimating the production order will trigger the creation of the associated kanban to supply item M0001.</span></span>  
2. <span data-ttu-id="16a43-149">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="16a43-149">Click OK.</span></span>
3. <span data-ttu-id="16a43-150">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="16a43-150">Close the page.</span></span>
4. <span data-ttu-id="16a43-151">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="16a43-151">Close the page.</span></span>
5. <span data-ttu-id="16a43-152">Ugorjon a Termékinformációk kezelése > A lean manufacturing > Kanbanszabályok lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="16a43-152">Go to Product information management > Lean manufacturing > Kanban rules.</span></span>
6. <span data-ttu-id="16a43-153">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="16a43-153">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="16a43-154">Válassza ki az M0001 cikkre vonatkozóan létrehozott esemény kanbanszabályt.</span><span class="sxs-lookup"><span data-stu-id="16a43-154">Select the event kanban rule created for item M0001.</span></span>  
7. <span data-ttu-id="16a43-155">Bontsa ki a Kanbanok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="16a43-155">Expand the Kanbans section.</span></span>
8. <span data-ttu-id="16a43-156">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="16a43-156">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="16a43-157">Vegye figyelembe, hogy a rendszer a kanbant az M0001 cikk beszerzésére hozta létre a becsült termelési rendelésre vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="16a43-157">Notice the kanban created to supply M0001 for the estimated production order.</span></span>  
    * <span data-ttu-id="16a43-158">Ez az utolsó lépés!</span><span class="sxs-lookup"><span data-stu-id="16a43-158">This is the last step!</span></span>  

