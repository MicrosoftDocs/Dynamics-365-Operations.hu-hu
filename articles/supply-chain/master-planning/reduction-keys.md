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
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 19251
ms.assetid: aa9e0dfb-6052-4a2e-9378-89507c02fdf2
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 506ca3aac7ad271ca7472f3b74627e94d97a74ee
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="reduction-keys"></a><span data-ttu-id="b7ffe-105">Csökkentési kulcsok</span><span class="sxs-lookup"><span data-stu-id="b7ffe-105">Reduction keys</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="b7ffe-106">Ez a cikk az csökkentési kulcs beállítását bemutató példákat tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="b7ffe-106">This articles provides examples that show how to set up a reduction key.</span></span> <span data-ttu-id="b7ffe-107">Tartalmaz információkat a különböző csökkentési kulcs beállításokról és azok eredményéről.</span><span class="sxs-lookup"><span data-stu-id="b7ffe-107">It includes information about the various reduction key settings and the results of each.</span></span> <span data-ttu-id="b7ffe-108">A csökkentési kulcsot használhatja az előrejelzési követelmények csökkentésének módjának meghatározásához.</span><span class="sxs-lookup"><span data-stu-id="b7ffe-108">You can use a reduction key to define how to reduce forecast requirements.</span></span>

<a name="example-1-percent---reduction-key-forecast-reduction-principle"></a><span data-ttu-id="b7ffe-109">1. példa: Százalék – csökkentési kulcs előrejelzés csökkentési elv</span><span class="sxs-lookup"><span data-stu-id="b7ffe-109">Example 1: Percent - reduction key forecast reduction principle</span></span>
---------------------------------------------------------------

<span data-ttu-id="b7ffe-110">Csökkentési kulcs az előrejelzési követelmények csökkentése a százalékok és az időszakok alapján történik, amelyeket a csökkentési kulcs definiál.</span><span class="sxs-lookup"><span data-stu-id="b7ffe-110">This example shows how a reduction key reduces demand forecast requirements according to the percentages and periods that are defined by the reduction key.</span></span>

1.  <span data-ttu-id="b7ffe-111">A **Csökkentési kulcsok** lapon állítsa be a következő sorokat.</span><span class="sxs-lookup"><span data-stu-id="b7ffe-111">On the **Reduction keys** page, set up the following lines.</span></span>
    | <span data-ttu-id="b7ffe-112">Módosítás</span><span class="sxs-lookup"><span data-stu-id="b7ffe-112">Change</span></span> | <span data-ttu-id="b7ffe-113">Egység</span><span class="sxs-lookup"><span data-stu-id="b7ffe-113">Unit</span></span>  | <span data-ttu-id="b7ffe-114">Százalék</span><span class="sxs-lookup"><span data-stu-id="b7ffe-114">Percent</span></span> |
    |--------|-------|---------|
    | <span data-ttu-id="b7ffe-115">1</span><span class="sxs-lookup"><span data-stu-id="b7ffe-115">1</span></span>      | <span data-ttu-id="b7ffe-116">Hónap</span><span class="sxs-lookup"><span data-stu-id="b7ffe-116">Month</span></span> | <span data-ttu-id="b7ffe-117">100</span><span class="sxs-lookup"><span data-stu-id="b7ffe-117">100</span></span>     |
    | <span data-ttu-id="b7ffe-118">2</span><span class="sxs-lookup"><span data-stu-id="b7ffe-118">2</span></span>      | <span data-ttu-id="b7ffe-119">Hónap</span><span class="sxs-lookup"><span data-stu-id="b7ffe-119">Month</span></span> | <span data-ttu-id="b7ffe-120">75</span><span class="sxs-lookup"><span data-stu-id="b7ffe-120">75</span></span>      |
    | <span data-ttu-id="b7ffe-121">3</span><span class="sxs-lookup"><span data-stu-id="b7ffe-121">3</span></span>      | <span data-ttu-id="b7ffe-122">Hónap</span><span class="sxs-lookup"><span data-stu-id="b7ffe-122">Month</span></span> | <span data-ttu-id="b7ffe-123">50</span><span class="sxs-lookup"><span data-stu-id="b7ffe-123">50</span></span>      |
    | <span data-ttu-id="b7ffe-124">4</span><span class="sxs-lookup"><span data-stu-id="b7ffe-124">4</span></span>      | <span data-ttu-id="b7ffe-125">Hónap</span><span class="sxs-lookup"><span data-stu-id="b7ffe-125">Month</span></span> | <span data-ttu-id="b7ffe-126">25</span><span class="sxs-lookup"><span data-stu-id="b7ffe-126">25</span></span>      |

