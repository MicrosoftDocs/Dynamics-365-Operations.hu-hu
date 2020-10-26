---
title: Eőfizetés eladási árai
description: Amikor előfizetést hoz létre, az eladási ár az Eladási ár (előfizetés) képernyőn létrehozott eladási ár beállításból jön létre.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMASalespriceSubscription
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f03efbbca4fc9da76c6ead7566457beb79c8c249
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/10/2020
ms.locfileid: "3985865"
---
# <a name="subscription-sales-prices"></a><span data-ttu-id="b02d3-103">Eőfizetés eladási árai</span><span class="sxs-lookup"><span data-stu-id="b02d3-103">Subscription sales prices</span></span>   

[!include [banner](../includes/banner.md)]


<span data-ttu-id="b02d3-104">Amikor előfizetést hoz létre, az eladási ár az **Eladási ár (előfizetés)** képernyőn létrehozott eladási ár beállításból jön létre.</span><span class="sxs-lookup"><span data-stu-id="b02d3-104">When you create a subscription, the sales price is derived from the sales price setup that was created in the **Sales price (subscription)** form.</span></span>

<span data-ttu-id="b02d3-105">Az **Eladási ár (előfizetés)** képernyőn egy-egy előfizetéshez is készíthet eladási árat, vagy létrehozhat olyan eladási árat, amely általánosabban érvényes.</span><span class="sxs-lookup"><span data-stu-id="b02d3-105">In the **Sales price (subscription)** form, you can create sales prices for a specific subscription or you can create sales prices that apply more broadly.</span></span> <span data-ttu-id="b02d3-106">Az eladási ár alkalmazásához az előfizetésre, meg kell egyeznie az előfizetés időszakkódjának és pénznemének az eladási ár időszakkódjával és pénznemével.</span><span class="sxs-lookup"><span data-stu-id="b02d3-106">For a sales price to be applied to a subscription, the period code and the currency of the subscription must be identical to the period code and the currency of the sales price.</span></span>

