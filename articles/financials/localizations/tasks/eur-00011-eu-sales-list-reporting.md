---
title: EUR-00011 Értékesítési lista jelentés beállítása
description: Ez a feladat végigvezeti az EU értékesítési lista jelentéséhez szükséges előfeltételeken.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionRepositoryTable, ERSolutionImport, SysQueryForm, SysQueryFieldLookUp,  TaxTable, TaxGroup, TaxItemGroup, TaxCountryRegionParameters, TaxVATNumTable, IntrastatParameters, CustTable, DirPartyQuickCreateForm
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: epopov
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: aef1d19aabb7937fcd961a9657b8ca65c064b0b1
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1564398"
---
# <a name="eur-00011-set-up-eu-sales-list-reporting"></a><span data-ttu-id="d5929-103">EUR-00011 Értékesítési lista jelentés beállítása</span><span class="sxs-lookup"><span data-stu-id="d5929-103">EUR-00011 Set up EU sales list reporting</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d5929-104">Ez a feladat végigvezeti az EU értékesítési lista jelentéséhez szükséges előfeltételeken.</span><span class="sxs-lookup"><span data-stu-id="d5929-104">This task walks you through an overview of the prerequisites required for EU sales list reporting.</span></span> <span data-ttu-id="d5929-105">További tájékoztatásért az EU értékesítési lista jelentéséről, a kötelező előfeltételeket is beleértve, lásd a Dynamics 365 for Finance and Operations súgóját.</span><span class="sxs-lookup"><span data-stu-id="d5929-105">For more information about EU Sales list reporting, including required prerequisites, refer to the Dynamics 365 for Finance and Operations Help.</span></span>

<span data-ttu-id="d5929-106">Ez a feladat minden európai országra/régióra vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="d5929-106">This task applies to all European countries/regions.</span></span> <span data-ttu-id="d5929-107">Ez az útmutató a DEMF bemutatócég adataival lett létrehozva, így a példa ország/régió Németország lett.</span><span class="sxs-lookup"><span data-stu-id="d5929-107">The guide was created using the demo data company DEMF and consequently Germany as an exemplar domestic country/region.</span></span> <span data-ttu-id="d5929-108">Az útmutató EU-s ország/régió példájaként Portugáliát is használja.</span><span class="sxs-lookup"><span data-stu-id="d5929-108">The guide also uses Portugal as an exemplar EU country/region.</span></span>

<span data-ttu-id="d5929-109">Ezek a feladatok rendszergazdáknak szólnak.</span><span class="sxs-lookup"><span data-stu-id="d5929-109">These tasks are intended for system administrators.</span></span>


