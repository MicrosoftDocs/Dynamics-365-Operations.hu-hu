---
title: "Tényleges és költségvetési Power BI-tartalom"
description: "Ez a témakör a Tényleges és költségvetési Power BI-tartalmat ismerteti. Leírja, hogy hogyan kell hozzáférni a tartalomcsomagban szereplő jelentésekhez, és információkat nyújt a tartalomcsomag összeállításához előzőleg használt entitásokkal és adatmodellekkel kapcsolatban."
author: ryansandness
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application user, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: f09af96fb1c76d8737d2c535f1a46565a18deca0
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="actual-vs-budget-power-bi-content"></a><span data-ttu-id="72f59-104">Tényleges és költségvetési Power BI-tartalom</span><span class="sxs-lookup"><span data-stu-id="72f59-104">Actual vs budget Power BI content</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="72f59-105">Ez a témakör a **Tényleges és költségvetési** Power BI-tartalmat ismerteti.</span><span class="sxs-lookup"><span data-stu-id="72f59-105">This topic describes the **Actual vs budget** Microsoft Power BI content.</span></span> <span data-ttu-id="72f59-106">Leírja, hogy hogyan kell hozzáférni Power BI-jelentésekhez, és információkat nyújt a tartalom összeállításához használt entitásokkal és adatmodellekkel kapcsolatban.</span><span class="sxs-lookup"><span data-stu-id="72f59-106">It explains how to access the Power BI reports, and provides information about the data model and entities that were used to build the content.</span></span> 

# <a name="overview"></a><span data-ttu-id="72f59-107">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="72f59-107">Overview</span></span>

<span data-ttu-id="72f59-108">A **Tényleges és költségvetési** Power BI-tartalmat azoknak hoztuk létre, akik a valós és a költségvetési teljesítmény összevetéséért felelősek a szervezetnél.</span><span class="sxs-lookup"><span data-stu-id="72f59-108">The **Actual vs budget** Power BI content was created for individuals who are responsible for monitoring actual versus budget performance in their organization.</span></span> <span data-ttu-id="72f59-109">A **Tényleges és költségvetési** Power BI-tartalom a költségvetés-eltérésekbe nyújt betekintést.</span><span class="sxs-lookup"><span data-stu-id="72f59-109">The **Actual vs budget** Power BI content provides visibility into your budget variances.</span></span> <span data-ttu-id="72f59-110">Az aktuális év költségvetését elemezheti számlakategória, költségvetési kód, fő számla, fő számla leírása vagy pénzügyi időszak szerint, hogy jobban megérthesse az esetleges eltérések okát.</span><span class="sxs-lookup"><span data-stu-id="72f59-110">You can analyze budget for the current year by account category, budget code, main account, main account descriptions, or fiscal period to get a better understanding of the cause of any variances.</span></span> 

# <a name="accessing-the-power-bi-content"></a><span data-ttu-id="72f59-111">Power BI-tartalom elérése</span><span class="sxs-lookup"><span data-stu-id="72f59-111">Accessing the Power BI content</span></span>
<span data-ttu-id="72f59-112">A Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (2017. július) használata esetén a **Tényleges és költségvetési** Power BI-tartalom a **Főkönyvi költségvetések és előrejelzések** és a **Pénzügyi igazgató** munkaterületen jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="72f59-112">If you're using Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (July 2017), reports from the **Actual vs budget** Power BI content are shown in the **Ledger budget and forecasts** and **CFO** workspaces.</span></span>

# <a name="reports-that-are-included-in-the-power-bi-content"></a><span data-ttu-id="72f59-113">A Power BI-tartalomhoz tartozó jelentések</span><span class="sxs-lookup"><span data-stu-id="72f59-113">Reports that are included in the Power BI content</span></span>
<span data-ttu-id="72f59-114">A következő táblázat ismerteti a **Tényleges és költségvetési** Power BI-tartalom egyes jelentésoldalain található mutatókat.</span><span class="sxs-lookup"><span data-stu-id="72f59-114">The following table provides details about the metrics that are found on each report page in the **Actual vs budget** Power BI content.</span></span>

