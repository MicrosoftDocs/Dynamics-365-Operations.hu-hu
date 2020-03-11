---
title: Online csatornajelentések készítése
description: Ez a témakör azt mutatja be, hogyan lehet jelentéseket létrehozni egy online csatornához a Microsoft Dynamics 365 Commerce alkalmazásban.
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
ms.openlocfilehash: ae7b73c7a51ffa606876072d607fc219f5f6a2ba
ms.sourcegitcommit: 12b9d6f2dd24e52e46487748c848864909af6967
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/14/2020
ms.locfileid: "3057590"
---
# <a name="generate-online-channel-reports"></a><span data-ttu-id="38523-103">Online csatornajelentések készítése</span><span class="sxs-lookup"><span data-stu-id="38523-103">Generate online channel reports</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="38523-104">Ez a témakör azt mutatja be, hogyan lehet jelentéseket létrehozni egy online csatornához a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="38523-104">This topic describes how to generate reports for your online channel in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="38523-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="38523-105">Overview</span></span>

<span data-ttu-id="38523-106">A Commerce alkalmazásban számos jelentés létrehozható és tekinthető meg, hogy megtudja, hogyan teljesít online csatornája.</span><span class="sxs-lookup"><span data-stu-id="38523-106">You can generate and view several reports in Commerce to see how your online channel is performing.</span></span>

## <a name="channel-summary-report"></a><span data-ttu-id="38523-107">Csatorna-összefoglaló jelentés</span><span class="sxs-lookup"><span data-stu-id="38523-107">Channel summary report</span></span>

<span data-ttu-id="38523-108">A **Csatorna-összefoglaló** jelentés a következő tranzakciók összesítését jeleníti meg a kiválasztott csatornához:</span><span class="sxs-lookup"><span data-stu-id="38523-108">The **Channel summary** report shows a summary of the following transactions for the selected channel:</span></span>

- <span data-ttu-id="38523-109">Értékesítési tranzakciók</span><span class="sxs-lookup"><span data-stu-id="38523-109">Sales transactions</span></span>
- <span data-ttu-id="38523-110">Fizetési tranzakciók</span><span class="sxs-lookup"><span data-stu-id="38523-110">Payment transactions</span></span>
- <span data-ttu-id="38523-111">Adótranzakciók</span><span class="sxs-lookup"><span data-stu-id="38523-111">Tax transactions</span></span>
- <span data-ttu-id="38523-112">Engedményes tranzakciók</span><span class="sxs-lookup"><span data-stu-id="38523-112">Discounted transactions</span></span>

<span data-ttu-id="38523-113">A **Csatorna-összesítő** jelentés létrehozásához hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="38523-113">To generate a **Channel summary** report, follow these steps.</span></span>

1. <span data-ttu-id="38523-114">Nyissa meg a **Retail és Commerce \> Lekérdezések és jelentések \> Értékesítési jelentések \> Csatornaösszesítő-jelentés** elemet.</span><span class="sxs-lookup"><span data-stu-id="38523-114">Go to **Retail and Commerce \> Inquiries and reports \> Sales reports \> Channel summary report**.</span></span>
1. <span data-ttu-id="38523-115">Adjon meg egy dátumot a **Kezdő dátum** mezőben.</span><span class="sxs-lookup"><span data-stu-id="38523-115">In the **From date** field, enter a date.</span></span>
1. <span data-ttu-id="38523-116">Adjon meg egy dátumot a **Záró dátum** mezőben.</span><span class="sxs-lookup"><span data-stu-id="38523-116">In the **To date** field, enter a date.</span></span>
1. <span data-ttu-id="38523-117">Válassza ki az online csatornát a **Csatorna** mezőben.</span><span class="sxs-lookup"><span data-stu-id="38523-117">In the **Channel** field, select the online channel.</span></span>
1. <span data-ttu-id="38523-118">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="38523-118">Select **OK**.</span></span>
 
