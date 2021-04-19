---
title: Eőfizetés eladási árai
description: Amikor előfizetést hoz létre, az eladási ár az Eladási ár (előfizetés) képernyőn létrehozott eladási ár beállításból jön létre.
author: ShylaThompson
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMASalespriceSubscription
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3b4b02af0a535e67818751c437482c3663524474
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5817413"
---
# <a name="subscription-sales-prices"></a><span data-ttu-id="997ee-103">Eőfizetés eladási árai</span><span class="sxs-lookup"><span data-stu-id="997ee-103">Subscription sales prices</span></span>   

[!include [banner](../includes/banner.md)]


<span data-ttu-id="997ee-104">Amikor előfizetést hoz létre, az eladási ár az **Eladási ár (előfizetés)** képernyőn létrehozott eladási ár beállításból jön létre.</span><span class="sxs-lookup"><span data-stu-id="997ee-104">When you create a subscription, the sales price is derived from the sales price setup that was created in the **Sales price (subscription)** form.</span></span>

<span data-ttu-id="997ee-105">Az **Eladási ár (előfizetés)** képernyőn egy-egy előfizetéshez is készíthet eladási árat, vagy létrehozhat olyan eladási árat, amely általánosabban érvényes.</span><span class="sxs-lookup"><span data-stu-id="997ee-105">In the **Sales price (subscription)** form, you can create sales prices for a specific subscription or you can create sales prices that apply more broadly.</span></span> <span data-ttu-id="997ee-106">Az eladási ár alkalmazásához az előfizetésre, meg kell egyeznie az előfizetés időszakkódjának és pénznemének az eladási ár időszakkódjával és pénznemével.</span><span class="sxs-lookup"><span data-stu-id="997ee-106">For a sales price to be applied to a subscription, the period code and the currency of the subscription must be identical to the period code and the currency of the sales price.</span></span>

