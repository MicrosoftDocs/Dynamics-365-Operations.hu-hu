---
title: EUR-00011 EU értékesítési lista jelentés létrehozása.
description: Ezzel az eljárás végigvezeti az EU értékesítési lista jelentésének létrehozásán.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, SalesEditLines,  EUSalesList, EUSalesListSelection, SysQueryForm, SysLookup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: epopov
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9fcafa2beca5d998b2556ba73e9f3cc2bdd314ba
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1564432"
---
# <a name="eur-00011-generate-the-eu-sales-list-report"></a><span data-ttu-id="82ed5-103">EUR-00011 EU értékesítési lista jelentés létrehozása.</span><span class="sxs-lookup"><span data-stu-id="82ed5-103">EUR-00011 Generate the EU sales list report</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="82ed5-104">Ezzel az eljárás végigvezeti az EU értékesítési lista jelentésének létrehozásán.</span><span class="sxs-lookup"><span data-stu-id="82ed5-104">This procedure walks you through generating the EU sales list report.</span></span> <span data-ttu-id="82ed5-105">Ez magában foglalja a Közösségen belüli kereskedelmi tranzakciók átvitelét az EU értékesítési listára és a jelentés futtatását.</span><span class="sxs-lookup"><span data-stu-id="82ed5-105">This includes transferring intra-community trade transactions to the EU sales list and running the report.</span></span> <span data-ttu-id="82ed5-106">Az eljárással egy bemutatásra szánt közösségen belüli kereskedelmi tranzakciót is létrehozhat.</span><span class="sxs-lookup"><span data-stu-id="82ed5-106">This  procedure also includes creating an intra-community trade transaction for demo purposes.</span></span> <span data-ttu-id="82ed5-107">További tájékoztatásért az EU értékesítési lista jelentéséről, a kötelező előfeltételeket is beleértve, lásd a Dynamics 365 for Finance and Operations súgóját.</span><span class="sxs-lookup"><span data-stu-id="82ed5-107">For more information about EU Sales list reporting, including required prerequisites, refer to the Dynamics 365 for Finance and Operations Help.</span></span>

<span data-ttu-id="82ed5-108">Ez az eljárás minden európai országra/régióra vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="82ed5-108">This procedure applies to all European countries/regions.</span></span> <span data-ttu-id="82ed5-109">Az eljárás a DEMF bemutatócég adataival lett létrehozva, így a példa ország/régió Németország lett.</span><span class="sxs-lookup"><span data-stu-id="82ed5-109">The procedure was created using the demo data company DEMF and consequently Germany as an exemplar domestic country/region.</span></span> <span data-ttu-id="82ed5-110">Az eljárás EU-s ország/régió példájaként Portugáliát is használja.</span><span class="sxs-lookup"><span data-stu-id="82ed5-110">The procedure also uses Portugal as an exemplar EU country/region.</span></span> <span data-ttu-id="82ed5-111">Ez az eljárás végrehajtása előtt be kell állítania az EU értékesítési lista jelentését.</span><span class="sxs-lookup"><span data-stu-id="82ed5-111">Before you can complete this procedure, you must configure EU sales list reporting.</span></span>

<span data-ttu-id="82ed5-112">Ez az eljárás könyvelőknek szól.</span><span class="sxs-lookup"><span data-stu-id="82ed5-112">This procedure is intended for accountants.</span></span>


