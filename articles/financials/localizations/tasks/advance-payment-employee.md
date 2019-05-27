---
title: EEU-00047 Előlegfizetés alkalmazottnak
description: Ez az eljárás bemutatja, hogyan lehet tranzakciókat beállítani és regisztrálni egy előlegre jogosult számára.
author: v-oloski
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RCashTable, LedgerJournalSetup, HcmWorkerGroup_RU, EmplPosting_RU, VendParameters, RCashPosting, BankParameters, PaymTerm, HcmWorker, HcmWorkerNewWorker, HcmWorkerAdvHolderTableListPage_RU, HcmWorkerAdvHolderTable_RU, PurchTable, PurchCreateOrder, HcmAdvHolderLookup_RU, InventItemIdLookupPurchase, VendEditInvoice, VendEditInvoiceDefaultQuantityForLinesDropDialog, EmplTrans_RU, EmplBalance_RU
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Czech Republic, Estonia, Hungary, Latvia, Lithuania, Poland, Russia
ms.author: v-oloski
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ffb49721ca3b1c180199230a5f7b9678e4e51186
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/07/2019
ms.locfileid: "1537967"
---
# <a name="eeu-00047-advance-payment-to-employee"></a><span data-ttu-id="52b73-103">EEU-00047 Előlegfizetés alkalmazottnak</span><span class="sxs-lookup"><span data-stu-id="52b73-103">EEU-00047 Advance payment to employee</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="52b73-104">Ez az eljárás bemutatja, hogyan lehet tranzakciókat beállítani és regisztrálni egy előlegre jogosult számára.</span><span class="sxs-lookup"><span data-stu-id="52b73-104">This procedure demonstrates how to set up and register transactions for an advance holder.</span></span> <span data-ttu-id="52b73-105">Ezt a eljárást a DEMF bemutatócéget használva hozták létre, az elsődleges címéhez tartozó ország pedig Litvánia.</span><span class="sxs-lookup"><span data-stu-id="52b73-105">This procedure was created using the demo data company DEMF with a primary address in Lithuania.</span></span> <span data-ttu-id="52b73-106">Ez a feladat csak az olyan jogi személyek esetében működik, amelyekben Lengyelországban, Litvániában, Lettországban, Észtországban, Csehországban vagy Magyarországon van az elsődleges címe.</span><span class="sxs-lookup"><span data-stu-id="52b73-106">This task only works for legal entities with a primary address in Poland, Lithuania, Latvia, Estonia, Czech Republic, or Hungary.</span></span> <span data-ttu-id="52b73-107">Az eljárás egy olyan szolgáltatáshoz tartozik, amely a Dynamics 365 for Operations 1611-es verziójában jelent meg.</span><span class="sxs-lookup"><span data-stu-id="52b73-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="create-a-new-cash-account"></a><span data-ttu-id="52b73-108">Új készpénzszámla létrehozása</span><span class="sxs-lookup"><span data-stu-id="52b73-108">Create a new cash account</span></span>
1. <span data-ttu-id="52b73-109">Nyissa meg a következőt: Készpénz- és bankkezelés > Bankszámlák > Készpénzszámlák.</span><span class="sxs-lookup"><span data-stu-id="52b73-109">Go to Cash and bank management > Bank accounts > Cash accounts.</span></span>
2. <span data-ttu-id="52b73-110">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="52b73-110">Click New.</span></span>
3. <span data-ttu-id="52b73-111">A Készpénz mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="52b73-111">In the Cash field, type a value.</span></span>
4. <span data-ttu-id="52b73-112">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="52b73-112">In the Name field, type a value.</span></span>
5. <span data-ttu-id="52b73-113">A Számsorozatcsoport mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="52b73-113">In the Number sequence group field, enter or select a value.</span></span>
6. <span data-ttu-id="52b73-114">Bontsa ki az Ellenőrzés szakaszt.</span><span class="sxs-lookup"><span data-stu-id="52b73-114">Expand the Validation section.</span></span>
7. <span data-ttu-id="52b73-115">A Pénznem mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="52b73-115">In the Currency field, enter or select a value.</span></span>
8. <span data-ttu-id="52b73-116">Válassza az Igen lehetőséget a Negatív készpénz mezőben.</span><span class="sxs-lookup"><span data-stu-id="52b73-116">Select Yes in the Negative cash field.</span></span>
9. <span data-ttu-id="52b73-117">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="52b73-117">Click Save.</span></span>

