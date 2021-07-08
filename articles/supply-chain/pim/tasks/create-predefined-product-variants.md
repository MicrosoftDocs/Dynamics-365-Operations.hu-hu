---
title: Az előre meghatározott termékváltozatok létrehozása
description: Ez az eljárás bemutatja az alaptermék termékváltozatainak a termékdimenziók kombinációjának használatával történő létrehozását.
author: t-benebo
ms.date: 04/22/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductListPage, EcoResProductCreate, EcoResProductDetails, EcoResProductMasterDimension, EcoResProductVariants, EcoResProductVariantSuggestions, EcoResProductVariantsPendingReleaseFormPart, EcoResProductVariantSuggestionsEnhanced
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 442a5f5b321833c170cfecc4069e62a1254605cd
ms.sourcegitcommit: dc4898aa32f381620c517bf89c7856e693563ace
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/17/2021
ms.locfileid: "6270480"
---
# <a name="predefined-product-variants"></a><span data-ttu-id="95a62-103">Előre meghatározott termékváltozatok</span><span class="sxs-lookup"><span data-stu-id="95a62-103">Predefined product variants</span></span>

[!include [banner](../../includes/banner.md)]

## <a name="example-scenario-create-predefined-product-variants"></a><span data-ttu-id="95a62-104">Példaforgatókönyv: Az előre meghatározott termékváltozatok létrehozása</span><span class="sxs-lookup"><span data-stu-id="95a62-104">Example scenario: Create predefined product variants</span></span>

<span data-ttu-id="95a62-105">Ez az példaforgatókönyv bemutatja az alaptermék termékváltozatainak a termékdimenziók kombinációjának használatával történő létrehozását.</span><span class="sxs-lookup"><span data-stu-id="95a62-105">This example scenario shows how to create product variants for a product master using a combinations of product dimensions.</span></span>

### <a name="make-demo-data-available"></a><span data-ttu-id="95a62-106">A bemutató adatok elérhetővé tétele</span><span class="sxs-lookup"><span data-stu-id="95a62-106">Make demo data available</span></span>

<span data-ttu-id="95a62-107">A jelen forgatókönyv itt javasolt értékekkel való követéséhez a demóadatokat kell telepíteni, és az *USMF* demó jogi személyt kell használnia.</span><span class="sxs-lookup"><span data-stu-id="95a62-107">To follow this scenario using the values suggested here, you must have demo data installed, and you must select the *USMF* legal entity.</span></span>

### <a name="step-1-create-a-product-master"></a><span data-ttu-id="95a62-108">1. lépés: Alaptermék létrehozása</span><span class="sxs-lookup"><span data-stu-id="95a62-108">Step 1: Create a product master</span></span>

<span data-ttu-id="95a62-109">Alaptermék létrehozásához:</span><span class="sxs-lookup"><span data-stu-id="95a62-109">To create a product master:</span></span>

1. <span data-ttu-id="95a62-110">Ugorjon a **Termékinformációk kezelése > Termékek > Alaptermékek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="95a62-110">Go to **Product information management > Products > Product masters**.</span></span>
1. <span data-ttu-id="95a62-111">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="95a62-111">Select **New**.</span></span>
1. <span data-ttu-id="95a62-112">Ha a **Termékszám** mezőben még nem létezik szám, adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="95a62-112">If the **Product number** field doesn't already show a number, then enter a value.</span></span> <span data-ttu-id="95a62-113">Ez csak akkor szükséges, ha nem lett számsorozat beállítva ehhez a mezőhöz.</span><span class="sxs-lookup"><span data-stu-id="95a62-113">This is only required if no number sequence has been set for this field.</span></span>
1. <span data-ttu-id="95a62-114">A **Termék neve** mezőbe írjon be egy nevet.</span><span class="sxs-lookup"><span data-stu-id="95a62-114">Enter a name in the **Product name** field.</span></span>
1. <span data-ttu-id="95a62-115">A **Termékdimenzió-csoport** mezőben válassza ki a *SizeCol* (Méret és Szín) termékdimenzió-csoportot.</span><span class="sxs-lookup"><span data-stu-id="95a62-115">In the **Product dimension group** field, select the product dimension group *SizeCol* (Size and Color).</span></span>
1. <span data-ttu-id="95a62-116">Az új alaptermék létrehozásához és megnyitásához kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="95a62-116">Select **OK** to create and open the new product master.</span></span>

