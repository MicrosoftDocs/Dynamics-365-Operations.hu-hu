---
title: 200 százalék degresszív értékcsökkenés
description: Ez a cikk a 200 százalékos degresszív értékcsökkenési módszerről nyújt áttekintést.
author: saraschi2
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 13951
ms.assetid: 69b4e010-7683-4dc2-8a06-6d572f37e903
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0474a8cecccaf1e23874458c27e0bea991140b6c
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/01/2019
ms.locfileid: "1840793"
---
# <a name="200-percent-reducing-balance-depreciation"></a><span data-ttu-id="41be2-103">200 százalék degresszív értékcsökkenés</span><span class="sxs-lookup"><span data-stu-id="41be2-103">200 percent reducing balance depreciation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="41be2-104">Ez a cikk a 200 százalékos degresszív értékcsökkenési módszerről nyújt áttekintést.</span><span class="sxs-lookup"><span data-stu-id="41be2-104">This article gives an overview of the 200 percent reducing balance method of depreciation.</span></span>

<span data-ttu-id="41be2-105">Amikor beállít egy tárgyieszköz-értékcsökkenési profilt és kijelöli a **200% degresszív** értéket a **Mód** mezőben az **Értékcsökkenési profilok** lapon, akkor a tárgyi eszközök, amelyek az értékcsökkenési profilokhoz vannak rendelve értékcsökkentve lesznek ugyanazzal százalékos értékkel, ami az egyes értékcsökkenési időszakoknál szerepel.</span><span class="sxs-lookup"><span data-stu-id="41be2-105">When you set up a fixed asset depreciation profile and select **200% reducing balance** in the **Method** field on the **Depreciation profiles** page, fixed assets that are assigned the depreciation profile are depreciated by the same percentage in each depreciation period.</span></span> <span data-ttu-id="41be2-106">A százalék kiszámítása az eszköz élettartama alapján történik.</span><span class="sxs-lookup"><span data-stu-id="41be2-106">The percentage is calculated based on the service life of the asset.</span></span> <span data-ttu-id="41be2-107">Ha például egy eszköz élettartama öt év, akkor a számított százalékos érték 40% lesz (200% ÷ 5).</span><span class="sxs-lookup"><span data-stu-id="41be2-107">For example, if an asset has a service life of five years, the percentage is calculated as 40 percent (200% ÷ 5).</span></span> 

<span data-ttu-id="41be2-108">Ez a módszer duplán degresszív értékcsökkenésként is ismert.</span><span class="sxs-lookup"><span data-stu-id="41be2-108">This method is also known as double declining balance.</span></span>

<span data-ttu-id="41be2-109">200 % degresszív értékcsökkenés beállítása esetén be kell még jelölnie a beállításokat az **Értékcsökkenési év** mezőben és az **Időszak-gyakoriság** mezőben az **Értékcsökkenési profilok** lapon.</span><span class="sxs-lookup"><span data-stu-id="41be2-109">To set up 200% reducing balance depreciation, you must also select options in the **Depreciation year** field and the **Period frequency** field on the **Depreciation profiles** page.</span></span> <span data-ttu-id="41be2-110">Az **Időszak-gyakoriság** mezőben rendelkezésre álló beállítások eltérőek lehetnek, az **Értékcsökkenési év** mezőben kijelölt értéktől függően.</span><span class="sxs-lookup"><span data-stu-id="41be2-110">The options that are available in the **Period frequency** field vary, depending on the value that you select in the **Depreciation year** field.</span></span>

## <a name="select-a-depreciation-year"></a><span data-ttu-id="41be2-111">Az értékcsökkenési év kiválasztása</span><span class="sxs-lookup"><span data-stu-id="41be2-111">Select a depreciation year</span></span>
<span data-ttu-id="41be2-112">Kiválaszthatja a **Naptár** vagy **Pénzügyi** elemeket az **Értékcsökkenési év** mezőben az **Értékcsökkenési profilok** lapon.</span><span class="sxs-lookup"><span data-stu-id="41be2-112">You can select either **Calendar** or **Fiscal** in the **Depreciation year** field on the **Depreciation profiles** page.</span></span> <span data-ttu-id="41be2-113">Az alapértelmezett érték **Naptár**.</span><span class="sxs-lookup"><span data-stu-id="41be2-113">The default value is **Calendar**.</span></span> 

