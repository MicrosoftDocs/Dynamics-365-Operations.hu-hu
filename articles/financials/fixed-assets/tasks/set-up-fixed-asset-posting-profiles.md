--- 
title: "Tárgyieszköz-feladási profilok beállítása"
description: "Ez a feladat-útmutató beállítja a Tárgyieszköz-feladási profilokat."
author: saraschi2
manager: AnnBe
ms.date: 02/24/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: b9766d96d16429d0ce0864695a3157f54cad4054
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-fixed-asset-posting-profiles"></a><span data-ttu-id="76895-103">Tárgyieszköz-feladási profilok beállítása</span><span class="sxs-lookup"><span data-stu-id="76895-103">Set up fixed asset posting profiles</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="76895-104">Ez a feladat-útmutató beállítja a Tárgyieszköz-feladási profilokat.</span><span class="sxs-lookup"><span data-stu-id="76895-104">This task guide will set up Fixed asset posting profiles.</span></span>  <span data-ttu-id="76895-105">Ez a Könyvelői szerepkört és a bemutató adatokat használja a USMF jogi személyhez.</span><span class="sxs-lookup"><span data-stu-id="76895-105">It uses the Accountant role and demo data for the USMF legal entity.</span></span>  <span data-ttu-id="76895-106">A feladat-útmutatóban megadott példák egy alap feladási profilra vonatkoznak, a feladási profilokat azonban az Ön konkrét számlatükrének és pénzügyi-jelentéskészítési elvárásainak megfelelően kell létrehoznia.</span><span class="sxs-lookup"><span data-stu-id="76895-106">Examples given in the task guide are for a basic posting profile, though posting profiles must be created for your specific chart of accounts and financial reporting requirements.</span></span>

1. <span data-ttu-id="76895-107">Ugrojon a Tárgyi eszközök > Beállítás > Tárgyieszköz-feladási profilok pontra.</span><span class="sxs-lookup"><span data-stu-id="76895-107">Go to Fixed assets > Setup > Fixed asset posting profiles.</span></span>
2. <span data-ttu-id="76895-108">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="76895-108">Click New.</span></span>
3. <span data-ttu-id="76895-109">Írjon egy értéket a Feladási profil mezőbe.</span><span class="sxs-lookup"><span data-stu-id="76895-109">In the Posting profile field, type a value.</span></span>
4. <span data-ttu-id="76895-110">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="76895-110">In the Description field, type a value.</span></span>
    * <span data-ttu-id="76895-111">Amikor tárgyi eszközökkel dolgozik, minden egyes tárgyieszköz-tranzakció típushoz létre kell hoznia feladási profilt.</span><span class="sxs-lookup"><span data-stu-id="76895-111">You will need to create a posting profile for each fixed asset transaction type you will be using when working with fixed assets.</span></span>  <span data-ttu-id="76895-112">Ez a feladat-útmutató a Beszerzési tranzakciótípussal indul.</span><span class="sxs-lookup"><span data-stu-id="76895-112">This task guide will start with the Acquisition transaction type.</span></span>  
5. <span data-ttu-id="76895-113">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="76895-113">Click Add.</span></span>
6. <span data-ttu-id="76895-114">A Könyv mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="76895-114">In the Book field, enter or select a value.</span></span>
    * <span data-ttu-id="76895-115">A Csoportosítások mező lehetővé teszi, hogy meghatározza a feladási profilt a Táblázat (külön számla beállítása minden egyes tárgyi eszközhöz) vagy a Csoport (külön számla beállítása minden egyes tárgyieszköz-csoporthoz) kapcsán.</span><span class="sxs-lookup"><span data-stu-id="76895-115">The Groupings field allows you to define the posting profile down to the Table (one account set up for each fixed asset) or Group (one account set up for each fixed asset group).</span></span>  <span data-ttu-id="76895-116">Ennél a feladat-útmutatónál az értéket a „Mind” beállításon hagyom, hogy a megadott könyvhöz tartozó összes tárgyi eszközre vonatkozzon.</span><span class="sxs-lookup"><span data-stu-id="76895-116">For this task guide I will leave the value set to “All” to apply to all fixed assets with the specified Book.</span></span>  