## <a name="create-a-new-journal"></a><span data-ttu-id="52b73-118">Új napló létrehozása</span><span class="sxs-lookup"><span data-stu-id="52b73-118">Create a new journal</span></span>
1. <span data-ttu-id="52b73-119">Ugorjon a Főkönyv > Naplóbeállítások > Naplónevek pontra.</span><span class="sxs-lookup"><span data-stu-id="52b73-119">Go to General ledger > Journal setup > Journal names.</span></span>
2. <span data-ttu-id="52b73-120">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="52b73-120">Click New.</span></span>
3. <span data-ttu-id="52b73-121">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="52b73-121">In the Name field, type a value.</span></span>
4. <span data-ttu-id="52b73-122">A Bizonylatsorozat mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="52b73-122">In the Voucher series field, enter or select a value.</span></span>
5. <span data-ttu-id="52b73-123">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="52b73-123">Click Save.</span></span>
6. <span data-ttu-id="52b73-124">Kattintson az Új elemre.</span><span class="sxs-lookup"><span data-stu-id="52b73-124">Click New.</span></span>
7. <span data-ttu-id="52b73-125">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="52b73-125">In the Name field, type a value.</span></span>
8. <span data-ttu-id="52b73-126">A Napló típusa mezőben válasszon ki egy lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="52b73-126">In the Journal type field, select an option.</span></span>
9. <span data-ttu-id="52b73-127">A Bizonylatsorozat mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="52b73-127">In the Voucher series field, enter or select a value.</span></span>
10. <span data-ttu-id="52b73-128">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="52b73-128">Click Save.</span></span>

## <a name="create-an-advance-holder-group"></a><span data-ttu-id="52b73-129">Előlegre jogosult csoport létrehozása</span><span class="sxs-lookup"><span data-stu-id="52b73-129">Create an advance holder group</span></span>
1. <span data-ttu-id="52b73-130">Ugrás a Kötelezettségek > Beállítás > Előlegre jogosultak > Előlegre jogosult csoportok elemre.</span><span class="sxs-lookup"><span data-stu-id="52b73-130">Go to Accounts payable > Setup > Advance holders > Advance holder groups.</span></span>
2. <span data-ttu-id="52b73-131">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="52b73-131">Click New.</span></span>
3. <span data-ttu-id="52b73-132">Érték beírása a Csoport mezőbe.</span><span class="sxs-lookup"><span data-stu-id="52b73-132">In the Group field, type a value.</span></span>
4. <span data-ttu-id="52b73-133">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="52b73-133">In the Description field, type a value.</span></span>
5. <span data-ttu-id="52b73-134">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="52b73-134">Click Save.</span></span>

## <a name="create-an-employee-posting-profile"></a><span data-ttu-id="52b73-135">Alkalmazott feladási sablonjának létrehozása</span><span class="sxs-lookup"><span data-stu-id="52b73-135">Create an employee posting profile</span></span>
1. <span data-ttu-id="52b73-136">Ugrás a Kötelezettségek > Beállítás > Előlegre jogosultak > Alkalmazott feladási sablonjai elemre.</span><span class="sxs-lookup"><span data-stu-id="52b73-136">Go to Accounts payable > Setup > Advance holders > Employee posting profiles.</span></span>
2. <span data-ttu-id="52b73-137">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="52b73-137">Click New.</span></span>
3. <span data-ttu-id="52b73-138">Írjon egy értéket a Feladási profil mezőbe.</span><span class="sxs-lookup"><span data-stu-id="52b73-138">In the Posting profile field, type a value.</span></span>
4. <span data-ttu-id="52b73-139">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="52b73-139">In the Description field, type a value.</span></span>
5. <span data-ttu-id="52b73-140">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="52b73-140">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="52b73-141">Az Érvényes mezőben válasszon ki egy lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="52b73-141">In the Valid for field, select an option.</span></span>
7. <span data-ttu-id="52b73-142">Az Összegzett számla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="52b73-142">In the Summary account field, specify the desired values.</span></span>
8. <span data-ttu-id="52b73-143">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="52b73-143">Click Save.</span></span>