<span data-ttu-id="997ee-107">Ha az előfizetés és az eladási ár időszakkódja és pénzneme megegyezik, akkor az előfizetés eladási ára az alábbi táblázatban szereplő prioritások alapján választható ki.</span><span class="sxs-lookup"><span data-stu-id="997ee-107">If the period code and currency are identical for the subscription and the sales price, subscription sales prices are selected on the basis of the priorities listed in the following table.</span></span> <span data-ttu-id="997ee-108">Az üres cella üres mezőt, az X pedig a előfizetésből létrejött tranzakcióban szereplő értékkel megegyező értéket jelent.</span><span class="sxs-lookup"><span data-stu-id="997ee-108">A blank cell in the table indicates an empty field and an X indicates a value that is equal to the value in the subscription from which the transaction is generated.</span></span>

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
<th><p><span data-ttu-id="997ee-109">. prioritás</span><span class="sxs-lookup"><span data-stu-id="997ee-109">Priority</span></span></p></th>
<th><p><span data-ttu-id="997ee-110"><strong>Kategória</strong></span><span class="sxs-lookup"><span data-stu-id="997ee-110"><strong>Category</strong></span></span></p></th>
<th><p><span data-ttu-id="997ee-111"><strong>Projektazonosító</strong></span><span class="sxs-lookup"><span data-stu-id="997ee-111"><strong>Project ID</strong></span></span></p></th>
<th><p><span data-ttu-id="997ee-112"><strong>Előfizetés</strong></span><span class="sxs-lookup"><span data-stu-id="997ee-112"><strong>Subscription</strong></span></span></p></th>
<th><p><span data-ttu-id="997ee-113"><strong>Értékesítés pénzneme</strong></span><span class="sxs-lookup"><span data-stu-id="997ee-113"><strong>Sales currency</strong></span></span></p></th>
<th><p><span data-ttu-id="997ee-114"><strong>Időszak kódja</strong></span><span class="sxs-lookup"><span data-stu-id="997ee-114"><strong>Period code</strong></span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="997ee-115">1</span><span class="sxs-lookup"><span data-stu-id="997ee-115">1</span></span></p></td>
<td><p><span data-ttu-id="997ee-116">X</span><span class="sxs-lookup"><span data-stu-id="997ee-116">X</span></span></p></td>
<td><p><span data-ttu-id="997ee-117">X</span><span class="sxs-lookup"><span data-stu-id="997ee-117">X</span></span></p></td>
<td><p><span data-ttu-id="997ee-118">X</span><span class="sxs-lookup"><span data-stu-id="997ee-118">X</span></span></p></td>
<td><p><span data-ttu-id="997ee-119">X</span><span class="sxs-lookup"><span data-stu-id="997ee-119">X</span></span></p></td>
<td><p><span data-ttu-id="997ee-120">X</span><span class="sxs-lookup"><span data-stu-id="997ee-120">X</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="997ee-121">2</span><span class="sxs-lookup"><span data-stu-id="997ee-121">2</span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="997ee-122">X</span><span class="sxs-lookup"><span data-stu-id="997ee-122">X</span></span></p></td>
<td><p><span data-ttu-id="997ee-123">X</span><span class="sxs-lookup"><span data-stu-id="997ee-123">X</span></span></p></td>
<td><p><span data-ttu-id="997ee-124">X</span><span class="sxs-lookup"><span data-stu-id="997ee-124">X</span></span></p></td>
<td><p><span data-ttu-id="997ee-125">X</span><span class="sxs-lookup"><span data-stu-id="997ee-125">X</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="997ee-126">3</span><span class="sxs-lookup"><span data-stu-id="997ee-126">3</span></span></p></td>
<td><p><span data-ttu-id="997ee-127">X</span><span class="sxs-lookup"><span data-stu-id="997ee-127">X</span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="997ee-128">X</span><span class="sxs-lookup"><span data-stu-id="997ee-128">X</span></span></p></td>
<td><p><span data-ttu-id="997ee-129">X</span><span class="sxs-lookup"><span data-stu-id="997ee-129">X</span></span></p></td>
<td><p><span data-ttu-id="997ee-130">X</span><span class="sxs-lookup"><span data-stu-id="997ee-130">X</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="997ee-131">4</span><span class="sxs-lookup"><span data-stu-id="997ee-131">4</span></span></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="997ee-132">X</span><span class="sxs-lookup"><span data-stu-id="997ee-132">X</span></span></p></td>
<td><p><span data-ttu-id="997ee-133">X</span><span class="sxs-lookup"><span data-stu-id="997ee-133">X</span></span></p></td>
<td><p><span data-ttu-id="997ee-134">X</span><span class="sxs-lookup"><span data-stu-id="997ee-134">X</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="997ee-135">5</span><span class="sxs-lookup"><span data-stu-id="997ee-135">5</span></span></p></td>
<td><p><span data-ttu-id="997ee-136">X</span><span class="sxs-lookup"><span data-stu-id="997ee-136">X</span></span></p></td>
<td><p><span data-ttu-id="997ee-137">X</span><span class="sxs-lookup"><span data-stu-id="997ee-137">X</span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="997ee-138">X</span><span class="sxs-lookup"><span data-stu-id="997ee-138">X</span></span></p></td>
<td><p><span data-ttu-id="997ee-139">X</span><span class="sxs-lookup"><span data-stu-id="997ee-139">X</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="997ee-140">6</span><span class="sxs-lookup"><span data-stu-id="997ee-140">6</span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="997ee-141">X</span><span class="sxs-lookup"><span data-stu-id="997ee-141">X</span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="997ee-142">X</span><span class="sxs-lookup"><span data-stu-id="997ee-142">X</span></span></p></td>
<td><p><span data-ttu-id="997ee-143">X</span><span class="sxs-lookup"><span data-stu-id="997ee-143">X</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="997ee-144">7</span><span class="sxs-lookup"><span data-stu-id="997ee-144">7</span></span></p></td>
<td><p><span data-ttu-id="997ee-145">X</span><span class="sxs-lookup"><span data-stu-id="997ee-145">X</span></span></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="997ee-146">X</span><span class="sxs-lookup"><span data-stu-id="997ee-146">X</span></span></p></td>
<td><p><span data-ttu-id="997ee-147">X</span><span class="sxs-lookup"><span data-stu-id="997ee-147">X</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="997ee-148">8</span><span class="sxs-lookup"><span data-stu-id="997ee-148">8</span></span></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="997ee-149">X</span><span class="sxs-lookup"><span data-stu-id="997ee-149">X</span></span></p></td>
<td><p><span data-ttu-id="997ee-150">X</span><span class="sxs-lookup"><span data-stu-id="997ee-150">X</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="997ee-151">Az előfizetési díj létrehozásakor a legnagyobb részletezettségű eladási ár (a fenti táblázatban jelöltek szerint) lesz az előfizetés eladási ára.</span><span class="sxs-lookup"><span data-stu-id="997ee-151">When a subscription fee is created, the sales price with the greatest level of detail, as noted in the table above, is selected as the subscription sales price.</span></span>

