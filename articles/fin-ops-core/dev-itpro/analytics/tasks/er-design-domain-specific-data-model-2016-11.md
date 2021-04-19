---
title: ER - tartományspecifikus adatmodell kialakítása
description: Ez a témakör azt ismerteti, hogyan lehet létrehozni egy olyan új Elektronikus jelentéskészítési (ER) konfigurációt, amely egy adatmodellt tartalmaz az elektronikus fizetési bizonylatokhoz.
author: NickSelin
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, ERDataModelDesigner, ERDataModelContentsItemCreationDialog, ERDataContainerDescriptorReferenceSwitchDialog
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 351c5a6624f7ee912c507a9f74324f4c8f61166b
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5755034"
---
# <a name="er-design-domain-specific-data-model"></a><span data-ttu-id="46a0c-103">ER - tartományspecifikus adatmodell kialakítása</span><span class="sxs-lookup"><span data-stu-id="46a0c-103">ER Design domain specific data model</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="46a0c-104">A következő lépések leírják, hogy egy Rendszergazda vagy Elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználó miként hozhat létre egy új Elektronikus jelentés (ER) konfigurációt, amely tartalmazza az Elektronikus fizetési dokumentumok adatmodelljét.</span><span class="sxs-lookup"><span data-stu-id="46a0c-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can create a new Electronic reporting (ER) configuration that contains a data model for electronic payment documents.</span></span> <span data-ttu-id="46a0c-105">Ezt az adatmodellt később adatforrásként használja a fizetési dokumentumok formátumának létrehozásakor.</span><span class="sxs-lookup"><span data-stu-id="46a0c-105">This data model will later be used as a data source when you create the format of the payment documents.</span></span>

<span data-ttu-id="46a0c-106">Ebben a példában a mintavállalatra, Litware-ra, Inc.-ra vonatkozóan létrehoz egy konfigurációs szolgáltatót. Ezeket a lépéseket a vállalatok között megosztott ER konfigurációkként hajthatók végre az egyes vállalatoknál.</span><span class="sxs-lookup"><span data-stu-id="46a0c-106">In this example, you will create a configuration for sample company, Litware, Inc. These steps can be performed in any company as ER configurations are shared among companies.</span></span> <span data-ttu-id="46a0c-107">Hajtsa végre az alábbi lépéseket: először hajtsa végre a „Konfigurációszolgáltató létrehozása és aktívként történő megjelölése” eljárás lépéseit.</span><span class="sxs-lookup"><span data-stu-id="46a0c-107">To complete these steps, you must first complete the steps in the "Create a configuration provider and mark it as active" procedure.</span></span>

1. <span data-ttu-id="46a0c-108">Ugorjon a Szervezeti adminisztráció > Munkaterületek > Elektronikus jelentés pontra.</span><span class="sxs-lookup"><span data-stu-id="46a0c-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>

    <span data-ttu-id="46a0c-109">Válassza ki a konfigurációs szolgáltatót a Litware, Inc. mintavállalatra vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="46a0c-109">Select the configuration provider for sample company, 'Litware, Inc.'</span></span> <span data-ttu-id="46a0c-110">Ha nem látja a konfigurációszolgáltatót, először el kell végeznie a „Konfigurációszolgáltató létrehozása, és megjelölés aktívként” eljárásban szereplő lépéseket.</span><span class="sxs-lookup"><span data-stu-id="46a0c-110">If you don't see this configuration provider, you must first complete the steps in the "Create a configuration provider and mark it as active" procedure.</span></span>  
    
2. <span data-ttu-id="46a0c-111">Kattintson a Jelentéskészítés konfigurációi lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="46a0c-111">Click Reporting configurations.</span></span>

    <span data-ttu-id="46a0c-112">Létrehoz egy konfigurációt, amely tartalmazza az elektronikus fizetési dokumentumok adatmodelljét.</span><span class="sxs-lookup"><span data-stu-id="46a0c-112">You will create a configuration that contains a data model for electronic payment documents.</span></span> <span data-ttu-id="46a0c-113">Ezt az adatmodellt később használja majd adatforrásként a fizetési dokumentumok formátumának létrehozásakor.</span><span class="sxs-lookup"><span data-stu-id="46a0c-113">This data model will be used later as a data source when you create the format for the payment documents.</span></span>  