## <a name="set-up-advance-holder-parameters"></a><span data-ttu-id="52b73-144">Előlegre jogosultak paramétereinek beállítása</span><span class="sxs-lookup"><span data-stu-id="52b73-144">Set up advance holder parameters</span></span>
1. <span data-ttu-id="52b73-145">Ugorjon a Kötelezettségek > Beállítás > Kötelezettségek paraméterei pontra.</span><span class="sxs-lookup"><span data-stu-id="52b73-145">Go to Accounts payable > Setup > Accounts payable parameters.</span></span>
2. <span data-ttu-id="52b73-146">Kattintson az Előlegre jogosultak fülre.</span><span class="sxs-lookup"><span data-stu-id="52b73-146">Click the Advance holders tab.</span></span>
3. <span data-ttu-id="52b73-147">A Feladási profil mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="52b73-147">In the Posting profile field, enter or select a value.</span></span>
4. <span data-ttu-id="52b73-148">A Név mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="52b73-148">In the Name field, enter or select a value.</span></span>
5. <span data-ttu-id="52b73-149">A Készpénz mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="52b73-149">In the Cash field, enter or select a value.</span></span>
6. <span data-ttu-id="52b73-150">A Név mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="52b73-150">In the Name field, enter or select a value.</span></span>
7. <span data-ttu-id="52b73-151">Válasszon egy lehetőséget a Számla típusa mezőben.</span><span class="sxs-lookup"><span data-stu-id="52b73-151">In the Account type field, select an option.</span></span>
8. <span data-ttu-id="52b73-152">A Fő számla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="52b73-152">In the Main account field, specify the desired values.</span></span>
9. <span data-ttu-id="52b73-153">Kattintson a Számsorozatok lapra.</span><span class="sxs-lookup"><span data-stu-id="52b73-153">Click the Number sequences tab.</span></span>
10. <span data-ttu-id="52b73-154">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="52b73-154">Click Save.</span></span>

## <a name="set-up-a-cash-posting-profile"></a><span data-ttu-id="52b73-155">Állítson be egy készpénzfeladási profilt</span><span class="sxs-lookup"><span data-stu-id="52b73-155">Set up a cash posting profile</span></span>
1. <span data-ttu-id="52b73-156">Nyissa meg a következőt: Készpénz- és bankkezelés > Beállítás > Készpénzfeladási sablonok.</span><span class="sxs-lookup"><span data-stu-id="52b73-156">Go to Cash and bank management > Setup > Cash posting profiles.</span></span>
2. <span data-ttu-id="52b73-157">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="52b73-157">Click New.</span></span>
3. <span data-ttu-id="52b73-158">A Készpénzfeladás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="52b73-158">In the Cash posting field, type a value.</span></span>
4. <span data-ttu-id="52b73-159">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="52b73-159">In the Description field, type a value.</span></span>
5. <span data-ttu-id="52b73-160">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="52b73-160">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="52b73-161">Az Érvényes mezőben válasszon ki egy lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="52b73-161">In the Valid for field, select an option.</span></span>
7. <span data-ttu-id="52b73-162">A Fő számla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="52b73-162">In the Main account field, specify the desired values.</span></span>
8. <span data-ttu-id="52b73-163">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="52b73-163">Click Save.</span></span>

