---
title: Karbantartási előrejelzések
description: Ez a cikk a karbantartási előrejelzések az Eszközkezelésben való használatát ismerteti.
author: josaw1
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetWorkOrderForecastToJournals, EntAssetWorkOrderForecast
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: c60834a1f818b142a0f2f022d66fe1f42edeb536
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/16/2021
ms.locfileid: "5020862"
---
# <a name="maintenance-forecasts"></a><span data-ttu-id="79b7e-103">Karbantartási előrejelzések</span><span class="sxs-lookup"><span data-stu-id="79b7e-103">Maintenance forecasts</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="79b7e-104">A munkarendelések létrehozásakor munkarendelési feladatokat hoz létre, amelyek a kapcsolódó eszközökkel és karbantartási feladattípusokkal rendelkeznek.</span><span class="sxs-lookup"><span data-stu-id="79b7e-104">When you create a work order, you create work order jobs that have related assets and maintenance job types.</span></span> <span data-ttu-id="79b7e-105">Karbantartási előrejelzéseket tartalmazó karbantartási feladattípus kiválasztásakor a program automatikusan átmásolja a munkarendelésbe az előrejelzéseket.</span><span class="sxs-lookup"><span data-stu-id="79b7e-105">When you select a maintenance job type that contains maintenance forecasts, the forecasts are automatically copied to the work order.</span></span>

<span data-ttu-id="79b7e-106">Előfordulhat, hogy előrejelzési sorokat szeretné egy munkarendeléshez hozzáadni, vagy egy munkarendelésből törölni azokat.</span><span class="sxs-lookup"><span data-stu-id="79b7e-106">You might be able to add forecast lines to a work order or delete them from a work order.</span></span> <span data-ttu-id="79b7e-107">A munkarendelés életciklus-állapotának beállítása, a kapcsolódó projekttípus és a projekt típusára vonatkozó szakaszszabályok határozzák meg, hogy az előrejelzési sorok hozzáadhatók-e a naplóhoz, vagy szerkeszthetők-e.</span><span class="sxs-lookup"><span data-stu-id="79b7e-107">The setup of the work order lifecycle state, the related project type, and the stage rules that are related to the project type determine whether you can add or edit forecast lines.</span></span> <span data-ttu-id="79b7e-108">A munkarendelés életciklus-állapotaival és kapcsolódó projektfázisaival kapcsolatos további információért lásd: [Előrejelzések, munkarendelések és projektek](../integration-to-project-management-and-accounting/forecasts-work-orders-and-projects.md).</span><span class="sxs-lookup"><span data-stu-id="79b7e-108">For more information about work order lifecycle states and related project stages, see [Forecasts, work orders, and projects](../integration-to-project-management-and-accounting/forecasts-work-orders-and-projects.md).</span></span>

1. <span data-ttu-id="79b7e-109">Válassza az **Eszközkezelés** > **Közös** > **Munkarendelések** > **Összes munkarendelés** vagy **Aktív munkarendelések** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="79b7e-109">Select **Asset management** > **Common** > **Work orders** > **All work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="79b7e-110">Válassza ki a munkarendelést a listában, majd a Művelet panel > **Munkarendelés** lapján a **Projekt** csoportban válassz az **Előrejelzés** pontot.</span><span class="sxs-lookup"><span data-stu-id="79b7e-110">Select the work order in the list, and then, on the Action Pane > **Work order** tab > the **Project** group, select **Forecast**.</span></span> <span data-ttu-id="79b7e-111">A **Munkarendelés karbantartási előrejelzése** oldalon a munkarendelésen a kiválasztott karbantartási feladattípusból származó előrejelzési sorok jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="79b7e-111">The **Work order maintenance forecast** page shows forecast lines from the maintenance job type that is selected on the work order job.</span></span>


## <a name="add-an-hours-forecast-to-a-work-order"></a><span data-ttu-id="79b7e-112">Órák előrejelzésének hozzáadása egymunkarendeléshez</span><span class="sxs-lookup"><span data-stu-id="79b7e-112">Add an hours forecast to a work order</span></span>

1. <span data-ttu-id="79b7e-113">A **Munkarendelés karbantartási előrejelzése** lapon válassza ki azt a munkarendelési feladatot, amelyhez előrejelzést szeretne hozzáadni.</span><span class="sxs-lookup"><span data-stu-id="79b7e-113">On the **Work order maintenance forecast** page, select the work order job to add a forecast to.</span></span>

2. <span data-ttu-id="79b7e-114">Az **Órák** gyorslapon válassza a **Hozzáadás** lehetőséget egy új sor létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="79b7e-114">On the **Hours** FastTab, select **Add** to create a new line.</span></span>

