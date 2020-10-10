---
title: Kosármodul
description: Ez a témakör a kosármodulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
manager: annbe
ms.date: 08/31/2020
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
ms.openlocfilehash: d9a15f85838849796d6ce4674712636251c75bf3
ms.sourcegitcommit: 97ceb24f191161ca601e0889a539df665834ac3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/16/2020
ms.locfileid: "3818275"
---
# <a name="cart-module"></a><span data-ttu-id="ca8b4-103">Kosármodul</span><span class="sxs-lookup"><span data-stu-id="ca8b4-103">Cart module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="ca8b4-104">Ez a témakör a kosármodulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="ca8b4-104">This topic covers cart modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="ca8b4-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="ca8b4-105">Overview</span></span>

<span data-ttu-id="ca8b4-106">A kosármodullal megjeleníthetők a kosárba tett cikkek, mielőtt az ügyfél a pénztárra lép.</span><span class="sxs-lookup"><span data-stu-id="ca8b4-106">A cart module shows the items that have been added to the cart before the customer proceeds to checkout.</span></span> <span data-ttu-id="ca8b4-107">A modul a rendelés összegzését is megjeleníti, és lehetővé teszi, hogy a vevő hozzáadja vagy eltávolítsa a promóciós kódokat.</span><span class="sxs-lookup"><span data-stu-id="ca8b4-107">The module also shows an order summary and lets the customer apply or remove promotional codes.</span></span>

<span data-ttu-id="ca8b4-108">A kosár modul támogatja a bejelentkezett fizetést és a vendégfizetést.</span><span class="sxs-lookup"><span data-stu-id="ca8b4-108">The cart module supports signed-in checkout and guest checkout.</span></span> <span data-ttu-id="ca8b4-109">Támogatja a **Vissza a vásárláshoz** hivatkozást.</span><span class="sxs-lookup"><span data-stu-id="ca8b4-109">It also supports a **Back to shopping** link.</span></span> <span data-ttu-id="ca8b4-110">A hivatkozáshoz vezető útvonalat a **Webhely-beállítások \> Bővítmények \> Útvonala** oldalon.</span><span class="sxs-lookup"><span data-stu-id="ca8b4-110">You can configure the route for this link at **Site Settings \> Extensions \> Routes**.</span></span>

<span data-ttu-id="ca8b4-111">A kosár modul a kosár azonosítója alapján jeleníti meg az adatokat, ami a webhely teljes területén elérhető böngésző cookie.</span><span class="sxs-lookup"><span data-stu-id="ca8b4-111">The cart module renders data based on the cart ID, which is a browser cookie available throughout the site.</span></span> 

<span data-ttu-id="ca8b4-112">A következő kép a Fabrikam webhelyen használt kosároldal egy példáját jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="ca8b4-112">The following image shows an example of a cart page on the Fabrikam site.</span></span>

![Példa egy gyár webhelyén lévő kosármodulra](./media/cart2.PNG)

<span data-ttu-id="ca8b4-114">A következő kép a Fabrikam webhelyen használt kosároldal egy példáját jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="ca8b4-114">The following image shows an example of a cart page on the Fabrikam site.</span></span> <span data-ttu-id="ca8b4-115">Ebben a példában egy sortételre kezelési díjat számolnak fel.</span><span class="sxs-lookup"><span data-stu-id="ca8b4-115">In this example, there is a handling fee for a line item.</span></span>

![Példa arra, amikor egy sortételre kezelési díjat számolnak fel](./media/ecommerce-handling-fee.png)

## <a name="cart-module-properties-and-slots"></a><span data-ttu-id="ca8b4-117">A kosármodul tulajdonságai és helyei</span><span class="sxs-lookup"><span data-stu-id="ca8b4-117">Cart module properties and slots</span></span>