### <a name="step-2-add-product-dimensions"></a><span data-ttu-id="95a62-117">2. lépés: Termékdimenziók hozzáadása</span><span class="sxs-lookup"><span data-stu-id="95a62-117">Step 2: Add product dimensions</span></span>

<span data-ttu-id="95a62-118">Ez a példa bemutatja, hogy hogyan lehet manuálisan megadni a termékdimenziókat.</span><span class="sxs-lookup"><span data-stu-id="95a62-118">This example shows how to manually enter product dimensions.</span></span> <span data-ttu-id="95a62-119">Arra is lehetősége van, hogy kiválassza a méretet, a színt és a stíluscsoportot, amely a használni kívánt termékdimenzió értékeket tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="95a62-119">You can also choose to select a size, color, or style group that includes the product dimension values you want to use.</span></span>

<span data-ttu-id="95a62-120">Termékdimenziók hozzáadásához:</span><span class="sxs-lookup"><span data-stu-id="95a62-120">To add product dimensions:</span></span>

1. <span data-ttu-id="95a62-121">Ha az új alaptermék még nyitva marad, válassza ki a **Termékdimenziókat** a műveleti ablaktáblán.</span><span class="sxs-lookup"><span data-stu-id="95a62-121">With your new product master still open, select **Product dimensions** on the Action Pane.</span></span>
1. <span data-ttu-id="95a62-122">Ha új sort szeretne felvenni a rácsba, nyissa meg a **Méret** lapot, és válassza az eszköztár **Új** gombját.</span><span class="sxs-lookup"><span data-stu-id="95a62-122">Open the **Size** tab and select **New** on the toolbar to add a row to the grid.</span></span> <span data-ttu-id="95a62-123">Az új sorhoz állítsa be a következőket:</span><span class="sxs-lookup"><span data-stu-id="95a62-123">Make the following settings for the new row:</span></span>
    - <span data-ttu-id="95a62-124">**Méret:** Válasszon egy méretértéket.</span><span class="sxs-lookup"><span data-stu-id="95a62-124">**Size:** Select a size value.</span></span>
    - <span data-ttu-id="95a62-125">**Név:** Adjon meg egy nevet a méretnek.</span><span class="sxs-lookup"><span data-stu-id="95a62-125">**Name:** Enter a name for the size.</span></span>
1. <span data-ttu-id="95a62-126">Válassza az eszköztár **Új** gombját, és adjon hozzá egy második méretet a rácshoz egy új **Méret** és **Név** használatával.</span><span class="sxs-lookup"><span data-stu-id="95a62-126">Select **New** on the toolbar and add a second size to the grid with a new **Size** and **Name**.</span></span>
1. <span data-ttu-id="95a62-127">Ha új sort szeretne felvenni a rácsba, nyissa meg a **Színek** lapot, és válassza az eszköztár **Új** gombját.</span><span class="sxs-lookup"><span data-stu-id="95a62-127">Open the **Colors** tab and select **New** on the toolbar to add a row to the grid.</span></span> <span data-ttu-id="95a62-128">Az új sorhoz állítsa be a következőket:</span><span class="sxs-lookup"><span data-stu-id="95a62-128">Make the following settings for the new row:</span></span>
    - <span data-ttu-id="95a62-129">**Szín:** Válasszon egy színértéket.</span><span class="sxs-lookup"><span data-stu-id="95a62-129">**Color:** Select a color value.</span></span>
    - <span data-ttu-id="95a62-130">**Név:** Adjon meg egy nevet a színnek.</span><span class="sxs-lookup"><span data-stu-id="95a62-130">**Name:** Enter a name for the color.</span></span>
