---
title: Raktár beállítása
description: Ez a témakör azt mutatja be, hogyan lehet beállítani a raktárakat új csatornával való használathoz a Microsoft Dynamics 365 Commerce szolgáltatásban.
author: samjarawan
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 154ec719e16e4826b0e24deb5ecadf587d938e3c
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5800495"
---
# <a name="warehouse-set-up"></a><span data-ttu-id="8de1a-103">Raktár beállítása</span><span class="sxs-lookup"><span data-stu-id="8de1a-103">Warehouse set up</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="8de1a-104">Ez a témakör azt mutatja be, hogyan lehet beállítani a raktárakat új csatornával való használathoz a Microsoft Dynamics 365 Commerce szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="8de1a-104">This topic describes how to set up a warehouse to be used with a new channel in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="8de1a-105">Minden egyes Commerce-csatornához hozzá kell rendelni egy konfigurált raktárat.</span><span class="sxs-lookup"><span data-stu-id="8de1a-105">Each Commerce channel requires a configured warehouse to be associated with it.</span></span> <span data-ttu-id="8de1a-106">A következő eljárások a Commerce csatorna raktárának beállításához szükséges minimális konfigurációját nyújtják.</span><span class="sxs-lookup"><span data-stu-id="8de1a-106">The following procedures provide the minimum configuration required to set up a warehouse for a Commerce channel.</span></span> <span data-ttu-id="8de1a-107">A raktár beállításaival kapcsolatos további tudnivalókat lásd a [Raktárkezelés – áttekintés](../supply-chain/warehousing/warehouse-management-overview.md?toc=/dynamics365/commerce/toc.json) című témakörben.</span><span class="sxs-lookup"><span data-stu-id="8de1a-107">For more information regarding warehouse setup, please see the [Warehouse management overview](../supply-chain/warehousing/warehouse-management-overview.md?toc=/dynamics365/commerce/toc.json).</span></span>

## <a name="configure-a-warehouse-site"></a><span data-ttu-id="8de1a-108">Raktár webhelyének konfigurálása</span><span class="sxs-lookup"><span data-stu-id="8de1a-108">Configure a warehouse site</span></span>

<span data-ttu-id="8de1a-109">A raktár beállítása előtt konfigurálnia kell egy raktári webhelyet.</span><span class="sxs-lookup"><span data-stu-id="8de1a-109">Before setting up a warehouse, you need to configure a warehouse site.</span></span>

<span data-ttu-id="8de1a-110">A raktári webhely konfigurálásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="8de1a-110">To configure a warehouse site, follow these steps.</span></span>

1. <span data-ttu-id="8de1a-111">A navigációs ablaktáblán lépjen a **Modulok \> Kiskereskedelem és kereskedelem \> Csatornák beállítása \> Webhelyek** részhez.</span><span class="sxs-lookup"><span data-stu-id="8de1a-111">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Sites**.</span></span>
1. <span data-ttu-id="8de1a-112">A műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="8de1a-112">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="8de1a-113">A **Webhely** mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="8de1a-113">In the **Site** field, enter a value.</span></span>
1. <span data-ttu-id="8de1a-114">A **Név** mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="8de1a-114">In the **Name** field, enter a value.</span></span>
1. <span data-ttu-id="8de1a-115">Az **Általános** szakaszban adja meg a megfelelő **időzónát**.</span><span class="sxs-lookup"><span data-stu-id="8de1a-115">In the **General** section, set the appropriate **Time zone**.</span></span>
1. <span data-ttu-id="8de1a-116">A **Címek** szakaszban adjon meg egy címet.</span><span class="sxs-lookup"><span data-stu-id="8de1a-116">In the **Addresses** section, enter an address.</span></span>
1. <span data-ttu-id="8de1a-117">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8de1a-117">On the action pane, select **Save**.</span></span>

<span data-ttu-id="8de1a-118">A következő kép egy példát mutat a raktárwebhelyre.</span><span class="sxs-lookup"><span data-stu-id="8de1a-118">The following image shows an example warehouse site.</span></span>

