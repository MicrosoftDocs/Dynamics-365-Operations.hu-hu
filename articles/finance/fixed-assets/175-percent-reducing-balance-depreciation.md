---
title: 175 százalékos degresszív értékcsökkenés
description: Ez a témakör a 175 százalékos degresszív értékcsökkenési módszerről nyújt áttekintést.
author: saraschi2
manager: AnnBe
ms.date: 10/30/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: roschlom
ms.custom: 13911
ms.assetid: cc5d001f-bcfe-4602-9ec1-9e265e9fd188
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 82af2a810df4ea0ab8880eb2215e22e5818e178d
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4995040"
---
# <a name="175-percent-reducing-balance-depreciation"></a><span data-ttu-id="fdb3f-103">175 százalékos degresszív értékcsökkenés</span><span class="sxs-lookup"><span data-stu-id="fdb3f-103">175 percent reducing balance depreciation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="fdb3f-104">Ez a témakör a 175 százalékos degresszív értékcsökkenési módszerről nyújt áttekintést.</span><span class="sxs-lookup"><span data-stu-id="fdb3f-104">This topic gives an overview of the 175 percent reducing balance method of depreciation.</span></span>

<span data-ttu-id="fdb3f-105">Amikor beállít egy tárgyieszköz-értékcsökkenési profilt és kijelöli a **175% degresszív** értéket a **Mód** mezőben az **Értékcsökkenési profilok** lapon, akkor a tárgyi eszközök, amelyek az értékcsökkenési profilokhoz vannak rendelve értékcsökkenése ugyanazzal százalékos értékkel lesz egyenlő, ami az egyes értékcsökkenési időszakoknál szerepel.</span><span class="sxs-lookup"><span data-stu-id="fdb3f-105">When you set up a fixed asset depreciation profile and select **175% reducing balance** in the **Method** field on the **Depreciation profiles** page, fixed assets that are assigned the depreciation profile are depreciated by the same percentage in each depreciation period.</span></span> 

<span data-ttu-id="fdb3f-106">175 % degresszív értékcsökkenés beállítása esetén be kell még jelölnie a beállításokat az **Értékcsökkenési év** mezőben és az **Időszak-gyakoriság** mezőben az **Értékcsökkenési profilok** lapon.</span><span class="sxs-lookup"><span data-stu-id="fdb3f-106">To set up 175% reducing balance depreciation, you must also select options in the **Depreciation year** field and the **Period frequency** field on the **Depreciation profiles** page.</span></span> <span data-ttu-id="fdb3f-107">Az **Időszak-gyakoriság** mezőben rendelkezésre álló beállítások eltérőek lehetnek, az **Értékcsökkenési év** mezőben kijelölt értéktől függően.</span><span class="sxs-lookup"><span data-stu-id="fdb3f-107">The options that are available in the **Period frequency** field vary, depending on the value that is selected in the **Depreciation year** field.</span></span>

## <a name="select-a-depreciation-year"></a><span data-ttu-id="fdb3f-108">Az értékcsökkenési év kiválasztása</span><span class="sxs-lookup"><span data-stu-id="fdb3f-108">Select a depreciation year</span></span>
<span data-ttu-id="fdb3f-109">Kiválaszthatja a **Naptár** vagy **Pénzügyi** elemeket az **Értékcsökkenési év** mezőben az **Értékcsökkenési profilok** lapon.</span><span class="sxs-lookup"><span data-stu-id="fdb3f-109">You can select either **Calendar** or **Fiscal** in the **Depreciation year** field on the **Depreciation profiles** page.</span></span> <span data-ttu-id="fdb3f-110">Az alapértelmezett érték **Naptár**.</span><span class="sxs-lookup"><span data-stu-id="fdb3f-110">The default value is **Calendar**.</span></span> 

<span data-ttu-id="fdb3f-111">A kiválasztás függvényében változnak az **Időszak gyakorisága** mezőben elérhető beállítások.</span><span class="sxs-lookup"><span data-stu-id="fdb3f-111">Your selection determines the options that are available in the **Period frequency** field.</span></span> <span data-ttu-id="fdb3f-112">Ez a mező meghatározza a az értékcsökkenés könyvelésének feladási időpontját és összegét a naptári év során.</span><span class="sxs-lookup"><span data-stu-id="fdb3f-112">This field defines the depreciation accrual posting dates and amounts throughout the calendar year.</span></span>

### <a name="calendar"></a><span data-ttu-id="fdb3f-113">Naptár</span><span class="sxs-lookup"><span data-stu-id="fdb3f-113">Calendar</span></span>

