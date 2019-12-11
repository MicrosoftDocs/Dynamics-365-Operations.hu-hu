---
title: AI-ML-alapú termékajánlás eredményeinek kezelése
description: Ez a témakör azt mutatja be, hogyan lehet testreszabni a termékjavaslatok eredményeit a mesterséges intelligencia gépi tanulás (AI-ML) alapján a vállalkozása számára.
author: bebeale
manager: AnnBe
ms.date: 10/1/2019
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
ms.openlocfilehash: 669b056c38614c8ac9be2d7b244a0ab0c73bc9f8
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770070"
---
# <a name="manage-ai-ml-based-product-recommendation-results"></a><span data-ttu-id="b7c14-103">AI-ML-alapú termékajánlás eredményeinek kezelése</span><span class="sxs-lookup"><span data-stu-id="b7c14-103">Manage AI-ML-based product recommendation results</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="b7c14-104">Ez a témakör azt mutatja be, hogyan lehet testreszabni a termékjavaslatok eredményeit a mesterséges intelligencia gépi tanulás (AI-ML) alapján a vállalkozása számára.</span><span class="sxs-lookup"><span data-stu-id="b7c14-104">This topic explains how to tailor product recommendation results based on artificial intelligence-machine learning (AI-ML) to your business.</span></span> 

<span data-ttu-id="b7c14-105">A termékjavaslatok engedélyezése után az alapértelmezett beállítások lépnek érvénybe ezek a paraméterek számos szükséglethez használhatók lehetnek.</span><span class="sxs-lookup"><span data-stu-id="b7c14-105">After enabling product recommendations, the default settings will take effect; these parameters will work for may work for many needs.</span></span> <span data-ttu-id="b7c14-106">A legjobb az, ha hagynak egy kis időt arra, hogy az eredmények megfelelnek-e a termékek értékesítési irányának.</span><span class="sxs-lookup"><span data-stu-id="b7c14-106">It is best to plan to spend some time evaluating whether the results fit the selling motion of products.</span></span> <span data-ttu-id="b7c14-107">Javasoljuk, hogy néhány napig értékelje ki az eredményeket, mielőtt igény szerint módosítaná a paramétereket az újratesztelés előtt.</span><span class="sxs-lookup"><span data-stu-id="b7c14-107">We suggest evaluating results for a few days before changing parameters as needed before testing again.</span></span> 

## <a name="understanding-recommendation-list-parameters"></a><span data-ttu-id="b7c14-108">Az ajánlási lista paramétereinek ismertetése</span><span class="sxs-lookup"><span data-stu-id="b7c14-108">Understanding recommendation list parameters</span></span>

<span data-ttu-id="b7c14-109">A paraméterek módosítása előtt az alábbi részből megismerheti, hogy milyen hatással lesznek az eredményekre.</span><span class="sxs-lookup"><span data-stu-id="b7c14-109">Before changing the parameters, learn about how they will affect the results below.</span></span>

### <a name="trending-product-list"></a><span data-ttu-id="b7c14-110">Népszerű terméklista</span><span class="sxs-lookup"><span data-stu-id="b7c14-110">Trending product list</span></span>

