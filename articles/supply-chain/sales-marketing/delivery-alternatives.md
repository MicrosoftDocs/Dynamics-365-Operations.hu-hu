---
title: Szállítási alternatívák
description: Az értékesítési rendelések a Szállítási alternatívák lap használatával tájékozódhatnak az alternatív rendelésteljesítési beállításokról.
author: ChristianRytt
manager: AnnBe
ms.date: 04/10/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesLineDeliveryDetails
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 271623
ms.assetid: 527f6084-44fe-41bb-924f-4386e926358a
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: crytt
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 1fbf8f08322c954a482777abcf041ff0b9d8fb77
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1555862"
---
# <a name="delivery-alternatives"></a><span data-ttu-id="88a5a-103">Szállítási alternatívák</span><span class="sxs-lookup"><span data-stu-id="88a5a-103">Delivery alternatives</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="88a5a-104">Az értékesítési rendelések felvevői a **Szállítási alternatívák** oldalt használhatják arra, hogy alternatív lehetőségeket keressenek a rendelés teljesítéséhez.</span><span class="sxs-lookup"><span data-stu-id="88a5a-104">Sales order takers can use the **Delivery alternatives** page to discover alternative order fulfillment options.</span></span>

<span data-ttu-id="88a5a-105">A **Szállítási alternatívák** oldal elrendezése lehetővé teszi az alternatív lehetőségek áttekintését.</span><span class="sxs-lookup"><span data-stu-id="88a5a-105">The **Delivery alternatives** page layout gives an overview of all alternative options.</span></span> <span data-ttu-id="88a5a-106">Ezenkívül lehetővé teszi a rendelés végrehajtói számára, hogy az aktuális vállalaton túl keressenek teljesítési lehetőségeket.</span><span class="sxs-lookup"><span data-stu-id="88a5a-106">It also lets order takers look beyond the current company for fulfillment opportunities.</span></span> <span data-ttu-id="88a5a-107">Megtekinthetik a vállalatközi lehetőségeket és a külső szállítók által biztosított lehetőségeket is.</span><span class="sxs-lookup"><span data-stu-id="88a5a-107">They can now view both intercompany opportunities and opportunities from external vendors.</span></span> <span data-ttu-id="88a5a-108">A beállítások szállítási dátum szerint történő rendezésével az értékesítési rendelés végrehajtói a szállítási alternatívák intelligens listáját tekinthetik meg.</span><span class="sxs-lookup"><span data-stu-id="88a5a-108">By sorting the options by delivery date, sales order takers can view an intelligent list of delivery alternatives.</span></span> <span data-ttu-id="88a5a-109">Ezenkívül a paraméterek segítségével jobban kezelhetik a javasolt szállításokat.</span><span class="sxs-lookup"><span data-stu-id="88a5a-109">In addition, parameters help them better manage the suggested deliveries.</span></span> <span data-ttu-id="88a5a-110">Mivel a szállítási idő hatással lehet a szállítási dátumokra, az értékesítési rendelés végrehajtói tallózhatnak a szállítmányozók által megadott különböző szállítási beállítások között.</span><span class="sxs-lookup"><span data-stu-id="88a5a-110">Because transport time can affect delivery dates, sales order takers can explore the various transportation choices that carriers offer.</span></span> <span data-ttu-id="88a5a-111">Mivel minden javaslat mellett részletes információk jelennek meg, a rendelés végrehajtói megalapozott döntést hozhatnak közvetlenül a **Szállítási alternatívák** lap alapján.</span><span class="sxs-lookup"><span data-stu-id="88a5a-111">Because detailed information is shown for each suggestion, order takers can make informed decisions directly from the **Delivery alternatives** page.</span></span>