## <a name="update-and-index-subscription-sales-prices"></a><span data-ttu-id="997ee-152">Előfizetési árak frissítése és indexelése</span><span class="sxs-lookup"><span data-stu-id="997ee-152">Update and index subscription sales prices</span></span>

<span data-ttu-id="997ee-153">Az előfizetés eladási árat az alapár vagy az indexár frissítésével lehet módosítani.</span><span class="sxs-lookup"><span data-stu-id="997ee-153">You can update the subscription sales price by updating the base price or the index.</span></span> <span data-ttu-id="997ee-154">Százalékosan vagy új érték megadásával lehet átállítani.</span><span class="sxs-lookup"><span data-stu-id="997ee-154">You can update by a percentage or to a new value.</span></span>

## <a name="subscription-fee-sales-prices"></a><span data-ttu-id="997ee-155">Előfizetési díj eladási árak</span><span class="sxs-lookup"><span data-stu-id="997ee-155">Subscription fee sales prices</span></span>

<span data-ttu-id="997ee-156">Előfizetési díj létrehozásakor az előfizetés eladási árbeállítása a konkrét eladási ár alapja.</span><span class="sxs-lookup"><span data-stu-id="997ee-156">When you create a subscription fee, the sales price is based on the sales price setup of the subscription.</span></span> <span data-ttu-id="997ee-157">Használni az előfizetés eladási árbeállításából az alapárat lehet, vagy létre lehet hozni indexelt eladási árakat.</span><span class="sxs-lookup"><span data-stu-id="997ee-157">You can either use the base price from the subscription price setup or create indexed sales prices.</span></span>

## <a name="example"></a><span data-ttu-id="997ee-158">Példa</span><span class="sxs-lookup"><span data-stu-id="997ee-158">Example</span></span>

<span data-ttu-id="997ee-159">Szeretne 500 eurós előfizetés eladási árakat beállítani, egy új, 9030 kódú projekt számra.</span><span class="sxs-lookup"><span data-stu-id="997ee-159">You want to set up subscription sales prices of EUR 500 for a new project 9030.</span></span> <span data-ttu-id="997ee-160">Az **Eladási ár (előfizetés)** képernyőn létrehoz egy előfizetési eladásiár-sort a következő táblázat szerint.</span><span class="sxs-lookup"><span data-stu-id="997ee-160">In the **Sales price (subscription)** form, you create a subscription sales price line as indicated in the following table.</span></span>

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
<th><p><span data-ttu-id="997ee-161">Érvényesség kezdete</span><span class="sxs-lookup"><span data-stu-id="997ee-161">Valid from</span></span></p></th>
<th><p><span data-ttu-id="997ee-162">Kategória</span><span class="sxs-lookup"><span data-stu-id="997ee-162">Category</span></span></p></th>
<th><p><span data-ttu-id="997ee-163">Project</span><span class="sxs-lookup"><span data-stu-id="997ee-163">Project</span></span></p></th>
<th><p><span data-ttu-id="997ee-164">Előfizetés</span><span class="sxs-lookup"><span data-stu-id="997ee-164">Subscription</span></span></p></th>
<th><p><span data-ttu-id="997ee-165">Időszak kódja</span><span class="sxs-lookup"><span data-stu-id="997ee-165">Period code</span></span></p></th>
<th><p><span data-ttu-id="997ee-166">Értékesítés pénzneme</span><span class="sxs-lookup"><span data-stu-id="997ee-166">Sales currency</span></span></p></th>
<th><p><span data-ttu-id="997ee-167">Eladási ár</span><span class="sxs-lookup"><span data-stu-id="997ee-167">Sales price</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="997ee-168">2006. 08. 28.</span><span class="sxs-lookup"><span data-stu-id="997ee-168">28-08-2006</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="997ee-169">9030</span><span class="sxs-lookup"><span data-stu-id="997ee-169">9030</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="997ee-170">Hónap</span><span class="sxs-lookup"><span data-stu-id="997ee-170">Month</span></span></p></td>
<td><p><span data-ttu-id="997ee-171">HUF</span><span class="sxs-lookup"><span data-stu-id="997ee-171">EUR</span></span></p></td>
<td><p><span data-ttu-id="997ee-172">500</span><span class="sxs-lookup"><span data-stu-id="997ee-172">500</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="997ee-173">Ne feledje, hogy a **Kategória** és az **Előfizetés** mező üres.</span><span class="sxs-lookup"><span data-stu-id="997ee-173">Note that the **Category** and **Subscription** fields are empty.</span></span>

