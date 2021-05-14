---
title: Szabálytalanság létrehozása és feldolgozása
description: Ez a témakör leírja, hogy hogyan hajtsa végre a szabálytalanság kezelését, a meglévő minőségi rendelés alapján.
author: perlynne
ms.date: 03/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 06a56a694f7a80d65cb46d08744e78d8361cee3b
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956206"
---
# <a name="create-and-process-nonconformances"></a><span data-ttu-id="b3940-103">Szabálytalanság létrehozása és feldolgozása</span><span class="sxs-lookup"><span data-stu-id="b3940-103">Create and process nonconformances</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b3940-104">Ez a témakör leírja, hogy hogyan hajtsa végre a szabálytalanság kezelését, a meglévő minőségi rendelés alapján.</span><span class="sxs-lookup"><span data-stu-id="b3940-104">This topic describes how to perform nonconformance management based on an existing quality order.</span></span> <span data-ttu-id="b3940-105">A szabálytalanságok kezelését általában egy minőségi munkatárs végez.</span><span class="sxs-lookup"><span data-stu-id="b3940-105">Typically, nonconformance management is done by a quality clerk.</span></span> <span data-ttu-id="b3940-106">Előfeltételként rendelkeznie kell egy minőségi rendeléssel.</span><span class="sxs-lookup"><span data-stu-id="b3940-106">As a prerequisite, you must have a quality order available.</span></span> <span data-ttu-id="b3940-107">(A minőségi rendelés létrehozásáról további tájékoztatásért lásd: [Az áruk minőségének vizsgálata](inspect-quality-goods.md).)</span><span class="sxs-lookup"><span data-stu-id="b3940-107">(For information about how to create a quality order, see [Inspect the quality of goods](inspect-quality-goods.md).)</span></span>

<span data-ttu-id="b3940-108">Ahhoz, hogy egy felhasználó feldolgozhassa a szabálytalanság jóváhagyását, hozzájuk kell rendelni egy dolgozót a **Személy** mezőben a **Felhasználók** oldalon.</span><span class="sxs-lookup"><span data-stu-id="b3940-108">Before a user can process the approval of a nonconformance, a worker must be assigned to them in the **Person** field on the **Users** page.</span></span> <span data-ttu-id="b3940-109">Ezenkívül ahhoz, hogy a felhasználó használni tudja a dokumentum megjegyzéseit, felhasználói beállításai között be kell állítani a **Dokumentumkezelés engedélyezése** beállítást *Igen* értékre.</span><span class="sxs-lookup"><span data-stu-id="b3940-109">Additionally, before the user can use the document notes, the **Enable document handling** option must be set to *Yes* in their user options.</span></span>

## <a name="create-a-nonconformance"></a><span data-ttu-id="b3940-110">Kattintson a Szabálytalanság létrehozása elemre.</span><span class="sxs-lookup"><span data-stu-id="b3940-110">Create a nonconformance</span></span>

<span data-ttu-id="b3940-111">Szabálytalanság létrehozásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="b3940-111">To create a nonconformance, follow these steps.</span></span>

1. <span data-ttu-id="b3940-112">Ugorjon a **Készletkezelés \> Időszakos feladatok \> Minőségkezelés \> Szabálytalanságok** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b3940-112">Go to **Inventory management \> Periodic tasks \> Quality management \> Non conformances**.</span></span>
1. <span data-ttu-id="b3940-113">A műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="b3940-113">On the Action pane, select **New**.</span></span>
1. <span data-ttu-id="b3940-114">A **Szabálytalanság létrehozása** párbeszédpanel **Problématípus** mezőjében válassza ki a vizsgálati folyamat során talált probléma típusát.</span><span class="sxs-lookup"><span data-stu-id="b3940-114">In the **Create non conformance** dialog box, in **Problem type** field, select the type of problem that was found during the inspection process.</span></span>
1. <span data-ttu-id="b3940-115">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b3940-115">Select **OK**.</span></span>

## <a name="approve-or-reject-a-nonconformance"></a><span data-ttu-id="b3940-116">Szabálytalanság jóváhagyása vagy elutasítása</span><span class="sxs-lookup"><span data-stu-id="b3940-116">Approve or reject a nonconformance</span></span>

<span data-ttu-id="b3940-117">Az alábbi lépésekkel jóváhagyhatja vagy elutasíthatja a szabálytalanságot.</span><span class="sxs-lookup"><span data-stu-id="b3940-117">To approve or reject a nonconformance, follow these steps.</span></span>

1. <span data-ttu-id="b3940-118">Ugorjon a **Készletkezelés \> Időszakos feladatok \> Minőségkezelés \> Szabálytalanságok** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b3940-118">Go to **Inventory management \> Periodic tasks \> Quality management \> Non conformances**.</span></span>
1. <span data-ttu-id="b3940-119">A listában keresse meg és válassza ki a frissíteni kívánt szabálytalanságot.</span><span class="sxs-lookup"><span data-stu-id="b3940-119">In the list, select the nonconformance that you want to update.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b3940-120">Javítást csak jóváhagyott szabálytalansághoz lehet hozzáadni.</span><span class="sxs-lookup"><span data-stu-id="b3940-120">You can add a correction only to nonconformances that are approved.</span></span>

