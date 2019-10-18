---
title: Karbantartási előrejelzések
description: Ez a cikk a karbantartási előrejelzések az Eszközkezelésben való használatát ismerteti.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 383c910b40199f2da863144c6dc85a579d0091e9
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/24/2019
ms.locfileid: "2024499"
---
# <a name="maintenance-forecasts"></a><span data-ttu-id="1977e-103">Karbantartási előrejelzések</span><span class="sxs-lookup"><span data-stu-id="1977e-103">Maintenance forecasts</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


<span data-ttu-id="1977e-104">A munkarendelések létrehozásakor munkarendelési feladatokat hoz létre kapcsolódó eszközökkel és karbantartási feladattípusokkal.</span><span class="sxs-lookup"><span data-stu-id="1977e-104">When you create a work order, you create work order jobs with related assets and maintenance job types.</span></span> <span data-ttu-id="1977e-105">Karbantartási előrejelzéseket tartalmazó karbantartási feladattípus kiválasztásakor a program automatikusan átmásolja a munkarendelésbe az előrejelzéseket.</span><span class="sxs-lookup"><span data-stu-id="1977e-105">When you select a maintenance job type containing maintenance forecasts, the forecasts are automatically copied to the work order.</span></span>

<span data-ttu-id="1977e-106">Előfordulhat, hogy egy munkarendelésben lehetősége van hozzáadni vagy törölni előrejelzési sorokat.</span><span class="sxs-lookup"><span data-stu-id="1977e-106">You may be able to add or delete forecast lines on a work order.</span></span> <span data-ttu-id="1977e-107">A munkarendelés életciklus-állapotának beállítása, a kapcsolódó projekttípus és a projekt típusára vonatkozó szakaszszabályok határozzák meg, hogy az előrejelzés-sorok hozzáadhatók-e a naplóhoz, vagy szerkeszthetők-e.</span><span class="sxs-lookup"><span data-stu-id="1977e-107">The setup of a work order lifecycle state, the related project type, and the stage rules related to the project type determines if you are able to add or edit forecast lines.</span></span> 

1. <span data-ttu-id="1977e-108">Kattintson az **Eszközkezelés** > **Közös** > **Munkarendelések** > **Összes munkarendelés** vagy **Aktív munkarendelések** elemre.</span><span class="sxs-lookup"><span data-stu-id="1977e-108">Click **Asset management** > **Common** > **Work orders** > **All work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="1977e-109">Válassza ki a munkarendelést a listában, majd kattintson az **Előrejelzés** elemre.</span><span class="sxs-lookup"><span data-stu-id="1977e-109">Select the work order in the list, and click **Forecast**.</span></span> <span data-ttu-id="1977e-110">A **Munkarendelés karbantartási előrejelzésébe**a munkarendelésen a kiválasztott karbantartási feladattípusból származó előrejelzési sorok jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="1977e-110">In **Work order maintenance forecast**, forecast lines from the maintenance job type selected on the work order job are displayed.</span></span>


## <a name="add-hours-forecast-to-a-work-order"></a><span data-ttu-id="1977e-111">Órák előrejelzésének hozzáadása egymunkarendeléshez</span><span class="sxs-lookup"><span data-stu-id="1977e-111">Add hours forecast to a work order</span></span>

1. <span data-ttu-id="1977e-112">Válassza ki azt a munkarendelés-feladatot, amelyhez előrejelzést szeretne hozzáadni.</span><span class="sxs-lookup"><span data-stu-id="1977e-112">Select the work order job to which you want to add a forecast.</span></span>

2. <span data-ttu-id="1977e-113">Az **Órák** gyorslapon kattintson a **Hozzáadás** lehetőségre egy új sor létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="1977e-113">On the **Hours** FastTab, click **Add** to create a new line.</span></span>

3. <span data-ttu-id="1977e-114">Válasszon kategóriát a **Kategória** mezőben.</span><span class="sxs-lookup"><span data-stu-id="1977e-114">Select a category in the **Category** field.</span></span>

