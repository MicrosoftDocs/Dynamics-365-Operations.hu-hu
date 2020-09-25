---
title: Fejlécmodul
description: Ez a témakör a fejlécmodulokkal foglalkozik, és bemutatja, hogy hogyan lehet oldalfejléceket létrehozni a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar
manager: annbe
ms.date: 08/31/2020
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
ms.openlocfilehash: eb440a8fb67888c9411ad5998fead4d00982b436
ms.sourcegitcommit: 420b9e538f706178f8e1f2786e02f4f400bf2336
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/02/2020
ms.locfileid: "3761224"
---
# <a name="header-module"></a><span data-ttu-id="b2cb5-103">Fejlécmodul</span><span class="sxs-lookup"><span data-stu-id="b2cb5-103">Header module</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="b2cb5-104">Ez a témakör a fejlécmodulokkal foglalkozik, és bemutatja, hogy hogyan lehet oldalfejléceket létrehozni a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="b2cb5-104">This topic covers header modules and describes how to create page headers in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="b2cb5-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="b2cb5-105">Overview</span></span>

<span data-ttu-id="b2cb5-106">A Dynamics 365 Commerce alkalmazásban egy oldalfejléc oldaltöredékként van konfigurálva, amely tartalmazza a fejléc, promóciós banner és cookie-hozzájárulás modulokat.</span><span class="sxs-lookup"><span data-stu-id="b2cb5-106">In Dynamics 365 Commerce, a page header is configured as a page fragment that includes the header, promo banner, and cookie consent modules.</span></span> 

<span data-ttu-id="b2cb5-107">A fejlécmodul tartalmaz egy webhelyemblémát, a navigációs hierarchiára mutató hivatkozásokat, a webhely egyéb oldalaira mutató hivatkozásokat, egy kosárikon modult, egy kívánságlista szimbólumot, bejelentkezési beállításokat és a keresési sávot.</span><span class="sxs-lookup"><span data-stu-id="b2cb5-107">The header module includes a site logo, links to the navigation hierarchy, links to other pages on the site, a cart icon module, a wishlist symbol, sign-in options, and the search bar.</span></span> <span data-ttu-id="b2cb5-108">A program automatikusan optimalizálja a fejlécmodult arra az eszközre, amelyről a webhelyet megtekintik (azaz egy asztali eszközre vagy egy mobileszközre).</span><span class="sxs-lookup"><span data-stu-id="b2cb5-108">A header module is automatically optimized for the device that the site is being viewed on (in other words, for a desktop device or a mobile device).</span></span> <span data-ttu-id="b2cb5-109">Egy mobileszköz esetében például a navigációs sáv össze van csukva egy **Menü** gombba (amelyet néha *hamburger menünek* neveznek).</span><span class="sxs-lookup"><span data-stu-id="b2cb5-109">For example, on a mobile device, the navigation bar is collapsed into a **Menu** button (which is sometimes referred to as a *hamburger menu*).</span></span>

<span data-ttu-id="b2cb5-110">A következő kép egy kezdőoldalon használt címsormodul egy példáját jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="b2cb5-110">The following image shows an example of a header module on a home page.</span></span>

![Példa egy címsor modulra](./media/ecommerce-header.png)

## <a name="properties-of-a-header-module"></a><span data-ttu-id="b2cb5-112">Fejlécmodul tulajdonságai</span><span class="sxs-lookup"><span data-stu-id="b2cb5-112">Properties of a header module</span></span>

<span data-ttu-id="b2cb5-113">A fejlécmodul az **Emblémakép**, **Embléma hivatkozása** és **Saját fiókhivatkozások** tulajdonságokat támogatja.</span><span class="sxs-lookup"><span data-stu-id="b2cb5-113">A header module supports **Logo image**, **Logo link**, and **My account links** properties.</span></span> 

<span data-ttu-id="b2cb5-114">Az **Emblémakép** és az **Emblémahivatkozás** tulajdonságokkal adható meg az embléma az oldalon.</span><span class="sxs-lookup"><span data-stu-id="b2cb5-114">The **Logo image** and **Logo link** properties are used to define a logo on the page.</span></span> <span data-ttu-id="b2cb5-115">További tudnivalók: [Embléma hozzáadása](add-logo.md).</span><span class="sxs-lookup"><span data-stu-id="b2cb5-115">For more information, see [Add a logo](add-logo.md).</span></span> 

