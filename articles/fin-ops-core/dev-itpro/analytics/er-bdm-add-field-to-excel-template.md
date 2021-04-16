---
title: Új mezők hozzáadása üzleti dokumentum-sablonhoz a Microsoft Excel szolgáltatásban
description: Ez a témakör azt mutatja be, hogyan lehet új mezőket felvenni egy üzleti dokumentumsablonba a Microsoft Excel programban az üzleti dokumentumkezelő funkció segítségével.
author: NickSelin
ms.date: 11/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERBDWorkspace, ERBDParameters, ERBDTemplateEditor
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-10-01
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: 991fe4ea56a2726c5df835cfc90a390cef2d5df5
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5751130"
---
# <a name="add-new-fields-to-a-business-document-template-in-microsoft-excel"></a><span data-ttu-id="ca244-103">Új mezők hozzáadása üzleti dokumentum-sablonhoz a Microsoft Excel szolgáltatásban</span><span class="sxs-lookup"><span data-stu-id="ca244-103">Add new fields to a business document template in Microsoft Excel</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="ca244-104">Új mezőket hozzáadhat egy sablonhoz, amely a következő Microsoft Excel formátumú üzleti dokumentumok létrehozásához használatos.</span><span class="sxs-lookup"><span data-stu-id="ca244-104">You can add new fields to a template that is used to generate business documents in Microsoft Excel format.</span></span> <span data-ttu-id="ca244-105">Ezek a mezők olyan helyőrzőként adhatók hozzá, amelyekkel az alkalmazásból a létrehozott dokumentumokat a szükséges adatokkal ki lehet tölteni.</span><span class="sxs-lookup"><span data-stu-id="ca244-105">These fields can be added as placeholders that are used to fill generated documents with required information from the application.</span></span> <span data-ttu-id="ca244-106">Minden hozzáadott mező esetében megadhat egy kötést az adatforrásokhoz, amely meghatározza, hogy milyen alkalmazásadatok szerepeljenek a mezőben, ha a sablont az üzleti dokumentumok létrehozásához használják.</span><span class="sxs-lookup"><span data-stu-id="ca244-106">For every field that you add, you can also specify a binding to the data sources, to specify what application data will be entered in the field when the template is used to generate business documents.</span></span>

<span data-ttu-id="ca244-107">Ha további tájékoztatást szeretne erről a funkcióról, végezze el a példafeladatot ebben a témakörben.</span><span class="sxs-lookup"><span data-stu-id="ca244-107">To learn more about this feature, complete the example in this topic.</span></span> <span data-ttu-id="ca244-108">Ez a példa azt mutatja be, hogyan lehet módosítani egy sablont a létrejövő Szabadszöveges számlaűrlapok mezőinek kitöltéséhez.</span><span class="sxs-lookup"><span data-stu-id="ca244-108">This example shows how to update a template to fill in the fields in free text invoice forms that are generated.</span></span>

## <a name="configure-business-document-management-to-edit-templates"></a><span data-ttu-id="ca244-109">Az üzleti dokumentumkezelés modul konfigurálása sablonok szerkesztéséhez</span><span class="sxs-lookup"><span data-stu-id="ca244-109">Configure Business document management to edit templates</span></span>

<span data-ttu-id="ca244-110">Mivel az üzleti Dokumentumkezelés (BDM) az [Elektronikus jelentéskészítés (ER) áttekintése](general-electronic-reporting.md) keretrendszerén alapul, konfigurálnia kell a szükséges ER és BDM paramétereket, mielőtt elkezdené a munkát a BDM-mel.</span><span class="sxs-lookup"><span data-stu-id="ca244-110">Because Business document management (BDM) is built on top of the [Electronic reporting (ER) overview](general-electronic-reporting.md) framework, you must configure the required ER and BDM parameters before you can start to work with BDM.</span></span>