2.  <span data-ttu-id="b7ffe-127">Hivatkozás a csökkentési kulcsot a cikk fedezeti csoporthoz.</span><span class="sxs-lookup"><span data-stu-id="b7ffe-127">Link the reduction key to the item's coverage group.</span></span>
3.  <span data-ttu-id="b7ffe-128">A **Alaptervek** az oldalon a **Csökkentési elv** mezőben válassza ki **Százalék - csökkentési kulcs**.</span><span class="sxs-lookup"><span data-stu-id="b7ffe-128">On the **Master plans** page, in the **Reduction principle** field, select **Percent - reduction key**.</span></span>
4.  <span data-ttu-id="b7ffe-129">Hozzon létre egy havi 1000 darabos értékesítési előrejelzést.</span><span class="sxs-lookup"><span data-stu-id="b7ffe-129">Create a demand forecast of 1,000 pieces per month.</span></span>

<span data-ttu-id="b7ffe-130">Ha előrejelzési ütemezést január 1-jén futtatja, az igény-előrejelzés követelményeinek felhasználása a százalékokat, amelyek a beállítása a **Csökkentési kulcsok** oldalon.</span><span class="sxs-lookup"><span data-stu-id="b7ffe-130">If you run forecast scheduling on January 1, the demand forecast requirements are consumed according to the percentages that you set up on the **Reduction keys** page.</span></span> <span data-ttu-id="b7ffe-131">Az alábbi mennyiségi követelések kerülnek az alaptervbe.</span><span class="sxs-lookup"><span data-stu-id="b7ffe-131">The following requirement quantities are transferred to the master plan.</span></span>

| <span data-ttu-id="b7ffe-132">Hónap</span><span class="sxs-lookup"><span data-stu-id="b7ffe-132">Month</span></span>                | <span data-ttu-id="b7ffe-133">Szükséges darabszám</span><span class="sxs-lookup"><span data-stu-id="b7ffe-133">Number of pieces required</span></span> |
|----------------------|---------------------------|
| <span data-ttu-id="b7ffe-134">Január</span><span class="sxs-lookup"><span data-stu-id="b7ffe-134">January</span></span>              | <span data-ttu-id="b7ffe-135">0</span><span class="sxs-lookup"><span data-stu-id="b7ffe-135">0</span></span>                         |
| <span data-ttu-id="b7ffe-136">Február</span><span class="sxs-lookup"><span data-stu-id="b7ffe-136">February</span></span>             | <span data-ttu-id="b7ffe-137">250</span><span class="sxs-lookup"><span data-stu-id="b7ffe-137">250</span></span>                       |
| <span data-ttu-id="b7ffe-138">Március</span><span class="sxs-lookup"><span data-stu-id="b7ffe-138">March</span></span>                | <span data-ttu-id="b7ffe-139">500</span><span class="sxs-lookup"><span data-stu-id="b7ffe-139">500</span></span>                       |
| <span data-ttu-id="b7ffe-140">Április</span><span class="sxs-lookup"><span data-stu-id="b7ffe-140">April</span></span>                | <span data-ttu-id="b7ffe-141">750</span><span class="sxs-lookup"><span data-stu-id="b7ffe-141">750</span></span>                       |
| <span data-ttu-id="b7ffe-142">május – december</span><span class="sxs-lookup"><span data-stu-id="b7ffe-142">May through December</span></span> | <span data-ttu-id="b7ffe-143">1000</span><span class="sxs-lookup"><span data-stu-id="b7ffe-143">1,000</span></span>                     |

