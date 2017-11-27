--- 
title: "Cikkek fedezeti szabályainak meghatározása"
description: "Ez az eljárás az USMF bemutatócéget használja."
author: YuyuScheller
manager: AnnBe
ms.date: 11/02/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 76334f7ee4efe33df4a86aaa11a59748387cec89
ms.openlocfilehash: fe92393cc264df68f084db6974f7d4607d37d3ab
ms.contentlocale: hu-hu
ms.lasthandoff: 11/02/2017

---
# <a name="define-coverage-rules-for-items"></a><span data-ttu-id="e5090-103">Cikkek fedezeti szabályainak meghatározása</span><span class="sxs-lookup"><span data-stu-id="e5090-103">Define coverage rules for items</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e5090-104">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="e5090-104">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="e5090-105">Ez az eljárás bemutatja, hogyan tud fedezeti szabályokat létrehozni és egy adott cikk fedezeti beállításait felülírni.</span><span class="sxs-lookup"><span data-stu-id="e5090-105">This procedure shows how to create coverage rules and override coverage settings for a specific item.</span></span> <span data-ttu-id="e5090-106">Azt is bemutatja, hogyan kell megadni az alapértelmezett készletbeállításokat.</span><span class="sxs-lookup"><span data-stu-id="e5090-106">It also shows how to specify default inventory settings.</span></span>


## <a name="create-a-coverage-group"></a><span data-ttu-id="e5090-107">Fedezetcsoport létrehozása</span><span class="sxs-lookup"><span data-stu-id="e5090-107">Create a coverage group</span></span>
1. <span data-ttu-id="e5090-108">Ugrás a Fedezetcsoportokra.</span><span class="sxs-lookup"><span data-stu-id="e5090-108">Go to Coverage groups.</span></span>
2. <span data-ttu-id="e5090-109">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e5090-109">Click New.</span></span>
3. <span data-ttu-id="e5090-110">Írjon be egy értéket a Fedezeti csoport mezőbe.</span><span class="sxs-lookup"><span data-stu-id="e5090-110">In the Coverage group field, type a value.</span></span>
4. <span data-ttu-id="e5090-111">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="e5090-111">In the Name field, type a value.</span></span>
5. <span data-ttu-id="e5090-112">Írjon be egy értéket a Naptár mezőbe.</span><span class="sxs-lookup"><span data-stu-id="e5090-112">In the Calendar field, type a value.</span></span>
    * <span data-ttu-id="e5090-113">Válassza ki azt a naptárat, amely alapján az ebben a csoportban szereplő cikkek esetében az alaptervezés a feltöltési javaslatokat létrehozza.</span><span class="sxs-lookup"><span data-stu-id="e5090-113">Choose the calendar that master planning uses to create replenishment suggestions for items in this group.</span></span>  
6. <span data-ttu-id="e5090-114">A Fedezet kódja mezőben válasszon ki egy lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e5090-114">In the Coverage code field, select an option.</span></span>
    * <span data-ttu-id="e5090-115">Jelölje be az eljáráshoz szükséges követelményeket.</span><span class="sxs-lookup"><span data-stu-id="e5090-115">Select Requirement for this procedure.</span></span>  
7. <span data-ttu-id="e5090-116">A fedezet időkorlátja (napok) mezőben, írja be: '90'.</span><span class="sxs-lookup"><span data-stu-id="e5090-116">In the Coverage time fence (days) field, enter '90'.</span></span>
    * <span data-ttu-id="e5090-117">Az ebben a csoportban szereplő cikkek esetében az alaptervezés legfeljebb 90 napos jövőbeni időszakra szóló feltöltési javaslatokat hoz létre.</span><span class="sxs-lookup"><span data-stu-id="e5090-117">For items in this group, master planning will create replenishment suggestions for up to 90 days in the future.</span></span>  
