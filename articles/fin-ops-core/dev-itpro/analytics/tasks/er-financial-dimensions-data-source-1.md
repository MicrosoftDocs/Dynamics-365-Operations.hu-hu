---
title: ER Pénzügyi dimenziók használata adatforrásként (1. rész – Adatmodell kialakítása)
description: Ez a témakör azt ismerteti, hogyan kell konfigurálni egy Elektronikus jelentési (ER) modellt, amely a pénzügyi dimenziókat használja az ER-jelentések adatforrásaként. (1. rész)
author: NickSelin
ms.date: 05/27/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionTable, ERSolutionCreateDropDialog, ERDataModelDesigner, ERDataModelContentsItemCreationDialog
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 92b44532dfae70f03d6686ca1d2f8b6f74345ee6
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5752460"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-1---design-data-model"></a><span data-ttu-id="5b286-104">ER Pénzügyi dimenziók használata adatforrásként (1. rész – Adatmodell kialakítása)</span><span class="sxs-lookup"><span data-stu-id="5b286-104">ER Use financial dimensions as a data source (Part 1 - Design data model)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="5b286-105">A következő lépések leírják, hogy egy rendszergazda vagy az elektronikus jelentések fejlesztője miként konfigurálhat egy elektronikusjelentés-modellt (ER-modell) a pénzügyi dimenzió használatához az ER-jelentések adatforrásaként.</span><span class="sxs-lookup"><span data-stu-id="5b286-105">The following steps explain how either a system administrator or electronic reporting developer can configure an Electronic reporting (ER) model to use financial dimensions as a data source for ER reports.</span></span> <span data-ttu-id="5b286-106">Ezeket a lépéseket bármely vállalatban végrehajthatja.</span><span class="sxs-lookup"><span data-stu-id="5b286-106">These steps can be performed in any company.</span></span>

<span data-ttu-id="5b286-107">Hajtsa végre az alábbi lépéseket: először hajtsa végre a „Konfigurációszolgáltató létrehozása és aktívként történő megjelölése” eljárás lépéseit.</span><span class="sxs-lookup"><span data-stu-id="5b286-107">To complete these steps, you must first complete the steps in the procedure, "Create a configuration provider and mark it as active".</span></span>


