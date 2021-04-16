---
title: 125 százalékos degresszív értékcsökkenés
description: Ez a cikk a 125 százalékos degresszív értékcsökkenési módszerről nyújt áttekintést.
author: saraschi2
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: roschlom
ms.custom: 13871
ms.assetid: 3abc263e-59d6-4f1a-986d-1be388948bd3
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e1d05ec02d47a563c0d7ae7cb0fafdbad45bd140
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5827194"
---
# <a name="125-percent-reducing-balance-depreciation"></a><span data-ttu-id="1809b-103">125 százalékos degresszív értékcsökkenés</span><span class="sxs-lookup"><span data-stu-id="1809b-103">125 percent reducing balance depreciation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1809b-104">Ez a cikk a 125 százalékos degresszív értékcsökkenési módszerről nyújt áttekintést.</span><span class="sxs-lookup"><span data-stu-id="1809b-104">This article gives an overview of the 125 percent reducing balance method of depreciation.</span></span>

<span data-ttu-id="1809b-105">Amikor beállít egy tárgyieszköz-értékcsökkenési profilt a **125% degresszív** értéket választja a **Mód** mezőben az **Értékcsökkenési profilok** lapon, akkor a tárgyi eszközök, amelyek az értékcsökkenési profilokhoz vannak rendelve értékcsökkenése ugyanazzal százalékos értékkel lesz egyenlő, ami az egyes értékcsökkenési időszakoknál szerepel.</span><span class="sxs-lookup"><span data-stu-id="1809b-105">When you set up a fixed asset depreciation profile and select **125% reducing balance** in the **Method** field on the **Depreciation profiles** page, fixed assets that are assigned to the depreciation profile are depreciated by the same percentage in each depreciation period.</span></span> <span data-ttu-id="1809b-106">A százalék kiszámítása az eszköz élettartama alapján történik.</span><span class="sxs-lookup"><span data-stu-id="1809b-106">This percentage is calculated based on the service life of the asset.</span></span> <span data-ttu-id="1809b-107">Ha például egy eszköz élettartama öt év, akkor a számított százalékos érték 25% lesz (125% ÷ 5).</span><span class="sxs-lookup"><span data-stu-id="1809b-107">For example, if an asset has a service life of five years, the percentage is calculated as 25 percent (125% ÷ 5).</span></span>

<span data-ttu-id="1809b-108">125 % degresszív értékcsökkenés beállítása esetén be kell még jelölnie a beállításokat az **Értékcsökkenési év** mezőben és az **Időszak-gyakoriság** mezőben az **Értékcsökkenési profilok** lapon.</span><span class="sxs-lookup"><span data-stu-id="1809b-108">To set up 125% reducing balance depreciation, you must also select options in the **Depreciation year** field and the **Period frequency** field on the **Depreciation profiles** page.</span></span> <span data-ttu-id="1809b-109">Az **Időszak-gyakoriság** mezőben rendelkezésre álló beállítások eltérőek lehetnek, az **Értékcsökkenési év** mezőben kijelölt értéktől függően.</span><span class="sxs-lookup"><span data-stu-id="1809b-109">The options that are available in the **Period frequency** field vary, depending on the value that is selected in the **Depreciation year** field.</span></span>

## <a name="select-a-depreciation-year"></a><span data-ttu-id="1809b-110">Az értékcsökkenési év kiválasztása</span><span class="sxs-lookup"><span data-stu-id="1809b-110">Select a depreciation year</span></span>
<span data-ttu-id="1809b-111">Kiválaszthatja a **Naptár** vagy **Pénzügyi** elemeket az **Értékcsökkenési év** mezőben az **Értékcsökkenési profilok** lapon.</span><span class="sxs-lookup"><span data-stu-id="1809b-111">You can select either **Calendar** or **Fiscal** in the **Depreciation year** field on the **Depreciation profiles** page.</span></span> <span data-ttu-id="1809b-112">Az alapértelmezett érték **Naptár**.</span><span class="sxs-lookup"><span data-stu-id="1809b-112">The default value is **Calendar**.</span></span> 

<span data-ttu-id="1809b-113">A kiválasztás függvényében változnak az **Időszak gyakorisága** mezőben elérhető beállítások.</span><span class="sxs-lookup"><span data-stu-id="1809b-113">Your selection determines the options that are available in the **Period frequency** field.</span></span> <span data-ttu-id="1809b-114">Ez a mező meghatározza a az értékcsökkenés könyvelésének feladási időpontját és összegét a naptári év során.</span><span class="sxs-lookup"><span data-stu-id="1809b-114">This field defines the depreciation accrual posting dates and amounts throughout the calendar year.</span></span>