8. <span data-ttu-id="e5090-118">A Negatív napok mezőbe írja be az „1” értéket.</span><span class="sxs-lookup"><span data-stu-id="e5090-118">In the Negative days field, enter '1'.</span></span>
9. <span data-ttu-id="e5090-119">A Pozitív napok mezőbe írja be az „1” értéket.</span><span class="sxs-lookup"><span data-stu-id="e5090-119">In the Positive days field, enter '1'.</span></span>
10. <span data-ttu-id="e5090-120">Bontsa ki vagy zárja be az Egyéb szakaszt.</span><span class="sxs-lookup"><span data-stu-id="e5090-120">Expand or collapse the Other section.</span></span>
11. <span data-ttu-id="e5090-121">A Követelmény dátumához hozzáadott bevételezési időtartalék mezőbe írja be az „1” értéket.</span><span class="sxs-lookup"><span data-stu-id="e5090-121">In the Receipt margin added to requirement date field, enter '1'.</span></span>
    * <span data-ttu-id="e5090-122">Ha például a bevételezési különbözet 1 napra van állítva, és a beszerzési rendelési sor május 15-re van bevételezésre ütemezve, az alapütemezés május 16-ra számítja ki a korrigált bevételezési dátumot.</span><span class="sxs-lookup"><span data-stu-id="e5090-122">For example, if the receipt margin is set to 1 day, and a purchase order line is scheduled for receipt on May 15, master planning calculates the adjusted receipt date as May 16.</span></span>  
12. <span data-ttu-id="e5090-123">A Követelmény dátumából levont kiadási időtartalék mezőbe írja be az „1” értéket.</span><span class="sxs-lookup"><span data-stu-id="e5090-123">In the Issue margin deducted from requirement date field, enter '1'.</span></span>
    * <span data-ttu-id="e5090-124">Ha például a kiadási különbözet 1 napra van állítva, és az értékesítési rendelési sor május 15-re van kiszállításra ütemezve, az alapütemezés május 14-re számítja ki a korrigált kiadási dátumot.</span><span class="sxs-lookup"><span data-stu-id="e5090-124">For example, if the safety margin is set to 1 day, and a sales order line is scheduled for delivery on May 15, master scheduling calculates the adjusted delivery date as May 14.</span></span>  
13. <span data-ttu-id="e5090-125">Az Újrarendelési időtartalék hozzáadva a cikkátfutási időhöz mezőbe írja be az „1” értéket.</span><span class="sxs-lookup"><span data-stu-id="e5090-125">In the Reorder margin added to item lead time field, enter '1'.</span></span>
14. <span data-ttu-id="e5090-126">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="e5090-126">Click Save.</span></span>

## <a name="create-a-new-product"></a><span data-ttu-id="e5090-127">Új termék létrehozása</span><span class="sxs-lookup"><span data-stu-id="e5090-127">Create a new product</span></span>
1. <span data-ttu-id="e5090-128">Ugrás a Kiadott termékek elemre.</span><span class="sxs-lookup"><span data-stu-id="e5090-128">Go to Released products.</span></span>
2. <span data-ttu-id="e5090-129">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e5090-129">Click New.</span></span>
3. <span data-ttu-id="e5090-130">Írjon be egy értéket a Termékszám mezőbe.</span><span class="sxs-lookup"><span data-stu-id="e5090-130">In the Product number field, type a value.</span></span>
4. <span data-ttu-id="e5090-131">Írjon be egy értéket a Terméknév mezőbe.</span><span class="sxs-lookup"><span data-stu-id="e5090-131">In the Product name field, type a value.</span></span>
5. <span data-ttu-id="e5090-132">A Cikkmodellcsoport mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="e5090-132">In the Item model group field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="e5090-133">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="e5090-133">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="e5090-134">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="e5090-134">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="e5090-135">A Cikkcsoport mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="e5090-135">In the Item group field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="e5090-136">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="e5090-136">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="e5090-137">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="e5090-137">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="e5090-138">A Tárolási dimenzió csoport mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="e5090-138">In the Storage dimension group field, click the drop-down button to open the lookup.</span></span>
12. <span data-ttu-id="e5090-139">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="e5090-139">In the list, find and select the desired record.</span></span>
13. <span data-ttu-id="e5090-140">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="e5090-140">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="e5090-141">A Nyomon követési dimenzió csoport mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="e5090-141">In the Tracking dimension group field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="e5090-142">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="e5090-142">In the list, find and select the desired record.</span></span>
16. <span data-ttu-id="e5090-143">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="e5090-143">In the list, click the link in the selected row.</span></span>
17. <span data-ttu-id="e5090-144">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="e5090-144">Click OK.</span></span>

