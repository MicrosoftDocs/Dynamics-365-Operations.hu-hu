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
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 35f4e3f3bdbdad7a48b89bad7da96d221f09bdb4
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4974212"
---
# <a name="subscription-sales-prices"></a><span data-ttu-id="2109f-103">Eőfizetés eladási árai</span><span class="sxs-lookup"><span data-stu-id="2109f-103">Subscription sales prices</span></span>   

[!include [banner](../includes/banner.md)]


<span data-ttu-id="2109f-104">Amikor előfizetést hoz létre, az eladási ár az **Eladási ár (előfizetés)** képernyőn létrehozott eladási ár beállításból jön létre.</span><span class="sxs-lookup"><span data-stu-id="2109f-104">When you create a subscription, the sales price is derived from the sales price setup that was created in the **Sales price (subscription)** form.</span></span>

<span data-ttu-id="2109f-105">Az **Eladási ár (előfizetés)** képernyőn egy-egy előfizetéshez is készíthet eladási árat, vagy létrehozhat olyan eladási árat, amely általánosabban érvényes.</span><span class="sxs-lookup"><span data-stu-id="2109f-105">In the **Sales price (subscription)** form, you can create sales prices for a specific subscription or you can create sales prices that apply more broadly.</span></span> <span data-ttu-id="2109f-106">Az eladási ár alkalmazásához az előfizetésre, meg kell egyeznie az előfizetés időszakkódjának és pénznemének az eladási ár időszakkódjával és pénznemével.</span><span class="sxs-lookup"><span data-stu-id="2109f-106">For a sales price to be applied to a subscription, the period code and the currency of the subscription must be identical to the period code and the currency of the sales price.</span></span>

