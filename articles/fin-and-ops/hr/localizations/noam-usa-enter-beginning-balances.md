---
title: "Adja meg a bérlista nyitó egyenlegeit"
description: "A témakör a nyitó egyenlegek bevitelének lépéseit ismerteti a kereseti kódok, levonások, juttatások és adók esetében. Ez az információ értékes a partnerek számára az adatok áttelepítéséhez vagy átviteléhez egy új Bérlista rendszerbe egy másik rendszerből."
author: kherr75
manager: AnnBe
ms.date: 07/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 20931
ms.assetid: b48b1cb2-6e66-467e-9c0e-09b6a4aeb9fe
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2017-07-01
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 736eedf270ac08b0bdf9364821f8a7bae981ade9
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="enter-payroll-beginning-balances"></a><span data-ttu-id="0cd81-104">Adja meg a bérlista nyitó egyenlegeit</span><span class="sxs-lookup"><span data-stu-id="0cd81-104">Enter payroll beginning balances</span></span>

[!include[banner](../../includes/banner.md)]

<span data-ttu-id="0cd81-105">A témakör a nyitó egyenlegek bevitelének lépéseit ismerteti a kereseti kódok, levonások, juttatások és adók esetében.</span><span class="sxs-lookup"><span data-stu-id="0cd81-105">The topic describes the steps for entering beginning balances for earning codes, deductions, benefits, and taxes.</span></span> <span data-ttu-id="0cd81-106">Ez az információ értékes az olyan partnerek számára, akik adatokat telepítenek át vagy visznek át egy új Bérlista rendszerbe egy másik rendszerből.</span><span class="sxs-lookup"><span data-stu-id="0cd81-106">This information is valuable for partners who transfer data for a new Payroll implementation from another system.</span></span> <span data-ttu-id="0cd81-107">A nyitó bérlistaegyenlegek bevitelének előkészítéseként ellenőrizzük az alábbi információkat:</span><span class="sxs-lookup"><span data-stu-id="0cd81-107">To prepare to enter beginning payroll balances, we verify the following information:</span></span>

> * <span data-ttu-id="0cd81-108">Az alkalmazotti rekordok meg vannak adva és elérhetők a rendszerben</span><span class="sxs-lookup"><span data-stu-id="0cd81-108">Employee records are entered and available in the system</span></span>
> * <span data-ttu-id="0cd81-109">Az alábbi adatok be vannak állítva és hozzá vannak rendelve az alkalmazottakhoz:</span><span class="sxs-lookup"><span data-stu-id="0cd81-109">The following data is set up and assigned to employees:</span></span>

> > * <span data-ttu-id="0cd81-110">Fizetési ciklusok és fizetési időszakok</span><span class="sxs-lookup"><span data-stu-id="0cd81-110">Pay cycles and pay periods</span></span>
> > * <span data-ttu-id="0cd81-111">Bevételkódok</span><span class="sxs-lookup"><span data-stu-id="0cd81-111">Earning codes</span></span>
> > * <span data-ttu-id="0cd81-112">Adók</span><span class="sxs-lookup"><span data-stu-id="0cd81-112">Taxes</span></span>
> > * <span data-ttu-id="0cd81-113">Juttatások és levonások</span><span class="sxs-lookup"><span data-stu-id="0cd81-113">Benefits and deductions</span></span>

> * <span data-ttu-id="0cd81-114">A vállalatnak ki kellett volna választania egy dátumot, amelyen megadhatók a nyitó bérlistaegyenlegek.</span><span class="sxs-lookup"><span data-stu-id="0cd81-114">The company should have chosen a date where payroll beginning balances can be set.</span></span>

> * <span data-ttu-id="0cd81-115">A korábbi rendszerből összegyűjtött adatok minden bevételről, juttatásról és levonásról, juttatások hozzájárulásairól, alkalmazott által fizetendő adóról, munkáltatói adóról és ezek folyó évi összegeiről.</span><span class="sxs-lookup"><span data-stu-id="0cd81-115">Information were gathered on all earnings, benefits/deductions, benefit contributions, employee taxes, and employer taxes and their YTD amounts from the legacy system.</span></span>

