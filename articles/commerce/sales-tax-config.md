---
title: Az online rendelések áfájának konfigurálása
description: Ez a témakör áttekintést nyújt a különböző online rendeléstípusok áfacsoportjának kiválasztásáról a Dynamics 365 Commerce alkalmazásban.
author: gvrmohanreddy
manager: AnnBe
ms.date: 11/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: gmohanv
ms.search.validFrom: 2020-11-01
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 40c20bf13779f73289e43df21b763e1b864686a7
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/17/2020
ms.locfileid: "4530197"
---
# <a name="configure-sales-tax-for-online-orders"></a><span data-ttu-id="bad52-103">Az online rendelések áfájának konfigurálása</span><span class="sxs-lookup"><span data-stu-id="bad52-103">Configure sales tax for online orders</span></span>

[!include [banner](../includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="bad52-104">Ez a témakör áttekintést nyújt a különböző online rendeléstípusok áfacsoportjának kiválasztásáról.</span><span class="sxs-lookup"><span data-stu-id="bad52-104">This topic provides an overview of sales tax group selection for different online order types.</span></span> 

<span data-ttu-id="bad52-105">Előfordulhat, hogy az e-kereskedelmi csatornája támogatni szeretné az olyan lehetőségeket, mint a kézbesítés vagy az online rendelések felvétele.</span><span class="sxs-lookup"><span data-stu-id="bad52-105">Your e-commerce channel may want to support options like delivery or pickup for online orders.</span></span> <span data-ttu-id="bad52-106">Az áfa alkalmazhatósága az online felhasználók által kiválasztott beállításon alapul.</span><span class="sxs-lookup"><span data-stu-id="bad52-106">The sales tax applicability is based on the option selected by your online users.</span></span> <span data-ttu-id="bad52-107">Amikor a webhely egyik ügyfele úgy dönt, hogy online vásárol egy cikket, és egy címre szállíttatja, az áfa meghatározása a vevő szállítási címéhez tartozó adócsoport beállításától függ.</span><span class="sxs-lookup"><span data-stu-id="bad52-107">When a site customer chooses to buy an item online and gets it shipped to an address, the sales tax is determined based on the customer's shipping address tax group setting.</span></span> <span data-ttu-id="bad52-108">Amikor egy vevő úgy dönt, hogy egy megvásárolt cikket vesz fel egy üzletben, az áfa meghatározása a felvételi üzlet adócsoportjának beállítása alapján történik.</span><span class="sxs-lookup"><span data-stu-id="bad52-108">When a customer opts to pick up a purchased item at a store, the sales tax is determined based on the pickup store's tax group setting.</span></span> 

## <a name="orders-shipped-to-a-customer-address"></a><span data-ttu-id="bad52-109">Vevői címre szállított rendelések</span><span class="sxs-lookup"><span data-stu-id="bad52-109">Orders shipped to a customer address</span></span> 

<span data-ttu-id="bad52-110">A vevői címekre szállítandó online rendelésekre kivetett adókat általában a cél határozza meg.</span><span class="sxs-lookup"><span data-stu-id="bad52-110">In general, taxes for online orders that ship to customer addresses are defined by the destination.</span></span> <span data-ttu-id="bad52-111">Minden áfacsoport rendelkezik egy kiskereskedelmi célalapú adókonfigurációval, amelyben a vállalkozás hierarchikus formában definiálhatja a céladatokat, például a megye/régió, az állam, a megye és a város értékét.</span><span class="sxs-lookup"><span data-stu-id="bad52-111">Every sales tax group has a retail destination-based tax configuration in which your business can define destination details such as county/region, state, county, and city in a hierarchical form.</span></span> <span data-ttu-id="bad52-112">Online rendelés leadásakor a Commerce adómotor a rendelés minden sorcikk szállítási címét használja, és megkeresi az áfacsoportokat a megfelelő célalapú adózási feltételekkel.</span><span class="sxs-lookup"><span data-stu-id="bad52-112">When an online order is placed, the Commerce tax engine uses the delivery address of every line item in the order, and finds sales tax groups with matching destination-based tax criteria.</span></span> <span data-ttu-id="bad52-113">Például egy olyan online rendelés esetén, amelynek sorcikkének szállítási címe San Franciscóban (Kalifornia) van, az adómotor megkeresi Kalifornia áfacsoportját és áfakódját, majd ennek megfelelően kiszámítja az adót minden sorra vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="bad52-113">For example, for an online order with a line item delivery address to San Francisco, California, the tax engine will find the sales tax group and sales tax code for California and then calculate tax for each line item accordingly.</span></span>  

## <a name="customer-based-tax-groups"></a><span data-ttu-id="bad52-114">Vevőalapú adócsoportok</span><span class="sxs-lookup"><span data-stu-id="bad52-114">Customer-based tax groups</span></span>

<span data-ttu-id="bad52-115">A Commerce központban két helyen van konfigurálva vevőadó-csoportok:</span><span class="sxs-lookup"><span data-stu-id="bad52-115">In Commerce headquarters, there are two places where customer tax groups are configured:</span></span>

- <span data-ttu-id="bad52-116">**Vevő profilja**</span><span class="sxs-lookup"><span data-stu-id="bad52-116">**Customer's profile**</span></span>
- <span data-ttu-id="bad52-117">**A vevő szállítási címe**</span><span class="sxs-lookup"><span data-stu-id="bad52-117">**Customer's shipping address**</span></span>

### <a name="if-a-customers-profile-has-a-tax-group-configured"></a><span data-ttu-id="bad52-118">Ha egy vevő profiljához be van állítva egy adócsoport</span><span class="sxs-lookup"><span data-stu-id="bad52-118">If a customer's profile has a tax group configured</span></span>

<span data-ttu-id="bad52-119">Előfordulhat, hogy a központban lévő vevői profilrekordhoz konfigurálva van egy áfacsoport, azonban az online rendelések esetében a vevő profiljában beállított áfacsoportot az adómotor nem fogja használni.</span><span class="sxs-lookup"><span data-stu-id="bad52-119">A customer's profile record in headquarters may have a sales tax group configured, however for online orders the sales tax group configured in a customer's profile will not be used by the tax engine.</span></span> 

### <a name="if-a-customers-shipping-address-has-a-tax-group-configured"></a><span data-ttu-id="bad52-120">Ha egy vevő szállítási címéhez be van állítva egy adócsoport</span><span class="sxs-lookup"><span data-stu-id="bad52-120">If a customer's shipping address has a tax group configured</span></span>

<span data-ttu-id="bad52-121">Ha a vevő szállítási cím rekordjánál adócsoport van konfigurálva, és egy online rendelést (vagy sorelemet) szállítanak a vevő szállítási címére, akkor a vevő címrekordjában beállított adócsoportot az adómotor fogja használni az adószámítási célokra.</span><span class="sxs-lookup"><span data-stu-id="bad52-121">If a customer's shipping address record has a tax group configured and an online order (or line item) is shipped to the customer's shipping address, the tax group configured in the customer's address record will be used by the tax engine for tax calculations.</span></span>

#### <a name="configure-a-tax-group-for-a-customers-shipping-address-record"></a><span data-ttu-id="bad52-122">Adócsoport konfigurálása egy vevő szállítási cím rekordjához</span><span class="sxs-lookup"><span data-stu-id="bad52-122">Configure a tax group for a customer's shipping address record</span></span>

<span data-ttu-id="bad52-123">Ha egy vevő szállítási cím rekordjának adócsoportját szeretné konfigurálni a Commerce-központban, kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="bad52-123">To configure a tax group for a customer's shipping address record in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="bad52-124">Nyissa meg az **Összes ügyfél** lehetőséget, és válassza ki a kívánt ügyfelet.</span><span class="sxs-lookup"><span data-stu-id="bad52-124">Go to **All customers**, and then select the desired customer.</span></span> 
1. <span data-ttu-id="bad52-125">A **Címek** gyorslapon válassza ki a kívánt címet, majd válassza a **További beállítások \> Speciális** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="bad52-125">On the **Addresses** FastTab, select the desired address, and then select **More options \> Advanced**.</span></span> 
1. <span data-ttu-id="bad52-126">A **Címek kezelése** oldal **Általános** lapján szükség szerint állítsa be az áfaértékét.</span><span class="sxs-lookup"><span data-stu-id="bad52-126">Under the **General** tab on the **Manage addresses** page, set the sales tax value as needed.</span></span>

> [!NOTE]
> <span data-ttu-id="bad52-127">Az adócsoport a rendelési sor szállítási címe alapján van definiálva, és a célalapú adók az adócsoportnál vannak konfigurálva.</span><span class="sxs-lookup"><span data-stu-id="bad52-127">The tax group is defined using the delivery address of the order line and the destination-based taxes are configured at the tax group itself.</span></span> <span data-ttu-id="bad52-128">További információ: [Online áruházak adóinak beállítása cél alapján](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-taxes-for-online-stores-based-on-destination) című témakörben olvashat.</span><span class="sxs-lookup"><span data-stu-id="bad52-128">For more information, see [Set up taxes for online stores based on destination](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-taxes-for-online-stores-based-on-destination).</span></span>

## <a name="order-pickup-in-store"></a><span data-ttu-id="bad52-129">Rendelésfelvétel az üzletben</span><span class="sxs-lookup"><span data-stu-id="bad52-129">Order pickup in store</span></span>

<span data-ttu-id="bad52-130">Az üzletbeli vagy a járdaszéli felvétellel megadott csomagfelvételeket megadó rendeléssorok esetén a kiválasztott átvételi áruház adócsoportja lesz alkalmazva.</span><span class="sxs-lookup"><span data-stu-id="bad52-130">For order lines with pickup in store or curbside pickup specified, the tax group from the selected pickup store will be applied.</span></span> <span data-ttu-id="bad52-131">Az adócsoport adott üzlethez való konfigurálásáról az [Üzletek egyéb adóbeállításainak megadása](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-other-tax-options-for-stores) című témakörben talál további tudnivalókat.</span><span class="sxs-lookup"><span data-stu-id="bad52-131">For details about how to configure the tax group for a given store, see [Set other tax options for stores](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-other-tax-options-for-stores).</span></span>

> [!NOTE]
> <span data-ttu-id="bad52-132">Amikor egy rendelési sort üzletben való átvételekor, a vevői cím adóbeállításait (ha be van állítva) az adómotor figyelmen kívül hagyja, és az átvételi üzlet adókonfigurációját alkalmazza.</span><span class="sxs-lookup"><span data-stu-id="bad52-132">When an order line is picked up at a store, a customer's address tax settings (if set up) will be ignored by the tax engine and the pickup store's tax configuration will be applied.</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="bad52-133">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="bad52-133">Additional resources</span></span>

[<span data-ttu-id="bad52-134">Áfa áttekintése</span><span class="sxs-lookup"><span data-stu-id="bad52-134">Sales tax overview</span></span>](https://docs.microsoft.com/dynamics365/finance/general-ledger/indirect-taxes-overview?toc=/dynamics365/commerce/toc.json) 

[<span data-ttu-id="bad52-135">Áfaszámítási módok a Kiindulás mezőben</span><span class="sxs-lookup"><span data-stu-id="bad52-135">Sales tax calculation methods in the Origin field</span></span>](https://docs.microsoft.com/dynamics365/finance/general-ledger/sales-tax-calculation-methods-origin-field?toc=/dynamics365/commerce/toc.json) 

[<span data-ttu-id="bad52-136">Áfa-hozzárendelés és felülbírálások</span><span class="sxs-lookup"><span data-stu-id="bad52-136">Sales tax assignment and overrides</span></span>](https://docs.microsoft.com/dynamics365/supply-chain/procurement/tasks/sales-tax-assignment-overrides?toc=/dynamics365/commerce/toc.json) 

[<span data-ttu-id="bad52-137">Teljesösszeg- és intervallumszámítási opciók áfakódokhoz</span><span class="sxs-lookup"><span data-stu-id="bad52-137">Whole amount and Interval calculation options for sales tax codes</span></span>](https://docs.microsoft.com/dynamics365/finance/general-ledger/whole-amount-interval-options-sales-tax-codes?toc=/dynamics365/commerce/toc.json) 

[<span data-ttu-id="bad52-138">Adómentesség számítása</span><span class="sxs-lookup"><span data-stu-id="bad52-138">Calculation of tax exemption</span></span>](tax-exempt-price-inclusive.md) 

