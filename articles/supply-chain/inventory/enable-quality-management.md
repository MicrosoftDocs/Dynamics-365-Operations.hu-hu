---
title: Minőségkezelés áttekintése
description: Ez a témakör leírja, hogyan alkalmazza a minőségkezelés funkciót a Dynamics 365 Supply Chain Management szolgáltatásban, hogy ezzel segítse a termékminőség fejlesztését az ön ellátási láncán belül.
author: perlynne
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestAssociationTable, InventTestGroup, InventTestItemQualityGroup, InventTestTable, InventTestVariable, InventTestVariableOutcome
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 23406f68e6ed317025a072eb3377392f0b129626
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5829932"
---
# <a name="quality-management-overview"></a><span data-ttu-id="49dc4-103">Minőségkezelés áttekintése</span><span class="sxs-lookup"><span data-stu-id="49dc4-103">Quality management overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="49dc4-104">Ez a témakör leírja, hogyan alkalmazza a minőségkezelés funkciót a Dynamics 365 Supply Chain Management szolgáltatásban, hogy ezzel segítse a termékminőség fejlesztését az ön ellátási láncán belül.</span><span class="sxs-lookup"><span data-stu-id="49dc4-104">This topic describes how you can use quality management in Dynamics 365 Supply Chain Management to help improve product quality within your supply chain.</span></span>

<span data-ttu-id="49dc4-105">A minőségkezelés segítséget nyújt a szabálytalan termékek javítási folyamatának kezelésében, azok eredetétől függetlenül.</span><span class="sxs-lookup"><span data-stu-id="49dc4-105">Quality management can help you manage turnaround times when you handle nonconforming products, regardless of their point of origin.</span></span> <span data-ttu-id="49dc4-106">Mivel a diagnosztikai típusok javítási jelentésekhez kapcsolódnak, a Supply Chain Management képes beütemezni a problémák megoldásához és azok visszatérésének megelőzéséhez szükséges feladatokat.</span><span class="sxs-lookup"><span data-stu-id="49dc4-106">Because diagnostic types are linked to correction reporting, Supply Chain Management can schedule tasks to correct problems and prevent them from recurring.</span></span>

<span data-ttu-id="49dc4-107">A szabálytalanság kezelésére szolgáló funkció mellett a minőségkezelés egyéb funkciói lehetővé teszik a problémakövetést problématípus (akár belső problémák) szerint, valamint a rövid- és hosszútávú megoldások azonosítását.</span><span class="sxs-lookup"><span data-stu-id="49dc4-107">In addition to functionality for managing nonconformance, quality management includes functionality for tracking issues by problem type (even internal problems), and for identifying solutions as short-term or long-term.</span></span> <span data-ttu-id="49dc4-108">A fő teljesítménymutatókról (KPI-kről) vezetett statisztikák betekintést nyújtanak a múltban megtörtént szabálytalansági problémákba és az azok javítására használt megoldásokba.</span><span class="sxs-lookup"><span data-stu-id="49dc4-108">Statistics about key performance indicators (KPIs) provide insight into the history of previous nonconformance issues and the solutions that were used to correct them.</span></span> <span data-ttu-id="49dc4-109">Az előzményadatok segítségével felülvizsgálhatja a korábbi minőségi mérések hatékonyságát, és kidolgozhatja a jövőben alkalmazni kívánt megfelelő méréseket.</span><span class="sxs-lookup"><span data-stu-id="49dc4-109">You can use historical data to review the effectiveness of previous quality measures and determine appropriate measures to use in the future.</span></span>

<span data-ttu-id="49dc4-110">Mikor beállít egy minőségi társítást, a Supply Chain Management képes létrehozni különféle üzleti folyamatok, események és feltételek minőségi rendeléseit.</span><span class="sxs-lookup"><span data-stu-id="49dc4-110">When you set up a quality association, Supply Chain Management can generate quality orders for various business processes, events, and conditions.</span></span> <span data-ttu-id="49dc4-111">A minőségi társítás vonatkozhat egyetlen cikkre, cikkek egy csoportjára vagy minden cikkre.</span><span class="sxs-lookup"><span data-stu-id="49dc4-111">The quality association can cover a specific item, a specific group of items, or all items.</span></span>

## <a name="examples-of-the-use-of-quality-management"></a><span data-ttu-id="49dc4-112">Példák a minőségkezelés használatára</span><span class="sxs-lookup"><span data-stu-id="49dc4-112">Examples of the use of quality management</span></span>
<span data-ttu-id="49dc4-113">A minőségkezelés rugalmas és sokféle módon megvalósítható, így meg tud felelni az ellátási lánc műveleteinek adott szintjeire vonatkozó követelményeknek.</span><span class="sxs-lookup"><span data-stu-id="49dc4-113">Quality management is flexible and can be implemented in various ways to meet the requirements of specific levels of supply chain operations.</span></span> <span data-ttu-id="49dc4-114">Az alábbi példák ezeknek a funkcióknak a felhasználási lehetőségeit mutatják be.</span><span class="sxs-lookup"><span data-stu-id="49dc4-114">The following examples illustrate possible uses of these features:</span></span>

-   <span data-ttu-id="49dc4-115">Indítson automatikusan minőségellenőrzési folyamatot előre meghatározott feltételek teljesülésekor (adott szállítótól történő beszerzési rendelés raktári regisztrációja alapján).</span><span class="sxs-lookup"><span data-stu-id="49dc4-115">Automatically start a quality control process, based on predefined criteria (upon warehouse registration of a purchase order from a specific vendor).</span></span>
-   <span data-ttu-id="49dc4-116">Vizsgálat alatt zárolja a készletet a jóvá nem hagyott készlet használatának megakadályozása érdekében (a beszerzési rendelési mennyiségek teljes zárolása).</span><span class="sxs-lookup"><span data-stu-id="49dc4-116">Block inventory during inspection to prevent non-approved inventory from being used (full blocking of purchase order quantities).</span></span>
-   <span data-ttu-id="49dc4-117">Az aktuális tényleges készlet vizsgálandó mennyiségének meghatározásához használja a minőségi társítás részét képező cikkmintavételt.</span><span class="sxs-lookup"><span data-stu-id="49dc4-117">Use item sampling as part of a quality association to define the amount of current physical inventory that must be inspected.</span></span> <span data-ttu-id="49dc4-118">A mintavétel történhet rögzített mennyiség, százalékos érték vagy teljes azonosítótábla alapján.</span><span class="sxs-lookup"><span data-stu-id="49dc4-118">Sampling can be based on fixed quantities, a percentage, or full license plate.</span></span>

> [!NOTE]
> <span data-ttu-id="49dc4-119">A _Minőségkezelés a raktári folyamatokhoz_ funkció kiterjeszti a minőségkezelés képességeit.</span><span class="sxs-lookup"><span data-stu-id="49dc4-119">The _Quality management for warehouse processes_ feature extends the capabilities of quality management.</span></span> <span data-ttu-id="49dc4-120">Ha használja ezt a funkciót, akkor tekintse meg a [Minőségkezelés a raktári folyamatokhoz](quality-management-for-warehouses-processes.md) részt példákért, hogy hogyan működik a minőségirányítás a program engedélyezése esetén.</span><span class="sxs-lookup"><span data-stu-id="49dc4-120">If you are using this feature, then see [Quality management for warehouse processes](quality-management-for-warehouses-processes.md) for examples of how quality management works when it's enabled.</span></span>

-   <span data-ttu-id="49dc4-121">A részleges bevételezésekhez minőségi rendeléseket kell létrehozni.</span><span class="sxs-lookup"><span data-stu-id="49dc4-121">Create quality orders for partial receipts.</span></span> <span data-ttu-id="49dc4-122">Ha olyan minőségi rendelést szeretne létrehozni, amely egy rendelésen fizikailag bevételezett mennyiségen alapul, akkor be kell jelölnie a **Frissített mennyiségenként** jelölőnégyzetet a **Cikkmintavétel** űrlapon.</span><span class="sxs-lookup"><span data-stu-id="49dc4-122">To create a quality order that is based on the quantity that is physically received with an order, you must select the **Per updated quantity** check box on the **Item sampling** form.</span></span>
-   <span data-ttu-id="49dc4-123">Hozzon létre minimum, maximum és cél tesztértékeket magukban foglaló teszttípusokat, és végezzen előre definiált ellenőrzési eredményeket adó minőségi-mennyiségi teszteket.</span><span class="sxs-lookup"><span data-stu-id="49dc4-123">Create test types that include minimum, maximum, and target test values, and perform qualitative-versus-quantitative testing that has predefined validation results.</span></span>
-   <span data-ttu-id="49dc4-124">Adja meg az elfogadható minőségi szint értékét a minőségi mérések tűréshatárainak szabályozása érdekében.</span><span class="sxs-lookup"><span data-stu-id="49dc4-124">Specify an acceptable quality level (AQL) to control quality measure tolerances.</span></span>
-   <span data-ttu-id="49dc4-125">Határozza meg a vizsgálati művelethez szükséges erőforrásokat (például tesztterület és tesztműszerek).</span><span class="sxs-lookup"><span data-stu-id="49dc4-125">Specify the resources that an inspection operation requires, such as a test area and test instruments.</span></span>

## <a name="working-with-quality-associations"></a><span data-ttu-id="49dc4-126">Minőségi társítások használata</span><span class="sxs-lookup"><span data-stu-id="49dc4-126">Working with quality associations</span></span>
<span data-ttu-id="49dc4-127">Egy minőségi társítást használó üzleti folyamat különféle forrásbizonylatokkal lehet kapcsolatban (például beszerzési rendelésekkel, értékesítési rendelésekkel, vagy termelési rendelésekkel).</span><span class="sxs-lookup"><span data-stu-id="49dc4-127">The business process that uses a quality association can be related to various source documents, such as purchase orders, sales orders, or production orders.</span></span>

