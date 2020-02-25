---
title: Felhőalapú keresés – áttekintés
description: Ez a témakör áttekintést nyújt a felhőalapú keresésről a Microsoft Dynamics 365 Commerce alkalmazásban.
author: v-chgri
manager: annbe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: de0981d3200c2b1d62cab7600d2382bd11dd4b20
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/01/2020
ms.locfileid: "3002243"
---
# <a name="cloud-powered-search-overview"></a><span data-ttu-id="fef05-103">Felhőalapú keresés – áttekintés</span><span class="sxs-lookup"><span data-stu-id="fef05-103">Cloud-powered search overview</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="fef05-104">Ez a témakör áttekintést nyújt a felhőalapú keresésről a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="fef05-104">This topic gives an overview of cloud-powered search in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="fef05-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="fef05-105">Overview</span></span>

<span data-ttu-id="fef05-106">A termék felderíthetővé tételével biztosíthatja, hogy a vevők gyorsan és egyszerűen megtalálják a termékeket a kategóriák böngészésével, kereséssel és szűréssel.</span><span class="sxs-lookup"><span data-stu-id="fef05-106">Product discoverability helps guarantee that customers can quickly and easily find products by browsing categories, searching, and filtering.</span></span> <span data-ttu-id="fef05-107">A kiskereskedők a termékfelderítésre elsődleges eszközként tekintenek az ügyfélinterakciókhoz összes kiskereskedelmi csatornán.</span><span class="sxs-lookup"><span data-stu-id="fef05-107">Retailers consider product discovery a primary tool for customer interaction across all retail channels.</span></span>

<span data-ttu-id="fef05-108">A vevők megszokták a webes keresőmotorok, a kifinomult e-kereskedelmi webhelyek, a közösségi alkalmazások, a keresőkifejezések gépelésekor megjelenő automatikus javaslatok, a jellemzőalapú navigáció és a kiemelés szinte azonnali reakcióidejét.</span><span class="sxs-lookup"><span data-stu-id="fef05-108">Customers are accustomed to the nearly instantaneous response times of web search engines, sophisticated e-Commerce websites, social apps, automatic suggestions that appear as they type search terms, faceted navigation, and highlighting.</span></span> <span data-ttu-id="fef05-109">Ha a vevők nem találnak meg elég gyorsan egy terméket egy e-kereskedelmi áruházban, akkor habozás nélkül váltani fognak egy másik e-kereskedelmi áruházra.</span><span class="sxs-lookup"><span data-stu-id="fef05-109">If customers can't find the product that they are looking for quickly enough in one e-Commerce store, they won't hesitate to go to a different e-Commerce store.</span></span>

<span data-ttu-id="fef05-110">A felhőalapú termék-felderíthetőség a Dynamics 365 Commerce alkalmazásban segít a kiskereskedőknek a vásárlók megtartásának és a konverziós rátának a növelésében az összes csatornán, mind az e-kereskedelmi csatornákat, mind a pénztár (POS) csatornákat beleértve.</span><span class="sxs-lookup"><span data-stu-id="fef05-110">The cloud-powered product discoverability in Dynamics 365 Commerce helps retailers continue to increase consumer retention and conversion rates across all channels, both e-Commerce channels and point of sale (POS) channels.</span></span>

<span data-ttu-id="fef05-111">A Dynamics 365 Commerce keresési élmény továbbfejlesztett képességekkel rendelkezik, amelyek segítenek a kiskereskedők számára a jobb termék-felderíthetőség elérésében.</span><span class="sxs-lookup"><span data-stu-id="fef05-111">The Dynamics 365 Commerce search experience has improved capabilities to help retailers achieve better product discoverability.</span></span> <span data-ttu-id="fef05-112">Ezek a képességek egyidejűleg az e-kereskedelmi forgalomhoz szükséges méretezhetőséget és teljesítményt is biztosítják.</span><span class="sxs-lookup"><span data-stu-id="fef05-112">At the same time, these capabilities deliver the scalability and performance that are required for e-Commerce traffic.</span></span>

## <a name="browse-and-search"></a><span data-ttu-id="fef05-113">Böngészés és keresés</span><span class="sxs-lookup"><span data-stu-id="fef05-113">Browse and search</span></span>

<span data-ttu-id="fef05-114">A keresés relevanciája és teljesítménye kulcsfontosságú tényező a többcsatornás élményben, mivel a termékek felderítése elsősorban az információ lekérésére és a tartalom navigálására szolgáló keresési funkció alapján történik.</span><span class="sxs-lookup"><span data-stu-id="fef05-114">Search relevance and performance are key factors in the omnichannel experience, because product discovery relies primarily on search functionality for information retrieval and content navigation.</span></span> <span data-ttu-id="fef05-115">A hatékony és hatásos böngészési és keresési élmény növeli a konverziót.</span><span class="sxs-lookup"><span data-stu-id="fef05-115">An effective and efficient browse and search experience helps increase conversion.</span></span>

<span data-ttu-id="fef05-116">A következő ábra a jellemző böngészési és keresési funkciók egy példáját mutatja be.</span><span class="sxs-lookup"><span data-stu-id="fef05-116">The following illustration shows an example of typical browse and search functionality.</span></span>

![Keresés céloldala](./media/SearchLanding.png)

