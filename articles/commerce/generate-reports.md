---
title: Online csatornajelentések készítése
description: Ez a témakör azt mutatja be, hogyan lehet jelentéseket létrehozni egy online csatornához a Microsoft Dynamics 365 Commerce alkalmazásban.
author: psimolin
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: f70f42f2650a439c7131f228588c11124d326aec
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5792367"
---
# <a name="generate-online-channel-reports"></a><span data-ttu-id="1be13-103">Online csatornajelentések készítése</span><span class="sxs-lookup"><span data-stu-id="1be13-103">Generate online channel reports</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="1be13-104">Ez a témakör azt mutatja be, hogyan lehet jelentéseket létrehozni egy online csatornához a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="1be13-104">This topic describes how to generate reports for your online channel in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="1be13-105">A Commerce alkalmazásban számos jelentés létrehozható és tekinthető meg, hogy megtudja, hogyan teljesít online csatornája.</span><span class="sxs-lookup"><span data-stu-id="1be13-105">You can generate and view several reports in Commerce to see how your online channel is performing.</span></span>

## <a name="channel-summary-report"></a><span data-ttu-id="1be13-106">Csatorna-összefoglaló jelentés</span><span class="sxs-lookup"><span data-stu-id="1be13-106">Channel summary report</span></span>

<span data-ttu-id="1be13-107">A **Csatorna-összefoglaló** jelentés a következő tranzakciók összesítését jeleníti meg a kiválasztott csatornához:</span><span class="sxs-lookup"><span data-stu-id="1be13-107">The **Channel summary** report shows a summary of the following transactions for the selected channel:</span></span>

- <span data-ttu-id="1be13-108">Értékesítési tranzakciók</span><span class="sxs-lookup"><span data-stu-id="1be13-108">Sales transactions</span></span>
- <span data-ttu-id="1be13-109">Fizetési tranzakciók</span><span class="sxs-lookup"><span data-stu-id="1be13-109">Payment transactions</span></span>
- <span data-ttu-id="1be13-110">Adótranzakciók</span><span class="sxs-lookup"><span data-stu-id="1be13-110">Tax transactions</span></span>
- <span data-ttu-id="1be13-111">Engedményes tranzakciók</span><span class="sxs-lookup"><span data-stu-id="1be13-111">Discounted transactions</span></span>

<span data-ttu-id="1be13-112">A **Csatorna-összesítő** jelentés létrehozásához hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="1be13-112">To generate a **Channel summary** report, follow these steps.</span></span>

1. <span data-ttu-id="1be13-113">Nyissa meg a **Retail és Commerce \> Lekérdezések és jelentések \> Értékesítési jelentések \> Csatornaösszesítő-jelentés** elemet.</span><span class="sxs-lookup"><span data-stu-id="1be13-113">Go to **Retail and Commerce \> Inquiries and reports \> Sales reports \> Channel summary report**.</span></span>
1. <span data-ttu-id="1be13-114">Adjon meg egy dátumot a **Kezdő dátum** mezőben.</span><span class="sxs-lookup"><span data-stu-id="1be13-114">In the **From date** field, enter a date.</span></span>
1. <span data-ttu-id="1be13-115">Adjon meg egy dátumot a **Záró dátum** mezőben.</span><span class="sxs-lookup"><span data-stu-id="1be13-115">In the **To date** field, enter a date.</span></span>
1. <span data-ttu-id="1be13-116">Válassza ki az online csatornát a **Csatorna** mezőben.</span><span class="sxs-lookup"><span data-stu-id="1be13-116">In the **Channel** field, select the online channel.</span></span>
1. <span data-ttu-id="1be13-117">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1be13-117">Select **OK**.</span></span>
 
## <a name="channel-sales-by-year-report"></a><span data-ttu-id="1be13-118">Csatorna értékesítése év szerint – jelentés</span><span class="sxs-lookup"><span data-stu-id="1be13-118">Channel sales by year report</span></span> 