3. <span data-ttu-id="79b7e-115">Válasszon egy kategóriát a **Kategória** mezőben.</span><span class="sxs-lookup"><span data-stu-id="79b7e-115">In the **Category** field, select a category.</span></span>

4. <span data-ttu-id="79b7e-116">Az előre jelzett órák számát írja be az **Órák** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="79b7e-116">In the **Hours** field, enter the number of forecasted hours.</span></span>

5. <span data-ttu-id="79b7e-117">A **Sor tulajdonsága** mezőben válassza ki a sorhoz használandó költségtípust.</span><span class="sxs-lookup"><span data-stu-id="79b7e-117">In the **Line property** field, select the type of charge that should be used on the line.</span></span>


## <a name="add-an-items-forecast-to-a-work-order"></a><span data-ttu-id="79b7e-118">A Cikkek előrejelzésének hozzáadása egymunkarendeléshez</span><span class="sxs-lookup"><span data-stu-id="79b7e-118">Add an items forecast to a work order</span></span>

<span data-ttu-id="79b7e-119">Háromféle módja van cikkek munkarendelés karbantartási előrejelzésekhez történő hozzáadására.</span><span class="sxs-lookup"><span data-stu-id="79b7e-119">There are three ways to add items to a work order maintenance forecast.</span></span> <span data-ttu-id="79b7e-120">Létrehozhat sorokat a cikkekhez (pótalkatrészek), amelyek nem szerepelnek az eszköz anyagjegyzékén (DBJ), kiválaszthat cserealkatrészeket a jóváhagyott cserealkatrész-listából, illetve kiválaszthat cikkeket az eszköz DBJ-ről.</span><span class="sxs-lookup"><span data-stu-id="79b7e-120">You can create lines for items (spare parts) that aren't included on the spare parts list or the asset bill of materials (BOM), you can select spare parts from the approved spare parts list, or you can select items from the asset BOM.</span></span>

- <span data-ttu-id="79b7e-121">A **Munkarendelés karbantartási előrejelzése** lapon válassza ki azt a munkarendelési feladatot, amelyhez előrejelzést szeretne hozzáadni.</span><span class="sxs-lookup"><span data-stu-id="79b7e-121">On the **Work order maintenance forecast** page, select the work order job to add a forecast to.</span></span>

- <span data-ttu-id="79b7e-122">A **Cikkek** gyorslapon a megfelelő módszer használatával vegyen fel cikkeket a karbantartási előrejelzésbe.</span><span class="sxs-lookup"><span data-stu-id="79b7e-122">On the **Items** FastTab, add items to the maintenance forecast by using the appropriate method.</span></span>

<span data-ttu-id="79b7e-123">Új sor létrehozásához egy olyan pótalkatrészhez, amely nem szerepel a pótalkatrészek vagy az eszköz DBJ listáján kövesse az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="79b7e-123">To create a line for a spare part that isn't on the spare parts list or the asset BOM, follow these steps:</span></span>

1. <span data-ttu-id="79b7e-124">Válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="79b7e-124">Select **Add**.</span></span>
2. <span data-ttu-id="79b7e-125">Válasszon egy cikket a **Cikkszám** mezőben.</span><span class="sxs-lookup"><span data-stu-id="79b7e-125">In the **Item number** field, select the item.</span></span>
3. <span data-ttu-id="79b7e-126">Az **Értékesítési Mennyiség** mezőben Írja be a mennyiséget.</span><span class="sxs-lookup"><span data-stu-id="79b7e-126">In the **Sales quantity** field, enter the quantity.</span></span>
4. <span data-ttu-id="79b7e-127">Az **Egység** mezőben válassza ki a mennyiséghez tartozó mértékegységet.</span><span class="sxs-lookup"><span data-stu-id="79b7e-127">In the **Unit** field, select the unit of measure for the quantity.</span></span>
5. <span data-ttu-id="79b7e-128">Az **Önköltségi ár** és a **Pénznem** mezőkbe írja be a megfelelő értékeket.</span><span class="sxs-lookup"><span data-stu-id="79b7e-128">In the **Cost price** and **Currency** fields, enter appropriate values.</span></span>
6. <span data-ttu-id="79b7e-129">A **Sortulajdonság** mezőben válasszon ki egy sortulajdonságot.</span><span class="sxs-lookup"><span data-stu-id="79b7e-129">In the **Line property** field, select a line property.</span></span>
7. <span data-ttu-id="79b7e-130">A cikkek soraiban megjelenített dimenziók módosításához, válassza a **Készlet** > **Dimenziók megjelenítése** elemre, válassza ki a dimenziókat, majd az a **Beállítás mentése** beállításnál az **Igen** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="79b7e-130">To change the list of dimensions that is shown on the item lines, select **Inventory** > **Display dimensions**, select the dimensions, and then set the **Save setup** option to **Yes**.</span></span>

