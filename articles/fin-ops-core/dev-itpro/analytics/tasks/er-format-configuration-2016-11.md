---
title: ER – Formátumkonfiguráció létrehozása (2016. november)
description: Ez a témakör bemutatja, hogyan lehet formátumkonfigurációt létrehozni az Elektronikus jelentéskészítéshez (ER).
author: NickSelin
ms.date: 08/02/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 46686b9e4f6197f565a324a9d03cbb695b6a933b
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5749069"
---
# <a name="er-create-a-format-configuration-november-2016"></a><span data-ttu-id="eed98-103">ER – Formátumkonfiguráció létrehozása (2016. november)</span><span class="sxs-lookup"><span data-stu-id="eed98-103">ER Create a format configuration (November 2016)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="eed98-104">Ez a témakör leírja, hogy egy Rendszergazda vagy Elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználó miként hozhat létre formátum konfigurációt az Elektronikus jelentéshez (ER).</span><span class="sxs-lookup"><span data-stu-id="eed98-104">This topic explains how a user in the System Administrator or Electronic Reporting Developer role can create a format configuration for Electronic reporting (ER).</span></span> <span data-ttu-id="eed98-105">Ez a formátum konfiguráció határozza meg a kifizetések feldolgozására használt elektronikus dokumentumok formátumát.</span><span class="sxs-lookup"><span data-stu-id="eed98-105">This format configuration will define the format of electronic documents that are used for processing payments.</span></span> <span data-ttu-id="eed98-106">Ebben a példában létrehoz egy formátum konfigurációt a mintavállalatra, a Litware, Inc.-re vonatkozóan. Hajtsa végre az alábbi lépéseket: Először végezze el a „Modell leképezése a kiválasztott adatforrásokhoz” műveletsorban ismertetett lépéseket.</span><span class="sxs-lookup"><span data-stu-id="eed98-106">In this example, you will create a format configuration for sample company, Litware, Inc. To complete these steps, you must first complete the steps in the "Map model to selected datasources" procedure.</span></span>


## <a name="create-a-new-format-configuration"></a><span data-ttu-id="eed98-107">Új formátumkonfiguráció létrehozása</span><span class="sxs-lookup"><span data-stu-id="eed98-107">Create a new format configuration</span></span>
1. <span data-ttu-id="eed98-108">Ugorjon a **Szervezeti adminisztráció > Munkaterületek > Elektronikus jelentés** pontra.</span><span class="sxs-lookup"><span data-stu-id="eed98-108">Go to **Organization administration > Workspaces > Electronic reporting**.</span></span>
2. <span data-ttu-id="eed98-109">Kattintson a **Jelentéskészítés konfigurációi** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="eed98-109">Click **Reporting configurations**.</span></span>
3. <span data-ttu-id="eed98-110">A fán válassza ki a következőt: **Payments (simplified model)**.</span><span class="sxs-lookup"><span data-stu-id="eed98-110">In the tree, select **Payments (simplified model)**.</span></span>
4. <span data-ttu-id="eed98-111">A **Konfiguráció létrehozása** gombra kattintva megnyithatja a legördülő párbeszédablakot.</span><span class="sxs-lookup"><span data-stu-id="eed98-111">Click **Create configuration** to open the drop dialog.</span></span>

 > [!NOTE]
 > <span data-ttu-id="eed98-112">Ha nem látja a **Konfiguráció létrehozása** lehetőséget, a tervező módot engedélyeznie kell a **elektronikus bevallási paraméterek** lapon.</span><span class="sxs-lookup"><span data-stu-id="eed98-112">If you don't see **Create configuration**, you must enable design mode on the **Electronic reporting parameters** page.</span></span> 
 
