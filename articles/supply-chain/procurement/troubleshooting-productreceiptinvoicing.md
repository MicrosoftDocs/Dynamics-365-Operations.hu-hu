---
title: Termékbevételezések és számlázás hibaelhárítása
description: Ez a témakör azt mutatja be, hogyan lehet javítani az termékbevételezések és számlázás használata során felmerülő problémákat.
author: SmithaNataraj
manager: tfehr
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
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
ms.openlocfilehash: 22b1abec0c6dd5f571e604c5c07379b397b8bdaa
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4999053"
---
# <a name="troubleshoot-product-receipts-and-invoicing"></a><span data-ttu-id="f79c0-103">Termékbevételezések és számlázás hibaelhárítása</span><span class="sxs-lookup"><span data-stu-id="f79c0-103">Troubleshoot product receipts and invoicing</span></span>

<span data-ttu-id="f79c0-104">Ez a témakör azt mutatja be, hogyan lehet javítani az termékbevételezések és számlázás használata során felmerülő problémákat.</span><span class="sxs-lookup"><span data-stu-id="f79c0-104">This topic describes how to fix issues that you might encounter while you work with product receipts and invoicing.</span></span>

## <a name="i-cant-post-more-than-one-invoice-for-a-purchase-order-line-that-has-category-based-items"></a><span data-ttu-id="f79c0-105">Nem tudok egynél több számlát feladni egy olyan beszerzésirendelés-sorhoz, amelyen kategória alapú cikkek szerepelnek.</span><span class="sxs-lookup"><span data-stu-id="f79c0-105">I can't post more than one invoice for a purchase order line that has category-based items.</span></span>

<span data-ttu-id="f79c0-106">A mennyiséget kötelező megadni, ha számlákat szeretne feladni.</span><span class="sxs-lookup"><span data-stu-id="f79c0-106">A quantity is mandatory if you want to post invoices.</span></span> <span data-ttu-id="f79c0-107">Ha tehát egy sor teljes mennyisége csak részlegesen lett kiszámlázva, akkor egy másik számlával nem számlázhatja a fennmaradó összeget.</span><span class="sxs-lookup"><span data-stu-id="f79c0-107">Therefore, if the full quantity of a line has been invoiced for only a partial amount, you won't be able to invoice the remaining amount on another invoice.</span></span>

## <a name="i-receive-an-object-reference-not-set-error-during-purchase-order-confirmation-or-an-exception-has-been-thrown-by-the-target-of-an-invocation-exception-occurs-during-vendor-invoice-posting"></a><span data-ttu-id="f79c0-108">A beszerzési rendelés visszaigazolásakor egy „Objektumhivatkozás nincs beállítva” hiba vagy „Kivétel történt a meghívás célja felől” kivétel jelenik meg szállítói számla feladása során.</span><span class="sxs-lookup"><span data-stu-id="f79c0-108">I receive an "Object reference not set" error during purchase order confirmation, or an "Exception has been thrown by the target of an invocation" exception occurs during vendor invoice posting.</span></span>

<span data-ttu-id="f79c0-109">Ez a hiba a beszerzési rendelések felosztásakor jelentkező ellentmondás miatt fordulhat elő.</span><span class="sxs-lookup"><span data-stu-id="f79c0-109">This issue can occur because of inconsistency in purchase order distributions.</span></span>

<span data-ttu-id="f79c0-110">A hiba blokkolásának feloldásához és a beszerzési rendelés *Vázlat* állapotra állításához nyissa meg a **Beszerzés és forrás \> Időszakos feladatok \> Tisztítás \> Beszerzési rendelés felosztásának visszaállítása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f79c0-110">To unblock this issue and reset the purchase order to a *Draft* state, go to **Procurement and sourcing \> Periodic tasks \> Clean up \> Purchase order distribution reset**.</span></span> <span data-ttu-id="f79c0-111">A további tudnivalókat lásd a következő blogbejegyzésben: [Beszerzésirendelés-felosztási hibák megoldása a Dynamics 365 Supply Chain Management-alkalmazásban](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).</span><span class="sxs-lookup"><span data-stu-id="f79c0-111">For more information, see the following blog post: [Resolve PO distribution errors in Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).</span></span>

