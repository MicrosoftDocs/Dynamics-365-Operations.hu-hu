---
title: ER Pénzügyi dimenziók használata adatforrásként (1. rész – Adatmodell kialakítása)
description: A következő lépések leírják, hogy egy rendszergazda vagy az elektronikus jelentések fejlesztője miként konfigurálhat egy elektronikusjelentés-modellt (ER-modell) a pénzügyi dimenzió használatához az ER-jelentések adatforrásaként.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionTable, ERSolutionCreateDropDialog, ERDataModelDesigner, ERDataModelContentsItemCreationDialog
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 84f546b73eefe3ead78c6ab3fdbbc05d0db5fef5
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "339510"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-1-design-data-model"></a><span data-ttu-id="5b873-103">ER Pénzügyi dimenziók használata adatforrásként (1. rész: Adatmodell kialakítása)</span><span class="sxs-lookup"><span data-stu-id="5b873-103">ER Use financial dimensions as a data source (Part 1: Design data model)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="5b873-104">A következő lépések leírják, hogy egy rendszergazda vagy az elektronikus jelentések fejlesztője miként konfigurálhat egy elektronikusjelentés-modellt (ER-modell) a pénzügyi dimenzió használatához az ER-jelentések adatforrásaként.</span><span class="sxs-lookup"><span data-stu-id="5b873-104">The following steps explain how either a system administrator or electronic reporting developer can configure an Electronic reporting (ER) model to use financial dimensions as a data source for ER reports.</span></span> <span data-ttu-id="5b873-105">Ezeket a lépéseket bármely vállalatban végrehajthatja.</span><span class="sxs-lookup"><span data-stu-id="5b873-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="5b873-106">Hajtsa végre az alábbi lépéseket: először hajtsa végre a „Konfigurációszolgáltató létrehozása és aktívként történő megjelölése” eljárás lépéseit.</span><span class="sxs-lookup"><span data-stu-id="5b873-106">To complete these steps, you must first complete the steps in the procedure, “Create a configuration provider and mark it as active”.</span></span>


## <a name="create-a-new-data-model"></a><span data-ttu-id="5b873-107">Új adatmodell létrehozása</span><span class="sxs-lookup"><span data-stu-id="5b873-107">Create a new data model</span></span>
1. <span data-ttu-id="5b873-108">Ugorjon a Szervezeti adminisztráció > Munkaterületek > Elektronikus jelentés pontra.</span><span class="sxs-lookup"><span data-stu-id="5b873-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="5b873-109">Győződjön meg róla, hogy a Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="5b873-109">Make sure that the “Litware, Inc.”</span></span> <span data-ttu-id="5b873-110">szolgáltató elérhető és aktívként megjelölt legyen.</span><span class="sxs-lookup"><span data-stu-id="5b873-110">provider is available and marked as active.</span></span>  
2. <span data-ttu-id="5b873-111">Kattintson a Jelentéskészítés konfigurációi lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5b873-111">Click Reporting configurations.</span></span>
3. <span data-ttu-id="5b873-112">A Konfiguráció létrehozása gombra kattintva megnyithatja a legördülő párbeszédablakot.</span><span class="sxs-lookup"><span data-stu-id="5b873-112">Click Create configuration to open the drop dialog.</span></span>
4. <span data-ttu-id="5b873-113">A Név mezőben írja be a „Pénzügyi dimenziók mintamodell” szöveget.</span><span class="sxs-lookup"><span data-stu-id="5b873-113">In the Name field, type 'Financial dimensions sample model'.</span></span>
5. <span data-ttu-id="5b873-114">Kattintson a Konfiguráció létrehozása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5b873-114">Click Create configuration.</span></span>
6. <span data-ttu-id="5b873-115">Kattintson a Tervező pontra.</span><span class="sxs-lookup"><span data-stu-id="5b873-115">Click Designer.</span></span>
7. <span data-ttu-id="5b873-116">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="5b873-116">Click New to open the drop dialog.</span></span>
8. <span data-ttu-id="5b873-117">A Név mezőbe írja be a következőt: „Bejegyzés”.</span><span class="sxs-lookup"><span data-stu-id="5b873-117">In the Name field, type 'Entry'.</span></span>
9. <span data-ttu-id="5b873-118">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="5b873-118">Click Add.</span></span>
10. <span data-ttu-id="5b873-119">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="5b873-119">Click New to open the drop dialog.</span></span>
11. <span data-ttu-id="5b873-120">A Név mezőbe írja be a Vállalat szót.</span><span class="sxs-lookup"><span data-stu-id="5b873-120">In the Name field, type 'Company'.</span></span>
12. <span data-ttu-id="5b873-121">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="5b873-121">Click Add.</span></span>
    * <span data-ttu-id="5b873-122">A modellhez hozzáadunk egy új rekordlistát.</span><span class="sxs-lookup"><span data-stu-id="5b873-122">We will add to our model a new record list.</span></span> <span data-ttu-id="5b873-123">Ez a lista (a modellt adatforrásként használó összes ER-jelentés esetében) megmutatja kijelölt pénzügyi dimenziók beállításait.</span><span class="sxs-lookup"><span data-stu-id="5b873-123">This list will expose (for any ER reports using this model as data source) the settings of selected financial dimensions.</span></span> <span data-ttu-id="5b873-124">Minden egyes pénzügyi dimenzió rekordként jelenik meg a listában, és a megfelelő mezők képezik le a dimenzió beállításait.</span><span class="sxs-lookup"><span data-stu-id="5b873-124">Each financial dimension will be presented in this list as a record with appropriate fields representing dimension’s setting.</span></span>  
