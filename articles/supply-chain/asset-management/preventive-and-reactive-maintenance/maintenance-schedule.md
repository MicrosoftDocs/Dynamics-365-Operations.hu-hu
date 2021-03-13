---
title: Karbantartási ütemezés
description: Ez a cikk az Eszközkezelés karbantartási ütemezését ismerteti.
author: josaw1
manager: tfehr
ms.date: 08/27/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetObjectCalendarCreateWO, EntAssetObjectCalendarListPagePoolsOpen, EntAssetObjectCalendarListPage, EntAssetObjectCalendarListPagePreviewPart, EntAssetObjectCalendarEdit, EntAssetObjectCalendarAdjust, EntAssetObjectCalendarDiscard, EntAssetObjectCalendarInfoPart
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: d235a3797b1acee9c92c3d81e8b4a20e1f7c5c75
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/16/2021
ms.locfileid: "5017954"
---
# <a name="maintenance-schedule"></a><span data-ttu-id="94b1e-103">Karbantartási ütemezés</span><span class="sxs-lookup"><span data-stu-id="94b1e-103">Maintenance schedule</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="94b1e-104">A karbantartási ütemezésben az elvárt és végrehajtandó megelőző karbantartási tervek, a karbantartási kérések és karbantartási körök találhatók. Lehetséges, hogy néhány ütemezési sort munkarendelésekké alakítottak.</span><span class="sxs-lookup"><span data-stu-id="94b1e-104">The maintenance schedule contains a list of all the expected preventive maintenance plans, maintenance requests, and maintenance rounds to be carried out. Some schedule lines may have been converted to work orders.</span></span>

<span data-ttu-id="94b1e-105">A karbantartási ütemezés négy nézete némileg különbözik, attól függően, hogy melyik karbantartási ütemezési sort szeretné megtekinteni.</span><span class="sxs-lookup"><span data-stu-id="94b1e-105">The four maintenance schedule views are slightly different, depending on which maintenance schedule lines you want to see.</span></span>

| <span data-ttu-id="94b1e-106">Menüelem</span><span class="sxs-lookup"><span data-stu-id="94b1e-106">Menu item</span></span>                  | <span data-ttu-id="94b1e-107">A tartalmak leírása</span><span class="sxs-lookup"><span data-stu-id="94b1e-107">Description of contents</span></span>                                                                                                                                             |
|----------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="94b1e-108">Összes karbantartási ütemezés</span><span class="sxs-lookup"><span data-stu-id="94b1e-108">All maintenance schedule</span></span>       | <span data-ttu-id="94b1e-109">A karbantartási ütemezés minden sora látható.</span><span class="sxs-lookup"><span data-stu-id="94b1e-109">All maintenance schedule lines are shown.</span></span>     |
| <span data-ttu-id="94b1e-110">Saját eszközütemezés</span><span class="sxs-lookup"><span data-stu-id="94b1e-110">My asset schedule</span></span>        | <span data-ttu-id="94b1e-111">Ebben a listában a karbantartási ütemezés összes olyan sora látható, amely olyan munkavégzési helyszíneken telepített eszközöket tartalmaz, ahova Ön dolgozóként kapcsolódik (ezt a [Karbantartási dolgozók és dolgozói csoportok](../setup-for-objects/workers-and-worker-groups.md) részen kell beállítani).</span><span class="sxs-lookup"><span data-stu-id="94b1e-111">All maintenance schedule lines containing assets installed on functional locations to which you are related as a worker (set up in [Maintenance workers and worker groups](../setup-for-objects/workers-and-worker-groups.md)) are shown in this list.</span></span> |
| <span data-ttu-id="94b1e-112">Karbantartási ütemezési sorok megnyitása</span><span class="sxs-lookup"><span data-stu-id="94b1e-112">Open maintenance schedule lines</span></span> | <span data-ttu-id="94b1e-113">Ebben a listában a „Létrehozva” állapotú karbantartási ütemezési sorok láthatók. Ez az állapot azt jelenti, hogy ezek a sorok még nem lettek munkarendeléssé alakítva vagy elvetve.</span><span class="sxs-lookup"><span data-stu-id="94b1e-113">Maintenance schedule lines with status "Created" - meaning they have not yet been converted to a work order or discarded - are shown in this list.</span></span>                                            |
| <span data-ttu-id="94b1e-114">Karbantartási ütemezési gyűjtők megnyitása</span><span class="sxs-lookup"><span data-stu-id="94b1e-114">Open maintenance schedule pools</span></span> | <span data-ttu-id="94b1e-115">Ebben a listában láthatók a munkarendelési gyűjtőhöz kapcsolódó karbantartási ütemezési sorok.</span><span class="sxs-lookup"><span data-stu-id="94b1e-115">Maintenance schedule lines related to a work order pool are shown in this list.</span></span>                                                                                                                  |

