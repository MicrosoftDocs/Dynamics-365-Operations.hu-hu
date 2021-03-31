---
title: Leírási napló létrehozása vevőhöz
description: Az útmutató bemutatja, hogyan állíthatja be a leírások paramétereit, majd hogyan írhat le tranzakciókat a Beszedések lapról, a Nyitott vevői számlák lapról és a Vevő lapról.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustParameters, CustPosting, DefaultDashboard, CustCollectionsPoolsListPage, CustWriteOff, LedgerJournalTable, LedgerJournalTransDaily, CustCollections, CustOpenInvoicesListPage, CustTable
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 182afb5b105fec6dcac323b4f98db5fb7b3e0d68
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5220275"
---
# <a name="create-a-write-off-journal-for-a-customer"></a><span data-ttu-id="3fa15-103">Leírási napló létrehozása vevőhöz</span><span class="sxs-lookup"><span data-stu-id="3fa15-103">Create a write-off journal for a customer</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="3fa15-104">Az útmutató bemutatja, hogyan állíthatja be a leírások paramétereit, majd hogyan írhat le tranzakciókat a Beszedések lapról, a Nyitott vevői számlák lapról és a Vevő lapról.</span><span class="sxs-lookup"><span data-stu-id="3fa15-104">This task guide will show you how to set up the parameters for write-offs and then write off transactions from the Collections page, the Open customer invoices page, and the Customer page.</span></span> <span data-ttu-id="3fa15-105">Ez a feladat az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="3fa15-105">This task uses the USMF demo company.</span></span>


## <a name="set-up-the-write-off-parameters"></a><span data-ttu-id="3fa15-106">Leírási paraméterek beállítása</span><span class="sxs-lookup"><span data-stu-id="3fa15-106">Set up the write off parameters</span></span>
1. <span data-ttu-id="3fa15-107">Ugorjon ide: **Navigációs ablaktábla >Modulok > Követelések és beszedések > Beállítás > Kinnlevőségek paraméterei**.</span><span class="sxs-lookup"><span data-stu-id="3fa15-107">Go to **Navigation pane > Modules > Credit and collections > Setup > Accounts receivable parameters**.</span></span>
2. <span data-ttu-id="3fa15-108">Kattintson a **Beszedések** lapra.</span><span class="sxs-lookup"><span data-stu-id="3fa15-108">Click the **Collections** tab.</span></span>
3. <span data-ttu-id="3fa15-109">Bontsa ki vagy csukja össze a **Veszteségleírás** szakaszt.</span><span class="sxs-lookup"><span data-stu-id="3fa15-109">Expand or collapse the **Write-off** section.</span></span>
    - <span data-ttu-id="3fa15-110">A **leírási napló** egy általános napló, amely tartalmazza majd a létrehozott leírási tranzakciókat.</span><span class="sxs-lookup"><span data-stu-id="3fa15-110">The **Write-off journal** is the general journal that will hold the write-off transactions that you create.</span></span>  
    - <span data-ttu-id="3fa15-111">Minden leíráshoz társíthat okkódot.</span><span class="sxs-lookup"><span data-stu-id="3fa15-111">You can attach a reason code to every write-off.</span></span> <span data-ttu-id="3fa15-112">Ezt a beállítást felülírhatja a leírás alkalmával.</span><span class="sxs-lookup"><span data-stu-id="3fa15-112">You can override this default at the time of the write-off.</span></span>  
    - <span data-ttu-id="3fa15-113">Állítsa a **Külön áfa** beállítást Igenre, ha el szeretné különíteni az áfát a leírás eredeti tranzakciójától.</span><span class="sxs-lookup"><span data-stu-id="3fa15-113">Set the **Separate sales tax** to Yes if you want to separate the sales tax from the original transaction in the write-off.</span></span>  
4. <span data-ttu-id="3fa15-114">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="3fa15-114">Close the page.</span></span>
5. <span data-ttu-id="3fa15-115">Ugorjon a **Követelések és beszedések > Beállítás > Vevői feladási profilok pontra**.</span><span class="sxs-lookup"><span data-stu-id="3fa15-115">Go to **Credit and collections > Setup > Customer posting profiles**.</span></span> <span data-ttu-id="3fa15-116">A leírási számla költségszámlaként vagy foglaláshelyesbítésként jelenik meg az általános naplóban.</span><span class="sxs-lookup"><span data-stu-id="3fa15-116">The write-off account will be used as the expense account or reserve adjustment in the general journal.</span></span>
6. <span data-ttu-id="3fa15-117">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="3fa15-117">Close the page.</span></span>