5. <span data-ttu-id="eed98-113">Az **Új** mezőbe írja be a **PaymentModel modellen alapuló formátum** kifejezést.</span><span class="sxs-lookup"><span data-stu-id="eed98-113">In the **New** field, enter **Format based on data model PaymentModel**.</span></span>
6. <span data-ttu-id="eed98-114">A **Név** mezőbe írja be a **BACS (UK fictitious)** szöveget.</span><span class="sxs-lookup"><span data-stu-id="eed98-114">In the **Name** field, type **BACS (UK fictitious)**.</span></span>
7. <span data-ttu-id="eed98-115">A **Leírás** mezőbe írja be a **BACS vendor payment format (UK fictitious)** szöveget.</span><span class="sxs-lookup"><span data-stu-id="eed98-115">In the **Description** field, type **BACS vendor payment format (UK fictitious)**.</span></span>
    * <span data-ttu-id="eed98-116">Az aktív konfigurációs szolgáltató automatikusan megjelenik itt.</span><span class="sxs-lookup"><span data-stu-id="eed98-116">The active configuration provider is automatically entered here.</span></span> <span data-ttu-id="eed98-117">Ez a szolgáltató tartja majd karban ezt a konfigurációt.</span><span class="sxs-lookup"><span data-stu-id="eed98-117">This provider will be able to maintain this configuration.</span></span> <span data-ttu-id="eed98-118">Más szolgáltatók is használhatják ezt a konfigurációt, de nem tudják majd karbantartani.</span><span class="sxs-lookup"><span data-stu-id="eed98-118">Other providers can use this configuration, but will not be able to maintain it.</span></span>  
    * <span data-ttu-id="eed98-119">Elektronikusdokumentum-formátum definiálható.</span><span class="sxs-lookup"><span data-stu-id="eed98-119">A particular format of electronic document can be defined.</span></span> <span data-ttu-id="eed98-120">Ezt a mezőt hagyja üresen, ha azt szeretné, hogy futásidőben választhassa ki a formátumot.</span><span class="sxs-lookup"><span data-stu-id="eed98-120">Leave this field blank if you want to select a format at run-time.</span></span>  
8. <span data-ttu-id="eed98-121">Az **Adatmodell mezőben** adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="eed98-121">In the **Data model definition** field, enter or select a value.</span></span>
9. <span data-ttu-id="eed98-122">Kattintson a **Konfiguráció létrehozása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="eed98-122">Click **Create configuration**.</span></span> <span data-ttu-id="eed98-123">Új konfiguráció létrehozása megtörtént.</span><span class="sxs-lookup"><span data-stu-id="eed98-123">A new configuration has been created.</span></span> <span data-ttu-id="eed98-124">Egy vázlat verzió használható a tervezési formátum tárolására az elektronikus dokumentumok kezeléséhez.</span><span class="sxs-lookup"><span data-stu-id="eed98-124">The draft version can be used to store the design format for managing electronic documents.</span></span>  