<span data-ttu-id="1be13-119">A **Csatorna értékesítése év szerint** jelentés egy adott üzlet értékesítésének évek szerinti összehasonlítását jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="1be13-119">The **Channel sales by year** report shows a comparison of year-over-year sales for a specific store.</span></span> <span data-ttu-id="1be13-120">Válassza ki az évet, amelyhez hasonlítani szeretné az értékesítést, és a jelentés összeveti a kiválasztott év értékesítéseit az előző évhez képest.</span><span class="sxs-lookup"><span data-stu-id="1be13-120">You select the year to compare the sales against, and the report compares sales for the selected year with sales for the previous year.</span></span>

<span data-ttu-id="1be13-121">A **Csatorna értékesítése év szerint** jelentés létrehozásához hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="1be13-121">To generate a **Channel sales by year** report, follow these steps.</span></span>

1. <span data-ttu-id="1be13-122">Nyissa meg a **Retail és Commerce \> Lekérdezések és jelentések \> Értékesítési jelentések \> Csatorna értékesítése év szerint – jelentés** elemet.</span><span class="sxs-lookup"><span data-stu-id="1be13-122">Go to **Retail and Commerce \> Inquiries and reports \> Sales reports \> Channel sales by year report**.</span></span>
1. <span data-ttu-id="1be13-123">Adjon meg egy évet a **Kezdő naptári év** mezőben.</span><span class="sxs-lookup"><span data-stu-id="1be13-123">In the **From calendar year** field, enter a year.</span></span>
1. <span data-ttu-id="1be13-124">Adjon meg egy évet a **Befejező naptári év** mezőben.</span><span class="sxs-lookup"><span data-stu-id="1be13-124">In the **To calendar year** field, enter a year.</span></span>
1. <span data-ttu-id="1be13-125">Válassza ki az online csatornát a **Csatorna** mezőben.</span><span class="sxs-lookup"><span data-stu-id="1be13-125">In the **Channel** field, select the online channel.</span></span>
1. <span data-ttu-id="1be13-126">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1be13-126">Select **OK**.</span></span>

## <a name="channel-sales-by-hour-report"></a><span data-ttu-id="1be13-127">Csatorna értékesítése óra szerint – jelentés</span><span class="sxs-lookup"><span data-stu-id="1be13-127">Channel sales by hour report</span></span>

<span data-ttu-id="1be13-128">A **Csatorna értékesítése óra szerint** jelentés megjeleníti az óránkénti értékesítési metrikákat a kiválasztott csatornához vagy üzemi egységhez.</span><span class="sxs-lookup"><span data-stu-id="1be13-128">The **Channel sales by hour** report shows sales metrics per hour for a selected channel or operating unit.</span></span>

<span data-ttu-id="1be13-129">A **Csatorna értékesítése óra szerint** jelentés létrehozásához hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="1be13-129">To generate a **Channel sales by hour** report, follow these steps.</span></span>

1. <span data-ttu-id="1be13-130">Nyissa meg a **Retail és Commerce \> Lekérdezések és jelentések \> Értékesítési jelentések \> Csatorna értékesítése óra szerint – jelentés** elemet.</span><span class="sxs-lookup"><span data-stu-id="1be13-130">Go to **Retail and Commerce \> Inquiries and reports \> Sales reports \> Channel sales by hour report**.</span></span>
1. <span data-ttu-id="1be13-131">Adjon meg egy dátumot a **Kezdő dátum** mezőben.</span><span class="sxs-lookup"><span data-stu-id="1be13-131">In the **From date** field, enter a date.</span></span>
1. <span data-ttu-id="1be13-132">Adjon meg egy dátumot a **Záró dátum** mezőben.</span><span class="sxs-lookup"><span data-stu-id="1be13-132">In the **To date** field, enter a date.</span></span>
1. <span data-ttu-id="1be13-133">Válassza ki az online csatornát a **Csatorna** mezőben.</span><span class="sxs-lookup"><span data-stu-id="1be13-133">In the **Channel** field, select the online channel.</span></span>
1. <span data-ttu-id="1be13-134">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1be13-134">Select **OK**.</span></span>

