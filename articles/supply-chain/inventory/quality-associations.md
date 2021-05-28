---
title: Minőségi társítások
description: Ez a témakör azt mutatja be, hogyan használhatók a Microsoft Dynamics 365 Supply Chain Management minőségi társításai az értékesítési, beszerzési és termelési folyamatokkal kapcsolatos minőségi rendelések automatikus létrehozása során.
author: rachel-profitt
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestAssociationTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2020-06-18
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6c6fab1b89b7e58d9e443c27da03a6b13afcc9c6
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/11/2021
ms.locfileid: "6022324"
---
# <a name="quality-associations"></a><span data-ttu-id="815c0-103">Minőségi társítások</span><span class="sxs-lookup"><span data-stu-id="815c0-103">Quality associations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="815c0-104">Ez a témakör azt mutatja be, hogyan használhatók a Microsoft Dynamics 365 Supply Chain Management minőségi társításai az értékesítési, beszerzési és termelési folyamatokkal kapcsolatos minőségi rendelések automatikus létrehozása során.</span><span class="sxs-lookup"><span data-stu-id="815c0-104">This topic describes how you can use quality associations in Microsoft Dynamics 365 Supply Chain Management to automatically generate quality orders that are related to your sales, purchase, and production processes.</span></span>

<span data-ttu-id="815c0-105">A minőségi társítás meghatározza a létrehozott minőségi rendelésre vonatkozó alábbi adatok mindegyikét:</span><span class="sxs-lookup"><span data-stu-id="815c0-105">A quality association defines all the following information for a quality order that is generated:</span></span>

- <span data-ttu-id="815c0-106">Tranzakcióesemény</span><span class="sxs-lookup"><span data-stu-id="815c0-106">The transaction event</span></span>
- <span data-ttu-id="815c0-107">A cikkeken elvégzendő tesztek</span><span class="sxs-lookup"><span data-stu-id="815c0-107">The set of tests that must be performed on the items</span></span>
- <span data-ttu-id="815c0-108">Az elfogadható minőségi szint (AQL)</span><span class="sxs-lookup"><span data-stu-id="815c0-108">The acceptable quality level (AQL)</span></span>
- <span data-ttu-id="815c0-109">Mintavételi terv</span><span class="sxs-lookup"><span data-stu-id="815c0-109">The sampling plan</span></span>

<span data-ttu-id="815c0-110">Definiálnia kell egy minőségi társítást az üzleti folyamat minden olyan változatához, ahol minőségi rendelés automatikus létrehozása szükséges.</span><span class="sxs-lookup"><span data-stu-id="815c0-110">You must define a quality association for each variation in a business process that requires automatic generation of quality orders.</span></span> <span data-ttu-id="815c0-111">Minőségi rendelés létrehozható például az üzleti folyamatokban beszerzési rendelésekhez, karanténutasításokhoz, értékesítési rendelésekhez és termelési rendelésekhez.</span><span class="sxs-lookup"><span data-stu-id="815c0-111">For example, a quality order can be generated in the business processes for purchase orders, quarantine orders, sales orders, and production orders.</span></span>

## <a name="working-with-quality-associations"></a><span data-ttu-id="815c0-112">Minőségi társítások használata</span><span class="sxs-lookup"><span data-stu-id="815c0-112">Working with quality associations</span></span>

<span data-ttu-id="815c0-113">Egy minőségi társítást használó üzleti folyamat különféle forrásbizonylatokkal lehet kapcsolatban (például beszerzési rendelésekkel, értékesítési rendelésekkel, vagy termelési rendelésekkel).</span><span class="sxs-lookup"><span data-stu-id="815c0-113">The business process that uses a quality association can be related to various source documents, such as purchase orders, sales orders, or production orders.</span></span>

<span data-ttu-id="815c0-114">Minden egyes minőségi társítási rekord meghatározza a létrehozott minőségi rendelésekre vonatkozó teszteket, elfogadható minőségi szintet és mintavételi eljárást.</span><span class="sxs-lookup"><span data-stu-id="815c0-114">Each quality association record defines the set of tests, the AQL, and the sampling plan that applies to the quality orders that are generated.</span></span> <span data-ttu-id="815c0-115">Az üzleti folyamat minden egyes változatára definiálnia kell egy minőségi társítási rekordot.</span><span class="sxs-lookup"><span data-stu-id="815c0-115">You must define a quality association record for each variation in a business process.</span></span> <span data-ttu-id="815c0-116">Például beállíthat egy olyan minőségi társítást, amely egy beszerzési rendelés termékbevételezésének frissítésekor létrehoz egy minőségi rendelést.</span><span class="sxs-lookup"><span data-stu-id="815c0-116">For example, you can set up a quality association that generates a quality order when a purchase order product receipt is updated.</span></span> <span data-ttu-id="815c0-117">A végrehajtási terv beállításaitól függően maga az aktiváló folyamat blokkolható nyitott minőségi rendelés közben.</span><span class="sxs-lookup"><span data-stu-id="815c0-117">Depending on the setup of the execution plan, the triggering process itself can be blocked while there is an open quality order.</span></span> <span data-ttu-id="815c0-118">A további folyamatok, például a beszerzési rendelés számlázása is blokkolható.</span><span class="sxs-lookup"><span data-stu-id="815c0-118">Alternatively, subsequent processes, such as purchase order invoicing, can be blocked.</span></span>

> [!NOTE]
> <span data-ttu-id="815c0-119">Amíg vannak nyitott minőségi rendelések, a készletmennyiségek kiadása automatikusan le van tiltva.</span><span class="sxs-lookup"><span data-stu-id="815c0-119">While there are open quality orders, inventory quantities are automatically blocked from being issued.</span></span> <span data-ttu-id="815c0-120">A **Cikkmintavételek** lap **Teljes zárolás** mező beállításától függően a mennyiség a minőségi rendelésen vagy a forrásbizonylat sorában szereplő mennyiség lehet.</span><span class="sxs-lookup"><span data-stu-id="815c0-120">Depending on the setting of the **Full blocking** field on the **Item samplings** page, the quantity is either the quantity on the quality order or the quantity on the source document line.</span></span> <span data-ttu-id="815c0-121">További információért lásd: [Minőségkezelési cikk mintavételezése](quality-item-sampling.md).</span><span class="sxs-lookup"><span data-stu-id="815c0-121">For more information, see [Quality management item sampling](quality-item-sampling.md).</span></span>

