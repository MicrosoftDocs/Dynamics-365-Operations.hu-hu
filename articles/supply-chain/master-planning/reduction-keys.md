---
title: "Csökkentési kulcsok"
description: "Ez a cikk az csökkentési kulcs beállítását bemutató példákat tartalmaz. Tartalmaz információkat a különböző csökkentési kulcs beállításokról és azok eredményéről. A csökkentési kulcsot használhatja az előrejelzési követelmények csökkentésének módjának meghatározásához."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
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
ms.translationtype: HT
ms.sourcegitcommit: d9747ba144d56c9410846769e5465372c89ea111
ms.openlocfilehash: 3e62431a1fdbeb81dda68297f034ee00adece079
ms.contentlocale: hu-hu
ms.lasthandoff: 08/07/2018

---

# <a name="reduction-keys"></a><span data-ttu-id="39e9b-105">Csökkentési kulcsok</span><span class="sxs-lookup"><span data-stu-id="39e9b-105">Reduction keys</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="39e9b-106">Ez a cikk az csökkentési kulcs beállítását bemutató példákat tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="39e9b-106">This articles provides examples that show how to set up a reduction key.</span></span> <span data-ttu-id="39e9b-107">Tartalmaz információkat a különböző csökkentési kulcs beállításokról és azok eredményéről.</span><span class="sxs-lookup"><span data-stu-id="39e9b-107">It includes information about the various reduction key settings and the results of each.</span></span> <span data-ttu-id="39e9b-108">A csökkentési kulcsot használhatja az előrejelzési követelmények csökkentésének módjának meghatározásához.</span><span class="sxs-lookup"><span data-stu-id="39e9b-108">You can use a reduction key to define how to reduce forecast requirements.</span></span>

<a name="example-1-percent---reduction-key-forecast-reduction-principle"></a><span data-ttu-id="39e9b-109">1. példa: Százalék – csökkentési kulcs előrejelzés csökkentési elv</span><span class="sxs-lookup"><span data-stu-id="39e9b-109">Example 1: Percent - reduction key forecast reduction principle</span></span>
---------------------------------------------------------------

<span data-ttu-id="39e9b-110">Csökkentési kulcs az előrejelzési követelmények csökkentése a százalékok és az időszakok alapján történik, amelyeket a csökkentési kulcs definiál.</span><span class="sxs-lookup"><span data-stu-id="39e9b-110">This example shows how a reduction key reduces demand forecast requirements according to the percentages and periods that are defined by the reduction key.</span></span>

1. <span data-ttu-id="39e9b-111">A **Csökkentési kulcsok** lapon állítsa be a következő sorokat.</span><span class="sxs-lookup"><span data-stu-id="39e9b-111">On the **Reduction keys** page, set up the following lines.</span></span>

   | <span data-ttu-id="39e9b-112">Módosítás</span><span class="sxs-lookup"><span data-stu-id="39e9b-112">Change</span></span> | <span data-ttu-id="39e9b-113">Egység</span><span class="sxs-lookup"><span data-stu-id="39e9b-113">Unit</span></span>  | <span data-ttu-id="39e9b-114">Százalék</span><span class="sxs-lookup"><span data-stu-id="39e9b-114">Percent</span></span> |
   |--------|-------|---------|
   |   <span data-ttu-id="39e9b-115">1</span><span class="sxs-lookup"><span data-stu-id="39e9b-115">1</span></span>    | <span data-ttu-id="39e9b-116">Hónap</span><span class="sxs-lookup"><span data-stu-id="39e9b-116">Month</span></span> |   <span data-ttu-id="39e9b-117">100</span><span class="sxs-lookup"><span data-stu-id="39e9b-117">100</span></span>   |
   |   <span data-ttu-id="39e9b-118">2</span><span class="sxs-lookup"><span data-stu-id="39e9b-118">2</span></span>    | <span data-ttu-id="39e9b-119">Hónap</span><span class="sxs-lookup"><span data-stu-id="39e9b-119">Month</span></span> |   <span data-ttu-id="39e9b-120">75</span><span class="sxs-lookup"><span data-stu-id="39e9b-120">75</span></span>    |
   |   <span data-ttu-id="39e9b-121">3</span><span class="sxs-lookup"><span data-stu-id="39e9b-121">3</span></span>    | <span data-ttu-id="39e9b-122">Hónap</span><span class="sxs-lookup"><span data-stu-id="39e9b-122">Month</span></span> |   <span data-ttu-id="39e9b-123">50</span><span class="sxs-lookup"><span data-stu-id="39e9b-123">50</span></span>    |
   |   <span data-ttu-id="39e9b-124">4</span><span class="sxs-lookup"><span data-stu-id="39e9b-124">4</span></span>    | <span data-ttu-id="39e9b-125">Hónap</span><span class="sxs-lookup"><span data-stu-id="39e9b-125">Month</span></span> |   <span data-ttu-id="39e9b-126">25</span><span class="sxs-lookup"><span data-stu-id="39e9b-126">25</span></span>    |


