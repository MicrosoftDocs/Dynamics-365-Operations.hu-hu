---
title: Beszerzési rendelések hibaelhárítása
description: Ez a témakör azt mutatja be, hogyan lehet javítani a beszerzési rendelések használata során felmerülő problémákat.
author: SmithaNataraj
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-9-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 964f31c21faae6a947174f637624aca917881297
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5841455"
---
# <a name="troubleshoot-purchase-orders"></a><span data-ttu-id="c568d-103">Beszerzési rendelések hibaelhárítása</span><span class="sxs-lookup"><span data-stu-id="c568d-103">Troubleshoot purchase orders</span></span>

<span data-ttu-id="c568d-104">Ez a témakör azt mutatja be, hogyan lehet javítani a beszerzési rendelések használata során felmerülő problémákat.</span><span class="sxs-lookup"><span data-stu-id="c568d-104">This topic describes how to fix issues that you might encounter while you work with purchase orders.</span></span>

## <a name="an-action-can-be-completed-only-after-the-line-number-is-fully-distributed"></a><span data-ttu-id="c568d-105">Egy művelet csak akkor hajtható végre, ha a sorszám teljesen ki van osztva.</span><span class="sxs-lookup"><span data-stu-id="c568d-105">An action can be completed only after the line number is fully distributed.</span></span>

<span data-ttu-id="c568d-106">Ez a hiba a beszerzési rendelések felosztásakor jelentkező ellentmondás miatt fordulhat elő.</span><span class="sxs-lookup"><span data-stu-id="c568d-106">This issue can occur because of inconsistency in purchase order distributions.</span></span>

<span data-ttu-id="c568d-107">A hiba blokkolásának feloldásához és a beszerzési rendelés *Vázlat* állapotra állításához nyissa meg a **Beszerzés és forrás \> Időszakos feladatok \> Tisztítás \> Beszerzési rendelés felosztásának visszaállítása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c568d-107">To unblock this issue and reset the purchase order to a *Draft* state, go to **Procurement and sourcing \> Periodic tasks \> Clean up \> Purchase order distribution reset**.</span></span> <span data-ttu-id="c568d-108">A további tudnivalókat lásd a következő blogbejegyzésben: [Beszerzésirendelés-felosztási hibák megoldása a Dynamics 365 Supply Chain Management-alkalmazásban](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).</span><span class="sxs-lookup"><span data-stu-id="c568d-108">For more information, see the following blog post: [Resolve PO distribution errors in Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).</span></span>

## <a name="when-purchase-orders-are-imported-through-data-management-purchase-order-line-numbers-dont-follow-the-increment-that-defined-in-system-parameters"></a><span data-ttu-id="c568d-109">Amikor a beszerzési rendeléseket adatkezelés útján importálja, a beszerzésirendelés-sorok száma nem követi a rendszer paraméterei között megadott növekményt.</span><span class="sxs-lookup"><span data-stu-id="c568d-109">When purchase orders are imported through data management, purchase order line numbers don't follow the increment that defined in system parameters.</span></span>

### <a name="issue-description"></a><span data-ttu-id="c568d-110">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="c568d-110">Issue description</span></span>

<span data-ttu-id="c568d-111">Alapértelmezés szerint a az automatikusan generált sorszámok a beszerzésirendelés-sorokhoz, amelyek a *Beszerésirendelés-sorok V2* adatentitáson keresztül vannak importálva, nem használják a rendszer számnövekményét, ami a rendszerparaméterekben van meghatározva.</span><span class="sxs-lookup"><span data-stu-id="c568d-111">By default, automatically generated line numbers for purchase order lines that are imported through the *Purchase order lines V2* data entity don't use the system line number increment that is specified in system parameters.</span></span> <span data-ttu-id="c568d-112">Ha kézzel hoz létre egy beszerzési rendelést, és a felhasználói felületen (UI) keresztül ad hozzá sorokat, akkor a program a sorszámokat helyesen növeli.</span><span class="sxs-lookup"><span data-stu-id="c568d-112">If you manually create a purchase order and add lines through the user interface (UI), the line numbers are incremented correctly.</span></span> <span data-ttu-id="c568d-113">Az Adatkezelési keretrendszer (DMF) használata esetén azonban nem megfelelőek a növekmények.</span><span class="sxs-lookup"><span data-stu-id="c568d-113">However, if you use the Data management framework (DMF), they aren't incremented correctly.</span></span>

