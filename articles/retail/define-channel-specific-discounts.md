---
title: "Csatornaspecifikus engedmények definiálása"
description: "A kiskereskedők gyakran különböző engedményeket állítanak be a különböző csatornákon. Ez a témakör ellenőrzi azokat a fogalmakat, amelyeket a megadott csatornára vonatkozó engedmények létrehozásához tudnia kell."
author: scott-tucker
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
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
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: f68400bf10b6235decc7ac5cb82e58b369c7c0c7
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="define-channel-specific-discounts"></a><span data-ttu-id="fa72b-104">Csatornaspecifikus engedmények definiálása</span><span class="sxs-lookup"><span data-stu-id="fa72b-104">Define channel-specific discounts</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="fa72b-105">A kiskereskedők gyakran különböző engedményeket állítanak be a különböző csatornákon.</span><span class="sxs-lookup"><span data-stu-id="fa72b-105">Retailers often set different discounts in different channels.</span></span> <span data-ttu-id="fa72b-106">Ez a témakör ellenőrzi azokat a fogalmakat, amelyeket a megadott csatornára vonatkozó engedmények létrehozásához tudnia kell.</span><span class="sxs-lookup"><span data-stu-id="fa72b-106">This topic reviews the concepts you need to know to create a discount for a specific channel.</span></span> 

<a name="channel-specific-discounts"></a><span data-ttu-id="fa72b-107">Csatornaspecifikus engedmények</span><span class="sxs-lookup"><span data-stu-id="fa72b-107">Channel-specific discounts</span></span>
--------------------------

<span data-ttu-id="fa72b-108">A kiskereskedők gyakran különböző engedményeket ajánlanak a különböző csatornákon.</span><span class="sxs-lookup"><span data-stu-id="fa72b-108">Retailers often offer different discounts in different channels.</span></span> <span data-ttu-id="fa72b-109">Ezt tehetik a helyi piaci feltétetelek kezelése vagy a versenytárs kiskereskedők legyőzése érdekében.</span><span class="sxs-lookup"><span data-stu-id="fa72b-109">This is may be done to address local market conditions or to deal with competing retailers.</span></span>

<span data-ttu-id="fa72b-110">A Microsoft Dynamics 365 for Retail árcsoportok segítségével csatornaspecifikus engedményeket határoz meg.</span><span class="sxs-lookup"><span data-stu-id="fa72b-110">Microsoft Dynamics 365 for Retail uses price groups to define channel-specific discounts.</span></span> <span data-ttu-id="fa72b-111">Az árcsoportok a következő entitások egy vagy több lehetőségéhez rendelhetők hozzá: csatornák, katalógusok, fiókok és hűségprogramok.</span><span class="sxs-lookup"><span data-stu-id="fa72b-111">Price groups can be assigned to one or more of the following entities: channels, catalogs, affiliations, and loyalty programs.</span></span> <span data-ttu-id="fa72b-112">A cikk a csatornákat tárgyalja, de az azonos koncepciók a katalógus engedményekre, fiók engedményekre és a hűséges engedményekre vonatkoznak.</span><span class="sxs-lookup"><span data-stu-id="fa72b-112">This article discusses channels, but the same concepts apply to catalog discounts, affiliations discounts, and loyalty discounts.</span></span>

## <a name="price-groups"></a><span data-ttu-id="fa72b-113">Árcsoportok</span><span class="sxs-lookup"><span data-stu-id="fa72b-113">Price groups</span></span>

<span data-ttu-id="fa72b-114">[![Árcsoportok](./media/price-groups-1024x608.png)](./media/price-groups.png)</span><span class="sxs-lookup"><span data-stu-id="fa72b-114">[![Price groups](./media/price-groups-1024x608.png)](./media/price-groups.png)</span></span>