<span data-ttu-id="41be2-114">A kiválasztás függvényében változnak az **Időszak gyakorisága** mezőben elérhető beállítások.</span><span class="sxs-lookup"><span data-stu-id="41be2-114">Your selection determines the options that are available in the **Period frequency** field.</span></span> <span data-ttu-id="41be2-115">Ez a mező meghatározza a az értékcsökkenés könyvelésének feladási időpontját és összegét a naptári év során.</span><span class="sxs-lookup"><span data-stu-id="41be2-115">This field defines the depreciation accrual posting dates and amounts throughout the calendar year.</span></span>

### <a name="calendar"></a><span data-ttu-id="41be2-116">Naptár</span><span class="sxs-lookup"><span data-stu-id="41be2-116">Calendar</span></span>

<span data-ttu-id="41be2-117">Megtarthatja az alapértelmezett értéket az **Értékcsökkenési év** mezőben, **Naptár**.</span><span class="sxs-lookup"><span data-stu-id="41be2-117">You can keep the default value in the **Depreciation year** field, **Calendar**.</span></span> 

<span data-ttu-id="41be2-118">A **naptár** lehetőség választása esetén az értékcsökkenés alapja minden évben január 1-jén frissül.</span><span class="sxs-lookup"><span data-stu-id="41be2-118">The **Calendar** option updates the depreciation base on January 1 of each year.</span></span> <span data-ttu-id="41be2-119">Jellemzően az értékcsökkenés a nettó könyv szerinti érték mínusz a maradványérték.</span><span class="sxs-lookup"><span data-stu-id="41be2-119">Typically, the depreciation is the net book value minus the scrap value.</span></span> <span data-ttu-id="41be2-120">Az ebben a témában szereplő későbbi példákban az értékcsökkenés alapja a számítások oszlop első kifejezésében szereplő számláló.</span><span class="sxs-lookup"><span data-stu-id="41be2-120">In the examples later in this topic, the depreciation base is the numerator in the first expression in the calculations column.</span></span> 

<span data-ttu-id="41be2-121">Ha bejelöli **Naptár** értéket az értékcsökkenés éveként a következő lehetőségek érhetők el az **Időszak-gyakoriság** mezőben:</span><span class="sxs-lookup"><span data-stu-id="41be2-121">If you select **Calendar** as the depreciation year, the following options are available in the **Period frequency** field:</span></span>

-   <span data-ttu-id="41be2-122">**Éves** felad egy összeget december 31-én.</span><span class="sxs-lookup"><span data-stu-id="41be2-122">**Yearly** posts an amount on December 31.</span></span>
-   <span data-ttu-id="41be2-123">**Havi**: felad egy havi összeget minden naptári hó végén.</span><span class="sxs-lookup"><span data-stu-id="41be2-123">**Monthly** posts a monthly amount at the end of each calendar month.</span></span>
-   <span data-ttu-id="41be2-124">**Negyedéves**:Felad egy negyedéves összeget minden naptári negyedév végén (március 31., június 30., szeptember 30. és december 31.).</span><span class="sxs-lookup"><span data-stu-id="41be2-124">**Quarterly** posts a quarterly amount at the end of each calendar quarter (March 31, June 30, September 30, and December 31).</span></span>
-   <span data-ttu-id="41be2-125">**Féléves**: felad egy féléves összeget minden naptári félév végén (június 30. és december 31.).</span><span class="sxs-lookup"><span data-stu-id="41be2-125">**Half-Yearly** posts a half-yearly amount at the calendar half year (June 30 and December 31).</span></span>
-   <span data-ttu-id="41be2-126">**Napi** Feladja az értékcsökkenési összeget a napi értékcsökkenési módhoz úgy, hogy minden naphoz egy tranzakciót használ.</span><span class="sxs-lookup"><span data-stu-id="41be2-126">**Daily** posts the depreciation amount for the daily depreciation method by using one transaction for each day.</span></span>

### <a name="fiscal"></a><span data-ttu-id="41be2-127">Pénzügyi</span><span class="sxs-lookup"><span data-stu-id="41be2-127">Fiscal</span></span>

<span data-ttu-id="41be2-128">Ha bejelöli a **Pénzügyi** lehetőséget az **Értékcsökkenési** év mezőben, akkor a 200 % degresszív értékcsökkenés számítása azon pénzügyi év szerint történik, amelynek pénzügyi naptára meg van adva a könyvben vagy amelyik pénzügyi naptár ki van jelölve a **Főkönyv** lapon.</span><span class="sxs-lookup"><span data-stu-id="41be2-128">If you select **Fiscal** in the **Depreciation** year field, 200% reducing balance depreciation is calculated based on the fiscal year for the fiscal calendar that is specified for the book, or for the fiscal calendar that is selected on the **Ledger** page.</span></span> <span data-ttu-id="41be2-129">A pénzügyi naptárak a **Pénzügyi naptárak** oldalon állíthatóak be.</span><span class="sxs-lookup"><span data-stu-id="41be2-129">Fiscal calendars are set up on the **Fiscal calendars** page.</span></span> 

