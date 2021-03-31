---
title: Alapértelmezett kategória-céloldal és keresési találatoldal áttekintése
description: Ez a témakör a Dynamics 365 Commerce alkalmazás alapértelmezett kategória-céloldalának és keresési találatoldalának áttekintését nyújtja
author: ashishmsft
manager: annbe
ms.date: 06/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 7a40df479bffdc6fdee8f0a7f64fde980cbbdbab
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5215721"
---
# <a name="default-category-landing-page-and-search-results-page-overview"></a><span data-ttu-id="61f59-103">Alapértelmezett kategória-céloldal és keresési találatoldal áttekintése</span><span class="sxs-lookup"><span data-stu-id="61f59-103">Default category landing page and search results page overview</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="61f59-104">Ez a témakör a Microsoft Dynamics 365 Commerce e-Commerce alkalmazás alapértelmezett kategória-céloldalának és keresési találatoldalának áttekintését nyújtja.</span><span class="sxs-lookup"><span data-stu-id="61f59-104">This topic provides an overview of the default category landing page and search results page in Microsoft Dynamics 365 Commerce e-Commerce.</span></span>

## <a name="default-category-landing-page"></a><span data-ttu-id="61f59-105">Alapértelmezett kategória-céloldal</span><span class="sxs-lookup"><span data-stu-id="61f59-105">Default category landing page</span></span>

<span data-ttu-id="61f59-106">Az alapértelmezett kategória kezdőlap az a lap, ahova a rendszer a webhely felhasználóit általában irányítja, amikor egy kategóriát választanak ki a navigációs hierarchiában.</span><span class="sxs-lookup"><span data-stu-id="61f59-106">The default category landing page is the page that website users typically are taken to when they select a category in the navigation hierarchy.</span></span> <span data-ttu-id="61f59-107">A kategória lapon tallózhat, és a kategorizált termékeket is rendezheti és finomíthatja.</span><span class="sxs-lookup"><span data-stu-id="61f59-107">The category page lets you browse, and you can also sort and refine the categorized products.</span></span>

![Alapértelmezett kategória-céloldal](./media/SimpleCategoryLandingDressCategory.png)

<span data-ttu-id="61f59-109">A lap tetején egy fejléc jelenik meg, amelyen látható az összes termékkategória és egyéb lap, amelyet a termékkihelyezési vezető kategorizált.</span><span class="sxs-lookup"><span data-stu-id="61f59-109">At the top of the page is a header that shows all the product categories and other pages that the merchandising manager has categorized.</span></span> <span data-ttu-id="61f59-110">A konfiguráció a csatorna navigációs hierarchiájának konfigurációja részeként történik.</span><span class="sxs-lookup"><span data-stu-id="61f59-110">Configuration is done as part of the configuration of the channel navigation hierarchy.</span></span> <span data-ttu-id="61f59-111">A lap alján van egy lábléc, amely gyorshivatkozásokat tartalmaz a különböző témákhoz, amelyek érdekesek lehetnek a vevők számára.</span><span class="sxs-lookup"><span data-stu-id="61f59-111">At the bottom of the page is a footer that includes quick links to various topics that a shopper might be interested in.</span></span>

<span data-ttu-id="61f59-112">A következő összetevők elengedhetetlenek a kategóriákhoz:</span><span class="sxs-lookup"><span data-stu-id="61f59-112">The following components are essential for a category:</span></span>

