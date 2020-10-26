---
title: Költségbejegyzések
description: Ez a cikk tájékoztat a költségbejegyzésekről és a létrehozásuk idejéről. Egy költségbejegyzés egy olyan rekord, amely feljegyzi egy adott esemény költségét és mennyiségét.
author: AndersGirke
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventCostOnhandItem
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 19131
ms.assetid: dd2663d8-bcc0-47b1-b36d-57433143487c
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3116f9fd2d1fe6a0967b114a069f495cea6217a1
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/10/2020
ms.locfileid: "3979780"
---
# <a name="cost-entries"></a><span data-ttu-id="2c612-104">Költségbejegyzések</span><span class="sxs-lookup"><span data-stu-id="2c612-104">Cost entries</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2c612-105">Ez a cikk tájékoztat a költségbejegyzésekről és a létrehozásuk idejéről.</span><span class="sxs-lookup"><span data-stu-id="2c612-105">This article provides information about cost entries and when they are created.</span></span> <span data-ttu-id="2c612-106">Egy költségbejegyzés egy olyan rekord, amely feljegyzi egy adott esemény költségét és mennyiségét.</span><span class="sxs-lookup"><span data-stu-id="2c612-106">A cost entry is a record that registers the quantity and cost of a given event.</span></span>

<span data-ttu-id="2c612-107">A költségbejegyzések olyan készlettranzakciók aggregációja, amelyek aktív pénzügyi készletdimenziókon lettek rögzítve.</span><span class="sxs-lookup"><span data-stu-id="2c612-107">Cost entries are aggregations of inventory transactions that are recorded on active financial inventory dimensions.</span></span>

## <a name="examples"></a><span data-ttu-id="2c612-108">Példák</span><span class="sxs-lookup"><span data-stu-id="2c612-108">Examples</span></span>
### <a name="example-1-no-cost-entries-are-created"></a><span data-ttu-id="2c612-109">1. példa: Nincsenek költségbejegyzések létrehozva</span><span class="sxs-lookup"><span data-stu-id="2c612-109">Example 1: No cost entries are created</span></span>

<span data-ttu-id="2c612-110">Egy átmozgatási naplóesemény regisztrálásra kerül.</span><span class="sxs-lookup"><span data-stu-id="2c612-110">A transfer journal event is registered.</span></span> <span data-ttu-id="2c612-111">Az esemény áthelyezi az A cikk egyik részét A helyről B helyre. A helykészlet dimenziója nem képezi a költségobjektum részét.</span><span class="sxs-lookup"><span data-stu-id="2c612-111">The event transfers one piece of item A from location A to location B. The Location inventory dimension isn't considered part of the cost object.</span></span> <span data-ttu-id="2c612-112">Emiatt az esemény két készlettranzakciót hoz létre, de nem költségtételeket nem jön létre.</span><span class="sxs-lookup"><span data-stu-id="2c612-112">Therefore, the event creates two inventory transactions and no cost entries.</span></span>

### <a name="example-2-cost-entries-are-created"></a><span data-ttu-id="2c612-113">2. példa: Költségbejegyzések létrehozva</span><span class="sxs-lookup"><span data-stu-id="2c612-113">Example 2: Cost entries are created</span></span>

<span data-ttu-id="2c612-114">Egy átmozgatási naplóesemény regisztrálásra kerül.</span><span class="sxs-lookup"><span data-stu-id="2c612-114">A transfer journal event is registered.</span></span> <span data-ttu-id="2c612-115">Az esemény egy darab A cikket visz át az 1. telephelyről a 2. telephelyre.</span><span class="sxs-lookup"><span data-stu-id="2c612-115">The event transfers one piece of item A from site 1 to site 2.</span></span> <span data-ttu-id="2c612-116">A telephely készletdimenziója az önköltségi objektum részének tekintendő.</span><span class="sxs-lookup"><span data-stu-id="2c612-116">The Site inventory dimension is considered part of the cost object.</span></span> <span data-ttu-id="2c612-117">Emiatt az esemény két készlettranzakciót és költségtételt hoz létre.</span><span class="sxs-lookup"><span data-stu-id="2c612-117">Therefore, the event creates two inventory transactions and two cost entries.</span></span>

### <a name="example-3-one-cost-entry-is-created"></a><span data-ttu-id="2c612-118">3. példa: Egy költségbejegyzés jön létre</span><span class="sxs-lookup"><span data-stu-id="2c612-118">Example 3: One cost entry is created</span></span>

