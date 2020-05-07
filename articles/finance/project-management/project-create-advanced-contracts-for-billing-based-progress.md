---
title: Speciális szerződések létrehozása a folyamat alapján történő számlázáshoz
description: Ez a témakör azt mutatja be, hogyan lehet létrehozni projekt-szerződéseket, hogy a teljesített munka százaléka alapján számlákat lehessen generálni a vevők számára.
author: RadhikaRS
manager: AnnBe
ms.date: 03/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: v-radsh
ms.dyn365.ops.version: 7
ms.search.validFrom: 2019-01-15
ms.openlocfilehash: 90cae104d0abad909606ef6a0e0c45ed95e74de2
ms.sourcegitcommit: dfef2faf881b2db1bd0f016df36e2b838105312b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/22/2020
ms.locfileid: "3282829"
---
# <a name="create-advanced-contracts-for-billing-based-on-progress"></a><span data-ttu-id="9767d-103">Speciális szerződések létrehozása a folyamat alapján történő számlázáshoz</span><span class="sxs-lookup"><span data-stu-id="9767d-103">Create advanced contracts for billing based on progress</span></span>
[!include [banner](../includes/banner.md)]

<span data-ttu-id="9767d-104">Ez a témakör azt mutatja be, hogyan lehet létrehozni projekt-szerződéseket, hogy a teljesített munka százaléka alapján számlákat lehessen létrehozni a vevők számára.</span><span class="sxs-lookup"><span data-stu-id="9767d-104">This topic explains how to create project contracts so that you can create invoices for customers, based on a percentage of completed work.</span></span> <span data-ttu-id="9767d-105">A számlaösszegek kiszámítása automatikusan, a projekt keretén belül végzett munkához beállított költségvetési kategóriák alapján történik.</span><span class="sxs-lookup"><span data-stu-id="9767d-105">Invoice amounts are automatically calculated for the budget categories of work that you set up for a project.</span></span> <span data-ttu-id="9767d-106">A számlázási időszakokról a projektszerződés egyeztetésekor kell megállapodni a vevővel.</span><span class="sxs-lookup"><span data-stu-id="9767d-106">The invoice timing is set when you negotiate the project contract with the customer.</span></span>

<span data-ttu-id="9767d-107">A témakör eljárásaival hozhatja létre a szerződést, az ahhoz kapcsolódó projektet és a számlázási szabályokat, melyek alapján kiszámíthatja a projekthez megadott munka egyes költségvetési kategóriáira eső számlaösszegeket.</span><span class="sxs-lookup"><span data-stu-id="9767d-107">Use the procedures in this topic to set up a contract, an associated project, and the billing rules that calculate invoice amounts for the budget categories of work that you set up for the project.</span></span>

<span data-ttu-id="9767d-108">A szerződés és a projekt létrehozása után beállíthatja a projekt részletes adatait.</span><span class="sxs-lookup"><span data-stu-id="9767d-108">After you've created the contract and the project, you can set up the details of the project.</span></span> <span data-ttu-id="9767d-109">például meghatározhatja a tevékenységeket, és dolgozókat rendelhet a projekthez.</span><span class="sxs-lookup"><span data-stu-id="9767d-109">For example, you can define activities and assign workers to the project.</span></span>

## <a name="example"></a><span data-ttu-id="9767d-110">Példa</span><span class="sxs-lookup"><span data-stu-id="9767d-110">Example</span></span>

