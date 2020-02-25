---
title: Csatornaspecifikus engedmények definiálása
description: A kiskereskedők gyakran különböző engedményeket állítanak be a különböző csatornákon. Ez a témakör ellenőrzi azokat a fogalmakat, amelyeket a megadott csatornára vonatkozó engedmények létrehozásához tudnia kell.
author: scott-tucker
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailAffiliationPriceGroup, RetailCatalogPriceGroup, RetailChannelPriceGroup, RetailDiscountPriceGroup, RetailDiscountPricingWorkspace, RetailPeriodicDiscount, RetailStoreItemPriceList, RetailStoreTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 16401
ms.assetid: d807fd51-86aa-47a0-8e00-6c5ddd21ff6b
ms.search.region: global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 539a6f2df46450c5e0fd18ba69501432d6f3fbdd
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/01/2020
ms.locfileid: "3022738"
---
# <a name="define-channel-specific-discounts"></a><span data-ttu-id="207af-104">Csatornaspecifikus engedmények definiálása</span><span class="sxs-lookup"><span data-stu-id="207af-104">Define channel-specific discounts</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="207af-105">Ez a témakör ellenőrzi azokat a fogalmakat, amelyeket a megadott csatornára vonatkozó engedmények létrehozásához tudnia kell.</span><span class="sxs-lookup"><span data-stu-id="207af-105">This topic reviews the concepts you need to know to create a discount for a specific channel.</span></span>

## <a name="channel-specific-discounts"></a><span data-ttu-id="207af-106">Csatornaspecifikus engedmények</span><span class="sxs-lookup"><span data-stu-id="207af-106">Channel-specific discounts</span></span>

<span data-ttu-id="207af-107">A kiskereskedők gyakran különböző engedményeket ajánlanak a különböző csatornákon.</span><span class="sxs-lookup"><span data-stu-id="207af-107">Retailers often offer different discounts in different channels.</span></span> <span data-ttu-id="207af-108">Ezt tehetik a helyi piaci feltétetelek kezelése vagy a versenytárs kiskereskedők legyőzése érdekében.</span><span class="sxs-lookup"><span data-stu-id="207af-108">This may be done to address local market conditions or to deal with competing retailers.</span></span>

<span data-ttu-id="207af-109">A Commerce árcsoportok segítségével definiálja a csatornaspecifikus engedményeket.</span><span class="sxs-lookup"><span data-stu-id="207af-109">Commerce uses price groups to define channel-specific discounts.</span></span> <span data-ttu-id="207af-110">Az árcsoportok a következő entitások egy vagy több lehetőségéhez rendelhetők hozzá: csatornák, katalógusok, fiókok és hűségprogramok.</span><span class="sxs-lookup"><span data-stu-id="207af-110">Price groups can be assigned to one or more of the following entities: channels, catalogs, affiliations, and loyalty programs.</span></span> <span data-ttu-id="207af-111">A cikk a csatornákat tárgyalja, de az azonos koncepciók a katalógus engedményekre, fiók engedményekre és a hűséges engedményekre vonatkoznak.</span><span class="sxs-lookup"><span data-stu-id="207af-111">This article discusses channels, but the same concepts apply to catalog discounts, affiliations discounts, and loyalty discounts.</span></span>

## <a name="price-groups"></a><span data-ttu-id="207af-112">Árcsoportok</span><span class="sxs-lookup"><span data-stu-id="207af-112">Price groups</span></span>

<span data-ttu-id="207af-113">[![Árcsoportok](./media/price-groups-1024x608.png)](./media/price-groups.png)</span><span class="sxs-lookup"><span data-stu-id="207af-113">[![Price groups](./media/price-groups-1024x608.png)](./media/price-groups.png)</span></span>

<span data-ttu-id="207af-114">A fenti ábra bemutatja a tranzakciókban megtalálható (csatorna, katalógus, fiók, vevő, hűségkártya) entitások és a különféle konfigurálható engedménytípusok közötti kapcsolatot.</span><span class="sxs-lookup"><span data-stu-id="207af-114">The diagram above illustrates the relationship between entities that may be on a transaction (channel, catalog, affiliation, customer, loyalty card) and the various discount types that can be configured.</span></span> <span data-ttu-id="207af-115">Az összes tranzakció egy csatornában fordul elő, így a csatorna garantáltan rajta van egy tranzakción.</span><span class="sxs-lookup"><span data-stu-id="207af-115">All transactions occur in a channel, so the channel is guaranteed to be present on a transaction.</span></span> <span data-ttu-id="207af-116">A fennmaradó entitások megadása nem kötelező.</span><span class="sxs-lookup"><span data-stu-id="207af-116">The remaining entities are optional.</span></span> <span data-ttu-id="207af-117">Minden egyes alapadat lapon van egy hivatkozás a kapcsolódó árcsoportok lapjához, ahol megtekintheti az árcsoportokat és szükség szerint hozzá is adhat árcsoportokat.</span><span class="sxs-lookup"><span data-stu-id="207af-117">On each master data pages there is a link to a related price groups page where you can view and add price groups as needed.</span></span> <span data-ttu-id="207af-118">Az árcsoportok segítségével az entitások négy különböző típusát kapcsolják össze az engedményekkel, az ármódosításokkal és kereskedelmi megállapodásokkal.</span><span class="sxs-lookup"><span data-stu-id="207af-118">A price group is used to relate four different types of entities to discounts, price adjustments, and trade agreements.</span></span> <span data-ttu-id="207af-119">Azt ajánljuk, hogy tervezzen meg egy stratégiát, hogyan fogja az árcsoportjait elnevezni annak érdekében, hogy rendben tartsa őket.</span><span class="sxs-lookup"><span data-stu-id="207af-119">We recommend that you plan a strategy for how you will name your price groups to keep them organized.</span></span> <span data-ttu-id="207af-120">Például egy betű- vagy számelőtag vagy -utótag segítségével megkülönböztet különféle típusokat.</span><span class="sxs-lookup"><span data-stu-id="207af-120">One option would be to use a letter or number prefix or suffix to distinguish between the different types.</span></span> <span data-ttu-id="207af-121">Például 1-xxxxx a csatornaárcsoportok és 2-xxxxx a katalógusárcsoportok számára.</span><span class="sxs-lookup"><span data-stu-id="207af-121">For example, 1-xxxxx for channel price groups and 2-xxxxx for catalog price groups.</span></span> <span data-ttu-id="207af-122">Négy lekérdezési oldal van, amely valamennyi engedményekhez rendelt kereskedelmi entitásra fókuszál.</span><span class="sxs-lookup"><span data-stu-id="207af-122">There are four inquiry pages that focus on each of the commerce entities that can have discounts associated to them.</span></span>

