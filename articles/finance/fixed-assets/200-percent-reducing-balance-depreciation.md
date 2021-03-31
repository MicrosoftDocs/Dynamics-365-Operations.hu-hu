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
ms.custom: 13951
ms.assetid: 69b4e010-7683-4dc2-8a06-6d572f37e903
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b761a14f44be292e9dd21eb580473bd0981d9044
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5230322"
---
# <a name="200-percent-reducing-balance-depreciation"></a><span data-ttu-id="919ed-103">200 százalék degresszív értékcsökkenés</span><span class="sxs-lookup"><span data-stu-id="919ed-103">200 percent reducing balance depreciation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="919ed-104">Ez a cikk a 200 százalékos degresszív értékcsökkenési módszerről nyújt áttekintést.</span><span class="sxs-lookup"><span data-stu-id="919ed-104">This article gives an overview of the 200 percent reducing balance method of depreciation.</span></span>

<span data-ttu-id="919ed-105">Amikor beállít egy tárgyieszköz-értékcsökkenési profilt és kijelöli a **200% degresszív** értéket a **Mód** mezőben az **Értékcsökkenési profilok** lapon, akkor a tárgyi eszközök, amelyek az értékcsökkenési profilokhoz vannak rendelve értékcsökkentve lesznek ugyanazzal százalékos értékkel, ami az egyes értékcsökkenési időszakoknál szerepel.</span><span class="sxs-lookup"><span data-stu-id="919ed-105">When you set up a fixed asset depreciation profile and select **200% reducing balance** in the **Method** field on the **Depreciation profiles** page, fixed assets that are assigned the depreciation profile are depreciated by the same percentage in each depreciation period.</span></span> <span data-ttu-id="919ed-106">A százalék kiszámítása az eszköz élettartama alapján történik.</span><span class="sxs-lookup"><span data-stu-id="919ed-106">The percentage is calculated based on the service life of the asset.</span></span> <span data-ttu-id="919ed-107">Ha például egy eszköz élettartama öt év, akkor a számított százalékos érték 40% lesz (200% ÷ 5).</span><span class="sxs-lookup"><span data-stu-id="919ed-107">For example, if an asset has a service life of five years, the percentage is calculated as 40 percent (200% ÷ 5).</span></span> 

<span data-ttu-id="919ed-108">Ez a módszer duplán degresszív értékcsökkenésként is ismert.</span><span class="sxs-lookup"><span data-stu-id="919ed-108">This method is also known as double declining balance.</span></span>

<span data-ttu-id="919ed-109">200 % degresszív értékcsökkenés beállítása esetén be kell még jelölnie a beállításokat az **Értékcsökkenési év** mezőben és az **Időszak-gyakoriság** mezőben az **Értékcsökkenési profilok** lapon.</span><span class="sxs-lookup"><span data-stu-id="919ed-109">To set up 200% reducing balance depreciation, you must also select options in the **Depreciation year** field and the **Period frequency** field on the **Depreciation profiles** page.</span></span> <span data-ttu-id="919ed-110">Az **Időszak-gyakoriság** mezőben rendelkezésre álló beállítások eltérőek lehetnek, az **Értékcsökkenési év** mezőben kijelölt értéktől függően.</span><span class="sxs-lookup"><span data-stu-id="919ed-110">The options that are available in the **Period frequency** field vary, depending on the value that you select in the **Depreciation year** field.</span></span>

## <a name="select-a-depreciation-year"></a><span data-ttu-id="919ed-111">Az értékcsökkenési év kiválasztása</span><span class="sxs-lookup"><span data-stu-id="919ed-111">Select a depreciation year</span></span>
<span data-ttu-id="919ed-112">Kiválaszthatja a **Naptár** vagy **Pénzügyi** elemeket az **Értékcsökkenési év** mezőben az **Értékcsökkenési profilok** lapon.</span><span class="sxs-lookup"><span data-stu-id="919ed-112">You can select either **Calendar** or **Fiscal** in the **Depreciation year** field on the **Depreciation profiles** page.</span></span> <span data-ttu-id="919ed-113">Az alapértelmezett érték **Naptár**.</span><span class="sxs-lookup"><span data-stu-id="919ed-113">The default value is **Calendar**.</span></span> 

<span data-ttu-id="919ed-114">A kiválasztás függvényében változnak az **Időszak gyakorisága** mezőben elérhető beállítások.</span><span class="sxs-lookup"><span data-stu-id="919ed-114">Your selection determines the options that are available in the **Period frequency** field.</span></span> <span data-ttu-id="919ed-115">Ez a mező meghatározza a az értékcsökkenés könyvelésének feladási időpontját és összegét a naptári év során.</span><span class="sxs-lookup"><span data-stu-id="919ed-115">This field defines the depreciation accrual posting dates and amounts throughout the calendar year.</span></span>