<span data-ttu-id="c568d-114">Ez a probléma azért fordulhat elő, mert amikor DMF keresztül importál sorokat, ha a sorok száma még nincs hozzárendelve az importált entitáshoz, akkor a rendszer a DMF metódusát használja a hozzárendelésekhez.</span><span class="sxs-lookup"><span data-stu-id="c568d-114">This issue occurs because, when you import lines via DMF, if line numbers aren't already assigned in the imported entity, the system uses DMF's method for assigning them.</span></span> <span data-ttu-id="c568d-115">Ez a módszer mindig eggyel növeli a sorszámokat.</span><span class="sxs-lookup"><span data-stu-id="c568d-115">That method always increments line numbers by one.</span></span>

### <a name="issue-workaround"></a><span data-ttu-id="c568d-116">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="c568d-116">Issue workaround</span></span>

<span data-ttu-id="c568d-117">Ügyeljen arra, hogy a kívánt sorszámok már meg legyenek adva az adatelem sorszám mezőiben a beszerzésirendelés-sorok importálásakor.</span><span class="sxs-lookup"><span data-stu-id="c568d-117">Make sure that the desired line numbers are already given in the data entity line number fields when you import the purchase order lines.</span></span> <span data-ttu-id="c568d-118">Ebben az esetben a DMF nem írja felül a sorszámokat.</span><span class="sxs-lookup"><span data-stu-id="c568d-118">In this case, DMF won't overwrite the line numbers.</span></span>

## <a name="a-default-tax-group-and-a-default-cash-discount-arent-filled-in-from-the-invoice-account"></a><span data-ttu-id="c568d-119">Egy alapértelmezett adócsoport és egy alapértelmezett készpénzfizetési engedmény nem kerül kitöltésre a számlázási fiókból.</span><span class="sxs-lookup"><span data-stu-id="c568d-119">A default tax group and a default cash discount aren't filled in from the invoice account.</span></span>

<span data-ttu-id="c568d-120">Ha olyan számlázási fiókot használ, amely eltér a vevői számlától, akkor egy alapértelmezett áfacsoport és egy alapértelmezett készpénzfizetési engedmény nem lesz kitöltve a számlázási fiókból a beszerzési rendelés létrehozásakor.</span><span class="sxs-lookup"><span data-stu-id="c568d-120">If you're using an invoice account that differs from the customer account, a default tax group and a default cash discount aren't filled in from the invoice account when a purchase order is created.</span></span>

<span data-ttu-id="c568d-121">Ez szándékosan van.</span><span class="sxs-lookup"><span data-stu-id="c568d-121">This behavior is by design.</span></span> <span data-ttu-id="c568d-122">Az adócsoport, készpénzfizetési engedmények és egyéb áradatok alapértelmezett értékei a vevői fiókon, nem pedig a számlázási fiókon alapulnak.</span><span class="sxs-lookup"><span data-stu-id="c568d-122">The default values for the tax group, cash discounts, and other price information are based on the customer account, not the invoice account.</span></span>

## <a name="i-receive-an-object-reference-not-set-error-during-purchase-order-confirmation-or-an-exception-has-been-thrown-by-the-target-of-an-invocation-exception-occurs-during-vendor-invoice-posting"></a><span data-ttu-id="c568d-123">A beszerzési rendelés visszaigazolásakor egy „Objektumhivatkozás nincs beállítva” hiba vagy „Kivétel történt a meghívás célja felől” kivétel jelenik meg szállítói számla feladása során.</span><span class="sxs-lookup"><span data-stu-id="c568d-123">I receive an "Object reference not set" error during purchase order confirmation, or an "Exception has been thrown by the target of an invocation" exception occurs during vendor invoice posting.</span></span>

<span data-ttu-id="c568d-124">Ez a hiba a beszerzési rendelések felosztásakor jelentkező ellentmondás miatt fordulhat elő.</span><span class="sxs-lookup"><span data-stu-id="c568d-124">This issue can occur because of inconsistency in purchase order distributions.</span></span>

<span data-ttu-id="c568d-125">A hiba blokkolásának feloldásához és a beszerzési rendelés *Vázlat* állapotra állításához nyissa meg a **Beszerzés és forrás \> Időszakos feladatok \> Tisztítás \> Beszerzési rendelés felosztásának visszaállítása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c568d-125">To unblock this issue and reset the purchase order to a *Draft* state, go to **Procurement and sourcing \> Periodic tasks \> Clean up \> Purchase order distribution reset**.</span></span> <span data-ttu-id="c568d-126">A további tudnivalókat lásd a következő blogbejegyzésben: [Beszerzésirendelés-felosztási hibák megoldása a Dynamics 365 Supply Chain Management-alkalmazásban](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).</span><span class="sxs-lookup"><span data-stu-id="c568d-126">For more information, see the following blog post: [Resolve PO distribution errors in Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).</span></span>

