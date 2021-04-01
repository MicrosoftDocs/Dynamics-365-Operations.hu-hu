---
title: 150 százalék degresszív értékcsökkenés
description: Ez a cikk a 150 százalékos degresszív értékcsökkenési módszerről nyújt áttekintést.
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
ms.custom: 13891
ms.assetid: 36d1112d-921c-4fff-abe0-0ff2429848d3
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4edc868b76d466c41be8036b962730db90eeb68a
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5249437"
---
# <a name="150-percent-reducing-balance-depreciation"></a><span data-ttu-id="41819-103">150 százalék degresszív értékcsökkenés</span><span class="sxs-lookup"><span data-stu-id="41819-103">150 percent reducing balance depreciation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="41819-104">Ez a cikk a 150 százalékos degresszív értékcsökkenési módszerről nyújt áttekintést.</span><span class="sxs-lookup"><span data-stu-id="41819-104">This article gives an overview of the 150 percent reducing balance method of depreciation.</span></span>

<span data-ttu-id="41819-105">Amikor beállít egy tárgyieszköz-értékcsökkenési profilt és kijelöli a **150% degresszív** értéket a **Mód** mezőben az **Értékcsökkenési profilok** lapon, akkor a tárgyi eszközök, amelyek az értékcsökkenési profilokhoz vannak rendelve értékcsökkenése ugyanazzal százalékos értékkel lesz egyenlő, ami az egyes értékcsökkenési időszakoknál szerepel.</span><span class="sxs-lookup"><span data-stu-id="41819-105">When you set up a fixed asset depreciation profile and select **150% reducing balance** in the **Method** field on the **Depreciation profiles** page, fixed assets that are assigned the depreciation profile are depreciated by the same percentage in each depreciation period.</span></span> <span data-ttu-id="41819-106">A százalék kiszámítása az eszköz élettartama alapján történik.</span><span class="sxs-lookup"><span data-stu-id="41819-106">This percentage is calculated based on the service life of the asset.</span></span> <span data-ttu-id="41819-107">Ha például egy eszköz élettartama öt év, akkor a számított százalékos érték 30% lesz (150% ÷ 5).</span><span class="sxs-lookup"><span data-stu-id="41819-107">For example, if an asset has a service life of five years, the percentage is calculated as 30 percent (150% ÷ 5).</span></span> 

<span data-ttu-id="41819-108">150 % degresszív értékcsökkenés beállítása esetén be kell még jelölnie a beállításokat az **Értékcsökkenési év** mezőben és az **Időszak-gyakoriság** mezőben az **Értékcsökkenési profilok** lapon.</span><span class="sxs-lookup"><span data-stu-id="41819-108">To set up 150% reducing balance depreciation, you must also select options in the **Depreciation year** field and the **Period frequency** field on the **Depreciation profiles** page.</span></span> <span data-ttu-id="41819-109">Az **Időszak-gyakoriság** mezőben rendelkezésre álló beállítások eltérőek lehetnek, az **Értékcsökkenési év** mezőben kijelölt értéktől függően.</span><span class="sxs-lookup"><span data-stu-id="41819-109">The options that are available in the **Period frequency** field vary, depending on the value that is selected in the **Depreciation year** field.</span></span>

## <a name="selection-of-depreciation-year"></a><span data-ttu-id="41819-110">Az értékcsökkenési év kiválasztása</span><span class="sxs-lookup"><span data-stu-id="41819-110">Selection of depreciation year</span></span>
<span data-ttu-id="41819-111">Kiválaszthatja a **Naptár** vagy **Pénzügyi** elemeket az **Értékcsökkenési év** mezőben az **Értékcsökkenési profilok** lapon.</span><span class="sxs-lookup"><span data-stu-id="41819-111">You can select either **Calendar** or **Fiscal** in the **Depreciation year** field on the **Depreciation profiles** page.</span></span> 

<span data-ttu-id="41819-112">Az alapértelmezett érték **Naptár**.</span><span class="sxs-lookup"><span data-stu-id="41819-112">The default value is **Calendar**.</span></span> <span data-ttu-id="41819-113">A kiválasztás függvényében változnak az **Időszak gyakorisága** mezőben elérhető beállítások.</span><span class="sxs-lookup"><span data-stu-id="41819-113">Your selection determines the options that are available in the **Period frequency** field.</span></span> <span data-ttu-id="41819-114">Ez a mező meghatározza a az értékcsökkenés könyvelésének feladási időpontját és összegét a naptári év során.</span><span class="sxs-lookup"><span data-stu-id="41819-114">This field defines the depreciation accrual posting dates and amounts throughout the calendar year.</span></span>