## <a name="design-the-format-of-an-electronic-document"></a><span data-ttu-id="eed98-125">Elektronikus dokumentumok formátumának tervezése</span><span class="sxs-lookup"><span data-stu-id="eed98-125">Design the format of an electronic document</span></span>
1. <span data-ttu-id="eed98-126">Kattintson a **Tervező** pontra.</span><span class="sxs-lookup"><span data-stu-id="eed98-126">Click **Designer**.</span></span>
2. <span data-ttu-id="eed98-127">Kattintson a **Gyökér hozzáadása** lehetőségre a legördülő párbeszédpanel megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="eed98-127">Click **Add root** to open the drop dialog.</span></span>
3. <span data-ttu-id="eed98-128">A fában válassza ki a **Common\File** csomópontot.</span><span class="sxs-lookup"><span data-stu-id="eed98-128">In the tree, select **Common\File**.</span></span>
4. <span data-ttu-id="eed98-129">A **Név** mezőbe írja be az **Xml** szót.</span><span class="sxs-lookup"><span data-stu-id="eed98-129">In the **Name** field, type **Xml**.</span></span>
5. <span data-ttu-id="eed98-130">A **Kódolás** mezőbe írja be az **UTF-8** szót.</span><span class="sxs-lookup"><span data-stu-id="eed98-130">In the **Encoding** field, type **UTF-8**.</span></span>
6. <span data-ttu-id="eed98-131">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="eed98-131">Click **OK**.</span></span>
7. <span data-ttu-id="eed98-132">Kattintson a **Hozzáadás** gombra.</span><span class="sxs-lookup"><span data-stu-id="eed98-132">Click **Add**.</span></span>
8. <span data-ttu-id="eed98-133">A fában válassza ki az **XML\Element** csomópontot.</span><span class="sxs-lookup"><span data-stu-id="eed98-133">In the tree, select **XML\Element**.</span></span>
9. <span data-ttu-id="eed98-134">A **Név** mezőbe írja be a **Message** szöveget.</span><span class="sxs-lookup"><span data-stu-id="eed98-134">In the **Name** field, type **Message**.</span></span>
10. <span data-ttu-id="eed98-135">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="eed98-135">Click **OK**.</span></span>
11. <span data-ttu-id="eed98-136">A fastruktúrában válassza ki ezt: **Xml\Üzenet**.</span><span class="sxs-lookup"><span data-stu-id="eed98-136">In the tree, select **Xml\Message**.</span></span>
12. <span data-ttu-id="eed98-137">Kattintson az **Elem hozzáadása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="eed98-137">Click **Add Element**.</span></span>
13. <span data-ttu-id="eed98-138">A **Név** mezőbe írja be a **ProcessingDate** szót.</span><span class="sxs-lookup"><span data-stu-id="eed98-138">In the **Name** field, type **ProcessingDate**.</span></span>
14. <span data-ttu-id="eed98-139">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="eed98-139">Click **OK**.</span></span>
15. <span data-ttu-id="eed98-140">Kattintson az **Elem hozzáadása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="eed98-140">Click **Add Element**.</span></span>
16. <span data-ttu-id="eed98-141">A Név mezőbe írja be a **MessageId** szöveget.</span><span class="sxs-lookup"><span data-stu-id="eed98-141">In the Name field, type **MessageId**.</span></span>
17. <span data-ttu-id="eed98-142">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="eed98-142">Click **OK**.</span></span>
18. <span data-ttu-id="eed98-143">Kattintson az **Elem hozzáadása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="eed98-143">Click **Add Element**.</span></span>
19. <span data-ttu-id="eed98-144">A **Név** mezőbe írja be a **Fizetések** szöveget.</span><span class="sxs-lookup"><span data-stu-id="eed98-144">In the **Name** field, type **Payments**.</span></span>
20. <span data-ttu-id="eed98-145">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="eed98-145">Click **OK**.</span></span>
21. <span data-ttu-id="eed98-146">A fastruktúrában válassza ki ezt: **Xml\Üzenet\Fizetések**.</span><span class="sxs-lookup"><span data-stu-id="eed98-146">In the tree, select **Xml\Message\Payments**.</span></span>
22. <span data-ttu-id="eed98-147">Kattintson az **Elem hozzáadása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="eed98-147">Click **Add Element**.</span></span>
23. <span data-ttu-id="eed98-148">A **Név mezőbe** írja be az **Item** szót.</span><span class="sxs-lookup"><span data-stu-id="eed98-148">In the **Name** field, type **Item**.</span></span>
24. <span data-ttu-id="eed98-149">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="eed98-149">Click **OK**.</span></span>
25. <span data-ttu-id="eed98-150">A fastruktúrában válassza ki ezt: **Xml\Message\Payments\Item**.</span><span class="sxs-lookup"><span data-stu-id="eed98-150">In the tree, select **Xml\Message\Payments\Item**.</span></span>
26. <span data-ttu-id="eed98-151">Kattintson a **Hozzáadás** gombra.</span><span class="sxs-lookup"><span data-stu-id="eed98-151">Click **Add**.</span></span>
27. <span data-ttu-id="eed98-152">A fastruktúrában válassza ki az **XML\Attribute** elemet.</span><span class="sxs-lookup"><span data-stu-id="eed98-152">In the tree, select **XML\Attribute**.</span></span>
28. <span data-ttu-id="eed98-153">A Név mezőbe írja be az **Id** szöveget.</span><span class="sxs-lookup"><span data-stu-id="eed98-153">In the Name field, type **Id**.</span></span>
29. <span data-ttu-id="eed98-154">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="eed98-154">Click **OK**.</span></span>
30. <span data-ttu-id="eed98-155">Kattintson a **Hozzáadás** gombra.</span><span class="sxs-lookup"><span data-stu-id="eed98-155">Click **Add**.</span></span>
31. <span data-ttu-id="eed98-156">A fában válassza ki az **XML\Element** csomópontot.</span><span class="sxs-lookup"><span data-stu-id="eed98-156">In the tree, select **XML\Element**.</span></span>
32. <span data-ttu-id="eed98-157">A Név mezőbe írja be a **Vendor** szöveget.</span><span class="sxs-lookup"><span data-stu-id="eed98-157">In the Name field, type **Vendor**.</span></span>
33. <span data-ttu-id="eed98-158">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="eed98-158">Click **OK**.</span></span>
34. <span data-ttu-id="eed98-159">A fastruktúrában válassza ki ezt: **Xml\Message\Payments\Item\Vendor**.</span><span class="sxs-lookup"><span data-stu-id="eed98-159">In the tree, select **Xml\Message\Payments\Item\Vendor**.</span></span>
35. <span data-ttu-id="eed98-160">Kattintson az **Elem hozzáadása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="eed98-160">Click **Add Element**.</span></span>
36. <span data-ttu-id="eed98-161">A Név mezőbe írja be a **Name** szöveget.</span><span class="sxs-lookup"><span data-stu-id="eed98-161">In the Name field, type **Name**.</span></span>
37. <span data-ttu-id="eed98-162">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="eed98-162">Click **OK**.</span></span>
38. <span data-ttu-id="eed98-163">Kattintson az **Elem hozzáadása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="eed98-163">Click **Add Element**.</span></span>
39. <span data-ttu-id="eed98-164">A **Név** mezőbe írja be a **Bank** szöveget.</span><span class="sxs-lookup"><span data-stu-id="eed98-164">In the **Name** field, type **Bank**.</span></span>
40. <span data-ttu-id="eed98-165">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="eed98-165">Click **OK**.</span></span>
41. <span data-ttu-id="eed98-166">A fastruktúrában válassza ki ezt: **Xml\Message\Payments\Item\Vendor\Bank**.</span><span class="sxs-lookup"><span data-stu-id="eed98-166">In the tree, select **Xml\Message\Payments\Item\Vendor\Bank**.</span></span>
42. <span data-ttu-id="eed98-167">Kattintson az **Elem hozzáadása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="eed98-167">Click **Add Element**.</span></span>
43. <span data-ttu-id="eed98-168">A **Név** mezőbe írja be a **RoutingNumber** szöveget.</span><span class="sxs-lookup"><span data-stu-id="eed98-168">In the **Name** field, type **RoutingNumber**.</span></span>
44. <span data-ttu-id="eed98-169">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="eed98-169">Click **OK**.</span></span>
45. <span data-ttu-id="eed98-170">Kattintson az **Elem hozzáadása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="eed98-170">Click **Add Element**.</span></span>
46. <span data-ttu-id="eed98-171">A **Név** mezőbe írja be az **AccountNumber** szöveget.</span><span class="sxs-lookup"><span data-stu-id="eed98-171">In the **Name** field, type **AccountNumber**.</span></span>
47. <span data-ttu-id="eed98-172">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="eed98-172">Click **OK**.</span></span>
48. <span data-ttu-id="eed98-173">A fastruktúrában válassza ki ezt: **Xml\Message\Payments\Item\Vendor**.</span><span class="sxs-lookup"><span data-stu-id="eed98-173">In the tree, select **Xml\Message\Payments\Item\Vendor**.</span></span>
49. <span data-ttu-id="eed98-174">Kattintson a **Másolás** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="eed98-174">Click **Copy**.</span></span>
50. <span data-ttu-id="eed98-175">A fastruktúrában válassza ki ezt: **Xml\Message\Payments\Item**.</span><span class="sxs-lookup"><span data-stu-id="eed98-175">In the tree, select **Xml\Message\Payments\Item**.</span></span>
51. <span data-ttu-id="eed98-176">Kattintson a **Beillesztés** parancsra.</span><span class="sxs-lookup"><span data-stu-id="eed98-176">Click **Paste**.</span></span>
52. <span data-ttu-id="eed98-177">A **Név** mezőbe írja be a **Payer** szöveget.</span><span class="sxs-lookup"><span data-stu-id="eed98-177">In the **Name** field, type **Payer**.</span></span>
53. <span data-ttu-id="eed98-178">A fastruktúrában válassza ki ezt: **Xml\Message\Payments\Item**.</span><span class="sxs-lookup"><span data-stu-id="eed98-178">In the tree, select **Xml\Message\Payments\Item**.</span></span>
54. <span data-ttu-id="eed98-179">Kattintson az **Elem hozzáadása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="eed98-179">Click **Add Element**.</span></span>
55. <span data-ttu-id="eed98-180">A **Név** mezőbe írja be a **Pénznem** szöveget.</span><span class="sxs-lookup"><span data-stu-id="eed98-180">In the **Name** field, type **Currency**.</span></span>
56. <span data-ttu-id="eed98-181">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="eed98-181">Click **OK**.</span></span>
57. <span data-ttu-id="eed98-182">Kattintson az **Elem hozzáadása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="eed98-182">Click **Add Element**.</span></span>
58. <span data-ttu-id="eed98-183">A **Név** mezőbe írja be a **Leírás** szöveget.</span><span class="sxs-lookup"><span data-stu-id="eed98-183">In the **Name** field, type **Description**.</span></span>
59. <span data-ttu-id="eed98-184">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="eed98-184">Click **OK**.</span></span>
60. <span data-ttu-id="eed98-185">Kattintson az **Elem hozzáadása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="eed98-185">Click **Add Element**.</span></span>
61. <span data-ttu-id="eed98-186">A Név mezőbe írja be a **TransDate** szöveget.</span><span class="sxs-lookup"><span data-stu-id="eed98-186">In the Name field, type **TransDate**.</span></span>
62. <span data-ttu-id="eed98-187">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="eed98-187">Click **OK**.</span></span>
63. <span data-ttu-id="eed98-188">Kattintson az **Elem hozzáadása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="eed98-188">Click **Add Element**.</span></span>
64. <span data-ttu-id="eed98-189">A Név mezőbe írja be az **Amount** szöveget.</span><span class="sxs-lookup"><span data-stu-id="eed98-189">In the Name field, type **Amount**.</span></span>
65. <span data-ttu-id="eed98-190">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="eed98-190">Click **OK**.</span></span>