13. <span data-ttu-id="5b873-125">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="5b873-125">Click New to open the drop dialog.</span></span>
14. <span data-ttu-id="5b873-126">A Név mezőbe írja be a következőt: „Dimenziók beállítása”.</span><span class="sxs-lookup"><span data-stu-id="5b873-126">In the Name field, type 'Dimensions setting'.</span></span>
15. <span data-ttu-id="5b873-127">A Cikktípus mezőben válassza ki a „Rekordlista” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5b873-127">In the Item type field, select 'Record list'.</span></span>
16. <span data-ttu-id="5b873-128">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="5b873-128">Click Add.</span></span>
17. <span data-ttu-id="5b873-129">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="5b873-129">Click New to open the drop dialog.</span></span>
18. <span data-ttu-id="5b873-130">A Név mezőbe írja be a következőt: „Kód”.</span><span class="sxs-lookup"><span data-stu-id="5b873-130">In the Name field, type 'Code'.</span></span>
19. <span data-ttu-id="5b873-131">A Cikktípus mezőben válassza ki a „Karakterlánc” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5b873-131">In the Item type field, select 'String'.</span></span>
20. <span data-ttu-id="5b873-132">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="5b873-132">Click Add.</span></span>
21. <span data-ttu-id="5b873-133">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="5b873-133">Click New to open the drop dialog.</span></span>
22. <span data-ttu-id="5b873-134">A Név mezőbe írja be a „Név” szöveget.</span><span class="sxs-lookup"><span data-stu-id="5b873-134">In the Name field, type 'Name'.</span></span>
23. <span data-ttu-id="5b873-135">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="5b873-135">Click Add.</span></span>
24. <span data-ttu-id="5b873-136">A fastruktúrában válassza ki ezt: „Bejegyzés”.</span><span class="sxs-lookup"><span data-stu-id="5b873-136">In the tree, select 'Entry'.</span></span>
25. <span data-ttu-id="5b873-137">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="5b873-137">Click New to open the drop dialog.</span></span>
26. <span data-ttu-id="5b873-138">A Név mezőbe írja be a következőt: „Napló”.</span><span class="sxs-lookup"><span data-stu-id="5b873-138">In the Name field, type 'Journal'.</span></span>
27. <span data-ttu-id="5b873-139">A Cikktípus mezőben válassza ki a „Rekordlista” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5b873-139">In the Item type field, select 'Record list'.</span></span>
28. <span data-ttu-id="5b873-140">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="5b873-140">Click Add.</span></span>
29. <span data-ttu-id="5b873-141">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="5b873-141">Click New to open the drop dialog.</span></span>
30. <span data-ttu-id="5b873-142">A Név mezőbe írja be a következőt: „Köteg”.</span><span class="sxs-lookup"><span data-stu-id="5b873-142">In the Name field, type 'Batch'.</span></span>
31. <span data-ttu-id="5b873-143">A Cikktípus mezőben válassza ki a „Karakterlánc” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5b873-143">In the Item type field, select 'String'.</span></span>
32. <span data-ttu-id="5b873-144">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="5b873-144">Click Add.</span></span>
33. <span data-ttu-id="5b873-145">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="5b873-145">Click New to open the drop dialog.</span></span>
34. <span data-ttu-id="5b873-146">A Név mezőbe írja be a „Tranzakció” szöveget.</span><span class="sxs-lookup"><span data-stu-id="5b873-146">In the Name field, type 'Transaction'.</span></span>
35. <span data-ttu-id="5b873-147">A Cikktípus mezőben válassza ki a „Rekordlista” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5b873-147">In the Item type field, select 'Record list'.</span></span>
36. <span data-ttu-id="5b873-148">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="5b873-148">Click Add.</span></span>
37. <span data-ttu-id="5b873-149">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="5b873-149">Click New to open the drop dialog.</span></span>
38. <span data-ttu-id="5b873-150">A Név mezőbe írja be a következőt: „Dátum”.</span><span class="sxs-lookup"><span data-stu-id="5b873-150">In the Name field, type 'Date'.</span></span>
39. <span data-ttu-id="5b873-151">A Cikktípus mezőben válassza ki a „Dátum” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5b873-151">In the Item type field, select 'Date'.</span></span>
40. <span data-ttu-id="5b873-152">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="5b873-152">Click Add.</span></span>
41. <span data-ttu-id="5b873-153">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="5b873-153">Click New to open the drop dialog.</span></span>
42. <span data-ttu-id="5b873-154">A Név mezőbe írja be a következőt: „Tartozik”.</span><span class="sxs-lookup"><span data-stu-id="5b873-154">In the Name field, type 'Debit'.</span></span>
43. <span data-ttu-id="5b873-155">A Cikktípus mezőben válassza ki a „Valós” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5b873-155">In the Item type field, select 'Real'.</span></span>
44. <span data-ttu-id="5b873-156">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="5b873-156">Click Add.</span></span>
45. <span data-ttu-id="5b873-157">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="5b873-157">Click New to open the drop dialog.</span></span>
46. <span data-ttu-id="5b873-158">A Név mezőbe írja be a „Követel” szöveget.</span><span class="sxs-lookup"><span data-stu-id="5b873-158">In the Name field, type 'Credit'.</span></span>
47. <span data-ttu-id="5b873-159">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="5b873-159">Click Add.</span></span>
48. <span data-ttu-id="5b873-160">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="5b873-160">Click New to open the drop dialog.</span></span>
49. <span data-ttu-id="5b873-161">A név mezőbe írja be a „Pénznem” szöveget.</span><span class="sxs-lookup"><span data-stu-id="5b873-161">In the Name field, type 'Currency'.</span></span>
50. <span data-ttu-id="5b873-162">A Cikktípus mezőben válassza ki a „Karakterlánc” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5b873-162">In the Item type field, select 'String'.</span></span>
51. <span data-ttu-id="5b873-163">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="5b873-163">Click Add.</span></span>
52. <span data-ttu-id="5b873-164">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="5b873-164">Click New to open the drop dialog.</span></span>
53. <span data-ttu-id="5b873-165">A Név mezőbe írja be a következőt: „Bizonylat”.</span><span class="sxs-lookup"><span data-stu-id="5b873-165">In the Name field, type 'Voucher'.</span></span>
54. <span data-ttu-id="5b873-166">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="5b873-166">Click Add.</span></span>
55. <span data-ttu-id="5b873-167">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="5b873-167">Click New to open the drop dialog.</span></span>
56. <span data-ttu-id="5b873-168">A Név mezőbe írja be a következőt: „Dimenzióadatok”.</span><span class="sxs-lookup"><span data-stu-id="5b873-168">In the Name field, type 'Dimensions data'.</span></span>
57. <span data-ttu-id="5b873-169">A Cikktípus mezőben válassza ki a „Rekordlista” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5b873-169">In the Item type field, select 'Record list'.</span></span>
58. <span data-ttu-id="5b873-170">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="5b873-170">Click Add.</span></span>
    * <span data-ttu-id="5b873-171">A modellhez hozzáadtunk egy új rekordlistát.</span><span class="sxs-lookup"><span data-stu-id="5b873-171">We added to our model a new record list.</span></span> <span data-ttu-id="5b873-172">Ez a lista (a modellt adatforrásként használó összes ER-jelentés esetében) megmutatja kijelölt pénzügyi dimenziók értékeit.</span><span class="sxs-lookup"><span data-stu-id="5b873-172">This list will expose (for any ER reports using this model as data source) the values of selected financial dimensions.</span></span> <span data-ttu-id="5b873-173">Minden egyes pénzügyi dimenzió rekordként jelenik meg a listában, és a megfelelő mezők képezik le a dimenzió értékeit.</span><span class="sxs-lookup"><span data-stu-id="5b873-173">Each financial dimension will be presented in this list as a record with appropriate fields representing dimension’s values.</span></span> <span data-ttu-id="5b873-174">A dimenzió neve is megjelenik a rekordban mezőként, amely szükség esetén kiválasztási célból használható.</span><span class="sxs-lookup"><span data-stu-id="5b873-174">Dimension name will be also presented in this record as a field to be used, if needed, for selection purposes.</span></span>  
