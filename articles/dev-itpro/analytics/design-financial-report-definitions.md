---
title: "Jelentésdefiníciók a pénzügyi jelentéstervezőben"
description: "Ez a cikk a jelentésdefiníciókról tartalmaz információt. A jelentésdefiníció egy jelentés-összetevő (vagy építőelem), amely egy sordefiníció, egy oszlopdefiníció és egy opcionális jelentési-fa definíciót használ a jelentés elkészítéséhez. Továbbá a jelentésdefiníció biztosít lehetőségeket és beállításokat, a jelentés testreszabásához."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations, Core
ms.custom: 59131
ms.assetid: 966a3f1d-c59c-4a84-acd4-5bb7e65144c8
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 58030df8db467f754ec93ecc3f41585b20f03893
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="report-definitions-in-financial-report-designer"></a><span data-ttu-id="69733-105">Jelentésdefiníciók a pénzügyi jelentéstervezőben</span><span class="sxs-lookup"><span data-stu-id="69733-105">Report definitions in financial report designer</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="69733-106">Ez a cikk a jelentésdefiníciókról tartalmaz információt.</span><span class="sxs-lookup"><span data-stu-id="69733-106">This article provides information about report definitions.</span></span> <span data-ttu-id="69733-107">A jelentésdefiníció egy jelentés-összetevő (vagy építőelem), amely egy sordefiníció, egy oszlopdefiníció és egy opcionális jelentési-fa definíciót használ a jelentés elkészítéséhez.</span><span class="sxs-lookup"><span data-stu-id="69733-107">A report definition is a report component (or building block) that uses a row definition, a column definition, and an optional reporting tree definition to create a report.</span></span> <span data-ttu-id="69733-108">Továbbá a jelentésdefiníció biztosít lehetőségeket és beállításokat, a jelentés testreszabásához.</span><span class="sxs-lookup"><span data-stu-id="69733-108">A report definition also provides options and settings that for customizing a report.</span></span> 

<span data-ttu-id="69733-109">A jelentésdefiníció egy jelentés-összetevő (vagy építőelem), amely egy sordefiníció, egy oszlopdefiníció és egy opcionális jelentési-fa definíciót használ a jelentés elkészítéséhez.</span><span class="sxs-lookup"><span data-stu-id="69733-109">A report definition is a report component (or building block) that uses a row definition, a column definition, and an optional reporting tree definition to create a report.</span></span> <span data-ttu-id="69733-110">A jelentésdefiníció emellett a jelentés testre szabását lehetővé tevő lehetőségeket és beállításokat is tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="69733-110">A report definition also provides options and settings that you can use to customize a report.</span></span> <span data-ttu-id="69733-111">A sordefiníciók és oszlopdefiníciók meghatározása után kombinálni kell azokat egy jelentésdefinícióban.</span><span class="sxs-lookup"><span data-stu-id="69733-111">After you define row definitions and column definitions, you must combine them in a report definition.</span></span> <span data-ttu-id="69733-112">Ezen a ponton határozhatja meg a definíciók egyéb aspektusait, például a részletezési szintet és a jelentés dátumát.</span><span class="sxs-lookup"><span data-stu-id="69733-112">At this point, you also define other aspects of the definitions, such as the detail level and report date.</span></span> <span data-ttu-id="69733-113">Ezután mentheti, majd generálhat jelentéseket.</span><span class="sxs-lookup"><span data-stu-id="69733-113">You can then save and generate a report.</span></span> <span data-ttu-id="69733-114">A pénzügyi jelentéskészítés a következő részletességi szinteket nyújtja:</span><span class="sxs-lookup"><span data-stu-id="69733-114">Financial reporting offers the following levels of detail:</span></span>

-   <span data-ttu-id="69733-115">Pénzügyi</span><span class="sxs-lookup"><span data-stu-id="69733-115">Financial</span></span>
-   <span data-ttu-id="69733-116">Pénzügy és számla</span><span class="sxs-lookup"><span data-stu-id="69733-116">Financial and Account</span></span>
-   <span data-ttu-id="69733-117">Pénzügy, Számla és Tranzakció</span><span class="sxs-lookup"><span data-stu-id="69733-117">Financial, Account, and Transaction</span></span>

<span data-ttu-id="69733-118">Ugyanakkor attól függően, hogy hogyan tárolja a Microsoft Dynamics ERP rendszer az adatokat, előfordulhat, hogy a tranzakció részletei nem elérhetők a jelentésben.</span><span class="sxs-lookup"><span data-stu-id="69733-118">However, depending on how data is stored in the Microsoft Dynamics ERP system, transaction details might not be available in reports.</span></span>

## <a name="create-a-report-definition"></a><span data-ttu-id="69733-119">Jelentésmeghatározás létrehozása</span><span class="sxs-lookup"><span data-stu-id="69733-119">Create a report definition</span></span>
1.  <span data-ttu-id="69733-120">A jelentéstervezőben a **Fájl** menüben kattintson az **Új** lehetőségre, majd válassza a **Jelentésdefiníció** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="69733-120">In Report Designer, on the **File** menu, click **New**, and then select **Report Definition**.</span></span>
2.  <span data-ttu-id="69733-121">A szükséges információkat a **Jelentés**, **Kimenet és elosztás**, **Fejlécek és láblécek**, valamint a **Beállítások** lapokon határozhatja meg.</span><span class="sxs-lookup"><span data-stu-id="69733-121">Specify the appropriate information on the **Report**, **Output and Distribution**, **Headers and Footers**, and **Settings** tabs.</span></span>