## <a name="create-a-new-data-model-configuration"></a><span data-ttu-id="46a0c-114">Új adatmodell-konfiguráció létrehozása</span><span class="sxs-lookup"><span data-stu-id="46a0c-114">Create a new data model configuration</span></span>
1. <span data-ttu-id="46a0c-115">A Konfiguráció létrehozása gombra kattintva megnyithatja a legördülő párbeszédablakot.</span><span class="sxs-lookup"><span data-stu-id="46a0c-115">Click Create configuration to open the drop dialog.</span></span>
2. <span data-ttu-id="46a0c-116">A név mezőben írja be a „Fizetések (egyszerűsített modelladatok)” szöveget.</span><span class="sxs-lookup"><span data-stu-id="46a0c-116">In the Name field, type 'Payments (simplified model)'.</span></span>
3. <span data-ttu-id="46a0c-117">A Leírás mezőben írja be a „Fizetés modell konfigurációja” szöveget.</span><span class="sxs-lookup"><span data-stu-id="46a0c-117">In the Description field, type 'Payment model configuration'.</span></span>

    <span data-ttu-id="46a0c-118">Az aktív konfigurációs szolgáltató automatikusan megjelenik itt.</span><span class="sxs-lookup"><span data-stu-id="46a0c-118">The active configuration provider is automatically entered here.</span></span> <span data-ttu-id="46a0c-119">Ez a szolgáltató tartja majd karban ezt a konfigurációt.</span><span class="sxs-lookup"><span data-stu-id="46a0c-119">This provider will be able to maintain this configuration.</span></span> <span data-ttu-id="46a0c-120">Más szolgáltatók is használhatják ezt a konfigurációt, de nem tudják majd karbantartani.</span><span class="sxs-lookup"><span data-stu-id="46a0c-120">Other providers can use this configuration, but will not be able to maintain it.</span></span>  

4. <span data-ttu-id="46a0c-121">Kattintson a „Konfiguráció létrehozása” gombra a konfigurációlétrehozási feladat befejezéséhez</span><span class="sxs-lookup"><span data-stu-id="46a0c-121">Click 'Create configuration' button to complete the configuration creation task</span></span>

## <a name="create-a-data-model"></a><span data-ttu-id="46a0c-122">Adatmodell létrehozása</span><span class="sxs-lookup"><span data-stu-id="46a0c-122">Create a data model</span></span>
<span data-ttu-id="46a0c-123">Új adatmodellt hoz létre a kiválasztott konfigurációhoz.</span><span class="sxs-lookup"><span data-stu-id="46a0c-123">You're creating a new data model for the selected configuration.</span></span> <span data-ttu-id="46a0c-124">Ennek a konfigurációverziónak az állapota Vázlat lesz.</span><span class="sxs-lookup"><span data-stu-id="46a0c-124">This configuration version will have a status of Draft.</span></span>  
1. <span data-ttu-id="46a0c-125">Kattintson a Tervező pontra.</span><span class="sxs-lookup"><span data-stu-id="46a0c-125">Click Designer.</span></span>

## <a name="define-the-structure-of-a-party-participating-in-a-payment-process"></a><span data-ttu-id="46a0c-126">A kifizetési folyamatban részt vevő fél szerkezetének meghatározása</span><span class="sxs-lookup"><span data-stu-id="46a0c-126">Define the structure of a party participating in a payment process</span></span>
1. <span data-ttu-id="46a0c-127">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="46a0c-127">Click New to open the drop dialog.</span></span>
2. <span data-ttu-id="46a0c-128">A Név mezőbe írja be a következőt: „Fél”.</span><span class="sxs-lookup"><span data-stu-id="46a0c-128">In the Name field, type 'Party'.</span></span>
3. <span data-ttu-id="46a0c-129">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="46a0c-129">Click Add.</span></span>
4. <span data-ttu-id="46a0c-130">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="46a0c-130">Click New to open the drop dialog.</span></span>
5. <span data-ttu-id="46a0c-131">A Név mezőbe írja be a „Név” szöveget.</span><span class="sxs-lookup"><span data-stu-id="46a0c-131">In the Name field, type 'Name'.</span></span>
6. <span data-ttu-id="46a0c-132">A Cikktípus mezőben válassza ki a „Karakterlánc” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="46a0c-132">In the Item type field, select 'String'.</span></span>
7. <span data-ttu-id="46a0c-133">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="46a0c-133">Click Add.</span></span>
8. <span data-ttu-id="46a0c-134">A Keresés mezőbe írja be a következőt: „Fél”.</span><span class="sxs-lookup"><span data-stu-id="46a0c-134">In the Find field, type 'Party'.</span></span>
9. <span data-ttu-id="46a0c-135">Kattintson az Előző keresése lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="46a0c-135">Click Find previous.</span></span>

