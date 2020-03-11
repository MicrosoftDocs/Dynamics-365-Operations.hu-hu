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
ms.openlocfilehash: d7882a7a17f5736d9d5a11cd91ac963fa89ff12f
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042896"
---
# <a name="er-design-domain-specific-data-model"></a><span data-ttu-id="167b1-103">ER - tartományspecifikus adatmodell kialakítása</span><span class="sxs-lookup"><span data-stu-id="167b1-103">ER Design domain specific data model</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="167b1-104">A következő lépések leírják, hogy egy Rendszergazda vagy Elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználó miként hozhat létre egy új Elektronikus jelentés (ER) konfigurációt, amely tartalmazza az Elektronikus fizetési dokumentumok adatmodelljét.</span><span class="sxs-lookup"><span data-stu-id="167b1-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can create a new Electronic reporting (ER) configuration that contains a data model for electronic payment documents.</span></span> <span data-ttu-id="167b1-105">Ezt az adatmodellt később adatforrásként használja a fizetési dokumentumok formátumának létrehozásakor.</span><span class="sxs-lookup"><span data-stu-id="167b1-105">This data model will later be used as a data source when you create the format of the payment documents.</span></span>

<span data-ttu-id="167b1-106">Ebben a példában a mintavállalatra, Litware-ra, Inc.-ra vonatkozóan létrehoz egy konfigurációs szolgáltatót. Ezeket a lépéseket a vállalatok között megosztott ER konfigurációkként hajthatók végre az egyes vállalatoknál.</span><span class="sxs-lookup"><span data-stu-id="167b1-106">In this example, you will create a configuration for sample company, Litware, Inc. These steps can be performed in any company as ER configurations are shared among companies.</span></span> <span data-ttu-id="167b1-107">Hajtsa végre az alábbi lépéseket: Először hajtsa végre a „Konfiguráció szolgáltatói létrehozása és aktívként történő megjelölése” eljárás lépéseit.</span><span class="sxs-lookup"><span data-stu-id="167b1-107">To complete these steps, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span>

1. <span data-ttu-id="167b1-108">Ugorjon a Szervezeti adminisztráció > Munkaterületek > Elektronikus jelentés pontra.</span><span class="sxs-lookup"><span data-stu-id="167b1-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>

    <span data-ttu-id="167b1-109">Válassza ki a konfigurációs szolgáltatót a Litware, Inc. mintavállalatra vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="167b1-109">Select the configuration provider for sample company, ‘Litware, Inc.’</span></span> <span data-ttu-id="167b1-110">Ha nem látja a konfigurációs szolgáltatót, először el kell végeznie a „Konfigurációszolgáltató létrehozása, és megjelölés aktívként” eljárásban szereplő lépéseket.</span><span class="sxs-lookup"><span data-stu-id="167b1-110">If you don’t see this configuration provider, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span>  
    
2. <span data-ttu-id="167b1-111">Kattintson a Jelentéskészítés konfigurációi lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="167b1-111">Click Reporting configurations.</span></span>

    <span data-ttu-id="167b1-112">Létrehoz egy konfigurációt, amely tartalmazza az elektronikus fizetési dokumentumok adatmodelljét.</span><span class="sxs-lookup"><span data-stu-id="167b1-112">You will create a configuration that contains a data model for electronic payment documents.</span></span> <span data-ttu-id="167b1-113">Ezt az adatmodellt később használja majd adatforrásként a fizetési dokumentumok formátumának létrehozásakor.</span><span class="sxs-lookup"><span data-stu-id="167b1-113">This data model will be used later as a data source when you create the format for the payment documents.</span></span>  

