---
title: Termékajánlatok áttekintése
description: Ez a témakör a rendezési termékjavaslatok ismertetését tartalmazza. A termékjavaslatoknak köszönhetően a vevők egyszerűen és gyorsan megtalálják azokat a termékeket, amelyeket szeretnének, és még olyanokat is, amelyek eredetileg nem szándékoznak megvásárolni.
author: Moonma
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
ms.author: moonma
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: eb369e6d1356ba13a2310d523b671ac57b9642bf
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770047"
---
# <a name="product-recommendations-overview"></a><span data-ttu-id="8cd64-104">Termékajánlatok áttekintése</span><span class="sxs-lookup"><span data-stu-id="8cd64-104">Product recommendations overview</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="8cd64-105">A Microsoft Dynamics 365 Commerce a termékjavaslatok megjelenítésére használható az e-kereskedelmi webhelyeken és a pénztári (POS) eszközön.</span><span class="sxs-lookup"><span data-stu-id="8cd64-105">Microsoft Dynamics 365 Commerce can be used to show product recommendations on the e-Commerce website and point of sale (POS) device.</span></span> <span data-ttu-id="8cd64-106">A termékjavaslatok olyan cikkek, amelyeket a vevő számára érdekesek lehetnek.</span><span class="sxs-lookup"><span data-stu-id="8cd64-106">Product recommendations are items that a customer might be interested in.</span></span> <span data-ttu-id="8cd64-107">Az ajánlások az online és a fizikai áruházakban a más vevők beszerzési trendjein alapulnak.</span><span class="sxs-lookup"><span data-stu-id="8cd64-107">The recommendations are based on the purchase trends of other customers in online and brick-and-mortar stores.</span></span>

<span data-ttu-id="8cd64-108">A termékjavaslatok révén a vevők egyszerűen és gyorsan megtalálják azokat a termékeket, amelyeket szeretnének, és mindeközben jó élményben van részük.</span><span class="sxs-lookup"><span data-stu-id="8cd64-108">Product recommendations let customers easily and quickly find products that they want while they have an experience that serves them well.</span></span> <span data-ttu-id="8cd64-109">A kereszt- és felülértékesítések arra is használhatók, hogy a vásárlók olyan termékeket is találjanak, amelyeket eredetileg nem is szándékoztak megvásárolni.</span><span class="sxs-lookup"><span data-stu-id="8cd64-109">Cross-selling and upselling can even be used to help customers find additional products than they didn't originally intend to buy.</span></span> <span data-ttu-id="8cd64-110">Amikor a termékek felfedezésével kapcsolatos segítséghez használják a javaslatokat, több konverziós lehetőséget is kialakíthatnak, és ezek elősegítik az értékesítési bevételek növelését, valamint javíthatják a vevői elégedettséget és a visszatartást.</span><span class="sxs-lookup"><span data-stu-id="8cd64-110">When recommendations are used to help with product discovery, they can create more conversion opportunities, help increase sales revenue, and even help enhance customer satisfaction and retention.</span></span>

<span data-ttu-id="8cd64-111">A Commerce alkalmazásban a termékjavaslatokat a Microsoft Recommendations gép tanulási technológiái támogatják.</span><span class="sxs-lookup"><span data-stu-id="8cd64-111">In Commerce, product recommendations are powered by Microsoft Recommendations machine learning technologies on a large scale.</span></span>


## <a name="scenarios"></a><span data-ttu-id="8cd64-112">Esetek</span><span class="sxs-lookup"><span data-stu-id="8cd64-112">Scenarios</span></span>

<span data-ttu-id="8cd64-113">Az alábbi POS-esetekben érhetők el a termékajánlások.</span><span class="sxs-lookup"><span data-stu-id="8cd64-113">Product recommendations are available for the following scenarios:</span></span>

