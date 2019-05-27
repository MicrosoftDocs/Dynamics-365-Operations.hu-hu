---
title: Minőségi rendelések beállítása
description: Ez az eljárás bemutatja, hogy hogyan engedélyezheti a minőségkezelési folyamatot, ha a bejövő készletet, a beérkezés regisztrációja után azonnal ellenőrizni szükséges.
author: perlynne
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventParameters, InventTestReportSetup, InventTestTable, DefaultDashboard, InventTestVariable, InventTestVariableOutcome, InventItemSampling, InventTestQualityGroup, InventTestItemQualityGroupAdd, SysQueryForm, InventTestItemQualityGroup, InventTestGroup, InventTestAssociationTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5a073de7bdfd2ef597c09a8066ff2b6a7721ca62
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1561317"
---
# <a name="set-up-quality-orders"></a><span data-ttu-id="d5b82-103">Minőségi rendelések beállítása</span><span class="sxs-lookup"><span data-stu-id="d5b82-103">Set up quality orders</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d5b82-104">Ez az eljárás bemutatja, hogy hogyan engedélyezheti a minőségkezelési folyamatot, ha a bejövő készletet, a beérkezés regisztrációja után azonnal ellenőrizni szükséges.</span><span class="sxs-lookup"><span data-stu-id="d5b82-104">This procedure shows you how to enable a quality management process where incoming inventory must be inspected immediately after arrival registration.</span></span> <span data-ttu-id="d5b82-105">Ezt az eljárást jellemzően egy minőségbiztosítási vezető végzi.</span><span class="sxs-lookup"><span data-stu-id="d5b82-105">The procedure will typically be carried out by a quality manager.</span></span> <span data-ttu-id="d5b82-106">A folyamat részét képezi a minőségi csoport létrehozása, a mintavétellel érintett cikkek, valamint a minőségi csoportban szereplő cikkeken végzendő tesztek csoportosítását szolgáló tesztcsoport meghatározása.</span><span class="sxs-lookup"><span data-stu-id="d5b82-106">The process includes the creation of a quality group, to define the items that are going to be sampled, and a test group to group the tests that are to be performed on items in the quality group.</span></span> <span data-ttu-id="d5b82-107">Ezt az útmutatót lefuttathatja az USMF bemutatócégen.</span><span class="sxs-lookup"><span data-stu-id="d5b82-107">You can run this guide in the USMF demo data company.</span></span>


## <a name="enable-quality-management"></a><span data-ttu-id="d5b82-108">Minőségkezelés engedélyezése</span><span class="sxs-lookup"><span data-stu-id="d5b82-108">Enable quality management</span></span>
1. <span data-ttu-id="d5b82-109">Ugrás a Készletkezelés > Beállítás > Készlet- és raktárkezelési paraméterek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d5b82-109">Go to Inventory management > Setup > Inventory and warehouse management parameters.</span></span>
2. <span data-ttu-id="d5b82-110">Kattintson a Minőségkezelés lapra.</span><span class="sxs-lookup"><span data-stu-id="d5b82-110">Click the Quality management tab.</span></span>
3. <span data-ttu-id="d5b82-111">Állítsa a Minőségkezelés használata beállítást Igen értékre.</span><span class="sxs-lookup"><span data-stu-id="d5b82-111">Set the Use quality management option to Yes.</span></span>
4. <span data-ttu-id="d5b82-112">Kattintson a Jelentés-beállítás elemre.</span><span class="sxs-lookup"><span data-stu-id="d5b82-112">Click Report setup.</span></span>
    * <span data-ttu-id="d5b82-113">Az USMF-ben, a minőségkezelési jelentések beállításai előre definiálva vannak.</span><span class="sxs-lookup"><span data-stu-id="d5b82-113">In USMF, the report setup for quality management is already defined.</span></span> <span data-ttu-id="d5b82-114">Ha ez nem történt meg, adjon hozzá új sorokat a különböző típusú jelentés típusokhoz, majd válassza ki az egyes jelentésekhez használandó dokumentum típust.</span><span class="sxs-lookup"><span data-stu-id="d5b82-114">If this wasn’t done, you’d add new lines here for the different report types, and select the type of document to be used for each report.</span></span>  