7. <span data-ttu-id="76895-117">A Fő számla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="76895-117">In the Main account field, specify the desired values.</span></span>
    * <span data-ttu-id="76895-118">A Beszerzésekhez megadhat ellenszámlát, vagy hagyja a mezőt üresen, ha azt az adott tranzakció kapcsán szeretné kitölteni.</span><span class="sxs-lookup"><span data-stu-id="76895-118">For Acquisitions, you can enter an offset account or leave it blank to be filled in for the specific transaction.</span></span>    
8. <span data-ttu-id="76895-119">A Tranzakció típusa mezőben válassza a „Beszerzés-kiigazítás” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="76895-119">In the Transaction type field, select 'Acquisition adjustment'.</span></span>
    * <span data-ttu-id="76895-120">Beszerzés-kiigazítási tranzakciók esetén ugyanazokat a számlákat használjuk, mint amelyeket a Beszerzési tranzakciók esetén.</span><span class="sxs-lookup"><span data-stu-id="76895-120">For Acquisition adjustment transactions, we will use the same accounts as used for Acquisition transactions.</span></span>  
9. <span data-ttu-id="76895-121">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="76895-121">Click Add.</span></span>
10. <span data-ttu-id="76895-122">A Könyv mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="76895-122">In the Book field, enter or select a value.</span></span>
11. <span data-ttu-id="76895-123">A Fő számla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="76895-123">In the Main account field, specify the desired values.</span></span>
    * <span data-ttu-id="76895-124">A Beszerzés-kiigazításokhoz megadhat ellenszámlát, vagy hagyja a mezőt üresen, ha azt az adott tranzakció kapcsán szeretné kitölteni.</span><span class="sxs-lookup"><span data-stu-id="76895-124">For Acquisition adjustments, you can enter an offset account or leave it blank to be filled in for the specific transaction.</span></span>    
12. <span data-ttu-id="76895-125">A Tranzakció típusa mezőben válassza az „Értékcsökkenés” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="76895-125">In the Transaction type field, select 'Depreciation'.</span></span>
13. <span data-ttu-id="76895-126">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="76895-126">Click Add.</span></span>
14. <span data-ttu-id="76895-127">A Könyv mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="76895-127">In the Book field, enter or select a value.</span></span>
15. <span data-ttu-id="76895-128">A Fő számla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="76895-128">In the Main account field, specify the desired values.</span></span>
16. <span data-ttu-id="76895-129">Az Ellenszámla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="76895-129">In the Offset account field, specify the desired values.</span></span>
17. <span data-ttu-id="76895-130">A Tranzakció típusa mezőben válassza az „Értékcsökkenés-kiigazítás” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="76895-130">In the Transaction type field, select 'Depreciation adjustment'.</span></span>
    * <span data-ttu-id="76895-131">Értékcsökkenés-kiigazítási tranzakciók esetén ugyanazokat a számlákat használjuk, mint amelyeket az Értékcsökkenés tranzakciók esetén.</span><span class="sxs-lookup"><span data-stu-id="76895-131">For Depreciation adjustment transactions, we will use the same accounts as used for Depreciation transactions.</span></span>  
18. <span data-ttu-id="76895-132">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="76895-132">Click Add.</span></span>
19. <span data-ttu-id="76895-133">A Könyv mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="76895-133">In the Book field, enter or select a value.</span></span>
20. <span data-ttu-id="76895-134">A Fő számla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="76895-134">In the Main account field, specify the desired values.</span></span>
21. <span data-ttu-id="76895-135">Az Ellenszámla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="76895-135">In the Offset account field, specify the desired values.</span></span>
22. <span data-ttu-id="76895-136">A Tranzakció típusa mezőben válassza a „Kivezetés - eladás” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="76895-136">In the Transaction type field, select 'Disposal - sale'.</span></span>
23. <span data-ttu-id="76895-137">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="76895-137">Click Add.</span></span>
24. <span data-ttu-id="76895-138">A Könyv mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="76895-138">In the Book field, enter or select a value.</span></span>
25. <span data-ttu-id="76895-139">A Fő számla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="76895-139">In the Main account field, specify the desired values.</span></span>
    * <span data-ttu-id="76895-140">A Kivezetésekhez megadhat ellenszámlát, vagy hagyja a mezőt üresen, ha azt az adott tranzakció kapcsán szeretné kitölteni.</span><span class="sxs-lookup"><span data-stu-id="76895-140">For Disposals, you can enter an offset account or leave it blank to be filled in for the specific transaction.</span></span>  
