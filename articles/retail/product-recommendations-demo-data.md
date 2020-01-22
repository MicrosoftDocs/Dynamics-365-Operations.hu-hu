---
title: Többcsatornás termékajánlások demóadatok
description: A dokumentum célja, hogy útmutatást adjon a többcsatornás termékajánlásoknak az 1.szintű egyablakos környezetekben történő kihasználásához előre kitöltött, testreszabható demóadatok felhasználásával.
author: bebeale
manager: AnnBe
ms.date: 12/1/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: ''
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-07-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 31aa5dbd2fa814fd572024a4ae36b9d9b46a2fb0
ms.sourcegitcommit: 398c0652acde12c953de007d06055456d6e0a516
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/02/2019
ms.locfileid: "2872326"
---
# <a name="omni-channel-product-recommendations-demo-data"></a><span data-ttu-id="c5b20-103">Többcsatornás termékajánlások demóadatok</span><span class="sxs-lookup"><span data-stu-id="c5b20-103">Omni-channel product recommendations demo data</span></span>

<span data-ttu-id="c5b20-104">A dokumentum célja, hogy útmutatást adjon a többcsatornás termékajánlásoknak az 1.szintű egyablakos környezetekben történő kihasználásához előre kitöltött, testreszabható demóadatok felhasználásával.</span><span class="sxs-lookup"><span data-stu-id="c5b20-104">This document aims to provide guidance on how to leverage omni-channel product recommendations in Tier-1 single box environments using pre-populated, customizable demo data.</span></span>

<span data-ttu-id="c5b20-105">A többcsatornás termékajánlások termékek szerkesztők által karbantartott vagy program által generált rendezett listájának készletét adják.</span><span class="sxs-lookup"><span data-stu-id="c5b20-105">Omni-channel product recommendations provide a set of editorially curated or programmatically generated ordered list of products.</span></span> <span data-ttu-id="c5b20-106">Ezek a listák több esetben is használhatók, attól függően, hogy milyen üzleti szükséglet van.</span><span class="sxs-lookup"><span data-stu-id="c5b20-106">These lists can be used in several scenarios, depending on the business need.</span></span> <span data-ttu-id="c5b20-107">A termékajánlási listákkal kapcsolatos további tudnivalókat lásd: [Termékajánlások áttekintése.](../commerce/product-recommendations.md)</span><span class="sxs-lookup"><span data-stu-id="c5b20-107">For more information about product recommendation lists, see [Product recommendations overview.](../commerce/product-recommendations.md)</span></span>

<span data-ttu-id="c5b20-108">A 2. és magasabb szintű Dynamics környezetekben a termékajánlások automatikusan, a vevői adatok alapján kerülnek kiszámításra.</span><span class="sxs-lookup"><span data-stu-id="c5b20-108">For Tier-2 and higher Dynamics Environments product recommendations are automatically computed based on customer data.</span></span>
<span data-ttu-id="c5b20-109">A termékajánlások demóadatainak használata nem tiltja le a környezetben már kiépített ajánlási megoldásokat, illetve a vonatkozó használati költségeket.</span><span class="sxs-lookup"><span data-stu-id="c5b20-109">Using product recommendations demo data does not disable any product recommendations solution already provisioned in the environment and any costs associated with its usage.</span></span>

<span data-ttu-id="c5b20-110">Az 1. szintű környezetekben a termékajánlások csak a CSV-fájlban tárolt statikus demóadatokon alapulnak.</span><span class="sxs-lookup"><span data-stu-id="c5b20-110">For Tier-1 environments product recommendations are based only off the static demo data stored in a csv file.</span></span>

## <a name="enabling-product-recommendations-demo-data-in-an-environment"></a><span data-ttu-id="c5b20-111">A termékajánlások demóadatainak engedélyezése egy környezetben</span><span class="sxs-lookup"><span data-stu-id="c5b20-111">Enabling product recommendations demo data in an environment</span></span>

<span data-ttu-id="c5b20-112">A **Dynamics 365 Commerce Preview Demo Extension** kiterjesztést a megfelelő környezetre kell telepíteni, ami automatikusan engedélyezi a termékajánlások demóadatait.</span><span class="sxs-lookup"><span data-stu-id="c5b20-112">Customers need to deploy the **Dynamics 365 Commerce Preview Demo Extension** to the respective environment, which automatically enables product recommendations demo data.</span></span>