<span data-ttu-id="815c0-122">Egy adott üzleti folyamatra a minőségi társítási rekord azonosítja azokat az eseményeket és feltételeket, amelyek fennállása esetén a minőségi rendelés létrejön.</span><span class="sxs-lookup"><span data-stu-id="815c0-122">For a given business process, the quality association record identifies the event and conditions that a quality order is generated for.</span></span> <span data-ttu-id="815c0-123">A feltételek helyre vagy jogi személyre vonatkozhatnak.</span><span class="sxs-lookup"><span data-stu-id="815c0-123">The conditions can be specific to either a site or a legal entity.</span></span> <span data-ttu-id="815c0-124">Romboló teszteket igénylő minőségi rendelés csak akkor generálható, ha az eseményhez létezik aktuális készlet.</span><span class="sxs-lookup"><span data-stu-id="815c0-124">A quality order that involves destructive tests can be generated only when on-hand inventory exists for the event.</span></span>

<span data-ttu-id="815c0-125">A minőségi társítások használatához kattintson a **Készletkezelés \> Beállítás \> Minőségellenőrzés \> Minőségi társítások** gombra.</span><span class="sxs-lookup"><span data-stu-id="815c0-125">To work with quality associations, go to **Inventory management \> Setup \> Quality control \> Quality associations**.</span></span> <span data-ttu-id="815c0-126">A következő példák bemutatják egy minőségi társítási rekord meghatározását az egyes üzleti folyamatok változásainak megfelelően.</span><span class="sxs-lookup"><span data-stu-id="815c0-126">The following examples show how a quality association record is defined for the variations in each business process.</span></span> <span data-ttu-id="815c0-127">Egy minőségi társítási rekord által az egyes példák esetén meghatározott eseményeket és feltételeket az alábbi táblázat összegzi.</span><span class="sxs-lookup"><span data-stu-id="815c0-127">For each example, the following table summarizes the events and conditions that are defined by a quality association record.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="815c0-128">Hivatkozás típusa</span><span class="sxs-lookup"><span data-stu-id="815c0-128">Reference type</span></span></th>
<th><span data-ttu-id="815c0-129">Eseménytípus</span><span class="sxs-lookup"><span data-stu-id="815c0-129">Event type</span></span></th>
<th><span data-ttu-id="815c0-130">Végrehajtás</span><span class="sxs-lookup"><span data-stu-id="815c0-130">Execution</span></span></th>
<th><span data-ttu-id="815c0-131">Eseményzárolás</span><span class="sxs-lookup"><span data-stu-id="815c0-131">Event blocking</span></span></th>
<th><span data-ttu-id="815c0-132">Dokumentumhivatkozás</span><span class="sxs-lookup"><span data-stu-id="815c0-132">Document reference</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="815c0-133">Készlet</span><span class="sxs-lookup"><span data-stu-id="815c0-133">Inventory</span></span></td>
<td><span data-ttu-id="815c0-134">Nem alkalmazható</span><span class="sxs-lookup"><span data-stu-id="815c0-134">Not applicable</span></span></td>
<td><span data-ttu-id="815c0-135">Nem alkalmazható</span><span class="sxs-lookup"><span data-stu-id="815c0-135">Not applicable</span></span></td>
<td><span data-ttu-id="815c0-136">Egyik sem</span><span class="sxs-lookup"><span data-stu-id="815c0-136">None</span></span></td>
<td><span data-ttu-id="815c0-137">Mind</span><span class="sxs-lookup"><span data-stu-id="815c0-137">All</span></span></td>
</tr>
<tr>
<td rowspan="7"><span data-ttu-id="815c0-138">Értékesítés</span><span class="sxs-lookup"><span data-stu-id="815c0-138">Sales</span></span></td>
<td rowspan="4"><span data-ttu-id="815c0-139">Kitárolási folyamat ütemezve</span><span class="sxs-lookup"><span data-stu-id="815c0-139">Picking process is scheduled</span></span></td>
<td rowspan="4"><span data-ttu-id="815c0-140">Előtte</span><span class="sxs-lookup"><span data-stu-id="815c0-140">Before</span></span></td>
<td><span data-ttu-id="815c0-141">Egyik sem</span><span class="sxs-lookup"><span data-stu-id="815c0-141">None</span></span></td>
<td rowspan="22"><span data-ttu-id="815c0-142">Csak Egyedi azonosító, Csoport vagy Mind</span><span class="sxs-lookup"><span data-stu-id="815c0-142">Specific ID, Group, or All only</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="815c0-143">Kitárolási folyamat</span><span class="sxs-lookup"><span data-stu-id="815c0-143">Picking process</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="815c0-144">Szállítólevél</span><span class="sxs-lookup"><span data-stu-id="815c0-144">Packing slip</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="815c0-145">Számla</span><span class="sxs-lookup"><span data-stu-id="815c0-145">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="815c0-146">Szállítólevél</span><span class="sxs-lookup"><span data-stu-id="815c0-146">Packing slip</span></span></td>
<td rowspan="3"><span data-ttu-id="815c0-147">Előtte</span><span class="sxs-lookup"><span data-stu-id="815c0-147">Before</span></span></td>
<td><span data-ttu-id="815c0-148">Egyik sem</span><span class="sxs-lookup"><span data-stu-id="815c0-148">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="815c0-149">Szállítólevél</span><span class="sxs-lookup"><span data-stu-id="815c0-149">Packing slip</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="815c0-150">Számla</span><span class="sxs-lookup"><span data-stu-id="815c0-150">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="15"><span data-ttu-id="815c0-151">Beszerzés</span><span class="sxs-lookup"><span data-stu-id="815c0-151">Purchase</span></span></td>
<td rowspan="7"><span data-ttu-id="815c0-152">Bevételezési lista</span><span class="sxs-lookup"><span data-stu-id="815c0-152">Receipt list</span></span></td>
<td rowspan="4"><span data-ttu-id="815c0-153">Előtte</span><span class="sxs-lookup"><span data-stu-id="815c0-153">Before</span></span></td>
<td><span data-ttu-id="815c0-154">Egyik sem</span><span class="sxs-lookup"><span data-stu-id="815c0-154">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="815c0-155">Bevételezési lista</span><span class="sxs-lookup"><span data-stu-id="815c0-155">Receipt list</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="815c0-156">Termékbevételezés</span><span class="sxs-lookup"><span data-stu-id="815c0-156">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="815c0-157">Számla</span><span class="sxs-lookup"><span data-stu-id="815c0-157">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="815c0-158">Utána</span><span class="sxs-lookup"><span data-stu-id="815c0-158">After</span></span></td>
<td><span data-ttu-id="815c0-159">Egyik sem</span><span class="sxs-lookup"><span data-stu-id="815c0-159">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="815c0-160">Termékbevételezés</span><span class="sxs-lookup"><span data-stu-id="815c0-160">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="815c0-161">Számla</span><span class="sxs-lookup"><span data-stu-id="815c0-161">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="815c0-162">Nyilvántartás</span><span class="sxs-lookup"><span data-stu-id="815c0-162">Registration</span></span></td>
<td rowspan="3"><span data-ttu-id="815c0-163">Nem alkalmazható</span><span class="sxs-lookup"><span data-stu-id="815c0-163">Not applicable</span></span></td>
<td><span data-ttu-id="815c0-164">Egyik sem</span><span class="sxs-lookup"><span data-stu-id="815c0-164">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="815c0-165">Termékbevételezés</span><span class="sxs-lookup"><span data-stu-id="815c0-165">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="815c0-166">Számla</span><span class="sxs-lookup"><span data-stu-id="815c0-166">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="5"><span data-ttu-id="815c0-167">Termékbevételezés</span><span class="sxs-lookup"><span data-stu-id="815c0-167">Product receipt</span></span></td>
<td rowspan="3"><span data-ttu-id="815c0-168">Előtte</span><span class="sxs-lookup"><span data-stu-id="815c0-168">Before</span></span></td>
<td><span data-ttu-id="815c0-169">Egyik sem</span><span class="sxs-lookup"><span data-stu-id="815c0-169">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="815c0-170">Termékbevételezés</span><span class="sxs-lookup"><span data-stu-id="815c0-170">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="815c0-171">Számla</span><span class="sxs-lookup"><span data-stu-id="815c0-171">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="2"><span data-ttu-id="815c0-172">Utána</span><span class="sxs-lookup"><span data-stu-id="815c0-172">After</span></span></td>
<td><span data-ttu-id="815c0-173">Egyik sem</span><span class="sxs-lookup"><span data-stu-id="815c0-173">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="815c0-174">Számla</span><span class="sxs-lookup"><span data-stu-id="815c0-174">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="8"><span data-ttu-id="815c0-175">Termelés</span><span class="sxs-lookup"><span data-stu-id="815c0-175">Production</span></span></td>
<td rowspan="3"><span data-ttu-id="815c0-176">Nyilvántartás</span><span class="sxs-lookup"><span data-stu-id="815c0-176">Registration</span></span></td>
<td rowspan="3"><span data-ttu-id="815c0-177">Nem alkalmazható</span><span class="sxs-lookup"><span data-stu-id="815c0-177">Not applicable</span></span></td>
<td><span data-ttu-id="815c0-178">Egyik sem</span><span class="sxs-lookup"><span data-stu-id="815c0-178">None</span></span></td>
<td rowspan="12"><span data-ttu-id="815c0-179">Mind</span><span class="sxs-lookup"><span data-stu-id="815c0-179">All</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="815c0-180">Készként jelentés</span><span class="sxs-lookup"><span data-stu-id="815c0-180">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="815c0-181">Záró</span><span class="sxs-lookup"><span data-stu-id="815c0-181">End</span></span></td>
</tr>
<tr>
<td rowspan="5"><span data-ttu-id="815c0-182">Készként jelentés</span><span class="sxs-lookup"><span data-stu-id="815c0-182">Report as finished</span></span></td>
<td rowspan="3"><span data-ttu-id="815c0-183">Előtte</span><span class="sxs-lookup"><span data-stu-id="815c0-183">Before</span></span></td>
<td><span data-ttu-id="815c0-184">Egyik sem</span><span class="sxs-lookup"><span data-stu-id="815c0-184">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="815c0-185">Készként jelentés</span><span class="sxs-lookup"><span data-stu-id="815c0-185">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="815c0-186">Záró</span><span class="sxs-lookup"><span data-stu-id="815c0-186">End</span></span></td>
</tr>
<tr>
<td rowspan="2"><span data-ttu-id="815c0-187">Utána</span><span class="sxs-lookup"><span data-stu-id="815c0-187">After</span></span></td>
<td><span data-ttu-id="815c0-188">Egyik sem</span><span class="sxs-lookup"><span data-stu-id="815c0-188">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="815c0-189">Záró</span><span class="sxs-lookup"><span data-stu-id="815c0-189">End</span></span></td>
</tr>
<tr>
<td rowspan="4"><span data-ttu-id="815c0-190">Karantén</span><span class="sxs-lookup"><span data-stu-id="815c0-190">Quarantine</span></span></td>
<td rowspan="3"><span data-ttu-id="815c0-191">Készként jelentés</span><span class="sxs-lookup"><span data-stu-id="815c0-191">Report as finished</span></span></td>
<td rowspan="2"><span data-ttu-id="815c0-192">Előtte</span><span class="sxs-lookup"><span data-stu-id="815c0-192">Before</span></span></td>
<td><span data-ttu-id="815c0-193">Készként jelentés</span><span class="sxs-lookup"><span data-stu-id="815c0-193">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="815c0-194">Záró</span><span class="sxs-lookup"><span data-stu-id="815c0-194">End</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="815c0-195">Utána</span><span class="sxs-lookup"><span data-stu-id="815c0-195">After</span></span></td>
<td><span data-ttu-id="815c0-196">Záró</span><span class="sxs-lookup"><span data-stu-id="815c0-196">End</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="815c0-197">Záró</span><span class="sxs-lookup"><span data-stu-id="815c0-197">End</span></span></td>
<td><span data-ttu-id="815c0-198">Előtte</span><span class="sxs-lookup"><span data-stu-id="815c0-198">Before</span></span></td>
<td><span data-ttu-id="815c0-199">Záró</span><span class="sxs-lookup"><span data-stu-id="815c0-199">End</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="815c0-200">Útvonalművelet</span><span class="sxs-lookup"><span data-stu-id="815c0-200">Route operation</span></span></td>
<td rowspan="3"><span data-ttu-id="815c0-201">Készként jelentés</span><span class="sxs-lookup"><span data-stu-id="815c0-201">Report as finished</span></span></td>
<td rowspan="2"><span data-ttu-id="815c0-202">Előtte</span><span class="sxs-lookup"><span data-stu-id="815c0-202">Before</span></span></td>
<td><span data-ttu-id="815c0-203">None</span><span class="sxs-lookup"><span data-stu-id="815c0-203">None</span></span></td>
<td rowspan="3"><span data-ttu-id="815c0-204">Egyedi azonosító, Csoport vagy Mind, valamint adott Erőforrás, Csoport vagy Mind</span><span class="sxs-lookup"><span data-stu-id="815c0-204">Specific ID, Group, or All, and specific Resource, Group, or All</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="815c0-205">Készként jelentés</span><span class="sxs-lookup"><span data-stu-id="815c0-205">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="815c0-206">Után</span><span class="sxs-lookup"><span data-stu-id="815c0-206">After</span></span></td>
<td><span data-ttu-id="815c0-207">None</span><span class="sxs-lookup"><span data-stu-id="815c0-207">None</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="815c0-208">Társtermék gyártása</span><span class="sxs-lookup"><span data-stu-id="815c0-208">Co-product production</span></span></td>
<td><span data-ttu-id="815c0-209">Nyilvántartás</span><span class="sxs-lookup"><span data-stu-id="815c0-209">Registration</span></span></td>
<td><span data-ttu-id="815c0-210">Nem alkalmazható</span><span class="sxs-lookup"><span data-stu-id="815c0-210">Not applicable</span></span></td>
<td rowspan="3"><span data-ttu-id="815c0-211">None</span><span class="sxs-lookup"><span data-stu-id="815c0-211">None</span></span></td>
<td rowspan="3"><span data-ttu-id="815c0-212">Összes</span><span class="sxs-lookup"><span data-stu-id="815c0-212">All</span></span></td>
</tr>
<tr>
<td rowspan="2"><span data-ttu-id="815c0-213">Készként jelentés</span><span class="sxs-lookup"><span data-stu-id="815c0-213">Report as finished</span></span></td>
<td><span data-ttu-id="815c0-214">Előtte</span><span class="sxs-lookup"><span data-stu-id="815c0-214">Before</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="815c0-215">Után</span><span class="sxs-lookup"><span data-stu-id="815c0-215">After</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="815c0-216">A *Minőségkezelés a raktári folyamatokhoz* funkció hozzáadja a minőségi rendelés feldolgozásához szükséges képességeket, ahol az **Eseménytípus** mező beállítása *Készként jelentés*, és a **Végrehajtás** mező beállítása *Után*, és ahol az **Eseménytípus** mező típusú beszerzések beállítása *Regisztráció*.</span><span class="sxs-lookup"><span data-stu-id="815c0-216">The *Quality management for warehouse processes* feature adds capabilities for quality order processing for production where the **Event type** field is set to *Report as finished* and the **Execution** field is set to *After*, and for purchases where the **Event type** field is set to *Registration*.</span></span> <span data-ttu-id="815c0-217">További információ: [Raktári folyamatok minőségkezelése](quality-management-for-warehouses-processes.md).</span><span class="sxs-lookup"><span data-stu-id="815c0-217">For more information, see [Quality management for warehouse processes](quality-management-for-warehouses-processes.md).</span></span>