26. <span data-ttu-id="76895-141">A Tranzakció típusa mezőben válassza a „Kivezetés - selejtezés” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="76895-141">In the Transaction type field, select 'Disposal - scrap'.</span></span>
    * <span data-ttu-id="76895-142">Kivezetés - eladás esetén ugyanazokat a számlákat használjuk, mint Kivezetés - selejtezés esetén.</span><span class="sxs-lookup"><span data-stu-id="76895-142">We will use the same accounts for Disposal sale and Disposal scrap.</span></span>  
27. <span data-ttu-id="76895-143">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="76895-143">Click Add.</span></span>
28. <span data-ttu-id="76895-144">A Könyv mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="76895-144">In the Book field, enter or select a value.</span></span>
29. <span data-ttu-id="76895-145">A Fő számla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="76895-145">In the Main account field, specify the desired values.</span></span>
    * <span data-ttu-id="76895-146">A Kivezetésekhez megadhat ellenszámlát, vagy hagyja a mezőt üresen, ha azt az adott tranzakció kapcsán szeretné kitölteni.</span><span class="sxs-lookup"><span data-stu-id="76895-146">For Disposals, you can enter an offset account or leave it blank to be filled in for the specific transaction.</span></span>  
30. <span data-ttu-id="76895-147">Bontsa ki a Kivezetés szakaszt.</span><span class="sxs-lookup"><span data-stu-id="76895-147">Expand the Disposal section.</span></span>
    * <span data-ttu-id="76895-148">Mind az eladás, mind a selejtezés kapcsán kell beállítania kivezetés feladást.</span><span class="sxs-lookup"><span data-stu-id="76895-148">You must set up disposal posting profiles for both sale and scrap.</span></span>  <span data-ttu-id="76895-149">A folyamatot az értékesítéses kivezetés tranzakciókkal indítjuk.</span><span class="sxs-lookup"><span data-stu-id="76895-149">We will start with disposal sale transactions.</span></span>  
31. <span data-ttu-id="76895-150">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="76895-150">Click Add.</span></span>
32. <span data-ttu-id="76895-151">A Könyv mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="76895-151">In the Book field, enter or select a value.</span></span>
33. <span data-ttu-id="76895-152">A Feladási érték mezőben válassza a „Beszerzési érték" lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="76895-152">In the Post value field, select 'Acquisition value'.</span></span>
    * <span data-ttu-id="76895-153">A beszerzési érték minden évre vonatkozóan figyelembe veszi a Beszerzési és Beszerzés-kiigazítási értékeket.</span><span class="sxs-lookup"><span data-stu-id="76895-153">Acquisition value will address Acquisition and Acquisition adjustment values for all years.</span></span>  <span data-ttu-id="76895-154">Ön is megadhat számlákat az ilyen tranzakciótípusok kapcsán.</span><span class="sxs-lookup"><span data-stu-id="76895-154">You can also define accounts for these transaction types separately.</span></span>  
    * <span data-ttu-id="76895-155">A kivezetési folyamatot be lehet úgy állítani, hogy az - a kivezetés eredményének előjele függvényében - más-más számlát használjon.</span><span class="sxs-lookup"><span data-stu-id="76895-155">You can set the disposal process to use different accounts depending upon if the disposal results in a gain or loss.</span></span>  <span data-ttu-id="76895-156">Az Eladás értéktípusát „Mind” értékre állítom, hogy ugyanazokat a számlákat használjam az összes selejtezés-típusra.</span><span class="sxs-lookup"><span data-stu-id="76895-156">I will set the Sales value type to “All” to use the same accounts for all types of disposals.</span></span>  