| <span data-ttu-id="ca8b4-118">Tulajdonság</span><span class="sxs-lookup"><span data-stu-id="ca8b4-118">Property</span></span> | <span data-ttu-id="ca8b4-119">Értékek</span><span class="sxs-lookup"><span data-stu-id="ca8b4-119">Values</span></span> | <span data-ttu-id="ca8b4-120">Leírás</span><span class="sxs-lookup"><span data-stu-id="ca8b4-120">Description</span></span> |
|----------------|--------|-------------|
| <span data-ttu-id="ca8b4-121">Fejléc</span><span class="sxs-lookup"><span data-stu-id="ca8b4-121">Heading</span></span> | <span data-ttu-id="ca8b4-122">A fejléc szövege és a fejléc címkéje (**H1**, **H2**, **H3**, **H4**, **H5** vagy **H6**)</span><span class="sxs-lookup"><span data-stu-id="ca8b4-122">Heading text and a heading tag (**H1**, **H2**, **H3**, **H4**, **H5**, or **H6**)</span></span> | <span data-ttu-id="ca8b4-123">A kosarának olyan címsor, mint például a "Bevásárlótáska" vagy a "Kosárban található termékek."</span><span class="sxs-lookup"><span data-stu-id="ca8b4-123">A heading for the cart, such as "Shopping bag" or "Items in your cart."</span></span> |
| <span data-ttu-id="ca8b4-124">A nincs készleten állapottal kapcsolatos hibák megjelenítése</span><span class="sxs-lookup"><span data-stu-id="ca8b4-124">Show out of stock errors</span></span> | <span data-ttu-id="ca8b4-125">**Igaz** vagy **Hamis**</span><span class="sxs-lookup"><span data-stu-id="ca8b4-125">**True** or **False**</span></span> | <span data-ttu-id="ca8b4-126">Ha ez a tulajdonság **Igaz** értékre van állítva, a kosár oldal a készlettel kapcsolatos hibákat fog jelezni.</span><span class="sxs-lookup"><span data-stu-id="ca8b4-126">If this property is set to **True**, the cart page will show stock-related errors.</span></span> <span data-ttu-id="ca8b4-127">Azt ajánljuk Önnek, hogy állítsa ezt a tulajdonságot **igaz**-ra, ha a készlet ellenőrzés engedélyezve van az oldalon.</span><span class="sxs-lookup"><span data-stu-id="ca8b4-127">We recommend that you set this property to **True** if inventory checks are applied on the site.</span></span> |
| <span data-ttu-id="ca8b4-128">Szállítási költségek megjelenítések sorcikkeknél</span><span class="sxs-lookup"><span data-stu-id="ca8b4-128">Show shipping charges for line items</span></span> | <span data-ttu-id="ca8b4-129">**Igaz** vagy **Hamis**</span><span class="sxs-lookup"><span data-stu-id="ca8b4-129">**True** or **False**</span></span> | <span data-ttu-id="ca8b4-130">Ha ez a tulajdonság **Igaz** értékre van állítva, akkor a kosár sortételei megmutatják a szállítás költségeit, amennyiben ez az információ elérhető.</span><span class="sxs-lookup"><span data-stu-id="ca8b4-130">If this property is set to **True**, cart line items will show the shipping charges, if this information is available.</span></span> <span data-ttu-id="ca8b4-131">Ez a funkció nem támogatott a Fabrikam témában, mert a felhasználók a csak szállítást választják a fizetési folyamaton belül.</span><span class="sxs-lookup"><span data-stu-id="ca8b4-131">This feature isn't supported in the Fabrikam theme, because users select shipping only in the checkout flow.</span></span> <span data-ttu-id="ca8b4-132">Azonban ez a funkció más munkafolyamatokban is bekapcsolható, ha az alkalmazható az adott munkafolyamatban.</span><span class="sxs-lookup"><span data-stu-id="ca8b4-132">However, this feature can be turned on in other workflows if it's applicable.</span></span> |

