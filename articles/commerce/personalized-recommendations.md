---
title: Személyre szabott termékajánlatok engedélyezése
description: Ez a témakör bemutatja, hogyan készíthet személyre szabott termékajánlatokat az ügyfelei számára a Microsoft Dynamics 365 Commerce alkalmazásban.
author: bebeale
manager: AnnBe
ms.date: 01/28/2020
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
ms.openlocfilehash: 6b3c6140b8bd3ea15458223c0f61810421d0b2bc
ms.sourcegitcommit: b5ecde955a69f577de46e7db10e89caaedeb2b49
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/04/2020
ms.locfileid: "3025253"
---
# <a name="enable-personalized-recommendations"></a><span data-ttu-id="8ff64-103">Személyre szabott ajánlatok engedélyezése</span><span class="sxs-lookup"><span data-stu-id="8ff64-103">Enable personalized recommendations</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="8ff64-104">Ez a témakör bemutatja, hogyan készíthet személyre szabott termékajánlatokat az ügyfelei számára a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="8ff64-104">This topic describes how to make personalized product recommendations available for customers in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="8ff64-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="8ff64-105">Overview</span></span>

<span data-ttu-id="8ff64-106">A Dynamics 365 Commerce programban a kiskereskedők a személyre szabott termékajánlatokat (más néven személyre szabásokat) tehetnek elérhetővé.</span><span class="sxs-lookup"><span data-stu-id="8ff64-106">In Dynamics 365 Commerce, retailers can make personalized product recommendations (also known as personalization) available.</span></span> <span data-ttu-id="8ff64-107">Ily módon a személyre szabott ajánlások belefoglalhatók az online felhasználói élménybe és a pénztárba (POS).</span><span class="sxs-lookup"><span data-stu-id="8ff64-107">In this way, personalized recommendations can be incorporated into the customer experience online and at the point of sale (POS).</span></span> <span data-ttu-id="8ff64-108">Ha be van kapcsolva a személyre szabási funkció, akkor a rendszer társíthatja a felhasználó beszerzési és termékinformációit az egyéni ajánlások előállításához.</span><span class="sxs-lookup"><span data-stu-id="8ff64-108">When the personalization functionality is turned on, the system can associate a user's purchase and product information to generate individualized product recommendations.</span></span>

## <a name="personalization-prerequisites"></a><span data-ttu-id="8ff64-109">Személyre szabás előfeltételei</span><span class="sxs-lookup"><span data-stu-id="8ff64-109">Personalization prerequisites</span></span>