1.  <span data-ttu-id="ca244-111">Jelentkezzen be a Microsoft Dynamics 365 Finance példányára rendszeradminisztrátorként.</span><span class="sxs-lookup"><span data-stu-id="ca244-111">Sign in to the instance of Microsoft Dynamics 365 Finance as the system administrator.</span></span>
2.  <span data-ttu-id="ca244-112">Hajtsa végre a példa következő lépéseit az [üzleti Dokumentumkezelés – áttekintés](er-business-document-management.md) témakörben:</span><span class="sxs-lookup"><span data-stu-id="ca244-112">Complete the following steps of the example in the [Business document management overview](er-business-document-management.md) topic:</span></span>

    1.  <span data-ttu-id="ca244-113">Konfigurálja az ER-paramétereket.</span><span class="sxs-lookup"><span data-stu-id="ca244-113">Configure ER parameters.</span></span>
    2.  <span data-ttu-id="ca244-114">Kapcsolja be a BDM-et.</span><span class="sxs-lookup"><span data-stu-id="ca244-114">Turn on BDM.</span></span>

<span data-ttu-id="ca244-115">Most már elkezdheti használni a BDM-et az üzleti dokumentumok sablonjainak szerkesztéséhez.</span><span class="sxs-lookup"><span data-stu-id="ca244-115">You can now start to use BDM to edit business document templates.</span></span>

## <a name="import-er-solutions-that-contain-a-template"></a><span data-ttu-id="ca244-116">Sablont tartalmazó ER-megoldások importálása</span><span class="sxs-lookup"><span data-stu-id="ca244-116">Import ER solutions that contain a template</span></span>

<span data-ttu-id="ca244-117">Az ebben az eljárásban szereplő példa a hivatalosan közzétett ER megoldást használja.</span><span class="sxs-lookup"><span data-stu-id="ca244-117">The example in this procedure uses the officially published ER solution.</span></span> <span data-ttu-id="ca244-118">Az adott megoldás ER-konfigurációit importálnia kell a Finance aktuális példányába.</span><span class="sxs-lookup"><span data-stu-id="ca244-118">You must import the ER configurations of this solution into your current instance of Finance.</span></span>

<span data-ttu-id="ca244-119">A megoldás **Szabadszöveges számla (Excel)** ER formátumkonfigurációja Excel-formátumban tartalmazza az üzletidokumentum-sablont, amelyet a BDM-mel szerkeszthet.</span><span class="sxs-lookup"><span data-stu-id="ca244-119">The **Free text invoice (Excel)** ER format configuration of this solution contains the business document template in Excel format that can be edited by using BDM.</span></span> <span data-ttu-id="ca244-120">Importálja az adott ER formátumkonfiguráció legújabb verzióját a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásból.</span><span class="sxs-lookup"><span data-stu-id="ca244-120">Import the latest version of this ER format configuration from Microsoft Dynamics Lifecycle Service (LCS).</span></span> <span data-ttu-id="ca244-121">A program automatikusan importálja a megfelelő ER adatmodellt és az ER modell-leképezési konfigurációkat.</span><span class="sxs-lookup"><span data-stu-id="ca244-121">The corresponding ER data model and ER model mapping configurations will be imported automatically.</span></span>

<span data-ttu-id="ca244-122">Az ER-konfigurációk importálásának módjával kapcsolatos további tudnivalókat lásd: [Elektronikus jelentéskészítési konfigurációk életciklusainak kezelése](general-electronic-reporting-manage-configuration-lifecycle.md).</span><span class="sxs-lookup"><span data-stu-id="ca244-122">For more information about how to import ER configurations, see [Manage the ER configuration lifecycle](general-electronic-reporting-manage-configuration-lifecycle.md).</span></span>

![LCS Közös eszközök tára oldal](./media/BDM-AddFldExcel-LCS.png)

### <a name="edit-the-er-solution-template"></a><span data-ttu-id="ca244-124">Az ER megoldássablon szerkesztése</span><span class="sxs-lookup"><span data-stu-id="ca244-124">Edit the ER solution template</span></span>

