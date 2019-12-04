---
title: Beszerzési és ráfordítási elemzés Power BI tartalom
description: Ez a témakör a Beszerzési kiadások elemzése Power BI tartalom modul tartalmát ismerteti. Leírja, hogy hogyan kell hozzáférni a tartalomban szereplő jelentésekhez, és információkat nyújt a tartalom összeállításához használt entitásokkal és adatmodellekkel kapcsolatban.
author: FrankDahl
manager: AnnBe
ms.date: 04/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: PurchaseSpendAnalysisPowerBI
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 265434
ms.assetid: 3cd9dfce-2687-4303-bc78-349e7cb5ea75
ms.search.region: global
ms.author: fdahl
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 2d31aaf14f6399baca8531707864c48cd2d56ac2
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/06/2019
ms.locfileid: "2769971"
---
# <a name="purchase-spend-analysis-power-bi-content"></a><span data-ttu-id="e6672-104">Beszerzési és ráfordítási elemzés Power BI tartalom</span><span class="sxs-lookup"><span data-stu-id="e6672-104">Purchase spend analysis Power BI content</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e6672-105">Ez a témakör a **Beszerzési kiadások elemzése** Microsoft Power BI tartalom modul tartalmát ismerteti.</span><span class="sxs-lookup"><span data-stu-id="e6672-105">This topic describes what is included in the **Purchase spend analysis** Microsoft Power BI content.</span></span> <span data-ttu-id="e6672-106">Leírja, hogy hogyan kell hozzáférni a Power BI-jelentésekhez, és információkat nyújt a tartalomcsomag összeállításához korábban használt entitásokkal és adatmodellekkel kapcsolatban.</span><span class="sxs-lookup"><span data-stu-id="e6672-106">It explains how to access the Power BI reports, and provides information about the data model and entities that are used to build the content.</span></span>

## <a name="overview"></a><span data-ttu-id="e6672-107">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="e6672-107">Overview</span></span>

<span data-ttu-id="e6672-108">A **Beszerzési kiadások elemzése** Power BI-tartalom a beszerzési vezetők és olyan vezetők segítségével készült, akik a beszerzési kiadások költségvetéésének nyomon követésért felelősek.</span><span class="sxs-lookup"><span data-stu-id="e6672-108">The **Purchase spend analysis** Power BI content was designed to help purchasing managers and managers who are responsible for budgets keep track of purchase spending.</span></span> <span data-ttu-id="e6672-109">A vezetők az alábbi módokon elemezhetik a beszerzési költségeket:</span><span class="sxs-lookup"><span data-stu-id="e6672-109">Managers can analyze purchase spending in the following ways:</span></span>

- <span data-ttu-id="e6672-110">Az év megadott napjáig tartó beszerzések (szállítói csoport és az egyes szállítók , beszerzési kategória és egyes termékek, valamint a szállító helye szerint)</span><span class="sxs-lookup"><span data-stu-id="e6672-110">Year-to-date purchase (by vendor group and individual vendors, procurement category and individual products, and vendor location)</span></span>
- <span data-ttu-id="e6672-111">Egy éves időszak beszerzési változásai (szállítói csoport és a beszerzési kategória szerint)</span><span class="sxs-lookup"><span data-stu-id="e6672-111">Year-over-year purchase change (by vendor group and procurement category)</span></span>

