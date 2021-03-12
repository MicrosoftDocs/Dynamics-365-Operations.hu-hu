---
title: Bevételelszámolás újbóli felosztása – 4. eset
description: Ebben a témakörben az újbóli felosztásnak azt az esetét mutatjuk be, amikor egy meglévő, részben kiszámlázott értékesítési rendelésből törölnek egy sort. Nem számít, hogy a sort eltávolítják az értékesítési rendelésből vagy Érvénytelenítve állapotra állítják, az eredmény ugyanaz lesz.
author: kweekley
manager: aolson
ms.date: 12/21/2020
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2020-12-21
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 500c7817795448d7d9759c4ad7a1842df0a9bdc5
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "5003280"
---
# <a name="revenue-recognition-reallocation--scenario-4"></a><span data-ttu-id="42467-104">Bevételelszámolás újbóli felosztása – 4. eset</span><span class="sxs-lookup"><span data-stu-id="42467-104">Revenue recognition reallocation – Scenario 4</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="42467-105">Ebben a témakörben az újbóli felosztásnak azt az esetét mutatjuk be, amikor egy meglévő, részben kiszámlázott értékesítési rendelésből törölnek egy sort.</span><span class="sxs-lookup"><span data-stu-id="42467-105">This topic goes through a reallocation scenario where a line is removed from an existing, partially invoiced sales order.</span></span> <span data-ttu-id="42467-106">Nem számít, hogy a sort eltávolítják az értékesítési rendelésből vagy Érvénytelenítve állapotra állítják, az eredmény ugyanaz lesz.</span><span class="sxs-lookup"><span data-stu-id="42467-106">This scenario produces the same result, regardless of whether the line is removed from the sales order or set to a canceled status.</span></span>

<span data-ttu-id="42467-107">Ennél az esetnél a **Számlajavítások feladása a Kinnlevőségekbe** beállítás a **Nem** értékre van állítva. Ez a beállítás a **Bevételelszámolás** lapon, a **Főkönyvi paraméterek** oldalon található. (**Bevételelszámolás \> Beállítás \> Főkönyvi paraméterek**).</span><span class="sxs-lookup"><span data-stu-id="42467-107">For this scenario, the **Post invoice corrections to Accounts receivable** option is set to **No** on the **Revenue recognition** tab of the **General ledger parameters** page (**Revenue recognition \> Setup \> General ledger parameters**).</span></span>

<span data-ttu-id="42467-108">[![Számlajavítások feladása a Kinnlevőségekbe beállítva a Nem értékre](./media/37_rev-rec-scenarios.png)](./media/37_rev-rec-scenarios.png)</span><span class="sxs-lookup"><span data-stu-id="42467-108">[![Post invoice corrections to Accounts receivable option set to No](./media/37_rev-rec-scenarios.png)](./media/37_rev-rec-scenarios.png)</span></span>

<span data-ttu-id="42467-109">Létrehoznak egy értékesítési rendelt az US\_SI\_0003 nevű vevőhöz.</span><span class="sxs-lookup"><span data-stu-id="42467-109">A sales order is created for customer US\_SI\_0003.</span></span> <span data-ttu-id="42467-110">A vevő vásárol egy laptopot (cikkszám: S0012), telepítési szolgáltatásokat (cikkszám: S0001) és egy támogatási csomagot a laptophoz (cikkszám: S0008, „Sustained Engineering Service” (Folyamatos mérnöki szolgáltatás)).</span><span class="sxs-lookup"><span data-stu-id="42467-110">The customer is purchasing a laptop (item number S0012), installation services (item number S0001), and a support plan for the laptop (item number S0008, "Sustained Engineering Service").</span></span> <span data-ttu-id="42467-111">A laptophoz és a telepítési szolgáltatásokhoz kapcsolódó bevételt azonnal elszámolják.</span><span class="sxs-lookup"><span data-stu-id="42467-111">The revenue for the laptop and installation services is immediately recognized.</span></span> <span data-ttu-id="42467-112">A rendszer a támogatási csomagra vonatkozó bevételt késlelteti, és 12 hónapra lebontva számolja el, a szerződés dátumtartományának megfelelően.</span><span class="sxs-lookup"><span data-stu-id="42467-112">The revenue for the support plan will be deferred and recognized over 12 months, as defined by the date range in the contract.</span></span>

