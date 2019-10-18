---
title: Jelentésdefiníciók a pénzügyi jelentéstervezőben
description: Ez a cikk a jelentésdefiníciókról tartalmaz információt. A jelentésdefiníció egy jelentés-összetevő (vagy építőelem), amely egy sordefiníció, egy oszlopdefiníció és egy opcionális jelentési-fa definíciót használ a jelentés elkészítéséhez. Továbbá a jelentésdefiníció biztosít lehetőségeket és beállításokat, a jelentés testreszabásához.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 59131
ms.assetid: 966a3f1d-c59c-4a84-acd4-5bb7e65144c8
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 07f49e63fc2e0410d2673f3ca9378325e9b4ebf8
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/27/2019
ms.locfileid: "2174144"
---
# <a name="report-definitions-in-financial-report-designer"></a><span data-ttu-id="dec9f-105">Jelentésdefiníciók a pénzügyi jelentéstervezőben</span><span class="sxs-lookup"><span data-stu-id="dec9f-105">Report definitions in financial report designer</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="dec9f-106">Ez a cikk a jelentésdefiníciókról tartalmaz információt.</span><span class="sxs-lookup"><span data-stu-id="dec9f-106">This article provides information about report definitions.</span></span> <span data-ttu-id="dec9f-107">A jelentésdefiníció egy jelentés-összetevő (vagy építőelem), amely egy sordefiníció, egy oszlopdefiníció és egy opcionális jelentési-fa definíciót használ a jelentés elkészítéséhez.</span><span class="sxs-lookup"><span data-stu-id="dec9f-107">A report definition is a report component (or building block) that uses a row definition, a column definition, and an optional reporting tree definition to create a report.</span></span> <span data-ttu-id="dec9f-108">Továbbá a jelentésdefiníció biztosít lehetőségeket és beállításokat, a jelentés testreszabásához.</span><span class="sxs-lookup"><span data-stu-id="dec9f-108">A report definition also provides options and settings that for customizing a report.</span></span> 

<span data-ttu-id="dec9f-109">A jelentésdefiníció egy jelentés-összetevő (vagy építőelem), amely egy sordefiníció, egy oszlopdefiníció és egy opcionális jelentési-fa definíciót használ a jelentés elkészítéséhez.</span><span class="sxs-lookup"><span data-stu-id="dec9f-109">A report definition is a report component (or building block) that uses a row definition, a column definition, and an optional reporting tree definition to create a report.</span></span> <span data-ttu-id="dec9f-110">A jelentésdefiníció emellett a jelentés testre szabását lehetővé tevő lehetőségeket és beállításokat is tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="dec9f-110">A report definition also provides options and settings that you can use to customize a report.</span></span> <span data-ttu-id="dec9f-111">A sordefiníciók és oszlopdefiníciók meghatározása után kombinálni kell azokat egy jelentésdefinícióban.</span><span class="sxs-lookup"><span data-stu-id="dec9f-111">After you define row definitions and column definitions, you must combine them in a report definition.</span></span> <span data-ttu-id="dec9f-112">Ezen a ponton határozhatja meg a definíciók egyéb aspektusait, például a részletezési szintet és a jelentés dátumát.</span><span class="sxs-lookup"><span data-stu-id="dec9f-112">At this point, you also define other aspects of the definitions, such as the detail level and report date.</span></span> <span data-ttu-id="dec9f-113">Ezután mentheti, majd generálhat jelentéseket.</span><span class="sxs-lookup"><span data-stu-id="dec9f-113">You can then save and generate a report.</span></span> <span data-ttu-id="dec9f-114">A pénzügyi jelentéskészítés a következő részletességi szinteket nyújtja:</span><span class="sxs-lookup"><span data-stu-id="dec9f-114">Financial reporting offers the following levels of detail:</span></span>

- <span data-ttu-id="dec9f-115">Pénzügyi</span><span class="sxs-lookup"><span data-stu-id="dec9f-115">Financial</span></span>
- <span data-ttu-id="dec9f-116">Pénzügy és számla</span><span class="sxs-lookup"><span data-stu-id="dec9f-116">Financial and Account</span></span>
- <span data-ttu-id="dec9f-117">Pénzügy, Számla és Tranzakció</span><span class="sxs-lookup"><span data-stu-id="dec9f-117">Financial, Account, and Transaction</span></span>

<span data-ttu-id="dec9f-118">Előfordulhat azonban – attól függően, hogyan tárolja a Microsoft Dynamics ERP rendszer az adatokat –, hogy a tranzakciók részletes adatai nem érhetők el a jelentésekben.</span><span class="sxs-lookup"><span data-stu-id="dec9f-118">However, depending on how data is stored in the Microsoft Dynamics ERP system, transaction details might not be available in reports.</span></span>

## <a name="create-a-report-definition"></a><span data-ttu-id="dec9f-119">Jelentésmeghatározás létrehozása</span><span class="sxs-lookup"><span data-stu-id="dec9f-119">Create a report definition</span></span>
1. <span data-ttu-id="dec9f-120">A jelentéstervezőben a **Fájl** menüben kattintson az **Új** lehetőségre, majd válassza a **Jelentésdefiníció** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="dec9f-120">In Report Designer, on the **File** menu, click **New**, and then select **Report Definition**.</span></span>
2. <span data-ttu-id="dec9f-121">A szükséges információkat a **Jelentés**, **Kimenet és elosztás**, **Fejlécek és láblécek**, valamint a **Beállítások** lapokon határozhatja meg.</span><span class="sxs-lookup"><span data-stu-id="dec9f-121">Specify the appropriate information on the **Report**, **Output and Distribution**, **Headers and Footers**, and **Settings** tabs.</span></span>