<span data-ttu-id="9767d-111">Ön egy szoftverfejlesztő cégnél dolgozik.</span><span class="sxs-lookup"><span data-stu-id="9767d-111">Your organization is a software development firm.</span></span> <span data-ttu-id="9767d-112">Megyegyezik a vevővel abban, hogy egy bérszámfejtési programcsomagot fejlesztenek számára 20 000 dollár (USD) értékben.</span><span class="sxs-lookup"><span data-stu-id="9767d-112">You agree to develop a payroll accounting package for a customer for a total fee of 20,000 US dollars (USD).</span></span> <span data-ttu-id="9767d-113">Az Ön cége vállalja, hogy a projekt meghatározott százalékainak teljesítésekor számlát állít ki a vevőnek.</span><span class="sxs-lookup"><span data-stu-id="9767d-113">Your organization agrees to invoice the customer as you complete specific percentages of the project.</span></span> <span data-ttu-id="9767d-114">A következő projektkategóriáka állítja be a munkához, hogy a számlázási folyamat során ezeket használhassa:</span><span class="sxs-lookup"><span data-stu-id="9767d-114">You set up the following project categories for the work, so that you can use them in the billing process:</span></span>

- <span data-ttu-id="9767d-115">Konzultáció</span><span class="sxs-lookup"><span data-stu-id="9767d-115">Consulting</span></span>
- <span data-ttu-id="9767d-116">Terv</span><span class="sxs-lookup"><span data-stu-id="9767d-116">Design</span></span>
- <span data-ttu-id="9767d-117">Telepítés</span><span class="sxs-lookup"><span data-stu-id="9767d-117">Installation</span></span>

<span data-ttu-id="9767d-118">Azt is be lehet állítani olyan számlázási szabályokat, amelyek alapján az egyes kategóriákban elvégzett projektmunka százaléka után járó számlaösszegek kiszámítása automatikusan történjen.</span><span class="sxs-lookup"><span data-stu-id="9767d-118">You also set up billing rules that automatically calculate the invoice amounts for the percentage of project work that is completed in each category.</span></span>

<span data-ttu-id="9767d-119">A projektkategóriák költségvetését a költségvetés-kezelő hozza létre.</span><span class="sxs-lookup"><span data-stu-id="9767d-119">The budget manager creates a budget for the project categories.</span></span> <span data-ttu-id="9767d-120">Az elvégzett munka mennyisége automatikusan kiszámítható mint a munka ténylegesen elvégzett százaléka a költségvetési összegekhez viszonyítva.</span><span class="sxs-lookup"><span data-stu-id="9767d-120">The amount of completed work is automatically calculated as a percentage of actual work in comparison to the budgeted amounts.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9767d-121">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="9767d-121">Prerequisites</span></span>

<span data-ttu-id="9767d-122">Számlázási szabályokat használó projekt létrehozása előtt be kell állítania a számlázási szabályokhoz tartozó számsorozatokat, valamint a folyamatalapú számlázások feladásához használt díjnaplót.</span><span class="sxs-lookup"><span data-stu-id="9767d-122">Before you create a project that uses billing rules, you must set up the number sequences for billing rules and a fee journal that is used to post progress billings.</span></span>

1. <span data-ttu-id="9767d-123">Nyissa meg a **Projektvezetés és könyvelés** \> **Beállítások** \> **Projektvezetési és könyvelési paraméterek** pontot.</span><span class="sxs-lookup"><span data-stu-id="9767d-123">Go to **Project management and accounting** \> **Setup** \> **Project management and accounting parameters**.</span></span>
2. <span data-ttu-id="9767d-124">A **Projektvezetési és könyvelési paraméterek** oldal **Számsorozatok** lapján állítsa be azt a számsorozatot, amelyet a számlázási szabályok létrehozásakor kíván használni.</span><span class="sxs-lookup"><span data-stu-id="9767d-124">On the **Project management and accounting parameters** page, on the **Number sequences** tab, set up the number sequence that you want to use when billing rules are created.</span></span>
3. <span data-ttu-id="9767d-125">Ugorjon a **Projektvezetés és könyvelés** \> **Naplók** \> **Díj** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9767d-125">Go to **Project management and accounting** \> **Journals** \> **Fee**.</span></span>
4. <span data-ttu-id="9767d-126">A **Díjnapló** oldalon válassza az **Új** lehetőséget, majd írja be a napló nevét.</span><span class="sxs-lookup"><span data-stu-id="9767d-126">On the **Fee journal** page, select **New**, and enter the journal name.</span></span>

