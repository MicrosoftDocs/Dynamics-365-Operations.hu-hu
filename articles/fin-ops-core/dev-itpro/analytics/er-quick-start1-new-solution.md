---
title: Új ER-megoldás tervezése egyéni jelentés nyomtatásához
description: Ez a témakör azt mutatja be, hogyan tervezhető elektronikus jelentési megoldás (ER) egyéni jelentés nyomtatásához.
author: NickSelin
manager: AnnBe
ms.date: 08/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERParameters, ERDataModelDesigner, ERModelMappingTable, ERModelMappingDesigner, EROperationDesigner, ERVendorTable
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7cd0d8e7aa9595e705416798772f52956ef609da
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4680242"
---
# <a name="design-a-new-er-solution-to-print-a-custom-report"></a><span data-ttu-id="87dde-103">Új ER-megoldás tervezése egyéni jelentés nyomtatásához</span><span class="sxs-lookup"><span data-stu-id="87dde-103">Design a new ER solution to print a custom report</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="87dde-104">A következő lépések áttekintik, hogy a Rendszergazda, az Elektronikus jelentések fejlesztője vagy az Elektronikus jelentések funkcionális konzulense szerepkörű felhasználók hogyan konfigurálhatják az ER-keretrendszer paramétereit, hogyan tervezhetik meg az új ER-megoldásokhoz szükséges ER-konfigurációkat az adott üzleti tartományok adatainak eléréséhez, illetve hogyan hozhatnak létre egyéni jelentést Microsoft Office-formátumban.</span><span class="sxs-lookup"><span data-stu-id="87dde-104">The following steps explain how a user in the System Administrator, Electronic Reporting Developer, or Electronic Reporting Functional Consultant role can configure parameters of the ER framework, design the required ER configurations of a new ER solution to access the data of a particular business domain, and generate a custom report in Microsoft Office format.</span></span> <span data-ttu-id="87dde-105">Ezeket a lépéseket a **USMF** vállalatban hajthatja végre.</span><span class="sxs-lookup"><span data-stu-id="87dde-105">These steps can be completed in the **USMF** company.</span></span>