## <a name="create-a-new-data-model-configuration"></a><span data-ttu-id="167b1-114">Új adatmodell-konfiguráció létrehozása</span><span class="sxs-lookup"><span data-stu-id="167b1-114">Create a new data model configuration</span></span>
1. <span data-ttu-id="167b1-115">A Konfiguráció létrehozása gombra kattintva megnyithatja a legördülő párbeszédablakot.</span><span class="sxs-lookup"><span data-stu-id="167b1-115">Click Create configuration to open the drop dialog.</span></span>
2. <span data-ttu-id="167b1-116">A név mezőben írja be a „Fizetések (egyszerűsített modelladatok)” szöveget.</span><span class="sxs-lookup"><span data-stu-id="167b1-116">In the Name field, type 'Payments (simplified model)'.</span></span>
3. <span data-ttu-id="167b1-117">A Leírás mezőben írja be a „Fizetés modell konfigurációja” szöveget.</span><span class="sxs-lookup"><span data-stu-id="167b1-117">In the Description field, type 'Payment model configuration'.</span></span>

    <span data-ttu-id="167b1-118">Az aktív konfigurációs szolgáltató automatikusan megjelenik itt.</span><span class="sxs-lookup"><span data-stu-id="167b1-118">The active configuration provider is automatically entered here.</span></span> <span data-ttu-id="167b1-119">Ez a szolgáltató tartja majd karban ezt a konfigurációt.</span><span class="sxs-lookup"><span data-stu-id="167b1-119">This provider will be able to maintain this configuration.</span></span> <span data-ttu-id="167b1-120">Más szolgáltatók is használhatják ezt a konfigurációt, de nem tudják majd karbantartani.</span><span class="sxs-lookup"><span data-stu-id="167b1-120">Other providers can use this configuration, but will not be able to maintain it.</span></span>  

4. <span data-ttu-id="167b1-121">Kattintson a „Konfiguráció létrehozása” gombra a konfigurációlétrehozási feladat befejezéséhez</span><span class="sxs-lookup"><span data-stu-id="167b1-121">Click ‘Create configuration’ button to complete the configuration creation task</span></span>

## <a name="create-a-data-model"></a><span data-ttu-id="167b1-122">Adatmodell létrehozása</span><span class="sxs-lookup"><span data-stu-id="167b1-122">Create a data model</span></span>
<span data-ttu-id="167b1-123">Új adatmodellt hoz létre a kiválasztott konfigurációhoz.</span><span class="sxs-lookup"><span data-stu-id="167b1-123">You're creating a new data model for the selected configuration.</span></span> <span data-ttu-id="167b1-124">Ennek a konfigurációverziónak az állapota Vázlat lesz.</span><span class="sxs-lookup"><span data-stu-id="167b1-124">This configuration version will have a status of Draft.</span></span>  
1. <span data-ttu-id="167b1-125">Kattintson a Tervező pontra.</span><span class="sxs-lookup"><span data-stu-id="167b1-125">Click Designer.</span></span>

## <a name="define-the-structure-of-a-party-participating-in-a-payment-process"></a><span data-ttu-id="167b1-126">A kifizetési folyamatban részt vevő fél szerkezetének meghatározása</span><span class="sxs-lookup"><span data-stu-id="167b1-126">Define the structure of a party participating in a payment process</span></span>
1. <span data-ttu-id="167b1-127">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="167b1-127">Click New to open the drop dialog.</span></span>
2. <span data-ttu-id="167b1-128">A Név mezőbe írja be a következőt: „Fél”.</span><span class="sxs-lookup"><span data-stu-id="167b1-128">In the Name field, type 'Party'.</span></span>
3. <span data-ttu-id="167b1-129">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="167b1-129">Click Add.</span></span>
4. <span data-ttu-id="167b1-130">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="167b1-130">Click New to open the drop dialog.</span></span>
5. <span data-ttu-id="167b1-131">A Név mezőbe írja be a „Név” szöveget.</span><span class="sxs-lookup"><span data-stu-id="167b1-131">In the Name field, type 'Name'.</span></span>
6. <span data-ttu-id="167b1-132">A Cikktípus mezőben válassza ki a „Karakterlánc” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="167b1-132">In the Item type field, select 'String'.</span></span>
7. <span data-ttu-id="167b1-133">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="167b1-133">Click Add.</span></span>
8. <span data-ttu-id="167b1-134">A Keresés mezőbe írja be a következőt: „Fél”.</span><span class="sxs-lookup"><span data-stu-id="167b1-134">In the Find field, type 'Party'.</span></span>
9. <span data-ttu-id="167b1-135">Kattintson az Előző keresése lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="167b1-135">Click Find previous.</span></span>

