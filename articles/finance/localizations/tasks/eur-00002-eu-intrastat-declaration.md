---
title: EUR 00002 Az EU Intrastat nyilatkozat létrehozása
description: Ez az eljárás bemutatja azokat a lépéseket, amelyeket el kell végezni az Intrastat nyilatkozat elektronikus fájlformátumba történő exportálásához és egy Excel fájlformátum bevallási dokumentumainak áttekintéséhez.
author: Anasyash
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionRepositoryTable, ERSolutionImport, IntrastatParameters, IntrastatCommodityLookup, IntrastatCompressParameters, Intrastat, SysQueryForm
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: anasyash
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e2aba5caaaf0fbee511e1a293b09fa8301bb6831
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/18/2020
ms.locfileid: "3145266"
---
# <a name="eur-00002-generate-an-eu-intrastat-declaration"></a><span data-ttu-id="e2bc0-103">EUR 00002 Az EU Intrastat nyilatkozat létrehozása</span><span class="sxs-lookup"><span data-stu-id="e2bc0-103">EUR-00002 Generate an EU Intrastat declaration</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="e2bc0-104">Ez az eljárás bemutatja azokat a lépéseket, amelyeket el kell végezni az Intrastat nyilatkozat elektronikus fájlformátumba történő exportálásához és egy Excel fájlformátum bevallási dokumentumainak áttekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="e2bc0-104">This procedure walks you through the steps required to export the Intrastat declaration in the electronic file format and preview the declaration data in an Excel format.</span></span> 

<span data-ttu-id="e2bc0-105">Mielőtt végrehajtaná ezt az eljárást, át kell helyeznie a tranzakciókat az Intrastatba.</span><span class="sxs-lookup"><span data-stu-id="e2bc0-105">Before you can complete this procedure, you must transfer transactions to the Intrastat.</span></span> 

<span data-ttu-id="e2bc0-106">Ez az eljárás a DEMF bemutatócég segítségével lett létrehozva.</span><span class="sxs-lookup"><span data-stu-id="e2bc0-106">This procedure was created using the demo data company DEMF.</span></span>


## <a name="import-configurations-with-settings"></a><span data-ttu-id="e2bc0-107">A konfiguráció beállításokkal történő importálása</span><span class="sxs-lookup"><span data-stu-id="e2bc0-107">Import configurations with settings</span></span>
1. <span data-ttu-id="e2bc0-108">Ugorjon a Munkaterületek > Elektronikus jelentés pontra</span><span class="sxs-lookup"><span data-stu-id="e2bc0-108">Go to Workspaces > Electronic reporting</span></span>
2. <span data-ttu-id="e2bc0-109">Kattintson erre: Beállítás aktívként.</span><span class="sxs-lookup"><span data-stu-id="e2bc0-109">Click Set active.</span></span>
3. <span data-ttu-id="e2bc0-110">Kattintson a Tárházak gombra.</span><span class="sxs-lookup"><span data-stu-id="e2bc0-110">Click Repositories.</span></span>
4. <span data-ttu-id="e2bc0-111">Kattintson a Megnyitás gombra.</span><span class="sxs-lookup"><span data-stu-id="e2bc0-111">Click Open.</span></span>
5. <span data-ttu-id="e2bc0-112">Nyissa meg a Konfiguráció neve oszlopszűrőt.</span><span class="sxs-lookup"><span data-stu-id="e2bc0-112">Open Configuration name column filter.</span></span>
6. <span data-ttu-id="e2bc0-113">Alkalmazzon szűrőt a „Konfiguráció neve” mezőben a „Intrastat (DE)” értékkel az „Ezzel kezdődik” szűrési operátor használatával.</span><span class="sxs-lookup"><span data-stu-id="e2bc0-113">Apply a filter on the "Configuration name" field, with a value of "Intrastat (DE)", using the "begins with" filter operator.</span></span>
    * <span data-ttu-id="e2bc0-114">Ki kell választania a jogi személy országára vonatkozó konfigurációs nevet.</span><span class="sxs-lookup"><span data-stu-id="e2bc0-114">You should select the configuration name applicable for the country of your legal entity.</span></span> <span data-ttu-id="e2bc0-115">Ez az eljárás a német jogi személyt (DEMF) példaként használja, ezért az „Intrastat” lehetőséget kell kiválasztani.</span><span class="sxs-lookup"><span data-stu-id="e2bc0-115">This procedure uses the German legal entity (DEMF) as an example, therefore "Intrastat (DE)" should be chosen.</span></span>  
    * <span data-ttu-id="e2bc0-116">Kattintson az Importálás, majd az Igen lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e2bc0-116">Click Import and then click Yes.</span></span>  
