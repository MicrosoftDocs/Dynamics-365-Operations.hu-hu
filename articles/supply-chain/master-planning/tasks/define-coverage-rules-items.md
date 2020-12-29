---
title: Cikkek fedezeti szabályainak meghatározása
description: Ez az eljárás az USMF bemutatócéget használja.
author: ShylaThompson
manager: tfehr
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqGroup, DefaultDashboard, EcoResProductDetailsExtended, EcoResProductCreate, InventItemOrderSetup, ReqItemTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 11d92185bdbcf7aa1a668b6d2aa311805e42293c
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4429535"
---
# <a name="define-coverage-rules-for-items"></a><span data-ttu-id="62fd0-103">Cikkek fedezeti szabályainak meghatározása</span><span class="sxs-lookup"><span data-stu-id="62fd0-103">Define coverage rules for items</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="62fd0-104">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="62fd0-104">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="62fd0-105">Ez az eljárás bemutatja, hogyan tud fedezeti szabályokat létrehozni és egy adott cikk fedezeti beállításait felülírni.</span><span class="sxs-lookup"><span data-stu-id="62fd0-105">This procedure shows how to create coverage rules and override coverage settings for a specific item.</span></span> <span data-ttu-id="62fd0-106">Azt is bemutatja, hogyan kell megadni az alapértelmezett készletbeállításokat.</span><span class="sxs-lookup"><span data-stu-id="62fd0-106">It also shows how to specify default inventory settings.</span></span>


## <a name="create-a-coverage-group"></a><span data-ttu-id="62fd0-107">Fedezetcsoport létrehozása</span><span class="sxs-lookup"><span data-stu-id="62fd0-107">Create a coverage group</span></span>
1. <span data-ttu-id="62fd0-108">Nyissa meg a **Navigációs ablak > Modulok > alaptervezés > Beállítások> Fedezeti csoportok** elemet.</span><span class="sxs-lookup"><span data-stu-id="62fd0-108">Go to **Navigation pane > Modules > Master planning > Setup > Coverage groups**.</span></span>
2. <span data-ttu-id="62fd0-109">Kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="62fd0-109">Click **New**.</span></span>
3. <span data-ttu-id="62fd0-110">Írjon be egy értéket a **Fedezeti csoport** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="62fd0-110">In the **Coverage group** field, type a value.</span></span>
4. <span data-ttu-id="62fd0-111">Írjon be egy értéket a **Név** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="62fd0-111">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="62fd0-112">Írjon be egy értéket a **Naptár** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="62fd0-112">In the **Calendar** field, type a value.</span></span> <span data-ttu-id="62fd0-113">Válassza ki azt a naptárat, amely alapján az ebben a csoportban szereplő cikkek esetében az alaptervezés a feltöltési javaslatokat létrehozza.</span><span class="sxs-lookup"><span data-stu-id="62fd0-113">Choose the calendar that master planning uses to create replenishment suggestions for items in this group.</span></span>  
6. <span data-ttu-id="62fd0-114">A **Fedezet kódja** mezőben válasszon ki egy lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="62fd0-114">In the **Coverage code** field, select an option.</span></span> <span data-ttu-id="62fd0-115">Jelölje be az eljáráshoz szükséges „követelményeket”.</span><span class="sxs-lookup"><span data-stu-id="62fd0-115">Select 'Requirement' for this procedure.</span></span>  
7. <span data-ttu-id="62fd0-116">A **Fedezet időkorlátja (napok)** mezőben, írja be: '90'.</span><span class="sxs-lookup"><span data-stu-id="62fd0-116">In the **Coverage time fence (days) field**, enter '90'.</span></span> <span data-ttu-id="62fd0-117">Az ebben a csoportban szereplő cikkek esetében az alaptervezés legfeljebb 90 napos jövőbeni időszakra szóló feltöltési javaslatokat hoz létre.</span><span class="sxs-lookup"><span data-stu-id="62fd0-117">For items in this group, master planning will create replenishment suggestions for up to 90 days in the future.</span></span>  
8. <span data-ttu-id="62fd0-118">A **Negatív napok** mezőbe írja be az „1” értéket.</span><span class="sxs-lookup"><span data-stu-id="62fd0-118">In the **Negative days** field, enter '1'.</span></span>
9. <span data-ttu-id="62fd0-119">A **Pozitív napok** mezőbe írja be az „1” értéket.</span><span class="sxs-lookup"><span data-stu-id="62fd0-119">In the **Positive days** field, enter '1'.</span></span>
10. <span data-ttu-id="62fd0-120">Bontsa ki vagy zárja be az **Egyéb** szakaszt.</span><span class="sxs-lookup"><span data-stu-id="62fd0-120">Expand or collapse the **Other** section.</span></span>
11. <span data-ttu-id="62fd0-121">A **Biztonsági időtartalék napban** szakaszban a **Követelmény dátumához hozzáadott bevételezési időtartalék** mezőbe írja be az „1” értéket.</span><span class="sxs-lookup"><span data-stu-id="62fd0-121">Under the **Safety margins in days** section, in the **Receipt margin added to requirement date** field, enter '1'.</span></span> <span data-ttu-id="62fd0-122">Ha például a bevételezési különbözet 1 napra van állítva, és a beszerzési rendelési sor május 15-re van bevételezésre ütemezve, az alapütemezés május 16-ra számítja ki a korrigált bevételezési dátumot.</span><span class="sxs-lookup"><span data-stu-id="62fd0-122">For example, if the receipt margin is set to 1 day, and a purchase order line is scheduled for receipt on May 15, master planning calculates the adjusted receipt date as May 16.</span></span>  
12. <span data-ttu-id="62fd0-123">A **Követelmény dátumából levont kiadási időtartalék** mezőbe írja be az „1” értéket.</span><span class="sxs-lookup"><span data-stu-id="62fd0-123">In the **Issue margin deducted from requirement date** field, enter '1'.</span></span> <span data-ttu-id="62fd0-124">Ha például a kiadási különbözet 1 napra van állítva, és az értékesítési rendelési sor május 15-re van kiszállításra ütemezve, az alapütemezés május 14-re számítja ki a korrigált kiadási dátumot.</span><span class="sxs-lookup"><span data-stu-id="62fd0-124">For example, if the safety margin is set to 1 day, and a sales order line is scheduled for delivery on May 15, master scheduling calculates the adjusted delivery date as May 14.</span></span>  
13. <span data-ttu-id="62fd0-125">Az **Újrarendelési időtartalék hozzáadva a cikkátfutási időhöz** mezőbe írja be az „1” értéket.</span><span class="sxs-lookup"><span data-stu-id="62fd0-125">In the **Reorder margin added to item lead time** field, enter '1'.</span></span>
14. <span data-ttu-id="62fd0-126">Kattintson a **Mentés** gombra.</span><span class="sxs-lookup"><span data-stu-id="62fd0-126">Click **Save**.</span></span>

