---
title: (RCS) Fájlok importálása XML-formátumban opcionális attribútumokkal
description: Ez a témakör azt mutatja be, hogy egy felhasználó hogyan tud ER-formátumkonfigurációt tervezni arra, hogy opcionális attribútumokat tartalmazó XML-formátumban importáljon fájlokat.
author: NickSelin
manager: AnnBe
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-07-28
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e1290598d8dbd5b72d679ccf3e642e75b6dc3215
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/27/2019
ms.locfileid: "2182186"
---
# <a name="rcs-import-files-in-xml-format-with-optional-attributes"></a><span data-ttu-id="1d4bc-103">(RCS) Fájlok importálása XML-formátumban opcionális attribútumokkal</span><span class="sxs-lookup"><span data-stu-id="1d4bc-103">(RCS) Import files in XML format with optional attributes</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="1d4bc-104">A következő lépések bemutatják, hogy egy Rendszergazda vagy Elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználó hogyan alakíthat ki Elektronikus jelentés (ER) formátumkonfigurációt választható attribútumokat tartalmazó XML-formátumú fájlok importálásához.</span><span class="sxs-lookup"><span data-stu-id="1d4bc-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can design ER format configuration to import files in XML format containing optional attributes.</span></span> <span data-ttu-id="1d4bc-105">Hajtsa végre az alábbi lépéseket: Először hajtsa végre a „Konfiguráció szolgáltatói létrehozása és aktívként történő megjelölése” eljárás lépéseit.</span><span class="sxs-lookup"><span data-stu-id="1d4bc-105">To complete these steps, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span> <span data-ttu-id="1d4bc-106">A kezdés előtt töltse le és mentse helyileg az IncomingDocumentToLearnHowToHandleOptionalAttributes.xml fájlt a [Microsoft letöltőközpontból](https://go.microsoft.com/fwlink/?linkid=874684).</span><span class="sxs-lookup"><span data-stu-id="1d4bc-106">Before you begin, download and save locally the IncomingDocumentToLearnHowToHandleOptionalAttributes.xml file from [Microsoft Download Center](https://go.microsoft.com/fwlink/?linkid=874684).</span></span>

1.  <span data-ttu-id="1d4bc-107">Ugorjon **Az összes munkaterület** > **Elektronikus jelentés** pontra.</span><span class="sxs-lookup"><span data-stu-id="1d4bc-107">Go to **All workspaces** > **Electronic reporting**.</span></span>
2.  <span data-ttu-id="1d4bc-108">Ellenőrizze, hogy a Litware, Inc. mintavállalat esetében rendelkezésre áll és **aktívként** van megjelölve a konfigurációszolgáltató.</span><span class="sxs-lookup"><span data-stu-id="1d4bc-108">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as **Active**.</span></span> <span data-ttu-id="1d4bc-109">Ha nem látja a konfigurációszolgáltatót, végezze el a [Konfigurációszolgáltató létrehozása, és megjelölés aktívként](er-configuration-provider-mark-it-active-2016-11.md) eljárásban szereplő lépéseket.</span><span class="sxs-lookup"><span data-stu-id="1d4bc-109">If you don’t see this configuration provider, complete the steps in the procedure [Create a configuration provider and mark it as active](er-configuration-provider-mark-it-active-2016-11.md).</span></span>
3.  <span data-ttu-id="1d4bc-110">Kattintson a **Jelentéskészítés konfigurációi** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="1d4bc-110">Click **Reporting configurations**.</span></span>

