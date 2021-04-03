---
title: Engedélyezze a "hasonló megvásárlása" javaslatlistákat
description: Ez a témakör azt mutatja be, hogyan lehet engedélyezni a "hasonló megjelenésű" javaslatlistákat a Microsoft Dynamics 365 Commerce szolgáltatásnál.
author: bebeale
manager: AnnBe
ms.date: 08/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: d0b3585ce326e47b119b3f6c41436b9e6494ec87
ms.sourcegitcommit: c88b54ba13a4dfe39b844ffaced4dc435560c47d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/19/2021
ms.locfileid: "5478092"
---
# <a name="enable-shop-similar-looks-recommendations"></a><span data-ttu-id="9462e-103">„Hasonló szettek vásárlása” javaslatok engedélyezése</span><span class="sxs-lookup"><span data-stu-id="9462e-103">Enable "shop similar looks" recommendations</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="9462e-104">Ez a témakör azt mutatja be, hogyan lehet engedélyezni a "hasonló megjelenésű" javaslatlistákat a Microsoft Dynamics 365 Commerce szolgáltatásnál.</span><span class="sxs-lookup"><span data-stu-id="9462e-104">This topic describes how to enable "shop similar looks" product recommendations in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="9462e-105">A "hasonló megvásárlása" javaslatlista funkció a Dynamics 365 Commerce által mesterséges intelligenciát és gépi tanulást (AI-ML) alkalmaz, hogy a vizuálisan hasonló termékeket a vevők számára ajánlani tudja.</span><span class="sxs-lookup"><span data-stu-id="9462e-105">The "shop similar looks" recommendations feature in Dynamics 365 Commerce uses the power of artificial intelligence and machine learning (AI-ML) to deliver recommendations for visually similar products to customers.</span></span> <span data-ttu-id="9462e-106">A "hasonló megvásárlása" javaslatok elérhetők a Commerce összes kiskereskedelmi csatornáján, ezzel a kiskereskedők növelhetik a vevők elégedettségét azzal, hogy könnyebben megtalálják azt, amit akarnak.</span><span class="sxs-lookup"><span data-stu-id="9462e-106">By making "shop similar looks" recommendations available for all retail channels in Commerce, retailers can increase customer satisfaction by helping customers easily find what they want.</span></span>

<span data-ttu-id="9462e-107">A "hasonló megvásárlása" javaslatlista funkció felhasználja a termékek képeit a megtekintett termékek változataiban ahhoz, hogy találatot adjon és javasoljon vizuálisan hasonló termékeket a kiskereskedők termékkatalógusaiból.</span><span class="sxs-lookup"><span data-stu-id="9462e-107">The functionality for "shop similar looks" recommendations uses product images of seed product variants to find and recommend visually similar products in a retailer's product catalog.</span></span> 

<span data-ttu-id="9462e-108">A "hasonló megvásárlása" javaslatlisták elérhetők mind a pénztárnál (POS), mind az e-Commerce tapasztalatainál.</span><span class="sxs-lookup"><span data-stu-id="9462e-108">"Shop similar looks" recommendations are available in both the point of sale (POS) and e-Commerce experiences.</span></span>

### <a name="example-scenarios"></a><span data-ttu-id="9462e-109">Példaforgatókönyvek</span><span class="sxs-lookup"><span data-stu-id="9462e-109">Example scenarios</span></span>

- <span data-ttu-id="9462e-110">Egy vevő egy fekete csíkos pulóvert tekint meg, egy hasonló pulóverre vonatkozó ajánlást kap piros színben.</span><span class="sxs-lookup"><span data-stu-id="9462e-110">A customer views a black striped sweater and receives a recommendation for a similar sweater in red.</span></span> <span data-ttu-id="9462e-111">A vevő kiválasztja a javasolt terméket az eredetileg megtekintett termék helyett és ezután kap javaslatot egy hasonló termékre piros színben.</span><span class="sxs-lookup"><span data-stu-id="9462e-111">The customer selects the recommended product instead of the originally viewed product and then receives recommendations for similar products in red.</span></span> 
- <span data-ttu-id="9462e-112">A vevő a "hasonló megvásárlása" javaslatlisták alapján talál olyan fülbevalókra, melyek összeillenek ahhoz a gyűrűhöz, amelyet a vevő megvenne.</span><span class="sxs-lookup"><span data-stu-id="9462e-112">A customer uses "shop similar looks" recommendations to discover matching earrings for a ring that the customer is interested in buying.</span></span>

