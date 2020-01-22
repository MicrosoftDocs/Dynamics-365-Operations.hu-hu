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
ms.openlocfilehash: cc98419077f6f563ea2265d4e68ba809971cfbd6
ms.sourcegitcommit: ff93b8f6a11993f2cd00be2da7aa77ef0d950ab8
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/03/2019
ms.locfileid: "2885478"
---
# <a name="header-module"></a><span data-ttu-id="a0e4e-103">Fejlécmodul</span><span class="sxs-lookup"><span data-stu-id="a0e4e-103">Header module</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="a0e4e-104">Ez a témakör a fejlécmodulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket létrehozni a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="a0e4e-104">This topic covers header modules and describes how to create them in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="a0e4e-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="a0e4e-105">Overview</span></span>

<span data-ttu-id="a0e4e-106">A fejlécmodul egy speciális tároló, amely a lapok fejlécében megjelenített modulok tárolására szolgál.</span><span class="sxs-lookup"><span data-stu-id="a0e4e-106">A header module is a special container that is used to host all the modules that will be shown in a page's header.</span></span> <span data-ttu-id="a0e4e-107">Ez lehet például a webhely emblémája, a navigációs hierarchiára mutató hivatkozások, a webhely egyéb lapjaira mutató hivatkozások és a keresősáv.</span><span class="sxs-lookup"><span data-stu-id="a0e4e-107">For example, it can include your site logo, links to the navigation hierarchy, links to other pages on the site, and the search bar.</span></span>

<span data-ttu-id="a0e4e-108">A program automatikusan optimalizálja a fejlécmodult arra az eszközre, amelyről a webhelyet megtekintik (azaz egy asztali eszközre vagy egy mobileszközre).</span><span class="sxs-lookup"><span data-stu-id="a0e4e-108">A header module is automatically optimized for the device that the site is being viewed on (that is, a desktop device or a mobile device).</span></span> <span data-ttu-id="a0e4e-109">Egy mobileszköz esetében például a navigációs sáv össze van csukva egy **Menü** gombba (amelyet néha *hamburger menünek* neveznek).</span><span class="sxs-lookup"><span data-stu-id="a0e4e-109">For example, on a mobile device, the navigation bar is collapsed into a **Menu** button (which is sometimes referred to as a *hamburger menu*).</span></span>

## <a name="properties-of-a-header"></a><span data-ttu-id="a0e4e-110">Fejléc tulajdonságai</span><span class="sxs-lookup"><span data-stu-id="a0e4e-110">Properties of a header</span></span>

<span data-ttu-id="a0e4e-111">Az általános tárolókhoz hasonlóan a fejlécmodul is támogatja a **fejléc** és **szélesség** tulajdonságokat.</span><span class="sxs-lookup"><span data-stu-id="a0e4e-111">Like generic containers, a header module supports the **heading** and **width** properties.</span></span>

<span data-ttu-id="a0e4e-112">A fejléc modul több helyet tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="a0e4e-112">A header module has multiple slots.</span></span> <span data-ttu-id="a0e4e-113">Például vannak helyek a tájékoztató üzenetek, a navigációs menü, az embléma, a keresősáv, a kosár ikon, a kívánságlista ikon és a fiókinformációk számára.</span><span class="sxs-lookup"><span data-stu-id="a0e4e-113">For example, there are slots for an informational message, navigation menu, logo, search bar, cart icon, wish list icon, and account information.</span></span> <span data-ttu-id="a0e4e-114">Minden hely a modulok meghatározott csoportját támogatja.</span><span class="sxs-lookup"><span data-stu-id="a0e4e-114">Each slot supports a specific set of modules.</span></span>

## <a name="modules-that-are-available-in-a-header-module"></a><span data-ttu-id="a0e4e-115">A fejlécmodulban elérhető modulok</span><span class="sxs-lookup"><span data-stu-id="a0e4e-115">Modules that are available in a header module</span></span>

