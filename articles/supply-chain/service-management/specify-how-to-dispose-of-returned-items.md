---
title: "A visszaadott cikkek kivezetési módjának megadása"
description: "A visszaadott cikkek kivezetési módjának megadása."
author: YuyuScheller
manager: AnnBe
ms.date: 05/07/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventQuarantineOrder
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: YuyuScheller
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: d25a53ac58b0ab44605af253f174ba2ec7b74174
ms.contentlocale: hu-hu
ms.lasthandoff: 05/08/2018

---

# <a name="specify-how-to-dispose-of-returned-items"></a><span data-ttu-id="fb441-103">A visszaadott cikkek kivezetési módjának megadása</span><span class="sxs-lookup"><span data-stu-id="fb441-103">Specify how to dispose of returned items</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="fb441-104">Visszárurendelés kezelése esetén egy visszajuttatási okkóddal meg kell adnia, hogy a terméket miért küldték vissza.</span><span class="sxs-lookup"><span data-stu-id="fb441-104">When you handle a return order, you must specify a reason return code to identify why the product is being returned.</span></span> <span data-ttu-id="fb441-105">Emellett egy intézkedéskóddal és egy intézkedési művelettel meg kell határoznia, hogy mi történjen a visszaküldött termékkel.</span><span class="sxs-lookup"><span data-stu-id="fb441-105">You must also specify a disposition code and a disposition action to determine what should be done with the returned product itself.</span></span>

<span data-ttu-id="fb441-106">Az intézkedési kód a visszárurendelés létrehozásakor, a cikkbeérkezés regisztrálásakor illetve a csomagjegyzék frissítésekor, valamint a karanténutasítás befejezésekor alkalmazható.</span><span class="sxs-lookup"><span data-stu-id="fb441-106">A disposition code can be applied when you create the return order, register item arrival or packing-slip update an item arrival, and end a quarantine order.</span></span>