### <a name="calendar"></a><span data-ttu-id="41819-115">Naptár</span><span class="sxs-lookup"><span data-stu-id="41819-115">Calendar</span></span>

<span data-ttu-id="41819-116">Megtarthatja az alapértelmezett értéket az **Értékcsökkenési év** mezőben, **Naptár**.</span><span class="sxs-lookup"><span data-stu-id="41819-116">You can keep the default value in the **Depreciation year** field, **Calendar**.</span></span> 

<span data-ttu-id="41819-117">A **naptár** lehetőség választása esetén az értékcsökkenés alapja minden évben január 1-jén frissül.</span><span class="sxs-lookup"><span data-stu-id="41819-117">The **Calendar** option updates the depreciation base on January 1 of each year.</span></span> <span data-ttu-id="41819-118">Jellemzően az értékcsökkenés alapja a nettó könyv szerinti érték mínusz a maradványérték.</span><span class="sxs-lookup"><span data-stu-id="41819-118">Typically, the depreciation base is the net book value minus the scrap value.</span></span> <span data-ttu-id="41819-119">Az ebben a témában szereplő későbbi példákban az értékcsökkenés alapja a számítások oszlop első kifejezésében szereplő számláló.</span><span class="sxs-lookup"><span data-stu-id="41819-119">In the examples later in this topic, the depreciation base is the numerator in the first expression in the calculations column.</span></span> 

<span data-ttu-id="41819-120">Ha bejelöli **Naptár** értéket az értékcsökkenés éveként a következő lehetőségek érhetők el az **Időszak-gyakoriság** mezőben:</span><span class="sxs-lookup"><span data-stu-id="41819-120">If you select **Calendar** as the depreciation year, the following options are available in the **Period frequency** field:</span></span>

-   <span data-ttu-id="41819-121">**Éves** felad egy összeget december 31-én.</span><span class="sxs-lookup"><span data-stu-id="41819-121">**Yearly** posts an amount on December 31.</span></span>
-   <span data-ttu-id="41819-122">**Havi**: felad egy havi összeget minden naptári hó végén.</span><span class="sxs-lookup"><span data-stu-id="41819-122">**Monthly** posts a monthly amount at the end of each calendar month.</span></span>
-   <span data-ttu-id="41819-123">**Negyedéves**:Felad egy negyedéves összeget minden naptári negyedév végén (március 31., június 30., szeptember 30. és december 31.).</span><span class="sxs-lookup"><span data-stu-id="41819-123">**Quarterly** posts a quarterly amount at the end of each calendar quarter (March 31, June 30, September 30, and December 31).</span></span>
-   <span data-ttu-id="41819-124">**Féléves**: felad egy féléves összeget minden naptári félév végén (június 30. és december 31.).</span><span class="sxs-lookup"><span data-stu-id="41819-124">**Half-Yearly** posts a half-yearly amount at the calendar half year (June 30 and December 31).</span></span>
-   <span data-ttu-id="41819-125">**Napi** Feladja az értékcsökkenési összeget a napi értékcsökkenési módhoz úgy, hogy minden naphoz egy tranzakciót használ.</span><span class="sxs-lookup"><span data-stu-id="41819-125">**Daily** posts the depreciation amount for the daily depreciation method by using one transaction for each day.</span></span>

### <a name="fiscal"></a><span data-ttu-id="41819-126">Pénzügyi</span><span class="sxs-lookup"><span data-stu-id="41819-126">Fiscal</span></span>

<span data-ttu-id="41819-127">Ha bejelöli a **Pénzügyi** lehetőséget az **Értékcsökkenési év** mezőben, akkor a 150 % degresszív értékcsökkenés számítása azon pénzügyi év szerint történik, amelynek pénzügyi naptára meg van adva a könyvben vagy amelyik pénzügyi naptár ki van jelölve a **Főkönyv** lapon.</span><span class="sxs-lookup"><span data-stu-id="41819-127">If you select **Fiscal** in the **Depreciation year** field, 150% reducing balance depreciation is calculated based on the fiscal year for the fiscal calendar that is specified for the book, or for the fiscal calendar that is selected on the **Ledger** page.</span></span> <span data-ttu-id="41819-128">A pénzügyi naptárak a **Pénzügyi naptárak** oldalon állíthatóak be.</span><span class="sxs-lookup"><span data-stu-id="41819-128">Fiscal calendars are set up on the **Fiscal calendars** page.</span></span> 

