---
title: Beszerzési és ráfordítási elemzés Power BI tartalom
description: Ez a témakör a Beszerzési kiadások elemzése Power BI tartalom modul tartalmát ismerteti.
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
ms.custom: 265434
ms.assetid: 3cd9dfce-2687-4303-bc78-349e7cb5ea75
ms.search.region: global
ms.author: fdahl
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 5914abaafab509e278d7a85441928feddb0b5164
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/30/2021
ms.locfileid: "5093442"
---
# <a name="purchase-spend-analysis-power-bi-content"></a><span data-ttu-id="5b392-103">Beszerzési és ráfordítási elemzés Power BI tartalom</span><span class="sxs-lookup"><span data-stu-id="5b392-103">Purchase spend analysis Power BI content</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5b392-104">Ez a témakör a **Beszerzési kiadások elemzése** Microsoft Power BI tartalom modul tartalmát ismerteti.</span><span class="sxs-lookup"><span data-stu-id="5b392-104">This topic describes what is included in the **Purchase spend analysis** Microsoft Power BI content.</span></span> <span data-ttu-id="5b392-105">Leírja, hogy hogyan kell hozzáférni a Power BI-jelentésekhez, és információkat nyújt a tartalomcsomag összeállításához korábban használt entitásokkal és adatmodellekkel kapcsolatban.</span><span class="sxs-lookup"><span data-stu-id="5b392-105">It explains how to access the Power BI reports, and provides information about the data model and entities that are used to build the content.</span></span>

## <a name="overview"></a><span data-ttu-id="5b392-106">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="5b392-106">Overview</span></span>

<span data-ttu-id="5b392-107">A **Beszerzési kiadások elemzése** Power BI-tartalom a beszerzési vezetők és olyan vezetők segítségével készült, akik a beszerzési kiadások költségvetéésének nyomon követésért felelősek.</span><span class="sxs-lookup"><span data-stu-id="5b392-107">The **Purchase spend analysis** Power BI content was designed to help purchasing managers and managers who are responsible for budgets keep track of purchase spending.</span></span> <span data-ttu-id="5b392-108">A vezetők az alábbi módokon elemezhetik a beszerzési költségeket:</span><span class="sxs-lookup"><span data-stu-id="5b392-108">Managers can analyze purchase spending in the following ways:</span></span>

- <span data-ttu-id="5b392-109">Az év megadott napjáig tartó beszerzések (szállítói csoport és az egyes szállítók , beszerzési kategória és egyes termékek, valamint a szállító helye szerint)</span><span class="sxs-lookup"><span data-stu-id="5b392-109">Year-to-date purchase (by vendor group and individual vendors, procurement category and individual products, and vendor location)</span></span>
- <span data-ttu-id="5b392-110">Egy éves időszak beszerzési változásai (szállítói csoport és a beszerzési kategória szerint)</span><span class="sxs-lookup"><span data-stu-id="5b392-110">Year-over-year purchase change (by vendor group and procurement category)</span></span>

<span data-ttu-id="5b392-111">A tartalom beszerzési tranzakciós adatokat használ, és egyrészt összesített adatokat nyújt a vállalati szintű beszerzési számokról, másrészt a kiadások szállító és termék szerinti lebontását kínálja.</span><span class="sxs-lookup"><span data-stu-id="5b392-111">The content uses purchase transactional data, and provides both an aggregate view of the company-wide purchase figures and a breakdown of purchase spending by vendor and product.</span></span> <span data-ttu-id="5b392-112">A jelentések kiemelik a beszerzési kiadások időbeli változásait.</span><span class="sxs-lookup"><span data-stu-id="5b392-112">Reports highlight changes in purchase spending over time.</span></span> <span data-ttu-id="5b392-113">Ezért a jelentések riasztásra használhatók a menedzserek számára a kiadások pozitív és negatív trendjeiről az egyes szállítókra és termékekre nézve.</span><span class="sxs-lookup"><span data-stu-id="5b392-113">Therefore, the reports can be used to alert managers about positive and negative spending trends for individual vendors and products.</span></span> <span data-ttu-id="5b392-114">Ezenkívül diagramok jelenítik meg a beszerzési kiadásokat a különböző beszerzési kategóriákra és szállítói csoportokra nézve.</span><span class="sxs-lookup"><span data-stu-id="5b392-114">Additionally, charts show purchase spending for different procurement categories and vendor groups.</span></span> <span data-ttu-id="5b392-115">Ezért a kategória- és regionális vezetők a diagramok segítségével a kiadások viselkedési változásait azonosíthatják.</span><span class="sxs-lookup"><span data-stu-id="5b392-115">Therefore, category and regional managers can use the charts to help identify changes in spending behavior.</span></span>