## <a name="write-off-a-customer-balance-from-the-aged-balances-page"></a><span data-ttu-id="3fa15-118">Vevői egyenleg leírása a korosított egyenlegek oldalról</span><span class="sxs-lookup"><span data-stu-id="3fa15-118">Write off a customer balance from the aged balances page</span></span>
1. <span data-ttu-id="3fa15-119">Ugorjon a **Hitelezés és beszedés > Beszedés > Korosított egyenlegek** elemre.</span><span class="sxs-lookup"><span data-stu-id="3fa15-119">Go to **Credit and collections > Collections > Aged balances**.</span></span>
2. <span data-ttu-id="3fa15-120">Jelölje meg a leírni kívánt vevő sorát.</span><span class="sxs-lookup"><span data-stu-id="3fa15-120">Mark the row for the customer that you want to write off.</span></span> <span data-ttu-id="3fa15-121">Jelölje meg például a Birch Company nevet tartalmazó sort.</span><span class="sxs-lookup"><span data-stu-id="3fa15-121">For example, mark the line with Birch Company on it.</span></span>
3. <span data-ttu-id="3fa15-122">A **Művelet panelen** kattintson a **Beszed** elemre.</span><span class="sxs-lookup"><span data-stu-id="3fa15-122">On the **Action Pane**, click **Collect**.</span></span>
4. <span data-ttu-id="3fa15-123">Kattintson a **Leírás** gombra.</span><span class="sxs-lookup"><span data-stu-id="3fa15-123">Click **Write off**.</span></span>
5. <span data-ttu-id="3fa15-124">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="3fa15-124">Click **OK**.</span></span>
6. <span data-ttu-id="3fa15-125">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="3fa15-125">Close the page.</span></span>
7. <span data-ttu-id="3fa15-126">Nyissa meg a **Navigációs ablak > Modulok > Főkönyv > Naplóbejegyzések > Általános naplók** elemet.</span><span class="sxs-lookup"><span data-stu-id="3fa15-126">Go to **Navigation pane > Modules > General ledger > Journal entries > General journals**.</span></span>
8. <span data-ttu-id="3fa15-127">Válassza ki a leírást tartalmazó napló cikkszámát.</span><span class="sxs-lookup"><span data-stu-id="3fa15-127">Select the journal batch number for the journal that contains your write-off.</span></span> <span data-ttu-id="3fa15-128">Egy sor jön létre a vevői egyenleg visszaállításához.</span><span class="sxs-lookup"><span data-stu-id="3fa15-128">One line is created to reverse the customer balance.</span></span> <span data-ttu-id="3fa15-129">Egy vagy több sor jön létre a leírás leírási számlára való feladásához.</span><span class="sxs-lookup"><span data-stu-id="3fa15-129">One or more lines are created to post the write-off to the write-off account.</span></span>  
9. <span data-ttu-id="3fa15-130">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="3fa15-130">Close the page.</span></span>
10. <span data-ttu-id="3fa15-131">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="3fa15-131">Close the page.</span></span>

## <a name="write-off-transactions-from-the-collections-form"></a><span data-ttu-id="3fa15-132">Írja le a tranzakciókat a beszedések képernyőről.</span><span class="sxs-lookup"><span data-stu-id="3fa15-132">Write off transactions from the collections form.</span></span>
1. <span data-ttu-id="3fa15-133">Ugorjon a **Hitelezés és beszedés > Beszedés > Korosított egyenlegek** elemre.</span><span class="sxs-lookup"><span data-stu-id="3fa15-133">Go to **Credit and collections > Collections > Aged balances**.</span></span>
2. <span data-ttu-id="3fa15-134">Válassza ki a vevő nevét, akinél a leírni kívánt tranzakciók vannak.</span><span class="sxs-lookup"><span data-stu-id="3fa15-134">Select the name of the customer that has the transactions that you want to write off.</span></span> <span data-ttu-id="3fa15-135">Válassza ki például a Cave Wholesales (US-004) lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3fa15-135">For example, select Cave Wholesales (US-004).</span></span>
3. <span data-ttu-id="3fa15-136">Jelölje meg az első tranzakció sorát.</span><span class="sxs-lookup"><span data-stu-id="3fa15-136">Mark the row for the first transaction.</span></span>
4. <span data-ttu-id="3fa15-137">Jelölje meg a második tranzakció sorát.</span><span class="sxs-lookup"><span data-stu-id="3fa15-137">Mark the row for the second transaction.</span></span>
5. <span data-ttu-id="3fa15-138">Kattintson a **Leírás** gombra.</span><span class="sxs-lookup"><span data-stu-id="3fa15-138">Click **Write off**.</span></span>
6. <span data-ttu-id="3fa15-139">Az **Okra vonatkozó megjegyzés** mezőbe írja be a „Behajthatatlan tartozások” okot.</span><span class="sxs-lookup"><span data-stu-id="3fa15-139">In the **Reason comment** field, type 'Bad debts'.</span></span>
7. <span data-ttu-id="3fa15-140">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="3fa15-140">Click **OK**.</span></span>
8. <span data-ttu-id="3fa15-141">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="3fa15-141">Close the page.</span></span>
9. <span data-ttu-id="3fa15-142">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="3fa15-142">Close the page.</span></span>
10. <span data-ttu-id="3fa15-143">Ugorjon a **Főkönyv > Naplóbejegyzések > Általános naplók** pontra.</span><span class="sxs-lookup"><span data-stu-id="3fa15-143">Go to **General ledger > Journal entries > General journals**.</span></span>
11. <span data-ttu-id="3fa15-144">Válassza ki a leírást tartalmazó napló cikkszámát.</span><span class="sxs-lookup"><span data-stu-id="3fa15-144">Select the journal batch number for the journal that contains your write-off.</span></span> <span data-ttu-id="3fa15-145">Egy sor jön létre a vevői egyenleg visszaállításához.</span><span class="sxs-lookup"><span data-stu-id="3fa15-145">One line is created to reverse the customer balance.</span></span> <span data-ttu-id="3fa15-146">Egy vagy több sor jön létre a leírás leírási számlára való feladásához.</span><span class="sxs-lookup"><span data-stu-id="3fa15-146">One or more lines are created to post the write-off to the write-off account.</span></span>  
12. <span data-ttu-id="3fa15-147">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="3fa15-147">Close the page.</span></span>
13. <span data-ttu-id="3fa15-148">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="3fa15-148">Close the page.</span></span>