<span data-ttu-id="a0e4e-116">A következő modulban használható a fejlécmodulban:</span><span class="sxs-lookup"><span data-stu-id="a0e4e-116">The following modules can be used in a header module:</span></span>

- <span data-ttu-id="a0e4e-117">**Navigációs menü** – A navigációs menü a csatorna navigációs hierarchiáját és más statikus navigációs hivatkozásokat jelenít meg.</span><span class="sxs-lookup"><span data-stu-id="a0e4e-117">**Navigation menu** – The navigation menu represents the channel navigation hierarchy and other static navigation links.</span></span> <span data-ttu-id="a0e4e-118">A csatorna navigációs hierarchiája a Dynamics 365 Retail alkalmazásban állítható be.</span><span class="sxs-lookup"><span data-stu-id="a0e4e-118">The channel navigation hierarchy can be configured in Dynamics 365 Retail.</span></span> <span data-ttu-id="a0e4e-119">A konfigurált elemek ezután fejlécnavigációként jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="a0e4e-119">Configured items then appear as header navigation.</span></span> <span data-ttu-id="a0e4e-120">Ezenkívül statikus navigációs hivatkozások is konfigurálhatók, és az e-kereskedelmi webhely egyéb lapjaira mutató relatív hivatkozásokat is meg lehet adni.</span><span class="sxs-lookup"><span data-stu-id="a0e4e-120">In addition, static navigation links can be configured, and relative links to other pages on the e-Commerce site can be provided.</span></span> <span data-ttu-id="a0e4e-121">Maga a fejléc balra, jobbra vagy középre igazítható.</span><span class="sxs-lookup"><span data-stu-id="a0e4e-121">The header itself can be aligned left, right, or center.</span></span>
- <span data-ttu-id="a0e4e-122">**Kosár ikon** – A kosár ikon a kosarat ábrázoló speciális ikon.</span><span class="sxs-lookup"><span data-stu-id="a0e4e-122">**Cart icon** – The cart icon is a special icon that represents the cart.</span></span> <span data-ttu-id="a0e4e-123">Ez a fejlécben látható, és a cikkek számát jelzi a kosárban.</span><span class="sxs-lookup"><span data-stu-id="a0e4e-123">It's shown in the header and indicates the number of items in the cart.</span></span> <span data-ttu-id="a0e4e-124">A kosárlapra mutató hivatkozást a kosárikonhoz kell társítani, hogy a vevők a kosárlapra legyenek irányítva, amikor a ikonra kattintanak.</span><span class="sxs-lookup"><span data-stu-id="a0e4e-124">A link to the cart page should accompany the cart icon, so that customers can be redirected to the cart page when they interact with the icon.</span></span>
- <span data-ttu-id="a0e4e-125">**Kívánságlista ikon** – A kívánságlista ikon a fejlécben látható, és azt jelzi, hogy hány cikket adtak hozzá a vevő kívánságlistájához.</span><span class="sxs-lookup"><span data-stu-id="a0e4e-125">**Wish list icon** – The wish list icon is shown in the header and indicates the number of items that have been added to the customer's wish list.</span></span> <span data-ttu-id="a0e4e-126">A kívánságlista lapra mutató hivatkozást ehhez az ikonhoz kell társítani, hogy a vevők a kívánságlista lapra legyenek irányítva, amikor a ikonra kattintanak.</span><span class="sxs-lookup"><span data-stu-id="a0e4e-126">A link to the wish list page should accompany this icon, so that customers can be redirected to the wish list page when they interact with the icon.</span></span>
- <span data-ttu-id="a0e4e-127">**Bejelentkezési modul** – A bejelentkezési modul a fejlécben jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="a0e4e-127">**Sign-in module** – The sign-in module is shown in the header.</span></span> <span data-ttu-id="a0e4e-128">A vevők vagy a saját fiókjukba jelentkeznek be, vagy regisztrálnak egy fiókot.</span><span class="sxs-lookup"><span data-stu-id="a0e4e-128">It lets customers either sign in to their account or sign up for an account.</span></span> <span data-ttu-id="a0e4e-129">Ha a vevő már be van jelentkezve, a modul beállítható úgy, hogy a fióklapra, a rendelési előzmények lapra vagy egy egyéb lapra mutató hivatkozást jelenítsen meg.</span><span class="sxs-lookup"><span data-stu-id="a0e4e-129">If the customer is already signed in, the module can be configured to show links to the account page, order history page, or another page.</span></span>
- <span data-ttu-id="a0e4e-130">**Logó modul** – Ez a modul a kiskereskedőt és a márkát képviselő logót jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="a0e4e-130">**Logo module** – This module shows the logo that represents the retailer and brand.</span></span> <span data-ttu-id="a0e4e-131">Ez egy kép egy hivatkozással.</span><span class="sxs-lookup"><span data-stu-id="a0e4e-131">It's an image that has a link.</span></span> <span data-ttu-id="a0e4e-132">A hivatkozás általában úgy van beállítva, hogy a kezdőlapra irányítson át, így a vevők gyorsan visszatérhetnek a kezdőlapra a webhely bármely lapjáról.</span><span class="sxs-lookup"><span data-stu-id="a0e4e-132">The link is typically configured so that it has a redirect to the home page, Therefore, customers can quickly return to the home page from any page on the site.</span></span>
- <span data-ttu-id="a0e4e-133">**Figyelmeztetés** – A figyelmeztetés a fejlécben jelenik meg, és egy olyan belső üzenetet jelenít meg, amely a webhely minden lapjára vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="a0e4e-133">**Alert** – An alert appears in the header and is used to show an inline message that applies to all pages on the site.</span></span> <span data-ttu-id="a0e4e-134">Egy figyelmeztető üzenet például megjelenítheti a következő üzenetet: „Az éves akció 2 napon belül lejár”.</span><span class="sxs-lookup"><span data-stu-id="a0e4e-134">For example, an alert might show a message such as "Annual sale ends in 2 days."</span></span>
- <span data-ttu-id="a0e4e-135">**Keresősáv** – A keresősáv lehetővé teszi a felhasználók számára, hogy keresési kifejezéseket írjanak be, amelyekkel termékeket kereshetnek.</span><span class="sxs-lookup"><span data-stu-id="a0e4e-135">**Search bar** – The search bar lets users enter search terms so that they can search for products.</span></span> <span data-ttu-id="a0e4e-136">A modult a keresési eredmények lap URL-címével kell konfigurálni.</span><span class="sxs-lookup"><span data-stu-id="a0e4e-136">The module must be configured with the URL of the search results page.</span></span> <span data-ttu-id="a0e4e-137">A lekérdezési karakterlánc paraméter konfigurálható (az alapértelmezett érték **„q”**).</span><span class="sxs-lookup"><span data-stu-id="a0e4e-137">The query string parameter can be configured (the default value is **"q"**).</span></span> <span data-ttu-id="a0e4e-138">A keresősáv egy olyan automatikus javaslati helyet tartalmaz, ahol egy automatikus javaslati modul adható hozzá.</span><span class="sxs-lookup"><span data-stu-id="a0e4e-138">The search bar has an autosuggest slot where the autosuggest module should be added.</span></span>
- <span data-ttu-id="a0e4e-139">**Automatikus javaslat** – Az automatikus javaslati modul automatikusan javasolt találatokat jelenít meg.</span><span class="sxs-lookup"><span data-stu-id="a0e4e-139">**Autosuggest** – The autosuggest module shows automatically suggested results.</span></span> <span data-ttu-id="a0e4e-140">Ezek a találatok olyan kulcsszavak, termékek vagy kategóriák lehetnek, amelyekben a keresési kifejezés megtalálható.</span><span class="sxs-lookup"><span data-stu-id="a0e4e-140">These results can be keywords, products, or categories where the search term is found.</span></span>

