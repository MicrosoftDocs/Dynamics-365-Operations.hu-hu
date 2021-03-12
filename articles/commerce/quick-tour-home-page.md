---
title: Kezdőlap áttekintése
description: Ez a témakör a Microsoft Dynamics 365 Commerce kezdőlapjával kapcsolatban nyújt áttekintést.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
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
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: c7f9762b5e00a04f189874a3695c33fe989b579c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4979853"
---
# <a name="home-page-overview"></a><span data-ttu-id="d264e-103">Kezdőlap áttekintése</span><span class="sxs-lookup"><span data-stu-id="d264e-103">Home page overview</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="d264e-104">Ez a témakör a Microsoft Dynamics 365 Commerce kezdőlapjával kapcsolatban nyújt áttekintést.</span><span class="sxs-lookup"><span data-stu-id="d264e-104">This topic provides an overview of the home page in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="d264e-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="d264e-105">Overview</span></span>

<span data-ttu-id="d264e-106">A kezdőlap az az alapértelmezett lap, amelyre a vásárlók kerülnek, amikor meglátogatnak egy e-kereskedelmi webhelyet.</span><span class="sxs-lookup"><span data-stu-id="d264e-106">The home page is the default page that shoppers go to when they visit an e-Commerce site.</span></span> <span data-ttu-id="d264e-107">Ez a lap általában termékeket és promóciókat jelenít meg marketingmodulok kombinációjának használatával.</span><span class="sxs-lookup"><span data-stu-id="d264e-107">Typically, this page showcases products and promotions by using a combination of marketing modules.</span></span> <span data-ttu-id="d264e-108">A kezdőlapnak képekben és szövegben gazdagnak kell lennie ahhoz, hogy a bevonzza a vásárlókat.</span><span class="sxs-lookup"><span data-stu-id="d264e-108">The home page should be rich with images and text to keep shoppers engaged.</span></span>

<span data-ttu-id="d264e-109">A következő ábra egy olyan kezdőlapot mutat be, amely a modulkönyvtár és a „gyár” téma alapján készült.</span><span class="sxs-lookup"><span data-stu-id="d264e-109">The following illustration shows an example of a home page that was built by using the module library and the "Fabrikam" theme.</span></span>

![Példa a kezdőlapra](./media/Homepage2.PNG)

<span data-ttu-id="d264e-111">A kezdőlap felső részén egy fejléc jelenik meg, amely az összes termékkategóriát és az egyéb olyan oldalakt, amelyet a kereskedő azt szeretné, hogy böngésznének.</span><span class="sxs-lookup"><span data-stu-id="d264e-111">The top of the home page has a header that shows all the product categories and other pages that the retailer wants customers to browse.</span></span> <span data-ttu-id="d264e-112">A kezdőlaplap alján van egy lábléc, amely gyorshivatkozásokat tartalmaz a különböző témájú témákhoz, amelyek érdekesek lehetnek a vevők számára.</span><span class="sxs-lookup"><span data-stu-id="d264e-112">The bottom of the home page has a footer that contains quick links to various topics that might interest customers.</span></span>

<span data-ttu-id="d264e-113">A kezdőlap fő része a termékeket, kategóriákat vagy promóciókat jelenít meg különböző Dynamics 365 Commerce modulok használatával:</span><span class="sxs-lookup"><span data-stu-id="d264e-113">The main section of the home page can highlight products, categories, or promotions by using various Dynamics 365 Commerce modules:</span></span>

- <span data-ttu-id="d264e-114">**Főkép** – Általában a fő szakasz felső részén található első elem egy vagy több „főkép” képet jelenít meg, amelyek az üzlet új termékekeit és promócióit emelik ki.</span><span class="sxs-lookup"><span data-stu-id="d264e-114">**Hero** – Typically, the first item at the top of the main section shows one or more "hero" images that highlight new products and promotions in the store.</span></span> <span data-ttu-id="d264e-115">Ha több főkép van, akkor egy forgótár modulban vannak tárolva, így a felhasználók böngészhetik azokat.</span><span class="sxs-lookup"><span data-stu-id="d264e-115">If there are multiple hero images, they are hosted in a carousel module so that users can browse them.</span></span>

    <span data-ttu-id="d264e-116">A következő ábra egy olyan kezdőlap példáját mutatja be, amelynél a fő szakasz első eleme egy „Most érkezett” nevű tartalomblokk modul főkép-elrendezése.</span><span class="sxs-lookup"><span data-stu-id="d264e-116">The following illustration shows an example of a home page where the first item in the main section is a hero layout of a content block module that is named "New Arrival."</span></span>

    ![Példa egy főkép modulra](./media/Hero.PNG)

- <span data-ttu-id="d264e-118">**Funkció** – a tartalomblokk modul funkcióelrendezése a termékek és a promóciók képek és szövegek kombinálásával történő forgalmazására szolgál.</span><span class="sxs-lookup"><span data-stu-id="d264e-118">**Feature** – A feature layout of a content block module is used to market products or promotions by using a combination of images and text.</span></span> <span data-ttu-id="d264e-119">A funkcióelrendezések önállóan is használhatók, de elhelyezhetők forgótár modulban is.</span><span class="sxs-lookup"><span data-stu-id="d264e-119">Features layouts can be used independently, or they can be hosted in a carousel module.</span></span>

    <span data-ttu-id="d264e-120">A következő ábra a kezdőlapon található tartalomblokk modul funkcióelrendezésére mutat be egy példát.</span><span class="sxs-lookup"><span data-stu-id="d264e-120">The following illustration shows an example of feature layout of a content block module on a home page.</span></span>

    ![Példák a funkciómodulokra](./media/Feature.PNG)

