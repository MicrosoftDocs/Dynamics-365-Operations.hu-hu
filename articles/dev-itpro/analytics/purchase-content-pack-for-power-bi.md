---
title: "Beszerzési kiadások elemzése Power BI-tartalom"
description: "Ez a témakör a Beszerzési kiadások elemzése Power BI-tartalom modul tartalmát ismerteti. Leírja, hogy hogyan kell hozzáférni a tartalomban szereplő jelentésekhez, és információkat nyújt a tartalom összeállításához használt entitásokkal és adatmodellekkel kapcsolatban."
author: FrankDahl
manager: AnnBe
ms.date: 12/18/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 265434
ms.assetid: 3cd9dfce-2687-4303-bc78-349e7cb5ea75
ms.search.region: global
ms.author: fdahl
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: aac6439bb54b3b9cab066b06c01763e880efef8e
ms.openlocfilehash: 07b6f433a8355d7f9ed6dce8e26f78d38a86a713
ms.contentlocale: hu-hu
ms.lasthandoff: 12/18/2017

---

# <a name="purchase-spend-analysis-power-bi-content"></a><span data-ttu-id="01a06-104">Beszerzési kiadások elemzése Power BI-tartalom</span><span class="sxs-lookup"><span data-stu-id="01a06-104">Purchase spend analysis Power BI content</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="01a06-105">Ez a témakör a **Beszerzési kiadások elemzése** Power BI-tartalom modul tartalmát ismerteti.</span><span class="sxs-lookup"><span data-stu-id="01a06-105">This topic describes what is included in the **Purchase spend analysis** Microsoft Power BI content.</span></span> <span data-ttu-id="01a06-106">Leírja, hogy hogyan kell hozzáférni Power BI-jelentésekhez, és információkat nyújt a tartalom összeállításához használt entitásokkal és adatmodellekkel kapcsolatban.</span><span class="sxs-lookup"><span data-stu-id="01a06-106">It explains how to access the Power BI reports, and provides information about the data model and entities that are used to build the content.</span></span>

## <a name="overview"></a><span data-ttu-id="01a06-107">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="01a06-107">Overview</span></span>

<span data-ttu-id="01a06-108">A **Beszerzési kiadások elemzése** Power BI-tartalom a beszerzési vezetők és olyan vezetők segítségével készült, akik a beszerzési kiadások költségvetéésért felelősek.</span><span class="sxs-lookup"><span data-stu-id="01a06-108">The **Purchase spend analysis** Power BI content was designed to help purchasing managers and managers who are responsible for budgets keep an eye on purchase spending.</span></span> <span data-ttu-id="01a06-109">A vezetők az alábbi módokon elemezhetik a beszerzési költségeket:</span><span class="sxs-lookup"><span data-stu-id="01a06-109">Managers can analyze purchase spending in the following ways:</span></span>

-   <span data-ttu-id="01a06-110">Az év megadott napjáig tartó beszerzések (szállítói csoport és az egyes szállítók , beszerzési kategória és egyes termékek, valamint a szállító helye szerint)</span><span class="sxs-lookup"><span data-stu-id="01a06-110">Year-to-date purchase (by vendor group and individual vendors, procurement category and individual products, and vendor location)</span></span>
-   <span data-ttu-id="01a06-111">Egy éves időszak beszerzési változásai (szállítói csoport és a beszerzési kategória szerint)</span><span class="sxs-lookup"><span data-stu-id="01a06-111">Year-over-year purchase change (by vendor group and procurement category)</span></span>

<span data-ttu-id="01a06-112">A tartalom beszerzési tranzakciós adatokat használ, és egyrészt összesített adatokat nyújt a vállalati szintű beszerzési számokról, másrészt a kiadások szállító és termék szerinti lebontását kínálja.</span><span class="sxs-lookup"><span data-stu-id="01a06-112">The content uses purchase transactional data, and provides both an aggregate view of the company-wide purchase figures and a breakdown of purchase spending by vendor and product.</span></span> <span data-ttu-id="01a06-113">A jelentések kiemelik a beszerzési kiadások időbeli változásait.</span><span class="sxs-lookup"><span data-stu-id="01a06-113">Reports highlight changes in purchase spending over time.</span></span> <span data-ttu-id="01a06-114">Ezért a jelentések riasztásra használhatók a menedzserek számára a kiadások pozitív és negatív trendjeiről az egyes szállítókra és termékekre nézve.</span><span class="sxs-lookup"><span data-stu-id="01a06-114">Therefore, the reports can be used to alert managers about positive and negative spending trends for individual vendors and products.</span></span> <span data-ttu-id="01a06-115">Ezenkívül diagramok jelenítik meg a beszerzési kiadásokat a különböző beszerzési kategóriákra és szállítói csoportokra nézve.</span><span class="sxs-lookup"><span data-stu-id="01a06-115">Additionally, charts show purchase spending for different procurement categories and vendor groups.</span></span> <span data-ttu-id="01a06-116">Ezért a kategória- és regionális vezetők a diagramok segítségével a kiadások viselkedési változásait azonosíthatják.</span><span class="sxs-lookup"><span data-stu-id="01a06-116">Therefore, category and regional managers can use the charts to help identify changes in spending behavior.</span></span>