## <a name="open-the-delivery-alternatives-page"></a><span data-ttu-id="88a5a-112">A Szállítási alternatívák lap megnyitása</span><span class="sxs-lookup"><span data-stu-id="88a5a-112">Open the Delivery alternatives page</span></span>
<span data-ttu-id="88a5a-113">Az értékesítési rendelés soráról megnyithatja a **Szállítási alternatívák** képernyőt.</span><span class="sxs-lookup"><span data-stu-id="88a5a-113">You can open the **Delivery alternatives** page from the sales order line.</span></span>

1.  <span data-ttu-id="88a5a-114">Kattintson a **Termékek és készlet** &gt; **Szállítási alternatívák** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="88a5a-114">Click **Products and supply** &gt; **Delivery alternatives**.</span></span>
2.  <span data-ttu-id="88a5a-115">Kattintson a **Sor adatai** &gt; **Szállítás** &gt; **Szállítási alternatívák** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="88a5a-115">Click **Line details** &gt; **Delivery** &gt; **Delivery alternatives.**</span></span>

<span data-ttu-id="88a5a-116">A **Szállítási alternatívák** lapot az **Értékesítési rendelés feldolgozása és lekérdezése** munkaterület megnyitásával is megnyithatja, ahol kattintson a **Rendelések és kedvencek** &gt; **Késleltetett rendeléssorok** &gt; **Szállítási alternatívák** lehetőségre **Megjegyzés:** a **Szállítási alternatívák** lapot csak akkor nyithatja meg ha teljesül mindkét következő feltétel:</span><span class="sxs-lookup"><span data-stu-id="88a5a-116">You can also open the **Delivery alternatives** page by opening the **Sales order processing and inquiry** workspace, and then clicking **Orders and favorites** &gt; **Delayed order lines** &gt; **Delivery alternatives** **Note:** You can open the **Delivery alternatives** page only if both the following conditions are met:</span></span>

-   <span data-ttu-id="88a5a-117">Minden kötelező értékesítési sor adata ki van töltve.</span><span class="sxs-lookup"><span data-stu-id="88a5a-117">All mandatory sales line information is filled in.</span></span>
-   <span data-ttu-id="88a5a-118">A **Szállítási dátum ellenőrzése** mező a **Nincs** értéktől eltérő értékre van állítva.</span><span class="sxs-lookup"><span data-stu-id="88a5a-118">The **Delivery date control** field is set to a value other than **None**.</span></span>

