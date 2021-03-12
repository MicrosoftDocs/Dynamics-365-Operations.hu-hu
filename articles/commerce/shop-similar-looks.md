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
ms.openlocfilehash: 95e4246d6c5f9ac5bc86b626be0d971f756c5130
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4985611"
---
# <a name="enable-shop-similar-looks-recommendations"></a><span data-ttu-id="234cb-103">Engedélyezze a "hasonló megvásárlása" javaslatlistákat</span><span class="sxs-lookup"><span data-stu-id="234cb-103">Enable "shop similar looks" recommendations</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="234cb-104">Ez a témakör azt mutatja be, hogyan lehet engedélyezni a "hasonló megjelenésű" javaslatlistákat a Microsoft Dynamics 365 Commerce szolgáltatásnál.</span><span class="sxs-lookup"><span data-stu-id="234cb-104">This topic describes how to enable "shop similar looks" product recommendations in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="234cb-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="234cb-105">Overview</span></span>

<span data-ttu-id="234cb-106">A "hasonló megvásárlása" javaslatlista funkció a Dynamics 365 Commerce által mesterséges intelligenciát és gépi tanulást (AI-ML) alkalmaz, hogy a vizuálisan hasonló termékeket a vevők számára ajánlani tudja.</span><span class="sxs-lookup"><span data-stu-id="234cb-106">The "shop similar looks" recommendations feature in Dynamics 365 Commerce uses the power of artificial intelligence and machine learning (AI-ML) to deliver recommendations for visually similar products to customers.</span></span> <span data-ttu-id="234cb-107">A "hasonló megvásárlása" javaslatok elérhetők a Commerce összes kiskereskedelmi csatornáján, ezzel a kiskereskedők növelhetik a vevők elégedettségét azzal, hogy könnyebben megtalálják azt, amit akarnak.</span><span class="sxs-lookup"><span data-stu-id="234cb-107">By making "shop similar looks" recommendations available for all retail channels in Commerce, retailers can increase customer satisfaction by helping customers easily find what they want.</span></span>

<span data-ttu-id="234cb-108">A "hasonló megvásárlása" javaslatlista funkció felhasználja a termékek képeit a megtekintett termékek változataiban ahhoz, hogy találatot adjon és javasoljon vizuálisan hasonló termékeket a kiskereskedők termékkatalógusaiból.</span><span class="sxs-lookup"><span data-stu-id="234cb-108">The functionality for "shop similar looks" recommendations uses product images of seed product variants to find and recommend visually similar products in a retailer's product catalog.</span></span> 

<span data-ttu-id="234cb-109">A "hasonló megvásárlása" javaslatlisták elérhetők mind a pénztárnál (POS), mind az e-Commerce tapasztalatainál.</span><span class="sxs-lookup"><span data-stu-id="234cb-109">"Shop similar looks" recommendations are available in both the point of sale (POS) and e-Commerce experiences.</span></span>

### <a name="example-scenarios"></a><span data-ttu-id="234cb-110">Példaforgatókönyvek</span><span class="sxs-lookup"><span data-stu-id="234cb-110">Example scenarios</span></span>

- <span data-ttu-id="234cb-111">Egy vevő egy fekete csíkos pulóvert tekint meg, egy hasonló pulóverre vonatkozó ajánlást kap piros színben.</span><span class="sxs-lookup"><span data-stu-id="234cb-111">A customer views a black striped sweater and receives a recommendation for a similar sweater in red.</span></span> <span data-ttu-id="234cb-112">A vevő kiválasztja a javasolt terméket az eredetileg megtekintett termék helyett és ezután kap javaslatot egy hasonló termékre piros színben.</span><span class="sxs-lookup"><span data-stu-id="234cb-112">The customer selects the recommended product instead of the originally viewed product and then receives recommendations for similar products in red.</span></span> 
- <span data-ttu-id="234cb-113">A vevő a "hasonló megvásárlása" javaslatlisták alapján talál olyan fülbevalókra, melyek összeillenek ahhoz a gyűrűhöz, amelyet a vevő megvenne.</span><span class="sxs-lookup"><span data-stu-id="234cb-113">A customer uses "shop similar looks" recommendations to discover matching earrings for a ring that the customer is interested in buying.</span></span>

