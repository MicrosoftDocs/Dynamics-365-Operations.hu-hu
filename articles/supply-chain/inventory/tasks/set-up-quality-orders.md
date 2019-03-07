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
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "356990"
---
# <a name="set-up-quality-orders"></a><span data-ttu-id="db2a1-103">Minőségi rendelések beállítása</span><span class="sxs-lookup"><span data-stu-id="db2a1-103">Set up quality orders</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="db2a1-104">Ez az eljárás bemutatja, hogy hogyan engedélyezheti a minőségkezelési folyamatot, ha a bejövő készletet, a beérkezés regisztrációja után azonnal ellenőrizni szükséges.</span><span class="sxs-lookup"><span data-stu-id="db2a1-104">This procedure shows you how to enable a quality management process where incoming inventory must be inspected immediately after arrival registration.</span></span> <span data-ttu-id="db2a1-105">Ezt az eljárást jellemzően egy minőségbiztosítási vezető végzi.</span><span class="sxs-lookup"><span data-stu-id="db2a1-105">The procedure will typically be carried out by a quality manager.</span></span> <span data-ttu-id="db2a1-106">A folyamat részét képezi a minőségi csoport létrehozása, a mintavétellel érintett cikkek, valamint a minőségi csoportban szereplő cikkeken végzendő tesztek csoportosítását szolgáló tesztcsoport meghatározása.</span><span class="sxs-lookup"><span data-stu-id="db2a1-106">The process includes the creation of a quality group, to define the items that are going to be sampled, and a test group to group the tests that are to be performed on items in the quality group.</span></span> <span data-ttu-id="db2a1-107">Ezt az útmutatót lefuttathatja az USMF bemutatócégen.</span><span class="sxs-lookup"><span data-stu-id="db2a1-107">You can run this guide in the USMF demo data company.</span></span>


## <a name="enable-quality-management"></a><span data-ttu-id="db2a1-108">Minőségkezelés engedélyezése</span><span class="sxs-lookup"><span data-stu-id="db2a1-108">Enable quality management</span></span>
1. <span data-ttu-id="db2a1-109">Ugrás a Készletkezelés > Beállítás > Készlet- és raktárkezelési paraméterek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="db2a1-109">Go to Inventory management > Setup > Inventory and warehouse management parameters.</span></span>
2. <span data-ttu-id="db2a1-110">Kattintson a Minőségkezelés lapra.</span><span class="sxs-lookup"><span data-stu-id="db2a1-110">Click the Quality management tab.</span></span>
3. <span data-ttu-id="db2a1-111">Állítsa a Minőségkezelés használata beállítást Igen értékre.</span><span class="sxs-lookup"><span data-stu-id="db2a1-111">Set the Use quality management option to Yes.</span></span>
4. <span data-ttu-id="db2a1-112">Kattintson a Jelentés-beállítás elemre.</span><span class="sxs-lookup"><span data-stu-id="db2a1-112">Click Report setup.</span></span>
    * <span data-ttu-id="db2a1-113">Az USMF-ben, a minőségkezelési jelentések beállításai előre definiálva vannak.</span><span class="sxs-lookup"><span data-stu-id="db2a1-113">In USMF, the report setup for quality management is already defined.</span></span> <span data-ttu-id="db2a1-114">Ha ez nem történt meg, adjon hozzá új sorokat a különböző típusú jelentés típusokhoz, majd válassza ki az egyes jelentésekhez használandó dokumentum típust.</span><span class="sxs-lookup"><span data-stu-id="db2a1-114">If this wasn’t done, you’d add new lines here for the different report types, and select the type of document to be used for each report.</span></span>  
5. <span data-ttu-id="db2a1-115">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="db2a1-115">Close the page.</span></span>
6. <span data-ttu-id="db2a1-116">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="db2a1-116">Close the page.</span></span>