## <a name="i-cant-consolidate-multiple-product-receipts-into-a-single-purchase-order"></a><span data-ttu-id="f79c0-112">Egyetlen beszerzési rendelésbe nem tudok több terméknyugtát egyesíteni.</span><span class="sxs-lookup"><span data-stu-id="f79c0-112">I can't consolidate multiple product receipts into a single purchase order.</span></span>

<span data-ttu-id="f79c0-113">Egyetlen beszerzési rendelésbe nem lehet több terméknyugtát összesíteni, ha a különböző szállítólevél-sorok különböző könyvelési dátumokkal rendelkeznek.</span><span class="sxs-lookup"><span data-stu-id="f79c0-113">You can't consolidate multiple product receipts into a single purchase order if the different product receipt lines have different accounting dates.</span></span>

<span data-ttu-id="f79c0-114">A Microsoft Dynamics 365 Supply Chain Management korábbi verzióiban a konszolidációt ebben a helyzetben engedélyezett volt.</span><span class="sxs-lookup"><span data-stu-id="f79c0-114">In earlier versions of Microsoft Dynamics 365 Supply Chain Management, consolidation was allowed in this situation.</span></span> <span data-ttu-id="f79c0-115">Ez a gyakorlat azonban hibákhoz vezethet.</span><span class="sxs-lookup"><span data-stu-id="f79c0-115">However, the practice is prone to error.</span></span> <span data-ttu-id="f79c0-116">A létrejövő beszerzésirendelés-sorok könyvelési dátuma nem térhet el azon terméknyugta-sorok könyvelés dátumától, amelyek alapján ezeket a beszerzésirendelés-sorokat létrehozták.</span><span class="sxs-lookup"><span data-stu-id="f79c0-116">The accounting date on the purchase order lines that are created should not differ from the accounting date on the product receipt lines that those purchase order lines were created from.</span></span> <span data-ttu-id="f79c0-117">(A beszerzési rendelés sorainak könyvelési dátuma megegyezik a beszerzési rendelés fejlécében szereplő könyvelési dátummal.) Ezért a több nyugta egyetlen beszerzési rendelésbe történő konszolidációja már nem engedélyezett.</span><span class="sxs-lookup"><span data-stu-id="f79c0-117">(The accounting date on the purchase order lines matches the accounting date on the purchase order header.) Therefore, the consolidation of multiple product receipts into a single purchase orders is no longer allowed.</span></span>

<span data-ttu-id="f79c0-118">A könyvelési dátum például költségvetési foglalások és kötelezettségvállalások esetén használatos.</span><span class="sxs-lookup"><span data-stu-id="f79c0-118">The accounting date is used, for example, for budget reservations and encumbrance.</span></span> <span data-ttu-id="f79c0-119">Ezért a termék bevételezéséről a beszerzési rendelésre való áttérés során meg kell őrizni.</span><span class="sxs-lookup"><span data-stu-id="f79c0-119">Therefore, it should be kept during the transition from product receipt to purchase order.</span></span>

## <a name="when-product-receipts-are-canceled-transactions-can-be-posted-to-a-suspended-ledger-account"></a><span data-ttu-id="f79c0-120">A termékbevételezés törlése esetén a tranzakciók feladása felfüggesztett főkönyvi számlára történhet.</span><span class="sxs-lookup"><span data-stu-id="f79c0-120">When product receipts are canceled, transactions can be posted to a suspended ledger account.</span></span>

### <a name="issue-description"></a><span data-ttu-id="f79c0-121">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="f79c0-121">Issue description</span></span>

<span data-ttu-id="f79c0-122">Ha egy termékbevételezés érvénytelenítve van, a rendszer lehetővé teszi a tranzakciók feladását a felfüggesztett főkönyvi számlákra, még akkor is, ha a fő számlákat felfüggesztették.</span><span class="sxs-lookup"><span data-stu-id="f79c0-122">If a product receipt is canceled, the system allows transactions to be posted to suspended ledger accounts, even though the main accounts are suspended.</span></span>

### <a name="reproduce-the-issue"></a><span data-ttu-id="f79c0-123">A hiba reprodukálása</span><span class="sxs-lookup"><span data-stu-id="f79c0-123">Reproduce the issue</span></span>

