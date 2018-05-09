--- 
title: "Értékesítési ajánlatok tömeges létrehozása"
description: "Ez az eljárás bemutatja, hogyan lehet hatékonyan árajánlatokat létrehozni termékek és szolgáltatásokat ajánlva, amelyek több vevőnek lesznek elküldve."
author: omulvad
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: e3bc39912d19880258ff7dd56c74b77b52deda3a
ms.contentlocale: hu-hu
ms.lasthandoff: 05/08/2018

---
# <a name="mass-create-sales-quotations"></a><span data-ttu-id="b3828-103">Értékesítési ajánlatok tömeges létrehozása</span><span class="sxs-lookup"><span data-stu-id="b3828-103">Mass create sales quotations</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="b3828-104">Ez az eljárás bemutatja, hogyan lehet hatékonyan árajánlatokat létrehozni termékek és szolgáltatásokat ajánlva, amelyek több vevőnek lesznek elküldve.</span><span class="sxs-lookup"><span data-stu-id="b3828-104">This procedure demonstrates how to efficiently create quotations offering a set of products or services that are to be sent to multiple customers.</span></span> <span data-ttu-id="b3828-105">Ez a tömeges árajánlatlétrehozás árajánlatsablonokon alapul.</span><span class="sxs-lookup"><span data-stu-id="b3828-105">This mass quotation creation is based on quotation templates.</span></span> <span data-ttu-id="b3828-106">Ezt a folyamatot saját adatokkal, vagy az USMF bemutatócég adataival is futtathatja.</span><span class="sxs-lookup"><span data-stu-id="b3828-106">You can run this procedure on your own data or in demo data company USMF.</span></span>


## <a name="create-a-quotation-template"></a><span data-ttu-id="b3828-107">Árajánlatsablon létrehozása</span><span class="sxs-lookup"><span data-stu-id="b3828-107">Create a quotation template</span></span>
1. <span data-ttu-id="b3828-108">Lépjen az Értékesítés és marketing > Beállítás > Árajánlatok > sabloncsoportok menüpontba.</span><span class="sxs-lookup"><span data-stu-id="b3828-108">Go to Sales and marketing > Setup > Quotations > Template groups.</span></span>
2. <span data-ttu-id="b3828-109">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b3828-109">Click New.</span></span>
3. <span data-ttu-id="b3828-110">A Csoportazonosító mezőben adjon meg egy tetszés szerinti azonosítót.</span><span class="sxs-lookup"><span data-stu-id="b3828-110">In the Group ID field, type an ID of your choice.</span></span>
4. <span data-ttu-id="b3828-111">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="b3828-111">In the Description field, type a value.</span></span>
5. <span data-ttu-id="b3828-112">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="b3828-112">Click Save.</span></span>
6. <span data-ttu-id="b3828-113">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="b3828-113">Close the page.</span></span>
7. <span data-ttu-id="b3828-114">Lépjen az Értékesítés és marketing > Értékesítési árajánlatok > Minden árajánlat menüpontba.</span><span class="sxs-lookup"><span data-stu-id="b3828-114">Go to Sales and marketing > Sales quotations > All quotations.</span></span>
8. <span data-ttu-id="b3828-115">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b3828-115">Click New.</span></span>
9. <span data-ttu-id="b3828-116">A Számla típusa mezőben válassza a Vevő lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b3828-116">In the Account type field, select 'Customer'.</span></span>
10. <span data-ttu-id="b3828-117">A Vevőszámla mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="b3828-117">In the Customer account field, enter or select a value.</span></span>
11. <span data-ttu-id="b3828-118">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="b3828-118">Click OK.</span></span>
    * <span data-ttu-id="b3828-119">Ahhoz, hogy egy árajánlatból sablon legyen, el kell végezni bizonyos lépéseket az árajánlat fejlécében.</span><span class="sxs-lookup"><span data-stu-id="b3828-119">For a quotation to become a template you must carry out  setup steps on the quotation header.</span></span> <span data-ttu-id="b3828-120">Ezt az árajánlati sorok hozzáadása előtt kell elvégezni.</span><span class="sxs-lookup"><span data-stu-id="b3828-120">This must be done before you add lines to the quotation.</span></span>   
