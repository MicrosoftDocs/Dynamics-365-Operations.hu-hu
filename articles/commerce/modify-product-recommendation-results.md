---
title: AI-ML-alapú termékajánlás eredményeinek kiigazítása
description: Ez a témakör azt mutatja be, hogyan lehet testreszabni a termékjavaslatok eredményeit a mesterséges intelligencia gépi tanulás (AI-ML) alapján a vállalkozása számára.
author: bebeale
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
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: bc6a793061a3e644599f0882ff163f5f57b2162d
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4412947"
---
# <a name="adjust-ai-ml-based-product-recommendation-results"></a><span data-ttu-id="74d17-103">AI-ML-alapú termékajánlás eredményeinek kiigazítása</span><span class="sxs-lookup"><span data-stu-id="74d17-103">Adjust AI-ML-based product recommendation results</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="74d17-104">Ez a témakör azt mutatja be, hogyan lehet kiigazítani a termékjavaslatok eredményeit a mesterséges intelligencia gépi tanulás (AI-ML) alapján a vállalkozása számára.</span><span class="sxs-lookup"><span data-stu-id="74d17-104">This topic explains how to adjust product recommendation results based on artificial intelligence-machine learning (AI-ML) to your business.</span></span> 

<span data-ttu-id="74d17-105">A termékjavaslatok engedélyezése után az alapértelmezett beállítások lépnek érvénybe ezek a paraméterek számos szükséglethez használhatók lehetnek.</span><span class="sxs-lookup"><span data-stu-id="74d17-105">After enabling product recommendations, the default settings will take effect; these parameters will work for may work for many needs.</span></span> <span data-ttu-id="74d17-106">A legjobb az, ha hagynak egy kis időt arra, hogy az eredmények megfelelnek-e a termékek értékesítési irányának.</span><span class="sxs-lookup"><span data-stu-id="74d17-106">It is best to plan to spend some time evaluating whether the results fit the selling motion of products.</span></span> <span data-ttu-id="74d17-107">Javasoljuk, hogy néhány napig értékelje ki az eredményeket, mielőtt igény szerint módosítaná a paramétereket az újratesztelés előtt.</span><span class="sxs-lookup"><span data-stu-id="74d17-107">We suggest evaluating results for a few days before changing parameters as needed before testing again.</span></span> 

## <a name="understanding-recommendation-list-parameters"></a><span data-ttu-id="74d17-108">Az ajánlási lista paramétereinek ismertetése</span><span class="sxs-lookup"><span data-stu-id="74d17-108">Understanding recommendation list parameters</span></span>

<span data-ttu-id="74d17-109">A paraméterek módosítása előtt az alábbi részből megismerheti, hogy milyen hatással lesznek az eredményekre.</span><span class="sxs-lookup"><span data-stu-id="74d17-109">Before changing the parameters, learn about how they will affect the results below.</span></span>

### <a name="trending-product-list"></a><span data-ttu-id="74d17-110">"Népszerű" terméklista</span><span class="sxs-lookup"><span data-stu-id="74d17-110">"Trending" product list</span></span>

<span data-ttu-id="74d17-111">A "Népszerű" terméklista két módosítható paraméterrel rendelkezik:</span><span class="sxs-lookup"><span data-stu-id="74d17-111">The "Trending" product list has two parameters that can be changed:</span></span>

![Példa a "Népszerű" lista alapértelmezett paramétereire](./media/exampletrendingparameters.png)

1. <span data-ttu-id="74d17-113">**Új termékek belefoglalása a legutóbbi X napból** – Azok a termékek, amelyek az aktuális dátumtól számított megadott számú napon belül lettek hozzáadva használhatók termékjelöltek kiválasztásához.</span><span class="sxs-lookup"><span data-stu-id="74d17-113">**Include new products from last X days** - Products that have been added within the specified number of days before the current date can be used to select product candidates.</span></span> <span data-ttu-id="74d17-114">A kép alapértelmezett értéke azt sugallja, hogy maximum 180 napos termékek használhatók fel a népszerű termékek listájában.</span><span class="sxs-lookup"><span data-stu-id="74d17-114">The default value in the picture suggests that products as old has 180 days can be used in the trending product list.</span></span>
1. <span data-ttu-id="74d17-115">**Értékesítések belefoglalása a legutóbbi X napból** – Azok az értékesítési tranzakciók, amelyek az aktuális dátumtól számított megadott számú napon belül történtek használhatók a termékek rendezéséhez.</span><span class="sxs-lookup"><span data-stu-id="74d17-115">**Include sales from last X days** - Sales transactions that have occurred within the specified number of days before the current date can be used to order the products.</span></span> <span data-ttu-id="74d17-116">A fenti alapértelmezett érték azt sugallja, hogy az elmúlt 30 napban a termékhez tartozó összes vásárlás lenne felhasználva a termék helyének meghatározásához a népszerű termékek listáján.</span><span class="sxs-lookup"><span data-stu-id="74d17-116">The default value above suggests that all purchases made of a product in the last 30 days would be used to determine the placement of the product in the trending product list.</span></span> 

