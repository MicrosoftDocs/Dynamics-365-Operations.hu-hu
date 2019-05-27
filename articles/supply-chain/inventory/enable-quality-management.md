---
title: Minőségkezelés áttekintése
description: Ez a témakör leírja, hogyan alkalmazza a minőségkezelés funkciót a Microsoft Dynamics 365 for Finance and Operations szolgáltatásban, hogy ezzel segítse a termékminőség fejlesztését az ön ellátási láncán belül.
author: perlynne
manager: AnnBe
ms.date: 11/02/2017
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
ms.openlocfilehash: 1630d13437d7e930fdf32ed5fdc61fc62bc33817
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1557500"
---
# <a name="quality-management-overview"></a><span data-ttu-id="e3bd8-103">Minőségkezelés áttekintése</span><span class="sxs-lookup"><span data-stu-id="e3bd8-103">Quality management overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e3bd8-104">Ez a témakör leírja, hogyan alkalmazza a minőségkezelés funkciót a Microsoft Dynamics 365 for Finance and Operations szolgáltatásban, hogy ezzel segítse a termékminőség fejlesztését az ön ellátási láncán belül.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-104">This topic describes how you can use quality management in Microsoft Dynamics 365 for Finance and Operations to help improve product quality within your supply chain.</span></span>

<span data-ttu-id="e3bd8-105">A minőségkezelés segítséget nyújt a szabálytalan termékek javítási folyamatának kezelésében, azok eredetétől függetlenül.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-105">Quality management can help you manage turnaround times when you handle nonconforming products, regardless of their point of origin.</span></span> <span data-ttu-id="e3bd8-106">Mivel a diagnosztikai típusok javítási jelentésekhez kapcsolódnak, a Microsoft Dynamics 365 for Finance and Operations képes beütemezni a problémák megoldásához és azok visszatérésének megelőzéséhez szükséges feladatokat.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-106">Because diagnostic types are linked to correction reporting, Microsoft Dynamics 365 for Finance and Operations can schedule tasks to correct problems and prevent them from recurring.</span></span>

<span data-ttu-id="e3bd8-107">A szabálytalanság kezelésére szolgáló funkció mellett a minőségkezelés egyéb funkciói lehetővé teszik a problémakövetést problématípus (akár belső problémák) szerint, valamint a rövid- és hosszútávú megoldások azonosítását.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-107">In addition to functionality for managing nonconformance, quality management includes functionality for tracking issues by problem type (even internal problems), and for identifying solutions as short-term or long-term.</span></span> <span data-ttu-id="e3bd8-108">A fő teljesítménymutatókról (KPI-kről) vezetett statisztikák betekintést nyújtanak a múltban megtörtént szabálytalansági problémákba és az azok javítására használt megoldásokba.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-108">Statistics about key performance indicators (KPIs) provide insight into the history of previous nonconformance issues and the solutions that were used to correct them.</span></span> <span data-ttu-id="e3bd8-109">Az előzményadatok segítségével felülvizsgálhatja a korábbi minőségi mérések hatékonyságát, és kidolgozhatja a jövőben alkalmazni kívánt megfelelő méréseket.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-109">You can use historical data to review the effectiveness of previous quality measures and determine appropriate measures to use in the future.</span></span>

<span data-ttu-id="e3bd8-110">Mikor beállít egy minőségi társítást, a Finance and Operations képes létrehozni különféle üzleti folyamatok, események és feltételek minőségi rendeléseit.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-110">When you set up a quality association, Finance and Operations can generate quality orders for various business processes, events, and conditions.</span></span> <span data-ttu-id="e3bd8-111">A minőségi társítás vonatkozhat egyetlen cikkre, cikkek egy csoportjára vagy minden cikkre.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-111">The quality association can cover a specific item, a specific group of items, or all items.</span></span>

## <a name="examples-of-the-use-of-quality-management"></a><span data-ttu-id="e3bd8-112">Példák a minőségkezelés használatára</span><span class="sxs-lookup"><span data-stu-id="e3bd8-112">Examples of the use of quality management</span></span>
<span data-ttu-id="e3bd8-113">A minőségkezelés rugalmas és sokféle módon megvalósítható, így meg tud felelni az ellátási lánc műveleteinek adott szintjeire vonatkozó követelményeknek.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-113">Quality management is flexible and can be implemented in various ways to meet the requirements of specific levels of supply chain operations.</span></span> <span data-ttu-id="e3bd8-114">Az alábbi példák ezeknek a funkcióknak a felhasználási lehetőségeit mutatják be.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-114">The following examples illustrate possible uses of these features:</span></span>

-   <span data-ttu-id="e3bd8-115">Indítson automatikusan minőségellenőrzési folyamatot előre meghatározott feltételek teljesülésekor (adott szállítótól történő beszerzési rendelés raktári regisztrációja alapján).</span><span class="sxs-lookup"><span data-stu-id="e3bd8-115">Automatically start a quality control process, based on predefined criteria (upon warehouse registration of a purchase order from a specific vendor).</span></span>
-   <span data-ttu-id="e3bd8-116">Vizsgálat alatt zárolja a készletet a jóvá nem hagyott készlet használatának megakadályozása érdekében (a beszerzési rendelési mennyiségek teljes zárolása).</span><span class="sxs-lookup"><span data-stu-id="e3bd8-116">Block inventory during inspection to prevent non-approved inventory from being used (full blocking of purchase order quantities).</span></span>
-   <span data-ttu-id="e3bd8-117">Az aktuális tényleges készlet vizsgálandó mennyiségének meghatározásához használja a minőségi társítás részét képező cikkmintavételt.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-117">Use item sampling as part of a quality association to define the amount of current physical inventory that must be inspected.</span></span> <span data-ttu-id="e3bd8-118">A mintavétel történhet adott mennyiség vagy százalékos érték alapján.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-118">Sampling can be based on fixed quantities or a percentage.</span></span>
-   <span data-ttu-id="e3bd8-119">A részleges bevételezésekhez minőségi rendeléseket kell létrehozni.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-119">Create quality orders for partial receipts.</span></span> <span data-ttu-id="e3bd8-120">Ha olyan minőségi rendelést szeretne létrehozni, amely egy rendelésen fizikailag bevételezett mennyiségen alapul, akkor be kell jelölnie a **Frissített mennyiségenként** jelölőnégyzetet a **Cikkmintavétel** űrlapon.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-120">To create a quality order that is based on the quantity that is physically received with an order, you must select the **Per updated quantity** check box on the **Item sampling** form.</span></span>
-   <span data-ttu-id="e3bd8-121">Hozzon létre minimum, maximum és cél tesztértékeket magukban foglaló teszttípusokat, és végezzen előre definiált ellenőrzési eredményeket adó minőségi-mennyiségi teszteket.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-121">Create test types that include minimum, maximum, and target test values, and perform qualitative-versus-quantitative testing that has predefined validation results.</span></span>
-   <span data-ttu-id="e3bd8-122">Adja meg az elfogadható minőségi szint értékét a minőségi mérések tűréshatárainak szabályozása érdekében.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-122">Specify an acceptable quality level (AQL) to control quality measure tolerances.</span></span>
-   <span data-ttu-id="e3bd8-123">Határozza meg a vizsgálati művelethez szükséges erőforrásokat (például tesztterület és tesztműszerek).</span><span class="sxs-lookup"><span data-stu-id="e3bd8-123">Specify the resources that an inspection operation requires, such as a test area and test instruments.</span></span>

