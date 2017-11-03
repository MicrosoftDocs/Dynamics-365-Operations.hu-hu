---
title: "Kézi értékcsökkenés"
description: "Ez a cikk az értékcsökkenés felhasználási módszeréről nyújt áttekintést."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 13811
ms.assetid: b0e837c9-515a-4aed-9060-5ec94f37edeb
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: d7a672b80a0da7ab05acf5b5efe041f0f89c0042
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="manual-depreciation"></a><span data-ttu-id="0cc91-103">Kézi értékcsökkenés</span><span class="sxs-lookup"><span data-stu-id="0cc91-103">Manual depreciation</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="0cc91-104">Ez a cikk az értékcsökkenés felhasználási módszeréről nyújt áttekintést.</span><span class="sxs-lookup"><span data-stu-id="0cc91-104">This article gives an overview of the manual depreciation method.</span></span>

<span data-ttu-id="0cc91-105">Amikor beállítja egy tárgyi eszköz értékesítési profilját és kijelöli a **Manuális** opciót a **Metódus** mezőben az **Értékcsökkenési profilok** lapon, akkor az értékcsökkenési profilhoz rendelt tárgyi eszközök értékcsökkenése az alapján a százalék alapján van meghatározva, amelyet megad az egyes időintervallumokhoz a naptári évben.</span><span class="sxs-lookup"><span data-stu-id="0cc91-105">When you set up a fixed asset depreciation profile and select **Manual** in the **Method** field on the **Depreciation profiles** page, the depreciation of fixed assets that are assigned to the depreciation profile is determined by the percentage that you enter for each interval in the calendar year.</span></span> <span data-ttu-id="0cc91-106">Az időközök, amelyekhez százalékokat ad meg feladásra kerülnek azon értéknek megfelelően, amit az **Értékcsökkenési profilok** lap **Általános** gyorslapján az **Időszak-gyakoriság** mezőben meghatároz.</span><span class="sxs-lookup"><span data-stu-id="0cc91-106">The intervals that you set up percentages for are posted according to the value that you select in the **Period frequency** field on the **General** FastTab of the **Depreciation profiles** page.</span></span> <span data-ttu-id="0cc91-107">Itt szerepelnek a kiválasztható értékek:</span><span class="sxs-lookup"><span data-stu-id="0cc91-107">Here are the values that you can select:</span></span>

-   <span data-ttu-id="0cc91-108">Évente</span><span class="sxs-lookup"><span data-stu-id="0cc91-108">Yearly</span></span>
-   <span data-ttu-id="0cc91-109">Havonta</span><span class="sxs-lookup"><span data-stu-id="0cc91-109">Monthly</span></span>
-   <span data-ttu-id="0cc91-110">Negyedévente</span><span class="sxs-lookup"><span data-stu-id="0cc91-110">Quarterly</span></span>
-   <span data-ttu-id="0cc91-111">Féléves</span><span class="sxs-lookup"><span data-stu-id="0cc91-111">Half-Yearly</span></span>
-   <span data-ttu-id="0cc91-112">Napi</span><span class="sxs-lookup"><span data-stu-id="0cc91-112">Daily</span></span>

<span data-ttu-id="0cc91-113">Miután kijelöli az időszak-gyakoriságot kattintson a **Kézi ütemezések** gombra és állítsa be a százalékokat az egyes feladási intervallumokhoz.</span><span class="sxs-lookup"><span data-stu-id="0cc91-113">After you select the period frequency, click **Manual schedules**, and set up percentages for each posting interval.</span></span> <span data-ttu-id="0cc91-114">A kézi ütemezések és a feladási intervallumok közösen meghatározzák az értékcsökkenés összegét, úgy ahogy az ebben a cikkben szereplő példák később bemutatják.</span><span class="sxs-lookup"><span data-stu-id="0cc91-114">Together, the manual schedules and the posting intervals define the depreciation amount, as shown in the examples later in this article.</span></span> <span data-ttu-id="0cc91-115">A kézi értékcsökkenés mindig a beszerzési ár egy százalékaként számítandó.</span><span class="sxs-lookup"><span data-stu-id="0cc91-115">Manual depreciation is always calculated as a percentage of the acquisition price.</span></span> <span data-ttu-id="0cc91-116">Kézi értékcsökkenés esetén az Ön által az értékcsökkenés intervallumaiban megadott százalékok összegének nem kell 100 százaléknak lennie.</span><span class="sxs-lookup"><span data-stu-id="0cc91-116">For manual depreciation, the percentages that you enter in the intervals of the depreciation don't have to add up to 100 percent.</span></span> <span data-ttu-id="0cc91-117">A kézi értékcsökkenés egy rugalmas értékcsökkenési mód, amely gyakran használatos rendkívüli értékcsökkenési profilok meghatározásához a **Könyvek** lapon, úgy mint egy nem periodikus értékcsökkenés különleges célokra (mint például adó).</span><span class="sxs-lookup"><span data-stu-id="0cc91-117">Manual depreciation is a flexible depreciation method that is often used to define an extraordinary depreciation profile on the **Books** page, such as a non-periodic depreciation for special purposes (for example, tax).</span></span>

