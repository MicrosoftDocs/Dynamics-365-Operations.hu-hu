---
title: „Hasonló megvásárlása leírás” javaslatok engedélyezése
description: Ez a témakör azt mutatja be, hogyan engedélyezheti a „hasonló megvásárlása leírás” termékjavaslatokat a Microsoft Dynamics 365 Commerce szolgáltatásban.
author: bsokolov
manager: AnnBe
ms.date: 01/13/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: b6b397b1f21e3dfcdb4a2b7fe67ddb541d090a97
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5234389"
---
# <a name="enable-shop-similar-description-recommendations"></a><span data-ttu-id="1b10a-103">„Hasonló leírású termékek vásárlása” javaslatok engedélyezése</span><span class="sxs-lookup"><span data-stu-id="1b10a-103">Enable "shop similar description" recommendations</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="1b10a-104">Ez a témakör azt mutatja be, hogyan engedélyezheti a „hasonló megvásárlása leírás” termékjavaslatokat a Microsoft Dynamics 365 Commerce szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="1b10a-104">This topic describes how to enable "shop similar description" product recommendations in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="1b10a-105">A „hasonló megvásárlása leírás” javaslatokat tartalmazó funkció a Dynamics 365 Commerce szolgáltatásban mesterséges intelligenciát és gépi tanulást (AI-ML) alkalmaz, hogy olyan termékeket ajánljon a vevőnek, amelyek leírása hasonlít ahhoz, amit a vevő keres.</span><span class="sxs-lookup"><span data-stu-id="1b10a-105">The "shop similar description" recommendations feature in Dynamics 365 Commerce uses artificial intelligence and machine learning (AI-ML) to deliver recommendations for products that have descriptions that are similar to what the customer is looking for.</span></span> <span data-ttu-id="1b10a-106">A „hasonló megvásárlása leírás” javaslatok elérhetők a Commerce összes kiskereskedelmi csatornáján, ezzel a kiskereskedők segíthetnek a vevőknek abban, hogy könnyebben megtalálják azt, amit akarnak.</span><span class="sxs-lookup"><span data-stu-id="1b10a-106">By making "shop similar description" recommendations available for all retail channels in Commerce, retailers can help customers easily find what they want.</span></span>

<span data-ttu-id="1b10a-107">A „hasonló megvásárlása leírás” javaslatok a termékek képeit és leírásait használják a megtekintett termékek változataiban ahhoz, hogy találatot adjanak és javasoljanak vizuálisan hasonló termékeket a kiskereskedők termékkatalógusaiból.</span><span class="sxs-lookup"><span data-stu-id="1b10a-107">The functionality for "shop similar description" recommendations uses the product name and description of seed products to find and recommend similar products in a retailer's product catalog.</span></span>

<span data-ttu-id="1b10a-108">A „hasonló megvásárlása leírás” javaslatlisták elérhetők mind a pénztárnál (POS), mind az e-kereskedelmi felületeken.</span><span class="sxs-lookup"><span data-stu-id="1b10a-108">"Shop similar description" recommendations are available in both the point of sale (POS) and e-commerce experiences.</span></span>

## <a name="example-scenarios"></a><span data-ttu-id="1b10a-109">Példaforgatókönyvek</span><span class="sxs-lookup"><span data-stu-id="1b10a-109">Example scenarios</span></span>

<span data-ttu-id="1b10a-110">A következő példaforgatókönyvek azokat a javaslattípusokat mutatják be, amelyeket a „hasonló megvásárlása leírás” funkció nyújthat:</span><span class="sxs-lookup"><span data-stu-id="1b10a-110">The following example scenarios show the types of recommendations that the "shop similar description" functionality can provide:</span></span>

- <span data-ttu-id="1b10a-111">Egy vevő megtekint egy retró stílusú szarukeretes szemüveget, és egy sor ajánlást kap más, hasonló kialakítású szemüvegekre vonatkozóan a kiskereskedői kínálatból.</span><span class="sxs-lookup"><span data-stu-id="1b10a-111">A customer views a pair of retro-style horn-rimmed glasses and receives a set of recommendations for other glasses that have a similar design, in the context of the retailer's industry.</span></span>
- <span data-ttu-id="1b10a-112">Egy vevő a „hasonló megvásárlása leírás” javaslatokat használja olyan kávéízek keresésére, amelyek hasonlóak ízben ahhoz, amelyet korábban vásárolt a kiskereskedőtől.</span><span class="sxs-lookup"><span data-stu-id="1b10a-112">A customer uses "shop similar description" recommendations to discover coffee flavors that are similar to a flavor that they previously purchased from the retailer.</span></span>

