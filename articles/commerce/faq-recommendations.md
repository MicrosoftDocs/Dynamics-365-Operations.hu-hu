---
title: Termékajánlatok GYIK-je
description: Ez a témakör a termékajánlások vagy azok eredményeivel kapcsolatos problémák elhárításához használható folyamatokkal és eszközökkel kapcsolatban tartalmaz tájékoztatást.
author: bebeale
manager: AnnBe
ms.date: 03/12/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: ''
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, Core, Operations
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 3add4e2e0d5cc16b561b808aacf5cef94fea5ae5
ms.sourcegitcommit: 1e7e7c4bc197b0a42e4d53d2a54600a2fb125b69
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/13/2020
ms.locfileid: "3127790"
---
# <a name="product-recommendations-faq"></a><span data-ttu-id="ff3ad-103">Termékajánlatok GYIK-je</span><span class="sxs-lookup"><span data-stu-id="ff3ad-103">Product recommendations FAQ</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="ff3ad-104">Ez a témakör a [termékajánlások](product-recommendations.md) vagy azok eredményeivel kapcsolatos problémák elhárításához használható folyamatokkal és eszközökkel kapcsolatban tartalmaz tájékoztatást.</span><span class="sxs-lookup"><span data-stu-id="ff3ad-104">This topic provides information about processes and tools that you can use to troubleshoot issues that are related to [product recommendations](product-recommendations.md) or their results.</span></span>

## <a name="best-practices"></a><span data-ttu-id="ff3ad-105">Gyakorlati tanácsok</span><span class="sxs-lookup"><span data-stu-id="ff3ad-105">Best practices</span></span>
<span data-ttu-id="ff3ad-106">Nagyon fontos az alaptermék és változatai fogalmának hasznosítása.</span><span class="sxs-lookup"><span data-stu-id="ff3ad-106">It's very important to utilize the concept of product masters and variants.</span></span> <span data-ttu-id="ff3ad-107">Egy adott szülő alaptermék változatainak ésszerű csoportosítása segít a listaalgoritmusoknak és a szolgáltatásnak a jobb modellek létrehozásában.</span><span class="sxs-lookup"><span data-stu-id="ff3ad-107">The sensible grouping of variants to a parent product master helps the list algorithms and service create better models.</span></span> <span data-ttu-id="ff3ad-108">A szolgáltatás ezenkívül a termék egyetlen példányát is kiszolgálhatja ahelyett, hogy egy listára helyezné az összes közeli kapcsolatban álló változatot.</span><span class="sxs-lookup"><span data-stu-id="ff3ad-108">Additionally, the service can serve just one instance of a product instead of putting all closely related variants in a list.</span></span> <span data-ttu-id="ff3ad-109">Ha minden szorosan kapcsolódó változat szerepel egy listán, akkor hibás vagy ismétlődő eredmények léphetnek fel.</span><span class="sxs-lookup"><span data-stu-id="ff3ad-109">When all closely related variants are put in a list, erroneous or duplicate results can occur.</span></span>

## <a name="why-are-products-missing-from-my-recommendation-lists"></a><span data-ttu-id="ff3ad-110">Miért hiányoznak a termékek a saját ajánlási listáimról?</span><span class="sxs-lookup"><span data-stu-id="ff3ad-110">Why are products missing from my recommendation lists?</span></span>

<span data-ttu-id="ff3ad-111">Jellemzően, ha egy cikk hiányzik egy termékajánlási listáról, akkor termékkonfigurációs probléma állhat fenn.</span><span class="sxs-lookup"><span data-stu-id="ff3ad-111">Typically, if an item is missing from a product recommendation list, there might be a product configuration issue.</span></span> <span data-ttu-id="ff3ad-112">Előfordulhat például, hogy hibás a termék kezdési vagy befejezési dátuma, a dimenziót rosszul van konfigurálva, vagy a termék nem a megfelelő csatornaszortimentben található stb.</span><span class="sxs-lookup"><span data-stu-id="ff3ad-112">For example, there might be an incorrect product start date or end date, a dimension might be misconfigured, or the product might not be in the correct channel assortment, etc.</span></span>

