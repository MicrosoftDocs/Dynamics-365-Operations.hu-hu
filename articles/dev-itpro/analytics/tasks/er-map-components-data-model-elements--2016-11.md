---
title: ER – A létrehozott formátum összetevőinek leképezése az adatmodellelemekre (2016. november)
description: Az alábbi eljárás azt mutatja, hogy egy Rendszergazda vagy Elektronikus jelentések fejlesztője szerepkörű felhasználó miként képezhet le adatmodellelemeket a létrehozott elektronikusjelentési-konfigurációra, amely egy elektronikus dokumentumformátumot határoz meg a kifizetések üzleti tartománya számára.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, EROperationDesigner
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a24ef0e091379f14a163a6385be988143a1ec608
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1544334"
---
# <a name="er-map-components-of-the-created-format-to-data-model-elements-november-2016"></a><span data-ttu-id="e3bbf-103">ER – A létrehozott formátum összetevőinek leképezése az adatmodellelemekre (2016. november)</span><span class="sxs-lookup"><span data-stu-id="e3bbf-103">ER Map components of the created format to data model elements (November 2016)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e3bbf-104">Az alábbi eljárás azt mutatja, hogy egy Rendszergazda vagy Elektronikus jelentések fejlesztője szerepkörű felhasználó miként képezhet le adatmodellelemeket a létrehozott elektronikusjelentési-konfigurációra, amely egy elektronikus dokumentumformátumot határoz meg a kifizetések üzleti tartománya számára.</span><span class="sxs-lookup"><span data-stu-id="e3bbf-104">The following procedure shows how a user in either the System administrator or Electronic reporting developer role can map data model elements to components of the created Electronic reporting (ER) configuration, which defines an electronic document format for the payments business domain.</span></span> <span data-ttu-id="e3bbf-105">A formátumot a rendszer később elektronikus dokumentumok létrehozására használja majd a kifizetések feldolgozásához.</span><span class="sxs-lookup"><span data-stu-id="e3bbf-105">This format will be used later to generate electronic documents for processing payments.</span></span> <span data-ttu-id="e3bbf-106">Ebben a példában egy formátumkonfigurációt hozunk létre a Litware, Inc. mintavállalat számára.</span><span class="sxs-lookup"><span data-stu-id="e3bbf-106">In this example, you will create a format configuration for the sample company, ‘Litware, Inc.’.</span></span> <span data-ttu-id="e3bbf-107">Ezeket a lépéseket a vállalat között megosztott ER konfigurációjaként minden vállalatnál végrehajthatja.</span><span class="sxs-lookup"><span data-stu-id="e3bbf-107">These steps can be performed in any company as ER configurations are shared for all companies.</span></span> <span data-ttu-id="e3bbf-108">Ezeknek a lépéseknek a végrehajtásához először hajtsa végre az „Új formátumkonfiguráció létrehozása” feladat-útmutató lépéseit.</span><span class="sxs-lookup"><span data-stu-id="e3bbf-108">To complete these steps, you must first complete the steps in the “Create a format configuration” task guide.</span></span>


