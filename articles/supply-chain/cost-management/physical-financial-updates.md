---
title: Pénzügyi és fizikai frissítések
description: Ez a témakör áttekintést ad a készlet mennyiségét növelő vagy csökkentő tranzakciók típusairól.
author: AndersGirke
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTrans, InventTransVoucher
audience: Application User
ms.reviewer: kamaybac
ms.custom: 75023
ms.assetid: 128340e1-c573-48e6-b835-6c350d8dd0fb
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 88432b9a5e564f9e81892e0bb379f95ff40d6c9d
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5842153"
---
# <a name="physical-and-financial-updates"></a><span data-ttu-id="871ec-103">Pénzügyi és fizikai frissítések</span><span class="sxs-lookup"><span data-stu-id="871ec-103">Physical and financial updates</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="871ec-104">Ez a témakör áttekintést ad a készlet mennyiségét növelő vagy csökkentő tranzakciók típusairól.</span><span class="sxs-lookup"><span data-stu-id="871ec-104">This topic provides an overview of which types of transactions increase or decrease inventory quantities.</span></span> 

<span data-ttu-id="871ec-105">A készlettranzakciók fizikailag és pénzügyileg is frissíthetőek a Dynamics 365 Supply Chain Management rendszerben.</span><span class="sxs-lookup"><span data-stu-id="871ec-105">Inventory transactions can be physically updated and financially updated in Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="871ec-106">Egyes fizikai és pénzügyi tranzakciótípusok növelik a készlet mennyiségét, míg mások csökkentik.</span><span class="sxs-lookup"><span data-stu-id="871ec-106">Some types of physical and financial transactions increase inventory quantities, whereas others decrease the quantity.</span></span>

## <a name="physical-increases"></a><span data-ttu-id="871ec-107">Fizikai növekedések</span><span class="sxs-lookup"><span data-stu-id="871ec-107">Physical increases</span></span>
<span data-ttu-id="871ec-108">Fizikai tranzakció feladásakor a tranzakciórekord állapota **Beérkezett**.</span><span class="sxs-lookup"><span data-stu-id="871ec-108">When a physical transaction is posted, the status of the transaction record is **Received**.</span></span> <span data-ttu-id="871ec-109">A következő tranzakciók tekintendők fizikai mennyiségnövekedésnek:</span><span class="sxs-lookup"><span data-stu-id="871ec-109">The following transactions are considered physical increases:</span></span>

-   <span data-ttu-id="871ec-110">Beszerzési rendelés – bevételezés</span><span class="sxs-lookup"><span data-stu-id="871ec-110">Purchase order receipt</span></span>
-   <span data-ttu-id="871ec-111">Értékesítési rendelés – csomagjegyzék – visszáru</span><span class="sxs-lookup"><span data-stu-id="871ec-111">Sales order packing slip return</span></span>
-   <span data-ttu-id="871ec-112">Termelési rendelés készként jelentése</span><span class="sxs-lookup"><span data-stu-id="871ec-112">Reporting a production order as finished</span></span>
-   <span data-ttu-id="871ec-113">Termelési rendelés – kitárolási lista mellékterméke</span><span class="sxs-lookup"><span data-stu-id="871ec-113">By-product on a production order picking list</span></span>

## <a name="financial-increases"></a><span data-ttu-id="871ec-114">Pénzügyi növekedések</span><span class="sxs-lookup"><span data-stu-id="871ec-114">Financial increases</span></span>
<span data-ttu-id="871ec-115">Pénzügyi bevételezési tranzakció feladásakor a mennyiséget növelő tranzakciórekord állapota **Beszerezve**.</span><span class="sxs-lookup"><span data-stu-id="871ec-115">When a financial receipt transaction is posted, the status of the transaction record that increases the quantity is **Purchased**.</span></span> <span data-ttu-id="871ec-116">A következő tranzakciók tekintendők pénzügyi mennyiségnövekedésnek:</span><span class="sxs-lookup"><span data-stu-id="871ec-116">The following transactions are considered financial increases:</span></span>

