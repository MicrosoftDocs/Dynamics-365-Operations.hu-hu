---
title: A kiskereskedelmi üzlet nem jelenik meg a felvételt lehetővé tevő üzletek listájában
description: Ez a témakör olyan hibaelhárítási útmutatást tartalmaz, amelyek segítséget nyújtanak abban az esetben, ha egy kiskereskedelmi üzlet nem jelenik meg azon üzletek listájában, ahol felvehető az áru.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 9974b3e10bbdcd2e8a8723a3be4b70401bb9e546
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5801603"
---
# <a name="retail-store-doesnt-appear-in-the-list-of-stores-to-pick-up-from"></a><span data-ttu-id="e2ac8-103">A kiskereskedelmi üzlet nem jelenik meg a felvételt lehetővé tevő üzletek listájában</span><span class="sxs-lookup"><span data-stu-id="e2ac8-103">Retail store doesn't appear in the list of stores to pick up from</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="e2ac8-104">Ez a témakör olyan hibaelhárítási útmutatást tartalmaz, amelyek segítséget nyújtanak abban az esetben, ha egy kiskereskedelmi üzlet nem jelenik meg azon üzletek listájában, ahol felvehető az áru.</span><span class="sxs-lookup"><span data-stu-id="e2ac8-104">This topic provides troubleshooting guidance that can help when a retail store doesn't appear in the list of stores where items can be picked up.</span></span>

## <a name="description"></a><span data-ttu-id="e2ac8-105">Leírás</span><span class="sxs-lookup"><span data-stu-id="e2ac8-105">Description</span></span>

<span data-ttu-id="e2ac8-106">A kiskereskedelmi üzlet nem jelenik meg azon üzletek listáján, amelyekben felvehető az áru.</span><span class="sxs-lookup"><span data-stu-id="e2ac8-106">A retail store doesn't appear in the list of stores where items can be picked up.</span></span>

## <a name="resolution"></a><span data-ttu-id="e2ac8-107">Felbontás</span><span class="sxs-lookup"><span data-stu-id="e2ac8-107">Resolution</span></span>

### <a name="configure-the-longitude-and-latitude-for-the-store-address-in-commerce-headquarters"></a><span data-ttu-id="e2ac8-108">Az üzlet címét jelző földrajzi hosszúság és szélesség beállítása a Commerce központi felületén</span><span class="sxs-lookup"><span data-stu-id="e2ac8-108">Configure the longitude and latitude for the store address in Commerce headquarters</span></span>

<span data-ttu-id="e2ac8-109">Az üzlet címét jelző földrajzi hosszúság és szélesség beállításához a Commerce központi felületén kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="e2ac8-109">To configure the longitude and latitude for the store address in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="e2ac8-110">Ugorjon a következő oldalra: **Kiskereskedelem és kereskedelem \> Csatornák \> Üzletek \> Minden kiskereskedelmi üzlet**.</span><span class="sxs-lookup"><span data-stu-id="e2ac8-110">Go to **Retail and Commerce \> Channels \> Stores \> All stores**.</span></span>
1. <span data-ttu-id="e2ac8-111">Keresse meg azt az üzletet, amelyet meg szeretne jeleníteni a felvételi lehetőségek az e-kereskedelmi webhelyen.</span><span class="sxs-lookup"><span data-stu-id="e2ac8-111">Find the store that you want to appear among the pickup options on the e-commerce site.</span></span> <span data-ttu-id="e2ac8-112">Jegyezze fel az **Üzemi egység száma** értékét.</span><span class="sxs-lookup"><span data-stu-id="e2ac8-112">Make a note of its **Operating unit number** value.</span></span>
1. <span data-ttu-id="e2ac8-113">Nyissa meg a következőt: **Szervezeti adminisztráció \> Szervezetek \> Üzemi egységek**.</span><span class="sxs-lookup"><span data-stu-id="e2ac8-113">Go to **Organization administration \> Organizations \> Operating units**.</span></span>
1. <span data-ttu-id="e2ac8-114">Keresse meg a korábban feljegyzett üzemi egység számát, majd válassza ki az üzemi egységet a keresési eredmények közül.</span><span class="sxs-lookup"><span data-stu-id="e2ac8-114">Search for the operating unit number that you noted earlier, and then select the operating unit in the search results.</span></span>
1. <span data-ttu-id="e2ac8-115">A **Címek** gyorslapon válassza a **További beállítások** lehetőséget, majd válassza a **Speciális** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e2ac8-115">On the **Addresses** FastTab, select **More options**, and then select **Advanced**.</span></span>
1. <span data-ttu-id="e2ac8-116">Az **Általános** gyorslapon ellenőrizze, hogy helyesen van-e beállítva a **Földrajzi hosszúság** és a **Földrajzi szélesség** mező.</span><span class="sxs-lookup"><span data-stu-id="e2ac8-116">On the **General** FastTab, make sure that the **Longitude** and **Latitude** fields are correctly set.</span></span> <span data-ttu-id="e2ac8-117">Ennek a lépésnek a részeként ellenőrizze, hogy az értékek helyesen vannak-e megadva pozitív vagy negatív számként.</span><span class="sxs-lookup"><span data-stu-id="e2ac8-117">As part of this step, make sure that the values are correctly specified as positive or negative numbers.</span></span>

