---
title: Fejlécmodul
description: Ez a témakör a fejlécmodulokkal foglalkozik, és bemutatja, hogy hogyan lehet oldalfejléceket létrehozni a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar
manager: annbe
ms.date: 05/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar-ms
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: a5f7ad7d9c5ff63c3c3a8fe38275eec0d138891d
ms.sourcegitcommit: b52477b7d0d52102a7ca2fb95f4ebfa30ecd9f54
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/29/2020
ms.locfileid: "3411208"
---
# <a name="header-module"></a><span data-ttu-id="27749-103">Fejlécmodul</span><span class="sxs-lookup"><span data-stu-id="27749-103">Header module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="27749-104">Ez a témakör a fejlécmodulokkal foglalkozik, és bemutatja, hogy hogyan lehet oldalfejléceket létrehozni a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="27749-104">This topic covers header modules and describes how to create page headers in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="27749-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="27749-105">Overview</span></span>

<span data-ttu-id="27749-106">A Dynamics 365 Commerce szolgáltatásban egy oldalfejléc több modulból áll, például a fejlécből, a navigációs menüből, a keresésből, a promóciós szalagcímből és a cookie-hozzájárulás moduljaiból.</span><span class="sxs-lookup"><span data-stu-id="27749-106">In Dynamics 365 Commerce, a page header comprises multiple modules, such as the header, navigation menu, search, promo banner, and cookie consent modules.</span></span> 

<span data-ttu-id="27749-107">A fejlécmodul tartalmaz egy webhelyemblémát, a navigációs hierarchiára mutató hivatkozásokat, a webhely egyéb oldalaira mutató hivatkozásokat, egy kosár-szimbólumot, egy kívánságlista szimbólumot, bejelentkezési beállításokat és a keresési sávot.</span><span class="sxs-lookup"><span data-stu-id="27749-107">The header module includes a site logo, links to the navigation hierarchy, links to other pages on the site, a cart symbol, a wishlist symbol, sign-in options, and the search bar.</span></span> <span data-ttu-id="27749-108">A program automatikusan optimalizálja a fejlécmodult arra az eszközre, amelyről a webhelyet megtekintik (azaz egy asztali eszközre vagy egy mobileszközre).</span><span class="sxs-lookup"><span data-stu-id="27749-108">A header module is automatically optimized for the device that the site is being viewed on (in other words, for a desktop device or a mobile device).</span></span> <span data-ttu-id="27749-109">Egy mobileszköz esetében például a navigációs sáv össze van csukva egy **Menü** gombba (amelyet néha *hamburger menünek* neveznek).</span><span class="sxs-lookup"><span data-stu-id="27749-109">For example, on a mobile device, the navigation bar is collapsed into a **Menu** button (which is sometimes referred to as a *hamburger menu*).</span></span>

<span data-ttu-id="27749-110">A következő kép egy kezdőoldalon használt címsormodul egy példáját jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="27749-110">The following image shows an example of a header module on a home page.</span></span>

![Példa egy címsor modulra](./media/ecommerce-header.png)

## <a name="properties-of-a-header-module"></a><span data-ttu-id="27749-112">Fejlécmodul tulajdonságai</span><span class="sxs-lookup"><span data-stu-id="27749-112">Properties of a header module</span></span>

<span data-ttu-id="27749-113">A fejlécmodul az **Emblémakép**, **Embléma hivatkozása** és **Saját fiókhivatkozások** tulajdonságokat támogatja.</span><span class="sxs-lookup"><span data-stu-id="27749-113">A header module supports **Logo image**, **Logo link**, and **My account links** properties.</span></span> 

<span data-ttu-id="27749-114">Az **Emblémakép** és az **Emblémahivatkozás** tulajdonságokkal adható meg az embléma az oldalon.</span><span class="sxs-lookup"><span data-stu-id="27749-114">The **Logo image** and **Logo link** properties are used to define a logo on the page.</span></span> <span data-ttu-id="27749-115">További tudnivalók: [Embléma hozzáadása](add-logo.md).</span><span class="sxs-lookup"><span data-stu-id="27749-115">For more information, see [Add a logo](add-logo.md).</span></span> 

