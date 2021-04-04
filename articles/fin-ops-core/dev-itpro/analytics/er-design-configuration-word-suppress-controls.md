---
title: Word tartalmi vezérlőelemek figyelmen kívül hagyása a létrehozott jelentésekben
description: Ez a témakör bemutatja, hogyan kell konfigurálni egy elektronikus jelentéskészítési (ER) formátumot úgy, hogy az a jelentéseket olyan Microsoft Word formátumú fájlokként generálja, amelyekben a tartalomvezérlők el vannak rejtve.
author: NickSelin
manager: AnnBe
ms.date: 02/11/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, EROperationDesigner,  LedgerJournalTable, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-01-01
ms.dyn365.ops.version: Version 10.0.6
ms.openlocfilehash: 81ad25514154dd8982aa4f849f0b2bfeb85270f7
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/09/2021
ms.locfileid: "5562118"
---
# <a name="suppress-word-content-controls-in-generated-reports"></a><span data-ttu-id="b4fcb-103">Word tartalmi vezérlőelemek figyelmen kívül hagyása a létrehozott jelentésekben</span><span class="sxs-lookup"><span data-stu-id="b4fcb-103">Suppress Word content controls in generated reports</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b4fcb-104">Ahhoz, hogy Microsoft Word-dokumentumként hozzon létre jelentéseket, meg kell terveznie egy sablont Word-dokumentumként a jelentésekhez.</span><span class="sxs-lookup"><span data-stu-id="b4fcb-104">To generate reports as Microsoft Word documents, you must design a template for the reports as a Word document.</span></span> <span data-ttu-id="b4fcb-105">Ennek a sablonnak Word-tartalomvezérlőket kell tartalmaznia helyőrzőkként a futásidőben kitöltendő adatokhoz.</span><span class="sxs-lookup"><span data-stu-id="b4fcb-105">This template must contain Word content controls as placeholders for data that will be filled in at runtime.</span></span> <span data-ttu-id="b4fcb-106">Ha a létrehozott Word-dokumentumot szeretné használni a jelentések sablonjaként, egy új [Elektronikus jelentéskészítési (ER)](general-electronic-reporting.md) [megoldást](er-quick-start1-new-solution.md) is [konfigurálhat](er-design-configuration-word.md).</span><span class="sxs-lookup"><span data-stu-id="b4fcb-106">To use the Word document that is created as a template for your reports, you can [configure](er-design-configuration-word.md) a new [Electronic reporting (ER)](general-electronic-reporting.md) [solution](er-quick-start1-new-solution.md).</span></span> <span data-ttu-id="b4fcb-107">A megoldásnak egy ER [konfigurációt](general-electronic-reporting.md#Configuration) kell tartalmaznia egy ER [formátum](general-electronic-reporting.md#FormatComponentOutbound) összetevővel.</span><span class="sxs-lookup"><span data-stu-id="b4fcb-107">The solution must include an ER [configuration](general-electronic-reporting.md#Configuration) that contains an ER [format](general-electronic-reporting.md#FormatComponentOutbound) component.</span></span> <span data-ttu-id="b4fcb-108">Ezt az ER-formátumot úgy kell konfigurálnia, hogy a jelentés generálásához a meghatározott sablont használja.</span><span class="sxs-lookup"><span data-stu-id="b4fcb-108">This ER format must be configured to use the designed template for report generation.</span></span>

<span data-ttu-id="b4fcb-109">A Dynamics 365 Finance 10.0.6-os és újabb verzióiban konfigurálhatja az ER-formátumban található képleteket annak érdekében, hogy mellőzzön néhány Word-tartalomvezérlőt a létrehozott dokumentumokban.</span><span class="sxs-lookup"><span data-stu-id="b4fcb-109">In version 10.0.6 and later of Dynamics 365 Finance, you can configure formulas in your ER format to suppress some Word content controls in generated documents.</span></span>

<span data-ttu-id="b4fcb-110">A következő lépések bemutatják, hogy a Rendszergazdához vagy az Elektronikus jelentések funkcióival foglalkozó konzulenshez rendelt felhasználó hogyan konfigurálhatja az ER-formátumot, amely Word-fájlként generálja a jelentéseket, és elnyomja a létrehozott jelentésekben lévő, a Word-sablon használatával konfigurált tartalomvezérlőket.</span><span class="sxs-lookup"><span data-stu-id="b4fcb-110">The following steps explain how a user who is assigned to the System administrator or Electronic reporting functional consultant role can configure an ER format that generates reports as Word files and suppresses some of the content controls in the generated reports that have been configured by using a Word template.</span></span>