<span data-ttu-id="2c612-119">Egy termék-bevételezési esemény kerül regisztrálásra egy beszerzési rendeléshez.</span><span class="sxs-lookup"><span data-stu-id="2c612-119">A product receipt event is registered for a purchase order.</span></span> <span data-ttu-id="2c612-120">Az esemény 100 darabot regisztrál A cikkből 10,00 USD egységköltség mellett.</span><span class="sxs-lookup"><span data-stu-id="2c612-120">The event registers 100 pieces of item A at a unit cost of 10.00 U.S. dollars (USD).</span></span> <span data-ttu-id="2c612-121">Mivel az A cikk sorozatszámot alkalmaz a készletkezelés céljának nyomon követéséhez, egy egyedi sorozatszám jön létre minden egyes bevételezett cikkhez.</span><span class="sxs-lookup"><span data-stu-id="2c612-121">Because item A uses a serial number to track the purpose of inventory management, a unique serial number is created for each item that is received.</span></span> <span data-ttu-id="2c612-122">Emiatt az esemény két 100-as készlettranzakciót és egy költségtételt hoz létre.</span><span class="sxs-lookup"><span data-stu-id="2c612-122">Therefore, the event creates 100 inventory transactions and one cost entry.</span></span>

## <a name="cost-entries-page"></a><span data-ttu-id="2c612-123">Költségbejegyzések oldal</span><span class="sxs-lookup"><span data-stu-id="2c612-123">Cost entries page</span></span>
<span data-ttu-id="2c612-124">Az új **Költségbejegyzések** lap lehetővé teszi a mennyiségek és a költségek regisztrációjának megtekintését és felügyeletét.</span><span class="sxs-lookup"><span data-stu-id="2c612-124">The new **Cost entries** page lets you view and control registrations of quantities and costs.</span></span> <span data-ttu-id="2c612-125">Ezen lap a **Készlettranzakció** és a **Készletkiegyenlítési** lapokat egészíti ki.</span><span class="sxs-lookup"><span data-stu-id="2c612-125">This page complements the **Inventory transaction** and **Inventory settlement** pages.</span></span> <span data-ttu-id="2c612-126">A rekordok időrendi sorrendben kerülnek regisztrálásra egy adott eseményhez.</span><span class="sxs-lookup"><span data-stu-id="2c612-126">Records are registered in chronological order for an event.</span></span> <span data-ttu-id="2c612-127">Ezért gyorsan megkeresheti és szabályozhatja az összesített költségeket egy adott eseményre vagy a dokumentumhoz kapcsolódó összes eseményre vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="2c612-127">Therefore, you can quickly find and control the accumulated costs of a specific event or all events that are related to a document.</span></span> <span data-ttu-id="2c612-128">Egy példa:</span><span class="sxs-lookup"><span data-stu-id="2c612-128">Here is an example:</span></span>

-   <span data-ttu-id="2c612-129">Egy termék-bevételezési esemény kerül regisztrálásra az A termékhez. 100 darab kerül bevételezésre 10,00 USD egységköltséggel.</span><span class="sxs-lookup"><span data-stu-id="2c612-129">A product receipt event is registered for item A. One hundred pieces are received at a unit cost of 10.00 USD.</span></span>
-   <span data-ttu-id="2c612-130">Néhány nappal a számlaesemény regisztrálását követően a költség 11,00 USD összegre nő.</span><span class="sxs-lookup"><span data-stu-id="2c612-130">A few days after the invoice event is registered, the cost increases to 11.00 USD.</span></span> <span data-ttu-id="2c612-131">Emiatt a teljes összeg 1100 USD lesz.</span><span class="sxs-lookup"><span data-stu-id="2c612-131">Therefore, the total amount is 1,100 USD.</span></span> <span data-ttu-id="2c612-132">Egy második bizonylat jön létre az 100 USD értékű eltérés számlázásához.</span><span class="sxs-lookup"><span data-stu-id="2c612-132">A second voucher is created to account for the difference of 100 USD.</span></span>
-   <span data-ttu-id="2c612-133">Néhány nappal később 15,00 USD vegyes költség kerül regisztrálásra a beszerzési rendeléshez a szállítási költségek fedezésére.</span><span class="sxs-lookup"><span data-stu-id="2c612-133">A few days later, a miscellaneous charge of 15.00 USD to cover the transportation cost is registered on the purchase order.</span></span>

