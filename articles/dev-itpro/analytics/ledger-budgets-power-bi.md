---
title: Tényleges viszonyítva a költségvetéshez Power BI tartalom
description: Ez a témakör a Tényleges viszonyítva a költségvetéshez Power BI-tartalmat ismerteti. Leírja, hogy hogyan kell hozzáférni a tartalomcsomagban szereplő jelentésekhez, és információkat nyújt a tartalomcsomag összeállításához előzőleg használt entitásokkal és adatmodellekkel kapcsolatban.
author: ryansandness
manager: AnnBe
ms.date: 12/18/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BudgetTrackingWorkspace
audience: Application user, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: c801544e9e37a528203f5a1730aa8cb526d63dbf
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1553738"
---
# <a name="actual-vs-budget-power-bi-content"></a><span data-ttu-id="9b210-104">Tényleges viszonyítva a költségvetéshez Power BI tartalom</span><span class="sxs-lookup"><span data-stu-id="9b210-104">Actual vs budget Power BI content</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9b210-105">Ez a témakör a **Tényleges viszonyítva a költségvetéshez** Microsoft Power BI-tartalmat ismerteti.</span><span class="sxs-lookup"><span data-stu-id="9b210-105">This topic describes the **Actual vs budget** Microsoft Power BI content.</span></span> <span data-ttu-id="9b210-106">Leírja, hogy hogyan kell hozzáférni a Power BI-jelentésekhez, és információkat nyújt a tartalomcsomag összeállításához előzőleg használt entitásokkal és adatmodellekkel kapcsolatban.</span><span class="sxs-lookup"><span data-stu-id="9b210-106">It explains how to access the Power BI reports, and provides information about the data model and entities that were used to build the content.</span></span>

## <a name="overview"></a><span data-ttu-id="9b210-107">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="9b210-107">Overview</span></span>

<span data-ttu-id="9b210-108">A **Tényleges viszonyítva a költségvetéshez** Power BI-tartalmat azoknak hoztuk létre, akik a valós és a költségvetési teljesítmény összevetéséért felelősek a szervezetnél.</span><span class="sxs-lookup"><span data-stu-id="9b210-108">The **Actual vs budget** Power BI content was created for individuals who are responsible for monitoring actual versus budget performance in their organization.</span></span> <span data-ttu-id="9b210-109">A **Tényleges viszonyítva a költségvetéshez** Power BI-tartalom a költségvetés-eltérésekbe nyújt betekintést.</span><span class="sxs-lookup"><span data-stu-id="9b210-109">The **Actual vs budget** Power BI content provides visibility into your budget variances.</span></span> <span data-ttu-id="9b210-110">Az aktuális év költségvetését elemezheti számlakategória, költségvetési kód, fő számla, fő számla leírása vagy pénzügyi időszak szerint, hogy jobban megérthesse az esetleges eltérések okát.</span><span class="sxs-lookup"><span data-stu-id="9b210-110">You can analyze budget for the current year by account category, budget code, main account, main account descriptions, or fiscal period to get a better understanding of the cause of any variances.</span></span>

## <a name="accessing-the-power-bi-content"></a><span data-ttu-id="9b210-111">A Power BI tartalom elérése</span><span class="sxs-lookup"><span data-stu-id="9b210-111">Accessing the Power BI content</span></span>
<span data-ttu-id="9b210-112">A **Tényleges viszonyítva a költségvetéshez** Power BI-tartalom jelentései a **Főkönyvi költségvetések és előrejelzések** és a **Pénzügyi igazgató** munkaterületen jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="9b210-112">Reports from the **Actual vs budget** Power BI content are shown in the **Ledger budget and forecasts** and **CFO** workspaces.</span></span>

## <a name="reports-that-are-included-in-the-power-bi-content"></a><span data-ttu-id="9b210-113">Jelentések, amelyek a Power BI-tartalomban szerepelnek</span><span class="sxs-lookup"><span data-stu-id="9b210-113">Reports that are included in the Power BI content</span></span>
<span data-ttu-id="9b210-114">A következő táblázat ismerteti a **Tényleges viszonyítva a költségvetéshez** Power BI-tartalom egyes jelentésoldalain található mutatókat.</span><span class="sxs-lookup"><span data-stu-id="9b210-114">The following table provides details about the metrics that are found on each report page in the **Actual vs budget** Power BI content.</span></span>