1. <span data-ttu-id="b3940-121">A műveletpanelen válassza a **Függvények \> Szabálytlaanság jóváhagyása** elemet a szabálytalanság jóváhagyásához, vagy a **Függvények \> Szabálytalanság elutasítása** elemet az elutasításhoz.</span><span class="sxs-lookup"><span data-stu-id="b3940-121">On the Action Pane, select **Functions \> Approve non conformance** to approve the nonconformance or **Functions \> Refuse non conformance** to reject it.</span></span> <span data-ttu-id="b3940-122">A jóváhagyott szabálytalanságok a [kapcsolódó műveletekhez](../quality-operations.md) társíthatók.</span><span class="sxs-lookup"><span data-stu-id="b3940-122">You can associate approved nonconformances with [related operations](../quality-operations.md).</span></span> <span data-ttu-id="b3940-123">Ily módon rögzítheti a szabálytalanságok kezelésének és a javítás kezelésének részeként végzett munkát.</span><span class="sxs-lookup"><span data-stu-id="b3940-123">In this way, you can record work that is done as part of the nonconformance handling and the processing of correction handling.</span></span>
1. <span data-ttu-id="b3940-124">A rendszer felszólítja, hogy erősítse meg a kiválasztást.</span><span class="sxs-lookup"><span data-stu-id="b3940-124">You're prompted to confirm your selection.</span></span> <span data-ttu-id="b3940-125">A folytatáshoz kattintson az **Igen** gombra.</span><span class="sxs-lookup"><span data-stu-id="b3940-125">Select **Yes** to continue.</span></span>

## <a name="add-operations-and-other-details-to-nonconformances"></a><span data-ttu-id="b3940-126">Műveletek és egyéb részletek hozzáadása a szabálytalanságokhoz</span><span class="sxs-lookup"><span data-stu-id="b3940-126">Add operations and other details to nonconformances</span></span>

<span data-ttu-id="b3940-127">A szabálytalanság létrehozása után elkezdheti hozzáadni a kapcsolódó műveleteket, és további információkat adhat meg az ilyen műveletekről.</span><span class="sxs-lookup"><span data-stu-id="b3940-127">After you've created a nonconformance, you can start to add related operations and specify additional information about those operations.</span></span> <span data-ttu-id="b3940-128">Kapcsolódó műveleteket csak jóváhagyott szabálytalansághoz lehet hozzáadni.</span><span class="sxs-lookup"><span data-stu-id="b3940-128">You can add related operations only to nonconformances that are approved.</span></span>

<span data-ttu-id="b3940-129">Az alapvető információk mellett a következő részleteket lehet hozzáadni egy művelethez:</span><span class="sxs-lookup"><span data-stu-id="b3940-129">Besides the basic information, you can add the following details to an operation:</span></span>

- <span data-ttu-id="b3940-130">**Cikkek** – Létrehozhatja a javítás végrehajtásához felhasznált cikkek listáját.</span><span class="sxs-lookup"><span data-stu-id="b3940-130">**Items** – You can create a list of items that are consumed to perform the correction.</span></span> <span data-ttu-id="b3940-131">Például a cikkek olyan termékek lehetnek, amelyek szükségesek a berendezés javításához, vagy összetevők, amelyek szükségesek a kész termék átdolgozásához.</span><span class="sxs-lookup"><span data-stu-id="b3940-131">For example, the items might be products that are required to repair equipment or ingredients that are required to rework a finished product.</span></span>
- <span data-ttu-id="b3940-132">**Minőségi költségek** – létrehozhatja a külső forrásoknál felmerült vagy nekik számlázott költségek listáját.</span><span class="sxs-lookup"><span data-stu-id="b3940-132">**Quality charges** – You can create a list of charges that are incurred or billed out to external sources.</span></span>
- <span data-ttu-id="b3940-133">**Időnyilvántartás** – Létrehozhat egy naplót arról az időről, amelyet az egyes dolgozók a művelettel töltöttek.</span><span class="sxs-lookup"><span data-stu-id="b3940-133">**Timesheet** – You can create a log of the time that each worker spends on the operation.</span></span>

<span data-ttu-id="b3940-134">A fennmaradó beállítások megadása nem kötelező.</span><span class="sxs-lookup"><span data-stu-id="b3940-134">The remaining settings are optional.</span></span> <span data-ttu-id="b3940-135">Az egyes cikkek költsége, a minőségi költségek és az időnyilvántartások összegezve jelennek meg a műveletben.</span><span class="sxs-lookup"><span data-stu-id="b3940-135">The cost for each item, quality charges, and the timesheet are summed and shown on the operation.</span></span> <span data-ttu-id="b3940-136">A művelet **Költség** mezője nem szerkeszthető közvetlenül.</span><span class="sxs-lookup"><span data-stu-id="b3940-136">You can't directly edit the **Cost** field on the operation.</span></span>

### <a name="create-an-operation-for-a-nonconformance"></a><span data-ttu-id="b3940-137">Művelet létrehozása szabálytalansághoz kapcsolódóan</span><span class="sxs-lookup"><span data-stu-id="b3940-137">Create an operation for a nonconformance</span></span>

<span data-ttu-id="b3940-138">Művelet szabálytalansághoz való létrehozásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="b3940-138">To create an operation for a nonconformance, follow these steps.</span></span>

