---
title: Értékesítési ajánlatok tömeges létrehozása
description: Ez az eljárás bemutatja, hogyan lehet hatékonyan árajánlatokat létrehozni termékek és szolgáltatásokat ajánlva, amelyek több vevőnek lesznek elküldve.
author: omulvad
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesQuotationTemplateGroup, SalesQuotationListPage, SalesCreateQuotation, SalesQuotationTable, SysQueryForm, SalesQuickQuote
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 227ff0dd03f8917f4551ce08067ef26c6204b059
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/10/2020
ms.locfileid: "3980718"
---
# <a name="mass-create-sales-quotations"></a><span data-ttu-id="57341-103">Értékesítési ajánlatok tömeges létrehozása</span><span class="sxs-lookup"><span data-stu-id="57341-103">Mass create sales quotations</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="57341-104">Ez az eljárás bemutatja, hogyan lehet hatékonyan árajánlatokat létrehozni termékek és szolgáltatásokat ajánlva, amelyek több vevőnek lesznek elküldve.</span><span class="sxs-lookup"><span data-stu-id="57341-104">This procedure demonstrates how to efficiently create quotations offering a set of products or services that are to be sent to multiple customers.</span></span> <span data-ttu-id="57341-105">Ez a tömeges árajánlatlétrehozás árajánlatsablonokon alapul.</span><span class="sxs-lookup"><span data-stu-id="57341-105">This mass quotation creation is based on quotation templates.</span></span> <span data-ttu-id="57341-106">Ezt a folyamatot saját adatokkal, vagy az USMF bemutatócég adataival is futtathatja.</span><span class="sxs-lookup"><span data-stu-id="57341-106">You can run this procedure on your own data or in demo data company USMF.</span></span>


## <a name="create-a-quotation-template"></a><span data-ttu-id="57341-107">Árajánlatsablon létrehozása</span><span class="sxs-lookup"><span data-stu-id="57341-107">Create a quotation template</span></span>
1. <span data-ttu-id="57341-108">Lépjen az Értékesítés és marketing > Beállítás > Árajánlatok > sabloncsoportok menüpontba.</span><span class="sxs-lookup"><span data-stu-id="57341-108">Go to Sales and marketing > Setup > Quotations > Template groups.</span></span>
2. <span data-ttu-id="57341-109">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="57341-109">Click New.</span></span>
3. <span data-ttu-id="57341-110">A Csoportazonosító mezőben adjon meg egy tetszés szerinti azonosítót.</span><span class="sxs-lookup"><span data-stu-id="57341-110">In the Group ID field, type an ID of your choice.</span></span>
4. <span data-ttu-id="57341-111">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="57341-111">In the Description field, type a value.</span></span>
5. <span data-ttu-id="57341-112">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="57341-112">Click Save.</span></span>
6. <span data-ttu-id="57341-113">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="57341-113">Close the page.</span></span>
7. <span data-ttu-id="57341-114">Lépjen az Értékesítés és marketing > Értékesítési árajánlatok > Minden árajánlat menüpontba.</span><span class="sxs-lookup"><span data-stu-id="57341-114">Go to Sales and marketing > Sales quotations > All quotations.</span></span>
8. <span data-ttu-id="57341-115">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="57341-115">Click New.</span></span>
9. <span data-ttu-id="57341-116">A Számla típusa mezőben válassza a Vevő lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="57341-116">In the Account type field, select 'Customer'.</span></span>
10. <span data-ttu-id="57341-117">A Vevőszámla mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="57341-117">In the Customer account field, enter or select a value.</span></span>
11. <span data-ttu-id="57341-118">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="57341-118">Click OK.</span></span>
    * <span data-ttu-id="57341-119">Ahhoz, hogy egy árajánlatból sablon legyen, el kell végezni bizonyos lépéseket az árajánlat fejlécében.</span><span class="sxs-lookup"><span data-stu-id="57341-119">For a quotation to become a template you must carry out  setup steps on the quotation header.</span></span> <span data-ttu-id="57341-120">Ezt az árajánlati sorok hozzáadása előtt kell elvégezni.</span><span class="sxs-lookup"><span data-stu-id="57341-120">This must be done before you add lines to the quotation.</span></span>   