<span data-ttu-id="fb441-107">Az üzleti folyamatoknak megfelelően igény szerint bármilyen intézkedési kódot meghatározhat.</span><span class="sxs-lookup"><span data-stu-id="fb441-107">You can define any disposition codes that you need in order to support the business processes.</span></span> <span data-ttu-id="fb441-108">A következő táblázatban néhány jellemzően használt kód szerepel, amely a visszárukra vonatkozó intézkedés kijelölésére használható.</span><span class="sxs-lookup"><span data-stu-id="fb441-108">The following table provides a set of typically used codes to assign return-item disposition.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="fb441-109">Intézkedés típusa</span><span class="sxs-lookup"><span data-stu-id="fb441-109">Disposition type</span></span></p></th>
<th><p><span data-ttu-id="fb441-110">Általános kód</span><span class="sxs-lookup"><span data-stu-id="fb441-110">Common code</span></span></p></th>
<th><p><span data-ttu-id="fb441-111">Leírás</span><span class="sxs-lookup"><span data-stu-id="fb441-111">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fb441-112">Kivezetés</span><span class="sxs-lookup"><span data-stu-id="fb441-112">Disposal</span></span></p></td>
<td><p><span data-ttu-id="fb441-113">SC</span><span class="sxs-lookup"><span data-stu-id="fb441-113">SC</span></span></p></td>
<td><p><span data-ttu-id="fb441-114">Selejtezés/megsemmisítés</span><span class="sxs-lookup"><span data-stu-id="fb441-114">Scrap/Destroy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb441-115">Kivezetés</span><span class="sxs-lookup"><span data-stu-id="fb441-115">Disposal</span></span></p></td>
<td><p><span data-ttu-id="fb441-116">DC</span><span class="sxs-lookup"><span data-stu-id="fb441-116">DC</span></span></p></td>
<td><p><span data-ttu-id="fb441-117">Adományozás jótékony célra</span><span class="sxs-lookup"><span data-stu-id="fb441-117">Donate to Charity</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb441-118">Kivezetés</span><span class="sxs-lookup"><span data-stu-id="fb441-118">Disposal</span></span></p></td>
<td><p><span data-ttu-id="fb441-119">TD</span><span class="sxs-lookup"><span data-stu-id="fb441-119">TD</span></span></p></td>
<td><p><span data-ttu-id="fb441-120">Átadás külső félnek</span><span class="sxs-lookup"><span data-stu-id="fb441-120">Third-Party Disposal</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb441-121">Kivezetés</span><span class="sxs-lookup"><span data-stu-id="fb441-121">Disposal</span></span></p></td>
<td><p><span data-ttu-id="fb441-122">SL</span><span class="sxs-lookup"><span data-stu-id="fb441-122">SL</span></span></p></td>
<td><p><span data-ttu-id="fb441-123">Megmentés</span><span class="sxs-lookup"><span data-stu-id="fb441-123">Salvage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb441-124">Kivezetés</span><span class="sxs-lookup"><span data-stu-id="fb441-124">Disposal</span></span></p></td>
<td><p><span data-ttu-id="fb441-125">TS</span><span class="sxs-lookup"><span data-stu-id="fb441-125">TS</span></span></p></td>
<td><p><span data-ttu-id="fb441-126">Eladás külső félnek (másodlagos piacok)</span><span class="sxs-lookup"><span data-stu-id="fb441-126">Third-Party Sale (Secondary Markets)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb441-127">Javítás/módosítás</span><span class="sxs-lookup"><span data-stu-id="fb441-127">Repair/Modify</span></span></p></td>
<td><p><span data-ttu-id="fb441-128">RW</span><span class="sxs-lookup"><span data-stu-id="fb441-128">RW</span></span></p></td>
<td><p><span data-ttu-id="fb441-129">Átdolgozás</span><span class="sxs-lookup"><span data-stu-id="fb441-129">Rework</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb441-130">Javítás/módosítás</span><span class="sxs-lookup"><span data-stu-id="fb441-130">Repair/Modify</span></span></p></td>
<td><p><span data-ttu-id="fb441-131">RF</span><span class="sxs-lookup"><span data-stu-id="fb441-131">RF</span></span></p></td>
<td><p><span data-ttu-id="fb441-132">Újragyártás/hasznosítás</span><span class="sxs-lookup"><span data-stu-id="fb441-132">Remanufacture/Refurbish</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb441-133">Javítás/módosítás</span><span class="sxs-lookup"><span data-stu-id="fb441-133">Repair/Modify</span></span></p></td>
<td><p><span data-ttu-id="fb441-134">MD</span><span class="sxs-lookup"><span data-stu-id="fb441-134">MD</span></span></p></td>
<td><p><span data-ttu-id="fb441-135">Módosítás</span><span class="sxs-lookup"><span data-stu-id="fb441-135">Modify</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb441-136">Javítás/módosítás</span><span class="sxs-lookup"><span data-stu-id="fb441-136">Repair/Modify</span></span></p></td>
<td><p><span data-ttu-id="fb441-137">RP</span><span class="sxs-lookup"><span data-stu-id="fb441-137">RP</span></span></p></td>
<td><p><span data-ttu-id="fb441-138">Javítás</span><span class="sxs-lookup"><span data-stu-id="fb441-138">Repair</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb441-139">Javítás/módosítás</span><span class="sxs-lookup"><span data-stu-id="fb441-139">Repair/Modify</span></span></p></td>
<td><p><span data-ttu-id="fb441-140">RV</span><span class="sxs-lookup"><span data-stu-id="fb441-140">RV</span></span></p></td>
<td><p><span data-ttu-id="fb441-141">Visszajuttatás a szállítóhoz</span><span class="sxs-lookup"><span data-stu-id="fb441-141">Return to Vendor</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb441-142">Egyéb</span><span class="sxs-lookup"><span data-stu-id="fb441-142">Other</span></span></p></td>
<td><p><span data-ttu-id="fb441-143">AI</span><span class="sxs-lookup"><span data-stu-id="fb441-143">AI</span></span></p></td>
<td><p><span data-ttu-id="fb441-144">Felhasználás változatlan formában</span><span class="sxs-lookup"><span data-stu-id="fb441-144">Use as is</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb441-145">Egyéb</span><span class="sxs-lookup"><span data-stu-id="fb441-145">Other</span></span></p></td>
<td><p><span data-ttu-id="fb441-146">RS</span><span class="sxs-lookup"><span data-stu-id="fb441-146">RS</span></span></p></td>
<td><p><span data-ttu-id="fb441-147">Viszontértékesítés</span><span class="sxs-lookup"><span data-stu-id="fb441-147">Resale</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb441-148">Egyéb</span><span class="sxs-lookup"><span data-stu-id="fb441-148">Other</span></span></p></td>
<td><p><span data-ttu-id="fb441-149">EX</span><span class="sxs-lookup"><span data-stu-id="fb441-149">EX</span></span></p></td>
<td><p><span data-ttu-id="fb441-150">Átváltás</span><span class="sxs-lookup"><span data-stu-id="fb441-150">Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb441-151">Egyéb</span><span class="sxs-lookup"><span data-stu-id="fb441-151">Other</span></span></p></td>
<td><p><span data-ttu-id="fb441-152">MS</span><span class="sxs-lookup"><span data-stu-id="fb441-152">MS</span></span></p></td>
<td><p><span data-ttu-id="fb441-153">Vegyes</span><span class="sxs-lookup"><span data-stu-id="fb441-153">Miscellaneous</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="fb441-154">Minden egyes intézkedési kódhoz választania kell egy intézkedési műveletet is.</span><span class="sxs-lookup"><span data-stu-id="fb441-154">For each disposition code that you define, you must select a disposition action.</span></span> <span data-ttu-id="fb441-155">Az intézkedési művelet az intézkedési kód fizikai és pénzügyi vonatkozásait határozza meg.</span><span class="sxs-lookup"><span data-stu-id="fb441-155">The disposition action determines the physical and financial implications of the disposition codes.</span></span> <span data-ttu-id="fb441-156">Az intézkedési művelet határozza meg többek között a visszáru fizikai kezelési módját, pénzügyi hatását, illetve azt, hogy kell-e cserecikket küldeni az ügyfélnek.</span><span class="sxs-lookup"><span data-stu-id="fb441-156">For example, the disposition action determines the physical handling of the returned item, the financial effect of the returned item, and if a replacement item must be sent to the customer.</span></span> <span data-ttu-id="fb441-157">Az üzleti igényeknek megfelelően korlátlan számú intézkedési kódot definiálhat, azonban mindössze hat előre definiált intézkedési művelet közül választhat.</span><span class="sxs-lookup"><span data-stu-id="fb441-157">You can define an unlimited number of disposition codes according to your business needs, but there are only six predefined disposition actions that you can select from.</span></span> <span data-ttu-id="fb441-158">Az alábbi táblázatban az intézkedési műveletek és definícióik szerepelnek.</span><span class="sxs-lookup"><span data-stu-id="fb441-158">The following table provides the disposition actions and their definitions.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="fb441-159">Intézkedési művelet</span><span class="sxs-lookup"><span data-stu-id="fb441-159">Disposition action</span></span></p></th>
<th><p><span data-ttu-id="fb441-160">Leírás</span><span class="sxs-lookup"><span data-stu-id="fb441-160">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fb441-161"><strong>Jóváírás</strong></span><span class="sxs-lookup"><span data-stu-id="fb441-161"><strong>Credit</strong></span></span></p></td>
<td><p><span data-ttu-id="fb441-162">A cikk visszahelyezése a készletbe és a cikk értékének jóváírása a vevő számára.</span><span class="sxs-lookup"><span data-stu-id="fb441-162">Return the item to inventory and credit the customer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb441-163"><strong>Csak követelés</strong></span><span class="sxs-lookup"><span data-stu-id="fb441-163"><strong>Credit only</strong></span></span></p></td>
<td><p><span data-ttu-id="fb441-164">A cikk értékének jóváírása a cikk visszaküldésének igénylése nélkül.</span><span class="sxs-lookup"><span data-stu-id="fb441-164">Credit the customer without requiring or expecting the item to be returned.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb441-165"><strong>Selejt</strong></span><span class="sxs-lookup"><span data-stu-id="fb441-165"><strong>Scrap</strong></span></span></p></td>
<td><p><span data-ttu-id="fb441-166">A cikk leselejtezése és értékének jóváírása a vevő számára.</span><span class="sxs-lookup"><span data-stu-id="fb441-166">Scrap the item and credit the customer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb441-167"><strong>Csere és jóváírás</strong></span><span class="sxs-lookup"><span data-stu-id="fb441-167"><strong>Replace and credit</strong></span></span></p></td>
<td><p><span data-ttu-id="fb441-168">A cikk visszahelyezése a készletbe, csererendelés létrehozása és az összeg jóváírása a vevő számára.</span><span class="sxs-lookup"><span data-stu-id="fb441-168">Return the item to inventory, create a replacement order, and credit the customer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb441-169"><strong>Csere és selejtezés</strong></span><span class="sxs-lookup"><span data-stu-id="fb441-169"><strong>Replace and scrap</strong></span></span></p></td>
<td><p><span data-ttu-id="fb441-170">A cikk leselejtezése, csererendelés létrehozása és az összes jóváírása a vevő számára.</span><span class="sxs-lookup"><span data-stu-id="fb441-170">Scrap the item, create a replacement order, and credit the customer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb441-171"><strong>Vissza a vevőnek</strong></span><span class="sxs-lookup"><span data-stu-id="fb441-171"><strong>Return to customer</strong></span></span></p></td>
<td><p><span data-ttu-id="fb441-172">A visszáru elutasítása és visszaküldése a vevőnek.</span><span class="sxs-lookup"><span data-stu-id="fb441-172">Reject the returned item and return it to the customer.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="select-a-disposition-code-for-a-quarantine-order"></a><span data-ttu-id="fb441-173">Intézkedési kód választása karanténutasításhoz</span><span class="sxs-lookup"><span data-stu-id="fb441-173">Select a disposition code for a quarantine order</span></span>