## <a name="define-the-bank-structure-for-this-model"></a><span data-ttu-id="46a0c-136">Modell bankstruktúrájának meghatározása</span><span class="sxs-lookup"><span data-stu-id="46a0c-136">Define the bank structure for this model</span></span>
1. <span data-ttu-id="46a0c-137">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="46a0c-137">Click New to open the drop dialog.</span></span>
2. <span data-ttu-id="46a0c-138">A név mezőbe írja be az „Ügynök”.</span><span class="sxs-lookup"><span data-stu-id="46a0c-138">In the Name field, type 'Agent'.</span></span>
3. <span data-ttu-id="46a0c-139">A Cikktípus mezőben válassza ki a „Rekord” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="46a0c-139">In the Item type field, select 'Record'.</span></span>
4. <span data-ttu-id="46a0c-140">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="46a0c-140">Click Add.</span></span>
5. <span data-ttu-id="46a0c-141">A Leírás mezőben adja meg a „Pénzintézet (pl. bank), amely számlát tart fenn a fél (kötelezett/hitelező) részére.” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="46a0c-141">In the Description field, enter 'Financial institution (for instance, a bank) servicing an account for the party (debtor/creditor).'.</span></span>

    <span data-ttu-id="46a0c-142">Pénzintézet (pl. bank), amely számlát tart fenn a fél (kötelezett/hitelező) részére.</span><span class="sxs-lookup"><span data-stu-id="46a0c-142">Financial institution (for instance, a bank) servicing an account for the party (debtor/creditor).</span></span>  

6. <span data-ttu-id="46a0c-143">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="46a0c-143">Click New to open the drop dialog.</span></span>
7. <span data-ttu-id="46a0c-144">A Név mezőbe írja be a „Név” szöveget.</span><span class="sxs-lookup"><span data-stu-id="46a0c-144">In the Name field, type 'Name'.</span></span> 
8. <span data-ttu-id="46a0c-145">A Cikktípus mezőben válassza ki a „Karakterlánc” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="46a0c-145">In the Item type field, select 'String'.</span></span>
9. <span data-ttu-id="46a0c-146">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="46a0c-146">Click Add.</span></span>
10. <span data-ttu-id="46a0c-147">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="46a0c-147">Click New to open the drop dialog.</span></span>
11. <span data-ttu-id="46a0c-148">A Név mezőbe írja be a „SWIFT” szöveget.</span><span class="sxs-lookup"><span data-stu-id="46a0c-148">In the Name field, type 'SWIFT'.</span></span>
12. <span data-ttu-id="46a0c-149">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="46a0c-149">Click Add.</span></span>
13. <span data-ttu-id="46a0c-150">A Leírás mezőben adja meg a következőt: „Bankazonosító kód”.</span><span class="sxs-lookup"><span data-stu-id="46a0c-150">In the Description field, enter 'Bank identification code'.</span></span> 
14. <span data-ttu-id="46a0c-151">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="46a0c-151">Click New to open the drop dialog.</span></span>
15. <span data-ttu-id="46a0c-152">A Név mezőbe írja be a „RoutingNumber” szöveget.</span><span class="sxs-lookup"><span data-stu-id="46a0c-152">In the Name field, type 'RoutingNumber'.</span></span>
16. <span data-ttu-id="46a0c-153">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="46a0c-153">Click Add.</span></span>
17. <span data-ttu-id="46a0c-154">A Leírás mezőben adja meg a következőt: „Regisztrációs azonosító száma”.</span><span class="sxs-lookup"><span data-stu-id="46a0c-154">In the Description field, enter 'Routing number'.</span></span>
18. <span data-ttu-id="46a0c-155">Kattintson az Előző keresése lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="46a0c-155">Click Find previous.</span></span>

