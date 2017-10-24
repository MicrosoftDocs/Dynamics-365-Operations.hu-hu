--- 
title: "Adatmodell hozzárendelése a kiválasztott adatforrásokhoz az elektronikus jelentéskészítéshez (ER)"
description: "A következő lépések leírják, hogy egy Rendszergazda vagy Elektronikus jelentések fejlesztője szerepkörű felhasználó miként képezhet le egy Elektronikus jelentés (ER) adatmodellt a kiválasztott Dynamics 365 for Finance and Operations Enterprise kiadás adatforrásokra."
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
ms.openlocfilehash: 96974d7c1597db4ac31168be40cecbc7e12d6edd
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="map-a-data-model-to-selected-data-sources-for-electronic-reporting-er"></a><span data-ttu-id="e63a6-103">Adatmodell hozzárendelése a kiválasztott adatforrásokhoz az elektronikus jelentéskészítéshez (ER)</span><span class="sxs-lookup"><span data-stu-id="e63a6-103">Map a data model to selected data sources for electronic reporting (ER)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e63a6-104">A következő lépések leírják, hogy egy Rendszergazda vagy Elektronikus jelentések fejlesztője szerepkörű felhasználó miként képezhet le egy Elektronikus jelentés (ER) adatmodellt a kiválasztott Dynamics 365 for Finance and Operations Enterprise kiadás adatforrásokra.</span><span class="sxs-lookup"><span data-stu-id="e63a6-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can map an Electronic reporting (ER) data model to selected Dynamics 365 for Finance and Operations, Enterprise edition data sources.</span></span> <span data-ttu-id="e63a6-105">Ez a modell leképezést lesz később az adatforrás egy formátumkonfigurációban, amely elektronikus fizetési dokumentumok kezelésére lesz használva.</span><span class="sxs-lookup"><span data-stu-id="e63a6-105">This model mapping will later be used as a data source in a format configuration that will be used to manage electronic payment documents.</span></span> <span data-ttu-id="e63a6-106">Ebben a példában a mintavállalat, a Litware, a Inc. adatmodelljét képezi le az adatforrásokhoz.</span><span class="sxs-lookup"><span data-stu-id="e63a6-106">In this example, you map a data model for sample company, Litware, Inc. to data sources.</span></span> <span data-ttu-id="e63a6-107">A lépések végrehajtásához először hajtsa végre az „Adatforrások kijelölése modell-leképezéshez” műveletsorban ismertetett lépéseket.</span><span class="sxs-lookup"><span data-stu-id="e63a6-107">To complete these steps, you must first complete the steps in the “Select data sources for model mapping” procedure.</span></span>


## <a name="open-er-configurations-tree"></a><span data-ttu-id="e63a6-108">Nyitott ER konfigurációs fa</span><span class="sxs-lookup"><span data-stu-id="e63a6-108">Open ER configurations tree</span></span>
1. <span data-ttu-id="e63a6-109">Ugorjon a Szervezeti adminisztráció > Munkaterületek > Elektronikus jelentés pontra.</span><span class="sxs-lookup"><span data-stu-id="e63a6-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="e63a6-110">Kattintson a Konfigurációk lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e63a6-110">Click Configurations.</span></span>

## <a name="select-created-model-mapping"></a><span data-ttu-id="e63a6-111">Válassza ki a létrehozott modell-leképezést</span><span class="sxs-lookup"><span data-stu-id="e63a6-111">Select created model mapping</span></span>
1. <span data-ttu-id="e63a6-112">A fán válassza ki a következőt: „Payments (simplified model)”.</span><span class="sxs-lookup"><span data-stu-id="e63a6-112">In the tree, select 'Payments (simplified model)'.</span></span>
    * <span data-ttu-id="e63a6-113">Győződjön meg arról, hogy a „Kifizetések (egyszerűsített modell)” modellkonfigurációja előre létre lett hozva.</span><span class="sxs-lookup"><span data-stu-id="e63a6-113">Make sure that the model configuration “Payments (simplified model)” has been created in advance.</span></span> <span data-ttu-id="e63a6-114">Ellenkező esetben álljon meg itt, és térjen vissza az „Új konfiguráció létrehozása a kijelölt tartomány adatmodelljével” feladat-útmutató elvégzése után.</span><span class="sxs-lookup"><span data-stu-id="e63a6-114">Otherwise, stop now and return after completion of the task guide ‘Create a new configuration with data model of the selected domain’.</span></span>  