<span data-ttu-id="ff3ad-113">Ha egy mesterséges intelligencia-gép tanuláson (AI-ML) alapuló ajánlási listából hiányzik egy elem, előfordulhat, hogy az elem nem felel meg az ajánlási lista feltételeinek, vagy nem rendelkezik elegendő vásárlási tranzakcióval, hogy az ajánlási lista megjelenítse.</span><span class="sxs-lookup"><span data-stu-id="ff3ad-113">If an item is missing from a recommendation list that is based on artificial intelligence-machine learning (AI-ML), the item might not fit the criteria of the recommendation list, or it might not have enough purchase transactions for the recommendation list to show it.</span></span>

<span data-ttu-id="ff3ad-114">Javasoljuk, hogy ellenőrizze ezeket a lépéseket:</span><span class="sxs-lookup"><span data-stu-id="ff3ad-114">We recommend that you check these steps:</span></span>
1. <span data-ttu-id="ff3ad-115">**Ellenőrizze, hogy engedélyezve vannak-e a termékajánlások a központban.**</span><span class="sxs-lookup"><span data-stu-id="ff3ad-115">**Make sure that product recommendations have been enabled in HQ.**</span></span> <span data-ttu-id="ff3ad-116">Ha további információt szeretne a szolgáltatás bekapcsolásáról, tekintse meg a következőt: [Termékajánlatok engedélyezése](enable-product-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="ff3ad-116">For more information about how to enable this service, see [Enable product recommendations](enable-product-recommendations.md).</span></span>
1. <span data-ttu-id="ff3ad-117">**Győződjön meg róla, hogy a legfontosabb terméktulajdonságok be vannak állítva.**</span><span class="sxs-lookup"><span data-stu-id="ff3ad-117">**Make sure that key product properties are set.**</span></span> <span data-ttu-id="ff3ad-118">A termékszortimenteket például **Tartalmazza** értékre kell beállítani.</span><span class="sxs-lookup"><span data-stu-id="ff3ad-118">For example, product assortments must be set to **Include**.</span></span>
1. <span data-ttu-id="ff3ad-119">**Az szortimentbe újonnan felvett termékek esetében akár 3 órát is igénybe vehet, hogy a termék megjelenjen az új listában.**</span><span class="sxs-lookup"><span data-stu-id="ff3ad-119">**For newly assorted products, it might take up to 3 hours before the product will start appearing in the new list.**</span></span>
1. <span data-ttu-id="ff3ad-120">**Ha egy termék még nem jelenik meg a Népszerű, Legnépszerűbb, Másoknak ez is tetszett vagy a Gyakran együtt vásárolt részben, akkor előfordulhat, hogy a termék nem rendelkezik elég tranzakcióval.**</span><span class="sxs-lookup"><span data-stu-id="ff3ad-120">**If a product is still not appearing in Trending, Best selling, People also like, or Frequently bought together, then that product might not have enough transactions.**</span></span> <span data-ttu-id="ff3ad-121">Ebben az esetben megvárhatja a további tranzakciókat, frissítheti az alapértelmezett ajánlási lista paramétereit, vagy manuális beavatkozással módosíthatja az ajánlási terméklista találatait.</span><span class="sxs-lookup"><span data-stu-id="ff3ad-121">In this case, you can either wait for more transactions to occur, update the default recommendation list parameters, or use manual intervention to modify the recommendation product list results.</span></span> <span data-ttu-id="ff3ad-122">Az ajánlási paraméterekkel kapcsolatos további tudnivalókért tekintse meg a következőt: [AI-ML-alapú termékajánlási találatok kezelése](modify-product-recommendation-results.md).</span><span class="sxs-lookup"><span data-stu-id="ff3ad-122">For more information about recommendation parameters, see [Manage AI-ML-based product recommendation results](modify-product-recommendation-results.md).</span></span>
1. <span data-ttu-id="ff3ad-123">**Győződjön meg róla, hogy a termék megfelel a lista ajánlási feltételeinek.**</span><span class="sxs-lookup"><span data-stu-id="ff3ad-123">**Make sure that the product meets the recommendation criteria for the list.**</span></span> <span data-ttu-id="ff3ad-124">A termékajánlási paraméterekkel kapcsolatos további tudnivalókért tekintse meg a következőt: [AI-ML-alapú termékajánlási találatok kezelése](modify-product-recommendation-results.md).</span><span class="sxs-lookup"><span data-stu-id="ff3ad-124">For more information about product recommendation parameters, see [Manage AI-ML-based product recommendation results](modify-product-recommendation-results.md).</span></span>

## <a name="how-can-i-prevent-poor-recommendation-results-from-being-returned"></a><span data-ttu-id="ff3ad-125">Hogyan lehet megakadályozni, hogy a rendszer rossz minőségű ajánlási találatokat adjon vissza?</span><span class="sxs-lookup"><span data-stu-id="ff3ad-125">How can I prevent poor recommendation results from being returned?</span></span>

<span data-ttu-id="ff3ad-126">Az ajánlási listák esetében a találatok előállításához nagy mennyiségű tranzakcióra van szükség.</span><span class="sxs-lookup"><span data-stu-id="ff3ad-126">Recommendation lists require a large volume of transactions to produce results.</span></span> <span data-ttu-id="ff3ad-127">Ezért fontos, hogy a felhasználók teljes körű múltbeli tranzakcióadatokat adjanak meg.</span><span class="sxs-lookup"><span data-stu-id="ff3ad-127">Therefore, it's important that users provide full historical transaction data.</span></span>

<span data-ttu-id="ff3ad-128">Ezenkívül a tranzakciókkal nem rendelkező vagy kevés tranzakcióval rendelkező termékek általában nem rendelkeznek **Másoknak ez is tetszett** vagy **Gyakran együtt vásárolt** találatokkal, és nem szerepelnek a **Népszerű** vagy **Legnépszerűbb** javaslati listában.</span><span class="sxs-lookup"><span data-stu-id="ff3ad-128">Additionally, products that have no transactions or few transactions typically don't have **People also like** or **Frequently bought together** results, and don't appear in **Trending** or **Best selling** recommendation lists.</span></span> <span data-ttu-id="ff3ad-129">Ez a helyzet gyakran előfordulhat nagyon új termékek esetében, illetve olyan régi termékek esetében, amelyeknél kis számú vásárlás történt.</span><span class="sxs-lookup"><span data-stu-id="ff3ad-129">This situation can often occur for very new products, or for old products that have a small number of purchases.</span></span> <span data-ttu-id="ff3ad-130">A népszerű új cikkek könnyedén leküzdik ezt a problémát.</span><span class="sxs-lookup"><span data-stu-id="ff3ad-130">Popular new items will easily overcome this issue.</span></span>

<span data-ttu-id="ff3ad-131">Javasoljuk, hogy kövesse ezeket a lépéseket:</span><span class="sxs-lookup"><span data-stu-id="ff3ad-131">We recommend that you follow these steps:</span></span>
1. <span data-ttu-id="ff3ad-132">**Győződjön meg róla, hogy a termék megfelel a lista ajánlási feltételeinek.**</span><span class="sxs-lookup"><span data-stu-id="ff3ad-132">**Make sure that the product meets the recommendation criteria for that list.**</span></span> <span data-ttu-id="ff3ad-133">A termékajánlási paraméterekkel kapcsolatos további tudnivalókért tekintse meg a következőt: AI-ML-alapú termékajánlási találatok módosítása.</span><span class="sxs-lookup"><span data-stu-id="ff3ad-133">For more information about product recommendation parameters, see Modify AI-ML-based product recommendation results.</span></span>
1. <span data-ttu-id="ff3ad-134">**Ha a termék új, akkor érdemes módosítani egy ajánlási listát, amíg a termék több tranzakcióval nem rendelkezik.**</span><span class="sxs-lookup"><span data-stu-id="ff3ad-134">**If the product is new, consider modifying a recommendation list until the product has more transactions.**</span></span> <span data-ttu-id="ff3ad-135">Az ajánlási lista találatainak módosításával kapcsolatos további tudnivalókért tekintse meg a következőt: [AI-ML-alapú termékajánlási találatok kezelése](modify-product-recommendation-results.md).</span><span class="sxs-lookup"><span data-stu-id="ff3ad-135">For more information about how to modify recommendation list results, see [Manage AI-ML-based product recommendation results](modify-product-recommendation-results.md).</span></span>


- <span data-ttu-id="ff3ad-136">**Győződjön meg róla, hogy a termék megfelel a lista ajánlási feltételeinek.**</span><span class="sxs-lookup"><span data-stu-id="ff3ad-136">**Make sure that the product meets the recommendation criteria for that list.**</span></span> <span data-ttu-id="ff3ad-137">A termékajánlási paraméterekkel kapcsolatos további tudnivalókért tekintse meg a következőt: [AI-ML-alapú termékajánlási találatok kezelése](modify-product-recommendation-results.md).</span><span class="sxs-lookup"><span data-stu-id="ff3ad-137">For more information about product recommendation parameters, see [Manage AI-ML-based product recommendation results](modify-product-recommendation-results.md).</span></span>
- <span data-ttu-id="ff3ad-138">**Ha a termék új, akkor érdemes módosítani egy ajánlási listát, amíg a termék több tranzakcióval nem rendelkezik**.</span><span class="sxs-lookup"><span data-stu-id="ff3ad-138">**If the product is new, consider modifying a recommendation list until the product has more transactions**.</span></span> <span data-ttu-id="ff3ad-139">Az ajánlási lista találatainak módosításával kapcsolatos további tudnivalókért tekintse meg a következőt: [AI-ML-alapú termékajánlási találatok kezelése](modify-product-recommendation-results.md).</span><span class="sxs-lookup"><span data-stu-id="ff3ad-139">For more information about how to modify recommendation list results, see [Manage AI-ML-based product recommendation results](modify-product-recommendation-results.md).</span></span>

## <a name="can-i-remove-a-product-but-still-see-it-in-the-store"></a><span data-ttu-id="ff3ad-140">Eltávolíthatok egy terméket, és továbbra is láthatom az áruházban?</span><span class="sxs-lookup"><span data-stu-id="ff3ad-140">Can I remove a product but still see it in the store?</span></span>

<span data-ttu-id="ff3ad-141">Lehetőség van az üzleti szükségletek felmerülése esetén az algoritmus alapján generált listák módosítására.</span><span class="sxs-lookup"><span data-stu-id="ff3ad-141">You can adjust lists that are algorithmically generated if a business need arises.</span></span> <span data-ttu-id="ff3ad-142">Ha azonban egy terméket eltávolítanak egy ajánlási listából, a termék továbbra is megtalálható lesz az áruházban.</span><span class="sxs-lookup"><span data-stu-id="ff3ad-142">However, if a product is removed from a recommendation list, the product will remain discoverable in the store.</span></span> <span data-ttu-id="ff3ad-143">A termékajánlások találatainak módosításával kapcsolatos további tudnivalókért tekintse meg a következőt: [AI-ML-alapú termékajánlási találatok kezelése](modify-product-recommendation-results.md).</span><span class="sxs-lookup"><span data-stu-id="ff3ad-143">For more information about how to modify product recommendation results, see [Manage AI-ML-based product recommendation results](modify-product-recommendation-results.md).</span></span>

<span data-ttu-id="ff3ad-144">Ha blokkolni kell egy cikket, hogy ne legyen megtalálható az áruházban, módosítania kell a **Cikkszortimentek** beállítást **Kihagyás** értékre.</span><span class="sxs-lookup"><span data-stu-id="ff3ad-144">If you must block an item from being discovered in the store, you must change the **Item assortments** value to **Exclude**.</span></span>

## <a name="how-do-i-add-a-list-to-an-e-commerce-page"></a><span data-ttu-id="ff3ad-145">Hogyan lehet listát hozzáadni az e-kereskedelmi oldalhoz?</span><span class="sxs-lookup"><span data-stu-id="ff3ad-145">How do I add a list to an e-Commerce page?</span></span>

<span data-ttu-id="ff3ad-146">A termékajánlási lapoknak az e-kereskedelmi webhelyhez történő hozzáadásával kapcsolatos további tudnivalókat lásd: [Termékajánlások listájának hozzáadása lapokhoz](add-reco-list-to-page.md).</span><span class="sxs-lookup"><span data-stu-id="ff3ad-146">For information about how to add product recommendation pages to your e-Commerce website, see [Add product recommendation lists to pages](add-reco-list-to-page.md).</span></span>

## <a name="how-do-i-enable-recommendations-on-pos"></a><span data-ttu-id="ff3ad-147">Hogyan engedélyezhetők ajánlások a POS-en?</span><span class="sxs-lookup"><span data-stu-id="ff3ad-147">How do I enable recommendations on POS?</span></span>

<span data-ttu-id="ff3ad-148">A termékajánlások engedélyezése után hozzá kell adnia az ajánlások panelt a POS vezérlése képernyőhöz.</span><span class="sxs-lookup"><span data-stu-id="ff3ad-148">After enabling product recommendations, you will need to add the recommendations panel to the control POS screen.</span></span> <span data-ttu-id="ff3ad-149">További információért lásd: [Ajánlatok vezérlőjének hozzáadása a pénztáreszközök tranzakciós képernyőjéhez](add-recommendations-control-pos-screen.md).</span><span class="sxs-lookup"><span data-stu-id="ff3ad-149">For more information, see [Add a recommendations control to the transaction screen on POS devices](add-recommendations-control-pos-screen.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ff3ad-150">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="ff3ad-150">Additional resources</span></span>

[<span data-ttu-id="ff3ad-151">Termékajánlatok áttekintése</span><span class="sxs-lookup"><span data-stu-id="ff3ad-151">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="ff3ad-152">ADLS engedélyezése a Dynamics 365 Commerce környezetben</span><span class="sxs-lookup"><span data-stu-id="ff3ad-152">Enable ADLS in a Dynamics 365 Commerce environment</span></span>](enable-adls-environment.md)

[<span data-ttu-id="ff3ad-153">Termékajánlatok engedélyezése</span><span class="sxs-lookup"><span data-stu-id="ff3ad-153">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="ff3ad-154">Személyre szabott ajánlatok engedélyezése</span><span class="sxs-lookup"><span data-stu-id="ff3ad-154">Enable personalized recommendations</span></span>](personalized-recommendations.md)

[<span data-ttu-id="ff3ad-155">Személyre szabott termékajánlatok kikapcsolása</span><span class="sxs-lookup"><span data-stu-id="ff3ad-155">Opt out of personalized recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="ff3ad-156">Ajánlat listáinak hozzáadása egy e-Commerce webhelyhez</span><span class="sxs-lookup"><span data-stu-id="ff3ad-156">Add recommendation lists to an e-Commerce site</span></span>](add-reco-list-to-page.md)

[<span data-ttu-id="ff3ad-157">Termékajánlások hozzáadása a pénztárnál</span><span class="sxs-lookup"><span data-stu-id="ff3ad-157">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="ff3ad-158">Ajánlatok hozzáadása a tranzakciós képernyőhöz</span><span class="sxs-lookup"><span data-stu-id="ff3ad-158">Add recommendations to the transaction screen</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="ff3ad-159">AI-ML ajánlások eredményeinek helyesbítése</span><span class="sxs-lookup"><span data-stu-id="ff3ad-159">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="ff3ad-160">Válogatott ajánlások manuális létrehozása</span><span class="sxs-lookup"><span data-stu-id="ff3ad-160">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="ff3ad-161">Ajánlások létrehozása bemutató adatokkal</span><span class="sxs-lookup"><span data-stu-id="ff3ad-161">Create recommendations with demo data</span></span>](product-recommendations-demo-data.md)