## <a name="create-a-test"></a><span data-ttu-id="db2a1-117">Teszt létrehozása</span><span class="sxs-lookup"><span data-stu-id="db2a1-117">Create a test</span></span>
1. <span data-ttu-id="db2a1-118">Ugorjon a következőhöz: Készletkezelés > Beállítás > Minőség-ellenőrzés > Készlet.</span><span class="sxs-lookup"><span data-stu-id="db2a1-118">Go to Inventory management > Setup > Quality control > Tests.</span></span>
2. <span data-ttu-id="db2a1-119">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="db2a1-119">Click New.</span></span>
3. <span data-ttu-id="db2a1-120">Írjon be egy értéket a Teszt mezőbe.</span><span class="sxs-lookup"><span data-stu-id="db2a1-120">In the Test field, type a value.</span></span>
4. <span data-ttu-id="db2a1-121">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="db2a1-121">In the Description field, type a value.</span></span>
5. <span data-ttu-id="db2a1-122">Az „Opció” kiválasztása a Típus mezőben.</span><span class="sxs-lookup"><span data-stu-id="db2a1-122">In the Type field, select 'Option'.</span></span>
    * <span data-ttu-id="db2a1-123">Ebben a példában kiválasztjuk az „Opciók” lehetőséget, ami lehetővé teszi a teszteredmények, előre megadott értékek alapján történő társítását.</span><span class="sxs-lookup"><span data-stu-id="db2a1-123">In this example, we'll select "Option" which will make it possible to assign the test results based on pre-defined values.</span></span>  
6. <span data-ttu-id="db2a1-124">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="db2a1-124">Click Save.</span></span>
7. <span data-ttu-id="db2a1-125">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="db2a1-125">Close the page.</span></span>

## <a name="create-test-variables-to-define-the-way-test-results-are-recorded"></a><span data-ttu-id="db2a1-126">Tesztváltozók létrehozása a teszteredmények rögzítési módjának meghatározása érdekében</span><span class="sxs-lookup"><span data-stu-id="db2a1-126">Create Test variables to define the way test results are recorded</span></span>
1. <span data-ttu-id="db2a1-127">Ugorjon a következőhöz: Készletkezelés > Beállítás > Minőség-ellenőrzés > Tesztváltozók.</span><span class="sxs-lookup"><span data-stu-id="db2a1-127">Go to Inventory management > Setup > Quality control > Test variables.</span></span>
2. <span data-ttu-id="db2a1-128">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="db2a1-128">Click New.</span></span>
3. <span data-ttu-id="db2a1-129">Írjon be egy értéket a Változó mezőbe.</span><span class="sxs-lookup"><span data-stu-id="db2a1-129">In the Variable field, type a value.</span></span>
4. <span data-ttu-id="db2a1-130">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="db2a1-130">In the Description field, type a value.</span></span>
5. <span data-ttu-id="db2a1-131">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="db2a1-131">Click Save.</span></span>
6. <span data-ttu-id="db2a1-132">Kattintson az Eredmények elemre.</span><span class="sxs-lookup"><span data-stu-id="db2a1-132">Click Outcomes.</span></span>
7. <span data-ttu-id="db2a1-133">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="db2a1-133">Click New.</span></span>
8. <span data-ttu-id="db2a1-134">Írjon be egy értéket az Eredmény mezőbe.</span><span class="sxs-lookup"><span data-stu-id="db2a1-134">In the Outcome field, type a value.</span></span>
9. <span data-ttu-id="db2a1-135">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="db2a1-135">In the Description field, type a value.</span></span>
10. <span data-ttu-id="db2a1-136">Az Eredményállapot mezőben válassza a „Megfelelt” értéket.</span><span class="sxs-lookup"><span data-stu-id="db2a1-136">In the Outcome status field, select 'Pass'.</span></span>
11. <span data-ttu-id="db2a1-137">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="db2a1-137">Click Save.</span></span>
12. <span data-ttu-id="db2a1-138">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="db2a1-138">Click New.</span></span>
13. <span data-ttu-id="db2a1-139">Írjon be egy értéket az Eredmény mezőbe.</span><span class="sxs-lookup"><span data-stu-id="db2a1-139">In the Outcome field, type a value.</span></span>
14. <span data-ttu-id="db2a1-140">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="db2a1-140">In the Description field, type a value.</span></span>
15. <span data-ttu-id="db2a1-141">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="db2a1-141">Click Save.</span></span>
16. <span data-ttu-id="db2a1-142">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="db2a1-142">Close the page.</span></span>
17. <span data-ttu-id="db2a1-143">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="db2a1-143">Close the page.</span></span>

