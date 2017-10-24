---
title: "Raktári munkairányelvek"
description: "A raktári munkairányelvek szabályozzák, hogy a gyártási raktári folyamatai létrehoznak-e raktári munkát a munkarendelés-típus, a készlethely és a termék alapján."
author: johanhoffmann
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WHSWorkPolicy
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 196561
ms.assetid: cbf48ec6-1836-48d5-ad66-a9b534af1786
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: ec7dd3b91851729e866bc90ca85a118839f9d71d
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="warehouse-work-policies"></a><span data-ttu-id="8a2b4-103">Raktári munkairányelvek</span><span class="sxs-lookup"><span data-stu-id="8a2b4-103">Warehouse work policies</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="8a2b4-104">A Microsoft Dynamics 365 for Finance and Operations Enterprise edition rendszerben a raktári munkairányelvek szabályozzák, hogy a gyártási raktári folyamatai létrehoznak-e raktári munkát a munkarendelés-típus, a készlethely és a termék alapján.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-104">Warehouse work policies in Microsoft Dynamics 365 for Finance and Operations, Enterprise edition control whether warehouse work is created by warehouse processes in manufacturing, based on work order type, inventory location, and product.</span></span>

<span data-ttu-id="8a2b4-105">Ez a munka-irányelv szabályozza, hogy létrejöjjön-e raktári munka a gyártás raktári folyamataihoz.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-105">This work policy controls whether warehouse work is created for warehouse processes in manufacturing.</span></span> <span data-ttu-id="8a2b4-106">A munka-irányelvet a **munkarendelési típusok**, egy **készlethely** és egy **termék** kombinációjának segítségével állíthatja be.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-106">You can set up the work policy by using a combination of **work order types**, an **inventory location**, and a **product**.</span></span> <span data-ttu-id="8a2b4-107">Például az L0101 termék a jelentés szerint elkészült leszállításra a 001. helyre.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-107">For example, product L0101 is reported as finished to output location 001.</span></span> <span data-ttu-id="8a2b4-108">A késztermék később egy másik termelési rendelésben kerül felhasználásra a 001. kimeneti helyen.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-108">The finished good is later consumed in another production order at output location 001.</span></span> <span data-ttu-id="8a2b4-109">Ebben az esetben beállíthat egy munka-irányelvet annak megakadályozására, hogy munka jöjjön létre a késztermék betárolására, amikor az L0101 termék úgy szerepel a jelentésben, mint amely elkészült leszállításra a 001. helyre.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-109">In this case, you can set up a work policy to prevent the work for finished goods put-away from being created when you report product L0101 as finished to output location 001.</span></span> <span data-ttu-id="8a2b4-110">A munka-irányelv egy egyéni entitás, amelyet a következő információk segítségével lehet leírni:</span><span class="sxs-lookup"><span data-stu-id="8a2b4-110">The work policy is an individual entity that can be described through the following information:</span></span>

-   <span data-ttu-id="8a2b4-111">**Munka-irányelv neve** (a munka-irányelv egyedi azonosítója)</span><span class="sxs-lookup"><span data-stu-id="8a2b4-111">**Work policy name** (the unique identifier of the work policy)</span></span>
-   <span data-ttu-id="8a2b4-112">**Munkarendelési típusok** és **A munka létrehozásának módszere**</span><span class="sxs-lookup"><span data-stu-id="8a2b4-112">**Work order types** and **Work creation method**</span></span>
-   <span data-ttu-id="8a2b4-113">**Készlethelyek**</span><span class="sxs-lookup"><span data-stu-id="8a2b4-113">**Inventory locations**</span></span>
-   <span data-ttu-id="8a2b4-114">**Termékek**</span><span class="sxs-lookup"><span data-stu-id="8a2b4-114">**Products**</span></span>

