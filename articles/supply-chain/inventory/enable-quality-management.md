---
title: Minőségkezelés áttekintése
description: Ez a témakör leírja, hogyan alkalmazza a minőségkezelés funkciót a Dynamics 365 Supply Chain Management szolgáltatásban, hogy ezzel segítse a termékminőség fejlesztését az ön ellátási láncán belül.
author: perlynne
manager: AnnBe
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventTestAssociationTable, InventTestGroup, InventTestItemQualityGroup, InventTestTable, InventTestVariable, InventTestVariableOutcome
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ba38f9c43fed81768155a27dda88a4bfb4a7828e
ms.sourcegitcommit: 0099fb24f5f40ff442020b488ef4171836c35c48
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/23/2019
ms.locfileid: "2653556"
---
# <a name="quality-management-overview"></a><span data-ttu-id="db6e9-103">Minőségkezelés áttekintése</span><span class="sxs-lookup"><span data-stu-id="db6e9-103">Quality management overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="db6e9-104">Ez a témakör leírja, hogyan alkalmazza a minőségkezelés funkciót a Dynamics 365 Supply Chain Management szolgáltatásban, hogy ezzel segítse a termékminőség fejlesztését az ön ellátási láncán belül.</span><span class="sxs-lookup"><span data-stu-id="db6e9-104">This topic describes how you can use quality management in Dynamics 365 Supply Chain Management to help improve product quality within your supply chain.</span></span>

<span data-ttu-id="db6e9-105">A minőségkezelés segítséget nyújt a szabálytalan termékek javítási folyamatának kezelésében, azok eredetétől függetlenül.</span><span class="sxs-lookup"><span data-stu-id="db6e9-105">Quality management can help you manage turnaround times when you handle nonconforming products, regardless of their point of origin.</span></span> <span data-ttu-id="db6e9-106">Mivel a diagnosztikai típusok javítási jelentésekhez kapcsolódnak, a Supply Chain Management képes beütemezni a problémák megoldásához és azok visszatérésének megelőzéséhez szükséges feladatokat.</span><span class="sxs-lookup"><span data-stu-id="db6e9-106">Because diagnostic types are linked to correction reporting, Supply Chain Management can schedule tasks to correct problems and prevent them from recurring.</span></span>

<span data-ttu-id="db6e9-107">A szabálytalanság kezelésére szolgáló funkció mellett a minőségkezelés egyéb funkciói lehetővé teszik a problémakövetést problématípus (akár belső problémák) szerint, valamint a rövid- és hosszútávú megoldások azonosítását.</span><span class="sxs-lookup"><span data-stu-id="db6e9-107">In addition to functionality for managing nonconformance, quality management includes functionality for tracking issues by problem type (even internal problems), and for identifying solutions as short-term or long-term.</span></span> <span data-ttu-id="db6e9-108">A fő teljesítménymutatókról (KPI-kről) vezetett statisztikák betekintést nyújtanak a múltban megtörtént szabálytalansági problémákba és az azok javítására használt megoldásokba.</span><span class="sxs-lookup"><span data-stu-id="db6e9-108">Statistics about key performance indicators (KPIs) provide insight into the history of previous nonconformance issues and the solutions that were used to correct them.</span></span> <span data-ttu-id="db6e9-109">Az előzményadatok segítségével felülvizsgálhatja a korábbi minőségi mérések hatékonyságát, és kidolgozhatja a jövőben alkalmazni kívánt megfelelő méréseket.</span><span class="sxs-lookup"><span data-stu-id="db6e9-109">You can use historical data to review the effectiveness of previous quality measures and determine appropriate measures to use in the future.</span></span>

<span data-ttu-id="db6e9-110">Mikor beállít egy minőségi társítást, a Supply Chain Management képes létrehozni különféle üzleti folyamatok, események és feltételek minőségi rendeléseit.</span><span class="sxs-lookup"><span data-stu-id="db6e9-110">When you set up a quality association, Supply Chain Management can generate quality orders for various business processes, events, and conditions.</span></span> <span data-ttu-id="db6e9-111">A minőségi társítás vonatkozhat egyetlen cikkre, cikkek egy csoportjára vagy minden cikkre.</span><span class="sxs-lookup"><span data-stu-id="db6e9-111">The quality association can cover a specific item, a specific group of items, or all items.</span></span>

## <a name="examples-of-the-use-of-quality-management"></a><span data-ttu-id="db6e9-112">Példák a minőségkezelés használatára</span><span class="sxs-lookup"><span data-stu-id="db6e9-112">Examples of the use of quality management</span></span>
<span data-ttu-id="db6e9-113">A minőségkezelés rugalmas és sokféle módon megvalósítható, így meg tud felelni az ellátási lánc műveleteinek adott szintjeire vonatkozó követelményeknek.</span><span class="sxs-lookup"><span data-stu-id="db6e9-113">Quality management is flexible and can be implemented in various ways to meet the requirements of specific levels of supply chain operations.</span></span> <span data-ttu-id="db6e9-114">Az alábbi példák ezeknek a funkcióknak a felhasználási lehetőségeit mutatják be.</span><span class="sxs-lookup"><span data-stu-id="db6e9-114">The following examples illustrate possible uses of these features:</span></span>

-   <span data-ttu-id="db6e9-115">Indítson automatikusan minőségellenőrzési folyamatot előre meghatározott feltételek teljesülésekor (adott szállítótól történő beszerzési rendelés raktári regisztrációja alapján).</span><span class="sxs-lookup"><span data-stu-id="db6e9-115">Automatically start a quality control process, based on predefined criteria (upon warehouse registration of a purchase order from a specific vendor).</span></span>
-   <span data-ttu-id="db6e9-116">Vizsgálat alatt zárolja a készletet a jóvá nem hagyott készlet használatának megakadályozása érdekében (a beszerzési rendelési mennyiségek teljes zárolása).</span><span class="sxs-lookup"><span data-stu-id="db6e9-116">Block inventory during inspection to prevent non-approved inventory from being used (full blocking of purchase order quantities).</span></span>
-   <span data-ttu-id="db6e9-117">Az aktuális tényleges készlet vizsgálandó mennyiségének meghatározásához használja a minőségi társítás részét képező cikkmintavételt.</span><span class="sxs-lookup"><span data-stu-id="db6e9-117">Use item sampling as part of a quality association to define the amount of current physical inventory that must be inspected.</span></span> <span data-ttu-id="db6e9-118">A mintavétel történhet adott mennyiség vagy százalékos érték alapján.</span><span class="sxs-lookup"><span data-stu-id="db6e9-118">Sampling can be based on fixed quantities or a percentage.</span></span>
-   <span data-ttu-id="db6e9-119">A részleges bevételezésekhez minőségi rendeléseket kell létrehozni.</span><span class="sxs-lookup"><span data-stu-id="db6e9-119">Create quality orders for partial receipts.</span></span> <span data-ttu-id="db6e9-120">Ha olyan minőségi rendelést szeretne létrehozni, amely egy rendelésen fizikailag bevételezett mennyiségen alapul, akkor be kell jelölnie a **Frissített mennyiségenként** jelölőnégyzetet a **Cikkmintavétel** űrlapon.</span><span class="sxs-lookup"><span data-stu-id="db6e9-120">To create a quality order that is based on the quantity that is physically received with an order, you must select the **Per updated quantity** check box on the **Item sampling** form.</span></span>
-   <span data-ttu-id="db6e9-121">Hozzon létre minimum, maximum és cél tesztértékeket magukban foglaló teszttípusokat, és végezzen előre definiált ellenőrzési eredményeket adó minőségi-mennyiségi teszteket.</span><span class="sxs-lookup"><span data-stu-id="db6e9-121">Create test types that include minimum, maximum, and target test values, and perform qualitative-versus-quantitative testing that has predefined validation results.</span></span>
-   <span data-ttu-id="db6e9-122">Adja meg az elfogadható minőségi szint értékét a minőségi mérések tűréshatárainak szabályozása érdekében.</span><span class="sxs-lookup"><span data-stu-id="db6e9-122">Specify an acceptable quality level (AQL) to control quality measure tolerances.</span></span>
-   <span data-ttu-id="db6e9-123">Határozza meg a vizsgálati művelethez szükséges erőforrásokat (például tesztterület és tesztműszerek).</span><span class="sxs-lookup"><span data-stu-id="db6e9-123">Specify the resources that an inspection operation requires, such as a test area and test instruments.</span></span>

## <a name="working-with-quality-associations"></a><span data-ttu-id="db6e9-124">Minőségi társítások használata</span><span class="sxs-lookup"><span data-stu-id="db6e9-124">Working with quality associations</span></span>
<span data-ttu-id="db6e9-125">Egy minőségi társítást használó üzleti folyamat különféle forrásbizonylatokkal lehet kapcsolatban (például beszerzési rendelésekkel, értékesítési rendelésekkel, vagy termelési rendelésekkel).</span><span class="sxs-lookup"><span data-stu-id="db6e9-125">The business process that uses a quality association can be related to various source documents, such as purchase orders, sales orders, or production orders.</span></span>

<span data-ttu-id="db6e9-126">Minden egyes minőségi társítási rekord meghatározza a létrehozott minőségi rendelésekre vonatkozó teszteket, elfogadható minőségi szintet és mintavételi eljárást.</span><span class="sxs-lookup"><span data-stu-id="db6e9-126">Each quality association record defines the set of tests, the AQL, and the sampling plan that applies to the quality orders that are generated.</span></span> <span data-ttu-id="db6e9-127">Az üzleti folyamat minden egyes változatára definiálnia kell egy minőségi társítási rekordot.</span><span class="sxs-lookup"><span data-stu-id="db6e9-127">You must define a quality association record for each variation in a business process.</span></span> <span data-ttu-id="db6e9-128">Például beállíthat egy olyan minőségi társítást, amely egy beszerzési rendelés termékbevételezésének frissítésekor létrehoz egy minőségi rendelést.</span><span class="sxs-lookup"><span data-stu-id="db6e9-128">For example, you can set up a quality association that generates a quality order when a purchase order product receipt is updated.</span></span> <span data-ttu-id="db6e9-129">A végrehajtási terv beállításától függően letiltható maga az indító folyamat, ha van egy nyitott minőségi rendelés, vagy letilthatóak az ezután következő folyamatok, például a beszerzési rendelés számlázása.</span><span class="sxs-lookup"><span data-stu-id="db6e9-129">Depending on the setup of the execution plan, the triggering process itself can be blocked while there is an open quality order, or the next processes, such as purchase order invoicing, can be blocked.</span></span>

<span data-ttu-id="db6e9-130">**Megjegyzés:** Amíg vannak nyitott minőségi rendelések, a készletmennyiségek kiadása automatikusan le van tiltva.</span><span class="sxs-lookup"><span data-stu-id="db6e9-130">**Note:** While there are open quality orders, inventory quantities are automatically blocked from being issued.</span></span> <span data-ttu-id="db6e9-131">A **Cikkmintavételek** lap **Teljes zárolás** beállításától függően a mennyiség a minőségi rendelésen vagy a forrásbizonylat sorában szereplő mennyiség lehet.</span><span class="sxs-lookup"><span data-stu-id="db6e9-131">Depending on the **Full blocking** setting on the **Item samplings** page, the quantity is either the quantity on the quality order or the quantity on the source document line.</span></span>