## <a name="examples"></a><span data-ttu-id="0cc91-118">Példák</span><span class="sxs-lookup"><span data-stu-id="0cc91-118">Examples</span></span>
<span data-ttu-id="0cc91-119">Beszerzési ár: 11 000,00 Várható maradványérték: 1 000,00 A következő táblázat mutatja az időintervallumokat és százalékokat, amelyek Ön beállít a **Tárgyi eszköz értékcsökkenési profiljának ütemezései** lapon.</span><span class="sxs-lookup"><span data-stu-id="0cc91-119">Acquisition price: 11,000.00 Expected scrap value: 1,000.00 The following table shows the intervals and percentages that you set up on the **Fixed asset depreciation profile schedules** page.</span></span>

| <span data-ttu-id="0cc91-120">Időköz száma</span><span class="sxs-lookup"><span data-stu-id="0cc91-120">Interval number</span></span> | <span data-ttu-id="0cc91-121">Százalék</span><span class="sxs-lookup"><span data-stu-id="0cc91-121">Percentage</span></span> |
|-----------------|------------|
| <span data-ttu-id="0cc91-122">1</span><span class="sxs-lookup"><span data-stu-id="0cc91-122">1</span></span>               | <span data-ttu-id="0cc91-123">10,00</span><span class="sxs-lookup"><span data-stu-id="0cc91-123">10.00</span></span>      |
| <span data-ttu-id="0cc91-124">2</span><span class="sxs-lookup"><span data-stu-id="0cc91-124">2</span></span>               | <span data-ttu-id="0cc91-125">50,00</span><span class="sxs-lookup"><span data-stu-id="0cc91-125">50.00</span></span>      |
| <span data-ttu-id="0cc91-126">3</span><span class="sxs-lookup"><span data-stu-id="0cc91-126">3</span></span>               | <span data-ttu-id="0cc91-127">8,00</span><span class="sxs-lookup"><span data-stu-id="0cc91-127">8.00</span></span>       |

<span data-ttu-id="0cc91-128">A következő táblázat mutatja, az értékcsökkenés számítását az egyes intervallumokra.</span><span class="sxs-lookup"><span data-stu-id="0cc91-128">The following table shows how the depreciation for each interval is calculated.</span></span>

|  <span data-ttu-id="0cc91-129">Időköz száma</span><span class="sxs-lookup"><span data-stu-id="0cc91-129">Interval number</span></span> | <span data-ttu-id="0cc91-130">Az éves értékcsökkenés-összeg számítása</span><span class="sxs-lookup"><span data-stu-id="0cc91-130">Calculation of the yearly depreciation amount</span></span> | <span data-ttu-id="0cc91-131">Nettó könyv szerinti érték az intervallum végén</span><span class="sxs-lookup"><span data-stu-id="0cc91-131">Net book value at the end of the interval</span></span> |
|------------------|-----------------------------------------------|-------------------------------------------|
| <span data-ttu-id="0cc91-132">1</span><span class="sxs-lookup"><span data-stu-id="0cc91-132">1</span></span>                | <span data-ttu-id="0cc91-133">(11 000-1 000) × 10% = 1 000</span><span class="sxs-lookup"><span data-stu-id="0cc91-133">(11,000 – 1,000) × 10% = 1,000</span></span>                | <span data-ttu-id="0cc91-134">10 000 × (11 000-1 000)</span><span class="sxs-lookup"><span data-stu-id="0cc91-134">10,000 (11,000 – 1,000)</span></span>                   |
| <span data-ttu-id="0cc91-135">2</span><span class="sxs-lookup"><span data-stu-id="0cc91-135">2</span></span>                | <span data-ttu-id="0cc91-136">(11 000-1 000) × 50% = 5 000</span><span class="sxs-lookup"><span data-stu-id="0cc91-136">(11,000 – 1,000) × 50% = 5,000</span></span>                | <span data-ttu-id="0cc91-137">5 000 × (10 000-5 000)</span><span class="sxs-lookup"><span data-stu-id="0cc91-137">5,000 (10,000 – 5,000)</span></span>                    |
| <span data-ttu-id="0cc91-138">3</span><span class="sxs-lookup"><span data-stu-id="0cc91-138">3</span></span>                | <span data-ttu-id="0cc91-139">(11 000-1 000) × 8% = 800</span><span class="sxs-lookup"><span data-stu-id="0cc91-139">(11,000 – 1,000) × 8% = 800</span></span>                   | <span data-ttu-id="0cc91-140">4 200 (5 000-800)</span><span class="sxs-lookup"><span data-stu-id="0cc91-140">4,200 (5,000 – 800)</span></span>                       |