## <a name="set-up-item-sampling"></a><span data-ttu-id="db2a1-144">Cikk-mintavétel beállítása</span><span class="sxs-lookup"><span data-stu-id="db2a1-144">Set up item sampling</span></span>
1. <span data-ttu-id="db2a1-145">Ugorjon a következőhöz: Készletkezelés > Beállítás > Minőség-ellenőrzés > Cikk-mintavétel.</span><span class="sxs-lookup"><span data-stu-id="db2a1-145">Go to Inventory management > Setup > Quality control > Item sampling.</span></span>
2. <span data-ttu-id="db2a1-146">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="db2a1-146">Click New.</span></span>
3. <span data-ttu-id="db2a1-147">Írjon be egy értéket a Cikk-mintavétel mezőbe.</span><span class="sxs-lookup"><span data-stu-id="db2a1-147">In the Item sampling field, type a value.</span></span>
4. <span data-ttu-id="db2a1-148">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="db2a1-148">In the Description field, type a value.</span></span>
5. <span data-ttu-id="db2a1-149">Adjon meg egy számot az Érték mezőben.</span><span class="sxs-lookup"><span data-stu-id="db2a1-149">In the Value field, enter a number.</span></span>
    * <span data-ttu-id="db2a1-150">Ez az értéket a szomszédos mezőben kiválasztott Megadott mennyiségre vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="db2a1-150">This value relates to the Quantity specification that’s selected in the adjacent field.</span></span>  
6. <span data-ttu-id="db2a1-151">Bontsa ki vagy csukja össze a Folyamat szakaszt.</span><span class="sxs-lookup"><span data-stu-id="db2a1-151">Expand or collapse the Process section.</span></span>
7. <span data-ttu-id="db2a1-152">Jelölje be a Teljes zárolás jelölőnégyzetet, vagy törölje belőle a jelet.</span><span class="sxs-lookup"><span data-stu-id="db2a1-152">Select or clear the Full blocking check box.</span></span>
    * <span data-ttu-id="db2a1-153">Ha kiválasztja ezt a lehetőséget, úgy sikertelen teszt esetén blokkolva lesz a teljes adat vagy rendelési sor mennyiség.</span><span class="sxs-lookup"><span data-stu-id="db2a1-153">If you select this option, the whole lot or order line quantity is blocked if a test is failed.</span></span> <span data-ttu-id="db2a1-154">Ha nem választja ki a lehetőséget, úgy csak a minőségi rendelésben szereplő cikkek kerülnek blokkolásra.</span><span class="sxs-lookup"><span data-stu-id="db2a1-154">If you don't select it, only the items in the quality order are blocked.</span></span>  
8. <span data-ttu-id="db2a1-155">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="db2a1-155">Click Save.</span></span>
9. <span data-ttu-id="db2a1-156">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="db2a1-156">Close the page.</span></span>

## <a name="create-a-quality-group"></a><span data-ttu-id="db2a1-157">Minőségi csoport létrehozása</span><span class="sxs-lookup"><span data-stu-id="db2a1-157">Create a quality group</span></span>
1. <span data-ttu-id="db2a1-158">Ugorjon a következőhöz: Készletkezelés > Beállítás > Minőség-ellenőrzés > Minőségi csoportok.</span><span class="sxs-lookup"><span data-stu-id="db2a1-158">Go to Inventory management > Setup > Quality control > Quality groups.</span></span>
2. <span data-ttu-id="db2a1-159">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="db2a1-159">Click New.</span></span>
3. <span data-ttu-id="db2a1-160">Írjon be egy értéket a Minőségi csoport mezőbe.</span><span class="sxs-lookup"><span data-stu-id="db2a1-160">In the Quality group field, type a value.</span></span>
    * <span data-ttu-id="db2a1-161">Használjon leíró jellegű nevet, ami segít beazonosítani, hogy a csoport milyen jellegű cikkeket tartalmaz (mintavételi feltételek).</span><span class="sxs-lookup"><span data-stu-id="db2a1-161">Use a descriptive name to help you identify which kind of items the group will contain (your sampling criteria).</span></span>  
