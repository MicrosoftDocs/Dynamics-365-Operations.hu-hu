--- 
title: "Modell-leképezés meghatározása és adatforrások kiválasztása elektronikus jelentéskészítéshez (ER)"
description: "A következő lépések leírják, hogy egy Rendszergazda vagy Elektronikus jelentések fejlesztője szerepkörű felhasználó miként választhat ki adatforrásokat az Elektronikus jelentés (ER) adatmodellhez."
author: NickSelin
manager: AnnBe
ms.date: 01/16/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 512e24b5d0e20f00890e2a9abfe45b660a913913
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="define-model-mapping-and-select-data-sources-for-electronic-reporting-er"></a><span data-ttu-id="a1754-103">Modell-leképezés meghatározása és adatforrások kiválasztása elektronikus jelentéskészítéshez (ER)</span><span class="sxs-lookup"><span data-stu-id="a1754-103">Define model mapping and select data sources for electronic reporting (ER)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="a1754-104">A következő lépések leírják, hogy egy Rendszergazda vagy Elektronikus jelentések fejlesztője szerepkörű felhasználó miként választhat ki adatforrásokat az Elektronikus jelentés (ER) adatmodellhez.</span><span class="sxs-lookup"><span data-stu-id="a1754-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can select data sources for an Electronic reporting (ER) data model.</span></span> <span data-ttu-id="a1754-105">Az adatforrások a kijelölt adatmodell egyes komponenseihez lesznek kötve a tervezéskor, és futásidőben feltöltik az adatmodellt üzleti adatokkal.</span><span class="sxs-lookup"><span data-stu-id="a1754-105">The data sources will be bound to individual components of the selected data model at design time and populate business data to that data model at run-time.</span></span> <span data-ttu-id="a1754-106">Ebben a példában ki fogja választani a meglévő adatok termékmodellt a minta vállalatra vonatkozóan, amelyet az vállalat, a Litware, Inc. mintájára hoztak létre. Hajtsa végre az alábbi lépéseket, először végezze el a „Hozzon létre egy új adatmodell” műveletsorban ismertetett lépéseket.</span><span class="sxs-lookup"><span data-stu-id="a1754-106">In this example, you will select data sources for an existing data model that has been created for sample company, Litware, Inc. To complete these steps, you must first complete the steps in the “Create a new data model” procedure.</span></span>


## <a name="open-the-electronic-reporting-configurations-tree"></a><span data-ttu-id="a1754-107">Az elektronikus jelentéskészítés konfigurációs fa megnyitása</span><span class="sxs-lookup"><span data-stu-id="a1754-107">Open the Electronic Reporting configurations tree</span></span>
1. <span data-ttu-id="a1754-108">Ugorjon a Szervezeti adminisztráció > Munkaterületek > Elektronikus jelentés pontra.</span><span class="sxs-lookup"><span data-stu-id="a1754-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="a1754-109">Kattintson a Jelentéskészítés konfigurációi lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="a1754-109">Click Reporting configurations.</span></span>