## <a name="import-electronic-reporting-configurations-for-eu-sales-list-reporting"></a><span data-ttu-id="d5929-110">Elektronikus jelentési konfigurációk importálása EU értékesítési lista jelentéséhez</span><span class="sxs-lookup"><span data-stu-id="d5929-110">Import electronic reporting configurations for EU sales list reporting</span></span>
1. <span data-ttu-id="d5929-111">Ugorjon a Szervezeti adminisztráció > Munkaterületek > Elektronikus jelentés pontra.</span><span class="sxs-lookup"><span data-stu-id="d5929-111">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="d5929-112">Kattintson erre: Beállítás aktívként.</span><span class="sxs-lookup"><span data-stu-id="d5929-112">Click Set active.</span></span>
3. <span data-ttu-id="d5929-113">Kattintson a Tárházak gombra.</span><span class="sxs-lookup"><span data-stu-id="d5929-113">Click Repositories.</span></span>
4. <span data-ttu-id="d5929-114">Kattintson a Megnyitás gombra.</span><span class="sxs-lookup"><span data-stu-id="d5929-114">Click Open.</span></span>
5. <span data-ttu-id="d5929-115">A Művelet ablaktáblában kattintson a Beállítások elemre.</span><span class="sxs-lookup"><span data-stu-id="d5929-115">On the Action Pane, click Options.</span></span>
6. <span data-ttu-id="d5929-116">Kattintson a Speciális szűrés/rendezés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d5929-116">Click Advanced Filter/Sort.</span></span>
7. <span data-ttu-id="d5929-117">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="d5929-117">Click Add.</span></span>
8. <span data-ttu-id="d5929-118">A Mező mezőben válassza ki a „Konfigurációnév” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d5929-118">In the Field field, select 'Configuration name'.</span></span>
9. <span data-ttu-id="d5929-119">A Feltétel mezőbe írja be, hogy „EU értékesítési lista (DE)”</span><span class="sxs-lookup"><span data-stu-id="d5929-119">In the Criteria field, type 'EU Sales list (DE)'.</span></span>
10. <span data-ttu-id="d5929-120">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="d5929-120">Click OK.</span></span>
11. <span data-ttu-id="d5929-121">Kattintson az Importálás gombra.</span><span class="sxs-lookup"><span data-stu-id="d5929-121">Click Import.</span></span>
12. <span data-ttu-id="d5929-122">Kattintson az Igen gombra.</span><span class="sxs-lookup"><span data-stu-id="d5929-122">Click Yes.</span></span>
13. <span data-ttu-id="d5929-123">A Művelet ablaktáblában kattintson a Beállítások elemre.</span><span class="sxs-lookup"><span data-stu-id="d5929-123">On the Action Pane, click Options.</span></span>
14. <span data-ttu-id="d5929-124">Kattintson a Speciális szűrés/rendezés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d5929-124">Click Advanced Filter/Sort.</span></span>
15. <span data-ttu-id="d5929-125">Kattintson az Alaphelyzet gombra.</span><span class="sxs-lookup"><span data-stu-id="d5929-125">Click Reset.</span></span>
16. <span data-ttu-id="d5929-126">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="d5929-126">Click Add.</span></span>
17. <span data-ttu-id="d5929-127">A Mező mezőben válassza ki a „Konfigurációnév” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d5929-127">In the Field field, select 'Configuration name'.</span></span>
18. <span data-ttu-id="d5929-128">A Feltétel mezőbe írja be, hogy „EU értékesítési lista kimutatási sorok alapján”.</span><span class="sxs-lookup"><span data-stu-id="d5929-128">In the Criteria field, type 'EU Sales list by rows report'.</span></span>
19. <span data-ttu-id="d5929-129">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="d5929-129">Click OK.</span></span>
20. <span data-ttu-id="d5929-130">Kattintson az Importálás gombra.</span><span class="sxs-lookup"><span data-stu-id="d5929-130">Click Import.</span></span>
21. <span data-ttu-id="d5929-131">Kattintson az Igen gombra.</span><span class="sxs-lookup"><span data-stu-id="d5929-131">Click Yes.</span></span>

## <a name="set-up-sales-tax-codes-for-eu-sales-list-reporting"></a><span data-ttu-id="d5929-132">Áfakódok beállítása EU értékesítési lista jelentéséhez</span><span class="sxs-lookup"><span data-stu-id="d5929-132">Set up sales tax codes for EU sales list reporting</span></span>
1. <span data-ttu-id="d5929-133">Ugrás az Adó > Közvetett adók > Áfa > Áfakódok pontra.</span><span class="sxs-lookup"><span data-stu-id="d5929-133">Go to Tax > Indirect taxes > Sales tax > Sales tax codes.</span></span>
2. <span data-ttu-id="d5929-134">A gyorsszűrő használatával keresse meg azokat az Áfakód mezőket, ahol a „VAT19” érték szerepel.</span><span class="sxs-lookup"><span data-stu-id="d5929-134">Use the Quick Filter to filter on the Sales tax code field with a value of 'VAT19'.</span></span>
3. <span data-ttu-id="d5929-135">Bontsa ki a Jelentésbeállítás szakaszt.</span><span class="sxs-lookup"><span data-stu-id="d5929-135">Expand the Report setup section.</span></span>
    * <span data-ttu-id="d5929-136">Ellenőrizze, hogy a Kizárva kiválasztás a Nem lehetőségre van állítva.</span><span class="sxs-lookup"><span data-stu-id="d5929-136">Verify that the Excluded selection is set to No.</span></span>  
    * <span data-ttu-id="d5929-137">A beállítás módosításához szükség lehet a feladat-útmutató feloldására.</span><span class="sxs-lookup"><span data-stu-id="d5929-137">You may need to unlock the task guide to change this setting.</span></span>  