<span data-ttu-id="b02d3-107">Ha az előfizetés és az eladási ár időszakkódja és pénzneme megegyezik, akkor az előfizetés eladási ára az alábbi táblázatban szereplő prioritások alapján választható ki.</span><span class="sxs-lookup"><span data-stu-id="b02d3-107">If the period code and currency are identical for the subscription and the sales price, subscription sales prices are selected on the basis of the priorities listed in the following table.</span></span> <span data-ttu-id="b02d3-108">Az üres cella üres mezőt, az X pedig a előfizetésből létrejött tranzakcióban szereplő értékkel megegyező értéket jelent.</span><span class="sxs-lookup"><span data-stu-id="b02d3-108">A blank cell in the table indicates an empty field and an X indicates a value that is equal to the value in the subscription from which the transaction is generated.</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="b02d3-109">. prioritás</span><span class="sxs-lookup"><span data-stu-id="b02d3-109">Priority</span></span></p></th>
<th><p><span data-ttu-id="b02d3-110"><strong>Kategória</strong></span><span class="sxs-lookup"><span data-stu-id="b02d3-110"><strong>Category</strong></span></span></p></th>
<th><p><span data-ttu-id="b02d3-111"><strong>Projektazonosító</strong></span><span class="sxs-lookup"><span data-stu-id="b02d3-111"><strong>Project ID</strong></span></span></p></th>
<th><p><span data-ttu-id="b02d3-112"><strong>Előfizetés</strong></span><span class="sxs-lookup"><span data-stu-id="b02d3-112"><strong>Subscription</strong></span></span></p></th>
<th><p><span data-ttu-id="b02d3-113"><strong>Értékesítés pénzneme</strong></span><span class="sxs-lookup"><span data-stu-id="b02d3-113"><strong>Sales currency</strong></span></span></p></th>
<th><p><span data-ttu-id="b02d3-114"><strong>Időszak kódja</strong></span><span class="sxs-lookup"><span data-stu-id="b02d3-114"><strong>Period code</strong></span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b02d3-115">1</span><span class="sxs-lookup"><span data-stu-id="b02d3-115">1</span></span></p></td>
<td><p><span data-ttu-id="b02d3-116">X</span><span class="sxs-lookup"><span data-stu-id="b02d3-116">X</span></span></p></td>
<td><p><span data-ttu-id="b02d3-117">X</span><span class="sxs-lookup"><span data-stu-id="b02d3-117">X</span></span></p></td>
<td><p><span data-ttu-id="b02d3-118">X</span><span class="sxs-lookup"><span data-stu-id="b02d3-118">X</span></span></p></td>
<td><p><span data-ttu-id="b02d3-119">X</span><span class="sxs-lookup"><span data-stu-id="b02d3-119">X</span></span></p></td>
<td><p><span data-ttu-id="b02d3-120">X</span><span class="sxs-lookup"><span data-stu-id="b02d3-120">X</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b02d3-121">2</span><span class="sxs-lookup"><span data-stu-id="b02d3-121">2</span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="b02d3-122">X</span><span class="sxs-lookup"><span data-stu-id="b02d3-122">X</span></span></p></td>
<td><p><span data-ttu-id="b02d3-123">X</span><span class="sxs-lookup"><span data-stu-id="b02d3-123">X</span></span></p></td>
<td><p><span data-ttu-id="b02d3-124">X</span><span class="sxs-lookup"><span data-stu-id="b02d3-124">X</span></span></p></td>
<td><p><span data-ttu-id="b02d3-125">X</span><span class="sxs-lookup"><span data-stu-id="b02d3-125">X</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b02d3-126">3</span><span class="sxs-lookup"><span data-stu-id="b02d3-126">3</span></span></p></td>
<td><p><span data-ttu-id="b02d3-127">X</span><span class="sxs-lookup"><span data-stu-id="b02d3-127">X</span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="b02d3-128">X</span><span class="sxs-lookup"><span data-stu-id="b02d3-128">X</span></span></p></td>
<td><p><span data-ttu-id="b02d3-129">X</span><span class="sxs-lookup"><span data-stu-id="b02d3-129">X</span></span></p></td>
<td><p><span data-ttu-id="b02d3-130">X</span><span class="sxs-lookup"><span data-stu-id="b02d3-130">X</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b02d3-131">4</span><span class="sxs-lookup"><span data-stu-id="b02d3-131">4</span></span></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="b02d3-132">X</span><span class="sxs-lookup"><span data-stu-id="b02d3-132">X</span></span></p></td>
<td><p><span data-ttu-id="b02d3-133">X</span><span class="sxs-lookup"><span data-stu-id="b02d3-133">X</span></span></p></td>
<td><p><span data-ttu-id="b02d3-134">X</span><span class="sxs-lookup"><span data-stu-id="b02d3-134">X</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b02d3-135">5</span><span class="sxs-lookup"><span data-stu-id="b02d3-135">5</span></span></p></td>
<td><p><span data-ttu-id="b02d3-136">X</span><span class="sxs-lookup"><span data-stu-id="b02d3-136">X</span></span></p></td>
<td><p><span data-ttu-id="b02d3-137">X</span><span class="sxs-lookup"><span data-stu-id="b02d3-137">X</span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="b02d3-138">X</span><span class="sxs-lookup"><span data-stu-id="b02d3-138">X</span></span></p></td>
<td><p><span data-ttu-id="b02d3-139">X</span><span class="sxs-lookup"><span data-stu-id="b02d3-139">X</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b02d3-140">6</span><span class="sxs-lookup"><span data-stu-id="b02d3-140">6</span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="b02d3-141">X</span><span class="sxs-lookup"><span data-stu-id="b02d3-141">X</span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="b02d3-142">X</span><span class="sxs-lookup"><span data-stu-id="b02d3-142">X</span></span></p></td>
<td><p><span data-ttu-id="b02d3-143">X</span><span class="sxs-lookup"><span data-stu-id="b02d3-143">X</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b02d3-144">7</span><span class="sxs-lookup"><span data-stu-id="b02d3-144">7</span></span></p></td>
<td><p><span data-ttu-id="b02d3-145">X</span><span class="sxs-lookup"><span data-stu-id="b02d3-145">X</span></span></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="b02d3-146">X</span><span class="sxs-lookup"><span data-stu-id="b02d3-146">X</span></span></p></td>
<td><p><span data-ttu-id="b02d3-147">X</span><span class="sxs-lookup"><span data-stu-id="b02d3-147">X</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b02d3-148">8</span><span class="sxs-lookup"><span data-stu-id="b02d3-148">8</span></span></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="b02d3-149">X</span><span class="sxs-lookup"><span data-stu-id="b02d3-149">X</span></span></p></td>
<td><p><span data-ttu-id="b02d3-150">X</span><span class="sxs-lookup"><span data-stu-id="b02d3-150">X</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="b02d3-151">Az előfizetési díj létrehozásakor a legnagyobb részletezettségű eladási ár (a fenti táblázatban jelöltek szerint) lesz az előfizetés eladási ára.</span><span class="sxs-lookup"><span data-stu-id="b02d3-151">When a subscription fee is created, the sales price with the greatest level of detail, as noted in the table above, is selected as the subscription sales price.</span></span>

