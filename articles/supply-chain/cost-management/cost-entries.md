---
title: Költségbejegyzések
description: Ez a cikk tájékoztat a költségbejegyzésekről és a létrehozásuk idejéről. Egy költségbejegyzés egy olyan rekord, amely feljegyzi egy adott esemény költségét és mennyiségét.
author: AndersGirke
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventCostOnhandItem
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19131
ms.assetid: dd2663d8-bcc0-47b1-b36d-57433143487c
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 48c37e4355bc3448930a7cfa73ce08ac8e439b97
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5839415"
---
# <a name="cost-entries"></a><span data-ttu-id="70164-104">Költségbejegyzések</span><span class="sxs-lookup"><span data-stu-id="70164-104">Cost entries</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="70164-105">Ez a cikk tájékoztat a költségbejegyzésekről és a létrehozásuk idejéről.</span><span class="sxs-lookup"><span data-stu-id="70164-105">This article provides information about cost entries and when they are created.</span></span> <span data-ttu-id="70164-106">Egy költségbejegyzés egy olyan rekord, amely feljegyzi egy adott esemény költségét és mennyiségét.</span><span class="sxs-lookup"><span data-stu-id="70164-106">A cost entry is a record that registers the quantity and cost of a given event.</span></span>

<span data-ttu-id="70164-107">A költségbejegyzések olyan készlettranzakciók aggregációja, amelyek aktív pénzügyi készletdimenziókon lettek rögzítve.</span><span class="sxs-lookup"><span data-stu-id="70164-107">Cost entries are aggregations of inventory transactions that are recorded on active financial inventory dimensions.</span></span>

## <a name="examples"></a><span data-ttu-id="70164-108">Példák</span><span class="sxs-lookup"><span data-stu-id="70164-108">Examples</span></span>
### <a name="example-1-no-cost-entries-are-created"></a><span data-ttu-id="70164-109">1. példa: Nincsenek költségbejegyzések létrehozva</span><span class="sxs-lookup"><span data-stu-id="70164-109">Example 1: No cost entries are created</span></span>

<span data-ttu-id="70164-110">Egy átmozgatási naplóesemény regisztrálásra kerül.</span><span class="sxs-lookup"><span data-stu-id="70164-110">A transfer journal event is registered.</span></span> <span data-ttu-id="70164-111">Az esemény áthelyezi az A cikk egyik részét A helyről B helyre. A helykészlet dimenziója nem képezi a költségobjektum részét.</span><span class="sxs-lookup"><span data-stu-id="70164-111">The event transfers one piece of item A from location A to location B. The Location inventory dimension isn't considered part of the cost object.</span></span> <span data-ttu-id="70164-112">Emiatt az esemény két készlettranzakciót hoz létre, de nem költségtételeket nem jön létre.</span><span class="sxs-lookup"><span data-stu-id="70164-112">Therefore, the event creates two inventory transactions and no cost entries.</span></span>

### <a name="example-2-cost-entries-are-created"></a><span data-ttu-id="70164-113">2. példa: Költségbejegyzések létrehozva</span><span class="sxs-lookup"><span data-stu-id="70164-113">Example 2: Cost entries are created</span></span>

<span data-ttu-id="70164-114">Egy átmozgatási naplóesemény regisztrálásra kerül.</span><span class="sxs-lookup"><span data-stu-id="70164-114">A transfer journal event is registered.</span></span> <span data-ttu-id="70164-115">Az esemény egy darab A cikket visz át az 1. telephelyről a 2. telephelyre.</span><span class="sxs-lookup"><span data-stu-id="70164-115">The event transfers one piece of item A from site 1 to site 2.</span></span> <span data-ttu-id="70164-116">A telephely készletdimenziója az önköltségi objektum részének tekintendő.</span><span class="sxs-lookup"><span data-stu-id="70164-116">The Site inventory dimension is considered part of the cost object.</span></span> <span data-ttu-id="70164-117">Emiatt az esemény két készlettranzakciót és költségtételt hoz létre.</span><span class="sxs-lookup"><span data-stu-id="70164-117">Therefore, the event creates two inventory transactions and two cost entries.</span></span>

### <a name="example-3-one-cost-entry-is-created"></a><span data-ttu-id="70164-118">3. példa: Egy költségbejegyzés jön létre</span><span class="sxs-lookup"><span data-stu-id="70164-118">Example 3: One cost entry is created</span></span>

