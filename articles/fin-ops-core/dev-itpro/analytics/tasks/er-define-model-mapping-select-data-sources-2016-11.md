---
title: ER-modelleképezések meghatározása és adatforrások kiválasztása hozzájuk
description: A következő lépések leírják, hogy egy Rendszergazda vagy Elektronikus jelentések fejlesztője szerepkörű felhasználó miként választhat ki adatforrásokat az Elektronikus jelentés adatmodellhez.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERDataModelDesigner, ERModelMappingTable, ERModelMappingDesigner, ERExpressionDesignerFormula
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a6287fa95b7ce7341e99d1b1a6b972db68a30398
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/18/2020
ms.locfileid: "3142167"
---
# <a name="define-er-model-mappings-and-select-data-sources-for-them"></a><span data-ttu-id="aab8c-103">ER-modelleképezések meghatározása és adatforrások kiválasztása hozzájuk</span><span class="sxs-lookup"><span data-stu-id="aab8c-103">Define ER model mappings and select data sources for them</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="aab8c-104">A következő lépések leírják, hogy egy Rendszergazda vagy Elektronikus jelentések fejlesztője szerepkörű felhasználó miként választhat ki adatforrásokat az Elektronikus jelentés (ER) adatmodellhez.</span><span class="sxs-lookup"><span data-stu-id="aab8c-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can select data sources for an Electronic reporting (ER) data model.</span></span> <span data-ttu-id="aab8c-105">Az adatforrások a kijelölt adatmodell egyes komponenseihez lesznek kötve a tervezéskor, és futásidőben feltöltik az adatmodellt üzleti adatokkal.</span><span class="sxs-lookup"><span data-stu-id="aab8c-105">The data sources will be bound to individual components of the selected data model at design time and populate business data to that data model at run-time.</span></span> <span data-ttu-id="aab8c-106">Ebben a példában ki fogja választani a meglévő adatok termékmodellt a minta vállalatra vonatkozóan, amelyet az vállalat, a Litware, Inc. mintájára hoztak létre. Hajtsa végre az alábbi lépéseket, először végezze el a „Hozzon létre egy új adatmodell” műveletsorban ismertetett lépéseket.</span><span class="sxs-lookup"><span data-stu-id="aab8c-106">In this example, you will select data sources for an existing data model that has been created for sample company, Litware, Inc. To complete these steps, you must first complete the steps in the "Create a new data model" procedure.</span></span>


## <a name="open-the-electronic-reporting-configurations-tree"></a><span data-ttu-id="aab8c-107">Az elektronikus jelentéskészítés konfigurációs fa megnyitása</span><span class="sxs-lookup"><span data-stu-id="aab8c-107">Open the Electronic Reporting configurations tree</span></span>
1. <span data-ttu-id="aab8c-108">Ugorjon a Szervezeti adminisztráció > Munkaterületek > Elektronikus jelentés pontra.</span><span class="sxs-lookup"><span data-stu-id="aab8c-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="aab8c-109">Kattintson a Jelentéskészítés konfigurációi lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="aab8c-109">Click Reporting configurations.</span></span>

