---
title: Munkarendelés-gyűjtők
description: Ez a témakör bemutatja a munkarendelés-gyűjtők használatát az Eszközkezelés modulban.
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
ms.openlocfilehash: 069fa02073808fd7bbaac9bc1603e49ce4d450eb
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875694"
---
# <a name="work-order-pools"></a><span data-ttu-id="2884f-103">Munkarendelés-gyűjtők</span><span class="sxs-lookup"><span data-stu-id="2884f-103">Work order pools</span></span>


[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


<span data-ttu-id="2884f-104">A munkarendelés-gyűjtőkkel csoportosíthatja a valamiben egyeztő munkarendeléseket.</span><span class="sxs-lookup"><span data-stu-id="2884f-104">You can use work order pools to group work orders that have something in common.</span></span> <span data-ttu-id="2884f-105">Létrehozhat például munkarendelés-gyűjtőket a következőhöz:</span><span class="sxs-lookup"><span data-stu-id="2884f-105">For example, you can create work order pools for</span></span>

- <span data-ttu-id="2884f-106">munkaszemélyzet, például A karbantartási személyzet, B karbantartási személyzet</span><span class="sxs-lookup"><span data-stu-id="2884f-106">work crews, for example, Maintenance Crew A, Maintenance Crew B</span></span>  

- <span data-ttu-id="2884f-107">szakmához kapcsolódó szakértelmek, például villanyszerelők vagy vízvezeték-szerelők</span><span class="sxs-lookup"><span data-stu-id="2884f-107">professional skills, for example, electricians or plumbers</span></span>  

- <span data-ttu-id="2884f-108">tényleges helyek</span><span class="sxs-lookup"><span data-stu-id="2884f-108">physical locations</span></span>  

- <span data-ttu-id="2884f-109">időbeosztások, például hetek vagy más időszakok</span><span class="sxs-lookup"><span data-stu-id="2884f-109">time schedules, for example, weeks or other periods</span></span>  


<span data-ttu-id="2884f-110">Szükség esetén egy munkarendelés számos munkarendelés-gyűjtőbe elhelyezhető.</span><span class="sxs-lookup"><span data-stu-id="2884f-110">If required, one work order can be placed in many work order pools.</span></span>


## <a name="create-work-order-pool"></a><span data-ttu-id="2884f-111">Munkarendelés-gyűjtő létrehozása</span><span class="sxs-lookup"><span data-stu-id="2884f-111">Create work order pool</span></span>

<span data-ttu-id="2884f-112">Az **Összes munkarendelés-gyűjtő** vagy **Aktív munkarendelés-gyűjtők** pontokban áttekintést kaphat saját munkarendelés-gyűjtőiről, és új gyűjtőket hozhat létre.</span><span class="sxs-lookup"><span data-stu-id="2884f-112">In **All work order pools** or **Active work order pools**, you can get an overview of your work order pools and create new pools.</span></span>

1. <span data-ttu-id="2884f-113">Kattintson az **Eszközkezelés** > **Általános** > **Munkarendelés-gyűjtők** > **Összes munkarendelés-gyűjtő** vagy **Aktív munkarendelés-gyűjtők** elemre.</span><span class="sxs-lookup"><span data-stu-id="2884f-113">Click **Asset management** > **Common** > **Work order pools** > **All work order pools** or **Active work order pools**.</span></span>

2. <span data-ttu-id="2884f-114">Kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="2884f-114">Click **New**.</span></span>

3. <span data-ttu-id="2884f-115">Szúrjon be egy munkarendelés-gyűjtőhöz tartozó azonosítót a **Gyűjtő** mezőbe és írjon be egy nevet a **Név** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="2884f-115">Insert a work order pool ID in the **Pool** field and a name in the **Name** field.</span></span>

4. <span data-ttu-id="2884f-116">Válassza az „Igen” beállítást az **Aktív** választógombon, amellyel jelezheti, hogy a munkarendelés-gyűjtő aktív.</span><span class="sxs-lookup"><span data-stu-id="2884f-116">Select "Yes" on the **Active** toggle button to indicate that the work order pool is active.</span></span>

5. <span data-ttu-id="2884f-117">Válassza az „Igen” beállítást a **Munkarendelés kapcsolatainak törlése** választógombon, ha szeretne automatikusan eltávolítani munkarendeléseket a munkarendelés-gyűjtőből.</span><span class="sxs-lookup"><span data-stu-id="2884f-117">Select "Yes" on the **Delete work order relations** toggle button if you want work orders to be automatically removed from the work order pool.</span></span>

6. <span data-ttu-id="2884f-118">Az **Életciklus-állapot törlése** mezőben válassza a munkarendelés életciklus-állapotát.</span><span class="sxs-lookup"><span data-stu-id="2884f-118">In the **Delete lifecycle state** field, select the work order lifecycle state.</span></span> <span data-ttu-id="2884f-119">Például a munkarendelés befejezéséhez tartozó munkarendelési életciklus-állapotot beállíthatja, hogy automatikusan törölje a kapcsolatokat a munkarendelés-gyűjtőkből.</span><span class="sxs-lookup"><span data-stu-id="2884f-119">For example, the work order lifecycle state for completing a work order could be set to automatically delete relations to work order pools.</span></span>

7. <span data-ttu-id="2884f-120">A munkarendelés-gyűjtőhöz azonnal hozzáadhat munkarendeléseket.</span><span class="sxs-lookup"><span data-stu-id="2884f-120">You can start adding work orders to your work order pool right away.</span></span> <span data-ttu-id="2884f-121">A **Munkarendelések** gyorslapon kattintson a **Sor hozzáadása** parancsra.</span><span class="sxs-lookup"><span data-stu-id="2884f-121">On the **Work orders** FastTab, click **Add line**.</span></span>

8. <span data-ttu-id="2884f-122">A **Munkarendelés** mezőben válasszon ki egy munkarendelést.</span><span class="sxs-lookup"><span data-stu-id="2884f-122">Select a work order in the **Work order** field.</span></span> <span data-ttu-id="2884f-123">A kapcsolódó mezők frissítése automatikusan történik.</span><span class="sxs-lookup"><span data-stu-id="2884f-123">The related fields are automatically updated.</span></span>

9. <span data-ttu-id="2884f-124">Ha több munkarendelést szeretne hozzáadni, ismételje meg a 7-8. lépést.</span><span class="sxs-lookup"><span data-stu-id="2884f-124">Repeat steps 7-8 if you want to add more work orders.</span></span>

10. <span data-ttu-id="2884f-125">A **Rendezési sorrend** mezőben jelezheti, hogy a munkarendeléseket meghatározott sorrendben kell-e végrehajtani.</span><span class="sxs-lookup"><span data-stu-id="2884f-125">In the **Sort order** field, you can indicate if the work orders should be carried out in a certain order.</span></span> <span data-ttu-id="2884f-126">A kiválasztott munkarendelések megadott sorrendjét az 1, 2, 3 stb. számok megadásával határozhatja meg.</span><span class="sxs-lookup"><span data-stu-id="2884f-126">Insert numbers 1, 2, 3, and so on to indicate a specific sequence for the selected work orders.</span></span>

11. <span data-ttu-id="2884f-127">**A munkarendelések** gombra kattintva megtekintheti a munkarendelés-gyűjtőben szereplő munkarendelések listáját.</span><span class="sxs-lookup"><span data-stu-id="2884f-127">Click the **Work orders** button to see a list of all the work orders included in the work order pool.</span></span>

12. <span data-ttu-id="2884f-128">Kattintson a **Kapacitásterhelés** gombra a **Kapacitásterhelés** pont megnyitásához a karbantartási ütemezéshez, a nem ütemezett munkarendelésekhez és az ütemezett munkarendelésekhez kapcsolódó kapacitásterhelés kiszámításához és megtekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="2884f-128">Click the **Capacity load** button to open **Capacity load** to calculate and view capacity load for maintenance schedule, not-scheduled work orders, and scheduled work orders.</span></span>

13. <span data-ttu-id="2884f-129">A **Cikkelőrejelzés** gombra kattintva megnyílik a **Cikkelőrejelzés**, ahol cikkekkel (pótalkatrészekkel és egyéb szükséges cikkekkel) kapcsolatos előrejelzéseket számíthat ki és tekinthet meg a karbantartási ütemezéshez, nem ütemezett munkarendelésekhez és ütemezett munkarendelésekhez kapcsolódóan.</span><span class="sxs-lookup"><span data-stu-id="2884f-129">Click the **Item forecast** button to open **Item forecast** to calculate and view forecasts for items (spare parts and other required items) related to maintenance schedule, not-scheduled work orders, and scheduled work orders.</span></span>

14. <span data-ttu-id="2884f-130">Kattintson a **Munkarendelés beszerzési igénylése** gombbal a **Munkarendelés beszerzési igénylése** lista megnyitásához, ahol a munkarendelésgyűjtőben szereplő munkarendelésekhez kapcsolódó beszerzési igénylések listája látható.</span><span class="sxs-lookup"><span data-stu-id="2884f-130">Click the **Work order purchase requisition** button to open the **Work order purchase requisition** list to see a list of purchase requisitions related to the work orders in the work order pool.</span></span>

15. <span data-ttu-id="2884f-131">Kattintson a **Munkarendelés-beszerzés** gombra a **Munkarendelés-beszerzés** lista megnyitásához, ahol a munkarendelés-gyűjtőben szereplő munkarendelésekhez kapcsolódó beszerzési rendelések listája látható.</span><span class="sxs-lookup"><span data-stu-id="2884f-131">Click the **Work order purchase** button to open the **Work order purchase** list to see a list of purchase orders related to the work orders in the work order pool.</span></span>

>[!NOTE]
><span data-ttu-id="2884f-132">Ha egy munkarendelés-gyűjtő már nem releváns a munkatervezéshez, akkor a gyűjtő **Aktív** jelölőnégyzetét állítsa „Nem” értékre a **Munkarendelés-gyűjtő** listanézetében.</span><span class="sxs-lookup"><span data-stu-id="2884f-132">When a work order pool is no longer relevant for your work planning, set the **Active** check box for that pool to "No" in the **Work order pool** list view.</span></span>

<span data-ttu-id="2884f-133">Jelölje be a **Munkarendelés-kapcsolatok törlése** jelölőnégyzetet, ha az összes munkarendelési sort törölni szeretné, például azért, hogy üres gyűjtőt hozzon létre, amelyet később más munkarendelésekhez használhat.</span><span class="sxs-lookup"><span data-stu-id="2884f-133">Select the **Delete work order relations** check box if you want to delete all work order lines, for example to create an empty pool that you can later use for other work orders.</span></span> <span data-ttu-id="2884f-134">Ne felejtse el törölni a **Munkarendelés-kapcsolatok törlése** jelölőnégyzetet, ha a munkarendelés-gyűjtőt szeretné használni a későbbiekben új munkarendelés-kapcsolatok létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="2884f-134">Remember to clear the **Delete work order relations** check box if you want to use the work order pool to create new work order relations later.</span></span>


![1. ábra](media/22-work-orders.png)


## <a name="add-work-order-to-a-work-order-pool"></a><span data-ttu-id="2884f-136">Munkarendelés hozzáadása egy munkarendelés-gyűjtőhöz</span><span class="sxs-lookup"><span data-stu-id="2884f-136">Add work order to a work order pool</span></span>

<span data-ttu-id="2884f-137">A fenti szakaszban leírt módon munkarendeléseket adhat hozzá a munkarendelés-gyűjtőhöz, amikor létrehozza a gyűjtőt.</span><span class="sxs-lookup"><span data-stu-id="2884f-137">As described in the section above, you can add work orders to a work order pool when you create the pool.</span></span> <span data-ttu-id="2884f-138">Munkarendeléseket az **Összes munkarendelés** listából is hozzáadhat egy munkarendelés-gyűjtőhöz.</span><span class="sxs-lookup"><span data-stu-id="2884f-138">You can also add a work order to a work order pool from one of the **All work orders** list.</span></span>

1. <span data-ttu-id="2884f-139">Kattintson az **Eszközkezelés** > **Közös** > **Munkarendelések** > **Összes munkarendelés** vagy **Aktív munkarendelések** elemre.</span><span class="sxs-lookup"><span data-stu-id="2884f-139">Click **Asset management** > **Common** > **Work orders** > **All work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="2884f-140">Válassza ki a munkarendelést a listán, majd kattintson a **Munkarendelés-gyűjtő** elemre.</span><span class="sxs-lookup"><span data-stu-id="2884f-140">Select the work order in the list, and click **Work order pool**.</span></span>

3. <span data-ttu-id="2884f-141">Válassza a „Hozzáadás” lehetőséget a **Hozzáadás/eltávolítás** mezőben.</span><span class="sxs-lookup"><span data-stu-id="2884f-141">Select "Add" in the **Add/remove** field.</span></span>

4. <span data-ttu-id="2884f-142">Válassza a munkarendelés-gyűjtőt a **Gyűjtő** mezőben.</span><span class="sxs-lookup"><span data-stu-id="2884f-142">Select the work order pool in the **Pool** field.</span></span>

5. <span data-ttu-id="2884f-143">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="2884f-143">Click **OK**.</span></span>

6. <span data-ttu-id="2884f-144">Miután a munkarendelést a munkarendelés-gyűjtőhöz adta, ha szeretné a munkarendelést a gyűjtőben meghatározott sorrendbe tenni: Nyissa meg a munkarendelés-gyűjtő egyik listaoldalát, válassza ki a gyűjtőt, majd kattintson a **Szerkesztés** lehetőségre, és rendezze a gyűjtőben található munkarendelések rendezési sorrendjét a **Munkarendelés-gyűjtő** űrlap > **Munkarendelések** gyorslap > **Rendezési sorrend** mezőben.</span><span class="sxs-lookup"><span data-stu-id="2884f-144">After you have added a work order to a work order pool, if you want to place the work order in a specific sequence in the pool: Open one of the work order pools list pages, select the pool and click **Edit**, and adjust the sort order of the work orders included in pool in the **Work order pool** form > **Work orders** FastTab > **Sort order** field.</span></span>

<span data-ttu-id="2884f-145">Ha egy munkarendelési gyűjtőből szeretné eltávolítani a kiválasztott munkarendelést, válassza a 3. lépésben az „Eltávolítás” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2884f-145">If you want to remove the selected work order from a work order pool, select "Remove" in step 3.</span></span>