>[!NOTE]
><span data-ttu-id="94b1e-116">Ha a karbantartási ütemezés egy sora több munkarendelési gyűjtőben is szerepel (lásd: [Munkarendelés-gyűjtők](../work-orders/work-order-pools.md)), akkor minden gyűjtőhöz egy rekord jelenik meg a **Nyitott karbantartási ütemezési csoportok** részen.</span><span class="sxs-lookup"><span data-stu-id="94b1e-116">If a maintenance schedule line is included in several work order pools (refer to [Work order pools](../work-orders/work-order-pools.md)), one record is shown for each pool in **Open maintenance schedule pools**.</span></span> <span data-ttu-id="94b1e-117">Ez a munkarendelés-gyűjtők szűrési beállításainak optimalizálására szolgál.</span><span class="sxs-lookup"><span data-stu-id="94b1e-117">This is done to optimize filtering options on work order pools.</span></span>

<span data-ttu-id="94b1e-118">Karbantartási ütemezés megnyitása:</span><span class="sxs-lookup"><span data-stu-id="94b1e-118">To open a maintenance schedule:</span></span>

1. <span data-ttu-id="94b1e-119">Kattintson az **Eszközkezelés** > **Közös** > **Karbantartási ütemezés** > **Összes karbantartási ütemezés** vagy **Nyitott karbantartási ütemezési sorok** vagy **Nyitott karbantartási ütemezési csoportok** elemre.</span><span class="sxs-lookup"><span data-stu-id="94b1e-119">Click **Asset management** > **Common** > **Maintenance schedule** > **All maintenance schedule** or **Open maintenance schedule lines** or **Open maintenance schedule pools**.</span></span>

2. <span data-ttu-id="94b1e-120">A karbantartási ütemezés frissítéséhez kattintson a **Karbantartási terv** vagy a **Karbantartási körök** elemre.</span><span class="sxs-lookup"><span data-stu-id="94b1e-120">To update the maintenance schedule, click **Maintenance plan** or **Maintenance rounds**.</span></span> 

3. <span data-ttu-id="94b1e-121">A karbantartási ütemezési sor szerkesztéséhez jelölje ki a sort, és kattintson a **Szerkesztés** elemre.</span><span class="sxs-lookup"><span data-stu-id="94b1e-121">You can edit a maintenance schedule line by selecting it and clicking **Edit**.</span></span> <span data-ttu-id="94b1e-122">Egyszerűen frissítheti például a szolgáltatási szintet vagy a feladatért felelős dolgozót.</span><span class="sxs-lookup"><span data-stu-id="94b1e-122">For example, you can easily update the service level or the worker responsible for the job.</span></span> <span data-ttu-id="94b1e-123">A karbantartási ütemezésnek csak azok a sorai szerkeszthetők, amelyek még nem kapcsolódnak munkarendeléshez.</span><span class="sxs-lookup"><span data-stu-id="94b1e-123">You can only edit maintenance schedule lines that have not yet been connected to a work order.</span></span>

4. <span data-ttu-id="94b1e-124">A karbantartási ütemezési sor törléséhez jelölje ki a sort a listaoldalon, és kattintson a **Törlés** gombra.</span><span class="sxs-lookup"><span data-stu-id="94b1e-124">You can delete a maintenance schedule line by selecting it in the list page and clicking **Delete**.</span></span>

5. <span data-ttu-id="94b1e-125">A karbantartási ütemezési sor elvetéséhez jelölje ki a sort a listaoldalon, és kattintson az **Elvetés** gombra.</span><span class="sxs-lookup"><span data-stu-id="94b1e-125">You can discard a maintenance schedule line by selecting it in the list page and clicking **Discard**.</span></span> <span data-ttu-id="94b1e-126">Ez a funkció akkor hasznos, ha például egy eszköz egy 2000 km-es és egy 10 000 km-es karbantartási tervvel is rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="94b1e-126">This function is useful if, for example, an asset has a 2,000 km maintenance plan and a 10,000 km maintenance plan.</span></span> <span data-ttu-id="94b1e-127">Ekkor érdemes lehet elvetni a 2000 km-es karbantartási tervből létrehozott sort, ha az egyezik a 10 000 (vagy 20 000 vagy 30 000) km-es terv sorával.</span><span class="sxs-lookup"><span data-stu-id="94b1e-127">Then, you may want to discard the line created from the 2,000 km maintenance plan when it coincides with 10,000 km, 20,000 km, 30,000 km, and so on.</span></span> <span data-ttu-id="94b1e-128">Ha egy karbantartási tervhez kapcsolódó karbantartási ütemezési sort elvet, akkor az a sor többet nem fog megjelenni az adott karbantartási terv ütemezésekor.</span><span class="sxs-lookup"><span data-stu-id="94b1e-128">If you discard a maintenance schedule line related to a maintenance plan, that line will never again appear when that maintenance plan is scheduled.</span></span>

