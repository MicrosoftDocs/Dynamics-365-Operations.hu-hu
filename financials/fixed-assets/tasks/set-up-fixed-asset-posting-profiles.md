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
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: b9766d96d16429d0ce0864695a3157f54cad4054
ms.contentlocale: hu-hu
ms.lasthandoff: 08/29/2017

---
# <a name="set-up-fixed-asset-posting-profiles"></a><span data-ttu-id="ca777-103">Tárgyieszköz-feladási profilok beállítása</span><span class="sxs-lookup"><span data-stu-id="ca777-103">Set up fixed asset posting profiles</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ca777-104">Ez a feladat-útmutató beállítja a Tárgyieszköz-feladási profilokat.</span><span class="sxs-lookup"><span data-stu-id="ca777-104">This task guide will set up Fixed asset posting profiles.</span></span>  <span data-ttu-id="ca777-105">Ez a Könyvelői szerepkört és a bemutató adatokat használja a USMF jogi személyhez.</span><span class="sxs-lookup"><span data-stu-id="ca777-105">It uses the Accountant role and demo data for the USMF legal entity.</span></span>  <span data-ttu-id="ca777-106">A feladat-útmutatóban megadott példák egy alap feladási profilra vonatkoznak, a feladási profilokat azonban az Ön konkrét számlatükrének és pénzügyi-jelentéskészítési elvárásainak megfelelően kell létrehoznia.</span><span class="sxs-lookup"><span data-stu-id="ca777-106">Examples given in the task guide are for a basic posting profile, though posting profiles must be created for your specific chart of accounts and financial reporting requirements.</span></span>

1. <span data-ttu-id="ca777-107">Ugrojon a Tárgyi eszközök > Beállítás > Tárgyieszköz-feladási profilok pontra.</span><span class="sxs-lookup"><span data-stu-id="ca777-107">Go to Fixed assets > Setup > Fixed asset posting profiles.</span></span>
2. <span data-ttu-id="ca777-108">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="ca777-108">Click New.</span></span>
3. <span data-ttu-id="ca777-109">Írjon egy értéket a Feladási profil mezőbe.</span><span class="sxs-lookup"><span data-stu-id="ca777-109">In the Posting profile field, type a value.</span></span>
4. <span data-ttu-id="ca777-110">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="ca777-110">In the Description field, type a value.</span></span>
    * <span data-ttu-id="ca777-111">Amikor tárgyi eszközökkel dolgozik, minden egyes tárgyieszköz-tranzakció típushoz létre kell hoznia feladási profilt.</span><span class="sxs-lookup"><span data-stu-id="ca777-111">You will need to create a posting profile for each fixed asset transaction type you will be using when working with fixed assets.</span></span>  <span data-ttu-id="ca777-112">Ez a feladat-útmutató a Beszerzési tranzakciótípussal indul.</span><span class="sxs-lookup"><span data-stu-id="ca777-112">This task guide will start with the Acquisition transaction type.</span></span>  
5. <span data-ttu-id="ca777-113">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="ca777-113">Click Add.</span></span>
6. <span data-ttu-id="ca777-114">A Könyv mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="ca777-114">In the Book field, enter or select a value.</span></span>
    * <span data-ttu-id="ca777-115">A Csoportosítások mező lehetővé teszi, hogy meghatározza a feladási profilt a Táblázat (külön számla beállítása minden egyes tárgyi eszközhöz) vagy a Csoport (külön számla beállítása minden egyes tárgyieszköz-csoporthoz) kapcsán.</span><span class="sxs-lookup"><span data-stu-id="ca777-115">The Groupings field allows you to define the posting profile down to the Table (one account set up for each fixed asset) or Group (one account set up for each fixed asset group).</span></span>  <span data-ttu-id="ca777-116">Ennél a feladat-útmutatónál az értéket a „Mind” beállításon hagyom, hogy a megadott könyvhöz tartozó összes tárgyi eszközre vonatkozzon.</span><span class="sxs-lookup"><span data-stu-id="ca777-116">For this task guide I will leave the value set to “All” to apply to all fixed assets with the specified Book.</span></span>  