<span data-ttu-id="27749-116">A **Saját fiókhivatkozások** tulajdonsággal megadhatók olyan fiókoldalak, amelyekre mutató hivatkozásokat a webhelytulajdonos meg akar jeleníteni a fejlécben.</span><span class="sxs-lookup"><span data-stu-id="27749-116">The **My account links** property can be used to define account pages that the site owner wants to show quick links for in the header.</span></span>

## <a name="modules-that-are-available-in-a-header-module"></a><span data-ttu-id="27749-117">A fejlécmodulban elérhető modulok</span><span class="sxs-lookup"><span data-stu-id="27749-117">Modules that are available in a header module</span></span>

<span data-ttu-id="27749-118">A következő modulban használható a fejlécmodulban:</span><span class="sxs-lookup"><span data-stu-id="27749-118">The following modules can be used in a header module:</span></span>

- <span data-ttu-id="27749-119">**Navigációs menü** – A navigációs menü a csatorna navigációs hierarchiáját és más statikus navigációs hivatkozásokat jelenít meg.</span><span class="sxs-lookup"><span data-stu-id="27749-119">**Navigation menu** – The navigation menu represents the channel navigation hierarchy and other static navigation links.</span></span> <span data-ttu-id="27749-120">A csatorna navigációs hierarchiája a Dynamics 365 Commerce alkalmazásban állítható be.</span><span class="sxs-lookup"><span data-stu-id="27749-120">The channel navigation hierarchy can be configured in Dynamics 365 Commerce.</span></span> <span data-ttu-id="27749-121">A navigációs menü egy **navigációs forrás** tulajdonsággal rendelkezik, amellyel megadhatók a Retail Server navigációs menüelemei és a statikus menüelemek forrásként.</span><span class="sxs-lookup"><span data-stu-id="27749-121">The navigation menu has a **Navigation Source** property that is used to specify Retail Server navigation menu items and static menu items as a source.</span></span> <span data-ttu-id="27749-122">Ha a statikus menüelemek forrásként vannak megadva, akkor a webhely más lapjaihoz kapcsolódó relatív hivatkozásokat is meg lehet adni.</span><span class="sxs-lookup"><span data-stu-id="27749-122">If static menu items are specified as a source, relative links to other pages on the site can be provided.</span></span> <span data-ttu-id="27749-123">A konfigurált elemek ezután fejlécnavigációként jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="27749-123">Configured items then appear as header navigation.</span></span> 

- <span data-ttu-id="27749-124">**Keresősáv** – A keresőmodul lehetővé teszi a felhasználók számára, hogy keresési kifejezéseket írjanak be, amelyekkel termékeket kereshetnek.</span><span class="sxs-lookup"><span data-stu-id="27749-124">**Search** – The search module lets users enter search terms to search for products.</span></span> <span data-ttu-id="27749-125">Az alapértelmezett keresési lap URL-jét és a keresési lekérdezések paramétereit a **Webhelybeállítások \> Bővítmények** részben kell megadni.</span><span class="sxs-lookup"><span data-stu-id="27749-125">The URL of the default search page and the search query parameters must be provided at **Site Settings \> Extensions**.</span></span> <span data-ttu-id="27749-126">A keresési modulnak van olyan tulajdonsága, amely lehetővé teszi a keresési gomb vagy címke elrejtését szükség esetén.</span><span class="sxs-lookup"><span data-stu-id="27749-126">The search module has properties that let you suppress the search button or label as you require.</span></span> <span data-ttu-id="27749-127">A keresési modul olyan automatikus javaslati beállításokat is támogat, mint a termék, a kulcsszó és a kategória keresési eredményei.</span><span class="sxs-lookup"><span data-stu-id="27749-127">The search module also supports auto-suggest options, such as product, keyword, and category search results.</span></span>

- <span data-ttu-id="27749-128">**Kosár ikon** - A kosár ikon modul a kosárikont jeleníti meg, amely a kosárban lévő cikkek számát mutatja bármely időpontban.</span><span class="sxs-lookup"><span data-stu-id="27749-128">**Cart icon** - The cart icon module represents the cart icon, which shows the number of items in the cart at any given time.</span></span> <span data-ttu-id="27749-129">A további tudnivalókat lásd a [kosár ikon modul](cart-icon-module.md) részben.</span><span class="sxs-lookup"><span data-stu-id="27749-129">For more information, see [Cart icon module](cart-icon-module.md).</span></span>

