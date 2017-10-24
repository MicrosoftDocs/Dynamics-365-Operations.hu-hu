--- 
title: " Alapár- és kereskedelmi megállapodások"
description: "Ez az eljárás bemutatja csatornaspecifikus eladási árra vonatkozó kereskedelmi megállapodások létrehozását."
author: josaw1
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: d9692ce9ad282b76504588d8f796560c00773a8c
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="base-price-and-trade-agreements"></a><span data-ttu-id="918a0-103"> Alapár- és kereskedelmi megállapodások</span><span class="sxs-lookup"><span data-stu-id="918a0-103">Base price and trade agreements</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="918a0-104">Ez az eljárás bemutatja csatornaspecifikus eladási árra vonatkozó kereskedelmi megállapodások létrehozását.</span><span class="sxs-lookup"><span data-stu-id="918a0-104">This procedure walks through creating channel-specific sales price trade agreements.</span></span> <span data-ttu-id="918a0-105">Ez az eljárás az USRT bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="918a0-105">This procedure uses the USRT demo data company.</span></span>

1. <span data-ttu-id="918a0-106">Nyissa meg a következőt: Kiskereskedelem és kereskedelem > Árképzés és engedmények > Árcsoportok > Minden árcsoport.</span><span class="sxs-lookup"><span data-stu-id="918a0-106">Go to Retail and commerce > Pricing and discounts > Price groups > All price groups.</span></span>
    * <span data-ttu-id="918a0-107">Az árcsoportok megadják, hogyan történjen a kereskedelmi megállapodások társítása az egyes csatornákhoz.</span><span class="sxs-lookup"><span data-stu-id="918a0-107">Price groups are how trade agreements are assigned to specific channels.</span></span> <span data-ttu-id="918a0-108">Ha árcsoportokat használunk kereskedelmi megállapodások csatornához való társítására, lehetővé válik a csatornaspecifikus árazás.</span><span class="sxs-lookup"><span data-stu-id="918a0-108">Using price groups to assign trade agreements to a channel enables channel-specific pricing.</span></span>  
2. <span data-ttu-id="918a0-109">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="918a0-109">Click New.</span></span>
3. <span data-ttu-id="918a0-110">Írjon be egy értéket az Árcsoportok mezőbe.</span><span class="sxs-lookup"><span data-stu-id="918a0-110">In the Price groups field, type a value.</span></span>
4. <span data-ttu-id="918a0-111">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="918a0-111">In the Name field, type a value.</span></span>
5. <span data-ttu-id="918a0-112">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="918a0-112">Click Save.</span></span>
6. <span data-ttu-id="918a0-113">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="918a0-113">Close the page.</span></span>
7. <span data-ttu-id="918a0-114">Nyissa meg a következőt: Kiskereskedelem és kereskedelem > Csatornák > Kiskereskedelmi áruházak > Minden kiskereskedelmi üzlet.</span><span class="sxs-lookup"><span data-stu-id="918a0-114">Go to Retail and commerce > Channels > Retail stores > All retail stores.</span></span>
8. <span data-ttu-id="918a0-115">Válassza ki a listából a következőt: „New York”.</span><span class="sxs-lookup"><span data-stu-id="918a0-115">In the list, select 'New York'</span></span>
9. <span data-ttu-id="918a0-116">A Művelet panelen kattintson az Üzlet elemre.</span><span class="sxs-lookup"><span data-stu-id="918a0-116">On the Action Pane, click Store.</span></span>
10. <span data-ttu-id="918a0-117">Kattintson az Árcsoportok lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="918a0-117">Click Price groups.</span></span>
11. <span data-ttu-id="918a0-118">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="918a0-118">Click New.</span></span>
12. <span data-ttu-id="918a0-119">Az Árcsoportok mezőben kattintson a legördülő gombra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="918a0-119">In the Price groups field, click the drop-down button to open the lookup.</span></span>
13. <span data-ttu-id="918a0-120">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="918a0-120">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="918a0-121">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="918a0-121">Click Save.</span></span>
15. <span data-ttu-id="918a0-122">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="918a0-122">Close the page.</span></span>
16. <span data-ttu-id="918a0-123">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="918a0-123">Close the page.</span></span>
17. <span data-ttu-id="918a0-124">Nyissa meg a következőt: Kiskereskedelem és kereskedelem > Termékek és kategóriák > Felszabadított termékek kategóriák szerint.</span><span class="sxs-lookup"><span data-stu-id="918a0-124">Go to Retail and commerce > Products and categories > Released products by category.</span></span>
18. <span data-ttu-id="918a0-125">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="918a0-125">In the list, click the link in the selected row.</span></span>
19. <span data-ttu-id="918a0-126">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="918a0-126">Click Edit.</span></span>
20. <span data-ttu-id="918a0-127">Váltsa át az Eladás szakasz bővítését.</span><span class="sxs-lookup"><span data-stu-id="918a0-127">Toggle the expansion of the Sell section.</span></span>
21. <span data-ttu-id="918a0-128">Adjon meg egy számot az Ár mezőben.</span><span class="sxs-lookup"><span data-stu-id="918a0-128">In the Price field, enter a number.</span></span>
    * <span data-ttu-id="918a0-129">Ez az ár akkor használatos, ha nem található megfelelő kereskedelmi megállapodás.</span><span class="sxs-lookup"><span data-stu-id="918a0-129">This price is used if no applicable trade agreements are found.</span></span>  