<span data-ttu-id="997ee-174">Ezután a következő előfizetéseket hozza létre.</span><span class="sxs-lookup"><span data-stu-id="997ee-174">You then create the following subscriptions.</span></span>

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
<th><p><span data-ttu-id="997ee-175">Előfizetés szolgáltatásra</span><span class="sxs-lookup"><span data-stu-id="997ee-175">Service subscription</span></span></p></th>
<th><p><span data-ttu-id="997ee-176">Project</span><span class="sxs-lookup"><span data-stu-id="997ee-176">Project</span></span></p></th>
<th><p><span data-ttu-id="997ee-177">Előfizetési csoport</span><span class="sxs-lookup"><span data-stu-id="997ee-177">Subscription group</span></span></p></th>
<th><p><span data-ttu-id="997ee-178">Kategória</span><span class="sxs-lookup"><span data-stu-id="997ee-178">Category</span></span></p></th>
<th><p><span data-ttu-id="997ee-179">Pénznem</span><span class="sxs-lookup"><span data-stu-id="997ee-179">Currency</span></span></p></th>
<th><p><span data-ttu-id="997ee-180">Időszak kódja</span><span class="sxs-lookup"><span data-stu-id="997ee-180">Period code</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="997ee-181">00020_135</span><span class="sxs-lookup"><span data-stu-id="997ee-181">00020_135</span></span></p></td>
<td><p><span data-ttu-id="997ee-182">9030</span><span class="sxs-lookup"><span data-stu-id="997ee-182">9030</span></span></p></td>
<td><p><span data-ttu-id="997ee-183">Al1</span><span class="sxs-lookup"><span data-stu-id="997ee-183">Sub1</span></span></p></td>
<td><p><span data-ttu-id="997ee-184">Alkateg1</span><span class="sxs-lookup"><span data-stu-id="997ee-184">SubCat1</span></span></p></td>
<td><p><span data-ttu-id="997ee-185">HUF</span><span class="sxs-lookup"><span data-stu-id="997ee-185">EUR</span></span></p></td>
<td><p><span data-ttu-id="997ee-186">Havi</span><span class="sxs-lookup"><span data-stu-id="997ee-186">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="997ee-187">00021_135</span><span class="sxs-lookup"><span data-stu-id="997ee-187">00021_135</span></span></p></td>
<td><p><span data-ttu-id="997ee-188">9030</span><span class="sxs-lookup"><span data-stu-id="997ee-188">9030</span></span></p></td>
<td><p><span data-ttu-id="997ee-189">Al1</span><span class="sxs-lookup"><span data-stu-id="997ee-189">Sub1</span></span></p></td>
<td><p><span data-ttu-id="997ee-190">Alkateg2</span><span class="sxs-lookup"><span data-stu-id="997ee-190">SubCat2</span></span></p></td>
<td><p><span data-ttu-id="997ee-191">HUF</span><span class="sxs-lookup"><span data-stu-id="997ee-191">EUR</span></span></p></td>
<td><p><span data-ttu-id="997ee-192">Havi</span><span class="sxs-lookup"><span data-stu-id="997ee-192">Monthly</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="997ee-193">Ekkor létre hozza az előfizetési díjakat mindkét előfizetéshez a Al1 előfizetési csoportban:</span><span class="sxs-lookup"><span data-stu-id="997ee-193">Now you create subscription fees for both subscriptions in the subscription group Sub1:</span></span>

