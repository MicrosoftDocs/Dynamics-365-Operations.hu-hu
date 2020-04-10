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
ms.openlocfilehash: b02496ebb06e0c2eb644fc7ef3280ca4eca05923
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/18/2020
ms.locfileid: "3142024"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-1---design-data-model"></a><span data-ttu-id="59f93-103">ER Pénzügyi dimenziók használata adatforrásként (1. rész – Adatmodell kialakítása)</span><span class="sxs-lookup"><span data-stu-id="59f93-103">ER Use financial dimensions as a data source (Part 1 - Design data model)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="59f93-104">A következő lépések leírják, hogy egy rendszergazda vagy az elektronikus jelentések fejlesztője miként konfigurálhat egy elektronikusjelentés-modellt (ER-modell) a pénzügyi dimenzió használatához az ER-jelentések adatforrásaként.</span><span class="sxs-lookup"><span data-stu-id="59f93-104">The following steps explain how either a system administrator or electronic reporting developer can configure an Electronic reporting (ER) model to use financial dimensions as a data source for ER reports.</span></span> <span data-ttu-id="59f93-105">Ezeket a lépéseket bármely vállalatban végrehajthatja.</span><span class="sxs-lookup"><span data-stu-id="59f93-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="59f93-106">Hajtsa végre az alábbi lépéseket: először hajtsa végre a „Konfigurációszolgáltató létrehozása és aktívként történő megjelölése” eljárás lépéseit.</span><span class="sxs-lookup"><span data-stu-id="59f93-106">To complete these steps, you must first complete the steps in the procedure, "Create a configuration provider and mark it as active".</span></span>


## <a name="create-a-new-data-model"></a><span data-ttu-id="59f93-107">Új adatmodell létrehozása</span><span class="sxs-lookup"><span data-stu-id="59f93-107">Create a new data model</span></span>
1. <span data-ttu-id="59f93-108">Ugorjon a Szervezeti adminisztráció > Munkaterületek > Elektronikus jelentés pontra.</span><span class="sxs-lookup"><span data-stu-id="59f93-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="59f93-109">Győződjön meg róla, hogy a „Litware, Inc.”</span><span class="sxs-lookup"><span data-stu-id="59f93-109">Make sure that the "Litware, Inc."</span></span> <span data-ttu-id="59f93-110">szolgáltató elérhető és aktívként megjelölt legyen.</span><span class="sxs-lookup"><span data-stu-id="59f93-110">provider is available and marked as active.</span></span>  
2. <span data-ttu-id="59f93-111">Kattintson a Jelentéskészítés konfigurációi lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="59f93-111">Click Reporting configurations.</span></span>
3. <span data-ttu-id="59f93-112">A Konfiguráció létrehozása gombra kattintva megnyithatja a legördülő párbeszédablakot.</span><span class="sxs-lookup"><span data-stu-id="59f93-112">Click Create configuration to open the drop dialog.</span></span>
4. <span data-ttu-id="59f93-113">A Név mezőben írja be a „Pénzügyi dimenziók mintamodell” szöveget.</span><span class="sxs-lookup"><span data-stu-id="59f93-113">In the Name field, type 'Financial dimensions sample model'.</span></span>
5. <span data-ttu-id="59f93-114">Kattintson a Konfiguráció létrehozása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="59f93-114">Click Create configuration.</span></span>
6. <span data-ttu-id="59f93-115">Kattintson a Tervező pontra.</span><span class="sxs-lookup"><span data-stu-id="59f93-115">Click Designer.</span></span>
7. <span data-ttu-id="59f93-116">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="59f93-116">Click New to open the drop dialog.</span></span>
8. <span data-ttu-id="59f93-117">A Név mezőbe írja be a következőt: „Bejegyzés”.</span><span class="sxs-lookup"><span data-stu-id="59f93-117">In the Name field, type 'Entry'.</span></span>
9. <span data-ttu-id="59f93-118">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="59f93-118">Click Add.</span></span>
10. <span data-ttu-id="59f93-119">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="59f93-119">Click New to open the drop dialog.</span></span>
11. <span data-ttu-id="59f93-120">A Név mezőbe írja be a Vállalat szót.</span><span class="sxs-lookup"><span data-stu-id="59f93-120">In the Name field, type 'Company'.</span></span>
12. <span data-ttu-id="59f93-121">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="59f93-121">Click Add.</span></span>
    * <span data-ttu-id="59f93-122">A modellhez hozzáadunk egy új rekordlistát.</span><span class="sxs-lookup"><span data-stu-id="59f93-122">We will add to our model a new record list.</span></span> <span data-ttu-id="59f93-123">Ez a lista (a modellt adatforrásként használó összes ER-jelentés esetében) megmutatja kijelölt pénzügyi dimenziók beállításait.</span><span class="sxs-lookup"><span data-stu-id="59f93-123">This list will expose (for any ER reports using this model as data source) the settings of selected financial dimensions.</span></span> <span data-ttu-id="59f93-124">Minden egyes pénzügyi dimenzió rekordként jelenik meg a listában, és a megfelelő mezők képezik le a dimenzió beállításait.</span><span class="sxs-lookup"><span data-stu-id="59f93-124">Each financial dimension will be presented in this list as a record with appropriate fields representing dimension's setting.</span></span>  