## <a name="define-the-bank-structure-for-this-model"></a><span data-ttu-id="167b1-136">Modell bankstruktúrájának meghatározása</span><span class="sxs-lookup"><span data-stu-id="167b1-136">Define the bank structure for this model</span></span>
1. <span data-ttu-id="167b1-137">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="167b1-137">Click New to open the drop dialog.</span></span>
2. <span data-ttu-id="167b1-138">A név mezőbe írja be az „Ügynök”.</span><span class="sxs-lookup"><span data-stu-id="167b1-138">In the Name field, type 'Agent'.</span></span>
3. <span data-ttu-id="167b1-139">A Cikktípus mezőben válassza ki a „Rekord” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="167b1-139">In the Item type field, select 'Record'.</span></span>
4. <span data-ttu-id="167b1-140">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="167b1-140">Click Add.</span></span>
5. <span data-ttu-id="167b1-141">A Leírás mezőben adja meg a „Pénzintézet (pl. bank), amely számlát tart fenn a fél (kötelezett/hitelező) részére.” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="167b1-141">In the Description field, enter 'Financial institution (for instance, a bank) servicing an account for the party (debtor/creditor).'.</span></span>

    <span data-ttu-id="167b1-142">Pénzintézet (pl. bank), amely számlát tart fenn a fél (kötelezett/hitelező) részére.</span><span class="sxs-lookup"><span data-stu-id="167b1-142">Financial institution (for instance, a bank) servicing an account for the party (debtor/creditor).</span></span>  

6. <span data-ttu-id="167b1-143">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="167b1-143">Click New to open the drop dialog.</span></span>
7. <span data-ttu-id="167b1-144">A Név mezőbe írja be a „Név” szöveget.</span><span class="sxs-lookup"><span data-stu-id="167b1-144">In the Name field, type 'Name'.</span></span> 
8. <span data-ttu-id="167b1-145">A Cikktípus mezőben válassza ki a „Karakterlánc” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="167b1-145">In the Item type field, select 'String'.</span></span>
9. <span data-ttu-id="167b1-146">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="167b1-146">Click Add.</span></span>
10. <span data-ttu-id="167b1-147">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="167b1-147">Click New to open the drop dialog.</span></span>
11. <span data-ttu-id="167b1-148">A Név mezőbe írja be a „SWIFT” szöveget.</span><span class="sxs-lookup"><span data-stu-id="167b1-148">In the Name field, type 'SWIFT'.</span></span>
12. <span data-ttu-id="167b1-149">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="167b1-149">Click Add.</span></span>
13. <span data-ttu-id="167b1-150">A Leírás mezőben adja meg a következőt: „Bankazonosító kód”.</span><span class="sxs-lookup"><span data-stu-id="167b1-150">In the Description field, enter 'Bank identification code'.</span></span> 
14. <span data-ttu-id="167b1-151">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="167b1-151">Click New to open the drop dialog.</span></span>
15. <span data-ttu-id="167b1-152">A Név mezőbe írja be a „RoutingNumber” szöveget.</span><span class="sxs-lookup"><span data-stu-id="167b1-152">In the Name field, type 'RoutingNumber'.</span></span>
16. <span data-ttu-id="167b1-153">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="167b1-153">Click Add.</span></span>
17. <span data-ttu-id="167b1-154">A Leírás mezőben adja meg a következőt: „Regisztrációs azonosító száma”.</span><span class="sxs-lookup"><span data-stu-id="167b1-154">In the Description field, enter 'Routing number'.</span></span>
18. <span data-ttu-id="167b1-155">Kattintson az Előző keresése lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="167b1-155">Click Find previous.</span></span>