7. <span data-ttu-id="ca777-117">A Fő számla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="ca777-117">In the Main account field, specify the desired values.</span></span>
    * <span data-ttu-id="ca777-118">A Beszerzésekhez megadhat ellenszámlát, vagy hagyja a mezőt üresen, ha azt az adott tranzakció kapcsán szeretné kitölteni.</span><span class="sxs-lookup"><span data-stu-id="ca777-118">For Acquisitions, you can enter an offset account or leave it blank to be filled in for the specific transaction.</span></span>    
8. <span data-ttu-id="ca777-119">A Tranzakció típusa mezőben válassza a „Beszerzés-kiigazítás” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ca777-119">In the Transaction type field, select 'Acquisition adjustment'.</span></span>
    * <span data-ttu-id="ca777-120">Beszerzés-kiigazítási tranzakciók esetén ugyanazokat a számlákat használjuk, mint amelyeket a Beszerzési tranzakciók esetén.</span><span class="sxs-lookup"><span data-stu-id="ca777-120">For Acquisition adjustment transactions, we will use the same accounts as used for Acquisition transactions.</span></span>  
9. <span data-ttu-id="ca777-121">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="ca777-121">Click Add.</span></span>
10. <span data-ttu-id="ca777-122">A Könyv mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="ca777-122">In the Book field, enter or select a value.</span></span>
11. <span data-ttu-id="ca777-123">A Fő számla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="ca777-123">In the Main account field, specify the desired values.</span></span>
    * <span data-ttu-id="ca777-124">A Beszerzés-kiigazításokhoz megadhat ellenszámlát, vagy hagyja a mezőt üresen, ha azt az adott tranzakció kapcsán szeretné kitölteni.</span><span class="sxs-lookup"><span data-stu-id="ca777-124">For Acquisition adjustments, you can enter an offset account or leave it blank to be filled in for the specific transaction.</span></span>    
12. <span data-ttu-id="ca777-125">A Tranzakció típusa mezőben válassza az „Értékcsökkenés” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ca777-125">In the Transaction type field, select 'Depreciation'.</span></span>
13. <span data-ttu-id="ca777-126">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="ca777-126">Click Add.</span></span>
14. <span data-ttu-id="ca777-127">A Könyv mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="ca777-127">In the Book field, enter or select a value.</span></span>
15. <span data-ttu-id="ca777-128">A Fő számla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="ca777-128">In the Main account field, specify the desired values.</span></span>
16. <span data-ttu-id="ca777-129">Az Ellenszámla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="ca777-129">In the Offset account field, specify the desired values.</span></span>
17. <span data-ttu-id="ca777-130">A Tranzakció típusa mezőben válassza az „Értékcsökkenés-kiigazítás” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ca777-130">In the Transaction type field, select 'Depreciation adjustment'.</span></span>
    * <span data-ttu-id="ca777-131">Értékcsökkenés-kiigazítási tranzakciók esetén ugyanazokat a számlákat használjuk, mint amelyeket az Értékcsökkenés tranzakciók esetén.</span><span class="sxs-lookup"><span data-stu-id="ca777-131">For Depreciation adjustment transactions, we will use the same accounts as used for Depreciation transactions.</span></span>  
18. <span data-ttu-id="ca777-132">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="ca777-132">Click Add.</span></span>
19. <span data-ttu-id="ca777-133">A Könyv mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="ca777-133">In the Book field, enter or select a value.</span></span>
20. <span data-ttu-id="ca777-134">A Fő számla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="ca777-134">In the Main account field, specify the desired values.</span></span>
21. <span data-ttu-id="ca777-135">Az Ellenszámla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="ca777-135">In the Offset account field, specify the desired values.</span></span>
22. <span data-ttu-id="ca777-136">A Tranzakció típusa mezőben válassza a „Kivezetés - eladás” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ca777-136">In the Transaction type field, select 'Disposal - sale'.</span></span>
23. <span data-ttu-id="ca777-137">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="ca777-137">Click Add.</span></span>
24. <span data-ttu-id="ca777-138">A Könyv mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="ca777-138">In the Book field, enter or select a value.</span></span>
25. <span data-ttu-id="ca777-139">A Fő számla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="ca777-139">In the Main account field, specify the desired values.</span></span>
    * <span data-ttu-id="ca777-140">A Kivezetésekhez megadhat ellenszámlát, vagy hagyja a mezőt üresen, ha azt az adott tranzakció kapcsán szeretné kitölteni.</span><span class="sxs-lookup"><span data-stu-id="ca777-140">For Disposals, you can enter an offset account or leave it blank to be filled in for the specific transaction.</span></span>  
