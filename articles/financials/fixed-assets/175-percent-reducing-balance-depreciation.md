---
title: "175 százalék degresszív értékcsökkenés"
description: "Ez a cikk a 175 százalékos degresszív értékcsökkenési módszerről nyújt áttekintést."
author: saraschi2
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 13911
ms.assetid: cc5d001f-bcfe-4602-9ec1-9e265e9fd188
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 318e111f784157666c2853bcd6d5b3af2c9ffdc5
ms.contentlocale: hu-hu
ms.lasthandoff: 08/29/2017

---

# <a name="175-percent-reducing-balance-depreciation"></a><span data-ttu-id="9050e-103">175 százalék degresszív értékcsökkenés</span><span class="sxs-lookup"><span data-stu-id="9050e-103">175 percent reducing balance depreciation</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="9050e-104">Ez a cikk a 175 százalékos degresszív értékcsökkenési módszerről nyújt áttekintést.</span><span class="sxs-lookup"><span data-stu-id="9050e-104">This article gives an overview of the 175 percent reducing balance method of depreciation.</span></span>

<span data-ttu-id="9050e-105">Amikor beállít egy tárgyieszköz-értékcsökkenési profilt és kijelöli a **175% degresszív** értéket a **Mód** mezőben az **Értékcsökkenési profilok** lapon, akkor a tárgyi eszközök, amelyek az értékcsökkenési profilokhoz vannak rendelve értékcsökkenése ugyanazzal százalékos értékkel lesz egyenlő, ami az egyes értékcsökkenési időszakoknál szerepel.</span><span class="sxs-lookup"><span data-stu-id="9050e-105">When you set up a fixed asset depreciation profile and select **175% reducing balance** in the **Method** field on the **Depreciation profiles** page, fixed assets that are assigned the depreciation profile are depreciated by the same percentage in each depreciation period.</span></span> 

<span data-ttu-id="9050e-106">175 % degresszív értékcsökkenés beállítása esetén be kell még jelölnie a beállításokat az **Értékcsökkenési év** mezőben és az **Időszak-gyakoriság** mezőben az **Értékcsökkenési profilok** lapon.</span><span class="sxs-lookup"><span data-stu-id="9050e-106">To set up 175% reducing balance depreciation, you must also select options in the **Depreciation year** field and the **Period frequency** field on the **Depreciation profiles** page.</span></span> <span data-ttu-id="9050e-107">Az **Időszak-gyakoriság** mezőben rendelkezésre álló beállítások eltérőek lehetnek, az **Értékcsökkenési év** mezőben kijelölt értéktől függően.</span><span class="sxs-lookup"><span data-stu-id="9050e-107">The options that are available in the **Period frequency** field vary, depending on the value that is selected in the **Depreciation year** field.</span></span>

## <a name="select-a-depreciation-year"></a><span data-ttu-id="9050e-108">Az értékcsökkenési év kiválasztása</span><span class="sxs-lookup"><span data-stu-id="9050e-108">Select a depreciation year</span></span>
<span data-ttu-id="9050e-109">Kiválaszthatja a **Naptár** vagy **Pénzügyi** elemeket az **Értékcsökkenési év** mezőben az **Értékcsökkenési profilok** lapon.</span><span class="sxs-lookup"><span data-stu-id="9050e-109">You can select either **Calendar** or **Fiscal** in the **Depreciation year** field on the **Depreciation profiles** page.</span></span> <span data-ttu-id="9050e-110">Az alapértelmezett érték **Naptár**.</span><span class="sxs-lookup"><span data-stu-id="9050e-110">The default value is **Calendar**.</span></span> 

<span data-ttu-id="9050e-111">A kiválasztás függvényében változnak az **Időszak gyakorisága** mezőben elérhető beállítások.</span><span class="sxs-lookup"><span data-stu-id="9050e-111">Your selection determines the options that are available in the **Period frequency** field.</span></span> <span data-ttu-id="9050e-112">Ez a mező meghatározza a az értékcsökkenés könyvelésének feladási időpontját és összegét a naptári év során.</span><span class="sxs-lookup"><span data-stu-id="9050e-112">This field defines the depreciation accrual posting dates and amounts throughout the calendar year.</span></span>

### <a name="calendar"></a><span data-ttu-id="9050e-113">Naptár</span><span class="sxs-lookup"><span data-stu-id="9050e-113">Calendar</span></span>