<span data-ttu-id="42467-113">[![Az értékesítési rendelés sorai a laptophoz, a telepítési szolgáltatásokhoz és a támogatási csomaghoz](./media/38_rev-rec-scenarios.png)](./media/38_rev-rec-scenarios.png)</span><span class="sxs-lookup"><span data-stu-id="42467-113">[![Sales order lines for the laptop, installation services, and support plan](./media/38_rev-rec-scenarios.png)](./media/38_rev-rec-scenarios.png)</span></span>

<span data-ttu-id="42467-114">Az értékesítési rendelést visszaigazolják.</span><span class="sxs-lookup"><span data-stu-id="42467-114">The sales order is confirmed.</span></span> <span data-ttu-id="42467-115">Mivel mindhárom cikk esetében be van állítva a bevételi ár felosztása, a rendszer az értékesítési rendelés visszaigazolásakor kiszámítja a bevételi árat.</span><span class="sxs-lookup"><span data-stu-id="42467-115">Because all three items are set up for revenue price allocation, the revenue price is calculated when the sales order is confirmed.</span></span> <span data-ttu-id="42467-116">A **Bevételi ár felosztása** oldalon megtekintheti a rendszer által könyvelt bevételt (a Műveletpanel **Értékesítési rendelés** oldalán, a **Kezelés** lapon, a **Bevételelszámolás** csoportban válassza a **Bevételi ár felosztása** lehetőséget).</span><span class="sxs-lookup"><span data-stu-id="42467-116">You can view the revenue that will be recognized on the **Revenue price allocation** page (on the **Sales order** page, on the Action Pane, on the **Manage** tab, in the **Revenue recognition** group, select **Revenue price allocation**).</span></span> <span data-ttu-id="42467-117">A laptopra vonatkozó 995,84 $ bevételt a rendszer feladja a Bevétel számlára.</span><span class="sxs-lookup"><span data-stu-id="42467-117">The revenue for the laptop will be posted to the Revenue account in the amount of $995.84.</span></span> <span data-ttu-id="42467-118">A telepítési szolgáltatásokra vonatkozó 314,47 $ összegű bevétel a Bevétel számlára kerül.</span><span class="sxs-lookup"><span data-stu-id="42467-118">The revenue for the installation services will also be posted to the Revenue account, in the amount of $314.47.</span></span> <span data-ttu-id="42467-119">A támogatási csomagra vonatkozó 188,69 $ bevételt a rendszer feladja a Halasztott bevétel számlára.</span><span class="sxs-lookup"><span data-stu-id="42467-119">The revenue for the support plan will be posted to a Deferred revenue account in the amount of $188.69.</span></span> <span data-ttu-id="42467-120">A bevételi árak összegének meg kell egyeznie a bevételi ár felosztásának rögzítésére beállított sorok összegével (1499,00 $).</span><span class="sxs-lookup"><span data-stu-id="42467-120">The sum of the revenue prices must equal the sum of the lines that were set up to capture revenue price allocation ($1,499.00).</span></span>

<span data-ttu-id="42467-121">[![Bevételi ár felosztása oldal](./media/39_rev-rec-scenarios.png)](./media/39_rev-rec-scenarios.png)</span><span class="sxs-lookup"><span data-stu-id="42467-121">[![Revenue price allocation page](./media/39_rev-rec-scenarios.png)](./media/39_rev-rec-scenarios.png)</span></span>

<span data-ttu-id="42467-122">A vevőnek kiszámlázzák a laptop és a támogatási csomag díját, de a telepítési szolgáltatásokat nem.</span><span class="sxs-lookup"><span data-stu-id="42467-122">The customer is invoiced for the laptop and support plan, but not for the installation services.</span></span> <span data-ttu-id="42467-123">A következő illusztráción a számlához feladott könyvelési tétel látható.</span><span class="sxs-lookup"><span data-stu-id="42467-123">The following illustration shows the accounting entry that is posted for the invoice.</span></span>

<span data-ttu-id="42467-124">[![A kiszámlázott értékesítési rendelés könyvelési tétele](./media/40_rev-rec-scenarios.png)](./media/40_rev-rec-scenarios.png)</span><span class="sxs-lookup"><span data-stu-id="42467-124">[![Accounting entry for the invoiced sales order](./media/40_rev-rec-scenarios.png)](./media/40_rev-rec-scenarios.png)</span></span>

