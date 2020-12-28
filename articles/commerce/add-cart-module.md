---
title: Kosármodul
description: Ez a témakör a kosármodulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
manager: annbe
ms.date: 10/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 33db06ecfa2a8fa93cde3c4f1b31d6b30bfd0c34
ms.sourcegitcommit: 12d271bb26c7490e7525d9b4bbf125cdc39fef43
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/07/2020
ms.locfileid: "4413019"
---
# <a name="cart-module"></a><span data-ttu-id="2be9e-103">Kosármodul</span><span class="sxs-lookup"><span data-stu-id="2be9e-103">Cart module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="2be9e-104">Ez a témakör a kosármodulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="2be9e-104">This topic covers cart modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="2be9e-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="2be9e-105">Overview</span></span>

<span data-ttu-id="2be9e-106">A kosármodullal megjeleníthetők a kosárba tett cikkek, mielőtt az ügyfél a pénztárra lép.</span><span class="sxs-lookup"><span data-stu-id="2be9e-106">A cart module shows the items that have been added to the cart before the customer proceeds to checkout.</span></span> <span data-ttu-id="2be9e-107">A modul a rendelés összegzését is megjeleníti, és lehetővé teszi, hogy a vevő hozzáadja vagy eltávolítsa a promóciós kódokat.</span><span class="sxs-lookup"><span data-stu-id="2be9e-107">The module also shows an order summary and lets the customer apply or remove promotional codes.</span></span>

<span data-ttu-id="2be9e-108">A kosár modul támogatja a bejelentkezett fizetést és a vendégfizetést.</span><span class="sxs-lookup"><span data-stu-id="2be9e-108">The cart module supports signed-in checkout and guest checkout.</span></span> <span data-ttu-id="2be9e-109">Támogatja a **Vissza a vásárláshoz** hivatkozást.</span><span class="sxs-lookup"><span data-stu-id="2be9e-109">It also supports a **Back to shopping** link.</span></span> <span data-ttu-id="2be9e-110">A hivatkozáshoz vezető útvonalat a **Webhely-beállítások \> Bővítmények \> Útvonala** oldalon.</span><span class="sxs-lookup"><span data-stu-id="2be9e-110">You can configure the route for this link at **Site Settings \> Extensions \> Routes**.</span></span>

<span data-ttu-id="2be9e-111">A kosár modul a kosár azonosítója alapján jeleníti meg az adatokat, ami a webhely teljes területén elérhető böngésző cookie.</span><span class="sxs-lookup"><span data-stu-id="2be9e-111">The cart module renders data based on the cart ID, which is a browser cookie available throughout the site.</span></span> 

<span data-ttu-id="2be9e-112">A következő kép a Fabrikam webhelyen használt kosároldal egy példáját jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="2be9e-112">The following image shows an example of a cart page on the Fabrikam site.</span></span>

![Példa egy gyár webhelyén lévő kosármodulra](./media/cart2.PNG)

<span data-ttu-id="2be9e-114">A következő kép a Fabrikam webhelyen használt kosároldal egy példáját jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="2be9e-114">The following image shows an example of a cart page on the Fabrikam site.</span></span> <span data-ttu-id="2be9e-115">Ebben a példában egy sortételre kezelési díjat számolnak fel.</span><span class="sxs-lookup"><span data-stu-id="2be9e-115">In this example, there is a handling fee for a line item.</span></span>

![Példa arra, amikor egy sortételre kezelési díjat számolnak fel](./media/ecommerce-handling-fee.png)

## <a name="cart-module-properties-and-slots"></a><span data-ttu-id="2be9e-117">A kosármodul tulajdonságai és helyei</span><span class="sxs-lookup"><span data-stu-id="2be9e-117">Cart module properties and slots</span></span>