1. <span data-ttu-id="95a62-131">Válassza az eszköztár **Új** gombját, és adjon hozzá egy második színt a rácshoz egy új **Szín** és **Név** használatával.</span><span class="sxs-lookup"><span data-stu-id="95a62-131">Select **New** on the toolbar and add a second color to the grid with a new **Color** and **Name**.</span></span>
1. <span data-ttu-id="95a62-132">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="95a62-132">Select **Save**.</span></span>
1. <span data-ttu-id="95a62-133">Az új alaptermékhez való visszatéréshez zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="95a62-133">Close the page to return to your new product master.</span></span>

### <a name="step-3-generate-product-variants"></a><span data-ttu-id="95a62-134">3. lépés: Termékváltozatok létrehozása</span><span class="sxs-lookup"><span data-stu-id="95a62-134">Step 3: Generate product variants</span></span>

> [!NOTE]
> <span data-ttu-id="95a62-135">Ez a szakasz azt írja le, hogyan lehet termékváltozatokat generálni, ha nincs engedélyezve a *Változatjavaslatok oldal javításai* funkció.</span><span class="sxs-lookup"><span data-stu-id="95a62-135">This section describes how to generate product variants when the *Variant suggestions page improvements* feature isn't enabled.</span></span> <span data-ttu-id="95a62-136">A következő szakaszban arról olvashat részletesen, hogy hogyan lehet termékváltozatokat generálni, ha ez a funkció elérhető.</span><span class="sxs-lookup"><span data-stu-id="95a62-136">See the next section for details about how to generate product variants when that feature is available.</span></span>

<span data-ttu-id="95a62-137">Termékváltozatok létrehozásához:</span><span class="sxs-lookup"><span data-stu-id="95a62-137">To generate product variants:</span></span>

1. <span data-ttu-id="95a62-138">Ha az új alaptermék még nyitva marad, válassza ki a **Termékváltozatokat** a műveleti ablaktáblán.</span><span class="sxs-lookup"><span data-stu-id="95a62-138">With your new product master still open, select **Product variants** on the Action Pane.</span></span>
1. <span data-ttu-id="95a62-139">A Műveleti ablaktáblán válassza ki a **Változatjavaslatok** elemet.</span><span class="sxs-lookup"><span data-stu-id="95a62-139">Select **Variant suggestions** on the Action Pane.</span></span>
1. <span data-ttu-id="95a62-140">A rendszer listát generál a termékhez megadott méretek és színek összes lehetséges kombinációjáról.</span><span class="sxs-lookup"><span data-stu-id="95a62-140">The system generates a list with all possible combinations of the sizes and colors you defined for the product.</span></span> <span data-ttu-id="95a62-141">Válassza at **Összes kijelölése** elemet az eszköztáron.</span><span class="sxs-lookup"><span data-stu-id="95a62-141">Select **Select all** on the toolbar.</span></span>
    - <span data-ttu-id="95a62-142">Az alábbi példában válassza ki az összes lehetséges változatot.</span><span class="sxs-lookup"><span data-stu-id="95a62-142">In this example, select all of the possible variants.</span></span> <span data-ttu-id="95a62-143">Ha csak a lehetséges termékdimenzió-kombinációk egy részhalmazát szeretné használni, csak a szükséges jelölőnégyzeteket jelölje be.</span><span class="sxs-lookup"><span data-stu-id="95a62-143">If you only want to use a subset of the possible product dimension combinations, select only the required check boxes as needed.</span></span>  
1. <span data-ttu-id="95a62-144">Válassza a **Létrehozása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="95a62-144">Select **Create**.</span></span>
1. <span data-ttu-id="95a62-145">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="95a62-145">Select **Save**.</span></span>

## <a name="improved-variant-suggestions"></a><span data-ttu-id="95a62-146">Továbbfejlesztett változatjavaslatok</span><span class="sxs-lookup"><span data-stu-id="95a62-146">Improved variant suggestions</span></span>

