---
title: Kosármodul
description: Ez a témakör a kosármodulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
manager: annbe
ms.date: 05/28/2020
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
ms.openlocfilehash: 3ba46fd90507a9cf8da92598c8449a2e553da352
ms.sourcegitcommit: b52477b7d0d52102a7ca2fb95f4ebfa30ecd9f54
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/29/2020
ms.locfileid: "3411273"
---
# <a name="cart-module"></a><span data-ttu-id="bad87-103">Kosármodul</span><span class="sxs-lookup"><span data-stu-id="bad87-103">Cart module</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="bad87-104">Ez a témakör a kosármodulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="bad87-104">This topic covers cart modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="bad87-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="bad87-105">Overview</span></span>

<span data-ttu-id="bad87-106">A kosármodullal megjeleníthetők a kosárba tett cikkek, mielőtt az ügyfél a pénztárra lép.</span><span class="sxs-lookup"><span data-stu-id="bad87-106">A cart module shows the items that have been added to the cart before the customer proceeds to checkout.</span></span> <span data-ttu-id="bad87-107">A modul a rendelés összegzését is megjeleníti, és lehetővé teszi, hogy a vevő hozzáadja vagy eltávolítsa a promóciós kódokat.</span><span class="sxs-lookup"><span data-stu-id="bad87-107">The module also shows an order summary and lets the customer apply or remove promotional codes.</span></span>

<span data-ttu-id="bad87-108">A kosár modul támogatja a bejelentkezett fizetést és a vendégfizetést.</span><span class="sxs-lookup"><span data-stu-id="bad87-108">The cart module supports signed-in checkout and guest checkout.</span></span> <span data-ttu-id="bad87-109">Támogatja a **Vissza a vásárláshoz** hivatkozást.</span><span class="sxs-lookup"><span data-stu-id="bad87-109">It also supports a **Back to shopping** link.</span></span> <span data-ttu-id="bad87-110">A hivatkozáshoz vezető útvonalat a **Webhely-beállítások \> Bővítmények \> Útvonala** oldalon.</span><span class="sxs-lookup"><span data-stu-id="bad87-110">You can configure the route for this link at **Site Settings \> Extensions \> Routes**.</span></span>

<span data-ttu-id="bad87-111">A kosár modul a kosár azonosítója alapján jeleníti meg az adatokat, ami a webhely teljes területén elérhető böngésző cookie.</span><span class="sxs-lookup"><span data-stu-id="bad87-111">The cart module renders data based on the cart ID, which is a browser cookie available throughout the site.</span></span> 

<span data-ttu-id="bad87-112">A következő kép a Fabrikam webhelyen használt kosároldal egy példáját jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="bad87-112">The following image shows an example of a cart page on the Fabrikam site.</span></span>

![Példa egy kosármodulra](./media/cart2.PNG)

## <a name="cart-module-properties-and-slots"></a><span data-ttu-id="bad87-114">A kosármodul tulajdonságai és helyei</span><span class="sxs-lookup"><span data-stu-id="bad87-114">Cart module properties and slots</span></span>

<span data-ttu-id="bad87-115">A kosár modulnak van egy **Címsor** tulajdonsága, amelyet olyan értékekre állíthat, mint **Bevásárlótáska** vagy **Kosárban levő cikkek**.</span><span class="sxs-lookup"><span data-stu-id="bad87-115">The cart module has a **Heading** property that can be set to values such as **Shopping bag** and **Items in your cart**.</span></span> 

## <a name="modules-that-can-be-used-in-a-cart-module"></a><span data-ttu-id="bad87-116">A kosármodulban használható modulok</span><span class="sxs-lookup"><span data-stu-id="bad87-116">Modules that can be used in a cart module</span></span>

- <span data-ttu-id="bad87-117">**Szövegblokk** – Ez a modul a kosár modulban használható egyéni üzenetküldést támogatja.</span><span class="sxs-lookup"><span data-stu-id="bad87-117">**Text block** – This module supports custom messaging in the cart module.</span></span> <span data-ttu-id="bad87-118">Az üzeneteket a tartalomkezelő rendszer (CMS) vezérli.</span><span class="sxs-lookup"><span data-stu-id="bad87-118">The messages are driven by the content management system (CMS).</span></span> <span data-ttu-id="bad87-119">Bármilyen üzenet megadható, például: „A rendeléssel kapcsolatos problémák esetén hívja az 1-800-Fabrikam számot”.</span><span class="sxs-lookup"><span data-stu-id="bad87-119">Any message can be added, such as "For issues with your order, contact 1-800-Fabrikam."</span></span>
- <span data-ttu-id="bad87-120">**Áruházválasztó** – Ez a modul felsorolja azokat a közeli áruházakat, ahol a cikkek elérhetők és felvehetők.</span><span class="sxs-lookup"><span data-stu-id="bad87-120">**Store selector** – This module shows a list of nearby stores where an item is available for pickup.</span></span> <span data-ttu-id="bad87-121">Ez lehetővé teszi a felhasználók számára, hogy a közelben levő üzleteket megtalálják.</span><span class="sxs-lookup"><span data-stu-id="bad87-121">It lets users enter a location to find stores that are nearby.</span></span> <span data-ttu-id="bad87-122">A modullal kapcsolatos további tudnivalókat lásd: [Üzletkiválasztó modul](store-selector.md).</span><span class="sxs-lookup"><span data-stu-id="bad87-122">For more information on this module, see [Store selector module](store-selector.md).</span></span>