## <a name="define-the-bank-account-structure-for-this-model"></a><span data-ttu-id="46a0c-156">Modell bankszámla-struktúrájának meghatározása</span><span class="sxs-lookup"><span data-stu-id="46a0c-156">Define the bank account structure for this model</span></span>
1. <span data-ttu-id="46a0c-157">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="46a0c-157">Click New to open the drop dialog.</span></span>
2. <span data-ttu-id="46a0c-158">A Név mezőbe írja be a „Számla” szöveget.</span><span class="sxs-lookup"><span data-stu-id="46a0c-158">In the Name field, type 'Account'.</span></span> 
3. <span data-ttu-id="46a0c-159">A Cikktípus mezőben válassza ki a „Rekord” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="46a0c-159">In the Item type field, select 'Record'.</span></span>
4. <span data-ttu-id="46a0c-160">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="46a0c-160">Click Add.</span></span>
5. <span data-ttu-id="46a0c-161">A Leírás mezőben adja meg a következőt: „A fél pénzintézetben (például a bank) vezetett számlájának azonosítása.”.</span><span class="sxs-lookup"><span data-stu-id="46a0c-161">In the Description field, enter 'Identification of an account of a party in a financial institution (for instance, a bank).'.</span></span>

    <span data-ttu-id="46a0c-162">A fél pénzintézetben (például a bank) vezetett számlájának azonosítása.</span><span class="sxs-lookup"><span data-stu-id="46a0c-162">Identification of an account of a party in a financial institution (for instance, a bank).</span></span>  

6. <span data-ttu-id="46a0c-163">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="46a0c-163">Click New to open the drop dialog.</span></span>
7. <span data-ttu-id="46a0c-164">A név mezőbe írja be a „Pénznem” szöveget.</span><span class="sxs-lookup"><span data-stu-id="46a0c-164">In the Name field, type 'Currency'.</span></span> 
8. <span data-ttu-id="46a0c-165">A Cikktípus mezőben válassza ki a „Karakterlánc” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="46a0c-165">In the Item type field, select 'String'.</span></span>
9. <span data-ttu-id="46a0c-166">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="46a0c-166">Click Add.</span></span>
10. <span data-ttu-id="46a0c-167">A Leírás mezőben adja meg a következőt: „Pénznemkód”.</span><span class="sxs-lookup"><span data-stu-id="46a0c-167">In the Description field, enter 'Currency code'.</span></span>
11. <span data-ttu-id="46a0c-168">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="46a0c-168">Click New to open the drop dialog.</span></span>
12. <span data-ttu-id="46a0c-169">A Név mezőbe írja be a „Szám” szöveget.</span><span class="sxs-lookup"><span data-stu-id="46a0c-169">In the Name field, type 'Number'.</span></span> 
13. <span data-ttu-id="46a0c-170">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="46a0c-170">Click Add.</span></span>
14. <span data-ttu-id="46a0c-171">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="46a0c-171">Click New to open the drop dialog.</span></span>
15. <span data-ttu-id="46a0c-172">A Név mezőbe írja be az „IBAN” szöveget.</span><span class="sxs-lookup"><span data-stu-id="46a0c-172">In the Name field, type 'IBAN'.</span></span> 
16. <span data-ttu-id="46a0c-173">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="46a0c-173">Click Add.</span></span>
17. <span data-ttu-id="46a0c-174">A Leírás mezőben adja meg a következőt: „Nemzetközi bankszámlaszám”.</span><span class="sxs-lookup"><span data-stu-id="46a0c-174">In the Description field, enter 'International bank account number'.</span></span>