4. <span data-ttu-id="1977e-115">Az előre jelzett órák számának beszúrása az **Órák** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="1977e-115">Insert number of forecasted hours in the **Hours** field.</span></span>

5. <span data-ttu-id="1977e-116">A **Sor tulajdonsága** mezőben válassza ki a sorban használt költségtípust.</span><span class="sxs-lookup"><span data-stu-id="1977e-116">In the **Line property** field, select the charge type to be used on the line.</span></span>


## <a name="add-items-forecast-to-a-work-order"></a><span data-ttu-id="1977e-117">Cikkek előrejelzésének hozzáadása egymunkarendeléshez</span><span class="sxs-lookup"><span data-stu-id="1977e-117">Add items forecast to a work order</span></span>

<span data-ttu-id="1977e-118">A cikkek munkarendelés karbantartási előrejelzéshez történő hozzáadásának három módja van: Létrehozhat sorokat a cikkekhez (pótalkatrészek), amelyek nem szerepelnek a cserealkatrészek listáján az eszköz DBJ-n, kiválaszthat cserealkatrészeket a jóváhagyott cserealkatrész-listából, illetve kiválaszthat cikkeket az eszköz DBJ-ről.</span><span class="sxs-lookup"><span data-stu-id="1977e-118">There are three ways to add items to a work order maintenance forecast: You can create lines for items (spare parts) that are not included in the spare parts list or asset BOM, you can select spare parts from the approved spare parts list, and you can select items from the asset BOM.</span></span>

1. <span data-ttu-id="1977e-119">Válassza ki azt a munkarendelés-feladatot, amelyhez előrejelzést szeretne hozzáadni.</span><span class="sxs-lookup"><span data-stu-id="1977e-119">Select the work order job to which you want to add a forecast.</span></span>

2. <span data-ttu-id="1977e-120">Válassza a **Cikkek** gyorslapot.</span><span class="sxs-lookup"><span data-stu-id="1977e-120">Select the **Items** FastTab.</span></span>

3. <span data-ttu-id="1977e-121">A **Hozzáadás** gombra kattintva hozzon létre egy új sort egy olyan pótalkatrészhez, amely nem szerepel a pótalkatrészek vagy az eszköz DBJ listáján.</span><span class="sxs-lookup"><span data-stu-id="1977e-121">Click **Add** to create a new line for a spare part that is not on the spare parts list or the asset BOM list.</span></span>

4. <span data-ttu-id="1977e-122">Válassza ki a cikket a **Cikkszám** mezőben.</span><span class="sxs-lookup"><span data-stu-id="1977e-122">Select the item in the **Item number** field.</span></span>

5. <span data-ttu-id="1977e-123">Írja be a mennyiséget az **Értékesítési mennyiség** mezőbe, majd válassza ki a mennyiségi egységet az **Egység** mezőben.</span><span class="sxs-lookup"><span data-stu-id="1977e-123">Insert quantity in the **Sales quantity** field, and select a quantity unit in the **Unit** field.</span></span>

6. <span data-ttu-id="1977e-124">Írja be az önköltségi árat és a pénznemet a megfelelő mezőkbe, majd válassza ki a **Sortulajdonság** értékét.</span><span class="sxs-lookup"><span data-stu-id="1977e-124">Insert cost price and currency in the relevant fields, and select a **Line property**.</span></span>

7. <span data-ttu-id="1977e-125">Ha módosítani szeretné a cikkek soraiban megjelenített dimenziókat, kattintson a **Készlet** > **Dimenziók megjelenítése**elemre, válassza ki a dimenziókat, és válassza az „igen” beállítást a **Beállítás mentése** gombra kattintva.</span><span class="sxs-lookup"><span data-stu-id="1977e-125">If you want to change the list of dimensions displayed on the item lines, click **Inventory** > **Display dimensions**, select the dimensions, and select "Yes" on the **Save setup** toggle button.</span></span>