## <a name="create-a-contract-for-progress-billings"></a><span data-ttu-id="9767d-127">Szerződés létrehozása a folyamatalapú számlázáshoz</span><span class="sxs-lookup"><span data-stu-id="9767d-127">Create a contract for progress billings</span></span>

<span data-ttu-id="9767d-128">Az alábbi eljárás segítségével projektszerződést hozhat létre rögzített árú projekthez.</span><span class="sxs-lookup"><span data-stu-id="9767d-128">Use this procedure to create a project contract for a fixed-price project.</span></span> <span data-ttu-id="9767d-129">Projektszámlát akkor hozhat létre, amikor a projekt során elvégzett munka elér egy bizonyos százalékot.</span><span class="sxs-lookup"><span data-stu-id="9767d-129">You create a project invoice when the work that is completed on the project reaches a specified percentage.</span></span>

1. <span data-ttu-id="9767d-130">Lépjen a **Projektvezetés és könyvelés** \> **Projektek** \> **Projektszerződések** menüpontba.</span><span class="sxs-lookup"><span data-stu-id="9767d-130">Go to **Project management and accounting** \> **Projects** \> **Project contracts**.</span></span>
2. <span data-ttu-id="9767d-131">A **Projektszerződések** oldalon válassza az **Új** elemet.</span><span class="sxs-lookup"><span data-stu-id="9767d-131">On the **Project contracts** page, select **New**.</span></span>
3. <span data-ttu-id="9767d-132">Az **Új projektszerződés** párbeszédpanelen a következő mezőket állíthatja be:</span><span class="sxs-lookup"><span data-stu-id="9767d-132">In the **New project contract** dialog box, set the following fields:</span></span>

    - <span data-ttu-id="9767d-133">**Név**</span><span class="sxs-lookup"><span data-stu-id="9767d-133">**Name**</span></span>
    - <span data-ttu-id="9767d-134">**Finanszírozás típusa**</span><span class="sxs-lookup"><span data-stu-id="9767d-134">**Funding type**</span></span>
    - <span data-ttu-id="9767d-135">**Finanszírozási forrás**</span><span class="sxs-lookup"><span data-stu-id="9767d-135">**Funding source**</span></span>
    - <span data-ttu-id="9767d-136">**Értékesítés pénzneme** – A rendszer alapértelmezés szerint ezt a pénznemet használja a projektszerződéshez társított vevői számlákhoz.</span><span class="sxs-lookup"><span data-stu-id="9767d-136">**Sales currency** – By default, this currency is used for customer invoices that are associated with the project contract.</span></span> <span data-ttu-id="9767d-137">az egyes vevői számlák értékesítési pénzneme ugyanakkor külön is módosítható.</span><span class="sxs-lookup"><span data-stu-id="9767d-137">However, you can change the sales currency on a specific customer invoice.</span></span>

4. <span data-ttu-id="9767d-138">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9767d-138">Select **OK**.</span></span> <span data-ttu-id="9767d-139">A program átmásolja az információt a **Projektszerződések** lap fejlécébe.</span><span class="sxs-lookup"><span data-stu-id="9767d-139">The information is copied to the header of the **Project contracts** page.</span></span>
5. <span data-ttu-id="9767d-140">Töltse ki a **Projektszerződések** oldalon a többi szükséges információt a projekthez.</span><span class="sxs-lookup"><span data-stu-id="9767d-140">On the **Project contracts** page, fill in the rest of the required information for the project.</span></span>

## <a name="create-a-project-for-progress-billings"></a><span data-ttu-id="9767d-141">Projekt létrehozása folyamatalapú számlázáshoz</span><span class="sxs-lookup"><span data-stu-id="9767d-141">Create a project for progress billings</span></span>

<span data-ttu-id="9767d-142">Az alábbi lépéseket követve hozhat létre projektet és alprojekteket egy adott projektszerződéshez kapcsolódóan.</span><span class="sxs-lookup"><span data-stu-id="9767d-142">Follow these steps to create a project and any subprojects that are associated with a project contract.</span></span>