## <a name="define-the-payment-message-structure-for-credit-transfer-payment-type"></a><span data-ttu-id="46a0c-175">A fizetési üzenetstruktúra meghatározása a jóváírási átmozgatás fizetési típusra</span><span class="sxs-lookup"><span data-stu-id="46a0c-175">Define the payment message structure for credit transfer payment type</span></span>
1. <span data-ttu-id="46a0c-176">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="46a0c-176">Click New to open the drop dialog.</span></span>
2. <span data-ttu-id="46a0c-177">Az Új csomópontként mezőben adja meg a következőt: „Modellgyökér”.</span><span class="sxs-lookup"><span data-stu-id="46a0c-177">In the New node as a field, enter 'Model root'.</span></span>
3. <span data-ttu-id="46a0c-178">A Név mezőbe írja be a „CustomerCreditTransferInitiation” szöveget.</span><span class="sxs-lookup"><span data-stu-id="46a0c-178">In the Name field, type 'CustomerCreditTransferInitiation'.</span></span>
4. <span data-ttu-id="46a0c-179">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="46a0c-179">Click Add.</span></span>
5. <span data-ttu-id="46a0c-180">A Keresés mezőbe írja be a „CustomerCreditTransferInitiation” szöveget.</span><span class="sxs-lookup"><span data-stu-id="46a0c-180">In the Find field, type 'CustomerCreditTransferInitiation'.</span></span> 
6. <span data-ttu-id="46a0c-181">Kattintson az Előző keresése lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="46a0c-181">Click Find previous.</span></span>
7. <span data-ttu-id="46a0c-182">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="46a0c-182">Click New to open the drop dialog.</span></span>
8. <span data-ttu-id="46a0c-183">A Név mezőbe írja be a „MessageIdentification” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="46a0c-183">In the Name field, type 'MessageIdentification'.</span></span> 
9. <span data-ttu-id="46a0c-184">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="46a0c-184">Click Add.</span></span>
10. <span data-ttu-id="46a0c-185">A Leírás mezőben adja meg „A pontról pontra mutató hivatkozás, amelyet az utasító fél rendel hozzá az üzenethez (majd küld tovább a következő félnek) az üzenet azonosításához.” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="46a0c-185">In the Description field, enter 'The point-to-point reference assigned by the instructing party (and sent to the next party) to identify a message.'.</span></span>

    <span data-ttu-id="46a0c-186">A pontról pontra mutató hivatkozás, amelyet az utasító fél rendel hozzá az üzenethez (majd küld tovább a következő félnek) az üzenet egyértelmű azonosításához.</span><span class="sxs-lookup"><span data-stu-id="46a0c-186">The point-to-point reference assigned by the instructing party (and sent to the next party) to identify a message.</span></span>  

11. <span data-ttu-id="46a0c-187">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="46a0c-187">Click New to open the drop dialog.</span></span>
12. <span data-ttu-id="46a0c-188">A Név mezőbe írja be az „ProcessingDateTime” szöveget.</span><span class="sxs-lookup"><span data-stu-id="46a0c-188">In the Name field, type 'ProcessingDateTime'.</span></span>
13. <span data-ttu-id="46a0c-189">A Cikktípus mezőben válassza ki a „DateTime” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="46a0c-189">In the Item type field, select 'DateTime'.</span></span>
14. <span data-ttu-id="46a0c-190">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="46a0c-190">Click Add.</span></span>
15. <span data-ttu-id="46a0c-191">A Leírás mezőben adja meg az „A fizetési üzenet létrehozásának dátuma és ideje” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="46a0c-191">In the Description field, enter 'Date and time at which the payment message was created.'.</span></span> 
16. <span data-ttu-id="46a0c-192">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="46a0c-192">Click New to open the drop dialog.</span></span>

    <span data-ttu-id="46a0c-193">Modell fizetési tranzakciós struktúrájának meghatározása.</span><span class="sxs-lookup"><span data-stu-id="46a0c-193">Define the payment transaction structure for this model.</span></span>  