### <a name="best-selling-product-list"></a><span data-ttu-id="74d17-117">"Legkelendőbb" termékek listája</span><span class="sxs-lookup"><span data-stu-id="74d17-117">"Best selling" product list</span></span>

<span data-ttu-id="74d17-118">A vállalattól függően a "Legkelendőbb" lista eltérő eredményt adhat, mint a népszerű, annak ellenére, hogy mindkettő tranzakcióadatokat használ a termékek rendezéséhez.</span><span class="sxs-lookup"><span data-stu-id="74d17-118">Depending on your business, the "Best selling" list can bring different results than trending, even though they both use transaction data to order products.</span></span> <span data-ttu-id="74d17-119">Mivel a legjobban fogyó termékek esetében nincs határ a szortiment dátuma alapján, a legjobban fogyó termékek listáján megjelenhetnek olyan nagyon népszerű, régebbi termékek , amelyek már lekerültek a népszerű termékek listájáról.</span><span class="sxs-lookup"><span data-stu-id="74d17-119">Because best selling has no cut off based on assortment date, Best selling can still highlight very popular, older products that might have been dropped from the trending list.</span></span> 

<span data-ttu-id="74d17-120">A "Legkelendőbb" terméklista egyetlen módosítható paraméterrel rendelkezik:</span><span class="sxs-lookup"><span data-stu-id="74d17-120">The "Best selling" product list has one parameter that can be changed:</span></span>

![Példa a Legkelendőbb lista alapértelmezett paraméterére](./media/examplebestsellingparameters.PNG)

1. <span data-ttu-id="74d17-122">**Értékesítések belefoglalása a legutóbbi X napból** – Azok az értékesítési tranzakciók, amelyek az aktuális dátumtól számított megadott számú napon belül történtek használhatók a termékek rendezéséhez.</span><span class="sxs-lookup"><span data-stu-id="74d17-122">**Include sales from last X days** - Sales transactions that have occurred within the specified number of days before the current date can be used to order the products.</span></span> <span data-ttu-id="74d17-123">A fenti alapértelmezett érték azt sugallja, hogy az elmúlt 30 napban a termékhez tartozó összes vásárlás lenne felhasználva a termék helyének meghatározásához a Legkelendőbb termékek listáján.</span><span class="sxs-lookup"><span data-stu-id="74d17-123">The default value above suggests that all purchases made of a product in the last 30 days would be used to determine the placement of the product in the Best selling product list.</span></span> 

## <a name="manually-add-or-remove-products-from-recommendation-lists"></a><span data-ttu-id="74d17-124">Termékek manuális hozzáadása vagy eltávolítása az ajánlási listákból</span><span class="sxs-lookup"><span data-stu-id="74d17-124">Manually add or remove products from recommendation lists</span></span>

### <a name="for-new-trending-or-best-selling-lists"></a><span data-ttu-id="74d17-125">Az "Új", "Népszerű" vagy "Legkelendőbb" listák esetében</span><span class="sxs-lookup"><span data-stu-id="74d17-125">For "New," "Trending," or "Best selling" lists</span></span>

1.  <span data-ttu-id="74d17-126">Válassza a **Retail és Commerce** > **Termékajánlatok** > **Ajánlási paraméterek** elemet.</span><span class="sxs-lookup"><span data-stu-id="74d17-126">Go to **Retail and Commerce** > **Product recommendations** > **Recommendation parameters**.</span></span>
1.  <span data-ttu-id="74d17-127">A megosztott paraméterek listáján válassza az **Ajánlati listák** elemet.</span><span class="sxs-lookup"><span data-stu-id="74d17-127">In the list of shared parameters, select **Recommendation lists**.</span></span>
1.  <span data-ttu-id="74d17-128">Jelölje ki a listát a termékek hozzáadásához vagy eltávolításához.</span><span class="sxs-lookup"><span data-stu-id="74d17-128">Select the list add or remove products from.</span></span>
1.  <span data-ttu-id="74d17-129">Ha termékeket szeretne hozzáadni a táblázathoz, válassza a **Sor hozzáadása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="74d17-129">To add products to the table, select **Add line.**</span></span> 
1.  <span data-ttu-id="74d17-130">A Termék oszlopban keressen egy terméket **Név** vagy **Termékszám** alapján.</span><span class="sxs-lookup"><span data-stu-id="74d17-130">Under the Product column, search for a product by **Name** or **Product number.**</span></span>

    ![Példa a termék keresésére az Új terméklistán](./media/examplenewlistconfiguration1.png)