## <a name="set-up-sales-tax-groups-for-eu-sales-list-reporting"></a><span data-ttu-id="d5929-138">Áfacsoport beállítása EU értékesítési lista jelentéséhez</span><span class="sxs-lookup"><span data-stu-id="d5929-138">Set up sales tax groups for EU sales list reporting</span></span>
1. <span data-ttu-id="d5929-139">Ugorjon az Adó > Közvetett adók > Áfa > Áfakódcsoportok pontra.</span><span class="sxs-lookup"><span data-stu-id="d5929-139">Go to Tax > Indirect taxes > Sales tax > Sales tax groups.</span></span>
2. <span data-ttu-id="d5929-140">A gyorsszűrő használatával keresse meg azokat az Áfacsoport mezőket, ahol a „AR-DOM” érték szerepel.</span><span class="sxs-lookup"><span data-stu-id="d5929-140">Use the Quick Filter to filter on the Sales tax group field with a value of 'AR-DOM'.</span></span>
3. <span data-ttu-id="d5929-141">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d5929-141">Click Edit.</span></span>
4. <span data-ttu-id="d5929-142">Bontsa ki a Beállítások szakaszt.</span><span class="sxs-lookup"><span data-stu-id="d5929-142">Expand the Setup section.</span></span>
5. <span data-ttu-id="d5929-143">A listában jelölje meg az első sort.</span><span class="sxs-lookup"><span data-stu-id="d5929-143">In the list, select the first row.</span></span>
6. <span data-ttu-id="d5929-144">Jelölje be az Adómentes jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="d5929-144">Select the Exempt check box.</span></span>
7. <span data-ttu-id="d5929-145">A listában jelölje meg a második sort.</span><span class="sxs-lookup"><span data-stu-id="d5929-145">In the list, select the second row.</span></span>
8. <span data-ttu-id="d5929-146">Jelölje be az Adómentes jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="d5929-146">Select the Exempt check box.</span></span>
9. <span data-ttu-id="d5929-147">A listában jelölje meg a harmadik sort.</span><span class="sxs-lookup"><span data-stu-id="d5929-147">In the list, select the third row.</span></span>
10. <span data-ttu-id="d5929-148">Jelölje be az Adómentes jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="d5929-148">Select the Exempt check box.</span></span>

## <a name="set-up-item-sales-tax-groups-for-eu-sales-list-reporting"></a><span data-ttu-id="d5929-149">Cikkáfacsoport beállítása EU értékesítési lista jelentéséhez</span><span class="sxs-lookup"><span data-stu-id="d5929-149">Set up item sales tax groups for EU sales list reporting</span></span>
1. <span data-ttu-id="d5929-150">Ugorjon az Adó > Közvetett adók > Áfa > Áfakódcsoportok pontra.</span><span class="sxs-lookup"><span data-stu-id="d5929-150">Go to Tax > Indirect taxes > Sales tax > Item sales tax groups.</span></span>
2. <span data-ttu-id="d5929-151">A gyorsszűrő használatával keresse meg azokat a Cikkáfacsoport mezőket, ahol a „FULL” érték szerepel.</span><span class="sxs-lookup"><span data-stu-id="d5929-151">Use the Quick Filter to filter on the Item sales tax group field with a value of 'FULL '.</span></span>
    * <span data-ttu-id="d5929-152">Ellenőrizze, hogy a Jelentéstípus kiválasztás a „Cikk” lehetőségre van állítva.</span><span class="sxs-lookup"><span data-stu-id="d5929-152">Verify that the Reporting type selection is set to 'Item'.</span></span>  
    * <span data-ttu-id="d5929-153">A mező értékének a módosításához szükség lehet a feladat-útmutató feloldására.</span><span class="sxs-lookup"><span data-stu-id="d5929-153">You may need to unlock the task guide to change the value in this field.</span></span>  
3. <span data-ttu-id="d5929-154">A gyorsszűrő használatával keresse meg azokat a Cikkáfacsoport mezőket, ahol a „RED” érték szerepel.</span><span class="sxs-lookup"><span data-stu-id="d5929-154">Use the Quick Filter to filter on the Item sales tax group field with a value of 'RED '.</span></span>
    * <span data-ttu-id="d5929-155">Ellenőrizze, hogy a Jelentéstípus kiválasztás a „Szolgáltatás” lehetőségre van állítva.</span><span class="sxs-lookup"><span data-stu-id="d5929-155">Verify that the Reporting type selection is set to 'Service'.</span></span>  
    * <span data-ttu-id="d5929-156">A mező értékének a módosításához szükség lehet a feladat-útmutató feloldására.</span><span class="sxs-lookup"><span data-stu-id="d5929-156">You may need to unlock the task guide to change the value in this field.</span></span>  