<span data-ttu-id="0cd81-116">A nyitó egyenleg bevitelének tervezésekor fontolja meg, hogy mennyire kell részletesnek lenniük az adatoknak.</span><span class="sxs-lookup"><span data-stu-id="0cd81-116">As you plan to enter beginning balances, consider how detailed the data needs to be.</span></span> <span data-ttu-id="0cd81-117">A vállalkozások többsége egyetlen, összevont, a folyó évben az adott dátumig számolt összeget ad meg.</span><span class="sxs-lookup"><span data-stu-id="0cd81-117">Most businesses enter a single, consolidated year-to-date amount.</span></span> <span data-ttu-id="0cd81-118">Ha azonban részletesebb információkra van szükség, az egyenlegek negyedéves lépésekben is bevihetők.</span><span class="sxs-lookup"><span data-stu-id="0cd81-118">However if more detailed information is needed, balances can be entered in quarterly increments.</span></span> <span data-ttu-id="0cd81-119">A szükséges részletességi szinttel kapcsolatos döntés határozza meg, hogy hány manuális fizetési kimutatást kell létrehozni minden dolgozóhoz.</span><span class="sxs-lookup"><span data-stu-id="0cd81-119">Deciding the level of detail that's needed determines how many manual pay statements must be created for each worker.</span></span> <span data-ttu-id="0cd81-120">Csak egy manuális kimutatásra van szükség minden egyes alkalmazott esetében, ha egyetlen év az aktuális dátumig összeget visznek be.</span><span class="sxs-lookup"><span data-stu-id="0cd81-120">For a single year-to-date amount, only one manual statement is needed for each employee.</span></span> <span data-ttu-id="0cd81-121">Ehhez a korábbi rendszerből származó végső fizetési kimutatás év az aktuális dátumig összegeit kell bevinni az új bérszámfejtő rendszerbe.</span><span class="sxs-lookup"><span data-stu-id="0cd81-121">To do this use year-to-date amounts from the final pay statement from the previous system as the amount entered in the new payroll system.</span></span>

<span data-ttu-id="0cd81-122">A következő példa bemutatja, hogyan lehet bevinni az alkalmazotti bérlista-nyitóegyenlegeket, beleértve a kereseti kódokat, a juttatásokat és levonásokat, valamint az adókat.</span><span class="sxs-lookup"><span data-stu-id="0cd81-122">The following example shows how you can enter employee payroll beginning balances, including earning codes, benefits/deductions, and taxes.</span></span> <span data-ttu-id="0cd81-123">Egy való életből vett példában minden egyes bevitt kereseti kódról, juttatás levonásairól, juttatás hozzájárulásairól, alkalmazott által fizetendő adóról és munkáltatói adóról lenne egy sortétel az év az aktuális dátumig összeggel.</span><span class="sxs-lookup"><span data-stu-id="0cd81-123">In a real-world example you would have a line item for each earning code, benefit deduction, benefit contribution, employee tax and employer tax with the amount entered being the year-to-date amount.</span></span> <span data-ttu-id="0cd81-124">Használja a kódok és az összegek listáját, és kövesse a kereseti és kifizetési kimutatás manuális létrehozásának lépéseit kikapcsolt könyvelés mellett a nyitó egyenlegek bérszámfejtés céljára való átviteléhez.</span><span class="sxs-lookup"><span data-stu-id="0cd81-124">Using that list of codes and amounts, follow the steps for creating a manual earning and pay statement with accounting disabled to bring over beginning balances for payroll purposes.</span></span>  <span data-ttu-id="0cd81-125">A könyvelést le kell tiltani, mivel nem szeretnénk feladni a főkönyvbe a nyitó egyenleg fizetési kimutatását.</span><span class="sxs-lookup"><span data-stu-id="0cd81-125">You disable accounting because you won't want to post this beginning balance pay statement to your general ledger.</span></span> <span data-ttu-id="0cd81-126">Ez a korábbi rendszerben készült, és az új rendszerbe a nyitó egyenlegeknek a főkönyvben való beállításakor kerül át.</span><span class="sxs-lookup"><span data-stu-id="0cd81-126">That was done in the legacy system and will come over to the new system when you set beginning balances in General ledger.</span></span>

### <a name="a-how-to-set-up-earnings-codes-to-be-used-on-payroll-beginning-balances"></a><span data-ttu-id="0cd81-127">A.</span><span class="sxs-lookup"><span data-stu-id="0cd81-127">A.</span></span> <span data-ttu-id="0cd81-128">Hogyan kell beállítani a bevételkódokat nyitó bérlista egyenlegekhez való használathoz</span><span class="sxs-lookup"><span data-stu-id="0cd81-128">How to set up earnings codes to be used on payroll beginning balances</span></span>
<span data-ttu-id="0cd81-129">Amikor megadja a nyitó bérlistaegyenlegeket, győződjön meg arról, hogy a használni kívánt bevételkódok a „Kereseti kimutatási mértékek szerkesztésének engedélyezése” beállítás engedélyezésével vannak konfigurálva.</span><span class="sxs-lookup"><span data-stu-id="0cd81-129">When you enter payroll beginning balances, be sure the earning codes that you will be using are configured with the "Allow editing of earning statement rates" option enabled.</span></span> <span data-ttu-id="0cd81-130">Ez lehetővé teszi, hogy manuálisan írja be az összeget a korábbi rendszerből.</span><span class="sxs-lookup"><span data-stu-id="0cd81-130">This will allow you to manually key the amount from the legacy system.</span></span> 

