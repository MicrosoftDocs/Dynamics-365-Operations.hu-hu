---
title: Online csatornajelentések készítése
description: Ez a témakör azt mutatja be, hogyan lehet jelentéseket létrehozni egy online csatornához a Microsoft Dynamics 365 Retail alkalmazásban.
author: psimolin
manager: annbe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 77737c134df8f3ba598fe9026fa7c01ca9976733
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/01/2019
ms.locfileid: "2698050"
---
# <a name="generate-online-channel-reports"></a><span data-ttu-id="4939c-103">Online csatornajelentések készítése</span><span class="sxs-lookup"><span data-stu-id="4939c-103">Generate online channel reports</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="4939c-104">Ez a témakör azt mutatja be, hogyan lehet jelentéseket létrehozni egy online csatornához a Microsoft Dynamics 365 Retail alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="4939c-104">This topic describes how to generate reports for your online channel in Microsoft Dynamics 365 Retail.</span></span>

## <a name="overview"></a><span data-ttu-id="4939c-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="4939c-105">Overview</span></span>

<span data-ttu-id="4939c-106">A Retail alkalmazásban számos jelentés létrehozható és megtekinthető, hogy megtudja, hogyan teljesít online csatornája.</span><span class="sxs-lookup"><span data-stu-id="4939c-106">You can generate and view several reports in Retail to see how your online channel is performing.</span></span>

## <a name="channel-summary-report"></a><span data-ttu-id="4939c-107">Csatorna-összefoglaló jelentés</span><span class="sxs-lookup"><span data-stu-id="4939c-107">Channel summary report</span></span>

<span data-ttu-id="4939c-108">A **Csatorna-összefoglaló** jelentés a következő tranzakciók összesítését jeleníti meg a kiválasztott csatornához:</span><span class="sxs-lookup"><span data-stu-id="4939c-108">The **Channel summary** report shows a summary of the following transactions for the selected channel:</span></span>

- <span data-ttu-id="4939c-109">Értékesítési tranzakciók</span><span class="sxs-lookup"><span data-stu-id="4939c-109">Sales transactions</span></span>
- <span data-ttu-id="4939c-110">Fizetési tranzakciók</span><span class="sxs-lookup"><span data-stu-id="4939c-110">Payment transactions</span></span>
- <span data-ttu-id="4939c-111">Adótranzakciók</span><span class="sxs-lookup"><span data-stu-id="4939c-111">Tax transactions</span></span>
- <span data-ttu-id="4939c-112">Engedményes tranzakciók</span><span class="sxs-lookup"><span data-stu-id="4939c-112">Discounted transactions</span></span>

<span data-ttu-id="4939c-113">A **Csatorna-összesítő** jelentés létrehozásához hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="4939c-113">To generate a **Channel summary** report, follow these steps.</span></span>

1. <span data-ttu-id="4939c-114">Nyissa meg a **Retail \> Lekérdezések és jelentések \> Értékesítési jelentések \> Csatornaösszesítő-jelentés** elemet.</span><span class="sxs-lookup"><span data-stu-id="4939c-114">Go to **Retail \> Inquiries and reports \> Sales reports \> Channel summary report**.</span></span>
1. <span data-ttu-id="4939c-115">Adjon meg egy dátumot a **Kezdő dátum** mezőben.</span><span class="sxs-lookup"><span data-stu-id="4939c-115">In the **From date** field, enter a date.</span></span>
1. <span data-ttu-id="4939c-116">Adjon meg egy dátumot a **Záró dátum** mezőben.</span><span class="sxs-lookup"><span data-stu-id="4939c-116">In the **To date** field, enter a date.</span></span>
1. <span data-ttu-id="4939c-117">Válassza ki az online csatornát a **Csatorna** mezőben.</span><span class="sxs-lookup"><span data-stu-id="4939c-117">In the **Channel** field, select the online channel.</span></span>
1. <span data-ttu-id="4939c-118">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4939c-118">Select **OK**.</span></span>
 
