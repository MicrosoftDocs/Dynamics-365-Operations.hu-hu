---
title: Üzleti dokumentumsablon szerkezetének frissítése
description: Ez a témakör azt mutatja be, hogyan lehet frissíteni egy üzleti dokumentumsablon szerkezetét az üzleti dokumentumkezelő funkció segítségével.
author: NickSelin
manager: AnnBe
ms.date: 11/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERBDWorkspace, ERBDParameters, ERBDTemplateEditor
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-12-01
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: cb0188e372b5f6275472cf040d10bb796eed1858
ms.sourcegitcommit: 95d2fc0fa7d17d3a96f7969f12c985b018b4ff94
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/12/2020
ms.locfileid: "4728089"
---
# <a name="update-the-structure-of-a-business-document-template"></a><span data-ttu-id="a56dc-103">Üzleti dokumentumsablon szerkezetének frissítése</span><span class="sxs-lookup"><span data-stu-id="a56dc-103">Update the structure of a business document template</span></span> 

[!include[banner](../includes/banner.md)]

<span data-ttu-id="a56dc-104">Az **Üzleti Dokumentumkezelés** sablonszerkesztő [Sablonszerkeze](er-business-document-management.md) paneljén módosíthatja az üzleti dokumentum sablonját [új mezők hozzáadásával](er-bdm-add-field-to-excel-template.md) egy sablonhoz a Microsoft Excel alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="a56dc-104">In the **Template structure** pane of the [Business document management](er-business-document-management.md) template editor, you can modify a business document template by [adding new fields](er-bdm-add-field-to-excel-template.md) to a template in Microsoft Excel.</span></span> <span data-ttu-id="a56dc-105">A program ezután automatikusan frissíti a sablon struktúráját Dynamics 365 Finance alkalmazásban, hogy az tükrözze a **Sablon szerkezete** ablaktáblán elvégzett változtatásokat.</span><span class="sxs-lookup"><span data-stu-id="a56dc-105">The structure of the template is then automatically updated in Dynamics 365 Finance, so that it reflects the changes that you made in the **Template structure** pane.</span></span>

<span data-ttu-id="a56dc-106">A sablonokat az Office 365 online funkció használatával is módosíthatja.</span><span class="sxs-lookup"><span data-stu-id="a56dc-106">You can also modify a template by using Office 365 online functionality.</span></span> <span data-ttu-id="a56dc-107">Hozzáadhat például egy új névvel ellátott elemet, például képet vagy alakzatot a szerkeszthető munkalapra.</span><span class="sxs-lookup"><span data-stu-id="a56dc-107">For example, you can add a new named item, such as a picture or shape, to the editable worksheet.</span></span> <span data-ttu-id="a56dc-108">Ebben az esetben a sablon szerkezete nem frissül automatikusan a Finance alkalmazásban, és a hozzáadott tétel nem jelenik meg a **Sablon szerkezete** ablaktáblán.</span><span class="sxs-lookup"><span data-stu-id="a56dc-108">In this case, the structure of the template isn't automatically updated in Finance, and the item that you added doesn't appear in the **Template structure** pane.</span></span> <span data-ttu-id="a56dc-109">A sablon struktúrájának manuális frissítése a Finance-ban a sablonszerkesztő lap **Szerkezet frissítése** lehetőségének kiválasztásával.</span><span class="sxs-lookup"><span data-stu-id="a56dc-109">Manually update the template structure in Finance by selecting **Update structure** on the template editor page.</span></span>

<span data-ttu-id="a56dc-110">Ha további tájékoztatást szeretne erről a funkcióról, hajtsa végre a következő példát.</span><span class="sxs-lookup"><span data-stu-id="a56dc-110">For more information about this feature, complete the following example.</span></span>

## <a name="example-update-the-structure-of-a-business-document-template"></a><span data-ttu-id="a56dc-111">Példa: Üzleti dokumentumsablon szerkezetének frissítése</span><span class="sxs-lookup"><span data-stu-id="a56dc-111">Example: Update the structure of a business document template</span></span>