<span data-ttu-id="49dc4-128">Minden egyes minőségi társítási rekord meghatározza a létrehozott minőségi rendelésekre vonatkozó teszteket, elfogadható minőségi szintet és mintavételi eljárást.</span><span class="sxs-lookup"><span data-stu-id="49dc4-128">Each quality association record defines the set of tests, the AQL, and the sampling plan that applies to the quality orders that are generated.</span></span> <span data-ttu-id="49dc4-129">Az üzleti folyamat minden egyes változatára definiálnia kell egy minőségi társítási rekordot.</span><span class="sxs-lookup"><span data-stu-id="49dc4-129">You must define a quality association record for each variation in a business process.</span></span> <span data-ttu-id="49dc4-130">Például beállíthat egy olyan minőségi társítást, amely egy beszerzési rendelés termékbevételezésének frissítésekor létrehoz egy minőségi rendelést.</span><span class="sxs-lookup"><span data-stu-id="49dc4-130">For example, you can set up a quality association that generates a quality order when a purchase order product receipt is updated.</span></span> <span data-ttu-id="49dc4-131">A végrehajtási terv beállításától függően letiltható maga az indító folyamat, ha van egy nyitott minőségi rendelés, vagy letilthatóak az ezután következő folyamatok, például a beszerzési rendelés számlázása.</span><span class="sxs-lookup"><span data-stu-id="49dc4-131">Depending on the setup of the execution plan, the triggering process itself can be blocked while there is an open quality order, or the next processes, such as purchase order invoicing, can be blocked.</span></span>

<span data-ttu-id="49dc4-132">**Megjegyzés:** Amíg vannak nyitott minőségi rendelések, a készletmennyiségek kiadása automatikusan le van tiltva.</span><span class="sxs-lookup"><span data-stu-id="49dc4-132">**Note:** While there are open quality orders, inventory quantities are automatically blocked from being issued.</span></span> <span data-ttu-id="49dc4-133">A **Cikkmintavételek** lap **Teljes zárolás** beállításától függően a mennyiség a minőségi rendelésen vagy a forrásbizonylat sorában szereplő mennyiség lehet.</span><span class="sxs-lookup"><span data-stu-id="49dc4-133">Depending on the **Full blocking** setting on the **Item samplings** page, the quantity is either the quantity on the quality order or the quantity on the source document line.</span></span>

<span data-ttu-id="49dc4-134">Egy adott üzleti folyamatra a minőségi társítási rekord azonosítja azokat az eseményeket és feltételeket, amelyek fennállása esetén a minőségi rendelés létrejön.</span><span class="sxs-lookup"><span data-stu-id="49dc4-134">For a given business process, the quality association record identifies the event and the conditions that a quality order is generated for.</span></span> <span data-ttu-id="49dc4-135">A feltételek helyre vagy jogi személyre vonatkozhatnak.</span><span class="sxs-lookup"><span data-stu-id="49dc4-135">The conditions can be specific to either a site or a legal entity.</span></span> <span data-ttu-id="49dc4-136">Romboló teszteket igénylő minőségi rendelés csak akkor generálható, ha az eseményhez létezik aktuális készlet.</span><span class="sxs-lookup"><span data-stu-id="49dc4-136">A quality order that involves destructive tests can be generated only when on-hand inventory exists for the event.</span></span>

<span data-ttu-id="49dc4-137">A következő példák bemutatják egy minőségi társítási rekord meghatározását az egyes üzleti folyamatok változásainak megfelelően.</span><span class="sxs-lookup"><span data-stu-id="49dc4-137">The following examples illustrate how a quality association record is defined for the variations in each business process.</span></span> <span data-ttu-id="49dc4-138">Egy minőségi társítási rekord által az egyes példák esetén meghatározott eseményeket és feltételeket az alábbi táblázat összegzi.</span><span class="sxs-lookup"><span data-stu-id="49dc4-138">For each example, the following table summarizes the events and conditions that are defined by a quality association record.</span></span>