## <a name="create-a-header-module"></a><span data-ttu-id="a0e4e-141">Fejlécmodul létrehozása</span><span class="sxs-lookup"><span data-stu-id="a0e4e-141">Create a header module</span></span>

<span data-ttu-id="a0e4e-142">Fejlécmodul létrehozásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="a0e4e-142">To create a header module, follow these steps.</span></span>

1. <span data-ttu-id="a0e4e-143">Hozzon létre egy fejlécmodult tartalmazó laptöredékét.</span><span class="sxs-lookup"><span data-stu-id="a0e4e-143">Create a page fragment that includes a header module.</span></span>
1. <span data-ttu-id="a0e4e-144">Adjon hozzá modulokat a fejlécmodul helyeihez.</span><span class="sxs-lookup"><span data-stu-id="a0e4e-144">Add modules to the slots in the header module.</span></span>
1. <span data-ttu-id="a0e4e-145">Frissítse az egyes modulok beállításait.</span><span class="sxs-lookup"><span data-stu-id="a0e4e-145">Update the settings for each module.</span></span>
1. <span data-ttu-id="a0e4e-146">Mentse a laptöredéket.</span><span class="sxs-lookup"><span data-stu-id="a0e4e-146">Save the page fragment.</span></span> 
1. <span data-ttu-id="a0e4e-147">Adja be a lapot, és tegye közzé.</span><span class="sxs-lookup"><span data-stu-id="a0e4e-147">Check in the page, and publish it.</span></span>

