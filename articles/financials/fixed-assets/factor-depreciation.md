---
title: "Értékcsökkenési tényező"
description: "Ez a cikk az tényezős értékcsökkentési módszerről nyújt áttekintést."
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
ms.custom: 13831
ms.assetid: 2b6c4fe4-02ff-4191-bcad-32f1f34c15f2
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 6e7eb5c924f27446fcba9b0f340b7110dbdaab8b
ms.contentlocale: hu-hu
ms.lasthandoff: 04/13/2018

---

# <a name="factor-depreciation"></a><span data-ttu-id="b61df-103">Értékcsökkenési tényező</span><span class="sxs-lookup"><span data-stu-id="b61df-103">Factor depreciation</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="b61df-104">Ez a cikk az tényezős értékcsökkentési módszerről nyújt áttekintést.</span><span class="sxs-lookup"><span data-stu-id="b61df-104">This article gives an overview of the factor depreciation method.</span></span>

<span data-ttu-id="b61df-105">A szorzók a tárgyi eszközök értékcsökkenéséhez használt százalékos értékek.</span><span class="sxs-lookup"><span data-stu-id="b61df-105">Factors are the percentages that are used to depreciate assets.</span></span> <span data-ttu-id="b61df-106">Ha az értékcsökkenési profilok beállítása során a **Mód** mezőjében a **Szorzó** értéket választja az **Értékcsökkenési profilok** oldalon, akkor növekvő, csökkenő vagy lineáris értékcsökkenést állíthat be:</span><span class="sxs-lookup"><span data-stu-id="b61df-106">When you set up a fixed asset depreciation profile and select **Factor** in the **Method** field on the **Depreciation profiles** page, you can set up progressive, digressive, or straight line depreciation:</span></span>

-   <span data-ttu-id="b61df-107">Ha a növekvő értékcsökkenést választja, akkor az értékcsökkenés összege minden értékcsökkenési időszakban emelkedik.</span><span class="sxs-lookup"><span data-stu-id="b61df-107">In progressive depreciation, the amount of depreciation increases each depreciation period.</span></span>
-   <span data-ttu-id="b61df-108">Ha csökkenő értékcsökkenést állít be, akkor az értékcsökkenés időszakonkénti összege mindig csökken.</span><span class="sxs-lookup"><span data-stu-id="b61df-108">In digressive depreciation, the amount of depreciation per period decreases over time.</span></span>
-   <span data-ttu-id="b61df-109">Ha lineáris értékcsökkenést választja, akkor az értékcsökkenés minden időszakban ugyanannyi.</span><span class="sxs-lookup"><span data-stu-id="b61df-109">In straight line depreciation, the depreciation is the same in each period.</span></span>

<span data-ttu-id="b61df-110">Az itt következő szabályok és példák bemutatják, hogyan kell beállítani a szorzókat az értékcsökkenés különböző típusaihoz.</span><span class="sxs-lookup"><span data-stu-id="b61df-110">The rules and examples that follow indicate how you can set up factors for each type of depreciation.</span></span> 

> [!NOTE] 
> <span data-ttu-id="b61df-111">Megjegyzés: Ha a **Szorzó** értéket választja a **Mód** mezőben, megjelenik a **Szorzó** és az **Intervallum** mező.</span><span class="sxs-lookup"><span data-stu-id="b61df-111">When you select **Factor** in the **Method** field, the **Factor** field and the **Interval** field are displayed.</span></span>

## <a name="progressive-depreciation"></a><span data-ttu-id="b61df-112">Növekvő értékcsökkenés</span><span class="sxs-lookup"><span data-stu-id="b61df-112">Progressive depreciation</span></span>
<span data-ttu-id="b61df-113">A **Szorzó** mezőben szereplő érték nagyobb mint **50**.</span><span class="sxs-lookup"><span data-stu-id="b61df-113">The value in the **Factor** field is more than **50**.</span></span>