<span data-ttu-id="2109f-107">Ha az előfizetés és az eladási ár időszakkódja és pénzneme megegyezik, akkor az előfizetés eladási ára az alábbi táblázatban szereplő prioritások alapján választható ki.</span><span class="sxs-lookup"><span data-stu-id="2109f-107">If the period code and currency are identical for the subscription and the sales price, subscription sales prices are selected on the basis of the priorities listed in the following table.</span></span> <span data-ttu-id="2109f-108">Az üres cella üres mezőt, az X pedig a előfizetésből létrejött tranzakcióban szereplő értékkel megegyező értéket jelent.</span><span class="sxs-lookup"><span data-stu-id="2109f-108">A blank cell in the table indicates an empty field and an X indicates a value that is equal to the value in the subscription from which the transaction is generated.</span></span>

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
<th><p><span data-ttu-id="2109f-109">. prioritás</span><span class="sxs-lookup"><span data-stu-id="2109f-109">Priority</span></span></p></th>
<th><p><span data-ttu-id="2109f-110"><strong>Kategória</strong></span><span class="sxs-lookup"><span data-stu-id="2109f-110"><strong>Category</strong></span></span></p></th>
<th><p><span data-ttu-id="2109f-111"><strong>Projektazonosító</strong></span><span class="sxs-lookup"><span data-stu-id="2109f-111"><strong>Project ID</strong></span></span></p></th>
<th><p><span data-ttu-id="2109f-112"><strong>Előfizetés</strong></span><span class="sxs-lookup"><span data-stu-id="2109f-112"><strong>Subscription</strong></span></span></p></th>
<th><p><span data-ttu-id="2109f-113"><strong>Értékesítés pénzneme</strong></span><span class="sxs-lookup"><span data-stu-id="2109f-113"><strong>Sales currency</strong></span></span></p></th>
<th><p><span data-ttu-id="2109f-114"><strong>Időszak kódja</strong></span><span class="sxs-lookup"><span data-stu-id="2109f-114"><strong>Period code</strong></span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2109f-115">1</span><span class="sxs-lookup"><span data-stu-id="2109f-115">1</span></span></p></td>
<td><p><span data-ttu-id="2109f-116">X</span><span class="sxs-lookup"><span data-stu-id="2109f-116">X</span></span></p></td>
<td><p><span data-ttu-id="2109f-117">X</span><span class="sxs-lookup"><span data-stu-id="2109f-117">X</span></span></p></td>
<td><p><span data-ttu-id="2109f-118">X</span><span class="sxs-lookup"><span data-stu-id="2109f-118">X</span></span></p></td>
<td><p><span data-ttu-id="2109f-119">X</span><span class="sxs-lookup"><span data-stu-id="2109f-119">X</span></span></p></td>
<td><p><span data-ttu-id="2109f-120">X</span><span class="sxs-lookup"><span data-stu-id="2109f-120">X</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2109f-121">2</span><span class="sxs-lookup"><span data-stu-id="2109f-121">2</span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="2109f-122">X</span><span class="sxs-lookup"><span data-stu-id="2109f-122">X</span></span></p></td>
<td><p><span data-ttu-id="2109f-123">X</span><span class="sxs-lookup"><span data-stu-id="2109f-123">X</span></span></p></td>
<td><p><span data-ttu-id="2109f-124">X</span><span class="sxs-lookup"><span data-stu-id="2109f-124">X</span></span></p></td>
<td><p><span data-ttu-id="2109f-125">X</span><span class="sxs-lookup"><span data-stu-id="2109f-125">X</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2109f-126">3</span><span class="sxs-lookup"><span data-stu-id="2109f-126">3</span></span></p></td>
<td><p><span data-ttu-id="2109f-127">X</span><span class="sxs-lookup"><span data-stu-id="2109f-127">X</span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="2109f-128">X</span><span class="sxs-lookup"><span data-stu-id="2109f-128">X</span></span></p></td>
<td><p><span data-ttu-id="2109f-129">X</span><span class="sxs-lookup"><span data-stu-id="2109f-129">X</span></span></p></td>
<td><p><span data-ttu-id="2109f-130">X</span><span class="sxs-lookup"><span data-stu-id="2109f-130">X</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2109f-131">4</span><span class="sxs-lookup"><span data-stu-id="2109f-131">4</span></span></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="2109f-132">X</span><span class="sxs-lookup"><span data-stu-id="2109f-132">X</span></span></p></td>
<td><p><span data-ttu-id="2109f-133">X</span><span class="sxs-lookup"><span data-stu-id="2109f-133">X</span></span></p></td>
<td><p><span data-ttu-id="2109f-134">X</span><span class="sxs-lookup"><span data-stu-id="2109f-134">X</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2109f-135">5</span><span class="sxs-lookup"><span data-stu-id="2109f-135">5</span></span></p></td>
<td><p><span data-ttu-id="2109f-136">X</span><span class="sxs-lookup"><span data-stu-id="2109f-136">X</span></span></p></td>
<td><p><span data-ttu-id="2109f-137">X</span><span class="sxs-lookup"><span data-stu-id="2109f-137">X</span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="2109f-138">X</span><span class="sxs-lookup"><span data-stu-id="2109f-138">X</span></span></p></td>
<td><p><span data-ttu-id="2109f-139">X</span><span class="sxs-lookup"><span data-stu-id="2109f-139">X</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2109f-140">6</span><span class="sxs-lookup"><span data-stu-id="2109f-140">6</span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="2109f-141">X</span><span class="sxs-lookup"><span data-stu-id="2109f-141">X</span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="2109f-142">X</span><span class="sxs-lookup"><span data-stu-id="2109f-142">X</span></span></p></td>
<td><p><span data-ttu-id="2109f-143">X</span><span class="sxs-lookup"><span data-stu-id="2109f-143">X</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2109f-144">7</span><span class="sxs-lookup"><span data-stu-id="2109f-144">7</span></span></p></td>
<td><p><span data-ttu-id="2109f-145">X</span><span class="sxs-lookup"><span data-stu-id="2109f-145">X</span></span></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="2109f-146">X</span><span class="sxs-lookup"><span data-stu-id="2109f-146">X</span></span></p></td>
<td><p><span data-ttu-id="2109f-147">X</span><span class="sxs-lookup"><span data-stu-id="2109f-147">X</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2109f-148">8</span><span class="sxs-lookup"><span data-stu-id="2109f-148">8</span></span></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="2109f-149">X</span><span class="sxs-lookup"><span data-stu-id="2109f-149">X</span></span></p></td>
<td><p><span data-ttu-id="2109f-150">X</span><span class="sxs-lookup"><span data-stu-id="2109f-150">X</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="2109f-151">Az előfizetési díj létrehozásakor a legnagyobb részletezettségű eladási ár (a fenti táblázatban jelöltek szerint) lesz az előfizetés eladási ára.</span><span class="sxs-lookup"><span data-stu-id="2109f-151">When a subscription fee is created, the sales price with the greatest level of detail, as noted in the table above, is selected as the subscription sales price.</span></span>