13. <span data-ttu-id="59f93-125">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="59f93-125">Click New to open the drop dialog.</span></span>
14. <span data-ttu-id="59f93-126">A Név mezőbe írja be a következőt: „Dimenziók beállítása”.</span><span class="sxs-lookup"><span data-stu-id="59f93-126">In the Name field, type 'Dimensions setting'.</span></span>
15. <span data-ttu-id="59f93-127">A Cikktípus mezőben válassza ki a „Rekordlista” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="59f93-127">In the Item type field, select 'Record list'.</span></span>
16. <span data-ttu-id="59f93-128">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="59f93-128">Click Add.</span></span>
17. <span data-ttu-id="59f93-129">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="59f93-129">Click New to open the drop dialog.</span></span>
18. <span data-ttu-id="59f93-130">A Név mezőbe írja be a következőt: „Kód”.</span><span class="sxs-lookup"><span data-stu-id="59f93-130">In the Name field, type 'Code'.</span></span>
19. <span data-ttu-id="59f93-131">A Cikktípus mezőben válassza ki a „Karakterlánc” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="59f93-131">In the Item type field, select 'String'.</span></span>
20. <span data-ttu-id="59f93-132">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="59f93-132">Click Add.</span></span>
21. <span data-ttu-id="59f93-133">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="59f93-133">Click New to open the drop dialog.</span></span>
22. <span data-ttu-id="59f93-134">A Név mezőbe írja be a „Név” szöveget.</span><span class="sxs-lookup"><span data-stu-id="59f93-134">In the Name field, type 'Name'.</span></span>
23. <span data-ttu-id="59f93-135">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="59f93-135">Click Add.</span></span>
24. <span data-ttu-id="59f93-136">A fastruktúrában válassza ki ezt: „Bejegyzés”.</span><span class="sxs-lookup"><span data-stu-id="59f93-136">In the tree, select 'Entry'.</span></span>
25. <span data-ttu-id="59f93-137">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="59f93-137">Click New to open the drop dialog.</span></span>
26. <span data-ttu-id="59f93-138">A Név mezőbe írja be a következőt: „Napló”.</span><span class="sxs-lookup"><span data-stu-id="59f93-138">In the Name field, type 'Journal'.</span></span>
27. <span data-ttu-id="59f93-139">A Cikktípus mezőben válassza ki a „Rekordlista” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="59f93-139">In the Item type field, select 'Record list'.</span></span>
28. <span data-ttu-id="59f93-140">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="59f93-140">Click Add.</span></span>
29. <span data-ttu-id="59f93-141">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="59f93-141">Click New to open the drop dialog.</span></span>
30. <span data-ttu-id="59f93-142">A Név mezőbe írja be a következőt: „Köteg”.</span><span class="sxs-lookup"><span data-stu-id="59f93-142">In the Name field, type 'Batch'.</span></span>
31. <span data-ttu-id="59f93-143">A Cikktípus mezőben válassza ki a „Karakterlánc” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="59f93-143">In the Item type field, select 'String'.</span></span>
32. <span data-ttu-id="59f93-144">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="59f93-144">Click Add.</span></span>
33. <span data-ttu-id="59f93-145">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="59f93-145">Click New to open the drop dialog.</span></span>
34. <span data-ttu-id="59f93-146">A Név mezőbe írja be a „Tranzakció” szöveget.</span><span class="sxs-lookup"><span data-stu-id="59f93-146">In the Name field, type 'Transaction'.</span></span>
35. <span data-ttu-id="59f93-147">A Cikktípus mezőben válassza ki a „Rekordlista” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="59f93-147">In the Item type field, select 'Record list'.</span></span>
36. <span data-ttu-id="59f93-148">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="59f93-148">Click Add.</span></span>
37. <span data-ttu-id="59f93-149">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="59f93-149">Click New to open the drop dialog.</span></span>
38. <span data-ttu-id="59f93-150">A Név mezőbe írja be a következőt: „Dátum”.</span><span class="sxs-lookup"><span data-stu-id="59f93-150">In the Name field, type 'Date'.</span></span>
39. <span data-ttu-id="59f93-151">A Cikktípus mezőben válassza ki a „Dátum” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="59f93-151">In the Item type field, select 'Date'.</span></span>
40. <span data-ttu-id="59f93-152">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="59f93-152">Click Add.</span></span>
41. <span data-ttu-id="59f93-153">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="59f93-153">Click New to open the drop dialog.</span></span>
42. <span data-ttu-id="59f93-154">A Név mezőbe írja be a következőt: „Tartozik”.</span><span class="sxs-lookup"><span data-stu-id="59f93-154">In the Name field, type 'Debit'.</span></span>
43. <span data-ttu-id="59f93-155">A Cikktípus mezőben válassza ki a „Valós” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="59f93-155">In the Item type field, select 'Real'.</span></span>
44. <span data-ttu-id="59f93-156">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="59f93-156">Click Add.</span></span>
45. <span data-ttu-id="59f93-157">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="59f93-157">Click New to open the drop dialog.</span></span>
46. <span data-ttu-id="59f93-158">A Név mezőbe írja be a „Követel” szöveget.</span><span class="sxs-lookup"><span data-stu-id="59f93-158">In the Name field, type 'Credit'.</span></span>
47. <span data-ttu-id="59f93-159">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="59f93-159">Click Add.</span></span>
48. <span data-ttu-id="59f93-160">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="59f93-160">Click New to open the drop dialog.</span></span>
49. <span data-ttu-id="59f93-161">A név mezőbe írja be a „Pénznem” szöveget.</span><span class="sxs-lookup"><span data-stu-id="59f93-161">In the Name field, type 'Currency'.</span></span>
50. <span data-ttu-id="59f93-162">A Cikktípus mezőben válassza ki a „Karakterlánc” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="59f93-162">In the Item type field, select 'String'.</span></span>
51. <span data-ttu-id="59f93-163">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="59f93-163">Click Add.</span></span>
52. <span data-ttu-id="59f93-164">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="59f93-164">Click New to open the drop dialog.</span></span>
53. <span data-ttu-id="59f93-165">A Név mezőbe írja be a következőt: „Bizonylat”.</span><span class="sxs-lookup"><span data-stu-id="59f93-165">In the Name field, type 'Voucher'.</span></span>
54. <span data-ttu-id="59f93-166">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="59f93-166">Click Add.</span></span>
55. <span data-ttu-id="59f93-167">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="59f93-167">Click New to open the drop dialog.</span></span>
56. <span data-ttu-id="59f93-168">A Név mezőbe írja be a következőt: „Dimenzióadatok”.</span><span class="sxs-lookup"><span data-stu-id="59f93-168">In the Name field, type 'Dimensions data'.</span></span>
57. <span data-ttu-id="59f93-169">A Cikktípus mezőben válassza ki a „Rekordlista” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="59f93-169">In the Item type field, select 'Record list'.</span></span>
58. <span data-ttu-id="59f93-170">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="59f93-170">Click Add.</span></span>
    * <span data-ttu-id="59f93-171">A modellhez hozzáadtunk egy új rekordlistát.</span><span class="sxs-lookup"><span data-stu-id="59f93-171">We added to our model a new record list.</span></span> <span data-ttu-id="59f93-172">Ez a lista (a modellt adatforrásként használó összes ER-jelentés esetében) megmutatja kijelölt pénzügyi dimenziók értékeit.</span><span class="sxs-lookup"><span data-stu-id="59f93-172">This list will expose (for any ER reports using this model as data source) the values of selected financial dimensions.</span></span> <span data-ttu-id="59f93-173">Minden egyes pénzügyi dimenzió rekordként jelenik meg a listában, és a megfelelő mezők képezik le a dimenzió értékeit.</span><span class="sxs-lookup"><span data-stu-id="59f93-173">Each financial dimension will be presented in this list as a record with appropriate fields representing dimension's values.</span></span> <span data-ttu-id="59f93-174">A dimenzió neve is megjelenik a rekordban mezőként, amely szükség esetén kiválasztási célból használható.</span><span class="sxs-lookup"><span data-stu-id="59f93-174">Dimension name will be also presented in this record as a field to be used, if needed, for selection purposes.</span></span>  
