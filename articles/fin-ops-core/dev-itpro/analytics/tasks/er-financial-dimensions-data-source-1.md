---
title: ER Pénzügyi dimenziók használata adatforrásként (1. rész – Adatmodell kialakítása)
description: Ez a témakör azt ismerteti, hogyan kell konfigurálni egy Elektronikus jelentési (ER) modellt, amely a pénzügyi dimenziókat használja az ER-jelentések adatforrásaként. (1. rész)
author: NickSelin
manager: AnnBe
ms.date: 05/27/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionTable, ERSolutionCreateDropDialog, ERDataModelDesigner, ERDataModelContentsItemCreationDialog
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 92d29d954debddd509eaba6b710f39b218da2c77
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/30/2021
ms.locfileid: "5092175"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-1---design-data-model"></a><span data-ttu-id="6498c-104">ER Pénzügyi dimenziók használata adatforrásként (1. rész – Adatmodell kialakítása)</span><span class="sxs-lookup"><span data-stu-id="6498c-104">ER Use financial dimensions as a data source (Part 1 - Design data model)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="6498c-105">A következő lépések leírják, hogy egy rendszergazda vagy az elektronikus jelentések fejlesztője miként konfigurálhat egy elektronikusjelentés-modellt (ER-modell) a pénzügyi dimenzió használatához az ER-jelentések adatforrásaként.</span><span class="sxs-lookup"><span data-stu-id="6498c-105">The following steps explain how either a system administrator or electronic reporting developer can configure an Electronic reporting (ER) model to use financial dimensions as a data source for ER reports.</span></span> <span data-ttu-id="6498c-106">Ezeket a lépéseket bármely vállalatban végrehajthatja.</span><span class="sxs-lookup"><span data-stu-id="6498c-106">These steps can be performed in any company.</span></span>

<span data-ttu-id="6498c-107">Hajtsa végre az alábbi lépéseket: először hajtsa végre a „Konfigurációszolgáltató létrehozása és aktívként történő megjelölése” eljárás lépéseit.</span><span class="sxs-lookup"><span data-stu-id="6498c-107">To complete these steps, you must first complete the steps in the procedure, "Create a configuration provider and mark it as active".</span></span>


