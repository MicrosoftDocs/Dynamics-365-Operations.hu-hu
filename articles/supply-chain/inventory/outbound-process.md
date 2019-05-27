---
title: Kimenő folyamat
description: Ez a témakör a Készletkezelés kimenő folyamatairól nyújt áttekintést.
author: perlynne
manager: AnnBe
ms.date: 10/04/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WMSOrder, WMSShipment, MCRPickingWorkbench, WMSPickingRegistration, CustomFilterGroup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 274363
ms.assetid: 375807b2-a426-4f1b-bc1f-2fe00fd48413
ms.search.region: global
ms.search.industry: Distribution
ms.author: perlynne
ms.dyn365.ops.version: AX 7.0.0
ms.search.validFrom: 2016-02-28
ms.openlocfilehash: 5ac3260f128acbc819d7207f68f17adb085da11c
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1570468"
---
# <a name="outbound-process"></a><span data-ttu-id="c0aa7-103">Kimenő folyamat</span><span class="sxs-lookup"><span data-stu-id="c0aa7-103">Outbound process</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c0aa7-104">Ez a témakör a Készletkezelés kimenő folyamatairól nyújt áttekintést.</span><span class="sxs-lookup"><span data-stu-id="c0aa7-104">This topic provides an overview of the outbound process in Inventory management.</span></span>

## <a name="output-orders"></a><span data-ttu-id="c0aa7-105">Kimeneti rendelések</span><span class="sxs-lookup"><span data-stu-id="c0aa7-105">Output orders</span></span>

<span data-ttu-id="c0aa7-106">Kimeneti rendelésekkel az értékesítésirendelés-sorok és az átmozgatási rendelés sorai összeköthetők a kitárolási listákat használó kimenő kitárolási folyamatokkal.</span><span class="sxs-lookup"><span data-stu-id="c0aa7-106">Output orders are used to link sales order lines and transfer order lines with the outbound picking processes that use picking lists.</span></span>

<span data-ttu-id="c0aa7-107">Amikor a kitárolási listák értékesítési rendelések vagy átmozgatási rendelések alapján létrejönnek, automatikusan létrejönnek a szállítmányok és a kimeneti rendelések.</span><span class="sxs-lookup"><span data-stu-id="c0aa7-107">When picking lists are generated from either sales orders or transfer orders, output orders and shipments are automatically created.</span></span> <span data-ttu-id="c0aa7-108">Minden kitárolási lista egyetlen szállítmányhoz tartozik.</span><span class="sxs-lookup"><span data-stu-id="c0aa7-108">A picking list has a one-to-one relationship with a shipment.</span></span> <span data-ttu-id="c0aa7-109">Az átmozgatási rendelés szállítmánya vagy az értékesítési rendelés csomagjegyzéke a szállítmányból dolgozható fel.</span><span class="sxs-lookup"><span data-stu-id="c0aa7-109">The transfer order shipment or the sales order packing slip can be processed from the shipment.</span></span> 

<span data-ttu-id="c0aa7-110">A következő ábrán áttekinthető a kimenő rendelések folyamata.</span><span class="sxs-lookup"><span data-stu-id="c0aa7-110">The following diagram shows an overview of the process for outbound orders.</span></span> 

<span data-ttu-id="c0aa7-111">[![A kimenő rendelési folyamat áttekintése](./media/outbound-order.png)](./media/outbound-order.png)</span><span class="sxs-lookup"><span data-stu-id="c0aa7-111">[![Overview of the outbound order process](./media/outbound-order.png)](./media/outbound-order.png)</span></span>