<span data-ttu-id="a56dc-112">Ez a példa azt mutatja be, hogy a rendszergazda milyen módon frissítheti egy üzleti dokumentumsablon szerkezetét, miután a sablon módosult az Office Online szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="a56dc-112">This example shows how a system administrator can update the structure of a business document template in Finance after the template is modified in Office Online.</span></span> <span data-ttu-id="a56dc-113">A következő szakaszok a szóban forgó lépéseket mutatják be.</span><span class="sxs-lookup"><span data-stu-id="a56dc-113">The following sections explain the steps that are involved.</span></span>

### <a name="prepare-a-business-document-template-for-editing"></a><span data-ttu-id="a56dc-114">Üzleti dokumentum sablonjának előkészítése szerkesztésre</span><span class="sxs-lookup"><span data-stu-id="a56dc-114">Prepare a business document template for editing</span></span>

<span data-ttu-id="a56dc-115">Hajtsa végre a következő lépéseket az [Üzleti dokumentumkezelés áttekintése](er-business-document-management.md) részben.</span><span class="sxs-lookup"><span data-stu-id="a56dc-115">Complete the following procedures in [Business document management overview](er-business-document-management.md).</span></span>

1. [<span data-ttu-id="a56dc-116">ER-paraméterek konfigurálása</span><span class="sxs-lookup"><span data-stu-id="a56dc-116">Configure ER parameters</span></span>](er-business-document-management.md#configure-er-parameters)
2. [<span data-ttu-id="a56dc-117">ER-megoldások importálása</span><span class="sxs-lookup"><span data-stu-id="a56dc-117">Import ER solutions</span></span>](er-business-document-management.md#import-er-solutions)
3. [<span data-ttu-id="a56dc-118">Az Üzletidokumentum-kezelés engedélyezése</span><span class="sxs-lookup"><span data-stu-id="a56dc-118">Enable Business document management</span></span>](er-business-document-management.md#enable-business-document-management)
4. [<span data-ttu-id="a56dc-119">Paraméterek konfigurálása</span><span class="sxs-lookup"><span data-stu-id="a56dc-119">Configure parameters</span></span>](er-business-document-management.md#configure-parameters)

### <a name="edit-a-business-document-template"></a><span data-ttu-id="a56dc-120">Üzleti dokumentumsablonok szerkesztése</span><span class="sxs-lookup"><span data-stu-id="a56dc-120">Edit a business document template</span></span>

1. <span data-ttu-id="a56dc-121">Az **Üzleti dokumentumkezelés** munkaterületen válassza az **Új dokumentum** elemet.</span><span class="sxs-lookup"><span data-stu-id="a56dc-121">In the **Business document management** workspace, select **New document**.</span></span>
2. <span data-ttu-id="a56dc-122">Az **Új sablon létrehozása** lapon válassza ki a **Szabadszöveges számla (ER minta) (Excel)** sablont.</span><span class="sxs-lookup"><span data-stu-id="a56dc-122">On the **Create a new template** page, select the **Free text invoice (ER sample)(Excel)** template.</span></span>
3. <span data-ttu-id="a56dc-123">Válassza a **Dokumentum létrehozása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a56dc-123">Select **Create document**.</span></span>
4. <span data-ttu-id="a56dc-124">A **Cím** mezőbe írja be a következőt: **FTI minta Litware**.</span><span class="sxs-lookup"><span data-stu-id="a56dc-124">In the **Title** field, enter **FTI sample Litware**.</span></span>
5. <span data-ttu-id="a56dc-125">Válassza az **OK** lehetőséget egy új sablon létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="a56dc-125">Select **OK** to create the new template.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a56dc-126">Ha még nem jelentkezett be az Office Online-szolgáltatásba, akkor [az Office 365 bejelentkezési oldalára](er-business-document-management.md#frequently-asked-questions) lesz irányítva.</span><span class="sxs-lookup"><span data-stu-id="a56dc-126">If you haven't yet signed in to Office Online, you're [directed to the Office 365 sign-in page](er-business-document-management.md#frequently-asked-questions).</span></span> <span data-ttu-id="a56dc-127">A pénzügyi környezethez történő visszatéréshez kattintson a böngésző **Vissza** gombjára.</span><span class="sxs-lookup"><span data-stu-id="a56dc-127">To return to your Finance environment, select the **Back** button in your browser.</span></span>

    <span data-ttu-id="a56dc-128">Az új sablon szerkesztésre megnyílik az Excel Online beágyazott vezérlőben a sablonszerkesztő lapon.</span><span class="sxs-lookup"><span data-stu-id="a56dc-128">The new template is opened for editing in the Excel Online embedded control on the template editor page.</span></span>

<span data-ttu-id="a56dc-129">[![Üzleti dokumentumsablon szerkesztésének megkezdése az Üzleti dokumentumkezelő munkaterületen](./media/er-bdm-update-structure1.gif)](./media/er-bdm-update-structure1.gif)</span><span class="sxs-lookup"><span data-stu-id="a56dc-129">[![Using the Business document management workspace to start to edit a business document template](./media/er-bdm-update-structure1.gif)](./media/er-bdm-update-structure1.gif)</span></span>

### <a name="review-the-current-structure-of-the-editable-template"></a><span data-ttu-id="a56dc-130">A szerkeszthető sablon aktuális szerkezetének áttekintése</span><span class="sxs-lookup"><span data-stu-id="a56dc-130">Review the current structure of the editable template</span></span>

1. <span data-ttu-id="a56dc-131">Az Excel Online alkalmazásban a menüszalag **Nézet** lapján a **Megjelenítés** csoportban válassza ki a **Rácsvonalak** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a56dc-131">In Excel Online, on the ribbon, on the **View** tab, in the **Show** group, select **Gridlines**.</span></span>
2. <span data-ttu-id="a56dc-132">A szerkeszthető sablonban válassza ki a sablon címéhe fölött látható téglalapot.</span><span class="sxs-lookup"><span data-stu-id="a56dc-132">In the editable template, select the rectangle above the template title.</span></span> <span data-ttu-id="a56dc-133">Ez a téglalap egy **rptHeaderCompLogo** nevű kép.</span><span class="sxs-lookup"><span data-stu-id="a56dc-133">This rectangle is a picture that is named **rptHeaderCompLogo**.</span></span>
3. <span data-ttu-id="a56dc-134">Ha a **Sablon szerkezete** ablaktábla rejtett, válassza a **Szerkezet megjelenítése** elemet.</span><span class="sxs-lookup"><span data-stu-id="a56dc-134">If the **Template structure** pane is hidden, select **Show structure**.</span></span>
4. <span data-ttu-id="a56dc-135">A **Sablon szerkezete** ablaktáblán bontsa ki a **Jelentés \> Számla \> rptHeader \> rptHeaderPart1** elemet.</span><span class="sxs-lookup"><span data-stu-id="a56dc-135">In the **Template structure** pane, expand **Report \> Invoice \> rptHeader \> rptHeaderPart1**.</span></span>
5. <span data-ttu-id="a56dc-136">Figyelje meg, hogy a sablonstruktúra a Finance-ban, a **rptHeaderCompLogo** elem a **Jelentés \> Számla \> rptHeader \> rptHeaderPart1** származtatott elemeként jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="a56dc-136">Notice that, in the template structure in Finance, the **rptHeaderCompLogo** item is presented as a child item of **Report \> Invoice \> rptHeader \> rptHeaderPart1**.</span></span>

<span data-ttu-id="a56dc-137">[![Egy szerkeszthető sablon aktuális szerkezetének áttekintése az Üzleti dokumentumkezelés munkaterületen](./media/er-bdm-update-structure2.gif)](./media/er-bdm-update-structure2.gif)</span><span class="sxs-lookup"><span data-stu-id="a56dc-137">[![Using the Business document management workspace to review the current structure of an editable template](./media/er-bdm-update-structure2.gif)](./media/er-bdm-update-structure2.gif)</span></span>

### <a name="update-the-structure-of-a-business-document-template-by-deleting-a-picture"></a><span data-ttu-id="a56dc-138">Üzleti dokumentumsablon szerkezetének frissítése a kép törlésével</span><span class="sxs-lookup"><span data-stu-id="a56dc-138">Update the structure of a business document template by deleting a picture</span></span>

1. <span data-ttu-id="a56dc-139">Az Excel Online alkalmazásban a szerkeszthető sablonban válassza ki a **rptHeaderCompLogo** képet.</span><span class="sxs-lookup"><span data-stu-id="a56dc-139">In Excel Online, in the editable template, select the **rptHeaderCompLogo** picture.</span></span>
2. <span data-ttu-id="a56dc-140">Hajtsa végre a következő lépések egyikét, ha a szerkeszthető sablonból törölni szeretné a kijelölt képet:</span><span class="sxs-lookup"><span data-stu-id="a56dc-140">Follow one of these steps to delete the selected picture from the editable template:</span></span>

    - <span data-ttu-id="a56dc-141">Nyomja meg a **Delete** billentyűt billentyűzeten.</span><span class="sxs-lookup"><span data-stu-id="a56dc-141">Select the **Delete** key on your keyboard.</span></span>
    - <span data-ttu-id="a56dc-142">Jelölje ki és tartsa megnyomva a képet (vagy kattintson rá a jobb gombbal), majd válassza a **Kivágás** parancsot.</span><span class="sxs-lookup"><span data-stu-id="a56dc-142">Select and hold (or right-click) the picture, and then select **Cut**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a56dc-143">Az **rptHeaderCompLogo** elem jelenleg még mindig szerepel a Finance sablonstruktúrájában, még akkor is, ha a kép már nem szerepel az Excel-sablonban.</span><span class="sxs-lookup"><span data-stu-id="a56dc-143">The **rptHeaderCompLogo** item is currently still present in the template structure in Finance, even though the picture is no longer included in the Excel template.</span></span>

3. <span data-ttu-id="a56dc-144">Az Excel és a Finance szerkeszthető sablon struktúrájának szinkronizálásához válassza a **Struktúra frissítése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a56dc-144">Select **Update structure** to sync the structure of the editable template in Excel and Finance.</span></span>
4. <span data-ttu-id="a56dc-145">A **Sablon szerkezete** ablaktáblán bontsa ki a **Jelentés \> Számla \> rptHeader \> rptHeaderPart1** elemet.</span><span class="sxs-lookup"><span data-stu-id="a56dc-145">In the **Template structure** pane, expand **Report \> Invoice \> rptHeader \> rptHeaderPart1**.</span></span>
5. <span data-ttu-id="a56dc-146">Figyelje meg, hogy az **rptHeaderCompLogo** elem tétel már nem szerepel a Finance sablonstruktúrájában.</span><span class="sxs-lookup"><span data-stu-id="a56dc-146">Notice that the **rptHeaderCompLogo** item is no longer included in the template structure in Finance.</span></span>

<span data-ttu-id="a56dc-147">[![Üzleti dokumentumsablon egy képének törlése az Üzleti dokumentumkezelő munkaterületen](./media/er-bdm-update-structure3.gif)](./media/er-bdm-update-structure3.gif)</span><span class="sxs-lookup"><span data-stu-id="a56dc-147">[![Using the Business document management workspace to delete a picture from a business document template](./media/er-bdm-update-structure3.gif)](./media/er-bdm-update-structure3.gif)</span></span>

### <a name="update-the-structure-of-a-business-document-template-by-adding-a-picture"></a><span data-ttu-id="a56dc-148">Üzleti dokumentumsablon szerkezetének frissítése egy kép hozzáadásával</span><span class="sxs-lookup"><span data-stu-id="a56dc-148">Update the structure of a business document template by adding a picture</span></span>

1. <span data-ttu-id="a56dc-149">Az Excel Online alkalmazásban a menüszalag **Beszúrás** lapján az **Illusztrációk** csoportban válassza ki a **Kép** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a56dc-149">In Excel Online, on the ribbon, on the **Insert** tab, in the **Illustrations** group, select **Picture**.</span></span>
2. <span data-ttu-id="a56dc-150">Válassza ki a **Fájl kiválasztása** elemet , tallózzon a hozzáadni kívánt képhez, jelölje ki, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="a56dc-150">Select **Choose file**, browse to the image that you want to add, select it, and then select **OK**.</span></span>
3. <span data-ttu-id="a56dc-151">Válassza a **Beszúrás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a56dc-151">Select **Insert**.</span></span>
4. <span data-ttu-id="a56dc-152">Mozgassa az új képet, amíg az a megfelelő helyre nem kerül.</span><span class="sxs-lookup"><span data-stu-id="a56dc-152">Move the new picture until it's in the correct place.</span></span> <span data-ttu-id="a56dc-153">Alapértelmezés szerint az Excel nevezi el a képet.</span><span class="sxs-lookup"><span data-stu-id="a56dc-153">By default, Excel names the picture.</span></span> <span data-ttu-id="a56dc-154">Például kaphatja a **Kép 2** nevet.</span><span class="sxs-lookup"><span data-stu-id="a56dc-154">For example, it might name the picture **Picture 2**.</span></span>
5. <span data-ttu-id="a56dc-155">Az Excel és a Finance szerkeszthető sablon struktúrájának szinkronizálásához válassza a **Struktúra frissítése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a56dc-155">Select **Update structure** to sync the structure of the editable template in Excel and Finance.</span></span>
6. <span data-ttu-id="a56dc-156">A **Sablon szerkezete** ablaktáblán bontsa ki a **Jelentés \> Számla \> rptHeader \> rptHeaderPart1** elemet.</span><span class="sxs-lookup"><span data-stu-id="a56dc-156">In the **Template structure** pane, expand **Report \> Invoice \> rptHeader \> rptHeaderPart1**.</span></span>
7. <span data-ttu-id="a56dc-157">Figyelje meg, hogy az új kép immár elemként szerepel a Finance sablonstruktúrájában.</span><span class="sxs-lookup"><span data-stu-id="a56dc-157">Notice that the new picture is now included as an item in the template structure in Finance.</span></span>

<span data-ttu-id="a56dc-158">[![Üzleti dokumentumsablonhoz kép hozzáadása az Üzleti dokumentumkezelő munkaterületen](./media/er-bdm-update-structure4.gif)](./media/er-bdm-update-structure4.gif)</span><span class="sxs-lookup"><span data-stu-id="a56dc-158">[![Using the Business document management workspace to add a picture to a business document template](./media/er-bdm-update-structure4.gif)](./media/er-bdm-update-structure4.gif)</span></span>

## <a name="related-links"></a><span data-ttu-id="a56dc-159">Kapcsolódó hivatkozások</span><span class="sxs-lookup"><span data-stu-id="a56dc-159">Related links</span></span>

[<span data-ttu-id="a56dc-160">Elektronikus jelentéskészítés (ER) áttekintése</span><span class="sxs-lookup"><span data-stu-id="a56dc-160">Electronic reporting (ER) overview</span></span>](general-electronic-reporting.md)

[<span data-ttu-id="a56dc-161">Üzletidokumentum-kezelés – áttekintés</span><span class="sxs-lookup"><span data-stu-id="a56dc-161">Business document management overview</span></span>](er-business-document-management.md)