## <a name="working-with-quality-associations"></a><span data-ttu-id="e3bd8-124">Minőségi társítások használata</span><span class="sxs-lookup"><span data-stu-id="e3bd8-124">Working with quality associations</span></span>
<span data-ttu-id="e3bd8-125">Egy minőségi társítást használó üzleti folyamat különféle forrásbizonylatokkal lehet kapcsolatban (például beszerzési rendelésekkel, értékesítési rendelésekkel, vagy termelési rendelésekkel).</span><span class="sxs-lookup"><span data-stu-id="e3bd8-125">The business process that uses a quality association can be related to various source documents, such as purchase orders, sales orders, or production orders.</span></span>

<span data-ttu-id="e3bd8-126">Minden egyes minőségi társítási rekord meghatározza a létrehozott minőségi rendelésekre vonatkozó teszteket, elfogadható minőségi szintet és mintavételi eljárást.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-126">Each quality association record defines the set of tests, the AQL, and the sampling plan that applies to the quality orders that are generated.</span></span> <span data-ttu-id="e3bd8-127">Az üzleti folyamat minden egyes változatára definiálnia kell egy minőségi társítási rekordot.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-127">You must define a quality association record for each variation in a business process.</span></span> <span data-ttu-id="e3bd8-128">Például beállíthat egy olyan minőségi társítást, amely egy beszerzési rendelés termékbevételezésének frissítésekor létrehoz egy minőségi rendelést.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-128">For example, you can set up a quality association that generates a quality order when a purchase order product receipt is updated.</span></span> <span data-ttu-id="e3bd8-129">A végrehajtási terv beállításától függően letiltható maga az indító folyamat, ha van egy nyitott minőségi rendelés, vagy letilthatóak az ezután következő folyamatok, például a beszerzési rendelés számlázása.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-129">Depending on the setup of the execution plan, the triggering process itself can be blocked while there is an open quality order, or the next processes, such as purchase order invoicing, can be blocked.</span></span>

<span data-ttu-id="e3bd8-130">**Megjegyzés:** Amíg vannak nyitott minőségi rendelések, a készletmennyiségek kiadása automatikusan le van tiltva.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-130">**Note:** While there are open quality orders, inventory quantities are automatically blocked from being issued.</span></span> <span data-ttu-id="e3bd8-131">A **Cikkmintavételek** lap **Teljes zárolás** beállításától függően a mennyiség a minőségi rendelésen vagy a forrásbizonylat sorában szereplő mennyiség lehet.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-131">Depending on the **Full blocking** setting on the **Item samplings** page, the quantity is either the quantity on the quality order or the quantity on the source document line.</span></span>

<span data-ttu-id="e3bd8-132">Egy adott üzleti folyamatra a minőségi társítási rekord azonosítja azokat az eseményeket és feltételeket, amelyek fennállása esetén a minőségi rendelés létrejön.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-132">For a given business process, the quality association record identifies the event and the conditions that a quality order is generated for.</span></span> <span data-ttu-id="e3bd8-133">A feltételek helyre vagy jogi személyre vonatkozhatnak.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-133">The conditions can be specific to either a site or a legal entity.</span></span> <span data-ttu-id="e3bd8-134">Romboló teszteket igénylő minőségi rendelés csak akkor generálható, ha az eseményhez létezik aktuális készlet.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-134">A quality order that involves destructive tests can be generated only when on-hand inventory exists for the event.</span></span>

<span data-ttu-id="e3bd8-135">A következő példák bemutatják egy minőségi társítási rekord meghatározását az egyes üzleti folyamatok változásainak megfelelően.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-135">The following examples illustrate how a quality association record is defined for the variations in each business process.</span></span> <span data-ttu-id="e3bd8-136">Egy minőségi társítási rekord által az egyes példák esetén meghatározott eseményeket és feltételeket az alábbi táblázat összegzi.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-136">For each example, the following table summarizes the events and conditions that are defined by a quality association record.</span></span>