<span data-ttu-id="42467-125">A könyvelési tétel feladja az 1276,94 $ értéket a kinnlevőségekbe.</span><span class="sxs-lookup"><span data-stu-id="42467-125">The accounting entry posts $1,276.94 to Accounts receivable.</span></span> <span data-ttu-id="42467-126">Mivel azonban ez egy részleges számla, a bevétel/késleltetett bevétel plusz az adó összege nem egyezik a kinnlevőségekben szereplő összeggel.</span><span class="sxs-lookup"><span data-stu-id="42467-126">However, because this invoice is a partial invoice, the revenue or deferred revenue plus the tax doesn't equal the Accounts receivable amount.</span></span> <span data-ttu-id="42467-127">A különbséget (–14,47 $) fel kell adni a Részleges számlabevétel elszámolási számlára.</span><span class="sxs-lookup"><span data-stu-id="42467-127">The difference of -$14.47 is posted to the Partial invoice revenue clearing account.</span></span>

<span data-ttu-id="42467-128">A program a bevételelszámolási ütemezést is létrehozza.</span><span class="sxs-lookup"><span data-stu-id="42467-128">The revenue recognition schedule is also created.</span></span>

<span data-ttu-id="42467-129">[![A részleges számla Bevételelszámolási ütemezés oldala](./media/41_rev-rec-scenarios.png)](./media/41_rev-rec-scenarios.png)</span><span class="sxs-lookup"><span data-stu-id="42467-129">[![Revenue recognition schedule page for the partial invoice](./media/41_rev-rec-scenarios.png)](./media/41_rev-rec-scenarios.png)</span></span>

<span data-ttu-id="42467-130">A vevő később úgy dönt, hogy mégsem vásárolja meg a telepítési szolgáltatásokat.</span><span class="sxs-lookup"><span data-stu-id="42467-130">Later, the customer decides not to purchase installation services.</span></span> <span data-ttu-id="42467-131">Ezért ezt a sort eltávolítják az értékesítési rendelésből.</span><span class="sxs-lookup"><span data-stu-id="42467-131">Therefore, that line is removed from the sales order.</span></span> <span data-ttu-id="42467-132">Ne feledje, hogy az értékesítési rendelést nem lehet ismét megerősíteni, mivel csak a kiszámlázott sorok maradnak meg benne.</span><span class="sxs-lookup"><span data-stu-id="42467-132">Note that the sales order can't be confirmed again, because only invoiced lines remain on the sales order.</span></span>

<span data-ttu-id="42467-133">[![Az értékesítési rendelés a telepítési szolgáltatások sorának eltávolítása után](./media/42_rev-rec-scenarios.png)](./media/42_rev-rec-scenarios.png)</span><span class="sxs-lookup"><span data-stu-id="42467-133">[![Sales order after the line for installation services is removed](./media/42_rev-rec-scenarios.png)](./media/42_rev-rec-scenarios.png)</span></span>

<span data-ttu-id="42467-134">Az értékesítési rendelést nem lehet megerősíteni, de újra fel lehet osztani.</span><span class="sxs-lookup"><span data-stu-id="42467-134">Even though the sales order can't be confirmed, it can be reallocated.</span></span> <span data-ttu-id="42467-135">Az értékesítési rendelésnél válassza az **Ár újbóli felosztása új rendelési sorokba** lehetőséget az **Ár újbóli felosztása új rendelési sorokba** oldal megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="42467-135">In the sales order, select **Reallocate price with new order lines** to open the **Reallocate price with new order lines** page.</span></span> <span data-ttu-id="42467-136">Válassza ki az értékesítési rendelés két fennmaradó sorát, majd válassza az **Újbóli felosztás frissítése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="42467-136">Select the two remaining sales order lines, and then select **Update reallocation**.</span></span> <span data-ttu-id="42467-137">Az **Újból felosztott összeg** oszlopban megjelenik az egyes fennmaradó értékesítésirendelés-sorok új bevételi ára.</span><span class="sxs-lookup"><span data-stu-id="42467-137">The **Reallocated amount** column shows the new revenue price for each remaining sales order line.</span></span>