## <a name="accessing-the-power-bi-content"></a><span data-ttu-id="01a06-117">Power BI-tartalom elérése</span><span class="sxs-lookup"><span data-stu-id="01a06-117">Accessing the Power BI content</span></span>
<span data-ttu-id="01a06-118">A **Beszerzési és ráfordítási elemzés** Power BI tartalom a **Beszerzési és ráfordítási elemzés** oldalon látható (**Beszerzés és forrás** > **Lekérdezések és jelentések** > **Beszerzési teljesítményelemzés** > **Beszerzési és ráfordítási elemzés**).</span><span class="sxs-lookup"><span data-stu-id="01a06-118">The **Purchase spend analysis** Power BI content is shown on the **Purchase and spend analysis** page (**Procurement and sourcing** > **Inquiries and reports** > **Purchase performance analysis** > **Purchase and spend analysis**).</span></span> 

## <a name="metrics-that-are-included-in-the-power-bi-content"></a><span data-ttu-id="01a06-119">A Power BI-tartalomhoz tartozó metrikák</span><span class="sxs-lookup"><span data-stu-id="01a06-119">Metrics that are included in the Power BI content</span></span>
<span data-ttu-id="01a06-120">A **Beszerzési kiadások elemzése** Power BI-tartalom tartalmaz egy jelentést, amely metrikák készletéből áll.</span><span class="sxs-lookup"><span data-stu-id="01a06-120">The **Purchase spend analysis** Power BI content includes a report that consists of a set of metrics.</span></span> <span data-ttu-id="01a06-121">Ezek a metrikák mozaikok, táblázatok és diagramok formájában jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="01a06-121">These metrics are visualized as charts, tiles, and tables.</span></span> <span data-ttu-id="01a06-122">Az alábbi táblázat tartalmazza a megjelenítések áttekintését.</span><span class="sxs-lookup"><span data-stu-id="01a06-122">The following table provides an overview of the visualizations.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="01a06-123">Jelentéslap</span><span class="sxs-lookup"><span data-stu-id="01a06-123">Report page</span></span></th>
<th><span data-ttu-id="01a06-124">Diagramok</span><span class="sxs-lookup"><span data-stu-id="01a06-124">Charts</span></span></th>
<th><span data-ttu-id="01a06-125">Mozaik</span><span class="sxs-lookup"><span data-stu-id="01a06-125">Tiles</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="01a06-126">Szállító beszerzés</span><span class="sxs-lookup"><span data-stu-id="01a06-126">Purchase by vendor</span></span></td>
<td><ul>
<li><span data-ttu-id="01a06-127">10 legmagasabb szállító beszerzés szerint (halmozott sávdiagram)</span><span class="sxs-lookup"><span data-stu-id="01a06-127">Top 10 vendors by purchase (stacked bar chart)</span></span></li>
<li><span data-ttu-id="01a06-128">Teljes beszerzések szállítói csoport / ország / név szerint (kördiagram)</span><span class="sxs-lookup"><span data-stu-id="01a06-128">Total purchase by vendor group / country / name (pie chart)</span></span></li>
<li><span data-ttu-id="01a06-129">Beszerzések szállítói csoport / ország / név szerint (oszlopdiagram)</span><span class="sxs-lookup"><span data-stu-id="01a06-129">Purchase by vendor group / country / name (column chart)</span></span></li>
<li><span data-ttu-id="01a06-130">Átlagos beszerzések szállítói csoport / ország / név szerint (oszlopdiagram)</span><span class="sxs-lookup"><span data-stu-id="01a06-130">Average purchase by vendor group / country / name (column chart)</span></span></li>
</ul></td>
<td><ul>
<li><span data-ttu-id="01a06-131">Összes beszerzés</span><span class="sxs-lookup"><span data-stu-id="01a06-131">Total purchase</span></span></li>
<li><span data-ttu-id="01a06-132">Egy éves időszak beszerzési növekedése</span><span class="sxs-lookup"><span data-stu-id="01a06-132">YOY purchase growth</span></span></li>
<li><span data-ttu-id="01a06-133">Összes szállító száma</span><span class="sxs-lookup"><span data-stu-id="01a06-133">Total # vendors</span></span></li>
<li><span data-ttu-id="01a06-134">Aktív szállítók száma</span><span class="sxs-lookup"><span data-stu-id="01a06-134">Total # of active vendors</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="01a06-135">Beszerzés termékenként</span><span class="sxs-lookup"><span data-stu-id="01a06-135">Purchase by product</span></span></td>
<td><ul>
<li><span data-ttu-id="01a06-136">Beszerzés beszerzési kategória / termék neve szerint (oszlopdiagram)</span><span class="sxs-lookup"><span data-stu-id="01a06-136">Purchase by procurement category / product name (column chart)</span></span></li>
<li><span data-ttu-id="01a06-137">Összes beszerzés beszerzési kategória / termék neve szerint (kördiagram)</span><span class="sxs-lookup"><span data-stu-id="01a06-137">Total purchase by procurement category / product name (pie chart)</span></span></li>
<li><span data-ttu-id="01a06-138">10 legmagasabb termék beszerzés szerint (halmozott sávdiagram)</span><span class="sxs-lookup"><span data-stu-id="01a06-138">Top 10 products by purchase (stacked bar chart)</span></span></li>
</ul></td>
<td><ul>
<li><span data-ttu-id="01a06-139">Termékek összes száma</span><span class="sxs-lookup"><span data-stu-id="01a06-139">Total # of products</span></span></li>
<li><span data-ttu-id="01a06-140">Összes aktív termék, teljes termékszám százaléka</span><span class="sxs-lookup"><span data-stu-id="01a06-140">Total active products percentage of total # of products</span></span></li>
<li><span data-ttu-id="01a06-141">A beszerzések 80%-át lefedő termékek száma</span><span class="sxs-lookup"><span data-stu-id="01a06-141">Number of products accounting for 80% purchase</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="01a06-142">Beszerzés időszak szerint\*</span><span class="sxs-lookup"><span data-stu-id="01a06-142">Purchase by period\*</span></span></td>
<td><ul>
<li><span data-ttu-id="01a06-143">Beszerzés hónap / nap szerint (oszlopdiagram)</span><span class="sxs-lookup"><span data-stu-id="01a06-143">Purchase by month / day (column chart)</span></span></li>
<li><span data-ttu-id="01a06-144">Összesített beszerzés, egy éves időszak eltérése (vízesésdiagram)</span><span class="sxs-lookup"><span data-stu-id="01a06-144">Cumulative purchase YOY variance (waterfall chart)</span></span></li>
<li><span data-ttu-id="01a06-145">Teljes beszerzés, egy éves időszak növekedése (oszlopdiagram)</span><span class="sxs-lookup"><span data-stu-id="01a06-145">Total purchase YOY growth (column chart)</span></span></li>
<li><span data-ttu-id="01a06-146">Beszerzési kimutatás (mátrix)</span><span class="sxs-lookup"><span data-stu-id="01a06-146">Procurement statement (matrix)</span></span></li>
</ul></td>
<td><ul>
<li><span data-ttu-id="01a06-147">Egy éves időszak beszerzési növekedése</span><span class="sxs-lookup"><span data-stu-id="01a06-147">YOY purchase growth</span></span></li>
<li><span data-ttu-id="01a06-148">Egy éves időszak beszerzési növekedése %</span><span class="sxs-lookup"><span data-stu-id="01a06-148">YOY purchase growth %</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="01a06-149">Beszerzés a szállító helye szerint</span><span class="sxs-lookup"><span data-stu-id="01a06-149">Purchase by vendor location</span></span></td>
<td><ul>
<li><span data-ttu-id="01a06-150">Beszerzés település szerint</span><span class="sxs-lookup"><span data-stu-id="01a06-150">Purchase by city</span></span></li>
<li><span data-ttu-id="01a06-151">Egy éves időszak beszerzési növekedési százaléka</span><span class="sxs-lookup"><span data-stu-id="01a06-151">Purchase YOY growth %</span></span></li>
<li><span data-ttu-id="01a06-152">Beszerzési ország szerint</span><span class="sxs-lookup"><span data-stu-id="01a06-152">Purchase by country</span></span></li>
</ul></td>
<td></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="01a06-153">Beszerzési kiadások elemzése idő szerint</span><span class="sxs-lookup"><span data-stu-id="01a06-153">Purchase spend analysis by time</span></span></td>
<td><ul>
<li><span data-ttu-id="01a06-154">Beszerzési folyó év, hónap / nap szerint (vonaldiagram)</span><span class="sxs-lookup"><span data-stu-id="01a06-154">Purchase current year by month / day (line chart)</span></span></li>
<li><span data-ttu-id="01a06-155">Beszerzés, jelenlegi és az előző év (vonal- és oszlopdiagram)</span><span class="sxs-lookup"><span data-stu-id="01a06-155">Purchase current and last year (line and column chart)</span></span></li>
</ul></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="01a06-156">Beszerzési kiadások elemzése szállító szerint</span><span class="sxs-lookup"><span data-stu-id="01a06-156">Purchase spend analysis by vendor</span></span></td>
<td><ul>
<li><span data-ttu-id="01a06-157">A legjobb szállítói beszerzési %-a a beszerzésekből (tölcsér)</span><span class="sxs-lookup"><span data-stu-id="01a06-157">Top 10 vendor purchase % of purchase (funnel)</span></span></li>
<li><span data-ttu-id="01a06-158">Top 10 szállító megnövekedett kiadásokkal egy éves időszakban</span><span class="sxs-lookup"><span data-stu-id="01a06-158">Top 10 vendors with increased spending YOY</span></span></li>
<li><span data-ttu-id="01a06-159">Top 10 szállító csökkent kiadásokkal egy éves időszakban</span><span class="sxs-lookup"><span data-stu-id="01a06-159">Top 10 vendors with decreased spending YOY</span></span></li>
</ul></td>
<td></td>
</tr>
</tbody>
</table>

