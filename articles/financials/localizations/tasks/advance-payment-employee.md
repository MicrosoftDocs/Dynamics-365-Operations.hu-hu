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
ms.openlocfilehash: e3c07789bfa0839436caf32e428f3abeecb8f2b7
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "370895"
---
# <a name="eeu-00047-advance-payment-to-employee"></a><span data-ttu-id="ab926-103">EEU-00047 Előlegfizetés alkalmazottnak</span><span class="sxs-lookup"><span data-stu-id="ab926-103">EEU-00047 Advance payment to employee</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ab926-104">Ez az eljárás bemutatja, hogyan lehet tranzakciókat beállítani és regisztrálni egy előlegre jogosult számára.</span><span class="sxs-lookup"><span data-stu-id="ab926-104">This procedure demonstrates how to set up and register transactions for an advance holder.</span></span> <span data-ttu-id="ab926-105">Ezt a eljárást a DEMF bemutatócéget használva hozták létre, az elsődleges címéhez tartozó ország pedig Litvánia.</span><span class="sxs-lookup"><span data-stu-id="ab926-105">This procedure was created using the demo data company DEMF with a primary address in Lithuania.</span></span> <span data-ttu-id="ab926-106">Ez a feladat csak az olyan jogi személyek esetében működik, amelyekben Lengyelországban, Litvániában, Lettországban, Észtországban, Csehországban vagy Magyarországon van az elsődleges címe.</span><span class="sxs-lookup"><span data-stu-id="ab926-106">This task only works for legal entities with a primary address in Poland, Lithuania, Latvia, Estonia, Czech Republic, or Hungary.</span></span> <span data-ttu-id="ab926-107">Az eljárás egy olyan szolgáltatáshoz tartozik, amely a Dynamics 365 for Operations 1611-es verziójában jelent meg.</span><span class="sxs-lookup"><span data-stu-id="ab926-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="create-a-new-cash-account"></a><span data-ttu-id="ab926-108">Új készpénzszámla létrehozása</span><span class="sxs-lookup"><span data-stu-id="ab926-108">Create a new cash account</span></span>
1. <span data-ttu-id="ab926-109">Nyissa meg a következőt: Készpénz- és bankkezelés > Bankszámlák > Készpénzszámlák.</span><span class="sxs-lookup"><span data-stu-id="ab926-109">Go to Cash and bank management > Bank accounts > Cash accounts.</span></span>
2. <span data-ttu-id="ab926-110">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="ab926-110">Click New.</span></span>
3. <span data-ttu-id="ab926-111">A Készpénz mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="ab926-111">In the Cash field, type a value.</span></span>
4. <span data-ttu-id="ab926-112">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="ab926-112">In the Name field, type a value.</span></span>
5. <span data-ttu-id="ab926-113">A Számsorozatcsoport mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="ab926-113">In the Number sequence group field, enter or select a value.</span></span>
6. <span data-ttu-id="ab926-114">Bontsa ki az Ellenőrzés szakaszt.</span><span class="sxs-lookup"><span data-stu-id="ab926-114">Expand the Validation section.</span></span>
7. <span data-ttu-id="ab926-115">A Pénznem mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="ab926-115">In the Currency field, enter or select a value.</span></span>
8. <span data-ttu-id="ab926-116">Válassza az Igen lehetőséget a Negatív készpénz mezőben.</span><span class="sxs-lookup"><span data-stu-id="ab926-116">Select Yes in the Negative cash field.</span></span>
9. <span data-ttu-id="ab926-117">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="ab926-117">Click Save.</span></span>

