---
title: ER - tartományspecifikus adatmodell kialakítása
description: A következő lépések leírják, hogy egy Rendszergazda vagy Elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználó miként hozhat létre egy új Elektronikus jelentés (ER) konfigurációt, amely tartalmazza az Elektronikus fizetési dokumentumok adatmodelljét.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, ERDataModelDesigner, ERDataModelContentsItemCreationDialog, ERDataContainerDescriptorReferenceSwitchDialog
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0debb7276c4f3e41c2e85ce6bc63b8df5bc159f8
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1551525"
---
# <a name="er-design-domain-specific-data-model"></a><span data-ttu-id="dc038-103">ER - tartományspecifikus adatmodell kialakítása</span><span class="sxs-lookup"><span data-stu-id="dc038-103">ER Design domain specific data model</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="dc038-104">A következő lépések leírják, hogy egy Rendszergazda vagy Elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználó miként hozhat létre egy új Elektronikus jelentés (ER) konfigurációt, amely tartalmazza az Elektronikus fizetési dokumentumok adatmodelljét.</span><span class="sxs-lookup"><span data-stu-id="dc038-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can create a new Electronic reporting (ER) configuration that contains a data model for electronic payment documents.</span></span> <span data-ttu-id="dc038-105">Ezt az adatmodellt később adatforrásként használja a fizetési dokumentumok formátumának létrehozásakor.</span><span class="sxs-lookup"><span data-stu-id="dc038-105">This data model will later be used as a data source when you create the format of the payment documents.</span></span>



<span data-ttu-id="dc038-106">Ebben a példában a mintavállalatra, Litware-ra, Inc.-ra vonatkozóan létrehoz egy konfigurációs szolgáltatót. Ezeket a lépéseket a vállalatok között megosztott ER konfigurációkként hajthatók végre az egyes vállalatoknál.</span><span class="sxs-lookup"><span data-stu-id="dc038-106">In this example, you will create a configuration for sample company, Litware, Inc. These steps can be performed in any company as ER configurations are shared among companies.</span></span> <span data-ttu-id="dc038-107">Hajtsa végre az alábbi lépéseket: Először hajtsa végre a „Konfiguráció szolgáltatói létrehozása és aktívként történő megjelölése” eljárás lépéseit.</span><span class="sxs-lookup"><span data-stu-id="dc038-107">To complete these steps, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span>

1. <span data-ttu-id="dc038-108">Ugorjon a Szervezeti adminisztráció > Munkaterületek > Elektronikus jelentés pontra.</span><span class="sxs-lookup"><span data-stu-id="dc038-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="dc038-109">Válassza ki a konfigurációs szolgáltatót a Litware, Inc. mintavállalatra vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="dc038-109">Select the configuration provider for sample company, ‘Litware, Inc.’</span></span> <span data-ttu-id="dc038-110">Ha nem látja a konfigurációs szolgáltatót, először el kell végeznie a „Konfigurációszolgáltató létrehozása, és megjelölés aktívként” eljárásban szereplő lépéseket.</span><span class="sxs-lookup"><span data-stu-id="dc038-110">If you don’t see this configuration provider, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span>  
2. <span data-ttu-id="dc038-111">Kattintson a Jelentéskészítés konfigurációi lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="dc038-111">Click Reporting configurations.</span></span>
    * <span data-ttu-id="dc038-112">Létrehoz egy konfigurációt, amely tartalmazza az elektronikus fizetési dokumentumok adatmodelljét.</span><span class="sxs-lookup"><span data-stu-id="dc038-112">You will create a configuration that contains a data model for electronic payment documents.</span></span> <span data-ttu-id="dc038-113">Ezt az adatmodellt később használja majd adatforrásként a fizetési dokumentumok formátumának létrehozásakor.</span><span class="sxs-lookup"><span data-stu-id="dc038-113">This data model will be used later as a data source when you create the format for the payment documents.</span></span>  

## <a name="create-a-new-data-model-configuration"></a><span data-ttu-id="dc038-114">Új adatmodell-konfiguráció létrehozása</span><span class="sxs-lookup"><span data-stu-id="dc038-114">Create a new data model configuration</span></span>
1. <span data-ttu-id="dc038-115">A Konfiguráció létrehozása gombra kattintva megnyithatja a legördülő párbeszédablakot.</span><span class="sxs-lookup"><span data-stu-id="dc038-115">Click Create configuration to open the drop dialog.</span></span>
2. <span data-ttu-id="dc038-116">A név mezőben írja be a „Fizetések (egyszerűsített modelladatok)” szöveget.</span><span class="sxs-lookup"><span data-stu-id="dc038-116">In the Name field, type 'Payments (simplified model)'.</span></span>
    * <span data-ttu-id="dc038-117">Kifizetések (egyszerűsített modell)</span><span class="sxs-lookup"><span data-stu-id="dc038-117">Payments (simplified model)</span></span>  