## <a name="work-order-types"></a><span data-ttu-id="8a2b4-115">Munkarendelés típusai</span><span class="sxs-lookup"><span data-stu-id="8a2b4-115">Work order types</span></span>
<span data-ttu-id="8a2b4-116">A következő munkarendelési típusok közül választhat:</span><span class="sxs-lookup"><span data-stu-id="8a2b4-116">You can select the following work order types:</span></span>

-   <span data-ttu-id="8a2b4-117">Késztermékek betárolása</span><span class="sxs-lookup"><span data-stu-id="8a2b4-117">Finished goods put away</span></span>
-   <span data-ttu-id="8a2b4-118">Társ- és melléktermék betárolása</span><span class="sxs-lookup"><span data-stu-id="8a2b4-118">Co-product and by-product put away</span></span>
-   <span data-ttu-id="8a2b4-119">Nyersanyag kitárolása</span><span class="sxs-lookup"><span data-stu-id="8a2b4-119">Raw material picking</span></span>

<span data-ttu-id="8a2b4-120">A **Munka létrehozásának módszere** mező értéke **Soha**.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-120">The **Work creation method** field has the value **Never**.</span></span> <span data-ttu-id="8a2b4-121">Ez az érték azt jelzi, hogy a munka-irányelv megakadályozza, hogy raktárkezelési munka jöjjön létre a kiválasztott munkarendelési típushoz.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-121">This value indicates that the work policy will prevent warehouse work from being created for the selected work order type.</span></span>

## <a name="inventory-locations"></a><span data-ttu-id="8a2b4-122">Készlethelyek</span><span class="sxs-lookup"><span data-stu-id="8a2b4-122">Inventory locations</span></span>
<span data-ttu-id="8a2b4-123">Kiválaszthatja a helyet, amelyre a munka-irányelv vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-123">You can select a location that the work policy applies to.</span></span> <span data-ttu-id="8a2b4-124">Ha nincs hely társítva a munka-irányelvhez, a munka-irányelv nem vonatkozik semmilyen folyamatra.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-124">If no location is associated with a work policy, the work policy doesn’t apply to any processes.</span></span> <span data-ttu-id="8a2b4-125">A **Helyek** lapon is kiválaszthatja az adott helyre vonatkozó munka-irányelvet, illetve törölheti a kijelölést.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-125">On the **Locations** page, you can also select or cancel the selection of the work policy for a specific location.</span></span>

## <a name="products"></a><span data-ttu-id="8a2b4-126">Termékek</span><span class="sxs-lookup"><span data-stu-id="8a2b4-126">Products</span></span>
<span data-ttu-id="8a2b4-127">Kiválaszthatja egy terméket, amelyre a munka-irányelv vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-127">You can select a product that the work policy applies to.</span></span> <span data-ttu-id="8a2b4-128">A munka-irányelv vonatkozhat az összes termékre vagy a kijelölt termékekre.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-128">You can apply the work policy to either all products or selected products.</span></span>

## <a name="example"></a><span data-ttu-id="8a2b4-129">Példa</span><span class="sxs-lookup"><span data-stu-id="8a2b4-129">Example</span></span>
<span data-ttu-id="8a2b4-130">A következő példában két termelési rendelés szerepel: a PRD-001 és a PRD-00*2*.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-130">In the following example, there are two production orders, PRD-001 and PRD-00*2*.</span></span> <span data-ttu-id="8a2b4-131">A PRD-001 termelési rendeléshez egy **Összeszerelés** nevű művelet tartozik, ahol az SC1 termék a jelentés szerint elkészült leszállításra az O1 helyre.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-131">Production order PRD-001 has an operation that is named **Assembly**, where product SC1 is being reported as finished to location O1.</span></span> <span data-ttu-id="8a2b4-132">A PRD-002 termelési rendeléshez egy **Festés** nevű művelet tartozik, ami felhasználja az SC1 terméket a O1 helyről.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-132">Production order PRD-002 has an operation that is named **Painting** and consumes product SC1 from location O1.</span></span> <span data-ttu-id="8a2b4-133">A PRD-002 termelési rendelés RM1 nyersanyagot is felhasznál az O1 helyről.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-133">Production order PRD-002 also consumes raw material RM1 from location O1.</span></span> <span data-ttu-id="8a2b4-134">Az RM1 tárolása a BULK-001 raktári helyszínen történik, és kitárolásra kerül az O1 helyre a nyersanyag-kitárolási raktári munka segítségével.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-134">RM1 is stored in warehouse location BULK-001 and will be picked to location O1 by warehouse work for raw material picking.</span></span> <span data-ttu-id="8a2b4-135">A kitárolási munka akkor jön létre, amikor a PRD-002 termelés kiadásra kerül.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-135">The picking work is generated when production PRD-002 is released.</span></span> 