<span data-ttu-id="41819-129">Egy július 1-től június 30-ig tartó pénzügyi év esetén az értékcsökkenés számítása július 1-jén kezdődik.</span><span class="sxs-lookup"><span data-stu-id="41819-129">For example, for the fiscal year July 1 through June 30, the depreciation calculation starts on July 1.</span></span> <span data-ttu-id="41819-130">Az üzleti év 12 hónapnál hosszabb vagy rövidebb is lehet.</span><span class="sxs-lookup"><span data-stu-id="41819-130">The fiscal year can be longer or shorter than 12 months.</span></span> <span data-ttu-id="41819-131">Az értékcsökkenés minden időszakhoz helyesbítve van.</span><span class="sxs-lookup"><span data-stu-id="41819-131">The depreciation is adjusted for each period.</span></span> <span data-ttu-id="41819-132">A következő üzleti év hossza az időszakok beállítása alapján van meghatározva a **Pénzügyi naptárak** oldalon.</span><span class="sxs-lookup"><span data-stu-id="41819-132">The length of the next fiscal year is determined by the setup of periods on the **Fiscal calendars** page.</span></span> 

<span data-ttu-id="41819-133">Ha bejelöli **Pénzügyi** értéket az értékcsökkenés éveként a következő lehetőségek érhetők el az **Időszak-gyakoriság** mezőben:</span><span class="sxs-lookup"><span data-stu-id="41819-133">If you select **Fiscal** as the depreciation year, the following options are available in the **Period frequency** field:</span></span>

-   <span data-ttu-id="41819-134">**Éves**: Feladja az értékcsökkenés teles összegét, aminek számítása a pénzügyi évre történik, annak utolsó napján.</span><span class="sxs-lookup"><span data-stu-id="41819-134">**Yearly** posts the total amount of the depreciation that is calculated for the fiscal year on the last day of the fiscal year.</span></span>
-   <span data-ttu-id="41819-135">**Pénzügyi időszak** feladja az értékcsökkenés teljes értékét a pénzügyi évre.</span><span class="sxs-lookup"><span data-stu-id="41819-135">**Fiscal period** posts the total amount of the depreciation that is calculated for the fiscal year.</span></span> <span data-ttu-id="41819-136">Ez az összeg azon pénzügyi időszakokba van elszámolva, amelyek a **Pénzügyi naptárak** lapon meg vannak határozva.</span><span class="sxs-lookup"><span data-stu-id="41819-136">This amount is accrued into the fiscal periods that are defined on the **Fiscal calendars** page.</span></span>

## <a name="example-of-150-reducing-balance-depreciation"></a><span data-ttu-id="41819-137">Példa a 150% degresszív értékcsökkenésre</span><span class="sxs-lookup"><span data-stu-id="41819-137">Example of 150% reducing balance depreciation</span></span>

|                                |        |
|--------------------------------|--------|
| <span data-ttu-id="41819-138">Beszerzési költség</span><span class="sxs-lookup"><span data-stu-id="41819-138">Acquisition cost</span></span>               | <span data-ttu-id="41819-139">11 000</span><span class="sxs-lookup"><span data-stu-id="41819-139">11,000</span></span> |
| <span data-ttu-id="41819-140">Maradványérték</span><span class="sxs-lookup"><span data-stu-id="41819-140">Salvage value</span></span>                  | <span data-ttu-id="41819-141">1000</span><span class="sxs-lookup"><span data-stu-id="41819-141">1,000</span></span>  |
| <span data-ttu-id="41819-142">Értékcsökkenés alapja</span><span class="sxs-lookup"><span data-stu-id="41819-142">Depreciation base</span></span>              | <span data-ttu-id="41819-143">10 000</span><span class="sxs-lookup"><span data-stu-id="41819-143">10,000</span></span> |
| <span data-ttu-id="41819-144">Élettartam (év)</span><span class="sxs-lookup"><span data-stu-id="41819-144">Service life years</span></span>             | <span data-ttu-id="41819-145">5</span><span class="sxs-lookup"><span data-stu-id="41819-145">5</span></span>      |
| <span data-ttu-id="41819-146">Éves százalékos értékcsökkenés</span><span class="sxs-lookup"><span data-stu-id="41819-146">Yearly depreciation percentage</span></span> | <span data-ttu-id="41819-147">30%</span><span class="sxs-lookup"><span data-stu-id="41819-147">30%</span></span>    |

