---
title: Személyre szabott termékajánlatok engedélyezése
description: Ez a témakör bemutatja, hogyan készíthet személyre szabott termékajánlatokat az ügyfelei számára a Microsoft Dynamics 365 Commerce alkalmazásban.
author: bebeale
manager: AnnBe
ms.date: 03/12/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: ''
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: bdb56a1f45cdea1832bd269502e534efdb207b03
ms.sourcegitcommit: 1e7e7c4bc197b0a42e4d53d2a54600a2fb125b69
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/13/2020
ms.locfileid: "3127905"
---
# <a name="enable-personalized-recommendations"></a><span data-ttu-id="9af02-103">Személyre szabott ajánlatok engedélyezése</span><span class="sxs-lookup"><span data-stu-id="9af02-103">Enable personalized recommendations</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="9af02-104">Ez a témakör bemutatja, hogyan készíthet személyre szabott termékajánlatokat az ügyfelei számára a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="9af02-104">This topic describes how to make personalized product recommendations available for customers in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="9af02-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="9af02-105">Overview</span></span>

<span data-ttu-id="9af02-106">A Dynamics 365 Commerce programban a kiskereskedők a személyre szabott termékajánlatokat (más néven személyre szabásokat) tehetnek elérhetővé.</span><span class="sxs-lookup"><span data-stu-id="9af02-106">In Dynamics 365 Commerce, retailers can make personalized product recommendations (also known as personalization) available.</span></span> <span data-ttu-id="9af02-107">Ily módon a személyre szabott ajánlások belefoglalhatók az online felhasználói élménybe és a pénztárba (POS).</span><span class="sxs-lookup"><span data-stu-id="9af02-107">In this way, personalized recommendations can be incorporated into the customer experience online and at the point of sale (POS).</span></span> <span data-ttu-id="9af02-108">Ha be van kapcsolva a személyre szabási funkció, akkor a rendszer társíthatja a felhasználó beszerzési és termékinformációit az egyéni ajánlások előállításához.</span><span class="sxs-lookup"><span data-stu-id="9af02-108">When the personalization functionality is turned on, the system can associate a user's purchase and product information to generate individualized product recommendations.</span></span>

## <a name="personalization-prerequisites"></a><span data-ttu-id="9af02-109">Személyre szabás előfeltételei</span><span class="sxs-lookup"><span data-stu-id="9af02-109">Personalization prerequisites</span></span>

