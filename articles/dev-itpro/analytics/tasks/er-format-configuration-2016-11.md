--- 
title: "ER – Formátumkonfiguráció létrehozása (2016. november)"
description: "A következő lépések leírják, hogy egy Rendszergazda vagy Elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználó miként hozhat létre formátum konfigurációt az Elektronikus jelentéshez (ER)."
author: NickSelin
manager: AnnBe
ms.date: 11/27/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f004451a260b5be6c15c3975cd9e63ba9c1a7a2e
ms.openlocfilehash: 6fa5023a29c95ab9f10d8aacd51edc1a06c3c152
ms.contentlocale: hu-hu
ms.lasthandoff: 02/06/2019

---
# <a name="er-create-a-format-configuration-november-2016"></a><span data-ttu-id="e739d-103">ER – Formátumkonfiguráció létrehozása (2016. november)</span><span class="sxs-lookup"><span data-stu-id="e739d-103">ER Create a format configuration (November 2016)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e739d-104">A következő lépések leírják, hogy egy Rendszergazda vagy Elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználó miként hozhat létre formátum konfigurációt az Elektronikus jelentéshez (ER).</span><span class="sxs-lookup"><span data-stu-id="e739d-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can create a format configuration for Electronic reporting (ER).</span></span> <span data-ttu-id="e739d-105">Ez a formátum konfiguráció határozza meg a kifizetések feldolgozására használt elektronikus dokumentumok formátumát.</span><span class="sxs-lookup"><span data-stu-id="e739d-105">This format configuration will define the format of electronic documents that are used for processing payments.</span></span> <span data-ttu-id="e739d-106">Ebben a példában létrehoz egy formátum konfigurációt a mintavállalatra, a Litware, Inc.-re vonatkozóan. Hajtsa végre az alábbi lépéseket: Először végezze el a „Modell leképezése a kiválasztott adatforrásokhoz” műveletsorban ismertetett lépéseket.</span><span class="sxs-lookup"><span data-stu-id="e739d-106">In this example, you will create a format configuration for sample company, Litware, Inc. To complete these steps, you must first complete the steps in the “Map model to selected datasources” procedure.</span></span>


## <a name="create-a-new-format-configuration"></a><span data-ttu-id="e739d-107">Új formátumkonfiguráció létrehozása</span><span class="sxs-lookup"><span data-stu-id="e739d-107">Create a new format configuration</span></span>
1. <span data-ttu-id="e739d-108">Ugorjon a **Szervezeti adminisztráció > Munkaterületek > Elektronikus jelentés** pontra.</span><span class="sxs-lookup"><span data-stu-id="e739d-108">Go to **Organization administration > Workspaces > Electronic reporting**.</span></span>
2. <span data-ttu-id="e739d-109">Kattintson a **Jelentéskészítés konfigurációi** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e739d-109">Click **Reporting configurations**.</span></span>
3. <span data-ttu-id="e739d-110">A fán válassza ki a következőt: **Payments (simplified model)**.</span><span class="sxs-lookup"><span data-stu-id="e739d-110">In the tree, select **Payments (simplified model)**.</span></span>
4. <span data-ttu-id="e739d-111">A **Konfiguráció létrehozása** gombra kattintva megnyithatja a legördülő párbeszédablakot.</span><span class="sxs-lookup"><span data-stu-id="e739d-111">Click **Create configuration** to open the drop dialog.</span></span>

 > [!NOTE]
 > <span data-ttu-id="e739d-112">Ha nem látja a **Konfiguráció létrehozása** lehetőséget, a tervező módot engedélyeznie kell a **elektronikus bevallási paraméterek** lapon.</span><span class="sxs-lookup"><span data-stu-id="e739d-112">If you don't see **Create configuration**, you must enable design mode on the **Electronic reporting parameters** page.</span></span> 
 