- <span data-ttu-id="d264e-122">**Csempe** – a tartalomblokk modul csempeelrendezése a különböző termékek vagy termékkategóriák megjelenítésére szolgál a képek és a szöveg kombinációjának használatával a többoszlopos elrendezésben.</span><span class="sxs-lookup"><span data-stu-id="d264e-122">**Tile** – A tile layout of a content block module is used to showcase multiple products or category of products by using a combination of images and text in a multicolumn layout.</span></span> <span data-ttu-id="d264e-123">A jelen témakörben korábban bemutatott kezdőlap illusztráción egy csempeelrendezés van használva a **Vásárlás nőknek**, **Vásárlás férfiaknak** és **Kiegészítők vásárlása** háromoszlopos leképezéshez.</span><span class="sxs-lookup"><span data-stu-id="d264e-123">In the illustration of a home page that appears earlier in this topic, a tile  layout is used for the three-column rendering of the **Shop Women**, **Shop Men**, and **Shop Accessories** items.</span></span>
- <span data-ttu-id="d264e-124">**Videolejátszó** – A videolejátszó modul videotartalom megjelenítésére használható a kezdőlapon.</span><span class="sxs-lookup"><span data-stu-id="d264e-124">**Video player** – A video player module can be used to showcase video content on the home page.</span></span> <span data-ttu-id="d264e-125">A témakörben korábban bemutatott Kezdőlap illusztrációja egy videolejátszó modult is tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="d264e-125">The illustration of a home page that appears earlier in this topic includes a video player module.</span></span>
- <span data-ttu-id="d264e-126">**Szövegblokk** – a tartalomgazdag blokkmodul a kezdőlapon egy egyoszlopos vagy többoszlopos elrendezésben megjeleníthető szöveges tartalom megjelenítésére használható.</span><span class="sxs-lookup"><span data-stu-id="d264e-126">**Text block** – A content rich block module can be used to present text content on the home page in a single-column or multicolumn layout.</span></span>
- <span data-ttu-id="d264e-127">**Termékjavaslatok** – A termékjavaslatok modulok olyan listák megjelenítésére használhatók a kezdőlapon, mint az **Új**, **Népszerű** és **Legkelendőbb**.</span><span class="sxs-lookup"><span data-stu-id="d264e-127">**Product recommendations** – Product recommendations modules are used to show lists, such as **New**, **Trending**, and **Best Selling** on the home page.</span></span> <span data-ttu-id="d264e-128">Ezek a listák a termékeket a vásárlási trendek alapján jelenítik meg, és a algoritmussal generálhaók vagy manuálisan is összeállíthatók.</span><span class="sxs-lookup"><span data-stu-id="d264e-128">These lists showcase products based on shopping trends, and they can be algorithmically generated or manually curated.</span></span> <span data-ttu-id="d264e-129">Segítségükkel a vevők gyorsan felfedezhetik a legnépszerűbb termékeket, majd folytathatják a vásárlást.</span><span class="sxs-lookup"><span data-stu-id="d264e-129">They help customers quickly discover top products and then continue to shop.</span></span>

    <span data-ttu-id="d264e-130">A következő ábra a kezdőlapon található termékjavaslatok modulra mutat be egy példát.</span><span class="sxs-lookup"><span data-stu-id="d264e-130">The following illustration shows an example of product recommendations modules on a home page.</span></span>

    ![Példák a termékjavaslatok modulokra](./media/Recommendations.PNG)

> [!NOTE]
> <span data-ttu-id="d264e-132">Minden itt felsorolt modul használható bármilyen a webhely összes oldalán.</span><span class="sxs-lookup"><span data-stu-id="d264e-132">All the modules that are listed here can be used on any site page.</span></span> <span data-ttu-id="d264e-133">Azonban a kezdőlapon történő elhelyezésük fontos, mert ez az a lap, amellyel a vevők először találkoznak a webhelyen.</span><span class="sxs-lookup"><span data-stu-id="d264e-133">However, their placement on the home page is important because that page is where customers first interact with your site.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d264e-134">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="d264e-134">Additional resources</span></span>

[<span data-ttu-id="d264e-135">Termékadatok oldalainak áttekintése</span><span class="sxs-lookup"><span data-stu-id="d264e-135">Product details pages overview</span></span>](quick-tour-pdp.md)

[<span data-ttu-id="d264e-136">Kosár és pénztár oldalainak áttekintése</span><span class="sxs-lookup"><span data-stu-id="d264e-136">Cart and checkout pages overview</span></span>](quick-tour-cart-checkout.md)

[<span data-ttu-id="d264e-137">Fiókkezelési oldalak áttekintése</span><span class="sxs-lookup"><span data-stu-id="d264e-137">Account management pages overview</span></span>](quick-tour-account-management.md)