6. <span data-ttu-id="94b1e-129">Ha azt szeretné, hogy minden kiválasztott sor szerepeljen ugyanabban a munkarendelési gyűjtőben, akkor válassza ki a karbantartási ütemezés több sorát az **Összes karbantartási ütemezés** részen, és kattintson a **Munkarendelés-gyűjtő** elemre.</span><span class="sxs-lookup"><span data-stu-id="94b1e-129">You can select a number of maintenance schedule lines in **All maintenance schedule** and click **Work order pool**, if you want all selected lines to be included in the same work order pool.</span></span>

7. <span data-ttu-id="94b1e-130">Ha több sorhoz szeretné végrehajtani ugyanazt a módosítást, akkor válassza ki a karbantartási ütemezés több sorát az **Összes karbantartási ütemezés** vagy a **Nyitott karbantartási ütemezési sorok** vagy a **Nyitott karbantartási ütemezési csoportok** részen, majd kattintson az **Ütemezés kiigazítása** elemre.</span><span class="sxs-lookup"><span data-stu-id="94b1e-130">You can select a number of maintenance schedule lines in **All maintenance schedule** or **Open maintenance schedule lines** or **Open maintenance schedule pools** and click **Adjust schedule** if you want to make the same adjustments on several lines.</span></span> <span data-ttu-id="94b1e-131">A kiválasztott karbantartási ütemezési soroknál módosíthatja a várt kezdési és befejezési dátumot, a szolgáltatási szintet, valamint a karbantartási dolgozók felelős csoportját vagy a felelős karbantartási dolgozót.</span><span class="sxs-lookup"><span data-stu-id="94b1e-131">You can change expected start and end dates, service level, and the responsible maintenance worker group or responsible maintenance worker related to the selected maintenance schedule lines.</span></span>

- <span data-ttu-id="94b1e-132">Amikor egy karbantartási ütemezési sor egy munkarendeléshez kapcsolódik, a munkarendelés azonosítója jelenik meg a **Munkarendelés** mezőben.</span><span class="sxs-lookup"><span data-stu-id="94b1e-132">When a maintenance schedule line has been related to a work order, the work order ID will be displayed in the **Work order** field.</span></span>  
- <span data-ttu-id="94b1e-133">A **Minden eszköz** részletes nézet > **Eszköz karbantartási tervei** gyorslapon kiválaszthatja az eszköz karbantartási terveit.</span><span class="sxs-lookup"><span data-stu-id="94b1e-133">In **All assets** details view > **Asset maintenance plans** FastTab, you can select maintenance plans for the asset.</span></span> <span data-ttu-id="94b1e-134">Ha később törli az eszközhöz kapcsolódó karbantartási terv egyik sorát az **Összes eszköz** részen, akkor automatikusan törlődik a karbantartási terv összes „Létrehozott” állapotú sora, amely az adott karbantartási terv alapján jött létre.</span><span class="sxs-lookup"><span data-stu-id="94b1e-134">Later, if you delete a maintenance plan line related to an asset in **All assets**, you also automatically delete all maintenance schedule lines with status "Created" that have been created based on that maintenance plan.</span></span> <span data-ttu-id="94b1e-135">Lásd még: [Eszköz létrehozása](../objects/create-an-object.md).</span><span class="sxs-lookup"><span data-stu-id="94b1e-135">See also [Create an asset](../objects/create-an-object.md).</span></span>

<span data-ttu-id="94b1e-136">Az alábbi ábra az **Összes karbantartási ütemezés** listaoldalt mutatja.</span><span class="sxs-lookup"><span data-stu-id="94b1e-136">The illustration below shows the **All maintenance schedule** list page.</span></span>

![1. ábra](media/16-preventive-maintenance.png)