<span data-ttu-id="c0aa7-112">Kimenő szabályok beállításával meg lehet határozni, hogyan kezelje a program a kimenő folyamatot.</span><span class="sxs-lookup"><span data-stu-id="c0aa7-112">You can set up outbound rules to define how the program should handle the outbound process.</span></span> <span data-ttu-id="c0aa7-113">Ezeket a szabályokat a szállítmányozási folyamat nagyobb mértékű ellenőrzéshez használhatja.</span><span class="sxs-lookup"><span data-stu-id="c0aa7-113">You can use these rules to control the shipment process.</span></span> <span data-ttu-id="c0aa7-114">A szabályok segítségével különösen meg lehet szabni, a folyamat mely fázisában lehet szállítmányt küldeni.</span><span class="sxs-lookup"><span data-stu-id="c0aa7-114">In particular, you can use the rules to control which stage in the process a shipment can be sent during.</span></span> <span data-ttu-id="c0aa7-115">A következő beállítások határozzák meg, hogy hogyan kezeli a rendszer a kimenő folyamatokat.</span><span class="sxs-lookup"><span data-stu-id="c0aa7-115">The following settings define how the outbound processes are handled.</span></span>

## <a name="picking-route-status-for-sales-and-transfer-orders"></a><span data-ttu-id="c0aa7-116">Kitárolási útvonali állapot értékesítési és átmozgatási rendeléseknél</span><span class="sxs-lookup"><span data-stu-id="c0aa7-116">Picking route status for sales and transfer orders</span></span> 

<span data-ttu-id="c0aa7-117">Lépjen a **Kinnlévőségszámlák**\>**Beállítás**\>**Kinnlévőségek paraméterei** pontra, majd a **Frissítések** fülön válasszon egy értéket a **Kitárolási útvonal állapota** mezőben.</span><span class="sxs-lookup"><span data-stu-id="c0aa7-117">Go to **Account receivable** \> **Setup** \> **Account receivable parameters**, and then, on the **Updates** tab, select a value in the **Picking route status** field.</span></span>

<span data-ttu-id="c0aa7-118">[![Kitárolási útvonali állapot mező értékesítési rendeléseknél](./media/picking-route-status-sales-order.png)](./media/picking-route-status-sales-order.png)</span><span class="sxs-lookup"><span data-stu-id="c0aa7-118">[![Picking route status field for sales orders](./media/picking-route-status-sales-order.png)](./media/picking-route-status-sales-order.png)</span></span>

<span data-ttu-id="c0aa7-119">Ha a **Kitárolási útvonal állapota** mező értéke **Kész**, a kitárolási folyamat automatikusan megtörténik a kitárolási listák létrehozása során.</span><span class="sxs-lookup"><span data-stu-id="c0aa7-119">If the **Picking route status** field is set to **Completed**, the picking process occurs automatically as part of the process of generating picking lists.</span></span> <span data-ttu-id="c0aa7-120">Ha a mező értéke **Aktív**, a kitárolásilista-sorokat kézzel kell frissíteni.</span><span class="sxs-lookup"><span data-stu-id="c0aa7-120">If the field is set to **Activated**, the picking list lines must be manually updated.</span></span>

<span data-ttu-id="c0aa7-121">Ugyanez a beállítás vonatkozik az átmozgatási rendelésekre.</span><span class="sxs-lookup"><span data-stu-id="c0aa7-121">The same setup applies to transfer orders.</span></span> <span data-ttu-id="c0aa7-122">Lépjen a **Készletkezelés**\>**Beállítása**\>**Készlet- és raktárkezelési paraméterek** elemre, majd az a **Szállítási** fülön válasszon egy értéket a **Kitárolási útvonal állapota** mezőben.</span><span class="sxs-lookup"><span data-stu-id="c0aa7-122">Go to **Inventory management** \> **Setup** \> **Inventory and warehouse management parameters**, and then, on the **Transport** tab, select a value in the **Picking route status** field.</span></span>

<span data-ttu-id="c0aa7-123">[![Kitárolási útvonali állapot mező átmozgatási rendeléseknél](./media/picking-route-status-transfer-order.png)](./media/picking-route-status-transfer-order.png)</span><span class="sxs-lookup"><span data-stu-id="c0aa7-123">[![Picking route status field for transfer orders](./media/picking-route-status-transfer-order.png)](./media/picking-route-status-transfer-order.png)</span></span>