## <a name="define-the-bank-account-structure-for-this-model"></a><span data-ttu-id="167b1-156">Modell bankszámla-struktúrájának meghatározása</span><span class="sxs-lookup"><span data-stu-id="167b1-156">Define the bank account structure for this model</span></span>
1. <span data-ttu-id="167b1-157">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="167b1-157">Click New to open the drop dialog.</span></span>
2. <span data-ttu-id="167b1-158">A Név mezőbe írja be a „Számla” szöveget.</span><span class="sxs-lookup"><span data-stu-id="167b1-158">In the Name field, type 'Account'.</span></span> 
3. <span data-ttu-id="167b1-159">A Cikktípus mezőben válassza ki a „Rekord” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="167b1-159">In the Item type field, select 'Record'.</span></span>
4. <span data-ttu-id="167b1-160">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="167b1-160">Click Add.</span></span>
5. <span data-ttu-id="167b1-161">A Leírás mezőben adja meg a következőt: „A fél pénzintézetben (például a bank) vezetett számlájának azonosítása.”.</span><span class="sxs-lookup"><span data-stu-id="167b1-161">In the Description field, enter 'Identification of an account of a party in a financial institution (for instance, a bank).'.</span></span>

    <span data-ttu-id="167b1-162">A fél pénzintézetben (például a bank) vezetett számlájának azonosítása.</span><span class="sxs-lookup"><span data-stu-id="167b1-162">Identification of an account of a party in a financial institution (for instance, a bank).</span></span>  

6. <span data-ttu-id="167b1-163">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="167b1-163">Click New to open the drop dialog.</span></span>
7. <span data-ttu-id="167b1-164">A név mezőbe írja be a „Pénznem” szöveget.</span><span class="sxs-lookup"><span data-stu-id="167b1-164">In the Name field, type 'Currency'.</span></span> 
8. <span data-ttu-id="167b1-165">A Cikktípus mezőben válassza ki a „Karakterlánc” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="167b1-165">In the Item type field, select 'String'.</span></span>
9. <span data-ttu-id="167b1-166">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="167b1-166">Click Add.</span></span>
10. <span data-ttu-id="167b1-167">A Leírás mezőben adja meg a következőt: „Pénznemkód”.</span><span class="sxs-lookup"><span data-stu-id="167b1-167">In the Description field, enter 'Currency code'.</span></span>
11. <span data-ttu-id="167b1-168">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="167b1-168">Click New to open the drop dialog.</span></span>
12. <span data-ttu-id="167b1-169">A Név mezőbe írja be a „Szám” szöveget.</span><span class="sxs-lookup"><span data-stu-id="167b1-169">In the Name field, type 'Number'.</span></span> 
13. <span data-ttu-id="167b1-170">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="167b1-170">Click Add.</span></span>
14. <span data-ttu-id="167b1-171">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="167b1-171">Click New to open the drop dialog.</span></span>
15. <span data-ttu-id="167b1-172">A Név mezőbe írja be az „IBAN” szöveget.</span><span class="sxs-lookup"><span data-stu-id="167b1-172">In the Name field, type 'IBAN'.</span></span> 
16. <span data-ttu-id="167b1-173">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="167b1-173">Click Add.</span></span>
17. <span data-ttu-id="167b1-174">A Leírás mezőben adja meg a következőt: „Nemzetközi bankszámlaszám”.</span><span class="sxs-lookup"><span data-stu-id="167b1-174">In the Description field, enter 'International bank account number'.</span></span>