### <a name="b-create-earnings-statement-for-an-employee-to-have-a-beginning-balance"></a><span data-ttu-id="0cd81-131">B.</span><span class="sxs-lookup"><span data-stu-id="0cd81-131">B.</span></span> <span data-ttu-id="0cd81-132">Kereseti kimutatás létrehozása az alkalmazotthoz a nyitó egyenleg létrehozásához</span><span class="sxs-lookup"><span data-stu-id="0cd81-132">Create earnings statement for an employee to have a beginning balance</span></span>
<span data-ttu-id="0cd81-133">Ez a lépés manuálisan hoz létre kereseti kimutatást minden dolgozóhoz a korábbi rendszer utolsó fizetési időszakához, ami létrehozza a kereseti kimutatási sorokat az új bérszámfejtő rendszerben.</span><span class="sxs-lookup"><span data-stu-id="0cd81-133">This step manually creates an earnings statement for each worker for the last pay period of the legacy system, which creates the earning statement lines in the new payroll system.</span></span> <span data-ttu-id="0cd81-134">Adjon meg egy sort bevételkódonként, valamint a folyó évi összeget és órákat.</span><span class="sxs-lookup"><span data-stu-id="0cd81-134">Enter one line per earning code and the YTD amount and hours.</span></span> <span data-ttu-id="0cd81-135">A minta lépések a következők:</span><span class="sxs-lookup"><span data-stu-id="0cd81-135">The sample steps are as follows:</span></span>

1. <span data-ttu-id="0cd81-136">Nyissa meg az **Összes kereseti kimutatás** lapot, és kattintson az **Új** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="0cd81-136">Open the **All earnings statements** page and click **New**.</span></span>  

<span data-ttu-id="0cd81-137">Adja meg a következő adatokat:</span><span class="sxs-lookup"><span data-stu-id="0cd81-137">Enter the following:</span></span> 

| <span data-ttu-id="0cd81-138">Mező</span><span class="sxs-lookup"><span data-stu-id="0cd81-138">Field</span></span>      | <span data-ttu-id="0cd81-139">Érték</span><span class="sxs-lookup"><span data-stu-id="0cd81-139">Value</span></span>                 |
|------------|-----------------------|
| <span data-ttu-id="0cd81-140">Dolgozó</span><span class="sxs-lookup"><span data-stu-id="0cd81-140">Worker</span></span>     | <span data-ttu-id="0cd81-141">Michael Redmond</span><span class="sxs-lookup"><span data-stu-id="0cd81-141">Michael Redmond</span></span>       |
| <span data-ttu-id="0cd81-142">Fizetési ciklus</span><span class="sxs-lookup"><span data-stu-id="0cd81-142">Pay cycle</span></span>  | <span data-ttu-id="0cd81-143">sm</span><span class="sxs-lookup"><span data-stu-id="0cd81-143">sm</span></span>                    |
| <span data-ttu-id="0cd81-144">Fizetési időszak</span><span class="sxs-lookup"><span data-stu-id="0cd81-144">Pay period</span></span> | <span data-ttu-id="0cd81-145">2017/06/16 - 2017/6/30</span><span class="sxs-lookup"><span data-stu-id="0cd81-145">6/16/2017 - 6/30/2017</span></span> |

2. <span data-ttu-id="0cd81-146">A **Kereseti kimutatás sorai** lapon írja be a következőket:</span><span class="sxs-lookup"><span data-stu-id="0cd81-146">In the **Earnings statement line** tab, enter the following:</span></span>

<span data-ttu-id="0cd81-147">1. sor: **Kereseti kimutatás sorai** lap</span><span class="sxs-lookup"><span data-stu-id="0cd81-147">Line 1: **Earning statement line** tab</span></span>

| <span data-ttu-id="0cd81-148">Mező</span><span class="sxs-lookup"><span data-stu-id="0cd81-148">Field</span></span>            | <span data-ttu-id="0cd81-149">Érték</span><span class="sxs-lookup"><span data-stu-id="0cd81-149">Value</span></span>       |
|------------------|-------------|
| <span data-ttu-id="0cd81-150">Bevételkód</span><span class="sxs-lookup"><span data-stu-id="0cd81-150">Earnings code</span></span>    | <span data-ttu-id="0cd81-151">Rendszeres fizetés</span><span class="sxs-lookup"><span data-stu-id="0cd81-151">Regular pay</span></span> |
| <span data-ttu-id="0cd81-152">Mennyiség</span><span class="sxs-lookup"><span data-stu-id="0cd81-152">Quantity</span></span>         | <span data-ttu-id="0cd81-153">1.00</span><span class="sxs-lookup"><span data-stu-id="0cd81-153">1.00</span></span>        |
| <span data-ttu-id="0cd81-154">Árfolyam</span><span class="sxs-lookup"><span data-stu-id="0cd81-154">Rage</span></span>             | <span data-ttu-id="0cd81-155">30 000</span><span class="sxs-lookup"><span data-stu-id="0cd81-155">30,000</span></span>      |
| <span data-ttu-id="0cd81-156">Sor részletei lap</span><span class="sxs-lookup"><span data-stu-id="0cd81-156">Line details tab</span></span> |             |
| <span data-ttu-id="0cd81-157">Manuális</span><span class="sxs-lookup"><span data-stu-id="0cd81-157">Manual</span></span>           | <span data-ttu-id="0cd81-158">(megjelölve)</span><span class="sxs-lookup"><span data-stu-id="0cd81-158">(marked)</span></span>    |