## <a name="channel-sales-by-year-report"></a><span data-ttu-id="4939c-119">Csatorna értékesítése év szerint – jelentés</span><span class="sxs-lookup"><span data-stu-id="4939c-119">Channel sales by year report</span></span> 

<span data-ttu-id="4939c-120">A **Csatorna értékesítése év szerint** jelentés egy adott üzlet értékesítésének évek szerinti összehasonlítását jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="4939c-120">The **Channel sales by year** report shows a comparison of year-over-year sales for a specific store.</span></span> <span data-ttu-id="4939c-121">Válassza ki az évet, amelyhez hasonlítani szeretné az értékesítést, és a jelentés összeveti a kiválasztott év értékesítéseit az előző évhez képest.</span><span class="sxs-lookup"><span data-stu-id="4939c-121">You select the year to compare the sales against, and the report compares sales for the selected year with sales for the previous year.</span></span>

<span data-ttu-id="4939c-122">A **Csatorna értékesítése év szerint** jelentés létrehozásához hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="4939c-122">To generate a **Channel sales by year** report, follow these steps.</span></span>

1. <span data-ttu-id="4939c-123">Nyissa meg a **Retail \> Lekérdezések és jelentések \> Értékesítési jelentések \> Csatorna értékesítése év szerint** elemet.</span><span class="sxs-lookup"><span data-stu-id="4939c-123">Go to **Retail \> Inquiries and reports \> Sales reports \> Channel sales by year report**.</span></span>
1. <span data-ttu-id="4939c-124">Adjon meg egy évet a **Kezdő naptári év** mezőben.</span><span class="sxs-lookup"><span data-stu-id="4939c-124">In the **From calendar year** field, enter a year.</span></span>
1. <span data-ttu-id="4939c-125">Adjon meg egy évet a **Befejező naptári év** mezőben.</span><span class="sxs-lookup"><span data-stu-id="4939c-125">In the **To calendar year** field, enter a year.</span></span>
1. <span data-ttu-id="4939c-126">Válassza ki az online csatornát a **Csatorna** mezőben.</span><span class="sxs-lookup"><span data-stu-id="4939c-126">In the **Channel** field, select the online channel.</span></span>
1. <span data-ttu-id="4939c-127">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4939c-127">Select **OK**.</span></span>

## <a name="channel-sales-by-hour-report"></a><span data-ttu-id="4939c-128">Csatorna értékesítése óra szerint – jelentés</span><span class="sxs-lookup"><span data-stu-id="4939c-128">Channel sales by hour report</span></span>

<span data-ttu-id="4939c-129">A **Csatorna értékesítése óra szerint** jelentés megjeleníti az óránkénti értékesítési metrikákat a kiválasztott csatornához vagy üzemi egységhez.</span><span class="sxs-lookup"><span data-stu-id="4939c-129">The **Channel sales by hour** report shows sales metrics per hour for a selected channel or operating unit.</span></span>

<span data-ttu-id="4939c-130">A **Csatorna értékesítése óra szerint** jelentés létrehozásához hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="4939c-130">To generate a **Channel sales by hour** report, follow these steps.</span></span>

1. <span data-ttu-id="4939c-131">Nyissa meg a **Retail \> Lekérdezések és jelentések \> Értékesítési jelentések \> Csatorna értékesítése óra szerint** elemet.</span><span class="sxs-lookup"><span data-stu-id="4939c-131">Go to **Retail \> Inquiries and reports \> Sales reports \> Channel sales by hour report**.</span></span>
1. <span data-ttu-id="4939c-132">Adjon meg egy dátumot a **Kezdő dátum** mezőben.</span><span class="sxs-lookup"><span data-stu-id="4939c-132">In the **From date** field, enter a date.</span></span>
1. <span data-ttu-id="4939c-133">Adjon meg egy dátumot a **Záró dátum** mezőben.</span><span class="sxs-lookup"><span data-stu-id="4939c-133">In the **To date** field, enter a date.</span></span>
1. <span data-ttu-id="4939c-134">Válassza ki az online csatornát a **Csatorna** mezőben.</span><span class="sxs-lookup"><span data-stu-id="4939c-134">In the **Channel** field, select the online channel.</span></span>
1. <span data-ttu-id="4939c-135">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4939c-135">Select **OK**.</span></span>