<span data-ttu-id="fdb3f-114">Megtarthatja az alapértelmezett értéket az **Értékcsökkenési év** mezőben, **Naptár**.</span><span class="sxs-lookup"><span data-stu-id="fdb3f-114">You can keep the default value in the **Depreciation year** field, **Calendar**.</span></span> 

<span data-ttu-id="fdb3f-115">A **naptár** lehetőség választása esetén az értékcsökkenés alapja minden évben január 1-jén frissül.</span><span class="sxs-lookup"><span data-stu-id="fdb3f-115">The **Calendar** option updates the depreciation base on January 1 of each year.</span></span> <span data-ttu-id="fdb3f-116">Jellemzően az értékcsökkenés alapja a nettó könyv szerinti érték mínusz a maradványérték.</span><span class="sxs-lookup"><span data-stu-id="fdb3f-116">Typically, the depreciation base is the net book value minus the scrap value.</span></span> <span data-ttu-id="fdb3f-117">Az ebben a témában szereplő későbbi példákban az értékcsökkenés alapja a számítások oszlop első kifejezésében szereplő számláló.</span><span class="sxs-lookup"><span data-stu-id="fdb3f-117">In the examples later in this topic, the depreciation base is the numerator in the first expression in the calculations column.</span></span> 

<span data-ttu-id="fdb3f-118">Ha bejelöli **Naptár** értéket az értékcsökkenés éveként a következő lehetőségek érhetők el az **Időszak-gyakoriság** mezőben:</span><span class="sxs-lookup"><span data-stu-id="fdb3f-118">If you select **Calendar** as the depreciation year, the following options are available in the **Period frequency** field:</span></span>

-   <span data-ttu-id="fdb3f-119">**Éves** felad egy összeget december 31-én.</span><span class="sxs-lookup"><span data-stu-id="fdb3f-119">**Yearly** posts an amount on December 31.</span></span>
-   <span data-ttu-id="fdb3f-120">**Havi**: felad egy havi összeget minden naptári hó végén.</span><span class="sxs-lookup"><span data-stu-id="fdb3f-120">**Monthly** posts a monthly amount at the end of each calendar month.</span></span>
-   <span data-ttu-id="fdb3f-121">**Negyedéves**:Felad egy negyedéves összeget minden naptári negyedév végén (március 31., június 30., szeptember 30. és december 31.).</span><span class="sxs-lookup"><span data-stu-id="fdb3f-121">**Quarterly** posts a quarterly amount at the end of each calendar quarter (March 31, June 30, September 30, and December 31).</span></span>
-   <span data-ttu-id="fdb3f-122">**Féléves**: felad egy féléves összeget minden naptári félév végén (június 30. és december 31.).</span><span class="sxs-lookup"><span data-stu-id="fdb3f-122">**Half-Yearly** posts a half-yearly amount at the calendar half year (June 30 and December 31).</span></span>
-   <span data-ttu-id="fdb3f-123">**Napi** Feladja az értékcsökkenési összeget a napi értékcsökkenési módhoz úgy, hogy minden naphoz egy tranzakciót használ.</span><span class="sxs-lookup"><span data-stu-id="fdb3f-123">**Daily** posts the depreciation amount for the daily depreciation method by using one transaction for each day.</span></span>

### <a name="fiscal"></a><span data-ttu-id="fdb3f-124">Pénzügyi</span><span class="sxs-lookup"><span data-stu-id="fdb3f-124">Fiscal</span></span>

<span data-ttu-id="fdb3f-125">Ha bejelöli a **Pénzügyi** lehetőséget az **Értékcsökkenési év** mezőben, akkor a 175 % degresszív értékcsökkenés számítása azon pénzügyi év szerint történik, amelynek pénzügyi naptára meg van adva a könyvben vagy amelyik pénzügyi naptár ki van jelölve a **Főkönyv** lapon.</span><span class="sxs-lookup"><span data-stu-id="fdb3f-125">If you select **Fiscal** in the **Depreciation year** field, 175% reducing balance depreciation is calculated based on the fiscal year for the fiscal calendar that is specified for the book, or for the fiscal calendar that is selected on the **Ledger** page.</span></span> <span data-ttu-id="fdb3f-126">A pénzügyi naptárak a **Pénzügyi naptárak** oldalon állíthatóak be.</span><span class="sxs-lookup"><span data-stu-id="fdb3f-126">Fiscal calendars are set up on the **Fiscal calendars** page.</span></span> <span data-ttu-id="fdb3f-127">További tudnivalókért lásd: [Pénzügyi naptárak, pénzügyi évek és időszakok.](../budgeting/fiscal-calendars-fiscal-years-periods.md).</span><span class="sxs-lookup"><span data-stu-id="fdb3f-127">For more information, see [Fiscal calendars, fiscal years, and periods](../budgeting/fiscal-calendars-fiscal-years-periods.md).</span></span>