17. <span data-ttu-id="46a0c-194">A Név mezőbe írja be a „Fizetések” szöveget.</span><span class="sxs-lookup"><span data-stu-id="46a0c-194">In the Name field, type 'Payments'.</span></span>
18. <span data-ttu-id="46a0c-195">A Cikktípus mezőben válassza ki a „Rekordlista” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="46a0c-195">In the Item type field, select 'Record list'.</span></span>
19. <span data-ttu-id="46a0c-196">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="46a0c-196">Click Add.</span></span>
20. <span data-ttu-id="46a0c-197">A Leírás mezőben adja meg a „Az aktuális üzenet fizetési sorai” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="46a0c-197">In the Description field, enter 'Payment lines of the current message'.</span></span>
21. <span data-ttu-id="46a0c-198">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="46a0c-198">Click New to open the drop dialog.</span></span>
22. <span data-ttu-id="46a0c-199">A Név mezőbe írja be a „Hitelező” szöveget.</span><span class="sxs-lookup"><span data-stu-id="46a0c-199">In the Name field, type 'Creditor'.</span></span> 
23. <span data-ttu-id="46a0c-200">A Cikktípus mezőben válassza ki a „Rekord” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="46a0c-200">In the Item type field, select 'Record'.</span></span>
24. <span data-ttu-id="46a0c-201">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="46a0c-201">Click Add.</span></span>
25. <span data-ttu-id="46a0c-202">A Leírás mezőben adja meg az „Az a fél, amely egy pénzösszegre jogosult” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="46a0c-202">In the Description field, enter 'Party to which an amount of money is due.'.</span></span> 
26. <span data-ttu-id="46a0c-203">Kattintson a Cikkhivatkozás átváltása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="46a0c-203">Click Switch item reference.</span></span>
27. <span data-ttu-id="46a0c-204">A Keresés mezőbe írja be a következőt: „Fél”.</span><span class="sxs-lookup"><span data-stu-id="46a0c-204">In the Find field, type 'Party'.</span></span>
28. <span data-ttu-id="46a0c-205">Kattintson a Következő keresése lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="46a0c-205">Click Find next.</span></span>
29. <span data-ttu-id="46a0c-206">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="46a0c-206">Click OK.</span></span>
30. <span data-ttu-id="46a0c-207">A Keresés mezőbe írja be a „Fizetések” szöveget.</span><span class="sxs-lookup"><span data-stu-id="46a0c-207">In the Find field, type 'Payments'.</span></span>
31. <span data-ttu-id="46a0c-208">Kattintson a Következő keresése lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="46a0c-208">Click Find next.</span></span>
32. <span data-ttu-id="46a0c-209">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="46a0c-209">Click New to open the drop dialog.</span></span>
33. <span data-ttu-id="46a0c-210">A Név mezőbe írja be a „Kötelezett” szöveget.</span><span class="sxs-lookup"><span data-stu-id="46a0c-210">In the Name field, type 'Debtor'.</span></span> 
34. <span data-ttu-id="46a0c-211">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="46a0c-211">Click Add.</span></span>
35. <span data-ttu-id="46a0c-212">A Leírás mezőben adja meg „Az a fél, amely tartozik egy pénzösszeggel a (végső) hitelezőnek” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="46a0c-212">In the Description field, enter 'Party that owes an amount of money to the (ultimate) creditor.'.</span></span>
36. <span data-ttu-id="46a0c-213">Kattintson a Cikkhivatkozás átváltása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="46a0c-213">Click Switch item reference.</span></span>
37. <span data-ttu-id="46a0c-214">A Keresés mezőbe írja be a következőt: „Fél”.</span><span class="sxs-lookup"><span data-stu-id="46a0c-214">In the Find field, type 'Party'.</span></span>
38. <span data-ttu-id="46a0c-215">Kattintson a Következő keresése lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="46a0c-215">Click Find next.</span></span>
39. <span data-ttu-id="46a0c-216">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="46a0c-216">Click OK.</span></span>
40. <span data-ttu-id="46a0c-217">Kattintson a Következő keresése lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="46a0c-217">Click Find next.</span></span>
41. <span data-ttu-id="46a0c-218">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="46a0c-218">Click New to open the drop dialog.</span></span>
42. <span data-ttu-id="46a0c-219">A Név mezőbe írja be a „Leírás” szöveget.</span><span class="sxs-lookup"><span data-stu-id="46a0c-219">In the Name field, type 'Description'.</span></span>
43. <span data-ttu-id="46a0c-220">A Cikktípus mezőben válassza ki a „Karakterlánc” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="46a0c-220">In the Item type field, select 'String'.</span></span>
44. <span data-ttu-id="46a0c-221">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="46a0c-221">Click Add.</span></span>
45. <span data-ttu-id="46a0c-222">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="46a0c-222">Click New to open the drop dialog.</span></span>
46. <span data-ttu-id="46a0c-223">A név mezőbe írja be a „Pénznem” szöveget.</span><span class="sxs-lookup"><span data-stu-id="46a0c-223">In the Name field, type 'Currency'.</span></span>
47. <span data-ttu-id="46a0c-224">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="46a0c-224">Click Add.</span></span>
48. <span data-ttu-id="46a0c-225">A Leírás mezőben adja meg a következőt: „Pénznemkód”.</span><span class="sxs-lookup"><span data-stu-id="46a0c-225">In the Description field, enter 'Currency code'.</span></span>
49. <span data-ttu-id="46a0c-226">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="46a0c-226">Click New to open the drop dialog.</span></span>
50. <span data-ttu-id="46a0c-227">A Név mezőbe írja be a „TransactionDate” szöveget.</span><span class="sxs-lookup"><span data-stu-id="46a0c-227">In the Name field, type 'TransactionDate'.</span></span> 
51. <span data-ttu-id="46a0c-228">A Cikktípus mezőben válassza ki a „Dátum” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="46a0c-228">In the Item type field, select 'Date'.</span></span>
52. <span data-ttu-id="46a0c-229">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="46a0c-229">Click Add.</span></span>
53. <span data-ttu-id="46a0c-230">A Leírás mezőben adja meg a következőt: „Tranzakció dátuma”.</span><span class="sxs-lookup"><span data-stu-id="46a0c-230">In the Description field, enter 'Transaction date'.</span></span> 
54. <span data-ttu-id="46a0c-231">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="46a0c-231">Click New to open the drop dialog.</span></span>
55. <span data-ttu-id="46a0c-232">A Név mezőbe írja be az „InstructedAmount” szöveget.</span><span class="sxs-lookup"><span data-stu-id="46a0c-232">In the Name field, type 'InstructedAmount'.</span></span>  
56. <span data-ttu-id="46a0c-233">A Cikktípus mezőben válassza ki a „Valós” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="46a0c-233">In the Item type field, select 'Real'.</span></span>
57. <span data-ttu-id="46a0c-234">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="46a0c-234">Click Add.</span></span>
58. <span data-ttu-id="46a0c-235">A Leírás mezőben adja meg „A kötelezett és a hitelező között továbbítandó pénzösszeg, a költségek levonása előtt.</span><span class="sxs-lookup"><span data-stu-id="46a0c-235">In the Description field, enter 'The amount of money to be moved between the debtor and creditor, before deduction of charges.</span></span> <span data-ttu-id="46a0c-236">Az összeget a kezdeményező fél által meghatározott pénznemben kell kifejezni.” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="46a0c-236">The amount should be expressed in the currency as ordered by the initiating party.'.</span></span>

    <span data-ttu-id="46a0c-237">A kötelezett és a hitelező között továbbítandó pénzösszeg, a költségek levonása előtt.</span><span class="sxs-lookup"><span data-stu-id="46a0c-237">The amount of money to be moved between the debtor and creditor, before deduction of charges.</span></span> <span data-ttu-id="46a0c-238">Az összeget a kezdeményező fél által meghatározott pénznemben kell kifejezni.</span><span class="sxs-lookup"><span data-stu-id="46a0c-238">The amount should be expressed in the currency as ordered by the initiating party.</span></span>  

