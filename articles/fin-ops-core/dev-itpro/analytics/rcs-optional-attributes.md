---
title: Fájlok importálása XML-formátumban opcionális attribútumokkal
description: Ez a rész az olyan ER-formátumok kialakítását ismerteti, amelyek meghatározzák az XML-formátumú beérkező elektronikus dokumentumok elemzésére használt XML-attribútumokat.
author: NickSelin
manager: AnnBe
ms.date: 07/03/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EROperationDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 399f19197a729c11eaff94d708c837caef0d366d
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/09/2021
ms.locfileid: "5562952"
---
# <a name="import-files-in-xml-format-with-optional-attributes"></a><span data-ttu-id="9a8ba-103">Fájlok importálása XML-formátumban opcionális attribútumokkal</span><span class="sxs-lookup"><span data-stu-id="9a8ba-103">Import files in XML format with optional attributes</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9a8ba-104">Olyan elektronikus jelentési (ER) formátumokat tervezhet, amelyekkel elemezhetők az XML-formátumú bejövő elektronikus dokumentumok.</span><span class="sxs-lookup"><span data-stu-id="9a8ba-104">You can design Electronic reporting (ER) formats to parse incoming electronic documents in XML format.</span></span> <span data-ttu-id="9a8ba-105">Az XML-elemek bizonyos attribútumai választhatóként adhatók meg a tervezett ER-formátumban.</span><span class="sxs-lookup"><span data-stu-id="9a8ba-105">Certain attributes of XML elements can be specified in designed ER format as optional.</span></span> <span data-ttu-id="9a8ba-106">Ezzel a megoldással megfelelően kezelhetők az ilyen XML-attribútumokkal rendelkező és nem rendelkező bejövő fájlok.</span><span class="sxs-lookup"><span data-stu-id="9a8ba-106">It will allow you to handle incoming files with and without such XML attributes properly.</span></span> <span data-ttu-id="9a8ba-107">Az ezekből a fájljokból származó tartalmakat felhasználhatja az alkalmazásadatok frissítésére.</span><span class="sxs-lookup"><span data-stu-id="9a8ba-107">You can then use the content from these files to update application data.</span></span>