<table>
<tbody>
<tr>
<th><span data-ttu-id="49dc4-139">Hivatkozás típusa</span><span class="sxs-lookup"><span data-stu-id="49dc4-139">Reference type</span></span></th>
<th><span data-ttu-id="49dc4-140">Eseménytípus</span><span class="sxs-lookup"><span data-stu-id="49dc4-140">Event type</span></span></th>
<th><span data-ttu-id="49dc4-141">Végrehajtás</span><span class="sxs-lookup"><span data-stu-id="49dc4-141">Execution</span></span></th>
<th><span data-ttu-id="49dc4-142">Eseményzárolás</span><span class="sxs-lookup"><span data-stu-id="49dc4-142">Event blocking</span></span></th>
<th><span data-ttu-id="49dc4-143">Dokumentumhivatkozás</span><span class="sxs-lookup"><span data-stu-id="49dc4-143">Document reference</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="49dc4-144">Készlet</span><span class="sxs-lookup"><span data-stu-id="49dc4-144">Inventory</span></span></td>
<td><span data-ttu-id="49dc4-145">Nem alkalmazható</span><span class="sxs-lookup"><span data-stu-id="49dc4-145">Not applicable</span></span></td>
<td><span data-ttu-id="49dc4-146">Nem alkalmazható</span><span class="sxs-lookup"><span data-stu-id="49dc4-146">Not applicable</span></span></td>
<td><span data-ttu-id="49dc4-147">Egyik sem</span><span class="sxs-lookup"><span data-stu-id="49dc4-147">None</span></span></td>
<td><span data-ttu-id="49dc4-148">Mind</span><span class="sxs-lookup"><span data-stu-id="49dc4-148">All</span></span></td>
</tr>
<tr>
<td rowspan="7"><span data-ttu-id="49dc4-149">Értékesítés</span><span class="sxs-lookup"><span data-stu-id="49dc4-149">Sales</span></span></td>
<td rowspan="4"><span data-ttu-id="49dc4-150">Kitárolási folyamat ütemezve</span><span class="sxs-lookup"><span data-stu-id="49dc4-150">Picking process is scheduled</span></span></td>
<td rowspan="4"><span data-ttu-id="49dc4-151">Előtte</span><span class="sxs-lookup"><span data-stu-id="49dc4-151">Before</span></span></td>
<td><span data-ttu-id="49dc4-152">Egyik sem</span><span class="sxs-lookup"><span data-stu-id="49dc4-152">None</span></span></td>
<td rowspan="22"><span data-ttu-id="49dc4-153">Csak Egyedi azonosító, Csoport vagy Mind</span><span class="sxs-lookup"><span data-stu-id="49dc4-153">Specific ID, Group, or All only</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="49dc4-154">Kitárolási folyamat</span><span class="sxs-lookup"><span data-stu-id="49dc4-154">Picking process</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="49dc4-155">Szállítólevél</span><span class="sxs-lookup"><span data-stu-id="49dc4-155">Packing slip</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="49dc4-156">Számla</span><span class="sxs-lookup"><span data-stu-id="49dc4-156">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="49dc4-157">Szállítólevél</span><span class="sxs-lookup"><span data-stu-id="49dc4-157">Packing slip</span></span></td>
<td rowspan="3"><span data-ttu-id="49dc4-158">Előtte</span><span class="sxs-lookup"><span data-stu-id="49dc4-158">Before</span></span></td>
<td><span data-ttu-id="49dc4-159">Egyik sem</span><span class="sxs-lookup"><span data-stu-id="49dc4-159">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="49dc4-160">Szállítólevél</span><span class="sxs-lookup"><span data-stu-id="49dc4-160">Packing slip</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="49dc4-161">Számla</span><span class="sxs-lookup"><span data-stu-id="49dc4-161">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="15"><span data-ttu-id="49dc4-162">Beszerzés</span><span class="sxs-lookup"><span data-stu-id="49dc4-162">Purchase</span></span></td>
<td rowspan="7"><span data-ttu-id="49dc4-163">Bevételezési lista</span><span class="sxs-lookup"><span data-stu-id="49dc4-163">Receipt list</span></span></td>
<td rowspan="4"><span data-ttu-id="49dc4-164">Előtte</span><span class="sxs-lookup"><span data-stu-id="49dc4-164">Before</span></span></td>
<td><span data-ttu-id="49dc4-165">Egyik sem</span><span class="sxs-lookup"><span data-stu-id="49dc4-165">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="49dc4-166">Bevételezési lista</span><span class="sxs-lookup"><span data-stu-id="49dc4-166">Receipt list</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="49dc4-167">Termékbevételezés</span><span class="sxs-lookup"><span data-stu-id="49dc4-167">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="49dc4-168">Számla</span><span class="sxs-lookup"><span data-stu-id="49dc4-168">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="49dc4-169">Utána</span><span class="sxs-lookup"><span data-stu-id="49dc4-169">After</span></span></td>
<td><span data-ttu-id="49dc4-170">Egyik sem</span><span class="sxs-lookup"><span data-stu-id="49dc4-170">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="49dc4-171">Termékbevételezés</span><span class="sxs-lookup"><span data-stu-id="49dc4-171">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="49dc4-172">Számla</span><span class="sxs-lookup"><span data-stu-id="49dc4-172">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="49dc4-173">Nyilvántartás</span><span class="sxs-lookup"><span data-stu-id="49dc4-173">Registration</span></span></td>
<td rowspan="3"><span data-ttu-id="49dc4-174">Nem alkalmazható</span><span class="sxs-lookup"><span data-stu-id="49dc4-174">Not applicable</span></span></td>
<td><span data-ttu-id="49dc4-175">Egyik sem</span><span class="sxs-lookup"><span data-stu-id="49dc4-175">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="49dc4-176">Termékbevételezés</span><span class="sxs-lookup"><span data-stu-id="49dc4-176">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="49dc4-177">Számla</span><span class="sxs-lookup"><span data-stu-id="49dc4-177">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="5"><span data-ttu-id="49dc4-178">Termékbevételezés</span><span class="sxs-lookup"><span data-stu-id="49dc4-178">Product receipt</span></span></td>
<td rowspan="3"><span data-ttu-id="49dc4-179">Előtte</span><span class="sxs-lookup"><span data-stu-id="49dc4-179">Before</span></span></td>
<td><span data-ttu-id="49dc4-180">Egyik sem</span><span class="sxs-lookup"><span data-stu-id="49dc4-180">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="49dc4-181">Termékbevételezés</span><span class="sxs-lookup"><span data-stu-id="49dc4-181">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="49dc4-182">Számla</span><span class="sxs-lookup"><span data-stu-id="49dc4-182">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="2"><span data-ttu-id="49dc4-183">Utána</span><span class="sxs-lookup"><span data-stu-id="49dc4-183">After</span></span></td>
<td><span data-ttu-id="49dc4-184">Egyik sem</span><span class="sxs-lookup"><span data-stu-id="49dc4-184">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="49dc4-185">Számla</span><span class="sxs-lookup"><span data-stu-id="49dc4-185">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="8"><span data-ttu-id="49dc4-186">Termelés</span><span class="sxs-lookup"><span data-stu-id="49dc4-186">Production</span></span></td>
<td rowspan="3"><span data-ttu-id="49dc4-187">Nyilvántartás</span><span class="sxs-lookup"><span data-stu-id="49dc4-187">Registration</span></span></td>
<td rowspan="3"><span data-ttu-id="49dc4-188">Nem alkalmazható</span><span class="sxs-lookup"><span data-stu-id="49dc4-188">Not applicable</span></span></td>
<td><span data-ttu-id="49dc4-189">Egyik sem</span><span class="sxs-lookup"><span data-stu-id="49dc4-189">None</span></span></td>
<td rowspan="12"><span data-ttu-id="49dc4-190">Mind</span><span class="sxs-lookup"><span data-stu-id="49dc4-190">All</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="49dc4-191">Készként jelentés</span><span class="sxs-lookup"><span data-stu-id="49dc4-191">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="49dc4-192">Záró</span><span class="sxs-lookup"><span data-stu-id="49dc4-192">End</span></span></td>
</tr>
<tr>
<td rowspan="5"><span data-ttu-id="49dc4-193">Készként jelentés</span><span class="sxs-lookup"><span data-stu-id="49dc4-193">Report as finished</span></span></td>
<td rowspan="3"><span data-ttu-id="49dc4-194">Előtte</span><span class="sxs-lookup"><span data-stu-id="49dc4-194">Before</span></span></td>
<td><span data-ttu-id="49dc4-195">Egyik sem</span><span class="sxs-lookup"><span data-stu-id="49dc4-195">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="49dc4-196">Készként jelentés</span><span class="sxs-lookup"><span data-stu-id="49dc4-196">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="49dc4-197">Záró</span><span class="sxs-lookup"><span data-stu-id="49dc4-197">End</span></span></td>
</tr>
<tr>
<td rowspan="2"><span data-ttu-id="49dc4-198">Utána</span><span class="sxs-lookup"><span data-stu-id="49dc4-198">After</span></span></td>
<td><span data-ttu-id="49dc4-199">Egyik sem</span><span class="sxs-lookup"><span data-stu-id="49dc4-199">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="49dc4-200">Záró</span><span class="sxs-lookup"><span data-stu-id="49dc4-200">End</span></span></td>
</tr>
<tr>
<td rowspan="4"><span data-ttu-id="49dc4-201">Karantén</span><span class="sxs-lookup"><span data-stu-id="49dc4-201">Quarantine</span></span></td>
<td rowspan="3"><span data-ttu-id="49dc4-202">Készként jelentés</span><span class="sxs-lookup"><span data-stu-id="49dc4-202">Report as finished</span></span></td>
<td rowspan="2"><span data-ttu-id="49dc4-203">Előtte</span><span class="sxs-lookup"><span data-stu-id="49dc4-203">Before</span></span></td>
<td><span data-ttu-id="49dc4-204">Készként jelentés</span><span class="sxs-lookup"><span data-stu-id="49dc4-204">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="49dc4-205">Záró</span><span class="sxs-lookup"><span data-stu-id="49dc4-205">End</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="49dc4-206">Utána</span><span class="sxs-lookup"><span data-stu-id="49dc4-206">After</span></span></td>
<td><span data-ttu-id="49dc4-207">Záró</span><span class="sxs-lookup"><span data-stu-id="49dc4-207">End</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="49dc4-208">Záró</span><span class="sxs-lookup"><span data-stu-id="49dc4-208">End</span></span></td>
<td><span data-ttu-id="49dc4-209">Előtte</span><span class="sxs-lookup"><span data-stu-id="49dc4-209">Before</span></span></td>
<td><span data-ttu-id="49dc4-210">Záró</span><span class="sxs-lookup"><span data-stu-id="49dc4-210">End</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="49dc4-211">Útvonalművelet</span><span class="sxs-lookup"><span data-stu-id="49dc4-211">Route operation</span></span></td>
<td rowspan="3"><span data-ttu-id="49dc4-212">Készként jelentés</span><span class="sxs-lookup"><span data-stu-id="49dc4-212">Report as finished</span></span></td>
<td rowspan="2"><span data-ttu-id="49dc4-213">Előtte</span><span class="sxs-lookup"><span data-stu-id="49dc4-213">Before</span></span></td>
<td><span data-ttu-id="49dc4-214">Egyik sem</span><span class="sxs-lookup"><span data-stu-id="49dc4-214">None</span></span></td>
<td rowspan="3"><span data-ttu-id="49dc4-215">Egyedi azonosító, Csoport vagy Mind, valamint Erőforrás-specifikus, Csoport vagy Mind</span><span class="sxs-lookup"><span data-stu-id="49dc4-215">Specific ID, Group, or All, and Resource specific, Group, or All</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="49dc4-216">Készként jelentés</span><span class="sxs-lookup"><span data-stu-id="49dc4-216">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="49dc4-217">Utána</span><span class="sxs-lookup"><span data-stu-id="49dc4-217">After</span></span></td>
<td><span data-ttu-id="49dc4-218">Egyik sem</span><span class="sxs-lookup"><span data-stu-id="49dc4-218">None</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="49dc4-219">Társtermék gyártása</span><span class="sxs-lookup"><span data-stu-id="49dc4-219">Co-product production</span></span></td>
<td><span data-ttu-id="49dc4-220">Nyilvántartás</span><span class="sxs-lookup"><span data-stu-id="49dc4-220">Registration</span></span></td>
<td><span data-ttu-id="49dc4-221">Nem alkalmazható</span><span class="sxs-lookup"><span data-stu-id="49dc4-221">Not applicable</span></span></td>
<td rowspan="3"><span data-ttu-id="49dc4-222">Egyik sem</span><span class="sxs-lookup"><span data-stu-id="49dc4-222">None</span></span></td>
<td rowspan="3"><span data-ttu-id="49dc4-223">Mind</span><span class="sxs-lookup"><span data-stu-id="49dc4-223">All</span></span></td>
</tr>
<tr>
<td rowspan="2"><span data-ttu-id="49dc4-224">Készként jelentés</span><span class="sxs-lookup"><span data-stu-id="49dc4-224">Report as finished</span></span></td>
<td><span data-ttu-id="49dc4-225">Előtte</span><span class="sxs-lookup"><span data-stu-id="49dc4-225">Before</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="49dc4-226">Utána</span><span class="sxs-lookup"><span data-stu-id="49dc4-226">After</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="49dc4-227">A következő táblázatban bővebben tájékozódhat arról, hogy hogyan hozhatóak létre minőségi rendelések adott típusú folyamatokhoz.</span><span class="sxs-lookup"><span data-stu-id="49dc4-227">The following table provides more information about how quality orders can be generated for specific types of processes.</span></span>
<div class="tableSection">