<span data-ttu-id="b2cb5-116">A **Saját fiókhivatkozások** tulajdonsággal megadhatók olyan fiókoldalak, amelyekre mutató hivatkozásokat a webhelytulajdonos meg akar jeleníteni a fejlécben.</span><span class="sxs-lookup"><span data-stu-id="b2cb5-116">The **My account links** property can be used to define account pages that the site owner wants to show quick links for in the header.</span></span>

## <a name="modules-that-are-available-within-a-header-module"></a><span data-ttu-id="b2cb5-117">A fejlécmodulban elérhető modulok</span><span class="sxs-lookup"><span data-stu-id="b2cb5-117">Modules that are available within a header module</span></span>

<span data-ttu-id="b2cb5-118">A következő modulban használható a fejlécmodulban:</span><span class="sxs-lookup"><span data-stu-id="b2cb5-118">The following modules can be used in a header module:</span></span>

- <span data-ttu-id="b2cb5-119">**Navigációs menü** – A navigációs menü a csatorna navigációs hierarchiáját és más statikus navigációs hivatkozásokat jelenít meg.</span><span class="sxs-lookup"><span data-stu-id="b2cb5-119">**Navigation menu** – The navigation menu represents the channel navigation hierarchy and other static navigation links.</span></span> <span data-ttu-id="b2cb5-120">További információ: [Navigációs menü modul](nav-menu-module.md).</span><span class="sxs-lookup"><span data-stu-id="b2cb5-120">For more information, see [Navigation menu module](nav-menu-module.md).</span></span>

- <span data-ttu-id="b2cb5-121">**Keresősáv** – A keresőmodul lehetővé teszi a felhasználók számára, hogy keresési kifejezéseket írjanak be, amelyekkel termékeket kereshetnek.</span><span class="sxs-lookup"><span data-stu-id="b2cb5-121">**Search** – The search module lets users enter search terms to search for products.</span></span> <span data-ttu-id="b2cb5-122">Az alapértelmezett keresési lap URL-jét és a keresési lekérdezések paramétereit a **Webhelybeállítások \> Bővítmények** részben kell megadni.</span><span class="sxs-lookup"><span data-stu-id="b2cb5-122">The URL of the default search page and the search query parameters must be provided at **Site Settings \> Extensions**.</span></span> <span data-ttu-id="b2cb5-123">A keresési modulnak van olyan tulajdonsága, amely lehetővé teszi a keresési gomb vagy címke elrejtését szükség esetén.</span><span class="sxs-lookup"><span data-stu-id="b2cb5-123">The search module has properties that let you suppress the search button or label as you require.</span></span> <span data-ttu-id="b2cb5-124">A keresési modul olyan automatikus javaslati beállításokat is támogat, mint a termék, a kulcsszó és a kategória keresési eredményei.</span><span class="sxs-lookup"><span data-stu-id="b2cb5-124">The search module also supports auto-suggest options, such as product, keyword, and category search results.</span></span>

- <span data-ttu-id="b2cb5-125">**Kosár ikon** - A kosár ikon modul a kosárikont jeleníti meg, amely a kosárban lévő cikkek számát mutatja bármely időpontban.</span><span class="sxs-lookup"><span data-stu-id="b2cb5-125">**Cart icon** - The cart icon module represents the cart icon, which shows the number of items in the cart at any given time.</span></span> <span data-ttu-id="b2cb5-126">A további tudnivalókat lásd a [kosár ikon modul](cart-icon-module.md) részben.</span><span class="sxs-lookup"><span data-stu-id="b2cb5-126">For more information, see [Cart icon module](cart-icon-module.md).</span></span>

## <a name="create-a-header-fragment-for-a-page"></a><span data-ttu-id="b2cb5-127">Fejléctöredék létrehozása egy oldalhoz</span><span class="sxs-lookup"><span data-stu-id="b2cb5-127">Create a header fragment for a page</span></span>

<span data-ttu-id="b2cb5-128">Fejléctöredék létrehozásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="b2cb5-128">To create a header fragment, follow these steps.</span></span>