<span data-ttu-id="0cd81-159">2. sor: **Kereseti kimutatás sorai** lap</span><span class="sxs-lookup"><span data-stu-id="0cd81-159">Line 2: **Earning statement line** tab</span></span>

| <span data-ttu-id="0cd81-160">Mező</span><span class="sxs-lookup"><span data-stu-id="0cd81-160">Field</span></span>            | <span data-ttu-id="0cd81-161">Érték</span><span class="sxs-lookup"><span data-stu-id="0cd81-161">Value</span></span>    |
|------------------|----------|
| <span data-ttu-id="0cd81-162">Bevételkód</span><span class="sxs-lookup"><span data-stu-id="0cd81-162">Earnings code</span></span>    | <span data-ttu-id="0cd81-163">Jutalom</span><span class="sxs-lookup"><span data-stu-id="0cd81-163">Bonus</span></span>    |
| <span data-ttu-id="0cd81-164">Mennyiség</span><span class="sxs-lookup"><span data-stu-id="0cd81-164">Quantity</span></span>         | <span data-ttu-id="0cd81-165">1.0000</span><span class="sxs-lookup"><span data-stu-id="0cd81-165">1.0000</span></span>   |
| <span data-ttu-id="0cd81-166">Árfolyam</span><span class="sxs-lookup"><span data-stu-id="0cd81-166">Rate</span></span>             | <span data-ttu-id="0cd81-167">4250.00</span><span class="sxs-lookup"><span data-stu-id="0cd81-167">4250.00</span></span>  |
| <span data-ttu-id="0cd81-168">Sor részletei lap</span><span class="sxs-lookup"><span data-stu-id="0cd81-168">Line details tab</span></span> |          |
| <span data-ttu-id="0cd81-169">Manuális</span><span class="sxs-lookup"><span data-stu-id="0cd81-169">Manual</span></span>           | <span data-ttu-id="0cd81-170">(megjelölve)</span><span class="sxs-lookup"><span data-stu-id="0cd81-170">(marked)</span></span> |

<span data-ttu-id="0cd81-171">3. sor: **Kereseti kimutatás sorai** lap</span><span class="sxs-lookup"><span data-stu-id="0cd81-171">Line 3: **Earning statement line** tab</span></span>

| <span data-ttu-id="0cd81-172">Mező</span><span class="sxs-lookup"><span data-stu-id="0cd81-172">Field</span></span>           | <span data-ttu-id="0cd81-173">Érték</span><span class="sxs-lookup"><span data-stu-id="0cd81-173">Value</span></span>      |
|-----------------|------------|
| <span data-ttu-id="0cd81-174">Bevételkód</span><span class="sxs-lookup"><span data-stu-id="0cd81-174">Earnings code</span></span>   | <span data-ttu-id="0cd81-175">Jutalék</span><span class="sxs-lookup"><span data-stu-id="0cd81-175">Commission</span></span> |
| <span data-ttu-id="0cd81-176">Mennyiség</span><span class="sxs-lookup"><span data-stu-id="0cd81-176">Quantity</span></span>        | <span data-ttu-id="0cd81-177">1.0000</span><span class="sxs-lookup"><span data-stu-id="0cd81-177">1.0000</span></span>     |
| <span data-ttu-id="0cd81-178">Árfolyam</span><span class="sxs-lookup"><span data-stu-id="0cd81-178">Rate</span></span>            | <span data-ttu-id="0cd81-179">!,299.00</span><span class="sxs-lookup"><span data-stu-id="0cd81-179">!,299.00</span></span>   |
| <span data-ttu-id="0cd81-180">Árfolyam</span><span class="sxs-lookup"><span data-stu-id="0cd81-180">Rate</span></span>            | <span data-ttu-id="0cd81-181">1,299.00</span><span class="sxs-lookup"><span data-stu-id="0cd81-181">1,299.00</span></span>   |
| <span data-ttu-id="0cd81-182">Sor részletei lap</span><span class="sxs-lookup"><span data-stu-id="0cd81-182">Line detail tab</span></span> |            |
| <span data-ttu-id="0cd81-183">Manuális</span><span class="sxs-lookup"><span data-stu-id="0cd81-183">Manual</span></span>          | <span data-ttu-id="0cd81-184">(megjelölve)</span><span class="sxs-lookup"><span data-stu-id="0cd81-184">(Marked)</span></span>   |