## <a name="create-a-new-journal"></a><span data-ttu-id="ab926-118">Új napló létrehozása</span><span class="sxs-lookup"><span data-stu-id="ab926-118">Create a new journal</span></span>
1. <span data-ttu-id="ab926-119">Ugorjon a Főkönyv > Naplóbeállítások > Naplónevek pontra.</span><span class="sxs-lookup"><span data-stu-id="ab926-119">Go to General ledger > Journal setup > Journal names.</span></span>
2. <span data-ttu-id="ab926-120">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="ab926-120">Click New.</span></span>
3. <span data-ttu-id="ab926-121">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="ab926-121">In the Name field, type a value.</span></span>
4. <span data-ttu-id="ab926-122">A Bizonylatsorozat mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="ab926-122">In the Voucher series field, enter or select a value.</span></span>
5. <span data-ttu-id="ab926-123">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="ab926-123">Click Save.</span></span>
6. <span data-ttu-id="ab926-124">Kattintson az Új elemre.</span><span class="sxs-lookup"><span data-stu-id="ab926-124">Click New.</span></span>
7. <span data-ttu-id="ab926-125">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="ab926-125">In the Name field, type a value.</span></span>
8. <span data-ttu-id="ab926-126">A Napló típusa mezőben válasszon ki egy lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ab926-126">In the Journal type field, select an option.</span></span>
9. <span data-ttu-id="ab926-127">A Bizonylatsorozat mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="ab926-127">In the Voucher series field, enter or select a value.</span></span>
10. <span data-ttu-id="ab926-128">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="ab926-128">Click Save.</span></span>

## <a name="create-an-advance-holder-group"></a><span data-ttu-id="ab926-129">Előlegre jogosult csoport létrehozása</span><span class="sxs-lookup"><span data-stu-id="ab926-129">Create an advance holder group</span></span>
1. <span data-ttu-id="ab926-130">Ugrás a Kötelezettségek > Beállítás > Előlegre jogosultak > Előlegre jogosult csoportok elemre.</span><span class="sxs-lookup"><span data-stu-id="ab926-130">Go to Accounts payable > Setup > Advance holders > Advance holder groups.</span></span>
2. <span data-ttu-id="ab926-131">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="ab926-131">Click New.</span></span>
3. <span data-ttu-id="ab926-132">Érték beírása a Csoport mezőbe.</span><span class="sxs-lookup"><span data-stu-id="ab926-132">In the Group field, type a value.</span></span>
4. <span data-ttu-id="ab926-133">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="ab926-133">In the Description field, type a value.</span></span>
5. <span data-ttu-id="ab926-134">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="ab926-134">Click Save.</span></span>

## <a name="create-an-employee-posting-profile"></a><span data-ttu-id="ab926-135">Alkalmazott feladási sablonjának létrehozása</span><span class="sxs-lookup"><span data-stu-id="ab926-135">Create an employee posting profile</span></span>
1. <span data-ttu-id="ab926-136">Ugrás a Kötelezettségek > Beállítás > Előlegre jogosultak > Alkalmazott feladási sablonjai elemre.</span><span class="sxs-lookup"><span data-stu-id="ab926-136">Go to Accounts payable > Setup > Advance holders > Employee posting profiles.</span></span>
2. <span data-ttu-id="ab926-137">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="ab926-137">Click New.</span></span>
3. <span data-ttu-id="ab926-138">Írjon egy értéket a Feladási profil mezőbe.</span><span class="sxs-lookup"><span data-stu-id="ab926-138">In the Posting profile field, type a value.</span></span>
4. <span data-ttu-id="ab926-139">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="ab926-139">In the Description field, type a value.</span></span>
5. <span data-ttu-id="ab926-140">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="ab926-140">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="ab926-141">Az Érvényes mezőben válasszon ki egy lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ab926-141">In the Valid for field, select an option.</span></span>
7. <span data-ttu-id="ab926-142">Az Összegzett számla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="ab926-142">In the Summary account field, specify the desired values.</span></span>
8. <span data-ttu-id="ab926-143">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="ab926-143">Click Save.</span></span>