## <a name="modules-that-can-be-used-in-a-cart-module"></a><span data-ttu-id="ca8b4-133">A kosármodulban használható modulok</span><span class="sxs-lookup"><span data-stu-id="ca8b4-133">Modules that can be used in a cart module</span></span>

- <span data-ttu-id="ca8b4-134">**Szövegblokk** – Ez a modul a kosár modulban használható egyéni üzenetküldést támogatja.</span><span class="sxs-lookup"><span data-stu-id="ca8b4-134">**Text block** – This module supports custom messaging in the cart module.</span></span> <span data-ttu-id="ca8b4-135">Az üzeneteket a tartalomkezelő rendszer (CMS) vezérli.</span><span class="sxs-lookup"><span data-stu-id="ca8b4-135">The messages are driven by the content management system (CMS).</span></span> <span data-ttu-id="ca8b4-136">Bármilyen üzenet megadható, például: „A rendeléssel kapcsolatos problémák esetén hívja az 1-800-Fabrikam számot”.</span><span class="sxs-lookup"><span data-stu-id="ca8b4-136">Any message can be added, such as "For issues with your order, contact 1-800-Fabrikam."</span></span>
- <span data-ttu-id="ca8b4-137">**Áruházválasztó** – Ez a modul felsorolja azokat a közeli áruházakat, ahol a cikkek elérhetők és felvehetők.</span><span class="sxs-lookup"><span data-stu-id="ca8b4-137">**Store selector** – This module shows a list of nearby stores where an item is available for pickup.</span></span> <span data-ttu-id="ca8b4-138">Ez lehetővé teszi a felhasználók számára, hogy a közelben levő üzleteket megtalálják.</span><span class="sxs-lookup"><span data-stu-id="ca8b4-138">It lets users enter a location to find stores that are nearby.</span></span> <span data-ttu-id="ca8b4-139">A modullal kapcsolatos további tudnivalókat lásd: [Üzletkiválasztó modul](store-selector.md).</span><span class="sxs-lookup"><span data-stu-id="ca8b4-139">For more information on this module, see [Store selector module](store-selector.md).</span></span>

## <a name="module-properties"></a><span data-ttu-id="ca8b4-140">Modul tulajdonságai</span><span class="sxs-lookup"><span data-stu-id="ca8b4-140">Module properties</span></span>

<span data-ttu-id="ca8b4-141">A kosármodulok következő beállításai konfigurálhatók a **Webhelybeállítások \> Bővítmények** pontban:</span><span class="sxs-lookup"><span data-stu-id="ca8b4-141">The following cart module settings can be configured at **Site Settings \> Extensions**:</span></span>

- <span data-ttu-id="ca8b4-142">**Maximális mennyiség** – Ez a tulajdonság megadja az egyes cikkek kosárhoz adható maximális számát.</span><span class="sxs-lookup"><span data-stu-id="ca8b4-142">**Maximum quantity** – This property is used to specify the maximum number of each item that can be added to the cart.</span></span> <span data-ttu-id="ca8b4-143">Előfordulhat például, hogy egy kiskereskedő úgy dönt, hogy egyetlen tranzakcióban csak 10 terméket lehet értékesíteni.</span><span class="sxs-lookup"><span data-stu-id="ca8b4-143">For example, a retailer might decide that only 10 of each product can be sold in a single transaction.</span></span>
- <span data-ttu-id="ca8b4-144">**Készlet** – A készletbeállítások alkalmazásával kapcsolatban a következő témakör tartalmaz további tájékoztatást: [Készletbeállítások alkalmazása](inventory-settings.md).</span><span class="sxs-lookup"><span data-stu-id="ca8b4-144">**Inventory** – For information about how to apply inventory settings, see [Apply inventory settings](inventory-settings.md).</span></span>
- <span data-ttu-id="ca8b4-145">**Vissza a vásárláshoz** – a tulajdonság a **Vissza a vásárláshoz** linkhez megadott útvonal meghatározására szolgál.</span><span class="sxs-lookup"><span data-stu-id="ca8b4-145">**Back to shopping** – This property is used to specify the route for the **Back to shopping** link.</span></span> <span data-ttu-id="ca8b4-146">Az útvonal a webhely szintjén konfigurálható, amely lehetővé teszi, hogy a kiskereskedők visszavigyék a vevőt a kezdőlapra vagy más lapjára.</span><span class="sxs-lookup"><span data-stu-id="ca8b4-146">The route can be configured at the site level, allowing retailers to take the customer back to the home page or any other page on the site.</span></span>