> [!NOTE]
> <span data-ttu-id="0cd81-185">A **Manuális** csúszka **Igen** állásra állítása a **Sor részletei** lapon minden egyes keresetikimutatás-sornál kulcsfontosságú ahhoz, hogy minden dolgozónál be lehessen vinni a nyitó bérlistaegyenlegeket.</span><span class="sxs-lookup"><span data-stu-id="0cd81-185">Setting the **Manual** slider to **Yes** in the **Line Details** tab for each earnings statement line is key to have payroll beginning balances entered for each worker.</span></span>

3. <span data-ttu-id="0cd81-186">A **Művelet** ablaktáblán kattintson a következőre: **Kereseti kimutatás kiadása** USA-FED-ER-FICA.</span><span class="sxs-lookup"><span data-stu-id="0cd81-186">On the **Action** pane, click **Release earnings statement** USA-FED-ER-FICA.</span></span>

4. <span data-ttu-id="0cd81-187">A **Művelet** ablaktáblán kattintson a **Fizetési kimutatás** lehetőségre a **Fizetési kimutatások létrehozása** lap megnyitásához, és állítsa be a következőket:</span><span class="sxs-lookup"><span data-stu-id="0cd81-187">On the **Action** pane click **Pay statement** to open the **Generate pay statements** page and set the following:</span></span>

| <span data-ttu-id="0cd81-188">Mező</span><span class="sxs-lookup"><span data-stu-id="0cd81-188">Field</span></span>              | <span data-ttu-id="0cd81-189">Érték</span><span class="sxs-lookup"><span data-stu-id="0cd81-189">Value</span></span>     |
|--------------------|-----------|
| <span data-ttu-id="0cd81-190">Fizetés dátuma</span><span class="sxs-lookup"><span data-stu-id="0cd81-190">Payment date</span></span>       | <span data-ttu-id="0cd81-191">2017/30/6</span><span class="sxs-lookup"><span data-stu-id="0cd81-191">6/30/2017</span></span> |
| <span data-ttu-id="0cd81-192">Kifizetés típusa</span><span class="sxs-lookup"><span data-stu-id="0cd81-192">Payment run type</span></span>   | <span data-ttu-id="0cd81-193">Manuális</span><span class="sxs-lookup"><span data-stu-id="0cd81-193">Manual</span></span>    |
| <span data-ttu-id="0cd81-194">Könyvelés letiltása</span><span class="sxs-lookup"><span data-stu-id="0cd81-194">Disable accounting</span></span> |   <span data-ttu-id="0cd81-195">Igen</span><span class="sxs-lookup"><span data-stu-id="0cd81-195">Yes</span></span>     |

> [!NOTE] 
> <span data-ttu-id="0cd81-196">Ez csak akkor érhető el, ha a kifizetési típus kézi, és a felhasználó le szeretné tiltani a könyvelést a fizetési időszakra.</span><span class="sxs-lookup"><span data-stu-id="0cd81-196">This is only available when the payment run type is manual and wherein the user want to disable accounting on the pay run.</span></span>

<span data-ttu-id="0cd81-197">Kattintson az **OK** lehetőségre, és zárja be az **Információs napló** elemet.</span><span class="sxs-lookup"><span data-stu-id="0cd81-197">Click **OK** and close the **Infolog**.</span></span>

#### <a name="why-the-disable-accounting-slider-needs-to-set-to-yes-when-generating-pay-statements"></a><span data-ttu-id="0cd81-198">Miért kell a Könyvelés letiltása csúszkát Igen állásba állítani a fizetési kimutatások létrehozásakor?</span><span class="sxs-lookup"><span data-stu-id="0cd81-198">Why the Disable Accounting slider needs to set to Yes when generating pay statements?</span></span>
<span data-ttu-id="0cd81-199">A csúszka **Igen** állásba állításával megelőzhető, hogy megtörténjen a fizetési kimutatás sorainak kiosztása a főkönyvbe.</span><span class="sxs-lookup"><span data-stu-id="0cd81-199">Setting the slider to **Yes** prevents lines in the pay statement from being districuted to General ledger.</span></span> <span data-ttu-id="0cd81-200">A főkönyvi összegek korábban frissítésre kerültek, amikor a régi rendszertől származó számlák egyenlegeit beírták.</span><span class="sxs-lookup"><span data-stu-id="0cd81-200">General ledger amounts were updating earlier when account balances from the legacy system were entered.</span></span> <span data-ttu-id="0cd81-201">A bérlista kezdeti egyenlegének bevitele révén olyan jelentéseket hozhat létre, amelyek tartalmazzák az előző évekből származó információkat, valamint a határértékek meghatározását juttatási és adózási célokból.</span><span class="sxs-lookup"><span data-stu-id="0cd81-201">Entering beginning balances for Payroll lets you generate reports that include information from prior years, as well as for identifying limits for benefit and tax purposes.</span></span>   