## <a name="insert-a-new-model-mapping"></a><span data-ttu-id="a1754-110">Új modell leképezés beszúrása</span><span class="sxs-lookup"><span data-stu-id="a1754-110">Insert a new model mapping</span></span>
1. <span data-ttu-id="a1754-111">A fán válassza ki a következőt: „Payments (simplified model)”.</span><span class="sxs-lookup"><span data-stu-id="a1754-111">In the tree, select 'Payments (simplified model)'.</span></span>
2. <span data-ttu-id="a1754-112">Kattintson a Tervező pontra.</span><span class="sxs-lookup"><span data-stu-id="a1754-112">Click Designer.</span></span>
3. <span data-ttu-id="a1754-113">Kattintson a Modell hozzárendelése adatforráshoz gombra.</span><span class="sxs-lookup"><span data-stu-id="a1754-113">Click Map model to datasource.</span></span>
4. <span data-ttu-id="a1754-114">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="a1754-114">Click New.</span></span>
    * <span data-ttu-id="a1754-115">Ez létrehoz egy új rekordot, amely az adatmodellt leképezi az adatforrásokra.</span><span class="sxs-lookup"><span data-stu-id="a1754-115">This will create a new record that will map the data model to data sources.</span></span> <span data-ttu-id="a1754-116">Ebben a példában az adatmodellt a kívánt fizetéstípus adatforrásaira képezi le: a jóváírás-átvitelre.</span><span class="sxs-lookup"><span data-stu-id="a1754-116">In this example, you will map the data model to data sources for the desired payment type: credit transfer.</span></span>     <span data-ttu-id="a1754-117">Lehetséges egynél több hozzárendelés egy adott adatmodellhez.</span><span class="sxs-lookup"><span data-stu-id="a1754-117">It is possible to design more than one mapping for a particular data model.</span></span> <span data-ttu-id="a1754-118">Például létrehozhat leképezést a különböző típusú kifizetésekre, például beszedési megbízások vagy átutalások.</span><span class="sxs-lookup"><span data-stu-id="a1754-118">For example, you could create a mapping for the different types of payments, such as for direct debit or for credit transfers.</span></span> <span data-ttu-id="a1754-119">Ebben a példában létrehoz egy leképezést jóváírás-átvitelekhez.</span><span class="sxs-lookup"><span data-stu-id="a1754-119">In this example, you will create a mapping for credit transfers.</span></span>  
5. <span data-ttu-id="a1754-120">A Név mezőbe írja be a „CT mapping” szöveget.</span><span class="sxs-lookup"><span data-stu-id="a1754-120">In the Name field, type 'CT mapping'.</span></span>
    * <span data-ttu-id="a1754-121">CT-leképezés</span><span class="sxs-lookup"><span data-stu-id="a1754-121">CT mapping</span></span>  
6. <span data-ttu-id="a1754-122">A Leírás mezőbe írja be a „Payment model mapping CT” szöveget.</span><span class="sxs-lookup"><span data-stu-id="a1754-122">In the Description field, type 'Payment model mapping CT'.</span></span>
    * <span data-ttu-id="a1754-123">Fizetési modell leképezési CT</span><span class="sxs-lookup"><span data-stu-id="a1754-123">Payment model mapping CT</span></span>  
7. <span data-ttu-id="a1754-124">A Definíció mezőbe írja be a „CustomerCreditTransferInitiation” szöveget.</span><span class="sxs-lookup"><span data-stu-id="a1754-124">In the Definition field, type 'CustomerCreditTransferInitiation'.</span></span>
    * <span data-ttu-id="a1754-125">CustomerCreditTransferInitiation</span><span class="sxs-lookup"><span data-stu-id="a1754-125">CustomerCreditTransferInitiation</span></span>  
8. <span data-ttu-id="a1754-126">ResolveChanges meghatározása.</span><span class="sxs-lookup"><span data-stu-id="a1754-126">ResolveChanges the Definition.</span></span>
9. <span data-ttu-id="a1754-127">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="a1754-127">Click Save.</span></span>

## <a name="define-required-data-sources-for-the-current-model-mapping"></a><span data-ttu-id="a1754-128">Adja meg a szükséges adatforrásokat az aktuális modell-leképezéshez</span><span class="sxs-lookup"><span data-stu-id="a1754-128">Define required data sources for the current model mapping</span></span>
1. <span data-ttu-id="a1754-129">Kattintson a Tervező pontra.</span><span class="sxs-lookup"><span data-stu-id="a1754-129">Click Designer.</span></span>
2. <span data-ttu-id="a1754-130">A fán válassza ki a „Dynamics 365 for Operations\Table records” pontot.</span><span class="sxs-lookup"><span data-stu-id="a1754-130">In the tree, select 'Dynamics 365 for Operations\Table records'.</span></span>
3. <span data-ttu-id="a1754-131">Kattintson a Gyökér hozzáadása gombra.</span><span class="sxs-lookup"><span data-stu-id="a1754-131">Click Add root.</span></span>
    * <span data-ttu-id="a1754-132">Adja meg az adatforrást a fizetési tranzakció eléréséhez.</span><span class="sxs-lookup"><span data-stu-id="a1754-132">Enter this data source to access payment transactions.</span></span>  
