---
title: Csökkentési kulcsok
description: Ez a cikk az csökkentési kulcs beállítását bemutató példákat tartalmaz. Tartalmaz információkat a különböző csökkentési kulcs beállításokról és azok eredményéről. A csökkentési kulcsot használhatja az előrejelzési követelmények csökkentésének módjának meghatározásához.
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqPlanSched
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 19251
ms.assetid: aa9e0dfb-6052-4a2e-9378-89507c02fdf2
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3e62431a1fdbeb81dda68297f034ee00adece079
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "364810"
---
# <a name="reduction-keys"></a><span data-ttu-id="c630a-105">Csökkentési kulcsok</span><span class="sxs-lookup"><span data-stu-id="c630a-105">Reduction keys</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c630a-106">Ez a cikk az csökkentési kulcs beállítását bemutató példákat tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="c630a-106">This articles provides examples that show how to set up a reduction key.</span></span> <span data-ttu-id="c630a-107">Tartalmaz információkat a különböző csökkentési kulcs beállításokról és azok eredményéről.</span><span class="sxs-lookup"><span data-stu-id="c630a-107">It includes information about the various reduction key settings and the results of each.</span></span> <span data-ttu-id="c630a-108">A csökkentési kulcsot használhatja az előrejelzési követelmények csökkentésének módjának meghatározásához.</span><span class="sxs-lookup"><span data-stu-id="c630a-108">You can use a reduction key to define how to reduce forecast requirements.</span></span>

<a name="example-1-percent---reduction-key-forecast-reduction-principle"></a><span data-ttu-id="c630a-109">1. példa: Százalék – csökkentési kulcs előrejelzés csökkentési elv</span><span class="sxs-lookup"><span data-stu-id="c630a-109">Example 1: Percent - reduction key forecast reduction principle</span></span>
---------------------------------------------------------------

<span data-ttu-id="c630a-110">Csökkentési kulcs az előrejelzési követelmények csökkentése a százalékok és az időszakok alapján történik, amelyeket a csökkentési kulcs definiál.</span><span class="sxs-lookup"><span data-stu-id="c630a-110">This example shows how a reduction key reduces demand forecast requirements according to the percentages and periods that are defined by the reduction key.</span></span>

1. <span data-ttu-id="c630a-111">A **Csökkentési kulcsok** lapon állítsa be a következő sorokat.</span><span class="sxs-lookup"><span data-stu-id="c630a-111">On the **Reduction keys** page, set up the following lines.</span></span>

   | <span data-ttu-id="c630a-112">Módosítás</span><span class="sxs-lookup"><span data-stu-id="c630a-112">Change</span></span> | <span data-ttu-id="c630a-113">Egység</span><span class="sxs-lookup"><span data-stu-id="c630a-113">Unit</span></span>  | <span data-ttu-id="c630a-114">Százalék</span><span class="sxs-lookup"><span data-stu-id="c630a-114">Percent</span></span> |
   |--------|-------|---------|
   |   <span data-ttu-id="c630a-115">1</span><span class="sxs-lookup"><span data-stu-id="c630a-115">1</span></span>    | <span data-ttu-id="c630a-116">Hónap</span><span class="sxs-lookup"><span data-stu-id="c630a-116">Month</span></span> |   <span data-ttu-id="c630a-117">100</span><span class="sxs-lookup"><span data-stu-id="c630a-117">100</span></span>   |
   |   <span data-ttu-id="c630a-118">2</span><span class="sxs-lookup"><span data-stu-id="c630a-118">2</span></span>    | <span data-ttu-id="c630a-119">Hónap</span><span class="sxs-lookup"><span data-stu-id="c630a-119">Month</span></span> |   <span data-ttu-id="c630a-120">75</span><span class="sxs-lookup"><span data-stu-id="c630a-120">75</span></span>    |
   |   <span data-ttu-id="c630a-121">3</span><span class="sxs-lookup"><span data-stu-id="c630a-121">3</span></span>    | <span data-ttu-id="c630a-122">Hónap</span><span class="sxs-lookup"><span data-stu-id="c630a-122">Month</span></span> |   <span data-ttu-id="c630a-123">50</span><span class="sxs-lookup"><span data-stu-id="c630a-123">50</span></span>    |
   |   <span data-ttu-id="c630a-124">4</span><span class="sxs-lookup"><span data-stu-id="c630a-124">4</span></span>    | <span data-ttu-id="c630a-125">Hónap</span><span class="sxs-lookup"><span data-stu-id="c630a-125">Month</span></span> |   <span data-ttu-id="c630a-126">25</span><span class="sxs-lookup"><span data-stu-id="c630a-126">25</span></span>    |