## <a name="module-properties"></a><span data-ttu-id="bad87-123">Modul tulajdonságai</span><span class="sxs-lookup"><span data-stu-id="bad87-123">Module properties</span></span>

<span data-ttu-id="bad87-124">A kosármodulok következő beállításai konfigurálhatók a **Webhelybeállítások \> Bővítmények** pontban:</span><span class="sxs-lookup"><span data-stu-id="bad87-124">The following cart module settings can be configured at **Site Settings \> Extensions**:</span></span>

- <span data-ttu-id="bad87-125">**Maximális mennyiség** – Ez a tulajdonság megadja az egyes cikkek kosárhoz adható maximális számát.</span><span class="sxs-lookup"><span data-stu-id="bad87-125">**Maximum quantity** – This property is used to specify the maximum number of each item that can be added to the cart.</span></span> <span data-ttu-id="bad87-126">Előfordulhat például, hogy egy kiskereskedő úgy dönt, hogy egyetlen tranzakcióban csak 10 terméket lehet értékesíteni.</span><span class="sxs-lookup"><span data-stu-id="bad87-126">For example, a retailer might decide that only 10 of each product can be sold in a single transaction.</span></span>
- <span data-ttu-id="bad87-127">**Készlet** – A készletbeállítások alkalmazásával kapcsolatban a következő témakör tartalmaz további tájékoztatást: [Készletbeállítások alkalmazása](inventory-settings.md).</span><span class="sxs-lookup"><span data-stu-id="bad87-127">**Inventory** – For information about how to apply inventory settings, see [Apply inventory settings](inventory-settings.md).</span></span>
- <span data-ttu-id="bad87-128">**Vissza a vásárláshoz** – a tulajdonság a **Vissza a vásárláshoz** linkhez megadott útvonal meghatározására szolgál.</span><span class="sxs-lookup"><span data-stu-id="bad87-128">**Back to shopping** – This property is used to specify the route for the **Back to shopping** link.</span></span> <span data-ttu-id="bad87-129">Az útvonal a webhely szintjén konfigurálható, amely lehetővé teszi, hogy a kiskereskedők visszavigyék a vevőt a kezdőlapra vagy más lapjára.</span><span class="sxs-lookup"><span data-stu-id="bad87-129">The route can be configured at the site level, allowing retailers to take the customer back to the home page or any other page on the site.</span></span>

## <a name="commerce-scale-unit-interaction"></a><span data-ttu-id="bad87-130">Commerce Scale Unit-interakció</span><span class="sxs-lookup"><span data-stu-id="bad87-130">Commerce Scale Unit interaction</span></span>

<span data-ttu-id="bad87-131">A kosármodul a termék adatait a Commerce Scale Unit API-k használatával olvassa be.</span><span class="sxs-lookup"><span data-stu-id="bad87-131">The cart module retrieves product information by using Commerce Scale Unit APIs.</span></span> <span data-ttu-id="bad87-132">A böngésző cookie-jából származó kosárazonosító szolgál az összes termékadat beolvasására a Commerce Scale Unitról.</span><span class="sxs-lookup"><span data-stu-id="bad87-132">The cart ID from the browser cookie is used to retrieve all the product information from Commerce Scale Unit.</span></span>

## <a name="add-a-cart-module-to-a-page"></a><span data-ttu-id="bad87-133">Kosármodul felvétele egy oldalra</span><span class="sxs-lookup"><span data-stu-id="bad87-133">Add a cart module to a page</span></span>