## <a name="create-a-new-product"></a><span data-ttu-id="62fd0-127">Új termék létrehozása</span><span class="sxs-lookup"><span data-stu-id="62fd0-127">Create a new product</span></span>
1. <span data-ttu-id="62fd0-128">Kattintson ide: **Navigációs ablaktábla > Modulok > Termékinformációk kezelése > Termékek > Kiadott termékek**.</span><span class="sxs-lookup"><span data-stu-id="62fd0-128">Go to **Navigation pane > Modules > Product information management > Products > Released products**.</span></span>
2. <span data-ttu-id="62fd0-129">Kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="62fd0-129">Click **New**.</span></span>
3. <span data-ttu-id="62fd0-130">Írjon be egy értéket a **Termékszám** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="62fd0-130">In the **Product number** field, type a value.</span></span>
4. <span data-ttu-id="62fd0-131">Írjon be egy értéket a **Terméknév** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="62fd0-131">In the **Product name** field, type a value.</span></span>
5. <span data-ttu-id="62fd0-132">A **Cikkmodellcsoport** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="62fd0-132">In the **Item model group** field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="62fd0-133">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="62fd0-133">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="62fd0-134">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="62fd0-134">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="62fd0-135">A **Cikkcsoport** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="62fd0-135">In the **Item group** field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="62fd0-136">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="62fd0-136">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="62fd0-137">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="62fd0-137">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="62fd0-138">A **Tárolási dimenzió csoport** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="62fd0-138">In the **Storage dimension group** field, click the drop-down button to open the lookup.</span></span>
12. <span data-ttu-id="62fd0-139">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="62fd0-139">In the list, find and select the desired record.</span></span>
13. <span data-ttu-id="62fd0-140">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="62fd0-140">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="62fd0-141">A **Nyomon követési dimenzió csoport** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="62fd0-141">In the **Tracking dimension group** field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="62fd0-142">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="62fd0-142">In the list, find and select the desired record.</span></span>
16. <span data-ttu-id="62fd0-143">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="62fd0-143">In the list, click the link in the selected row.</span></span>
17. <span data-ttu-id="62fd0-144">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="62fd0-144">Click **OK**.</span></span>