<span data-ttu-id="fdb3f-128">Egy július 1-től június 30-ig tartó pénzügyi év esetén az értékcsökkenés számítása július 1-jén kezdődik.</span><span class="sxs-lookup"><span data-stu-id="fdb3f-128">For example, for the fiscal year July 1 through June 30, the depreciation calculation starts on July 1.</span></span> <span data-ttu-id="fdb3f-129">Az üzleti év 12 hónapnál hosszabb vagy rövidebb is lehet.</span><span class="sxs-lookup"><span data-stu-id="fdb3f-129">The fiscal year can be longer or shorter than 12 months.</span></span> <span data-ttu-id="fdb3f-130">Az egyes időszakokban az értékcsökkenés automatikusan módosul, és a következő naptári év hossza a **Pénzügyi naptárak** oldalon található időszakok beállítása alapján történik.</span><span class="sxs-lookup"><span data-stu-id="fdb3f-130">The depreciation is automatically adjusted for each period, and the length of the next fiscal year is determined by the setup of periods on the **Fiscal calendars** page.</span></span> 

<span data-ttu-id="fdb3f-131">Ha bejelöli **Pénzügyi** értéket az értékcsökkenés éveként a következő lehetőségek érhetők el az **Időszak-gyakoriság** mezőben:</span><span class="sxs-lookup"><span data-stu-id="fdb3f-131">If you select **Fiscal** as the depreciation year, the following options are available in the **Period frequency** field:</span></span>

-   <span data-ttu-id="fdb3f-132">**Éves**: Feladja az értékcsökkenés teles összegét, aminek számítása a pénzügyi évre történik, annak utolsó napján.</span><span class="sxs-lookup"><span data-stu-id="fdb3f-132">**Yearly** posts the total amount of the depreciation that is calculated for the fiscal year on the last day of the fiscal year.</span></span>
-   <span data-ttu-id="fdb3f-133">**Pénzügyi időszak** kiszámítja az értékcsökkenés teljes értékét a pénzügyi évre.</span><span class="sxs-lookup"><span data-stu-id="fdb3f-133">**Fiscal period** calculates the total amount of the depreciation for the fiscal year.</span></span> <span data-ttu-id="fdb3f-134">Ez az összeg azon pénzügyi időszakokba van elszámolva, amelyek a **Pénzügyi naptárak** lapon meg vannak határozva.</span><span class="sxs-lookup"><span data-stu-id="fdb3f-134">This amount is accrued into the fiscal periods that are defined on the **Fiscal calendars** page.</span></span>

## <a name="example-of-175-reducing-balance-depreciation"></a><span data-ttu-id="fdb3f-135">Példa a 175% degresszív értékcsökkenésre</span><span class="sxs-lookup"><span data-stu-id="fdb3f-135">Example of 175% reducing balance depreciation</span></span>

|                                |        |
|--------------------------------|--------|
| <span data-ttu-id="fdb3f-136">Beszerzési költség</span><span class="sxs-lookup"><span data-stu-id="fdb3f-136">Acquisition cost</span></span>               | <span data-ttu-id="fdb3f-137">11 000</span><span class="sxs-lookup"><span data-stu-id="fdb3f-137">11,000</span></span> |
| <span data-ttu-id="fdb3f-138">Maradványérték</span><span class="sxs-lookup"><span data-stu-id="fdb3f-138">Salvage value</span></span>                  | <span data-ttu-id="fdb3f-139">1000</span><span class="sxs-lookup"><span data-stu-id="fdb3f-139">1,000</span></span>  |
| <span data-ttu-id="fdb3f-140">Értékcsökkenés alapja</span><span class="sxs-lookup"><span data-stu-id="fdb3f-140">Depreciation base</span></span>              | <span data-ttu-id="fdb3f-141">10 000</span><span class="sxs-lookup"><span data-stu-id="fdb3f-141">10,000</span></span> |
| <span data-ttu-id="fdb3f-142">Élettartam (év)</span><span class="sxs-lookup"><span data-stu-id="fdb3f-142">Service life years</span></span>             | <span data-ttu-id="fdb3f-143">5</span><span class="sxs-lookup"><span data-stu-id="fdb3f-143">5</span></span>      |
| <span data-ttu-id="fdb3f-144">Éves százalékos értékcsökkenés</span><span class="sxs-lookup"><span data-stu-id="fdb3f-144">Yearly depreciation percentage</span></span> | <span data-ttu-id="fdb3f-145">35%</span><span class="sxs-lookup"><span data-stu-id="fdb3f-145">35%</span></span>    |