5. <span data-ttu-id="d5b82-115">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="d5b82-115">Close the page.</span></span>
6. <span data-ttu-id="d5b82-116">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="d5b82-116">Close the page.</span></span>

## <a name="create-a-test"></a><span data-ttu-id="d5b82-117">Teszt létrehozása</span><span class="sxs-lookup"><span data-stu-id="d5b82-117">Create a test</span></span>
1. <span data-ttu-id="d5b82-118">Ugorjon a következőhöz: Készletkezelés > Beállítás > Minőség-ellenőrzés > Készlet.</span><span class="sxs-lookup"><span data-stu-id="d5b82-118">Go to Inventory management > Setup > Quality control > Tests.</span></span>
2. <span data-ttu-id="d5b82-119">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d5b82-119">Click New.</span></span>
3. <span data-ttu-id="d5b82-120">Írjon be egy értéket a Teszt mezőbe.</span><span class="sxs-lookup"><span data-stu-id="d5b82-120">In the Test field, type a value.</span></span>
4. <span data-ttu-id="d5b82-121">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="d5b82-121">In the Description field, type a value.</span></span>
5. <span data-ttu-id="d5b82-122">Az „Opció” kiválasztása a Típus mezőben.</span><span class="sxs-lookup"><span data-stu-id="d5b82-122">In the Type field, select 'Option'.</span></span>
    * <span data-ttu-id="d5b82-123">Ebben a példában kiválasztjuk az „Opciók” lehetőséget, ami lehetővé teszi a teszteredmények, előre megadott értékek alapján történő társítását.</span><span class="sxs-lookup"><span data-stu-id="d5b82-123">In this example, we'll select "Option" which will make it possible to assign the test results based on pre-defined values.</span></span>  
6. <span data-ttu-id="d5b82-124">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="d5b82-124">Click Save.</span></span>
7. <span data-ttu-id="d5b82-125">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="d5b82-125">Close the page.</span></span>

## <a name="create-test-variables-to-define-the-way-test-results-are-recorded"></a><span data-ttu-id="d5b82-126">Tesztváltozók létrehozása a teszteredmények rögzítési módjának meghatározása érdekében</span><span class="sxs-lookup"><span data-stu-id="d5b82-126">Create Test variables to define the way test results are recorded</span></span>
1. <span data-ttu-id="d5b82-127">Ugorjon a következőhöz: Készletkezelés > Beállítás > Minőség-ellenőrzés > Tesztváltozók.</span><span class="sxs-lookup"><span data-stu-id="d5b82-127">Go to Inventory management > Setup > Quality control > Test variables.</span></span>
2. <span data-ttu-id="d5b82-128">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d5b82-128">Click New.</span></span>
3. <span data-ttu-id="d5b82-129">Írjon be egy értéket a Változó mezőbe.</span><span class="sxs-lookup"><span data-stu-id="d5b82-129">In the Variable field, type a value.</span></span>
4. <span data-ttu-id="d5b82-130">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="d5b82-130">In the Description field, type a value.</span></span>
5. <span data-ttu-id="d5b82-131">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="d5b82-131">Click Save.</span></span>
6. <span data-ttu-id="d5b82-132">Kattintson az Eredmények elemre.</span><span class="sxs-lookup"><span data-stu-id="d5b82-132">Click Outcomes.</span></span>
7. <span data-ttu-id="d5b82-133">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d5b82-133">Click New.</span></span>
8. <span data-ttu-id="d5b82-134">Írjon be egy értéket az Eredmény mezőbe.</span><span class="sxs-lookup"><span data-stu-id="d5b82-134">In the Outcome field, type a value.</span></span>
9. <span data-ttu-id="d5b82-135">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="d5b82-135">In the Description field, type a value.</span></span>
10. <span data-ttu-id="d5b82-136">Az Eredményállapot mezőben válassza a „Megfelelt” értéket.</span><span class="sxs-lookup"><span data-stu-id="d5b82-136">In the Outcome status field, select 'Pass'.</span></span>
11. <span data-ttu-id="d5b82-137">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="d5b82-137">Click Save.</span></span>
12. <span data-ttu-id="d5b82-138">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d5b82-138">Click New.</span></span>
13. <span data-ttu-id="d5b82-139">Írjon be egy értéket az Eredmény mezőbe.</span><span class="sxs-lookup"><span data-stu-id="d5b82-139">In the Outcome field, type a value.</span></span>
14. <span data-ttu-id="d5b82-140">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="d5b82-140">In the Description field, type a value.</span></span>
15. <span data-ttu-id="d5b82-141">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="d5b82-141">Click Save.</span></span>
16. <span data-ttu-id="d5b82-142">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="d5b82-142">Close the page.</span></span>
17. <span data-ttu-id="d5b82-143">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="d5b82-143">Close the page.</span></span>

