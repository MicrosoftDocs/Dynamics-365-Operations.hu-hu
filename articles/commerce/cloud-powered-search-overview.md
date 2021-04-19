---
title: Felhőalapú keresés – áttekintés
description: Ez a témakör áttekintést nyújt a felhőalapú keresésről a Microsoft Dynamics 365 Commerce alkalmazásban.
author: ashishmsft
ms.date: 06/29/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: b5182df9d45a3b5d2572a5b6b391c924ef23bf9a
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5800421"
---
# <a name="cloud-powered-search-overview"></a><span data-ttu-id="d00ca-103">Felhőalapú keresés – áttekintés</span><span class="sxs-lookup"><span data-stu-id="d00ca-103">Cloud-powered search overview</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="d00ca-104">Ez a témakör áttekintést nyújt a felhőalapú keresésről a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="d00ca-104">This topic gives an overview of cloud-powered search in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="d00ca-105">A termék felderíthetővé tételével biztosíthatja, hogy a vevők gyorsan és egyszerűen megtalálják a termékeket a kategóriák böngészésével, kereséssel és szűréssel.</span><span class="sxs-lookup"><span data-stu-id="d00ca-105">Product discoverability helps guarantee that customers can quickly and easily find products by browsing categories, searching, and filtering.</span></span> <span data-ttu-id="d00ca-106">A kiskereskedők a termékfelderítésre elsődleges eszközként tekintenek az ügyfélinterakciókhoz összes kereskedelmi csatornán.</span><span class="sxs-lookup"><span data-stu-id="d00ca-106">Retailers consider product discovery a primary tool for customer interaction across all channels.</span></span>

<span data-ttu-id="d00ca-107">A vevők megszokták a webes keresőmotorok, a kifinomult e-kereskedelmi webhelyek, a közösségi alkalmazások, a keresőkifejezések gépelésekor megjelenő automatikus javaslatok, a jellemzőalapú navigáció és a kiemelés szinte azonnali reakcióidejét.</span><span class="sxs-lookup"><span data-stu-id="d00ca-107">Customers are accustomed to the nearly instantaneous response times of web search engines, sophisticated e-Commerce websites, social apps, automatic suggestions that appear as they type search terms, faceted navigation, and highlighting.</span></span> <span data-ttu-id="d00ca-108">Ha a vevők nem találnak meg elég gyorsan egy terméket egy e-kereskedelmi áruházban, akkor habozás nélkül váltani fognak egy másik e-kereskedelmi áruházra.</span><span class="sxs-lookup"><span data-stu-id="d00ca-108">If customers can't find the product that they are looking for quickly enough in one e-Commerce store, they won't hesitate to go to a different e-Commerce store.</span></span>

<span data-ttu-id="d00ca-109">A felhőalapú termék-felderíthetőség a Dynamics 365 Commerce alkalmazásban segít a kiskereskedőknek a vásárlók megtartásának és a konverziós rátának a növelésében az összes csatornán, mind az e-kereskedelmi csatornákat, mind a pénztár (POS) csatornákat beleértve.</span><span class="sxs-lookup"><span data-stu-id="d00ca-109">The cloud-powered product discoverability in Dynamics 365 Commerce helps retailers continue to increase consumer retention and conversion rates across all channels, both e-Commerce channels and point of sale (POS) channels.</span></span>

<span data-ttu-id="d00ca-110">A Dynamics 365 Commerce keresési élmény továbbfejlesztett képességekkel rendelkezik, amelyek segítenek a kiskereskedők számára a jobb termék-felderíthetőség elérésében.</span><span class="sxs-lookup"><span data-stu-id="d00ca-110">The Dynamics 365 Commerce search experience has improved capabilities to help retailers achieve better product discoverability.</span></span> <span data-ttu-id="d00ca-111">Ezek a képességek egyidejűleg az e-kereskedelmi forgalomhoz szükséges méretezhetőséget és teljesítményt is biztosítják.</span><span class="sxs-lookup"><span data-stu-id="d00ca-111">At the same time, these capabilities deliver the scalability and performance that are required for e-Commerce traffic.</span></span>

