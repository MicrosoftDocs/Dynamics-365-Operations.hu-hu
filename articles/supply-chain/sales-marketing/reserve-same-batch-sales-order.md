---
title: Egy értékesítési rendelés foglalása ugyanazon kötegből
description: Ez a cikk ismerteti, hogyan végezze el termék beállítását a készletfoglalás engedélyezéséhez a készlet egyetlen adott kötegéből.
author: omulvad
ms.date: 03/17/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, EcoResStorageDimensionGroup, EcoResTrackingDimensionGroup, InventBatch, InventModelGroup, PdsAskSameLotForm, PdsCustSellableDays, WHSReservationHierarchy, WHSInventTableReservationHierarchy
audience: Application User
ms.reviewer: kamaybac
ms.custom: 28911
ms.assetid: 5823d75e-f839-46dd-beb3-e09b79fc8aa4
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e0937be76aa687ed986ff83e67f2db3e2dadd0f0
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5807656"
---
# <a name="reserve-the-same-batch-for-a-sales-order"></a><span data-ttu-id="71996-103">Egy értékesítési rendelés foglalása ugyanazon kötegből</span><span class="sxs-lookup"><span data-stu-id="71996-103">Reserve the same batch for a sales order</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="71996-104">Ez a cikk ismerteti, hogyan végezze el termék beállítását a készletfoglalás engedélyezéséhez a készlet egyetlen adott kötegéből.</span><span class="sxs-lookup"><span data-stu-id="71996-104">This article explains how to set up a product to allow reservation of inventory against a single batch of inventory.</span></span>

<span data-ttu-id="71996-105">Az ugyanazon kötegből való foglalás funkcióval egy értékesítési rendelést a készlet egyetlen adott kötegéből foglalhatja le.</span><span class="sxs-lookup"><span data-stu-id="71996-105">Same batch reservation lets you reserve inventory for a sales order line against a single batch of inventory.</span></span> <span data-ttu-id="71996-106">Tegyük fel, hogy egy tapétát rendelő vevő azt szeretné, hogy a teljes rendelést egy adott kötegből vagy adagból szállítsák neki, nehogy eltérő legyen a tekercsek minősége.</span><span class="sxs-lookup"><span data-stu-id="71996-106">For example, a customer who orders wallpaper can request that the whole order be filled from the same batch or lot, to avoid inconsistencies among the rolls.</span></span> <span data-ttu-id="71996-107">Ha egyazon kötegből szeretne foglalni, az alábbi beállításoknak kell aktívnak lenniük a termékhez rendelt cikkmodellcsoportban, a nyomon követési dimenzióban és a tárolási dimenziócsoportban:</span><span class="sxs-lookup"><span data-stu-id="71996-107">To set up a product to use same batch reservation, the following settings must be active in the item model group, tracking dimension group, and storage dimension group that you assign to the product:</span></span>

- <span data-ttu-id="71996-108">**Cikkmodellcsoportok** – A cikkmodellcsoportnál be kell jelölni az **Azonos köteg kiválasztása** és az **Összesített követelmény** mezőket a **Foglalás** mezőcsoportban, a készletirányelvek között.</span><span class="sxs-lookup"><span data-stu-id="71996-108">**Item model groups** – The item model group must have the **Same batch selection** and **Consolidate requirement** fields selected in the **Reservation** field group for inventory policies.</span></span>
- <span data-ttu-id="71996-109">**Nyomon követési dimenziócsoportok** – A nyomon követési dimenziócsoportoknál be kell jelölni a kötegszámhoz tartozó **Fedezeti terv dimenziónként** mezőt.</span><span class="sxs-lookup"><span data-stu-id="71996-109">**Tracking dimensions groups** – The tracking dimension group must have the **Coverage plan by dimension** field selected for the batch number.</span></span>
- <span data-ttu-id="71996-110">**Tárolási dimenziócsoportok** – A tárolási dimenziócsoportoknál be kell jelölni a **Fedezeti terv dimenziónként** mezőt a **Hely** és a **Raktár** vonatkozásában.</span><span class="sxs-lookup"><span data-stu-id="71996-110">**Storage dimensions groups** – The storage dimension group must have the **Coverage plan by dimension** field selected for **Site** and **Warehouse**.</span></span>