2. <span data-ttu-id="39e9b-127">Hivatkozás a csökkentési kulcsot a cikk fedezeti csoporthoz.</span><span class="sxs-lookup"><span data-stu-id="39e9b-127">Link the reduction key to the item's coverage group.</span></span>
3. <span data-ttu-id="39e9b-128">A **Alaptervek** az oldalon a **Csökkentési elv** mezőben válassza ki **Százalék - csökkentési kulcs**.</span><span class="sxs-lookup"><span data-stu-id="39e9b-128">On the **Master plans** page, in the **Reduction principle** field, select **Percent - reduction key**.</span></span>
4. <span data-ttu-id="39e9b-129">Hozzon létre egy havi 1000 darabos értékesítési előrejelzést.</span><span class="sxs-lookup"><span data-stu-id="39e9b-129">Create a demand forecast of 1,000 pieces per month.</span></span>

<span data-ttu-id="39e9b-130">Ha előrejelzési ütemezést január 1-jén futtatja, az igény-előrejelzés követelményeinek felhasználása a százalékokat, amelyek a beállítása a **Csökkentési kulcsok** oldalon.</span><span class="sxs-lookup"><span data-stu-id="39e9b-130">If you run forecast scheduling on January 1, the demand forecast requirements are consumed according to the percentages that you set up on the **Reduction keys** page.</span></span> <span data-ttu-id="39e9b-131">Az alábbi mennyiségi követelések kerülnek az alaptervbe.</span><span class="sxs-lookup"><span data-stu-id="39e9b-131">The following requirement quantities are transferred to the master plan.</span></span>

| <span data-ttu-id="39e9b-132">Hónap</span><span class="sxs-lookup"><span data-stu-id="39e9b-132">Month</span></span>                | <span data-ttu-id="39e9b-133">Szükséges darabszám</span><span class="sxs-lookup"><span data-stu-id="39e9b-133">Number of pieces required</span></span> |
|----------------------|---------------------------|
| <span data-ttu-id="39e9b-134">Január</span><span class="sxs-lookup"><span data-stu-id="39e9b-134">January</span></span>              | <span data-ttu-id="39e9b-135">0</span><span class="sxs-lookup"><span data-stu-id="39e9b-135">0</span></span>                         |
| <span data-ttu-id="39e9b-136">Február</span><span class="sxs-lookup"><span data-stu-id="39e9b-136">February</span></span>             | <span data-ttu-id="39e9b-137">250</span><span class="sxs-lookup"><span data-stu-id="39e9b-137">250</span></span>                       |
| <span data-ttu-id="39e9b-138">Március</span><span class="sxs-lookup"><span data-stu-id="39e9b-138">March</span></span>                | <span data-ttu-id="39e9b-139">500</span><span class="sxs-lookup"><span data-stu-id="39e9b-139">500</span></span>                       |
| <span data-ttu-id="39e9b-140">Április</span><span class="sxs-lookup"><span data-stu-id="39e9b-140">April</span></span>                | <span data-ttu-id="39e9b-141">750</span><span class="sxs-lookup"><span data-stu-id="39e9b-141">750</span></span>                       |
| <span data-ttu-id="39e9b-142">május – december</span><span class="sxs-lookup"><span data-stu-id="39e9b-142">May through December</span></span> | <span data-ttu-id="39e9b-143">1000</span><span class="sxs-lookup"><span data-stu-id="39e9b-143">1,000</span></span>                     |