<span data-ttu-id="e6672-112">A tartalom beszerzési tranzakciós adatokat használ, és egyrészt összesített adatokat nyújt a vállalati szintű beszerzési számokról, másrészt a kiadások szállító és termék szerinti lebontását kínálja.</span><span class="sxs-lookup"><span data-stu-id="e6672-112">The content uses purchase transactional data, and provides both an aggregate view of the company-wide purchase figures and a breakdown of purchase spending by vendor and product.</span></span> <span data-ttu-id="e6672-113">A jelentések kiemelik a beszerzési kiadások időbeli változásait.</span><span class="sxs-lookup"><span data-stu-id="e6672-113">Reports highlight changes in purchase spending over time.</span></span> <span data-ttu-id="e6672-114">Ezért a jelentések riasztásra használhatók a menedzserek számára a kiadások pozitív és negatív trendjeiről az egyes szállítókra és termékekre nézve.</span><span class="sxs-lookup"><span data-stu-id="e6672-114">Therefore, the reports can be used to alert managers about positive and negative spending trends for individual vendors and products.</span></span> <span data-ttu-id="e6672-115">Ezenkívül diagramok jelenítik meg a beszerzési kiadásokat a különböző beszerzési kategóriákra és szállítói csoportokra nézve.</span><span class="sxs-lookup"><span data-stu-id="e6672-115">Additionally, charts show purchase spending for different procurement categories and vendor groups.</span></span> <span data-ttu-id="e6672-116">Ezért a kategória- és regionális vezetők a diagramok segítségével a kiadások viselkedési változásait azonosíthatják.</span><span class="sxs-lookup"><span data-stu-id="e6672-116">Therefore, category and regional managers can use the charts to help identify changes in spending behavior.</span></span>

## <a name="accessing-the-power-bi-content"></a><span data-ttu-id="e6672-117">A Power BI tartalom elérése</span><span class="sxs-lookup"><span data-stu-id="e6672-117">Accessing the Power BI content</span></span>
<span data-ttu-id="e6672-118">A **Beszerzési és ráfordítási elemzés** Power BI tartalom a **Beszerzési és ráfordítási elemzés** oldalon látható (**Beszerzés és forrás** \> **Lekérdezések és jelentések** \> **Beszerzési teljesítményelemzés** \> **Beszerzési és ráfordítási elemzés**).</span><span class="sxs-lookup"><span data-stu-id="e6672-118">The **Purchase spend analysis** Power BI content is shown on the **Purchase and spend analysis** page (**Procurement and sourcing** \> **Inquiries and reports** \> **Purchase performance analysis** \> **Purchase and spend analysis**).</span></span>

## <a name="metrics-that-are-included-in-the-power-bi-content"></a><span data-ttu-id="e6672-119">Mérőszámok, amelyek a Power BI tartalomban szerepelnek</span><span class="sxs-lookup"><span data-stu-id="e6672-119">Metrics that are included in the Power BI content</span></span>
<span data-ttu-id="e6672-120">A **Beszerzési kiadások elemzése** Power BI tartalomcsomag tartalmaz egy jelentést, amely metrikák készletéből áll.</span><span class="sxs-lookup"><span data-stu-id="e6672-120">The **Purchase spend analysis** Power BI content includes a report that consists of a set of metrics.</span></span> <span data-ttu-id="e6672-121">Ezek a metrikák mozaikok, táblázatok és diagramok formájában jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="e6672-121">These metrics are visualized as charts, tiles, and tables.</span></span> 

<span data-ttu-id="e6672-122">Az alábbi szakaszok tartalmazzák a megjelenítések áttekintését.</span><span class="sxs-lookup"><span data-stu-id="e6672-122">The following sections provide an overview of the visualizations.</span></span>

### <a name="purchase-by-vendor-report-page"></a><span data-ttu-id="e6672-123">Beszerzés a szállítói jelentés lapján</span><span class="sxs-lookup"><span data-stu-id="e6672-123">Purchase by vendor report page</span></span>
<span data-ttu-id="e6672-124">**Diagramok**</span><span class="sxs-lookup"><span data-stu-id="e6672-124">**Charts**</span></span>
- <span data-ttu-id="e6672-125">10 legmagasabb szállító beszerzés szerint (halmozott sávdiagram)</span><span class="sxs-lookup"><span data-stu-id="e6672-125">Top 10 vendors by purchase (stacked bar chart)</span></span>
- <span data-ttu-id="e6672-126">Teljes beszerzések szállítói csoport / ország / név szerint (kördiagram)</span><span class="sxs-lookup"><span data-stu-id="e6672-126">Total purchase by vendor group / country / name (pie chart)</span></span>
- <span data-ttu-id="e6672-127">Beszerzések szállítói csoport / ország / név szerint (oszlopdiagram)</span><span class="sxs-lookup"><span data-stu-id="e6672-127">Purchase by vendor group / country / name (column chart)</span></span>
- <span data-ttu-id="e6672-128">Átlagos beszerzések szállítói csoport / ország / név szerint (oszlopdiagram)</span><span class="sxs-lookup"><span data-stu-id="e6672-128">Average purchase by vendor group / country / name (column chart)</span></span>