## <a name="update-and-index-subscription-sales-prices"></a><span data-ttu-id="2109f-152">Előfizetési árak frissítése és indexelése</span><span class="sxs-lookup"><span data-stu-id="2109f-152">Update and index subscription sales prices</span></span>

<span data-ttu-id="2109f-153">Az előfizetés eladási árat az alapár vagy az indexár frissítésével lehet módosítani.</span><span class="sxs-lookup"><span data-stu-id="2109f-153">You can update the subscription sales price by updating the base price or the index.</span></span> <span data-ttu-id="2109f-154">Százalékosan vagy új érték megadásával lehet átállítani.</span><span class="sxs-lookup"><span data-stu-id="2109f-154">You can update by a percentage or to a new value.</span></span>

## <a name="subscription-fee-sales-prices"></a><span data-ttu-id="2109f-155">Előfizetési díj eladási árak</span><span class="sxs-lookup"><span data-stu-id="2109f-155">Subscription fee sales prices</span></span>

<span data-ttu-id="2109f-156">Előfizetési díj létrehozásakor az előfizetés eladási árbeállítása a konkrét eladási ár alapja.</span><span class="sxs-lookup"><span data-stu-id="2109f-156">When you create a subscription fee, the sales price is based on the sales price setup of the subscription.</span></span> <span data-ttu-id="2109f-157">Használni az előfizetés eladási árbeállításából az alapárat lehet, vagy létre lehet hozni indexelt eladási árakat.</span><span class="sxs-lookup"><span data-stu-id="2109f-157">You can either use the base price from the subscription price setup or create indexed sales prices.</span></span>

## <a name="example"></a><span data-ttu-id="2109f-158">Példa</span><span class="sxs-lookup"><span data-stu-id="2109f-158">Example</span></span>

<span data-ttu-id="2109f-159">Szeretne 500 eurós előfizetés eladási árakat beállítani, egy új, 9030 kódú projekt számra.</span><span class="sxs-lookup"><span data-stu-id="2109f-159">You want to set up subscription sales prices of EUR 500 for a new project 9030.</span></span> <span data-ttu-id="2109f-160">Az **Eladási ár (előfizetés)** képernyőn létrehoz egy előfizetési eladásiár-sort a következő táblázat szerint.</span><span class="sxs-lookup"><span data-stu-id="2109f-160">In the **Sales price (subscription)** form, you create a subscription sales price line as indicated in the following table.</span></span>

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
<th><p><span data-ttu-id="2109f-161">Érvényesség kezdete</span><span class="sxs-lookup"><span data-stu-id="2109f-161">Valid from</span></span></p></th>
<th><p><span data-ttu-id="2109f-162">Kategória</span><span class="sxs-lookup"><span data-stu-id="2109f-162">Category</span></span></p></th>
<th><p><span data-ttu-id="2109f-163">Project</span><span class="sxs-lookup"><span data-stu-id="2109f-163">Project</span></span></p></th>
<th><p><span data-ttu-id="2109f-164">Előfizetés</span><span class="sxs-lookup"><span data-stu-id="2109f-164">Subscription</span></span></p></th>
<th><p><span data-ttu-id="2109f-165">Időszak kódja</span><span class="sxs-lookup"><span data-stu-id="2109f-165">Period code</span></span></p></th>
<th><p><span data-ttu-id="2109f-166">Értékesítés pénzneme</span><span class="sxs-lookup"><span data-stu-id="2109f-166">Sales currency</span></span></p></th>
<th><p><span data-ttu-id="2109f-167">Eladási ár</span><span class="sxs-lookup"><span data-stu-id="2109f-167">Sales price</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2109f-168">2006. 08. 28.</span><span class="sxs-lookup"><span data-stu-id="2109f-168">28-08-2006</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2109f-169">9030</span><span class="sxs-lookup"><span data-stu-id="2109f-169">9030</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2109f-170">Hónap</span><span class="sxs-lookup"><span data-stu-id="2109f-170">Month</span></span></p></td>
<td><p><span data-ttu-id="2109f-171">HUF</span><span class="sxs-lookup"><span data-stu-id="2109f-171">EUR</span></span></p></td>
<td><p><span data-ttu-id="2109f-172">500</span><span class="sxs-lookup"><span data-stu-id="2109f-172">500</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="2109f-173">Ne feledje, hogy a **Kategória** és az **Előfizetés** mező üres.</span><span class="sxs-lookup"><span data-stu-id="2109f-173">Note that the **Category** and **Subscription** fields are empty.</span></span>