## <a name="update-and-index-subscription-sales-prices"></a><span data-ttu-id="b02d3-152">Előfizetési árak frissítése és indexelése</span><span class="sxs-lookup"><span data-stu-id="b02d3-152">Update and index subscription sales prices</span></span>

<span data-ttu-id="b02d3-153">Az előfizetés eladási árat az alapár vagy az indexár frissítésével lehet módosítani.</span><span class="sxs-lookup"><span data-stu-id="b02d3-153">You can update the subscription sales price by updating the base price or the index.</span></span> <span data-ttu-id="b02d3-154">Százalékosan vagy új érték megadásával lehet átállítani.</span><span class="sxs-lookup"><span data-stu-id="b02d3-154">You can update by a percentage or to a new value.</span></span>

## <a name="subscription-fee-sales-prices"></a><span data-ttu-id="b02d3-155">Előfizetési díj eladási árak</span><span class="sxs-lookup"><span data-stu-id="b02d3-155">Subscription fee sales prices</span></span>

<span data-ttu-id="b02d3-156">Előfizetési díj létrehozásakor az előfizetés eladási árbeállítása a konkrét eladási ár alapja.</span><span class="sxs-lookup"><span data-stu-id="b02d3-156">When you create a subscription fee, the sales price is based on the sales price setup of the subscription.</span></span> <span data-ttu-id="b02d3-157">Használni az előfizetés eladási árbeállításából az alapárat lehet, vagy létre lehet hozni indexelt eladási árakat.</span><span class="sxs-lookup"><span data-stu-id="b02d3-157">You can either use the base price from the subscription price setup or create indexed sales prices.</span></span>

## <a name="example"></a><span data-ttu-id="b02d3-158">Példa</span><span class="sxs-lookup"><span data-stu-id="b02d3-158">Example</span></span>

<span data-ttu-id="b02d3-159">Szeretne 500 eurós előfizetés eladási árakat beállítani, egy új, 9030 kódú projekt számra.</span><span class="sxs-lookup"><span data-stu-id="b02d3-159">You want to set up subscription sales prices of EUR 500 for a new project 9030.</span></span> <span data-ttu-id="b02d3-160">Az **Eladási ár (előfizetés)** képernyőn létrehoz egy előfizetési eladásiár-sort a következő táblázat szerint.</span><span class="sxs-lookup"><span data-stu-id="b02d3-160">In the **Sales price (subscription)** form, you create a subscription sales price line as indicated in the following table.</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="b02d3-161">Érvényesség kezdete</span><span class="sxs-lookup"><span data-stu-id="b02d3-161">Valid from</span></span></p></th>
<th><p><span data-ttu-id="b02d3-162">Kategória</span><span class="sxs-lookup"><span data-stu-id="b02d3-162">Category</span></span></p></th>
<th><p><span data-ttu-id="b02d3-163">Project</span><span class="sxs-lookup"><span data-stu-id="b02d3-163">Project</span></span></p></th>
<th><p><span data-ttu-id="b02d3-164">Előfizetés</span><span class="sxs-lookup"><span data-stu-id="b02d3-164">Subscription</span></span></p></th>
<th><p><span data-ttu-id="b02d3-165">Időszak kódja</span><span class="sxs-lookup"><span data-stu-id="b02d3-165">Period code</span></span></p></th>
<th><p><span data-ttu-id="b02d3-166">Értékesítés pénzneme</span><span class="sxs-lookup"><span data-stu-id="b02d3-166">Sales currency</span></span></p></th>
<th><p><span data-ttu-id="b02d3-167">Eladási ár</span><span class="sxs-lookup"><span data-stu-id="b02d3-167">Sales price</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b02d3-168">2006. 08. 28.</span><span class="sxs-lookup"><span data-stu-id="b02d3-168">28-08-2006</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b02d3-169">9030</span><span class="sxs-lookup"><span data-stu-id="b02d3-169">9030</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b02d3-170">Hónap</span><span class="sxs-lookup"><span data-stu-id="b02d3-170">Month</span></span></p></td>
<td><p><span data-ttu-id="b02d3-171">HUF</span><span class="sxs-lookup"><span data-stu-id="b02d3-171">EUR</span></span></p></td>
<td><p><span data-ttu-id="b02d3-172">500</span><span class="sxs-lookup"><span data-stu-id="b02d3-172">500</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="b02d3-173">Ne feledje, hogy a **Kategória** és az **Előfizetés** mező üres.</span><span class="sxs-lookup"><span data-stu-id="b02d3-173">Note that the **Category** and **Subscription** fields are empty.</span></span>