## <a name="commerce-scale-unit-interaction"></a><span data-ttu-id="ca8b4-147">Commerce Scale Unit-interakció</span><span class="sxs-lookup"><span data-stu-id="ca8b4-147">Commerce Scale Unit interaction</span></span>

<span data-ttu-id="ca8b4-148">A kosármodul a termék adatait a Commerce Scale Unit API-k használatával olvassa be.</span><span class="sxs-lookup"><span data-stu-id="ca8b4-148">The cart module retrieves product information by using Commerce Scale Unit APIs.</span></span> <span data-ttu-id="ca8b4-149">A böngésző cookie-jából származó kosárazonosító szolgál az összes termékadat beolvasására a Commerce Scale Unitról.</span><span class="sxs-lookup"><span data-stu-id="ca8b4-149">The cart ID from the browser cookie is used to retrieve all the product information from Commerce Scale Unit.</span></span>

## <a name="add-a-cart-module-to-a-page"></a><span data-ttu-id="ca8b4-150">Kosármodul felvétele egy oldalra</span><span class="sxs-lookup"><span data-stu-id="ca8b4-150">Add a cart module to a page</span></span>

<span data-ttu-id="ca8b4-151">A kosármodul új oldalra való felvételéhez és a kötelező tulajdonságok beállításához hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="ca8b4-151">To add a cart module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="ca8b4-152">Lépjen a **Töredékek** pontra, és válassza az **Új** lehetőséget új töredék létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="ca8b4-152">Go to **Fragments**, and select **New** to create a new fragment.</span></span>
1. <span data-ttu-id="ca8b4-153">Az **Új töredék** párbeszédpanelen válassza ki a **Kosár** modult.</span><span class="sxs-lookup"><span data-stu-id="ca8b4-153">In the **New fragment** dialog box, select the **Cart** module.</span></span>
1. <span data-ttu-id="ca8b4-154">A **Töredék neve** pontban adja meg a **Kosár töredék** nevet, ezután válassza az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ca8b4-154">Under **Fragment name**, enter the name **Cart fragment**, and then select **OK**.</span></span>
1. <span data-ttu-id="ca8b4-155">Válassza ki **Kosár** helyet.</span><span class="sxs-lookup"><span data-stu-id="ca8b4-155">Select the **Cart** slot.</span></span>
1. <span data-ttu-id="ca8b4-156">A jobb oldali tulajdonságok ablaktáblán válassza ki a ceruza szimbólumot, adja meg a címsor szövegét a mezőben, majd jelölje be a pipa jelet.</span><span class="sxs-lookup"><span data-stu-id="ca8b4-156">In the properties pane on the right, select the pencil symbol, enter heading text in the field, and then select the check mark symbol.</span></span>
1. <span data-ttu-id="ca8b4-157">A **Kosár** helyben válassza a három pont (**…**) gombot, majd válassza az **Modul hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="ca8b4-157">In the **Cart** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="ca8b4-158">A **Modul hozzáadása** párbeszédpanelen válassza ki az **Áruházválasztó** modult, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="ca8b4-158">In the **Add Module** dialog box, select the **Store selector** module, and then select **OK**.</span></span>
1. <span data-ttu-id="ca8b4-159">Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot a töredék ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.</span><span class="sxs-lookup"><span data-stu-id="ca8b4-159">Select **Save**, select **Finish editing** to check in the fragment, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="ca8b4-160">Lépjen a **Sablonok** pontra, majd új sablon készítéséhez válassza az **Új** elemet.</span><span class="sxs-lookup"><span data-stu-id="ca8b4-160">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="ca8b4-161">Az **Új sablon** párbeszédablakban a **Sablon neve** alatt adja meg a sablon nevét.</span><span class="sxs-lookup"><span data-stu-id="ca8b4-161">In the **New Template** dialog box, under **Template name**, enter a name for the template.</span></span>
1. <span data-ttu-id="ca8b4-162">A Vázlatablakban válassza ki a **Törzs** helyét, válassza a három pont (**…**) majd válassza a **Töredék hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="ca8b4-162">In the outline tree, select the **Body** slot, select the ellipsis (**...**), and then select **Add fragment**.</span></span>
1. <span data-ttu-id="ca8b4-163">A **Töredék kiválasztása** párbeszédpanelen válassza ki a **Kosártöredék** nevű töredékét, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="ca8b4-163">In the **Select fragment** dialog box, select the **Cart fragment** fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="ca8b4-164">Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot a sablon ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.</span><span class="sxs-lookup"><span data-stu-id="ca8b4-164">Select **Save**, select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="ca8b4-165">Lépjen az **Oldalak** pontra, majd válassza az **Új** lehetőséget új oldal létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="ca8b4-165">Go to **Pages**, and select **New** to create a new page.</span></span>
1. <span data-ttu-id="ca8b4-166">A **Sablon kiválasztása** párbeszédpanelen válassza ki a létrehozott sablont, adjon meg egy oldalnevet, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="ca8b4-166">In the **Choose a template** dialog box, select the template that you created, enter a page name, and then select **OK**.</span></span>
1. <span data-ttu-id="ca8b4-167">Válassza a **Mentés** lehetőséget, majd az oldal előnézetének megtekintéséhez az **Előnézet** elemet.</span><span class="sxs-lookup"><span data-stu-id="ca8b4-167">Select **Save**, and then select **Preview** to preview the page.</span></span>
1. <span data-ttu-id="ca8b4-168">Válassza a **Szerkesztés befejezése** parancsot az oldal ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.</span><span class="sxs-lookup"><span data-stu-id="ca8b4-168">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ca8b4-169">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="ca8b4-169">Additional resources</span></span>