1. <span data-ttu-id="b2cb5-129">Lépjen a **Töredékek** pontra, és válassza az **Új** lehetőséget új töredék létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="b2cb5-129">Go to **Fragments**, and select **New** to create a new fragment.</span></span>
1. <span data-ttu-id="b2cb5-130">Az **Új töredék** párbeszédpanelen válassza ki a **Tároló** modult, adja meg a töredék nevét, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="b2cb5-130">In the **New fragment** dialog box, select the **Container** module, enter a name for the fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="b2cb5-131">Válassza ki az **Alapértelmezett tároló** helyet, majd a jobb oldali tulajdonságok ablaktáblán állítsa be a **Szélesség** tulajdonságot **Képernyő kitöltése** értékre.</span><span class="sxs-lookup"><span data-stu-id="b2cb5-131">Select the **Default container** slot, and then, in the properties pane on the right, set the **Width** property to **Fill Screen**.</span></span>
1. <span data-ttu-id="b2cb5-132">Az **Alapértelmezett tároló** helyben válassza a három pont (**…**) gombot, majd válassza az **Modul hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="b2cb5-132">In the **Default container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="b2cb5-133">A **Modul hozzáadása** párbeszédpanelen válassza a **Cookie hozzájárulás** **Fejléc** és **Promóciós banner** modulokat majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="b2cb5-133">In the **Add Module** dialog box, select the **Cookie consent**, **Header**, and **Promo banner** modules, and then select **OK**.</span></span>
1. <span data-ttu-id="b2cb5-134">A **Promóciós banner** modul tulajdonságok ablaktábláján válassza az **Üzenet hozzáadása** lehetőséget, majd válassza az **Üzenet** elemet.</span><span class="sxs-lookup"><span data-stu-id="b2cb5-134">In the properties pane of the **Promo banner** module, select **Add Message**, and then select **Message**.</span></span>
1. <span data-ttu-id="b2cb5-135">Az **Üzenet** párbeszédpanelen adja meg a szöveget és a promóciós tartalomhoz tartozó hivatkozásokat, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="b2cb5-135">In the **Message** dialog box, add text and links for the promotional content, and then select **OK**.</span></span>
1. <span data-ttu-id="b2cb5-136">A **Cookie-hozzájárulás** modul tulajdonságok ablaktáblájában adja meg a szöveget és a webhelye adatvédelmi oldalára mutató hivatkozást.</span><span class="sxs-lookup"><span data-stu-id="b2cb5-136">In the properties pane of the **Cookie consent** module, add and configure text and a link to the site privacy page.</span></span>
1. <span data-ttu-id="b2cb5-137">Válassza ki a három pont (**...**) elemet a címsor modul **Navigációs menü** helyén, amely tartalmazza a váráslásmező modult, majd válassza a **Modul hozzáadása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b2cb5-137">In the **Navigation menu** slot of the header module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="b2cb5-138">A **Modul hozzáadása** párbeszédpanelen válassza ki a **Navigációs menü** modult, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="b2cb5-138">In the **Add Module** dialog box, select the **Navigation menu** module, and then select **OK**.</span></span>
1. <span data-ttu-id="b2cb5-139">A navigációs menü modul tulajdonság lapján, a **Navigációs menü forrása** alatt válassza a **Retail Server** elemet.</span><span class="sxs-lookup"><span data-stu-id="b2cb5-139">In the property pane for the navigation menu module, under **Source for navigation menu**, select **Retail Server**.</span></span>
1. <span data-ttu-id="b2cb5-140">A navigációs menü modul tulajdonságlapján, a **Statikus menüelemek** területen válassza a **Menüelem hozzáadása** lehetőséget. majd válassza a **Menüelem** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b2cb5-140">In the property pane for the navigation menu module, under **Static menu items**, select **Add Menu item**, and then select **Menu item**.</span></span> 
1. <span data-ttu-id="b2cb5-141">A **Menüelem** párbeszédpanelén, a **Menüelem szövege** mezőbe írja be: „Kapcsolat”.</span><span class="sxs-lookup"><span data-stu-id="b2cb5-141">In the **Menu item** dialog box, under **Menu Item Text** enter "Contact."</span></span>
1. <span data-ttu-id="b2cb5-142">A **Menüelem** párbeszédpanelen a **Menüelem-hivatkozás célja** alatt válassz a **Hivatkozás hozzáadása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b2cb5-142">In the **Menu item** dialog box, under **Menu Item Link target** select **Add a link**.</span></span>
1. <span data-ttu-id="b2cb5-143">A **Hivatkozás hozzáadása** párbeszédpanelen jelölje ki a „Kapcsolat” lap URL-címét, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="b2cb5-143">In the **Add a link** dialog box, select the URL for the site's "Contact" page, and then select **OK**.</span></span>  
1. <span data-ttu-id="b2cb5-144">A **Menüelem** párbeszédpanelen válassza az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b2cb5-144">In the **Menu item** dialog box, select **OK**.</span></span>
1. <span data-ttu-id="b2cb5-145">Válassza ki a három pont (**...**) elemet a címsor modul **Keresés** helyén, amely tartalmazza a váráslásmező modult, majd válassza a **Modul hozzáadása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b2cb5-145">In the **Search** slot of the header module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="b2cb5-146">A **Modul hozzáadása** párbeszédpanelen válassza ki a **Keresés** modult, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="b2cb5-146">In the **Add Module** dialog box, select the **Search** module, and then select **OK**.</span></span>
1. <span data-ttu-id="b2cb5-147">A keresés modul tulajdonságlapján konfigurálja a tulajdonságokat igény szerint.</span><span class="sxs-lookup"><span data-stu-id="b2cb5-147">In the property pane for the search module, configure the properties as needed.</span></span>
1. <span data-ttu-id="b2cb5-148">Válassza ki a három pont (**...**) elemet a címsor modul **Kosárikon** helyén, amely tartalmazza a váráslásmező modult, majd válassza a **Modul hozzáadása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b2cb5-148">In the **Cart icon** slot of the header module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="b2cb5-149">A **Modul hozzáadása** párbeszédpanelen válassza ki az **Kosárikon** modult, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="b2cb5-149">In the **Add Module** dialog box, select the **Cart icon** module, and then select **OK**.</span></span>
1. <span data-ttu-id="b2cb5-150">A kosárikon modul tulajdonságlapján konfigurálja a tulajdonságokat igény szerint.</span><span class="sxs-lookup"><span data-stu-id="b2cb5-150">In the property pane for the cart icon module, configure the properties as needed.</span></span> <span data-ttu-id="b2cb5-151">Ha azt szeretné, hogy a kosárikon megjelenítsen egy kosárösszegzést (más néven mini kosarat), amikor a felhasználó fölé viszi az egérmutatót, akkor válassza ki a **Mini kosár megjelenítése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b2cb5-151">If you want the cart icon to display a cart summary (also known as a mini cart) when users hover over it, select **Show mini cart**.</span></span>
1. <span data-ttu-id="b2cb5-152">Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot a töredék ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.</span><span class="sxs-lookup"><span data-stu-id="b2cb5-152">Select **Save**, select **Finish editing** to check in the fragment, and then select **Publish** to publish it.</span></span>