<span data-ttu-id="2109f-174">Ezután a következő előfizetéseket hozza létre.</span><span class="sxs-lookup"><span data-stu-id="2109f-174">You then create the following subscriptions.</span></span>

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
<th><p><span data-ttu-id="2109f-175">Előfizetés szolgáltatásra</span><span class="sxs-lookup"><span data-stu-id="2109f-175">Service subscription</span></span></p></th>
<th><p><span data-ttu-id="2109f-176">Project</span><span class="sxs-lookup"><span data-stu-id="2109f-176">Project</span></span></p></th>
<th><p><span data-ttu-id="2109f-177">Előfizetési csoport</span><span class="sxs-lookup"><span data-stu-id="2109f-177">Subscription group</span></span></p></th>
<th><p><span data-ttu-id="2109f-178">Kategória</span><span class="sxs-lookup"><span data-stu-id="2109f-178">Category</span></span></p></th>
<th><p><span data-ttu-id="2109f-179">Pénznem</span><span class="sxs-lookup"><span data-stu-id="2109f-179">Currency</span></span></p></th>
<th><p><span data-ttu-id="2109f-180">Időszak kódja</span><span class="sxs-lookup"><span data-stu-id="2109f-180">Period code</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2109f-181">00020_135</span><span class="sxs-lookup"><span data-stu-id="2109f-181">00020_135</span></span></p></td>
<td><p><span data-ttu-id="2109f-182">9030</span><span class="sxs-lookup"><span data-stu-id="2109f-182">9030</span></span></p></td>
<td><p><span data-ttu-id="2109f-183">Al1</span><span class="sxs-lookup"><span data-stu-id="2109f-183">Sub1</span></span></p></td>
<td><p><span data-ttu-id="2109f-184">Alkateg1</span><span class="sxs-lookup"><span data-stu-id="2109f-184">SubCat1</span></span></p></td>
<td><p><span data-ttu-id="2109f-185">HUF</span><span class="sxs-lookup"><span data-stu-id="2109f-185">EUR</span></span></p></td>
<td><p><span data-ttu-id="2109f-186">Havi</span><span class="sxs-lookup"><span data-stu-id="2109f-186">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2109f-187">00021_135</span><span class="sxs-lookup"><span data-stu-id="2109f-187">00021_135</span></span></p></td>
<td><p><span data-ttu-id="2109f-188">9030</span><span class="sxs-lookup"><span data-stu-id="2109f-188">9030</span></span></p></td>
<td><p><span data-ttu-id="2109f-189">Al1</span><span class="sxs-lookup"><span data-stu-id="2109f-189">Sub1</span></span></p></td>
<td><p><span data-ttu-id="2109f-190">Alkateg2</span><span class="sxs-lookup"><span data-stu-id="2109f-190">SubCat2</span></span></p></td>
<td><p><span data-ttu-id="2109f-191">HUF</span><span class="sxs-lookup"><span data-stu-id="2109f-191">EUR</span></span></p></td>
<td><p><span data-ttu-id="2109f-192">Havi</span><span class="sxs-lookup"><span data-stu-id="2109f-192">Monthly</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="2109f-193">Ekkor létre hozza az előfizetési díjakat mindkét előfizetéshez a Al1 előfizetési csoportban:</span><span class="sxs-lookup"><span data-stu-id="2109f-193">Now you create subscription fees for both subscriptions in the subscription group Sub1:</span></span>

