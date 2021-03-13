---
title: Karanténutasítások
description: Ez a témakör bemutatja, hogy a karanténutasításokat hogyan lehet a készlet blokkolására használni.
author: perlynne
manager: tfehr
ms.date: 11/02/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
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
ms.openlocfilehash: 03a9004aae563959dd19276268b9f81aca4b0735
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "5011697"
---
# <a name="quarantine-orders"></a><span data-ttu-id="0398e-103">Karanténutasítások</span><span class="sxs-lookup"><span data-stu-id="0398e-103">Quarantine orders</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0398e-104">Ez a témakör bemutatja, hogy a karanténutasításokat hogyan lehet a készlet blokkolására használni.</span><span class="sxs-lookup"><span data-stu-id="0398e-104">This topic describes how quarantine orders are used to block inventory.</span></span>

<span data-ttu-id="0398e-105">A karantén-utasítások használhatóak a készlet blokkolására.</span><span class="sxs-lookup"><span data-stu-id="0398e-105">Quarantine orders can be used to block inventory.</span></span> <span data-ttu-id="0398e-106">Például lehet, hogy minőség-ellenőrzési okok miatt szeretne karanténba tenni cikkeket.</span><span class="sxs-lookup"><span data-stu-id="0398e-106">For example, you might want to quarantine items for quality control reasons.</span></span> <span data-ttu-id="0398e-107">A karanténba helyezett készlet át lesz szállítva egy karantén raktárba.</span><span class="sxs-lookup"><span data-stu-id="0398e-107">Inventory that has been quarantined is transferred to a quarantine warehouse.</span></span> <span data-ttu-id="0398e-108">**Megjegyzés:** Ha speciális raktárkezelési folyamatokat használ (a Raktárkezelésben), a karantén utasítás feldolgozása csak értékesítési visszáru-rendeléseknél lesz használva.</span><span class="sxs-lookup"><span data-stu-id="0398e-108">**Note:** If you're using advanced warehouse management processes (in Warehouse management), quarantine order processing is used only for return sales orders.</span></span>

## <a name="quarantine-on-hand-inventory-items"></a><span data-ttu-id="0398e-109">Aktuálisan készleten lévő cikkek karanténba helyezése</span><span class="sxs-lookup"><span data-stu-id="0398e-109">Quarantine on-hand inventory items</span></span>
<span data-ttu-id="0398e-110">Cikkek karanténba helyezésekor létrehozhatja a karanténutasításokat manuálisan, vagy beállíthatja a rendszert, hogy automatikusan hozza létre a karantén utasításokat a bejövő feldolgozás során.</span><span class="sxs-lookup"><span data-stu-id="0398e-110">When you quarantine items, you can either create the quarantine orders manually or set up the system to create the quarantine orders automatically during inbound processing.</span></span> <span data-ttu-id="0398e-111">Karantén-utasítások automatikus létrehozásához válassza ki a **Karantén kezelése** lehetőséget a **Készletre vonatkozó irányelvek** fülön a **Cikkmodellcsoportok** lapon.</span><span class="sxs-lookup"><span data-stu-id="0398e-111">To create quarantine orders automatically, select the **Quarantine management** option on the **Inventory policies** tab on the **Item model groups** page.</span></span> <span data-ttu-id="0398e-112">Az alapértelmezett karantén raktárt is meg kell adnia a **Karantén raktár** mezőben, a fogadó raktár esetén.</span><span class="sxs-lookup"><span data-stu-id="0398e-112">You must also specify a default quarantine warehouse in the **Quarantine warehouse** field for the receiving warehouses.</span></span> <span data-ttu-id="0398e-113">Amikor az aktuális készlet rögzítve lesz egy beszerzési rendelésben vagy termelési rendelésben, a karanténba helyezett cikkek automatikus egy karantén raktárba kerülnek a Supply Chain Management rendszerben.</span><span class="sxs-lookup"><span data-stu-id="0398e-113">When the physically on-hand inventory is recorded in a purchase order or production order, quarantined items are automatically moved to a quarantine warehouse in Supply Chain Management.</span></span> <span data-ttu-id="0398e-114">Ez a mozgás akkor következik be, a karantén rendelés állapota felveszi a következő értéket: **Elindítva**.</span><span class="sxs-lookup"><span data-stu-id="0398e-114">This movement occurs because the status of the quarantine order is changed to **Started**.</span></span> <span data-ttu-id="0398e-115">Amikor manuálisan hoz létre karanténutasításokat, akkor nincs rá szükség, hogy az aktuális cikkhez be legyen állítva a karantén kezelés a társított cikkmodellcsoportban.</span><span class="sxs-lookup"><span data-stu-id="0398e-115">When you create quarantine orders manually, the item doesn't have to be set up for quarantine management in the associated item model group.</span></span> <span data-ttu-id="0398e-116">Ehhez a folyamathoz meg kell határoznia a karanténozásra váró aktuális készletet, valamint a használni kívánt karantén raktárt.</span><span class="sxs-lookup"><span data-stu-id="0398e-116">For this process, you must specify the on-hand inventory that should be quarantined and the quarantine warehouse that should be used.</span></span> <span data-ttu-id="0398e-117">A folyamat megtervezéséhez használhatja a karanténutasítás állapotokat.</span><span class="sxs-lookup"><span data-stu-id="0398e-117">You can use the quarantine order statuses to help plan the process.</span></span>