<span data-ttu-id="e6672-129">**Mozaik**</span><span class="sxs-lookup"><span data-stu-id="e6672-129">**Tiles**</span></span>
- <span data-ttu-id="e6672-130">Összes beszerzés</span><span class="sxs-lookup"><span data-stu-id="e6672-130">Total purchase</span></span>
- <span data-ttu-id="e6672-131">Egy éves időszak beszerzési növekedése</span><span class="sxs-lookup"><span data-stu-id="e6672-131">YOY purchase growth</span></span>
- <span data-ttu-id="e6672-132">Összes szállító száma</span><span class="sxs-lookup"><span data-stu-id="e6672-132">Total # vendors</span></span>
- <span data-ttu-id="e6672-133">Aktív szállítók száma</span><span class="sxs-lookup"><span data-stu-id="e6672-133">Total # of active vendors</span></span>

<span data-ttu-id="e6672-134">**Példa**</span><span class="sxs-lookup"><span data-stu-id="e6672-134">**Example**</span></span>
<img src="media/spend1.png" alt="Purchase by vendor">

### <a name="purchase-by-product-report-page"></a><span data-ttu-id="e6672-135">Beszerzés a termékjelentés lapján</span><span class="sxs-lookup"><span data-stu-id="e6672-135">Purchase by product report page</span></span>

<span data-ttu-id="e6672-136">**Diagramok**</span><span class="sxs-lookup"><span data-stu-id="e6672-136">**Charts**</span></span>
- <span data-ttu-id="e6672-137">Beszerzés beszerzési kategória / termék neve szerint (oszlopdiagram)</span><span class="sxs-lookup"><span data-stu-id="e6672-137">Purchase by procurement category / product name (column chart)</span></span>
- <span data-ttu-id="e6672-138">Összes beszerzés beszerzési kategória / termék neve szerint (kördiagram)</span><span class="sxs-lookup"><span data-stu-id="e6672-138">Total purchase by procurement category / product name (pie chart)</span></span>
- <span data-ttu-id="e6672-139">10 legmagasabb termék beszerzés szerint (halmozott sávdiagram)</span><span class="sxs-lookup"><span data-stu-id="e6672-139">Top 10 products by purchase (stacked bar chart)</span></span>

<span data-ttu-id="e6672-140">**Mozaik**</span><span class="sxs-lookup"><span data-stu-id="e6672-140">**Tiles**</span></span>
- <span data-ttu-id="e6672-141">Termékek összes száma</span><span class="sxs-lookup"><span data-stu-id="e6672-141">Total # of products</span></span></li>
- <span data-ttu-id="e6672-142">Összes aktív termék, teljes termékszám százaléka</span><span class="sxs-lookup"><span data-stu-id="e6672-142">Total active products percentage of total # of products</span></span>
- <span data-ttu-id="e6672-143">A beszerzések 80%-át lefedő termékek száma</span><span class="sxs-lookup"><span data-stu-id="e6672-143">Number of products accounting for 80% purchase</span></span>

<span data-ttu-id="e6672-144">**Példa**</span><span class="sxs-lookup"><span data-stu-id="e6672-144">**Example**</span></span>


<img src="media/purchaseByProduct.png" alt="Purchase by Product">

### <a name="purchase-by-period-report-page"></a><span data-ttu-id="e6672-145">Beszerzés a az időszakjelentés lapján</span><span class="sxs-lookup"><span data-stu-id="e6672-145">Purchase by period report page</span></span>
<span data-ttu-id="e6672-146">Ez az oldal az erre az évre és az előző évre eső beszerzéseket, és növekedés beszerzési kategória szerint adatokat mutatja.</span><span class="sxs-lookup"><span data-stu-id="e6672-146">This page shows purchases this year and last year, and growth by procurement category.</span></span>