## <a name="create-a-header-module-for-a-page"></a><span data-ttu-id="27749-130">Fejlécmodul létrehozása egy oldalhoz</span><span class="sxs-lookup"><span data-stu-id="27749-130">Create a header module for a page</span></span>

<span data-ttu-id="27749-131">Fejlécmodul létrehozásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="27749-131">To create a header module, follow these steps.</span></span>

1. <span data-ttu-id="27749-132">Lépjen az **Oldaltöredékek** pontra, majd válassza az **Új** lehetőséget új töredék létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="27749-132">Go to **Page Fragments**, and select **New** to create a new fragment.</span></span>
1. <span data-ttu-id="27749-133">Az **Új oldaltöredék** párbeszédpanelen jelölje ki a **Tároló** modult, adja meg a laptöredék nevét, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="27749-133">In the **New Page Fragment** dialog box, select the **Container** module, enter a name for the page fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="27749-134">Válassza ki az **Alapértelmezett tároló** helyet, majd a jobb oldali tulajdonságok ablaktáblán állítsa be a **Szélesség** tulajdonságot **Tároló kitöltése** értékre.</span><span class="sxs-lookup"><span data-stu-id="27749-134">Select the **Default container** slot, and then, in the properties pane on the right, set the **Width** property to **Fill container**.</span></span>
1. <span data-ttu-id="27749-135">Az **Alapértelmezett tároló** helyben válassza a három pont (**…**) gombot, majd válassza az **Modul hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="27749-135">In the **Default container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="27749-136">A **Modul hozzáadása** párbeszédpanelen válassza a **Promóciós banner** és a **Süti beleegyezés** modulokat majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="27749-136">In the **Add Module** dialog box, select the **Promo banner** and **Cookie consent** modules, and then select **OK**.</span></span>
1. <span data-ttu-id="27749-137">Az **Alapértelmezett tároló** helyben válassza a három pont (**…**) gombot, majd válassza az **Modul hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="27749-137">In the **Default container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="27749-138">A **Modul hozzáadása** párbeszédpanelen válassza ki az **Tároló** modult, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="27749-138">In the **Add Module** dialog box, select the **Container** module, and then select **OK**.</span></span>
1. <span data-ttu-id="27749-139">Válassza ki az **Tároló** helyet, majd a jobb oldali tulajdonságok ablaktáblán állítsa be a **Szélesség** tulajdonságot **Tároló kitöltése** értékre.</span><span class="sxs-lookup"><span data-stu-id="27749-139">Select the **Container** slot, and then, in the properties pane on the right, set the **Width** property to **Fill container**.</span></span>
1. <span data-ttu-id="27749-140">Az **Tároló** helyben válassza a három pont (**…**) gombot, majd válassza az **Modul hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="27749-140">In the **Container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="27749-141">A **Modul hozzáadása** párbeszédpanelen válassza ki a **Címsor** modult, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="27749-141">In the **Add Module** dialog box, select the **Header** module, and then select **OK**.</span></span>
1. <span data-ttu-id="27749-142">Válassza ki a három pont (**...**) elemet a címsor modul **Navigációs menü** helyén, amely tartalmazza a váráslásmező modult, majd válassza a **Modul hozzáadása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="27749-142">In the **Navigation menu** slot of the header module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="27749-143">A **Modul hozzáadása** párbeszédpanelen válassza ki a **Navigációs menü** modult, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="27749-143">In the **Add Module** dialog box, select the **Navigation menu** module, and then select **OK**.</span></span>
1. <span data-ttu-id="27749-144">A navigációs menü modul tulajdonságlapján konfigurálja a tulajdonságokat igény szerint.</span><span class="sxs-lookup"><span data-stu-id="27749-144">In the property pane for the navigation menu module, configure the properties as needed.</span></span>
1. <span data-ttu-id="27749-145">Válassza ki a három pont (**...**) elemet a címsor modul **Keresés** helyén, amely tartalmazza a váráslásmező modult, majd válassza a **Modul hozzáadása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="27749-145">In the **Search** slot of the header module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="27749-146">A **Modul hozzáadása** párbeszédpanelen válassza ki a **Keresés** modult, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="27749-146">In the **Add Module** dialog box, select the **Search** module, and then select **OK**.</span></span>
1. <span data-ttu-id="27749-147">A keresés modul tulajdonságlapján konfigurálja a tulajdonságokat igény szerint.</span><span class="sxs-lookup"><span data-stu-id="27749-147">In the property pane for the search module, configure the properties as needed.</span></span>
1. <span data-ttu-id="27749-148">Válassza ki a három pont (**...**) elemet a címsor modul **Kosárikon** helyén, amely tartalmazza a váráslásmező modult, majd válassza a **Modul hozzáadása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="27749-148">In the **Cart icon** slot of the header module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="27749-149">A **Modul hozzáadása** párbeszédpanelen válassza ki az **Kosárikon** modult, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="27749-149">In the **Add Module** dialog box, select the **Cart icon** module, and then select **OK**.</span></span>
1. <span data-ttu-id="27749-150">A kosárikon modul tulajdonságlapján konfigurálja a tulajdonságokat igény szerint.</span><span class="sxs-lookup"><span data-stu-id="27749-150">In the property pane for the cart icon module, configure the properties as needed.</span></span> <span data-ttu-id="27749-151">Ha azt szeretné, hogy a kosárikon megjelenítsen egy kosárösszegzést (más néven mini kosarat), amikor a felhasználó fölé viszi az egérmutatót, akkor válassza ki a **Mini kosár megjelenítése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="27749-151">If you want the cart icon to display a cart summary (also known as a mini cart) when users hover over it, select **Show mini cart**.</span></span>
1. <span data-ttu-id="27749-152">Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot a töredék ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.</span><span class="sxs-lookup"><span data-stu-id="27749-152">Select **Save**, select **Finish editing** to check in the fragment, and then select **Publish** to publish it.</span></span>