| <span data-ttu-id="2be9e-118">Tulajdonság</span><span class="sxs-lookup"><span data-stu-id="2be9e-118">Property</span></span> | <span data-ttu-id="2be9e-119">Értékek</span><span class="sxs-lookup"><span data-stu-id="2be9e-119">Values</span></span> | <span data-ttu-id="2be9e-120">Leírás</span><span class="sxs-lookup"><span data-stu-id="2be9e-120">Description</span></span> |
|----------------|--------|-------------|
| <span data-ttu-id="2be9e-121">Fejléc</span><span class="sxs-lookup"><span data-stu-id="2be9e-121">Heading</span></span> | <span data-ttu-id="2be9e-122">A fejléc szövege és a fejléc címkéje (**H1**, **H2**, **H3**, **H4**, **H5** vagy **H6**)</span><span class="sxs-lookup"><span data-stu-id="2be9e-122">Heading text and a heading tag (**H1**, **H2**, **H3**, **H4**, **H5**, or **H6**)</span></span> | <span data-ttu-id="2be9e-123">A kosarának olyan címsor, mint például a "Bevásárlótáska" vagy a "Kosárban található termékek."</span><span class="sxs-lookup"><span data-stu-id="2be9e-123">A heading for the cart, such as "Shopping bag" or "Items in your cart."</span></span> |
| <span data-ttu-id="2be9e-124">A nincs készleten állapottal kapcsolatos hibák megjelenítése</span><span class="sxs-lookup"><span data-stu-id="2be9e-124">Show out of stock errors</span></span> | <span data-ttu-id="2be9e-125">**Igaz** vagy **Hamis**</span><span class="sxs-lookup"><span data-stu-id="2be9e-125">**True** or **False**</span></span> | <span data-ttu-id="2be9e-126">Ha ez a tulajdonság **Igaz** értékre van állítva, a kosár oldal a készlettel kapcsolatos hibákat fog jelezni.</span><span class="sxs-lookup"><span data-stu-id="2be9e-126">If this property is set to **True**, the cart page will show stock-related errors.</span></span> <span data-ttu-id="2be9e-127">Azt ajánljuk Önnek, hogy állítsa ezt a tulajdonságot **igaz**-ra, ha a készlet ellenőrzés engedélyezve van az oldalon.</span><span class="sxs-lookup"><span data-stu-id="2be9e-127">We recommend that you set this property to **True** if inventory checks are applied on the site.</span></span> |
| <span data-ttu-id="2be9e-128">Szállítási költségek megjelenítések sorcikkeknél</span><span class="sxs-lookup"><span data-stu-id="2be9e-128">Show shipping charges for line items</span></span> | <span data-ttu-id="2be9e-129">**Igaz** vagy **Hamis**</span><span class="sxs-lookup"><span data-stu-id="2be9e-129">**True** or **False**</span></span> | <span data-ttu-id="2be9e-130">Ha ez a tulajdonság **Igaz** értékre van állítva, akkor a kosár sortételei megmutatják a szállítás költségeit, amennyiben ez az információ elérhető.</span><span class="sxs-lookup"><span data-stu-id="2be9e-130">If this property is set to **True**, cart line items will show the shipping charges, if this information is available.</span></span> <span data-ttu-id="2be9e-131">Ez a funkció nem támogatott a Fabrikam témában, mert a felhasználók a csak szállítást választják a fizetési folyamaton belül.</span><span class="sxs-lookup"><span data-stu-id="2be9e-131">This feature isn't supported in the Fabrikam theme, because users select shipping only in the checkout flow.</span></span> <span data-ttu-id="2be9e-132">Azonban ez a funkció más munkafolyamatokban is bekapcsolható, ha az alkalmazható az adott munkafolyamatban.</span><span class="sxs-lookup"><span data-stu-id="2be9e-132">However, this feature can be turned on in other workflows if it's applicable.</span></span> |

## <a name="modules-that-can-be-used-in-a-cart-module"></a><span data-ttu-id="2be9e-133">A kosármodulban használható modulok</span><span class="sxs-lookup"><span data-stu-id="2be9e-133">Modules that can be used in a cart module</span></span>