## <a name="example-2-transactions--reduction-key-forecast-reduction-principle"></a><span data-ttu-id="b7ffe-144">2. példa: Tranzakciók csökkentési kulcs előrejelzés csökkentési elv</span><span class="sxs-lookup"><span data-stu-id="b7ffe-144">Example 2: Transactions  reduction key forecast reduction principle</span></span>
<span data-ttu-id="b7ffe-145">Csökkentési kulcs az előrejelzési követelmények csökkentése a százalékok és az időszakok alapján történik, amelyeket a csökkentési kulcs definiál.</span><span class="sxs-lookup"><span data-stu-id="b7ffe-145">This example shows how actual orders that occur during the periods that are defined by the reduction key reduce demand forecast requirements.</span></span>

-   <span data-ttu-id="b7ffe-146">Az **Alaptervek** az oldalon a **Csökkentési elv** mezőben válassza ki **Tranzakciók - csökkentési kulcs**.</span><span class="sxs-lookup"><span data-stu-id="b7ffe-146">On the **Master plans** page, in the **Reduction principle** field, select **Transactions - reduction key**.</span></span>

<span data-ttu-id="b7ffe-147">A következő értékesítési rendelések léteznek január 1-én.</span><span class="sxs-lookup"><span data-stu-id="b7ffe-147">The following sales orders exist on January 1.</span></span>

| <span data-ttu-id="b7ffe-148">Hónap</span><span class="sxs-lookup"><span data-stu-id="b7ffe-148">Month</span></span>    | <span data-ttu-id="b7ffe-149">Rendelt darabszám</span><span class="sxs-lookup"><span data-stu-id="b7ffe-149">Number of pieces ordered</span></span> |
|----------|--------------------------|
| <span data-ttu-id="b7ffe-150">Január</span><span class="sxs-lookup"><span data-stu-id="b7ffe-150">January</span></span>  | <span data-ttu-id="b7ffe-151">956</span><span class="sxs-lookup"><span data-stu-id="b7ffe-151">956</span></span>                      |
| <span data-ttu-id="b7ffe-152">Február</span><span class="sxs-lookup"><span data-stu-id="b7ffe-152">February</span></span> | <span data-ttu-id="b7ffe-153">1,176</span><span class="sxs-lookup"><span data-stu-id="b7ffe-153">1,176</span></span>                    |
| <span data-ttu-id="b7ffe-154">Március</span><span class="sxs-lookup"><span data-stu-id="b7ffe-154">March</span></span>    | <span data-ttu-id="b7ffe-155">451</span><span class="sxs-lookup"><span data-stu-id="b7ffe-155">451</span></span>                      |
| <span data-ttu-id="b7ffe-156">Április</span><span class="sxs-lookup"><span data-stu-id="b7ffe-156">April</span></span>    | <span data-ttu-id="b7ffe-157">119</span><span class="sxs-lookup"><span data-stu-id="b7ffe-157">119</span></span>                      |

<span data-ttu-id="b7ffe-158">Ugyanazt a havi 1000 darabos értékesítési előrejelzést alkalmazva az alábbi mennyiségi követelések kerülnek az alaptervbe.</span><span class="sxs-lookup"><span data-stu-id="b7ffe-158">If you use the same demand forecast of 1,000 pieces per month, the following requirement quantities are transferred to the master plan.</span></span>

| <span data-ttu-id="b7ffe-159">Hónap</span><span class="sxs-lookup"><span data-stu-id="b7ffe-159">Month</span></span>                | <span data-ttu-id="b7ffe-160">Szükséges darabszám</span><span class="sxs-lookup"><span data-stu-id="b7ffe-160">Number of pieces required</span></span> |
|----------------------|---------------------------|
| <span data-ttu-id="b7ffe-161">Január</span><span class="sxs-lookup"><span data-stu-id="b7ffe-161">January</span></span>              | <span data-ttu-id="b7ffe-162">44</span><span class="sxs-lookup"><span data-stu-id="b7ffe-162">44</span></span>                        |
| <span data-ttu-id="b7ffe-163">Február</span><span class="sxs-lookup"><span data-stu-id="b7ffe-163">February</span></span>             | <span data-ttu-id="b7ffe-164">0</span><span class="sxs-lookup"><span data-stu-id="b7ffe-164">0</span></span>                         |
| <span data-ttu-id="b7ffe-165">Március</span><span class="sxs-lookup"><span data-stu-id="b7ffe-165">March</span></span>                | <span data-ttu-id="b7ffe-166">549</span><span class="sxs-lookup"><span data-stu-id="b7ffe-166">549</span></span>                       |
| <span data-ttu-id="b7ffe-167">Április</span><span class="sxs-lookup"><span data-stu-id="b7ffe-167">April</span></span>                | <span data-ttu-id="b7ffe-168">881</span><span class="sxs-lookup"><span data-stu-id="b7ffe-168">881</span></span>                       |
| <span data-ttu-id="b7ffe-169">május – december</span><span class="sxs-lookup"><span data-stu-id="b7ffe-169">May through December</span></span> | <span data-ttu-id="b7ffe-170">1000</span><span class="sxs-lookup"><span data-stu-id="b7ffe-170">1,000</span></span>                     |