### <a name="configure-fulfillment-groups-in-commerce-headquarters"></a><span data-ttu-id="e2ac8-118">Teljesítési csoportok konfigurálása a Commerce központi felületén</span><span class="sxs-lookup"><span data-stu-id="e2ac8-118">Configure fulfillment groups in Commerce headquarters</span></span>

<span data-ttu-id="e2ac8-119">A teljesítési csoportok Commerce központi felületén történő konfigurálásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="e2ac8-119">To configure fulfillment groups in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="e2ac8-120">Nyissa meg a következőt: **Retail és Commerce \> Csatornák \> Online áruházak**.</span><span class="sxs-lookup"><span data-stu-id="e2ac8-120">Go to **Retail and Commerce \> Channels \> Online stores**.</span></span>
1. <span data-ttu-id="e2ac8-121">Válassza ki a konfigurálni kívánt online üzletet.</span><span class="sxs-lookup"><span data-stu-id="e2ac8-121">Select the online store to configure.</span></span>
1. <span data-ttu-id="e2ac8-122">A műveleti ablaktáblán válassza a **Beállítás** lehetőséget, majd válassza ki a **Teljesítési csoport hozzárendelése** elemet.</span><span class="sxs-lookup"><span data-stu-id="e2ac8-122">On the Action Pane, select **Set up**, and then select **Fulfillment group assignment**.</span></span>
1. <span data-ttu-id="e2ac8-123">A **Teljesítési csoportok hozzárendelése** oldalon válassza ki az online üzlet teljesítési csoportját.</span><span class="sxs-lookup"><span data-stu-id="e2ac8-123">On the **Fulfillment group assignment** page, select the fulfillment group for the online store.</span></span>
1. <span data-ttu-id="e2ac8-124">A **Beállítás** csoportban győződjön meg arról, hogy a kiskereskedelmi üzlet megfelelően legyen konfigurálva a teljesítési csoporthoz.</span><span class="sxs-lookup"><span data-stu-id="e2ac8-124">Under **Setup**, make sure that the retail store is correctly configured for the fulfillment group.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e2ac8-125">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="e2ac8-125">Additional resources</span></span> 

[<span data-ttu-id="e2ac8-126">Üzemi egység létrehozása</span><span class="sxs-lookup"><span data-stu-id="e2ac8-126">Create an operating unit</span></span>](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/tasks/create-operating-unit)

[<span data-ttu-id="e2ac8-127">Online csatorna beállítása</span><span class="sxs-lookup"><span data-stu-id="e2ac8-127">Set up an online channel</span></span>](../channel-setup-online.md)