1.  <span data-ttu-id="ca244-125">Az **Üzleti dokumentum kezelése** munkaterületre való hozzáféréssel rendelkező felhasználóként jelentkezzen be.</span><span class="sxs-lookup"><span data-stu-id="ca244-125">Sign in as a user who has access to the **Business document management** workspace.</span></span>
2.  <span data-ttu-id="ca244-126">Nyissa meg az **Üzletidokumentum-kezelés** munkaterületet.</span><span class="sxs-lookup"><span data-stu-id="ca244-126">Open the **Business document management** workspace.</span></span>

    ![Üzletidokumentum-kezelés munkaterület](./media/BDM-AddFldExcel-Workspace.png)

3.  <span data-ttu-id="ca244-128">A rácsban válassza ki a **Szabadszöveges számla (Excel)** sablonját.</span><span class="sxs-lookup"><span data-stu-id="ca244-128">In the grid, select the **Free text invoice (Excel)** template.</span></span>
4.  <span data-ttu-id="ca244-129">A jobb oldali ablakban válassza ki az **új sablon** elemet a kiválasztott sablonon alapuló új sablon létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="ca244-129">In the right pane, select **New template** to create a new template that is based on the selected template.</span></span>
5.  <span data-ttu-id="ca244-130">A **Cím** mezőbe írja be: **Szabadszöveges számla (Excel) Contoso** az új sablon címeként.</span><span class="sxs-lookup"><span data-stu-id="ca244-130">In the **Title** field, enter **Free text invoice (Excel) Contoso** as the title of the new template.</span></span>
6.  <span data-ttu-id="ca244-131">A szerkesztési folyamat kezdetének jóváhagyásához kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="ca244-131">Select **OK** to confirm the start of the editing process.</span></span>

<span data-ttu-id="ca244-132">Megjelenik a BDM sablonszerkesztő lap.</span><span class="sxs-lookup"><span data-stu-id="ca244-132">The BDM template editor page appears.</span></span> <span data-ttu-id="ca244-133">A kiválasztott sablont a Microsoft 365 segítségével online szerkesztheti a beágyazott vezérlőben.</span><span class="sxs-lookup"><span data-stu-id="ca244-133">You can use Microsoft 365 to edit the selected template online in the embedded control.</span></span>

![BDM-sablonszerkesztő lapja](./media/BDM-AddFldExcel-EditableTemplate.png)

### <a name="add-the-label-for-a-new-field-to-the-template"></a><span data-ttu-id="ca244-135">Új mező címkéjének hozzáadása a sablonhoz</span><span class="sxs-lookup"><span data-stu-id="ca244-135">Add the label for a new field to the template</span></span>

1.  <span data-ttu-id="ca244-136">A BDM-sablonszerkesztő lapon az Excel menüszalagjának **Nézet** lapján válassza a **Címsorok és rácsvonalak** jelölőnégyzeteket a szerkeszthető Excel-sablonnál.</span><span class="sxs-lookup"><span data-stu-id="ca244-136">On the BDM template editor page, on the Excel ribbon, on the **View** tab, select the **Headings and Gridlines** check boxes for the editable Excel template.</span></span>

    ![A címsorok és a rácsvonalak jelölőnégyzete be van jelölve.](./media/BDM-AddFldExcel-EditableTemplate2.png)

2.  <span data-ttu-id="ca244-138">Válassza a következő cellákat: **E8:F8**.</span><span class="sxs-lookup"><span data-stu-id="ca244-138">Select cells **E8:F8**.</span></span>
3.  <span data-ttu-id="ca244-139">Az Excel menüszalag **Kezdőlap** lapján jelölje be az **Egyesítés és középre igazítás** lehetőséget a kiválasztott cellák egyesítéséhez az új egyesített **E8:F8** cellába.</span><span class="sxs-lookup"><span data-stu-id="ca244-139">On the Excel ribbon, on the **Home** tab, select **Merge & Center** to merge the selected cells into a new merged **E8:F8** cell.</span></span>
4.  <span data-ttu-id="ca244-140">Az egyesített **E8:F8** cellában adja meg: **URL**.</span><span class="sxs-lookup"><span data-stu-id="ca244-140">In the merged cell **E8:F8**, enter **URL**.</span></span>
5.  <span data-ttu-id="ca244-141">Válassza ki az **E7:F7** egyesített cellát, válassza a **Formátummásolót**, majd válassza az egyesített **E8:F8** cellát, hogy ugyanúgy formázza, mint az egyesített **E7:F7** cellát.</span><span class="sxs-lookup"><span data-stu-id="ca244-141">Select merged cell **E7:F7**, select **Format painter**, and then select merged cell **E8:F8** to format it in the same way as merged cell **E7:F7**.</span></span>

    ![Új mező címkét hozzáadott a sablonhoz](./media/BDM-AddFldExcel-EditableTemplate3.png)