<span data-ttu-id="b4fcb-111">Ezeket a lépéseket a GBSI vállalatban hajthatja végre.</span><span class="sxs-lookup"><span data-stu-id="b4fcb-111">These steps can be completed in the GBSI company.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b4fcb-112">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="b4fcb-112">Prerequisites</span></span>

<span data-ttu-id="b4fcb-113">A lépések végrehajtásához először hajtsa végre a következő feladat-útmutatókban található lépéseket:</span><span class="sxs-lookup"><span data-stu-id="b4fcb-113">To complete these steps, you must first complete the steps in the following task guides:</span></span>

- [<span data-ttu-id="b4fcb-114">Az OPENXML formátumban létrejövő jelentésekre vonatkozó konfigurációk tervezése</span><span class="sxs-lookup"><span data-stu-id="b4fcb-114">Design a configuration for generating reports in OPENXML format</span></span>](./tasks/er-design-reports-openxml-2016-11.md)
- [<span data-ttu-id="b4fcb-115">ER-konfigurációk újrafelhasználása Excel-sablonok segítségével Word formátumú jelentések generálásához</span><span class="sxs-lookup"><span data-stu-id="b4fcb-115">Re-use ER configurations with Excel templates to generate reports in Word format</span></span>](./tasks/er-design-configuration-word-2016-11.md)

<span data-ttu-id="b4fcb-116">A feladat-útmutatókban található lépések végrehajtása után létrejönnek a következő fájlok:</span><span class="sxs-lookup"><span data-stu-id="b4fcb-116">When you complete the steps of these task guides, the following items are prepared:</span></span>