- <span data-ttu-id="2be9e-134">**Szövegblokk** – Ez a modul a kosár modulban használható egyéni üzenetküldést támogatja.</span><span class="sxs-lookup"><span data-stu-id="2be9e-134">**Text block** – This module supports custom messaging in the cart module.</span></span> <span data-ttu-id="2be9e-135">Az üzeneteket a tartalomkezelő rendszer (CMS) vezérli.</span><span class="sxs-lookup"><span data-stu-id="2be9e-135">The messages are driven by the content management system (CMS).</span></span> <span data-ttu-id="2be9e-136">Bármilyen üzenet megadható, például: „A rendeléssel kapcsolatos problémák esetén hívja az 1-800-Fabrikam számot”.</span><span class="sxs-lookup"><span data-stu-id="2be9e-136">Any message can be added, such as "For issues with your order, contact 1-800-Fabrikam."</span></span>
- <span data-ttu-id="2be9e-137">**Áruházválasztó** – Ez a modul felsorolja azokat a közeli áruházakat, ahol a cikkek elérhetők és felvehetők.</span><span class="sxs-lookup"><span data-stu-id="2be9e-137">**Store selector** – This module shows a list of nearby stores where an item is available for pickup.</span></span> <span data-ttu-id="2be9e-138">Ez lehetővé teszi a felhasználók számára, hogy a közelben levő üzleteket megtalálják.</span><span class="sxs-lookup"><span data-stu-id="2be9e-138">It lets users enter a location to find stores that are nearby.</span></span> <span data-ttu-id="2be9e-139">A modullal kapcsolatos további tudnivalókat lásd: [Üzletkiválasztó modul](store-selector.md).</span><span class="sxs-lookup"><span data-stu-id="2be9e-139">For more information on this module, see [Store selector module](store-selector.md).</span></span>

## <a name="module-properties"></a><span data-ttu-id="2be9e-140">Modul tulajdonságai</span><span class="sxs-lookup"><span data-stu-id="2be9e-140">Module properties</span></span>

<span data-ttu-id="2be9e-141">A kosármodulok következő beállításai konfigurálhatók a **Webhelybeállítások \> Bővítmények** pontban:</span><span class="sxs-lookup"><span data-stu-id="2be9e-141">The following cart module settings can be configured at **Site Settings \> Extensions**:</span></span>

- <span data-ttu-id="2be9e-142">**Maximális mennyiség** – Ez a tulajdonság megadja az egyes cikkek kosárhoz adható maximális számát.</span><span class="sxs-lookup"><span data-stu-id="2be9e-142">**Maximum quantity** – This property is used to specify the maximum number of each item that can be added to the cart.</span></span> <span data-ttu-id="2be9e-143">Előfordulhat például, hogy egy kiskereskedő úgy dönt, hogy egyetlen tranzakcióban csak 10 terméket lehet értékesíteni.</span><span class="sxs-lookup"><span data-stu-id="2be9e-143">For example, a retailer might decide that only 10 of each product can be sold in a single transaction.</span></span>
- <span data-ttu-id="2be9e-144">**Készlet** – A készletbeállítások alkalmazásával kapcsolatban a következő témakör tartalmaz további tájékoztatást: [Készletbeállítások alkalmazása](inventory-settings.md).</span><span class="sxs-lookup"><span data-stu-id="2be9e-144">**Inventory** – For information about how to apply inventory settings, see [Apply inventory settings](inventory-settings.md).</span></span>
- <span data-ttu-id="2be9e-145">**Vissza a vásárláshoz** – a tulajdonság a **Vissza a vásárláshoz** linkhez megadott útvonal meghatározására szolgál.</span><span class="sxs-lookup"><span data-stu-id="2be9e-145">**Back to shopping** – This property is used to specify the route for the **Back to shopping** link.</span></span> <span data-ttu-id="2be9e-146">Az útvonal a webhely szintjén konfigurálható, amely lehetővé teszi, hogy a kiskereskedők visszavigyék a vevőt a kezdőlapra vagy más lapjára.</span><span class="sxs-lookup"><span data-stu-id="2be9e-146">The route can be configured at the site level, allowing retailers to take the customer back to the home page or any other page on the site.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2be9e-147">A Dynamics 365 Commerce 10.0.14-verzióban és a későbbiekben a kosárban szereplő cikkek a Commerce központ online áruházának online funkcionális profiljában megadott beállítások alapján kerülnek összesítésre.</span><span class="sxs-lookup"><span data-stu-id="2be9e-147">In the Dynamics 365 Commerce 10.0.14 release and later, items in the cart are aggregated based on the settings that are defined in the online functionality profile for the online store in Commerce headquarters.</span></span> <span data-ttu-id="2be9e-148">Ha további tájékoztatást szeretne arról, hogyan lehet létrehozni egy online funkcionális profilt, és be kell állítania az összesítéshez szükséges tulajdonságokat, akkor lásd: [online működési profil létrehozása](online-functionality-profile.md).</span><span class="sxs-lookup"><span data-stu-id="2be9e-148">For more information about how to create an online functionality profile and set the properties that are required for aggregation, see [Create an online functionality profile](online-functionality-profile.md).</span></span>