## <a name="create-a-new-data-model-configuration"></a><span data-ttu-id="1d4bc-111">Új adatmodell-konfiguráció létrehozása</span><span class="sxs-lookup"><span data-stu-id="1d4bc-111">Create a new data model configuration</span></span>
1.  <span data-ttu-id="1d4bc-112">A **Konfiguráció létrehozása** gombra kattintva megnyithatja a legördülő párbeszédablakot.</span><span class="sxs-lookup"><span data-stu-id="1d4bc-112">Click **Create configuration** to open the drop dialog.</span></span>
2.  <span data-ttu-id="1d4bc-113">A **Név** mezőbe írja be: „Modell xml-fájl importálásához”.</span><span class="sxs-lookup"><span data-stu-id="1d4bc-113">In the **Name** field, type 'Model to import xml file'.</span></span>
3.  <span data-ttu-id="1d4bc-114">Kattintson a **Konfiguráció létrehozása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="1d4bc-114">Click **Create configuration**.</span></span>
4.  <span data-ttu-id="1d4bc-115">Kattintson a **Tervező** pontra.</span><span class="sxs-lookup"><span data-stu-id="1d4bc-115">Click **Designer**.</span></span>
5.  <span data-ttu-id="1d4bc-116">Az **Új** gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="1d4bc-116">Click **New** to open the drop dialog.</span></span>
6.  <span data-ttu-id="1d4bc-117">A **Név** mezőbe írja be a következőt: „Gyökér”.</span><span class="sxs-lookup"><span data-stu-id="1d4bc-117">In the **Name** field, type 'Root'.</span></span>
7.  <span data-ttu-id="1d4bc-118">Kattintson a **Hozzáadás** parancsra.</span><span class="sxs-lookup"><span data-stu-id="1d4bc-118">Click **Add**.</span></span>
8.  <span data-ttu-id="1d4bc-119">Az **Új** gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="1d4bc-119">Click **New** to open the drop dialog.</span></span>
9.  <span data-ttu-id="1d4bc-120">A **Név** mezőbe írja be a következőt: „Lista”.</span><span class="sxs-lookup"><span data-stu-id="1d4bc-120">In the **Name** field, type 'List'.</span></span>
10. <span data-ttu-id="1d4bc-121">A **Cikktípus** mezőben válassza ki a **Rekordlista** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1d4bc-121">In the **Item type** field, select **Record list**.</span></span>
11. <span data-ttu-id="1d4bc-122">Kattintson a **Hozzáadás** parancsra.</span><span class="sxs-lookup"><span data-stu-id="1d4bc-122">Click **Add**.</span></span>
12. <span data-ttu-id="1d4bc-123">Az **Új** gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="1d4bc-123">Click **New** to open the drop dialog.</span></span>
13. <span data-ttu-id="1d4bc-124">A **Név** mezőbe írja be a következőt: „Kód”.</span><span class="sxs-lookup"><span data-stu-id="1d4bc-124">In the **Name** field, type 'Code'.</span></span>
14. <span data-ttu-id="1d4bc-125">A **Cikktípus** mezőben válassza ki a **Karakterlánc** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1d4bc-125">In the **Item type** field, select **String**.</span></span>
15. <span data-ttu-id="1d4bc-126">Kattintson a **Hozzáadás** parancsra.</span><span class="sxs-lookup"><span data-stu-id="1d4bc-126">Click **Add**.</span></span>
16. <span data-ttu-id="1d4bc-127">Kattintson a **Mentés** gombra.</span><span class="sxs-lookup"><span data-stu-id="1d4bc-127">Click **Save**.</span></span>
17. <span data-ttu-id="1d4bc-128">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="1d4bc-128">Close the page.</span></span>
18. <span data-ttu-id="1d4bc-129">Kattintson az **Állapot módosítása** elemre.</span><span class="sxs-lookup"><span data-stu-id="1d4bc-129">Click **Change status**.</span></span>
19. <span data-ttu-id="1d4bc-130">Kattintson a **Befejezés** gombra.</span><span class="sxs-lookup"><span data-stu-id="1d4bc-130">Click **Complete**.</span></span>
20. <span data-ttu-id="1d4bc-131">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="1d4bc-131">Click **OK**.</span></span>

## <a name="create-a-format-for-data-import"></a><span data-ttu-id="1d4bc-132">Adatimportálási formátum létrehozása</span><span class="sxs-lookup"><span data-stu-id="1d4bc-132">Create a format for data import</span></span>
1.  <span data-ttu-id="1d4bc-133">A **Konfiguráció létrehozása** gombra kattintva megnyithatja a legördülő párbeszédablakot.</span><span class="sxs-lookup"><span data-stu-id="1d4bc-133">Click **Create configuration** to open the drop dialog.</span></span>
2.  <span data-ttu-id="1d4bc-134">Az **Új** mezőbe írja be a „Formátum alapja a következő adatmodell: Modell xml-fájl importálásához” kifejezést.</span><span class="sxs-lookup"><span data-stu-id="1d4bc-134">In the **New** field, enter 'Format based on data model Model to import xml file'.</span></span>
3.  <span data-ttu-id="1d4bc-135">A **Név** mezőbe írja be: „Formátum xml-fájl importálásához”.</span><span class="sxs-lookup"><span data-stu-id="1d4bc-135">In the **Name** field, type 'Format to import xml file'.</span></span>
4.  <span data-ttu-id="1d4bc-136">Az **Igen** értéket válassza ki a **Támogatja az adatimportálást** mezőben.</span><span class="sxs-lookup"><span data-stu-id="1d4bc-136">Select **Yes** in the **Supports data import** field.</span></span>
5.  <span data-ttu-id="1d4bc-137">Kattintson a **Konfiguráció létrehozása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="1d4bc-137">Click **Create configuration**.</span></span>

