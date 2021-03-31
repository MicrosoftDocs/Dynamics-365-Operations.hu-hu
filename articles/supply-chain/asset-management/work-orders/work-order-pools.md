---
title: Munkarendelés-gyűjtők
description: Ez a témakör bemutatja a munkarendelés-gyűjtők használatát az Eszközkezelés modulban.
author: josaw1
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetWorkOrderTablePoolPart, EntAssetWorkOrderPoolReferenceInfoPart, EntAssetWorkOrderPool, EntAssetWorkOrderPoolPreviewPart
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 6154282045d8ef6da00ecc70ff67f1f9fd3dc53b
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5223482"
---
# <a name="work-order-pools"></a><span data-ttu-id="7f4fc-103">Munkarendelés-gyűjtők</span><span class="sxs-lookup"><span data-stu-id="7f4fc-103">Work order pools</span></span>

[!include [banner](../../includes/banner.md)]


<span data-ttu-id="7f4fc-104">A munkarendelés-gyűjtőkkel csoportosíthatja a valamiben egyeztő munkarendeléseket.</span><span class="sxs-lookup"><span data-stu-id="7f4fc-104">You can use work order pools to group work orders that have something in common.</span></span> <span data-ttu-id="7f4fc-105">Íme néhány példa olyan dolgokra, amelyekhez létrehozhat munkarendelés-gyűjtőket:</span><span class="sxs-lookup"><span data-stu-id="7f4fc-105">Here are some examples of things that you can create  work order pools for:</span></span>

- <span data-ttu-id="7f4fc-106">Munkaszemélyzet, például A karbantartási személyzet vagy B karbantartási személyzet</span><span class="sxs-lookup"><span data-stu-id="7f4fc-106">Work crews, for example, Maintenance Crew A or Maintenance Crew B</span></span>  

- <span data-ttu-id="7f4fc-107">Szakmához kapcsolódó szakértelmek, például villanyszerelők vagy vízvezeték-szerelők</span><span class="sxs-lookup"><span data-stu-id="7f4fc-107">Professional skills, such as electricians or plumbers</span></span>  

- <span data-ttu-id="7f4fc-108">Fizikai helyek</span><span class="sxs-lookup"><span data-stu-id="7f4fc-108">Physical locations</span></span>  

- <span data-ttu-id="7f4fc-109">Időbeosztások, például hetek vagy más időszakok</span><span class="sxs-lookup"><span data-stu-id="7f4fc-109">Time schedules, such as weeks or other periods</span></span>  

<span data-ttu-id="7f4fc-110">A szükséges módon egyetlen munkarendelést is beállíthat több munkarendelés-gyűjtőben.</span><span class="sxs-lookup"><span data-stu-id="7f4fc-110">As you require, you can put one work order in multiple work order pools.</span></span>


## <a name="create-a-work-order-pool"></a><span data-ttu-id="7f4fc-111">Egy munkarendelés-gyűjtő létrehozása</span><span class="sxs-lookup"><span data-stu-id="7f4fc-111">Create a work order pool</span></span>

<span data-ttu-id="7f4fc-112">Az **Összes munkarendelés-gyűjtő** vagy **Aktív munkarendelés-gyűjtők** listaoldalon áttekintést kaphat saját munkarendelés-gyűjtőiről, és új gyűjtőket hozhat létre.</span><span class="sxs-lookup"><span data-stu-id="7f4fc-112">On the **All work order pools** or **Active work order pools** list page, you can get an overview of your work order pools and create new pools.</span></span>

1. <span data-ttu-id="7f4fc-113">Válassza az **Eszközkezelés** > **Általános** > **Munkarendelés-gyűjtők** > **Összes munkarendelés-gyűjtő** vagy **Aktív munkarendelés-gyűjtők** elemet.</span><span class="sxs-lookup"><span data-stu-id="7f4fc-113">Select **Asset management** > **Common** > **Work order pools** > **All work order pools** or **Active work order pools**.</span></span>

2. <span data-ttu-id="7f4fc-114">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7f4fc-114">Select **New**.</span></span>

3. <span data-ttu-id="7f4fc-115">A **Gyűjtő** mezőben adja meg a munkarendelés-gyűjtő azonosítóját.</span><span class="sxs-lookup"><span data-stu-id="7f4fc-115">In the **Pool** field, enter an ID for the work order pool.</span></span>