2. <span data-ttu-id="c630a-127">Hivatkozás a csökkentési kulcsot a cikk fedezeti csoporthoz.</span><span class="sxs-lookup"><span data-stu-id="c630a-127">Link the reduction key to the item's coverage group.</span></span>
3. <span data-ttu-id="c630a-128">A **Alaptervek** az oldalon a **Csökkentési elv** mezőben válassza ki **Százalék - csökkentési kulcs**.</span><span class="sxs-lookup"><span data-stu-id="c630a-128">On the **Master plans** page, in the **Reduction principle** field, select **Percent - reduction key**.</span></span>
4. <span data-ttu-id="c630a-129">Hozzon létre egy havi 1000 darabos értékesítési előrejelzést.</span><span class="sxs-lookup"><span data-stu-id="c630a-129">Create a demand forecast of 1,000 pieces per month.</span></span>

<span data-ttu-id="c630a-130">Ha előrejelzési ütemezést január 1-jén futtatja, az igény-előrejelzés követelményeinek felhasználása a százalékokat, amelyek a beállítása a **Csökkentési kulcsok** oldalon.</span><span class="sxs-lookup"><span data-stu-id="c630a-130">If you run forecast scheduling on January 1, the demand forecast requirements are consumed according to the percentages that you set up on the **Reduction keys** page.</span></span> <span data-ttu-id="c630a-131">Az alábbi mennyiségi követelések kerülnek az alaptervbe.</span><span class="sxs-lookup"><span data-stu-id="c630a-131">The following requirement quantities are transferred to the master plan.</span></span>

| <span data-ttu-id="c630a-132">Hónap</span><span class="sxs-lookup"><span data-stu-id="c630a-132">Month</span></span>                | <span data-ttu-id="c630a-133">Szükséges darabszám</span><span class="sxs-lookup"><span data-stu-id="c630a-133">Number of pieces required</span></span> |
|----------------------|---------------------------|
| <span data-ttu-id="c630a-134">Január</span><span class="sxs-lookup"><span data-stu-id="c630a-134">January</span></span>              | <span data-ttu-id="c630a-135">0</span><span class="sxs-lookup"><span data-stu-id="c630a-135">0</span></span>                         |
| <span data-ttu-id="c630a-136">Február</span><span class="sxs-lookup"><span data-stu-id="c630a-136">February</span></span>             | <span data-ttu-id="c630a-137">250</span><span class="sxs-lookup"><span data-stu-id="c630a-137">250</span></span>                       |
| <span data-ttu-id="c630a-138">Március</span><span class="sxs-lookup"><span data-stu-id="c630a-138">March</span></span>                | <span data-ttu-id="c630a-139">500</span><span class="sxs-lookup"><span data-stu-id="c630a-139">500</span></span>                       |
| <span data-ttu-id="c630a-140">Április</span><span class="sxs-lookup"><span data-stu-id="c630a-140">April</span></span>                | <span data-ttu-id="c630a-141">750</span><span class="sxs-lookup"><span data-stu-id="c630a-141">750</span></span>                       |
| <span data-ttu-id="c630a-142">május – december</span><span class="sxs-lookup"><span data-stu-id="c630a-142">May through December</span></span> | <span data-ttu-id="c630a-143">1000</span><span class="sxs-lookup"><span data-stu-id="c630a-143">1,000</span></span>                     |