[<span data-ttu-id="ca8b4-170">Kosárikon modul</span><span class="sxs-lookup"><span data-stu-id="ca8b4-170">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="ca8b4-171">Fizetésmodul</span><span class="sxs-lookup"><span data-stu-id="ca8b4-171">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="ca8b4-172">Fizetési modul</span><span class="sxs-lookup"><span data-stu-id="ca8b4-172">Payment module</span></span>](payment-module.md)

[<span data-ttu-id="ca8b4-173">Szállítási cím modul</span><span class="sxs-lookup"><span data-stu-id="ca8b4-173">Shipping address module</span></span>](ship-address-module.md)

[<span data-ttu-id="ca8b4-174">Szállítási lehetőségek modul</span><span class="sxs-lookup"><span data-stu-id="ca8b4-174">Delivery options module</span></span>](delivery-options-module.md)

[<span data-ttu-id="ca8b4-175">Rendelési részletek modul</span><span class="sxs-lookup"><span data-stu-id="ca8b4-175">Order details module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="ca8b4-176">Ajándékutalvány modul</span><span class="sxs-lookup"><span data-stu-id="ca8b4-176">Gift card module</span></span>](add-giftcard.md)

[<span data-ttu-id="ca8b4-177">Kiskereskedelmi csatornák készletelérhetőségének kiszámítása</span><span class="sxs-lookup"><span data-stu-id="ca8b4-177">Calculate inventory availability for retail channels</span></span>](calculated-inventory-retail-channels.md)