### <a name="calendar"></a><span data-ttu-id="1809b-115">Naptár</span><span class="sxs-lookup"><span data-stu-id="1809b-115">Calendar</span></span>

<span data-ttu-id="1809b-116">Megtarthatja az alapértelmezett értéket az **Értékcsökkenési év** mezőben, **Naptár**.</span><span class="sxs-lookup"><span data-stu-id="1809b-116">You can keep the default value in the **Depreciation year** field, **Calendar**.</span></span> 

<span data-ttu-id="1809b-117">A **naptár** lehetőség választása esetén az értékcsökkenés alapja minden évben január 1-jén frissül.</span><span class="sxs-lookup"><span data-stu-id="1809b-117">The **Calendar** option updates the depreciation base on January 1 of each year.</span></span> <span data-ttu-id="1809b-118">Jellemzően az értékcsökkenés alapja a nettó könyv szerinti érték mínusz a maradványérték.</span><span class="sxs-lookup"><span data-stu-id="1809b-118">Typically, the depreciation base is the net book value minus the scrap value.</span></span> <span data-ttu-id="1809b-119">Az ebben a témában szereplő későbbi példákban az értékcsökkenés alapja a számítások oszlop első kifejezésében szereplő számláló.</span><span class="sxs-lookup"><span data-stu-id="1809b-119">In the examples later in this topic, the depreciation base is the numerator in the first expression in the calculations column.</span></span> 

<span data-ttu-id="1809b-120">Ha bejelöli **Naptár** értéket az értékcsökkenés éveként a következő lehetőségek érhetők el az **Időszak-gyakoriság** mezőben:</span><span class="sxs-lookup"><span data-stu-id="1809b-120">If you select **Calendar** as the depreciation year, the following options are available in the **Period frequency** field:</span></span>

-   <span data-ttu-id="1809b-121">**Éves** felad egy összeget december 31-én.</span><span class="sxs-lookup"><span data-stu-id="1809b-121">**Yearly** posts an amount on December 31.</span></span>
-   <span data-ttu-id="1809b-122">**Havi**: felad egy havi összeget minden naptári hó végén.</span><span class="sxs-lookup"><span data-stu-id="1809b-122">**Monthly** posts a monthly amount at the end of each calendar month.</span></span>
-   <span data-ttu-id="1809b-123">**Negyedéves**:Felad egy negyedéves összeget minden naptári negyedév végén (március 31., június 30., szeptember 30. és december 31.).</span><span class="sxs-lookup"><span data-stu-id="1809b-123">**Quarterly** posts a quarterly amount at the end of each calendar quarter (March 31, June 30, September 30, and December 31).</span></span>
-   <span data-ttu-id="1809b-124">**Féléves**: felad egy féléves összeget minden naptári félév végén (június 30. és december 31.).</span><span class="sxs-lookup"><span data-stu-id="1809b-124">**Half-Yearly** posts a half-yearly amount at the calendar half year (June 30 and December 31).</span></span>
-   <span data-ttu-id="1809b-125">**Napi** Feladja az értékcsökkenési összeget a napi értékcsökkenési módhoz úgy, hogy minden naphoz egy tranzakciót használ.</span><span class="sxs-lookup"><span data-stu-id="1809b-125">**Daily** posts the depreciation amount for the daily depreciation method by using one transaction for each day.</span></span>

### <a name="fiscal"></a><span data-ttu-id="1809b-126">Pénzügyi</span><span class="sxs-lookup"><span data-stu-id="1809b-126">Fiscal</span></span>

<span data-ttu-id="1809b-127">Ha bejelöli a **Pénzügyi** lehetőséget az **Értékcsökkenési év** mezőben, akkor a 125 % degresszív értékcsökkenés számítása azon pénzügyi év szerint történik, amelynek pénzügyi naptára meg van adva a könyvben vagy amelyik pénzügyi naptár ki van jelölve a **Főkönyv** lapon.</span><span class="sxs-lookup"><span data-stu-id="1809b-127">If you select **Fiscal** in the **Depreciation year** field, 125% reducing depreciation is calculated based on the fiscal year for the fiscal calendar that is specified for the book, or for the fiscal calendar that is selected on the **Ledger** page.</span></span> <span data-ttu-id="1809b-128">A pénzügyi naptárak a **Pénzügyi naptárak** oldalon állíthatóak be.</span><span class="sxs-lookup"><span data-stu-id="1809b-128">Fiscal calendars are set up on the **Fiscal calendars** page.</span></span> 