## <a name="setup-default-order-settings"></a><span data-ttu-id="62fd0-145">Alapértelmezett rendelésbeállítások beállítása</span><span class="sxs-lookup"><span data-stu-id="62fd0-145">Setup default order settings</span></span>
1. <span data-ttu-id="62fd0-146">A **Művelet panelen** kattintson a **Tervezés** elemre.</span><span class="sxs-lookup"><span data-stu-id="62fd0-146">On the **Action Pane**, click **Plan**.</span></span>
2. <span data-ttu-id="62fd0-147">Kattintson a **Rendelésbeállításai** alatta az **Alapértelmezett rendelés beállításai** elemre.</span><span class="sxs-lookup"><span data-stu-id="62fd0-147">Under **Order settings**, click **Default order settings**.</span></span>
3. <span data-ttu-id="62fd0-148">A **Beszerzési rendelés** alatta az **Alapértelmezett telephely** mezőbe írja be azt a telephelyet amelyet alapértelmezettként használtak a beszerzési rendelések létrehozásakor.</span><span class="sxs-lookup"><span data-stu-id="62fd0-148">Under **Purchase order**, in the **Default site** field, type the site used as default when purchase orders are created.</span></span>
4. <span data-ttu-id="62fd0-149">Az **Alapértelmezett raktár** mezőjébe írja be azt a helyet, ahol a cikket tárolják.</span><span class="sxs-lookup"><span data-stu-id="62fd0-149">In the **Default warehouse** field, type the site where the item is stored.</span></span>
5. <span data-ttu-id="62fd0-150">Bontsa ki vagy csukja össze a **Készlet** szakaszt.</span><span class="sxs-lookup"><span data-stu-id="62fd0-150">Expand or collapse the **Inventory** section.</span></span>
6. <span data-ttu-id="62fd0-151">A **Többszörös** mezőbe írja be 10 értéket.</span><span class="sxs-lookup"><span data-stu-id="62fd0-151">In the **Multiple** field, type '10'.</span></span>
7. <span data-ttu-id="62fd0-152">A **Minimális rendelési mennyiség** mezőbe írja be a „10” értéket.</span><span class="sxs-lookup"><span data-stu-id="62fd0-152">In the **Min. order quantity** field, type '10'.</span></span>
8. <span data-ttu-id="62fd0-153">A **Maximális rendelési mennyiség** mezőbe írja be a „100” értéket.</span><span class="sxs-lookup"><span data-stu-id="62fd0-153">In the **Max. order quantity** field, type '100'.</span></span>
9. <span data-ttu-id="62fd0-154">A **Standard rendelési mennyiség** mezőbe írja be a „10” értéket.</span><span class="sxs-lookup"><span data-stu-id="62fd0-154">In the **Standard order quantity**, type '10'.</span></span>
10. <span data-ttu-id="62fd0-155">Adjon meg egy számot az **Beszerzési átfutási idő** mezőben.</span><span class="sxs-lookup"><span data-stu-id="62fd0-155">In the **Purchase lead time** field, enter a number.</span></span>
11. <span data-ttu-id="62fd0-156">Jelölje be törölje a **Munkanapok** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="62fd0-156">Select or clear the **Working days** check box.</span></span>
12. <span data-ttu-id="62fd0-157">Kattintson a **Mentés** gombra.</span><span class="sxs-lookup"><span data-stu-id="62fd0-157">Click **Save**.</span></span>
13. <span data-ttu-id="62fd0-158">Az **Alapértelmezett rendeléstípus** mezőben válassza ki a „Beszerzési rendelés” elemet.</span><span class="sxs-lookup"><span data-stu-id="62fd0-158">In the **Default order type** field select 'Purchase order'.</span></span>
14. <span data-ttu-id="62fd0-159">Kattintson a **Mentés** gombra.</span><span class="sxs-lookup"><span data-stu-id="62fd0-159">Click **Save**.</span></span>
15. <span data-ttu-id="62fd0-160">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="62fd0-160">Close the page.</span></span> <span data-ttu-id="62fd0-161">Zárja be az Alapértelmezett rendelésbeállítások oldalt.</span><span class="sxs-lookup"><span data-stu-id="62fd0-161">Close the Default order settings page.</span></span>  