## <a name="commerce-scale-unit-interaction"></a><span data-ttu-id="2be9e-149">Commerce Scale Unit-interakció</span><span class="sxs-lookup"><span data-stu-id="2be9e-149">Commerce Scale Unit interaction</span></span>

<span data-ttu-id="2be9e-150">A kosármodul a termék adatait a Commerce Scale Unit API-k használatával olvassa be.</span><span class="sxs-lookup"><span data-stu-id="2be9e-150">The cart module retrieves product information by using Commerce Scale Unit APIs.</span></span> <span data-ttu-id="2be9e-151">A böngésző cookie-jából származó kosárazonosító szolgál az összes termékadat beolvasására a Commerce Scale Unitról.</span><span class="sxs-lookup"><span data-stu-id="2be9e-151">The cart ID from the browser cookie is used to retrieve all the product information from Commerce Scale Unit.</span></span>

## <a name="add-a-cart-module-to-a-page"></a><span data-ttu-id="2be9e-152">Kosármodul felvétele egy oldalra</span><span class="sxs-lookup"><span data-stu-id="2be9e-152">Add a cart module to a page</span></span>

<span data-ttu-id="2be9e-153">A kosármodul új oldalra való felvételéhez és a kötelező tulajdonságok beállításához hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="2be9e-153">To add a cart module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="2be9e-154">Lépjen a **Töredékek** pontra, és válassza az **Új** lehetőséget új töredék létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="2be9e-154">Go to **Fragments**, and select **New** to create a new fragment.</span></span>
1. <span data-ttu-id="2be9e-155">Az **Új töredék** párbeszédpanelen válassza ki a **Kosár** modult.</span><span class="sxs-lookup"><span data-stu-id="2be9e-155">In the **New fragment** dialog box, select the **Cart** module.</span></span>
1. <span data-ttu-id="2be9e-156">A **Töredék neve** pontban adja meg a **Kosár töredék** nevet, ezután válassza az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2be9e-156">Under **Fragment name**, enter the name **Cart fragment**, and then select **OK**.</span></span>
1. <span data-ttu-id="2be9e-157">Válassza ki **Kosár** helyet.</span><span class="sxs-lookup"><span data-stu-id="2be9e-157">Select the **Cart** slot.</span></span>
1. <span data-ttu-id="2be9e-158">A jobb oldali tulajdonságok ablaktáblán válassza ki a ceruza szimbólumot, adja meg a címsor szövegét a mezőben, majd jelölje be a pipa jelet.</span><span class="sxs-lookup"><span data-stu-id="2be9e-158">In the properties pane on the right, select the pencil symbol, enter heading text in the field, and then select the check mark symbol.</span></span>
1. <span data-ttu-id="2be9e-159">A **Kosár** helyben válassza a három pont (**…**) gombot, majd válassza az **Modul hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="2be9e-159">In the **Cart** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="2be9e-160">A **Modul hozzáadása** párbeszédpanelen válassza ki az **Áruházválasztó** modult, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="2be9e-160">In the **Add Module** dialog box, select the **Store selector** module, and then select **OK**.</span></span>
1. <span data-ttu-id="2be9e-161">Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot a töredék ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.</span><span class="sxs-lookup"><span data-stu-id="2be9e-161">Select **Save**, select **Finish editing** to check in the fragment, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="2be9e-162">Lépjen a **Sablonok** pontra, majd új sablon készítéséhez válassza az **Új** elemet.</span><span class="sxs-lookup"><span data-stu-id="2be9e-162">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="2be9e-163">Az **Új sablon** párbeszédablakban a **Sablon neve** alatt adja meg a sablon nevét.</span><span class="sxs-lookup"><span data-stu-id="2be9e-163">In the **New Template** dialog box, under **Template name**, enter a name for the template.</span></span>
1. <span data-ttu-id="2be9e-164">A Vázlatablakban válassza ki a **Törzs** helyét, válassza a három pont (**…**) majd válassza a **Töredék hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="2be9e-164">In the outline tree, select the **Body** slot, select the ellipsis (**...**), and then select **Add fragment**.</span></span>
1. <span data-ttu-id="2be9e-165">A **Töredék kiválasztása** párbeszédpanelen válassza ki a **Kosártöredék** nevű töredékét, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="2be9e-165">In the **Select fragment** dialog box, select the **Cart fragment** fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="2be9e-166">Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot a sablon ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.</span><span class="sxs-lookup"><span data-stu-id="2be9e-166">Select **Save**, select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="2be9e-167">Lépjen az **Oldalak** pontra, majd válassza az **Új** lehetőséget új oldal létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="2be9e-167">Go to **Pages**, and select **New** to create a new page.</span></span>
1. <span data-ttu-id="2be9e-168">A **Sablon kiválasztása** párbeszédpanelen válassza ki a létrehozott sablont, adjon meg egy oldalnevet, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="2be9e-168">In the **Choose a template** dialog box, select the template that you created, enter a page name, and then select **OK**.</span></span>
1. <span data-ttu-id="2be9e-169">Válassza a **Mentés** lehetőséget, majd az oldal előnézetének megtekintéséhez az **Előnézet** elemet.</span><span class="sxs-lookup"><span data-stu-id="2be9e-169">Select **Save**, and then select **Preview** to preview the page.</span></span>
1. <span data-ttu-id="2be9e-170">Válassza a **Szerkesztés befejezése** parancsot az oldal ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.</span><span class="sxs-lookup"><span data-stu-id="2be9e-170">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2be9e-171">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="2be9e-171">Additional resources</span></span>

