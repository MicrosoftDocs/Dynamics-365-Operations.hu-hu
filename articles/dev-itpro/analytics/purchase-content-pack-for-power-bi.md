---
title: "Beszerzési kiadások elemzése Power BI-tartalom"
description: "Ez a témakör a Beszerzési kiadások elemzése Power BI-tartalom modul tartalmát ismerteti. Leírja, hogy hogyan kell hozzáférni a tartalomban szereplő jelentésekhez, és információkat nyújt a tartalom összeállításához használt entitásokkal és adatmodellekkel kapcsolatban."
author: FrankDahl
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 265434
ms.assetid: 3cd9dfce-2687-4303-bc78-349e7cb5ea75
ms.search.region: global
ms.author: fdahl
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 3e42746329b1194c0ce0e2fb5c476742259a5b43
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="purchase-spend-analysis-power-bi-content"></a><span data-ttu-id="d3ed5-104">Beszerzési kiadások elemzése Power BI-tartalom</span><span class="sxs-lookup"><span data-stu-id="d3ed5-104">Purchase spend analysis Power BI content</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="d3ed5-105">Ez a témakör a **Beszerzési kiadások elemzése** Power BI-tartalom modul tartalmát ismerteti.</span><span class="sxs-lookup"><span data-stu-id="d3ed5-105">This topic describes what is included in the **Purchase spend analysis** Microsoft Power BI content.</span></span> <span data-ttu-id="d3ed5-106">Leírja, hogy hogyan kell hozzáférni Power BI-jelentésekhez, és információkat nyújt a tartalom összeállításához használt entitásokkal és adatmodellekkel kapcsolatban.</span><span class="sxs-lookup"><span data-stu-id="d3ed5-106">It explains how to access the Power BI reports, and provides information about the data model and entities that are used to build the content.</span></span>

## <a name="overview"></a><span data-ttu-id="d3ed5-107">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="d3ed5-107">Overview</span></span>

<span data-ttu-id="d3ed5-108">A **Beszerzési kiadások elemzése** Power BI-tartalom a beszerzési vezetők és olyan vezetők segítségével készült, akik a beszerzési kiadások költségvetéésért felelősek.</span><span class="sxs-lookup"><span data-stu-id="d3ed5-108">The **Purchase spend analysis** Power BI content was designed to help purchasing managers and managers who are responsible for budgets keep an eye on purchase spending.</span></span> <span data-ttu-id="d3ed5-109">A vezetők az alábbi módokon elemezhetik a beszerzési költségeket:</span><span class="sxs-lookup"><span data-stu-id="d3ed5-109">Managers can analyze purchase spending in the following ways:</span></span>

-   <span data-ttu-id="d3ed5-110">Az év megadott napjáig tartó beszerzések (szállítói csoport és az egyes szállítók , beszerzési kategória és egyes termékek, valamint a szállító helye szerint)</span><span class="sxs-lookup"><span data-stu-id="d3ed5-110">Year-to-date purchase (by vendor group and individual vendors, procurement category and individual products, and vendor location)</span></span>
-   <span data-ttu-id="d3ed5-111">Egy éves időszak beszerzési változásai (szállítói csoport és a beszerzési kategória szerint)</span><span class="sxs-lookup"><span data-stu-id="d3ed5-111">Year-over-year purchase change (by vendor group and procurement category)</span></span>