## <a name="insert-a-new-model-mapping"></a><span data-ttu-id="aab8c-110">Új modell leképezés beszúrása</span><span class="sxs-lookup"><span data-stu-id="aab8c-110">Insert a new model mapping</span></span>
1. <span data-ttu-id="aab8c-111">A fán válassza ki a következőt: „Payments (simplified model)”.</span><span class="sxs-lookup"><span data-stu-id="aab8c-111">In the tree, select 'Payments (simplified model)'.</span></span>
2. <span data-ttu-id="aab8c-112">Kattintson a Tervező pontra.</span><span class="sxs-lookup"><span data-stu-id="aab8c-112">Click Designer.</span></span>
3. <span data-ttu-id="aab8c-113">Kattintson a Modell hozzárendelése adatforráshoz gombra.</span><span class="sxs-lookup"><span data-stu-id="aab8c-113">Click Map model to datasource.</span></span>
4. <span data-ttu-id="aab8c-114">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="aab8c-114">Click New.</span></span>
    * <span data-ttu-id="aab8c-115">Ez létrehoz egy új rekordot, amely az adatmodellt leképezi az adatforrásokra.</span><span class="sxs-lookup"><span data-stu-id="aab8c-115">This will create a new record that will map the data model to data sources.</span></span> <span data-ttu-id="aab8c-116">Ebben a példában az adatmodellt a kívánt fizetéstípus adatforrásaira képezi le: a jóváírás-átvitelre.</span><span class="sxs-lookup"><span data-stu-id="aab8c-116">In this example, you will map the data model to data sources for the desired payment type: credit transfer.</span></span>     <span data-ttu-id="aab8c-117">Lehetséges egynél több hozzárendelés egy adott adatmodellhez.</span><span class="sxs-lookup"><span data-stu-id="aab8c-117">It is possible to design more than one mapping for a particular data model.</span></span> <span data-ttu-id="aab8c-118">Például létrehozhat leképezést a különböző típusú kifizetésekre, például beszedési megbízások vagy átutalások.</span><span class="sxs-lookup"><span data-stu-id="aab8c-118">For example, you could create a mapping for the different types of payments, such as for direct debit or for credit transfers.</span></span> <span data-ttu-id="aab8c-119">Ebben a példában létrehoz egy leképezést jóváírás-átvitelekhez.</span><span class="sxs-lookup"><span data-stu-id="aab8c-119">In this example, you will create a mapping for credit transfers.</span></span>  
5. <span data-ttu-id="aab8c-120">A Név mezőbe írja be a „CT mapping” szöveget.</span><span class="sxs-lookup"><span data-stu-id="aab8c-120">In the Name field, type 'CT mapping'.</span></span>
    * <span data-ttu-id="aab8c-121">CT-leképezés</span><span class="sxs-lookup"><span data-stu-id="aab8c-121">CT mapping</span></span>  
6. <span data-ttu-id="aab8c-122">A Leírás mezőbe írja be a „Payment model mapping CT” szöveget.</span><span class="sxs-lookup"><span data-stu-id="aab8c-122">In the Description field, type 'Payment model mapping CT'.</span></span>
    * <span data-ttu-id="aab8c-123">Fizetési modell leképezési CT</span><span class="sxs-lookup"><span data-stu-id="aab8c-123">Payment model mapping CT</span></span>  
7. <span data-ttu-id="aab8c-124">A Definíció mezőbe írja be a „CustomerCreditTransferInitiation” szöveget.</span><span class="sxs-lookup"><span data-stu-id="aab8c-124">In the Definition field, type 'CustomerCreditTransferInitiation'.</span></span>
    * <span data-ttu-id="aab8c-125">CustomerCreditTransferInitiation</span><span class="sxs-lookup"><span data-stu-id="aab8c-125">CustomerCreditTransferInitiation</span></span>  
8. <span data-ttu-id="aab8c-126">ResolveChanges meghatározása.</span><span class="sxs-lookup"><span data-stu-id="aab8c-126">ResolveChanges the Definition.</span></span>
9. <span data-ttu-id="aab8c-127">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="aab8c-127">Click Save.</span></span>

## <a name="define-required-data-sources-for-the-current-model-mapping"></a><span data-ttu-id="aab8c-128">Adja meg a szükséges adatforrásokat az aktuális modell-leképezéshez</span><span class="sxs-lookup"><span data-stu-id="aab8c-128">Define required data sources for the current model mapping</span></span>
1. <span data-ttu-id="aab8c-129">Kattintson a Tervező pontra.</span><span class="sxs-lookup"><span data-stu-id="aab8c-129">Click Designer.</span></span>
2. <span data-ttu-id="aab8c-130">A fastruktúrában válassza ki a következőt: „Dynamics 365 for Operations\Tábla rekordjai” csomópont.</span><span class="sxs-lookup"><span data-stu-id="aab8c-130">In the tree, select 'Dynamics 365 for Operations\Table records'.</span></span>
3. <span data-ttu-id="aab8c-131">Kattintson a Gyökér hozzáadása gombra.</span><span class="sxs-lookup"><span data-stu-id="aab8c-131">Click Add root.</span></span>
    * <span data-ttu-id="aab8c-132">Adja meg az adatforrást a fizetési tranzakció eléréséhez.</span><span class="sxs-lookup"><span data-stu-id="aab8c-132">Enter this data source to access payment transactions.</span></span>  