7. <span data-ttu-id="e2bc0-117">Nyissa meg a Konfiguráció neve oszlopszűrőt.</span><span class="sxs-lookup"><span data-stu-id="e2bc0-117">Open Configuration name column filter.</span></span>
8. <span data-ttu-id="e2bc0-118">Alkalmazzon szűrőt a „Konfiguráció neve” mezőben a „Intrastat jelentés” értékkel az „Ezzel kezdődik” szűrési operátor használatával.</span><span class="sxs-lookup"><span data-stu-id="e2bc0-118">Apply a filter on the "Configuration name" field, with a value of "intrastat report", using the "begins with" filter operator.</span></span>
    * <span data-ttu-id="e2bc0-119">Kattintson az Importálás, majd az Igen lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e2bc0-119">Click Import and then click Yes.</span></span>  

## <a name="set-up-foreign-trade-parameters"></a><span data-ttu-id="e2bc0-120">A Külkereskedelmi paraméterek beállítása</span><span class="sxs-lookup"><span data-stu-id="e2bc0-120">Set up Foreign trade parameters</span></span>
1. <span data-ttu-id="e2bc0-121">Ugrás az Adó > Beállítás > Külkereskedelem > Külkereskedelmi paraméterek pontra</span><span class="sxs-lookup"><span data-stu-id="e2bc0-121">Go to Tax > Setup > Foreign trade > Foreign trade parameters</span></span>
2. <span data-ttu-id="e2bc0-122">Bontsa ki az elektronikus jelentéskészítés szakaszát.</span><span class="sxs-lookup"><span data-stu-id="e2bc0-122">Expand the Electronic reporting section.</span></span>
3. <span data-ttu-id="e2bc0-123">A Fájlformátum-hozzárendelés mezőben adja meg vagy válassza ki a Intrastat (DE) értéket.</span><span class="sxs-lookup"><span data-stu-id="e2bc0-123">In the File format mapping field, enter or select a value Intrastat (DE)</span></span>
4. <span data-ttu-id="e2bc0-124">A Jelentésformátum-hozzárendelés mezőben adja meg vagy válassza ki a Intrastat jelentés értéket.</span><span class="sxs-lookup"><span data-stu-id="e2bc0-124">In the Report format mapping field, enter or select a value Intrastat report</span></span>
5. <span data-ttu-id="e2bc0-125">Bontsa ki a Kerekítési szabályok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="e2bc0-125">Expand the Rounding rules section.</span></span>
    * <span data-ttu-id="e2bc0-126">Be kell állítania azokat a kerekítési szabályokat, amelyek az országában/régiójában alkalmazhatóak az Intrastat-jelentésekhez.</span><span class="sxs-lookup"><span data-stu-id="e2bc0-126">You should set up rounding rules that are applicable in your country/region for Intrastat reporting.</span></span>  
6. <span data-ttu-id="e2bc0-127">A Kerekítési szabályok mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="e2bc0-127">In the Rounding rule field, enter a number.</span></span>
    * <span data-ttu-id="e2bc0-128">Adja meg a kerekítési pontosságot, például adja meg a „0,01” értéket.</span><span class="sxs-lookup"><span data-stu-id="e2bc0-128">Enter rounding precision, for example, enter '0.01'.</span></span>  