## <a name="quarantine-order-statuses"></a><span data-ttu-id="0398e-118">Karanténutasítás-állapotok</span><span class="sxs-lookup"><span data-stu-id="0398e-118">Quarantine order statuses</span></span>
<span data-ttu-id="0398e-119">A karanténutasítások a következő állapotúak lehetnek:</span><span class="sxs-lookup"><span data-stu-id="0398e-119">Quarantine orders can have the following statuses:</span></span>

-   <span data-ttu-id="0398e-120">Létrehozva</span><span class="sxs-lookup"><span data-stu-id="0398e-120">Created</span></span>
-   <span data-ttu-id="0398e-121">Elkezdve</span><span class="sxs-lookup"><span data-stu-id="0398e-121">Started</span></span>
-   <span data-ttu-id="0398e-122">Készként jelentve</span><span class="sxs-lookup"><span data-stu-id="0398e-122">Reported as finished</span></span>
-   <span data-ttu-id="0398e-123">Befejezve</span><span class="sxs-lookup"><span data-stu-id="0398e-123">Ended</span></span>

### <a name="created"></a><span data-ttu-id="0398e-124">Létrehozva</span><span class="sxs-lookup"><span data-stu-id="0398e-124">Created</span></span>

<span data-ttu-id="0398e-125">Ha egy karanténutasítást manuálisan hoztak létre, de a cikk még nincs a karantén raktárban, akkor a karanténutasítás állapota **Létrehozott**.</span><span class="sxs-lookup"><span data-stu-id="0398e-125">When a quarantine order has been created manually, but the item isn't yet in the quarantine warehouse, the quarantine order has a status of **Created**.</span></span> <span data-ttu-id="0398e-126">Két készlettranzakció jön létre.</span><span class="sxs-lookup"><span data-stu-id="0398e-126">Two inventory transactions are generated.</span></span> <span data-ttu-id="0398e-127">Az egyik tranzakció egy kiadási tranzakció, amelynek az állapota lehet **Megrendelt**, **Foglalt tényleges**, vagy **Kitárolt**.</span><span class="sxs-lookup"><span data-stu-id="0398e-127">One transaction is an issue transaction that can have a status of **On order**, **Reserved physical**, or **Picked**.</span></span> <span data-ttu-id="0398e-128">A második pedig egy bevételezési tranzakció, amely a **Megrendelt** vagy **Regisztrált** állapotokkal rendelkezhet a karantén raktárban.</span><span class="sxs-lookup"><span data-stu-id="0398e-128">The other transaction is a receipt transaction that can have a status of **Ordered** or **Registered** at the quarantine warehouse.</span></span> <span data-ttu-id="0398e-129">A szokásos folyamatokkal végezheti a lefoglalását, a kitárolást és a készlet frissítésének regisztrálást.</span><span class="sxs-lookup"><span data-stu-id="0398e-129">You can reserve, pick, and register updates to the inventory by using the usual processes.</span></span>

### <a name="started"></a><span data-ttu-id="0398e-130">Elkezdve</span><span class="sxs-lookup"><span data-stu-id="0398e-130">Started</span></span>