## <a name="browse-and-search"></a><span data-ttu-id="d00ca-112">Böngészés és keresés</span><span class="sxs-lookup"><span data-stu-id="d00ca-112">Browse and search</span></span>

<span data-ttu-id="d00ca-113">A keresés relevanciája és teljesítménye kulcsfontosságú tényező a többcsatornás élményben, mivel a termékek felderítése elsősorban az információ lekérésére és a tartalom navigálására szolgáló keresési funkció alapján történik.</span><span class="sxs-lookup"><span data-stu-id="d00ca-113">Search relevance and performance are key factors in the omnichannel experience, because product discovery relies primarily on search functionality for information retrieval and content navigation.</span></span> <span data-ttu-id="d00ca-114">A hatékony és hatásos böngészési és keresési élmény növeli a konverziót.</span><span class="sxs-lookup"><span data-stu-id="d00ca-114">An effective and efficient browse and search experience helps increase conversion.</span></span>

<span data-ttu-id="d00ca-115">A következő ábra a jellemző böngészési és keresési funkciók egy példáját mutatja be.</span><span class="sxs-lookup"><span data-stu-id="d00ca-115">The following illustration shows an example of typical browse and search functionality.</span></span>

![Keresés céloldala](./media/SearchLanding.png)

## <a name="faceted-navigation-and-choice-summary"></a><span data-ttu-id="d00ca-117">A jellemzőalapú navigáció és a választási lehetőségek összegzése</span><span class="sxs-lookup"><span data-stu-id="d00ca-117">Faceted navigation and choice summary</span></span> 

<span data-ttu-id="d00ca-118">A jellemzőalapú navigálás révén a vevők könnyebben böngészhetik a tartalmat, ha megadják azokat a finomítók számára, amelyek egy kifejezéskészlet kifejezéseihez kötődnek.</span><span class="sxs-lookup"><span data-stu-id="d00ca-118">Faceted navigation helps customers more easily browse for content by letting them filter on refiners that are linked to terms in a term set.</span></span> <span data-ttu-id="d00ca-119">Ha egy vevő kiválasztott és alkalmazott finomítókat, akkor megjelenik a választási lehetőségek összesítése.</span><span class="sxs-lookup"><span data-stu-id="d00ca-119">After a customer has selected and applied refiners, a summary of the choices is shown.</span></span> 

<span data-ttu-id="d00ca-120">A jellemzőalapú navigáció segítségével különböző finomítók állíthatók be a kifejezéskészlet különböző kifejezéseihez anélkül, hogy további oldalakat kellene létrehoznia.</span><span class="sxs-lookup"><span data-stu-id="d00ca-120">By using faceted navigation, you can configure different refiners for different terms in a term set, without having to create additional pages.</span></span> 

<span data-ttu-id="d00ca-121">A következő ábra egy példát mutat be, ahol a jellemzőalapú navigálás kerül felhasználásra egy keresésben.</span><span class="sxs-lookup"><span data-stu-id="d00ca-121">The following illustration shows an example where faceted navigation is used in a search.</span></span>

![Választási lehetőségek összegzése](./media/ChoiceSummary.png)

## <a name="immersive-autosuggest"></a><span data-ttu-id="d00ca-123">Modern automatikus ajánlások</span><span class="sxs-lookup"><span data-stu-id="d00ca-123">Immersive autosuggest</span></span>

<span data-ttu-id="d00ca-124">A jelenlegi automatikus ajánlások funkció csak azokat a kulcsszavakat jeleníti meg, amelyek a megfelelő kulcsszó keresését jelenítik meg.</span><span class="sxs-lookup"><span data-stu-id="d00ca-124">Current autosuggest functionality just shows keywords that trigger a search for the matching keyword.</span></span> <span data-ttu-id="d00ca-125">Az új fejlesztések miatt a Dynamics 365 Commerce vevői gyakran a gépelés befejeződése előtt felfedezhetik a termékekre mutató hivatkozásokat.</span><span class="sxs-lookup"><span data-stu-id="d00ca-125">Because of new enhancements in Dynamics 365 Commerce, customers can often discover links to products before they have finished typing.</span></span>