<span data-ttu-id="db6e9-132">Egy adott üzleti folyamatra a minőségi társítási rekord azonosítja azokat az eseményeket és feltételeket, amelyek fennállása esetén a minőségi rendelés létrejön.</span><span class="sxs-lookup"><span data-stu-id="db6e9-132">For a given business process, the quality association record identifies the event and the conditions that a quality order is generated for.</span></span> <span data-ttu-id="db6e9-133">A feltételek helyre vagy jogi személyre vonatkozhatnak.</span><span class="sxs-lookup"><span data-stu-id="db6e9-133">The conditions can be specific to either a site or a legal entity.</span></span> <span data-ttu-id="db6e9-134">Romboló teszteket igénylő minőségi rendelés csak akkor generálható, ha az eseményhez létezik aktuális készlet.</span><span class="sxs-lookup"><span data-stu-id="db6e9-134">A quality order that involves destructive tests can be generated only when on-hand inventory exists for the event.</span></span>

<span data-ttu-id="db6e9-135">A következő példák bemutatják egy minőségi társítási rekord meghatározását az egyes üzleti folyamatok változásainak megfelelően.</span><span class="sxs-lookup"><span data-stu-id="db6e9-135">The following examples illustrate how a quality association record is defined for the variations in each business process.</span></span> <span data-ttu-id="db6e9-136">Egy minőségi társítási rekord által az egyes példák esetén meghatározott eseményeket és feltételeket az alábbi táblázat összegzi.</span><span class="sxs-lookup"><span data-stu-id="db6e9-136">For each example, the following table summarizes the events and conditions that are defined by a quality association record.</span></span>

<table>
<tbody>
<tr>
<th><span data-ttu-id="db6e9-137">Hivatkozás típusa</span><span class="sxs-lookup"><span data-stu-id="db6e9-137">Reference type</span></span></th>
<th><span data-ttu-id="db6e9-138">Eseménytípus</span><span class="sxs-lookup"><span data-stu-id="db6e9-138">Event type</span></span></th>
<th><span data-ttu-id="db6e9-139">Végrehajtás</span><span class="sxs-lookup"><span data-stu-id="db6e9-139">Execution</span></span></th>
<th><span data-ttu-id="db6e9-140">Eseményzárolás</span><span class="sxs-lookup"><span data-stu-id="db6e9-140">Event blocking</span></span></th>
<th><span data-ttu-id="db6e9-141">Dokumentumhivatkozás</span><span class="sxs-lookup"><span data-stu-id="db6e9-141">Document reference</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="db6e9-142">Készlet</span><span class="sxs-lookup"><span data-stu-id="db6e9-142">Inventory</span></span></td>
<td><span data-ttu-id="db6e9-143">Nem alkalmazható</span><span class="sxs-lookup"><span data-stu-id="db6e9-143">Not applicable</span></span></td>
<td><span data-ttu-id="db6e9-144">Nem alkalmazható</span><span class="sxs-lookup"><span data-stu-id="db6e9-144">Not applicable</span></span></td>
<td><span data-ttu-id="db6e9-145">Egyik sem</span><span class="sxs-lookup"><span data-stu-id="db6e9-145">None</span></span></td>
<td><span data-ttu-id="db6e9-146">Mind</span><span class="sxs-lookup"><span data-stu-id="db6e9-146">All</span></span></td>
</tr>
<tr>
<td rowspan="7"><span data-ttu-id="db6e9-147">Értékesítés</span><span class="sxs-lookup"><span data-stu-id="db6e9-147">Sales</span></span></td>
<td rowspan="4"><span data-ttu-id="db6e9-148">Kitárolási folyamat ütemezve</span><span class="sxs-lookup"><span data-stu-id="db6e9-148">Picking process is scheduled</span></span></td>
<td rowspan="4"><span data-ttu-id="db6e9-149">Előtte</span><span class="sxs-lookup"><span data-stu-id="db6e9-149">Before</span></span></td>
<td><span data-ttu-id="db6e9-150">Egyik sem</span><span class="sxs-lookup"><span data-stu-id="db6e9-150">None</span></span></td>
<td rowspan="22"><span data-ttu-id="db6e9-151">Csak Egyedi azonosító, Csoport vagy Mind</span><span class="sxs-lookup"><span data-stu-id="db6e9-151">Specific ID, Group, or All only</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="db6e9-152">Kitárolási folyamat</span><span class="sxs-lookup"><span data-stu-id="db6e9-152">Picking process</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="db6e9-153">Szállítólevél</span><span class="sxs-lookup"><span data-stu-id="db6e9-153">Packing slip</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="db6e9-154">Számla</span><span class="sxs-lookup"><span data-stu-id="db6e9-154">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="db6e9-155">Szállítólevél</span><span class="sxs-lookup"><span data-stu-id="db6e9-155">Packing slip</span></span></td>
<td rowspan="3"><span data-ttu-id="db6e9-156">Előtte</span><span class="sxs-lookup"><span data-stu-id="db6e9-156">Before</span></span></td>
<td><span data-ttu-id="db6e9-157">Egyik sem</span><span class="sxs-lookup"><span data-stu-id="db6e9-157">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="db6e9-158">Szállítólevél</span><span class="sxs-lookup"><span data-stu-id="db6e9-158">Packing slip</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="db6e9-159">Számla</span><span class="sxs-lookup"><span data-stu-id="db6e9-159">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="15"><span data-ttu-id="db6e9-160">Beszerzés</span><span class="sxs-lookup"><span data-stu-id="db6e9-160">Purchase</span></span></td>
<td rowspan="7"><span data-ttu-id="db6e9-161">Bevételezési lista</span><span class="sxs-lookup"><span data-stu-id="db6e9-161">Receipt list</span></span></td>
<td rowspan="4"><span data-ttu-id="db6e9-162">Előtte</span><span class="sxs-lookup"><span data-stu-id="db6e9-162">Before</span></span></td>
<td><span data-ttu-id="db6e9-163">Egyik sem</span><span class="sxs-lookup"><span data-stu-id="db6e9-163">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="db6e9-164">Bevételezési lista</span><span class="sxs-lookup"><span data-stu-id="db6e9-164">Receipt list</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="db6e9-165">Termékbevételezés</span><span class="sxs-lookup"><span data-stu-id="db6e9-165">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="db6e9-166">Számla</span><span class="sxs-lookup"><span data-stu-id="db6e9-166">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="db6e9-167">Utána</span><span class="sxs-lookup"><span data-stu-id="db6e9-167">After</span></span></td>
<td><span data-ttu-id="db6e9-168">Egyik sem</span><span class="sxs-lookup"><span data-stu-id="db6e9-168">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="db6e9-169">Termékbevételezés</span><span class="sxs-lookup"><span data-stu-id="db6e9-169">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="db6e9-170">Számla</span><span class="sxs-lookup"><span data-stu-id="db6e9-170">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="db6e9-171">Nyilvántartás</span><span class="sxs-lookup"><span data-stu-id="db6e9-171">Registration</span></span></td>
<td rowspan="3"><span data-ttu-id="db6e9-172">Nem alkalmazható</span><span class="sxs-lookup"><span data-stu-id="db6e9-172">Not applicable</span></span></td>
<td><span data-ttu-id="db6e9-173">Egyik sem</span><span class="sxs-lookup"><span data-stu-id="db6e9-173">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="db6e9-174">Termékbevételezés</span><span class="sxs-lookup"><span data-stu-id="db6e9-174">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="db6e9-175">Számla</span><span class="sxs-lookup"><span data-stu-id="db6e9-175">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="5"><span data-ttu-id="db6e9-176">Termékbevételezés</span><span class="sxs-lookup"><span data-stu-id="db6e9-176">Product receipt</span></span></td>
<td rowspan="3"><span data-ttu-id="db6e9-177">Előtte</span><span class="sxs-lookup"><span data-stu-id="db6e9-177">Before</span></span></td>
<td><span data-ttu-id="db6e9-178">Egyik sem</span><span class="sxs-lookup"><span data-stu-id="db6e9-178">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="db6e9-179">Termékbevételezés</span><span class="sxs-lookup"><span data-stu-id="db6e9-179">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="db6e9-180">Számla</span><span class="sxs-lookup"><span data-stu-id="db6e9-180">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="2"><span data-ttu-id="db6e9-181">Utána</span><span class="sxs-lookup"><span data-stu-id="db6e9-181">After</span></span></td>
<td><span data-ttu-id="db6e9-182">Egyik sem</span><span class="sxs-lookup"><span data-stu-id="db6e9-182">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="db6e9-183">Számla</span><span class="sxs-lookup"><span data-stu-id="db6e9-183">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="8"><span data-ttu-id="db6e9-184">Termelés</span><span class="sxs-lookup"><span data-stu-id="db6e9-184">Production</span></span></td>
<td rowspan="3"><span data-ttu-id="db6e9-185">Nyilvántartás</span><span class="sxs-lookup"><span data-stu-id="db6e9-185">Registration</span></span></td>
<td rowspan="3"><span data-ttu-id="db6e9-186">Nem alkalmazható</span><span class="sxs-lookup"><span data-stu-id="db6e9-186">Not applicable</span></span></td>
<td><span data-ttu-id="db6e9-187">Egyik sem</span><span class="sxs-lookup"><span data-stu-id="db6e9-187">None</span></span></td>
<td rowspan="12"><span data-ttu-id="db6e9-188">Mind</span><span class="sxs-lookup"><span data-stu-id="db6e9-188">All</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="db6e9-189">Készként jelentés</span><span class="sxs-lookup"><span data-stu-id="db6e9-189">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="db6e9-190">Záró</span><span class="sxs-lookup"><span data-stu-id="db6e9-190">End</span></span></td>
</tr>
<tr>
<td rowspan="5"><span data-ttu-id="db6e9-191">Készként jelentés</span><span class="sxs-lookup"><span data-stu-id="db6e9-191">Report as finished</span></span></td>
<td rowspan="3"><span data-ttu-id="db6e9-192">Előtte</span><span class="sxs-lookup"><span data-stu-id="db6e9-192">Before</span></span></td>
<td><span data-ttu-id="db6e9-193">Egyik sem</span><span class="sxs-lookup"><span data-stu-id="db6e9-193">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="db6e9-194">Készként jelentés</span><span class="sxs-lookup"><span data-stu-id="db6e9-194">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="db6e9-195">Záró</span><span class="sxs-lookup"><span data-stu-id="db6e9-195">End</span></span></td>
</tr>
<tr>
<td rowspan="2"><span data-ttu-id="db6e9-196">Utána</span><span class="sxs-lookup"><span data-stu-id="db6e9-196">After</span></span></td>
<td><span data-ttu-id="db6e9-197">Egyik sem</span><span class="sxs-lookup"><span data-stu-id="db6e9-197">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="db6e9-198">Záró</span><span class="sxs-lookup"><span data-stu-id="db6e9-198">End</span></span></td>
</tr>
<tr>
<td rowspan="4"><span data-ttu-id="db6e9-199">Karantén</span><span class="sxs-lookup"><span data-stu-id="db6e9-199">Quarantine</span></span></td>
<td rowspan="3"><span data-ttu-id="db6e9-200">Készként jelentés</span><span class="sxs-lookup"><span data-stu-id="db6e9-200">Report as finished</span></span></td>
<td rowspan="2"><span data-ttu-id="db6e9-201">Előtte</span><span class="sxs-lookup"><span data-stu-id="db6e9-201">Before</span></span></td>
<td><span data-ttu-id="db6e9-202">Készként jelentés</span><span class="sxs-lookup"><span data-stu-id="db6e9-202">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="db6e9-203">Záró</span><span class="sxs-lookup"><span data-stu-id="db6e9-203">End</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="db6e9-204">Utána</span><span class="sxs-lookup"><span data-stu-id="db6e9-204">After</span></span></td>
<td><span data-ttu-id="db6e9-205">Záró</span><span class="sxs-lookup"><span data-stu-id="db6e9-205">End</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="db6e9-206">Záró</span><span class="sxs-lookup"><span data-stu-id="db6e9-206">End</span></span></td>
<td><span data-ttu-id="db6e9-207">Előtte</span><span class="sxs-lookup"><span data-stu-id="db6e9-207">Before</span></span></td>
<td><span data-ttu-id="db6e9-208">Záró</span><span class="sxs-lookup"><span data-stu-id="db6e9-208">End</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="db6e9-209">Útvonalművelet</span><span class="sxs-lookup"><span data-stu-id="db6e9-209">Route operation</span></span></td>
<td rowspan="3"><span data-ttu-id="db6e9-210">Készként jelentés</span><span class="sxs-lookup"><span data-stu-id="db6e9-210">Report as finished</span></span></td>
<td rowspan="2"><span data-ttu-id="db6e9-211">Előtte</span><span class="sxs-lookup"><span data-stu-id="db6e9-211">Before</span></span></td>
<td><span data-ttu-id="db6e9-212">Egyik sem</span><span class="sxs-lookup"><span data-stu-id="db6e9-212">None</span></span></td>
<td rowspan="3"><span data-ttu-id="db6e9-213">Egyedi azonosító, Csoport vagy Mind, valamint Erőforrás-specifikus, Csoport vagy Mind</span><span class="sxs-lookup"><span data-stu-id="db6e9-213">Specific ID, Group, or All, and Resource specific, Group, or All</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="db6e9-214">Készként jelentés</span><span class="sxs-lookup"><span data-stu-id="db6e9-214">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="db6e9-215">Utána</span><span class="sxs-lookup"><span data-stu-id="db6e9-215">After</span></span></td>
<td><span data-ttu-id="db6e9-216">Egyik sem</span><span class="sxs-lookup"><span data-stu-id="db6e9-216">None</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="db6e9-217">Társtermék gyártása</span><span class="sxs-lookup"><span data-stu-id="db6e9-217">Co-product production</span></span></td>
<td><span data-ttu-id="db6e9-218">Nyilvántartás</span><span class="sxs-lookup"><span data-stu-id="db6e9-218">Registration</span></span></td>
<td><span data-ttu-id="db6e9-219">Nem alkalmazható</span><span class="sxs-lookup"><span data-stu-id="db6e9-219">Not applicable</span></span></td>
<td rowspan="3"><span data-ttu-id="db6e9-220">Egyik sem</span><span class="sxs-lookup"><span data-stu-id="db6e9-220">None</span></span></td>
<td rowspan="3"><span data-ttu-id="db6e9-221">Mind</span><span class="sxs-lookup"><span data-stu-id="db6e9-221">All</span></span></td>
</tr>
<tr>
<td rowspan="2"><span data-ttu-id="db6e9-222">Készként jelentés</span><span class="sxs-lookup"><span data-stu-id="db6e9-222">Report as finished</span></span></td>
<td><span data-ttu-id="db6e9-223">Előtte</span><span class="sxs-lookup"><span data-stu-id="db6e9-223">Before</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="db6e9-224">Utána</span><span class="sxs-lookup"><span data-stu-id="db6e9-224">After</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="db6e9-225">A következő táblázatban bővebben tájékozódhat arról, hogy hogyan hozhatóak létre minőségi rendelések adott típusú folyamatokhoz.</span><span class="sxs-lookup"><span data-stu-id="db6e9-225">The following table provides more information about how quality orders can be generated for specific types of processes.</span></span>
<div class="tableSection">