- <span data-ttu-id="61f59-113">A **Termékelhelyezési csempék** azokat a termékeket jelenítik meg, amelyeket a termékkihelyezési vezető meghatározott egy kategóriában a navigációs hierarchia konfigurációjának részeként.</span><span class="sxs-lookup"><span data-stu-id="61f59-113">**Product placement tiles** show the products that the merchandising manager has defined in a category as part of the configuration of the navigation hierarchy.</span></span>
- <span data-ttu-id="61f59-114">A **Finomítások és választási lehetőségek összefoglalása** olyan szűrők, amelyek számokat biztosítanak, és a cikkek finomítására használhatók.</span><span class="sxs-lookup"><span data-stu-id="61f59-114">**Refiners and choice summary** are filters that provide counts and that can be used to refine items.</span></span> <span data-ttu-id="61f59-115">A termékkihelyezési vezető a csatornakategóriákhoz és termékattribútumokhoz kapcsolódó metaadatok konfigurációjának részeként konfigurálja őket.</span><span class="sxs-lookup"><span data-stu-id="61f59-115">The merchandising manager configures them as part of the configuration of the metadata related to channel categories and product attributes.</span></span>
- <span data-ttu-id="61f59-116">A **Rendezési beállításokat** a webhely látogatói a termékek rendezéséhez használják.</span><span class="sxs-lookup"><span data-stu-id="61f59-116">**Sorting options** are used by website visitors to sort the products.</span></span> <span data-ttu-id="61f59-117">Alapértelmezés szerint a következő rendezési lehetőségek érhetők el:</span><span class="sxs-lookup"><span data-stu-id="61f59-117">By default, the following sorting options are available:</span></span>

    - <span data-ttu-id="61f59-118">Ár – növekvő sorrend</span><span class="sxs-lookup"><span data-stu-id="61f59-118">Price – low to high</span></span>
    - <span data-ttu-id="61f59-119">Ár – csökkenő sorrend</span><span class="sxs-lookup"><span data-stu-id="61f59-119">Price – high to low</span></span>
    - <span data-ttu-id="61f59-120">Termék neve – \[A–Z\]</span><span class="sxs-lookup"><span data-stu-id="61f59-120">Product name – \[A-Z\]</span></span>
    - <span data-ttu-id="61f59-121">Termék neve – \[Z–A\]</span><span class="sxs-lookup"><span data-stu-id="61f59-121">Product name – \[Z-A\]</span></span>
    - <span data-ttu-id="61f59-122">Értékelések – növekvő sorrend</span><span class="sxs-lookup"><span data-stu-id="61f59-122">Ratings – low to high</span></span>
    - <span data-ttu-id="61f59-123">Értékelések – csökkenő sorrend</span><span class="sxs-lookup"><span data-stu-id="61f59-123">Ratings – high to low</span></span>

- <span data-ttu-id="61f59-124">Az **Oldalszámozás** segítségével a webhely látogatói a kategorizált termékek találatainak egyik lapjáról a másikra kerülnek.</span><span class="sxs-lookup"><span data-stu-id="61f59-124">**Pagination** lets website visitors move from one page of categorized product results to another page.</span></span>
- <span data-ttu-id="61f59-125">A **Teljes szám** az adott kategóriába tartozó termékek teljes számát adja meg.</span><span class="sxs-lookup"><span data-stu-id="61f59-125">**Total count** provides the total number of products that are defined in a category.</span></span>

## <a name="enrich-a-category-landing-page"></a><span data-ttu-id="61f59-126">Kategória céloldalának gazdagítása</span><span class="sxs-lookup"><span data-stu-id="61f59-126">Enrich a category landing page</span></span>

<span data-ttu-id="61f59-127">Ha azt szeretné, hogy a kategória kezdőlapja egy adott kategóriára vonatkozóan testre szabottabb élményt nyújtson, akkor „bővítheti” az adott kategóriához tartozó céloldalt.</span><span class="sxs-lookup"><span data-stu-id="61f59-127">If you want a category landing page to have a more tailored experience for a specific category, you can "enrich" the category landing page for that category.</span></span> <span data-ttu-id="61f59-128">Hozzáadhat például egy marketingvideót és némi kategórialeírást a vásárló figyelmének felkeltéséhez.</span><span class="sxs-lookup"><span data-stu-id="61f59-128">For example, you can add a marketing video and some category storytelling to get the shopper's attention.</span></span> <span data-ttu-id="61f59-129">A további tudnivalókat lásd: [Kategória céloldalának bővítése](enrich-category-page.md).</span><span class="sxs-lookup"><span data-stu-id="61f59-129">For more information, see [Enrich a category landing page](enrich-category-page.md).</span></span>

![Bővített kategória-céloldal](./media/CategoryLandingPages.png)

## <a name="auto-suggest-and-search-results-pages"></a><span data-ttu-id="61f59-131">Automatikus javaslat és keresési eredmények lapjai</span><span class="sxs-lookup"><span data-stu-id="61f59-131">Auto-suggest and search results pages</span></span>

<span data-ttu-id="61f59-132">A webhely felhasználói felfedezhetik a webhelyet úgy, hogy a navigációs hierarchia egyik kategóriájába lépnek, vagy egy keresési kifejezés beírásával megadják a keresési feltételt a keresési mezőben.</span><span class="sxs-lookup"><span data-stu-id="61f59-132">Website users can explore a site either by going to a category from the navigation hierarchy or by entering a search term in the search field.</span></span>