## <a name="define-the-payment-message-structure-for-credit-transfer-payment-type"></a><span data-ttu-id="167b1-175">A fizetési üzenetstruktúra meghatározása a jóváírási átmozgatás fizetési típusra</span><span class="sxs-lookup"><span data-stu-id="167b1-175">Define the payment message structure for credit transfer payment type</span></span>
1. <span data-ttu-id="167b1-176">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="167b1-176">Click New to open the drop dialog.</span></span>
2. <span data-ttu-id="167b1-177">Az Új csomópontként mezőben adja meg a következőt: „Modellgyökér”.</span><span class="sxs-lookup"><span data-stu-id="167b1-177">In the New node as a field, enter 'Model root'.</span></span>
3. <span data-ttu-id="167b1-178">A Név mezőbe írja be a „CustomerCreditTransferInitiation” szöveget.</span><span class="sxs-lookup"><span data-stu-id="167b1-178">In the Name field, type 'CustomerCreditTransferInitiation'.</span></span>
4. <span data-ttu-id="167b1-179">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="167b1-179">Click Add.</span></span>
5. <span data-ttu-id="167b1-180">A Keresés mezőbe írja be a „CustomerCreditTransferInitiation” szöveget.</span><span class="sxs-lookup"><span data-stu-id="167b1-180">In the Find field, type 'CustomerCreditTransferInitiation'.</span></span> 
6. <span data-ttu-id="167b1-181">Kattintson az Előző keresése lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="167b1-181">Click Find previous.</span></span>
7. <span data-ttu-id="167b1-182">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="167b1-182">Click New to open the drop dialog.</span></span>
8. <span data-ttu-id="167b1-183">A Név mezőbe írja be a „MessageIdentification” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="167b1-183">In the Name field, type 'MessageIdentification'.</span></span> 
9. <span data-ttu-id="167b1-184">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="167b1-184">Click Add.</span></span>
10. <span data-ttu-id="167b1-185">A Leírás mezőben adja meg „A pontról pontra mutató hivatkozás, amelyet az utasító fél rendel hozzá az üzenethez (majd küld tovább a következő félnek) az üzenet azonosításához.” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="167b1-185">In the Description field, enter 'The point-to-point reference assigned by the instructing party (and sent to the next party) to identify a message.'.</span></span>

    <span data-ttu-id="167b1-186">A pontról pontra mutató hivatkozás, amelyet az utasító fél rendel hozzá az üzenethez (majd küld tovább a következő félnek) az üzenet egyértelmű azonosításához.</span><span class="sxs-lookup"><span data-stu-id="167b1-186">The point-to-point reference assigned by the instructing party (and sent to the next party) to identify a message.</span></span>  

11. <span data-ttu-id="167b1-187">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="167b1-187">Click New to open the drop dialog.</span></span>
12. <span data-ttu-id="167b1-188">A Név mezőbe írja be az „ProcessingDateTime” szöveget.</span><span class="sxs-lookup"><span data-stu-id="167b1-188">In the Name field, type 'ProcessingDateTime'.</span></span>
13. <span data-ttu-id="167b1-189">A Cikktípus mezőben válassza ki a „DateTime” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="167b1-189">In the Item type field, select 'DateTime'.</span></span>
14. <span data-ttu-id="167b1-190">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="167b1-190">Click Add.</span></span>
15. <span data-ttu-id="167b1-191">A Leírás mezőben adja meg az „A fizetési üzenet létrehozásának dátuma és ideje” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="167b1-191">In the Description field, enter 'Date and time at which the payment message was created.'.</span></span> 
16. <span data-ttu-id="167b1-192">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="167b1-192">Click New to open the drop dialog.</span></span>

    <span data-ttu-id="167b1-193">Modell fizetési tranzakciós struktúrájának meghatározása.</span><span class="sxs-lookup"><span data-stu-id="167b1-193">Define the payment transaction structure for this model.</span></span>  