<span data-ttu-id="95a62-147">A *Változatjavaslatok oldal javításai* funkció javítja a **Változatjavaslatok** oldalt, így reagálva az olyan vállalatok teljesítmény- és használhatósági problémáira, amelyek nagy számú termékdimenzió-kombinációt használnak.</span><span class="sxs-lookup"><span data-stu-id="95a62-147">The *Variant suggestions page improvements* feature improves the **Variant suggestions** page to address performance and usability issues for companies that have a high number of product dimension combinations.</span></span> <span data-ttu-id="95a62-148">Az olyan termékdimenzió-értékek kiválasztásának továbbfejlesztett folyamata, amelyekhez változatjavaslatokat kell létrehozni, felgyorsítja és megkönnyíti a termékváltozatok releváns halmazának beazonosítását és kiadását.</span><span class="sxs-lookup"><span data-stu-id="95a62-148">The enhanced process for selecting the product dimension values for which to generate variant suggestions makes it faster and easier to identify and release the relevant set of product variants.</span></span>

<span data-ttu-id="95a62-149">Ez a funkció a következő fejlesztéseket biztosítja:</span><span class="sxs-lookup"><span data-stu-id="95a62-149">The following improvements are added by this feature:</span></span>

- <span data-ttu-id="95a62-150">**Változatjavaslatok késleltetett létrehozása:** A **Változatjavaslatok** oldal már nem jelenít meg javaslatokat az első megnyitáskor.</span><span class="sxs-lookup"><span data-stu-id="95a62-150">**Deferred generation of variant suggestions:** The **Variant suggestions** page no longer shows suggestions when you first open it.</span></span> <span data-ttu-id="95a62-151">Ehelyett explicit módon ki kell választania, hogy milyen értékekre lesz szüksége, majd a kombinációk létrehozásához kattintson a **Javaslat** gombra.</span><span class="sxs-lookup"><span data-stu-id="95a62-151">Instead, you must explicitly choose which values you will need and then select the **Suggest** button to generate the combinations.</span></span> <span data-ttu-id="95a62-152">Így a folyamat láthatóvá és interaktívvá válik.</span><span class="sxs-lookup"><span data-stu-id="95a62-152">This makes the process more visible and interactive.</span></span>
- <span data-ttu-id="95a62-153">**Dimenzióértékek kiválasztása**: Ha sok dimenzióértékkel rendelkezik, akkor általában csak néhányat tartalmazó változatjavaslatok létrehozása szükséges az Ön számára (például amikor új színeket vagy stílusokat vezet be).</span><span class="sxs-lookup"><span data-stu-id="95a62-153">**Selection of dimensions values:** When you have many dimension values, you are typically interested in generating variant suggestions that include just a few of them (such as when introducing a new set of colors or styles).</span></span> <span data-ttu-id="95a62-154">A továbbfejlesztett kialakítással kiválaszthatja azokat a dimenzióértékeket, amelyekhez termékváltozat-javaslatokat szeretne létrehozni.</span><span class="sxs-lookup"><span data-stu-id="95a62-154">With the improved design, you can select the dimension values for which you want to generate product variant suggestions.</span></span> <span data-ttu-id="95a62-155">Ez nagy mértékben növeli a javasolt változatok relevanciáját, és javítja a rendszer teljesítményét és a felhasználói hatékonyságot.</span><span class="sxs-lookup"><span data-stu-id="95a62-155">This greatly increases the relevance of the suggested variants and improves both system performance and user productivity.</span></span>

### <a name="turn-on-the-variant-suggestions-page-improvements-feature"></a><span data-ttu-id="95a62-156">A Változatjavaslatok oldal javításai funkció bekapcsolása</span><span class="sxs-lookup"><span data-stu-id="95a62-156">Turn on the Variant suggestions page improvements feature</span></span>