## <a name="default-demo-data"></a><span data-ttu-id="c5b20-113">Alapértelmezett demóadatok</span><span class="sxs-lookup"><span data-stu-id="c5b20-113">Default demo data</span></span>
<span data-ttu-id="c5b20-114">Minden Onebox típusú környezet rendelkezik egy előre betöltött termékajánlás-demóadat készlettel a vesszővel elválasztott **‘reco_demo_data.csv’** fájlban, amely ugyanabban a mappában található, mint ez a dokumentuma Retail Server kiszolgálón.</span><span class="sxs-lookup"><span data-stu-id="c5b20-114">Each Onebox type environment comes with a preloaded set of product recommendations demo data stored in the coma separated **‘reco_demo_data.csv’** file, located in the same folder as this document on Retail Server.</span></span>

<span data-ttu-id="c5b20-115">Ezek az adatok a következő oszlopok mentén strukturáltak.</span><span class="sxs-lookup"><span data-stu-id="c5b20-115">This data is structured along the following columns</span></span>

| <span data-ttu-id="c5b20-116">Oszlop neve</span><span class="sxs-lookup"><span data-stu-id="c5b20-116">Column name</span></span>         | <span data-ttu-id="c5b20-117">Kötelező</span><span class="sxs-lookup"><span data-stu-id="c5b20-117">Mandatory</span></span>          | <span data-ttu-id="c5b20-118">Leírás</span><span class="sxs-lookup"><span data-stu-id="c5b20-118">Description</span></span>                                                                                                                                 | <span data-ttu-id="c5b20-119">Lehetséges értékek</span><span class="sxs-lookup"><span data-stu-id="c5b20-119">Possible Values</span></span>                                                              |
|---------------------|--------------------|---------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------|
| <span data-ttu-id="c5b20-120">RecoList</span><span class="sxs-lookup"><span data-stu-id="c5b20-120">RecoList</span></span>            | :heavy_check_mark: | <span data-ttu-id="c5b20-122">A konkrét termékajánlási listatípust, amelyre a demóadatok mutatnak, létre kell hozni.</span><span class="sxs-lookup"><span data-stu-id="c5b20-122">The specific product   recommendation list type that the demo data point is to generate.</span></span>                                                    | <ul><li><span data-ttu-id="c5b20-123">RecoBestSelling</span><span class="sxs-lookup"><span data-stu-id="c5b20-123">RecoBestSelling</span></span></li><li><span data-ttu-id="c5b20-124">RecoNew</span><span class="sxs-lookup"><span data-stu-id="c5b20-124">RecoNew</span></span></li><li><span data-ttu-id="c5b20-125">RecoTrending</span><span class="sxs-lookup"><span data-stu-id="c5b20-125">RecoTrending</span></span></li><li><span data-ttu-id="c5b20-126">RecoCart</span><span class="sxs-lookup"><span data-stu-id="c5b20-126">RecoCart</span></span></li><li><span data-ttu-id="c5b20-127">RecoPeopleAlsoBuy</span><span class="sxs-lookup"><span data-stu-id="c5b20-127">RecoPeopleAlsoBuy</span></span></li></ul> |
| <span data-ttu-id="c5b20-128">OperatingUnitNumber</span><span class="sxs-lookup"><span data-stu-id="c5b20-128">OperatingUnitNumber</span></span> | :heavy_check_mark: | <span data-ttu-id="c5b20-130">Az a meghatározott üzemiegység-szám, amelyekben a termékajánlásoknak meg kell jelenniük.</span><span class="sxs-lookup"><span data-stu-id="c5b20-130">The specific   operating unit number where product recommendations are expected to be   surfaced in.</span></span>                                        |                                                                              |
| <span data-ttu-id="c5b20-131">Kategória</span><span class="sxs-lookup"><span data-stu-id="c5b20-131">Category</span></span>            |                    |    <span data-ttu-id="c5b20-132">Az a kategória, amelyhez a megadott lista visszaadandó.</span><span class="sxs-lookup"><span data-stu-id="c5b20-132">The category the   specific list should be returned for.</span></span> <span data-ttu-id="c5b20-133">Ha nincs megadva kategória, akkor a lista csak a navigációs hierarchia elejére kerül.</span><span class="sxs-lookup"><span data-stu-id="c5b20-133">If no category is specified, list is   for top of navigation hierarchy only.</span></span>    |                                                                              |
| <span data-ttu-id="c5b20-134">SeedItemId</span><span class="sxs-lookup"><span data-stu-id="c5b20-134">SeedItemId</span></span>          |                    |    <span data-ttu-id="c5b20-135">A kiindulást igénylő listáknál (RecoPeopleAlsoBuy és RecoCart) a terméknél a listán további termékeket kell megjeleníteni.</span><span class="sxs-lookup"><span data-stu-id="c5b20-135">For lists that   require seed (RecoPeopleAlsoBuy and RecoCart) the product those lists should   show additional products for.</span></span>            |                                                                              |
| <span data-ttu-id="c5b20-136">ItemIds</span><span class="sxs-lookup"><span data-stu-id="c5b20-136">ItemIds</span></span>             | :heavy_check_mark: | <span data-ttu-id="c5b20-138">Egy vagy több termék, amelyet eredményként kell visszaküldeni, elválasztva a következővel **";"**.</span><span class="sxs-lookup"><span data-stu-id="c5b20-138">One or more products   to be returned as the result, separated by **‘;’**.</span></span>                                                                  |                                                                              |