<span data-ttu-id="d3ed5-112">A tartalom beszerzési tranzakciós adatokat használ, és egyrészt összesített adatokat nyújt a vállalati szintű beszerzési számokról, másrészt a kiadások szállító és termék szerinti lebontását kínálja.</span><span class="sxs-lookup"><span data-stu-id="d3ed5-112">The content uses purchase transactional data, and provides both an aggregate view of the company-wide purchase figures and a breakdown of purchase spending by vendor and product.</span></span> <span data-ttu-id="d3ed5-113">A jelentések kiemelik a beszerzési kiadások időbeli változásait.</span><span class="sxs-lookup"><span data-stu-id="d3ed5-113">Reports highlight changes in purchase spending over time.</span></span> <span data-ttu-id="d3ed5-114">Ezért a jelentések riasztásra használhatók a menedzserek számára a kiadások pozitív és negatív trendjeiről az egyes szállítókra és termékekre nézve.</span><span class="sxs-lookup"><span data-stu-id="d3ed5-114">Therefore, the reports can be used to alert managers about positive and negative spending trends for individual vendors and products.</span></span> <span data-ttu-id="d3ed5-115">Ezenkívül diagramok jelenítik meg a beszerzési kiadásokat a különböző beszerzési kategóriákra és szállítói csoportokra nézve.</span><span class="sxs-lookup"><span data-stu-id="d3ed5-115">Additionally, charts show purchase spending for different procurement categories and vendor groups.</span></span> <span data-ttu-id="d3ed5-116">Ezért a kategória- és regionális vezetők a diagramok segítségével a kiadások viselkedési változásait azonosíthatják.</span><span class="sxs-lookup"><span data-stu-id="d3ed5-116">Therefore, category and regional managers can use the charts to help identify changes in spending behavior.</span></span>

## <a name="accessing-the-power-bi-content"></a><span data-ttu-id="d3ed5-117">Power BI-tartalom elérése</span><span class="sxs-lookup"><span data-stu-id="d3ed5-117">Accessing the Power BI content</span></span>
<span data-ttu-id="d3ed5-118">Amennyiben a Microsoft Dynamics 365 for Finance and Operations Enterprise edition (2017. július) rendszert használja, a **Beszerzési kiadások elemzése** Power BI-tartalom a **Beszerzési és ráfordítási elemzés** (**Beszerzés és forrás** > **Lekérdezések és jelentések** > **Beszerzési teljesítményelemzés** > **Beszerzési és ráfordítási elemzés**) lap található.</span><span class="sxs-lookup"><span data-stu-id="d3ed5-118">If you're using Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (July 2017), the **Purchase spend analysis** Power BI content is shown on the **Purchase and spend analysis** page (**Procurement and sourcing** > **Inquiries and reports** > **Purchase performance analysis** > **Purchase and spend analysis**).</span></span> 

