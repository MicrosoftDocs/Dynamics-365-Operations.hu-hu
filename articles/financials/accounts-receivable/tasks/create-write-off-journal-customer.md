---
title: Leírási napló létrehozása vevőhöz
description: Az útmutató bemutatja, hogyan állíthatja be a leírások paramétereit, majd hogyan írhat le tranzakciókat a Beszedések lapról, a Nyitott vevői számlák lapról és a Vevő lapról.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustParameters, CustPosting, DefaultDashboard, CustCollectionsPoolsListPage, CustWriteOff, LedgerJournalTable, LedgerJournalTransDaily, CustCollections, CustOpenInvoicesListPage, CustTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2cd576458bab1e4654d21773b581a5b0f726c928
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1545516"
---
# <a name="create-a-write-off-journal-for-a-customer"></a><span data-ttu-id="20078-103">Leírási napló létrehozása vevőhöz</span><span class="sxs-lookup"><span data-stu-id="20078-103">Create a write-off journal for a customer</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="20078-104">Az útmutató bemutatja, hogyan állíthatja be a leírások paramétereit, majd hogyan írhat le tranzakciókat a Beszedések lapról, a Nyitott vevői számlák lapról és a Vevő lapról.</span><span class="sxs-lookup"><span data-stu-id="20078-104">This task guide will show you how to set up the parameters for write-offs and then write off transactions from the Collections page, the Open customer invoices page, and the Customer page.</span></span> <span data-ttu-id="20078-105">Ez a feladat az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="20078-105">This task uses the USMF demo company.</span></span>


## <a name="set-up-the-write-off-parameters"></a><span data-ttu-id="20078-106">Leírási paraméterek beállítása</span><span class="sxs-lookup"><span data-stu-id="20078-106">Set up the write off parameters</span></span>
1. <span data-ttu-id="20078-107">Ugorjon a Követel és beszedések > Beállítás > Kinnlevőségek paraméterei pontra.</span><span class="sxs-lookup"><span data-stu-id="20078-107">Go to Credit and collections > Setup > Accounts receivable parameters.</span></span>
2. <span data-ttu-id="20078-108">Kattintson a Beszedések lapra.</span><span class="sxs-lookup"><span data-stu-id="20078-108">Click the Collections tab.</span></span>
3. <span data-ttu-id="20078-109">Bontsa ki vagy csukja össze a Leírás szakaszt.</span><span class="sxs-lookup"><span data-stu-id="20078-109">Expand or collapse the Write-off section.</span></span>
    * <span data-ttu-id="20078-110">A leírási napló egy általános napló, amely tartalmazza majd a létrehozott leírási tranzakciókat.</span><span class="sxs-lookup"><span data-stu-id="20078-110">The Write-off journal is the general journal that will hold the write-off transactions that you create.</span></span>  
    * <span data-ttu-id="20078-111">Minden leíráshoz társíthat okkódot.</span><span class="sxs-lookup"><span data-stu-id="20078-111">You can attach a reason code to every write-off.</span></span> <span data-ttu-id="20078-112">Ezt a beállítást felülírhatja a leírás alkalmával.</span><span class="sxs-lookup"><span data-stu-id="20078-112">You can override this default at the time of the write-off.</span></span>  
    * <span data-ttu-id="20078-113">Állítsa ezt a beállítást Igenre, ha el szeretné különíteni az áfát a leírás eredeti tranzakciójától.</span><span class="sxs-lookup"><span data-stu-id="20078-113">Set this to Yes if you want to separate the sales tax from the original transaction in the write-off.</span></span>  
4. <span data-ttu-id="20078-114">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="20078-114">Close the page.</span></span>
5. <span data-ttu-id="20078-115">Ugorjon a Követel és beszedések > Beállítás > Vevői feladási profilok pontra.</span><span class="sxs-lookup"><span data-stu-id="20078-115">Go to Credit and collections > Setup > Customer posting profiles.</span></span>
    * <span data-ttu-id="20078-116">A leírási számla költségszámlaként vagy foglaláshelyesbítésként jelenik meg az általános naplóban</span><span class="sxs-lookup"><span data-stu-id="20078-116">The write-off account will be used as the expense account or reserve adjustment in the general journal</span></span>   
6. <span data-ttu-id="20078-117">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="20078-117">Close the page.</span></span>

