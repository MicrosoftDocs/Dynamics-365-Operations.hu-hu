---
title: Beszerzésekkel és forrásokkal kapcsolatos munkafolyamatok hibaelhárítása
description: Ez a témakör azt mutatja be, hogyan lehet javítani a beszerzésekkel és forrásokkal kapcsolatosa munkafolyamatok használata során felmerülő problémákat.
author: SmithaNataraj
manager: tfehr
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-9-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 940a6c39ac83e7388d4e1a08b656b75df81ed801
ms.sourcegitcommit: 91e101d7a51a8b63bd196ec80e9224e5e6e6fc95
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/22/2020
ms.locfileid: "3834366"
---
# <a name="troubleshoot-procurement-and-sourcing-workflows"></a><span data-ttu-id="c86c5-103">Beszerzésekkel és forrásokkal kapcsolatos munkafolyamatok hibaelhárítása</span><span class="sxs-lookup"><span data-stu-id="c86c5-103">Troubleshoot procurement and sourcing workflows</span></span>

<span data-ttu-id="c86c5-104">Ez a témakör azt mutatja be, hogyan lehet javítani a beszerzésekkel és forrásokkal kapcsolatosa munkafolyamatok használata során felmerülő problémákat.</span><span class="sxs-lookup"><span data-stu-id="c86c5-104">This topic describes how to fix issues that you might encounter while you work with procurement and sourcing workflows.</span></span>

## <a name="error-when-re-submitting-a-purchase-order-to-the-workflow-after-a-change-changes-to-purchase-order-x-are-allowed-only-in-a-draft-state-when-change-management-is-activated"></a><span data-ttu-id="c86c5-105">Hiba történt egy beszerzési rendelésnek a munkafolyamatba történő ismételt elküldésekor egy módosítás után: „Az X beszerzési rendelés módosításai csak Válzlat állapotban engedélyezettek, ha a változáskezelés aktív”</span><span class="sxs-lookup"><span data-stu-id="c86c5-105">Error when re-submitting a purchase order to the workflow after a change: "Changes to purchase order X are allowed only in a Draft state when change management is activated"</span></span>

<span data-ttu-id="c86c5-106">Ez a probléma csak akkor fordul elő, ha a beszerzési rendelés *Visszaigazolt* állapotban volt, mielőtt a változtatásokat kérte.</span><span class="sxs-lookup"><span data-stu-id="c86c5-106">This issue occurs only if the purchase order was in a *Confirmed* state before you requested changes.</span></span> <span data-ttu-id="c86c5-107">Ha a beszerzési rendelés *Jóváhagyott* állapotú, amikor a módosítást kérelmezi, a munkafolyamat sikeresen feldolgozható.</span><span class="sxs-lookup"><span data-stu-id="c86c5-107">If you request changes while the purchase order is in an *Approved* state, the workflow can be processed successfully.</span></span>

### <a name="error-description"></a><span data-ttu-id="c86c5-108">Hiba leírása</span><span class="sxs-lookup"><span data-stu-id="c86c5-108">Error description</span></span>

<span data-ttu-id="c86c5-109">A következő hiba történik a munkafolyamatban, amikor egy módosítást követően újra beküld egy beszerzési rendelést:</span><span class="sxs-lookup"><span data-stu-id="c86c5-109">The following error occurs in the workflow when a purchase order is resubmitted after a change:</span></span>

> <span data-ttu-id="c86c5-110">Leállítva (hiba): X + + kivétel: A PO 0000569 beszerzési rendelés módosítása csak Vázlat állapotban engedélyezett, ha a változáskezelés aktiválva van</span><span class="sxs-lookup"><span data-stu-id="c86c5-110">Stopped (error): X++ Exception: Changes to purchase order PO0000569 are only allowed in state Draft when change management is activated at</span></span><br>
<span data-ttu-id="c86c5-111">SysWorkflowParticipantProvider-resolve</span><span class="sxs-lookup"><span data-stu-id="c86c5-111">SysWorkflowParticipantProvider-resolve</span></span><br>
<span data-ttu-id="c86c5-112">SysWorkflowParticipantProvider-resolveParticipants</span><span class="sxs-lookup"><span data-stu-id="c86c5-112">SysWorkflowParticipantProvider-resolveParticipants</span></span><br>
<span data-ttu-id="c86c5-113">SysWorkflowServiceProvider-resolveParticipant</span><span class="sxs-lookup"><span data-stu-id="c86c5-113">SysWorkflowServiceProvider-resolveParticipant</span></span><br>
<span data-ttu-id="c86c5-114">SysWorkflowQueue-resume</span><span class="sxs-lookup"><span data-stu-id="c86c5-114">SysWorkflowQueue-resume</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="c86c5-115">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="c86c5-115">Issue resolution</span></span>

