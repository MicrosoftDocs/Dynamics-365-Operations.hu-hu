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
ms.openlocfilehash: e249c7d450510a3a9a33158e9e1c33f832a1f91c
ms.sourcegitcommit: b5ecde955a69f577de46e7db10e89caaedeb2b49
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/04/2020
ms.locfileid: "3024979"
---
# <a name="product-recommendations-overview"></a><span data-ttu-id="0e342-104">Termékajánlatok áttekintése</span><span class="sxs-lookup"><span data-stu-id="0e342-104">Product recommendations overview</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="0e342-105">A Microsoft Dynamics 365 Commerce a termékjavaslatok megjelenítésére használható az e-kereskedelmi webhelyeken és a pénztári (POS) eszközön.</span><span class="sxs-lookup"><span data-stu-id="0e342-105">Microsoft Dynamics 365 Commerce can be used to show product recommendations on the e-Commerce website and point of sale (POS) device.</span></span> <span data-ttu-id="0e342-106">A termékjavaslatok olyan cikkek, amelyeket a vevő számára érdekesek lehetnek.</span><span class="sxs-lookup"><span data-stu-id="0e342-106">Product recommendations are items that a customer might be interested in.</span></span> <span data-ttu-id="0e342-107">Az ajánlások az online és a fizikai áruházakban a más vevők beszerzési trendjein alapulnak.</span><span class="sxs-lookup"><span data-stu-id="0e342-107">The recommendations are based on the purchase trends of other customers in online and brick-and-mortar stores.</span></span>

<span data-ttu-id="0e342-108">A termékjavaslatok révén a vevők egyszerűen és gyorsan megtalálják azokat a termékeket, amelyeket szeretnének, és mindeközben jó élményben van részük.</span><span class="sxs-lookup"><span data-stu-id="0e342-108">Product recommendations let customers easily and quickly find products that they want while they have an experience that serves them well.</span></span> <span data-ttu-id="0e342-109">A kereszt- és felülértékesítések arra is használhatók, hogy a vásárlók olyan termékeket is találjanak, amelyeket eredetileg nem is szándékoztak megvásárolni.</span><span class="sxs-lookup"><span data-stu-id="0e342-109">Cross-selling and upselling can even be used to help customers find additional products than they didn't originally intend to buy.</span></span> <span data-ttu-id="0e342-110">Amikor a termékek felfedezésével kapcsolatos segítséghez használják a javaslatokat, több konverziós lehetőséget is kialakíthatnak, és ezek elősegítik az értékesítési bevételek növelését, valamint javíthatják a vevői elégedettséget és a visszatartást.</span><span class="sxs-lookup"><span data-stu-id="0e342-110">When recommendations are used to help with product discovery, they can create more conversion opportunities, help increase sales revenue, and even help enhance customer satisfaction and retention.</span></span>

<span data-ttu-id="0e342-111">A Commerce alkalmazásban a termékjavaslatokat a Microsoft Recommendations gép tanulási technológiái támogatják.</span><span class="sxs-lookup"><span data-stu-id="0e342-111">In Commerce, product recommendations are powered by Microsoft Recommendations machine learning technologies on a large scale.</span></span>


## <a name="scenarios"></a><span data-ttu-id="0e342-112">Esetek</span><span class="sxs-lookup"><span data-stu-id="0e342-112">Scenarios</span></span>

<span data-ttu-id="0e342-113">Az alábbi POS-esetekben érhetők el a termékajánlások.</span><span class="sxs-lookup"><span data-stu-id="0e342-113">Product recommendations are available for the following scenarios:</span></span>