## <a name="design-a-format-to-parse-incoming-file-in-xml-format"></a><span data-ttu-id="1d4bc-138">XML-formátumú bejövő fájl elemzésére szolgáló formátum kialakítása</span><span class="sxs-lookup"><span data-stu-id="1d4bc-138">Design a format to parse incoming file in xml format</span></span>
1.  <span data-ttu-id="1d4bc-139">Kattintson a **Tervező** pontra.</span><span class="sxs-lookup"><span data-stu-id="1d4bc-139">Click **Designer**.</span></span>
2.  <span data-ttu-id="1d4bc-140">Kattintson a **Gyökér hozzáadása** lehetőségre a legördülő párbeszédpanel megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="1d4bc-140">Click **Add root** to open the drop dialog.</span></span>
3.  <span data-ttu-id="1d4bc-141">A fában válassza ki az **XML\Element** csomópontot.</span><span class="sxs-lookup"><span data-stu-id="1d4bc-141">In the tree, select **XML\Element**.</span></span>
4.  <span data-ttu-id="1d4bc-142">A **Név** mezőbe írja be a következőt: „Gyökér”.</span><span class="sxs-lookup"><span data-stu-id="1d4bc-142">In the **Name** field, type 'root'.</span></span>
5.  <span data-ttu-id="1d4bc-143">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="1d4bc-143">Click **OK**.</span></span>
6.  <span data-ttu-id="1d4bc-144">A **Hozzáadás** gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="1d4bc-144">Click **Add** to open the drop dialog.</span></span>
7.  <span data-ttu-id="1d4bc-145">A fában válassza ki az **XML\Element** csomópontot.</span><span class="sxs-lookup"><span data-stu-id="1d4bc-145">In the tree, select **XML\Element**.</span></span>
8.  <span data-ttu-id="1d4bc-146">A **Név** mezőbe írja be a következőt: „Dokumentum”.</span><span class="sxs-lookup"><span data-stu-id="1d4bc-146">In the **Name** field, type 'document'.</span></span>
9.  <span data-ttu-id="1d4bc-147">A **Multiplicitás** mezőben válassza ki az **Egy a többhöz** értéket.</span><span class="sxs-lookup"><span data-stu-id="1d4bc-147">In the **Multiplicity** field, select **One many**.</span></span>
10. <span data-ttu-id="1d4bc-148">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="1d4bc-148">Click **OK**.</span></span>
11. <span data-ttu-id="1d4bc-149">A fastruktúrában válassza ki a **root\document** csomópontot.</span><span class="sxs-lookup"><span data-stu-id="1d4bc-149">In the tree, select **root\document**.</span></span>
12. <span data-ttu-id="1d4bc-150">A **Hozzáadás** gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="1d4bc-150">Click **Add** to open the drop dialog.</span></span>
13. <span data-ttu-id="1d4bc-151">A fastruktúrában válassza ki az **XML\Attribute** elemet.</span><span class="sxs-lookup"><span data-stu-id="1d4bc-151">In the tree, select **XML\Attribute**.</span></span>
14. <span data-ttu-id="1d4bc-152">A **Név** mezőbe írja be az ID szöveget.</span><span class="sxs-lookup"><span data-stu-id="1d4bc-152">In the **Name** field, type 'ID'.</span></span>
15. <span data-ttu-id="1d4bc-153">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="1d4bc-153">Click **OK**.</span></span>
16. <span data-ttu-id="1d4bc-154">Kattintson a **Mentés** gombra.</span><span class="sxs-lookup"><span data-stu-id="1d4bc-154">Click **Save**.</span></span>