## <a name="delivery-date-control-methods"></a><span data-ttu-id="88a5a-119">Szállítási dátum ellenőrzési módszerei</span><span class="sxs-lookup"><span data-stu-id="88a5a-119">Delivery date control methods</span></span>
<span data-ttu-id="88a5a-120">A szállítási dátum ellenőrzési módszere határozza meg, a szállítási dátumok rendszer általi létrehozásának módját, a szállítási alternatívák kiszámításának a módját, valamint a megjelenő információkat.</span><span class="sxs-lookup"><span data-stu-id="88a5a-120">The delivery date control method determines how the system establishes delivery dates, how delivery alternatives are calculated, and what information is shown.</span></span> <span data-ttu-id="88a5a-121">Vegye figyelembe, hogy a szállítási dátum ellenőrzése naptárakat vesz figyelembe.</span><span class="sxs-lookup"><span data-stu-id="88a5a-121">Note that delivery data control takes calendars into consideration.</span></span> <span data-ttu-id="88a5a-122">Emiatt a következő naptárak hatással lehetnek a javasolt bevételezési dátumra: a raktárhoz rendelt naptár, a szállítási naptár, a szállítóhoz rendelt naptár és a vevőhöz rendelt naptár.</span><span class="sxs-lookup"><span data-stu-id="88a5a-122">Therefore, the following calendars can affect the suggested receipt date: Warehouse calendar, Transport calendar, Vendor calendar, and Customer calendar.</span></span> <span data-ttu-id="88a5a-123">A következő táblázat leírja a szállítási dátum ellenőrzésének egyes módszereit.</span><span class="sxs-lookup"><span data-stu-id="88a5a-123">The following table describes each method for delivery date control.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><span data-ttu-id="88a5a-124"><strong>Metódus</strong></span><span class="sxs-lookup"><span data-stu-id="88a5a-124"><strong>Method</strong></span></span></td>
<td><span data-ttu-id="88a5a-125"><strong>Leírás</strong></span><span class="sxs-lookup"><span data-stu-id="88a5a-125"><strong>Description</strong></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="88a5a-126"><strong>Egyik sem</strong></span><span class="sxs-lookup"><span data-stu-id="88a5a-126"><strong>None</strong></span></span></td>
<td><ul>
<li><span data-ttu-id="88a5a-127">Az értékesítési sorok szállítási alternatívái nem támogatottak.</span><span class="sxs-lookup"><span data-stu-id="88a5a-127">Delivery alternatives for sales lines aren&#39;t supported.</span></span> <span data-ttu-id="88a5a-128">Ez a beállítás kikapcsolja a szállítási adatok ellenőrzését.</span><span class="sxs-lookup"><span data-stu-id="88a5a-128">This option turns off delivery data control.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="88a5a-129"><strong>Értékesítés átfutási ideje</strong></span><span class="sxs-lookup"><span data-stu-id="88a5a-129"><strong>Sales lead time</strong></span></span></td>
<td><ul>
<li><span data-ttu-id="88a5a-130">A szállítási alternatívák kiszámítása az előre meghatározott értékesítési átfutási időn alapul.</span><span class="sxs-lookup"><span data-stu-id="88a5a-130">Delivery alternatives are calculated based on the predefined sales lead time.</span></span> <span data-ttu-id="88a5a-131">A szállítási napok kiszámítása a szállítási módon alapul.</span><span class="sxs-lookup"><span data-stu-id="88a5a-131">The transport days are calculated based on the mode of delivery.</span></span></li>
<li><span data-ttu-id="88a5a-132">A szállítási alternatívák tartalmazzák az aktuális készlettel rendelkező raktárak és a készlet- és igényrendelések kínálatát.</span><span class="sxs-lookup"><span data-stu-id="88a5a-132">Delivery alternatives include warehouses that have on-hand inventory, and supply/demand orders.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="88a5a-133"><strong>Ígérethez rendelkezésre áll</strong></span><span class="sxs-lookup"><span data-stu-id="88a5a-133"><strong>ATP</strong></span></span></td>
<td><ul>
<li><span data-ttu-id="88a5a-134">A szállítási alternatívák kiszámítása az ígérethez rendelkezésre álló logikán alapul.</span><span class="sxs-lookup"><span data-stu-id="88a5a-134">Delivery alternatives are calculated based on available to promise (ATP) logic.</span></span> <span data-ttu-id="88a5a-135">A rendszer a jelenlegi elérhetőséget és a várható jövőbeli elérhetőséget veszi figyelembe.</span><span class="sxs-lookup"><span data-stu-id="88a5a-135">The current availability and expected future availability are considered.</span></span> <span data-ttu-id="88a5a-136">A szállítási napok kiszámítása a szállítási módon alapul.</span><span class="sxs-lookup"><span data-stu-id="88a5a-136">The transport days are calculated based on the mode of delivery.</span></span></li>
<li><span data-ttu-id="88a5a-137">A szállítási alternatívák tartalmazzák az aktuális készlettel rendelkező raktárak és a készlet- és igényrendelések kínálatát.</span><span class="sxs-lookup"><span data-stu-id="88a5a-137">Delivery alternatives include warehouses that have on-hand inventory, and supply/demand orders.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="88a5a-138"><strong>Ígérethez rendelkezésre áll + kiadási időtartalék</strong></span><span class="sxs-lookup"><span data-stu-id="88a5a-138"><strong>ATP + Issue margin</strong></span></span></td>
<td><ul>
<li><span data-ttu-id="88a5a-139">A szállítási alternatívákat az ígérethez rendelkezésre állás metódus alapján számítja ki a rendszer, de a számításba belefoglalja a kiadási időtartalékot is.</span><span class="sxs-lookup"><span data-stu-id="88a5a-139">Delivery alternatives are calculated as for the ATP method, but the issue margin is included in the calculation.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="88a5a-140"><strong>Ígérhető (CTP)</strong></span><span class="sxs-lookup"><span data-stu-id="88a5a-140"><strong>CTP</strong></span></span></td>
<td><ul>
<li><span data-ttu-id="88a5a-141">A szállítási alternatívák kiszámítása az ígérhető logikán alapul.</span><span class="sxs-lookup"><span data-stu-id="88a5a-141">Delivery alternatives are calculated based on the capable to promise (CTP) logic.</span></span> <span data-ttu-id="88a5a-142">Az MRP-alábontás az elérhetőség meghatározására szolgál.</span><span class="sxs-lookup"><span data-stu-id="88a5a-142">MRP explosion is used to determine availability.</span></span> <span data-ttu-id="88a5a-143">Vegye figyelembe, az ígérhető minimálisan eltolja a szállítási dátumokat az értékesítés átfutási idejéhez.</span><span class="sxs-lookup"><span data-stu-id="88a5a-143">Note that, at a minimum, CTP offsets delivery dates to the sales lead time.</span></span> <span data-ttu-id="88a5a-144">A szállítási napok kiszámítása a szállítási módon alapul.</span><span class="sxs-lookup"><span data-stu-id="88a5a-144">The transport days are calculated based on the mode of delivery.</span></span></li>
<li><span data-ttu-id="88a5a-145">A szállítási alternatívák a következő raktárakra vonatkozó javaslatokat tartalmazzák:</span><span class="sxs-lookup"><span data-stu-id="88a5a-145">Delivery alternatives include suggestions for the following warehouses:</span></span>
<ul>
<li><span data-ttu-id="88a5a-146">Aktuális raktár</span><span class="sxs-lookup"><span data-stu-id="88a5a-146">Current warehouse</span></span></li>
<li><span data-ttu-id="88a5a-147">Alapértelmezett raktár</span><span class="sxs-lookup"><span data-stu-id="88a5a-147">Default warehouse</span></span></li>
<li><span data-ttu-id="88a5a-148">Rendelkezésre álló aktuális készlettel rendelkező raktárak</span><span class="sxs-lookup"><span data-stu-id="88a5a-148">All warehouses that have available on-hand inventory</span></span></li>
<li><span data-ttu-id="88a5a-149">Ellátási rendelésekkel rendelkező raktárak</span><span class="sxs-lookup"><span data-stu-id="88a5a-149">All warehouses that have supply orders</span></span></li>
<li><span data-ttu-id="88a5a-150">Aktív anyagjegyzék-verziókkal rendelkező raktárak</span><span class="sxs-lookup"><span data-stu-id="88a5a-150">All warehouses that have active bill of materials (BOM) versions</span></span></li>
</ul></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="view-information-about-delivery-alternatives"></a><span data-ttu-id="88a5a-151">Szállítási alternatívák adatainak megtekintése</span><span class="sxs-lookup"><span data-stu-id="88a5a-151">View information about delivery alternatives</span></span>
<span data-ttu-id="88a5a-152">Ez a szakasz bemutatja a szállítási alternatívák adatait, amelyeket a **Szállítási alternatívák** lap egyes lapjain érhetők el.</span><span class="sxs-lookup"><span data-stu-id="88a5a-152">This section describes the information about delivery alternatives that is available on each tab of the **Delivery alternatives** page.</span></span>