4. <span data-ttu-id="aab8c-133">A Név mezőbe írja be a „Transactions” szöveget.</span><span class="sxs-lookup"><span data-stu-id="aab8c-133">In the Name field, type 'Transactions'.</span></span>
    * <span data-ttu-id="aab8c-134">Tranzakciók</span><span class="sxs-lookup"><span data-stu-id="aab8c-134">Transactions</span></span>  
5. <span data-ttu-id="aab8c-135">Írja be a Címke mezőbe, hogy „Tranzakciók”.</span><span class="sxs-lookup"><span data-stu-id="aab8c-135">In the Label field, enter 'Transactions'.</span></span>
    * <span data-ttu-id="aab8c-136">Tranzakciók</span><span class="sxs-lookup"><span data-stu-id="aab8c-136">Transactions</span></span>  
6. <span data-ttu-id="aab8c-137">A Súgó mezőbe írja be a "Főkönyvi naplósorok" szöveget.</span><span class="sxs-lookup"><span data-stu-id="aab8c-137">In the Help field, enter 'Ledger journal lines'.</span></span>
    * <span data-ttu-id="aab8c-138">Főkönyvi naplósorok</span><span class="sxs-lookup"><span data-stu-id="aab8c-138">Ledger journal lines</span></span>  
7. <span data-ttu-id="aab8c-139">Válassza az Igen lehetőséget a Lekérdezés kérése mezőben.</span><span class="sxs-lookup"><span data-stu-id="aab8c-139">Select Yes in the Ask for query field.</span></span>
    * <span data-ttu-id="aab8c-140">Válassza az Igen lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="aab8c-140">Select Yes.</span></span>  
8. <span data-ttu-id="aab8c-141">Írja be a Tábla mezőbe a „LedgerJournalTrans” szöveget.</span><span class="sxs-lookup"><span data-stu-id="aab8c-141">In the Table field, type 'LedgerJournalTrans'.</span></span>
    * <span data-ttu-id="aab8c-142">LedgerJournalTrans</span><span class="sxs-lookup"><span data-stu-id="aab8c-142">LedgerJournalTrans</span></span>  
9. <span data-ttu-id="aab8c-143">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="aab8c-143">Click OK.</span></span>
    * <span data-ttu-id="aab8c-144">Az aktuális adatmodellhez adatforrásként válassza a LedgerJournalTrans táblát.</span><span class="sxs-lookup"><span data-stu-id="aab8c-144">Select the LedgerJournalTrans table as a data source for the current data model.</span></span>  
10. <span data-ttu-id="aab8c-145">A fán válassza ki a „Functions\Calculated mező” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="aab8c-145">In the tree, select 'Functions\Calculated field'.</span></span>
11. <span data-ttu-id="aab8c-146">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="aab8c-146">Click Add.</span></span>
    * <span data-ttu-id="aab8c-147">Kattintson a Hozzáadás gombra egy új számított mező hozzáadásához.</span><span class="sxs-lookup"><span data-stu-id="aab8c-147">Click Add to add a new calculated field.</span></span>  
12. <span data-ttu-id="aab8c-148">A Név mezőbe írja be a '$EndToEndID' szöveget.</span><span class="sxs-lookup"><span data-stu-id="aab8c-148">In the Name field, type '$EndToEndID'.</span></span>
    * <span data-ttu-id="aab8c-149">$EndToEndID</span><span class="sxs-lookup"><span data-stu-id="aab8c-149">$EndToEndID</span></span>  