1.  <span data-ttu-id="997ee-194">Kattintson a következőkre: **Szolgáltatáskezelés**\>**Beállítás**\>**Szolgáltatási előfizetések**\>**Előfizetési csoportok**.</span><span class="sxs-lookup"><span data-stu-id="997ee-194">Click **Service management** \> **Setup** \> **Service subscriptions** \> **Subscription groups**.</span></span>

2.  <span data-ttu-id="997ee-195">Az **Előfizetési csoportok** képernyőn kattintson ide: **Funkció** \> **Előfizetési díj létrehozása**.</span><span class="sxs-lookup"><span data-stu-id="997ee-195">In the **Subscription groups** form, click **Function** \> **Create subscription fee**.</span></span>

3.  <span data-ttu-id="997ee-196">Írja be a megfelelő adatokat az **Előfizetési díj létrehozása** képernyő mezőibe.</span><span class="sxs-lookup"><span data-stu-id="997ee-196">In the **Create subscription fee** form, enter the appropriate information.</span></span> <span data-ttu-id="997ee-197">A díjtranzakciókról az [Előfizetési díj tranzakcióinak létrehozása](create-subscription-fee-transactions.md) című témakörben olvashat bővebben.</span><span class="sxs-lookup"><span data-stu-id="997ee-197">For more information, see [Create subscription fee transactions](create-subscription-fee-transactions.md).</span></span>