## <a name="set-up-cash-and-bank-parameters"></a><span data-ttu-id="52b73-164">Készpénz- és bankparaméterek beállítása</span><span class="sxs-lookup"><span data-stu-id="52b73-164">Set up cash and bank parameters</span></span>
1. <span data-ttu-id="52b73-165">Ugorjon a Készpénz- és bankkezelés > Beállítás > Készpénz- és bankkezelési paraméterek pontra.</span><span class="sxs-lookup"><span data-stu-id="52b73-165">Go to Cash and bank management > Setup > Cash and bank management parameters.</span></span>
2. <span data-ttu-id="52b73-166">Kattintson a Készpénz lapra.</span><span class="sxs-lookup"><span data-stu-id="52b73-166">Click the Cash tab.</span></span>
3. <span data-ttu-id="52b73-167">A Készpénz mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="52b73-167">In the Cash field, enter or select a value.</span></span>
4. <span data-ttu-id="52b73-168">A Készpénzfeladás mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="52b73-168">In the Cash posting field, enter or select a value.</span></span>
5. <span data-ttu-id="52b73-169">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="52b73-169">Click Save.</span></span>
6. <span data-ttu-id="52b73-170">Kattintson a Számsorozatok lapra.</span><span class="sxs-lookup"><span data-stu-id="52b73-170">Click the Number sequences tab.</span></span>
7. <span data-ttu-id="52b73-171">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="52b73-171">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="52b73-172">A Számsorrend kódja mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="52b73-172">In the Number sequence code field, enter or select a value.</span></span>
9. <span data-ttu-id="52b73-173">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="52b73-173">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="52b73-174">A Számsorrend kódja mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="52b73-174">In the Number sequence code field, enter or select a value.</span></span>
11. <span data-ttu-id="52b73-175">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="52b73-175">Click Save.</span></span>

## <a name="set-up-terms-of-payment"></a><span data-ttu-id="52b73-176">Fizetési feltételek beállítása</span><span class="sxs-lookup"><span data-stu-id="52b73-176">Set up terms of payment</span></span>
1. <span data-ttu-id="52b73-177">Ugrás a Kötelezettségek > Kifizetés beállítása > Fizetési feltételek elemre.</span><span class="sxs-lookup"><span data-stu-id="52b73-177">Go to Accounts payable > Payment setup > Terms of payment.</span></span>
2. <span data-ttu-id="52b73-178">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="52b73-178">Click Edit.</span></span>
3. <span data-ttu-id="52b73-179">A Kezdő előlegre jogosult mezőben válassza az Igen lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="52b73-179">Select Yes in the From advance holder field.</span></span>
4. <span data-ttu-id="52b73-180">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="52b73-180">Click Save.</span></span>

## <a name="create-a-new-worker"></a><span data-ttu-id="52b73-181">Új dolgozó létrehozása</span><span class="sxs-lookup"><span data-stu-id="52b73-181">Create a new worker</span></span>
1. <span data-ttu-id="52b73-182">Ugrás az Emberi erőforrások > Dolgozók > Dolgozók elemre.</span><span class="sxs-lookup"><span data-stu-id="52b73-182">Go to Human resources > Workers > Workers.</span></span>
2. <span data-ttu-id="52b73-183">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="52b73-183">Click New.</span></span>
3. <span data-ttu-id="52b73-184">Az Utónév mezőbe írjon be egy értéket.</span><span class="sxs-lookup"><span data-stu-id="52b73-184">In the First name field, type a value.</span></span>
4. <span data-ttu-id="52b73-185">A Vezetéknéve mezőbe írjon be egy értéket.</span><span class="sxs-lookup"><span data-stu-id="52b73-185">In the Last name field, type a value.</span></span>
5. <span data-ttu-id="52b73-186">Adjon meg egy értéket a Dolgozó azonosítója mezőben.</span><span class="sxs-lookup"><span data-stu-id="52b73-186">In the Worker ID field, type a value.</span></span>
6. <span data-ttu-id="52b73-187">Kattintson az Új dolgozó felvételére.</span><span class="sxs-lookup"><span data-stu-id="52b73-187">Click Hire new worker.</span></span>
7. <span data-ttu-id="52b73-188">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="52b73-188">Click Save.</span></span>