<span data-ttu-id="c86c5-116">Ez a hiba a beszerzési rendelések felosztásakor jelentkező ellentmondás miatt fordulhat elő.</span><span class="sxs-lookup"><span data-stu-id="c86c5-116">This issue can occur because of inconsistency in purchase order distributions.</span></span>

<span data-ttu-id="c86c5-117">A hiba blokkolásának feloldásához és a beszerzési rendelés *Vázlat* állapotra állításához nyissa meg a **Beszerzés és forrás \> Időszakos feladatok \> Tisztítás \> Beszerzési rendelés felosztásának visszaállítása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c86c5-117">To unblock this issue and reset the purchase order to a *Draft* state, go to **Procurement and sourcing \> Periodic tasks \> Clean up \> Purchase order distribution reset**.</span></span> <span data-ttu-id="c86c5-118">A további tudnivalókat lásd a következő blogbejegyzésben: [Beszerzésirendelés-felosztási hibák megoldása a Dynamics 365 Supply Chain Management-alkalmazásban](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).</span><span class="sxs-lookup"><span data-stu-id="c86c5-118">For more information, see the following blog post: [Resolve PO distribution errors in Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).</span></span>

<span data-ttu-id="c86c5-119">A probléma javítás lehetséges [ezen Microsoft tudásbázis (KB) cikk](https://msdyneng.visualstudio.com/FinOps/_workitems/edit/467138) alapján.</span><span class="sxs-lookup"><span data-stu-id="c86c5-119">The issue will be fixed through [this Microsoft Knowledge Base (KB) article](https://msdyneng.visualstudio.com/FinOps/_workitems/edit/467138).</span></span>

## <a name="one-or-more-accounting-distributions-are-either-over-distributed-or-under-distributed"></a><span data-ttu-id="c86c5-120">Egy vagy több könyvelési felosztás túlzottan fel van osztva, vagy nincsen eléggé felosztva.</span><span class="sxs-lookup"><span data-stu-id="c86c5-120">One or more accounting distributions are either over-distributed or under-distributed.</span></span>

<span data-ttu-id="c86c5-121">Ez a hiba a beszerzési rendelések felosztásakor jelentkező ellentmondás miatt fordulhat elő.</span><span class="sxs-lookup"><span data-stu-id="c86c5-121">This issue can occur because of inconsistency in purchase order distributions.</span></span>

<span data-ttu-id="c86c5-122">A hiba blokkolásának feloldásához és a beszerzési rendelés *Vázlat* állapotra állításához nyissa meg a **Beszerzés és forrás \> Időszakos feladatok \> Tisztítás \> Beszerzési rendelés felosztásának visszaállítása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c86c5-122">To unblock this issue and reset the purchase order to a *Draft* state, go to **Procurement and sourcing \> Periodic tasks \> Clean up \> Purchase order distribution reset**.</span></span> <span data-ttu-id="c86c5-123">A további tudnivalókat lásd a következő blogbejegyzésben: [Beszerzésirendelés-felosztási hibák megoldása a Dynamics 365 Supply Chain Management-alkalmazásban](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).</span><span class="sxs-lookup"><span data-stu-id="c86c5-123">For more information, see the following blog post: [Resolve PO distribution errors in Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).</span></span>

## <a name="if-a-delivery-remainder-is-canceled-on-a-purchase-order-where-change-management-is-turned-on-the-purchase-order-goes-to-a-confirmed-state"></a><span data-ttu-id="c86c5-124">Ha szállítási maradék visszavonása egy olyan beszerzési rendelésen történik, amelyen a változáskezelés be van kapcsolva, a beszerzési rendelés Visszaigazolt állapotba kerül.</span><span class="sxs-lookup"><span data-stu-id="c86c5-124">If a delivery remainder is canceled on a purchase order where change management is turned on, the purchase order goes to a Confirmed state.</span></span>

### <a name="issue-description"></a><span data-ttu-id="c86c5-125">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="c86c5-125">Issue description</span></span>

<span data-ttu-id="c86c5-126">Olyan beszerzési rendelés esetében, amelyre a változáskezelés érvényes, ha az egyetlen kért módosítás a szállítási maradék törlése egy vagy több sorhoz, a beszerzési rendelés automatikusan *Megerősített* állapotba kerül, a jóváhagyást követően, és nem jön létre napló.</span><span class="sxs-lookup"><span data-stu-id="c86c5-126">For a purchase order that is subject to change management, if the only change that is requested is the cancellation of a delivery remainder on one or more of the lines, the purchase order will go directly to a *Confirmed* state when it's approved, and no journal will be created.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="c86c5-127">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="c86c5-127">Issue resolution</span></span>

<span data-ttu-id="c86c5-128">A szállítás maradék visszavonása nem befolyásolja a visszaigazolási napló tartalmát.</span><span class="sxs-lookup"><span data-stu-id="c86c5-128">Cancellation of a delivery remainder doesn't affect the contents of the confirmation journal.</span></span> <span data-ttu-id="c86c5-129">Ezt a funkciót akkor kell használni, ha a sor részlegesen beérkezett, és a fennmaradó minőséget érvényteleníteni kell egy feldolgozási lépésben, miután a beszerzési rendelést a szállító megerősítette.</span><span class="sxs-lookup"><span data-stu-id="c86c5-129">This functionality should be used when the line has been partially received, and the remainder quality should be canceled in the process step after the purchase order has been confirmed with the vendor.</span></span>

<span data-ttu-id="c86c5-130">Ha ennek tükröződnie kell a beszerzési rendelés visszaigazolásán, akkor a mennyiséget helyesbíteni kell a beszerzési rendelés sorában, hogy a visszaigazolást legyen szükséges.</span><span class="sxs-lookup"><span data-stu-id="c86c5-130">If this should be reflected on the purchase order confirmation, the quantity should be adjusted on the purchase order line so that the confirmation will be required.</span></span> <span data-ttu-id="c86c5-131">Azt is megteheti, hogy ha a sorban nem érkezett be semmi, akkor a mennyiséget eltávolítja.</span><span class="sxs-lookup"><span data-stu-id="c86c5-131">Alternatively, if nothing has been received on the line, the quantity can be removed.</span></span> <span data-ttu-id="c86c5-132">Ebben az esetben visszaigazolás szükséges.</span><span class="sxs-lookup"><span data-stu-id="c86c5-132">In this case, reconfirmation will be required.</span></span>

## <a name="canceled-purchase-orders-appear-in-the-draft-list-in-the-purchase-order-preparation-workspace"></a><span data-ttu-id="c86c5-133">A visszavont beszerzési rendelések megjelennek a Beszerzési rendelés előkészítő munkaterületének vázlatok listájában.</span><span class="sxs-lookup"><span data-stu-id="c86c5-133">Canceled purchase orders appear in the draft list in the Purchase order preparation workspace.</span></span>

### <a name="issue-description"></a><span data-ttu-id="c86c5-134">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="c86c5-134">Issue description</span></span>

<span data-ttu-id="c86c5-135">Miután *Jóváhagyott* állapotú beszerzési rendeléseket vont vissza a **Beszerzési rendelések előkészítése** munkaterületen a beszerzési rendelések vázlatainak listáján továbbra is megjelennek a visszavont beszerzési rendelések.</span><span class="sxs-lookup"><span data-stu-id="c86c5-135">After you cancel purchase orders that were in a *Confirmed* state, the canceled purchase orders still appear in the list of draft purchase orders in the **Purchase order preparation** workspace.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="c86c5-136">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="c86c5-136">Issue resolution</span></span>

<span data-ttu-id="c86c5-137">Ez a probléma csak a változáskezelés hatálya alá tartozó beszerzési rendelésekhez fordulhat elő.</span><span class="sxs-lookup"><span data-stu-id="c86c5-137">This issue occurs only for purchase orders that are subject to change management.</span></span> <span data-ttu-id="c86c5-138">Ennek oka az, hogy a törlést olyan módosításnak kell tekinteni, amelyet jóvá kell hagyni.</span><span class="sxs-lookup"><span data-stu-id="c86c5-138">It occurs because the cancellation is considered a change that must be approved.</span></span> <span data-ttu-id="c86c5-139">A jóváhagyást a rendszer automatikusan elvégezheti.</span><span class="sxs-lookup"><span data-stu-id="c86c5-139">The approval can be done automatically by the system.</span></span> <span data-ttu-id="c86c5-140">Ennek megfelelően az eljárás a megszüntetett beszerzési rendelés elküldése a jóváhagyási munkafolyamatba, hogy az *Jóváhagyott* állapotba lépjen.</span><span class="sxs-lookup"><span data-stu-id="c86c5-140">Therefore, the process is to submit the canceled purchase order to the approval workflow so that it can go to an *Approved* state.</span></span> <span data-ttu-id="c86c5-141">Ezen a ponton a **Beszerzési rendelés előkészítése** munkaterületén nem fog megjelenni a beszerzési rendelések vázlatainak listájában.</span><span class="sxs-lookup"><span data-stu-id="c86c5-141">At that point, the purchase order will no longer appear in the list of draft purchase orders in the **Purchase order preparation** workspace.</span></span>