### <a name="format-the-template-to-reserve-space-for-a-new-field"></a><span data-ttu-id="ca244-143">A sablon formázása egy új mező számára fenntartott hellyel</span><span class="sxs-lookup"><span data-stu-id="ca244-143">Format the template to reserve space for a new field</span></span>

1.  <span data-ttu-id="ca244-144">A BDM sablonszerkesztő lapján válassza az egyesített **G8:H8** cellát.</span><span class="sxs-lookup"><span data-stu-id="ca244-144">On the BDM template editor page, select merged cell **G8:H8**.</span></span>
2.  <span data-ttu-id="ca244-145">Az Excel menüszalag **Kezdőlap** lapján jelölje be az **Egyesítés és középre igazítás** lehetőséget a kiválasztott cellák egyesítéséhez az új egyesített **G8:H8** cellába.</span><span class="sxs-lookup"><span data-stu-id="ca244-145">On the Excel ribbon, on the **Home** tab, select **Merge & Center** to merge the selected cells into a new merged **G8:H8** cell.</span></span>
3.  <span data-ttu-id="ca244-146">Válassza ki az **G7:H7** egyesített cellát, válassza a **Formátummásolót**, majd válassza az egyesített **G8:H8** cellát, hogy ugyanúgy formázza, mint az egyesített **G7:H7** cellát.</span><span class="sxs-lookup"><span data-stu-id="ca244-146">Select merged cell **G7:H7**, select **Format painter**, and then select merged cell **G8:H8** to format it in the same way as merged cell **G7:H7**.</span></span>

    ![Az új mező számára fenntartott hely](./media/BDM-AddFldExcel-EditableTemplate4.png)

4.  <span data-ttu-id="ca244-148">A **név** mezőben válassza ki: **CompanyInfo**.</span><span class="sxs-lookup"><span data-stu-id="ca244-148">In the **Name** box field, select **CompanyInfo**.</span></span>

    <span data-ttu-id="ca244-149">Az aktuális Excel-sablon **CompanyInfo**-tartománya minden olyan mezőt tartalmaz, amely a létrejövő Jelentés fejlécének kitöltéséhez használatos az aktuális vállalat, mint eladó fél adataival.</span><span class="sxs-lookup"><span data-stu-id="ca244-149">The **CompanyInfo** range of the current Excel template holds all the fields that are used to fill the header of a generated report with the details of the current company as a seller party.</span></span>

    ![Kijelölt CompanyInfo-tartomány](./media/BDM-AddFldExcel-SelectCompanyInfoRange.png)

### <a name="add-a-new-field-to-the-template"></a><span data-ttu-id="ca244-151">Új mező hozzáadása a sablonhoz</span><span class="sxs-lookup"><span data-stu-id="ca244-151">Add a new field to the template</span></span>