| <span data-ttu-id="72f59-115">Jelentés</span><span class="sxs-lookup"><span data-stu-id="72f59-115">Report</span></span>                      | <span data-ttu-id="72f59-116">Mutatók</span><span class="sxs-lookup"><span data-stu-id="72f59-116">Metrics</span></span> |
|-----------------------------|---------|
| <span data-ttu-id="72f59-117">Költségek – Tényleges - költségvetés</span><span class="sxs-lookup"><span data-stu-id="72f59-117">Expenses - Actual vs budget</span></span> | <ul><li><span data-ttu-id="72f59-118">Az idei teljes kiadás</span><span class="sxs-lookup"><span data-stu-id="72f59-118">Total expenses this year</span></span></li><li><span data-ttu-id="72f59-119">Költségvetés szerinti idei teljes kiadás</span><span class="sxs-lookup"><span data-stu-id="72f59-119">Budget total expenses this year</span></span></li></ul> |
| <span data-ttu-id="72f59-120">Bevétel - Tényleges és költségvetés</span><span class="sxs-lookup"><span data-stu-id="72f59-120">Revenue - Actual vs budget</span></span>  | <ul><li><span data-ttu-id="72f59-121">Az idei teljes bevétel</span><span class="sxs-lookup"><span data-stu-id="72f59-121">Total revenue this year</span></span></li><li><span data-ttu-id="72f59-122">Költségvetés szerinti idei teljes bevétel</span><span class="sxs-lookup"><span data-stu-id="72f59-122">Budget total revenue this year</span></span></li><ul> |
| <span data-ttu-id="72f59-123">Kiadás</span><span class="sxs-lookup"><span data-stu-id="72f59-123">Expense</span></span>                     | <ul><li><span data-ttu-id="72f59-124">Az idei teljes kiadás</span><span class="sxs-lookup"><span data-stu-id="72f59-124">Total expenses this year</span></span></li><li><span data-ttu-id="72f59-125">Költségcél a költségvetési alapján</span><span class="sxs-lookup"><span data-stu-id="72f59-125">Goal for expenses based on budget</span></span> </li><ul> |
| <span data-ttu-id="72f59-126">Bevétel</span><span class="sxs-lookup"><span data-stu-id="72f59-126">Revenue</span></span>                     | <ul><li><span data-ttu-id="72f59-127">Az idei teljes bevétel</span><span class="sxs-lookup"><span data-stu-id="72f59-127">Total revenue this year</span></span></li><li><span data-ttu-id="72f59-128">Bevételi cél a költségvetési alapján</span><span class="sxs-lookup"><span data-stu-id="72f59-128">Goal for revenue based on budget</span></span> </li><ul> |
| <span data-ttu-id="72f59-129">Nettó árbevétel</span><span class="sxs-lookup"><span data-stu-id="72f59-129">Net income</span></span>                  | <ul><li><span data-ttu-id="72f59-130">Az idei nettó bevétel</span><span class="sxs-lookup"><span data-stu-id="72f59-130">Net income this year</span></span></li><li><span data-ttu-id="72f59-131">Nettó bevételi cél a költségvetési alapján</span><span class="sxs-lookup"><span data-stu-id="72f59-131">Goal for net income based on budget</span></span> </li><ul> |

## <a name="extending-the-power-bi-content"></a><span data-ttu-id="72f59-132">Power BI-tartalom kibővítése</span><span class="sxs-lookup"><span data-stu-id="72f59-132">Extending the Power BI content</span></span>
<span data-ttu-id="72f59-133">A Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásban található tartalomcsomagok révén nagyszerű elemzési lehetőségeket nyújthat azoknak a személyeknek, akik nem jelentkeztek be a Microsoft Dynamics 365 szolgáltatásba.</span><span class="sxs-lookup"><span data-stu-id="72f59-133">By using the content packs that are available in Microsoft Dynamics Lifecycle Services (LCS), you can provide great analytics to people who don't sign in to Microsoft Dynamics 365.</span></span> <span data-ttu-id="72f59-134">Ezek a tartalomcsomagok módosíthatók, hogy más jelentéseket vagy megjelenítéseket is tartalmazhassanak, majd a tartalomcsomagok elemzés céljából közzétehetők a Power BI.com-bérlőjénél.</span><span class="sxs-lookup"><span data-stu-id="72f59-134">You can modify these content packs so that they include other reports or visuals, and then publish the content packs to your Power BI.com tenant for analysis.</span></span> 