1. <span data-ttu-id="b3940-139">Ugorjon a **Készletkezelés \> Időszakos feladatok \> Minőségkezelés \> Szabálytalanságok** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b3940-139">Go to **Inventory management \> Periodic tasks \> Quality management \> Non conformances**.</span></span>
1. <span data-ttu-id="b3940-140">A listában keresse meg és válassza ki a frissíteni kívánt szabálytalanságot.</span><span class="sxs-lookup"><span data-stu-id="b3940-140">In the list, select the nonconformance that you want to update.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b3940-141">Műveleteket csak jóváhagyott szabálytalansághoz lehet hozzáadni vagy frissíteni.</span><span class="sxs-lookup"><span data-stu-id="b3940-141">You can add or update operations only for nonconformances that are approved.</span></span>

1. <span data-ttu-id="b3940-142">A Művelet ablaktáblán válassza ki a **Kapcsolódó műveletek** elemet.</span><span class="sxs-lookup"><span data-stu-id="b3940-142">On the Action Pane, select **Related operations**.</span></span>
1. <span data-ttu-id="b3940-143">A **Kapcsolódó műveletek** oldalon a műveleti ablaktáblán válassza az **Új** elemet sor rácshoz adásához.</span><span class="sxs-lookup"><span data-stu-id="b3940-143">On the **Related operations** page, on the Action pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="b3940-144">Ezután új sorhoz állítsa be a következő mezőket:</span><span class="sxs-lookup"><span data-stu-id="b3940-144">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="b3940-145">**Művelet** – A szabálytalanság végrehajtásához szükséges művelet kódjának kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="b3940-145">**Operation** – Select the code of the operation that will be performed for the nonconformance.</span></span>
    - <span data-ttu-id="b3940-146">**Ok** – adjon meg egy részletes leírást, amely leírja, hogy miért van szükség a műveletre.</span><span class="sxs-lookup"><span data-stu-id="b3940-146">**Reason** – Enter a detailed description that explains why the operation is required.</span></span>
    - <span data-ttu-id="b3940-147">**Értékesítési rendelés** – ha a kiválasztott műveletkód az értékesítési rendelés típusával van kapcsolatban, válassza ki azt az értékesítési rendelést, amelyhez a műveletet csatolja.</span><span class="sxs-lookup"><span data-stu-id="b3940-147">**Sales order** – If the selected operation code is related to the sales order type, select the sales order that you're linking the operation to.</span></span>
    - <span data-ttu-id="b3940-148">**Beszerzési rendelés** – ha a kiválasztott műveletkód a beszerzési rendelés típusával van kapcsolatban, válassza ki azt a beszerzési rendelést, amelyhez a műveletet csatolja.</span><span class="sxs-lookup"><span data-stu-id="b3940-148">**Purchase order** – If the selected operation code is related to the purchase order type, select the purchase order that you're linking the operation to.</span></span>

1. <span data-ttu-id="b3940-149">Zárja be a lapokat.</span><span class="sxs-lookup"><span data-stu-id="b3940-149">Close the pages.</span></span>

### <a name="add-items-to-an-operation"></a><span data-ttu-id="b3940-150">Cikkek hozzáadása művelethez</span><span class="sxs-lookup"><span data-stu-id="b3940-150">Add items to an operation</span></span>

<span data-ttu-id="b3940-151">A következő lépésekkel adhat hozzá cikkeket a műveletekhez.</span><span class="sxs-lookup"><span data-stu-id="b3940-151">To add items to an operation, follow these steps.</span></span>

1. <span data-ttu-id="b3940-152">Ugorjon a **Készletkezelés \> Időszakos feladatok \> Minőségkezelés \> Szabálytalanságok** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b3940-152">Go to **Inventory management \> Periodic tasks \> Quality management \> Non conformances**.</span></span>
1. <span data-ttu-id="b3940-153">A listában keresse meg és válassza ki a frissíteni kívánt szabálytalanságot.</span><span class="sxs-lookup"><span data-stu-id="b3940-153">In the list, select the nonconformance that you want to update.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b3940-154">Műveleteket csak jóváhagyott szabálytalansághoz lehet hozzáadni vagy frissíteni.</span><span class="sxs-lookup"><span data-stu-id="b3940-154">You can add or update operations only for nonconformances that are approved.</span></span>