<span data-ttu-id="e6672-147">**Diagramok**</span><span class="sxs-lookup"><span data-stu-id="e6672-147">**Charts**</span></span> 
- <span data-ttu-id="e6672-148">Beszerzés hónap / nap szerint (oszlopdiagram)</span><span class="sxs-lookup"><span data-stu-id="e6672-148">Purchase by month / day (column chart)</span></span>
- <span data-ttu-id="e6672-149">Összesített beszerzés, egy éves időszak eltérése (vízesésdiagram)</span><span class="sxs-lookup"><span data-stu-id="e6672-149">Cumulative purchase YOY variance (waterfall chart)</span></span>
- <span data-ttu-id="e6672-150">Teljes beszerzés, egy éves időszak növekedése (oszlopdiagram)</span><span class="sxs-lookup"><span data-stu-id="e6672-150">Total purchase YOY growth (column chart)</span></span>
- <span data-ttu-id="e6672-151">Beszerzési kimutatás (mátrix)</span><span class="sxs-lookup"><span data-stu-id="e6672-151">Procurement statement (matrix)</span></span>

<span data-ttu-id="e6672-152">**Mozaik**</span><span class="sxs-lookup"><span data-stu-id="e6672-152">**Tiles**</span></span>
- <span data-ttu-id="e6672-153">Egy éves időszak beszerzési növekedése</span><span class="sxs-lookup"><span data-stu-id="e6672-153">YOY purchase growth</span></span>
- <span data-ttu-id="e6672-154">Egy éves időszak beszerzési növekedése %</span><span class="sxs-lookup"><span data-stu-id="e6672-154">YOY purchase growth %</span></span>

<span data-ttu-id="e6672-155">**Példa**</span><span class="sxs-lookup"><span data-stu-id="e6672-155">**Example**</span></span>
<img src="media/purchaseByPeriod.png" alt="Purchase by Period">

### <a name="purchase-by-vendor-location-report-page"></a><span data-ttu-id="e6672-156">Beszerzés a szállítói helyjelentés lapján</span><span class="sxs-lookup"><span data-stu-id="e6672-156">Purchase by vendor location report page</span></span>

<span data-ttu-id="e6672-157">**Diagramok**</span><span class="sxs-lookup"><span data-stu-id="e6672-157">**Charts**</span></span>
- <span data-ttu-id="e6672-158">Beszerzés település szerint</span><span class="sxs-lookup"><span data-stu-id="e6672-158">Purchase by city</span></span>
- <span data-ttu-id="e6672-159">Egy éves időszak beszerzési növekedési százaléka</span><span class="sxs-lookup"><span data-stu-id="e6672-159">Purchase YOY growth %</span></span>
- <span data-ttu-id="e6672-160">Beszerzési ország szerint</span><span class="sxs-lookup"><span data-stu-id="e6672-160">Purchase by country</span></span>

<span data-ttu-id="e6672-161">**Példa**</span><span class="sxs-lookup"><span data-stu-id="e6672-161">**Example**</span></span>
<img src="media/purchByVendorLocation.png" alt="Purchase by Vendor Location">

### <a name="purchase-spend-analysis-by-time-report-page"></a><span data-ttu-id="e6672-162">Beszerzési kiadások elemzése idő szerint lapján</span><span class="sxs-lookup"><span data-stu-id="e6672-162">Purchase spend analysis by time report page</span></span>

<span data-ttu-id="e6672-163">**Diagramok**</span><span class="sxs-lookup"><span data-stu-id="e6672-163">**Charts**</span></span> 
- <span data-ttu-id="e6672-164">Beszerzési folyó év, hónap / nap szerint (vonaldiagram)</span><span class="sxs-lookup"><span data-stu-id="e6672-164">Purchase current year by month / day (line chart)</span></span>
- <span data-ttu-id="e6672-165">Beszerzés, jelenlegi és az előző év (vonal- és oszlopdiagram)</span><span class="sxs-lookup"><span data-stu-id="e6672-165">Purchase current and last year (line and column chart)</span></span>