26. <span data-ttu-id="ca777-141">A Tranzakció típusa mezőben válassza a „Kivezetés - selejtezés” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ca777-141">In the Transaction type field, select 'Disposal - scrap'.</span></span>
    * <span data-ttu-id="ca777-142">Kivezetés - eladás esetén ugyanazokat a számlákat használjuk, mint Kivezetés - selejtezés esetén.</span><span class="sxs-lookup"><span data-stu-id="ca777-142">We will use the same accounts for Disposal sale and Disposal scrap.</span></span>  
27. <span data-ttu-id="ca777-143">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="ca777-143">Click Add.</span></span>
28. <span data-ttu-id="ca777-144">A Könyv mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="ca777-144">In the Book field, enter or select a value.</span></span>
29. <span data-ttu-id="ca777-145">A Fő számla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="ca777-145">In the Main account field, specify the desired values.</span></span>
    * <span data-ttu-id="ca777-146">A Kivezetésekhez megadhat ellenszámlát, vagy hagyja a mezőt üresen, ha azt az adott tranzakció kapcsán szeretné kitölteni.</span><span class="sxs-lookup"><span data-stu-id="ca777-146">For Disposals, you can enter an offset account or leave it blank to be filled in for the specific transaction.</span></span>  
30. <span data-ttu-id="ca777-147">Bontsa ki a Kivezetés szakaszt.</span><span class="sxs-lookup"><span data-stu-id="ca777-147">Expand the Disposal section.</span></span>
    * <span data-ttu-id="ca777-148">Mind az eladás, mind a selejtezés kapcsán kell beállítania kivezetés feladást.</span><span class="sxs-lookup"><span data-stu-id="ca777-148">You must set up disposal posting profiles for both sale and scrap.</span></span>  <span data-ttu-id="ca777-149">A folyamatot az értékesítéses kivezetés tranzakciókkal indítjuk.</span><span class="sxs-lookup"><span data-stu-id="ca777-149">We will start with disposal sale transactions.</span></span>  
31. <span data-ttu-id="ca777-150">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="ca777-150">Click Add.</span></span>
32. <span data-ttu-id="ca777-151">A Könyv mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="ca777-151">In the Book field, enter or select a value.</span></span>
33. <span data-ttu-id="ca777-152">A Feladási érték mezőben válassza a „Beszerzési érték" lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ca777-152">In the Post value field, select 'Acquisition value'.</span></span>
    * <span data-ttu-id="ca777-153">A beszerzési érték minden évre vonatkozóan figyelembe veszi a Beszerzési és Beszerzés-kiigazítási értékeket.</span><span class="sxs-lookup"><span data-stu-id="ca777-153">Acquisition value will address Acquisition and Acquisition adjustment values for all years.</span></span>  <span data-ttu-id="ca777-154">Ön is megadhat számlákat az ilyen tranzakciótípusok kapcsán.</span><span class="sxs-lookup"><span data-stu-id="ca777-154">You can also define accounts for these transaction types separately.</span></span>  
    * <span data-ttu-id="ca777-155">A kivezetési folyamatot be lehet úgy állítani, hogy az - a kivezetés eredményének előjele függvényében - más-más számlát használjon.</span><span class="sxs-lookup"><span data-stu-id="ca777-155">You can set the disposal process to use different accounts depending upon if the disposal results in a gain or loss.</span></span>  <span data-ttu-id="ca777-156">Az Eladás értéktípusát „Mind” értékre állítom, hogy ugyanazokat a számlákat használjam az összes selejtezés-típusra.</span><span class="sxs-lookup"><span data-stu-id="ca777-156">I will set the Sales value type to “All” to use the same accounts for all types of disposals.</span></span>  