<span data-ttu-id="9050e-114">Megtarthatja az alapértelmezett értéket az **Értékcsökkenési év** mezőben, **Naptár**.</span><span class="sxs-lookup"><span data-stu-id="9050e-114">You can keep the default value in the **Depreciation year** field, **Calendar**.</span></span> 

<span data-ttu-id="9050e-115">A **naptár** lehetőség választása esetén az értékcsökkenés alapja minden évben január 1-jén frissül.</span><span class="sxs-lookup"><span data-stu-id="9050e-115">The **Calendar** option updates the depreciation base on January 1 of each year.</span></span> <span data-ttu-id="9050e-116">Jellemzően az értékcsökkenés alapja a nettó könyv szerinti érték mínusz a maradványérték.</span><span class="sxs-lookup"><span data-stu-id="9050e-116">Typically, the depreciation base is the net book value minus the scrap value.</span></span> <span data-ttu-id="9050e-117">Az ebben a témában szereplő későbbi példákban az értékcsökkenés alapja a számítások oszlop első kifejezésében szereplő számláló.</span><span class="sxs-lookup"><span data-stu-id="9050e-117">In the examples later in this topic, the depreciation base is the numerator in the first expression in the calculations column.</span></span> 

<span data-ttu-id="9050e-118">Ha bejelöli **Naptár** értéket az értékcsökkenés éveként a következő lehetőségek érhetők el az **Időszak-gyakoriság** mezőben:</span><span class="sxs-lookup"><span data-stu-id="9050e-118">If you select **Calendar** as the depreciation year, the following options are available in the **Period frequency** field:</span></span>

-   <span data-ttu-id="9050e-119">**Éves** felad egy összeget december 31-én.</span><span class="sxs-lookup"><span data-stu-id="9050e-119">**Yearly** posts an amount on December 31.</span></span>
-   <span data-ttu-id="9050e-120">**Havi**: felad egy havi összeget minden naptári hó végén.</span><span class="sxs-lookup"><span data-stu-id="9050e-120">**Monthly** posts a monthly amount at the end of each calendar month.</span></span>
-   <span data-ttu-id="9050e-121">**Negyedéves**:Felad egy negyedéves összeget minden naptári negyedév végén (március 31., június 30., szeptember 30. és december 31.).</span><span class="sxs-lookup"><span data-stu-id="9050e-121">**Quarterly** posts a quarterly amount at the end of each calendar quarter (March 31, June 30, September 30, and December 31).</span></span>
-   <span data-ttu-id="9050e-122">**Féléves**: felad egy féléves összeget minden naptári félév végén (június 30. és december 31.).</span><span class="sxs-lookup"><span data-stu-id="9050e-122">**Half-Yearly** posts a half-yearly amount at the calendar half year (June 30 and December 31).</span></span>
-   <span data-ttu-id="9050e-123">**Napi** Feladja az értékcsökkenési összeget a napi értékcsökkenési módhoz úgy, hogy minden naphoz egy tranzakciót használ.</span><span class="sxs-lookup"><span data-stu-id="9050e-123">**Daily** posts the depreciation amount for the daily depreciation method by using one transaction for each day.</span></span>

### <a name="fiscal"></a><span data-ttu-id="9050e-124">Pénzügyi</span><span class="sxs-lookup"><span data-stu-id="9050e-124">Fiscal</span></span>

<span data-ttu-id="9050e-125">Ha bejelöli a **Pénzügyi** lehetőséget az **Értékcsökkenési év** mezőben, akkor a 175 % degresszív értékcsökkenés számítása azon pénzügyi év szerint történik, amelynek pénzügyi naptára meg van adva a könyvben vagy amelyik pénzügyi naptár ki van jelölve a **Főkönyv** lapon.</span><span class="sxs-lookup"><span data-stu-id="9050e-125">If you select **Fiscal** in the **Depreciation year** field, 175% reducing balance depreciation is calculated based on the fiscal year for the fiscal calendar that is specified for the book, or for the fiscal calendar that is selected on the **Ledger** page.</span></span> <span data-ttu-id="9050e-126">A pénzügyi naptárak a **Pénzügyi naptárak** oldalon állíthatóak be.</span><span class="sxs-lookup"><span data-stu-id="9050e-126">Fiscal calendars are set up on the **Fiscal calendars** page.</span></span> <span data-ttu-id="9050e-127">További tudnivalókért lásd: [Pénzügyi naptárak, pénzügyi évek és időszakok.](..\budgeting\fiscal-calendars-fiscal-years-periods.md).</span><span class="sxs-lookup"><span data-stu-id="9050e-127">For more information, see [Fiscal calendars, fiscal years, and periods.](..\budgeting\fiscal-calendars-fiscal-years-periods.md).</span></span>