## <a name="setup-default-order-settings"></a><span data-ttu-id="e5090-145">Alapértelmezett rendelésbeállítások beállítása</span><span class="sxs-lookup"><span data-stu-id="e5090-145">Setup default order settings</span></span>
1. <span data-ttu-id="e5090-146">A Művelet panelen kattintson a Terv elemre.</span><span class="sxs-lookup"><span data-stu-id="e5090-146">On the Action Pane, click Plan.</span></span>
2. <span data-ttu-id="e5090-147">Kattintson az Alapértelmezett rendelésbeállítások elemre.</span><span class="sxs-lookup"><span data-stu-id="e5090-147">Click Default order settings.</span></span>
3. <span data-ttu-id="e5090-148">A Beszerzési telephely mezőbe írja be azt a telephelyet, amelyet alapértelmezettként használtak a beszerzési rendelések létrehozásakor.</span><span class="sxs-lookup"><span data-stu-id="e5090-148">In the Purchase site field, type the site used as default when purchase orders are created.</span></span>
4. <span data-ttu-id="e5090-149">A Készletező hely mezőjébe írja be azt a helyet, ahol a cikket tárolják.</span><span class="sxs-lookup"><span data-stu-id="e5090-149">In the Inventory site field, type the site where the item is stored.</span></span>
5. <span data-ttu-id="e5090-150">Bontsa ki vagy csukja össze a Készlet szakaszt.</span><span class="sxs-lookup"><span data-stu-id="e5090-150">Expand or collapse the Inventory section.</span></span>
6. <span data-ttu-id="e5090-151">Adja meg a Több értékeként a „10”-et.</span><span class="sxs-lookup"><span data-stu-id="e5090-151">Set Multiple to '10'.</span></span>
7. <span data-ttu-id="e5090-152">Min.</span><span class="sxs-lookup"><span data-stu-id="e5090-152">Set Min.</span></span> <span data-ttu-id="e5090-153">rendelt mennyiség beállítása „10”-re.</span><span class="sxs-lookup"><span data-stu-id="e5090-153">order quantity to '10'.</span></span>
8. <span data-ttu-id="e5090-154">Maximális beállítása.</span><span class="sxs-lookup"><span data-stu-id="e5090-154">Set Max.</span></span> <span data-ttu-id="e5090-155">rendelt mennyiség beállítása „100”-re.</span><span class="sxs-lookup"><span data-stu-id="e5090-155">order quantity to '100'.</span></span>
9. <span data-ttu-id="e5090-156">Szokásos rendelési mennyiség beállítása „10”-re.</span><span class="sxs-lookup"><span data-stu-id="e5090-156">Set Standard order quantity to '10'.</span></span>
10. <span data-ttu-id="e5090-157">Adjon meg egy számot az Beszerzési átfutási idő mezőben.</span><span class="sxs-lookup"><span data-stu-id="e5090-157">In the Purchase lead time field, enter a number.</span></span>
11. <span data-ttu-id="e5090-158">Jelölje be törölje a Munkanapok jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="e5090-158">Select or clear the Working days check box.</span></span>
12. <span data-ttu-id="e5090-159">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="e5090-159">Click Save.</span></span>
13. <span data-ttu-id="e5090-160">Az Alapértelmezett rendeléstípus mezőben válassza ki a „Beszerzési rendelés” elemet.</span><span class="sxs-lookup"><span data-stu-id="e5090-160">In the Default order type field select 'Purchase order'.</span></span>
14. <span data-ttu-id="e5090-161">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="e5090-161">Click Save.</span></span>
15. <span data-ttu-id="e5090-162">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="e5090-162">Close the page.</span></span>
    * <span data-ttu-id="e5090-163">Zárja be az Alapértelmezett rendelésbeállítások oldalt.</span><span class="sxs-lookup"><span data-stu-id="e5090-163">Close the Default order settings page.</span></span>  