## <a name="accessing-the-power-bi-content"></a><span data-ttu-id="5b392-116">A Power BI tartalom elérése</span><span class="sxs-lookup"><span data-stu-id="5b392-116">Accessing the Power BI content</span></span>
<span data-ttu-id="5b392-117">A **Beszerzési és ráfordítási elemzés** Power BI tartalom a **Beszerzési és ráfordítási elemzés** oldalon látható (**Beszerzés és forrás** \> **Lekérdezések és jelentések** \> **Beszerzési teljesítményelemzés** \> **Beszerzési és ráfordítási elemzés**).</span><span class="sxs-lookup"><span data-stu-id="5b392-117">The **Purchase spend analysis** Power BI content is shown on the **Purchase and spend analysis** page (**Procurement and sourcing** \> **Inquiries and reports** \> **Purchase performance analysis** \> **Purchase and spend analysis**).</span></span>

## <a name="metrics-that-are-included-in-the-power-bi-content"></a><span data-ttu-id="5b392-118">Mérőszámok, amelyek a Power BI tartalomban szerepelnek</span><span class="sxs-lookup"><span data-stu-id="5b392-118">Metrics that are included in the Power BI content</span></span>
<span data-ttu-id="5b392-119">A **Beszerzési kiadások elemzése** Power BI tartalomcsomag tartalmaz egy jelentést, amely metrikák készletéből áll.</span><span class="sxs-lookup"><span data-stu-id="5b392-119">The **Purchase spend analysis** Power BI content includes a report that consists of a set of metrics.</span></span> <span data-ttu-id="5b392-120">Ezek a metrikák mozaikok, táblázatok és diagramok formájában jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="5b392-120">These metrics are visualized as charts, tiles, and tables.</span></span> 

<span data-ttu-id="5b392-121">Az alábbi szakaszok tartalmazzák a megjelenítések áttekintését.</span><span class="sxs-lookup"><span data-stu-id="5b392-121">The following sections provide an overview of the visualizations.</span></span>

### <a name="purchase-by-vendor-report-page"></a><span data-ttu-id="5b392-122">Beszerzés a szállítói jelentés lapján</span><span class="sxs-lookup"><span data-stu-id="5b392-122">Purchase by vendor report page</span></span>
<span data-ttu-id="5b392-123">**Diagramok**</span><span class="sxs-lookup"><span data-stu-id="5b392-123">**Charts**</span></span>
- <span data-ttu-id="5b392-124">10 legmagasabb szállító beszerzés szerint (halmozott sávdiagram)</span><span class="sxs-lookup"><span data-stu-id="5b392-124">Top 10 vendors by purchase (stacked bar chart)</span></span>
- <span data-ttu-id="5b392-125">Teljes beszerzések szállítói csoport / ország / név szerint (kördiagram)</span><span class="sxs-lookup"><span data-stu-id="5b392-125">Total purchase by vendor group / country / name (pie chart)</span></span>
- <span data-ttu-id="5b392-126">Beszerzések szállítói csoport / ország / név szerint (oszlopdiagram)</span><span class="sxs-lookup"><span data-stu-id="5b392-126">Purchase by vendor group / country / name (column chart)</span></span>
- <span data-ttu-id="5b392-127">Átlagos beszerzések szállítói csoport / ország / név szerint (oszlopdiagram)</span><span class="sxs-lookup"><span data-stu-id="5b392-127">Average purchase by vendor group / country / name (column chart)</span></span>