### <a name="products"></a><span data-ttu-id="88a5a-153">Termékek</span><span class="sxs-lookup"><span data-stu-id="88a5a-153">Products</span></span>

<span data-ttu-id="88a5a-154">Ez a lap megjeleníti a termék összegzését és az aktuális értékesítési sor részletes adatait.</span><span class="sxs-lookup"><span data-stu-id="88a5a-154">This tab shows a summary of the product and details of the current sales line.</span></span>

### <a name="delivery-alternatives"></a><span data-ttu-id="88a5a-155">Szállítási alternatívák</span><span class="sxs-lookup"><span data-stu-id="88a5a-155">Delivery alternatives</span></span>

<span data-ttu-id="88a5a-156">Ez a lap a termékbevételezési adatok szerint rendezett szállítási alternatívák listáját jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="88a5a-156">This tab shows a list of delivery alternatives that is sorted by receipt data.</span></span> <span data-ttu-id="88a5a-157">A lista fölött kiválaszthatja a javaslat alapját képező lehetőségeket.</span><span class="sxs-lookup"><span data-stu-id="88a5a-157">Above the list, you can select which options to base the suggestions on.</span></span> <span data-ttu-id="88a5a-158">Kiválaszthatja a szállítási módot is, amely meghatározza a szállítási napokat is.</span><span class="sxs-lookup"><span data-stu-id="88a5a-158">You can also select the mode of delivery, which determines the transport days.</span></span> <span data-ttu-id="88a5a-159">Az alábbi lehetőségek közül választhat:</span><span class="sxs-lookup"><span data-stu-id="88a5a-159">The following options are available:</span></span>