8. <span data-ttu-id="1977e-126">Ha a karbantartási előrejelzéshez jóváhagyott pótalkatrészt szeretne hozzáadni, kattintson a **Pótalkatrészek hozzáadása** elemre, válassza ki a pótalkatrészt, szerkessze a szükséges adatokat, ha szükséges, és kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="1977e-126">If you want to add an approved spare part to the maintenance forecast, click **Add spare parts**, select the spare part, edit related information if required, and click **OK**.</span></span>

9. <span data-ttu-id="1977e-127">Ha szeretné hozzáadni a eszköz DBJ tételeit az előrejelzéshez, kattintson a **DBJ-cikkek hozzáadása** hivatkozásra, válassza ki a cikket, szerkessze akapcsolódó információt, ha szükséges, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="1977e-127">If you want to add asset BOM items to the forecast, click **Add BOM items**, select the item, edit related information if required, and click **OK**.</span></span>

10. <span data-ttu-id="1977e-128">Ha szeretne áttekintést kapni arról, hogy az Eszközkezelésben hol használják a kiválasztott sorban található cikk az eszközökkel, alapértelmezett karbantartási feladattípusokkal, pótalkatrészekkel és munkarendelésekkel kapcsolatban, válassza a **Cikket hol használják** elemet.</span><span class="sxs-lookup"><span data-stu-id="1977e-128">Click **Item where used** if you want to get an overview of where the item on the selected line is used in Asset Management in relation to assets, maintenance job type defaults, spare parts, and work orders.</span></span> 



## <a name="add-expense-forecast-to-a-work-order"></a><span data-ttu-id="1977e-129">Költségek előrejelzésének hozzáadása egymunkarendeléshez</span><span class="sxs-lookup"><span data-stu-id="1977e-129">Add expense forecast to a work order</span></span>

1. <span data-ttu-id="1977e-130">Ez a témakör azt mutatja be, hogyan lehet költség-előrejelzést hozzáadni egy munkarendeléshez.</span><span class="sxs-lookup"><span data-stu-id="1977e-130">This topic explains how to add an expense forecast to a work order.</span></span> <span data-ttu-id="1977e-131">A képernyő bal oldali részén válassza ki azt a munkarendelés-feladatot, amelyhez előrejelzést szeretne hozzáadni.</span><span class="sxs-lookup"><span data-stu-id="1977e-131">In the left-hand side of the form, select the work order job to which you want to add a forecast.</span></span>

2. <span data-ttu-id="1977e-132">Válassza a **Költség** gyorslapot.</span><span class="sxs-lookup"><span data-stu-id="1977e-132">Select the **Expense** FastTab.</span></span>

3. <span data-ttu-id="1977e-133">Kattintson a **Hozzáadás** elemre új sor létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="1977e-133">Click **Add** to create a new line.</span></span>

4. <span data-ttu-id="1977e-134">Válasszon kategóriát a **Kategória** mezőben.</span><span class="sxs-lookup"><span data-stu-id="1977e-134">Select a category in the **Category** field.</span></span>

5. <span data-ttu-id="1977e-135">A **Mennyiség** mezőben adja meg a mennyiséget.</span><span class="sxs-lookup"><span data-stu-id="1977e-135">Insert quantity in the **Quantity** field.</span></span>

6. <span data-ttu-id="1977e-136">Szúrja be az önköltségi ár, az értékesítési pénznem és az eladási ár értékeit a megfelelő mezőkbe.</span><span class="sxs-lookup"><span data-stu-id="1977e-136">Insert cost price, sales currency, and sales price in the relevant fields.</span></span>

7. <span data-ttu-id="1977e-137">A **Sor tulajdonsága** mezőben válassza ki a sorban használt költségtípust.</span><span class="sxs-lookup"><span data-stu-id="1977e-137">In the **Line property** field, select the charge type to be used on the line.</span></span>