## <a name="design-a-format-mapping-to-save-parsed-information-to-data-model"></a><span data-ttu-id="1d4bc-155">Az elemzett adatok adatmodellbe való mentéséhez használandó formátum-hozzárendelés kialakítása</span><span class="sxs-lookup"><span data-stu-id="1d4bc-155">Design a format mapping to save parsed information to data model</span></span>
1. <span data-ttu-id="1d4bc-156">Kattintson a **Formátum hozzárendelése modellhez** elemre.</span><span class="sxs-lookup"><span data-stu-id="1d4bc-156">Click **Map format to model**.</span></span>
2. <span data-ttu-id="1d4bc-157">Kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="1d4bc-157">Click **New**.</span></span>
3. <span data-ttu-id="1d4bc-158">A **Definíció** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="1d4bc-158">In the **Definition** field, enter or select a value.</span></span>
4. <span data-ttu-id="1d4bc-159">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="1d4bc-159">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="1d4bc-160">A **Név** mezőbe írja be a következőt: „Hozzárendelés”.</span><span class="sxs-lookup"><span data-stu-id="1d4bc-160">In the **Name** field, type 'Mapping'.</span></span>
6. <span data-ttu-id="1d4bc-161">Kattintson a **Mentés** gombra.</span><span class="sxs-lookup"><span data-stu-id="1d4bc-161">Click **Save**.</span></span>
7. <span data-ttu-id="1d4bc-162">Kattintson a **Tervező** pontra.</span><span class="sxs-lookup"><span data-stu-id="1d4bc-162">Click **Designer**.</span></span>
8. <span data-ttu-id="1d4bc-163">A fastruktúrában bontsa ki a **format** csomópontot.</span><span class="sxs-lookup"><span data-stu-id="1d4bc-163">In the tree, expand **format**.</span></span>
9. <span data-ttu-id="1d4bc-164">A fastruktúrában bontsa ki a **format\root: XML Element(root)** csomópontot.</span><span class="sxs-lookup"><span data-stu-id="1d4bc-164">In the tree, expand **format\root: XML Element(root)**.</span></span>
10. <span data-ttu-id="1d4bc-165">A fastruktúrában válassza ki a \**format\root: XML Element(root)\document: XML Element 1..* elemet</span><span class="sxs-lookup"><span data-stu-id="1d4bc-165">In the tree, select \**format\root: XML Element(root)\document: XML Element 1..*</span></span> <span data-ttu-id="1d4bc-166">(dokumentum)\*\*.</span><span class="sxs-lookup"><span data-stu-id="1d4bc-166">(document)\*\*.</span></span>
11. <span data-ttu-id="1d4bc-167">Kattintson a **Kötés** gombra.</span><span class="sxs-lookup"><span data-stu-id="1d4bc-167">Click **Bind**.</span></span>
12. <span data-ttu-id="1d4bc-168">A fastruktúrában bontsa ki a \**format\root: XML Element(root)\document: XML Element 1..* elemet</span><span class="sxs-lookup"><span data-stu-id="1d4bc-168">In the tree, expand \**format\root: XML Element(root)\document: XML Element 1..*</span></span> <span data-ttu-id="1d4bc-169">(dokumentum)\*\*.</span><span class="sxs-lookup"><span data-stu-id="1d4bc-169">(document)\*\*.</span></span>
13. <span data-ttu-id="1d4bc-170">A fastruktúrában válassza ki a \**format\root: XML Element(root)\document: XML Element 1..* elemet</span><span class="sxs-lookup"><span data-stu-id="1d4bc-170">In the tree, select \**format\root: XML Element(root)\document: XML Element 1..*</span></span> <span data-ttu-id="1d4bc-171">(document)\id\*\*.</span><span class="sxs-lookup"><span data-stu-id="1d4bc-171">(document)\id\*\*.</span></span>
14. <span data-ttu-id="1d4bc-172">A fastruktúrában bontsa ki a **List = format.root.document** részt.</span><span class="sxs-lookup"><span data-stu-id="1d4bc-172">In the tree, expand **List = format.root.document**.</span></span>
15. <span data-ttu-id="1d4bc-173">A fastruktúrában válassza ki a **List = format.root.document\Code** pontot.</span><span class="sxs-lookup"><span data-stu-id="1d4bc-173">In the tree, select **List = format.root.document\Code**.</span></span>
16. <span data-ttu-id="1d4bc-174">Kattintson a **Kötés** gombra.</span><span class="sxs-lookup"><span data-stu-id="1d4bc-174">Click **Bind**.</span></span>
17. <span data-ttu-id="1d4bc-175">Kattintson a **Mentés** gombra.</span><span class="sxs-lookup"><span data-stu-id="1d4bc-175">Click **Save**.</span></span>
18. <span data-ttu-id="1d4bc-176">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="1d4bc-176">Close the page.</span></span>
 