<span data-ttu-id="79b7e-131">Ha a pótalkatrészeket szeretne a jóváhagyott pótalkatrész listából hozzáadni, hajtsa végre az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="79b7e-131">To add a spare part from an approved spare parts list, follow these steps:</span></span>

1. <span data-ttu-id="79b7e-132">Válassza a **Pótalkatrészek hozzáadása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="79b7e-132">Select **Add spare parts**.</span></span>
2. <span data-ttu-id="79b7e-133">Válassza ki a pótalkatrészt, és igény szerint szerkessze a szükséges adatokat.</span><span class="sxs-lookup"><span data-stu-id="79b7e-133">Select the spare part, and edit the related information as you require.</span></span>
3. <span data-ttu-id="79b7e-134">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="79b7e-134">Select **OK**.</span></span>

<span data-ttu-id="79b7e-135">Cikk az eszköz DBJ-ből történő hozzáadásához kövesse az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="79b7e-135">To add an item from the asset BOM, follow these steps:</span></span>

1. <span data-ttu-id="79b7e-136">Válassza a **DBJ-cikkek hozzáadása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="79b7e-136">Select **Add BOM items**.</span></span>
2. <span data-ttu-id="79b7e-137">Válassza ki a cikket, és igény szerint szerkessze a szükséges adatokat.</span><span class="sxs-lookup"><span data-stu-id="79b7e-137">Select the item, and edit the related information as you require.</span></span>
3. <span data-ttu-id="79b7e-138">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="79b7e-138">Select **OK**.</span></span>

<span data-ttu-id="79b7e-139">Ha szeretne áttekintést kapni arról, hogy hol használják a kiválasztott sorban található cikket az eszközökkel, alapértelmezett feladattípusokkal, pótalkatrészekkel és munkarendelésekkel kapcsolatban, válassza a **Cikket hol használják** elemet.</span><span class="sxs-lookup"><span data-stu-id="79b7e-139">To get an overview that shows where the item on the selected line is used in relation to assets, maintenance job type defaults, spare parts, and work orders in Asset Management, select **Item where used**.</span></span> <span data-ttu-id="79b7e-140">Az áttekintéssel kapcsolatos további tudnivalókat lásd a [Cikk használati helye](../controlling-and-reporting/item-where-used.md)részben.</span><span class="sxs-lookup"><span data-stu-id="79b7e-140">For more information about this overview, see [Item where used](../controlling-and-reporting/item-where-used.md).</span></span>


## <a name="add-an-expense-forecast-to-a-work-order"></a><span data-ttu-id="79b7e-141">Költségek előrejelzésének hozzáadása egy munkarendeléshez</span><span class="sxs-lookup"><span data-stu-id="79b7e-141">Add an expense forecast to a work order</span></span>

1. <span data-ttu-id="79b7e-142">A **Munkarendelés karbantartási előrejelzése** lapon válassza ki azt a munkarendelési feladatot, amelyhez előrejelzést szeretne hozzáadni.</span><span class="sxs-lookup"><span data-stu-id="79b7e-142">On the **Work order maintenance forecast** page, select the work order job to add a forecast to.</span></span>

2. <span data-ttu-id="79b7e-143">A **Költség** gyorslapon válassza a **Hozzáadás** lehetőséget egy új sor létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="79b7e-143">On the **Expense** FastTab, select **Add** to create a line.</span></span>

3. <span data-ttu-id="79b7e-144">Válasszon egy kategóriát a **Kategória** mezőben.</span><span class="sxs-lookup"><span data-stu-id="79b7e-144">In the **Category** field, select a category.</span></span>

4. <span data-ttu-id="79b7e-145">A **Mennyiség** mezőben Írja be a mennyiséget.</span><span class="sxs-lookup"><span data-stu-id="79b7e-145">In the **Quantity** field, enter the quantity.</span></span>

5. <span data-ttu-id="79b7e-146">A **Önköltségi ár**, **Értékesítési pénznem** és **Eladási ár** mezőkbe adja meg a megfelelő értékeket.</span><span class="sxs-lookup"><span data-stu-id="79b7e-146">In the **Cost price**, **Sales currency**, and **Sales price** fields, enter appropriate values.</span></span>

6. <span data-ttu-id="79b7e-147">A **Sor tulajdonsága** mezőben válassza ki a sorhoz használandó költségtípust.</span><span class="sxs-lookup"><span data-stu-id="79b7e-147">In the **Line property** field, select the type of charge that should be used on the line.</span></span>