### <a name="calendar"></a><span data-ttu-id="919ed-116">Naptár</span><span class="sxs-lookup"><span data-stu-id="919ed-116">Calendar</span></span>

<span data-ttu-id="919ed-117">Megtarthatja az alapértelmezett értéket az **Értékcsökkenési év** mezőben, **Naptár**.</span><span class="sxs-lookup"><span data-stu-id="919ed-117">You can keep the default value in the **Depreciation year** field, **Calendar**.</span></span> 

<span data-ttu-id="919ed-118">A **naptár** lehetőség választása esetén az értékcsökkenés alapja minden évben január 1-jén frissül.</span><span class="sxs-lookup"><span data-stu-id="919ed-118">The **Calendar** option updates the depreciation base on January 1 of each year.</span></span> <span data-ttu-id="919ed-119">Jellemzően az értékcsökkenés a nettó könyv szerinti érték mínusz a maradványérték.</span><span class="sxs-lookup"><span data-stu-id="919ed-119">Typically, the depreciation is the net book value minus the scrap value.</span></span> <span data-ttu-id="919ed-120">Az ebben a témában szereplő későbbi példákban az értékcsökkenés alapja a számítások oszlop első kifejezésében szereplő számláló.</span><span class="sxs-lookup"><span data-stu-id="919ed-120">In the examples later in this topic, the depreciation base is the numerator in the first expression in the calculations column.</span></span> 

<span data-ttu-id="919ed-121">Ha bejelöli **Naptár** értéket az értékcsökkenés éveként a következő lehetőségek érhetők el az **Időszak-gyakoriság** mezőben:</span><span class="sxs-lookup"><span data-stu-id="919ed-121">If you select **Calendar** as the depreciation year, the following options are available in the **Period frequency** field:</span></span>

-   <span data-ttu-id="919ed-122">**Éves** felad egy összeget december 31-én.</span><span class="sxs-lookup"><span data-stu-id="919ed-122">**Yearly** posts an amount on December 31.</span></span>
-   <span data-ttu-id="919ed-123">**Havi**: felad egy havi összeget minden naptári hó végén.</span><span class="sxs-lookup"><span data-stu-id="919ed-123">**Monthly** posts a monthly amount at the end of each calendar month.</span></span>
-   <span data-ttu-id="919ed-124">**Negyedéves**:Felad egy negyedéves összeget minden naptári negyedév végén (március 31., június 30., szeptember 30. és december 31.).</span><span class="sxs-lookup"><span data-stu-id="919ed-124">**Quarterly** posts a quarterly amount at the end of each calendar quarter (March 31, June 30, September 30, and December 31).</span></span>
-   <span data-ttu-id="919ed-125">**Féléves**: felad egy féléves összeget minden naptári félév végén (június 30. és december 31.).</span><span class="sxs-lookup"><span data-stu-id="919ed-125">**Half-Yearly** posts a half-yearly amount at the calendar half year (June 30 and December 31).</span></span>
-   <span data-ttu-id="919ed-126">**Napi** Feladja az értékcsökkenési összeget a napi értékcsökkenési módhoz úgy, hogy minden naphoz egy tranzakciót használ.</span><span class="sxs-lookup"><span data-stu-id="919ed-126">**Daily** posts the depreciation amount for the daily depreciation method by using one transaction for each day.</span></span>

### <a name="fiscal"></a><span data-ttu-id="919ed-127">Pénzügyi</span><span class="sxs-lookup"><span data-stu-id="919ed-127">Fiscal</span></span>

<span data-ttu-id="919ed-128">Ha bejelöli a **Pénzügyi** lehetőséget az **Értékcsökkenési** év mezőben, akkor a 200 % degresszív értékcsökkenés számítása azon pénzügyi év szerint történik, amelynek pénzügyi naptára meg van adva a könyvben vagy amelyik pénzügyi naptár ki van jelölve a **Főkönyv** lapon.</span><span class="sxs-lookup"><span data-stu-id="919ed-128">If you select **Fiscal** in the **Depreciation** year field, 200% reducing balance depreciation is calculated based on the fiscal year for the fiscal calendar that is specified for the book, or for the fiscal calendar that is selected on the **Ledger** page.</span></span> <span data-ttu-id="919ed-129">A pénzügyi naptárak a **Pénzügyi naptárak** oldalon állíthatóak be.</span><span class="sxs-lookup"><span data-stu-id="919ed-129">Fiscal calendars are set up on the **Fiscal calendars** page.</span></span> 