## <a name="create-a-new-data-model"></a><span data-ttu-id="6498c-108">Új adatmodell létrehozása</span><span class="sxs-lookup"><span data-stu-id="6498c-108">Create a new data model</span></span>
1. <span data-ttu-id="6498c-109">Ugorjon a Szervezeti adminisztráció > Munkaterületek > Elektronikus jelentés pontra.</span><span class="sxs-lookup"><span data-stu-id="6498c-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="6498c-110">Győződjön meg róla, hogy a „Litware, Inc.”</span><span class="sxs-lookup"><span data-stu-id="6498c-110">Make sure that the "Litware, Inc."</span></span> <span data-ttu-id="6498c-111">szolgáltató elérhető és aktívként megjelölt legyen.</span><span class="sxs-lookup"><span data-stu-id="6498c-111">provider is available and marked as active.</span></span>  
2. <span data-ttu-id="6498c-112">Kattintson a Jelentéskészítés konfigurációi lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="6498c-112">Click Reporting configurations.</span></span>
3. <span data-ttu-id="6498c-113">A Konfiguráció létrehozása gombra kattintva megnyithatja a legördülő párbeszédablakot.</span><span class="sxs-lookup"><span data-stu-id="6498c-113">Click Create configuration to open the drop dialog.</span></span>
4. <span data-ttu-id="6498c-114">A Név mezőben írja be a „Pénzügyi dimenziók mintamodell” szöveget.</span><span class="sxs-lookup"><span data-stu-id="6498c-114">In the Name field, type 'Financial dimensions sample model'.</span></span>
5. <span data-ttu-id="6498c-115">Kattintson a Konfiguráció létrehozása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="6498c-115">Click Create configuration.</span></span>
6. <span data-ttu-id="6498c-116">Kattintson a Tervező pontra.</span><span class="sxs-lookup"><span data-stu-id="6498c-116">Click Designer.</span></span>
7. <span data-ttu-id="6498c-117">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="6498c-117">Click New to open the drop dialog.</span></span>
8. <span data-ttu-id="6498c-118">A Név mezőbe írja be a következőt: „Bejegyzés”.</span><span class="sxs-lookup"><span data-stu-id="6498c-118">In the Name field, type 'Entry'.</span></span>
9. <span data-ttu-id="6498c-119">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="6498c-119">Click Add.</span></span>
10. <span data-ttu-id="6498c-120">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="6498c-120">Click New to open the drop dialog.</span></span>
11. <span data-ttu-id="6498c-121">A Név mezőbe írja be a Vállalat szót.</span><span class="sxs-lookup"><span data-stu-id="6498c-121">In the Name field, type 'Company'.</span></span>
12. <span data-ttu-id="6498c-122">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="6498c-122">Click Add.</span></span>
    * <span data-ttu-id="6498c-123">A modellhez hozzáadunk egy új rekordlistát.</span><span class="sxs-lookup"><span data-stu-id="6498c-123">We will add to our model a new record list.</span></span> <span data-ttu-id="6498c-124">Ez a lista (a modellt adatforrásként használó összes ER-jelentés esetében) megmutatja kijelölt pénzügyi dimenziók beállításait.</span><span class="sxs-lookup"><span data-stu-id="6498c-124">This list will expose (for any ER reports using this model as data source) the settings of selected financial dimensions.</span></span> <span data-ttu-id="6498c-125">Minden egyes pénzügyi dimenzió rekordként jelenik meg a listában, és a megfelelő mezők képezik le a dimenzió beállításait.</span><span class="sxs-lookup"><span data-stu-id="6498c-125">Each financial dimension will be presented in this list as a record with appropriate fields representing dimension's setting.</span></span>  
