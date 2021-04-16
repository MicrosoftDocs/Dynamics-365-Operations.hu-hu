---
title: Beszedési megbízási felhatalmazás létrehozása vevő részére
description: Ez az útmutató bemutatja, hogyan hozhat létre beszedési megbízási felhatalmazást, és hogyan használhatja azt számlához.
author: ShivamPandey-msft
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustTable, CustBankAccounts, BankAccountTable, CustPaymMode, CustDirectDebitMandate, BankAccountTableLookUp, SrsReportViewerForm,  LogisticsAddressCityLookup, CustFreeInvoice, CustTableLookup
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e3bbf3703941255dfd82b8fb501ba8a9d1f3a2ec
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5835076"
---
# <a name="create-a-direct-debit-mandate-for-a-customer"></a><span data-ttu-id="295e6-103">Beszedési megbízási felhatalmazás létrehozása vevő részére</span><span class="sxs-lookup"><span data-stu-id="295e6-103">Create a direct debit mandate for a customer</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="295e6-104">Ez az útmutató bemutatja, hogyan hozhat létre beszedési megbízási felhatalmazást, és hogyan használhatja azt számlához.</span><span class="sxs-lookup"><span data-stu-id="295e6-104">This task guide demonstrates how to create a direct debit mandate and use it on an invoice.</span></span>


## <a name="create-a-bank-account"></a><span data-ttu-id="295e6-105">Bankszámla létrehozása</span><span class="sxs-lookup"><span data-stu-id="295e6-105">Create a bank account</span></span>
1. <span data-ttu-id="295e6-106">A **Navigációs ablaktáblán** ugorjon a **Modulok > Kintlévőségek > Ügyfelek > Minden ügyfél** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="295e6-106">In the **Navigation pane**, go to **Modules > Accounts receivable > Customers > All customers**.</span></span>
2. <span data-ttu-id="295e6-107">A listában válasszon ki egy rekordot.</span><span class="sxs-lookup"><span data-stu-id="295e6-107">In the list, select a record.</span></span> <span data-ttu-id="295e6-108">Válassza ki például az US-001-et.</span><span class="sxs-lookup"><span data-stu-id="295e6-108">For example, select US-001</span></span>
3. <span data-ttu-id="295e6-109">A Művelet panelen kattintson a **Vevő** elemre.</span><span class="sxs-lookup"><span data-stu-id="295e6-109">On the Action Pane, click **Customer**.</span></span>
4. <span data-ttu-id="295e6-110">Kattintson a **Bankszámlák** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="295e6-110">Click **Bank accounts**.</span></span>
5. <span data-ttu-id="295e6-111">Kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="295e6-111">Click **New**.</span></span>
6. <span data-ttu-id="295e6-112">A **Bankszámla** mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="295e6-112">In the **Bank account** field, type a value.</span></span>
7. <span data-ttu-id="295e6-113">Írjon be egy értéket a **Név** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="295e6-113">In the **Name** field, type a value.</span></span>
8. <span data-ttu-id="295e6-114">Az **IBAN** mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="295e6-114">In the **IBAN** field, type a value.</span></span>
9. <span data-ttu-id="295e6-115">Érték beírása a **Pénznem** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="295e6-115">In the **Currency** field, type a value.</span></span>
10. <span data-ttu-id="295e6-116">Kattintson a **Mentés** gombra.</span><span class="sxs-lookup"><span data-stu-id="295e6-116">Click **Save**.</span></span>
11. <span data-ttu-id="295e6-117">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="295e6-117">Close the page.</span></span>
12. <span data-ttu-id="295e6-118">A **navigációs ablakban** nyissa meg ezt: **Modulok > Készpénz- és banki menedzsment > Bankszámlák > Bankszámlák**.</span><span class="sxs-lookup"><span data-stu-id="295e6-118">In the **Navigation pane**, go to **Modules > Cash and bank management > Bank accounts > Bank accounts**.</span></span>
13. <span data-ttu-id="295e6-119">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="295e6-119">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="295e6-120">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="295e6-120">In the list, click the link in the selected row.</span></span>
15. <span data-ttu-id="295e6-121">Kattintson a **Szerkesztés** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="295e6-121">Click **Edit**.</span></span>
16. <span data-ttu-id="295e6-122">Bontsa ki a **További azonosítás** gyorslapot.</span><span class="sxs-lookup"><span data-stu-id="295e6-122">Expand the **Additional identification** fastTab.</span></span>
17. <span data-ttu-id="295e6-123">Írjon egy értéket a **Beszedési megbízási azonosító** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="295e6-123">In the **Direct debit ID** field, type a value.</span></span>
18. <span data-ttu-id="295e6-124">Az **IBAN** mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="295e6-124">In the **IBAN** field, type a value.</span></span>
19. <span data-ttu-id="295e6-125">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="295e6-125">Close the page.</span></span>
20. <span data-ttu-id="295e6-126">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="295e6-126">Close the page.</span></span>