<table>
<tbody>
<tr>
<th><span data-ttu-id="49dc4-228">Folyamat típusa</span><span class="sxs-lookup"><span data-stu-id="49dc4-228">Type of process</span></span></th>
<th><span data-ttu-id="49dc4-229">Mikor hozhatóak létre automatikusan minőségi rendelések?</span><span class="sxs-lookup"><span data-stu-id="49dc4-229">When quality orders can be automatically generated</span></span></th>
<th><span data-ttu-id="49dc4-230">Mikor hozhatóak létre minőségi rendelések, amennyiben romboló tesztekre van szükség?</span><span class="sxs-lookup"><span data-stu-id="49dc4-230">When quality orders can be generated if destructive testing is required</span></span></th>
<th><span data-ttu-id="49dc4-231">Feltételekre vonatkozó információ</span><span class="sxs-lookup"><span data-stu-id="49dc4-231">Condition information</span></span></th>
<th><span data-ttu-id="49dc4-232">Manuális létrehozásra vonatkozó információ</span><span class="sxs-lookup"><span data-stu-id="49dc4-232">Manual generation information</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="49dc4-233">Beszerzési rendelés</span><span class="sxs-lookup"><span data-stu-id="49dc4-233">Purchase order</span></span></td>
<td><span data-ttu-id="49dc4-234">A bevételezett anyagra vonatkozó bevételezési lista vagy termékbevételezés feladása előtt vagy után</span><span class="sxs-lookup"><span data-stu-id="49dc4-234">Before or after a receipts list or product receipt for the material that is received is posted</span></span></td>
<td><span data-ttu-id="49dc4-235">A bevételezett anyagra vonatkozó termékbevételezés feladása után, mivel az anyagnak rendelkezésre kell állnia a romboló teszt elvégzéséhez</span><span class="sxs-lookup"><span data-stu-id="49dc4-235">After the product receipt for the material that is received is posted, because the material must be available for destructive testing</span></span></td>
<td><span data-ttu-id="49dc4-236">A minőségi rendelés követelménye vonatkozhat egy adott telephelyre, cikkre vagy szállítóra, illetve ezek bármilyen kombinációjára.</span><span class="sxs-lookup"><span data-stu-id="49dc4-236">The requirement for a quality order can reflect a particular site, item, or vendor, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="49dc4-237">A beszerzési rendelésekhez manuálisan generált minőségi rendelésekben felhasználhatók a minőségi társítási rekordban szereplő adatok, például a mintavételezési eljárás.</span><span class="sxs-lookup"><span data-stu-id="49dc4-237">A manually generated quality order that refers to a purchase order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="49dc4-238">Karanténutasítás</span><span class="sxs-lookup"><span data-stu-id="49dc4-238">Quarantine order</span></span></td>
<td><span data-ttu-id="49dc4-239">Mielőtt vagy miután a karanténutasítás készként lett jelentve vagy befejeződött</span><span class="sxs-lookup"><span data-stu-id="49dc4-239">Before or after the quarantine order is reported as finished or ended</span></span></td>
<td><span data-ttu-id="49dc4-240">Romboló teszteket igénylő minőségi rendelések nem hozhatóak létre.</span><span class="sxs-lookup"><span data-stu-id="49dc4-240">Quality orders that require destructive tests can&#39;t be generated.</span></span> <span data-ttu-id="49dc4-241">A rendszer feltételezi, hogy a karanténutasítás funkció kezeli a roncsolt anyag elhelyezését.</span><span class="sxs-lookup"><span data-stu-id="49dc4-241">It&#39;s assumed that the quarantine order functionality handles the disposition of the material that is destroyed.</span></span></td>
<td><span data-ttu-id="49dc4-242">A minőségi rendelés követelménye vonatkozhat egy adott telephelyre, cikkre vagy szállítóra, illetve ezek bármilyen kombinációjára.</span><span class="sxs-lookup"><span data-stu-id="49dc4-242">The requirement for a quality order can reflect a particular site, item, or vendor, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="49dc4-243">A karanténutasításokhoz manuálisan generált minőségi rendelésekben felhasználhatók a minőségi társítási rekordban szereplő adatok, például a mintavételezési eljárás.</span><span class="sxs-lookup"><span data-stu-id="49dc4-243">A manually generated quality order that refers to a quarantine order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="49dc4-244">Értékesítési rendelés</span><span class="sxs-lookup"><span data-stu-id="49dc4-244">Sales order</span></span></td>
<td><span data-ttu-id="49dc4-245">A szállított cikkekre vonatkozó ütemezett kitárolási folyamat vagy szállítólevél frissítése előtt</span><span class="sxs-lookup"><span data-stu-id="49dc4-245">Before a scheduled picking process or packing slip update for the items that are being shipped</span></span></td>
<td><span data-ttu-id="49dc4-246">Bármelyik lépésnél</span><span class="sxs-lookup"><span data-stu-id="49dc4-246">At any step</span></span></td>
<td><span data-ttu-id="49dc4-247">A minőségi rendelés követelménye vonatkozhat egy adott telephelyre, cikkre vagy vevőre, illetve ezek bármilyen kombinációjára.</span><span class="sxs-lookup"><span data-stu-id="49dc4-247">The requirement for a quality order can reflect a particular site, item, or customer, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="49dc4-248">Az értékesítési rendelésekhez manuálisan generált minőségi rendelésekben felhasználhatók a minőségi társítási rekordban szereplő adatok, például a mintavételezési eljárás.</span><span class="sxs-lookup"><span data-stu-id="49dc4-248">A manually generated quality order that refers to a sales order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="49dc4-249">Termelési rendelés</span><span class="sxs-lookup"><span data-stu-id="49dc4-249">Production order</span></span></td>
<td><span data-ttu-id="49dc4-250">A termelési rendelés befejezett mennyiségének jelentése előtt vagy után</span><span class="sxs-lookup"><span data-stu-id="49dc4-250">Before or after the finished quantity for the production order is reported</span></span></td>
<td><span data-ttu-id="49dc4-251">A termelési rendelés befejezett mennyiségének jelentése után</span><span class="sxs-lookup"><span data-stu-id="49dc4-251">After the finished quantity for the production order is reported</span></span></td>
<td><span data-ttu-id="49dc4-252">A minőségi rendelés követelménye vonatkozhat egy adott telephelyre vagy vevőre, illetve ezek kombinációjára.</span><span class="sxs-lookup"><span data-stu-id="49dc4-252">The requirement for a quality order can reflect a particular site or item, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="49dc4-253">A termelési rendelésekhez manuálisan generált minőségi rendelésekben felhasználhatók a minőségi társítási rekordban szereplő adatok, például a mintavételezési eljárás.</span><span class="sxs-lookup"><span data-stu-id="49dc4-253">A manually generated quality order that refers to a production order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="49dc4-254">Útvonalművelettel rendelkező termelési utasítás</span><span class="sxs-lookup"><span data-stu-id="49dc4-254">Production order that has a route operation</span></span></td>
<td><span data-ttu-id="49dc4-255">A műveletre vonatkozó jelentés befejezése előtt vagy után</span><span class="sxs-lookup"><span data-stu-id="49dc4-255">Before or after the report is finished for an operation</span></span></td>
<td><span data-ttu-id="49dc4-256">Miután az utolsó művelet készként való jelentése megtörtént</span><span class="sxs-lookup"><span data-stu-id="49dc4-256">After the reporting production is finished for the last operation</span></span></td>
<td><span data-ttu-id="49dc4-257">A minőségi rendelés követelménye vonatkozhat egy adott telephelyre, cikkre, vevőre vagy üzemi erőforrásra, illetve ezek bármilyen kombinációjára.</span><span class="sxs-lookup"><span data-stu-id="49dc4-257">The requirement for a quality order can reflect a particular, site, item, or operations resource, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="49dc4-258">Az útvonalművelethez manuálisan generált minőségi rendelésekben felhasználhatók a minőségi társítási rekordban szereplő adatok, például a mintavételezési eljárás.</span><span class="sxs-lookup"><span data-stu-id="49dc4-258">A manually generated quality order that refers to a route operation can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="49dc4-259">Készlet</span><span class="sxs-lookup"><span data-stu-id="49dc4-259">Inventory</span></span></td>
<td><span data-ttu-id="49dc4-260">A készletnaplón belüli tranzakciókhoz és az átmozgatási rendelési tranzakciókhoz nem generálhatók automatikusan minőségi rendelések.</span><span class="sxs-lookup"><span data-stu-id="49dc4-260">A quality order cannot be automatically generated for a transaction in an inventory journal or for transfer order transactions.</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="49dc4-261">Cikk készletmennyiségére vonatkozó minőségi rendelést manuálisan kell létrehozni.</span><span class="sxs-lookup"><span data-stu-id="49dc4-261">A quality order must be created manually for an item&#39;s inventory quantity.</span></span> <span data-ttu-id="49dc4-262">Tényleges aktuális készlet szükséges.</span><span class="sxs-lookup"><span data-stu-id="49dc4-262">Physical on-hand inventory is required.</span></span></td>
</tr>
</tbody>
</table>

## <a name="quality-order-auto-generation-examples"></a><span data-ttu-id="49dc4-263">Minőségi rendelési automatikus generálásával kapcsolatos példák</span><span class="sxs-lookup"><span data-stu-id="49dc4-263">Quality order auto-generation examples</span></span>

### <a name="purchasing"></a><span data-ttu-id="49dc4-264">Beszerzés</span><span class="sxs-lookup"><span data-stu-id="49dc4-264">Purchasing</span></span>

<span data-ttu-id="49dc4-265">Ha a beszerzés modulban az **Eseménytípus** mezőt a **Termék nyugtája** értékre állítja, a **Végrehajtás** mezőt pedig **Után** értékre a **Minőségi társítások** lapon, akkor a következő eredményeket kapja:</span><span class="sxs-lookup"><span data-stu-id="49dc4-265">In purchasing, if you set the **Event type** field to **Product receipt** and the **Execution** field to **After** on the **Quality associations** page, you get the following results:</span></span> 

- <span data-ttu-id="49dc4-266">Ha a **Frissített mennyiség** beállítás **Igen** értékre van állítva , akkor a program minőségi rendelést hoz létre a beszerzési rendeléshez tartozó összes bevételezéshez, a bevételezett mennyiség és a cikkmintavétel beállításai alapján.</span><span class="sxs-lookup"><span data-stu-id="49dc4-266">If the **Per updated quantity** option is set to **Yes**, a quality order is generated for every receipt against the purchase order, based on the received quantity and settings in the item sampling.</span></span> <span data-ttu-id="49dc4-267">Minden alkalommal, amikor egy mennyiséget a beszerzési rendeléssel szemben megkapnak, új minőségi rendelések jönnek létre az újonnan megkapott mennyiség alapján.</span><span class="sxs-lookup"><span data-stu-id="49dc4-267">Every time that a quantity is received against the purchase order, new quality orders are generated based on the newly received quantity.</span></span>
- <span data-ttu-id="49dc4-268">Ha a **Frissített mennyiség** beállítás **Igen** értékre van állítva , akkor a program minőségi rendelést hoz létre a beszerzési rendeléshez tartozó első bevételezéshez, a bevételezett mennyiség és a cikkmintavétel beállításai alapján.</span><span class="sxs-lookup"><span data-stu-id="49dc4-268">If the **Per updated quantity** option is set to **No**, a quality order is generated for the first receipt against the purchase order, based on the received quantity.</span></span> <span data-ttu-id="49dc4-269">Ezenkívül a program egy vagy több minőségi rendelést hoz létre a fennmaradó mennyiség alapján, a nyomon követési dimenziók függvényében.</span><span class="sxs-lookup"><span data-stu-id="49dc4-269">Additionally, one or more quality orders are created based on the remaining quantity, depending on the tracking dimensions.</span></span> <span data-ttu-id="49dc4-270">Nem jönnek létre minőségi rendelések a beszerzési rendelés későbbi bevételezéseihez.</span><span class="sxs-lookup"><span data-stu-id="49dc4-270">Quality orders aren't generated for subsequent receipts against the purchase order.</span></span>

### <a name="production"></a><span data-ttu-id="49dc4-271">Termelés</span><span class="sxs-lookup"><span data-stu-id="49dc4-271">Production</span></span>

<span data-ttu-id="49dc4-272">Ha a gyártásban az **Eseménytípus** mezőt a **Befejezettnek jelentés** értékre állítja, a **Végrehajtás** mezőt pedig **Után** értékre a **Minőségi társítások** lapon, akkor a következő eredményeket kapja:</span><span class="sxs-lookup"><span data-stu-id="49dc4-272">In production, if you set the **Event type** field to **Report as finished** and the **Execution** field to **After** on the **Quality associations** page, you get the following results:</span></span>

