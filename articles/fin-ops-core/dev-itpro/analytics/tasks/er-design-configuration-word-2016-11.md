---
title: ER-konfigurációk újrafelhasználása Excel-sablonokkal Word-formátumú jelentések generálásához
description: Ez a témakör azt mutatja be, hogyan lehet jelentések Excel-munkafüzetként való előállítására használható jelentésformátumokat beállítani úgy, hogy a jelentéseket Word-dokumentumként hozza létre.
author: NickSelin
manager: AnnBe
ms.date: 01/11/2021
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, EROperationDesigner, LedgerJournalTable, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 769913fd0344eb276b3b1bd055255272ca5dfffd
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/30/2021
ms.locfileid: "5092716"
---
# <a name="reuse-er-configurations-with-excel-templates-to-generate-reports-in-word-format"></a><span data-ttu-id="b8673-103">ER-konfigurációk újrafelhasználása Excel-sablonokkal Word-formátumú jelentések generálásához</span><span class="sxs-lookup"><span data-stu-id="b8673-103">Reuse ER configurations with Excel templates to generate reports in Word format</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b8673-104">A jelentések Microsoft Word dokumentumokként történő létrehozásához [konfigurálhat](../er-design-configuration-word.md) egy új [elektronikus jelentéskészítési (ER)](../general-electronic-reporting.md) [formátumot](../general-electronic-reporting.md#FormatComponentOutbound).</span><span class="sxs-lookup"><span data-stu-id="b8673-104">To generate reports as Microsoft Word documents, you can [configure](../er-design-configuration-word.md) a new [Electronic reporting (ER)](../general-electronic-reporting.md) [format](../general-electronic-reporting.md#FormatComponentOutbound).</span></span> <span data-ttu-id="b8673-105">Arra is lehetőség van, hogy egy eredetileg Excel-munkafüzetként generált jelentéseket készítő ER-formátumot újrafelhasználjon.</span><span class="sxs-lookup"><span data-stu-id="b8673-105">Alternatively, you can reuse an ER format that was originally designed to generate reports as Excel workbooks.</span></span> <span data-ttu-id="b8673-106">Ebben az esetben az Excel-sablont Word-sablonra kell cserélnie.</span><span class="sxs-lookup"><span data-stu-id="b8673-106">In this case, you must replace the Excel template with a Word template.</span></span>

<span data-ttu-id="b8673-107">A következő eljárások bemutatják, hogyan konfigurálhat egy ER-formátumot a Rendszergazda szerepkör vagy az Elektronikus jelentések fejlesztője szerepkör egy felhasználója úgy, hogy a jelentések Word-fájlként való generálása során egy jelentések Excel-fájlként való generálására tervezett ER-formátumot használ fel újra.</span><span class="sxs-lookup"><span data-stu-id="b8673-107">The following procedures show how a user in either the System administrator role or the Electronic reporting developer role can configure an ER format to generate reports as Word files by reusing an ER format that was designed to generate reports as Excel files.</span></span>

<span data-ttu-id="b8673-108">Ezen eljárásokat a GBSI vállalatban hajthatja végre.</span><span class="sxs-lookup"><span data-stu-id="b8673-108">These procedures can be completed in the GBSI company.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b8673-109">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="b8673-109">Prerequisites</span></span>

<span data-ttu-id="b8673-110">Az eljárás végrehajtásához kövesse a lépéseket a [Konfiguráció tervezése az OPENXML formátumban létrejövő jelentésekre létrehozásához](er-design-reports-openxml-2016-11.md) feladat-útmutatót.</span><span class="sxs-lookup"><span data-stu-id="b8673-110">To complete these procedures, you must first follow the steps in the [Design a configuration for generating reports in OPENXML format](er-design-reports-openxml-2016-11.md) task guide.</span></span>

<span data-ttu-id="b8673-111">Le kell tölteni és helyileg menteni a következő sablonokat is a mintajelentéshez:</span><span class="sxs-lookup"><span data-stu-id="b8673-111">You must also download and locally save the following templates for the sample report:</span></span>