<span data-ttu-id="b02d3-174">Ezután a következő előfizetéseket hozza létre.</span><span class="sxs-lookup"><span data-stu-id="b02d3-174">You then create the following subscriptions.</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="b02d3-175">Előfizetés szolgáltatásra</span><span class="sxs-lookup"><span data-stu-id="b02d3-175">Service subscription</span></span></p></th>
<th><p><span data-ttu-id="b02d3-176">Project</span><span class="sxs-lookup"><span data-stu-id="b02d3-176">Project</span></span></p></th>
<th><p><span data-ttu-id="b02d3-177">Előfizetési csoport</span><span class="sxs-lookup"><span data-stu-id="b02d3-177">Subscription group</span></span></p></th>
<th><p><span data-ttu-id="b02d3-178">Kategória</span><span class="sxs-lookup"><span data-stu-id="b02d3-178">Category</span></span></p></th>
<th><p><span data-ttu-id="b02d3-179">Pénznem</span><span class="sxs-lookup"><span data-stu-id="b02d3-179">Currency</span></span></p></th>
<th><p><span data-ttu-id="b02d3-180">Időszak kódja</span><span class="sxs-lookup"><span data-stu-id="b02d3-180">Period code</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b02d3-181">00020_135</span><span class="sxs-lookup"><span data-stu-id="b02d3-181">00020_135</span></span></p></td>
<td><p><span data-ttu-id="b02d3-182">9030</span><span class="sxs-lookup"><span data-stu-id="b02d3-182">9030</span></span></p></td>
<td><p><span data-ttu-id="b02d3-183">Al1</span><span class="sxs-lookup"><span data-stu-id="b02d3-183">Sub1</span></span></p></td>
<td><p><span data-ttu-id="b02d3-184">Alkateg1</span><span class="sxs-lookup"><span data-stu-id="b02d3-184">SubCat1</span></span></p></td>
<td><p><span data-ttu-id="b02d3-185">HUF</span><span class="sxs-lookup"><span data-stu-id="b02d3-185">EUR</span></span></p></td>
<td><p><span data-ttu-id="b02d3-186">Havi</span><span class="sxs-lookup"><span data-stu-id="b02d3-186">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b02d3-187">00021_135</span><span class="sxs-lookup"><span data-stu-id="b02d3-187">00021_135</span></span></p></td>
<td><p><span data-ttu-id="b02d3-188">9030</span><span class="sxs-lookup"><span data-stu-id="b02d3-188">9030</span></span></p></td>
<td><p><span data-ttu-id="b02d3-189">Al1</span><span class="sxs-lookup"><span data-stu-id="b02d3-189">Sub1</span></span></p></td>
<td><p><span data-ttu-id="b02d3-190">Alkateg2</span><span class="sxs-lookup"><span data-stu-id="b02d3-190">SubCat2</span></span></p></td>
<td><p><span data-ttu-id="b02d3-191">HUF</span><span class="sxs-lookup"><span data-stu-id="b02d3-191">EUR</span></span></p></td>
<td><p><span data-ttu-id="b02d3-192">Havi</span><span class="sxs-lookup"><span data-stu-id="b02d3-192">Monthly</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="b02d3-193">Ekkor létre hozza az előfizetési díjakat mindkét előfizetéshez a Al1 előfizetési csoportban:</span><span class="sxs-lookup"><span data-stu-id="b02d3-193">Now you create subscription fees for both subscriptions in the subscription group Sub1:</span></span>