## <a name="end-output-inventory-orders"></a><span data-ttu-id="c0aa7-124">Kimeneti készletrendelések lezárása</span><span class="sxs-lookup"><span data-stu-id="c0aa7-124">End output inventory orders</span></span>

<span data-ttu-id="c0aa7-125">Lépjen a **Készletkezelés** \> **Beállítás** \> **Készlet- és raktárkezelési paraméterek** elemre, majd az **Általános** lapon állítsa be a  **Kimeneti készletrendelés befejezése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c0aa7-125">Go to **Inventory management** \> **Setup** \> **Inventory and warehouse management parameters**, and then, on the **General** tab, set the **End output inventory order** option.</span></span>

<span data-ttu-id="c0aa7-126">[![Kimeneti készletrendelési opció lezárása](./media//end-output-inventory-order.png)](./media//end-output-inventory-order.png)</span><span class="sxs-lookup"><span data-stu-id="c0aa7-126">[![End output inventory order option](./media//end-output-inventory-order.png)](./media//end-output-inventory-order.png)</span></span>

<span data-ttu-id="c0aa7-127">Ha a raktári dolgozó csökkenti a kitárolási lista mennyiségeket, a megfelelő rendelés készletmennyiségek törlődnek a szállítmányból.</span><span class="sxs-lookup"><span data-stu-id="c0aa7-127">When the warehouse worker reduces the picking list quantities, then the corresponding inventory order quantities will be removed from the shipment.</span></span> <span data-ttu-id="c0aa7-128">A kitárolási lista egy időpontbeli frissítésekor a fennmaradó mennyiséget visszajelentik a rendelésbe, ha a **Kimeneti készletrendelés lezárása** beállítása **Igen**.</span><span class="sxs-lookup"><span data-stu-id="c0aa7-128">When the picking list is updated at a point in time, the remaining quantities get reported back to the order if the **End output inventory order** option is set to **Yes**.</span></span> <span data-ttu-id="c0aa7-129">Ha a **Kimeneti készletrendelés lezárása** beállítása **Nem**, a fennmaradó mennyiség nyitott kimeneti rendelésmennyiségként lesz tárolva, és hozzá kell adni egy új kitárolási listához a **Kimenő megrendelések** funkció részeként.</span><span class="sxs-lookup"><span data-stu-id="c0aa7-129">If the **End output inventory order** option is set to **No**, the remaining quantities are kept as an open output order quantity and must be added to a new picking list as part of the **Open output orders** functionality.</span></span> 

<span data-ttu-id="c0aa7-130">[![Kimenő megrendelések a Funkciók menüben](./media/open-output-order.png)](./media/open-output-order.png)</span><span class="sxs-lookup"><span data-stu-id="c0aa7-130">[![Open output orders command on the Functions menu](./media/open-output-order.png)](./media/open-output-order.png)</span></span>

<span data-ttu-id="c0aa7-131">[![Funkciók menü a Kimenő megrendelések oldalon](./media/open-output-order-function.png)](./media/open-output-order-function.png)</span><span class="sxs-lookup"><span data-stu-id="c0aa7-131">[![Functions menu on the Open output orders page](./media/open-output-order-function.png)](./media/open-output-order-function.png)</span></span>

## <a name="reduce-quantity"></a><span data-ttu-id="c0aa7-132">Mennyiség csökkentése</span><span class="sxs-lookup"><span data-stu-id="c0aa7-132">Reduce quantity</span></span>

<span data-ttu-id="c0aa7-133">A harmadik paraméter, amely a kitárolási listák létrehozása folyamat részeként használható, a **Mennyiség csökkentése** paraméter.</span><span class="sxs-lookup"><span data-stu-id="c0aa7-133">The third parameter that you can use as part of the process of generating picking lists is the **Reduce quantity** parameter.</span></span> <span data-ttu-id="c0aa7-134">E paraméter beállítása együttesen működik a **Foglalás** beállítással, amely a raktárba való kiadás részeként kiváltja a foglalási folyamatot.</span><span class="sxs-lookup"><span data-stu-id="c0aa7-134">The setting of this parameter works together with the **Reservation** setting that triggers a reservation process as part of the release to the warehouse.</span></span>

<span data-ttu-id="c0aa7-135">[![Mennyiség csökkentése paraméter](./media/reduce-quantity.png)](./media/reduce-quantity.png)</span><span class="sxs-lookup"><span data-stu-id="c0aa7-135">[![Reduce quantity parameter](./media/reduce-quantity.png)](./media/reduce-quantity.png)</span></span>

## <a name="example-of-an-outbound-process-for-a-sales-order"></a><span data-ttu-id="c0aa7-136">Példa értékesítési rendelés kimenő folyamatára</span><span class="sxs-lookup"><span data-stu-id="c0aa7-136">Example of an outbound process for a sales order</span></span>

<span data-ttu-id="c0aa7-137">Ebben a példában egy értékesítési rendelést találunk két elemre.</span><span class="sxs-lookup"><span data-stu-id="c0aa7-137">For this example, there is a sales order for two items.</span></span> <span data-ttu-id="c0aa7-138">A kitárolási lista létrehozása során válassza a **Mennyiség csökkentése** paramétert.</span><span class="sxs-lookup"><span data-stu-id="c0aa7-138">During picking list generation, you select the **Reduce quantity** parameter.</span></span> <span data-ttu-id="c0aa7-139">Így csak az elérhető aktuális készletet adja ki és hoz létre kitárolási sorokat.</span><span class="sxs-lookup"><span data-stu-id="c0aa7-139">Therefore, you release and create picking lines only for available on-hand inventory.</span></span> <span data-ttu-id="c0aa7-140">A kitárolást jelenteni kell a kitárolási listák regisztrációs folyamatán keresztül (**Kitárolási útvonal állapota** = **Aktív**).</span><span class="sxs-lookup"><span data-stu-id="c0aa7-140">The picking must be reported via a registration process for picking lists (**Picking route status** = **Activated**).</span></span>

<span data-ttu-id="c0aa7-141">A készlet, amely még nem foglalt, fenntartásra kerül a kitárolási lista létrehozása során.</span><span class="sxs-lookup"><span data-stu-id="c0aa7-141">The inventory that hasn't already been reserved is reserved during picking list generation.</span></span> <span data-ttu-id="c0aa7-142">A rendelkezésre nem álló készlet vagy eltávolítható az értékesítési rendelésből, vagy kiadható a raktárnak későbbi kimenő feldolgozásra, amikor készlet elérhető lesz kitárolásra.</span><span class="sxs-lookup"><span data-stu-id="c0aa7-142">The unavailable inventory can be either removed from the sales order or released to the warehouse for outbound processing later, when inventory is available for picking.</span></span>

<span data-ttu-id="c0aa7-143">[![A kitárolási lista frissítése](./media/update-picking-list.png)](./media/update-picking-list.png)</span><span class="sxs-lookup"><span data-stu-id="c0aa7-143">[![Update the picking list](./media/update-picking-list.png)](./media/update-picking-list.png)</span></span>

<span data-ttu-id="c0aa7-144">Amint a kiadási sorok kitárolása a **Kitárolási lista rögzítése** oldalon megtörtént, a társított szállítmány lezárul.</span><span class="sxs-lookup"><span data-stu-id="c0aa7-144">As soon as all the picking lines have been picked on the **Picking list registration** page, the associated shipment is completed.</span></span> <span data-ttu-id="c0aa7-145">Az értékesítési rendelés szállítóleveleinek folyamata ezután inicializálható a kitárolt készlet alapján.</span><span class="sxs-lookup"><span data-stu-id="c0aa7-145">The process for sales order packing slips can then be initialized based on the picked inventory.</span></span>

<span data-ttu-id="c0aa7-146">[![Kimenő szállítmányok frissítése](./media/outbound-shipments.png)](./media/outbound-shipments.png)</span><span class="sxs-lookup"><span data-stu-id="c0aa7-146">[![Update outbound shipments](./media/outbound-shipments.png)](./media/outbound-shipments.png)</span></span>