## <a name="write-off-an-invoice-from-the-open-customers-invoices-page"></a><span data-ttu-id="3fa15-149">Számla leírása a nyitott vevői számlák lapról</span><span class="sxs-lookup"><span data-stu-id="3fa15-149">Write off an invoice from the Open customers invoices page</span></span>
1. <span data-ttu-id="3fa15-150">Ugorjon a következőre: **Navigációs panel > Kinnlévőségek > Számlák > Nyitott vevői számlák**.</span><span class="sxs-lookup"><span data-stu-id="3fa15-150">Go to **Navigation pane > Modules > Accounts receivable > Invoices > Open customer invoices**.</span></span>
2. <span data-ttu-id="3fa15-151">Jelölje meg a sort számlázásra.</span><span class="sxs-lookup"><span data-stu-id="3fa15-151">Mark the line for an invoice.</span></span> <span data-ttu-id="3fa15-152">Jelölje meg például a CIV-000667 sort.</span><span class="sxs-lookup"><span data-stu-id="3fa15-152">For example, mark the line for CIV-000667.</span></span>
3. <span data-ttu-id="3fa15-153">A **Művelet panelen** kattintson a **Számla** elemre.</span><span class="sxs-lookup"><span data-stu-id="3fa15-153">On the **Action Pane**, click **Invoice**.</span></span>
4. <span data-ttu-id="3fa15-154">Kattintson a **Leírás** gombra.</span><span class="sxs-lookup"><span data-stu-id="3fa15-154">Click **Write off**.</span></span>
5. <span data-ttu-id="3fa15-155">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="3fa15-155">Click **OK**.</span></span>
6. <span data-ttu-id="3fa15-156">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="3fa15-156">Close the page.</span></span>

## <a name="write-off-a-customer-balance-from-the-customer-page"></a><span data-ttu-id="3fa15-157">Egy vevő egyenlegének leírása a vevői lapon</span><span class="sxs-lookup"><span data-stu-id="3fa15-157">Write off a customer balance from the customer page</span></span>
1. <span data-ttu-id="3fa15-158">Ugorjon a **Kinnlevőségek > Vevők > Minden vevő** pontra.</span><span class="sxs-lookup"><span data-stu-id="3fa15-158">Go to **Accounts receivable > Customers > All customers**.</span></span>
2. <span data-ttu-id="3fa15-159">Válasszon ki egy vevőt.</span><span class="sxs-lookup"><span data-stu-id="3fa15-159">Select a customer account.</span></span> <span data-ttu-id="3fa15-160">Válassza ki a például az US-001 (Contoso Retail San Diego) lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3fa15-160">For example, select US-001 (Contoso Retail San Diego).</span></span>
3. <span data-ttu-id="3fa15-161">A **Művelet panelen** kattintson a **Beszed** elemre.</span><span class="sxs-lookup"><span data-stu-id="3fa15-161">On the **Action Pane**, click **Collect**.</span></span>
4. <span data-ttu-id="3fa15-162">Kattintson a **Leírás** gombra.</span><span class="sxs-lookup"><span data-stu-id="3fa15-162">Click **Write off**.</span></span>
5. <span data-ttu-id="3fa15-163">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="3fa15-163">Click **OK**.</span></span>
6. <span data-ttu-id="3fa15-164">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="3fa15-164">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]