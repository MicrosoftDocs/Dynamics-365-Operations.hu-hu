---
title: Leírási napló létrehozása vevőhöz
description: Az útmutató bemutatja, hogyan állíthatja be a leírások paramétereit, majd hogyan írhat le tranzakciókat a Beszedések lapról, a Nyitott vevői számlák lapról és a Vevő lapról.
author: ShivamPandey-msft
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustParameters, CustPosting, DefaultDashboard, CustCollectionsPoolsListPage, CustWriteOff, LedgerJournalTable, LedgerJournalTransDaily, CustCollections, CustOpenInvoicesListPage, CustTable
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 857d3a224f35c4eeedbf4913aea14011091d5466
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5823119"
---
# <a name="create-a-write-off-journal-for-a-customer"></a><span data-ttu-id="ab1c8-103">Leírási napló létrehozása vevőhöz</span><span class="sxs-lookup"><span data-stu-id="ab1c8-103">Create a write-off journal for a customer</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ab1c8-104">Az útmutató bemutatja, hogyan állíthatja be a leírások paramétereit, majd hogyan írhat le tranzakciókat a Beszedések lapról, a Nyitott vevői számlák lapról és a Vevő lapról.</span><span class="sxs-lookup"><span data-stu-id="ab1c8-104">This task guide will show you how to set up the parameters for write-offs and then write off transactions from the Collections page, the Open customer invoices page, and the Customer page.</span></span> <span data-ttu-id="ab1c8-105">Ez a feladat az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="ab1c8-105">This task uses the USMF demo company.</span></span>


## <a name="set-up-the-write-off-parameters"></a><span data-ttu-id="ab1c8-106">Leírási paraméterek beállítása</span><span class="sxs-lookup"><span data-stu-id="ab1c8-106">Set up the write off parameters</span></span>
1. <span data-ttu-id="ab1c8-107">Ugorjon ide: **Navigációs ablaktábla >Modulok > Követelések és beszedések > Beállítás > Kinnlevőségek paraméterei**.</span><span class="sxs-lookup"><span data-stu-id="ab1c8-107">Go to **Navigation pane > Modules > Credit and collections > Setup > Accounts receivable parameters**.</span></span>
2. <span data-ttu-id="ab1c8-108">Kattintson a **Beszedések** lapra.</span><span class="sxs-lookup"><span data-stu-id="ab1c8-108">Click the **Collections** tab.</span></span>
3. <span data-ttu-id="ab1c8-109">Bontsa ki vagy csukja össze a **Veszteségleírás** szakaszt.</span><span class="sxs-lookup"><span data-stu-id="ab1c8-109">Expand or collapse the **Write-off** section.</span></span>
    - <span data-ttu-id="ab1c8-110">A **leírási napló** egy általános napló, amely tartalmazza majd a létrehozott leírási tranzakciókat.</span><span class="sxs-lookup"><span data-stu-id="ab1c8-110">The **Write-off journal** is the general journal that will hold the write-off transactions that you create.</span></span>  
    - <span data-ttu-id="ab1c8-111">Minden leíráshoz társíthat okkódot.</span><span class="sxs-lookup"><span data-stu-id="ab1c8-111">You can attach a reason code to every write-off.</span></span> <span data-ttu-id="ab1c8-112">Ezt a beállítást felülírhatja a leírás alkalmával.</span><span class="sxs-lookup"><span data-stu-id="ab1c8-112">You can override this default at the time of the write-off.</span></span>  
    - <span data-ttu-id="ab1c8-113">Állítsa a **Külön áfa** beállítást Igenre, ha el szeretné különíteni az áfát a leírás eredeti tranzakciójától.</span><span class="sxs-lookup"><span data-stu-id="ab1c8-113">Set the **Separate sales tax** to Yes if you want to separate the sales tax from the original transaction in the write-off.</span></span>  
4. <span data-ttu-id="ab1c8-114">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="ab1c8-114">Close the page.</span></span>
5. <span data-ttu-id="ab1c8-115">Ugorjon a **Követelések és beszedések > Beállítás > Vevői feladási profilok pontra**.</span><span class="sxs-lookup"><span data-stu-id="ab1c8-115">Go to **Credit and collections > Setup > Customer posting profiles**.</span></span> <span data-ttu-id="ab1c8-116">A leírási számla költségszámlaként vagy foglaláshelyesbítésként jelenik meg az általános naplóban.</span><span class="sxs-lookup"><span data-stu-id="ab1c8-116">The write-off account will be used as the expense account or reserve adjustment in the general journal.</span></span>
6. <span data-ttu-id="ab1c8-117">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="ab1c8-117">Close the page.</span></span>