## <a name="customize-demo-data"></a><span data-ttu-id="c5b20-139">Demóadatok testreszabása</span><span class="sxs-lookup"><span data-stu-id="c5b20-139">Customize demo data</span></span>
<span data-ttu-id="c5b20-140">A felhasználók szerkeszthetik az alapértelmezett demóadatokat bármilyen termék- és kategóriainformációval, amelyet a HQ konfigurál.</span><span class="sxs-lookup"><span data-stu-id="c5b20-140">Customers can edit the default demo data with any product and category information that is configured in HQ.</span></span> <span data-ttu-id="c5b20-141">A CSV-fájl frissítését követően a vevőknek visszaküldött termékajánlásokban azonnal megjelennek a módosítások.</span><span class="sxs-lookup"><span data-stu-id="c5b20-141">Once the CSV is updated, the Product Recommendations returned to customers will immediately reflect the changes.</span></span>

<span data-ttu-id="c5b20-142">A kiterjesztés tartalmaz egy RecoMockDataset.csv nevű adatfájlt, amely lehetővé teszi, hogy a vevő vezérelje azt az adathalmazt, amely a szimulált ajánlások eredményeinek alkalmazására használt.</span><span class="sxs-lookup"><span data-stu-id="c5b20-142">The extension contains a datafile called RecoMockDataset.csv which allows the customer to control the dataset used to power the mock recommendations results.</span></span> <span data-ttu-id="c5b20-143">A fájlnév a kiterjesztéskonfigurációt használva vezérelhető a **ext.Recommendations.DemoFilePath** DemoFilePath beállítás használatával.</span><span class="sxs-lookup"><span data-stu-id="c5b20-143">The file name can be controlled through extension configuration using the **ext.Recommendations.DemoFilePath** setting.</span></span> <span data-ttu-id="c5b20-144">Ez lehetővé teszi a vevők számára, hogy több adatkészlettel rendelkezzenek, amelyek között a konfiguráció használatával könnyen lehet váltani.</span><span class="sxs-lookup"><span data-stu-id="c5b20-144">This enables the customers to have multiple datasets available that can be switched between easily through configuration.</span></span>

```
  <settings>
    <add name="ext.Recommendations.DemoFilePath" value="RecoMockDataset.csv" />
  </settings>
```

## <a name="additional-resources"></a><span data-ttu-id="c5b20-145">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="c5b20-145">Additional resources</span></span>

[<span data-ttu-id="c5b20-146">Termékajánlások áttekintése</span><span class="sxs-lookup"><span data-stu-id="c5b20-146">Product recommendations overview</span></span>](../commerce/product-recommendations.md)

[<span data-ttu-id="c5b20-147">Környezet tervezése</span><span class="sxs-lookup"><span data-stu-id="c5b20-147">Environment planning</span></span>](../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md)