1. <span data-ttu-id="9767d-143">Ugorjon a **Projektvezetés és könyvelés** \> **Projektek** \> **Minden projekt** pontra.</span><span class="sxs-lookup"><span data-stu-id="9767d-143">Go to **Project management and accounting** \> **Projects** \> **All projects**.</span></span>
2. <span data-ttu-id="9767d-144">A **Minden projekt** oldalon válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9767d-144">On the **All projects** page, select **New**.</span></span>
3. <span data-ttu-id="9767d-145">Az **Új projekt** párbeszédpanel **Projekt típusa** mezőjében válassza az **Idő és anyag** elemet.</span><span class="sxs-lookup"><span data-stu-id="9767d-145">In the **New project** dialog box, in the **Project type** field, select **Time and material**.</span></span>
4. <span data-ttu-id="9767d-146">Válasszon egy projektcsoportot.</span><span class="sxs-lookup"><span data-stu-id="9767d-146">Select a project group.</span></span> <span data-ttu-id="9767d-147">A projektcsoport határozza meg a csoporthoz rendelt projektek feladási információit.</span><span class="sxs-lookup"><span data-stu-id="9767d-147">A project group defines the posting information for the projects that are assigned to the group.</span></span>
5. <span data-ttu-id="9767d-148">Válassza a **Projekt létrehozása** elemet.</span><span class="sxs-lookup"><span data-stu-id="9767d-148">Select **Create project**.</span></span>
6. <span data-ttu-id="9767d-149">A projekt létrehozása után, állítsa a projektszakaszt **Folyamatban** értékre.</span><span class="sxs-lookup"><span data-stu-id="9767d-149">After the project is created, set the project stage to **In process**.</span></span>

## <a name="create-a-budget-for-a-project"></a><span data-ttu-id="9767d-150">A projekt költségvetésének létrehozása</span><span class="sxs-lookup"><span data-stu-id="9767d-150">Create a budget for a project</span></span>

<span data-ttu-id="9767d-151">A költségvetési kategóriák alapján automatikusan kiszámíthatók az egyes kategóriákban elvégzett munka százaléka után kiszámlázandó összegek.</span><span class="sxs-lookup"><span data-stu-id="9767d-151">Budget categories are used to automatically calculate the invoice amounts for the percentage of work that is completed for each category.</span></span> <span data-ttu-id="9767d-152">Hajtsa végre a következő lépéseket a becsült költségek költségvetési kategóriáinak létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="9767d-152">Follow these steps to create budget categories for the estimated costs.</span></span>

1. <span data-ttu-id="9767d-153">Ugorjon a **Projektvezetés és könyvelés** \> **Projektek** \> **Minden projekt** pontra.</span><span class="sxs-lookup"><span data-stu-id="9767d-153">Go to **Project management and accounting** \> **Projects** \> **All projects**.</span></span>
2. <span data-ttu-id="9767d-154">A **Minden projekt** lapon válassza ki a kívánt projektet, majd nyissa meg azt.</span><span class="sxs-lookup"><span data-stu-id="9767d-154">On the **All projects** page, select and open the project that you want.</span></span>
3. <span data-ttu-id="9767d-155">A **Projektek** lap műveleti panelén a **Terv** lapon a **Költségvetés** csoportban válassza ki a **Projektköltségvetés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9767d-155">On the **Projects** page, on the Action Pane, on the **Plan** tab, in the **Budget** group, select **Project budget**.</span></span>
4. <span data-ttu-id="9767d-156">A **Projektköltségvetés** oldalon adja meg a projekt egyes kategóriának becsült költségét.</span><span class="sxs-lookup"><span data-stu-id="9767d-156">On the **Project budget** page, enter an estimated cost for each category in the project.</span></span>

## <a name="create-billing-rules-for-progress-billings"></a><span data-ttu-id="9767d-157">Számlázási szabályok létrehozása a folyamatalapú számlázáshoz</span><span class="sxs-lookup"><span data-stu-id="9767d-157">Create billing rules for progress billings</span></span>