1.  <span data-ttu-id="b02d3-194">Kattintson a következőkre: **Szolgáltatáskezelés**\>**Beállítás**\>**Szolgáltatási előfizetések**\>**Előfizetési csoportok** .</span><span class="sxs-lookup"><span data-stu-id="b02d3-194">Click **Service management** \> **Setup** \> **Service subscriptions** \> **Subscription groups** .</span></span>

2.  <span data-ttu-id="b02d3-195">Az **Előfizetési csoportok** képernyőn kattintson ide: **Funkció** \> **Előfizetési díj létrehozása** .</span><span class="sxs-lookup"><span data-stu-id="b02d3-195">In the **Subscription groups** form, click **Function** \> **Create subscription fee** .</span></span>

3.  <span data-ttu-id="b02d3-196">Írja be a megfelelő adatokat az **Előfizetési díj létrehozása** képernyő mezőibe.</span><span class="sxs-lookup"><span data-stu-id="b02d3-196">In the **Create subscription fee** form, enter the appropriate information.</span></span> <span data-ttu-id="b02d3-197">A díjtranzakciókról az [Előfizetési díj tranzakcióinak létrehozása](create-subscription-fee-transactions.md) című témakörben olvashat bővebben.</span><span class="sxs-lookup"><span data-stu-id="b02d3-197">For more information, see [Create subscription fee transactions](create-subscription-fee-transactions.md).</span></span>

<span data-ttu-id="b02d3-198">Előfizetési díjak 500 EURÓS eladási árral rendelkezve mindkét előfizetéséhez, létrejönnek a következő táblázatban látható módon.</span><span class="sxs-lookup"><span data-stu-id="b02d3-198">Subscription fees that have a sales price of EUR 500 are created for both subscriptions, as shown in the following table.</span></span>