<span data-ttu-id="815c0-218">A következő táblázatban bővebben tájékozódhat arról, hogy hogyan hozhatóak létre minőségi rendelések adott típusú folyamatokhoz.</span><span class="sxs-lookup"><span data-stu-id="815c0-218">The following table provides more information about how quality orders can be generated for specific types of processes.</span></span>

<div class="tableSection">
<table>
<thead>
<tr>
<th><span data-ttu-id="815c0-219">Folyamat típusa</span><span class="sxs-lookup"><span data-stu-id="815c0-219">Type of process</span></span></th>
<th><span data-ttu-id="815c0-220">Mikor hozhatóak létre automatikusan minőségi rendelések?</span><span class="sxs-lookup"><span data-stu-id="815c0-220">When quality orders can be automatically generated</span></span></th>
<th><span data-ttu-id="815c0-221">Mikor hozhatóak létre minőségi rendelések, amennyiben romboló tesztekre van szükség?</span><span class="sxs-lookup"><span data-stu-id="815c0-221">When quality orders can be generated if destructive testing is required</span></span></th>
<th><span data-ttu-id="815c0-222">Feltételekre vonatkozó információ</span><span class="sxs-lookup"><span data-stu-id="815c0-222">Condition information</span></span></th>
<th><span data-ttu-id="815c0-223">Manuális létrehozásra vonatkozó információ</span><span class="sxs-lookup"><span data-stu-id="815c0-223">Manual generation information</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="815c0-224">Beszerzési rendelés</span><span class="sxs-lookup"><span data-stu-id="815c0-224">Purchase order</span></span></td>
<td><span data-ttu-id="815c0-225">A bevételezett anyagra vonatkozó bevételezési lista vagy termékbevételezés feladása előtt vagy után</span><span class="sxs-lookup"><span data-stu-id="815c0-225">Before or after a receipts list or product receipt for the material that is received is posted</span></span></td>
<td><span data-ttu-id="815c0-226">A bevételezett anyagra vonatkozó termékbevételezés feladása után, mivel az anyagnak rendelkezésre kell állnia a romboló teszt elvégzéséhez</span><span class="sxs-lookup"><span data-stu-id="815c0-226">After the product receipt for the material that is received is posted, because the material must be available for destructive testing</span></span></td>
<td><span data-ttu-id="815c0-227">A minőségi rendelés követelménye vonatkozhat egy adott telephelyre, cikkre vagy szállítóra, illetve ezek bármilyen kombinációjára.</span><span class="sxs-lookup"><span data-stu-id="815c0-227">The requirement for a quality order can reflect a specific site, item, or vendor, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="815c0-228">A beszerzési rendelésekhez manuálisan generált minőségi rendelésekben felhasználhatók a minőségi társítási rekordban szereplő adatok, például a mintavételezési eljárás.</span><span class="sxs-lookup"><span data-stu-id="815c0-228">A manually generated quality order that refers to a purchase order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="815c0-229">Karanténutasítás</span><span class="sxs-lookup"><span data-stu-id="815c0-229">Quarantine order</span></span></td>
<td><span data-ttu-id="815c0-230">Mielőtt vagy miután a karanténutasítás készként lett jelentve vagy befejeződött</span><span class="sxs-lookup"><span data-stu-id="815c0-230">Before or after the quarantine order is reported as finished or ended</span></span></td>
<td><span data-ttu-id="815c0-231">Romboló teszteket igénylő minőségi rendelések nem hozhatóak létre.</span><span class="sxs-lookup"><span data-stu-id="815c0-231">Quality orders that require destructive tests can't be generated.</span></span> <span data-ttu-id="815c0-232">A rendszer feltételezi, hogy a karanténutasítás funkció kezeli a roncsolt anyag elhelyezését.</span><span class="sxs-lookup"><span data-stu-id="815c0-232">It's assumed that the quarantine order functionality handles the disposition of the material that is destroyed.</span></span></td>
<td><span data-ttu-id="815c0-233">A minőségi rendelés követelménye vonatkozhat egy adott telephelyre, cikkre vagy szállítóra, illetve ezek bármilyen kombinációjára.</span><span class="sxs-lookup"><span data-stu-id="815c0-233">The requirement for a quality order can reflect a specific site, item, or vendor, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="815c0-234">A karanténutasításokhoz manuálisan generált minőségi rendelésekben felhasználhatók a minőségi társítási rekordban szereplő adatok, például a mintavételezési eljárás.</span><span class="sxs-lookup"><span data-stu-id="815c0-234">A manually generated quality order that refers to a quarantine order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="815c0-235">Értékesítési rendelés</span><span class="sxs-lookup"><span data-stu-id="815c0-235">Sales order</span></span></td>
<td><span data-ttu-id="815c0-236">A szállított cikkekre vonatkozó ütemezett kitárolási folyamat vagy szállítólevél frissítése előtt</span><span class="sxs-lookup"><span data-stu-id="815c0-236">Before a scheduled picking process or packing slip update for the items that are being shipped</span></span></td>
<td><span data-ttu-id="815c0-237">Bármelyik lépésnél</span><span class="sxs-lookup"><span data-stu-id="815c0-237">At any step</span></span></td>
<td><span data-ttu-id="815c0-238">A minőségi rendelés követelménye vonatkozhat egy adott telephelyre, cikkre vagy vevőre, illetve ezek bármilyen kombinációjára.</span><span class="sxs-lookup"><span data-stu-id="815c0-238">The requirement for a quality order can reflect a specific site, item, or customer, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="815c0-239">Az értékesítési rendelésekhez manuálisan generált minőségi rendelésekben felhasználhatók a minőségi társítási rekordban szereplő adatok, például a mintavételezési eljárás.</span><span class="sxs-lookup"><span data-stu-id="815c0-239">A manually generated quality order that refers to a sales order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="815c0-240">Termelési rendelés</span><span class="sxs-lookup"><span data-stu-id="815c0-240">Production order</span></span></td>
<td><span data-ttu-id="815c0-241">A termelési rendelés befejezett mennyiségének jelentése előtt vagy után</span><span class="sxs-lookup"><span data-stu-id="815c0-241">Before or after the finished quantity for the production order is reported</span></span></td>
<td><span data-ttu-id="815c0-242">A termelési rendelés befejezett mennyiségének jelentése után</span><span class="sxs-lookup"><span data-stu-id="815c0-242">After the finished quantity for the production order is reported</span></span></td>
<td><span data-ttu-id="815c0-243">A minőségi rendelés követelménye vonatkozhat egy adott telephelyre, cikkre, illetve ezek bármilyen kombinációjára.</span><span class="sxs-lookup"><span data-stu-id="815c0-243">The requirement for a quality order can reflect a specific site or item, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="815c0-244">A termelési rendelésekhez manuálisan generált minőségi rendelésekben felhasználhatók a minőségi társítási rekordban szereplő adatok, például a mintavételezési eljárás.</span><span class="sxs-lookup"><span data-stu-id="815c0-244">A manually generated quality order that refers to a production order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="815c0-245">Útvonalművelettel rendelkező termelési utasítás</span><span class="sxs-lookup"><span data-stu-id="815c0-245">Production order that has a route operation</span></span></td>
<td><span data-ttu-id="815c0-246">A műveletre vonatkozó jelentés befejezése előtt vagy után</span><span class="sxs-lookup"><span data-stu-id="815c0-246">Before or after the report is finished for an operation</span></span></td>
<td><span data-ttu-id="815c0-247">Miután az utolsó művelet készként való jelentése megtörtént</span><span class="sxs-lookup"><span data-stu-id="815c0-247">After the reporting production is finished for the last operation</span></span></td>
<td><span data-ttu-id="815c0-248">A minőségi rendelés követelménye vonatkozhat egy adott telephelyre, cikkre, vevőre vagy üzemi erőforrásra, illetve ezek bármilyen kombinációjára.</span><span class="sxs-lookup"><span data-stu-id="815c0-248">The requirement for a quality order can reflect a specific site, item, or operations resource, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="815c0-249">Az útvonalművelethez manuálisan generált minőségi rendelésekben felhasználhatók a minőségi társítási rekordban szereplő adatok, például a mintavételezési eljárás.</span><span class="sxs-lookup"><span data-stu-id="815c0-249">A manually generated quality order that refers to a route operation can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="815c0-250">Készlet</span><span class="sxs-lookup"><span data-stu-id="815c0-250">Inventory</span></span></td>
<td><span data-ttu-id="815c0-251">A készletnaplón belüli tranzakciókhoz és az átmozgatási rendelési tranzakciókhoz nem generálhatók automatikusan minőségi rendelések.</span><span class="sxs-lookup"><span data-stu-id="815c0-251">A quality order can't be automatically generated for a transaction in an inventory journal or for transfer order transactions.</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="815c0-252">Cikk készletmennyiségére vonatkozó minőségi rendelést manuálisan kell létrehozni.</span><span class="sxs-lookup"><span data-stu-id="815c0-252">A quality order must be manually created for an item's inventory quantity.</span></span> <span data-ttu-id="815c0-253">Tényleges aktuális készlet szükséges.</span><span class="sxs-lookup"><span data-stu-id="815c0-253">Physical on-hand inventory is required.</span></span></td>
</tr>
</tbody>
</table>
</div>