## <a name="example-2-transactions--reduction-key-forecast-reduction-principle"></a><span data-ttu-id="c630a-144">2. példa: Tranzakciók csökkentési kulcs előrejelzés csökkentési elv</span><span class="sxs-lookup"><span data-stu-id="c630a-144">Example 2: Transactions  reduction key forecast reduction principle</span></span>
<span data-ttu-id="c630a-145">Csökkentési kulcs az előrejelzési követelmények csökkentése a százalékok és az időszakok alapján történik, amelyeket a csökkentési kulcs definiál.</span><span class="sxs-lookup"><span data-stu-id="c630a-145">This example shows how actual orders that occur during the periods that are defined by the reduction key reduce demand forecast requirements.</span></span>

-   <span data-ttu-id="c630a-146">Az **Alaptervek** az oldalon a **Csökkentési elv** mezőben válassza ki **Tranzakciók - csökkentési kulcs**.</span><span class="sxs-lookup"><span data-stu-id="c630a-146">On the **Master plans** page, in the **Reduction principle** field, select **Transactions - reduction key**.</span></span>

<span data-ttu-id="c630a-147">A következő értékesítési rendelések léteznek január 1-én.</span><span class="sxs-lookup"><span data-stu-id="c630a-147">The following sales orders exist on January 1.</span></span>

| <span data-ttu-id="c630a-148">Hónap</span><span class="sxs-lookup"><span data-stu-id="c630a-148">Month</span></span>    | <span data-ttu-id="c630a-149">Rendelt darabszám</span><span class="sxs-lookup"><span data-stu-id="c630a-149">Number of pieces ordered</span></span> |
|----------|--------------------------|
| <span data-ttu-id="c630a-150">Január</span><span class="sxs-lookup"><span data-stu-id="c630a-150">January</span></span>  | <span data-ttu-id="c630a-151">956</span><span class="sxs-lookup"><span data-stu-id="c630a-151">956</span></span>                      |
| <span data-ttu-id="c630a-152">Február</span><span class="sxs-lookup"><span data-stu-id="c630a-152">February</span></span> | <span data-ttu-id="c630a-153">1,176</span><span class="sxs-lookup"><span data-stu-id="c630a-153">1,176</span></span>                    |
| <span data-ttu-id="c630a-154">Március</span><span class="sxs-lookup"><span data-stu-id="c630a-154">March</span></span>    | <span data-ttu-id="c630a-155">451</span><span class="sxs-lookup"><span data-stu-id="c630a-155">451</span></span>                      |
| <span data-ttu-id="c630a-156">Április</span><span class="sxs-lookup"><span data-stu-id="c630a-156">April</span></span>    | <span data-ttu-id="c630a-157">119</span><span class="sxs-lookup"><span data-stu-id="c630a-157">119</span></span>                      |

<span data-ttu-id="c630a-158">Ugyanazt a havi 1000 darabos értékesítési előrejelzést alkalmazva az alábbi mennyiségi követelések kerülnek az alaptervbe.</span><span class="sxs-lookup"><span data-stu-id="c630a-158">If you use the same demand forecast of 1,000 pieces per month, the following requirement quantities are transferred to the master plan.</span></span>