## <a name="channel-sales-by-year-report"></a><span data-ttu-id="38523-119">Csatorna értékesítése év szerint – jelentés</span><span class="sxs-lookup"><span data-stu-id="38523-119">Channel sales by year report</span></span> 

<span data-ttu-id="38523-120">A **Csatorna értékesítése év szerint** jelentés egy adott üzlet értékesítésének évek szerinti összehasonlítását jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="38523-120">The **Channel sales by year** report shows a comparison of year-over-year sales for a specific store.</span></span> <span data-ttu-id="38523-121">Válassza ki az évet, amelyhez hasonlítani szeretné az értékesítést, és a jelentés összeveti a kiválasztott év értékesítéseit az előző évhez képest.</span><span class="sxs-lookup"><span data-stu-id="38523-121">You select the year to compare the sales against, and the report compares sales for the selected year with sales for the previous year.</span></span>

<span data-ttu-id="38523-122">A **Csatorna értékesítése év szerint** jelentés létrehozásához hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="38523-122">To generate a **Channel sales by year** report, follow these steps.</span></span>

1. <span data-ttu-id="38523-123">Nyissa meg a **Retail és Commerce \> Lekérdezések és jelentések \> Értékesítési jelentések \> Csatorna értékesítése év szerint – jelentés** elemet.</span><span class="sxs-lookup"><span data-stu-id="38523-123">Go to **Retail and Commerce \> Inquiries and reports \> Sales reports \> Channel sales by year report**.</span></span>
1. <span data-ttu-id="38523-124">Adjon meg egy évet a **Kezdő naptári év** mezőben.</span><span class="sxs-lookup"><span data-stu-id="38523-124">In the **From calendar year** field, enter a year.</span></span>
1. <span data-ttu-id="38523-125">Adjon meg egy évet a **Befejező naptári év** mezőben.</span><span class="sxs-lookup"><span data-stu-id="38523-125">In the **To calendar year** field, enter a year.</span></span>
1. <span data-ttu-id="38523-126">Válassza ki az online csatornát a **Csatorna** mezőben.</span><span class="sxs-lookup"><span data-stu-id="38523-126">In the **Channel** field, select the online channel.</span></span>
1. <span data-ttu-id="38523-127">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="38523-127">Select **OK**.</span></span>

## <a name="channel-sales-by-hour-report"></a><span data-ttu-id="38523-128">Csatorna értékesítése óra szerint – jelentés</span><span class="sxs-lookup"><span data-stu-id="38523-128">Channel sales by hour report</span></span>

<span data-ttu-id="38523-129">A **Csatorna értékesítése óra szerint** jelentés megjeleníti az óránkénti értékesítési metrikákat a kiválasztott csatornához vagy üzemi egységhez.</span><span class="sxs-lookup"><span data-stu-id="38523-129">The **Channel sales by hour** report shows sales metrics per hour for a selected channel or operating unit.</span></span>

<span data-ttu-id="38523-130">A **Csatorna értékesítése óra szerint** jelentés létrehozásához hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="38523-130">To generate a **Channel sales by hour** report, follow these steps.</span></span>

1. <span data-ttu-id="38523-131">Nyissa meg a **Retail és Commerce \> Lekérdezések és jelentések \> Értékesítési jelentések \> Csatorna értékesítése óra szerint – jelentés** elemet.</span><span class="sxs-lookup"><span data-stu-id="38523-131">Go to **Retail and Commerce \> Inquiries and reports \> Sales reports \> Channel sales by hour report**.</span></span>
1. <span data-ttu-id="38523-132">Adjon meg egy dátumot a **Kezdő dátum** mezőben.</span><span class="sxs-lookup"><span data-stu-id="38523-132">In the **From date** field, enter a date.</span></span>
1. <span data-ttu-id="38523-133">Adjon meg egy dátumot a **Záró dátum** mezőben.</span><span class="sxs-lookup"><span data-stu-id="38523-133">In the **To date** field, enter a date.</span></span>
1. <span data-ttu-id="38523-134">Válassza ki az online csatornát a **Csatorna** mezőben.</span><span class="sxs-lookup"><span data-stu-id="38523-134">In the **Channel** field, select the online channel.</span></span>
1. <span data-ttu-id="38523-135">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="38523-135">Select **OK**.</span></span>