- <span data-ttu-id="49dc4-273">Ha a **Frissített mennyiség** beállítás **Igen** értékre van állítva , akkor a program minőségi rendelést hoz létre minden befejezett mennyiség és a cikkmintavételezés beállításai alapján.</span><span class="sxs-lookup"><span data-stu-id="49dc4-273">If the **Per updated quantity** option is set to **Yes**, a quality order is generated based on every finished quantity and settings in the item sampling.</span></span> <span data-ttu-id="49dc4-274">Minden alkalommal, amikor egy mennyiséget a beszerzési rendeléssel szemben késznek jelentenek, új minőségi rendelések jönnek létre az újonnan elkészült mennyiség alapján.</span><span class="sxs-lookup"><span data-stu-id="49dc4-274">Every time that a quantity is reported as finished against the production order, new quality orders are generated based on newly finished quantity.</span></span> <span data-ttu-id="49dc4-275">Ez a generálási logika összhangban van a beszerzéssel.</span><span class="sxs-lookup"><span data-stu-id="49dc4-275">This generation logic is consistent with purchasing.</span></span>
- <span data-ttu-id="49dc4-276">Ha a **Frissített mennyiség** beállítás **Igen** értékre van állítva , akkor a program minőségi rendelést hoz létre az első alkalommal, amikor a mennyiség készek van jelentve, a kész mennyiség és a cikkmintavétel beállításai alapján.</span><span class="sxs-lookup"><span data-stu-id="49dc4-276">If the **Per updated quantity** option is set to **No**, a quality order is generated the first time that a quantity is reported as finished, based on the finished quantity.</span></span> <span data-ttu-id="49dc4-277">Ezenkívül a program egy vagy több minőségi rendelést hoz létre a fennmaradó mennyiség alapján, a cikkmintavételezés nyomon követési dimenziói függvényében.</span><span class="sxs-lookup"><span data-stu-id="49dc4-277">Additionally, one or more quality orders are created based on the remaining quantity, depending on the tracking dimensions of the item sampling.</span></span> <span data-ttu-id="49dc4-278">A további kész mennyiségek esetében nem jönnek létre minőségi rendelések.</span><span class="sxs-lookup"><span data-stu-id="49dc4-278">Quality orders aren't generated for subsequent finished quantities.</span></span>

<table>
<tbody>
<tr>
<th><span data-ttu-id="49dc4-279">Minőség megadása</span><span class="sxs-lookup"><span data-stu-id="49dc4-279">Quality specification</span></span></th>
<th><span data-ttu-id="49dc4-280">Frissített mennyiségenként</span><span class="sxs-lookup"><span data-stu-id="49dc4-280">Per updated quantity</span></span></th>
<th><span data-ttu-id="49dc4-281">Nyomon követési dimenziónként</span><span class="sxs-lookup"><span data-stu-id="49dc4-281">Per tracking dimension</span></span></th>
<th><span data-ttu-id="49dc4-282">Eredmény</span><span class="sxs-lookup"><span data-stu-id="49dc4-282">Result</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="49dc4-283">Százalék: 10%</span><span class="sxs-lookup"><span data-stu-id="49dc4-283">Percentage: 10%</span></span></td>
<td><span data-ttu-id="49dc4-284">Igen</span><span class="sxs-lookup"><span data-stu-id="49dc4-284">Yes</span></span></td>
<td>
<p><span data-ttu-id="49dc4-285">Kötegszám: Nincs</span><span class="sxs-lookup"><span data-stu-id="49dc4-285">Batch number: No</span></span></p>
<p><span data-ttu-id="49dc4-286">Sorozatszám: Nincs</span><span class="sxs-lookup"><span data-stu-id="49dc4-286">Serial number: No</span></span></p>
</td>
<td>
<p><span data-ttu-id="49dc4-287">Rendelt mennyiség: 100</span><span class="sxs-lookup"><span data-stu-id="49dc4-287">Order quantity: 100</span></span></p>
<ol>
<li><span data-ttu-id="49dc4-288">Készként jelentés 30-hoz</span><span class="sxs-lookup"><span data-stu-id="49dc4-288">Report as finished for 30</span></span>
<ul>
<li><span data-ttu-id="49dc4-289">1. minőségi rendelés 3-hoz (A 30 10%-a)</span><span class="sxs-lookup"><span data-stu-id="49dc4-289">Quality order #1 for 3 (10% of 30)</span></span></li>
</ul>
</li>
<li><span data-ttu-id="49dc4-290">Készként jelentés 70-hoz</span><span class="sxs-lookup"><span data-stu-id="49dc4-290">Report as finished for 70</span></span>
<ul>
<li><span data-ttu-id="49dc4-291">2. minőségi rendelés 7-hez (a fennmaradó rendelési mennyiség 10%-a, amely ebben az esetben 70).</span><span class="sxs-lookup"><span data-stu-id="49dc4-291">Quality order #2 for 7 (10% of the remaining order quantity, which equals 70 in this case)</span></span></li>
</ul>
</li>
</ol>
</td>
</tr>
<tr>
<td><span data-ttu-id="49dc4-292">Rögzített mennyiség: 1</span><span class="sxs-lookup"><span data-stu-id="49dc4-292">Fixed quantity: 1</span></span></td>
<td><span data-ttu-id="49dc4-293">Nem</span><span class="sxs-lookup"><span data-stu-id="49dc4-293">No</span></span></td>
<td>
<p><span data-ttu-id="49dc4-294">Kötegszám: Nincs</span><span class="sxs-lookup"><span data-stu-id="49dc4-294">Batch number: No</span></span></p>
<p><span data-ttu-id="49dc4-295">Sorozatszám: Nincs</span><span class="sxs-lookup"><span data-stu-id="49dc4-295">Serial number: No</span></span></p>
</td>
<td><span data-ttu-id="49dc4-296">Rendelt mennyiség: 100</span><span class="sxs-lookup"><span data-stu-id="49dc4-296">Order quantity: 100</span></span>
<ol>
<li><span data-ttu-id="49dc4-297">Készként jelentés 30-hoz</span><span class="sxs-lookup"><span data-stu-id="49dc4-297">Report as finished for 30</span></span>
<ul>
<li><span data-ttu-id="49dc4-298">Az 1. minőségi rendelés 1-hez lesz létrehozva (az első jelentett kész mennyiséghez, amelynek rögzített értéke 1)</span><span class="sxs-lookup"><span data-stu-id="49dc4-298">Quality order #1 for 1 (for the first reported-as-finished quantity, which has a fixed value of 1)</span></span></li>
<li><span data-ttu-id="49dc4-299">Az 2. minőségi rendelés 1-hez lesz létrehozva (a fennmaradó mennyiséghez, amelynek rögzített értéke 1)</span><span class="sxs-lookup"><span data-stu-id="49dc4-299">Quality order #2 for 1 (for the remaining quantity, which still has a fixed value of 1)</span></span></li>
</ul>
</li>
<li><span data-ttu-id="49dc4-300">Készként jelentés 10-hoz</span><span class="sxs-lookup"><span data-stu-id="49dc4-300">Report as finished for 10</span></span>
<ul>
<li><span data-ttu-id="49dc4-301">Nem jönnek létre minőségi rendelések.</span><span class="sxs-lookup"><span data-stu-id="49dc4-301">No quality orders are created.</span></span></li>
</ul>
</li>
<li><span data-ttu-id="49dc4-302">Készként jelentés 60-hoz</span><span class="sxs-lookup"><span data-stu-id="49dc4-302">Report as finished for 60</span></span>
<ul>
<li><span data-ttu-id="49dc4-303">Nem jönnek létre minőségi rendelések.</span><span class="sxs-lookup"><span data-stu-id="49dc4-303">No quality orders are created.</span></span></li>
</ul>
</li>
</ol>
</td>
</tr>
<tr>
<td><span data-ttu-id="49dc4-304">Rögzített mennyiség: 1</span><span class="sxs-lookup"><span data-stu-id="49dc4-304">Fixed quantity: 1</span></span></td>
<td><span data-ttu-id="49dc4-305">Igen</span><span class="sxs-lookup"><span data-stu-id="49dc4-305">Yes</span></span></td>
<td>
<p><span data-ttu-id="49dc4-306">Kötegszám: Igen</span><span class="sxs-lookup"><span data-stu-id="49dc4-306">Batch number: Yes</span></span></p>
<p><span data-ttu-id="49dc4-307">Sorozatszám: Igen</span><span class="sxs-lookup"><span data-stu-id="49dc4-307">Serial number: Yes</span></span></p>
</td>
<td>
<p><span data-ttu-id="49dc4-308">Rendelt mennyiség: 10</span><span class="sxs-lookup"><span data-stu-id="49dc4-308">Order quantity: 10</span></span></p>
<ol>
<li><span data-ttu-id="49dc4-309">Készként jelentve 3:1 #b1-hez, #s1-hez; 1 #b2-höz, #s2-höz; és 1 #b3-hoz, #s3-hoz</span><span class="sxs-lookup"><span data-stu-id="49dc4-309">Report as finished for 3: 1 for #b1, #s1; 1 for #b2, #s2; and 1 for #b3, #s3</span></span>
<ul>
<li><span data-ttu-id="49dc4-310">1. minőségi rendelés 1-hez, #b1 köteg, #s1 sorozat</span><span class="sxs-lookup"><span data-stu-id="49dc4-310">Quality order #1 for 1 of batch #b1, serial #s1</span></span></li>
<li><span data-ttu-id="49dc4-311">2. minőségi rendelés 1-hez, #b2 köteg, #s2 sorozat</span><span class="sxs-lookup"><span data-stu-id="49dc4-311">Quality order #2 for 1 of batch #b2, serial #s2</span></span></li>
<li><span data-ttu-id="49dc4-312">3. minőségi rendelés 1-hez, #b3 köteg, #s3 sorozat</span><span class="sxs-lookup"><span data-stu-id="49dc4-312">Quality order #3 for 1 of batch #b3, serial #s3</span></span></li>
</ul>
</li>
<li><span data-ttu-id="49dc4-313">Készként jelentve a 2:1 #b4-hez, #s4-hez; és 1 #b5-höz, #s5-höz</span><span class="sxs-lookup"><span data-stu-id="49dc4-313">Report as finished for 2: 1 for #b4, #s4; and 1 for #b5, #s5</span></span>
<ul>
<li><span data-ttu-id="49dc4-314">4. minőségi rendelés 1-hez, #b4 köteg, #s4 sorozat</span><span class="sxs-lookup"><span data-stu-id="49dc4-314">Quality order #4 for 1 of batch #b4, serial #s4</span></span></li>
<li><span data-ttu-id="49dc4-315">5. minőségi rendelés 1-hez, #b5 köteg, #s5 sorozat</span><span class="sxs-lookup"><span data-stu-id="49dc4-315">Quality order #5 for 1 of batch #b5, serial #s5</span></span></li>
</ul>
</li>
</ol>
<p><span data-ttu-id="49dc4-316"><strong>Megjegyzés:</strong> A köteg újra felhasználható.</span><span class="sxs-lookup"><span data-stu-id="49dc4-316"><strong>Note:</strong> The batch can be reused.</span></span></p>
</td>
</tr>
<tr>
<td><span data-ttu-id="49dc4-317">Rögzített mennyiség: 2</span><span class="sxs-lookup"><span data-stu-id="49dc4-317">Fixed quantity: 2</span></span></td>
<td><span data-ttu-id="49dc4-318">Nem</span><span class="sxs-lookup"><span data-stu-id="49dc4-318">No</span></span></td>
<td>
<p><span data-ttu-id="49dc4-319">Kötegszám: Igen</span><span class="sxs-lookup"><span data-stu-id="49dc4-319">Batch number: Yes</span></span></p>
<p><span data-ttu-id="49dc4-320">Sorozatszám: Igen</span><span class="sxs-lookup"><span data-stu-id="49dc4-320">Serial number: Yes</span></span></p>
</td>
<td>
<p><span data-ttu-id="49dc4-321">Rendelt mennyiség: 10</span><span class="sxs-lookup"><span data-stu-id="49dc4-321">Order quantity: 10</span></span></p>
<ol>
<li><span data-ttu-id="49dc4-322">Készként jelentve 4:1 #b1-hez, #s1-hez; 1 #b2-höz, #s2-höz; és 1 #b3-hoz, #s3-hoz és 1 #b4-hez, #s4-hez</span><span class="sxs-lookup"><span data-stu-id="49dc4-322">Report as finished for 4: 1 for #b1, #s1; 1 for #b2, #s2; 1 for #b3, #s3; and 1 for #b4, #s4</span></span>
<ul>
<li><span data-ttu-id="49dc4-323">1. minőségi rendelés 1-hez, #b1 köteg, #s1 sorozat</span><span class="sxs-lookup"><span data-stu-id="49dc4-323">Quality order #1 for 1 of batch #b1, serial #s1</span></span></li>
<li><span data-ttu-id="49dc4-324">2. minőségi rendelés 1-hez, #b2 köteg, #s2 sorozat</span><span class="sxs-lookup"><span data-stu-id="49dc4-324">Quality order #2 for 1 of batch #b2, serial #s2</span></span></li>
<li><span data-ttu-id="49dc4-325">3. minőségi rendelés 1-hez, #b3 köteg, #s3 sorozat</span><span class="sxs-lookup"><span data-stu-id="49dc4-325">Quality order #3 for 1 of batch #b3, serial #s3</span></span></li>
<li><span data-ttu-id="49dc4-326">4. minőségi rendelés 1-hez, #b4 köteg, #s4 sorozat</span><span class="sxs-lookup"><span data-stu-id="49dc4-326">Quality order #4 for 1 of batch #b4, serial #s4</span></span></li>
</ul>
<ul>
<li><span data-ttu-id="49dc4-327">Minőségi rendelés #5 2-höz, egy kötegre és egy sorozatszámra való hivatkozás nélkül</span><span class="sxs-lookup"><span data-stu-id="49dc4-327">Quality order #5 for 2, without a reference to a batch and a serial number</span></span></li>
</ul>
</li>
<li><span data-ttu-id="49dc4-328">Készként jelentve a 6: 1 #b5-höz, #s5-höz; 1 #b6-hoz, #s6-hoz; 1 #b7-hez, #s7-hez; 1 #b8-hoz, #s8-hoz; 1 #b9-hez, #s9-hez; és 1 #b10-hez, #s10-hez</span><span class="sxs-lookup"><span data-stu-id="49dc4-328">Report as finished for 6: 1 for #b5, #s5; 1 for #b6, #s6; 1 for #b7, #s7; 1 for #b8, #s8; 1 for #b9, #s9; and 1 for #b10, #s10</span></span>
<ul>
<li><span data-ttu-id="49dc4-329">Nem jönnek létre minőségi rendelések.</span><span class="sxs-lookup"><span data-stu-id="49dc4-329">No quality orders are created.</span></span></li>
</ul>
</li>
</ol>
</td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="49dc4-330">A *Minőségkezelés a raktári folyamatokhoz* funkció hozzáadja a minőségi rendelés feldolgozásához szükséges képességeket, ha az **Eseménytípus** beállítása *Készként jelentés*, és a **Végrehajtás** beállítása *Után*, és az **Eseménytípus** típusú beszerzések beállítása *Regisztráció*.</span><span class="sxs-lookup"><span data-stu-id="49dc4-330">The *Quality management for warehouse processes* feature adds capabilities for quality order processing for production with **Event type** set to *Report as finished* and **Execution** set to *After*, and for purchases with **Event type** set to *Registration*.</span></span> <span data-ttu-id="49dc4-331">Részletekért lásd: [Raktári folyamatok minőségkezelése](quality-management-for-warehouses-processes.md).</span><span class="sxs-lookup"><span data-stu-id="49dc4-331">For details, see [Quality management for warehouse processes](quality-management-for-warehouses-processes.md).</span></span>