<table>
<colgroup>
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="b02d3-199">Projekt dátuma</span><span class="sxs-lookup"><span data-stu-id="b02d3-199">Project date</span></span></p></th>
<th><p><span data-ttu-id="b02d3-200">Előfizetés szolgáltatásra</span><span class="sxs-lookup"><span data-stu-id="b02d3-200">Service subscription</span></span></p></th>
<th><p><span data-ttu-id="b02d3-201">Project</span><span class="sxs-lookup"><span data-stu-id="b02d3-201">Project</span></span></p></th>
<th><p><span data-ttu-id="b02d3-202">Kategória</span><span class="sxs-lookup"><span data-stu-id="b02d3-202">Category</span></span></p></th>
<th><p><span data-ttu-id="b02d3-203">Kezdő dátum</span><span class="sxs-lookup"><span data-stu-id="b02d3-203">Start date</span></span></p></th>
<th><p><span data-ttu-id="b02d3-204">Záró dátum</span><span class="sxs-lookup"><span data-stu-id="b02d3-204">End date</span></span></p></th>
<th><p><span data-ttu-id="b02d3-205">Értékesítés pénzneme</span><span class="sxs-lookup"><span data-stu-id="b02d3-205">Sales currency</span></span></p></th>
<th><p><span data-ttu-id="b02d3-206">Eladási ár</span><span class="sxs-lookup"><span data-stu-id="b02d3-206">Sales price</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b02d3-207">2006. 08. 28.</span><span class="sxs-lookup"><span data-stu-id="b02d3-207">28-08-2006</span></span></p></td>
<td><p><span data-ttu-id="b02d3-208">00020_135</span><span class="sxs-lookup"><span data-stu-id="b02d3-208">00020_135</span></span></p></td>
<td><p><span data-ttu-id="b02d3-209">9030</span><span class="sxs-lookup"><span data-stu-id="b02d3-209">9030</span></span></p></td>
<td><p><span data-ttu-id="b02d3-210">Alkateg1</span><span class="sxs-lookup"><span data-stu-id="b02d3-210">SubCat1</span></span></p></td>
<td><p><span data-ttu-id="b02d3-211">2007. 01. 01.</span><span class="sxs-lookup"><span data-stu-id="b02d3-211">01-01-2007</span></span></p></td>
<td><p><span data-ttu-id="b02d3-212">2007. 03. 31.</span><span class="sxs-lookup"><span data-stu-id="b02d3-212">31-03-2007</span></span></p></td>
<td><p><span data-ttu-id="b02d3-213">HUF</span><span class="sxs-lookup"><span data-stu-id="b02d3-213">EUR</span></span></p></td>
<td><p><span data-ttu-id="b02d3-214">500</span><span class="sxs-lookup"><span data-stu-id="b02d3-214">500</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b02d3-215">2006. 08. 28.</span><span class="sxs-lookup"><span data-stu-id="b02d3-215">28-08-2006</span></span></p></td>
<td><p><span data-ttu-id="b02d3-216">00021_135</span><span class="sxs-lookup"><span data-stu-id="b02d3-216">00021_135</span></span></p></td>
<td><p><span data-ttu-id="b02d3-217">9030</span><span class="sxs-lookup"><span data-stu-id="b02d3-217">9030</span></span></p></td>
<td><p><span data-ttu-id="b02d3-218">Alkateg2</span><span class="sxs-lookup"><span data-stu-id="b02d3-218">SubCat2</span></span></p></td>
<td><p><span data-ttu-id="b02d3-219">2007. 01. 01.</span><span class="sxs-lookup"><span data-stu-id="b02d3-219">01-01-2007</span></span></p></td>
<td><p><span data-ttu-id="b02d3-220">2007. 03. 31.</span><span class="sxs-lookup"><span data-stu-id="b02d3-220">31-03-2007</span></span></p></td>
<td><p><span data-ttu-id="b02d3-221">HUF</span><span class="sxs-lookup"><span data-stu-id="b02d3-221">EUR</span></span></p></td>
<td><p><span data-ttu-id="b02d3-222">500</span><span class="sxs-lookup"><span data-stu-id="b02d3-222">500</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="b02d3-223">Később úgy dönt, hogy a 9030-as projekt Alkateg1 kategóriájához szeretne eladási árakat megadni.</span><span class="sxs-lookup"><span data-stu-id="b02d3-223">Later, you decide that you want to specify sales prices for the category SubCat1 for project 9030.</span></span> <span data-ttu-id="b02d3-224">Ezért a 9030-as projekt és a Alkateg1 díjkategória kombinációjához létrehoz egy új eladásiár-sort 550 eurós eladási árral.</span><span class="sxs-lookup"><span data-stu-id="b02d3-224">Therefore, you create a new sales price line that has a sales price of EUR 550 for the combination of project 9030 and fee category SubCat1.</span></span> <span data-ttu-id="b02d3-225">Ezzel már két előfizetés eladásiár-sor szerepel a 9030-as projektnél, a következő táblázatban látható módon:</span><span class="sxs-lookup"><span data-stu-id="b02d3-225">There are now two subscription sales price lines for project 9030, as shown in the following table.</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="b02d3-226">Érvényesség kezdete</span><span class="sxs-lookup"><span data-stu-id="b02d3-226">Valid from</span></span></p></th>
<th><p><span data-ttu-id="b02d3-227">Kategória</span><span class="sxs-lookup"><span data-stu-id="b02d3-227">Category</span></span></p></th>
<th><p><span data-ttu-id="b02d3-228">Project</span><span class="sxs-lookup"><span data-stu-id="b02d3-228">Project</span></span></p></th>
<th><p><span data-ttu-id="b02d3-229">Előfizetés</span><span class="sxs-lookup"><span data-stu-id="b02d3-229">Subscription</span></span></p></th>
<th><p><span data-ttu-id="b02d3-230">Időszak kódja</span><span class="sxs-lookup"><span data-stu-id="b02d3-230">Period code</span></span></p></th>
<th><p><span data-ttu-id="b02d3-231">Pénznem</span><span class="sxs-lookup"><span data-stu-id="b02d3-231">Currency</span></span></p></th>
<th><p><span data-ttu-id="b02d3-232">Eladási ár</span><span class="sxs-lookup"><span data-stu-id="b02d3-232">Sales price</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b02d3-233">2007. 08. 28.</span><span class="sxs-lookup"><span data-stu-id="b02d3-233">28-08-2007</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b02d3-234">9030</span><span class="sxs-lookup"><span data-stu-id="b02d3-234">9030</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b02d3-235">Hónap</span><span class="sxs-lookup"><span data-stu-id="b02d3-235">Month</span></span></p></td>
<td><p><span data-ttu-id="b02d3-236">HUF</span><span class="sxs-lookup"><span data-stu-id="b02d3-236">EUR</span></span></p></td>
<td><p><span data-ttu-id="b02d3-237">500</span><span class="sxs-lookup"><span data-stu-id="b02d3-237">500</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b02d3-238">2007. 08. 28.</span><span class="sxs-lookup"><span data-stu-id="b02d3-238">28-08-2007</span></span></p></td>
<td><p><span data-ttu-id="b02d3-239">Alkateg1</span><span class="sxs-lookup"><span data-stu-id="b02d3-239">SubCat1</span></span></p></td>
<td><p><span data-ttu-id="b02d3-240">9030</span><span class="sxs-lookup"><span data-stu-id="b02d3-240">9030</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b02d3-241">Hónap</span><span class="sxs-lookup"><span data-stu-id="b02d3-241">Month</span></span></p></td>
<td><p><span data-ttu-id="b02d3-242">HUF</span><span class="sxs-lookup"><span data-stu-id="b02d3-242">EUR</span></span></p></td>
<td><p><span data-ttu-id="b02d3-243">550</span><span class="sxs-lookup"><span data-stu-id="b02d3-243">550</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="b02d3-244">A fentebb részletezett eljárást ismételve az Alkateg1 előfizetési csoport mindkét előfizetéséhez létrehoz egy előfizetési díjat.</span><span class="sxs-lookup"><span data-stu-id="b02d3-244">You repeat the procedure described above to create subscription fees for both subscriptions in the subscription group Sub1.</span></span> <span data-ttu-id="b02d3-245">A következő tábla megmutatja, hogy két tranzakció jön létre, vagyis előfizetési csoporthoz társított előfizetésenként egy:</span><span class="sxs-lookup"><span data-stu-id="b02d3-245">The following table shows the transactions that are created for each subscription that is attached to the subscription group.</span></span>