12. <span data-ttu-id="b3828-121">A Művelet ablaktáblában kattintson a Beállítások elemre.</span><span class="sxs-lookup"><span data-stu-id="b3828-121">On the Action Pane, click Options.</span></span>
13. <span data-ttu-id="b3828-122">Kattintson a Nézetváltás elemre.</span><span class="sxs-lookup"><span data-stu-id="b3828-122">Click Change view.</span></span>
14. <span data-ttu-id="b3828-123">Kattintson a Fejlécnézet gombra.</span><span class="sxs-lookup"><span data-stu-id="b3828-123">Click Header view.</span></span>
15. <span data-ttu-id="b3828-124">Bontsa ki a Beállítások szakaszt.</span><span class="sxs-lookup"><span data-stu-id="b3828-124">Expand the Setup section.</span></span>
16. <span data-ttu-id="b3828-125">A Csoportazonosító mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="b3828-125">In the Group ID field, enter or select a value.</span></span>
17. <span data-ttu-id="b3828-126">Írjon be egy értéket a Sablonnév mezőbe.</span><span class="sxs-lookup"><span data-stu-id="b3828-126">In the Template name field, type a value.</span></span>
18. <span data-ttu-id="b3828-127">Válassza ki az Igen lehetőséget az Aktív mezőben.</span><span class="sxs-lookup"><span data-stu-id="b3828-127">Select Yes in the Active field.</span></span>
    * <span data-ttu-id="b3828-128">Csak aktív sablonok használható, amikor egy sablont alkalmaz egy új értékesítési árajánlatra.</span><span class="sxs-lookup"><span data-stu-id="b3828-128">Only active templates can be used when you apply a template to a new sales quotation.</span></span>  
19. <span data-ttu-id="b3828-129">A Művelet ablaktáblában kattintson a Beállítások elemre.</span><span class="sxs-lookup"><span data-stu-id="b3828-129">On the Action Pane, click Options.</span></span>
20. <span data-ttu-id="b3828-130">Kattintson a Nézetváltás elemre.</span><span class="sxs-lookup"><span data-stu-id="b3828-130">Click Change view.</span></span>
21. <span data-ttu-id="b3828-131">Kattintson a Sor nézetre.</span><span class="sxs-lookup"><span data-stu-id="b3828-131">Click Line view.</span></span>
22. <span data-ttu-id="b3828-132">A Cikk mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="b3828-132">In the Item field, enter or select a value.</span></span>
23. <span data-ttu-id="b3828-133">Írjon be egy értéket a Cikk mezőbe.</span><span class="sxs-lookup"><span data-stu-id="b3828-133">In the Item field, type a value.</span></span>
24. <span data-ttu-id="b3828-134">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="b3828-134">Close the page.</span></span>
25. <span data-ttu-id="b3828-135">Adjon meg egy számot az Engedményszázalék mezőben.</span><span class="sxs-lookup"><span data-stu-id="b3828-135">In the Discount percent field, enter a number.</span></span>
26. <span data-ttu-id="b3828-136">Kattintson az Új sor hozzáadására.</span><span class="sxs-lookup"><span data-stu-id="b3828-136">Click Add line.</span></span>
27. <span data-ttu-id="b3828-137">A Cikk mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="b3828-137">In the Item field, enter or select a value.</span></span>
28. <span data-ttu-id="b3828-138">Írjon be egy értéket a Cikk mezőbe.</span><span class="sxs-lookup"><span data-stu-id="b3828-138">In the Item field, type a value.</span></span>
29. <span data-ttu-id="b3828-139">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="b3828-139">Close the page.</span></span>
30. <span data-ttu-id="b3828-140">Az Egységár mezőben adjon meg egy új árat, vagy módosítsa az aktuálisat.</span><span class="sxs-lookup"><span data-stu-id="b3828-140">In the Unit price field, enter a new price or change the current one.</span></span>
31. <span data-ttu-id="b3828-141">Kattintson az Új sor hozzáadására.</span><span class="sxs-lookup"><span data-stu-id="b3828-141">Click Add line.</span></span>
32. <span data-ttu-id="b3828-142">A Cikk mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="b3828-142">In the Item field, enter or select a value.</span></span>
33. <span data-ttu-id="b3828-143">Írjon be egy értéket a Cikk mezőbe.</span><span class="sxs-lookup"><span data-stu-id="b3828-143">In the Item field, type a value.</span></span>
34. <span data-ttu-id="b3828-144">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="b3828-144">Close the page.</span></span>
35. <span data-ttu-id="b3828-145">Adjon meg egy számot a Mennyiség mezőben.</span><span class="sxs-lookup"><span data-stu-id="b3828-145">In the Quantity field, enter a number.</span></span>
36. <span data-ttu-id="b3828-146">Adjon meg egy számot az Engedmény mezőben.</span><span class="sxs-lookup"><span data-stu-id="b3828-146">In the Discount field, enter a number.</span></span>
37. <span data-ttu-id="b3828-147">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="b3828-147">Click Save.</span></span>

## <a name="apply-the-template-to-create-a-single-quotation"></a><span data-ttu-id="b3828-148">Sablon alkalmazása egyetlen árajánlat létrehozásához</span><span class="sxs-lookup"><span data-stu-id="b3828-148">Apply the template to create a single quotation</span></span>
1. <span data-ttu-id="b3828-149">Lépjen az Értékesítés és marketing > Értékesítési árajánlatok > Minden árajánlat menüpontba.</span><span class="sxs-lookup"><span data-stu-id="b3828-149">Go to Sales and marketing > Sales quotations > All quotations.</span></span>
    * <span data-ttu-id="b3828-150">Vegye figyelembe, hogy az imént létrehozott ajánlat sablonként van megjelölve.</span><span class="sxs-lookup"><span data-stu-id="b3828-150">Note that the quotation you have just created is marked as template.</span></span>  