1.  <span data-ttu-id="fb441-174">Kattintson ide: **Készletkezelés** \> **Időszakos** \> **Minőségkezelés** \> **Karanténutasítások**.</span><span class="sxs-lookup"><span data-stu-id="fb441-174">Click **Inventory management** \> **Periodic** \> **Quality management** \> **Quarantine orders**.</span></span>

2.  <span data-ttu-id="fb441-175">Meglévő karanténutasításokhoz válasszon egy műveletet az **Áttekintés** lap **Intézkedési kód** mezőjében.</span><span class="sxs-lookup"><span data-stu-id="fb441-175">For an existing quarantine order, select an action from the **Disposition code** field on the **Overview** tab.</span></span>



## <a name="see-also"></a><span data-ttu-id="fb441-176">Lásd még</span><span class="sxs-lookup"><span data-stu-id="fb441-176">See also</span></span>

<span data-ttu-id="fb441-177">[Karanténutasítás (képernyő)](https://technet.microsoft.com/en-us/library/aa554073(v=ax.60))</span><span class="sxs-lookup"><span data-stu-id="fb441-177">[Quarantine order (form)](https://technet.microsoft.com/en-us/library/aa554073(v=ax.60))</span></span>

<span data-ttu-id="fb441-178">[Intézkedési kódok (képernyő)](https://technet.microsoft.com/en-us/library/hh597113\(v=ax.60\))</span><span class="sxs-lookup"><span data-stu-id="fb441-178">[Disposition codes (form)](https://technet.microsoft.com/en-us/library/hh597113\(v=ax.60\))</span></span>

  