## <a name="contents-of-a-report-definition"></a><span data-ttu-id="69733-122">Jelentésdefiníció tartalma</span><span class="sxs-lookup"><span data-stu-id="69733-122">Contents of a report definition</span></span>
<span data-ttu-id="69733-123">A következő táblázat bemutatja a jelentésdefinícióban lévő lapokat és az információk használatának módját.</span><span class="sxs-lookup"><span data-stu-id="69733-123">The following table describes the tabs in a report definition and how the information is used.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="69733-124">Lap</span><span class="sxs-lookup"><span data-stu-id="69733-124">Tab</span></span></th>
<th><span data-ttu-id="69733-125">Leírás</span><span class="sxs-lookup"><span data-stu-id="69733-125">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="69733-126">Jelentés</span><span class="sxs-lookup"><span data-stu-id="69733-126">Report</span></span></td>
<td><span data-ttu-id="69733-127">Jelentése létrehozás, jelentés beállítása vagy meglévő jelentés módosítása.</span><span class="sxs-lookup"><span data-stu-id="69733-127">Create a report, configure a report, or modify an existing report.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="69733-128">Kimenet és felosztás</span><span class="sxs-lookup"><span data-stu-id="69733-128">Output and Distribution</span></span></td>
<td><span data-ttu-id="69733-129">A kimenet típusának és a jelentés céljának módosítása.</span><span class="sxs-lookup"><span data-stu-id="69733-129">Change the output type and destination of the report.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="69733-130">Fejlécek és láblécek</span><span class="sxs-lookup"><span data-stu-id="69733-130">Headers and Footers</span></span></td>
<td><span data-ttu-id="69733-131">A jelentés fejléceinek és lábléceinek meghatározása és formázása.</span><span class="sxs-lookup"><span data-stu-id="69733-131">Define and format the headers and footers for the report.</span></span> <span data-ttu-id="69733-132">Például hozzáadhat szöveget vagy képeket a fejléchez vagy a lábléchez.</span><span class="sxs-lookup"><span data-stu-id="69733-132">For example, you can add text or images to the header or footer.</span></span> <span data-ttu-id="69733-133">A pénzügyi jelentéskészítés a .bmp, .jpg, és .png formátumokat támogatja képek esetén.</span><span class="sxs-lookup"><span data-stu-id="69733-133">Financial reporting supports .bmp, .jpg, and .png files for images.</span></span> <span data-ttu-id="69733-134">Az autotext kódok hozzáadásával egyéb információkat is beszúrhat, például a cég nevét, a jelentés nevét vagy az oldalszámot.</span><span class="sxs-lookup"><span data-stu-id="69733-134">You can also add autotext codes to insert other information, such as a company name, report name, or page number.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="69733-135">Beállítások</span><span class="sxs-lookup"><span data-stu-id="69733-135">Settings</span></span></td>
<td><span data-ttu-id="69733-136">Adja meg a jelentésdefiníció beállításait, például a következőket:</span><span class="sxs-lookup"><span data-stu-id="69733-136">Specify report definition settings, such as the following settings:</span></span>
<ul>
<li><span data-ttu-id="69733-137">Formázás és kerekített összegek</span><span class="sxs-lookup"><span data-stu-id="69733-137">Formatting and rounding amounts</span></span></li>
<li><span data-ttu-id="69733-138">Részletes jelentés formázása</span><span class="sxs-lookup"><span data-stu-id="69733-138">Format detail reports</span></span></li>
<li><span data-ttu-id="69733-139">Jelentéskészítési fa formátum</span><span class="sxs-lookup"><span data-stu-id="69733-139">Format reporting trees</span></span></li>
<li><span data-ttu-id="69733-140">Kivétel jelentés készítése</span><span class="sxs-lookup"><span data-stu-id="69733-140">Generate an exception report</span></span></li>
<li><span data-ttu-id="69733-141">Pénznem átváltásának meghatározása</span><span class="sxs-lookup"><span data-stu-id="69733-141">Specify currency conversion</span></span></li>
<li><span data-ttu-id="69733-142">Részösszeg és szűrőszámla részletei</span><span class="sxs-lookup"><span data-stu-id="69733-142">Subtotal and filter account details</span></span></li>
</ul></td>
</tr>
</tbody>
</table>



<a name="see-also"></a><span data-ttu-id="69733-143">Lásd még</span><span class="sxs-lookup"><span data-stu-id="69733-143">See also</span></span>
--------

[<span data-ttu-id="69733-144">Pénzügyi jelentéskészítés</span><span class="sxs-lookup"><span data-stu-id="69733-144">Financial reporting</span></span>](financial-reporting-intro.md)