### <a name="example"></a><span data-ttu-id="b61df-114">Példa</span><span class="sxs-lookup"><span data-stu-id="b61df-114">Example</span></span>

<span data-ttu-id="b61df-115">A beszerzési ár 100 000, a szorzó 70, az élettartam 10 év, és az értékcsökkenés január 1-jén indul.</span><span class="sxs-lookup"><span data-stu-id="b61df-115">The acquisition price is 100,000, the factor is 70, the service life is 10 years, and depreciation starts on January 1.</span></span> <span data-ttu-id="b61df-116">Az értékcsökkenési összegek és a nettó könyv szerinti érték csak az élettartam első hat évében láthatók.</span><span class="sxs-lookup"><span data-stu-id="b61df-116">The depreciation amounts and net book value amounts are shown only for the first six years of service life.</span></span>

| <span data-ttu-id="b61df-117">Év</span><span class="sxs-lookup"><span data-stu-id="b61df-117">Year</span></span> | <span data-ttu-id="b61df-118">Időszak</span><span class="sxs-lookup"><span data-stu-id="b61df-118">Period</span></span>      | <span data-ttu-id="b61df-119">Értékcsökkenés összege</span><span class="sxs-lookup"><span data-stu-id="b61df-119">Depreciation amount</span></span> | <span data-ttu-id="b61df-120">Nettó könyv szerinti érték összege</span><span class="sxs-lookup"><span data-stu-id="b61df-120">Net book value amount</span></span> |
|------|-------------|---------------------|-----------------------|
| <span data-ttu-id="b61df-121">1</span><span class="sxs-lookup"><span data-stu-id="b61df-121">1</span></span>    | <span data-ttu-id="b61df-122">december 31.</span><span class="sxs-lookup"><span data-stu-id="b61df-122">December 31</span></span> | <span data-ttu-id="b61df-123">307,69</span><span class="sxs-lookup"><span data-stu-id="b61df-123">307.69</span></span>              | <span data-ttu-id="b61df-124">99 692,31</span><span class="sxs-lookup"><span data-stu-id="b61df-124">99,692.31</span></span>             |
| <span data-ttu-id="b61df-125">2</span><span class="sxs-lookup"><span data-stu-id="b61df-125">2</span></span>    | <span data-ttu-id="b61df-126">december 31.</span><span class="sxs-lookup"><span data-stu-id="b61df-126">December 31</span></span> | <span data-ttu-id="b61df-127">1447,21</span><span class="sxs-lookup"><span data-stu-id="b61df-127">1,447.21</span></span>            | <span data-ttu-id="b61df-128">98 245,10</span><span class="sxs-lookup"><span data-stu-id="b61df-128">98,245.10</span></span>             |
| <span data-ttu-id="b61df-129">3</span><span class="sxs-lookup"><span data-stu-id="b61df-129">3</span></span>    | <span data-ttu-id="b61df-130">december 31.</span><span class="sxs-lookup"><span data-stu-id="b61df-130">December 31</span></span> | <span data-ttu-id="b61df-131">3 104,50</span><span class="sxs-lookup"><span data-stu-id="b61df-131">3,104.50</span></span>            | <span data-ttu-id="b61df-132">95 140,60</span><span class="sxs-lookup"><span data-stu-id="b61df-132">95,140.60</span></span>             |
| <span data-ttu-id="b61df-133">4</span><span class="sxs-lookup"><span data-stu-id="b61df-133">4</span></span>    | <span data-ttu-id="b61df-134">december 31.</span><span class="sxs-lookup"><span data-stu-id="b61df-134">December 31</span></span> | <span data-ttu-id="b61df-135">5 150,21</span><span class="sxs-lookup"><span data-stu-id="b61df-135">5,150.21</span></span>            | <span data-ttu-id="b61df-136">89 990,39</span><span class="sxs-lookup"><span data-stu-id="b61df-136">89,990.39</span></span>             |
| <span data-ttu-id="b61df-137">5</span><span class="sxs-lookup"><span data-stu-id="b61df-137">5</span></span>    | <span data-ttu-id="b61df-138">december 31.</span><span class="sxs-lookup"><span data-stu-id="b61df-138">December 31</span></span> | <span data-ttu-id="b61df-139">7 522,95</span><span class="sxs-lookup"><span data-stu-id="b61df-139">7,522.95</span></span>            | <span data-ttu-id="b61df-140">82 467,44</span><span class="sxs-lookup"><span data-stu-id="b61df-140">82,467.44</span></span>             |
| <span data-ttu-id="b61df-141">6</span><span class="sxs-lookup"><span data-stu-id="b61df-141">6</span></span>    | <span data-ttu-id="b61df-142">december 31.</span><span class="sxs-lookup"><span data-stu-id="b61df-142">December 31</span></span> | <span data-ttu-id="b61df-143">10 184,06</span><span class="sxs-lookup"><span data-stu-id="b61df-143">10,184.06</span></span>           | <span data-ttu-id="b61df-144">72 283,38</span><span class="sxs-lookup"><span data-stu-id="b61df-144">72,283.38</span></span>             |