## <a name="set-up-advance-holder-parameters"></a><span data-ttu-id="ab926-144">Előlegre jogosultak paramétereinek beállítása</span><span class="sxs-lookup"><span data-stu-id="ab926-144">Set up advance holder parameters</span></span>
1. <span data-ttu-id="ab926-145">Ugorjon a Kötelezettségek > Beállítás > Kötelezettségek paraméterei pontra.</span><span class="sxs-lookup"><span data-stu-id="ab926-145">Go to Accounts payable > Setup > Accounts payable parameters.</span></span>
2. <span data-ttu-id="ab926-146">Kattintson az Előlegre jogosultak fülre.</span><span class="sxs-lookup"><span data-stu-id="ab926-146">Click the Advance holders tab.</span></span>
3. <span data-ttu-id="ab926-147">A Feladási profil mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="ab926-147">In the Posting profile field, enter or select a value.</span></span>
4. <span data-ttu-id="ab926-148">A Név mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="ab926-148">In the Name field, enter or select a value.</span></span>
5. <span data-ttu-id="ab926-149">A Készpénz mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="ab926-149">In the Cash field, enter or select a value.</span></span>
6. <span data-ttu-id="ab926-150">A Név mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="ab926-150">In the Name field, enter or select a value.</span></span>
7. <span data-ttu-id="ab926-151">Válasszon egy lehetőséget a Számla típusa mezőben.</span><span class="sxs-lookup"><span data-stu-id="ab926-151">In the Account type field, select an option.</span></span>
8. <span data-ttu-id="ab926-152">A Fő számla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="ab926-152">In the Main account field, specify the desired values.</span></span>
9. <span data-ttu-id="ab926-153">Kattintson a Számsorozatok lapra.</span><span class="sxs-lookup"><span data-stu-id="ab926-153">Click the Number sequences tab.</span></span>
10. <span data-ttu-id="ab926-154">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="ab926-154">Click Save.</span></span>

## <a name="set-up-a-cash-posting-profile"></a><span data-ttu-id="ab926-155">Állítson be egy készpénzfeladási profilt</span><span class="sxs-lookup"><span data-stu-id="ab926-155">Set up a cash posting profile</span></span>
1. <span data-ttu-id="ab926-156">Nyissa meg a következőt: Készpénz- és bankkezelés > Beállítás > Készpénzfeladási sablonok.</span><span class="sxs-lookup"><span data-stu-id="ab926-156">Go to Cash and bank management > Setup > Cash posting profiles.</span></span>
2. <span data-ttu-id="ab926-157">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="ab926-157">Click New.</span></span>
3. <span data-ttu-id="ab926-158">A Készpénzfeladás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="ab926-158">In the Cash posting field, type a value.</span></span>
4. <span data-ttu-id="ab926-159">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="ab926-159">In the Description field, type a value.</span></span>
5. <span data-ttu-id="ab926-160">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="ab926-160">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="ab926-161">Az Érvényes mezőben válasszon ki egy lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ab926-161">In the Valid for field, select an option.</span></span>
7. <span data-ttu-id="ab926-162">A Fő számla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="ab926-162">In the Main account field, specify the desired values.</span></span>
8. <span data-ttu-id="ab926-163">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="ab926-163">Click Save.</span></span>

## <a name="set-up-cash-and-bank-parameters"></a><span data-ttu-id="ab926-164">Készpénz- és bankparaméterek beállítása</span><span class="sxs-lookup"><span data-stu-id="ab926-164">Set up cash and bank parameters</span></span>
1. <span data-ttu-id="ab926-165">Ugorjon a Készpénz- és bankkezelés > Beállítás > Készpénz- és bankkezelési paraméterek pontra.</span><span class="sxs-lookup"><span data-stu-id="ab926-165">Go to Cash and bank management > Setup > Cash and bank management parameters.</span></span>
2. <span data-ttu-id="ab926-166">Kattintson a Készpénz lapra.</span><span class="sxs-lookup"><span data-stu-id="ab926-166">Click the Cash tab.</span></span>
3. <span data-ttu-id="ab926-167">A Készpénz mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="ab926-167">In the Cash field, enter or select a value.</span></span>
4. <span data-ttu-id="ab926-168">A Készpénzfeladás mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="ab926-168">In the Cash posting field, enter or select a value.</span></span>
5. <span data-ttu-id="ab926-169">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="ab926-169">Click Save.</span></span>
6. <span data-ttu-id="ab926-170">Kattintson a Számsorozatok lapra.</span><span class="sxs-lookup"><span data-stu-id="ab926-170">Click the Number sequences tab.</span></span>
7. <span data-ttu-id="ab926-171">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="ab926-171">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="ab926-172">A Számsorrend kódja mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="ab926-172">In the Number sequence code field, enter or select a value.</span></span>
9. <span data-ttu-id="ab926-173">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="ab926-173">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="ab926-174">A Számsorrend kódja mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="ab926-174">In the Number sequence code field, enter or select a value.</span></span>
11. <span data-ttu-id="ab926-175">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="ab926-175">Click Save.</span></span>

