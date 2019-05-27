---
title: Beszedési megbízási felhatalmazás létrehozása vevő részére
description: Ez az útmutató bemutatja, hogyan hozhat létre beszedési megbízási felhatalmazást, és hogyan használhatja azt számlához.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustTable, CustBankAccounts, BankAccountTable, CustPaymMode, CustDirectDebitMandate, BankAccountTableLookUp, SrsReportViewerForm,  LogisticsAddressCityLookup, CustFreeInvoice, CustTableLookup
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: fc3052fdfc6e3dcf2826b3069f6d644201a70c3c
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1572535"
---
# <a name="create-a-direct-debit-mandate-for-a-customer"></a><span data-ttu-id="a1d00-103">Beszedési megbízási felhatalmazás létrehozása vevő részére</span><span class="sxs-lookup"><span data-stu-id="a1d00-103">Create a direct debit mandate for a customer</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="a1d00-104">Ez az útmutató bemutatja, hogyan hozhat létre beszedési megbízási felhatalmazást, és hogyan használhatja azt számlához.</span><span class="sxs-lookup"><span data-stu-id="a1d00-104">This task guide demonstrates how to create a direct debit mandate and use it on an invoice.</span></span>


## <a name="create-a-bank-account"></a><span data-ttu-id="a1d00-105">Bankszámla létrehozása</span><span class="sxs-lookup"><span data-stu-id="a1d00-105">Create a bank account</span></span>
1. <span data-ttu-id="a1d00-106">Ugorjon a Kinnlevőségek > Vevők > Minden vevő pontra.</span><span class="sxs-lookup"><span data-stu-id="a1d00-106">Go to Accounts receivable > Customers > All customers.</span></span>
2. <span data-ttu-id="a1d00-107">Válassza ki például az US-001-et.</span><span class="sxs-lookup"><span data-stu-id="a1d00-107">For example, select US-001</span></span>
3. <span data-ttu-id="a1d00-108">A Művelet panelen kattintson a Vevő elemre.</span><span class="sxs-lookup"><span data-stu-id="a1d00-108">On the Action Pane, click Customer.</span></span>
4. <span data-ttu-id="a1d00-109">Kattintson a Bankszámlák lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="a1d00-109">Click Bank accounts.</span></span>
5. <span data-ttu-id="a1d00-110">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="a1d00-110">Click New.</span></span>
6. <span data-ttu-id="a1d00-111">A Bankszámla mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="a1d00-111">In the Bank account field, type a value.</span></span>
7. <span data-ttu-id="a1d00-112">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="a1d00-112">In the Name field, type a value.</span></span>
8. <span data-ttu-id="a1d00-113">Az IBAN mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="a1d00-113">In the IBAN field, type a value.</span></span>
9. <span data-ttu-id="a1d00-114">Érték beírása a Pénznem mezőbe.</span><span class="sxs-lookup"><span data-stu-id="a1d00-114">In the Currency field, type a value.</span></span>
10. <span data-ttu-id="a1d00-115">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="a1d00-115">Click Save.</span></span>
11. <span data-ttu-id="a1d00-116">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="a1d00-116">Close the page.</span></span>
12. <span data-ttu-id="a1d00-117">Menjen a Készpénz és bankkezelés > Bankszámlák > Bankszámlák menüpontra.</span><span class="sxs-lookup"><span data-stu-id="a1d00-117">Go to Cash and bank management > Bank accounts > Bank accounts.</span></span>
13. <span data-ttu-id="a1d00-118">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="a1d00-118">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="a1d00-119">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="a1d00-119">In the list, click the link in the selected row.</span></span>
15. <span data-ttu-id="a1d00-120">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="a1d00-120">Click Edit.</span></span>
16. <span data-ttu-id="a1d00-121">Bontsa ki a További azonosítás szakaszt.</span><span class="sxs-lookup"><span data-stu-id="a1d00-121">Expand the Additional identification section.</span></span>
17. <span data-ttu-id="a1d00-122">Írjon egy értéket a Beszedési megbízási azonosító mezőbe.</span><span class="sxs-lookup"><span data-stu-id="a1d00-122">In the Direct debit ID field, type a value.</span></span>
18. <span data-ttu-id="a1d00-123">Az IBAN mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="a1d00-123">In the IBAN field, type a value.</span></span>
19. <span data-ttu-id="a1d00-124">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="a1d00-124">Close the page.</span></span>
20. <span data-ttu-id="a1d00-125">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="a1d00-125">Close the page.</span></span>

## <a name="define-the-electronic-payment-method"></a><span data-ttu-id="a1d00-126">Elektronikus fizetési mód meghatározása</span><span class="sxs-lookup"><span data-stu-id="a1d00-126">Define the electronic payment method</span></span>
1. <span data-ttu-id="a1d00-127">Ugorjon a Kinnlevőségek > Fizetési beállítás > Fizetési mód pontra.</span><span class="sxs-lookup"><span data-stu-id="a1d00-127">Go to Accounts receivable > Payments setup > Methods of payment.</span></span>
2. <span data-ttu-id="a1d00-128">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="a1d00-128">Click New.</span></span>
3. <span data-ttu-id="a1d00-129">Írjon be egy értéket a Fizetési mód mezőbe.</span><span class="sxs-lookup"><span data-stu-id="a1d00-129">In the Method of payment field, type a value.</span></span>
4. <span data-ttu-id="a1d00-130">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="a1d00-130">In the Description field, type a value.</span></span>
5. <span data-ttu-id="a1d00-131">A beszedési megbízási felhatalmazás fizetési módjában elektronikus fizetést kell beállítani.</span><span class="sxs-lookup"><span data-stu-id="a1d00-131">The payment type for a direct debit mandate method of payment must be Electronic payment.</span></span>
6. <span data-ttu-id="a1d00-132">Válassza az Igen lehetőséget a Felhatalmazás szükséges mezőben.</span><span class="sxs-lookup"><span data-stu-id="a1d00-132">Select Yes in the Require mandate field.</span></span>
7. <span data-ttu-id="a1d00-133">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="a1d00-133">Close the page.</span></span>