## <a name="set-up-countryregion-parameters-for-eu-sales-list-reporting"></a><span data-ttu-id="d5929-157">Ország/régió paramétereinek beállítása EU értékesítési lista jelentéséhez</span><span class="sxs-lookup"><span data-stu-id="d5929-157">Set up country/region parameters for EU sales list reporting</span></span>
1. <span data-ttu-id="d5929-158">Ugorjon az Adó > Beállítás > Áfa> Országok és régiók paraméterei pontra.</span><span class="sxs-lookup"><span data-stu-id="d5929-158">Go to Tax > Setup > Sales tax > Country/region parameters.</span></span>
2. <span data-ttu-id="d5929-159">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d5929-159">Click New.</span></span>
3. <span data-ttu-id="d5929-160">Írja be a „PRT” értéket az Ország/régió mezőbe.</span><span class="sxs-lookup"><span data-stu-id="d5929-160">In the Country/region field, type 'PRT'.</span></span>
4. <span data-ttu-id="d5929-161">Az Áfakód mezőbe írja be a „PT” értéket.</span><span class="sxs-lookup"><span data-stu-id="d5929-161">In the Sales tax field, type 'PT'.</span></span>

## <a name="create-tax-exempt-numbers"></a><span data-ttu-id="d5929-162">Adószámok létrehozása</span><span class="sxs-lookup"><span data-stu-id="d5929-162">Create tax exempt numbers</span></span>
1. <span data-ttu-id="d5929-163">Ugorjon az Adó > Beállítás > Áfa > Adószámok pontra.</span><span class="sxs-lookup"><span data-stu-id="d5929-163">Go to Tax > Setup > Sales tax > Tax exempt numbers.</span></span>
2. <span data-ttu-id="d5929-164">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d5929-164">Click New.</span></span>
3. <span data-ttu-id="d5929-165">Írja be a „PRT” értéket az Ország/régió mezőbe.</span><span class="sxs-lookup"><span data-stu-id="d5929-165">In the Country/region field, type 'PRT'.</span></span>
4. <span data-ttu-id="d5929-166">Az Adószám mezőbe írja be a „PT12345” értéket.</span><span class="sxs-lookup"><span data-stu-id="d5929-166">In the Tax exempt number field, type 'PT12345'.</span></span>

## <a name="set-up-eu-sales-list-reporting-parameters"></a><span data-ttu-id="d5929-167">EU értékesítési lista jelentési paraméterek beállítása</span><span class="sxs-lookup"><span data-stu-id="d5929-167">Set up EU sales list reporting parameters</span></span>
1. <span data-ttu-id="d5929-168">Ugorjon az Adó > Beállítás > Külkereskedelmi > Külkereskedelmi paraméterek pontra.</span><span class="sxs-lookup"><span data-stu-id="d5929-168">Go to Tax > Setup > Foreign trade > Foreign trade parameters.</span></span>
2. <span data-ttu-id="d5929-169">Kattintson az EU értékesítési lista fülre.</span><span class="sxs-lookup"><span data-stu-id="d5929-169">Click the EU sales list tab.</span></span>
3. <span data-ttu-id="d5929-170">Válassza az Igen lehetőséget a Beszerzések átvitele mezőben.</span><span class="sxs-lookup"><span data-stu-id="d5929-170">Select Yes in the Transfer purchases field.</span></span>
4. <span data-ttu-id="d5929-171">Bontsa ki a Kerekítési szabályok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="d5929-171">Expand the Rounding rules section.</span></span>
5. <span data-ttu-id="d5929-172">Kerekítési szabálynak adja meg a „0,1” értéket.</span><span class="sxs-lookup"><span data-stu-id="d5929-172">Set Rounding rule to '0.1'.</span></span>
6. <span data-ttu-id="d5929-173">A Minimum érték használata mezőben válassza az Igen lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d5929-173">Select Yes in the Use minimum value field.</span></span>
7. <span data-ttu-id="d5929-174">A Tizedesek száma mezőben adja meg a „2” értéket.</span><span class="sxs-lookup"><span data-stu-id="d5929-174">In the Number of decimals field, enter '2'.</span></span>
8. <span data-ttu-id="d5929-175">Bontsa ki az elektronikus jelentéskészítés szakaszát.</span><span class="sxs-lookup"><span data-stu-id="d5929-175">Expand the Electronic reporting section.</span></span>
9. <span data-ttu-id="d5929-176">A Fájlformátum-hozzárendelés mezőben válassza ki az „EU értékesítési lista (DE)” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d5929-176">In the File format mapping field, select 'EU Sales list (DE)'.</span></span>
10. <span data-ttu-id="d5929-177">A Jelentésformátum-hozzárendelés mezőben válassza ki az „EU értékesítési lista kimutatási sorok alapján” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d5929-177">In the Report format mapping field, select 'EU Sales list by rows report'.</span></span>
11. <span data-ttu-id="d5929-178">Kattintson az Ország/régió tulajdonságai lapra.</span><span class="sxs-lookup"><span data-stu-id="d5929-178">Click the Country/region properties tab.</span></span>
    * <span data-ttu-id="d5929-179">Ellenőrizze, hogy az Ország/régió típusa mező „Helyi” lehetőségre van állítva a DEU Ország/régió esetén.</span><span class="sxs-lookup"><span data-stu-id="d5929-179">Verify that the Country/region type field is set to 'Domestic' for Country/region DEU.</span></span>  
    * <span data-ttu-id="d5929-180">A mező értékének a módosításához szükség lehet a feladat-útmutató feloldására.</span><span class="sxs-lookup"><span data-stu-id="d5929-180">You may need to unlock the task guide to change the value in this field.</span></span>  