## <a name="set-up-terms-of-payment"></a><span data-ttu-id="ab926-176">Fizetési feltételek beállítása</span><span class="sxs-lookup"><span data-stu-id="ab926-176">Set up terms of payment</span></span>
1. <span data-ttu-id="ab926-177">Ugrás a Kötelezettségek > Kifizetés beállítása > Fizetési feltételek elemre.</span><span class="sxs-lookup"><span data-stu-id="ab926-177">Go to Accounts payable > Payment setup > Terms of payment.</span></span>
2. <span data-ttu-id="ab926-178">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="ab926-178">Click Edit.</span></span>
3. <span data-ttu-id="ab926-179">A Kezdő előlegre jogosult mezőben válassza az Igen lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ab926-179">Select Yes in the From advance holder field.</span></span>
4. <span data-ttu-id="ab926-180">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="ab926-180">Click Save.</span></span>

## <a name="create-a-new-worker"></a><span data-ttu-id="ab926-181">Új dolgozó létrehozása</span><span class="sxs-lookup"><span data-stu-id="ab926-181">Create a new worker</span></span>
1. <span data-ttu-id="ab926-182">Ugrás az Emberi erőforrások > Dolgozók > Dolgozók elemre.</span><span class="sxs-lookup"><span data-stu-id="ab926-182">Go to Human resources > Workers > Workers.</span></span>
2. <span data-ttu-id="ab926-183">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="ab926-183">Click New.</span></span>
3. <span data-ttu-id="ab926-184">Az Utónév mezőbe írjon be egy értéket.</span><span class="sxs-lookup"><span data-stu-id="ab926-184">In the First name field, type a value.</span></span>
4. <span data-ttu-id="ab926-185">A Vezetéknéve mezőbe írjon be egy értéket.</span><span class="sxs-lookup"><span data-stu-id="ab926-185">In the Last name field, type a value.</span></span>
5. <span data-ttu-id="ab926-186">Adjon meg egy értéket a Dolgozó azonosítója mezőben.</span><span class="sxs-lookup"><span data-stu-id="ab926-186">In the Worker ID field, type a value.</span></span>
6. <span data-ttu-id="ab926-187">Kattintson az Új dolgozó felvételére.</span><span class="sxs-lookup"><span data-stu-id="ab926-187">Click Hire new worker.</span></span>
7. <span data-ttu-id="ab926-188">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="ab926-188">Click Save.</span></span>

## <a name="set-up-a-worker-as-an-advance-holder"></a><span data-ttu-id="ab926-189">Dolgozó beállítása előlegre jogosultként</span><span class="sxs-lookup"><span data-stu-id="ab926-189">Set up a worker as an advance holder</span></span>
1. <span data-ttu-id="ab926-190">Ugrás a Kötelezettségek > Előlegre jogosultak > Előlegre jogosultak elemre.</span><span class="sxs-lookup"><span data-stu-id="ab926-190">Go to Accounts payable > Advance holders > Advance holders.</span></span>
2. <span data-ttu-id="ab926-191">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="ab926-191">Click Edit.</span></span>
3. <span data-ttu-id="ab926-192">A Csoport mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="ab926-192">In the Group field, enter or select a value.</span></span>
4. <span data-ttu-id="ab926-193">Az Előlegre jogosult mezőben válassza az Igen lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ab926-193">Select Yes in the Advance holder field.</span></span>
5. <span data-ttu-id="ab926-194">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="ab926-194">Click Save.</span></span>