## <a name="example-2-transactions--reduction-key-forecast-reduction-principle"></a><span data-ttu-id="39e9b-144">2. példa: Tranzakciók csökkentési kulcs előrejelzés csökkentési elv</span><span class="sxs-lookup"><span data-stu-id="39e9b-144">Example 2: Transactions  reduction key forecast reduction principle</span></span>
<span data-ttu-id="39e9b-145">Csökkentési kulcs az előrejelzési követelmények csökkentése a százalékok és az időszakok alapján történik, amelyeket a csökkentési kulcs definiál.</span><span class="sxs-lookup"><span data-stu-id="39e9b-145">This example shows how actual orders that occur during the periods that are defined by the reduction key reduce demand forecast requirements.</span></span>

-   <span data-ttu-id="39e9b-146">Az **Alaptervek** az oldalon a **Csökkentési elv** mezőben válassza ki **Tranzakciók - csökkentési kulcs**.</span><span class="sxs-lookup"><span data-stu-id="39e9b-146">On the **Master plans** page, in the **Reduction principle** field, select **Transactions - reduction key**.</span></span>

<span data-ttu-id="39e9b-147">A következő értékesítési rendelések léteznek január 1-én.</span><span class="sxs-lookup"><span data-stu-id="39e9b-147">The following sales orders exist on January 1.</span></span>

| <span data-ttu-id="39e9b-148">Hónap</span><span class="sxs-lookup"><span data-stu-id="39e9b-148">Month</span></span>    | <span data-ttu-id="39e9b-149">Rendelt darabszám</span><span class="sxs-lookup"><span data-stu-id="39e9b-149">Number of pieces ordered</span></span> |
|----------|--------------------------|
| <span data-ttu-id="39e9b-150">Január</span><span class="sxs-lookup"><span data-stu-id="39e9b-150">January</span></span>  | <span data-ttu-id="39e9b-151">956</span><span class="sxs-lookup"><span data-stu-id="39e9b-151">956</span></span>                      |
| <span data-ttu-id="39e9b-152">Február</span><span class="sxs-lookup"><span data-stu-id="39e9b-152">February</span></span> | <span data-ttu-id="39e9b-153">1,176</span><span class="sxs-lookup"><span data-stu-id="39e9b-153">1,176</span></span>                    |
| <span data-ttu-id="39e9b-154">Március</span><span class="sxs-lookup"><span data-stu-id="39e9b-154">March</span></span>    | <span data-ttu-id="39e9b-155">451</span><span class="sxs-lookup"><span data-stu-id="39e9b-155">451</span></span>                      |
| <span data-ttu-id="39e9b-156">Április</span><span class="sxs-lookup"><span data-stu-id="39e9b-156">April</span></span>    | <span data-ttu-id="39e9b-157">119</span><span class="sxs-lookup"><span data-stu-id="39e9b-157">119</span></span>                      |

<span data-ttu-id="39e9b-158">Ugyanazt a havi 1000 darabos értékesítési előrejelzést alkalmazva az alábbi mennyiségi követelések kerülnek az alaptervbe.</span><span class="sxs-lookup"><span data-stu-id="39e9b-158">If you use the same demand forecast of 1,000 pieces per month, the following requirement quantities are transferred to the master plan.</span></span>