<span data-ttu-id="5b392-128">**Mozaik**</span><span class="sxs-lookup"><span data-stu-id="5b392-128">**Tiles**</span></span>
- <span data-ttu-id="5b392-129">Összes beszerzés</span><span class="sxs-lookup"><span data-stu-id="5b392-129">Total purchase</span></span>
- <span data-ttu-id="5b392-130">Egy éves időszak beszerzési növekedése</span><span class="sxs-lookup"><span data-stu-id="5b392-130">YOY purchase growth</span></span>
- <span data-ttu-id="5b392-131">Összes szállító száma</span><span class="sxs-lookup"><span data-stu-id="5b392-131">Total # vendors</span></span>
- <span data-ttu-id="5b392-132">Aktív szállítók száma</span><span class="sxs-lookup"><span data-stu-id="5b392-132">Total # of active vendors</span></span>

<span data-ttu-id="5b392-133">**Példa**</span><span class="sxs-lookup"><span data-stu-id="5b392-133">**Example**</span></span>
<img src="media/spend1.png" alt="Purchase by vendor">

### <a name="purchase-by-product-report-page"></a><span data-ttu-id="5b392-134">Beszerzés a termékjelentés lapján</span><span class="sxs-lookup"><span data-stu-id="5b392-134">Purchase by product report page</span></span>

<span data-ttu-id="5b392-135">**Diagramok**</span><span class="sxs-lookup"><span data-stu-id="5b392-135">**Charts**</span></span>
- <span data-ttu-id="5b392-136">Beszerzés beszerzési kategória / termék neve szerint (oszlopdiagram)</span><span class="sxs-lookup"><span data-stu-id="5b392-136">Purchase by procurement category / product name (column chart)</span></span>
- <span data-ttu-id="5b392-137">Összes beszerzés beszerzési kategória / termék neve szerint (kördiagram)</span><span class="sxs-lookup"><span data-stu-id="5b392-137">Total purchase by procurement category / product name (pie chart)</span></span>
- <span data-ttu-id="5b392-138">10 legmagasabb termék beszerzés szerint (halmozott sávdiagram)</span><span class="sxs-lookup"><span data-stu-id="5b392-138">Top 10 products by purchase (stacked bar chart)</span></span>

<span data-ttu-id="5b392-139">**Mozaik**</span><span class="sxs-lookup"><span data-stu-id="5b392-139">**Tiles**</span></span>
- <span data-ttu-id="5b392-140">Termékek összes száma</span><span class="sxs-lookup"><span data-stu-id="5b392-140">Total # of products</span></span></li>
- <span data-ttu-id="5b392-141">Összes aktív termék, teljes termékszám százaléka</span><span class="sxs-lookup"><span data-stu-id="5b392-141">Total active products percentage of total # of products</span></span>
- <span data-ttu-id="5b392-142">A beszerzések 80%-át lefedő termékek száma</span><span class="sxs-lookup"><span data-stu-id="5b392-142">Number of products accounting for 80% purchase</span></span>

<span data-ttu-id="5b392-143">**Példa**</span><span class="sxs-lookup"><span data-stu-id="5b392-143">**Example**</span></span>


<img src="media/purchaseByProduct.png" alt="Purchase by Product">

### <a name="purchase-by-period-report-page"></a><span data-ttu-id="5b392-144">Beszerzés a az időszakjelentés lapján</span><span class="sxs-lookup"><span data-stu-id="5b392-144">Purchase by period report page</span></span>
<span data-ttu-id="5b392-145">Ez az oldal az erre az évre és az előző évre eső beszerzéseket, és növekedés beszerzési kategória szerint adatokat mutatja.</span><span class="sxs-lookup"><span data-stu-id="5b392-145">This page shows purchases this year and last year, and growth by procurement category.</span></span>