17. <span data-ttu-id="167b1-194">A Név mezőbe írja be a „Fizetések” szöveget.</span><span class="sxs-lookup"><span data-stu-id="167b1-194">In the Name field, type 'Payments'.</span></span>
18. <span data-ttu-id="167b1-195">A Cikktípus mezőben válassza ki a „Rekordlista” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="167b1-195">In the Item type field, select 'Record list'.</span></span>
19. <span data-ttu-id="167b1-196">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="167b1-196">Click Add.</span></span>
20. <span data-ttu-id="167b1-197">A Leírás mezőben adja meg a „Az aktuális üzenet fizetési sorai” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="167b1-197">In the Description field, enter 'Payment lines of the current message'.</span></span>
21. <span data-ttu-id="167b1-198">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="167b1-198">Click New to open the drop dialog.</span></span>
22. <span data-ttu-id="167b1-199">A Név mezőbe írja be a „Hitelező” szöveget.</span><span class="sxs-lookup"><span data-stu-id="167b1-199">In the Name field, type 'Creditor'.</span></span> 
23. <span data-ttu-id="167b1-200">A Cikktípus mezőben válassza ki a „Rekord” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="167b1-200">In the Item type field, select 'Record'.</span></span>
24. <span data-ttu-id="167b1-201">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="167b1-201">Click Add.</span></span>
25. <span data-ttu-id="167b1-202">A Leírás mezőben adja meg az „Az a fél, amely egy pénzösszegre jogosult” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="167b1-202">In the Description field, enter 'Party to which an amount of money is due.'.</span></span> 
26. <span data-ttu-id="167b1-203">Kattintson a Cikkhivatkozás átváltása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="167b1-203">Click Switch item reference.</span></span>
27. <span data-ttu-id="167b1-204">A Keresés mezőbe írja be a következőt: „Fél”.</span><span class="sxs-lookup"><span data-stu-id="167b1-204">In the Find field, type 'Party'.</span></span>
28. <span data-ttu-id="167b1-205">Kattintson a Következő keresése lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="167b1-205">Click Find next.</span></span>
29. <span data-ttu-id="167b1-206">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="167b1-206">Click OK.</span></span>
30. <span data-ttu-id="167b1-207">A Keresés mezőbe írja be a „Fizetések” szöveget.</span><span class="sxs-lookup"><span data-stu-id="167b1-207">In the Find field, type 'Payments'.</span></span>
31. <span data-ttu-id="167b1-208">Kattintson a Következő keresése lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="167b1-208">Click Find next.</span></span>
32. <span data-ttu-id="167b1-209">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="167b1-209">Click New to open the drop dialog.</span></span>
33. <span data-ttu-id="167b1-210">A Név mezőbe írja be a „Kötelezett” szöveget.</span><span class="sxs-lookup"><span data-stu-id="167b1-210">In the Name field, type 'Debtor'.</span></span> 
34. <span data-ttu-id="167b1-211">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="167b1-211">Click Add.</span></span>
35. <span data-ttu-id="167b1-212">A Leírás mezőben adja meg „Az a fél, amely tartozik egy pénzösszeggel a (végső) hitelezőnek” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="167b1-212">In the Description field, enter 'Party that owes an amount of money to the (ultimate) creditor.'.</span></span>
36. <span data-ttu-id="167b1-213">Kattintson a Cikkhivatkozás átváltása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="167b1-213">Click Switch item reference.</span></span>
37. <span data-ttu-id="167b1-214">A Keresés mezőbe írja be a következőt: „Fél”.</span><span class="sxs-lookup"><span data-stu-id="167b1-214">In the Find field, type 'Party'.</span></span>
38. <span data-ttu-id="167b1-215">Kattintson a Következő keresése lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="167b1-215">Click Find next.</span></span>
39. <span data-ttu-id="167b1-216">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="167b1-216">Click OK.</span></span>
40. <span data-ttu-id="167b1-217">Kattintson a Következő keresése lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="167b1-217">Click Find next.</span></span>
41. <span data-ttu-id="167b1-218">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="167b1-218">Click New to open the drop dialog.</span></span>
42. <span data-ttu-id="167b1-219">A Név mezőbe írja be a „Leírás” szöveget.</span><span class="sxs-lookup"><span data-stu-id="167b1-219">In the Name field, type 'Description'.</span></span>
43. <span data-ttu-id="167b1-220">A Cikktípus mezőben válassza ki a „Karakterlánc” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="167b1-220">In the Item type field, select 'String'.</span></span>
44. <span data-ttu-id="167b1-221">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="167b1-221">Click Add.</span></span>
45. <span data-ttu-id="167b1-222">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="167b1-222">Click New to open the drop dialog.</span></span>
46. <span data-ttu-id="167b1-223">A név mezőbe írja be a „Pénznem” szöveget.</span><span class="sxs-lookup"><span data-stu-id="167b1-223">In the Name field, type 'Currency'.</span></span>
47. <span data-ttu-id="167b1-224">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="167b1-224">Click Add.</span></span>
48. <span data-ttu-id="167b1-225">A Leírás mezőben adja meg a következőt: „Pénznemkód”.</span><span class="sxs-lookup"><span data-stu-id="167b1-225">In the Description field, enter 'Currency code'.</span></span>
49. <span data-ttu-id="167b1-226">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="167b1-226">Click New to open the drop dialog.</span></span>
50. <span data-ttu-id="167b1-227">A Név mezőbe írja be a „TransactionDate” szöveget.</span><span class="sxs-lookup"><span data-stu-id="167b1-227">In the Name field, type 'TransactionDate'.</span></span> 
51. <span data-ttu-id="167b1-228">A Cikktípus mezőben válassza ki a „Dátum” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="167b1-228">In the Item type field, select 'Date'.</span></span>
52. <span data-ttu-id="167b1-229">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="167b1-229">Click Add.</span></span>
53. <span data-ttu-id="167b1-230">A Leírás mezőben adja meg a következőt: „Tranzakció dátuma”.</span><span class="sxs-lookup"><span data-stu-id="167b1-230">In the Description field, enter 'Transaction date'.</span></span> 
54. <span data-ttu-id="167b1-231">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="167b1-231">Click New to open the drop dialog.</span></span>
55. <span data-ttu-id="167b1-232">A Név mezőbe írja be az „InstructedAmount” szöveget.</span><span class="sxs-lookup"><span data-stu-id="167b1-232">In the Name field, type 'InstructedAmount'.</span></span>  
56. <span data-ttu-id="167b1-233">A Cikktípus mezőben válassza ki a „Valós” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="167b1-233">In the Item type field, select 'Real'.</span></span>
57. <span data-ttu-id="167b1-234">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="167b1-234">Click Add.</span></span>
58. <span data-ttu-id="167b1-235">A Leírás mezőben adja meg „A kötelezett és a hitelező között továbbítandó pénzösszeg, a költségek levonása előtt.</span><span class="sxs-lookup"><span data-stu-id="167b1-235">In the Description field, enter 'The amount of money to be moved between the debtor and creditor, before deduction of charges.</span></span> <span data-ttu-id="167b1-236">Az összeget a kezdeményező fél által meghatározott pénznemben kell kifejezni.” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="167b1-236">The amount should be expressed in the currency as ordered by the initiating party.'.</span></span>

    <span data-ttu-id="167b1-237">A kötelezett és a hitelező között továbbítandó pénzösszeg, a költségek levonása előtt.</span><span class="sxs-lookup"><span data-stu-id="167b1-237">The amount of money to be moved between the debtor and creditor, before deduction of charges.</span></span> <span data-ttu-id="167b1-238">Az összeget a kezdeményező fél által meghatározott pénznemben kell kifejezni.</span><span class="sxs-lookup"><span data-stu-id="167b1-238">The amount should be expressed in the currency as ordered by the initiating party.</span></span>  