## <a name="enable-shop-similar-looks-recommendations-in-commerce-headquarters"></a><span data-ttu-id="9462e-113">"Hasonló megvásárlása" javaslatlista engedélyezése a Commerce Headquarters alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="9462e-113">Enable "shop similar looks" recommendations in Commerce headquarters</span></span>

<span data-ttu-id="9462e-114">A termékjavaslatok funkció csak azoknak a Commerce-ügyfeleknek támogatott, akik a tárhelyüket az Azure Data Lake Gen2-re telepítették.</span><span class="sxs-lookup"><span data-stu-id="9462e-114">Product recommendations are supported only for Commerce users who have migrated their storage to Azure Data Lake Gen2.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="9462e-115">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="9462e-115">Prerequisites</span></span>

<span data-ttu-id="9462e-116">Mielőtt a kiskereskedők megkezdhetik a "hasonló megvásárlása" javaslatlisták megjelenítését a vevők számára, két előfeltételt kell teljesíteni:</span><span class="sxs-lookup"><span data-stu-id="9462e-116">Before retailers can begin to show "shop similar looks" recommendations to customers, there are two prerequisite steps:</span></span>

- <span data-ttu-id="9462e-117">[Termék ajánlásainak engedélyezése ](enable-product-recommendations.md)a Commerce Headquarters alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="9462e-117">[Enable product recommendations](enable-product-recommendations.md) in Commerce headquarters.</span></span>
- <span data-ttu-id="9462e-118">Győződjön meg róla, hogy a médiakiszolgáló támogatja a HTTPS-hívásokat.</span><span class="sxs-lookup"><span data-stu-id="9462e-118">Confirm that the media server supports HTTPS calls.</span></span>

<span data-ttu-id="9462e-119">Ahhoz hogy a javaslatlista keresőmotorja hozzáférhessen a termékek képeihez, a kiskereskedőknek generálniuk kell URL-címet a termékekhez.</span><span class="sxs-lookup"><span data-stu-id="9462e-119">For the recommendations engine to access the product images, retailers must generate the product URLs.</span></span> <span data-ttu-id="9462e-120">A termékek URL-címének generálásához kövesse az alábbi lépéseket a Commerce-központban.</span><span class="sxs-lookup"><span data-stu-id="9462e-120">To generate product URLs in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="9462e-121">Menjen a **Termék képek**-re.</span><span class="sxs-lookup"><span data-stu-id="9462e-121">Go to **Product images**.</span></span>
1. <span data-ttu-id="9462e-122">A műveleti ablaktáblán válassza ki a **Médiasablon meghatározása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9462e-122">On the Action Pane, select **Define media template**.</span></span>
1. <span data-ttu-id="9462e-123">A **Médiasablon meghatározása** tulajdonságai panelen, a **Média URL-cím** alatt válassza ki a **URL-cím generálása** elemet.</span><span class="sxs-lookup"><span data-stu-id="9462e-123">In the **Define media template** properties pane, under **Media URLs**, select **Generate URLs**.</span></span>

> [!NOTE]
> <span data-ttu-id="9462e-124">Ha engedélyezi a "hasonló megvásárlása" ajánlások funkcióját, akkor a javaslatlista létrehozási folyamata elkezdődik.</span><span class="sxs-lookup"><span data-stu-id="9462e-124">When you enable the "shop similar looks" recommendations feature, the process of generating product recommendation lists begins.</span></span> <span data-ttu-id="9462e-125">Legalább egy napot vesz igénybe, amíg a listák elérhetővé és láthatóvá válnak az online felületen és a POS terminálon.</span><span class="sxs-lookup"><span data-stu-id="9462e-125">Up to a day might be required before those lists are available and visible online and on POS terminals.</span></span>