## <a name="set-up-item-sampling"></a><span data-ttu-id="d5b82-144">Cikk-mintavétel beállítása</span><span class="sxs-lookup"><span data-stu-id="d5b82-144">Set up item sampling</span></span>
1. <span data-ttu-id="d5b82-145">Ugorjon a következőhöz: Készletkezelés > Beállítás > Minőség-ellenőrzés > Cikk-mintavétel.</span><span class="sxs-lookup"><span data-stu-id="d5b82-145">Go to Inventory management > Setup > Quality control > Item sampling.</span></span>
2. <span data-ttu-id="d5b82-146">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d5b82-146">Click New.</span></span>
3. <span data-ttu-id="d5b82-147">Írjon be egy értéket a Cikk-mintavétel mezőbe.</span><span class="sxs-lookup"><span data-stu-id="d5b82-147">In the Item sampling field, type a value.</span></span>
4. <span data-ttu-id="d5b82-148">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="d5b82-148">In the Description field, type a value.</span></span>
5. <span data-ttu-id="d5b82-149">Adjon meg egy számot az Érték mezőben.</span><span class="sxs-lookup"><span data-stu-id="d5b82-149">In the Value field, enter a number.</span></span>
    * <span data-ttu-id="d5b82-150">Ez az értéket a szomszédos mezőben kiválasztott Megadott mennyiségre vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="d5b82-150">This value relates to the Quantity specification that’s selected in the adjacent field.</span></span>  
6. <span data-ttu-id="d5b82-151">Bontsa ki vagy csukja össze a Folyamat szakaszt.</span><span class="sxs-lookup"><span data-stu-id="d5b82-151">Expand or collapse the Process section.</span></span>
7. <span data-ttu-id="d5b82-152">Jelölje be a Teljes zárolás jelölőnégyzetet, vagy törölje belőle a jelet.</span><span class="sxs-lookup"><span data-stu-id="d5b82-152">Select or clear the Full blocking check box.</span></span>
    * <span data-ttu-id="d5b82-153">Ha kiválasztja ezt a lehetőséget, úgy sikertelen teszt esetén blokkolva lesz a teljes adat vagy rendelési sor mennyiség.</span><span class="sxs-lookup"><span data-stu-id="d5b82-153">If you select this option, the whole lot or order line quantity is blocked if a test is failed.</span></span> <span data-ttu-id="d5b82-154">Ha nem választja ki a lehetőséget, úgy csak a minőségi rendelésben szereplő cikkek kerülnek blokkolásra.</span><span class="sxs-lookup"><span data-stu-id="d5b82-154">If you don't select it, only the items in the quality order are blocked.</span></span>  
8. <span data-ttu-id="d5b82-155">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="d5b82-155">Click Save.</span></span>
9. <span data-ttu-id="d5b82-156">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="d5b82-156">Close the page.</span></span>

## <a name="create-a-quality-group"></a><span data-ttu-id="d5b82-157">Minőségi csoport létrehozása</span><span class="sxs-lookup"><span data-stu-id="d5b82-157">Create a quality group</span></span>
1. <span data-ttu-id="d5b82-158">Ugorjon a következőhöz: Készletkezelés > Beállítás > Minőség-ellenőrzés > Minőségi csoportok.</span><span class="sxs-lookup"><span data-stu-id="d5b82-158">Go to Inventory management > Setup > Quality control > Quality groups.</span></span>
2. <span data-ttu-id="d5b82-159">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d5b82-159">Click New.</span></span>
3. <span data-ttu-id="d5b82-160">Írjon be egy értéket a Minőségi csoport mezőbe.</span><span class="sxs-lookup"><span data-stu-id="d5b82-160">In the Quality group field, type a value.</span></span>
    * <span data-ttu-id="d5b82-161">Használjon leíró jellegű nevet, ami segít beazonosítani, hogy a csoport milyen jellegű cikkeket tartalmaz (mintavételi feltételek).</span><span class="sxs-lookup"><span data-stu-id="d5b82-161">Use a descriptive name to help you identify which kind of items the group will contain (your sampling criteria).</span></span>  