13. <span data-ttu-id="6498c-126">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="6498c-126">Click New to open the drop dialog.</span></span>
14. <span data-ttu-id="6498c-127">A Név mezőbe írja be a következőt: „Dimenziók beállítása”.</span><span class="sxs-lookup"><span data-stu-id="6498c-127">In the Name field, type 'Dimensions setting'.</span></span>
15. <span data-ttu-id="6498c-128">A Cikktípus mezőben válassza ki a „Rekordlista” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6498c-128">In the Item type field, select 'Record list'.</span></span>
16. <span data-ttu-id="6498c-129">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="6498c-129">Click Add.</span></span>
17. <span data-ttu-id="6498c-130">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="6498c-130">Click New to open the drop dialog.</span></span>
18. <span data-ttu-id="6498c-131">A Név mezőbe írja be a következőt: „Kód”.</span><span class="sxs-lookup"><span data-stu-id="6498c-131">In the Name field, type 'Code'.</span></span>
19. <span data-ttu-id="6498c-132">A Cikktípus mezőben válassza ki a „Karakterlánc” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6498c-132">In the Item type field, select 'String'.</span></span>
20. <span data-ttu-id="6498c-133">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="6498c-133">Click Add.</span></span>
21. <span data-ttu-id="6498c-134">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="6498c-134">Click New to open the drop dialog.</span></span>
22. <span data-ttu-id="6498c-135">A Név mezőbe írja be a „Név” szöveget.</span><span class="sxs-lookup"><span data-stu-id="6498c-135">In the Name field, type 'Name'.</span></span>
23. <span data-ttu-id="6498c-136">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="6498c-136">Click Add.</span></span>
24. <span data-ttu-id="6498c-137">A fastruktúrában válassza ki ezt: „Bejegyzés”.</span><span class="sxs-lookup"><span data-stu-id="6498c-137">In the tree, select 'Entry'.</span></span>
25. <span data-ttu-id="6498c-138">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="6498c-138">Click New to open the drop dialog.</span></span>
26. <span data-ttu-id="6498c-139">A Név mezőbe írja be a következőt: „Napló”.</span><span class="sxs-lookup"><span data-stu-id="6498c-139">In the Name field, type 'Journal'.</span></span>
27. <span data-ttu-id="6498c-140">A Cikktípus mezőben válassza ki a „Rekordlista” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6498c-140">In the Item type field, select 'Record list'.</span></span>
28. <span data-ttu-id="6498c-141">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="6498c-141">Click Add.</span></span>
29. <span data-ttu-id="6498c-142">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="6498c-142">Click New to open the drop dialog.</span></span>
30. <span data-ttu-id="6498c-143">A Név mezőbe írja be a következőt: „Köteg”.</span><span class="sxs-lookup"><span data-stu-id="6498c-143">In the Name field, type 'Batch'.</span></span>
31. <span data-ttu-id="6498c-144">A Cikktípus mezőben válassza ki a „Karakterlánc” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6498c-144">In the Item type field, select 'String'.</span></span>
32. <span data-ttu-id="6498c-145">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="6498c-145">Click Add.</span></span>
33. <span data-ttu-id="6498c-146">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="6498c-146">Click New to open the drop dialog.</span></span>
34. <span data-ttu-id="6498c-147">A Név mezőbe írja be a „Tranzakció” szöveget.</span><span class="sxs-lookup"><span data-stu-id="6498c-147">In the Name field, type 'Transaction'.</span></span>
35. <span data-ttu-id="6498c-148">A Cikktípus mezőben válassza ki a „Rekordlista” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6498c-148">In the Item type field, select 'Record list'.</span></span>
36. <span data-ttu-id="6498c-149">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="6498c-149">Click Add.</span></span>
37. <span data-ttu-id="6498c-150">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="6498c-150">Click New to open the drop dialog.</span></span>
38. <span data-ttu-id="6498c-151">A Név mezőbe írja be a következőt: „Dátum”.</span><span class="sxs-lookup"><span data-stu-id="6498c-151">In the Name field, type 'Date'.</span></span>
39. <span data-ttu-id="6498c-152">A Cikktípus mezőben válassza ki a „Dátum” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6498c-152">In the Item type field, select 'Date'.</span></span>
40. <span data-ttu-id="6498c-153">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="6498c-153">Click Add.</span></span>
41. <span data-ttu-id="6498c-154">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="6498c-154">Click New to open the drop dialog.</span></span>
42. <span data-ttu-id="6498c-155">A Név mezőbe írja be a következőt: „Tartozik”.</span><span class="sxs-lookup"><span data-stu-id="6498c-155">In the Name field, type 'Debit'.</span></span>
43. <span data-ttu-id="6498c-156">A Cikktípus mezőben válassza ki a „Valós” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6498c-156">In the Item type field, select 'Real'.</span></span>
44. <span data-ttu-id="6498c-157">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="6498c-157">Click Add.</span></span>
45. <span data-ttu-id="6498c-158">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="6498c-158">Click New to open the drop dialog.</span></span>
46. <span data-ttu-id="6498c-159">A Név mezőbe írja be a „Követel” szöveget.</span><span class="sxs-lookup"><span data-stu-id="6498c-159">In the Name field, type 'Credit'.</span></span>
47. <span data-ttu-id="6498c-160">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="6498c-160">Click Add.</span></span>
48. <span data-ttu-id="6498c-161">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="6498c-161">Click New to open the drop dialog.</span></span>
49. <span data-ttu-id="6498c-162">A név mezőbe írja be a „Pénznem” szöveget.</span><span class="sxs-lookup"><span data-stu-id="6498c-162">In the Name field, type 'Currency'.</span></span>
50. <span data-ttu-id="6498c-163">A Cikktípus mezőben válassza ki a „Karakterlánc” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6498c-163">In the Item type field, select 'String'.</span></span>
51. <span data-ttu-id="6498c-164">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="6498c-164">Click Add.</span></span>
52. <span data-ttu-id="6498c-165">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="6498c-165">Click New to open the drop dialog.</span></span>
53. <span data-ttu-id="6498c-166">A Név mezőbe írja be a következőt: „Bizonylat”.</span><span class="sxs-lookup"><span data-stu-id="6498c-166">In the Name field, type 'Voucher'.</span></span>
54. <span data-ttu-id="6498c-167">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="6498c-167">Click Add.</span></span>
55. <span data-ttu-id="6498c-168">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="6498c-168">Click New to open the drop dialog.</span></span>
56. <span data-ttu-id="6498c-169">A Név mezőbe írja be a következőt: „Dimenzióadatok”.</span><span class="sxs-lookup"><span data-stu-id="6498c-169">In the Name field, type 'Dimensions data'.</span></span>
57. <span data-ttu-id="6498c-170">A Cikktípus mezőben válassza ki a „Rekordlista” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6498c-170">In the Item type field, select 'Record list'.</span></span>
58. <span data-ttu-id="6498c-171">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="6498c-171">Click Add.</span></span>
    * <span data-ttu-id="6498c-172">A modellhez hozzáadtunk egy új rekordlistát.</span><span class="sxs-lookup"><span data-stu-id="6498c-172">We added to our model a new record list.</span></span> <span data-ttu-id="6498c-173">Ez a lista (a modellt adatforrásként használó összes ER-jelentés esetében) megmutatja kijelölt pénzügyi dimenziók értékeit.</span><span class="sxs-lookup"><span data-stu-id="6498c-173">This list will expose (for any ER reports using this model as data source) the values of selected financial dimensions.</span></span> <span data-ttu-id="6498c-174">Minden egyes pénzügyi dimenzió rekordként jelenik meg a listában, és a megfelelő mezők képezik le a dimenzió értékeit.</span><span class="sxs-lookup"><span data-stu-id="6498c-174">Each financial dimension will be presented in this list as a record with appropriate fields representing dimension's values.</span></span> <span data-ttu-id="6498c-175">A dimenzió neve is megjelenik a rekordban mezőként, amely szükség esetén kiválasztási célból használható.</span><span class="sxs-lookup"><span data-stu-id="6498c-175">Dimension name will be also presented in this record as a field to be used, if needed, for selection purposes.</span></span>  