<span data-ttu-id="9462e-126">Ha engedélyezni szeretné a Commerce Headquarters "hasonló megvásárlása" funkcióját, kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="9462e-126">To enable the "shop similar looks" recommendations feature in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="9462e-127">Lépjen a **Funkciókezelés** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="9462e-127">Go to **Feature management**.</span></span>
1. <span data-ttu-id="9462e-128">A rendelkezésre álló szolgáltatások listáján keresse meg és válassza ki a **hasonló megvásárlása** funkciót.</span><span class="sxs-lookup"><span data-stu-id="9462e-128">In the list of available features, search for and select **Shop similar looks**.</span></span>
1. <span data-ttu-id="9462e-129">A jobb oldali ablakban válassza az **Engedélyezés** lehetőséget a szolgáltatás bekapcsolásához.</span><span class="sxs-lookup"><span data-stu-id="9462e-129">In the right pane, select **Enable** to turn on the service.</span></span>

<span data-ttu-id="9462e-130">A következő ábra bemutatja a **hasonló megvásárlása** funkciót a **Funkciókezelés** oldalon a Commerce Headquarters lapján.</span><span class="sxs-lookup"><span data-stu-id="9462e-130">The following illustration shows the **Shop similar looks** feature on the **Feature management** page in Commerce headquarters.</span></span>

![A hasonló megvásárlása funkció a Funkciókezelés lapján a Commerce Headquarters oldalán](./media/enableshopsimilarlooks.png)

<span data-ttu-id="9462e-132">Az előző feladatok befejezése után a POS-terminálokat a program automatikusan kibővíti egy  **hasonló termékek**-et tartalmazó panellel.</span><span class="sxs-lookup"><span data-stu-id="9462e-132">After the preceding tasks been completed, POS terminals are automatically enhanced with a contextual **Shop similar products** panel.</span></span> <span data-ttu-id="9462e-133">Ha rámegy a **Bővebben** lehetőségre, a POS terminál felhasználóit egy "hasonló megvásárlása" oldalra irányítja, amely tovább szűrhető.</span><span class="sxs-lookup"><span data-stu-id="9462e-133">By selecting **See more**, POS terminal users can be taken to a dedicated "shop similar looks" page that can be filtered further.</span></span>

