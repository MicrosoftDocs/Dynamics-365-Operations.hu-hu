---
title: Vevői előlegek
description: Ez a témakör elmagyarázza, hogyan lehet beállítani és feldolgozni az ügyfelek előlegeit (más néven vevői letéteket).
author: roschlom
ms.date: 04/30/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustPosting, LedgerJournalTransCustPaym, CustParameters
audience: Application User
ms.reviewer: ''
ms.search.scope: Core, Operations
ms.custom: 24651
ms.assetid: cb82245e-8c02-429c-b36e-8db0e3e6f7e5
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: ''
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c3314803b994aed40e5b04d8546a45bd305d48b6
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/11/2021
ms.locfileid: "6019420"
---
# <a name="customer-prepayments"></a><span data-ttu-id="1a0d7-103">Vevői előlegek</span><span class="sxs-lookup"><span data-stu-id="1a0d7-103">Customer prepayments</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1a0d7-104">A vevői előlegeket akkor használjuk, amikor egy ügyféltől befizetést kap, de nincs olyan számla, amellyel szemben a fizetés kiegyenlíthető.</span><span class="sxs-lookup"><span data-stu-id="1a0d7-104">Customer prepayments are used when you receive a payment from a customer, but there is no invoice that the payment can be settled against.</span></span> <span data-ttu-id="1a0d7-105">Az ilyen típusú kifizetéseket ügyfélletétnek is nevezik.</span><span class="sxs-lookup"><span data-stu-id="1a0d7-105">These types of payments are also referred to as customer deposits.</span></span>

<span data-ttu-id="1a0d7-106">Az ügyfél előlegek beállításának és feldolgozásának folyamata a következő alapvető lépésekből áll.</span><span class="sxs-lookup"><span data-stu-id="1a0d7-106">The process of setting up and working with customer prepayments consists of the following basic steps.</span></span>

1. <span data-ttu-id="1a0d7-107">Hozzon létre egy vevőfeladási profilt az előlegekhez.</span><span class="sxs-lookup"><span data-stu-id="1a0d7-107">Create a customer posting profile for prepayments.</span></span>
2. <span data-ttu-id="1a0d7-108">Állítsa be a **Feladási profil az előlegnapló-bizonylathoz** paramétert.</span><span class="sxs-lookup"><span data-stu-id="1a0d7-108">Set the **Posting profile with prepayment journal voucher** parameter.</span></span>
3. <span data-ttu-id="1a0d7-109">Hozzon létre egy vevői fizetési naplót, és jelölje be az **Előlegnapló-bizonylat** jelölőnégyzetet minden sorban.</span><span class="sxs-lookup"><span data-stu-id="1a0d7-109">Create a customer payment journal, and select the **Prepayment journal voucher** check box on each line.</span></span>
4. <span data-ttu-id="1a0d7-110">A vevői kifizetési napló feladása.</span><span class="sxs-lookup"><span data-stu-id="1a0d7-110">Post the customer payment journal.</span></span>
5. <span data-ttu-id="1a0d7-111">A számla kiállítása után egyenlítse ki vele az előleget a **Nyitott tranzakciók rendezése** lapon.</span><span class="sxs-lookup"><span data-stu-id="1a0d7-111">After an invoice is generated, settle the prepayment with it by using the **Settle open transactions** page.</span></span>

## <a name="create-a-customer-posting-profile-for-prepayments"></a><span data-ttu-id="1a0d7-112">Hozzon létre egy vevőfeladási profilt az előlegekhez</span><span class="sxs-lookup"><span data-stu-id="1a0d7-112">Create a customer posting profile for prepayments</span></span>

