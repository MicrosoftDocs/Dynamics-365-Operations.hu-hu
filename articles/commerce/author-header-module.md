---
title: Fejlécmodul
description: Ez a témakör a fejlécmodulokkal foglalkozik, és bemutatja, hogy hogyan lehet oldalfejléceket létrehozni a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar
manager: annbe
ms.date: 01/23/2020
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
ms.openlocfilehash: efadd19681bbb21ea5b2b469e55bc6f4b0535046
ms.sourcegitcommit: 34e543e807ac8790597f522fe3b4f0266cf4ee56
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/24/2020
ms.locfileid: "3025661"
---
# <a name="header-module"></a><span data-ttu-id="85642-103">Fejlécmodul</span><span class="sxs-lookup"><span data-stu-id="85642-103">Header module</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="85642-104">Ez a témakör a fejlécmodulokkal foglalkozik, és bemutatja, hogy hogyan lehet oldalfejléceket létrehozni a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="85642-104">This topic covers header modules and describes how to create page headers in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="85642-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="85642-105">Overview</span></span>

<span data-ttu-id="85642-106">A Dynamics 365 Commerce szolgáltatásban egy oldalfejléc több modulból áll, például a fejlécből, a navigációs menüből, a keresésből, a promóciós szalagcímből és a cookie-hozzájárulás moduljaiból.</span><span class="sxs-lookup"><span data-stu-id="85642-106">In Dynamics 365 Commerce, a page header comprises multiple modules, such as the header, navigation menu, search, promo banner, and cookie consent modules.</span></span> 

<span data-ttu-id="85642-107">A fejlécmodul tartalmaz egy webhelyemblémát, a navigációs hierarchiára mutató hivatkozásokat, a webhely egyéb oldalaira mutató hivatkozásokat, egy kosár-szimbólumot, egy kívánságlista szimbólumot, bejelentkezési beállításokat és a keresési sávot.</span><span class="sxs-lookup"><span data-stu-id="85642-107">The header module includes a site logo, links to the navigation hierarchy, links to other pages on the site, a cart symbol, a wishlist symbol, sign-in options, and the search bar.</span></span> <span data-ttu-id="85642-108">A program automatikusan optimalizálja a fejlécmodult arra az eszközre, amelyről a webhelyet megtekintik (azaz egy asztali eszközre vagy egy mobileszközre).</span><span class="sxs-lookup"><span data-stu-id="85642-108">A header module is automatically optimized for the device that the site is being viewed on (in other words, for a desktop device or a mobile device).</span></span> <span data-ttu-id="85642-109">Egy mobileszköz esetében például a navigációs sáv össze van csukva egy **Menü** gombba (amelyet néha *hamburger menünek* neveznek).</span><span class="sxs-lookup"><span data-stu-id="85642-109">For example, on a mobile device, the navigation bar is collapsed into a **Menu** button (which is sometimes referred to as a *hamburger menu*).</span></span>

## <a name="properties-of-a-header-module"></a><span data-ttu-id="85642-110">Fejlécmodul tulajdonságai</span><span class="sxs-lookup"><span data-stu-id="85642-110">Properties of a header module</span></span>

<span data-ttu-id="85642-111">A fejlécmodul az **Emblémakép**, **Embléma hivatkozása** és **Saját fiókhivatkozások** tulajdonságokat támogatja.</span><span class="sxs-lookup"><span data-stu-id="85642-111">A header module supports **Logo image**, **Logo link**, and **My account links** properties.</span></span> 

<span data-ttu-id="85642-112">Az **Emblémakép** és az **Emblémahivatkozás** tulajdonságokkal adható meg az embléma az oldalon.</span><span class="sxs-lookup"><span data-stu-id="85642-112">The **Logo image** and **Logo link** properties are used to define a logo on the page.</span></span> <span data-ttu-id="85642-113">További tudnivalók: [Embléma hozzáadása](add-logo.md).</span><span class="sxs-lookup"><span data-stu-id="85642-113">For more information, see [Add a logo](add-logo.md).</span></span> 

<span data-ttu-id="85642-114">A **Saját fiókhivatkozások** tulajdonsággal megadhatók olyan fiókoldalak, amelyekre mutató hivatkozásokat a webhelytulajdonos meg akar jeleníteni a fejlécben.</span><span class="sxs-lookup"><span data-stu-id="85642-114">The **My account links** property can be used to define account pages that the site owner wants to show quick links for in the header.</span></span>

