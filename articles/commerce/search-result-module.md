---
title: Keresési eredmények modul
description: Ez a témakör a keresési eredmények modulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
manager: annbe
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 5d852fe1a81b1e42484bc49ae136ef8613a2d3a5
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5254769"
---
# <a name="search-results-module"></a><span data-ttu-id="7a28f-103">Keresési eredmények modul</span><span class="sxs-lookup"><span data-stu-id="7a28f-103">Search results module</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="7a28f-104">Ez a témakör a keresési eredmények modulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="7a28f-104">This topic covers search results modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="7a28f-105">A keresési eredmények modul megjeleníti a termékkeresési eredményeket és a termékekre alkalmazható finomítók listáját.</span><span class="sxs-lookup"><span data-stu-id="7a28f-105">The search results module returns product search results and a list of applicable refiners for the products.</span></span> <span data-ttu-id="7a28f-106">A Dynamics 365 Commerce-webhelyek keresési eredmény moduljai a következő helyzetekben használhatók lapok megjelenítésére:</span><span class="sxs-lookup"><span data-stu-id="7a28f-106">Search results modules on Dynamics 365 Commerce sites can be used to render pages for the following scenarios:</span></span>

- <span data-ttu-id="7a28f-107">Felhasználói keresés által kezdeményezett keresési eredmények</span><span class="sxs-lookup"><span data-stu-id="7a28f-107">Search results that are initiated by a user search</span></span>
- <span data-ttu-id="7a28f-108">Olyan keresési eredmények, amelyek adott termékhalmazt mutatnak, például a „hasonló megvásárlása” kifejezés</span><span class="sxs-lookup"><span data-stu-id="7a28f-108">Search results that show a specific set of products, such as "Shop similar looks"</span></span>
- <span data-ttu-id="7a28f-109">Adott kategóriába tartozó termékek listái</span><span class="sxs-lookup"><span data-stu-id="7a28f-109">Lists of products that belong to a category</span></span>

<span data-ttu-id="7a28f-110">A kategóriákról és a keresési eredmények oldalairól [Az alapértelmezett kategória céloldala és keresési találatoldala](category-search-page-overview.md) nyújt további tájékoztatást.</span><span class="sxs-lookup"><span data-stu-id="7a28f-110">For more information about category and search results pages, see [Default category landing page and search results page overview](category-search-page-overview.md).</span></span>

<span data-ttu-id="7a28f-111">A következő ábra egy példát mutat be egy keresési eredmény oldal megjelenítésére egy kategóriához kapcsolódóan a Fabrikam webhelyen.</span><span class="sxs-lookup"><span data-stu-id="7a28f-111">The following illustration shows an example of a search results page for a category on the Fabrikam site.</span></span>

![Példa a Fabrikam webhelyén lévő keresési eredmények oldalra](./media/SimpleCategoryLandingDressCategory.png)

## <a name="search-results-module-properties"></a><span data-ttu-id="7a28f-113">Keresési eredmények modul tulajdonságai</span><span class="sxs-lookup"><span data-stu-id="7a28f-113">Search results module properties</span></span>

<span data-ttu-id="7a28f-114">Az alábbi táblázat felsorolja a keresési eredmények modulok tulajdonságait, valamint azok értékeit és leírásait.</span><span class="sxs-lookup"><span data-stu-id="7a28f-114">The following table lists the properties of search result modules, together with their values and descriptions.</span></span>