59. <span data-ttu-id="5b873-175">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="5b873-175">Click New to open the drop dialog.</span></span>
60. <span data-ttu-id="5b873-176">A Név mezőbe írja be a következőt: „Kód”.</span><span class="sxs-lookup"><span data-stu-id="5b873-176">In the Name field, type 'Code'.</span></span>
61. <span data-ttu-id="5b873-177">A Cikktípus mezőben válassza ki a „Karakterlánc” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5b873-177">In the Item type field, select 'String'.</span></span>
62. <span data-ttu-id="5b873-178">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="5b873-178">Click Add.</span></span>
63. <span data-ttu-id="5b873-179">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="5b873-179">Click New to open the drop dialog.</span></span>
64. <span data-ttu-id="5b873-180">A Név mezőbe írja be a „Leírás” szöveget.</span><span class="sxs-lookup"><span data-stu-id="5b873-180">In the Name field, type 'Description'.</span></span>
65. <span data-ttu-id="5b873-181">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="5b873-181">Click Add.</span></span>
66. <span data-ttu-id="5b873-182">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="5b873-182">Click New to open the drop dialog.</span></span>
67. <span data-ttu-id="5b873-183">A Név mezőbe írja be a „Név” szöveget.</span><span class="sxs-lookup"><span data-stu-id="5b873-183">In the Name field, type 'Name'.</span></span>
68. <span data-ttu-id="5b873-184">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="5b873-184">Click Add.</span></span>
69. <span data-ttu-id="5b873-185">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="5b873-185">Click Save.</span></span>
70. <span data-ttu-id="5b873-186">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="5b873-186">Close the page.</span></span>

