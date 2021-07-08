---
title: A mennyiség nem csökkenthető értékesítési rendelés visszavonásakor
description: A mennyiség nem csökkenthető értékesítési rendelés visszavonásakor.
author: hja-ms
ms.date: 5/17/2021
ms.topic: troubleshooting
ms.search.form: SalesTable_SalesCancelOrder, SalesTableListPage_SalesCancelOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: hja
ms.search.validFrom: 2021-05-17
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 1a2cc9c9fd3d085508fc652bc9ee0a352d869dee
ms.sourcegitcommit: a02d3d64c899f8554b74342d5a1856d824bf1abe
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/11/2021
ms.locfileid: "6230836"
---
# <a name="the-quantity-cant-be-reduced-when-a-sales-order-is-canceled"></a><span data-ttu-id="ef774-103">A mennyiség nem csökkenthető értékesítési rendelés visszavonásakor</span><span class="sxs-lookup"><span data-stu-id="ef774-103">The quantity can't be reduced when a sales order is canceled</span></span>

<span data-ttu-id="ef774-104">Hibakód: SYS138831</span><span class="sxs-lookup"><span data-stu-id="ef774-104">Error code: SYS138831</span></span>

## <a name="symptoms"></a><span data-ttu-id="ef774-105">Tünetek</span><span class="sxs-lookup"><span data-stu-id="ef774-105">Symptoms</span></span>

<span data-ttu-id="ef774-106">A rendszer a következő hibaüzenetet jeleníti meg:</span><span class="sxs-lookup"><span data-stu-id="ef774-106">The system shows the following error message:</span></span>

> <span data-ttu-id="ef774-107">A mennyiség nem csökkenthető.</span><span class="sxs-lookup"><span data-stu-id="ef774-107">The quantity cannot be reduced.</span></span> <span data-ttu-id="ef774-108">A rendelésben szereplő készlettranzakciók száma túl alacsony, mert a mennyiségre vagy annak egy részére kimeneti rendelés vagy termelési rendelés hivatkozik, vagy más tranzakciókkal van megjelölve.</span><span class="sxs-lookup"><span data-stu-id="ef774-108">The number of inventory transactions on order is too low because the quantity or part of it is referenced by an output order or a production order or is marked against other transactions.</span></span>

## <a name="cause"></a><span data-ttu-id="ef774-109">Ok</span><span class="sxs-lookup"><span data-stu-id="ef774-109">Cause</span></span>

<span data-ttu-id="ef774-110">Ha van munka egy értékesítési rendeléshez van társítva, akkor az értékesítési rendelés nem törölhető, amíg a munka nincs érvénytelenítve és visszavonva.</span><span class="sxs-lookup"><span data-stu-id="ef774-110">If work is associated with a sales order, you can't cancel the sales order until the work is canceled and reversed.</span></span> <span data-ttu-id="ef774-111">Ez a követelmény akkor is érvényes, ha az értékesítési rendeléshez társított munka le van zárva.</span><span class="sxs-lookup"><span data-stu-id="ef774-111">This requirement applies even if the work that is associated with the sales order is closed.</span></span>

## <a name="resolution"></a><span data-ttu-id="ef774-112">Megoldás</span><span class="sxs-lookup"><span data-stu-id="ef774-112">Resolution</span></span>

<span data-ttu-id="ef774-113">A probléma javításához végezze el a következő feladatok egyikét:</span><span class="sxs-lookup"><span data-stu-id="ef774-113">To fix this issue, complete the following tasks:</span></span>

1. <span data-ttu-id="ef774-114">Nyitott munka visszavonása.</span><span class="sxs-lookup"><span data-stu-id="ef774-114">Cancel open work.</span></span>
1. <span data-ttu-id="ef774-115">Törölje a rakományt.</span><span class="sxs-lookup"><span data-stu-id="ef774-115">Delete the load.</span></span>
1. <span data-ttu-id="ef774-116">A kitárolt mennyiség csökkentése.</span><span class="sxs-lookup"><span data-stu-id="ef774-116">Reduce the picked quantity.</span></span>