-   <span data-ttu-id="88a5a-160">**Egyéb termékváltozatok belefoglalása** – Ez a lehetőség a termékváltozatokkal rendelkező termékek esetében érhető el.</span><span class="sxs-lookup"><span data-stu-id="88a5a-160">**Include other product variants** - This option is available for products that have product variants.</span></span> <span data-ttu-id="88a5a-161">Ez magában foglalja a termék többi változatának szállítási módszereit.</span><span class="sxs-lookup"><span data-stu-id="88a5a-161">It will include delivery alternatives for other variants of the product.</span></span> <span data-ttu-id="88a5a-162">Ez a beállítás nem érhető el az ígérhető verzió esetében.</span><span class="sxs-lookup"><span data-stu-id="88a5a-162">This option isn't available for CTP.</span></span>
-   <span data-ttu-id="88a5a-163">**Részleges mennyiség szerepeltetése** – Alapértelmezés szerint itt csak azok a javaslatok szerepelnek, amelyek megfelelnek az értékesítési sor teljes mennyiségének.</span><span class="sxs-lookup"><span data-stu-id="88a5a-163">**Include partial quantity** - By default, only suggestions that fulfill the full quantity of the sales line are included.</span></span> <span data-ttu-id="88a5a-164">Válassza ezt a lehetőséget az olyan javaslatok szerepeltetéséhez, amelyek csak részben felelnek meg a rendeléssornak.</span><span class="sxs-lookup"><span data-stu-id="88a5a-164">Select this option to include suggestions that only partially fulfill the order line.</span></span> <span data-ttu-id="88a5a-165">Ez akkor hasznos, amikor a vevő korábbi szállítási dátumot kér, és elfogadja a részleges szállítást.</span><span class="sxs-lookup"><span data-stu-id="88a5a-165">This option is useful when the customer requests an earlier delivery date and accepts partial delivery.</span></span>
-   <span data-ttu-id="88a5a-166">**Későbbi dátumok belefoglalása** – Alapértelmezett módon itt csak azon javaslatok jelennek meg, amelyek jobbak (korábbiak) az értékesítési sorban levő aktuális dátumnál.</span><span class="sxs-lookup"><span data-stu-id="88a5a-166">**Include later dates** - By default, only suggestions that are better (earlier) than the current dates on the sales line are shown.</span></span> <span data-ttu-id="88a5a-167">A későbbi dátumok belefoglalásához válassza ezt a lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="88a5a-167">Select this option to include later dates.</span></span> <span data-ttu-id="88a5a-168">Ez a beállítás olyankor lehet hasznos, ahol a dátumtól eltérő paraméterek élveznek prioritást.</span><span class="sxs-lookup"><span data-stu-id="88a5a-168">This option can be useful in situations where parameters other than the date have priority.</span></span> <span data-ttu-id="88a5a-169">Például ha egy adott szállítót vagy raktárt részesítene előnyben.</span><span class="sxs-lookup"><span data-stu-id="88a5a-169">For example, a specific vendor or warehouse might be preferred.</span></span>
-   <span data-ttu-id="88a5a-170">**Szállítás módja** – Válassza ki az előnyben részesített szállítási módot a szállítási idő és költség optimalizálása érdekében.</span><span class="sxs-lookup"><span data-stu-id="88a5a-170">**Mode of delivery** - Select the preferred mode of delivery to optimize transport time and cost.</span></span> <span data-ttu-id="88a5a-171">Azonnal láthatja a javasolt szállítási alternatívákra gyakorolt hatást.</span><span class="sxs-lookup"><span data-stu-id="88a5a-171">You will immediately see the effect on the suggested delivery alternatives.</span></span> <span data-ttu-id="88a5a-172">Ezért az alternatívák összevetése egyszerű.</span><span class="sxs-lookup"><span data-stu-id="88a5a-172">Therefore, it's easy to compare the alternatives.</span></span>
-   <span data-ttu-id="88a5a-173">**Beszerzéssel együtt** – Ha a beszerzés be van jelölve, a javasolt szállítási alternatívák tartalmazzák mind a külső szállítóktól, mind a vállalaton belüli (vállalatközi) más vállalatoktól történő beszerzési lehetőségeket.</span><span class="sxs-lookup"><span data-stu-id="88a5a-173">**Include procurement** - When procurement is selected, the suggested delivery alternatives include options to procure from both external vendors and other companies in the enterprise (intercompany).</span></span> <span data-ttu-id="88a5a-174">A **Beszerzéssel együtt** lehetőséget az ígérethez rendelkezésre áll és az ígérethez rendelkezésre áll+ kiadási időtartalék szállításidátum-ellenőrzés is támogatja.</span><span class="sxs-lookup"><span data-stu-id="88a5a-174">The **Include procurement** option is supported for ATP and ATP + Issue margin delivery date control.</span></span> <span data-ttu-id="88a5a-175">Ebben szerepelnek a termék alapértelmezett beszerzési szállítójának beszerzési beállításai és a termék összes engedélyezett szállítója.</span><span class="sxs-lookup"><span data-stu-id="88a5a-175">Procurement options from the default purchase vendor for the product and all approved vendors for the product are included.</span></span>
-   <span data-ttu-id="88a5a-176">Külső szállítók esetén a kiszámítás alapját a beszerzés átfutási ideje képezi.</span><span class="sxs-lookup"><span data-stu-id="88a5a-176">For external vendors, the calculation is based on the purchase lead time.</span></span>
-   <span data-ttu-id="88a5a-177">Vállalatközi szállítók esetén a számítás a forrásvállalatnál végzett szállításidátum-ellenőrzés alapján megvizsgálja, hogy mi érhető el a forrásvállalatnál.</span><span class="sxs-lookup"><span data-stu-id="88a5a-177">For intercompany, the calculation considers what is available from the sourcing company, based on delivery date control in the sourcing company.</span></span>
-   <span data-ttu-id="88a5a-178">**Szállítás típusa** (A beszerzés szempontjából releváns)</span><span class="sxs-lookup"><span data-stu-id="88a5a-178">**Delivery type** (Relevant for procurement)</span></span>
    -   <span data-ttu-id="88a5a-179">**Készlet** – A termékeket a forrásraktárból az értékesítési soron az adott helyre/raktárba szállítják.</span><span class="sxs-lookup"><span data-stu-id="88a5a-179">**Stock** - Products are shipped from the sourcing warehouse to the site/warehouse on the sales line.</span></span> <span data-ttu-id="88a5a-180">Ezután a termékeket kiszállítják az adott raktárból a vevőnek.</span><span class="sxs-lookup"><span data-stu-id="88a5a-180">They are then shipped from that warehouse to the customer.</span></span>
    -   <span data-ttu-id="88a5a-181">**Közvetlen kiszállítás** – A termékeket a forrásraktárból közvetlenül a vevőnek szállítják ki.</span><span class="sxs-lookup"><span data-stu-id="88a5a-181">**Direct delivery** - Products are shipped directly from the sourcing warehouse to the customer.</span></span>