<table>
<tbody>
<tr>
<th><span data-ttu-id="db6e9-226">Folyamat típusa</span><span class="sxs-lookup"><span data-stu-id="db6e9-226">Type of process</span></span></th>
<th><span data-ttu-id="db6e9-227">Mikor hozhatóak létre automatikusan minőségi rendelések?</span><span class="sxs-lookup"><span data-stu-id="db6e9-227">When quality orders can be automatically generated</span></span></th>
<th><span data-ttu-id="db6e9-228">Mikor hozhatóak létre minőségi rendelések, amennyiben romboló tesztekre van szükség?</span><span class="sxs-lookup"><span data-stu-id="db6e9-228">When quality orders can be generated if destructive testing is required</span></span></th>
<th><span data-ttu-id="db6e9-229">Feltételekre vonatkozó információ</span><span class="sxs-lookup"><span data-stu-id="db6e9-229">Condition information</span></span></th>
<th><span data-ttu-id="db6e9-230">Manuális létrehozásra vonatkozó információ</span><span class="sxs-lookup"><span data-stu-id="db6e9-230">Manual generation information</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="db6e9-231">Beszerzési rendelés</span><span class="sxs-lookup"><span data-stu-id="db6e9-231">Purchase order</span></span></td>
<td><span data-ttu-id="db6e9-232">A bevételezett anyagra vonatkozó bevételezési lista vagy termékbevételezés feladása előtt vagy után</span><span class="sxs-lookup"><span data-stu-id="db6e9-232">Before or after a receipts list or product receipt for the material that is received is posted</span></span></td>
<td><span data-ttu-id="db6e9-233">A bevételezett anyagra vonatkozó termékbevételezés feladása után, mivel az anyagnak rendelkezésre kell állnia a romboló teszt elvégzéséhez</span><span class="sxs-lookup"><span data-stu-id="db6e9-233">After the product receipt for the material that is received is posted, because the material must be available for destructive testing</span></span></td>
<td><span data-ttu-id="db6e9-234">A minőségi rendelés követelménye vonatkozhat egy adott telephelyre, cikkre vagy szállítóra, illetve ezek bármilyen kombinációjára.</span><span class="sxs-lookup"><span data-stu-id="db6e9-234">The requirement for a quality order can reflect a particular site, item, or vendor, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="db6e9-235">A beszerzési rendelésekhez manuálisan generált minőségi rendelésekben felhasználhatók a minőségi társítási rekordban szereplő adatok, például a mintavételezési eljárás.</span><span class="sxs-lookup"><span data-stu-id="db6e9-235">A manually generated quality order that refers to a purchase order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="db6e9-236">Karanténutasítás</span><span class="sxs-lookup"><span data-stu-id="db6e9-236">Quarantine order</span></span></td>
<td><span data-ttu-id="db6e9-237">Mielőtt vagy miután a karanténutasítás készként lett jelentve vagy befejeződött</span><span class="sxs-lookup"><span data-stu-id="db6e9-237">Before or after the quarantine order is reported as finished or ended</span></span></td>
<td><span data-ttu-id="db6e9-238">Romboló teszteket igénylő minőségi rendelések nem hozhatóak létre.</span><span class="sxs-lookup"><span data-stu-id="db6e9-238">Quality orders that require destructive tests can&#39;t be generated.</span></span> <span data-ttu-id="db6e9-239">A rendszer feltételezi, hogy a karanténutasítás funkció kezeli a roncsolt anyag elhelyezését.</span><span class="sxs-lookup"><span data-stu-id="db6e9-239">It&#39;s assumed that the quarantine order functionality handles the disposition of the material that is destroyed.</span></span></td>
<td><span data-ttu-id="db6e9-240">A minőségi rendelés követelménye vonatkozhat egy adott telephelyre, cikkre vagy szállítóra, illetve ezek bármilyen kombinációjára.</span><span class="sxs-lookup"><span data-stu-id="db6e9-240">The requirement for a quality order can reflect a particular site, item, or vendor, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="db6e9-241">A karanténutasításokhoz manuálisan generált minőségi rendelésekben felhasználhatók a minőségi társítási rekordban szereplő adatok, például a mintavételezési eljárás.</span><span class="sxs-lookup"><span data-stu-id="db6e9-241">A manually generated quality order that refers to a quarantine order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="db6e9-242">Értékesítési rendelés</span><span class="sxs-lookup"><span data-stu-id="db6e9-242">Sales order</span></span></td>
<td><span data-ttu-id="db6e9-243">A szállított cikkekre vonatkozó ütemezett kitárolási folyamat vagy szállítólevél frissítése előtt</span><span class="sxs-lookup"><span data-stu-id="db6e9-243">Before a scheduled picking process or packing slip update for the items that are being shipped</span></span></td>
<td><span data-ttu-id="db6e9-244">Bármelyik lépésnél</span><span class="sxs-lookup"><span data-stu-id="db6e9-244">At any step</span></span></td>
<td><span data-ttu-id="db6e9-245">A minőségi rendelés követelménye vonatkozhat egy adott telephelyre, cikkre vagy vevőre, illetve ezek bármilyen kombinációjára.</span><span class="sxs-lookup"><span data-stu-id="db6e9-245">The requirement for a quality order can reflect a particular site, item, or customer, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="db6e9-246">Az értékesítési rendelésekhez manuálisan generált minőségi rendelésekben felhasználhatók a minőségi társítási rekordban szereplő adatok, például a mintavételezési eljárás.</span><span class="sxs-lookup"><span data-stu-id="db6e9-246">A manually generated quality order that refers to a sales order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="db6e9-247">Termelési rendelés</span><span class="sxs-lookup"><span data-stu-id="db6e9-247">Production order</span></span></td>
<td><span data-ttu-id="db6e9-248">A termelési rendelés befejezett mennyiségének jelentése előtt vagy után</span><span class="sxs-lookup"><span data-stu-id="db6e9-248">Before or after the finished quantity for the production order is reported</span></span></td>
<td><span data-ttu-id="db6e9-249">A termelési rendelés befejezett mennyiségének jelentése után</span><span class="sxs-lookup"><span data-stu-id="db6e9-249">After the finished quantity for the production order is reported</span></span></td>
<td><span data-ttu-id="db6e9-250">A minőségi rendelés követelménye vonatkozhat egy adott telephelyre vagy vevőre, illetve ezek kombinációjára.</span><span class="sxs-lookup"><span data-stu-id="db6e9-250">The requirement for a quality order can reflect a particular site or item, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="db6e9-251">A termelési rendelésekhez manuálisan generált minőségi rendelésekben felhasználhatók a minőségi társítási rekordban szereplő adatok, például a mintavételezési eljárás.</span><span class="sxs-lookup"><span data-stu-id="db6e9-251">A manually generated quality order that refers to a production order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="db6e9-252">Útvonalművelettel rendelkező termelési utasítás</span><span class="sxs-lookup"><span data-stu-id="db6e9-252">Production order that has a route operation</span></span></td>
<td><span data-ttu-id="db6e9-253">A műveletre vonatkozó jelentés befejezése előtt vagy után</span><span class="sxs-lookup"><span data-stu-id="db6e9-253">Before or after the report is finished for an operation</span></span></td>
<td><span data-ttu-id="db6e9-254">Miután az utolsó művelet készként való jelentése megtörtént</span><span class="sxs-lookup"><span data-stu-id="db6e9-254">After the reporting production is finished for the last operation</span></span></td>
<td><span data-ttu-id="db6e9-255">A minőségi rendelés követelménye vonatkozhat egy adott telephelyre, cikkre, vevőre vagy üzemi erőforrásra, illetve ezek bármilyen kombinációjára.</span><span class="sxs-lookup"><span data-stu-id="db6e9-255">The requirement for a quality order can reflect a particular, site, item, or operations resource, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="db6e9-256">Az útvonalművelethez manuálisan generált minőségi rendelésekben felhasználhatók a minőségi társítási rekordban szereplő adatok, például a mintavételezési eljárás.</span><span class="sxs-lookup"><span data-stu-id="db6e9-256">A manually generated quality order that refers to a route operation can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="db6e9-257">Készlet</span><span class="sxs-lookup"><span data-stu-id="db6e9-257">Inventory</span></span></td>
<td><span data-ttu-id="db6e9-258">A készletnaplón belüli tranzakciókhoz és az átmozgatási rendelési tranzakciókhoz nem generálhatók automatikusan minőségi rendelések.</span><span class="sxs-lookup"><span data-stu-id="db6e9-258">A quality order cannot be automatically generated for a transaction in an inventory journal or for transfer order transactions.</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="db6e9-259">Cikk készletmennyiségére vonatkozó minőségi rendelést manuálisan kell létrehozni.</span><span class="sxs-lookup"><span data-stu-id="db6e9-259">A quality order must be created manually for an item&#39;s inventory quantity.</span></span> <span data-ttu-id="db6e9-260">Tényleges aktuális készlet szükséges.</span><span class="sxs-lookup"><span data-stu-id="db6e9-260">Physical on-hand inventory is required.</span></span></td>
</tr>
</tbody>
</table>