## <a name="define-the-electronic-payment-method"></a><span data-ttu-id="295e6-127">Elektronikus fizetési mód meghatározása</span><span class="sxs-lookup"><span data-stu-id="295e6-127">Define the electronic payment method</span></span>
1. <span data-ttu-id="295e6-128">A **navigációs ablaktáblán** ugorjon a **Modulok > Követelések és beszedések > Fizetés beállítása > Fizetési módok** elemre.</span><span class="sxs-lookup"><span data-stu-id="295e6-128">In the **Navigation pane**, go to **Modules > Accounts receivable > Payments setup > Methods of payment**.</span></span>
2. <span data-ttu-id="295e6-129">Kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="295e6-129">Click **New**.</span></span>
3. <span data-ttu-id="295e6-130">Írjon be egy értéket a **Fizetési mód** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="295e6-130">In the **Method of payment** field, type a value.</span></span>
4. <span data-ttu-id="295e6-131">Írjon egy értéket a **Leírás** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="295e6-131">In the **Description** field, type a value.</span></span>
5. <span data-ttu-id="295e6-132">A **Fizetés típusa** mezőben adja meg az „Elektronikus fizetés” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="295e6-132">In the **Payment type** field, enter 'Electronic payment'.</span></span> <span data-ttu-id="295e6-133">A beszedési megbízási felhatalmazás fizetési módjában elektronikus fizetést kell beállítani.</span><span class="sxs-lookup"><span data-stu-id="295e6-133">The payment type for a direct debit mandate method of payment must be Electronic payment.</span></span>
6. <span data-ttu-id="295e6-134">Válassza az Igen lehetőséget a **Felhatalmazás szükséges** mezőben.</span><span class="sxs-lookup"><span data-stu-id="295e6-134">Select Yes in the **Require mandate** field.</span></span>
7. <span data-ttu-id="295e6-135">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="295e6-135">Close the page.</span></span>