| <span data-ttu-id="39e9b-159">Hónap</span><span class="sxs-lookup"><span data-stu-id="39e9b-159">Month</span></span>                | <span data-ttu-id="39e9b-160">Szükséges darabszám</span><span class="sxs-lookup"><span data-stu-id="39e9b-160">Number of pieces required</span></span> |
|----------------------|---------------------------|
| <span data-ttu-id="39e9b-161">Január</span><span class="sxs-lookup"><span data-stu-id="39e9b-161">January</span></span>              | <span data-ttu-id="39e9b-162">44</span><span class="sxs-lookup"><span data-stu-id="39e9b-162">44</span></span>                        |
| <span data-ttu-id="39e9b-163">Február</span><span class="sxs-lookup"><span data-stu-id="39e9b-163">February</span></span>             | <span data-ttu-id="39e9b-164">0</span><span class="sxs-lookup"><span data-stu-id="39e9b-164">0</span></span>                         |
| <span data-ttu-id="39e9b-165">Március</span><span class="sxs-lookup"><span data-stu-id="39e9b-165">March</span></span>                | <span data-ttu-id="39e9b-166">549</span><span class="sxs-lookup"><span data-stu-id="39e9b-166">549</span></span>                       |
| <span data-ttu-id="39e9b-167">Április</span><span class="sxs-lookup"><span data-stu-id="39e9b-167">April</span></span>                | <span data-ttu-id="39e9b-168">881</span><span class="sxs-lookup"><span data-stu-id="39e9b-168">881</span></span>                       |
| <span data-ttu-id="39e9b-169">május – december</span><span class="sxs-lookup"><span data-stu-id="39e9b-169">May through December</span></span> | <span data-ttu-id="39e9b-170">1000</span><span class="sxs-lookup"><span data-stu-id="39e9b-170">1,000</span></span>                     |

## <a name="example-3-transactions--dynamic-period-forecast-reduction-principle"></a><span data-ttu-id="39e9b-171">3. példa: Tranzakciók dinamikus periódus előrejelzés csökkentési elv</span><span class="sxs-lookup"><span data-stu-id="39e9b-171">Example 3: Transactions  dynamic period forecast reduction principle</span></span>
<span data-ttu-id="39e9b-172">A legtöbb esetben rendszerek vannak beállítva, hogy a tranzakciók csökkenti az igény-előrejelzés egyedi előrejelzési időszakokon belül: hét, hónap, és így tovább.</span><span class="sxs-lookup"><span data-stu-id="39e9b-172">In most cases, systems are set up so that transactions reduce demand forecast within specific forecast periods: weeks, months, and so on.</span></span> <span data-ttu-id="39e9b-173">A csökkentési kulcs határozza meg ezeket az időszakokat.</span><span class="sxs-lookup"><span data-stu-id="39e9b-173">These periods are defined in the reduction key.</span></span> <span data-ttu-id="39e9b-174">Ugyanakkor két között eltelt idő igény-előrejelzési sort is *Jelenti* egy időszakot.</span><span class="sxs-lookup"><span data-stu-id="39e9b-174">However, the time between two demand forecast lines can also *imply* a period.</span></span>

1. <span data-ttu-id="39e9b-175">Hozzon létre egy igény-előrejelzés a következő dátumokat és mennyiségeket.</span><span class="sxs-lookup"><span data-stu-id="39e9b-175">Create a demand forecast for the following dates and quantities.</span></span>

   | <span data-ttu-id="39e9b-176">Dátum</span><span class="sxs-lookup"><span data-stu-id="39e9b-176">Date</span></span>       | <span data-ttu-id="39e9b-177">Igény-előrejelzés</span><span class="sxs-lookup"><span data-stu-id="39e9b-177">Demand forecast</span></span> |
   |------------|-----------------|
   | <span data-ttu-id="39e9b-178">Január 1.</span><span class="sxs-lookup"><span data-stu-id="39e9b-178">January 1</span></span>  | <span data-ttu-id="39e9b-179">1000</span><span class="sxs-lookup"><span data-stu-id="39e9b-179">1,000</span></span>           |
   | <span data-ttu-id="39e9b-180">Január 5.</span><span class="sxs-lookup"><span data-stu-id="39e9b-180">January 5</span></span>  | <span data-ttu-id="39e9b-181">500</span><span class="sxs-lookup"><span data-stu-id="39e9b-181">500</span></span>             |
   | <span data-ttu-id="39e9b-182">Január 12.</span><span class="sxs-lookup"><span data-stu-id="39e9b-182">January 12</span></span> | <span data-ttu-id="39e9b-183">1000</span><span class="sxs-lookup"><span data-stu-id="39e9b-183">1,000</span></span>           |

   <span data-ttu-id="39e9b-184">Ez előrejelzésben, nincs időszak törlése a következő előre jelzett dátum között: az első és második dátum között nincs négy nappal az az időtartam, és a második és harmadik dátum között van az az időtartam hét nap.</span><span class="sxs-lookup"><span data-stu-id="39e9b-184">In this forecast, there isn't a clear period between the forecast dates: between the first and second dates there is a four-day span, and between the second and third dates there is a seven-day span.</span></span> <span data-ttu-id="39e9b-185">A különböző kiterjed a dinamikus időszakok lesznek.</span><span class="sxs-lookup"><span data-stu-id="39e9b-185">These various spans are the dynamic periods.</span></span>