### <a name="availability-information"></a><span data-ttu-id="88a5a-182">Elérhetőségi információ</span><span class="sxs-lookup"><span data-stu-id="88a5a-182">Availability information</span></span>

<span data-ttu-id="88a5a-183">Az ezen a lapon található adatok a kijelölt alternatív kézbesítési sorhoz kapcsolódnak.</span><span class="sxs-lookup"><span data-stu-id="88a5a-183">Information on this tab is related to the delivery alternative line that is selected.</span></span> <span data-ttu-id="88a5a-184">A következő információk jelennek meg az értékesítési sor szállításidátum-ellenőrzésétől függően:</span><span class="sxs-lookup"><span data-stu-id="88a5a-184">The following information is shown, depending on the delivery date control for the sales line:</span></span>

-   <span data-ttu-id="88a5a-185">**Értékesítés átfutási ideje**</span><span class="sxs-lookup"><span data-stu-id="88a5a-185">**Sales lead time**</span></span>
    -   <span data-ttu-id="88a5a-186">**Elérhető ma** – A tényleges aktuális, a ténylegesen lefoglalt és a rendelkezésre álló tényleges készletet jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="88a5a-186">**Available today** - Show the current physical on-hand, physical reserved, and available physical inventory.</span></span>
    -   <span data-ttu-id="88a5a-187">**Paraméterek** – A készletegység és az értékesítés átfutási idejét jelenítik meg.</span><span class="sxs-lookup"><span data-stu-id="88a5a-187">**Parameters** - Show the inventory unit and sales lead time.</span></span>