<span data-ttu-id="1809b-129">Egy július 1-től június 30-ig tartó pénzügyi év esetén az értékcsökkenés számítása július 1-jén kezdődik.</span><span class="sxs-lookup"><span data-stu-id="1809b-129">For example, for the fiscal year July 1 through June 30, the depreciation calculation starts on July 1.</span></span> <span data-ttu-id="1809b-130">Az üzleti év 12 hónapnál hosszabb vagy rövidebb is lehet.</span><span class="sxs-lookup"><span data-stu-id="1809b-130">The fiscal year can be longer or shorter than 12 months.</span></span> <span data-ttu-id="1809b-131">Az egyes időszakokban az értékcsökkenés automatikusan módosul, és a következő naptári év hossza a **Pénzügyi naptárak** oldalon található időszakok beállítása alapján történik.</span><span class="sxs-lookup"><span data-stu-id="1809b-131">The depreciation is automatically adjusted for each period, and the length of the next fiscal year is determined by the setup of periods on the **Fiscal calendars** page.</span></span> 

<span data-ttu-id="1809b-132">Ha bejelöli **Pénzügyi** értéket az értékcsökkenés éveként a következő lehetőségek érhetők el az **Időszak-gyakoriság** mezőben:</span><span class="sxs-lookup"><span data-stu-id="1809b-132">If you select **Fiscal** as the depreciation year, the following options are available in the **Period frequency** field:</span></span>

-   <span data-ttu-id="1809b-133">Az **Éves** esetében az üzleti évre vonatkozó értékcsökkenés teljes összege a pénzügyi év utolsó napján egy összegként lesz feladva.</span><span class="sxs-lookup"><span data-stu-id="1809b-133">**Yearly** posts the total amount of the depreciation that is calculated for the fiscal year as one amount, on the last day of the fiscal year.</span></span>
-   <span data-ttu-id="1809b-134">**Pénzügyi időszak** feladja az értékcsökkenés teljes értékét a pénzügyi évre.</span><span class="sxs-lookup"><span data-stu-id="1809b-134">**Fiscal period** posts the total amount of the depreciation that is calculated for the fiscal year.</span></span> <span data-ttu-id="1809b-135">Ez az összeg azon pénzügyi időszakokba van elszámolva, amelyek a **Pénzügyi naptárak** lapon meg vannak határozva.</span><span class="sxs-lookup"><span data-stu-id="1809b-135">This amount is accrued into the fiscal periods that are defined on the **Fiscal calendars** page.</span></span>

## <a name="example-of-125-reducing-balance-depreciation"></a><span data-ttu-id="1809b-136">Példa a 125% degresszív értékcsökkenésre</span><span class="sxs-lookup"><span data-stu-id="1809b-136">Example of 125% reducing balance depreciation</span></span>

| &nbsp;                         | &nbsp; |
|--------------------------------|--------|
| <span data-ttu-id="1809b-137">Beszerzési költség</span><span class="sxs-lookup"><span data-stu-id="1809b-137">Acquisition cost</span></span>               | <span data-ttu-id="1809b-138">11 000</span><span class="sxs-lookup"><span data-stu-id="1809b-138">11,000</span></span> |
| <span data-ttu-id="1809b-139">Maradványérték</span><span class="sxs-lookup"><span data-stu-id="1809b-139">Salvage value</span></span>                  | <span data-ttu-id="1809b-140">1000</span><span class="sxs-lookup"><span data-stu-id="1809b-140">1,000</span></span>  |
| <span data-ttu-id="1809b-141">Értékcsökkenés alapja</span><span class="sxs-lookup"><span data-stu-id="1809b-141">Depreciation base</span></span>              | <span data-ttu-id="1809b-142">10 000</span><span class="sxs-lookup"><span data-stu-id="1809b-142">10,000</span></span> |
| <span data-ttu-id="1809b-143">Élettartam (év)</span><span class="sxs-lookup"><span data-stu-id="1809b-143">Service life years</span></span>             | <span data-ttu-id="1809b-144">5</span><span class="sxs-lookup"><span data-stu-id="1809b-144">5</span></span>      |
| <span data-ttu-id="1809b-145">Éves százalékos értékcsökkenés</span><span class="sxs-lookup"><span data-stu-id="1809b-145">Yearly depreciation percentage</span></span> | <span data-ttu-id="1809b-146">25%</span><span class="sxs-lookup"><span data-stu-id="1809b-146">25%</span></span>    |

