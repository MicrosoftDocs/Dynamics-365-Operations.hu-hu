---
title: Bevételelszámolás újbóli felosztása – 1. eset
description: Ebben a témakörben az újbóli felosztásnak azt az esetét mutatjuk be, amelyben két értékesítési rendelést adnak meg, de ezeket csak visszaigazolják. Ugyanez a forgatókönyv hasonló eredményekkel jár, ha kettőnél több értékesítési rendelés van visszaigazolt állapotban.
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
ms.openlocfilehash: 2a0add2d4bc01127c1f359736398123a6a3df9fe
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4969652"
---
# <a name="revenue-recognition-reallocation--scenario-1"></a><span data-ttu-id="90a7d-104">Bevételelszámolás újbóli felosztása – 1. eset</span><span class="sxs-lookup"><span data-stu-id="90a7d-104">Revenue recognition reallocation – Scenario 1</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="90a7d-105">Ebben a témakörben az újbóli felosztásnak azt az esetét mutatjuk be, amelyben két értékesítési rendelést adnak meg, de ezeket csak visszaigazolják.</span><span class="sxs-lookup"><span data-stu-id="90a7d-105">This topic goes through a reallocation scenario where two sales orders are entered, but they are only confirmed.</span></span> <span data-ttu-id="90a7d-106">Ugyanez a forgatókönyv hasonló eredményekkel jár, ha kettőnél több értékesítési rendelés van visszaigazolt állapotban.</span><span class="sxs-lookup"><span data-stu-id="90a7d-106">The same scenario will produce similar results if more than two sales orders are in a confirmed state.</span></span>

<span data-ttu-id="90a7d-107">Ennél az esetnél a **Számlajavítások feladása a Kinnlevőségekbe** beállítás a **Nem** értékre van állítva. Ez a beállítás a **Bevételelszámolás** lapon, a **Főkönyvi paraméterek** oldalon található. (**Bevételelszámolás \> Beállítás \> Főkönyvi paraméterek**).</span><span class="sxs-lookup"><span data-stu-id="90a7d-107">For this scenario, the **Post invoice corrections to Accounts receivable** option is set to **No** on the **Revenue recognition** tab of the **General ledger parameters** page (**Revenue recognition \> Setup \> General ledger parameters**).</span></span>

<span data-ttu-id="90a7d-108">[![Számlajavítások feladása a Kinnlevőségekbe beállítva a Nem értékre](./media/06_rev-rec-scenarios.png)](./media/06_rev-rec-scenarios.png)</span><span class="sxs-lookup"><span data-stu-id="90a7d-108">[![Post invoice corrections to Accounts receivable option set to No](./media/06_rev-rec-scenarios.png)](./media/06_rev-rec-scenarios.png)</span></span>

<span data-ttu-id="90a7d-109">Létrehoznak egy értékesítési rendelt az US\_SI\_0003 nevű vevőhöz.</span><span class="sxs-lookup"><span data-stu-id="90a7d-109">A sales order is created for customer US\_SI\_0003.</span></span> <span data-ttu-id="90a7d-110">A vevő vásárol egy laptopot (cikkszám: S0012) és hozzá egy támogatási csomagot (cikkszám: S0008, „Sustained Engineering Service” (Folyamatos mérnöki szolgáltatás)).</span><span class="sxs-lookup"><span data-stu-id="90a7d-110">The customer is purchasing a laptop (item number S0012) and a support plan for it (item number S0008, "Sustained Engineering Service").</span></span> <span data-ttu-id="90a7d-111">A rendszer azonnal felismeri a laptophoz tartozó bevételt (nincs bevételelszámolási ütemezés).</span><span class="sxs-lookup"><span data-stu-id="90a7d-111">The revenue for the laptop is immediately recognized (there is no revenue recognition schedule).</span></span> <span data-ttu-id="90a7d-112">A rendszer a támogatási csomagra vonatkozó bevételt késlelteti, és 12 hónapra lebontva számolja el, a szerződés dátumtartományának megfelelően.</span><span class="sxs-lookup"><span data-stu-id="90a7d-112">The revenue for the support plan will be deferred and recognized over 12 months, as defined by the date range in the contract.</span></span>

<span data-ttu-id="90a7d-113">[![Az értékesítési rendelés sorai a laptophoz és a támogatási csomaghoz](./media/07_rev-rec-scenarios.png)](./media/07_rev-rec-scenarios.png)</span><span class="sxs-lookup"><span data-stu-id="90a7d-113">[![Sales order lines for the laptop and support plan](./media/07_rev-rec-scenarios.png)](./media/07_rev-rec-scenarios.png)</span></span>