3. <span data-ttu-id="dc038-118">A Leírás mezőben írja be a „Fizetés modell konfigurációja” szöveget.</span><span class="sxs-lookup"><span data-stu-id="dc038-118">In the Description field, type 'Payment model configuration'.</span></span>
    * <span data-ttu-id="dc038-119">Fizetési modell konfigurációja</span><span class="sxs-lookup"><span data-stu-id="dc038-119">Payment model configuration</span></span>  
    * <span data-ttu-id="dc038-120">Az aktív konfigurációs szolgáltató automatikusan megjelenik itt.</span><span class="sxs-lookup"><span data-stu-id="dc038-120">The active configuration provider is automatically entered here.</span></span> <span data-ttu-id="dc038-121">Ez a szolgáltató tartja majd karban ezt a konfigurációt.</span><span class="sxs-lookup"><span data-stu-id="dc038-121">This provider will be able to maintain this configuration.</span></span> <span data-ttu-id="dc038-122">Más szolgáltatók is használhatják ezt a konfigurációt, de nem tudják majd karbantartani.</span><span class="sxs-lookup"><span data-stu-id="dc038-122">Other providers can use this configuration, but will not be able to maintain it.</span></span>  
4. <span data-ttu-id="dc038-123">Kattintson a „Konfiguráció létrehozása” gombra a konfigurációlétrehozási feladat befejezéséhez</span><span class="sxs-lookup"><span data-stu-id="dc038-123">Click ‘Create configuration’ button to complete the configuration creation task</span></span>

## <a name="create-a-data-model"></a><span data-ttu-id="dc038-124">Adatmodell létrehozása</span><span class="sxs-lookup"><span data-stu-id="dc038-124">Create a data model</span></span>
    * <span data-ttu-id="dc038-125">Új adatmodellt hoz létre a kiválasztott konfigurációhoz.</span><span class="sxs-lookup"><span data-stu-id="dc038-125">You're creating a new data model for the selected configuration.</span></span> <span data-ttu-id="dc038-126">Ennek a konfigurációverziónak az állapota Vázlat lesz.</span><span class="sxs-lookup"><span data-stu-id="dc038-126">This configuration version will have a status of Draft.</span></span>  
1. <span data-ttu-id="dc038-127">Kattintson a Tervező pontra.</span><span class="sxs-lookup"><span data-stu-id="dc038-127">Click Designer.</span></span>

## <a name="define-the-structure-of-a-party-participating-in-a-payment-process"></a><span data-ttu-id="dc038-128">A kifizetési folyamatban részt vevő fél szerkezetének meghatározása</span><span class="sxs-lookup"><span data-stu-id="dc038-128">Define the structure of a party participating in a payment process</span></span>
1. <span data-ttu-id="dc038-129">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="dc038-129">Click New to open the drop dialog.</span></span>
2. <span data-ttu-id="dc038-130">A Név mezőbe írja be a következőt: „Fél”.</span><span class="sxs-lookup"><span data-stu-id="dc038-130">In the Name field, type 'Party'.</span></span>
    * <span data-ttu-id="dc038-131">Fél</span><span class="sxs-lookup"><span data-stu-id="dc038-131">Party</span></span>  
3. <span data-ttu-id="dc038-132">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="dc038-132">Click Add.</span></span>
4. <span data-ttu-id="dc038-133">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="dc038-133">Click New to open the drop dialog.</span></span>
5. <span data-ttu-id="dc038-134">A Név mezőbe írja be a „Név” szöveget.</span><span class="sxs-lookup"><span data-stu-id="dc038-134">In the Name field, type 'Name'.</span></span>
    * <span data-ttu-id="dc038-135">Név</span><span class="sxs-lookup"><span data-stu-id="dc038-135">Name</span></span>  
6. <span data-ttu-id="dc038-136">A Cikktípus mezőben válassza ki a „Karakterlánc” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="dc038-136">In the Item type field, select 'String'.</span></span>
7. <span data-ttu-id="dc038-137">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="dc038-137">Click Add.</span></span>
8. <span data-ttu-id="dc038-138">A Keresés mezőbe írja be a következőt: „Fél”.</span><span class="sxs-lookup"><span data-stu-id="dc038-138">In the Find field, type 'Party'.</span></span>
    * <span data-ttu-id="dc038-139">Fél</span><span class="sxs-lookup"><span data-stu-id="dc038-139">Party</span></span>  
