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
ms.openlocfilehash: 9a033853be17d6013daa5550ca9c061198bb0330
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/27/2019
ms.locfileid: "2184738"
---
# <a name="er-map-components-of-the-created-format-to-data-model-elements-november-2016"></a><span data-ttu-id="677b9-103">ER – A létrehozott formátum összetevőinek leképezése az adatmodellelemekre (2016. november)</span><span class="sxs-lookup"><span data-stu-id="677b9-103">ER Map components of the created format to data model elements (November 2016)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="677b9-104">Az alábbi eljárás azt mutatja, hogy egy Rendszergazda vagy Elektronikus jelentések fejlesztője szerepkörű felhasználó miként képezhet le adatmodellelemeket a létrehozott elektronikusjelentési-konfigurációra, amely egy elektronikus dokumentumformátumot határoz meg a kifizetések üzleti tartománya számára.</span><span class="sxs-lookup"><span data-stu-id="677b9-104">The following procedure shows how a user in either the System administrator or Electronic reporting developer role can map data model elements to components of the created Electronic reporting (ER) configuration, which defines an electronic document format for the payments business domain.</span></span> <span data-ttu-id="677b9-105">A formátumot a rendszer később elektronikus dokumentumok létrehozására használja majd a kifizetések feldolgozásához.</span><span class="sxs-lookup"><span data-stu-id="677b9-105">This format will be used later to generate electronic documents for processing payments.</span></span> <span data-ttu-id="677b9-106">Ebben a példában egy formátumkonfigurációt hozunk létre a Litware, Inc. mintavállalat számára.</span><span class="sxs-lookup"><span data-stu-id="677b9-106">In this example, you will create a format configuration for the sample company, ‘Litware, Inc.’.</span></span> <span data-ttu-id="677b9-107">Ezeket a lépéseket a vállalat között megosztott ER konfigurációjaként minden vállalatnál végrehajthatja.</span><span class="sxs-lookup"><span data-stu-id="677b9-107">These steps can be performed in any company as ER configurations are shared for all companies.</span></span> <span data-ttu-id="677b9-108">Ezeknek a lépéseknek a végrehajtásához először hajtsa végre az „Új formátumkonfiguráció létrehozása” feladat-útmutató lépéseit.</span><span class="sxs-lookup"><span data-stu-id="677b9-108">To complete these steps, you must first complete the steps in the “Create a format configuration” task guide.</span></span>