4. <span data-ttu-id="db2a1-162">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="db2a1-162">In the Description field, type a value.</span></span>
5. <span data-ttu-id="db2a1-163">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="db2a1-163">Click Save.</span></span>
6. <span data-ttu-id="db2a1-164">Kattintson a Cikkek hozzáadása pontra.</span><span class="sxs-lookup"><span data-stu-id="db2a1-164">Click Add items.</span></span>
7. <span data-ttu-id="db2a1-165">Válassza ki a Cikkszám sort</span><span class="sxs-lookup"><span data-stu-id="db2a1-165">Select the Item number row</span></span>
    * <span data-ttu-id="db2a1-166">Ebben a példában a szűrést a cikkszám alapján futtatjuk.</span><span class="sxs-lookup"><span data-stu-id="db2a1-166">In this example the filtering will be run based on  the item number.</span></span>  
8. <span data-ttu-id="db2a1-167">Érték beírása a Feltétel mezőbe.</span><span class="sxs-lookup"><span data-stu-id="db2a1-167">In the Criteria field, type a value.</span></span>
    * <span data-ttu-id="db2a1-168">A T betűvel kezdődő cikkszámok szűréséhez például gépelje be azt, hogy T\*.</span><span class="sxs-lookup"><span data-stu-id="db2a1-168">For example, type T\* to filter on the item numbers that start with T.</span></span>  
9. <span data-ttu-id="db2a1-169">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="db2a1-169">Click OK.</span></span>
10. <span data-ttu-id="db2a1-170">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="db2a1-170">Click OK.</span></span>
11. <span data-ttu-id="db2a1-171">Cikkminőségi csoportok megtekintése.</span><span class="sxs-lookup"><span data-stu-id="db2a1-171">Click Item quality groups.</span></span>
12. <span data-ttu-id="db2a1-172">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="db2a1-172">Close the page.</span></span>
13. <span data-ttu-id="db2a1-173">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="db2a1-173">Close the page.</span></span>

## <a name="create-a-test-group"></a><span data-ttu-id="db2a1-174">Tesztcsoport létrehozása</span><span class="sxs-lookup"><span data-stu-id="db2a1-174">Create a test group</span></span>
1. <span data-ttu-id="db2a1-175">Ugorjon a következőhöz: Készletkezelés > Beállítás > Minőség-ellenőrzés > Tesztcsoportok.</span><span class="sxs-lookup"><span data-stu-id="db2a1-175">Go to Inventory management > Setup > Quality control > Test groups.</span></span>
2. <span data-ttu-id="db2a1-176">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="db2a1-176">Click New.</span></span>
3. <span data-ttu-id="db2a1-177">Írjon be egy értéket a Tesztcsoport mezőbe.</span><span class="sxs-lookup"><span data-stu-id="db2a1-177">In the Test group field, type a value.</span></span>
    * <span data-ttu-id="db2a1-178">Olyan nevet adjon a Tesztcsoportnak, amely utal arra, hogy milyen jellegű teszteket futtat, és azt milyen minőségi csoporttal kell társítani.</span><span class="sxs-lookup"><span data-stu-id="db2a1-178">Give the Test group a name that will help you remember what kind of tests are being run, and which quality group it should be associated with.</span></span> <span data-ttu-id="db2a1-179">Ha például azt olyan minőségi csoporttal kívánja használni, ami a „T”-vel kezdődő cikkeket választja ki, úgy nevezze a csoportot például „T-cikk tesztek”-nek.</span><span class="sxs-lookup"><span data-stu-id="db2a1-179">For example, it it’s to be used with a quality group that selects items starting with “T”, you could call it “T-item tests”.</span></span>  