![Példa: raktárwebhely](media/warehouse-site.png)

## <a name="set-up-a-warehouse"></a><span data-ttu-id="8de1a-120">Raktár beállítása</span><span class="sxs-lookup"><span data-stu-id="8de1a-120">Set up a warehouse</span></span>

<span data-ttu-id="8de1a-121">Raktár beállításához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="8de1a-121">To set up a warehouse, follow these steps.</span></span>

1. <span data-ttu-id="8de1a-122">A navigációs ablaktáblán lépjen a **Modulok \> Kiskereskedelem és kereskedelem \> Csatornák beállítása \> Raktárak** részhez.</span><span class="sxs-lookup"><span data-stu-id="8de1a-122">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Warehouses**.</span></span>
1. <span data-ttu-id="8de1a-123">A műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="8de1a-123">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="8de1a-124">A **Raktár** mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="8de1a-124">In the **Warehouse** field, enter a value.</span></span>  <span data-ttu-id="8de1a-125">Ha ez egy 1:1 hozzárendelés egy üzlethez, vegye fontolóra az üzlet nevének vagy egy területi elosztó központ nevének használatát.</span><span class="sxs-lookup"><span data-stu-id="8de1a-125">If this is a 1:1 mapping to a store, consider using the store name or the name of a regional distribution center.</span></span>
1. <span data-ttu-id="8de1a-126">A **Név** mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="8de1a-126">In the **Name** field, enter a value.</span></span>
1. <span data-ttu-id="8de1a-127">A **webhely** legördülő listában válassza ki a korábban létrehozott raktári webhelyet.</span><span class="sxs-lookup"><span data-stu-id="8de1a-127">In the **Site** drop-down list, select the warehouse site created previously.</span></span>
1. <span data-ttu-id="8de1a-128">A **Típus** mezőben válassza ki az **Alapértelmezett** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8de1a-128">In the **Type** field, select **Default**.</span></span>
    - <span data-ttu-id="8de1a-129">Ha meg kívánja adni a **karanténraktárat**, akkor az alábbi lépések követésével hozzon létre egy olyan további raktárat, amelyben a **Típus** legyen **Karantén**.</span><span class="sxs-lookup"><span data-stu-id="8de1a-129">If you want to set a **Quarantine warehouse**, first you'll need to follow these steps to create an additional warehouse where the **Type** is set to **Quarantine**.</span></span>
    - <span data-ttu-id="8de1a-130">Ha meg kívánja adni a **Tranzitraktárat**, akkor az alábbi lépések követésével hozzon létre egy olyan további raktárat, amelyben a **Típus** legyen **Tranzit**.</span><span class="sxs-lookup"><span data-stu-id="8de1a-130">If you want to set a **Transit warehouse**, first you'll need to follow these steps to create an additional warehouse where the **Type** is set to **Transit**.</span></span>
1. <span data-ttu-id="8de1a-131">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8de1a-131">On the action pane, select **Save**.</span></span>

## <a name="set-up-inventory-aisles"></a><span data-ttu-id="8de1a-132">Raktárfolyosók beállítása</span><span class="sxs-lookup"><span data-stu-id="8de1a-132">Set up inventory aisles</span></span>

<span data-ttu-id="8de1a-133">A készletfolyosók beállításához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="8de1a-133">To set up inventory aisles, follow these steps.</span></span>