<span data-ttu-id="e6672-166">**Példa**</span><span class="sxs-lookup"><span data-stu-id="e6672-166">**Example**</span></span>
<img src="media/PurchByTIme.png" alt="Purchase by Time">

### <a name="purchase-spend-analysis-by-vendor-report-page"></a><span data-ttu-id="e6672-167">Beszerzési kiadások elemzése beszállító szerint lapján</span><span class="sxs-lookup"><span data-stu-id="e6672-167">Purchase spend analysis by vendor report page</span></span>

<span data-ttu-id="e6672-168">**Diagramok**</span><span class="sxs-lookup"><span data-stu-id="e6672-168">**Charts**</span></span> 
- <span data-ttu-id="e6672-169">A legjobb szállítói beszerzési %-a a beszerzésekből (tölcsér)</span><span class="sxs-lookup"><span data-stu-id="e6672-169">Top 10 vendor purchase % of purchase (funnel)</span></span>
- <span data-ttu-id="e6672-170">Top 10 szállító megnövekedett kiadásokkal egy éves időszakban</span><span class="sxs-lookup"><span data-stu-id="e6672-170">Top 10 vendors with increased spending YOY</span></span>
- <span data-ttu-id="e6672-171">Top 10 szállító csökkent kiadásokkal egy éves időszakban</span><span class="sxs-lookup"><span data-stu-id="e6672-171">Top 10 vendors with decreased spending YOY</span></span>

<span data-ttu-id="e6672-172">**Példa** 
</span><span class="sxs-lookup"><span data-stu-id="e6672-172">**Example** 
</span></span><img src="media/PurchSpendAnalysisByVendor.png" alt="Purchase spend by vendor">


## <a name="data-model-and-entities"></a><span data-ttu-id="e6672-173">Adatmodell és entitások</span><span class="sxs-lookup"><span data-stu-id="e6672-173">Data model and entities</span></span>
<span data-ttu-id="e6672-174">A **Beszerzési kiadások elemzése** Power BI tartalom jelentési oldalainak feltöltésére a következő adatok szolgálnak.</span><span class="sxs-lookup"><span data-stu-id="e6672-174">The following data is used to fill the report pages in the **Purchase spend analysis** Power BI content.</span></span> <span data-ttu-id="e6672-175">Ezeket az adatokat az Entitástárban lebonyolított összesített mérések jelenítik meg.</span><span class="sxs-lookup"><span data-stu-id="e6672-175">This data is represented as aggregate measurements that are staged in the Entity store.</span></span> <span data-ttu-id="e6672-176">Az entitástár az analitikai célokra optimalizált Microsoft SQL Server adatbázisa.</span><span class="sxs-lookup"><span data-stu-id="e6672-176">The Entity store is a Microsoft SQL Server database that is optimized for analytics.</span></span> <span data-ttu-id="e6672-177">További tudnivalókért lásd: [Power BI integrációja az entitástárral](power-bi-integration-entity-store.md).</span><span class="sxs-lookup"><span data-stu-id="e6672-177">For more information, see [Power BI integration with Entity store](power-bi-integration-entity-store.md).</span></span>

<span data-ttu-id="e6672-178">A tartalomcsomag összesítő mértékek a következőkben rendelkezésre álló összesítő mértékek részhalmazát alkotják: Purchase Cube in Microsoft Dynamics AX 2012 és Microsoft Dynamics AX 2012 R3.</span><span class="sxs-lookup"><span data-stu-id="e6672-178">The aggregate measurements in this content are the subset of aggregate measurements that were available in the Purchase Cube in Microsoft Dynamics AX 2012 and Microsoft Dynamics AX 2012 R3.</span></span> <span data-ttu-id="e6672-179">A kocka összesítő mértékeinek előkészítéséhez az entitástárban, a mértékeket központilag telepíthetővé kell tenni.</span><span class="sxs-lookup"><span data-stu-id="e6672-179">To stage the cube's aggregate measurements in the Entity store, you must make them deployable.</span></span> <span data-ttu-id="e6672-180">További információért lásd a következő blogbejegyzést az összesítő mértékek előkészítésének eljárásáról az entitástárban: [Power BI és az entitástár integrálása](power-bi-integration-entity-store.md).</span><span class="sxs-lookup"><span data-stu-id="e6672-180">For more information, see the procedure for staging aggregate measurements in the Entity store in [Power BI integration with Entity store](power-bi-integration-entity-store.md).</span></span> <span data-ttu-id="e6672-181">A következő kulcs összesítő mértékek közvetlenül a számla sorai entitásból érhetők el, és a tartalom alapjául szolgálnak.</span><span class="sxs-lookup"><span data-stu-id="e6672-181">The following key aggregate measurements are available directly from the Invoice lines entity and are used as the basis of the content.</span></span>