- <span data-ttu-id="0e342-114">**Az e-Commerce-ben egy üzlet böngészési vagy érkezőoldalán**: Ha a vevők vagy az üzlet munkatársai meglátogatják a bolt egy oldalát, akkor az ajánlási rendszer az **Új**, **Legkelendőbb**és **Legnépszerűbb** listákban javasolhat termékeket.</span><span class="sxs-lookup"><span data-stu-id="0e342-114">**On any store page for browsing or landing page in e-Commerce:** If customers or store associates visit a store page, the recommendation engine can suggest products in the **New**, **Best Selling**, and **Trending** lists.</span></span>
- <span data-ttu-id="0e342-115">**A Termékrészletek oldalon:** Ha a vevők vagy az üzlet munkatársai felkeresnek egy **Termékrészletek** lapot, akkor az ajánlási motor további, valószínűleg megvásárolni kívánt cikkeket javasol.</span><span class="sxs-lookup"><span data-stu-id="0e342-115">**On the Product details page:** If customers or store associates visit a **Product details** page, the recommendation engine suggests additional items that are also likely to be purchased.</span></span> <span data-ttu-id="0e342-116">Ezek a cikkek a **Másoknak ez is tetszett** listán jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="0e342-116">These items appear in the **People also like** list.</span></span>
- <span data-ttu-id="0e342-117">**A tranzakció oldalon vagy a pénztár oldalon:** Az ajánlási motor a kosárban található cikkek teljes listája alapján javasolja a cikkeket.</span><span class="sxs-lookup"><span data-stu-id="0e342-117">**On the Transaction page or the checkout page:** The recommendation engine suggests items, based on the whole list of items in the basket.</span></span> <span data-ttu-id="0e342-118">Ezek a cikkek megjelennek a **Gyakran együtt vásárolt** listán.</span><span class="sxs-lookup"><span data-stu-id="0e342-118">These items appear in the **Frequently bought together** list.</span></span>
- <span data-ttu-id="0e342-119">**Személyre szabott ajánlások:**: a kereskedők a bejelentkezett vevők számára személyre szabott **kitárolásokat** adhatnak meg a listán, emellett olyan új funkciókat, amelyek lehetővé teszik a meglévő lista-forgatókönyvek személyre szabását a vevő alapján.</span><span class="sxs-lookup"><span data-stu-id="0e342-119">**Personalized recommendations:** Merchandizers can provide signed-in customers a personalized **picks for you** list, in addition to new functionality that allows for existing list scenarios to be personalized based on that customer.</span></span> <span data-ttu-id="0e342-120">A további tudnivalókat lásd a funkció dokumentációban: [személyre szabott ajánlatok engedélyezése.](personalized-recommendations.md)</span><span class="sxs-lookup"><span data-stu-id="0e342-120">To learn more, please see the feature documenation: [enable personalized recommedations.](personalized-recommendations.md)</span></span>

## <a name="recommendation-service"></a><span data-ttu-id="0e342-121">Ajánlási szolgáltatás</span><span class="sxs-lookup"><span data-stu-id="0e342-121">Recommendation service</span></span>

<span data-ttu-id="0e342-122">A termékjavaslatoka következő módon használják a Javaslatok gép tanulási technológiákat:</span><span class="sxs-lookup"><span data-stu-id="0e342-122">Product recommendations use the Recommendations machine learning technologies in the following way:</span></span>

- <span data-ttu-id="0e342-123">Az ajánlási szolgáltatásnak megfelelő formátumú adatokat a rendszer kivonja az adatokat a Commerce működési adatbázisából, és elküldi őket az entitástárba.</span><span class="sxs-lookup"><span data-stu-id="0e342-123">Data in the format that the Recommendation service requires is extracted from the Commerce operational database and sent to the Entity store.</span></span>
- <span data-ttu-id="0e342-124">Az ajánlási szolgáltatás az adatokat az ajánlási modellek tanításához használja a **Másoknak ez is tetszett**. **Gyakran együtt vásárolt**, **Új**, **Legkelendőbb** és **Legnépszerűbbek** listákhoz.</span><span class="sxs-lookup"><span data-stu-id="0e342-124">The Recommendation service uses the data to train recommendation models for the **People also like**, **Frequently bought together**, **New**, **Best selling**, and **Trending** lists.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0e342-125">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="0e342-125">Additional resources</span></span>

[<span data-ttu-id="0e342-126">Termékajánlatok engedélyezése</span><span class="sxs-lookup"><span data-stu-id="0e342-126">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="0e342-127">Személyre szabott ajánlatok engedélyezése</span><span class="sxs-lookup"><span data-stu-id="0e342-127">Enable personalized recommendations</span></span>](personalized-recommendations.md)

[<span data-ttu-id="0e342-128">Termékgyűjtési modul áttekintése</span><span class="sxs-lookup"><span data-stu-id="0e342-128">Product collection module overview</span></span>](product-collection-module-overview.md)

[<span data-ttu-id="0e342-129">Válogatott termékek ajánlati listájának létrehozása</span><span class="sxs-lookup"><span data-stu-id="0e342-129">Create curated product recommendation lists</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="0e342-130">AI-ML-alapú termékajánlás eredményeinek kezelése</span><span class="sxs-lookup"><span data-stu-id="0e342-130">Manage AI-ML-based product recommendation results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="0e342-131">Termékjavaslat-listák hozzáadása az oldalakhoz</span><span class="sxs-lookup"><span data-stu-id="0e342-131">Add product recommendation lists to pages</span></span>](add-reco-list-to-page.md)