## <a name="top-customers-report"></a><span data-ttu-id="1be13-135">Legfőbb vevők – jelentés</span><span class="sxs-lookup"><span data-stu-id="1be13-135">Top customers report</span></span>

<span data-ttu-id="1be13-136">A **Legfőbb vevők** jelentés megjeleníti a kiválasztott csatorna vagy üzemi egység felső *N* vevőinek értékesítési metrikáját.</span><span class="sxs-lookup"><span data-stu-id="1be13-136">The **Top customers** report shows sales metrics for the top *N* customers for a selected channel or operating unit.</span></span> <span data-ttu-id="1be13-137">Az *N* érték egy 10 és 100 közötti szám, amely a felhasználó által kiválasztott összesítő mérőszámon alapul.</span><span class="sxs-lookup"><span data-stu-id="1be13-137">The value *N* is a number from 10 to 100 and is based on a user-selected aggregate measure.</span></span>

<span data-ttu-id="1be13-138">A **Legfőbb vevők** jelentés létrehozásához hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="1be13-138">To generate a **Top customers** report, follow these steps.</span></span>

1. <span data-ttu-id="1be13-139">Nyissa meg a **Retail és Commerce \> Lekérdezések és jelentések \> Értékesítési jelentések \> Legfőbb vevők – jelentés** elemet.</span><span class="sxs-lookup"><span data-stu-id="1be13-139">Go to **Retail and Commerce \> Inquiries and reports \> Sales reports \> Top customers report**.</span></span>
1. <span data-ttu-id="1be13-140">Adjon meg egy dátumot a **Kezdő dátum** mezőben.</span><span class="sxs-lookup"><span data-stu-id="1be13-140">In the **From date** field, enter a date.</span></span>
1. <span data-ttu-id="1be13-141">Adjon meg egy dátumot a **Záró dátum** mezőben.</span><span class="sxs-lookup"><span data-stu-id="1be13-141">In the **To date** field, enter a date.</span></span>
1. <span data-ttu-id="1be13-142">Válassza ki az online csatornát a **Csatorna** mezőben.</span><span class="sxs-lookup"><span data-stu-id="1be13-142">In the **Channel** field, select the online channel.</span></span>
1. <span data-ttu-id="1be13-143">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1be13-143">Select **OK**.</span></span>

## <a name="top-discounts-report"></a><span data-ttu-id="1be13-144">Legnagyobb engedmények jelentése</span><span class="sxs-lookup"><span data-stu-id="1be13-144">Top discounts report</span></span>

<span data-ttu-id="1be13-145">A **Legnagyobb engedmények** jelentés megjeleníti a kiválasztott csatorna vagy üzemi egység legnagyobb *N* kedvezményének értékesítési metrikáját.</span><span class="sxs-lookup"><span data-stu-id="1be13-145">The **Top discounts** report shows sales metrics for the top *N* discounts for a selected channel or operating unit.</span></span> <span data-ttu-id="1be13-146">Az *N* érték egy 10 és 100 közötti szám, amely a felhasználó által kiválasztott összesítő mérőszámon alapul.</span><span class="sxs-lookup"><span data-stu-id="1be13-146">The value *N* is a number from 10 to 100 and is based on a user-selected aggregate measure.</span></span>

<span data-ttu-id="1be13-147">A **Legnagyobb engedmények** jelentés létrehozásához hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="1be13-147">To generate a **Top discounts** report, follow these steps.</span></span>