<span data-ttu-id="0cc91-141">Ha kiválasztja a **Havi** lehetőséget az**Időszak gyakoriság** mezőben, akkor 12 kézi ütemezési intervallum jön létre.</span><span class="sxs-lookup"><span data-stu-id="0cc91-141">If you select **Monthly** in the **Period frequency** field, you set up 12 manual schedule intervals.</span></span> <span data-ttu-id="0cc91-142">A következő táblázat mutatja az értékcsökkenés-összegeket az első két időszakra.</span><span class="sxs-lookup"><span data-stu-id="0cc91-142">The following table shows the depreciation amounts for the first two intervals.</span></span>

| <span data-ttu-id="0cc91-143">Intervallum</span><span class="sxs-lookup"><span data-stu-id="0cc91-143">Interval</span></span> | <span data-ttu-id="0cc91-144">Értékcsökkenés összege</span><span class="sxs-lookup"><span data-stu-id="0cc91-144">Depreciation amount</span></span>            |
|----------|--------------------------------|
| <span data-ttu-id="0cc91-145">Január</span><span class="sxs-lookup"><span data-stu-id="0cc91-145">January</span></span>  | <span data-ttu-id="0cc91-146">(11 000-1 000) × 10% = 1 000</span><span class="sxs-lookup"><span data-stu-id="0cc91-146">(11,000 – 1,000) × 10% = 1,000</span></span> |
| <span data-ttu-id="0cc91-147">Február</span><span class="sxs-lookup"><span data-stu-id="0cc91-147">February</span></span> | <span data-ttu-id="0cc91-148">(11 000-1 000) × 50% = 5 000</span><span class="sxs-lookup"><span data-stu-id="0cc91-148">(11,000 – 1,000) × 50% = 5,000</span></span> |

<span data-ttu-id="0cc91-149">Ha a **Féléves** lehetőséget választja az ****Időszak-gyakoriság** mezőben**, akkor 2 kézi ütemezési intervallum jön létre.</span><span class="sxs-lookup"><span data-stu-id="0cc91-149">If you select **Half-Yearly** in the ****Period frequency** field**, you set up two manual schedule intervals.</span></span> <span data-ttu-id="0cc91-150">A következő táblázat mutatja az értékcsökkenés-összegeket ezekhez az időszakokhoz.</span><span class="sxs-lookup"><span data-stu-id="0cc91-150">The following table shows the depreciation amounts for those two intervals.</span></span>

| <span data-ttu-id="0cc91-151">Intervallum</span><span class="sxs-lookup"><span data-stu-id="0cc91-151">Interval</span></span>    | <span data-ttu-id="0cc91-152">Értékcsökkenés összege</span><span class="sxs-lookup"><span data-stu-id="0cc91-152">Depreciation amount</span></span>            |
|-------------|--------------------------------|
| <span data-ttu-id="0cc91-153">június 30.</span><span class="sxs-lookup"><span data-stu-id="0cc91-153">June 30</span></span>     | <span data-ttu-id="0cc91-154">(11 000-1 000) × 10% = 1 000</span><span class="sxs-lookup"><span data-stu-id="0cc91-154">(11,000 – 1,000) × 10% = 1,000</span></span> |
| <span data-ttu-id="0cc91-155">december 31.</span><span class="sxs-lookup"><span data-stu-id="0cc91-155">December 31</span></span> | <span data-ttu-id="0cc91-156">(11 000-1 000) × 50% = 5 000</span><span class="sxs-lookup"><span data-stu-id="0cc91-156">(11,000 – 1,000) × 50% = 5,000</span></span> |

<span data-ttu-id="0cc91-157">Az intervallumokban megadott százalékoknak nem kell 100-at kiadniuk.</span><span class="sxs-lookup"><span data-stu-id="0cc91-157">The total of percentages for all intervals doesn't have to be 100.</span></span> <span data-ttu-id="0cc91-158">Azonban üzenetet kap, ha a **Halmozott százalékos érték** mezőben a **Tárgyi eszköz értékcsökkenési profiljának ütemezései** lapon az érték nem **100**.</span><span class="sxs-lookup"><span data-stu-id="0cc91-158">However, you receive a message if the value in the **Cumulative percentage** field on the **Fixed asset depreciation profile schedules** page isn't **100**.</span></span>