9. <span data-ttu-id="dc038-140">Kattintson az Előző keresése lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="dc038-140">Click Find previous.</span></span>

## <a name="define-the-bank-structure-for-this-model"></a><span data-ttu-id="dc038-141">Modell bankstruktúrájának meghatározása</span><span class="sxs-lookup"><span data-stu-id="dc038-141">Define the bank structure for this model</span></span>
1. <span data-ttu-id="dc038-142">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="dc038-142">Click New to open the drop dialog.</span></span>
2. <span data-ttu-id="dc038-143">A név mezőbe írja be az „Ügynök”.</span><span class="sxs-lookup"><span data-stu-id="dc038-143">In the Name field, type 'Agent'.</span></span>
    * <span data-ttu-id="dc038-144">Ügynök</span><span class="sxs-lookup"><span data-stu-id="dc038-144">Agent</span></span>  
3. <span data-ttu-id="dc038-145">A Cikktípus mezőben válassza ki a „Rekord” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="dc038-145">In the Item type field, select 'Record'.</span></span>
4. <span data-ttu-id="dc038-146">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="dc038-146">Click Add.</span></span>
5. <span data-ttu-id="dc038-147">A Leírás mezőben adja meg a „Pénzintézet (pl. bank), amely számlát tart fenn a fél (kötelezett/hitelező) részére.” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="dc038-147">In the Description field, enter 'Financial institution (for instance, a bank) servicing an account for the party (debtor/creditor).'.</span></span>
    * <span data-ttu-id="dc038-148">Pénzintézet (pl. bank), amely számlát tart fenn a fél (kötelezett/hitelező) részére.</span><span class="sxs-lookup"><span data-stu-id="dc038-148">Financial institution (for instance, a bank) servicing an account for the party (debtor/creditor).</span></span>  
6. <span data-ttu-id="dc038-149">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="dc038-149">Click New to open the drop dialog.</span></span>
7. <span data-ttu-id="dc038-150">A Név mezőbe írja be a „Név” szöveget.</span><span class="sxs-lookup"><span data-stu-id="dc038-150">In the Name field, type 'Name'.</span></span>
    * <span data-ttu-id="dc038-151">Név</span><span class="sxs-lookup"><span data-stu-id="dc038-151">Name</span></span>  
8. <span data-ttu-id="dc038-152">A Cikktípus mezőben válassza ki a „Karakterlánc” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="dc038-152">In the Item type field, select 'String'.</span></span>
9. <span data-ttu-id="dc038-153">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="dc038-153">Click Add.</span></span>
10. <span data-ttu-id="dc038-154">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="dc038-154">Click New to open the drop dialog.</span></span>
11. <span data-ttu-id="dc038-155">A Név mezőbe írja be a „SWIFT” szöveget.</span><span class="sxs-lookup"><span data-stu-id="dc038-155">In the Name field, type 'SWIFT'.</span></span>
    * <span data-ttu-id="dc038-156">SWIFT</span><span class="sxs-lookup"><span data-stu-id="dc038-156">SWIFT</span></span>  
12. <span data-ttu-id="dc038-157">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="dc038-157">Click Add.</span></span>
13. <span data-ttu-id="dc038-158">A Leírás mezőben adja meg a következőt: „Bankazonosító kód”.</span><span class="sxs-lookup"><span data-stu-id="dc038-158">In the Description field, enter 'Bank identification code'.</span></span>
    * <span data-ttu-id="dc038-159">Bankazonosító kód</span><span class="sxs-lookup"><span data-stu-id="dc038-159">Bank identification code</span></span>  
14. <span data-ttu-id="dc038-160">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="dc038-160">Click New to open the drop dialog.</span></span>
15. <span data-ttu-id="dc038-161">A Név mezőbe írja be a „RoutingNumber” szöveget.</span><span class="sxs-lookup"><span data-stu-id="dc038-161">In the Name field, type 'RoutingNumber'.</span></span>
    * <span data-ttu-id="dc038-162">Útvonalszám</span><span class="sxs-lookup"><span data-stu-id="dc038-162">RoutingNumber</span></span>  
16. <span data-ttu-id="dc038-163">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="dc038-163">Click Add.</span></span>
17. <span data-ttu-id="dc038-164">A Leírás mezőben adja meg a következőt: „Regisztrációs azonosító száma”.</span><span class="sxs-lookup"><span data-stu-id="dc038-164">In the Description field, enter 'Routing number'.</span></span>
    * <span data-ttu-id="dc038-165">Regisztrációs azonosító száma</span><span class="sxs-lookup"><span data-stu-id="dc038-165">Routing number</span></span>  
