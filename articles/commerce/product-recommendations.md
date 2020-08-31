---
title: Termékajánlatok áttekintése
description: Ez a témakör a rendezési termékjavaslatok ismertetését tartalmazza. A termékjavaslatoknak köszönhetően a vevők egyszerűen és gyorsan megtalálják azokat a termékeket, amelyeket szeretnének, és még olyanokat is, amelyek eredetileg nem szándékoznak megvásárolni.
author: Moonma
manager: AnnBe
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: moonma
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 5aa7db8e53906f9e1416b912fe2c3b70d5430258
ms.sourcegitcommit: 8905d7a7a010e451c5435086480f66650ec54926
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/06/2020
ms.locfileid: "3664882"
---
# <a name="product-recommendations-overview"></a><span data-ttu-id="6f2f8-104">Termékajánlatok áttekintése</span><span class="sxs-lookup"><span data-stu-id="6f2f8-104">Product recommendations overview</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="6f2f8-105">A Microsoft Dynamics 365 Commerce a termékjavaslatok megjelenítésére használható az e-kereskedelmi webhelyeken és a pénztári (POS) eszközön.</span><span class="sxs-lookup"><span data-stu-id="6f2f8-105">Microsoft Dynamics 365 Commerce can be used to show product recommendations on the e-Commerce website and point of sale (POS) device.</span></span> <span data-ttu-id="6f2f8-106">A termékjavaslatok olyan cikkek, amelyeket a vevő számára érdekesek lehetnek.</span><span class="sxs-lookup"><span data-stu-id="6f2f8-106">Product recommendations are items that a customer might be interested in.</span></span> <span data-ttu-id="6f2f8-107">Az ajánlások az online és a fizikai áruházakban a más vevők beszerzési trendjein alapulnak.</span><span class="sxs-lookup"><span data-stu-id="6f2f8-107">The recommendations are based on the purchase trends of other customers in online and brick-and-mortar stores.</span></span>

<span data-ttu-id="6f2f8-108">A termékjavaslatok révén a vevők egyszerűen és gyorsan megtalálják azokat a termékeket, amelyeket szeretnének, és mindeközben jó élményben van részük.</span><span class="sxs-lookup"><span data-stu-id="6f2f8-108">Product recommendations allow customers to easily and quickly find products that they want while they have an experience that serves them well.</span></span> <span data-ttu-id="6f2f8-109">A kereszt- és felülértékesítések arra is használhatók, hogy a vásárlók olyan termékeket is találjanak, amelyeket eredetileg nem is szándékoztak megvásárolni.</span><span class="sxs-lookup"><span data-stu-id="6f2f8-109">Cross-selling and upselling can even be used to assist customers find additional products that they didn't originally intend to buy.</span></span> <span data-ttu-id="6f2f8-110">Amikor a termékek felfedezésével kapcsolatos támogatáshoz használják a javaslatokat, több konverziós lehetőséget is kialakíthatnak, és ezek elősegítik az értékesítési bevételek növelését, valamint javíthatják a vevői elégedettséget és a visszatartást.</span><span class="sxs-lookup"><span data-stu-id="6f2f8-110">When recommendations are used to enhance product discovery, they create more conversion opportunities, help increase sales revenue, and even amplify customer satisfaction and retention.</span></span>

<span data-ttu-id="6f2f8-111">Az e-kereskedelemben a termékjavaslatokat a Microsoft Recommendations gép tanulási technológiái támogatják.</span><span class="sxs-lookup"><span data-stu-id="6f2f8-111">In e-Commerce, product recommendations are powered by Microsoft Recommendations machine learning technologies on a large scale.</span></span>

## <a name="recommendation-service"></a><span data-ttu-id="6f2f8-112">Ajánlási szolgáltatás</span><span class="sxs-lookup"><span data-stu-id="6f2f8-112">Recommendation service</span></span>

<span data-ttu-id="6f2f8-113">A termékajánlások szolgáltatás mesterséges intelligencia és a gépi tanulás (AI-ML) technológiák felhasználását használja a következő módon:</span><span class="sxs-lookup"><span data-stu-id="6f2f8-113">The product recommendations service utilizes artificial intelligence and machine learning (AI-ML) technologies in the following way:</span></span>