## <a name="enable-shop-similar-looks-recommendations-in-commerce-headquarters"></a><span data-ttu-id="234cb-114">"Hasonló megvásárlása" javaslatlista engedélyezése a Commerce Headquarters alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="234cb-114">Enable "shop similar looks" recommendations in Commerce headquarters</span></span>

<span data-ttu-id="234cb-115">A termékjavaslatok funkció csak azoknak a Commerce-ügyfeleknek támogatott, akik a tárhelyüket az Azure Data Lake Gen2-re telepítették.</span><span class="sxs-lookup"><span data-stu-id="234cb-115">Product recommendations are supported only for Commerce users who have migrated their storage to Azure Data Lake Gen2.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="234cb-116">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="234cb-116">Prerequisites</span></span>

<span data-ttu-id="234cb-117">Mielőtt a kiskereskedők megkezdhetik a "hasonló megvásárlása" javaslatlisták megjelenítését a vevők számára, két előfeltételt kell teljesíteni:</span><span class="sxs-lookup"><span data-stu-id="234cb-117">Before retailers can begin to show "shop similar looks" recommendations to customers, there are two prerequisite steps:</span></span>

- <span data-ttu-id="234cb-118">[Termék ajánlásainak engedélyezése ](enable-product-recommendations.md)a Commerce Headquarters alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="234cb-118">[Enable product recommendations](enable-product-recommendations.md) in Commerce headquarters.</span></span>
- <span data-ttu-id="234cb-119">Győződjön meg róla, hogy a médiakiszolgáló támogatja a HTTPS-hívásokat.</span><span class="sxs-lookup"><span data-stu-id="234cb-119">Confirm that the media server supports HTTPS calls.</span></span>

<span data-ttu-id="234cb-120">Ahhoz hogy a javaslatlista keresőmotorja hozzáférhessen a termékek képeihez, a kiskereskedőknek generálniuk kell URL-címet a termékekhez.</span><span class="sxs-lookup"><span data-stu-id="234cb-120">For the recommendations engine to access the product images, retailers must generate the product URLs.</span></span> <span data-ttu-id="234cb-121">A termékek URL-címének generálásához kövesse az alábbi lépéseket a Commerce-központban.</span><span class="sxs-lookup"><span data-stu-id="234cb-121">To generate product URLs in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="234cb-122">Menjen a **Termék képek**-re.</span><span class="sxs-lookup"><span data-stu-id="234cb-122">Go to **Product images**.</span></span>
1. <span data-ttu-id="234cb-123">A műveleti ablaktáblán válassza ki a **Médiasablon meghatározása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="234cb-123">On the Action Pane, select **Define media template**.</span></span>
1. <span data-ttu-id="234cb-124">A **Médiasablon meghatározása** tulajdonságai panelen, a **Média URL-cím** alatt válassza ki a **URL-cím generálása** elemet.</span><span class="sxs-lookup"><span data-stu-id="234cb-124">In the **Define media template** properties pane, under **Media URLs**, select **Generate URLs**.</span></span>

> [!NOTE]
> <span data-ttu-id="234cb-125">Ha engedélyezi a "hasonló megvásárlása" ajánlások funkcióját, akkor a javaslatlista létrehozási folyamata elkezdődik.</span><span class="sxs-lookup"><span data-stu-id="234cb-125">When you enable the "shop similar looks" recommendations feature, the process of generating product recommendation lists begins.</span></span> <span data-ttu-id="234cb-126">Legalább egy napot vesz igénybe, amíg a listák elérhetővé és láthatóvá válnak az online felületen és a POS terminálon.</span><span class="sxs-lookup"><span data-stu-id="234cb-126">Up to a day might be required before those lists are available and visible online and on POS terminals.</span></span>