## <a name="metrics-that-are-included-in-the-power-bi-content"></a><span data-ttu-id="d3ed5-119">A Power BI-tartalomhoz tartozó metrikák</span><span class="sxs-lookup"><span data-stu-id="d3ed5-119">Metrics that are included in the Power BI content</span></span>
<span data-ttu-id="d3ed5-120">A **Beszerzési kiadások elemzése** Power BI-tartalom tartalmaz egy jelentést, amely metrikák készletéből áll.</span><span class="sxs-lookup"><span data-stu-id="d3ed5-120">The **Purchase spend analysis** Power BI content includes a report that consists of a set of metrics.</span></span> <span data-ttu-id="d3ed5-121">Ezek a metrikák mozaikok, táblázatok és diagramok formájában jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="d3ed5-121">These metrics are visualized as charts, tiles, and tables.</span></span> <span data-ttu-id="d3ed5-122">Az alábbi táblázat tartalmazza a megjelenítések áttekintését.</span><span class="sxs-lookup"><span data-stu-id="d3ed5-122">The following table provides an overview of the visualizations.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d3ed5-123">Jelentéslap</span><span class="sxs-lookup"><span data-stu-id="d3ed5-123">Report page</span></span></th>
<th><span data-ttu-id="d3ed5-124">Diagramok</span><span class="sxs-lookup"><span data-stu-id="d3ed5-124">Charts</span></span></th>
<th><span data-ttu-id="d3ed5-125">Mozaik</span><span class="sxs-lookup"><span data-stu-id="d3ed5-125">Tiles</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="d3ed5-126">Szállító beszerzés</span><span class="sxs-lookup"><span data-stu-id="d3ed5-126">Purchase by vendor</span></span></td>
<td><ul>
<li><span data-ttu-id="d3ed5-127">10 legmagasabb szállító beszerzés szerint (halmozott sávdiagram)</span><span class="sxs-lookup"><span data-stu-id="d3ed5-127">Top 10 vendors by purchase (stacked bar chart)</span></span></li>
<li><span data-ttu-id="d3ed5-128">Teljes beszerzések szállítói csoport / ország / név szerint (kördiagram)</span><span class="sxs-lookup"><span data-stu-id="d3ed5-128">Total purchase by vendor group / country / name (pie chart)</span></span></li>
<li><span data-ttu-id="d3ed5-129">Beszerzések szállítói csoport / ország / név szerint (oszlopdiagram)</span><span class="sxs-lookup"><span data-stu-id="d3ed5-129">Purchase by vendor group / country / name (column chart)</span></span></li>
<li><span data-ttu-id="d3ed5-130">Átlagos beszerzések szállítói csoport / ország / név szerint (oszlopdiagram)</span><span class="sxs-lookup"><span data-stu-id="d3ed5-130">Average purchase by vendor group / country / name (column chart)</span></span></li>
</ul></td>
<td><ul>
<li><span data-ttu-id="d3ed5-131">Összes beszerzés</span><span class="sxs-lookup"><span data-stu-id="d3ed5-131">Total purchase</span></span></li>
<li><span data-ttu-id="d3ed5-132">Egy éves időszak beszerzési növekedése</span><span class="sxs-lookup"><span data-stu-id="d3ed5-132">YOY purchase growth</span></span></li>
<li><span data-ttu-id="d3ed5-133">Összes szállító száma</span><span class="sxs-lookup"><span data-stu-id="d3ed5-133">Total # vendors</span></span></li>
<li><span data-ttu-id="d3ed5-134">Aktív szállítók száma</span><span class="sxs-lookup"><span data-stu-id="d3ed5-134">Total # of active vendors</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="d3ed5-135">Beszerzés termékenként</span><span class="sxs-lookup"><span data-stu-id="d3ed5-135">Purchase by product</span></span></td>
<td><ul>
<li><span data-ttu-id="d3ed5-136">Beszerzés beszerzési kategória / termék neve szerint (oszlopdiagram)</span><span class="sxs-lookup"><span data-stu-id="d3ed5-136">Purchase by procurement category / product name (column chart)</span></span></li>
<li><span data-ttu-id="d3ed5-137">Összes beszerzés beszerzési kategória / termék neve szerint (kördiagram)</span><span class="sxs-lookup"><span data-stu-id="d3ed5-137">Total purchase by procurement category / product name (pie chart)</span></span></li>
<li><span data-ttu-id="d3ed5-138">10 legmagasabb termék beszerzés szerint (halmozott sávdiagram)</span><span class="sxs-lookup"><span data-stu-id="d3ed5-138">Top 10 products by purchase (stacked bar chart)</span></span></li>
</ul></td>
<td><ul>
<li><span data-ttu-id="d3ed5-139">Termékek összes száma</span><span class="sxs-lookup"><span data-stu-id="d3ed5-139">Total # of products</span></span></li>
<li><span data-ttu-id="d3ed5-140">Összes aktív termék, teljes termékszám százaléka</span><span class="sxs-lookup"><span data-stu-id="d3ed5-140">Total active products percentage of total # of products</span></span></li>
<li><span data-ttu-id="d3ed5-141">A beszerzések 80%-át lefedő termékek száma</span><span class="sxs-lookup"><span data-stu-id="d3ed5-141">Number of products accounting for 80% purchase</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="d3ed5-142">Beszerzés időszak szerint*</span><span class="sxs-lookup"><span data-stu-id="d3ed5-142">Purchase by period*</span></span></td>
<td><ul>
<li><span data-ttu-id="d3ed5-143">Beszerzés hónap / nap szerint (oszlopdiagram)</span><span class="sxs-lookup"><span data-stu-id="d3ed5-143">Purchase by month / day (column chart)</span></span></li>
<li><span data-ttu-id="d3ed5-144">Összesített beszerzés, egy éves időszak eltérése (vízesésdiagram)</span><span class="sxs-lookup"><span data-stu-id="d3ed5-144">Cumulative purchase YOY variance (waterfall chart)</span></span></li>
<li><span data-ttu-id="d3ed5-145">Teljes beszerzés, egy éves időszak növekedése (oszlopdiagram)</span><span class="sxs-lookup"><span data-stu-id="d3ed5-145">Total purchase YOY growth (column chart)</span></span></li>
<li><span data-ttu-id="d3ed5-146">Beszerzési kimutatás (mátrix)</span><span class="sxs-lookup"><span data-stu-id="d3ed5-146">Procurement statement (matrix)</span></span></li>
</ul></td>
<td><ul>
<li><span data-ttu-id="d3ed5-147">Egy éves időszak beszerzési növekedése</span><span class="sxs-lookup"><span data-stu-id="d3ed5-147">YOY purchase growth</span></span></li>
<li><span data-ttu-id="d3ed5-148">Egy éves időszak beszerzési növekedése %</span><span class="sxs-lookup"><span data-stu-id="d3ed5-148">YOY purchase growth %</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="d3ed5-149">Beszerzés a szállító helye szerint</span><span class="sxs-lookup"><span data-stu-id="d3ed5-149">Purchase by vendor location</span></span></td>
<td><ul>
<li><span data-ttu-id="d3ed5-150">Beszerzés település szerint</span><span class="sxs-lookup"><span data-stu-id="d3ed5-150">Purchase by city</span></span></li>
<li><span data-ttu-id="d3ed5-151">Egy éves időszak beszerzési növekedési százaléka</span><span class="sxs-lookup"><span data-stu-id="d3ed5-151">Purchase YOY growth %</span></span></li>
<li><span data-ttu-id="d3ed5-152">Beszerzési ország szerint</span><span class="sxs-lookup"><span data-stu-id="d3ed5-152">Purchase by country</span></span></li>
</ul></td>
<td></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="d3ed5-153">Beszerzési kiadások elemzése idő szerint</span><span class="sxs-lookup"><span data-stu-id="d3ed5-153">Purchase spend analysis by time</span></span></td>
<td><ul>
<li><span data-ttu-id="d3ed5-154">Beszerzési folyó év, hónap / nap szerint (vonaldiagram)</span><span class="sxs-lookup"><span data-stu-id="d3ed5-154">Purchase current year by month / day (line chart)</span></span></li>
<li><span data-ttu-id="d3ed5-155">Beszerzés, jelenlegi és az előző év (vonal- és oszlopdiagram)</span><span class="sxs-lookup"><span data-stu-id="d3ed5-155">Purchase current and last year (line and column chart)</span></span></li>
</ul></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="d3ed5-156">Beszerzési kiadások elemzése szállító szerint</span><span class="sxs-lookup"><span data-stu-id="d3ed5-156">Purchase spend analysis by vendor</span></span></td>
<td><ul>
<li><span data-ttu-id="d3ed5-157">A legjobb szállítói beszerzési %-a a beszerzésekből (tölcsér)</span><span class="sxs-lookup"><span data-stu-id="d3ed5-157">Top 10 vendor purchase % of purchase (funnel)</span></span></li>
<li><span data-ttu-id="d3ed5-158">Top 10 szállító megnövekedett kiadásokkal egy éves időszakban</span><span class="sxs-lookup"><span data-stu-id="d3ed5-158">Top 10 vendors with increased spending YOY</span></span></li>
<li><span data-ttu-id="d3ed5-159">Top 10 szállító csökkent kiadásokkal egy éves időszakban</span><span class="sxs-lookup"><span data-stu-id="d3ed5-159">Top 10 vendors with decreased spending YOY</span></span></li>
</ul></td>
<td></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d3ed5-160">\* Erre az évre és az előző évre eső beszerzés, és növekedés beszerzési kategória szerint</span><span class="sxs-lookup"><span data-stu-id="d3ed5-160">\* Purchase this year and last year, and growth by procurement category</span></span>