## <a name="select-a-format-configuration"></a><span data-ttu-id="e3bbf-109">Formátumkonfiguráció kiválasztása</span><span class="sxs-lookup"><span data-stu-id="e3bbf-109">Select a format configuration</span></span>
1. <span data-ttu-id="e3bbf-110">Ugorjon a Szervezeti adminisztráció > Munkaterületek > Elektronikus jelentés pontra.</span><span class="sxs-lookup"><span data-stu-id="e3bbf-110">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="e3bbf-111">Kattintson a Jelentéskészítés konfigurációi lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e3bbf-111">Click Reporting configurations.</span></span>
3. <span data-ttu-id="e3bbf-112">A fastruktúrában bontsa ki a „Kifizetések (egyszerűsített modell)” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e3bbf-112">In the tree, expand 'Payments (simplified model)'.</span></span>
4. <span data-ttu-id="e3bbf-113">A fastruktúrában válassza ki a „Kifizetések (egyszerűsített modell\BACS (UK fiktív)”.</span><span class="sxs-lookup"><span data-stu-id="e3bbf-113">In the tree, select 'Payments (simplified model)\BACS (UK fictitious)'.</span></span>
5. <span data-ttu-id="e3bbf-114">Kattintson a Tervező pontra.</span><span class="sxs-lookup"><span data-stu-id="e3bbf-114">Click Designer.</span></span>

## <a name="map-format-components-to-data-model-elements"></a><span data-ttu-id="e3bbf-115">Formátum-összetevők leképezése adatmodell-elemekhez</span><span class="sxs-lookup"><span data-stu-id="e3bbf-115">Map format components to data model elements</span></span>
1. <span data-ttu-id="e3bbf-116">Kattintson a Csomópont kibontása/összecsukása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e3bbf-116">Click Expand/collapse.</span></span>
2. <span data-ttu-id="e3bbf-117">Kattintson a Hozzárendelés fülre.</span><span class="sxs-lookup"><span data-stu-id="e3bbf-117">Click the Mapping tab.</span></span>
3. <span data-ttu-id="e3bbf-118">A fában bontsa ki a „model” elemet.</span><span class="sxs-lookup"><span data-stu-id="e3bbf-118">In the tree, expand 'model'.</span></span>
4. <span data-ttu-id="e3bbf-119">A fastruktúrában válassza ki ezt: „Xml\Üzenet\ProcessingDate\DateTime”.</span><span class="sxs-lookup"><span data-stu-id="e3bbf-119">In the tree, select 'Xml\Message\ProcessingDate\DateTime'.</span></span>
5. <span data-ttu-id="e3bbf-120">A fastruktúrában válassza ki ezt: „modell\ProcessingDateTime”.</span><span class="sxs-lookup"><span data-stu-id="e3bbf-120">In the tree, select 'model\ProcessingDateTime'.</span></span>
6. <span data-ttu-id="e3bbf-121">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="e3bbf-121">Click Bind.</span></span>
7. <span data-ttu-id="e3bbf-122">A fastruktúrában válassza ki ezt: „Xml\Üzenet\MessageId\Karakterlánc”.</span><span class="sxs-lookup"><span data-stu-id="e3bbf-122">In the tree, select 'Xml\Message\MessageId\String'.</span></span>
8. <span data-ttu-id="e3bbf-123">A fastruktúrában válassza ki a „modell\MessageIdentification” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e3bbf-123">In the tree, select 'model\MessageIdentification'.</span></span>
9. <span data-ttu-id="e3bbf-124">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="e3bbf-124">Click Bind.</span></span>
10. <span data-ttu-id="e3bbf-125">A fában bontsa ki a „model\Payments” elemet.</span><span class="sxs-lookup"><span data-stu-id="e3bbf-125">In the tree, expand 'model\Payments'.</span></span>
11. <span data-ttu-id="e3bbf-126">A fastruktúrában válassza ki ezt: „Xml\Üzenet\Fizetések\Cikk\Összeg\Karakterlánc”.</span><span class="sxs-lookup"><span data-stu-id="e3bbf-126">In the tree, select 'Xml\Message\Payments\Item\Amount\String'.</span></span>
12. <span data-ttu-id="e3bbf-127">A fastruktúrában válassza ki ezt: „modell\Fizetések\InstructedAmount”.</span><span class="sxs-lookup"><span data-stu-id="e3bbf-127">In the tree, select 'model\Payments\InstructedAmount'.</span></span>
13. <span data-ttu-id="e3bbf-128">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="e3bbf-128">Click Bind.</span></span>
14. <span data-ttu-id="e3bbf-129">A fastruktúrában válassza ki ezt: „Xml\Üzenet\Fizetések\Cikk\TransDate\DateTime”.</span><span class="sxs-lookup"><span data-stu-id="e3bbf-129">In the tree, select 'Xml\Message\Payments\Item\TransDate\DateTime'.</span></span>
15. <span data-ttu-id="e3bbf-130">A fastruktúrában válassza ki ezt: „modell\Fizetések\TransactionDate”.</span><span class="sxs-lookup"><span data-stu-id="e3bbf-130">In the tree, select 'model\Payments\TransactionDate'.</span></span>
16. <span data-ttu-id="e3bbf-131">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="e3bbf-131">Click Bind.</span></span>
17. <span data-ttu-id="e3bbf-132">A fastruktúrában válassza ki ezt: „Xml\Üzenet\Fizetések\Cikk\Leírás\Karakterlánc”.</span><span class="sxs-lookup"><span data-stu-id="e3bbf-132">In the tree, select 'Xml\Message\Payments\Item\Description\String'.</span></span>
18. <span data-ttu-id="e3bbf-133">A fán válassza ki a következőt: „model\Payments\Description”.</span><span class="sxs-lookup"><span data-stu-id="e3bbf-133">In the tree, select 'model\Payments\Description'.</span></span>
19. <span data-ttu-id="e3bbf-134">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="e3bbf-134">Click Bind.</span></span>
20. <span data-ttu-id="e3bbf-135">A fastruktúrában válassza ki ezt: „Xml\Üzenet\Fizetések\Cikk\Pénznem\Karakterlánc”.</span><span class="sxs-lookup"><span data-stu-id="e3bbf-135">In the tree, select 'Xml\Message\Payments\Item\Currency\String'.</span></span>
21. <span data-ttu-id="e3bbf-136">A fastruktúrában válassza ki a „Modell\Kifizetések\Pénznem” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e3bbf-136">In the tree, select 'model\Payments\Currency'.</span></span>
22. <span data-ttu-id="e3bbf-137">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="e3bbf-137">Click Bind.</span></span>
23. <span data-ttu-id="e3bbf-138">A fastruktúrában válassza ki ezt: „Xml\Üzenet\Fizetések\Cikk\Azonosító”.</span><span class="sxs-lookup"><span data-stu-id="e3bbf-138">In the tree, select 'Xml\Message\Payments\Item\Id'.</span></span>
24. <span data-ttu-id="e3bbf-139">A fastruktúrában válassza ki a „modell\Fizetések\End2EndID” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e3bbf-139">In the tree, select 'model\Payments\End2EndID'.</span></span>
25. <span data-ttu-id="e3bbf-140">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="e3bbf-140">Click Bind.</span></span>
26. <span data-ttu-id="e3bbf-141">A fában bontsa ki a „model\Payments= Transactions\Creditor” elemet.</span><span class="sxs-lookup"><span data-stu-id="e3bbf-141">In the tree, expand 'model\Payments\Creditor'.</span></span>
27. <span data-ttu-id="e3bbf-142">A fában bontsa ki a következőt: „model\Payments\Creditor\Account”.</span><span class="sxs-lookup"><span data-stu-id="e3bbf-142">In the tree, expand 'model\Payments\Creditor\Account'.</span></span>
28. <span data-ttu-id="e3bbf-143">A fában bontsa ki a következőt: „model\Payments\Creditor\Agent”.</span><span class="sxs-lookup"><span data-stu-id="e3bbf-143">In the tree, expand 'model\Payments\Creditor\Agent'.</span></span>
29. <span data-ttu-id="e3bbf-144">A fastruktúrában válassza ki ezt: „Xml\Üzenet\Fizetések\Cikk\Szállító\Név\Karakterlánc”.</span><span class="sxs-lookup"><span data-stu-id="e3bbf-144">In the tree, select 'Xml\Message\Payments\Item\Vendor\Name\String'.</span></span>
30. <span data-ttu-id="e3bbf-145">A fán válassza ki „model\Kifizetések = Transactions\Creditor\Name” pontot.</span><span class="sxs-lookup"><span data-stu-id="e3bbf-145">In the tree, select 'model\Payments\Creditor\Name'.</span></span>
31. <span data-ttu-id="e3bbf-146">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="e3bbf-146">Click Bind.</span></span>
32. <span data-ttu-id="e3bbf-147">A fastruktúrában válassza ki ezt: „Xml\Üzenet\Fizetések\Cikk\Szállító\Bank\RoutingNumber\Karakterlánc”.</span><span class="sxs-lookup"><span data-stu-id="e3bbf-147">In the tree, select 'Xml\Message\Payments\Item\Vendor\Bank\RoutingNumber\String'.</span></span>
33. <span data-ttu-id="e3bbf-148">A fastruktúrában válassza ki ezt: „modell\Fizetések\Beszedő\Ügynök\RoutingNumber”.</span><span class="sxs-lookup"><span data-stu-id="e3bbf-148">In the tree, select 'model\Payments\Creditor\Agent\RoutingNumber'.</span></span>
34. <span data-ttu-id="e3bbf-149">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="e3bbf-149">Click Bind.</span></span>
35. <span data-ttu-id="e3bbf-150">A fastruktúrában válassza ki ezt: „Xml\Üzenet\Fizetések\Cikk\Szállító\Bank\AccountNumber\Karakterlánc”.</span><span class="sxs-lookup"><span data-stu-id="e3bbf-150">In the tree, select 'Xml\Message\Payments\Item\Vendor\Bank\AccountNumber\String'.</span></span>
36. <span data-ttu-id="e3bbf-151">A fán válassza ki „model\Kifizetések = Transactions\Creditor\Account\Number” pontot.</span><span class="sxs-lookup"><span data-stu-id="e3bbf-151">In the tree, select 'model\Payments\Creditor\Account\Number'.</span></span>
37. <span data-ttu-id="e3bbf-152">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="e3bbf-152">Click Bind.</span></span>
38. <span data-ttu-id="e3bbf-153">A fastruktúrában válassza ki ezt: „Xml\Üzenet\Fizetések\Cikk\Fizető\Név\Karakterlánc”.</span><span class="sxs-lookup"><span data-stu-id="e3bbf-153">In the tree, select 'Xml\Message\Payments\Item\Payer\Name\String'.</span></span>
39. <span data-ttu-id="e3bbf-154">A fában bontsa ki a „model\Payments= Transactions\Debtor” elemet.</span><span class="sxs-lookup"><span data-stu-id="e3bbf-154">In the tree, expand 'model\Payments\Debtor'.</span></span>
40. <span data-ttu-id="e3bbf-155">A fában bontsa ki a következőt: „model\Payments\Debtor\Account”.</span><span class="sxs-lookup"><span data-stu-id="e3bbf-155">In the tree, expand 'model\Payments\Debtor\Account'.</span></span>
41. <span data-ttu-id="e3bbf-156">A fában bontsa ki a következőt: „model\Payments\Debtor\Agent”.</span><span class="sxs-lookup"><span data-stu-id="e3bbf-156">In the tree, expand 'model\Payments\Debtor\Agent'.</span></span>
42. <span data-ttu-id="e3bbf-157">A fán válassza ki „model\Kifizetések = Transactions\Debtor\Name” pontot.</span><span class="sxs-lookup"><span data-stu-id="e3bbf-157">In the tree, select 'model\Payments\Debtor\Name'.</span></span>
43. <span data-ttu-id="e3bbf-158">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="e3bbf-158">Click Bind.</span></span>
44. <span data-ttu-id="e3bbf-159">A fastruktúrában válassza ki ezt: „Xml\Üzenet\Fizetések\Cikk\Fizető\Bank\RoutingNumber\Karakterlánc”.</span><span class="sxs-lookup"><span data-stu-id="e3bbf-159">In the tree, select 'Xml\Message\Payments\Item\Payer\Bank\RoutingNumber\String'.</span></span>
45. <span data-ttu-id="e3bbf-160">A fastruktúrában válassza ki ezt: „modell\Fizetések\Kötelezett\Ügynök\RoutingNumber”.</span><span class="sxs-lookup"><span data-stu-id="e3bbf-160">In the tree, select 'model\Payments\Debtor\Agent\RoutingNumber'.</span></span>
46. <span data-ttu-id="e3bbf-161">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="e3bbf-161">Click Bind.</span></span>
47. <span data-ttu-id="e3bbf-162">A fastruktúrában válassza ki ezt: „Xml\Üzenet\Fizetések\Cikk\Fizető\Bank\AccountNumber\Karakterlánc”.</span><span class="sxs-lookup"><span data-stu-id="e3bbf-162">In the tree, select 'Xml\Message\Payments\Item\Payer\Bank\AccountNumber\String'.</span></span>
48. <span data-ttu-id="e3bbf-163">A fán válassza ki „model\Kifizetések = Transactions\Debtor\Account\Number” pontot.</span><span class="sxs-lookup"><span data-stu-id="e3bbf-163">In the tree, select 'model\Payments\Debtor\Account\Number'.</span></span>
49. <span data-ttu-id="e3bbf-164">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="e3bbf-164">Click Bind.</span></span>
50. <span data-ttu-id="e3bbf-165">A fastruktúrában válassza ki ezt: „Xml\Üzenet\Fizetések\Cikk”.</span><span class="sxs-lookup"><span data-stu-id="e3bbf-165">In the tree, select 'Xml\Message\Payments\Item'.</span></span>
51. <span data-ttu-id="e3bbf-166">A fán válassza ki a következőt: „model\Payments”.</span><span class="sxs-lookup"><span data-stu-id="e3bbf-166">In the tree, select 'model\Payments'.</span></span>
52. <span data-ttu-id="e3bbf-167">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="e3bbf-167">Click Bind.</span></span>
53. <span data-ttu-id="e3bbf-168">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="e3bbf-168">Click Save.</span></span>

## <a name="validate-format-mapping"></a><span data-ttu-id="e3bbf-169">Formátumleképezés ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="e3bbf-169">Validate format mapping</span></span>
1. <span data-ttu-id="e3bbf-170">Kattintson az Érvényesítés gombra.</span><span class="sxs-lookup"><span data-stu-id="e3bbf-170">Click Validate.</span></span>
    * <span data-ttu-id="e3bbf-171">Ellenőrizze az új hozzárendelést annak a biztosítására, hogy az összes kötés rendben legyen.</span><span class="sxs-lookup"><span data-stu-id="e3bbf-171">Validate the new mapping to ensure that all bindings are okay.</span></span>  
2. <span data-ttu-id="e3bbf-172">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="e3bbf-172">Close the page.</span></span>

## <a name="change-status-of-the-current-version-of-format-configuration"></a><span data-ttu-id="e3bbf-173">A formátumkonfiguráció aktuális verziójának állapotmódosítása</span><span class="sxs-lookup"><span data-stu-id="e3bbf-173">Change status of the current version of format configuration</span></span>
    * <span data-ttu-id="e3bbf-174">A következő lépésekben módosítsa a formátumkonfiguráció állapotát vázlatról teljesítettre, hogy elérhetővé tegye a fizetési dokumentumok létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="e3bbf-174">In the next steps, you’ll change the status of the format configuration from Draft to Completed to make it available for payment document generation.</span></span>  
1. <span data-ttu-id="e3bbf-175">Kattintson az Állapot módosítása elemre.</span><span class="sxs-lookup"><span data-stu-id="e3bbf-175">Click Change status.</span></span>
2. <span data-ttu-id="e3bbf-176">Kattintson a Befejezés gombra.</span><span class="sxs-lookup"><span data-stu-id="e3bbf-176">Click Complete.</span></span>
3. <span data-ttu-id="e3bbf-177">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="e3bbf-177">In the Description field, type a value.</span></span>
    * <span data-ttu-id="e3bbf-178">Például: „1-es verzió”.</span><span class="sxs-lookup"><span data-stu-id="e3bbf-178">For example, 'version 1'.</span></span>  
4. <span data-ttu-id="e3bbf-179">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="e3bbf-179">Click OK.</span></span>
5. <span data-ttu-id="e3bbf-180">Válassza ki az aktuális konfiguráció teljesített verzióját.</span><span class="sxs-lookup"><span data-stu-id="e3bbf-180">Select completed version of the current configuration.</span></span>
    * <span data-ttu-id="e3bbf-181">Fontos, hogy a konfiguráció teljesített 1.1-es verzióként lesz mentve: ez a formátum 1-es verziója, amely az adatmodell 1-es verzióján alapul.</span><span class="sxs-lookup"><span data-stu-id="e3bbf-181">Note that the configuration is saved as completed version 1.1: version 1 of the format based on the version 1 of the data model.</span></span>  

## <a name="define-effective-date-for-completed-version-of-format"></a><span data-ttu-id="e3bbf-182">Formátum teljesített verziójának érvénybe lépési dátumának meghatározása</span><span class="sxs-lookup"><span data-stu-id="e3bbf-182">Define effective date for completed version of format</span></span>
    * <span data-ttu-id="e3bbf-183">Minden egyes formátumverzió konfigurálható egy bizonyos dátumtól kezdve használatra.</span><span class="sxs-lookup"><span data-stu-id="e3bbf-183">Each format version can be configured as available for usage starting from a certain date.</span></span> <span data-ttu-id="e3bbf-184">Ha egynél több fájlformátum-verzió aktív egy meghatározott időpontban, a legújabb formátum (verziószáma alapján) lesz jelölve használatra.</span><span class="sxs-lookup"><span data-stu-id="e3bbf-184">When more than one format version is active on a certain date, the latest format (based on version number) will be selected for usage.</span></span> <span data-ttu-id="e3bbf-185">A munkamenet dátumértéke a megfelelő verzió kiválasztásához használatos.</span><span class="sxs-lookup"><span data-stu-id="e3bbf-185">The session date value is used for proper version selection.</span></span>  

## <a name="restrict-access-to-created-format-from-companies"></a><span data-ttu-id="e3bbf-186">Korlátozott hozzáférés a létrehozott formátumhoz a vállalatoktól</span><span class="sxs-lookup"><span data-stu-id="e3bbf-186">Restrict access to created format from companies</span></span>
1. <span data-ttu-id="e3bbf-187">Bontsa ki az ISO Ország/régió kódok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="e3bbf-187">Expand the ISO Country/region codes section.</span></span>
    * <span data-ttu-id="e3bbf-188">A formátum-hozzáférések korlátozhatók egyes országok/régiók azonosításával, amelyekben a formátumok alkalmazhatók.</span><span class="sxs-lookup"><span data-stu-id="e3bbf-188">Each format access can be restricted by identifying particular countries/regions in which a format is applicable.</span></span> <span data-ttu-id="e3bbf-189">Ha egy adott formátum országainak/régióinak listája üres, akkor ez a formátum használható bármely vállalatnál.</span><span class="sxs-lookup"><span data-stu-id="e3bbf-189">When the list of countries/regions for particular format is empty, this format can be used in any company.</span></span> <span data-ttu-id="e3bbf-190">Néhány ISO ország-/régiókód beszúrása esetén az országok/régiók adott listájába, a formátum csak akkor használható a vállalatokban, ha az elsődleges cím az országban/régióban van.</span><span class="sxs-lookup"><span data-stu-id="e3bbf-190">When some ISO country/region codes are inserted in the list of countries/regions, the format can only be use in companies if the primary address is in the country/region.</span></span>  

