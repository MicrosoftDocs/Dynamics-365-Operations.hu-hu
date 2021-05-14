---
title: Karanténutasítások
description: Ez a témakör bemutatja, hogy a karanténrendeléseket hogyan lehet a készlet blokkolására használni.
author: perlynne
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventLocation, InventModelGroup, InventQuarantineOrder, InventQuarantineParmEnd, InventQuarantineParmReportFinished, InventQuarantineParmStartUp, InventTrans
audience: Application User
ms.reviewer: kamaybac
ms.custom: 30021
ms.assetid: d5047727-653c-49da-b489-6fd3fe50445e
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5e1eed14b7d38cf569af7192dec9580e771f06df
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956182"
---
# <a name="quarantine-orders"></a><span data-ttu-id="8dc9f-103">Karanténutasítások</span><span class="sxs-lookup"><span data-stu-id="8dc9f-103">Quarantine orders</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8dc9f-104">Ez a témakör bemutatja, hogy a karanténrendeléseket hogyan lehet a készlet blokkolására használni.</span><span class="sxs-lookup"><span data-stu-id="8dc9f-104">This topic describes how to use quarantine orders to block inventory.</span></span>

<span data-ttu-id="8dc9f-105">A karanténutasításokkal blokkolhatja a készletet.</span><span class="sxs-lookup"><span data-stu-id="8dc9f-105">Quarantine orders let you block inventory.</span></span> <span data-ttu-id="8dc9f-106">Például lehet, hogy minőség-ellenőrzési okok miatt szeretne karanténba tenni cikkeket.</span><span class="sxs-lookup"><span data-stu-id="8dc9f-106">For example, you might want to quarantine items for quality control reasons.</span></span> <span data-ttu-id="8dc9f-107">A karanténba helyezett készlet át lesz szállítva egy karantén raktárba.</span><span class="sxs-lookup"><span data-stu-id="8dc9f-107">Inventory that has been quarantined is transferred to a quarantine warehouse.</span></span>

> [!NOTE]
> <span data-ttu-id="8dc9f-108">Ha speciális raktárkezelési folyamatokat használ (a Raktárkezelésben), a karantén utasítás feldolgozása csak értékesítési visszáru-rendeléseknél lesz használva.</span><span class="sxs-lookup"><span data-stu-id="8dc9f-108">If you're using advanced warehouse management processes (in Warehouse management), quarantine order processing is used only for return sales orders.</span></span>

## <a name="quarantine-on-hand-inventory-items"></a><span data-ttu-id="8dc9f-109">Aktuálisan készleten lévő cikkek karanténba helyezése</span><span class="sxs-lookup"><span data-stu-id="8dc9f-109">Quarantine on-hand inventory items</span></span>

<span data-ttu-id="8dc9f-110">Cikkek karanténba helyezésekor létrehozhatja a karanténutasításokat manuálisan, vagy beállíthatja a rendszert, hogy automatikusan hozza létre azokat a bejövő feldolgozás során.</span><span class="sxs-lookup"><span data-stu-id="8dc9f-110">When you quarantine items, you can either manually create the quarantine orders or set up the system to automatically create them during inbound processing.</span></span>

<span data-ttu-id="8dc9f-111">A következő lépések szerint állítsa be a rendszert a karanténutasítások automatikus előállítására.</span><span class="sxs-lookup"><span data-stu-id="8dc9f-111">To set up the system to automatically generate quarantine orders, follow these steps.</span></span>

1. <span data-ttu-id="8dc9f-112">Ugorjon a **Készletkezelés \> Beállítás \> Készlet \> Cikkmodellcsoportok** pontra.</span><span class="sxs-lookup"><span data-stu-id="8dc9f-112">Go to **Inventory management \> Setup \> Inventory \> Item model groups**.</span></span>
1. <span data-ttu-id="8dc9f-113">Válasszon ki egy kapcsolódó modellcsoportot a listapanelen, vagy hozzon létre egy új modellcsoportot.</span><span class="sxs-lookup"><span data-stu-id="8dc9f-113">Select a relevant model group in the list pane, or create a new model group.</span></span>
1. <span data-ttu-id="8dc9f-114">A **Készletszabályok** gyorslapon jelölje be a **Karantén kezelése** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="8dc9f-114">On the **Inventory policies** FastTab, select the **Quarantine management** check box.</span></span>
1. <span data-ttu-id="8dc9f-115">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="8dc9f-115">Close the page.</span></span>
1. <span data-ttu-id="8dc9f-116">Az alapértelmezett karantén raktárt is meg kell adnia a **Karantén raktár** mezőben, a fogadó raktár esetén.</span><span class="sxs-lookup"><span data-stu-id="8dc9f-116">In the **Quarantine warehouse** field for the receiving warehouses, specify a default quarantine warehouse.</span></span>