- <span data-ttu-id="b4fcb-117">Egy **minta munkalap jelentés** ER-formátum, amely a dokumentumok Word formátumú előállítására van konfigurálva</span><span class="sxs-lookup"><span data-stu-id="b4fcb-117">A **Sample worksheet report** ER format that is configured to generate a document in Word format</span></span>
- <span data-ttu-id="b4fcb-118">A **minta munkalap jelentés** ER-formátumának [piszkozat](general-electronic-reporting.md#component-versioning) verziója, amely **futtathatóként** van megjelölve</span><span class="sxs-lookup"><span data-stu-id="b4fcb-118">A [draft](general-electronic-reporting.md#component-versioning) version of the **Sample worksheet report** ER format that is marked as **Runnable**</span></span>
- <span data-ttu-id="b4fcb-119">A kifizetések **elektronikus** módszere, amely a szállítói kifizetések feldolgozásához a **minta munkalap jelentés** ER-formátumának használatára van konfigurálva</span><span class="sxs-lookup"><span data-stu-id="b4fcb-119">An **Electronic** method of payments that is configured to use the **Sample worksheet report** ER format for vendor payment processing</span></span>

<span data-ttu-id="b4fcb-120">Le kell tölteni és menteni a következő sablont is a mintajelentéshez:</span><span class="sxs-lookup"><span data-stu-id="b4fcb-120">You must also download and save the following template for the sample report:</span></span>

- [<span data-ttu-id="b4fcb-121">Kifizetési jelentés bekötött sablonja 2 (SampleVendPaymDocReportBounded2.docx)</span><span class="sxs-lookup"><span data-stu-id="b4fcb-121">Bounded Template 2 of Payment Report (SampleVendPaymDocReportBounded2.docx)</span></span>](https://download.microsoft.com/download/a/1/2/a126cb43-6281-4f7b-bde0-25e03ff9bc1e/SampleVendPaymDocReportBounded2.docx)

## <a name="review-the-downloaded-word-template"></a><a id="tag-control"></a><span data-ttu-id="b4fcb-122">A letöltött Word-sablon áttekintése</span><span class="sxs-lookup"><span data-stu-id="b4fcb-122">Review the downloaded Word template</span></span>

1. <span data-ttu-id="b4fcb-123">Az asztali Word-alkalmazásban nyissa meg a korábban letöltött **SampleVendPaymDocReportBounded2.docx** sablonfájlt.</span><span class="sxs-lookup"><span data-stu-id="b4fcb-123">In the Word desktop application, open the **SampleVendPaymDocReportBounded2.docx** template file that you downloaded earlier.</span></span>
2. <span data-ttu-id="b4fcb-124">Ellenőrizze, hogy a sablonfájl tartalmaz-e egy összegző szakaszt, amely megjeleníti a feldolgozott kifizetésekben teljesült összes pénznemkód esetében a teljes kifizetések összegét.</span><span class="sxs-lookup"><span data-stu-id="b4fcb-124">Verify that the template file contains a summary section that shows the total payment amounts for every currency code that has been met in the processed payments.</span></span>

    - <span data-ttu-id="b4fcb-125">Az összegző szakasz a Word-dokumentum egy külön táblájában található.</span><span class="sxs-lookup"><span data-stu-id="b4fcb-125">The summary section resides in a separate table of the Word document.</span></span>
    - <span data-ttu-id="b4fcb-126">A tábla első sorában a tábla oszlopfejlécei láthatók szakaszfejlécként.</span><span class="sxs-lookup"><span data-stu-id="b4fcb-126">The first row of this table holds the table columns headings as the section header.</span></span>
    - <span data-ttu-id="b4fcb-127">A tábla második sorában az ismétlődő tartalomellenőrző található a szakasz részleteiként.</span><span class="sxs-lookup"><span data-stu-id="b4fcb-127">The second row of this table holds the repeating content control as the section details.</span></span>
    - <span data-ttu-id="b4fcb-128">Ez a tartalomvezérlő a **Jelentés** egyéni XML-rész **Összefoglaló sorok** mezőjéhez van hozzárendelve.</span><span class="sxs-lookup"><span data-stu-id="b4fcb-128">This content control is mapped to the **SummaryLines** field of the **Report** custom XML part.</span></span>
    - <span data-ttu-id="b4fcb-129">A leképezés alapján a tartalomvezérlő a szerkeszthető ER-formátum **Összefoglaló sorok** eleméhez van társítva.</span><span class="sxs-lookup"><span data-stu-id="b4fcb-129">Based on this mapping, the content control is associated with the **SummaryLines** element of the editable ER format.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b4fcb-130">Az ismétlődő tartalomvezérlőt az **Összefoglaló sorok** kulcs címkézi, amely megfelel annak az egyéni XML-rész mezőjének, amelyben lekérdezték.</span><span class="sxs-lookup"><span data-stu-id="b4fcb-130">The repeating content control is tagged by the **SummaryLines** key that matches the field of the custom XML part that it has been mapped to.</span></span>

    ![Word-sablon elrendezés](./media/er-design-configuration-word-suppress-controls-image1.gif)

## <a name="select-the-existing-er-report-configuration"></a><span data-ttu-id="b4fcb-132">Válassza ki a meglévő ER-jelentéskonfigurációt</span><span class="sxs-lookup"><span data-stu-id="b4fcb-132">Select the existing ER report configuration</span></span>

<span data-ttu-id="b4fcb-133">A következő lépésekben újra használja majd a meglévő ER-konfigurációt, amelyet a korábban említett feladat-útmutatók lépéseinek végrehajtása során konfigurált.</span><span class="sxs-lookup"><span data-stu-id="b4fcb-133">For the following steps, you will reuse the existing ER configuration that you configured when you completed the steps in the previously mentioned task guides.</span></span>

1. <span data-ttu-id="b4fcb-134">Ugorjon a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.</span><span class="sxs-lookup"><span data-stu-id="b4fcb-134">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="b4fcb-135">Válassza a **Jelentéskészítési konfigurációk** elemet.</span><span class="sxs-lookup"><span data-stu-id="b4fcb-135">Select **Reporting configurations**.</span></span>
3. <span data-ttu-id="b4fcb-136">A **Konfigurációk** oldalon, a konfigurációk fájában bontsa ki a **Fizetési modell** elemet, majd válassza a **Minta munkalap jelentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b4fcb-136">On the **Configurations** page, in the configuration tree, expand **Payment model**, and select **Sample worksheet report**.</span></span>
4. <span data-ttu-id="b4fcb-137">Válassza a **Tervező** lehetőséget, ha szerkeszteni szeretné a kiválasztott ER-formátum piszkozatverzióját.</span><span class="sxs-lookup"><span data-stu-id="b4fcb-137">Select **Designer** to edit the draft version of the selected ER format.</span></span>

## <a name="replace-the-current-template-with-the-new-template"></a><span data-ttu-id="b4fcb-138">Cserélje ki a jelenlegi sablont az új sablonra</span><span class="sxs-lookup"><span data-stu-id="b4fcb-138">Replace the current template with the new template</span></span>

<span data-ttu-id="b4fcb-139">Jelenleg a SampleVendPaymDocReportBounded.docx fájl használatos sablonként a kimenet Word-formátumú előállításához.</span><span class="sxs-lookup"><span data-stu-id="b4fcb-139">Currently, the SampleVendPaymDocReportBounded.docx file is used as a template to generate the output in Word format.</span></span> <span data-ttu-id="b4fcb-140">A következő lépésekben ezt a Word-sablont cserélje le a korábban letöltött SampleVendPaymDocReportBounded2.docx nevű új Word-sablonra.</span><span class="sxs-lookup"><span data-stu-id="b4fcb-140">In the following steps, you will replace this Word template with the new Word template, SampleVendPaymDocReportBounded2.docx, that you downloaded earlier.</span></span>

1. <span data-ttu-id="b4fcb-141">A **Formátumtervező** oldalon válassza a **Mellékletek** elemet.</span><span class="sxs-lookup"><span data-stu-id="b4fcb-141">On the **Format designer** page, select **Attachments**.</span></span>
2. <span data-ttu-id="b4fcb-142">A meglévő sablon eltávolításához válassza a **Törlés** lehetőséget a **Mellékletek** lapon.</span><span class="sxs-lookup"><span data-stu-id="b4fcb-142">On the **Attachments** page, select **Delete** to remove the existing template.</span></span>
3. <span data-ttu-id="b4fcb-143">A törlés jóváhagyásához válassza az **Igen** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b4fcb-143">Select **Yes** to confirm the deletion.</span></span>
4. <span data-ttu-id="b4fcb-144">Válassza az **Új** \> **Fájl** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b4fcb-144">Select **New** \> **File**.</span></span>
5. <span data-ttu-id="b4fcb-145">Válassza a **Tallózás** lehetőséget, majd tallózással keresse meg és válassza ki a korábban letöltött **SampleVendPaymDocReportBounded2.docx** fájlt.</span><span class="sxs-lookup"><span data-stu-id="b4fcb-145">Select **Browse**, and browse to and select the **SampleVendPaymDocReportBounded2.docx** file that you downloaded earlier.</span></span>
6. <span data-ttu-id="b4fcb-146">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b4fcb-146">Select **OK**.</span></span>
7. <span data-ttu-id="b4fcb-147">Zárja be a **Mellékletek** lapot.</span><span class="sxs-lookup"><span data-stu-id="b4fcb-147">Close the **Attachments** page.</span></span>
8. <span data-ttu-id="b4fcb-148">A **Formátumtervező** lap **Sablon** mezőjében adja meg vagy válassza ki a **SampleVendPaymDocReportBounded2.docx** fájlt.</span><span class="sxs-lookup"><span data-stu-id="b4fcb-148">On the **Format designer** page, in the **Template** field, enter or select the **SampleVendPaymDocReportBounded2.docx** file.</span></span>

## <a name="run-the-format-to-create-word-output"></a><span data-ttu-id="b4fcb-149">Formátum futtatása Word-kimenet létrehozásához</span><span class="sxs-lookup"><span data-stu-id="b4fcb-149">Run the format to create Word output</span></span>

1. <span data-ttu-id="b4fcb-150">Ugorjon a **Kötelezettségek** \> **Fizetések** \> **Fizetési napló** pontra.</span><span class="sxs-lookup"><span data-stu-id="b4fcb-150">Go to **Accounts payable** \> **Payments** \> **Payment journal**.</span></span>
2. <span data-ttu-id="b4fcb-151">A **Szállítói kifizetések** lapon, a **Lista** lapfülön jelölje ki az összes kifizetést.</span><span class="sxs-lookup"><span data-stu-id="b4fcb-151">On the **Vendor payments** page, on the **List** tab, select all the payments.</span></span>
3. <span data-ttu-id="b4fcb-152">Válassza ki a **Fizetési állapot** \> **Nincs** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b4fcb-152">Select **Payment status** \> **None**.</span></span>
4. <span data-ttu-id="b4fcb-153">**Kifizetések létrehozása** kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="b4fcb-153">Select **Generate payments**.</span></span>
5. <span data-ttu-id="b4fcb-154">A **Fizetési mód** mezőben válassza az **Elektronikus** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b4fcb-154">In the **Method of payment** field, select **Electronic**.</span></span>
6. <span data-ttu-id="b4fcb-155">A **Bankszámla** mezőben válassza a **GBSI OPER** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b4fcb-155">In the **Bank account** field, select **GBSI OPER**.</span></span>
7. <span data-ttu-id="b4fcb-156">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b4fcb-156">Select **OK**.</span></span>
8. <span data-ttu-id="b4fcb-157">Az **Elektronikus jelentés paraméterei** párbeszédablakban kattintson az **OK** gombra, és elemezze a létrehozott kimenetet.</span><span class="sxs-lookup"><span data-stu-id="b4fcb-157">In the **Electronic report parameters** dialog box, select **OK**, and analyze the generated output.</span></span>

    ![A feldolgozandó kifizetések hozzáadva a Szállítói fizetések lapon](./media/er-design-configuration-word-suppress-controls-image2.gif)

    <span data-ttu-id="b4fcb-159">A kimenet Word-formátumban tekinthető meg, és tartalmazza az összegző szakaszt.</span><span class="sxs-lookup"><span data-stu-id="b4fcb-159">The output is presented in Word format and contains the summary section.</span></span>

## <a name="configure-the-editable-format-to-suppress-the-summary-section"></a><a id="configure-to-suppress-control"></a><span data-ttu-id="b4fcb-160">A szerkeszthető formátum konfigurálása az összegző szakasz elrejtésére</span><span class="sxs-lookup"><span data-stu-id="b4fcb-160">Configure the editable format to suppress the summary section</span></span>

<span data-ttu-id="b4fcb-161">Ha az ER-formátumot futtató felhasználó kérése alapján el szeretné rejteni az összesítő szakaszt egy létrehozott dokumentumban, akkor módosítania kell a szerkeszthető ER-formátumot.</span><span class="sxs-lookup"><span data-stu-id="b4fcb-161">If you want to suppress the summary section in a generated document, based on the request of a user who runs this ER format, you must modify the editable ER format.</span></span>

1. <span data-ttu-id="b4fcb-162">Nyissa meg a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentéskészítés** menüpontot, majd nyissa meg a szerkeszteni kívánt ER-formátum piszkozatverzióját.</span><span class="sxs-lookup"><span data-stu-id="b4fcb-162">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**, and open the draft version of the ER format for editing.</span></span>
2. <span data-ttu-id="b4fcb-163">Válassza a **Jelentéskészítési konfigurációk** elemet.</span><span class="sxs-lookup"><span data-stu-id="b4fcb-163">Select **Reporting configurations**.</span></span> 
3. <span data-ttu-id="b4fcb-164">A **Konfigurációk** oldalon, a konfigurációk fájában bontsa ki a **Fizetési modell** \> **Minta munkalap jelentés** elemet.</span><span class="sxs-lookup"><span data-stu-id="b4fcb-164">On the **Configurations** page, in the configuration tree, expand **Payment model** \> **Sample worksheet report**.</span></span>
4. <span data-ttu-id="b4fcb-165">Válassza a **Tervező** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b4fcb-165">Select **Designer**.</span></span>
5. <span data-ttu-id="b4fcb-166">A **Formátumtervező** oldalon bontsa ki a **Word** elemet, és válassza ki az **Összefoglaló sorok** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b4fcb-166">On the **Format designer** page, expand **Word**, and select **SummaryLines**.</span></span>
6. <span data-ttu-id="b4fcb-167">A **Hozzárendelés** lapfülön adjon hozzá egy új adatforrást, amely futásidőben megkérdezi a felhasználót, hogy el kell-e rejteni az összegző szakaszt:</span><span class="sxs-lookup"><span data-stu-id="b4fcb-167">On the **Mapping** tab, add a new data source to ask the user, at runtime, whether the summary section should be suppressed:</span></span>

    1. <span data-ttu-id="b4fcb-168">Válassza a **Gyökér hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="b4fcb-168">Select **Add root**.</span></span>
    2. <span data-ttu-id="b4fcb-169">Az **Adatforrás hozzáadása** párbeszédpanelen válassza az **Általános\Felhasználói beviteli paraméter** lehetőséget a **Felhasználói beviteli paraméter adatforrás tulajdonságai** párbeszédpanel megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="b4fcb-169">In the **Add data source** dialog box, select **General\User input parameter** to open the **'User input parameter' data source properties** dialog box.</span></span>
    3. <span data-ttu-id="b4fcb-170">A **Név** mezőbe írja be az **uipSuppress** szót.</span><span class="sxs-lookup"><span data-stu-id="b4fcb-170">In the **Name** field, enter **uipSuppress**.</span></span>
    4. <span data-ttu-id="b4fcb-171">A **Címke** mezőben írja be a következőt: **Összegző szakasz figyelmen kívül hagyása**.</span><span class="sxs-lookup"><span data-stu-id="b4fcb-171">In the **Label** field, enter **Suppress summary section**.</span></span>
    5. <span data-ttu-id="b4fcb-172">A **Műveletek adattípus neve** mezőben válassza ki vagy írja be a **NoYes** kifejezést.</span><span class="sxs-lookup"><span data-stu-id="b4fcb-172">In the **Operations data type name** field, select or enter **NoYes**.</span></span>
    6. <span data-ttu-id="b4fcb-173">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b4fcb-173">Select **OK**.</span></span>

7. <span data-ttu-id="b4fcb-174">Adjon hozzá egy új adatforrást a **NoYes** alkalmazás-felsorolási típusból:</span><span class="sxs-lookup"><span data-stu-id="b4fcb-174">Add a new data source of the **NoYes** application enumeration type:</span></span>

    1. <span data-ttu-id="b4fcb-175">Válassza a **Gyökér hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="b4fcb-175">Select **Add root**.</span></span>
    2. <span data-ttu-id="b4fcb-176">Az **Adatforrás hozzáadása** párbeszédpanelen válassza a **Dynamics 365 for Operations\Felsorolás** lehetőséget a **Felsorolás adatforrás tulajdonságai** párbeszédpanel megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="b4fcb-176">In the **Add data source** dialog box, select **Dynamics 365 for Operations\Enumeration** to open the **'Enumeration' data source properties** dialog box.</span></span>
    3. <span data-ttu-id="b4fcb-177">A **Név** mezőbe írja be az **enumNoYes** kifejezést.</span><span class="sxs-lookup"><span data-stu-id="b4fcb-177">In the **Name** field, enter **enumNoYes**.</span></span>
    4. <span data-ttu-id="b4fcb-178">A **Címke** mezőben írja be a következőt: **Lehetőséget figyelmen kívül hagyása**.</span><span class="sxs-lookup"><span data-stu-id="b4fcb-178">In the **Label** field, enter **Suppress options**.</span></span>
    5. <span data-ttu-id="b4fcb-179">A **Műveletek adattípus neve** mezőben válassza ki vagy írja be a **NoYes** kifejezést.</span><span class="sxs-lookup"><span data-stu-id="b4fcb-179">In the **Operations data type name** field, select or enter **NoYes**.</span></span>
    6. <span data-ttu-id="b4fcb-180">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b4fcb-180">Select **OK**.</span></span>

8. <span data-ttu-id="b4fcb-181">Állítsa be a képletet a kiválasztott **SummaryLines** formátumelemhez, hogy meghatározza, mikor legyen figyelmen kívül hagyva a kijelölt formátumelemhez társított Word-tartalomvezérlő:</span><span class="sxs-lookup"><span data-stu-id="b4fcb-181">For the selected **SummaryLines** format element, configure the formula to specify when the Word content control that is associated with the selected format element should be suppressed:</span></span>

    1. <span data-ttu-id="b4fcb-182">A **Leképezés** lap **Eltávolítva** szakaszában a **Szerkesztés** gombra kattintva nyissa meg a **[Képletszerkesztő](general-electronic-reporting-formula-designer.md)** oldalt.</span><span class="sxs-lookup"><span data-stu-id="b4fcb-182">On the **Mapping** tab, in the **Removed** section, select **Edit** to open the **[Formula designer](general-electronic-reporting-formula-designer.md)** page.</span></span>
    2. <span data-ttu-id="b4fcb-183">A **Képlet** mezőben adja meg a következő képletet: `uipSuppress = enumNoYes.Yes`.</span><span class="sxs-lookup"><span data-stu-id="b4fcb-183">In the **Formula** field, enter the formula `uipSuppress = enumNoYes.Yes`.</span></span>
    3. <span data-ttu-id="b4fcb-184">Válassza a **Mentés** lehetőséget, majd a **Képlettervező** oldalt.</span><span class="sxs-lookup"><span data-stu-id="b4fcb-184">Select **Save**, and close the **Formula designer** page.</span></span>

        > [!NOTE]
        > <span data-ttu-id="b4fcb-185">A program ezt a képletet alkalmazza egy generált dokumentumra **az összes többi formátumelem futtatása** után.</span><span class="sxs-lookup"><span data-stu-id="b4fcb-185">This formula will be applied to a generated document **after all other format elements are run**.</span></span> <span data-ttu-id="b4fcb-186">A képlet alkalmazásához a létrehozott dokumentumban megtalálható egy Word-tartalomvezérlő, amely olyan formátumelemként van megjelölve, amelyhez a képlet konfigurálva van (ebben az esetben **SummaryLines**).</span><span class="sxs-lookup"><span data-stu-id="b4fcb-186">To apply this formula, a Word content control that is tagged as a format element that the formula is configured for (**SummaryLines** in this case) is found in a generated document.</span></span> <span data-ttu-id="b4fcb-187">Ez a tartalomvezérlő ezután teljesen törlődik, együtt az azzal rendelkező Word-tábla sorával.</span><span class="sxs-lookup"><span data-stu-id="b4fcb-187">That content control is then completely removed, together with the row in the Word table that holds it.</span></span> <span data-ttu-id="b4fcb-188">Az összegző szakasz részletező sorát a program eltávolítja a generált dokumentumból.</span><span class="sxs-lookup"><span data-stu-id="b4fcb-188">The details row of the summary section is removed from the generated document.</span></span>
        >
        > <span data-ttu-id="b4fcb-189">A tervezés során előfordulhat, hogy egy formátumelemhez konfigurálja az **Eltávolítva** képletet, még akkor is, ha a használt Word-sablonban nincs olyan tartalomvezérlő, amely megfelel azon formátumelem nevének, amelyhez az **Eltávolítva** tulajdonságot konfigurálták.</span><span class="sxs-lookup"><span data-stu-id="b4fcb-189">At design time, you might configure the **Removed** formula for a format element, even though no content control in the Word template that you're using has a tag that matches the name of a format element that the **Removed** property is configured for.</span></span> <span data-ttu-id="b4fcb-190">Amikor a formátumot a tervezési időpontban ellenőrzi, egy [figyelmeztetés](er-components-inspections.md#i14) jelenik meg erről az inkonzisztenciáról.</span><span class="sxs-lookup"><span data-stu-id="b4fcb-190">When you validate the format at design time, you receive a [warning](er-components-inspections.md#i14) about this inconsistency.</span></span>
        >
        > <span data-ttu-id="b4fcb-191">Futásidőben kivétel áll elő, ha a használt Word-sablon egyetlen tartalomvezérlője sem tartalmaz olyan címkét, amely megfelel annak a formátumelemnek, amelyhez be van állítva az **Eltávolítva** tulajdonság.</span><span class="sxs-lookup"><span data-stu-id="b4fcb-191">At runtime, an exception is thrown if no content control in the Word template that you're using has a tag that matches the name of a format element that the **Removed** property is configured for.</span></span>

    4. <span data-ttu-id="b4fcb-192">A **Leképezés** lap **Eltávolítva** szakaszában állítsa a **Szülővel** beállítást **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="b4fcb-192">On the **Mapping** tab, in the **Removed** section, set the **With parent** option to **Yes**.</span></span>

        > [!NOTE]
        > <span data-ttu-id="b4fcb-193">Ha az összesítő szakasz részleteit tartalmazó sor szülőobjektumaként az egész Word-táblát el szeretné távolítani, állítsa ezt a beállítást **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="b4fcb-193">You must set this option to **Yes** to remove the whole Word table as the parent object of the row that holds the summary section details.</span></span> <span data-ttu-id="b4fcb-194">Ha a **Nem** értéket választja, a szakaszfejléc sora a generált dokumentumban marad.</span><span class="sxs-lookup"><span data-stu-id="b4fcb-194">If you set this option to **No**, the section header row remains in the generated document.</span></span>

9. <span data-ttu-id="b4fcb-195">A szerkeszthető formátum módosításainak mentéséhez válassza a **Mentés** elemet.</span><span class="sxs-lookup"><span data-stu-id="b4fcb-195">Select **Save** to save your changes to the editable format.</span></span>

    ![A létrehozott kimenet Word-formátumban](./media/er-design-configuration-word-suppress-controls-image3.gif)

## <a name="run-the-modified-format-to-create-word-output"></a><span data-ttu-id="b4fcb-197">Módosított formátum futtatása Word-kimenet létrehozásához</span><span class="sxs-lookup"><span data-stu-id="b4fcb-197">Run the modified format to create Word output</span></span>

1. <span data-ttu-id="b4fcb-198">Ugorjon a **Kötelezettségek** \> **Fizetések** \> **Fizetési napló** pontra.</span><span class="sxs-lookup"><span data-stu-id="b4fcb-198">Go to **Accounts payable** \> **Payments** \> **Payment journal**.</span></span>
2. <span data-ttu-id="b4fcb-199">Válassza ki a létrehozott kifizetési naplót, majd válassza a **Sorok** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b4fcb-199">Select the payment journal that you created, and then select **Lines**.</span></span>
3. <span data-ttu-id="b4fcb-200">A **Szállítói kifizetések** oldalon jelölje ki az összes sort, majd válassza a **Kifizetési állapot** \> **Nincs** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b4fcb-200">On the **Vendor payments** page, select all the rows, and then select **Payment status** \> **None**.</span></span>
4. <span data-ttu-id="b4fcb-201">**Kifizetések létrehozása** kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="b4fcb-201">Select **Generate payments**.</span></span>
5. <span data-ttu-id="b4fcb-202">A **Fizetési mód** mezőben válassza az **Elektronikus** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b4fcb-202">In the **Method of payment** field, select **Electronic**.</span></span>
6. <span data-ttu-id="b4fcb-203">A **Bankszámla** mezőben válassza a **GBSI OPER** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b4fcb-203">In the **Bank account** field, select **GBSI OPER**.</span></span>
7. <span data-ttu-id="b4fcb-204">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b4fcb-204">Select **OK**.</span></span>
8. <span data-ttu-id="b4fcb-205">Az **Elektronikus jelentés paraméterei** párbeszédpanelben az **Összefoglaló szakasz figyelmen kívül hagyása** mezőben válassza az **Igen** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b4fcb-205">In the **Electronic report parameters** dialog box, in the **Suppress summary section** field, select **Yes**.</span></span>
9. <span data-ttu-id="b4fcb-206">Kattintson az **OK** gombra, és elemezze a létrehozott kimenetet.</span><span class="sxs-lookup"><span data-stu-id="b4fcb-206">Select **OK**, and analyze the generated output.</span></span>

    ![Létrehozott kimenet Word-formátumban](./media/er-design-configuration-word-suppress-controls-image4.gif)

    <span data-ttu-id="b4fcb-208">A kimenet nem tartalmazza az összesítő szakaszt, mert figyelmen kívül hagyta.</span><span class="sxs-lookup"><span data-stu-id="b4fcb-208">Notice that the output doesn't contain the summary section, because it has been suppressed.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b4fcb-209">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="b4fcb-209">Additional resources</span></span>

- [<span data-ttu-id="b4fcb-210">Az OPENXML formátumban létrejövő jelentésekre vonatkozó konfigurációk tervezése</span><span class="sxs-lookup"><span data-stu-id="b4fcb-210">Design a configuration for generating reports in OPENXML format</span></span>](./tasks/er-design-reports-openxml-2016-11.md)
- [<span data-ttu-id="b4fcb-211">Új ER-konfiguráció tervezése Word formátumú jelentések generálásához</span><span class="sxs-lookup"><span data-stu-id="b4fcb-211">Design a new ER configuration to generate reports in Word format</span></span>](er-design-configuration-word.md)
- [<span data-ttu-id="b4fcb-212">ER-konfigurációk újrafelhasználása Excel-sablonok segítségével Word formátumú jelentések generálásához</span><span class="sxs-lookup"><span data-stu-id="b4fcb-212">Re-use ER configurations with Excel templates to generate reports in Word format</span></span>](./tasks/er-design-configuration-word-2016-11.md)
- [<span data-ttu-id="b4fcb-213">A konfigurált ER-összetevő ellenőrzése a futásidejű problémák megelőzése érdekében</span><span class="sxs-lookup"><span data-stu-id="b4fcb-213">Inspect the configured ER component to prevent runtime issues</span></span>](er-components-inspections.md#i14)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]