## <a name="digressive-depreciation"></a><span data-ttu-id="b61df-145">Csökkenő értékcsökkenés</span><span class="sxs-lookup"><span data-stu-id="b61df-145">Digressive depreciation</span></span>
<span data-ttu-id="b61df-146">A **Szorzó** mezőben szereplő érték kisebb, mint **50**.</span><span class="sxs-lookup"><span data-stu-id="b61df-146">The value in the **Factor** field is less than **50**.</span></span>

### <a name="example"></a><span data-ttu-id="b61df-147">Példa</span><span class="sxs-lookup"><span data-stu-id="b61df-147">Example</span></span>

<span data-ttu-id="b61df-148">A beszerzési ár 100 000, a szorzó 20, az élettartam 10 év, és az értékcsökkenés január 1-jén indul.</span><span class="sxs-lookup"><span data-stu-id="b61df-148">The acquisition price is 100,000, the factor is 20, the service life is 10 years, and depreciation starts on January 1.</span></span> <span data-ttu-id="b61df-149">Az értékcsökkenési összegek és a nettó könyv szerinti érték csak az élettartam első hat évében láthatók.</span><span class="sxs-lookup"><span data-stu-id="b61df-149">The depreciation amounts and net book value amounts are shown only for the first six years of service life.</span></span>