## <a name="faceted-navigation-and-choice-summary"></a><span data-ttu-id="fef05-118">A jellemzőalapú navigáció és a választási lehetőségek összegzése</span><span class="sxs-lookup"><span data-stu-id="fef05-118">Faceted navigation and choice summary</span></span> 

<span data-ttu-id="fef05-119">A jellemzőalapú navigálás révén a vevők könnyebben böngészhetik a tartalmat, ha megadják azokat a finomítók számára, amelyek egy kifejezéskészlet kifejezéseihez kötődnek.</span><span class="sxs-lookup"><span data-stu-id="fef05-119">Faceted navigation helps customers more easily browse for content by letting them filter on refiners that are linked to terms in a term set.</span></span> <span data-ttu-id="fef05-120">Ha egy vevő kiválasztott és alkalmazott finomítókat, akkor megjelenik a választási lehetőségek összesítése.</span><span class="sxs-lookup"><span data-stu-id="fef05-120">After a customer has selected and applied refiners, a summary of the choices is shown.</span></span> 

<span data-ttu-id="fef05-121">A jellemzőalapú navigáció segítségével különböző finomítók állíthatók be a kifejezéskészlet különböző kifejezéseihez anélkül, hogy további oldalakat kellene létrehoznia.</span><span class="sxs-lookup"><span data-stu-id="fef05-121">By using faceted navigation, you can configure different refiners for different terms in a term set, without having to create additional pages.</span></span> 

<span data-ttu-id="fef05-122">A következő ábra egy példát mutat be, ahol a jellemzőalapú navigálás kerül felhasználásra egy keresésben.</span><span class="sxs-lookup"><span data-stu-id="fef05-122">The following illustration shows an example where faceted navigation is used in a search.</span></span>

![Választási lehetőségek összegzése](./media/ChoiceSummary.png)

## <a name="immersive-autosuggest"></a><span data-ttu-id="fef05-124">Modern automatikus ajánlások</span><span class="sxs-lookup"><span data-stu-id="fef05-124">Immersive autosuggest</span></span>

<span data-ttu-id="fef05-125">A jelenlegi automatikus ajánlások funkció csak azokat a kulcsszavakat jeleníti meg, amelyek a megfelelő kulcsszó keresését jelenítik meg.</span><span class="sxs-lookup"><span data-stu-id="fef05-125">Current autosuggest functionality just shows keywords that trigger a search for the matching keyword.</span></span> <span data-ttu-id="fef05-126">Az új fejlesztések miatt a Dynamics 365 Commerce vevői gyakran a gépelés befejeződése előtt felfedezhetik a termékekre mutató hivatkozásokat.</span><span class="sxs-lookup"><span data-stu-id="fef05-126">Because of new enhancements in Dynamics 365 Commerce, customers can often discover links to products before they have finished typing.</span></span>

<span data-ttu-id="fef05-127">Dynamics 365 Commerce támogatja a kulcsszavas egyeztetések működését is a különböző kategóriákban.</span><span class="sxs-lookup"><span data-stu-id="fef05-127">Dynamics 365 Commerce also supports functionality for keyword matches in various categories.</span></span> <span data-ttu-id="fef05-128">Ez a funkció lehetővé teszi a vevők számára, hogy megtekintsék az egyező kulcsszavak számát a kategóriákban, és más kategóriákban keressenek egy kifejezést.</span><span class="sxs-lookup"><span data-stu-id="fef05-128">This functionality lets customers see the number of matching keywords across categories and trigger a search for a keyword in other categories.</span></span>

<span data-ttu-id="fef05-129">A következő ábra egy példát mutat be, ahol a modern automatikus javaslat van használatban.</span><span class="sxs-lookup"><span data-stu-id="fef05-129">The following illustration shows an example where immersive autosuggest is being used.</span></span>

![modern automatikus ajánlások](./media/ImmersiveAutoSuggestUX.png)

## <a name="sort"></a><span data-ttu-id="fef05-131">Rendezés</span><span class="sxs-lookup"><span data-stu-id="fef05-131">Sort</span></span>

<span data-ttu-id="fef05-132">A Dynamics 365 Commerce továbbfejlesztett rendezésével a vevők rendezhetnek, kereshetnek és böngészhetnek a keresési találatok között, valamint finomíthatják azokat ár, terméknév és termékszám szerint.</span><span class="sxs-lookup"><span data-stu-id="fef05-132">Enhanced sorting in Dynamics 365 Commerce lets customers sort, search, and browse search results, and refine them by criteria such as price, product name, and product number.</span></span> <span data-ttu-id="fef05-133">A vevők az eredményeket úgy is rendezhetik, hogy a termék új, a legnépszerűbb vagy újonnan hozzáadott-e.</span><span class="sxs-lookup"><span data-stu-id="fef05-133">Customers can also sort results based on whether a product is new, top-selling, or recently added.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="fef05-134">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="fef05-134">Additional resources</span></span>

[<span data-ttu-id="fef05-135">Az alapértelmezett kategória-céloldal és keresési találatoldal</span><span class="sxs-lookup"><span data-stu-id="fef05-135">Default category landing page and search results page</span></span>](category-search-page-overview.md)

[<span data-ttu-id="fef05-136">SEO-metaadatok kezelése</span><span class="sxs-lookup"><span data-stu-id="fef05-136">Manage SEO metadata</span></span>](manage-seo-metadata.md)