## <a name="select-a-format-configuration"></a><span data-ttu-id="677b9-109">Formátumkonfiguráció kiválasztása</span><span class="sxs-lookup"><span data-stu-id="677b9-109">Select a format configuration</span></span>
1. <span data-ttu-id="677b9-110">Ugorjon a Szervezeti adminisztráció > Munkaterületek > Elektronikus jelentés pontra.</span><span class="sxs-lookup"><span data-stu-id="677b9-110">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="677b9-111">Kattintson a Jelentéskészítés konfigurációi lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="677b9-111">Click Reporting configurations.</span></span>
3. <span data-ttu-id="677b9-112">A fastruktúrában bontsa ki a „Kifizetések (egyszerűsített modell)” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="677b9-112">In the tree, expand 'Payments (simplified model)'.</span></span>
4. <span data-ttu-id="677b9-113">A fastruktúrában válassza ki a „Kifizetések (egyszerűsített modell\BACS (UK fiktív)”.</span><span class="sxs-lookup"><span data-stu-id="677b9-113">In the tree, select 'Payments (simplified model)\BACS (UK fictitious)'.</span></span>
5. <span data-ttu-id="677b9-114">Kattintson a Tervező pontra.</span><span class="sxs-lookup"><span data-stu-id="677b9-114">Click Designer.</span></span>

## <a name="map-format-components-to-data-model-elements"></a><span data-ttu-id="677b9-115">Formátum-összetevők leképezése adatmodell-elemekhez</span><span class="sxs-lookup"><span data-stu-id="677b9-115">Map format components to data model elements</span></span>
1. <span data-ttu-id="677b9-116">Kattintson a Csomópont kibontása/összecsukása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="677b9-116">Click Expand/collapse.</span></span>
2. <span data-ttu-id="677b9-117">Kattintson a Hozzárendelés fülre.</span><span class="sxs-lookup"><span data-stu-id="677b9-117">Click the Mapping tab.</span></span>
3. <span data-ttu-id="677b9-118">A fában bontsa ki a „model” elemet.</span><span class="sxs-lookup"><span data-stu-id="677b9-118">In the tree, expand 'model'.</span></span>
4. <span data-ttu-id="677b9-119">A fastruktúrában válassza ki ezt: „Xml\Üzenet\ProcessingDate\DateTime”.</span><span class="sxs-lookup"><span data-stu-id="677b9-119">In the tree, select 'Xml\Message\ProcessingDate\DateTime'.</span></span>
5. <span data-ttu-id="677b9-120">A fastruktúrában válassza ki ezt: „modell\ProcessingDateTime”.</span><span class="sxs-lookup"><span data-stu-id="677b9-120">In the tree, select 'model\ProcessingDateTime'.</span></span>
6. <span data-ttu-id="677b9-121">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="677b9-121">Click Bind.</span></span>
7. <span data-ttu-id="677b9-122">A fastruktúrában válassza ki ezt: „Xml\Üzenet\MessageId\Karakterlánc”.</span><span class="sxs-lookup"><span data-stu-id="677b9-122">In the tree, select 'Xml\Message\MessageId\String'.</span></span>
8. <span data-ttu-id="677b9-123">A fastruktúrában válassza ki a „modell\MessageIdentification” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="677b9-123">In the tree, select 'model\MessageIdentification'.</span></span>
9. <span data-ttu-id="677b9-124">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="677b9-124">Click Bind.</span></span>
10. <span data-ttu-id="677b9-125">A fában bontsa ki a „model\Payments” elemet.</span><span class="sxs-lookup"><span data-stu-id="677b9-125">In the tree, expand 'model\Payments'.</span></span>
11. <span data-ttu-id="677b9-126">A fastruktúrában válassza ki ezt: „Xml\Üzenet\Fizetések\Cikk\Összeg\Karakterlánc”.</span><span class="sxs-lookup"><span data-stu-id="677b9-126">In the tree, select 'Xml\Message\Payments\Item\Amount\String'.</span></span>
12. <span data-ttu-id="677b9-127">A fastruktúrában válassza ki ezt: „modell\Fizetések\InstructedAmount”.</span><span class="sxs-lookup"><span data-stu-id="677b9-127">In the tree, select 'model\Payments\InstructedAmount'.</span></span>
13. <span data-ttu-id="677b9-128">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="677b9-128">Click Bind.</span></span>
14. <span data-ttu-id="677b9-129">A fastruktúrában válassza ki ezt: „Xml\Üzenet\Fizetések\Cikk\TransDate\DateTime”.</span><span class="sxs-lookup"><span data-stu-id="677b9-129">In the tree, select 'Xml\Message\Payments\Item\TransDate\DateTime'.</span></span>
15. <span data-ttu-id="677b9-130">A fastruktúrában válassza ki ezt: „modell\Fizetések\TransactionDate”.</span><span class="sxs-lookup"><span data-stu-id="677b9-130">In the tree, select 'model\Payments\TransactionDate'.</span></span>
16. <span data-ttu-id="677b9-131">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="677b9-131">Click Bind.</span></span>
17. <span data-ttu-id="677b9-132">A fastruktúrában válassza ki ezt: „Xml\Üzenet\Fizetések\Cikk\Leírás\Karakterlánc”.</span><span class="sxs-lookup"><span data-stu-id="677b9-132">In the tree, select 'Xml\Message\Payments\Item\Description\String'.</span></span>
18. <span data-ttu-id="677b9-133">A fán válassza ki a következőt: „model\Payments\Description”.</span><span class="sxs-lookup"><span data-stu-id="677b9-133">In the tree, select 'model\Payments\Description'.</span></span>
19. <span data-ttu-id="677b9-134">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="677b9-134">Click Bind.</span></span>
20. <span data-ttu-id="677b9-135">A fastruktúrában válassza ki ezt: „Xml\Üzenet\Fizetések\Cikk\Pénznem\Karakterlánc”.</span><span class="sxs-lookup"><span data-stu-id="677b9-135">In the tree, select 'Xml\Message\Payments\Item\Currency\String'.</span></span>
21. <span data-ttu-id="677b9-136">A fastruktúrában válassza ki a „Modell\Kifizetések\Pénznem” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="677b9-136">In the tree, select 'model\Payments\Currency'.</span></span>
22. <span data-ttu-id="677b9-137">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="677b9-137">Click Bind.</span></span>
23. <span data-ttu-id="677b9-138">A fastruktúrában válassza ki ezt: „Xml\Üzenet\Fizetések\Cikk\Azonosító”.</span><span class="sxs-lookup"><span data-stu-id="677b9-138">In the tree, select 'Xml\Message\Payments\Item\Id'.</span></span>
24. <span data-ttu-id="677b9-139">A fastruktúrában válassza ki a „modell\Fizetések\End2EndID” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="677b9-139">In the tree, select 'model\Payments\End2EndID'.</span></span>
25. <span data-ttu-id="677b9-140">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="677b9-140">Click Bind.</span></span>
26. <span data-ttu-id="677b9-141">A fában bontsa ki a „model\Payments= Transactions\Creditor” elemet.</span><span class="sxs-lookup"><span data-stu-id="677b9-141">In the tree, expand 'model\Payments\Creditor'.</span></span>
27. <span data-ttu-id="677b9-142">A fában bontsa ki a következőt: „model\Payments\Creditor\Account”.</span><span class="sxs-lookup"><span data-stu-id="677b9-142">In the tree, expand 'model\Payments\Creditor\Account'.</span></span>
28. <span data-ttu-id="677b9-143">A fában bontsa ki a következőt: „model\Payments\Creditor\Agent”.</span><span class="sxs-lookup"><span data-stu-id="677b9-143">In the tree, expand 'model\Payments\Creditor\Agent'.</span></span>
29. <span data-ttu-id="677b9-144">A fastruktúrában válassza ki ezt: „Xml\Üzenet\Fizetések\Cikk\Szállító\Név\Karakterlánc”.</span><span class="sxs-lookup"><span data-stu-id="677b9-144">In the tree, select 'Xml\Message\Payments\Item\Vendor\Name\String'.</span></span>
30. <span data-ttu-id="677b9-145">A fán válassza ki „model\Kifizetések = Transactions\Creditor\Name” pontot.</span><span class="sxs-lookup"><span data-stu-id="677b9-145">In the tree, select 'model\Payments\Creditor\Name'.</span></span>
31. <span data-ttu-id="677b9-146">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="677b9-146">Click Bind.</span></span>
32. <span data-ttu-id="677b9-147">A fastruktúrában válassza ki ezt: „Xml\Üzenet\Fizetések\Cikk\Szállító\Bank\RoutingNumber\Karakterlánc”.</span><span class="sxs-lookup"><span data-stu-id="677b9-147">In the tree, select 'Xml\Message\Payments\Item\Vendor\Bank\RoutingNumber\String'.</span></span>
33. <span data-ttu-id="677b9-148">A fastruktúrában válassza ki ezt: „modell\Fizetések\Beszedő\Ügynök\RoutingNumber”.</span><span class="sxs-lookup"><span data-stu-id="677b9-148">In the tree, select 'model\Payments\Creditor\Agent\RoutingNumber'.</span></span>
34. <span data-ttu-id="677b9-149">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="677b9-149">Click Bind.</span></span>
35. <span data-ttu-id="677b9-150">A fastruktúrában válassza ki ezt: „Xml\Üzenet\Fizetések\Cikk\Szállító\Bank\AccountNumber\Karakterlánc”.</span><span class="sxs-lookup"><span data-stu-id="677b9-150">In the tree, select 'Xml\Message\Payments\Item\Vendor\Bank\AccountNumber\String'.</span></span>
36. <span data-ttu-id="677b9-151">A fán válassza ki „model\Kifizetések = Transactions\Creditor\Account\Number” pontot.</span><span class="sxs-lookup"><span data-stu-id="677b9-151">In the tree, select 'model\Payments\Creditor\Account\Number'.</span></span>
37. <span data-ttu-id="677b9-152">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="677b9-152">Click Bind.</span></span>
38. <span data-ttu-id="677b9-153">A fastruktúrában válassza ki ezt: „Xml\Üzenet\Fizetések\Cikk\Fizető\Név\Karakterlánc”.</span><span class="sxs-lookup"><span data-stu-id="677b9-153">In the tree, select 'Xml\Message\Payments\Item\Payer\Name\String'.</span></span>
39. <span data-ttu-id="677b9-154">A fában bontsa ki a „model\Payments= Transactions\Debtor” elemet.</span><span class="sxs-lookup"><span data-stu-id="677b9-154">In the tree, expand 'model\Payments\Debtor'.</span></span>
40. <span data-ttu-id="677b9-155">A fában bontsa ki a következőt: „model\Payments\Debtor\Account”.</span><span class="sxs-lookup"><span data-stu-id="677b9-155">In the tree, expand 'model\Payments\Debtor\Account'.</span></span>
41. <span data-ttu-id="677b9-156">A fában bontsa ki a következőt: „model\Payments\Debtor\Agent”.</span><span class="sxs-lookup"><span data-stu-id="677b9-156">In the tree, expand 'model\Payments\Debtor\Agent'.</span></span>
42. <span data-ttu-id="677b9-157">A fán válassza ki „model\Kifizetések = Transactions\Debtor\Name” pontot.</span><span class="sxs-lookup"><span data-stu-id="677b9-157">In the tree, select 'model\Payments\Debtor\Name'.</span></span>
43. <span data-ttu-id="677b9-158">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="677b9-158">Click Bind.</span></span>
44. <span data-ttu-id="677b9-159">A fastruktúrában válassza ki ezt: „Xml\Üzenet\Fizetések\Cikk\Fizető\Bank\RoutingNumber\Karakterlánc”.</span><span class="sxs-lookup"><span data-stu-id="677b9-159">In the tree, select 'Xml\Message\Payments\Item\Payer\Bank\RoutingNumber\String'.</span></span>
45. <span data-ttu-id="677b9-160">A fastruktúrában válassza ki ezt: „modell\Fizetések\Kötelezett\Ügynök\RoutingNumber”.</span><span class="sxs-lookup"><span data-stu-id="677b9-160">In the tree, select 'model\Payments\Debtor\Agent\RoutingNumber'.</span></span>
46. <span data-ttu-id="677b9-161">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="677b9-161">Click Bind.</span></span>
47. <span data-ttu-id="677b9-162">A fastruktúrában válassza ki ezt: „Xml\Üzenet\Fizetések\Cikk\Fizető\Bank\AccountNumber\Karakterlánc”.</span><span class="sxs-lookup"><span data-stu-id="677b9-162">In the tree, select 'Xml\Message\Payments\Item\Payer\Bank\AccountNumber\String'.</span></span>
48. <span data-ttu-id="677b9-163">A fán válassza ki „model\Kifizetések = Transactions\Debtor\Account\Number” pontot.</span><span class="sxs-lookup"><span data-stu-id="677b9-163">In the tree, select 'model\Payments\Debtor\Account\Number'.</span></span>
49. <span data-ttu-id="677b9-164">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="677b9-164">Click Bind.</span></span>
50. <span data-ttu-id="677b9-165">A fastruktúrában válassza ki ezt: „Xml\Üzenet\Fizetések\Cikk”.</span><span class="sxs-lookup"><span data-stu-id="677b9-165">In the tree, select 'Xml\Message\Payments\Item'.</span></span>
51. <span data-ttu-id="677b9-166">A fán válassza ki a következőt: „model\Payments”.</span><span class="sxs-lookup"><span data-stu-id="677b9-166">In the tree, select 'model\Payments'.</span></span>
52. <span data-ttu-id="677b9-167">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="677b9-167">Click Bind.</span></span>
53. <span data-ttu-id="677b9-168">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="677b9-168">Click Save.</span></span>

## <a name="validate-format-mapping"></a><span data-ttu-id="677b9-169">Formátumleképezés ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="677b9-169">Validate format mapping</span></span>
1. <span data-ttu-id="677b9-170">Kattintson az Érvényesítés gombra.</span><span class="sxs-lookup"><span data-stu-id="677b9-170">Click Validate.</span></span>
    * <span data-ttu-id="677b9-171">Ellenőrizze az új hozzárendelést annak a biztosítására, hogy az összes kötés rendben legyen.</span><span class="sxs-lookup"><span data-stu-id="677b9-171">Validate the new mapping to ensure that all bindings are okay.</span></span>  
2. <span data-ttu-id="677b9-172">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="677b9-172">Close the page.</span></span>

## <a name="change-status-of-the-current-version-of-format-configuration"></a><span data-ttu-id="677b9-173">A formátumkonfiguráció aktuális verziójának állapotmódosítása</span><span class="sxs-lookup"><span data-stu-id="677b9-173">Change status of the current version of format configuration</span></span>
    * <span data-ttu-id="677b9-174">A következő lépésekben módosítsa a formátumkonfiguráció állapotát vázlatról teljesítettre, hogy elérhetővé tegye a fizetési dokumentumok létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="677b9-174">In the next steps, you’ll change the status of the format configuration from Draft to Completed to make it available for payment document generation.</span></span>  
1. <span data-ttu-id="677b9-175">Kattintson az Állapot módosítása elemre.</span><span class="sxs-lookup"><span data-stu-id="677b9-175">Click Change status.</span></span>
2. <span data-ttu-id="677b9-176">Kattintson a Befejezés gombra.</span><span class="sxs-lookup"><span data-stu-id="677b9-176">Click Complete.</span></span>
3. <span data-ttu-id="677b9-177">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="677b9-177">In the Description field, type a value.</span></span>
    * <span data-ttu-id="677b9-178">Például: „1-es verzió”.</span><span class="sxs-lookup"><span data-stu-id="677b9-178">For example, 'version 1'.</span></span>  
4. <span data-ttu-id="677b9-179">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="677b9-179">Click OK.</span></span>
5. <span data-ttu-id="677b9-180">Válassza ki az aktuális konfiguráció teljesített verzióját.</span><span class="sxs-lookup"><span data-stu-id="677b9-180">Select completed version of the current configuration.</span></span>
    * <span data-ttu-id="677b9-181">Fontos, hogy a konfiguráció teljesített 1.1-es verzióként lesz mentve: ez a formátum 1-es verziója, amely az adatmodell 1-es verzióján alapul.</span><span class="sxs-lookup"><span data-stu-id="677b9-181">Note that the configuration is saved as completed version 1.1: version 1 of the format based on the version 1 of the data model.</span></span>  

## <a name="define-effective-date-for-completed-version-of-format"></a><span data-ttu-id="677b9-182">Formátum teljesített verziójának érvénybe lépési dátumának meghatározása</span><span class="sxs-lookup"><span data-stu-id="677b9-182">Define effective date for completed version of format</span></span>
    * <span data-ttu-id="677b9-183">Minden egyes formátumverzió konfigurálható egy bizonyos dátumtól kezdve használatra.</span><span class="sxs-lookup"><span data-stu-id="677b9-183">Each format version can be configured as available for usage starting from a certain date.</span></span> <span data-ttu-id="677b9-184">Ha egynél több fájlformátum-verzió aktív egy meghatározott időpontban, a legújabb formátum (verziószáma alapján) lesz jelölve használatra.</span><span class="sxs-lookup"><span data-stu-id="677b9-184">When more than one format version is active on a certain date, the latest format (based on version number) will be selected for usage.</span></span> <span data-ttu-id="677b9-185">A munkamenet dátumértéke a megfelelő verzió kiválasztásához használatos.</span><span class="sxs-lookup"><span data-stu-id="677b9-185">The session date value is used for proper version selection.</span></span>  

## <a name="restrict-access-to-created-format-from-companies"></a><span data-ttu-id="677b9-186">Korlátozott hozzáférés a létrehozott formátumhoz a vállalatoktól</span><span class="sxs-lookup"><span data-stu-id="677b9-186">Restrict access to created format from companies</span></span>
1. <span data-ttu-id="677b9-187">Bontsa ki az ISO Ország/régió kódok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="677b9-187">Expand the ISO Country/region codes section.</span></span>
    * <span data-ttu-id="677b9-188">A formátum-hozzáférések korlátozhatók egyes országok/régiók azonosításával, amelyekben a formátumok alkalmazhatók.</span><span class="sxs-lookup"><span data-stu-id="677b9-188">Each format access can be restricted by identifying particular countries/regions in which a format is applicable.</span></span> <span data-ttu-id="677b9-189">Ha egy adott formátum országainak/régióinak listája üres, akkor ez a formátum használható bármely vállalatnál.</span><span class="sxs-lookup"><span data-stu-id="677b9-189">When the list of countries/regions for particular format is empty, this format can be used in any company.</span></span> <span data-ttu-id="677b9-190">Néhány ISO ország-/régiókód beszúrása esetén az országok/régiók adott listájába, a formátum csak akkor használható a vállalatokban, ha az elsődleges cím az országban/régióban van.</span><span class="sxs-lookup"><span data-stu-id="677b9-190">When some ISO country/region codes are inserted in the list of countries/regions, the format can only be use in companies if the primary address is in the country/region.</span></span>  