7. <span data-ttu-id="e2bc0-129">Adjon meg egy számot Az összeg tizedesjegyeinek száma mezőben.</span><span class="sxs-lookup"><span data-stu-id="e2bc0-129">In the Number of decimals for amount field, enter a number.</span></span>
    * <span data-ttu-id="e2bc0-130">Adja meg például a „2” értéket.</span><span class="sxs-lookup"><span data-stu-id="e2bc0-130">For example, enter '2'.</span></span>  
8. <span data-ttu-id="e2bc0-131">Válasszon ki egy lehetőséget a Kerekítés 1 kg alatt mezőben.</span><span class="sxs-lookup"><span data-stu-id="e2bc0-131">In the Rounding below 1 kg field, select an option.</span></span>
    * <span data-ttu-id="e2bc0-132">Válassza ki például a „Felkerekítés 1 kg-ra” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e2bc0-132">For example, select 'Rounding up to 1 kg'.</span></span>  
9. <span data-ttu-id="e2bc0-133">A Kerekítési szabályok mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="e2bc0-133">In the Rounding rule field, enter a number.</span></span>
    * <span data-ttu-id="e2bc0-134">Adja meg példáié az „1” a súly kerekítése az egész számhoz.</span><span class="sxs-lookup"><span data-stu-id="e2bc0-134">For example, enter '1' for rounding weight to the integer.</span></span>  
10. <span data-ttu-id="e2bc0-135">Bontsa ki a Minimumhatár szakaszt.</span><span class="sxs-lookup"><span data-stu-id="e2bc0-135">Expand the Minimum limit section.</span></span>
11. <span data-ttu-id="e2bc0-136">Adjon meg egy számot a Súly mezőben.</span><span class="sxs-lookup"><span data-stu-id="e2bc0-136">In the Weight field, enter a number.</span></span>
    * <span data-ttu-id="e2bc0-137">Adja meg, például minimális súlyként a „10”értéket.</span><span class="sxs-lookup"><span data-stu-id="e2bc0-137">For example, enter '10' as the minimum weight.</span></span>  
12. <span data-ttu-id="e2bc0-138">Az Összeg mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="e2bc0-138">In the Amount field, enter a number.</span></span>
    * <span data-ttu-id="e2bc0-139">Adja meg, például minimális összegként a „200” értéket.</span><span class="sxs-lookup"><span data-stu-id="e2bc0-139">For example, enter '200' as the minimum amount.</span></span>  
13. <span data-ttu-id="e2bc0-140">Az Árucikk mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="e2bc0-140">In the Commodity field, enter or select a value.</span></span>

## <a name="set-up-compression-of-intrastat"></a><span data-ttu-id="e2bc0-141">Az Intrastat Tömörítés beállítása</span><span class="sxs-lookup"><span data-stu-id="e2bc0-141">Set up Compression of Intrastat</span></span>
1. <span data-ttu-id="e2bc0-142">Ugorjon az Adó > Beállítás > Külkereskedelem > Intrastat tömörítése pontra.</span><span class="sxs-lookup"><span data-stu-id="e2bc0-142">Go to Tax > Setup > Foreign trade > Compression of Intrastat.</span></span>
2. <span data-ttu-id="e2bc0-143">Kattintson az Eltávolítás gombra.</span><span class="sxs-lookup"><span data-stu-id="e2bc0-143">Click Remove.</span></span>
3. <span data-ttu-id="e2bc0-144">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="e2bc0-144">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="e2bc0-145">Válassza ki például az Árucikk a Rendelkezésre álló szakaszban lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e2bc0-145">For example, select Commodity in the Available section.</span></span>  
4. <span data-ttu-id="e2bc0-146">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="e2bc0-146">Click Add.</span></span>