<span data-ttu-id="a0e4e-148">Ha azt szeretné, hogy minden lapon megjelenjen a fejléc, hajtsa végre az alábbi lépéseket a webhelyhez létrehozott összes oldalsablon esetében.</span><span class="sxs-lookup"><span data-stu-id="a0e4e-148">To help guarantee that a header appears on every page, follow these steps on every page template that is created for the site.</span></span>

1. <span data-ttu-id="a0e4e-149">Az alapértelmezett lapon adja hozzá a fejlécmodult tartalmazó laptöredéket a fő hely fejlécéhez.</span><span class="sxs-lookup"><span data-stu-id="a0e4e-149">On the default page, add the page fragment containing the header module to the header in the main slot.</span></span>
1. <span data-ttu-id="a0e4e-150">Mentse a sablont.</span><span class="sxs-lookup"><span data-stu-id="a0e4e-150">Save the template.</span></span> 
1. <span data-ttu-id="a0e4e-151">Adja be a sablont és tegye közzé.</span><span class="sxs-lookup"><span data-stu-id="a0e4e-151">Check in the template, and publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a0e4e-152">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="a0e4e-152">Additional resources</span></span>

[<span data-ttu-id="a0e4e-153">Kezdő csomag áttekintése</span><span class="sxs-lookup"><span data-stu-id="a0e4e-153">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="a0e4e-154">Tárolómodul</span><span class="sxs-lookup"><span data-stu-id="a0e4e-154">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="a0e4e-155">Vásárlásmező-modul</span><span class="sxs-lookup"><span data-stu-id="a0e4e-155">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="a0e4e-156">Kosármodul</span><span class="sxs-lookup"><span data-stu-id="a0e4e-156">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="a0e4e-157">Fizetésmodul</span><span class="sxs-lookup"><span data-stu-id="a0e4e-157">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="a0e4e-158">Rendelésmegerősítési modul</span><span class="sxs-lookup"><span data-stu-id="a0e4e-158">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="a0e4e-159">Fejlécmodul</span><span class="sxs-lookup"><span data-stu-id="a0e4e-159">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="a0e4e-160">Láblécmodul</span><span class="sxs-lookup"><span data-stu-id="a0e4e-160">Footer module</span></span>](author-footer-module.md)