<span data-ttu-id="8ff64-110">Mielőtt személyre szabott termékajánlásokat tehetne elérhetővé a vevők számára, vegye figyelembe, hogy csak a Commerce azon felhasználónak esetében támogatottak a termékajánlások, akik áttelepítették a tárolójukat az Azure Data Lake Store rendszerbe.</span><span class="sxs-lookup"><span data-stu-id="8ff64-110">Before you make personalized product recommendations available for customers, note that product recommendations are supported only for Commerce users who have migrated their storage to Azure Data Lake Store.</span></span> <span data-ttu-id="8ff64-111">Mielőtt a vevők személyre szabott termékajánlásokat kaphatnának, a kereskedőknek [be kell kapcsolniuk a termékajánlatokat](enable-product-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="8ff64-111">Before customers can receive personalized product recommendations, retailers must [turn on product recommendations](enable-product-recommendations.md).</span></span>

> [!NOTE]
> <span data-ttu-id="8ff64-112">A termékajánlások bekapcsolásával bekapcsolja a személyre szabást is.</span><span class="sxs-lookup"><span data-stu-id="8ff64-112">By turning on product recommendations, you also turn on personalization.</span></span> <span data-ttu-id="8ff64-113">Ha azonban kikapcsolja a személyre szabást, akkor nem kapcsolja ki a termékajánlások egyéb típusait.</span><span class="sxs-lookup"><span data-stu-id="8ff64-113">However, if you turn off personalization, you don't turn off the other types of product recommendations.</span></span>

<span data-ttu-id="8ff64-114">A termékajánlásokkal kapcsolatos további tudnivalókat lásd: [Termékajánlások áttekintése](product-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="8ff64-114">For more information about product recommendations, see the [Product recommendations overview](product-recommendations.md).</span></span>

## <a name="turn-on-personalization"></a><span data-ttu-id="8ff64-115">Személyre szabás bekapcsolása</span><span class="sxs-lookup"><span data-stu-id="8ff64-115">Turn on personalization</span></span>

<span data-ttu-id="8ff64-116">Ha be szeretné kapcsolni a személyre szabást, hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="8ff64-116">To turn on personalization, follow these steps.</span></span>

1. <span data-ttu-id="8ff64-117">Válassza a **Kiskereskedelem és kereskedelem \> Termékjavaslatok \> Ajánlási paraméterek** elemet.</span><span class="sxs-lookup"><span data-stu-id="8ff64-117">Go to **Retail and commerce \> Product recommendations \> Recommendation parameters**.</span></span>
1. <span data-ttu-id="8ff64-118">A Megosztott kiskereskedelmi paraméterek listáján válassza az **Ajánlati listák** elemet.</span><span class="sxs-lookup"><span data-stu-id="8ff64-118">In the list of Retail shared parameters, select **Recommendation lists**.</span></span>
1. <span data-ttu-id="8ff64-119">Állítsa a **Személyre szabás engedélyezése** beállítást **Igen** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8ff64-119">Set the **Enable personalization** option to **Yes**.</span></span>

![Személyre szabás bekapcsolása](./media/enablepersonalization.png)

> [!NOTE]
> <span data-ttu-id="8ff64-121">A személyre szabás bekapcsolásakor a személyre szabott termékajánlási lista létrehozásának folyamata elindul.</span><span class="sxs-lookup"><span data-stu-id="8ff64-121">When you turn on personalization, the process of generating personalized product recommendation lists is started.</span></span> <span data-ttu-id="8ff64-122">Előfordulhat, hogy egy napra is szükség lehet, amíg a listák elérhetővé és láthatóvá válnak online és a pénztárnál.</span><span class="sxs-lookup"><span data-stu-id="8ff64-122">Up to one day might be required before these lists are available and visible online and at the POS.</span></span>

## <a name="personalized-lists"></a><span data-ttu-id="8ff64-123">Személyre szabott lista</span><span class="sxs-lookup"><span data-stu-id="8ff64-123">Personalized lists</span></span>

<span data-ttu-id="8ff64-124">A már létező, géppel készített listák személyre szabásának engedélyezése mellett az ajánlatok szolgáltatás lehetővé teszi a termék felfedezési élményének személyre szabását online és a pénztárnál egyaránt.</span><span class="sxs-lookup"><span data-stu-id="8ff64-124">In addition to allowing for personalization of existing machine-generated lists, the recommendations service allows for personalization of the product discovery experience both online and at the POS.</span></span>

<span data-ttu-id="8ff64-125">Ha be van kapcsolva a személyre szabás, akkor a kiskereskedők személyre szabott „Önnek ajánljuk” listákat jeleníthetnek meg online, vagy „Vásárlónak ajánlott” listákat a POS terminálokon.</span><span class="sxs-lookup"><span data-stu-id="8ff64-125">After personalization is turned on, retailers can show shoppers personalized "Picks for you" lists online or "Recommended for customer" lists on POS terminals.</span></span> <span data-ttu-id="8ff64-126">Ezenkívül a kiskereskedők személyre szabhatják a meglévő termékajánlási listákat, és az Általános adatvédelmi rendelet (GDPR) által biztosított leiratkozási élményt nyújthatnak a hitelesített felhasználók számára.</span><span class="sxs-lookup"><span data-stu-id="8ff64-126">Additionally, retailers can apply personalization to existing product recommendation lists and provide General Data Protection Regulation (GDPR) opt-out experiences for authenticated users.</span></span> <span data-ttu-id="8ff64-127">Ha kikapcsolja a személyre szabást, kikapcsolja ezeket a funkciókat is.</span><span class="sxs-lookup"><span data-stu-id="8ff64-127">If you turn off personalization, you also turn off these features.</span></span>

### <a name="online-picks-for-you-lists"></a><span data-ttu-id="8ff64-128">Online „Önnek ajánljuk” listák</span><span class="sxs-lookup"><span data-stu-id="8ff64-128">Online "Picks for you" lists</span></span>

<span data-ttu-id="8ff64-129">A „Önnek ajánljuk” lista egy mesterséges intelligencia/gépi tanulás (AI-ML) lista, amely ajánlott termékek személyre szabott listáját jeleníti meg egy hitelesített felhasználó számára.</span><span class="sxs-lookup"><span data-stu-id="8ff64-129">A "Picks for you" list is an artificial intelligence-machine learning (AI-ML) list that shows an authenticated user a personalized list of suggested products.</span></span> <span data-ttu-id="8ff64-130">Ez a lista a felhasználói omnicsatorna beszerzési előzményein alapul.</span><span class="sxs-lookup"><span data-stu-id="8ff64-130">This list is based on the user's omnichannel purchase history.</span></span> <span data-ttu-id="8ff64-131">A személyre szabott ajánlások dinamikusan frissülnek, ahogy a felhasználó több beszerzést eszközöl.</span><span class="sxs-lookup"><span data-stu-id="8ff64-131">Personalized recommendations are dynamically updated as the user makes more purchases.</span></span> <span data-ttu-id="8ff64-132">Ez a listatípus a kategóriák szerinti szűrést is támogatja, így a kiskereskedők legjobb ajánlatokat jeleníthetnek meg a navigációs hierarchiák alapján.</span><span class="sxs-lookup"><span data-stu-id="8ff64-132">This type of list also supports category filtering, so that retailers can show top picks, based on navigational hierarchies.</span></span>

<span data-ttu-id="8ff64-133">Mielőtt az „Önnek ajánljuk” lista megjelenne bármilyen e-Commerce oldalon, a következő felhasználói követelményeknek kell teljesülniük:</span><span class="sxs-lookup"><span data-stu-id="8ff64-133">Before the "Picks for you" list can appear on any e-Commerce page, the following user requirements must be met:</span></span>

- <span data-ttu-id="8ff64-134">A felhasználóknak be kell jelentkezniük.</span><span class="sxs-lookup"><span data-stu-id="8ff64-134">Users must be signed in.</span></span> <span data-ttu-id="8ff64-135">A névtelen felhasználók nem fogják látni a személyre szabott ajánlásokat.</span><span class="sxs-lookup"><span data-stu-id="8ff64-135">Anonymous users won't see personalized recommendations.</span></span>
- <span data-ttu-id="8ff64-136">A felhasználóknak legalább egy beszerzéssel kall rendelkezniük a fiókjukban.</span><span class="sxs-lookup"><span data-stu-id="8ff64-136">Users must have at least one purchase on their account.</span></span>
- <span data-ttu-id="8ff64-137">A felhasználóknak fel kell iratkozniuk a személyre szabott ajánlások fogadására.</span><span class="sxs-lookup"><span data-stu-id="8ff64-137">Users must opt in to receive personalized recommendations.</span></span>

<span data-ttu-id="8ff64-138">A következő ábra egy „Önnek ajánljuk” lista példáját jeleníti meg egy online áruház oldalon.</span><span class="sxs-lookup"><span data-stu-id="8ff64-138">The following illustration shows an example of a "Picks for you" list on an online store page.</span></span>

![Online „Önnek ajánljuk” lista](./media/picksforyou.png)

### <a name="recommended-for-customer-lists-at-the-pos"></a><span data-ttu-id="8ff64-140">„Vásárlónak ajánlott” listák a pénztárnál</span><span class="sxs-lookup"><span data-stu-id="8ff64-140">"Recommended for customer" lists at the POS</span></span>

<span data-ttu-id="8ff64-141">Az ügyfélkör-kezelési élmény javítása érdekében a kiskereskedők személyre szabhatják a meglévő ügyfélrészletek oldalakat egy környezetfüggő „Vásárlónak ajánlott” lista hozzáadásával.</span><span class="sxs-lookup"><span data-stu-id="8ff64-141">To enhance their clienteling experience, retailers can personalize existing customer details pages by adding a contextual "Recommended for customer" list.</span></span>

<span data-ttu-id="8ff64-142">A következő ábra egy „Vásárlónak ajánlott” lista példáját jeleníti meg POS terminálon.</span><span class="sxs-lookup"><span data-stu-id="8ff64-142">The following illustration shows an example of a "Recommended for customer" list on a POS terminal.</span></span>

![„Vásárlónak ajánlott” lista a pénztárnál](./media/picksonpos.png)

## <a name="apply-personalization-to-existing-recommendation-lists"></a><span data-ttu-id="8ff64-144">Személyre szabás alkalmazása a meglévő ajánlatok listáira</span><span class="sxs-lookup"><span data-stu-id="8ff64-144">Apply personalization to existing recommendation lists</span></span>

<span data-ttu-id="8ff64-145">A kiskereskedők személyre szabhatják a meglévő ajánlási listákat, például: „Új”, „Népszerű”, „Legkelendőbb”, „Másoknak ez is tetszett” és „Gyakran együtt vásárolt modell”.</span><span class="sxs-lookup"><span data-stu-id="8ff64-145">Retailers can apply personalization to existing recommendation lists, such as "New," "Trending," "Best selling," "People also like," and "Frequently bought together."</span></span> <span data-ttu-id="8ff64-146">Ha a meglévő listákra alkalmaznak személyre szabást, akkor a bejelentkezett felhasználó által korábban vásárolt termékek eltávolításra kerülnek ezekből a listákból.</span><span class="sxs-lookup"><span data-stu-id="8ff64-146">When personalization is applied to existing lists, items that a signed-in user previously bought are removed from those lists.</span></span> <span data-ttu-id="8ff64-147">Mind a névtelen felhasználók, mind a személyre szabott ajánlások fogadásáról leiratkozott felhasználók számára a meglévő listák alapértelmezett verziói jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="8ff64-147">For both anonymous users and users who opted out of receiving personalized recommendations, default versions of the existing lists are shown.</span></span> <span data-ttu-id="8ff64-148">Ennélfogva a kiskereskedőknek nem kell manuálisan karbantartania különböző oldalélményeket.</span><span class="sxs-lookup"><span data-stu-id="8ff64-148">Therefore, retailers don't have to manually maintain separate page experiences.</span></span>

<span data-ttu-id="8ff64-149">Például egy bejelentkezett felhasználó már megvásárolta a fekete órát és a barna munkabakancsot, amely a „Népszerű - alapértelmezett” listában jelenik meg a következő ábrán.</span><span class="sxs-lookup"><span data-stu-id="8ff64-149">For example, a signed-in user has already bought the black watch and the brown work boots that appear in the "Trending - default" list in the following illustration.</span></span> <span data-ttu-id="8ff64-150">Ennélfogva a felhasználó ezen termékek helyett új termékeket fog látni a „Népszerű - személyre szabott” listában látható módon.</span><span class="sxs-lookup"><span data-stu-id="8ff64-150">Therefore, the user will see new products instead of those products, as shown in the "Trending - personalized" list.</span></span>

![Személyre szabás alkalmazása](./media/applypersonalization.png)

<span data-ttu-id="8ff64-152">Személyre szabás alkalmazásához egy meglévő ajánlati listára a Commerce webhelykészítőjében, kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="8ff64-152">To apply personalization to an existing recommendation list in the Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="8ff64-153">Nyisson meg egy termékgyűjtő modult tartalmazó meglévő webhelykészítő lapot.</span><span class="sxs-lookup"><span data-stu-id="8ff64-153">Open an existing site builder page that contains a product collection module.</span></span>
1. <span data-ttu-id="8ff64-154">A bal oldali navigációs ablakban válassza ki a termékgyűjtő modult.</span><span class="sxs-lookup"><span data-stu-id="8ff64-154">In the left navigation pane, select the product collection module.</span></span>
1. <span data-ttu-id="8ff64-155">A jobb oldali navigációs ablakban válassza ki a listát a **Termékek** alatt.</span><span class="sxs-lookup"><span data-stu-id="8ff64-155">In the right navigation pane, under **Products**, select the list.</span></span>
1. <span data-ttu-id="8ff64-156">A **Terméklista-konfiguráció kiválasztása** párbeszédpanelen, a **Típus** alatt vélassza ki a típust.</span><span class="sxs-lookup"><span data-stu-id="8ff64-156">In the **Select product list configuration** dialog box, under **Type**, select the list type.</span></span>
1. <span data-ttu-id="8ff64-157">Válassza ki a **Személyre szabás alkalmazása** jelölőnégyzetet, majd válassza az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8ff64-157">Select the **Apply Personalization** check box, and then select **OK**.</span></span>

    ![Személyre szabás alkalmazása egy népszerű listára](./media/ApplyPersonalizationToTrending.PNG)

1. <span data-ttu-id="8ff64-159">Mentse az oldalt, fejezze be a szerkesztését, majd tegye közzé.</span><span class="sxs-lookup"><span data-stu-id="8ff64-159">Save the page, finish editing it, and then publish it.</span></span> <span data-ttu-id="8ff64-160">Az oldal közzététele után a bejelentkezett felhasználók személyre szabott népszerű listákat láthatnak.</span><span class="sxs-lookup"><span data-stu-id="8ff64-160">After the page is published, signed-in users will see personalized trending lists.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8ff64-161">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="8ff64-161">Additional resources</span></span>

[<span data-ttu-id="8ff64-162">Termékajánlatok áttekintése</span><span class="sxs-lookup"><span data-stu-id="8ff64-162">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="8ff64-163">Termékajánlatok engedélyezése</span><span class="sxs-lookup"><span data-stu-id="8ff64-163">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="8ff64-164">GDPR és termékajánlatok</span><span class="sxs-lookup"><span data-stu-id="8ff64-164">GDPR and product recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="8ff64-165">Termékjavaslat-listák hozzáadása az oldalakhoz</span><span class="sxs-lookup"><span data-stu-id="8ff64-165">Add product recommendation lists to pages</span></span>](add-reco-list-to-page.md)

[<span data-ttu-id="8ff64-166">Ajánlások panel hozzáadása a pénztáreszközökhöz</span><span class="sxs-lookup"><span data-stu-id="8ff64-166">Add recommendations panel to POS devices</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="8ff64-167">Termékgyűjtési modul áttekintése</span><span class="sxs-lookup"><span data-stu-id="8ff64-167">Product collection module overview</span></span>](product-collection-module-overview.md)