### <a name="c-create-pay-statements-for-employees"></a><span data-ttu-id="0cd81-202">C.</span><span class="sxs-lookup"><span data-stu-id="0cd81-202">C.</span></span> <span data-ttu-id="0cd81-203">Fizetési kimutatások létrehozása az alkalmazottak számára</span><span class="sxs-lookup"><span data-stu-id="0cd81-203">Create pay statements for employees</span></span>
<span data-ttu-id="0cd81-204">A nyitó egyenlegekkel rendelkező fizetési kimutatások létrehozása után ellenőriznie kell, hogy a fizetési kimutatások pontosan tükrözik-e a bérlistaadatokat.</span><span class="sxs-lookup"><span data-stu-id="0cd81-204">After you generate pay statements that have beginning balances, you must verify that the pay statements accurately reflect payroll data.</span></span> <span data-ttu-id="0cd81-205">Emellett manuálisan kell frissíteni a juttatásokra és az adókra vonatkozó adatokat, hogy megfeleljenek az előző bérszámfejtő rendszer értékeinek.</span><span class="sxs-lookup"><span data-stu-id="0cd81-205">You must also manually update the benefit and taxes information to match the values in the previous payroll system.</span></span> <span data-ttu-id="0cd81-206">Miután meggyőződött arról, hogy a korábbi bérszámfejtő rendszer összegei megfelelnek az aktuális fizetési kimutatások összegeinek, a fizetési kimutatásokat véglegesíteni kell.</span><span class="sxs-lookup"><span data-stu-id="0cd81-206">After you verify that the amounts from the previous payroll system match the amounts on the current pay statements, you must finalize the pay statements.</span></span>

1. <span data-ttu-id="0cd81-207">Nyissa meg az **Összes fizetési kimutatás** oldalt.</span><span class="sxs-lookup"><span data-stu-id="0cd81-207">Open the **All pay statements** page.</span></span>

2. <span data-ttu-id="0cd81-208">Jelölje ki a legutóbb Michael Redmond számára létrehozott fizetési kimutatást</span><span class="sxs-lookup"><span data-stu-id="0cd81-208">Highlight the last generated pay statement for Michael Redmond</span></span>

3. <span data-ttu-id="0cd81-209">Kattintson a **Szerkesztés** elemre a **Fizetési kimutatás** oldal megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="0cd81-209">Click **Edit** to open the **Pay statement** page.</span></span>

4. <span data-ttu-id="0cd81-210">Nyissa meg a **Juttatás levonásai** lapot, és írja be a következőt:</span><span class="sxs-lookup"><span data-stu-id="0cd81-210">Open the **Benefit deductions** tab and enter the following:</span></span>

| <span data-ttu-id="0cd81-211">Mező</span><span class="sxs-lookup"><span data-stu-id="0cd81-211">Field</span></span>                           | <span data-ttu-id="0cd81-212">Érték</span><span class="sxs-lookup"><span data-stu-id="0cd81-212">Value</span></span>            |
|---------------------------------|------------------|
| <span data-ttu-id="0cd81-213">Juttatás</span><span class="sxs-lookup"><span data-stu-id="0cd81-213">Benefit</span></span>                         | <span data-ttu-id="0cd81-214">Levonás összege</span><span class="sxs-lookup"><span data-stu-id="0cd81-214">Deduction amount</span></span> |
| <span data-ttu-id="0cd81-215">401K</span><span class="sxs-lookup"><span data-stu-id="0cd81-215">401K</span></span> | <span data-ttu-id="0cd81-216">Résztvétel</span><span class="sxs-lookup"><span data-stu-id="0cd81-216">Participate</span></span>              | <span data-ttu-id="0cd81-217">3000.00</span><span class="sxs-lookup"><span data-stu-id="0cd81-217">3000.00</span></span>          |
| <span data-ttu-id="0cd81-218">Fogászati</span><span class="sxs-lookup"><span data-stu-id="0cd81-218">Dental</span></span> | <span data-ttu-id="0cd81-219">SubSp</span><span class="sxs-lookup"><span data-stu-id="0cd81-219">SubSp</span></span>                  | <span data-ttu-id="0cd81-220">495,00</span><span class="sxs-lookup"><span data-stu-id="0cd81-220">495.00</span></span>           |
| <span data-ttu-id="0cd81-221">Elt. ellátási kiadások</span><span class="sxs-lookup"><span data-stu-id="0cd81-221">Dep care spending</span></span> | <span data-ttu-id="0cd81-222">Résztvétel</span><span class="sxs-lookup"><span data-stu-id="0cd81-222">Participate</span></span> | <span data-ttu-id="0cd81-223">2500.00</span><span class="sxs-lookup"><span data-stu-id="0cd81-223">2500.00</span></span>          |
| <span data-ttu-id="0cd81-224">Látás</span><span class="sxs-lookup"><span data-stu-id="0cd81-224">Vision</span></span> | <span data-ttu-id="0cd81-225">SupSp</span><span class="sxs-lookup"><span data-stu-id="0cd81-225">SupSp</span></span>                  | <span data-ttu-id="0cd81-226">500.00</span><span class="sxs-lookup"><span data-stu-id="0cd81-226">500.00</span></span>           |