[<span data-ttu-id="2be9e-172">Kosárikon modul</span><span class="sxs-lookup"><span data-stu-id="2be9e-172">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="2be9e-173">Fizetésmodul</span><span class="sxs-lookup"><span data-stu-id="2be9e-173">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="2be9e-174">Fizetési modul</span><span class="sxs-lookup"><span data-stu-id="2be9e-174">Payment module</span></span>](payment-module.md)

[<span data-ttu-id="2be9e-175">Szállítási cím modul</span><span class="sxs-lookup"><span data-stu-id="2be9e-175">Shipping address module</span></span>](ship-address-module.md)

[<span data-ttu-id="2be9e-176">Szállítási lehetőségek modul</span><span class="sxs-lookup"><span data-stu-id="2be9e-176">Delivery options module</span></span>](delivery-options-module.md)

[<span data-ttu-id="2be9e-177">Átvételi információk modul</span><span class="sxs-lookup"><span data-stu-id="2be9e-177">Pickup information module</span></span>](pickup-info-module.md)

[<span data-ttu-id="2be9e-178">Rendelési részletek modul</span><span class="sxs-lookup"><span data-stu-id="2be9e-178">Order details module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="2be9e-179">Ajándékutalvány modul</span><span class="sxs-lookup"><span data-stu-id="2be9e-179">Gift card module</span></span>](add-giftcard.md)

[<span data-ttu-id="2be9e-180">Kiskereskedelmi csatornák készletelérhetőségének kiszámítása</span><span class="sxs-lookup"><span data-stu-id="2be9e-180">Calculate inventory availability for retail channels</span></span>](calculated-inventory-retail-channels.md)

[<span data-ttu-id="2be9e-181">Online funkcióprofil létrehozása</span><span class="sxs-lookup"><span data-stu-id="2be9e-181">Create an online functionality profile</span></span>](online-functionality-profile.md)