<span data-ttu-id="90a7d-114">Az értékesítési rendelést visszaigazolják.</span><span class="sxs-lookup"><span data-stu-id="90a7d-114">The sales order is confirmed.</span></span> <span data-ttu-id="90a7d-115">Mivel mindkét cikk esetében be van állítva a bevételi ár felosztása, a rendszer az értékesítési rendelés visszaigazolásakor kiszámítja a bevételi árat.</span><span class="sxs-lookup"><span data-stu-id="90a7d-115">Because both items are set up for revenue price allocation, the revenue price is calculated when the sales order is confirmed.</span></span> <span data-ttu-id="90a7d-116">A **Bevételi ár felosztása** oldalon megtekintheti a rendszer által könyvelt bevételt (a Műveletpanel **Értékesítési rendelés** oldalán, a **Kezelés** lapon, a **Bevételelszámolás** csoportban válassza a **Bevételi ár felosztása** lehetőséget).</span><span class="sxs-lookup"><span data-stu-id="90a7d-116">You can view the revenue that will be recognized on the **Revenue price allocation** page (on the **Sales order** page, on the Action Pane, on the **Manage** tab, in the **Revenue recognition** group, select **Revenue price allocation**).</span></span> <span data-ttu-id="90a7d-117">A laptopra vonatkozó 1008,01 $ bevételt a rendszer feladja a Bevétel számlára.</span><span class="sxs-lookup"><span data-stu-id="90a7d-117">The revenue for the laptop will be posted to the Revenue account in the amount of $1,008.01.</span></span> <span data-ttu-id="90a7d-118">A támogatási csomagra vonatkozó 190,99 $ bevételt a rendszer feladja a Halasztott bevétel számlára.</span><span class="sxs-lookup"><span data-stu-id="90a7d-118">The revenue for the support plan will be posted to the Deferred revenue account in the amount of $190.99.</span></span> <span data-ttu-id="90a7d-119">A bevételi árak összegének meg kell egyeznie a bevételi ár felosztásának rögzítésére beállított sorok összegével (1199,00 $).</span><span class="sxs-lookup"><span data-stu-id="90a7d-119">The sum of the revenue prices must equal the sum of the lines that were set up to capture revenue price allocation ($1,199.00).</span></span>

<span data-ttu-id="90a7d-120">[![Bevételi ár felosztása oldal](./media/08_rev-rec-scenarios.png)](./media/08_rev-rec-scenarios.png)</span><span class="sxs-lookup"><span data-stu-id="90a7d-120">[![Revenue price allocation page](./media/08_rev-rec-scenarios.png)](./media/08_rev-rec-scenarios.png)</span></span>

<span data-ttu-id="90a7d-121">A vevő úgy döntött, hogy a vásárlás időpontjában nem vásárol telepítési szolgáltatásokat (cikkszám: S0001), de később meggondolta magát.</span><span class="sxs-lookup"><span data-stu-id="90a7d-121">The customer chose not to purchase installation services (item number S0001) at the time of the sale but later changed their mind.</span></span> <span data-ttu-id="90a7d-122">Ezért ugyanehhez a vevőhöz egy második értékesítési rendelés is létrejön.</span><span class="sxs-lookup"><span data-stu-id="90a7d-122">Therefore, a second sales order is entered for the same customer.</span></span>

<span data-ttu-id="90a7d-123">[![Az értékesítési rendelés sora a telepítési szolgáltatásokhoz](./media/09_rev-rec-scenarios.png)](./media/09_rev-rec-scenarios.png)</span><span class="sxs-lookup"><span data-stu-id="90a7d-123">[![Sales order line for installation services](./media/09_rev-rec-scenarios.png)](./media/09_rev-rec-scenarios.png)</span></span>

<span data-ttu-id="90a7d-124">A második értékesítési rendelést is visszaigazolják.</span><span class="sxs-lookup"><span data-stu-id="90a7d-124">The second sales order is confirmed.</span></span> <span data-ttu-id="90a7d-125">Mivel ez az értékesítési rendelés csak egy sort tartalmaz, az értékesítési rendelés visszaigazolásakor nem kerül sor a bevételi ár felosztására.</span><span class="sxs-lookup"><span data-stu-id="90a7d-125">Because this sales order contains only one line, revenue price allocation isn't done when the sales order is confirmed.</span></span> <span data-ttu-id="90a7d-126">A rendszer csak akkor végzi el a bevételi ár felosztását, ha két vagy több egyedi tételről van szó, és ha ezeknél a tételeknél be van állítva a bevételi ár felosztása.</span><span class="sxs-lookup"><span data-stu-id="90a7d-126">Revenue price allocation occurs only if there are two or more unique items, and if those items are set up for revenue price allocation.</span></span>