1. <span data-ttu-id="b3940-155">A Művelet ablaktáblán válassza ki a **Kapcsolódó műveletek** elemet.</span><span class="sxs-lookup"><span data-stu-id="b3940-155">On the Action Pane, select **Related operations**.</span></span>
1. <span data-ttu-id="b3940-156">A **Kapcsolódó műveletek** oldalon válassza ki azt a műveletet, amelybe cikkeket szeretne felvenni.</span><span class="sxs-lookup"><span data-stu-id="b3940-156">On the **Related operations** page, select the operation that you want to add items to.</span></span>
1. <span data-ttu-id="b3940-157">A Művelet ablaktáblán kattintson a **Cikkek** elemre.</span><span class="sxs-lookup"><span data-stu-id="b3940-157">On the Action Pane, select **Items**.</span></span>
1. <span data-ttu-id="b3940-158">A **Kapcsolódó műveletek** oldalon a műveleti ablaktáblán válassza az **Új** elemet sor rácshoz adásához.</span><span class="sxs-lookup"><span data-stu-id="b3940-158">On the **Related operations** page, on the Action pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="b3940-159">Ezután új sorhoz állítsa be a következő mezőket:</span><span class="sxs-lookup"><span data-stu-id="b3940-159">Then set the following fields for new row:</span></span>

    - <span data-ttu-id="b3940-160">**Cikkszám** – válassza ki azt a terméket, amely a kiválasztott művelet részeként fel lesz használva.</span><span class="sxs-lookup"><span data-stu-id="b3940-160">**Item number** – Select the product that will be consumed as part of the selected operation.</span></span>
    - <span data-ttu-id="b3940-161">**Mennyiség** – adja meg a felhasználandó cikkek számát.</span><span class="sxs-lookup"><span data-stu-id="b3940-161">**Quantity** – Enter the number of items that will be consumed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b3940-162">A cikk költségét az **Általános** lap **Költség** mezőjében lehet megtekinteni. Az itt látható költség a **Kiadott termék** oldalon beállított költségből származik.</span><span class="sxs-lookup"><span data-stu-id="b3940-162">You can view the cost for the item in the **Cost** field on the **General** tab. The cost that is shown there comes from the cost that is set up on the **Released product** page.</span></span> <span data-ttu-id="b3940-163">A költség nem frissíthető közvetlenül a **Kapcsolódó művelet cikkje** lapon.</span><span class="sxs-lookup"><span data-stu-id="b3940-163">The cost can't be updated directly on the **Related operation item** page.</span></span> <span data-ttu-id="b3940-164">A **Kapcsolódó művelet cikkjei** oldalon hozzáadott összes cikk költségét a program automatikusan hozzáadja a **Költség** mezőhöz a **Kapcsolódó műveletek** oldalon.</span><span class="sxs-lookup"><span data-stu-id="b3940-164">The cost of all items that are added on the **Related operation items** page is automatically added to the **Cost** field on the **Related operations** page.</span></span>

1. <span data-ttu-id="b3940-165">Ismételje meg az előző lépést minden további hozzáadni kívánt cikkel.</span><span class="sxs-lookup"><span data-stu-id="b3940-165">Repeat the previous step for each additional item that you must add.</span></span>
1. <span data-ttu-id="b3940-166">Zárja be a lapokat.</span><span class="sxs-lookup"><span data-stu-id="b3940-166">Close the pages.</span></span>

### <a name="add-quality-charges-to-an-operation"></a><span data-ttu-id="b3940-167">Minőségi költségek hozzáadása egy művelethez</span><span class="sxs-lookup"><span data-stu-id="b3940-167">Add quality charges to an operation</span></span>

<span data-ttu-id="b3940-168">A következő lépésekkel adhat hozzá minőségi költségeket a műveletekhez.</span><span class="sxs-lookup"><span data-stu-id="b3940-168">To add quality charges to an operation, follow these steps.</span></span>

1. <span data-ttu-id="b3940-169">Ugorjon a **Készletkezelés \> Időszakos feladatok \> Minőségkezelés \> Szabálytalanságok** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b3940-169">Go to **Inventory management \> Periodic tasks \> Quality management \> Non conformances**.</span></span>
1. <span data-ttu-id="b3940-170">A listában keresse meg és válassza ki a frissíteni kívánt szabálytalanságot.</span><span class="sxs-lookup"><span data-stu-id="b3940-170">In the list, select the nonconformance that you want to update.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b3940-171">Műveleteket csak jóváhagyott szabálytalansághoz lehet hozzáadni vagy frissíteni.</span><span class="sxs-lookup"><span data-stu-id="b3940-171">You can add or update operations only for nonconformances that are approved.</span></span>

1. <span data-ttu-id="b3940-172">A Művelet ablaktáblán válassza ki a **Kapcsolódó műveletek** elemet.</span><span class="sxs-lookup"><span data-stu-id="b3940-172">On the Action Pane, select **Related operations**.</span></span>
1. <span data-ttu-id="b3940-173">A **Kapcsolódó műveletek** oldalon válassza ki azt a műveletet, amelybe minőségi költségeket szeretne felvenni.</span><span class="sxs-lookup"><span data-stu-id="b3940-173">On the **Related operations** page, select the operation that you want to add quality charges to.</span></span>
1. <span data-ttu-id="b3940-174">A Művelet ablaktáblán válassza ki a **Minőségi költségek** elemet.</span><span class="sxs-lookup"><span data-stu-id="b3940-174">On the Action Pane, select **Quality charges**.</span></span>
1. <span data-ttu-id="b3940-175">A **Kapcsolódó műveletek költségei** oldalon a műveleti ablaktáblán válassza az **Új** elemet sor rácshoz adásához.</span><span class="sxs-lookup"><span data-stu-id="b3940-175">On the **Related operation charges** page, on the Action pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="b3940-176">Ezután új sorhoz állítsa be a következő mezőket:</span><span class="sxs-lookup"><span data-stu-id="b3940-176">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="b3940-177">**Költségkód** – a hozzáadni kívánt minőségi költség kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="b3940-177">**Charges code** – Select the quality charge that you want to add.</span></span>
    - <span data-ttu-id="b3940-178">**Leírás** – Adja meg a költség részletes leírását.</span><span class="sxs-lookup"><span data-stu-id="b3940-178">**Description** – Enter a detailed description of the charge.</span></span>
    - <span data-ttu-id="b3940-179">**Költségek értéke** – A költség összegének megadása.</span><span class="sxs-lookup"><span data-stu-id="b3940-179">**Charges value** – Enter the amount of the charge.</span></span>