12. <span data-ttu-id="57341-121">A Művelet ablaktáblában kattintson a Beállítások elemre.</span><span class="sxs-lookup"><span data-stu-id="57341-121">On the Action Pane, click Options.</span></span>
13. <span data-ttu-id="57341-122">Kattintson a Nézetváltás elemre.</span><span class="sxs-lookup"><span data-stu-id="57341-122">Click Change view.</span></span>
14. <span data-ttu-id="57341-123">Kattintson a Fejlécnézet gombra.</span><span class="sxs-lookup"><span data-stu-id="57341-123">Click Header view.</span></span>
15. <span data-ttu-id="57341-124">Bontsa ki a Beállítások szakaszt.</span><span class="sxs-lookup"><span data-stu-id="57341-124">Expand the Setup section.</span></span>
16. <span data-ttu-id="57341-125">A Csoportazonosító mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="57341-125">In the Group ID field, enter or select a value.</span></span>
17. <span data-ttu-id="57341-126">Írjon be egy értéket a Sablonnév mezőbe.</span><span class="sxs-lookup"><span data-stu-id="57341-126">In the Template name field, type a value.</span></span>
18. <span data-ttu-id="57341-127">Válassza ki az Igen lehetőséget az Aktív mezőben.</span><span class="sxs-lookup"><span data-stu-id="57341-127">Select Yes in the Active field.</span></span>
    * <span data-ttu-id="57341-128">Csak aktív sablonok használható, amikor egy sablont alkalmaz egy új értékesítési árajánlatra.</span><span class="sxs-lookup"><span data-stu-id="57341-128">Only active templates can be used when you apply a template to a new sales quotation.</span></span>  
19. <span data-ttu-id="57341-129">A Művelet ablaktáblában kattintson a Beállítások elemre.</span><span class="sxs-lookup"><span data-stu-id="57341-129">On the Action Pane, click Options.</span></span>
20. <span data-ttu-id="57341-130">Kattintson a Nézetváltás elemre.</span><span class="sxs-lookup"><span data-stu-id="57341-130">Click Change view.</span></span>
21. <span data-ttu-id="57341-131">Kattintson a Sor nézetre.</span><span class="sxs-lookup"><span data-stu-id="57341-131">Click Line view.</span></span>
22. <span data-ttu-id="57341-132">A Cikk mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="57341-132">In the Item field, enter or select a value.</span></span>
23. <span data-ttu-id="57341-133">Írjon be egy értéket a Cikk mezőbe.</span><span class="sxs-lookup"><span data-stu-id="57341-133">In the Item field, type a value.</span></span>
24. <span data-ttu-id="57341-134">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="57341-134">Close the page.</span></span>
25. <span data-ttu-id="57341-135">Adjon meg egy számot az Engedményszázalék mezőben.</span><span class="sxs-lookup"><span data-stu-id="57341-135">In the Discount percent field, enter a number.</span></span>
26. <span data-ttu-id="57341-136">Kattintson az Új sor hozzáadására.</span><span class="sxs-lookup"><span data-stu-id="57341-136">Click Add line.</span></span>
27. <span data-ttu-id="57341-137">A Cikk mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="57341-137">In the Item field, enter or select a value.</span></span>
28. <span data-ttu-id="57341-138">Írjon be egy értéket a Cikk mezőbe.</span><span class="sxs-lookup"><span data-stu-id="57341-138">In the Item field, type a value.</span></span>
29. <span data-ttu-id="57341-139">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="57341-139">Close the page.</span></span>
30. <span data-ttu-id="57341-140">Az Egységár mezőben adjon meg egy új árat, vagy módosítsa az aktuálisat.</span><span class="sxs-lookup"><span data-stu-id="57341-140">In the Unit price field, enter a new price or change the current one.</span></span>
31. <span data-ttu-id="57341-141">Kattintson az Új sor hozzáadására.</span><span class="sxs-lookup"><span data-stu-id="57341-141">Click Add line.</span></span>
32. <span data-ttu-id="57341-142">A Cikk mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="57341-142">In the Item field, enter or select a value.</span></span>
33. <span data-ttu-id="57341-143">Írjon be egy értéket a Cikk mezőbe.</span><span class="sxs-lookup"><span data-stu-id="57341-143">In the Item field, type a value.</span></span>
34. <span data-ttu-id="57341-144">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="57341-144">Close the page.</span></span>
35. <span data-ttu-id="57341-145">Adjon meg egy számot a Mennyiség mezőben.</span><span class="sxs-lookup"><span data-stu-id="57341-145">In the Quantity field, enter a number.</span></span>
36. <span data-ttu-id="57341-146">Adjon meg egy számot az Engedmény mezőben.</span><span class="sxs-lookup"><span data-stu-id="57341-146">In the Discount field, enter a number.</span></span>
37. <span data-ttu-id="57341-147">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="57341-147">Click Save.</span></span>

## <a name="apply-the-template-to-create-a-single-quotation"></a><span data-ttu-id="57341-148">Sablon alkalmazása egyetlen árajánlat létrehozásához</span><span class="sxs-lookup"><span data-stu-id="57341-148">Apply the template to create a single quotation</span></span>
1. <span data-ttu-id="57341-149">Lépjen az Értékesítés és marketing > Értékesítési árajánlatok > Minden árajánlat menüpontba.</span><span class="sxs-lookup"><span data-stu-id="57341-149">Go to Sales and marketing > Sales quotations > All quotations.</span></span>
    * <span data-ttu-id="57341-150">Vegye figyelembe, hogy az imént létrehozott ajánlat sablonként van megjelölve.</span><span class="sxs-lookup"><span data-stu-id="57341-150">Note that the quotation you have just created is marked as template.</span></span>  