-   <span data-ttu-id="88a5a-188">**Ígérethez rendelkezésre áll és ígérethez rendelkezésre áll + kiadási időtartalék**</span><span class="sxs-lookup"><span data-stu-id="88a5a-188">**ATP and ATP + Issue margin**</span></span>
    -   <span data-ttu-id="88a5a-189">**Elérhető ma** – A tényleges aktuális, a ténylegesen lefoglalt és a rendelkezésre álló tényleges készletet jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="88a5a-189">**Available today** - Show the current physical on-hand, physical reserved, and available physical inventory.</span></span>
    -   <span data-ttu-id="88a5a-190">**Paraméterek** – A készletegység és az értékesítés átfutási idejét jelenítik meg.</span><span class="sxs-lookup"><span data-stu-id="88a5a-190">**Parameters** - Show the inventory unit and sales lead time.</span></span>
    -   <span data-ttu-id="88a5a-191">**Jövőbeli elérhetőség** – A kiválasztott hely és raktár jelenlegi és jövőbeli elérhetőségének grafikus ábrázolását jeleníti meg a **Szállítási alternatívák** lapon.</span><span class="sxs-lookup"><span data-stu-id="88a5a-191">**Future availability** - Show a graphical representation of current and future availability for the selected site and warehouse under **Delivery alternatives**.</span></span> <span data-ttu-id="88a5a-192">A diagram oszlopaira kattintva részletesebb információkat tek‌inthet meg a termék jövőbeli elérhetőségéről.</span><span class="sxs-lookup"><span data-stu-id="88a5a-192">You can click the chart columns to see more detailed information about the future availability of the product.</span></span> <span data-ttu-id="88a5a-193">A csúszka az ígérethez rendelkezésre álló időkorláton belüli feltételnek megfelelő igény- és ellátási rendelések listáját jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="88a5a-193">The slider shows a list of relevant demand and supply orders within the ATP time fence.</span></span>