13. <span data-ttu-id="aab8c-150">Kattintson a Receptúra szerkesztése lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="aab8c-150">Click Edit formula.</span></span>
14. <span data-ttu-id="aab8c-151">A fában válassza ki a 'String\CONCATENATE' lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="aab8c-151">In the tree, select 'String\CONCATENATE'.</span></span>
15. <span data-ttu-id="aab8c-152">Kattintson a Függvény hozzáadása gombra.</span><span class="sxs-lookup"><span data-stu-id="aab8c-152">Click Add function.</span></span>
16. <span data-ttu-id="aab8c-153">A fában bontsa ki a Tranzakciók csomópontot.</span><span class="sxs-lookup"><span data-stu-id="aab8c-153">In the tree, expand 'Transactions'.</span></span>
17. <span data-ttu-id="aab8c-154">A fastruktúrában válassza ki a „Transactions\Voucher” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="aab8c-154">In the tree, select 'Transactions\Voucher'.</span></span>
18. <span data-ttu-id="aab8c-155">Kattintson az Adatforrás hozzáadása pontra.</span><span class="sxs-lookup"><span data-stu-id="aab8c-155">Click Add data source.</span></span>
19. <span data-ttu-id="aab8c-156">Adja meg a Képlet mezőben a „CONCATENATE(Transactions.Voucher, "-", ” szöveget.</span><span class="sxs-lookup"><span data-stu-id="aab8c-156">In the Formula field, enter 'CONCATENATE(Transactions.Voucher, "-", '.</span></span>
    * <span data-ttu-id="aab8c-157">Írja be a [, "-",] kifejezést a képlet végére.</span><span class="sxs-lookup"><span data-stu-id="aab8c-157">Type [ , "-", ] at the end of the formula.</span></span>  
20. <span data-ttu-id="aab8c-158">A fában válassza ki a 'String\TEXT' csomópontot.</span><span class="sxs-lookup"><span data-stu-id="aab8c-158">In the tree, select 'String\TEXT'.</span></span>
21. <span data-ttu-id="aab8c-159">Kattintson a Függvény hozzáadása gombra.</span><span class="sxs-lookup"><span data-stu-id="aab8c-159">Click Add function.</span></span>
22. <span data-ttu-id="aab8c-160">A fán válassza ki a „Transactions\Record-ID(RecId)” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="aab8c-160">In the tree, select 'Transactions\Record-ID(RecId)'.</span></span>
23. <span data-ttu-id="aab8c-161">Kattintson az Adatforrás hozzáadása pontra.</span><span class="sxs-lookup"><span data-stu-id="aab8c-161">Click Add data source.</span></span>
24. <span data-ttu-id="aab8c-162">Adja meg a Képlet mezőben a „CONCATENATE(Transactions.Voucher, "-", TEXT(Transactions.RecId))” szöveget.</span><span class="sxs-lookup"><span data-stu-id="aab8c-162">In the Formula field, enter 'CONCATENATE(Transactions.Voucher, "-", TEXT(Transactions.RecId))'.</span></span>
    * <span data-ttu-id="aab8c-163">Írja be a [))] kifejezést a képlet végére.</span><span class="sxs-lookup"><span data-stu-id="aab8c-163">Type [))] at the end of the formula.</span></span>  
25. <span data-ttu-id="aab8c-164">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="aab8c-164">Click Save.</span></span>
    * <span data-ttu-id="aab8c-165">Győződjön meg arról, hogy nincsenek hibák a létrehozott képletben.</span><span class="sxs-lookup"><span data-stu-id="aab8c-165">Make sure that no errors have been discovered for the created formula.</span></span> <span data-ttu-id="aab8c-166">Lásd a receptúra-szerkesztő vezérlőelem alatti HIBÁK fület.</span><span class="sxs-lookup"><span data-stu-id="aab8c-166">See the ERRORS tab below the formula editor control.</span></span>  
26. <span data-ttu-id="aab8c-167">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="aab8c-167">Close the page.</span></span>
27. <span data-ttu-id="aab8c-168">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="aab8c-168">Click OK.</span></span>
    * <span data-ttu-id="aab8c-169">A számított mező hozzáadása az adatforráshoz.</span><span class="sxs-lookup"><span data-stu-id="aab8c-169">Add the calculated field to this data source.</span></span>  
28. <span data-ttu-id="aab8c-170">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="aab8c-170">Click Add.</span></span>
    * <span data-ttu-id="aab8c-171">Kattintson a Hozzáadás gombra egy új számított mező hozzáadásához.</span><span class="sxs-lookup"><span data-stu-id="aab8c-171">Click Add to add a new calculated field.</span></span>  
29. <span data-ttu-id="aab8c-172">A Név mezőbe írja be a '$Amount' szöveget.</span><span class="sxs-lookup"><span data-stu-id="aab8c-172">In the Name field, type '$Amount'.</span></span>
    * <span data-ttu-id="aab8c-173">$Összeg</span><span class="sxs-lookup"><span data-stu-id="aab8c-173">$Amount</span></span>  