>[!NOTE]
><span data-ttu-id="79b7e-148">A **Karbantartási előrejelzés összesítése** gyorslapon egy áttekintés látható az egyes gyorslapokon létrehozott sorok számáról a kiválasztott munkarendelési feladathoz és a munkarendeléshez.</span><span class="sxs-lookup"><span data-stu-id="79b7e-148">The **Maintenance forecast totals** FastTab shows an overview of the number of lines that have been created, for the selected work order job and for the work order, on each FastTab.</span></span> <span data-ttu-id="79b7e-149">Ezenkívül a munkarendelés feladathoz és a munkarendeléshez tartozó előre jelzett munkaórák összege is megjelenik.</span><span class="sxs-lookup"><span data-stu-id="79b7e-149">It also shows the total forecasted work hours for the work order job and the work order.</span></span>

<span data-ttu-id="79b7e-150">Az alábbi ábra a **Munkarendelés beszerzés előrejelzés** egy példáját mutatja be.</span><span class="sxs-lookup"><span data-stu-id="79b7e-150">The illustration below shows an example of the **Work order maintenance forecast** page.</span></span>

![1. ábra](media/06-work-orders.png)


## <a name="automatic-update-of-work-order-forecasts"></a><span data-ttu-id="79b7e-152">Munkarendelés-előrejelzések automatikus frissítése</span><span class="sxs-lookup"><span data-stu-id="79b7e-152">Automatic update of work order forecasts</span></span>

<span data-ttu-id="79b7e-153">Ha az óraköltség, a cikköltségek és más kiadások frissítve lettek a Microsoft Dynamics 365 for Finance and Operations moduljaiban a munkarendelés előrejelzések automatikusan frissíthetők az Eszközkezelésben, hogy tükrözzék ezeket a módosításokat.</span><span class="sxs-lookup"><span data-stu-id="79b7e-153">If hour costs, item costs, and expenses are updated in other modules in Microsoft Dynamics 365 for Finance and Operations, work order forecasts in Asset Management can automatically be updated to reflect those changes.</span></span> <span data-ttu-id="79b7e-154">Ez a képesség segít garantálni, hogy a legutóbbi önköltségi árak legyenek mindig használva a munkarendelés-előrejelzésekben.</span><span class="sxs-lookup"><span data-stu-id="79b7e-154">This capability helps guarantee that the latest cost prices are always used in your work order forecasts.</span></span> <span data-ttu-id="79b7e-155">Hasonló frissítéseket végezhet a [karbantartási feladattípus előrejelzésekhez](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md) is.</span><span class="sxs-lookup"><span data-stu-id="79b7e-155">You can also do similar updates for [maintenance job type forecasts](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md).</span></span>

1. <span data-ttu-id="79b7e-156">Válassza az **Eszközkezelés** > **Időszakos** > **Előrejelzés** > **Munkarendelés-előrejelzés frissítése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="79b7e-156">Select **Asset management** > **Periodic** > **Forecast** > **Update work order forecast**.</span></span>

2. <span data-ttu-id="79b7e-157">Ha szükséges , adja meg a munkarendelésekre vagy munkarendelés-feladatokra vonatkozó beállításokat a **Munkarendelés frissítése-előrejelzés** legördülő párbeszédpanelen a **Befoglalandó rekordok** lapon.</span><span class="sxs-lookup"><span data-stu-id="79b7e-157">In the **Update work order forecast** dialog, on the **Records to include** FastTab, you can add selections regarding specific work orders or work order jobs, as you require.</span></span> <span data-ttu-id="79b7e-158">Kattintson a **Szűrő** elemre a kapcsolódó kiválasztásokhoz.</span><span class="sxs-lookup"><span data-stu-id="79b7e-158">Click **Filter** to make the relevant selections.</span></span>

3. <span data-ttu-id="79b7e-159">A **Futtatás a háttérben** gyorslapon szükség szerint kötegelt feladatként is beállíthatja az automatikus frissítést.</span><span class="sxs-lookup"><span data-stu-id="79b7e-159">On the **Run in the background** FastTab, you can set up the automatic update as a batch job, as you require.</span></span>

4. <span data-ttu-id="79b7e-160">Az előrejelzés frissítése az **OK** gombot választva indítható el.</span><span class="sxs-lookup"><span data-stu-id="79b7e-160">Select **OK** to start the forecast update.</span></span>


<span data-ttu-id="79b7e-161">Az alábbi ábra a **Munkarendelés előrejelzés frissítése** párbeszédpanel egy példáját mutatja be.</span><span class="sxs-lookup"><span data-stu-id="79b7e-161">The illustration below shows an example of the **Update work order forecast** dialog.</span></span>

![2. ábra](media/07-work-orders.png)