| <span data-ttu-id="e6672-182">Entitás</span><span class="sxs-lookup"><span data-stu-id="e6672-182">Entity</span></span>        | <span data-ttu-id="e6672-183">Kulcs összesítő mértékek</span><span class="sxs-lookup"><span data-stu-id="e6672-183">Key aggregate measurements</span></span> | <span data-ttu-id="e6672-184">Adatforrás</span><span class="sxs-lookup"><span data-stu-id="e6672-184">Data source</span></span>                                 | <span data-ttu-id="e6672-185">Mező</span><span class="sxs-lookup"><span data-stu-id="e6672-185">Field</span></span>              | <span data-ttu-id="e6672-186">Leírás</span><span class="sxs-lookup"><span data-stu-id="e6672-186">Description</span></span>                            |
|---------------|----------------------------|---------------------------------------------|--------------------|----------------------------------------|
| <span data-ttu-id="e6672-187">Számlasorok</span><span class="sxs-lookup"><span data-stu-id="e6672-187">Invoice lines</span></span> | <span data-ttu-id="e6672-188">Beszerzés</span><span class="sxs-lookup"><span data-stu-id="e6672-188">Purchase</span></span>                   | <span data-ttu-id="e6672-189">VendInvoiceTrans</span><span class="sxs-lookup"><span data-stu-id="e6672-189">VendInvoiceTrans</span></span>                            | <span data-ttu-id="e6672-190">SUM(LineAmountMST)</span><span class="sxs-lookup"><span data-stu-id="e6672-190">SUM(LineAmountMST)</span></span> | <span data-ttu-id="e6672-191">Összeg a könyvelési pénznemben.</span><span class="sxs-lookup"><span data-stu-id="e6672-191">The amount in the accounting currency.</span></span> |

<span data-ttu-id="e6672-192">Az alábbi táblázat a kulcs mértékeket mutatja, amelyeknek a kiszámítása a tartalomban történik a számla sorai entitásból.</span><span class="sxs-lookup"><span data-stu-id="e6672-192">The following table shows the key measurements in the content that are calculated from the Invoice lines entity.</span></span>

| <span data-ttu-id="e6672-193">Méret</span><span class="sxs-lookup"><span data-stu-id="e6672-193">Measure</span></span>               | <span data-ttu-id="e6672-194">Számítás</span><span class="sxs-lookup"><span data-stu-id="e6672-194">Calculation</span></span>                                                                                         |
|-----------------------|-----------------------------------------------------------------------------------------------------|
| <span data-ttu-id="e6672-195">Aktuális év beszerzései</span><span class="sxs-lookup"><span data-stu-id="e6672-195">Purchase current year</span></span> | <span data-ttu-id="e6672-196">Aktuális év beszerzései = SUM('Számlasorok'\[Beszerzés\])</span><span class="sxs-lookup"><span data-stu-id="e6672-196">Purchase current year = SUM('Invoice lines'\[Purchase\])</span></span>                                            |
| <span data-ttu-id="e6672-197">Tavalyi év beszerzései</span><span class="sxs-lookup"><span data-stu-id="e6672-197">Purchase last year</span></span>    | <span data-ttu-id="e6672-198">Tavalyi év beszerzései = CALCULATE(SUM('Számlasorok'\[Beszerzés\]), SAMEPERIODLASTYEAR(Dátumok\[Dátum\]))</span><span class="sxs-lookup"><span data-stu-id="e6672-198">Purchase last year = CALCULATE(SUM('Invoice lines'\[Purchase\]), SAMEPERIODLASTYEAR(Dates\[Date\]))</span></span> |
| <span data-ttu-id="e6672-199">Egy éves időszak beszerzési növekedése</span><span class="sxs-lookup"><span data-stu-id="e6672-199">YOY purchase growth</span></span>   | <span data-ttu-id="e6672-200">Egy éves időszak beszerzési növekedése = \[Aktuális év beszerzései\] – \[Tavalyi év beszerzései\]</span><span class="sxs-lookup"><span data-stu-id="e6672-200">YOY purchase growth = \[Purchase current year\] – \[Purchase last year\]</span></span>                            |