<span data-ttu-id="72f59-135">A **Tényleges és költségvetési** Power BI-tartalmat az LCS Megosztott eszközök könyvtárában találja.</span><span class="sxs-lookup"><span data-stu-id="72f59-135">You can find the **Actual vs budget** Power BI content in the Shared assets library in LCS.</span></span> <span data-ttu-id="72f59-136">A tartalom letöltésére és szervezeténél való megvalósítására vonatkozó további információért lásd: [Power BI-tartalom az LCS megoldásban a Microsofttól és a partnerektől](power-bi-content-microsoft-partners.md).</span><span class="sxs-lookup"><span data-stu-id="72f59-136">For more information about how to download the content and implement it in your organization, see [Power BI content in LCS from Microsoft and your partners](power-bi-content-microsoft-partners.md).</span></span> <span data-ttu-id="72f59-137">Ha meg szeretne tekinteni egy demót, amely bemutatja a Power BI-tartalmak megvalósítását, lásd a [Power BI-tartalom a Microsofttól és az Ön partnereitől a Dynamics Lifecycle Services szolgáltatásban](https://mix.office.com/watch/9puyb1b2xs1w) című részt (Office Mix).</span><span class="sxs-lookup"><span data-stu-id="72f59-137">To watch a demo that shows how to implement the Power BI content, see the [Power BI content from Microsoft and your partners in Dynamics Lifecycle Services](https://mix.office.com/watch/9puyb1b2xs1w) Office Mix.</span></span>

# <a name="understanding-the-data-model-and-entities"></a><span data-ttu-id="72f59-138">Adatmodell, illetve entitások ismertetése</span><span class="sxs-lookup"><span data-stu-id="72f59-138">Understanding the data model and entities</span></span>

| <span data-ttu-id="72f59-139">Entitás</span><span class="sxs-lookup"><span data-stu-id="72f59-139">Entity</span></span>                    | <span data-ttu-id="72f59-140">Tartalom</span><span class="sxs-lookup"><span data-stu-id="72f59-140">Contents</span></span> |
|---------------------------|----------|
| <span data-ttu-id="72f59-141">Főkönyvi tevékenységek</span><span class="sxs-lookup"><span data-stu-id="72f59-141">General Ledger Activities</span></span> | <span data-ttu-id="72f59-142">Tranzakciós összegek a főkönyvbe</span><span class="sxs-lookup"><span data-stu-id="72f59-142">Transaction amounts for the general ledger</span></span> |
| <span data-ttu-id="72f59-143">Költségvetési tevékenységek</span><span class="sxs-lookup"><span data-stu-id="72f59-143">Budget Activities</span></span>         | <span data-ttu-id="72f59-144">Tranzakciós összegek a költségvetési jegyzékbe</span><span class="sxs-lookup"><span data-stu-id="72f59-144">Transaction amounts for the budget register</span></span> |
| <span data-ttu-id="72f59-145">Fő számlák</span><span class="sxs-lookup"><span data-stu-id="72f59-145">Main Accounts</span></span>             | <span data-ttu-id="72f59-146">Fő számlák a jelentések szűréséhez</span><span class="sxs-lookup"><span data-stu-id="72f59-146">Main accounts to filter reports by</span></span> |
| <span data-ttu-id="72f59-147">Pénzügyi naptárak</span><span class="sxs-lookup"><span data-stu-id="72f59-147">Fiscal Calendars</span></span>          | <span data-ttu-id="72f59-148">Pénzügyi naptárak a jelentések szűréséhez</span><span class="sxs-lookup"><span data-stu-id="72f59-148">Fiscal calendars to filter reports by</span></span> |
| <span data-ttu-id="72f59-149">Főkönyvek</span><span class="sxs-lookup"><span data-stu-id="72f59-149">Ledgers</span></span>                   | <span data-ttu-id="72f59-150">A jelenlegi főkönyvi jelentés szűréséhez használható főkönyvek</span><span class="sxs-lookup"><span data-stu-id="72f59-150">Ledgers that can be used to filter the report to the current ledger</span></span> |
| <span data-ttu-id="72f59-151">Költségvetési kódok</span><span class="sxs-lookup"><span data-stu-id="72f59-151">Budget Codes</span></span>              | <span data-ttu-id="72f59-152">Költségvetési kódok a jelentések szűréséhez</span><span class="sxs-lookup"><span data-stu-id="72f59-152">Budget codes to filter reports by</span></span> |
| <span data-ttu-id="72f59-153">Jogi személyek</span><span class="sxs-lookup"><span data-stu-id="72f59-153">Legal Entities</span></span>            | <span data-ttu-id="72f59-154">A jelenlegi jogi személyre vonatkozó jelentés szűréséhez használható jogi személyek</span><span class="sxs-lookup"><span data-stu-id="72f59-154">Legal entities that can be used to filter the report to the current legal entity</span></span> |