## <a name="write-off-a-customer-balance-from-the-aged-balances-page"></a><span data-ttu-id="20078-118">Vevői egyenleg leírása a korosított egyenlegek oldalról</span><span class="sxs-lookup"><span data-stu-id="20078-118">Write off a customer balance from the aged balances page</span></span>
1. <span data-ttu-id="20078-119">Ugorjon a Hitelezés és beszedés > Beszedés > Korosított egyenlegek pontra.</span><span class="sxs-lookup"><span data-stu-id="20078-119">Go to Credit and collections > Collections > Aged balances.</span></span>
2. <span data-ttu-id="20078-120">Jelölje meg a leírni kívánt vevő sorát.</span><span class="sxs-lookup"><span data-stu-id="20078-120">Mark the row for the customer that you want to write off.</span></span> <span data-ttu-id="20078-121">Jelölje meg például a Birch Company nevet tartalmazó sort.</span><span class="sxs-lookup"><span data-stu-id="20078-121">For example, mark the line with Birch Company on it.</span></span>
3. <span data-ttu-id="20078-122">A Művelet panelen kattintson a Beszed elemre.</span><span class="sxs-lookup"><span data-stu-id="20078-122">On the Action Pane, click Collect.</span></span>
4. <span data-ttu-id="20078-123">Kattintson a „Leírás” gombra.</span><span class="sxs-lookup"><span data-stu-id="20078-123">Click Write off.</span></span>
5. <span data-ttu-id="20078-124">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="20078-124">Click OK.</span></span>
6. <span data-ttu-id="20078-125">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="20078-125">Close the page.</span></span>
7. <span data-ttu-id="20078-126">Ugorjon a Főkönyv > Naplóbejegyzések > Általános naplók pontra.</span><span class="sxs-lookup"><span data-stu-id="20078-126">Go to General ledger > Journal entries > General journals.</span></span>
8. <span data-ttu-id="20078-127">Válassza ki a leírást tartalmazó napló cikkszámát.</span><span class="sxs-lookup"><span data-stu-id="20078-127">Select the journal batch number for the journal that contains your write-off.</span></span>
    * <span data-ttu-id="20078-128">Egy sor jön létre a vevői egyenleg visszaállításához.</span><span class="sxs-lookup"><span data-stu-id="20078-128">One line is created to reverse the customer balance.</span></span> <span data-ttu-id="20078-129">Egy vagy több sor jön létre a leírás leírási számlára való feladásához.</span><span class="sxs-lookup"><span data-stu-id="20078-129">One or more lines are created to post the write-off to the write-off account.</span></span>  
9. <span data-ttu-id="20078-130">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="20078-130">Close the page.</span></span>
10. <span data-ttu-id="20078-131">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="20078-131">Close the page.</span></span>

## <a name="write-off-transactions-from-the-collections-form"></a><span data-ttu-id="20078-132">Írja le a tranzakciókat a beszedések képernyőről.</span><span class="sxs-lookup"><span data-stu-id="20078-132">Write off transactions from the collections form.</span></span>
1. <span data-ttu-id="20078-133">Ugorjon a Hitelezés és beszedés > Beszedés > Korosított egyenlegek pontra.</span><span class="sxs-lookup"><span data-stu-id="20078-133">Go to Credit and collections > Collections > Aged balances.</span></span>
2. <span data-ttu-id="20078-134">Válassza ki a vevő nevét, akinél a leírni kívánt tranzakciók vannak.</span><span class="sxs-lookup"><span data-stu-id="20078-134">Select the name of the customer that has the transactions that you want to write off.</span></span> <span data-ttu-id="20078-135">Válassza ki például a Cave Wholesales (US-004) lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="20078-135">For example, select Cave Wholesales (US-004).</span></span>
3. <span data-ttu-id="20078-136">Jelölje meg az első tranzakció sorát.</span><span class="sxs-lookup"><span data-stu-id="20078-136">Mark the row for the first transaction.</span></span>
4. <span data-ttu-id="20078-137">Jelölje meg a második tranzakció sorát.</span><span class="sxs-lookup"><span data-stu-id="20078-137">Mark the row for the second transaction.</span></span>
5. <span data-ttu-id="20078-138">Kattintson a „Leírás” gombra.</span><span class="sxs-lookup"><span data-stu-id="20078-138">Click Write off.</span></span>
6. <span data-ttu-id="20078-139">Az Okra vonatkozó megjegyzés mezőbe írja be a „Behajthatatlan tartozások” okot.</span><span class="sxs-lookup"><span data-stu-id="20078-139">In the Reason comment field, type 'Bad debts'.</span></span>
7. <span data-ttu-id="20078-140">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="20078-140">Click OK.</span></span>
8. <span data-ttu-id="20078-141">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="20078-141">Close the page.</span></span>
9. <span data-ttu-id="20078-142">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="20078-142">Close the page.</span></span>
10. <span data-ttu-id="20078-143">Ugorjon a Főkönyv > Naplóbejegyzések > Általános naplók pontra.</span><span class="sxs-lookup"><span data-stu-id="20078-143">Go to General ledger > Journal entries > General journals.</span></span>
11. <span data-ttu-id="20078-144">Válassza ki a leírást tartalmazó napló cikkszámát.</span><span class="sxs-lookup"><span data-stu-id="20078-144">Select the journal batch number for the journal that contains your write-off.</span></span>
    * <span data-ttu-id="20078-145">Egy sor jön létre a vevői egyenleg visszaállításához.</span><span class="sxs-lookup"><span data-stu-id="20078-145">One line is created to reverse the customer balance.</span></span> <span data-ttu-id="20078-146">Egy vagy több sor jön létre a leírás leírási számlára való feladásához.</span><span class="sxs-lookup"><span data-stu-id="20078-146">One or more lines are created to post the write-off to the write-off account.</span></span>  