4. <span data-ttu-id="d5b82-162">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="d5b82-162">In the Description field, type a value.</span></span>
5. <span data-ttu-id="d5b82-163">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="d5b82-163">Click Save.</span></span>
6. <span data-ttu-id="d5b82-164">Kattintson a Cikkek hozzáadása pontra.</span><span class="sxs-lookup"><span data-stu-id="d5b82-164">Click Add items.</span></span>
7. <span data-ttu-id="d5b82-165">Válassza ki a Cikkszám sort</span><span class="sxs-lookup"><span data-stu-id="d5b82-165">Select the Item number row</span></span>
    * <span data-ttu-id="d5b82-166">Ebben a példában a szűrést a cikkszám alapján futtatjuk.</span><span class="sxs-lookup"><span data-stu-id="d5b82-166">In this example the filtering will be run based on  the item number.</span></span>  
8. <span data-ttu-id="d5b82-167">Érték beírása a Feltétel mezőbe.</span><span class="sxs-lookup"><span data-stu-id="d5b82-167">In the Criteria field, type a value.</span></span>
    * <span data-ttu-id="d5b82-168">A T betűvel kezdődő cikkszámok szűréséhez például gépelje be azt, hogy T\*.</span><span class="sxs-lookup"><span data-stu-id="d5b82-168">For example, type T\* to filter on the item numbers that start with T.</span></span>  
9. <span data-ttu-id="d5b82-169">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="d5b82-169">Click OK.</span></span>
10. <span data-ttu-id="d5b82-170">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="d5b82-170">Click OK.</span></span>
11. <span data-ttu-id="d5b82-171">Cikkminőségi csoportok megtekintése.</span><span class="sxs-lookup"><span data-stu-id="d5b82-171">Click Item quality groups.</span></span>
12. <span data-ttu-id="d5b82-172">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="d5b82-172">Close the page.</span></span>
13. <span data-ttu-id="d5b82-173">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="d5b82-173">Close the page.</span></span>

## <a name="create-a-test-group"></a><span data-ttu-id="d5b82-174">Tesztcsoport létrehozása</span><span class="sxs-lookup"><span data-stu-id="d5b82-174">Create a test group</span></span>
1. <span data-ttu-id="d5b82-175">Ugorjon a következőhöz: Készletkezelés > Beállítás > Minőség-ellenőrzés > Tesztcsoportok.</span><span class="sxs-lookup"><span data-stu-id="d5b82-175">Go to Inventory management > Setup > Quality control > Test groups.</span></span>
2. <span data-ttu-id="d5b82-176">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d5b82-176">Click New.</span></span>
3. <span data-ttu-id="d5b82-177">Írjon be egy értéket a Tesztcsoport mezőbe.</span><span class="sxs-lookup"><span data-stu-id="d5b82-177">In the Test group field, type a value.</span></span>
    * <span data-ttu-id="d5b82-178">Olyan nevet adjon a Tesztcsoportnak, amely utal arra, hogy milyen jellegű teszteket futtat, és azt milyen minőségi csoporttal kell társítani.</span><span class="sxs-lookup"><span data-stu-id="d5b82-178">Give the Test group a name that will help you remember what kind of tests are being run, and which quality group it should be associated with.</span></span> <span data-ttu-id="d5b82-179">Ha például azt olyan minőségi csoporttal kívánja használni, ami a „T”-vel kezdődő cikkeket választja ki, úgy nevezze a csoportot például „T-cikk tesztek”-nek.</span><span class="sxs-lookup"><span data-stu-id="d5b82-179">For example, it it’s to be used with a quality group that selects items starting with “T”, you could call it “T-item tests”.</span></span>  
