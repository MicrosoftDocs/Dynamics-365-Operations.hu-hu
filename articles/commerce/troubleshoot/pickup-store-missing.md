---
title: A kiskereskedelmi üzlet nem jelenik meg a felvételt lehetővé tevő üzletek listájában
description: Ez a témakör olyan hibaelhárítási útmutatást tartalmaz, amelyek segítséget nyújtanak abban az esetben, ha egy kiskereskedelmi üzlet nem jelenik meg azon üzletek listájában, ahol felvehető az áru.
author: Reza-Assadi
manager: AnnBe
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
ms.openlocfilehash: 652f5f1a779a412c21c18814071ba0fb7dd2e155
ms.sourcegitcommit: 6c108be3378b365e6ec596a1a8666d59b758db25
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/12/2021
ms.locfileid: "5585364"
---
# <a name="retail-store-doesnt-appear-in-the-list-of-stores-to-pick-up-from"></a><span data-ttu-id="7b570-103">A kiskereskedelmi üzlet nem jelenik meg a felvételt lehetővé tevő üzletek listájában</span><span class="sxs-lookup"><span data-stu-id="7b570-103">Retail store doesn't appear in the list of stores to pick up from</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="7b570-104">Ez a témakör olyan hibaelhárítási útmutatást tartalmaz, amelyek segítséget nyújtanak abban az esetben, ha egy kiskereskedelmi üzlet nem jelenik meg azon üzletek listájában, ahol felvehető az áru.</span><span class="sxs-lookup"><span data-stu-id="7b570-104">This topic provides troubleshooting guidance that can help when a retail store doesn't appear in the list of stores where items can be picked up.</span></span>

## <a name="description"></a><span data-ttu-id="7b570-105">Leírás</span><span class="sxs-lookup"><span data-stu-id="7b570-105">Description</span></span>

<span data-ttu-id="7b570-106">A kiskereskedelmi üzlet nem jelenik meg azon üzletek listáján, amelyekben felvehető az áru.</span><span class="sxs-lookup"><span data-stu-id="7b570-106">A retail store doesn't appear in the list of stores where items can be picked up.</span></span>

## <a name="resolution"></a><span data-ttu-id="7b570-107">Felbontás</span><span class="sxs-lookup"><span data-stu-id="7b570-107">Resolution</span></span>

### <a name="configure-the-longitude-and-latitude-for-the-store-address-in-commerce-headquarters"></a><span data-ttu-id="7b570-108">Az üzlet címét jelző földrajzi hosszúság és szélesség beállítása a Commerce központi felületén</span><span class="sxs-lookup"><span data-stu-id="7b570-108">Configure the longitude and latitude for the store address in Commerce headquarters</span></span>