<span data-ttu-id="919ed-130">Egy július 1-től június 30-ig tartó pénzügyi év esetén az értékcsökkenés számítása július 1-jén kezdődik.</span><span class="sxs-lookup"><span data-stu-id="919ed-130">For example, for the fiscal year July 1 through June 30, the depreciation calculation starts on July 1.</span></span> <span data-ttu-id="919ed-131">Az üzleti év 12 hónapnál hosszabb vagy rövidebb is lehet.</span><span class="sxs-lookup"><span data-stu-id="919ed-131">The fiscal year can be longer or shorter than 12 months.</span></span> <span data-ttu-id="919ed-132">Az értékcsökkenés minden időszakhoz helyesbítve van.</span><span class="sxs-lookup"><span data-stu-id="919ed-132">The depreciation is adjusted for each period.</span></span> <span data-ttu-id="919ed-133">A következő üzleti év hossza az időszakok beállítása alapján van meghatározva a **Pénzügyi naptárak** oldalon.</span><span class="sxs-lookup"><span data-stu-id="919ed-133">The length of the next fiscal year is determined by the setup of periods on the **Fiscal calendars** page.</span></span> 

<span data-ttu-id="919ed-134">Ha bejelöli **Pénzügyi** értéket az értékcsökkenés éveként, a következő lehetőségek érhetők el az **Időszak-gyakoriság** mezőben:</span><span class="sxs-lookup"><span data-stu-id="919ed-134">When **Fiscal** is selected as the depreciation year, the following options are available in the **Period frequency** field:</span></span>

-   <span data-ttu-id="919ed-135">Az **Éves** esetében az üzleti évre vonatkozó értékcsökkenés teljes összege a pénzügyi év utolsó napján egy összegként lesz feladva.</span><span class="sxs-lookup"><span data-stu-id="919ed-135">**Yearly** posts the total amount of the depreciation that is calculated for the fiscal year as one amount, on the last day of the fiscal year.</span></span>
-   <span data-ttu-id="919ed-136">**Pénzügyi időszak** feladja az értékcsökkenés teljes értékét a pénzügyi évre.</span><span class="sxs-lookup"><span data-stu-id="919ed-136">**Fiscal period** posts the total amount of the depreciation that is calculated for the fiscal year.</span></span> <span data-ttu-id="919ed-137">Ez az összeg azon pénzügyi időszakokba van elszámolva, amelyek a **Pénzügyi naptárak** lapon meg vannak határozva.</span><span class="sxs-lookup"><span data-stu-id="919ed-137">This amount is accrued into the fiscal periods that are defined on the **Fiscal calendars** page.</span></span>

## <a name="example-of-200-reducing-balance-depreciation"></a><span data-ttu-id="919ed-138">Példa a 200% degresszív értékcsökkenésre</span><span class="sxs-lookup"><span data-stu-id="919ed-138">Example of 200% reducing balance depreciation</span></span>

|                                |        |
|--------------------------------|--------|
| <span data-ttu-id="919ed-139">Beszerzési költség</span><span class="sxs-lookup"><span data-stu-id="919ed-139">Acquisition cost</span></span>               | <span data-ttu-id="919ed-140">11 000</span><span class="sxs-lookup"><span data-stu-id="919ed-140">11,000</span></span> |
| <span data-ttu-id="919ed-141">Maradványérték</span><span class="sxs-lookup"><span data-stu-id="919ed-141">Salvage value</span></span>                  | <span data-ttu-id="919ed-142">1 000</span><span class="sxs-lookup"><span data-stu-id="919ed-142">1, 000</span></span> |
| <span data-ttu-id="919ed-143">Értékcsökkenés alapja</span><span class="sxs-lookup"><span data-stu-id="919ed-143">Depreciation base</span></span>              | <span data-ttu-id="919ed-144">10 000</span><span class="sxs-lookup"><span data-stu-id="919ed-144">10,000</span></span> |
| <span data-ttu-id="919ed-145">Élettartam (év)</span><span class="sxs-lookup"><span data-stu-id="919ed-145">Service life years</span></span>             | <span data-ttu-id="919ed-146">5</span><span class="sxs-lookup"><span data-stu-id="919ed-146">5</span></span>      |
| <span data-ttu-id="919ed-147">Éves százalékos értékcsökkenés</span><span class="sxs-lookup"><span data-stu-id="919ed-147">Yearly depreciation percentage</span></span> | <span data-ttu-id="919ed-148">40%</span><span class="sxs-lookup"><span data-stu-id="919ed-148">40%</span></span>    |