1.  <span data-ttu-id="ca244-152">Válassza ki a **BDM sablonszerkesztő** lapján a művelet ablaktáblán a **formátum megjelenítése** elemet.</span><span class="sxs-lookup"><span data-stu-id="ca244-152">On the **BDM template editor** page, on the Action Pane, select **Show format**.</span></span>
2.  <span data-ttu-id="ca244-153">Válassza a **Sablon szerkezete** ablaktábla **Hozzáadás** elemét.</span><span class="sxs-lookup"><span data-stu-id="ca244-153">In the **Template structure** pane, select **Add**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ca244-154">Módosítania kell a sablonnak azt a szakaszát, amelyet új mezőként szeretne használni.</span><span class="sxs-lookup"><span data-stu-id="ca244-154">You must adjust the section of the template that you want to use as a new field.</span></span> <span data-ttu-id="ca244-155">Ezt a módosítást már elvégezte az egyesített cella formázásával: **G8:H8**.</span><span class="sxs-lookup"><span data-stu-id="ca244-155">You already made this adjustment by formatting merged cell **G8:H8**.</span></span>

    ![Új mező hozzáadása a sablonhoz](./media/BDM-AddFldExcel-AddCell.png)

3.  <span data-ttu-id="ca244-157">Az **Excel\Cella** kiválasztásával új mezőt adhat hozzá a sablonban szereplő cellaként.</span><span class="sxs-lookup"><span data-stu-id="ca244-157">Select **Excel\Cell** to add a new field as a cell in the template.</span></span>

    <span data-ttu-id="ca244-158">Az **Excel\Range** kiválasztásával a sablonhoz új tartományt szeretne adhat hozzá.</span><span class="sxs-lookup"><span data-stu-id="ca244-158">You can select **Excel\Range** if you want to add a new range to the template.</span></span> <span data-ttu-id="ca244-159">A megadott tartomány több cellát is tartalmazhat.</span><span class="sxs-lookup"><span data-stu-id="ca244-159">The range that is entered can contain multiple cells.</span></span> <span data-ttu-id="ca244-160">Ezek a cellák később is hozzáadhatók.</span><span class="sxs-lookup"><span data-stu-id="ca244-160">You can add these cells later.</span></span>
    
    <span data-ttu-id="ca244-161">Figyelje meg, hogy a **CompanyInfo** sablonösszetevője automatikusan be van jelölve a **sablon szerkezete** ablaktáblában, mert ez a legmegfelelőbb fölérendelt összetevő az aktuális sablonszerkezetben a hozzáadni kívánt mező számára.</span><span class="sxs-lookup"><span data-stu-id="ca244-161">Notice that the **CompanyInfo** template component, is automatically selected in the **Template structure** pane, because it's the most suitable parent component in the current template structure for the field that you're adding.</span></span>
    
4.  <span data-ttu-id="ca244-162">Az **Excel-tartomány** mezőbe írja be: **CompanyURL_Value**.</span><span class="sxs-lookup"><span data-stu-id="ca244-162">In the **Excel range** field, enter **CompanyURL_Value**.</span></span>
5.  <span data-ttu-id="ca244-163">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ca244-163">Select **OK**.</span></span>

    ![A sablon struktúrájához hozzáadva a CompanyURL_Value mező](./media/BDM-AddFldExcel-EditableTemplate5.png)

6.  <span data-ttu-id="ca244-165">A **Sablon szerkezete** ablaktáblán válassza a három pont gombot (...), majd válassza a **kötések megjelenítése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ca244-165">In the **Template structure** pane, select the ellipsis button (...), and then select **Show bindings**.</span></span>

    ![Kiválasztott kötések megjelenítése](./media/BDM-AddFldExcel-ShowBindings.png)

    <span data-ttu-id="ca244-167">A **sablon szerkezete** ablaktábla most megjeleníti azokat az adatforrásokat, amelyek elérhetők a mögöttes ER formátumában.</span><span class="sxs-lookup"><span data-stu-id="ca244-167">The **Template structure** pane now shows the data sources that are available in the underlying ER format.</span></span>