18. <span data-ttu-id="dc038-166">Kattintson az Előző keresése lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="dc038-166">Click Find previous.</span></span>

## <a name="define-the-bank-account-structure-for-this-model"></a><span data-ttu-id="dc038-167">Modell bankszámla-struktúrájának meghatározása</span><span class="sxs-lookup"><span data-stu-id="dc038-167">Define the bank account structure for this model</span></span>
1. <span data-ttu-id="dc038-168">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="dc038-168">Click New to open the drop dialog.</span></span>
2. <span data-ttu-id="dc038-169">A Név mezőbe írja be a „Számla” szöveget.</span><span class="sxs-lookup"><span data-stu-id="dc038-169">In the Name field, type 'Account'.</span></span>
    * <span data-ttu-id="dc038-170">Könyvelési számla</span><span class="sxs-lookup"><span data-stu-id="dc038-170">Account</span></span>  
3. <span data-ttu-id="dc038-171">A Cikktípus mezőben válassza ki a „Rekord” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="dc038-171">In the Item type field, select 'Record'.</span></span>
4. <span data-ttu-id="dc038-172">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="dc038-172">Click Add.</span></span>
5. <span data-ttu-id="dc038-173">A Leírás mezőben adja meg a következőt: „A fél pénzintézetben (például a bank) vezetett számlájának azonosítása.”.</span><span class="sxs-lookup"><span data-stu-id="dc038-173">In the Description field, enter 'Identification of an account of a party in a financial institution (for instance, a bank).'.</span></span>
    * <span data-ttu-id="dc038-174">A fél pénzintézetben (például a bank) vezetett számlájának azonosítása.</span><span class="sxs-lookup"><span data-stu-id="dc038-174">Identification of an account of a party in a financial institution (for instance, a bank).</span></span>  
6. <span data-ttu-id="dc038-175">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="dc038-175">Click New to open the drop dialog.</span></span>
7. <span data-ttu-id="dc038-176">A név mezőbe írja be a „Pénznem” szöveget.</span><span class="sxs-lookup"><span data-stu-id="dc038-176">In the Name field, type 'Currency'.</span></span>
    * <span data-ttu-id="dc038-177">Pénznem</span><span class="sxs-lookup"><span data-stu-id="dc038-177">Currency</span></span>  
8. <span data-ttu-id="dc038-178">A Cikktípus mezőben válassza ki a „Karakterlánc” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="dc038-178">In the Item type field, select 'String'.</span></span>
9. <span data-ttu-id="dc038-179">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="dc038-179">Click Add.</span></span>
10. <span data-ttu-id="dc038-180">A Leírás mezőben adja meg a következőt: „Pénznemkód”.</span><span class="sxs-lookup"><span data-stu-id="dc038-180">In the Description field, enter 'Currency code'.</span></span>
    * <span data-ttu-id="dc038-181">Pénznemkód</span><span class="sxs-lookup"><span data-stu-id="dc038-181">Currency code</span></span>  
11. <span data-ttu-id="dc038-182">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="dc038-182">Click New to open the drop dialog.</span></span>
12. <span data-ttu-id="dc038-183">A Név mezőbe írja be a „Szám” szöveget.</span><span class="sxs-lookup"><span data-stu-id="dc038-183">In the Name field, type 'Number'.</span></span>
    * <span data-ttu-id="dc038-184">Szám</span><span class="sxs-lookup"><span data-stu-id="dc038-184">Number</span></span>  
13. <span data-ttu-id="dc038-185">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="dc038-185">Click Add.</span></span>
14. <span data-ttu-id="dc038-186">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="dc038-186">Click New to open the drop dialog.</span></span>
15. <span data-ttu-id="dc038-187">A Név mezőbe írja be az „IBAN” szöveget.</span><span class="sxs-lookup"><span data-stu-id="dc038-187">In the Name field, type 'IBAN'.</span></span>
    * <span data-ttu-id="dc038-188">IBAN</span><span class="sxs-lookup"><span data-stu-id="dc038-188">IBAN</span></span>  