<span data-ttu-id="01a06-160">\\* Erre az évre és az előző évre eső beszerzés, és növekedés beszerzési kategória szerint</span><span class="sxs-lookup"><span data-stu-id="01a06-160">\\* Purchase this year and last year, and growth by procurement category</span></span>

## <a name="data-model-and-entities"></a><span data-ttu-id="01a06-161">Adatmodell és entitások</span><span class="sxs-lookup"><span data-stu-id="01a06-161">Data model and entities</span></span>
<span data-ttu-id="01a06-162">A **Beszerzési kiadások elemzése** Power BI-tartalom jelentési oldalainak feltöltésére a következő adatok szolgálnak.</span><span class="sxs-lookup"><span data-stu-id="01a06-162">The following data is used to fill the report pages in the **Purchase spend analysis** Power BI content.</span></span> <span data-ttu-id="01a06-163">Ezeket az adatokat az Entitástárban lebonyolított összesített mérések jelenítik meg.</span><span class="sxs-lookup"><span data-stu-id="01a06-163">This data is represented as aggregate measurements that are staged in the Entity store.</span></span> <span data-ttu-id="01a06-164">Az entitástár a Microsoft analitikai célokra optimalizált SQL-szerveradatbázisa.</span><span class="sxs-lookup"><span data-stu-id="01a06-164">The Entity store is a Microsoft SQL Server database that is optimized for analytics.</span></span> <span data-ttu-id="01a06-165">További tudnivalókért lásd: [Az entitástár és a Power BI integrációjának áttekintése](power-bi-integration-entity-store.md).</span><span class="sxs-lookup"><span data-stu-id="01a06-165">For more information, see [Overview of Power BI integration with Entity store](power-bi-integration-entity-store.md).</span></span>