| <span data-ttu-id="7a28f-115">Tulajdonság</span><span class="sxs-lookup"><span data-stu-id="7a28f-115">Property</span></span> | <span data-ttu-id="7a28f-116">Értékek</span><span class="sxs-lookup"><span data-stu-id="7a28f-116">Values</span></span> | <span data-ttu-id="7a28f-117">Leírás</span><span class="sxs-lookup"><span data-stu-id="7a28f-117">Description</span></span> |
|----------|--------|-------------|
| <span data-ttu-id="7a28f-118">Cikkek száma oldalanként</span><span class="sxs-lookup"><span data-stu-id="7a28f-118">Items per page</span></span> | <span data-ttu-id="7a28f-119">Egész</span><span class="sxs-lookup"><span data-stu-id="7a28f-119">Integer</span></span> | <span data-ttu-id="7a28f-120">Az egyes oldalakon megjelenítendő elemek száma.</span><span class="sxs-lookup"><span data-stu-id="7a28f-120">The number of items that should be shown on each page.</span></span> |
| <span data-ttu-id="7a28f-121">Visszalépés engedélyezése a PDP-n</span><span class="sxs-lookup"><span data-stu-id="7a28f-121">Allow back on PDP</span></span> | <span data-ttu-id="7a28f-122">**Igaz** vagy **Hamis**</span><span class="sxs-lookup"><span data-stu-id="7a28f-122">**True** or **False**</span></span> | <span data-ttu-id="7a28f-123">Ha a tulajdonság beállítása **Igaz**, amikor egy felhasználó kiválasztja a terméket a keresési eredmények oldalon, a termék részleteit tartalmazó megnyitott oldalon az útkövető navigációs rendszer megjeleníti a Vissza az eredményekhez hivatkozást.</span><span class="sxs-lookup"><span data-stu-id="7a28f-123">If this property is set to **True**, when a user selects a product on the search results page, the breadcrumb navigation on the product details page (PDP) that is opened will show a "Back to results" link.</span></span> |
| <span data-ttu-id="7a28f-124">Finomítók kibővítése</span><span class="sxs-lookup"><span data-stu-id="7a28f-124">Expand Refiners</span></span> | <span data-ttu-id="7a28f-125">**Mind**, **1**, **2**, **3** vagy **4**</span><span class="sxs-lookup"><span data-stu-id="7a28f-125">**All**, **1**, **2**, **3**, or **4**</span></span> | <span data-ttu-id="7a28f-126">Az oldal betöltésekor kibontandó legjobb finomítók száma.</span><span class="sxs-lookup"><span data-stu-id="7a28f-126">The number of top refiners that should be expanded when a page is loaded.</span></span> <span data-ttu-id="7a28f-127">Ha például a tulajdonság értéke **3**, a program az oldal első három finomítóját bontja ki.</span><span class="sxs-lookup"><span data-stu-id="7a28f-127">For example, if this property is set to **3**, the first three refiners on the page will be expanded.</span></span> |
| <span data-ttu-id="7a28f-128">Kategóriahierarchia megjelenítésének elrejtése</span><span class="sxs-lookup"><span data-stu-id="7a28f-128">Hide category hierarchy display</span></span> | <span data-ttu-id="7a28f-129">**Igaz** vagy **Hamis**</span><span class="sxs-lookup"><span data-stu-id="7a28f-129">**True** or **False**</span></span> | <span data-ttu-id="7a28f-130">Ha ez a tulajdonság **Igaz**, a kategóriahierarchia nem jelenik meg az oldalon.</span><span class="sxs-lookup"><span data-stu-id="7a28f-130">If this property is set to **True**, the category hierarchy display on the page will be hidden.</span></span> <span data-ttu-id="7a28f-131">Ha az [útvonalkövető modult](add-breadcrumb.md) használja a kategóriahierarchia megjelenítéséhez, ezt a tulajdonságot **Igaz** értékre kell beállítani.</span><span class="sxs-lookup"><span data-stu-id="7a28f-131">This property should be set to **True** if you're using the [breadcrumb module](add-breadcrumb.md) to show the category hierarchy.</span></span>|
| <span data-ttu-id="7a28f-132">Termékattribútumok hozzáadása a keresési eredményekhez</span><span class="sxs-lookup"><span data-stu-id="7a28f-132">Include product attributes in search results</span></span> | <span data-ttu-id="7a28f-133">**Igaz** vagy **Hamis**</span><span class="sxs-lookup"><span data-stu-id="7a28f-133">**True** or **False**</span></span> | <span data-ttu-id="7a28f-134">Ha a tulajdonság értéke **Igaz**, a keresési eredmények megjelenítik a termékek attribútumait.</span><span class="sxs-lookup"><span data-stu-id="7a28f-134">If this property is set to **True**, attributes will be returned for the products in the search results.</span></span> <span data-ttu-id="7a28f-135">Bár ezek az attribútumok a Commerce webhelyen is megjeleníthetők, bővítményre van szükség.</span><span class="sxs-lookup"><span data-stu-id="7a28f-135">Although these attributes can be shown on a Commerce site, an extension is required.</span></span>|
| <span data-ttu-id="7a28f-136">Fiókárak megjelenítése</span><span class="sxs-lookup"><span data-stu-id="7a28f-136">Show affiliation prices</span></span> | <span data-ttu-id="7a28f-137">**Igaz** vagy **Hamis**</span><span class="sxs-lookup"><span data-stu-id="7a28f-137">**True** or **False**</span></span> | <span data-ttu-id="7a28f-138">Ha ez a tulajdonság **Igaz**, a termékek fiókárai megjelennek a keresési eredményekben, amikor egy bejelentkezett felhasználó tallóz az oldalon.</span><span class="sxs-lookup"><span data-stu-id="7a28f-138">If this property is set to **True**, affiliation prices for products will be shown in the search results when a signed-in user browses the page.</span></span> |