## <a name="quality-order-auto-generation-examples"></a><span data-ttu-id="db6e9-261">Minőségi rendelési automatikus generálásával kapcsolatos példák</span><span class="sxs-lookup"><span data-stu-id="db6e9-261">Quality order auto-generation examples</span></span>

### <a name="purchasing"></a><span data-ttu-id="db6e9-262">Beszerzés</span><span class="sxs-lookup"><span data-stu-id="db6e9-262">Purchasing</span></span>

<span data-ttu-id="db6e9-263">Ha a beszerzés modulban az **Eseménytípus** mezőt a **Termék nyugtája** értékre állítja, a **Végrehajtás** mezőt pedig **Után** értékre a **Minőségi társítások** lapon, akkor a következő eredményeket kapja:</span><span class="sxs-lookup"><span data-stu-id="db6e9-263">In purchasing, if you set the **Event type** field to **Product receipt** and the **Execution** field to **After** on the **Quality associations** page, you get the following results:</span></span> 

- <span data-ttu-id="db6e9-264">Ha a **Frissített mennyiség** beállítás **Igen** értékre van állítva , akkor a program minőségi rendelést hoz létre a beszerzési rendeléshez tartozó összes bevételezéshez, a bevételezett mennyiség és a cikkmintavétel beállításai alapján.</span><span class="sxs-lookup"><span data-stu-id="db6e9-264">If the **Per updated quantity** option is set to **Yes**, a quality order is generated for every receipt against the purchase order, based on the received quantity and settings in the item sampling.</span></span> <span data-ttu-id="db6e9-265">Minden alkalommal, amikor egy mennyiséget a beszerzési rendeléssel szemben megkapnak, új minőségi rendelések jönnek létre az újonnan megkapott mennyiség alapján.</span><span class="sxs-lookup"><span data-stu-id="db6e9-265">Every time that a quantity is received against the purchase order, new quality orders are generated based on the newly received quantity.</span></span>
- <span data-ttu-id="db6e9-266">Ha a **Frissített mennyiség** beállítás **Igen** értékre van állítva , akkor a program minőségi rendelést hoz létre a beszerzési rendeléshez tartozó első bevételezéshez, a bevételezett mennyiség és a cikkmintavétel beállításai alapján.</span><span class="sxs-lookup"><span data-stu-id="db6e9-266">If the **Per updated quantity** option is set to **No**, a quality order is generated for the first receipt against the purchase order, based on the received quantity.</span></span> <span data-ttu-id="db6e9-267">Ezenkívül a program egy vagy több minőségi rendelést hoz létre a fennmaradó mennyiség alapján, a nyomon követési dimenziók függvényében.</span><span class="sxs-lookup"><span data-stu-id="db6e9-267">Additionally, one or more quality orders are created based on the remaining quantity, depending on the tracking dimensions.</span></span> <span data-ttu-id="db6e9-268">Nem jönnek létre minőségi rendelések a beszerzési rendelés későbbi bevételezéseihez.</span><span class="sxs-lookup"><span data-stu-id="db6e9-268">Quality orders aren't generated for subsequent receipts against the purchase order.</span></span>

<table>
<tbody>
<tr>
<th><span data-ttu-id="db6e9-269">Minőség megadása</span><span class="sxs-lookup"><span data-stu-id="db6e9-269">Quality specification</span></span></th>
<th><span data-ttu-id="db6e9-270">Frissített mennyiségenként</span><span class="sxs-lookup"><span data-stu-id="db6e9-270">Per updated quantity</span></span></th>
<th><span data-ttu-id="db6e9-271">Nyomon követési dimenziónként</span><span class="sxs-lookup"><span data-stu-id="db6e9-271">Per tracking dimension</span></span></th>
<th><span data-ttu-id="db6e9-272">Eredmény</span><span class="sxs-lookup"><span data-stu-id="db6e9-272">Result</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="db6e9-273">Százalék: 10%</span><span class="sxs-lookup"><span data-stu-id="db6e9-273">Percentage: 10%</span></span></td>
<td><span data-ttu-id="db6e9-274">Igen</span><span class="sxs-lookup"><span data-stu-id="db6e9-274">Yes</span></span></td>
<td>
<p><span data-ttu-id="db6e9-275">Kötegszám: Nincs</span><span class="sxs-lookup"><span data-stu-id="db6e9-275">Batch number: No</span></span></p>
<p><span data-ttu-id="db6e9-276">Sorozatszám: Nincs</span><span class="sxs-lookup"><span data-stu-id="db6e9-276">Serial number: No</span></span></p>
</td>
<td>
<p><span data-ttu-id="db6e9-277">Rendelt mennyiség: 100</span><span class="sxs-lookup"><span data-stu-id="db6e9-277">Order quantity: 100</span></span></p>
<ol>
<li><span data-ttu-id="db6e9-278">Készként jelentés 30-hoz</span><span class="sxs-lookup"><span data-stu-id="db6e9-278">Report as finished for 30</span></span>
<ul>
<li><span data-ttu-id="db6e9-279">1. minőségi rendelés 3-hoz (A 30 10%-a)</span><span class="sxs-lookup"><span data-stu-id="db6e9-279">Quality order #1 for 3 (10% of 30)</span></span></li>
</ul>
</li>
<li><span data-ttu-id="db6e9-280">Készként jelentés 70-hoz</span><span class="sxs-lookup"><span data-stu-id="db6e9-280">Report as finished for 70</span></span>
<ul>
<li><span data-ttu-id="db6e9-281">2. minőségi rendelés 7-hez (a fennmaradó rendelési mennyiség 10%-a, amely ebben az esetben 70).</span><span class="sxs-lookup"><span data-stu-id="db6e9-281">Quality order #2 for 7 (10% of the remaining order quantity, which equals 70 in this case)</span></span></li>
</ul>
</li>
</ol>
</td>
</tr>
<tr>
<td><span data-ttu-id="db6e9-282">Rögzített mennyiség: 1</span><span class="sxs-lookup"><span data-stu-id="db6e9-282">Fixed quantity: 1</span></span></td>
<td><span data-ttu-id="db6e9-283">Nem</span><span class="sxs-lookup"><span data-stu-id="db6e9-283">No</span></span></td>
<td>
<p><span data-ttu-id="db6e9-284">Kötegszám: Nincs</span><span class="sxs-lookup"><span data-stu-id="db6e9-284">Batch number: No</span></span></p>
<p><span data-ttu-id="db6e9-285">Sorozatszám: Nincs</span><span class="sxs-lookup"><span data-stu-id="db6e9-285">Serial number: No</span></span></p>
</td>
<td><span data-ttu-id="db6e9-286">Rendelt mennyiség: 100</span><span class="sxs-lookup"><span data-stu-id="db6e9-286">Order quantity: 100</span></span>
<ol>
<li><span data-ttu-id="db6e9-287">Készként jelentés 30-hoz</span><span class="sxs-lookup"><span data-stu-id="db6e9-287">Report as finished for 30</span></span>
<ul>
<li><span data-ttu-id="db6e9-288">Az 1. minőségi rendelés 1-hez jön létre (az első jelentett kész mennyiséghez, amelynek rögzített értéke 1).</span><span class="sxs-lookup"><span data-stu-id="db6e9-288">Quality order #1 is created for 1 (for the first reported-as-finished quantity, which has a fixed value of 1).</span></span></li>
<li><span data-ttu-id="db6e9-289">Nem jön létre több minőségi rendelés a hátralévő mennyiséggel szemben.</span><span class="sxs-lookup"><span data-stu-id="db6e9-289">No more quality orders are created against the remaining quantity.</span></span></li>
</ul>
</li>
<li><span data-ttu-id="db6e9-290">Készként jelentés 10-hoz</span><span class="sxs-lookup"><span data-stu-id="db6e9-290">Report as finished for 10</span></span>
<ul>
<li><span data-ttu-id="db6e9-291">Nem jönnek létre minőségi rendelések.</span><span class="sxs-lookup"><span data-stu-id="db6e9-291">No quality orders are created.</span></span></li>
</ul>
</li>
<li><span data-ttu-id="db6e9-292">Készként jelentés 60-hoz</span><span class="sxs-lookup"><span data-stu-id="db6e9-292">Report as finished for 60</span></span>
<ul>
<li><span data-ttu-id="db6e9-293">Nem jönnek létre minőségi rendelések.</span><span class="sxs-lookup"><span data-stu-id="db6e9-293">No quality orders are created.</span></span></li>
</ul>
</li>
</ol>
</td>
</tr>
<tr>
<td><span data-ttu-id="db6e9-294">Rögzített mennyiség: 1</span><span class="sxs-lookup"><span data-stu-id="db6e9-294">Fixed quantity: 1</span></span></td>
<td><span data-ttu-id="db6e9-295">Igen</span><span class="sxs-lookup"><span data-stu-id="db6e9-295">Yes</span></span></td>
<td>
<p><span data-ttu-id="db6e9-296">Kötegszám: Igen</span><span class="sxs-lookup"><span data-stu-id="db6e9-296">Batch number: Yes</span></span></p>
<p><span data-ttu-id="db6e9-297">Sorozatszám: Igen</span><span class="sxs-lookup"><span data-stu-id="db6e9-297">Serial number: Yes</span></span></p>
</td>
<td>
<p><span data-ttu-id="db6e9-298">Rendelt mennyiség: 10</span><span class="sxs-lookup"><span data-stu-id="db6e9-298">Order quantity: 10</span></span></p>
<ol>
<li><span data-ttu-id="db6e9-299">Készként jelentés 3-hoz</span><span class="sxs-lookup"><span data-stu-id="db6e9-299">Report as finished for 3</span></span>
<ul>
<li><span data-ttu-id="db6e9-300">1. minőségi rendelés 1-hez, #b1 köteg, #s1 sorozat</span><span class="sxs-lookup"><span data-stu-id="db6e9-300">Quality order #1 for 1 of batch #b1, serial #s1</span></span></li>
<li><span data-ttu-id="db6e9-301">2. minőségi rendelés 1-hez, #b2 köteg, #s2 sorozat</span><span class="sxs-lookup"><span data-stu-id="db6e9-301">Quality order #2 for 1 of batch #b2, serial #s2</span></span></li>
<li><span data-ttu-id="db6e9-302">3. minőségi rendelés 1-hez, #b3 köteg, #s3 sorozat</span><span class="sxs-lookup"><span data-stu-id="db6e9-302">Quality order #3 for 1 of batch #b3, serial #s3</span></span></li>
</ul>
</li>
<li><span data-ttu-id="db6e9-303">Készként jelentés 2-hoz</span><span class="sxs-lookup"><span data-stu-id="db6e9-303">Report as finished for 2</span></span>
<ul>
<li><span data-ttu-id="db6e9-304">4. minőségi rendelés 1-hez, #b4 köteg, #s4 sorozat</span><span class="sxs-lookup"><span data-stu-id="db6e9-304">Quality order #4 for 1 of batch #b4, serial #s4</span></span></li>
<li><span data-ttu-id="db6e9-305">5. minőségi rendelés 1-hez, #b5 köteg, #s5 sorozat</span><span class="sxs-lookup"><span data-stu-id="db6e9-305">Quality order #5 for 1 of batch #b5, serial #s5</span></span></li>
</ul>
</li>
</ol>
<p><span data-ttu-id="db6e9-306"><strong>Megjegyzés:</strong> A köteg újra felhasználható.</span><span class="sxs-lookup"><span data-stu-id="db6e9-306"><strong>Note:</strong> The batch can be reused.</span></span></p>
</td>
</tr>
<tr>
<td><span data-ttu-id="db6e9-307">Rögzített mennyiség: 2</span><span class="sxs-lookup"><span data-stu-id="db6e9-307">Fixed quantity: 2</span></span></td>
<td><span data-ttu-id="db6e9-308">Nem</span><span class="sxs-lookup"><span data-stu-id="db6e9-308">No</span></span></td>
<td>
<p><span data-ttu-id="db6e9-309">Kötegszám: Igen</span><span class="sxs-lookup"><span data-stu-id="db6e9-309">Batch number: Yes</span></span></p>
<p><span data-ttu-id="db6e9-310">Sorozatszám: Igen</span><span class="sxs-lookup"><span data-stu-id="db6e9-310">Serial number: Yes</span></span></p>
</td>
<td>
<p><span data-ttu-id="db6e9-311">Rendelt mennyiség: 10</span><span class="sxs-lookup"><span data-stu-id="db6e9-311">Order quantity: 10</span></span></p>
<ol>
<li><span data-ttu-id="db6e9-312">Készként jelentés 4-hoz</span><span class="sxs-lookup"><span data-stu-id="db6e9-312">Report as finished for 4</span></span>
<ul>
<li><span data-ttu-id="db6e9-313">1. minőségi rendelés 1-hez, #b1 köteg, #s1 sorozat.</span><span class="sxs-lookup"><span data-stu-id="db6e9-313">Quality order #1 for 1 of batch #b1, serial #s1.</span></span></li>
<li><span data-ttu-id="db6e9-314">2. minőségi rendelés 1-hez, #b2 köteg, #s2 sorozat.</span><span class="sxs-lookup"><span data-stu-id="db6e9-314">Quality order #2 for 1 of batch #b2, serial #s2.</span></span></li>
<li><span data-ttu-id="db6e9-315">3. minőségi rendelés 1-hez, #b3 köteg, #s3 sorozat.</span><span class="sxs-lookup"><span data-stu-id="db6e9-315">Quality order #3 for 1 of batch #b3, serial #s3.</span></span></li>
<li><span data-ttu-id="db6e9-316">4. minőségi rendelés 1-hez, #b4 köteg, #s4 sorozat.</span><span class="sxs-lookup"><span data-stu-id="db6e9-316">Quality order #4 for 1 of batch #b4, serial #s4.</span></span></li>
<li><span data-ttu-id="db6e9-317">Nem jön létre több minőségi rendelés a hátralévő mennyiséggel szemben.</span><span class="sxs-lookup"><span data-stu-id="db6e9-317">No more quality orders are created against the remaining quantity.</span></span></li>
</ul>
</li>
<li><span data-ttu-id="db6e9-318">Készként jelentés 6-hoz</span><span class="sxs-lookup"><span data-stu-id="db6e9-318">Report as finished for 6</span></span>
<ul>
<li><span data-ttu-id="db6e9-319">Nem jönnek létre minőségi rendelések.</span><span class="sxs-lookup"><span data-stu-id="db6e9-319">No quality orders are created.</span></span></li>
</ul>
</li>
</ol>
</td>
</tr>
</tbody>
</table>