<span data-ttu-id="fa72b-115">A fenti ábra bemutatja a tranzakciókban megtalálható (csatorna, katalógus, fiók, vevő, hűségkártya) entitások és a különféle konfigurálható engedménytípusok közötti kapcsolatot.</span><span class="sxs-lookup"><span data-stu-id="fa72b-115">The diagram above illustrates the relationship between entities that may be on a transaction (channel, catalog, affiliation, customer, loyalty card) and the various discount types that can be configured.</span></span> <span data-ttu-id="fa72b-116">Az összes tranzakció egy csatornában fordul elő, így a csatorna garantáltan rajta van egy tranzakción.</span><span class="sxs-lookup"><span data-stu-id="fa72b-116">All transactions occur in a channel, so the channel is guaranteed to be present on a transaction.</span></span> <span data-ttu-id="fa72b-117">A fennmaradó entitások megadása nem kötelező.</span><span class="sxs-lookup"><span data-stu-id="fa72b-117">The remaining entities are optional.</span></span> <span data-ttu-id="fa72b-118">Minden egyes alapadat lapon van egy hivatkozás a kapcsolódó árcsoportok lapjához, ahol megtekintheti az árcsoportokat és szükség szerint hozzá is adhat árcsoportokat.</span><span class="sxs-lookup"><span data-stu-id="fa72b-118">On each master data pages there is a link to a related price groups page where you can view and add price groups as needed.</span></span> <span data-ttu-id="fa72b-119">Az árcsoportok segítségével az entitások négy különböző típusát kapcsolják össze az engedményekkel, az ármódosításokkal és kereskedelmi megállapodásokkal.</span><span class="sxs-lookup"><span data-stu-id="fa72b-119">A price group is used to relate four different types of entities to discounts, price adjustments, and trade agreements.</span></span> <span data-ttu-id="fa72b-120">Azt ajánljuk, hogy tervezzen meg egy stratégiát, hogyan fogja az árcsoportjait elnevezni annak érdekében, hogy rendben tartsa őket.</span><span class="sxs-lookup"><span data-stu-id="fa72b-120">We recommend that you plan a strategy for how you will name your price groups to keep them organized.</span></span> <span data-ttu-id="fa72b-121">Például egy betű- vagy számelőtag vagy -utótag segítségével megkülönböztet különféle típusokat.</span><span class="sxs-lookup"><span data-stu-id="fa72b-121">One option would be to use a letter or number prefix or suffix to distinguish between the different types.</span></span> <span data-ttu-id="fa72b-122">Például 1-xxxxx a csatornaárcsoportok és 2-xxxxx a katalógusárcsoportok számára.</span><span class="sxs-lookup"><span data-stu-id="fa72b-122">For example, 1-xxxxx for channel price groups and 2-xxxxx for catalog price groups.</span></span> <span data-ttu-id="fa72b-123">Négy lekérdezési oldal van, amely valamennyi engedményekhez rendelt kiskereskedelmi entitásra fókuszál.</span><span class="sxs-lookup"><span data-stu-id="fa72b-123">There are four inquiry pages that focus on each of the retail entities that can have discounts associated to them.</span></span>

-   <span data-ttu-id="fa72b-124">**Kiskereskedelmi csatorna árcsoportjai**– Ez a lap megjeleníti a minden egyes árcsoporthoz kapcsolódó engedmények és csatornák listáját.</span><span class="sxs-lookup"><span data-stu-id="fa72b-124">**Retail channel price groups** - This page shows a list of channels and discounts linked together for each price group.</span></span>
-   <span data-ttu-id="fa72b-125">**Katalógus árcsoportjai**– Ez a lap megjeleníti a minden egyes árcsoporthoz kapcsolódó engedmények és katalógusok listáját.</span><span class="sxs-lookup"><span data-stu-id="fa72b-125">**Catalog price groups** - This page shows a list of catalogs and discounts linked together for each price group.</span></span>
-   <span data-ttu-id="fa72b-126">**Hűség árcsoportjai**– Ez a lap megjeleníti a minden egyes árcsoporthoz kapcsolódó engedmények és hűségprogramok listáját.</span><span class="sxs-lookup"><span data-stu-id="fa72b-126">**Loyalty price groups** - This page shows a list of loyalty programs and discounts linked together for each price group.</span></span>
-   <span data-ttu-id="fa72b-127">**Fiók árcsoportjai**– Ez a lap megjeleníti a minden egyes árcsoporthoz kapcsolódó engedmények és fiókok listáját.</span><span class="sxs-lookup"><span data-stu-id="fa72b-127">**Affiliation price groups** - This page shows a list of affiliations and discounts linked together for each price group.</span></span>