<span data-ttu-id="8a2b4-136">[![Raktári munkairányelvek](./media/warehouse-work-policies.png)](./media/warehouse-work-policies.png)</span><span class="sxs-lookup"><span data-stu-id="8a2b4-136">[![Warehouse work policies](./media/warehouse-work-policies.png)](./media/warehouse-work-policies.png)</span></span> 

<span data-ttu-id="8a2b4-137">Amikor raktári munka-irányelv konfigurálását tervezi ehhez az esethez, vegye figyelembe a következő információkat:</span><span class="sxs-lookup"><span data-stu-id="8a2b4-137">When you plan to configure a warehouse work policy for this scenario, you should consider the following information:</span></span>

-   <span data-ttu-id="8a2b4-138">A késztermékek betárolására vonatkozó raktári munkára nincs szükség, ha az SC1 terméket úgy szerepelteti a jelentésben, mint amely a PRD-001 termelési rendelésből elkészült, és az O1 helyre került.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-138">Warehouse work for finished goods put-away isn’t required when you report product SC1 as finished from production order PRD-001 to location O1.</span></span> <span data-ttu-id="8a2b4-139">Ennek oka, hogy a PRD-002 termelési rendelés **Festés** művelete SC1-et használ fel ugyanazon a helyen.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-139">This is because the **Painting** operation for production order PRD-002 consumes SC1 at the same location.</span></span>
-   <span data-ttu-id="8a2b4-140">A nyersanyag kitárolására vonatkozó raktári munkára szükség van, hogy az RM1 nyersanyagot át lehessen helyezni a BULK-001 raktári helyszínről az O1 helyre.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-140">Warehouse work for raw material picking is required in order to move raw material RM1 from warehouse location BULK-001 to location O1.</span></span>

<span data-ttu-id="8a2b4-141">Íme egy példa a munka-irányelvre, amelyet be lehet beállítani ezen szempontok alapján.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-141">Here is an example of the work policy that you can set up, based on these considerations.</span></span>