| <span data-ttu-id="9b210-115">Jelentés</span><span class="sxs-lookup"><span data-stu-id="9b210-115">Report</span></span>                      | <span data-ttu-id="9b210-116">Mutatók</span><span class="sxs-lookup"><span data-stu-id="9b210-116">Metrics</span></span>                                                                             |
|-----------------------------|-------------------------------------------------------------------------------------|
| <span data-ttu-id="9b210-117">Költségek – Tényleges - költségvetés</span><span class="sxs-lookup"><span data-stu-id="9b210-117">Expenses - Actual vs budget</span></span> | <ul><li><span data-ttu-id="9b210-118">Az idei teljes kiadás</span><span class="sxs-lookup"><span data-stu-id="9b210-118">Total expenses this year</span></span></li><li><span data-ttu-id="9b210-119">Költségvetés szerinti idei teljes kiadás</span><span class="sxs-lookup"><span data-stu-id="9b210-119">Budget total expenses this year</span></span></li></ul>  |
| <span data-ttu-id="9b210-120">Bevétel - Tényleges és költségvetés</span><span class="sxs-lookup"><span data-stu-id="9b210-120">Revenue - Actual vs budget</span></span>  | <ul><li><span data-ttu-id="9b210-121">Az idei teljes bevétel</span><span class="sxs-lookup"><span data-stu-id="9b210-121">Total revenue this year</span></span></li><li><span data-ttu-id="9b210-122">Költségvetés szerinti idei teljes bevétel</span><span class="sxs-lookup"><span data-stu-id="9b210-122">Budget total revenue this year</span></span></li><ul>     |
| <span data-ttu-id="9b210-123">Kiadás</span><span class="sxs-lookup"><span data-stu-id="9b210-123">Expense</span></span>                     | <ul><li><span data-ttu-id="9b210-124">Az idei teljes kiadás</span><span class="sxs-lookup"><span data-stu-id="9b210-124">Total expenses this year</span></span></li><li><span data-ttu-id="9b210-125">Költségcél a költségvetési alapján</span><span class="sxs-lookup"><span data-stu-id="9b210-125">Goal for expenses based on budget</span></span></li><ul> |
| <span data-ttu-id="9b210-126">Bevétel</span><span class="sxs-lookup"><span data-stu-id="9b210-126">Revenue</span></span>                     | <ul><li><span data-ttu-id="9b210-127">Az idei teljes bevétel</span><span class="sxs-lookup"><span data-stu-id="9b210-127">Total revenue this year</span></span></li><li><span data-ttu-id="9b210-128">Bevételi cél a költségvetési alapján</span><span class="sxs-lookup"><span data-stu-id="9b210-128">Goal for revenue based on budget</span></span></li><ul>   |
| <span data-ttu-id="9b210-129">Nettó árbevétel</span><span class="sxs-lookup"><span data-stu-id="9b210-129">Net income</span></span>                  | <ul><li><span data-ttu-id="9b210-130">Az idei nettó bevétel</span><span class="sxs-lookup"><span data-stu-id="9b210-130">Net income this year</span></span></li><li><span data-ttu-id="9b210-131">Nettó bevételi cél a költségvetési alapján</span><span class="sxs-lookup"><span data-stu-id="9b210-131">Goal for net income based on budget</span></span></li><ul>   |

## <a name="understanding-the-data-model-and-entities"></a><span data-ttu-id="9b210-132">Adatmodell, illetve entitások ismertetése</span><span class="sxs-lookup"><span data-stu-id="9b210-132">Understanding the data model and entities</span></span>

| <span data-ttu-id="9b210-133">Entitás</span><span class="sxs-lookup"><span data-stu-id="9b210-133">Entity</span></span>                    | <span data-ttu-id="9b210-134">Tartalom</span><span class="sxs-lookup"><span data-stu-id="9b210-134">Contents</span></span>                                                                         |
|---------------------------|----------------------------------------------------------------------------------|
| <span data-ttu-id="9b210-135">Főkönyvi tevékenységek</span><span class="sxs-lookup"><span data-stu-id="9b210-135">General Ledger Activities</span></span> | <span data-ttu-id="9b210-136">Tranzakciós összegek a főkönyvbe</span><span class="sxs-lookup"><span data-stu-id="9b210-136">Transaction amounts for the general ledger</span></span>                                       |
| <span data-ttu-id="9b210-137">Költségvetési tevékenységek</span><span class="sxs-lookup"><span data-stu-id="9b210-137">Budget Activities</span></span>         | <span data-ttu-id="9b210-138">Tranzakciós összegek a költségvetési jegyzékbe</span><span class="sxs-lookup"><span data-stu-id="9b210-138">Transaction amounts for the budget register</span></span>                                      |
| <span data-ttu-id="9b210-139">Fő számlák</span><span class="sxs-lookup"><span data-stu-id="9b210-139">Main Accounts</span></span>             | <span data-ttu-id="9b210-140">Fő számlák a jelentések szűréséhez</span><span class="sxs-lookup"><span data-stu-id="9b210-140">Main accounts to filter reports by</span></span>                                               |
| <span data-ttu-id="9b210-141">Pénzügyi naptárak</span><span class="sxs-lookup"><span data-stu-id="9b210-141">Fiscal Calendars</span></span>          | <span data-ttu-id="9b210-142">Pénzügyi naptárak a jelentések szűréséhez</span><span class="sxs-lookup"><span data-stu-id="9b210-142">Fiscal calendars to filter reports by</span></span>                                            |
| <span data-ttu-id="9b210-143">Főkönyvek</span><span class="sxs-lookup"><span data-stu-id="9b210-143">Ledgers</span></span>                   | <span data-ttu-id="9b210-144">A jelenlegi főkönyvi jelentés szűréséhez használható főkönyvek</span><span class="sxs-lookup"><span data-stu-id="9b210-144">Ledgers that can be used to filter the report to the current ledger</span></span>              |
| <span data-ttu-id="9b210-145">Költségvetési kódok</span><span class="sxs-lookup"><span data-stu-id="9b210-145">Budget Codes</span></span>              | <span data-ttu-id="9b210-146">Költségvetési kódok a jelentések szűréséhez</span><span class="sxs-lookup"><span data-stu-id="9b210-146">Budget codes to filter reports by</span></span>                                                |
| <span data-ttu-id="9b210-147">Jogi személyek</span><span class="sxs-lookup"><span data-stu-id="9b210-147">Legal Entities</span></span>            | <span data-ttu-id="9b210-148">A jelenlegi jogi személyre vonatkozó jelentés szűréséhez használható jogi személyek</span><span class="sxs-lookup"><span data-stu-id="9b210-148">Legal entities that can be used to filter the report to the current legal entity</span></span> |