## <a name="generate-intrastat-declaration"></a><span data-ttu-id="e2bc0-147">Az Intrastat nyilatkozat létrehozása</span><span class="sxs-lookup"><span data-stu-id="e2bc0-147">Generate Intrastat declaration</span></span>
1. <span data-ttu-id="e2bc0-148">Ugorjon az Adó > Nyilatkozatok > Külkereskedelem > Intrastat pontra</span><span class="sxs-lookup"><span data-stu-id="e2bc0-148">Go to Tax > Declarations > Foreign trade > Intrastat</span></span>
2. <span data-ttu-id="e2bc0-149">Kattintson az Érvényesítés gombra.</span><span class="sxs-lookup"><span data-stu-id="e2bc0-149">Click Validate.</span></span>
    * <span data-ttu-id="e2bc0-150">A rendszer az ellenőrzést a Beállítások ellenőrzése mező szerint végzi el a Külkereskedelem paraméterei lapon.</span><span class="sxs-lookup"><span data-stu-id="e2bc0-150">The validation is done according to the Check setup field on the Foreign trade parameters page.</span></span>  
3. <span data-ttu-id="e2bc0-151">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="e2bc0-151">Click OK.</span></span>
4. <span data-ttu-id="e2bc0-152">Kattintson a Módosítás gombra.</span><span class="sxs-lookup"><span data-stu-id="e2bc0-152">Click Update.</span></span>
5. <span data-ttu-id="e2bc0-153">Kattintson a Minimumhatár lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e2bc0-153">Click Minimum limit.</span></span>
6. <span data-ttu-id="e2bc0-154">Adja meg a dátumot a Kezdő dátum mezőben.</span><span class="sxs-lookup"><span data-stu-id="e2bc0-154">In the Start date field, enter a date.</span></span>
    * <span data-ttu-id="e2bc0-155">Adja meg például a 2015. január 1-jei dátumot.</span><span class="sxs-lookup"><span data-stu-id="e2bc0-155">For example, enter January 1, 2015.</span></span>  
7. <span data-ttu-id="e2bc0-156">Válassza ki az Igen lehetőséget a Tömörítés mezőben.</span><span class="sxs-lookup"><span data-stu-id="e2bc0-156">Select Yes in the Compress field.</span></span>
8. <span data-ttu-id="e2bc0-157">Adja meg a dátumot a Záró dátum mezőben.</span><span class="sxs-lookup"><span data-stu-id="e2bc0-157">In the End date field, enter a date.</span></span>
    * <span data-ttu-id="e2bc0-158">Adja meg például a 2015. január 31-ei dátumot.</span><span class="sxs-lookup"><span data-stu-id="e2bc0-158">For example, enter January 31, 2015.</span></span>  
9. <span data-ttu-id="e2bc0-159">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="e2bc0-159">Click OK.</span></span>
10. <span data-ttu-id="e2bc0-160">Kattintson a Módosítás gombra.</span><span class="sxs-lookup"><span data-stu-id="e2bc0-160">Click Update.</span></span>
11. <span data-ttu-id="e2bc0-161">Kattintson a Tömörítés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e2bc0-161">Click Compress.</span></span>
    * <span data-ttu-id="e2bc0-162">Ezt a tömörítést a rendszer attól függően végzi el, hogy hogyan állítják be az Intrastat beállítások Tömörítését.</span><span class="sxs-lookup"><span data-stu-id="e2bc0-162">This compression happens according to how you set the Compression of intrastate settings.</span></span>  
12. <span data-ttu-id="e2bc0-163">Adja meg a dátumot a Kezdő dátum mezőben.</span><span class="sxs-lookup"><span data-stu-id="e2bc0-163">In the Start date field, enter a date.</span></span>
    * <span data-ttu-id="e2bc0-164">Adja meg például a 2015. január 1-jei dátumot.</span><span class="sxs-lookup"><span data-stu-id="e2bc0-164">For example, enter January 1, 2015.</span></span>  