## <a name="modules-that-are-available-in-a-header-module"></a><span data-ttu-id="85642-115">A fejlécmodulban elérhető modulok</span><span class="sxs-lookup"><span data-stu-id="85642-115">Modules that are available in a header module</span></span>

<span data-ttu-id="85642-116">A következő modulban használható a fejlécmodulban:</span><span class="sxs-lookup"><span data-stu-id="85642-116">The following modules can be used in a header module:</span></span>

- <span data-ttu-id="85642-117">**Navigációs menü** – A navigációs menü a csatorna navigációs hierarchiáját és más statikus navigációs hivatkozásokat jelenít meg.</span><span class="sxs-lookup"><span data-stu-id="85642-117">**Navigation menu** – The navigation menu represents the channel navigation hierarchy and other static navigation links.</span></span> <span data-ttu-id="85642-118">A csatorna navigációs hierarchiája a Dynamics 365 Commerce alkalmazásban állítható be.</span><span class="sxs-lookup"><span data-stu-id="85642-118">The channel navigation hierarchy can be configured in Dynamics 365 Commerce.</span></span> <span data-ttu-id="85642-119">A navigációs menü egy **navigációs forrás** tulajdonsággal rendelkezik, amellyel megadhatók a Retail Server navigációs menüelemei és a statikus menüelemek forrásként.</span><span class="sxs-lookup"><span data-stu-id="85642-119">The navigation menu has a **Navigation Source** property that is used to specify Retail Server navigation menu items and static menu items as a source.</span></span> <span data-ttu-id="85642-120">Ha a statikus menüelemek forrásként vannak megadva, akkor a webhely más lapjaihoz kapcsolódó relatív hivatkozásokat is meg lehet adni.</span><span class="sxs-lookup"><span data-stu-id="85642-120">If static menu items are specified as a source, relative links to other pages on the site can be provided.</span></span> <span data-ttu-id="85642-121">A konfigurált elemek ezután fejlécnavigációként jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="85642-121">Configured items then appear as header navigation.</span></span> 
- <span data-ttu-id="85642-122">**Keresősáv** – A keresőmodul lehetővé teszi a felhasználók számára, hogy keresési kifejezéseket írjanak be, amelyekkel termékeket kereshetnek.</span><span class="sxs-lookup"><span data-stu-id="85642-122">**Search** – The search module lets users enter search terms to search for products.</span></span> <span data-ttu-id="85642-123">Az alapértelmezett keresési lap URL-jét és a keresési lekérdezések paramétereit a **Webhelybeállítások \> Bővítmények** részben kell megadni.</span><span class="sxs-lookup"><span data-stu-id="85642-123">The URL of the default search page and the search query parameters must be provided at **Site Settings \> Extensions**.</span></span> <span data-ttu-id="85642-124">A keresési modulnak van olyan tulajdonsága, amely lehetővé teszi a keresési gomb vagy címke elrejtését szükség esetén.</span><span class="sxs-lookup"><span data-stu-id="85642-124">The search module has properties that let you suppress the search button or label as you require.</span></span> <span data-ttu-id="85642-125">A keresési modul olyan automatikus javaslati beállításokat is támogat, mint a termék, a kulcsszó és a kategória keresési eredményei.</span><span class="sxs-lookup"><span data-stu-id="85642-125">The search module also supports auto-suggest options, such as product, keyword, and category search results.</span></span>

## <a name="create-a-header-module-for-a-page"></a><span data-ttu-id="85642-126">Fejlécmodul létrehozása egy oldalhoz</span><span class="sxs-lookup"><span data-stu-id="85642-126">Create a header module for a page</span></span>

<span data-ttu-id="85642-127">Fejlécmodul létrehozásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="85642-127">To create a header module, follow these steps.</span></span>

