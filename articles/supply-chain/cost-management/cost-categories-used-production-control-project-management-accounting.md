---
title: A gyártásvezérlésben és a projekt vezetés könyvelésében alkalmazott költségkategóriák
description: A termelési munkák bizonyos típusai vonatkozhatnak a projektek időbecslésére és jelentésekre. Ez a cikk tájékoztatást nyújt azokról a költségkategóriákról, amelyeket meg kell határozni a termelési munka ezen típusaihoz a termelés és a projekt céljai számára.
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjCategory
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 78253
ms.assetid: cfdd58a0-8afa-4a6f-a208-a76e2c162429
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cab4629740e92f9075b7afc7a5d228b2e01c4664
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1557871"
---
# <a name="cost-categories-used-in-production-control-and-project-management-accounting"></a><span data-ttu-id="3d186-104">A gyártásvezérlésben és a projekt vezetés könyvelésében alkalmazott költségkategóriák</span><span class="sxs-lookup"><span data-stu-id="3d186-104">Cost categories used in Production control and Project management accounting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3d186-105">A termelési munkák bizonyos típusai vonatkozhatnak a projektek időbecslésére és jelentésekre.</span><span class="sxs-lookup"><span data-stu-id="3d186-105">Some types of production work can apply to project time estimates and reporting.</span></span> <span data-ttu-id="3d186-106">Ez a cikk tájékoztatást nyújt azokról a költségkategóriákról, amelyeket meg kell határozni a termelési munka ezen típusaihoz a termelés és a projekt céljai számára.</span><span class="sxs-lookup"><span data-stu-id="3d186-106">This article provides information about the cost categories that you must define for these types of production work for production and project purposes.</span></span>

<span data-ttu-id="3d186-107">A termelési munkák bizonyos típusai vonatkozhatnak a projektek időbecslésére és jelentésekre.</span><span class="sxs-lookup"><span data-stu-id="3d186-107">Some types of production work can apply to project time estimates and reporting.</span></span> <span data-ttu-id="3d186-108">Ebben az esetben a költségkategóriára termelési és projektcélokból van szükség.</span><span class="sxs-lookup"><span data-stu-id="3d186-108">In this case, a cost category is required for production and project purposes.</span></span> <span data-ttu-id="3d186-109">Amikor egy költségkategóriát termelésben vagy projektekben használnak, további projektekhez kapcsolódó információkat is meg kell adni.</span><span class="sxs-lookup"><span data-stu-id="3d186-109">When a cost category is used in production and projects, additional project-related information must be defined.</span></span> <span data-ttu-id="3d186-110">Például a projektekhez kapcsolódó óránkénti költségek eltérőek lehetnek a termeléshez kapcsolódó óránkénti költségekhez képest.</span><span class="sxs-lookup"><span data-stu-id="3d186-110">For example, the hourly costs that are associated with projects can differ from the hourly costs that are associated with production.</span></span> <span data-ttu-id="3d186-111">A **Költségkategóriák** lap segítségével meghatározhatja a Gyártásvezérlésben és a Projekt vezetés könyvelésében alkalmazott költségkategóriákat.</span><span class="sxs-lookup"><span data-stu-id="3d186-111">You can use the **Cost categories** page to define a cost category that is used in Production control and Project management accounting.</span></span> 

<span data-ttu-id="3d186-112">**Megjegyzés:** A költségkönyvelés **Projektkategóriák** oldallal rendelkezik, de ez az oldal még nincs kapcsolatban az ebben a témakörben ismertetett funkciókkal.</span><span class="sxs-lookup"><span data-stu-id="3d186-112">**Note:** Cost accounting has a **Project categories** page, but this page has no relationship to the functionality that is described in this topic.</span></span> <span data-ttu-id="3d186-113">A költségkategóriák projektekben történő használata esetén a **költségkategóriák** lapon további projekthez kapcsolódó adatot megjelenítő további lapok találhatók.</span><span class="sxs-lookup"><span data-stu-id="3d186-113">When you use a cost category in projects, the **Cost categories** page has additional tabs that show additional project-related information.</span></span> <span data-ttu-id="3d186-114">Ez az adat a kategóriacsoportot, a sortulajdonságot és a költségkategóriához társított főkönyvi számlákat tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="3d186-114">This information includes the category group, a line property, and ledger accounts that are assigned to the cost category.</span></span>

-   <span data-ttu-id="3d186-115">A költségkategóriákat az **Órák** tranzakciótípust támogató költségcsoporthoz kell hozzárendelni.</span><span class="sxs-lookup"><span data-stu-id="3d186-115">The cost category must be assigned to a category group that supports a transaction type of **Hours**.</span></span>
-   <span data-ttu-id="3d186-116">A sortulajdonság arról nyújt alapértelmezett információkat, hogy hogyan lehet a jelentett időt a projektekre terhelhetővé tenni.</span><span class="sxs-lookup"><span data-stu-id="3d186-116">The line property indicates default information about how reported time can be charged to a project.</span></span>
-   <span data-ttu-id="3d186-117">A költségekhez és értékesítéshez kapcsolódó főkönyvi számlák rendszerint a költségkategóriához rendelt költségcsoportra vonatkozóan vannak meghatározva.</span><span class="sxs-lookup"><span data-stu-id="3d186-117">Typically, the ledger accounts that are related to costs and sales are defined for the category group that is assigned to the cost category.</span></span> <span data-ttu-id="3d186-118">Azonban bizonyos számlák egy adott egyéni költségkategóriára vonatkozóan vannak meghatározva.</span><span class="sxs-lookup"><span data-stu-id="3d186-118">However, specific accounts can be defined for an individual cost category.</span></span>

<span data-ttu-id="3d186-119">A **Költségkategóriák** lapon található további gombokkal elérheti a kijelölt költségkategóriára vonatkozó, projektekkel kapcsolatos információkat.</span><span class="sxs-lookup"><span data-stu-id="3d186-119">Additional buttons on the **Cost categories** page let you access project-related information about a selected cost category.</span></span> <span data-ttu-id="3d186-120">Például megjelenítheti a projekthez kapcsolódó tranzakciókat, megadhatja az alkalmazottakat vagy a projekteket, meghatározhatja az óránkénti költségeket és az eladási árakat és megjelenítheti a jelentéseket.</span><span class="sxs-lookup"><span data-stu-id="3d186-120">For example, you can view project-related transactions, define employees or projects, define hourly costs and sales prices, and view reports.</span></span>