59. <span data-ttu-id="167b1-239">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="167b1-239">Click New to open the drop dialog.</span></span>
60. <span data-ttu-id="167b1-240">A Név mezőbe írja be az „End2EndID” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="167b1-240">In the Name field, type 'End2EndID'.</span></span> 
61. <span data-ttu-id="167b1-241">A Cikktípus mezőben válassza ki a „Karakterlánc” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="167b1-241">In the Item type field, select 'String'.</span></span>
62. <span data-ttu-id="167b1-242">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="167b1-242">Click Add.</span></span>
63. <span data-ttu-id="167b1-243">A Leírás mezőben adja meg „Az egyedi azonosító, amelyet a kezdeményező fél rendel hozzá az üzenethez.</span><span class="sxs-lookup"><span data-stu-id="167b1-243">In the Description field, enter 'The unique identification assigned by the initiating party.</span></span> <span data-ttu-id="167b1-244">Ezt az azonosítót a rendszer változtatás nélkül továbbítja a teljes láncon a végpontok között.” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="167b1-244">This identification is passed on, unchanged, throughout the entire end-to-end chain.'.</span></span> 
64. <span data-ttu-id="167b1-245">A Név mezőbe írja be a „PaymentModel” szöveget.</span><span class="sxs-lookup"><span data-stu-id="167b1-245">In the Name field, type 'PaymentModel'.</span></span>

    <span data-ttu-id="167b1-246">A Fizetési modell neve megfelel a fizetési formák előre meghatározott interfészeinek.</span><span class="sxs-lookup"><span data-stu-id="167b1-246">The PaymentModel name aligns with predefined interfaces of payment forms.</span></span>  

65. <span data-ttu-id="167b1-247">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="167b1-247">Click Save.</span></span>
66. <span data-ttu-id="167b1-248">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="167b1-248">Close the page.</span></span>