<span data-ttu-id="d00ca-126">Dynamics 365 Commerce támogatja a kulcsszavas egyeztetések működését is a különböző kategóriákban.</span><span class="sxs-lookup"><span data-stu-id="d00ca-126">Dynamics 365 Commerce also supports functionality for keyword matches in various categories.</span></span> <span data-ttu-id="d00ca-127">Ez a funkció lehetővé teszi a vevők számára, hogy megtekintsék az egyező kulcsszavak számát a kategóriákban, és más kategóriákban keressenek egy kifejezést.</span><span class="sxs-lookup"><span data-stu-id="d00ca-127">This functionality lets customers see the number of matching keywords across categories and trigger a search for a keyword in other categories.</span></span>

<span data-ttu-id="d00ca-128">A következő ábra egy példát mutat be, ahol a modern automatikus javaslat van használatban.</span><span class="sxs-lookup"><span data-stu-id="d00ca-128">The following illustration shows an example where immersive autosuggest is being used.</span></span>

![modern automatikus ajánlások](./media/ImmersiveAutoSuggestUX.png)

## <a name="sort"></a><span data-ttu-id="d00ca-130">Rendezés</span><span class="sxs-lookup"><span data-stu-id="d00ca-130">Sort</span></span>

<span data-ttu-id="d00ca-131">A Dynamics 365 Commerce továbbfejlesztett rendezésével a vevők rendezhetnek, kereshetnek és böngészhetnek a keresési találatok között, valamint finomíthatják azokat ár, terméknév és termékszám szerint.</span><span class="sxs-lookup"><span data-stu-id="d00ca-131">Enhanced sorting in Dynamics 365 Commerce lets customers sort, search, and browse search results, and refine them by criteria such as price, product name, and product number.</span></span> <span data-ttu-id="d00ca-132">A vevők az eredményeket úgy is rendezhetik, hogy a termék új, a legnépszerűbb vagy újonnan hozzáadott-e.</span><span class="sxs-lookup"><span data-stu-id="d00ca-132">Customers can also sort results based on whether a product is new, top-selling, or recently added.</span></span>

>[!NOTE]
><span data-ttu-id="d00ca-133">Ezek a felhőalapú keresési funkciók a 10.0.8 verziótól érhetők el.</span><span class="sxs-lookup"><span data-stu-id="d00ca-133">These cloud-powered search capabilities are available starting in version 10.0.8.</span></span> <span data-ttu-id="d00ca-134">Ellenőrizze, hogy a **Kereskedelmi paraméterek > Konfigurációs paraméterek** között van-e egy bejegyzés a következőhöz: „ProductSearch. UseAzureSearch 'igaz' értékre állítva”.</span><span class="sxs-lookup"><span data-stu-id="d00ca-134">Ensure that under **Commerce Parameters > Configuration Parameters** there is an entry for "ProductSearch.UseAzureSearch set to 'true'".</span></span> 
<span data-ttu-id="d00ca-135">![A felhőalapú keresés konfigurációs paraméterei](./media/CloudPoweredSearchConfigurationParameters.png)</span><span class="sxs-lookup"><span data-stu-id="d00ca-135">![Configuration parameters for cloud-powered search](./media/CloudPoweredSearchConfigurationParameters.png)</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d00ca-136">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="d00ca-136">Additional resources</span></span>

[<span data-ttu-id="d00ca-137">Alapértelmezett kategória-céloldal és keresési találatoldal áttekintése</span><span class="sxs-lookup"><span data-stu-id="d00ca-137">Default category landing page and search results page overview</span></span>](category-search-page-overview.md)

[<span data-ttu-id="d00ca-138">SEO-metaadatok kezelése</span><span class="sxs-lookup"><span data-stu-id="d00ca-138">Manage SEO metadata</span></span>](manage-seo-metadata.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