1.  <span data-ttu-id="2109f-194">Kattintson a következőkre: **Szolgáltatáskezelés**\>**Beállítás**\>**Szolgáltatási előfizetések**\>**Előfizetési csoportok**.</span><span class="sxs-lookup"><span data-stu-id="2109f-194">Click **Service management** \> **Setup** \> **Service subscriptions** \> **Subscription groups**.</span></span>

2.  <span data-ttu-id="2109f-195">Az **Előfizetési csoportok** képernyőn kattintson ide: **Funkció** \> **Előfizetési díj létrehozása**.</span><span class="sxs-lookup"><span data-stu-id="2109f-195">In the **Subscription groups** form, click **Function** \> **Create subscription fee**.</span></span>

3.  <span data-ttu-id="2109f-196">Írja be a megfelelő adatokat az **Előfizetési díj létrehozása** képernyő mezőibe.</span><span class="sxs-lookup"><span data-stu-id="2109f-196">In the **Create subscription fee** form, enter the appropriate information.</span></span> <span data-ttu-id="2109f-197">A díjtranzakciókról az [Előfizetési díj tranzakcióinak létrehozása](create-subscription-fee-transactions.md) című témakörben olvashat bővebben.</span><span class="sxs-lookup"><span data-stu-id="2109f-197">For more information, see [Create subscription fee transactions](create-subscription-fee-transactions.md).</span></span>