-   <span data-ttu-id="871ec-117">Szállítói számla</span><span class="sxs-lookup"><span data-stu-id="871ec-117">Vendor invoice</span></span>
-   <span data-ttu-id="871ec-118">Visszáru értékesítési rendelése – számla</span><span class="sxs-lookup"><span data-stu-id="871ec-118">Sales order invoice for a return</span></span>
-   <span data-ttu-id="871ec-119">Termelési megrendelés költségszámítása</span><span class="sxs-lookup"><span data-stu-id="871ec-119">Production order costing</span></span>
-   <span data-ttu-id="871ec-120">Pozitív mennyiségű készletnaplók, például mozgás-, eredmény- és leltárnaplók, anyagjegyzékek és átmozgatás</span><span class="sxs-lookup"><span data-stu-id="871ec-120">Positive quantity inventory journals, such as movement, profit and loss, counting, bill of materials, and transfer</span></span>

## <a name="transactions-that-increase-quantity"></a><span data-ttu-id="871ec-121">Mennyiséget növelő tranzakciók</span><span class="sxs-lookup"><span data-stu-id="871ec-121">Transactions that increase quantity</span></span>
<span data-ttu-id="871ec-122">A mozgóátlagon alapuló önköltségi ár mennyiséget növelő tranzakciók feladása.</span><span class="sxs-lookup"><span data-stu-id="871ec-122">Transactions that increase quantity are posted at the running average cost price.</span></span> <span data-ttu-id="871ec-123">A cikkhez kiszámított mozgóátlagon alapuló önköltségi ár a pénzügyileg követett egyes készletdimenziók tranzakcióinak költségén alapul.</span><span class="sxs-lookup"><span data-stu-id="871ec-123">The calculated running average cost price is based on the cost of each of these transactions for each inventory dimension that is being tracked financially.</span></span> <span data-ttu-id="871ec-124">A mozgóátlagos önköltségi árakkal kapcsolatos további tudnivalókat lásd: [Mozgóátlagon alapuló önköltségi árak](running-average-cost-price.md).</span><span class="sxs-lookup"><span data-stu-id="871ec-124">For information about running average cost prices, see [Running average cost price](running-average-cost-price.md).</span></span>

## <a name="transactions-that-decrease-quantity"></a><span data-ttu-id="871ec-125">Mennyiséget csökkentő tranzakciók</span><span class="sxs-lookup"><span data-stu-id="871ec-125">Transactions that decrease quantity</span></span>
<span data-ttu-id="871ec-126">A számított mozgóátlagon alapuló önköltségi ár használt a mennyiséget csökkentő tranzakció feladásakor, függetlenül attól, mely készletmodell van társítva a készlethez.</span><span class="sxs-lookup"><span data-stu-id="871ec-126">The calculated running average cost price is used  when a transaction that decreases quantity is posted, regardless of the inventory model that is associated with that inventory.</span></span> <span data-ttu-id="871ec-127">A mennyiséget csökkentő tranzakció a feladás előtt korábban nem lehetett megjelölve egy másik tranzakcióhoz.</span><span class="sxs-lookup"><span data-stu-id="871ec-127">The transaction that decreases quantity must not have been marked to another transaction before it was posted.</span></span> <span data-ttu-id="871ec-128">Ha a fizikai tényleges készlet negatívvá válik, a készletköltség használt, amely meg van határozva a cikkhez a **Cikk** oldalon.</span><span class="sxs-lookup"><span data-stu-id="871ec-128">If the physical on-hand inventory becomes negative, the inventory cost that is defined for the item on the **Item** page is used.</span></span> 