## <a name="set-up-a-worker-as-an-advance-holder"></a><span data-ttu-id="52b73-189">Dolgozó beállítása előlegre jogosultként</span><span class="sxs-lookup"><span data-stu-id="52b73-189">Set up a worker as an advance holder</span></span>
1. <span data-ttu-id="52b73-190">Ugrás a Kötelezettségek > Előlegre jogosultak > Előlegre jogosultak elemre.</span><span class="sxs-lookup"><span data-stu-id="52b73-190">Go to Accounts payable > Advance holders > Advance holders.</span></span>
2. <span data-ttu-id="52b73-191">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="52b73-191">Click Edit.</span></span>
3. <span data-ttu-id="52b73-192">A Csoport mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="52b73-192">In the Group field, enter or select a value.</span></span>
4. <span data-ttu-id="52b73-193">Az Előlegre jogosult mezőben válassza az Igen lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="52b73-193">Select Yes in the Advance holder field.</span></span>
5. <span data-ttu-id="52b73-194">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="52b73-194">Click Save.</span></span>

## <a name="create-and-post-a-purchase-order-invoice"></a><span data-ttu-id="52b73-195">Beszerzési rendelés számlájának létrehozása és feladása</span><span class="sxs-lookup"><span data-stu-id="52b73-195">Create and post a purchase order invoice</span></span>
1. <span data-ttu-id="52b73-196">Nyissa meg a következőt: Kötelezettségek > Beszerzési rendelések > Minden beszerzési rendelés.</span><span class="sxs-lookup"><span data-stu-id="52b73-196">Go to Accounts payable > Purchase orders > All purchase orders.</span></span>
2. <span data-ttu-id="52b73-197">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="52b73-197">Click New.</span></span>
3. <span data-ttu-id="52b73-198">A Szállítószámla mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="52b73-198">In the Vendor account field, enter or select a value.</span></span>
4. <span data-ttu-id="52b73-199">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="52b73-199">Click OK.</span></span>
5. <span data-ttu-id="52b73-200">A Sorok vagy fejléc mezőben válasszon egy lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="52b73-200">In the Lines or header field, select an option.</span></span>
6. <span data-ttu-id="52b73-201">Bontsa ki az Ár és engedmény szakaszt.</span><span class="sxs-lookup"><span data-stu-id="52b73-201">Expand the Price and discount section.</span></span>
7. <span data-ttu-id="52b73-202">Adjon meg vagy válasszon ki egy értéket a Fizetési feltételek mezőben.</span><span class="sxs-lookup"><span data-stu-id="52b73-202">In the Terms of payment field, enter or select a value.</span></span>
8. <span data-ttu-id="52b73-203">Az Előlegre jogosult mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="52b73-203">In the Advance holder field, enter or select a value.</span></span>
9. <span data-ttu-id="52b73-204">A Sorok vagy fejléc mezőben válasszon egy lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="52b73-204">In the Lines or header field, select an option.</span></span>
10. <span data-ttu-id="52b73-205">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="52b73-205">In the list, mark the selected row.</span></span>
11. <span data-ttu-id="52b73-206">Az Elemszám mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="52b73-206">In the Item number field, enter or select a value.</span></span>
12. <span data-ttu-id="52b73-207">Adjon meg egy számot a Mennyiség mezőben.</span><span class="sxs-lookup"><span data-stu-id="52b73-207">In the Quantity field, enter a number.</span></span>
13. <span data-ttu-id="52b73-208">Adjon meg egy számot az Egységár mezőben.</span><span class="sxs-lookup"><span data-stu-id="52b73-208">In the Unit price field, enter a number.</span></span>
14. <span data-ttu-id="52b73-209">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="52b73-209">Click Save.</span></span>
15. <span data-ttu-id="52b73-210">A Művelet panelen kattintson a Beszerzés elemre.</span><span class="sxs-lookup"><span data-stu-id="52b73-210">On the Action Pane, click Purchase.</span></span>
16. <span data-ttu-id="52b73-211">Kattintson a Megerősítés gombra.</span><span class="sxs-lookup"><span data-stu-id="52b73-211">Click Confirm.</span></span>
17. <span data-ttu-id="52b73-212">A Művelet panelen kattintson a Számla lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="52b73-212">On the Action Pane, click Invoice.</span></span>
18. <span data-ttu-id="52b73-213">Kattintson a Számla lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="52b73-213">Click Invoice.</span></span>
19. <span data-ttu-id="52b73-214">Kattintson az Alapértelmezett forrás: Termék érkező mennyisége lehetőségre a legördülő párbeszédablak megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="52b73-214">Click Default from: Product receipt quantity to open the drop dialog.</span></span>
20. <span data-ttu-id="52b73-215">Egy lehetőség kiválasztása a Sorok alapértelmezett mennyisége mezőben.</span><span class="sxs-lookup"><span data-stu-id="52b73-215">In the Default quantity for lines field, select an option.</span></span>
21. <span data-ttu-id="52b73-216">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="52b73-216">Click OK.</span></span>
22. <span data-ttu-id="52b73-217">Érték beírása a Szám mezőbe.</span><span class="sxs-lookup"><span data-stu-id="52b73-217">In the Number field, type a value.</span></span>
23. <span data-ttu-id="52b73-218">A Számla leírása mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="52b73-218">In the Invoice description field, type a value.</span></span>
24. <span data-ttu-id="52b73-219">Adjon meg egy dátumot a Számla dátuma mezőben.</span><span class="sxs-lookup"><span data-stu-id="52b73-219">In the Invoice date field, enter a date.</span></span>
25. <span data-ttu-id="52b73-220">Az Áfatételjegyzék dátuma mezőbe írjon be egy dátumot.</span><span class="sxs-lookup"><span data-stu-id="52b73-220">In the Date of VAT register field, enter a date.</span></span>
26. <span data-ttu-id="52b73-221">Adjon meg egy dátumot a Beérkezési dokumentum dátuma mezőben.</span><span class="sxs-lookup"><span data-stu-id="52b73-221">In the Receive document date field, enter a date.</span></span>
27. <span data-ttu-id="52b73-222">Kattintson a Feladás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="52b73-222">Click Post.</span></span>