5. <span data-ttu-id="e739d-113">Az **Új** mezőbe írja be a **PaymentModel modellen alapuló formátum** kifejezést.</span><span class="sxs-lookup"><span data-stu-id="e739d-113">In the **New** field, enter **Format based on data model PaymentModel**.</span></span>
6. <span data-ttu-id="e739d-114">A **Név** mezőbe írja be a **BACS (UK fictitious)** szöveget.</span><span class="sxs-lookup"><span data-stu-id="e739d-114">In the **Name** field, type **BACS (UK fictitious)**.</span></span>
7. <span data-ttu-id="e739d-115">A **Leírás** mezőbe írja be a **BACS vendor payment format (UK fictitious)** szöveget.</span><span class="sxs-lookup"><span data-stu-id="e739d-115">In the **Description** field, type **BACS vendor payment format (UK fictitious)**.</span></span>
    * <span data-ttu-id="e739d-116">Az aktív konfigurációs szolgáltató automatikusan megjelenik itt.</span><span class="sxs-lookup"><span data-stu-id="e739d-116">The active configuration provider is automatically entered here.</span></span> <span data-ttu-id="e739d-117">Ez a szolgáltató tartja majd karban ezt a konfigurációt.</span><span class="sxs-lookup"><span data-stu-id="e739d-117">This provider will be able to maintain this configuration.</span></span> <span data-ttu-id="e739d-118">Más szolgáltatók is használhatják ezt a konfigurációt, de nem tudják majd karbantartani.</span><span class="sxs-lookup"><span data-stu-id="e739d-118">Other providers can use this configuration, but will not be able to maintain it.</span></span>  
    * <span data-ttu-id="e739d-119">Elektronikusdokumentum-formátum definiálható.</span><span class="sxs-lookup"><span data-stu-id="e739d-119">A particular format of electronic document can be defined.</span></span> <span data-ttu-id="e739d-120">Ezt a mezőt hagyja üresen, ha azt szeretné, hogy futásidőben választhassa ki a formátumot.</span><span class="sxs-lookup"><span data-stu-id="e739d-120">Leave this field blank if you want to select a format at run-time.</span></span>  
8. <span data-ttu-id="e739d-121">Az **Adatmodell mezőben** adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="e739d-121">In the **Data model definition** field, enter or select a value.</span></span>
9. <span data-ttu-id="e739d-122">Kattintson a **Konfiguráció létrehozása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e739d-122">Click **Create configuration**.</span></span> <span data-ttu-id="e739d-123">Új konfiguráció létrehozása megtörtént.</span><span class="sxs-lookup"><span data-stu-id="e739d-123">A new configuration has been created.</span></span> <span data-ttu-id="e739d-124">Egy vázlat verzió használható a tervezési formátum tárolására az elektronikus dokumentumok kezeléséhez.</span><span class="sxs-lookup"><span data-stu-id="e739d-124">The draft version can be used to store the design format for managing electronic documents.</span></span>  

 > [!NOTE]
 > <span data-ttu-id="e739d-125">Ha nem látja a **Konfiguráció létrehozása** lehetőséget, a tervező módot engedélyeznie kell a **elektronikus bevallási paraméterek** lapon.</span><span class="sxs-lookup"><span data-stu-id="e739d-125">If you don't see **Create configuration**, you must enable design mode on the **Electronic reporting parameters** page.</span></span>