## <a name="one-or-more-accounting-distributions-are-either-over-distributed-or-under-distributed"></a><span data-ttu-id="c568d-127">Egy vagy több könyvelési felosztás túlzottan fel van osztva, vagy nincsen eléggé felosztva.</span><span class="sxs-lookup"><span data-stu-id="c568d-127">One or more accounting distributions are either over-distributed or under-distributed.</span></span>

### <a name="issue-description"></a><span data-ttu-id="c568d-128">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="c568d-128">Issue description</span></span>

<span data-ttu-id="c568d-129">A következő hibaüzenet jelenik meg: „Egy vagy több könyvelési felosztás túlzottan fel van osztva, vagy nincsen eléggé felosztva.”</span><span class="sxs-lookup"><span data-stu-id="c568d-129">You receive the following error: "One or more accounting distributions is either over-distributed or under-distributed."</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="c568d-130">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="c568d-130">Issue resolution</span></span>

<span data-ttu-id="c568d-131">Ez a hiba a beszerzési rendelések felosztásakor jelentkező ellentmondás miatt fordulhat elő.</span><span class="sxs-lookup"><span data-stu-id="c568d-131">This issue can occur because of inconsistency in purchase order distributions.</span></span>

<span data-ttu-id="c568d-132">A hiba blokkolásának feloldásához és a beszerzési rendelés *Vázlat* állapotra állításához nyissa meg a **Beszerzés és forrás \> Időszakos feladatok \> Tisztítás \> Beszerzési rendelés felosztásának visszaállítása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c568d-132">To unblock this issue and reset the purchase order to a *Draft* state, go to **Procurement and sourcing \> Periodic tasks \> Clean up \> Purchase order distribution reset**.</span></span> <span data-ttu-id="c568d-133">A további tudnivalókat lásd a következő blogbejegyzésben: [Beszerzésirendelés-felosztási hibák megoldása a Dynamics 365 Supply Chain Management-alkalmazásban](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).</span><span class="sxs-lookup"><span data-stu-id="c568d-133">For more information, see the following blog post: [Resolve PO distribution errors in Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).</span></span>

## <a name="can-i-show-only-purchase-orders-that-i-created"></a><span data-ttu-id="c568d-134">Megjeleníthetem a csak általam létrehozott beszerzési rendeléseket?</span><span class="sxs-lookup"><span data-stu-id="c568d-134">Can I show only purchase orders that I created?</span></span>

<span data-ttu-id="c568d-135">Ez a funkció jelenleg nem érhető el.</span><span class="sxs-lookup"><span data-stu-id="c568d-135">This functionality isn't currently available.</span></span>

## <a name="can-i-reserve-inventory-and-create-transactions-against-registered-inventory-on-a-purchase-order"></a><span data-ttu-id="c568d-136">Lefoglalhatók készletet és létrehozhatok tranzakciókat egy beszerzési rendelésen szereplő regisztrált készlettel szemben?</span><span class="sxs-lookup"><span data-stu-id="c568d-136">Can I reserve inventory and create transactions against registered inventory on a purchase order?</span></span>

### <a name="issue-description"></a><span data-ttu-id="c568d-137">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="c568d-137">Issue description</span></span>

<span data-ttu-id="c568d-138">A készletet továbbra is lefoglalhatja még akkor is, ha a cikkek *Regisztrált* állapotban vannak a beszerzési rendelésen.</span><span class="sxs-lookup"><span data-stu-id="c568d-138">Even when items are in a *Registered* state on a purchase order, you can still reserve the inventory.</span></span> <span data-ttu-id="c568d-139">Más szóval a regisztrált készlettel szemben is lehet tranzakciókat létrehozni.</span><span class="sxs-lookup"><span data-stu-id="c568d-139">In other words, you can create transactions against the registered inventory.</span></span>

### <a name="reproduce-the-issue"></a><span data-ttu-id="c568d-140">A hiba reprodukálása</span><span class="sxs-lookup"><span data-stu-id="c568d-140">Reproduce the issue</span></span>

<span data-ttu-id="c568d-141">A következő eljárás bemutatja a hiba reprodukálásának egyik módját.</span><span class="sxs-lookup"><span data-stu-id="c568d-141">The following procedure shows one way to reproduce the issue.</span></span>