## <a name="add-a-direct-debit-mandate-to-a-customer"></a><span data-ttu-id="a1d00-134">Beszedési megbízási rendelet hozzáadása a vevőhöz.</span><span class="sxs-lookup"><span data-stu-id="a1d00-134">Add a direct debit mandate to a customer.</span></span>
1. <span data-ttu-id="a1d00-135">Ugorjon a Kinnlevőségek > Vevők > Minden vevő pontra.</span><span class="sxs-lookup"><span data-stu-id="a1d00-135">Go to Accounts receivable > Customers > All customers.</span></span>
2. <span data-ttu-id="a1d00-136">Válassza ki például az US-001-et.</span><span class="sxs-lookup"><span data-stu-id="a1d00-136">For example, select US-001</span></span>
3. <span data-ttu-id="a1d00-137">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="a1d00-137">Click Edit.</span></span>
4. <span data-ttu-id="a1d00-138">Bontsa ki a Fizetés alapértelmezései szakaszt.</span><span class="sxs-lookup"><span data-stu-id="a1d00-138">Expand the Payment defaults section.</span></span>
5. <span data-ttu-id="a1d00-139">A Fizetési mód mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="a1d00-139">In the Method of payment field, enter or select a value.</span></span>
6. <span data-ttu-id="a1d00-140">Bontsa ki a Fizetés alapértelmezései szakaszt.</span><span class="sxs-lookup"><span data-stu-id="a1d00-140">Expand the Payment defaults section.</span></span>
7. <span data-ttu-id="a1d00-141">Bontsa ki a beszedési megbízási felhatalmazások szakaszt.</span><span class="sxs-lookup"><span data-stu-id="a1d00-141">Expand the Direct debit mandates section.</span></span>
8. <span data-ttu-id="a1d00-142">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="a1d00-142">Click Add.</span></span>
9. <span data-ttu-id="a1d00-143">A Bankszámlák mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="a1d00-143">In the Bank account field, enter or select a value.</span></span>
10. <span data-ttu-id="a1d00-144">A Hitelező bank mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="a1d00-144">In the Creditor bank account field, enter or select a value.</span></span>
11. <span data-ttu-id="a1d00-145">Adja meg, hogy várhatóan hány fizetést tervez feldolgozni ehhez a felhatalmazáshoz.</span><span class="sxs-lookup"><span data-stu-id="a1d00-145">Enter the number of payments that you expect to process for this mandate.</span></span>
12. <span data-ttu-id="a1d00-146">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="a1d00-146">Click OK.</span></span>
13. <span data-ttu-id="a1d00-147">Kattintson a Nyomtatás parancsra.</span><span class="sxs-lookup"><span data-stu-id="a1d00-147">Click Print.</span></span>
14. <span data-ttu-id="a1d00-148">Kattintson a Felhatalmazás jelentése pontra.</span><span class="sxs-lookup"><span data-stu-id="a1d00-148">Click Mandate report.</span></span>
15. <span data-ttu-id="a1d00-149">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="a1d00-149">Close the page.</span></span>
16. <span data-ttu-id="a1d00-150">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="a1d00-150">Click Edit.</span></span>
17. <span data-ttu-id="a1d00-151">Adja meg a dátumot az Aláírás dátuma mezőben.</span><span class="sxs-lookup"><span data-stu-id="a1d00-151">In the Signature date field, enter a date.</span></span>
18. <span data-ttu-id="a1d00-152">Kattintson az Igen gombra.</span><span class="sxs-lookup"><span data-stu-id="a1d00-152">Click Yes.</span></span>
19. <span data-ttu-id="a1d00-153">Adja meg a felhatalmazás aláírásának helyét.</span><span class="sxs-lookup"><span data-stu-id="a1d00-153">Enter the location where the mandate was signed.</span></span>
20. <span data-ttu-id="a1d00-154">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="a1d00-154">Click OK.</span></span>
21. <span data-ttu-id="a1d00-155">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="a1d00-155">Close the page.</span></span>

## <a name="create-a-free-text-invoice-with-mandate"></a><span data-ttu-id="a1d00-156">Szabadszöveges számla létrehozása felhatalmazással</span><span class="sxs-lookup"><span data-stu-id="a1d00-156">Create a free text invoice with mandate</span></span>
1. <span data-ttu-id="a1d00-157">Ugorjon a Kinnlévőségek > Számlák > Kizárólag szabadszöveges számlák pontra.</span><span class="sxs-lookup"><span data-stu-id="a1d00-157">Go to Accounts receivable > Invoices > All free text invoices.</span></span>
2. <span data-ttu-id="a1d00-158">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="a1d00-158">Click New.</span></span>
3. <span data-ttu-id="a1d00-159">Válassza ki a vevőt, akihez hozzáadta a felhatalmazást.</span><span class="sxs-lookup"><span data-stu-id="a1d00-159">Select the customer that you added the mandate to.</span></span>
4. <span data-ttu-id="a1d00-160">A Beszedési megbízási felhatalmazás azonosítója mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="a1d00-160">In the Direct debit mandate ID field, enter or select a value.</span></span>