2. <span data-ttu-id="b3828-151">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b3828-151">Click New.</span></span>
3. <span data-ttu-id="b3828-152">A Számla típusa mezőben válassza a Vevő lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b3828-152">In the Account type field, select 'Customer'.</span></span>
4. <span data-ttu-id="b3828-153">A Vevőszámla mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="b3828-153">In the Customer account field, enter or select a value.</span></span>
5. <span data-ttu-id="b3828-154">Bontsa ki a Sablon szakaszt.</span><span class="sxs-lookup"><span data-stu-id="b3828-154">Expand the Template section.</span></span>
6. <span data-ttu-id="b3828-155">A Csoportazonosító mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="b3828-155">In the Group ID field, enter or select a value.</span></span>
7. <span data-ttu-id="b3828-156">A Sablonnév mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="b3828-156">In the Template name field, enter or select a value.</span></span>
8. <span data-ttu-id="b3828-157">A Számítási mód mezőben válassza ki a „Sablonértékek alapján” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b3828-157">In the Calculation method field, select 'Based on template values'.</span></span>
9. <span data-ttu-id="b3828-158">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="b3828-158">Click OK.</span></span>
    * <span data-ttu-id="b3828-159">Az új ajánlat létrehozása megtörtént, a sablon adatai és feltételei alapján.</span><span class="sxs-lookup"><span data-stu-id="b3828-159">The new quotation has now been created, based on the data and terms of the template.</span></span>  
10. <span data-ttu-id="b3828-160">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="b3828-160">Close the page.</span></span>
11. <span data-ttu-id="b3828-161">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="b3828-161">Close the page.</span></span>

## <a name="apply-the-template-to-mass-create-quotations"></a><span data-ttu-id="b3828-162">Sablon alkalmazása tömeges árajánlatlétrehozáshoz</span><span class="sxs-lookup"><span data-stu-id="b3828-162">Apply the template to mass create quotations</span></span>
1. <span data-ttu-id="b3828-163">Lépjen az Értékesítés és marketing > Értékesítési ajánlatok > Árajánlatfrissítés > Ajánlatok tömeges létrehozása menüpontba.</span><span class="sxs-lookup"><span data-stu-id="b3828-163">Go to Sales and marketing > Sales quotations > Quotation update > Mass create quotations.</span></span>
2. <span data-ttu-id="b3828-164">A Számla típusa mezőben válassza a Vevő lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b3828-164">In the Account type field, select 'Customer'.</span></span>
3. <span data-ttu-id="b3828-165">A Csoportazonosító mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="b3828-165">In the Group ID field, enter or select a value.</span></span>
4. <span data-ttu-id="b3828-166">A Sablonnév mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="b3828-166">In the Template name field, enter or select a value.</span></span>
5. <span data-ttu-id="b3828-167">A Számítási mód mezőben válassza ki a „Sablonértékek alapján” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b3828-167">In the Calculation method field, select 'Based on template values'.</span></span>
6. <span data-ttu-id="b3828-168">Bontsa ki a Szerepeltetni kívánt rekordok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="b3828-168">Expand the Records to include section.</span></span>
7. <span data-ttu-id="b3828-169">Kattintson a Szűrő parancsra.</span><span class="sxs-lookup"><span data-stu-id="b3828-169">Click Filter.</span></span>
8. <span data-ttu-id="b3828-170">A Feltétel mezőben állítsa a szűrőt úgy, hogy lefedje a vevők azon tartományát, amelyet bele akar foglalni ebbe a tömeges árajánlatlétrehozásba.</span><span class="sxs-lookup"><span data-stu-id="b3828-170">In the Criteria field, set the filter to cover a range of customers you want to include in this mass quotation creation.</span></span> <span data-ttu-id="b3828-171">A következő formátumot használja: "Customer1... CustomerN.</span><span class="sxs-lookup"><span data-stu-id="b3828-171">Use the following format "Customer1..CustomerN.</span></span>
    * <span data-ttu-id="b3828-172">Például beállítja a szűrést erre: US-001..US-004</span><span class="sxs-lookup"><span data-stu-id="b3828-172">For example, you could set the filter to: US-001..US-004</span></span>  
9. <span data-ttu-id="b3828-173">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="b3828-173">Click OK.</span></span>
10. <span data-ttu-id="b3828-174">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="b3828-174">Click OK.</span></span>
11. <span data-ttu-id="b3828-175">Lépjen az Értékesítés és marketing > Értékesítési árajánlatok > Minden árajánlat menüpontba.</span><span class="sxs-lookup"><span data-stu-id="b3828-175">Go to Sales and marketing > Sales quotations > All quotations.</span></span>
    * <span data-ttu-id="b3828-176">Győződjön meg róla, hogy az a kiválasztott sablonon alapján a tömeges frissítési rutinban megadott minden vevőhöz lett árajánlat létrehozva.</span><span class="sxs-lookup"><span data-stu-id="b3828-176">Verify that quotations have been created for all the customers specified in the mass update routine, as based on the selected template.</span></span>  