1. <span data-ttu-id="8de1a-134">A navigációs ablaktáblán lépjen a **Modulok \> Kiskereskedelem és kereskedelem \> Csatornák beállítása \> Hely beállítása \> Készletfolyosók** részhez.</span><span class="sxs-lookup"><span data-stu-id="8de1a-134">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Location setup \> Inventory aisles**.</span></span>
1. <span data-ttu-id="8de1a-135">A műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="8de1a-135">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="8de1a-136">A **Raktár** legördülő listában válassza ki a korábban létrehozott raktárat.</span><span class="sxs-lookup"><span data-stu-id="8de1a-136">In the **Warehouse** drop-down list, select the warehouse created previously.</span></span>
1. <span data-ttu-id="8de1a-137">A **Folyosó** mezőben adjon meg egy nevet (például „Def”).</span><span class="sxs-lookup"><span data-stu-id="8de1a-137">In the **Aisle** field, enter a name (for example, "Def").</span></span>
1. <span data-ttu-id="8de1a-138">A **Név** mezőben adjon meg egy nevet (például „Alapértelmezett folyosó”).</span><span class="sxs-lookup"><span data-stu-id="8de1a-138">In the **Name** field, enter a name (for example, "Default aisle").</span></span>
1. <span data-ttu-id="8de1a-139">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8de1a-139">On the action pane, select **Save**.</span></span>

## <a name="set-up-warehouse-inventory-locations"></a><span data-ttu-id="8de1a-140">Raktári készlethelyek beállítása</span><span class="sxs-lookup"><span data-stu-id="8de1a-140">Set up warehouse inventory locations</span></span>

<span data-ttu-id="8de1a-141">A szokásos, sérült és visszaküldött készlet raktári készlethelyének beállításához hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="8de1a-141">To set up warehouse inventory locations for standard, damaged, and returned inventory, follow these steps.</span></span>

1. <span data-ttu-id="8de1a-142">A navigációs ablaktáblán lépjen a **Modulok \> Kiskereskedelem és kereskedelem \> Csatornák beállítása \> Raktárak** részhez.</span><span class="sxs-lookup"><span data-stu-id="8de1a-142">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Warehouses**.</span></span>
1. <span data-ttu-id="8de1a-143">Válassza ki a korábban létrehozott raktárat.</span><span class="sxs-lookup"><span data-stu-id="8de1a-143">Select the warehouse you created previously.</span></span>
1. <span data-ttu-id="8de1a-144">A műveleti ablaktáblán válassza a **Szerkesztés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8de1a-144">On the action pane, select **Edit**.</span></span>
1. <span data-ttu-id="8de1a-145">A műveleti ablaktáblán válassza a **Raktár** elemet, majd válassza ki a **Készlet helyét**.</span><span class="sxs-lookup"><span data-stu-id="8de1a-145">On the action pane, select **Warehouse**, and then select **Inventory location**.</span></span>
1. <span data-ttu-id="8de1a-146">A műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="8de1a-146">On the action pane, select **New**.</span></span> <span data-ttu-id="8de1a-147">A **raktár** legördülő listájának alapértelmezett értéke az új raktárnak kell lennie.</span><span class="sxs-lookup"><span data-stu-id="8de1a-147">The **Warehouse** drop-down list should default to your new warehouse.</span></span>
    1. <span data-ttu-id="8de1a-148">A **folyosó** mezőbe írja be a korábban megadott folyosó nevét.</span><span class="sxs-lookup"><span data-stu-id="8de1a-148">In the **Aisle** box, enter the name of the aisle you specified earlier.</span></span> 
    1. <span data-ttu-id="8de1a-149">Állítsa a **Manuális frissítés** értékét **Igen** értékét</span><span class="sxs-lookup"><span data-stu-id="8de1a-149">Set **Manual update** to **Yes**</span></span>
    1. <span data-ttu-id="8de1a-150">A **Hely** mezőbe írja be a raktár nevét.</span><span class="sxs-lookup"><span data-stu-id="8de1a-150">In the **Location** box, enter the name of the warehouse.</span></span>
    1. <span data-ttu-id="8de1a-151">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8de1a-151">On the action pane, select **Save**.</span></span>
 1. <span data-ttu-id="8de1a-152">A műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="8de1a-152">On the action pane, select **New**.</span></span>  <span data-ttu-id="8de1a-153">A **raktár** legördülő listájának alapértelmezett értéke az új raktárnak kell lennie.</span><span class="sxs-lookup"><span data-stu-id="8de1a-153">The **Warehouse** drop-down list should default to your new warehouse.</span></span>
    1. <span data-ttu-id="8de1a-154">A **folyosó** mezőbe írja be a korábban megadott folyosó nevét.</span><span class="sxs-lookup"><span data-stu-id="8de1a-154">In the **Aisle** box, enter the name of the aisle you specified earlier.</span></span>  
    1. <span data-ttu-id="8de1a-155">Állítsa a **Manuális frissítés** értékét **Igen** értékét</span><span class="sxs-lookup"><span data-stu-id="8de1a-155">Set **Manual update** to **Yes**</span></span>
    1. <span data-ttu-id="8de1a-156">A **Hely** mezőbe írja be a „Sérült” értéket.</span><span class="sxs-lookup"><span data-stu-id="8de1a-156">In the **Location** box, enter "Damaged".</span></span>
    1. <span data-ttu-id="8de1a-157">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8de1a-157">On the action pane, select **Save**.</span></span>
 1. <span data-ttu-id="8de1a-158">A műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="8de1a-158">On the action pane, select **New**.</span></span>  <span data-ttu-id="8de1a-159">A **raktár** legördülő listájának alapértelmezett értéke az új raktárnak kell lennie.</span><span class="sxs-lookup"><span data-stu-id="8de1a-159">The **Warehouse** drop-down list should default to your new warehouse.</span></span>
    1. <span data-ttu-id="8de1a-160">A **folyosó** mezőbe írja be a korábban megadott folyosó nevét.</span><span class="sxs-lookup"><span data-stu-id="8de1a-160">In the **Aisle** box, enter the name of the aisle you specified earlier.</span></span> 
    1. <span data-ttu-id="8de1a-161">Állítsa a **Manuális frissítés** értékét **Igen** értékét</span><span class="sxs-lookup"><span data-stu-id="8de1a-161">Set **Manual update** to **Yes**</span></span>
    1. <span data-ttu-id="8de1a-162">A **Hely** mezőbe írja be a „Visszáruk” értéket.</span><span class="sxs-lookup"><span data-stu-id="8de1a-162">In the **Location** box, enter "Returns".</span></span>
    1. <span data-ttu-id="8de1a-163">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8de1a-163">On the action pane, select **Save**.</span></span>
    