- <span data-ttu-id="207af-123">**Csatorna csatorna árcsoportjai** – Ez a lap megjeleníti a minden egyes árcsoporthoz kapcsolódó engedmények és csatornák listáját.</span><span class="sxs-lookup"><span data-stu-id="207af-123">**Channel channel price groups** – This page shows a list of channels and discounts linked together for each price group.</span></span>
- <span data-ttu-id="207af-124">**Katalógus árcsoportjai**– Ez a lap megjeleníti a minden egyes árcsoporthoz kapcsolódó engedmények és katalógusok listáját.</span><span class="sxs-lookup"><span data-stu-id="207af-124">**Catalog price groups** – This page shows a list of catalogs and discounts linked together for each price group.</span></span>
- <span data-ttu-id="207af-125">**Hűség árcsoportjai**– Ez a lap megjeleníti a minden egyes árcsoporthoz kapcsolódó engedmények és hűségprogramok listáját.</span><span class="sxs-lookup"><span data-stu-id="207af-125">**Loyalty price groups** – This page shows a list of loyalty programs and discounts linked together for each price group.</span></span>
- <span data-ttu-id="207af-126">**Fiók árcsoportjai**– Ez a lap megjeleníti a minden egyes árcsoporthoz kapcsolódó engedmények és fiókok listáját.</span><span class="sxs-lookup"><span data-stu-id="207af-126">**Affiliation price groups** – This page shows a list of affiliations and discounts linked together for each price group.</span></span>

## <a name="example-channel-discount-set-up"></a><span data-ttu-id="207af-127">Csatorna kedvezmény beállítás példája</span><span class="sxs-lookup"><span data-stu-id="207af-127">Example channel discount set up</span></span>

<span data-ttu-id="207af-128">A következő példa bemutatja egy csatorna engedmény beállításába bevont feladatokat.</span><span class="sxs-lookup"><span data-stu-id="207af-128">The following example illustrates the tasks involved in setting up a channel discount.</span></span>

1. <span data-ttu-id="207af-129">Ebben a példában egy úgynevezett **Houston**csatornával rendelkezik, és egy **Vissza az iskolába**nevezett új engedményt fog létrehozni.</span><span class="sxs-lookup"><span data-stu-id="207af-129">For this example, you have a channel called **Houston**, and you're going to create a new discount called **Back-to-School**.</span></span>
2. <span data-ttu-id="207af-130">Mivel az árképzés és az engedmény stratégia csatorna engedmények lehetőségét tartalmazza, mindig létrehoz csatornaspecifikus árcsoportot egy csatorna létrehozásakor.</span><span class="sxs-lookup"><span data-stu-id="207af-130">Because the pricing and discount strategy includes the possibility of channel discounts, you always create a channel-specific price group when you create a channel.</span></span>
3. <span data-ttu-id="207af-131">**Houston-PG** árcsoporttal rendelkezik és ez hozzá van rendelve a **Houston** csatornához.</span><span class="sxs-lookup"><span data-stu-id="207af-131">You have the price group **Houston-PG** and it is assigned to the **Houston** channel.</span></span>
4. <span data-ttu-id="207af-132">Miután létrehozta az új **Vissza az iskolába** engedményt, akkor kattintson **Árcsoportok** az **Engedmény** lap tetején.</span><span class="sxs-lookup"><span data-stu-id="207af-132">After you create the new **Back-to-School** discount, you need to click **Price groups** on the top of the **Discount** page.</span></span> <span data-ttu-id="207af-133">Az **Árcsoportok engedménye engedmény** oldal jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="207af-133">The **Discount price groups** page will open.</span></span> <span data-ttu-id="207af-134">Ezután kattintson **Új** , és válassza ki a **Houston-PG** árcsoportot.</span><span class="sxs-lookup"><span data-stu-id="207af-134">Next, click **New** and select the **Houston-PG** price group.</span></span>
5. <span data-ttu-id="207af-135">Ezután engedélyezheti a kedvezményt és űthelyezheti a csatornába.</span><span class="sxs-lookup"><span data-stu-id="207af-135">Now you can enable the discount and push it to the channel.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="207af-136">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="207af-136">Additional resources</span></span>

[<span data-ttu-id="207af-137">Ármódosítások és engedmények</span><span class="sxs-lookup"><span data-stu-id="207af-137">Price adjustments and discounts</span></span>](price-adjustments-discounts.md)