4. <span data-ttu-id="7f4fc-116">A **Név** mezőben adjon meg egy nevet.</span><span class="sxs-lookup"><span data-stu-id="7f4fc-116">the **Name** field, enter a name.</span></span>

5. <span data-ttu-id="7f4fc-117">Válassza az **Igen** lehetőséget az **Aktív** beállításnál, amellyel jelezheti, hogy a munkarendelés-gyűjtő aktív.</span><span class="sxs-lookup"><span data-stu-id="7f4fc-117">Set the **Active** option to **Yes** to indicate that the work order pool is active.</span></span>

6. <span data-ttu-id="7f4fc-118">Állítsa **Igen** értékre a **Munkarendelés kapcsolatainak törlése** beállítást, ha szeretne automatikusan eltávolítani munkarendeléseket a munkarendelés-gyűjtőből.</span><span class="sxs-lookup"><span data-stu-id="7f4fc-118">Set the **Delete work order relations** option to **Yes** if work orders should automatically be removed from the work order pool.</span></span>

7. <span data-ttu-id="7f4fc-119">Az **Életciklus-állapot törlése** mezőben válassza a munkarendelés életciklus-állapotát.</span><span class="sxs-lookup"><span data-stu-id="7f4fc-119">In the **Delete lifecycle state** field, select the work order lifecycle state.</span></span> <span data-ttu-id="7f4fc-120">Például a munkarendelés befejezéséhez tartozó munkarendelési életciklus-állapotot beállíthatja, hogy automatikusan törölje a kapcsolatokat a munkarendelés-gyűjtőkből.</span><span class="sxs-lookup"><span data-stu-id="7f4fc-120">For example, the work order lifecycle state for completing a work order could be set to automatically delete relations to work order pools.</span></span>

    <span data-ttu-id="7f4fc-121">A munkarendelés-gyűjtőhöz azonnal hozzáadhat munkarendeléseket.</span><span class="sxs-lookup"><span data-stu-id="7f4fc-121">You can start adding work orders to your work order pool right away.</span></span>

8. <span data-ttu-id="7f4fc-122">A **Munkarendelések** gyorslapon válassza a **Sor hozzáadása** parancsot.</span><span class="sxs-lookup"><span data-stu-id="7f4fc-122">On the **Work orders** FastTab, select **Add line**.</span></span>

9. <span data-ttu-id="7f4fc-123">A **Munkarendelés** mezőben válasszon ki egy munkarendelést.</span><span class="sxs-lookup"><span data-stu-id="7f4fc-123">In the **Work order** field, select a work order.</span></span> <span data-ttu-id="7f4fc-124">A kapcsolódó mezők frissítése automatikusan történik.</span><span class="sxs-lookup"><span data-stu-id="7f4fc-124">The related fields are automatically updated.</span></span>

10. <span data-ttu-id="7f4fc-125">További munkarendelések hozzáadásához ismételje meg a 8–9. lépéseket.</span><span class="sxs-lookup"><span data-stu-id="7f4fc-125">Repeat steps 8 through 9 to add more work orders.</span></span>

11. <span data-ttu-id="7f4fc-126">Ha a hozzáadott munkarendeléseket meghatározott sorrendben kell végrehajtani, akkor a **Rendezési sorrend** mezőbe írja be az **1**, **2**, **3**, és így tovább értékeket a sorrend meghatározásához.</span><span class="sxs-lookup"><span data-stu-id="7f4fc-126">If the work orders that you added should be done in a specific order, in the **Sort order** field, you can enter the numbers **1**, **2**, **3**, and so on, to specify that order.</span></span>

12. <span data-ttu-id="7f4fc-127">A munkarendelési gyűjtőben lévő összes munkarendelés listájának megtekintéséhez kattintson a Művelet ablaktáblán a **Munkarendelési gyűjtő** lapon a **Munkarendelési gyűjtőhöz kapcsolódó** csoportra, válassza a **Munkarendelések** elemet az **Összes munkarendelés** listaoldal megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="7f4fc-127">To view a list of all the work orders that are included in the work order pool, on the Action Pane, on the **Work order pool** tab, in the **View work order pool related** group, select **Work orders** to open the **All work orders** list page.</span></span>