## <a name="create-and-post-a-purchase-order-invoice"></a><span data-ttu-id="ab926-195">Beszerzési rendelés számlájának létrehozása és feladása</span><span class="sxs-lookup"><span data-stu-id="ab926-195">Create and post a purchase order invoice</span></span>
1. <span data-ttu-id="ab926-196">Nyissa meg a következőt: Kötelezettségek > Beszerzési rendelések > Minden beszerzési rendelés.</span><span class="sxs-lookup"><span data-stu-id="ab926-196">Go to Accounts payable > Purchase orders > All purchase orders.</span></span>
2. <span data-ttu-id="ab926-197">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="ab926-197">Click New.</span></span>
3. <span data-ttu-id="ab926-198">A Szállítószámla mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="ab926-198">In the Vendor account field, enter or select a value.</span></span>
4. <span data-ttu-id="ab926-199">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="ab926-199">Click OK.</span></span>
5. <span data-ttu-id="ab926-200">A Sorok vagy fejléc mezőben válasszon egy lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ab926-200">In the Lines or header field, select an option.</span></span>
6. <span data-ttu-id="ab926-201">Bontsa ki az Ár és engedmény szakaszt.</span><span class="sxs-lookup"><span data-stu-id="ab926-201">Expand the Price and discount section.</span></span>
7. <span data-ttu-id="ab926-202">Adjon meg vagy válasszon ki egy értéket a Fizetési feltételek mezőben.</span><span class="sxs-lookup"><span data-stu-id="ab926-202">In the Terms of payment field, enter or select a value.</span></span>
8. <span data-ttu-id="ab926-203">Az Előlegre jogosult mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="ab926-203">In the Advance holder field, enter or select a value.</span></span>
9. <span data-ttu-id="ab926-204">A Sorok vagy fejléc mezőben válasszon egy lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ab926-204">In the Lines or header field, select an option.</span></span>
10. <span data-ttu-id="ab926-205">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="ab926-205">In the list, mark the selected row.</span></span>
11. <span data-ttu-id="ab926-206">Az Elemszám mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="ab926-206">In the Item number field, enter or select a value.</span></span>
12. <span data-ttu-id="ab926-207">Adjon meg egy számot a Mennyiség mezőben.</span><span class="sxs-lookup"><span data-stu-id="ab926-207">In the Quantity field, enter a number.</span></span>
13. <span data-ttu-id="ab926-208">Adjon meg egy számot az Egységár mezőben.</span><span class="sxs-lookup"><span data-stu-id="ab926-208">In the Unit price field, enter a number.</span></span>
14. <span data-ttu-id="ab926-209">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="ab926-209">Click Save.</span></span>
15. <span data-ttu-id="ab926-210">A Művelet panelen kattintson a Beszerzés elemre.</span><span class="sxs-lookup"><span data-stu-id="ab926-210">On the Action Pane, click Purchase.</span></span>
16. <span data-ttu-id="ab926-211">Kattintson a Megerősítés gombra.</span><span class="sxs-lookup"><span data-stu-id="ab926-211">Click Confirm.</span></span>
17. <span data-ttu-id="ab926-212">A Művelet panelen kattintson a Számla lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="ab926-212">On the Action Pane, click Invoice.</span></span>
18. <span data-ttu-id="ab926-213">Kattintson a Számla lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="ab926-213">Click Invoice.</span></span>
19. <span data-ttu-id="ab926-214">Kattintson az Alapértelmezett forrás: Termék érkező mennyisége lehetőségre a legördülő párbeszédablak megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="ab926-214">Click Default from: Product receipt quantity to open the drop dialog.</span></span>
20. <span data-ttu-id="ab926-215">Egy lehetőség kiválasztása a Sorok alapértelmezett mennyisége mezőben.</span><span class="sxs-lookup"><span data-stu-id="ab926-215">In the Default quantity for lines field, select an option.</span></span>
21. <span data-ttu-id="ab926-216">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="ab926-216">Click OK.</span></span>
22. <span data-ttu-id="ab926-217">Érték beírása a Szám mezőbe.</span><span class="sxs-lookup"><span data-stu-id="ab926-217">In the Number field, type a value.</span></span>
23. <span data-ttu-id="ab926-218">A Számla leírása mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="ab926-218">In the Invoice description field, type a value.</span></span>
24. <span data-ttu-id="ab926-219">Adjon meg egy dátumot a Számla dátuma mezőben.</span><span class="sxs-lookup"><span data-stu-id="ab926-219">In the Invoice date field, enter a date.</span></span>
25. <span data-ttu-id="ab926-220">Az Áfatételjegyzék dátuma mezőbe írjon be egy dátumot.</span><span class="sxs-lookup"><span data-stu-id="ab926-220">In the Date of VAT register field, enter a date.</span></span>
26. <span data-ttu-id="ab926-221">Adjon meg egy dátumot a Beérkezési dokumentum dátuma mezőben.</span><span class="sxs-lookup"><span data-stu-id="ab926-221">In the Receive document date field, enter a date.</span></span>
27. <span data-ttu-id="ab926-222">Kattintson a Feladás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="ab926-222">Click Post.</span></span>