<table>
<tbody>
<tr>
<th><span data-ttu-id="e3bd8-137">Hivatkozás típusa</span><span class="sxs-lookup"><span data-stu-id="e3bd8-137">Reference type</span></span></th>
<th><span data-ttu-id="e3bd8-138">Eseménytípus</span><span class="sxs-lookup"><span data-stu-id="e3bd8-138">Event type</span></span></th>
<th><span data-ttu-id="e3bd8-139">Végrehajtás</span><span class="sxs-lookup"><span data-stu-id="e3bd8-139">Execution</span></span></th>
<th><span data-ttu-id="e3bd8-140">Eseményzárolás</span><span class="sxs-lookup"><span data-stu-id="e3bd8-140">Event blocking</span></span></th>
<th><span data-ttu-id="e3bd8-141">Dokumentumhivatkozás</span><span class="sxs-lookup"><span data-stu-id="e3bd8-141">Document reference</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="e3bd8-142">Készlet</span><span class="sxs-lookup"><span data-stu-id="e3bd8-142">Inventory</span></span></td>
<td><span data-ttu-id="e3bd8-143">Nem alkalmazható</span><span class="sxs-lookup"><span data-stu-id="e3bd8-143">Not applicable</span></span></td>
<td><span data-ttu-id="e3bd8-144">Nem alkalmazható</span><span class="sxs-lookup"><span data-stu-id="e3bd8-144">Not applicable</span></span></td>
<td><span data-ttu-id="e3bd8-145">Egyik sem</span><span class="sxs-lookup"><span data-stu-id="e3bd8-145">None</span></span></td>
<td><span data-ttu-id="e3bd8-146">Mind</span><span class="sxs-lookup"><span data-stu-id="e3bd8-146">All</span></span></td>
</tr>
<tr>
<td rowspan="7"><span data-ttu-id="e3bd8-147">Értékesítés</span><span class="sxs-lookup"><span data-stu-id="e3bd8-147">Sales</span></span></td>
<td rowspan="4"><span data-ttu-id="e3bd8-148">Kitárolási folyamat ütemezve</span><span class="sxs-lookup"><span data-stu-id="e3bd8-148">Picking process is scheduled</span></span></td>
<td rowspan="4"><span data-ttu-id="e3bd8-149">Előtte</span><span class="sxs-lookup"><span data-stu-id="e3bd8-149">Before</span></span></td>
<td><span data-ttu-id="e3bd8-150">Egyik sem</span><span class="sxs-lookup"><span data-stu-id="e3bd8-150">None</span></span></td>
<td rowspan="22"><span data-ttu-id="e3bd8-151">Csak Egyedi azonosító, Csoport vagy Mind</span><span class="sxs-lookup"><span data-stu-id="e3bd8-151">Specific ID, Group, or All only</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e3bd8-152">Kitárolási folyamat</span><span class="sxs-lookup"><span data-stu-id="e3bd8-152">Picking process</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e3bd8-153">Szállítólevél</span><span class="sxs-lookup"><span data-stu-id="e3bd8-153">Packing slip</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e3bd8-154">Számla</span><span class="sxs-lookup"><span data-stu-id="e3bd8-154">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="e3bd8-155">Szállítólevél</span><span class="sxs-lookup"><span data-stu-id="e3bd8-155">Packing slip</span></span></td>
<td rowspan="3"><span data-ttu-id="e3bd8-156">Előtte</span><span class="sxs-lookup"><span data-stu-id="e3bd8-156">Before</span></span></td>
<td><span data-ttu-id="e3bd8-157">Egyik sem</span><span class="sxs-lookup"><span data-stu-id="e3bd8-157">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e3bd8-158">Szállítólevél</span><span class="sxs-lookup"><span data-stu-id="e3bd8-158">Packing slip</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e3bd8-159">Számla</span><span class="sxs-lookup"><span data-stu-id="e3bd8-159">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="15"><span data-ttu-id="e3bd8-160">Beszerzés</span><span class="sxs-lookup"><span data-stu-id="e3bd8-160">Purchase</span></span></td>
<td rowspan="7"><span data-ttu-id="e3bd8-161">Bevételezési lista</span><span class="sxs-lookup"><span data-stu-id="e3bd8-161">Receipt list</span></span></td>
<td rowspan="4"><span data-ttu-id="e3bd8-162">Előtte</span><span class="sxs-lookup"><span data-stu-id="e3bd8-162">Before</span></span></td>
<td><span data-ttu-id="e3bd8-163">Egyik sem</span><span class="sxs-lookup"><span data-stu-id="e3bd8-163">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e3bd8-164">Bevételezési lista</span><span class="sxs-lookup"><span data-stu-id="e3bd8-164">Receipt list</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e3bd8-165">Termékbevételezés</span><span class="sxs-lookup"><span data-stu-id="e3bd8-165">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e3bd8-166">Számla</span><span class="sxs-lookup"><span data-stu-id="e3bd8-166">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="e3bd8-167">Utána</span><span class="sxs-lookup"><span data-stu-id="e3bd8-167">After</span></span></td>
<td><span data-ttu-id="e3bd8-168">Egyik sem</span><span class="sxs-lookup"><span data-stu-id="e3bd8-168">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e3bd8-169">Termékbevételezés</span><span class="sxs-lookup"><span data-stu-id="e3bd8-169">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e3bd8-170">Számla</span><span class="sxs-lookup"><span data-stu-id="e3bd8-170">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="e3bd8-171">Nyilvántartás</span><span class="sxs-lookup"><span data-stu-id="e3bd8-171">Registration</span></span></td>
<td rowspan="3"><span data-ttu-id="e3bd8-172">Nem alkalmazható</span><span class="sxs-lookup"><span data-stu-id="e3bd8-172">Not applicable</span></span></td>
<td><span data-ttu-id="e3bd8-173">Egyik sem</span><span class="sxs-lookup"><span data-stu-id="e3bd8-173">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e3bd8-174">Termékbevételezés</span><span class="sxs-lookup"><span data-stu-id="e3bd8-174">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e3bd8-175">Számla</span><span class="sxs-lookup"><span data-stu-id="e3bd8-175">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="5"><span data-ttu-id="e3bd8-176">Termékbevételezés</span><span class="sxs-lookup"><span data-stu-id="e3bd8-176">Product receipt</span></span></td>
<td rowspan="3"><span data-ttu-id="e3bd8-177">Előtte</span><span class="sxs-lookup"><span data-stu-id="e3bd8-177">Before</span></span></td>
<td><span data-ttu-id="e3bd8-178">Egyik sem</span><span class="sxs-lookup"><span data-stu-id="e3bd8-178">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e3bd8-179">Termékbevételezés</span><span class="sxs-lookup"><span data-stu-id="e3bd8-179">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e3bd8-180">Számla</span><span class="sxs-lookup"><span data-stu-id="e3bd8-180">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="2"><span data-ttu-id="e3bd8-181">Utána</span><span class="sxs-lookup"><span data-stu-id="e3bd8-181">After</span></span></td>
<td><span data-ttu-id="e3bd8-182">Egyik sem</span><span class="sxs-lookup"><span data-stu-id="e3bd8-182">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e3bd8-183">Számla</span><span class="sxs-lookup"><span data-stu-id="e3bd8-183">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="8"><span data-ttu-id="e3bd8-184">Termelés</span><span class="sxs-lookup"><span data-stu-id="e3bd8-184">Production</span></span></td>
<td rowspan="3"><span data-ttu-id="e3bd8-185">Nyilvántartás</span><span class="sxs-lookup"><span data-stu-id="e3bd8-185">Registration</span></span></td>
<td rowspan="3"><span data-ttu-id="e3bd8-186">Nem alkalmazható</span><span class="sxs-lookup"><span data-stu-id="e3bd8-186">Not applicable</span></span></td>
<td><span data-ttu-id="e3bd8-187">Egyik sem</span><span class="sxs-lookup"><span data-stu-id="e3bd8-187">None</span></span></td>
<td rowspan="12"><span data-ttu-id="e3bd8-188">Mind</span><span class="sxs-lookup"><span data-stu-id="e3bd8-188">All</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e3bd8-189">Készként jelentés</span><span class="sxs-lookup"><span data-stu-id="e3bd8-189">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e3bd8-190">Záró</span><span class="sxs-lookup"><span data-stu-id="e3bd8-190">End</span></span></td>
</tr>
<tr>
<td rowspan="5"><span data-ttu-id="e3bd8-191">Készként jelentés</span><span class="sxs-lookup"><span data-stu-id="e3bd8-191">Report as finished</span></span></td>
<td rowspan="3"><span data-ttu-id="e3bd8-192">Előtte</span><span class="sxs-lookup"><span data-stu-id="e3bd8-192">Before</span></span></td>
<td><span data-ttu-id="e3bd8-193">Egyik sem</span><span class="sxs-lookup"><span data-stu-id="e3bd8-193">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e3bd8-194">Készként jelentés</span><span class="sxs-lookup"><span data-stu-id="e3bd8-194">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e3bd8-195">Záró</span><span class="sxs-lookup"><span data-stu-id="e3bd8-195">End</span></span></td>
</tr>
<tr>
<td rowspan="2"><span data-ttu-id="e3bd8-196">Utána</span><span class="sxs-lookup"><span data-stu-id="e3bd8-196">After</span></span></td>
<td><span data-ttu-id="e3bd8-197">Egyik sem</span><span class="sxs-lookup"><span data-stu-id="e3bd8-197">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e3bd8-198">Záró</span><span class="sxs-lookup"><span data-stu-id="e3bd8-198">End</span></span></td>
</tr>
<tr>
<td rowspan="4"><span data-ttu-id="e3bd8-199">Karantén</span><span class="sxs-lookup"><span data-stu-id="e3bd8-199">Quarantine</span></span></td>
<td rowspan="3"><span data-ttu-id="e3bd8-200">Készként jelentés</span><span class="sxs-lookup"><span data-stu-id="e3bd8-200">Report as finished</span></span></td>
<td rowspan="2"><span data-ttu-id="e3bd8-201">Előtte</span><span class="sxs-lookup"><span data-stu-id="e3bd8-201">Before</span></span></td>
<td><span data-ttu-id="e3bd8-202">Készként jelentés</span><span class="sxs-lookup"><span data-stu-id="e3bd8-202">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e3bd8-203">Záró</span><span class="sxs-lookup"><span data-stu-id="e3bd8-203">End</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e3bd8-204">Utána</span><span class="sxs-lookup"><span data-stu-id="e3bd8-204">After</span></span></td>
<td><span data-ttu-id="e3bd8-205">Záró</span><span class="sxs-lookup"><span data-stu-id="e3bd8-205">End</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e3bd8-206">Záró</span><span class="sxs-lookup"><span data-stu-id="e3bd8-206">End</span></span></td>
<td><span data-ttu-id="e3bd8-207">Előtte</span><span class="sxs-lookup"><span data-stu-id="e3bd8-207">Before</span></span></td>
<td><span data-ttu-id="e3bd8-208">Záró</span><span class="sxs-lookup"><span data-stu-id="e3bd8-208">End</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="e3bd8-209">Útvonalművelet</span><span class="sxs-lookup"><span data-stu-id="e3bd8-209">Route operation</span></span></td>
<td rowspan="3"><span data-ttu-id="e3bd8-210">Készként jelentés</span><span class="sxs-lookup"><span data-stu-id="e3bd8-210">Report as finished</span></span></td>
<td rowspan="2"><span data-ttu-id="e3bd8-211">Előtte</span><span class="sxs-lookup"><span data-stu-id="e3bd8-211">Before</span></span></td>
<td><span data-ttu-id="e3bd8-212">Egyik sem</span><span class="sxs-lookup"><span data-stu-id="e3bd8-212">None</span></span></td>
<td rowspan="3"><span data-ttu-id="e3bd8-213">Egyedi azonosító, Csoport vagy Mind, valamint Erőforrás-specifikus, Csoport vagy Mind</span><span class="sxs-lookup"><span data-stu-id="e3bd8-213">Specific ID, Group, or All, and Resource specific, Group, or All</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e3bd8-214">Készként jelentés</span><span class="sxs-lookup"><span data-stu-id="e3bd8-214">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e3bd8-215">Utána</span><span class="sxs-lookup"><span data-stu-id="e3bd8-215">After</span></span></td>
<td><span data-ttu-id="e3bd8-216">Egyik sem</span><span class="sxs-lookup"><span data-stu-id="e3bd8-216">None</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="e3bd8-217">Társtermék gyártása</span><span class="sxs-lookup"><span data-stu-id="e3bd8-217">Co-product production</span></span></td>
<td><span data-ttu-id="e3bd8-218">Nyilvántartás</span><span class="sxs-lookup"><span data-stu-id="e3bd8-218">Registration</span></span></td>
<td><span data-ttu-id="e3bd8-219">Nem alkalmazható</span><span class="sxs-lookup"><span data-stu-id="e3bd8-219">Not applicable</span></span></td>
<td rowspan="3"><span data-ttu-id="e3bd8-220">Egyik sem</span><span class="sxs-lookup"><span data-stu-id="e3bd8-220">None</span></span></td>
<td rowspan="3"><span data-ttu-id="e3bd8-221">Mind</span><span class="sxs-lookup"><span data-stu-id="e3bd8-221">All</span></span></td>
</tr>
<tr>
<td rowspan="2"><span data-ttu-id="e3bd8-222">Készként jelentés</span><span class="sxs-lookup"><span data-stu-id="e3bd8-222">Report as finished</span></span></td>
<td><span data-ttu-id="e3bd8-223">Előtte</span><span class="sxs-lookup"><span data-stu-id="e3bd8-223">Before</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e3bd8-224">Utána</span><span class="sxs-lookup"><span data-stu-id="e3bd8-224">After</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="e3bd8-225">A következő táblázatban bővebben tájékozódhat arról, hogy hogyan hozhatóak létre minőségi rendelések adott típusú folyamatokhoz.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-225">The following table provides more information about how quality orders can be generated for specific types of processes.</span></span>
<div class="tableSection">