7.  <span data-ttu-id="ca244-168">Válassza ki a **CompanyInfo_Value** mezőt olyan mezőként, amelyet a mögöttes ER formátum adatforrásához kíván kötni.</span><span class="sxs-lookup"><span data-stu-id="ca244-168">Select **CompanyInfo_Value** as the field that you plan to bind to a data source of the underlying ER format.</span></span>
8.  <span data-ttu-id="ca244-169">A **Sablon szerkezete** **Adatforrások** szakaszában bontsa ki a **Modell \> InvoiceBase \> CompanyInfo** elemet.</span><span class="sxs-lookup"><span data-stu-id="ca244-169">In the **Data sources** section of the **Template structure** pane, expand **Model \> InvoiceBase \> CompanyInfo**.</span></span>
9.  <span data-ttu-id="ca244-170">A **CompanyInfo** területen válassza ki a **WebsiteURI** elemet.</span><span class="sxs-lookup"><span data-stu-id="ca244-170">Under **CompanyInfo**, select the **WebsiteURI** item.</span></span>

    ![A WebsiteURI elem kiválasztva](./media/BDM-AddFldExcel-BindURL.png)

10. <span data-ttu-id="ca244-172">Válassza a **Bind** elemet.</span><span class="sxs-lookup"><span data-stu-id="ca244-172">Select **Bind**.</span></span>
11. <span data-ttu-id="ca244-173">Válassza a **Sablon szerkezete** ablaktáblában a **Mentés** elemet, majd zárja be a BDM-sablon szerkesztő lapját.</span><span class="sxs-lookup"><span data-stu-id="ca244-173">In the **Template structure** pane, select **Save**, and then close the BDM template editor page.</span></span>

<span data-ttu-id="ca244-174">Az **üzleti Dokumentumkezelés** munkaterületen a **Sablon** lap jobb oldali ablaktáblájában látható a frissített sablon.</span><span class="sxs-lookup"><span data-stu-id="ca244-174">In the **Business document management** workspace, the **Template** tab in the right pane shows the updated template.</span></span> <span data-ttu-id="ca244-175">A rácsban figyelje meg, hogy a szerkesztett sablon **állapot** mezője **Tervezet** állapotra módosult, és a **módosítás** mező már nem üres.</span><span class="sxs-lookup"><span data-stu-id="ca244-175">In the grid, notice that the **Status** field for the edited template has been changed to **Draft**, and the **Revision** field is no longer blank.</span></span> <span data-ttu-id="ca244-176">Ezek a módosítások azt jelentik, hogy a sablon szerkesztésének folyamata elindult.</span><span class="sxs-lookup"><span data-stu-id="ca244-176">These changes indicate that the process of editing this template has been started.</span></span>

![Szerkesztett sablon az üzleti Dokumentumkezelés munkaterületen](./media/BDM-AddFldExcel-Workspace2.png)

## <a name="review-company-settings"></a><span data-ttu-id="ca244-178">Vállalati beállítások felülvizsgálata</span><span class="sxs-lookup"><span data-stu-id="ca244-178">Review company settings</span></span>

1.  <span data-ttu-id="ca244-179">Nyissa meg a következőt: **Szervezeti adminisztráció \> Szervezetek \> Jogi személyek**.</span><span class="sxs-lookup"><span data-stu-id="ca244-179">Go to **Organization administration \> Organizations \> Legal entities**.</span></span>
2.  <span data-ttu-id="ca244-180">A **kapcsolattartási adatok** gyorslapon győződjön meg arról, hogy a vállalat URL-címe meg van adva.</span><span class="sxs-lookup"><span data-stu-id="ca244-180">On the **Contact information** FastTab, verify that the company URL is entered.</span></span>

![A jogi személyek oldalon megadott vállalati URL-cím](./media/BDM-AddFldExcel-CompanyInfo.png)

## <a name="generate-business-documents-to-test-the-updated-template"></a><span data-ttu-id="ca244-182">Üzleti dokumentumok létrehozása a frissített sablon teszteléséhez</span><span class="sxs-lookup"><span data-stu-id="ca244-182">Generate business documents to test the updated template</span></span>