<span data-ttu-id="8dc9f-117">Ha egy, a raktárban bevételként regisztrált cikk olyan modellcsoportba tartozik, amelyben be van jelölve a **Karanténkezelés** jelölőnégyzet, akkor a rendszer létrehoz hozzá egy karanténutasítást.</span><span class="sxs-lookup"><span data-stu-id="8dc9f-117">When an item that is registered as received at the warehouse belongs to a model group where the **Quarantine management** check box is selected, the system generates a quarantine order for it.</span></span> <span data-ttu-id="8dc9f-118">A karanténutasítás arra utasítja a dolgozókat, hogy helyezzék át a cikket a karanténraktárba.</span><span class="sxs-lookup"><span data-stu-id="8dc9f-118">The quarantine order instructs workers to move the item to the quarantine warehouse.</span></span>

<span data-ttu-id="8dc9f-119">Amikor manuálisan hoz létre karanténutasításokat a **Karanténutasítások** oldalon, akkor nincs rá szükség, hogy az aktuális cikkhez be legyen állítva a karantén kezelés a társított cikkmodellcsoportban.</span><span class="sxs-lookup"><span data-stu-id="8dc9f-119">When you manually create quarantine orders on the **Quarantine orders** page, the item doesn't have to be set up for quarantine management in the associated item model group.</span></span> <span data-ttu-id="8dc9f-120">Ehhez a folyamathoz meg kell határoznia a karanténozásra váró aktuális készletet, valamint a használni kívánt karantén raktárt.</span><span class="sxs-lookup"><span data-stu-id="8dc9f-120">For this process, you must specify the on-hand inventory that should be quarantined and the quarantine warehouse that should be used.</span></span> <span data-ttu-id="8dc9f-121">A folyamat megtervezéséhez használhatja a karanténutasítás állapotokat.</span><span class="sxs-lookup"><span data-stu-id="8dc9f-121">You can use the quarantine order statuses to help plan the process.</span></span>

## <a name="quarantine-order-statuses"></a><span data-ttu-id="8dc9f-122">Karanténutasítás-állapotok</span><span class="sxs-lookup"><span data-stu-id="8dc9f-122">Quarantine order statuses</span></span>

<span data-ttu-id="8dc9f-123">A karanténutasítások a következő állapotúak lehetnek:</span><span class="sxs-lookup"><span data-stu-id="8dc9f-123">Quarantine orders can have the following statuses:</span></span>

- <span data-ttu-id="8dc9f-124">Létrehozva</span><span class="sxs-lookup"><span data-stu-id="8dc9f-124">Created</span></span>
- <span data-ttu-id="8dc9f-125">Elkezdve</span><span class="sxs-lookup"><span data-stu-id="8dc9f-125">Started</span></span>
- <span data-ttu-id="8dc9f-126">Készként jelentve</span><span class="sxs-lookup"><span data-stu-id="8dc9f-126">Reported as finished</span></span>
- <span data-ttu-id="8dc9f-127">Befejezve</span><span class="sxs-lookup"><span data-stu-id="8dc9f-127">Ended</span></span>

### <a name="created"></a><span data-ttu-id="8dc9f-128">Létrehozva</span><span class="sxs-lookup"><span data-stu-id="8dc9f-128">Created</span></span>

<span data-ttu-id="8dc9f-129">Ha egy karanténutasítást manuálisan hoztak létre, de a cikk még nincs a karantén raktárban, akkor a karanténutasítás állapota **Létrehozott**.</span><span class="sxs-lookup"><span data-stu-id="8dc9f-129">When a quarantine order has been created manually, but the item isn't yet in the quarantine warehouse, the quarantine order has a status of **Created**.</span></span> <span data-ttu-id="8dc9f-130">Két készlettranzakció jön létre.</span><span class="sxs-lookup"><span data-stu-id="8dc9f-130">Two inventory transactions are generated.</span></span> <span data-ttu-id="8dc9f-131">Az egyik tranzakció egy kiadási tranzakció, amelynek az állapota lehet **Megrendelt**, **Foglalt tényleges**, vagy **Kitárolt**.</span><span class="sxs-lookup"><span data-stu-id="8dc9f-131">One transaction is an issue transaction that can have a status of **On order**, **Reserved physical**, or **Picked**.</span></span> <span data-ttu-id="8dc9f-132">A második pedig egy bevételezési tranzakció, amely a **Megrendelt** vagy **Regisztrált** állapotokkal rendelkezhet a karantén raktárban.</span><span class="sxs-lookup"><span data-stu-id="8dc9f-132">The other transaction is a receipt transaction that can have a status of **Ordered** or **Registered** at the quarantine warehouse.</span></span> <span data-ttu-id="8dc9f-133">A szokásos folyamatokkal végezheti a lefoglalását, a kitárolást és a készlet frissítésének regisztrálást.</span><span class="sxs-lookup"><span data-stu-id="8dc9f-133">You can reserve, pick, and register updates to the inventory by using the usual processes.</span></span>

### <a name="started"></a><span data-ttu-id="8dc9f-134">Elkezdve</span><span class="sxs-lookup"><span data-stu-id="8dc9f-134">Started</span></span>