<span data-ttu-id="01a06-166">A tartalom összesítő mértékek a következőkben rendelkezésre álló összesítő mértékek részhalmazát alkotják: Purchase Cube in Microsoft Dynamics AX 2012 és Microsoft Dynamics AX 2012 R3.</span><span class="sxs-lookup"><span data-stu-id="01a06-166">The aggregate measurements in this content are the subset of aggregate measurements that were available in the Purchase Cube in Microsoft Dynamics AX 2012 and Microsoft Dynamics AX 2012 R3.</span></span> <span data-ttu-id="01a06-167">A kocka összesítő mértékeinek előkészítéséhez az entitástárban, a mértékeket központilag telepíthetővé kell tenni.</span><span class="sxs-lookup"><span data-stu-id="01a06-167">To stage the cube’s aggregate measurements in the Entity store, you must make them deployable.</span></span> <span data-ttu-id="01a06-168">További információért lásd a következő blogbejegyzést az összesítő mértékek előkészítésének eljárásáról az entitástárban: [A Power BI és az entitástár integrálása a Dynamics programban - áttekintés](power-bi-integration-entity-store.md).</span><span class="sxs-lookup"><span data-stu-id="01a06-168">For more information, see the procedure for staging aggregate measurements in the Entity store in [Overview of Power BI integration with Entity store](power-bi-integration-entity-store.md).</span></span> <span data-ttu-id="01a06-169">A következő kulcs összesítő mértékek közvetlenül a számla sorai entitásból érhetők el, és a tartalom alapjául szolgálnak.</span><span class="sxs-lookup"><span data-stu-id="01a06-169">The following key aggregate measurements are available directly from the Invoice lines entity and are used as the basis of the content.</span></span>