30. <span data-ttu-id="aab8c-174">Kattintson a Receptúra szerkesztése lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="aab8c-174">Click Edit formula.</span></span>
31. <span data-ttu-id="aab8c-175">A fában bontsa ki a Tranzakciók csomópontot.</span><span class="sxs-lookup"><span data-stu-id="aab8c-175">In the tree, expand 'Transactions'.</span></span>
32. <span data-ttu-id="aab8c-176">A fán válassza ki a „Transactions\Debit(AmountCurDebit)” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="aab8c-176">In the tree, select 'Transactions\Debit(AmountCurDebit)'.</span></span>
33. <span data-ttu-id="aab8c-177">Kattintson az Adatforrás hozzáadása pontra.</span><span class="sxs-lookup"><span data-stu-id="aab8c-177">Click Add data source.</span></span>
34. <span data-ttu-id="aab8c-178">Adja meg a Képlet mezőben a „Transactions.AmountCurDebit - ” szöveget.</span><span class="sxs-lookup"><span data-stu-id="aab8c-178">In the Formula field, enter 'Transactions.AmountCurDebit - '.</span></span>
    * <span data-ttu-id="aab8c-179">Írja be a [ - ] kifejezést a képlet végére.</span><span class="sxs-lookup"><span data-stu-id="aab8c-179">Type [ - ] at the end of the formula.</span></span>  
35. <span data-ttu-id="aab8c-180">A fán válassza ki a „Transactions\Credit(AmountCurCredit)” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="aab8c-180">In the tree, select 'Transactions\Credit(AmountCurCredit)'.</span></span>
36. <span data-ttu-id="aab8c-181">Kattintson az Adatforrás hozzáadása pontra.</span><span class="sxs-lookup"><span data-stu-id="aab8c-181">Click Add data source.</span></span>
37. <span data-ttu-id="aab8c-182">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="aab8c-182">Click Save.</span></span>
38. <span data-ttu-id="aab8c-183">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="aab8c-183">Close the page.</span></span>
39. <span data-ttu-id="aab8c-184">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="aab8c-184">Click OK.</span></span>
    * <span data-ttu-id="aab8c-185">Ez a $Amount számított mezőt hozzáadja a kijelölt adatforráshoz az aktuális adatmodell számára.</span><span class="sxs-lookup"><span data-stu-id="aab8c-185">This will add the $Amount calculated field to the selected data source for the current data model.</span></span>  
40. <span data-ttu-id="aab8c-186">A fastruktúrában válassza ki a „Transactions\$Amount” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="aab8c-186">In the tree, select 'Transactions\$Amount'.</span></span>
41. <span data-ttu-id="aab8c-187">A fában bontsa ki a Tranzakciók csomópontot.</span><span class="sxs-lookup"><span data-stu-id="aab8c-187">In the tree, expand 'Transactions'.</span></span>
42. <span data-ttu-id="aab8c-188">A fában bontsa ki a „Tranzakciók\$Összeg” elemet.</span><span class="sxs-lookup"><span data-stu-id="aab8c-188">In the tree, expand or collapse 'Transactions\$Amount'.</span></span>
43. <span data-ttu-id="aab8c-189">A fában bontsa ki vagy csukja össze a „Tranzakciók” elemet.</span><span class="sxs-lookup"><span data-stu-id="aab8c-189">In the tree, expand or collapse 'Transactions'.</span></span>
44. <span data-ttu-id="aab8c-190">A fastruktúrában válassza ki a következőt: „Dynamics 365 for Operations\Tábla rekordjai” csomópont.</span><span class="sxs-lookup"><span data-stu-id="aab8c-190">In the tree, select 'Dynamics 365 for Operations\Table records'.</span></span>
45. <span data-ttu-id="aab8c-191">Kattintson a Gyökér hozzáadása gombra.</span><span class="sxs-lookup"><span data-stu-id="aab8c-191">Click Add root.</span></span>
    * <span data-ttu-id="aab8c-192">Adja meg az adatforrást a vállalati bankszámla részleteihez való hozzáféréshez.</span><span class="sxs-lookup"><span data-stu-id="aab8c-192">Enter this data source to access the company's bank account details.</span></span>  