34. <span data-ttu-id="76895-157">A Fő számla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="76895-157">In the Main account field, specify the desired values.</span></span>
35. <span data-ttu-id="76895-158">Az Ellenszámla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="76895-158">In the Offset account field, specify the desired values.</span></span>
36. <span data-ttu-id="76895-159">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="76895-159">Click Add.</span></span>
37. <span data-ttu-id="76895-160">A Könyv mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="76895-160">In the Book field, enter or select a value.</span></span>
    * <span data-ttu-id="76895-161">A Feladási érték mezőben válassza az „Értékcsökkenés (előző évek)” elemet.</span><span class="sxs-lookup"><span data-stu-id="76895-161">In the Post value field, select 'Depreciation (prior years)'.</span></span>  
38. <span data-ttu-id="76895-162">A Fő számla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="76895-162">In the Main account field, specify the desired values.</span></span>
39. <span data-ttu-id="76895-163">Az Ellenszámla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="76895-163">In the Offset account field, specify the desired values.</span></span>
40. <span data-ttu-id="76895-164">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="76895-164">Click Add.</span></span>
41. <span data-ttu-id="76895-165">A Könyv mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="76895-165">In the Book field, enter or select a value.</span></span>
42. <span data-ttu-id="76895-166">A Feladási érték mezőben válassza az „Értékcsökkenés (tárgyév)” elemet.</span><span class="sxs-lookup"><span data-stu-id="76895-166">In the Post value field, select 'Depreciation (this year)'.</span></span>
43. <span data-ttu-id="76895-167">A Fő számla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="76895-167">In the Main account field, specify the desired values.</span></span>
44. <span data-ttu-id="76895-168">Az Ellenszámla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="76895-168">In the Offset account field, specify the desired values.</span></span>
45. <span data-ttu-id="76895-169">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="76895-169">Click Add.</span></span>
46. <span data-ttu-id="76895-170">A Könyv mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="76895-170">In the Book field, enter or select a value.</span></span>
47. <span data-ttu-id="76895-171">A Feladási érték mezőben válassza az „Értékcsökkenés-kiigazítások (előző évek)” elemet.</span><span class="sxs-lookup"><span data-stu-id="76895-171">In the Post value field, select 'Depreciation adjustments (prior years)'.</span></span>
48. <span data-ttu-id="76895-172">A Fő számla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="76895-172">In the Main account field, specify the desired values.</span></span>
49. <span data-ttu-id="76895-173">Az Ellenszámla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="76895-173">In the Offset account field, specify the desired values.</span></span>
50. <span data-ttu-id="76895-174">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="76895-174">Click Add.</span></span>
51. <span data-ttu-id="76895-175">A Könyv mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="76895-175">In the Book field, enter or select a value.</span></span>
52. <span data-ttu-id="76895-176">A Feladási érték mezőben válassza az „Értékcsökkenés-kiigazítások (tárgyév)” elemet.</span><span class="sxs-lookup"><span data-stu-id="76895-176">In the Post value field, select 'Depreciation adjustments (this year)'.</span></span>
53. <span data-ttu-id="76895-177">A Fő számla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="76895-177">In the Main account field, specify the desired values.</span></span>
54. <span data-ttu-id="76895-178">Az Ellenszámla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="76895-178">In the Offset account field, specify the desired values.</span></span>
55. <span data-ttu-id="76895-179">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="76895-179">Click Add.</span></span>
56. <span data-ttu-id="76895-180">A Könyv mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="76895-180">In the Book field, enter or select a value.</span></span>
57. <span data-ttu-id="76895-181">A Feladási érték mezőben válassza a „Nettó könyv szerinti érték" lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="76895-181">In the Post value field, select 'Net book value'.</span></span>
58. <span data-ttu-id="76895-182">A Fő számla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="76895-182">In the Main account field, specify the desired values.</span></span>
59. <span data-ttu-id="76895-183">Az Ellenszámla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="76895-183">In the Offset account field, specify the desired values.</span></span>
60. <span data-ttu-id="76895-184">Az értékesítés vagy selejtezés mezőben válassza a „Selejtezés” elemet.</span><span class="sxs-lookup"><span data-stu-id="76895-184">In the Sale or scrap field, select 'Scrap'.</span></span>
61. <span data-ttu-id="76895-185">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="76895-185">Click Add.</span></span>
62. <span data-ttu-id="76895-186">A Könyv mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="76895-186">In the Book field, enter or select a value.</span></span>
63. <span data-ttu-id="76895-187">A Feladási érték mezőben válassza a „Beszerzési érték" lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="76895-187">In the Post value field, select 'Acquisition value'.</span></span>
64. <span data-ttu-id="76895-188">A Fő számla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="76895-188">In the Main account field, specify the desired values.</span></span>
65. <span data-ttu-id="76895-189">Az Ellenszámla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="76895-189">In the Offset account field, specify the desired values.</span></span>
66. <span data-ttu-id="76895-190">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="76895-190">Click Add.</span></span>
67. <span data-ttu-id="76895-191">A Könyv mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="76895-191">In the Book field, enter or select a value.</span></span>
    * <span data-ttu-id="76895-192">A Feladási érték mezőben válassza az „Értékcsökkenés (előző évek)” elemet.</span><span class="sxs-lookup"><span data-stu-id="76895-192">In Post value field, select 'Depreciation (prior years)'.</span></span>  