### <a name="production"></a><span data-ttu-id="db6e9-320">Termelés</span><span class="sxs-lookup"><span data-stu-id="db6e9-320">Production</span></span>

<span data-ttu-id="db6e9-321">Ha a gyártásban az **Eseménytípus** mezőt a **Befejezettnek jelentés** értékre állítja, a **Végrehajtás** mezőt pedig **Után** értékre a **Minőségi társítások** lapon, akkor a következő eredményeket kapja:</span><span class="sxs-lookup"><span data-stu-id="db6e9-321">In production, if you set the **Event type** field to **Report as finished** and the **Execution** field to **After** on the **Quality associations** page, you get the following results:</span></span>

- <span data-ttu-id="db6e9-322">Ha a **Frissített mennyiség** beállítás **Igen** értékre van állítva , akkor a program minőségi rendelést hoz létre minden befejezett mennyiség és a cikkmintavételezés beállításai alapján.</span><span class="sxs-lookup"><span data-stu-id="db6e9-322">If the **Per updated quantity** option is set to **Yes**, a quality order is generated based on every finished quantity and settings in the item sampling.</span></span> <span data-ttu-id="db6e9-323">Minden alkalommal, amikor egy mennyiséget a beszerzési rendeléssel szemben késznek jelentenek, új minőségi rendelések jönnek létre az újonnan elkészült mennyiség alapján.</span><span class="sxs-lookup"><span data-stu-id="db6e9-323">Every time that a quantity is reported as finished against the production order, new quality orders are generated based on newly finished quantity.</span></span> <span data-ttu-id="db6e9-324">Ez a generálási logika összhangban van a beszerzéssel.</span><span class="sxs-lookup"><span data-stu-id="db6e9-324">This generation logic is consistent with purchasing.</span></span>
- <span data-ttu-id="db6e9-325">Ha a **Frissített mennyiség** beállítás **Igen** értékre van állítva , akkor a program minőségi rendelést hoz létre az első alkalommal, amikor a mennyiség készek van jelentve, a kész mennyiség és a cikkmintavétel beállításai alapján.</span><span class="sxs-lookup"><span data-stu-id="db6e9-325">If the **Per updated quantity** option is set to **No**, a quality order is generated the first time that a quantity is reported as finished, based on the finished quantity.</span></span> <span data-ttu-id="db6e9-326">Ezenkívül a program egy vagy több minőségi rendelést hoz létre a fennmaradó mennyiség alapján, a cikkmintavételezés nyomon követési dimenziói függvényében.</span><span class="sxs-lookup"><span data-stu-id="db6e9-326">Additionally, one or more quality orders are created based on the remaining quantity, depending on the tracking dimensions of the item sampling.</span></span> <span data-ttu-id="db6e9-327">A további kész mennyiségek esetében nem jönnek létre minőségi rendelések.</span><span class="sxs-lookup"><span data-stu-id="db6e9-327">Quality orders aren't generated for subsequent finished quantities.</span></span>