## <a name="quality-management-pages"></a><span data-ttu-id="49dc4-332">A Minőségkezelés oldalai</span><span class="sxs-lookup"><span data-stu-id="49dc4-332">Quality management pages</span></span>
<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="49dc4-333">Oldal</span><span class="sxs-lookup"><span data-stu-id="49dc4-333">Page</span></span></th>
<th><span data-ttu-id="49dc4-334">Leírás</span><span class="sxs-lookup"><span data-stu-id="49dc4-334">Description</span></span></th>
<th><span data-ttu-id="49dc4-335">Példa</span><span class="sxs-lookup"><span data-stu-id="49dc4-335">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="49dc4-336">Minőségi társítások</span><span class="sxs-lookup"><span data-stu-id="49dc4-336">Quality associations</span></span></td>
<td><span data-ttu-id="49dc4-337">Lásd a cikk előző szakaszait.</span><span class="sxs-lookup"><span data-stu-id="49dc4-337">See the previous sections of this article.</span></span></td>
<td><span data-ttu-id="49dc4-338">A minőségi társítás meghatározza a létrehozott minőségi rendelésre vonatkozó alábbi adatok mindegyikét:</span><span class="sxs-lookup"><span data-stu-id="49dc4-338">A quality association defines all the following information for a quality order that is generated:</span></span>
<ul>
<li><span data-ttu-id="49dc4-339">Tranzakcióesemény</span><span class="sxs-lookup"><span data-stu-id="49dc4-339">The transaction event</span></span></li>
<li><span data-ttu-id="49dc4-340">A cikkeken elvégzendő tesztek</span><span class="sxs-lookup"><span data-stu-id="49dc4-340">The set of tests that must be performed on the items</span></span></li>
<li><span data-ttu-id="49dc4-341">Elfogadható minőségi szint</span><span class="sxs-lookup"><span data-stu-id="49dc4-341">The AQL</span></span></li>
<li><span data-ttu-id="49dc4-342">Mintavételi terv</span><span class="sxs-lookup"><span data-stu-id="49dc4-342">The sampling plan</span></span></li>
</ul>
<span data-ttu-id="49dc4-343">Definiálnia kell egy minőségi társítást az üzleti folyamat minden olyan változatához, ahol minőségi rendelés automatikus létrehozása szükséges.</span><span class="sxs-lookup"><span data-stu-id="49dc4-343">You must define a quality association for each variation in a business process that requires automatic generation of quality orders.</span></span> <span data-ttu-id="49dc4-344">Minőségi rendelés létrehozható például az üzleti folyamatokban beszerzési rendelésekhez, karanténutasításokhoz, értékesítési rendelésekhez és termelési rendelésekhez.</span><span class="sxs-lookup"><span data-stu-id="49dc4-344">For example, a quality order can be generated in the business processes for purchase orders, quarantine orders, sales orders, and production orders.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="49dc4-345">Tesztek</span><span class="sxs-lookup"><span data-stu-id="49dc4-345">Tests</span></span></td>
<td><span data-ttu-id="49dc4-346">Ezen az oldalon lehet meghatározni és megtekinteni azokat a teszteket, amelyekkel megállapítható, hogy a termékek megfelelnek-e a minőségi specifikációknak.</span><span class="sxs-lookup"><span data-stu-id="49dc4-346">Use this page to define and view the individual tests that determine whether your products meet quality specifications.</span></span> <span data-ttu-id="49dc4-347">Hozzárendelhet egy vagy több különálló tesztet egy tesztcsoporthoz.</span><span class="sxs-lookup"><span data-stu-id="49dc4-347">You can assign one or more individual tests to a test group.</span></span> <span data-ttu-id="49dc4-348">Ebben az esetben tesztspecifikus adatokat is megadhat, például az elfogadható mérési értékeket.</span><span class="sxs-lookup"><span data-stu-id="49dc4-348">In this case, you also specify test-specific information, such as the acceptable measurement values.</span></span> <span data-ttu-id="49dc4-349">Mennyiségi tesztekhez mérési értékek, minőségi tesztekhez pedig tesztváltozók használhatók.</span><span class="sxs-lookup"><span data-stu-id="49dc4-349">Measurement values are used for quantitative tests, and test variables are used for qualitative tests.</span></span>
<ul>
<li><span data-ttu-id="49dc4-350">Egy mennyiségi teszt teszttípusa <strong>Egész</strong> vagy <strong>Tört</strong> lehet, és egy kijelölt mértékegység is tartozik hozzá.</span><span class="sxs-lookup"><span data-stu-id="49dc4-350">A quantitative test has a test type of <strong>Integer</strong> or <strong>Fraction</strong>, and also has a designated unit of measure.</span></span> <span data-ttu-id="49dc4-351">A minőségi specifikációk és a teszteredmények számokként fejeződnek ki.</span><span class="sxs-lookup"><span data-stu-id="49dc4-351">Quality specifications and test results are expressed as numbers.</span></span></li>
<li><span data-ttu-id="49dc4-352">A minőségi tesztek teszttípusa: <strong>Lehetőség</strong>.</span><span class="sxs-lookup"><span data-stu-id="49dc4-352">A qualitative test has a test type of <strong>Option</strong>.</span></span> <span data-ttu-id="49dc4-353">A minőségi tesztekhez további, a mérendő tesztváltozóra és annak sorszámozott lehetőségeire vonatkozó adatok szükségesek.</span><span class="sxs-lookup"><span data-stu-id="49dc4-353">Qualitative tests require additional information about the test variable that is being measured and its enumerated options.</span></span> <span data-ttu-id="49dc4-354">A minőségi specifikációk és a teszteredmények egy eredménynek megfelelően fejeződnek ki.</span><span class="sxs-lookup"><span data-stu-id="49dc4-354">Quality specifications and test results are expressed according to an outcome.</span></span></li>
</ul></td>
<td><span data-ttu-id="49dc4-355">Egy gyártóvállalat a beszerzett anyagon két tesztet végez el: ezek egyike az anyagminőséggel kapcsolatos mennyiségi teszt, a másik pedig a csomagolási sérüléseket felmérő minőségi teszt.</span><span class="sxs-lookup"><span data-stu-id="49dc4-355">A manufacturing company performs two tests on purchased material: a quantitative test about material quality and a qualitative test about packaging damage.</span></span> <span data-ttu-id="49dc4-356">A vállalat további adatokat ad meg a kvalitatív tesztre vonatkozóan, hogy meghatározza a tesztváltozót (sérült csomagolás) és annak kimeneteleit.</span><span class="sxs-lookup"><span data-stu-id="49dc4-356">The company defines additional information about the qualitative test to identify the test variable (damaged packaging) and its outcomes.</span></span> <span data-ttu-id="49dc4-357">A vállalat a <strong>Tesztcsoportok</strong> oldalon hozzárendeli a két tesztet egy tesztcsoporthoz és megadja a tesztspecifikus adatokat.</span><span class="sxs-lookup"><span data-stu-id="49dc4-357">The company uses the <strong>Test groups</strong> page to assign the two tests to a test group and to specify the test-specific information.</span></span> <span data-ttu-id="49dc4-358">A tesztcsoportot hozzárendeli egy minőségi rendeléshez, hogy a két teszt eredményét jelenteni tudja.</span><span class="sxs-lookup"><span data-stu-id="49dc4-358">The test group is assigned to a quality order, so that the company can report test results for the two tests.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="49dc4-359">Tesztcsoportok</span><span class="sxs-lookup"><span data-stu-id="49dc4-359">Test groups</span></span></td>
<td><span data-ttu-id="49dc4-360">Ezen az oldalon lehet beállítani, módosítani és megtekinteni a tesztcsoportokat és a tesztcsoportokhoz rendelt különálló teszteket.</span><span class="sxs-lookup"><span data-stu-id="49dc4-360">Use this page to set up, edit, and view test groups and the individual tests that are assigned to a test group.</span></span> <span data-ttu-id="49dc4-361">A felső ablak jeleníti meg a tesztcsoportokat, míg az alsó ablakban láthatók a kiválasztott tesztcsoporthoz tartozó tesztek.</span><span class="sxs-lookup"><span data-stu-id="49dc4-361">The upper pane displays test groups, and the lower pane displays the tests that are assigned to a selected test group.</span></span> <span data-ttu-id="49dc4-362">Egy tesztcsoporthoz több szabályt is hozzá lehet rendelni, például mintavételi tervet, elfogadható minőségi szintet, valamint a romboló teszt követelményét.</span><span class="sxs-lookup"><span data-stu-id="49dc4-362">You assign several policies to a test group, such as a sampling plan, an AQL, and the requirement for destructive testing.</span></span> <span data-ttu-id="49dc4-363">Amikor hozzárendel egy különálló tesztet egy tesztcsoporthoz, további adatokat definiálhat, például sorrendet, dokumentumokat és érvényességi dátumokat.</span><span class="sxs-lookup"><span data-stu-id="49dc4-363">When you assign an individual test to a test group, you define additional information, such as the sequence, documents, and validity dates.</span></span> <span data-ttu-id="49dc4-364">Mennyiségi teszt esetén a megadott adatok az elfogadható mérési értékeket is tartalmazzák.</span><span class="sxs-lookup"><span data-stu-id="49dc4-364">For a quantitative test, the information that you define also includes the acceptable measurement values.</span></span> <span data-ttu-id="49dc4-365">Minőségi teszt esetén az adatok a tesztváltozót és az alapértelmezett eredményt tartalmazzák.</span><span class="sxs-lookup"><span data-stu-id="49dc4-365">For a qualitative test, the information includes the test variable and default outcome.</span></span> <span data-ttu-id="49dc4-366">A minőségi rendelésekhez rendelt tesztcsoport meghatározza azokat az alapértelmezett teszteket, amelyeket az adott cikken végre kell hajtani.</span><span class="sxs-lookup"><span data-stu-id="49dc4-366">The test group that is assigned to a quality order defines the default set of tests that must be performed on the specified item.</span></span> <span data-ttu-id="49dc4-367">Azonban hozzáadhat, törölhet, vagy módosíthat adott minőségi rendelésre vonatkozó teszteket.</span><span class="sxs-lookup"><span data-stu-id="49dc4-367">However, you can add, delete, or change tests on the quality order.</span></span> <span data-ttu-id="49dc4-368">A minőségi rendelés keretében végzett mindegyik tesztnél megtörténik a teszteredmények jelentése.</span><span class="sxs-lookup"><span data-stu-id="49dc4-368">Test results are reported for each test on a quality order.</span></span></td>
<td><span data-ttu-id="49dc4-369">Egy gyártóvállalat minőségi irányelveinek minden variációjához meghatároz egy-egy tesztcsoportot.</span><span class="sxs-lookup"><span data-stu-id="49dc4-369">A manufacturing company defines a test group for each variation of its quality guidelines.</span></span> <span data-ttu-id="49dc4-370">A különböző tesztcsoportok tükrözik a mintavételi tervek, az együttesen végrehajtandó tesztsorok, az elfogadható mérési értékek, az elfogadható minőségi szint és egyéb tényezők eltéréseit.</span><span class="sxs-lookup"><span data-stu-id="49dc4-370">The various test groups reflect differences in the sampling plans, the sets of tests that must be performed together, the AQL, and other factors.</span></span> <span data-ttu-id="49dc4-371">Mennyiségi teszt esetén az elfogadható mérési értékekben is van különbség.</span><span class="sxs-lookup"><span data-stu-id="49dc4-371">For quantitative tests, there are also differences in the acceptable measurement values.</span></span> <span data-ttu-id="49dc4-372">A minőségi irányelveinek érvényesítése érdekében a vállalat minden egyes, minőségi rendeléseket automatikusan generáló szabályhoz a <strong>Minőségi társítások</strong> oldalon hozzárendel egy tesztcsoportot, valamint a manuálisan létrehozott minőségi rendelésekhez is hozzárendel egy tesztcsoportot.</span><span class="sxs-lookup"><span data-stu-id="49dc4-372">To enforce its quality guidelines, the company assigns a test group to each rule for automatically generating quality orders on the <strong>Quality associations</strong> page, and also assigns a test group to quality orders that are manually created.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="49dc4-373">Cikkminőségi csoportok</span><span class="sxs-lookup"><span data-stu-id="49dc4-373">Item quality groups</span></span></td>
<td><span data-ttu-id="49dc4-374">Ezen az oldalon a minőségi csoporthoz rendelt cikkeket, illetve a cikkhez rendelt minőségi csoportokat lehet beállítani, módosítani és megtekinteni.</span><span class="sxs-lookup"><span data-stu-id="49dc4-374">Use this page to set up, edit, and view the items that are assigned to a quality group or the quality groups that are assigned to an item.</span></span> <span data-ttu-id="49dc4-375">A minőségi csoport a cikkekre vonatkozó közös tesztkövetelményeket képvisel.</span><span class="sxs-lookup"><span data-stu-id="49dc4-375">A quality group represents common testing requirements for items.</span></span> <span data-ttu-id="49dc4-376">Miután a <strong>Tesztcsoportok</strong> oldalon definiálta a tesztkövetelményeket, meghatározhatja a minőségi rendelések automatikus létrehozásának szabályait.</span><span class="sxs-lookup"><span data-stu-id="49dc4-376">After you define the test requirements on the <strong>Test groups</strong> page, you can define the rules for automatically generating quality orders.</span></span> <span data-ttu-id="49dc4-377">A folyamat egyszerűsítése érdekében az egyes cikkekhez tartozó szabályokat nem definiáljuk.</span><span class="sxs-lookup"><span data-stu-id="49dc4-377">To simplify the process, you don&#39;t define rules for individual items.</span></span> <span data-ttu-id="49dc4-378">Ehelyett egy minőségi csoportra vonatkozó szabályokat definiálhatunk a <strong>Minőségi társítások</strong> oldalon.</span><span class="sxs-lookup"><span data-stu-id="49dc4-378">Instead, you define rules for a quality group, by using the <strong>Quality associations</strong> page.</span></span> <span data-ttu-id="49dc4-379">Emellett egy kiválasztott minőségi csoporthoz tartozó <strong>Cikkminőségi csoportok</strong> oldal is használható arra, hogy megfelelő cikkeket az adott csoporthoz rendeljünk.</span><span class="sxs-lookup"><span data-stu-id="49dc4-379">You can also use the <strong>Item quality groups</strong> page for a selected quality group to assign relevant items to that group.</span></span> <span data-ttu-id="49dc4-380">Emellett egy kiválasztott cikkhez tartozó <strong>Cikkminőségi csoportok</strong> oldal is használható arra, hogy megfelelő minőségi csoportokat az adott cikkhez rendeljünk.</span><span class="sxs-lookup"><span data-stu-id="49dc4-380">You can also use the <strong>Item quality groups</strong> page for a selected item to assign relevant quality groups to that item.</span></span></td>
<td><span data-ttu-id="49dc4-381">Egy gyártóvállalat több nyersanyagot is vásárol, amelyeknél a beérkezéskor szükséges vizsgálatokra ugyanazok a tesztkövetelmények vonatkoznak.</span><span class="sxs-lookup"><span data-stu-id="49dc4-381">A manufacturing company purchases various raw materials that have the same testing requirements for incoming inspection.</span></span> <span data-ttu-id="49dc4-382">A vállalat definiál egy minőségi csoportot, majd hozzárendeli a nyersanyagokhoz társított cikkszámokat a csoporthoz.</span><span class="sxs-lookup"><span data-stu-id="49dc4-382">The company defines a quality group and then assigns the item numbers that are associated with the raw materials to that group.</span></span> <span data-ttu-id="49dc4-383">Később a vállalat egy új típusú nyersanyagot vásárol, amelyre az előzőekkel azonos tesztkövetelmények vonatkoznak.</span><span class="sxs-lookup"><span data-stu-id="49dc4-383">Later, the company purchases a new type of raw material that has the same testing requirements.</span></span> <span data-ttu-id="49dc4-384">Ahelyett, hogy az új anyagra új tesztkövetelményeket állítana be, a vállalat hozzáadja az új anyag cikkszámát a meglévő minőségi csoporthoz.</span><span class="sxs-lookup"><span data-stu-id="49dc4-384">Instead of setting up new testing requirements for the new material, the company adds the item number for the new material to the existing quality group.</span></span> <span data-ttu-id="49dc4-385">Ugyanez a gyártóvállalat olyan cikkeket is gyárt, amelyek gyártási tesztjeire ugyanazok a követelmények érvényesek, és olyan cikkeket is szállít, amelyek szállítás előtti tesztjeire ugyanolyan követelmények vonatkoznak.</span><span class="sxs-lookup"><span data-stu-id="49dc4-385">The same manufacturing company also produces items that have the same production testing requirements and ships items that have the same requirement for pre-shipment testing.</span></span> <span data-ttu-id="49dc4-386">A vállalat két további minőségi csoportot határoz meg, majd a megfelelő cikkszámokat hozzárendeli az egyes minőségi csoportokhoz.</span><span class="sxs-lookup"><span data-stu-id="49dc4-386">The company defines two additional quality groups and then assigns the relevant item numbers to each group.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="49dc4-387">Tesztváltozók</span><span class="sxs-lookup"><span data-stu-id="49dc4-387">Test variables</span></span></td>
<td><span data-ttu-id="49dc4-388">Ezen az oldalon meghatározhatja és megtekintheti a minőségi tesztekhez társított változókat.</span><span class="sxs-lookup"><span data-stu-id="49dc4-388">Use this page to define and view the variables that are associated with a qualitative test.</span></span> <span data-ttu-id="49dc4-389">Minden változóhoz definiálhat sorszámozott eredményeket, amelyek a szóba jöhető lehetőségeket jelölik.</span><span class="sxs-lookup"><span data-stu-id="49dc4-389">For each variable, you define enumerated outcomes that represent the possible options.</span></span> <span data-ttu-id="49dc4-390">Teszteket a <strong>Tesztek</strong> oldalon adhat meg.</span><span class="sxs-lookup"><span data-stu-id="49dc4-390">You define tests on the <strong>Tests</strong> page.</span></span> <span data-ttu-id="49dc4-391">Minőségi tesztek esetén a teszt típusát <strong>Lehetőség</strong>-re kell állítania.</span><span class="sxs-lookup"><span data-stu-id="49dc4-391">For qualitative tests, you must set the test type to <strong>Option</strong>.</span></span> <span data-ttu-id="49dc4-392">A <strong>Tesztcsoportok</strong> oldal használatával lehet tesztváltozót adott teszthez hozzárendelni.</span><span class="sxs-lookup"><span data-stu-id="49dc4-392">Use the <strong>Test groups</strong> page to assign a test variable to an individual test.</span></span></td>
<td><span data-ttu-id="49dc4-393">Egy süteménygyártó a készterméken vizsgálatot végez.</span><span class="sxs-lookup"><span data-stu-id="49dc4-393">A manufacturing company that produces cookies uses an inspection test for the finished product.</span></span> <span data-ttu-id="49dc4-394">A vizsgálat tesztnek többféle változója van.</span><span class="sxs-lookup"><span data-stu-id="49dc4-394">This inspection test has several variables.</span></span> <span data-ttu-id="49dc4-395">Az egyik változó az íz, ennek lehetséges eredményei: jó és rossz.</span><span class="sxs-lookup"><span data-stu-id="49dc4-395">One variable is taste, and the possible outcomes for this variable are good and bad.</span></span> <span data-ttu-id="49dc4-396">Egy másik változó a szín, ennek lehetséges eredményei: túl sötét, túl világos és megfelelő.</span><span class="sxs-lookup"><span data-stu-id="49dc4-396">A second variable is color, and the possible outcomes are too dark, too light, and correct.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="49dc4-397">Tesztváltozó eredményei</span><span class="sxs-lookup"><span data-stu-id="49dc4-397">Test variable outcomes</span></span></td>
<td><span data-ttu-id="49dc4-398">Ezen az oldalon lehet beállítani, módosítani vagy megtekinteni a minőségi teszthez kapcsolódó tesztváltozó lehetséges teszteredményeit.</span><span class="sxs-lookup"><span data-stu-id="49dc4-398">Use this page to set up, edit, and to view the possible test results for a test variable that is associated with a qualitative test.</span></span> <span data-ttu-id="49dc4-399">Mindegyik eredményhez egy <strong>megfelelt</strong> vagy egy <strong>nem felelt meg</strong> állapotot kell hozzárendelni.</span><span class="sxs-lookup"><span data-stu-id="49dc4-399">For each outcome, you assign a <strong>pass</strong> or <strong>fail</strong> status.</span></span> <span data-ttu-id="49dc4-400">Minden egyes, a <strong>Tesztek</strong> oldalon megadott minőségi teszthez definiálnia kell egy változót és annak eredményeit.</span><span class="sxs-lookup"><span data-stu-id="49dc4-400">You must define a variable and its outcomes for each qualitative test that is defined on the <strong>Tests</strong> page.</span></span> <span data-ttu-id="49dc4-401">(Minőségi tesztek esetén a <strong>Tesztek</strong> oldalon beállított teszttípus <strong>Lehetőség</strong>.) A <strong>Tesztcsoportok</strong> oldal használatával lehet tesztváltozót és az alapértelmezett eredményt adott minőségi teszthez hozzárendelni.</span><span class="sxs-lookup"><span data-stu-id="49dc4-401">(For qualitative tests, the test type is set to <strong>Option</strong> on the <strong>Tests</strong> page.) Use the <strong>Test groups</strong> page to assign a test variable and the default outcome to an individual qualitative test.</span></span></td>
<td><span data-ttu-id="49dc4-402">Egy süteménygyártó a készterméken vizsgálatot végez.</span><span class="sxs-lookup"><span data-stu-id="49dc4-402">A manufacturing company that produces cookies uses an inspection test for the finished product.</span></span> <span data-ttu-id="49dc4-403">Ennek a vizsgálati tesztnek többféle változója van.</span><span class="sxs-lookup"><span data-stu-id="49dc4-403">This inspection test has of several variables.</span></span> <span data-ttu-id="49dc4-404">Az egyik változó az íz, ennek lehetséges eredményei: jó és rossz.</span><span class="sxs-lookup"><span data-stu-id="49dc4-404">One variable is taste, and the possible outcomes for this variable are good and bad.</span></span> <span data-ttu-id="49dc4-405">Egy másik változó a szín, ennek lehetséges eredményei: túl sötét, túl világos és megfelelő.</span><span class="sxs-lookup"><span data-stu-id="49dc4-405">A second variable is color, and the possible outcomes are too dark, too light, and correct.</span></span> <span data-ttu-id="49dc4-406">Mindegyik eredményhez hozzá van rendelve egy <strong>megfelelt</strong> vagy <strong>nem felelt meg</strong> állapot.</span><span class="sxs-lookup"><span data-stu-id="49dc4-406">A status of <strong>pass</strong> or <strong>fail</strong> is assigned to each outcome.</span></span> <span data-ttu-id="49dc4-407">Az egyes változók vizsgálatakor az ellenőr a teszt eredményét az egyik eredmény kiválasztásával jelenti.</span><span class="sxs-lookup"><span data-stu-id="49dc4-407">During the inspection test for each variable, the inspector reports the test result by selecting one of the outcomes.</span></span></td>
</tr>
</tbody>
</table>



<a name="additional-resources"></a><span data-ttu-id="49dc4-408">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="49dc4-408">Additional resources</span></span>
--------

[<span data-ttu-id="49dc4-409">Minőségkezelési folyamatok</span><span class="sxs-lookup"><span data-stu-id="49dc4-409">Quality management processes</span></span>](quality-management-processes.md)

[<span data-ttu-id="49dc4-410">Szabálytalanság kezelése</span><span class="sxs-lookup"><span data-stu-id="49dc4-410">Nonconformance management</span></span>](enable-nonconformance-management.md)

[<span data-ttu-id="49dc4-411">Raktári folyamatok minőségkezelése</span><span class="sxs-lookup"><span data-stu-id="49dc4-411">Quality management for warehouse processes</span></span>](quality-management-for-warehouses-processes.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]