| <span data-ttu-id="c630a-159">Hónap</span><span class="sxs-lookup"><span data-stu-id="c630a-159">Month</span></span>                | <span data-ttu-id="c630a-160">Szükséges darabszám</span><span class="sxs-lookup"><span data-stu-id="c630a-160">Number of pieces required</span></span> |
|----------------------|---------------------------|
| <span data-ttu-id="c630a-161">Január</span><span class="sxs-lookup"><span data-stu-id="c630a-161">January</span></span>              | <span data-ttu-id="c630a-162">44</span><span class="sxs-lookup"><span data-stu-id="c630a-162">44</span></span>                        |
| <span data-ttu-id="c630a-163">Február</span><span class="sxs-lookup"><span data-stu-id="c630a-163">February</span></span>             | <span data-ttu-id="c630a-164">0</span><span class="sxs-lookup"><span data-stu-id="c630a-164">0</span></span>                         |
| <span data-ttu-id="c630a-165">Március</span><span class="sxs-lookup"><span data-stu-id="c630a-165">March</span></span>                | <span data-ttu-id="c630a-166">549</span><span class="sxs-lookup"><span data-stu-id="c630a-166">549</span></span>                       |
| <span data-ttu-id="c630a-167">Április</span><span class="sxs-lookup"><span data-stu-id="c630a-167">April</span></span>                | <span data-ttu-id="c630a-168">881</span><span class="sxs-lookup"><span data-stu-id="c630a-168">881</span></span>                       |
| <span data-ttu-id="c630a-169">május – december</span><span class="sxs-lookup"><span data-stu-id="c630a-169">May through December</span></span> | <span data-ttu-id="c630a-170">1000</span><span class="sxs-lookup"><span data-stu-id="c630a-170">1,000</span></span>                     |

## <a name="example-3-transactions--dynamic-period-forecast-reduction-principle"></a><span data-ttu-id="c630a-171">3. példa: Tranzakciók dinamikus periódus előrejelzés csökkentési elv</span><span class="sxs-lookup"><span data-stu-id="c630a-171">Example 3: Transactions  dynamic period forecast reduction principle</span></span>
<span data-ttu-id="c630a-172">A legtöbb esetben rendszerek vannak beállítva, hogy a tranzakciók csökkenti az igény-előrejelzés egyedi előrejelzési időszakokon belül: hét, hónap, és így tovább.</span><span class="sxs-lookup"><span data-stu-id="c630a-172">In most cases, systems are set up so that transactions reduce demand forecast within specific forecast periods: weeks, months, and so on.</span></span> <span data-ttu-id="c630a-173">A csökkentési kulcs határozza meg ezeket az időszakokat.</span><span class="sxs-lookup"><span data-stu-id="c630a-173">These periods are defined in the reduction key.</span></span> <span data-ttu-id="c630a-174">Ugyanakkor két között eltelt idő igény-előrejelzési sort is *Jelenti* egy időszakot.</span><span class="sxs-lookup"><span data-stu-id="c630a-174">However, the time between two demand forecast lines can also *imply* a period.</span></span>

1. <span data-ttu-id="c630a-175">Hozzon létre egy igény-előrejelzés a következő dátumokat és mennyiségeket.</span><span class="sxs-lookup"><span data-stu-id="c630a-175">Create a demand forecast for the following dates and quantities.</span></span>

   | <span data-ttu-id="c630a-176">Dátum</span><span class="sxs-lookup"><span data-stu-id="c630a-176">Date</span></span>       | <span data-ttu-id="c630a-177">Igény-előrejelzés</span><span class="sxs-lookup"><span data-stu-id="c630a-177">Demand forecast</span></span> |
   |------------|-----------------|
   | <span data-ttu-id="c630a-178">Január 1.</span><span class="sxs-lookup"><span data-stu-id="c630a-178">January 1</span></span>  | <span data-ttu-id="c630a-179">1000</span><span class="sxs-lookup"><span data-stu-id="c630a-179">1,000</span></span>           |
   | <span data-ttu-id="c630a-180">Január 5.</span><span class="sxs-lookup"><span data-stu-id="c630a-180">January 5</span></span>  | <span data-ttu-id="c630a-181">500</span><span class="sxs-lookup"><span data-stu-id="c630a-181">500</span></span>             |
   | <span data-ttu-id="c630a-182">Január 12.</span><span class="sxs-lookup"><span data-stu-id="c630a-182">January 12</span></span> | <span data-ttu-id="c630a-183">1000</span><span class="sxs-lookup"><span data-stu-id="c630a-183">1,000</span></span>           |

   <span data-ttu-id="c630a-184">Ez előrejelzésben, nincs időszak törlése a következő előre jelzett dátum között: az első és második dátum között nincs négy nappal az az időtartam, és a második és harmadik dátum között van az az időtartam hét nap.</span><span class="sxs-lookup"><span data-stu-id="c630a-184">In this forecast, there isn't a clear period between the forecast dates: between the first and second dates there is a four-day span, and between the second and third dates there is a seven-day span.</span></span> <span data-ttu-id="c630a-185">A különböző kiterjed a dinamikus időszakok lesznek.</span><span class="sxs-lookup"><span data-stu-id="c630a-185">These various spans are the dynamic periods.</span></span>