<table>
<tbody>
<tr>
<th><span data-ttu-id="db6e9-328">Minőség megadása</span><span class="sxs-lookup"><span data-stu-id="db6e9-328">Quality specification</span></span></th>
<th><span data-ttu-id="db6e9-329">Frissített mennyiségenként</span><span class="sxs-lookup"><span data-stu-id="db6e9-329">Per updated quantity</span></span></th>
<th><span data-ttu-id="db6e9-330">Nyomon követési dimenziónként</span><span class="sxs-lookup"><span data-stu-id="db6e9-330">Per tracking dimension</span></span></th>
<th><span data-ttu-id="db6e9-331">Eredmény</span><span class="sxs-lookup"><span data-stu-id="db6e9-331">Result</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="db6e9-332">Százalék: 10%</span><span class="sxs-lookup"><span data-stu-id="db6e9-332">Percentage: 10%</span></span></td>
<td><span data-ttu-id="db6e9-333">Igen</span><span class="sxs-lookup"><span data-stu-id="db6e9-333">Yes</span></span></td>
<td>
<p><span data-ttu-id="db6e9-334">Kötegszám: Nincs</span><span class="sxs-lookup"><span data-stu-id="db6e9-334">Batch number: No</span></span></p>
<p><span data-ttu-id="db6e9-335">Sorozatszám: Nincs</span><span class="sxs-lookup"><span data-stu-id="db6e9-335">Serial number: No</span></span></p>
</td>
<td>
<p><span data-ttu-id="db6e9-336">Rendelt mennyiség: 100</span><span class="sxs-lookup"><span data-stu-id="db6e9-336">Order quantity: 100</span></span></p>
<ol>
<li><span data-ttu-id="db6e9-337">Készként jelentés 30-hoz</span><span class="sxs-lookup"><span data-stu-id="db6e9-337">Report as finished for 30</span></span>
<ul>
<li><span data-ttu-id="db6e9-338">1. minőségi rendelés 3-hoz (A 30 10%-a)</span><span class="sxs-lookup"><span data-stu-id="db6e9-338">Quality order #1 for 3 (10% of 30)</span></span></li>
</ul>
</li>
<li><span data-ttu-id="db6e9-339">Készként jelentés 70-hoz</span><span class="sxs-lookup"><span data-stu-id="db6e9-339">Report as finished for 70</span></span>
<ul>
<li><span data-ttu-id="db6e9-340">2. minőségi rendelés 7-hez (a fennmaradó rendelési mennyiség 10%-a, amely ebben az esetben 70).</span><span class="sxs-lookup"><span data-stu-id="db6e9-340">Quality order #2 for 7 (10% of the remaining order quantity, which equals 70 in this case)</span></span></li>
</ul>
</li>
</ol>
</td>
</tr>
<tr>
<td><span data-ttu-id="db6e9-341">Rögzített mennyiség: 1</span><span class="sxs-lookup"><span data-stu-id="db6e9-341">Fixed quantity: 1</span></span></td>
<td><span data-ttu-id="db6e9-342">Nem</span><span class="sxs-lookup"><span data-stu-id="db6e9-342">No</span></span></td>
<td>
<p><span data-ttu-id="db6e9-343">Kötegszám: Nincs</span><span class="sxs-lookup"><span data-stu-id="db6e9-343">Batch number: No</span></span></p>
<p><span data-ttu-id="db6e9-344">Sorozatszám: Nincs</span><span class="sxs-lookup"><span data-stu-id="db6e9-344">Serial number: No</span></span></p>
</td>
<td><span data-ttu-id="db6e9-345">Rendelt mennyiség: 100</span><span class="sxs-lookup"><span data-stu-id="db6e9-345">Order quantity: 100</span></span>
<ol>
<li><span data-ttu-id="db6e9-346">Készként jelentés 30-hoz</span><span class="sxs-lookup"><span data-stu-id="db6e9-346">Report as finished for 30</span></span>
<ul>
<li><span data-ttu-id="db6e9-347">Az 1. minőségi rendelés 1-hez lesz létrehozva (az első jelentett kész mennyiséghez, amelynek rögzített értéke 1)</span><span class="sxs-lookup"><span data-stu-id="db6e9-347">Quality order #1 for 1 (for the first reported-as-finished quantity, which has a fixed value of 1)</span></span></li>
<li><span data-ttu-id="db6e9-348">Az 2. minőségi rendelés 1-hez lesz létrehozva (a fennmaradó mennyiséghez, amelynek rögzített értéke 1)</span><span class="sxs-lookup"><span data-stu-id="db6e9-348">Quality order #2 for 1 (for the remaining quantity, which still has a fixed value of 1)</span></span></li>
</ul>
</li>
<li><span data-ttu-id="db6e9-349">Készként jelentés 10-hoz</span><span class="sxs-lookup"><span data-stu-id="db6e9-349">Report as finished for 10</span></span>
<ul>
<li><span data-ttu-id="db6e9-350">Nem jönnek létre minőségi rendelések.</span><span class="sxs-lookup"><span data-stu-id="db6e9-350">No quality orders are created.</span></span></li>
</ul>
</li>
<li><span data-ttu-id="db6e9-351">Készként jelentés 60-hoz</span><span class="sxs-lookup"><span data-stu-id="db6e9-351">Report as finished for 60</span></span>
<ul>
<li><span data-ttu-id="db6e9-352">Nem jönnek létre minőségi rendelések.</span><span class="sxs-lookup"><span data-stu-id="db6e9-352">No quality orders are created.</span></span></li>
</ul>
</li>
</ol>
</td>
</tr>
<tr>
<td><span data-ttu-id="db6e9-353">Rögzített mennyiség: 1</span><span class="sxs-lookup"><span data-stu-id="db6e9-353">Fixed quantity: 1</span></span></td>
<td><span data-ttu-id="db6e9-354">Igen</span><span class="sxs-lookup"><span data-stu-id="db6e9-354">Yes</span></span></td>
<td>
<p><span data-ttu-id="db6e9-355">Kötegszám: Igen</span><span class="sxs-lookup"><span data-stu-id="db6e9-355">Batch number: Yes</span></span></p>
<p><span data-ttu-id="db6e9-356">Sorozatszám: Igen</span><span class="sxs-lookup"><span data-stu-id="db6e9-356">Serial number: Yes</span></span></p>
</td>
<td>
<p><span data-ttu-id="db6e9-357">Rendelt mennyiség: 10</span><span class="sxs-lookup"><span data-stu-id="db6e9-357">Order quantity: 10</span></span></p>
<ol>
<li><span data-ttu-id="db6e9-358">Készként jelentve 3:1 #b1-hez, #s1-hez; 1 #b2-höz, #s2-höz; és 1 #b3-hoz, #s3-hoz</span><span class="sxs-lookup"><span data-stu-id="db6e9-358">Report as finished for 3: 1 for #b1, #s1; 1 for #b2, #s2; and 1 for #b3, #s3</span></span>
<ul>
<li><span data-ttu-id="db6e9-359">1. minőségi rendelés 1-hez, #b1 köteg, #s1 sorozat</span><span class="sxs-lookup"><span data-stu-id="db6e9-359">Quality order #1 for 1 of batch #b1, serial #s1</span></span></li>
<li><span data-ttu-id="db6e9-360">2. minőségi rendelés 1-hez, #b2 köteg, #s2 sorozat</span><span class="sxs-lookup"><span data-stu-id="db6e9-360">Quality order #2 for 1 of batch #b2, serial #s2</span></span></li>
<li><span data-ttu-id="db6e9-361">3. minőségi rendelés 1-hez, #b3 köteg, #s3 sorozat</span><span class="sxs-lookup"><span data-stu-id="db6e9-361">Quality order #3 for 1 of batch #b3, serial #s3</span></span></li>
</ul>
</li>
<li><span data-ttu-id="db6e9-362">Készként jelentve a 2:1 #b4-hez, #s4-hez; és 1 #b5-höz, #s5-höz</span><span class="sxs-lookup"><span data-stu-id="db6e9-362">Report as finished for 2: 1 for #b4, #s4; and 1 for #b5, #s5</span></span>
<ul>
<li><span data-ttu-id="db6e9-363">4. minőségi rendelés 1-hez, #b4 köteg, #s4 sorozat</span><span class="sxs-lookup"><span data-stu-id="db6e9-363">Quality order #4 for 1 of batch #b4, serial #s4</span></span></li>
<li><span data-ttu-id="db6e9-364">5. minőségi rendelés 1-hez, #b5 köteg, #s5 sorozat</span><span class="sxs-lookup"><span data-stu-id="db6e9-364">Quality order #5 for 1 of batch #b5, serial #s5</span></span></li>
</ul>
</li>
</ol>
<p><span data-ttu-id="db6e9-365"><strong>Megjegyzés:</strong> A köteg újra felhasználható.</span><span class="sxs-lookup"><span data-stu-id="db6e9-365"><strong>Note:</strong> The batch can be reused.</span></span></p>
</td>
</tr>
<tr>
<td><span data-ttu-id="db6e9-366">Rögzített mennyiség: 2</span><span class="sxs-lookup"><span data-stu-id="db6e9-366">Fixed quantity: 2</span></span></td>
<td><span data-ttu-id="db6e9-367">Nem</span><span class="sxs-lookup"><span data-stu-id="db6e9-367">No</span></span></td>
<td>
<p><span data-ttu-id="db6e9-368">Kötegszám: Igen</span><span class="sxs-lookup"><span data-stu-id="db6e9-368">Batch number: Yes</span></span></p>
<p><span data-ttu-id="db6e9-369">Sorozatszám: Igen</span><span class="sxs-lookup"><span data-stu-id="db6e9-369">Serial number: Yes</span></span></p>
</td>
<td>
<p><span data-ttu-id="db6e9-370">Rendelt mennyiség: 10</span><span class="sxs-lookup"><span data-stu-id="db6e9-370">Order quantity: 10</span></span></p>
<ol>
<li><span data-ttu-id="db6e9-371">Készként jelentve 4:1 #b1-hez, #s1-hez; 1 #b2-höz, #s2-höz; és 1 #b3-hoz, #s3-hoz és 1 #b4-hez, #s4-hez</span><span class="sxs-lookup"><span data-stu-id="db6e9-371">Report as finished for 4: 1 for #b1, #s1; 1 for #b2, #s2; 1 for #b3, #s3; and 1 for #b4, #s4</span></span>
<ul>
<li><span data-ttu-id="db6e9-372">1. minőségi rendelés 1-hez, #b1 köteg, #s1 sorozat</span><span class="sxs-lookup"><span data-stu-id="db6e9-372">Quality order #1 for 1 of batch #b1, serial #s1</span></span></li>
<li><span data-ttu-id="db6e9-373">2. minőségi rendelés 1-hez, #b2 köteg, #s2 sorozat</span><span class="sxs-lookup"><span data-stu-id="db6e9-373">Quality order #2 for 1 of batch #b2, serial #s2</span></span></li>
<li><span data-ttu-id="db6e9-374">3. minőségi rendelés 1-hez, #b3 köteg, #s3 sorozat</span><span class="sxs-lookup"><span data-stu-id="db6e9-374">Quality order #3 for 1 of batch #b3, serial #s3</span></span></li>
<li><span data-ttu-id="db6e9-375">4. minőségi rendelés 1-hez, #b4 köteg, #s4 sorozat</span><span class="sxs-lookup"><span data-stu-id="db6e9-375">Quality order #4 for 1 of batch #b4, serial #s4</span></span></li>
</ul>
<ul>
<li><span data-ttu-id="db6e9-376">Minőségi rendelés #5 2-höz, egy kötegre és egy sorozatszámra való hivatkozás nélkül</span><span class="sxs-lookup"><span data-stu-id="db6e9-376">Quality order #5 for 2, without a reference to a batch and a serial number</span></span></li>
</ul>
</li>
<li><span data-ttu-id="db6e9-377">Készként jelentve a 6: 1 #b5-höz, #s5-höz; 1 #b6-hoz, #s6-hoz; 1 #b7-hez, #s7-hez; 1 #b8-hoz, #s8-hoz; 1 #b9-hez, #s9-hez; és 1 #b10-hez, #s10-hez</span><span class="sxs-lookup"><span data-stu-id="db6e9-377">Report as finished for 6: 1 for #b5, #s5; 1 for #b6, #s6; 1 for #b7, #s7; 1 for #b8, #s8; 1 for #b9, #s9; and 1 for #b10, #s10</span></span>
<ul>
<li><span data-ttu-id="db6e9-378">Nem jönnek létre minőségi rendelések.</span><span class="sxs-lookup"><span data-stu-id="db6e9-378">No quality orders are created.</span></span></li>
</ul>
</li>
</ol>
</td>
</tr>
</tbody>
</table>