> [!NOTE]
> <span data-ttu-id="9462e-134">Ha kikapcsolja a "hasonló megvásárlása" javaslatok funkcióját, nem lesz egyik termék se hatással az ajánlatokra.</span><span class="sxs-lookup"><span data-stu-id="9462e-134">If you turn off the "shop similar looks" recommendations feature, no other types of product recommendations are affected.</span></span> <span data-ttu-id="9462e-135">A termékajánlásokkal kapcsolatos további tudnivalókat lásd: [Termékajánlások áttekintése](product-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="9462e-135">For more information about product recommendations, see [Product recommendations overview](product-recommendations.md).</span></span>

## <a name="add-a-shop-similar-looks-button-to-product-details-pages-by-using-commerce-site-builder"></a><span data-ttu-id="9462e-136">Adja hozzá a hasonló megvásárlása gombot a termék adatlapjához a Commerce Site Builder segítségével</span><span class="sxs-lookup"><span data-stu-id="9462e-136">Add a Shop similar looks button to product details pages by using Commerce site builder</span></span>

<span data-ttu-id="9462e-137">Miután engedélyezte a "hasonló megvásárlása" javaslatok funkcióját a Commerce Headquarters rendszerben, a Commerce webhelykészítő lehetővé teszi a kiskereskedők számára, hogy hozzáadjon **hasonló megvásárlása** gombot a vásárlásmezőhöz bármely termék adatlapján (PDP).</span><span class="sxs-lookup"><span data-stu-id="9462e-137">After you enable the "shop similar looks" recommendations feature in Commerce headquarters, an option in Commerce site builder lets retailers to add a **Shop similar looks** button to the buy box on any product details page (PDP).</span></span> <span data-ttu-id="9462e-138">A gombot kiválasztó vevő egy "hasonló megvásárlása" oldalra kerül, ahol vizuálisan hasonló termékek jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="9462e-138">A customer who selects this button is taken to a dedicated "shop similar looks" page that returns visually similar products.</span></span> <span data-ttu-id="9462e-139">Ott a vevő használhatja a választókat a termékek szűrésére.</span><span class="sxs-lookup"><span data-stu-id="9462e-139">There, the customer can use selectors to further filter the products.</span></span>

<span data-ttu-id="9462e-140">Ahhoz, hogy a **Hasonló megvásárlása** gombot hozzáadja a PDP-hez a Commerce webhelykészítő segítségével, kövesse ezeket a lépéseket.</span><span class="sxs-lookup"><span data-stu-id="9462e-140">To add a **Shop similar looks** button to a PDP by using Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="9462e-141">Nyisson meg egy már meglévő webhelykészítő lapot, ami vásárlásmező modult tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="9462e-141">Open an existing site builder page that contains a buy box module.</span></span>
1. <span data-ttu-id="9462e-142">A bal oldali navigációs ablakban válassza ki a vásárlásmező modult.</span><span class="sxs-lookup"><span data-stu-id="9462e-142">In the left navigation pane, select the buy box module.</span></span>
1. <span data-ttu-id="9462e-143">A jobb oldali navigációs ablakban jelölje be a **Hasonló megvásárlása link engedélyezése** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="9462e-143">In the right navigation pane, select the **Enable Shop Similar Looks Link** check box.</span></span>
1. <span data-ttu-id="9462e-144">Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot az oldal ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.</span><span class="sxs-lookup"><span data-stu-id="9462e-144">Select **Save**, select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span> <span data-ttu-id="9462e-145">A lap közzététele után a PDP tartalmazni fogja a **hasonló megvásárlása** gombot.</span><span class="sxs-lookup"><span data-stu-id="9462e-145">After the page is published, the PDP will include a **Shop similar looks** button.</span></span>

<span data-ttu-id="9462e-146">A következő ábra bemutatja a **Hasonló megvásárlása link engedélyezése** jelölőnégyzetet, és a **hasonló megvásárlása** gombot egy PDP-oldalon a webhelykészítőben.</span><span class="sxs-lookup"><span data-stu-id="9462e-146">The following illustration shows the **Enable Shop Similar Looks Link** check box and **Shop similar looks** button on an example PDP in site builder.</span></span>

![A Hasonló megvásárlása link engedélyezése jelölőnégyzeten és hasonló megvásárlása gomb egy PDP-oldalon a webhelykészítőben](./media/SSLecomtooling.png)

## <a name="additional-resources"></a><span data-ttu-id="9462e-148">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="9462e-148">Additional resources</span></span>

[<span data-ttu-id="9462e-149">Termékajánlatok áttekintése</span><span class="sxs-lookup"><span data-stu-id="9462e-149">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="9462e-150">Az Azure Data Lake Storage engedélyezése a Dynamics 365 Commerce környezetben</span><span class="sxs-lookup"><span data-stu-id="9462e-150">Enable Azure Data Lake Storage in a Dynamics 365 Commerce environment</span></span>](enable-adls-environment.md)

[<span data-ttu-id="9462e-151">Termékajánlatok engedélyezése</span><span class="sxs-lookup"><span data-stu-id="9462e-151">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="9462e-152">Személyre szabott termékajánlatok kikapcsolása</span><span class="sxs-lookup"><span data-stu-id="9462e-152">Opt out of personalized recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="9462e-153">Termékajánlások hozzáadása a pénztárnál</span><span class="sxs-lookup"><span data-stu-id="9462e-153">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="9462e-154">Ajánlatok hozzáadása a tranzakciós képernyőhöz</span><span class="sxs-lookup"><span data-stu-id="9462e-154">Add recommendations to the transaction screen</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="9462e-155">AI-ML ajánlások eredményeinek helyesbítése</span><span class="sxs-lookup"><span data-stu-id="9462e-155">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="9462e-156">Válogatott ajánlások manuális létrehozása</span><span class="sxs-lookup"><span data-stu-id="9462e-156">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="9462e-157">Ajánlások létrehozása bemutató adatokkal</span><span class="sxs-lookup"><span data-stu-id="9462e-157">Create recommendations with demo data</span></span>](product-recommendations-demo-data.md)

[<span data-ttu-id="9462e-158">Termékajánlatok GYIK-je</span><span class="sxs-lookup"><span data-stu-id="9462e-158">Product recommendations FAQ</span></span>](faq-recommendations.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