<table>
<tbody>
<tr>
<th><span data-ttu-id="e3bd8-226">Folyamat típusa</span><span class="sxs-lookup"><span data-stu-id="e3bd8-226">Type of process</span></span></th>
<th><span data-ttu-id="e3bd8-227">Mikor hozhatóak létre automatikusan minőségi rendelések?</span><span class="sxs-lookup"><span data-stu-id="e3bd8-227">When quality orders can be automatically generated</span></span></th>
<th><span data-ttu-id="e3bd8-228">Mikor hozhatóak létre minőségi rendelések, amennyiben romboló tesztekre van szükség?</span><span class="sxs-lookup"><span data-stu-id="e3bd8-228">When quality orders can be generated if destructive testing is required</span></span></th>
<th><span data-ttu-id="e3bd8-229">Feltételekre vonatkozó információ</span><span class="sxs-lookup"><span data-stu-id="e3bd8-229">Condition information</span></span></th>
<th><span data-ttu-id="e3bd8-230">Manuális létrehozásra vonatkozó információ</span><span class="sxs-lookup"><span data-stu-id="e3bd8-230">Manual generation information</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="e3bd8-231">Beszerzési rendelés</span><span class="sxs-lookup"><span data-stu-id="e3bd8-231">Purchase order</span></span></td>
<td><span data-ttu-id="e3bd8-232">A bevételezett anyagra vonatkozó bevételezési lista vagy termékbevételezés feladása előtt vagy után</span><span class="sxs-lookup"><span data-stu-id="e3bd8-232">Before or after a receipts list or product receipt for the material that is received is posted</span></span></td>
<td><span data-ttu-id="e3bd8-233">A bevételezett anyagra vonatkozó termékbevételezés feladása után, mivel az anyagnak rendelkezésre kell állnia a romboló teszt elvégzéséhez</span><span class="sxs-lookup"><span data-stu-id="e3bd8-233">After the product receipt for the material that is received is posted, because the material must be available for destructive testing</span></span></td>
<td><span data-ttu-id="e3bd8-234">A minőségi rendelés követelménye vonatkozhat egy adott telephelyre, cikkre vagy szállítóra, illetve ezek bármilyen kombinációjára.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-234">The requirement for a quality order can reflect a particular site, item, or vendor, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="e3bd8-235">A beszerzési rendelésekhez manuálisan generált minőségi rendelésekben felhasználhatók a minőségi társítási rekordban szereplő adatok, például a mintavételezési eljárás.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-235">A manually generated quality order that refers to a purchase order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e3bd8-236">Karanténutasítás</span><span class="sxs-lookup"><span data-stu-id="e3bd8-236">Quarantine order</span></span></td>
<td><span data-ttu-id="e3bd8-237">Mielőtt vagy miután a karanténutasítás készként lett jelentve vagy befejeződött</span><span class="sxs-lookup"><span data-stu-id="e3bd8-237">Before or after the quarantine order is reported as finished or ended</span></span></td>
<td><span data-ttu-id="e3bd8-238">Romboló teszteket igénylő minőségi rendelések nem hozhatóak létre.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-238">Quality orders that require destructive tests can&#39;t be generated.</span></span> <span data-ttu-id="e3bd8-239">A rendszer feltételezi, hogy a karanténutasítás funkció kezeli a roncsolt anyag elhelyezését.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-239">It&#39;s assumed that the quarantine order functionality handles the disposition of the material that is destroyed.</span></span></td>
<td><span data-ttu-id="e3bd8-240">A minőségi rendelés követelménye vonatkozhat egy adott telephelyre, cikkre vagy szállítóra, illetve ezek bármilyen kombinációjára.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-240">The requirement for a quality order can reflect a particular site, item, or vendor, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="e3bd8-241">A karanténutasításokhoz manuálisan generált minőségi rendelésekben felhasználhatók a minőségi társítási rekordban szereplő adatok, például a mintavételezési eljárás.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-241">A manually generated quality order that refers to a quarantine order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e3bd8-242">Értékesítési rendelés</span><span class="sxs-lookup"><span data-stu-id="e3bd8-242">Sales order</span></span></td>
<td><span data-ttu-id="e3bd8-243">A szállított cikkekre vonatkozó ütemezett kitárolási folyamat vagy szállítólevél frissítése előtt</span><span class="sxs-lookup"><span data-stu-id="e3bd8-243">Before a scheduled picking process or packing slip update for the items that are being shipped</span></span></td>
<td><span data-ttu-id="e3bd8-244">Bármelyik lépésnél</span><span class="sxs-lookup"><span data-stu-id="e3bd8-244">At any step</span></span></td>
<td><span data-ttu-id="e3bd8-245">A minőségi rendelés követelménye vonatkozhat egy adott telephelyre, cikkre vagy vevőre, illetve ezek bármilyen kombinációjára.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-245">The requirement for a quality order can reflect a particular site, item, or customer, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="e3bd8-246">Az értékesítési rendelésekhez manuálisan generált minőségi rendelésekben felhasználhatók a minőségi társítási rekordban szereplő adatok, például a mintavételezési eljárás.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-246">A manually generated quality order that refers to a sales order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e3bd8-247">Termelési rendelés</span><span class="sxs-lookup"><span data-stu-id="e3bd8-247">Production order</span></span></td>
<td><span data-ttu-id="e3bd8-248">A termelési rendelés befejezett mennyiségének jelentése előtt vagy után</span><span class="sxs-lookup"><span data-stu-id="e3bd8-248">Before or after the finished quantity for the production order is reported</span></span></td>
<td><span data-ttu-id="e3bd8-249">A termelési rendelés befejezett mennyiségének jelentése után</span><span class="sxs-lookup"><span data-stu-id="e3bd8-249">After the finished quantity for the production order is reported</span></span></td>
<td><span data-ttu-id="e3bd8-250">A minőségi rendelés követelménye vonatkozhat egy adott telephelyre vagy vevőre, illetve ezek kombinációjára.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-250">The requirement for a quality order can reflect a particular site or item, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="e3bd8-251">A termelési rendelésekhez manuálisan generált minőségi rendelésekben felhasználhatók a minőségi társítási rekordban szereplő adatok, például a mintavételezési eljárás.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-251">A manually generated quality order that refers to a production order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e3bd8-252">Útvonalművelettel rendelkező termelési utasítás</span><span class="sxs-lookup"><span data-stu-id="e3bd8-252">Production order that has a route operation</span></span></td>
<td><span data-ttu-id="e3bd8-253">A műveletre vonatkozó jelentés befejezése előtt vagy után</span><span class="sxs-lookup"><span data-stu-id="e3bd8-253">Before or after the report is finished for an operation</span></span></td>
<td><span data-ttu-id="e3bd8-254">Miután az utolsó művelet készként való jelentése megtörtént</span><span class="sxs-lookup"><span data-stu-id="e3bd8-254">After the reporting production is finished for the last operation</span></span></td>
<td><span data-ttu-id="e3bd8-255">A minőségi rendelés követelménye vonatkozhat egy adott telephelyre, cikkre, vevőre vagy üzemi erőforrásra, illetve ezek bármilyen kombinációjára.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-255">The requirement for a quality order can reflect a particular, site, item, or operations resource, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="e3bd8-256">Az útvonalművelethez manuálisan generált minőségi rendelésekben felhasználhatók a minőségi társítási rekordban szereplő adatok, például a mintavételezési eljárás.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-256">A manually generated quality order that refers to a route operation can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e3bd8-257">Készlet</span><span class="sxs-lookup"><span data-stu-id="e3bd8-257">Inventory</span></span></td>
<td><span data-ttu-id="e3bd8-258">A készletnaplón belüli tranzakciókhoz és az átmozgatási rendelési tranzakciókhoz nem generálhatók automatikusan minőségi rendelések.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-258">A quality order cannot be automatically generated for a transaction in an inventory journal or for transfer order transactions.</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="e3bd8-259">Cikk készletmennyiségére vonatkozó minőségi rendelést manuálisan kell létrehozni.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-259">A quality order must be created manually for an item&#39;s inventory quantity.</span></span> <span data-ttu-id="e3bd8-260">Tényleges aktuális készlet szükséges.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-260">Physical on-hand inventory is required.</span></span></td>
</tr>
</tbody>
</table>