12. <span data-ttu-id="20078-147">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="20078-147">Close the page.</span></span>
13. <span data-ttu-id="20078-148">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="20078-148">Close the page.</span></span>

## <a name="write-off-an-invoice-from-the-open-customers-invoices-page"></a><span data-ttu-id="20078-149">Számla leírása a nyitott vevői számlák lapról</span><span class="sxs-lookup"><span data-stu-id="20078-149">Write off an invoice from the Open customers invoices page</span></span>
1. <span data-ttu-id="20078-150">Ugorjon a Kinnlévőségek > Számlák > Nyitott vevői számlák pontra.</span><span class="sxs-lookup"><span data-stu-id="20078-150">Go to Accounts receivable > Invoices > Open customer invoices.</span></span>
2. <span data-ttu-id="20078-151">Jelölje meg a sort számlázásra.</span><span class="sxs-lookup"><span data-stu-id="20078-151">Mark the line for an invoice.</span></span> <span data-ttu-id="20078-152">Jelölje meg például a CIV-000667 sort.</span><span class="sxs-lookup"><span data-stu-id="20078-152">For example, mark the line for CIV-000667.</span></span>
3. <span data-ttu-id="20078-153">A Művelet panelen kattintson a Számla lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="20078-153">On the Action Pane, click Invoice.</span></span>
4. <span data-ttu-id="20078-154">Kattintson a „Leírás” gombra.</span><span class="sxs-lookup"><span data-stu-id="20078-154">Click Write off.</span></span>
5. <span data-ttu-id="20078-155">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="20078-155">Click OK.</span></span>
6. <span data-ttu-id="20078-156">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="20078-156">Close the page.</span></span>

## <a name="write-off-a-customer-balance-from-the-customer-page"></a><span data-ttu-id="20078-157">Egy vevő egyenlegének leírása a vevői lapon</span><span class="sxs-lookup"><span data-stu-id="20078-157">Write off a customer balance from the customer page</span></span>
1. <span data-ttu-id="20078-158">Ugorjon a Kinnlevőségek > Vevők > Minden vevő pontra.</span><span class="sxs-lookup"><span data-stu-id="20078-158">Go to Accounts receivable > Customers > All customers.</span></span>
2. <span data-ttu-id="20078-159">Válasszon ki egy vevőt.</span><span class="sxs-lookup"><span data-stu-id="20078-159">Select a customer account.</span></span> <span data-ttu-id="20078-160">Válassza ki a például az US-001 (Contoso Retail San Diego) lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="20078-160">For example, select US-001 (Contoso Retail San Diego).</span></span>
3. <span data-ttu-id="20078-161">A Művelet panelen kattintson a Beszed elemre.</span><span class="sxs-lookup"><span data-stu-id="20078-161">On the Action Pane, click Collect.</span></span>
4. <span data-ttu-id="20078-162">Kattintson a „Leírás” gombra.</span><span class="sxs-lookup"><span data-stu-id="20078-162">Click Write off.</span></span>
5. <span data-ttu-id="20078-163">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="20078-163">Click OK.</span></span>
6. <span data-ttu-id="20078-164">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="20078-164">Close the page.</span></span>