## <a name="create-an-intra-community-sales-transaction-for-demo-purposes"></a><span data-ttu-id="82ed5-113">Bemutatás céljából egy Közösségen belüli értékesítési tranzakció létrehozása</span><span class="sxs-lookup"><span data-stu-id="82ed5-113">Create an intra-community sales transaction for demo purposes</span></span>
1. <span data-ttu-id="82ed5-114">Ugorjon a Kinnlevőségek > Rendelések > Minden értékesítési rendelés elemre.</span><span class="sxs-lookup"><span data-stu-id="82ed5-114">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="82ed5-115">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="82ed5-115">Click New.</span></span>
3. <span data-ttu-id="82ed5-116">A Vevői számla mezőbe írja be a „PRT-001” szöveget.</span><span class="sxs-lookup"><span data-stu-id="82ed5-116">In the Customer account field, type 'PRT-001'.</span></span>
4. <span data-ttu-id="82ed5-117">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="82ed5-117">Click OK.</span></span>
5. <span data-ttu-id="82ed5-118">A Cikkszám mezőbe írja be az „D0001” értéket.</span><span class="sxs-lookup"><span data-stu-id="82ed5-118">In the Item number field, type 'D0001'.</span></span>
6. <span data-ttu-id="82ed5-119">Bontsa ki a Soradatok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="82ed5-119">Expand the Line details section.</span></span>
7. <span data-ttu-id="82ed5-120">Kattintson a Beállítások fülre.</span><span class="sxs-lookup"><span data-stu-id="82ed5-120">Click the Setup tab.</span></span>
8. <span data-ttu-id="82ed5-121">A Cikkértékesítési adócsoport mezőbe írja be hogy „FULL”.</span><span class="sxs-lookup"><span data-stu-id="82ed5-121">In the Item sales tax group field, type 'FULL'.</span></span>
9. <span data-ttu-id="82ed5-122">Kattintson az Új sor hozzáadására.</span><span class="sxs-lookup"><span data-stu-id="82ed5-122">Click Add line.</span></span>
10. <span data-ttu-id="82ed5-123">A Cikkszám mezőbe írja be az „D0003” értéket.</span><span class="sxs-lookup"><span data-stu-id="82ed5-123">In the Item number field, type 'D0003'.</span></span>
11. <span data-ttu-id="82ed5-124">A Cikkértékesítési adócsoport mezőbe írja be hogy „RED”.</span><span class="sxs-lookup"><span data-stu-id="82ed5-124">In the Item sales tax group field, type 'RED'.</span></span>
12. <span data-ttu-id="82ed5-125">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="82ed5-125">Click Save.</span></span>
13. <span data-ttu-id="82ed5-126">A Művelet panelen kattintson a Számla lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="82ed5-126">On the Action Pane, click Invoice.</span></span>
14. <span data-ttu-id="82ed5-127">Kattintson a Számla lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="82ed5-127">Click Invoice.</span></span>
15. <span data-ttu-id="82ed5-128">Bontsa ki a Paraméterek szakaszt.</span><span class="sxs-lookup"><span data-stu-id="82ed5-128">Expand the Parameters section.</span></span>
16. <span data-ttu-id="82ed5-129">A Mennyiség mezőben válassza a „Mind” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="82ed5-129">In the Quantity field, select 'All'.</span></span>
17. <span data-ttu-id="82ed5-130">Bontsa ki a Beállítások szakaszt.</span><span class="sxs-lookup"><span data-stu-id="82ed5-130">Expand the Setup section.</span></span>
18. <span data-ttu-id="82ed5-131">A Számla kelte mezőben állítsa „01/11/2016” értékűre a dátumot.</span><span class="sxs-lookup"><span data-stu-id="82ed5-131">In the Invoice date field, set the date to '01/11/2016'.</span></span>
19. <span data-ttu-id="82ed5-132">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="82ed5-132">Click OK.</span></span>
20. <span data-ttu-id="82ed5-133">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="82ed5-133">Click OK.</span></span>

## <a name="transfer-intra-community-trade-transactions-to-the-eu-sales-list"></a><span data-ttu-id="82ed5-134">Közösségen belüli kereskedelmi tranzakciók átvitele EU értékesítési listára</span><span class="sxs-lookup"><span data-stu-id="82ed5-134">Transfer intra-community trade transactions to the EU sales list</span></span>
1. <span data-ttu-id="82ed5-135">Ugorjon az Adó > Nyilatkozatok > Külkereskedelmi > EU értékesítési lista menüpontba.</span><span class="sxs-lookup"><span data-stu-id="82ed5-135">Go to Tax > Declarations > Foreign trade > EU sales list.</span></span>
2. <span data-ttu-id="82ed5-136">Kattintson az Áthelyezés elemre.</span><span class="sxs-lookup"><span data-stu-id="82ed5-136">Click Transfer.</span></span>
3. <span data-ttu-id="82ed5-137">Válassza az Igen beállítást a Cikk mezőben a cikktranzakciók átviteléhez.</span><span class="sxs-lookup"><span data-stu-id="82ed5-137">Select Yes in the Item field to transfer item transactions.</span></span>
4. <span data-ttu-id="82ed5-138">Válassza az Igen beállítást a Szolgáltatás mezőben a szolgáltatástranzakciói átviteléhez.</span><span class="sxs-lookup"><span data-stu-id="82ed5-138">Select Yes in the Service field to transfer service transactions.</span></span>
    * <span data-ttu-id="82ed5-139">Megadhat további szűrőket a Közösségen belüli kereskedelmi tranzakciók átviteléhez.</span><span class="sxs-lookup"><span data-stu-id="82ed5-139">You can also specify additional filters on intra-community trade transactions to transfer.</span></span>  