## <a name="design-the-format-of-an-electronic-document"></a><span data-ttu-id="e739d-126">Elektronikus dokumentumok formátumának tervezése</span><span class="sxs-lookup"><span data-stu-id="e739d-126">Design the format of an electronic document</span></span>
1. <span data-ttu-id="e739d-127">Kattintson a **Tervező** pontra.</span><span class="sxs-lookup"><span data-stu-id="e739d-127">Click **Designer**.</span></span>
2. <span data-ttu-id="e739d-128">Kattintson a **Gyökér hozzáadása** lehetőségre a legördülő párbeszédpanel megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="e739d-128">Click **Add root** to open the drop dialog.</span></span>
3. <span data-ttu-id="e739d-129">A fában válassza ki a **Common\File** csomópontot.</span><span class="sxs-lookup"><span data-stu-id="e739d-129">In the tree, select **Common\File**.</span></span>
4. <span data-ttu-id="e739d-130">A **Név** mezőbe írja be az **Xml** szót.</span><span class="sxs-lookup"><span data-stu-id="e739d-130">In the **Name** field, type **Xml**.</span></span>
5. <span data-ttu-id="e739d-131">A **Kódolás** mezőbe írja be az **UTF-8** szót.</span><span class="sxs-lookup"><span data-stu-id="e739d-131">In the **Encoding** field, type **UTF-8**.</span></span>
6. <span data-ttu-id="e739d-132">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="e739d-132">Click **OK**.</span></span>
7. <span data-ttu-id="e739d-133">Kattintson a **Hozzáadás** gombra.</span><span class="sxs-lookup"><span data-stu-id="e739d-133">Click **Add**.</span></span>
8. <span data-ttu-id="e739d-134">A fában válassza ki az **XML\Element** csomópontot.</span><span class="sxs-lookup"><span data-stu-id="e739d-134">In the tree, select **XML\Element**.</span></span>
9. <span data-ttu-id="e739d-135">A **Név** mezőbe írja be a **Message** szöveget.</span><span class="sxs-lookup"><span data-stu-id="e739d-135">In the **Name** field, type **Message**.</span></span>
10. <span data-ttu-id="e739d-136">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="e739d-136">Click **OK**.</span></span>
11. <span data-ttu-id="e739d-137">A fastruktúrában válassza ki ezt: **Xml\Üzenet**.</span><span class="sxs-lookup"><span data-stu-id="e739d-137">In the tree, select **Xml\Message**.</span></span>
12. <span data-ttu-id="e739d-138">Kattintson az **Elem hozzáadása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e739d-138">Click **Add Element**.</span></span>
13. <span data-ttu-id="e739d-139">A **Név** mezőbe írja be a **ProcessingDate** szót.</span><span class="sxs-lookup"><span data-stu-id="e739d-139">In the **Name** field, type **ProcessingDate**.</span></span>
14. <span data-ttu-id="e739d-140">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="e739d-140">Click **OK**.</span></span>
15. <span data-ttu-id="e739d-141">Kattintson az **Elem hozzáadása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e739d-141">Click **Add Element**.</span></span>
16. <span data-ttu-id="e739d-142">A Név mezőbe írja be a **MessageId** szöveget.</span><span class="sxs-lookup"><span data-stu-id="e739d-142">In the Name field, type **MessageId**.</span></span>
17. <span data-ttu-id="e739d-143">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="e739d-143">Click **OK**.</span></span>
18. <span data-ttu-id="e739d-144">Kattintson az **Elem hozzáadása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e739d-144">Click **Add Element**.</span></span>
19. <span data-ttu-id="e739d-145">A **Név** mezőbe írja be a **Fizetések** szöveget.</span><span class="sxs-lookup"><span data-stu-id="e739d-145">In the **Name** field, type **Payments**.</span></span>
20. <span data-ttu-id="e739d-146">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="e739d-146">Click **OK**.</span></span>
21. <span data-ttu-id="e739d-147">A fastruktúrában válassza ki ezt: **Xml\Üzenet\Fizetések**.</span><span class="sxs-lookup"><span data-stu-id="e739d-147">In the tree, select **Xml\Message\Payments**.</span></span>
22. <span data-ttu-id="e739d-148">Kattintson az **Elem hozzáadása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e739d-148">Click **Add Element**.</span></span>
23. <span data-ttu-id="e739d-149">A **Név mezőbe** írja be az **Item** szót.</span><span class="sxs-lookup"><span data-stu-id="e739d-149">In the **Name** field, type **Item**.</span></span>
24. <span data-ttu-id="e739d-150">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="e739d-150">Click **OK**.</span></span>
25. <span data-ttu-id="e739d-151">A fastruktúrában válassza ki ezt: **Xml\Message\Payments\Item**.</span><span class="sxs-lookup"><span data-stu-id="e739d-151">In the tree, select **Xml\Message\Payments\Item**.</span></span>
26. <span data-ttu-id="e739d-152">Kattintson a **Hozzáadás** gombra.</span><span class="sxs-lookup"><span data-stu-id="e739d-152">Click **Add**.</span></span>
27. <span data-ttu-id="e739d-153">A fastruktúrában válassza ki az **XML\Attribute** elemet.</span><span class="sxs-lookup"><span data-stu-id="e739d-153">In the tree, select **XML\Attribute**.</span></span>
28. <span data-ttu-id="e739d-154">A Név mezőbe írja be az **Id** szöveget.</span><span class="sxs-lookup"><span data-stu-id="e739d-154">In the Name field, type **Id**.</span></span>
29. <span data-ttu-id="e739d-155">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="e739d-155">Click **OK**.</span></span>
30. <span data-ttu-id="e739d-156">Kattintson a **Hozzáadás** gombra.</span><span class="sxs-lookup"><span data-stu-id="e739d-156">Click **Add**.</span></span>
31. <span data-ttu-id="e739d-157">A fában válassza ki az **XML\Element** csomópontot.</span><span class="sxs-lookup"><span data-stu-id="e739d-157">In the tree, select **XML\Element**.</span></span>
32. <span data-ttu-id="e739d-158">A Név mezőbe írja be a **Vendor** szöveget.</span><span class="sxs-lookup"><span data-stu-id="e739d-158">In the Name field, type **Vendor**.</span></span>
33. <span data-ttu-id="e739d-159">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="e739d-159">Click **OK**.</span></span>
34. <span data-ttu-id="e739d-160">A fastruktúrában válassza ki ezt: **Xml\Message\Payments\Item\Vendor**.</span><span class="sxs-lookup"><span data-stu-id="e739d-160">In the tree, select **Xml\Message\Payments\Item\Vendor**.</span></span>
35. <span data-ttu-id="e739d-161">Kattintson az **Elem hozzáadása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e739d-161">Click **Add Element**.</span></span>
36. <span data-ttu-id="e739d-162">A Név mezőbe írja be a **Name** szöveget.</span><span class="sxs-lookup"><span data-stu-id="e739d-162">In the Name field, type **Name**.</span></span>
37. <span data-ttu-id="e739d-163">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="e739d-163">Click **OK**.</span></span>
38. <span data-ttu-id="e739d-164">Kattintson az **Elem hozzáadása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e739d-164">Click **Add Element**.</span></span>
39. <span data-ttu-id="e739d-165">A **Név** mezőbe írja be a **Bank** szöveget.</span><span class="sxs-lookup"><span data-stu-id="e739d-165">In the **Name** field, type **Bank**.</span></span>
40. <span data-ttu-id="e739d-166">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="e739d-166">Click **OK**.</span></span>
41. <span data-ttu-id="e739d-167">A fastruktúrában válassza ki ezt: **Xml\Message\Payments\Item\Vendor\Bank**.</span><span class="sxs-lookup"><span data-stu-id="e739d-167">In the tree, select **Xml\Message\Payments\Item\Vendor\Bank**.</span></span>
42. <span data-ttu-id="e739d-168">Kattintson az **Elem hozzáadása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e739d-168">Click **Add Element**.</span></span>
43. <span data-ttu-id="e739d-169">A **Név** mezőbe írja be a **RoutingNumber** szöveget.</span><span class="sxs-lookup"><span data-stu-id="e739d-169">In the **Name** field, type **RoutingNumber**.</span></span>
44. <span data-ttu-id="e739d-170">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="e739d-170">Click **OK**.</span></span>
45. <span data-ttu-id="e739d-171">Kattintson az **Elem hozzáadása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e739d-171">Click **Add Element**.</span></span>
46. <span data-ttu-id="e739d-172">A **Név** mezőbe írja be az **AccountNumber** szöveget.</span><span class="sxs-lookup"><span data-stu-id="e739d-172">In the **Name** field, type **AccountNumber**.</span></span>
47. <span data-ttu-id="e739d-173">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="e739d-173">Click **OK**.</span></span>
48. <span data-ttu-id="e739d-174">A fastruktúrában válassza ki ezt: **Xml\Message\Payments\Item\Vendor**.</span><span class="sxs-lookup"><span data-stu-id="e739d-174">In the tree, select **Xml\Message\Payments\Item\Vendor**.</span></span>
49. <span data-ttu-id="e739d-175">Kattintson a **Másolás** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e739d-175">Click **Copy**.</span></span>
50. <span data-ttu-id="e739d-176">A fastruktúrában válassza ki ezt: **Xml\Message\Payments\Item**.</span><span class="sxs-lookup"><span data-stu-id="e739d-176">In the tree, select **Xml\Message\Payments\Item**.</span></span>
51. <span data-ttu-id="e739d-177">Kattintson a **Beillesztés** parancsra.</span><span class="sxs-lookup"><span data-stu-id="e739d-177">Click **Paste**.</span></span>
52. <span data-ttu-id="e739d-178">A **Név** mezőbe írja be a **Payer** szöveget.</span><span class="sxs-lookup"><span data-stu-id="e739d-178">In the **Name** field, type **Payer**.</span></span>
53. <span data-ttu-id="e739d-179">A fastruktúrában válassza ki ezt: **Xml\Message\Payments\Item**.</span><span class="sxs-lookup"><span data-stu-id="e739d-179">In the tree, select **Xml\Message\Payments\Item**.</span></span>
54. <span data-ttu-id="e739d-180">Kattintson az **Elem hozzáadása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e739d-180">Click **Add Element**.</span></span>
55. <span data-ttu-id="e739d-181">A **Név** mezőbe írja be a **Pénznem** szöveget.</span><span class="sxs-lookup"><span data-stu-id="e739d-181">In the **Name** field, type **Currency**.</span></span>
56. <span data-ttu-id="e739d-182">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="e739d-182">Click **OK**.</span></span>
57. <span data-ttu-id="e739d-183">Kattintson az **Elem hozzáadása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e739d-183">Click **Add Element**.</span></span>
58. <span data-ttu-id="e739d-184">A **Név** mezőbe írja be a **Leírás** szöveget.</span><span class="sxs-lookup"><span data-stu-id="e739d-184">In the **Name** field, type **Description**.</span></span>
59. <span data-ttu-id="e739d-185">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="e739d-185">Click **OK**.</span></span>
60. <span data-ttu-id="e739d-186">Kattintson az **Elem hozzáadása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e739d-186">Click **Add Element**.</span></span>
61. <span data-ttu-id="e739d-187">A Név mezőbe írja be a **TransDate** szöveget.</span><span class="sxs-lookup"><span data-stu-id="e739d-187">In the Name field, type **TransDate**.</span></span>
62. <span data-ttu-id="e739d-188">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="e739d-188">Click **OK**.</span></span>
63. <span data-ttu-id="e739d-189">Kattintson az **Elem hozzáadása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e739d-189">Click **Add Element**.</span></span>
64. <span data-ttu-id="e739d-190">A Név mezőbe írja be az **Amount** szöveget.</span><span class="sxs-lookup"><span data-stu-id="e739d-190">In the Name field, type **Amount**.</span></span>
65. <span data-ttu-id="e739d-191">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="e739d-191">Click **OK**.</span></span>