## <a name="balance-and-close-advance-holders-transactions"></a><span data-ttu-id="ab926-223">Előlegre jogosultak tranzakcióinak egyenlegének elkészítése és zárása</span><span class="sxs-lookup"><span data-stu-id="ab926-223">Balance and close advance holders transactions</span></span>
1. <span data-ttu-id="ab926-224">Ugrás a Kötelezettségek > Előlegre jogosultak > Előlegre jogosultak elemre.</span><span class="sxs-lookup"><span data-stu-id="ab926-224">Go to Accounts payable > Advance holders > Advance holders.</span></span>
2. <span data-ttu-id="ab926-225">Kattintson a Tranzakciók elemre.</span><span class="sxs-lookup"><span data-stu-id="ab926-225">Click Transactions.</span></span>
3. <span data-ttu-id="ab926-226">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="ab926-226">Close the page.</span></span>
4. <span data-ttu-id="ab926-227">Kattintson az Egyenleg lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="ab926-227">Click Balance.</span></span>
5. <span data-ttu-id="ab926-228">Kattintson a Zárás bankon keresztül lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="ab926-228">Click Close via bank.</span></span>
6. <span data-ttu-id="ab926-229">Válassza ki az Igen lehetőséget az Automatikus mezőben.</span><span class="sxs-lookup"><span data-stu-id="ab926-229">Select Yes in the Automatic field.</span></span>
7. <span data-ttu-id="ab926-230">Az Átutalandó összeg mezőben.</span><span class="sxs-lookup"><span data-stu-id="ab926-230">In the Amount to be transferred.</span></span> <span data-ttu-id="ab926-231">mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="ab926-231">field, enter a number.</span></span>
8. <span data-ttu-id="ab926-232">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="ab926-232">Click OK.</span></span>
9. <span data-ttu-id="ab926-233">Kattintson a Zárás készpénzen keresztül lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="ab926-233">Click Close via cash.</span></span>
10. <span data-ttu-id="ab926-234">Válassza ki az Igen lehetőséget az Automatikus mezőben.</span><span class="sxs-lookup"><span data-stu-id="ab926-234">Select Yes in the Automatic field.</span></span>
11. <span data-ttu-id="ab926-235">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="ab926-235">Click OK.</span></span>
12. <span data-ttu-id="ab926-236">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="ab926-236">Close the page.</span></span>
13. <span data-ttu-id="ab926-237">Kattintson a Tranzakciók elemre.</span><span class="sxs-lookup"><span data-stu-id="ab926-237">Click Transactions.</span></span>