## <a name="create-a-new-data-model"></a><span data-ttu-id="5b286-108">Új adatmodell létrehozása</span><span class="sxs-lookup"><span data-stu-id="5b286-108">Create a new data model</span></span>
1. <span data-ttu-id="5b286-109">Ugorjon a Szervezeti adminisztráció > Munkaterületek > Elektronikus jelentés pontra.</span><span class="sxs-lookup"><span data-stu-id="5b286-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="5b286-110">Győződjön meg róla, hogy a „Litware, Inc.”</span><span class="sxs-lookup"><span data-stu-id="5b286-110">Make sure that the "Litware, Inc."</span></span> <span data-ttu-id="5b286-111">szolgáltató elérhető és aktívként megjelölt legyen.</span><span class="sxs-lookup"><span data-stu-id="5b286-111">provider is available and marked as active.</span></span>  
2. <span data-ttu-id="5b286-112">Kattintson a Jelentéskészítés konfigurációi lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5b286-112">Click Reporting configurations.</span></span>
3. <span data-ttu-id="5b286-113">A Konfiguráció létrehozása gombra kattintva megnyithatja a legördülő párbeszédablakot.</span><span class="sxs-lookup"><span data-stu-id="5b286-113">Click Create configuration to open the drop dialog.</span></span>
4. <span data-ttu-id="5b286-114">A Név mezőben írja be a „Pénzügyi dimenziók mintamodell” szöveget.</span><span class="sxs-lookup"><span data-stu-id="5b286-114">In the Name field, type 'Financial dimensions sample model'.</span></span>
5. <span data-ttu-id="5b286-115">Kattintson a Konfiguráció létrehozása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5b286-115">Click Create configuration.</span></span>
6. <span data-ttu-id="5b286-116">Kattintson a Tervező pontra.</span><span class="sxs-lookup"><span data-stu-id="5b286-116">Click Designer.</span></span>
7. <span data-ttu-id="5b286-117">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="5b286-117">Click New to open the drop dialog.</span></span>
8. <span data-ttu-id="5b286-118">A Név mezőbe írja be a következőt: „Bejegyzés”.</span><span class="sxs-lookup"><span data-stu-id="5b286-118">In the Name field, type 'Entry'.</span></span>
9. <span data-ttu-id="5b286-119">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="5b286-119">Click Add.</span></span>
10. <span data-ttu-id="5b286-120">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="5b286-120">Click New to open the drop dialog.</span></span>
11. <span data-ttu-id="5b286-121">A Név mezőbe írja be a Vállalat szót.</span><span class="sxs-lookup"><span data-stu-id="5b286-121">In the Name field, type 'Company'.</span></span>
12. <span data-ttu-id="5b286-122">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="5b286-122">Click Add.</span></span>
    * <span data-ttu-id="5b286-123">A modellhez hozzáadunk egy új rekordlistát.</span><span class="sxs-lookup"><span data-stu-id="5b286-123">We will add to our model a new record list.</span></span> <span data-ttu-id="5b286-124">Ez a lista (a modellt adatforrásként használó összes ER-jelentés esetében) megmutatja kijelölt pénzügyi dimenziók beállításait.</span><span class="sxs-lookup"><span data-stu-id="5b286-124">This list will expose (for any ER reports using this model as data source) the settings of selected financial dimensions.</span></span> <span data-ttu-id="5b286-125">Minden egyes pénzügyi dimenzió rekordként jelenik meg a listában, és a megfelelő mezők képezik le a dimenzió beállításait.</span><span class="sxs-lookup"><span data-stu-id="5b286-125">Each financial dimension will be presented in this list as a record with appropriate fields representing dimension's setting.</span></span>  