> [!IMPORTANT]
> <span data-ttu-id="7a28f-139">A Dynamics 365 Commerce 10.0.16-os és későbbi kiadásában a **Fiókárak megjelenítése** konfiguráció használható a fiókárak oldalon történő megjelenítésére.</span><span class="sxs-lookup"><span data-stu-id="7a28f-139">In the Dynamics 365 Commerce 10.0.16 release and later, the **Show affiliation prices** configuration can be used to show affiliation prices on the page.</span></span>

## <a name="supported-modules"></a><span data-ttu-id="7a28f-140">Támogatott modulok</span><span class="sxs-lookup"><span data-stu-id="7a28f-140">Supported modules</span></span>

<span data-ttu-id="7a28f-141">A keresési eredmények modul támogatja a [gyorsnézet modult](quick-view-module.md), amellyel a felhasználók megtekinthetik a termékadatokat, és cikkeket adhatnak hozzá a kosárhoz egy keresési eredmények oldalról.</span><span class="sxs-lookup"><span data-stu-id="7a28f-141">The search results module supports the [quick view module](quick-view-module.md), which lets users view product information and add items to the cart from the search results page.</span></span>

## <a name="add-a-search-results-module-to-a-category-page"></a><span data-ttu-id="7a28f-142">Keresési eredmények modul hozzáadása kategóriaoldalhoz</span><span class="sxs-lookup"><span data-stu-id="7a28f-142">Add a search results module to a category page</span></span>

<span data-ttu-id="7a28f-143">A következő lépésekkel lehet hozzáadni egy keresési eredmények modult egy kategóriaoldalhoz.</span><span class="sxs-lookup"><span data-stu-id="7a28f-143">To add a search results module to a category page, follow these steps.</span></span>