<span data-ttu-id="8dc9f-135">Ha egy karanténutasítás állapota **Elindítva** a készlet átkerül a szokásos raktárból a karanténraktárba, és létrejön két készlettranzakció.</span><span class="sxs-lookup"><span data-stu-id="8dc9f-135">When a quarantine order has a status of **Started**, the inventory is transferred from the regular warehouse to the quarantine warehouse, and two inventory transactions are generated.</span></span> <span data-ttu-id="8dc9f-136">Az egyik tranzakció állapota **Levonva**, a másik tranzakció állapota pedig **Bevételezett**.</span><span class="sxs-lookup"><span data-stu-id="8dc9f-136">One transaction has a status of **Deducted**, and the other transaction has a status of **Received**.</span></span> <span data-ttu-id="8dc9f-137">Ugyanakkor két olyan készlettranzakció is létrejön, amelyek a visszáru-átvezetés kezelését szolgálják.</span><span class="sxs-lookup"><span data-stu-id="8dc9f-137">At the same time, two inventory transactions are created to handle the return transfer.</span></span> <span data-ttu-id="8dc9f-138">Ezek a tranzakciók nem dátumhoz kötöttek.</span><span class="sxs-lookup"><span data-stu-id="8dc9f-138">These transactions aren't dated.</span></span> <span data-ttu-id="8dc9f-139">Az egyik tranzakció állapota **Foglalt tényleges**, a másik tranzakció állapota pedig **Megrendelt**.</span><span class="sxs-lookup"><span data-stu-id="8dc9f-139">One transaction has a status of **Reserved physical**, and the other transaction has a status of **Ordered**.</span></span>

### <a name="reported-as-finished"></a><span data-ttu-id="8dc9f-140">Készként jelentve</span><span class="sxs-lookup"><span data-stu-id="8dc9f-140">Reported as finished</span></span>

<span data-ttu-id="8dc9f-141">Ha egy elindított karanténutasítást készként szeretne jelenteni, nyissa meg a rendelést, és válassza a műveletpanel **Készként jelentés** elemét.</span><span class="sxs-lookup"><span data-stu-id="8dc9f-141">To report a started quarantine order as finished, open the order, and select **Report as finished** on the Action Pane.</span></span> <span data-ttu-id="8dc9f-142">A cikk felszabadul a karanténból, de még nem kerül vissza a szokásos raktárba.</span><span class="sxs-lookup"><span data-stu-id="8dc9f-142">The item is released from quarantine, but it isn't yet moved back to the regular warehouse.</span></span> <span data-ttu-id="8dc9f-143">A visszamozgatást az eredeti raktárba egy cikkbeérkezési naplón keresztül lehet feldolgozni, amelyet a jelentés során lehet befejezett folyamatként inicializálni.</span><span class="sxs-lookup"><span data-stu-id="8dc9f-143">The movement back to the regular warehouse can be processed via an item arrival journal that can be initialized during the report as finished process.</span></span>

### <a name="ended"></a><span data-ttu-id="8dc9f-144">Befejezve</span><span class="sxs-lookup"><span data-stu-id="8dc9f-144">Ended</span></span>

<span data-ttu-id="8dc9f-145">Egy karanténutasítás befejezésekor, a cikk a karantén raktárból visszakerül a rendes raktárba.</span><span class="sxs-lookup"><span data-stu-id="8dc9f-145">When a quarantine order is ended, the item is moved from the quarantine warehouse back to the regular warehouse.</span></span> <span data-ttu-id="8dc9f-146">A cikktranzakció állapota *Eladva* a karanténraktárban és *Beszerezve* a rendes raktárban.</span><span class="sxs-lookup"><span data-stu-id="8dc9f-146">The status of the item transaction is set to *Sold* at the quarantine warehouse and *Purchased* at the regular warehouse.</span></span>

## <a name="quarantine-order-scrap"></a><span data-ttu-id="8dc9f-147">Karanténutasítás-selejt</span><span class="sxs-lookup"><span data-stu-id="8dc9f-147">Quarantine order scrap</span></span>

<span data-ttu-id="8dc9f-148">A karanténutasítási folyamat részeként lehetséges a készlet selejtezése.</span><span class="sxs-lookup"><span data-stu-id="8dc9f-148">As part of the quarantine order process, you can scrap inventory.</span></span> <span data-ttu-id="8dc9f-149">A selejt feldolgozásakor a készlet állapota *Értékesítve* lesz, a karantén raktárból származó kiadási tranzakció által.</span><span class="sxs-lookup"><span data-stu-id="8dc9f-149">When you process scrap, the status of the inventory is set to *Sold* by an issue transaction from the quarantine warehouse.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8dc9f-150">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="8dc9f-150">Additional resources</span></span>

- [<span data-ttu-id="8dc9f-151">Készletzárolás</span><span class="sxs-lookup"><span data-stu-id="8dc9f-151">Inventory blocking</span></span>](inventory-blocking.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