<span data-ttu-id="9af02-110">Mielőtt személyre szabott termékajánlásokat tehetne elérhetővé a vevők számára, vegye figyelembe, hogy csak a Commerce azon felhasználónak esetében támogatottak a termékajánlások, akik áttelepítették a tárolójukat az Azure Data Lake Store rendszerbe.</span><span class="sxs-lookup"><span data-stu-id="9af02-110">Before you make personalized product recommendations available for customers, note that product recommendations are supported only for Commerce users who have migrated their storage to Azure Data Lake Store.</span></span> <span data-ttu-id="9af02-111">Mielőtt a vevők személyre szabott termékajánlásokat kaphatnának, a kereskedőknek [be kell kapcsolniuk a termékajánlatokat](enable-product-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="9af02-111">Before customers can receive personalized product recommendations, retailers must [turn on product recommendations](enable-product-recommendations.md).</span></span>

> [!NOTE]
> <span data-ttu-id="9af02-112">A termékajánlások bekapcsolásával bekapcsolja a személyre szabást is.</span><span class="sxs-lookup"><span data-stu-id="9af02-112">By turning on product recommendations, you also turn on personalization.</span></span> <span data-ttu-id="9af02-113">Ha azonban kikapcsolja a személyre szabást, akkor nem kapcsolja ki a termékajánlások egyéb típusait.</span><span class="sxs-lookup"><span data-stu-id="9af02-113">However, if you turn off personalization, you don't turn off the other types of product recommendations.</span></span>

<span data-ttu-id="9af02-114">A termékajánlásokkal kapcsolatos további tudnivalókat lásd: [Termékajánlások áttekintése](product-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="9af02-114">For more information about product recommendations, see the [Product recommendations overview](product-recommendations.md).</span></span>

## <a name="turn-on-personalization"></a><span data-ttu-id="9af02-115">Személyre szabás bekapcsolása</span><span class="sxs-lookup"><span data-stu-id="9af02-115">Turn on personalization</span></span>

<span data-ttu-id="9af02-116">Ha be szeretné kapcsolni a személyre szabást, hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="9af02-116">To turn on personalization, follow these steps.</span></span>

1. <span data-ttu-id="9af02-117">Válassza a **Kiskereskedelem és kereskedelem \> Termékjavaslatok \> Ajánlási paraméterek** elemet.</span><span class="sxs-lookup"><span data-stu-id="9af02-117">Go to **Retail and commerce \> Product recommendations \> Recommendation parameters**.</span></span>
1. <span data-ttu-id="9af02-118">A Megosztott kiskereskedelmi paraméterek listáján válassza az **Ajánlati listák** elemet.</span><span class="sxs-lookup"><span data-stu-id="9af02-118">In the list of Retail shared parameters, select **Recommendation lists**.</span></span>
1. <span data-ttu-id="9af02-119">Állítsa a **Személyre szabás engedélyezése** beállítást **Igen** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="9af02-119">Set the **Enable personalization** option to **Yes**.</span></span>

![Személyre szabás bekapcsolása](./media/enablepersonalization.png)

> [!NOTE]
> <span data-ttu-id="9af02-121">A személyre szabás bekapcsolásakor a személyre szabott termékajánlási lista létrehozásának folyamata elindul.</span><span class="sxs-lookup"><span data-stu-id="9af02-121">When you turn on personalization, the process of generating personalized product recommendation lists is started.</span></span> <span data-ttu-id="9af02-122">Előfordulhat, hogy egy napra is szükség lehet, amíg a listák elérhetővé és láthatóvá válnak online és a pénztárnál.</span><span class="sxs-lookup"><span data-stu-id="9af02-122">Up to one day might be required before these lists are available and visible online and at the POS.</span></span>

## <a name="personalized-lists"></a><span data-ttu-id="9af02-123">Személyre szabott lista</span><span class="sxs-lookup"><span data-stu-id="9af02-123">Personalized lists</span></span>

<span data-ttu-id="9af02-124">A már létező, géppel készített listák személyre szabásának engedélyezése mellett az ajánlatok szolgáltatás lehetővé teszi a termék felfedezési élményének személyre szabását online és a pénztárnál egyaránt.</span><span class="sxs-lookup"><span data-stu-id="9af02-124">In addition to allowing for personalization of existing machine-generated lists, the recommendations service allows for personalization of the product discovery experience both online and at the POS.</span></span>

<span data-ttu-id="9af02-125">Ha be van kapcsolva a személyre szabás, akkor a kiskereskedők személyre szabott „Önnek ajánljuk” listákat jeleníthetnek meg online, vagy „Vásárlónak ajánlott” listákat a POS terminálokon.</span><span class="sxs-lookup"><span data-stu-id="9af02-125">After personalization is turned on, retailers can show shoppers personalized "Picks for you" lists online or "Recommended for customer" lists on POS terminals.</span></span> <span data-ttu-id="9af02-126">Ezenkívül a kiskereskedők személyre szabhatják a meglévő termékajánlási listákat, és az Általános adatvédelmi rendelet (GDPR) által biztosított leiratkozási élményt nyújthatnak a hitelesített felhasználók számára.</span><span class="sxs-lookup"><span data-stu-id="9af02-126">Additionally, retailers can apply personalization to existing product recommendation lists and provide General Data Protection Regulation (GDPR) opt-out experiences for authenticated users.</span></span> <span data-ttu-id="9af02-127">Ha kikapcsolja a személyre szabást, kikapcsolja ezeket a funkciókat is.</span><span class="sxs-lookup"><span data-stu-id="9af02-127">If you turn off personalization, you also turn off these features.</span></span>

### <a name="online-picks-for-you-lists"></a><span data-ttu-id="9af02-128">Online „Önnek ajánljuk” listák</span><span class="sxs-lookup"><span data-stu-id="9af02-128">Online "Picks for you" lists</span></span>

<span data-ttu-id="9af02-129">A „Önnek ajánljuk” lista egy mesterséges intelligencia/gépi tanulás (AI-ML) lista, amely ajánlott termékek személyre szabott listáját jeleníti meg egy hitelesített felhasználó számára.</span><span class="sxs-lookup"><span data-stu-id="9af02-129">A "Picks for you" list is an artificial intelligence-machine learning (AI-ML) list that shows an authenticated user a personalized list of suggested products.</span></span> <span data-ttu-id="9af02-130">Ez a lista a felhasználói omnicsatorna beszerzési előzményein alapul.</span><span class="sxs-lookup"><span data-stu-id="9af02-130">This list is based on the user's omnichannel purchase history.</span></span> <span data-ttu-id="9af02-131">A személyre szabott ajánlások dinamikusan frissülnek, ahogy a felhasználó több beszerzést eszközöl.</span><span class="sxs-lookup"><span data-stu-id="9af02-131">Personalized recommendations are dynamically updated as the user makes more purchases.</span></span> <span data-ttu-id="9af02-132">Ez a listatípus a kategóriák szerinti szűrést is támogatja, így a kiskereskedők legjobb ajánlatokat jeleníthetnek meg a navigációs hierarchiák alapján.</span><span class="sxs-lookup"><span data-stu-id="9af02-132">This type of list also supports category filtering, so that retailers can show top picks, based on navigational hierarchies.</span></span>

<span data-ttu-id="9af02-133">Mielőtt az „Önnek ajánljuk” lista megjelenne bármilyen e-Commerce oldalon, a következő felhasználói követelményeknek kell teljesülniük:</span><span class="sxs-lookup"><span data-stu-id="9af02-133">Before the "Picks for you" list can appear on any e-Commerce page, the following user requirements must be met:</span></span>

- <span data-ttu-id="9af02-134">A felhasználóknak be kell jelentkezniük.</span><span class="sxs-lookup"><span data-stu-id="9af02-134">Users must be signed in.</span></span> <span data-ttu-id="9af02-135">A névtelen felhasználók nem fogják látni a személyre szabott ajánlásokat.</span><span class="sxs-lookup"><span data-stu-id="9af02-135">Anonymous users won't see personalized recommendations.</span></span>
- <span data-ttu-id="9af02-136">A felhasználóknak legalább egy beszerzéssel kall rendelkezniük a fiókjukban.</span><span class="sxs-lookup"><span data-stu-id="9af02-136">Users must have at least one purchase on their account.</span></span>
- <span data-ttu-id="9af02-137">A felhasználóknak fel kell iratkozniuk a személyre szabott ajánlások fogadására.</span><span class="sxs-lookup"><span data-stu-id="9af02-137">Users must opt in to receive personalized recommendations.</span></span>

<span data-ttu-id="9af02-138">A következő ábra egy „Önnek ajánljuk” lista példáját jeleníti meg egy online áruház oldalon.</span><span class="sxs-lookup"><span data-stu-id="9af02-138">The following illustration shows an example of a "Picks for you" list on an online store page.</span></span>

![Online „Önnek ajánljuk” lista](./media/picksforyou.png)

### <a name="recommended-for-customer-lists-at-the-pos"></a><span data-ttu-id="9af02-140">„Vásárlónak ajánlott” listák a pénztárnál</span><span class="sxs-lookup"><span data-stu-id="9af02-140">"Recommended for customer" lists at the POS</span></span>

<span data-ttu-id="9af02-141">Az ügyfélkör-kezelési élmény javítása érdekében a kiskereskedők személyre szabhatják a meglévő ügyfélrészletek oldalakat egy környezetfüggő „Vásárlónak ajánlott” lista hozzáadásával.</span><span class="sxs-lookup"><span data-stu-id="9af02-141">To enhance their clienteling experience, retailers can personalize existing customer details pages by adding a contextual "Recommended for customer" list.</span></span>

<span data-ttu-id="9af02-142">A következő ábra egy „Vásárlónak ajánlott” lista példáját jeleníti meg POS terminálon.</span><span class="sxs-lookup"><span data-stu-id="9af02-142">The following illustration shows an example of a "Recommended for customer" list on a POS terminal.</span></span>

![„Vásárlónak ajánlott” lista a pénztárnál](./media/picksonpos.png)

## <a name="apply-personalization-to-existing-recommendation-lists"></a><span data-ttu-id="9af02-144">Személyre szabás alkalmazása a meglévő ajánlatok listáira</span><span class="sxs-lookup"><span data-stu-id="9af02-144">Apply personalization to existing recommendation lists</span></span>

<span data-ttu-id="9af02-145">A kiskereskedők személyre szabhatják a meglévő ajánlási listákat, például: „Új”, „Népszerű”, „Legkelendőbb”, „Másoknak ez is tetszett” és „Gyakran együtt vásárolt modell”.</span><span class="sxs-lookup"><span data-stu-id="9af02-145">Retailers can apply personalization to existing recommendation lists, such as "New," "Trending," "Best selling," "People also like," and "Frequently bought together."</span></span> <span data-ttu-id="9af02-146">Ha a meglévő listákra alkalmaznak személyre szabást, akkor a bejelentkezett felhasználó által korábban vásárolt termékek eltávolításra kerülnek ezekből a listákból.</span><span class="sxs-lookup"><span data-stu-id="9af02-146">When personalization is applied to existing lists, items that a signed-in user previously bought are removed from those lists.</span></span> <span data-ttu-id="9af02-147">Mind a névtelen felhasználók, mind a személyre szabott ajánlások fogadásáról leiratkozott felhasználók számára a meglévő listák alapértelmezett verziói jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="9af02-147">For both anonymous users and users who opted out of receiving personalized recommendations, default versions of the existing lists are shown.</span></span> <span data-ttu-id="9af02-148">Ennélfogva a kiskereskedőknek nem kell manuálisan karbantartania különböző oldalélményeket.</span><span class="sxs-lookup"><span data-stu-id="9af02-148">Therefore, retailers don't have to manually maintain separate page experiences.</span></span>

<span data-ttu-id="9af02-149">Például egy bejelentkezett felhasználó már megvásárolta a fekete órát és a barna munkabakancsot, amely a „Népszerű - alapértelmezett” listában jelenik meg a következő ábrán.</span><span class="sxs-lookup"><span data-stu-id="9af02-149">For example, a signed-in user has already bought the black watch and the brown work boots that appear in the "Trending - default" list in the following illustration.</span></span> <span data-ttu-id="9af02-150">Ennélfogva a felhasználó ezen termékek helyett új termékeket fog látni a „Népszerű - személyre szabott” listában látható módon.</span><span class="sxs-lookup"><span data-stu-id="9af02-150">Therefore, the user will see new products instead of those products, as shown in the "Trending - personalized" list.</span></span>

![Személyre szabás alkalmazása](./media/applypersonalization.png)

<span data-ttu-id="9af02-152">Személyre szabás alkalmazásához egy meglévő ajánlati listára a Commerce webhelykészítőjében, kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="9af02-152">To apply personalization to an existing recommendation list in the Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="9af02-153">Nyisson meg egy termékgyűjtő modult tartalmazó meglévő webhelykészítő lapot.</span><span class="sxs-lookup"><span data-stu-id="9af02-153">Open an existing site builder page that contains a product collection module.</span></span>
1. <span data-ttu-id="9af02-154">A bal oldali navigációs ablakban válassza ki a termékgyűjtő modult.</span><span class="sxs-lookup"><span data-stu-id="9af02-154">In the left navigation pane, select the product collection module.</span></span>
1. <span data-ttu-id="9af02-155">A jobb oldali navigációs ablakban válassza ki a listát a **Termékek** alatt.</span><span class="sxs-lookup"><span data-stu-id="9af02-155">In the right navigation pane, under **Products**, select the list.</span></span>
1. <span data-ttu-id="9af02-156">A **Terméklista-konfiguráció kiválasztása** párbeszédpanelen, a **Típus** alatt vélassza ki a típust.</span><span class="sxs-lookup"><span data-stu-id="9af02-156">In the **Select product list configuration** dialog box, under **Type**, select the list type.</span></span>
1. <span data-ttu-id="9af02-157">Válassza ki a **Személyre szabás alkalmazása** jelölőnégyzetet, majd válassza az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9af02-157">Select the **Apply Personalization** check box, and then select **OK**.</span></span>

    ![Személyre szabás alkalmazása egy népszerű listára](./media/ApplyPersonalizationToTrending.PNG)

1. <span data-ttu-id="9af02-159">Mentse az oldalt, fejezze be a szerkesztését, majd tegye közzé.</span><span class="sxs-lookup"><span data-stu-id="9af02-159">Save the page, finish editing it, and then publish it.</span></span> <span data-ttu-id="9af02-160">Az oldal közzététele után a bejelentkezett felhasználók személyre szabott népszerű listákat láthatnak.</span><span class="sxs-lookup"><span data-stu-id="9af02-160">After the page is published, signed-in users will see personalized trending lists.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9af02-161">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="9af02-161">Additional resources</span></span>

[<span data-ttu-id="9af02-162">Termékajánlatok áttekintése</span><span class="sxs-lookup"><span data-stu-id="9af02-162">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="9af02-163">ADLS engedélyezése a Dynamics 365 Commerce környezetben</span><span class="sxs-lookup"><span data-stu-id="9af02-163">Enable ADLS in a Dynamics 365 Commerce environment</span></span>](enable-adls-environment.md)

[<span data-ttu-id="9af02-164">Termékajánlatok engedélyezése</span><span class="sxs-lookup"><span data-stu-id="9af02-164">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="9af02-165">Személyre szabott termékajánlatok kikapcsolása</span><span class="sxs-lookup"><span data-stu-id="9af02-165">Opt out of personalized recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="9af02-166">Ajánlat listáinak hozzáadása egy e-Commerce webhelyhez</span><span class="sxs-lookup"><span data-stu-id="9af02-166">Add recommendation lists to an e-Commerce site</span></span>](add-reco-list-to-page.md)

[<span data-ttu-id="9af02-167">Termékajánlások hozzáadása a pénztárnál</span><span class="sxs-lookup"><span data-stu-id="9af02-167">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="9af02-168">Ajánlatok hozzáadása a tranzakciós képernyőhöz</span><span class="sxs-lookup"><span data-stu-id="9af02-168">Add recommendations to the transaction screen</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="9af02-169">AI-ML ajánlások eredményeinek helyesbítése</span><span class="sxs-lookup"><span data-stu-id="9af02-169">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="9af02-170">Válogatott ajánlások manuális létrehozása</span><span class="sxs-lookup"><span data-stu-id="9af02-170">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="9af02-171">Ajánlások létrehozása bemutató adatokkal</span><span class="sxs-lookup"><span data-stu-id="9af02-171">Create recommendations with demo data</span></span>](product-recommendations-demo-data.md)

[<span data-ttu-id="9af02-172">Termékajánlatok GYIK-je</span><span class="sxs-lookup"><span data-stu-id="9af02-172">Product recommendations FAQ</span></span>](faq-recommendations.md)