1. <span data-ttu-id="7a28f-144">Lépjen a **Sablonok** pontra, majd új sablon készítéséhez válassza az **Új** elemet.</span><span class="sxs-lookup"><span data-stu-id="7a28f-144">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="7a28f-145">Az **Új sablon** párbeszédablakban írja be a **Keresési eredmények** nevet, majd válassza az **OK** gombot.</span><span class="sxs-lookup"><span data-stu-id="7a28f-145">In the **New template** dialog box, enter the name **Search results**, and then select **OK**.</span></span>
1. <span data-ttu-id="7a28f-146">A **Törzs** helyben válassza a három pont (…) gombot, majd válassza a **Modul hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="7a28f-146">In the **Body** slot, select the ellipsis (...), and then select **Add Module**.</span></span>
1. <span data-ttu-id="7a28f-147">A **Modul hozzáadása** párbeszédpanelen válassza ki az **Alapértelmezett oldal** modult, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="7a28f-147">In the **Add Module** dialog box, select the **Default Page** module, and then select **OK**.</span></span>
1. <span data-ttu-id="7a28f-148">Az **Alapértelmezett oldal** modul **Fő** helyén válassza ki a három pont (…) gombot, majd válassza a **Modul hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="7a28f-148">In the **Main** slot of the **Default Page** module, select the ellipsis (...), and then select **Add Module**.</span></span>
1. <span data-ttu-id="7a28f-149">A **Modul hozzáadása** párbeszédpanelen válassza ki az **Tároló** modult, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="7a28f-149">In the **Add Module** dialog box, select the **Container** module, and then select **OK**.</span></span>
1. <span data-ttu-id="7a28f-150">A **Tároló** helyben válassza a három pont (…) gombot, majd válassza a **Modul hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="7a28f-150">In the **Container** slot, select the ellipsis (...), and then select **Add Module**.</span></span>
1. <span data-ttu-id="7a28f-151">A **Modul hozzáadása** párbeszédpanelen válassza ki az **Útkövetési** modult, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="7a28f-151">In the **Add Module** dialog box, select the **Breadcrumb** module, and then select **OK**.</span></span>
1. <span data-ttu-id="7a28f-152">Az **Útkövetés** tulajdonságok panelen írja be az **1** értéket az **Előfordulások minimális száma** pontban.</span><span class="sxs-lookup"><span data-stu-id="7a28f-152">In the **Breadcrumb** properties pane, enter the value **1** for **Min Occurs**.</span></span>
1. <span data-ttu-id="7a28f-153">A **Tároló** helyben válassza a három pont (…) gombot, majd válassza a **Modul hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="7a28f-153">In the **Container** slot, select the ellipsis (...), and then select **Add Module**.</span></span>
1. <span data-ttu-id="7a28f-154">A **Modul hozzáadása** párbeszédpanelen válassza ki a **Keresési eredmények** modult, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="7a28f-154">In the **Add Module** dialog box, select the **Search results** module, and then select **OK**.</span></span>
1. <span data-ttu-id="7a28f-155">A **Keresési eredmények** tulajdonságok panelen adja meg az **1** értéket az **Előfordulások minimális száma** pontban, majd állítsa be az egyéb szükséges tulajdonságokat a keresési eredmények modulhoz.</span><span class="sxs-lookup"><span data-stu-id="7a28f-155">In the **Search results** properties pane, enter the value **1** for **Min Occurs**, and then set any other required properties for the search results module.</span></span> <span data-ttu-id="7a28f-156">A tulajdonságoknak a sablonban való beállításával biztosíthatja, hogy az adott kategóriaoldal minden testreszabása automatikusan tartalmazza ezeket a beállításokat.</span><span class="sxs-lookup"><span data-stu-id="7a28f-156">By setting these properties in the template, you ensure that any customizations to a specific category page will automatically include these settings.</span></span>
1. <span data-ttu-id="7a28f-157">Válassza a **Szerkesztés befejezése** parancsot, majd a **Közzététel** elemet a sablon közzétételhez.</span><span class="sxs-lookup"><span data-stu-id="7a28f-157">Select **Finish editing**, and then select **Publish** to publish the template.</span></span>
1. <span data-ttu-id="7a28f-158">Lépjen az **Oldalak** pontra, majd válassza az **Új** lehetőséget új oldal létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="7a28f-158">Go to **Pages**, and select **New** to create a new page.</span></span>
1. <span data-ttu-id="7a28f-159">A **Sablon kiválasztása** párbeszédpanelen válassza ki a létrehozott **Keresési eredmények** sablont, írja be a **Kategóriaoldal** lehetőséget az **OIdal neve** pontba, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="7a28f-159">In the **Choose a template** dialog box, select the **Search results** template that you created, enter **Category page** for **Page name**, and then select **OK**.</span></span> <span data-ttu-id="7a28f-160">Mivel a sablonban minden érték be van állítva, az oldal készen áll a közzétételre.</span><span class="sxs-lookup"><span data-stu-id="7a28f-160">Because all the values are set in the template, the page is ready to be published.</span></span>
1. <span data-ttu-id="7a28f-161">Válassza a **Szerkesztés befejezése** parancsot az oldal ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.</span><span class="sxs-lookup"><span data-stu-id="7a28f-161">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="7a28f-162">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="7a28f-162">Additional resources</span></span>

[<span data-ttu-id="7a28f-163">Az alapértelmezett kategória-céloldal és keresési találatoldal áttekintése</span><span class="sxs-lookup"><span data-stu-id="7a28f-163">Default category landing page and search results page overview</span></span>](category-search-page-overview.md)

[<span data-ttu-id="7a28f-164">Modultár áttekintése</span><span class="sxs-lookup"><span data-stu-id="7a28f-164">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="7a28f-165">Gyorsnézeti modul</span><span class="sxs-lookup"><span data-stu-id="7a28f-165">Quick view module</span></span>](quick-view-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]