1. <span data-ttu-id="c568d-142">Beszerzési rendelés létrehozása</span><span class="sxs-lookup"><span data-stu-id="c568d-142">Create a purchase order.</span></span>
2. <span data-ttu-id="c568d-143">Regisztrálja a beszerzési rendelés sorát.</span><span class="sxs-lookup"><span data-stu-id="c568d-143">Register the purchase order line.</span></span>
3. <span data-ttu-id="c568d-144">Figyelje meg, hogy a regisztrált készlettel szemben foglalásokat vagy tranzakciókat lehet létrehozni.</span><span class="sxs-lookup"><span data-stu-id="c568d-144">Notice that you can generate reservations or transactions against the registered inventory.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="c568d-145">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="c568d-145">Issue resolution</span></span>

<span data-ttu-id="c568d-146">Ez szándékosan van.</span><span class="sxs-lookup"><span data-stu-id="c568d-146">This behavior is by design.</span></span> <span data-ttu-id="c568d-147">A várakozás az, hogy a regisztrált cikkek fizikailag megérkeztek a raktárba vagy a készletbe, és így elérhetőek a foglalásra.</span><span class="sxs-lookup"><span data-stu-id="c568d-147">The expectation is that the registered items have physically arrived in the warehouse or inventory, and that they are therefore available for reservation.</span></span>

## <a name="purchase-orders-dont-reflect-the-language-settings-of-the-legal-entity"></a><span data-ttu-id="c568d-148">A beszerzési rendelések nem veszik figyelembe a jogi személy nyelvi beállításait.</span><span class="sxs-lookup"><span data-stu-id="c568d-148">Purchase orders don't reflect the language settings of the legal entity.</span></span>

### <a name="issue-description"></a><span data-ttu-id="c568d-149">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="c568d-149">Issue description</span></span>

<span data-ttu-id="c568d-150">A beszerzési rendelésen szereplő terméknév a rendszer nyelvén jelenik meg a beszerzési rendelés létrehozásához használt jogi személyhez megadott nyelv helyett.</span><span class="sxs-lookup"><span data-stu-id="c568d-150">The product name on a purchase order is shown in the system language instead of the language that is set for the legal entity where the purchase order was created.</span></span>

### <a name="reproduce-the-issue"></a><span data-ttu-id="c568d-151">A hiba reprodukálása</span><span class="sxs-lookup"><span data-stu-id="c568d-151">Reproduce the issue</span></span>

<span data-ttu-id="c568d-152">A következő eljárás bemutatja a hiba reprodukálásának egyik módját.</span><span class="sxs-lookup"><span data-stu-id="c568d-152">The following procedure shows one way to reproduce the issue.</span></span>

1. <span data-ttu-id="c568d-153">A rendszer nyelvét állítsa *EN-US* (amerikai angol) értékre.</span><span class="sxs-lookup"><span data-stu-id="c568d-153">Set the system language to *EN-US* (US English).</span></span>
1. <span data-ttu-id="c568d-154">Győződjön meg róla, hogy van olyan termék, ahol az *EN-US* és *DE* (német) nyelvek vannak fenntartva a termék név fordításaihoz.</span><span class="sxs-lookup"><span data-stu-id="c568d-154">Make sure that there is a product where the *EN-US* and *DE* (German) languages are maintained for translations of the product name.</span></span>
1. <span data-ttu-id="c568d-155">Jogi személy nyelvét módosítsa *DE* értékre.</span><span class="sxs-lookup"><span data-stu-id="c568d-155">Change the language of a legal entity to *DE*.</span></span>
1. <span data-ttu-id="c568d-156">A jogi személyben, ahol a nyelv beállítása *DE* hozzon létre egy beszerzési rendelés, ami tartalmazza a terméket.</span><span class="sxs-lookup"><span data-stu-id="c568d-156">In the legal entity where *DE* is set as the language, create a purchase order that includes the product.</span></span>
1. <span data-ttu-id="c568d-157">Figyelje meg, hogy a termék neve továbbra is az angol nyelven jelenik meg (a rendszer nyelvén).</span><span class="sxs-lookup"><span data-stu-id="c568d-157">Notice that the product name is still shown in US English (the system language).</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="c568d-158">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="c568d-158">Issue resolution</span></span>