<span data-ttu-id="2109f-198">Előfizetési díjak 500 EURÓS eladási árral rendelkezve mindkét előfizetéséhez, létrejönnek a következő táblázatban látható módon.</span><span class="sxs-lookup"><span data-stu-id="2109f-198">Subscription fees that have a sales price of EUR 500 are created for both subscriptions, as shown in the following table.</span></span>

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
<th><p><span data-ttu-id="2109f-199">Projekt dátuma</span><span class="sxs-lookup"><span data-stu-id="2109f-199">Project date</span></span></p></th>
<th><p><span data-ttu-id="2109f-200">Előfizetés szolgáltatásra</span><span class="sxs-lookup"><span data-stu-id="2109f-200">Service subscription</span></span></p></th>
<th><p><span data-ttu-id="2109f-201">Project</span><span class="sxs-lookup"><span data-stu-id="2109f-201">Project</span></span></p></th>
<th><p><span data-ttu-id="2109f-202">Kategória</span><span class="sxs-lookup"><span data-stu-id="2109f-202">Category</span></span></p></th>
<th><p><span data-ttu-id="2109f-203">Kezdő dátum</span><span class="sxs-lookup"><span data-stu-id="2109f-203">Start date</span></span></p></th>
<th><p><span data-ttu-id="2109f-204">Záró dátum</span><span class="sxs-lookup"><span data-stu-id="2109f-204">End date</span></span></p></th>
<th><p><span data-ttu-id="2109f-205">Értékesítés pénzneme</span><span class="sxs-lookup"><span data-stu-id="2109f-205">Sales currency</span></span></p></th>
<th><p><span data-ttu-id="2109f-206">Eladási ár</span><span class="sxs-lookup"><span data-stu-id="2109f-206">Sales price</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2109f-207">2006. 08. 28.</span><span class="sxs-lookup"><span data-stu-id="2109f-207">28-08-2006</span></span></p></td>
<td><p><span data-ttu-id="2109f-208">00020_135</span><span class="sxs-lookup"><span data-stu-id="2109f-208">00020_135</span></span></p></td>
<td><p><span data-ttu-id="2109f-209">9030</span><span class="sxs-lookup"><span data-stu-id="2109f-209">9030</span></span></p></td>
<td><p><span data-ttu-id="2109f-210">Alkateg1</span><span class="sxs-lookup"><span data-stu-id="2109f-210">SubCat1</span></span></p></td>
<td><p><span data-ttu-id="2109f-211">2007. 01. 01.</span><span class="sxs-lookup"><span data-stu-id="2109f-211">01-01-2007</span></span></p></td>
<td><p><span data-ttu-id="2109f-212">2007. 03. 31.</span><span class="sxs-lookup"><span data-stu-id="2109f-212">31-03-2007</span></span></p></td>
<td><p><span data-ttu-id="2109f-213">HUF</span><span class="sxs-lookup"><span data-stu-id="2109f-213">EUR</span></span></p></td>
<td><p><span data-ttu-id="2109f-214">500</span><span class="sxs-lookup"><span data-stu-id="2109f-214">500</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2109f-215">2006. 08. 28.</span><span class="sxs-lookup"><span data-stu-id="2109f-215">28-08-2006</span></span></p></td>
<td><p><span data-ttu-id="2109f-216">00021_135</span><span class="sxs-lookup"><span data-stu-id="2109f-216">00021_135</span></span></p></td>
<td><p><span data-ttu-id="2109f-217">9030</span><span class="sxs-lookup"><span data-stu-id="2109f-217">9030</span></span></p></td>
<td><p><span data-ttu-id="2109f-218">Alkateg2</span><span class="sxs-lookup"><span data-stu-id="2109f-218">SubCat2</span></span></p></td>
<td><p><span data-ttu-id="2109f-219">2007. 01. 01.</span><span class="sxs-lookup"><span data-stu-id="2109f-219">01-01-2007</span></span></p></td>
<td><p><span data-ttu-id="2109f-220">2007. 03. 31.</span><span class="sxs-lookup"><span data-stu-id="2109f-220">31-03-2007</span></span></p></td>
<td><p><span data-ttu-id="2109f-221">HUF</span><span class="sxs-lookup"><span data-stu-id="2109f-221">EUR</span></span></p></td>
<td><p><span data-ttu-id="2109f-222">500</span><span class="sxs-lookup"><span data-stu-id="2109f-222">500</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="2109f-223">Később úgy dönt, hogy a 9030-as projekt Alkateg1 kategóriájához szeretne eladási árakat megadni.</span><span class="sxs-lookup"><span data-stu-id="2109f-223">Later, you decide that you want to specify sales prices for the category SubCat1 for project 9030.</span></span> <span data-ttu-id="2109f-224">Ezért a 9030-as projekt és a Alkateg1 díjkategória kombinációjához létrehoz egy új eladásiár-sort 550 eurós eladási árral.</span><span class="sxs-lookup"><span data-stu-id="2109f-224">Therefore, you create a new sales price line that has a sales price of EUR 550 for the combination of project 9030 and fee category SubCat1.</span></span> <span data-ttu-id="2109f-225">Ezzel már két előfizetés eladásiár-sor szerepel a 9030-as projektnél, a következő táblázatban látható módon:</span><span class="sxs-lookup"><span data-stu-id="2109f-225">There are now two subscription sales price lines for project 9030, as shown in the following table.</span></span>

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
<th><p><span data-ttu-id="2109f-226">Érvényesség kezdete</span><span class="sxs-lookup"><span data-stu-id="2109f-226">Valid from</span></span></p></th>
<th><p><span data-ttu-id="2109f-227">Kategória</span><span class="sxs-lookup"><span data-stu-id="2109f-227">Category</span></span></p></th>
<th><p><span data-ttu-id="2109f-228">Project</span><span class="sxs-lookup"><span data-stu-id="2109f-228">Project</span></span></p></th>
<th><p><span data-ttu-id="2109f-229">Előfizetés</span><span class="sxs-lookup"><span data-stu-id="2109f-229">Subscription</span></span></p></th>
<th><p><span data-ttu-id="2109f-230">Időszak kódja</span><span class="sxs-lookup"><span data-stu-id="2109f-230">Period code</span></span></p></th>
<th><p><span data-ttu-id="2109f-231">Pénznem</span><span class="sxs-lookup"><span data-stu-id="2109f-231">Currency</span></span></p></th>
<th><p><span data-ttu-id="2109f-232">Eladási ár</span><span class="sxs-lookup"><span data-stu-id="2109f-232">Sales price</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2109f-233">2007. 08. 28.</span><span class="sxs-lookup"><span data-stu-id="2109f-233">28-08-2007</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2109f-234">9030</span><span class="sxs-lookup"><span data-stu-id="2109f-234">9030</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2109f-235">Hónap</span><span class="sxs-lookup"><span data-stu-id="2109f-235">Month</span></span></p></td>
<td><p><span data-ttu-id="2109f-236">HUF</span><span class="sxs-lookup"><span data-stu-id="2109f-236">EUR</span></span></p></td>
<td><p><span data-ttu-id="2109f-237">500</span><span class="sxs-lookup"><span data-stu-id="2109f-237">500</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2109f-238">2007. 08. 28.</span><span class="sxs-lookup"><span data-stu-id="2109f-238">28-08-2007</span></span></p></td>
<td><p><span data-ttu-id="2109f-239">Alkateg1</span><span class="sxs-lookup"><span data-stu-id="2109f-239">SubCat1</span></span></p></td>
<td><p><span data-ttu-id="2109f-240">9030</span><span class="sxs-lookup"><span data-stu-id="2109f-240">9030</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2109f-241">Hónap</span><span class="sxs-lookup"><span data-stu-id="2109f-241">Month</span></span></p></td>
<td><p><span data-ttu-id="2109f-242">HUF</span><span class="sxs-lookup"><span data-stu-id="2109f-242">EUR</span></span></p></td>
<td><p><span data-ttu-id="2109f-243">550</span><span class="sxs-lookup"><span data-stu-id="2109f-243">550</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="2109f-244">A fentebb részletezett eljárást ismételve az Alkateg1 előfizetési csoport mindkét előfizetéséhez létrehoz egy előfizetési díjat.</span><span class="sxs-lookup"><span data-stu-id="2109f-244">You repeat the procedure described above to create subscription fees for both subscriptions in the subscription group Sub1.</span></span> <span data-ttu-id="2109f-245">A következő tábla megmutatja, hogy két tranzakció jön létre, vagyis előfizetési csoporthoz társított előfizetésenként egy:</span><span class="sxs-lookup"><span data-stu-id="2109f-245">The following table shows the transactions that are created for each subscription that is attached to the subscription group.</span></span>

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
<th><p><span data-ttu-id="2109f-246">Projekt dátuma</span><span class="sxs-lookup"><span data-stu-id="2109f-246">Project date</span></span></p></th>
<th><p><span data-ttu-id="2109f-247">Előfizetés</span><span class="sxs-lookup"><span data-stu-id="2109f-247">Subscription</span></span></p></th>
<th><p><span data-ttu-id="2109f-248">Project</span><span class="sxs-lookup"><span data-stu-id="2109f-248">Project</span></span></p></th>
<th><p><span data-ttu-id="2109f-249">Kategória</span><span class="sxs-lookup"><span data-stu-id="2109f-249">Category</span></span></p></th>
<th><p><span data-ttu-id="2109f-250">Kezdő dátum</span><span class="sxs-lookup"><span data-stu-id="2109f-250">Start date</span></span></p></th>
<th><p><span data-ttu-id="2109f-251">Befejezés</span><span class="sxs-lookup"><span data-stu-id="2109f-251">End date</span></span></p></th>
<th><p><span data-ttu-id="2109f-252">Értékesítés pénzneme</span><span class="sxs-lookup"><span data-stu-id="2109f-252">Sales currency</span></span></p></th>
<th><p><span data-ttu-id="2109f-253">Eladási ár</span><span class="sxs-lookup"><span data-stu-id="2109f-253">Sales price</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2109f-254">2007. 07. 28.</span><span class="sxs-lookup"><span data-stu-id="2109f-254">28-07-2007</span></span></p></td>
<td><p><span data-ttu-id="2109f-255">00020_135</span><span class="sxs-lookup"><span data-stu-id="2109f-255">00020_135</span></span></p></td>
<td><p><span data-ttu-id="2109f-256">9030</span><span class="sxs-lookup"><span data-stu-id="2109f-256">9030</span></span></p></td>
<td><p><span data-ttu-id="2109f-257">Alkateg1</span><span class="sxs-lookup"><span data-stu-id="2109f-257">SubCat1</span></span></p></td>
<td><p><span data-ttu-id="2109f-258">2008. 01. 01.</span><span class="sxs-lookup"><span data-stu-id="2109f-258">01-01-2008</span></span></p></td>
<td><p><span data-ttu-id="2109f-259">2008. 03. 31.</span><span class="sxs-lookup"><span data-stu-id="2109f-259">31-03-2008</span></span></p></td>
<td><p><span data-ttu-id="2109f-260">HUF</span><span class="sxs-lookup"><span data-stu-id="2109f-260">EUR</span></span></p></td>
<td><p><span data-ttu-id="2109f-261">550</span><span class="sxs-lookup"><span data-stu-id="2109f-261">550</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2109f-262">2008. 07. 28.</span><span class="sxs-lookup"><span data-stu-id="2109f-262">28-07-2008</span></span></p></td>
<td><p><span data-ttu-id="2109f-263">00021_135</span><span class="sxs-lookup"><span data-stu-id="2109f-263">00021_135</span></span></p></td>
<td><p><span data-ttu-id="2109f-264">9030</span><span class="sxs-lookup"><span data-stu-id="2109f-264">9030</span></span></p></td>
<td><p><span data-ttu-id="2109f-265">Alkateg2</span><span class="sxs-lookup"><span data-stu-id="2109f-265">SubCat2</span></span></p></td>
<td><p><span data-ttu-id="2109f-266">2008. 01. 01.</span><span class="sxs-lookup"><span data-stu-id="2109f-266">01-01-2008</span></span></p></td>
<td><p><span data-ttu-id="2109f-267">2008. 03. 31.</span><span class="sxs-lookup"><span data-stu-id="2109f-267">31-03-2008</span></span></p></td>
<td><p><span data-ttu-id="2109f-268">HUF</span><span class="sxs-lookup"><span data-stu-id="2109f-268">EUR</span></span></p></td>
<td><p><span data-ttu-id="2109f-269">500</span><span class="sxs-lookup"><span data-stu-id="2109f-269">500</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="2109f-270">A 00020\_135-ös előfizetéshez tartozó első tranzakcióban az 550 eurós eladási ár egy adott projekt és kategória kombinációjához beállított előfizetés eladási árból származik.</span><span class="sxs-lookup"><span data-stu-id="2109f-270">In the first transaction for subscription 00020\_135, the sales price of EUR 550 derives from the subscription sales price that is set up for the combination of the specific project and category.</span></span> <span data-ttu-id="2109f-271">A 00021\_135-ös előfizetéshez tartozó második tranzakcióban azért szerepel 500 euró a projekt-előfizetés eladási áraként, mert a 9030-as projekt és az Alkateg2 kategória kombinációjához nincs ár beállítva.</span><span class="sxs-lookup"><span data-stu-id="2109f-271">In the second transaction for subscription 00021\_135, the sales price of EUR 500 is used as the project subscription sales price because there is no price set up for the combination of project 9030 and category SubCat2.</span></span>

## <a name="see-also"></a><span data-ttu-id="2109f-272">Lásd még</span><span class="sxs-lookup"><span data-stu-id="2109f-272">See also</span></span>

[<span data-ttu-id="2109f-273">Előfizetési árak frissítése és indexelése</span><span class="sxs-lookup"><span data-stu-id="2109f-273">Update and index subscription sales prices</span></span>](update-and-index-subscription-sales-prices.md)

  