<span data-ttu-id="70164-119">Egy termék-bevételezési esemény kerül regisztrálásra egy beszerzési rendeléshez.</span><span class="sxs-lookup"><span data-stu-id="70164-119">A product receipt event is registered for a purchase order.</span></span> <span data-ttu-id="70164-120">Az esemény 100 darabot regisztrál A cikkből 10,00 USD egységköltség mellett.</span><span class="sxs-lookup"><span data-stu-id="70164-120">The event registers 100 pieces of item A at a unit cost of 10.00 U.S. dollars (USD).</span></span> <span data-ttu-id="70164-121">Mivel az A cikk sorozatszámot alkalmaz a készletkezelés céljának nyomon követéséhez, egy egyedi sorozatszám jön létre minden egyes bevételezett cikkhez.</span><span class="sxs-lookup"><span data-stu-id="70164-121">Because item A uses a serial number to track the purpose of inventory management, a unique serial number is created for each item that is received.</span></span> <span data-ttu-id="70164-122">Emiatt az esemény két 100-as készlettranzakciót és egy költségtételt hoz létre.</span><span class="sxs-lookup"><span data-stu-id="70164-122">Therefore, the event creates 100 inventory transactions and one cost entry.</span></span>

## <a name="cost-entries-page"></a><span data-ttu-id="70164-123">Költségbejegyzések oldal</span><span class="sxs-lookup"><span data-stu-id="70164-123">Cost entries page</span></span>
<span data-ttu-id="70164-124">Az új **Költségbejegyzések** lap lehetővé teszi a mennyiségek és a költségek regisztrációjának megtekintését és felügyeletét.</span><span class="sxs-lookup"><span data-stu-id="70164-124">The new **Cost entries** page lets you view and control registrations of quantities and costs.</span></span> <span data-ttu-id="70164-125">Ezen lap a **Készlettranzakció** és a **Készletkiegyenlítési** lapokat egészíti ki.</span><span class="sxs-lookup"><span data-stu-id="70164-125">This page complements the **Inventory transaction** and **Inventory settlement** pages.</span></span> <span data-ttu-id="70164-126">A rekordok időrendi sorrendben kerülnek regisztrálásra egy adott eseményhez.</span><span class="sxs-lookup"><span data-stu-id="70164-126">Records are registered in chronological order for an event.</span></span> <span data-ttu-id="70164-127">Ezért gyorsan megkeresheti és szabályozhatja az összesített költségeket egy adott eseményre vagy a dokumentumhoz kapcsolódó összes eseményre vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="70164-127">Therefore, you can quickly find and control the accumulated costs of a specific event or all events that are related to a document.</span></span> <span data-ttu-id="70164-128">Egy példa:</span><span class="sxs-lookup"><span data-stu-id="70164-128">Here is an example:</span></span>

-   <span data-ttu-id="70164-129">Egy termék-bevételezési esemény kerül regisztrálásra az A termékhez. 100 darab kerül bevételezésre 10,00 USD egységköltséggel.</span><span class="sxs-lookup"><span data-stu-id="70164-129">A product receipt event is registered for item A. One hundred pieces are received at a unit cost of 10.00 USD.</span></span>
-   <span data-ttu-id="70164-130">Néhány nappal a számlaesemény regisztrálását követően a költség 11,00 USD összegre nő.</span><span class="sxs-lookup"><span data-stu-id="70164-130">A few days after the invoice event is registered, the cost increases to 11.00 USD.</span></span> <span data-ttu-id="70164-131">Emiatt a teljes összeg 1100 USD lesz.</span><span class="sxs-lookup"><span data-stu-id="70164-131">Therefore, the total amount is 1,100 USD.</span></span> <span data-ttu-id="70164-132">Egy második bizonylat jön létre az 100 USD értékű eltérés számlázásához.</span><span class="sxs-lookup"><span data-stu-id="70164-132">A second voucher is created to account for the difference of 100 USD.</span></span>
-   <span data-ttu-id="70164-133">Néhány nappal később 15,00 USD vegyes költség kerül regisztrálásra a beszerzési rendeléshez a szállítási költségek fedezésére.</span><span class="sxs-lookup"><span data-stu-id="70164-133">A few days later, a miscellaneous charge of 15.00 USD to cover the transportation cost is registered on the purchase order.</span></span>

