---
title: " Alapár- és kereskedelmi megállapodások"
description: Ez az eljárás bemutatja csatornaspecifikus eladási árra vonatkozó kereskedelmi megállapodások létrehozását.
author: josaw1
manager: AnnBe
ms.date: 08/12/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PriceDiscGroup, RetailStoreTable, RetailChannelPriceGroup, EcoResProductDetailsExtended, PriceDiscAdmTable, PriceDiscAdm
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8138b6144cc6ba09834f2bfb61cc7334767307d6
ms.sourcegitcommit: cbcf344b3b552acca56c3e27606eac7f2f124afe
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/22/2019
ms.locfileid: "1916553"
---
# <a name="base-price-and-trade-agreements"></a><span data-ttu-id="29356-103"> Alapár- és kereskedelmi megállapodások</span><span class="sxs-lookup"><span data-stu-id="29356-103">Base price and trade agreements</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="29356-104">Ez az eljárás bemutatja csatornaspecifikus eladási árra vonatkozó kereskedelmi megállapodások létrehozását.</span><span class="sxs-lookup"><span data-stu-id="29356-104">This procedure walks through creating channel-specific sales price trade agreements.</span></span> <span data-ttu-id="29356-105">Ez az eljárás az USRT bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="29356-105">This procedure uses the USRT demo data company.</span></span>