4. <span data-ttu-id="d5b82-180">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="d5b82-180">In the Description field, type a value.</span></span>
5. <span data-ttu-id="d5b82-181">A Cikk-mintavétel mezőben válassza a korábban létrehozott cikk-mintavétel sort.</span><span class="sxs-lookup"><span data-stu-id="d5b82-181">In the Item sampling field, select the item sampling line that you created before.</span></span>
6. <span data-ttu-id="d5b82-182">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="d5b82-182">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="d5b82-183">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="d5b82-183">Click Add.</span></span>
8. <span data-ttu-id="d5b82-184">Adjon meg egy számot a Sorozatszám mezőben.</span><span class="sxs-lookup"><span data-stu-id="d5b82-184">In the Sequence number field, enter a number.</span></span>
9. <span data-ttu-id="d5b82-185">A Teszt mezőben válassza ki az előbbiekben létrehozott tesztet.</span><span class="sxs-lookup"><span data-stu-id="d5b82-185">In the Test field, select the test that you created earlier.</span></span>
10. <span data-ttu-id="d5b82-186">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="d5b82-186">In the list, find and select the desired record.</span></span>
11. <span data-ttu-id="d5b82-187">Kattintson a Teszt lapra.</span><span class="sxs-lookup"><span data-stu-id="d5b82-187">Click the Test tab.</span></span>
12. <span data-ttu-id="d5b82-188">A Változók mezőben válassza ki az előbbiekben létrehozott változót.</span><span class="sxs-lookup"><span data-stu-id="d5b82-188">In the Variable field, select the test variable that you created before</span></span>
13. <span data-ttu-id="d5b82-189">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="d5b82-189">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="d5b82-190">Az Alapértelmezett eredmény mezőben kattintson a legördülő gombra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="d5b82-190">In the Default outcome field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="d5b82-191">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="d5b82-191">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="d5b82-192">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="d5b82-192">Click Save.</span></span>
17. <span data-ttu-id="d5b82-193">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="d5b82-193">Close the page.</span></span>

## <a name="define-when-quality-orders-will-be-created"></a><span data-ttu-id="d5b82-194">Határozza meg, hogy mikor történjen a minőségi rendelések létrehozása</span><span class="sxs-lookup"><span data-stu-id="d5b82-194">Define when quality orders will be created</span></span>
1. <span data-ttu-id="d5b82-195">Ugorjon a következőhöz: Készletkezelés > Beállítás > Minőség-ellenőrzés > Minőségi társítások.</span><span class="sxs-lookup"><span data-stu-id="d5b82-195">Go to Inventory management > Setup > Quality control > Quality associations.</span></span>
2. <span data-ttu-id="d5b82-196">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d5b82-196">Click New.</span></span>
3. <span data-ttu-id="d5b82-197">Válasszon egy lehetőséget a Hivatkozástípus mezőben.</span><span class="sxs-lookup"><span data-stu-id="d5b82-197">In the Reference type field, select an option.</span></span>
4. <span data-ttu-id="d5b82-198">Válassza a „Csoport” lehetőséget a Cikk mezőben:</span><span class="sxs-lookup"><span data-stu-id="d5b82-198">In the Item code field, select 'Group'.</span></span>
    * <span data-ttu-id="d5b82-199">Ebben a példában a „Csoport”-ot " választjuk ki és a korábban létrehozott minőségi csoportot fogjuk felhasználni.</span><span class="sxs-lookup"><span data-stu-id="d5b82-199">In this example, we’ll select "Group" and use the quality group we created before.</span></span> <span data-ttu-id="d5b82-200">Használhatja a „Táblázat” beállítást is, ha manuálisan kívánja megadni a cikkeket, vagy válassza a „Mind” lehetőséget az összes cikk, a minőségi csoporthoz történő hozzáadásához.</span><span class="sxs-lookup"><span data-stu-id="d5b82-200">You could also set this to "Table" to specify the items manually, or select "All" to add all items to the quality order.</span></span>  