## <a name="add-an-item-to-a-coverage-group"></a><span data-ttu-id="62fd0-162">Cikk felvétele egy fedezetcsoportba</span><span class="sxs-lookup"><span data-stu-id="62fd0-162">Add an item to a coverage group</span></span>
1. <span data-ttu-id="62fd0-163">Bontsa ki vagy zárja be a **Terv** szakaszt.</span><span class="sxs-lookup"><span data-stu-id="62fd0-163">Expand or collapse the **Plan** section.</span></span>
2. <span data-ttu-id="62fd0-164">A **Fedezeti csoport** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="62fd0-164">In the **Coverage group** field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="62fd0-165">Keresse meg a létrehozott **Fedezeti csoportot** a listában.</span><span class="sxs-lookup"><span data-stu-id="62fd0-165">In the list, find the **Coverage group** you have created.</span></span>
4. <span data-ttu-id="62fd0-166">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="62fd0-166">In the list, click the link in the selected row.</span></span>

## <a name="create-item-coverage-rules"></a><span data-ttu-id="62fd0-167">Cikkfedezet szabályainak létrehozása</span><span class="sxs-lookup"><span data-stu-id="62fd0-167">Create item coverage rules</span></span>
1. <span data-ttu-id="62fd0-168">A **Művelet panelen** kattintson a **Tervezés** elemre.</span><span class="sxs-lookup"><span data-stu-id="62fd0-168">On the **Action Pane**, click **Plan**.</span></span>
2. <span data-ttu-id="62fd0-169">A **Fedezet** területen kattintson a **Cikkfedezeti** elemre.</span><span class="sxs-lookup"><span data-stu-id="62fd0-169">Under **Coverage**, click **Item coverage**.</span></span>
3. <span data-ttu-id="62fd0-170">Kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="62fd0-170">Click **New**.</span></span>
4. <span data-ttu-id="62fd0-171">Kattintson az **Általános** fülre.</span><span class="sxs-lookup"><span data-stu-id="62fd0-171">Click the **General** tab.</span></span>
5. <span data-ttu-id="62fd0-172">Jelölje be a négyzetet a fejlécben a **Fedezeticsoport** beállítások felülbírálatában.</span><span class="sxs-lookup"><span data-stu-id="62fd0-172">Check the box on the header of **Override coverage group** settings.</span></span>
6. <span data-ttu-id="62fd0-173">A **Fedezet időkorlátja (napok)** mezőbe, írja be: '60'.</span><span class="sxs-lookup"><span data-stu-id="62fd0-173">In the **Coverage time fence (days)** field, enter '60'.</span></span> <span data-ttu-id="62fd0-174">Annak ellenére, hogy a fedezeti csoport Követelményeket 90 nappal előre megtervezik, ezt a cikket 60 nappal előre fogják tervezni.</span><span class="sxs-lookup"><span data-stu-id="62fd0-174">Although items in coverage group Requiremen are planned 90 days ahead, this item will be planned 60 days ahead.</span></span>  
7. <span data-ttu-id="62fd0-175">A **Negatív napok** mezőbe írja be az „2” értéket.</span><span class="sxs-lookup"><span data-stu-id="62fd0-175">In the **Negative days** field, enter '2'.</span></span>
8. <span data-ttu-id="62fd0-176">A **Pozitív napok** mezőbe írja be az „2” értéket.</span><span class="sxs-lookup"><span data-stu-id="62fd0-176">In the **Positive days** field, enter '2'.</span></span>
9. <span data-ttu-id="62fd0-177">Kattintson az **Átfutási idő** fülre.</span><span class="sxs-lookup"><span data-stu-id="62fd0-177">Click the **Lead time** tab.</span></span>
10. <span data-ttu-id="62fd0-178">Jelölje be a **Vásárlás** fejlécén lévő jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="62fd0-178">Check the box on the header of **Purchase**.</span></span>
11. <span data-ttu-id="62fd0-179">A **Beszerzés ideje** mezőbe írja be, hogy „5”.</span><span class="sxs-lookup"><span data-stu-id="62fd0-179">In the **Purchase time** field, enter '5'.</span></span>
12. <span data-ttu-id="62fd0-180">Kattintson a **Mentés** gombra.</span><span class="sxs-lookup"><span data-stu-id="62fd0-180">Click **Save**.</span></span>