## <a name="top-customers-report"></a><span data-ttu-id="38523-136">Legfőbb vevők – jelentés</span><span class="sxs-lookup"><span data-stu-id="38523-136">Top customers report</span></span>

<span data-ttu-id="38523-137">A **Legfőbb vevők** jelentés megjeleníti a kiválasztott csatorna vagy üzemi egység felső *N* vevőinek értékesítési metrikáját.</span><span class="sxs-lookup"><span data-stu-id="38523-137">The **Top customers** report shows sales metrics for the top *N* customers for a selected channel or operating unit.</span></span> <span data-ttu-id="38523-138">Az *N* érték egy 10 és 100 közötti szám, amely a felhasználó által kiválasztott összesítő mérőszámon alapul.</span><span class="sxs-lookup"><span data-stu-id="38523-138">The value *N* is a number from 10 to 100 and is based on a user-selected aggregate measure.</span></span>

<span data-ttu-id="38523-139">A **Legfőbb vevők** jelentés létrehozásához hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="38523-139">To generate a **Top customers** report, follow these steps.</span></span>

1. <span data-ttu-id="38523-140">Nyissa meg a **Retail és Commerce \> Lekérdezések és jelentések \> Értékesítési jelentések \> Legfőbb vevők – jelentés** elemet.</span><span class="sxs-lookup"><span data-stu-id="38523-140">Go to **Retail and Commerce \> Inquiries and reports \> Sales reports \> Top customers report**.</span></span>
1. <span data-ttu-id="38523-141">Adjon meg egy dátumot a **Kezdő dátum** mezőben.</span><span class="sxs-lookup"><span data-stu-id="38523-141">In the **From date** field, enter a date.</span></span>
1. <span data-ttu-id="38523-142">Adjon meg egy dátumot a **Záró dátum** mezőben.</span><span class="sxs-lookup"><span data-stu-id="38523-142">In the **To date** field, enter a date.</span></span>
1. <span data-ttu-id="38523-143">Válassza ki az online csatornát a **Csatorna** mezőben.</span><span class="sxs-lookup"><span data-stu-id="38523-143">In the **Channel** field, select the online channel.</span></span>
1. <span data-ttu-id="38523-144">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="38523-144">Select **OK**.</span></span>

## <a name="top-discounts-report"></a><span data-ttu-id="38523-145">Legnagyobb engedmények jelentése</span><span class="sxs-lookup"><span data-stu-id="38523-145">Top discounts report</span></span>

<span data-ttu-id="38523-146">A **Legnagyobb engedmények** jelentés megjeleníti a kiválasztott csatorna vagy üzemi egység legnagyobb *N* kedvezményének értékesítési metrikáját.</span><span class="sxs-lookup"><span data-stu-id="38523-146">The **Top discounts** report shows sales metrics for the top *N* discounts for a selected channel or operating unit.</span></span> <span data-ttu-id="38523-147">Az *N* érték egy 10 és 100 közötti szám, amely a felhasználó által kiválasztott összesítő mérőszámon alapul.</span><span class="sxs-lookup"><span data-stu-id="38523-147">The value *N* is a number from 10 to 100 and is based on a user-selected aggregate measure.</span></span>

<span data-ttu-id="38523-148">A **Legnagyobb engedmények** jelentés létrehozásához hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="38523-148">To generate a **Top discounts** report, follow these steps.</span></span>