<span data-ttu-id="919ed-149">A 200% degresszív értékcsökkenési módszer elosztja a 200 százalékot az élettartam éveivel.</span><span class="sxs-lookup"><span data-stu-id="919ed-149">The 200% reducing balance method divides 200 percent by the service life years.</span></span> <span data-ttu-id="919ed-150">Ez a százalék lesz megszorozva az eszköz nettó könyv szerinti értékével, és így lesz megállapítva az egy évre vonatkozó értékcsökkenési összeg.</span><span class="sxs-lookup"><span data-stu-id="919ed-150">That percentage will be multiplied by the net book value of the asset to determine the depreciation amount for the year.</span></span>

| <span data-ttu-id="919ed-151">Időszak</span><span class="sxs-lookup"><span data-stu-id="919ed-151">Period</span></span> | <span data-ttu-id="919ed-152">Az éves értékcsökkenés-összeg számítása</span><span class="sxs-lookup"><span data-stu-id="919ed-152">Calculation of the yearly depreciation amount</span></span> | <span data-ttu-id="919ed-153">Könyv szerinti érték</span><span class="sxs-lookup"><span data-stu-id="919ed-153">Book value</span></span>             | <span data-ttu-id="919ed-154">Nettó könyv szerinti érték az év végén</span><span class="sxs-lookup"><span data-stu-id="919ed-154">Net book value at the end of the year</span></span> |
|--------|-----------------------------------------------|------------------------|---------------------------------------|
| <span data-ttu-id="919ed-155">1. év</span><span class="sxs-lookup"><span data-stu-id="919ed-155">Year 1</span></span> | <span data-ttu-id="919ed-156">(11 000 – 1000) × 40% = 4000</span><span class="sxs-lookup"><span data-stu-id="919ed-156">(11,000 – 1,000) × 40% = 4,000</span></span>                | <span data-ttu-id="919ed-157">11 000 – 4000 = 7000</span><span class="sxs-lookup"><span data-stu-id="919ed-157">11,000 – 4,000 = 7,000</span></span> | <span data-ttu-id="919ed-158">11 000 – 1000 – 4000 = 6000</span><span class="sxs-lookup"><span data-stu-id="919ed-158">11,000 – 1,000 – 4,000 = 6,000</span></span>        |
| <span data-ttu-id="919ed-159">2. év</span><span class="sxs-lookup"><span data-stu-id="919ed-159">Year 2</span></span> | <span data-ttu-id="919ed-160">6000 × 40% = 2400</span><span class="sxs-lookup"><span data-stu-id="919ed-160">6,000 × 40% = 2,400</span></span>                           | <span data-ttu-id="919ed-161">7000 – 2400 = 4600</span><span class="sxs-lookup"><span data-stu-id="919ed-161">7,000 – 2,400 = 4,600</span></span>  | <span data-ttu-id="919ed-162">6000 – 2400 = 3600</span><span class="sxs-lookup"><span data-stu-id="919ed-162">6,000 – 2,400 = 3,600</span></span>                 |
| <span data-ttu-id="919ed-163">3. év</span><span class="sxs-lookup"><span data-stu-id="919ed-163">Year 3</span></span> | <span data-ttu-id="919ed-164">3600 × 40% = 1440</span><span class="sxs-lookup"><span data-stu-id="919ed-164">3,600 × 40% = 1,440</span></span>                           | <span data-ttu-id="919ed-165">4600 – 1440 = 3160</span><span class="sxs-lookup"><span data-stu-id="919ed-165">4,600 – 1,440 = 3,160</span></span>  | <span data-ttu-id="919ed-166">3600 – 1440 = 2160</span><span class="sxs-lookup"><span data-stu-id="919ed-166">3,600 – 1,440 = 2,160</span></span>                 |

> [!NOTE] 
> <span data-ttu-id="919ed-167">Általában amikor az összeg számolása a 200 % degresszív értékcsökkenési módszerrel történik, akkor az érték kisebb lesz mint amit a lineáris értékcsökkenés módszerrel kapnánk, a hátralévő élettartamhoz létezik egy átalakítás a lineáris értékcsökkenés módszeréhez.</span><span class="sxs-lookup"><span data-stu-id="919ed-167">Typically, when the amount that is calculated by using the 200% reducing balance depreciation method becomes less than the amount that would be calculated by using the straight line method, there is a conversion to the straight line method for the remaining life.</span></span>





[!INCLUDE[footer-include](../../includes/footer-banner.md)]