5. <span data-ttu-id="d5b82-201">A Cikk mezőben válassza ki az előbbiekben létrehozott minőségi csoportot.</span><span class="sxs-lookup"><span data-stu-id="d5b82-201">In the Item field, select the quality group that you created before.</span></span>
    * <span data-ttu-id="d5b82-202">A Cikk mezőben rendelkezésre álló lehetőségek köre attól függ, hogy mit állított be a Cikk-kód mezőben.</span><span class="sxs-lookup"><span data-stu-id="d5b82-202">The options available in the Item field depend on what you set in the Item code field.</span></span>  
6. <span data-ttu-id="d5b82-203">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="d5b82-203">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="d5b82-204">Bontsa ki vagy csukja össze a Folyamat szakaszt.</span><span class="sxs-lookup"><span data-stu-id="d5b82-204">Expand or collapse the Process section.</span></span>
8. <span data-ttu-id="d5b82-205">Válasszon egy lehetőséget az Eseménytípus mezőben.</span><span class="sxs-lookup"><span data-stu-id="d5b82-205">In the Event type field, select an option.</span></span>
    * <span data-ttu-id="d5b82-206">Ez az esemény aktiválja a tesztet.</span><span class="sxs-lookup"><span data-stu-id="d5b82-206">This is the event that triggers the test.</span></span> <span data-ttu-id="d5b82-207">A rendelkezésre álló lehetőségek köre attól függ, hogy milyen eljárást választott ki a Hivatkozástípus mezőben</span><span class="sxs-lookup"><span data-stu-id="d5b82-207">The options available here depend on which process you selected in the Reference type field.</span></span>  
9. <span data-ttu-id="d5b82-208">Válasszon egy lehetőséget a Végrehajtás mezőben.</span><span class="sxs-lookup"><span data-stu-id="d5b82-208">In the Execution field, select an option.</span></span>
10. <span data-ttu-id="d5b82-209">Bontsa ki vagy csukja össze a Minőségi rendelési folyamat szakaszt.</span><span class="sxs-lookup"><span data-stu-id="d5b82-209">Expand or collapse the Quality order process section.</span></span>
11. <span data-ttu-id="d5b82-210">Az Eseményzárolás mezőben kattintson a legördülő gombra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="d5b82-210">In the Event blocking field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="d5b82-211">Ez a mező azon eljárások jegyzékét tartalmazza, melyeket zárolni lehet, amikor a minőségi rendelés még nyitva van.</span><span class="sxs-lookup"><span data-stu-id="d5b82-211">This field shows the list of processes that it’s possible to block if the quality order is still open.</span></span> <span data-ttu-id="d5b82-212">A lehetőségek köre attól függ, hogy mit választott ki az Eseménytípus mezőben.</span><span class="sxs-lookup"><span data-stu-id="d5b82-212">The options depend on what you selected in the Event type field.</span></span>  
12. <span data-ttu-id="d5b82-213">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="d5b82-213">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="d5b82-214">Ez a korábban kiválasztott értékek függvénye.</span><span class="sxs-lookup"><span data-stu-id="d5b82-214">This will be depending on the previous selected values.</span></span> <span data-ttu-id="d5b82-215">Jelölje be, ha a következő folyamatokat zárolni kell, amikor nyitott minőségi rendelések kapcsolódnak egy forrásbizonylat-sorhoz.</span><span class="sxs-lookup"><span data-stu-id="d5b82-215">Select if the following processes must be blocked while having open quality orders linked to a source document line.</span></span>  
13. <span data-ttu-id="d5b82-216">Bontsa ki vagy csukja össze a Specifikációk szakaszt.</span><span class="sxs-lookup"><span data-stu-id="d5b82-216">Expand or collapse the Specifications section.</span></span>
14. <span data-ttu-id="d5b82-217">A Tesztcsoport mezőben válassza ki az előbbiekben létrehozott tesztcsoportot.</span><span class="sxs-lookup"><span data-stu-id="d5b82-217">In the Test group field, select the test group that you created before.</span></span>
15. <span data-ttu-id="d5b82-218">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="d5b82-218">In the list, find and select the desired record.</span></span>
16. <span data-ttu-id="d5b82-219">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="d5b82-219">Click Save.</span></span>
17. <span data-ttu-id="d5b82-220">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="d5b82-220">Close the page.</span></span>