## <a name="quality-management-pages"></a><span data-ttu-id="e3bd8-261">A Minőségkezelés oldalai</span><span class="sxs-lookup"><span data-stu-id="e3bd8-261">Quality management pages</span></span>
<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e3bd8-262">Oldal</span><span class="sxs-lookup"><span data-stu-id="e3bd8-262">Page</span></span></th>
<th><span data-ttu-id="e3bd8-263">Leírás</span><span class="sxs-lookup"><span data-stu-id="e3bd8-263">Description</span></span></th>
<th><span data-ttu-id="e3bd8-264">Példa</span><span class="sxs-lookup"><span data-stu-id="e3bd8-264">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="e3bd8-265">Minőségi társítások</span><span class="sxs-lookup"><span data-stu-id="e3bd8-265">Quality associations</span></span></td>
<td><span data-ttu-id="e3bd8-266">Lásd a cikk előző szakaszait.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-266">See the previous sections of this article.</span></span></td>
<td><span data-ttu-id="e3bd8-267">A minőségi társítás meghatározza a létrehozott minőségi rendelésre vonatkozó alábbi adatok mindegyikét:</span><span class="sxs-lookup"><span data-stu-id="e3bd8-267">A quality association defines all the following information for a quality order that is generated:</span></span>
<ul>
<li><span data-ttu-id="e3bd8-268">Tranzakcióesemény</span><span class="sxs-lookup"><span data-stu-id="e3bd8-268">The transaction event</span></span></li>
<li><span data-ttu-id="e3bd8-269">A cikkeken elvégzendő tesztek</span><span class="sxs-lookup"><span data-stu-id="e3bd8-269">The set of tests that must be performed on the items</span></span></li>
<li><span data-ttu-id="e3bd8-270">Elfogadható minőségi szint</span><span class="sxs-lookup"><span data-stu-id="e3bd8-270">The AQL</span></span></li>
<li><span data-ttu-id="e3bd8-271">Mintavételi terv</span><span class="sxs-lookup"><span data-stu-id="e3bd8-271">The sampling plan</span></span></li>
</ul>
<span data-ttu-id="e3bd8-272">Definiálnia kell egy minőségi társítást az üzleti folyamat minden olyan változatához, ahol minőségi rendelés automatikus létrehozása szükséges.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-272">You must define a quality association for each variation in a business process that requires automatic generation of quality orders.</span></span> <span data-ttu-id="e3bd8-273">Minőségi rendelés létrehozható például az üzleti folyamatokban beszerzési rendelésekhez, karanténutasításokhoz, értékesítési rendelésekhez és termelési rendelésekhez.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-273">For example, a quality order can be generated in the business processes for purchase orders, quarantine orders, sales orders, and production orders.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="e3bd8-274">Tesztek</span><span class="sxs-lookup"><span data-stu-id="e3bd8-274">Tests</span></span></td>
<td><span data-ttu-id="e3bd8-275">Ezen az oldalon lehet meghatározni és megtekinteni azokat a teszteket, amelyekkel megállapítható, hogy a termékek megfelelnek-e a minőségi specifikációknak.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-275">Use this page to define and view the individual tests that determine whether your products meet quality specifications.</span></span> <span data-ttu-id="e3bd8-276">Hozzárendelhet egy vagy több különálló tesztet egy tesztcsoporthoz.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-276">You can assign one or more individual tests to a test group.</span></span> <span data-ttu-id="e3bd8-277">Ebben az esetben tesztspecifikus adatokat is megadhat, például az elfogadható mérési értékeket.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-277">In this case, you also specify test-specific information, such as the acceptable measurement values.</span></span> <span data-ttu-id="e3bd8-278">Mennyiségi tesztekhez mérési értékek, minőségi tesztekhez pedig tesztváltozók használhatók.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-278">Measurement values are used for quantitative tests, and test variables are used for qualitative tests.</span></span>
<ul>
<li><span data-ttu-id="e3bd8-279">Egy mennyiségi teszt teszttípusa <strong>Egész</strong> vagy <strong>Tört</strong> lehet, és egy kijelölt mértékegység is tartozik hozzá.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-279">A quantitative test has a test type of <strong>Integer</strong> or <strong>Fraction</strong>, and also has a designated unit of measure.</span></span> <span data-ttu-id="e3bd8-280">A minőségi specifikációk és a teszteredmények számokként fejeződnek ki.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-280">Quality specifications and test results are expressed as numbers.</span></span></li>
<li><span data-ttu-id="e3bd8-281">A minőségi tesztek teszttípusa: <strong>Lehetőség</strong>.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-281">A qualitative test has a test type of <strong>Option</strong>.</span></span> <span data-ttu-id="e3bd8-282">A minőségi tesztekhez további, a mérendő tesztváltozóra és annak sorszámozott lehetőségeire vonatkozó adatok szükségesek.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-282">Qualitative tests require additional information about the test variable that is being measured and its enumerated options.</span></span> <span data-ttu-id="e3bd8-283">A minőségi specifikációk és a teszteredmények egy eredménynek megfelelően fejeződnek ki.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-283">Quality specifications and test results are expressed according to an outcome.</span></span></li>
</ul></td>
<td><span data-ttu-id="e3bd8-284">Egy gyártóvállalat a beszerzett anyagon két tesztet végez el: ezek egyike az anyagminőséggel kapcsolatos mennyiségi teszt, a másik pedig a csomagolási sérüléseket felmérő minőségi teszt.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-284">A manufacturing company performs two tests on purchased material: a quantitative test about material quality and a qualitative test about packaging damage.</span></span> <span data-ttu-id="e3bd8-285">A vállalat további adatokat ad meg a kvalitatív tesztre vonatkozóan, hogy meghatározza a tesztváltozót (sérült csomagolás) és annak kimeneteleit.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-285">The company defines additional information about the qualitative test to identify the test variable (damaged packaging) and its outcomes.</span></span> <span data-ttu-id="e3bd8-286">A vállalat a <strong>Tesztcsoportok</strong> oldalon hozzárendeli a két tesztet egy tesztcsoporthoz és megadja a tesztspecifikus adatokat.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-286">The company uses the <strong>Test groups</strong> page to assign the two tests to a test group and to specify the test-specific information.</span></span> <span data-ttu-id="e3bd8-287">A tesztcsoportot hozzárendeli egy minőségi rendeléshez, hogy a két teszt eredményét jelenteni tudja.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-287">The test group is assigned to a quality order, so that the company can report test results for the two tests.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="e3bd8-288">Tesztcsoportok</span><span class="sxs-lookup"><span data-stu-id="e3bd8-288">Test groups</span></span></td>
<td><span data-ttu-id="e3bd8-289">Ezen az oldalon lehet beállítani, módosítani és megtekinteni a tesztcsoportokat és a tesztcsoportokhoz rendelt különálló teszteket.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-289">Use this page to set up, edit, and view test groups and the individual tests that are assigned to a test group.</span></span> <span data-ttu-id="e3bd8-290">A felső ablak jeleníti meg a tesztcsoportokat, míg az alsó ablakban láthatók a kiválasztott tesztcsoporthoz tartozó tesztek.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-290">The upper pane displays test groups, and the lower pane displays the tests that are assigned to a selected test group.</span></span> <span data-ttu-id="e3bd8-291">Egy tesztcsoporthoz több szabályt is hozzá lehet rendelni, például mintavételi tervet, elfogadható minőségi szintet, valamint a romboló teszt követelményét.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-291">You assign several policies to a test group, such as a sampling plan, an AQL, and the requirement for destructive testing.</span></span> <span data-ttu-id="e3bd8-292">Amikor hozzárendel egy különálló tesztet egy tesztcsoporthoz, további adatokat definiálhat, például sorrendet, dokumentumokat és érvényességi dátumokat.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-292">When you assign an individual test to a test group, you define additional information, such as the sequence, documents, and validity dates.</span></span> <span data-ttu-id="e3bd8-293">Mennyiségi teszt esetén a megadott adatok az elfogadható mérési értékeket is tartalmazzák.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-293">For a quantitative test, the information that you define also includes the acceptable measurement values.</span></span> <span data-ttu-id="e3bd8-294">Minőségi teszt esetén az adatok a tesztváltozót és az alapértelmezett eredményt tartalmazzák.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-294">For a qualitative test, the information includes the test variable and default outcome.</span></span> <span data-ttu-id="e3bd8-295">A minőségi rendelésekhez rendelt tesztcsoport meghatározza azokat az alapértelmezett teszteket, amelyeket az adott cikken végre kell hajtani.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-295">The test group that is assigned to a quality order defines the default set of tests that must be performed on the specified item.</span></span> <span data-ttu-id="e3bd8-296">Azonban hozzáadhat, törölhet, vagy módosíthat adott minőségi rendelésre vonatkozó teszteket.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-296">However, you can add, delete, or change tests on the quality order.</span></span> <span data-ttu-id="e3bd8-297">A minőségi rendelés keretében végzett mindegyik tesztnél megtörténik a teszteredmények jelentése.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-297">Test results are reported for each test on a quality order.</span></span></td>
<td><span data-ttu-id="e3bd8-298">Egy gyártóvállalat minőségi irányelveinek minden variációjához meghatároz egy-egy tesztcsoportot.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-298">A manufacturing company defines a test group for each variation of its quality guidelines.</span></span> <span data-ttu-id="e3bd8-299">A különböző tesztcsoportok tükrözik a mintavételi tervek, az együttesen végrehajtandó tesztsorok, az elfogadható mérési értékek, az elfogadható minőségi szint és egyéb tényezők eltéréseit.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-299">The various test groups reflect differences in the sampling plans, the sets of tests that must be performed together, the AQL, and other factors.</span></span> <span data-ttu-id="e3bd8-300">Mennyiségi teszt esetén az elfogadható mérési értékekben is van különbség.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-300">For quantitative tests, there are also differences in the acceptable measurement values.</span></span> <span data-ttu-id="e3bd8-301">A minőségi irányelveinek érvényesítése érdekében a vállalat minden egyes, minőségi rendeléseket automatikusan generáló szabályhoz a <strong>Minőségi társítások</strong> oldalon hozzárendel egy tesztcsoportot, valamint a manuálisan létrehozott minőségi rendelésekhez is hozzárendel egy tesztcsoportot.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-301">To enforce its quality guidelines, the company assigns a test group to each rule for automatically generating quality orders on the <strong>Quality associations</strong> page, and also assigns a test group to quality orders that are manually created.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="e3bd8-302">Cikkminőségi csoportok</span><span class="sxs-lookup"><span data-stu-id="e3bd8-302">Item quality groups</span></span></td>
<td><span data-ttu-id="e3bd8-303">Ezen az oldalon a minőségi csoporthoz rendelt cikkeket, illetve a cikkhez rendelt minőségi csoportokat lehet beállítani, módosítani és megtekinteni.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-303">Use this page to set up, edit, and view the items that are assigned to a quality group or the quality groups that are assigned to an item.</span></span> <span data-ttu-id="e3bd8-304">A minőségi csoport a cikkekre vonatkozó közös tesztkövetelményeket képvisel.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-304">A quality group represents common testing requirements for items.</span></span> <span data-ttu-id="e3bd8-305">Miután a <strong>Tesztcsoportok</strong> oldalon definiálta a tesztkövetelményeket, meghatározhatja a minőségi rendelések automatikus létrehozásának szabályait.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-305">After you define the test requirements on the <strong>Test groups</strong> page, you can define the rules for automatically generating quality orders.</span></span> <span data-ttu-id="e3bd8-306">A folyamat egyszerűsítése érdekében az egyes cikkekhez tartozó szabályokat nem definiáljuk.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-306">To simplify the process, you don&#39;t define rules for individual items.</span></span> <span data-ttu-id="e3bd8-307">Ehelyett egy minőségi csoportra vonatkozó szabályokat definiálhatunk a <strong>Minőségi társítások</strong> oldalon.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-307">Instead, you define rules for a quality group, by using the <strong>Quality associations</strong> page.</span></span> <span data-ttu-id="e3bd8-308">Emellett egy kiválasztott minőségi csoporthoz tartozó <strong>Cikkminőségi csoportok</strong> oldal is használható arra, hogy megfelelő cikkeket az adott csoporthoz rendeljünk.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-308">You can also use the <strong>Item quality groups</strong> page for a selected quality group to assign relevant items to that group.</span></span> <span data-ttu-id="e3bd8-309">Emellett egy kiválasztott cikkhez tartozó <strong>Cikkminőségi csoportok</strong> oldal is használható arra, hogy megfelelő minőségi csoportokat az adott cikkhez rendeljünk.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-309">You can also use the <strong>Item quality groups</strong> page for a selected item to assign relevant quality groups to that item.</span></span></td>
<td><span data-ttu-id="e3bd8-310">Egy gyártóvállalat több nyersanyagot is vásárol, amelyeknél a beérkezéskor szükséges vizsgálatokra ugyanazok a tesztkövetelmények vonatkoznak.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-310">A manufacturing company purchases various raw materials that have the same testing requirements for incoming inspection.</span></span> <span data-ttu-id="e3bd8-311">A vállalat definiál egy minőségi csoportot, majd hozzárendeli a nyersanyagokhoz társított cikkszámokat a csoporthoz.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-311">The company defines a quality group and then assigns the item numbers that are associated with the raw materials to that group.</span></span> <span data-ttu-id="e3bd8-312">Később a vállalat egy új típusú nyersanyagot vásárol, amelyre az előzőekkel azonos tesztkövetelmények vonatkoznak.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-312">Later, the company purchases a new type of raw material that has the same testing requirements.</span></span> <span data-ttu-id="e3bd8-313">Ahelyett, hogy az új anyagra új tesztkövetelményeket állítana be, a vállalat hozzáadja az új anyag cikkszámát a meglévő minőségi csoporthoz.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-313">Instead of setting up new testing requirements for the new material, the company adds the item number for the new material to the existing quality group.</span></span> <span data-ttu-id="e3bd8-314">Ugyanez a gyártóvállalat olyan cikkeket is gyárt, amelyek gyártási tesztjeire ugyanazok a követelmények érvényesek, és olyan cikkeket is szállít, amelyek szállítás előtti tesztjeire ugyanolyan követelmények vonatkoznak.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-314">The same manufacturing company also produces items that have the same production testing requirements and ships items that have the same requirement for pre-shipment testing.</span></span> <span data-ttu-id="e3bd8-315">A vállalat két további minőségi csoportot határoz meg, majd a megfelelő cikkszámokat hozzárendeli az egyes minőségi csoportokhoz.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-315">The company defines two additional quality groups and then assigns the relevant item numbers to each group.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="e3bd8-316">Tesztváltozók</span><span class="sxs-lookup"><span data-stu-id="e3bd8-316">Test variables</span></span></td>
<td><span data-ttu-id="e3bd8-317">Ezen az oldalon meghatározhatja és megtekintheti a minőségi tesztekhez társított változókat.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-317">Use this page to define and view the variables that are associated with a qualitative test.</span></span> <span data-ttu-id="e3bd8-318">Minden változóhoz definiálhat sorszámozott eredményeket, amelyek a szóba jöhető lehetőségeket jelölik.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-318">For each variable, you define enumerated outcomes that represent the possible options.</span></span> <span data-ttu-id="e3bd8-319">Teszteket a <strong>Tesztek</strong> oldalon adhat meg.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-319">You define tests on the <strong>Tests</strong> page.</span></span> <span data-ttu-id="e3bd8-320">Minőségi tesztek esetén a teszt típusát <strong>Lehetőség</strong>-re kell állítania.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-320">For qualitative tests, you must set the test type to <strong>Option</strong>.</span></span> <span data-ttu-id="e3bd8-321">A <strong>Tesztcsoportok</strong> oldal használatával lehet tesztváltozót adott teszthez hozzárendelni.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-321">Use the <strong>Test groups</strong> page to assign a test variable to an individual test.</span></span></td>
<td><span data-ttu-id="e3bd8-322">Egy süteménygyártó a készterméken vizsgálatot végez.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-322">A manufacturing company that produces cookies uses an inspection test for the finished product.</span></span> <span data-ttu-id="e3bd8-323">A vizsgálat tesztnek többféle változója van.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-323">This inspection test has several variables.</span></span> <span data-ttu-id="e3bd8-324">Az egyik változó az íz, ennek lehetséges eredményei: jó és rossz.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-324">One variable is taste, and the possible outcomes for this variable are good and bad.</span></span> <span data-ttu-id="e3bd8-325">Egy másik változó a szín, ennek lehetséges eredményei: túl sötét, túl világos és megfelelő.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-325">A second variable is color, and the possible outcomes are too dark, too light, and correct.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="e3bd8-326">Tesztváltozó eredményei</span><span class="sxs-lookup"><span data-stu-id="e3bd8-326">Test variable outcomes</span></span></td>
<td><span data-ttu-id="e3bd8-327">Ezen az oldalon lehet beállítani, módosítani vagy megtekinteni a minőségi teszthez kapcsolódó tesztváltozó lehetséges teszteredményeit.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-327">Use this page to set up, edit, and to view the possible test results for a test variable that is associated with a qualitative test.</span></span> <span data-ttu-id="e3bd8-328">Mindegyik eredményhez egy <strong>megfelelt</strong> vagy egy <strong>nem felelt meg</strong> állapotot kell hozzárendelni.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-328">For each outcome, you assign a <strong>pass</strong> or <strong>fail</strong> status.</span></span> <span data-ttu-id="e3bd8-329">Minden egyes, a <strong>Tesztek</strong> oldalon megadott minőségi teszthez definiálnia kell egy változót és annak eredményeit.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-329">You must define a variable and its outcomes for each qualitative test that is defined on the <strong>Tests</strong> page.</span></span> <span data-ttu-id="e3bd8-330">(Minőségi tesztek esetén a <strong>Tesztek</strong> oldalon beállított teszttípus <strong>Lehetőség</strong>.) A <strong>Tesztcsoportok</strong> oldal használatával lehet tesztváltozót és az alapértelmezett eredményt adott minőségi teszthez hozzárendelni.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-330">(For qualitative tests, the test type is set to <strong>Option</strong> on the <strong>Tests</strong> page.) Use the <strong>Test groups</strong> page to assign a test variable and the default outcome to an individual qualitative test.</span></span></td>
<td><span data-ttu-id="e3bd8-331">Egy süteménygyártó a készterméken vizsgálatot végez.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-331">A manufacturing company that produces cookies uses an inspection test for the finished product.</span></span> <span data-ttu-id="e3bd8-332">Ennek a vizsgálati tesztnek többféle változója van.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-332">This inspection test has of several variables.</span></span> <span data-ttu-id="e3bd8-333">Az egyik változó az íz, ennek lehetséges eredményei: jó és rossz.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-333">One variable is taste, and the possible outcomes for this variable are good and bad.</span></span> <span data-ttu-id="e3bd8-334">Egy másik változó a szín, ennek lehetséges eredményei: túl sötét, túl világos és megfelelő.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-334">A second variable is color, and the possible outcomes are too dark, too light, and correct.</span></span> <span data-ttu-id="e3bd8-335">Mindegyik eredményhez hozzá van rendelve egy <strong>megfelelt</strong> vagy <strong>nem felelt meg</strong> állapot.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-335">A status of <strong>pass</strong> or <strong>fail</strong> is assigned to each outcome.</span></span> <span data-ttu-id="e3bd8-336">Az egyes változók vizsgálatakor az ellenőr a teszt eredményét az egyik eredmény kiválasztásával jelenti.</span><span class="sxs-lookup"><span data-stu-id="e3bd8-336">During the inspection test for each variable, the inspector reports the test result by selecting one of the outcomes.</span></span></td>
</tr>
</tbody>
</table>



<a name="additional-resources"></a><span data-ttu-id="e3bd8-337">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="e3bd8-337">Additional resources</span></span>
--------

[<span data-ttu-id="e3bd8-338">Minőségkezelési folyamatok</span><span class="sxs-lookup"><span data-stu-id="e3bd8-338">Quality management processes</span></span>](quality-management-processes.md)

[<span data-ttu-id="e3bd8-339">Szabálytalanság kezelésének aktiválása</span><span class="sxs-lookup"><span data-stu-id="e3bd8-339">Enabling nonconformance management</span></span>](enable-nonconformance-management.md)