<span data-ttu-id="95a62-157">A *Változatjavaslatok oldal javításai* funkció használata előtt be kell kapcsolni azt a rendszerben.</span><span class="sxs-lookup"><span data-stu-id="95a62-157">Before you can use *Variant suggestions page improvements* feature, it must be turned on in your system.</span></span> <span data-ttu-id="95a62-158">A rendszergazdák használhatják a [funkciókezelési](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) beállításokat a funkció állapotának ellenőrzéséhez, és bekapcsolásához.</span><span class="sxs-lookup"><span data-stu-id="95a62-158">Admins can use the [feature management](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on.</span></span> <span data-ttu-id="95a62-159">A **Funkció kezelése** munkaterületen a funkció a következő módon van listázva:</span><span class="sxs-lookup"><span data-stu-id="95a62-159">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="95a62-160">**Modul:** *Termékinformáció-kezelés*</span><span class="sxs-lookup"><span data-stu-id="95a62-160">**Module:** *Product information management*</span></span>
- <span data-ttu-id="95a62-161">**Funkciónév:** *Változatjavaslatok oldal javításai*</span><span class="sxs-lookup"><span data-stu-id="95a62-161">**Feature name:** *Variant suggestions page improvements*</span></span>

### <a name="work-with-the-improved-variant-suggestions"></a><span data-ttu-id="95a62-162">A továbbfejlesztett változatjavaslatok használata</span><span class="sxs-lookup"><span data-stu-id="95a62-162">Work with the improved variant suggestions</span></span>

<span data-ttu-id="95a62-163">A termékváltozat-javaslatok létrehozásához, ha engedélyezve van a *Változatjavaslatok oldal javításai* funkció:</span><span class="sxs-lookup"><span data-stu-id="95a62-163">To generate product variant suggestions when the *Variant suggestions page improvements* feature is enabled:</span></span>

1. <span data-ttu-id="95a62-164">Nyisson meg vagy hozzon létre egy alapterméket, és adja hozzá a szükséges termékdimenziókat az előző szakaszban leírtak szerint.</span><span class="sxs-lookup"><span data-stu-id="95a62-164">Open or create a product master and add the required product dimensions to it, as described in the previous section.</span></span>
1. <span data-ttu-id="95a62-165">Ha az alaptermék még nyitva marad, válassza ki a **Termékváltozatokat** a műveleti ablaktáblán.</span><span class="sxs-lookup"><span data-stu-id="95a62-165">With the product master open, select **Product variants** on the Action Pane.</span></span>
1. <span data-ttu-id="95a62-166">A Műveleti ablaktáblán válassza ki a **Változatjavaslatok** elemet.</span><span class="sxs-lookup"><span data-stu-id="95a62-166">Select **Variant suggestions** on the Action Pane.</span></span>
1. <span data-ttu-id="95a62-167">Válassza ki a használni kívánt értékeket az egyes dimenziókhoz.</span><span class="sxs-lookup"><span data-stu-id="95a62-167">Select the values that you want to use for each of the dimensions.</span></span>
1. <span data-ttu-id="95a62-168">A felső eszköztáron válassza a **Javaslat** elemet.</span><span class="sxs-lookup"><span data-stu-id="95a62-168">On the top toolbar, select **Suggest**.</span></span>
1. <span data-ttu-id="95a62-169">A rendszer listát generál a kiválasztott méretek és színek összes lehetséges kombinációjáról.</span><span class="sxs-lookup"><span data-stu-id="95a62-169">The system generates a list with all possible combinations of the sizes and colors you selected.</span></span> <span data-ttu-id="95a62-170">Jelölje be a **Javasolt változatok** gyorstáblán a használni kívánt termékdimenzió-kombinációk jelölőnégyzetét, vagy válassza az **Összes kijelölése** elemet az eszköztáron az összes kiválasztásához.</span><span class="sxs-lookup"><span data-stu-id="95a62-170">On the **Suggested variants** FastTab, select the check box for each product dimension combination that you want to use, or select **Select all** on the toolbar to select all of them.</span></span>  
1. <span data-ttu-id="95a62-171">Válassza a **Létrehozás** lehetőséget, ha a változatokat hozzá szeretne adni az aktuális alaptermékhez.</span><span class="sxs-lookup"><span data-stu-id="95a62-171">Select **Create** to add the variants to the current product master.</span></span>

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