4. <span data-ttu-id="db2a1-180">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="db2a1-180">In the Description field, type a value.</span></span>
5. <span data-ttu-id="db2a1-181">A Cikk-mintavétel mezőben válassza a korábban létrehozott cikk-mintavétel sort.</span><span class="sxs-lookup"><span data-stu-id="db2a1-181">In the Item sampling field, select the item sampling line that you created before.</span></span>
6. <span data-ttu-id="db2a1-182">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="db2a1-182">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="db2a1-183">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="db2a1-183">Click Add.</span></span>
8. <span data-ttu-id="db2a1-184">Adjon meg egy számot a Sorozatszám mezőben.</span><span class="sxs-lookup"><span data-stu-id="db2a1-184">In the Sequence number field, enter a number.</span></span>
9. <span data-ttu-id="db2a1-185">A Teszt mezőben válassza ki az előbbiekben létrehozott tesztet.</span><span class="sxs-lookup"><span data-stu-id="db2a1-185">In the Test field, select the test that you created earlier.</span></span>
10. <span data-ttu-id="db2a1-186">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="db2a1-186">In the list, find and select the desired record.</span></span>
11. <span data-ttu-id="db2a1-187">Kattintson a Teszt lapra.</span><span class="sxs-lookup"><span data-stu-id="db2a1-187">Click the Test tab.</span></span>
12. <span data-ttu-id="db2a1-188">A Változók mezőben válassza ki az előbbiekben létrehozott változót.</span><span class="sxs-lookup"><span data-stu-id="db2a1-188">In the Variable field, select the test variable that you created before</span></span>
13. <span data-ttu-id="db2a1-189">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="db2a1-189">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="db2a1-190">Az Alapértelmezett eredmény mezőben kattintson a legördülő gombra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="db2a1-190">In the Default outcome field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="db2a1-191">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="db2a1-191">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="db2a1-192">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="db2a1-192">Click Save.</span></span>
17. <span data-ttu-id="db2a1-193">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="db2a1-193">Close the page.</span></span>

## <a name="define-when-quality-orders-will-be-created"></a><span data-ttu-id="db2a1-194">Határozza meg, hogy mikor történjen a minőségi rendelések létrehozása</span><span class="sxs-lookup"><span data-stu-id="db2a1-194">Define when quality orders will be created</span></span>
1. <span data-ttu-id="db2a1-195">Ugorjon a következőhöz: Készletkezelés > Beállítás > Minőség-ellenőrzés > Minőségi társítások.</span><span class="sxs-lookup"><span data-stu-id="db2a1-195">Go to Inventory management > Setup > Quality control > Quality associations.</span></span>
2. <span data-ttu-id="db2a1-196">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="db2a1-196">Click New.</span></span>
3. <span data-ttu-id="db2a1-197">Válasszon egy lehetőséget a Hivatkozástípus mezőben.</span><span class="sxs-lookup"><span data-stu-id="db2a1-197">In the Reference type field, select an option.</span></span>
4. <span data-ttu-id="db2a1-198">Válassza a „Csoport” lehetőséget a Cikk mezőben:</span><span class="sxs-lookup"><span data-stu-id="db2a1-198">In the Item code field, select 'Group'.</span></span>
    * <span data-ttu-id="db2a1-199">Ebben a példában a „Csoport”-ot " választjuk ki és a korábban létrehozott minőségi csoportot fogjuk felhasználni.</span><span class="sxs-lookup"><span data-stu-id="db2a1-199">In this example, we’ll select "Group" and use the quality group we created before.</span></span> <span data-ttu-id="db2a1-200">Használhatja a „Táblázat” beállítást is, ha manuálisan kívánja megadni a cikkeket, vagy válassza a „Mind” lehetőséget az összes cikk, a minőségi csoporthoz történő hozzáadásához.</span><span class="sxs-lookup"><span data-stu-id="db2a1-200">You could also set this to "Table" to specify the items manually, or select "All" to add all items to the quality order.</span></span>  
