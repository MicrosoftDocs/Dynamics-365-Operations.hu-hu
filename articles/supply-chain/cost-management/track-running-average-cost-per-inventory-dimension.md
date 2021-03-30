---
title: Mozgóátlagon alapuló önköltségi ár követése készletdimenziónként
description: Egy készletdimenzió-csoport minden készletcikkhez hozzá van kapcsolva. Ezért a cikk mozgóátlagon alapuló önköltségi árának számítása ennek megfelelően a pénzügyileg követett készletdimenziók beállításán alapul.
author: AndersGirke
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventOnhandItem
audience: Application User
ms.reviewer: kamaybac
ms.custom: 75053
ms.assetid: 68cc00f4-0f7a-4a7d-be90-8f2e0d0563d3
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b2bf04a42edf09c35e81742b1c60db8944eba2ac
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5252870"
---
# <a name="track-running-average-cost-per-inventory-dimension"></a><span data-ttu-id="c8393-104">Mozgóátlagon alapuló önköltségi ár követése készletdimenziónként</span><span class="sxs-lookup"><span data-stu-id="c8393-104">Track running average cost per inventory dimension</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c8393-105">Egy készletdimenzió-csoport minden készletcikkhez hozzá van kapcsolva.</span><span class="sxs-lookup"><span data-stu-id="c8393-105">An inventory dimension group is attached to every inventory item.</span></span> <span data-ttu-id="c8393-106">Ezért a cikk mozgóátlagon alapuló önköltségi árának számítása ennek megfelelően a pénzügyileg követett készletdimenziók beállításán alapul.</span><span class="sxs-lookup"><span data-stu-id="c8393-106">Therefore, the running average cost price of an item is calculated based on the selected inventory dimensions that are being tracked financially.</span></span>

<span data-ttu-id="c8393-107">A készletdimenzióknak három típusa van: termék-, tárolási és nyomonkövetési.</span><span class="sxs-lookup"><span data-stu-id="c8393-107">There are three types of inventory dimensions: product, storage, and tracking.</span></span> <span data-ttu-id="c8393-108">A készletdimenziók tartalmazzák a konfiguráció, a méret és a szín adatait.</span><span class="sxs-lookup"><span data-stu-id="c8393-108">Product dimensions include configuration, size, and color.</span></span> <span data-ttu-id="c8393-109">A termékdimenziókat minden esetben pénzügyileg nyomon követi a rendszer.</span><span class="sxs-lookup"><span data-stu-id="c8393-109">Product dimensions are always tracked financially.</span></span> <span data-ttu-id="c8393-110">A tárolási és nyomonkövetési dimenziók tartalmazzák a telephely, a raktár, a hely, a készletállapot, az azonosítótábla, a kötegszám, és a sorozatszám adatait.</span><span class="sxs-lookup"><span data-stu-id="c8393-110">Storage and tracking dimensions include site, warehouse, location, inventory status, license plate, batch number, and serial number.</span></span> <span data-ttu-id="c8393-111">Ki lehet választani, hogy mely tárolási és nyomonkövetési dimenzióhoz történjen pénzügyi nyomon követés.</span><span class="sxs-lookup"><span data-stu-id="c8393-111">You can decide which storage and tracking dimensions are tracked financially.</span></span> 

<span data-ttu-id="c8393-112">**1. példa**</span><span class="sxs-lookup"><span data-stu-id="c8393-112">**Example 1**</span></span> 

<span data-ttu-id="c8393-113">Ha a cikkhez tartozó tárolási dimenzió-csoport raktár szerint van pénzügyileg nyomon követve, a mozgóátlagon alapuló önköltségi ár számítása raktáranként történik.</span><span class="sxs-lookup"><span data-stu-id="c8393-113">If the storage dimension group that is attached to the item is financially tracked by warehouse, the running average cost price is calculated per warehouse.</span></span> <span data-ttu-id="c8393-114">A következő beszerzési rendelések számlázása történt meg:</span><span class="sxs-lookup"><span data-stu-id="c8393-114">The following purchase orders have been invoiced:</span></span>

-   <span data-ttu-id="c8393-115">2 darabos beszerzési rendelés számlázása a GW raktárhoz 10,00 USD önköltségi áron történt.</span><span class="sxs-lookup"><span data-stu-id="c8393-115">A purchase order for a quantity of 2 at a cost price of USD 10.00 has been invoiced for warehouse GW.</span></span>
-   <span data-ttu-id="c8393-116">3 darabos beszerzési rendelés számlázása a GW raktárhoz 12,00 USD önköltségi áron történt.</span><span class="sxs-lookup"><span data-stu-id="c8393-116">A purchase order for a quantity of 3 at a cost price of USD 12.00 has been invoiced for warehouse GW.</span></span>
-   <span data-ttu-id="c8393-117">5 darabos beszerzési rendelés számlázása az MW raktárhoz 15,00 USD önköltségi áron történt.</span><span class="sxs-lookup"><span data-stu-id="c8393-117">A purchase order for a quantity of 5 at a cost price of USD 15.00 has been invoiced for warehouse MW.</span></span>