<span data-ttu-id="42467-138">[![Új bevételi árak az Ár újbóli felosztása új rendelési sorokba oldalon](./media/43_rev-rec-scenarios.png)](./media/43_rev-rec-scenarios.png)</span><span class="sxs-lookup"><span data-stu-id="42467-138">[![New revenue prices on the Reallocate price with new order lines page](./media/43_rev-rec-scenarios.png)](./media/43_rev-rec-scenarios.png)</span></span>

<span data-ttu-id="42467-139">Ezután válassza a **Várható bizonylat** lehetőséget a könyvelési tételek megtekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="42467-139">Next, select **Expected voucher** to view the accounting entries.</span></span>

<span data-ttu-id="42467-140">[![Könyvelési tételek a Várható bizonylat oldalon](./media/44_rev-rec-scenarios.png)](./media/44_rev-rec-scenarios.png)</span><span class="sxs-lookup"><span data-stu-id="42467-140">[![Accounting entries on the Expected voucher page](./media/44_rev-rec-scenarios.png)](./media/44_rev-rec-scenarios.png)</span></span>

<span data-ttu-id="42467-141">A **Várható bizonylat** oldalon az utolsó öt sor sztornírozza a feladott számláról származó eredeti könyvelési tételt.</span><span class="sxs-lookup"><span data-stu-id="42467-141">On the **Expected voucher** page, the last five lines reverse the original accounting entry from the posted invoice.</span></span> <span data-ttu-id="42467-142">Az első négy sorban szerepelnek a számlához feladott új könyvelési tételek.</span><span class="sxs-lookup"><span data-stu-id="42467-142">The first four lines are the new accounting entries that are posted for the invoice.</span></span> <span data-ttu-id="42467-143">Fontos tudni, hogy az új számla nem jelenik meg a vevő számára.</span><span class="sxs-lookup"><span data-stu-id="42467-143">It's important that you understand that a new invoice isn't presented to the customer.</span></span> <span data-ttu-id="42467-144">Az újbóli felosztás után a vevő még további 1276,94 $ összeggel tartozik, ezt az összeget egy új könyvelési tétellel fel kell adni a kinnlevőségekbe.</span><span class="sxs-lookup"><span data-stu-id="42467-144">After the reallocation, the customer still owes $1,276.94, which is the amount that must be posted to Accounts receivable in the new accounting entry.</span></span> <span data-ttu-id="42467-145">Az új bevétel/halasztott bevétel és az adó összege: 1276,96 $.</span><span class="sxs-lookup"><span data-stu-id="42467-145">The new revenue or deferred revenue plus tax equals $1,276.94.</span></span> <span data-ttu-id="42467-146">Így semmit nem kell feladni a Részleges számlabevétel elszámolási számlára.</span><span class="sxs-lookup"><span data-stu-id="42467-146">Therefore, you don't have to post to the Partial invoice revenue clearing account.</span></span>

<span data-ttu-id="42467-147">Az újbóli felosztás befejezéséhez válassza a **Feldolgozás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="42467-147">To complete the reallocation, select **Process**.</span></span> <span data-ttu-id="42467-148">Meg kell adni a feladási dátumot.</span><span class="sxs-lookup"><span data-stu-id="42467-148">A posting date is entered.</span></span> <span data-ttu-id="42467-149">Ha befejeződött az újbóli felosztás, a **Bevételi ár felosztása** oldalon láthatja a két fennmaradó cikk árának újbóli felosztását.</span><span class="sxs-lookup"><span data-stu-id="42467-149">After the reallocation is completed, the **Revenue price allocation** page shows the price reallocation for the two remaining items.</span></span>

<span data-ttu-id="42467-150">[![Az ár újbóli felosztása a fennmaradó cikkek esetében a Bevételi ár felosztása oldalon](./media/45_rev-rec-scenarios.png)](./media/45_rev-rec-scenarios.png)</span><span class="sxs-lookup"><span data-stu-id="42467-150">[![Price reallocation for the remaining items on the Revenue price allocation page](./media/45_rev-rec-scenarios.png)](./media/45_rev-rec-scenarios.png)</span></span>