68. <span data-ttu-id="76895-193">A Fő számla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="76895-193">In the Main account field, specify the desired values.</span></span>
69. <span data-ttu-id="76895-194">Az Ellenszámla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="76895-194">In the Offset account field, specify the desired values.</span></span>
70. <span data-ttu-id="76895-195">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="76895-195">Click Add.</span></span>
71. <span data-ttu-id="76895-196">A Könyv mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="76895-196">In the Book field, enter or select a value.</span></span>
72. <span data-ttu-id="76895-197">A Feladási érték mezőben válassza az „Értékcsökkenés (tárgyév)” elemet.</span><span class="sxs-lookup"><span data-stu-id="76895-197">In the Post value field, select 'Depreciation (this year)'.</span></span>
73. <span data-ttu-id="76895-198">A Fő számla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="76895-198">In the Main account field, specify the desired values.</span></span>
74. <span data-ttu-id="76895-199">Az Ellenszámla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="76895-199">In the Offset account field, specify the desired values.</span></span>
75. <span data-ttu-id="76895-200">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="76895-200">Click Add.</span></span>
76. <span data-ttu-id="76895-201">A Könyv mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="76895-201">In the Book field, enter or select a value.</span></span>
77. <span data-ttu-id="76895-202">A Feladási érték mezőben válassza az „Értékcsökkenés-kiigazítások (előző évek)” elemet.</span><span class="sxs-lookup"><span data-stu-id="76895-202">In the Post value field, select 'Depreciation adjustments (prior years)'.</span></span>
78. <span data-ttu-id="76895-203">A Fő számla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="76895-203">In the Main account field, specify the desired values.</span></span>
79. <span data-ttu-id="76895-204">Az Ellenszámla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="76895-204">In the Offset account field, specify the desired values.</span></span>
80. <span data-ttu-id="76895-205">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="76895-205">Click Add.</span></span>
81. <span data-ttu-id="76895-206">A Könyv mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="76895-206">In the Book field, enter or select a value.</span></span>
82. <span data-ttu-id="76895-207">A Feladási érték mezőben válassza az „Értékcsökkenés-kiigazítások (tárgyév)” elemet.</span><span class="sxs-lookup"><span data-stu-id="76895-207">In the Post value field, select 'Depreciation adjustments (this year)'.</span></span>
83. <span data-ttu-id="76895-208">A Fő számla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="76895-208">In the Main account field, specify the desired values.</span></span>
84. <span data-ttu-id="76895-209">Az Ellenszámla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="76895-209">In the Offset account field, specify the desired values.</span></span>
85. <span data-ttu-id="76895-210">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="76895-210">Click Add.</span></span>
86. <span data-ttu-id="76895-211">A Könyv mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="76895-211">In the Book field, enter or select a value.</span></span>
87. <span data-ttu-id="76895-212">A Feladási érték mezőben válassza a „Nettó könyv szerinti érték" lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="76895-212">In the Post value field, select 'Net book value'.</span></span>
88. <span data-ttu-id="76895-213">A Fő számla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="76895-213">In the Main account field, specify the desired values.</span></span>
89. <span data-ttu-id="76895-214">Az Ellenszámla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="76895-214">In the Offset account field, specify the desired values.</span></span>