59. <span data-ttu-id="6498c-176">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="6498c-176">Click New to open the drop dialog.</span></span>
60. <span data-ttu-id="6498c-177">A Név mezőbe írja be a következőt: „Kód”.</span><span class="sxs-lookup"><span data-stu-id="6498c-177">In the Name field, type 'Code'.</span></span>
61. <span data-ttu-id="6498c-178">A Cikktípus mezőben válassza ki a „Karakterlánc” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6498c-178">In the Item type field, select 'String'.</span></span>
62. <span data-ttu-id="6498c-179">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="6498c-179">Click Add.</span></span>
63. <span data-ttu-id="6498c-180">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="6498c-180">Click New to open the drop dialog.</span></span>
64. <span data-ttu-id="6498c-181">A Név mezőbe írja be a „Leírás” szöveget.</span><span class="sxs-lookup"><span data-stu-id="6498c-181">In the Name field, type 'Description'.</span></span>
65. <span data-ttu-id="6498c-182">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="6498c-182">Click Add.</span></span>
66. <span data-ttu-id="6498c-183">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="6498c-183">Click New to open the drop dialog.</span></span>
67. <span data-ttu-id="6498c-184">A Név mezőbe írja be a „Név” szöveget.</span><span class="sxs-lookup"><span data-stu-id="6498c-184">In the Name field, type 'Name'.</span></span>
68. <span data-ttu-id="6498c-185">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="6498c-185">Click Add.</span></span>
69. <span data-ttu-id="6498c-186">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="6498c-186">Click Save.</span></span>
70. <span data-ttu-id="6498c-187">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="6498c-187">Close the page.</span></span>

![ER adatmodell-tervező oldal](../media/er-financial-dimensions-guides-data-model.png)