## <a name="quality-management-pages"></a><span data-ttu-id="db6e9-379">A Minőségkezelés oldalai</span><span class="sxs-lookup"><span data-stu-id="db6e9-379">Quality management pages</span></span>
<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="db6e9-380">Oldal</span><span class="sxs-lookup"><span data-stu-id="db6e9-380">Page</span></span></th>
<th><span data-ttu-id="db6e9-381">Leírás</span><span class="sxs-lookup"><span data-stu-id="db6e9-381">Description</span></span></th>
<th><span data-ttu-id="db6e9-382">Példa</span><span class="sxs-lookup"><span data-stu-id="db6e9-382">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="db6e9-383">Minőségi társítások</span><span class="sxs-lookup"><span data-stu-id="db6e9-383">Quality associations</span></span></td>
<td><span data-ttu-id="db6e9-384">Lásd a cikk előző szakaszait.</span><span class="sxs-lookup"><span data-stu-id="db6e9-384">See the previous sections of this article.</span></span></td>
<td><span data-ttu-id="db6e9-385">A minőségi társítás meghatározza a létrehozott minőségi rendelésre vonatkozó alábbi adatok mindegyikét:</span><span class="sxs-lookup"><span data-stu-id="db6e9-385">A quality association defines all the following information for a quality order that is generated:</span></span>
<ul>
<li><span data-ttu-id="db6e9-386">Tranzakcióesemény</span><span class="sxs-lookup"><span data-stu-id="db6e9-386">The transaction event</span></span></li>
<li><span data-ttu-id="db6e9-387">A cikkeken elvégzendő tesztek</span><span class="sxs-lookup"><span data-stu-id="db6e9-387">The set of tests that must be performed on the items</span></span></li>
<li><span data-ttu-id="db6e9-388">Elfogadható minőségi szint</span><span class="sxs-lookup"><span data-stu-id="db6e9-388">The AQL</span></span></li>
<li><span data-ttu-id="db6e9-389">Mintavételi terv</span><span class="sxs-lookup"><span data-stu-id="db6e9-389">The sampling plan</span></span></li>
</ul>
<span data-ttu-id="db6e9-390">Definiálnia kell egy minőségi társítást az üzleti folyamat minden olyan változatához, ahol minőségi rendelés automatikus létrehozása szükséges.</span><span class="sxs-lookup"><span data-stu-id="db6e9-390">You must define a quality association for each variation in a business process that requires automatic generation of quality orders.</span></span> <span data-ttu-id="db6e9-391">Minőségi rendelés létrehozható például az üzleti folyamatokban beszerzési rendelésekhez, karanténutasításokhoz, értékesítési rendelésekhez és termelési rendelésekhez.</span><span class="sxs-lookup"><span data-stu-id="db6e9-391">For example, a quality order can be generated in the business processes for purchase orders, quarantine orders, sales orders, and production orders.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="db6e9-392">Tesztek</span><span class="sxs-lookup"><span data-stu-id="db6e9-392">Tests</span></span></td>
<td><span data-ttu-id="db6e9-393">Ezen az oldalon lehet meghatározni és megtekinteni azokat a teszteket, amelyekkel megállapítható, hogy a termékek megfelelnek-e a minőségi specifikációknak.</span><span class="sxs-lookup"><span data-stu-id="db6e9-393">Use this page to define and view the individual tests that determine whether your products meet quality specifications.</span></span> <span data-ttu-id="db6e9-394">Hozzárendelhet egy vagy több különálló tesztet egy tesztcsoporthoz.</span><span class="sxs-lookup"><span data-stu-id="db6e9-394">You can assign one or more individual tests to a test group.</span></span> <span data-ttu-id="db6e9-395">Ebben az esetben tesztspecifikus adatokat is megadhat, például az elfogadható mérési értékeket.</span><span class="sxs-lookup"><span data-stu-id="db6e9-395">In this case, you also specify test-specific information, such as the acceptable measurement values.</span></span> <span data-ttu-id="db6e9-396">Mennyiségi tesztekhez mérési értékek, minőségi tesztekhez pedig tesztváltozók használhatók.</span><span class="sxs-lookup"><span data-stu-id="db6e9-396">Measurement values are used for quantitative tests, and test variables are used for qualitative tests.</span></span>
<ul>
<li><span data-ttu-id="db6e9-397">Egy mennyiségi teszt teszttípusa <strong>Egész</strong> vagy <strong>Tört</strong> lehet, és egy kijelölt mértékegység is tartozik hozzá.</span><span class="sxs-lookup"><span data-stu-id="db6e9-397">A quantitative test has a test type of <strong>Integer</strong> or <strong>Fraction</strong>, and also has a designated unit of measure.</span></span> <span data-ttu-id="db6e9-398">A minőségi specifikációk és a teszteredmények számokként fejeződnek ki.</span><span class="sxs-lookup"><span data-stu-id="db6e9-398">Quality specifications and test results are expressed as numbers.</span></span></li>
<li><span data-ttu-id="db6e9-399">A minőségi tesztek teszttípusa: <strong>Lehetőség</strong>.</span><span class="sxs-lookup"><span data-stu-id="db6e9-399">A qualitative test has a test type of <strong>Option</strong>.</span></span> <span data-ttu-id="db6e9-400">A minőségi tesztekhez további, a mérendő tesztváltozóra és annak sorszámozott lehetőségeire vonatkozó adatok szükségesek.</span><span class="sxs-lookup"><span data-stu-id="db6e9-400">Qualitative tests require additional information about the test variable that is being measured and its enumerated options.</span></span> <span data-ttu-id="db6e9-401">A minőségi specifikációk és a teszteredmények egy eredménynek megfelelően fejeződnek ki.</span><span class="sxs-lookup"><span data-stu-id="db6e9-401">Quality specifications and test results are expressed according to an outcome.</span></span></li>
</ul></td>
<td><span data-ttu-id="db6e9-402">Egy gyártóvállalat a beszerzett anyagon két tesztet végez el: ezek egyike az anyagminőséggel kapcsolatos mennyiségi teszt, a másik pedig a csomagolási sérüléseket felmérő minőségi teszt.</span><span class="sxs-lookup"><span data-stu-id="db6e9-402">A manufacturing company performs two tests on purchased material: a quantitative test about material quality and a qualitative test about packaging damage.</span></span> <span data-ttu-id="db6e9-403">A vállalat további adatokat ad meg a kvalitatív tesztre vonatkozóan, hogy meghatározza a tesztváltozót (sérült csomagolás) és annak kimeneteleit.</span><span class="sxs-lookup"><span data-stu-id="db6e9-403">The company defines additional information about the qualitative test to identify the test variable (damaged packaging) and its outcomes.</span></span> <span data-ttu-id="db6e9-404">A vállalat a <strong>Tesztcsoportok</strong> oldalon hozzárendeli a két tesztet egy tesztcsoporthoz és megadja a tesztspecifikus adatokat.</span><span class="sxs-lookup"><span data-stu-id="db6e9-404">The company uses the <strong>Test groups</strong> page to assign the two tests to a test group and to specify the test-specific information.</span></span> <span data-ttu-id="db6e9-405">A tesztcsoportot hozzárendeli egy minőségi rendeléshez, hogy a két teszt eredményét jelenteni tudja.</span><span class="sxs-lookup"><span data-stu-id="db6e9-405">The test group is assigned to a quality order, so that the company can report test results for the two tests.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="db6e9-406">Tesztcsoportok</span><span class="sxs-lookup"><span data-stu-id="db6e9-406">Test groups</span></span></td>
<td><span data-ttu-id="db6e9-407">Ezen az oldalon lehet beállítani, módosítani és megtekinteni a tesztcsoportokat és a tesztcsoportokhoz rendelt különálló teszteket.</span><span class="sxs-lookup"><span data-stu-id="db6e9-407">Use this page to set up, edit, and view test groups and the individual tests that are assigned to a test group.</span></span> <span data-ttu-id="db6e9-408">A felső ablak jeleníti meg a tesztcsoportokat, míg az alsó ablakban láthatók a kiválasztott tesztcsoporthoz tartozó tesztek.</span><span class="sxs-lookup"><span data-stu-id="db6e9-408">The upper pane displays test groups, and the lower pane displays the tests that are assigned to a selected test group.</span></span> <span data-ttu-id="db6e9-409">Egy tesztcsoporthoz több szabályt is hozzá lehet rendelni, például mintavételi tervet, elfogadható minőségi szintet, valamint a romboló teszt követelményét.</span><span class="sxs-lookup"><span data-stu-id="db6e9-409">You assign several policies to a test group, such as a sampling plan, an AQL, and the requirement for destructive testing.</span></span> <span data-ttu-id="db6e9-410">Amikor hozzárendel egy különálló tesztet egy tesztcsoporthoz, további adatokat definiálhat, például sorrendet, dokumentumokat és érvényességi dátumokat.</span><span class="sxs-lookup"><span data-stu-id="db6e9-410">When you assign an individual test to a test group, you define additional information, such as the sequence, documents, and validity dates.</span></span> <span data-ttu-id="db6e9-411">Mennyiségi teszt esetén a megadott adatok az elfogadható mérési értékeket is tartalmazzák.</span><span class="sxs-lookup"><span data-stu-id="db6e9-411">For a quantitative test, the information that you define also includes the acceptable measurement values.</span></span> <span data-ttu-id="db6e9-412">Minőségi teszt esetén az adatok a tesztváltozót és az alapértelmezett eredményt tartalmazzák.</span><span class="sxs-lookup"><span data-stu-id="db6e9-412">For a qualitative test, the information includes the test variable and default outcome.</span></span> <span data-ttu-id="db6e9-413">A minőségi rendelésekhez rendelt tesztcsoport meghatározza azokat az alapértelmezett teszteket, amelyeket az adott cikken végre kell hajtani.</span><span class="sxs-lookup"><span data-stu-id="db6e9-413">The test group that is assigned to a quality order defines the default set of tests that must be performed on the specified item.</span></span> <span data-ttu-id="db6e9-414">Azonban hozzáadhat, törölhet, vagy módosíthat adott minőségi rendelésre vonatkozó teszteket.</span><span class="sxs-lookup"><span data-stu-id="db6e9-414">However, you can add, delete, or change tests on the quality order.</span></span> <span data-ttu-id="db6e9-415">A minőségi rendelés keretében végzett mindegyik tesztnél megtörténik a teszteredmények jelentése.</span><span class="sxs-lookup"><span data-stu-id="db6e9-415">Test results are reported for each test on a quality order.</span></span></td>
<td><span data-ttu-id="db6e9-416">Egy gyártóvállalat minőségi irányelveinek minden variációjához meghatároz egy-egy tesztcsoportot.</span><span class="sxs-lookup"><span data-stu-id="db6e9-416">A manufacturing company defines a test group for each variation of its quality guidelines.</span></span> <span data-ttu-id="db6e9-417">A különböző tesztcsoportok tükrözik a mintavételi tervek, az együttesen végrehajtandó tesztsorok, az elfogadható mérési értékek, az elfogadható minőségi szint és egyéb tényezők eltéréseit.</span><span class="sxs-lookup"><span data-stu-id="db6e9-417">The various test groups reflect differences in the sampling plans, the sets of tests that must be performed together, the AQL, and other factors.</span></span> <span data-ttu-id="db6e9-418">Mennyiségi teszt esetén az elfogadható mérési értékekben is van különbség.</span><span class="sxs-lookup"><span data-stu-id="db6e9-418">For quantitative tests, there are also differences in the acceptable measurement values.</span></span> <span data-ttu-id="db6e9-419">A minőségi irányelveinek érvényesítése érdekében a vállalat minden egyes, minőségi rendeléseket automatikusan generáló szabályhoz a <strong>Minőségi társítások</strong> oldalon hozzárendel egy tesztcsoportot, valamint a manuálisan létrehozott minőségi rendelésekhez is hozzárendel egy tesztcsoportot.</span><span class="sxs-lookup"><span data-stu-id="db6e9-419">To enforce its quality guidelines, the company assigns a test group to each rule for automatically generating quality orders on the <strong>Quality associations</strong> page, and also assigns a test group to quality orders that are manually created.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="db6e9-420">Cikkminőségi csoportok</span><span class="sxs-lookup"><span data-stu-id="db6e9-420">Item quality groups</span></span></td>
<td><span data-ttu-id="db6e9-421">Ezen az oldalon a minőségi csoporthoz rendelt cikkeket, illetve a cikkhez rendelt minőségi csoportokat lehet beállítani, módosítani és megtekinteni.</span><span class="sxs-lookup"><span data-stu-id="db6e9-421">Use this page to set up, edit, and view the items that are assigned to a quality group or the quality groups that are assigned to an item.</span></span> <span data-ttu-id="db6e9-422">A minőségi csoport a cikkekre vonatkozó közös tesztkövetelményeket képvisel.</span><span class="sxs-lookup"><span data-stu-id="db6e9-422">A quality group represents common testing requirements for items.</span></span> <span data-ttu-id="db6e9-423">Miután a <strong>Tesztcsoportok</strong> oldalon definiálta a tesztkövetelményeket, meghatározhatja a minőségi rendelések automatikus létrehozásának szabályait.</span><span class="sxs-lookup"><span data-stu-id="db6e9-423">After you define the test requirements on the <strong>Test groups</strong> page, you can define the rules for automatically generating quality orders.</span></span> <span data-ttu-id="db6e9-424">A folyamat egyszerűsítése érdekében az egyes cikkekhez tartozó szabályokat nem definiáljuk.</span><span class="sxs-lookup"><span data-stu-id="db6e9-424">To simplify the process, you don&#39;t define rules for individual items.</span></span> <span data-ttu-id="db6e9-425">Ehelyett egy minőségi csoportra vonatkozó szabályokat definiálhatunk a <strong>Minőségi társítások</strong> oldalon.</span><span class="sxs-lookup"><span data-stu-id="db6e9-425">Instead, you define rules for a quality group, by using the <strong>Quality associations</strong> page.</span></span> <span data-ttu-id="db6e9-426">Emellett egy kiválasztott minőségi csoporthoz tartozó <strong>Cikkminőségi csoportok</strong> oldal is használható arra, hogy megfelelő cikkeket az adott csoporthoz rendeljünk.</span><span class="sxs-lookup"><span data-stu-id="db6e9-426">You can also use the <strong>Item quality groups</strong> page for a selected quality group to assign relevant items to that group.</span></span> <span data-ttu-id="db6e9-427">Emellett egy kiválasztott cikkhez tartozó <strong>Cikkminőségi csoportok</strong> oldal is használható arra, hogy megfelelő minőségi csoportokat az adott cikkhez rendeljünk.</span><span class="sxs-lookup"><span data-stu-id="db6e9-427">You can also use the <strong>Item quality groups</strong> page for a selected item to assign relevant quality groups to that item.</span></span></td>
<td><span data-ttu-id="db6e9-428">Egy gyártóvállalat több nyersanyagot is vásárol, amelyeknél a beérkezéskor szükséges vizsgálatokra ugyanazok a tesztkövetelmények vonatkoznak.</span><span class="sxs-lookup"><span data-stu-id="db6e9-428">A manufacturing company purchases various raw materials that have the same testing requirements for incoming inspection.</span></span> <span data-ttu-id="db6e9-429">A vállalat definiál egy minőségi csoportot, majd hozzárendeli a nyersanyagokhoz társított cikkszámokat a csoporthoz.</span><span class="sxs-lookup"><span data-stu-id="db6e9-429">The company defines a quality group and then assigns the item numbers that are associated with the raw materials to that group.</span></span> <span data-ttu-id="db6e9-430">Később a vállalat egy új típusú nyersanyagot vásárol, amelyre az előzőekkel azonos tesztkövetelmények vonatkoznak.</span><span class="sxs-lookup"><span data-stu-id="db6e9-430">Later, the company purchases a new type of raw material that has the same testing requirements.</span></span> <span data-ttu-id="db6e9-431">Ahelyett, hogy az új anyagra új tesztkövetelményeket állítana be, a vállalat hozzáadja az új anyag cikkszámát a meglévő minőségi csoporthoz.</span><span class="sxs-lookup"><span data-stu-id="db6e9-431">Instead of setting up new testing requirements for the new material, the company adds the item number for the new material to the existing quality group.</span></span> <span data-ttu-id="db6e9-432">Ugyanez a gyártóvállalat olyan cikkeket is gyárt, amelyek gyártási tesztjeire ugyanazok a követelmények érvényesek, és olyan cikkeket is szállít, amelyek szállítás előtti tesztjeire ugyanolyan követelmények vonatkoznak.</span><span class="sxs-lookup"><span data-stu-id="db6e9-432">The same manufacturing company also produces items that have the same production testing requirements and ships items that have the same requirement for pre-shipment testing.</span></span> <span data-ttu-id="db6e9-433">A vállalat két további minőségi csoportot határoz meg, majd a megfelelő cikkszámokat hozzárendeli az egyes minőségi csoportokhoz.</span><span class="sxs-lookup"><span data-stu-id="db6e9-433">The company defines two additional quality groups and then assigns the relevant item numbers to each group.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="db6e9-434">Tesztváltozók</span><span class="sxs-lookup"><span data-stu-id="db6e9-434">Test variables</span></span></td>
<td><span data-ttu-id="db6e9-435">Ezen az oldalon meghatározhatja és megtekintheti a minőségi tesztekhez társított változókat.</span><span class="sxs-lookup"><span data-stu-id="db6e9-435">Use this page to define and view the variables that are associated with a qualitative test.</span></span> <span data-ttu-id="db6e9-436">Minden változóhoz definiálhat sorszámozott eredményeket, amelyek a szóba jöhető lehetőségeket jelölik.</span><span class="sxs-lookup"><span data-stu-id="db6e9-436">For each variable, you define enumerated outcomes that represent the possible options.</span></span> <span data-ttu-id="db6e9-437">Teszteket a <strong>Tesztek</strong> oldalon adhat meg.</span><span class="sxs-lookup"><span data-stu-id="db6e9-437">You define tests on the <strong>Tests</strong> page.</span></span> <span data-ttu-id="db6e9-438">Minőségi tesztek esetén a teszt típusát <strong>Lehetőség</strong>-re kell állítania.</span><span class="sxs-lookup"><span data-stu-id="db6e9-438">For qualitative tests, you must set the test type to <strong>Option</strong>.</span></span> <span data-ttu-id="db6e9-439">A <strong>Tesztcsoportok</strong> oldal használatával lehet tesztváltozót adott teszthez hozzárendelni.</span><span class="sxs-lookup"><span data-stu-id="db6e9-439">Use the <strong>Test groups</strong> page to assign a test variable to an individual test.</span></span></td>
<td><span data-ttu-id="db6e9-440">Egy süteménygyártó a készterméken vizsgálatot végez.</span><span class="sxs-lookup"><span data-stu-id="db6e9-440">A manufacturing company that produces cookies uses an inspection test for the finished product.</span></span> <span data-ttu-id="db6e9-441">A vizsgálat tesztnek többféle változója van.</span><span class="sxs-lookup"><span data-stu-id="db6e9-441">This inspection test has several variables.</span></span> <span data-ttu-id="db6e9-442">Az egyik változó az íz, ennek lehetséges eredményei: jó és rossz.</span><span class="sxs-lookup"><span data-stu-id="db6e9-442">One variable is taste, and the possible outcomes for this variable are good and bad.</span></span> <span data-ttu-id="db6e9-443">Egy másik változó a szín, ennek lehetséges eredményei: túl sötét, túl világos és megfelelő.</span><span class="sxs-lookup"><span data-stu-id="db6e9-443">A second variable is color, and the possible outcomes are too dark, too light, and correct.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="db6e9-444">Tesztváltozó eredményei</span><span class="sxs-lookup"><span data-stu-id="db6e9-444">Test variable outcomes</span></span></td>
<td><span data-ttu-id="db6e9-445">Ezen az oldalon lehet beállítani, módosítani vagy megtekinteni a minőségi teszthez kapcsolódó tesztváltozó lehetséges teszteredményeit.</span><span class="sxs-lookup"><span data-stu-id="db6e9-445">Use this page to set up, edit, and to view the possible test results for a test variable that is associated with a qualitative test.</span></span> <span data-ttu-id="db6e9-446">Mindegyik eredményhez egy <strong>megfelelt</strong> vagy egy <strong>nem felelt meg</strong> állapotot kell hozzárendelni.</span><span class="sxs-lookup"><span data-stu-id="db6e9-446">For each outcome, you assign a <strong>pass</strong> or <strong>fail</strong> status.</span></span> <span data-ttu-id="db6e9-447">Minden egyes, a <strong>Tesztek</strong> oldalon megadott minőségi teszthez definiálnia kell egy változót és annak eredményeit.</span><span class="sxs-lookup"><span data-stu-id="db6e9-447">You must define a variable and its outcomes for each qualitative test that is defined on the <strong>Tests</strong> page.</span></span> <span data-ttu-id="db6e9-448">(Minőségi tesztek esetén a <strong>Tesztek</strong> oldalon beállított teszttípus <strong>Lehetőség</strong>.) A <strong>Tesztcsoportok</strong> oldal használatával lehet tesztváltozót és az alapértelmezett eredményt adott minőségi teszthez hozzárendelni.</span><span class="sxs-lookup"><span data-stu-id="db6e9-448">(For qualitative tests, the test type is set to <strong>Option</strong> on the <strong>Tests</strong> page.) Use the <strong>Test groups</strong> page to assign a test variable and the default outcome to an individual qualitative test.</span></span></td>
<td><span data-ttu-id="db6e9-449">Egy süteménygyártó a készterméken vizsgálatot végez.</span><span class="sxs-lookup"><span data-stu-id="db6e9-449">A manufacturing company that produces cookies uses an inspection test for the finished product.</span></span> <span data-ttu-id="db6e9-450">Ennek a vizsgálati tesztnek többféle változója van.</span><span class="sxs-lookup"><span data-stu-id="db6e9-450">This inspection test has of several variables.</span></span> <span data-ttu-id="db6e9-451">Az egyik változó az íz, ennek lehetséges eredményei: jó és rossz.</span><span class="sxs-lookup"><span data-stu-id="db6e9-451">One variable is taste, and the possible outcomes for this variable are good and bad.</span></span> <span data-ttu-id="db6e9-452">Egy másik változó a szín, ennek lehetséges eredményei: túl sötét, túl világos és megfelelő.</span><span class="sxs-lookup"><span data-stu-id="db6e9-452">A second variable is color, and the possible outcomes are too dark, too light, and correct.</span></span> <span data-ttu-id="db6e9-453">Mindegyik eredményhez hozzá van rendelve egy <strong>megfelelt</strong> vagy <strong>nem felelt meg</strong> állapot.</span><span class="sxs-lookup"><span data-stu-id="db6e9-453">A status of <strong>pass</strong> or <strong>fail</strong> is assigned to each outcome.</span></span> <span data-ttu-id="db6e9-454">Az egyes változók vizsgálatakor az ellenőr a teszt eredményét az egyik eredmény kiválasztásával jelenti.</span><span class="sxs-lookup"><span data-stu-id="db6e9-454">During the inspection test for each variable, the inspector reports the test result by selecting one of the outcomes.</span></span></td>
</tr>
</tbody>
</table>



<a name="additional-resources"></a><span data-ttu-id="db6e9-455">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="db6e9-455">Additional resources</span></span>
--------

[<span data-ttu-id="db6e9-456">Minőségkezelési folyamatok</span><span class="sxs-lookup"><span data-stu-id="db6e9-456">Quality management processes</span></span>](quality-management-processes.md)

[<span data-ttu-id="db6e9-457">Szabálytalanság kezelésének aktiválása</span><span class="sxs-lookup"><span data-stu-id="db6e9-457">Enabling nonconformance management</span></span>](enable-nonconformance-management.md)
