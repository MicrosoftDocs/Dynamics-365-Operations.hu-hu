---
title: Fejlécmodul
description: Ez a témakör a fejlécmodulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket létrehozni a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar
manager: annbe
ms.date: 10/31/2019
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
ms.openlocfilehash: d393701dacb88ab03a4b56724d93c794da6bb5c8
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697275"
---
# <a name="header-module"></a><span data-ttu-id="c1b5c-103">Fejlécmodul</span><span class="sxs-lookup"><span data-stu-id="c1b5c-103">Header module</span></span>

<span data-ttu-id="c1b5c-104">[!include [banner](includes/preview-banner.md)] [!include [banner](includes/banner.md)]</span><span class="sxs-lookup"><span data-stu-id="c1b5c-104">[!include [banner]includes/preview-banner.md)] [!include [banner](includes/banner.md)]</span></span>

<span data-ttu-id="c1b5c-105">Ez a témakör a fejlécmodulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket létrehozni a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="c1b5c-105">This topic covers header modules and describes how to create them in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="c1b5c-106">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="c1b5c-106">Overview</span></span>

<span data-ttu-id="c1b5c-107">A fejlécmodul egy speciális tároló, amely a lapok fejlécében megjelenített modulok tárolására szolgál.</span><span class="sxs-lookup"><span data-stu-id="c1b5c-107">A header module is a special container that is used to host all the modules that will be shown in a page's header.</span></span> <span data-ttu-id="c1b5c-108">Ez lehet például a webhely emblémája, a navigációs hierarchiára mutató hivatkozások, a webhely egyéb lapjaira mutató hivatkozások és a keresősáv.</span><span class="sxs-lookup"><span data-stu-id="c1b5c-108">For example, it can include your site logo, links to the navigation hierarchy, links to other pages on the site, and the search bar.</span></span>

<span data-ttu-id="c1b5c-109">A program automatikusan optimalizálja a fejlécmodult arra az eszközre, amelyről a webhelyet megtekintik (azaz egy asztali eszközre vagy egy mobileszközre).</span><span class="sxs-lookup"><span data-stu-id="c1b5c-109">A header module is automatically optimized for the device that the site is being viewed on (that is, a desktop device or a mobile device).</span></span> <span data-ttu-id="c1b5c-110">Egy mobileszköz esetében például a navigációs sáv össze van csukva egy **Menü** gombba (amelyet néha *hamburger menünek* neveznek).</span><span class="sxs-lookup"><span data-stu-id="c1b5c-110">For example, on a mobile device, the navigation bar is collapsed into a **Menu** button (which is sometimes referred to as a *hamburger menu*).</span></span>

## <a name="properties-of-a-header"></a><span data-ttu-id="c1b5c-111">Fejléc tulajdonságai</span><span class="sxs-lookup"><span data-stu-id="c1b5c-111">Properties of a header</span></span>

<span data-ttu-id="c1b5c-112">Az általános tárolókhoz hasonlóan a fejlécmodul is támogatja a **fejléc** és **szélesség** tulajdonságokat.</span><span class="sxs-lookup"><span data-stu-id="c1b5c-112">Like generic containers, a header module supports the **heading** and **width** properties.</span></span>

<span data-ttu-id="c1b5c-113">A fejléc modul több helyet tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="c1b5c-113">A header module has multiple slots.</span></span> <span data-ttu-id="c1b5c-114">Például vannak helyek a tájékoztató üzenetek, a navigációs menü, az embléma, a keresősáv, a kosár ikon, a kívánságlista ikon és a fiókinformációk számára.</span><span class="sxs-lookup"><span data-stu-id="c1b5c-114">For example, there are slots for an informational message, navigation menu, logo, search bar, cart icon, wish list icon, and account information.</span></span> <span data-ttu-id="c1b5c-115">Minden hely a modulok meghatározott csoportját támogatja.</span><span class="sxs-lookup"><span data-stu-id="c1b5c-115">Each slot supports a specific set of modules.</span></span>