5. <span data-ttu-id="0cd81-227">A **Juttatás hozzájárulásai** lapon írja be a következőt:</span><span class="sxs-lookup"><span data-stu-id="0cd81-227">In the **Benefit contributions** tab and enter the following:</span></span>

| <span data-ttu-id="0cd81-228">Mező</span><span class="sxs-lookup"><span data-stu-id="0cd81-228">Field</span></span>              | <span data-ttu-id="0cd81-229">Érték</span><span class="sxs-lookup"><span data-stu-id="0cd81-229">Value</span></span>               |
|--------------------|---------------------|
| <span data-ttu-id="0cd81-230">Juttatás</span><span class="sxs-lookup"><span data-stu-id="0cd81-230">Benefit</span></span>            | <span data-ttu-id="0cd81-231">Hozzájárulási összeg</span><span class="sxs-lookup"><span data-stu-id="0cd81-231">Contribution amount</span></span> |
| <span data-ttu-id="0cd81-232">401K</span><span class="sxs-lookup"><span data-stu-id="0cd81-232">401K</span></span> | <span data-ttu-id="0cd81-233">Résztvétel</span><span class="sxs-lookup"><span data-stu-id="0cd81-233">Participate</span></span> | <span data-ttu-id="0cd81-234">3000,00</span><span class="sxs-lookup"><span data-stu-id="0cd81-234">3000,00</span></span>             |
| <span data-ttu-id="0cd81-235">Fogászati</span><span class="sxs-lookup"><span data-stu-id="0cd81-235">Dental</span></span> | <span data-ttu-id="0cd81-236">SubSp</span><span class="sxs-lookup"><span data-stu-id="0cd81-236">SubSp</span></span>     | <span data-ttu-id="0cd81-237">495,00</span><span class="sxs-lookup"><span data-stu-id="0cd81-237">495.00</span></span>              |
| <span data-ttu-id="0cd81-238">Látás</span><span class="sxs-lookup"><span data-stu-id="0cd81-238">Vision</span></span> | <span data-ttu-id="0cd81-239">SubSp</span><span class="sxs-lookup"><span data-stu-id="0cd81-239">SubSp</span></span>     | <span data-ttu-id="0cd81-240">500.00</span><span class="sxs-lookup"><span data-stu-id="0cd81-240">500.00</span></span>              |

6. <span data-ttu-id="0cd81-241">Az **Adólevonások** lapon írja be a következőt:</span><span class="sxs-lookup"><span data-stu-id="0cd81-241">In the **Tax deductions** tab, enter the following:</span></span>

| <span data-ttu-id="0cd81-242">Mező</span><span class="sxs-lookup"><span data-stu-id="0cd81-242">Field</span></span>           | <span data-ttu-id="0cd81-243">Érték</span><span class="sxs-lookup"><span data-stu-id="0cd81-243">Value</span></span>            |
|-----------------|------------------|
| <span data-ttu-id="0cd81-244">Adókód</span><span class="sxs-lookup"><span data-stu-id="0cd81-244">Tax code</span></span>        | <span data-ttu-id="0cd81-245">Levonás összege</span><span class="sxs-lookup"><span data-stu-id="0cd81-245">Deduction amount</span></span> |
| <span data-ttu-id="0cd81-246">USA-FED-ER-FICA</span><span class="sxs-lookup"><span data-stu-id="0cd81-246">USA-FED-ER-FICA</span></span> | <span data-ttu-id="0cd81-247">1600.00</span><span class="sxs-lookup"><span data-stu-id="0cd81-247">1600.00</span></span>          |
| <span data-ttu-id="0cd81-248">USA-FED-ER-MEDI</span><span class="sxs-lookup"><span data-stu-id="0cd81-248">USA-FED-ER-MEDI</span></span> | <span data-ttu-id="0cd81-249">825.75</span><span class="sxs-lookup"><span data-stu-id="0cd81-249">825.75</span></span>           |

7. <span data-ttu-id="0cd81-250">Az **Adó-hozzájárulások** lapon írja be a következőt:</span><span class="sxs-lookup"><span data-stu-id="0cd81-250">In the **Tax contributions** tab enter the following:</span></span>