## <a name="example-3-transactions--dynamic-period-forecast-reduction-principle"></a><span data-ttu-id="b7ffe-171">3. példa: Tranzakciók dinamikus periódus előrejelzés csökkentési elv</span><span class="sxs-lookup"><span data-stu-id="b7ffe-171">Example 3: Transactions  dynamic period forecast reduction principle</span></span>
<span data-ttu-id="b7ffe-172">A legtöbb esetben rendszerek vannak beállítva, hogy a tranzakciók csökkenti az igény-előrejelzés egyedi előrejelzési időszakokon belül: hét, hónap, és így tovább.</span><span class="sxs-lookup"><span data-stu-id="b7ffe-172">In most cases, systems are set up so that transactions reduce demand forecast within specific forecast periods: weeks, months, and so on.</span></span> <span data-ttu-id="b7ffe-173">A csökkentési kulcs határozza meg ezeket az időszakokat.</span><span class="sxs-lookup"><span data-stu-id="b7ffe-173">These periods are defined in the reduction key.</span></span> <span data-ttu-id="b7ffe-174">Ugyanakkor két között eltelt idő igény-előrejelzési sort is *Jelenti* egy időszakot.</span><span class="sxs-lookup"><span data-stu-id="b7ffe-174">However, the time between two demand forecast lines can also *imply* a period.</span></span>

1.  <span data-ttu-id="b7ffe-175">Hozzon létre egy igény-előrejelzés a következő dátumokat és mennyiségeket.</span><span class="sxs-lookup"><span data-stu-id="b7ffe-175">Create a demand forecast for the following dates and quantities.</span></span>
    | <span data-ttu-id="b7ffe-176">Dátum</span><span class="sxs-lookup"><span data-stu-id="b7ffe-176">Date</span></span>       | <span data-ttu-id="b7ffe-177">Igény-előrejelzés</span><span class="sxs-lookup"><span data-stu-id="b7ffe-177">Demand forecast</span></span> |
    |------------|-----------------|
    | <span data-ttu-id="b7ffe-178">Január 1.</span><span class="sxs-lookup"><span data-stu-id="b7ffe-178">January 1</span></span>  | <span data-ttu-id="b7ffe-179">1000</span><span class="sxs-lookup"><span data-stu-id="b7ffe-179">1,000</span></span>           |
    | <span data-ttu-id="b7ffe-180">Január 5.</span><span class="sxs-lookup"><span data-stu-id="b7ffe-180">January 5</span></span>  | <span data-ttu-id="b7ffe-181">500</span><span class="sxs-lookup"><span data-stu-id="b7ffe-181">500</span></span>             |
    | <span data-ttu-id="b7ffe-182">Január 12.</span><span class="sxs-lookup"><span data-stu-id="b7ffe-182">January 12</span></span> | <span data-ttu-id="b7ffe-183">1000</span><span class="sxs-lookup"><span data-stu-id="b7ffe-183">1,000</span></span>           |

    <span data-ttu-id="b7ffe-184">Ez előrejelzésben, nincs időszak törlése a következő előre jelzett dátum között: az első és második dátum között nincs négy nappal az az időtartam, és a második és harmadik dátum között van az az időtartam hét nap.</span><span class="sxs-lookup"><span data-stu-id="b7ffe-184">In this forecast, there isn't a clear period between the forecast dates: between the first and second dates there is a four-day span, and between the second and third dates there is a seven-day span.</span></span> <span data-ttu-id="b7ffe-185">A különböző kiterjed a dinamikus időszakok lesznek.</span><span class="sxs-lookup"><span data-stu-id="b7ffe-185">These various spans are the dynamic periods.</span></span>