## <a name="modules-that-are-available-in-a-header-module"></a><span data-ttu-id="c1b5c-116">A fejlécmodulban elérhető modulok</span><span class="sxs-lookup"><span data-stu-id="c1b5c-116">Modules that are available in a header module</span></span>

<span data-ttu-id="c1b5c-117">A következő modulban használható a fejlécmodulban:</span><span class="sxs-lookup"><span data-stu-id="c1b5c-117">The following modules can be used in a header module:</span></span>

- <span data-ttu-id="c1b5c-118">**Navigációs menü** – A navigációs menü a csatorna navigációs hierarchiáját és más statikus navigációs hivatkozásokat jelenít meg.</span><span class="sxs-lookup"><span data-stu-id="c1b5c-118">**Navigation menu** – The navigation menu represents the channel navigation hierarchy and other static navigation links.</span></span> <span data-ttu-id="c1b5c-119">A csatorna navigációs hierarchiája a Dynamics 365 Retail alkalmazásban állítható be.</span><span class="sxs-lookup"><span data-stu-id="c1b5c-119">The channel navigation hierarchy can be configured in Dynamics 365 Retail.</span></span> <span data-ttu-id="c1b5c-120">A konfigurált elemek ezután fejlécnavigációként jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="c1b5c-120">Configured items then appear as header navigation.</span></span> <span data-ttu-id="c1b5c-121">Ezenkívül statikus navigációs hivatkozások is konfigurálhatók, és az e-kereskedelmi webhely egyéb lapjaira mutató relatív hivatkozásokat is meg lehet adni.</span><span class="sxs-lookup"><span data-stu-id="c1b5c-121">In addition, static navigation links can be configured, and relative links to other pages on the e-Commerce site can be provided.</span></span> <span data-ttu-id="c1b5c-122">Maga a fejléc balra, jobbra vagy középre igazítható.</span><span class="sxs-lookup"><span data-stu-id="c1b5c-122">The header itself can be aligned left, right, or center.</span></span>
- <span data-ttu-id="c1b5c-123">**Kosár ikon** – A kosár ikon a kosarat ábrázoló speciális ikon.</span><span class="sxs-lookup"><span data-stu-id="c1b5c-123">**Cart icon** – The cart icon is a special icon that represents the cart.</span></span> <span data-ttu-id="c1b5c-124">Ez a fejlécben látható, és a cikkek számát jelzi a kosárban.</span><span class="sxs-lookup"><span data-stu-id="c1b5c-124">It's shown in the header and indicates the number of items in the cart.</span></span> <span data-ttu-id="c1b5c-125">A kosárlapra mutató hivatkozást a kosárikonhoz kell társítani, hogy a vevők a kosárlapra legyenek irányítva, amikor a ikonra kattintanak.</span><span class="sxs-lookup"><span data-stu-id="c1b5c-125">A link to the cart page should accompany the cart icon, so that customers can be redirected to the cart page when they interact with the icon.</span></span>
- <span data-ttu-id="c1b5c-126">**Kívánságlista ikon** – A kívánságlista ikon a fejlécben látható, és azt jelzi, hogy hány cikket adtak hozzá a vevő kívánságlistájához.</span><span class="sxs-lookup"><span data-stu-id="c1b5c-126">**Wish list icon** – The wish list icon is shown in the header and indicates the number of items that have been added to the customer's wish list.</span></span> <span data-ttu-id="c1b5c-127">A kívánságlista lapra mutató hivatkozást ehhez az ikonhoz kell társítani, hogy a vevők a kívánságlista lapra legyenek irányítva, amikor a ikonra kattintanak.</span><span class="sxs-lookup"><span data-stu-id="c1b5c-127">A link to the wish list page should accompany this icon, so that customers can be redirected to the wish list page when they interact with the icon.</span></span>
- <span data-ttu-id="c1b5c-128">**Bejelentkezési modul** – A bejelentkezési modul a fejlécben jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="c1b5c-128">**Sign-in module** – The sign-in module is shown in the header.</span></span> <span data-ttu-id="c1b5c-129">A vevők vagy a saját fiókjukba jelentkeznek be, vagy regisztrálnak egy fiókot.</span><span class="sxs-lookup"><span data-stu-id="c1b5c-129">It lets customers either sign in to their account or sign up for an account.</span></span> <span data-ttu-id="c1b5c-130">Ha a vevő már be van jelentkezve, a modul beállítható úgy, hogy a fióklapra, a rendelési előzmények lapra vagy egy egyéb lapra mutató hivatkozást jelenítsen meg.</span><span class="sxs-lookup"><span data-stu-id="c1b5c-130">If the customer is already signed in, the module can be configured to show links to the account page, order history page, or another page.</span></span>
- <span data-ttu-id="c1b5c-131">**Logó modul** – Ez a modul a kiskereskedőt és a márkát képviselő logót jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="c1b5c-131">**Logo module** – This module shows the logo that represents the retailer and brand.</span></span> <span data-ttu-id="c1b5c-132">Ez egy kép egy hivatkozással.</span><span class="sxs-lookup"><span data-stu-id="c1b5c-132">It's an image that has a link.</span></span> <span data-ttu-id="c1b5c-133">A hivatkozás általában úgy van beállítva, hogy a kezdőlapra irányítson át, így a vevők gyorsan visszatérhetnek a kezdőlapra a webhely bármely lapjáról.</span><span class="sxs-lookup"><span data-stu-id="c1b5c-133">The link is typically configured so that it has a redirect to the home page, Therefore, customers can quickly return to the home page from any page on the site.</span></span>
- <span data-ttu-id="c1b5c-134">**Figyelmeztetés** – A figyelmeztetés a fejlécben jelenik meg, és egy olyan belső üzenetet jelenít meg, amely a webhely minden lapjára vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="c1b5c-134">**Alert** – An alert appears in the header and is used to show an inline message that applies to all pages on the site.</span></span> <span data-ttu-id="c1b5c-135">Egy figyelmeztető üzenet például megjelenítheti a következő üzenetet: „Az éves akció 2 napon belül lejár”.</span><span class="sxs-lookup"><span data-stu-id="c1b5c-135">For example, an alert might show a message such as "Annual sale ends in 2 days."</span></span>
- <span data-ttu-id="c1b5c-136">**Keresősáv** – A keresősáv lehetővé teszi a felhasználók számára, hogy keresési kifejezéseket írjanak be, amelyekkel termékeket kereshetnek.</span><span class="sxs-lookup"><span data-stu-id="c1b5c-136">**Search bar** – The search bar lets users enter search terms so that they can search for products.</span></span> <span data-ttu-id="c1b5c-137">A modult a keresési eredmények lap URL-címével kell konfigurálni.</span><span class="sxs-lookup"><span data-stu-id="c1b5c-137">The module must be configured with the URL of the search results page.</span></span> <span data-ttu-id="c1b5c-138">A lekérdezési karakterlánc paraméter konfigurálható (az alapértelmezett érték **„q”**).</span><span class="sxs-lookup"><span data-stu-id="c1b5c-138">The query string parameter can be configured (the default value is **"q"**).</span></span> <span data-ttu-id="c1b5c-139">A keresősáv egy olyan automatikus javaslati helyet tartalmaz, ahol egy automatikus javaslati modul adható hozzá.</span><span class="sxs-lookup"><span data-stu-id="c1b5c-139">The search bar has an autosuggest slot where the autosuggest module should be added.</span></span>
- <span data-ttu-id="c1b5c-140">**Automatikus javaslat** – Az automatikus javaslati modul automatikusan javasolt találatokat jelenít meg.</span><span class="sxs-lookup"><span data-stu-id="c1b5c-140">**Autosuggest** – The autosuggest module shows automatically suggested results.</span></span> <span data-ttu-id="c1b5c-141">Ezek a találatok olyan kulcsszavak, termékek vagy kategóriák lehetnek, amelyekben a keresési kifejezés megtalálható.</span><span class="sxs-lookup"><span data-stu-id="c1b5c-141">These results can be keywords, products, or categories where the search term is found.</span></span>