- [<span data-ttu-id="b8673-112">Kifizetési jelentés mintája (SampleVendPaymDocReport.docx)</span><span class="sxs-lookup"><span data-stu-id="b8673-112">Template of Payment Report (SampleVendPaymDocReport.docx)</span></span>](https://go.microsoft.com/fwlink/?linkid=862266)
- [<span data-ttu-id="b8673-113">Kifizetési jelentés bekötött sablonja (SampleVendPaymDocReportBounded.docx)</span><span class="sxs-lookup"><span data-stu-id="b8673-113">Bounded Template of Payment Report (SampleVendPaymDocReportBounded.docx)</span></span>](https://go.microsoft.com/fwlink/?linkid=862266)

<span data-ttu-id="b8673-114">Ezek az eljárások a Dynamics 365 for Operations 1611-es verzióban (2016. november) hozzáadott funkciókra vonatkozóak.</span><span class="sxs-lookup"><span data-stu-id="b8673-114">These procedures are for a feature that was added in Dynamics 365 for Operations version 1611 (November 2016).</span></span>

## <a name="select-the-existing-er-report-configuration"></a><span data-ttu-id="b8673-115">Válassza ki a meglévő ER-jelentéskonfigurációt</span><span class="sxs-lookup"><span data-stu-id="b8673-115">Select the existing ER report configuration</span></span>

1. <span data-ttu-id="b8673-116">A Dynamics 365 Finance alkalmazásban lépjen a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.</span><span class="sxs-lookup"><span data-stu-id="b8673-116">In Dynamics 365 Finance, go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="b8673-117">Győződjön meg arról, hogy a **Litware, Inc.** konfigurációszolgáltató **Aktív** állapottal van megjelölve.</span><span class="sxs-lookup"><span data-stu-id="b8673-117">Make sure that the **Litware, Inc.** configuration provider is selected as **Active**.</span></span> <span data-ttu-id="b8673-118">Ha nem, kövesse a [Konfigurációszolgáltatók létrehozása és megjelölése aktívként](er-configuration-provider-mark-it-active-2016-11.md) feladat-útmutatót.</span><span class="sxs-lookup"><span data-stu-id="b8673-118">If it isn't, follow the steps in the [Create configuration providers and mark them as active](er-configuration-provider-mark-it-active-2016-11.md) task guide.</span></span>
3. <span data-ttu-id="b8673-119">Válassza a **Jelentéskészítési konfigurációk** elemet.</span><span class="sxs-lookup"><span data-stu-id="b8673-119">Select **Reporting configurations**.</span></span> <span data-ttu-id="b8673-120">Újrahasznosítja a meglévő ER-konfigurációt, amelyet a jelentés OPENXML-formátumban történő előállítására terveztek.</span><span class="sxs-lookup"><span data-stu-id="b8673-120">You will reuse the existing ER configuration that was designed to generate the report output in OPENXML format.</span></span>
4. <span data-ttu-id="b8673-121">A **Konfigurációk** oldalon, a bal oldali panelen található konfigurációk fájában bontsa ki a **Fizetési modell** elemet, majd válassza a **Minta munkalap jelentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b8673-121">On the **Configurations** page, in the configuration tree in the left pane, expand **Payment model**, and select **Sample worksheet report**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b8673-122">A **Verziók** gyorslapon szerkesztheti a kijelölt ER-formátum piszkozatverzióját.</span><span class="sxs-lookup"><span data-stu-id="b8673-122">The draft version of the selected ER format can be edited on the **Versions** FastTab.</span></span>

5. <span data-ttu-id="b8673-123">Válassza a **Tervező** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b8673-123">Select **Designer**.</span></span>
6. <span data-ttu-id="b8673-124">A **Formátumtervező** lapon figyelje meg, hogy a gyökérformátum-elem címe jelzi, hogy jelenleg egy Excel-sablon van használatban.</span><span class="sxs-lookup"><span data-stu-id="b8673-124">On the **Format designer** page, notice that the title of the root format element indicates that an Excel template is currently used.</span></span>

![A meglévő konfiguráció kiválasztása](../media/er-design-configuration-word-2016-11-image01.gif)

## <a name="review-the-downloaded-word-template"></a><span data-ttu-id="b8673-126">A letöltött Word-sablon áttekintése</span><span class="sxs-lookup"><span data-stu-id="b8673-126">Review the downloaded Word template</span></span>

1. <span data-ttu-id="b8673-127">Az asztali Word-alkalmazásban nyissa meg a korábban letöltött **SampleVendPaymDocReport.docx** sablonfájlt.</span><span class="sxs-lookup"><span data-stu-id="b8673-127">In the Word desktop application, open the **SampleVendPaymDocReport.docx** template file that you downloaded earlier.</span></span>
2. <span data-ttu-id="b8673-128">Ellenőrizze, hogy a sablon csak az ER-kimenetként létrehozandó dokumentum elrendezését tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="b8673-128">Verify that the template contains only the layout of the document that you want to generate as ER output.</span></span>

![A Word-sablon elrendezése az asztali alkalmazásban](../media/er-design-configuration-word-2016-11-image02.png)

## <a name="replace-the-excel-template-with-the-word-template-and-add-a-custom-xml-part"></a><span data-ttu-id="b8673-130">Az Excel-sablon cseréje Word-sablonra és egyéni XML-rész hozzáadása</span><span class="sxs-lookup"><span data-stu-id="b8673-130">Replace the Excel template with the Word template and add a custom XML part</span></span>

<span data-ttu-id="b8673-131">Jelenleg az Excel-dokumentum használatos sablonként a kimenet OPENXML-formátumú előállításához.</span><span class="sxs-lookup"><span data-stu-id="b8673-131">Currently, the Excel document is used as a template to generate the output in OPENXML format.</span></span> <span data-ttu-id="b8673-132">Ezt a sablont cserélje le a korábban letöltött SampleVendPaymDocReport.docx Word-sablonfájlra.</span><span class="sxs-lookup"><span data-stu-id="b8673-132">You will replace this template with the SampleVendPaymDocReport.docx Word template file that you downloaded earlier.</span></span> <span data-ttu-id="b8673-133">Terjessze ki a Word-sablont egy egyéni XML-rész hozzáadásával is.</span><span class="sxs-lookup"><span data-stu-id="b8673-133">You will also extend the Word template by adding a custom XML part.</span></span>

1. <span data-ttu-id="b8673-134">A Finance **Formátumtervező** oldalának **Formátum** lapján válassza ki a **Mellékletek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b8673-134">In Finance, on the **Format designer** page, on the **Format** tab, select **Attachments**.</span></span>
2. <span data-ttu-id="b8673-135">A meglévő Excel-sablon eltávolításához válassza a **Törlés** lehetőséget a **Mellékletek** lapon.</span><span class="sxs-lookup"><span data-stu-id="b8673-135">On the **Attachments** page, select **Delete** to remove the existing Excel template.</span></span> <span data-ttu-id="b8673-136">A módosítás jóváhagyásához válassza az **Igen** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b8673-136">Select **Yes** to confirm the change.</span></span>
3. <span data-ttu-id="b8673-137">Válassza az **Új** \> **Fájl** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b8673-137">Select **New** \> **File**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b8673-138">Az ER-formátumok sablonjainak tárolásához ki kell választania egy ER-paraméterekben [konfigurált](../electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents) dokumentumtípust.</span><span class="sxs-lookup"><span data-stu-id="b8673-138">You must select a document type that has been [configured](../electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents) in the ER parameters to store templates of ER formats.</span></span>

4. <span data-ttu-id="b8673-139">Válassza a **Tallózás** lehetőséget, majd tallózással keresse meg és válassza ki a korábban letöltött **SampleVendPaymDocReport.docx** fájlt.</span><span class="sxs-lookup"><span data-stu-id="b8673-139">Select **Browse**, and then browse to and select the **SampleVendPaymDocReport.docx** file that you downloaded earlier.</span></span>
5. <span data-ttu-id="b8673-140">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b8673-140">Select **OK**.</span></span>
6. <span data-ttu-id="b8673-141">Zárja be a **Mellékletek** lapot.</span><span class="sxs-lookup"><span data-stu-id="b8673-141">Close the **Attachments** page.</span></span>
7. <span data-ttu-id="b8673-142">A **Formátumtervező** oldal **Sablon** mezőjében adja meg vagy válassza ki azt a **SampleVendPaymDocReport.docx** fájlt, amelyet Word-sablonként használni kíván a korábban használt Excel-sablon helyett.</span><span class="sxs-lookup"><span data-stu-id="b8673-142">On the **Format designer** page, in the **Template** field, enter or select the **SampleVendPaymDocReport.docx** file to use that Word template instead of the Excel template that was previously used.</span></span>
8. <span data-ttu-id="b8673-143">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b8673-143">Select **Save**.</span></span>

    <span data-ttu-id="b8673-144">A konfigurációs módosítások tárolása mellett a **Mentés** művelet a csatolt Word-sablont is frissíti.</span><span class="sxs-lookup"><span data-stu-id="b8673-144">In addition to storing configuration changes, the **Save** action updates the attached Word template.</span></span> <span data-ttu-id="b8673-145">A tervezett formátum hierarchikus szerkezete **Jelentés** néven, új egyéni XML-részként kerül hozzáadásra a csatolt Word-dokumentumhoz.</span><span class="sxs-lookup"><span data-stu-id="b8673-145">The hierarchical structure of the designed format is added to the attached Word document as a new custom XML part that is named **Report**.</span></span> <span data-ttu-id="b8673-146">A csatolt Word-sablon nem csak az ER-kimentként létrehozandó dokumentum elrendezését tartalmazza, hanem azt az adatszerkezetet is, amelyet az ER futásidőben ad meg a sablonban.</span><span class="sxs-lookup"><span data-stu-id="b8673-146">The attached Word template contains the layout of the document that will be generated as ER output and the structure of data that ER will enter in that template at runtime.</span></span>

9. <span data-ttu-id="b8673-147">Figyelje meg, hogy a gyökérformátum-elem címe jelzi, hogy jelenleg egy Word-sablon van használatban.</span><span class="sxs-lookup"><span data-stu-id="b8673-147">Notice that the title of the root format element indicates that a Word template is currently used.</span></span>

    ![Az Excel-sablon cseréje Word-sablonra és egyéni XML-rész hozzáadása](../media/er-design-configuration-word-2016-11-image03.gif)

10. <span data-ttu-id="b8673-149">Válassza a **Formátum** lap **Mellékletek** elemét.</span><span class="sxs-lookup"><span data-stu-id="b8673-149">On the **Format** tab, select **Attachments**.</span></span>

<span data-ttu-id="b8673-150">Most már leképezheti a **Jelentés** egyéni XML-rész elemeinek leképezését a Word-dokumentum tartalomvezérlőire.</span><span class="sxs-lookup"><span data-stu-id="b8673-150">You can now map the elements of the **Report** custom XML part to the content controls of the Word document.</span></span>

<span data-ttu-id="b8673-151">Ha megfelelő ismeretekkel rendelkezik a Word-dokumentumok tervezéséről [egyéni XML-részek](https://docs.microsoft.com/visualstudio/vsto/custom-xml-parts-overview?view=vs-2019) elemeire leképezett [tartalomvezérlőket](https://docs.microsoft.com/office/client-developer/word/content-controls-in-word) tartalmazó űrlapokként, akkor hajtsa végre a következő eljárás minden lépését a dokumentum létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="b8673-151">If you're familiar with the process of designing Word documents as forms that contain [content controls](https://docs.microsoft.com/office/client-developer/word/content-controls-in-word) that are mapped to elements of [custom XML parts](https://docs.microsoft.com/visualstudio/vsto/custom-xml-parts-overview?view=vs-2019), complete all steps in the next procedure to create the document.</span></span> <span data-ttu-id="b8673-152">A további információk: [A felhasználó által Wordben kitölthető vagy kinyomtatható űrlapok létrehozása](https://support.office.com/article/Create-forms-that-users-complete-or-print-in-Word-040c5cc1-e309-445b-94ac-542f732c8c8b).</span><span class="sxs-lookup"><span data-stu-id="b8673-152">For more information, see [Create forms that users complete or print in Words](https://support.office.com/article/Create-forms-that-users-complete-or-print-in-Word-040c5cc1-e309-445b-94ac-542f732c8c8b).</span></span> <span data-ttu-id="b8673-153">Ellenkező esetben hagyja ki a következő eljárást.</span><span class="sxs-lookup"><span data-stu-id="b8673-153">Otherwise, skip the next procedure.</span></span>

## <a name="get-a-word-document-that-has-a-custom-xml-part-and-do-data-mapping"></a><a id='get-word-doc'></a><span data-ttu-id="b8673-154">Egyéni XML-résszel rendelkező Word-dokumentum beszerzése adatleképezés végrehajtásához</span><span class="sxs-lookup"><span data-stu-id="b8673-154">Get a Word document that has a custom XML part and do data mapping</span></span>

1. <span data-ttu-id="b8673-155">A Finance alkalmazás **Mellékletek** oldalán válassza a **Megnyitás** lehetőséget a kiválasztott sablon Finance alkalmazásból való letöltéséhez és helyi tárolásához Word-dokumentumként.</span><span class="sxs-lookup"><span data-stu-id="b8673-155">In Finance, on the **Attachments** page, select **Open** to download the selected template from Finance and store it locally as a Word document.</span></span>
3. <span data-ttu-id="b8673-156">Az asztali Word alkalmazásban nyissa meg az éppen letöltött dokumentumot.</span><span class="sxs-lookup"><span data-stu-id="b8673-156">In the Word desktop application, open the document that you just downloaded.</span></span>
4. <span data-ttu-id="b8673-157">Válassza a **Fejlesztő** lap **XML-megfeleltetés munkaablak** elemét.</span><span class="sxs-lookup"><span data-stu-id="b8673-157">On the **Developer** tab, select **XML Mapping Pane**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b8673-158">Ha a **Fejlesztő** lap nem jelenik meg a menüsávon, a hozzáadáshoz szabja testre a menüsávot.</span><span class="sxs-lookup"><span data-stu-id="b8673-158">If the **Developer** tab doesn't appear on the ribbon, customize the ribbon to add it.</span></span>

5. <span data-ttu-id="b8673-159">Az **XML-leképezés** panel **Egyéni XML-rész** mezőjében válassza ki a **Jelentés** egyéni XML-részt.</span><span class="sxs-lookup"><span data-stu-id="b8673-159">In the **XML Mapping** pane, in the **Custom XML Part** field, select the **Report** custom XML part.</span></span>
6. <span data-ttu-id="b8673-160">Képezze le a kiválasztott **Jelentés** egyéni XML-rész elemeit és a Word-dokumentum tartalomvezérlőt.</span><span class="sxs-lookup"><span data-stu-id="b8673-160">Map the elements of the selected **Report** custom XML part and the content controls of the Word document.</span></span>
7. <span data-ttu-id="b8673-161">Mentse a frissített Word-dokumentumot helyileg **SampleVendPaymDocReportBounded.docx** néven.</span><span class="sxs-lookup"><span data-stu-id="b8673-161">Save the updated Word document locally as **SampleVendPaymDocReportBounded.docx**.</span></span>

## <a name="review-the-word-template-where-the-custom-xml-part-is-mapped-to-content-controls"></a><span data-ttu-id="b8673-162">Annak a Word-sablonnak az áttekintése, ahol az egyéni XML-rész tartalomvezérlőkre van leképezve</span><span class="sxs-lookup"><span data-stu-id="b8673-162">Review the Word template where the custom XML part is mapped to content controls</span></span>

1. <span data-ttu-id="b8673-163">Az asztali Word-alkalmazásban nyissa meg a **SampleVendPaymDocReportBounded.docx** sablonfájlt.</span><span class="sxs-lookup"><span data-stu-id="b8673-163">In the Word desktop application, open the **SampleVendPaymDocReportBounded.docx** template file.</span></span>
2. <span data-ttu-id="b8673-164">Ellenőrizze, hogy a sablon az ER-kimenetként létrehozandó dokumentum elrendezését tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="b8673-164">Verify that the template contains the layout of the document that you want to generate as ER output.</span></span> <span data-ttu-id="b8673-165">Az ER által futásidőben ebbe a sablonba beírt adatok helyőrzőjeként használt tartalomvezérlők a **Jelentés** egyéni XML-része és a Word dokumentum tartalomvezérlői között beállított leképezéseken alapulnak.</span><span class="sxs-lookup"><span data-stu-id="b8673-165">The content controls that are used as placeholders for data that ER will enter in this template at runtime are based on the mappings that are configured between elements of the **Report** custom XML part and the content controls of the Word document.</span></span>

![A Word-sablon előnézete az asztali alkalmazásban](../media/er-design-configuration-word-2016-11-image04.png)

## <a name="upload-the-word-template-where-the-custom-xml-part-is-mapped-to-content-controls"></a><span data-ttu-id="b8673-167">Annak a Word-sablonnak a feltöltése, ahol az egyéni XML-rész tartalomvezérlőkre van leképezve</span><span class="sxs-lookup"><span data-stu-id="b8673-167">Upload the Word template where the custom XML part is mapped to content controls</span></span>

1. <span data-ttu-id="b8673-168">A Finance alkalmazás **Mellékletek** oldalának **Törlés** elemét választva távolítsa el azt a Word-sablont, amely nem rendelkezik leképezéssel a **Jelentés** egyéni XML-részei és a tartalomvezérlők között.</span><span class="sxs-lookup"><span data-stu-id="b8673-168">In Finance, on the **Attachments** page, select **Delete** to remove the Word template that has no mappings between elements of the **Report** custom XML part and content controls.</span></span> <span data-ttu-id="b8673-169">A módosítás jóváhagyásához válassza az **Igen** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b8673-169">Select **Yes** to confirm the change.</span></span>
2. <span data-ttu-id="b8673-170">Válassza az **Új** \> **Fájl** lehetőséget, ha új sablonfájlt szeretne hozzáadni, amely a **Jelentés** egyéni XML-részei és a tartalomvezérlők közötti megfeleltetéseket tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="b8673-170">Select **New** \> **File** to add a new template file that contains mappings between elements of the **Report** custom XML part and content controls.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b8673-171">Az ER-formátumok sablonjainak tárolásához ki kell választania egy ER-paraméterekben [konfigurált](../electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents) dokumentumtípust.</span><span class="sxs-lookup"><span data-stu-id="b8673-171">You must select a document type that has been [configured](../electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents) in the ER parameters to store templates of ER formats.</span></span>

3. <span data-ttu-id="b8673-172">Válassza a **Tallózás** lehetőséget, majd tallózással keresse meg és válassza ki azt a **SampleVendPaymDocReportBounded.docx** fájlt, amelyet az [Egyéni XML-résszel rendelkező Word-dokumentum beszerzése adatleképezés végrehajtásához](#get-word-doc) eljárás elvégzésével letöltött vagy készített.</span><span class="sxs-lookup"><span data-stu-id="b8673-172">Select **Browse**, and then browse to and select the **SampleVendPaymDocReportBounded.docx** file that you downloaded or prepared by completing the procedure in the [Get a Word that has a custom XML part to do data mapping](#get-word-doc) section.</span></span>
4. <span data-ttu-id="b8673-173">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b8673-173">Select **OK**.</span></span>
5. <span data-ttu-id="b8673-174">Zárja be a **Mellékletek** lapot.</span><span class="sxs-lookup"><span data-stu-id="b8673-174">Close the **Attachments** page.</span></span>
6. <span data-ttu-id="b8673-175">A **Formátumtervező** oldal **Sablon** mezőjében válassza ki a most letöltött dokumentumot.</span><span class="sxs-lookup"><span data-stu-id="b8673-175">On the **Format designer** page, in the **Template** field, select the document that you just downloaded.</span></span>
7. <span data-ttu-id="b8673-176">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b8673-176">Select **Save**.</span></span>
8. <span data-ttu-id="b8673-177">Zárja be a **Formátumtervező** lapot.</span><span class="sxs-lookup"><span data-stu-id="b8673-177">Close the **Format designer** page.</span></span>

## <a name="mark-the-configured-format-as-runnable"></a><span data-ttu-id="b8673-178">A konfigurált formátum megjelölése futtathatóként</span><span class="sxs-lookup"><span data-stu-id="b8673-178">Mark the configured format as runnable</span></span>

<span data-ttu-id="b8673-179">Ahhoz, hogy a szerkeszthető formátum vázlatverzióját futtatni tudja, [futtathatóra](../er-quick-start2-customize-report.md#MarkFormatRunnable) kell tennie.</span><span class="sxs-lookup"><span data-stu-id="b8673-179">To run the draft version of the editable format, you must make it [runnable](../er-quick-start2-customize-report.md#MarkFormatRunnable).</span></span>

1. <span data-ttu-id="b8673-180">A Finance alkalmazásban a **Konfigurációk** oldal műveleti ablaktábláján, a **Konfigurációk** lapon, a **Speciális beállítások** csoportban válassza a **Felhasználói paraméterek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b8673-180">In Finance, on the **Configurations** page, on the Action Pane, on the **Configurations** tab, in the **Advanced settings** group, select **User parameters**.</span></span>
2. <span data-ttu-id="b8673-181">A **Felhasználói paraméterek** párbeszédpanelen állítsa a **Futtatási beállítások** beállítását **Igen** értékre, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="b8673-181">In the **User parameters** dialog box, set the **Run settings** option to **Yes**, and then select **OK**.</span></span>
3. <span data-ttu-id="b8673-182">Ha szükséges, a **Szerkesztés** gombbal az aktuális lapot szerkeszthetőre állíthatja.</span><span class="sxs-lookup"><span data-stu-id="b8673-182">Select **Edit** to make the current page editable, as required.</span></span>
4. <span data-ttu-id="b8673-183">A jelenleg kiválasztott **Minta munkalap jelentés** konfiguráció esetében állítsa **Igen** beállításra a **Vázlat futtatása** beállítást.</span><span class="sxs-lookup"><span data-stu-id="b8673-183">For the currently selected **Sample worksheet report** configuration, set the **Run Draft** option to **Yes**.</span></span>
5. <span data-ttu-id="b8673-184">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b8673-184">Select **Save**.</span></span>

## <a name="run-the-format-to-create-output-in-word-format"></a><span data-ttu-id="b8673-185">A kimenet Word formátumban való létrehozásához használt formátum futtatása</span><span class="sxs-lookup"><span data-stu-id="b8673-185">Run the format to create output in Word format</span></span>

1. <span data-ttu-id="b8673-186">A Finance alkalmazásban lépjen a **Kötelezettségek** \> **Fizetések** \> **Fizetési napló** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b8673-186">In Finance, go to **Accounts payable** \> **Payments** \> **Payment journal**.</span></span>
2. <span data-ttu-id="b8673-187">A korábban megadott fizetési naplóban válassza a **Sorok** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b8673-187">In a payment journal that you entered earlier, select **Lines**.</span></span>
3. <span data-ttu-id="b8673-188">A **Szállítói kifizetések** lapon jelölje ki a rács összes sorát.</span><span class="sxs-lookup"><span data-stu-id="b8673-188">On the **Vendor payments** page, select all rows in the grid.</span></span>
4. <span data-ttu-id="b8673-189">Válassza ki a **Fizetési állapot** \> **Nincs** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b8673-189">Select **Payment status** \> **None**.</span></span>

    ![A feldolgozandó kifizetések hozzáadva a Szállítói fizetések lapon](../media/er-design-configuration-word-2016-11-image05.png)

5. <span data-ttu-id="b8673-191">A Művelet ablaktáblán válassza ki a **Kifizetések generálása** elemet.</span><span class="sxs-lookup"><span data-stu-id="b8673-191">On the Action Pane, select **Generate payments**.</span></span>
6. <span data-ttu-id="b8673-192">A megjelenő párbeszédpanelen hajtsa végre a következő lépéseket:</span><span class="sxs-lookup"><span data-stu-id="b8673-192">In the dialog box that appears, follow these steps:</span></span>

    1. <span data-ttu-id="b8673-193">A **Fizetési mód** mezőben válassza az **Elektronikus** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b8673-193">In the **Method of payment** field, select **Electronic**.</span></span>
    2. <span data-ttu-id="b8673-194">A **Bankszámla** mezőben válassza a **GBSI OPER** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b8673-194">In the **Bank account** field, select **GBSI OPER**.</span></span>
    3. <span data-ttu-id="b8673-195">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b8673-195">Select **OK**.</span></span>

7. <span data-ttu-id="b8673-196">Az **Elektronikus jelentési paraméterek** párbeszédablakban válassza az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b8673-196">In the **Electronic report parameters** dialog box, select **OK**.</span></span>
8. <span data-ttu-id="b8673-197">A létrehozott kimenet Word-formátumban jelenik meg, és a feldolgozott kifizetések adatait tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="b8673-197">The generated output is presented in Word format and contains the details of the processed payments.</span></span> <span data-ttu-id="b8673-198">Elemezze a létrehozott kimenetet.</span><span class="sxs-lookup"><span data-stu-id="b8673-198">Analyze the generated output.</span></span>

    ![Létrehozott kimenet Word-formátumban](../media/er-design-configuration-word-2016-11-image06.png)

## <a name="additional-resources"></a><span data-ttu-id="b8673-200">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="b8673-200">Additional resources</span></span>

- [<span data-ttu-id="b8673-201">Új ER-konfiguráció tervezése Word-formátumú jelentések generálásához</span><span class="sxs-lookup"><span data-stu-id="b8673-201">Design a new ER configuration to generate reports in Word format</span></span>](../er-design-configuration-word.md)
- [<span data-ttu-id="b8673-202">Beágyazott képek és alakzatok az ER-rel generált dokumentumokban</span><span class="sxs-lookup"><span data-stu-id="b8673-202">Embed images and shapes in documents that you generate by using ER</span></span>](../electronic-reporting-embed-images-shapes.md#embed-an-image-in-a-word-document)