<span data-ttu-id="7b570-109">Az üzlet címét jelző földrajzi hosszúság és szélesség beállításához a Commerce központi felületén kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="7b570-109">To configure the longitude and latitude for the store address in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="7b570-110">Ugorjon a következő oldalra: **Kiskereskedelem és kereskedelem \> Csatornák \> Üzletek \> Minden kiskereskedelmi üzlet**.</span><span class="sxs-lookup"><span data-stu-id="7b570-110">Go to **Retail and Commerce \> Channels \> Stores \> All stores**.</span></span>
1. <span data-ttu-id="7b570-111">Keresse meg azt az üzletet, amelyet meg szeretne jeleníteni a felvételi lehetőségek az e-kereskedelmi webhelyen.</span><span class="sxs-lookup"><span data-stu-id="7b570-111">Find the store that you want to appear among the pickup options on the e-commerce site.</span></span> <span data-ttu-id="7b570-112">Jegyezze fel az **Üzemi egység száma** értékét.</span><span class="sxs-lookup"><span data-stu-id="7b570-112">Make a note of its **Operating unit number** value.</span></span>
1. <span data-ttu-id="7b570-113">Nyissa meg a következőt: **Szervezeti adminisztráció \> Szervezetek \> Üzemi egységek**.</span><span class="sxs-lookup"><span data-stu-id="7b570-113">Go to **Organization administration \> Organizations \> Operating units**.</span></span>
1. <span data-ttu-id="7b570-114">Keresse meg a korábban feljegyzett üzemi egység számát, majd válassza ki az üzemi egységet a keresési eredmények közül.</span><span class="sxs-lookup"><span data-stu-id="7b570-114">Search for the operating unit number that you noted earlier, and then select the operating unit in the search results.</span></span>
1. <span data-ttu-id="7b570-115">A **Címek** gyorslapon válassza a **További beállítások** lehetőséget, majd válassza a **Speciális** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7b570-115">On the **Addresses** FastTab, select **More options**, and then select **Advanced**.</span></span>
1. <span data-ttu-id="7b570-116">Az **Általános** gyorslapon ellenőrizze, hogy helyesen van-e beállítva a **Földrajzi hosszúság** és a **Földrajzi szélesség** mező.</span><span class="sxs-lookup"><span data-stu-id="7b570-116">On the **General** FastTab, make sure that the **Longitude** and **Latitude** fields are correctly set.</span></span> <span data-ttu-id="7b570-117">Ennek a lépésnek a részeként ellenőrizze, hogy az értékek helyesen vannak-e megadva pozitív vagy negatív számként.</span><span class="sxs-lookup"><span data-stu-id="7b570-117">As part of this step, make sure that the values are correctly specified as positive or negative numbers.</span></span>

### <a name="configure-fulfillment-groups-in-commerce-headquarters"></a><span data-ttu-id="7b570-118">Teljesítési csoportok konfigurálása a Commerce központi felületén</span><span class="sxs-lookup"><span data-stu-id="7b570-118">Configure fulfillment groups in Commerce headquarters</span></span>

<span data-ttu-id="7b570-119">A teljesítési csoportok Commerce központi felületén történő konfigurálásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="7b570-119">To configure fulfillment groups in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="7b570-120">Nyissa meg a következőt: **Retail és Commerce \> Csatornák \> Online áruházak**.</span><span class="sxs-lookup"><span data-stu-id="7b570-120">Go to **Retail and Commerce \> Channels \> Online stores**.</span></span>
1. <span data-ttu-id="7b570-121">Válassza ki a konfigurálni kívánt online üzletet.</span><span class="sxs-lookup"><span data-stu-id="7b570-121">Select the online store to configure.</span></span>
1. <span data-ttu-id="7b570-122">A műveleti ablaktáblán válassza a **Beállítás** lehetőséget, majd válassza ki a **Teljesítési csoport hozzárendelése** elemet.</span><span class="sxs-lookup"><span data-stu-id="7b570-122">On the Action Pane, select **Set up**, and then select **Fulfillment group assignment**.</span></span>
1. <span data-ttu-id="7b570-123">A **Teljesítési csoportok hozzárendelése** oldalon válassza ki az online üzlet teljesítési csoportját.</span><span class="sxs-lookup"><span data-stu-id="7b570-123">On the **Fulfillment group assignment** page, select the fulfillment group for the online store.</span></span>
1. <span data-ttu-id="7b570-124">A **Beállítás** csoportban győződjön meg arról, hogy a kiskereskedelmi üzlet megfelelően legyen konfigurálva a teljesítési csoporthoz.</span><span class="sxs-lookup"><span data-stu-id="7b570-124">Under **Setup**, make sure that the retail store is correctly configured for the fulfillment group.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="7b570-125">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="7b570-125">Additional resources</span></span> 

[<span data-ttu-id="7b570-126">Üzemi egység létrehozása</span><span class="sxs-lookup"><span data-stu-id="7b570-126">Create an operating unit</span></span>](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/tasks/create-operating-unit)

[<span data-ttu-id="7b570-127">Online csatorna beállítása</span><span class="sxs-lookup"><span data-stu-id="7b570-127">Set up an online channel</span></span>](../channel-setup-online.md)