<span data-ttu-id="5b392-146">**Diagramok**</span><span class="sxs-lookup"><span data-stu-id="5b392-146">**Charts**</span></span> 
- <span data-ttu-id="5b392-147">Beszerzés hónap / nap szerint (oszlopdiagram)</span><span class="sxs-lookup"><span data-stu-id="5b392-147">Purchase by month / day (column chart)</span></span>
- <span data-ttu-id="5b392-148">Összesített beszerzés, egy éves időszak eltérése (vízesésdiagram)</span><span class="sxs-lookup"><span data-stu-id="5b392-148">Cumulative purchase YOY variance (waterfall chart)</span></span>
- <span data-ttu-id="5b392-149">Teljes beszerzés, egy éves időszak növekedése (oszlopdiagram)</span><span class="sxs-lookup"><span data-stu-id="5b392-149">Total purchase YOY growth (column chart)</span></span>
- <span data-ttu-id="5b392-150">Beszerzési kimutatás (mátrix)</span><span class="sxs-lookup"><span data-stu-id="5b392-150">Procurement statement (matrix)</span></span>

<span data-ttu-id="5b392-151">**Mozaik**</span><span class="sxs-lookup"><span data-stu-id="5b392-151">**Tiles**</span></span>
- <span data-ttu-id="5b392-152">Egy éves időszak beszerzési növekedése</span><span class="sxs-lookup"><span data-stu-id="5b392-152">YOY purchase growth</span></span>
- <span data-ttu-id="5b392-153">Egy éves időszak beszerzési növekedése %</span><span class="sxs-lookup"><span data-stu-id="5b392-153">YOY purchase growth %</span></span>

<span data-ttu-id="5b392-154">**Példa**</span><span class="sxs-lookup"><span data-stu-id="5b392-154">**Example**</span></span>
<img src="media/purchaseByPeriod.png" alt="Purchase by Period">

### <a name="purchase-by-vendor-location-report-page"></a><span data-ttu-id="5b392-155">Beszerzés a szállítói helyjelentés lapján</span><span class="sxs-lookup"><span data-stu-id="5b392-155">Purchase by vendor location report page</span></span>

<span data-ttu-id="5b392-156">**Diagramok**</span><span class="sxs-lookup"><span data-stu-id="5b392-156">**Charts**</span></span>
- <span data-ttu-id="5b392-157">Beszerzés település szerint</span><span class="sxs-lookup"><span data-stu-id="5b392-157">Purchase by city</span></span>
- <span data-ttu-id="5b392-158">Egy éves időszak beszerzési növekedési százaléka</span><span class="sxs-lookup"><span data-stu-id="5b392-158">Purchase YOY growth %</span></span>
- <span data-ttu-id="5b392-159">Beszerzési ország szerint</span><span class="sxs-lookup"><span data-stu-id="5b392-159">Purchase by country</span></span>

<span data-ttu-id="5b392-160">**Példa**</span><span class="sxs-lookup"><span data-stu-id="5b392-160">**Example**</span></span>
<img src="media/purchByVendorLocation.png" alt="Purchase by Vendor Location">

### <a name="purchase-spend-analysis-by-time-report-page"></a><span data-ttu-id="5b392-161">Beszerzési kiadások elemzése idő szerint lapján</span><span class="sxs-lookup"><span data-stu-id="5b392-161">Purchase spend analysis by time report page</span></span>

<span data-ttu-id="5b392-162">**Diagramok**</span><span class="sxs-lookup"><span data-stu-id="5b392-162">**Charts**</span></span> 
- <span data-ttu-id="5b392-163">Beszerzési folyó év, hónap / nap szerint (vonaldiagram)</span><span class="sxs-lookup"><span data-stu-id="5b392-163">Purchase current year by month / day (line chart)</span></span>
- <span data-ttu-id="5b392-164">Beszerzés, jelenlegi és az előző év (vonal- és oszlopdiagram)</span><span class="sxs-lookup"><span data-stu-id="5b392-164">Purchase current and last year (line and column chart)</span></span>

<span data-ttu-id="5b392-165">**Példa**</span><span class="sxs-lookup"><span data-stu-id="5b392-165">**Example**</span></span>
<img src="media/PurchByTIme.png" alt="Purchase by Time">