## <a name="examples-of-automatic-generation-of-quality-orders"></a><span data-ttu-id="815c0-254">Minőségi rendelések automatikus generálásával kapcsolatos példák</span><span class="sxs-lookup"><span data-stu-id="815c0-254">Examples of automatic generation of quality orders</span></span>

### <a name="purchasing"></a><span data-ttu-id="815c0-255">Beszerzés</span><span class="sxs-lookup"><span data-stu-id="815c0-255">Purchasing</span></span>

<span data-ttu-id="815c0-256">Ha a beszerzés modulban az **Eseménytípus** mezőt a *Termék nyugtája* értékre állítja, a **Végrehajtás** mezőt pedig *Után* értékre a **Minőségi társítások** lapon, akkor a következő eredményeket kapja:</span><span class="sxs-lookup"><span data-stu-id="815c0-256">In purchasing, if you set the **Event type** field to *Product receipt* and the **Execution** field to *After* on the **Quality associations** page, you get the following results:</span></span>

- <span data-ttu-id="815c0-257">Ha a **Frissített mennyiség** beállítás *Igen* értékre van állítva , akkor a program minőségi rendelést hoz létre a beszerzési rendeléshez tartozó összes bevételezéshez, a bevételezett mennyiség és a cikkmintavétel beállításai alapján.</span><span class="sxs-lookup"><span data-stu-id="815c0-257">If the **Per updated quantity** option is set to *Yes*, a quality order is generated for every receipt against the purchase order, based on the received quantity and settings in the item sampling.</span></span> <span data-ttu-id="815c0-258">Minden alkalommal, amikor egy mennyiséget a beszerzési rendeléssel szemben megkapnak, új minőségi rendelések jönnek létre az újonnan megkapott mennyiség alapján.</span><span class="sxs-lookup"><span data-stu-id="815c0-258">Every time that a quantity is received against the purchase order, new quality orders are generated based on the newly received quantity.</span></span>
- <span data-ttu-id="815c0-259">Ha a **Frissített mennyiség** beállítás *Igen* értékre van állítva , akkor a program minőségi rendelést hoz létre a beszerzési rendeléshez tartozó első bevételezéshez, a bevételezett mennyiség és a cikkmintavétel beállításai alapján.</span><span class="sxs-lookup"><span data-stu-id="815c0-259">If the **Per updated quantity** option is set to *No*, a quality order is generated for the first receipt against the purchase order, based on the received quantity.</span></span> <span data-ttu-id="815c0-260">Ezenkívül a program egy vagy több minőségi rendelést hoz létre a fennmaradó mennyiség alapján, a nyomon követési dimenziók függvényében.</span><span class="sxs-lookup"><span data-stu-id="815c0-260">Additionally, one or more quality orders are created based on the remaining quantity, depending on the tracking dimensions.</span></span> <span data-ttu-id="815c0-261">Nem jönnek létre minőségi rendelések a beszerzési rendelés későbbi bevételezéseihez.</span><span class="sxs-lookup"><span data-stu-id="815c0-261">Quality orders aren't generated for subsequent receipts against the purchase order.</span></span>