## <a name="create-a-header-module"></a><span data-ttu-id="c1b5c-142">Fejlécmodul létrehozása</span><span class="sxs-lookup"><span data-stu-id="c1b5c-142">Create a header module</span></span>

<span data-ttu-id="c1b5c-143">Fejlécmodul létrehozásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="c1b5c-143">To create a header module, follow these steps.</span></span>

1. <span data-ttu-id="c1b5c-144">Hozzon létre egy fejlécmodult tartalmazó laptöredékét.</span><span class="sxs-lookup"><span data-stu-id="c1b5c-144">Create a page fragment that includes a header module.</span></span>
1. <span data-ttu-id="c1b5c-145">Adjon hozzá modulokat a fejlécmodul helyeihez.</span><span class="sxs-lookup"><span data-stu-id="c1b5c-145">Add modules to the slots in the header module.</span></span>
1. <span data-ttu-id="c1b5c-146">Frissítse az egyes modulok beállításait.</span><span class="sxs-lookup"><span data-stu-id="c1b5c-146">Update the settings for each module.</span></span>
1. <span data-ttu-id="c1b5c-147">Mentse a laptöredéket.</span><span class="sxs-lookup"><span data-stu-id="c1b5c-147">Save the page fragment.</span></span> 
1. <span data-ttu-id="c1b5c-148">Adja be a lapot, és tegye közzé.</span><span class="sxs-lookup"><span data-stu-id="c1b5c-148">Check in the page, and publish it.</span></span>