- <span data-ttu-id="6f2f8-114">Az ajánlási szolgáltatásnak megfelelő formátumú adatokat a rendszer kivonja az adatokat a Commerce működési adatbázisából, és elküldi őket az Azure Data Lake Storage megoldásba vagy az entitástárba.</span><span class="sxs-lookup"><span data-stu-id="6f2f8-114">Data in the format that the Recommendation service requires is extracted from the Commerce operational database and sent to Azure Data Lake Storage or Entity store.</span></span>
- <span data-ttu-id="6f2f8-115">Az ajánlási szolgáltatás a tárolt adatokat az ajánlási modellek tanításához használja a **Másoknak ez is tetszett**, **Gyakran együtt vásárolt**, **Új**, **Legkelendőbb** és **Legnépszerűbbek** listákhoz.</span><span class="sxs-lookup"><span data-stu-id="6f2f8-115">The recommendations service uses the stored data to train recommendation models for the **People also like**, **Frequently bought together**, **New**, **Best selling**, and **Trending** lists.</span></span>

## <a name="scenarios"></a><span data-ttu-id="6f2f8-116">Forgatókönyvek</span><span class="sxs-lookup"><span data-stu-id="6f2f8-116">Scenarios</span></span>

<span data-ttu-id="6f2f8-117">Az alábbi POS-esetekben érhetők el a termékajánlások.</span><span class="sxs-lookup"><span data-stu-id="6f2f8-117">Product recommendations are available for the following scenarios:</span></span>