59. <span data-ttu-id="46a0c-239">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="46a0c-239">Click New to open the drop dialog.</span></span>
60. <span data-ttu-id="46a0c-240">A Név mezőbe írja be az „End2EndID” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="46a0c-240">In the Name field, type 'End2EndID'.</span></span> 
61. <span data-ttu-id="46a0c-241">A Cikktípus mezőben válassza ki a „Karakterlánc” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="46a0c-241">In the Item type field, select 'String'.</span></span>
62. <span data-ttu-id="46a0c-242">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="46a0c-242">Click Add.</span></span>
63. <span data-ttu-id="46a0c-243">A Leírás mezőben adja meg „Az egyedi azonosító, amelyet a kezdeményező fél rendel hozzá az üzenethez.</span><span class="sxs-lookup"><span data-stu-id="46a0c-243">In the Description field, enter 'The unique identification assigned by the initiating party.</span></span> <span data-ttu-id="46a0c-244">Ezt az azonosítót a rendszer változtatás nélkül továbbítja a teljes láncon a végpontok között.” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="46a0c-244">This identification is passed on, unchanged, throughout the entire end-to-end chain.'.</span></span> 
64. <span data-ttu-id="46a0c-245">A Név mezőbe írja be a „PaymentModel” szöveget.</span><span class="sxs-lookup"><span data-stu-id="46a0c-245">In the Name field, type 'PaymentModel'.</span></span>

    <span data-ttu-id="46a0c-246">A Fizetési modell neve megfelel a fizetési formák előre meghatározott interfészeinek.</span><span class="sxs-lookup"><span data-stu-id="46a0c-246">The PaymentModel name aligns with predefined interfaces of payment forms.</span></span>  

65. <span data-ttu-id="46a0c-247">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="46a0c-247">Click Save.</span></span>
66. <span data-ttu-id="46a0c-248">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="46a0c-248">Close the page.</span></span>



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]