22. <span data-ttu-id="918a0-130">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="918a0-130">Click Save.</span></span>
23. <span data-ttu-id="918a0-131">A Művelet panelen kattintson az Értékesítés elemre.</span><span class="sxs-lookup"><span data-stu-id="918a0-131">On the Action Pane, click Sell.</span></span>
24. <span data-ttu-id="918a0-132">Kattintson a Kereskedelmi megállapodások létrehozása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="918a0-132">Click Create trade agreements.</span></span>
25. <span data-ttu-id="918a0-133">Kattintson az Új elemre.</span><span class="sxs-lookup"><span data-stu-id="918a0-133">Click New.</span></span>
26. <span data-ttu-id="918a0-134">A Név mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="918a0-134">In the Name field, click the drop-down button to open the lookup.</span></span>
27. <span data-ttu-id="918a0-135">A listában válassza ki a következőt: „Kiskereskedelem”.</span><span class="sxs-lookup"><span data-stu-id="918a0-135">In the list, select 'Retail'.</span></span>
    * <span data-ttu-id="918a0-136">A bemutató adatsorban a „Kiskereskedelem” naplónév a következő alapértelmezett objektumkapcsolattal rendelkezik: „Ár (eladási)”.</span><span class="sxs-lookup"><span data-stu-id="918a0-136">In the demo data, the 'Retail' journal name has the default relation of 'Price (sales)'.</span></span> <span data-ttu-id="918a0-137">Ez azt jelenti, hogy minden létrehozott új sor alapértelmezés szerint eladási árra vonatkozó kereskedelmi megállapodás lesz.</span><span class="sxs-lookup"><span data-stu-id="918a0-137">That means all new lines created will default to sales price trade agreements.</span></span>  
28. <span data-ttu-id="918a0-138">Kattintson a Sorok pontra.</span><span class="sxs-lookup"><span data-stu-id="918a0-138">Click Lines.</span></span>
29. <span data-ttu-id="918a0-139">A Számlakód mezőben válassza ki a következőt: „Csoport”.</span><span class="sxs-lookup"><span data-stu-id="918a0-139">In the Account code field, select 'Group'.</span></span>
30. <span data-ttu-id="918a0-140">A Fiókválasztás mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="918a0-140">In the Account selection field, click the drop-down button to open the lookup.</span></span>
31. <span data-ttu-id="918a0-141">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="918a0-141">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="918a0-142">Ez befejezi a Csatorna és a Kereskedelmi megállapodás közötti, Árcsoport által közvetített hivatkozást.</span><span class="sxs-lookup"><span data-stu-id="918a0-142">This will complete the link from Channel to Price group to Trade agreement.</span></span>  
32. <span data-ttu-id="918a0-143">Írjon be egy értéket a Cikk-kapcsolat mezőbe.</span><span class="sxs-lookup"><span data-stu-id="918a0-143">In the Item relation field, type a value.</span></span>
33. <span data-ttu-id="918a0-144">Az Összeg devizában mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="918a0-144">In the Amount in currency field, enter a number.</span></span>
34. <span data-ttu-id="918a0-145">Jelölje be a Következő keresése jelölőnégyzetet, vagy törölje a jelölést.</span><span class="sxs-lookup"><span data-stu-id="918a0-145">Check or uncheck the Find next checkbox.</span></span>
    * <span data-ttu-id="918a0-146">Amennyiben a Következő keresése beállításnál az „Igen” van kiválasztva, az árképzési motor folytatja alacsonyabb eladási árra vonatkozó, megfelelő kereskedelmi megállapodások keresését.</span><span class="sxs-lookup"><span data-stu-id="918a0-146">When Find next is set to 'Yes', the pricing engine will continue to search for applicable trade agreements with a lower sale price.</span></span> <span data-ttu-id="918a0-147">Amennyiben a Következő keresése beállításnál a „Nem” van kiválasztva, az árképzési motor befejezi a keresést és a meglévő kereskedelmi megállapodást használja.</span><span class="sxs-lookup"><span data-stu-id="918a0-147">When Find next is set to 'No', the price engine stops searching and uses the trade agreement.</span></span>  
35. <span data-ttu-id="918a0-148">Kattintson a Feladás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="918a0-148">Click Post.</span></span>
36. <span data-ttu-id="918a0-149">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="918a0-149">Click OK.</span></span>
37. <span data-ttu-id="918a0-150">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="918a0-150">Close the page.</span></span>
38. <span data-ttu-id="918a0-151">A Művelet panelen kattintson az Értékesítés elemre.</span><span class="sxs-lookup"><span data-stu-id="918a0-151">On the Action Pane, click Sell.</span></span>
39. <span data-ttu-id="918a0-152">Kattintson az Eladási ár lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="918a0-152">Click Sales price.</span></span>