>[!NOTE]
><span data-ttu-id="1977e-138">A **Karbantartási előrejelzés összesítése** gyorslapon egy áttekintés látható az egyes lapokon létrehozott sorok számáról a kiválasztott munkarendelési feladathoz és a munkarendeléshez.</span><span class="sxs-lookup"><span data-stu-id="1977e-138">On the **Maintenance forecast totals** FastTab, you can see an overview of the number of lines created on each tab, for the selected work order job and for the work order.</span></span> <span data-ttu-id="1977e-139">Ezenkívül a munkarendelés feladathoz és a munkarendeléshez tartozó előre jelzett munkaórák összege is látható.</span><span class="sxs-lookup"><span data-stu-id="1977e-139">Also, you can see a sum of forecasted work hours for the work order job and for the work order.</span></span>

![1. ábra](media/06-work-orders.png)


## <a name="automatic-update-of-work-order-forecasts"></a><span data-ttu-id="1977e-141">Munkarendelés-előrejelzések automatikus frissítése</span><span class="sxs-lookup"><span data-stu-id="1977e-141">Automatic update of work order forecasts</span></span>

<span data-ttu-id="1977e-142">Az Eszközkezelésben automatikusan frissítheti a munkarendelések előrejelzéseinek módosításait az óraköltség, a cikköltségekhez és más kiadásokhoz, amelyek frissítve lettek más modulokban.</span><span class="sxs-lookup"><span data-stu-id="1977e-142">In Asset Management, you can automatically update any changes in work order forecasts regarding hour costs, item costs, and expenses, which have been updated in other modules.</span></span> <span data-ttu-id="1977e-143">Erre azért van szükség, hogy a legutóbbi önköltségi árak legyenek mindig használva a munkarendelés-előrejelzésekben.</span><span class="sxs-lookup"><span data-stu-id="1977e-143">This is done to ensure that the latest cost prices are always used in your work order forecasts.</span></span> <span data-ttu-id="1977e-144">Hasonló frissítések lehetségesek a [karbantartási feladattípus előrejelzésekhez](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md) is.</span><span class="sxs-lookup"><span data-stu-id="1977e-144">It is also possible to make similar updates for [maintenance job type forecasts](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md).</span></span>

1. <span data-ttu-id="1977e-145">Kattintson az **Eszközkezelés** > **Időszakos** > **Előrejelzés** > **Munkarendelés-előrejelzés frissítése** hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="1977e-145">Click **Asset management** > **Periodic** > **Forecast** > **Update work order forecast**.</span></span>

2. <span data-ttu-id="1977e-146">Ha szükséges , adja meg a munkarendelésekre vagy munkarendelés-feladatokra vonatkozó beállításokat a **Munkarendelés frissítése-előrejelzés** legördülő párbeszédpanelen.</span><span class="sxs-lookup"><span data-stu-id="1977e-146">In the **Update work order forecast** drop-down dialog, you can add selections regarding specific work orders or work order jobs, if required.</span></span> <span data-ttu-id="1977e-147">Kattintson a **Szűrőt** elemre ezen kiválasztásokhoz.</span><span class="sxs-lookup"><span data-stu-id="1977e-147">Click **Filter** to make those selections.</span></span>

3. <span data-ttu-id="1977e-148">Ha szükséges, a **Futtatás a háttérben** gyorslapon szükség szerint kötegelt feladatként is beállíthatja az automatikus frissítést.</span><span class="sxs-lookup"><span data-stu-id="1977e-148">If required, you can set up the automatic update as a batch job on the **Run in the background** FastTab.</span></span>

4. <span data-ttu-id="1977e-149">Az előrejelzés frissítése az **OK** gombra kattintva indítható el.</span><span class="sxs-lookup"><span data-stu-id="1977e-149">Click **OK** to start the forecast update.</span></span>


![2. ábra](media/07-work-orders.png)