2.  <span data-ttu-id="b7ffe-186">Értékesítésirendelés-sorok létrehozása.</span><span class="sxs-lookup"><span data-stu-id="b7ffe-186">Create sales order lines as follows.</span></span>
    | <span data-ttu-id="b7ffe-187">Dátum</span><span class="sxs-lookup"><span data-stu-id="b7ffe-187">Date</span></span>                             | <span data-ttu-id="b7ffe-188">Eladási árhoz kapcsolódó mennyiség</span><span class="sxs-lookup"><span data-stu-id="b7ffe-188">Sales order quantity</span></span> |
    |----------------------------------|----------------------|
    | <span data-ttu-id="b7ffe-189">December 15-re vonatkozóan az előző év</span><span class="sxs-lookup"><span data-stu-id="b7ffe-189">December 15 in the previous year</span></span> | <span data-ttu-id="b7ffe-190">500</span><span class="sxs-lookup"><span data-stu-id="b7ffe-190">500</span></span>                  |
    | <span data-ttu-id="b7ffe-191">Január 3.</span><span class="sxs-lookup"><span data-stu-id="b7ffe-191">January 3</span></span>                        | <span data-ttu-id="b7ffe-192">100</span><span class="sxs-lookup"><span data-stu-id="b7ffe-192">100</span></span>                  |
    | <span data-ttu-id="b7ffe-193">Január 10.</span><span class="sxs-lookup"><span data-stu-id="b7ffe-193">January 10</span></span>                       | <span data-ttu-id="b7ffe-194">200</span><span class="sxs-lookup"><span data-stu-id="b7ffe-194">200</span></span>                  |

<span data-ttu-id="b7ffe-195">Az előrejelzés csökken a következőképpen történik:</span><span class="sxs-lookup"><span data-stu-id="b7ffe-195">The forecast will be reduced as follows:</span></span>

-   <span data-ttu-id="b7ffe-196">Az első értékesítési rendelés nem minden időszakban, így azt nem csökkenti az esetleges előrejelzés.</span><span class="sxs-lookup"><span data-stu-id="b7ffe-196">The first sales order isn't within any period, so it won't reduce any forecast.</span></span>
-   <span data-ttu-id="b7ffe-197">A második értékesítési rendelés helyzet között január 1-én január 5-én csökkenteni fogja az előrejelzéshez tartozó január 1-100.</span><span class="sxs-lookup"><span data-stu-id="b7ffe-197">The second sales order is between January 1 and January 5, so it will reduce the forecast for January 1 by 100.</span></span>
-   <span data-ttu-id="b7ffe-198">A harmadik értékesítési rendelés helyzet között január 5 és január 12 között csökkenteni fogja az előrejelzéshez tartozó január 5-200.</span><span class="sxs-lookup"><span data-stu-id="b7ffe-198">The third sales order is between January 5 and January 12, so it will reduce the forecast for January 5 by 200.</span></span>

<span data-ttu-id="b7ffe-199">A következő tervezett rendelés létrejön, az előrejelzés kielégítése céljából.</span><span class="sxs-lookup"><span data-stu-id="b7ffe-199">The following planned order will be created to fulfill the forecast.</span></span>