1. <span data-ttu-id="b3940-180">Ismételje meg az előző lépést minden további hozzáadni kívánt költséggel.</span><span class="sxs-lookup"><span data-stu-id="b3940-180">Repeat the previous step for each additional charge that you must add.</span></span>
1. <span data-ttu-id="b3940-181">Zárja be a lapokat.</span><span class="sxs-lookup"><span data-stu-id="b3940-181">Close the pages.</span></span>

> [!NOTE]
> <span data-ttu-id="b3940-182">A **Költségek értéke** mezőben található összeget a program automatikusan összegzi minden minőségi költséghez, és hozzáadja a **Kapcsolódó műveletek** oldal **Költség** mezőjében található egyéb összegekhez.</span><span class="sxs-lookup"><span data-stu-id="b3940-182">The amount in the **Charges value** field is automatically summed for all quality charges and added to any other amounts in the **Cost** field on the **Related operations** page.</span></span>

### <a name="create-a-timesheet-on-an-operation"></a><span data-ttu-id="b3940-183">Időnyilvántartás létrehozása művelethez</span><span class="sxs-lookup"><span data-stu-id="b3940-183">Create a timesheet on an operation</span></span>

<span data-ttu-id="b3940-184">A következő lépésekkel adhat hozzá időnyilvántartást a műveletekhez.</span><span class="sxs-lookup"><span data-stu-id="b3940-184">To add a timesheet to an operation, follow these steps.</span></span>

1. <span data-ttu-id="b3940-185">Ugorjon a **Készletkezelés \> Időszakos feladatok \> Minőségkezelés \> Szabálytalanságok** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b3940-185">Go to **Inventory management \> Periodic tasks \> Quality management \> Non conformances**.</span></span>
1. <span data-ttu-id="b3940-186">A listában keresse meg és válassza ki a frissíteni kívánt szabálytalanságot.</span><span class="sxs-lookup"><span data-stu-id="b3940-186">In the list, select the nonconformance that you want to update.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b3940-187">Műveleteket csak jóváhagyott szabálytalansághoz lehet hozzáadni vagy frissíteni.</span><span class="sxs-lookup"><span data-stu-id="b3940-187">You can add or update operations only for nonconformances that are approved.</span></span>

1. <span data-ttu-id="b3940-188">A Művelet ablaktáblán válassza ki a **Kapcsolódó műveletek** elemet.</span><span class="sxs-lookup"><span data-stu-id="b3940-188">On the Action Pane, select **Related operations**.</span></span>
1. <span data-ttu-id="b3940-189">A **Kapcsolódó műveletek** oldalon válassza ki azt a műveletet, amelybe időnyilvántartást szeretne felvenni.</span><span class="sxs-lookup"><span data-stu-id="b3940-189">On the **Related operations** page, select the operation that you want to add a timesheet to.</span></span>
1. <span data-ttu-id="b3940-190">A Műveleti ablaktáblán kattintson a **Időnyilvántartás** elemre.</span><span class="sxs-lookup"><span data-stu-id="b3940-190">On the Action Pane, select **Timesheet**.</span></span>
1. <span data-ttu-id="b3940-191">A **Kapcsolódó műveletek időnyilvántartásai** oldalon a műveleti ablaktáblán válassza az **Új** elemet sor rácshoz adásához.</span><span class="sxs-lookup"><span data-stu-id="b3940-191">On the **Related operation time sheets** page, on the Action pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="b3940-192">Ezután új sorhoz állítsa be a következő mezőket:</span><span class="sxs-lookup"><span data-stu-id="b3940-192">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="b3940-193">**Dátum** – a munka befejezési dátumának megadása.</span><span class="sxs-lookup"><span data-stu-id="b3940-193">**Date** – Specify the date when work was done.</span></span> <span data-ttu-id="b3940-194">Alapértelmezés szerint ez a mező az aktuális dátum.</span><span class="sxs-lookup"><span data-stu-id="b3940-194">By default, this field is set to the current date.</span></span>
    - <span data-ttu-id="b3940-195">**Dolgozó** – Válassza ki a dolgozót, aki a munkát elvégezte.</span><span class="sxs-lookup"><span data-stu-id="b3940-195">**Worker** – Select the worker who did the work.</span></span> <span data-ttu-id="b3940-196">Alapértelmezés szerint ez a mező az aktuális felhasználóhoz rendelt dolgozóra van beállítva.</span><span class="sxs-lookup"><span data-stu-id="b3940-196">By default, this field is set to the worker that is assigned to the current user.</span></span>
    - <span data-ttu-id="b3940-197">**Művelet óraszáma** – adja meg a kijelölt műveletben ledolgozott órák számát.</span><span class="sxs-lookup"><span data-stu-id="b3940-197">**Operation hours** – Enter the number of hours that were worked on the selected operation.</span></span>
    - <span data-ttu-id="b3940-198">**Számlázva** – akkor jelölje be ezt a jelölőnégyzetet, ha az időt kiszámlázták a vevőnek vagy szállítónak egy számlán.</span><span class="sxs-lookup"><span data-stu-id="b3940-198">**Invoiced** – Select this check box if the time has been charged to a customer or vendor on an invoice.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b3940-199">A költséget az **Általános** lap **Költség** mezőjében lehet megtekinteni. A költség kiszámítása a **Készletkezelési paraméterek** oldalon megadott díj alapján történik.</span><span class="sxs-lookup"><span data-stu-id="b3940-199">You can view the cost in the **Cost** field on the **General** tab. The cost is calculated by using the rate that you define on the **Inventory management parameters** page.</span></span>