1. <span data-ttu-id="1be13-148">Nyissa meg a **Retail és Commerce \> Lekérdezések és jelentések \> Értékesítési jelentések \> Legnagyobb engedmények jelentése** elemet.</span><span class="sxs-lookup"><span data-stu-id="1be13-148">Go to **Retail and Commerce \> Inquiries and reports \> Sales reports \> Top discounts report**.</span></span>
1. <span data-ttu-id="1be13-149">Adjon meg egy dátumot a **Kezdő dátum** mezőben.</span><span class="sxs-lookup"><span data-stu-id="1be13-149">In the **From date** field, enter a date.</span></span>
1. <span data-ttu-id="1be13-150">Adjon meg egy dátumot a **Záró dátum** mezőben.</span><span class="sxs-lookup"><span data-stu-id="1be13-150">In the **To date** field, enter a date.</span></span>
1. <span data-ttu-id="1be13-151">Válassza ki az online csatornát a **Csatorna** mezőben.</span><span class="sxs-lookup"><span data-stu-id="1be13-151">In the **Channel** field, select the online channel.</span></span>
1. <span data-ttu-id="1be13-152">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1be13-152">Select **OK**.</span></span>

## <a name="top-products-report"></a><span data-ttu-id="1be13-153">Vezető termékek jelentése</span><span class="sxs-lookup"><span data-stu-id="1be13-153">Top products report</span></span>

<span data-ttu-id="1be13-154">A **Vezető termékek** jelentés megjeleníti a kiválasztott csatorna vagy üzemi egység vezető *N* termék értékesítési metrikáját.</span><span class="sxs-lookup"><span data-stu-id="1be13-154">The **Top products** report shows sales metrics for the top *N* products for a selected channel or operating unit.</span></span> <span data-ttu-id="1be13-155">Az *N* érték egy 10 és 100 közötti szám, amely a felhasználó által kiválasztott összesítő mérőszámon alapul.</span><span class="sxs-lookup"><span data-stu-id="1be13-155">The value *N* is a number from 10 to 100 and is based on a user-selected aggregate measure.</span></span>

<span data-ttu-id="1be13-156">A **Vezető termékek** jelentés létrehozásához hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="1be13-156">To generate a **Top products** report, follow these steps.</span></span>

1. <span data-ttu-id="1be13-157">Nyissa meg a **Retail és Commerce \> Lekérdezések és jelentések \> Értékesítési jelentések \> Vezető termékek jelentése** elemet.</span><span class="sxs-lookup"><span data-stu-id="1be13-157">Go to **Retail and Commerce \> Inquiries and reports \> Sales reports \> Top products report**.</span></span>
1. <span data-ttu-id="1be13-158">Adjon meg egy dátumot a **Kezdő dátum** mezőben.</span><span class="sxs-lookup"><span data-stu-id="1be13-158">In the **From date** field, enter a date.</span></span>
1. <span data-ttu-id="1be13-159">Adjon meg egy dátumot a **Záró dátum** mezőben.</span><span class="sxs-lookup"><span data-stu-id="1be13-159">In the **To date** field, enter a date.</span></span>
1. <span data-ttu-id="1be13-160">Válassza ki az online csatornát a **Csatorna** mezőben.</span><span class="sxs-lookup"><span data-stu-id="1be13-160">In the **Channel** field, select the online channel.</span></span>
1. <span data-ttu-id="1be13-161">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1be13-161">Select **OK**.</span></span>

## <a name="category-sales-report"></a><span data-ttu-id="1be13-162">Kategória értékesítése – jelentés</span><span class="sxs-lookup"><span data-stu-id="1be13-162">Category sales report</span></span>

<span data-ttu-id="1be13-163">A **Kategória értékesítései** jelentés egy kiválasztott időszakra vonatkozóan megjeleníti az értékesítési mérőszámokat a kiválasztott csatornához vagy üzemi egységhez tartozó kategória-hierarchia egyes csomópontjaihoz.</span><span class="sxs-lookup"><span data-stu-id="1be13-163">The **Category sales** report shows sales metrics over a selected period for each node of a category hierarchy for a selected channel or operating unit.</span></span>

