---
title: Leiratkozás a személyre szabott ajánlatokról
description: Ez a témakör azt mutatja be, hogyan teheti lehetővé az ügyfeleinek a személyre szabott ajánlatok fogadásáról való leiratkozást a Microsoft Dynamics 365 Commerce alkalmazásban.
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
ms.openlocfilehash: 8e7b800218f68167901d86d61ae483680a04cfab
ms.sourcegitcommit: b5ecde955a69f577de46e7db10e89caaedeb2b49
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/04/2020
ms.locfileid: "3025252"
---
# <a name="opt-out-of-personalized-recommendations"></a><span data-ttu-id="b361e-103">Leiratkozás a személyre szabott ajánlatokról</span><span class="sxs-lookup"><span data-stu-id="b361e-103">Opt out of personalized recommendations</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="b361e-104">Ez a témakör azt mutatja be, hogyan teheti lehetővé az ügyfeleinek a személyre szabott ajánlatok fogadásáról való leiratkozást a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="b361e-104">This topic explains how you can let customers opt out of receiving personalized recommendations in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="b361e-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="b361e-105">Overview</span></span>

<span data-ttu-id="b361e-106">A fiók létrehozása során az új vásárlók számára automatikusan be van állítva a személyre szabott ajánlatok fogadására.</span><span class="sxs-lookup"><span data-stu-id="b361e-106">During account creation, new customers are automatically set up to receive personalized recommendations.</span></span> <span data-ttu-id="b361e-107">A Dynamics 365 Commerce azonban többféle módszert kínál a kereskedőknek, amellyel felhasználóik számára lehetővé tehetik az ezen ajánlások fogadásáról való leiratkozást és a személyes adatok feldolgozásának korlátozását.</span><span class="sxs-lookup"><span data-stu-id="b361e-107">However, Dynamics 365 Commerce provides various ways for retailers to let users opt out of receiving these recommendations and restrict the processing of their personal data.</span></span> <span data-ttu-id="b361e-108">A személyre szabott ajánlások fogadásáról leiratkozott hitelesített felhasználóknak esetében azonnal leáll a személyre szabott listák megelenítése.</span><span class="sxs-lookup"><span data-stu-id="b361e-108">Authenticated users who opt out of receiving personalized recommendations will immediately stop seeing personalized lists.</span></span> <span data-ttu-id="b361e-109">Ezenkívül a személyre szabáshoz gyűjtött összes személyes adat el lesz távolítva a személyre szabott ajánlások modelljeiből.</span><span class="sxs-lookup"><span data-stu-id="b361e-109">Additionally, all personal data that is collected for personalization will be removed from personalized recommendations models.</span></span>