13. <span data-ttu-id="5b286-126">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="5b286-126">Click New to open the drop dialog.</span></span>
14. <span data-ttu-id="5b286-127">A Név mezőbe írja be a következőt: „Dimenziók beállítása”.</span><span class="sxs-lookup"><span data-stu-id="5b286-127">In the Name field, type 'Dimensions setting'.</span></span>
15. <span data-ttu-id="5b286-128">A Cikktípus mezőben válassza ki a „Rekordlista” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5b286-128">In the Item type field, select 'Record list'.</span></span>
16. <span data-ttu-id="5b286-129">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="5b286-129">Click Add.</span></span>
17. <span data-ttu-id="5b286-130">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="5b286-130">Click New to open the drop dialog.</span></span>
18. <span data-ttu-id="5b286-131">A Név mezőbe írja be a következőt: „Kód”.</span><span class="sxs-lookup"><span data-stu-id="5b286-131">In the Name field, type 'Code'.</span></span>
19. <span data-ttu-id="5b286-132">A Cikktípus mezőben válassza ki a „Karakterlánc” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5b286-132">In the Item type field, select 'String'.</span></span>
20. <span data-ttu-id="5b286-133">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="5b286-133">Click Add.</span></span>
21. <span data-ttu-id="5b286-134">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="5b286-134">Click New to open the drop dialog.</span></span>
22. <span data-ttu-id="5b286-135">A Név mezőbe írja be a „Név” szöveget.</span><span class="sxs-lookup"><span data-stu-id="5b286-135">In the Name field, type 'Name'.</span></span>
23. <span data-ttu-id="5b286-136">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="5b286-136">Click Add.</span></span>
24. <span data-ttu-id="5b286-137">A fastruktúrában válassza ki ezt: „Bejegyzés”.</span><span class="sxs-lookup"><span data-stu-id="5b286-137">In the tree, select 'Entry'.</span></span>
25. <span data-ttu-id="5b286-138">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="5b286-138">Click New to open the drop dialog.</span></span>
26. <span data-ttu-id="5b286-139">A Név mezőbe írja be a következőt: „Napló”.</span><span class="sxs-lookup"><span data-stu-id="5b286-139">In the Name field, type 'Journal'.</span></span>
27. <span data-ttu-id="5b286-140">A Cikktípus mezőben válassza ki a „Rekordlista” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5b286-140">In the Item type field, select 'Record list'.</span></span>
28. <span data-ttu-id="5b286-141">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="5b286-141">Click Add.</span></span>
29. <span data-ttu-id="5b286-142">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="5b286-142">Click New to open the drop dialog.</span></span>
30. <span data-ttu-id="5b286-143">A Név mezőbe írja be a következőt: „Köteg”.</span><span class="sxs-lookup"><span data-stu-id="5b286-143">In the Name field, type 'Batch'.</span></span>
31. <span data-ttu-id="5b286-144">A Cikktípus mezőben válassza ki a „Karakterlánc” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5b286-144">In the Item type field, select 'String'.</span></span>
32. <span data-ttu-id="5b286-145">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="5b286-145">Click Add.</span></span>
33. <span data-ttu-id="5b286-146">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="5b286-146">Click New to open the drop dialog.</span></span>
34. <span data-ttu-id="5b286-147">A Név mezőbe írja be a „Tranzakció” szöveget.</span><span class="sxs-lookup"><span data-stu-id="5b286-147">In the Name field, type 'Transaction'.</span></span>
35. <span data-ttu-id="5b286-148">A Cikktípus mezőben válassza ki a „Rekordlista” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5b286-148">In the Item type field, select 'Record list'.</span></span>
36. <span data-ttu-id="5b286-149">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="5b286-149">Click Add.</span></span>
37. <span data-ttu-id="5b286-150">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="5b286-150">Click New to open the drop dialog.</span></span>
38. <span data-ttu-id="5b286-151">A Név mezőbe írja be a következőt: „Dátum”.</span><span class="sxs-lookup"><span data-stu-id="5b286-151">In the Name field, type 'Date'.</span></span>
39. <span data-ttu-id="5b286-152">A Cikktípus mezőben válassza ki a „Dátum” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5b286-152">In the Item type field, select 'Date'.</span></span>
40. <span data-ttu-id="5b286-153">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="5b286-153">Click Add.</span></span>
41. <span data-ttu-id="5b286-154">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="5b286-154">Click New to open the drop dialog.</span></span>
42. <span data-ttu-id="5b286-155">A Név mezőbe írja be a következőt: „Tartozik”.</span><span class="sxs-lookup"><span data-stu-id="5b286-155">In the Name field, type 'Debit'.</span></span>
43. <span data-ttu-id="5b286-156">A Cikktípus mezőben válassza ki a „Valós” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5b286-156">In the Item type field, select 'Real'.</span></span>
44. <span data-ttu-id="5b286-157">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="5b286-157">Click Add.</span></span>
45. <span data-ttu-id="5b286-158">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="5b286-158">Click New to open the drop dialog.</span></span>
46. <span data-ttu-id="5b286-159">A Név mezőbe írja be a „Követel” szöveget.</span><span class="sxs-lookup"><span data-stu-id="5b286-159">In the Name field, type 'Credit'.</span></span>
47. <span data-ttu-id="5b286-160">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="5b286-160">Click Add.</span></span>
48. <span data-ttu-id="5b286-161">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="5b286-161">Click New to open the drop dialog.</span></span>
49. <span data-ttu-id="5b286-162">A név mezőbe írja be a „Pénznem” szöveget.</span><span class="sxs-lookup"><span data-stu-id="5b286-162">In the Name field, type 'Currency'.</span></span>
50. <span data-ttu-id="5b286-163">A Cikktípus mezőben válassza ki a „Karakterlánc” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5b286-163">In the Item type field, select 'String'.</span></span>
51. <span data-ttu-id="5b286-164">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="5b286-164">Click Add.</span></span>
52. <span data-ttu-id="5b286-165">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="5b286-165">Click New to open the drop dialog.</span></span>
53. <span data-ttu-id="5b286-166">A Név mezőbe írja be a következőt: „Bizonylat”.</span><span class="sxs-lookup"><span data-stu-id="5b286-166">In the Name field, type 'Voucher'.</span></span>
54. <span data-ttu-id="5b286-167">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="5b286-167">Click Add.</span></span>
55. <span data-ttu-id="5b286-168">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="5b286-168">Click New to open the drop dialog.</span></span>
56. <span data-ttu-id="5b286-169">A Név mezőbe írja be a következőt: „Dimenzióadatok”.</span><span class="sxs-lookup"><span data-stu-id="5b286-169">In the Name field, type 'Dimensions data'.</span></span>
57. <span data-ttu-id="5b286-170">A Cikktípus mezőben válassza ki a „Rekordlista” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5b286-170">In the Item type field, select 'Record list'.</span></span>
58. <span data-ttu-id="5b286-171">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="5b286-171">Click Add.</span></span>
    * <span data-ttu-id="5b286-172">A modellhez hozzáadtunk egy új rekordlistát.</span><span class="sxs-lookup"><span data-stu-id="5b286-172">We added to our model a new record list.</span></span> <span data-ttu-id="5b286-173">Ez a lista (a modellt adatforrásként használó összes ER-jelentés esetében) megmutatja kijelölt pénzügyi dimenziók értékeit.</span><span class="sxs-lookup"><span data-stu-id="5b286-173">This list will expose (for any ER reports using this model as data source) the values of selected financial dimensions.</span></span> <span data-ttu-id="5b286-174">Minden egyes pénzügyi dimenzió rekordként jelenik meg a listában, és a megfelelő mezők képezik le a dimenzió értékeit.</span><span class="sxs-lookup"><span data-stu-id="5b286-174">Each financial dimension will be presented in this list as a record with appropriate fields representing dimension's values.</span></span> <span data-ttu-id="5b286-175">A dimenzió neve is megjelenik a rekordban mezőként, amely szükség esetén kiválasztási célból használható.</span><span class="sxs-lookup"><span data-stu-id="5b286-175">Dimension name will be also presented in this record as a field to be used, if needed, for selection purposes.</span></span>  