<span data-ttu-id="f79c0-124">A következő eljárás bemutatja a hiba reprodukálásának egyik módját.</span><span class="sxs-lookup"><span data-stu-id="f79c0-124">The following procedure shows one way to reproduce the issue.</span></span>

1. <span data-ttu-id="f79c0-125">A **Kötelezettségek paraméterei** lap **Általános** lapján győződjön meg arról, hogy a **Termékbevételezés feladása a főkönyvben** beállítás *Igen* értékre van állítva.</span><span class="sxs-lookup"><span data-stu-id="f79c0-125">On the **Accounts payable parameters** page, on the **General** tab, make sure that the **Post product receipt in ledger** option is set to *Yes*.</span></span>
1. <span data-ttu-id="f79c0-126">Hozzon létre egy beszerzési rendelést, és adjon hozzá egy *1000* mennyiséget tartalmazó rendelési sort a termékhez.</span><span class="sxs-lookup"><span data-stu-id="f79c0-126">Create a purchase order, and add an order line that has a quantity of *1,000* for a product.</span></span>
1. <span data-ttu-id="f79c0-127">Erősítse meg a beszerzési rendelést.</span><span class="sxs-lookup"><span data-stu-id="f79c0-127">Confirm the purchase order.</span></span>
1. <span data-ttu-id="f79c0-128">Adja fel a termékbevételezést, és ellenőrizze a bizonylatokat.</span><span class="sxs-lookup"><span data-stu-id="f79c0-128">Post the product receipt, and check the vouchers.</span></span>
1. <span data-ttu-id="f79c0-129">Függessze fel a kapcsolódó fő számlákat: *200140* és *140200*.</span><span class="sxs-lookup"><span data-stu-id="f79c0-129">Suspend the relevant main accounts, *200140* and *140200*.</span></span>
1. <span data-ttu-id="f79c0-130">Vonja vissza feladott termékbevételezést.</span><span class="sxs-lookup"><span data-stu-id="f79c0-130">Cancel the posted product receipt.</span></span>
1. <span data-ttu-id="f79c0-131">Figyelje meg, hogy a tranzakciók feladhatók a felfüggesztett főkönyvi számlákra.</span><span class="sxs-lookup"><span data-stu-id="f79c0-131">Notice that transactions can be posted to the suspended leger accounts.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="f79c0-132">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="f79c0-132">Issue resolution</span></span>

<span data-ttu-id="f79c0-133">A tranzakciókat fel lehet adni a felfüggesztett főkönyvi számlákra, ha a termékbevételezéseket érvénytelenítik, mert ez a viselkedés lehetővé teszi a megfelelő feladásokat.</span><span class="sxs-lookup"><span data-stu-id="f79c0-133">Transactions can be posted to the suspended leger accounts when product receipts are canceled, because this behavior allows for correct postings.</span></span>

## <a name="a-product-receipt-voucher-number-is-consumed-even-if-no-financial-voucher-is-generated-during-product-receipt"></a><span data-ttu-id="f79c0-134">A termék bevételezési bizonylatának száma akkor is fel lesz használva, ha a termék bevételezése során nem készül pénzügyi bizonylat.</span><span class="sxs-lookup"><span data-stu-id="f79c0-134">A product receipt voucher number is consumed even if no financial voucher is generated during product receipt.</span></span>

<span data-ttu-id="f79c0-135">Ha a **Kötelezettség elhatárolása termékbevételezéskor** beállítás értéke *Nem* cikkmodell-csoporthoz, akkor nem történik feladás a főkönyvbe.</span><span class="sxs-lookup"><span data-stu-id="f79c0-135">If the **Accrue liability on product receipt** option is set to *No* for the item model group, no postings to the general ledger will occur.</span></span> <span data-ttu-id="f79c0-136">A program azonban egy fizikai eseményt rögzít egy analitikába történő könyvelés céljából, és az eseményhez bizonylatszámot kell megadni.</span><span class="sxs-lookup"><span data-stu-id="f79c0-136">However, a physical event will be recorded for the purpose of accounting in a subledger, and that event requires a voucher number.</span></span> <span data-ttu-id="f79c0-137">Ez a bizonylatszám a készlettranzakciókban hivatkozott bizonylatszám.</span><span class="sxs-lookup"><span data-stu-id="f79c0-137">This voucher number is the voucher number that is referenced in the inventory transactions.</span></span>