<span data-ttu-id="41819-148">A 150% degresszív értékcsökkenési módszer elosztja a 150 százalékot az élettartam éveivel.</span><span class="sxs-lookup"><span data-stu-id="41819-148">The 150% reducing balance method divides 150 percent by the service life years.</span></span> <span data-ttu-id="41819-149">Ez a százalék lesz megszorozva az eszköz nettó könyv szerinti értékével, és így lesz megállapítva az egy évre vonatkozó értékcsökkenési összeg.</span><span class="sxs-lookup"><span data-stu-id="41819-149">That percentage will be multiplied by the net book value of the asset to determine the depreciation amount for the year.</span></span>

| <span data-ttu-id="41819-150">Időszak</span><span class="sxs-lookup"><span data-stu-id="41819-150">Period</span></span> | <span data-ttu-id="41819-151">Az éves értékcsökkenés-összeg számítása</span><span class="sxs-lookup"><span data-stu-id="41819-151">Calculation of the yearly depreciation amount</span></span> | <span data-ttu-id="41819-152">Könyv szerinti érték</span><span class="sxs-lookup"><span data-stu-id="41819-152">Book value</span></span>             | <span data-ttu-id="41819-153">Nettó könyv szerinti érték az év végén</span><span class="sxs-lookup"><span data-stu-id="41819-153">Net book value at the end of the year</span></span> |
|--------|-----------------------------------------------|------------------------|---------------------------------------|
| <span data-ttu-id="41819-154">1. év</span><span class="sxs-lookup"><span data-stu-id="41819-154">Year 1</span></span> | <span data-ttu-id="41819-155">(11 000-1 000) × 30% = 3 000</span><span class="sxs-lookup"><span data-stu-id="41819-155">(11,000 – 1,000) × 30% = 3,000</span></span>                | <span data-ttu-id="41819-156">11 000 - 3 000 = 8 000</span><span class="sxs-lookup"><span data-stu-id="41819-156">11,000 – 3,000 = 8,000</span></span> | <span data-ttu-id="41819-157">11 000 - 1 000 - 3 000 = 7 000</span><span class="sxs-lookup"><span data-stu-id="41819-157">11,000 – 1,000 – 3,000 = 7,000</span></span>        |
| <span data-ttu-id="41819-158">2. év</span><span class="sxs-lookup"><span data-stu-id="41819-158">Year 2</span></span> | <span data-ttu-id="41819-159">7 000 × 30% = 2 100</span><span class="sxs-lookup"><span data-stu-id="41819-159">7,000 × 30% = 2,100</span></span>                           | <span data-ttu-id="41819-160">8 000 - 2 100 = 5 900</span><span class="sxs-lookup"><span data-stu-id="41819-160">8,000 – 2,100 = 5,900</span></span>  | <span data-ttu-id="41819-161">7 000 - 2 100 = 4 900</span><span class="sxs-lookup"><span data-stu-id="41819-161">7,000 – 2,100 = 4,900</span></span>                 |
| <span data-ttu-id="41819-162">3. év</span><span class="sxs-lookup"><span data-stu-id="41819-162">Year 3</span></span> | <span data-ttu-id="41819-163">4 900 × 30% = 1 470</span><span class="sxs-lookup"><span data-stu-id="41819-163">4,900 × 30% = 1,470</span></span>                           | <span data-ttu-id="41819-164">5 900 - 1 470 = 4 430</span><span class="sxs-lookup"><span data-stu-id="41819-164">5,900 – 1,470 = 4,430</span></span>  | <span data-ttu-id="41819-165">4 900 - 1 470 = 3 430</span><span class="sxs-lookup"><span data-stu-id="41819-165">4,900 – 1,470 = 3,430</span></span>                 |

> [!NOTE]
> <span data-ttu-id="41819-166">Általában amikor az összeg számolása a 150 % degresszív értékcsökkenési módszerrel történik, akkor az érték kisebb lesz mint amit a lineáris értékcsökkenés módszerrel kapnánk, a hátralévő élettartamhoz létezik egy átalakítás a lineáris értékcsökkenés módszeréhez.</span><span class="sxs-lookup"><span data-stu-id="41819-166">Typically, when the amount that is calculated by using the 150% reducing balance depreciation method becomes less than the amount that would be calculated by using the straight line method, there is a conversion to the straight line method for the remaining life.</span></span>





[!INCLUDE[footer-include](../../includes/footer-banner.md)]