| <span data-ttu-id="b61df-150">Év</span><span class="sxs-lookup"><span data-stu-id="b61df-150">Year</span></span> | <span data-ttu-id="b61df-151">Időszak</span><span class="sxs-lookup"><span data-stu-id="b61df-151">Period</span></span>      | <span data-ttu-id="b61df-152">Értékcsökkenés összege</span><span class="sxs-lookup"><span data-stu-id="b61df-152">Depreciation amount</span></span> | <span data-ttu-id="b61df-153">Nettó könyv szerinti érték összege</span><span class="sxs-lookup"><span data-stu-id="b61df-153">Net book value amount</span></span> |
|------|-------------|---------------------|-----------------------|
| <span data-ttu-id="b61df-154">1</span><span class="sxs-lookup"><span data-stu-id="b61df-154">1</span></span>    | <span data-ttu-id="b61df-155">december 31.</span><span class="sxs-lookup"><span data-stu-id="b61df-155">December 31</span></span> | <span data-ttu-id="b61df-156">56 080,43</span><span class="sxs-lookup"><span data-stu-id="b61df-156">56,080.43</span></span>           | <span data-ttu-id="b61df-157">43 919,57</span><span class="sxs-lookup"><span data-stu-id="b61df-157">43,919.57</span></span>             |
| <span data-ttu-id="b61df-158">2</span><span class="sxs-lookup"><span data-stu-id="b61df-158">2</span></span>    | <span data-ttu-id="b61df-159">december 31.</span><span class="sxs-lookup"><span data-stu-id="b61df-159">December 31</span></span> | <span data-ttu-id="b61df-160">10 665,70</span><span class="sxs-lookup"><span data-stu-id="b61df-160">10,665.70</span></span>           | <span data-ttu-id="b61df-161">33 253,87</span><span class="sxs-lookup"><span data-stu-id="b61df-161">33,253.87</span></span>             |
| <span data-ttu-id="b61df-162">3</span><span class="sxs-lookup"><span data-stu-id="b61df-162">3</span></span>    | <span data-ttu-id="b61df-163">december 31.</span><span class="sxs-lookup"><span data-stu-id="b61df-163">December 31</span></span> | <span data-ttu-id="b61df-164">7 156,22</span><span class="sxs-lookup"><span data-stu-id="b61df-164">7,156.22</span></span>            | <span data-ttu-id="b61df-165">26 097,65</span><span class="sxs-lookup"><span data-stu-id="b61df-165">26,097.65</span></span>             |
| <span data-ttu-id="b61df-166">4</span><span class="sxs-lookup"><span data-stu-id="b61df-166">4</span></span>    | <span data-ttu-id="b61df-167">december 31.</span><span class="sxs-lookup"><span data-stu-id="b61df-167">December 31</span></span> | <span data-ttu-id="b61df-168">5 538,06</span><span class="sxs-lookup"><span data-stu-id="b61df-168">5,538.06</span></span>            | <span data-ttu-id="b61df-169">20 559,59</span><span class="sxs-lookup"><span data-stu-id="b61df-169">20,559.59</span></span>             |
| <span data-ttu-id="b61df-170">5</span><span class="sxs-lookup"><span data-stu-id="b61df-170">5</span></span>    | <span data-ttu-id="b61df-171">december 31.</span><span class="sxs-lookup"><span data-stu-id="b61df-171">December 31</span></span> | <span data-ttu-id="b61df-172">4 579,89</span><span class="sxs-lookup"><span data-stu-id="b61df-172">4,579.89</span></span>            | <span data-ttu-id="b61df-173">15 979,70</span><span class="sxs-lookup"><span data-stu-id="b61df-173">15,979.70</span></span>             |
| <span data-ttu-id="b61df-174">6</span><span class="sxs-lookup"><span data-stu-id="b61df-174">6</span></span>    | <span data-ttu-id="b61df-175">december 31.</span><span class="sxs-lookup"><span data-stu-id="b61df-175">December 31</span></span> | <span data-ttu-id="b61df-176">3 937,36</span><span class="sxs-lookup"><span data-stu-id="b61df-176">3,937.36</span></span>            | <span data-ttu-id="b61df-177">12 042,34</span><span class="sxs-lookup"><span data-stu-id="b61df-177">12,042.34</span></span>             |

## <a name="straight-line-depreciation"></a><span data-ttu-id="b61df-178">Lineáris értékcsökkenés</span><span class="sxs-lookup"><span data-stu-id="b61df-178">Straight line depreciation</span></span>
<span data-ttu-id="b61df-179">A **Szorzó** mezőben szereplő érték egyenlő az **50** értékkel.</span><span class="sxs-lookup"><span data-stu-id="b61df-179">The value in the **Factor** field is equal to **50**.</span></span> <span data-ttu-id="b61df-180">Ebben az esetben az értékcsökkenés minden időszakban ugyanannyi, és ajánlott figyelembe venni a többi mezőben megadott beállítás következményeit, az [Élettartam alatti lineáris értékcsökkenés](straight-line-service-life-depreciation.md) témakörben leírtaknak megfelelően.</span><span class="sxs-lookup"><span data-stu-id="b61df-180">In this case, the depreciation is the same in each period, and you should consider the implications of the values that you have specified in other fields, as described in [Straight line service life depreciation](straight-line-service-life-depreciation.md).</span></span>