1. <span data-ttu-id="b3940-200">Ismételje meg az előző lépést minden további hozzáadni kívánt időnyilvántartással.</span><span class="sxs-lookup"><span data-stu-id="b3940-200">Repeat the previous step for each additional timesheet line that you must add.</span></span>
1. <span data-ttu-id="b3940-201">Zárja be a lapokat.</span><span class="sxs-lookup"><span data-stu-id="b3940-201">Close the pages.</span></span>

> [!NOTE]
> <span data-ttu-id="b3940-202">A **Költség** mezőben található összeget a program automatikusan összegzi minden időnyilvántartási sorhoz, és hozzáadja a **Kapcsolódó műveletek** oldal **Költség** mezőjében található egyéb összegekhez.</span><span class="sxs-lookup"><span data-stu-id="b3940-202">The amount in the **Cost** field is summed for all timesheet lines and added to any other amounts in the **Cost** field on the **Related operations** page.</span></span>

## <a name="add-a-correction-to-a-nonconformance"></a><span data-ttu-id="b3940-203">Szabálytalanság javításának hozzáadása</span><span class="sxs-lookup"><span data-stu-id="b3940-203">Add a correction to a nonconformance</span></span>

<span data-ttu-id="b3940-204">Javítás szabálytalansághoz való hozzáadásához tegye a következőket.</span><span class="sxs-lookup"><span data-stu-id="b3940-204">To add a correction to a nonconformance, follow these steps.</span></span>

1. <span data-ttu-id="b3940-205">Ugorjon a **Készletkezelés \> Időszakos feladatok \> Minőségkezelés \> Szabálytalanságok** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b3940-205">Go to **Inventory management \> Periodic tasks \> Quality management \> Non conformances**.</span></span>
1. <span data-ttu-id="b3940-206">A listában keresse meg és válassza ki a frissíteni kívánt szabálytalanságot.</span><span class="sxs-lookup"><span data-stu-id="b3940-206">In the list, select the nonconformance that you want to update.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b3940-207">Javítást csak jóváhagyott szabálytalansághoz lehet hozzáadni.</span><span class="sxs-lookup"><span data-stu-id="b3940-207">You can add a correction only to nonconformances that are approved.</span></span>

1. <span data-ttu-id="b3940-208">Válassza a Művelet panelen a **Javítások** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b3940-208">On the Action Pane, select **Corrections**.</span></span>
1. <span data-ttu-id="b3940-209">A **Javítások** oldalon a Művelet panelen válassza az **Új** lehetőséget egy sor rácshoz való hozzáadásához.</span><span class="sxs-lookup"><span data-stu-id="b3940-209">On the **Corrections** page, on the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="b3940-210">Ezután új sorhoz állítsa be a következő mezőket:</span><span class="sxs-lookup"><span data-stu-id="b3940-210">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="b3940-211">**Diagnosztika** – a most létrehozott javítás típusát azonosító diagnosztikai típus kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="b3940-211">**Diagnostic** – Select the diagnostic type that identifies the type of correction that you're creating.</span></span>
    - <span data-ttu-id="b3940-212">**Dolgozó** – A javításért pénzügyileg felelős személy kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="b3940-212">**Worker** – Select the person who is responsible for the correction.</span></span>
    - <span data-ttu-id="b3940-213">**Javítás prioritása** – válassza ki az egyik lehetőséget annak jelzésére, hogy a javítás milyen prioritású legyen (*Alacsony*, *Normális* vagy *Magas*).</span><span class="sxs-lookup"><span data-stu-id="b3940-213">**Correction priority** – Select an option to indicate how the correction should be prioritized (*Low*, *Normal*, or *High*).</span></span>
    - <span data-ttu-id="b3940-214">**Kért dátum** – Adja meg a dátumot, amikor a helyesbítő műveletet igényelték.</span><span class="sxs-lookup"><span data-stu-id="b3940-214">**Requested date** – Enter the date when the corrective action was requested.</span></span>
    - <span data-ttu-id="b3940-215">**Tervezett dátum** – Adja meg a javítás várható befejezésének dátumát.</span><span class="sxs-lookup"><span data-stu-id="b3940-215">**Planned date** – Enter the date when the correction is expected to be completed.</span></span>
    - <span data-ttu-id="b3940-216">**Rövid távú megoldás** – akkor jelölje be ezt a jelölőnégyzetet, ha a javító művelet csak rövid időre javítja ki a szabálytalanságot.</span><span class="sxs-lookup"><span data-stu-id="b3940-216">**Short term solution** – Select this check box if the corrective action corrects the nonconformance only for a short time.</span></span>