### <a name="production"></a><span data-ttu-id="815c0-262">Termelés</span><span class="sxs-lookup"><span data-stu-id="815c0-262">Production</span></span>

<span data-ttu-id="815c0-263">Ha a gyártásban az **Eseménytípus** mezőt a *Befejezettnek jelentés* értékre állítja, a **Végrehajtás** mezőt pedig *Után* értékre a **Minőségi társítások** lapon, akkor a következő eredményeket kapja:</span><span class="sxs-lookup"><span data-stu-id="815c0-263">In production, if you set the **Event type** field to *Report as finished* and the **Execution** field to *After* on the **Quality associations** page, you get the following results:</span></span>

- <span data-ttu-id="815c0-264">Ha a **Frissített mennyiség** beállítás *Igen* értékre van állítva , akkor a program minőségi rendelést hoz létre minden befejezett mennyiség és a cikkmintavételezés beállításai alapján.</span><span class="sxs-lookup"><span data-stu-id="815c0-264">If the **Per updated quantity** option is set to *Yes*, a quality order is generated based on every finished quantity and settings in the item sampling.</span></span> <span data-ttu-id="815c0-265">Minden alkalommal, amikor egy mennyiséget a beszerzési rendeléssel szemben késznek jelentenek, új minőségi rendelések jönnek létre az újonnan elkészült mennyiség alapján.</span><span class="sxs-lookup"><span data-stu-id="815c0-265">Every time that a quantity is reported as finished against the production order, new quality orders are generated based on the newly finished quantity.</span></span> <span data-ttu-id="815c0-266">Ez a generálási logika összhangban van a beszerzéssel.</span><span class="sxs-lookup"><span data-stu-id="815c0-266">This generation logic is consistent with purchasing.</span></span>
- <span data-ttu-id="815c0-267">Ha a **Frissített mennyiség** beállítás *Igen* értékre van állítva , akkor a program minőségi rendelést hoz létre az első alkalommal, amikor a mennyiség készek van jelentve, a kész mennyiség és a cikkmintavétel beállításai alapján.</span><span class="sxs-lookup"><span data-stu-id="815c0-267">If the **Per updated quantity** option is set to *No*, a quality order is generated the first time that a quantity is reported as finished, based on the finished quantity.</span></span> <span data-ttu-id="815c0-268">Ezenkívül a program egy vagy több minőségi rendelést hoz létre a fennmaradó mennyiség alapján, a cikkmintavételezés nyomon követési dimenziói függvényében.</span><span class="sxs-lookup"><span data-stu-id="815c0-268">Additionally, one or more quality orders are created based on the remaining quantity, depending on the tracking dimensions of the item sampling.</span></span> <span data-ttu-id="815c0-269">A további kész mennyiségek esetében nem jönnek létre minőségi rendelések.</span><span class="sxs-lookup"><span data-stu-id="815c0-269">Quality orders aren't generated for subsequent finished quantities.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="815c0-270">Minőség megadása</span><span class="sxs-lookup"><span data-stu-id="815c0-270">Quality specification</span></span></th>
<th><span data-ttu-id="815c0-271">Frissített mennyiségenként</span><span class="sxs-lookup"><span data-stu-id="815c0-271">Per updated quantity</span></span></th>
<th><span data-ttu-id="815c0-272">Nyomon követési dimenziónként</span><span class="sxs-lookup"><span data-stu-id="815c0-272">Per tracking dimension</span></span></th>
<th><span data-ttu-id="815c0-273">Eredmény</span><span class="sxs-lookup"><span data-stu-id="815c0-273">Result</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="815c0-274">Százalék: 10%</span><span class="sxs-lookup"><span data-stu-id="815c0-274">Percentage: 10%</span></span></td>
<td><span data-ttu-id="815c0-275">Igen</span><span class="sxs-lookup"><span data-stu-id="815c0-275">Yes</span></span></td>
<td>
<p><span data-ttu-id="815c0-276">Kötegszám: Nincs</span><span class="sxs-lookup"><span data-stu-id="815c0-276">Batch number: No</span></span></p>
<p><span data-ttu-id="815c0-277">Sorozatszám: Nincs</span><span class="sxs-lookup"><span data-stu-id="815c0-277">Serial number: No</span></span></p>
</td>
<td>
<p><span data-ttu-id="815c0-278">Rendelt mennyiség: 100</span><span class="sxs-lookup"><span data-stu-id="815c0-278">Order quantity: 100</span></span></p>
<ol>
<li><span data-ttu-id="815c0-279">Készként jelentés 30-hoz</span><span class="sxs-lookup"><span data-stu-id="815c0-279">Report as finished for 30</span></span>
<ul>
<li><span data-ttu-id="815c0-280">1. minőségi rendelés 3-hoz (a 30 10%-a)</span><span class="sxs-lookup"><span data-stu-id="815c0-280">Quality order 1 for 3 (10% of 30)</span></span></li>
</ul>
</li>
<li><span data-ttu-id="815c0-281">Készként jelentés 70-hoz</span><span class="sxs-lookup"><span data-stu-id="815c0-281">Report as finished for 70</span></span>
<ul>
<li><span data-ttu-id="815c0-282">2. minőségi rendelés 7-hez (a fennmaradó rendelési mennyiség 10%-a, amely ebben az esetben 70)</span><span class="sxs-lookup"><span data-stu-id="815c0-282">Quality order 2 for 7 (10% of the remaining order quantity, which is 70 in this case)</span></span></li>
</ul>
</li>
</ol>
</td>
</tr>
<tr>
<td><span data-ttu-id="815c0-283">Rögzített mennyiség: 1</span><span class="sxs-lookup"><span data-stu-id="815c0-283">Fixed quantity: 1</span></span></td>
<td><span data-ttu-id="815c0-284">Nincs</span><span class="sxs-lookup"><span data-stu-id="815c0-284">No</span></span></td>
<td>
<p><span data-ttu-id="815c0-285">Kötegszám: Nincs</span><span class="sxs-lookup"><span data-stu-id="815c0-285">Batch number: No</span></span></p>
<p><span data-ttu-id="815c0-286">Sorozatszám: Nincs</span><span class="sxs-lookup"><span data-stu-id="815c0-286">Serial number: No</span></span></p>
</td>
<td><span data-ttu-id="815c0-287">Rendelt mennyiség: 100</span><span class="sxs-lookup"><span data-stu-id="815c0-287">Order quantity: 100</span></span>
<ol>
<li><span data-ttu-id="815c0-288">Készként jelentés 30-hoz</span><span class="sxs-lookup"><span data-stu-id="815c0-288">Report as finished for 30</span></span>
<ul>
<li><span data-ttu-id="815c0-289">Az 1. minőségi rendelés 1-hez lesz létrehozva (az első jelentett kész mennyiséghez, amelynek rögzített értéke 1)</span><span class="sxs-lookup"><span data-stu-id="815c0-289">Quality order 1 for 1 (for the first reported-as-finished quantity, which has a fixed value of 1)</span></span></li>
<li><span data-ttu-id="815c0-290">A 2. minőségi rendelés 1-hez lesz létrehozva (a fennmaradó mennyiséghez, amelynek rögzített értéke 1)</span><span class="sxs-lookup"><span data-stu-id="815c0-290">Quality order 2 for 1 (for the remaining quantity, which still has a fixed value of 1)</span></span></li>
</ul>
</li>
<li><span data-ttu-id="815c0-291">Készként jelentés 10-hoz</span><span class="sxs-lookup"><span data-stu-id="815c0-291">Report as finished for 10</span></span>
<ul>
<li><span data-ttu-id="815c0-292">Nem jönnek létre minőségi rendelések.</span><span class="sxs-lookup"><span data-stu-id="815c0-292">No quality orders are created.</span></span></li>
</ul>
</li>
<li><span data-ttu-id="815c0-293">Készként jelentés 60-hoz</span><span class="sxs-lookup"><span data-stu-id="815c0-293">Report as finished for 60</span></span>
<ul>
<li><span data-ttu-id="815c0-294">Nem jönnek létre minőségi rendelések.</span><span class="sxs-lookup"><span data-stu-id="815c0-294">No quality orders are created.</span></span></li>
</ul>
</li>
</ol>
</td>
</tr>
<tr>
<td><span data-ttu-id="815c0-295">Rögzített mennyiség: 1</span><span class="sxs-lookup"><span data-stu-id="815c0-295">Fixed quantity: 1</span></span></td>
<td><span data-ttu-id="815c0-296">Igen</span><span class="sxs-lookup"><span data-stu-id="815c0-296">Yes</span></span></td>
<td>
<p><span data-ttu-id="815c0-297">Kötegszám: Igen</span><span class="sxs-lookup"><span data-stu-id="815c0-297">Batch number: Yes</span></span></p>
<p><span data-ttu-id="815c0-298">Sorozatszám: Igen</span><span class="sxs-lookup"><span data-stu-id="815c0-298">Serial number: Yes</span></span></p>
</td>
<td>
<p><span data-ttu-id="815c0-299">Rendelt mennyiség: 10</span><span class="sxs-lookup"><span data-stu-id="815c0-299">Order quantity: 10</span></span></p>
<ol>
<li><span data-ttu-id="815c0-300">Készként jelentve a 3-hoz: 1 a b1 kötegszámhoz, sorozatszám: s1; 1 a b2 kötegszámhoz, sorozatszám: s2; 1 a b3 kötegszámhoz, sorozatszám: s3</span><span class="sxs-lookup"><span data-stu-id="815c0-300">Report as finished for 3: 1 for batch number b1, serial number s1; 1 for batch number b2, serial number s2; and 1 for batch number b3, serial number s3</span></span>
<ul>
<li><span data-ttu-id="815c0-301">1. minőségi rendelés 1-hez, b1 kötegszám, sorozatszám: s1</span><span class="sxs-lookup"><span data-stu-id="815c0-301">Quality order 1 for 1 of batch number b1, serial number s1</span></span></li>
<li><span data-ttu-id="815c0-302">2. minőségi rendelés 1-hez, b2 kötegszám, sorozatszám: s2</span><span class="sxs-lookup"><span data-stu-id="815c0-302">Quality order 2 for 1 of batch number b2, serial number s2</span></span></li>
<li><span data-ttu-id="815c0-303">3. minőségi rendelés 1-hez, b3 kötegszám, sorozatszám: s3</span><span class="sxs-lookup"><span data-stu-id="815c0-303">Quality order 3 for 1 of batch number b3, serial number s3</span></span></li>
</ul>
</li>
<li><span data-ttu-id="815c0-304">Készként jelentve a 2-höz: 1 a b4 kötegszámhoz, sorozatszám: s4; 1 a b5 kötegszámhoz, sorozatszám: s5</span><span class="sxs-lookup"><span data-stu-id="815c0-304">Report as finished for 2: 1 for batch number b4, serial number s4; and 1 for batch number b5, serial number s5</span></span>
<ul>
<li><span data-ttu-id="815c0-305">4. minőségi rendelés 1-hez, b4 kötegszám, sorozatszám: s4</span><span class="sxs-lookup"><span data-stu-id="815c0-305">Quality order 4 for 1 of batch number b4, serial number s4</span></span></li>
<li><span data-ttu-id="815c0-306">5. minőségi rendelés 1-hez, b5 kötegszám, sorozatszám: s5</span><span class="sxs-lookup"><span data-stu-id="815c0-306">Quality order 5 for 1 of batch number b5, serial number s5</span></span></li>
</ul>
</li>
</ol>
<p><span data-ttu-id="815c0-307"><strong>Megjegyzés:</strong> A köteg újra felhasználható.</span><span class="sxs-lookup"><span data-stu-id="815c0-307"><strong>Note:</strong> The batch can be reused.</span></span></p>
</td>
</tr>
<tr>
<td><span data-ttu-id="815c0-308">Rögzített mennyiség: 2</span><span class="sxs-lookup"><span data-stu-id="815c0-308">Fixed quantity: 2</span></span></td>
<td><span data-ttu-id="815c0-309">Nincs</span><span class="sxs-lookup"><span data-stu-id="815c0-309">No</span></span></td>
<td>
<p><span data-ttu-id="815c0-310">Kötegszám: Igen</span><span class="sxs-lookup"><span data-stu-id="815c0-310">Batch number: Yes</span></span></p>
<p><span data-ttu-id="815c0-311">Sorozatszám: Igen</span><span class="sxs-lookup"><span data-stu-id="815c0-311">Serial number: Yes</span></span></p>
</td>
<td>
<p><span data-ttu-id="815c0-312">Rendelt mennyiség: 10</span><span class="sxs-lookup"><span data-stu-id="815c0-312">Order quantity: 10</span></span></p>
<ol>
<li><span data-ttu-id="815c0-313">Készként jelentve a 3-hoz: 1 a b1 kötegszámhoz, sorozatszám: s1; 1 a b2 kötegszámhoz, sorozatszám: s2; 1 a b3 kötegszámhoz, sorozatszám: s3; és 1 a b4 kötegszámhoz, sorozatszám: s4</span><span class="sxs-lookup"><span data-stu-id="815c0-313">Report as finished for 4: 1 for batch number b1, serial number s1; 1 for batch number b2, serial number s2; 1 for batch number b3, serial number s3; and 1 for batch number b4, serial number s4</span></span>
<ul>
<li><span data-ttu-id="815c0-314">1. minőségi rendelés 1-hez, b1 kötegszám, sorozatszám: s1</span><span class="sxs-lookup"><span data-stu-id="815c0-314">Quality order 1 for 1 of batch number b1, serial number s1</span></span></li>
<li><span data-ttu-id="815c0-315">2. minőségi rendelés 1-hez, b2 kötegszám, sorozatszám: s2</span><span class="sxs-lookup"><span data-stu-id="815c0-315">Quality order 2 for 1 of batch number b2, serial number s2</span></span></li>
<li><span data-ttu-id="815c0-316">3. minőségi rendelés 1-hez, b3 kötegszám, sorozatszám: s3</span><span class="sxs-lookup"><span data-stu-id="815c0-316">Quality order 3 for 1 of batch number b3, serial number s3</span></span></li>
<li><span data-ttu-id="815c0-317">4. minőségi rendelés 1-hez, b4 kötegszám, sorozatszám: s4</span><span class="sxs-lookup"><span data-stu-id="815c0-317">Quality order 4 for 1 of batch number b4, serial number s4</span></span></li>
</ul>
<ul>
<li><span data-ttu-id="815c0-318">5. minőségi rendelés a 2-höz, egy kötegszámra és egy sorozatszámra való hivatkozás nélkül</span><span class="sxs-lookup"><span data-stu-id="815c0-318">Quality order 5 for 2, without a reference to a batch number and a serial number</span></span></li>
</ul>
</li>
<li><span data-ttu-id="815c0-319">Készként jelentve a 6-hoz: 1 a b5 kötegszámhoz, sorozatszám: s5; 1 a b6 kötegszámhoz, sorozatszám: s6; 1 a b7 kötegszámhoz, sorozatszám: s7; 1 a b8 kötegszámhoz, sorozatszám: s8; 1 a b9 kötegszámhoz, sorozatszám: s9; 1 a b10 kötegszámhoz, sorozatszám: s10</span><span class="sxs-lookup"><span data-stu-id="815c0-319">Report as finished for 6: 1 for batch number b5, serial number s5; 1 for batch number b6, serial number s6; 1 for batch number b7, serial number s7; 1 for batch number b8, serial number s8; 1 for batch number b9, serial number s9; and 1 for batch number b10, serial number s10</span></span>
<ul>
<li><span data-ttu-id="815c0-320">Nem jönnek létre minőségi rendelések.</span><span class="sxs-lookup"><span data-stu-id="815c0-320">No quality orders are created.</span></span></li>
</ul>
</li>
</ol>
</td>
</tr>
</tbody>
</table>

## <a name="additional-resources"></a><span data-ttu-id="815c0-321">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="815c0-321">Additional resources</span></span>

- [<span data-ttu-id="815c0-322">Minőségkezelési folyamatok</span><span class="sxs-lookup"><span data-stu-id="815c0-322">Quality management processes</span></span>](quality-management-processes.md)
- [<span data-ttu-id="815c0-323">A minőség- és a szabálytalanságkezelés engedélyezése</span><span class="sxs-lookup"><span data-stu-id="815c0-323">Enable quality and nonconformance management</span></span>](enable-quality-management.md)
- [<span data-ttu-id="815c0-324">Raktári folyamatok minőségkezelése</span><span class="sxs-lookup"><span data-stu-id="815c0-324">Quality management for warehouse processes</span></span>](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