### <a name="purchase-spend-analysis-by-vendor-report-page"></a><span data-ttu-id="5b392-166">Beszerzési kiadások elemzése beszállító szerint lapján</span><span class="sxs-lookup"><span data-stu-id="5b392-166">Purchase spend analysis by vendor report page</span></span>

<span data-ttu-id="5b392-167">**Diagramok**</span><span class="sxs-lookup"><span data-stu-id="5b392-167">**Charts**</span></span> 
- <span data-ttu-id="5b392-168">A legjobb szállítói beszerzési %-a a beszerzésekből (tölcsér)</span><span class="sxs-lookup"><span data-stu-id="5b392-168">Top 10 vendor purchase % of purchase (funnel)</span></span>
- <span data-ttu-id="5b392-169">Top 10 szállító megnövekedett kiadásokkal egy éves időszakban</span><span class="sxs-lookup"><span data-stu-id="5b392-169">Top 10 vendors with increased spending YOY</span></span>
- <span data-ttu-id="5b392-170">Top 10 szállító csökkent kiadásokkal egy éves időszakban</span><span class="sxs-lookup"><span data-stu-id="5b392-170">Top 10 vendors with decreased spending YOY</span></span>

<span data-ttu-id="5b392-171">**Példa** 
</span><span class="sxs-lookup"><span data-stu-id="5b392-171">**Example** 
</span></span><img src="media/PurchSpendAnalysisByVendor.png" alt="Purchase spend by vendor">


## <a name="data-model-and-entities"></a><span data-ttu-id="5b392-172">Adatmodell és entitások</span><span class="sxs-lookup"><span data-stu-id="5b392-172">Data model and entities</span></span>
<span data-ttu-id="5b392-173">A **Beszerzési kiadások elemzése** Power BI tartalom jelentési oldalainak feltöltésére a következő adatok szolgálnak.</span><span class="sxs-lookup"><span data-stu-id="5b392-173">The following data is used to fill the report pages in the **Purchase spend analysis** Power BI content.</span></span> <span data-ttu-id="5b392-174">Ezeket az adatokat az Entitástárban lebonyolított összesített mérések jelenítik meg.</span><span class="sxs-lookup"><span data-stu-id="5b392-174">This data is represented as aggregate measurements that are staged in the Entity store.</span></span> <span data-ttu-id="5b392-175">Az entitástár az analitikai célokra optimalizált Microsoft SQL Server adatbázisa.</span><span class="sxs-lookup"><span data-stu-id="5b392-175">The Entity store is a Microsoft SQL Server database that is optimized for analytics.</span></span> <span data-ttu-id="5b392-176">További tudnivalókért lásd: [Power BI integrációja az entitástárral](power-bi-integration-entity-store.md).</span><span class="sxs-lookup"><span data-stu-id="5b392-176">For more information, see [Power BI integration with Entity store](power-bi-integration-entity-store.md).</span></span>

<span data-ttu-id="5b392-177">A tartalomcsomag összesítő mértékek a következőkben rendelkezésre álló összesítő mértékek részhalmazát alkotják: Purchase Cube in Microsoft Dynamics AX 2012 és Microsoft Dynamics AX 2012 R3.</span><span class="sxs-lookup"><span data-stu-id="5b392-177">The aggregate measurements in this content are the subset of aggregate measurements that were available in the Purchase Cube in Microsoft Dynamics AX 2012 and Microsoft Dynamics AX 2012 R3.</span></span> <span data-ttu-id="5b392-178">A kocka összesítő mértékeinek előkészítéséhez az entitástárban, a mértékeket központilag telepíthetővé kell tenni.</span><span class="sxs-lookup"><span data-stu-id="5b392-178">To stage the cube's aggregate measurements in the Entity store, you must make them deployable.</span></span> <span data-ttu-id="5b392-179">További információért lásd a következő blogbejegyzést az összesítő mértékek előkészítésének eljárásáról az entitástárban: [Power BI és az entitástár integrálása](power-bi-integration-entity-store.md).</span><span class="sxs-lookup"><span data-stu-id="5b392-179">For more information, see the procedure for staging aggregate measurements in the Entity store in [Power BI integration with Entity store](power-bi-integration-entity-store.md).</span></span> <span data-ttu-id="5b392-180">A következő kulcs összesítő mértékek közvetlenül a számla sorai entitásból érhetők el, és a tartalom alapjául szolgálnak.</span><span class="sxs-lookup"><span data-stu-id="5b392-180">The following key aggregate measurements are available directly from the Invoice lines entity and are used as the basis of the content.</span></span>