-   <span data-ttu-id="88a5a-194">**Ígérhető**</span><span class="sxs-lookup"><span data-stu-id="88a5a-194">**CTP**</span></span>
    -   <span data-ttu-id="88a5a-195">**Elérhető ma** – A tényleges aktuális, a ténylegesen lefoglalt és a rendelkezésre álló tényleges készletet jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="88a5a-195">**Available today** - Show the current physical on-hand, physical reserved, and available physical inventory.</span></span>
    -   <span data-ttu-id="88a5a-196">**Paraméterek** – A készletegység és az értékesítés átfutási idejét jelenítik meg.</span><span class="sxs-lookup"><span data-stu-id="88a5a-196">**Parameters** - Show the inventory unit and sales lead time.</span></span>
    -   <span data-ttu-id="88a5a-197">**Alábontás** – Megjeleníti a kiválasztott szállítási alternatíva készlet alábontását.</span><span class="sxs-lookup"><span data-stu-id="88a5a-197">**Explosion** - Show a supply explosion of the selected delivery alternative.</span></span> <span data-ttu-id="88a5a-198">A **Beállítás** pontban módosíthatja az alábontásban megjelenített mezőket és készletdimenziókat.</span><span class="sxs-lookup"><span data-stu-id="88a5a-198">You can use **Setup** to change the fields and inventory dimensions that are shown in the explosion.</span></span>

### <a name="impact-of-selected-alternative"></a><span data-ttu-id="88a5a-199">Kiválasztott alternatív kézbesítés hatása</span><span class="sxs-lookup"><span data-stu-id="88a5a-199">Impact of selected alternative</span></span>

<span data-ttu-id="88a5a-200">Ez a lap kiemeli a kiválasztott szállítási alternatíva hatását.</span><span class="sxs-lookup"><span data-stu-id="88a5a-200">This tab highlights the impact of the selected delivery alternative.</span></span> <span data-ttu-id="88a5a-201">Ha az **OK** gombra kattint, az értékesítési sor a KIJELÖLT oszlopokban a kijelölt értékekkel frissül.</span><span class="sxs-lookup"><span data-stu-id="88a5a-201">If you click **OK**, the sales line is updated with the highlighted values in the SELECTED columns.</span></span> <span data-ttu-id="88a5a-202">Vegye figyelembe, hogy ha a kiválasztott szállítási alternatíva mennyisége kisebb, mint az értékesítési sorban szereplő mennyiség, szállítási ütemezés jön létre, és a rendelési sor két sorra oszlik: egy sor a kiválasztott mennyiséget, a másik pedig a fennmaradó mennyiséget jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="88a5a-202">Note that, if the quantity on the selected delivery alternative is less than quantity on the sales line, a delivery schedule is created, and the order line is split into two lines: one line for the selected quantity and one line for the remaining quantity.</span></span> <span data-ttu-id="88a5a-203">Frissítheti a kereskedelmi sort is, hogy az megfeleljen az ütemezési soroknak, és befolyásolja az árképzést.</span><span class="sxs-lookup"><span data-stu-id="88a5a-203">You can also update the commercial line so that it matches the schedule lines and affects the pricing.</span></span>

<a name="additional-resources"></a><span data-ttu-id="88a5a-204">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="88a5a-204">Additional resources</span></span>
--------

[<span data-ttu-id="88a5a-205">Rendelési ígéretek</span><span class="sxs-lookup"><span data-stu-id="88a5a-205">Order promising</span></span>](delivery-dates-available-promise-calculations.md)