<span data-ttu-id="c568d-159">Ez szándékosan van.</span><span class="sxs-lookup"><span data-stu-id="c568d-159">This behavior is by design.</span></span> <span data-ttu-id="c568d-160">A beszerzési rendeléseken a termék mindig a rendszer nyelvén jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="c568d-160">On purchase orders, the product is always shown in the system language.</span></span> <span data-ttu-id="c568d-161">A beszerzési rendelés nyelvét a rendszer a visszaigazolási napló létrehozásakor használja.</span><span class="sxs-lookup"><span data-stu-id="c568d-161">The purchase order language is used when a confirmation journal is created.</span></span>

## <a name="the-approved-vendor-list-by-product-entity-doesnt-allow-the-effective-date-to-be-changed"></a><span data-ttu-id="c568d-162">Az Engedélyezett szállító lista a termék entitása nem teszi lehetővé a hatályos dátum módosítását.</span><span class="sxs-lookup"><span data-stu-id="c568d-162">The Approved vendor list by product entity doesn't allow the effective date to be changed.</span></span>

### <a name="issue-description"></a><span data-ttu-id="c568d-163">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="c568d-163">Issue description</span></span>

<span data-ttu-id="c568d-164">A termék olyan engedélyezett szállítóval rendelkezik, amely például 2018. január 11-i (*01/11/2018*) érvényességi dátummal és a *Soha* lejárati dátummal rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="c568d-164">A product has an approved vendor that has, for example, an effective date of January 11, 2018 (*01/11/2018*), and an expiration date of *Never*.</span></span> <span data-ttu-id="c568d-165">Ha a hatályosság dátumát 2018. január 10-re (*01/10/2018*) vagy 2018. január 12-re (*01/12/2018*) szeretné módosítani, akkor a következő hibaüzenet jelenik meg:</span><span class="sxs-lookup"><span data-stu-id="c568d-165">If you try to change the effective date to January 10, 2018 (*01/10/2018*), or January 12, 2018 (*01/12/2018*), you receive the following error:</span></span>

> <span data-ttu-id="c568d-166">Nem hozható létre rekord az Engedélyezett szállítói listán (PdsApproveVendorList).</span><span class="sxs-lookup"><span data-stu-id="c568d-166">Cannot create a record in Approved supplier list (PdsApproveVendorList).</span></span> <span data-ttu-id="c568d-167">A „Lejárat” értéknek nagyobbnak kell lennie, mint a „Hatályos” értéknek.</span><span class="sxs-lookup"><span data-stu-id="c568d-167">The 'Expiration' value needs to be greater than or equal to the 'Effective' value.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="c568d-168">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="c568d-168">Issue resolution</span></span>

<span data-ttu-id="c568d-169">Csak addig hosszabbíthatja meg azt az időszakot, ameddig a szállítót jóváhagyták.</span><span class="sxs-lookup"><span data-stu-id="c568d-169">You can only extend the period that the vendor is approved for.</span></span> <span data-ttu-id="c568d-170">Az alábbi szabályokat kell betartani:</span><span class="sxs-lookup"><span data-stu-id="c568d-170">The following rules apply:</span></span>

- <span data-ttu-id="c568d-171">Ha azt szeretné, hogy a program a hatályossági dátumot a szállítóhoz tartozó létező rekordoknál (időszakok) korábbira módosítsa, akkor az új időszak lejárati dátumának korábban kell lennie a meglévő rekordok összes lejárati dátumával.</span><span class="sxs-lookup"><span data-stu-id="c568d-171">To change the effective date so that it's earlier than any of the existing records (periods) for the item vendor, the expiration date of the new period must be before all the expiration dates in the existing records.</span></span>
- <span data-ttu-id="c568d-172">Ha módosítani szeretné a lejárati dátumot úgy, hogy az később legyen, mint a meglévő időszakok, akkor az érvényességi dátumnak a legkésőbbi lejárati dátum után kell lennie minden meglévő rekordban.</span><span class="sxs-lookup"><span data-stu-id="c568d-172">To change the expiration date so that it's later than any of the existing periods, the effective date must be after the latest expiration date in any existing record.</span></span>
- <span data-ttu-id="c568d-173">Ha csökkenteni szeretné a szállító számára jóváhagyott teljes időszakot, akkor törölnie kell vagy módosítania kell a meglévő rekordokat.</span><span class="sxs-lookup"><span data-stu-id="c568d-173">To reduce the overall period that the vendor is approved for, you must delete or modify existing records.</span></span> <span data-ttu-id="c568d-174">Azt is megteheti, hogy az Importálás során a **csonkolás** kapcsolót használja.</span><span class="sxs-lookup"><span data-stu-id="c568d-174">Alternatively, you can use the **truncate** switch during import.</span></span> <span data-ttu-id="c568d-175">Ez a kapcsoló törli a táblából a jóváhagyott szállítókhoz tartozó összes meglévő rekordot.</span><span class="sxs-lookup"><span data-stu-id="c568d-175">This switch deletes all existing records in the table for approved vendors by item.</span></span>