16. <span data-ttu-id="dc038-189">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="dc038-189">Click Add.</span></span>
17. <span data-ttu-id="dc038-190">A Leírás mezőben adja meg a következőt: „Nemzetközi bankszámlaszám”.</span><span class="sxs-lookup"><span data-stu-id="dc038-190">In the Description field, enter 'International bank account number'.</span></span>
    * <span data-ttu-id="dc038-191">Nemzetközi bankszámlaszám</span><span class="sxs-lookup"><span data-stu-id="dc038-191">International bank account number</span></span>  

## <a name="define-the-payment-message-structure-for-credit-transfer-payment-type"></a><span data-ttu-id="dc038-192">A fizetési üzenetstruktúra meghatározása a jóváírási átmozgatás fizetési típusra</span><span class="sxs-lookup"><span data-stu-id="dc038-192">Define the payment message structure for credit transfer payment type</span></span>
1. <span data-ttu-id="dc038-193">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="dc038-193">Click New to open the drop dialog.</span></span>
2. <span data-ttu-id="dc038-194">Az Új csomópontként mezőben adja meg a következőt: „Modellgyökér”.</span><span class="sxs-lookup"><span data-stu-id="dc038-194">In the New node as a field, enter 'Model root'.</span></span>
3. <span data-ttu-id="dc038-195">A Név mezőbe írja be a „CustomerCreditTransferInitiation” szöveget.</span><span class="sxs-lookup"><span data-stu-id="dc038-195">In the Name field, type 'CustomerCreditTransferInitiation'.</span></span>
    * <span data-ttu-id="dc038-196">CustomerCreditTransferInitiation</span><span class="sxs-lookup"><span data-stu-id="dc038-196">CustomerCreditTransferInitiation</span></span>  
4. <span data-ttu-id="dc038-197">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="dc038-197">Click Add.</span></span>
5. <span data-ttu-id="dc038-198">A Keresés mezőbe írja be a „CustomerCreditTransferInitiation” szöveget.</span><span class="sxs-lookup"><span data-stu-id="dc038-198">In the Find field, type 'CustomerCreditTransferInitiation'.</span></span>
    * <span data-ttu-id="dc038-199">CustomerCreditTransferInitiation</span><span class="sxs-lookup"><span data-stu-id="dc038-199">CustomerCreditTransferInitiation</span></span>  
6. <span data-ttu-id="dc038-200">Kattintson az Előző keresése lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="dc038-200">Click Find previous.</span></span>
7. <span data-ttu-id="dc038-201">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="dc038-201">Click New to open the drop dialog.</span></span>
8. <span data-ttu-id="dc038-202">A Név mezőbe írja be a „MessageIdentification” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="dc038-202">In the Name field, type 'MessageIdentification'.</span></span>
    * <span data-ttu-id="dc038-203">MessageIdentification</span><span class="sxs-lookup"><span data-stu-id="dc038-203">MessageIdentification</span></span>  
9. <span data-ttu-id="dc038-204">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="dc038-204">Click Add.</span></span>
10. <span data-ttu-id="dc038-205">A Leírás mezőben adja meg „A pontról pontra mutató hivatkozás, amelyet az utasító fél rendel hozzá az üzenethez (majd küld tovább a következő félnek) az üzenet azonosításához.” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="dc038-205">In the Description field, enter 'The point-to-point reference assigned by the instructing party (and sent to the next party) to identify a message.'.</span></span>
    * <span data-ttu-id="dc038-206">A pontról pontra mutató hivatkozás, amelyet az utasító fél rendel hozzá az üzenethez (majd küld tovább a következő félnek) az üzenet egyértelmű azonosításához.</span><span class="sxs-lookup"><span data-stu-id="dc038-206">The point-to-point reference assigned by the instructing party (and sent to the next party) to identify a message.</span></span>  
11. <span data-ttu-id="dc038-207">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="dc038-207">Click New to open the drop dialog.</span></span>
12. <span data-ttu-id="dc038-208">A Név mezőbe írja be az „ProcessingDateTime” szöveget.</span><span class="sxs-lookup"><span data-stu-id="dc038-208">In the Name field, type 'ProcessingDateTime'.</span></span>
    * <span data-ttu-id="dc038-209">ProcessingDateTime</span><span class="sxs-lookup"><span data-stu-id="dc038-209">ProcessingDateTime</span></span>  
13. <span data-ttu-id="dc038-210">A Cikktípus mezőben válassza ki a „DateTime” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="dc038-210">In the Item type field, select 'DateTime'.</span></span>
14. <span data-ttu-id="dc038-211">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="dc038-211">Click Add.</span></span>
15. <span data-ttu-id="dc038-212">A Leírás mezőben adja meg az „A fizetési üzenet létrehozásának dátuma és ideje” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="dc038-212">In the Description field, enter 'Date and time at which the payment message was created.'.</span></span>
    * <span data-ttu-id="dc038-213">A fizetési üzenet létrehozásának dátuma és ideje.</span><span class="sxs-lookup"><span data-stu-id="dc038-213">Date and time at which the payment message was created.</span></span>  