| <span data-ttu-id="b7ffe-200">Igény-előrejelzés kockája</span><span class="sxs-lookup"><span data-stu-id="b7ffe-200">Demand forecast date</span></span> | <span data-ttu-id="b7ffe-201">Mennyiség csökkentése</span><span class="sxs-lookup"><span data-stu-id="b7ffe-201">Reduced quantity</span></span> |
|----------------------|------------------|
| <span data-ttu-id="b7ffe-202">Január 1.</span><span class="sxs-lookup"><span data-stu-id="b7ffe-202">January 1</span></span>            | <span data-ttu-id="b7ffe-203">900</span><span class="sxs-lookup"><span data-stu-id="b7ffe-203">900</span></span>              |
| <span data-ttu-id="b7ffe-204">Január 5.</span><span class="sxs-lookup"><span data-stu-id="b7ffe-204">January 5</span></span>            | <span data-ttu-id="b7ffe-205">300</span><span class="sxs-lookup"><span data-stu-id="b7ffe-205">300</span></span>              |
| <span data-ttu-id="b7ffe-206">Január 12.</span><span class="sxs-lookup"><span data-stu-id="b7ffe-206">January 12</span></span>           | <span data-ttu-id="b7ffe-207">1000</span><span class="sxs-lookup"><span data-stu-id="b7ffe-207">1,000</span></span>            |

<span data-ttu-id="b7ffe-208">Íme összefoglalását **Tranzakciók - dinamikus időszak** csökkentési:</span><span class="sxs-lookup"><span data-stu-id="b7ffe-208">Here is a summary of **Transactions - dynamic period** reduction:</span></span>

-   <span data-ttu-id="b7ffe-209">Előrejelzési követelmények csökkentése a tényleges tranzakciókat a dinamikus időszak során előforduló.</span><span class="sxs-lookup"><span data-stu-id="b7ffe-209">Forecast requirements are reduced by the actual order transactions that occur during the dynamic period.</span></span> <span data-ttu-id="b7ffe-210">A dinamikus időszak fedezi az aktuális előrejelzési dátumokat és akkor ér véget a következő előrejelzés kezdetén.</span><span class="sxs-lookup"><span data-stu-id="b7ffe-210">The dynamic period covers the current forecast dates and ends at the start of the next forecast.</span></span>
-   <span data-ttu-id="b7ffe-211">Ezzel a módszerrel nem használja, vagy a csökkentési kulcs szükséges.</span><span class="sxs-lookup"><span data-stu-id="b7ffe-211">This method doesn't use or require a reduction key.</span></span>
-   <span data-ttu-id="b7ffe-212">Ez a beállítás használata esetén a következő történik:</span><span class="sxs-lookup"><span data-stu-id="b7ffe-212">When this option is used, the following behavior occurs:</span></span>
    -   <span data-ttu-id="b7ffe-213">Ha az előrejelzés teljes mértékben csökken, az előrejelzési követelmények az aktuális előrejelzési válnak, 0 (nulla).</span><span class="sxs-lookup"><span data-stu-id="b7ffe-213">If the forecast is reduced completely, the forecast requirements for the current forecast become 0 (zero).</span></span>
    -   <span data-ttu-id="b7ffe-214">Nincs jövőbeli előrejelzés esetén beírt utolsó előrejelzésből az előrejelzési követelmények csökkentése.</span><span class="sxs-lookup"><span data-stu-id="b7ffe-214">If there is no future forecast, forecast requirements from the last forecast that was entered are reduced.</span></span>
    -   <span data-ttu-id="b7ffe-215">Időkorlátok az előrejelzés-csökkentés-számításban szerepel.</span><span class="sxs-lookup"><span data-stu-id="b7ffe-215">Time fences are included in the forecast reduction calculation.</span></span>
    -   <span data-ttu-id="b7ffe-216">Időkorlátok az előrejelzés-csökkentés-számításban szerepel.</span><span class="sxs-lookup"><span data-stu-id="b7ffe-216">Positive days are included in the forecast reduction calculation.</span></span>
    -   <span data-ttu-id="b7ffe-217">Tényleges rendelési tranzakciók túllépik az előre jelzett követelményeit, ha a fennmaradó tranzakciók nem továbbítja a következő előrejelzési időszak.</span><span class="sxs-lookup"><span data-stu-id="b7ffe-217">If actual order transactions exceed the forecasted requirements, the remaining transactions aren't forwarded to the next forecast period.</span></span>


<a name="see-also"></a><span data-ttu-id="b7ffe-218">Lásd még</span><span class="sxs-lookup"><span data-stu-id="b7ffe-218">See also</span></span>
--------

[<span data-ttu-id="b7ffe-219">Alaptervek</span><span class="sxs-lookup"><span data-stu-id="b7ffe-219">Master plans</span></span>](master-plans.md)