<span data-ttu-id="27749-153">Ha azt szeretné, hogy minden lapon megjelenjen a fejléc, hajtsa végre az alábbi lépéseket a webhelyhez létrehozott összes oldalsablon esetében.</span><span class="sxs-lookup"><span data-stu-id="27749-153">To help guarantee that a header appears on every page, follow these steps on every page template that is created for the site.</span></span>

1. <span data-ttu-id="27749-154">Az **Alapértelmezett** lap **Címsor** helyén a láblécmodulban adja meg a létrehozott lábléctöredéket.</span><span class="sxs-lookup"><span data-stu-id="27749-154">In the **Header** slot of the **Default page** module, add the footer fragment that you created.</span></span>
1. <span data-ttu-id="27749-155">Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot a sablon ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.</span><span class="sxs-lookup"><span data-stu-id="27749-155">Select **Save**, select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="27749-156">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="27749-156">Additional resources</span></span>

[<span data-ttu-id="27749-157">Kezdőcsomag áttekintése</span><span class="sxs-lookup"><span data-stu-id="27749-157">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="27749-158">Tárolómodul</span><span class="sxs-lookup"><span data-stu-id="27749-158">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="27749-159">Vásárlásmező-modul</span><span class="sxs-lookup"><span data-stu-id="27749-159">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="27749-160">Kosármodul</span><span class="sxs-lookup"><span data-stu-id="27749-160">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="27749-161">Kosárikon modul</span><span class="sxs-lookup"><span data-stu-id="27749-161">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="27749-162">Fizetésmodul</span><span class="sxs-lookup"><span data-stu-id="27749-162">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="27749-163">Rendelésmegerősítési modul</span><span class="sxs-lookup"><span data-stu-id="27749-163">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="27749-164">Fejlécmodul</span><span class="sxs-lookup"><span data-stu-id="27749-164">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="27749-165">Láblécmodul</span><span class="sxs-lookup"><span data-stu-id="27749-165">Footer module</span></span>](author-footer-module.md)