4. <span data-ttu-id="a1754-133">A Név mezőbe írja be a „Transactions” szöveget.</span><span class="sxs-lookup"><span data-stu-id="a1754-133">In the Name field, type 'Transactions'.</span></span>
    * <span data-ttu-id="a1754-134">Tranzakciók</span><span class="sxs-lookup"><span data-stu-id="a1754-134">Transactions</span></span>  
5. <span data-ttu-id="a1754-135">Írja be a Címke mezőbe, hogy „Tranzakciók”.</span><span class="sxs-lookup"><span data-stu-id="a1754-135">In the Label field, enter 'Transactions'.</span></span>
    * <span data-ttu-id="a1754-136">Tranzakciók</span><span class="sxs-lookup"><span data-stu-id="a1754-136">Transactions</span></span>  
6. <span data-ttu-id="a1754-137">A Súgó mezőbe írja be a "Főkönyvi naplósorok" szöveget.</span><span class="sxs-lookup"><span data-stu-id="a1754-137">In the Help field, enter 'Ledger journal lines'.</span></span>
    * <span data-ttu-id="a1754-138">Főkönyvi naplósorok</span><span class="sxs-lookup"><span data-stu-id="a1754-138">Ledger journal lines</span></span>  
7. <span data-ttu-id="a1754-139">Válassza az Igen lehetőséget a Lekérdezés kérése mezőben.</span><span class="sxs-lookup"><span data-stu-id="a1754-139">Select Yes in the Ask for query field.</span></span>
    * <span data-ttu-id="a1754-140">Válassza az Igen lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a1754-140">Select Yes.</span></span>  
8. <span data-ttu-id="a1754-141">Írja be a Tábla mezőbe a „LedgerJournalTrans” szöveget.</span><span class="sxs-lookup"><span data-stu-id="a1754-141">In the Table field, type 'LedgerJournalTrans'.</span></span>
    * <span data-ttu-id="a1754-142">LedgerJournalTrans</span><span class="sxs-lookup"><span data-stu-id="a1754-142">LedgerJournalTrans</span></span>  
9. <span data-ttu-id="a1754-143">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="a1754-143">Click OK.</span></span>
    * <span data-ttu-id="a1754-144">Az aktuális adatmodellhez adatforrásként válassza a LedgerJournalTrans táblát.</span><span class="sxs-lookup"><span data-stu-id="a1754-144">Select the LedgerJournalTrans table as a data source for the current data model.</span></span>  
10. <span data-ttu-id="a1754-145">A fán válassza ki a „Functions\Calculated mező” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a1754-145">In the tree, select 'Functions\Calculated field'.</span></span>
11. <span data-ttu-id="a1754-146">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="a1754-146">Click Add.</span></span>
    * <span data-ttu-id="a1754-147">Kattintson a Hozzáadás gombra egy új számított mező hozzáadásához.</span><span class="sxs-lookup"><span data-stu-id="a1754-147">Click Add to add a new calculated field.</span></span>  
12. <span data-ttu-id="a1754-148">A Név mezőbe írja be a '$EndToEndID' szöveget.</span><span class="sxs-lookup"><span data-stu-id="a1754-148">In the Name field, type '$EndToEndID'.</span></span>
    * <span data-ttu-id="a1754-149">$EndToEndID</span><span class="sxs-lookup"><span data-stu-id="a1754-149">$EndToEndID</span></span>  