<span data-ttu-id="c1b5c-149">Ha azt szeretné, hogy minden lapon megjelenjen a fejléc, hajtsa végre az alábbi lépéseket a webhelyhez létrehozott összes oldalsablon esetében.</span><span class="sxs-lookup"><span data-stu-id="c1b5c-149">To help guarantee that a header appears on every page, follow these steps on every page template that is created for the site.</span></span>

1. <span data-ttu-id="c1b5c-150">Az alapértelmezett lapon adja hozzá a fejlécmodult tartalmazó laptöredéket a fő hely fejlécéhez.</span><span class="sxs-lookup"><span data-stu-id="c1b5c-150">On the default page, add the page fragment containing the header module to the header in the main slot.</span></span>
1. <span data-ttu-id="c1b5c-151">Mentse a sablont.</span><span class="sxs-lookup"><span data-stu-id="c1b5c-151">Save the template.</span></span> 
1. <span data-ttu-id="c1b5c-152">Adja be a sablont és tegye közzé.</span><span class="sxs-lookup"><span data-stu-id="c1b5c-152">Check in the template, and publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c1b5c-153">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="c1b5c-153">Additional resources</span></span>

[<span data-ttu-id="c1b5c-154">Kezdő csomag áttekintése</span><span class="sxs-lookup"><span data-stu-id="c1b5c-154">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="c1b5c-155">Tárolómodul</span><span class="sxs-lookup"><span data-stu-id="c1b5c-155">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="c1b5c-156">Vásárlásmező-modul</span><span class="sxs-lookup"><span data-stu-id="c1b5c-156">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="c1b5c-157">Kosármodul</span><span class="sxs-lookup"><span data-stu-id="c1b5c-157">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="c1b5c-158">Fizetésmodul</span><span class="sxs-lookup"><span data-stu-id="c1b5c-158">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="c1b5c-159">Rendelésmegerősítési modul</span><span class="sxs-lookup"><span data-stu-id="c1b5c-159">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="c1b5c-160">Fejlécmodul</span><span class="sxs-lookup"><span data-stu-id="c1b5c-160">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="c1b5c-161">Láblécmodul</span><span class="sxs-lookup"><span data-stu-id="c1b5c-161">Footer module</span></span>](author-footer-module.md)