<span data-ttu-id="997ee-198">Előfizetési díjak 500 EURÓS eladási árral rendelkezve mindkét előfizetéséhez, létrejönnek a következő táblázatban látható módon.</span><span class="sxs-lookup"><span data-stu-id="997ee-198">Subscription fees that have a sales price of EUR 500 are created for both subscriptions, as shown in the following table.</span></span>

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
<th><p><span data-ttu-id="997ee-199">Projekt dátuma</span><span class="sxs-lookup"><span data-stu-id="997ee-199">Project date</span></span></p></th>
<th><p><span data-ttu-id="997ee-200">Előfizetés szolgáltatásra</span><span class="sxs-lookup"><span data-stu-id="997ee-200">Service subscription</span></span></p></th>
<th><p><span data-ttu-id="997ee-201">Project</span><span class="sxs-lookup"><span data-stu-id="997ee-201">Project</span></span></p></th>
<th><p><span data-ttu-id="997ee-202">Kategória</span><span class="sxs-lookup"><span data-stu-id="997ee-202">Category</span></span></p></th>
<th><p><span data-ttu-id="997ee-203">Kezdő dátum</span><span class="sxs-lookup"><span data-stu-id="997ee-203">Start date</span></span></p></th>
<th><p><span data-ttu-id="997ee-204">Záró dátum</span><span class="sxs-lookup"><span data-stu-id="997ee-204">End date</span></span></p></th>
<th><p><span data-ttu-id="997ee-205">Értékesítés pénzneme</span><span class="sxs-lookup"><span data-stu-id="997ee-205">Sales currency</span></span></p></th>
<th><p><span data-ttu-id="997ee-206">Eladási ár</span><span class="sxs-lookup"><span data-stu-id="997ee-206">Sales price</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="997ee-207">2006. 08. 28.</span><span class="sxs-lookup"><span data-stu-id="997ee-207">28-08-2006</span></span></p></td>
<td><p><span data-ttu-id="997ee-208">00020_135</span><span class="sxs-lookup"><span data-stu-id="997ee-208">00020_135</span></span></p></td>
<td><p><span data-ttu-id="997ee-209">9030</span><span class="sxs-lookup"><span data-stu-id="997ee-209">9030</span></span></p></td>
<td><p><span data-ttu-id="997ee-210">Alkateg1</span><span class="sxs-lookup"><span data-stu-id="997ee-210">SubCat1</span></span></p></td>
<td><p><span data-ttu-id="997ee-211">2007. 01. 01.</span><span class="sxs-lookup"><span data-stu-id="997ee-211">01-01-2007</span></span></p></td>
<td><p><span data-ttu-id="997ee-212">2007. 03. 31.</span><span class="sxs-lookup"><span data-stu-id="997ee-212">31-03-2007</span></span></p></td>
<td><p><span data-ttu-id="997ee-213">HUF</span><span class="sxs-lookup"><span data-stu-id="997ee-213">EUR</span></span></p></td>
<td><p><span data-ttu-id="997ee-214">500</span><span class="sxs-lookup"><span data-stu-id="997ee-214">500</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="997ee-215">2006. 08. 28.</span><span class="sxs-lookup"><span data-stu-id="997ee-215">28-08-2006</span></span></p></td>
<td><p><span data-ttu-id="997ee-216">00021_135</span><span class="sxs-lookup"><span data-stu-id="997ee-216">00021_135</span></span></p></td>
<td><p><span data-ttu-id="997ee-217">9030</span><span class="sxs-lookup"><span data-stu-id="997ee-217">9030</span></span></p></td>
<td><p><span data-ttu-id="997ee-218">Alkateg2</span><span class="sxs-lookup"><span data-stu-id="997ee-218">SubCat2</span></span></p></td>
<td><p><span data-ttu-id="997ee-219">2007. 01. 01.</span><span class="sxs-lookup"><span data-stu-id="997ee-219">01-01-2007</span></span></p></td>
<td><p><span data-ttu-id="997ee-220">2007. 03. 31.</span><span class="sxs-lookup"><span data-stu-id="997ee-220">31-03-2007</span></span></p></td>
<td><p><span data-ttu-id="997ee-221">HUF</span><span class="sxs-lookup"><span data-stu-id="997ee-221">EUR</span></span></p></td>
<td><p><span data-ttu-id="997ee-222">500</span><span class="sxs-lookup"><span data-stu-id="997ee-222">500</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="997ee-223">Később úgy dönt, hogy a 9030-as projekt Alkateg1 kategóriájához szeretne eladási árakat megadni.</span><span class="sxs-lookup"><span data-stu-id="997ee-223">Later, you decide that you want to specify sales prices for the category SubCat1 for project 9030.</span></span> <span data-ttu-id="997ee-224">Ezért a 9030-as projekt és a Alkateg1 díjkategória kombinációjához létrehoz egy új eladásiár-sort 550 eurós eladási árral.</span><span class="sxs-lookup"><span data-stu-id="997ee-224">Therefore, you create a new sales price line that has a sales price of EUR 550 for the combination of project 9030 and fee category SubCat1.</span></span> <span data-ttu-id="997ee-225">Ezzel már két előfizetés eladásiár-sor szerepel a 9030-as projektnél, a következő táblázatban látható módon:</span><span class="sxs-lookup"><span data-stu-id="997ee-225">There are now two subscription sales price lines for project 9030, as shown in the following table.</span></span>

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
<th><p><span data-ttu-id="997ee-226">Érvényesség kezdete</span><span class="sxs-lookup"><span data-stu-id="997ee-226">Valid from</span></span></p></th>
<th><p><span data-ttu-id="997ee-227">Kategória</span><span class="sxs-lookup"><span data-stu-id="997ee-227">Category</span></span></p></th>
<th><p><span data-ttu-id="997ee-228">Project</span><span class="sxs-lookup"><span data-stu-id="997ee-228">Project</span></span></p></th>
<th><p><span data-ttu-id="997ee-229">Előfizetés</span><span class="sxs-lookup"><span data-stu-id="997ee-229">Subscription</span></span></p></th>
<th><p><span data-ttu-id="997ee-230">Időszak kódja</span><span class="sxs-lookup"><span data-stu-id="997ee-230">Period code</span></span></p></th>
<th><p><span data-ttu-id="997ee-231">Pénznem</span><span class="sxs-lookup"><span data-stu-id="997ee-231">Currency</span></span></p></th>
<th><p><span data-ttu-id="997ee-232">Eladási ár</span><span class="sxs-lookup"><span data-stu-id="997ee-232">Sales price</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="997ee-233">2007. 08. 28.</span><span class="sxs-lookup"><span data-stu-id="997ee-233">28-08-2007</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="997ee-234">9030</span><span class="sxs-lookup"><span data-stu-id="997ee-234">9030</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="997ee-235">Hónap</span><span class="sxs-lookup"><span data-stu-id="997ee-235">Month</span></span></p></td>
<td><p><span data-ttu-id="997ee-236">HUF</span><span class="sxs-lookup"><span data-stu-id="997ee-236">EUR</span></span></p></td>
<td><p><span data-ttu-id="997ee-237">500</span><span class="sxs-lookup"><span data-stu-id="997ee-237">500</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="997ee-238">2007. 08. 28.</span><span class="sxs-lookup"><span data-stu-id="997ee-238">28-08-2007</span></span></p></td>
<td><p><span data-ttu-id="997ee-239">Alkateg1</span><span class="sxs-lookup"><span data-stu-id="997ee-239">SubCat1</span></span></p></td>
<td><p><span data-ttu-id="997ee-240">9030</span><span class="sxs-lookup"><span data-stu-id="997ee-240">9030</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="997ee-241">Hónap</span><span class="sxs-lookup"><span data-stu-id="997ee-241">Month</span></span></p></td>
<td><p><span data-ttu-id="997ee-242">HUF</span><span class="sxs-lookup"><span data-stu-id="997ee-242">EUR</span></span></p></td>
<td><p><span data-ttu-id="997ee-243">550</span><span class="sxs-lookup"><span data-stu-id="997ee-243">550</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="997ee-244">A fentebb részletezett eljárást ismételve az Alkateg1 előfizetési csoport mindkét előfizetéséhez létrehoz egy előfizetési díjat.</span><span class="sxs-lookup"><span data-stu-id="997ee-244">You repeat the procedure described above to create subscription fees for both subscriptions in the subscription group Sub1.</span></span> <span data-ttu-id="997ee-245">A következő tábla megmutatja, hogy két tranzakció jön létre, vagyis előfizetési csoporthoz társított előfizetésenként egy:</span><span class="sxs-lookup"><span data-stu-id="997ee-245">The following table shows the transactions that are created for each subscription that is attached to the subscription group.</span></span>

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
<th><p><span data-ttu-id="997ee-246">Projekt dátuma</span><span class="sxs-lookup"><span data-stu-id="997ee-246">Project date</span></span></p></th>
<th><p><span data-ttu-id="997ee-247">Előfizetés</span><span class="sxs-lookup"><span data-stu-id="997ee-247">Subscription</span></span></p></th>
<th><p><span data-ttu-id="997ee-248">Project</span><span class="sxs-lookup"><span data-stu-id="997ee-248">Project</span></span></p></th>
<th><p><span data-ttu-id="997ee-249">Kategória</span><span class="sxs-lookup"><span data-stu-id="997ee-249">Category</span></span></p></th>
<th><p><span data-ttu-id="997ee-250">Kezdő dátum</span><span class="sxs-lookup"><span data-stu-id="997ee-250">Start date</span></span></p></th>
<th><p><span data-ttu-id="997ee-251">Befejezés</span><span class="sxs-lookup"><span data-stu-id="997ee-251">End date</span></span></p></th>
<th><p><span data-ttu-id="997ee-252">Értékesítés pénzneme</span><span class="sxs-lookup"><span data-stu-id="997ee-252">Sales currency</span></span></p></th>
<th><p><span data-ttu-id="997ee-253">Eladási ár</span><span class="sxs-lookup"><span data-stu-id="997ee-253">Sales price</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="997ee-254">2007. 07. 28.</span><span class="sxs-lookup"><span data-stu-id="997ee-254">28-07-2007</span></span></p></td>
<td><p><span data-ttu-id="997ee-255">00020_135</span><span class="sxs-lookup"><span data-stu-id="997ee-255">00020_135</span></span></p></td>
<td><p><span data-ttu-id="997ee-256">9030</span><span class="sxs-lookup"><span data-stu-id="997ee-256">9030</span></span></p></td>
<td><p><span data-ttu-id="997ee-257">Alkateg1</span><span class="sxs-lookup"><span data-stu-id="997ee-257">SubCat1</span></span></p></td>
<td><p><span data-ttu-id="997ee-258">2008. 01. 01.</span><span class="sxs-lookup"><span data-stu-id="997ee-258">01-01-2008</span></span></p></td>
<td><p><span data-ttu-id="997ee-259">2008. 03. 31.</span><span class="sxs-lookup"><span data-stu-id="997ee-259">31-03-2008</span></span></p></td>
<td><p><span data-ttu-id="997ee-260">HUF</span><span class="sxs-lookup"><span data-stu-id="997ee-260">EUR</span></span></p></td>
<td><p><span data-ttu-id="997ee-261">550</span><span class="sxs-lookup"><span data-stu-id="997ee-261">550</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="997ee-262">2008. 07. 28.</span><span class="sxs-lookup"><span data-stu-id="997ee-262">28-07-2008</span></span></p></td>
<td><p><span data-ttu-id="997ee-263">00021_135</span><span class="sxs-lookup"><span data-stu-id="997ee-263">00021_135</span></span></p></td>
<td><p><span data-ttu-id="997ee-264">9030</span><span class="sxs-lookup"><span data-stu-id="997ee-264">9030</span></span></p></td>
<td><p><span data-ttu-id="997ee-265">Alkateg2</span><span class="sxs-lookup"><span data-stu-id="997ee-265">SubCat2</span></span></p></td>
<td><p><span data-ttu-id="997ee-266">2008. 01. 01.</span><span class="sxs-lookup"><span data-stu-id="997ee-266">01-01-2008</span></span></p></td>
<td><p><span data-ttu-id="997ee-267">2008. 03. 31.</span><span class="sxs-lookup"><span data-stu-id="997ee-267">31-03-2008</span></span></p></td>
<td><p><span data-ttu-id="997ee-268">HUF</span><span class="sxs-lookup"><span data-stu-id="997ee-268">EUR</span></span></p></td>
<td><p><span data-ttu-id="997ee-269">500</span><span class="sxs-lookup"><span data-stu-id="997ee-269">500</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="997ee-270">A 00020\_135-ös előfizetéshez tartozó első tranzakcióban az 550 eurós eladási ár egy adott projekt és kategória kombinációjához beállított előfizetés eladási árból származik.</span><span class="sxs-lookup"><span data-stu-id="997ee-270">In the first transaction for subscription 00020\_135, the sales price of EUR 550 derives from the subscription sales price that is set up for the combination of the specific project and category.</span></span> <span data-ttu-id="997ee-271">A 00021\_135-ös előfizetéshez tartozó második tranzakcióban azért szerepel 500 euró a projekt-előfizetés eladási áraként, mert a 9030-as projekt és az Alkateg2 kategória kombinációjához nincs ár beállítva.</span><span class="sxs-lookup"><span data-stu-id="997ee-271">In the second transaction for subscription 00021\_135, the sales price of EUR 500 is used as the project subscription sales price because there is no price set up for the combination of project 9030 and category SubCat2.</span></span>

## <a name="see-also"></a><span data-ttu-id="997ee-272">Lásd még</span><span class="sxs-lookup"><span data-stu-id="997ee-272">See also</span></span>

[<span data-ttu-id="997ee-273">Előfizetési árak frissítése és indexelése</span><span class="sxs-lookup"><span data-stu-id="997ee-273">Update and index subscription sales prices</span></span>](update-and-index-subscription-sales-prices.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]