- <span data-ttu-id="8cd64-114">**Az e-Commerce-ben egy üzlet böngészési vagy érkezőoldalán**: Ha a vevők vagy az üzlet munkatársai meglátogatják a bolt egy oldalát, akkor az ajánlási rendszer az **Új**, **Legkelendőbb**és **Legnépszerűbb** listákban javasolhat termékeket.</span><span class="sxs-lookup"><span data-stu-id="8cd64-114">**On any store page for browsing or landing page in e-Commerce:** If customers or store associates visit a store page, the recommendation engine can suggest products in the **New**, **Best Selling**, and **Trending** lists.</span></span>
- <span data-ttu-id="8cd64-115">**A Termékrészletek oldalon:** Ha a vevők vagy az üzlet munkatársai felkeresnek egy **Termékrészletek** lapot, akkor az ajánlási motor további, valószínűleg megvásárolni kívánt cikkeket javasol.</span><span class="sxs-lookup"><span data-stu-id="8cd64-115">**On the Product details page:** If customers or store associates visit a **Product details** page, the recommendation engine suggests additional items that are also likely to be purchased.</span></span> <span data-ttu-id="8cd64-116">Ezek a cikkek a **Másoknak ez is tetszett** listán jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="8cd64-116">These items appear in the **People also like** list.</span></span>
- <span data-ttu-id="8cd64-117">**A tranzakció oldalon vagy a pénztár oldalon:** Az ajánlási motor a kosárban található cikkek teljes listája alapján javasolja a cikkeket.</span><span class="sxs-lookup"><span data-stu-id="8cd64-117">**On the Transaction page or the checkout page:** The recommendation engine suggests items, based on the whole list of items in the basket.</span></span> <span data-ttu-id="8cd64-118">Ezek a cikkek megjelennek a **Gyakran együtt vásárolt** listán.</span><span class="sxs-lookup"><span data-stu-id="8cd64-118">These items appear in the **Frequently bought together** list.</span></span>

## <a name="recommendation-service"></a><span data-ttu-id="8cd64-119">Ajánlási szolgáltatás</span><span class="sxs-lookup"><span data-stu-id="8cd64-119">Recommendation service</span></span>

<span data-ttu-id="8cd64-120">A termékjavaslatoka következő módon használják a Javaslatok gép tanulási technológiákat:</span><span class="sxs-lookup"><span data-stu-id="8cd64-120">Product recommendations use the Recommendations machine learning technologies in the following way:</span></span>

- <span data-ttu-id="8cd64-121">Az ajánlási szolgáltatásnak megfelelő formátumú adatokat a rendszer kivonja az adatokat a Commerce működési adatbázisából, és elküldi őket az entitástárba.</span><span class="sxs-lookup"><span data-stu-id="8cd64-121">Data in the format that the Recommendation service requires is extracted from the Commerce operational database and sent to the Entity store.</span></span>
- <span data-ttu-id="8cd64-122">Az ajánlási szolgáltatás az adatokat az ajánlási modellek tanításához használja a **Másoknak ez is tetszett**. **Gyakran együtt vásárolt**, **Új**, **Legkelendőbb** és **Legnépszerűbbek** listákhoz.</span><span class="sxs-lookup"><span data-stu-id="8cd64-122">The Recommendation service uses the data to train recommendation models for the **People also like**, **Frequently bought together**, **New**, **Best selling**, and **Trending** lists.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8cd64-123">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="8cd64-123">Additional resources</span></span>

[<span data-ttu-id="8cd64-124">Termékajánlatok engedélyezése</span><span class="sxs-lookup"><span data-stu-id="8cd64-124">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="8cd64-125">Válogatott termékek ajánlati listájának létrehozása</span><span class="sxs-lookup"><span data-stu-id="8cd64-125">Create curated product recommendation lists</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="8cd64-126">AI-ML-alapú termékajánlás eredményeinek kezelése</span><span class="sxs-lookup"><span data-stu-id="8cd64-126">Manage AI-ML-based product recommendation results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="8cd64-127">Termékjavaslat-listák hozzáadása az oldalakhoz</span><span class="sxs-lookup"><span data-stu-id="8cd64-127">Add product recommendation lists to pages</span></span>](add-reco-list-to-page.md)
