---
title: "Bevételkimutatás pénzügyi jelentés"
description: "Ez a cikk a bevételkimutatások alapvető jelentését írja le. Emellett a jelentéshez tartozó építőelemeket is leírja."
author: jcart1106
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 12294
ms.assetid: 30820be0-d943-4f8b-8c25-6414ec393b3d
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 0017d13b7f7594462dfff4ef896f4139607d4bc5
ms.contentlocale: hu-hu
ms.lasthandoff: 08/29/2017

---

# <a name="income-statement-financial-report"></a><span data-ttu-id="62308-104">Bevételkimutatás pénzügyi jelentés</span><span class="sxs-lookup"><span data-stu-id="62308-104">Income statement financial report</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="62308-105">Ez a cikk a bevételkimutatások alapvető jelentését írja le.</span><span class="sxs-lookup"><span data-stu-id="62308-105">This article describes the default report for income statements.</span></span> <span data-ttu-id="62308-106">Emellett a jelentéshez tartozó építőelemeket is leírja.</span><span class="sxs-lookup"><span data-stu-id="62308-106">It also describes the building blocks that are associated with this report.</span></span> 

<a name="default-income-statement-report"></a><span data-ttu-id="62308-107">Alapértelmezett bevételkimutatás jelentés</span><span class="sxs-lookup"><span data-stu-id="62308-107">Default income statement report</span></span>
-------------------------------

| <span data-ttu-id="62308-108">Alapértelmezett jelentés</span><span class="sxs-lookup"><span data-stu-id="62308-108">Default report</span></span>             | <span data-ttu-id="62308-109">Mire szolgál?</span><span class="sxs-lookup"><span data-stu-id="62308-109">What it does</span></span>                                                                                              |
|----------------------------|-----------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="62308-110">Bevétel-kimutatás – Alapértelmezett</span><span class="sxs-lookup"><span data-stu-id="62308-110">Income Statement – Default</span></span> | <span data-ttu-id="62308-111">Megmutatja a szervezet nyereségességét az aktuális időszakra és a folyó év mai napjáig.</span><span class="sxs-lookup"><span data-stu-id="62308-111">Provides a view of the organization’s profitability for the current period and also for the year to date.</span></span> |

## <a name="building-blocks"></a><span data-ttu-id="62308-112">Építőelemek</span><span class="sxs-lookup"><span data-stu-id="62308-112">Building blocks</span></span>
<span data-ttu-id="62308-113">Az eredménykimutatás pénzügyi jelentések a következő építőelemekből állnak.</span><span class="sxs-lookup"><span data-stu-id="62308-113">The income statement financial report uses the following building blocks.</span></span>

| <span data-ttu-id="62308-114">Alapértelmezett jelentés</span><span class="sxs-lookup"><span data-stu-id="62308-114">Default report</span></span>             | <span data-ttu-id="62308-115">Sor definíciója</span><span class="sxs-lookup"><span data-stu-id="62308-115">Row definition</span></span>                     | <span data-ttu-id="62308-116">Oszlopdefiníció</span><span class="sxs-lookup"><span data-stu-id="62308-116">Column definition</span></span>          |
|----------------------------|------------------------------------|----------------------------|
| <span data-ttu-id="62308-117">Bevételkimutatás – Alapértelmezett</span><span class="sxs-lookup"><span data-stu-id="62308-117">Income Statement - Default</span></span> | <span data-ttu-id="62308-118">Összesített bevételkimutatás – Alapértelmezett</span><span class="sxs-lookup"><span data-stu-id="62308-118">Summary Income Statement - Default</span></span> | <span data-ttu-id="62308-119">Időszakos és Idei – Alapértelmezett</span><span class="sxs-lookup"><span data-stu-id="62308-119">Periodic and YTD - Default</span></span> |

### <a name="row-definition"></a><span data-ttu-id="62308-120">Sor definíciója</span><span class="sxs-lookup"><span data-stu-id="62308-120">Row definition</span></span>

<span data-ttu-id="62308-121">A sordefiníció, Összesítő Eredménykimutatás – Alapértelmezett, a hagyományos eredménykimutatás minden részére tartalmaz egy szakaszt.</span><span class="sxs-lookup"><span data-stu-id="62308-121">The row definition, Summary Income Statement – Default, contains a section for each part of a traditional income statement.</span></span> <span data-ttu-id="62308-122">A Főszámla-kategória dimenzió a sordefiníció létrehozásához használatos.</span><span class="sxs-lookup"><span data-stu-id="62308-122">The Main Account Category dimension is used to build this row definition.</span></span> <span data-ttu-id="62308-123">Ezért bárki létrehozhat jelentést anélkül, hogy módosításokat végezne.</span><span class="sxs-lookup"><span data-stu-id="62308-123">Therefore, anyone can generate the report without having to make any modifications.</span></span>

### <a name="column-definition"></a><span data-ttu-id="62308-124">Oszlopdefiníció</span><span class="sxs-lookup"><span data-stu-id="62308-124">Column Definition</span></span>

<span data-ttu-id="62308-125">Az oszlopdefiníciók tartalmaznak különböző típusú oszlopokot, a különböző szintű részletességre és pénzügyi adatokra.</span><span class="sxs-lookup"><span data-stu-id="62308-125">The column definitions contain different types of columns to provide different levels of detail and financial data.</span></span>

-   <span data-ttu-id="62308-126">**Szakaszos és Idei – Alapértelmezett oszloptípusok:**</span><span class="sxs-lookup"><span data-stu-id="62308-126">**Periodic and YTD – Default column types:**</span></span>
    -   <span data-ttu-id="62308-127">**DESC** – A leírás a sordefinícióból</span><span class="sxs-lookup"><span data-stu-id="62308-127">**DESC** – The description from the row definition</span></span>
    -   <span data-ttu-id="62308-128">**FD** – Az aktuális időszak pénzügyi adatai</span><span class="sxs-lookup"><span data-stu-id="62308-128">**FD** – Financial data for the current period</span></span>
    -   <span data-ttu-id="62308-129">**FD** – Pénzügyi év adatai, a mai napig.</span><span class="sxs-lookup"><span data-stu-id="62308-129">**FD** – Financial data for the year to date</span></span>

 

<a name="see-also"></a><span data-ttu-id="62308-130">Lásd még</span><span class="sxs-lookup"><span data-stu-id="62308-130">See also</span></span>
--------

[<span data-ttu-id="62308-131">Pénzügyi jelentéskészítés</span><span class="sxs-lookup"><span data-stu-id="62308-131">Financial reporting</span></span>](financial-reporting-getting-started.md)

[<span data-ttu-id="62308-132">Pénzügyi jelentések megtekintése</span><span class="sxs-lookup"><span data-stu-id="62308-132">View financial reports</span></span>](view-financial-reports.md)

[<span data-ttu-id="62308-133">Dynamics Pénzügyi jelentések blog</span><span class="sxs-lookup"><span data-stu-id="62308-133">Dynamics Financial Reporting Blog</span></span>](http://blogs.msdn.com/b/dynamics_financial_reporting/)