5. <span data-ttu-id="82ed5-140">Kattintson az Áthelyezés elemre.</span><span class="sxs-lookup"><span data-stu-id="82ed5-140">Click Transfer.</span></span>
    * <span data-ttu-id="82ed5-141">Győződjön meg róla, hogy a Közösségen belüli értékesítési tranzakció sikeresen átkerül az EU értékesítési listára.</span><span class="sxs-lookup"><span data-stu-id="82ed5-141">Verify that the intra-community sales transaction is successfully transferred to the EU sales list.</span></span>  

## <a name="generate-the-eu-sales-list-report"></a><span data-ttu-id="82ed5-142">EU értékesítési lista jelentés készítése</span><span class="sxs-lookup"><span data-stu-id="82ed5-142">Generate the EU sales list report</span></span>
1. <span data-ttu-id="82ed5-143">Kattintson a Jelentéskészítés elemre.</span><span class="sxs-lookup"><span data-stu-id="82ed5-143">Click Reporting.</span></span>
2. <span data-ttu-id="82ed5-144">A Jelentéskészítési időszak mezőben válassza a „Havi” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="82ed5-144">In the Reporting period field, select 'Monthly'.</span></span>
3. <span data-ttu-id="82ed5-145">A Kezdő dátum mezőben állítsa „01/01/2016” értékűre a dátumot.</span><span class="sxs-lookup"><span data-stu-id="82ed5-145">In the From date field, set the date to '01/01/2016'.</span></span>
4. <span data-ttu-id="82ed5-146">Válassza az Igen lehetőséget a Fájl létrehozása mezőben.</span><span class="sxs-lookup"><span data-stu-id="82ed5-146">Select Yes in the Generate file field.</span></span>
5. <span data-ttu-id="82ed5-147">Válassza az Igen lehetőséget a Jelentés létrehozása mezőben.</span><span class="sxs-lookup"><span data-stu-id="82ed5-147">Select Yes in the Generate report field.</span></span>
6. <span data-ttu-id="82ed5-148">A Fájlnév mezőbe írja be, hogy „EUSalesList”.</span><span class="sxs-lookup"><span data-stu-id="82ed5-148">In the File name field, type 'EUSalesList'.</span></span>
7. <span data-ttu-id="82ed5-149">A Jelentésnév mezőbe írja be, hogy „EUSalesList”.</span><span class="sxs-lookup"><span data-stu-id="82ed5-149">In the Report file name field, type 'EUSalesList'.</span></span>
8. <span data-ttu-id="82ed5-150">A EU értékesítési lista regisztrációs azonosítója mezőbe írja be, hogy „123”.</span><span class="sxs-lookup"><span data-stu-id="82ed5-150">In the EU Sales List Registration ID field, type '123'.</span></span>
    * <span data-ttu-id="82ed5-151">Ez a mező csak Németországban érhető el.</span><span class="sxs-lookup"><span data-stu-id="82ed5-151">This field is only available for Germany.</span></span>  
    * <span data-ttu-id="82ed5-152">Megadhat további szűrőket a Közösségen belüli kereskedelmi tranzakciók jelentésbe foglalásához.</span><span class="sxs-lookup"><span data-stu-id="82ed5-152">You can also specify additional filters on intra-community trade transactions to include in the report.</span></span>  
9. <span data-ttu-id="82ed5-153">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="82ed5-153">Click OK.</span></span>
    * <span data-ttu-id="82ed5-154">Győződjön meg róla, hogy előugró ablakok jelennek meg, amelyek megerősítik, hogy a fájl és az ellenőrző jelentés letöltése folyamatban van.</span><span class="sxs-lookup"><span data-stu-id="82ed5-154">Verify that pop-up windows appear to confirm that the file and the control report are being downloaded.</span></span>  