<span data-ttu-id="0398e-131">Ha egy karanténutasítás állapota **Elindítva** a készlet átkerül a szokásos raktárból a karanténraktárba, és létrejön két készlettranzakció.</span><span class="sxs-lookup"><span data-stu-id="0398e-131">When a quarantine order has a status of **Started**, the inventory is transferred from the regular warehouse to the quarantine warehouse, and two inventory transactions are generated.</span></span> <span data-ttu-id="0398e-132">Az egyik tranzakció állapota **Levonva**, a másik tranzakció állapota pedig **Bevételezett**.</span><span class="sxs-lookup"><span data-stu-id="0398e-132">One transaction has a status of **Deducted**, and the other transaction has a status of **Received**.</span></span> <span data-ttu-id="0398e-133">Ugyanakkor két olyan készlettranzakció is létrejön, amelyek a visszáru-átvezetés kezelését szolgálják.</span><span class="sxs-lookup"><span data-stu-id="0398e-133">At the same time, two inventory transactions are created to handle the return transfer.</span></span> <span data-ttu-id="0398e-134">Ezek a tranzakciók nem dátumhoz kötöttek.</span><span class="sxs-lookup"><span data-stu-id="0398e-134">These transactions aren't dated.</span></span> <span data-ttu-id="0398e-135">Az egyik tranzakció állapota **Foglalt tényleges**, a másik tranzakció állapota pedig **Megrendelt**.</span><span class="sxs-lookup"><span data-stu-id="0398e-135">One transaction has a status of **Reserved physical**, and the other transaction has a status of **Ordered**.</span></span>

### <a name="reported-as-finished"></a><span data-ttu-id="0398e-136">Készként jelentve</span><span class="sxs-lookup"><span data-stu-id="0398e-136">Reported as finished</span></span>

<span data-ttu-id="0398e-137">A **Jelentés készként** parancsra kattintva jelentheti, hogy egy elindított karanténutasítás befejeződött.</span><span class="sxs-lookup"><span data-stu-id="0398e-137">By clicking **Report as finished**, you can report a started quarantine order as finished.</span></span> <span data-ttu-id="0398e-138">A cikk felszabadul a karanténból, de még nem kerül vissza a szokásos raktárba.</span><span class="sxs-lookup"><span data-stu-id="0398e-138">The item is released from quarantine but isn't yet moved back to the regular warehouse.</span></span> <span data-ttu-id="0398e-139">A visszamozgatást az eredeti raktárba egy cikkbeérkezési naplón keresztül lehet feldolgozni, amelyet a Jelentés során lehet befejezett folyamatként inicializálni.</span><span class="sxs-lookup"><span data-stu-id="0398e-139">The movement back to the regular warehouse can be processed via an Item arrival journal that can be initialized during the Report as finished process.</span></span>

### <a name="ended"></a><span data-ttu-id="0398e-140">Befejezve</span><span class="sxs-lookup"><span data-stu-id="0398e-140">Ended</span></span>

<span data-ttu-id="0398e-141">Egy karanténutasítás befejezésekor, a cikk a karantén raktárból visszakerül a rendes raktárba.</span><span class="sxs-lookup"><span data-stu-id="0398e-141">When a quarantine order is ended, the item is moved from the quarantine warehouse back to the regular warehouse.</span></span> <span data-ttu-id="0398e-142">A cikktranzakció állapota **Eladva** a karanténraktárban és **Beszerezve** a rendes raktárban.</span><span class="sxs-lookup"><span data-stu-id="0398e-142">The status of the item transaction is set to **Sold** at the quarantine warehouse and **Purchased** at the regular warehouse.</span></span>

## <a name="quarantine-order-scrap"></a><span data-ttu-id="0398e-143">Karanténutasítás-selejt</span><span class="sxs-lookup"><span data-stu-id="0398e-143">Quarantine order scrap</span></span>
<span data-ttu-id="0398e-144">A karanténutasítási folyamat részeként lehetséges a készlet selejtezése.</span><span class="sxs-lookup"><span data-stu-id="0398e-144">As part of the quarantine order process, you can scrap inventory.</span></span> <span data-ttu-id="0398e-145">A selejt feldolgozásakor a készlet állapota **Értékesítve** lesz, a karantén raktárból származó kiadási tranzakció által.</span><span class="sxs-lookup"><span data-stu-id="0398e-145">When you process scrap, the status of the inventory will be set to **Sold** by an issue transaction from the quarantine warehouse.</span></span>

<a name="additional-resources"></a><span data-ttu-id="0398e-146">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="0398e-146">Additional resources</span></span>
--------

[<span data-ttu-id="0398e-147">Készletzárolás</span><span class="sxs-lookup"><span data-stu-id="0398e-147">Inventory blocking</span></span>](inventory-blocking.md)
