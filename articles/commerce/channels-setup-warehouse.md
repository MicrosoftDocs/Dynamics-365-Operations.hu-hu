---
title: Raktár beállítása
description: Ez a témakör azt mutatja be, hogyan lehet beállítani a raktárakat új csatornával való használathoz a Microsoft Dynamics 365 Commerce szolgáltatásban.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 9ba12876a8c8f841733d8ec49c33e900211c4ab4
ms.sourcegitcommit: 12b9d6f2dd24e52e46487748c848864909af6967
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/14/2020
ms.locfileid: "3057856"
---
# <a name="warehouse-set-up"></a><span data-ttu-id="a2f49-103">Raktár beállítása</span><span class="sxs-lookup"><span data-stu-id="a2f49-103">Warehouse set up</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="a2f49-104">Ez a témakör azt mutatja be, hogyan lehet beállítani a raktárakat új csatornával való használathoz a Microsoft Dynamics 365 Commerce szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="a2f49-104">This topic describes how to set up a warehouse to be used with a new channel in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="a2f49-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="a2f49-105">Overview</span></span>

<span data-ttu-id="a2f49-106">Minden egyes Commerce-csatornához hozzá kell rendelni egy konfigurált raktárat.</span><span class="sxs-lookup"><span data-stu-id="a2f49-106">Each Commerce channel requires a configured warehouse to be associated with it.</span></span> <span data-ttu-id="a2f49-107">A következő eljárások a Commerce csatorna raktárának beállításához szükséges minimális konfigurációját nyújtják.</span><span class="sxs-lookup"><span data-stu-id="a2f49-107">The following procedures provide the minimum configuration required to set up a warehouse for a Commerce channel.</span></span> <span data-ttu-id="a2f49-108">A raktár beállításaival kapcsolatos további tudnivalókat lásd a [Raktárkezelés – áttekintés](https://docs.microsoft.com/en-us/dynamics365/supply-chain/warehousing/warehouse-management-overview) című témakörben.</span><span class="sxs-lookup"><span data-stu-id="a2f49-108">For more information regarding warehouse setup, please see the [Warehouse management overview](https://docs.microsoft.com/en-us/dynamics365/supply-chain/warehousing/warehouse-management-overview).</span></span>

## <a name="configure-a-warehouse-site"></a><span data-ttu-id="a2f49-109">Raktár webhelyének konfigurálása</span><span class="sxs-lookup"><span data-stu-id="a2f49-109">Configure a warehouse site</span></span>

<span data-ttu-id="a2f49-110">A raktár beállítása előtt konfigurálnia kell egy raktári webhelyet.</span><span class="sxs-lookup"><span data-stu-id="a2f49-110">Before setting up a warehouse, you need to configure a warehouse site.</span></span>

<span data-ttu-id="a2f49-111">A raktári webhely konfigurálásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="a2f49-111">To configure a warehouse site, follow these steps.</span></span>

1. <span data-ttu-id="a2f49-112">A navigációs ablaktáblán lépjen a **Modulok \> Kiskereskedelem és kereskedelem \> Csatornák beállítása \> Webhelyek** részhez.</span><span class="sxs-lookup"><span data-stu-id="a2f49-112">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Sites**.</span></span>
1. <span data-ttu-id="a2f49-113">A műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="a2f49-113">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="a2f49-114">A **Webhely** mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="a2f49-114">In the **Site** field, enter a value.</span></span>
1. <span data-ttu-id="a2f49-115">A **Név** mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="a2f49-115">In the **Name** field, enter a value.</span></span>
1. <span data-ttu-id="a2f49-116">Az **Általános** szakaszban adja meg a megfelelő **időzónát**.</span><span class="sxs-lookup"><span data-stu-id="a2f49-116">In the **General** section, set the appropriate **Time zone**.</span></span>
1. <span data-ttu-id="a2f49-117">A **Címek** szakaszban adjon meg egy címet.</span><span class="sxs-lookup"><span data-stu-id="a2f49-117">In the **Addresses** section, enter an address.</span></span>
1. <span data-ttu-id="a2f49-118">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a2f49-118">On the action pane, select **Save**.</span></span>

<span data-ttu-id="a2f49-119">A következő kép egy példát mutat a raktárwebhelyre.</span><span class="sxs-lookup"><span data-stu-id="a2f49-119">The following image shows an example warehouse site.</span></span>

![Példa: raktárwebhely](media/warehouse-site.png)

## <a name="set-up-a-warehouse"></a><span data-ttu-id="a2f49-121">Raktár beállítása</span><span class="sxs-lookup"><span data-stu-id="a2f49-121">Set up a warehouse</span></span>

<span data-ttu-id="a2f49-122">Raktár beállításához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="a2f49-122">To set up a warehouse, follow these steps.</span></span>

1. <span data-ttu-id="a2f49-123">A navigációs ablaktáblán lépjen a **Modulok \> Kiskereskedelem és kereskedelem \> Csatornák beállítása \> Raktárak** részhez.</span><span class="sxs-lookup"><span data-stu-id="a2f49-123">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Warehouses**.</span></span>
1. <span data-ttu-id="a2f49-124">A műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="a2f49-124">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="a2f49-125">A **Raktár** mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="a2f49-125">In the **Warehouse** field, enter a value.</span></span>  <span data-ttu-id="a2f49-126">Ha ez egy 1:1 hozzárendelés egy üzlethez, vegye fontolóra az üzlet nevének vagy egy területi elosztó központ nevének használatát.</span><span class="sxs-lookup"><span data-stu-id="a2f49-126">If this is a 1:1 mapping to a store, consider using the store name or the name of a regional distribution center.</span></span>
1. <span data-ttu-id="a2f49-127">A **Név** mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="a2f49-127">In the **Name** field, enter a value.</span></span>
1. <span data-ttu-id="a2f49-128">A **webhely** legördülő listában válassza ki a korábban létrehozott raktári webhelyet.</span><span class="sxs-lookup"><span data-stu-id="a2f49-128">In the **Site** drop-down list, select the warehouse site created previously.</span></span>
1. <span data-ttu-id="a2f49-129">A **Típus** mezőben válassza ki az **Alapértelmezett** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a2f49-129">In the **Type** field, select **Default**.</span></span>
    - <span data-ttu-id="a2f49-130">Ha meg kívánja adni a **karanténraktárat**, akkor az alábbi lépések követésével hozzon létre egy olyan további raktárat, amelyben a **Típus** legyen **Karantén**.</span><span class="sxs-lookup"><span data-stu-id="a2f49-130">If you want to set a **Quarantine warehouse**, first you'll need to follow these steps to create an additional warehouse where the **Type** is set to **Quarantine**.</span></span>
    - <span data-ttu-id="a2f49-131">Ha meg kívánja adni a **Tranzitraktárat**, akkor az alábbi lépések követésével hozzon létre egy olyan további raktárat, amelyben a **Típus** legyen **Tranzit**.</span><span class="sxs-lookup"><span data-stu-id="a2f49-131">If you want to set a **Transit warehouse**, first you'll need to follow these steps to create an additional warehouse where the **Type** is set to **Transit**.</span></span>
1. <span data-ttu-id="a2f49-132">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a2f49-132">On the action pane, select **Save**.</span></span>

## <a name="set-up-inventory-aisles"></a><span data-ttu-id="a2f49-133">Raktárfolyosók beállítása</span><span class="sxs-lookup"><span data-stu-id="a2f49-133">Set up inventory aisles</span></span>

<span data-ttu-id="a2f49-134">A készletfolyosók beállításához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="a2f49-134">To set up inventory aisles, follow these steps.</span></span>

1. <span data-ttu-id="a2f49-135">A navigációs ablaktáblán lépjen a **Modulok \> Kiskereskedelem és kereskedelem \> Csatornák beállítása \> Hely beállítása \> Készletfolyosók** részhez.</span><span class="sxs-lookup"><span data-stu-id="a2f49-135">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Location setup \> Inventory aisles**.</span></span>
1. <span data-ttu-id="a2f49-136">A műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="a2f49-136">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="a2f49-137">A **Raktár** legördülő listában válassza ki a korábban létrehozott raktárat.</span><span class="sxs-lookup"><span data-stu-id="a2f49-137">In the **Warehouse** drop-down list, select the warehouse created previously.</span></span>
1. <span data-ttu-id="a2f49-138">A **Folyosó** mezőben adjon meg egy nevet (például „Def”).</span><span class="sxs-lookup"><span data-stu-id="a2f49-138">In the **Aisle** field, enter a name (for example, "Def").</span></span>
1. <span data-ttu-id="a2f49-139">A **Név** mezőben adjon meg egy nevet (például „Alapértelmezett folyosó”).</span><span class="sxs-lookup"><span data-stu-id="a2f49-139">In the **Name** field, enter a name (for example, "Default aisle").</span></span>
1. <span data-ttu-id="a2f49-140">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a2f49-140">On the action pane, select **Save**.</span></span>

## <a name="set-up-warehouse-inventory-locations"></a><span data-ttu-id="a2f49-141">Raktári készlethelyek beállítása</span><span class="sxs-lookup"><span data-stu-id="a2f49-141">Set up warehouse inventory locations</span></span>

<span data-ttu-id="a2f49-142">A szokásos, sérült és visszaküldött készlet raktári készlethelyének beállításához hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="a2f49-142">To set up warehouse inventory locations for standard, damaged, and returned inventory, follow these steps.</span></span>

1. <span data-ttu-id="a2f49-143">A navigációs ablaktáblán lépjen a **Modulok \> Kiskereskedelem és kereskedelem \> Csatornák beállítása \> Raktárak** részhez.</span><span class="sxs-lookup"><span data-stu-id="a2f49-143">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Warehouses**.</span></span>
1. <span data-ttu-id="a2f49-144">Válassza ki a korábban létrehozott raktárat.</span><span class="sxs-lookup"><span data-stu-id="a2f49-144">Select the warehouse you created previously.</span></span>
1. <span data-ttu-id="a2f49-145">A műveleti ablaktáblán válassza a **Szerkesztés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a2f49-145">On the action pane, select **Edit**.</span></span>
1. <span data-ttu-id="a2f49-146">A műveleti ablaktáblán válassza a **Raktár** elemet, majd válassza ki a **Készlet helyét**.</span><span class="sxs-lookup"><span data-stu-id="a2f49-146">On the action pane, select **Warehouse**, and then select **Inventory location**.</span></span>
1. <span data-ttu-id="a2f49-147">A műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="a2f49-147">On the action pane, select **New**.</span></span> <span data-ttu-id="a2f49-148">A **raktár** legördülő listájának alapértelmezett értéke az új raktárnak kell lennie.</span><span class="sxs-lookup"><span data-stu-id="a2f49-148">The **Warehouse** drop-down list should default to your new warehouse.</span></span>
    1. <span data-ttu-id="a2f49-149">A **folyosó** mezőbe írja be a korábban megadott folyosó nevét.</span><span class="sxs-lookup"><span data-stu-id="a2f49-149">In the **Aisle** box, enter the name of the aisle you specified earlier.</span></span> 
    1. <span data-ttu-id="a2f49-150">Állítsa a **Manuális frissítés** értékét **Igen** értékét</span><span class="sxs-lookup"><span data-stu-id="a2f49-150">Set **Manual update** to **Yes**</span></span>
    1. <span data-ttu-id="a2f49-151">A **Hely** mezőbe írja be a raktár nevét.</span><span class="sxs-lookup"><span data-stu-id="a2f49-151">In the **Location** box, enter the name of the warehouse.</span></span>
    1. <span data-ttu-id="a2f49-152">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a2f49-152">On the action pane, select **Save**.</span></span>
 1. <span data-ttu-id="a2f49-153">A műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="a2f49-153">On the action pane, select **New**.</span></span>  <span data-ttu-id="a2f49-154">A **raktár** legördülő listájának alapértelmezett értéke az új raktárnak kell lennie.</span><span class="sxs-lookup"><span data-stu-id="a2f49-154">The **Warehouse** drop-down list should default to your new warehouse.</span></span>
    1. <span data-ttu-id="a2f49-155">A **folyosó** mezőbe írja be a korábban megadott folyosó nevét.</span><span class="sxs-lookup"><span data-stu-id="a2f49-155">In the **Aisle** box, enter the name of the aisle you specified earlier.</span></span>  
    1. <span data-ttu-id="a2f49-156">Állítsa a **Manuális frissítés** értékét **Igen** értékét</span><span class="sxs-lookup"><span data-stu-id="a2f49-156">Set **Manual update** to **Yes**</span></span>
    1. <span data-ttu-id="a2f49-157">A **Hely** mezőbe írja be a „Sérült” értéket.</span><span class="sxs-lookup"><span data-stu-id="a2f49-157">In the **Location** box, enter "Damaged".</span></span>
    1. <span data-ttu-id="a2f49-158">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a2f49-158">On the action pane, select **Save**.</span></span>
 1. <span data-ttu-id="a2f49-159">A műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="a2f49-159">On the action pane, select **New**.</span></span>  <span data-ttu-id="a2f49-160">A **raktár** legördülő listájának alapértelmezett értéke az új raktárnak kell lennie.</span><span class="sxs-lookup"><span data-stu-id="a2f49-160">The **Warehouse** drop-down list should default to your new warehouse.</span></span>
    1. <span data-ttu-id="a2f49-161">A **folyosó** mezőbe írja be a korábban megadott folyosó nevét.</span><span class="sxs-lookup"><span data-stu-id="a2f49-161">In the **Aisle** box, enter the name of the aisle you specified earlier.</span></span> 
    1. <span data-ttu-id="a2f49-162">Állítsa a **Manuális frissítés** értékét **Igen** értékét</span><span class="sxs-lookup"><span data-stu-id="a2f49-162">Set **Manual update** to **Yes**</span></span>
    1. <span data-ttu-id="a2f49-163">A **Hely** mezőbe írja be a „Visszáruk” értéket.</span><span class="sxs-lookup"><span data-stu-id="a2f49-163">In the **Location** box, enter "Returns".</span></span>
    1. <span data-ttu-id="a2f49-164">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a2f49-164">On the action pane, select **Save**.</span></span>
    
<span data-ttu-id="a2f49-165">A következő képen a San Francisco raktár készlethely beállítása látható.</span><span class="sxs-lookup"><span data-stu-id="a2f49-165">The following image shows a San Francisco warehouse inventory location setup.</span></span>

![Példa raktári hely beállítására](media/warehouse-inventory-locations.png)
    
## <a name="complete-warehouse-setup"></a><span data-ttu-id="a2f49-167">Teljes raktári beállítás</span><span class="sxs-lookup"><span data-stu-id="a2f49-167">Complete warehouse setup</span></span>

<span data-ttu-id="a2f49-168">Ennek a raktárbeállításnak a befejezéséhez kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="a2f49-168">To complete warehouse setup, follow these steps.</span></span>

1. <span data-ttu-id="a2f49-169">A navigációs ablaktáblán lépjen a **Modulok \> Kiskereskedelem és kereskedelem \> Csatornák beállítása \> Raktárak** részhez.</span><span class="sxs-lookup"><span data-stu-id="a2f49-169">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Warehouses**.</span></span>
1. <span data-ttu-id="a2f49-170">Válassza ki a korábban létrehozott raktárat.</span><span class="sxs-lookup"><span data-stu-id="a2f49-170">Select the warehouse you previously created.</span></span>
1. <span data-ttu-id="a2f49-171">A műveleti ablaktáblán válassza a **Szerkesztés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a2f49-171">On the action pane, select **Edit**.</span></span>
1. <span data-ttu-id="a2f49-172">A **Készlet- és raktárkezelés** részben:</span><span class="sxs-lookup"><span data-stu-id="a2f49-172">Under **Inventory and warehouse management**:</span></span>
    1. <span data-ttu-id="a2f49-173">**Alapértelmezett nyugta helyének** állítsa be a fent létrehozott alapértelmezett helyet.</span><span class="sxs-lookup"><span data-stu-id="a2f49-173">Set **Default receipt location** to the default location created above.</span></span>
    1. <span data-ttu-id="a2f49-174">**Alapértelmezett kibocsátási helynek** válassza ki a fent létrehozott alapértelmezett helyet.</span><span class="sxs-lookup"><span data-stu-id="a2f49-174">Select **Default issue location** to the default location created above.</span></span>
1. <span data-ttu-id="a2f49-175">A **címek** szakaszban adja meg a raktári címet.</span><span class="sxs-lookup"><span data-stu-id="a2f49-175">Under the **Addresses** section, enter a warehouse address.</span></span>
1. <span data-ttu-id="a2f49-176">A **kiskereskedelmi** szakasz keretében:</span><span class="sxs-lookup"><span data-stu-id="a2f49-176">Under the **Retail** section:</span></span> 
    1. <span data-ttu-id="a2f49-177">Az **Alapértelmezett visszáruhely** mezőbe írja be a korábban létrehozott visszáru helyet.</span><span class="sxs-lookup"><span data-stu-id="a2f49-177">In the **Default return location** box, enter the returns location created previously.</span></span>
    1. <span data-ttu-id="a2f49-178">Állítsa az **Üzlet** beállítását **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="a2f49-178">Set **Store** to **Yes**.</span></span>
    1. <span data-ttu-id="a2f49-179">A **Tömeget** állítsa a **1,00** értékre.</span><span class="sxs-lookup"><span data-stu-id="a2f49-179">Set **Weight** to **1.00**.</span></span> 
    1. <span data-ttu-id="a2f49-180">A **tárolási dimenziók** mezőbe írja be a korábban létrehozott alapértelmezett helyet.</span><span class="sxs-lookup"><span data-stu-id="a2f49-180">In the **Storage Dimensions** box, enter the default location created previously.</span></span>
1. <span data-ttu-id="a2f49-181">A **Raktár** szakaszban állítsa a **Tényleges negatív készlet** értékét **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="a2f49-181">Under the **Warehouse** section, set **Physical negative inventory** to **Yes**.</span></span>
1. <span data-ttu-id="a2f49-182">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a2f49-182">On the action pane, select **Save**.</span></span>

<span data-ttu-id="a2f49-183">A következő kép a konfigurált raktár adatait jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="a2f49-183">The following image shows details for a configured warehouse.</span></span>

![Példa konfigurált raktárra](media/warehouse-sample.png)

## <a name="additional-resources"></a><span data-ttu-id="a2f49-185">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="a2f49-185">Additional resources</span></span>

[<span data-ttu-id="a2f49-186">Raktárkezelés áttekintése</span><span class="sxs-lookup"><span data-stu-id="a2f49-186">Warehouse management overview</span></span>](https://docs.microsoft.com/en-us/dynamics365/supply-chain/warehousing/warehouse-management-overview)

[<span data-ttu-id="a2f49-187">Csatornák áttekintése</span><span class="sxs-lookup"><span data-stu-id="a2f49-187">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="a2f49-188">Csatornák beállításának előfeltételei</span><span class="sxs-lookup"><span data-stu-id="a2f49-188">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="a2f49-189">Kiskereskedelmi csatorna beállítása</span><span class="sxs-lookup"><span data-stu-id="a2f49-189">Set up a retail channel</span></span>](channel-setup-retail.md)
    
[<span data-ttu-id="a2f49-190">Online csatorna beállítása</span><span class="sxs-lookup"><span data-stu-id="a2f49-190">Set up an online channel</span></span>](channel-setup-online.md)

[<span data-ttu-id="a2f49-191">Hívásközpont csatorna beállítása</span><span class="sxs-lookup"><span data-stu-id="a2f49-191">Set up a call center channel</span></span>](channel-setup-callcenter.md)