1. <span data-ttu-id="38523-149">Nyissa meg a **Retail és Commerce \> Lekérdezések és jelentések \> Értékesítési jelentések \> Legnagyobb engedmények jelentése** elemet.</span><span class="sxs-lookup"><span data-stu-id="38523-149">Go to **Retail and Commerce \> Inquiries and reports \> Sales reports \> Top discounts report**.</span></span>
1. <span data-ttu-id="38523-150">Adjon meg egy dátumot a **Kezdő dátum** mezőben.</span><span class="sxs-lookup"><span data-stu-id="38523-150">In the **From date** field, enter a date.</span></span>
1. <span data-ttu-id="38523-151">Adjon meg egy dátumot a **Záró dátum** mezőben.</span><span class="sxs-lookup"><span data-stu-id="38523-151">In the **To date** field, enter a date.</span></span>
1. <span data-ttu-id="38523-152">Válassza ki az online csatornát a **Csatorna** mezőben.</span><span class="sxs-lookup"><span data-stu-id="38523-152">In the **Channel** field, select the online channel.</span></span>
1. <span data-ttu-id="38523-153">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="38523-153">Select **OK**.</span></span>

## <a name="top-products-report"></a><span data-ttu-id="38523-154">Vezető termékek jelentése</span><span class="sxs-lookup"><span data-stu-id="38523-154">Top products report</span></span>

<span data-ttu-id="38523-155">A **Vezető termékek** jelentés megjeleníti a kiválasztott csatorna vagy üzemi egység vezető *N* termék értékesítési metrikáját.</span><span class="sxs-lookup"><span data-stu-id="38523-155">The **Top products** report shows sales metrics for the top *N* products for a selected channel or operating unit.</span></span> <span data-ttu-id="38523-156">Az *N* érték egy 10 és 100 közötti szám, amely a felhasználó által kiválasztott összesítő mérőszámon alapul.</span><span class="sxs-lookup"><span data-stu-id="38523-156">The value *N* is a number from 10 to 100 and is based on a user-selected aggregate measure.</span></span>

<span data-ttu-id="38523-157">A **Vezető termékek** jelentés létrehozásához hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="38523-157">To generate a **Top products** report, follow these steps.</span></span>

1. <span data-ttu-id="38523-158">Nyissa meg a **Retail és Commerce \> Lekérdezések és jelentések \> Értékesítési jelentések \> Vezető termékek jelentése** elemet.</span><span class="sxs-lookup"><span data-stu-id="38523-158">Go to **Retail and Commerce \> Inquiries and reports \> Sales reports \> Top products report**.</span></span>
1. <span data-ttu-id="38523-159">Adjon meg egy dátumot a **Kezdő dátum** mezőben.</span><span class="sxs-lookup"><span data-stu-id="38523-159">In the **From date** field, enter a date.</span></span>
1. <span data-ttu-id="38523-160">Adjon meg egy dátumot a **Záró dátum** mezőben.</span><span class="sxs-lookup"><span data-stu-id="38523-160">In the **To date** field, enter a date.</span></span>
1. <span data-ttu-id="38523-161">Válassza ki az online csatornát a **Csatorna** mezőben.</span><span class="sxs-lookup"><span data-stu-id="38523-161">In the **Channel** field, select the online channel.</span></span>
1. <span data-ttu-id="38523-162">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="38523-162">Select **OK**.</span></span>

## <a name="category-sales-report"></a><span data-ttu-id="38523-163">Kategória értékesítése – jelentés</span><span class="sxs-lookup"><span data-stu-id="38523-163">Category sales report</span></span>

<span data-ttu-id="38523-164">A **Kategória értékesítései** jelentés egy kiválasztott időszakra vonatkozóan megjeleníti az értékesítési mérőszámokat a kiválasztott csatornához vagy üzemi egységhez tartozó kategória-hierarchia egyes csomópontjaihoz.</span><span class="sxs-lookup"><span data-stu-id="38523-164">The **Category sales** report shows sales metrics over a selected period for each node of a category hierarchy for a selected channel or operating unit.</span></span>