| <span data-ttu-id="2c612-134">Bizonylat </span><span class="sxs-lookup"><span data-stu-id="2c612-134">Voucher</span></span> | <span data-ttu-id="2c612-135">Dátum</span><span class="sxs-lookup"><span data-stu-id="2c612-135">Date</span></span>       | <span data-ttu-id="2c612-136">Hivatkozás</span><span class="sxs-lookup"><span data-stu-id="2c612-136">Reference</span></span>      | <span data-ttu-id="2c612-137">Szám</span><span class="sxs-lookup"><span data-stu-id="2c612-137">Number</span></span> | <span data-ttu-id="2c612-138">Adagazonosító</span><span class="sxs-lookup"><span data-stu-id="2c612-138">Lot ID</span></span>  | <span data-ttu-id="2c612-139">Mennyiség</span><span class="sxs-lookup"><span data-stu-id="2c612-139">Quantity</span></span> | <span data-ttu-id="2c612-140">Összeg</span><span class="sxs-lookup"><span data-stu-id="2c612-140">Amount</span></span>  |
|---------|------------|----------------|--------|---------|---------------|----|
| <span data-ttu-id="2c612-141">00001</span><span class="sxs-lookup"><span data-stu-id="2c612-141">00001</span></span>   | <span data-ttu-id="2c612-142">2015/01/01</span><span class="sxs-lookup"><span data-stu-id="2c612-142">01-01-2015</span></span> | <span data-ttu-id="2c612-143">Beszerzési rendelés</span><span class="sxs-lookup"><span data-stu-id="2c612-143">Purchase order</span></span> | <span data-ttu-id="2c612-144">100001</span><span class="sxs-lookup"><span data-stu-id="2c612-144">100001</span></span> | <span data-ttu-id="2c612-145">0000101</span><span class="sxs-lookup"><span data-stu-id="2c612-145">0000101</span></span> | <span data-ttu-id="2c612-146">100,00</span><span class="sxs-lookup"><span data-stu-id="2c612-146">100.00</span></span>   | <span data-ttu-id="2c612-147">1000.00</span><span class="sxs-lookup"><span data-stu-id="2c612-147">1000.00</span></span> |
| <span data-ttu-id="2c612-148">00002</span><span class="sxs-lookup"><span data-stu-id="2c612-148">00002</span></span>   | <span data-ttu-id="2c612-149">2015/01/20</span><span class="sxs-lookup"><span data-stu-id="2c612-149">20-01-2015</span></span> | <span data-ttu-id="2c612-150">Beszerzési rendelés</span><span class="sxs-lookup"><span data-stu-id="2c612-150">Purchase order</span></span> | <span data-ttu-id="2c612-151">100001</span><span class="sxs-lookup"><span data-stu-id="2c612-151">100001</span></span> | <span data-ttu-id="2c612-152">0000101</span><span class="sxs-lookup"><span data-stu-id="2c612-152">0000101</span></span> |          | <span data-ttu-id="2c612-153">100,00</span><span class="sxs-lookup"><span data-stu-id="2c612-153">100.00</span></span>  |
| <span data-ttu-id="2c612-154">00003</span><span class="sxs-lookup"><span data-stu-id="2c612-154">00003</span></span>   | <span data-ttu-id="2c612-155">2015/01/31</span><span class="sxs-lookup"><span data-stu-id="2c612-155">31-01-2015</span></span> | <span data-ttu-id="2c612-156">Kiigazítás</span><span class="sxs-lookup"><span data-stu-id="2c612-156">Adjustment</span></span>     | <span data-ttu-id="2c612-157">100001</span><span class="sxs-lookup"><span data-stu-id="2c612-157">100001</span></span> | <span data-ttu-id="2c612-158">0000101</span><span class="sxs-lookup"><span data-stu-id="2c612-158">0000101</span></span> |          | <span data-ttu-id="2c612-159">1500</span><span class="sxs-lookup"><span data-stu-id="2c612-159">15.00</span></span>   |

<span data-ttu-id="2c612-160">A **Költségtételek** lap lehetővé teszi a dokumentumazonosító és a dátum alapján történő szűréseket.</span><span class="sxs-lookup"><span data-stu-id="2c612-160">The **Cost entries** page enables filtering by document ID and document date.</span></span> 

> [!NOTE]
> <span data-ttu-id="2c612-161">A költségtételek csak a [költségobjektumok](cost-object.md) vagy a kiadott termékek esetében érhetők el.</span><span class="sxs-lookup"><span data-stu-id="2c612-161">Cost entries are available only for [cost objects](cost-object.md) or released products.</span></span>

<a name="additional-resources"></a><span data-ttu-id="2c612-162">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="2c612-162">Additional resources</span></span>
--------

[<span data-ttu-id="2c612-163">Költségobjektumok</span><span class="sxs-lookup"><span data-stu-id="2c612-163">Cost objects</span></span>](cost-object.md)