## <a name="prepare-format-components-for-mapping-to-data-model-elements"></a><span data-ttu-id="eed98-191">Formátum-összetevők előkészítése adatmodell-elemek leképezéséhez</span><span class="sxs-lookup"><span data-stu-id="eed98-191">Prepare format components for mapping to data model elements</span></span>
1. <span data-ttu-id="eed98-192">A fastruktúrában válassza ki ezt: **Xml\Message\ProcessingDate**.</span><span class="sxs-lookup"><span data-stu-id="eed98-192">In the tree, select **Xml\Message\ProcessingDate**.</span></span>
2. <span data-ttu-id="eed98-193">A **Hozzáadás** gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="eed98-193">Click **Add** to open the drop dialog.</span></span>
3. <span data-ttu-id="eed98-194">A fastruktúrában válassza ki ezt: **Text\DateTime**.</span><span class="sxs-lookup"><span data-stu-id="eed98-194">In the tree, select **Text\DateTime**.</span></span>
4. <span data-ttu-id="eed98-195">A **Formátum** mezőbe írja be az **yyyy-MM-dd** szöveget.</span><span class="sxs-lookup"><span data-stu-id="eed98-195">In the **Format** field, type **yyyy-MM-dd**.</span></span>
5. <span data-ttu-id="eed98-196">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="eed98-196">Click **OK**.</span></span>
6. <span data-ttu-id="eed98-197">A fastruktúrában válassza ki ezt: **Xml\Message\Payments\Item\TransDate**.</span><span class="sxs-lookup"><span data-stu-id="eed98-197">In the tree, select **Xml\Message\Payments\Item\TransDate**.</span></span>
7. <span data-ttu-id="eed98-198">Kattintson a **Dátum/idő hozzáadása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="eed98-198">Click **Add DateTime**.</span></span>
8. <span data-ttu-id="eed98-199">A **Formátum** mezőbe írja be az **yyyy-MM-dd** szöveget.</span><span class="sxs-lookup"><span data-stu-id="eed98-199">In the **Format** field, type **yyyy-MM-dd**.</span></span>
9. <span data-ttu-id="eed98-200">A **DateTime** típus mezőben válassza ki a **Dátum** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="eed98-200">In the **DateTime** type field, select **Date**.</span></span>
10. <span data-ttu-id="eed98-201">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="eed98-201">Click **OK**.</span></span>
11. <span data-ttu-id="eed98-202">A fastruktúrában válassza ki ezt: **Xml\Message\MessageId**.</span><span class="sxs-lookup"><span data-stu-id="eed98-202">In the tree, select **Xml\Message\MessageId**.</span></span>
12. <span data-ttu-id="eed98-203">A **Hozzáadás** gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="eed98-203">Click **Add** to open the drop dialog.</span></span>
13. <span data-ttu-id="eed98-204">A fában válassza ki ezt: **Text\String**.</span><span class="sxs-lookup"><span data-stu-id="eed98-204">In the tree, select **Text\String**.</span></span>
14. <span data-ttu-id="eed98-205">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="eed98-205">Click **OK**.</span></span>
15. <span data-ttu-id="eed98-206">A fastruktúrában válassza ki ezt: **Xml\Message\Payments\Item\Vendor\Name**.</span><span class="sxs-lookup"><span data-stu-id="eed98-206">In the tree, select **Xml\Message\Payments\Item\Vendor\Name**.</span></span>
16. <span data-ttu-id="eed98-207">Kattintson a **Karakterlánc hozzáadása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="eed98-207">Click **Add String**.</span></span>
17. <span data-ttu-id="eed98-208">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="eed98-208">Click **OK**.</span></span>
18. <span data-ttu-id="eed98-209">A fastruktúrában válassza ki ezt: **Xml\Message\Payments\Item\Vendor\Bank\RoutingNumber**.</span><span class="sxs-lookup"><span data-stu-id="eed98-209">In the tree, select **Xml\Message\Payments\Item\Vendor\Bank\RoutingNumber**.</span></span>
19. <span data-ttu-id="eed98-210">Kattintson a **Karakterlánc hozzáadása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="eed98-210">Click **Add String**.</span></span>
20. <span data-ttu-id="eed98-211">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="eed98-211">Click **OK**.</span></span>
21. <span data-ttu-id="eed98-212">A fastruktúrában válassza ki ezt: **Xml\Message\Payments\Item\Vendor\Bank\AccountNumber**.</span><span class="sxs-lookup"><span data-stu-id="eed98-212">In the tree, select **Xml\Message\Payments\Item\Vendor\Bank\AccountNumber**.</span></span>
22. <span data-ttu-id="eed98-213">Kattintson a **Karakterlánc hozzáadása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="eed98-213">Click **Add String**.</span></span>
23. <span data-ttu-id="eed98-214">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="eed98-214">Click **OK**.</span></span>
24. <span data-ttu-id="eed98-215">A fastruktúrában válassza ki ezt: **Xml\Message\Payments\Item\Payer\Name**.</span><span class="sxs-lookup"><span data-stu-id="eed98-215">In the tree, select **Xml\Message\Payments\Item\Payer\Name**.</span></span>
25. <span data-ttu-id="eed98-216">Kattintson a **Karakterlánc hozzáadása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="eed98-216">Click **Add String**.</span></span>
26. <span data-ttu-id="eed98-217">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="eed98-217">Click **OK**.</span></span>
27. <span data-ttu-id="eed98-218">A fastruktúrában válassza ki ezt: **Xml\Message\Payments\Item\Payer\Bank\RoutingNumber**.</span><span class="sxs-lookup"><span data-stu-id="eed98-218">In the tree, select **Xml\Message\Payments\Item\Payer\Bank\RoutingNumber**.</span></span>
28. <span data-ttu-id="eed98-219">Kattintson a **Karakterlánc hozzáadása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="eed98-219">Click **Add String**.</span></span>
29. <span data-ttu-id="eed98-220">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="eed98-220">Click **OK**.</span></span>
30. <span data-ttu-id="eed98-221">A fastruktúrában válassza ki ezt: **Xml\Message\Payments\Item\Payer\Bank\AccountNumber**.</span><span class="sxs-lookup"><span data-stu-id="eed98-221">In the tree, select **Xml\Message\Payments\Item\Payer\Bank\AccountNumber**.</span></span>
31. <span data-ttu-id="eed98-222">Kattintson a **Karakterlánc hozzáadása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="eed98-222">Click **Add String**.</span></span>
32. <span data-ttu-id="eed98-223">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="eed98-223">Click **OK**.</span></span>
33. <span data-ttu-id="eed98-224">A fastruktúrában válassza ki ezt: **Xml\Message\Payments\Item\Currency**.</span><span class="sxs-lookup"><span data-stu-id="eed98-224">In the tree, select **Xml\Message\Payments\Item\Currency**.</span></span>
34. <span data-ttu-id="eed98-225">Kattintson a **Karakterlánc hozzáadása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="eed98-225">Click **Add String**.</span></span>
35. <span data-ttu-id="eed98-226">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="eed98-226">Click **OK**.</span></span>
36. <span data-ttu-id="eed98-227">A fastruktúrában válassza ki ezt: **Xml\Message\Payments\Item\Description**.</span><span class="sxs-lookup"><span data-stu-id="eed98-227">In the tree, select **Xml\Message\Payments\Item\Description**.</span></span>
37. <span data-ttu-id="eed98-228">Kattintson a **Karakterlánc hozzáadása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="eed98-228">Click **Add String**.</span></span>
38. <span data-ttu-id="eed98-229">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="eed98-229">Click **OK**.</span></span>
39. <span data-ttu-id="eed98-230">A fastruktúrában válassza ki ezt: **Xml\Message\Payments\Item\Amount**.</span><span class="sxs-lookup"><span data-stu-id="eed98-230">In the tree, select **Xml\Message\Payments\Item\Amount**.</span></span>
40. <span data-ttu-id="eed98-231">Kattintson a **Karakterlánc hozzáadása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="eed98-231">Click **Add String**.</span></span>
41. <span data-ttu-id="eed98-232">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="eed98-232">Click **OK**.</span></span>
42. <span data-ttu-id="eed98-233">Kattintson a **Mentés** gombra.</span><span class="sxs-lookup"><span data-stu-id="eed98-233">Click **Save**.</span></span>
43. <span data-ttu-id="eed98-234">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="eed98-234">Close the page.</span></span>



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]