<span data-ttu-id="1a0d7-113">Általában, ha az áruk vagy szolgáltatások kiszállítása előtt, vagy a számla rendszerében számla kiállítása előtt fogad az ügyfelektől származó előlegeket vagy letéteket, akkor a készpénzt kötelezettségként kívánja rögzíteni, nem pedig eszközként a számlatükörben.</span><span class="sxs-lookup"><span data-stu-id="1a0d7-113">Typically, when you accept prepayments or deposits from your customers before goods or services are delivered, or before an invoice exists in your system, you will want to record the cash as a liability instead of an asset in your chart of accounts.</span></span> <span data-ttu-id="1a0d7-114">Ugyanakkor ezen összegek főkönyvben való rögzítésére vonatkozó követelmények azonban országtól vagy régiótól függően eltérőek lehetnek.</span><span class="sxs-lookup"><span data-stu-id="1a0d7-114">However, the requirements for recording these amounts in your general ledger might differ, depending on your country or region.</span></span> <span data-ttu-id="1a0d7-115">Ezért mindenképpen egyeztessen a könyvelőivel az alkalmazandó helyi szabályozásokról.</span><span class="sxs-lookup"><span data-stu-id="1a0d7-115">Therefore, be sure to consult your accountants about any local regulations that apply.</span></span>