1.  <span data-ttu-id="ca244-183">Az alkalmazásban változtassa meg a vállalatota **USMF** értékre, és lépjen a **Kinnlevőségek \> Számlák \> összes szabadszöveges számla** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="ca244-183">In the application, change the company to **USMF**, and go to **Accounts receivable \> Invoices \> All free text invoices**.</span></span>
2.  <span data-ttu-id="ca244-184">Válassza ki az **FTI-00000002** számlát, majd válassza a **Nyomtatáskezelő** parancsot.</span><span class="sxs-lookup"><span data-stu-id="ca244-184">Select invoice **FTI-00000002**, and then select **Print management**.</span></span>
3.  <span data-ttu-id="ca244-185">A bal oldali ablaktáblán bontsa ki a **Modul – Kinnlevőségek \> dokumentumok \> szabadszöveges számla** elemet.</span><span class="sxs-lookup"><span data-stu-id="ca244-185">In the left pane, expand **Module - accounts receivable \> Documents \> Free text invoice**.</span></span>
4.  <span data-ttu-id="ca244-186">A **Szabadszöveges számla** részben válassza az **Eredeti dokumentum** szintet a feldolgozáshoz szükséges számlahatókör megadásához.</span><span class="sxs-lookup"><span data-stu-id="ca244-186">Under **Free text invoice**, select the **Original document** level to specify the scope of invoices for processing.</span></span>
5.  <span data-ttu-id="ca244-187">A jobb oldali ablakban a **jelentés formátuma** mezőben válassza ki a **Szabadszöveges számla (Excel) contoso** sablonját a megadott dokumentum szintjén.</span><span class="sxs-lookup"><span data-stu-id="ca244-187">In the right pane, in the **Report format** field, select the **Free text invoice (Excel) Contoso** template for the specified document level.</span></span>

    ![A Szabadszöveges számla (Excel) contoso sablon kiválasztva](./media/BDM-AddFldExcel-PrintMngtSetting.png)

6.  <span data-ttu-id="ca244-189">Az **Esc** gombbal zárja be az aktuális lapot.</span><span class="sxs-lookup"><span data-stu-id="ca244-189">Press **Esc** to close the current page.</span></span>
7.  <span data-ttu-id="ca244-190">Válassza a **Nyomtatás \> Kiválasztott** elemet.</span><span class="sxs-lookup"><span data-stu-id="ca244-190">Select **Print \> Selected**.</span></span>
8.  <span data-ttu-id="ca244-191">Töltse le a létrejövő dokumentumot, és nyissa meg az Excel alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="ca244-191">Download the generated document, and open it in Excel.</span></span>

    ![Szabadszöveges számla Excelben](./media/BDM-AddFldExcel-PreviewReport.png)

<span data-ttu-id="ca244-193">A módosított sablon a szabadszöveges számlajelentés generálására szolgál a kiválasztott tételhez.</span><span class="sxs-lookup"><span data-stu-id="ca244-193">The modified template is used to generate the free text invoice report for the selected item.</span></span> <span data-ttu-id="ca244-194">Annak elemzéséhez, hogy milyen hatással vannak a sablonon végzett módosításai erre a jelentésre, futtassa ezt a jelentést azonnal egy alkalmazás-munkamenetben, közvetlenül azután, hogy módosította egy alkalmazásmunkamenetben.</span><span class="sxs-lookup"><span data-stu-id="ca244-194">To analyze how this report is affected by changes that you make to the template, run the report in one application session immediately after you change the template in another application session.</span></span>

## <a name="related-links"></a><span data-ttu-id="ca244-195">Kapcsolódó hivatkozások</span><span class="sxs-lookup"><span data-stu-id="ca244-195">Related links</span></span>

[<span data-ttu-id="ca244-196">Elektronikus jelentéskészítés (ER) áttekintése</span><span class="sxs-lookup"><span data-stu-id="ca244-196">Electronic reporting (ER) overview</span></span>](general-electronic-reporting.md)

[<span data-ttu-id="ca244-197">Üzletidokumentum-kezelés – áttekintés</span><span class="sxs-lookup"><span data-stu-id="ca244-197">Business document management overview</span></span>](er-business-document-management.md)

[<span data-ttu-id="ca244-198">Az OPENXML formátumban létrejövő jelentésekre vonatkozó konfigurációk tervezése</span><span class="sxs-lookup"><span data-stu-id="ca244-198">Design a configuration for generating reports in OPENXML format</span></span>](tasks/er-design-reports-openxml-2016-11.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]