<span data-ttu-id="bad87-134">A kosármodul új oldalra való felvételéhez és a kötelező tulajdonságok beállításához hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="bad87-134">To add a cart module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="bad87-135">Lépjen az **Oldaltöredékek** pontra, majd válassza az **Új** lehetőséget új töredék létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="bad87-135">Go to **Page Fragments**, and select **New** to create a new fragment.</span></span>
1. <span data-ttu-id="bad87-136">Az **Új oldaltöredék** párbeszédablakban válassza ki a **Kosár** modult.</span><span class="sxs-lookup"><span data-stu-id="bad87-136">In the **New Page Fragment** dialog box, select the **Cart** module.</span></span>
1. <span data-ttu-id="bad87-137">Az **Oldaltöredék neve** pontban adja meg a **Kosár töredék** nevét, majd válassza az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="bad87-137">Under **Page Fragment Name**, enter the name **Cart fragment**, and then select **OK**.</span></span>
1. <span data-ttu-id="bad87-138">Válassza ki **Kosár** helyet.</span><span class="sxs-lookup"><span data-stu-id="bad87-138">Select the **Cart** slot.</span></span>
1. <span data-ttu-id="bad87-139">A jobb oldali tulajdonságok ablaktáblán válassza ki a ceruza szimbólumot, adja meg a címsor szövegét a mezőben, majd jelölje be a pipa jelet.</span><span class="sxs-lookup"><span data-stu-id="bad87-139">In the properties pane on the right, select the pencil symbol, enter heading text in the field, and then select the check mark symbol.</span></span>
1. <span data-ttu-id="bad87-140">A **Kosár** helyben válassza a három pont (**…**) gombot, majd válassza az **Modul hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="bad87-140">In the **Cart** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="bad87-141">A **Modul hozzáadása** párbeszédpanelen válassza ki az **Áruházválasztó** modult, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="bad87-141">In the **Add Module** dialog box, select the **Store selector** module, and then select **OK**.</span></span>
1. <span data-ttu-id="bad87-142">Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot a töredék ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.</span><span class="sxs-lookup"><span data-stu-id="bad87-142">Select **Save**, select **Finish editing** to check in the fragment, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="bad87-143">Lépjen a **Sablonok** pontra, majd új sablon készítéséhez válassza az **Új** elemet.</span><span class="sxs-lookup"><span data-stu-id="bad87-143">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="bad87-144">Az **Új sablon** párbeszédablakban a **Sablon neve** alatt adja meg a sablon nevét.</span><span class="sxs-lookup"><span data-stu-id="bad87-144">In the **New Template** dialog box, under **Template name**, enter a name for the template.</span></span>
1. <span data-ttu-id="bad87-145">A Vázlatablakban válassza ki a **Törzs** helyét, válassza a három pont (**…**) majd válassza a **Töredék hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="bad87-145">In the outline tree, select the **Body** slot, select the ellipsis (**...**), and then select **Add Fragment**.</span></span>
1. <span data-ttu-id="bad87-146">Az **Oldaltöredék kiválasztása** párbeszédpanelen válassza ki a **Kosártöredék** töredékét, amelyet korábban hozott létre majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="bad87-146">In the **Select Page Fragment** dialog box, select the **Cart fragment** fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="bad87-147">Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot a sablon ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.</span><span class="sxs-lookup"><span data-stu-id="bad87-147">Select **Save**, select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="bad87-148">Lépjen az **Oldalak** pontra, majd válassza az **Új** lehetőséget új oldal létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="bad87-148">Go to **Pages**, and select **New** to create a new page.</span></span>
1. <span data-ttu-id="bad87-149">A **Sablon kiválasztása** párbeszédpanelen válassza ki a létrehozott sablont, adjon meg egy oldalnevet, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="bad87-149">In the **Choose a template** dialog box, select the template that you created, enter a page name, and then select **OK**.</span></span>
1. <span data-ttu-id="bad87-150">Válassza a **Mentés** lehetőséget, majd az oldal előnézetének megtekintéséhez az **Előnézet** elemet.</span><span class="sxs-lookup"><span data-stu-id="bad87-150">Select **Save**, and then select **Preview** to preview the page.</span></span>
1. <span data-ttu-id="bad87-151">Válassza a **Szerkesztés befejezése** parancsot az oldal ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.</span><span class="sxs-lookup"><span data-stu-id="bad87-151">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="bad87-152">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="bad87-152">Additional resources</span></span>

[<span data-ttu-id="bad87-153">Kezdőcsomag áttekintése</span><span class="sxs-lookup"><span data-stu-id="bad87-153">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="bad87-154">Tárolómodul</span><span class="sxs-lookup"><span data-stu-id="bad87-154">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="bad87-155">Üzletkiválasztó modul</span><span class="sxs-lookup"><span data-stu-id="bad87-155">Store selector module</span></span>](store-selector.md)

[<span data-ttu-id="bad87-156">Vásárlásmező-modul</span><span class="sxs-lookup"><span data-stu-id="bad87-156">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="bad87-157">Kosárikon modul</span><span class="sxs-lookup"><span data-stu-id="bad87-157">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="bad87-158">Fizetésmodul</span><span class="sxs-lookup"><span data-stu-id="bad87-158">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="bad87-159">Rendelésmegerősítési modul</span><span class="sxs-lookup"><span data-stu-id="bad87-159">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="bad87-160">Fejlécmodul</span><span class="sxs-lookup"><span data-stu-id="bad87-160">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="bad87-161">Láblécmodul</span><span class="sxs-lookup"><span data-stu-id="bad87-161">Footer module</span></span>](author-footer-module.md)

[<span data-ttu-id="bad87-162">Kiskereskedelmi csatornák készletelérhetőségének kiszámítása</span><span class="sxs-lookup"><span data-stu-id="bad87-162">Calculate inventory availability for retail channels</span></span>](calculated-inventory-retail-channels.md)
