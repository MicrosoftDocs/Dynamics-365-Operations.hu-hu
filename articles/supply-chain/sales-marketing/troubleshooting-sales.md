---
title: Értékesítési rendelések hibaelhárítása
description: Ez a témakör azt mutatja be, hogyan lehet javítani az értékesítési rendelések használata során felmerülő problémákat.
author: SmithaNataraj
manager: tfehr
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTable, SalesTableListPage
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
ms.openlocfilehash: 6e51723915892f465ce09d09ee9ed622bab9451e
ms.sourcegitcommit: c986d5234b81d31cc6d054298be6f6ec92c1754c
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/25/2020
ms.locfileid: "3889457"
---
# <a name="troubleshoot-sales-orders"></a><span data-ttu-id="b0d6a-103">Értékesítési rendelések hibaelhárítása</span><span class="sxs-lookup"><span data-stu-id="b0d6a-103">Troubleshoot sales orders</span></span>

<span data-ttu-id="b0d6a-104">Ez a témakör azt mutatja be, hogyan lehet javítani az értékesítési rendelések használata során felmerülő problémákat.</span><span class="sxs-lookup"><span data-stu-id="b0d6a-104">This topic describes how to fix issues that you might encounter while you work with sales orders.</span></span>

## <a name="the-tax-information-isnt-updated-if-i-change-the-location-on-a-sales-order-header"></a><span data-ttu-id="b0d6a-105">Az adózási információk nem frissülnek, ha módosítom a helyet egy értékesítési rendelés fejlécében.</span><span class="sxs-lookup"><span data-stu-id="b0d6a-105">The tax information isn't updated if I change the location on a sales order header.</span></span>

### <a name="issue-description"></a><span data-ttu-id="b0d6a-106">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="b0d6a-106">Issue description</span></span>

<span data-ttu-id="b0d6a-107">Ha a hely, a raktár vagy a szállítási cím egy értékesítési rendelés fejlécében vagy sor szintjén módosul, akkor a program nem frissíti automatikusan az eset adózási információit a sorokban.</span><span class="sxs-lookup"><span data-stu-id="b0d6a-107">If the site, warehouse, or delivery address is changed either on a sales order header or at the line level, the case tax information isn't automatically updated for the lines.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="b0d6a-108">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="b0d6a-108">Issue resolution</span></span>

<span data-ttu-id="b0d6a-109">Ez szándékosan van.</span><span class="sxs-lookup"><span data-stu-id="b0d6a-109">This behavior is by design.</span></span> <span data-ttu-id="b0d6a-110">A probléma oka az, hogy a szállítási cím, a hely és a raktár nem változik meg automatikusan a sor szintjén.</span><span class="sxs-lookup"><span data-stu-id="b0d6a-110">The issue occurs because the delivery address, site, and warehouse aren't automatically changed at the line level either.</span></span> <span data-ttu-id="b0d6a-111">Ezeket manuálisan kell frissítenie.</span><span class="sxs-lookup"><span data-stu-id="b0d6a-111">You must update them manually.</span></span>

## <a name="if-there-are-two-trade-agreements-for-the-same-period-or-overlapping-periods-the-same-agreement-line-is-always-selected"></a><span data-ttu-id="b0d6a-112">Ha ugyanarra az időszakra vagy egymást átfedő időszakokra két kereskedelmi megállapodás van kiválasztva, akkor minden esetben ugyanaz a szerződési sor van kiválasztva.</span><span class="sxs-lookup"><span data-stu-id="b0d6a-112">If there are two trade agreements for the same period or overlapping periods, the same agreement line is always selected.</span></span>

### <a name="issue-description"></a><span data-ttu-id="b0d6a-113">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="b0d6a-113">Issue description</span></span>