<span data-ttu-id="b7c14-111">A **Népszerű** terméklista két olyan paraméterrel rendelkezik, amelyek módosíthatók: ![Példa a Népszerű lista alapértelmezett paramétereire](./media/exampletrendingparameters.png)</span><span class="sxs-lookup"><span data-stu-id="b7c14-111">The **Trending** product list has two parameters that can be changed: ![Example Trending list default parameters](./media/exampletrendingparameters.png)</span></span>
1. <span data-ttu-id="b7c14-112">**Új termékek belefoglalása a legutóbbi X napból** – Azok a termékek, amelyek az aktuális dátumtól számított megadott számú napon belül lettek hozzáadva használhatók termékjelöltek kiválasztásához.</span><span class="sxs-lookup"><span data-stu-id="b7c14-112">**Include new products from last X days** - Products that have been added within the specified number of days before the current date can be used to select product candidates.</span></span> <span data-ttu-id="b7c14-113">A kép alapértelmezett értéke azt sugallja, hogy maximum 180 napos termékek használhatók fel a népszerű termékek listájában.</span><span class="sxs-lookup"><span data-stu-id="b7c14-113">The default value in the picture suggests that products as old has 180 days can be used in the trending product list.</span></span>
1. <span data-ttu-id="b7c14-114">**Értékesítések belefoglalása a legutóbbi X napból** – Azok az értékesítési tranzakciók, amelyek az aktuális dátumtól számított megadott számú napon belül történtek használhatók a termékek rendezéséhez.</span><span class="sxs-lookup"><span data-stu-id="b7c14-114">**Include sales from last X days** - Sales transactions that have occurred within the specified number of days before the current date can be used to order the products.</span></span> <span data-ttu-id="b7c14-115">A fenti alapértelmezett érték azt sugallja, hogy az elmúlt 30 napban a termékhez tartozó összes vásárlás lenne felhasználva a termék helyének meghatározásához a népszerű termékek listáján.</span><span class="sxs-lookup"><span data-stu-id="b7c14-115">The default value above suggests that all purchases made of a product in the last 30 days would be used to determine the placement of the product in the trending product list.</span></span> 

### <a name="best-selling-product-list"></a><span data-ttu-id="b7c14-116">Legkelendőbb termékek listája</span><span class="sxs-lookup"><span data-stu-id="b7c14-116">Best selling product list</span></span>

<span data-ttu-id="b7c14-117">A vállalattól függően a legkelendőbb szempont eltérő eredményt adhat, mint a népszerűség annak ellenére, hogy mindkettő a tranzakcióadatokat használ a termékek rendezéséhez.</span><span class="sxs-lookup"><span data-stu-id="b7c14-117">Depending on your business, Best selling can bring different results than trending, even though they both use transaction data to order products.</span></span> <span data-ttu-id="b7c14-118">Mivel a legjobban fogyó termékek esetében nincs határ a szortiment dátuma alapján, a legjobban fogyó termékek listáján megjelenhetnek olyan nagyon népszerű, régebbi termékek , amelyek már lekerültek a népszerű termékek listájáról.</span><span class="sxs-lookup"><span data-stu-id="b7c14-118">Because best selling has no cut off based on assortment date, Best selling can still highlight very popular, older products that might have been dropped from the trending list.</span></span> 

<span data-ttu-id="b7c14-119">A **Legkelendőbb** terméklistán egyetlen paraméterrel módosítható:</span><span class="sxs-lookup"><span data-stu-id="b7c14-119">The **Best selling** product list has one parameter that can be changed:</span></span>

![Példa a Legkelendőbb lista alapértelmezett paraméterére](./media/examplebestsellingparameters.PNG)
1. <span data-ttu-id="b7c14-121">**Értékesítések belefoglalása a legutóbbi X napból** – Azok az értékesítési tranzakciók, amelyek az aktuális dátumtól számított megadott számú napon belül történtek használhatók a termékek rendezéséhez.</span><span class="sxs-lookup"><span data-stu-id="b7c14-121">**Include sales from last X days** - Sales transactions that have occurred within the specified number of days before the current date can be used to order the products.</span></span> <span data-ttu-id="b7c14-122">A fenti alapértelmezett érték azt sugallja, hogy az elmúlt 30 napban a termékhez tartozó összes vásárlás lenne felhasználva a termék helyének meghatározásához a Legkelendőbb termékek listáján.</span><span class="sxs-lookup"><span data-stu-id="b7c14-122">The default value above suggests that all purchases made of a product in the last 30 days would be used to determine the placement of the product in the Best selling product list.</span></span> 

## <a name="manually-add-or-remove-products-from-recommendation-lists"></a><span data-ttu-id="b7c14-123">Termékek manuális hozzáadása vagy eltávolítása az ajánlási listákból</span><span class="sxs-lookup"><span data-stu-id="b7c14-123">Manually add or remove products from recommendation lists</span></span>

### <a name="for-new-trending-or-best-selling"></a><span data-ttu-id="b7c14-124">Az Új, Népszerű vagy Legkelendőbb esetében</span><span class="sxs-lookup"><span data-stu-id="b7c14-124">For New, Trending, or Best selling</span></span>