### <a name="cancel-open-work"></a><span data-ttu-id="ef774-117">Nyitott munka visszavonása</span><span class="sxs-lookup"><span data-stu-id="ef774-117">Cancel open work</span></span>

<span data-ttu-id="ef774-118">Nyitott munka megszakításához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="ef774-118">To cancel open work, follow these steps.</span></span>

1. <span data-ttu-id="ef774-119">Menjen a **Raktárkezelés \> Időszakos feladatok \> Tisztítás \> Munka megszakítása** menühöz.</span><span class="sxs-lookup"><span data-stu-id="ef774-119">Go to **Warehouse management \> Periodic tasks \> Clean up \> Cancel work**.</span></span>
1. <span data-ttu-id="ef774-120">A **Munkaazonosító** mezőben adja meg annak a munkának az azonosítóját, amelyről törölni szeretne, és amelynek jelenleg **Munkaállapot** értéke *Nyitott*, *Folyamatban*, *Megszakítva*, *Kombinálva* vagy *Lezárva*.</span><span class="sxs-lookup"><span data-stu-id="ef774-120">In the **Work ID** field, specify the ID of the work that you want to cancel, and that currently has a **Work status** value of *Open*, *In progress*, *Canceled*, *Combined*, or *Closed*.</span></span>
1. <span data-ttu-id="ef774-121">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ef774-121">Select **OK**.</span></span>
1. <span data-ttu-id="ef774-122">Válassza az **Igen** lehetőséget a munka megszakításához.</span><span class="sxs-lookup"><span data-stu-id="ef774-122">Select **Yes** to confirm that you want to cancel the work.</span></span>

### <a name="delete-the-load"></a><span data-ttu-id="ef774-123">Törölje a terhelést</span><span class="sxs-lookup"><span data-stu-id="ef774-123">Delete the load</span></span>

<span data-ttu-id="ef774-124">A terhelés törléséhez kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="ef774-124">To delete a load, follow these steps.</span></span>

1. <span data-ttu-id="ef774-125">Ugorjon az **Értékesítés és marketing \> Értékesítési rendelések \> Minden értékesítési rendelés** pontra.</span><span class="sxs-lookup"><span data-stu-id="ef774-125">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="ef774-126">Nyissa meg a megfelelő értékesítési rendelést.</span><span class="sxs-lookup"><span data-stu-id="ef774-126">Open the relevant sales order.</span></span>
1. <span data-ttu-id="ef774-127">Az **Értékesítési rendelés sorai** gyorslapon válassza ki a **Raktár \> Munka részletes adatai** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ef774-127">On the **Sales order lines** FastTab, select **Warehouse \> Work details**.</span></span>
1. <span data-ttu-id="ef774-128">A **Munka** lapon a Művelet ablaktábla **Munka** lapjának **Munka** csoportjában válassza a **Munka visszavonása** elemet.</span><span class="sxs-lookup"><span data-stu-id="ef774-128">On the **Work** page, on the Action Pane, on the **Work** tab, in the **Work** group, select **Cancel work**.</span></span>
1. <span data-ttu-id="ef774-129">Győződjön meg arról, hogy a **Munka állapota** mezője *Érvénytelenve* beállítású.</span><span class="sxs-lookup"><span data-stu-id="ef774-129">Confirm that the **Work status** field is set to *Canceled*.</span></span>
1. <span data-ttu-id="ef774-130">Zárja be a **Munka** oldalt.</span><span class="sxs-lookup"><span data-stu-id="ef774-130">Close the **Work** page.</span></span>
1. <span data-ttu-id="ef774-131">Az értékesítési rendelés részleteit tartalmazó lap **Értékesítésirendelés-sorok** gyorslapján válassza a **Raktár \> Rakomány részletei** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ef774-131">On the sales order details page, on the **Sales order lines** FastTab, select **Warehouse \> Load details**.</span></span>
1. <span data-ttu-id="ef774-132">A Műveletpanelen válassza ezután a **Törlés** elemet.</span><span class="sxs-lookup"><span data-stu-id="ef774-132">On the Action Pane, select **Delete**.</span></span>
1. <span data-ttu-id="ef774-133">Válassza az **Igen** lehetőséget a rakomány törlésének megerősítéséhez.</span><span class="sxs-lookup"><span data-stu-id="ef774-133">Select **Yes** to confirm that you want to delete the load.</span></span>
1. <span data-ttu-id="ef774-134">Zárja be a **Rakomány** oldalt.</span><span class="sxs-lookup"><span data-stu-id="ef774-134">Close the **Load** page.</span></span>