## <a name="mark-eu-sales-list-lines-as-reported"></a><span data-ttu-id="82ed5-155">EU értékesítési lista sorainak megjelölése Jelentettként</span><span class="sxs-lookup"><span data-stu-id="82ed5-155">Mark EU sales list lines as Reported</span></span>
1. <span data-ttu-id="82ed5-156">Kattintson a Megjelölés elemre.</span><span class="sxs-lookup"><span data-stu-id="82ed5-156">Click Mark.</span></span>
2. <span data-ttu-id="82ed5-157">Kattintson a Megjelölés jelentettként elemre.</span><span class="sxs-lookup"><span data-stu-id="82ed5-157">Click Mark as reported.</span></span>
3. <span data-ttu-id="82ed5-158">A listából válassza Számla keltezése mezőhöz tartozó sort.</span><span class="sxs-lookup"><span data-stu-id="82ed5-158">In the list, select the row for the Invoice date field.</span></span>
4. <span data-ttu-id="82ed5-159">A Feltétel mezőbe írja be, hogy „01/01/2016..01/31/2016”.</span><span class="sxs-lookup"><span data-stu-id="82ed5-159">In the Criteria field, type '01/01/2016..01/31/2016'.</span></span>
5. <span data-ttu-id="82ed5-160">A listából válassza Jelentés állapota mezőhöz tartozó sort.</span><span class="sxs-lookup"><span data-stu-id="82ed5-160">In the list, select the row for the Reporting status field.</span></span>
6. <span data-ttu-id="82ed5-161">A Feltételek mezőben válasszon ki a „Belefoglalva” értéket.</span><span class="sxs-lookup"><span data-stu-id="82ed5-161">In the Criteria field, select 'Included'.</span></span>
    * <span data-ttu-id="82ed5-162">Megadhat további szűrőket a Közösségen belüli kereskedelmi tranzakciók Jelentettként megjelöléséhez.</span><span class="sxs-lookup"><span data-stu-id="82ed5-162">You can also specify additional filters on intra-community trade transactions to mark as Reported.</span></span>  
7. <span data-ttu-id="82ed5-163">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="82ed5-163">Click OK.</span></span>
8. <span data-ttu-id="82ed5-164">A Kiválasztása mezőben válassza a „Jelentve” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="82ed5-164">In the Selection field, select 'Reported'.</span></span>

## <a name="mark-eu-sales-list-lines-as-closed"></a><span data-ttu-id="82ed5-165">EU értékesítési lista sorainak megjelölése Lezártként</span><span class="sxs-lookup"><span data-stu-id="82ed5-165">Mark EU sales list lines as Closed</span></span>
1. <span data-ttu-id="82ed5-166">Kattintson a Megjelölés elemre.</span><span class="sxs-lookup"><span data-stu-id="82ed5-166">Click Mark.</span></span>
2. <span data-ttu-id="82ed5-167">Kattintson a Megjelölés lezártként elemre.</span><span class="sxs-lookup"><span data-stu-id="82ed5-167">Click Mark as closed.</span></span>
3. <span data-ttu-id="82ed5-168">A listában jelölje meg a Számla keltezése mezőhöz tartozó sort.</span><span class="sxs-lookup"><span data-stu-id="82ed5-168">In the list, mark the row for the Invoice date field.</span></span>
4. <span data-ttu-id="82ed5-169">A Feltétel mezőbe írja be, hogy „01/01/2016..01/31/2016”.</span><span class="sxs-lookup"><span data-stu-id="82ed5-169">In the Criteria field, type '01/01/2016..01/31/2016'.</span></span>
5. <span data-ttu-id="82ed5-170">A listában jelölje meg a Jelentés állapota mezőhöz tartozó sort.</span><span class="sxs-lookup"><span data-stu-id="82ed5-170">In the list, mark the row for the Reporting status field.</span></span>
6. <span data-ttu-id="82ed5-171">A Feltételek mezőben válassza ki a „Jelentve” értéket.</span><span class="sxs-lookup"><span data-stu-id="82ed5-171">In the Criteria field, select ‘Reported’.</span></span>
    * <span data-ttu-id="82ed5-172">Megadhat további szűrőket a Közösségen belüli kereskedelmi tranzakciók Lezártként megjelöléséhez.</span><span class="sxs-lookup"><span data-stu-id="82ed5-172">You can also specify additional filters on intra-community trade transactions to mark as Closed.</span></span>  
7. <span data-ttu-id="82ed5-173">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="82ed5-173">Click OK.</span></span>
8. <span data-ttu-id="82ed5-174">A Kiválasztása mezőben válassza a „Lezárt” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="82ed5-174">In the Selection field, select 'Closed'.</span></span>