## <a name="set-up-shop-similar-description-recommendations"></a><span data-ttu-id="1b10a-113">„Hasonló megvásárlása leírás” javaslatok beállítása</span><span class="sxs-lookup"><span data-stu-id="1b10a-113">Set up "shop similar description" recommendations</span></span>

<span data-ttu-id="1b10a-114">A termékjavaslatok funkció csak azoknak a Commerce-ügyfeleknek támogatott, akik a tárhelyüket az Azure Data Lake Storage Gen2 szolgáltatásba telepítették.</span><span class="sxs-lookup"><span data-stu-id="1b10a-114">Product recommendations are supported only for Commerce users who have migrated their storage to Azure Data Lake Storage Gen2.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="1b10a-115">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="1b10a-115">Prerequisites</span></span>

<span data-ttu-id="1b10a-116">Mielőtt a „hasonló megvásárlása leírás” javaslatok megjeleníthetők a vevőknek, a következő előfeltételeknek kell megfelelnie:</span><span class="sxs-lookup"><span data-stu-id="1b10a-116">Before "shop similar description" recommendations can be shown to customers, you must complete the following prerequisites:</span></span>

- <span data-ttu-id="1b10a-117">[Termék ajánlásainak engedélyezése ](enable-product-recommendations.md)a Commerce Headquarters alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="1b10a-117">[Enable product recommendations](enable-product-recommendations.md) in Commerce headquarters.</span></span>
- <span data-ttu-id="1b10a-118">Győződjön meg róla, hogy a médiakiszolgáló támogatja a HTTPS-hívásokat.</span><span class="sxs-lookup"><span data-stu-id="1b10a-118">Confirm that the media server supports HTTPS calls.</span></span>

### <a name="turn-on-the-shop-similar-description-recommendations-feature"></a><span data-ttu-id="1b10a-119">„Hasonló megvásárlása leírás” javaslatok funkció bekapcsolása</span><span class="sxs-lookup"><span data-stu-id="1b10a-119">Turn on the "shop similar description" recommendations feature</span></span>

<span data-ttu-id="1b10a-120">Ha be szeretné kapcsolni a Commerce központi felületén a „hasonló megvásárlása leírás” ajánlások funkciót, kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="1b10a-120">To turn on the "shop similar description" recommendations feature in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="1b10a-121">A **Funkciókezelés** munkaterületen az elérhető funkciók listájában keresse meg és válassza ki a **Hasonló megvásárlása leírás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1b10a-121">In the **Feature management** workspace, in the list of available features, search for and select **Shop similar description**.</span></span>
1. <span data-ttu-id="1b10a-122">A jobb oldali panelen válassza ki az **Engedélyezés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1b10a-122">In the right pane, select **Enable**.</span></span>

> [!NOTE]
> <span data-ttu-id="1b10a-123">A funkció bekapcsolásakor a rendszer elkezdi létrehozni a termékajánlási listákat.</span><span class="sxs-lookup"><span data-stu-id="1b10a-123">When you turn on the feature, the system starts to generate product recommendation lists.</span></span> <span data-ttu-id="1b10a-124">Megtörténhet, hogy akár egy napot is igénybe vesz, amíg a listák elérhetővé és láthatóvá válnak az online felületen és a pénztárterminálokon.</span><span class="sxs-lookup"><span data-stu-id="1b10a-124">It might take up to a day for those lists to become available and visible online and on POS terminals.</span></span>
>
> <span data-ttu-id="1b10a-125">Ha kikapcsolja a funkciót, a termékjavaslatok más típusait ez nem érinti.</span><span class="sxs-lookup"><span data-stu-id="1b10a-125">If you turn off the feature, other types of product recommendations aren't affected.</span></span> <span data-ttu-id="1b10a-126">A termékajánlásokkal kapcsolatos további tudnivalókat lásd: [Termékajánlások áttekintése](product-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="1b10a-126">For more information about product recommendations, see [Product recommendations overview](product-recommendations.md).</span></span>

## <a name="add-a-shop-similar-description-button-to-product-details-pages"></a><span data-ttu-id="1b10a-127">Hasonló megvásárlása leírás hozzáadása a termékadatok oldalaihoz</span><span class="sxs-lookup"><span data-stu-id="1b10a-127">Add a Shop similar description button to product details pages</span></span>