5. <span data-ttu-id="db2a1-201">A Cikk mezőben válassza ki az előbbiekben létrehozott minőségi csoportot.</span><span class="sxs-lookup"><span data-stu-id="db2a1-201">In the Item field, select the quality group that you created before.</span></span>
    * <span data-ttu-id="db2a1-202">A Cikk mezőben rendelkezésre álló lehetőségek köre attól függ, hogy mit állított be a Cikk-kód mezőben.</span><span class="sxs-lookup"><span data-stu-id="db2a1-202">The options available in the Item field depend on what you set in the Item code field.</span></span>  
6. <span data-ttu-id="db2a1-203">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="db2a1-203">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="db2a1-204">Bontsa ki vagy csukja össze a Folyamat szakaszt.</span><span class="sxs-lookup"><span data-stu-id="db2a1-204">Expand or collapse the Process section.</span></span>
8. <span data-ttu-id="db2a1-205">Válasszon egy lehetőséget az Eseménytípus mezőben.</span><span class="sxs-lookup"><span data-stu-id="db2a1-205">In the Event type field, select an option.</span></span>
    * <span data-ttu-id="db2a1-206">Ez az esemény aktiválja a tesztet.</span><span class="sxs-lookup"><span data-stu-id="db2a1-206">This is the event that triggers the test.</span></span> <span data-ttu-id="db2a1-207">A rendelkezésre álló lehetőségek köre attól függ, hogy milyen eljárást választott ki a Hivatkozástípus mezőben</span><span class="sxs-lookup"><span data-stu-id="db2a1-207">The options available here depend on which process you selected in the Reference type field.</span></span>  
9. <span data-ttu-id="db2a1-208">Válasszon egy lehetőséget a Végrehajtás mezőben.</span><span class="sxs-lookup"><span data-stu-id="db2a1-208">In the Execution field, select an option.</span></span>
10. <span data-ttu-id="db2a1-209">Bontsa ki vagy csukja össze a Minőségi rendelési folyamat szakaszt.</span><span class="sxs-lookup"><span data-stu-id="db2a1-209">Expand or collapse the Quality order process section.</span></span>
11. <span data-ttu-id="db2a1-210">Az Eseményzárolás mezőben kattintson a legördülő gombra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="db2a1-210">In the Event blocking field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="db2a1-211">Ez a mező azon eljárások jegyzékét tartalmazza, melyeket zárolni lehet, amikor a minőségi rendelés még nyitva van.</span><span class="sxs-lookup"><span data-stu-id="db2a1-211">This field shows the list of processes that it’s possible to block if the quality order is still open.</span></span> <span data-ttu-id="db2a1-212">A lehetőségek köre attól függ, hogy mit választott ki az Eseménytípus mezőben.</span><span class="sxs-lookup"><span data-stu-id="db2a1-212">The options depend on what you selected in the Event type field.</span></span>  
12. <span data-ttu-id="db2a1-213">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="db2a1-213">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="db2a1-214">Ez a korábban kiválasztott értékek függvénye.</span><span class="sxs-lookup"><span data-stu-id="db2a1-214">This will be depending on the previous selected values.</span></span> <span data-ttu-id="db2a1-215">Jelölje be, ha a következő folyamatokat zárolni kell, amikor nyitott minőségi rendelések kapcsolódnak egy forrásbizonylat-sorhoz.</span><span class="sxs-lookup"><span data-stu-id="db2a1-215">Select if the following processes must be blocked while having open quality orders linked to a source document line.</span></span>  
13. <span data-ttu-id="db2a1-216">Bontsa ki vagy csukja össze a Specifikációk szakaszt.</span><span class="sxs-lookup"><span data-stu-id="db2a1-216">Expand or collapse the Specifications section.</span></span>
14. <span data-ttu-id="db2a1-217">A Tesztcsoport mezőben válassza ki az előbbiekben létrehozott tesztcsoportot.</span><span class="sxs-lookup"><span data-stu-id="db2a1-217">In the Test group field, select the test group that you created before.</span></span>
15. <span data-ttu-id="db2a1-218">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="db2a1-218">In the list, find and select the desired record.</span></span>
16. <span data-ttu-id="db2a1-219">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="db2a1-219">Click Save.</span></span>
17. <span data-ttu-id="db2a1-220">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="db2a1-220">Close the page.</span></span>