1. <span data-ttu-id="b3940-217">Zárja be a lapokat.</span><span class="sxs-lookup"><span data-stu-id="b3940-217">Close the pages.</span></span>

## <a name="mark-a-correction-as-completed"></a><span data-ttu-id="b3940-218">Javítás megjelölése befejezettként</span><span class="sxs-lookup"><span data-stu-id="b3940-218">Mark a correction as completed</span></span>

<span data-ttu-id="b3940-219">Szabálytalanság javításának befejezettként való megjelöléséhez tegye a következőket.</span><span class="sxs-lookup"><span data-stu-id="b3940-219">To mark a nonconformance correction as completed, follow these steps.</span></span>

1. <span data-ttu-id="b3940-220">Ugorjon a **Készletkezelés \> Időszakos feladatok \> Minőségkezelés \> Szabálytalanságok** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b3940-220">Go to **Inventory management \> Periodic tasks \> Quality management \> Non conformances**.</span></span>
1. <span data-ttu-id="b3940-221">A listában keresse meg és válassza ki a frissíteni kívánt szabálytalanságot.</span><span class="sxs-lookup"><span data-stu-id="b3940-221">In the list, select the nonconformance that you want to update.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b3940-222">Javítást csak jóváhagyott szabálytalansághoz lehet hozzáadni.</span><span class="sxs-lookup"><span data-stu-id="b3940-222">You can add a correction only to nonconformances that are approved.</span></span>

1. <span data-ttu-id="b3940-223">Válassza a Művelet panelen a **Javítások** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b3940-223">On the Action Pane, select **Corrections**.</span></span>
1. <span data-ttu-id="b3940-224">A **Javítások** oldalon a rácson válassza ki a befejezettként megjelölni kívánt javítást.</span><span class="sxs-lookup"><span data-stu-id="b3940-224">On the **Corrections** page, in the grid, select the correction that you want to mark as completed.</span></span>
1. <span data-ttu-id="b3940-225">A Műveleti ablaktáblán válassza ki a **Megjelölés befejezettként** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b3940-225">On the Action Pane, select **Mark complete**.</span></span>
1. <span data-ttu-id="b3940-226">A rendszer felszólítja, hogy erősítse meg a kiválasztást.</span><span class="sxs-lookup"><span data-stu-id="b3940-226">You're prompted to confirm your selection.</span></span> <span data-ttu-id="b3940-227">A folytatáshoz válassza az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b3940-227">Select **OK** to continue.</span></span> <span data-ttu-id="b3940-228">A **Befejezés dátuma és időpontja** mező az aktuális dátumra és időpontra van állítva, és a **Befejezve** jelölőnégyzet be van jelölve.</span><span class="sxs-lookup"><span data-stu-id="b3940-228">The **Completion date and time** field is set to the current date and time, and the **Completed** check box is selected.</span></span>
1. <span data-ttu-id="b3940-229">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="b3940-229">Close the page.</span></span>

## <a name="reopen-a-completed-correction"></a><span data-ttu-id="b3940-230">Befejezett javítás újbóli megnyitása</span><span class="sxs-lookup"><span data-stu-id="b3940-230">Reopen a completed correction</span></span>

<span data-ttu-id="b3940-231">BEfejezett javítás újbóli megnyitásához tegye a következőket.</span><span class="sxs-lookup"><span data-stu-id="b3940-231">To reopen a completed correction, follow these steps.</span></span>

1. <span data-ttu-id="b3940-232">Ugorjon a **Készletkezelés \> Időszakos feladatok \> Minőségkezelés \> Szabálytalanságok** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b3940-232">Go to **Inventory management \> Periodic tasks \> Quality management \> Non conformances**.</span></span>
1. <span data-ttu-id="b3940-233">A listában keresse meg és válassza ki a frissíteni kívánt szabálytalanságot.</span><span class="sxs-lookup"><span data-stu-id="b3940-233">In the list, select the nonconformance that you want to update.</span></span>
1. <span data-ttu-id="b3940-234">Válassza a Művelet panelen a **Javítások** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b3940-234">On the Action pane, select **Corrections**.</span></span>
1. <span data-ttu-id="b3940-235">A **Javítások** oldalon a rácson válassza ki a javítást, amit újból meg szeretne nyitni.</span><span class="sxs-lookup"><span data-stu-id="b3940-235">On the **Corrections** page, in the grid, select the correction that you want to reopen.</span></span>
1. <span data-ttu-id="b3940-236">A Műveleti ablaktáblán kattintson az **Újranyitás** elemre.</span><span class="sxs-lookup"><span data-stu-id="b3940-236">On the Action Pane, select **Reopen**.</span></span>
1. <span data-ttu-id="b3940-237">A rendszer felszólítja, hogy erősítse meg a kiválasztást.</span><span class="sxs-lookup"><span data-stu-id="b3940-237">You're prompted to confirm your selection.</span></span> <span data-ttu-id="b3940-238">A folytatáshoz válassza az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b3940-238">Select **OK** to continue.</span></span> <span data-ttu-id="b3940-239">Az érték törlődik a **Befejezés dátuma és időpontja** mezőből, és a **Befejezve** jelölőnégyzetből is törli a jelölést.</span><span class="sxs-lookup"><span data-stu-id="b3940-239">The value is cleared from the **Completion date and time** field, and the **Completed** check box is cleared.</span></span>
1. <span data-ttu-id="b3940-240">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="b3940-240">Close the page.</span></span>