2. <span data-ttu-id="e63a6-115">Kattintson a Modelltervező lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e63a6-115">Click Model designer.</span></span>
3. <span data-ttu-id="e63a6-116">Kattintson a Modell hozzárendelése adatforráshoz gombra.</span><span class="sxs-lookup"><span data-stu-id="e63a6-116">Click Map model to datasource.</span></span>
4. <span data-ttu-id="e63a6-117">Válassza ki a „CT leképezés” rekordot.</span><span class="sxs-lookup"><span data-stu-id="e63a6-117">Select the 'CT mapping' record.</span></span>
    * <span data-ttu-id="e63a6-118">CT-leképezés</span><span class="sxs-lookup"><span data-stu-id="e63a6-118">CT mapping</span></span>  

## <a name="bind-created-data-sources-to-data-model-elements"></a><span data-ttu-id="e63a6-119">Létrehozott adatforrások adatmodell-elemekhez kötése</span><span class="sxs-lookup"><span data-stu-id="e63a6-119">Bind created data sources to data model elements</span></span>
1. <span data-ttu-id="e63a6-120">Kattintson a Tervező pontra.</span><span class="sxs-lookup"><span data-stu-id="e63a6-120">Click Designer.</span></span>
2. <span data-ttu-id="e63a6-121">A fastruktúrán jelölje be a „Dátum és idő feldolgozása (ProcessingDateTime)” elemet.</span><span class="sxs-lookup"><span data-stu-id="e63a6-121">In the tree, select 'Processing date & time(ProcessingDateTime)'.</span></span>
3. <span data-ttu-id="e63a6-122">A fán jelölje be a „Dátum feldolgozása (ProcessingDateTime)” elemet.</span><span class="sxs-lookup"><span data-stu-id="e63a6-122">In the tree, select 'Processing date(ProcessingDateTime)'.</span></span>
4. <span data-ttu-id="e63a6-123">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="e63a6-123">Click Bind.</span></span>
5. <span data-ttu-id="e63a6-124">A fán jelölje be a „Fizetési üzenet azonosítása (MessageIdentification)”.</span><span class="sxs-lookup"><span data-stu-id="e63a6-124">In the tree, select 'Payment message identification(MessageIdentification)'.</span></span>
6. <span data-ttu-id="e63a6-125">A fában bontsa ki a Tranzakciók csomópontot.</span><span class="sxs-lookup"><span data-stu-id="e63a6-125">In the tree, expand 'Transactions'.</span></span>
7. <span data-ttu-id="e63a6-126">A fán jelölje be a „Tranzakciók/napló kötegelt szám(JournalNum)”.</span><span class="sxs-lookup"><span data-stu-id="e63a6-126">In the tree, select 'Transactions\Journal batch number(JournalNum)'.</span></span>
8. <span data-ttu-id="e63a6-127">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="e63a6-127">Click Bind.</span></span>
9. <span data-ttu-id="e63a6-128">A fastruktúrában válassza ki a „Fizetések” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e63a6-128">In the tree, select 'Payments'.</span></span>
10. <span data-ttu-id="e63a6-129">A fastruktúrában válassza ki a Tranzakciók pontot.</span><span class="sxs-lookup"><span data-stu-id="e63a6-129">In the tree, select 'Transactions'.</span></span>
11. <span data-ttu-id="e63a6-130">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="e63a6-130">Click Bind.</span></span>
12. <span data-ttu-id="e63a6-131">A fában bontsa ki a „Payments= Transactions” elemet.</span><span class="sxs-lookup"><span data-stu-id="e63a6-131">In the tree, expand 'Payments= Transactions'.</span></span>
13. <span data-ttu-id="e63a6-132">A fában bontsa ki a „Payments= Transactions\Creditor” elemet.</span><span class="sxs-lookup"><span data-stu-id="e63a6-132">In the tree, expand 'Payments= Transactions\Creditor'.</span></span>
14. <span data-ttu-id="e63a6-133">A fában bontsa ki a „Payments= Transactions\Creditor\Account” elemet.</span><span class="sxs-lookup"><span data-stu-id="e63a6-133">In the tree, expand 'Payments= Transactions\Creditor\Account'.</span></span>
15. <span data-ttu-id="e63a6-134">A fán válassza ki „Kifizetések = Transactions\Creditor\Account\Currency code(Currency)” pontot.</span><span class="sxs-lookup"><span data-stu-id="e63a6-134">In the tree, select 'Payments= Transactions\Creditor\Account\Currency code(Currency)'.</span></span>
16. <span data-ttu-id="e63a6-135">A fában bontsa ki a „Transactions\vendBankAccountInTransactionCompany()” elemet.</span><span class="sxs-lookup"><span data-stu-id="e63a6-135">In the tree, expand 'Transactions\vendBankAccountInTransactionCompany()'.</span></span>
17. <span data-ttu-id="e63a6-136">A fán válassza ki „Transactions\vendBankAccountInTransactionCompany()\Currency(CurrencyCode)” pontot.</span><span class="sxs-lookup"><span data-stu-id="e63a6-136">In the tree, select 'Transactions\vendBankAccountInTransactionCompany()\Currency(CurrencyCode)'.</span></span>
18. <span data-ttu-id="e63a6-137">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="e63a6-137">Click Bind.</span></span>
19. <span data-ttu-id="e63a6-138">A fán válassza ki „Kifizetések = Transactions\Creditor\Account\IBAN code(IBAN)” pontot.</span><span class="sxs-lookup"><span data-stu-id="e63a6-138">In the tree, select 'Payments= Transactions\Creditor\Account\IBAN code(IBAN)'.</span></span>
20. <span data-ttu-id="e63a6-139">A fában válassza ki a „Transactions\vendBankAccountInTransactionCompany()\IBAN(BankIBAN)” elemet.</span><span class="sxs-lookup"><span data-stu-id="e63a6-139">In the tree, select 'Transactions\vendBankAccountInTransactionCompany()\IBAN(BankIBAN)'.</span></span>
21. <span data-ttu-id="e63a6-140">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="e63a6-140">Click Bind.</span></span>
22. <span data-ttu-id="e63a6-141">A fán válassza ki „Kifizetések = Transactions\Creditor\Account\Number” pontot.</span><span class="sxs-lookup"><span data-stu-id="e63a6-141">In the tree, select 'Payments= Transactions\Creditor\Account\Number'.</span></span>
23. <span data-ttu-id="e63a6-142">A fában válassza ki a „Transactions\vendBankAccountInTransactionCompany()\Bank account number(AccountNum)” elemet.</span><span class="sxs-lookup"><span data-stu-id="e63a6-142">In the tree, select 'Transactions\vendBankAccountInTransactionCompany()\Bank account number(AccountNum)'.</span></span>
24. <span data-ttu-id="e63a6-143">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="e63a6-143">Click Bind.</span></span>
25. <span data-ttu-id="e63a6-144">A fában bontsa ki a „Payments= Transactions\Creditor\Agent” elemet.</span><span class="sxs-lookup"><span data-stu-id="e63a6-144">In the tree, expand 'Payments= Transactions\Creditor\Agent'.</span></span>
26. <span data-ttu-id="e63a6-145">A fán válassza ki „Kifizetések = Transactions\Creditor\Agent\Name” pontot.</span><span class="sxs-lookup"><span data-stu-id="e63a6-145">In the tree, select 'Payments= Transactions\Creditor\Agent\Name'.</span></span>
27. <span data-ttu-id="e63a6-146">A fában válassza ki a „Transactions\vendBankAccountInTransactionCompany()\Name” elemet.</span><span class="sxs-lookup"><span data-stu-id="e63a6-146">In the tree, select 'Transactions\vendBankAccountInTransactionCompany()\Name'.</span></span>
28. <span data-ttu-id="e63a6-147">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="e63a6-147">Click Bind.</span></span>
29. <span data-ttu-id="e63a6-148">A fán válassza ki „Kifizetések = Transactions\Creditor\Agent\Routing number(RoutingNumber)” pontot.</span><span class="sxs-lookup"><span data-stu-id="e63a6-148">In the tree, select 'Payments= Transactions\Creditor\Agent\Routing number(RoutingNumber)'.</span></span>
30. <span data-ttu-id="e63a6-149">A fában válassza ki a „Transactions\vendBankAccountInTransactionCompany()\Routing number(RegistrationNum)” elemet.</span><span class="sxs-lookup"><span data-stu-id="e63a6-149">In the tree, select 'Transactions\vendBankAccountInTransactionCompany()\Routing number(RegistrationNum)'.</span></span>
31. <span data-ttu-id="e63a6-150">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="e63a6-150">Click Bind.</span></span>
32. <span data-ttu-id="e63a6-151">A fán válassza ki „Kifizetések = Transactions\Creditor\Agent\SWIFT code(SWIFT)” pontot.</span><span class="sxs-lookup"><span data-stu-id="e63a6-151">In the tree, select 'Payments= Transactions\Creditor\Agent\SWIFT code(SWIFT)'.</span></span>
33. <span data-ttu-id="e63a6-152">A fán válassza ki „Transactions\vendBankAccountInTransactionCompany()\SWIFT code(SWIFTNo)” pontot.</span><span class="sxs-lookup"><span data-stu-id="e63a6-152">In the tree, select 'Transactions\vendBankAccountInTransactionCompany()\SWIFT code(SWIFTNo)'.</span></span>
34. <span data-ttu-id="e63a6-153">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="e63a6-153">Click Bind.</span></span>
35. <span data-ttu-id="e63a6-154">A fán válassza ki „Kifizetések = Transactions\Creditor\Name” pontot.</span><span class="sxs-lookup"><span data-stu-id="e63a6-154">In the tree, select 'Payments= Transactions\Creditor\Name'.</span></span>
36. <span data-ttu-id="e63a6-155">A fában bontsa ki a „Transactions\findVendTable()” elemet.</span><span class="sxs-lookup"><span data-stu-id="e63a6-155">In the tree, expand 'Transactions\findVendTable()'.</span></span>
37. <span data-ttu-id="e63a6-156">A fastruktúrában válassza ki a „Tranzakciók\findVendTable()ame()” elemet.</span><span class="sxs-lookup"><span data-stu-id="e63a6-156">In the tree, select 'Transactions\findVendTable()\name()'.</span></span>
38. <span data-ttu-id="e63a6-157">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="e63a6-157">Click Bind.</span></span>
39. <span data-ttu-id="e63a6-158">A fán válassza ki „Kifizetések = Transactions\Currency code(Currency)” pontot.</span><span class="sxs-lookup"><span data-stu-id="e63a6-158">In the tree, select 'Payments= Transactions\Currency code(Currency)'.</span></span>
40. <span data-ttu-id="e63a6-159">A fában bontsa ki a „Transactions\>Relations” elemet.</span><span class="sxs-lookup"><span data-stu-id="e63a6-159">In the tree, expand 'Transactions\>Relations'.</span></span>
41. <span data-ttu-id="e63a6-160">A fán bontsa ki a „Transactions\>Relations\Currency table(Currency)” pontot.</span><span class="sxs-lookup"><span data-stu-id="e63a6-160">In the tree, expand 'Transactions\>Relations\Currency table(Currency)'.</span></span>
42. <span data-ttu-id="e63a6-161">A fán válassza ki a „Transactions\>Relations\Currency table(Currency)\Currency code(CurrencyCodeISO)” pontot.</span><span class="sxs-lookup"><span data-stu-id="e63a6-161">In the tree, select 'Transactions\>Relations\Currency table(Currency)\Currency code(CurrencyCodeISO)'.</span></span>
43. <span data-ttu-id="e63a6-162">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="e63a6-162">Click Bind.</span></span>
44. <span data-ttu-id="e63a6-163">A fában bontsa ki a „Payments= Transactions\Debtor” elemet.</span><span class="sxs-lookup"><span data-stu-id="e63a6-163">In the tree, expand 'Payments= Transactions\Debtor'.</span></span>
45. <span data-ttu-id="e63a6-164">A fában bontsa ki a „Payments= Transactions\Debtor\Account” elemet.</span><span class="sxs-lookup"><span data-stu-id="e63a6-164">In the tree, expand 'Payments= Transactions\Debtor\Account'.</span></span>
46. <span data-ttu-id="e63a6-165">A fán válassza ki „Kifizetések = Transactions\Debtor\Account\Currency code(Currency)” pontot.</span><span class="sxs-lookup"><span data-stu-id="e63a6-165">In the tree, select 'Payments= Transactions\Debtor\Account\Currency code(Currency)'.</span></span>
47. <span data-ttu-id="e63a6-166">A fastruktúrában válassza ki a „Bank Account(BankAccount)” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e63a6-166">In the tree, select 'Bank Account(BankAccount)'.</span></span>
48. <span data-ttu-id="e63a6-167">A fastruktúrában bontsa ki a „Bank Account(BankAccount)” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e63a6-167">In the tree, expand 'Bank Account(BankAccount)'.</span></span>
49. <span data-ttu-id="e63a6-168">A fán válassza ki a „Bank Account(BankAccount)\Currency(CurrencyCode)” pontot.</span><span class="sxs-lookup"><span data-stu-id="e63a6-168">In the tree, select 'Bank Account(BankAccount)\Currency(CurrencyCode)'.</span></span>
50. <span data-ttu-id="e63a6-169">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="e63a6-169">Click Bind.</span></span>
51. <span data-ttu-id="e63a6-170">A fastruktúrában válassza ki a „Bank Account(BankAccount)\IBAN” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e63a6-170">In the tree, select 'Bank Account(BankAccount)\IBAN'.</span></span>
52. <span data-ttu-id="e63a6-171">A fán válassza ki „Kifizetések = Transactions\Debtor\Account\IBAN code(IBAN)” pontot.</span><span class="sxs-lookup"><span data-stu-id="e63a6-171">In the tree, select 'Payments= Transactions\Debtor\Account\IBAN code(IBAN)'.</span></span>
53. <span data-ttu-id="e63a6-172">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="e63a6-172">Click Bind.</span></span>
54. <span data-ttu-id="e63a6-173">A fán válassza ki „Kifizetések = Transactions\Debtor\Account\Number” pontot.</span><span class="sxs-lookup"><span data-stu-id="e63a6-173">In the tree, select 'Payments= Transactions\Debtor\Account\Number'.</span></span>
55. <span data-ttu-id="e63a6-174">A fán válassza ki a „Bank Account(BankAccount)\Bank account number(AccountNum)” pontot.</span><span class="sxs-lookup"><span data-stu-id="e63a6-174">In the tree, select 'Bank Account(BankAccount)\Bank account number(AccountNum)'.</span></span>
56. <span data-ttu-id="e63a6-175">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="e63a6-175">Click Bind.</span></span>
57. <span data-ttu-id="e63a6-176">A fában bontsa ki a „Payments= Transactions\Debtor\Agent” elemet.</span><span class="sxs-lookup"><span data-stu-id="e63a6-176">In the tree, expand 'Payments= Transactions\Debtor\Agent'.</span></span>
58. <span data-ttu-id="e63a6-177">A fán válassza ki „Kifizetések = Transactions\Debtor\Agent\Name” pontot.</span><span class="sxs-lookup"><span data-stu-id="e63a6-177">In the tree, select 'Payments= Transactions\Debtor\Agent\Name'.</span></span>
59. <span data-ttu-id="e63a6-178">A fastruktúrában válassza ki a „Bank Account(BankAccount)\Name” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e63a6-178">In the tree, select 'Bank Account(BankAccount)\Name'.</span></span>
60. <span data-ttu-id="e63a6-179">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="e63a6-179">Click Bind.</span></span>
61. <span data-ttu-id="e63a6-180">A fán válassza ki „Kifizetések = Transactions\Debtor\Agent\Routing number(RoutingNumber)” pontot.</span><span class="sxs-lookup"><span data-stu-id="e63a6-180">In the tree, select 'Payments= Transactions\Debtor\Agent\Routing number(RoutingNumber)'.</span></span>
62. <span data-ttu-id="e63a6-181">A fán válassza ki a „Bank Account(BankAccount)\Routing number(RegistrationNum)” pontot.</span><span class="sxs-lookup"><span data-stu-id="e63a6-181">In the tree, select 'Bank Account(BankAccount)\Routing number(RegistrationNum)'.</span></span>
63. <span data-ttu-id="e63a6-182">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="e63a6-182">Click Bind.</span></span>
64. <span data-ttu-id="e63a6-183">A fán válassza ki „Kifizetések = Transactions\Debtor\Agent\SWIFT code(SWIFT)” pontot.</span><span class="sxs-lookup"><span data-stu-id="e63a6-183">In the tree, select 'Payments= Transactions\Debtor\Agent\SWIFT code(SWIFT)'.</span></span>
65. <span data-ttu-id="e63a6-184">A fán válassza ki a „Bank Account(BankAccount)\SWIFT code(SWIFTNo)” pontot.</span><span class="sxs-lookup"><span data-stu-id="e63a6-184">In the tree, select 'Bank Account(BankAccount)\SWIFT code(SWIFTNo)'.</span></span>
66. <span data-ttu-id="e63a6-185">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="e63a6-185">Click Bind.</span></span>
67. <span data-ttu-id="e63a6-186">A fán válassza ki „Kifizetések = Transactions\Debtor\Name” pontot.</span><span class="sxs-lookup"><span data-stu-id="e63a6-186">In the tree, select 'Payments= Transactions\Debtor\Name'.</span></span>
68. <span data-ttu-id="e63a6-187">A fán válassza ki a „Company information(Company)” pontot.</span><span class="sxs-lookup"><span data-stu-id="e63a6-187">In the tree, select 'Company information(Company)'.</span></span>
69. <span data-ttu-id="e63a6-188">A fán bontsa ki a „Company information(Company)” pontot.</span><span class="sxs-lookup"><span data-stu-id="e63a6-188">In the tree, expand 'Company information(Company)'.</span></span>
70. <span data-ttu-id="e63a6-189">A fán válassza ki a „Company information(Company)\Name” pontot.</span><span class="sxs-lookup"><span data-stu-id="e63a6-189">In the tree, select 'Company information(Company)\Name'.</span></span>
71. <span data-ttu-id="e63a6-190">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="e63a6-190">Click Bind.</span></span>
72. <span data-ttu-id="e63a6-191">A fán válassza ki „Kifizetések = Transactions\Description” pontot.</span><span class="sxs-lookup"><span data-stu-id="e63a6-191">In the tree, select 'Payments= Transactions\Description'.</span></span>
73. <span data-ttu-id="e63a6-192">A fán válassza ki „Transactions\Description(Txt)” pontot.</span><span class="sxs-lookup"><span data-stu-id="e63a6-192">In the tree, select 'Transactions\Description(Txt)'.</span></span>
74. <span data-ttu-id="e63a6-193">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="e63a6-193">Click Bind.</span></span>
75. <span data-ttu-id="e63a6-194">A fán válassza ki a „Payments= Transactions\End to end identification code(End2EndID)” pontot.</span><span class="sxs-lookup"><span data-stu-id="e63a6-194">In the tree, select 'Payments= Transactions\End to end identification code(End2EndID)'.</span></span>
76. <span data-ttu-id="e63a6-195">A fastruktúrában válassza ki a „Transactions\$EndToEndID” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e63a6-195">In the tree, select 'Transactions\$EndToEndID'.</span></span>
77. <span data-ttu-id="e63a6-196">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="e63a6-196">Click Bind.</span></span>
78. <span data-ttu-id="e63a6-197">A fán válassza ki a „Payments= Transactions\Instructed amount(InstructedAmount)” pontot.</span><span class="sxs-lookup"><span data-stu-id="e63a6-197">In the tree, select 'Payments= Transactions\Instructed amount(InstructedAmount)'.</span></span>
79. <span data-ttu-id="e63a6-198">A fastruktúrában válassza ki a „Transactions\$Amount” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e63a6-198">In the tree, select 'Transactions\$Amount'.</span></span>
80. <span data-ttu-id="e63a6-199">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="e63a6-199">Click Bind.</span></span>
81. <span data-ttu-id="e63a6-200">A fán válassza ki a „Payments= Transactions\Transaction date(TransactionDate)” pontot.</span><span class="sxs-lookup"><span data-stu-id="e63a6-200">In the tree, select 'Payments= Transactions\Transaction date(TransactionDate)'.</span></span>
82. <span data-ttu-id="e63a6-201">A fán válassza ki „Transactions\Date(TransDate)” pontot.</span><span class="sxs-lookup"><span data-stu-id="e63a6-201">In the tree, select 'Transactions\Date(TransDate)'.</span></span>
83. <span data-ttu-id="e63a6-202">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="e63a6-202">Click Bind.</span></span>