<span data-ttu-id="71996-111">Amikor ugyanazon kötegből foglalja egy értékesítési rendelés termékeit, a rendszer megpróbálja a teljes rendelt mennyiséget egyetlen készletkötegből foglalni.</span><span class="sxs-lookup"><span data-stu-id="71996-111">When you reserve inventory for a product on a sales order line that is set up for same batch selection, the system tries to reserve the ordered quantity from a single inventory batch.</span></span> <span data-ttu-id="71996-112">Az esetleges specifikus kötegattribútumokat is figyelembe veszi.</span><span class="sxs-lookup"><span data-stu-id="71996-112">Any specific batch attribute requirements are also considered.</span></span> <span data-ttu-id="71996-113">Ha a mennyiség rendelhető be egyetlen kötegől, akkor az **Azonos köteg foglalása miatti ütközés** lap jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="71996-113">If the quantity can't be filled from a single batch, the **Same batch reservation conflict** page appears.</span></span> <span data-ttu-id="71996-114">Ez az oldal leírja a problémákat, és a lehetséges megoldásokat is, amelyekkel folytathatja a foglalást.</span><span class="sxs-lookup"><span data-stu-id="71996-114">This page describes the issues and also the actions that you can take to continue with the reservation.</span></span> <span data-ttu-id="71996-115">A következő események akadályozhatják meg a tétel foglalását:</span><span class="sxs-lookup"><span data-stu-id="71996-115">The following conditions might prevent the batch from being reserved:</span></span>

- <span data-ttu-id="71996-116">A kötegrendelkezési kódnál **Foglalás letiltása** van beállítva a **Zárolva** állapotú értékesítésekre.</span><span class="sxs-lookup"><span data-stu-id="71996-116">The batch disposition code has **Block reservation** for sales flagged as **Blocked**.</span></span>
- <span data-ttu-id="71996-117">A köteg a lejárati dátum alapján és a vevői eladhatósági napok alapján már lejárt.</span><span class="sxs-lookup"><span data-stu-id="71996-117">The batch has expired, based on the expiration date and any applicable customer sellable days.</span></span> <span data-ttu-id="71996-118">A cikk még nem alkalmas lefoglalásra, ha a cikkmodellcsoportja FEFO dátumvezérelt, és a komissiózási feltétel a lejárati nap.</span><span class="sxs-lookup"><span data-stu-id="71996-118">The item can still be considered for reservation if the item model group for the item is First Expiry First Out (FEFO) date–controlled, and if the best-before date is selected as the pick criterion.</span></span>
- <span data-ttu-id="71996-119">A köteg eltarthatósági napjaiból fennmaradó idő nem elégséges, a lejárati dátum és a szavatosság dátuma alapján, illetve a vevői eladhatósági napok alapján.</span><span class="sxs-lookup"><span data-stu-id="71996-119">The batch doesn't have enough shelf-life days remaining, based on the expiration date and best-before date, plus any customer sellable days.</span></span>

<span data-ttu-id="71996-120">Az engedélyezett **Raktárkezelési folyamatokkal** rendelkező tárolási csoportokhoz társított cikkek esetében a meghatározott kötegszámot foglalhat egy foglalási hierarchia használatával, ahol a kötegszám készletdimenzió a hely dimenzió fölött van megadva.</span><span class="sxs-lookup"><span data-stu-id="71996-120">For items associated with a storage dimension group that has **Use warehouse management processes** enabled, you can reserve specific batch numbers by using a reservation hierarchy where the batch number inventory dimension is defined above the location dimension.</span></span> <span data-ttu-id="71996-121">Az ilyen típusú foglalási hierarchia ismertebb neve *Kötegelt a \[hely\] felett* foglalási hierarchia.</span><span class="sxs-lookup"><span data-stu-id="71996-121">This type of reservation hierarchy is also known as a *Batch-above \[location\]* reservation hierarchy.</span></span> <span data-ttu-id="71996-122">Az értékesítési és átmozgatási rendelés sorainak **Kötegelt foglalás** lapja is lehetővé teszi több sor kiválasztását és foglalását a rendelkezésre álló kötegszám alapján.</span><span class="sxs-lookup"><span data-stu-id="71996-122">The **Batch reservation** page for sales and transfer order lines also lets you select and reserve multiple lines based on the available batch numbers.</span></span> <span data-ttu-id="71996-123">Ha további tájékoztatást szeretne arról, hogy mi a teendő, ha olyan foglalási hierarchiát használ, amelyben a kötegszám dimenzió a hely alatt található (*Kötegelt a \[hely\] alatt*), tekintse meg a [Rugalmas raktárszintű dimenzió foglalási irányelv](../warehousing/flexible-warehouse-level-dimension-reservation.md) dokumentumot.</span><span class="sxs-lookup"><span data-stu-id="71996-123">For more information about what to do if you are using a reservation hierarchy that has the batch number dimension below the location (*Batch-below \[location\]*), see [Flexible warehouse-level dimension reservation policy](../warehousing/flexible-warehouse-level-dimension-reservation.md).</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