34. <span data-ttu-id="ca777-157">A Fő számla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="ca777-157">In the Main account field, specify the desired values.</span></span>
35. <span data-ttu-id="ca777-158">Az Ellenszámla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="ca777-158">In the Offset account field, specify the desired values.</span></span>
36. <span data-ttu-id="ca777-159">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="ca777-159">Click Add.</span></span>
37. <span data-ttu-id="ca777-160">A Könyv mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="ca777-160">In the Book field, enter or select a value.</span></span>
    * <span data-ttu-id="ca777-161">A Feladási érték mezőben válassza az „Értékcsökkenés (előző évek)” elemet.</span><span class="sxs-lookup"><span data-stu-id="ca777-161">In the Post value field, select 'Depreciation (prior years)'.</span></span>  
38. <span data-ttu-id="ca777-162">A Fő számla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="ca777-162">In the Main account field, specify the desired values.</span></span>
39. <span data-ttu-id="ca777-163">Az Ellenszámla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="ca777-163">In the Offset account field, specify the desired values.</span></span>
40. <span data-ttu-id="ca777-164">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="ca777-164">Click Add.</span></span>
41. <span data-ttu-id="ca777-165">A Könyv mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="ca777-165">In the Book field, enter or select a value.</span></span>
42. <span data-ttu-id="ca777-166">A Feladási érték mezőben válassza az „Értékcsökkenés (tárgyév)” elemet.</span><span class="sxs-lookup"><span data-stu-id="ca777-166">In the Post value field, select 'Depreciation (this year)'.</span></span>
43. <span data-ttu-id="ca777-167">A Fő számla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="ca777-167">In the Main account field, specify the desired values.</span></span>
44. <span data-ttu-id="ca777-168">Az Ellenszámla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="ca777-168">In the Offset account field, specify the desired values.</span></span>
45. <span data-ttu-id="ca777-169">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="ca777-169">Click Add.</span></span>
46. <span data-ttu-id="ca777-170">A Könyv mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="ca777-170">In the Book field, enter or select a value.</span></span>
47. <span data-ttu-id="ca777-171">A Feladási érték mezőben válassza az „Értékcsökkenés-kiigazítások (előző évek)” elemet.</span><span class="sxs-lookup"><span data-stu-id="ca777-171">In the Post value field, select 'Depreciation adjustments (prior years)'.</span></span>
48. <span data-ttu-id="ca777-172">A Fő számla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="ca777-172">In the Main account field, specify the desired values.</span></span>
49. <span data-ttu-id="ca777-173">Az Ellenszámla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="ca777-173">In the Offset account field, specify the desired values.</span></span>
50. <span data-ttu-id="ca777-174">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="ca777-174">Click Add.</span></span>
51. <span data-ttu-id="ca777-175">A Könyv mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="ca777-175">In the Book field, enter or select a value.</span></span>
52. <span data-ttu-id="ca777-176">A Feladási érték mezőben válassza az „Értékcsökkenés-kiigazítások (tárgyév)” elemet.</span><span class="sxs-lookup"><span data-stu-id="ca777-176">In the Post value field, select 'Depreciation adjustments (this year)'.</span></span>
53. <span data-ttu-id="ca777-177">A Fő számla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="ca777-177">In the Main account field, specify the desired values.</span></span>
54. <span data-ttu-id="ca777-178">Az Ellenszámla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="ca777-178">In the Offset account field, specify the desired values.</span></span>
55. <span data-ttu-id="ca777-179">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="ca777-179">Click Add.</span></span>
56. <span data-ttu-id="ca777-180">A Könyv mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="ca777-180">In the Book field, enter or select a value.</span></span>
57. <span data-ttu-id="ca777-181">A Feladási érték mezőben válassza a „Nettó könyv szerinti érték" lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ca777-181">In the Post value field, select 'Net book value'.</span></span>
58. <span data-ttu-id="ca777-182">A Fő számla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="ca777-182">In the Main account field, specify the desired values.</span></span>
59. <span data-ttu-id="ca777-183">Az Ellenszámla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="ca777-183">In the Offset account field, specify the desired values.</span></span>
60. <span data-ttu-id="ca777-184">Az értékesítés vagy selejtezés mezőben válassza a „Selejtezés” elemet.</span><span class="sxs-lookup"><span data-stu-id="ca777-184">In the Sale or scrap field, select 'Scrap'.</span></span>
61. <span data-ttu-id="ca777-185">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="ca777-185">Click Add.</span></span>
62. <span data-ttu-id="ca777-186">A Könyv mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="ca777-186">In the Book field, enter or select a value.</span></span>
63. <span data-ttu-id="ca777-187">A Feladási érték mezőben válassza a „Beszerzési érték" lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ca777-187">In the Post value field, select 'Acquisition value'.</span></span>
64. <span data-ttu-id="ca777-188">A Fő számla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="ca777-188">In the Main account field, specify the desired values.</span></span>
65. <span data-ttu-id="ca777-189">Az Ellenszámla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="ca777-189">In the Offset account field, specify the desired values.</span></span>
66. <span data-ttu-id="ca777-190">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="ca777-190">Click Add.</span></span>
67. <span data-ttu-id="ca777-191">A Könyv mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="ca777-191">In the Book field, enter or select a value.</span></span>
    * <span data-ttu-id="ca777-192">A Feladási érték mezőben válassza az „Értékcsökkenés (előző évek)” elemet.</span><span class="sxs-lookup"><span data-stu-id="ca777-192">In Post value field, select 'Depreciation (prior years)'.</span></span>  