<span data-ttu-id="1a0d7-116">Általánosságban elmondható, hogy az előrefizetésre használható feladási profil létrehozásának folyamata megegyezik az egyéb feladási profilok létrehozásának folyamatával.</span><span class="sxs-lookup"><span data-stu-id="1a0d7-116">In general, the process for creating a posting profile that can be used for prepayments is the same as the process for creating other posting profiles.</span></span> <span data-ttu-id="1a0d7-117">Az elsődleges különbség az **Összegzett számla** mezőben kiválasztott fő fiók.</span><span class="sxs-lookup"><span data-stu-id="1a0d7-117">The primary difference is the main account that you select in the **Summary account** field.</span></span> <span data-ttu-id="1a0d7-118">A további információkat lásd: [Vevői feladási profilok](customer-posting-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="1a0d7-118">For more information, see [Customer posting profiles](customer-posting-profiles.md).</span></span>

## <a name="define-parameters-for-customer-prepayments"></a><span data-ttu-id="1a0d7-119">Vevői előlegek paramétereinek meghatározása</span><span class="sxs-lookup"><span data-stu-id="1a0d7-119">Define parameters for customer prepayments</span></span>

<span data-ttu-id="1a0d7-120">Két fő kintlévőség-paramétert kell figyelembe vennie, amikor konfigurálja a rendszert az ügyfelek előlegeihez.</span><span class="sxs-lookup"><span data-stu-id="1a0d7-120">There are two main Accounts receivable parameters that you must consider when you configure the system for customer prepayments.</span></span> <span data-ttu-id="1a0d7-121">Tegye a következőket a paraméterek konfigurálásához.</span><span class="sxs-lookup"><span data-stu-id="1a0d7-121">Follow these steps to configure the parameters.</span></span>

1. <span data-ttu-id="1a0d7-122">Lépjen a **Kinnlevőségek \> Beállítások \> Kinnlevőségek paraméterei** pontra.</span><span class="sxs-lookup"><span data-stu-id="1a0d7-122">Go to **Accounts receivable \> Setup \> Accounts receivable parameters**.</span></span>
2. <span data-ttu-id="1a0d7-123">Nem kötelező: A **Főkönyv és áfa** lapon, a **Fizetés** gyorslapon lapon állítsa be az **Áfa az előlegnapló-bizonylaton** beállítást **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="1a0d7-123">Optional: On the **Ledger and sales tax** tab, on the **Payment** FastTab, set the **Sales tax on prepayment journal voucher** option to **Yes**.</span></span>
3. <span data-ttu-id="1a0d7-124">A **Feladási profil az előlegnapló-bizonylathoz** mezőben válassza ki azt az ügyfél-feladási profilt, amelyet az ügyfélelőlegek közzétételekor használni szeretne.</span><span class="sxs-lookup"><span data-stu-id="1a0d7-124">In the **Posting profile with prepayment journal voucher** field, select the customer posting profile to use when customer prepayments are posted.</span></span>
4. <span data-ttu-id="1a0d7-125">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="1a0d7-125">Close the page.</span></span>

## <a name="create-customer-prepayment-vouchers"></a><span data-ttu-id="1a0d7-126">Vevői előlegbizonylatok létrehozása</span><span class="sxs-lookup"><span data-stu-id="1a0d7-126">Create customer prepayment vouchers</span></span>

<span data-ttu-id="1a0d7-127">Amikor létrehozza az ügyfél fizetési naplót, minden előleghez be kell állítania az **Előlegnapló-bizonylat** lehetőséget **Igen** értékre a **Vevő kifizetési naplója** oldalon.</span><span class="sxs-lookup"><span data-stu-id="1a0d7-127">When you create the customer payment journal, for every prepayment, you must set the **Prepayment journal voucher** option to **Yes** on the **Customer payment journal** page.</span></span> <span data-ttu-id="1a0d7-128">Vevői előleg létrehozásához tegye a következőket.</span><span class="sxs-lookup"><span data-stu-id="1a0d7-128">Follow these steps to create a customer prepayment.</span></span>

1. <span data-ttu-id="1a0d7-129">Válassza a **Kinnlevőségek \> Kifizetések \> Kifizetési napló** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1a0d7-129">Go to **Accounts receivable \> Payments \> Customer payment journal**.</span></span>
2. <span data-ttu-id="1a0d7-130">Válassza az **Új** lehetőséget egy napló létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="1a0d7-130">Select **New** to create a journal.</span></span>
3. <span data-ttu-id="1a0d7-131">A **Név** mezőben válassza ki a használandó napló nevét.</span><span class="sxs-lookup"><span data-stu-id="1a0d7-131">In the **Name** field, select the journal name to use.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="1a0d7-132">Ha az előző eljárásban az **Áfa az előlegnapló-bizonylaton** lehetőséget **Igen** értékre állította be, akkor ki kell választania egy naplónevet, ahol az **Összeg tartalmazza az áfát** paraméter ki van választva.</span><span class="sxs-lookup"><span data-stu-id="1a0d7-132">If you set the **Sales tax on prepayment journal voucher** option to **Yes** in the previous procedure, you must select a journal name where the **Amount includes sales tax** parameter is selected.</span></span> 

4. <span data-ttu-id="1a0d7-133">Opcionális: A **Leírás** mezőbe írja be a részletes leírást.</span><span class="sxs-lookup"><span data-stu-id="1a0d7-133">Optional: In the **Description** field, enter a detailed description.</span></span>
5. <span data-ttu-id="1a0d7-134">**Sorok** kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="1a0d7-134">Select **Lines**.</span></span>
6. <span data-ttu-id="1a0d7-135">Ha üres sor nem létezik, válassza az **Új** lehetőséget egy sor létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="1a0d7-135">If a blank line doesn't exist, select **New** to create a line.</span></span>
7. <span data-ttu-id="1a0d7-136">A **Dátum** mezőben adja meg azt a dátumot, amikor az előleget könyvelni kell.</span><span class="sxs-lookup"><span data-stu-id="1a0d7-136">In the **Date** field, enter the date when the prepayment should be posted.</span></span>
8. <span data-ttu-id="1a0d7-137">A **Számla** mezőben válassza ki a vevőt az előleghez.</span><span class="sxs-lookup"><span data-stu-id="1a0d7-137">In the **Account** field, select the customer for the prepayment.</span></span>
9. <span data-ttu-id="1a0d7-138">Opcionális: A **Leírás** mezőbe írja be a tranzakció részletes leírását.</span><span class="sxs-lookup"><span data-stu-id="1a0d7-138">Optional: In the **Description** field, enter a detailed description of the transaction.</span></span>
10. <span data-ttu-id="1a0d7-139">A **Jóváírás** mezőbe írja be az előleg összegét.</span><span class="sxs-lookup"><span data-stu-id="1a0d7-139">In the **Credit** field, enter the amount of the prepayment.</span></span>
11. <span data-ttu-id="1a0d7-140">Az **Ellenszámla** mezőben válassza ki a fizetés ellenszámláját.</span><span class="sxs-lookup"><span data-stu-id="1a0d7-140">In the **Offset account** field, select the account to offset the payment to.</span></span> <span data-ttu-id="1a0d7-141">Válassza például azt a bankot vagy főszámlát, a amelyre a fizetést könyvelni szeretné.</span><span class="sxs-lookup"><span data-stu-id="1a0d7-141">For example, select the bank or main account to post the payment to.</span></span>
12. <span data-ttu-id="1a0d7-142">A **Fizetési mód** mezőben válassza ki az ügyfél fizetési módját.</span><span class="sxs-lookup"><span data-stu-id="1a0d7-142">In the **Method of payment** field, select the customer's method of payment.</span></span>
13. <span data-ttu-id="1a0d7-143">A **Fizetés** lapon állítsa be az **Előlegnapló bizonylat** opciót **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="1a0d7-143">On the **Payment** tab, set the **Prepayment journal voucher** option to **Yes**.</span></span>
14. <span data-ttu-id="1a0d7-144">Ismételje meg a 7-13. lépést minden további előleghez, amelyet könyvelni szeretne.</span><span class="sxs-lookup"><span data-stu-id="1a0d7-144">Repeat steps 7 through 13 for each additional prepayment that must be posted.</span></span>
15. <span data-ttu-id="1a0d7-145">Válassza a **Közzététel** lehetőséget a napló véglegesítéséhez.</span><span class="sxs-lookup"><span data-stu-id="1a0d7-145">Select **Post** to finalize the journal.</span></span>

## <a name="settle-prepayments-with-invoices"></a><span data-ttu-id="1a0d7-146">Előlegek kiegyenlítés számlákkal</span><span class="sxs-lookup"><span data-stu-id="1a0d7-146">Settle prepayments with invoices</span></span>

<span data-ttu-id="1a0d7-147">Az **Vevői kifizetések** munkaterületén egyszerűen megtalálhatja és kiegyenlítheti a még nem teljesen kiegyenlített kifizetéseket.</span><span class="sxs-lookup"><span data-stu-id="1a0d7-147">You can use the **Customer payments** workspace to easily find and settle payments that haven't been fully settled.</span></span>

1. <span data-ttu-id="1a0d7-148">A **Kezdőlap** irányítópulton válassza ki a **Vevői kifizetések** csempét.</span><span class="sxs-lookup"><span data-stu-id="1a0d7-148">On the **Home** dashboard, select the **Customer payments** tile.</span></span>
2. <span data-ttu-id="1a0d7-149">A **Vevői tranzakciók** részben, a **Nem kiegyenlített kifizetések** lapon keresse meg és válassza ki a kiegyenlítendő kifizetést.</span><span class="sxs-lookup"><span data-stu-id="1a0d7-149">In the **Customer transactions** section, on the **Payments not settled** tab, search for and select the payment to settle.</span></span>
3. <span data-ttu-id="1a0d7-150">Válassza a **Tranzakcióinak kiegyenlítése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1a0d7-150">Select **Settle transactions**.</span></span>
4. <span data-ttu-id="1a0d7-151">Jelölje be a kiegyenlített számlához a **Jelölés** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="1a0d7-151">Select the **Mark** check box for the invoice and the payment that will be settled.</span></span>
5. <span data-ttu-id="1a0d7-152">Válassza a **Feladás** parancsot.</span><span class="sxs-lookup"><span data-stu-id="1a0d7-152">Select **Post**.</span></span>

<span data-ttu-id="1a0d7-153">A nyitott tranzakciók kiegyenlítéséről további információt a [Kiegyenlítés áttekintése](/cash-bank-management/settlement-overview.md) részben talál.</span><span class="sxs-lookup"><span data-stu-id="1a0d7-153">For more information about how to settle open transactions, see [Settlement overview](/cash-bank-management/settlement-overview.md).</span></span>