16. <span data-ttu-id="dc038-214">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="dc038-214">Click New to open the drop dialog.</span></span>
    * <span data-ttu-id="dc038-215">Modell fizetési tranzakciós struktúrájának meghatározása.</span><span class="sxs-lookup"><span data-stu-id="dc038-215">Define the payment transaction structure for this model.</span></span>  
17. <span data-ttu-id="dc038-216">A Név mezőbe írja be a „Fizetések” szöveget.</span><span class="sxs-lookup"><span data-stu-id="dc038-216">In the Name field, type 'Payments'.</span></span>
    * <span data-ttu-id="dc038-217">Kifizetések</span><span class="sxs-lookup"><span data-stu-id="dc038-217">Payments</span></span>  
18. <span data-ttu-id="dc038-218">A Cikktípus mezőben válassza ki a „Rekordlista” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="dc038-218">In the Item type field, select 'Record list'.</span></span>
19. <span data-ttu-id="dc038-219">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="dc038-219">Click Add.</span></span>
20. <span data-ttu-id="dc038-220">A Leírás mezőben adja meg a „Az aktuális üzenet fizetési sorai” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="dc038-220">In the Description field, enter 'Payment lines of the current message'.</span></span>
    * <span data-ttu-id="dc038-221">Az aktuális üzenet fizetési sorai</span><span class="sxs-lookup"><span data-stu-id="dc038-221">Payment lines of the current message</span></span>  
21. <span data-ttu-id="dc038-222">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="dc038-222">Click New to open the drop dialog.</span></span>
22. <span data-ttu-id="dc038-223">A Név mezőbe írja be a „Hitelező” szöveget.</span><span class="sxs-lookup"><span data-stu-id="dc038-223">In the Name field, type 'Creditor'.</span></span>
    * <span data-ttu-id="dc038-224">Beszedő</span><span class="sxs-lookup"><span data-stu-id="dc038-224">Creditor</span></span>  
23. <span data-ttu-id="dc038-225">A Cikktípus mezőben válassza ki a „Rekord” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="dc038-225">In the Item type field, select 'Record'.</span></span>
24. <span data-ttu-id="dc038-226">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="dc038-226">Click Add.</span></span>
25. <span data-ttu-id="dc038-227">A Leírás mezőben adja meg az „Az a fél, amely egy pénzösszegre jogosult” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="dc038-227">In the Description field, enter 'Party to which an amount of money is due.'.</span></span>
    * <span data-ttu-id="dc038-228">Az a fél, amely egy pénzösszegre jogosult.</span><span class="sxs-lookup"><span data-stu-id="dc038-228">Party to which an amount of money is due.</span></span>  
26. <span data-ttu-id="dc038-229">Kattintson a Cikkhivatkozás átváltása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="dc038-229">Click Switch item reference.</span></span>
27. <span data-ttu-id="dc038-230">A Keresés mezőbe írja be a következőt: „Fél”.</span><span class="sxs-lookup"><span data-stu-id="dc038-230">In the Find field, type 'Party'.</span></span>
    * <span data-ttu-id="dc038-231">Fél</span><span class="sxs-lookup"><span data-stu-id="dc038-231">Party</span></span>  
28. <span data-ttu-id="dc038-232">Kattintson a Következő keresése lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="dc038-232">Click Find next.</span></span>
29. <span data-ttu-id="dc038-233">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="dc038-233">Click OK.</span></span>
30. <span data-ttu-id="dc038-234">A Keresés mezőbe írja be a „Fizetések” szöveget.</span><span class="sxs-lookup"><span data-stu-id="dc038-234">In the Find field, type 'Payments'.</span></span>
    * <span data-ttu-id="dc038-235">Kifizetések</span><span class="sxs-lookup"><span data-stu-id="dc038-235">Payments</span></span>  
31. <span data-ttu-id="dc038-236">Kattintson a Következő keresése lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="dc038-236">Click Find next.</span></span>
32. <span data-ttu-id="dc038-237">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="dc038-237">Click New to open the drop dialog.</span></span>
33. <span data-ttu-id="dc038-238">A Név mezőbe írja be a „Kötelezett” szöveget.</span><span class="sxs-lookup"><span data-stu-id="dc038-238">In the Name field, type 'Debtor'.</span></span>
    * <span data-ttu-id="dc038-239">Kötelezett</span><span class="sxs-lookup"><span data-stu-id="dc038-239">Debtor</span></span>  