### <a name="reduce-the-picked-quantity"></a><span data-ttu-id="ef774-135">A kitárolt mennyiség csökkentése</span><span class="sxs-lookup"><span data-stu-id="ef774-135">Reduce the picked quantity</span></span>

<span data-ttu-id="ef774-136">A ki nem választott mennyiség csökkentéséhez kövesse ezeket a lépéseket a munka visszavonása után.</span><span class="sxs-lookup"><span data-stu-id="ef774-136">After all work has been canceled, follow these steps to reduce the picked quantity.</span></span>

1. <span data-ttu-id="ef774-137">Ugorjon az **Értékesítés és marketing \> Értékesítési rendelések \> Minden értékesítési rendelés** pontra.</span><span class="sxs-lookup"><span data-stu-id="ef774-137">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="ef774-138">Nyissa meg a megfelelő értékesítési rendelést.</span><span class="sxs-lookup"><span data-stu-id="ef774-138">Open the relevant sales order.</span></span>
1. <span data-ttu-id="ef774-139">Az **Értékesítésirendelés-sorok** gyorslapon válassza az eszköztáron a **Sor frissítése \> Kitárolás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ef774-139">On the **Sales order lines** FastTab, select **Update line \> Pick** from the toolbar.</span></span>
1. <span data-ttu-id="ef774-140">Válassza ki a **Kitárolás** oldalon a **Tranzakciók** szakaszban a **Kiadás állapota** mezőben beállítása *Kitárolva*.</span><span class="sxs-lookup"><span data-stu-id="ef774-140">On the **Pick** page, in the **Transactions** section, select the line where the **Issue status** field is set to *Picked*.</span></span>
1. <span data-ttu-id="ef774-141">A **Tranzakciók** szakaszban válassza a **Kitárolási sor hozzáadása** lehetőséget az eszköztárról.</span><span class="sxs-lookup"><span data-stu-id="ef774-141">In the **Transactions** section, select **Add picking line** from the toolbar.</span></span>
1. <span data-ttu-id="ef774-142">A **Kitárolási sorok** szakaszban válassza az **Összes kitárolás megerősítése** lehetőséget az eszköztárról.</span><span class="sxs-lookup"><span data-stu-id="ef774-142">In the **Picking lines** section, select **Confirm pick all** from the toolbar.</span></span>
1. <span data-ttu-id="ef774-143">Zárja be a **Kitárolás** oldalt.</span><span class="sxs-lookup"><span data-stu-id="ef774-143">Close the **Pick** page.</span></span>
1. <span data-ttu-id="ef774-144">Az értékesítési rendelés részletei oldal műveleti ablaktábláján, az **Értékesítési rendelés** lapon, a **Karbantartás** csoportban válassza ki az **Érvénytelenítés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ef774-144">On the sales order details page, on the Action Pane, on the **Sales order** tab, in the **Maintain** group, select **Cancel**.</span></span>
1. <span data-ttu-id="ef774-145">Válassza az **Igen** lehetőséget az értékesítési rendelés érvénytelenítéséhez.</span><span class="sxs-lookup"><span data-stu-id="ef774-145">Select **Yes** to confirm that you want to cancel the sales order.</span></span>