## <a name="contents-of-a-report-definition"></a><span data-ttu-id="dec9f-122">Jelentésdefiníció tartalma</span><span class="sxs-lookup"><span data-stu-id="dec9f-122">Contents of a report definition</span></span>
<span data-ttu-id="dec9f-123">A következő táblázat bemutatja a jelentésdefinícióban lévő lapokat és az információk használatának módját.</span><span class="sxs-lookup"><span data-stu-id="dec9f-123">The following table describes the tabs in a report definition and how the information is used.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="dec9f-124">Lap</span><span class="sxs-lookup"><span data-stu-id="dec9f-124">Tab</span></span></th>
<th><span data-ttu-id="dec9f-125">Leírás</span><span class="sxs-lookup"><span data-stu-id="dec9f-125">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="dec9f-126">Jelentés</span><span class="sxs-lookup"><span data-stu-id="dec9f-126">Report</span></span></td>
<td><span data-ttu-id="dec9f-127">Jelentése létrehozás, jelentés beállítása vagy meglévő jelentés módosítása.</span><span class="sxs-lookup"><span data-stu-id="dec9f-127">Create a report, configure a report, or modify an existing report.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dec9f-128">Kimenet és felosztás</span><span class="sxs-lookup"><span data-stu-id="dec9f-128">Output and Distribution</span></span></td>
<td><span data-ttu-id="dec9f-129">A kimenet típusának és a jelentés céljának módosítása.</span><span class="sxs-lookup"><span data-stu-id="dec9f-129">Change the output type and destination of the report.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dec9f-130">Fejlécek és láblécek</span><span class="sxs-lookup"><span data-stu-id="dec9f-130">Headers and Footers</span></span></td>
<td><span data-ttu-id="dec9f-131">A jelentés fejléceinek és lábléceinek meghatározása és formázása.</span><span class="sxs-lookup"><span data-stu-id="dec9f-131">Define and format the headers and footers for the report.</span></span> <span data-ttu-id="dec9f-132">Például hozzáadhat szöveget vagy képeket a fejléchez vagy a lábléchez.</span><span class="sxs-lookup"><span data-stu-id="dec9f-132">For example, you can add text or images to the header or footer.</span></span> <span data-ttu-id="dec9f-133">A pénzügyi jelentéskészítés a .bmp, .jpg, és .png formátumokat támogatja képek esetén.</span><span class="sxs-lookup"><span data-stu-id="dec9f-133">Financial reporting supports .bmp, .jpg, and .png files for images.</span></span> <span data-ttu-id="dec9f-134">Az autotext kódok hozzáadásával egyéb információkat is beszúrhat, például a cég nevét, a jelentés nevét vagy az oldalszámot.</span><span class="sxs-lookup"><span data-stu-id="dec9f-134">You can also add autotext codes to insert other information, such as a company name, report name, or page number.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dec9f-135">Beállítások</span><span class="sxs-lookup"><span data-stu-id="dec9f-135">Settings</span></span></td>
<td><span data-ttu-id="dec9f-136">Adja meg a jelentésdefiníció beállításait, például a következőket:</span><span class="sxs-lookup"><span data-stu-id="dec9f-136">Specify report definition settings, such as the following settings:</span></span>
<ul>
<li><span data-ttu-id="dec9f-137">Formázás és kerekített összegek</span><span class="sxs-lookup"><span data-stu-id="dec9f-137">Formatting and rounding amounts</span></span></li>
<li><span data-ttu-id="dec9f-138">Részletes jelentés formázása</span><span class="sxs-lookup"><span data-stu-id="dec9f-138">Format detail reports</span></span></li>
<li><span data-ttu-id="dec9f-139">Jelentéskészítési fa formátum</span><span class="sxs-lookup"><span data-stu-id="dec9f-139">Format reporting trees</span></span></li>
<li><span data-ttu-id="dec9f-140">Kivétel jelentés készítése</span><span class="sxs-lookup"><span data-stu-id="dec9f-140">Generate an exception report</span></span></li>
<li><span data-ttu-id="dec9f-141">Pénznem átváltásának meghatározása</span><span class="sxs-lookup"><span data-stu-id="dec9f-141">Specify currency conversion</span></span></li>
<li><span data-ttu-id="dec9f-142">Részösszeg és szűrőszámla részletei</span><span class="sxs-lookup"><span data-stu-id="dec9f-142">Subtotal and filter account details</span></span></li>
</ul>
</td>
</tr>
</tbody>
</table>

## <a name="additional-resources"></a><span data-ttu-id="dec9f-143">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="dec9f-143">Additional resources</span></span>

[<span data-ttu-id="dec9f-144">Pénzügyi jelentéskészítés</span><span class="sxs-lookup"><span data-stu-id="dec9f-144">Financial reporting</span></span>](financial-reporting-intro.md)