<span data-ttu-id="1be13-164">A **Kategória értékesítései** jelentés létrehozásához hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="1be13-164">To generate a **Category sales** report, follow these steps.</span></span>

1. <span data-ttu-id="1be13-165">Lépjen a **Retail és Commerce \> Lekérdezések és jelentések \> Értékesítési jelentések \> Értékesítési kategória-jelentés** elemre.</span><span class="sxs-lookup"><span data-stu-id="1be13-165">Go to **Retail and Commerce \> Inquiries and reports \> Sales reports \> Category sales report**.</span></span>
1. <span data-ttu-id="1be13-166">Adjon meg egy dátumot a **Kezdő dátum** mezőben.</span><span class="sxs-lookup"><span data-stu-id="1be13-166">In the **From date** field, enter a date.</span></span>
1. <span data-ttu-id="1be13-167">Adjon meg egy dátumot a **Záró dátum** mezőben.</span><span class="sxs-lookup"><span data-stu-id="1be13-167">In the **To date** field, enter a date.</span></span>
1. <span data-ttu-id="1be13-168">Válassza ki az online csatornát a **Csatorna** mezőben.</span><span class="sxs-lookup"><span data-stu-id="1be13-168">In the **Channel** field, select the online channel.</span></span>
1. <span data-ttu-id="1be13-169">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1be13-169">Select **OK**.</span></span>

## <a name="organization-sales-report"></a><span data-ttu-id="1be13-170">Szervezeti értékesítés – jelentés</span><span class="sxs-lookup"><span data-stu-id="1be13-170">Organization sales report</span></span>

<span data-ttu-id="1be13-171">A **Szervezeti értékesítés** jelentés a szervezeti egység szerint jeleníti meg az üzletek teljesítményét.</span><span class="sxs-lookup"><span data-stu-id="1be13-171">The **Organization sales** report shows the performance of your stores by organization unit.</span></span> <span data-ttu-id="1be13-172">Ez a jelentés tartalmazza az értékesítési mennyiséget és az összeget üzletenként, valamint az egyes üzletek haszonkulcsát.</span><span class="sxs-lookup"><span data-stu-id="1be13-172">This report includes the sales quantity and amount by store, and the profit margin for each store.</span></span> <span data-ttu-id="1be13-173">A szervezeti egység az alapértelmezett jelentési hierarchián alapul.</span><span class="sxs-lookup"><span data-stu-id="1be13-173">The organization unit is based on the default reporting hierarchy.</span></span>

<span data-ttu-id="1be13-174">Egy **Szervezeti értékesítés** jelentés létrehozásához hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="1be13-174">To generate an **Organization sales** report, follow these steps.</span></span>

1. <span data-ttu-id="1be13-175">Ugorjon a **Retail és Commerce \> Lekérdezések és jelentések \> Értékesítési jelentések \> Szervezeti kategória-jelentés** elemre.</span><span class="sxs-lookup"><span data-stu-id="1be13-175">Go to **Retail and Commerce \> Inquiries and reports \> Sales reports \> Organization sales report**.</span></span>
1. <span data-ttu-id="1be13-176">Adjon meg egy dátumot a **Kezdő dátum** mezőben.</span><span class="sxs-lookup"><span data-stu-id="1be13-176">In the **From date** field, enter a date.</span></span>
1. <span data-ttu-id="1be13-177">Adjon meg egy dátumot a **Záró dátum** mezőben.</span><span class="sxs-lookup"><span data-stu-id="1be13-177">In the **To date** field, enter a date.</span></span>
1. <span data-ttu-id="1be13-178">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1be13-178">Select **OK**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1be13-179">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="1be13-179">Additional resources</span></span>

- [<span data-ttu-id="1be13-180">Commerce kezdőlap</span><span class="sxs-lookup"><span data-stu-id="1be13-180">Commerce home page</span></span>](../retail/index.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