1.  <span data-ttu-id="74d17-132">A Sor típusa oszlopban válassza ki a két beállítás egyikét:</span><span class="sxs-lookup"><span data-stu-id="74d17-132">Under the Line type column, select one of two options:</span></span>
    -   <span data-ttu-id="74d17-133">**Belefoglalás** – egy terméket a lista elejére kényszerít</span><span class="sxs-lookup"><span data-stu-id="74d17-133">**Include** – forces a product to the front of the list</span></span>
    -   <span data-ttu-id="74d17-134">**Kizárás** – eltávolít egy terméket a listából.</span><span class="sxs-lookup"><span data-stu-id="74d17-134">**Exclude** – removes a product from appearing in the list</span></span>
    
    ![Példa a termékeknek az Új terméklistára való felvételére vagy Új terméklistáról való kihagyására](./media/examplenewlistconfiguration2.png)

1.  <span data-ttu-id="74d17-136">A **Megjelenítési sorrend** módosítása megváltoztatja azt, hogy a **belefoglalásra** megjelölt termékek milyen sorendben jelenjenek meg a listában.</span><span class="sxs-lookup"><span data-stu-id="74d17-136">Changing the **Display order** will change the order that products marked **include** will appear in the list.</span></span>
    - <span data-ttu-id="74d17-137">Ha két terméknél ugyanaz **megjelenítési sorrend** értéke, akkor a két eredmény végső sorrendje eltérhet a háttéroldaltól.</span><span class="sxs-lookup"><span data-stu-id="74d17-137">If two products have the same **display order** value, then the final order of those two results may differ from the back office.</span></span>
1.  <span data-ttu-id="74d17-138">Termékek eltávolításához a táblázatból: válassza ki a törölni kívánt sort, és válassza az **Eltávolítás** elemet.</span><span class="sxs-lookup"><span data-stu-id="74d17-138">To remove products from the table: select the line to remove and select **Remove**.</span></span>


### <a name="for-people-also-like-or-frequently-bought-together-lists"></a><span data-ttu-id="74d17-139">A "Másoknak ez is tetszett" vagy "Gyakran együtt vásárolt" listák esetében</span><span class="sxs-lookup"><span data-stu-id="74d17-139">For "People also like" or "Frequently bought together" lists</span></span>

<span data-ttu-id="74d17-140">A "Gyakran együtt vásárolt", illetve a "Másoknak ez is tetszett" listák esetében gépi tanulást alkalmazunk a fogyasztók vásárlási mintáinak elemzéséhez, illetve kapcsolódó termékek ajánlásához, amelyeket gyakran megvásároltak együtt egy megtekintett termékkel.</span><span class="sxs-lookup"><span data-stu-id="74d17-140">In the context of "Frequently bought together" or "People also like" lists, machine learning is used to analyze consumer purchase patterns to recommend related products commonly purchased together for a unique seed product.</span></span> 
 
<span data-ttu-id="74d17-141">A *megtekintett termék* az a termék, amelyhez az eredményeket generálni szeretné.</span><span class="sxs-lookup"><span data-stu-id="74d17-141">A *seed product* is the product you want to generate results for.</span></span> <span data-ttu-id="74d17-142">Az ajánlási listák manuális módosításával összefüggésben ehhez a termékhez adja hozzá vagy távolítja el az eredményeket.</span><span class="sxs-lookup"><span data-stu-id="74d17-142">In the context of manually adjusting recommendation lists, you are adding or removing results for this product.</span></span> 