<span data-ttu-id="9a8ba-108">Ha további információt szeretne erről a szolgáltatásról, hajtsa végre az [(RCS) Fájlok importálása XML-formátumban opcionális attribútumokkal](tasks/import-files-xml-format-optional-attributes.md) című cikk lépéseit. Ez a cikk a 7.5.4.3 Informatikai szolgáltatások/megoldások összetevőinek beszerzése/kifejlesztése (10677) üzleti folyamat része.</span><span class="sxs-lookup"><span data-stu-id="9a8ba-108">To learn more about this feature, complete the steps in the topic, [(RCS) Import files in XML format with optional attributes](tasks/import-files-xml-format-optional-attributes.md), which is part of the 7.5.4.3 Acquire/Develop IT service/solution components (10677) business process.</span></span> <span data-ttu-id="9a8ba-109">Ez a feladat-útmutató és a kapcsolódó mintafájlok a [Microsoft letöltőközpontjából](https://go.microsoft.com/fwlink/?linkid=874684) tölthetők le.</span><span class="sxs-lookup"><span data-stu-id="9a8ba-109">You can download this task guide and associated sample files from the [Microsoft Download Center](https://go.microsoft.com/fwlink/?linkid=874684).</span></span>


| <span data-ttu-id="9a8ba-110">Tartalom leírása</span><span class="sxs-lookup"><span data-stu-id="9a8ba-110">Content description</span></span>       | <span data-ttu-id="9a8ba-111">Fájl</span><span class="sxs-lookup"><span data-stu-id="9a8ba-111">File</span></span>                                                         |
|---------------------------|--------------------------------------------------------------|
| <span data-ttu-id="9a8ba-112">Mintafájl XML-formátumban</span><span class="sxs-lookup"><span data-stu-id="9a8ba-112">Sample file in XML format</span></span> | <span data-ttu-id="9a8ba-113">IncomingDocumentToLearnHowToHandleOptionalAttributes.xml</span><span class="sxs-lookup"><span data-stu-id="9a8ba-113">IncomingDocumentToLearnHowToHandleOptionalAttributes.xml</span></span>     |
| <span data-ttu-id="9a8ba-114">Feladat-útmutatók</span><span class="sxs-lookup"><span data-stu-id="9a8ba-114">Task guide</span></span>                | <span data-ttu-id="9a8ba-115">RCS fájlok importálása XML-formátumban opcionális attribútumokkal.axtr</span><span class="sxs-lookup"><span data-stu-id="9a8ba-115">RCS Import files in XML format with optional attributes.axtr</span></span> |


<span data-ttu-id="9a8ba-116">A következő lépések bemutatják, hogy egy Rendszergazda vagy Elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználó hogyan alakíthat ki Elektronikus jelentés (ER) formátumkonfigurációt választható attribútumokat tartalmazó XML-formátumú fájlok importálásához.</span><span class="sxs-lookup"><span data-stu-id="9a8ba-116">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can design ER format configuration to import files in XML format containing optional attributes.</span></span> <span data-ttu-id="9a8ba-117">Az alábbi lépések végrehajtásához először hajtsa végre a [Konfigurációszolgáltatók létrehozása és megjelölése aktívként](tasks/er-configuration-provider-mark-it-active-2016-11.md) eljárás lépéseit.</span><span class="sxs-lookup"><span data-stu-id="9a8ba-117">To complete these steps, you must first complete the steps in the procedure, [Create configuration providers and mark them as active](tasks/er-configuration-provider-mark-it-active-2016-11.md).</span></span> <span data-ttu-id="9a8ba-118">A kezdés előtt töltse le a Microsoft letöltőközpontjából (https://go.microsoft.com/fwlink/?linkid=874684 ) és mentse helyileg az IncomingDocumentToLearnHowToHandleOptionalAttributes.xml fájlt.</span><span class="sxs-lookup"><span data-stu-id="9a8ba-118">Before you begin, download and save locally the IncomingDocumentToLearnHowToHandleOptionalAttributes.xml file from Microsoft Download Center (https://go.microsoft.com/fwlink/?linkid=874684 ).</span></span>

1. <span data-ttu-id="9a8ba-119">Lépjen a **Szervezeti adminisztráció** > **Munkaterületek** > **Elektronikus jelentés** részre.</span><span class="sxs-lookup"><span data-stu-id="9a8ba-119">Go to **Organization administration** > **Workspaces** > **Electronic reporting**.</span></span>
2. <span data-ttu-id="9a8ba-120">Ellenőrizze, hogy a Litware, Inc. mintavállalat esetében rendelkezésre áll és **aktívként** van megjelölve a konfigurációszolgáltató.</span><span class="sxs-lookup"><span data-stu-id="9a8ba-120">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as **Active**.</span></span> <span data-ttu-id="9a8ba-121">Ha nem látja a konfigurációszolgáltatót, végezze el a [Konfigurációszolgáltatók létrehozása és megjelölése aktívként](tasks/er-configuration-provider-mark-it-active-2016-11.md) témakör lépéseit.</span><span class="sxs-lookup"><span data-stu-id="9a8ba-121">If you don't see this configuration provider, complete the steps in the topic, [Create configuration providers and mark them as active](tasks/er-configuration-provider-mark-it-active-2016-11.md).</span></span>
3. <span data-ttu-id="9a8ba-122">Kattintson a **Jelentéskészítés konfigurációi** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="9a8ba-122">Click **Reporting configurations**.</span></span>

## <a name="create-a-new-data-model-configuration"></a><span data-ttu-id="9a8ba-123">Új adatmodell-konfiguráció létrehozása</span><span class="sxs-lookup"><span data-stu-id="9a8ba-123">Create a new data model configuration</span></span>
1. <span data-ttu-id="9a8ba-124">A **Konfiguráció létrehozása** gombra kattintva megnyithatja a legördülő párbeszédablakot.</span><span class="sxs-lookup"><span data-stu-id="9a8ba-124">Click **Create configuration** to open the drop dialog.</span></span>
2. <span data-ttu-id="9a8ba-125">A **Név** mezőbe írja be: „Modell xml-fájl importálásához”.</span><span class="sxs-lookup"><span data-stu-id="9a8ba-125">In the **Name** field, type 'Model to import xml file'.</span></span>
3. <span data-ttu-id="9a8ba-126">Kattintson a **Konfiguráció létrehozása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="9a8ba-126">Click **Create configuration**.</span></span>
4. <span data-ttu-id="9a8ba-127">Kattintson a **Tervező** pontra.</span><span class="sxs-lookup"><span data-stu-id="9a8ba-127">Click **Designer**.</span></span>
5. <span data-ttu-id="9a8ba-128">Az **Új** gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="9a8ba-128">Click **New** to open the drop dialog.</span></span>
6. <span data-ttu-id="9a8ba-129">A **Név** mezőbe írja be a következőt: „Gyökér”.</span><span class="sxs-lookup"><span data-stu-id="9a8ba-129">In the **Name** field, type 'Root'.</span></span>
7. <span data-ttu-id="9a8ba-130">Kattintson a **Hozzáadás** parancsra.</span><span class="sxs-lookup"><span data-stu-id="9a8ba-130">Click **Add**.</span></span>
8. <span data-ttu-id="9a8ba-131">Az **Új** gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="9a8ba-131">Click **New** to open the drop dialog.</span></span>
9. <span data-ttu-id="9a8ba-132">A **Név** mezőbe írja be a következőt: „Lista”.</span><span class="sxs-lookup"><span data-stu-id="9a8ba-132">In the **Name** field, type 'List'.</span></span>
10.    <span data-ttu-id="9a8ba-133">A **Cikktípus** mezőben válassza ki a **Rekordlista** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9a8ba-133">In the **Item type** field, select **Record list**.</span></span>
11.    <span data-ttu-id="9a8ba-134">Kattintson a **Hozzáadás** parancsra.</span><span class="sxs-lookup"><span data-stu-id="9a8ba-134">Click **Add**.</span></span>
12.    <span data-ttu-id="9a8ba-135">Az **Új** gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="9a8ba-135">Click **New** to open the drop dialog.</span></span>
13.    <span data-ttu-id="9a8ba-136">A **Név** mezőbe írja be a következőt: „Kód”.</span><span class="sxs-lookup"><span data-stu-id="9a8ba-136">In the **Name** field, type 'Code'.</span></span>
14.    <span data-ttu-id="9a8ba-137">A **Cikktípus** mezőben válassza ki a **Karakterlánc** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9a8ba-137">In the **Item type** field, select **String**.</span></span>
15.    <span data-ttu-id="9a8ba-138">Kattintson a **Hozzáadás** parancsra.</span><span class="sxs-lookup"><span data-stu-id="9a8ba-138">Click **Add**.</span></span>
16.    <span data-ttu-id="9a8ba-139">Kattintson a **Mentés** gombra.</span><span class="sxs-lookup"><span data-stu-id="9a8ba-139">Click **Save**.</span></span>
17.    <span data-ttu-id="9a8ba-140">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="9a8ba-140">Close the page.</span></span>
18.    <span data-ttu-id="9a8ba-141">Kattintson az **Állapot módosítása** elemre.</span><span class="sxs-lookup"><span data-stu-id="9a8ba-141">Click **Change status**.</span></span>
19.    <span data-ttu-id="9a8ba-142">Kattintson a **Befejezés** gombra.</span><span class="sxs-lookup"><span data-stu-id="9a8ba-142">Click **Complete**.</span></span>
20.    <span data-ttu-id="9a8ba-143">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="9a8ba-143">Click **OK**.</span></span>

## <a name="create-a-format-for-data-import"></a><span data-ttu-id="9a8ba-144">Adatimportálási formátum létrehozása</span><span class="sxs-lookup"><span data-stu-id="9a8ba-144">Create a format for data import</span></span>
1. <span data-ttu-id="9a8ba-145">A **Konfiguráció létrehozása** gombra kattintva megnyithatja a legördülő párbeszédablakot.</span><span class="sxs-lookup"><span data-stu-id="9a8ba-145">Click **Create configuration** to open the drop dialog.</span></span>
2. <span data-ttu-id="9a8ba-146">Az **Új** mezőbe írja be a „Formátum alapja a következő adatmodell: Modell xml-fájl importálásához” kifejezést.</span><span class="sxs-lookup"><span data-stu-id="9a8ba-146">In the **New** field, enter 'Format based on data model Model to import xml file'.</span></span>
3. <span data-ttu-id="9a8ba-147">A **Név** mezőbe írja be: „Formátum xml-fájl importálásához”.</span><span class="sxs-lookup"><span data-stu-id="9a8ba-147">In the **Nam** e field, type 'Format to import xml file'.</span></span> 
4. <span data-ttu-id="9a8ba-148">Az **Igen** értéket válassza ki a **Támogatja az adatimportálást** mezőben.</span><span class="sxs-lookup"><span data-stu-id="9a8ba-148">Select **Yes** in the **Supports data import** field.</span></span>
5. <span data-ttu-id="9a8ba-149">Kattintson a **Konfiguráció létrehozása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="9a8ba-149">Click **Create configuration**.</span></span>

## <a name="design-a-format-to-parse-incoming-file-in-xml-format"></a><span data-ttu-id="9a8ba-150">XML-formátumú bejövő fájl elemzésére szolgáló formátum kialakítása</span><span class="sxs-lookup"><span data-stu-id="9a8ba-150">Design a format to parse incoming file in xml format</span></span>
1. <span data-ttu-id="9a8ba-151">Kattintson a **Tervező** pontra.</span><span class="sxs-lookup"><span data-stu-id="9a8ba-151">Click **Designer**.</span></span>
2. <span data-ttu-id="9a8ba-152">Kattintson a **Gyökér hozzáadása** lehetőségre a legördülő párbeszédpanel megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="9a8ba-152">Click **Add root** to open the drop dialog.</span></span>
3. <span data-ttu-id="9a8ba-153">A fában válassza ki az **XML\Element** csomópontot.</span><span class="sxs-lookup"><span data-stu-id="9a8ba-153">In the tree, select **XML\Element**.</span></span>
4. <span data-ttu-id="9a8ba-154">A **Név** mezőbe írja be a következőt: „Gyökér”.</span><span class="sxs-lookup"><span data-stu-id="9a8ba-154">In the **Name** field, type 'root'.</span></span>
5. <span data-ttu-id="9a8ba-155">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="9a8ba-155">Click **OK**.</span></span>
6. <span data-ttu-id="9a8ba-156">A **Hozzáadás** gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="9a8ba-156">Click **Add** to open the drop dialog.</span></span>
7. <span data-ttu-id="9a8ba-157">A fában válassza ki az **XML\Element** csomópontot.</span><span class="sxs-lookup"><span data-stu-id="9a8ba-157">In the tree, select **XML\Element**.</span></span>
8. <span data-ttu-id="9a8ba-158">A **Név** mezőbe írja be a következőt: „Dokumentum”.</span><span class="sxs-lookup"><span data-stu-id="9a8ba-158">In the **Name** field, type 'document'.</span></span>
9. <span data-ttu-id="9a8ba-159">A **Multiplicitás** mezőben válassza ki az **Egy a többhöz** értéket.</span><span class="sxs-lookup"><span data-stu-id="9a8ba-159">In the **Multiplicity** field, select **One many**.</span></span>
10.    <span data-ttu-id="9a8ba-160">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="9a8ba-160">Click **OK**.</span></span>
11.    <span data-ttu-id="9a8ba-161">A fastruktúrában válassza ki a **root\document** csomópontot.</span><span class="sxs-lookup"><span data-stu-id="9a8ba-161">In the tree, select **root\document**.</span></span>
12.    <span data-ttu-id="9a8ba-162">A **Hozzáadás** gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="9a8ba-162">Click **Add** to open the drop dialog.</span></span>
13.    <span data-ttu-id="9a8ba-163">A fastruktúrában válassza ki az **XML\Attribute** elemet.</span><span class="sxs-lookup"><span data-stu-id="9a8ba-163">In the tree, select **XML\Attribute**.</span></span>
14.    <span data-ttu-id="9a8ba-164">A **Név** mezőbe írja be az „azonosító” kifejezést.</span><span class="sxs-lookup"><span data-stu-id="9a8ba-164">In the **Name** field, type 'id'.</span></span>
15.    <span data-ttu-id="9a8ba-165">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="9a8ba-165">Click **OK**.</span></span>
16.    <span data-ttu-id="9a8ba-166">Kattintson a **Mentés** gombra.</span><span class="sxs-lookup"><span data-stu-id="9a8ba-166">Click **Save**.</span></span>

## <a name="design-a-format-mapping-to-save-parsed-information-to-data-model"></a><span data-ttu-id="9a8ba-167">Az elemzett adatok adatmodellbe való mentéséhez használandó formátum-hozzárendelés kialakítása</span><span class="sxs-lookup"><span data-stu-id="9a8ba-167">Design a format mapping to save parsed information to data model</span></span>
1.    <span data-ttu-id="9a8ba-168">Kattintson a **Formátum hozzárendelése modellhez** elemre.</span><span class="sxs-lookup"><span data-stu-id="9a8ba-168">Click **Map format to model**.</span></span>
2.    <span data-ttu-id="9a8ba-169">Kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="9a8ba-169">Click **New**.</span></span>
3.    <span data-ttu-id="9a8ba-170">A **Definíció** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="9a8ba-170">In the **Definition** field, enter or select a value.</span></span>
4.    <span data-ttu-id="9a8ba-171">A **Név** mezőbe írja be a következőt: „Hozzárendelés”.</span><span class="sxs-lookup"><span data-stu-id="9a8ba-171">In the **Name** field, type 'Mapping'.</span></span>
5.    <span data-ttu-id="9a8ba-172">Kattintson a **Mentés** gombra.</span><span class="sxs-lookup"><span data-stu-id="9a8ba-172">Click **Save**.</span></span>
6.    <span data-ttu-id="9a8ba-173">Kattintson a **Tervező** pontra.</span><span class="sxs-lookup"><span data-stu-id="9a8ba-173">Click **Designer**.</span></span>
7.    <span data-ttu-id="9a8ba-174">A fastruktúrában bontsa ki a **format** csomópontot.</span><span class="sxs-lookup"><span data-stu-id="9a8ba-174">In the tree, expand **format**.</span></span>
8.    <span data-ttu-id="9a8ba-175">A fastruktúrában bontsa ki a **format\root: XML Element(root)** csomópontot.</span><span class="sxs-lookup"><span data-stu-id="9a8ba-175">In the tree, expand **format\root: XML Element(root)**.</span></span>
9.    <span data-ttu-id="9a8ba-176">A fastruktúrában válassza ki a \**format\root: XML Element(root)\document: XML Element 1..* elemet</span><span class="sxs-lookup"><span data-stu-id="9a8ba-176">In the tree, select \**format\root: XML Element(root)\document: XML Element 1..*</span></span> <span data-ttu-id="9a8ba-177">(dokumentum)\*\*.</span><span class="sxs-lookup"><span data-stu-id="9a8ba-177">(document)\*\*.</span></span>
10.    <span data-ttu-id="9a8ba-178">Kattintson a **Kötés** gombra.</span><span class="sxs-lookup"><span data-stu-id="9a8ba-178">Click **Bind**.</span></span>
11.    <span data-ttu-id="9a8ba-179">A fastruktúrában bontsa ki a \**format\root: XML Element(root)\document: XML Element 1..* elemet</span><span class="sxs-lookup"><span data-stu-id="9a8ba-179">In the tree, expand \**format\root: XML Element(root)\document: XML Element 1..*</span></span> <span data-ttu-id="9a8ba-180">(dokumentum)\*\*.</span><span class="sxs-lookup"><span data-stu-id="9a8ba-180">(document)\*\*.</span></span>
12.    <span data-ttu-id="9a8ba-181">A fastruktúrában válassza ki a \**format\root: XML Element(root)\document: XML Element 1..* elemet</span><span class="sxs-lookup"><span data-stu-id="9a8ba-181">In the tree, select \**format\root: XML Element(root)\document: XML Element 1..*</span></span> <span data-ttu-id="9a8ba-182">(document)\id\*\*.</span><span class="sxs-lookup"><span data-stu-id="9a8ba-182">(document)\id\*\*.</span></span>
13.    <span data-ttu-id="9a8ba-183">A fastruktúrában bontsa ki a **List = format.root.document** részt.</span><span class="sxs-lookup"><span data-stu-id="9a8ba-183">In the tree, expand **List = format.root.document**.</span></span>
14.    <span data-ttu-id="9a8ba-184">A fastruktúrában válassza ki a **List = format.root.document\Code** pontot.</span><span class="sxs-lookup"><span data-stu-id="9a8ba-184">In the tree, select **List = format.root.document\Code**.</span></span>
15.    <span data-ttu-id="9a8ba-185">Kattintson a **Kötés** gombra.</span><span class="sxs-lookup"><span data-stu-id="9a8ba-185">Click **Bind**.</span></span>
16.    <span data-ttu-id="9a8ba-186">Kattintson a **Mentés** gombra.</span><span class="sxs-lookup"><span data-stu-id="9a8ba-186">Click **Save**.</span></span>
17.    <span data-ttu-id="9a8ba-187">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="9a8ba-187">Close the page.</span></span>

## <a name="run-format-mapping"></a><span data-ttu-id="9a8ba-188">Formátum-hozzárendelés futtatása</span><span class="sxs-lookup"><span data-stu-id="9a8ba-188">Run format mapping</span></span>
1. <span data-ttu-id="9a8ba-189">Kattintson a **Futtatás** parancsra.</span><span class="sxs-lookup"><span data-stu-id="9a8ba-189">Click **Run**.</span></span>
2. <span data-ttu-id="9a8ba-190">Kattintson a **Tallózás** gombra, és válassza az **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml** fájlt.</span><span class="sxs-lookup"><span data-stu-id="9a8ba-190">Click **Browse** and select the file, **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml**.</span></span>
3. <span data-ttu-id="9a8ba-191">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="9a8ba-191">Click **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="9a8ba-192">A kiválasztott fájl importálása nem történt meg, mert a formátum terve azt feltételezi, hogy a „dokumentum” elemhez létezik az „azonosító” attribútum, az importált fájl viszont nem tartalmaz ilyen attribútumot.</span><span class="sxs-lookup"><span data-stu-id="9a8ba-192">The selected file has not been imported as the format design assumes the existence of 'id' attribute for the 'document' element, but the imported file contains no such attribute.</span></span>

## <a name="modify-format-structure-to-handle-xml-attribute-as-optional"></a><span data-ttu-id="9a8ba-193">A formátum szerkezetének módosítása az XML-attribútumot nem kötelezőként való kezeléséhez</span><span class="sxs-lookup"><span data-stu-id="9a8ba-193">Modify format structure to handle xml attribute as optional</span></span>
1. <span data-ttu-id="9a8ba-194">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="9a8ba-194">Close the page.</span></span>
2. <span data-ttu-id="9a8ba-195">A fastruktúrában bontsa ki a **root\document** csomópontot.</span><span class="sxs-lookup"><span data-stu-id="9a8ba-195">In the tree, expand **root\document**.</span></span>
3. <span data-ttu-id="9a8ba-196">A fastruktúrában válassza ki a **root\document\id** pontot.</span><span class="sxs-lookup"><span data-stu-id="9a8ba-196">In the tree, select **root\document\id**.</span></span>
4. <span data-ttu-id="9a8ba-197">A **Hiányzó attribútumhoz tartozó üres karakterlánc** mezőben válassza az **Igen** értéket.</span><span class="sxs-lookup"><span data-stu-id="9a8ba-197">In the **Empty string for missing attribute** field, select **Yes**.</span></span>
5. <span data-ttu-id="9a8ba-198">Kattintson a **Mentés** gombra.</span><span class="sxs-lookup"><span data-stu-id="9a8ba-198">Click **Save**.</span></span>

## <a name="run-format-mapping-to-test-changes"></a><span data-ttu-id="9a8ba-199">Formátum-hozzárendelés futtatása a módosítások teszteléséhez</span><span class="sxs-lookup"><span data-stu-id="9a8ba-199">Run format mapping to test changes</span></span>
1. <span data-ttu-id="9a8ba-200">Kattintson a **Formátum hozzárendelése modellhez** elemre.</span><span class="sxs-lookup"><span data-stu-id="9a8ba-200">Click **Map format to model**.</span></span>
2. <span data-ttu-id="9a8ba-201">Kattintson a **Futtatás** parancsra.</span><span class="sxs-lookup"><span data-stu-id="9a8ba-201">Click **Run**.</span></span>
3. <span data-ttu-id="9a8ba-202">Kattintson a **Tallózás** gombra, és válassza az **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml** fájlt.</span><span class="sxs-lookup"><span data-stu-id="9a8ba-202">Click **Browse** and select the file, **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml**.</span></span>
4. <span data-ttu-id="9a8ba-203">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="9a8ba-203">Click **OK**.</span></span>
5. <span data-ttu-id="9a8ba-204">Ellenőrizze a létrehozott fájlt.</span><span class="sxs-lookup"><span data-stu-id="9a8ba-204">Review the generated file.</span></span> <span data-ttu-id="9a8ba-205">Ügyeljen rá, hogy ugyanazt a fájlt importálta, mivel a formátumtervező most az „azonosító” attribútumot a „dokumentum” elemhez opcionálisnak veszi.</span><span class="sxs-lookup"><span data-stu-id="9a8ba-205">Note that same file has been imported as the format design now consider the 'id' attribute for the 'document' element as optional.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]