1. <span data-ttu-id="29356-106">A **navigációs ablakban**nyissa meg a **Modulok > Kiskereskedelem és kereskedelem > Árképzés és engedmények kezelése > Árcsoport > Összes árcsoport**.</span><span class="sxs-lookup"><span data-stu-id="29356-106">In the **Navigation pane**, go to **Modules > Retail and commerce > Pricing and discounts management > Price groups > All price groups**.</span></span> <span data-ttu-id="29356-107">Az árcsoportok megadják, hogyan történjen a kereskedelmi megállapodások társítása az egyes csatornákhoz.</span><span class="sxs-lookup"><span data-stu-id="29356-107">Price groups are how trade agreements are assigned to specific channels.</span></span> <span data-ttu-id="29356-108">Ha árcsoportokat használunk kereskedelmi megállapodások csatornához való társítására, lehetővé válik a csatornaspecifikus árazás.</span><span class="sxs-lookup"><span data-stu-id="29356-108">Using price groups to assign trade agreements to a channel enables channel-specific pricing.</span></span>  
2. <span data-ttu-id="29356-109">Kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="29356-109">Click **New**.</span></span>
3. <span data-ttu-id="29356-110">Írjon be egy értéket az **Árcsoportok** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="29356-110">In the **Price groups** field, type a value.</span></span>
4. <span data-ttu-id="29356-111">Írjon be egy értéket a **Név** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="29356-111">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="29356-112">Kattintson a **Mentés** gombra.</span><span class="sxs-lookup"><span data-stu-id="29356-112">Click **Save**.</span></span>
6. <span data-ttu-id="29356-113">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="29356-113">Close the page.</span></span>
7. <span data-ttu-id="29356-114">A **navigációs ablaktáblán** lépjen a **Modulok > Kiskereskedelem és kereskedelem > Csatornák > Kiskereskedelmi áruházak > Minden kiskereskedelmi üzlet** részhez.</span><span class="sxs-lookup"><span data-stu-id="29356-114">In the **Navigation pane**, go to **Modules > Retail and commerce > Channels > Retail stores > All retail stores**.</span></span>
8. <span data-ttu-id="29356-115">Válassza ki a listából a következőt: „New York”.</span><span class="sxs-lookup"><span data-stu-id="29356-115">In the list, select 'New York'</span></span>
9. <span data-ttu-id="29356-116">A Művelet panelen kattintson az **Üzlet** elemre.</span><span class="sxs-lookup"><span data-stu-id="29356-116">On the Action Pane, click **Store**.</span></span>
10. <span data-ttu-id="29356-117">Kattintson az **Árcsoportok** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="29356-117">Click **Price groups**.</span></span>
11. <span data-ttu-id="29356-118">Kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="29356-118">Click **New**.</span></span>
12. <span data-ttu-id="29356-119">Az **Árcsoportok** mezőben kattintson a legördülő gombra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="29356-119">In the **Price groups** field, click the drop-down button to open the lookup.</span></span>
13. <span data-ttu-id="29356-120">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="29356-120">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="29356-121">Kattintson a **Mentés** gombra.</span><span class="sxs-lookup"><span data-stu-id="29356-121">Click **Save**.</span></span>
15. <span data-ttu-id="29356-122">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="29356-122">Close the page.</span></span>
16. <span data-ttu-id="29356-123">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="29356-123">Close the page.</span></span>
17. <span data-ttu-id="29356-124">A **navigációs ablaktáblán** lépjen ide: **Modulok > Kiskereskedelmi és kereskedelem > Termékek és kategóriák > Kiadott termékek kategóriák szerint**.</span><span class="sxs-lookup"><span data-stu-id="29356-124">In the **Navigation pane**, go to **Modules > Retail and commerce > Products and categories > Released products by category**.</span></span>
18. <span data-ttu-id="29356-125">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="29356-125">In the list, click the link in the selected row.</span></span>
19. <span data-ttu-id="29356-126">Kattintson a **Szerkesztés** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="29356-126">Click **Edit**.</span></span>
20. <span data-ttu-id="29356-127">Bontsa ki az **Eladás** gyorslapot.</span><span class="sxs-lookup"><span data-stu-id="29356-127">Expand the **Sell** fastTab.</span></span>
21. <span data-ttu-id="29356-128">Adjon meg egy számot az **Ár** mezőben.</span><span class="sxs-lookup"><span data-stu-id="29356-128">In the **Price** field, enter a number.</span></span> <span data-ttu-id="29356-129">Ez az ár akkor használatos, ha nem található megfelelő kereskedelmi megállapodás.</span><span class="sxs-lookup"><span data-stu-id="29356-129">This price is used if no applicable trade agreements are found.</span></span>  
22. <span data-ttu-id="29356-130">Kattintson a **Mentés** gombra.</span><span class="sxs-lookup"><span data-stu-id="29356-130">Click **Save**.</span></span>
23. <span data-ttu-id="29356-131">A **Művelet panelen** kattintson az **Értékesítés** elemre.</span><span class="sxs-lookup"><span data-stu-id="29356-131">On the **Action Pane**, click **Sell**.</span></span>
24. <span data-ttu-id="29356-132">Kattintson a **Kereskedelmi megállapodások létrehozása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="29356-132">Click **Create trade agreements**.</span></span>
25. <span data-ttu-id="29356-133">Kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="29356-133">Click **New**.</span></span>
26. <span data-ttu-id="29356-134">A **Név** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="29356-134">In the **Name** field, click the drop-down button to open the lookup.</span></span>
27. <span data-ttu-id="29356-135">A listában válassza ki a következőt: „Kiskereskedelem”.</span><span class="sxs-lookup"><span data-stu-id="29356-135">In the list, select 'Retail'.</span></span> <span data-ttu-id="29356-136">A bemutató adatsorban a „Kiskereskedelem” naplónév a következő alapértelmezett objektumkapcsolattal rendelkezik: „Ár (eladási)”.</span><span class="sxs-lookup"><span data-stu-id="29356-136">In the demo data, the 'Retail' journal name has the default relation of 'Price (sales)'.</span></span> <span data-ttu-id="29356-137">Ez azt jelenti, hogy minden létrehozott új sor alapértelmezés szerint eladási árra vonatkozó kereskedelmi megállapodás lesz.</span><span class="sxs-lookup"><span data-stu-id="29356-137">That means all new lines created will default to sales price trade agreements.</span></span>  
28. <span data-ttu-id="29356-138">A **Művelet ablaktáblán** kattintson a **Sorok** elemre.</span><span class="sxs-lookup"><span data-stu-id="29356-138">On the **Action pane**, click **Lines**.</span></span>
29. <span data-ttu-id="29356-139">A **Számlakód** mezőben válassza ki a következőt: „Csoport”.</span><span class="sxs-lookup"><span data-stu-id="29356-139">In the **Account code** field, select 'Group'.</span></span>
30. <span data-ttu-id="29356-140">A **Fiókválasztás** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="29356-140">In the **Account selection** field, click the drop-down button to open the lookup.</span></span>
31. <span data-ttu-id="29356-141">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="29356-141">In the list, find and select the desired record.</span></span> <span data-ttu-id="29356-142">Ez befejezi a Csatorna és a Kereskedelmi megállapodás közötti, Árcsoport által közvetített hivatkozást.</span><span class="sxs-lookup"><span data-stu-id="29356-142">This will complete the link from Channel to Price group to Trade agreement.</span></span>  
32. <span data-ttu-id="29356-143">Írjon be egy értéket a **Cikk-kapcsolat** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="29356-143">In the **Item relation** field, type a value.</span></span>
33. <span data-ttu-id="29356-144">Az **Összeg devizában** mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="29356-144">In the **Amount in currency** field, enter a number.</span></span>
34. <span data-ttu-id="29356-145">A **Részletek** gyorslapon jelölje be a következő jelölőnégyzetet, vagy szüntesse meg a bejelölését: **Következő keresése**.</span><span class="sxs-lookup"><span data-stu-id="29356-145">In the **Details** fastTab, check or uncheck the **Find next** checkbox.</span></span> <span data-ttu-id="29356-146">Amennyiben a **Következő keresése** beállításnál az „Igen” van kiválasztva, az árképzési motor folytatja alacsonyabb eladási árra vonatkozó, megfelelő kereskedelmi megállapodások keresését.</span><span class="sxs-lookup"><span data-stu-id="29356-146">When **Find next** is set to 'Yes', the pricing engine will continue to search for applicable trade agreements with a lower sale price.</span></span> <span data-ttu-id="29356-147">Amennyiben a **Következő keresése** beállításnál a „Nem” van kiválasztva, az árképzési motor befejezi a keresést és a meglévő kereskedelmi megállapodást használja.</span><span class="sxs-lookup"><span data-stu-id="29356-147">When **Find next** is set to 'No', the price engine stops searching and uses the trade agreement.</span></span>  
35. <span data-ttu-id="29356-148">Kattintson a **Bejegyzés** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="29356-148">Click **Post**.</span></span>
36. <span data-ttu-id="29356-149">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="29356-149">Click **OK**.</span></span>
37. <span data-ttu-id="29356-150">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="29356-150">Close the page.</span></span>
38. <span data-ttu-id="29356-151">A **Művelet** panelen kattintson az Értékesítés elemre.</span><span class="sxs-lookup"><span data-stu-id="29356-151">On the **Action Pane**, click Sell.</span></span>
39. <span data-ttu-id="29356-152">Kattintson az **Eladási ár** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="29356-152">Click **Sales price**.</span></span>