<span data-ttu-id="9050e-128">Egy július 1-től június 30-ig tartó pénzügyi év esetén az értékcsökkenés számítása július 1-jén kezdődik.</span><span class="sxs-lookup"><span data-stu-id="9050e-128">For example, for the fiscal year July 1 through June 30, the depreciation calculation starts on July 1.</span></span> <span data-ttu-id="9050e-129">Az üzleti év 12 hónapnál hosszabb vagy rövidebb is lehet.</span><span class="sxs-lookup"><span data-stu-id="9050e-129">The fiscal year can be longer or shorter than 12 months.</span></span> <span data-ttu-id="9050e-130">Az egyes időszakokban az értékcsökkenés automatikusan módosul, és a következő naptári év hossza a **Pénzügyi naptárak** oldalon található időszakok beállítása alapján történik.</span><span class="sxs-lookup"><span data-stu-id="9050e-130">The depreciation is automatically adjusted for each period, and the length of the next fiscal year is determined by the setup of periods on the **Fiscal calendars** page.</span></span> 

<span data-ttu-id="9050e-131">Ha bejelöli **Pénzügyi** értéket az értékcsökkenés éveként a következő lehetőségek érhetők el az **Időszak-gyakoriság** mezőben:</span><span class="sxs-lookup"><span data-stu-id="9050e-131">If you select **Fiscal** as the depreciation year, the following options are available in the **Period frequency** field:</span></span>

-   <span data-ttu-id="9050e-132">**Éves**: Feladja az értékcsökkenés teles összegét, aminek számítása a pénzügyi évre történik, annak utolsó napján.</span><span class="sxs-lookup"><span data-stu-id="9050e-132">**Yearly** posts the total amount of the depreciation that is calculated for the fiscal year on the last day of the fiscal year.</span></span>
-   <span data-ttu-id="9050e-133">**Pénzügyi időszak** kiszámítja az értékcsökkenés teljes értékét a pénzügyi évre.</span><span class="sxs-lookup"><span data-stu-id="9050e-133">**Fiscal period** calculates the total amount of the depreciation for the fiscal year.</span></span> <span data-ttu-id="9050e-134">Ez az összeg azon pénzügyi időszakokba van elszámolva, amelyek a **Pénzügyi naptárak** lapon meg vannak határozva.</span><span class="sxs-lookup"><span data-stu-id="9050e-134">This amount is accrued into the fiscal periods that are defined on the **Fiscal calendars** page.</span></span>

## <a name="example-of-175-reducing-balance-depreciation"></a><span data-ttu-id="9050e-135">Példa a 175% degresszív értékcsökkenésre</span><span class="sxs-lookup"><span data-stu-id="9050e-135">Example of 175% reducing balance depreciation</span></span>
|                                |        |
|--------------------------------|--------|
| <span data-ttu-id="9050e-136">Beszerzési költség</span><span class="sxs-lookup"><span data-stu-id="9050e-136">Acquisition cost</span></span>               | <span data-ttu-id="9050e-137">11 000</span><span class="sxs-lookup"><span data-stu-id="9050e-137">11,000</span></span> |
| <span data-ttu-id="9050e-138">Maradványérték</span><span class="sxs-lookup"><span data-stu-id="9050e-138">Salvage value</span></span>                  | <span data-ttu-id="9050e-139">1000</span><span class="sxs-lookup"><span data-stu-id="9050e-139">1,000</span></span>  |
| <span data-ttu-id="9050e-140">Értékcsökkenés alapja</span><span class="sxs-lookup"><span data-stu-id="9050e-140">Depreciation base</span></span>              | <span data-ttu-id="9050e-141">10 000</span><span class="sxs-lookup"><span data-stu-id="9050e-141">10,000</span></span> |
| <span data-ttu-id="9050e-142">Élettartam (év)</span><span class="sxs-lookup"><span data-stu-id="9050e-142">Service life years</span></span>             | <span data-ttu-id="9050e-143">5</span><span class="sxs-lookup"><span data-stu-id="9050e-143">5</span></span>      |
| <span data-ttu-id="9050e-144">Éves százalékos értékcsökkenés</span><span class="sxs-lookup"><span data-stu-id="9050e-144">Yearly depreciation percentage</span></span> | <span data-ttu-id="9050e-145">35%</span><span class="sxs-lookup"><span data-stu-id="9050e-145">35%</span></span>    |