1.  <span data-ttu-id="b7c14-125">Válassza a **Retail** > **Termékajánlások** > **Ajánlási paraméterek** elemet.</span><span class="sxs-lookup"><span data-stu-id="b7c14-125">Go to **Retail** > **Product recommendations** > **Recommendation parameters**.</span></span>
1.  <span data-ttu-id="b7c14-126">A kiskereskedelmi megosztott paraméterek listáján válassza az **Ajánlati listák**elemet.</span><span class="sxs-lookup"><span data-stu-id="b7c14-126">In the list of retail shared parameters, select **Recommendation lists**.</span></span>
1.  <span data-ttu-id="b7c14-127">Jelölje ki a listát a termékek hozzáadásához vagy eltávolításához.</span><span class="sxs-lookup"><span data-stu-id="b7c14-127">Select the list add or remove products from.</span></span>
1.  <span data-ttu-id="b7c14-128">Ha termékeket szeretne hozzáadni a táblázathoz, válassza a **Sor hozzáadása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b7c14-128">To add products to the table, select **Add line.**</span></span> 
1.  <span data-ttu-id="b7c14-129">A Termék oszlopban keressen egy terméket **Név** vagy **Cikkszám** alapján
![Példa a termék keresésére az új Termékek listájában](./media/examplenewlistconfiguration1.png)</span><span class="sxs-lookup"><span data-stu-id="b7c14-129">Under the Product column, search for a product by **Name** or **Product number.**
![Example of searching for a product on the New product list](./media/examplenewlistconfiguration1.png)</span></span>
1.  <span data-ttu-id="b7c14-130">A Sor típusa oszlopban válassza ki a két beállítás egyikét:</span><span class="sxs-lookup"><span data-stu-id="b7c14-130">Under the Line type column, select one of two options:</span></span>
    -   <span data-ttu-id="b7c14-131">**Belefoglalás** – egy terméket a lista elejére kényszerít</span><span class="sxs-lookup"><span data-stu-id="b7c14-131">**Include** – forces a product to the front of the list</span></span>
    -   <span data-ttu-id="b7c14-132">**Kizárás** – eltávolít egy terméket a listából ![Például a termék befoglalására kizárására az Új termékek listáján](./media/examplenewlistconfiguration2.png)</span><span class="sxs-lookup"><span data-stu-id="b7c14-132">**Exclude** – removes a product from appearing in the list ![Example of Including or Excluding a product from the New product list](./media/examplenewlistconfiguration2.png)</span></span>
1.  <span data-ttu-id="b7c14-133">A **Megjelenítési sorrend** módosítása megváltoztatja azt, hogy a **belefoglalásra** megjelölt termékek milyen sorendben jelenjenek meg a listában.</span><span class="sxs-lookup"><span data-stu-id="b7c14-133">Changing the **Display order** will change the order that products marked **include** will appear in the list.</span></span>
    - <span data-ttu-id="b7c14-134">Ha két terméknél ugyanaz **megjelenítési sorrend** értéke, akkor a két eredmény végső sorrendje eltérhet a háttéroldaltól.</span><span class="sxs-lookup"><span data-stu-id="b7c14-134">If two products have the same **display order** value, then the final order of those two results may differ from the back office.</span></span>
1.  <span data-ttu-id="b7c14-135">Termékek eltávolításához a táblázatból: válassza ki a törölni kívánt sort, és válassza az **Eltávolítás** elemet.</span><span class="sxs-lookup"><span data-stu-id="b7c14-135">To remove products from the table: select the line to remove and select **Remove**.</span></span>


### <a name="for-people-also-like-or-frequently-bought-together-lists"></a><span data-ttu-id="b7c14-136">A Másoknak ez is tetszett vagy Gyakran együtt vásárolt listák esetében</span><span class="sxs-lookup"><span data-stu-id="b7c14-136">For People also like or Frequently bought together lists</span></span>