<span data-ttu-id="c8393-118">A GW raktárhoz a mozgóátlagon alapuló önköltségi ár 11,20 USD, és az MW raktárhoz a mozgóátlagon alapuló önköltségi ár 15,00 USD.</span><span class="sxs-lookup"><span data-stu-id="c8393-118">The running average cost price for warehouse GW is USD 11.20, and the running average cost price for warehouse MW is USD 15.00.</span></span> <span data-ttu-id="c8393-119">A GW raktárhoz értékesítésirendelés-számlájának feladása.</span><span class="sxs-lookup"><span data-stu-id="c8393-119">A sales order invoice is posted for warehouse GW.</span></span> <span data-ttu-id="c8393-120">A készlet értéke és az eladott áruk beszerzési értéke (a készletzárás lefuttatása előtt, és a jelölés nélkül) 11,20 USD.</span><span class="sxs-lookup"><span data-stu-id="c8393-120">The value of the inventory and the cost of goods sold (before inventory close is run and without marking) is USD 11.20.</span></span> <span data-ttu-id="c8393-121">Az MW raktárhoz egy további értékesítési rendelés feladása.</span><span class="sxs-lookup"><span data-stu-id="c8393-121">Another sales order is posted for warehouse MW.</span></span> <span data-ttu-id="c8393-122">A készlet értéke és az eladott áruk beszerzési értéke (a készletzárás lefuttatása előtt, és a jelölés nélkül) 15,00 USD.</span><span class="sxs-lookup"><span data-stu-id="c8393-122">The value of the inventory and the cost of goods sold (before inventory close is run and without marking) is USD 15.00.</span></span> 

<span data-ttu-id="c8393-123">**2. példa** , ha a tárolásidimenzió-csoport, amelyhez a cikk kapcsolódik pénzügyileg nyomon van követve a raktár által, és a nyomon követési dimenziócsoport pénzügyileg nyomon van követve kötegszám szerint, a mozgóátlagon alapuló önköltségi ár minden egyes köteghez ki lesz számolva.</span><span class="sxs-lookup"><span data-stu-id="c8393-123">**Example 2** If the storage dimension group that is attached to the item is financially tracked by warehouse, and the tracking dimension group is financially tracked by batch number, the running average cost price is calculated for each batch.</span></span> 

<span data-ttu-id="c8393-124">**Megjegyzés:** Minden esetben ajánlott az önköltségi ár megtekintése az összes nyomon követett pénzügyi dimenzió esetében.</span><span class="sxs-lookup"><span data-stu-id="c8393-124">**Note:** We recommend that you always view the cost price for all financial dimensions that are being tracked.</span></span> <span data-ttu-id="c8393-125">A következő beszerzési rendelések számlázása történt meg:</span><span class="sxs-lookup"><span data-stu-id="c8393-125">The following purchase orders have been invoiced:</span></span>

-   <span data-ttu-id="c8393-126">2 darabos beszerzési rendelés számlázása a GW raktárhoz és az AAA adaghoz 10,00 USD önköltségi áron történt.</span><span class="sxs-lookup"><span data-stu-id="c8393-126">A purchase order for a quantity of 2 at a cost price of USD 10.00 has been invoiced for warehouse GW and batch AAA.</span></span>
-   <span data-ttu-id="c8393-127">3 darabos beszerzési rendelés számlázása a GW raktárhoz és az AAA adaghoz 12,00 USD önköltségi áron történt.</span><span class="sxs-lookup"><span data-stu-id="c8393-127">A purchase order for a quantity of 3 at a cost price of USD 12.00 has been invoiced for warehouse GW and batch AAA.</span></span>
-   <span data-ttu-id="c8393-128">2 darabos beszerzési rendelés számlázása a GW raktárhoz és az BBB adaghoz 15,00 USD önköltségi áron történt.</span><span class="sxs-lookup"><span data-stu-id="c8393-128">A purchase order for a quantity of 2 at a cost price of USD 15.00 has been invoiced for warehouse GW and batch BBB.</span></span>

<span data-ttu-id="c8393-129">A GW raktárhoz és az AAA adaghoz a mozgóátlagon alapuló önköltségi ár 11,20 USD, és a GW raktárhoz és a BBB adaghoz a mozgóátlagon alapuló önköltségi ár 15,00 USD.</span><span class="sxs-lookup"><span data-stu-id="c8393-129">The running average cost price for warehouse GW and batch AAA is USD 11.20, and the running average cost price for warehouse GW and batch BBB is USD 15.00.</span></span>





[!INCLUDE[footer-include](../../includes/footer-banner.md)]