13. <span data-ttu-id="a1754-150">Kattintson a Receptúra szerkesztése lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="a1754-150">Click Edit formula.</span></span>
14. <span data-ttu-id="a1754-151">A fában válassza ki a 'String\CONCATENATE' lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a1754-151">In the tree, select 'String\CONCATENATE'.</span></span>
15. <span data-ttu-id="a1754-152">Kattintson a Függvény hozzáadása gombra.</span><span class="sxs-lookup"><span data-stu-id="a1754-152">Click Add function.</span></span>
16. <span data-ttu-id="a1754-153">A fában bontsa ki a Tranzakciók csomópontot.</span><span class="sxs-lookup"><span data-stu-id="a1754-153">In the tree, expand 'Transactions'.</span></span>
17. <span data-ttu-id="a1754-154">A fastruktúrában válassza ki a „Transactions\Voucher” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a1754-154">In the tree, select 'Transactions\Voucher'.</span></span>
18. <span data-ttu-id="a1754-155">Kattintson az Adatforrás hozzáadása pontra.</span><span class="sxs-lookup"><span data-stu-id="a1754-155">Click Add data source.</span></span>
19. <span data-ttu-id="a1754-156">Adja meg a Képlet mezőben a „CONCATENATE(Transactions.Voucher, "-", ” szöveget.</span><span class="sxs-lookup"><span data-stu-id="a1754-156">In the Formula field, enter 'CONCATENATE(Transactions.Voucher, "-", '.</span></span>
    * <span data-ttu-id="a1754-157">Írja be a [, "-",] kifejezést a képlet végére.</span><span class="sxs-lookup"><span data-stu-id="a1754-157">Type [ , “-“, ] at the end of the formula.</span></span>  
20. <span data-ttu-id="a1754-158">A fában válassza ki a 'String\TEXT' csomópontot.</span><span class="sxs-lookup"><span data-stu-id="a1754-158">In the tree, select 'String\TEXT'.</span></span>
21. <span data-ttu-id="a1754-159">Kattintson a Függvény hozzáadása gombra.</span><span class="sxs-lookup"><span data-stu-id="a1754-159">Click Add function.</span></span>
22. <span data-ttu-id="a1754-160">A fán válassza ki a „Transactions\Record-ID(RecId)” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a1754-160">In the tree, select 'Transactions\Record-ID(RecId)'.</span></span>
23. <span data-ttu-id="a1754-161">Kattintson az Adatforrás hozzáadása pontra.</span><span class="sxs-lookup"><span data-stu-id="a1754-161">Click Add data source.</span></span>
24. <span data-ttu-id="a1754-162">Adja meg a Képlet mezőben a „CONCATENATE(Transactions.Voucher, "-", TEXT(Transactions.RecId))” szöveget.</span><span class="sxs-lookup"><span data-stu-id="a1754-162">In the Formula field, enter 'CONCATENATE(Transactions.Voucher, "-", TEXT(Transactions.RecId))'.</span></span>
    * <span data-ttu-id="a1754-163">Írja be a [))] kifejezést a képlet végére.</span><span class="sxs-lookup"><span data-stu-id="a1754-163">Type [))] at the end of the formula.</span></span>  
25. <span data-ttu-id="a1754-164">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="a1754-164">Click Save.</span></span>
    * <span data-ttu-id="a1754-165">Győződjön meg arról, hogy nincsenek hibák a létrehozott képletben.</span><span class="sxs-lookup"><span data-stu-id="a1754-165">Make sure that no errors have been discovered for the created formula.</span></span> <span data-ttu-id="a1754-166">Lásd a receptúra-szerkesztő vezérlőelem alatti HIBÁK fület.</span><span class="sxs-lookup"><span data-stu-id="a1754-166">See the ERRORS tab below the formula editor control.</span></span>  
26. <span data-ttu-id="a1754-167">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="a1754-167">Close the page.</span></span>
27. <span data-ttu-id="a1754-168">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="a1754-168">Click OK.</span></span>
    * <span data-ttu-id="a1754-169">A számított mező hozzáadása az adatforráshoz.</span><span class="sxs-lookup"><span data-stu-id="a1754-169">Add the calculated field to this data source.</span></span>  
28. <span data-ttu-id="a1754-170">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="a1754-170">Click Add.</span></span>
    * <span data-ttu-id="a1754-171">Kattintson a Hozzáadás gombra egy új számított mező hozzáadásához.</span><span class="sxs-lookup"><span data-stu-id="a1754-171">Click Add to add a new calculated field.</span></span>  
29. <span data-ttu-id="a1754-172">A Név mezőbe írja be a '$Amount' szöveget.</span><span class="sxs-lookup"><span data-stu-id="a1754-172">In the Name field, type '$Amount'.</span></span>
    * <span data-ttu-id="a1754-173">$Összeg</span><span class="sxs-lookup"><span data-stu-id="a1754-173">$Amount</span></span>  