## <a name="top-customers-report"></a><span data-ttu-id="4939c-136">Legfőbb vevők – jelentés</span><span class="sxs-lookup"><span data-stu-id="4939c-136">Top customers report</span></span>

<span data-ttu-id="4939c-137">A **Legfőbb vevők** jelentés megjeleníti a kiválasztott csatorna vagy üzemi egység felső *N* vevőinek értékesítési metrikáját.</span><span class="sxs-lookup"><span data-stu-id="4939c-137">The **Top customers** report shows sales metrics for the top *N* customers for a selected channel or operating unit.</span></span> <span data-ttu-id="4939c-138">Az *N* érték egy 10 és 100 közötti szám, amely a felhasználó által kiválasztott összesítő mérőszámon alapul.</span><span class="sxs-lookup"><span data-stu-id="4939c-138">The value *N* is a number from 10 to 100 and is based on a user-selected aggregate measure.</span></span>

<span data-ttu-id="4939c-139">A **Legfőbb vevők** jelentés létrehozásához hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="4939c-139">To generate a **Top customers** report, follow these steps.</span></span>

1. <span data-ttu-id="4939c-140">Nyissa meg a **Retail \> Lekérdezések és jelentések \> Értékesítési jelentések \> Legfőbb vevők jelentés** elemet.</span><span class="sxs-lookup"><span data-stu-id="4939c-140">Go to **Retail \> Inquiries and reports \> Sales reports \> Top customers report**.</span></span>
1. <span data-ttu-id="4939c-141">Adjon meg egy dátumot a **Kezdő dátum** mezőben.</span><span class="sxs-lookup"><span data-stu-id="4939c-141">In the **From date** field, enter a date.</span></span>
1. <span data-ttu-id="4939c-142">Adjon meg egy dátumot a **Záró dátum** mezőben.</span><span class="sxs-lookup"><span data-stu-id="4939c-142">In the **To date** field, enter a date.</span></span>
1. <span data-ttu-id="4939c-143">Válassza ki az online csatornát a **Csatorna** mezőben.</span><span class="sxs-lookup"><span data-stu-id="4939c-143">In the **Channel** field, select the online channel.</span></span>
1. <span data-ttu-id="4939c-144">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4939c-144">Select **OK**.</span></span>

## <a name="top-discounts-report"></a><span data-ttu-id="4939c-145">Legnagyobb engedmények jelentése</span><span class="sxs-lookup"><span data-stu-id="4939c-145">Top discounts report</span></span>

<span data-ttu-id="4939c-146">A **Legnagyobb engedmények** jelentés megjeleníti a kiválasztott csatorna vagy üzemi egység legnagyobb *N* kedvezményének értékesítési metrikáját.</span><span class="sxs-lookup"><span data-stu-id="4939c-146">The **Top discounts** report shows sales metrics for the top *N* discounts for a selected channel or operating unit.</span></span> <span data-ttu-id="4939c-147">Az *N* érték egy 10 és 100 közötti szám, amely a felhasználó által kiválasztott összesítő mérőszámon alapul.</span><span class="sxs-lookup"><span data-stu-id="4939c-147">The value *N* is a number from 10 to 100 and is based on a user-selected aggregate measure.</span></span>

<span data-ttu-id="4939c-148">A **Legnagyobb engedmények** jelentés létrehozásához hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="4939c-148">To generate a **Top discounts** report, follow these steps.</span></span>

