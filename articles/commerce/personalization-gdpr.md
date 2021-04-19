---
title: Leiratkozás a személyre szabott ajánlatokról
description: Ez a témakör azt mutatja be, hogyan teheti lehetővé az ügyfeleinek a személyre szabott ajánlatok fogadásáról való leiratkozást a Microsoft Dynamics 365 Commerce alkalmazásban.
author: bebeale
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
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
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 1e7d0f505ce49bc9be0d027cbb0d636c9de0600b
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5804453"
---
# <a name="opt-out-of-personalized-recommendations"></a><span data-ttu-id="cc181-103">Személyre szabott ajánlatok kikapcsolása</span><span class="sxs-lookup"><span data-stu-id="cc181-103">Opt out of personalized recommendations</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="cc181-104">Ez a témakör azt mutatja be, hogyan teheti lehetővé az ügyfeleinek a személyre szabott ajánlatok fogadásáról való leiratkozást a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="cc181-104">This topic explains how you can let customers opt out of receiving personalized recommendations in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="cc181-105">A fiók létrehozása során az új vásárlók számára automatikusan be van állítva a személyre szabott ajánlatok fogadására.</span><span class="sxs-lookup"><span data-stu-id="cc181-105">During account creation, new customers are automatically set up to receive personalized recommendations.</span></span> <span data-ttu-id="cc181-106">A Dynamics 365 Commerce azonban többféle módszert kínál a kereskedőknek, amellyel felhasználóik számára lehetővé tehetik az ezen ajánlások fogadásáról való leiratkozást és a személyes adatok feldolgozásának korlátozását.</span><span class="sxs-lookup"><span data-stu-id="cc181-106">However, Dynamics 365 Commerce provides various ways for retailers to let users opt out of receiving these recommendations and restrict the processing of their personal data.</span></span> <span data-ttu-id="cc181-107">A személyre szabott ajánlások fogadásáról leiratkozott hitelesített felhasználóknak esetében azonnal leáll a személyre szabott listák megelenítése.</span><span class="sxs-lookup"><span data-stu-id="cc181-107">Authenticated users who opt out of receiving personalized recommendations will immediately stop seeing personalized lists.</span></span> <span data-ttu-id="cc181-108">Ezenkívül a személyre szabáshoz gyűjtött összes személyes adat el lesz távolítva a személyre szabott ajánlások modelljeiből.</span><span class="sxs-lookup"><span data-stu-id="cc181-108">Additionally, all personal data that is collected for personalization will be removed from personalized recommendations models.</span></span>