| <span data-ttu-id="70164-134">Bizonylat </span><span class="sxs-lookup"><span data-stu-id="70164-134">Voucher</span></span> | <span data-ttu-id="70164-135">Dátum</span><span class="sxs-lookup"><span data-stu-id="70164-135">Date</span></span>       | <span data-ttu-id="70164-136">Hivatkozás</span><span class="sxs-lookup"><span data-stu-id="70164-136">Reference</span></span>      | <span data-ttu-id="70164-137">Szám</span><span class="sxs-lookup"><span data-stu-id="70164-137">Number</span></span> | <span data-ttu-id="70164-138">Adagazonosító</span><span class="sxs-lookup"><span data-stu-id="70164-138">Lot ID</span></span>  | <span data-ttu-id="70164-139">Mennyiség</span><span class="sxs-lookup"><span data-stu-id="70164-139">Quantity</span></span> | <span data-ttu-id="70164-140">Összeg</span><span class="sxs-lookup"><span data-stu-id="70164-140">Amount</span></span>  |
|---------|------------|----------------|--------|---------|---------------|----|
| <span data-ttu-id="70164-141">00001</span><span class="sxs-lookup"><span data-stu-id="70164-141">00001</span></span>   | <span data-ttu-id="70164-142">2015/01/01</span><span class="sxs-lookup"><span data-stu-id="70164-142">01-01-2015</span></span> | <span data-ttu-id="70164-143">Beszerzési rendelés</span><span class="sxs-lookup"><span data-stu-id="70164-143">Purchase order</span></span> | <span data-ttu-id="70164-144">100001</span><span class="sxs-lookup"><span data-stu-id="70164-144">100001</span></span> | <span data-ttu-id="70164-145">0000101</span><span class="sxs-lookup"><span data-stu-id="70164-145">0000101</span></span> | <span data-ttu-id="70164-146">100,00</span><span class="sxs-lookup"><span data-stu-id="70164-146">100.00</span></span>   | <span data-ttu-id="70164-147">1000.00</span><span class="sxs-lookup"><span data-stu-id="70164-147">1000.00</span></span> |
| <span data-ttu-id="70164-148">00002</span><span class="sxs-lookup"><span data-stu-id="70164-148">00002</span></span>   | <span data-ttu-id="70164-149">2015/01/20</span><span class="sxs-lookup"><span data-stu-id="70164-149">20-01-2015</span></span> | <span data-ttu-id="70164-150">Beszerzési rendelés</span><span class="sxs-lookup"><span data-stu-id="70164-150">Purchase order</span></span> | <span data-ttu-id="70164-151">100001</span><span class="sxs-lookup"><span data-stu-id="70164-151">100001</span></span> | <span data-ttu-id="70164-152">0000101</span><span class="sxs-lookup"><span data-stu-id="70164-152">0000101</span></span> |          | <span data-ttu-id="70164-153">100,00</span><span class="sxs-lookup"><span data-stu-id="70164-153">100.00</span></span>  |
| <span data-ttu-id="70164-154">00003</span><span class="sxs-lookup"><span data-stu-id="70164-154">00003</span></span>   | <span data-ttu-id="70164-155">2015/01/31</span><span class="sxs-lookup"><span data-stu-id="70164-155">31-01-2015</span></span> | <span data-ttu-id="70164-156">Kiigazítás</span><span class="sxs-lookup"><span data-stu-id="70164-156">Adjustment</span></span>     | <span data-ttu-id="70164-157">100001</span><span class="sxs-lookup"><span data-stu-id="70164-157">100001</span></span> | <span data-ttu-id="70164-158">0000101</span><span class="sxs-lookup"><span data-stu-id="70164-158">0000101</span></span> |          | <span data-ttu-id="70164-159">1500</span><span class="sxs-lookup"><span data-stu-id="70164-159">15.00</span></span>   |

<span data-ttu-id="70164-160">A **Költségtételek** lap lehetővé teszi a dokumentumazonosító és a dátum alapján történő szűréseket.</span><span class="sxs-lookup"><span data-stu-id="70164-160">The **Cost entries** page enables filtering by document ID and document date.</span></span> 

> [!NOTE]
> <span data-ttu-id="70164-161">A költségtételek csak a [költségobjektumok](cost-object.md) vagy a kiadott termékek esetében érhetők el.</span><span class="sxs-lookup"><span data-stu-id="70164-161">Cost entries are available only for [cost objects](cost-object.md) or released products.</span></span>

<a name="additional-resources"></a><span data-ttu-id="70164-162">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="70164-162">Additional resources</span></span>
--------

[<span data-ttu-id="70164-163">Költségobjektumok</span><span class="sxs-lookup"><span data-stu-id="70164-163">Cost objects</span></span>](cost-object.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]