<span data-ttu-id="234cb-127">Ha engedélyezni szeretné a Commerce Headquarters "hasonló megvásárlása" funkcióját, kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="234cb-127">To enable the "shop similar looks" recommendations feature in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="234cb-128">Lépjen a **Funkciókezelés** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="234cb-128">Go to **Feature management**.</span></span>
1. <span data-ttu-id="234cb-129">A rendelkezésre álló szolgáltatások listáján keresse meg és válassza ki a **hasonló megvásárlása** funkciót.</span><span class="sxs-lookup"><span data-stu-id="234cb-129">In the list of available features, search for and select **Shop similar looks**.</span></span>
1. <span data-ttu-id="234cb-130">A jobb oldali ablakban válassza az **Engedélyezés** lehetőséget a szolgáltatás bekapcsolásához.</span><span class="sxs-lookup"><span data-stu-id="234cb-130">In the right pane, select **Enable** to turn on the service.</span></span>

<span data-ttu-id="234cb-131">A következő ábra bemutatja a **hasonló megvásárlása** funkciót a **Funkciókezelés** oldalon a Commerce Headquarters lapján.</span><span class="sxs-lookup"><span data-stu-id="234cb-131">The following illustration shows the **Shop similar looks** feature on the **Feature management** page in Commerce headquarters.</span></span>

![A hasonló megvásárlása funkció a Funkciókezelés lapján a Commerce Headquarters oldalán](./media/enableshopsimilarlooks.png)

<span data-ttu-id="234cb-133">Az előző feladatok befejezése után a POS-terminálokat a program automatikusan kibővíti egy  **hasonló termékek**-et tartalmazó panellel.</span><span class="sxs-lookup"><span data-stu-id="234cb-133">After the preceding tasks been completed, POS terminals are automatically enhanced with a contextual **Shop similar products** panel.</span></span> <span data-ttu-id="234cb-134">Ha rámegy a **Bővebben** lehetőségre, a POS terminál felhasználóit egy "hasonló megvásárlása" oldalra irányítja, amely tovább szűrhető.</span><span class="sxs-lookup"><span data-stu-id="234cb-134">By selecting **See more**, POS terminal users can be taken to a dedicated "shop similar looks" page that can be filtered further.</span></span>