2. <span data-ttu-id="39e9b-186">Értékesítésirendelés-sorok létrehozása.</span><span class="sxs-lookup"><span data-stu-id="39e9b-186">Create sales order lines as follows.</span></span>
   | <span data-ttu-id="39e9b-187">Dátum</span><span class="sxs-lookup"><span data-stu-id="39e9b-187">Date</span></span>                             | <span data-ttu-id="39e9b-188">Eladási árhoz kapcsolódó mennyiség</span><span class="sxs-lookup"><span data-stu-id="39e9b-188">Sales order quantity</span></span> |
   |----------------------------------|----------------------|
   | <span data-ttu-id="39e9b-189">December 15-re vonatkozóan az előző év</span><span class="sxs-lookup"><span data-stu-id="39e9b-189">December 15 in the previous year</span></span> | <span data-ttu-id="39e9b-190">500</span><span class="sxs-lookup"><span data-stu-id="39e9b-190">500</span></span>                  |
   | <span data-ttu-id="39e9b-191">Január 3.</span><span class="sxs-lookup"><span data-stu-id="39e9b-191">January 3</span></span>                        | <span data-ttu-id="39e9b-192">100</span><span class="sxs-lookup"><span data-stu-id="39e9b-192">100</span></span>                  |
   | <span data-ttu-id="39e9b-193">Január 10.</span><span class="sxs-lookup"><span data-stu-id="39e9b-193">January 10</span></span>                       | <span data-ttu-id="39e9b-194">200</span><span class="sxs-lookup"><span data-stu-id="39e9b-194">200</span></span>                  |

<span data-ttu-id="39e9b-195">Az előrejelzés csökken a következőképpen történik:</span><span class="sxs-lookup"><span data-stu-id="39e9b-195">The forecast will be reduced as follows:</span></span>

-   <span data-ttu-id="39e9b-196">Az első értékesítési rendelés nem minden időszakban, így azt nem csökkenti az esetleges előrejelzés.</span><span class="sxs-lookup"><span data-stu-id="39e9b-196">The first sales order isn't within any period, so it won't reduce any forecast.</span></span>
-   <span data-ttu-id="39e9b-197">A második értékesítési rendelés helyzet között január 1-én január 5-én csökkenteni fogja az előrejelzéshez tartozó január 1-100.</span><span class="sxs-lookup"><span data-stu-id="39e9b-197">The second sales order is between January 1 and January 5, so it will reduce the forecast for January 1 by 100.</span></span>
-   <span data-ttu-id="39e9b-198">A harmadik értékesítési rendelés helyzet között január 5 és január 12 között csökkenteni fogja az előrejelzéshez tartozó január 5-200.</span><span class="sxs-lookup"><span data-stu-id="39e9b-198">The third sales order is between January 5 and January 12, so it will reduce the forecast for January 5 by 200.</span></span>

<span data-ttu-id="39e9b-199">A következő tervezett rendelés létrejön, az előrejelzés kielégítése céljából.</span><span class="sxs-lookup"><span data-stu-id="39e9b-199">The following planned order will be created to fulfill the forecast.</span></span>