59. <span data-ttu-id="59f93-175">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="59f93-175">Click New to open the drop dialog.</span></span>
60. <span data-ttu-id="59f93-176">A Név mezőbe írja be a következőt: „Kód”.</span><span class="sxs-lookup"><span data-stu-id="59f93-176">In the Name field, type 'Code'.</span></span>
61. <span data-ttu-id="59f93-177">A Cikktípus mezőben válassza ki a „Karakterlánc” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="59f93-177">In the Item type field, select 'String'.</span></span>
62. <span data-ttu-id="59f93-178">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="59f93-178">Click Add.</span></span>
63. <span data-ttu-id="59f93-179">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="59f93-179">Click New to open the drop dialog.</span></span>
64. <span data-ttu-id="59f93-180">A Név mezőbe írja be a „Leírás” szöveget.</span><span class="sxs-lookup"><span data-stu-id="59f93-180">In the Name field, type 'Description'.</span></span>
65. <span data-ttu-id="59f93-181">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="59f93-181">Click Add.</span></span>
66. <span data-ttu-id="59f93-182">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="59f93-182">Click New to open the drop dialog.</span></span>
67. <span data-ttu-id="59f93-183">A Név mezőbe írja be a „Név” szöveget.</span><span class="sxs-lookup"><span data-stu-id="59f93-183">In the Name field, type 'Name'.</span></span>
68. <span data-ttu-id="59f93-184">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="59f93-184">Click Add.</span></span>
69. <span data-ttu-id="59f93-185">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="59f93-185">Click Save.</span></span>
70. <span data-ttu-id="59f93-186">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="59f93-186">Close the page.</span></span>