<span data-ttu-id="9050e-146">A 175 % degresszív értékcsökkenési módszer elosztja a 175 százalékot az élettartam éveivel.</span><span class="sxs-lookup"><span data-stu-id="9050e-146">The 175% reducing balance depreciation method divides 175 percent by the service life years.</span></span> <span data-ttu-id="9050e-147">Ez a százalék lesz megszorozva az eszköz nettó könyv szerinti értékével, és így lesz megállapítva az egy évre vonatkozó értékcsökkenési összeg.</span><span class="sxs-lookup"><span data-stu-id="9050e-147">That percentage will be multiplied by the net book value of the asset to determine the depreciation amount for the year.</span></span>

| <span data-ttu-id="9050e-148">Időszak</span><span class="sxs-lookup"><span data-stu-id="9050e-148">Period</span></span> | <span data-ttu-id="9050e-149">Az éves értékcsökkenés-összeg számítása</span><span class="sxs-lookup"><span data-stu-id="9050e-149">Calculation of the yearly depreciation amount</span></span> | <span data-ttu-id="9050e-150">Könyv szerinti érték</span><span class="sxs-lookup"><span data-stu-id="9050e-150">Book value</span></span>                  | <span data-ttu-id="9050e-151">Nettó könyv szerinti érték az év végén</span><span class="sxs-lookup"><span data-stu-id="9050e-151">Net book value at the end of the year</span></span> |
|--------|-----------------------------------------------|-----------------------------|---------------------------------------|
| <span data-ttu-id="9050e-152">1. év</span><span class="sxs-lookup"><span data-stu-id="9050e-152">Year 1</span></span> | <span data-ttu-id="9050e-153">(11 000-1 000) × 35% = 3 500</span><span class="sxs-lookup"><span data-stu-id="9050e-153">(11,000 – 1,000) × 35% = 3,500</span></span>                | <span data-ttu-id="9050e-154">11 000-3 500 = 7 500</span><span class="sxs-lookup"><span data-stu-id="9050e-154">11,000 – 3,500 = 7,500</span></span>      | <span data-ttu-id="9050e-155">(11 000-1 000) - 3 500 = 6 500</span><span class="sxs-lookup"><span data-stu-id="9050e-155">11,000 – 1,000 – 3,500 = 6,500</span></span>        |
| <span data-ttu-id="9050e-156">2. év</span><span class="sxs-lookup"><span data-stu-id="9050e-156">Year 2</span></span> | <span data-ttu-id="9050e-157">6 500 × 35% = 2 275</span><span class="sxs-lookup"><span data-stu-id="9050e-157">6,500 × 35% = 2,275</span></span>                           | <span data-ttu-id="9050e-158">7 500 - 2 275 = 5 225</span><span class="sxs-lookup"><span data-stu-id="9050e-158">7,500 – 2,275 = 5,225</span></span>       | <span data-ttu-id="9050e-159">6 500 - 2 275 = 4 225</span><span class="sxs-lookup"><span data-stu-id="9050e-159">6,500 – 2,275 = 4,225</span></span>                 |
| <span data-ttu-id="9050e-160">3. év</span><span class="sxs-lookup"><span data-stu-id="9050e-160">Year 3</span></span> | <span data-ttu-id="9050e-161">4 225 × 35% = 1 478,75</span><span class="sxs-lookup"><span data-stu-id="9050e-161">4,225 × 35% = 1,478.75</span></span>                        | <span data-ttu-id="9050e-162">5 225 - 1 478,75 = 3 746,25</span><span class="sxs-lookup"><span data-stu-id="9050e-162">5,225 – 1,478.75 = 3,746.25</span></span> | <span data-ttu-id="9050e-163">4 225 - 1 478,75 = 2 746,25</span><span class="sxs-lookup"><span data-stu-id="9050e-163">4,225 – 1,478.75 = 2,746.25</span></span>           |

> [!NOTE] 
> <span data-ttu-id="9050e-164">Általában amikor az összeg számolása a 175 % degresszív értékcsökkenési módszerrel történik, akkor az érték kisebb lesz mint amit a lineáris értékcsökkenés módszerrel kapnánk, a hátralévő élettartamhoz létezik egy átalakítás a lineáris értékcsökkenés módszeréhez.</span><span class="sxs-lookup"><span data-stu-id="9050e-164">Typically, when the amount that is calculated by using the 175% reducing balance depreciation method becomes less than the amount that would be calculated by using the straight line method, there is a conversion to the straight line method for the remaining life.</span></span>