## <a name="balance-and-close-advance-holders-transactions"></a><span data-ttu-id="52b73-223">Előlegre jogosultak tranzakcióinak egyenlegének elkészítése és zárása</span><span class="sxs-lookup"><span data-stu-id="52b73-223">Balance and close advance holders transactions</span></span>
1. <span data-ttu-id="52b73-224">Ugrás a Kötelezettségek > Előlegre jogosultak > Előlegre jogosultak elemre.</span><span class="sxs-lookup"><span data-stu-id="52b73-224">Go to Accounts payable > Advance holders > Advance holders.</span></span>
2. <span data-ttu-id="52b73-225">Kattintson a Tranzakciók elemre.</span><span class="sxs-lookup"><span data-stu-id="52b73-225">Click Transactions.</span></span>
3. <span data-ttu-id="52b73-226">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="52b73-226">Close the page.</span></span>
4. <span data-ttu-id="52b73-227">Kattintson az Egyenleg lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="52b73-227">Click Balance.</span></span>
5. <span data-ttu-id="52b73-228">Kattintson a Zárás bankon keresztül lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="52b73-228">Click Close via bank.</span></span>
6. <span data-ttu-id="52b73-229">Válassza ki az Igen lehetőséget az Automatikus mezőben.</span><span class="sxs-lookup"><span data-stu-id="52b73-229">Select Yes in the Automatic field.</span></span>
7. <span data-ttu-id="52b73-230">Az Átutalandó összeg mezőben.</span><span class="sxs-lookup"><span data-stu-id="52b73-230">In the Amount to be transferred.</span></span> <span data-ttu-id="52b73-231">mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="52b73-231">field, enter a number.</span></span>
8. <span data-ttu-id="52b73-232">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="52b73-232">Click OK.</span></span>
9. <span data-ttu-id="52b73-233">Kattintson a Zárás készpénzen keresztül lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="52b73-233">Click Close via cash.</span></span>
10. <span data-ttu-id="52b73-234">Válassza ki az Igen lehetőséget az Automatikus mezőben.</span><span class="sxs-lookup"><span data-stu-id="52b73-234">Select Yes in the Automatic field.</span></span>
11. <span data-ttu-id="52b73-235">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="52b73-235">Click OK.</span></span>
12. <span data-ttu-id="52b73-236">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="52b73-236">Close the page.</span></span>
13. <span data-ttu-id="52b73-237">Kattintson a Tranzakciók elemre.</span><span class="sxs-lookup"><span data-stu-id="52b73-237">Click Transactions.</span></span>