## <a name="prepare-format-components-for-mapping-to-data-model-elements"></a><span data-ttu-id="e739d-192">Formátum-összetevők előkészítése adatmodell-elemek leképezéséhez</span><span class="sxs-lookup"><span data-stu-id="e739d-192">Prepare format components for mapping to data model elements</span></span>
1. <span data-ttu-id="e739d-193">A fastruktúrában válassza ki ezt: **Xml\Message\ProcessingDate**.</span><span class="sxs-lookup"><span data-stu-id="e739d-193">In the tree, select **Xml\Message\ProcessingDate**.</span></span>
2. <span data-ttu-id="e739d-194">A **Hozzáadás** gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="e739d-194">Click **Add** to open the drop dialog.</span></span>
3. <span data-ttu-id="e739d-195">A fastruktúrában válassza ki ezt: **Text\DateTime**.</span><span class="sxs-lookup"><span data-stu-id="e739d-195">In the tree, select **Text\DateTime**.</span></span>
4. <span data-ttu-id="e739d-196">A **Formátum** mezőbe írja be az **yyyy-MM-dd** szöveget.</span><span class="sxs-lookup"><span data-stu-id="e739d-196">In the **Format** field, type **yyyy-MM-dd**.</span></span>
5. <span data-ttu-id="e739d-197">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="e739d-197">Click **OK**.</span></span>
6. <span data-ttu-id="e739d-198">A fastruktúrában válassza ki ezt: **Xml\Message\Payments\Item\TransDate**.</span><span class="sxs-lookup"><span data-stu-id="e739d-198">In the tree, select **Xml\Message\Payments\Item\TransDate**.</span></span>
7. <span data-ttu-id="e739d-199">Kattintson a **Dátum/idő hozzáadása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e739d-199">Click **Add DateTime**.</span></span>
8. <span data-ttu-id="e739d-200">A **Formátum** mezőbe írja be az **yyyy-MM-dd** szöveget.</span><span class="sxs-lookup"><span data-stu-id="e739d-200">In the **Format** field, type **yyyy-MM-dd**.</span></span>
9. <span data-ttu-id="e739d-201">A **DateTime** típus mezőben válassza ki a **Dátum** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e739d-201">In the **DateTime** type field, select **Date**.</span></span>
10. <span data-ttu-id="e739d-202">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="e739d-202">Click **OK**.</span></span>
11. <span data-ttu-id="e739d-203">A fastruktúrában válassza ki ezt: **Xml\Message\MessageId**.</span><span class="sxs-lookup"><span data-stu-id="e739d-203">In the tree, select **Xml\Message\MessageId**.</span></span>
12. <span data-ttu-id="e739d-204">A **Hozzáadás** gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="e739d-204">Click **Add** to open the drop dialog.</span></span>
13. <span data-ttu-id="e739d-205">A fában válassza ki ezt: **Text\String**.</span><span class="sxs-lookup"><span data-stu-id="e739d-205">In the tree, select **Text\String**.</span></span>
14. <span data-ttu-id="e739d-206">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="e739d-206">Click **OK**.</span></span>
15. <span data-ttu-id="e739d-207">A fastruktúrában válassza ki ezt: **Xml\Message\Payments\Item\Vendor\Name**.</span><span class="sxs-lookup"><span data-stu-id="e739d-207">In the tree, select **Xml\Message\Payments\Item\Vendor\Name**.</span></span>
16. <span data-ttu-id="e739d-208">Kattintson a **Karakterlánc hozzáadása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e739d-208">Click **Add String**.</span></span>
17. <span data-ttu-id="e739d-209">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="e739d-209">Click **OK**.</span></span>
18. <span data-ttu-id="e739d-210">A fastruktúrában válassza ki ezt: **Xml\Message\Payments\Item\Vendor\Bank\RoutingNumber**.</span><span class="sxs-lookup"><span data-stu-id="e739d-210">In the tree, select **Xml\Message\Payments\Item\Vendor\Bank\RoutingNumber**.</span></span>
19. <span data-ttu-id="e739d-211">Kattintson a **Karakterlánc hozzáadása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e739d-211">Click **Add String**.</span></span>
20. <span data-ttu-id="e739d-212">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="e739d-212">Click **OK**.</span></span>
21. <span data-ttu-id="e739d-213">A fastruktúrában válassza ki ezt: **Xml\Message\Payments\Item\Vendor\Bank\AccountNumber**.</span><span class="sxs-lookup"><span data-stu-id="e739d-213">In the tree, select **Xml\Message\Payments\Item\Vendor\Bank\AccountNumber**.</span></span>
22. <span data-ttu-id="e739d-214">Kattintson a **Karakterlánc hozzáadása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e739d-214">Click **Add String**.</span></span>
23. <span data-ttu-id="e739d-215">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="e739d-215">Click **OK**.</span></span>
24. <span data-ttu-id="e739d-216">A fastruktúrában válassza ki ezt: **Xml\Message\Payments\Item\Payer\Name**.</span><span class="sxs-lookup"><span data-stu-id="e739d-216">In the tree, select **Xml\Message\Payments\Item\Payer\Name**.</span></span>
25. <span data-ttu-id="e739d-217">Kattintson a **Karakterlánc hozzáadása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e739d-217">Click **Add String**.</span></span>
26. <span data-ttu-id="e739d-218">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="e739d-218">Click **OK**.</span></span>
27. <span data-ttu-id="e739d-219">A fastruktúrában válassza ki ezt: **Xml\Message\Payments\Item\Payer\Bank\RoutingNumber**.</span><span class="sxs-lookup"><span data-stu-id="e739d-219">In the tree, select **Xml\Message\Payments\Item\Payer\Bank\RoutingNumber**.</span></span>
28. <span data-ttu-id="e739d-220">Kattintson a **Karakterlánc hozzáadása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e739d-220">Click **Add String**.</span></span>
29. <span data-ttu-id="e739d-221">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="e739d-221">Click **OK**.</span></span>
30. <span data-ttu-id="e739d-222">A fastruktúrában válassza ki ezt: **Xml\Message\Payments\Item\Payer\Bank\AccountNumber**.</span><span class="sxs-lookup"><span data-stu-id="e739d-222">In the tree, select **Xml\Message\Payments\Item\Payer\Bank\AccountNumber**.</span></span>
31. <span data-ttu-id="e739d-223">Kattintson a **Karakterlánc hozzáadása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e739d-223">Click **Add String**.</span></span>
32. <span data-ttu-id="e739d-224">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="e739d-224">Click **OK**.</span></span>
33. <span data-ttu-id="e739d-225">A fastruktúrában válassza ki ezt: **Xml\Message\Payments\Item\Currency**.</span><span class="sxs-lookup"><span data-stu-id="e739d-225">In the tree, select **Xml\Message\Payments\Item\Currency**.</span></span>
34. <span data-ttu-id="e739d-226">Kattintson a **Karakterlánc hozzáadása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e739d-226">Click **Add String**.</span></span>
35. <span data-ttu-id="e739d-227">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="e739d-227">Click **OK**.</span></span>
36. <span data-ttu-id="e739d-228">A fastruktúrában válassza ki ezt: **Xml\Message\Payments\Item\Description**.</span><span class="sxs-lookup"><span data-stu-id="e739d-228">In the tree, select **Xml\Message\Payments\Item\Description**.</span></span>
37. <span data-ttu-id="e739d-229">Kattintson a **Karakterlánc hozzáadása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e739d-229">Click **Add String**.</span></span>
38. <span data-ttu-id="e739d-230">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="e739d-230">Click **OK**.</span></span>
39. <span data-ttu-id="e739d-231">A fastruktúrában válassza ki ezt: **Xml\Message\Payments\Item\Amount**.</span><span class="sxs-lookup"><span data-stu-id="e739d-231">In the tree, select **Xml\Message\Payments\Item\Amount**.</span></span>
40. <span data-ttu-id="e739d-232">Kattintson a **Karakterlánc hozzáadása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e739d-232">Click **Add String**.</span></span>
41. <span data-ttu-id="e739d-233">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="e739d-233">Click **OK**.</span></span>
42. <span data-ttu-id="e739d-234">Kattintson a **Mentés** gombra.</span><span class="sxs-lookup"><span data-stu-id="e739d-234">Click **Save**.</span></span>
43. <span data-ttu-id="e739d-235">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="e739d-235">Close the page.</span></span>