<span data-ttu-id="b361e-110">Ha további tájékoztatást szeretne arról, hogyan lehet személyre szabott termékajánlásokat kapni, lásd: [Személyre szabott ajánlatok engedélyezése](personalized-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="b361e-110">For more information about personalized product recommendations, see [Enable personalized recommendations](personalized-recommendations.md).</span></span>

## <a name="ways-for-retailers-to-implement-an-opt-out-experience"></a><span data-ttu-id="b361e-111">A leiratkozási élmény megvalósítási módjai a kereskedők számára</span><span class="sxs-lookup"><span data-stu-id="b361e-111">Ways for retailers to implement an opt-out experience</span></span>

<span data-ttu-id="b361e-112">A leiratkozási élményt a kerekedők háromféle módon tudják megvalósítani.</span><span class="sxs-lookup"><span data-stu-id="b361e-112">Retailers have three ways to implement an opt-out experience.</span></span>

### <a name="opting-out-on-behalf-of-users"></a><span data-ttu-id="b361e-113">Leiratkozás a felhasználók nevében</span><span class="sxs-lookup"><span data-stu-id="b361e-113">Opting out on behalf of users</span></span>

<span data-ttu-id="b361e-114">A Commerce háttérrendszer Fiókkezelés részében a kereskedők elvégezhetik a leiratkozást a felhasználók nevében.</span><span class="sxs-lookup"><span data-stu-id="b361e-114">In Account management in Commerce back office, retailers can opt out on behalf of users.</span></span>

1. <span data-ttu-id="b361e-115">A háttérrendszer kezdőoldaláról keressen rá az **összes vevőre**.</span><span class="sxs-lookup"><span data-stu-id="b361e-115">From the back-office home page, search for **all customers**.</span></span>
1. <span data-ttu-id="b361e-116">Keressen meg és válasszon ki egy vevőt, majd válassza ki a **Kiskereskedelem** gyorslapot.</span><span class="sxs-lookup"><span data-stu-id="b361e-116">Search for and select a customer, and then select the **Retail** FastTab.</span></span>

    ![Kiskereskedelem gyorslap](./media/Disablepersonalizationpart1.png)

1. <span data-ttu-id="b361e-118">Az **Adatvédelem** alatt állítsa a **Személyre szabás letiltása** beállítást **Igen**értékre.</span><span class="sxs-lookup"><span data-stu-id="b361e-118">Under **Privacy**, set the **Disable personalization** option to **Yes**.</span></span>

    ![Adatvédelmi beállítások](./media/Disablepersonalizationpart2.png)

1. <span data-ttu-id="b361e-120">Válassza a **Mentés** gombot, és zárja be az oldalt.</span><span class="sxs-lookup"><span data-stu-id="b361e-120">Select **Save**, and close the page.</span></span>

### <a name="module-based-opt-out-experience"></a><span data-ttu-id="b361e-121">Modulalapú leiratkozási élmény</span><span class="sxs-lookup"><span data-stu-id="b361e-121">Module-based opt-out experience</span></span>

<span data-ttu-id="b361e-122">A kereskedők lehetővé tehetik a hitelesített felhasználók számára, hogy saját maguk iratkozzanak le a személyre szabott ajánlásokról.</span><span class="sxs-lookup"><span data-stu-id="b361e-122">Retailers can let authenticated users opt out of personalized recommendations by themselves.</span></span> <span data-ttu-id="b361e-123">Ennek a leiratkozási élménynek a biztosításához adja hozzá a leiratkozási modult a vásárlói fiók profiloldalaihoz.</span><span class="sxs-lookup"><span data-stu-id="b361e-123">To provide this opt-out experience, add the user opt-out module to customer account profile pages.</span></span>

### <a name="custom-extensions"></a><span data-ttu-id="b361e-124">Egyéni bővítmények</span><span class="sxs-lookup"><span data-stu-id="b361e-124">Custom extensions</span></span>

<span data-ttu-id="b361e-125">A kereskedők saját bővítményeiket hozhatnak létre a felhasználók leiratkozási élményének kezeléséhez.</span><span class="sxs-lookup"><span data-stu-id="b361e-125">Retailers can create their own extensions to manage the opt-out experience for users.</span></span> <span data-ttu-id="b361e-126">További információk: [Retail Server API-k hívása](e-commerce-extensibility/call-retail-server-apis.md) és [Online csatorna bővíthetősége](e-commerce-extensibility/overview.md).</span><span class="sxs-lookup"><span data-stu-id="b361e-126">For more information, see [Call Retail Server APIs](e-commerce-extensibility/call-retail-server-apis.md) and [Online channel extensibility](e-commerce-extensibility/overview.md).</span></span>

## <a name="obtain-a-digital-copy-of-personalized-recommendations-data-on-behalf-of-an-authenticated-user"></a><span data-ttu-id="b361e-127">Személyre szabott ajánlási adatok digitális másolatának beolvasása egy hitelesített felhasználó nevében</span><span class="sxs-lookup"><span data-stu-id="b361e-127">Obtain a digital copy of personalized recommendations data on behalf of an authenticated user</span></span>

<span data-ttu-id="b361e-128">Előfordulhat, hogy a vevők a személyes adataik digitális másolatát szeretnék beszerezni, és meg szeretnék tekinteni az ajánlásaik eredményeinek exportált nézetét is.</span><span class="sxs-lookup"><span data-stu-id="b361e-128">Customers might want to obtain a digital copy of their personal data and also see an exported view of their recommendations results.</span></span> <span data-ttu-id="b361e-129">Ha egy vevő igényli ezeket az adatokat, akkor a kiskereskedőnek létre kell hoznia egy testreszabott kiterjesztést, amely meghívja a Retail Server alkalmazásprogramozási felületét (API), és lekérdezi az **Önnek ajánljuk** lista összes eredményét a vevő vevői azonosítója alapján.</span><span class="sxs-lookup"><span data-stu-id="b361e-129">If a customer requests this information, the retailer must create a customized extension that calls the Retail Server application programming interface (API) and queries for the full results from the **Picks for you** list, based on the customer's customer ID.</span></span> <span data-ttu-id="b361e-130">Ezután az eredmények vesszővel tagolt értékek (CSV) formátumban exportálhatók és a vevővel megoszthatók.</span><span class="sxs-lookup"><span data-stu-id="b361e-130">The results can then be exported in comma-separated values (CSV) format and shared with the customer.</span></span>

<span data-ttu-id="b361e-131">A következő példa azt mutatja be, hogyan hajthatja végre egy kiskereskedő ezt a feladatot.</span><span class="sxs-lookup"><span data-stu-id="b361e-131">The following example shows how a retailer can accomplish this task.</span></span>

1. <span data-ttu-id="b361e-132">A kiskereskedő létrehoz egy egyéni bővítményt a személyes ajánlások adatainak lekéréséhez a felhasználó nevében.</span><span class="sxs-lookup"><span data-stu-id="b361e-132">The retailer creates a custom extension to pull personal recommendations data on behalf of the user.</span></span> <span data-ttu-id="b361e-133">A modulok létrehozásával, a meglévő modulok klónozásával, a Retail Server API-k hívásával és a hívási adatokkal kapcsolatos további tudnivalókat lásd: [Online csatorna bővíthetősége](e-commerce-extensibility/overview.md).</span><span class="sxs-lookup"><span data-stu-id="b361e-133">For information about how to create modules, clone existing modules, call Retail Server APIs, and call data actions, see [Online channel extensibility](e-commerce-extensibility/overview.md).</span></span>
2. <span data-ttu-id="b361e-134">Az egyéni bővítmény hívást indít a **get-recommendations** alapadat-művelethez, és átadja a szükséges információkat a lista követelményei alapján.</span><span class="sxs-lookup"><span data-stu-id="b361e-134">The custom extension makes a call to the **get-recommendations** core data action and passes the required information to it, based on the requirements of the list.</span></span> <span data-ttu-id="b361e-135">Az **Önnek ajánljuk** lista esetében a bűvítménynek át kell adnia a helyes listanevet és a vevő ügyfél azonosítóját az adatműveletnek.</span><span class="sxs-lookup"><span data-stu-id="b361e-135">In the case of the **Picks for you** list, the extension must pass the correct list name and customer ID to the data action.</span></span>

    <span data-ttu-id="b361e-136">Az egyéni bővítmény létrehozásához egyik módja az ajánlási eredmények visszaadására szolgáló, meglévő termékgyűjtő modul klónozása.</span><span class="sxs-lookup"><span data-stu-id="b361e-136">One way to create the custom extension is to clone the existing product collection module that is used to return recommendations results.</span></span> <span data-ttu-id="b361e-137">A meglévő modul klónozásával a kiskereskedő módosíthatja a meglévő kódot, és hozzáadhat egy új gombot, amely az ajánlatok eredményeit CSV-fájlba exportálja.</span><span class="sxs-lookup"><span data-stu-id="b361e-137">By cloning this existing module, a retailer can modify the existing code and add a new button that exports the recommendations results to a CSV file.</span></span> <span data-ttu-id="b361e-138">További információk: [Kezdő csomag moduljának klónozása](e-commerce-extensibility/clone-starter-module.md) és [Termékgyűjtési modulok](product-collection-module-overview.md).</span><span class="sxs-lookup"><span data-stu-id="b361e-138">For more information, see [Clone a starter kit module](e-commerce-extensibility/clone-starter-module.md) and [Product collection modules](product-collection-module-overview.md).</span></span>

    <span data-ttu-id="b361e-139">A Retail Server API-függvénytár teljes nézetét lásd: [Retail Server ügyfél és fogyasztói API-k](dev-itpro/retail-server-customer-consumer-api.md).</span><span class="sxs-lookup"><span data-stu-id="b361e-139">For a full view of the Retail Server API library, see [Retail Server Customer and Consumer APIs](dev-itpro/retail-server-customer-consumer-api.md).</span></span>

3. <span data-ttu-id="b361e-140">Miután létrehozta az egyéni bővítményt, a kiskereskedő a hitelesített felhasználó egyedi vevői azonosítója alapján exportálhatja az összes ajánlási eredmény CSV-fájlját.</span><span class="sxs-lookup"><span data-stu-id="b361e-140">After the custom extension is created, the retailer can export a CSV file of all recommendations results, based on the unique customer ID of the authenticated user.</span></span>
4. <span data-ttu-id="b361e-141">A kiskereskedő megoszthatja a hitelesített felhasználóval az exportált CSV-fájlt, amely által ajánlott termékek teljes személyre szabott listáját tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="b361e-141">The retailer can share the exported CSV file that contains the full personalized list of recommended products with the authenticated user.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b361e-142">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="b361e-142">Additional resources</span></span>

[<span data-ttu-id="b361e-143">Termékajánlatok áttekintése</span><span class="sxs-lookup"><span data-stu-id="b361e-143">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="b361e-144">Termékajánlatok engedélyezése</span><span class="sxs-lookup"><span data-stu-id="b361e-144">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="b361e-145">Személyre szabott ajánlatok engedélyezése</span><span class="sxs-lookup"><span data-stu-id="b361e-145">Enable personalized recommendations</span></span>](personalized-recommendations.md)

[<span data-ttu-id="b361e-146">Termékjavaslat-listák hozzáadása az oldalakhoz</span><span class="sxs-lookup"><span data-stu-id="b361e-146">Add product recommendation lists to pages</span></span>](add-reco-list-to-page.md)

[<span data-ttu-id="b361e-147">Ajánlások panel hozzáadása a pénztáreszközökhöz</span><span class="sxs-lookup"><span data-stu-id="b361e-147">Add recommendations panel to POS devices</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="b361e-148">Termékgyűjtési modul áttekintése</span><span class="sxs-lookup"><span data-stu-id="b361e-148">Product collection module overview</span></span>](product-collection-module-overview.md)
