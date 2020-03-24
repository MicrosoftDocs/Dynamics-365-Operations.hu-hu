---
title: Ajánlások létrehozása bemutató adatokkal
description: A dokumentum útmutatást ad a többcsatornás termékajánlásoknak az 1.szintű egyablakos környezetekben történő kihasználásához előre kitöltött, testreszabható demóadatok felhasználásával.
author: bebeale
manager: AnnBe
ms.date: 03/12/20
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: RetailStoreTable, RetailTillLayout
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 260624
ms.assetid: a4f9d315-9951-451c-8ee6-37f9b3b15ef0
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 2e790d78b4d5216822ffda3a3895feb674876bd8
ms.sourcegitcommit: 1e7e7c4bc197b0a42e4d53d2a54600a2fb125b69
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/13/2020
ms.locfileid: "3127836"
---
# <a name="create-recommendations-with-demo-data"></a><span data-ttu-id="dc416-103">Ajánlások létrehozása bemutató adatokkal</span><span class="sxs-lookup"><span data-stu-id="dc416-103">Create recommendations with demo data</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="dc416-104">A dokumentum útmutatást ad a többcsatornás termékajánlásoknak az 1.szintű egyablakos környezetekben történő kihasználásához előre kitöltött, testreszabható demóadatok felhasználásával.</span><span class="sxs-lookup"><span data-stu-id="dc416-104">This document provides guidance on how to leverage omni-channel product recommendations in Tier-1 single box environments using pre-populated, customizable demo data.</span></span>