<span data-ttu-id="8de1a-164">A következő képen a San Francisco raktár készlethely beállítása látható.</span><span class="sxs-lookup"><span data-stu-id="8de1a-164">The following image shows a San Francisco warehouse inventory location setup.</span></span>

![Példa raktári hely beállítására](media/warehouse-inventory-locations.png)
    
## <a name="complete-warehouse-setup"></a><span data-ttu-id="8de1a-166">Teljes raktári beállítás</span><span class="sxs-lookup"><span data-stu-id="8de1a-166">Complete warehouse setup</span></span>

<span data-ttu-id="8de1a-167">Ennek a raktárbeállításnak a befejezéséhez kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="8de1a-167">To complete warehouse setup, follow these steps.</span></span>

1. <span data-ttu-id="8de1a-168">A navigációs ablaktáblán lépjen a **Modulok \> Kiskereskedelem és kereskedelem \> Csatornák beállítása \> Raktárak** részhez.</span><span class="sxs-lookup"><span data-stu-id="8de1a-168">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Warehouses**.</span></span>
1. <span data-ttu-id="8de1a-169">Válassza ki a korábban létrehozott raktárat.</span><span class="sxs-lookup"><span data-stu-id="8de1a-169">Select the warehouse you previously created.</span></span>
1. <span data-ttu-id="8de1a-170">A műveleti ablaktáblán válassza a **Szerkesztés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8de1a-170">On the action pane, select **Edit**.</span></span>
1. <span data-ttu-id="8de1a-171">A **Készlet- és raktárkezelés** részben:</span><span class="sxs-lookup"><span data-stu-id="8de1a-171">Under **Inventory and warehouse management**:</span></span>
    1. <span data-ttu-id="8de1a-172">**Alapértelmezett nyugta helyének** állítsa be a fent létrehozott alapértelmezett helyet.</span><span class="sxs-lookup"><span data-stu-id="8de1a-172">Set **Default receipt location** to the default location created above.</span></span>
    1. <span data-ttu-id="8de1a-173">**Alapértelmezett kibocsátási helynek** válassza ki a fent létrehozott alapértelmezett helyet.</span><span class="sxs-lookup"><span data-stu-id="8de1a-173">Select **Default issue location** to the default location created above.</span></span>