| <span data-ttu-id="39e9b-200">Igény-előrejelzés kockája</span><span class="sxs-lookup"><span data-stu-id="39e9b-200">Demand forecast date</span></span> | <span data-ttu-id="39e9b-201">Mennyiség csökkentése</span><span class="sxs-lookup"><span data-stu-id="39e9b-201">Reduced quantity</span></span> |
|----------------------|------------------|
| <span data-ttu-id="39e9b-202">Január 1.</span><span class="sxs-lookup"><span data-stu-id="39e9b-202">January 1</span></span>            | <span data-ttu-id="39e9b-203">900</span><span class="sxs-lookup"><span data-stu-id="39e9b-203">900</span></span>              |
| <span data-ttu-id="39e9b-204">Január 5.</span><span class="sxs-lookup"><span data-stu-id="39e9b-204">January 5</span></span>            | <span data-ttu-id="39e9b-205">300</span><span class="sxs-lookup"><span data-stu-id="39e9b-205">300</span></span>              |
| <span data-ttu-id="39e9b-206">Január 12.</span><span class="sxs-lookup"><span data-stu-id="39e9b-206">January 12</span></span>           | <span data-ttu-id="39e9b-207">1000</span><span class="sxs-lookup"><span data-stu-id="39e9b-207">1,000</span></span>            |

<span data-ttu-id="39e9b-208">Íme összefoglalását **Tranzakciók - dinamikus időszak** csökkentési:</span><span class="sxs-lookup"><span data-stu-id="39e9b-208">Here is a summary of **Transactions - dynamic period** reduction:</span></span>

-   <span data-ttu-id="39e9b-209">Előrejelzési követelmények csökkentése a tényleges tranzakciókat a dinamikus időszak során előforduló.</span><span class="sxs-lookup"><span data-stu-id="39e9b-209">Forecast requirements are reduced by the actual order transactions that occur during the dynamic period.</span></span> <span data-ttu-id="39e9b-210">A dinamikus időszak fedezi az aktuális előrejelzési dátumokat és akkor ér véget a következő előrejelzés kezdetén.</span><span class="sxs-lookup"><span data-stu-id="39e9b-210">The dynamic period covers the current forecast dates and ends at the start of the next forecast.</span></span>
-   <span data-ttu-id="39e9b-211">Ezzel a módszerrel nem használja, vagy a csökkentési kulcs szükséges.</span><span class="sxs-lookup"><span data-stu-id="39e9b-211">This method doesn't use or require a reduction key.</span></span>
-   <span data-ttu-id="39e9b-212">Ez a beállítás használata esetén a következő történik:</span><span class="sxs-lookup"><span data-stu-id="39e9b-212">When this option is used, the following behavior occurs:</span></span>
    -   <span data-ttu-id="39e9b-213">Ha az előrejelzés teljes mértékben csökken, az előrejelzési követelmények az aktuális előrejelzési válnak, 0 (nulla).</span><span class="sxs-lookup"><span data-stu-id="39e9b-213">If the forecast is reduced completely, the forecast requirements for the current forecast become 0 (zero).</span></span>
    -   <span data-ttu-id="39e9b-214">Nincs jövőbeli előrejelzés esetén beírt utolsó előrejelzésből az előrejelzési követelmények csökkentése.</span><span class="sxs-lookup"><span data-stu-id="39e9b-214">If there is no future forecast, forecast requirements from the last forecast that was entered are reduced.</span></span>
    -   <span data-ttu-id="39e9b-215">Időkorlátok az előrejelzés-csökkentés-számításban szerepel.</span><span class="sxs-lookup"><span data-stu-id="39e9b-215">Time fences are included in the forecast reduction calculation.</span></span>
    -   <span data-ttu-id="39e9b-216">Időkorlátok az előrejelzés-csökkentés-számításban szerepel.</span><span class="sxs-lookup"><span data-stu-id="39e9b-216">Positive days are included in the forecast reduction calculation.</span></span>
    -   <span data-ttu-id="39e9b-217">Tényleges rendelési tranzakciók túllépik az előre jelzett követelményeit, ha a fennmaradó tranzakciók nem továbbítja a következő előrejelzési időszak.</span><span class="sxs-lookup"><span data-stu-id="39e9b-217">If actual order transactions exceed the forecasted requirements, the remaining transactions aren't forwarded to the next forecast period.</span></span>


<a name="additional-resources"></a><span data-ttu-id="39e9b-218">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="39e9b-218">Additional resources</span></span>
--------

[<span data-ttu-id="39e9b-219">Alaptervek</span><span class="sxs-lookup"><span data-stu-id="39e9b-219">Master plans</span></span>](master-plans.md)