1. <span data-ttu-id="4939c-149">Nyissa meg a **Retail \> Lekérdezések és jelentések \> Értékesítési jelentések \> Legnagyobb engedmények jelentés** elemet.</span><span class="sxs-lookup"><span data-stu-id="4939c-149">Go to **Retail \> Inquiries and reports \> Sales reports \> Top discounts report**.</span></span>
1. <span data-ttu-id="4939c-150">Adjon meg egy dátumot a **Kezdő dátum** mezőben.</span><span class="sxs-lookup"><span data-stu-id="4939c-150">In the **From date** field, enter a date.</span></span>
1. <span data-ttu-id="4939c-151">Adjon meg egy dátumot a **Záró dátum** mezőben.</span><span class="sxs-lookup"><span data-stu-id="4939c-151">In the **To date** field, enter a date.</span></span>
1. <span data-ttu-id="4939c-152">Válassza ki az online csatornát a **Csatorna** mezőben.</span><span class="sxs-lookup"><span data-stu-id="4939c-152">In the **Channel** field, select the online channel.</span></span>
1. <span data-ttu-id="4939c-153">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4939c-153">Select **OK**.</span></span>

## <a name="top-products-report"></a><span data-ttu-id="4939c-154">Vezető termékek jelentése</span><span class="sxs-lookup"><span data-stu-id="4939c-154">Top products report</span></span>

<span data-ttu-id="4939c-155">A **Vezető termékek** jelentés megjeleníti a kiválasztott csatorna vagy üzemi egység vezető *N* termék értékesítési metrikáját.</span><span class="sxs-lookup"><span data-stu-id="4939c-155">The **Top products** report shows sales metrics for the top *N* products for a selected channel or operating unit.</span></span> <span data-ttu-id="4939c-156">Az *N* érték egy 10 és 100 közötti szám, amely a felhasználó által kiválasztott összesítő mérőszámon alapul.</span><span class="sxs-lookup"><span data-stu-id="4939c-156">The value *N* is a number from 10 to 100 and is based on a user-selected aggregate measure.</span></span>

<span data-ttu-id="4939c-157">A **Vezető termékek** jelentés létrehozásához hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="4939c-157">To generate a **Top products** report, follow these steps.</span></span>

1. <span data-ttu-id="4939c-158">Nyissa meg a **Retail \> Lekérdezések és jelentések \> Értékesítési jelentések \> Vezető termékek jelentés** elemet.</span><span class="sxs-lookup"><span data-stu-id="4939c-158">Go to **Retail \> Inquiries and reports \> Sales reports \> Top products report**.</span></span>
1. <span data-ttu-id="4939c-159">Adjon meg egy dátumot a **Kezdő dátum** mezőben.</span><span class="sxs-lookup"><span data-stu-id="4939c-159">In the **From date** field, enter a date.</span></span>
1. <span data-ttu-id="4939c-160">Adjon meg egy dátumot a **Záró dátum** mezőben.</span><span class="sxs-lookup"><span data-stu-id="4939c-160">In the **To date** field, enter a date.</span></span>
1. <span data-ttu-id="4939c-161">Válassza ki az online csatornát a **Csatorna** mezőben.</span><span class="sxs-lookup"><span data-stu-id="4939c-161">In the **Channel** field, select the online channel.</span></span>
1. <span data-ttu-id="4939c-162">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4939c-162">Select **OK**.</span></span>

## <a name="category-sales-report"></a><span data-ttu-id="4939c-163">Kategória értékesítése – jelentés</span><span class="sxs-lookup"><span data-stu-id="4939c-163">Category sales report</span></span>

<span data-ttu-id="4939c-164">A **Kategória értékesítései** jelentés egy kiválasztott időszakra vonatkozóan megjeleníti az értékesítési mérőszámokat a kiválasztott csatornához vagy üzemi egységhez tartozó kategória-hierarchia egyes csomópontjaihoz.</span><span class="sxs-lookup"><span data-stu-id="4939c-164">The **Category sales** report shows sales metrics over a selected period for each node of a category hierarchy for a selected channel or operating unit.</span></span>