<span data-ttu-id="90a7d-127">Ha ez az új értékesítési rendelés a vevő szerződését érintő egyetlen módosítás, most már le lehet futtatni az újbóli felosztás folyamatát.</span><span class="sxs-lookup"><span data-stu-id="90a7d-127">If this new sales order is the only change to the customer's contract, the reallocation process can now be run.</span></span> <span data-ttu-id="90a7d-128">A két értékesítési rendelés egyikében válassza az **Ár újbóli felosztása új rendelési sorokba** lehetőséget az **Ár újbóli felosztása új rendelési sorokba** oldal megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="90a7d-128">In one of the two sales orders, select **Reallocate price with new order lines** to open the **Reallocate price with new order lines** page.</span></span> <span data-ttu-id="90a7d-129">Másik lehetőségként lépjen a **Bevételelszámolás \> Időszakos feladatok \>Ár újbóli felosztása új rendelési sorokba** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="90a7d-129">Alternatively, go to **Revenue recognition \> Periodic tasks \> Reallocate price with new order lines**.</span></span> <span data-ttu-id="90a7d-130">Válassza ki a két értékesítési rendelést és a megfelelő értékesítésirendelés-sorokat, majd válassza az **Újbóli felosztás frissítése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="90a7d-130">Select the two sales orders and the corresponding sales order lines, and then select **Update reallocation**.</span></span> <span data-ttu-id="90a7d-131">Az **Újból felosztott összeg** oszlopban megjelenik az egyes értékesítésirendelés-sorok új bevételi ára.</span><span class="sxs-lookup"><span data-stu-id="90a7d-131">The **Reallocated amount** column shows the new revenue price for each sales order line.</span></span>

<span data-ttu-id="90a7d-132">[![Új bevételi árak az Ár újbóli felosztása új rendelési sorokba oldalon](./media/10_rev-rec-scenarios.png)](./media/10_rev-rec-scenarios.png)</span><span class="sxs-lookup"><span data-stu-id="90a7d-132">[![New revenue prices on the Reallocate price with new order lines page](./media/10_rev-rec-scenarios.png)](./media/10_rev-rec-scenarios.png)</span></span>

<span data-ttu-id="90a7d-133">Ha a **Várható bizonylat** lehetőséget választja, semmi nem jelenik meg, mivel egyetlen számlát sem adtak fel.</span><span class="sxs-lookup"><span data-stu-id="90a7d-133">If you select **Expected voucher**, nothing is shown, because no invoices have been posted.</span></span>

<span data-ttu-id="90a7d-134">Az újbóli felosztás befejezéséhez válassza a **Feldolgozás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="90a7d-134">To complete the reallocation, select **Process**.</span></span> <span data-ttu-id="90a7d-135">A program kéri, hogy adja meg a feladás dátumát, akkor is, ha nem adott fel semmit.</span><span class="sxs-lookup"><span data-stu-id="90a7d-135">You're prompted for a posting date, even if nothing is posted.</span></span> <span data-ttu-id="90a7d-136">Az újbóli felosztás befejezése után az egyes értékesítési rendelések **Bevételi ár felosztása** oldalán megjelenik a két értékesítési rendelés összes tételére vonatkozó felosztás.</span><span class="sxs-lookup"><span data-stu-id="90a7d-136">After the reallocation is completed, the **Revenue price allocation** page for each sales order will show the price allocation for all items across both sales orders.</span></span> <span data-ttu-id="90a7d-137">Más szóval minden értékesítési rendelés **Bevételi ár felosztása** oldalán szerepelni fog egy cikk, amely nem létezik az adott értékesítési rendelésben, mert ez ugyanannak a szerződésnek a része, de egy másik értékesítési rendeléshez tartozik.</span><span class="sxs-lookup"><span data-stu-id="90a7d-137">In other words, the **Revenue price allocation** page for each sales order will include an item that doesn't exist on that sales order, because it's part of the same contract but on a different sales order.</span></span>

> [!TIP]
> <span data-ttu-id="90a7d-138">Ha szeretne magyarázatot arról, hogy miért jelennek meg itt ezek a cikkek, további oszlopokat adhat a rácshoz, például: **Újrafelosztási azonosító** és **Értékesítési rendelés**.</span><span class="sxs-lookup"><span data-stu-id="90a7d-138">To provide context about why these additional items are shown, you can add other columns to the grid, such as **Reallocation ID** and **Sales order**.</span></span>
> 
> <span data-ttu-id="90a7d-139">[![További oszlopok a Bevételi ár felosztása oldalon](./media/11_rev-rec-scenarios.png)](./media/11_rev-rec-scenarios.png)</span><span class="sxs-lookup"><span data-stu-id="90a7d-139">[![Additional columns on the Revenue price allocations page](./media/11_rev-rec-scenarios.png)](./media/11_rev-rec-scenarios.png)</span></span>