- <span data-ttu-id="6f2f8-118">**Az e-Commerce-ben egy üzlet böngészési vagy érkezőoldalán**: Ha a vevők vagy az üzlet munkatársai meglátogatják a bolt egy oldalát, akkor az ajánlási rendszer az **Új**, **Legkelendőbb**és **Legnépszerűbb** listákban javasolhat termékeket.</span><span class="sxs-lookup"><span data-stu-id="6f2f8-118">**On any store page for browsing or landing page in e-Commerce:** If customers or store associates visit a store page, the recommendation engine can suggest products in the **New**, **Best Selling**, and **Trending** lists.</span></span>
- <span data-ttu-id="6f2f8-119">**A Termékrészletek oldalon:** Ha a vevők vagy az üzlet munkatársai felkeresnek egy **Termékrészletek** lapot, akkor az ajánlási motor további, valószínűleg megvásárolni kívánt cikkeket javasol.</span><span class="sxs-lookup"><span data-stu-id="6f2f8-119">**On the Product details page:** If customers or store associates visit a **Product details** page, the recommendation engine suggests additional items that are also likely to be purchased.</span></span> <span data-ttu-id="6f2f8-120">Ezek a cikkek a **Másoknak ez is tetszett** listán jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="6f2f8-120">These items appear in the **People also like** list.</span></span>
- <span data-ttu-id="6f2f8-121">**A tranzakció oldalon vagy a pénztár oldalon:** Az ajánlási motor a kosárban található cikkek teljes listája alapján javasolja a cikkeket.</span><span class="sxs-lookup"><span data-stu-id="6f2f8-121">**On the Transaction page or the checkout page:** The recommendation engine suggests items, based on the whole list of items in the basket.</span></span> <span data-ttu-id="6f2f8-122">Ezek a cikkek megjelennek a **Gyakran együtt vásárolt** listán.</span><span class="sxs-lookup"><span data-stu-id="6f2f8-122">These items appear in the **Frequently bought together** list.</span></span>
- <span data-ttu-id="6f2f8-123">**Személyre szabott ajánlások:**: a kereskedők a bejelentkezett vevők számára személyre szabott **kitárolásokat** adhatnak meg a listán, emellett olyan új funkciókat, amelyek lehetővé teszik a meglévő lista-forgatókönyvek személyre szabását a vevő alapján.</span><span class="sxs-lookup"><span data-stu-id="6f2f8-123">**Personalized recommendations:** Merchandizers can provide signed-in customers a personalized **picks for you** list, in addition to new functionality that allows for existing list scenarios to be personalized based on that customer.</span></span> <span data-ttu-id="6f2f8-124">További információ: [Személyre szabott ajánlatok engedélyezése.](personalized-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="6f2f8-124">To learn more, see [Enable personalized recommendations.](personalized-recommendations.md).</span></span>

### <a name="types-of-product-recommendations"></a><span data-ttu-id="6f2f8-125">Termékajánlatok típusai</span><span class="sxs-lookup"><span data-stu-id="6f2f8-125">Types of product recommendations</span></span>

<span data-ttu-id="6f2f8-126">A következő táblázat leírja, hogy milyen automatizált termék-javaslatok érhetők el a kiskereskedők számára a Dynamics 365 Commerce megoldás implementálásához a [termékkollekciók modulban](product-collection-module-overview.md).</span><span class="sxs-lookup"><span data-stu-id="6f2f8-126">The following table describes various types of automated product recommendations available for retailers to implement in their Dynamics 365 Commerce solution via the [product collection module](product-collection-module-overview.md).</span></span> <span data-ttu-id="6f2f8-127">A kereskedők megjeleníthetik a bejelentkezett felhasználó testreszabott eredményeit, ha a webhely szerzője ezt a lehetőséget választja.</span><span class="sxs-lookup"><span data-stu-id="6f2f8-127">Retailers can also show personalized results for a signed-in user if the site author chooses that option.</span></span>

| <span data-ttu-id="6f2f8-128">Termékgyűjtési modul</span><span class="sxs-lookup"><span data-stu-id="6f2f8-128">Product collection module</span></span>  | <span data-ttu-id="6f2f8-129">Típus</span><span class="sxs-lookup"><span data-stu-id="6f2f8-129">Type</span></span> | <span data-ttu-id="6f2f8-130">Leírás</span><span class="sxs-lookup"><span data-stu-id="6f2f8-130">Description</span></span> |
|----------------------------|------|-------------|
| <span data-ttu-id="6f2f8-131">Új</span><span class="sxs-lookup"><span data-stu-id="6f2f8-131">New</span></span>                        | <span data-ttu-id="6f2f8-132">Algoritmikus</span><span class="sxs-lookup"><span data-stu-id="6f2f8-132">Algorithmic</span></span> | <span data-ttu-id="6f2f8-133">A modul a csatornákhoz és katalógusokhoz nemrég hozzárendelt legújabb termékek listáját jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="6f2f8-133">This module shows a list of the newest products that have been recently assorted to channels and catalogs.</span></span> |
| <span data-ttu-id="6f2f8-134">Legnépszerűbb</span><span class="sxs-lookup"><span data-stu-id="6f2f8-134">Best selling</span></span>               | <span data-ttu-id="6f2f8-135">Algoritmikus</span><span class="sxs-lookup"><span data-stu-id="6f2f8-135">Algorithmic</span></span> | <span data-ttu-id="6f2f8-136">Ez a modul a termék listáját jeleníti meg, amelyek az eladások száma alapján van rendezve.</span><span class="sxs-lookup"><span data-stu-id="6f2f8-136">This module shows a list of products that are ranked by the highest number of sales.</span></span> |
| <span data-ttu-id="6f2f8-137">Felkapott</span><span class="sxs-lookup"><span data-stu-id="6f2f8-137">Trending</span></span>                   | <span data-ttu-id="6f2f8-138">Algoritmikus</span><span class="sxs-lookup"><span data-stu-id="6f2f8-138">Algorithmic</span></span> | <span data-ttu-id="6f2f8-139">Ez a modul egy adott időszakra vonatkozóan megjeleníti a legjobban teljesítő termékek listáját a legmagasabb eladások alapján rangsorolva.</span><span class="sxs-lookup"><span data-stu-id="6f2f8-139">This module shows a list of the highest-performing products for a given period, ranked by highest number of sales.</span></span>  |
| <span data-ttu-id="6f2f8-140">Gyakran együtt vásárolt</span><span class="sxs-lookup"><span data-stu-id="6f2f8-140">Frequently bought together</span></span> | <span data-ttu-id="6f2f8-141">MI-ML</span><span class="sxs-lookup"><span data-stu-id="6f2f8-141">AI-ML</span></span> | <span data-ttu-id="6f2f8-142">Ez a modul a leggyakrabban együtt vásárolt termékek listáját ajánlja, a fogyasztók aktuális kosártartalmával együtt.</span><span class="sxs-lookup"><span data-stu-id="6f2f8-142">This module recommends a list of products that are commonly purchased together with the contents of the consumers current cart.</span></span> |
| <span data-ttu-id="6f2f8-143">Szintén kedvelt</span><span class="sxs-lookup"><span data-stu-id="6f2f8-143">People also like</span></span>           | <span data-ttu-id="6f2f8-144">MI-ML</span><span class="sxs-lookup"><span data-stu-id="6f2f8-144">AI-ML</span></span> | <span data-ttu-id="6f2f8-145">Ez a modul termékeket ajánlja fel egy adott megtekintett termékre a fogyasztói beszerzési minták alapján.</span><span class="sxs-lookup"><span data-stu-id="6f2f8-145">This module recommends products for a given seed product based on consumer purchase patterns.</span></span> |
| <span data-ttu-id="6f2f8-146">Önnek ajánljuk</span><span class="sxs-lookup"><span data-stu-id="6f2f8-146">Picks for you</span></span>              | <span data-ttu-id="6f2f8-147">MI-ML</span><span class="sxs-lookup"><span data-stu-id="6f2f8-147">AI-ML</span></span> | <span data-ttu-id="6f2f8-148">Ez a modul a termékek személyre szabott listáját ajánlja a bejelentkezett felhasználó beszerzési szokásai alapján.</span><span class="sxs-lookup"><span data-stu-id="6f2f8-148">This module recommends a personalized list of products based on purchase patterns of the signed-in user.</span></span> <span data-ttu-id="6f2f8-149">A vendégfelhasználó számára ez a lista összecsukott állapotban lesz.</span><span class="sxs-lookup"><span data-stu-id="6f2f8-149">For a guest user, this list will be collapsed.</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="6f2f8-150">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="6f2f8-150">Additional resources</span></span>

[<span data-ttu-id="6f2f8-151">Az Azure Data Lake Storage engedélyezése a Dynamics 365 Commerce környezetben</span><span class="sxs-lookup"><span data-stu-id="6f2f8-151">Enable Azure Data Lake Storage in a Dynamics 365 Commerce environment</span></span>](enable-adls-environment.md)

[<span data-ttu-id="6f2f8-152">Termékajánlatok engedélyezése</span><span class="sxs-lookup"><span data-stu-id="6f2f8-152">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="6f2f8-153">Személyre szabott ajánlatok engedélyezése</span><span class="sxs-lookup"><span data-stu-id="6f2f8-153">Enable personalized recommendations</span></span>](personalized-recommendations.md)

[<span data-ttu-id="6f2f8-154">Személyre szabott termékajánlatok kikapcsolása</span><span class="sxs-lookup"><span data-stu-id="6f2f8-154">Opt out of personalized recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="6f2f8-155">A hasonlóak megvásárlására vonatkozó javaslatok engedélyezése</span><span class="sxs-lookup"><span data-stu-id="6f2f8-155">Enable "shop similar looks" recommendations</span></span>](shop-similar-looks.md)

[<span data-ttu-id="6f2f8-156">Termékajánlatok hozzáadása a pénztárnál</span><span class="sxs-lookup"><span data-stu-id="6f2f8-156">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="6f2f8-157">Ajánlatok hozzáadása a tranzakció képernyőjéhez</span><span class="sxs-lookup"><span data-stu-id="6f2f8-157">Add recommendations to the transaction screen</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="6f2f8-158">AI-ML ajánlások eredményeinek helyesbítése</span><span class="sxs-lookup"><span data-stu-id="6f2f8-158">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="6f2f8-159">Válogatott ajánlások manuális létrehozása</span><span class="sxs-lookup"><span data-stu-id="6f2f8-159">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="6f2f8-160">Ajánlások létrehozása bemutató adatokkal</span><span class="sxs-lookup"><span data-stu-id="6f2f8-160">Create recommendations with demo data</span></span>](product-recommendations-demo-data.md)

[<span data-ttu-id="6f2f8-161">Termékajánlatok GYIK-je</span><span class="sxs-lookup"><span data-stu-id="6f2f8-161">Product recommendations FAQ</span></span>](faq-recommendations.md)