2. <span data-ttu-id="c630a-186">Értékesítésirendelés-sorok létrehozása.</span><span class="sxs-lookup"><span data-stu-id="c630a-186">Create sales order lines as follows.</span></span>
   | <span data-ttu-id="c630a-187">Dátum</span><span class="sxs-lookup"><span data-stu-id="c630a-187">Date</span></span>                             | <span data-ttu-id="c630a-188">Eladási árhoz kapcsolódó mennyiség</span><span class="sxs-lookup"><span data-stu-id="c630a-188">Sales order quantity</span></span> |
   |----------------------------------|----------------------|
   | <span data-ttu-id="c630a-189">December 15-re vonatkozóan az előző év</span><span class="sxs-lookup"><span data-stu-id="c630a-189">December 15 in the previous year</span></span> | <span data-ttu-id="c630a-190">500</span><span class="sxs-lookup"><span data-stu-id="c630a-190">500</span></span>                  |
   | <span data-ttu-id="c630a-191">Január 3.</span><span class="sxs-lookup"><span data-stu-id="c630a-191">January 3</span></span>                        | <span data-ttu-id="c630a-192">100</span><span class="sxs-lookup"><span data-stu-id="c630a-192">100</span></span>                  |
   | <span data-ttu-id="c630a-193">Január 10.</span><span class="sxs-lookup"><span data-stu-id="c630a-193">January 10</span></span>                       | <span data-ttu-id="c630a-194">200</span><span class="sxs-lookup"><span data-stu-id="c630a-194">200</span></span>                  |

<span data-ttu-id="c630a-195">Az előrejelzés csökken a következőképpen történik:</span><span class="sxs-lookup"><span data-stu-id="c630a-195">The forecast will be reduced as follows:</span></span>

-   <span data-ttu-id="c630a-196">Az első értékesítési rendelés nem minden időszakban, így azt nem csökkenti az esetleges előrejelzés.</span><span class="sxs-lookup"><span data-stu-id="c630a-196">The first sales order isn't within any period, so it won't reduce any forecast.</span></span>
-   <span data-ttu-id="c630a-197">A második értékesítési rendelés helyzet között január 1-én január 5-én csökkenteni fogja az előrejelzéshez tartozó január 1-100.</span><span class="sxs-lookup"><span data-stu-id="c630a-197">The second sales order is between January 1 and January 5, so it will reduce the forecast for January 1 by 100.</span></span>
-   <span data-ttu-id="c630a-198">A harmadik értékesítési rendelés helyzet között január 5 és január 12 között csökkenteni fogja az előrejelzéshez tartozó január 5-200.</span><span class="sxs-lookup"><span data-stu-id="c630a-198">The third sales order is between January 5 and January 12, so it will reduce the forecast for January 5 by 200.</span></span>

<span data-ttu-id="c630a-199">A következő tervezett rendelés létrejön, az előrejelzés kielégítése céljából.</span><span class="sxs-lookup"><span data-stu-id="c630a-199">The following planned order will be created to fulfill the forecast.</span></span>