## <a name="run-format-mapping"></a><span data-ttu-id="1d4bc-177">Formátum-hozzárendelés futtatása</span><span class="sxs-lookup"><span data-stu-id="1d4bc-177">Run format mapping</span></span>
1. <span data-ttu-id="1d4bc-178">Kattintson a **Futtatás** parancsra.</span><span class="sxs-lookup"><span data-stu-id="1d4bc-178">Click **Run**.</span></span>
2. <span data-ttu-id="1d4bc-179">Kattintson a **Tallózás** gombra, és válassza az **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml** elemet.</span><span class="sxs-lookup"><span data-stu-id="1d4bc-179">Click **Browse** and select **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml**.</span></span>
3. <span data-ttu-id="1d4bc-180">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="1d4bc-180">Click **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="1d4bc-181">A kiválasztott fájl importálása nem történt meg, mert a formátum terve azt feltételezi, hogy a „dokumentum” elemhez létezik az „azonosító” attribútum, az importált fájl viszont nem tartalmaz ilyen attribútumot.</span><span class="sxs-lookup"><span data-stu-id="1d4bc-181">The selected file has not been imported as the format design assumes the existence of ‘id’ attribute for the ‘document’ element, but the imported file contains no such attribute.</span></span>

## <a name="modify-format-structure-to-handle-xml-attribute-as-optional"></a><span data-ttu-id="1d4bc-182">A formátum szerkezetének módosítása az XML-attribútumot nem kötelezőként való kezeléséhez</span><span class="sxs-lookup"><span data-stu-id="1d4bc-182">Modify format structure to handle xml attribute as optional</span></span>
1. <span data-ttu-id="1d4bc-183">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="1d4bc-183">Close the page.</span></span>
2. <span data-ttu-id="1d4bc-184">A fastruktúrában bontsa ki a **root\document** csomópontot.</span><span class="sxs-lookup"><span data-stu-id="1d4bc-184">In the tree, expand **root\document**.</span></span>
3. <span data-ttu-id="1d4bc-185">A fastruktúrában válassza ki a **root\document\id** pontot.</span><span class="sxs-lookup"><span data-stu-id="1d4bc-185">In the tree, select **root\document\id**.</span></span>
4. <span data-ttu-id="1d4bc-186">A **Hiányzó attribútumhoz tartozó üres karakterlánc** mezőben válassza az **Igen** értéket.</span><span class="sxs-lookup"><span data-stu-id="1d4bc-186">Select **Yes** in the **Empty string for missing attribute** field.</span></span>
5. <span data-ttu-id="1d4bc-187">Kattintson a **Mentés** gombra.</span><span class="sxs-lookup"><span data-stu-id="1d4bc-187">Click **Save**.</span></span>
 
## <a name="run-format-mapping-to-test-changes"></a><span data-ttu-id="1d4bc-188">Formátum-hozzárendelés futtatása a módosítások teszteléséhez</span><span class="sxs-lookup"><span data-stu-id="1d4bc-188">Run format mapping to test changes</span></span>
1. <span data-ttu-id="1d4bc-189">Kattintson a **Formátum hozzárendelése modellhez** elemre.</span><span class="sxs-lookup"><span data-stu-id="1d4bc-189">Click **Map format to model**.</span></span>
2. <span data-ttu-id="1d4bc-190">Kattintson a **Futtatás** parancsra.</span><span class="sxs-lookup"><span data-stu-id="1d4bc-190">Click **Run**.</span></span>
3. <span data-ttu-id="1d4bc-191">Kattintson a **Tallózás** gombra, és válassza az **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml** fájlt.</span><span class="sxs-lookup"><span data-stu-id="1d4bc-191">Click **Browse** and select the **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml** file.</span></span>
4. <span data-ttu-id="1d4bc-192">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="1d4bc-192">Click **OK**.</span></span>
5. <span data-ttu-id="1d4bc-193">Ellenőrizze a létrehozott fájlt.</span><span class="sxs-lookup"><span data-stu-id="1d4bc-193">Review the generated file.</span></span> 

> [!NOTE]
> <span data-ttu-id="1d4bc-194">Ugyanazt a fájlt importálta, mivel a formátumtervező most az „azonosító” attribútumot a „dokumentum” elemhez opcionálisnak veszi.</span><span class="sxs-lookup"><span data-stu-id="1d4bc-194">The same file has been imported as the format design now consider the ‘id’ attribute for the ‘document’ element as optional.</span></span>