<span data-ttu-id="61f59-133">Amint a felhasználó megkezdi a gépelést a keresési mezőben, megtapasztalhatja a keresési kifejezéseket ajánló automatikus javaslatok élményét.</span><span class="sxs-lookup"><span data-stu-id="61f59-133">As soon as users start to type in the search field, they experience the immersive auto-suggest functionality that suggests search terms.</span></span>

<span data-ttu-id="61f59-134">Az alábbiakban a javaslatok néhány típusa látható:</span><span class="sxs-lookup"><span data-stu-id="61f59-134">Here are some of the types of suggestions that might be shown:</span></span>

- <span data-ttu-id="61f59-135">A **Kulcsszavak** a cikkeknek a csatorna szortimentjébe tartozó összes termék közötti keresésére szolgálnak.</span><span class="sxs-lookup"><span data-stu-id="61f59-135">**Keywords** are used to find items across all products that are assorted to the channel.</span></span>
- <span data-ttu-id="61f59-136">A **Termékek** közvetlen kapcsolatot biztosítanak a termék részletes lapjához.</span><span class="sxs-lookup"><span data-stu-id="61f59-136">**Products** provide direct links to the product details page.</span></span>
- <span data-ttu-id="61f59-137">A **Hatókörön belüli kategória javaslatai** különböző kategóriákat sorolnak fel, és lehetővé teszik a felhasználók számára, hogy egy adott kategóriában keressenek rá a kulcsszóra.</span><span class="sxs-lookup"><span data-stu-id="61f59-137">**Scoped category search suggestions** list various categories and let users search for the keyword in a specific category.</span></span>

![Modern automatikus ajánlások](./media/ImmersiveAutoSuggestUX.png)

<span data-ttu-id="61f59-139">Amikor a felhasználók kiválasztják a kulcsszó vagy a hatókörön belüli kategória keresési javaslatainak valamelyikét, vagy ha a megadott keresési kifejezésre nem található javaslat, akkor a program a keresési találatok lapra irányítja őket.</span><span class="sxs-lookup"><span data-stu-id="61f59-139">When users select one of the keyword or scoped category search suggestions, or when there are no suggestions for the search term that they enter, they are redirected to a search results page.</span></span> <span data-ttu-id="61f59-140">A felhasználók ezután böngészhetik, rendezhetik és finomíthatják a keresési eredmények listáját a kívánt cikk megkereséséhez.</span><span class="sxs-lookup"><span data-stu-id="61f59-140">The users can then browse, sort, and refine the list of search results to find the desired item.</span></span>

![Keresés céloldala](./media/SearchLanding.png)

<span data-ttu-id="61f59-142">A következő összetevők elengedhetetlenek a keresési találatok laphoz:</span><span class="sxs-lookup"><span data-stu-id="61f59-142">The following components are essential for a search results page:</span></span>

- <span data-ttu-id="61f59-143">A **Termékelhelyezési csempék** a felhasználó kereséséhez jelenítik meg a termékeket.</span><span class="sxs-lookup"><span data-stu-id="61f59-143">**Product placement tiles** show the products for the user's search.</span></span> <span data-ttu-id="61f59-144">Alapértelmezés szerint ezek a csempék a felhasználó keresés felhőalapú relevancia-pontszáma alapján vannak sorba rendezve.</span><span class="sxs-lookup"><span data-stu-id="61f59-144">By default, these tiles are sorted by the cloud-powered search relevancy score for the user search.</span></span>
- <span data-ttu-id="61f59-145">A **Finomítások és választási lehetőségek összefoglalása** olyan szűrők, amelyek számokat biztosítanak, és a cikkek finomítására használhatók.</span><span class="sxs-lookup"><span data-stu-id="61f59-145">**Refiners and choice summary** are filters that provide counts and that can be used to refine items.</span></span> <span data-ttu-id="61f59-146">A termékkihelyezési vezető a „csatornakategóriákhoz és termékattribútumokhoz” kapcsolódó metaadatok konfigurációjának részeként konfigurálja őket.</span><span class="sxs-lookup"><span data-stu-id="61f59-146">The merchandising manager configures them as part of the configuration of the "channel categories and product attributes" metadata.</span></span>
- <span data-ttu-id="61f59-147">A **Rendezési beállításokat** a webhely látogatói a termékek rendezéséhez használják.</span><span class="sxs-lookup"><span data-stu-id="61f59-147">**Sorting options** are used by website visitors to sort the products.</span></span> <span data-ttu-id="61f59-148">Alapértelmezés szerint a következő rendezési lehetőségek érhetők el:</span><span class="sxs-lookup"><span data-stu-id="61f59-148">By default, the following sorting options are available:</span></span>

    - <span data-ttu-id="61f59-149">Ár – növekvő sorrend</span><span class="sxs-lookup"><span data-stu-id="61f59-149">Price – low to high</span></span>
    - <span data-ttu-id="61f59-150">Ár – csökkenő sorrend</span><span class="sxs-lookup"><span data-stu-id="61f59-150">Price – high to low</span></span>
    - <span data-ttu-id="61f59-151">Termék neve – \[A–Z\]</span><span class="sxs-lookup"><span data-stu-id="61f59-151">Product name – \[A-Z\]</span></span>
    - <span data-ttu-id="61f59-152">Termék neve – \[Z–A\]</span><span class="sxs-lookup"><span data-stu-id="61f59-152">Product name – \[Z-A\]</span></span>
    - <span data-ttu-id="61f59-153">Értékelések – növekvő sorrend</span><span class="sxs-lookup"><span data-stu-id="61f59-153">Ratings – low to high</span></span>
    - <span data-ttu-id="61f59-154">Értékelések – csökkenő sorrend</span><span class="sxs-lookup"><span data-stu-id="61f59-154">Ratings – high to low</span></span>
    - <span data-ttu-id="61f59-155">Alapértelmezett</span><span class="sxs-lookup"><span data-stu-id="61f59-155">Default</span></span>