| <span data-ttu-id="01a06-170">Entitás</span><span class="sxs-lookup"><span data-stu-id="01a06-170">Entity</span></span>        | <span data-ttu-id="01a06-171">Kulcs összesítő mértékek</span><span class="sxs-lookup"><span data-stu-id="01a06-171">Key aggregate measurements</span></span> | <span data-ttu-id="01a06-172">Adatforrás</span><span class="sxs-lookup"><span data-stu-id="01a06-172">Data source</span></span>                                 | <span data-ttu-id="01a06-173">Mező</span><span class="sxs-lookup"><span data-stu-id="01a06-173">Field</span></span>              | <span data-ttu-id="01a06-174">Leírás</span><span class="sxs-lookup"><span data-stu-id="01a06-174">Description</span></span>                            |
|---------------|----------------------------|---------------------------------------------|--------------------|----------------------------------------|
| <span data-ttu-id="01a06-175">Számlasorok</span><span class="sxs-lookup"><span data-stu-id="01a06-175">Invoice lines</span></span> | <span data-ttu-id="01a06-176">Beszerzés</span><span class="sxs-lookup"><span data-stu-id="01a06-176">Purchase</span></span>                   | <span data-ttu-id="01a06-177">VendInvoiceTrans</span><span class="sxs-lookup"><span data-stu-id="01a06-177">VendInvoiceTrans</span></span>                            | <span data-ttu-id="01a06-178">SUM(LineAmountMST)</span><span class="sxs-lookup"><span data-stu-id="01a06-178">SUM(LineAmountMST)</span></span> | <span data-ttu-id="01a06-179">Összeg a könyvelési pénznemben.</span><span class="sxs-lookup"><span data-stu-id="01a06-179">The amount in the accounting currency.</span></span> |

<span data-ttu-id="01a06-180">Az alábbi táblázat a kulcs mértékeket mutatja, amelyeknek a kiszámítása a tartalomban történik a számla sorai entitásból.</span><span class="sxs-lookup"><span data-stu-id="01a06-180">The following table shows the key measurements in the content that are calculated from the Invoice lines entity.</span></span>