46. <span data-ttu-id="aab8c-193">A Név mezőbe írja be a BankAccount szöveget.</span><span class="sxs-lookup"><span data-stu-id="aab8c-193">In the Name field, type 'BankAccount'.</span></span>
    * <span data-ttu-id="aab8c-194">Bankszámla</span><span class="sxs-lookup"><span data-stu-id="aab8c-194">BankAccount</span></span>  
47. <span data-ttu-id="aab8c-195">Írja be a Címke mezőbe, hogy „Bank Account”.</span><span class="sxs-lookup"><span data-stu-id="aab8c-195">In the Label field, enter 'Bank Account'.</span></span>
    * <span data-ttu-id="aab8c-196">Bankszámla</span><span class="sxs-lookup"><span data-stu-id="aab8c-196">Bank Account</span></span>  
48. <span data-ttu-id="aab8c-197">Írja be a Súgó mezőbe, hogy „Bank Account”.</span><span class="sxs-lookup"><span data-stu-id="aab8c-197">In the Help field, enter 'Bank Account'.</span></span>
    * <span data-ttu-id="aab8c-198">Bankszámla</span><span class="sxs-lookup"><span data-stu-id="aab8c-198">Bank Account</span></span>  
49. <span data-ttu-id="aab8c-199">Válassza az Igen lehetőséget a Lekérdezés kérése mezőben.</span><span class="sxs-lookup"><span data-stu-id="aab8c-199">Select Yes in the Ask for query field.</span></span>
    * <span data-ttu-id="aab8c-200">Válassza az Igen lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="aab8c-200">Select Yes.</span></span>  
50. <span data-ttu-id="aab8c-201">Írja be a Tábla mezőbe a „BankAccountTable” szöveget.</span><span class="sxs-lookup"><span data-stu-id="aab8c-201">In the Table field, type 'BankAccountTable'.</span></span>
    * <span data-ttu-id="aab8c-202">BankAccountTable</span><span class="sxs-lookup"><span data-stu-id="aab8c-202">BankAccountTable</span></span>  
51. <span data-ttu-id="aab8c-203">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="aab8c-203">Click OK.</span></span>
    * <span data-ttu-id="aab8c-204">Az aktuális adatmodellhez adatforrásként válassza a BankAccountTable táblát.</span><span class="sxs-lookup"><span data-stu-id="aab8c-204">Select the BankAccountTable table as a data source for the current data model.</span></span>  
52. <span data-ttu-id="aab8c-205">Kattintson a Gyökér hozzáadása gombra.</span><span class="sxs-lookup"><span data-stu-id="aab8c-205">Click Add root.</span></span>
    * <span data-ttu-id="aab8c-206">Adja meg az adatforrást a vállalati követelményekhez való hozzáféréshez.</span><span class="sxs-lookup"><span data-stu-id="aab8c-206">Enter this data source to access the company's requisites.</span></span>  
53. <span data-ttu-id="aab8c-207">A Név mezőbe írja be a Vállalat szót.</span><span class="sxs-lookup"><span data-stu-id="aab8c-207">In the Name field, type 'Company'.</span></span>
    * <span data-ttu-id="aab8c-208">Cég</span><span class="sxs-lookup"><span data-stu-id="aab8c-208">Company</span></span>  
54. <span data-ttu-id="aab8c-209">A Címke mezőbe írjon be egy értéket.</span><span class="sxs-lookup"><span data-stu-id="aab8c-209">In the Label field, type a value.</span></span>
    * <span data-ttu-id="aab8c-210">Cégadatok</span><span class="sxs-lookup"><span data-stu-id="aab8c-210">Company information</span></span>  
55. <span data-ttu-id="aab8c-211">A Súgó mezőbe írja be a Vállalati információk szöveget.</span><span class="sxs-lookup"><span data-stu-id="aab8c-211">In the Help field, enter 'Company information'.</span></span>
    * <span data-ttu-id="aab8c-212">Cégadatok</span><span class="sxs-lookup"><span data-stu-id="aab8c-212">Company information</span></span>  