13. <span data-ttu-id="e2bc0-165">Adja meg a dátumot a Záró dátum mezőben.</span><span class="sxs-lookup"><span data-stu-id="e2bc0-165">In the End date field, enter a date.</span></span>
    * <span data-ttu-id="e2bc0-166">Adja meg például a 2015. január 31-ei dátumot.</span><span class="sxs-lookup"><span data-stu-id="e2bc0-166">For example, enter 31st January 2015.</span></span>  
14. <span data-ttu-id="e2bc0-167">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="e2bc0-167">Click OK.</span></span>
15. <span data-ttu-id="e2bc0-168">Kattintson a Módosítás gombra.</span><span class="sxs-lookup"><span data-stu-id="e2bc0-168">Click Update.</span></span>
16. <span data-ttu-id="e2bc0-169">Kattintson a Sorszámok újbóli létrehozása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e2bc0-169">Click Regenerate sequence numbers.</span></span>
17. <span data-ttu-id="e2bc0-170">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="e2bc0-170">Click OK.</span></span>
18. <span data-ttu-id="e2bc0-171">Kattintson a Kimenet lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e2bc0-171">Click Output.</span></span>
19. <span data-ttu-id="e2bc0-172">Kattintson a Jelentésre.</span><span class="sxs-lookup"><span data-stu-id="e2bc0-172">Click Report.</span></span>
20. <span data-ttu-id="e2bc0-173">A Kezdő dátum mezőben adja meg a jelentési időszak első napját.</span><span class="sxs-lookup"><span data-stu-id="e2bc0-173">In the From date field, enter the first date of the reporting period.</span></span>
    * <span data-ttu-id="e2bc0-174">Állítsa át a dátumot például 2015. január 1-jére.</span><span class="sxs-lookup"><span data-stu-id="e2bc0-174">For example, set the date to January 1, 2015.</span></span>  
21. <span data-ttu-id="e2bc0-175">Adja meg a dátumot a „Záró dátum” mezőben.</span><span class="sxs-lookup"><span data-stu-id="e2bc0-175">In the To date field, enter a date.</span></span>
    * <span data-ttu-id="e2bc0-176">Adja meg például a 2015. január 31-ei dátumot.</span><span class="sxs-lookup"><span data-stu-id="e2bc0-176">For example, enter January 31, 2015.</span></span>  
22. <span data-ttu-id="e2bc0-177">Válassza az Igen lehetőséget a Fájl létrehozása mezőben.</span><span class="sxs-lookup"><span data-stu-id="e2bc0-177">Select Yes in the Generate file field.</span></span>
23. <span data-ttu-id="e2bc0-178">Írjon be egy értéket a Fájlnév mezőbe.</span><span class="sxs-lookup"><span data-stu-id="e2bc0-178">In the File name field, type a value.</span></span>
24. <span data-ttu-id="e2bc0-179">Válassza az Igen lehetőséget a Jelentés létrehozása mezőben.</span><span class="sxs-lookup"><span data-stu-id="e2bc0-179">Select Yes in the Generate report field.</span></span>
25. <span data-ttu-id="e2bc0-180">Írjon be egy értéket a Jelentésfájl neve mezőbe.</span><span class="sxs-lookup"><span data-stu-id="e2bc0-180">In the Report file name field, type a value.</span></span>
26. <span data-ttu-id="e2bc0-181">Válasszon ki egy lehetőséget az Irány mezőben.</span><span class="sxs-lookup"><span data-stu-id="e2bc0-181">In the Direction field, select an option.</span></span>
    * <span data-ttu-id="e2bc0-182">Válassza ki például a „Feladások” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e2bc0-182">For example, select 'Dispatches'.</span></span>  
27. <span data-ttu-id="e2bc0-183">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="e2bc0-183">Click OK.</span></span>