<span data-ttu-id="fdb3f-146">A 175% degresszív értékcsökkenési módszer elosztja a 175 százalékot az élettartam éveivel.</span><span class="sxs-lookup"><span data-stu-id="fdb3f-146">The 175% reducing balance depreciation method divides 175 percent by the service life years.</span></span> <span data-ttu-id="fdb3f-147">Ez a százalék lesz megszorozva az eszköz nettó könyv szerinti értékével, és így lesz megállapítva az egy évre vonatkozó értékcsökkenési összeg.</span><span class="sxs-lookup"><span data-stu-id="fdb3f-147">That percentage will be multiplied by the net book value of the asset to determine the depreciation amount for the year.</span></span>

| <span data-ttu-id="fdb3f-148">Időszak</span><span class="sxs-lookup"><span data-stu-id="fdb3f-148">Period</span></span> | <span data-ttu-id="fdb3f-149">Az éves értékcsökkenés-összeg számítása</span><span class="sxs-lookup"><span data-stu-id="fdb3f-149">Calculation of the yearly depreciation amount</span></span> | <span data-ttu-id="fdb3f-150">Könyv szerinti érték</span><span class="sxs-lookup"><span data-stu-id="fdb3f-150">Book value</span></span>                  | <span data-ttu-id="fdb3f-151">Nettó könyv szerinti érték az év végén</span><span class="sxs-lookup"><span data-stu-id="fdb3f-151">Net book value at the end of the year</span></span> |
|--------|-----------------------------------------------|-----------------------------|---------------------------------------|
| <span data-ttu-id="fdb3f-152">1. év</span><span class="sxs-lookup"><span data-stu-id="fdb3f-152">Year 1</span></span> | <span data-ttu-id="fdb3f-153">(11 000-1000) × 35% = 3500</span><span class="sxs-lookup"><span data-stu-id="fdb3f-153">(11,000 – 1,000) × 35% = 3,500</span></span>                | <span data-ttu-id="fdb3f-154">11 000-3500 = 7500</span><span class="sxs-lookup"><span data-stu-id="fdb3f-154">11,000 – 3,500 = 7,500</span></span>      | <span data-ttu-id="fdb3f-155">(11 000-1000) - 3500 = 6500</span><span class="sxs-lookup"><span data-stu-id="fdb3f-155">11,000 – 1,000 – 3,500 = 6,500</span></span>        |
| <span data-ttu-id="fdb3f-156">2. év</span><span class="sxs-lookup"><span data-stu-id="fdb3f-156">Year 2</span></span> | <span data-ttu-id="fdb3f-157">6500 × 35% = 2275</span><span class="sxs-lookup"><span data-stu-id="fdb3f-157">6,500 × 35% = 2,275</span></span>                           | <span data-ttu-id="fdb3f-158">7500 - 2275 = 5225</span><span class="sxs-lookup"><span data-stu-id="fdb3f-158">7,500 – 2,275 = 5,225</span></span>       | <span data-ttu-id="fdb3f-159">6500 - 2275 = 4225</span><span class="sxs-lookup"><span data-stu-id="fdb3f-159">6,500 – 2,275 = 4,225</span></span>                 |
| <span data-ttu-id="fdb3f-160">3. év</span><span class="sxs-lookup"><span data-stu-id="fdb3f-160">Year 3</span></span> | <span data-ttu-id="fdb3f-161">4225 × 35% = 1478,75</span><span class="sxs-lookup"><span data-stu-id="fdb3f-161">4,225 × 35% = 1,478.75</span></span>                        | <span data-ttu-id="fdb3f-162">5225 – 1478,75 = 3746,25</span><span class="sxs-lookup"><span data-stu-id="fdb3f-162">5,225 – 1,478.75 = 3,746.25</span></span> | <span data-ttu-id="fdb3f-163">4225 – 1478,75 = 2746,25</span><span class="sxs-lookup"><span data-stu-id="fdb3f-163">4,225 – 1,478.75 = 2,746.25</span></span>           |

> [!NOTE] 
> <span data-ttu-id="fdb3f-164">Általában amikor az összeg számolása a 175 % degresszív értékcsökkenési módszerrel történik, akkor az érték kisebb lesz mint amit a lineáris értékcsökkenés módszerrel kapnánk, a hátralévő élettartamhoz létezik egy átalakítás a lineáris értékcsökkenés módszeréhez.</span><span class="sxs-lookup"><span data-stu-id="fdb3f-164">Typically, when the amount that is calculated by using the 175% reducing balance depreciation method becomes less than the amount that would be calculated by using the straight line method, there is a conversion to the straight line method for the remaining life.</span></span>