1. <span data-ttu-id="8de1a-174">A **címek** szakaszban adja meg a raktári címet.</span><span class="sxs-lookup"><span data-stu-id="8de1a-174">Under the **Addresses** section, enter a warehouse address.</span></span>
1. <span data-ttu-id="8de1a-175">A **kiskereskedelmi** szakasz keretében:</span><span class="sxs-lookup"><span data-stu-id="8de1a-175">Under the **Retail** section:</span></span> 
    1. <span data-ttu-id="8de1a-176">Az **Alapértelmezett visszáruhely** mezőbe írja be a korábban létrehozott visszáru helyet.</span><span class="sxs-lookup"><span data-stu-id="8de1a-176">In the **Default return location** box, enter the returns location created previously.</span></span>
    1. <span data-ttu-id="8de1a-177">Állítsa az **Üzlet** beállítását **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="8de1a-177">Set **Store** to **Yes**.</span></span>
    1. <span data-ttu-id="8de1a-178">A **Tömeget** állítsa a **1,00** értékre.</span><span class="sxs-lookup"><span data-stu-id="8de1a-178">Set **Weight** to **1.00**.</span></span> 
    1. <span data-ttu-id="8de1a-179">A **tárolási dimenziók** mezőbe írja be a korábban létrehozott alapértelmezett helyet.</span><span class="sxs-lookup"><span data-stu-id="8de1a-179">In the **Storage Dimensions** box, enter the default location created previously.</span></span>
1. <span data-ttu-id="8de1a-180">A **Raktár** szakaszban állítsa a **Tényleges negatív készlet** értékét **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="8de1a-180">Under the **Warehouse** section, set **Physical negative inventory** to **Yes**.</span></span>
1. <span data-ttu-id="8de1a-181">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8de1a-181">On the action pane, select **Save**.</span></span>

<span data-ttu-id="8de1a-182">A következő kép a konfigurált raktár adatait jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="8de1a-182">The following image shows details for a configured warehouse.</span></span>

![Példa konfigurált raktárra](media/warehouse-sample.png)

## <a name="additional-resources"></a><span data-ttu-id="8de1a-184">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="8de1a-184">Additional resources</span></span>

[<span data-ttu-id="8de1a-185">Raktárkezelés áttekintése</span><span class="sxs-lookup"><span data-stu-id="8de1a-185">Warehouse management overview</span></span>](../supply-chain/warehousing/warehouse-management-overview.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="8de1a-186">Csatornák áttekintése</span><span class="sxs-lookup"><span data-stu-id="8de1a-186">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="8de1a-187">Csatornák beállításának előfeltételei</span><span class="sxs-lookup"><span data-stu-id="8de1a-187">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="8de1a-188">Kiskereskedelmi csatorna beállítása</span><span class="sxs-lookup"><span data-stu-id="8de1a-188">Set up a retail channel</span></span>](channel-setup-retail.md)
    
[<span data-ttu-id="8de1a-189">Online csatorna beállítása</span><span class="sxs-lookup"><span data-stu-id="8de1a-189">Set up an online channel</span></span>](channel-setup-online.md)

[<span data-ttu-id="8de1a-190">Hívásközpont csatorna beállítása</span><span class="sxs-lookup"><span data-stu-id="8de1a-190">Set up a call center channel</span></span>](channel-setup-callcenter.md)







[!INCLUDE[footer-include](../includes/footer-banner.md)]
