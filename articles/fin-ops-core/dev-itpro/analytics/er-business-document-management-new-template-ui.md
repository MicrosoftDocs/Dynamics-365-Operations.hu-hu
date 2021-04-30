---
title: Microsoft Office stílusú felhasználói felület az Üzleti dokumentumkezelés modulban
description: Ez a témakör elmagyarázza, hogyan lehet használni az új felhasználói felületet az Elektronikus jelentések (ER) keretrendszert az Üzleti dokumentumkezelő funkciójában.
author: v-anamir
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERBDWorkspace, ERBDParameters
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: v-anamir
ms.search.validFrom: 2019-08-01
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: e6c5081f71a18dfac83b7aea950395436b42f50e
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/13/2021
ms.locfileid: "5881036"
---
# <a name="microsoft-office-style-user-interface-in-business-document-management"></a><span data-ttu-id="d1742-103">Microsoft Office stílusú felhasználói felület az Üzleti dokumentumkezelés modulban</span><span class="sxs-lookup"><span data-stu-id="d1742-103">Microsoft Office-style user interface in Business document management</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d1742-104">Az Üzleti dokumentumkezelés lehetővé teszi az üzleti felhasználók számára, hogy a Microsoft 365 szolgáltatás vagy a megfelelő Microsoft Office asztali alkalmazások segítségével szerkesszék az üzleti dokumentumok sablonjait.</span><span class="sxs-lookup"><span data-stu-id="d1742-104">Business document management lets business users edit business document templates by using a Microsoft 365 service or the appropriate Microsoft Office desktop application.</span></span> <span data-ttu-id="d1742-105">A szerkesztések lehetnek tervezési változtatások vagy új telepítések, illetve a felhasználók hozzáadhatnak helyőrzőket, hogy a forráskód módosítása nélkül is hozzáadhatók legyenek további adatok.</span><span class="sxs-lookup"><span data-stu-id="d1742-105">Edits might include design changes or new deployments, or users might add placeholders to include additional data without having to change the source code.</span></span> <span data-ttu-id="d1742-106">Az üzleti dokumentumkezelés működésével kapcsolatos további tudnivalókat lásd: [Üzleti dokumentumkezelés – áttekintés.](er-business-document-management.md).</span><span class="sxs-lookup"><span data-stu-id="d1742-106">For more information about how to work with Business document management, see [Business document management overview](er-business-document-management.md).</span></span>

<span data-ttu-id="d1742-107">Az új felhasználói felület (UI) egyértelműbb és kényelmesebben használható.</span><span class="sxs-lookup"><span data-stu-id="d1742-107">The new user interface (UI) is clearer and more comfortable to use.</span></span> <span data-ttu-id="d1742-108">Az **Üzleti dokumentum** terület csak az aktuális szolgáltatóhoz rendelkezésre álló sablonokat jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="d1742-108">The **Business document** area shows only the templates that are available for the current provider.</span></span> <span data-ttu-id="d1742-109">Az előző felhasználói felületen a **Sablon** fül felsorolja az összes szolgáltató számára elérhető sablonokat.</span><span class="sxs-lookup"><span data-stu-id="d1742-109">In the previous UI, the **Template** tab listed all the templates that were available for any providers.</span></span> <span data-ttu-id="d1742-110">Emellett minden olyan sablont megjelenít, amelyet az azonos szerepkörű felhasználók létrehoztak és megszerkesztettek.</span><span class="sxs-lookup"><span data-stu-id="d1742-110">It also showed all the templates that were created and edited by any user who had the same role.</span></span>

<span data-ttu-id="d1742-111">Az **Új dokumentum** gomb használatával egy másik szolgáltató által biztosított elektronikus jelentési (ER) formátum konfigurációban létrehozhat és szerkeszthet egy sablont.</span><span class="sxs-lookup"><span data-stu-id="d1742-111">You can use the **New document** button to create and edit a template in an Electronic reporting (ER) format configuration that is provided by another provider.</span></span> <span data-ttu-id="d1742-112">Az ebben a témakörben szereplő példában a szolgáltató a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d1742-112">In the example in this topic, the provider is Microsoft.</span></span> <span data-ttu-id="d1742-113">Másik lehetőségként készíthet egy sablont az Excel-formátumban feltöltött saját sablonjából.</span><span class="sxs-lookup"><span data-stu-id="d1742-113">Alternatively, you can create a template by uploading your own template in Excel format.</span></span>


> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWAVQg]

<span data-ttu-id="d1742-114">Az [Új üzleti dokumentum létrehozása az Üzleti dokumentumkezelés](https://youtu.be/gAIYl-mM_pw) videó (lásd fent) megtalálható a [Finance and Operations lejátszási listán](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW): YouTube.</span><span class="sxs-lookup"><span data-stu-id="d1742-114">The [Create a new business document using Business document management](https://youtu.be/gAIYl-mM_pw) video (shown above) is included in the [Finance and Operations playlist](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) available on YouTube.</span></span>

## <a name="make-the-new-document-ui-in-business-document-management-available"></a><span data-ttu-id="d1742-115">Az új dokumentum kezelőfelület elérhetővé tétele az üzleti dokumentumkezelés modulban</span><span class="sxs-lookup"><span data-stu-id="d1742-115">Make the new document UI in Business document management available</span></span>

<span data-ttu-id="d1742-116">Ha azt szeretné, hogy a program az új dokumentum kezelőfelületet használja az üzleti dokumentumkezelés modulban, akkor be kell kapcsolni az **Office-szerű UI-élmény az üzleti Dokumentumkezelés számára** funkciót a **Funkciókezelés** munkaterületen.</span><span class="sxs-lookup"><span data-stu-id="d1742-116">To start to use the new document UI in Business document management, you must turn on the **Office-like UI experience for Business document management** feature in the **Feature management** workspace.</span></span>

<span data-ttu-id="d1742-117">Kövesse az alábbi lépéseket a funkció bekapcsolásához az összes jogi személynél.</span><span class="sxs-lookup"><span data-stu-id="d1742-117">Follow these steps to turn on this feature for all legal entities.</span></span>

1. <span data-ttu-id="d1742-118">A **Funkciókezelés** munkaterületen, az **Összes** lapon válassza ki a listán az **Office-szerű UI-élmény az üzleti Dokumentumkezelés számára** funkciót.</span><span class="sxs-lookup"><span data-stu-id="d1742-118">In the **Feature management** workspace, on the **All** tab, select the **Office-like UI experience for Business document management** feature in the list.</span></span>
2. <span data-ttu-id="d1742-119">Válassza az **Engedélyezés most** lehetőséget a kiválasztott funkció bekapcsolásához.</span><span class="sxs-lookup"><span data-stu-id="d1742-119">Select **Enable now** to turn on the selected feature.</span></span>
3. <span data-ttu-id="d1742-120">Az új funkció eléréséhez frissítse a lapot.</span><span class="sxs-lookup"><span data-stu-id="d1742-120">Refresh the page to access the new feature.</span></span>

## <a name="edit-templates-that-are-owned-by-other-providers"></a><span data-ttu-id="d1742-121">Más szolgáltatók tulajdonában lévő sablonok szerkesztése</span><span class="sxs-lookup"><span data-stu-id="d1742-121">Edit templates that are owned by other providers</span></span>

1. <span data-ttu-id="d1742-122">Az **Üzleti dokumentumkezelés** munkaterületen válassza az **Új dokumentum** elemet.</span><span class="sxs-lookup"><span data-stu-id="d1742-122">In the **Business document management** workspace, select **New document**.</span></span>

    ![Üzletidokumentum-kezelés munkaterület](./media/BDM_overview_new_template1.png)

2. <span data-ttu-id="d1742-124">A **Kiválasztás** fülön válassza ki a sablonként használni kívánt dokumentumot, majd válassza a **Dokumentum létrehozása** elemet.</span><span class="sxs-lookup"><span data-stu-id="d1742-124">On the **Select** tab, select the document to use as a template, and then select **Create document**.</span></span>

    ![Üzleti dokumentumok párbeszédpanel](./media/BDM_overview_new_template2.png)

3. <span data-ttu-id="d1742-126">Az új párbeszédpanelen, a **Cím** mezőben, módosítsa a címet szükség szerint.</span><span class="sxs-lookup"><span data-stu-id="d1742-126">In the new dialog box, in the **Title** field, change the title as you require.</span></span> <span data-ttu-id="d1742-127">A program az automatikusan létrehozott új ER-formátumkonfiguráció elnevezésére használja a címszöveget.</span><span class="sxs-lookup"><span data-stu-id="d1742-127">The title text is used to name the new ER format configuration that is automatically created.</span></span> <span data-ttu-id="d1742-128">A konfiguráció vázlatverziója (**Customer FTI report (GER) másolata**) tartalmazza a szerkesztett sablont, és az ER-formátum futtatásá lesz használva az aktuális felhasználóhoz.</span><span class="sxs-lookup"><span data-stu-id="d1742-128">The draft version of this configuration (**Customer FTI report (GER) Copy**) will contain the edited template and will be used to run this ER format for the current user.</span></span> <span data-ttu-id="d1742-129">A rendszer alap ER formátumból származó nem módosított eredeti sablon alapján futtatja ezt az ER formátumot bármely más felhasználó számára.</span><span class="sxs-lookup"><span data-stu-id="d1742-129">The original template from the base ER format configuration will be used to run this ER format for every other user.</span></span>
4. <span data-ttu-id="d1742-130">A **Név** mezőben módosítsa az automatikusan létrehozandó szerkeszthető sablon első verziójának nevét.</span><span class="sxs-lookup"><span data-stu-id="d1742-130">In the **Name** field, change the name of the first revision of the editable template that will be automatically created.</span></span>
5. <span data-ttu-id="d1742-131">A **Megjegyzés** mezőben módosítsa a szerkeszthető sablon automatikusan létrehozott verziójának megjegyzéseit.</span><span class="sxs-lookup"><span data-stu-id="d1742-131">In the **Comment** field, update the remarks for the revision of the editable template that will be automatically created.</span></span>
6. <span data-ttu-id="d1742-132">A szerkesztési folyamat kezdetének jóváhagyásához kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="d1742-132">Select **OK** to confirm the start of the editing process.</span></span>

    ![Dokumentum-létrehozás párbeszédpanel](./media/BDM_overview_new_template3.png)

<span data-ttu-id="d1742-134">Az **Új dokumentum** gomb lehetővé teszi, hogy egy másik szolgáltató által biztosított elektronikus jelentési (ER) formátum konfigurációban hozzunk létre és szerkesszünk egy sablont.</span><span class="sxs-lookup"><span data-stu-id="d1742-134">The **New document** button is used to create and edit a template in an ER format configuration that is provided by another provider.</span></span> <span data-ttu-id="d1742-135">Ebben a példában a szolgáltató a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d1742-135">In this example, the provider is Microsoft.</span></span> <span data-ttu-id="d1742-136">Az **Új dokumentum** elem kiválasztásakor az aktuális és más szolgáltatók által birtokolt összes sablon látható.</span><span class="sxs-lookup"><span data-stu-id="d1742-136">When you select **New document**, you can view all the templates that are owned by current and other providers.</span></span> <span data-ttu-id="d1742-137">Miután kiválasztja a sablont, szerkesztésre megnyílik.</span><span class="sxs-lookup"><span data-stu-id="d1742-137">After you select the template, it's opened for editing.</span></span> <span data-ttu-id="d1742-138">Ezt követően a szerkesztett sablon egy új, automatikusan létrejövő ER formátumkonfigurációban lesz tárolva.</span><span class="sxs-lookup"><span data-stu-id="d1742-138">The edited template will then be stored in a new ER format configuration that is automatically generated.</span></span>

## <a name="upload-a-template-that-uses-an-existing-excel-format"></a><span data-ttu-id="d1742-139">Meglévő Excel-formátumot használó sablon feltöltése</span><span class="sxs-lookup"><span data-stu-id="d1742-139">Upload a template that uses an existing Excel format</span></span>
<span data-ttu-id="d1742-140">A sablon feltöltése előtt kövesse ezeket a lépéseket, és adja meg a szükséges adatokat.</span><span class="sxs-lookup"><span data-stu-id="d1742-140">Follow these steps to provide required information before you upload a template.</span></span>

1. <span data-ttu-id="d1742-141">Az **Üzleti dokumentumkezelés** munkaterületen válassza az **Új dokumentum** elemet.</span><span class="sxs-lookup"><span data-stu-id="d1742-141">In the **Business document management** workspace, select **New document**.</span></span>

    ![Üzletidokumentum-kezelés munkaterület](./media/BDM_overview_new_template1.png)
    
2. <span data-ttu-id="d1742-143">Az **Új sablon létrehozása** lap **Feltöltés** fül **Sablon** fülén válassza a **Tallózás** lehetőséget, és válassza ki a sablonként használni kívánt Excel-fájlt.</span><span class="sxs-lookup"><span data-stu-id="d1742-143">On the **Create a new template** page, on the **Upload** tab, on the **Template** tab, select **Browse** to find and select the Excel file that you want to use as a template.</span></span> <span data-ttu-id="d1742-144">A **Sablon** szakasz **Cím** és **Leírás** mezőit a program automatikusan kitölti.</span><span class="sxs-lookup"><span data-stu-id="d1742-144">In the **Template** section, the **Title** and **Description** fields are automatically filled in.</span></span> <span data-ttu-id="d1742-145">Illetve meghatározza az automatikusan létrehozott új ER-formátum konfiguráció nevét és leírását.</span><span class="sxs-lookup"><span data-stu-id="d1742-145">They specify the name and description of the new ER format configuration that is automatically created.</span></span> <span data-ttu-id="d1742-146">Igény szerint módosíthatja ezeket a mezőket.</span><span class="sxs-lookup"><span data-stu-id="d1742-146">You can edit these fields as you require.</span></span>
3. <span data-ttu-id="d1742-147">A **Dokumentumtípus** szakaszban, a **Név** mezőben adja meg az üzleti dokumentum típusát.</span><span class="sxs-lookup"><span data-stu-id="d1742-147">In the **Document Type** section, in the **Name** field, specify the type of business document.</span></span> <span data-ttu-id="d1742-148">Ez az érték lesz használva a helyes adatforrás kereséséhez (azaz ER modellkonfiguráció).</span><span class="sxs-lookup"><span data-stu-id="d1742-148">This value will be used to search the correct data source (that is, the ER model configuration).</span></span>

    ![Sablon fül](./media/BDM_overview_new_UI_import_21.jpg)

4. <span data-ttu-id="d1742-150">Az **Adatforrás** fül **Szűrő** gyorslapján válassza a **Szűrő alkalmazása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d1742-150">On the **Data source** tab, on the **Filter** FastTab, select **Apply filter**.</span></span> <span data-ttu-id="d1742-151">Az **Adatforrás** szakaszban a rendszer automatikusan kitölti a **Név** mezőt, vagy manuálisan kiválaszthat egy értéket.</span><span class="sxs-lookup"><span data-stu-id="d1742-151">In the **Data source** section, the **Name** field is automatically filled in, or you can manually select a value.</span></span> <span data-ttu-id="d1742-152">A szűrő használatával név, leírás, ország/régiókód és üzleti dokumentumtípus szerint keresheti meg a megfelelő adatforrásnevet.</span><span class="sxs-lookup"><span data-stu-id="d1742-152">You can use the filter to search for the appropriate data source name by name, description, country/region code, and business document type.</span></span>

    ![Adatforrás fül](./media/BDM_overview_new_UI_import_31.jpg)
    
    > [!NOTE]
    > <span data-ttu-id="d1742-154">A **Szűrő** gyorslapot a helyes adatforrás kereséséhez használják (azaz ER modellkonfiguráció).</span><span class="sxs-lookup"><span data-stu-id="d1742-154">The **Filter** FastTab is used to search the correct data source (that is, the ER model configuration).</span></span> <span data-ttu-id="d1742-155">Az összes szűrőmező szerkesztésével megkeresheti a feltöltött dokumentumnak leginkább megfelelő adatforrást.</span><span class="sxs-lookup"><span data-stu-id="d1742-155">You can edit all filter fields to find the most appropriate data source for the document that you're uploading.</span></span>
    > 
    > <span data-ttu-id="d1742-156">A **Szűrő** gyorslap feltételeit **VAGY** feltételként használják.</span><span class="sxs-lookup"><span data-stu-id="d1742-156">The conditions on the **Filter** FastTab are used as **OR** conditions.</span></span>
    
5. <span data-ttu-id="d1742-157">Válassza a **Hozzárendelés** lap **Automatikus észlelés** elemét.</span><span class="sxs-lookup"><span data-stu-id="d1742-157">On the **Mapping** tab, select **Auto detect**.</span></span> <span data-ttu-id="d1742-158">A **Gyökér definíció** mezőt a rendszer automatikusan kitölti, vagy manuálisan kiválaszthat egy értéket.</span><span class="sxs-lookup"><span data-stu-id="d1742-158">The **Root definition** field is automatically filled in, or you can manually select a value.</span></span> <span data-ttu-id="d1742-159">Ezen a fülön a sablon és a modell elemeinek záró leképezése látható.</span><span class="sxs-lookup"><span data-stu-id="d1742-159">This tab shows the end mapping for the elements from the template and the model.</span></span>

    ![Leképezési fül](./media/BDM_overview_new_UI_import_41.jpg)
    
   > [!NOTE]
   > <span data-ttu-id="d1742-161">A **Sablonstruktúra** szakasz leképezése az adatforrás címkéinek vagy leírásának teljes egyezését használja a felhasználó nyelvén és a sablon cellanevében.</span><span class="sxs-lookup"><span data-stu-id="d1742-161">The mapping in the **Template structure** section uses the full match of the labels or descriptions in the data source in the user's language, and in the cell name in the template.</span></span>

6. <span data-ttu-id="d1742-162">Válassza a **Dokumentum létrehozása** lehetőséget, és erősítse meg, hogy létre szeretne hozni egy sablont, és el szeretné indítani a szerkesztési folyamatot.</span><span class="sxs-lookup"><span data-stu-id="d1742-162">Select **Create document** to confirm that you want to create a template and start the editing process.</span></span>

<span data-ttu-id="d1742-163">További tájékoztatás: [Üzleti dokumentumkezelés – áttekintés](er-business-document-management.md).</span><span class="sxs-lookup"><span data-stu-id="d1742-163">For more information, see [Business document management overview](er-business-document-management.md).</span></span>

<span data-ttu-id="d1742-164">Ha nincs szolgáltató az Elektronikus jelentéskészítésben, létrehozhat egyet.</span><span class="sxs-lookup"><span data-stu-id="d1742-164">If there isn't a provider in Electronic reporting, you can create one.</span></span> <span data-ttu-id="d1742-165">Ha nincs aktív szolgáltató, kiválaszthat és aktiválhat egyet.</span><span class="sxs-lookup"><span data-stu-id="d1742-165">If there's no active provider, you can select to activate one.</span></span>

- <span data-ttu-id="d1742-166">Szolgáltató létrehozásához módosítsa a szolgáltató nevét a **Név** mezőben, frissítse az új szolgáltató internetcímét az **Internetcím** mezőben, majd a megerősítéshez kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="d1742-166">To create a provider, change the name of the provider in the **Name** field, update the internet address of the new provider in the **Internet address** field, and select **OK** to confirm.</span></span>

    ![Új szolgáltató létrehozása a BDM-ben](./media/bdm_create_provider.png)
    
- <span data-ttu-id="d1742-168">A meglévő szolgáltató aktiválásához válassza ki a szolgáltató nevét a **Konfigurációszolgáltató** mezőben, és válassza az **OK** gombot, a szolgáltató aktiválásához.</span><span class="sxs-lookup"><span data-stu-id="d1742-168">To activate existing provider, choose the name of the provider in the **Configuration provider** field, and select **OK** to set provider as active.</span></span>

    ![Szolgáltató aktiválása a BDM-ben](./media/bdm_choose_provider.png)

> [!NOTE]
> <span data-ttu-id="d1742-170">Minden egyes BDM-sablon a konfiguráció szerzőjeként hivatkozik a szolgáltatóra.</span><span class="sxs-lookup"><span data-stu-id="d1742-170">Each BDM template refers to the provider as the author of the configuration.</span></span> <span data-ttu-id="d1742-171">Ezért van szükség egy aktív szolgáltatóra a sablonhoz.</span><span class="sxs-lookup"><span data-stu-id="d1742-171">This is why an active provider is required for the template.</span></span>

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