- <span data-ttu-id="61f59-156">Az **Oldalszámozás** segítségével a webhely látogatói a kategorizált termékek találatainak egyik lapjáról a másikra kerülnek.</span><span class="sxs-lookup"><span data-stu-id="61f59-156">**Pagination** lets website visitors move from one page of categorized product results to another page.</span></span>
- <span data-ttu-id="61f59-157">A **Teljes szám** az adott kategóriába tartozó és a keresési feltételeknek megfelelő termékek teljes számát adja meg.</span><span class="sxs-lookup"><span data-stu-id="61f59-157">**Total count** provides the total number of products that are defined in a category and that match the search criteria.</span></span>

>[!NOTE]
><span data-ttu-id="61f59-158">Ezek a felhőalapú keresési funkciók a 10.0.8 verziótól érhetők el.</span><span class="sxs-lookup"><span data-stu-id="61f59-158">These cloud-powered search capabilities are available starting in version 10.0.8.</span></span> <span data-ttu-id="61f59-159">Ellenőrizze, hogy a **Kereskedelmi paraméterek > Konfigurációs paraméterek** között van-e egy bejegyzés a következőhöz: „ProductSearch. UseAzureSearch 'igaz' értékre állítva”.</span><span class="sxs-lookup"><span data-stu-id="61f59-159">Ensure that under **Commerce Parameters > Configuration Parameters** there is an entry for "ProductSearch.UseAzureSearch set to 'true'".</span></span> 
<span data-ttu-id="61f59-160">![A felhőalapú keresés konfigurációs paraméterei](./media/CloudPoweredSearchConfigurationParameters.png)</span><span class="sxs-lookup"><span data-stu-id="61f59-160">![Configuration parameters for cloud-powered search](./media/CloudPoweredSearchConfigurationParameters.png)</span></span>

## <a name="additional-resources"></a><span data-ttu-id="61f59-161">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="61f59-161">Additional resources</span></span>

[<span data-ttu-id="61f59-162">Felhőalapú keresés – áttekintés</span><span class="sxs-lookup"><span data-stu-id="61f59-162">Cloud-powered search overview</span></span>](cloud-powered-search-overview.md)

[<span data-ttu-id="61f59-163">Kezdőlap áttekintése</span><span class="sxs-lookup"><span data-stu-id="61f59-163">Home page overview</span></span>](quick-tour-home-page.md)

[<span data-ttu-id="61f59-164">Termékadatok oldalainak áttekintése</span><span class="sxs-lookup"><span data-stu-id="61f59-164">Product details pages overview</span></span>](quick-tour-pdp.md)

[<span data-ttu-id="61f59-165">Kosár és pénztár oldalainak áttekintése</span><span class="sxs-lookup"><span data-stu-id="61f59-165">Cart and checkout pages overview</span></span>](quick-tour-cart-checkout.md)

[<span data-ttu-id="61f59-166">Fiókkezelési oldalak áttekintése</span><span class="sxs-lookup"><span data-stu-id="61f59-166">Account management pages overview</span></span>](quick-tour-account-management.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]