59. <span data-ttu-id="5b286-176">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="5b286-176">Click New to open the drop dialog.</span></span>
60. <span data-ttu-id="5b286-177">A Név mezőbe írja be a következőt: „Kód”.</span><span class="sxs-lookup"><span data-stu-id="5b286-177">In the Name field, type 'Code'.</span></span>
61. <span data-ttu-id="5b286-178">A Cikktípus mezőben válassza ki a „Karakterlánc” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5b286-178">In the Item type field, select 'String'.</span></span>
62. <span data-ttu-id="5b286-179">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="5b286-179">Click Add.</span></span>
63. <span data-ttu-id="5b286-180">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="5b286-180">Click New to open the drop dialog.</span></span>
64. <span data-ttu-id="5b286-181">A Név mezőbe írja be a „Leírás” szöveget.</span><span class="sxs-lookup"><span data-stu-id="5b286-181">In the Name field, type 'Description'.</span></span>
65. <span data-ttu-id="5b286-182">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="5b286-182">Click Add.</span></span>
66. <span data-ttu-id="5b286-183">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="5b286-183">Click New to open the drop dialog.</span></span>
67. <span data-ttu-id="5b286-184">A Név mezőbe írja be a „Név” szöveget.</span><span class="sxs-lookup"><span data-stu-id="5b286-184">In the Name field, type 'Name'.</span></span>
68. <span data-ttu-id="5b286-185">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="5b286-185">Click Add.</span></span>
69. <span data-ttu-id="5b286-186">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="5b286-186">Click Save.</span></span>
70. <span data-ttu-id="5b286-187">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="5b286-187">Close the page.</span></span>

![ER adatmodell-tervező oldal](../media/er-financial-dimensions-guides-data-model.png)



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]