<span data-ttu-id="cc181-109">Ha további tájékoztatást szeretne arról, hogyan lehet személyre szabott termékajánlásokat kapni, lásd: [Személyre szabott ajánlatok engedélyezése](personalized-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="cc181-109">For more information about personalized product recommendations, see [Enable personalized recommendations](personalized-recommendations.md).</span></span>

## <a name="ways-for-retailers-to-implement-an-opt-out-experience"></a><span data-ttu-id="cc181-110">A leiratkozási élmény megvalósítási módjai a kereskedők számára</span><span class="sxs-lookup"><span data-stu-id="cc181-110">Ways for retailers to implement an opt-out experience</span></span>

<span data-ttu-id="cc181-111">A leiratkozási élményt a kerekedők háromféle módon tudják megvalósítani.</span><span class="sxs-lookup"><span data-stu-id="cc181-111">Retailers have three ways to implement an opt-out experience.</span></span>

### <a name="opting-out-on-behalf-of-users"></a><span data-ttu-id="cc181-112">Leiratkozás a felhasználók nevében</span><span class="sxs-lookup"><span data-stu-id="cc181-112">Opting out on behalf of users</span></span>

<span data-ttu-id="cc181-113">A Commerce háttérrendszer Fiókkezelés részében a kereskedők elvégezhetik a leiratkozást a felhasználók nevében.</span><span class="sxs-lookup"><span data-stu-id="cc181-113">In Account management in Commerce back office, retailers can opt out on behalf of users.</span></span>

1. <span data-ttu-id="cc181-114">A háttérrendszer kezdőoldaláról keressen rá az **összes vevőre**.</span><span class="sxs-lookup"><span data-stu-id="cc181-114">From the back-office home page, search for **all customers**.</span></span>
1. <span data-ttu-id="cc181-115">Keressen meg és válasszon ki egy vevőt, majd válassza ki a **Kiskereskedelem** gyorslapot.</span><span class="sxs-lookup"><span data-stu-id="cc181-115">Search for and select a customer, and then select the **Retail** FastTab.</span></span>

    ![Kiskereskedelem gyorslap](./media/Disablepersonalizationpart1.png)

1. <span data-ttu-id="cc181-117">Az **Adatvédelem** alatt állítsa a **Személyre szabás letiltása** beállítást **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="cc181-117">Under **Privacy**, set the **Disable personalization** option to **Yes**.</span></span>

    ![Adatvédelmi beállítások](./media/Disablepersonalizationpart2.png)

1. <span data-ttu-id="cc181-119">Válassza a **Mentés** gombot, és zárja be az oldalt.</span><span class="sxs-lookup"><span data-stu-id="cc181-119">Select **Save**, and close the page.</span></span>

### <a name="module-based-opt-out-experience"></a><span data-ttu-id="cc181-120">Modulalapú leiratkozási élmény</span><span class="sxs-lookup"><span data-stu-id="cc181-120">Module-based opt-out experience</span></span>

<span data-ttu-id="cc181-121">A kereskedők lehetővé tehetik a hitelesített felhasználók számára, hogy saját maguk iratkozzanak le a személyre szabott ajánlásokról.</span><span class="sxs-lookup"><span data-stu-id="cc181-121">Retailers can let authenticated users opt out of personalized recommendations by themselves.</span></span> <span data-ttu-id="cc181-122">Ennek a leiratkozási élménynek a biztosításához adja hozzá a leiratkozási modult a vásárlói fiók profiloldalaihoz.</span><span class="sxs-lookup"><span data-stu-id="cc181-122">To provide this opt-out experience, add the user opt-out module to customer account profile pages.</span></span>

### <a name="custom-extensions"></a><span data-ttu-id="cc181-123">Egyéni bővítmények</span><span class="sxs-lookup"><span data-stu-id="cc181-123">Custom extensions</span></span>

<span data-ttu-id="cc181-124">A kereskedők saját bővítményeiket hozhatnak létre a felhasználók leiratkozási élményének kezeléséhez.</span><span class="sxs-lookup"><span data-stu-id="cc181-124">Retailers can create their own extensions to manage the opt-out experience for users.</span></span> <span data-ttu-id="cc181-125">További információk: [Retail Server API-k hívása](e-commerce-extensibility/call-retail-server-apis.md) és [Online csatorna bővíthetősége](e-commerce-extensibility/overview.md).</span><span class="sxs-lookup"><span data-stu-id="cc181-125">For more information, see [Call Retail Server APIs](e-commerce-extensibility/call-retail-server-apis.md) and [Online channel extensibility](e-commerce-extensibility/overview.md).</span></span>

## <a name="obtain-a-digital-copy-of-personalized-recommendations-data-on-behalf-of-an-authenticated-user"></a><span data-ttu-id="cc181-126">Személyre szabott ajánlási adatok digitális másolatának beolvasása egy hitelesített felhasználó nevében</span><span class="sxs-lookup"><span data-stu-id="cc181-126">Obtain a digital copy of personalized recommendations data on behalf of an authenticated user</span></span>

<span data-ttu-id="cc181-127">Előfordulhat, hogy a vevők a személyes adataik digitális másolatát szeretnék beszerezni, és meg szeretnék tekinteni az ajánlásaik eredményeinek exportált nézetét is.</span><span class="sxs-lookup"><span data-stu-id="cc181-127">Customers might want to obtain a digital copy of their personal data and also see an exported view of their recommendations results.</span></span> <span data-ttu-id="cc181-128">Ha egy vevő igényli ezeket az adatokat, akkor a kiskereskedőnek létre kell hoznia egy testreszabott kiterjesztést, amely meghívja a Retail Server alkalmazásprogramozási felületét (API), és lekérdezi az **Önnek ajánljuk** lista összes eredményét a vevő vevői azonosítója alapján.</span><span class="sxs-lookup"><span data-stu-id="cc181-128">If a customer requests this information, the retailer must create a customized extension that calls the Retail Server application programming interface (API) and queries for the full results from the **Picks for you** list, based on the customer's customer ID.</span></span> <span data-ttu-id="cc181-129">Ezután az eredmények vesszővel tagolt értékek (CSV) formátumban exportálhatók és a vevővel megoszthatók.</span><span class="sxs-lookup"><span data-stu-id="cc181-129">The results can then be exported in comma-separated values (CSV) format and shared with the customer.</span></span>

<span data-ttu-id="cc181-130">A következő példa azt mutatja be, hogyan hajthatja végre egy kiskereskedő ezt a feladatot.</span><span class="sxs-lookup"><span data-stu-id="cc181-130">The following example shows how a retailer can accomplish this task.</span></span>

1. <span data-ttu-id="cc181-131">A kiskereskedő létrehoz egy egyéni bővítményt a személyes ajánlások adatainak lekéréséhez a felhasználó nevében.</span><span class="sxs-lookup"><span data-stu-id="cc181-131">The retailer creates a custom extension to pull personal recommendations data on behalf of the user.</span></span> <span data-ttu-id="cc181-132">A modulok létrehozásával, a meglévő modulok klónozásával, a Retail Server API-k hívásával és a hívási adatokkal kapcsolatos további tudnivalókat lásd: [Online csatorna bővíthetősége](e-commerce-extensibility/overview.md).</span><span class="sxs-lookup"><span data-stu-id="cc181-132">For information about how to create modules, clone existing modules, call Retail Server APIs, and call data actions, see [Online channel extensibility](e-commerce-extensibility/overview.md).</span></span>
2. <span data-ttu-id="cc181-133">Az egyéni bővítmény hívást indít a **get-recommendations** alapadat-művelethez, és átadja a szükséges információkat a lista követelményei alapján.</span><span class="sxs-lookup"><span data-stu-id="cc181-133">The custom extension makes a call to the **get-recommendations** core data action and passes the required information to it, based on the requirements of the list.</span></span> <span data-ttu-id="cc181-134">Az **Önnek ajánljuk** lista esetében a bűvítménynek át kell adnia a helyes listanevet és a vevő ügyfél azonosítóját az adatműveletnek.</span><span class="sxs-lookup"><span data-stu-id="cc181-134">In the case of the **Picks for you** list, the extension must pass the correct list name and customer ID to the data action.</span></span>

    <span data-ttu-id="cc181-135">Az egyéni bővítmény létrehozásához egyik módja az ajánlási eredmények visszaadására szolgáló, meglévő termékgyűjtő modul klónozása.</span><span class="sxs-lookup"><span data-stu-id="cc181-135">One way to create the custom extension is to clone the existing product collection module that is used to return recommendations results.</span></span> <span data-ttu-id="cc181-136">A meglévő modul klónozásával a kiskereskedő módosíthatja a meglévő kódot, és hozzáadhat egy új gombot, amely az ajánlatok eredményeit CSV-fájlba exportálja.</span><span class="sxs-lookup"><span data-stu-id="cc181-136">By cloning this existing module, a retailer can modify the existing code and add a new button that exports the recommendations results to a CSV file.</span></span> <span data-ttu-id="cc181-137">További információk: [Modulkönyvtár moduljának klónozása](e-commerce-extensibility/clone-starter-module.md) és [Termékgyűjtési modulok](product-collection-module-overview.md).</span><span class="sxs-lookup"><span data-stu-id="cc181-137">For more information, see [Clone a module library module](e-commerce-extensibility/clone-starter-module.md) and [Product collection modules](product-collection-module-overview.md).</span></span>

    <span data-ttu-id="cc181-138">A Retail Server API-függvénytár teljes nézetét lásd: [Retail Server ügyfél és fogyasztói API-k](dev-itpro/retail-server-customer-consumer-api.md).</span><span class="sxs-lookup"><span data-stu-id="cc181-138">For a full view of the Retail Server API library, see [Retail Server Customer and Consumer APIs](dev-itpro/retail-server-customer-consumer-api.md).</span></span>

3. <span data-ttu-id="cc181-139">Miután létrehozta az egyéni bővítményt, a kiskereskedő a hitelesített felhasználó egyedi vevői azonosítója alapján exportálhatja az összes ajánlási eredmény CSV-fájlját.</span><span class="sxs-lookup"><span data-stu-id="cc181-139">After the custom extension is created, the retailer can export a CSV file of all recommendations results, based on the unique customer ID of the authenticated user.</span></span>
4. <span data-ttu-id="cc181-140">A kiskereskedő megoszthatja a hitelesített felhasználóval az exportált CSV-fájlt, amely által ajánlott termékek teljes személyre szabott listáját tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="cc181-140">The retailer can share the exported CSV file that contains the full personalized list of recommended products with the authenticated user.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="cc181-141">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="cc181-141">Additional resources</span></span>

[<span data-ttu-id="cc181-142">Termékajánlatok áttekintése</span><span class="sxs-lookup"><span data-stu-id="cc181-142">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="cc181-143">Az Azure Data Lake Storage engedélyezése a Dynamics 365 Commerce környezetben</span><span class="sxs-lookup"><span data-stu-id="cc181-143">Enable Azure Data Lake Storage in a Dynamics 365 Commerce environment</span></span>](enable-adls-environment.md)

[<span data-ttu-id="cc181-144">Termékajánlatok engedélyezése</span><span class="sxs-lookup"><span data-stu-id="cc181-144">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="cc181-145">Személyre szabott ajánlatok engedélyezése</span><span class="sxs-lookup"><span data-stu-id="cc181-145">Enable personalized recommendations</span></span>](personalized-recommendations.md)

[<span data-ttu-id="cc181-146">A hasonlóak megvásárlására vonatkozó javaslatok engedélyezése</span><span class="sxs-lookup"><span data-stu-id="cc181-146">Enable "shop similar looks" recommendations</span></span>](shop-similar-looks.md)

[<span data-ttu-id="cc181-147">Termékajánlatok hozzáadása a pénztárnál</span><span class="sxs-lookup"><span data-stu-id="cc181-147">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="cc181-148">Ajánlatok hozzáadása a tranzakció képernyőjéhez</span><span class="sxs-lookup"><span data-stu-id="cc181-148">Add recommendations to the transaction screen</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="cc181-149">AI-ML ajánlások eredményeinek helyesbítése</span><span class="sxs-lookup"><span data-stu-id="cc181-149">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="cc181-150">Válogatott ajánlások manuális létrehozása</span><span class="sxs-lookup"><span data-stu-id="cc181-150">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="cc181-151">Ajánlások létrehozása bemutató adatokkal</span><span class="sxs-lookup"><span data-stu-id="cc181-151">Create recommendations with demo data</span></span>](product-recommendations-demo-data.md)

[<span data-ttu-id="cc181-152">Termékajánlatok GYIK-je</span><span class="sxs-lookup"><span data-stu-id="cc181-152">Product recommendations FAQ</span></span>](faq-recommendations.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