8. <span data-ttu-id="0cd81-251">Kattintson a **Számítás** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="0cd81-251">Click **Calculate**.</span></span>
> [!IMPORTANT] 
> <span data-ttu-id="0cd81-252">Ellenőrizze a fizetési kimutatás összegeit, hogy megfeleljenek a régi rendszerből hozott folyó évi összegnek a dolgozó esetében.</span><span class="sxs-lookup"><span data-stu-id="0cd81-252">Validate the totals of the pay statement that they match the YTD of the legacy system for the worker.</span></span> <span data-ttu-id="0cd81-253">A következő lépésben még nem kell végrehajtani a véglegesítést, hogy általános érvényesítést hajthasson végre az összes fizetési kimutatás összesített értékén.</span><span class="sxs-lookup"><span data-stu-id="0cd81-253">You may want to hold off on finalizing in the next step to do some overall validating of all pay statements in aggregate.</span></span> <span data-ttu-id="0cd81-254">Az ellenőrzést követően fusson végig az összes fizetési kimutatáson és véglegesítse őket.</span><span class="sxs-lookup"><span data-stu-id="0cd81-254">Once validated run through all the pay statements and finalize them.</span></span>

<span data-ttu-id="0cd81-255">Ugyanez az eljárás szükség esetén negyedéves lépésekben is elvégezhető, az összes korábbi negyedévre, minden évben.</span><span class="sxs-lookup"><span data-stu-id="0cd81-255">The same process can be done in quarter increments if necessary for all prior quarters in each year.</span></span> <span data-ttu-id="0cd81-256">Erre csak akkor van szükség, ha az ügyfélnek negyedéves bontásban kell megtekintenie az adatokat anélkül, hogy visszalépne a korábbi rendszerbe.</span><span class="sxs-lookup"><span data-stu-id="0cd81-256">This is only needed if the customer needs to see the data by quarter without going back to the legacy system.</span></span>

## <a name="if-you-make-a-mistake-entering-beginning-balances-for-an-employee"></a><span data-ttu-id="0cd81-257">Ha hibázik a nyitó egyenlegek alkalmazotthoz való bevitele közben</span><span class="sxs-lookup"><span data-stu-id="0cd81-257">If you make a mistake Entering Beginning Balances for an Employee</span></span>
<span data-ttu-id="0cd81-258">Lehetőség van a tranzakciók sztornírozására és ismételt bevitelére.</span><span class="sxs-lookup"><span data-stu-id="0cd81-258">It is possible to reverse and reenter transactions.</span></span> <span data-ttu-id="0cd81-259">A tranzakció sztornírozásához mindössze a következő lépéseket kell végrehajtani az **Összes fizetési kimutatás** oldalon.</span><span class="sxs-lookup"><span data-stu-id="0cd81-259">To reverse the transaction, all you have to do is to complete the follow steps on the **All pay statements** page.</span></span>

1. <span data-ttu-id="0cd81-260">Kattintson a **Sztornírozás** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="0cd81-260">Click **Reverse**.</span></span>

2. <span data-ttu-id="0cd81-261">Kattintson az **Igen** lehetőségre, amikor a következő üzenet: „Ha sztornírozza ezt a fizetési kimutatást, sztornírozó fizetési kimutatás kerül létrehozásra ezen fizetési kimutatás ellentételezésére.</span><span class="sxs-lookup"><span data-stu-id="0cd81-261">Click **Yes** when the message "When you reverse this pay statement, a reversing pay statement will be created to offset this pay statement.</span></span> <span data-ttu-id="0cd81-262">Egyik fizetési kimutatás sem szerkeszthető.</span><span class="sxs-lookup"><span data-stu-id="0cd81-262">Neither pay statement can be edited.</span></span> <span data-ttu-id="0cd81-263">Kívánja sztornírozni ezt a fizetési kimutatást?"</span><span class="sxs-lookup"><span data-stu-id="0cd81-263">Do you want to reverse this pay statement?"</span></span> <span data-ttu-id="0cd81-264">jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="0cd81-264">displays.</span></span> 

<span data-ttu-id="0cd81-265">A fizetési kimutatás sztornírozása után új fizetési kimutatást hozhat létre a munkavállaló számára a korábban létrehozott bevételi kimutatásból.</span><span class="sxs-lookup"><span data-stu-id="0cd81-265">After you reverse the pay statement, you can generate a new pay statement for the worker from the earnings statement that you created previously.</span></span> <span data-ttu-id="0cd81-266">Győződjön meg róla, hogy az új fizetési kimutatás létrehozása előtt kijavította a bevételi kimutatáson szereplő hibás sorokat, majd hozzon létre új fizetési kimutatásokat a helyes összegekkel.</span><span class="sxs-lookup"><span data-stu-id="0cd81-266">Be sure to fix any incorrect lines on the earnings statement before you generate the new pay statement, and then generate new pay statements with the correct amounts.</span></span> 