|                                         |                                                       |
|-----------------------------------------|-------------------------------------------------------|
|<span data-ttu-id="8a2b4-142">**Munkairányelv neve**</span><span class="sxs-lookup"><span data-stu-id="8a2b4-142">**Work policy name**</span></span><br>                 |<span data-ttu-id="8a2b4-143">**Munkarendelés típusai**</span><span class="sxs-lookup"><span data-stu-id="8a2b4-143">**Work order types**</span></span><br>                               |
| <span data-ttu-id="8a2b4-144">Nincs betárolás a 01 esetében</span><span class="sxs-lookup"><span data-stu-id="8a2b4-144">No put away 01     \`</span></span>                    |<span data-ttu-id="8a2b4-145">- Késztermék betárolása</span><span class="sxs-lookup"><span data-stu-id="8a2b4-145">- Finished good put away</span></span><br>                           |
|                                         |<span data-ttu-id="8a2b4-146">**Helyek**</span><span class="sxs-lookup"><span data-stu-id="8a2b4-146">**Locations**</span></span><br>                                      |
|                                         |<span data-ttu-id="8a2b4-147">- O1</span><span class="sxs-lookup"><span data-stu-id="8a2b4-147">- O1</span></span>   |                                               |
|                                         |<span data-ttu-id="8a2b4-148">**Termékek**</span><span class="sxs-lookup"><span data-stu-id="8a2b4-148">**Products**</span></span> <br>                                      |
|                                         |<span data-ttu-id="8a2b4-149">- SC1</span><span class="sxs-lookup"><span data-stu-id="8a2b4-149">- SC1</span></span>                                                  |

<span data-ttu-id="8a2b4-150">Az alábbi eljárások lépésről lépésre ismertetik, hogyan lehet a raktári munka-irányelvet beállítani ehhez az esethez.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-150">The following procedures provide step-by-step instructions about how to set up the warehouse work policy for this scenario.</span></span> <span data-ttu-id="8a2b4-151">Egy beállítási minta is ismertetésre kerül, amely azt mutatja meg, hogyan lehet egy jelentésben egy termelési rendelést készként szerepeltetni, ahol a leszállítás egy olyan helyre történik, amelynek szabályozása nem azonosítótáblán alapul.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-151">A sample setup showing how to report a production order as finished to a location that isn’t license plate–controlled is also described.</span></span>

## <a name="set-up-a-warehouse-work-policy"></a><span data-ttu-id="8a2b4-152">Raktári munka-irányelv beállítása</span><span class="sxs-lookup"><span data-stu-id="8a2b4-152">Set up a warehouse work policy</span></span>
<span data-ttu-id="8a2b4-153">A raktárkezelési folyamatok nem mindig tartalmazzák a raktári munkát.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-153">Warehouse processes don’t always include warehouse work.</span></span> <span data-ttu-id="8a2b4-154">A munka irányelveinek használatával megakadályozhatja a nyersanyag kitárolására és a befejezett termékek betárolására vonatkozó munka létrehozását egy termékkészletre vonatkozóan az adott helyeken.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-154">By defining a work policy, you can prevent the creation of work for raw material picking and put-away of finished goods for a set of products at specific locations.</span></span> <span data-ttu-id="8a2b4-155">Az USMF bemutatócég adatai kerültek felhasználásra a jelen eljárás létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-155">The USMF demo data company was used to create this procedure.</span></span> 

<span data-ttu-id="8a2b4-156">LÉPÉS (21)</span><span class="sxs-lookup"><span data-stu-id="8a2b4-156">STEPS (21)</span></span>

|     |                                                                            |
|-----|----------------------------------------------------------------------------|
| <span data-ttu-id="8a2b4-157">1.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-157">1.</span></span>  | <span data-ttu-id="8a2b4-158">Ugorjon a Raktárkezelés &gt; Beállítás &gt; Munka &gt; Munkairányelvek pontra.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-158">Go to Warehouse management &gt; Setup &gt; Work &gt; Work policies.</span></span>        |
| <span data-ttu-id="8a2b4-159">2.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-159">2.</span></span>  | <span data-ttu-id="8a2b4-160">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-160">Click New.</span></span>                                                                 |
| <span data-ttu-id="8a2b4-161">3.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-161">3.</span></span>  | <span data-ttu-id="8a2b4-162">A Munkairányelv neve mezőbe írja be a „Nincs betárolási munka” szöveget.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-162">In the Work policy name field, type 'No put-away work'.</span></span>                    |
| <span data-ttu-id="8a2b4-163">4.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-163">4.</span></span>  | <span data-ttu-id="8a2b4-164">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-164">Click Save.</span></span>                                                                |
| <span data-ttu-id="8a2b4-165">5.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-165">5.</span></span>  | <span data-ttu-id="8a2b4-166">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-166">Click Add.</span></span>                                                                 |
| <span data-ttu-id="8a2b4-167">6.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-167">6.</span></span>  | <span data-ttu-id="8a2b4-168">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-168">In the list, mark the selected row.</span></span>                                        |
| <span data-ttu-id="8a2b4-169">7.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-169">7.</span></span>  | <span data-ttu-id="8a2b4-170">A Munka rendelési típusa mezőben válassza ki a „Késztermékek betárolása” szöveget.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-170">In the Work order type field, select 'Finished goods put away'.</span></span>            |
| <span data-ttu-id="8a2b4-171">8.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-171">8.</span></span>  | <span data-ttu-id="8a2b4-172">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-172">Click Add.</span></span>                                                                 |
| <span data-ttu-id="8a2b4-173">9.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-173">9.</span></span>  | <span data-ttu-id="8a2b4-174">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-174">In the list, mark the selected row.</span></span>                                        |
| <span data-ttu-id="8a2b4-175">10.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-175">10.</span></span> | <span data-ttu-id="8a2b4-176">A Munka rendelés típusa mezőben válassza ki a „Társtermék és melléktermék betárolása” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-176">In the Work order type field, select 'Co-product and by-product put away'.</span></span> |
| <span data-ttu-id="8a2b4-177">11.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-177">11.</span></span> | <span data-ttu-id="8a2b4-178">Bontsa ki a Készlethelyek szakaszt.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-178">Expand the Inventory locations section.</span></span>                                    |
| <span data-ttu-id="8a2b4-179">12.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-179">12.</span></span> | <span data-ttu-id="8a2b4-180">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-180">Click Add.</span></span>                                                                 |
| <span data-ttu-id="8a2b4-181">13.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-181">13.</span></span> | <span data-ttu-id="8a2b4-182">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-182">In the list, mark the selected row.</span></span>                                        |
| <span data-ttu-id="8a2b4-183">14.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-183">14.</span></span> | <span data-ttu-id="8a2b4-184">Írja be az „51” értéket a Raktár listájában.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-184">In the Warehouse list, enter '51'.</span></span>                                         |
| <span data-ttu-id="8a2b4-185">15.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-185">15.</span></span> | <span data-ttu-id="8a2b4-186">A Hely mezőben adjon meg vagy válasszon ki a „001” értéket.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-186">In the Location field, enter or select '001'.</span></span>                              |
| <span data-ttu-id="8a2b4-187">16.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-187">16.</span></span> | <span data-ttu-id="8a2b4-188">Bontsa ki a Termékek szakaszt.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-188">Expand the Products section.</span></span>                                               |
| <span data-ttu-id="8a2b4-189">17.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-189">17.</span></span> | <span data-ttu-id="8a2b4-190">A Termékkiválasztás mezőben válassza ki a „Termékaltípus” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-190">In the Product selection field, select 'Selected'.</span></span>                         |
| <span data-ttu-id="8a2b4-191">18.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-191">18.</span></span> | <span data-ttu-id="8a2b4-192">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-192">Click Add.</span></span>                                                                 |
| <span data-ttu-id="8a2b4-193">19.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-193">19.</span></span> | <span data-ttu-id="8a2b4-194">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-194">In the list, mark the selected row.</span></span>                                        |
| <span data-ttu-id="8a2b4-195">20.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-195">20.</span></span> | <span data-ttu-id="8a2b4-196">Az Elemszám mezőben adjon meg, vagy válasszon ki „L0101” értéket.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-196">In the Item number field, enter or select 'L0101'.</span></span>                         |
| <span data-ttu-id="8a2b4-197">21.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-197">21.</span></span> | <span data-ttu-id="8a2b4-198">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-198">Click Save.</span></span>                                                                |

## <a name="report-a-production-order-as-finished-to-a-location-that-isnt-license-platecontrolled"></a><span data-ttu-id="8a2b4-199">Termelési megrendelés lejelentése készként egy olyan helyre, amelynek szabályozása nem azonosítótáblán alapul</span><span class="sxs-lookup"><span data-stu-id="8a2b4-199">Report a production order as finished to a location that isn’t license plate–controlled</span></span>
<span data-ttu-id="8a2b4-200">Ez az eljárás egy olyan példát tartalmaz, amely azt mutatja meg, hogyan lehet egy jelentésben egy rendelést készként és leszállítottként szerepeltetni egy olyan helyen, amelynek szabályozása nem azonosítótáblán alapul.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-200">This procedure shows an example of reporting as finished to a location that isn't license plate–controlled.</span></span> <span data-ttu-id="8a2b4-201">Az alkalmazható munkairányelvek ezen feladat előfeltételei.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-201">An applicable work policy is the prerequisite for this task.</span></span> <span data-ttu-id="8a2b4-202">A korábbi eljárás a munka-irányelvek beállítását mutatja be.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-202">The previous procedure shows the setup of the work policy.</span></span> 

<span data-ttu-id="8a2b4-203">LÉPÉS (25)</span><span class="sxs-lookup"><span data-stu-id="8a2b4-203">STEPS (25)</span></span>

<table>
<tbody>
<tr>
<td colspan="3"><span data-ttu-id="8a2b4-204"><strong>Részfeladat: A kimeneti helyek beállítása.</strong></span><span class="sxs-lookup"><span data-stu-id="8a2b4-204"><strong>Sub-task: Set up an output location.</strong></span></span></td>
</tr>
<tr>
<td></td>
<td>1.</td>
<td><span data-ttu-id="8a2b4-205">Ugrás a Szervezet felügyelete &gt; Erőforrások &gt; Erőforráscsoportok részhez.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-205">Go to Organization administration &gt; Resources &gt; Resource groups.</span></span></td>
</tr>
<tr>
<td></td>
<td>2.</td>
<td><span data-ttu-id="8a2b4-206">Válassza ki a listában az „5102” erőforráscsoportot.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-206">In the list, select resource group '5102'.</span></span></td>
</tr>
<tr>
<td></td>
<td>3.</td>
<td><span data-ttu-id="8a2b4-207">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-207">Click Edit.</span></span></td>
</tr>
<tr>
<td></td>
<td>4.</td>
<td><span data-ttu-id="8a2b4-208">Adja meg a Kimeneti raktár mezőben az „51” értéket.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-208">In the Output warehouse field, enter '51'.</span></span></td>
</tr>
<tr>
<td></td>
<td>5.</td>
<td><span data-ttu-id="8a2b4-209">Adja meg a Kimeneti hely mezőben az „001” értéket.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-209">In the Output location field, enter '001'.</span></span></td>
</tr>
<tr>
<td></td>
<td>6.</td>
<td><span data-ttu-id="8a2b4-210">A 001 Hely nem egy azonosítótáblás szabályozású hely.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-210">Location 001 isn't a license plate–controlled location.</span></span> <span data-ttu-id="8a2b4-211">A nem azonosítótáblás kimeneti helyet csak akkor állíthatja be, ha a megfelelő munkairányelveket létrehozták a helyre vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-211">You can set up a non–license plate output location only if an applicable work policy exists for the location.</span></span></td>
</tr>
<tr>
<td colspan="3"><span data-ttu-id="8a2b4-212"><strong>Részfeladat: A Termelési jelentés létrehozása és készként történő jelentése.</strong></span><span class="sxs-lookup"><span data-stu-id="8a2b4-212"><strong>Sub-task: Create a production order and report it as finished.</strong></span></span></td>
</tr>
<tr>
<td></td>
<td>1.</td>
<td><span data-ttu-id="8a2b4-213">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-213">Close the page.</span></span></td>
</tr>
<tr>
<td></td>
<td>2.</td>
<td><span data-ttu-id="8a2b4-214">Ugrás a Gyártásvezérlés &gt; Termelési rendelések &gt; Minden termelési rendelésre.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-214">Go to Production control &gt; Production orders &gt; All production orders.</span></span></td>
</tr>
<tr>
<td></td>
<td>3.</td>
<td><span data-ttu-id="8a2b4-215">Kattintson az Új termelési rendelés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-215">Click New production order.</span></span></td>
</tr>
<tr>
<td></td>
<td>4.</td>
<td><span data-ttu-id="8a2b4-216">Adja meg a „L0101” értéket a Cikkszám mezőben.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-216">In the Item number field, enter 'L0101'.</span></span></td>
</tr>
<tr>
<td></td>
<td>5.</td>
<td><span data-ttu-id="8a2b4-217">Kattintson az Új > lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-217">Click Create.</span></span></td>
</tr>
<tr>
<td></td>
<td>6.</td>
<td><span data-ttu-id="8a2b4-218">A Művelet panelen kattintson a Termelési rendelés elemre.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-218">On the Action Pane, click Production order.</span></span></td>
</tr>
<tr>
<td></td>
<td>7.</td>
<td><span data-ttu-id="8a2b4-219">Kattintson a Becslés elemre.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-219">Click Estimate.</span></span></td>
</tr>
<tr>
<td></td>
<td>8.</td>
<td><span data-ttu-id="8a2b4-220">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-220">Click OK.</span></span></td>
</tr>
<tr>
<td></td>
<td>9.</td>
<td><span data-ttu-id="8a2b4-221">Kattintson a Start parancsra.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-221">Click Start.</span></span></td>
</tr>
<tr>
<td></td>
<td>10.</td>
<td><span data-ttu-id="8a2b4-222">Kattintson az Általános fülre.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-222">Click the General tab.</span></span></td>
</tr>
<tr>
<td></td>
<td>11.</td>
<td><span data-ttu-id="8a2b4-223">Az automatikus BOM-felhasználás mezőben válassza ki a „Soha” értéket.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-223">In the Automatic BOM consumption field, select 'Never'.</span></span></td>
</tr>
<tr>
<td></td>
<td>12.</td>
<td><span data-ttu-id="8a2b4-224">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-224">Click OK.</span></span></td>
</tr>
<tr>
<td></td>
<td>13.</td>
<td><span data-ttu-id="8a2b4-225">Kattintson a Készre jelentés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-225">Click Report as finished.</span></span></td>
</tr>
<tr>
<td></td>
<td>14.</td>
<td><span data-ttu-id="8a2b4-226">Kattintson az Általános fülre.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-226">Click the General tab.</span></span></td>
</tr>
<tr>
<td></td>
<td>15.</td>
<td><span data-ttu-id="8a2b4-227">Válassza ki az Igen lehetőséget a Hiba elfogadása mezőben.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-227">Select Yes in the Accept error field.</span></span></td>
</tr>
<tr>
<td></td>
<td>16.</td>
<td><span data-ttu-id="8a2b4-228">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-228">Click OK.</span></span></td>
</tr>
<tr>
<td></td>
<td>17.</td>
<td><span data-ttu-id="8a2b4-229">A Műveleti panelen kattintson a Raktár elemre.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-229">On the Action Pane, click Warehouse.</span></span></td>
</tr>
<tr>
<td></td>
<td>18.</td>
<td><span data-ttu-id="8a2b4-230">Kattintson a Munka részletei lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-230">Click Work details.</span></span></td>
</tr>
<tr>
<td></td>
<td>19.</td>
<td><span data-ttu-id="8a2b4-231">Amikor a termelési rendelést készként jelentették, a rendszer nem hozott létre munkát a betárolásra.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-231">When the production order was reported as finished, no work was generated for put-away.</span></span> <span data-ttu-id="8a2b4-232">Ennek az az oka, hogy a munkairányelveket úgy határozzák meg, hogy megakadályozza a munka létrehozását, amikor a rendszer készként jelenti a L0101 terméket a 001 helyen.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-232">This occurs because a work policy is defined that prevents work from being generated when product L0101 is reported as finished to location 001.</span></span></td>
</tr>
</tbody>
</table>