| <span data-ttu-id="01a06-181">Méret</span><span class="sxs-lookup"><span data-stu-id="01a06-181">Measure</span></span>               | <span data-ttu-id="01a06-182">Számítás</span><span class="sxs-lookup"><span data-stu-id="01a06-182">Calculation</span></span>                                                                                         |
|-----------------------|-----------------------------------------------------------------------------------------------------|
| <span data-ttu-id="01a06-183">Aktuális év beszerzései</span><span class="sxs-lookup"><span data-stu-id="01a06-183">Purchase current year</span></span> | <span data-ttu-id="01a06-184">Aktuális év beszerzései = SUM('Számlasorok'\[Beszerzés\])</span><span class="sxs-lookup"><span data-stu-id="01a06-184">Purchase current year = SUM('Invoice lines'\[Purchase\])</span></span>                                            |
| <span data-ttu-id="01a06-185">Tavalyi év beszerzései</span><span class="sxs-lookup"><span data-stu-id="01a06-185">Purchase last year</span></span>    | <span data-ttu-id="01a06-186">Tavalyi év beszerzései = CALCULATE(SUM('Számlasorok'\[Beszerzés\]), SAMEPERIODLASTYEAR(Dátumok\[Dátum\]))</span><span class="sxs-lookup"><span data-stu-id="01a06-186">Purchase last year = CALCULATE(SUM('Invoice lines'\[Purchase\]), SAMEPERIODLASTYEAR(Dates\[Date\]))</span></span> |
| <span data-ttu-id="01a06-187">Egy éves időszak beszerzési növekedése</span><span class="sxs-lookup"><span data-stu-id="01a06-187">YOY purchase growth</span></span>   | <span data-ttu-id="01a06-188">Egy éves időszak beszerzési növekedése = \[Aktuális év beszerzései\] – \[Tavalyi év beszerzései\]</span><span class="sxs-lookup"><span data-stu-id="01a06-188">YOY purchase growth = \[Purchase current year\] – \[Purchase last year\]</span></span>                            |

<span data-ttu-id="01a06-189">A tartalomban a következő fő dimenziók szolgálnak szűrőként az összesítő mértékek szeletelésére, nagyobb részletességet és mélyebb elemzési betekintések elérését téve lehetővé.</span><span class="sxs-lookup"><span data-stu-id="01a06-189">The following key dimensions in the content are used as filters to slice the aggregate measurements, so that you can achieve more granularity and gain deeper analytical insights.</span></span>

| <span data-ttu-id="01a06-190">Entitás</span><span class="sxs-lookup"><span data-stu-id="01a06-190">Entity</span></span>                 | <span data-ttu-id="01a06-191">Példák az attribútumok</span><span class="sxs-lookup"><span data-stu-id="01a06-191">Examples of attributes</span></span>                                |
|------------------------|-------------------------------------------------------|
| <span data-ttu-id="01a06-192">Szállítók</span><span class="sxs-lookup"><span data-stu-id="01a06-192">Vendors</span></span>                | <span data-ttu-id="01a06-193">Szállítói csoportok, Szállító országok vagy régiók, Szállító neve</span><span class="sxs-lookup"><span data-stu-id="01a06-193">Vendor groups, Vendor country or regions, Vendor name</span></span> |
| <span data-ttu-id="01a06-194">Termékek</span><span class="sxs-lookup"><span data-stu-id="01a06-194">Products</span></span>               | <span data-ttu-id="01a06-195">Termékszám, Termék neve, Cikkcsoportok neve</span><span class="sxs-lookup"><span data-stu-id="01a06-195">Product number, Product name, Item groups name</span></span>        |
| <span data-ttu-id="01a06-196">Beszerzési kategóriák</span><span class="sxs-lookup"><span data-stu-id="01a06-196">Procurement categories</span></span> | <span data-ttu-id="01a06-197">Beszerzési kategória, Beszerzési kategórianevek</span><span class="sxs-lookup"><span data-stu-id="01a06-197">Procurement category, Procurement category names</span></span>      |
| <span data-ttu-id="01a06-198">Jogi személyek</span><span class="sxs-lookup"><span data-stu-id="01a06-198">Legal entities</span></span>         | <span data-ttu-id="01a06-199">Jogi személy neve</span><span class="sxs-lookup"><span data-stu-id="01a06-199">Legal entity name</span></span>                                     |
| <span data-ttu-id="01a06-200">Dátumok</span><span class="sxs-lookup"><span data-stu-id="01a06-200">Dates</span></span>                  | <span data-ttu-id="01a06-201">Dátumok, Év eltolása</span><span class="sxs-lookup"><span data-stu-id="01a06-201">Dates, Year offset</span></span>                                    |

<span data-ttu-id="01a06-202">Alapértelmezés szerint a tartalom a folyó naptári év adatait jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="01a06-202">By default, the content shows data for the current calendar year.</span></span> <span data-ttu-id="01a06-203">Azonban módosíthatja a dátumszűrőt a jelentésszűrők szakaszban.</span><span class="sxs-lookup"><span data-stu-id="01a06-203">However, you can change the date filter in the report filters section.</span></span> <span data-ttu-id="01a06-204">A vállalatszűrőt is módosíthatja.</span><span class="sxs-lookup"><span data-stu-id="01a06-204">You can also change the company filter.</span></span>

