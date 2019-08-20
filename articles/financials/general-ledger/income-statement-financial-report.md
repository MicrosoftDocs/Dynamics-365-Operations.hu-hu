---
title: Bevételkimutatás pénzügyi jelentés
description: Ez a cikk a bevételkimutatások alapvető jelentését írja le. Emellett a jelentéshez tartozó építőelemeket is leírja.
author: jcart1106
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 12294
ms.assetid: 30820be0-d943-4f8b-8c25-6414ec393b3d
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b7c5d27d43b287aef87f5ead7f469d5465dd2dcb
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/01/2019
ms.locfileid: "1839087"
---
# <a name="income-statement-financial-report"></a><span data-ttu-id="7ab03-104">Bevételkimutatás pénzügyi jelentés</span><span class="sxs-lookup"><span data-stu-id="7ab03-104">Income statement financial report</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7ab03-105">Ez a cikk a bevételkimutatások alapvető jelentését írja le.</span><span class="sxs-lookup"><span data-stu-id="7ab03-105">This article describes the default report for income statements.</span></span> <span data-ttu-id="7ab03-106">Emellett a jelentéshez tartozó építőelemeket is leírja.</span><span class="sxs-lookup"><span data-stu-id="7ab03-106">It also describes the building blocks that are associated with this report.</span></span> 

<a name="default-income-statement-report"></a><span data-ttu-id="7ab03-107">Alapértelmezett bevételkimutatás jelentés</span><span class="sxs-lookup"><span data-stu-id="7ab03-107">Default income statement report</span></span>
-------------------------------

| <span data-ttu-id="7ab03-108">Alapértelmezett jelentés</span><span class="sxs-lookup"><span data-stu-id="7ab03-108">Default report</span></span>             | <span data-ttu-id="7ab03-109">Mire szolgál?</span><span class="sxs-lookup"><span data-stu-id="7ab03-109">What it does</span></span>                                                                                              |
|----------------------------|-----------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="7ab03-110">Bevétel-kimutatás – Alapértelmezett</span><span class="sxs-lookup"><span data-stu-id="7ab03-110">Income Statement – Default</span></span> | <span data-ttu-id="7ab03-111">Megmutatja a szervezet nyereségességét az aktuális időszakra és a folyó év mai napjáig.</span><span class="sxs-lookup"><span data-stu-id="7ab03-111">Provides a view of the organization’s profitability for the current period and also for the year to date.</span></span> |

## <a name="building-blocks"></a><span data-ttu-id="7ab03-112">Építőelemek</span><span class="sxs-lookup"><span data-stu-id="7ab03-112">Building blocks</span></span>
<span data-ttu-id="7ab03-113">Az eredménykimutatás pénzügyi jelentések a következő építőelemekből állnak.</span><span class="sxs-lookup"><span data-stu-id="7ab03-113">The income statement financial report uses the following building blocks.</span></span>

| <span data-ttu-id="7ab03-114">Alapértelmezett jelentés</span><span class="sxs-lookup"><span data-stu-id="7ab03-114">Default report</span></span>             | <span data-ttu-id="7ab03-115">Sor definíciója</span><span class="sxs-lookup"><span data-stu-id="7ab03-115">Row definition</span></span>                     | <span data-ttu-id="7ab03-116">Oszlopdefiníció</span><span class="sxs-lookup"><span data-stu-id="7ab03-116">Column definition</span></span>          |
|----------------------------|------------------------------------|----------------------------|
| <span data-ttu-id="7ab03-117">Bevételkimutatás – Alapértelmezett</span><span class="sxs-lookup"><span data-stu-id="7ab03-117">Income Statement - Default</span></span> | <span data-ttu-id="7ab03-118">Összesített bevételkimutatás – Alapértelmezett</span><span class="sxs-lookup"><span data-stu-id="7ab03-118">Summary Income Statement - Default</span></span> | <span data-ttu-id="7ab03-119">Időszakos és Idei – Alapértelmezett</span><span class="sxs-lookup"><span data-stu-id="7ab03-119">Periodic and YTD - Default</span></span> |

### <a name="row-definition"></a><span data-ttu-id="7ab03-120">Sor definíciója</span><span class="sxs-lookup"><span data-stu-id="7ab03-120">Row definition</span></span>

<span data-ttu-id="7ab03-121">A sordefiníció, Összesítő Eredménykimutatás – Alapértelmezett, a hagyományos eredménykimutatás minden részére tartalmaz egy szakaszt.</span><span class="sxs-lookup"><span data-stu-id="7ab03-121">The row definition, Summary Income Statement – Default, contains a section for each part of a traditional income statement.</span></span> <span data-ttu-id="7ab03-122">A Főszámla-kategória dimenzió a sordefiníció létrehozásához használatos.</span><span class="sxs-lookup"><span data-stu-id="7ab03-122">The Main Account Category dimension is used to build this row definition.</span></span> <span data-ttu-id="7ab03-123">Ezért bárki létrehozhat jelentést anélkül, hogy módosításokat végezne.</span><span class="sxs-lookup"><span data-stu-id="7ab03-123">Therefore, anyone can generate the report without having to make any modifications.</span></span>

### <a name="column-definition"></a><span data-ttu-id="7ab03-124">Oszlopdefiníció</span><span class="sxs-lookup"><span data-stu-id="7ab03-124">Column Definition</span></span>

<span data-ttu-id="7ab03-125">Az oszlopdefiníciók tartalmaznak különböző típusú oszlopokot, a különböző szintű részletességre és pénzügyi adatokra.</span><span class="sxs-lookup"><span data-stu-id="7ab03-125">The column definitions contain different types of columns to provide different levels of detail and financial data.</span></span>

-   <span data-ttu-id="7ab03-126">**Szakaszos és Idei – Alapértelmezett oszloptípusok:**</span><span class="sxs-lookup"><span data-stu-id="7ab03-126">**Periodic and YTD – Default column types:**</span></span>
    -   <span data-ttu-id="7ab03-127">**DESC** – A leírás a sordefinícióból</span><span class="sxs-lookup"><span data-stu-id="7ab03-127">**DESC** – The description from the row definition</span></span>
    -   <span data-ttu-id="7ab03-128">**FD** – Az aktuális időszak pénzügyi adatai</span><span class="sxs-lookup"><span data-stu-id="7ab03-128">**FD** – Financial data for the current period</span></span>
    -   <span data-ttu-id="7ab03-129">**FD** – Pénzügyi év adatai, a mai napig.</span><span class="sxs-lookup"><span data-stu-id="7ab03-129">**FD** – Financial data for the year to date</span></span>



<a name="additional-resources"></a><span data-ttu-id="7ab03-130">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="7ab03-130">Additional resources</span></span>
--------

[<span data-ttu-id="7ab03-131">Pénzügyi jelentéskészítés</span><span class="sxs-lookup"><span data-stu-id="7ab03-131">Financial reporting</span></span>](financial-reporting-getting-started.md)

[<span data-ttu-id="7ab03-132">Pénzügyi jelentések megtekintése</span><span class="sxs-lookup"><span data-stu-id="7ab03-132">View financial reports</span></span>](view-financial-reports.md)

[<span data-ttu-id="7ab03-133">Dynamics Pénzügyi jelentések blog</span><span class="sxs-lookup"><span data-stu-id="7ab03-133">Dynamics Financial Reporting Blog</span></span>](https://blogs.msdn.com/b/dynamics_financial_reporting/)