<span data-ttu-id="38523-165">A **Kategória értékesítései** jelentés létrehozásához hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="38523-165">To generate a **Category sales** report, follow these steps.</span></span>

1. <span data-ttu-id="38523-166">Lépjen a **Retail és Commerce \> Lekérdezések és jelentések \> Értékesítési jelentések \> Értékesítési kategória-jelentés** elemre.</span><span class="sxs-lookup"><span data-stu-id="38523-166">Go to **Retail and Commerce \> Inquiries and reports \> Sales reports \> Category sales report**.</span></span>
1. <span data-ttu-id="38523-167">Adjon meg egy dátumot a **Kezdő dátum** mezőben.</span><span class="sxs-lookup"><span data-stu-id="38523-167">In the **From date** field, enter a date.</span></span>
1. <span data-ttu-id="38523-168">Adjon meg egy dátumot a **Záró dátum** mezőben.</span><span class="sxs-lookup"><span data-stu-id="38523-168">In the **To date** field, enter a date.</span></span>
1. <span data-ttu-id="38523-169">Válassza ki az online csatornát a **Csatorna** mezőben.</span><span class="sxs-lookup"><span data-stu-id="38523-169">In the **Channel** field, select the online channel.</span></span>
1. <span data-ttu-id="38523-170">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="38523-170">Select **OK**.</span></span>

## <a name="organization-sales-report"></a><span data-ttu-id="38523-171">Szervezeti értékesítés – jelentés</span><span class="sxs-lookup"><span data-stu-id="38523-171">Organization sales report</span></span>

<span data-ttu-id="38523-172">A **Szervezeti értékesítés** jelentés a szervezeti egység szerint jeleníti meg az üzletek teljesítményét.</span><span class="sxs-lookup"><span data-stu-id="38523-172">The **Organization sales** report shows the performance of your stores by organization unit.</span></span> <span data-ttu-id="38523-173">Ez a jelentés tartalmazza az értékesítési mennyiséget és az összeget üzletenként, valamint az egyes üzletek haszonkulcsát.</span><span class="sxs-lookup"><span data-stu-id="38523-173">This report includes the sales quantity and amount by store, and the profit margin for each store.</span></span> <span data-ttu-id="38523-174">A szervezeti egység az alapértelmezett jelentési hierarchián alapul.</span><span class="sxs-lookup"><span data-stu-id="38523-174">The organization unit is based on the default reporting hierarchy.</span></span>

<span data-ttu-id="38523-175">Egy **Szervezeti értékesítés** jelentés létrehozásához hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="38523-175">To generate an **Organization sales** report, follow these steps.</span></span>

1. <span data-ttu-id="38523-176">Ugorjon a **Retail és Commerce \> Lekérdezések és jelentések \> Értékesítési jelentések \> Szervezeti kategória-jelentés** elemre.</span><span class="sxs-lookup"><span data-stu-id="38523-176">Go to **Retail and Commerce \> Inquiries and reports \> Sales reports \> Organization sales report**.</span></span>
1. <span data-ttu-id="38523-177">Adjon meg egy dátumot a **Kezdő dátum** mezőben.</span><span class="sxs-lookup"><span data-stu-id="38523-177">In the **From date** field, enter a date.</span></span>
1. <span data-ttu-id="38523-178">Adjon meg egy dátumot a **Záró dátum** mezőben.</span><span class="sxs-lookup"><span data-stu-id="38523-178">In the **To date** field, enter a date.</span></span>
1. <span data-ttu-id="38523-179">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="38523-179">Select **OK**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="38523-180">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="38523-180">Additional resources</span></span>

- [<span data-ttu-id="38523-181">Commerce kezdőlap</span><span class="sxs-lookup"><span data-stu-id="38523-181">Commerce home page</span></span>](../retail/index.md)