68. <span data-ttu-id="ca777-193">A Fő számla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="ca777-193">In the Main account field, specify the desired values.</span></span>
69. <span data-ttu-id="ca777-194">Az Ellenszámla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="ca777-194">In the Offset account field, specify the desired values.</span></span>
70. <span data-ttu-id="ca777-195">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="ca777-195">Click Add.</span></span>
71. <span data-ttu-id="ca777-196">A Könyv mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="ca777-196">In the Book field, enter or select a value.</span></span>
72. <span data-ttu-id="ca777-197">A Feladási érték mezőben válassza az „Értékcsökkenés (tárgyév)” elemet.</span><span class="sxs-lookup"><span data-stu-id="ca777-197">In the Post value field, select 'Depreciation (this year)'.</span></span>
73. <span data-ttu-id="ca777-198">A Fő számla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="ca777-198">In the Main account field, specify the desired values.</span></span>
74. <span data-ttu-id="ca777-199">Az Ellenszámla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="ca777-199">In the Offset account field, specify the desired values.</span></span>
75. <span data-ttu-id="ca777-200">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="ca777-200">Click Add.</span></span>
76. <span data-ttu-id="ca777-201">A Könyv mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="ca777-201">In the Book field, enter or select a value.</span></span>
77. <span data-ttu-id="ca777-202">A Feladási érték mezőben válassza az „Értékcsökkenés-kiigazítások (előző évek)” elemet.</span><span class="sxs-lookup"><span data-stu-id="ca777-202">In the Post value field, select 'Depreciation adjustments (prior years)'.</span></span>
78. <span data-ttu-id="ca777-203">A Fő számla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="ca777-203">In the Main account field, specify the desired values.</span></span>
79. <span data-ttu-id="ca777-204">Az Ellenszámla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="ca777-204">In the Offset account field, specify the desired values.</span></span>
80. <span data-ttu-id="ca777-205">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="ca777-205">Click Add.</span></span>
81. <span data-ttu-id="ca777-206">A Könyv mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="ca777-206">In the Book field, enter or select a value.</span></span>
82. <span data-ttu-id="ca777-207">A Feladási érték mezőben válassza az „Értékcsökkenés-kiigazítások (tárgyév)” elemet.</span><span class="sxs-lookup"><span data-stu-id="ca777-207">In the Post value field, select 'Depreciation adjustments (this year)'.</span></span>
83. <span data-ttu-id="ca777-208">A Fő számla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="ca777-208">In the Main account field, specify the desired values.</span></span>
84. <span data-ttu-id="ca777-209">Az Ellenszámla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="ca777-209">In the Offset account field, specify the desired values.</span></span>
85. <span data-ttu-id="ca777-210">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="ca777-210">Click Add.</span></span>
86. <span data-ttu-id="ca777-211">A Könyv mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="ca777-211">In the Book field, enter or select a value.</span></span>
87. <span data-ttu-id="ca777-212">A Feladási érték mezőben válassza a „Nettó könyv szerinti érték" lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ca777-212">In the Post value field, select 'Net book value'.</span></span>
88. <span data-ttu-id="ca777-213">A Fő számla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="ca777-213">In the Main account field, specify the desired values.</span></span>
89. <span data-ttu-id="ca777-214">Az Ellenszámla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="ca777-214">In the Offset account field, specify the desired values.</span></span>