<span data-ttu-id="1b10a-128">Miután bekapcsolta a Hasonló megvásárlása leírás javaslatok funkciót a Commerce központi felületén, a Commerce webhelykészítő lehetővé teszi, hogy hozzáadjon **Hasonló megvásárlása leírás** gombot a vásárlásmezőhöz bármely termék adatlapján (PDP).</span><span class="sxs-lookup"><span data-stu-id="1b10a-128">After you turn on the "shop similar description" recommendations feature in Commerce headquarters, you can add a **Shop similar description** button to the buy box on any product details page (PDP).</span></span> <span data-ttu-id="1b10a-129">A gombot kiválasztó vevő egy erre dedikált **Hasonló megvásárlása leírás** oldalra kerül, ahol vizuálisan hasonló termékek jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="1b10a-129">A customer who selects this button is taken to a dedicated **Shop similar description** page that shows visually similar products.</span></span> <span data-ttu-id="1b10a-130">Itt a vevő használhatja a választókat a termékek szűrésére.</span><span class="sxs-lookup"><span data-stu-id="1b10a-130">The customer can then use selectors to further filter the products.</span></span>

<span data-ttu-id="1b10a-131">Ahhoz, hogy a **Hasonló megvásárlása leírás** gombot hozzáadja a PDP-hez a Commerce webhelykészítő segítségével, kövesse ezeket a lépéseket.</span><span class="sxs-lookup"><span data-stu-id="1b10a-131">To add a **Shop similar description** button to a PDP by using Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="1b10a-132">Nyisson meg egy már meglévő webhelykészítő lapot, ami vásárlásmező modult tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="1b10a-132">Open an existing site builder page that contains a buy box module.</span></span>
1. <span data-ttu-id="1b10a-133">A bal oldali navigációs ablakban válassza ki a vásárlásmező modult.</span><span class="sxs-lookup"><span data-stu-id="1b10a-133">In the left navigation pane, select the buy box module.</span></span>
1. <span data-ttu-id="1b10a-134">A jobb oldali navigációs ablakban jelölje be a **Hasonló megvásárlása hivatkozás engedélyezése** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="1b10a-134">In the right pane, select the **Enable Shop Similar description Link** check box.</span></span>
1. <span data-ttu-id="1b10a-135">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1b10a-135">Select **Save**.</span></span>
1. <span data-ttu-id="1b10a-136">Válassza a **Szerkesztés befejezése** parancsot az oldal ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.</span><span class="sxs-lookup"><span data-stu-id="1b10a-136">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span> <span data-ttu-id="1b10a-137">Az oldal közzététele után a PDP tartalmazni fogja a **Hasonló megvásárlása leírás** gombot.</span><span class="sxs-lookup"><span data-stu-id="1b10a-137">After the page is published, the PDP will include a **Shop similar description** button.</span></span>

<span data-ttu-id="1b10a-138">A következő ábra bemutatja a **Hasonló megvásárlása hivatkozás engedélyezése** jelölőnégyzetet, és a **Hasonló megvásárlása leírás** gombot egy PDP-oldalon a webhelykészítőben.</span><span class="sxs-lookup"><span data-stu-id="1b10a-138">The following illustration shows the **Enable shop similar description Link** check box and the **Shop similar description** button on an example PDP in site builder.</span></span>

![A Hasonló megvásárlása hivatkozás engedélyezése jelölőnégyzeten és Hasonló megvásárlása leírás gomb egy PDP-oldalon a webhelykészítőben](./media/ter_site_builder_buybox_button.png)

## <a name="additional-resources"></a><span data-ttu-id="1b10a-140">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="1b10a-140">Additional resources</span></span>

[<span data-ttu-id="1b10a-141">Termékajánlatok áttekintése</span><span class="sxs-lookup"><span data-stu-id="1b10a-141">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="1b10a-142">Az Azure Data Lake Storage engedélyezése a Dynamics 365 Commerce környezetben</span><span class="sxs-lookup"><span data-stu-id="1b10a-142">Enable Azure Data Lake Storage in a Dynamics 365 Commerce environment</span></span>](enable-adls-environment.md)

[<span data-ttu-id="1b10a-143">Termékajánlatok engedélyezése</span><span class="sxs-lookup"><span data-stu-id="1b10a-143">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="1b10a-144">„Hasonló szettek vásárlása” javaslatok engedélyezése</span><span class="sxs-lookup"><span data-stu-id="1b10a-144">Enable "shop similar looks" recommendations</span></span>](shop-similar-looks.md)

[<span data-ttu-id="1b10a-145">AI-ML ajánlások eredményeinek helyesbítése</span><span class="sxs-lookup"><span data-stu-id="1b10a-145">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="1b10a-146">Válogatott ajánlások manuális létrehozása</span><span class="sxs-lookup"><span data-stu-id="1b10a-146">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="1b10a-147">Termékajánlatok GYIK-je</span><span class="sxs-lookup"><span data-stu-id="1b10a-147">Product recommendations FAQ</span></span>](faq-recommendations.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]