## <a name="example-channel-discount-set-up"></a><span data-ttu-id="fa72b-128">Csatorna kedvezmény beállítás példája</span><span class="sxs-lookup"><span data-stu-id="fa72b-128">Example channel discount set up</span></span>
<span data-ttu-id="fa72b-129">A következő példa bemutatja egy csatorna engedmény beállításába bevont feladatokat.</span><span class="sxs-lookup"><span data-stu-id="fa72b-129">The following example illustrates the tasks involved in setting up a channel discount.</span></span>

1.  <span data-ttu-id="fa72b-130">Ebben a példában egy úgynevezett **Houston** csatornával rendelkezik, és egy **Vissza az iskolába** nevezett új engedményt fog létrehozni.</span><span class="sxs-lookup"><span data-stu-id="fa72b-130">For this example, you have a channel called **Houston**, and you're going to create a new discount called **Back-to-School.**</span></span>
2.  <span data-ttu-id="fa72b-131">Mivel az árképzés és az engedmény stratégia csatorna engedmények lehetőségét tartalmazza, mindig létrehoz csatornaspecifikus árcsoportot egy csatorna létrehozásakor.</span><span class="sxs-lookup"><span data-stu-id="fa72b-131">Because the pricing and discount strategy includes the possibility of channel discounts, you always create a channel-specific price group when you create a channel.</span></span>
3.  <span data-ttu-id="fa72b-132">**Houston-PG** árcsoporttal rendelkezik és ez hozzá van rendelve a **Houston** csatornához.</span><span class="sxs-lookup"><span data-stu-id="fa72b-132">You have the price group **Houston-PG** and it is assigned to the **Houston** channel.</span></span>
4.  <span data-ttu-id="fa72b-133">Miután létrehozta az új **Vissza az iskolába** engedményt, akkor kattintson **Árcsoportok** az **Engedmény** lap tetején.</span><span class="sxs-lookup"><span data-stu-id="fa72b-133">After you create the new **Back-to-School** discount, you need to click **Price groups** on the top of the **Discount** page.</span></span> <span data-ttu-id="fa72b-134">Az **Árcsoportok engedménye engedmény** oldal jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="fa72b-134">The **Discount price groups** page will open.</span></span> <span data-ttu-id="fa72b-135">Ezután kattintson **Új** , és válassza ki a **Houston-PG** árcsoportot.</span><span class="sxs-lookup"><span data-stu-id="fa72b-135">Next, click **New** and select the **Houston-PG** price group.</span></span>
5.  <span data-ttu-id="fa72b-136">Ezután engedélyezheti a kedvezményt és űthelyezheti a csatornába.</span><span class="sxs-lookup"><span data-stu-id="fa72b-136">Now you can enable the discount and push it to the channel.</span></span>

 

<a name="see-also"></a><span data-ttu-id="fa72b-137">Lásd még</span><span class="sxs-lookup"><span data-stu-id="fa72b-137">See also</span></span>
--------

[<span data-ttu-id="fa72b-138">Ármódosítások és engedmények</span><span class="sxs-lookup"><span data-stu-id="fa72b-138">Price adjustments and discounts</span></span>](price-adjustments-discounts.md)