## <a name="extending-the-power-bi-content"></a><span data-ttu-id="d3ed5-161">Power BI-tartalom kibővítése</span><span class="sxs-lookup"><span data-stu-id="d3ed5-161">Extending the Power BI content</span></span>
<span data-ttu-id="d3ed5-162">A Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásban található tartalomcsomagok révén nagyszerű elemzési lehetőségeket nyújthat azoknak a személyeknek, akik nem jelentkeztek be a Microsoft Dynamics 365 szolgáltatásba.</span><span class="sxs-lookup"><span data-stu-id="d3ed5-162">By using the content packs that are available in Microsoft Dynamics Lifecycle Services (LCS), you can provide great analytics to people who don't sign in to Microsoft Dynamics 365.</span></span> <span data-ttu-id="d3ed5-163">Ezek a tartalomcsomagok módosíthatók, hogy más jelentéseket vagy megjelenítéseket is tartalmazhassanak, majd a tartalomcsomagok elemzés céljából közzétehetők a Power BI.com-bérlőjénél.</span><span class="sxs-lookup"><span data-stu-id="d3ed5-163">You can modify these content packs so that they include other reports or visuals, and then publish the content packs to your Power BI.com tenant for analysis.</span></span> 

<span data-ttu-id="d3ed5-164">A **Beszerzési kiadások elemzése** Power BI-tartalmat az LCS Megosztott eszközök könyvtárában találja.</span><span class="sxs-lookup"><span data-stu-id="d3ed5-164">You can find the **Purchase spend analysis** Power BI content in the Shared assets library in LCS.</span></span> <span data-ttu-id="d3ed5-165">A tartalom letöltésére és szervezeténél való megvalósítására vonatkozó további információért lásd: [Power BI-tartalom az LCS megoldásban a Microsofttól és a partnerektől](power-bi-content-microsoft-partners.md).</span><span class="sxs-lookup"><span data-stu-id="d3ed5-165">For more information about how to download the content and implement it in your organization, see [Power BI content in LCS from Microsoft and your partners](power-bi-content-microsoft-partners.md).</span></span> <span data-ttu-id="d3ed5-166">Ha meg szeretne tekinteni egy demót, amely bemutatja a Power BI-tartalmak megvalósítását, lásd a [Power BI-tartalom a Microsofttól és az Ön partnereitől a Dynamics Lifecycle Services szolgáltatásban](https://mix.office.com/watch/9puyb1b2xs1w) című részt (Office Mix).</span><span class="sxs-lookup"><span data-stu-id="d3ed5-166">To watch a demo that shows how to implement the Power BI content, see the [Power BI content from Microsoft and your partners in Dynamics Lifecycle Services](https://mix.office.com/watch/9puyb1b2xs1w) Office Mix.</span></span>

<span data-ttu-id="d3ed5-167">Ügyeljen arra, hogy azt a **Beszerzési kiadások elemzése** tartalmat töltse le, amely a Dynamics 365 ön által használt verziójára vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="d3ed5-167">Be sure to download the **Purchase spend analysis** content that applies to the version of Dynamics 365 that you're using.</span></span>

> [!NOTE]
> <span data-ttu-id="d3ed5-168">Amennyiben a Microsoft Dynamics 365 for Finance and Operations Enterprise edition 1611-es verzióját használja, a KB 4011327 a Power BI-tartalom előfeltétele.</span><span class="sxs-lookup"><span data-stu-id="d3ed5-168">If you're using Microsoft Dynamics 365 for Operations version 1611, KB 4011327 is a prerequisite for this Power BI content.</span></span> <span data-ttu-id="d3ed5-169">A Lifecycle Services szolgáltatásba való bejelentkezést követően itt férhet hozzá a tudásbázishoz: https://fix.lcs.dynamics.com/issue/results/?q=kb4011327.</span><span class="sxs-lookup"><span data-stu-id="d3ed5-169">After you sign in to LCS, you can access the KB at https://fix.lcs.dynamics.com/issue/results/?q=kb4011327.</span></span>

## <a name="data-model-and-entities"></a><span data-ttu-id="d3ed5-170">Adatmodell és entitások</span><span class="sxs-lookup"><span data-stu-id="d3ed5-170">Data model and entities</span></span>
<span data-ttu-id="d3ed5-171">A **Beszerzési kiadások elemzése** Power BI-tartalom jelentési oldalainak feltöltésére a következő adatok szolgálnak.</span><span class="sxs-lookup"><span data-stu-id="d3ed5-171">The following data is used to fill the report pages in the **Purchase spend analysis** Power BI content.</span></span> <span data-ttu-id="d3ed5-172">Ezeket az adatokat az Entitástárban lebonyolított összesített mérések jelenítik meg.</span><span class="sxs-lookup"><span data-stu-id="d3ed5-172">This data is represented as aggregate measurements that are staged in the Entity store.</span></span> <span data-ttu-id="d3ed5-173">Az entitástár a Microsoft analitikai célokra optimalizált SQL-szerveradatbázisa.</span><span class="sxs-lookup"><span data-stu-id="d3ed5-173">The Entity store is a Microsoft SQL Server database that is optimized for analytics.</span></span> <span data-ttu-id="d3ed5-174">További tudnivalókért lásd: [Az entitástár és a Power BI integrációjának áttekintése](power-bi-integration-entity-store.md).</span><span class="sxs-lookup"><span data-stu-id="d3ed5-174">For more information, see [Overview of Power BI integration with Entity store](power-bi-integration-entity-store.md).</span></span>

<span data-ttu-id="d3ed5-175">A tartalom összesítő mértékek a következőkben rendelkezésre álló összesítő mértékek részhalmazát alkotják: Purchase Cube in Microsoft Dynamics AX 2012 és Microsoft Dynamics AX 2012 R3.</span><span class="sxs-lookup"><span data-stu-id="d3ed5-175">The aggregate measurements in this content are the subset of aggregate measurements that were available in the Purchase Cube in Microsoft Dynamics AX 2012 and Microsoft Dynamics AX 2012 R3.</span></span> <span data-ttu-id="d3ed5-176">A kocka összesítő mértékeinek előkészítéséhez az entitástárban, a mértékeket központilag telepíthetővé kell tenni.</span><span class="sxs-lookup"><span data-stu-id="d3ed5-176">To stage the cube’s aggregate measurements in the Entity store, you must make them deployable.</span></span> <span data-ttu-id="d3ed5-177">További információért lásd a következő blogbejegyzést az összesítő mértékek előkészítésének eljárásáról az entitástárban: [A Power BI és az entitástár integrálása a Dynamics programban - áttekintés](power-bi-integration-entity-store.md).</span><span class="sxs-lookup"><span data-stu-id="d3ed5-177">For more information, see the procedure for staging aggregate measurements in the Entity store in [Overview of Power BI integration with Entity store](power-bi-integration-entity-store.md).</span></span> <span data-ttu-id="d3ed5-178">A következő kulcs összesítő mértékek közvetlenül a számla sorai entitásból érhetők el, és a tartalom alapjául szolgálnak.</span><span class="sxs-lookup"><span data-stu-id="d3ed5-178">The following key aggregate measurements are available directly from the Invoice lines entity and are used as the basis of the content.</span></span>

| <span data-ttu-id="d3ed5-179">Entitás</span><span class="sxs-lookup"><span data-stu-id="d3ed5-179">Entity</span></span>        | <span data-ttu-id="d3ed5-180">Kulcs összesítő mértékek</span><span class="sxs-lookup"><span data-stu-id="d3ed5-180">Key aggregate measurements</span></span> | <span data-ttu-id="d3ed5-181">Adatforrás</span><span class="sxs-lookup"><span data-stu-id="d3ed5-181">Data source</span></span>                                 | <span data-ttu-id="d3ed5-182">Mező</span><span class="sxs-lookup"><span data-stu-id="d3ed5-182">Field</span></span>              | <span data-ttu-id="d3ed5-183">Leírás</span><span class="sxs-lookup"><span data-stu-id="d3ed5-183">Description</span></span>                            |
|---------------|----------------------------|---------------------------------------------|--------------------|----------------------------------------|
| <span data-ttu-id="d3ed5-184">Számlasorok</span><span class="sxs-lookup"><span data-stu-id="d3ed5-184">Invoice lines</span></span> | <span data-ttu-id="d3ed5-185">Beszerzés</span><span class="sxs-lookup"><span data-stu-id="d3ed5-185">Purchase</span></span>                   | <span data-ttu-id="d3ed5-186">VendInvoiceTrans</span><span class="sxs-lookup"><span data-stu-id="d3ed5-186">VendInvoiceTrans</span></span>                            | <span data-ttu-id="d3ed5-187">SUM(LineAmountMST)</span><span class="sxs-lookup"><span data-stu-id="d3ed5-187">SUM(LineAmountMST)</span></span> | <span data-ttu-id="d3ed5-188">Összeg a könyvelési pénznemben.</span><span class="sxs-lookup"><span data-stu-id="d3ed5-188">The amount in the accounting currency.</span></span> |

<span data-ttu-id="d3ed5-189">Az alábbi táblázat a kulcs mértékeket mutatja, amelyeknek a kiszámítása a tartalomban történik a számla sorai entitásból.</span><span class="sxs-lookup"><span data-stu-id="d3ed5-189">The following table shows the key measurements in the content that are calculated from the Invoice lines entity.</span></span>

| <span data-ttu-id="d3ed5-190">Méret</span><span class="sxs-lookup"><span data-stu-id="d3ed5-190">Measure</span></span>               | <span data-ttu-id="d3ed5-191">Számítás</span><span class="sxs-lookup"><span data-stu-id="d3ed5-191">Calculation</span></span>                                                                                         |
|-----------------------|-----------------------------------------------------------------------------------------------------|
| <span data-ttu-id="d3ed5-192">Aktuális év beszerzései</span><span class="sxs-lookup"><span data-stu-id="d3ed5-192">Purchase current year</span></span> | <span data-ttu-id="d3ed5-193">Aktuális év beszerzései = SUM('Számlasorok'\[Beszerzés\])</span><span class="sxs-lookup"><span data-stu-id="d3ed5-193">Purchase current year = SUM('Invoice lines'\[Purchase\])</span></span>                                            |
| <span data-ttu-id="d3ed5-194">Tavalyi év beszerzései</span><span class="sxs-lookup"><span data-stu-id="d3ed5-194">Purchase last year</span></span>    | <span data-ttu-id="d3ed5-195">Tavalyi év beszerzései = CALCULATE(SUM('Számlasorok'\[Beszerzés\]), SAMEPERIODLASTYEAR(Dátumok\[Dátum\]))</span><span class="sxs-lookup"><span data-stu-id="d3ed5-195">Purchase last year = CALCULATE(SUM('Invoice lines'\[Purchase\]), SAMEPERIODLASTYEAR(Dates\[Date\]))</span></span> |
| <span data-ttu-id="d3ed5-196">Egy éves időszak beszerzési növekedése</span><span class="sxs-lookup"><span data-stu-id="d3ed5-196">YOY purchase growth</span></span>   | <span data-ttu-id="d3ed5-197">Egy éves időszak beszerzési növekedése = \[Aktuális év beszerzései\] – \[Tavalyi év beszerzései\]</span><span class="sxs-lookup"><span data-stu-id="d3ed5-197">YOY purchase growth = \[Purchase current year\] – \[Purchase last year\]</span></span>                            |

<span data-ttu-id="d3ed5-198">A tartalomban a következő fő dimenziók szolgálnak szűrőként az összesítő mértékek szeletelésére, nagyobb részletességet és mélyebb elemzési betekintések elérését téve lehetővé.</span><span class="sxs-lookup"><span data-stu-id="d3ed5-198">The following key dimensions in the content are used as filters to slice the aggregate measurements, so that you can achieve more granularity and gain deeper analytical insights.</span></span>

| <span data-ttu-id="d3ed5-199">Entitás</span><span class="sxs-lookup"><span data-stu-id="d3ed5-199">Entity</span></span>                 | <span data-ttu-id="d3ed5-200">Példák az attribútumok</span><span class="sxs-lookup"><span data-stu-id="d3ed5-200">Examples of attributes</span></span>                                |
|------------------------|-------------------------------------------------------|
| <span data-ttu-id="d3ed5-201">Szállítók</span><span class="sxs-lookup"><span data-stu-id="d3ed5-201">Vendors</span></span>                | <span data-ttu-id="d3ed5-202">Szállítói csoportok, Szállító országok vagy régiók, Szállító neve</span><span class="sxs-lookup"><span data-stu-id="d3ed5-202">Vendor groups, Vendor country or regions, Vendor name</span></span> |
| <span data-ttu-id="d3ed5-203">Termékek</span><span class="sxs-lookup"><span data-stu-id="d3ed5-203">Products</span></span>               | <span data-ttu-id="d3ed5-204">Termékszám, Termék neve, Cikkcsoportok neve</span><span class="sxs-lookup"><span data-stu-id="d3ed5-204">Product number, Product name, Item groups name</span></span>        |
| <span data-ttu-id="d3ed5-205">Beszerzési kategóriák</span><span class="sxs-lookup"><span data-stu-id="d3ed5-205">Procurement categories</span></span> | <span data-ttu-id="d3ed5-206">Beszerzési kategória, Beszerzési kategórianevek</span><span class="sxs-lookup"><span data-stu-id="d3ed5-206">Procurement category, Procurement category names</span></span>      |
| <span data-ttu-id="d3ed5-207">Jogi személyek</span><span class="sxs-lookup"><span data-stu-id="d3ed5-207">Legal entities</span></span>         | <span data-ttu-id="d3ed5-208">Jogi személy neve</span><span class="sxs-lookup"><span data-stu-id="d3ed5-208">Legal entity name</span></span>                                     |
| <span data-ttu-id="d3ed5-209">Dátumok</span><span class="sxs-lookup"><span data-stu-id="d3ed5-209">Dates</span></span>                  | <span data-ttu-id="d3ed5-210">Dátumok, Év eltolása</span><span class="sxs-lookup"><span data-stu-id="d3ed5-210">Dates, Year offset</span></span>                                    |

<span data-ttu-id="d3ed5-211">Alapértelmezés szerint a tartalom a folyó naptári év adatait jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="d3ed5-211">By default, the content shows data for the current calendar year.</span></span> <span data-ttu-id="d3ed5-212">Azonban módosíthatja a dátumszűrőt a jelentésszűrők szakaszban.</span><span class="sxs-lookup"><span data-stu-id="d3ed5-212">However, you can change the date filter in the report filters section.</span></span> <span data-ttu-id="d3ed5-213">A vállalatszűrőt is módosíthatja.</span><span class="sxs-lookup"><span data-stu-id="d3ed5-213">You can also change the company filter.</span></span>