30. <span data-ttu-id="a1754-174">Kattintson a Receptúra szerkesztése lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="a1754-174">Click Edit formula.</span></span>
31. <span data-ttu-id="a1754-175">A fában bontsa ki a Tranzakciók csomópontot.</span><span class="sxs-lookup"><span data-stu-id="a1754-175">In the tree, expand 'Transactions'.</span></span>
32. <span data-ttu-id="a1754-176">A fán válassza ki a „Transactions\Debit(AmountCurDebit)” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a1754-176">In the tree, select 'Transactions\Debit(AmountCurDebit)'.</span></span>
33. <span data-ttu-id="a1754-177">Kattintson az Adatforrás hozzáadása pontra.</span><span class="sxs-lookup"><span data-stu-id="a1754-177">Click Add data source.</span></span>
34. <span data-ttu-id="a1754-178">Adja meg a Képlet mezőben a „Transactions.AmountCurDebit - ” szöveget.</span><span class="sxs-lookup"><span data-stu-id="a1754-178">In the Formula field, enter 'Transactions.AmountCurDebit - '.</span></span>
    * <span data-ttu-id="a1754-179">Írja be a [ - ] kifejezést a képlet végére.</span><span class="sxs-lookup"><span data-stu-id="a1754-179">Type [ - ] at the end of the formula.</span></span>  
35. <span data-ttu-id="a1754-180">A fán válassza ki a „Transactions\Credit(AmountCurCredit)” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a1754-180">In the tree, select 'Transactions\Credit(AmountCurCredit)'.</span></span>
36. <span data-ttu-id="a1754-181">Kattintson az Adatforrás hozzáadása pontra.</span><span class="sxs-lookup"><span data-stu-id="a1754-181">Click Add data source.</span></span>
37. <span data-ttu-id="a1754-182">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="a1754-182">Click Save.</span></span>
38. <span data-ttu-id="a1754-183">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="a1754-183">Close the page.</span></span>
39. <span data-ttu-id="a1754-184">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="a1754-184">Click OK.</span></span>
    * <span data-ttu-id="a1754-185">Ez a $Amount számított mezőt hozzáadja a kijelölt adatforráshoz az aktuális adatmodell számára.</span><span class="sxs-lookup"><span data-stu-id="a1754-185">This will add the $Amount calculated field to the selected data source for the current data model.</span></span>  
40. <span data-ttu-id="a1754-186">A fastruktúrában válassza ki a „Transactions\$Amount” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a1754-186">In the tree, select 'Transactions\$Amount'.</span></span>
41. <span data-ttu-id="a1754-187">A fában bontsa ki a Tranzakciók csomópontot.</span><span class="sxs-lookup"><span data-stu-id="a1754-187">In the tree, expand 'Transactions'.</span></span>
42. <span data-ttu-id="a1754-188">A fában bontsa ki a „Tranzakciók\$Összeg” elemet.</span><span class="sxs-lookup"><span data-stu-id="a1754-188">In the tree, expand or collapse 'Transactions\$Amount'.</span></span>
43. <span data-ttu-id="a1754-189">A fában bontsa ki vagy csukja össze a „Tranzakciók” elemet.</span><span class="sxs-lookup"><span data-stu-id="a1754-189">In the tree, expand or collapse 'Transactions'.</span></span>
44. <span data-ttu-id="a1754-190">A fán válassza ki a „Dynamics 365 for Operations\Table records” pontot.</span><span class="sxs-lookup"><span data-stu-id="a1754-190">In the tree, select 'Dynamics 365 for Operations\Table records'.</span></span>
45. <span data-ttu-id="a1754-191">Kattintson a Gyökér hozzáadása gombra.</span><span class="sxs-lookup"><span data-stu-id="a1754-191">Click Add root.</span></span>
    * <span data-ttu-id="a1754-192">Adja meg az adatforrást a vállalati bankszámla részleteihez való hozzáféréshez.</span><span class="sxs-lookup"><span data-stu-id="a1754-192">Enter this data source to access the company’s bank account details.</span></span>  