| <span data-ttu-id="c630a-200">Igény-előrejelzés kockája</span><span class="sxs-lookup"><span data-stu-id="c630a-200">Demand forecast date</span></span> | <span data-ttu-id="c630a-201">Mennyiség csökkentése</span><span class="sxs-lookup"><span data-stu-id="c630a-201">Reduced quantity</span></span> |
|----------------------|------------------|
| <span data-ttu-id="c630a-202">Január 1.</span><span class="sxs-lookup"><span data-stu-id="c630a-202">January 1</span></span>            | <span data-ttu-id="c630a-203">900</span><span class="sxs-lookup"><span data-stu-id="c630a-203">900</span></span>              |
| <span data-ttu-id="c630a-204">Január 5.</span><span class="sxs-lookup"><span data-stu-id="c630a-204">January 5</span></span>            | <span data-ttu-id="c630a-205">300</span><span class="sxs-lookup"><span data-stu-id="c630a-205">300</span></span>              |
| <span data-ttu-id="c630a-206">Január 12.</span><span class="sxs-lookup"><span data-stu-id="c630a-206">January 12</span></span>           | <span data-ttu-id="c630a-207">1000</span><span class="sxs-lookup"><span data-stu-id="c630a-207">1,000</span></span>            |

<span data-ttu-id="c630a-208">Íme összefoglalását **Tranzakciók - dinamikus időszak** csökkentési:</span><span class="sxs-lookup"><span data-stu-id="c630a-208">Here is a summary of **Transactions - dynamic period** reduction:</span></span>

-   <span data-ttu-id="c630a-209">Előrejelzési követelmények csökkentése a tényleges tranzakciókat a dinamikus időszak során előforduló.</span><span class="sxs-lookup"><span data-stu-id="c630a-209">Forecast requirements are reduced by the actual order transactions that occur during the dynamic period.</span></span> <span data-ttu-id="c630a-210">A dinamikus időszak fedezi az aktuális előrejelzési dátumokat és akkor ér véget a következő előrejelzés kezdetén.</span><span class="sxs-lookup"><span data-stu-id="c630a-210">The dynamic period covers the current forecast dates and ends at the start of the next forecast.</span></span>
-   <span data-ttu-id="c630a-211">Ezzel a módszerrel nem használja, vagy a csökkentési kulcs szükséges.</span><span class="sxs-lookup"><span data-stu-id="c630a-211">This method doesn't use or require a reduction key.</span></span>
-   <span data-ttu-id="c630a-212">Ez a beállítás használata esetén a következő történik:</span><span class="sxs-lookup"><span data-stu-id="c630a-212">When this option is used, the following behavior occurs:</span></span>
    -   <span data-ttu-id="c630a-213">Ha az előrejelzés teljes mértékben csökken, az előrejelzési követelmények az aktuális előrejelzési válnak, 0 (nulla).</span><span class="sxs-lookup"><span data-stu-id="c630a-213">If the forecast is reduced completely, the forecast requirements for the current forecast become 0 (zero).</span></span>
    -   <span data-ttu-id="c630a-214">Nincs jövőbeli előrejelzés esetén beírt utolsó előrejelzésből az előrejelzési követelmények csökkentése.</span><span class="sxs-lookup"><span data-stu-id="c630a-214">If there is no future forecast, forecast requirements from the last forecast that was entered are reduced.</span></span>
    -   <span data-ttu-id="c630a-215">Időkorlátok az előrejelzés-csökkentés-számításban szerepel.</span><span class="sxs-lookup"><span data-stu-id="c630a-215">Time fences are included in the forecast reduction calculation.</span></span>
    -   <span data-ttu-id="c630a-216">Időkorlátok az előrejelzés-csökkentés-számításban szerepel.</span><span class="sxs-lookup"><span data-stu-id="c630a-216">Positive days are included in the forecast reduction calculation.</span></span>
    -   <span data-ttu-id="c630a-217">Tényleges rendelési tranzakciók túllépik az előre jelzett követelményeit, ha a fennmaradó tranzakciók nem továbbítja a következő előrejelzési időszak.</span><span class="sxs-lookup"><span data-stu-id="c630a-217">If actual order transactions exceed the forecasted requirements, the remaining transactions aren't forwarded to the next forecast period.</span></span>


<a name="additional-resources"></a><span data-ttu-id="c630a-218">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="c630a-218">Additional resources</span></span>
--------

[<span data-ttu-id="c630a-219">Alaptervek</span><span class="sxs-lookup"><span data-stu-id="c630a-219">Master plans</span></span>](master-plans.md)