<span data-ttu-id="e6672-201">A tartalomban a következő fő dimenziók szolgálnak szűrőként az összesítő mértékek szeletelésére, nagyobb részletességet és mélyebb elemzési betekintések elérését téve lehetővé.</span><span class="sxs-lookup"><span data-stu-id="e6672-201">The following key dimensions in the content are used as filters to slice the aggregate measurements, so that you can achieve more granularity and gain deeper analytical insights.</span></span>

| <span data-ttu-id="e6672-202">Entitás</span><span class="sxs-lookup"><span data-stu-id="e6672-202">Entity</span></span>                 | <span data-ttu-id="e6672-203">Példák az attribútumok</span><span class="sxs-lookup"><span data-stu-id="e6672-203">Examples of attributes</span></span>                                |
|------------------------|-------------------------------------------------------|
| <span data-ttu-id="e6672-204">Szállítók</span><span class="sxs-lookup"><span data-stu-id="e6672-204">Vendors</span></span>                | <span data-ttu-id="e6672-205">Szállítói csoportok, Szállító országok vagy régiók, Szállító neve</span><span class="sxs-lookup"><span data-stu-id="e6672-205">Vendor groups, Vendor country or regions, Vendor name</span></span> |
| <span data-ttu-id="e6672-206">Termékek</span><span class="sxs-lookup"><span data-stu-id="e6672-206">Products</span></span>               | <span data-ttu-id="e6672-207">Termékszám, Termék neve, Cikkcsoportok neve</span><span class="sxs-lookup"><span data-stu-id="e6672-207">Product number, Product name, Item groups name</span></span>        |
| <span data-ttu-id="e6672-208">Beszerzési kategóriák</span><span class="sxs-lookup"><span data-stu-id="e6672-208">Procurement categories</span></span> | <span data-ttu-id="e6672-209">Beszerzési kategória, Beszerzési kategórianevek</span><span class="sxs-lookup"><span data-stu-id="e6672-209">Procurement category, Procurement category names</span></span>      |
| <span data-ttu-id="e6672-210">Jogi személyek</span><span class="sxs-lookup"><span data-stu-id="e6672-210">Legal entities</span></span>         | <span data-ttu-id="e6672-211">Jogi személy neve</span><span class="sxs-lookup"><span data-stu-id="e6672-211">Legal entity name</span></span>                                     |
| <span data-ttu-id="e6672-212">Dátumok</span><span class="sxs-lookup"><span data-stu-id="e6672-212">Dates</span></span>                  | <span data-ttu-id="e6672-213">Dátumok, Év eltolása</span><span class="sxs-lookup"><span data-stu-id="e6672-213">Dates, Year offset</span></span>                                    |

<span data-ttu-id="e6672-214">Alapértelmezés szerint a tartalom a folyó naptári év adatait jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="e6672-214">By default, the content shows data for the current calendar year.</span></span> <span data-ttu-id="e6672-215">Azonban módosíthatja a dátumszűrőt a jelentésszűrők szakaszban.</span><span class="sxs-lookup"><span data-stu-id="e6672-215">However, you can change the date filter in the report filters section.</span></span> <span data-ttu-id="e6672-216">A vállalatszűrőt is módosíthatja.</span><span class="sxs-lookup"><span data-stu-id="e6672-216">You can also change the company filter.</span></span>