46. <span data-ttu-id="a1754-193">A Név mezőbe írja be a BankAccount szöveget.</span><span class="sxs-lookup"><span data-stu-id="a1754-193">In the Name field, type 'BankAccount'.</span></span>
    * <span data-ttu-id="a1754-194">Bankszámla</span><span class="sxs-lookup"><span data-stu-id="a1754-194">BankAccount</span></span>  
47. <span data-ttu-id="a1754-195">Írja be a Címke mezőbe, hogy „Bank Account”.</span><span class="sxs-lookup"><span data-stu-id="a1754-195">In the Label field, enter 'Bank Account'.</span></span>
    * <span data-ttu-id="a1754-196">Bankszámla</span><span class="sxs-lookup"><span data-stu-id="a1754-196">Bank Account</span></span>  
48. <span data-ttu-id="a1754-197">Írja be a Súgó mezőbe, hogy „Bank Account”.</span><span class="sxs-lookup"><span data-stu-id="a1754-197">In the Help field, enter 'Bank Account'.</span></span>
    * <span data-ttu-id="a1754-198">Bankszámla</span><span class="sxs-lookup"><span data-stu-id="a1754-198">Bank Account</span></span>  
49. <span data-ttu-id="a1754-199">Válassza az Igen lehetőséget a Lekérdezés kérése mezőben.</span><span class="sxs-lookup"><span data-stu-id="a1754-199">Select Yes in the Ask for query field.</span></span>
    * <span data-ttu-id="a1754-200">Válassza az Igen lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a1754-200">Select Yes.</span></span>  
50. <span data-ttu-id="a1754-201">Írja be a Tábla mezőbe a „BankAccountTable” szöveget.</span><span class="sxs-lookup"><span data-stu-id="a1754-201">In the Table field, type 'BankAccountTable'.</span></span>
    * <span data-ttu-id="a1754-202">BankAccountTable</span><span class="sxs-lookup"><span data-stu-id="a1754-202">BankAccountTable</span></span>  
51. <span data-ttu-id="a1754-203">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="a1754-203">Click OK.</span></span>
    * <span data-ttu-id="a1754-204">Az aktuális adatmodellhez adatforrásként válassza a BankAccountTable táblát.</span><span class="sxs-lookup"><span data-stu-id="a1754-204">Select the BankAccountTable table as a data source for the current data model.</span></span>  
52. <span data-ttu-id="a1754-205">Kattintson a Gyökér hozzáadása gombra.</span><span class="sxs-lookup"><span data-stu-id="a1754-205">Click Add root.</span></span>
    * <span data-ttu-id="a1754-206">Adja meg az adatforrást a vállalati követelményekhez való hozzáféréshez.</span><span class="sxs-lookup"><span data-stu-id="a1754-206">Enter this data source to access the company’s requisites.</span></span>  
53. <span data-ttu-id="a1754-207">A Név mezőbe írja be a Vállalat szót.</span><span class="sxs-lookup"><span data-stu-id="a1754-207">In the Name field, type 'Company'.</span></span>
    * <span data-ttu-id="a1754-208">Cég</span><span class="sxs-lookup"><span data-stu-id="a1754-208">Company</span></span>  
54. <span data-ttu-id="a1754-209">A Címke mezőbe írjon be egy értéket.</span><span class="sxs-lookup"><span data-stu-id="a1754-209">In the Label field, type a value.</span></span>
    * <span data-ttu-id="a1754-210">Cégadatok</span><span class="sxs-lookup"><span data-stu-id="a1754-210">Company information</span></span>  
55. <span data-ttu-id="a1754-211">A Súgó mezőbe írja be a Vállalati információk szöveget.</span><span class="sxs-lookup"><span data-stu-id="a1754-211">In the Help field, enter 'Company information'.</span></span>
    * <span data-ttu-id="a1754-212">Cégadatok</span><span class="sxs-lookup"><span data-stu-id="a1754-212">Company information</span></span>  