- [<span data-ttu-id="87dde-106">ER-keretrendszer konfigurálása</span><span class="sxs-lookup"><span data-stu-id="87dde-106">Configure the ER framework</span></span>](#ConfigureFramework)

    - [<span data-ttu-id="87dde-107">ER-paraméterek konfigurálása</span><span class="sxs-lookup"><span data-stu-id="87dde-107">Configure ER parameters</span></span>](#ConfigureParameters)
    - [<span data-ttu-id="87dde-108">ER-konfigurációszolgáltató aktiválása</span><span class="sxs-lookup"><span data-stu-id="87dde-108">Activate an ER configuration provider</span></span>](#ActivateProvider)

        - [<span data-ttu-id="87dde-109">Az ER-konfigurációszolgáltatók listájának áttekintése</span><span class="sxs-lookup"><span data-stu-id="87dde-109">Review the list of ER configuration providers</span></span>](#ReviewProvidersList)
        - [<span data-ttu-id="87dde-110">Új ER-konfigurációszolgáltató hozzáadása</span><span class="sxs-lookup"><span data-stu-id="87dde-110">Add a new ER configuration provider</span></span>](#AddProvider)
        - [<span data-ttu-id="87dde-111">ER-konfigurációszolgáltató aktiválása</span><span class="sxs-lookup"><span data-stu-id="87dde-111">Activate an ER configuration provider</span></span>](#ActivateAddedProvider)

- [<span data-ttu-id="87dde-112">Tartományspecifikus adatmodell kialakítása</span><span class="sxs-lookup"><span data-stu-id="87dde-112">Design a domain-specific data model</span></span>](#DesignModel)

    - [<span data-ttu-id="87dde-113">Új adatmodell-konfiguráció importálása</span><span class="sxs-lookup"><span data-stu-id="87dde-113">Import a new data model configuration</span></span>](#ImportDataModel)
    - [<span data-ttu-id="87dde-114">Új adatmodell-konfiguráció létrehozása</span><span class="sxs-lookup"><span data-stu-id="87dde-114">Create a new data model configuration</span></span>](#DesignDataModel)

        - [<span data-ttu-id="87dde-115">Az adatmodell elnevezése</span><span class="sxs-lookup"><span data-stu-id="87dde-115">Name the data model</span></span>](#NameDataModel)
        - [<span data-ttu-id="87dde-116">Adatmodell mezőinek hozzáadása</span><span class="sxs-lookup"><span data-stu-id="87dde-116">Add data model fields</span></span>](#FieldsEntry)
        - [<span data-ttu-id="87dde-117">Az adatmodell kialakításának befejezése</span><span class="sxs-lookup"><span data-stu-id="87dde-117">Complete the design of the data model</span></span>](#CompleteDataModel)

- [<span data-ttu-id="87dde-118">Modell-leképezés tervezése a konfigurált adatmodellhez</span><span class="sxs-lookup"><span data-stu-id="87dde-118">Design a model mapping for the configured data model</span></span>](#DesignMapping)

    - [<span data-ttu-id="87dde-119">Új modell-leképezési konfiguráció importálása</span><span class="sxs-lookup"><span data-stu-id="87dde-119">Import a new model mapping configuration</span></span>](#ImportModelMapping)
    - [<span data-ttu-id="87dde-120">Új modell-leképezési konfiguráció létrehozása</span><span class="sxs-lookup"><span data-stu-id="87dde-120">Create a new model mapping configuration</span></span>](#CreateModelMapping)

        - [<span data-ttu-id="87dde-121">Új modell-leképezési összetevő tervezése</span><span class="sxs-lookup"><span data-stu-id="87dde-121">Design a new model mapping component</span></span>](#DesignMappingComponent)
        - [<span data-ttu-id="87dde-122">Adatforrások hozzáadása alkalmazástáblák eléréséhez</span><span class="sxs-lookup"><span data-stu-id="87dde-122">Add data sources to access application tables</span></span>](#AddMmDataSource1)
        - [<span data-ttu-id="87dde-123">Adatforrások hozzáadása alkalmazásfelsorolások eléréséhez</span><span class="sxs-lookup"><span data-stu-id="87dde-123">Add data sources to access application enumerations</span></span>](#AddMmDataSource2)
        - [<span data-ttu-id="87dde-124">ER-címkék hozzáadása adott nyelvű jelentés létrehozásához</span><span class="sxs-lookup"><span data-stu-id="87dde-124">Add ER labels to generate a report in a specified language</span></span>](#AddMmLabels)
        - [<span data-ttu-id="87dde-125">Adatforrás hozzáadása a felsorolási értékek és a szöveges érték összehasonlításakor kapott eredmények átalakításához</span><span class="sxs-lookup"><span data-stu-id="87dde-125">Add a data source to transform the results of comparing enumeration values to a text value</span></span>](#AddMmDataSource3)
        - [<span data-ttu-id="87dde-126">Adatforrások kötése az adatmodell mezőihez</span><span class="sxs-lookup"><span data-stu-id="87dde-126">Bind data sources to data model fields</span></span>](#AddMmBindings1)
        - [<span data-ttu-id="87dde-127">A modell-leképezés kialakításának befejezése</span><span class="sxs-lookup"><span data-stu-id="87dde-127">Complete the design of the model mapping</span></span>](#CompleteModelMapping)

- [<span data-ttu-id="87dde-128">Sablon tervezése egyéni jelentésekhez</span><span class="sxs-lookup"><span data-stu-id="87dde-128">Design a template for a custom report</span></span>](#DesignReportTemplate)
- [<span data-ttu-id="87dde-129">Formátum tervezése</span><span class="sxs-lookup"><span data-stu-id="87dde-129">Design a format</span></span>](#DesignFormat)

    - [<span data-ttu-id="87dde-130">Megtervezett formátumkonfiguráció importálása</span><span class="sxs-lookup"><span data-stu-id="87dde-130">Import a designed format configuration</span></span>](#FormatImport)
    - [<span data-ttu-id="87dde-131">Új formátumkonfiguráció létrehozása</span><span class="sxs-lookup"><span data-stu-id="87dde-131">Create a new format configuration</span></span>](#FormatCreate)

        - [<span data-ttu-id="87dde-132">Jelentéssablon importálása</span><span class="sxs-lookup"><span data-stu-id="87dde-132">Import a report template</span></span>](#ImportReportTemplate)
        - [<span data-ttu-id="87dde-133">Formátum konfigurálása</span><span class="sxs-lookup"><span data-stu-id="87dde-133">Configure a format</span></span>](#ConfigureFormat)
        - [<span data-ttu-id="87dde-134">Adatkötés definiálása a jelentés címéhez</span><span class="sxs-lookup"><span data-stu-id="87dde-134">Define the data binding for a report title</span></span>](#DefineFormatBindings)
        - [<span data-ttu-id="87dde-135">A modell adatforrásának ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="87dde-135">Review the model data source</span></span>](#ReviewModelDataSource)
        - [<span data-ttu-id="87dde-136">Formátum-összetevők összekötése az adatforrás mezőivel</span><span class="sxs-lookup"><span data-stu-id="87dde-136">Bind format elements to data source fields</span></span>](#BindFormatElements)

    - [<span data-ttu-id="87dde-137">Megtervezett formátum futtatása az ER-ből</span><span class="sxs-lookup"><span data-stu-id="87dde-137">Run a designed format from ER</span></span>](#RunFormatFromER)

- [<span data-ttu-id="87dde-138">Megtervezett formátum finomhangolása</span><span class="sxs-lookup"><span data-stu-id="87dde-138">Tune a designed format</span></span>](#TuneFormat)

    - [<span data-ttu-id="87dde-139">Formátum módosítása a létrehozott dokumentumok nevének módosításához</span><span class="sxs-lookup"><span data-stu-id="87dde-139">Modify a format to change the name of a generated document</span></span>](#ModifyToChangeName)
    - [<span data-ttu-id="87dde-140">Formátum módosítása a kérdések sorrendjének módosításához</span><span class="sxs-lookup"><span data-stu-id="87dde-140">Modify a format to change the order of questions</span></span>](#ModifyToOrder)
    - [<span data-ttu-id="87dde-141">Módosított formátum futtatása az ER-ből</span><span class="sxs-lookup"><span data-stu-id="87dde-141">Run a modified format from ER</span></span>](#RunFormatFromER2)
    - [<span data-ttu-id="87dde-142">A formátum kialakításának befejezése</span><span class="sxs-lookup"><span data-stu-id="87dde-142">Complete the format design</span></span>](#CompleteFormat)

- [<span data-ttu-id="87dde-143">Alkalmazás-összetevők fejlesztése a megtervezett jelentés meghívásához</span><span class="sxs-lookup"><span data-stu-id="87dde-143">Develop application artefacts to call the designed report</span></span>](#DevelopCustomCode)

    - [<span data-ttu-id="87dde-144">Forráskód módosítása</span><span class="sxs-lookup"><span data-stu-id="87dde-144">Modify source code</span></span>](#ModifySourceCode)

        - [<span data-ttu-id="87dde-145">Adatszerződés-osztály hozzáadása</span><span class="sxs-lookup"><span data-stu-id="87dde-145">Add a data contract class</span></span>](#DataContractClass)
        - [<span data-ttu-id="87dde-146">UI-készítő osztály hozzáadása</span><span class="sxs-lookup"><span data-stu-id="87dde-146">Add a UI builder class</span></span>](#UIBuilderClass)
        - [<span data-ttu-id="87dde-147">Adatszolgáltató-osztály hozzáadása</span><span class="sxs-lookup"><span data-stu-id="87dde-147">Add a data provider class</span></span>](#DataProviderClass)
        - [<span data-ttu-id="87dde-148">Címkéket tartalmazó fájlok hozzáadása</span><span class="sxs-lookup"><span data-stu-id="87dde-148">Add a labels file</span></span>](#LabelsFile)
        - [<span data-ttu-id="87dde-149">Jelentésszolgáltatási osztály hozzáadása</span><span class="sxs-lookup"><span data-stu-id="87dde-149">Add a report service class</span></span>](#ServiceClass)
        - [<span data-ttu-id="87dde-150">Jelentésvezérlő osztály hozzáadása</span><span class="sxs-lookup"><span data-stu-id="87dde-150">Add a report controller class</span></span>](#ControllerClass)
        - [<span data-ttu-id="87dde-151">Menüelem hozzáadása</span><span class="sxs-lookup"><span data-stu-id="87dde-151">Add a menu item</span></span>](#MenuItem)
        - [<span data-ttu-id="87dde-152">Menüelem hozzáadása a menükhöz</span><span class="sxs-lookup"><span data-stu-id="87dde-152">Add a menu item to a menu</span></span>](#Menu)
        - [<span data-ttu-id="87dde-153">Visual Studio-projekt készítése</span><span class="sxs-lookup"><span data-stu-id="87dde-153">Build a Visual Studio project</span></span>](#BuildVSProject)

    - [<span data-ttu-id="87dde-154">Formátum futtatása az alkalmazásból</span><span class="sxs-lookup"><span data-stu-id="87dde-154">Run a format from the application</span></span>](#RunFormatFromApp)

- [<span data-ttu-id="87dde-155">Megtervezett ER-megoldás finomhangolása</span><span class="sxs-lookup"><span data-stu-id="87dde-155">Tune a designed ER solution</span></span>](#TuneSolution)

    - [<span data-ttu-id="87dde-156">Modell-hozzárendelés módosítása</span><span class="sxs-lookup"><span data-stu-id="87dde-156">Modify a model mapping</span></span>](#ModifyModelMapping)

        - [<span data-ttu-id="87dde-157">Adatforrások hozzáadása adatszerződési objektum eléréséhez</span><span class="sxs-lookup"><span data-stu-id="87dde-157">Add data sources to access a data contract object</span></span>](#AddDataSource1)
        - [<span data-ttu-id="87dde-158">Adatforrások hozzáadása az ER-formátum leképezési rekordjaihoz való hozzáféréshez</span><span class="sxs-lookup"><span data-stu-id="87dde-158">Add a data source to access ER format mapping records</span></span>](#AddDataSource2)
        - [<span data-ttu-id="87dde-159">Adatforrások hozzáadása a futó ER-formátum formátumleképezési rekordjaihoz való hozzáféréshez</span><span class="sxs-lookup"><span data-stu-id="87dde-159">Add a data source to access a format mapping record of a running ER format</span></span>](#AddDataSource3)
        - [<span data-ttu-id="87dde-160">Futó ER-formátum nevének megadása az adatmodellben</span><span class="sxs-lookup"><span data-stu-id="87dde-160">Enter the name of the running ER format in the data model</span></span>](#AddBinding)
        - [<span data-ttu-id="87dde-161">A modell-leképezés kialakításának befejezése</span><span class="sxs-lookup"><span data-stu-id="87dde-161">Complete the design of the model mapping</span></span>](#CompleteModelMapping2)

    - [<span data-ttu-id="87dde-162">Formátum módosítása</span><span class="sxs-lookup"><span data-stu-id="87dde-162">Modify a format</span></span>](#ModifyFormat)

        - [<span data-ttu-id="87dde-163">Új formátumelem hozzáadása</span><span class="sxs-lookup"><span data-stu-id="87dde-163">Add a new format element</span></span>](#AddFormatElement)
        - [<span data-ttu-id="87dde-164">Hozzáadott formátumelem kötése</span><span class="sxs-lookup"><span data-stu-id="87dde-164">Bind the added format element</span></span>](#BindAddedFormatElement)
        - [<span data-ttu-id="87dde-165">A formátum kialakításának befejezése</span><span class="sxs-lookup"><span data-stu-id="87dde-165">Complete the format design</span></span>](#CompleteFormat2)

    - [<span data-ttu-id="87dde-166">Formátum futtatása az alkalmazásból</span><span class="sxs-lookup"><span data-stu-id="87dde-166">Run a format from the application</span></span>](#RunFormatFromApp2)
    - [<span data-ttu-id="87dde-167">Formátum futtatása az ER-ből</span><span class="sxs-lookup"><span data-stu-id="87dde-167">Run a format from ER</span></span>](#RunFormatFromER3)
    - [<span data-ttu-id="87dde-168">Formátum célhelyének konfigurálása a képernyőn látható előzetes verzióból</span><span class="sxs-lookup"><span data-stu-id="87dde-168">Configure a format destination for on-screen preview</span></span>](#ConfigureDestination)
    - [<span data-ttu-id="87dde-169">Formátum futtatása az alkalmazásból PDF-dokumentumként történő előzetes verzió készítéséhez</span><span class="sxs-lookup"><span data-stu-id="87dde-169">Run a format from the application to preview it as a PDF document</span></span>](#RunFormatFromApp3)

- [<span data-ttu-id="87dde-170">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="87dde-170">Additional resources</span></span>](#References)

<span data-ttu-id="87dde-171">Ebben a példában új ER-megoldást hoz létre a [Kérdőív](https://docs.microsoft.com/dynamics365/human-resources/hr-learning-questionnaires) modulhoz.</span><span class="sxs-lookup"><span data-stu-id="87dde-171">In this example, you will create a new ER solution for the [Questionnaire](https://docs.microsoft.com/dynamics365/human-resources/hr-learning-questionnaires) module.</span></span> <span data-ttu-id="87dde-172">Ezzel az új ER-megoldással jelentést tervezhet úgy, hogy Microsoft Excel-munkalapot használ sablonként.</span><span class="sxs-lookup"><span data-stu-id="87dde-172">This new ER solution lets you design a report by using a Microsoft Excel worksheet as a template.</span></span> <span data-ttu-id="87dde-173">Ezt követően létrehozhatja a **Kérdőív** jelentést Excel- vagy PDF-formátumban, valamint elkészítheti a meglévő SQL Server Reporting Services- (SSRS) jelentéseket.</span><span class="sxs-lookup"><span data-stu-id="87dde-173">You can then generate the **Questionnaire** report in Excel or PDF format, in addition to generating the existing SQL Server Reporting Services (SSRS) report.</span></span> <span data-ttu-id="87dde-174">Az új jelentést igény szerint módosíthatja később.</span><span class="sxs-lookup"><span data-stu-id="87dde-174">You can also modify the new report later, upon request.</span></span> <span data-ttu-id="87dde-175">Nincs szükség kódolásra.</span><span class="sxs-lookup"><span data-stu-id="87dde-175">No coding is required.</span></span>

1. <span data-ttu-id="87dde-176">A meglévő jelentés futtatásához lépjen a **Kérdőív** \> **Tervezés** \> **Kérdőívek jelentése** részre.</span><span class="sxs-lookup"><span data-stu-id="87dde-176">To run the existing report, go to **Questionnaire** \> **Design** \> **Questionnaires report**.</span></span>

    ![A Kérdőívek jelentése menüelem kiválasztása a Kérdőív modulban a meglévő SSRS-jelentés futtatásához](./media/er-quick-start1-application-menu-origin.png)

2. <span data-ttu-id="87dde-178">A **Kérdőívek jelentése** párbeszédpanelen adja meg a kiválasztási feltételeket.</span><span class="sxs-lookup"><span data-stu-id="87dde-178">In the **Questionnaires report** dialog box, specify selection criteria.</span></span> <span data-ttu-id="87dde-179">Alkalmazzon egy szűrőt, hogy a jelentés csak a **SBCCrsExam** kérdőívet tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="87dde-179">Apply a filter so that the report includes only the **SBCCrsExam** questionnaire.</span></span>

    ![A kiválasztási feltételek megadása a Kérdőívek jelentése párbeszédpanelen](./media/er-quick-start1-ssrs-report-dialog.png)

<span data-ttu-id="87dde-181">A következő ábrán az **SBCCrsExam** kérdőívhez SSRS-jelentés létrehozott változata látható.</span><span class="sxs-lookup"><span data-stu-id="87dde-181">The following illustration shows the generated version of the SSRS report for the **SBCCrsExam** questionnaire.</span></span>

![Létrehozott SSRS-jelentés](./media/er-quick-start1-ssrs-report.png)

## <a name="configure-the-er-framework"></a><a name="ConfigureFramework"></a><span data-ttu-id="87dde-183">ER-keretrendszer konfigurálása</span><span class="sxs-lookup"><span data-stu-id="87dde-183">Configure the ER framework</span></span>

<span data-ttu-id="87dde-184">Elektronikus jelentések fejlesztője szerepkörű felhasználóként konfigurálnia kell a minimálisan szükséges ER-paraméterek készletét, mielőtt új ER-megoldás tervezéséhez kezdené használni az ER-keretrendszert.</span><span class="sxs-lookup"><span data-stu-id="87dde-184">As a user in the Electronic Reporting Developer role, you must configure the minimal set of ER parameters before you can start to use the ER framework to design your new ER solution.</span></span>

### <a name="configure-er-parameters"></a><a name="ConfigureParameters"></a><span data-ttu-id="87dde-185">ER-paraméterek konfigurálása</span><span class="sxs-lookup"><span data-stu-id="87dde-185">Configure ER parameters</span></span>

1. <span data-ttu-id="87dde-186">Ugorjon a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.</span><span class="sxs-lookup"><span data-stu-id="87dde-186">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="87dde-187">Az **Elektronikus jelentéskészítés** munkaterületen kattintson az **Elektronikus jelentések paraméterei** hivatkozására.</span><span class="sxs-lookup"><span data-stu-id="87dde-187">In the **Electronic reporting** workspace, select **Electronic reporting parameters**.</span></span>
3. <span data-ttu-id="87dde-188">Az **Elektronikus jelentéskészítési paraméterek** oldalon, az **Általános** lapon a **Tervezői mód engedélyezése** lehetőséget állítsa **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="87dde-188">On the **Electronic reporting parameters** page, on the **General** tab, set the **Enable design mode** option to **Yes**.</span></span>
4. <span data-ttu-id="87dde-189">A **Mellékletek** lapon állítsa be a következő paramétereket:</span><span class="sxs-lookup"><span data-stu-id="87dde-189">On the **Attachments** tab, set the following parameters:</span></span>

    - <span data-ttu-id="87dde-190">A **Konfigurációk** mezőben állítsa be a **Fájl** értéket az **USMF** vállalathoz.</span><span class="sxs-lookup"><span data-stu-id="87dde-190">Set the **Configurations** field to **File** for the **USMF** company.</span></span>
    - <span data-ttu-id="87dde-191">A **Feladatarchívum**, **Ideiglenes**, **Alap** és **Egyebek** mezőkben adja meg a **Fájl** típust.</span><span class="sxs-lookup"><span data-stu-id="87dde-191">Set **Job archive**, **Temporary**, **Baseline**, and **Others** fields to **File**.</span></span>

<span data-ttu-id="87dde-192">Az ER-paraméterekkel kapcsolatos további tudnivalókat lásd: [ER-keretrendszer konfigurálása](electronic-reporting-er-configure-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="87dde-192">For more information about ER parameters, see [Configure the ER framework](electronic-reporting-er-configure-parameters.md).</span></span>

### <a name="activate-an-er-configuration-provider"></a><a name="ActivateProvider"></a><span data-ttu-id="87dde-193">ER-konfigurációszolgáltató aktiválása</span><span class="sxs-lookup"><span data-stu-id="87dde-193">Activate an ER configuration provider</span></span>

<span data-ttu-id="87dde-194">Minden ER-konfigurációt egy ER-konfigurációszolgáltató által birtokoltként kell megjelölni.</span><span class="sxs-lookup"><span data-stu-id="87dde-194">Every ER configuration is marked as owned by an ER configuration provider.</span></span> <span data-ttu-id="87dde-195">Ennek megfelelően aktiválnia kell egy ER-konfigurációszolgáltatót az **Elektronikus jelentéskészítés** munkaterületen, mielőtt megkezdené az ER-konfigurációk hozzáadását vagy szerkesztését.</span><span class="sxs-lookup"><span data-stu-id="87dde-195">Therefore, you must activate an ER configuration provider in the **Electronic reporting** workspace before you start to add or edit any ER configurations.</span></span>

> [!NOTE]
> <span data-ttu-id="87dde-196">Csak az ER-konfiguráció tulajdonosa szerkesztheti.</span><span class="sxs-lookup"><span data-stu-id="87dde-196">Only the owner of an ER configuration can edit it.</span></span> <span data-ttu-id="87dde-197">Éppen ezért aktiválnia kell a megfelelő ER-konfigurációszolgáltatót az **Elektronikus jelentéskészítés** munkaterületen, mielőtt elkezdené az ER-konfigurációk hozzáadását vagy szerkesztését.</span><span class="sxs-lookup"><span data-stu-id="87dde-197">Therefore, before an ER configuration can be edited, the appropriate ER configuration provider must be activated in the **Electronic reporting** workspace.</span></span>

#### <a name="review-the-list-of-er-configuration-providers"></a><a name="ReviewProvidersList"></a><span data-ttu-id="87dde-198">Az ER-konfigurációszolgáltatók listájának áttekintése</span><span class="sxs-lookup"><span data-stu-id="87dde-198">Review the list of ER configuration providers</span></span>

1. <span data-ttu-id="87dde-199">Ugorjon a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.</span><span class="sxs-lookup"><span data-stu-id="87dde-199">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="87dde-200">Az **Elektronikus jelentéskészítés** munkaterületen, a **Kapcsolódó hivatkozások** szakaszban, válassza a **Konfigurációszolgáltatók** elemet.</span><span class="sxs-lookup"><span data-stu-id="87dde-200">In the **Electronic reporting** workspace, in the **Related links** section, select **Configuration providers**.</span></span>
3. <span data-ttu-id="87dde-201">A **Konfigurációszolgáltatók** oldalon minden konfigurációszolgáltatói rekordnak egyedi neve és URL-címe van.</span><span class="sxs-lookup"><span data-stu-id="87dde-201">On the **Configuration providers** page, each configuration provider record has a unique name and URL.</span></span> <span data-ttu-id="87dde-202">Tekintse át az oldal tartalmát.</span><span class="sxs-lookup"><span data-stu-id="87dde-202">Review the contents of this page.</span></span> <span data-ttu-id="87dde-203">Ha a már létezik a **Litware, Inc.** (`https://www.litware.com`) rekordja, hagyja ki a következő eljárást: [Új ER-konfigurációszolgáltató hozzáadása](#ActivateProvider).</span><span class="sxs-lookup"><span data-stu-id="87dde-203">If a record for **Litware, Inc.** (`https://www.litware.com`) already exists, skip the next procedure, [Add a new ER configuration provider](#ActivateProvider).</span></span>

#### <a name="add-a-new-er-configuration-provider"></a><a name="AddProvider"></a><span data-ttu-id="87dde-204">Új ER-konfigurációszolgáltató hozzáadása</span><span class="sxs-lookup"><span data-stu-id="87dde-204">Add a new ER configuration provider</span></span>

1. <span data-ttu-id="87dde-205">A **Konfigurációszolgáltatók** oldalon válassza az **Új** elemet.</span><span class="sxs-lookup"><span data-stu-id="87dde-205">On the **Configuration providers** page, select **New**.</span></span>
2. <span data-ttu-id="87dde-206">A **Név** mezőbe írja be a következőt: **Litware, Inc.**.</span><span class="sxs-lookup"><span data-stu-id="87dde-206">In the **Name** field, enter **Litware, Inc.**</span></span>
3. <span data-ttu-id="87dde-207">Az **Internetcím** mezőben adja meg a következőt: `https://www.litware.com`.</span><span class="sxs-lookup"><span data-stu-id="87dde-207">In the **Internet address** field, enter `https://www.litware.com`.</span></span>
4. <span data-ttu-id="87dde-208">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-208">Select **Save**.</span></span>

#### <a name="activate-an-er-configuration-provider"></a><a name="ActivateAddedProvider"></a><span data-ttu-id="87dde-209">ER-konfigurációszolgáltató aktiválása</span><span class="sxs-lookup"><span data-stu-id="87dde-209">Activate an ER configuration provider</span></span>

1. <span data-ttu-id="87dde-210">Ugorjon a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.</span><span class="sxs-lookup"><span data-stu-id="87dde-210">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="87dde-211">Az **Elektronikus jelentés** munkaterületen válassza ki a **Litware, Inc.** konfigurációszolgáltatót.</span><span class="sxs-lookup"><span data-stu-id="87dde-211">In the **Electronic reporting** workspace, select the **Litware, Inc.** configuration provider.</span></span>
3. <span data-ttu-id="87dde-212">Válassza ki az **Aktív beállítása** elemet.</span><span class="sxs-lookup"><span data-stu-id="87dde-212">Select **Set active**.</span></span>

<span data-ttu-id="87dde-213">További információért az ER-konfigurációszolgáltatókkal kapcsolatban tekintse át a [Konfigurációszolgáltatók létrehozása és megjelölése aktívként](tasks/er-configuration-provider-mark-it-active-2016-11.md) eljárást.</span><span class="sxs-lookup"><span data-stu-id="87dde-213">For more information about ER configuration providers, see [Create configuration providers and mark them as active](tasks/er-configuration-provider-mark-it-active-2016-11.md).</span></span>

## <a name="design-a-domain-specific-data-model"></a><a name="DesignModel"></a><span data-ttu-id="87dde-214">Tartományspecifikus adatmodell kialakítása</span><span class="sxs-lookup"><span data-stu-id="87dde-214">Design a domain-specific data model</span></span>

<span data-ttu-id="87dde-215">Létre kell hoznia egy olyan új ER-konfigurációt, amely tartalmaz egy [adatmodell](general-electronic-reporting.md#data-model-and-model-mapping-components) összetevőt a **Kérdőív** üzleti tartományhoz.</span><span class="sxs-lookup"><span data-stu-id="87dde-215">You must create a new ER configuration that contains a [data model](general-electronic-reporting.md#data-model-and-model-mapping-components) component for the **Questionnaire** business domain.</span></span> <span data-ttu-id="87dde-216">Ez az adatmodell lesz az adatforrás, amikor megtervezi az ER-formátumot a **Kérdőív** jelentés létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="87dde-216">This data model will later be used as a data source when you design an ER format to generate the **Questionnaire** report.</span></span>

<span data-ttu-id="87dde-217">Az [Új adatmodell-konfiguráció importálása](#ImportDataModel) szakasz lépéseivel importálhatja a szükséges adatmodellt a megadott XML-fájlból.</span><span class="sxs-lookup"><span data-stu-id="87dde-217">By completing the steps in the [Import a new data model configuration](#ImportDataModel) section, you can import the required data model from the provided XML file.</span></span> <span data-ttu-id="87dde-218">Egy másik megoldás, hogy az [Új adatmodell-konfiguráció létrehozása](#DesignDataModel) szakasz lépéseit követve az alapoktól kezdve tervezi meg az adatmodellt.</span><span class="sxs-lookup"><span data-stu-id="87dde-218">Alternatively, you can complete the steps in the [Create a new data model configuration](#DesignDataModel) section to design this data model from scratch.</span></span>

### <a name="import-a-new-data-model-configuration"></a><a name="ImportDataModel"></a><span data-ttu-id="87dde-219">Új adatmodell-konfiguráció importálása</span><span class="sxs-lookup"><span data-stu-id="87dde-219">Import a new data model configuration</span></span>

1. <span data-ttu-id="87dde-220">Töltse le a [Questionnaires model.version.1.xml](https://go.microsoft.com/fwlink/?linkid=851448) fájlt, és mentse a helyi számítógépen.</span><span class="sxs-lookup"><span data-stu-id="87dde-220">Download the [Questionnaires model.version.1.xml](https://go.microsoft.com/fwlink/?linkid=851448) file, and save it to your local computer.</span></span>
2. <span data-ttu-id="87dde-221">Ugorjon a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.</span><span class="sxs-lookup"><span data-stu-id="87dde-221">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
3. <span data-ttu-id="87dde-222">Az **Elektronikus jelentéskészítés** munkaterületen válassza ki a **Jelentéskészítési konfiguráció** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-222">In the **Electronic reporting** workspace, select **Reporting configurations**.</span></span>
4. <span data-ttu-id="87dde-223">A Műveleti ablaktáblában válassza az **Átváltás** \> **Betöltés XML-fájlból** elemet.</span><span class="sxs-lookup"><span data-stu-id="87dde-223">On the Action Pane, select **Exchange** \> **Load from XML file**.</span></span>
5. <span data-ttu-id="87dde-224">Kattintson a **Tallózás** elemre, majd keresse meg és válassza ki a **Questionnaires model.version.1.xml** fájlt.</span><span class="sxs-lookup"><span data-stu-id="87dde-224">Select **Browse**, and then find and select the **Questionnaires model.version.1.xml** file.</span></span>
6. <span data-ttu-id="87dde-225">A konfiguráció importálásához kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="87dde-225">Select **OK** to import the configuration.</span></span>

<span data-ttu-id="87dde-226">A folytatáshoz ugorja át a következő eljárást: [Új adatmodell-konfiguráció létrehozása](#DesignDataModel).</span><span class="sxs-lookup"><span data-stu-id="87dde-226">To continue, skip the next procedure, [Create a new data model configuration](#DesignDataModel).</span></span>

### <a name="create-a-new-data-model-configuration"></a><a name="DesignDataModel"></a><span data-ttu-id="87dde-227">Új adatmodell-konfiguráció létrehozása</span><span class="sxs-lookup"><span data-stu-id="87dde-227">Create a new data model configuration</span></span>

1. <span data-ttu-id="87dde-228">Ugorjon a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.</span><span class="sxs-lookup"><span data-stu-id="87dde-228">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="87dde-229">Az **Elektronikus jelentéskészítés** munkaterületen válassza ki a **Jelentéskészítési konfiguráció** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-229">In the **Electronic reporting** workspace, select **Reporting configurations**.</span></span>
3. <span data-ttu-id="87dde-230">Válassza a **Konfiguráció létrehozása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-230">Select **Create configuration**.</span></span>
4. <span data-ttu-id="87dde-231">Írja be a legördülő párbeszédpanel **Név** mezőjébe ezt: **Kérdőív modellje**.</span><span class="sxs-lookup"><span data-stu-id="87dde-231">In the drop-down dialog box, in the **Name** field, enter **Questionnaire model**.</span></span>
5. <span data-ttu-id="87dde-232">A konfiguráció létrehozása válassza a **Konfiguráció létrehozása** elemet.</span><span class="sxs-lookup"><span data-stu-id="87dde-232">Select **Create configuration** to create the configuration.</span></span>

#### <a name="name-the-data-model"></a><a name="NameDataModel"></a><span data-ttu-id="87dde-233">Az adatmodell elnevezése</span><span class="sxs-lookup"><span data-stu-id="87dde-233">Name the data model</span></span>

1. <span data-ttu-id="87dde-234">A **Konfigurációk** oldalon, a konfigurációk fastruktúrájában válassza a **Kérdőív modellje** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-234">On the **Configurations** page, in the configuration tree, select **Questionnaire model**.</span></span>
2. <span data-ttu-id="87dde-235">Válassza a **Tervező** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-235">Select **Designer**.</span></span>
3. <span data-ttu-id="87dde-236">Az **Adatmodell-tervező** oldal **Általános** gyorslapján írja be a **Név** mezőbe a <a name="DataModeName"></a>**Kérdőívek** szót.</span><span class="sxs-lookup"><span data-stu-id="87dde-236">On the **Data model designer** page, on the **General** FastTab, in the **Name** field, enter <a name="DataModeName"></a>**Questionnaires**.</span></span>

#### <a name="add-new-data-model-fields"></a><a name="FieldsEntry"></a><span data-ttu-id="87dde-237">Új adatmodellmezők hozzáadása</span><span class="sxs-lookup"><span data-stu-id="87dde-237">Add new data model fields</span></span>

1. <span data-ttu-id="87dde-238">Az **Adatmodell-tervező** oldalon válassza az **Új** elemet.</span><span class="sxs-lookup"><span data-stu-id="87dde-238">On the **Data model designer** page, select **New**.</span></span>
2. <span data-ttu-id="87dde-239">Az adatmodell csomópontjainak hozzáadására szolgáló legördülő párbeszédpanelen hajtsa végre az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="87dde-239">In the drop-down dialog box for adding a data model node, follow these steps:</span></span>

    1. <span data-ttu-id="87dde-240">Az új csomópont típusaként adja meg a **Modellgyökér** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-240">Select **Model root** as the type of the new node.</span></span>
    2. <span data-ttu-id="87dde-241">A **Név** mezőbe írja be a <a name="RootDefinitionName"></a>**Gyökér** szót.</span><span class="sxs-lookup"><span data-stu-id="87dde-241">In the **Name** field, enter <a name="RootDefinitionName"></a>**Root**.</span></span>
    3. <span data-ttu-id="87dde-242">Új csomópont hozzáadásához kattintson a **Hozzáadás** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="87dde-242">Select **Add** to add the new node.</span></span>

    <span data-ttu-id="87dde-243">Ez a gyökérleíró biztosít majd adatokat a **Kérdőív** jelentéshez.</span><span class="sxs-lookup"><span data-stu-id="87dde-243">This root descriptor will be used to provide data for the **Questionnaire** report.</span></span> <span data-ttu-id="87dde-244">Egy adatmodellhez több leíró is tartozhat.</span><span class="sxs-lookup"><span data-stu-id="87dde-244">A single data model can have multiple descriptors.</span></span> <span data-ttu-id="87dde-245">Mindegyik leíró meghatározható egy adott ER-jelentésformátumhoz, hogy meg lehessen határozni a jelentés létrehozásához szükséges adatokat.</span><span class="sxs-lookup"><span data-stu-id="87dde-245">Each descriptor can be specified for a single ER format, to identify data that is required to generate the report.</span></span>

3. <span data-ttu-id="87dde-246">Válassza ismét az **Új** lehetőséget, majd az adatmodell csomópontjainak hozzáadására szolgáló legördülő párbeszédpanelen hajtsa végre az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="87dde-246">Select **New** again, and then, in the drop-down dialog box for adding a data model node, follow these steps:</span></span>

    1. <span data-ttu-id="87dde-247">Az új csomópont típusaként válassza az **Aktív csomópont gyermeke** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-247">Select **Child of an active node** as the type of the new node.</span></span>
    2. <span data-ttu-id="87dde-248">A **Név** mezőbe írja be a **CompanyName** szót.</span><span class="sxs-lookup"><span data-stu-id="87dde-248">In the **Name** field, enter **CompanyName**.</span></span>
    3. <span data-ttu-id="87dde-249">A **Cikktípus** mezőben válassza ki a **Karakterlánc** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-249">In the **Item type** field, select **String**.</span></span>
    4. <span data-ttu-id="87dde-250">Új mező hozzáadásához kattintson a **Hozzáadás** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="87dde-250">Select **Add** to add the new field.</span></span>

    <span data-ttu-id="87dde-251">Ez a mező szükséges, hogy át lehessen adni az aktuális vállalat nevét az olyan ER-jelentéseknek, amelyek ezt az adatmodellt használják adatforrásként.</span><span class="sxs-lookup"><span data-stu-id="87dde-251">This field is required to pass the name of the current company to an ER report that consumes this data model as a data source.</span></span>

4. <span data-ttu-id="87dde-252">Válassza ismét az **Új** lehetőséget, majd az adatmodell csomópontjainak hozzáadására szolgáló legördülő párbeszédpanelen hajtsa végre az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="87dde-252">Select **New** again, and then, in the drop-down dialog box for adding a data model node, follow these steps:</span></span>

    1. <span data-ttu-id="87dde-253">Az új csomópont típusaként válassza az **Aktív csomópont gyermeke** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-253">Select **Child of an active node** as the type of the new node.</span></span>
    2. <span data-ttu-id="87dde-254">A **Név** mezőbe írja be a **Kérdőív** szót.</span><span class="sxs-lookup"><span data-stu-id="87dde-254">In the **Name** field, enter **Questionnaire**.</span></span>
    3. <span data-ttu-id="87dde-255">A **Cikktípus** mezőben válassza ki a **Rekordlista** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-255">In the **Item type** field, select **Record list**.</span></span>
    4. <span data-ttu-id="87dde-256">Új mező hozzáadásához kattintson a **Hozzáadás** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="87dde-256">Select **Add** to add the new field.</span></span>

    <span data-ttu-id="87dde-257">Ez a mező adja majd át a kérdőívek listáját az olyan ER-jelentéseknek, amelyek ezt az adatmodellt használják adatforrásként.</span><span class="sxs-lookup"><span data-stu-id="87dde-257">This field will be used to pass the list of questionnaires to an ER report that consumes this data model as a data source.</span></span>

5. <span data-ttu-id="87dde-258">Válassza ki a **Kérdőív** csomópontot.</span><span class="sxs-lookup"><span data-stu-id="87dde-258">Select the **Questionnaire** node.</span></span>
6. <span data-ttu-id="87dde-259">Hasonló módon adja hozzá a szerkeszthető adatmodell kötelező mezőit, amíg a következő adatmodell-struktúrát nem kapja.</span><span class="sxs-lookup"><span data-stu-id="87dde-259">Continue to add the required fields of the editable data model in the same manner until you complete the following data model structure.</span></span>

    | <span data-ttu-id="87dde-260">Mező elérési útja</span><span class="sxs-lookup"><span data-stu-id="87dde-260">Field path</span></span>                                                    | <span data-ttu-id="87dde-261">Adattípus</span><span class="sxs-lookup"><span data-stu-id="87dde-261">Data type</span></span>   | <span data-ttu-id="87dde-262">Mező megnevezése/visszaadott érték</span><span class="sxs-lookup"><span data-stu-id="87dde-262">Field designation/returned value</span></span> |
    |---------------------------------------------------------------|-------------|----------------------------------|
    | <span data-ttu-id="87dde-263">Gyökér</span><span class="sxs-lookup"><span data-stu-id="87dde-263">Root</span></span>                                                          |             | <span data-ttu-id="87dde-264">A kérdőív adatainak kérésére szolgáló hivatkozási pont.</span><span class="sxs-lookup"><span data-stu-id="87dde-264">The reference point to request questionnaire data.</span></span> |
    | <span data-ttu-id="87dde-265">Root\\CompanyName</span><span class="sxs-lookup"><span data-stu-id="87dde-265">Root\\CompanyName</span></span>                                             | <span data-ttu-id="87dde-266">Karakterlánc</span><span class="sxs-lookup"><span data-stu-id="87dde-266">String</span></span>      | <span data-ttu-id="87dde-267">Az aktuális vállalat neve.</span><span class="sxs-lookup"><span data-stu-id="87dde-267">The name of the current company.</span></span> |
    | <span data-ttu-id="87dde-268">Root\\ExecutionContext</span><span class="sxs-lookup"><span data-stu-id="87dde-268">Root\\ExecutionContext</span></span>                                        | <span data-ttu-id="87dde-269">Rögzítés</span><span class="sxs-lookup"><span data-stu-id="87dde-269">Record</span></span>      | <span data-ttu-id="87dde-270">Formátum-végrehajtás részletei.</span><span class="sxs-lookup"><span data-stu-id="87dde-270">Format execution details.</span></span> |
    | <span data-ttu-id="87dde-271">Root\\ExecutionContext\\FormatName</span><span class="sxs-lookup"><span data-stu-id="87dde-271">Root\\ExecutionContext\\FormatName</span></span>                            | <span data-ttu-id="87dde-272">Karakterlánc</span><span class="sxs-lookup"><span data-stu-id="87dde-272">String</span></span>      | <span data-ttu-id="87dde-273">Az éppen futtatott ER-formátum neve.</span><span class="sxs-lookup"><span data-stu-id="87dde-273">The name of the ER format that is being run.</span></span> |
    | <span data-ttu-id="87dde-274">Root\\Questionnaire</span><span class="sxs-lookup"><span data-stu-id="87dde-274">Root\\Questionnaire</span></span>                                           | <span data-ttu-id="87dde-275">Rekordlista</span><span class="sxs-lookup"><span data-stu-id="87dde-275">Record list</span></span> | <span data-ttu-id="87dde-276">A kérdőívek listája</span><span class="sxs-lookup"><span data-stu-id="87dde-276">The list of questionnaires</span></span> |
    | <span data-ttu-id="87dde-277">Root\\Questionnaire\\Active</span><span class="sxs-lookup"><span data-stu-id="87dde-277">Root\\Questionnaire\\Active</span></span>                                   | <span data-ttu-id="87dde-278">Karakterlánc</span><span class="sxs-lookup"><span data-stu-id="87dde-278">String</span></span>      | <span data-ttu-id="87dde-279">Az aktuális kérdőív állapota.</span><span class="sxs-lookup"><span data-stu-id="87dde-279">The status of the current questionnaire.</span></span> |
    | <span data-ttu-id="87dde-280">Root\\Questionnaire\\Code</span><span class="sxs-lookup"><span data-stu-id="87dde-280">Root\\Questionnaire\\Code</span></span>                                     | <span data-ttu-id="87dde-281">Karakterlánc</span><span class="sxs-lookup"><span data-stu-id="87dde-281">String</span></span>      | <span data-ttu-id="87dde-282">Az aktuális kérdőív kódja.</span><span class="sxs-lookup"><span data-stu-id="87dde-282">The code of the current questionnaire.</span></span> |
    | <span data-ttu-id="87dde-283">Root\\Questionnaire\\Description</span><span class="sxs-lookup"><span data-stu-id="87dde-283">Root\\Questionnaire\\Description</span></span>                              | <span data-ttu-id="87dde-284">Karakterlánc</span><span class="sxs-lookup"><span data-stu-id="87dde-284">String</span></span>      | <span data-ttu-id="87dde-285">Az aktuális kérdőív leírása.</span><span class="sxs-lookup"><span data-stu-id="87dde-285">The description of the current questionnaire.</span></span> |
    | <span data-ttu-id="87dde-286">Root\\Questionnaire\\QuestionnaireType</span><span class="sxs-lookup"><span data-stu-id="87dde-286">Root\\Questionnaire\\QuestionnaireType</span></span>                        | <span data-ttu-id="87dde-287">Karakterlánc</span><span class="sxs-lookup"><span data-stu-id="87dde-287">String</span></span>      | <span data-ttu-id="87dde-288">Az aktuális kérdőív típusa.</span><span class="sxs-lookup"><span data-stu-id="87dde-288">The type of the current questionnaire.</span></span> |
    | <span data-ttu-id="87dde-289">Root\\Questionnaire\\QuestionOrder</span><span class="sxs-lookup"><span data-stu-id="87dde-289">Root\\Questionnaire\\QuestionOrder</span></span>                            | <span data-ttu-id="87dde-290">Karakterlánc</span><span class="sxs-lookup"><span data-stu-id="87dde-290">String</span></span>      | <span data-ttu-id="87dde-291">Az aktuális kérdőív numerikus sorrendje.</span><span class="sxs-lookup"><span data-stu-id="87dde-291">The numerical order of the current questionnaire.</span></span> |
    | <span data-ttu-id="87dde-292">Root\\Questionnaire\\ResultsGroup</span><span class="sxs-lookup"><span data-stu-id="87dde-292">Root\\Questionnaire\\ResultsGroup</span></span>                             | <span data-ttu-id="87dde-293">Rögzítés</span><span class="sxs-lookup"><span data-stu-id="87dde-293">Record</span></span>      | <span data-ttu-id="87dde-294">Az aktuális kérdőív eredményparaméterei.</span><span class="sxs-lookup"><span data-stu-id="87dde-294">The result parameters of the current questionnaire.</span></span> |
    | <span data-ttu-id="87dde-295">Root\\Questionnaire\\ResultsGroup\\Code</span><span class="sxs-lookup"><span data-stu-id="87dde-295">Root\\Questionnaire\\ResultsGroup\\Code</span></span>                       | <span data-ttu-id="87dde-296">Karakterlánc</span><span class="sxs-lookup"><span data-stu-id="87dde-296">String</span></span>      | <span data-ttu-id="87dde-297">Az aktuális eredménycsoport azonosítókódja.</span><span class="sxs-lookup"><span data-stu-id="87dde-297">The identification code of the current result group.</span></span> |
    | <span data-ttu-id="87dde-298">Root\\Questionnaire\\ResultsGroup\\Description</span><span class="sxs-lookup"><span data-stu-id="87dde-298">Root\\Questionnaire\\ResultsGroup\\Description</span></span>                | <span data-ttu-id="87dde-299">Karakterlánc</span><span class="sxs-lookup"><span data-stu-id="87dde-299">String</span></span>      | <span data-ttu-id="87dde-300">Az aktuális eredménycsoport leírása.</span><span class="sxs-lookup"><span data-stu-id="87dde-300">The description of the current result group.</span></span> |
    | <span data-ttu-id="87dde-301">Root\\Questionnaire\\ResultsGroup\\MaxNumberOfPoints</span><span class="sxs-lookup"><span data-stu-id="87dde-301">Root\\Questionnaire\\ResultsGroup\\MaxNumberOfPoints</span></span>          | <span data-ttu-id="87dde-302">Valós</span><span class="sxs-lookup"><span data-stu-id="87dde-302">Real</span></span>        | <span data-ttu-id="87dde-303">A maximálisan megszerezhető pontok száma.</span><span class="sxs-lookup"><span data-stu-id="87dde-303">The maximum number of points that could be earned.</span></span> |
    | <span data-ttu-id="87dde-304">Root\\Questionnaire\\Question</span><span class="sxs-lookup"><span data-stu-id="87dde-304">Root\\Questionnaire\\Question</span></span>                                 | <span data-ttu-id="87dde-305">Rekordlista</span><span class="sxs-lookup"><span data-stu-id="87dde-305">Record list</span></span> | <span data-ttu-id="87dde-306">Az aktuális kérdőív kérdéseinek listája.</span><span class="sxs-lookup"><span data-stu-id="87dde-306">The list of questions for the current questionnaire.</span></span> |
    | <span data-ttu-id="87dde-307">Root\\Questionnaire\\Question\\CollectionSequenceNumber</span><span class="sxs-lookup"><span data-stu-id="87dde-307">Root\\Questionnaire\\Question\\CollectionSequenceNumber</span></span>       | <span data-ttu-id="87dde-308">Egész</span><span class="sxs-lookup"><span data-stu-id="87dde-308">Integer</span></span>     | <span data-ttu-id="87dde-309">Az aktuális válaszok gyűjteményének sorszáma.</span><span class="sxs-lookup"><span data-stu-id="87dde-309">The sequence number of the current answer collection.</span></span> |
    | <span data-ttu-id="87dde-310">Root\\Questionnaire\\Question\\Id</span><span class="sxs-lookup"><span data-stu-id="87dde-310">Root\\Questionnaire\\Question\\Id</span></span>                             | <span data-ttu-id="87dde-311">Karakterlánc</span><span class="sxs-lookup"><span data-stu-id="87dde-311">String</span></span>      | <span data-ttu-id="87dde-312">Az aktuális kérdés azonosítókódja.</span><span class="sxs-lookup"><span data-stu-id="87dde-312">The identification code of the current question.</span></span> |
    | <span data-ttu-id="87dde-313">Root\\Questionnaire\\Question\\MustBeCompleted</span><span class="sxs-lookup"><span data-stu-id="87dde-313">Root\\Questionnaire\\Question\\MustBeCompleted</span></span>                | <span data-ttu-id="87dde-314">Karakterlánc</span><span class="sxs-lookup"><span data-stu-id="87dde-314">String</span></span>      | <span data-ttu-id="87dde-315">Jelölő, amely azt jelzi, hogy az aktuális kérdést meg kell-e válaszolni.</span><span class="sxs-lookup"><span data-stu-id="87dde-315">A flag that indicates whether the current question must be answered.</span></span> |
    | <span data-ttu-id="87dde-316">Root\\Questionnaire\\Question\\PrimaryQuestion</span><span class="sxs-lookup"><span data-stu-id="87dde-316">Root\\Questionnaire\\Question\\PrimaryQuestion</span></span>                | <span data-ttu-id="87dde-317">Karakterlánc</span><span class="sxs-lookup"><span data-stu-id="87dde-317">String</span></span>      | <span data-ttu-id="87dde-318">Jelölő, amely azt jelzi, hogy az aktuális kérdés elsődleges-e.</span><span class="sxs-lookup"><span data-stu-id="87dde-318">A flag that indicates whether the current question is primary.</span></span> |
    | <span data-ttu-id="87dde-319">Root\\Questionnaire\\Question\\SequenceNumber</span><span class="sxs-lookup"><span data-stu-id="87dde-319">Root\\Questionnaire\\Question\\SequenceNumber</span></span>                 | <span data-ttu-id="87dde-320">Egész</span><span class="sxs-lookup"><span data-stu-id="87dde-320">Integer</span></span>     | <span data-ttu-id="87dde-321">Az aktuális kérdés sorszáma.</span><span class="sxs-lookup"><span data-stu-id="87dde-321">The sequence number of the current question.</span></span> |
    | <span data-ttu-id="87dde-322">Root\\Questionnaire\\Question\\Text</span><span class="sxs-lookup"><span data-stu-id="87dde-322">Root\\Questionnaire\\Question\\Text</span></span>                           | <span data-ttu-id="87dde-323">Karakterlánc</span><span class="sxs-lookup"><span data-stu-id="87dde-323">String</span></span>      | <span data-ttu-id="87dde-324">Az aktuális kérdés szövege.</span><span class="sxs-lookup"><span data-stu-id="87dde-324">The text of the current question.</span></span> |
    | <span data-ttu-id="87dde-325">Root\\Questionnaire\\Question\\Answer</span><span class="sxs-lookup"><span data-stu-id="87dde-325">Root\\Questionnaire\\Question\\Answer</span></span>                         | <span data-ttu-id="87dde-326">Rekordlista</span><span class="sxs-lookup"><span data-stu-id="87dde-326">Record list</span></span> | <span data-ttu-id="87dde-327">Az aktuális kérdés válaszainak listája.</span><span class="sxs-lookup"><span data-stu-id="87dde-327">The list of answers for the current question.</span></span> |
    | <span data-ttu-id="87dde-328">Root\\Questionnaire\\Question\\Answer\\CorrectAnswer</span><span class="sxs-lookup"><span data-stu-id="87dde-328">Root\\Questionnaire\\Question\\Answer\\CorrectAnswer</span></span>          | <span data-ttu-id="87dde-329">Karakterlánc</span><span class="sxs-lookup"><span data-stu-id="87dde-329">String</span></span>      | <span data-ttu-id="87dde-330">Jelölő, amely azt jelzi, hogy az aktuális válasz helyes-e.</span><span class="sxs-lookup"><span data-stu-id="87dde-330">A flag that indicates whether the current answer is correct.</span></span> |
    | <span data-ttu-id="87dde-331">Root\\Questionnaire\\Question\\Answer\\Points</span><span class="sxs-lookup"><span data-stu-id="87dde-331">Root\\Questionnaire\\Question\\Answer\\Points</span></span>                 | <span data-ttu-id="87dde-332">Valós</span><span class="sxs-lookup"><span data-stu-id="87dde-332">Real</span></span>        | <span data-ttu-id="87dde-333">Az aktuális válasz kiválasztása alkalmával kapott pontok.</span><span class="sxs-lookup"><span data-stu-id="87dde-333">The points that are earned when the current answer is selected.</span></span> |
    | <span data-ttu-id="87dde-334">Root\\Questionnaire\\Question\\Answer\\SequenceNumber</span><span class="sxs-lookup"><span data-stu-id="87dde-334">Root\\Questionnaire\\Question\\Answer\\SequenceNumber</span></span>         | <span data-ttu-id="87dde-335">Egész</span><span class="sxs-lookup"><span data-stu-id="87dde-335">Integer</span></span>     | <span data-ttu-id="87dde-336">Az aktuális válasz sorszáma.</span><span class="sxs-lookup"><span data-stu-id="87dde-336">The sequence number of the current answer.</span></span> |
    | <span data-ttu-id="87dde-337">Root\\Questionnaire\\Question\\Answer\\Text</span><span class="sxs-lookup"><span data-stu-id="87dde-337">Root\\Questionnaire\\Question\\Answer\\Text</span></span>                   | <span data-ttu-id="87dde-338">Karakterlánc</span><span class="sxs-lookup"><span data-stu-id="87dde-338">String</span></span>      | <span data-ttu-id="87dde-339">Az aktuális válasz szövege.</span><span class="sxs-lookup"><span data-stu-id="87dde-339">The text of the current answer.</span></span> |

    <span data-ttu-id="87dde-340">A következő ábra a befejezett szerkeszthető adatmodellt mutatja az **Adatmodell-tervező** oldalon.</span><span class="sxs-lookup"><span data-stu-id="87dde-340">The following illustration shows the completed editable data model on the **Data model designer** page.</span></span>

    ![Konfigurált adatmodell az ER adatmodell-tervezőjében](./media/er-quick-start1-model2.png)

7. <span data-ttu-id="87dde-342">Mentse el a módosításokat.</span><span class="sxs-lookup"><span data-stu-id="87dde-342">Save your changes.</span></span>
8. <span data-ttu-id="87dde-343">Zárja be az **Adatmodell-tervező** oldalt.</span><span class="sxs-lookup"><span data-stu-id="87dde-343">Close the **Data model designer** page.</span></span>

#### <a name="complete-the-design-of-the-data-model"></a><a name="CompleteDataModel"></a><span data-ttu-id="87dde-344">Az adatmodell kialakításának befejezése</span><span class="sxs-lookup"><span data-stu-id="87dde-344">Complete the design of the data model</span></span>

1. <span data-ttu-id="87dde-345">Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.</span><span class="sxs-lookup"><span data-stu-id="87dde-345">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="87dde-346">A **Konfigurációk** oldalon, a konfigurációk fastruktúrájában válassza a **Kérdőív modellje** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-346">On the **Configurations** page, in the configuration tree, select **Questionnaire model**.</span></span>
3. <span data-ttu-id="87dde-347">A **Verziók** gyorslapon válassza ki azt a konfigurációverziót, amelynek az állapota **Piszkozat**.</span><span class="sxs-lookup"><span data-stu-id="87dde-347">On the **Versions** FastTab, select the configuration version that has a status of **Draft**.</span></span>
4. <span data-ttu-id="87dde-348">Válassza az **Állapot módosítása** \> **Teljes** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-348">Select **Change status** \> **Complete**.</span></span>

<span data-ttu-id="87dde-349">A konfiguráció 1. verziójának állapota **Piszkozatról** **Befejezett** értékre módosul.</span><span class="sxs-lookup"><span data-stu-id="87dde-349">The status of version 1 of this configuration is changed from **Draft** to **Completed**.</span></span> <span data-ttu-id="87dde-350">Az 1. verzió a későbbiekben már nem módosítható.</span><span class="sxs-lookup"><span data-stu-id="87dde-350">Version 1 can no longer be changed.</span></span> <span data-ttu-id="87dde-351">Ez a verzió tartalmazza a konfigurált adatmodellt, és a többi ER-konfiguráció alapjaként használható.</span><span class="sxs-lookup"><span data-stu-id="87dde-351">This version contains the configured data model and can be used as the basis for other ER configurations.</span></span> <span data-ttu-id="87dde-352">A konfiguráció 2. változata létrejön **Piszkozat** állapottal.</span><span class="sxs-lookup"><span data-stu-id="87dde-352">Version 2 of this configuration is created and has a status of **Draft**.</span></span> <span data-ttu-id="87dde-353">Ezt a verziót a **Kérdőív** adatmodell módosításával szerkesztheti.</span><span class="sxs-lookup"><span data-stu-id="87dde-353">You can edit this version to adjust the **Questionnaire** data model.</span></span>

![A szerkeszthető ER-konfiguráció verziói a Konfigurációk oldalon](./media/er-quick-start1-model-configuration.png)

<span data-ttu-id="87dde-355">További információ az ER-konfigurációk verziószámozásáról: [Elektronikus jelentéskészítés (ER) áttekintése](general-electronic-reporting.md#component-versioning).</span><span class="sxs-lookup"><span data-stu-id="87dde-355">For more information about versioning for ER configurations, see [Electronic reporting (ER) overview](general-electronic-reporting.md#component-versioning).</span></span>

> [!NOTE]
> <span data-ttu-id="87dde-356">A konfigurált adatmodell a **Kérdőív** üzleti terület absztrakt ábrázolása, és nem tartalmaz konkrét, Microsoft Dynamics 365 Finance-specifikus összetevőket.</span><span class="sxs-lookup"><span data-stu-id="87dde-356">The configured data model is your abstract representation of the **Questionnaire** business domain and contains no relations to artefacts that are specific to Microsoft Dynamics 365 Finance.</span></span>

## <a name="design-a-model-mapping-for-the-configured-data-model"></a><a name="DesignMapping"></a><span data-ttu-id="87dde-357">Modell-leképezés tervezése a konfigurált adatmodellhez</span><span class="sxs-lookup"><span data-stu-id="87dde-357">Design a model mapping for the configured data model</span></span>

<span data-ttu-id="87dde-358">Elektronikus jelentések fejlesztője szerepkörű felhasználóként létre kell hoznia egy olyan új ER-konfigurációt, amely [modell-leképezési](general-electronic-reporting.md#data-model-and-model-mapping-components) összetevőt tartalmaz a **Kérdőív** adatmodellhez.</span><span class="sxs-lookup"><span data-stu-id="87dde-358">As a user in the Electronic Reporting Developer role, you must create a new ER configuration that contains a [model mapping](general-electronic-reporting.md#data-model-and-model-mapping-components) component for the **Questionnaire** data model.</span></span> <span data-ttu-id="87dde-359">Mivel ez az összetevő a Finance konfigurált adatmodelljét valósítja, Finance-specifikus.</span><span class="sxs-lookup"><span data-stu-id="87dde-359">Because this component implements the configured data model for Finance, it's Finance-specific.</span></span> <span data-ttu-id="87dde-360">A modell-hozzárendelési összetevőt úgy kell konfigurálni, hogy megadja azokat az alkalmazásobjektumokat, amelyeket a futásidőben használni kell a konfigurált adatmodell alkalmazásadatokkal való feltöltéséhez.</span><span class="sxs-lookup"><span data-stu-id="87dde-360">You must configure the model mapping component to specify the application objects that must be used to fill in the configured data model with application data at runtime.</span></span> <span data-ttu-id="87dde-361">Ennek a feladatnak a végrehajtásához ismernie kell a **Kérdőív** üzleti terület adatszerkezetét megvalósítási részleteit a Finance rendszerben.</span><span class="sxs-lookup"><span data-stu-id="87dde-361">To complete this task, you must be aware of the implementation details of the data structure of the **Questionnaire** business domain in Finance.</span></span>

<span data-ttu-id="87dde-362">Az alábbi [Új modell-leképezési konfiguráció importálása](#ImportModelMapping) szakasz lépéseivel importálhatja a szükséges modell-leképezési konfigurációt a megadott XML-fájlból.</span><span class="sxs-lookup"><span data-stu-id="87dde-362">By completing the steps in the [Import a new model mapping configuration](#ImportModelMapping) section that follows, you can import the required model mapping configuration from the provided XML file.</span></span> <span data-ttu-id="87dde-363">Egy másik megoldás, hogy az [Új modell-leképezés létrehozása](#CreateModelMapping) szakasz lépéseit követve az alapoktól kezdve tervezi meg a modell-leképezést.</span><span class="sxs-lookup"><span data-stu-id="87dde-363">Alternatively, you can complete the steps in the [Create a new model mapping configuration](#CreateModelMapping) section to design this model mapping from scratch.</span></span>

### <a name="import-a-new-model-mapping-configuration"></a><a name="ImportModelMapping"></a><span data-ttu-id="87dde-364">Új modell-leképezési konfiguráció importálása</span><span class="sxs-lookup"><span data-stu-id="87dde-364">Import a new model mapping configuration</span></span>

1. <span data-ttu-id="87dde-365">Töltse le a [Questionnaires mapping.version.1.1.xml](https://go.microsoft.com/fwlink/?linkid=851448) fájlt, és mentse a helyi számítógépen.</span><span class="sxs-lookup"><span data-stu-id="87dde-365">Download the [Questionnaires mapping.version.1.1.xml](https://go.microsoft.com/fwlink/?linkid=851448) file, and save it to your local computer.</span></span>
2. <span data-ttu-id="87dde-366">Ugorjon a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.</span><span class="sxs-lookup"><span data-stu-id="87dde-366">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
3. <span data-ttu-id="87dde-367">Az **Elektronikus jelentéskészítés** munkaterületen válassza ki a **Jelentéskészítési konfiguráció** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-367">In the **Electronic reporting** workspace, select **Reporting configurations**.</span></span>
4. <span data-ttu-id="87dde-368">A Műveleti ablaktáblában válassza az **Átváltás** \> **Betöltés XML-fájlból** elemet.</span><span class="sxs-lookup"><span data-stu-id="87dde-368">On the Action Pane, select **Exchange** \> **Load from XML file**.</span></span>
5. <span data-ttu-id="87dde-369">Kattintson a **Tallózás** elemre, majd keresse meg és válassza ki a **Questionnaires mapping.version.1.1.xml** fájlt.</span><span class="sxs-lookup"><span data-stu-id="87dde-369">Select **Browse**, and then find and select the **Questionnaires mapping.version.1.1.xml** file.</span></span>
6. <span data-ttu-id="87dde-370">A konfiguráció importálásához kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="87dde-370">Select **OK** to import the configuration.</span></span>

<span data-ttu-id="87dde-371">A folytatáshoz ugorja át a következő eljárást: [Új modell-leképezési konfiguráció létrehozása](#CreateModelMapping).</span><span class="sxs-lookup"><span data-stu-id="87dde-371">To continue, skip the next procedure, [Create a new model mapping configuration](#CreateModelMapping).</span></span>

### <a name="create-a-new-model-mapping-configuration"></a><a name="CreateModelMapping"></a><span data-ttu-id="87dde-372">Új modell-leképezési konfiguráció létrehozása</span><span class="sxs-lookup"><span data-stu-id="87dde-372">Create a new model mapping configuration</span></span>

1. <span data-ttu-id="87dde-373">Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.</span><span class="sxs-lookup"><span data-stu-id="87dde-373">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="87dde-374">A **Konfigurációk** oldalon, a konfigurációk fastruktúrájában válassza a **Kérdőív modellje** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-374">On the **Configurations** page, in the configuration tree, select **Questionnaire model**.</span></span>
3. <span data-ttu-id="87dde-375">Válassza a **Konfiguráció létrehozása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-375">Select **Create configuration**.</span></span>
4. <span data-ttu-id="87dde-376">A legördülő párbeszédpanelen hajtsa végre a következő lépéseket:</span><span class="sxs-lookup"><span data-stu-id="87dde-376">In the drop-down dialog box, follow these steps:</span></span>

    1. <span data-ttu-id="87dde-377">Az **Új** mezőben válassza az **Adatmodell kérdőívein alapuló modell-leképezés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-377">In the **New** field, select **Model Mapping based on data model Questionnaires**.</span></span>
    2. <span data-ttu-id="87dde-378">A **Név** mezőbe írja be **Kérdőív leképezése** szöveget.</span><span class="sxs-lookup"><span data-stu-id="87dde-378">In the **Name** field, enter **Questionnaire mapping**.</span></span>
    3. <span data-ttu-id="87dde-379">Az **Adatmodell definíciója** mezőben válassza ki a **Gyökér** definíciót.</span><span class="sxs-lookup"><span data-stu-id="87dde-379">In the **Data model definition** field, select the **Root** definition.</span></span>
    4. <span data-ttu-id="87dde-380">A konfiguráció létrehozása válassza a **Konfiguráció létrehozása** elemet.</span><span class="sxs-lookup"><span data-stu-id="87dde-380">Select **Create configuration** to create the configuration.</span></span>

#### <a name="design-a-new-model-mapping-component"></a><a name="DesignMappingComponent"></a><span data-ttu-id="87dde-381">Új modell-leképezési összetevő tervezése</span><span class="sxs-lookup"><span data-stu-id="87dde-381">Design a new model mapping component</span></span>

1. <span data-ttu-id="87dde-382">A **Konfigurációk** oldalon, a konfigurációk fastruktúrájában válassza a **Kérdőív leképezése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-382">On the **Configurations** page, in the configuration tree, select **Questionnaire mapping**.</span></span>
2. <span data-ttu-id="87dde-383">Válassza ki a **Tervezőt** a leképezések listájának megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="87dde-383">Select **Designer** to open the list of mappings.</span></span>
3. <span data-ttu-id="87dde-384">Válassza azt a **Kérdőívek leképezése** leképezést, amelyet a rendszer automatikusan hozzáadott a **Gyökér** definícióhoz.</span><span class="sxs-lookup"><span data-stu-id="87dde-384">Select the **Questionnaires mapping** mapping that was automatically added for the **Root** definition</span></span>
4. <span data-ttu-id="87dde-385">A kiválasztott hozzárendelés konfigurálásához válassza ki a **Tervező** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-385">Select **Designer** to start to configure the selected mapping.</span></span>

<span data-ttu-id="87dde-386">A rendszer automatikusan hozzáad egy új leképezést a **Gyökér** definícióhoz.</span><span class="sxs-lookup"><span data-stu-id="87dde-386">A new mapping is automatically added for the **Root** definition.</span></span> <span data-ttu-id="87dde-387">Ez a leképezés a **Modellhez** irányt használja.</span><span class="sxs-lookup"><span data-stu-id="87dde-387">This mapping has the **To model** direction.</span></span> <span data-ttu-id="87dde-388">Ezért ez a hozzárendelés használható az adatmodell szükséges adatokkal való feltöltéséhez.</span><span class="sxs-lookup"><span data-stu-id="87dde-388">Therefore, this mapping can be used to fill in a data model with required data.</span></span>

#### <a name="add-data-sources-to-access-application-tables"></a><a name="AddMmDataSource1"></a><span data-ttu-id="87dde-389">Adatforrások hozzáadása alkalmazástáblák eléréséhez</span><span class="sxs-lookup"><span data-stu-id="87dde-389">Add data sources to access application tables</span></span>

<span data-ttu-id="87dde-390">Az adatforrásokat konfigurálni kell, hogy elérjék a kérdőív részleteit tartalmazó alkalmazástáblákat.</span><span class="sxs-lookup"><span data-stu-id="87dde-390">You must configure data sources to access the application tables that contain questionnaire details.</span></span>

1. <span data-ttu-id="87dde-391">A **Modell-leképezés tervező** oldal **Adatforrástípusok** paneljén válassza a **Dynamics 365 for Operations\\Táblarekordok** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-391">On the **Model mapping designer** page, in the **Data source types** pane, select **Dynamics 365 for Operations\\Table records**.</span></span>
2. <span data-ttu-id="87dde-392">Adjon hozzá egy olyan új adatforrást, amely a KMCollection tábla elérésére szolgál. A táblában minden rekord egyetlen kérdőívhez tartozik:</span><span class="sxs-lookup"><span data-stu-id="87dde-392">Add a new data source that will be used to access the KMCollection table, where every record represents a single questionnaire:</span></span>

    1. <span data-ttu-id="87dde-393">Az **Adatforrás** panelen válassza a **Gyökér hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="87dde-393">In the **Data sources** pane, select **Add root**.</span></span>
    2. <span data-ttu-id="87dde-394">A párbeszédpanel **Név** mezőjébe írja be a **Kérdőív** kifejezést.</span><span class="sxs-lookup"><span data-stu-id="87dde-394">In dialog box, in the **Name** field, enter **Questionnaire**.</span></span>
    3. <span data-ttu-id="87dde-395">A **Tábla** mezőbe írja be a **KMCollection** szót.</span><span class="sxs-lookup"><span data-stu-id="87dde-395">In the **Table** field, enter **KMCollection**.</span></span>
    4. <span data-ttu-id="87dde-396">Állítsa a **Lekérdezés kérése** beállítást **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="87dde-396">Set the **Ask for query** option to **Yes**.</span></span> <span data-ttu-id="87dde-397">Ezt követően futásidőben ehhez a táblához megadhatja a [szűrési](../../fin-ops/get-started/advanced-filtering-query-options.md) beállításokat a rendszerlekérdezés párbeszédpanelen.</span><span class="sxs-lookup"><span data-stu-id="87dde-397">You will then be able to specify [filtering](../../fin-ops/get-started/advanced-filtering-query-options.md) options for this table in the system query dialog box at runtime.</span></span>
    5. <span data-ttu-id="87dde-398">Az új adatforrás hozzáadásához kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="87dde-398">Select **OK** to add the new data source.</span></span>

3. <span data-ttu-id="87dde-399">Az **Adatforrástípusok** panelen válassza a **Dynamics 365 for Operations\\Táblarekordok** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-399">In the **Data source types** pane, select **Dynamics 365 for Operations\\Table records**.</span></span>
4. <span data-ttu-id="87dde-400">Adjon hozzá egy olyan új adatforrást, amely a KMQuestion tábla elérésére szolgál. A táblában minden rekord a kérdőív egyetlen kérdéséhez tartozik:</span><span class="sxs-lookup"><span data-stu-id="87dde-400">Add a new data source that will be used to access the KMQuestion table, where every record represents a single question in a questionnaire:</span></span>

    1. <span data-ttu-id="87dde-401">Az **Adatforrás** panelen válassza a **Gyökér hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="87dde-401">In the **Data sources** pane, select **Add root**.</span></span>
    2. <span data-ttu-id="87dde-402">A párbeszédpanel **Név** mezőjébe írja be a **Kérdés** kifejezést.</span><span class="sxs-lookup"><span data-stu-id="87dde-402">In the dialog box, in the **Name** field, enter **Question**.</span></span>
    3. <span data-ttu-id="87dde-403">A **Tábla** mezőbe írja be a **KMQuestion** szót.</span><span class="sxs-lookup"><span data-stu-id="87dde-403">In the **Table** field, enter **KMQuestion**.</span></span>
    4. <span data-ttu-id="87dde-404">Az új adatforrás hozzáadásához kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="87dde-404">Select **OK** to add the new data source.</span></span>

5. <span data-ttu-id="87dde-405">Az **Adatforrástípusok** panelen válassza a **Dynamics 365 for Operations\\Táblarekordok** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-405">In the **Data source types** pane, select **Dynamics 365 for Operations\\Table records**.</span></span>
6. <span data-ttu-id="87dde-406">Adjon hozzá egy olyan új adatforrást, amely a KMAnswer tábla elérésére szolgál. A táblában minden rekord a kérdőív adott kérdésének egyetlen válaszához tartozik:</span><span class="sxs-lookup"><span data-stu-id="87dde-406">Add a new data source try that will be used to access the KMAnswer table, where every record represents a single answer to a question in a questionnaire:</span></span>

    1. <span data-ttu-id="87dde-407">Az **Adatforrás** panelen válassza a **Gyökér hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="87dde-407">In the **Data sources** pane, select **Add root**.</span></span>
    2. <span data-ttu-id="87dde-408">A **Név** mezőbe írja be a **Válasz** szót.</span><span class="sxs-lookup"><span data-stu-id="87dde-408">In the **Name** field, enter **Answer**.</span></span>
    3. <span data-ttu-id="87dde-409">A **Tábla** mezőbe írja be a **KMAnswer** szót.</span><span class="sxs-lookup"><span data-stu-id="87dde-409">In the **Table** field, enter **KMAnswer**.</span></span>
    4. <span data-ttu-id="87dde-410">Az új adatforrás hozzáadásához kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="87dde-410">Select **OK** to add the new data source.</span></span>

7. <span data-ttu-id="87dde-411">Az **Adatforrástípusok** panelen válassza a **Függvények\\Számított mező** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-411">In the **Data source types** pane, select **Functions\\Calculated field**.</span></span>
8. <span data-ttu-id="87dde-412">Adjon hozzá egy olyan új számított mezőt, amelyet a KMQuestionResultGroup tábla rekordjainak elérésére fog használni a szülő KMCollection tábla összes rekordjából:</span><span class="sxs-lookup"><span data-stu-id="87dde-412">Add a new calculated field that will be used to access a record of the KMQuestionResultGroup table from every record of the parent KMCollection table:</span></span>

    1. <span data-ttu-id="87dde-413">Az **Adatforrások** panelen válassza a **Kérdőív** elemet.</span><span class="sxs-lookup"><span data-stu-id="87dde-413">In the **Data sources** pane, select **Questionnaire**.</span></span>
    2. <span data-ttu-id="87dde-414">Válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-414">Select **Add**.</span></span>
    3. <span data-ttu-id="87dde-415">A párbeszédpanel **Név** mezőjébe írja be a következőt: **\$ResultGroup**.</span><span class="sxs-lookup"><span data-stu-id="87dde-415">In the dialog box, in the **Name** field, enter **\$ResultGroup**.</span></span>
    4. <span data-ttu-id="87dde-416">Válassza a **Képlet szerkesztése** elemet.</span><span class="sxs-lookup"><span data-stu-id="87dde-416">Select **Edit formula**.</span></span>
    5. <span data-ttu-id="87dde-417">Az [ER-receptúraszerkesztő](general-electronic-reporting-formula-designer.md) **Receptúra** mezőjében adja meg a **FIRSTORNULL(\@.'\<Relations'.KMQuestionResultGroup)** képletet a KMCollection és a KMQuestionResultGroup tábla közötti egy-a-többhöz kapcsolat [elérési útjának](er-formula-language.md#paths) használatához.</span><span class="sxs-lookup"><span data-stu-id="87dde-417">In the [ER formula editor](general-electronic-reporting-formula-designer.md), in the **Formula** field, enter **FIRSTORNULL(\@.'\<Relations'.KMQuestionResultGroup)** to use the [path](er-formula-language.md#paths) of the one-to-many relation between the KMCollection and KMQuestionResultGroup tables.</span></span>
    6. <span data-ttu-id="87dde-418">Válassza a **Mentés** gombot, majd zárja be a receptúraszerkesztőt.</span><span class="sxs-lookup"><span data-stu-id="87dde-418">Select **Save**, and close the formula editor.</span></span>
    7. <span data-ttu-id="87dde-419">Az új számított mező hozzáadásához kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="87dde-419">Select **OK** to add the new calculated field.</span></span>

9. <span data-ttu-id="87dde-420">Az **Adatforrástípusok** panelen válassza a **Függvények\\Számított mező** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-420">In the **Data source types** pane, select **Functions\\Calculated field**.</span></span>
10. <span data-ttu-id="87dde-421">Adjon hozzá egy olyan új számított mezőt, amelyet a KMQuestion tábla kérdésrekordjainak elérésére fog használni a szülő KMCollectionQuestion tábla összes rekordjából:</span><span class="sxs-lookup"><span data-stu-id="87dde-421">Add a new calculated field that will be used to access question records of the KMQuestion table from every record of the parent KMCollectionQuestion table:</span></span>

    1. <span data-ttu-id="87dde-422">Az **Adatforrások** panelen válassza a **Kérdőív** elemet.</span><span class="sxs-lookup"><span data-stu-id="87dde-422">In the **Data sources** pane, select **Questionnaire**.</span></span>
    2. <span data-ttu-id="87dde-423">Bontsa ki a KMCollection tábla egy-a-többhöz kapcsolatait tartalmazó **\<Kapcsolatok** csomópontot.</span><span class="sxs-lookup"><span data-stu-id="87dde-423">Expand the **\<Relations** node that contains one-to-many relations of the KMCollection table.</span></span>
    3. <span data-ttu-id="87dde-424">Válassza ki a kapcsolódó **KMCollectionQuestion** táblát, majd a **Hozzáadás** elemet.</span><span class="sxs-lookup"><span data-stu-id="87dde-424">Select the related **KMCollectionQuestion** table, and then select **Add**.</span></span>
    4. <span data-ttu-id="87dde-425">A párbeszédpanel **Név** mezőjébe írja be a **\$Kérdés** kifejezést.</span><span class="sxs-lookup"><span data-stu-id="87dde-425">In the dialog box, in the **Name** field, enter **\$Question**.</span></span>
    5. <span data-ttu-id="87dde-426">Válassza a **Képlet szerkesztése** elemet.</span><span class="sxs-lookup"><span data-stu-id="87dde-426">Select **Edit formula**.</span></span>
    6. <span data-ttu-id="87dde-427">A receptúraszerkesztő **Receptúra** mezőjébe írja be a **FIRSTORNULL (FILTER(Question, Question.kmQuestionId = \@.kmQuestionId))** képletet a megfelelő kérdésrekordok KMQuestion táblából való visszaadásához.</span><span class="sxs-lookup"><span data-stu-id="87dde-427">In the formula editor, in the **Formula** field, enter **FIRSTORNULL (FILTER(Question, Question.kmQuestionId = \@.kmQuestionId))** to return the appropriate question records from the KMQuestion table.</span></span>
    7. <span data-ttu-id="87dde-428">Válassza a **Mentés** gombot, majd zárja be a receptúraszerkesztőt.</span><span class="sxs-lookup"><span data-stu-id="87dde-428">Select **Save**, and close the formula editor.</span></span>
    8. <span data-ttu-id="87dde-429">Az új számított mező hozzáadásához kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="87dde-429">Select **OK** to add the new calculated field.</span></span>

11. <span data-ttu-id="87dde-430">Az **Adatforrástípusok** panelen válassza a **Függvények\\Számított mező** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-430">In the **Data source types** pane, select **Functions\\Calculated field**.</span></span>
12. <span data-ttu-id="87dde-431">Adjon hozzá egy olyan új számított mezőt, amelyet a KMAnswer tábla válaszrekordjainak elérésére fog használni a szülő KMQuestion tábla összes rekordjából:</span><span class="sxs-lookup"><span data-stu-id="87dde-431">Add a new calculated field that will be used to access answer records of the KMAnswer table from every record of the parent KMQuestion table:</span></span>

    1. <span data-ttu-id="87dde-432">Az **Adatforrások** panelen válassza a **Questionnaire.\<Relations.KMCollectionQuestion.\$Question**, majd a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-432">In the **Data sources** pane, select **Questionnaire.\<Relations.KMCollectionQuestion.\$Question**, and then select **Add**.</span></span>
    2. <span data-ttu-id="87dde-433">A párbeszédpanel **Név** mezőjébe írja be a **\$Válasz** kifejezést.</span><span class="sxs-lookup"><span data-stu-id="87dde-433">In the dialog box, in the **Name** field, enter **\$Answer**.</span></span>
    3. <span data-ttu-id="87dde-434">Válassza a **Képlet szerkesztése** elemet.</span><span class="sxs-lookup"><span data-stu-id="87dde-434">Select **Edit formula**.</span></span>
    4. <span data-ttu-id="87dde-435">A receptúraszerkesztő **Receptúra** mezőjébe írja be a **FILTER (Answer, Answer.kmAnswerCollectionId = \@.kmAnswerCollectionId)** képletet a megfelelő válaszrekordok KMAnswer táblából való visszaadásához.</span><span class="sxs-lookup"><span data-stu-id="87dde-435">In the formula editor, in the **Formula** field, enter **FILTER (Answer, Answer.kmAnswerCollectionId = \@.kmAnswerCollectionId)** to return the appropriate answer records from the KMAnswer table.</span></span>
    5. <span data-ttu-id="87dde-436">Válassza a **Mentés** gombot, majd zárja be a receptúraszerkesztőt.</span><span class="sxs-lookup"><span data-stu-id="87dde-436">Select **Save**, and close the formula editor.</span></span>
    6. <span data-ttu-id="87dde-437">Az új számított mező hozzáadásához kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="87dde-437">Select **OK** to add the new calculated field.</span></span>

13. <span data-ttu-id="87dde-438">Az **Adatforrástípusok** panelen válassza a **Dynamics 365 for Operations\\Tábla** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-438">In the **Data source types** pane, select **Dynamics 365 for Operations\\Table**.</span></span>
14. <span data-ttu-id="87dde-439">Adjon hozzá egy olyan új adatforrást, amely a CompanyInfo tábla metódusaihoz való hozzáférésre szolgál majd.</span><span class="sxs-lookup"><span data-stu-id="87dde-439">Add a new data source that will be used to access methods of the CompanyInfo table.</span></span> <span data-ttu-id="87dde-440">Ügyeljen arra, hogy a tábla **find()** metódusa olyan rekordot ad vissza, amely az aktuális Finance-példánynak azt a vállalatát jelöli, amelynek a környezetében megtörtént ennek a hozzárendelésnek a meghívása.</span><span class="sxs-lookup"><span data-stu-id="87dde-440">Note that the **find()** method of this table returns a record that represents a company of the current Finance instance that this mapping is called in the context of.</span></span>

    1. <span data-ttu-id="87dde-441">Az **Adatforrás** panelen válassza a **Gyökér hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="87dde-441">In the **Data sources** pane, select **Add root**.</span></span>
    2. <span data-ttu-id="87dde-442">A párbeszédpanel **Név** mezőjébe írja be a **CompanyInfo** kifejezést.</span><span class="sxs-lookup"><span data-stu-id="87dde-442">In the dialog box, in the **Name** field, enter **CompanyInfo**.</span></span>
    3. <span data-ttu-id="87dde-443">A **Tábla** mezőbe írja be a **CompanyInfo** szót.</span><span class="sxs-lookup"><span data-stu-id="87dde-443">In the **Table** field, enter **CompanyInfo**.</span></span>
    4. <span data-ttu-id="87dde-444">Az új adatforrás hozzáadásához kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="87dde-444">Select **OK** to add the new data source.</span></span>

#### <a name="add-data-sources-to-access-application-enumerations"></a><a name="AddMmDataSource2"></a><span data-ttu-id="87dde-445">Adatforrások hozzáadása alkalmazásfelsorolások eléréséhez</span><span class="sxs-lookup"><span data-stu-id="87dde-445">Add data sources to access application enumerations</span></span>

<span data-ttu-id="87dde-446">Az alkalmazásfelsorolások eléréséhez és az alkalmazásfelsorolások értékének az alkalmazástáblákban lévő **Felsorolás** típusú mezők értékének való összevetéséhez adatforrásokat kell konfigurálni.</span><span class="sxs-lookup"><span data-stu-id="87dde-446">You must configure data sources to access application enumerations and compare their values with values of fields of the **Enumeration** type in the application tables.</span></span> <span data-ttu-id="87dde-447">Az adatmodell megfelelő mezőinek kitöltéséhez az összehasonlítás eredményét kell használni.</span><span class="sxs-lookup"><span data-stu-id="87dde-447">You must use the result of the comparison to fill in appropriate fields of the data model.</span></span>

1. <span data-ttu-id="87dde-448">A **Modell-leképezés tervező** oldal **Adatforrástípusok** paneljén válassza a **Dynamics 365 for Operations\\Felsorolás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-448">On the **Model mapping designer** page, in the **Data source types** pane, select **Dynamics 365 for Operations\\Enumeration**.</span></span>
2. <span data-ttu-id="87dde-449">Adjon hozzá egy olyan új adatforrást, amely az **EnumAppNoYes** felsorolás értékeihez való hozzáférésre szolgál majd:</span><span class="sxs-lookup"><span data-stu-id="87dde-449">Add a new data source that will be used to access values of the **EnumAppNoYes** enumeration:</span></span>

    1. <span data-ttu-id="87dde-450">Az **Adatforrás** panelen válassza a **Gyökér hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="87dde-450">In the **Data sources** pane, select **Add root**.</span></span>
    2. <span data-ttu-id="87dde-451">A párbeszédpanel **Név** mezőjébe írja be az **EnumAppNoYes** kifejezést.</span><span class="sxs-lookup"><span data-stu-id="87dde-451">In the dialog box, in the **Name** field, enter **EnumAppNoYes**.</span></span>
    3. <span data-ttu-id="87dde-452">A **Felsorolás** mezőbe írja be a **NoYes** kifejezést.</span><span class="sxs-lookup"><span data-stu-id="87dde-452">In the **Enumeration** field, enter **NoYes**.</span></span>
    4. <span data-ttu-id="87dde-453">Az új adatforrás hozzáadásához kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="87dde-453">Select **OK** to add the new data source.</span></span>

3. <span data-ttu-id="87dde-454">Az **Adatforrástípusok** panelen válassza a **Dynamics 365 for Operations\\Felsorolás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-454">In the **Data source types** pane, select **Dynamics 365 for Operations\\Enumeration**.</span></span>
4. <span data-ttu-id="87dde-455">Adjon hozzá egy olyan új adatforrást, amely a **KMCollectionQuestionMode** felsorolás értékeihez való hozzáférésre szolgál majd:</span><span class="sxs-lookup"><span data-stu-id="87dde-455">Add a new data source that will be used to access the values of the **KMCollectionQuestionMode** enumeration:</span></span>

    1. <span data-ttu-id="87dde-456">Az **Adatforrás** panelen válassza a **Gyökér hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="87dde-456">In the **Data sources** pane, select **Add root**.</span></span>
    2. <span data-ttu-id="87dde-457">A párbeszédpanel **Név** mezőjébe írja be az **EnumAppQuestionOrder** kifejezést.</span><span class="sxs-lookup"><span data-stu-id="87dde-457">In the dialog box, in the **Name** field, enter **EnumAppQuestionOrder**.</span></span>
    3. <span data-ttu-id="87dde-458">A **Felsorolás** mezőbe írja be a **KMCollectionQuestionMode** kifejezést.</span><span class="sxs-lookup"><span data-stu-id="87dde-458">In the **Enumeration** field, enter **KMCollectionQuestionMode**.</span></span>
    4. <span data-ttu-id="87dde-459">Az új adatforrás hozzáadásához kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="87dde-459">Select **OK** to add the new data source.</span></span>

#### <a name="add-er-labels-to-generate-a-report-in-a-specified-language"></a><a name="AddMmLabels"></a><span data-ttu-id="87dde-460">ER-címkék hozzáadása adott nyelvű jelentés létrehozásához</span><span class="sxs-lookup"><span data-stu-id="87dde-460">Add ER labels to generate a report in a specified language</span></span>

<span data-ttu-id="87dde-461">Ha bizonyos adatforrásokat úgy szeretne konfigurálni, hogy olyan értékeket adjanak vissza, amelyek a modell-leképezés hívásának kontextusában meghatározott nyelvtől függenek, hozzáadhat ER-címkéket.</span><span class="sxs-lookup"><span data-stu-id="87dde-461">You can add ER labels to configure some of your data sources to return values that depend on the language that is defined in the context of the model mapping's call.</span></span>

1. <span data-ttu-id="87dde-462">A **Modell-hozzárendelési tervező** oldal **Adatforrások** paneljén válassza a **Válasz**, majd a **Szerkesztés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-462">On the **Model mapping designer** page, in the **Data sources** pane, select **Answer**, and then select **Edit**.</span></span>
2. <span data-ttu-id="87dde-463">Aktiválja a **Címke** mezőt.</span><span class="sxs-lookup"><span data-stu-id="87dde-463">Activate the **Label** field.</span></span>
3. <span data-ttu-id="87dde-464">Válassza a **Fordítás** elemet.</span><span class="sxs-lookup"><span data-stu-id="87dde-464">Select **Translate**.</span></span>
4. <span data-ttu-id="87dde-465">A **Szöveg fordítása** párbeszédpanelen hajtsa végre a következő lépéseket:</span><span class="sxs-lookup"><span data-stu-id="87dde-465">In the **Text translation** dialog box, follow these steps:</span></span>

    1. <span data-ttu-id="87dde-466">A **Címkeazonosító** mezőbe írja a **PositiveAnswer** értéket.</span><span class="sxs-lookup"><span data-stu-id="87dde-466">In the **Label Id** field, enter **PositiveAnswer**.</span></span>
    2. <span data-ttu-id="87dde-467">A **Szöveg az alapértelmezett nyelven** mezőben adja meg az **Igen** értéket.</span><span class="sxs-lookup"><span data-stu-id="87dde-467">In the **Text in default language** field, enter **Yes**.</span></span>
    3. <span data-ttu-id="87dde-468">Válassza a **Fordítás** elemet.</span><span class="sxs-lookup"><span data-stu-id="87dde-468">Select **Translate**.</span></span>
    4. <span data-ttu-id="87dde-469">A **Címkeazonosító** mezőbe írja a **NegativeAnswer** értéket.</span><span class="sxs-lookup"><span data-stu-id="87dde-469">In the **Label Id** field, enter **NegativeAnswer**.</span></span>
    5. <span data-ttu-id="87dde-470">A **Szöveg az alapértelmezett nyelven** mezőben adja meg a **Nem** értéket.</span><span class="sxs-lookup"><span data-stu-id="87dde-470">In the **Text in default language** field, enter **No**.</span></span>
    6. <span data-ttu-id="87dde-471">Válassza a **Fordítás** elemet.</span><span class="sxs-lookup"><span data-stu-id="87dde-471">Select **Translate**.</span></span>

5. <span data-ttu-id="87dde-472">Zárja be a **Szöveg fordítása** párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="87dde-472">Close the **Text translation** dialog box.</span></span>
6. <span data-ttu-id="87dde-473">Válassza a **Mégse** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-473">Select **Cancel**.</span></span>

![ER-címkék hozzáadása szerkeszthető modell-leképezéshez](./media/er-quick-start1-adding-labels.png)

<span data-ttu-id="87dde-475">Eddig csak az alapértelmezett nyelvhez vett fel ER-címkéket.</span><span class="sxs-lookup"><span data-stu-id="87dde-475">You've entered ER labels only for the default language.</span></span> <span data-ttu-id="87dde-476">További információ az ER-címkék más nyelvekre való lefordításáról: [Többnyelvű jelentések tervezése](er-design-multilingual-reports.md).</span><span class="sxs-lookup"><span data-stu-id="87dde-476">For information about how ER labels can be translated into other languages, see [Design multilingual reports](er-design-multilingual-reports.md).</span></span>

#### <a name="add-a-data-source-to-transform-the-results-of-comparing-enumeration-values-to-a-text-value"></a><a name="AddMmDataSource3"></a><span data-ttu-id="87dde-477">Adatforrás hozzáadása a felsorolási értékek és a szöveges érték összehasonlításakor kapott eredmények átalakításához</span><span class="sxs-lookup"><span data-stu-id="87dde-477">Add a data source to transform the results of comparing enumeration values to a text value</span></span>

<span data-ttu-id="87dde-478">Mivel a különböző forrásokhoz többször át kell alakítani a felsorolás értékeinek és a szövegértékek összevetése során kapott eredményeket, célszerű ezt a logikát egyetlen adatforrásként konfigurálni.</span><span class="sxs-lookup"><span data-stu-id="87dde-478">Because you must transform the results of the comparison between enumeration values and text values several times for difference sources, it's a good idea to configure this logic as a single data source.</span></span> <span data-ttu-id="87dde-479">Ha azonban ezt az adatforrást újra fel szeretné használni, akkor paraméteres adatforrásként kell konfigurálnia.</span><span class="sxs-lookup"><span data-stu-id="87dde-479">However, to make this data source reusable, you must then configure it as the parametrized data source.</span></span> <span data-ttu-id="87dde-480">További információ [A Számított mező típusának ER-adatforrásaihoz tartozó paraméteres hívások támogatása](er-calculated-field-type.md).</span><span class="sxs-lookup"><span data-stu-id="87dde-480">For more information, see [Support parameterized calls of ER data sources of the Calculated field type](er-calculated-field-type.md).</span></span>

1. <span data-ttu-id="87dde-481">A **Modell-leképezés tervező** oldal **Adatforrástípusok** paneljén válassza az **Általános\\Üres tároló** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-481">On the **Model mapping designer** page, in the **Data source types** pane, select **General\\Empty container**.</span></span>
2. <span data-ttu-id="87dde-482">Adja hozzá egy új tároló adatforrását:</span><span class="sxs-lookup"><span data-stu-id="87dde-482">Add a new container data source:</span></span>

    1. <span data-ttu-id="87dde-483">Az **Adatforrás** panelen válassza a **Gyökér hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="87dde-483">In the **Data sources** pane, select **Add root**.</span></span>
    2. <span data-ttu-id="87dde-484">A párbeszédpanel **Név** mezőjébe írja be a **Segítő** kifejezést.</span><span class="sxs-lookup"><span data-stu-id="87dde-484">In the dialog box, in the **Name** field, enter **Helper**.</span></span>
    3. <span data-ttu-id="87dde-485">Az új tároló adatforrás hozzáadásához kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="87dde-485">Select **OK** to add the new container data source.</span></span>

3. <span data-ttu-id="87dde-486">Az **Adatforrástípusok** panelen válassza a **Függvények\\Számított mező** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-486">In the **Data source types** pane, select **Functions\\Calculated field**.</span></span>
4. <span data-ttu-id="87dde-487">Adjon hozzá új adatforrást:</span><span class="sxs-lookup"><span data-stu-id="87dde-487">Add a new data source:</span></span>

    1. <span data-ttu-id="87dde-488">Válassza az **Adatforrások** ablaktábla **Segítő** elemét.</span><span class="sxs-lookup"><span data-stu-id="87dde-488">In the **Data sources** pane, select **Helper**.</span></span>
    2. <span data-ttu-id="87dde-489">Válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-489">Select **Add**.</span></span>
    3. <span data-ttu-id="87dde-490">A párbeszédpanel **Név** mezőjébe írja be a **NoYesEnumToString** kifejezést.</span><span class="sxs-lookup"><span data-stu-id="87dde-490">In the dialog box, in the **Name** field, enter **NoYesEnumToString**.</span></span>
    4. <span data-ttu-id="87dde-491">Válassza a **Képlet szerkesztése** elemet.</span><span class="sxs-lookup"><span data-stu-id="87dde-491">Select **Edit formula**.</span></span>
    5. <span data-ttu-id="87dde-492">A receptúraszerkesztőben válassza a **Paraméterek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-492">In the formula editor, select **Parameters**.</span></span>
    6. <span data-ttu-id="87dde-493">A konfigurált kifejezés paramétereinek megadásához kövesse az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="87dde-493">Follow these steps to specify parameters for the configured expression:</span></span>

        1. <span data-ttu-id="87dde-494">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-494">Select **New**.</span></span>
        2. <span data-ttu-id="87dde-495">A párbeszédpanel **Név** mezőjébe írja be az **Argumentum** kifejezést.</span><span class="sxs-lookup"><span data-stu-id="87dde-495">In the dialog box, in the **Name** field, enter **Argument**.</span></span>
        3. <span data-ttu-id="87dde-496">A **Típus** mezőben válassza ki a **Logikai** adattípust.</span><span class="sxs-lookup"><span data-stu-id="87dde-496">In the **Type** field, select the **Boolean** data type.</span></span>
        4. <span data-ttu-id="87dde-497">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-497">Select **OK**.</span></span>

    7. <span data-ttu-id="87dde-498">A **Receptúra** mezőbe írja be az **IF (Argument = true, \@"GER\_LABEL:PositiveAnswer", \@"GER\_LABEL:NegativeAnswer")** képletet a megfelelő ER-címke szövegének visszaadásához. Ez a végrehajtási környezet nyelvétől, illetve a megadott paraméter értékétől függ.</span><span class="sxs-lookup"><span data-stu-id="87dde-498">In the **Formula** field, enter **IF (Argument = true, \@"GER\_LABEL:PositiveAnswer", \@"GER\_LABEL:NegativeAnswer")** to return the text of the appropriate ER label, depending on the language of the execution context and value of the specified parameter.</span></span>
    8. <span data-ttu-id="87dde-499">Válassza a **Mentés** gombot, majd zárja be a receptúraszerkesztőt.</span><span class="sxs-lookup"><span data-stu-id="87dde-499">Select **Save**, and close the formula editor.</span></span>
    9. <span data-ttu-id="87dde-500">Az új adatforrás hozzáadásához kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="87dde-500">Select **OK** to add the new data source.</span></span>

![Konfigurált modell-leképezés az ER modell-leképezésének tervezőjében](./media/er-quick-start1-added-data-sources.png)

#### <a name="bind-data-sources-to-data-model-fields"></a><a name="AddMmBindings1"></a><span data-ttu-id="87dde-502">Adatforrások kötése az adatmodell mezőihez</span><span class="sxs-lookup"><span data-stu-id="87dde-502">Bind data sources to data model fields</span></span>

<span data-ttu-id="87dde-503">Ha meg szeretné adni, hogy az adatmodell hogyan legyen feltöltve az alkalmazás adataival, akkor az adatmodell mezőihez kell kötnie a konfigurált adatforrásokat.</span><span class="sxs-lookup"><span data-stu-id="87dde-503">You must bind the configured data sources to the fields of the data model to specify how the data model will by filled in with application data at runtime.</span></span>

1. <span data-ttu-id="87dde-504">A **Modell-leképezés tervező** oldal **Adatmodell** paneljén válassza a **CompanyName** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-504">On the **Model mapping designer** page, in the **Data model** pane, select **CompanyName**.</span></span>
2. <span data-ttu-id="87dde-505">Az **Adatforrások** panelen bontsa ki a **CompanyInfo** részt, majd kövesse az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="87dde-505">In the **Data sources** pane, expand **CompanyInfo**, and then follow these steps:</span></span>

    1. <span data-ttu-id="87dde-506">Bontsa ki a **CompanyInfo.find()** csomópontot, amely a CompanyInfo tábla **find()** metódusát jelzi.</span><span class="sxs-lookup"><span data-stu-id="87dde-506">Expand the **CompanyInfo.find()** node that represents the **find()** method of the CompanyInfo table.</span></span>
    2. <span data-ttu-id="87dde-507">Válassza ki a **CompanyInfo.find().Name** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-507">Select **CompanyInfo.find().Name**.</span></span>
    3. <span data-ttu-id="87dde-508">Annak a vállalatnak a nevének a kitöltéséhez, amelynek a környezetében meg szeretné hívni a konfigurált modell-leképezést a futásidőben, válassza a **Kötés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-508">Select **Bind** to fill in the name of the company that the configured model mapping is called in the context of at runtime.</span></span>

3. <span data-ttu-id="87dde-509">Az **Adatmodell** panelen válassza a **Kérdőív** elemet.</span><span class="sxs-lookup"><span data-stu-id="87dde-509">In the **Data model** pane, select **Questionnaire**.</span></span>
4. <span data-ttu-id="87dde-510">Az **Adatforrások** panelen válassza a **Kérdőív** lehetőséget, majd a kérdőív rekordjainak kitöltéséhez válassza a **Kötés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-510">In the **Data sources** pane, select **Questionnaire**, and then select **Bind** to fill in questionnaire records.</span></span>
5. <span data-ttu-id="87dde-511">Az **Adatmodell** panelen bontsa ki a **Kérdőív** részt, majd kövesse az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="87dde-511">In the **Data model** pane, expand **Questionnaire**, and then follow these steps:</span></span>

    1. <span data-ttu-id="87dde-512">Az **Adatmodell** panelen válassza az **Aktív** elemet.</span><span class="sxs-lookup"><span data-stu-id="87dde-512">In the **Data model** pane, select **Active**.</span></span>
    2. <span data-ttu-id="87dde-513">Az **Adatmodell** panelen válassza a **Szerkesztés** elemet.</span><span class="sxs-lookup"><span data-stu-id="87dde-513">In the **Data model** pane, select **Edit**.</span></span>
    3. <span data-ttu-id="87dde-514">A **Receptúra** mezőbe írja be a **Helper.NoYesEnumToString (\@.Active = EnumAppNoYes.Yes)** képletet a felsorolási értékek összehasonlításának szöveg- és nyelvfüggő eredményeinek kitöltéséhez.</span><span class="sxs-lookup"><span data-stu-id="87dde-514">In the **Formula** field, enter **Helper.NoYesEnumToString (\@.Active = EnumAppNoYes.Yes)** to fill the text-dependent and language-dependent result of the comparison between enumeration values.</span></span>

6. <span data-ttu-id="87dde-515">Az alábbi eredmény eléréséig folytassa az adatforrások adatmodell-mezőkhöz kötését ugyanezen a módon.</span><span class="sxs-lookup"><span data-stu-id="87dde-515">Continue to bind data sources to data model fields in the same manner until you achieve the following result.</span></span>

    | <span data-ttu-id="87dde-516">Mező elérési útja</span><span class="sxs-lookup"><span data-stu-id="87dde-516">Field path</span></span>                                              | <span data-ttu-id="87dde-517">Adattípus</span><span class="sxs-lookup"><span data-stu-id="87dde-517">Data type</span></span>   | <span data-ttu-id="87dde-518">Művelet</span><span class="sxs-lookup"><span data-stu-id="87dde-518">Action</span></span> | <span data-ttu-id="87dde-519">Kötési kifejezés</span><span class="sxs-lookup"><span data-stu-id="87dde-519">Binding expression</span></span> |
    |---------------------------------------------------------|-------------|--------|--------------------|
    | <span data-ttu-id="87dde-520">CompanyName</span><span class="sxs-lookup"><span data-stu-id="87dde-520">CompanyName</span></span>                                             | <span data-ttu-id="87dde-521">Karakterlánc</span><span class="sxs-lookup"><span data-stu-id="87dde-521">String</span></span>      | <span data-ttu-id="87dde-522">Kötés</span><span class="sxs-lookup"><span data-stu-id="87dde-522">Bind</span></span>   | <span data-ttu-id="87dde-523">CompanyInfo.'find()'.Name</span><span class="sxs-lookup"><span data-stu-id="87dde-523">CompanyInfo.'find()'.Name</span></span> |
    | <span data-ttu-id="87dde-524">Kérdőív</span><span class="sxs-lookup"><span data-stu-id="87dde-524">Questionnaire</span></span>                                           | <span data-ttu-id="87dde-525">Rekordlista</span><span class="sxs-lookup"><span data-stu-id="87dde-525">Record list</span></span> | <span data-ttu-id="87dde-526">Kötés</span><span class="sxs-lookup"><span data-stu-id="87dde-526">Bind</span></span>   | <span data-ttu-id="87dde-527">Kérdőív</span><span class="sxs-lookup"><span data-stu-id="87dde-527">Questionnaire</span></span> |
    | <span data-ttu-id="87dde-528">Questionnaire\\Active</span><span class="sxs-lookup"><span data-stu-id="87dde-528">Questionnaire\\Active</span></span>                                   | <span data-ttu-id="87dde-529">Karakterlánc</span><span class="sxs-lookup"><span data-stu-id="87dde-529">String</span></span>      | <span data-ttu-id="87dde-530">Szerkesztés</span><span class="sxs-lookup"><span data-stu-id="87dde-530">Edit</span></span>   | <span data-ttu-id="87dde-531">Helper.NoYesEnumToString(\@.active = EnumAppNoYes.Yes)</span><span class="sxs-lookup"><span data-stu-id="87dde-531">Helper.NoYesEnumToString(\@.active = EnumAppNoYes.Yes)</span></span> |
    | <span data-ttu-id="87dde-532">Questionnaire\\Code</span><span class="sxs-lookup"><span data-stu-id="87dde-532">Questionnaire\\Code</span></span>                                     | <span data-ttu-id="87dde-533">Karakterlánc</span><span class="sxs-lookup"><span data-stu-id="87dde-533">String</span></span>      | <span data-ttu-id="87dde-534">Kötés</span><span class="sxs-lookup"><span data-stu-id="87dde-534">Bind</span></span>   | <span data-ttu-id="87dde-535">\@.kmCollectionId</span><span class="sxs-lookup"><span data-stu-id="87dde-535">\@.kmCollectionId</span></span> |
    | <span data-ttu-id="87dde-536">Questionnaire\\Description</span><span class="sxs-lookup"><span data-stu-id="87dde-536">Questionnaire\\Description</span></span>                              | <span data-ttu-id="87dde-537">Karakterlánc</span><span class="sxs-lookup"><span data-stu-id="87dde-537">String</span></span>      | <span data-ttu-id="87dde-538">Kötés</span><span class="sxs-lookup"><span data-stu-id="87dde-538">Bind</span></span>   | <span data-ttu-id="87dde-539">\@.Description</span><span class="sxs-lookup"><span data-stu-id="87dde-539">\@.Description</span></span> |
    | <span data-ttu-id="87dde-540">Questionnaire\\QuestionnaireType</span><span class="sxs-lookup"><span data-stu-id="87dde-540">Questionnaire\\QuestionnaireType</span></span>                        | <span data-ttu-id="87dde-541">Karakterlánc</span><span class="sxs-lookup"><span data-stu-id="87dde-541">String</span></span>      | <span data-ttu-id="87dde-542">Kötés</span><span class="sxs-lookup"><span data-stu-id="87dde-542">Bind</span></span>   | <span data-ttu-id="87dde-543">\@.'&gt;Relations'.kmCollectionTypeId.Description</span><span class="sxs-lookup"><span data-stu-id="87dde-543">\@.'&gt;Relations'.kmCollectionTypeId.Description</span></span> |
    | <span data-ttu-id="87dde-544">Questionnaire\\QuestionOrder</span><span class="sxs-lookup"><span data-stu-id="87dde-544">Questionnaire\\QuestionOrder</span></span>                            | <span data-ttu-id="87dde-545">Karakterlánc</span><span class="sxs-lookup"><span data-stu-id="87dde-545">String</span></span>      | <span data-ttu-id="87dde-546">Szerkesztés</span><span class="sxs-lookup"><span data-stu-id="87dde-546">Edit</span></span>   | <span data-ttu-id="87dde-547">CASE (\@.questionMode,</span><span class="sxs-lookup"><span data-stu-id="87dde-547">CASE (\@.questionMode,</span></span><br><span data-ttu-id="87dde-548">EnumAppQuestionOrder.Conditional, "Feltételes",</span><span class="sxs-lookup"><span data-stu-id="87dde-548">EnumAppQuestionOrder.Conditional, "Conditional",</span></span><br><span data-ttu-id="87dde-549">EnumAppQuestionOrder.Random, "Véletlenszerű (százalékos arány a kérdőívben)",</span><span class="sxs-lookup"><span data-stu-id="87dde-549">EnumAppQuestionOrder.Random, "Random (percentage in questionnaire)",</span></span><br><span data-ttu-id="87dde-550">EnumAppQuestionOrder.RandomGroup, "Véletlenszerű (százalékos arány az eredménycsoportokban)",</span><span class="sxs-lookup"><span data-stu-id="87dde-550">EnumAppQuestionOrder.RandomGroup, "Random (percentage in result groups)",</span></span><br><span data-ttu-id="87dde-551">EnumAppQuestionOrder.Sequence, "Egymás utáni",</span><span class="sxs-lookup"><span data-stu-id="87dde-551">EnumAppQuestionOrder.Sequence, "Sequential",</span></span><br><span data-ttu-id="87dde-552">"")</span><span class="sxs-lookup"><span data-stu-id="87dde-552">"")</span></span> |
    | <span data-ttu-id="87dde-553">Questionnaire\\ResultsGroup</span><span class="sxs-lookup"><span data-stu-id="87dde-553">Questionnaire\\ResultsGroup</span></span>                             | <span data-ttu-id="87dde-554">Rögzítés</span><span class="sxs-lookup"><span data-stu-id="87dde-554">Record</span></span>      |        | |
    | <span data-ttu-id="87dde-555">Questionnaire\\ResultsGroup\\Code</span><span class="sxs-lookup"><span data-stu-id="87dde-555">Questionnaire\\ResultsGroup\\Code</span></span>                       | <span data-ttu-id="87dde-556">Karakterlánc</span><span class="sxs-lookup"><span data-stu-id="87dde-556">String</span></span>      | <span data-ttu-id="87dde-557">Kötés</span><span class="sxs-lookup"><span data-stu-id="87dde-557">Bind</span></span>   | <span data-ttu-id="87dde-558">\@.'\$ResultGroup'.kmQuestionResultGroupId</span><span class="sxs-lookup"><span data-stu-id="87dde-558">\@.'\$ResultGroup'.kmQuestionResultGroupId</span></span> |
    | <span data-ttu-id="87dde-559">Questionnaire\\ResultsGroup\\Description</span><span class="sxs-lookup"><span data-stu-id="87dde-559">Questionnaire\\ResultsGroup\\Description</span></span>                | <span data-ttu-id="87dde-560">Karakterlánc</span><span class="sxs-lookup"><span data-stu-id="87dde-560">String</span></span>      | <span data-ttu-id="87dde-561">Kötés</span><span class="sxs-lookup"><span data-stu-id="87dde-561">Bind</span></span>   | <span data-ttu-id="87dde-562">\@.'\$ResultGroup'.description</span><span class="sxs-lookup"><span data-stu-id="87dde-562">\@.'\$ResultGroup'.description</span></span> |
    | <span data-ttu-id="87dde-563">Questionnaire\\ResultsGroup\\MaxNumberOfPoints</span><span class="sxs-lookup"><span data-stu-id="87dde-563">Questionnaire\\ResultsGroup\\MaxNumberOfPoints</span></span>          | <span data-ttu-id="87dde-564">Valós</span><span class="sxs-lookup"><span data-stu-id="87dde-564">Real</span></span>        | <span data-ttu-id="87dde-565">Kötés</span><span class="sxs-lookup"><span data-stu-id="87dde-565">Bind</span></span>   | <span data-ttu-id="87dde-566">\@.'\$ResultGroup'.maxPoint</span><span class="sxs-lookup"><span data-stu-id="87dde-566">\@.'\$ResultGroup'.maxPoint</span></span> |
    | <span data-ttu-id="87dde-567">Questionnaire\\Question</span><span class="sxs-lookup"><span data-stu-id="87dde-567">Questionnaire\\Question</span></span>                                 | <span data-ttu-id="87dde-568">Rekordlista</span><span class="sxs-lookup"><span data-stu-id="87dde-568">Record list</span></span> | <span data-ttu-id="87dde-569">Kötés</span><span class="sxs-lookup"><span data-stu-id="87dde-569">Bind</span></span>   | <span data-ttu-id="87dde-570">\@.'&lt;Relations'.KMCollectionQuestion</span><span class="sxs-lookup"><span data-stu-id="87dde-570">\@.'&lt;Relations'.KMCollectionQuestion</span></span> |
    | <span data-ttu-id="87dde-571">Questionnaire\\Question\\CollectionSequenceNumber</span><span class="sxs-lookup"><span data-stu-id="87dde-571">Questionnaire\\Question\\CollectionSequenceNumber</span></span>       | <span data-ttu-id="87dde-572">Egész</span><span class="sxs-lookup"><span data-stu-id="87dde-572">Integer</span></span>     | <span data-ttu-id="87dde-573">Kötés</span><span class="sxs-lookup"><span data-stu-id="87dde-573">Bind</span></span>   | <span data-ttu-id="87dde-574">\@.answerCollectionSequenceNumber</span><span class="sxs-lookup"><span data-stu-id="87dde-574">\@.answerCollectionSequenceNumber</span></span> |
    | <span data-ttu-id="87dde-575">Questionnaire\\Question\\Id</span><span class="sxs-lookup"><span data-stu-id="87dde-575">Questionnaire\\Question\\Id</span></span>                             | <span data-ttu-id="87dde-576">Karakterlánc</span><span class="sxs-lookup"><span data-stu-id="87dde-576">String</span></span>      | <span data-ttu-id="87dde-577">Kötés</span><span class="sxs-lookup"><span data-stu-id="87dde-577">Bind</span></span>   | <span data-ttu-id="87dde-578">\@.kmQuestionId</span><span class="sxs-lookup"><span data-stu-id="87dde-578">\@.kmQuestionId</span></span> |
    | <span data-ttu-id="87dde-579">Questionnaire\\Question\\MustBeCompleted</span><span class="sxs-lookup"><span data-stu-id="87dde-579">Questionnaire\\Question\\MustBeCompleted</span></span>                | <span data-ttu-id="87dde-580">Karakterlánc</span><span class="sxs-lookup"><span data-stu-id="87dde-580">String</span></span>      | <span data-ttu-id="87dde-581">Szerkesztés</span><span class="sxs-lookup"><span data-stu-id="87dde-581">Edit</span></span>   | <span data-ttu-id="87dde-582">Helper.NoYesEnumToString(\@.mandatory = EnumAppNoYes.Yes)</span><span class="sxs-lookup"><span data-stu-id="87dde-582">Helper.NoYesEnumToString(\@.mandatory = EnumAppNoYes.Yes)</span></span> |
    | <span data-ttu-id="87dde-583">Questionnaire\\Question\\PrimaryQuestion</span><span class="sxs-lookup"><span data-stu-id="87dde-583">Questionnaire\\Question\\PrimaryQuestion</span></span>                | <span data-ttu-id="87dde-584">Karakterlánc</span><span class="sxs-lookup"><span data-stu-id="87dde-584">String</span></span>      | <span data-ttu-id="87dde-585">Kötés</span><span class="sxs-lookup"><span data-stu-id="87dde-585">Bind</span></span>   | <span data-ttu-id="87dde-586">\@.parentQuestionId</span><span class="sxs-lookup"><span data-stu-id="87dde-586">\@.parentQuestionId</span></span> |
    | <span data-ttu-id="87dde-587">Questionnaire\\Question\\SequenceNumber</span><span class="sxs-lookup"><span data-stu-id="87dde-587">Questionnaire\\Question\\SequenceNumber</span></span>                 | <span data-ttu-id="87dde-588">Egész</span><span class="sxs-lookup"><span data-stu-id="87dde-588">Integer</span></span>     | <span data-ttu-id="87dde-589">Kötés</span><span class="sxs-lookup"><span data-stu-id="87dde-589">Bind</span></span>   | <span data-ttu-id="87dde-590">\@.SequenceNumber</span><span class="sxs-lookup"><span data-stu-id="87dde-590">\@.SequenceNumber</span></span> |
    | <span data-ttu-id="87dde-591">Questionnaire\\Question\\Text</span><span class="sxs-lookup"><span data-stu-id="87dde-591">Questionnaire\\Question\\Text</span></span>                           | <span data-ttu-id="87dde-592">Karakterlánc</span><span class="sxs-lookup"><span data-stu-id="87dde-592">String</span></span>      | <span data-ttu-id="87dde-593">Kötés</span><span class="sxs-lookup"><span data-stu-id="87dde-593">Bind</span></span>   | <span data-ttu-id="87dde-594">\@.'\$Question'.text</span><span class="sxs-lookup"><span data-stu-id="87dde-594">\@.'\$Question'.text</span></span> |
    | <span data-ttu-id="87dde-595">Questionnaire\\Question\\Answer</span><span class="sxs-lookup"><span data-stu-id="87dde-595">Questionnaire\\Question\\Answer</span></span>                         | <span data-ttu-id="87dde-596">Rekordlista</span><span class="sxs-lookup"><span data-stu-id="87dde-596">Record list</span></span> | <span data-ttu-id="87dde-597">Kötés</span><span class="sxs-lookup"><span data-stu-id="87dde-597">Bind</span></span>   | <span data-ttu-id="87dde-598">\@.'\$Question'.'\$Answer'</span><span class="sxs-lookup"><span data-stu-id="87dde-598">\@.'\$Question'.'\$Answer'</span></span> |
    | <span data-ttu-id="87dde-599">Questionnaire\\Question\\Answer\\CorrectAnswer</span><span class="sxs-lookup"><span data-stu-id="87dde-599">Questionnaire\\Question\\Answer\\CorrectAnswer</span></span>          | <span data-ttu-id="87dde-600">Karakterlánc</span><span class="sxs-lookup"><span data-stu-id="87dde-600">String</span></span>      | <span data-ttu-id="87dde-601">Szerkesztés</span><span class="sxs-lookup"><span data-stu-id="87dde-601">Edit</span></span>   | <span data-ttu-id="87dde-602">Helper.NoYesEnumToString(\@.correctAnswer = EnumAppNoYes.Yes)</span><span class="sxs-lookup"><span data-stu-id="87dde-602">Helper.NoYesEnumToString(\@.correctAnswer = EnumAppNoYes.Yes)</span></span> |
    | <span data-ttu-id="87dde-603">Questionnaire\\Question\\Answer\\Points</span><span class="sxs-lookup"><span data-stu-id="87dde-603">Questionnaire\\Question\\Answer\\Points</span></span>                 | <span data-ttu-id="87dde-604">Valós</span><span class="sxs-lookup"><span data-stu-id="87dde-604">Real</span></span>        | <span data-ttu-id="87dde-605">Kötés</span><span class="sxs-lookup"><span data-stu-id="87dde-605">Bind</span></span>   | <span data-ttu-id="87dde-606">\@.point</span><span class="sxs-lookup"><span data-stu-id="87dde-606">\@.point</span></span> |
    | <span data-ttu-id="87dde-607">Questionnaire\\Question\\Answer\\SequenceNumber</span><span class="sxs-lookup"><span data-stu-id="87dde-607">Questionnaire\\Question\\Answer\\SequenceNumber</span></span>         | <span data-ttu-id="87dde-608">Egész</span><span class="sxs-lookup"><span data-stu-id="87dde-608">Integer</span></span>     | <span data-ttu-id="87dde-609">Kötés</span><span class="sxs-lookup"><span data-stu-id="87dde-609">Bind</span></span>   | <span data-ttu-id="87dde-610">\@.sequenceNumber</span><span class="sxs-lookup"><span data-stu-id="87dde-610">\@.sequenceNumber</span></span> |
    | <span data-ttu-id="87dde-611">Questionnaire\\Question\\Answer\\Text</span><span class="sxs-lookup"><span data-stu-id="87dde-611">Questionnaire\\Question\\Answer\\Text</span></span>                   | <span data-ttu-id="87dde-612">Karakterlánc</span><span class="sxs-lookup"><span data-stu-id="87dde-612">String</span></span>      | <span data-ttu-id="87dde-613">Kötés</span><span class="sxs-lookup"><span data-stu-id="87dde-613">Bind</span></span>   | <span data-ttu-id="87dde-614">\@.text</span><span class="sxs-lookup"><span data-stu-id="87dde-614">\@.text</span></span> |

    <span data-ttu-id="87dde-615">A következő ábra a **Modell-leképezés tervező** oldal konfigurált modell-leképezésének végleges állapotát mutatja.</span><span class="sxs-lookup"><span data-stu-id="87dde-615">The following illustration shows the final state of the configured model mapping on the **Model mapping designer** page.</span></span>

    ![Teljesen konfigurált modell-leképezés az ER modell-leképezésének tervezőjében](./media/er-quick-start1-mapping2.png)

7. <span data-ttu-id="87dde-617">Mentse el a módosításokat.</span><span class="sxs-lookup"><span data-stu-id="87dde-617">Save your changes.</span></span>
8. <span data-ttu-id="87dde-618">Zárja be a **Modell-hozzárendelési tervező** lapot.</span><span class="sxs-lookup"><span data-stu-id="87dde-618">Close the **Model mapping designer** page.</span></span>

#### <a name="complete-the-design-of-the-model-mapping"></a><a name="CompleteModelMapping"></a><span data-ttu-id="87dde-619">A modell-leképezés kialakításának befejezése</span><span class="sxs-lookup"><span data-stu-id="87dde-619">Complete the design of the model mapping</span></span>

1. <span data-ttu-id="87dde-620">Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.</span><span class="sxs-lookup"><span data-stu-id="87dde-620">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="87dde-621">A **Konfigurációk** oldalon, a konfigurációk fastruktúrájában válassza a **Kérdőív leképezése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-621">On the **Configurations** page, in the configuration tree, select **Questionnaire mapping**.</span></span>
3. <span data-ttu-id="87dde-622">A **Verziók** gyorslapon válassza ki azt a konfigurációverziót, amelynek az állapota **Piszkozat**.</span><span class="sxs-lookup"><span data-stu-id="87dde-622">On the **Versions** FastTab, select the configuration version that has a status of **Draft**.</span></span>
4. <span data-ttu-id="87dde-623">Válassza az **Állapot módosítása** \> **Teljes** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-623">Select **Change status** \> **Complete**.</span></span>

<span data-ttu-id="87dde-624">A konfiguráció 1.1. verziójának állapota **Piszkozatról** **Befejezett** értékre módosul.</span><span class="sxs-lookup"><span data-stu-id="87dde-624">The status of version 1.1 of this configuration is changed from **Draft** to **Completed**.</span></span> <span data-ttu-id="87dde-625">Az 1.1. verzió a későbbiekben már nem módosítható.</span><span class="sxs-lookup"><span data-stu-id="87dde-625">Version 1.1 can no longer be changed.</span></span> <span data-ttu-id="87dde-626">Ez a verzió tartalmazza a konfigurált modell-leképezést, és a többi ER-konfiguráció alapjaként használható.</span><span class="sxs-lookup"><span data-stu-id="87dde-626">This version contains the configured model mapping and can be used as the basis for other ER configurations.</span></span> <span data-ttu-id="87dde-627">A konfiguráció 1.2. változata létrejön **Piszkozat** állapottal.</span><span class="sxs-lookup"><span data-stu-id="87dde-627">Version 1.2 of this configuration is created and has a status of **Draft**.</span></span> <span data-ttu-id="87dde-628">Ezt a verziót a **Kérdőív leképezése** konfiguráció módosításával szerkesztheti.</span><span class="sxs-lookup"><span data-stu-id="87dde-628">You can edit this version to adjust the **Questionnaire mapping** configuration.</span></span>

![A szerkeszthető ER-konfiguráció verziói a Konfigurációk oldalon](./media/er-quick-start1-mapping-configuration.png)

> [!NOTE]
> <span data-ttu-id="87dde-630">A konfigurált modell-leképezés a **Kérdőív** üzleti területet képviselő absztrakt adatmodell Finance-specifikus megvalósítása.</span><span class="sxs-lookup"><span data-stu-id="87dde-630">The configured model mapping is your Finance-specific implementation of the abstract data model that represents the **Questionnaire** business domain.</span></span>

## <a name="design-a-template-for-a-custom-report"></a><a name="DesignReportTemplate"></a><span data-ttu-id="87dde-631">Sablon tervezése egyéni jelentésekhez</span><span class="sxs-lookup"><span data-stu-id="87dde-631">Design a template for a custom report</span></span>

<span data-ttu-id="87dde-632">Az ER keretrendszer előre definiált sablonok használatával készít jelentéseket Microsoft Office-formátumban (Excel-munkafüzetek vagy Word-dokumentumok).</span><span class="sxs-lookup"><span data-stu-id="87dde-632">The ER framework uses predefined templates to generate reports in Microsoft Office formats (Excel workbooks or Word documents).</span></span> <span data-ttu-id="87dde-633">A szükséges jelentés létrehozása során a program a konfigurált adatfolyamnak megfelelően kitölti a szükséges adatokkal a sablont.</span><span class="sxs-lookup"><span data-stu-id="87dde-633">While the required report is being generated, a template is filled in with required data according to the configured dataflow.</span></span> <span data-ttu-id="87dde-634">Ennek megfelelően először egy sablont kell terveznie a saját egyéni jelentéséhez.</span><span class="sxs-lookup"><span data-stu-id="87dde-634">Therefore, you must first design a template for your custom report.</span></span> <span data-ttu-id="87dde-635">Ezt a sablont Excel-munkafüzetként kell megtervezni; a szerkezet képezi le az egyéni jelentés elrendezését.</span><span class="sxs-lookup"><span data-stu-id="87dde-635">This template must be designed as an Excel workbook, the structure of which represents the layout of a custom report.</span></span> <span data-ttu-id="87dde-636">Minden olyan Excel-tételt meg kell neveznie, amelyet fel szeretne tölteni a szükséges adatokkal.</span><span class="sxs-lookup"><span data-stu-id="87dde-636">You must name every Excel item that you plan to fill in with required data.</span></span>

1. <span data-ttu-id="87dde-637">Töltse le a [Questionnaires report template.xslx](https://go.microsoft.com/fwlink/?linkid=851448) fájlt, és mentse a helyi számítógépen.</span><span class="sxs-lookup"><span data-stu-id="87dde-637">Download the [Questionnaires report template.xslx](https://go.microsoft.com/fwlink/?linkid=851448) file, and save it to your local computer.</span></span>
2. <span data-ttu-id="87dde-638">Nyissa meg a fájlt az Excel programban, és tekintse át a munkafüzet struktúráját.</span><span class="sxs-lookup"><span data-stu-id="87dde-638">Open the file in Excel, and review the structure of the workbook.</span></span>

<span data-ttu-id="87dde-639">Ahogy a következő ábrán látható, a letöltött sablon úgy lett kialakítva, hogy olyan konkrét kérdőíveket lehessen vele kinyomtatni, amelyek tartalmazzák a kérdőív kérdéseit és a megfelelő válaszokat.</span><span class="sxs-lookup"><span data-stu-id="87dde-639">As the following illustration shows, the downloaded template has been designed to print specified questionnaires that present a questionnaire's questions together with appropriate answers.</span></span>

![Excel-sablon a megadott kérdőívek nyomtatásához](./media/er-quick-start1-template-layout.png)

<span data-ttu-id="87dde-641">A sablonhoz Excel-neveket adtunk a kérdőív részleteinek kitöltéséhez.</span><span class="sxs-lookup"><span data-stu-id="87dde-641">Excel names have been added to this template to fill in the questionnaire details.</span></span> <span data-ttu-id="87dde-642">Az Excel-neveket a Névkezelővel ellenőrizheti.</span><span class="sxs-lookup"><span data-stu-id="87dde-642">You can use Name Manager to review the Excel names.</span></span>

![A megadott Excel-sablonban lévő Excel-nevek ellenőrzése a Névkezelővel](./media/er-quick-start1-template-names.png)

<span data-ttu-id="87dde-644">A jelentés címkéit angol nyelvű rögzített szövegként adtuk hozzá.</span><span class="sxs-lookup"><span data-stu-id="87dde-644">Report labels have been added as fixed text in the English language.</span></span> <span data-ttu-id="87dde-645">A jelentés címkéit olyan új Excel-nevekre cserélheti, amelyek az ER-formátum [címkéivel](#AddMmLabels) töltik ki nyelvtől függő szöveggel a címkéket (ahogy a konfigurált modell-leképezés nyelvtől függő kifejezései esetében is tette).</span><span class="sxs-lookup"><span data-stu-id="87dde-645">You can replace the report labels with new Excel names that fill in the labels with language-dependent text by using the ER format [labels](#AddMmLabels), as you did for language-dependent expressions in the configured model mapping.</span></span> <span data-ttu-id="87dde-646">Ebben az esetben az ER-címkéket szerkeszthető ER-formátumban kell megadni.</span><span class="sxs-lookup"><span data-stu-id="87dde-646">In this case, ER labels must be added in the editable ER format.</span></span>

<span data-ttu-id="87dde-647">A következő ábrán látható egyéni jelentés fejléce úgy lett megadva, hogy az Excel számára engedélyezze a lapozást.</span><span class="sxs-lookup"><span data-stu-id="87dde-647">As the following illustration shows, the custom report header has been specified to enable Excel to do paging.</span></span>

![Egyéni jelentés fejléce a megadott Excel-sablonban](./media/er-quick-start1-template-header.png)

## <a name="design-a-format"></a><a name="DesignFormat"></a><span data-ttu-id="87dde-649">Formátum tervezése</span><span class="sxs-lookup"><span data-stu-id="87dde-649">Design a format</span></span>

<span data-ttu-id="87dde-650">Elektronikus jelentéskészítési funkció tanácsadója szerepkörű felhasználóként Önnek kell olyan új ER-konfigurációt létrehoznia, amely tartalmaz [formátum](general-electronic-reporting.md#FormatComponentOutbound) összetevőt.</span><span class="sxs-lookup"><span data-stu-id="87dde-650">As a user in the Electronic Reporting Functional Consultant role, you must create a new ER configuration that contains a [format](general-electronic-reporting.md#FormatComponentOutbound) component.</span></span> <span data-ttu-id="87dde-651">A formátum összetevőt úgy kell konfigurálni, hogy megadhatja, hogy a program milyen módon töltse ki a futásidőben a jelentés sablonját a szükséges adatokkal.</span><span class="sxs-lookup"><span data-stu-id="87dde-651">You must configure the format component to specify how a report template will be filled in with required data at runtime.</span></span>

<span data-ttu-id="87dde-652">A [Megtervezett formátumkonfiguráció importálása](#FormatImport) szakasz lépéseivel importálhatja a szükséges formátumot a megadott XML-fájlból.</span><span class="sxs-lookup"><span data-stu-id="87dde-652">By completing the steps in the [Import a designed format configuration](#FormatImport) section, you can import the required format from the provided XML file.</span></span> <span data-ttu-id="87dde-653">Egy másik megoldás, hogy az [Új formátumkonfiguráció létrehozása](#FormatCreate) szakasz lépéseit követve az alapoktól kezdve tervezi meg a formátumot.</span><span class="sxs-lookup"><span data-stu-id="87dde-653">Alternatively, you can complete the steps in the [Create a new format configuration](#FormatCreate) section to design this format from scratch.</span></span>

### <a name="import-a-designed-format-configuration"></a><a name="FormatImport"></a><span data-ttu-id="87dde-654">Megtervezett formátumkonfiguráció importálása</span><span class="sxs-lookup"><span data-stu-id="87dde-654">Import a designed format configuration</span></span>

1. <span data-ttu-id="87dde-655">Töltse le a [Questionnaires format.version.1.1.xml](https://go.microsoft.com/fwlink/?linkid=851448) fájlt, és mentse a helyi számítógépen.</span><span class="sxs-lookup"><span data-stu-id="87dde-655">Download the [Questionnaires format.version.1.1.xml](https://go.microsoft.com/fwlink/?linkid=851448) file, and save it to your local computer.</span></span>
2. <span data-ttu-id="87dde-656">Ugorjon a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.</span><span class="sxs-lookup"><span data-stu-id="87dde-656">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
3. <span data-ttu-id="87dde-657">Az **Elektronikus jelentéskészítés** munkaterületen válassza ki a **Jelentéskészítési konfiguráció** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-657">In the **Electronic reporting** workspace, select **Reporting configurations**.</span></span>
4. <span data-ttu-id="87dde-658">A Művelet ablaktáblában válassza az **Átváltás** \> **Betöltés XML-fájlból** elemet.</span><span class="sxs-lookup"><span data-stu-id="87dde-658">On the Action pane, Select **Exchange** \> **Load from XML file**.</span></span>
5. <span data-ttu-id="87dde-659">Kattintson a **Tallózás** elemre, majd keresse meg és válassza ki a **Questionnaires format.version.1.1.xml** fájlt.</span><span class="sxs-lookup"><span data-stu-id="87dde-659">Select **Browse**, and then find and select the **Questionnaires format.version.1.1.xml** file.</span></span>
6. <span data-ttu-id="87dde-660">A konfiguráció importálásához kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="87dde-660">Select **OK** to import the configuration.</span></span>

<span data-ttu-id="87dde-661">A folytatáshoz ugorja át a következő eljárást: [Új formátumkonfiguráció létrehozása](#FormatCreate).</span><span class="sxs-lookup"><span data-stu-id="87dde-661">To continue, skip the next procedure, [Create a new format configuration](#FormatCreate).</span></span>

### <a name="create-a-new-format-configuration"></a><a name="FormatCreate"></a><span data-ttu-id="87dde-662">Új formátumkonfiguráció létrehozása</span><span class="sxs-lookup"><span data-stu-id="87dde-662">Create a new format configuration</span></span>
 
1. <span data-ttu-id="87dde-663">Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.</span><span class="sxs-lookup"><span data-stu-id="87dde-663">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="87dde-664">A **Konfigurációk** oldalon, a konfigurációk fastruktúrájában válassza a **Kérdőív modellje** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-664">On the **Configurations** page, in the configuration tree, select **Questionnaire model**.</span></span>
3. <span data-ttu-id="87dde-665">Válassza a **Konfiguráció létrehozása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-665">Select **Create configuration**.</span></span>
4. <span data-ttu-id="87dde-666">A legördülő párbeszédpanelen hajtsa végre a következő lépéseket:</span><span class="sxs-lookup"><span data-stu-id="87dde-666">In the drop-down dialog box, follow these steps:</span></span>

    1. <span data-ttu-id="87dde-667">Az **Új** mezőben válassza az **Adatmodell kérdőívein alapuló formátum** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-667">In the **New** field, select **Format based on data model Questionnaires**.</span></span>
    2. <span data-ttu-id="87dde-668">A **Név** mezőbe írja be a **Jelentés a kérdőívről** szöveget.</span><span class="sxs-lookup"><span data-stu-id="87dde-668">In the **Name** field, enter **Questionnaire report**.</span></span>
    3. <span data-ttu-id="87dde-669">Az **Adatmodell-verzió** mezőben válassza az **1** értéket.</span><span class="sxs-lookup"><span data-stu-id="87dde-669">In the **Data model version** field, select **1**.</span></span>

        > [!NOTE]
        > - <span data-ttu-id="87dde-670">Ha kiválasztja az alap adatmodell egy adott verzióját, akkor az adatmodell megfelelő verziójának struktúrája jelenik meg mint a létrehozott formátumú **Modell** adatforrás szerkezete.</span><span class="sxs-lookup"><span data-stu-id="87dde-670">If you select a specific version of the base data model, the structure of the corresponding version of the data model will be presented to you as the structure of the **Model** data source in the format that is created.</span></span>
        > - <span data-ttu-id="87dde-671">Ez a mező üresen maradhat.</span><span class="sxs-lookup"><span data-stu-id="87dde-671">You can leave this field blank.</span></span> <span data-ttu-id="87dde-672">Ebben az esetben az adatmodell **Piszkozat** verziójának a szerkezete jelenik meg mint a létrehozott formátumú **Modell** adatforrás szerkezete.</span><span class="sxs-lookup"><span data-stu-id="87dde-672">In that case, the structure of the **Draft** version of the data model will be presented to you as the structure of the **Model** data source in the format that is created.</span></span> <span data-ttu-id="87dde-673">Ezután a modell módosítható, és a módosítások azonnal megtekinthetők az Ön által használt formátumban.</span><span class="sxs-lookup"><span data-stu-id="87dde-673">You can then adjust your model and immediately see those adjustments in your format.</span></span> <span data-ttu-id="87dde-674">Ez a módszer hatékonyabbá teheti az ER-megoldás kialakítását, amikor az adatmodell, a modell-leképezés és a formátum konfigurálása egyidejűleg történik.</span><span class="sxs-lookup"><span data-stu-id="87dde-674">This approach might improve the efficiency of ER solution design when you configure your data model, model mapping, and format simultaneously.</span></span>
        > - <span data-ttu-id="87dde-675">Ha az alap adatmodelljéből egy adott verziót választja ki, akkor később, amikor szerkeszteni kezd egy formátumot, válthat a **Piszkozat** verzió használatára.</span><span class="sxs-lookup"><span data-stu-id="87dde-675">If you select a specific version of the base data model, you can switch to using the **Draft** version later, when you start to edit a format.</span></span>

    4. <span data-ttu-id="87dde-676">Az **Adatmodell definíciója** mezőben válassza ki a **Gyökér** definíciót.</span><span class="sxs-lookup"><span data-stu-id="87dde-676">In the **Data model definition** field, select the **Root** definition.</span></span>

5. <span data-ttu-id="87dde-677">A konfiguráció létrehozása válassza a **Konfiguráció létrehozása** elemet.</span><span class="sxs-lookup"><span data-stu-id="87dde-677">Select **Create configuration** to create the configuration.</span></span>

#### <a name="import-a-report-template"></a><a name="ImportReportTemplate"></a><span data-ttu-id="87dde-678">Jelentéssablon importálása</span><span class="sxs-lookup"><span data-stu-id="87dde-678">Import a report template</span></span>

1. <span data-ttu-id="87dde-679">A **Konfigurációk** oldalon, a konfigurációk fastruktúrájában válassza a **Jelentés a kérdőívről** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-679">On the **Configurations** page, in the configuration tree, select **Questionnaire report**.</span></span>
2. <span data-ttu-id="87dde-680">Egy egyéni formátum konfigurálásához válassza ki a **Tervező** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-680">Select **Designer** to start to configure a custom format.</span></span>
3. <span data-ttu-id="87dde-681">A **Formátumtervező** oldal Művelet Paneljén válassza az **Importálás** \> **Importálás a Microsoft Excel programból** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-681">On the **Format designer** page, on the Action Pane, select **Import** \> **Import from Excel**.</span></span>
4. <span data-ttu-id="87dde-682">A párbeszédpanelen hajtsa végre a következő lépéseket:</span><span class="sxs-lookup"><span data-stu-id="87dde-682">In the dialog box, follow these steps:</span></span>

    1. <span data-ttu-id="87dde-683">Válassza a **Sablon hozzáadása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-683">Select **Add template**.</span></span>
    2. <span data-ttu-id="87dde-684">Keresse meg és válassza ki a helyileg mentett **Questionnaires report template.xslx** fájlt, és válassza a **Megnyitás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-684">Find and select the locally saved **Questionnaires report template.xslx** file, and then select **Open**.</span></span>
    3. <span data-ttu-id="87dde-685">A sablon importálásához kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="87dde-685">Select **OK** to import the template.</span></span>

    ![Jelentéssablon importálása](./media/er-quick-start1-template-import.png)

<span data-ttu-id="87dde-687">Az **Excel\\File** formátumelemet a rendszer automatikusan hozzáadja gyökérelemként a szerkeszthető formátumhoz.</span><span class="sxs-lookup"><span data-stu-id="87dde-687">The **Excel\\File** format element is automatically added to the editable format as a root element.</span></span> <span data-ttu-id="87dde-688">Ezenkívül vagy az **Excel\\Range**, vagy a **Excel\\Cell** formátumelemet automatikusan hozzáadja az importált sablon valamennyi felismert Excel-nevéhez.</span><span class="sxs-lookup"><span data-stu-id="87dde-688">Additionally, either the **Excel\\Range** format element or the **Excel\\Cell** format element is automatically added for every recognized Excel name of the imported template.</span></span> <span data-ttu-id="87dde-689">A **Sztring** elembe beágyazott **Excel\\Header** formátumot a rendszer automatikusan hozzáadja, hogy lehessen látni az importált sablon fejlécbeállításait.</span><span class="sxs-lookup"><span data-stu-id="87dde-689">The **Excel\\Header** format that has the nested **String** element is automatically added to reflect the header settings of the imported template.</span></span>

![Formátumstruktúra, amely tartalmazza az automatikusan hozzáadott elemeket az ER-művelet tervezőjében](./media/er-quick-start1-template-import2.png)

#### <a name="configure-a-format"></a><a name="ConfigureFormat"></a><span data-ttu-id="87dde-691">Formátum konfigurálása</span><span class="sxs-lookup"><span data-stu-id="87dde-691">Configure a format</span></span>

1. <span data-ttu-id="87dde-692">A **Formátumtervező** oldal formátumfájában válassza ki az **Excel** gyökérelemet.</span><span class="sxs-lookup"><span data-stu-id="87dde-692">On the **Format designer** page, in the format tree, select the **Excel** root element.</span></span>
2. <span data-ttu-id="87dde-693">Az oldal jobb oldalán lévő **Formátum** lap **Név** mezőjébe írja be a <a name="AddFormatRootElement"></a>**Jelentés** kifejezést.</span><span class="sxs-lookup"><span data-stu-id="87dde-693">On the **Format** tab on the right side of the page, in the **Name** field, enter <a name="AddFormatRootElement"></a>**Report**.</span></span>
3. <span data-ttu-id="87dde-694">A **Nyelvi preferencia** mezőben válassza ki a **Felhasználói preferencia** lehetőséget a jelentés felhasználó által preferált nyelven történő futtatásához.</span><span class="sxs-lookup"><span data-stu-id="87dde-694">In the **Language preference** field, select **User preference** to run the report in the user's preferred language.</span></span>
4. <span data-ttu-id="87dde-695">A **Kulturális preferencia** mezőben válassza ki a **Felhasználói preferencia** lehetőséget a jelentés felhasználó által preferált kultúra használatával történő futtatásához.</span><span class="sxs-lookup"><span data-stu-id="87dde-695">In the **Culture preference** field, select **User preference** to run the report in the user's preferred culture.</span></span>

    <span data-ttu-id="87dde-696">További információ a nyelvi és kulturális környezet ER-folyamathoz történő megadásáról: [Többnyelvű jelentések tervezése](er-design-multilingual-reports.md).</span><span class="sxs-lookup"><span data-stu-id="87dde-696">For information about how to specify the language and culture contexts for an ER process, see [Design multilingual reports](er-design-multilingual-reports.md).</span></span>

    ![A tervezett jelentés nyelvi és kulturális beállításainak konfigurálása az ER-művelettervezőben](./media/er-quick-start1-template-format-structure1.png)

5. <span data-ttu-id="87dde-698">A formátumfában bontsa ki a gyökércsomópontot, majd válassza ki a **ResultsGroup** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-698">In the format tree, expand the root node, and then select **ResultsGroup**.</span></span>
6. <span data-ttu-id="87dde-699">A **Formátum** lap **Replikációs irány** mezőjében válassza a **Nem replikál** lehetőséget, mert egy kérdőív esetében nem várható több eredménycsoport.</span><span class="sxs-lookup"><span data-stu-id="87dde-699">On the **Format** tab, in the **Replication direction** field, select **No replication**, because you don't expect to have multiple result groups for a single questionnaire.</span></span>

    ![A replikálási irány meghatározása a Tartomány formátumelemhez az ER-művelettervezőben](./media/er-quick-start1-template-format-structure2.png)

7. <span data-ttu-id="87dde-701">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-701">Select **Save**.</span></span>

#### <a name="define-the-data-binding-for-a-report-title"></a><a name="DefineFormatBindings"></a><span data-ttu-id="87dde-702">Adatkötés definiálása a jelentés címéhez</span><span class="sxs-lookup"><span data-stu-id="87dde-702">Define the data binding for a report title</span></span>

<span data-ttu-id="87dde-703">Az olyan formátumelemekhez, amelyek a létrehozott jelentések címének kitöltésére szolgálnak, meg kell határozni adatkötést.</span><span class="sxs-lookup"><span data-stu-id="87dde-703">You must specify a data binding for a format element that is used to fill in the title of a generated report.</span></span>

1. <span data-ttu-id="87dde-704">A **Formátumtervező** oldal **Leképezés** lapjának jobb oldalán válassza a **Report\\ReportTitle** elemet.</span><span class="sxs-lookup"><span data-stu-id="87dde-704">On the **Format designer** page, on the **Mapping** tab on the right, select the **Report\\ReportTitle** element.</span></span>
2. <span data-ttu-id="87dde-705">Válassza a **Képlet szerkesztése** elemet.</span><span class="sxs-lookup"><span data-stu-id="87dde-705">Select **Edit formula**.</span></span>
3. <span data-ttu-id="87dde-706">A receptúraszerkesztőben válassza a **Fordítás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-706">In the formula editor, select **Translate**.</span></span>
4. <span data-ttu-id="87dde-707">A **Szöveg fordítása** párbeszédpanelen hajtsa végre a következő lépéseket:</span><span class="sxs-lookup"><span data-stu-id="87dde-707">In the **Text translation** dialog box, follow these steps:</span></span>

    1. <span data-ttu-id="87dde-708">A **Címkeazonosító** mezőbe írja a **ReportTitle** értéket.</span><span class="sxs-lookup"><span data-stu-id="87dde-708">In the **Label ID** field, enter **ReportTitle**.</span></span>
    2. <span data-ttu-id="87dde-709">A **Szöveg az alapértelmezett nyelven** mezőben adja meg: **Kérdőívek jelentése**.</span><span class="sxs-lookup"><span data-stu-id="87dde-709">In the **Text in default language** field, enter **Questionnaires report**.</span></span>
    3. <span data-ttu-id="87dde-710">Válassza a **Fordítás**, majd a **Mentés** elemet.</span><span class="sxs-lookup"><span data-stu-id="87dde-710">Select **Translate**, and then select **Save**.</span></span>
    4. <span data-ttu-id="87dde-711">A **Fordítás** lehetőség kiválasztásával zárja be a **Szöveg fordítása** párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="87dde-711">Select **Translate** to close the **Text translation** dialog box.</span></span>

5. <span data-ttu-id="87dde-712">Zárja be a receptúraszerkesztőt.</span><span class="sxs-lookup"><span data-stu-id="87dde-712">Close the formula editor.</span></span>

    ![A kötés konfigurálása a létrehozott jelentés címének kitöltéséhez](./media/er-quick-start1-add-report-title-label.png)

<span data-ttu-id="87dde-714">Ezzel a technikával az aktuális sablon sablonnyelvtől függő összes további címke elkészíthető.</span><span class="sxs-lookup"><span data-stu-id="87dde-714">You can use this technique to make all other labels of the current template language-dependent.</span></span> <span data-ttu-id="87dde-715">Ha további információt szeretne arról, hogyan egy adott ER-konfiguráció hozzáadott címkéi hogyan fordíthatók le az összes támogatott nyelvre, tekintse át a [Többnyelvű jelentések tervezése](er-design-multilingual-reports.md) részt.</span><span class="sxs-lookup"><span data-stu-id="87dde-715">For information about how the added labels of a single ER configuration can be translated into all supported languages, see [Design multilingual reports](er-design-multilingual-reports.md).</span></span>

#### <a name="review-model-data-source"></a><a name="ReviewModelDataSource"></a><span data-ttu-id="87dde-716">A modell adatforrásának ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="87dde-716">Review model data source</span></span>

1. <span data-ttu-id="87dde-717">A **Formátumtervező** oldal **Leképezés** lapján válassza ki a <a name="ModelDSName"></a>**modell** adatforrást, amely ennek az ER-formátumnak az alap adatmodelljét jelzi.</span><span class="sxs-lookup"><span data-stu-id="87dde-717">On the **Format designer** page, on the **Mapping** tab, select the <a name="ModelDSName"></a>**model** data source that represents the base data model of this ER format.</span></span>
2. <span data-ttu-id="87dde-718">Válassza ki a **Szerkesztés** opciót.</span><span class="sxs-lookup"><span data-stu-id="87dde-718">Select **Edit**.</span></span>
3. <span data-ttu-id="87dde-719">Tekintse át az **Adatforrás-tulajdonságok** párbeszédpanelen lévő adatokat.</span><span class="sxs-lookup"><span data-stu-id="87dde-719">Review the information in the **Data source properties** dialog box.</span></span> <span data-ttu-id="87dde-720">Ez az adatforrás jelöli a **Kérdőívek** adatmodell-összetevő 1. verzióját, amely a **Kérdőívek modell** ER-konfigurációjában található.</span><span class="sxs-lookup"><span data-stu-id="87dde-720">This data source represents version 1 of the **Questionnaires** data model component that resides in the **Questionnaires model** ER configuration.</span></span>

![A modelladatforrás tulajdonságai az ER-művelettervezőben](./media/er-quick-start1-model-data-source.png)

#### <a name="bind-format-elements-to-data-source-fields"></a><a name="BindFormatElements"></a><span data-ttu-id="87dde-722">Formátum-összetevők összekötése az adatforrás mezőivel</span><span class="sxs-lookup"><span data-stu-id="87dde-722">Bind format elements to data source fields</span></span>

<span data-ttu-id="87dde-723">Ha meg szeretné adni, hogyan történjen egy sablon kitöltése a futásidőben, akkor a megfelelő Excel-nevekhez társított minden formátumelemet kötni kell e formátum adatforrásának egy adott mezőjéhez.</span><span class="sxs-lookup"><span data-stu-id="87dde-723">To specify how a template is filled in at runtime, you must bind every format element that is associated with an appropriate Excel name to a single field of this format's data source.</span></span>

1. <span data-ttu-id="87dde-724">A **Formátumtervező** oldal formátumfájában válassza ki a **Report\\CompanyName** formátumelemet.</span><span class="sxs-lookup"><span data-stu-id="87dde-724">On the **Format designer** page, in the format tree, select the **Report\\CompanyName** format element.</span></span>
2. <span data-ttu-id="87dde-725">A **Leképezés** lapon válassza ki a **Sztring** típus **model.CompanyName** adatforrásmezőjét.</span><span class="sxs-lookup"><span data-stu-id="87dde-725">On the **Mapping** tab, select the **model.CompanyName** data source field of the **String** type.</span></span>
3. <span data-ttu-id="87dde-726">Ha meg szeretné adni egy vállalat nevét a sablonban, válassza a **Kötés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-726">Select **Bind** to enter a company name in a template.</span></span>
4. <span data-ttu-id="87dde-727">A formátumfában válassza ki a **Report\\Questionnaire** elemet.</span><span class="sxs-lookup"><span data-stu-id="87dde-727">In the format tree, select the **Report\\Questionnaire** element.</span></span>
5. <span data-ttu-id="87dde-728">A **Leképezés** lapon válassza ki a **Rekordlista** típus **model.Questionnaire** adatforrásmezőjét.</span><span class="sxs-lookup"><span data-stu-id="87dde-728">On the **Mapping** tab, select the **model.Questionnaire** data source field of the **Record list** type.</span></span>
6. <span data-ttu-id="87dde-729">Válassza a **Bind** elemet.</span><span class="sxs-lookup"><span data-stu-id="87dde-729">Select **Bind**.</span></span>
7. <span data-ttu-id="87dde-730">A formátumelemek további részleteinek megtekintéséhez válassza a **Részletek megjelenítése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-730">Select **Show details** to see more details for format elements.</span></span>

    <span data-ttu-id="87dde-731">A **Kérdőív** tartomány formátumeleme vertikálisan replikáltként van konfigurálva.</span><span class="sxs-lookup"><span data-stu-id="87dde-731">The **Questionnaire** range format element is configured as vertically replicated.</span></span> <span data-ttu-id="87dde-732">Amikor **Rekordlista** típusú adatforráshoz kötik, a program megismétli az Excel-sablon megfelelő **Kérdőív** tartományát a kötésben lévő adatforrás minden rekordjánál.</span><span class="sxs-lookup"><span data-stu-id="87dde-732">When it's bound to a data source of the **Record list** type, the appropriate **Questionnaire** range of the Excel template is repeated for every record of the bound data source.</span></span>
 
    ![A Kérdőív tartomány formátumelemének kötése a megfelelő Rekord lista adatforrásaihoz az ER-művelettervezőben](./media/er-quick-start1-bindings1.png)

    <span data-ttu-id="87dde-734">Mivel az Excel-sablon **Kérdőív** tartományának definiálása az 5–14. sor között történik, ezeket a sorokat a rendszer minden jelentett kérdőívnél megismétli.</span><span class="sxs-lookup"><span data-stu-id="87dde-734">Because the **Questionnaire** range of the Excel template is defined between rows 5 through 14, these rows are repeated for every reported questionnaire.</span></span>

    ![Az Excel-sablon olyan sorai, amelyek egy létrehozott jelentésben a Rekord lista adatforrásainak valamennyi rekordjához megismétlődnek](./media/er-quick-start1-template-questionnaire-range.png)

8. <span data-ttu-id="87dde-736">A fennmaradó formátumelemekhez konfiguráljon hasonló kötéseket, a következő táblázatban leírt módon.</span><span class="sxs-lookup"><span data-stu-id="87dde-736">Configure similar bindings for the remaining format elements, as described in the following table.</span></span>

    > [!NOTE]
    > <span data-ttu-id="87dde-737">Ebben a táblában az „Adatforrás elérési útja” oszlopban szereplő információ azt feltételezi, hogy a [relatív elérési út](relative-path-data-bindings-er-models-format.md) ER-funkció be van kapcsolva.</span><span class="sxs-lookup"><span data-stu-id="87dde-737">In this table, the information in the "Data source path" column assumes that the [relative path](relative-path-data-bindings-er-models-format.md) ER feature is turned on.</span></span>

    | <span data-ttu-id="87dde-738">Formátumelem elérési útja</span><span class="sxs-lookup"><span data-stu-id="87dde-738">Format element path</span></span>                                      | <span data-ttu-id="87dde-739">Adatforrás elérési útja</span><span class="sxs-lookup"><span data-stu-id="87dde-739">Data source path</span></span> |
    |----------------------------------------------------------|------------------|
    | <span data-ttu-id="87dde-740">Excel\\ReportTitle</span><span class="sxs-lookup"><span data-stu-id="87dde-740">Excel\\ReportTitle</span></span>                                       | <span data-ttu-id="87dde-741">**\@"GER\_LABEL:ReportTitle"**</span><span class="sxs-lookup"><span data-stu-id="87dde-741">**\@"GER\_LABEL:ReportTitle"**</span></span> |
    | <span data-ttu-id="87dde-742">Excel\\CompanyName</span><span class="sxs-lookup"><span data-stu-id="87dde-742">Excel\\CompanyName</span></span>                                       | <span data-ttu-id="87dde-743">**model.CompanyName**</span><span class="sxs-lookup"><span data-stu-id="87dde-743">**model.CompanyName**</span></span> |
    | <span data-ttu-id="87dde-744">Excel\\Questionnaire</span><span class="sxs-lookup"><span data-stu-id="87dde-744">Excel\\Questionnaire</span></span>                                     | <span data-ttu-id="87dde-745">**model.Questionnaire**</span><span class="sxs-lookup"><span data-stu-id="87dde-745">**model.Questionnaire**</span></span> |
    | <span data-ttu-id="87dde-746">Excel\\Questionnaire\\Active</span><span class="sxs-lookup"><span data-stu-id="87dde-746">Excel\\Questionnaire\\Active</span></span>                             | <span data-ttu-id="87dde-747">**\@.Active**, ahol a **\@** a **model.Questionnaire**</span><span class="sxs-lookup"><span data-stu-id="87dde-747">**\@.Active**, where **\@** is **model.Questionnaire**</span></span> |
    | <span data-ttu-id="87dde-748">Excel\\Questionnaire\\Code</span><span class="sxs-lookup"><span data-stu-id="87dde-748">Excel\\Questionnaire\\Code</span></span>                               | <span data-ttu-id="87dde-749">**\@.Code**</span><span class="sxs-lookup"><span data-stu-id="87dde-749">**\@.Code**</span></span> |
    | <span data-ttu-id="87dde-750">Excel\\Questionnaire\\Description</span><span class="sxs-lookup"><span data-stu-id="87dde-750">Excel\\Questionnaire\\Description</span></span>                        | <span data-ttu-id="87dde-751">**\@.Description**</span><span class="sxs-lookup"><span data-stu-id="87dde-751">**\@.Description**</span></span> |
    | <span data-ttu-id="87dde-752">Excel\\Questionnaire\\QuestionnaireType</span><span class="sxs-lookup"><span data-stu-id="87dde-752">Excel\\Questionnaire\\QuestionnaireType</span></span>                  | <span data-ttu-id="87dde-753">**\@.QuestionnaireType**</span><span class="sxs-lookup"><span data-stu-id="87dde-753">**\@.QuestionnaireType**</span></span> |
    | <span data-ttu-id="87dde-754">Excel\\Questionnaire\\QuestionOrder</span><span class="sxs-lookup"><span data-stu-id="87dde-754">Excel\\Questionnaire\\QuestionOrder</span></span>                      | <span data-ttu-id="87dde-755">**\@.QuestionOrder**</span><span class="sxs-lookup"><span data-stu-id="87dde-755">**\@.QuestionOrder**</span></span> |
    | <span data-ttu-id="87dde-756">Excel\\Questionnaire\\ResultsGroup\\Code\_</span><span class="sxs-lookup"><span data-stu-id="87dde-756">Excel\\Questionnaire\\ResultsGroup\\Code\_</span></span>               | <span data-ttu-id="87dde-757">**\@.ResultsGroup.Code**</span><span class="sxs-lookup"><span data-stu-id="87dde-757">**\@.ResultsGroup.Code**</span></span> |
    | <span data-ttu-id="87dde-758">Excel\\Questionnaire\\ResultsGroup\\Description\_</span><span class="sxs-lookup"><span data-stu-id="87dde-758">Excel\\Questionnaire\\ResultsGroup\\Description\_</span></span>        | <span data-ttu-id="87dde-759">**\@.ResultsGroup.Description**</span><span class="sxs-lookup"><span data-stu-id="87dde-759">**\@.ResultsGroup.Description**</span></span> |
    | <span data-ttu-id="87dde-760">Excel\\Questionnaire\\ResultsGroup\\MaxNumberOfPoints</span><span class="sxs-lookup"><span data-stu-id="87dde-760">Excel\\Questionnaire\\ResultsGroup\\MaxNumberOfPoints</span></span>    | <span data-ttu-id="87dde-761">**\@.ResultsGroup.MaxNumberOfPoint**</span><span class="sxs-lookup"><span data-stu-id="87dde-761">**\@.ResultsGroup.MaxNumberOfPoint**</span></span> |
    | <span data-ttu-id="87dde-762">Excel\\Questionnaire\\Question</span><span class="sxs-lookup"><span data-stu-id="87dde-762">Excel\\Questionnaire\\Question</span></span>                           | <span data-ttu-id="87dde-763">**\@.Question**</span><span class="sxs-lookup"><span data-stu-id="87dde-763">**\@.Question**</span></span> |
    | <span data-ttu-id="87dde-764">Excel\\Questionnaire\\Question\\CollectionSequenceNumber</span><span class="sxs-lookup"><span data-stu-id="87dde-764">Excel\\Questionnaire\\Question\\CollectionSequenceNumber</span></span> | <span data-ttu-id="87dde-765">**\@.CollectionSequenceNumber**, ahol a **\@** a **model.Questionnaire.Question**</span><span class="sxs-lookup"><span data-stu-id="87dde-765">**\@.CollectionSequenceNumber**, where **\@** is **model.Questionnaire.Question**</span></span> |
    | <span data-ttu-id="87dde-766">Excel\\Questionnaire\\Question\\Id</span><span class="sxs-lookup"><span data-stu-id="87dde-766">Excel\\Questionnaire\\Question\\Id</span></span>                       | <span data-ttu-id="87dde-767">**\@.Id**</span><span class="sxs-lookup"><span data-stu-id="87dde-767">**\@.Id**</span></span> |
    | <span data-ttu-id="87dde-768">Excel\\Questionnaire\\Question\\MustBeCompleted</span><span class="sxs-lookup"><span data-stu-id="87dde-768">Excel\\Questionnaire\\Question\\MustBeCompleted</span></span>          | <span data-ttu-id="87dde-769">**\@.MustBeCompleted**</span><span class="sxs-lookup"><span data-stu-id="87dde-769">**\@.MustBeCompleted**</span></span> |
    | <span data-ttu-id="87dde-770">Excel\\Questionnaire\\Question\\PrimaryQuestion</span><span class="sxs-lookup"><span data-stu-id="87dde-770">Excel\\Questionnaire\\Question\\PrimaryQuestion</span></span>          | <span data-ttu-id="87dde-771">**\@.PrimaryQuestion**</span><span class="sxs-lookup"><span data-stu-id="87dde-771">**\@.PrimaryQuestion**</span></span> |
    | <span data-ttu-id="87dde-772">Excel\\Questionnaire\\Question\\SequenceNumber</span><span class="sxs-lookup"><span data-stu-id="87dde-772">Excel\\Questionnaire\\Question\\SequenceNumber</span></span>           | <span data-ttu-id="87dde-773">**\@.SequenceNumber**</span><span class="sxs-lookup"><span data-stu-id="87dde-773">**\@.SequenceNumber**</span></span> |
    | <span data-ttu-id="87dde-774">Excel\\Questionnaire\\Question\\Text</span><span class="sxs-lookup"><span data-stu-id="87dde-774">Excel\\Questionnaire\\Question\\Text</span></span>                     | <span data-ttu-id="87dde-775">**\@.Text**</span><span class="sxs-lookup"><span data-stu-id="87dde-775">**\@.Text**</span></span> |
    | <span data-ttu-id="87dde-776">Excel\\Questionnaire\\Question\\Answer</span><span class="sxs-lookup"><span data-stu-id="87dde-776">Excel\\Questionnaire\\Question\\Answer</span></span>                   | <span data-ttu-id="87dde-777">**\@.Answer**</span><span class="sxs-lookup"><span data-stu-id="87dde-777">**\@.Answer**</span></span> |
    | <span data-ttu-id="87dde-778">Excel\\Questionnaire\\Question\\Answer\\CorrectAnswer</span><span class="sxs-lookup"><span data-stu-id="87dde-778">Excel\\Questionnaire\\Question\\Answer\\CorrectAnswer</span></span>    | <span data-ttu-id="87dde-779">**\@.CorrectAnswer**, ahol a **\@** a **model.Questionnaire.Answer**</span><span class="sxs-lookup"><span data-stu-id="87dde-779">**\@.CorrectAnswer**, where **\@** is **model.Questionnaire.Answer**</span></span> |
    | <span data-ttu-id="87dde-780">Excel\\Questionnaire\\Question\\Answer\\Points</span><span class="sxs-lookup"><span data-stu-id="87dde-780">Excel\\Questionnaire\\Question\\Answer\\Points</span></span>           | <span data-ttu-id="87dde-781">**\@.Points**</span><span class="sxs-lookup"><span data-stu-id="87dde-781">**\@.Points**</span></span> |
    | <span data-ttu-id="87dde-782">Excel\\Questionnaire\\Question\\Answer\\Text</span><span class="sxs-lookup"><span data-stu-id="87dde-782">Excel\\Questionnaire\\Question\\Answer\\Text</span></span>             | <span data-ttu-id="87dde-783">**\@.Text**</span><span class="sxs-lookup"><span data-stu-id="87dde-783">**\@.Text**</span></span> |

9. <span data-ttu-id="87dde-784">Amikor elkészült, válassza a **Mentés** elemet.</span><span class="sxs-lookup"><span data-stu-id="87dde-784">When you've finished, select **Save**.</span></span>

<span data-ttu-id="87dde-785">A következő ábra a **Formátumtervező** oldal konfigurált adatkötéseinek végleges állapotát mutatja.</span><span class="sxs-lookup"><span data-stu-id="87dde-785">The following illustration shows the final state of the configured data bindings on the **Format designer** page.</span></span>

![Konfigurált adatkötések az ER-művelettervezőben](./media/er-quick-start1-bindings2.png)

> [!IMPORTANT]
> <span data-ttu-id="87dde-787">A megadott adatforrások és kötések egész gyűjteménye a konfigurált formátum formátumleképezési összetevőjét jelöli.</span><span class="sxs-lookup"><span data-stu-id="87dde-787">The whole collection of specified data sources and bindings represents a format mapping component of the configured format.</span></span> <span data-ttu-id="87dde-788">A rendszer ezt a formátumleképezést hívja meg, amikor Ön futtatja konfigurált formátumot jelentések létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="87dde-788">This format mapping is called when you run the configured format for report generation.</span></span>

### <a name="run-a-designed-format-from-er"></a><a name="RunFormatFromER"></a><span data-ttu-id="87dde-789">Megtervezett formátum futtatása az ER-ből</span><span class="sxs-lookup"><span data-stu-id="87dde-789">Run a designed format from ER</span></span>

<span data-ttu-id="87dde-790">Most tesztelési célra futtathat egy tervezett formátumot a **Konfigurációk** oldalon.</span><span class="sxs-lookup"><span data-stu-id="87dde-790">You can now run a designed format for testing purposes from the **Configurations** page.</span></span>

1. <span data-ttu-id="87dde-791">Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.</span><span class="sxs-lookup"><span data-stu-id="87dde-791">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="87dde-792">A **Konfiguráció** oldalon, a konfigurációk bal oldali panelen található fájában bontsa ki a **Kérdőív modellje** elemet, majd válassza a **Jelentés a kérdőívről** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-792">On the **Configuration** page, in the configuration tree, expand **Questionnaire model**, and then select **Questionnaire report**.</span></span>
3. <span data-ttu-id="87dde-793">Válassza ki a **Tervező** lehetőséget a **Piszkozat** állapotú formátumverzióhoz.</span><span class="sxs-lookup"><span data-stu-id="87dde-793">Select **Designer** for the format version that has a status of **Draft**.</span></span>
4. <span data-ttu-id="87dde-794">A **Formátumtervező** oldalon válassza a **Futtatás** elemet.</span><span class="sxs-lookup"><span data-stu-id="87dde-794">On the **Format designer** page, select **Run**.</span></span>
5. <span data-ttu-id="87dde-795">Az **ER-paraméterek** párbeszédpanelén lévő **Belefoglalandó rekordok** gyorslapon adja meg a szűrőfeltételeket, hogy a rendszer csak az **SBCCrsExam** kérdőívet szerepeltesse.</span><span class="sxs-lookup"><span data-stu-id="87dde-795">In the **ER parameters** dialog box, on the **Records to include** FastTab, configure the filtering option so that only the **SBCCrsExam** questionnaire is included.</span></span>
6. <span data-ttu-id="87dde-796">A szűrési beállítás megerősítéséhez kattintson az **OK** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="87dde-796">Select **OK** to confirm the filtering option.</span></span>
7. <span data-ttu-id="87dde-797">A jelentés futtatásához válassza az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-797">Select **OK** to run the report.</span></span>
8. <span data-ttu-id="87dde-798">Tekintse át a létrehozott jelentést.</span><span class="sxs-lookup"><span data-stu-id="87dde-798">Review the generated report.</span></span>

<span data-ttu-id="87dde-799">[Alapértelmezés szerint](electronic-reporting-destinations.md#default-behavior) a létrejövő jelentések letölthető Excel-fájlként jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="87dde-799">By [default](electronic-reporting-destinations.md#default-behavior), a generated report is delivered as an Excel file that you can download.</span></span> <span data-ttu-id="87dde-800">A következő képeken a létrejövő Excel-formátumú jelentés két oldala látható.</span><span class="sxs-lookup"><span data-stu-id="87dde-800">The following illustrations show two pages of the generated report in Excel format.</span></span>

![A létrejövő Excel-formátumú jelentés példája, 1. oldal](./media/er-quick-start1-report1a.png)

![A létrejövő Excel-formátumú jelentés példája, 2. oldal](./media/er-quick-start1-report1b.png)

## <a name="tune-a-designed-format"></a><a name="TuneFormat"></a><span data-ttu-id="87dde-803">Megtervezett formátum finomhangolása</span><span class="sxs-lookup"><span data-stu-id="87dde-803">Tune a designed format</span></span>

### <a name="modify-a-format-to-change-the-name-of-a-generated-document"></a><a name="ModifyToChangeName"></a><span data-ttu-id="87dde-804">Formátum módosítása a létrehozott dokumentumok nevének módosításához</span><span class="sxs-lookup"><span data-stu-id="87dde-804">Modify a format to change the name of a generated document</span></span>

<span data-ttu-id="87dde-805">Alapértelmezés szerint a létrehozott dokumentumok elnevezése az aktuális felhasználó aliasával történik.</span><span class="sxs-lookup"><span data-stu-id="87dde-805">By default, a generated document is named by using the alias of the current user.</span></span> <span data-ttu-id="87dde-806">A formátum módosításával ezt a viselkedést módosíthatja, hogy a létrejövő dokumentumok elnevezése az Ön által megadott egyéni logika alapján történjen.</span><span class="sxs-lookup"><span data-stu-id="87dde-806">By modifying the format, you can change this behavior so that a generated document is named based on your custom logic.</span></span> <span data-ttu-id="87dde-807">A létrejövő dokumentumok neve például az aktuális munkamenet dátumán és időpontján és a jelentés címén alapulhat.</span><span class="sxs-lookup"><span data-stu-id="87dde-807">For example, the name of a generated document can be based on the current session date and time, and on the report's title.</span></span>

1. <span data-ttu-id="87dde-808">A **Formátumtervező** lapon válassza a **Jelentés** gyökérelemet.</span><span class="sxs-lookup"><span data-stu-id="87dde-808">On the **Format designer** page, select the **Report** root item.</span></span>
2. <span data-ttu-id="87dde-809">Válassza a **Leképezés** lap **Fájlnév szerkesztése** elemét.</span><span class="sxs-lookup"><span data-stu-id="87dde-809">On the **Mapping** tab, select **Edit file name**.</span></span>
3. <span data-ttu-id="87dde-810">A **Receptúra** mezőbe írja be a **CONCATENATE (\@"GER\_LABEL:ReportTitle", " - ", DATETIMEFORMAT(SESSIONNOW(), "yyyy-MM-dd hh-mm-ss"))** képletet.</span><span class="sxs-lookup"><span data-stu-id="87dde-810">In the **Formula** field, enter **CONCATENATE (\@"GER\_LABEL:ReportTitle", " - ", DATETIMEFORMAT(SESSIONNOW(), "yyyy-MM-dd hh-mm-ss"))**.</span></span>
4. <span data-ttu-id="87dde-811">Válassza a **Mentés** gombot, majd zárja be a receptúraszerkesztőt.</span><span class="sxs-lookup"><span data-stu-id="87dde-811">Select **Save**, and close the formula editor.</span></span>
5. <span data-ttu-id="87dde-812">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-812">Select **Save**.</span></span>

### <a name="modify-a-format-to-change-the-order-of-questions"></a><a name="ModifyToOrder"></a><span data-ttu-id="87dde-813">Formátum módosítása a kérdések sorrendjének módosításához</span><span class="sxs-lookup"><span data-stu-id="87dde-813">Modify a format to change the order of questions</span></span>

<span data-ttu-id="87dde-814">A kérdések nem megfelelő sorrendben vannak a létrejövő jelentésekben.</span><span class="sxs-lookup"><span data-stu-id="87dde-814">The questions aren't correctly ordered in a generated report.</span></span> <span data-ttu-id="87dde-815">A sorrendet a formátum módosításával lehet módosítani.</span><span class="sxs-lookup"><span data-stu-id="87dde-815">You can change the order by modifying the format.</span></span>

1. <span data-ttu-id="87dde-816">A **Formátumtervező** lapon válassza a **Jelentés** gyökérelemet.</span><span class="sxs-lookup"><span data-stu-id="87dde-816">On the **Format designer** page, select the **Report** root item.</span></span>
2. <span data-ttu-id="87dde-817">A **Leképezés** lapon lévő formátumfán bontsa ki a **Report\\Questionnaire\\Question** részt.</span><span class="sxs-lookup"><span data-stu-id="87dde-817">On the **Mapping** tab, in the format tree, expand **Report\\Questionnaire\\Question**.</span></span>

    ![A Tartomány típus Kérdés formátumeleme az ER-művelettervezőben](./media/er-quick-start1-bindings3.png)

3. <span data-ttu-id="87dde-819">A **Leképezés** lapon válassza a **model.Questionnaire** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-819">On the **Mapping** tab, select **model.Questionnaire**.</span></span>
4. <span data-ttu-id="87dde-820">Válassza a **Hozzáadás** \> **Functions\\Calculated field** lehetőséget, majd a **Név** mezőben adja meg, hogy **OrderedQuestions**.</span><span class="sxs-lookup"><span data-stu-id="87dde-820">Select **Add** \> **Functions\\Calculated field**, and then, in the **Name** field, enter **OrderedQuestions**.</span></span>
5. <span data-ttu-id="87dde-821">Válassza a **Képlet szerkesztése** elemet.</span><span class="sxs-lookup"><span data-stu-id="87dde-821">Select **Edit formula**.</span></span>
6. <span data-ttu-id="87dde-822">A receptúraszerkesztőben a **Receptúra** mezőbe írja be az **ORDERBY (model.Questionnaire.Question, model.Questionnaire.Question.SequenceNumber)** képletet az aktuális kérdőív kérdéslistájának sorszám szerint történő rendezéséhez.</span><span class="sxs-lookup"><span data-stu-id="87dde-822">In the formula editor, in the **Formula** field, enter **ORDERBY (model.Questionnaire.Question, model.Questionnaire.Question.SequenceNumber)** to order the list of questions of the current questionnaire by the sequence order number.</span></span>
7. <span data-ttu-id="87dde-823">Válassza a **Mentés** gombot, majd zárja be a receptúraszerkesztőt.</span><span class="sxs-lookup"><span data-stu-id="87dde-823">Select **Save**, and close the formula editor.</span></span>
8. <span data-ttu-id="87dde-824">Az új számított mező bejegyzésének befejezéséhez kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="87dde-824">Select **OK** to complete the entry of a new calculated field.</span></span>
9. <span data-ttu-id="87dde-825">A **Leképezés** lapon válassza a **model.Questionnaire.OrderedQuestions** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-825">On the **Mapping** tab, select **model.Questionnaire.OrderedQuestions**.</span></span>
10. <span data-ttu-id="87dde-826">A formátumokat megjelenítő fán válassza az **Excel\\Questionnaire\\Question** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-826">In the format tree, select **Excel\\Questionnaire\\Question**.</span></span>
11. <span data-ttu-id="87dde-827">Válassza a **Kötés** lehetőséget, majd győződjön meg arról, hogy az aktuális **model.Questionnaire.Questions** elérési utat a rendszer az új **model.Questionnaire.OrderedQuestions** elérési útra cserélte a beágyazott elemek összes kötésében.</span><span class="sxs-lookup"><span data-stu-id="87dde-827">Select **Bind**, and then confirm that the current **model.Questionnaire.Questions** path is replaced by the new **model.Questionnaire.OrderedQuestions** path in all bindings of nested elements.</span></span>
12. <span data-ttu-id="87dde-828">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-828">Select **Save**.</span></span>

![A Kérdés formátumú elem kötése a konfigurált OrderedQuestions-adatforráshoz az ER-művelettervezőben](./media/er-quick-start1-bindings4.png)

### <a name="run-a-modified-format-from-er"></a><a name="RunFormatFromER2"></a><span data-ttu-id="87dde-830">Módosított formátum futtatása az ER-ből</span><span class="sxs-lookup"><span data-stu-id="87dde-830">Run a modified format from ER</span></span>

<span data-ttu-id="87dde-831">Most már futtathat módosított formátumokat tesztelési célból az ER-keretrendszerből.</span><span class="sxs-lookup"><span data-stu-id="87dde-831">You can now run a modified format for testing purposes from the ER framework.</span></span>

1. <span data-ttu-id="87dde-832">A **Formátumtervező** oldalon válassza a **Futtatás** elemet.</span><span class="sxs-lookup"><span data-stu-id="87dde-832">On the **Format designer** page, select **Run**.</span></span>
2. <span data-ttu-id="87dde-833">Az **ER-paraméterek** párbeszédpanelén lévő **Belefoglalandó rekordok** gyorslapon adja meg a szűrőfeltételeket, hogy a rendszer csak az **SBCCrsExam** kérdőívet szerepeltesse.</span><span class="sxs-lookup"><span data-stu-id="87dde-833">In the **ER parameters** dialog box, on the **Records to include** FastTab, configure the filtering option so that only the **SBCCrsExam** questionnaire is included.</span></span>
3. <span data-ttu-id="87dde-834">A szűrési beállítás megerősítéséhez kattintson az **OK** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="87dde-834">Select **OK** to confirm the filtering option.</span></span>
4. <span data-ttu-id="87dde-835">A jelentés futtatásához válassza az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-835">Select **OK** to run the report.</span></span>
5. <span data-ttu-id="87dde-836">Tekintse át a létrehozott jelentést.</span><span class="sxs-lookup"><span data-stu-id="87dde-836">Review the generated report.</span></span>

<span data-ttu-id="87dde-837">A következő képen egy olyan Excel-formátumú létrehozott jelentés látható, amelyen helyes sorrendben vannak a kérdések.</span><span class="sxs-lookup"><span data-stu-id="87dde-837">The following illustration shows a generated report in Excel format where the questions are correctly ordered.</span></span>

![Excel-formátumú létrehozott jelentés, amely helyes sorrendbe rendezett kérdéseket tartalmaz](./media/er-quick-start1-report2.png)

### <a name="complete-the-format-design"></a><a name="CompleteFormat"></a><span data-ttu-id="87dde-839">A formátum kialakításának befejezése</span><span class="sxs-lookup"><span data-stu-id="87dde-839">Complete the format design</span></span>

1. <span data-ttu-id="87dde-840">Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.</span><span class="sxs-lookup"><span data-stu-id="87dde-840">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="87dde-841">A **Konfigurációk** oldalon, a konfigurációk bal oldali panelen található fájában bontsa ki a **Kérdőív modellje** elemet, majd válassza a **Jelentés a kérdőívről** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-841">On the **Configurations** page, in the configuration tree, expand **Questionnaire model**, and then select **Questionnaire report**.</span></span>
3. <span data-ttu-id="87dde-842">A **Verziók** gyorslapon válassza ki azt a konfigurációverziót, amelynek az állapota **Piszkozat**.</span><span class="sxs-lookup"><span data-stu-id="87dde-842">On the **Versions** FastTab, select the configuration version that has a status of **Draft**.</span></span>
4. <span data-ttu-id="87dde-843">Válassza az **Állapot módosítása** \> **Teljes** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-843">Select **Change status** \> **Complete**.</span></span>

<span data-ttu-id="87dde-844">A konfiguráció 1.1. verziójának állapota **Piszkozatról** **Befejezett** értékre módosul.</span><span class="sxs-lookup"><span data-stu-id="87dde-844">The status of version 1.1 of this configuration is changed from **Draft** to **Completed**.</span></span> <span data-ttu-id="87dde-845">Az 1.1. verzió a későbbiekben már nem módosítható.</span><span class="sxs-lookup"><span data-stu-id="87dde-845">Version 1.1 can no longer be changed.</span></span> <span data-ttu-id="87dde-846">Ez a verzió a konfigurált formátumot tartalmazza, és egyéni jelentés nyomtatására is használható.</span><span class="sxs-lookup"><span data-stu-id="87dde-846">This version contains the configured format and can be used to print your custom report.</span></span> <span data-ttu-id="87dde-847">A konfiguráció 1.2. változata létrejön **Piszkozat** állapottal.</span><span class="sxs-lookup"><span data-stu-id="87dde-847">Version 1.2 of this configuration is created and has a status of **Draft**.</span></span> <span data-ttu-id="87dde-848">Ezt a verziót a **Kérdőív** jelentés formátumának módosításával szerkesztheti.</span><span class="sxs-lookup"><span data-stu-id="87dde-848">You can edit this version to adjust the format of your **Questionnaire** report.</span></span>

![A szerkeszthető ER-konfiguráció verziói a Konfigurációk oldalon](./media/er-quick-start1-format-configuration.png)

> [!NOTE]
> <span data-ttu-id="87dde-850">A konfigurált formátum az Ön kialakítása a **Kérdőív** jelentéshez, és nincs kapcsolata Finance-specifikus összetevőkkel.</span><span class="sxs-lookup"><span data-stu-id="87dde-850">The configured format is your design of the **Questionnaire** report and contains no relations to the Finance-specific artefacts.</span></span>

## <a name="develop-application-artefacts-to-call-the-designed-report"></a><a name="DevelopCustomCode"></a><span data-ttu-id="87dde-851">Alkalmazás-összetevők fejlesztése a megtervezett jelentés meghívásához</span><span class="sxs-lookup"><span data-stu-id="87dde-851">Develop application artefacts to call the designed report</span></span>

<span data-ttu-id="87dde-852">Rendszergazda szerepkörű felhasználóként új logikát kell kidolgoznia, hogy a konfigurált ER-formátumot meg lehessen hívni az alkalmazás felhasználói felületéről (UI) az egyéni jelentés létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="87dde-852">As a user in the System Administrator role, you must develop new logic so that the configured ER format can be called from the application user interface (UI) to generate your custom report.</span></span> <span data-ttu-id="87dde-853">Az ER jelenleg nem rendelkezik ilyen típusú logika konfigurálásához használható funkciókkal.</span><span class="sxs-lookup"><span data-stu-id="87dde-853">Currently, ER doesn't offer any capability for configuring this type of logic.</span></span> <span data-ttu-id="87dde-854">Ennek megfelelően ehhez műszaki erőfeszítésre van szükség.</span><span class="sxs-lookup"><span data-stu-id="87dde-854">Therefore, some engineering work is required.</span></span> 

<span data-ttu-id="87dde-855">Az új logika kidolgozásához telepítenie kell egy olyan topológiát, amely támogatja a folyamatos buildet.</span><span class="sxs-lookup"><span data-stu-id="87dde-855">To develop the new logic, you must deploy a topology that supports continuous build.</span></span> <span data-ttu-id="87dde-856">A további tudnivalókért lásd: [A folyamatos build- és tesztautomatizálást támogató topológiák telepítése](../perf-test/continuous-build-test-automation.md).</span><span class="sxs-lookup"><span data-stu-id="87dde-856">For more information, see [Deploy topologies that support continuous build and test automation](../perf-test/continuous-build-test-automation.md).</span></span> <span data-ttu-id="87dde-857">Ezen topológia fejlesztői környezetéhez való hozzáféréssel is kell rendelkezzen.</span><span class="sxs-lookup"><span data-stu-id="87dde-857">You must also have access to the development environment for this topology.</span></span> <span data-ttu-id="87dde-858">További információ az elérhető ER API-ról: [Elektronikus jelentéskészítési keretrendszer API](er-apis-app73.md).</span><span class="sxs-lookup"><span data-stu-id="87dde-858">For more information about the available ER API, see [ER framework API](er-apis-app73.md).</span></span>

### <a name="modify-source-code"></a><a name="ModifySourceCode"></a><span data-ttu-id="87dde-859">Forráskód módosítása</span><span class="sxs-lookup"><span data-stu-id="87dde-859">Modify source code</span></span>

#### <a name="add-a-data-contract-class"></a><a name="DataContractClass"></a><span data-ttu-id="87dde-860">Adatszerződés-osztály hozzáadása</span><span class="sxs-lookup"><span data-stu-id="87dde-860">Add a data contract class</span></span>

<span data-ttu-id="87dde-861">Adja hozzá az új **QuestionnairesErReportContract** osztályt a Microsoft Visual Studio-projekthez, és írjon egy olyan kódot, amely meghatározza, hogy melyik adatszerződést kell használni a konfigurált ER-formátum futtatásához.</span><span class="sxs-lookup"><span data-stu-id="87dde-861">Add the new **QuestionnairesErReportContract** class to your Microsoft Visual Studio project, and write code that specifies the data contract that should be used to run the configured ER format.</span></span>

```xpp
/// <summary>
///     This class is the data contract class for the <c>QuestionnairesErReportDP</c> class.
/// </summary>
/// <remarks>
///    This is the data contract class for the Questionnaires ER report.
/// </remarks>
[
    DataContractAttribute,
    SysOperationContractProcessingAttribute(classStr(QuestionnairesErReportUIBuilder))
    ]
    public class QuestionnairesErReportContract extends ERFormatMappingRunBaseContract implements SysOperationValidatable
{
    ERFormatMappingId formatMapping;

    /// <summary>
    ///    Validates the report parameters.
    /// </summary>
    /// <returns>
    ///    true if no errors; otherwise, false.
    /// </returns>
    public boolean validate()
    {
        boolean ret = true;
        if (!formatMapping)
        {
            ret = checkFailed(strFmt("@SYS26332", new SysDictType(extendedTypeNum(ERFormatMappingId)).label()));
        }
        return ret;
    }
    [
        DataMemberAttribute('FormatMapping'),
        SysOperationLabelAttribute(literalstr("@ElectronicReporting:FormatMapping")),
        SysOperationHelpTextAttribute(literalstr("@ElectronicReporting:FormatMapping"))
    ]
    public ERFormatMappingId parmFormatMapping(ERFormatMappingId _formatMapping = formatMapping)
    {
        formatMapping = _formatMapping;
        return formatMapping;
    }
}
```

#### <a name="add-a-ui-builder-class"></a><a name="UIBuilderClass"></a><span data-ttu-id="87dde-862">UI-készítő osztály hozzáadása</span><span class="sxs-lookup"><span data-stu-id="87dde-862">Add a UI builder class</span></span>

<span data-ttu-id="87dde-863">Adja hozzá az új **QuestionnairesErReportUIBuilder** osztályt a Visual Studio-projekthez, és írjon egy kódot, amely olyan futásidejű párbeszédpanelt hoz létre, amellyel megkereshető a futtatandó ER-formátum formátum-hozzárendelési azonosítója.</span><span class="sxs-lookup"><span data-stu-id="87dde-863">Add the new **QuestionnairesErReportUIBuilder** class to your Visual Studio project, and write code to generate a runtime dialog box that will be used to look up the format mapping ID of the ER format that must be run.</span></span> <span data-ttu-id="87dde-864">A megadott kód csak olyan ER-formátumokat keres, amelyek az **Adatmodell** típus olyan adatforrását tartalmazzák, amely a **[Kérdőívek](#DataModeName)** adatmodellre a **[Gyökér](#RootDefinitionName)** definícióval hivatkozik.</span><span class="sxs-lookup"><span data-stu-id="87dde-864">The provided code looks up only ER formats that contain a data source of the **Data model** type that refers to the **[Questionnaires](#DataModeName)** data model by using the **[Root](#RootDefinitionName)** definition.</span></span>

> [!NOTE]
> <span data-ttu-id="87dde-865">Egy másik lehetőség, hogy az ER-formátumok szűréséhez ER-integrációs pontokat használ.</span><span class="sxs-lookup"><span data-stu-id="87dde-865">Alternatively, you can use ER integration points to filter ER formats.</span></span> <span data-ttu-id="87dde-866">További információ: [API a formátumleképezési keresés megjelenítéséhez](er-apis-app10-0-11.md#api-to-show-a-format-mapping-lookup).</span><span class="sxs-lookup"><span data-stu-id="87dde-866">For more information, see [API to show a format mapping lookup](er-apis-app10-0-11.md#api-to-show-a-format-mapping-lookup).</span></span>

```xpp
/// <summary>
/// The UIBuilder class for Questionnaires ER report
/// </summary>
class QuestionnairesErReportUIBuilder extends SysOperationAutomaticUIBuilder
{
    public const str ERQuestionnairesModel = 'Questionnaires';
    public const str ERQuestionnairesDataContainer = 'Root';

    /// <summary>
    /// Action after build of the dialog UI.
    /// </summary>
    public void postBuild()
    {
        DialogField formatMapping;
        super();
        formatMapping = this.bindInfo().getDialogField(this.dataContractObject(),
            methodStr(QuestionnairesErReportContract, parmFormatMapping));
        formatMapping.registerOverrideMethod(
            methodStr(FormReferenceControl, lookupReference),
            methodStr(QuestionnairesErReportUIBuilder, formatMappingLookup),
            this);
    }

    /// <summary>
    /// Performs the lookup form for format mapping.
    /// </summary>
    /// <param name="_referenceGroupControl">
    /// The control to perform lookup form.
    /// </param>
    public void formatMappingLookup(FormReferenceControl _referenceGroupControl)
    {
        ERObjectsFactory::createFormatMappingTableLookupForControlAndModel(
            _referenceGroupControl,
            ERQuestionnairesModel,
            ERQuestionnairesDataContainer).performFormLookup();
    }
}
```

#### <a name="add-a-data-provider-class"></a><a name="DataProviderClass"></a><span data-ttu-id="87dde-867">Adatszolgáltató-osztály hozzáadása</span><span class="sxs-lookup"><span data-stu-id="87dde-867">Add a data provider class</span></span>

<span data-ttu-id="87dde-868">Adja hozzá az új **QuestionnairesErReportDP** osztályt a Microsoft Visual Studio-projekthez, és írjon egy olyan kódot, amely megadja, hogy melyik adatszolgáltatót kell használni a konfigurált ER-formátum futtatásához.</span><span class="sxs-lookup"><span data-stu-id="87dde-868">Add the new **QuestionnairesErReportDP** class to your Visual Studio project, and write code that introduces the data provider that should used to run the configured ER format.</span></span> <span data-ttu-id="87dde-869">A megadott kód csak ennek az adatszolgáltatónak az adatszerződését tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="87dde-869">The provided code includes only the data contract for this data provider.</span></span>

```xpp
/// <summary>
/// Data provider class for Questionnaires ER report.
/// </summary>
public class QuestionnairesErReportDP
{
    QuestionnairesErReportContract contract;
    public static QuestionnairesErReportDP construct()
    {
        QuestionnairesErReportDP  dataProvider;
        dataProvider = new QuestionnairesErReportDP();
        return dataProvider;
    }
}
```

#### <a name="add-a-labels-file"></a><a name="LabelsFile"></a><span data-ttu-id="87dde-870">Címkéket tartalmazó fájlok hozzáadása</span><span class="sxs-lookup"><span data-stu-id="87dde-870">Add a labels file</span></span>

<span data-ttu-id="87dde-871">Adja hozzá az új **QuestionnairesErReportLabels\_en-US** címkék fájlját a Visual Studio-projekthez, és határozza meg a következő címkéket az új felhasználói felületi erőforrásokhoz:</span><span class="sxs-lookup"><span data-stu-id="87dde-871">Add the new **QuestionnairesErReportLabels\_en-US** labels file to your Visual Studio project, and specify the following labels for new UI resources:</span></span>

- <span data-ttu-id="87dde-872">A **\@QuestionnairesReport** címke olyan új menüelemhez, amely amerikai angol nyelven (en-US) tartalmazza a következő szöveget: **Kérdőívek jelentése (ER használatával)**</span><span class="sxs-lookup"><span data-stu-id="87dde-872">The **\@QuestionnairesReport** label for a new menu item that contains the following text in US English (en-US): **Questionnaires report (powered by ER)**</span></span>
- <span data-ttu-id="87dde-873">A **\@QuestionnairesReportBatchJobDescription** címke kötegelt feladatcímekhez, ha a kiválasztott ER-formátumot kötegelt feladatként ütemezték végrehajtásra</span><span class="sxs-lookup"><span data-stu-id="87dde-873">The **\@QuestionnairesReportBatchJobDescription** label for a batch job title if a selected ER format is scheduled for execution as a batch job</span></span>

#### <a name="add-a-report-service-class"></a><a name="ServiceClass"></a><span data-ttu-id="87dde-874">Jelentésszolgáltatási osztály hozzáadása</span><span class="sxs-lookup"><span data-stu-id="87dde-874">Add a report service class</span></span>

<span data-ttu-id="87dde-875">Adja hozzá az új **QuestionnairesErReportService** osztályt a Visual Studio-projekthez, és írjon egy olyan kódot, amely meghív egy ER-formátumot, meghatározza formátumleképezési azonosítóként, majd egy adatszerződést biztosít paraméterként.</span><span class="sxs-lookup"><span data-stu-id="87dde-875">Add the new **QuestionnairesErReportService** class to your Visual Studio project, and write code that calls an ER format, identifies it by a format mapping ID, and provides a data contract as a parameter.</span></span>

```xpp
using Microsoft.Dynamics365.LocalizationFramework;
/// <summary>
/// The electronic reporting service class for Questionnaires ER report
/// </summary>
class QuestionnairesErReportService extends SysOperationServiceBase
{
    public const str ERModelDataSourceName = 'model';
    public const str DefaultExportedFileName = 'Questionnaires report';
    public const str ParametersDataSourceName = 'RunTimeParameters';

    /// <summary>
    /// Generates report by using Electronic reporting framework
    /// </summary>
    /// <param name = "_contract">The Questionnaires report contract</param>
    public void generateReportByGER(QuestionnairesErReportContract _contract)
    {
        ERFormatMappingId formatMappingId;
        QuestionnairesErReportDP  dataProvider;
        dataProvider = QuestionnairesErReportDP::construct();
        formatMappingId = _contract.parmFormatMapping();
        if (formatMappingId)
        {
            try
            {
                ERIModelDefinitionParamsAction parameters = new ERModelDefinitionParamsUIActionComposite()
                    .add(new ERModelDefinitionObjectParameterAction(ERModelDataSourceName, ParametersDataSourceName, _contract, true));

                // Call ER to generate the report.
                ERIFormatMappingRun formatMappingRun = ERObjectsFactory::createFormatMappingRunByFormatMappingId(formatMappingId, DefaultExportedFileName);
                if (formatMappingRun.parmShowPromptDialog(true))
                {
                    formatMappingRun.withParameter(parameters);
                    formatMappingRun.withFileDestination(_contract.getFileDestination());
                    formatMappingRun.run();
                }
            }
            catch
            {
                // An error occurred while exporting data.
                error("@SYP4861341");
            }
        }
        else
        {
            // There is no data available.
            info("@SYS300117");
        }
    }
}
```

<span data-ttu-id="87dde-876">Amikor az alkalmazás adatait futtató ER-formátumot kell használnia, konfigurálnia kell az **Adatmodell** típus adatforrását a formátumleképezésben.</span><span class="sxs-lookup"><span data-stu-id="87dde-876">When you must use an ER format that runs application data, you must configure a data source of the **Data model** type in the format mapping.</span></span> <span data-ttu-id="87dde-877">Ez az adatforrás egyetlen gyökérdefiníció használatával utal a megadott adatmodell meghatározott részére.</span><span class="sxs-lookup"><span data-stu-id="87dde-877">This data source refers to a specific part of the specified data model by using a single root definition.</span></span> <span data-ttu-id="87dde-878">Az ER-formátum a futtatáskor ezt az adatforrást hívja meg, hogy elérje az adott modellhez és gyökérdefinícióhoz konfigurált megfelelő ER-modell-leképezést.</span><span class="sxs-lookup"><span data-stu-id="87dde-878">When the ER format is run, it calls this data source to access the appropriate ER model mapping that is configured for a given model and root definition.</span></span>

<span data-ttu-id="87dde-879">A forráskódban esetlegesen előkészített és az adatszerződés részeként tárolt összes adat átadható a futó ER-formátumnak az ilyen típusú ER-modell-leképezések használatával.</span><span class="sxs-lookup"><span data-stu-id="87dde-879">All the information that you might prepare in the source code and store as part of the data contract can be passed to the running ER format by using an ER model mapping of this type.</span></span> <span data-ttu-id="87dde-880">Az ER-modell-leképezésben konfigurálni kell egy olyan **Objektum** típusú adatforrást, amely a **[QuestionnairesErReportContract](#DataContractClass)** osztályra hivatkozik.</span><span class="sxs-lookup"><span data-stu-id="87dde-880">In the ER model mapping, you must configure a data source of the **Object** type that refers to the **[QuestionnairesErReportContract](#DataContractClass)** class.</span></span> <span data-ttu-id="87dde-881">A modell-leképezések azonosításához meg kell adnia egy olyan adatforrást, amely ezt a modell-leképezést hívja meg.</span><span class="sxs-lookup"><span data-stu-id="87dde-881">To identify a model mapping, you must specify a data source that calls this model mapping.</span></span> <span data-ttu-id="87dde-882">A megadott kódban ezt az adatforrást az az **ERModelDataSourceName** konstans határozza meg, amely a **[modell](#ModelDSName)** értékkel rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="87dde-882">In the provided code, this data source specified by the **ERModelDataSourceName** constant that has the **[model](#ModelDSName)** value.</span></span> <span data-ttu-id="87dde-883">Ha meg szeretné állapítani, hogy melyik adatforrás használatával történik a modell-leképezésben lévő adatszerződés elérhetővé tétele, meg kell adnia egy adatforrásnevet.</span><span class="sxs-lookup"><span data-stu-id="87dde-883">To identify which data source is used to expose the data contract in the model mapping, you must specify a data source name.</span></span> <span data-ttu-id="87dde-884">A megadott kódban ezt a nevet az a **ParametersDataSourceName** konstans határozza meg, amely a <a name="DataContractDSName"></a>**RunTimeParameters** értékkel rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="87dde-884">In the provided code, this name is specified by the **ParametersDataSourceName** constant that has <a name="DataContractDSName"></a>**RunTimeParameters** value.</span></span>

> [!NOTE]
> <span data-ttu-id="87dde-885">Az új környezetekben előfordulhat, hogy frissíteni kell az ER-metaadatokat, hogy az ilyen típusú osztály elérhető legyen az ER-modell-leképezés tervezőjében.</span><span class="sxs-lookup"><span data-stu-id="87dde-885">In a new environment, you might have to refresh the ER metadata so that this type of class is available in the ER model mapping designer.</span></span> <span data-ttu-id="87dde-886">További információ: [ER-keretrendszer konfigurálása](electronic-reporting-er-configure-parameters.md#frequently-asked-questions).</span><span class="sxs-lookup"><span data-stu-id="87dde-886">For more information, see [Configure the ER framework](electronic-reporting-er-configure-parameters.md#frequently-asked-questions).</span></span>

#### <a name="add-a-report-controller-class"></a><a name="ControllerClass"></a><span data-ttu-id="87dde-887">Jelentésvezérlő osztály hozzáadása</span><span class="sxs-lookup"><span data-stu-id="87dde-887">Add a report controller class</span></span>

<span data-ttu-id="87dde-888">Adja hozzá az új **QuestionnairesErReportController** osztályt a Visual Studio-projekthez, és írjon egy olyan kódot, amely (igény szerint) vagy szinkron vagy kötegelt módban futtat egy ER-formátumot azon a párbeszédpanelen, amely a megadott **QuestionnairesErReportUIBuilder** osztály logikájára épül.</span><span class="sxs-lookup"><span data-stu-id="87dde-888">Add the new **QuestionnairesErReportController** class to your Visual Studio project, and write code that runs an ER format in either synchronous mode or batch mode, as you prefer, in the dialog box that is built based on the logic of the provided **QuestionnairesErReportUIBuilder** class.</span></span>

```xpp
/// <summary>
/// The controller for Questionnaires ER report
/// </summary>
class QuestionnairesErReportController extends ERFormatMappingRunBaseController
{
    /// <summary>
    /// The main entrance of the controller
    /// </summary>
    /// <param name = "args">The arguments</param>
    public static void main(Args args)
    {
        QuestionnairesErReportController operation;
        operation = new QuestionnairesErReportController(
            classStr(QuestionnairesErReportService),
            methodStr(QuestionnairesErReportService, generateReportByGER),
            SysOperationExecutionMode::Synchronous);
        operation.startOperation();
    }

    /// <summary>
    /// Gets caption of the dialog.
    /// </summary>
    /// <returns>Caption of the dialog</returns>
    public ClassDescription defaultCaption()
    {
        ClassDescription batchDescription;
        batchDescription = "Questionnaires report (powered by ER)";
        return batchDescription;
    }
}
```

#### <a name="add-a-menu-item"></a><a name="MenuItem"></a><span data-ttu-id="87dde-889">Menüelem hozzáadása</span><span class="sxs-lookup"><span data-stu-id="87dde-889">Add a menu item</span></span>

<span data-ttu-id="87dde-890">Adja hozzá az új **QuestionnairesErReport** menüelemet a Visual Studio-projekthez.</span><span class="sxs-lookup"><span data-stu-id="87dde-890">Add the new **QuestionnairesErReport** menu item to your Visual Studio project.</span></span> <span data-ttu-id="87dde-891">Az **Objektum** tulajdonságában ez a menüelem a **QuestionnairesErReportController** osztályra hivatkozik, és az ER-formátumok kiválasztásához és futtatásához szükséges felhasználói engedély meghatározásához használatos.</span><span class="sxs-lookup"><span data-stu-id="87dde-891">In the **Object** property, this menu item refers to the **QuestionnairesErReportController** class, and it's used to specify a user permission to select and run an ER format.</span></span> <span data-ttu-id="87dde-892">A **Címke** tulajdonságban ez a menüelem a korábban létrehozott **\@QuestionnairesReport** címkére hivatkozik, hogy megfelelő szöveg jelenjen meg az alkalmazás kezelőfelületén.</span><span class="sxs-lookup"><span data-stu-id="87dde-892">In the **Label** property, this menu item refers to the **\@QuestionnairesReport** label that you created earlier, so that correct text is presented in the application UI.</span></span>

#### <a name="add-a-menu-item-to-a-menu"></a><a name="Menu"></a><span data-ttu-id="87dde-893">Menüelem hozzáadása a menükhöz</span><span class="sxs-lookup"><span data-stu-id="87dde-893">Add a menu item to a menu</span></span>

<span data-ttu-id="87dde-894">Adja hozzá a meglévő **KM** menüt a Visual Studio-projekthez.</span><span class="sxs-lookup"><span data-stu-id="87dde-894">Add the existing **KM** menu to your Visual Studio project.</span></span> <span data-ttu-id="87dde-895">Ehhez a menühöz fel kell vennie egy új **QuestionnairesErReport** elemet a **Kimenet** típusból.</span><span class="sxs-lookup"><span data-stu-id="87dde-895">You must add a new **QuestionnairesErReport** item of the **Output** type to this menu.</span></span> <span data-ttu-id="87dde-896">Ennek az elemnek az előző szakaszban leírt **QuestionnairesErReport** menüelemre kell hivatkoznia.</span><span class="sxs-lookup"><span data-stu-id="87dde-896">This item must refer to the **QuestionnairesErReport** menu item that is described in the previous section.</span></span>

#### <a name="build-a-visual-studio-project"></a><a name="BuildVSProject"></a><span data-ttu-id="87dde-897">Visual Studio-projekt készítése</span><span class="sxs-lookup"><span data-stu-id="87dde-897">Build a Visual Studio project</span></span>

<span data-ttu-id="87dde-898">Készítse el a felhasználók számára új menüelemet elérhetővé tevő projektet.</span><span class="sxs-lookup"><span data-stu-id="87dde-898">Build your project to make a new menu item available to users.</span></span>

### <a name="run-a-format-from-the-application"></a><a name="RunFormatFromApp"></a><span data-ttu-id="87dde-899">Formátum futtatása az alkalmazásból</span><span class="sxs-lookup"><span data-stu-id="87dde-899">Run a format from the application</span></span>

1. <span data-ttu-id="87dde-900">Lépjen a **Kérdőív** \> **Tervezés** \> **Kérdőívek jelentése (ER használatával)** részre.</span><span class="sxs-lookup"><span data-stu-id="87dde-900">Go to **Questionnaire** \> **Design** \> **Questionnaires report (powered by ER)**.</span></span>

    ![A Kérdőívek jelentése (ER használatával) menüelem kiválasztása a Kérdőív modulban a konfigurált ER-formátum futtatásához](./media/er-quick-start1-application-menu-modified.png)

2. <span data-ttu-id="87dde-902">A párbeszédpanel **Formátum leképezése** mezőjében válassza a **Kérdőívek jelentése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-902">In the dialog box, in the **Format mapping** field, select **Questionnaires report**.</span></span>
3. <span data-ttu-id="87dde-903">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-903">Select **OK**.</span></span>
4. <span data-ttu-id="87dde-904">Az **Elektronikus jelentés paraméterei** párbeszédpanelén lévő **Belefoglalandó rekordok** gyorslapon adja meg a szűrőfeltételeket, hogy a rendszer csak az **SBCCrsExam** kérdőívet szerepeltesse.</span><span class="sxs-lookup"><span data-stu-id="87dde-904">In the **Electronic report parameters** dialog box, on the **Records to include** FastTab, configure the filtering option so that only the **SBCCrsExam** questionnaire is included.</span></span>
5. <span data-ttu-id="87dde-905">A szűrési beállítás megerősítéséhez kattintson az **OK** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="87dde-905">Select **OK** to confirm the filtering option.</span></span>
6. <span data-ttu-id="87dde-906">A jelentés futtatásához válassza az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-906">Select **OK** to run the report.</span></span>

    ![A kiválasztási feltételek megadása az Elektronikus jelentés párbeszédpanelen](./media/er-quick-start1-report-run-dialog-page.png)

7. <span data-ttu-id="87dde-908">Tekintse át a létrehozott jelentést.</span><span class="sxs-lookup"><span data-stu-id="87dde-908">Review the generated report.</span></span>

## <a name="tune-a-designed-er-solution"></a><a name="TuneSolution"></a><span data-ttu-id="87dde-909">Megtervezett ER-megoldás finomhangolása</span><span class="sxs-lookup"><span data-stu-id="87dde-909">Tune a designed ER solution</span></span>

<span data-ttu-id="87dde-910">A konfigurált ER megoldást módosíthatja úgy, hogy azt az adatszolgáltató osztályt használja, amellyel Ön elérhetővé tette a futó ER-formátum részleteit, így a létrehozott jelentésben lévő ER-formátum nevét adja meg.</span><span class="sxs-lookup"><span data-stu-id="87dde-910">You can modify the configured ER solution so that it uses the data provider class that you developed to access details of the running ER format, and so that it enters the name of this ER format in a generated report.</span></span>

### <a name="modify-a-model-mapping"></a><a name="ModifyModelMapping"></a><span data-ttu-id="87dde-911">Modell-hozzárendelés módosítása</span><span class="sxs-lookup"><span data-stu-id="87dde-911">Modify a model mapping</span></span>

#### <a name="add-data-sources-to-access-a-data-contract-object"></a><a name="AddDataSource1"></a><span data-ttu-id="87dde-912">Adatforrások hozzáadása adatszerződési objektum eléréséhez</span><span class="sxs-lookup"><span data-stu-id="87dde-912">Add data sources to access a data contract object</span></span>

1. <span data-ttu-id="87dde-913">Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.</span><span class="sxs-lookup"><span data-stu-id="87dde-913">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="87dde-914">A **Konfigurációk** oldalon, a konfigurációk bal oldali panelen található fájában bontsa ki a **Kérdőív modellje** elemet, majd válassza a **Kérdőív leképezése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-914">On the **Configurations** page, in the configuration tree, expand **Questionnaire model**, and then select **Questionnaire mapping**.</span></span>
3. <span data-ttu-id="87dde-915">A **Tervező** lehetőség kiválasztásával nyissa meg a **Modell leképezése adatforráshoz** oldalt.</span><span class="sxs-lookup"><span data-stu-id="87dde-915">Select **Designer** to open the **Model to datasource mapping** page.</span></span>
4. <span data-ttu-id="87dde-916">A **Tervező** lehetőség kiválasztásával nyissa meg a kiválasztott leképezést a modell-leképezés tervezőjében.</span><span class="sxs-lookup"><span data-stu-id="87dde-916">Select **Designer** to open the selected mapping in the model mapping designer.</span></span>
5. <span data-ttu-id="87dde-917">A **Modell-leképezés tervező** oldal **Adatforrástípusok** paneljén válassza a **Dynamics 365 for Operations\\Objektum** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-917">On the **Model mapping designer** page, in the **Data source types** pane, select **Dynamics 365 for Operations\\Object**.</span></span>
6. <span data-ttu-id="87dde-918">Az **Adatforrás** panelen válassza a **Gyökér hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="87dde-918">In the **Data sources** pane, select **Add root**.</span></span>
7. <span data-ttu-id="87dde-919">A párbeszédpanel **Név** mezőjébe írja be a **[RunTimeParameters](#DataContractDSName)** **QuestionnairesErReportService** osztály forráskódjában meghatározott értékét.</span><span class="sxs-lookup"><span data-stu-id="87dde-919">In the dialog box, in the **Name** field, enter **[RunTimeParameters](#DataContractDSName)**, as defined in the source code of the **QuestionnairesErReportService** class.</span></span>
8. <span data-ttu-id="87dde-920">Az **Osztály** mezőbe írja be a korábban kódolt **[QuestionnairesErReportContract](#DataContractClass)** értéket.</span><span class="sxs-lookup"><span data-stu-id="87dde-920">In the **Class** field, enter **[QuestionnairesErReportContract](#DataContractClass)**, which was coded earlier.</span></span>
9. <span data-ttu-id="87dde-921">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-921">Select **OK**.</span></span>
10. <span data-ttu-id="87dde-922">Bontsa ki a **RunTimeParameters** részt.</span><span class="sxs-lookup"><span data-stu-id="87dde-922">Expand **RunTimeParameters**.</span></span>

<span data-ttu-id="87dde-923">A hozzáadott adatforrás információt tartalmaz a futó ER-formátumleképezés rekordazonosítójáról.</span><span class="sxs-lookup"><span data-stu-id="87dde-923">The added data source provides information about the record ID of the running ER format mapping.</span></span>

![Hozzáadott adatforrás az ER-modell-leképezés tervezőjében](./media/er-quick-start1-mapping3.png)

#### <a name="add-a-data-source-to-access-er-format-mapping-records"></a><a name="AddDataSource2"></a><span data-ttu-id="87dde-925">Adatforrások hozzáadása az ER-formátum leképezési rekordjaihoz való hozzáféréshez</span><span class="sxs-lookup"><span data-stu-id="87dde-925">Add a data source to access ER format mapping records</span></span>

<span data-ttu-id="87dde-926">Folytassa a kiválasztott modell-leképezés szerkesztését: adjon hozzá adatforrást az ER-formátum-leképezési rekordok eléréséhez.</span><span class="sxs-lookup"><span data-stu-id="87dde-926">Continue to edit the selected model mapping by adding a data source to access ER format mapping records.</span></span>

1. <span data-ttu-id="87dde-927">A **Modell-leképezés tervező** oldal **Adatforrástípusok** paneljén válassza a **Dynamics 365 for Operations\\Táblarekordok** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-927">On the **Model mapping designer** page, in the **Data source types** pane, select **Dynamics 365 for Operations\\Table records**.</span></span>
2. <span data-ttu-id="87dde-928">Az **Adatforrás** panelen válassza a **Gyökér hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="87dde-928">In the **Data sources** pane, select **Add root**.</span></span>
3. <span data-ttu-id="87dde-929">A párbeszédpanel **Név** mezőjébe írja be az **ER1** kifejezést.</span><span class="sxs-lookup"><span data-stu-id="87dde-929">In the dialog box, in the **Name** field, enter **ER1**.</span></span>
4. <span data-ttu-id="87dde-930">A **Tábla** mezőbe írja be a **ERFormatMappingTable** kifejezést.</span><span class="sxs-lookup"><span data-stu-id="87dde-930">In the **Table** field, enter **ERFormatMappingTable**.</span></span>
5. <span data-ttu-id="87dde-931">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-931">Select **OK**.</span></span>

#### <a name="add-a-data-source-to-access-a-format-mapping-record-of-a-running-er-format"></a><a name="AddDataSource3"></a><span data-ttu-id="87dde-932">Adatforrások hozzáadása a futó ER-formátum formátumleképezési rekordjaihoz való hozzáféréshez</span><span class="sxs-lookup"><span data-stu-id="87dde-932">Add a data source to access a format mapping record of a running ER format</span></span>

<span data-ttu-id="87dde-933">Folytassa a kiválasztott modell-leképezés szerkesztését: adjon hozzá adatforrást a futó ER-formátum formátumleképezési rekordjának eléréséhez.</span><span class="sxs-lookup"><span data-stu-id="87dde-933">Continue to edit the selected model mapping by adding a data source to access the format mapping record of the running ER format.</span></span>

1. <span data-ttu-id="87dde-934">A **Modell-leképezés tervező** oldal **Adatforrástípusok** paneljén válassza a **Functions\\Calculated field** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-934">On the **Model mapping designer** page, in the **Data source types** pane, select **Functions\\Calculated field**.</span></span>
2. <span data-ttu-id="87dde-935">Az **Adatforrás** panelen válassza a **Gyökér hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="87dde-935">In the **Data sources** pane, select **Add root**.</span></span>
3. <span data-ttu-id="87dde-936">A párbeszédpanel **Név** mezőjébe írja be az **ER2** kifejezést.</span><span class="sxs-lookup"><span data-stu-id="87dde-936">In the dialog box, in the **Name** field, enter **ER2**.</span></span>
4. <span data-ttu-id="87dde-937">Válassza a **Képlet szerkesztése** elemet.</span><span class="sxs-lookup"><span data-stu-id="87dde-937">Select **Edit formula**.</span></span>
5. <span data-ttu-id="87dde-938">A receptúraszerkesztő **Receptúra** mezőjébe írja be a **FIRSTORNULL (FILTER(ER1, ER1.RecId = RunTimeParameters.parmFormatMapping))** képletet.</span><span class="sxs-lookup"><span data-stu-id="87dde-938">In the formula editor, in the **Formula** field, enter **FIRSTORNULL (FILTER(ER1, ER1.RecId = RunTimeParameters.parmFormatMapping))**.</span></span>
6. <span data-ttu-id="87dde-939">Válassza a **Mentés** gombot, majd zárja be a receptúraszerkesztőt.</span><span class="sxs-lookup"><span data-stu-id="87dde-939">Select **Save**, and close the formula editor.</span></span>
7. <span data-ttu-id="87dde-940">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-940">Select **OK**.</span></span>

#### <a name="enter-the-name-of-the-running-er-format-in-the-data-model"></a><a name="AddBinding"></a><span data-ttu-id="87dde-941">Futó ER-formátum nevének megadása az adatmodellben</span><span class="sxs-lookup"><span data-stu-id="87dde-941">Enter the name of the running ER format in the data model</span></span>

<span data-ttu-id="87dde-942">Folytassa a kiválasztott modell-leképezés szerkesztését, hogy megadhassa az adatmodellben megadott futó ER-formátum nevét.</span><span class="sxs-lookup"><span data-stu-id="87dde-942">Continue to edit the selected model mapping so that the name of the running ER format is entered in the data model.</span></span>

1. <span data-ttu-id="87dde-943">A **Modell-leképezés tervező** oldal **Adatmodell** paneljén bontsa ki az **ExecutionContext** részt, és válassza az **ExecutionContext\\FormatName** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-943">On the **Model mapping designer** page, in the **Data model** pane, expand **ExecutionContext**, and then select **ExecutionContext\\FormatName**.</span></span>
2. <span data-ttu-id="87dde-944">Az **Adatmodell** panelen válassza a **Szerkesztés** lehetőséget a kiválasztott adatmodell mezőjéhez tartozó adatkötések konfigurálásához.</span><span class="sxs-lookup"><span data-stu-id="87dde-944">In the **Data model** pane, select **Edit** to configure a data binding for the selected data model's field.</span></span>
3. <span data-ttu-id="87dde-945">A receptúraszerkesztő **Receptúra** mezőjébe írja be a **FIRSTORNULL (ER2.'\>Relations'.Format).Name** képletet.</span><span class="sxs-lookup"><span data-stu-id="87dde-945">In the formula editor, in the **Formula** field, enter **FIRSTORNULL (ER2.'\>Relations'.Format).Name**.</span></span>
4. <span data-ttu-id="87dde-946">Válassza a **Mentés** gombot, majd zárja be a receptúraszerkesztőt.</span><span class="sxs-lookup"><span data-stu-id="87dde-946">Select **Save**, and close the formula editor.</span></span>

<span data-ttu-id="87dde-947">Mivel a **FormatName** mezőt használta, a konfigurált modell-leképezés megjeleníti egy olyan ER-formátum nevét, amely ezt a modellt hívja meg a végrehajtás során.</span><span class="sxs-lookup"><span data-stu-id="87dde-947">Because you used the **FormatName** field, the configured model mapping now exposes the name of an ER format that calls this model mapping during execution.</span></span>

![Az adatmodell mezőjének kötése az ER-modell-leképezés tervezőjében hozzáadott adatforrás metódusához](./media/er-quick-start1-mapping4.png)

#### <a name="complete-the-design-of-the-model-mapping"></a><a name="CompleteModelMapping2"></a><span data-ttu-id="87dde-949">A modell-leképezés kialakításának befejezése</span><span class="sxs-lookup"><span data-stu-id="87dde-949">Complete the design of the model mapping</span></span>

1. <span data-ttu-id="87dde-950">A **Modell-leképezés tervező** oldalon válassza a **Mentés** elemet.</span><span class="sxs-lookup"><span data-stu-id="87dde-950">On the **Model mapping designer** page, select **Save**.</span></span>
2. <span data-ttu-id="87dde-951">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="87dde-951">Close the page.</span></span>
3. <span data-ttu-id="87dde-952">Zárja be a Modell-leképezések oldalt.</span><span class="sxs-lookup"><span data-stu-id="87dde-952">Close the model mappings page.</span></span>
4. <span data-ttu-id="87dde-953">Ellenőrizze, hogy a **Konfigurációk** oldalon, a konfigurációkat tartalmazó fában a **Kérdőív leképezése** konfiguráció továbbra is be van jelölve.</span><span class="sxs-lookup"><span data-stu-id="87dde-953">On the **Configurations** page, in the configuration tree, make sure that the **Questionnaire mapping** configuration is still selected.</span></span> <span data-ttu-id="87dde-954">Ezután a **Verziók** gyorslapon válassza ki azt a konfigurációverziót, amelynek az állapota **Piszkozat**.</span><span class="sxs-lookup"><span data-stu-id="87dde-954">Then, on the **Versions** FastTab, select the configuration version that has a status of **Draft**.</span></span>
5. <span data-ttu-id="87dde-955">Válassza az **Állapot módosítása** \> **Teljes** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-955">Select **Change status** \> **Complete**.</span></span>

<span data-ttu-id="87dde-956">A konfiguráció 1.2. verziójának állapota **Piszkozatról** **Befejezett** értékre módosul.</span><span class="sxs-lookup"><span data-stu-id="87dde-956">The status of version 1.2 of this configuration is changed from **Draft** to **Completed**.</span></span> <span data-ttu-id="87dde-957">Az 1.2. verzió a későbbiekben már nem módosítható.</span><span class="sxs-lookup"><span data-stu-id="87dde-957">Version 1.2 can no longer be changed.</span></span> <span data-ttu-id="87dde-958">Ez a verzió tartalmazza a konfigurált modell-leképezést, és a többi ER-konfiguráció alapjaként használható.</span><span class="sxs-lookup"><span data-stu-id="87dde-958">This version contains the configured model mapping and can be used as the basis for other ER configurations.</span></span> <span data-ttu-id="87dde-959">A konfiguráció 1.3. változata létrejön **Piszkozat** állapottal.</span><span class="sxs-lookup"><span data-stu-id="87dde-959">Version 1.3 of this configuration is created and has a status of **Draft**.</span></span> <span data-ttu-id="87dde-960">Ezt a verziót a **Kérdőív** modell-leképezés módosításával szerkesztheti.</span><span class="sxs-lookup"><span data-stu-id="87dde-960">You can edit this version to adjust the **Questionnaire** model mapping.</span></span>

### <a name="modify-a-format"></a><a name="ModifyFormat"></a><span data-ttu-id="87dde-961">Formátum módosítása</span><span class="sxs-lookup"><span data-stu-id="87dde-961">Modify a format</span></span>

<span data-ttu-id="87dde-962">A konfigurált ER-formátum módosítható úgy, hogy a neve megjelenjen az ER-formátum futtatásakor létrehozott jelentés élőlábában.</span><span class="sxs-lookup"><span data-stu-id="87dde-962">You can modify the configured ER format so that its name is shown in the footer of a report that is generated when the ER format is run.</span></span>

#### <a name="add-a-new-format-element"></a><a name="AddFormatElement"></a><span data-ttu-id="87dde-963">Új formátumelem hozzáadása</span><span class="sxs-lookup"><span data-stu-id="87dde-963">Add a new format element</span></span>

1. <span data-ttu-id="87dde-964">Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.</span><span class="sxs-lookup"><span data-stu-id="87dde-964">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="87dde-965">A **Konfigurációk** oldalon, a konfigurációk bal oldali panelen található fájában bontsa ki a **Kérdőív modellje** elemet, majd válassza a **Jelentés a kérdőívről** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-965">On the **Configurations** page, in the configuration tree, expand **Questionnaire model**, and then select **Questionnaire report**.</span></span>
3. <span data-ttu-id="87dde-966">Válassza a **Tervező** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-966">Select **Designer**.</span></span>
4. <span data-ttu-id="87dde-967">A **Formátumtervező** lapon válassza a **Jelentés** gyökérelemet.</span><span class="sxs-lookup"><span data-stu-id="87dde-967">On the **Format designer** page, select the **Report** root item.</span></span>
5. <span data-ttu-id="87dde-968">A **Hozzáadás** lehetőséggel új beágyazott formátumelemet vehet fel a kiválasztott **Jelentés** gyökérelemhez.</span><span class="sxs-lookup"><span data-stu-id="87dde-968">Select **Add** to add a new nested format element for the selected **Report** root item.</span></span>
6. <span data-ttu-id="87dde-969">Válassza az **Excel\\Footer** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-969">Select **Excel\\Footer**.</span></span>
7. <span data-ttu-id="87dde-970">A **Név** mezőbe írja be a **Lábléc** szót.</span><span class="sxs-lookup"><span data-stu-id="87dde-970">In the **Name** field, enter **Footer**.</span></span>
8. <span data-ttu-id="87dde-971">Válassza a **Jelentés\Lábléc**, majd a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-971">Select **Report\Footer**, and then select **Add**.</span></span>
9. <span data-ttu-id="87dde-972">Válassza a **Text\\String** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-972">Select **Text\\String**.</span></span>

#### <a name="bind-the-added-format-element"></a><a name="BindAddedFormatElement"></a><span data-ttu-id="87dde-973">Hozzáadott formátumelem kötése</span><span class="sxs-lookup"><span data-stu-id="87dde-973">Bind the added format element</span></span>

1. <span data-ttu-id="87dde-974">A **Formátumtervező** oldal **Leképezés** lapján, a formátumok fájában válassza az aktív **Footer\\String** elemnél a **Receptúra szerkesztése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-974">On the **Format designer** page, on the **Mapping** tab, in the format tree, for the active **Footer\\String** element, select **Edit formula**.</span></span>
2. <span data-ttu-id="87dde-975">A receptúraszerkesztő **Receptúra** mezőjébe írja be a **CONCATENATE ("\&C\&10", FORMAT("Generated by'\%1' ER solution", model.ExecutionContext.FormatName))** képletet.</span><span class="sxs-lookup"><span data-stu-id="87dde-975">In the formula editor, in the **Formula** field, enter **CONCATENATE ("\&C\&10", FORMAT("Generated by'\%1' ER solution", model.ExecutionContext.FormatName))**.</span></span>
3. <span data-ttu-id="87dde-976">Válassza a **Mentés** gombot, majd zárja be a receptúraszerkesztőt.</span><span class="sxs-lookup"><span data-stu-id="87dde-976">Select **Save**, and close the formula editor.</span></span>
4. <span data-ttu-id="87dde-977">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-977">Select **Save**.</span></span>

<span data-ttu-id="87dde-978">A konfigurált formátum már módosult, így a rendszer a létrehozott jelentés láblécébe írja be a nevét, a **Footer\\String** elem használatával.</span><span class="sxs-lookup"><span data-stu-id="87dde-978">The configured format has now been modified so that its name will be entered in the footer of a generated report by using the **Footer\\String** element.</span></span>

![A Lábléc formátumelem hozzáadása a konfigurált formátumhoz az ER-művelettervezőben](./media/er-quick-start1-template-format-structure3.png)

#### <a name="complete-the-format-design"></a><a name="CompleteFormat2"></a><span data-ttu-id="87dde-980">A formátum kialakításának befejezése</span><span class="sxs-lookup"><span data-stu-id="87dde-980">Complete the format design</span></span>

1. <span data-ttu-id="87dde-981">Zárja be a **Formátumtervező** lapot.</span><span class="sxs-lookup"><span data-stu-id="87dde-981">Close the **Format designer** page.</span></span>
2. <span data-ttu-id="87dde-982">Ellenőrizze, hogy a **Konfigurációk** oldalon, a konfigurációkat tartalmazó fában a **Jelentés a kérdőívről** konfiguráció továbbra is be van jelölve.</span><span class="sxs-lookup"><span data-stu-id="87dde-982">On the **Configurations** page, in the configuration tree, make sure that the **Questionnaire report** configuration is still selected.</span></span> <span data-ttu-id="87dde-983">Ezután a **Verziók** gyorslapon válassza ki azt a konfigurációverziót, amelynek az állapota **Piszkozat**.</span><span class="sxs-lookup"><span data-stu-id="87dde-983">Then, on the **Versions** FastTab, select the configuration version that has a status of **Draft**.</span></span>
3. <span data-ttu-id="87dde-984">Válassza az **Állapot módosítása** \> **Teljes** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-984">Select **Change status** \> **Complete**.</span></span>

<span data-ttu-id="87dde-985">A konfiguráció 1.2. verziójának állapota **Piszkozatról** **Befejezett** értékre módosul.</span><span class="sxs-lookup"><span data-stu-id="87dde-985">The status of version 1.2 of this configuration is changed from **Draft** to **Completed**.</span></span> <span data-ttu-id="87dde-986">Az 1.2. verzió a későbbiekben már nem módosítható.</span><span class="sxs-lookup"><span data-stu-id="87dde-986">Version 1.2 can no longer be changed.</span></span> <span data-ttu-id="87dde-987">Ez a verzió tartalmazza a konfigurált formátumot, és a többi ER-konfiguráció alapjaként használható.</span><span class="sxs-lookup"><span data-stu-id="87dde-987">This version contains the configured format and can be used as the basis for other ER configurations.</span></span> <span data-ttu-id="87dde-988">A konfiguráció 1.3. változata létrejön **Piszkozat** állapottal.</span><span class="sxs-lookup"><span data-stu-id="87dde-988">Version 1.3 of this configuration is created and has a status of **Draft**.</span></span> <span data-ttu-id="87dde-989">Ezt a verziót a **Kérdőív** jelentés módosításával szerkesztheti.</span><span class="sxs-lookup"><span data-stu-id="87dde-989">You can edit this version to adjust the **Questionnaire** report.</span></span>

### <a name="run-a-format-from-the-application"></a><a name="RunFormatFromApp2"></a><span data-ttu-id="87dde-990">Formátum futtatása az alkalmazásból</span><span class="sxs-lookup"><span data-stu-id="87dde-990">Run a format from the application</span></span>

1. <span data-ttu-id="87dde-991">Lépjen a **Kérdőív** \> **Tervezés** \> **Kérdőívek jelentése (ER használatával)** részre.</span><span class="sxs-lookup"><span data-stu-id="87dde-991">Go to **Questionnaire** \> **Design** \> **Questionnaires report (powered by ER)**.</span></span>
2. <span data-ttu-id="87dde-992">A párbeszédpanel **Formátum leképezése** mezőjében válassza a **Kérdőívek jelentése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-992">In the dialog box, in the **Format mapping** field, select **Questionnaires report**.</span></span>
3. <span data-ttu-id="87dde-993">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-993">Select **OK**.</span></span>
4. <span data-ttu-id="87dde-994">Az **ER-paraméterek** párbeszédpanelén lévő **Belefoglalandó rekordok** gyorslapon adja meg a szűrőfeltételeket, hogy a rendszer csak az **SBCCrsExam** kérdőívet szerepeltesse.</span><span class="sxs-lookup"><span data-stu-id="87dde-994">In the **ER parameters** dialog box, on the **Records to include** FastTab, configure the filtering option so that only the **SBCCrsExam** questionnaire is included.</span></span>
5. <span data-ttu-id="87dde-995">A szűrési beállítás megerősítéséhez kattintson az **OK** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="87dde-995">Select **OK** to confirm the filtering option.</span></span>
6. <span data-ttu-id="87dde-996">A jelentés futtatásához válassza az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-996">Select **OK** to run the report.</span></span>
7. <span data-ttu-id="87dde-997">Tekintse meg a létrehozott jelentést Excel-formátumban.</span><span class="sxs-lookup"><span data-stu-id="87dde-997">Review the generated report in Excel format.</span></span>

<span data-ttu-id="87dde-998">Figyelje meg, hogy a létrehozott jelentés lábléce a létrehozásához használt ER-formátum nevét tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="87dde-998">Notice that the footer of the generated report contains the name of the ER format that was used to generate it.</span></span>

![A létrehozott jelentés Excel-formátumban](./media/er-quick-start1-report4.png)

### <a name="run-a-format-from-er"></a><a name="RunFormatFromER3"></a><span data-ttu-id="87dde-1000">Formátum futtatása az ER-ből</span><span class="sxs-lookup"><span data-stu-id="87dde-1000">Run a format from ER</span></span>

1. <span data-ttu-id="87dde-1001">Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.</span><span class="sxs-lookup"><span data-stu-id="87dde-1001">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="87dde-1002">A **Konfigurációk** oldalon, a konfigurációk bal oldali panelen található fájában bontsa ki a **Kérdőív modellje** elemet, majd válassza a **Jelentés a kérdőívről** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-1002">On the **Configurations** page, in the configuration tree, expand **Questionnaire model**, and then select **Questionnaire report**.</span></span>
3. <span data-ttu-id="87dde-1003">A Műveleti ablaktáblán kattintson a **Futtatás** elemre.</span><span class="sxs-lookup"><span data-stu-id="87dde-1003">On the Action Pane, select **Run**.</span></span>
4. <span data-ttu-id="87dde-1004">Az **Elektronikus jelentés paraméterei** párbeszédpanelén lévő **Belefoglalandó rekordok** gyorslapon adja meg a szűrőfeltételeket, hogy a rendszer csak az **SBCCrsExam** kérdőívet szerepeltesse.</span><span class="sxs-lookup"><span data-stu-id="87dde-1004">In the **Electronic report parameters** dialog box, on the **Records to include** FastTab, configure the filtering option so that only the **SBCCrsExam** questionnaire is included.</span></span>
5. <span data-ttu-id="87dde-1005">A szűrési beállítás megerősítéséhez kattintson az **OK** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="87dde-1005">Select **OK** to confirm the filtering option.</span></span>
6. <span data-ttu-id="87dde-1006">A jelentés futtatásához válassza az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-1006">Select **OK** to run the report.</span></span>
7. <span data-ttu-id="87dde-1007">Tekintse meg a létrehozott jelentést Excel-formátumban.</span><span class="sxs-lookup"><span data-stu-id="87dde-1007">Review the generated report in Excel format.</span></span>

<span data-ttu-id="87dde-1008">Figyelje meg, hogy a létrehozott jelentés lábléce nem tartalmazza a létrehozásához használt ER-formátum nevét, mivel az adatszerződési objektum nem lett átadva a futó modell-leképezésnek, amikor azt meghívta az ER-ből futtatott ER-formátum.</span><span class="sxs-lookup"><span data-stu-id="87dde-1008">Notice that the footer of the generated report doesn't contain the name of ER format that was used to generate it, because the data contract object wasn't passed to the running model mapping when it was called by the ER format that was run from ER.</span></span>

### <a name="configure-a-format-destination-for-on-screen-preview"></a><a name="ConfigureDestination"></a><span data-ttu-id="87dde-1009">Formátum célhelyének konfigurálása a képernyőn látható előzetes verzióból</span><span class="sxs-lookup"><span data-stu-id="87dde-1009">Configure a format destination for on-screen preview</span></span>

1. <span data-ttu-id="87dde-1010">Ugorjon a **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Elektronikus jelentéskészítési cél** részre.</span><span class="sxs-lookup"><span data-stu-id="87dde-1010">Go to **Organization administration** \> **Electronic reporting** \> **Electronic reporting destination**.</span></span>
2. <span data-ttu-id="87dde-1011">Az **Elektronikus jelentéskészítési cél** oldalon adjon meg egy célrekordot a konfigurált **Jelentés a kérdőívről** ER-formátumhoz.</span><span class="sxs-lookup"><span data-stu-id="87dde-1011">On the **Electronic reporting destination** page, add a destination record for the configured **Questionnaire report** ER format.</span></span>
3. <span data-ttu-id="87dde-1012">A **Fájl célja** gyorslapon állítsa be a **Képernyő** [célt](er-destination-type-screen.md) ahhoz a **Jelentés** formátum-összetevőhöz, amelyet [hozzáadott](#AddFormatRootElement) a konfigurált **Jelentés a kérdőívről** ER-formátum gyökérelemeként.</span><span class="sxs-lookup"><span data-stu-id="87dde-1012">On the **File destination** FastTab, set up the **Screen** [destination](er-destination-type-screen.md) for the **Report** format component that has been [added](#AddFormatRootElement) as the root element of the configured **Questionnaire report** ER format.</span></span>
4. <span data-ttu-id="87dde-1013">A **PDF-konverzió beállításai** gyorslapon konfigurálja a célhelyet a jelentés **Fekvő** tájolást használó [PDF-formátumra](electronic-reporting-destinations.md#OutputConversionToPDF) történő konvertálásához.</span><span class="sxs-lookup"><span data-stu-id="87dde-1013">On the **PDF conversion settings** FastTab, configure the destination to convert a report to [PDF format](electronic-reporting-destinations.md#OutputConversionToPDF) that uses the **Landscape** page orientation.</span></span>

![Az egyéni Képernyő cél konfigurálása az ER-formátumhoz az Elektronikus jelentéskészítés célja oldalon](./media/er-quick-start1-destination.png)

### <a name="run-a-format-from-the-application-to-preview-it-as-a-pdf-document"></a><a name="RunFormatFromApp3"></a><span data-ttu-id="87dde-1015">Formátum futtatása az alkalmazásból PDF-dokumentumként történő előzetes verzió készítéséhez</span><span class="sxs-lookup"><span data-stu-id="87dde-1015">Run a format from the application to preview it as a PDF document</span></span>

1. <span data-ttu-id="87dde-1016">Lépjen a **Kérdőív** \> **Tervezés** \> **Kérdőívek jelentése (ER használatával)** részre.</span><span class="sxs-lookup"><span data-stu-id="87dde-1016">Go to **Questionnaire** \> **Design** \> **Questionnaires report (powered by ER)**.</span></span>
2. <span data-ttu-id="87dde-1017">A párbeszédpanel **Formátum leképezése** mezőjében válassza a **Kérdőívek jelentése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-1017">In the dialog box, in the **Format mapping** field, select **Questionnaires report**.</span></span>
3. <span data-ttu-id="87dde-1018">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-1018">Select **OK**.</span></span>
4. <span data-ttu-id="87dde-1019">Az **Elektronikus jelentés paraméterei** párbeszédpanelén lévő **Belefoglalandó rekordok** gyorslapon adja meg a szűrőfeltételeket, hogy a rendszer csak az **SBCCrsExam** kérdőívet szerepeltesse.</span><span class="sxs-lookup"><span data-stu-id="87dde-1019">In the **Electronic report parameters** dialog box, on the **Records to include** FastTab, configure the filtering option so that only the **SBCCrsExam** questionnaire is included.</span></span>
5. <span data-ttu-id="87dde-1020">A szűrési beállítás megerősítéséhez kattintson az **OK** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="87dde-1020">Select **OK** to confirm the filtering option.</span></span>

    <span data-ttu-id="87dde-1021">A **Célok** gyorslapon figyelje meg, hogy a **Kimenet** mező értéke **Képernyő**.</span><span class="sxs-lookup"><span data-stu-id="87dde-1021">On the **Destinations** FastTab, notice that the **Output** field is set to **Screen**.</span></span> <span data-ttu-id="87dde-1022">Ha módosítani szeretné a konfigurált célt, válassza a **Módosítás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-1022">If you want to change the configured destination, select **Change**.</span></span>

    ![ER-jelentés konfigurált cél módosítását lehetővé tevő párbeszédpanelje futásidőben](./media/er-quick-start1-run-settings.png)

6. <span data-ttu-id="87dde-1024">A jelentés futtatásához válassza az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87dde-1024">Select **OK** to run the report.</span></span>
7. <span data-ttu-id="87dde-1025">Tekintse meg a létrehozott jelentést PDF-formátumban.</span><span class="sxs-lookup"><span data-stu-id="87dde-1025">Review the generated report in PDF format.</span></span>

    ![A létrehozott PDF-formátumú jelentés képernyőn látható előnézete](./media/er-quick-start1-preview-PDF.png)

## <a name="additional-resources"></a><a name="References"></a><span data-ttu-id="87dde-1027">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="87dde-1027">Additional resources</span></span>

- [<span data-ttu-id="87dde-1028">Elektronikus jelentések áttekintése</span><span class="sxs-lookup"><span data-stu-id="87dde-1028">Electronic Reporting overview</span></span>](general-electronic-reporting.md)
- [<span data-ttu-id="87dde-1029">Elektronikus jelentéskészítés képletének nyelve</span><span class="sxs-lookup"><span data-stu-id="87dde-1029">Electronic reporting formula language</span></span>](er-formula-language.md)
- [<span data-ttu-id="87dde-1030">Többnyelvű jelentések tervezése</span><span class="sxs-lookup"><span data-stu-id="87dde-1030">Design multilingual reports</span></span>](er-design-multilingual-reports.md)
- [<span data-ttu-id="87dde-1031">Elektronikus jelentéskészítési keretrendszer API</span><span class="sxs-lookup"><span data-stu-id="87dde-1031">ER framework API</span></span>](er-apis-app73.md)
- [<span data-ttu-id="87dde-1032">A CASE függvény</span><span class="sxs-lookup"><span data-stu-id="87dde-1032">CASE function</span></span>](er-functions-logical-case.md)
- [<span data-ttu-id="87dde-1033">A CONCATENATE függvény</span><span class="sxs-lookup"><span data-stu-id="87dde-1033">CONCATENATE function</span></span>](er-functions-text-concatenate.md)
- [<span data-ttu-id="87dde-1034">A DATETIMEFORMAT függvény</span><span class="sxs-lookup"><span data-stu-id="87dde-1034">DATETIMEFORMAT function</span></span>](er-functions-datetime-datetimeformat.md)
- [<span data-ttu-id="87dde-1035">A FILTER függvény</span><span class="sxs-lookup"><span data-stu-id="87dde-1035">FILTER function</span></span>](er-functions-list-filter.md)
- [<span data-ttu-id="87dde-1036">A FIRSTORNULL függvény</span><span class="sxs-lookup"><span data-stu-id="87dde-1036">FIRSTORNULL function</span></span>](er-functions-list-firstornull.md)
- [<span data-ttu-id="87dde-1037">A FORMAT függvény</span><span class="sxs-lookup"><span data-stu-id="87dde-1037">FORMAT function</span></span>](er-functions-text-format.md)
- [<span data-ttu-id="87dde-1038">Az IF függvény</span><span class="sxs-lookup"><span data-stu-id="87dde-1038">IF function</span></span>](er-functions-logical-if.md)
- [<span data-ttu-id="87dde-1039">Az ORDERBY függvény</span><span class="sxs-lookup"><span data-stu-id="87dde-1039">ORDERBY function</span></span>](er-functions-list-orderby.md)
- [<span data-ttu-id="87dde-1040">A SESSIONNOW függvény</span><span class="sxs-lookup"><span data-stu-id="87dde-1040">SESSIONNOW function</span></span>](er-functions-datetime-sessionnow.md)