<span data-ttu-id="b2cb5-153">Ha azt szeretné, hogy minden lapon megjelenjen a fejléc, hajtsa végre az alábbi lépéseket a webhelyhez létrehozott összes oldalsablon esetében.</span><span class="sxs-lookup"><span data-stu-id="b2cb5-153">To help ensure that a header appears on every page, follow these steps on every page template that is created for the site.</span></span>

1. <span data-ttu-id="b2cb5-154">Az **Alapértelmezett** lap **Címsor** helyén a láblécmodulban adja meg a létrehozott lábléctöredéket.</span><span class="sxs-lookup"><span data-stu-id="b2cb5-154">In the **Header** slot of the **Default page** module, add the footer fragment that you created.</span></span>
1. <span data-ttu-id="b2cb5-155">Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot a sablon ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.</span><span class="sxs-lookup"><span data-stu-id="b2cb5-155">Select **Save**, select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b2cb5-156">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="b2cb5-156">Additional resources</span></span>

[<span data-ttu-id="b2cb5-157">Kezdőcsomag áttekintése</span><span class="sxs-lookup"><span data-stu-id="b2cb5-157">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="b2cb5-158">Tárolómodul</span><span class="sxs-lookup"><span data-stu-id="b2cb5-158">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="b2cb5-159">Kosárikon modul</span><span class="sxs-lookup"><span data-stu-id="b2cb5-159">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="b2cb5-160">Promóciós szalagcím modul</span><span class="sxs-lookup"><span data-stu-id="b2cb5-160">Promo banner module</span></span>](add-alert.md)

[<span data-ttu-id="b2cb5-161">Navigációs menü modulja</span><span class="sxs-lookup"><span data-stu-id="b2cb5-161">Navigation Menu module</span></span>](nav-menu-module.md) 

[<span data-ttu-id="b2cb5-162">Cookie-kkal kapcsolatos hozzájárulás</span><span class="sxs-lookup"><span data-stu-id="b2cb5-162">Cookie consent</span></span>](cookie-consent-module.md)

[<span data-ttu-id="b2cb5-163">Láblécmodul</span><span class="sxs-lookup"><span data-stu-id="b2cb5-163">Footer module</span></span>](author-footer-module.md)