<span data-ttu-id="41be2-130">Egy július 1-től június 30-ig tartó pénzügyi év esetén az értékcsökkenés számítása július 1-jén kezdődik.</span><span class="sxs-lookup"><span data-stu-id="41be2-130">For example, for the fiscal year July 1 through June 30, the depreciation calculation starts on July 1.</span></span> <span data-ttu-id="41be2-131">Az üzleti év 12 hónapnál hosszabb vagy rövidebb is lehet.</span><span class="sxs-lookup"><span data-stu-id="41be2-131">The fiscal year can be longer or shorter than 12 months.</span></span> <span data-ttu-id="41be2-132">Az értékcsökkenés minden időszakhoz helyesbítve van.</span><span class="sxs-lookup"><span data-stu-id="41be2-132">The depreciation is adjusted for each period.</span></span> <span data-ttu-id="41be2-133">A következő üzleti év hossza az időszakok beállítása alapján van meghatározva a **Pénzügyi naptárak** oldalon.</span><span class="sxs-lookup"><span data-stu-id="41be2-133">The length of the next fiscal year is determined by the setup of periods on the **Fiscal calendars** page.</span></span> 

<span data-ttu-id="41be2-134">Ha bejelöli **Pénzügyi** értéket az értékcsökkenés éveként, a következő lehetőségek érhetők el az **Időszak-gyakoriság** mezőben:</span><span class="sxs-lookup"><span data-stu-id="41be2-134">When **Fiscal** is selected as the depreciation year, the following options are available in the **Period frequency** field:</span></span>

-   <span data-ttu-id="41be2-135">Az **Éves** esetében az üzleti évre vonatkozó értékcsökkenés teljes összege a pénzügyi év utolsó napján egy összegként lesz feladva.</span><span class="sxs-lookup"><span data-stu-id="41be2-135">**Yearly** posts the total amount of the depreciation that is calculated for the fiscal year as one amount, on the last day of the fiscal year.</span></span>
-   <span data-ttu-id="41be2-136">**Pénzügyi időszak** feladja az értékcsökkenés teljes értékét a pénzügyi évre.</span><span class="sxs-lookup"><span data-stu-id="41be2-136">**Fiscal period** posts the total amount of the depreciation that is calculated for the fiscal year.</span></span> <span data-ttu-id="41be2-137">Ez az összeg azon pénzügyi időszakokba van elszámolva, amelyek a **Pénzügyi naptárak** lapon meg vannak határozva.</span><span class="sxs-lookup"><span data-stu-id="41be2-137">This amount is accrued into the fiscal periods that are defined on the **Fiscal calendars** page.</span></span>

## <a name="example-of-200-reducing-balance-depreciation"></a><span data-ttu-id="41be2-138">Példa a 200% degresszív értékcsökkenésre</span><span class="sxs-lookup"><span data-stu-id="41be2-138">Example of 200% reducing balance depreciation</span></span>

|                                |        |
|--------------------------------|--------|
| <span data-ttu-id="41be2-139">Beszerzési költség</span><span class="sxs-lookup"><span data-stu-id="41be2-139">Acquisition cost</span></span>               | <span data-ttu-id="41be2-140">11 000</span><span class="sxs-lookup"><span data-stu-id="41be2-140">11,000</span></span> |
| <span data-ttu-id="41be2-141">Maradványérték</span><span class="sxs-lookup"><span data-stu-id="41be2-141">Salvage value</span></span>                  | <span data-ttu-id="41be2-142">1 000</span><span class="sxs-lookup"><span data-stu-id="41be2-142">1, 000</span></span> |
| <span data-ttu-id="41be2-143">Értékcsökkenés alapja</span><span class="sxs-lookup"><span data-stu-id="41be2-143">Depreciation base</span></span>              | <span data-ttu-id="41be2-144">10 000</span><span class="sxs-lookup"><span data-stu-id="41be2-144">10,000</span></span> |
| <span data-ttu-id="41be2-145">Élettartam (év)</span><span class="sxs-lookup"><span data-stu-id="41be2-145">Service life years</span></span>             | <span data-ttu-id="41be2-146">5</span><span class="sxs-lookup"><span data-stu-id="41be2-146">5</span></span>      |
| <span data-ttu-id="41be2-147">Éves százalékos értékcsökkenés</span><span class="sxs-lookup"><span data-stu-id="41be2-147">Yearly depreciation percentage</span></span> | <span data-ttu-id="41be2-148">40%</span><span class="sxs-lookup"><span data-stu-id="41be2-148">40%</span></span>    |