> [!NOTE]
> <span data-ttu-id="234cb-135">Ha kikapcsolja a "hasonló megvásárlása" javaslatok funkcióját, nem lesz egyik termék se hatással az ajánlatokra.</span><span class="sxs-lookup"><span data-stu-id="234cb-135">If you turn off the "shop similar looks" recommendations feature, no other types of product recommendations are affected.</span></span> <span data-ttu-id="234cb-136">A termékajánlásokkal kapcsolatos további tudnivalókat lásd: [Termékajánlások áttekintése](product-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="234cb-136">For more information about product recommendations, see [Product recommendations overview](product-recommendations.md).</span></span>

## <a name="add-a-shop-similar-looks-button-to-product-details-pages-by-using-commerce-site-builder"></a><span data-ttu-id="234cb-137">Adja hozzá a hasonló megvásárlása gombot a termék adatlapjához a Commerce Site Builder segítségével</span><span class="sxs-lookup"><span data-stu-id="234cb-137">Add a Shop similar looks button to product details pages by using Commerce site builder</span></span>

<span data-ttu-id="234cb-138">Miután engedélyezte a "hasonló megvásárlása" javaslatok funkcióját a Commerce Headquarters rendszerben, a Commerce webhelykészítő lehetővé teszi a kiskereskedők számára, hogy hozzáadjon **hasonló megvásárlása** gombot a vásárlásmezőhöz bármely termék adatlapján (PDP).</span><span class="sxs-lookup"><span data-stu-id="234cb-138">After you enable the "shop similar looks" recommendations feature in Commerce headquarters, an option in Commerce site builder lets retailers to add a **Shop similar looks** button to the buy box on any product details page (PDP).</span></span> <span data-ttu-id="234cb-139">A gombot kiválasztó vevő egy "hasonló megvásárlása" oldalra kerül, ahol vizuálisan hasonló termékek jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="234cb-139">A customer who selects this button is taken to a dedicated "shop similar looks" page that returns visually similar products.</span></span> <span data-ttu-id="234cb-140">Ott a vevő használhatja a választókat a termékek szűrésére.</span><span class="sxs-lookup"><span data-stu-id="234cb-140">There, the customer can use selectors to further filter the products.</span></span>

<span data-ttu-id="234cb-141">Ahhoz, hogy a **Hasonló megvásárlása** gombot hozzáadja a PDP-hez a Commerce webhelykészítő segítségével, kövesse ezeket a lépéseket.</span><span class="sxs-lookup"><span data-stu-id="234cb-141">To add a **Shop similar looks** button to a PDP by using Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="234cb-142">Nyisson meg egy már meglévő webhelykészítő lapot, ami vásárlásmező modult tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="234cb-142">Open an existing site builder page that contains a buy box module.</span></span>
1. <span data-ttu-id="234cb-143">A bal oldali navigációs ablakban válassza ki a vásárlásmező modult.</span><span class="sxs-lookup"><span data-stu-id="234cb-143">In the left navigation pane, select the buy box module.</span></span>
1. <span data-ttu-id="234cb-144">A jobb oldali navigációs ablakban jelölje be a **Hasonló megvásárlása link engedélyezése** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="234cb-144">In the right navigation pane, select the **Enable Shop Similar Looks Link** check box.</span></span>
1. <span data-ttu-id="234cb-145">Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot az oldal ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.</span><span class="sxs-lookup"><span data-stu-id="234cb-145">Select **Save**, select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span> <span data-ttu-id="234cb-146">A lap közzététele után a PDP tartalmazni fogja a **hasonló megvásárlása** gombot.</span><span class="sxs-lookup"><span data-stu-id="234cb-146">After the page is published, the PDP will include a **Shop similar looks** button.</span></span>

<span data-ttu-id="234cb-147">A következő ábra bemutatja a **Hasonló megvásárlása link engedélyezése** jelölőnégyzetet, és a **hasonló megvásárlása** gombot egy PDP-oldalon a webhelykészítőben.</span><span class="sxs-lookup"><span data-stu-id="234cb-147">The following illustration shows the **Enable Shop Similar Looks Link** check box and **Shop similar looks** button on an example PDP in site builder.</span></span>

![A Hasonló megvásárlása link engedélyezése jelölőnégyzeten és hasonló megvásárlása gomb egy PDP-oldalon a webhelykészítőben](./media/SSLecomtooling.png)

## <a name="additional-resources"></a><span data-ttu-id="234cb-149">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="234cb-149">Additional resources</span></span>

[<span data-ttu-id="234cb-150">Termékajánlatok áttekintése</span><span class="sxs-lookup"><span data-stu-id="234cb-150">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="234cb-151">Az Azure Data Lake Storage engedélyezése a Dynamics 365 Commerce környezetben</span><span class="sxs-lookup"><span data-stu-id="234cb-151">Enable Azure Data Lake Storage in a Dynamics 365 Commerce environment</span></span>](enable-adls-environment.md)

[<span data-ttu-id="234cb-152">Termékajánlatok engedélyezése</span><span class="sxs-lookup"><span data-stu-id="234cb-152">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="234cb-153">Személyre szabott termékajánlatok kikapcsolása</span><span class="sxs-lookup"><span data-stu-id="234cb-153">Opt out of personalized recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="234cb-154">Termékajánlások hozzáadása a pénztárnál</span><span class="sxs-lookup"><span data-stu-id="234cb-154">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="234cb-155">Ajánlatok hozzáadása a tranzakciós képernyőhöz</span><span class="sxs-lookup"><span data-stu-id="234cb-155">Add recommendations to the transaction screen</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="234cb-156">AI-ML ajánlások eredményeinek helyesbítése</span><span class="sxs-lookup"><span data-stu-id="234cb-156">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="234cb-157">Válogatott ajánlások manuális létrehozása</span><span class="sxs-lookup"><span data-stu-id="234cb-157">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="234cb-158">Ajánlások létrehozása bemutató adatokkal</span><span class="sxs-lookup"><span data-stu-id="234cb-158">Create recommendations with demo data</span></span>](product-recommendations-demo-data.md)

[<span data-ttu-id="234cb-159">Termékajánlatok GYIK-je</span><span class="sxs-lookup"><span data-stu-id="234cb-159">Product recommendations FAQ</span></span>](faq-recommendations.md)