<table>
<colgroup>
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="b02d3-246">Projekt dátuma</span><span class="sxs-lookup"><span data-stu-id="b02d3-246">Project date</span></span></p></th>
<th><p><span data-ttu-id="b02d3-247">Előfizetés</span><span class="sxs-lookup"><span data-stu-id="b02d3-247">Subscription</span></span></p></th>
<th><p><span data-ttu-id="b02d3-248">Project</span><span class="sxs-lookup"><span data-stu-id="b02d3-248">Project</span></span></p></th>
<th><p><span data-ttu-id="b02d3-249">Kategória</span><span class="sxs-lookup"><span data-stu-id="b02d3-249">Category</span></span></p></th>
<th><p><span data-ttu-id="b02d3-250">Kezdő dátum</span><span class="sxs-lookup"><span data-stu-id="b02d3-250">Start date</span></span></p></th>
<th><p><span data-ttu-id="b02d3-251">Befejezés</span><span class="sxs-lookup"><span data-stu-id="b02d3-251">End date</span></span></p></th>
<th><p><span data-ttu-id="b02d3-252">Értékesítés pénzneme</span><span class="sxs-lookup"><span data-stu-id="b02d3-252">Sales currency</span></span></p></th>
<th><p><span data-ttu-id="b02d3-253">Eladási ár</span><span class="sxs-lookup"><span data-stu-id="b02d3-253">Sales price</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b02d3-254">2007. 07. 28.</span><span class="sxs-lookup"><span data-stu-id="b02d3-254">28-07-2007</span></span></p></td>
<td><p><span data-ttu-id="b02d3-255">00020_135</span><span class="sxs-lookup"><span data-stu-id="b02d3-255">00020_135</span></span></p></td>
<td><p><span data-ttu-id="b02d3-256">9030</span><span class="sxs-lookup"><span data-stu-id="b02d3-256">9030</span></span></p></td>
<td><p><span data-ttu-id="b02d3-257">Alkateg1</span><span class="sxs-lookup"><span data-stu-id="b02d3-257">SubCat1</span></span></p></td>
<td><p><span data-ttu-id="b02d3-258">2008. 01. 01.</span><span class="sxs-lookup"><span data-stu-id="b02d3-258">01-01-2008</span></span></p></td>
<td><p><span data-ttu-id="b02d3-259">2008. 03. 31.</span><span class="sxs-lookup"><span data-stu-id="b02d3-259">31-03-2008</span></span></p></td>
<td><p><span data-ttu-id="b02d3-260">HUF</span><span class="sxs-lookup"><span data-stu-id="b02d3-260">EUR</span></span></p></td>
<td><p><span data-ttu-id="b02d3-261">550</span><span class="sxs-lookup"><span data-stu-id="b02d3-261">550</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b02d3-262">2008. 07. 28.</span><span class="sxs-lookup"><span data-stu-id="b02d3-262">28-07-2008</span></span></p></td>
<td><p><span data-ttu-id="b02d3-263">00021_135</span><span class="sxs-lookup"><span data-stu-id="b02d3-263">00021_135</span></span></p></td>
<td><p><span data-ttu-id="b02d3-264">9030</span><span class="sxs-lookup"><span data-stu-id="b02d3-264">9030</span></span></p></td>
<td><p><span data-ttu-id="b02d3-265">Alkateg2</span><span class="sxs-lookup"><span data-stu-id="b02d3-265">SubCat2</span></span></p></td>
<td><p><span data-ttu-id="b02d3-266">2008. 01. 01.</span><span class="sxs-lookup"><span data-stu-id="b02d3-266">01-01-2008</span></span></p></td>
<td><p><span data-ttu-id="b02d3-267">2008. 03. 31.</span><span class="sxs-lookup"><span data-stu-id="b02d3-267">31-03-2008</span></span></p></td>
<td><p><span data-ttu-id="b02d3-268">HUF</span><span class="sxs-lookup"><span data-stu-id="b02d3-268">EUR</span></span></p></td>
<td><p><span data-ttu-id="b02d3-269">500</span><span class="sxs-lookup"><span data-stu-id="b02d3-269">500</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="b02d3-270">A 00020\_135-ös előfizetéshez tartozó első tranzakcióban az 550 eurós eladási ár egy adott projekt és kategória kombinációjához beállított előfizetés eladási árból származik.</span><span class="sxs-lookup"><span data-stu-id="b02d3-270">In the first transaction for subscription 00020\_135, the sales price of EUR 550 derives from the subscription sales price that is set up for the combination of the specific project and category.</span></span> <span data-ttu-id="b02d3-271">A 00021\_135-ös előfizetéshez tartozó második tranzakcióban azért szerepel 500 euró a projekt-előfizetés eladási áraként, mert a 9030-as projekt és az Alkateg2 kategória kombinációjához nincs ár beállítva.</span><span class="sxs-lookup"><span data-stu-id="b02d3-271">In the second transaction for subscription 00021\_135, the sales price of EUR 500 is used as the project subscription sales price because there is no price set up for the combination of project 9030 and category SubCat2.</span></span>

## <a name="see-also"></a><span data-ttu-id="b02d3-272">Lásd még</span><span class="sxs-lookup"><span data-stu-id="b02d3-272">See also</span></span>

[<span data-ttu-id="b02d3-273">Előfizetési árak frissítése és indexelése</span><span class="sxs-lookup"><span data-stu-id="b02d3-273">Update and index subscription sales prices</span></span>](update-and-index-subscription-sales-prices.md)

  