<span data-ttu-id="b3940-241">Most további módosításokat vagy frissítéseket lehet végezni a javításon.</span><span class="sxs-lookup"><span data-stu-id="b3940-241">You can now make additional edits or updates to the correction.</span></span> <span data-ttu-id="b3940-242">Ha végzett, a javítást újra befejezettként jelölheti meg.</span><span class="sxs-lookup"><span data-stu-id="b3940-242">When you've finished, you can mark the correction as completed again.</span></span>

## <a name="close-a-nonconformance"></a><span data-ttu-id="b3940-243">Szabálytalanság lezárása</span><span class="sxs-lookup"><span data-stu-id="b3940-243">Close a nonconformance</span></span>

<span data-ttu-id="b3940-244">Szabálytalanság bezárásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="b3940-244">To close a nonconformance, follow these steps.</span></span>

1. <span data-ttu-id="b3940-245">Ugorjon a **Készletkezelés \> Időszakos feladatok \> Minőségkezelés \> Minőségi rendelések** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b3940-245">Go to **Inventory management \> Periodic tasks \> Quality management \> Quality orders**.</span></span>
1. <span data-ttu-id="b3940-246">Válasszon egy minőségi rendelést a rácsban.</span><span class="sxs-lookup"><span data-stu-id="b3940-246">Select a quality order in the grid.</span></span>
1. <span data-ttu-id="b3940-247">A Műveleti ablaktáblán kattintson a **Lekérdezések \> Szabálytalanságok** elemre.</span><span class="sxs-lookup"><span data-stu-id="b3940-247">On the Action Pane, select **Inquiries \> Non conformances**.</span></span>
1. <span data-ttu-id="b3940-248">A **Szabálytalanságok** oldalon válassza ki a célként megadott szabálytalanságot a rácsban.</span><span class="sxs-lookup"><span data-stu-id="b3940-248">On the **Non conformances** page, select the target nonconformance in the grid.</span></span>
1. <span data-ttu-id="b3940-249">A Műveleti ablaktáblán kattintson a **Függvények \> Szabálytalanság bezárása** elemre.</span><span class="sxs-lookup"><span data-stu-id="b3940-249">On the Action Pane, select **Functions \> Close non conformance**.</span></span>
1. <span data-ttu-id="b3940-250">A rendszer felszólítja, hogy erősítse meg a kiválasztást.</span><span class="sxs-lookup"><span data-stu-id="b3940-250">You're prompted to confirm your selection.</span></span> <span data-ttu-id="b3940-251">A folytatáshoz kattintson az **Igen** gombra.</span><span class="sxs-lookup"><span data-stu-id="b3940-251">Select **Yes** to continue.</span></span>
1. <span data-ttu-id="b3940-252">Zárja be a lapokat.</span><span class="sxs-lookup"><span data-stu-id="b3940-252">Close the pages.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b3940-253">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="b3940-253">Additional resources</span></span>

- [<span data-ttu-id="b3940-254">Minőségkezelés áttekintése</span><span class="sxs-lookup"><span data-stu-id="b3940-254">Quality management overview</span></span>](../quality-management-processes.md)
- [<span data-ttu-id="b3940-255">A minőség- és a szabálytalanságkezelés engedélyezése</span><span class="sxs-lookup"><span data-stu-id="b3940-255">Enable quality and nonconformance management</span></span>](../enable-quality-management.md)
- [<span data-ttu-id="b3940-256">A szabálytalanságok jóváhagyásáért felelős dolgozók</span><span class="sxs-lookup"><span data-stu-id="b3940-256">Workers responsible for approving nonconformances</span></span>](../quality-responsible-workers.md)
- [<span data-ttu-id="b3940-257">A szabálytalanságok karanténzónái</span><span class="sxs-lookup"><span data-stu-id="b3940-257">Quarantine zones for nonconformances</span></span>](../quality-quarantine-zones.md)
- [<span data-ttu-id="b3940-258">A szabálytalanságok diagnosztikai típusai</span><span class="sxs-lookup"><span data-stu-id="b3940-258">Diagnostic types for nonconformances</span></span>](../quality-diagnostic-types.md)
- [<span data-ttu-id="b3940-259">Szabálytalanságok minőségi költségei</span><span class="sxs-lookup"><span data-stu-id="b3940-259">Quality charges for nonconformances</span></span>](../quality-charges.md)
- [<span data-ttu-id="b3940-260">Műveletek szabálytalanságokhoz kapcsolódóan</span><span class="sxs-lookup"><span data-stu-id="b3940-260">Operations for nonconformances</span></span>](../quality-operations.md)
- [<span data-ttu-id="b3940-261">Raktári folyamatok minőségkezelése</span><span class="sxs-lookup"><span data-stu-id="b3940-261">Quality management for warehouse processes</span></span>](../quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