<span data-ttu-id="41be2-149">A 200% degresszív értékcsökkenési módszer elosztja a 200 százalékot az élettartam éveivel.</span><span class="sxs-lookup"><span data-stu-id="41be2-149">The 200% reducing balance method divides 200 percent by the service life years.</span></span> <span data-ttu-id="41be2-150">Ez a százalék lesz megszorozva az eszköz nettó könyv szerinti értékével, és így lesz megállapítva az egy évre vonatkozó értékcsökkenési összeg.</span><span class="sxs-lookup"><span data-stu-id="41be2-150">That percentage will be multiplied by the net book value of the asset to determine the depreciation amount for the year.</span></span>

| <span data-ttu-id="41be2-151">Időszak</span><span class="sxs-lookup"><span data-stu-id="41be2-151">Period</span></span> | <span data-ttu-id="41be2-152">Az éves értékcsökkenés-összeg számítása</span><span class="sxs-lookup"><span data-stu-id="41be2-152">Calculation of the yearly depreciation amount</span></span> | <span data-ttu-id="41be2-153">Könyv szerinti érték</span><span class="sxs-lookup"><span data-stu-id="41be2-153">Book value</span></span>             | <span data-ttu-id="41be2-154">Nettó könyv szerinti érték az év végén</span><span class="sxs-lookup"><span data-stu-id="41be2-154">Net book value at the end of the year</span></span> |
|--------|-----------------------------------------------|------------------------|---------------------------------------|
| <span data-ttu-id="41be2-155">1. év</span><span class="sxs-lookup"><span data-stu-id="41be2-155">Year 1</span></span> | <span data-ttu-id="41be2-156">(11 000 – 1 000) × 40% = 4 000</span><span class="sxs-lookup"><span data-stu-id="41be2-156">(11,000 – 1,000) × 40% = 4,000</span></span>                | <span data-ttu-id="41be2-157">11 000 – 4 000 = 7 000</span><span class="sxs-lookup"><span data-stu-id="41be2-157">11,000 – 4,000 = 7,000</span></span> | <span data-ttu-id="41be2-158">11 000 – 1 000 – 4 000 = 6 000</span><span class="sxs-lookup"><span data-stu-id="41be2-158">11,000 – 1,000 – 4,000 = 6,000</span></span>        |
| <span data-ttu-id="41be2-159">2. év</span><span class="sxs-lookup"><span data-stu-id="41be2-159">Year 2</span></span> | <span data-ttu-id="41be2-160">6 000 × 40% = 2 400</span><span class="sxs-lookup"><span data-stu-id="41be2-160">6,000 × 40% = 2,400</span></span>                           | <span data-ttu-id="41be2-161">7 000 – 2 400 = 4 600</span><span class="sxs-lookup"><span data-stu-id="41be2-161">7,000 – 2,400 = 4,600</span></span>  | <span data-ttu-id="41be2-162">6 000 – 2 400 = 3 600</span><span class="sxs-lookup"><span data-stu-id="41be2-162">6,000 – 2,400 = 3,600</span></span>                 |
| <span data-ttu-id="41be2-163">3. év</span><span class="sxs-lookup"><span data-stu-id="41be2-163">Year 3</span></span> | <span data-ttu-id="41be2-164">3 600 × 40% = 1 440</span><span class="sxs-lookup"><span data-stu-id="41be2-164">3,600 × 40% = 1,440</span></span>                           | <span data-ttu-id="41be2-165">4 600 – 1 440 = 3 160</span><span class="sxs-lookup"><span data-stu-id="41be2-165">4,600 – 1,440 = 3,160</span></span>  | <span data-ttu-id="41be2-166">3 600 – 1 440 = 2 160</span><span class="sxs-lookup"><span data-stu-id="41be2-166">3,600 – 1,440 = 2,160</span></span>                 |

> [!NOTE] 
> <span data-ttu-id="41be2-167">Általában amikor az összeg számolása a 200 % degresszív értékcsökkenési módszerrel történik, akkor az érték kisebb lesz, mint amit a lineáris értékcsökkenés módszerrel kapnánk, a hátralévő élettartamra létezik egy átalakítás a lineáris értékcsökkenés módszeréhez.</span><span class="sxs-lookup"><span data-stu-id="41be2-167">Typically, when the amount that is calculated by using the 200% reducing balance depreciation method becomes less than the amount that would be calculated by using the straight line method, there is a conversion to the straight line method for the remaining life.</span></span>