<span data-ttu-id="74d17-143">A következő lépések végrehajtásával manuálisan adhat hozzá vagy távolíthat el eredményeket egy alaptermékhez:</span><span class="sxs-lookup"><span data-stu-id="74d17-143">Follow these steps to manually add or remove results for a seed product:</span></span>
1.  <span data-ttu-id="74d17-144">Válassza ki a **Kiinduló terméket**.</span><span class="sxs-lookup"><span data-stu-id="74d17-144">Select the **Seed product**.</span></span> 
1.  <span data-ttu-id="74d17-145">A **Termék** oszlopban keressen egy terméket **Név** vagy **Cikkszám alapján.**
![Példa a termék keresésére a Gyakran együtt vásárolt listában](./media/exampleFBTlistconfiguration1.png)</span><span class="sxs-lookup"><span data-stu-id="74d17-145">Under the **Product** column, search for a product by **Name** or **Product number.**
![Example of searching for a product on the Frequently bought together list](./media/exampleFBTlistconfiguration1.png)</span></span>
1. <span data-ttu-id="74d17-146">A **Sor típusa** oszlopban válassza ki a két beállítás egyikét:</span><span class="sxs-lookup"><span data-stu-id="74d17-146">Under the **Line type** column, select one of two options:</span></span>
    - <span data-ttu-id="74d17-147">**Belefoglalás** – egy terméket a lista elejére kényszerít</span><span class="sxs-lookup"><span data-stu-id="74d17-147">**Include** – forces a product to the front of the list</span></span>
    - <span data-ttu-id="74d17-148">**Kizárás** – eltávolít egy terméket a listából.</span><span class="sxs-lookup"><span data-stu-id="74d17-148">**Exclude** – removes a product from appearing in the list</span></span>     
<span data-ttu-id="74d17-149">![Példa egy termék belefoglalására vagy kizárására a Gyakran együtt vásárolt listában](./media/exampleFBTlistconfiguration2.png)</span><span class="sxs-lookup"><span data-stu-id="74d17-149">![Example of Including or Excluding a product on the Frequently bought together list](./media/exampleFBTlistconfiguration2.png)</span></span>
1.  <span data-ttu-id="74d17-150">Termékek eltávolításához a táblázatból: válassza ki a törölni kívánt sort, és válassza az Eltávolítás elemet.</span><span class="sxs-lookup"><span data-stu-id="74d17-150">To remove products from the table: select the line to remove and select Remove.</span></span>


## <a name="additional-resources"></a><span data-ttu-id="74d17-151">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="74d17-151">Additional resources</span></span>

[<span data-ttu-id="74d17-152">Termékajánlatok áttekintése</span><span class="sxs-lookup"><span data-stu-id="74d17-152">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="74d17-153">Az Azure Data Lake Storage engedélyezése a Dynamics 365 Commerce környezetben</span><span class="sxs-lookup"><span data-stu-id="74d17-153">Enable Azure Data Lake Storage in a Dynamics 365 Commerce environment</span></span>](enable-adls-environment.md)

[<span data-ttu-id="74d17-154">Termékajánlatok engedélyezése</span><span class="sxs-lookup"><span data-stu-id="74d17-154">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="74d17-155">Személyre szabott ajánlatok engedélyezése</span><span class="sxs-lookup"><span data-stu-id="74d17-155">Enable personalized recommendations</span></span>](personalized-recommendations.md)

[<span data-ttu-id="74d17-156">Személyre szabott termékajánlatok kikapcsolása</span><span class="sxs-lookup"><span data-stu-id="74d17-156">Opt out of personalized recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="74d17-157">A hasonlóak megvásárlására vonatkozó javaslatok engedélyezése</span><span class="sxs-lookup"><span data-stu-id="74d17-157">Enable "shop similar looks" recommendations</span></span>](shop-similar-looks.md)

[<span data-ttu-id="74d17-158">Termékajánlatok hozzáadása a pénztárnál</span><span class="sxs-lookup"><span data-stu-id="74d17-158">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="74d17-159">Ajánlatok hozzáadása a tranzakció képernyőjéhez</span><span class="sxs-lookup"><span data-stu-id="74d17-159">Add recommendations to the transaction screen</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="74d17-160">Válogatott ajánlások manuális létrehozása</span><span class="sxs-lookup"><span data-stu-id="74d17-160">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="74d17-161">Ajánlások létrehozása bemutató adatokkal</span><span class="sxs-lookup"><span data-stu-id="74d17-161">Create recommendations with demo data</span></span>](product-recommendations-demo-data.md)

[<span data-ttu-id="74d17-162">Termékajánlatok GYIK-je</span><span class="sxs-lookup"><span data-stu-id="74d17-162">Product recommendations FAQ</span></span>](faq-recommendations.md)