<span data-ttu-id="dc416-105">A többcsatornás termékajánlások termékek szerkesztők által karbantartott vagy program által generált listájának készletét adják.</span><span class="sxs-lookup"><span data-stu-id="dc416-105">Omni-channel product recommendations provide a set of editorially curated or programmatically generated list of products.</span></span> <span data-ttu-id="dc416-106">Ezek a listák több esetben is használhatók, attól függően, hogy milyen üzleti szükséglet van.</span><span class="sxs-lookup"><span data-stu-id="dc416-106">These lists can be used in several scenarios, depending on the business need.</span></span> <span data-ttu-id="dc416-107">A termékajánlási listákkal kapcsolatos további tudnivalókat lásd: [Termékajánlások áttekintése](product-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="dc416-107">For more information about product recommendation lists, see [Product recommendations overview](product-recommendations.md).</span></span>

<span data-ttu-id="dc416-108">A 2. és magasabb szintű Dynamics 365 környezetekben a termékajánlások automatikusan, a vevői adatok alapján kerülnek kiszámításra.</span><span class="sxs-lookup"><span data-stu-id="dc416-108">For Tier-2 and higher Dynamics 365 environments, product recommendations are automatically computed based on customer data.</span></span> <span data-ttu-id="dc416-109">A termékajánlások demóadatainak használata nem tiltja le a környezetben már kiépített ajánlási megoldásokat, illetve a vonatkozó használati költségeket.</span><span class="sxs-lookup"><span data-stu-id="dc416-109">Using product recommendations demo data does not disable any product recommendations solution already provisioned in the environment and any costs associated with its usage.</span></span>

<span data-ttu-id="dc416-110">Az 1. szintű környezetekben a termékajánlások csak a .csv-fájlban tárolt statikus demóadatokon alapulnak.</span><span class="sxs-lookup"><span data-stu-id="dc416-110">For Tier-1 environments, product recommendations are based only off the static demo data stored in a .csv file.</span></span>

## <a name="enabling-product-recommendations-demo-data-in-an-environment"></a><span data-ttu-id="dc416-111">A termékajánlások demóadatainak engedélyezése egy környezetben</span><span class="sxs-lookup"><span data-stu-id="dc416-111">Enabling product recommendations demo data in an environment</span></span>
<span data-ttu-id="dc416-112">A Dynamics 365 Commerce Preview Demo Extension kiterjesztést a megfelelő környezetre kell telepíteni, hogy automatikusan engedélyezze a termékajánlások demóadatait.</span><span class="sxs-lookup"><span data-stu-id="dc416-112">To enable product recommendations demo date, you need to deploy the Dynamics 365 Commerce Preview Demo Extension to the respective environment.</span></span> <span data-ttu-id="dc416-113">Így automatikusan engedélyezve lesznek a temékjavaslatok demóadatai.</span><span class="sxs-lookup"><span data-stu-id="dc416-113">Doing so automatically enables product recommendations demo data.</span></span>

## <a name="default-demo-data"></a><span data-ttu-id="dc416-114">Alapértelmezett demóadatok</span><span class="sxs-lookup"><span data-stu-id="dc416-114">Default demo data</span></span>
<span data-ttu-id="dc416-115">Minden Onebox típusú környezet rendelkezik egy előre betöltött termékajánlás-demóadat készlettel a vesszővel elválasztott „reco_demo_data.csv” fájlban, amely ugyanabban a mappában található, mint ez a dokumentum a Commerce Scale Unit kiszolgálón.</span><span class="sxs-lookup"><span data-stu-id="dc416-115">Each Onebox type environment comes with a preloaded set of product recommendations demo data stored in the coma separated 'reco_demo_data.csv' file, located on the Commerce Scale Unit.</span></span>

<span data-ttu-id="dc416-116">Ezek az adatok a következő oszlopok mentén strukturáltak.</span><span class="sxs-lookup"><span data-stu-id="dc416-116">The data is structured along the following columns.</span></span>

| <span data-ttu-id="dc416-117">Oszlop neve</span><span class="sxs-lookup"><span data-stu-id="dc416-117">Column name</span></span>         | <span data-ttu-id="dc416-118">Kötelező</span><span class="sxs-lookup"><span data-stu-id="dc416-118">Mandatory</span></span>          | <span data-ttu-id="dc416-119">Leírás</span><span class="sxs-lookup"><span data-stu-id="dc416-119">Description</span></span>                                                                                                                                 | <span data-ttu-id="dc416-120">Lehetséges értékek</span><span class="sxs-lookup"><span data-stu-id="dc416-120">Possible Values</span></span>                                                              |
|---------------------|--------------------|---------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------|
| <span data-ttu-id="dc416-121">RecoList</span><span class="sxs-lookup"><span data-stu-id="dc416-121">RecoList</span></span>            | :heavy_check_mark: | <span data-ttu-id="dc416-123">A konkrét termékajánlási listatípust, amelyre a demóadatok mutatnak, létre kell hozni.</span><span class="sxs-lookup"><span data-stu-id="dc416-123">The specific product recommendation list type that the demo data point is to generate.</span></span>                                                    | <ul><li><span data-ttu-id="dc416-124">RecoBestSelling</span><span class="sxs-lookup"><span data-stu-id="dc416-124">RecoBestSelling</span></span></li><li><span data-ttu-id="dc416-125">RecoNew</span><span class="sxs-lookup"><span data-stu-id="dc416-125">RecoNew</span></span></li><li><span data-ttu-id="dc416-126">RecoTrending</span><span class="sxs-lookup"><span data-stu-id="dc416-126">RecoTrending</span></span></li><li><span data-ttu-id="dc416-127">RecoCart</span><span class="sxs-lookup"><span data-stu-id="dc416-127">RecoCart</span></span></li><li><span data-ttu-id="dc416-128">RecoPeopleAlsoBuy</span><span class="sxs-lookup"><span data-stu-id="dc416-128">RecoPeopleAlsoBuy</span></span></li></ul> |
| <span data-ttu-id="dc416-129">OperatingUnitNumber</span><span class="sxs-lookup"><span data-stu-id="dc416-129">OperatingUnitNumber</span></span> | :heavy_check_mark: | <span data-ttu-id="dc416-131">Az a meghatározott üzemiegység-szám, amelyekben a termékajánlásoknak meg kell jelenniük.</span><span class="sxs-lookup"><span data-stu-id="dc416-131">The specific operating unit number where product recommendations are expected to be   surfaced.</span></span>                                        |                                                                              |
| <span data-ttu-id="dc416-132">Kategória</span><span class="sxs-lookup"><span data-stu-id="dc416-132">Category</span></span>            |                    |    <span data-ttu-id="dc416-133">Az a kategória, amelyhez a megadott lista visszaadandó.</span><span class="sxs-lookup"><span data-stu-id="dc416-133">The category the specific list should be returned for.</span></span> <span data-ttu-id="dc416-134">Ha nincs megadva kategória, akkor a lista csak a navigációs hierarchia elejére kerül.</span><span class="sxs-lookup"><span data-stu-id="dc416-134">If no category is specified, the list is for top of navigation hierarchy only.</span></span>    |                                                                              |
| <span data-ttu-id="dc416-135">SeedItemId</span><span class="sxs-lookup"><span data-stu-id="dc416-135">SeedItemId</span></span>          |                    |    <span data-ttu-id="dc416-136">A kiindulást igénylő listáknál (RecoPeopleAlsoBuy és RecoCart) a terméknél a listán további termékeket kell megjeleníteni.</span><span class="sxs-lookup"><span data-stu-id="dc416-136">For lists that require seed (RecoPeopleAlsoBuy and RecoCart), the product those lists should show additional products for.</span></span>            |                                                                              |
| <span data-ttu-id="dc416-137">ItemIds</span><span class="sxs-lookup"><span data-stu-id="dc416-137">ItemIds</span></span>             | :heavy_check_mark: | <span data-ttu-id="dc416-139">Egy vagy több termék, amelyet eredményként kell visszaküldeni, elválasztva a következővel „;”.</span><span class="sxs-lookup"><span data-stu-id="dc416-139">One or more products to be returned as the result, separated by ';'.</span></span>                                                                  |                                                                              |

## <a name="customize-demo-data"></a><span data-ttu-id="dc416-140">Demóadatok testreszabása</span><span class="sxs-lookup"><span data-stu-id="dc416-140">Customize demo data</span></span>
<span data-ttu-id="dc416-141">Szerkesztheti az alapértelmezett demóadatokat bármilyen termék- és kategóriainformációval, amelyet a HQ konfigurál.</span><span class="sxs-lookup"><span data-stu-id="dc416-141">You can edit the default demo data with any product and category information configured in HQ.</span></span> <span data-ttu-id="dc416-142">A CSV-fájl frissítését követően a vevőknek visszaküldött termékjavaslatokban azonnal megjelennek a módosítások.</span><span class="sxs-lookup"><span data-stu-id="dc416-142">Once you update the .csv, the product recommendations that are returned to customers will immediately reflect the changes.</span></span>

<span data-ttu-id="dc416-143">A kiterjesztés tartalmaz egy „RecoMockDataset.csv” nevű adatfájlt, amely lehetővé teszi, hogy a vevő vezérelje azt az adathalmazt, amely a szimulált ajánlások eredményeinek alkalmazására használt.</span><span class="sxs-lookup"><span data-stu-id="dc416-143">The extension contains a datafile called 'RecoMockDataset.csv' which allows you to control the dataset used to power the mock recommendations results.</span></span> <span data-ttu-id="dc416-144">A fájlnév a kiterjesztéskonfigurációt használva vezérelhető a **ext.Recommendations.DemoFilePath** DemoFilePath beállítás használatával.</span><span class="sxs-lookup"><span data-stu-id="dc416-144">The file name can be controlled through extension configuration using the **ext.Recommendations.DemoFilePath** setting.</span></span> <span data-ttu-id="dc416-145">Ez lehetővé teszi a Önnek, hogy több adatkészlettel rendelkezzen, amelyek között a konfiguráció használatával könnyen lehet váltani.</span><span class="sxs-lookup"><span data-stu-id="dc416-145">This enables you to have multiple datasets available that can be switched between easily through configuration.</span></span>


```xml
<settings>
    <add name="ext.Recommendations.DemoFilePath" value="RecoMockDataset.csv" />
</settings>
```

## <a name="additional-resources"></a><span data-ttu-id="dc416-146">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="dc416-146">Additional Resources</span></span>

[<span data-ttu-id="dc416-147">Termékajánlatok áttekintése</span><span class="sxs-lookup"><span data-stu-id="dc416-147">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="dc416-148">ADLS engedélyezése a Dynamics 365 Commerce környezetben</span><span class="sxs-lookup"><span data-stu-id="dc416-148">Enable ADLS in a Dynamics 365 Commerce environment</span></span>](enable-adls-environment.md)

[<span data-ttu-id="dc416-149">Termékajánlatok engedélyezése</span><span class="sxs-lookup"><span data-stu-id="dc416-149">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="dc416-150">Személyre szabott ajánlatok engedélyezése</span><span class="sxs-lookup"><span data-stu-id="dc416-150">Enable personalized recommendations</span></span>](personalized-recommendations.md)

[<span data-ttu-id="dc416-151">Személyre szabott termékajánlatok kikapcsolása</span><span class="sxs-lookup"><span data-stu-id="dc416-151">Opt out of personalized recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="dc416-152">Ajánlat listáinak hozzáadása egy e-Commerce webhelyhez</span><span class="sxs-lookup"><span data-stu-id="dc416-152">Add recommendation lists to an e-Commerce site</span></span>](add-reco-list-to-page.md)

[<span data-ttu-id="dc416-153">Termékajánlások hozzáadása a pénztárnál</span><span class="sxs-lookup"><span data-stu-id="dc416-153">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="dc416-154">Ajánlatok hozzáadása a tranzakciós képernyőhöz</span><span class="sxs-lookup"><span data-stu-id="dc416-154">Add recommendations to the transaction screen</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="dc416-155">AI-ML ajánlások eredményeinek helyesbítése</span><span class="sxs-lookup"><span data-stu-id="dc416-155">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="dc416-156">Válogatott ajánlások manuális létrehozása</span><span class="sxs-lookup"><span data-stu-id="dc416-156">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="dc416-157">Termékajánlatok GYIK-je</span><span class="sxs-lookup"><span data-stu-id="dc416-157">Product recommendations FAQ</span></span>](faq-recommendations.md)