## <a name="validate-created-mapping"></a><span data-ttu-id="e63a6-203">Létrehozott leképezés validálása</span><span class="sxs-lookup"><span data-stu-id="e63a6-203">Validate created mapping</span></span>
1. <span data-ttu-id="e63a6-204">Kattintson az Érvényesítés gombra.</span><span class="sxs-lookup"><span data-stu-id="e63a6-204">Click Validate.</span></span>
    * <span data-ttu-id="e63a6-205">Ellenőrizze az új hozzárendelést annak a biztosítására, hogy az összes kötés rendben legyen.</span><span class="sxs-lookup"><span data-stu-id="e63a6-205">Validate the new mapping to ensure that all bindings are okay.</span></span>  
2. <span data-ttu-id="e63a6-206">Kattintson a nyílra vagy zárja be a hibalista szakaszt.</span><span class="sxs-lookup"><span data-stu-id="e63a6-206">Click the arrow to expand or collapse the Error List section.</span></span>
3. <span data-ttu-id="e63a6-207">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="e63a6-207">Click Save.</span></span>
4. <span data-ttu-id="e63a6-208">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="e63a6-208">Close the page.</span></span>
5. <span data-ttu-id="e63a6-209">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="e63a6-209">Close the page.</span></span>
6. <span data-ttu-id="e63a6-210">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="e63a6-210">Close the page.</span></span>