<span data-ttu-id="c568d-176">A probléma leírásában ismertetett példa esetében, amikor a rekord érvényességi dátuma *01/11/2018* érvényességi dátuma és a lejárati dátuma *Soha*, importálhat egy olyan új rekordot, amelynek érvényességi dátuma *01/10/2018*, és a lejárati dátuma *Soha*.</span><span class="sxs-lookup"><span data-stu-id="c568d-176">For the example scenario that is described in the issue description, where a record has an effective date of *01/11/2018* and an expiration date of *Never*, you can import a new record that has an effective date of *01/10/2018* and an expiration date of *Never*.</span></span> <span data-ttu-id="c568d-177">Az időszakot azonban nem lehet csökkenteni úgy, hogy az érvényességi dátumot *01/12/2018* értékre módosítja az adatkezelési folyamaton keresztül.</span><span class="sxs-lookup"><span data-stu-id="c568d-177">However, you can't reduce the period so that the effective date is updated to *01/12/2018* via data management.</span></span> <span data-ttu-id="c568d-178">Ezt a módosítást a felhasználói felületen keresztül kell elvégeznie.</span><span class="sxs-lookup"><span data-stu-id="c568d-178">You must make this change through the UI.</span></span>

## <a name="after-i-change-the-delivery-address-on-a-purchase-order-header-the-delivery-name-isnt-synced"></a><span data-ttu-id="c568d-179">A beszerzési rendelés fejlécében szereplő szállítási cím módosítása után a szállítási név nincs szinkronizálva.</span><span class="sxs-lookup"><span data-stu-id="c568d-179">After I change the delivery address on a purchase order header, the delivery name isn't synced.</span></span>

### <a name="issue-description"></a><span data-ttu-id="c568d-180">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="c568d-180">Issue description</span></span>

<span data-ttu-id="c568d-181">Egy beszerzési rendelés fejlécében szereplő cím olyan címre módosul, amely nem a szállítási cím.</span><span class="sxs-lookup"><span data-stu-id="c568d-181">The address on the header of a purchase order is updated to an address that isn't a delivery address.</span></span> <span data-ttu-id="c568d-182">Bár a cím frissítve van a beszerzési rendelésen, a szállítási név nem frissül a frissített cím alapján.</span><span class="sxs-lookup"><span data-stu-id="c568d-182">Although the address is updated on the purchase order, the delivery name isn't updated based on the updated address.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="c568d-183">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="c568d-183">Issue resolution</span></span>

<span data-ttu-id="c568d-184">Ez szándékosan van.</span><span class="sxs-lookup"><span data-stu-id="c568d-184">This behavior is by design.</span></span> <span data-ttu-id="c568d-185">A kiválasztott cím besorolása szállítási cím kell legyen.</span><span class="sxs-lookup"><span data-stu-id="c568d-185">The selected address must be classified as a delivery address.</span></span> <span data-ttu-id="c568d-186">Ellenkező esetben a szállítási név nem módosul a kiválasztott cím alapján.</span><span class="sxs-lookup"><span data-stu-id="c568d-186">Otherwise, the delivery name isn't updated based on the selected address.</span></span>

## <a name="can-i-find-the-user-who-canceled-a-purchase-order"></a><span data-ttu-id="c568d-187">Megkereshetem azt a felhasználót, aki törölte a beszerzési rendelést?</span><span class="sxs-lookup"><span data-stu-id="c568d-187">Can I find the user who canceled a purchase order?</span></span>

<span data-ttu-id="c568d-188">Ezt az információt csak akkor követi nyomon a program, ha a beszerzési rendelésen alkalmazva van a változások követése.</span><span class="sxs-lookup"><span data-stu-id="c568d-188">This information is tracked only if the purchase order is subject to change management.</span></span> <span data-ttu-id="c568d-189">Ha változáskövetést használ, megtekintheti, hogy ki küldte be a módosítást (a visszavonást), és ki hagyta jóvá.</span><span class="sxs-lookup"><span data-stu-id="c568d-189">If you use change management, you can see who submitted the change (the cancellation), and who approved it.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]