<span data-ttu-id="42467-151">A bevételelszámolási ütemezés az új bevétel újrafelosztási ára alapján frissült.</span><span class="sxs-lookup"><span data-stu-id="42467-151">The revenue recognition schedule was also updated, based on the new revenue reallocation price.</span></span> <span data-ttu-id="42467-152">Az értékesítési rendelésből nyissa meg a **Bevételelszámolási ütemezés** oldalt.</span><span class="sxs-lookup"><span data-stu-id="42467-152">From the sales order, open the **Revenue recognition schedule** page.</span></span> <span data-ttu-id="42467-153">Korábban 13 sor tartozott az S0008-as cikkhez (ehhez a cikkhez 12 hónapos ütemezést adtak meg).</span><span class="sxs-lookup"><span data-stu-id="42467-153">Previously, there were 13 lines for item S0008 (a 12-month schedule was assigned to this item).</span></span> <span data-ttu-id="42467-154">Jelenleg 39 sor van: az eredeti ütemezés 13 sora, 13 sztornírozott ütemezési sor, valamint az új bevételi áron alapuló 13 sor.</span><span class="sxs-lookup"><span data-stu-id="42467-154">There are now 39 lines: the 13 original schedule lines, 13 reversal schedule lines, and 13 lines that are based on the new revenue price.</span></span>

<span data-ttu-id="42467-155">[![A Bevételelszámolási ütemezés frissített oldala 39 sorral az S0008 cikkhez](./media/46_rev-rec-scenarios.png)](./media/46_rev-rec-scenarios.png)</span><span class="sxs-lookup"><span data-stu-id="42467-155">[![Updated Revenue recognition schedule page with 39 lines for item S0008](./media/46_rev-rec-scenarios.png)](./media/46_rev-rec-scenarios.png)</span></span>

<span data-ttu-id="42467-156">Ha a **Bizonylat** lehetőséget választja, a számlanapló az eredeti könyvelési tételt jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="42467-156">When you select **Voucher**, the invoice journal shows the original accounting entry.</span></span> <span data-ttu-id="42467-157">A sztornírozó tétel és az értékesítési rendelésből származó új könyvelési tétel megtekintéséhez válassza a **Bevételkiigazítások** lehetőséget a Műveletpanelen, majd válassza a **Bizonylat** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="42467-157">To view the reversing entry and the new accounting entry from the sales order, select **Revenue adjustments** on the Action Pane, and then select **Voucher**.</span></span>

<span data-ttu-id="42467-158">Ezután nyissa meg az **Összes vevő** oldalt (**Kinnlevőségek \> Vevők \> Összes vevő**), válassza ki az **US\_SI\_0003** vevőt, majd válassza a **Tranzakciók** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="42467-158">Next, open the **All customers** page (**Accounts receivable \> Customers \> All customers**), select customer **US\_SI\_0003**, and then select **Transactions**.</span></span> <span data-ttu-id="42467-159">A **Vevői tranzakciók** oldalon csak az eredeti számla (000008) és az eredeti könyvelési tétel szerepel.</span><span class="sxs-lookup"><span data-stu-id="42467-159">The **Customer transactions** page shows only the original invoice (000008), together with the original accounting entry.</span></span> <span data-ttu-id="42467-160">Mivel a **Számlajavítások feladása a Kinnlevőségekbe** lehetőség a **Nem** értékre van állítva a **Főkönyvi paraméterek** oldalon, csak a főkönyv frissül.</span><span class="sxs-lookup"><span data-stu-id="42467-160">Because the **Post invoice corrections to Accounts receivable** option is set to **No** on the **General ledger parameters** page, only General ledger is updated.</span></span> <span data-ttu-id="42467-161">Ezért nem jelennek meg a sztornírozó és a frissített könyvelési tételek.</span><span class="sxs-lookup"><span data-stu-id="42467-161">Therefore, the reversing and updated accounting entries aren't shown.</span></span> <span data-ttu-id="42467-162">Figyelje meg, hogy megjelennek a [3. esetnél](rev-rec-reallocation-scenario-3.md) létrehozott bevételkorrekciós tranzakciók.</span><span class="sxs-lookup"><span data-stu-id="42467-162">Note that the revenue adjustment transactions that were created in [scenario 3](rev-rec-reallocation-scenario-3.md) are shown.</span></span>

<span data-ttu-id="42467-163">[![Az eredeti könyvelési tétel a Vevői tranzakciók oldalon](./media/47_rev-rec-scenarios.png)](./media/47_rev-rec-scenarios.png)</span><span class="sxs-lookup"><span data-stu-id="42467-163">[![Original accounting entry on the Customer transactions page](./media/47_rev-rec-scenarios.png)](./media/47_rev-rec-scenarios.png)</span></span>