34. <span data-ttu-id="dc038-240">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="dc038-240">Click Add.</span></span>
35. <span data-ttu-id="dc038-241">A Leírás mezőben adja meg „Az a fél, amely tartozik egy pénzösszeggel a (végső) hitelezőnek” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="dc038-241">In the Description field, enter 'Party that owes an amount of money to the (ultimate) creditor.'.</span></span>
    * <span data-ttu-id="dc038-242">Az a fél, amely tartozik egy pénzösszeggel a (végső) hitelezőnek.</span><span class="sxs-lookup"><span data-stu-id="dc038-242">Party that owes an amount of money to the (ultimate) creditor.</span></span>  
36. <span data-ttu-id="dc038-243">Kattintson a Cikkhivatkozás átváltása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="dc038-243">Click Switch item reference.</span></span>
37. <span data-ttu-id="dc038-244">A Keresés mezőbe írja be a következőt: „Fél”.</span><span class="sxs-lookup"><span data-stu-id="dc038-244">In the Find field, type 'Party'.</span></span>
    * <span data-ttu-id="dc038-245">Fél</span><span class="sxs-lookup"><span data-stu-id="dc038-245">Party</span></span>  
38. <span data-ttu-id="dc038-246">Kattintson a Következő keresése lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="dc038-246">Click Find next.</span></span>
39. <span data-ttu-id="dc038-247">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="dc038-247">Click OK.</span></span>
40. <span data-ttu-id="dc038-248">Kattintson a Következő keresése lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="dc038-248">Click Find next.</span></span>
41. <span data-ttu-id="dc038-249">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="dc038-249">Click New to open the drop dialog.</span></span>
42. <span data-ttu-id="dc038-250">A Név mezőbe írja be a „Leírás” szöveget.</span><span class="sxs-lookup"><span data-stu-id="dc038-250">In the Name field, type 'Description'.</span></span>
    * <span data-ttu-id="dc038-251">Leírás</span><span class="sxs-lookup"><span data-stu-id="dc038-251">Description</span></span>  
43. <span data-ttu-id="dc038-252">A Cikktípus mezőben válassza ki a „Karakterlánc” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="dc038-252">In the Item type field, select 'String'.</span></span>
44. <span data-ttu-id="dc038-253">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="dc038-253">Click Add.</span></span>
45. <span data-ttu-id="dc038-254">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="dc038-254">Click New to open the drop dialog.</span></span>
46. <span data-ttu-id="dc038-255">A név mezőbe írja be a „Pénznem” szöveget.</span><span class="sxs-lookup"><span data-stu-id="dc038-255">In the Name field, type 'Currency'.</span></span>
    * <span data-ttu-id="dc038-256">Pénznem</span><span class="sxs-lookup"><span data-stu-id="dc038-256">Currency</span></span>  
47. <span data-ttu-id="dc038-257">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="dc038-257">Click Add.</span></span>
48. <span data-ttu-id="dc038-258">A Leírás mezőben adja meg a következőt: „Pénznemkód”.</span><span class="sxs-lookup"><span data-stu-id="dc038-258">In the Description field, enter 'Currency code'.</span></span>
    * <span data-ttu-id="dc038-259">Pénznemkód</span><span class="sxs-lookup"><span data-stu-id="dc038-259">Currency code</span></span>  
49. <span data-ttu-id="dc038-260">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="dc038-260">Click New to open the drop dialog.</span></span>
50. <span data-ttu-id="dc038-261">A Név mezőbe írja be a „TransactionDate” szöveget.</span><span class="sxs-lookup"><span data-stu-id="dc038-261">In the Name field, type 'TransactionDate'.</span></span>
    * <span data-ttu-id="dc038-262">TransactionDate</span><span class="sxs-lookup"><span data-stu-id="dc038-262">TransactionDate</span></span>  
51. <span data-ttu-id="dc038-263">A Cikktípus mezőben válassza ki a „Dátum” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="dc038-263">In the Item type field, select 'Date'.</span></span>
52. <span data-ttu-id="dc038-264">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="dc038-264">Click Add.</span></span>
53. <span data-ttu-id="dc038-265">A Leírás mezőben adja meg a következőt: „Tranzakció dátuma”.</span><span class="sxs-lookup"><span data-stu-id="dc038-265">In the Description field, enter 'Transaction date'.</span></span>
    * <span data-ttu-id="dc038-266">Tranzakció dátuma</span><span class="sxs-lookup"><span data-stu-id="dc038-266">Transaction date</span></span>  