13. <span data-ttu-id="7f4fc-128">A karbantartási ütemezés, nem ütemezett munkarendelések és az ütemezett munkarendelések kapacitásterhelésének kiszámításához és megjelenítéséhez kattintson a Művelet panel **Munkarendelés** lapján a **Munkarendelési gyűjtőhöz kapcsolódó** csoportra, válassza ki a **Kapacitásterhelés** lehetőséget a **Kapacitásterhelés kiszámítása** párbeszédpanel megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="7f4fc-128">To calculate and view capacity load for the maintenance schedule, unscheduled work orders, and scheduled work orders, on the Action Pane, on the **Work order pool** tab, in the **View work order pool related** group, select **Capacity load** to open the **Calculate capacity load** dialog.</span></span>

14. <span data-ttu-id="7f4fc-129">A karbantartási ütemezés, nem ütemezett munkarendelések és az ütemezett munkarendelések cikkelőrejelzéseinek (cserealkatrészek és más szükséges elemek) kiszámításához és megjelenítéséhez kattintson a Művelet panel **Munkarendelés** lapján a **Munkarendelési gyűjtőhöz kapcsolódó** csoportra, válassza ki a **Cikkelőrejelzés** lehetőséget a **Cikkelőrejelzés kiszámítása** párbeszédpanel megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="7f4fc-129">To calculate and view forecasts for items (spare parts and other required items) that are related to maintenance schedule, unscheduled work orders, and scheduled work orders, on the Action Pane, on the **Work order pool** tab, in the **View work order pool related** group, select **Item forecast** to open the **Calculate item forecast** dialog.</span></span>

15. <span data-ttu-id="7f4fc-130">A munkarendelési gyűjtőben lévő munkarendelésekhez kapcsolódó beszerzési igénylések megtekintéséhez kattintson a Művelet ablaktáblán a **Munkarendelési gyűjtő** lapon a **Bezserzés** csoportra, válassza a **Munkarendelés beszerzési igénylései** elemre az **A Munkarendelés beszerzési rendelései** listaoldal megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="7f4fc-130">To view a list of purchase requisitions that are related to the work orders in the work order pool, on the Action Pane, on the **Work order pool** tab, in the **Procurement** group, select **Work order purchase requisition** to open the **Work order purchase requisition** list page.</span></span>

16. <span data-ttu-id="7f4fc-131">A munkarendelési gyűjtőben lévő munkarendelésekhez kapcsolódó beszerzési rendelései megtekintéséhez kattintson a Művelet ablaktáblán a **Munkarendelési gyűjtő** lapon a **Bezserzés** csoportra, válassza a **Munkarendelés beszerzési igénylései** elemre az **A Munkarendelés beszerzései** listaoldal megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="7f4fc-131">To view a list of purchase orders that are related to the work orders in the work order pool, on the Action Pane, on the **Work order pool** tab, in the **Procurement** group, select **Work order purchase** to open the **Work order purchase** list page.</span></span>

>[!NOTE]
><span data-ttu-id="7f4fc-132">Ha egy munkarendelés-gyűjtő már nem releváns a munkatervezéshez, akkor a gyűjtő **Aktív** lehetőségét állítsa be **Nem** értékre a **Munkarendelés-gyűjtő** oldalának listanézetében.</span><span class="sxs-lookup"><span data-stu-id="7f4fc-132">When a work order pool is no longer relevant to your work planning, set the **Active** option for that pool to **No** in the list view of the **Work order pool** page.</span></span>

<span data-ttu-id="7f4fc-133">Az összes alkdolgozó rendelési sor törléséhez állítsa a **Munkarendelés- kapcsolatok törlése** beállítást **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="7f4fc-133">To delete all worker order lines, set the **Delete work order relations** option to **Yes**.</span></span> <span data-ttu-id="7f4fc-134">Ez a beállítás például akkor hasznos, ha egy üres gyűjtőt szeretne létrehozni, amelyet később más munkarendelésekhez használhat.</span><span class="sxs-lookup"><span data-stu-id="7f4fc-134">This option is useful if, for example, you want to create an empty pool that you can use later for other work orders.</span></span> <span data-ttu-id="7f4fc-135">Ha elkészült, ne felejtse a **Munkarendelés-kapcsolatok törlése** lehetőséget **Nem** értékre állítani, ha a munkarendelés-gyűjtőt szeretné használni a későbbiekben új munkarendelés-kapcsolatok létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="7f4fc-135">When you're ready to use the work order pool to create new work order relations later, remember to set the **Delete work order relations** option to **No**.</span></span>