## <a name="add-a-direct-debit-mandate-to-a-customer"></a><span data-ttu-id="295e6-136">Beszedési megbízási rendelet hozzáadása a vevőhöz.</span><span class="sxs-lookup"><span data-stu-id="295e6-136">Add a direct debit mandate to a customer.</span></span>
1. <span data-ttu-id="295e6-137">A **Navigációs ablaktáblán** ugorjon a **Modulok > Kintlévőségek > Ügyfelek > Minden ügyfél** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="295e6-137">In the **Navigation pane**, go to **Modules > Accounts receivable > Customers > All customers**.</span></span>
2. <span data-ttu-id="295e6-138">A listában válasszon ki egy rekordot.</span><span class="sxs-lookup"><span data-stu-id="295e6-138">In the list, select a record.</span></span> <span data-ttu-id="295e6-139">Válassza ki például az US-001-et.</span><span class="sxs-lookup"><span data-stu-id="295e6-139">For example, select US-001</span></span>
3. <span data-ttu-id="295e6-140">Kattintson a **Szerkesztés** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="295e6-140">Click **Edit**.</span></span>
4. <span data-ttu-id="295e6-141">Bontsa ki a **Fizetés alapértelmezései** gyorslapot.</span><span class="sxs-lookup"><span data-stu-id="295e6-141">Expand the **Payment defaults** fastTab.</span></span>
5. <span data-ttu-id="295e6-142">A **Fizetési mód** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="295e6-142">In the **Method of payment** field, enter or select a value.</span></span>
6. <span data-ttu-id="295e6-143">Bontsa ki a **Fizetés alapértelmezései** gyorslapot.</span><span class="sxs-lookup"><span data-stu-id="295e6-143">Expand the **Payment defaults** fastTab.</span></span>
7. <span data-ttu-id="295e6-144">Bontsa ki a **Beszedési megbízási felhatalmazások** gyorslapot.</span><span class="sxs-lookup"><span data-stu-id="295e6-144">Expand the **Direct debit mandates** fastTab.</span></span>
8. <span data-ttu-id="295e6-145">Kattintson a **Hozzáadás** parancsra.</span><span class="sxs-lookup"><span data-stu-id="295e6-145">Click **Add**.</span></span>
9. <span data-ttu-id="295e6-146">A **Bankszámlák** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="295e6-146">In the **Bank account** field, enter or select a value.</span></span>
10. <span data-ttu-id="295e6-147">A **Hitelező bank mezőben** adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="295e6-147">In the **Creditor bank account** field, enter or select a value.</span></span>
11. <span data-ttu-id="295e6-148">A **Fizetés gyakorisága** mezőben adja meg, hogy várhatóan hány fizetést tervez feldolgozni ehhez a felhatalmazáshoz.</span><span class="sxs-lookup"><span data-stu-id="295e6-148">In the **Payment frequency** field, enter the number of payments that you expect to process for this mandate.</span></span>
12. <span data-ttu-id="295e6-149">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="295e6-149">Click **OK**.</span></span>
13. <span data-ttu-id="295e6-150">Kattintson a **Nyomtatás** parancsra.</span><span class="sxs-lookup"><span data-stu-id="295e6-150">Click **Print**.</span></span>
14. <span data-ttu-id="295e6-151">Kattintson a **Felhatalmazás jelentése** pontra.</span><span class="sxs-lookup"><span data-stu-id="295e6-151">Click **Mandate report**.</span></span>
15. <span data-ttu-id="295e6-152">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="295e6-152">Close the page.</span></span>
16. <span data-ttu-id="295e6-153">Kattintson a **Szerkesztés** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="295e6-153">Click **Edit**.</span></span>
17. <span data-ttu-id="295e6-154">Adja meg a dátumot az **Aláírás dátuma** mezőben.</span><span class="sxs-lookup"><span data-stu-id="295e6-154">In the **Signature date** field, enter a date.</span></span>
18. <span data-ttu-id="295e6-155">Kattintson az **Igen** gombra.</span><span class="sxs-lookup"><span data-stu-id="295e6-155">Click **Yes**.</span></span>
19. <span data-ttu-id="295e6-156">Adja meg a felhatalmazás aláírásának helyét.</span><span class="sxs-lookup"><span data-stu-id="295e6-156">Enter the location where the mandate was signed.</span></span>
20. <span data-ttu-id="295e6-157">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="295e6-157">Click **OK**.</span></span>
21. <span data-ttu-id="295e6-158">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="295e6-158">Close the page.</span></span>

## <a name="create-a-free-text-invoice-with-mandate"></a><span data-ttu-id="295e6-159">Szabadszöveges számla létrehozása felhatalmazással</span><span class="sxs-lookup"><span data-stu-id="295e6-159">Create a free text invoice with mandate</span></span>
1. <span data-ttu-id="295e6-160">A **Navigációs panelen** ugorjon ide: **Modulok > Kinnlévőségek > Számlák > Kizárólag szabadszöveges számlák**.</span><span class="sxs-lookup"><span data-stu-id="295e6-160">In the **Navigation pane**, go to **Modules > Accounts receivable > Invoices > All free text invoices**.</span></span>
2. <span data-ttu-id="295e6-161">Kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="295e6-161">Click **New**.</span></span>
3. <span data-ttu-id="295e6-162">Válassza ki a vevőt, akihez hozzáadta a felhatalmazást.</span><span class="sxs-lookup"><span data-stu-id="295e6-162">Select the customer that you added the mandate to.</span></span>
4. <span data-ttu-id="295e6-163">A **Beszedési megbízási felhatalmazás azonosítója** mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="295e6-163">In the **Direct debit mandate ID** field, enter or select a value.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]