12. <span data-ttu-id="d5929-181">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d5929-181">Click New.</span></span>
13. <span data-ttu-id="d5929-182">Írja be a „PRT” értéket az Ország/régió mezőbe.</span><span class="sxs-lookup"><span data-stu-id="d5929-182">In the Country/region field, type 'PRT'.</span></span>
14. <span data-ttu-id="d5929-183">Az Intrastat-kód mezőbe írja be, hogy „PT”.</span><span class="sxs-lookup"><span data-stu-id="d5929-183">In the Intrastat code field, type 'PT'.</span></span>
15. <span data-ttu-id="d5929-184">Az Ország/régió típusa mezőben válassza ki az „EU” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d5929-184">In the Country/region type field, select 'EU'.</span></span>
16. <span data-ttu-id="d5929-185">Kattintson a Számsorozatok lapra.</span><span class="sxs-lookup"><span data-stu-id="d5929-185">Click the Number sequences tab.</span></span>
    * <span data-ttu-id="d5929-186">Ellenőrizze, hogy a Szám sorozatkód meg van határozva az „EU értékesítési lista” referenciájára.</span><span class="sxs-lookup"><span data-stu-id="d5929-186">Verify that a Number sequence code is specified for the Reference 'EU sales list'.</span></span>  

## <a name="create-a-customer-for-eu-sales-list-reporting-demo-purposes"></a><span data-ttu-id="d5929-187">Vevő létrehozása EU értékesítési lista jelentés bemutatói céljára</span><span class="sxs-lookup"><span data-stu-id="d5929-187">Create a customer for EU sales list reporting demo purposes</span></span>
1. <span data-ttu-id="d5929-188">Ugorjon a Kinnlevőségek > Vevők > Minden vevő pontra.</span><span class="sxs-lookup"><span data-stu-id="d5929-188">Go to Accounts receivable > Customers > All customers.</span></span>
2. <span data-ttu-id="d5929-189">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d5929-189">Click New.</span></span>
3. <span data-ttu-id="d5929-190">A Vevői számla mezőbe írja be a „PRT-001” szöveget.</span><span class="sxs-lookup"><span data-stu-id="d5929-190">In the Customer account field, type 'PRT-001'.</span></span>
4. <span data-ttu-id="d5929-191">A Név mezőbe írja be a „Vevő Portugáliából” szöveget.</span><span class="sxs-lookup"><span data-stu-id="d5929-191">In the Name field, type 'A customer from Portugal'.</span></span>
5. <span data-ttu-id="d5929-192">A Vevőcsoport mezőben válassza ki a „10” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d5929-192">In the Customer group field, select '10'.</span></span>
6. <span data-ttu-id="d5929-193">Az Áfacsoport mezőben válassza ki az „AR-DOM” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d5929-193">In the Sales tax group field, select 'AR-DOM'.</span></span>
7. <span data-ttu-id="d5929-194">Az Adószám mezőbe válassza ki a „PT12345” értéket.</span><span class="sxs-lookup"><span data-stu-id="d5929-194">In the Tax exempt number field, select 'PT12345'.</span></span>
8. <span data-ttu-id="d5929-195">Írja be a „PRT” értéket az Ország/régió mezőbe.</span><span class="sxs-lookup"><span data-stu-id="d5929-195">In the Country/region field, type 'PRT'.</span></span>
9. <span data-ttu-id="d5929-196">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="d5929-196">Click Save.</span></span>