<span data-ttu-id="b7c14-137">A **Gyakran együtt vásárolt**, illetve a **Másoknak ez is tetszett** listák esetében gépi tanulást alkalmazunk a fogyasztók vásárlási mintáinak elemzéséhez, illetve kapcsolódó termékek ajánlásához, amelyeket gyakran megvásároltak együtt egy megtekintett termékkel.</span><span class="sxs-lookup"><span data-stu-id="b7c14-137">In the context of **Frequently bought together** or **People also like** lists, machine learning is used to analyze consumer purchase patterns to recommend related products commonly purchased together for a unique seed product.</span></span> 
 
<span data-ttu-id="b7c14-138">A **megtekintett termék** az a termék, amelyhez az eredményeket generálni szeretné.</span><span class="sxs-lookup"><span data-stu-id="b7c14-138">A **seed product** is the product you want to generate results for.</span></span> <span data-ttu-id="b7c14-139">Az ajánlási listák manuális módosításával összefüggésben ehhez a termékhez adja hozzá vagy távolítja el az eredményeket.</span><span class="sxs-lookup"><span data-stu-id="b7c14-139">In the context of manually adjusting recommendation lists, you are adding or removing results for this product.</span></span> 

<span data-ttu-id="b7c14-140">A következő lépések végrehajtásával manuálisan adhat hozzá vagy távolíthat el eredményeket egy alaptermékhez:</span><span class="sxs-lookup"><span data-stu-id="b7c14-140">Follow these steps to manually add or remove results for a seed product:</span></span>
1.  <span data-ttu-id="b7c14-141">Válassza ki a **Kiinduló terméket**.</span><span class="sxs-lookup"><span data-stu-id="b7c14-141">Select the **Seed product**.</span></span> 
1.  <span data-ttu-id="b7c14-142">A **Termék** oszlopban keressen egy terméket **Név** vagy **Cikkszám alapján.**
![Példa a termék keresésére a Gyakran együtt vásárolt listában](./media/exampleFBTlistconfiguration1.png)</span><span class="sxs-lookup"><span data-stu-id="b7c14-142">Under the **Product** column, search for a product by **Name** or **Product number.**
![Example of searching for a product on the Frequently bought together list](./media/exampleFBTlistconfiguration1.png)</span></span>
1. <span data-ttu-id="b7c14-143">A **Sor típusa** oszlopban válassza ki a két beállítás egyikét:</span><span class="sxs-lookup"><span data-stu-id="b7c14-143">Under the **Line type** column, select one of two options:</span></span>
    - <span data-ttu-id="b7c14-144">**Belefoglalás** – egy terméket a lista elejére kényszerít</span><span class="sxs-lookup"><span data-stu-id="b7c14-144">**Include** – forces a product to the front of the list</span></span>
    - <span data-ttu-id="b7c14-145">**Kizárás** – eltávolít egy terméket a listából.</span><span class="sxs-lookup"><span data-stu-id="b7c14-145">**Exclude** – removes a product from appearing in the list</span></span>     
<span data-ttu-id="b7c14-146">![Példa egy termék belefoglalására vagy kizárására a Gyakran együtt vásárolt listában](./media/exampleFBTlistconfiguration2.png)</span><span class="sxs-lookup"><span data-stu-id="b7c14-146">![Example of Including or Excluding a product on the Frequently bought together list](./media/exampleFBTlistconfiguration2.png)</span></span>
1.  <span data-ttu-id="b7c14-147">Termékek eltávolításához a táblázatból: válassza ki a törölni kívánt sort, és válassza az Eltávolítás elemet.</span><span class="sxs-lookup"><span data-stu-id="b7c14-147">To remove products from the table: select the line to remove and select Remove.</span></span>


## <a name="additional-resources"></a><span data-ttu-id="b7c14-148">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="b7c14-148">Additional resources</span></span>

[<span data-ttu-id="b7c14-149">Termékajánlatok áttekintése</span><span class="sxs-lookup"><span data-stu-id="b7c14-149">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="b7c14-150">Termékajánlatok engedélyezése</span><span class="sxs-lookup"><span data-stu-id="b7c14-150">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="b7c14-151">Termékjavaslat-listák hozzáadása az oldalakhoz</span><span class="sxs-lookup"><span data-stu-id="b7c14-151">Add product recommendation lists to pages</span></span>](add-reco-list-to-page.md)