| <span data-ttu-id="5b392-181">Entitás</span><span class="sxs-lookup"><span data-stu-id="5b392-181">Entity</span></span>        | <span data-ttu-id="5b392-182">Kulcs összesítő mértékek</span><span class="sxs-lookup"><span data-stu-id="5b392-182">Key aggregate measurements</span></span> | <span data-ttu-id="5b392-183">Adatforrás</span><span class="sxs-lookup"><span data-stu-id="5b392-183">Data source</span></span>                                 | <span data-ttu-id="5b392-184">Mező</span><span class="sxs-lookup"><span data-stu-id="5b392-184">Field</span></span>              | <span data-ttu-id="5b392-185">Leírás</span><span class="sxs-lookup"><span data-stu-id="5b392-185">Description</span></span>                            |
|---------------|----------------------------|---------------------------------------------|--------------------|----------------------------------------|
| <span data-ttu-id="5b392-186">Számlasorok</span><span class="sxs-lookup"><span data-stu-id="5b392-186">Invoice lines</span></span> | <span data-ttu-id="5b392-187">Beszerzés</span><span class="sxs-lookup"><span data-stu-id="5b392-187">Purchase</span></span>                   | <span data-ttu-id="5b392-188">VendInvoiceTrans</span><span class="sxs-lookup"><span data-stu-id="5b392-188">VendInvoiceTrans</span></span>                            | <span data-ttu-id="5b392-189">SUM(LineAmountMST)</span><span class="sxs-lookup"><span data-stu-id="5b392-189">SUM(LineAmountMST)</span></span> | <span data-ttu-id="5b392-190">Összeg a könyvelési pénznemben.</span><span class="sxs-lookup"><span data-stu-id="5b392-190">The amount in the accounting currency.</span></span> |

<span data-ttu-id="5b392-191">Az alábbi táblázat a kulcs mértékeket mutatja, amelyeknek a kiszámítása a tartalomban történik a számla sorai entitásból.</span><span class="sxs-lookup"><span data-stu-id="5b392-191">The following table shows the key measurements in the content that are calculated from the Invoice lines entity.</span></span>

| <span data-ttu-id="5b392-192">Méret</span><span class="sxs-lookup"><span data-stu-id="5b392-192">Measure</span></span>               | <span data-ttu-id="5b392-193">Számítás</span><span class="sxs-lookup"><span data-stu-id="5b392-193">Calculation</span></span>                                                                                         |
|-----------------------|-----------------------------------------------------------------------------------------------------|
| <span data-ttu-id="5b392-194">Aktuális év beszerzései</span><span class="sxs-lookup"><span data-stu-id="5b392-194">Purchase current year</span></span> | <span data-ttu-id="5b392-195">Aktuális év beszerzései = SUM('Számlasorok'\[Beszerzés\])</span><span class="sxs-lookup"><span data-stu-id="5b392-195">Purchase current year = SUM('Invoice lines'\[Purchase\])</span></span>                                            |
| <span data-ttu-id="5b392-196">Tavalyi év beszerzései</span><span class="sxs-lookup"><span data-stu-id="5b392-196">Purchase last year</span></span>    | <span data-ttu-id="5b392-197">Tavalyi év beszerzései = CALCULATE(SUM('Számlasorok'\[Beszerzés\]), SAMEPERIODLASTYEAR(Dátumok\[Dátum\]))</span><span class="sxs-lookup"><span data-stu-id="5b392-197">Purchase last year = CALCULATE(SUM('Invoice lines'\[Purchase\]), SAMEPERIODLASTYEAR(Dates\[Date\]))</span></span> |
| <span data-ttu-id="5b392-198">Egy éves időszak beszerzési növekedése</span><span class="sxs-lookup"><span data-stu-id="5b392-198">YOY purchase growth</span></span>   | <span data-ttu-id="5b392-199">Egy éves időszak beszerzési növekedése = \[Aktuális év beszerzései\] – \[Tavalyi év beszerzései\]</span><span class="sxs-lookup"><span data-stu-id="5b392-199">YOY purchase growth = \[Purchase current year\] – \[Purchase last year\]</span></span>                            |