<span data-ttu-id="7f4fc-136">Az alábbi ábra a **Munkarendelés-gyűjtő létrehozása** listaoldal egy példáját mutatja be.</span><span class="sxs-lookup"><span data-stu-id="7f4fc-136">The illustration below shows an example of the **Work order pool** list page.</span></span>

![1. ábra](media/22-work-orders.png)


## <a name="add-a-work-order-to-a-work-order-pool"></a><span data-ttu-id="7f4fc-138">Egy munkarendelés hozzáadása egy munkarendelés-gyűjtőhöz</span><span class="sxs-lookup"><span data-stu-id="7f4fc-138">Add a work order to a work order pool</span></span>

<span data-ttu-id="7f4fc-139">Az előző szakaszban leírt módon munkarendeléseket adhat hozzá a munkarendelés-gyűjtőhöz, amikor létrehozza azt a gyűjtőt.</span><span class="sxs-lookup"><span data-stu-id="7f4fc-139">As described in the previous section, you can add work orders to a work order pool when you create that pool.</span></span> <span data-ttu-id="7f4fc-140">Az **Összes munkarendelések** vagy **Aktív munkarendelések** listaoldalon is hozzáadhat munkarendeléseket a munkarendelés-gyűjtőkhöz.</span><span class="sxs-lookup"><span data-stu-id="7f4fc-140">You can also add work orders to a work order pool on the **All work orders** or **Active work orders** list page.</span></span>

1. <span data-ttu-id="7f4fc-141">Válassza ki a munkarendelést, majd a Művelet panel **Munkarendelés** lapján a **Karbantartás** csoportban válassz a **Munkarendelés-gyűjtő** pontot.</span><span class="sxs-lookup"><span data-stu-id="7f4fc-141">Select the work order, and then, on the Action Pane, on the **Work order** tab, in the **Maintain** group, select **Work order pool**.</span></span>

2. <span data-ttu-id="7f4fc-142">Válassza ki a munkarendelést a listán, majd kattintson a **Munkarendelés-gyűjtő** elemre.</span><span class="sxs-lookup"><span data-stu-id="7f4fc-142">Select the work order in the list, and click **Work order pool**.</span></span>

3. <span data-ttu-id="7f4fc-143">A **Munkarendelés-gyűjtő karbantartása** párbeszédablakban a **Hozzáadás /eltávolítás** mezőben válassza a **Hozzáadás** elemet.</span><span class="sxs-lookup"><span data-stu-id="7f4fc-143">In the **Maintain work order pool** dialog, in the **Add/remove** field, select **Add**.</span></span>

4. <span data-ttu-id="7f4fc-144">Válassza a munkarendelés-gyűjtőt a **Gyűjtő** mezőben.</span><span class="sxs-lookup"><span data-stu-id="7f4fc-144">In the **Pool** field, select the work order pool.</span></span>

5. <span data-ttu-id="7f4fc-145">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7f4fc-145">Select **OK**.</span></span>

6. <span data-ttu-id="7f4fc-146">Ha azt szeretné a hozzáadott munkarendelést egy meghatározott sorrendbe helyezze a munkarendelés-gyűjtőben, az **Összes munkarendelés-gyűjtő** vagy az **Aktív munkarendelés-gyűjtők** listaoldalán válassza ki a gyűjtőt majd válassza a **Szerkesztés** parancsot.</span><span class="sxs-lookup"><span data-stu-id="7f4fc-146">To put the work order that you added in a specific order in the work order pool, on the **All work order pools** or **Active work order pools** list page, select the pool, and then select **Edit**.</span></span> <span data-ttu-id="7f4fc-147">Ezt követően a **Munkarendelési gyűjtő** lap **Munkarendelések** gyorslapján a **Rendezési sorrend** mező segítségével módosíthatja a gyűjtőbe foglalt munkarendelések rendezési sorrendjét.</span><span class="sxs-lookup"><span data-stu-id="7f4fc-147">Then, on the **Work order pool** page, on the **Work orders** FastTab, use the **Sort order** field to adjust the sort order of the work orders that are included in pool.</span></span>

<span data-ttu-id="7f4fc-148">A munkarendelési gyűjtőből egy kiválasztott munkarendelés eltávolításához, válassza a 3. lépésben az **Eltávolítás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7f4fc-148">To remove a work order from a work order pool, repeat these steps, but select **Remove** in step 3.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]