## <a name="write-off-a-customer-balance-from-the-aged-balances-page"></a><span data-ttu-id="ab1c8-118">Vevői egyenleg leírása a korosított egyenlegek oldalról</span><span class="sxs-lookup"><span data-stu-id="ab1c8-118">Write off a customer balance from the aged balances page</span></span>
1. <span data-ttu-id="ab1c8-119">Ugorjon a **Hitelezés és beszedés > Beszedés > Korosított egyenlegek** elemre.</span><span class="sxs-lookup"><span data-stu-id="ab1c8-119">Go to **Credit and collections > Collections > Aged balances**.</span></span>
2. <span data-ttu-id="ab1c8-120">Jelölje meg a leírni kívánt vevő sorát.</span><span class="sxs-lookup"><span data-stu-id="ab1c8-120">Mark the row for the customer that you want to write off.</span></span> <span data-ttu-id="ab1c8-121">Jelölje meg például a Birch Company nevet tartalmazó sort.</span><span class="sxs-lookup"><span data-stu-id="ab1c8-121">For example, mark the line with Birch Company on it.</span></span>
3. <span data-ttu-id="ab1c8-122">A **Művelet panelen** kattintson a **Beszed** elemre.</span><span class="sxs-lookup"><span data-stu-id="ab1c8-122">On the **Action Pane**, click **Collect**.</span></span>
4. <span data-ttu-id="ab1c8-123">Kattintson a **Leírás** gombra.</span><span class="sxs-lookup"><span data-stu-id="ab1c8-123">Click **Write off**.</span></span>
5. <span data-ttu-id="ab1c8-124">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="ab1c8-124">Click **OK**.</span></span>
6. <span data-ttu-id="ab1c8-125">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="ab1c8-125">Close the page.</span></span>
7. <span data-ttu-id="ab1c8-126">Nyissa meg a **Navigációs ablak > Modulok > Főkönyv > Naplóbejegyzések > Általános naplók** elemet.</span><span class="sxs-lookup"><span data-stu-id="ab1c8-126">Go to **Navigation pane > Modules > General ledger > Journal entries > General journals**.</span></span>
8. <span data-ttu-id="ab1c8-127">Válassza ki a leírást tartalmazó napló cikkszámát.</span><span class="sxs-lookup"><span data-stu-id="ab1c8-127">Select the journal batch number for the journal that contains your write-off.</span></span> <span data-ttu-id="ab1c8-128">Egy sor jön létre a vevői egyenleg visszaállításához.</span><span class="sxs-lookup"><span data-stu-id="ab1c8-128">One line is created to reverse the customer balance.</span></span> <span data-ttu-id="ab1c8-129">Egy vagy több sor jön létre a leírás leírási számlára való feladásához.</span><span class="sxs-lookup"><span data-stu-id="ab1c8-129">One or more lines are created to post the write-off to the write-off account.</span></span>  
9. <span data-ttu-id="ab1c8-130">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="ab1c8-130">Close the page.</span></span>
10. <span data-ttu-id="ab1c8-131">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="ab1c8-131">Close the page.</span></span>

## <a name="write-off-transactions-from-the-collections-form"></a><span data-ttu-id="ab1c8-132">Írja le a tranzakciókat a beszedések képernyőről.</span><span class="sxs-lookup"><span data-stu-id="ab1c8-132">Write off transactions from the collections form.</span></span>
1. <span data-ttu-id="ab1c8-133">Ugorjon a **Hitelezés és beszedés > Beszedés > Korosított egyenlegek** elemre.</span><span class="sxs-lookup"><span data-stu-id="ab1c8-133">Go to **Credit and collections > Collections > Aged balances**.</span></span>
2. <span data-ttu-id="ab1c8-134">Válassza ki a vevő nevét, akinél a leírni kívánt tranzakciók vannak.</span><span class="sxs-lookup"><span data-stu-id="ab1c8-134">Select the name of the customer that has the transactions that you want to write off.</span></span> <span data-ttu-id="ab1c8-135">Válassza ki például a Cave Wholesales (US-004) lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ab1c8-135">For example, select Cave Wholesales (US-004).</span></span>
3. <span data-ttu-id="ab1c8-136">Jelölje meg az első tranzakció sorát.</span><span class="sxs-lookup"><span data-stu-id="ab1c8-136">Mark the row for the first transaction.</span></span>
4. <span data-ttu-id="ab1c8-137">Jelölje meg a második tranzakció sorát.</span><span class="sxs-lookup"><span data-stu-id="ab1c8-137">Mark the row for the second transaction.</span></span>
5. <span data-ttu-id="ab1c8-138">Kattintson a **Leírás** gombra.</span><span class="sxs-lookup"><span data-stu-id="ab1c8-138">Click **Write off**.</span></span>
6. <span data-ttu-id="ab1c8-139">Az **Okra vonatkozó megjegyzés** mezőbe írja be a „Behajthatatlan tartozások” okot.</span><span class="sxs-lookup"><span data-stu-id="ab1c8-139">In the **Reason comment** field, type 'Bad debts'.</span></span>
7. <span data-ttu-id="ab1c8-140">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="ab1c8-140">Click **OK**.</span></span>
8. <span data-ttu-id="ab1c8-141">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="ab1c8-141">Close the page.</span></span>
9. <span data-ttu-id="ab1c8-142">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="ab1c8-142">Close the page.</span></span>
10. <span data-ttu-id="ab1c8-143">Ugorjon a **Főkönyv > Naplóbejegyzések > Általános naplók** pontra.</span><span class="sxs-lookup"><span data-stu-id="ab1c8-143">Go to **General ledger > Journal entries > General journals**.</span></span>
11. <span data-ttu-id="ab1c8-144">Válassza ki a leírást tartalmazó napló cikkszámát.</span><span class="sxs-lookup"><span data-stu-id="ab1c8-144">Select the journal batch number for the journal that contains your write-off.</span></span> <span data-ttu-id="ab1c8-145">Egy sor jön létre a vevői egyenleg visszaállításához.</span><span class="sxs-lookup"><span data-stu-id="ab1c8-145">One line is created to reverse the customer balance.</span></span> <span data-ttu-id="ab1c8-146">Egy vagy több sor jön létre a leírás leírási számlára való feladásához.</span><span class="sxs-lookup"><span data-stu-id="ab1c8-146">One or more lines are created to post the write-off to the write-off account.</span></span>  
12. <span data-ttu-id="ab1c8-147">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="ab1c8-147">Close the page.</span></span>
13. <span data-ttu-id="ab1c8-148">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="ab1c8-148">Close the page.</span></span>