2. <span data-ttu-id="57341-151">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="57341-151">Click New.</span></span>
3. <span data-ttu-id="57341-152">A Számla típusa mezőben válassza a Vevő lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="57341-152">In the Account type field, select 'Customer'.</span></span>
4. <span data-ttu-id="57341-153">A Vevőszámla mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="57341-153">In the Customer account field, enter or select a value.</span></span>
5. <span data-ttu-id="57341-154">Bontsa ki a Sablon szakaszt.</span><span class="sxs-lookup"><span data-stu-id="57341-154">Expand the Template section.</span></span>
6. <span data-ttu-id="57341-155">A Csoportazonosító mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="57341-155">In the Group ID field, enter or select a value.</span></span>
7. <span data-ttu-id="57341-156">A Sablonnév mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="57341-156">In the Template name field, enter or select a value.</span></span>
8. <span data-ttu-id="57341-157">A Számítási mód mezőben válassza ki a „Sablonértékek alapján” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="57341-157">In the Calculation method field, select 'Based on template values'.</span></span>
9. <span data-ttu-id="57341-158">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="57341-158">Click OK.</span></span>
    * <span data-ttu-id="57341-159">Az új ajánlat létrehozása megtörtént, a sablon adatai és feltételei alapján.</span><span class="sxs-lookup"><span data-stu-id="57341-159">The new quotation has now been created, based on the data and terms of the template.</span></span>  
10. <span data-ttu-id="57341-160">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="57341-160">Close the page.</span></span>
11. <span data-ttu-id="57341-161">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="57341-161">Close the page.</span></span>

## <a name="apply-the-template-to-mass-create-quotations"></a><span data-ttu-id="57341-162">Sablon alkalmazása tömeges árajánlatlétrehozáshoz</span><span class="sxs-lookup"><span data-stu-id="57341-162">Apply the template to mass create quotations</span></span>
1. <span data-ttu-id="57341-163">Lépjen az Értékesítés és marketing > Értékesítési ajánlatok > Árajánlatfrissítés > Ajánlatok tömeges létrehozása menüpontba.</span><span class="sxs-lookup"><span data-stu-id="57341-163">Go to Sales and marketing > Sales quotations > Quotation update > Mass create quotations.</span></span>
2. <span data-ttu-id="57341-164">A Számla típusa mezőben válassza a Vevő lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="57341-164">In the Account type field, select 'Customer'.</span></span>
3. <span data-ttu-id="57341-165">A Csoportazonosító mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="57341-165">In the Group ID field, enter or select a value.</span></span>
4. <span data-ttu-id="57341-166">A Sablonnév mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="57341-166">In the Template name field, enter or select a value.</span></span>
5. <span data-ttu-id="57341-167">A Számítási mód mezőben válassza ki a „Sablonértékek alapján” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="57341-167">In the Calculation method field, select 'Based on template values'.</span></span>
6. <span data-ttu-id="57341-168">Bontsa ki a Szerepeltetni kívánt rekordok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="57341-168">Expand the Records to include section.</span></span>
7. <span data-ttu-id="57341-169">Kattintson a Szűrő parancsra.</span><span class="sxs-lookup"><span data-stu-id="57341-169">Click Filter.</span></span>
8. <span data-ttu-id="57341-170">A Feltétel mezőben állítsa a szűrőt úgy, hogy lefedje a vevők azon tartományát, amelyet bele akar foglalni ebbe a tömeges árajánlatlétrehozásba.</span><span class="sxs-lookup"><span data-stu-id="57341-170">In the Criteria field, set the filter to cover a range of customers you want to include in this mass quotation creation.</span></span> <span data-ttu-id="57341-171">A következő formátumot használja: "Customer1... CustomerN.</span><span class="sxs-lookup"><span data-stu-id="57341-171">Use the following format "Customer1..CustomerN.</span></span>
    * <span data-ttu-id="57341-172">Például beállítja a szűrést erre: US-001..US-004</span><span class="sxs-lookup"><span data-stu-id="57341-172">For example, you could set the filter to: US-001..US-004</span></span>  
9. <span data-ttu-id="57341-173">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="57341-173">Click OK.</span></span>
10. <span data-ttu-id="57341-174">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="57341-174">Click OK.</span></span>
11. <span data-ttu-id="57341-175">Lépjen az Értékesítés és marketing > Értékesítési árajánlatok > Minden árajánlat menüpontba.</span><span class="sxs-lookup"><span data-stu-id="57341-175">Go to Sales and marketing > Sales quotations > All quotations.</span></span>
    * <span data-ttu-id="57341-176">Győződjön meg róla, hogy az a kiválasztott sablonon alapján a tömeges frissítési rutinban megadott minden vevőhöz lett árajánlat létrehozva.</span><span class="sxs-lookup"><span data-stu-id="57341-176">Verify that quotations have been created for all the customers specified in the mass update routine, as based on the selected template.</span></span>  