<span data-ttu-id="f79c0-138">Azt ajánljuk, hogy a **Kötelezettség elhatárolása termékbevételezéskor** beállítás *Igen* értékre állítsa , a következő blogbejegyzésben leírtak szerint: [Vegyes költségek feladása terméknyugta időpontjában](https://cloudblogs.microsoft.com/dynamics365/no-audience/2014/11/11/post-misc-charges-at-time-of-product-receipt/).</span><span class="sxs-lookup"><span data-stu-id="f79c0-138">We recommend that you set the **Accrue liability on product receipt** option to *Yes*, as described in the following blog post: [Post Misc. charges at time of product receipt](https://cloudblogs.microsoft.com/dynamics365/no-audience/2014/11/11/post-misc-charges-at-time-of-product-receipt/).</span></span>

## <a name="the-post-to-charge-account-in-ledger-setting-isnt-turned-on"></a><span data-ttu-id="f79c0-139">A Feladás főkönyvi költségszámlára beállítás nincs bekapcsolva.</span><span class="sxs-lookup"><span data-stu-id="f79c0-139">The Post to charge account in ledger setting isn't turned on.</span></span>

### <a name="issue-description"></a><span data-ttu-id="f79c0-140">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="f79c0-140">Issue description</span></span>

<span data-ttu-id="f79c0-141">Ez a probléma egy beszerzési rendelés számlázásakor fordul elő, ha a **Feladás főkönyvi költségszámlára** beállítás *Igen* értékre van állítva a **Számla** lapon a **Kötelezettségek paramétere** oldalon.</span><span class="sxs-lookup"><span data-stu-id="f79c0-141">This issue occurs when a purchase order is invoiced, if the **Post to charge account in ledger** option is set to *Yes* on the **Invoice** tab of the **Accounts payable parameters** page.</span></span>

### <a name="reproduce-the-issue"></a><span data-ttu-id="f79c0-142">A hiba reprodukálása</span><span class="sxs-lookup"><span data-stu-id="f79c0-142">Reproduce the issue</span></span>

<span data-ttu-id="f79c0-143">A következő eljárás bemutatja a hiba reprodukálásának egyik módját.</span><span class="sxs-lookup"><span data-stu-id="f79c0-143">The following procedure shows one way to reproduce the issue.</span></span>

1. <span data-ttu-id="f79c0-144">Ugorjon a **Kötelezettségek \> Beállítás \> Kötelezettségek paraméterei pontra**.</span><span class="sxs-lookup"><span data-stu-id="f79c0-144">Go to **Accounts payable \> Setup \> Accounts payable parameters**.</span></span>
1. <span data-ttu-id="f79c0-145">A **Számla** lapon állítsa a **Feladás főkönyvi költségszámlára** beállítást *Igen* értékre.</span><span class="sxs-lookup"><span data-stu-id="f79c0-145">On the **Invoice** tab, set the **Post to charge account in ledger** option to *Yes*.</span></span>
1. <span data-ttu-id="f79c0-146">Nyissa meg a **Készletkezelés \> Beállítás \> Feladás \> Feladás** menüt.</span><span class="sxs-lookup"><span data-stu-id="f79c0-146">Go to **Inventory management \> Setup \> Posting \> Posting**.</span></span>
1. <span data-ttu-id="f79c0-147">Győződjön meg róla, hogy a **Beszerzési rendelés** lapon törölte a termékre vonatkozó beszerzési kiadások összes sorát.</span><span class="sxs-lookup"><span data-stu-id="f79c0-147">On the **Purchase order** tab, make sure that you've deleted all the lines in the purchase expenditure for the product.</span></span>
1. <span data-ttu-id="f79c0-148">Nyissa meg a következőt: **Kötelezettségek \> Beszerzési rendelések \> Minden beszerzési rendelés**.</span><span class="sxs-lookup"><span data-stu-id="f79c0-148">Go to **Accounts payable \> Purchase orders \> All purchase orders**.</span></span>
1. <span data-ttu-id="f79c0-149">Beszerzési rendelés létrehozása</span><span class="sxs-lookup"><span data-stu-id="f79c0-149">Create a purchase order.</span></span> <span data-ttu-id="f79c0-150">A **Szállítói számla** mezőben válassza ki az *1001 Acme irodai kellék* lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f79c0-150">In the **Vendor account** field, select *1001 Acme Office Supplies*.</span></span>
1. <span data-ttu-id="f79c0-151">Adjon hozzá egy beszerzési rendelési sort, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="f79c0-151">Add a purchase order line that has the following settings:</span></span>

    - <span data-ttu-id="f79c0-152">**Cikkszám:** *D0011 lézeres projektor*</span><span class="sxs-lookup"><span data-stu-id="f79c0-152">**Item number:** *D0011 Laser Projector*</span></span>
    - <span data-ttu-id="f79c0-153">**Telephely:** *1*</span><span class="sxs-lookup"><span data-stu-id="f79c0-153">**Site:** *1*</span></span>
    - <span data-ttu-id="f79c0-154">**Raktár:** *11*</span><span class="sxs-lookup"><span data-stu-id="f79c0-154">**Warehouse:** *11*</span></span>
    - <span data-ttu-id="f79c0-155">**Mennyiség:** *4*</span><span class="sxs-lookup"><span data-stu-id="f79c0-155">**Quantity:** *4*</span></span>

1. <span data-ttu-id="f79c0-156">A Műveleti ablaktáblán a **Vásárlás** lapján a **Művelet** csoportban válassza a **Megerősítés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f79c0-156">On the Action Pane, on the **Purchase** tab, in the **Action** group, select **Confirm**.</span></span>
1. <span data-ttu-id="f79c0-157">A Művelet panel **Bevételezés** lapján, a **Generálás** csoportban válassza a **Termékbevételezés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f79c0-157">On the Action Pane, on the **Receive** tab, in the **Generate** group, select **Product receipt**.</span></span>
1. <span data-ttu-id="f79c0-158">A **Termékbevételezés feladása** párbeszédpanel **Termékbevételezés** mezőjébe írjon be egy tetszőleges számot, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="f79c0-158">In the **Posting product receipt** dialog box, in the **Product receipt** field, enter an arbitrary number, and then select **OK**.</span></span>
1. <span data-ttu-id="f79c0-159">A Műveleti ablaktábla **Számla** lapján a **Létrehozás** csoportban válassza a **Számla** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f79c0-159">On the Action Pane, on the **Invoice** tab, in the **Generate** group, select **Invoice**.</span></span>
1. <span data-ttu-id="f79c0-160">A **Szám** mezőbe írjon be egy tetszőleges számot a számla sorszámaként.</span><span class="sxs-lookup"><span data-stu-id="f79c0-160">In the **Number** field, enter an arbitrary number as the invoice number.</span></span>
1. <span data-ttu-id="f79c0-161">Az egyeztetési állapotot frissítése, és adja fel.</span><span class="sxs-lookup"><span data-stu-id="f79c0-161">Update the match status, and post.</span></span>
1. <span data-ttu-id="f79c0-162">Figyelje meg, hogy a következő hibaüzenet jelenik meg, amikor egy beszerzési rendelésből generál egy számlát: „A számlatípus a Beszerzési kiadás tranzakciótípushoz a termékhez nem létezik.”</span><span class="sxs-lookup"><span data-stu-id="f79c0-162">Notice that you now receive the following error when you generate an invoice from a purchase order: "Account number for transaction type Purchase expenditure for product does not exist."</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="f79c0-163">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="f79c0-163">Issue resolution</span></span>

<span data-ttu-id="f79c0-164">Ez a számlák és a számlázási csoportok paraméter-beállításaitól függ.</span><span class="sxs-lookup"><span data-stu-id="f79c0-164">This depends on the parameter settings for invoices and invoice groups.</span></span> <span data-ttu-id="f79c0-165">A további tudnivalókat lásd a következő blogbejegyzésben: [Könyvelés beszerzési díj és készlet változásához](https://cloudblogs.microsoft.com/dynamics365/no-audience/2014/12/15/accounting-for-purchase-charge-and-stock-variation/).</span><span class="sxs-lookup"><span data-stu-id="f79c0-165">For more information, see the following blog post: [Accounting for Purchase charge and Stock variation](https://cloudblogs.microsoft.com/dynamics365/no-audience/2014/12/15/accounting-for-purchase-charge-and-stock-variation/).</span></span>