## <a name="write-off-an-invoice-from-the-open-customers-invoices-page"></a><span data-ttu-id="ab1c8-149">Számla leírása a nyitott vevői számlák lapról</span><span class="sxs-lookup"><span data-stu-id="ab1c8-149">Write off an invoice from the Open customers invoices page</span></span>
1. <span data-ttu-id="ab1c8-150">Ugorjon a következőre: **Navigációs panel > Kinnlévőségek > Számlák > Nyitott vevői számlák**.</span><span class="sxs-lookup"><span data-stu-id="ab1c8-150">Go to **Navigation pane > Modules > Accounts receivable > Invoices > Open customer invoices**.</span></span>
2. <span data-ttu-id="ab1c8-151">Jelölje meg a sort számlázásra.</span><span class="sxs-lookup"><span data-stu-id="ab1c8-151">Mark the line for an invoice.</span></span> <span data-ttu-id="ab1c8-152">Jelölje meg például a CIV-000667 sort.</span><span class="sxs-lookup"><span data-stu-id="ab1c8-152">For example, mark the line for CIV-000667.</span></span>
3. <span data-ttu-id="ab1c8-153">A **Művelet panelen** kattintson a **Számla** elemre.</span><span class="sxs-lookup"><span data-stu-id="ab1c8-153">On the **Action Pane**, click **Invoice**.</span></span>
4. <span data-ttu-id="ab1c8-154">Kattintson a **Leírás** gombra.</span><span class="sxs-lookup"><span data-stu-id="ab1c8-154">Click **Write off**.</span></span>
5. <span data-ttu-id="ab1c8-155">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="ab1c8-155">Click **OK**.</span></span>
6. <span data-ttu-id="ab1c8-156">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="ab1c8-156">Close the page.</span></span>

## <a name="write-off-a-customer-balance-from-the-customer-page"></a><span data-ttu-id="ab1c8-157">Egy vevő egyenlegének leírása a vevői lapon</span><span class="sxs-lookup"><span data-stu-id="ab1c8-157">Write off a customer balance from the customer page</span></span>
1. <span data-ttu-id="ab1c8-158">Ugorjon a **Kinnlevőségek > Vevők > Minden vevő** pontra.</span><span class="sxs-lookup"><span data-stu-id="ab1c8-158">Go to **Accounts receivable > Customers > All customers**.</span></span>
2. <span data-ttu-id="ab1c8-159">Válasszon ki egy vevőt.</span><span class="sxs-lookup"><span data-stu-id="ab1c8-159">Select a customer account.</span></span> <span data-ttu-id="ab1c8-160">Válassza ki a például az US-001 (Contoso Retail San Diego) lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ab1c8-160">For example, select US-001 (Contoso Retail San Diego).</span></span>
3. <span data-ttu-id="ab1c8-161">A **Művelet panelen** kattintson a **Beszed** elemre.</span><span class="sxs-lookup"><span data-stu-id="ab1c8-161">On the **Action Pane**, click **Collect**.</span></span>
4. <span data-ttu-id="ab1c8-162">Kattintson a **Leírás** gombra.</span><span class="sxs-lookup"><span data-stu-id="ab1c8-162">Click **Write off**.</span></span>
5. <span data-ttu-id="ab1c8-163">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="ab1c8-163">Click **OK**.</span></span>
6. <span data-ttu-id="ab1c8-164">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="ab1c8-164">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]