56. <span data-ttu-id="aab8c-213">Válassza az Igen lehetőséget a Lekérdezés kérése mezőben.</span><span class="sxs-lookup"><span data-stu-id="aab8c-213">Select Yes in the Ask for query field.</span></span>
    * <span data-ttu-id="aab8c-214">Válassza az Igen lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="aab8c-214">Select Yes.</span></span>  
57. <span data-ttu-id="aab8c-215">Írja be a Tábla mezőbe a „CompanyInfo” szöveget.</span><span class="sxs-lookup"><span data-stu-id="aab8c-215">In the Table field, type 'CompanyInfo'.</span></span>
    * <span data-ttu-id="aab8c-216">CompanyInfo</span><span class="sxs-lookup"><span data-stu-id="aab8c-216">CompanyInfo</span></span>  
58. <span data-ttu-id="aab8c-217">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="aab8c-217">Click OK.</span></span>
    * <span data-ttu-id="aab8c-218">Az aktuális adatmodellhez adatforrásként válassza a CompanyInfo táblát.</span><span class="sxs-lookup"><span data-stu-id="aab8c-218">Select the CompanyInfo table as a data source for the current data model.</span></span>  
59. <span data-ttu-id="aab8c-219">A fán válassza ki a „Functions\Calculated mező” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="aab8c-219">In the tree, select 'Functions\Calculated field'.</span></span>
60. <span data-ttu-id="aab8c-220">Kattintson a Gyökér hozzáadása gombra.</span><span class="sxs-lookup"><span data-stu-id="aab8c-220">Click Add root.</span></span>
    * <span data-ttu-id="aab8c-221">Számított mező beszúrása új adatforrásként.</span><span class="sxs-lookup"><span data-stu-id="aab8c-221">Insert a calculated field as a new data source.</span></span>  
61. <span data-ttu-id="aab8c-222">A Név mezőbe írja be az „ProcessingDateTime” szöveget.</span><span class="sxs-lookup"><span data-stu-id="aab8c-222">In the Name field, type 'ProcessingDateTime'.</span></span>
    * <span data-ttu-id="aab8c-223">ProcessingDateTime</span><span class="sxs-lookup"><span data-stu-id="aab8c-223">ProcessingDateTime</span></span>  
62. <span data-ttu-id="aab8c-224">A Címke mezőbe írja be a 'Feldolgozás dátuma és időpontja' szöveget.</span><span class="sxs-lookup"><span data-stu-id="aab8c-224">In the Label field, enter 'Processing date & time'.</span></span>
    * <span data-ttu-id="aab8c-225">Feldolgozás dátuma és időpontja</span><span class="sxs-lookup"><span data-stu-id="aab8c-225">Processing date & time</span></span>  
63. <span data-ttu-id="aab8c-226">Kattintson a Receptúra szerkesztése lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="aab8c-226">Click Edit formula.</span></span>
64. <span data-ttu-id="aab8c-227">A fastruktúrán jelölje be a „Dátum/idő\SESSIONNOW” elemet.</span><span class="sxs-lookup"><span data-stu-id="aab8c-227">In the tree, select 'Date/time\SESSIONNOW'.</span></span>
65. <span data-ttu-id="aab8c-228">Kattintson a Függvény hozzáadása gombra.</span><span class="sxs-lookup"><span data-stu-id="aab8c-228">Click Add function.</span></span>
66. <span data-ttu-id="aab8c-229">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="aab8c-229">Click Save.</span></span>
67. <span data-ttu-id="aab8c-230">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="aab8c-230">Close the page.</span></span>
68. <span data-ttu-id="aab8c-231">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="aab8c-231">Click OK.</span></span>
    * <span data-ttu-id="aab8c-232">Adja hozzá a ProcessingDateTime számított mezőt az aktuális adatmodellhez adatforrásként.</span><span class="sxs-lookup"><span data-stu-id="aab8c-232">Add the ProcessingDateTime calculated field as a data source for the current data model.</span></span>  
69. <span data-ttu-id="aab8c-233">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="aab8c-233">Click Save.</span></span>
70. <span data-ttu-id="aab8c-234">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="aab8c-234">Close the page.</span></span>
71. <span data-ttu-id="aab8c-235">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="aab8c-235">Close the page.</span></span>
72. <span data-ttu-id="aab8c-236">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="aab8c-236">Close the page.</span></span>