## <a name="add-an-item-to-a-coverage-group"></a><span data-ttu-id="e5090-164">Cikk felvétele egy fedezetcsoportba</span><span class="sxs-lookup"><span data-stu-id="e5090-164">Add an item to a coverage group</span></span>
1. <span data-ttu-id="e5090-165">Bontsa ki vagy zárja be a Terv szakaszt.</span><span class="sxs-lookup"><span data-stu-id="e5090-165">Expand or collapse the Plan section.</span></span>
2. <span data-ttu-id="e5090-166">A Fedezeti csoport mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="e5090-166">In the Coverage group field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="e5090-167">Keresse meg a létrehozott fedezeti csoportot a listában.</span><span class="sxs-lookup"><span data-stu-id="e5090-167">In the list, find the Coverage group you have created.</span></span>
4. <span data-ttu-id="e5090-168">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="e5090-168">In the list, click the link in the selected row.</span></span>

## <a name="create-item-coverage-rules"></a><span data-ttu-id="e5090-169">Cikkfedezet szabályainak létrehozása</span><span class="sxs-lookup"><span data-stu-id="e5090-169">Create item coverage rules</span></span>
1. <span data-ttu-id="e5090-170">A Művelet panelen kattintson a Terv elemre.</span><span class="sxs-lookup"><span data-stu-id="e5090-170">On the Action Pane, click Plan.</span></span>
2. <span data-ttu-id="e5090-171">Kattintson a cikkfedezet elemre.</span><span class="sxs-lookup"><span data-stu-id="e5090-171">Click Item coverage.</span></span>
3. <span data-ttu-id="e5090-172">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e5090-172">Click New.</span></span>
4. <span data-ttu-id="e5090-173">Kattintson az Általános fülre.</span><span class="sxs-lookup"><span data-stu-id="e5090-173">Click the General tab.</span></span>
5. <span data-ttu-id="e5090-174">Jelölje be a négyzetet a fejlécben a Fedezeticsoport-beállítások felülbírálatában.</span><span class="sxs-lookup"><span data-stu-id="e5090-174">Check the box on the header of Override coverage group settings.</span></span>
6. <span data-ttu-id="e5090-175">A fedezet időkorlátja (napok) mezőbe, írja be: '60'.</span><span class="sxs-lookup"><span data-stu-id="e5090-175">In the Coverage time fence (days) field, enter '60'.</span></span>
    * <span data-ttu-id="e5090-176">Annak ellenére, hogy a fedezeti csoport Követelményeket 90 nappal előre megtervezik, ezt a cikket 60 nappal előre fogják tervezni.</span><span class="sxs-lookup"><span data-stu-id="e5090-176">Although items in coverage group Requirement are planned 90 days ahead, this item will be planned 60 days ahead.</span></span>  
7. <span data-ttu-id="e5090-177">A Negatív napok mezőbe írja be a „2” értéket.</span><span class="sxs-lookup"><span data-stu-id="e5090-177">In the Negative days field, enter '2'.</span></span>
8. <span data-ttu-id="e5090-178">A Pozitív napok mezőbe írja be a „2” értéket.</span><span class="sxs-lookup"><span data-stu-id="e5090-178">In the Positive days field, enter '2'.</span></span>
9. <span data-ttu-id="e5090-179">Kattintson az Átfutási idő fülre.</span><span class="sxs-lookup"><span data-stu-id="e5090-179">Click the Lead time tab.</span></span>
10. <span data-ttu-id="e5090-180">Jelölje be a Vásárlás fejlécén lévő jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="e5090-180">Check the box on the header of Purchase.</span></span>
11. <span data-ttu-id="e5090-181">A Beszerzés ideje mezőbe írja be, hogy „5”.</span><span class="sxs-lookup"><span data-stu-id="e5090-181">In the Purchase time field, enter '5'.</span></span>
12. <span data-ttu-id="e5090-182">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="e5090-182">Click Save.</span></span>