<span data-ttu-id="b0d6a-114">Ha ugyanarra az időszakra vagy egymást átfedő időszakokra két kereskedelmi megállapodást határoznak meg, minden alkalommal úgy tűnik, hogy az adott cikkeket tartalmazó értékesítésirendelés-sorok létrehozásakor ugyanez a kereskedelmi megállapodás van kiválasztva.</span><span class="sxs-lookup"><span data-stu-id="b0d6a-114">If two trade agreements are defined for the same period or overlapping periods, the same trade agreement seems to be selected every time when you create sales order lines that contain those items.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="b0d6a-115">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="b0d6a-115">Issue resolution</span></span>

<span data-ttu-id="b0d6a-116">Ha egy adott dátumra vonatkozóan egynél több kereskedelmi megállapodás van megadva, a legalacsonyabb árat tartalmazó kereskedelmi megállapodás van mindig kiválasztva.</span><span class="sxs-lookup"><span data-stu-id="b0d6a-116">If there is more than one trade agreement for a given date, the trade agreement that has the lowest price is always selected.</span></span> <span data-ttu-id="b0d6a-117">További tájékoztatásért töltse le a következő tanulmányt: [Kereskedelmi megállapodások a Microsoft Dynamics AX 2012-ben](https://www.axug.com/HigherLogic/System/DownloadDocumentFile.ashx?DocumentFileKey=3396a3a8-1f48-4d85-8cd6-5fa982f62e90).</span><span class="sxs-lookup"><span data-stu-id="b0d6a-117">For more information, download the following white paper: [Trade agreements in Microsoft Dynamics AX 2012](https://www.axug.com/HigherLogic/System/DownloadDocumentFile.ashx?DocumentFileKey=3396a3a8-1f48-4d85-8cd6-5fa982f62e90).</span></span>

## <a name="can-i-link-a-purchase-order-to-a-sales-order-to-fulfill-demand"></a><span data-ttu-id="b0d6a-118">Kapcsolható a beszerzési rendelés egy értékesítési rendeléshez igény teljesítéséhez?</span><span class="sxs-lookup"><span data-stu-id="b0d6a-118">Can I link a purchase order to a sales order to fulfill demand?</span></span>

<span data-ttu-id="b0d6a-119">Beszerzési rendelést létrehozhat értékesítési rendelésből.</span><span class="sxs-lookup"><span data-stu-id="b0d6a-119">You can create a purchase order from a sales order.</span></span> <span data-ttu-id="b0d6a-120">További információ: [Beszerzési rendelés létrehozása értékesítési rendelésből](tasks/create-purchase-order-sales-order.md).</span><span class="sxs-lookup"><span data-stu-id="b0d6a-120">For more information, see [Create a purchase order from a sales order](tasks/create-purchase-order-sales-order.md).</span></span>

## <a name="i-cant-cancel-or-delete-a-return-order-or-a-sales-order"></a><span data-ttu-id="b0d6a-121">Nem tudom érvényteleníteni vagy törölni a visszárurendelést vagy az értékesítési rendelést.</span><span class="sxs-lookup"><span data-stu-id="b0d6a-121">I can't cancel or delete a return order or a sales order.</span></span>

<span data-ttu-id="b0d6a-122">Csak a *Létrehozva* állapotú értékesítési rendelések és visszárurendelések vonhatók vissza.</span><span class="sxs-lookup"><span data-stu-id="b0d6a-122">You can cancel only sales orders and return orders that are in a *Created* state.</span></span> <span data-ttu-id="b0d6a-123">További információkkal kapcsolatban lásd: [Visszárurendelések törlése](../service-management/cancel-return-order.md).</span><span class="sxs-lookup"><span data-stu-id="b0d6a-123">For more information, see [Cancel a return order](../service-management/cancel-return-order.md).</span></span>

## <a name="when-i-try-to-cancel-a-sales-order-i-receive-a-reservations-cannot-be-removed-because-there-is-work-created-which-relies-on-the-reservations-error"></a><span data-ttu-id="b0d6a-124">Amikor megpróbálok érvényteleníteni egy értékesítési rendelést, a „Foglalások nem távolíthatók el, mert van olyan munkafolyamat, amely a foglalásokon alapul” hibaüzenet jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="b0d6a-124">When I try to cancel a sales order, I receive a "Reservations cannot be removed because there is work created which relies on the reservations" error.</span></span>

<span data-ttu-id="b0d6a-125">Ha van munka egy értékesítési rendeléshez van társítva, akkor az értékesítési rendelés nem törölhető, amíg a munka nincs érvénytelenítve és visszavonva.</span><span class="sxs-lookup"><span data-stu-id="b0d6a-125">If work is associated with a sales order, you can't cancel the sales order until the work is canceled and reversed.</span></span> <span data-ttu-id="b0d6a-126">Ez a követelmény akkor is érvényes, ha az értékesítési rendeléshez társított munka le van zárva.</span><span class="sxs-lookup"><span data-stu-id="b0d6a-126">This requirement applies even if the work that is associated with the sales order is closed.</span></span>

<span data-ttu-id="b0d6a-127">Ezen hiba javításához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="b0d6a-127">To fix this issue, follow these steps.</span></span>

1. <span data-ttu-id="b0d6a-128">Vonja vissza a munkát és a készletet helyezze vissza a kívánt helyre.</span><span class="sxs-lookup"><span data-stu-id="b0d6a-128">Cancel the work, and put inventory back into the desired location.</span></span> <span data-ttu-id="b0d6a-129">Nyissa meg az értékesítési rendelés megfelelő rakományát, majd válassza a **Kitárolt mennyiség csökkentése** lehetőséget a rakománysorban vagy a **Munka sztornírozása** lehetőséget Műveleti ablaktáblán.</span><span class="sxs-lookup"><span data-stu-id="b0d6a-129">Go to the relevant load of the sales order, and select either **Reduce picked quantity** on the load line or **Reverse work** on the Action Pane.</span></span>

    <span data-ttu-id="b0d6a-130">A munka állapota most *Érvénytelenítve*, és a rendszer automatikusan létrehozza és feldolgozza az új készletmozgatási munkát, hogy a készletet visszahelyezze arra a helyre, amely a sztornírozásnál le van írva.</span><span class="sxs-lookup"><span data-stu-id="b0d6a-130">The work now has a status of *Canceled*, and new inventory movement work is automatically created and processed to put inventory back into the location that was described at the time of reversal.</span></span>

2. <span data-ttu-id="b0d6a-131">Törölje a rakományt.</span><span class="sxs-lookup"><span data-stu-id="b0d6a-131">Delete the load.</span></span> <span data-ttu-id="b0d6a-132">A szállítmány is törölve lesz.</span><span class="sxs-lookup"><span data-stu-id="b0d6a-132">The shipment is also deleted.</span></span>
3. <span data-ttu-id="b0d6a-133">Most el kell tudnia menni az értékesítési rendeléshez, és érvényteleníteni azt.</span><span class="sxs-lookup"><span data-stu-id="b0d6a-133">You should now be able to go to the sales order and cancel it.</span></span>

## <a name="i-cant-cancel-an-intercompany-purchase-order-that-is-linked-to-a-sales-order"></a><span data-ttu-id="b0d6a-134">Nem tudok érvényteleníteni egy értékesítési rendeléshez kapcsolódó vállalatközi beszerzési rendelést.</span><span class="sxs-lookup"><span data-stu-id="b0d6a-134">I can't cancel an intercompany purchase order that is linked to a sales order.</span></span>

### <a name="issue-description"></a><span data-ttu-id="b0d6a-135">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="b0d6a-135">Issue description</span></span>

<span data-ttu-id="b0d6a-136">Ha egy értékesítési rendeléshez kapcsolódó vállalatközi beszerzési rendelést próbál meg törölni, a következő hibaüzenet jelenhet meg: „a mennyiség nem csökkenthető, mert a fennmaradó frissítési mennyiség megváltoztatja a jelet.”</span><span class="sxs-lookup"><span data-stu-id="b0d6a-136">If you try to cancel an intercompany purchase order that is linked to a sales order, you might receive the following error message: "Quantity cannot be reduced because the remaining update quantity changes sign."</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="b0d6a-137">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="b0d6a-137">Issue resolution</span></span>

<span data-ttu-id="b0d6a-138">Ez a probléma a Microsoft Dynamics 365 Supply Chain Management 10.0.13-as verziójában javítva lett.</span><span class="sxs-lookup"><span data-stu-id="b0d6a-138">This issue was fixed in Microsoft Dynamics 365 Supply Chain Management version 10.0.13.</span></span> <span data-ttu-id="b0d6a-139">Ebben a verzióban és a későbbi verziókban már érvényteleníteni lehet egy értékesítési rendeléshez kapcsolódó vállalatközi beszerzési rendelést.</span><span class="sxs-lookup"><span data-stu-id="b0d6a-139">In that version and later versions, you can now cancel an intercompany purchase order that is linked to a sales order.</span></span>

## <a name="can-i-restore-an-invoiced-sales-order-that-was-deleted"></a><span data-ttu-id="b0d6a-140">Visszaállíthatók egy számlázott értékesítési rendelést, amely törölve lett?</span><span class="sxs-lookup"><span data-stu-id="b0d6a-140">Can I restore an invoiced sales order that was deleted?</span></span>

### <a name="issue-description"></a><span data-ttu-id="b0d6a-141">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="b0d6a-141">Issue description</span></span>

<span data-ttu-id="b0d6a-142">A számlázott értékesítési rendelés tévedésből törölve lett, és vissza szeretné állítani vagy megtekinteni annak adatait.</span><span class="sxs-lookup"><span data-stu-id="b0d6a-142">An invoiced sales order was deleted by mistake, and you want to restore it or view its details.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="b0d6a-143">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="b0d6a-143">Issue resolution</span></span>

<span data-ttu-id="b0d6a-144">Ha a törölt értékesítési rendelés már számlázva van, nyissa meg a **Vevői számla \> Tranzakciók \> Eredeti dokumentum \> Részletek megtekintése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b0d6a-144">If the deleted sales order has already been invoiced, go to **Customer account \> Transactions \> Original document \> View details**.</span></span> <span data-ttu-id="b0d6a-145">Keresse meg a keresett számlát, és válassza ki, hogy megtekintse az adatait.</span><span class="sxs-lookup"><span data-stu-id="b0d6a-145">Find the invoice that you're looking for, and select it to view its details.</span></span> <span data-ttu-id="b0d6a-146">Ezek a részletek az értékesítési rendelés hivatkozását tartalmazzák.</span><span class="sxs-lookup"><span data-stu-id="b0d6a-146">These details include the sales order reference.</span></span> <span data-ttu-id="b0d6a-147">Erről a lapról az értékesítési rendelés részleteit is elérheti.</span><span class="sxs-lookup"><span data-stu-id="b0d6a-147">You should also be able to access the sales order details from that page.</span></span>

## <a name="the-deadline-of-a-sales-order-header-cant-be-found-in-the-salesorderheaderv2entity-data-entity"></a><span data-ttu-id="b0d6a-148">Az értékesítési rendelés fejlécének határideje nem található a SalesOrderHeaderV2Entity adatentitásban.</span><span class="sxs-lookup"><span data-stu-id="b0d6a-148">The deadline of a sales order header can't be found in the SalesOrderHeaderV2Entity data entity.</span></span>

<span data-ttu-id="b0d6a-149">A határidő mező nem létezik a *SalesOrderHeaderV2Entity* entitásban.</span><span class="sxs-lookup"><span data-stu-id="b0d6a-149">The deadline field doesn't exist on the *SalesOrderHeaderV2Entity* entity.</span></span>

## <a name="i-must-delete-orphaned-sales-order-records"></a><span data-ttu-id="b0d6a-150">Az elárvult értékesítési rendelési rekordokat törölnöm kell.</span><span class="sxs-lookup"><span data-stu-id="b0d6a-150">I must delete orphaned sales order records.</span></span>

<span data-ttu-id="b0d6a-151">Az elárvult értékesítési rendelések rekordjainak törléséhez futtassa az *Értékesítési rendelés törlése* ismétlődő feladatot a következő helyek valamelyikéről:</span><span class="sxs-lookup"><span data-stu-id="b0d6a-151">To clean up orphaned sales order records, run the *Sales order deletion* periodic job by going to either of the following places:</span></span>

- <span data-ttu-id="b0d6a-152">Értékesítés és marketing \> Időszakos feladatok \> Adattisztítás \> Értékesítési rendelések törlése</span><span class="sxs-lookup"><span data-stu-id="b0d6a-152">Sales and marketing \> Periodic tasks \> Clean up \> Delete sales orders</span></span>
- <span data-ttu-id="b0d6a-153">Kiskereskedelem és kereskedelem \> Kiskereskedelem és kereskedelem IT \> Adattisztítás \> Értékesítési rendelések törlése</span><span class="sxs-lookup"><span data-stu-id="b0d6a-153">Retail and commerce \> Retail and commerce IT \> Clean up \> Delete sales orders</span></span>

## <a name="is-there-a-way-to-calculate-commissions-on-invoices-that-have-already-been-posted"></a><span data-ttu-id="b0d6a-154">Van mód jutalékok kiszámítására a már feladott számlákon?</span><span class="sxs-lookup"><span data-stu-id="b0d6a-154">Is there a way to calculate commissions on invoices that have already been posted?</span></span>

<span data-ttu-id="b0d6a-155">A Supply Chain Management jelenleg nem támogatja a jutalékok számítását a feladott számlákra vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="b0d6a-155">Supply Chain Management doesn't currently support the calculation of commissions for posted invoices.</span></span>

## <a name="a-bundle-item-isnt-supported-in-an-intercompany-process"></a><span data-ttu-id="b0d6a-156">Egy csomagolt cikk nem támogatott a vállalatközi folyamatban.</span><span class="sxs-lookup"><span data-stu-id="b0d6a-156">A bundle item isn't supported in an intercompany process.</span></span>

<span data-ttu-id="b0d6a-157">A csomagolt cikk nem érhető el a beszerzési rendeléshez, mivel a csomagolt cikkhez tartozó értékesítésirendelés-sorok vizsgálatakor láthatja, hogy a mennyiség *0* (nulla), és az állapot *Érvénytelenítve*.</span><span class="sxs-lookup"><span data-stu-id="b0d6a-157">The bundle item isn't available for the purchase order because, if you examine the sales order lines for the bundle item, you will notice that the quantity is *0* (zero) and the status is *Cancelled*.</span></span> <span data-ttu-id="b0d6a-158">Ez szándékosan van.</span><span class="sxs-lookup"><span data-stu-id="b0d6a-158">This behavior is by design.</span></span> <span data-ttu-id="b0d6a-159">Az értékesítési rendelés csak a csomagolt cikk elemeit vásárolja.</span><span class="sxs-lookup"><span data-stu-id="b0d6a-159">The sales order buys only the components of the bundle item.</span></span> <span data-ttu-id="b0d6a-160">Nem vásárolja meg magát a csomagolt elemet.</span><span class="sxs-lookup"><span data-stu-id="b0d6a-160">It doesn't buy the bundle item itself.</span></span>

<span data-ttu-id="b0d6a-161">Ha csomagban kell vásárolnia, gondolja végig, hogy csomagként kell-e megjelölni , mivel ez a funkció valójában bevétel-megjelenítési forgatókönyvekhez van tervezve.</span><span class="sxs-lookup"><span data-stu-id="b0d6a-161">If you must buy a bundle, consider whether you have to mark it as bundle item, because this functionality is actually designed for revenue recognition scenarios.</span></span> <span data-ttu-id="b0d6a-162">További információ a csomagolt cikkekkel kapcsolatosan: [Csomagok](../../finance/accounts-receivable/revenue-recognition-setup.md#bundles).</span><span class="sxs-lookup"><span data-stu-id="b0d6a-162">For more information about bundle items, see [Bundles](../../finance/accounts-receivable/revenue-recognition-setup.md#bundles).</span></span>