> [!NOTE]
> <span data-ttu-id="871ec-129">Ha engedélyezve van a többhelyes funkció, ez a költség ehelyett az a készletköltség lesz, amely a helyhez van meghatározva az **Alapértelmezett rendelésbeállítások** képernyőn.</span><span class="sxs-lookup"><span data-stu-id="871ec-129">If multisite functionality is enabled, this cost will instead be the inventory cost that is defined for a site on the **Default order settings** page.</span></span>

## <a name="physical-issues-vs-financial-issues"></a><span data-ttu-id="871ec-130">Pénzügyi kiadások és a tényleges kiadások</span><span class="sxs-lookup"><span data-stu-id="871ec-130">Physical issues vs. financial issues</span></span>
<span data-ttu-id="871ec-131">Fizikai kiadási tranzakció feladásakor a tranzakciórekord állapota **Levonva**.</span><span class="sxs-lookup"><span data-stu-id="871ec-131">When a physical issue transaction is posted, the status of the transaction record is **Deducted**.</span></span> <span data-ttu-id="871ec-132">A következő tranzakciók tekintendők fizikai kiadásnak:</span><span class="sxs-lookup"><span data-stu-id="871ec-132">The following transactions are considered physical issues:</span></span>

-   <span data-ttu-id="871ec-133">Termelési rendelés – kitárolásilista-napló</span><span class="sxs-lookup"><span data-stu-id="871ec-133">Production order picking list journal</span></span>
-   <span data-ttu-id="871ec-134">Értékesítési rendelés - csomagjegyzék</span><span class="sxs-lookup"><span data-stu-id="871ec-134">Sales order packing slip</span></span>
-   <span data-ttu-id="871ec-135">Beszerzési rendelés – csomagjegyzék – visszáru</span><span class="sxs-lookup"><span data-stu-id="871ec-135">Purchase order packing slip return</span></span>

<span data-ttu-id="871ec-136">Pénzügyi tranzakció feladásakor a tranzakciórekord állapota **Eladva**.</span><span class="sxs-lookup"><span data-stu-id="871ec-136">When a financial transaction is posted, the status of the transaction record is **Sold**.</span></span> <span data-ttu-id="871ec-137">A következő tranzakciók tekintendők pénzügyi kiadásnak:</span><span class="sxs-lookup"><span data-stu-id="871ec-137">The following transactions are considered financial issues:</span></span>

-   <span data-ttu-id="871ec-138">A termelési rendelések befejezése</span><span class="sxs-lookup"><span data-stu-id="871ec-138">Ending a production order</span></span>
-   <span data-ttu-id="871ec-139">Értékesítési rendelés - számla</span><span class="sxs-lookup"><span data-stu-id="871ec-139">Sales order invoice</span></span>
-   <span data-ttu-id="871ec-140">Szállítói számlaforgalom</span><span class="sxs-lookup"><span data-stu-id="871ec-140">Vendor invoice return</span></span>
-   <span data-ttu-id="871ec-141">Negatív mennyiségű készletnaplók, például mozgás-, eredmény- és leltárnaplók, anyagjegyzékek és átmozgatás</span><span class="sxs-lookup"><span data-stu-id="871ec-141">Negative quantity inventory journals, such as movement, profit and loss, counting, bill of materials, and transfer</span></span>

<span data-ttu-id="871ec-142">A mozgóátlagon alapuló önköltségi ár mennyiséget csökkentő tranzakciók feladása.</span><span class="sxs-lookup"><span data-stu-id="871ec-142">Transactions that decrease quantity are posted at the running average cost price.</span></span> <span data-ttu-id="871ec-143">Így a készletzárás folyamata a cikk készletmodellben kiválasztott készletértékelési módszer alapján a kiadási tranzakciókat a bevételezési tranzakciókkal szemben egyenlíti ki.</span><span class="sxs-lookup"><span data-stu-id="871ec-143">Therefore, the inventory close procedure is required in order to settle issue transactions to receipt transactions, based on the inventory model that is assigned to each item.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]