<span data-ttu-id="1809b-147">A 125% degresszív értékcsökkenési módszer elosztja a 125 százalékot az élettartam éveivel.</span><span class="sxs-lookup"><span data-stu-id="1809b-147">The 125% reducing balance method divides 125 percent by the service life years.</span></span> <span data-ttu-id="1809b-148">Ez a százalék lesz megszorozva az eszköz nettó könyv szerinti értékével, és így lesz megállapítva az egy évre vonatkozó értékcsökkenési összeg.</span><span class="sxs-lookup"><span data-stu-id="1809b-148">That percentage will be multiplied by the net book value of the asset to determine the depreciation amount for the year.</span></span>

| <span data-ttu-id="1809b-149">Időszak</span><span class="sxs-lookup"><span data-stu-id="1809b-149">Period</span></span> | <span data-ttu-id="1809b-150">Az éves értékcsökkenés-összeg számítása</span><span class="sxs-lookup"><span data-stu-id="1809b-150">Calculation of the yearly depreciation amount</span></span> | <span data-ttu-id="1809b-151">Könyv szerinti érték</span><span class="sxs-lookup"><span data-stu-id="1809b-151">Book value</span></span>                    | <span data-ttu-id="1809b-152">Nettó könyv szerinti érték az év végén</span><span class="sxs-lookup"><span data-stu-id="1809b-152">Net book value at the end of the year</span></span> |
|--------|-----------------------------------------------|-------------------------------|---------------------------------------|
| <span data-ttu-id="1809b-153">1. év</span><span class="sxs-lookup"><span data-stu-id="1809b-153">Year 1</span></span> | <span data-ttu-id="1809b-154">(11 000 – 1000) × 25% = 2500</span><span class="sxs-lookup"><span data-stu-id="1809b-154">(11,000 – 1,000) × 25% = 2,500</span></span>                | <span data-ttu-id="1809b-155">(11 000 – 2500) = 8500</span><span class="sxs-lookup"><span data-stu-id="1809b-155">(11,000 – 2,500) = 8,500</span></span>      | <span data-ttu-id="1809b-156">(11 000 – 1000 – 2500) = 7500</span><span class="sxs-lookup"><span data-stu-id="1809b-156">(11,000 – 1,000 – 2,500) = 7,500</span></span>      |
| <span data-ttu-id="1809b-157">2. év</span><span class="sxs-lookup"><span data-stu-id="1809b-157">Year 2</span></span> | <span data-ttu-id="1809b-158">7500 × 25% = 1875</span><span class="sxs-lookup"><span data-stu-id="1809b-158">7,500 × 25% = 1,875</span></span>                           | <span data-ttu-id="1809b-159">(8500 – 1875) = 6625</span><span class="sxs-lookup"><span data-stu-id="1809b-159">(8,500 – 1,875) = 6,625</span></span>       | <span data-ttu-id="1809b-160">(7500 – 1875) = 5625</span><span class="sxs-lookup"><span data-stu-id="1809b-160">(7,500 – 1,875) = 5,625</span></span>               |
| <span data-ttu-id="1809b-161">3. év</span><span class="sxs-lookup"><span data-stu-id="1809b-161">Year 3</span></span> | <span data-ttu-id="1809b-162">5625 × 25% = 1406,25</span><span class="sxs-lookup"><span data-stu-id="1809b-162">5,625 × 25% = 1,406.25</span></span>                        | <span data-ttu-id="1809b-163">(6625 – 1406,25) = 5218,75</span><span class="sxs-lookup"><span data-stu-id="1809b-163">(6,625 – 1,406.25) = 5,218.75</span></span> | <span data-ttu-id="1809b-164">(5625 – 1406,25) = 4218,75</span><span class="sxs-lookup"><span data-stu-id="1809b-164">(5,625 – 1,406.25) = 4,218.75</span></span>         |

> [!NOTE] 
> <span data-ttu-id="1809b-165">Általában amikor az összeg számolása a 125 % degresszív értékcsökkenési módszerrel történik, akkor az érték kisebb lesz mint amit a lineáris értékcsökkenés módszerrel kapnánk, a hátralévő élettartamhoz létezik egy átalakítás a lineáris értékcsökkenés módszeréhez.</span><span class="sxs-lookup"><span data-stu-id="1809b-165">Typically, when the amount that is calculated by using the 125% reducing balance depreciation method becomes less than the amount that would be calculated by using the straight line method, there is a conversion to the straight line method for the remaining life.</span></span>





[!INCLUDE[footer-include](../../includes/footer-banner.md)]