1. <span data-ttu-id="85642-128">Hozzon létre egy **Fejléctöredék** nevű töredéket, majd adjon hozzá egy tárolómodult.</span><span class="sxs-lookup"><span data-stu-id="85642-128">Create a fragment that is named **Header fragment**, and add a container module to it.</span></span>
1. <span data-ttu-id="85642-129">A tárolómodul tulajdonságlapján a **Szélesség** tulajdonságot állítsa **Tároló kitöltése** értékre.</span><span class="sxs-lookup"><span data-stu-id="85642-129">In the property pane for the container module, set the **Width** property to **Fill container**.</span></span>
1. <span data-ttu-id="85642-130">Adjon a tárolómodulhoz promóciós szalagcímet tartalmazó és cookie-kkal kapcsolatos hozzájárulásra vonatkozó modulokat.</span><span class="sxs-lookup"><span data-stu-id="85642-130">Add promo banner and cookie consent modules to the container module.</span></span>
1. <span data-ttu-id="85642-131">Adjon másik tárolómodult a töredékhez, és a **Szélesség** tulajdonságot állítsa **Tároló kitöltése** értékre.</span><span class="sxs-lookup"><span data-stu-id="85642-131">Add another container module to the fragment, and set the **Width** property to **Fill container**.</span></span>
1. <span data-ttu-id="85642-132">Vegyen fel egy fejlécmodult a második tárolómodulba.</span><span class="sxs-lookup"><span data-stu-id="85642-132">Add a header module to the second container module.</span></span>
1. <span data-ttu-id="85642-133">A fejlécmodul **Navigációs menü** helyére adja hozzá a navigációsmenü-modult.</span><span class="sxs-lookup"><span data-stu-id="85642-133">In the **Navigation menu** slot of the header module, add a navigation menu module.</span></span> 
1. <span data-ttu-id="85642-134">A navigációs menü modul tulajdonságlapján konfigurálja a navigációs menü modul tulajdonságait.</span><span class="sxs-lookup"><span data-stu-id="85642-134">In the property pane for the navigation menu module, configure the properties of the navigation menu module.</span></span>
1. <span data-ttu-id="85642-135">A fejlécmodul **Keresés** helyén adjon hozzá egy keresési modult.</span><span class="sxs-lookup"><span data-stu-id="85642-135">In the **Search** slot of the header module, add a search module.</span></span> 
1. <span data-ttu-id="85642-136">A keresési modul tulajdonságlapján konfigurálja a keresési modul tulajdonságait.</span><span class="sxs-lookup"><span data-stu-id="85642-136">In the property pane for the search module, configure the properties of the search module.</span></span> 
1. <span data-ttu-id="85642-137">Mentse az oldaltöredéket, fejezze be a szerkesztését, majd tegye közzé.</span><span class="sxs-lookup"><span data-stu-id="85642-137">Save the page fragment, finish editing it, and publish it.</span></span> 

<span data-ttu-id="85642-138">Ha azt szeretné, hogy minden lapon megjelenjen a fejléc, hajtsa végre az alábbi lépéseket a webhelyhez létrehozott összes oldalsablon esetében.</span><span class="sxs-lookup"><span data-stu-id="85642-138">To help guarantee that a header appears on every page, follow these steps on every page template that is created for the site.</span></span>

1. <span data-ttu-id="85642-139">Az alapértelmezett lap **Fő** helyén adja hozzá a fejlécmodul-töredéket, amely tartalmazza a fejléc fejlécmodulját.</span><span class="sxs-lookup"><span data-stu-id="85642-139">In the **Main** slot of the default page, add the header page fragment that contains the header module to the header.</span></span>
1. <span data-ttu-id="85642-140">Mentse a sablont, fejezze be a szerkesztését, majd tegye közzé.</span><span class="sxs-lookup"><span data-stu-id="85642-140">Save the template, finish editing it, and publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="85642-141">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="85642-141">Additional resources</span></span>

[<span data-ttu-id="85642-142">Kezdő csomag áttekintése</span><span class="sxs-lookup"><span data-stu-id="85642-142">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="85642-143">Tárolómodul</span><span class="sxs-lookup"><span data-stu-id="85642-143">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="85642-144">Vásárlásmező-modul</span><span class="sxs-lookup"><span data-stu-id="85642-144">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="85642-145">Kosármodul</span><span class="sxs-lookup"><span data-stu-id="85642-145">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="85642-146">Fizetésmodul</span><span class="sxs-lookup"><span data-stu-id="85642-146">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="85642-147">Rendelésmegerősítési modul</span><span class="sxs-lookup"><span data-stu-id="85642-147">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="85642-148">Fejlécmodul</span><span class="sxs-lookup"><span data-stu-id="85642-148">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="85642-149">Láblécmodul</span><span class="sxs-lookup"><span data-stu-id="85642-149">Footer module</span></span>](author-footer-module.md)