56. <span data-ttu-id="a1754-213">Válassza az Igen lehetőséget a Lekérdezés kérése mezőben.</span><span class="sxs-lookup"><span data-stu-id="a1754-213">Select Yes in the Ask for query field.</span></span>
    * <span data-ttu-id="a1754-214">Válassza az Igen lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a1754-214">Select Yes.</span></span>  
57. <span data-ttu-id="a1754-215">Írja be a Tábla mezőbe a „CompanyInfo” szöveget.</span><span class="sxs-lookup"><span data-stu-id="a1754-215">In the Table field, type 'CompanyInfo'.</span></span>
    * <span data-ttu-id="a1754-216">CompanyInfo</span><span class="sxs-lookup"><span data-stu-id="a1754-216">CompanyInfo</span></span>  
58. <span data-ttu-id="a1754-217">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="a1754-217">Click OK.</span></span>
    * <span data-ttu-id="a1754-218">Az aktuális adatmodellhez adatforrásként válassza a CompanyInfo táblát.</span><span class="sxs-lookup"><span data-stu-id="a1754-218">Select the CompanyInfo table as a data source for the current data model.</span></span>  
59. <span data-ttu-id="a1754-219">A fán válassza ki a „Functions\Calculated mező” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a1754-219">In the tree, select 'Functions\Calculated field'.</span></span>
60. <span data-ttu-id="a1754-220">Kattintson a Gyökér hozzáadása gombra.</span><span class="sxs-lookup"><span data-stu-id="a1754-220">Click Add root.</span></span>
    * <span data-ttu-id="a1754-221">Számított mező beszúrása új adatforrásként.</span><span class="sxs-lookup"><span data-stu-id="a1754-221">Insert a calculated field as a new data source.</span></span>  
61. <span data-ttu-id="a1754-222">A Név mezőbe írja be az „ProcessingDateTime” szöveget.</span><span class="sxs-lookup"><span data-stu-id="a1754-222">In the Name field, type 'ProcessingDateTime'.</span></span>
    * <span data-ttu-id="a1754-223">ProcessingDateTime</span><span class="sxs-lookup"><span data-stu-id="a1754-223">ProcessingDateTime</span></span>  
62. <span data-ttu-id="a1754-224">A Címke mezőbe írja be a 'Feldolgozás dátuma és időpontja' szöveget.</span><span class="sxs-lookup"><span data-stu-id="a1754-224">In the Label field, enter 'Processing date & time'.</span></span>
    * <span data-ttu-id="a1754-225">Feldolgozás dátuma és időpontja</span><span class="sxs-lookup"><span data-stu-id="a1754-225">Processing date & time</span></span>  
63. <span data-ttu-id="a1754-226">Kattintson a Receptúra szerkesztése lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="a1754-226">Click Edit formula.</span></span>
64. <span data-ttu-id="a1754-227">A fastruktúrán jelölje be a „Dátum/idő\SESSIONNOW” elemet.</span><span class="sxs-lookup"><span data-stu-id="a1754-227">In the tree, select 'Date/time\SESSIONNOW'.</span></span>
65. <span data-ttu-id="a1754-228">Kattintson a Függvény hozzáadása gombra.</span><span class="sxs-lookup"><span data-stu-id="a1754-228">Click Add function.</span></span>
66. <span data-ttu-id="a1754-229">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="a1754-229">Click Save.</span></span>
67. <span data-ttu-id="a1754-230">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="a1754-230">Close the page.</span></span>
68. <span data-ttu-id="a1754-231">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="a1754-231">Click OK.</span></span>
    * <span data-ttu-id="a1754-232">Adja hozzá a ProcessingDateTime számított mezőt az aktuális adatmodellhez adatforrásként.</span><span class="sxs-lookup"><span data-stu-id="a1754-232">Add the ProcessingDateTime calculated field as a data source for the current data model.</span></span>  
69. <span data-ttu-id="a1754-233">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="a1754-233">Click Save.</span></span>
70. <span data-ttu-id="a1754-234">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="a1754-234">Close the page.</span></span>
71. <span data-ttu-id="a1754-235">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="a1754-235">Close the page.</span></span>
72. <span data-ttu-id="a1754-236">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="a1754-236">Close the page.</span></span>