54. <span data-ttu-id="dc038-267">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="dc038-267">Click New to open the drop dialog.</span></span>
55. <span data-ttu-id="dc038-268">A Név mezőbe írja be az „InstructedAmount” szöveget.</span><span class="sxs-lookup"><span data-stu-id="dc038-268">In the Name field, type 'InstructedAmount'.</span></span>
    * <span data-ttu-id="dc038-269">InstructedAmount</span><span class="sxs-lookup"><span data-stu-id="dc038-269">InstructedAmount</span></span>  
56. <span data-ttu-id="dc038-270">A Cikktípus mezőben válassza ki a „Valós” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="dc038-270">In the Item type field, select 'Real'.</span></span>
57. <span data-ttu-id="dc038-271">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="dc038-271">Click Add.</span></span>
58. <span data-ttu-id="dc038-272">A Leírás mezőben adja meg „A kötelezett és a hitelező között továbbítandó pénzösszeg, a költségek levonása előtt.</span><span class="sxs-lookup"><span data-stu-id="dc038-272">In the Description field, enter 'The amount of money to be moved between the debtor and creditor, before deduction of charges.</span></span> <span data-ttu-id="dc038-273">Az összeget a kezdeményező fél által meghatározott pénznemben kell kifejezni.” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="dc038-273">The amount should be expressed in the currency as ordered by the initiating party.'.</span></span>
    * <span data-ttu-id="dc038-274">A kötelezett és a hitelező között továbbítandó pénzösszeg, a költségek levonása előtt.</span><span class="sxs-lookup"><span data-stu-id="dc038-274">The amount of money to be moved between the debtor and creditor, before deduction of charges.</span></span> <span data-ttu-id="dc038-275">Az összeget a kezdeményező fél által meghatározott pénznemben kell kifejezni.</span><span class="sxs-lookup"><span data-stu-id="dc038-275">The amount should be expressed in the currency as ordered by the initiating party.</span></span>  
59. <span data-ttu-id="dc038-276">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="dc038-276">Click New to open the drop dialog.</span></span>
60. <span data-ttu-id="dc038-277">A Név mezőbe írja be az „End2EndID” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="dc038-277">In the Name field, type 'End2EndID'.</span></span>
    * <span data-ttu-id="dc038-278">End2EndID</span><span class="sxs-lookup"><span data-stu-id="dc038-278">End2EndID</span></span>  
61. <span data-ttu-id="dc038-279">A Cikktípus mezőben válassza ki a „Karakterlánc” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="dc038-279">In the Item type field, select 'String'.</span></span>
62. <span data-ttu-id="dc038-280">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="dc038-280">Click Add.</span></span>
63. <span data-ttu-id="dc038-281">A Leírás mezőben adja meg „Az egyedi azonosító, amelyet a kezdeményező fél rendel hozzá az üzenethez.</span><span class="sxs-lookup"><span data-stu-id="dc038-281">In the Description field, enter 'The unique identification assigned by the initiating party.</span></span> <span data-ttu-id="dc038-282">Ezt az azonosítót a rendszer változtatás nélkül továbbítja a teljes láncon a végpontok között.” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="dc038-282">This identification is passed on, unchanged, throughout the entire end-to-end chain.'.</span></span>
    * <span data-ttu-id="dc038-283">A kezdeményező fél által kiosztott egyedi azonosító.</span><span class="sxs-lookup"><span data-stu-id="dc038-283">The unique identification assigned by the initiating party.</span></span> <span data-ttu-id="dc038-284">Ezt az azonosítót adják tovább változatlanul a teljes láncon a végpontok között.</span><span class="sxs-lookup"><span data-stu-id="dc038-284">This identification is passed on, unchanged, throughout the entire end-to-end chain.</span></span>  
64. <span data-ttu-id="dc038-285">A Név mezőbe írja be a „PaymentModel” szöveget.</span><span class="sxs-lookup"><span data-stu-id="dc038-285">In the Name field, type 'PaymentModel'.</span></span>
    * <span data-ttu-id="dc038-286">A Fizetési modell neve megfelel a fizetési formák előre meghatározott interfészeinek.</span><span class="sxs-lookup"><span data-stu-id="dc038-286">The PaymentModel name aligns with predefined interfaces of payment forms.</span></span>  
65. <span data-ttu-id="dc038-287">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="dc038-287">Click Save.</span></span>
66. <span data-ttu-id="dc038-288">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="dc038-288">Close the page.</span></span>