<span data-ttu-id="4939c-165">A **Kategória értékesítései** jelentés létrehozásához hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="4939c-165">To generate a **Category sales** report, follow these steps.</span></span>

1. <span data-ttu-id="4939c-166">Ugorjon a **Kiskereskedelem \> Lekérdezések és jelentések \> Értékesítési jelentések \> Értékesítési kategória-jelentés** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4939c-166">Go to **Retail \> Inquiries and reports \> Sales reports \> Category sales report**.</span></span>
1. <span data-ttu-id="4939c-167">Adjon meg egy dátumot a **Kezdő dátum** mezőben.</span><span class="sxs-lookup"><span data-stu-id="4939c-167">In the **From date** field, enter a date.</span></span>
1. <span data-ttu-id="4939c-168">Adjon meg egy dátumot a **Záró dátum** mezőben.</span><span class="sxs-lookup"><span data-stu-id="4939c-168">In the **To date** field, enter a date.</span></span>
1. <span data-ttu-id="4939c-169">Válassza ki az online csatornát a **Csatorna** mezőben.</span><span class="sxs-lookup"><span data-stu-id="4939c-169">In the **Channel** field, select the online channel.</span></span>
1. <span data-ttu-id="4939c-170">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4939c-170">Select **OK**.</span></span>

## <a name="organization-sales-report"></a><span data-ttu-id="4939c-171">Szervezeti értékesítés – jelentés</span><span class="sxs-lookup"><span data-stu-id="4939c-171">Organization sales report</span></span>

<span data-ttu-id="4939c-172">A **Szervezeti értékesítés** jelentés a szervezeti egység szerint jeleníti meg a kiskereskedelmi üzletek teljesítményét.</span><span class="sxs-lookup"><span data-stu-id="4939c-172">The **Organization sales** report shows the performance of your retail stores by organization unit.</span></span> <span data-ttu-id="4939c-173">Ez a jelentés tartalmazza az értékesítési mennyiséget és az összeget üzletenként, valamint az egyes üzletek haszonkulcsát.</span><span class="sxs-lookup"><span data-stu-id="4939c-173">This report includes the sales quantity and amount by store, and the profit margin for each store.</span></span> <span data-ttu-id="4939c-174">A szervezeti egység az alapértelmezett jelentési hierarchián alapul.</span><span class="sxs-lookup"><span data-stu-id="4939c-174">The organization unit is based on the default reporting hierarchy.</span></span>

<span data-ttu-id="4939c-175">Egy **Szervezeti értékesítés** jelentés létrehozásához hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="4939c-175">To generate an **Organization sales** report, follow these steps.</span></span>

1. <span data-ttu-id="4939c-176">Ugorjon a **Kiskereskedelem \> Lekérdezések és jelentések \> Értékesítési jelentések \> Szervezeti értékesítési jelentés** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4939c-176">Go to **Retail \> Inquiries and reports \> Sales reports \> Organization sales report**.</span></span>
1. <span data-ttu-id="4939c-177">Adjon meg egy dátumot a **Kezdő dátum** mezőben.</span><span class="sxs-lookup"><span data-stu-id="4939c-177">In the **From date** field, enter a date.</span></span>
1. <span data-ttu-id="4939c-178">Adjon meg egy dátumot a **Záró dátum** mezőben.</span><span class="sxs-lookup"><span data-stu-id="4939c-178">In the **To date** field, enter a date.</span></span>
1. <span data-ttu-id="4939c-179">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4939c-179">Select **OK**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4939c-180">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="4939c-180">Additional resources</span></span>

- [<span data-ttu-id="4939c-181">Súgóerőforrások: Dynamics 365 Retail</span><span class="sxs-lookup"><span data-stu-id="4939c-181">Help resources for Dynamics 365 Retail</span></span>](../retail/index.md)