<span data-ttu-id="5b392-200">A tartalomban a következő fő dimenziók szolgálnak szűrőként az összesítő mértékek szeletelésére, nagyobb részletességet és mélyebb elemzési betekintések elérését téve lehetővé.</span><span class="sxs-lookup"><span data-stu-id="5b392-200">The following key dimensions in the content are used as filters to slice the aggregate measurements, so that you can achieve more granularity and gain deeper analytical insights.</span></span>

| <span data-ttu-id="5b392-201">Entitás</span><span class="sxs-lookup"><span data-stu-id="5b392-201">Entity</span></span>                 | <span data-ttu-id="5b392-202">Példák az attribútumok</span><span class="sxs-lookup"><span data-stu-id="5b392-202">Examples of attributes</span></span>                                |
|------------------------|-------------------------------------------------------|
| <span data-ttu-id="5b392-203">Szállítók</span><span class="sxs-lookup"><span data-stu-id="5b392-203">Vendors</span></span>                | <span data-ttu-id="5b392-204">Szállítói csoportok, Szállító országok vagy régiók, Szállító neve</span><span class="sxs-lookup"><span data-stu-id="5b392-204">Vendor groups, Vendor country or regions, Vendor name</span></span> |
| <span data-ttu-id="5b392-205">Termékek</span><span class="sxs-lookup"><span data-stu-id="5b392-205">Products</span></span>               | <span data-ttu-id="5b392-206">Termékszám, Termék neve, Cikkcsoportok neve</span><span class="sxs-lookup"><span data-stu-id="5b392-206">Product number, Product name, Item groups name</span></span>        |
| <span data-ttu-id="5b392-207">Beszerzési kategóriák</span><span class="sxs-lookup"><span data-stu-id="5b392-207">Procurement categories</span></span> | <span data-ttu-id="5b392-208">Beszerzési kategória, Beszerzési kategórianevek</span><span class="sxs-lookup"><span data-stu-id="5b392-208">Procurement category, Procurement category names</span></span>      |
| <span data-ttu-id="5b392-209">Jogi személyek</span><span class="sxs-lookup"><span data-stu-id="5b392-209">Legal entities</span></span>         | <span data-ttu-id="5b392-210">Jogi személy neve</span><span class="sxs-lookup"><span data-stu-id="5b392-210">Legal entity name</span></span>                                     |
| <span data-ttu-id="5b392-211">Dátumok</span><span class="sxs-lookup"><span data-stu-id="5b392-211">Dates</span></span>                  | <span data-ttu-id="5b392-212">Dátumok, Év eltolása</span><span class="sxs-lookup"><span data-stu-id="5b392-212">Dates, Year offset</span></span>                                    |

<span data-ttu-id="5b392-213">Alapértelmezés szerint a tartalom a folyó naptári év adatait jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="5b392-213">By default, the content shows data for the current calendar year.</span></span> <span data-ttu-id="5b392-214">Azonban módosíthatja a dátumszűrőt a jelentésszűrők szakaszban.</span><span class="sxs-lookup"><span data-stu-id="5b392-214">However, you can change the date filter in the report filters section.</span></span> <span data-ttu-id="5b392-215">A vállalatszűrőt is módosíthatja.</span><span class="sxs-lookup"><span data-stu-id="5b392-215">You can also change the company filter.</span></span>