1. <span data-ttu-id="9767d-158">Lépjen a **Projektvezetés és könyvelés** \> **Projektek** \> **Projektszerződések** menüpontba.</span><span class="sxs-lookup"><span data-stu-id="9767d-158">Go to **Project management and accounting** \> **Projects** \> **Project contracts**.</span></span>
2. <span data-ttu-id="9767d-159">A **Projektszerződések** lapon válassza ki, majd nyisson meg egy projektszerződést.</span><span class="sxs-lookup"><span data-stu-id="9767d-159">On the **Project contracts** page, select and open a project contract.</span></span>
3. <span data-ttu-id="9767d-160">A projektszerződés lap **Számlázási szabályok** gyorslapján válassza a **Hozzáadás** elemet.</span><span class="sxs-lookup"><span data-stu-id="9767d-160">On the project contract page, on the **Billing rules** FastTab, select **Add**.</span></span>
4. <span data-ttu-id="9767d-161">A **Számlázási szabály** oldal **Sor típusa** mezőjében válassza a **Folyamat** elemet.</span><span class="sxs-lookup"><span data-stu-id="9767d-161">On the **Billing rule** page, in the **Line type** field, select **Progress**.</span></span>
5. <span data-ttu-id="9767d-162">Adja meg a szerződés teljes értékét a **Számlázási szabály sorának részletes adatai gyorslap** **Szerződéses értéke** mezőjében adja meg.</span><span class="sxs-lookup"><span data-stu-id="9767d-162">On the **Billing rule line details** FastTab, in the **Contract value** field, enter the total value of the contract.</span></span>
6. <span data-ttu-id="9767d-163">A **Kategória** mezőben válassza ki a kategóriát a díjtranzakció feladásához.</span><span class="sxs-lookup"><span data-stu-id="9767d-163">In the **Category** field, select the category to post the fee transaction to.</span></span>
7. <span data-ttu-id="9767d-164">A **Projekt** mezőben válassza ki azt a projektet vagy feladatot, amely ezt a számlázási szabályt használja.</span><span class="sxs-lookup"><span data-stu-id="9767d-164">In the **Project** field, select the project that uses this billing rule.</span></span>
8. <span data-ttu-id="9767d-165">Opcionális: A számlázási szabályt további projektekhez is hozzárendelheti.</span><span class="sxs-lookup"><span data-stu-id="9767d-165">Optional: Assign the billing rule to additional projects.</span></span> <span data-ttu-id="9767d-166">Jelöljön ki egy projektet a **Projekt** gyorslapon a **Rendelkezésre álló projektek** szakaszban, majd válassza a jobbra mutató nyilat, és adja hozzá a projektet a **Kiválasztott projektek** szakaszhoz.</span><span class="sxs-lookup"><span data-stu-id="9767d-166">On the **Project** FastTab, in the **Available projects** section, select a project, and then select the right arrow button to add the project to the **Selected projects** section.</span></span>
9. <span data-ttu-id="9767d-167">Opcionális: Számítsa ki a százalékos értéket, amelyet a vevő visszatart egy számla kifizetésénél.</span><span class="sxs-lookup"><span data-stu-id="9767d-167">Optional: Calculate the percentage amount that the customer withholds from payments on an invoice.</span></span> <span data-ttu-id="9767d-168">A **Fizetés-visszatartási feltételek** gyorslapon válassza ki a finanszírozási forrást, majd a **Visszatartás százaléka** mezőben adja meg a visszatartási százalékot.</span><span class="sxs-lookup"><span data-stu-id="9767d-168">On the **Payment retention terms** FastTab, select the funding source, and then, in the **Retention percentage** field, enter the retention percentage.</span></span>
10. <span data-ttu-id="9767d-169">Ismételje meg ezeket a lépéseket a projektszerződés további számlázási szabályainak létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="9767d-169">Repeat these steps to create additional billing rules for the project contract.</span></span>