## <a name="change-the-status-of-the-current-version-of-model-configuration"></a><span data-ttu-id="e63a6-211">A modellkonfiguráció aktuális verziójának állapotmódosítása</span><span class="sxs-lookup"><span data-stu-id="e63a6-211">Change the status of the current version of model configuration</span></span>
1. <span data-ttu-id="e63a6-212">Kattintson az Állapot módosítása elemre.</span><span class="sxs-lookup"><span data-stu-id="e63a6-212">Click Change status.</span></span>
    * <span data-ttu-id="e63a6-213">Módosítsa a tervezett modellkonfiguráció állapotát – Vázlat állapotról Teljesített állapotra annak érdekében, hogy rendelkezésre álljon a kifizetési formátum tervezéséhez.</span><span class="sxs-lookup"><span data-stu-id="e63a6-213">Change the status of designed model configuration – from Draft to Completed to make it available for payment format design.</span></span>  
2. <span data-ttu-id="e63a6-214">Kattintson a Befejezés gombra.</span><span class="sxs-lookup"><span data-stu-id="e63a6-214">Click Complete.</span></span>
    * <span data-ttu-id="e63a6-215">Válassza a Kész lehetőséget</span><span class="sxs-lookup"><span data-stu-id="e63a6-215">Select Complete.</span></span>  
3. <span data-ttu-id="e63a6-216">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="e63a6-216">In the Description field, type a value.</span></span>
    * <span data-ttu-id="e63a6-217">Például: „1-es verzió”.</span><span class="sxs-lookup"><span data-stu-id="e63a6-217">For example, 'version 1'.</span></span>  
4. <span data-ttu-id="e63a6-218">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="e63a6-218">Click OK.</span></span>
5. <span data-ttu-id="e63a6-219">Válassza ki az aktuális konfiguráció teljesített verzióját.</span><span class="sxs-lookup"><span data-stu-id="e63a6-219">Select the completed version of the current configuration.</span></span>
    * <span data-ttu-id="e63a6-220">Fontos, hogy a létrehozott konfiguráció teljesített 1-es verzióként lesz mentve.</span><span class="sxs-lookup"><span data-stu-id="e63a6-220">Note that the created configuration is saved as completed version 1.</span></span>  

