---
title: "Kelet-európai házipénztár"
description: "Ez a témakör ismerteti a házipénztár funkciót, amellyel a felhasználók az Észtország, Litvánia, a Cseh Köztársaság, Magyarország, Lettország, Lengyelország és Oroszország készpénzműveleteit tükrözhetik a rendszerben."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: RCashBalance, RCashCountStatementForm, RCashPosting, RCashRemainLimit, RCashReportJour_PL, RCashTable, RCashTableBalance, RCashTableCredLimit, RCashTableLastRevaluation, RCashTableTransactions, RCashTrans
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 268504
ms.search.region: Czech Republic, Estonia, Hungary, Latvia, Lithuania, Poland, Russia
ms.author: v-elgolu
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 3ed41a57e40e8d90ebfd996f855a8dc8dc16de13
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="petty-cash-for-eastern-europe"></a><span data-ttu-id="f395a-103">Kelet-európai házipénztár</span><span class="sxs-lookup"><span data-stu-id="f395a-103">Petty cash for Eastern Europe</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="f395a-104">Ez a témakör ismerteti a házipénztár funkciót, amellyel a felhasználók az Észtország, Litvánia, a Cseh Köztársaság, Magyarország, Lettország, Lengyelország és Oroszország készpénzműveleteit tükrözhetik a rendszerben.</span><span class="sxs-lookup"><span data-stu-id="f395a-104">This topic provides information about the petty cash functionality that lets users in Estonia, Lithuania, Czech Republic, Hungary, Latvia, Poland, and Russia reflect cash operations in the system.</span></span>

<span data-ttu-id="f395a-105">A házipénztár funkciói készpénzműveletek, -bevételek és -kiadások automatizálására, elsődleges dokumentumok létrehozására és a kapcsolódó jelentések nyomtatására használhatók.</span><span class="sxs-lookup"><span data-stu-id="f395a-105">You can use the petty cash functionality to automate operations for receipts and expenditures of cash, the creation of primary documents, and the printing of related reports.</span></span> <span data-ttu-id="f395a-106">A házipénztár funkcióval az alábbi műveletek végezhetők:</span><span class="sxs-lookup"><span data-stu-id="f395a-106">The petty cash functionality lets you perform the following operations:</span></span>

-   <span data-ttu-id="f395a-107">A rendelkezésre álló készpénzes eszközök bevételének és kiadásának rögzítése.</span><span class="sxs-lookup"><span data-stu-id="f395a-107">Account the receipt and expenditure of available cash assets.</span></span>
-   <span data-ttu-id="f395a-108">Gyakori készpénzes űrlapok generálása: bevételezési pénztárbizonylatok, készpénzkifizetési bizonylatok és pénztárbizonylat-regisztrálási naplók.</span><span class="sxs-lookup"><span data-stu-id="f395a-108">Generate typical cash forms: Cash reimbursement slips, Cash disbursement slips, and a Journal of registration for cash slips.</span></span>
-   <span data-ttu-id="f395a-109">A vevői, szállítói stb. műveletek esetében engedélyezett legnagyobb készpénzösszeg ellenőrzése.</span><span class="sxs-lookup"><span data-stu-id="f395a-109">Control the maximum cash amount that is allowed for operations with customers, vendors, and so on.</span></span>
-   <span data-ttu-id="f395a-110">Különböző pénznemekben végzett készpénzműveletek tükrözése a rendszerben.</span><span class="sxs-lookup"><span data-stu-id="f395a-110">Reflect cash operations in various currencies in the system.</span></span>
-   <span data-ttu-id="f395a-111">Külföldi pénznemben végrejhatott készpénzösszeg-műveletek átváltása az alapértelmezett pénznemre a könyvelés számára készült jelentésekhez.</span><span class="sxs-lookup"><span data-stu-id="f395a-111">Convert the amounts of cash operations in foreign currency to the default currency to provide accounting reporting.</span></span>
-   <span data-ttu-id="f395a-112">**Pénztárkönyvi** és pénztári jelentés létrehozása.</span><span class="sxs-lookup"><span data-stu-id="f395a-112">Generate a **Cash book** report and a cashier’s report.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f395a-113">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="f395a-113">Prerequisites</span></span>
<span data-ttu-id="f395a-114">A házipénztár funkció használatához előbb a következő, előfeltételt jelentő feladatokat kell elvégezni:</span><span class="sxs-lookup"><span data-stu-id="f395a-114">Before you can use the petty cash functionality, you must complete the following prerequisites:</span></span>

-   <span data-ttu-id="f395a-115">Készpénzszámlák beállítása.</span><span class="sxs-lookup"><span data-stu-id="f395a-115">Set up cash accounts.</span></span>
-   <span data-ttu-id="f395a-116">Készpénzfeladási profilok beállítása.</span><span class="sxs-lookup"><span data-stu-id="f395a-116">Set up cash posting profiles.</span></span>
-   <span data-ttu-id="f395a-117">Számsorozatok beállítása pénztárbizonylatok számozásához.</span><span class="sxs-lookup"><span data-stu-id="f395a-117">Set up number sequences for cash document numbering.</span></span>
-   <span data-ttu-id="f395a-118">Alapértelmezett értékek és paraméterek beállítása készpénz és bank kezeléséhez.</span><span class="sxs-lookup"><span data-stu-id="f395a-118">Set up default values for Cash and bank management parameters.</span></span>
-   <span data-ttu-id="f395a-119">Készpénzkezelési naplónevek beállítása a főkönyvben.</span><span class="sxs-lookup"><span data-stu-id="f395a-119">Set up cash journal names in General ledger.</span></span>

### <a name="set-up-cash-accounts"></a><span data-ttu-id="f395a-120">Készpénzszámlák beállítása</span><span class="sxs-lookup"><span data-stu-id="f395a-120">Set up cash accounts</span></span>

<span data-ttu-id="f395a-121">Készpénz beállításához nyissa meg a **Készpénz- és bankkezelés** &gt; **Bankszámlák** &gt; **Készpénzszámlák** elemet, és adja meg a következő adatokat.</span><span class="sxs-lookup"><span data-stu-id="f395a-121">To set up a Cash, open **Cash and bank management** &gt; **Bank accounts** &gt; **Cash accounts**, and enter the following information.</span></span>

| <span data-ttu-id="f395a-122">Mező</span><span class="sxs-lookup"><span data-stu-id="f395a-122">Field</span></span>                 | <span data-ttu-id="f395a-123">Leírás</span><span class="sxs-lookup"><span data-stu-id="f395a-123">Description</span></span>                                                                                                          |
|-----------------------|----------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="f395a-124">Készpénz</span><span class="sxs-lookup"><span data-stu-id="f395a-124">Cash</span></span>                  | <span data-ttu-id="f395a-125">Adja meg a készpénzszámla (készpénz) azonosító kódját.</span><span class="sxs-lookup"><span data-stu-id="f395a-125">Enter a code to identify the cash account (cash).</span></span>                                                                    |
| <span data-ttu-id="f395a-126">Név</span><span class="sxs-lookup"><span data-stu-id="f395a-126">Name</span></span>                  | <span data-ttu-id="f395a-127">Adja meg a készpénzszámla leírását.</span><span class="sxs-lookup"><span data-stu-id="f395a-127">Enter a description of the cash account.</span></span>                                                                             |
| <span data-ttu-id="f395a-128">Pénznem</span><span class="sxs-lookup"><span data-stu-id="f395a-128">Currency</span></span>              | <span data-ttu-id="f395a-129">Állítsa be az alapértelmezett pénznemkódot a készpénztranzakciókhoz.</span><span class="sxs-lookup"><span data-stu-id="f395a-129">Select the default currency code for cash transactions.</span></span>                                                              |
| <span data-ttu-id="f395a-130">Számsorozatcsoport</span><span class="sxs-lookup"><span data-stu-id="f395a-130">Number sequence group</span></span> | <span data-ttu-id="f395a-131">Ha a pénztárbizonylatok számozása kötelezően különbözik paraméterek között megadott számozástól, adjon meg egy kódot.</span><span class="sxs-lookup"><span data-stu-id="f395a-131">If the numbering of cash documents must differ from the numbering that is specified in the parameters, enter a code.</span></span> |
| <span data-ttu-id="f395a-132">Több pénznem</span><span class="sxs-lookup"><span data-stu-id="f395a-132">More currencies</span></span>       | <span data-ttu-id="f395a-133">Jelölje be ezt a jelölőnégyzetet, és engedélyezze a pénznemeket, amelyek különböznek a könyvelés alapértelmezett pénznemétől.</span><span class="sxs-lookup"><span data-stu-id="f395a-133">Select this check box to allow currencies that differ from the accounting currency to be posted.</span></span>                     |
| <span data-ttu-id="f395a-134">Negatív készpénz</span><span class="sxs-lookup"><span data-stu-id="f395a-134">Negative cash</span></span>         | <span data-ttu-id="f395a-135">Jelölje be ezt a jelölőnégyzetet, és engedélyezze a negatív készpénzegyenlegeket bármely pénznemben.</span><span class="sxs-lookup"><span data-stu-id="f395a-135">Select this check box to allow negative cash balances in any currency.</span></span>                                               |

<span data-ttu-id="f395a-136">Készpénzszámla készpénzegyenlege ellenőrzési szabályainak beállításához válassza ki a készpénzszámlát, majd a műveletpanel **Készpénzszámla** lapján az **Egyenleg korlátja** csoportban kattintson az **Egyenleg korlátja** elemre.</span><span class="sxs-lookup"><span data-stu-id="f395a-136">To set up cash balance control rules for a cash account, select the cash account, and then, on the Action Pane, on the **Cash account** tab, in the **Balance limit** group, click **Balance limit**.</span></span> <span data-ttu-id="f395a-137">Adja meg a következő adatokat.</span><span class="sxs-lookup"><span data-stu-id="f395a-137">Enter the following information.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f395a-138">Mező</span><span class="sxs-lookup"><span data-stu-id="f395a-138">Field</span></span></th>
<th><span data-ttu-id="f395a-139">Leírás</span><span class="sxs-lookup"><span data-stu-id="f395a-139">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="f395a-140">Pénznemtípus</span><span class="sxs-lookup"><span data-stu-id="f395a-140">Currency type</span></span></td>
<td><span data-ttu-id="f395a-141">Válassza ki a pénznem típusát:</span><span class="sxs-lookup"><span data-stu-id="f395a-141">Select the type of currency:</span></span>
<ul>
<li><span data-ttu-id="f395a-142"><strong>Könyvelési pénznem</strong> – használja a vállalat alapvető pénznemkódját.</span><span class="sxs-lookup"><span data-stu-id="f395a-142"><strong>Accounting currency</strong> – Use the basic company currency code.</span></span></li>
<li><span data-ttu-id="f395a-143"><strong>Beállított valuta</strong> – használjon a vállalat alapvető pénznemkódjától eltérő pénznemkódot.</span><span class="sxs-lookup"><span data-stu-id="f395a-143"><strong>Indicated currency</strong> – Use a currency code that differs from the basic company currency code.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f395a-144">Pénznem</span><span class="sxs-lookup"><span data-stu-id="f395a-144">Currency</span></span></td>
<td><span data-ttu-id="f395a-145">Ha a <strong>Beállított valuta</strong> lehetőséget választotta a <strong>Pénznemtípus</strong> mezőben, válasszon pénznemkódot.</span><span class="sxs-lookup"><span data-stu-id="f395a-145">If you selected <strong>Indicated currency</strong> in the <strong>Currency type</strong> field, select a currency code.</span></span> <span data-ttu-id="f395a-146">Ez a mező nem áll rendelkezésre, ha a <strong>Könyvelési pénznem</strong> lehetőséget választotta a <strong>Pénznemtípus</strong> mezőben.</span><span class="sxs-lookup"><span data-stu-id="f395a-146">This field is unavailable if you selected <strong>Accounting currency</strong> in the <strong>Currency type</strong> field.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f395a-147">Egyenleg-határérték típusa</span><span class="sxs-lookup"><span data-stu-id="f395a-147">Balance limit type</span></span></td>
<td><span data-ttu-id="f395a-148">Válasszon a következő elérhető értékek közül:</span><span class="sxs-lookup"><span data-stu-id="f395a-148">Select one of the available values:</span></span>
<ul>
<li><span data-ttu-id="f395a-149"><strong>Maximális</strong> – a készpénzegyenleg nem haladhatja meg a készpénzszámlához tartozó <strong>Egyenleg korlátja</strong> összegét (felső határ).</span><span class="sxs-lookup"><span data-stu-id="f395a-149"><strong>Maximum</strong> – The cash balance should not be allowed to exceed the <strong>Balance limit</strong> amount for the cash account (upper bound).</span></span></li>
<li><span data-ttu-id="f395a-150"><strong>Minimális</strong> – a készpénzegyenleg nem süllyedhet a készpénzszámlához tartozó <strong>Egyenleg korlátja</strong> összege alá (alsó határ).</span><span class="sxs-lookup"><span data-stu-id="f395a-150"><strong>Minimum</strong> – The cash balance should not be allowed to go below the <strong>Balance limit</strong> amount for the cash account (bottom bound).</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f395a-151">Egyenlegkorlát ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="f395a-151">Check balance limit</span></span></td>
<td><span data-ttu-id="f395a-152">Válassza ki, mi történik a készpénzbefizetési bizonylatok jóváhagyási eljárása során, ha a készpénzszámla <strong>Egyenleg korlátja</strong> összegét átlépik:</span><span class="sxs-lookup"><span data-stu-id="f395a-152">Select what occurs during the approval process for cash documents if the <strong>Balance limit</strong> amount for the cash account is exceeded:</span></span>
<ul>
<li><span data-ttu-id="f395a-153"><strong>Elfogadás</strong> – A határérték túlléphető.</span><span class="sxs-lookup"><span data-stu-id="f395a-153"><strong>Accept</strong> – The limit can be exceeded.</span></span></li>
<li><span data-ttu-id="f395a-154"><strong>Figyelmeztetés</strong> – a határérték átléphető, de a felhasználó figyelmeztető üzenetet kap.</span><span class="sxs-lookup"><span data-stu-id="f395a-154"><strong>Warning</strong> – The limit can be exceeded, but the user receives a warning message.</span></span> <span data-ttu-id="f395a-155">A készpénzbizonylat megerősítésre vagy jóváhagyásra kerül.</span><span class="sxs-lookup"><span data-stu-id="f395a-155">The cash document is confirmed or approved.</span></span></li>
<li><span data-ttu-id="f395a-156"><strong>Hiba</strong> – A határérték nem léphető túl.</span><span class="sxs-lookup"><span data-stu-id="f395a-156"><strong>Error</strong> – The limit can't be exceeded.</span></span> <span data-ttu-id="f395a-157">A felhasználó hibaüzenetet kap, és a készpénzbizonylat nem kerül megerősítésre vagy jóváhagyásra.</span><span class="sxs-lookup"><span data-stu-id="f395a-157">The user receives an error message, and the cash document isn't confirmed or approved.</span></span></li>
</ul>
<span data-ttu-id="f395a-158">A készpénzbizonylatok jóváhagyási folyamatával kapcsolatos további tudnivalókért lásd a &quot;Készpénztranzakciók jóváhagyása és feladása&quot; részt a témakör későbbi részében.</span><span class="sxs-lookup"><span data-stu-id="f395a-158">For more information about the approval process for cash documents, see the &quot;Cash transaction approval and posting&quot; section, later in this topic.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f395a-159">Egyenleg korlátja</span><span class="sxs-lookup"><span data-stu-id="f395a-159">Balance limit</span></span></td>
<td><span data-ttu-id="f395a-160">Adja meg a készpénzszámla egyenlegének határértékét.</span><span class="sxs-lookup"><span data-stu-id="f395a-160">Enter a limit for the cash account balance.</span></span> <span data-ttu-id="f395a-161">Az összegnek a megadott pénznemben kell lennie.</span><span class="sxs-lookup"><span data-stu-id="f395a-161">The amount should be in the currency that you specified.</span></span></td>
</tr>
</tbody>
</table>

### <a name="set-up-cash-posting-profiles"></a><span data-ttu-id="f395a-162">Készpénzfeladási profilok beállítása</span><span class="sxs-lookup"><span data-stu-id="f395a-162">Set up cash posting profiles</span></span>

<span data-ttu-id="f395a-163">A készpénzfeladási profilok határozzák meg a főkönyvi feladásokat.</span><span class="sxs-lookup"><span data-stu-id="f395a-163">Cash posting profiles define postings to the general ledger.</span></span> <span data-ttu-id="f395a-164">Készpénzfeladási profil beállításához lépjen a **Készpénz-** **és bankkezelés** &gt; **Beállítás** &gt; **Készpénzfeladási sablonok** pontra, és válasszon vagy hozzon létre feladási profilt.</span><span class="sxs-lookup"><span data-stu-id="f395a-164">To set up a cash posting profile, go to **Cash** **and bank management** &gt; **Setup** &gt; **Cash posting profiles**, and select or create a posting profile.</span></span> <span data-ttu-id="f395a-165">Adja meg a következő adatokat.</span><span class="sxs-lookup"><span data-stu-id="f395a-165">Enter the following information.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f395a-166">Mező</span><span class="sxs-lookup"><span data-stu-id="f395a-166">Field</span></span></th>
<th><span data-ttu-id="f395a-167">Leírás</span><span class="sxs-lookup"><span data-stu-id="f395a-167">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="f395a-168">Érvényes</span><span class="sxs-lookup"><span data-stu-id="f395a-168">Valid for</span></span></td>
<td><span data-ttu-id="f395a-169">Válassza ki, hogy a feladási profil egy adott készpénzszámlára vagy minden készpénzszámlára vonatkozik-e:</span><span class="sxs-lookup"><span data-stu-id="f395a-169">Select whether the posting profile applies to a specific cash account or all cash accounts:</span></span>
<ul>
<li><span data-ttu-id="f395a-170"><strong>Táblázat</strong> – ha létezik feladási profilsor a készpénzes számlához, a úgy ez a sor kerül felhasználásra a készpénztranzakciók feladásánál.</span><span class="sxs-lookup"><span data-stu-id="f395a-170"><strong>Table</strong> – If there is a posting profile line for the cash account, that line is used for cash transaction posting.</span></span></li>
<li><span data-ttu-id="f395a-171"><strong>Mind</strong> – nincs feladási profilsor a készpénzszámlához.</span><span class="sxs-lookup"><span data-stu-id="f395a-171"><strong>All</strong> – There is no posting profile line for the cash account.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f395a-172">Készpénz</span><span class="sxs-lookup"><span data-stu-id="f395a-172">Cash</span></span></td>
<td><span data-ttu-id="f395a-173">Ha a <strong>Tábla</strong> lehetőséget választotta az <strong>Érvényes</strong> mezőben, akkor adja meg a készpénzszámlát.</span><span class="sxs-lookup"><span data-stu-id="f395a-173">If you selected <strong>Table</strong> in the <strong>Valid for</strong> field, specify the cash account.</span></span> <span data-ttu-id="f395a-174">A mező üresen marad, ha a <strong>Mind</strong> elemet választotta az <strong>Érvényes</strong> mezőben.</span><span class="sxs-lookup"><span data-stu-id="f395a-174">This field remains blank if you selected <strong>All</strong> in the <strong>Valid for</strong> field.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f395a-175">Főkönyvi számla</span><span class="sxs-lookup"><span data-stu-id="f395a-175">Ledger account</span></span></td>
<td><span data-ttu-id="f395a-176">Adja meg a készpénzszámla összegző számlájaként használni kívánt főkönyvi számla számát.</span><span class="sxs-lookup"><span data-stu-id="f395a-176">Enter the number of the ledger account to use as the summary account for the cash account.</span></span></td>
</tr>
</tbody>
</table>

### <a name="set-up-number-sequences-for-cash-documents"></a><span data-ttu-id="f395a-177">Készpénzbizonylatok számsorozatainak beállítása</span><span class="sxs-lookup"><span data-stu-id="f395a-177">Set up number sequences for cash documents</span></span>

<span data-ttu-id="f395a-178">Készpénzbizonylatok számsorozatainak beállításához lépjen a **Készpénz- és bankkezelés** &gt; **Beállítás** &gt; **Készpénz- és bankkezelési paraméterek** elemre.</span><span class="sxs-lookup"><span data-stu-id="f395a-178">To set up number sequences for cash documents, go to **Cash and bank management** &gt; **Setup** &gt; **Cash and bank management parameters**.</span></span> <span data-ttu-id="f395a-179">A **Számsorozat** lapon adja meg a számsorozat-kódokat a **Bevételezési pénztárbizonylatok**, **Készpénz-kifizetési bizonylatok**, **Készpénzkorrekciós bizonylatok** és **Árfolyam-korrekció** bizonylatok, valamint a **Készpénzjelentés száma** számára.</span><span class="sxs-lookup"><span data-stu-id="f395a-179">On the **Number sequence** tab, specify number sequence codes for the **Cash reimbursement slips**, **Cash disbursement slips**, **Cash correction voucher**, and **Exchange adjustment** documents, and for **Cash report number**.</span></span>

### <a name="set-up-default-values-for-cash-and-bank-management-parameters"></a><span data-ttu-id="f395a-180">Alapértelmezett értékek és paraméterek beállítása készpénz és bank kezeléséhez</span><span class="sxs-lookup"><span data-stu-id="f395a-180">Set up default values for Cash and bank management parameters</span></span>

<span data-ttu-id="f395a-181">Alapértelmezett értékek és paraméterek beállításához készpénz és bank kezeléséhez a házipénztár funkcióban lépjen a **Készpénz- és bankkezelés** &gt; **Beállítás** &gt; **Készpénz- és bankkezelési paraméterek** elemre.</span><span class="sxs-lookup"><span data-stu-id="f395a-181">To set up default values for Cash and bank management parameters for the petty cash functionality, go to **Cash and bank management** &gt; **Setup** &gt; **Cash and bank management parameters**.</span></span> <span data-ttu-id="f395a-182">A **Készpénz** lapon adja meg a következő adatokat.</span><span class="sxs-lookup"><span data-stu-id="f395a-182">On the **Cash** tab, enter the following information.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f395a-183">Mező</span><span class="sxs-lookup"><span data-stu-id="f395a-183">Field</span></span></th>
<th><span data-ttu-id="f395a-184">Leírás</span><span class="sxs-lookup"><span data-stu-id="f395a-184">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="f395a-185">Készpénz</span><span class="sxs-lookup"><span data-stu-id="f395a-185">Cash</span></span></td>
<td><span data-ttu-id="f395a-186">Válassza ki a naplókhoz használandó alapértelmezett készpénzszámlát.</span><span class="sxs-lookup"><span data-stu-id="f395a-186">Select the default cash account in journals.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f395a-187">Készpénzfeladás</span><span class="sxs-lookup"><span data-stu-id="f395a-187">Cash posting</span></span></td>
<td><span data-ttu-id="f395a-188">Adja meg az alapértelmezett feladási profilt, amelyet a rendszer akkor használ, ha más feladási profil nincs megadva.</span><span class="sxs-lookup"><span data-stu-id="f395a-188">Enter the default cash posting profile that is used if no other posting profile is specified.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f395a-189">Felhasznált bizonylat ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="f395a-189">Check for voucher used</span></span></td>
<td><span data-ttu-id="f395a-190">Válassza ki, mi történik, ha a készpénzbizonylat számának ellenőrzése során ismétlődő számok találhatók:</span><span class="sxs-lookup"><span data-stu-id="f395a-190">Select what occurs if duplicate numbers are found during the check of the cash document number:</span></span>
<ul>
<li><span data-ttu-id="f395a-191">Ismétlődések tiltása</span><span class="sxs-lookup"><span data-stu-id="f395a-191">Reject duplicate</span></span></li>
<li><span data-ttu-id="f395a-192">Ismétlődések tiltása a pénzügyi éven belül</span><span class="sxs-lookup"><span data-stu-id="f395a-192">Reject copies within fiscal year</span></span></li>
<li><span data-ttu-id="f395a-193">Ismétlődések elfogadása</span><span class="sxs-lookup"><span data-stu-id="f395a-193">Accept duplicates</span></span></li>
<li><span data-ttu-id="f395a-194">Figyelmeztetés ismétlődés esetén</span><span class="sxs-lookup"><span data-stu-id="f395a-194">Warn in case of duplicates</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f395a-195">Műveletek korlátjának ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="f395a-195">Check operations limit</span></span></td>
<td><span data-ttu-id="f395a-196">Adja meg, mi történik az ellenoldali feleket érintő műveletek határértékének túllépése esetén:</span><span class="sxs-lookup"><span data-stu-id="f395a-196">Specify what occurs if the limit for operations with counteragents is exceeded:</span></span>
<ul>
<li><span data-ttu-id="f395a-197"><strong>Elfogadás</strong> – A határérték túlléphető.</span><span class="sxs-lookup"><span data-stu-id="f395a-197"><strong>Accept</strong> – The limit can be exceeded.</span></span></li>
<li><span data-ttu-id="f395a-198"><strong>Figyelmeztetés</strong> – a határérték átléphető, de a felhasználó figyelmeztető üzenetet kap.</span><span class="sxs-lookup"><span data-stu-id="f395a-198"><strong>Warning</strong> – The limit can be exceeded, but the user receives a warning message.</span></span> <span data-ttu-id="f395a-199">A művelet fel van adva.</span><span class="sxs-lookup"><span data-stu-id="f395a-199">The operation is posted.</span></span></li>
<li><span data-ttu-id="f395a-200"><strong>Hiba</strong> – A határérték nem léphető túl.</span><span class="sxs-lookup"><span data-stu-id="f395a-200"><strong>Error</strong> – The limit can't be exceeded.</span></span> <span data-ttu-id="f395a-201">A felhasználó hibaüzenetet kap, és a művelet feladása nem történik meg.</span><span class="sxs-lookup"><span data-stu-id="f395a-201">The user receives an error message, and the operation isn't posted.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f395a-202">Ellenőrzési mód</span><span class="sxs-lookup"><span data-stu-id="f395a-202">Validation method</span></span></td>
<td><span data-ttu-id="f395a-203">Válassza ki a műveletek határértékének túllépését felügyelő ellenőrzési módot:</span><span class="sxs-lookup"><span data-stu-id="f395a-203">Select the validation method that is used to control exceeded limit amounts for operations:</span></span>
<ul>
<li><span data-ttu-id="f395a-204"><strong>Művelet</strong> – ellenőrzés tranzakciónként</span><span class="sxs-lookup"><span data-stu-id="f395a-204"><strong>Operation</strong> – Validation is done per transaction</span></span></li>
<li><span data-ttu-id="f395a-205"><strong>Megállapodás</strong> – ellenőrzés olyan tranzakciónként, amelyhez megadott szerződés tartozik egy ellenoldali féllel.</span><span class="sxs-lookup"><span data-stu-id="f395a-205"><strong>Agreement</strong> – Validation is done per transaction that has a specified contract with a counteragent.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f395a-206">Műveletek korlátja</span><span class="sxs-lookup"><span data-stu-id="f395a-206">Operations limit</span></span></td>
<td><span data-ttu-id="f395a-207">Adja meg az ellenoldali felekkel rendelkező műveletekhez tartozó maximális készpénzösszeget.</span><span class="sxs-lookup"><span data-stu-id="f395a-207">Enter the maximum amount that is allowed for operations with counteragents in cash.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f395a-208">Feladás korábbi dátummal</span><span class="sxs-lookup"><span data-stu-id="f395a-208">Posting on earlier date</span></span></td>
<td><span data-ttu-id="f395a-209">Jelölje be ezt a jelölőnégyzetet, hogy engedélyezze a legutóbbi készpénztranzakció dátuma előtti készpénztranzakciók feladását.</span><span class="sxs-lookup"><span data-stu-id="f395a-209">Select this check box to enable cash transactions to be posted before the last date of the cash transaction.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f395a-210">Dimenziók</span><span class="sxs-lookup"><span data-stu-id="f395a-210">Dimensions</span></span></td>
<td><span data-ttu-id="f395a-211">Adja meg a dimenziókat a <strong>Részleg kódja</strong>, <strong>Analitikai kód</strong> és <strong>Cél kódja</strong> mezőkben.</span><span class="sxs-lookup"><span data-stu-id="f395a-211">Enter dimensions in the <strong>Department code</strong>, <strong>Analytical code</strong>, and <strong>Purpose code</strong> fields.</span></span> <span data-ttu-id="f395a-212">A készpénzbizonylatok nyomtatása űrlap tükrözni fogja ezt az információt.</span><span class="sxs-lookup"><span data-stu-id="f395a-212">The printing form for cash documents will reflect this information.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f395a-213">Jóváhagyási állapot használata</span><span class="sxs-lookup"><span data-stu-id="f395a-213">Use confirm status</span></span></td>
<td><span data-ttu-id="f395a-214">Jelölje be ezt a jelölőnégyzetet, ha egy további állapotot (<strong>Visszaigazolva</strong>) kíván alkalmazni készpénzbizonylatok jóváhagyási folyamata során.</span><span class="sxs-lookup"><span data-stu-id="f395a-214">Select this check box to use an additional status, <strong>Confirmed</strong>, during the approval process for cash documents.</span></span> <span data-ttu-id="f395a-215">(További információkért lásd a &quot;Készpénztranzakciók jóváhagyása és feladása&quot; szakaszt.)</span><span class="sxs-lookup"><span data-stu-id="f395a-215">(For more information, see the &quot;Cash transaction approval and posting&quot; section.)</span></span></td>
</tr>
</tbody>
</table>

### <a name="set-up-cash-journal-names-in-general-ledger"></a><span data-ttu-id="f395a-216">Készpénzkezelési naplónevek beállítása a főkönyvben</span><span class="sxs-lookup"><span data-stu-id="f395a-216">Set up cash journal names in General ledger</span></span>

<span data-ttu-id="f395a-217">Készpénztranzakciók feladására napló létrehozásához lépjen a **Főkönyv** &gt; **Napló beállítása** &gt; **Naplónevek** elemre, és hozzon létre egy új rekordot.</span><span class="sxs-lookup"><span data-stu-id="f395a-217">To create a journal for cash transaction posting, go to **General ledger** &gt; **Journal setup** &gt; **Journal names**, and create a new record.</span></span> <span data-ttu-id="f395a-218">A **Naplótípus** mezőben válassza ki a **Készpénz** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f395a-218">In the **Journal type** field, specify **Cash**.</span></span> <span data-ttu-id="f395a-219">Adja meg az egyéb szükséges alapértelmezett naplóparamétereket.</span><span class="sxs-lookup"><span data-stu-id="f395a-219">Define other default journal parameters as you require.</span></span>

## <a name="daily-cash-operations-via-a-slip-journal"></a><span data-ttu-id="f395a-220">Napi készpénzműveletek Bizonylatnapló révén</span><span class="sxs-lookup"><span data-stu-id="f395a-220">Daily cash operations via a Slip journal</span></span>
<span data-ttu-id="f395a-221">Készpénzbizonylat létrehozásához Bizonylatnapló révén lépjen a **Készpénz- és bankkezelés** &gt; **Készpénztranzakciók** &gt; **Bizonylatnapló** elemre, és hozzon létre egy új naplót.</span><span class="sxs-lookup"><span data-stu-id="f395a-221">To create a cash document via a Slip journal, go to **Cash and bank management** &gt; **Cash transactions** &gt; **Slip journal**, and create a new journal.</span></span> <span data-ttu-id="f395a-222">A Művelet panelen kattintson a **Sorok** elemre.</span><span class="sxs-lookup"><span data-stu-id="f395a-222">On the Action Pane, click **Lines**.</span></span> <span data-ttu-id="f395a-223">Adjon hozzá új sort, és írja be a következő adatokat.</span><span class="sxs-lookup"><span data-stu-id="f395a-223">Add a new line, and enter the following information.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f395a-224">Mező</span><span class="sxs-lookup"><span data-stu-id="f395a-224">Field</span></span></th>
<th><span data-ttu-id="f395a-225">Leírás</span><span class="sxs-lookup"><span data-stu-id="f395a-225">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="f395a-226">Dátum</span><span class="sxs-lookup"><span data-stu-id="f395a-226">Date</span></span></td>
<td><span data-ttu-id="f395a-227">Adja meg a tranzakció dátumát.</span><span class="sxs-lookup"><span data-stu-id="f395a-227">Enter the date of the transaction.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f395a-228">Könyvelési számla</span><span class="sxs-lookup"><span data-stu-id="f395a-228">Account</span></span></td>
<td><span data-ttu-id="f395a-229">Válassza ki a készpénzes számlát.</span><span class="sxs-lookup"><span data-stu-id="f395a-229">Select the cash account.</span></span> <span data-ttu-id="f395a-230">Alapértelmezés szerint a készpénzes számlák a Készpénz- és bankkezelési paraméterek között vannak megadva.</span><span class="sxs-lookup"><span data-stu-id="f395a-230">By default, a cash account is specified in the Cash and bank management parameters.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f395a-231">Leírás</span><span class="sxs-lookup"><span data-stu-id="f395a-231">Description</span></span></td>
<td><span data-ttu-id="f395a-232">Adjon meg magyarázó szöveget a tranzakcióhoz.</span><span class="sxs-lookup"><span data-stu-id="f395a-232">Enter explanatory text for the transaction.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f395a-233">Tartozik Követel</span><span class="sxs-lookup"><span data-stu-id="f395a-233">Debit Credit</span></span></td>
<td><span data-ttu-id="f395a-234">Adja meg a készpénzbizonylat összegét a következő mezők egyikében:</span><span class="sxs-lookup"><span data-stu-id="f395a-234">Enter cash document amount in one of these fields:</span></span>
<ul>
<li><span data-ttu-id="f395a-235"><strong>Tartozik</strong> – a mező használatával készpénzbevételek és a bevételezési pénztárbizonylatok rögzíthetők.</span><span class="sxs-lookup"><span data-stu-id="f395a-235"><strong>Debit</strong> – Use this field to register cash receipts and a Cash reimbursement slip.</span></span></li>
<li><span data-ttu-id="f395a-236"><strong>Követel</strong> – a mező használatával készpénzkiadások és a készpénz-kifizetési bizonylatok rögzíthetők.</span><span class="sxs-lookup"><span data-stu-id="f395a-236"><strong>Credit</strong> – Use this field to register cash expenditures and a Cash disbursement slip.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f395a-237">Ellenszámla típusa Ellenszámla</span><span class="sxs-lookup"><span data-stu-id="f395a-237">Offset account type Offset account</span></span></td>
<td><span data-ttu-id="f395a-238">Válasszon ellenszámlatípust és ellenszámlaszámot.</span><span class="sxs-lookup"><span data-stu-id="f395a-238">Select an offset account type and offset account number.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f395a-239">Pénznem</span><span class="sxs-lookup"><span data-stu-id="f395a-239">Currency</span></span></td>
<td><span data-ttu-id="f395a-240">Válassza ki a tranzakció pénznemkódját.</span><span class="sxs-lookup"><span data-stu-id="f395a-240">Select the code for the transaction currency.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f395a-241">Bizonylat </span><span class="sxs-lookup"><span data-stu-id="f395a-241">Voucher</span></span></td>
<td><span data-ttu-id="f395a-242">Ezt a mezőt a rendszer automatikusan kitölti a napló beállítása alapján.</span><span class="sxs-lookup"><span data-stu-id="f395a-242">This field is filled in automatically, based on the journal setup.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f395a-243">Rendelés száma</span><span class="sxs-lookup"><span data-stu-id="f395a-243">Order number</span></span></td>
<td><span data-ttu-id="f395a-244">Ha nincs más számsorozat beállítva a készpénzszámlához, ez a mező automatikusan ki van töltve a paraméterekben megadott számsorozat alapján.</span><span class="sxs-lookup"><span data-stu-id="f395a-244">If no other number sequence is set up for the cash account, this field is filled in automatically, based on the number sequence that is specified in the parameters.</span></span> <span data-ttu-id="f395a-245">Igény szerint ebben a mezőben rendelési szám manuális bevitele lehetséges.</span><span class="sxs-lookup"><span data-stu-id="f395a-245">You can manually enter an order number in this field as you require.</span></span> <span data-ttu-id="f395a-246">A készpénzbizonylatok számozási következetlenségeinek megelőzése érdekében a következő felügyelet kerül alkamazásra: olyan készpénzbizonylat száma, amelynél a művelet dátuma korábbi, nem lehet nagyobb, mint a későbbi műveleti dátumú készpénzbizonylatok száma.</span><span class="sxs-lookup"><span data-stu-id="f395a-246">To prevent inconsistence in cash document numbering, the following control is applied: the number of a cash document that has an earlier date of operation can't be higher than number of a cash document that has a later date of operation.</span></span> <span data-ttu-id="f395a-247">Ha nem igényli ezt a felügyeletet, jelölje be a <strong>Feladás korábbi dátummal</strong> jelölőnégyzetet a Készpénz- és bankkezelési paraméterek között.</span><span class="sxs-lookup"><span data-stu-id="f395a-247">If you don't require this control, select the <strong>Posting on earlier date</strong> check box in the Cash and bank management parameters.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f395a-248">Jóváhagyási állapot</span><span class="sxs-lookup"><span data-stu-id="f395a-248">Approval status</span></span></td>
<td><span data-ttu-id="f395a-249">Az első tranzakció állapota <strong>Nincs</strong>.</span><span class="sxs-lookup"><span data-stu-id="f395a-249">The first transaction status is <strong>None</strong>.</span></span> <span data-ttu-id="f395a-250">A tranzakció állapotának beállításával kapcsolatos tudnivalókért lásd a &quot;Készpénztranzakciók jóváhagyása és feladása&quot; szakaszt.</span><span class="sxs-lookup"><span data-stu-id="f395a-250">For information about how to set the transaction status, See the &quot;Cash transaction approval and posting&quot; section.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f395a-251">Dokumentumtípus </span><span class="sxs-lookup"><span data-stu-id="f395a-251">Document type</span></span></td>
<td><span data-ttu-id="f395a-252">Ezt a mezőt a <strong>Készpénzutalvány</strong> lapon a rendszer automatikusan kitölti a készpénzbizonylathoz megadott összeg alapján:</span><span class="sxs-lookup"><span data-stu-id="f395a-252">This field on the <strong>Cash order</strong> tab is filled in automatically, based on the amount that you entered for the cash document:</span></span>
<ul>
<li><span data-ttu-id="f395a-253"><strong>Bevételezési pénztárbizonylat</strong> – ez az érték kerül használatra, ha a készpénzszámla <strong>Tartozik</strong> mezőjében adott meg összeget.</span><span class="sxs-lookup"><span data-stu-id="f395a-253"><strong>Cash reimbursement slip</strong> – This value is used if you entered an amount in the <strong>Debit</strong> field for the cash account.</span></span></li>
<li><span data-ttu-id="f395a-254"><strong>Készpénz-kifizetési bizonylat</strong> – ez az érték kerül használatra, ha a készpénzszámla <strong>Követel</strong> mezőjében adott meg összeget.</span><span class="sxs-lookup"><span data-stu-id="f395a-254"><strong>Cash disbursement slip</strong> – This value is used if you entered an amount in the <strong>Credit</strong> field for the cash account</span></span></li>
<li><span data-ttu-id="f395a-255"><strong>Korrekció</strong> – negatív összeget adott meg a készpénzszámla <strong>Tartozik</strong> vagy a <strong>Követel</strong> mezőjében.</span><span class="sxs-lookup"><span data-stu-id="f395a-255"><strong>Correction</strong> – You entered a negative amount in either the <strong>Debit</strong> field or the <strong>Credit</strong> field for the cash account.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f395a-256">Áfacsoport</span><span class="sxs-lookup"><span data-stu-id="f395a-256">Sales tax group</span></span></td>
<td><span data-ttu-id="f395a-257">Adjon meg egy áfacsoportot a művelet adóinak kiszámítására.</span><span class="sxs-lookup"><span data-stu-id="f395a-257">Specify a sales tax group to calculate taxes on the operation.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f395a-258">Cikkáfacsoport</span><span class="sxs-lookup"><span data-stu-id="f395a-258">Item sales tax group</span></span></td>
<td><span data-ttu-id="f395a-259">Adjon meg egy cikkáfacsoportot a művelet adóinak kiszámítására.</span><span class="sxs-lookup"><span data-stu-id="f395a-259">Specify an item sales tax group to calculate taxes on the operation.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f395a-260">Jogcím</span><span class="sxs-lookup"><span data-stu-id="f395a-260">Reason</span></span></td>
<td><span data-ttu-id="f395a-261">A <strong>Készpénzutalvány</strong> lapon adja meg a tranzakció tárgyának leírását.</span><span class="sxs-lookup"><span data-stu-id="f395a-261">On the <strong>Cash order</strong> tab, enter text that describes the transaction subject.</span></span> <span data-ttu-id="f395a-262">Ez a szöveg nyomtatásnál rákerül a pénztárbizonylat formanyomtatványára.</span><span class="sxs-lookup"><span data-stu-id="f395a-262">This text will be printed on the cash slip reporting form.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f395a-263">Dokumentum dátuma</span><span class="sxs-lookup"><span data-stu-id="f395a-263">Document Date</span></span></td>
<td><span data-ttu-id="f395a-264">Adja meg a tranzakció okát adó elsődleges dokumentum (például előzetes jelentés, számla vagy rendelés) leírását, számát és dátumát.</span><span class="sxs-lookup"><span data-stu-id="f395a-264">Enter the description, number, and date of the primary document that is the reason for the transaction (for example, advance reports, invoice, or order).</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f395a-265">Képviselő típusa</span><span class="sxs-lookup"><span data-stu-id="f395a-265">Representative type</span></span></td>
<td><span data-ttu-id="f395a-266">Ez a mező a következő értékeket veheti fel:</span><span class="sxs-lookup"><span data-stu-id="f395a-266">This field can have the following values:</span></span>
<ul>
<li><span data-ttu-id="f395a-267"><strong>Dolgozó</strong> – a <strong>Képviselő</strong> keresés alkalmazottak listáját tartalmazza, ha az <strong>Ellenszámla</strong> mező értéke <strong>Főkönyv</strong> vagy <strong>Bank</strong>, illetve az ellenoldali fél kapcsolattartóinak listáját, ha az <strong>Ellenszámla</strong> mező értéke <strong>Vevő</strong> vagy <strong>Szállító</strong>.</span><span class="sxs-lookup"><span data-stu-id="f395a-267"><strong>Worker</strong> – The <strong>Representative</strong> lookup contains a list of employees if the <strong>Offset account</strong> field is set to <strong>Ledger</strong> or <strong>Bank</strong>, or a list of the counteragent's contact persons if the <strong>Offset account</strong> field is set to <strong>Customer</strong> or <strong>Vendor</strong>.</span></span> <span data-ttu-id="f395a-268">Képviselők beállításához lépjen az <strong>Alap</strong> &gt; <strong>Beállítás</strong> &gt; <strong>Kapcsolattartók</strong> &gt; <strong>Kapcsolattartó</strong> elemre.</span><span class="sxs-lookup"><span data-stu-id="f395a-268">To set up representatives, go to <strong>Basic</strong> &gt; <strong>Setup</strong> &gt; <strong>Contacts</strong> &gt; <strong>Contact person</strong>.</span></span></li>
<li><span data-ttu-id="f395a-269"><strong>Egyéb</strong> – a <strong>Képviselő</strong> keresés más ügyfelek listáját tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="f395a-269"><strong>Other</strong> – The <strong>Representative</strong> lookup contains a list of other clients.</span></span> <span data-ttu-id="f395a-270">A <strong>Vevők</strong> vagy <strong>Szállítók</strong> táblában nem szereplő jogosultak beállításához lépjen a <strong>Főkönyv</strong> &gt; <strong>Jogosultak</strong> elemre.</span><span class="sxs-lookup"><span data-stu-id="f395a-270">To set up receivers who don't appear in the <strong>Customers</strong> or <strong>Vendors</strong> table, go to <strong>General ledger</strong> &gt; <strong>Receivers</strong>.</span></span> <span data-ttu-id="f395a-271">Ez a típus csak Lettországban érhető el.</span><span class="sxs-lookup"><span data-stu-id="f395a-271">This type is available only for Latvia.</span></span> <span data-ttu-id="f395a-272">(A <strong>CSELatvia</strong> konfigurációs kulcsnak engedélyezve kell lennie.)</span><span class="sxs-lookup"><span data-stu-id="f395a-272">(The <strong>CSELatvia</strong> configuration key should be enabled.)</span></span></li>
<li><span data-ttu-id="f395a-273"><strong>Szállító</strong> – a <strong>Képviselő</strong> keresés szállítók listáját tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="f395a-273"><strong>Vendor</strong> – The <strong>Representative</strong> lookup contains a list of vendors.</span></span> <span data-ttu-id="f395a-274">Szállítók beállításához lépjen a <strong>Kötelezettségek</strong> &gt; <strong>Szállítók</strong> elemre.</span><span class="sxs-lookup"><span data-stu-id="f395a-274">To set up vendors, go to <strong>Accounts payable</strong> &gt; <strong>Vendors</strong>.</span></span></li>
<li><span data-ttu-id="f395a-275"><strong>Vevő</strong> – a <strong>Képviselő</strong> keresés vevők listáját tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="f395a-275"><strong>Customer</strong> – The <strong>Representative</strong> lookup contains a list of customers.</span></span> <span data-ttu-id="f395a-276">Vevők beállításához lépjen a <strong>Kinnlevőségek</strong> &gt; <strong>Vevők</strong> elemre.</span><span class="sxs-lookup"><span data-stu-id="f395a-276">To set up customers, go to <strong>Accounts receivable</strong> &gt; <strong>Customers</strong>.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f395a-277">Jellegzetes</span><span class="sxs-lookup"><span data-stu-id="f395a-277">Representative</span></span></td>
<td><span data-ttu-id="f395a-278">Válasszon ki egy a <strong>Képviselő típusa</strong> mezőben megadott típusú képviselőt.</span><span class="sxs-lookup"><span data-stu-id="f395a-278">Select a representative of the type that you specified in the <strong>Representative type</strong> field.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f395a-279">A személy neve</span><span class="sxs-lookup"><span data-stu-id="f395a-279">Name of person</span></span></td>
<td><span data-ttu-id="f395a-280">Ezt a mezőt a rendszer automatikusan kitölti az <strong>Ellenszámla</strong> és a <strong>Képviselő</strong> mezők alapján.</span><span class="sxs-lookup"><span data-stu-id="f395a-280">This field is filled in automatically, based on the <strong>Offset account</strong> and <strong>Representative</strong> fields.</span></span> <span data-ttu-id="f395a-281">A pénztárbizonylatok nyomtatása űrlap tükrözni fogja ezt az információt.</span><span class="sxs-lookup"><span data-stu-id="f395a-281">The printing form for cash slips will reflect this information.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f395a-282">Személyi igazolvány</span><span class="sxs-lookup"><span data-stu-id="f395a-282">Identity card</span></span></td>
<td><span data-ttu-id="f395a-283">Ezt a mezőt a rendszer automatikusan kitölti a kapcsolattartó (képviselő) személyazonosító igazolványának adatai alapján.</span><span class="sxs-lookup"><span data-stu-id="f395a-283">This field is filled in automatically, based on the identity card data for the contact person (representative).</span></span> <span data-ttu-id="f395a-284">Ha az <strong>Ellenszámla típusa</strong> mező értéke <strong>Előleg jogosultja</strong> és az <strong>Ellenszámla</strong> mező értéke egy alkalmazotti szám, készpénzbe- és kifizetések végezhetők az alkalmazott részére vagy részéről.</span><span class="sxs-lookup"><span data-stu-id="f395a-284">If the <strong>Offset account type</strong> field is set to <strong>Advance holder</strong>, and the <strong>Offset account</strong> field is set to an employee number, cash receipts or expenditures can be done from or to the employee.</span></span> <span data-ttu-id="f395a-285">Ebben az esetben a <strong>Személyi igazolvány</strong> mező ki van töltve automatikusan az <strong>Alkalmazott</strong> táblában szereplő személyiigazolvány-adatok alapján (<strong>Személyzeti számvitel</strong> &gt; <strong>Alkalmazott tábla</strong>).</span><span class="sxs-lookup"><span data-stu-id="f395a-285">In this case the <strong>Identity card</strong> field is filled in automatically by using data for the identity card from the <strong>Employee</strong> table (<strong>Staff accounting</strong> &gt; <strong>Employee table</strong>).</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f395a-286">Cél</span><span class="sxs-lookup"><span data-stu-id="f395a-286">Purpose</span></span></td>
<td><span data-ttu-id="f395a-287">A <strong>Cél</strong> táblában adjon meg egy vagy több rendeltetésihely-kódot a tranzakció összegéhez.</span><span class="sxs-lookup"><span data-stu-id="f395a-287">In the <strong>Purpose</strong> table, define one or more destination codes for the transaction amount.</span></span> <span data-ttu-id="f395a-288">Válasszon ki egy rendeltetési kódot a <strong>Cél</strong> mezőben, és írja be a magyarázatot a <strong>Tranzakció szövege</strong> mezőben.</span><span class="sxs-lookup"><span data-stu-id="f395a-288">Select a destination code in the <strong>Purpose</strong> field, and enter an explanation in the <strong>Transaction text</strong> field.</span></span> <span data-ttu-id="f395a-289">Az <strong>Összeg</strong> mezőben adjon meg egy összeget a tranzakció pénznemében.</span><span class="sxs-lookup"><span data-stu-id="f395a-289">In the <strong>Amount</strong> field, enter an amount in the transaction currency.</span></span> <span data-ttu-id="f395a-290">A <strong>Százalék</strong> mező százalékos formában a célösszeg és a tranzakció teljes összegének arányát mutatja.</span><span class="sxs-lookup"><span data-stu-id="f395a-290">The <strong>Percent</strong> field shows, as a percentage, the ratio of the destination amount to the total transaction amount.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f395a-291">Maradvány</span><span class="sxs-lookup"><span data-stu-id="f395a-291">Remainder</span></span></td>
<td><span data-ttu-id="f395a-292">A fennmaradó, kiszámított összeg.</span><span class="sxs-lookup"><span data-stu-id="f395a-292">The remaining amount that is calculated.</span></span> <span data-ttu-id="f395a-293">Fontos megjegyezni, hogy a teljes tranzakció összegét rendeltetésihely-kódokhoz kell rendelni.</span><span class="sxs-lookup"><span data-stu-id="f395a-293">Note that the whole transaction amount must be assigned to destination codes.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f395a-294">Hivatalnokok</span><span class="sxs-lookup"><span data-stu-id="f395a-294">Officials</span></span></td>
<td><span data-ttu-id="f395a-295">A <strong>Hivatalnokok</strong> lapon adja a felelős személyek nevét és beosztását: igazgató, vezető könyvelő és pénztáros.</span><span class="sxs-lookup"><span data-stu-id="f395a-295">On the <strong>Officials</strong> tab, specify the names and titles for responsible persons: Director, Chief accountant, and Cashier.</span></span> <span data-ttu-id="f395a-296">A <strong>Pozíció</strong> értékeit a hivatalnokok beállítása határozza meg a <strong>Hivatalnokok</strong> oldal <strong>Általános</strong> és <strong>Főkönyv</strong> lapjain (<strong>Alap</strong> &gt; <strong>Beállítás</strong> &gt; <strong>Kapcsolattartók</strong> &gt; <strong>Hivatalnokok</strong>).</span><span class="sxs-lookup"><span data-stu-id="f395a-296">The <strong>Position</strong> values are determined by the setup of officials on the <strong>General</strong> and <strong>Ledger</strong> tabs of the <strong>Officials</strong> page (<strong>Basic</strong> &gt; <strong>Setup</strong> &gt; <strong>Contacts</strong> &gt; <strong>Officials</strong>).</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f395a-297">Előleg</span><span class="sxs-lookup"><span data-stu-id="f395a-297">Prepayment</span></span></td>
<td><span data-ttu-id="f395a-298">Jelölje be ezt a jelölőnégyzetet, ha a tranzakció előleg.</span><span class="sxs-lookup"><span data-stu-id="f395a-298">Select this check box if the transaction is a prepayment.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f395a-299">Feladási profil</span><span class="sxs-lookup"><span data-stu-id="f395a-299">Posting profile</span></span></td>
<td><span data-ttu-id="f395a-300">Adja meg a készpénzszámla feladási profilját.</span><span class="sxs-lookup"><span data-stu-id="f395a-300">Enter the posting profile for the cash account.</span></span> <span data-ttu-id="f395a-301">Alapértelmezés szerint a rendszer a Készpénz- és bankkezelési paraméterek között megadott feladási profilt használja.</span><span class="sxs-lookup"><span data-stu-id="f395a-301">By default, the posting profile that is specified in the Cash and bank management parameters is used.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f395a-302">Ellenszámla feladási sablonja</span><span class="sxs-lookup"><span data-stu-id="f395a-302">Offset posting profile</span></span></td>
<td><span data-ttu-id="f395a-303">Adja meg a kiválasztott ellenszámla feladási profilját.</span><span class="sxs-lookup"><span data-stu-id="f395a-303">Enter the posting profile for the selected offset account.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f395a-304">Teljes összeg</span><span class="sxs-lookup"><span data-stu-id="f395a-304">Total amount</span></span></td>
<td><span data-ttu-id="f395a-305">A <strong>Teljes összeg</strong> mezőcsoportban a lap alján a <strong>Visszatérítés</strong> a mező mutatja a végösszeget, amely az aktuális naplóban megadott összes Bevételezési pénztárbizonylat alapján kerül kiszámításra, a <strong>Kifiz</strong> mező pedig az összes Bevételezési pénztárbizonylat végösszegét mutatja.</span><span class="sxs-lookup"><span data-stu-id="f395a-305">In the <strong>Total amount</strong> field group at the bottom of the page, the <strong>Reimb</strong> field shows the total that is calculated for all Cash reimbursement slips that are entered in the current journal, and the <strong>Disb</strong> field shows the total for all Cash disbursement slips.</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="f395a-306">A naplóbejegyzések ellenőrzéséhez a műveletpanelen kattintson az **Ellenőrzés** elemre.</span><span class="sxs-lookup"><span data-stu-id="f395a-306">To check journal entries, on the Action Pane, click **Validate**.</span></span>

## <a name="daily-cash-operations-via-a-general-journal"></a><span data-ttu-id="f395a-307">Napi készpénzműveletek Általános napló révén</span><span class="sxs-lookup"><span data-stu-id="f395a-307">Daily cash operations via a General journal</span></span>
<span data-ttu-id="f395a-308">Készpénztranzakció Általános naplón keresztüli létrehozásához lépjen a **Főkönyv** &gt; **Naplóbejegyzések** &gt; **Általános naplók** elemre, és hozzon létre egy új naplót.</span><span class="sxs-lookup"><span data-stu-id="f395a-308">To create a cash transaction via a General journal, go to **General ledger** &gt; **Journal entries** &gt; **General journals**, and create a new journal.</span></span> <span data-ttu-id="f395a-309">A Művelet panelen kattintson a **Sorok** elemre.</span><span class="sxs-lookup"><span data-stu-id="f395a-309">On the Action Pane, click **Lines**.</span></span> <span data-ttu-id="f395a-310">Adjon hozzá új sort, és írja be a következő adatokat.</span><span class="sxs-lookup"><span data-stu-id="f395a-310">Add a new line, and enter the following information.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f395a-311">Mező</span><span class="sxs-lookup"><span data-stu-id="f395a-311">Field</span></span></th>
<th><span data-ttu-id="f395a-312">Leírás</span><span class="sxs-lookup"><span data-stu-id="f395a-312">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="f395a-313">Dátum</span><span class="sxs-lookup"><span data-stu-id="f395a-313">Date</span></span></td>
<td><span data-ttu-id="f395a-314">Adja meg a tranzakció dátumát.</span><span class="sxs-lookup"><span data-stu-id="f395a-314">Enter the date of the transaction.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f395a-315">Számla típusa</span><span class="sxs-lookup"><span data-stu-id="f395a-315">Account type</span></span></td>
<td><span data-ttu-id="f395a-316">Válassza a <strong>Pénztár</strong> elemet.</span><span class="sxs-lookup"><span data-stu-id="f395a-316">Select <strong>Petty cash</strong>.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f395a-317">Könyvelési számla</span><span class="sxs-lookup"><span data-stu-id="f395a-317">Account</span></span></td>
<td><span data-ttu-id="f395a-318">Válassza ki a készpénzszámla számát.</span><span class="sxs-lookup"><span data-stu-id="f395a-318">Select the cash account number.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f395a-319">Tranzakció szövege</span><span class="sxs-lookup"><span data-stu-id="f395a-319">Transaction text</span></span></td>
<td><span data-ttu-id="f395a-320">Adjon meg magyarázó szöveget a tranzakcióhoz.</span><span class="sxs-lookup"><span data-stu-id="f395a-320">Enter explanatory text for the transaction.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f395a-321">Tartozik Követel</span><span class="sxs-lookup"><span data-stu-id="f395a-321">Debit Credit</span></span></td>
<td><span data-ttu-id="f395a-322">Adja meg a készpénzbizonylat összegét a következő mezők egyikében:</span><span class="sxs-lookup"><span data-stu-id="f395a-322">Enter cash document amount in one of these fields:</span></span>
<ul>
<li><span data-ttu-id="f395a-323"><strong>Tartozik</strong> – a mező használatával készpénzbevételek és a bevételezési pénztárbizonylatok rögzíthetők.</span><span class="sxs-lookup"><span data-stu-id="f395a-323"><strong>Debit</strong> – Use this field to register cash receipts and a Cash reimbursement slip.</span></span></li>
<li><span data-ttu-id="f395a-324"><strong>Követel</strong> – a mező használatával készpénzkiadások és a készpénz-kifizetési bizonylatok rögzíthetők.</span><span class="sxs-lookup"><span data-stu-id="f395a-324"><strong>Credit</strong> – Use this field to register cash expenditures and a Cash disbursement slip.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f395a-325">Ellenszámla típusa Ellenszámla</span><span class="sxs-lookup"><span data-stu-id="f395a-325">Offset account type Offset account</span></span></td>
<td><span data-ttu-id="f395a-326">Válasszon ellenszámlatípust és ellenszámlaszámot.</span><span class="sxs-lookup"><span data-stu-id="f395a-326">Select an offset account type and offset account number.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f395a-327">Pénznem</span><span class="sxs-lookup"><span data-stu-id="f395a-327">Currency</span></span></td>
<td><span data-ttu-id="f395a-328">Válassza ki a tranzakció pénznemkódját.</span><span class="sxs-lookup"><span data-stu-id="f395a-328">Select the code for the transaction currency.</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="f395a-329">A **Számla** lapon adhatja meg a kijelölt számlához és ellenszámlához a feladási profilokat.</span><span class="sxs-lookup"><span data-stu-id="f395a-329">On the **Invoice** tab, you can specify posting profiles for the selected account and offset account.</span></span> <span data-ttu-id="f395a-330">Ha a regisztrált tranzakció egy előleg, jelölje be az **Előleg** jelölőnégyzetet a **Fizetés** lapon. A **Képviselő** mezőcsoportban töltse ki a mezőket a bizonylatnaplósorokban megadottaknak megfelelően; ezek nyomtatásnál bekerülnek a **Készpénz** jelentésbe.</span><span class="sxs-lookup"><span data-stu-id="f395a-330">If the registered transaction is a prepayment, select the **Prepayment** check box on the **Payment** tab. In the **Representative** field group, fill in the fields as you did for the Slip journal lines to print on the **Cash** report.</span></span> <span data-ttu-id="f395a-331">A naplóbejegyzések ellenőrzéséhez a műveletpanelen kattintson az **Ellenőrzés** elemre.</span><span class="sxs-lookup"><span data-stu-id="f395a-331">To check journal entries, on the Action Pane, click **Validate**.</span></span>

## <a name="cash-transaction-approval-and-posting"></a><span data-ttu-id="f395a-332">Készpénztranzakciók jóváhagyása és feladása</span><span class="sxs-lookup"><span data-stu-id="f395a-332">Cash transaction approval and posting</span></span>
<span data-ttu-id="f395a-333">Készpénztranzakciók esetén a következő állapotok alkalmazhatók: **Nincs**, **Visszaigazolva**, **Jóváhagyva** és **Elutasítva**.</span><span class="sxs-lookup"><span data-stu-id="f395a-333">For cash transactions, the following statuses can be applied: **None**, **Confirmed**, **Approved**, and **Rejected**.</span></span> <span data-ttu-id="f395a-334">A **Készpénz- és bankkezelés** &gt; **Beállítás** &gt; **Készpénz- és bankkezelési paraméterek** **Készpénz** lapjának **Jóváhagyás** gyorslapján szereplő **Jóváhagyási állapot használata** paraméter lehetővé teszi két további állapot aktiválását: **Visszaigazolva** és **Elutasítva**.</span><span class="sxs-lookup"><span data-stu-id="f395a-334">A **Use confirm status** parameter on the **Approval** FastTab of the **Cash** tab at **Cash and bank management** &gt; **Setup** &gt; **Cash and bank management parameters** lets you activate two additional statuses: **Confirmed** and **Rejected**.</span></span> <span data-ttu-id="f395a-335">Megerősítés akkor alkalmazható, ha a készpénzbizonylatok kiadására kerül sor, és a készpénzbefizetések vagy -kifizetések két alkalmazott: könyvelő és pénztáros között oszlanak meg.</span><span class="sxs-lookup"><span data-stu-id="f395a-335">Confirmation is appropriate when cash documents are issued, and cash receipts or expenditures are shared between two employees: accountant and cashier.</span></span> <span data-ttu-id="f395a-336">Az **Állapot visszaállítása** funkció az aktuális tranzakció állapotától függően változik.</span><span class="sxs-lookup"><span data-stu-id="f395a-336">The **Reset status** function changes the current transaction status.</span></span> <span data-ttu-id="f395a-337">A **Jóváhagyva** állapotból **Visszaigazolva**, a **Visszaigazolva** állapotból pedig **Nincs** lesz.</span><span class="sxs-lookup"><span data-stu-id="f395a-337">**Approved** becomes **Confirmed**, and **Confirmed** becomes **None**.</span></span> <span data-ttu-id="f395a-338">A pénztárnaplótételek szerkesztése csak akkor lehetséges, ha az állapot **Nincs**.</span><span class="sxs-lookup"><span data-stu-id="f395a-338">Cash journal entries can be edited only when the status is **None**.</span></span> <span data-ttu-id="f395a-339">A készpénzes tranzakciókat akkor lehet elutasítani, ha a tranzakció állapota **Visszaigazolva**.</span><span class="sxs-lookup"><span data-stu-id="f395a-339">Cash transactions can be rejected only if the transaction status is **Confirmed**.</span></span> <span data-ttu-id="f395a-340">Az elutasított készpénzbizonylatok szerepelnek a **Pénztárbizonylatok regisztrációs naplója** jelentésben, de nem jelennek meg a **Pénztárkönyv** jelentésben.</span><span class="sxs-lookup"><span data-stu-id="f395a-340">Rejected cash documents are included on the **Journal of registration of cash documents** report, but they aren't reflected on the **Cash book** report.</span></span> <span data-ttu-id="f395a-341">Tranzakció megerősítéséhez válassza ki a megfelelő bizonylatnaplósort, és kattintson a **Dokumentumok jóváhagyása** &gt; **Megerősítés** elemre.</span><span class="sxs-lookup"><span data-stu-id="f395a-341">To confirm a transaction, select the corresponding Slip journal line, and then click **Documents approval** &gt; **Confirm**.</span></span> <span data-ttu-id="f395a-342">Létrejön egy rendelésszám a megadott számsorozat alapján.</span><span class="sxs-lookup"><span data-stu-id="f395a-342">An order number is generated, based on the specified number sequence.</span></span> <span data-ttu-id="f395a-343">A tranzakció állapota **Visszaigazolva** értékre változik, és a naplósor többé nem szerkeszthető.</span><span class="sxs-lookup"><span data-stu-id="f395a-343">The transaction status is changed to **Confirmed**, and you can no longer edit the journal line.</span></span> <span data-ttu-id="f395a-344">A készpénzes számla egyenlege változatlan marad.</span><span class="sxs-lookup"><span data-stu-id="f395a-344">The cash account balance remains unchanged.</span></span> <span data-ttu-id="f395a-345">Készpénzbizonylat elutasításához kattintson a **Dokumentumok jóváhagyása** &gt; **Elutasítás** elemre.</span><span class="sxs-lookup"><span data-stu-id="f395a-345">To reject a cash document, click **Documents approval** &gt; **Reject**.</span></span> <span data-ttu-id="f395a-346">Ez a beállítás csak azon dokumentumoknál érhető el, amelyek állapota **Visszaigazolva**.</span><span class="sxs-lookup"><span data-stu-id="f395a-346">This option is available only for documents that have **Confirmed** status.</span></span> <span data-ttu-id="f395a-347">Tranzakció jóváhagyásához válassza ki a megfelelő bizonylatnaplósort, és kattintson a **Dokumentumok jóváhagyása** &gt; **Jóváhagyás** elemre.</span><span class="sxs-lookup"><span data-stu-id="f395a-347">To approve a transaction, select the corresponding Slip journal line, and then click **Documents approval** &gt; **Approve**.</span></span> <span data-ttu-id="f395a-348">A **Jóváhagyva** állapot azt jelzi, hogy a pénzalapok beérkezése vagy elküldése megtörtént.</span><span class="sxs-lookup"><span data-stu-id="f395a-348">The **Approved** status indicates that cash funds are received or expended.</span></span> <span data-ttu-id="f395a-349">A készpénzegyenleg módosul.</span><span class="sxs-lookup"><span data-stu-id="f395a-349">The cash balance is changed.</span></span> <span data-ttu-id="f395a-350">A készpénztranzakciót fel lehet adni.</span><span class="sxs-lookup"><span data-stu-id="f395a-350">The cash transaction can be posted.</span></span> <span data-ttu-id="f395a-351">**Jóváhagyva** állapot törléséhez és az állapot **Nincs** értékű alaphelyzetbe állításához kattintson a **Dokumentumok jóváhagyása** &gt; **Állapot visszaállítása** elemre.</span><span class="sxs-lookup"><span data-stu-id="f395a-351">To cancel an **Approved** status and reset the status to **None**, click **Documents approval** &gt; **Reset status**.</span></span> <span data-ttu-id="f395a-352">Csak jóváhagyott készpénztranzakciók adhatók fel.</span><span class="sxs-lookup"><span data-stu-id="f395a-352">Only approved cash transactions can be posted.</span></span> <span data-ttu-id="f395a-353">Napló feladásához kattintson a **Feladás** &gt; **Feladás** elemre.</span><span class="sxs-lookup"><span data-stu-id="f395a-353">To post a journal, click **Post** &gt; **Post**.</span></span>

## <a name="print-a-cash-order"></a><span data-ttu-id="f395a-354">Készpénzutalvány nyomtatása</span><span class="sxs-lookup"><span data-stu-id="f395a-354">Print a cash order</span></span>
<span data-ttu-id="f395a-355">Készpénzutalvány nyomtatásához válasszon bizonylatnaplósort, majd a műveletek panelen kattintson a **Nyomtatása** &gt; **Készpénzutalvány-jelentés** elemre.</span><span class="sxs-lookup"><span data-stu-id="f395a-355">To print a cash order, select a Slip journal line, and then, on the Action Pane, click **Print** &gt; **Cash order report**.</span></span> <span data-ttu-id="f395a-356">Létrejön egy nyomtatási űrlap bevételezési pénztárbizonylathoz vagy készpénzkifizetési bizonylathoz, attól függően, hogy az összeg a **Tartozik** vagy a **Követel** mezőben szerepel-e a a kijelölt sornál:</span><span class="sxs-lookup"><span data-stu-id="f395a-356">The system generates a printing form for either a Cash reimbursement slip or a Cash disbursement slip, depending on whether an amount is entered in the **Debit** field the or **Credit** field for the selected line:</span></span>

-   <span data-ttu-id="f395a-357">Ha az összeg a **Tartozik** mezőben szerepel: bevételezési pénztárbizonylat jön létre</span><span class="sxs-lookup"><span data-stu-id="f395a-357">If there is an amount in the **Debit** field: Cash reimbursement slip</span></span>
-   <span data-ttu-id="f395a-358">Ha az összeg a **Követel** mezőben szerepel: készpénzkifizetési bizonylat jön létre</span><span class="sxs-lookup"><span data-stu-id="f395a-358">If there is an amount in the **Credit** field: Cash disbursement slip</span></span>

<span data-ttu-id="f395a-359">Azok a bizonylatnaplósorok nyomtathatók, amelyek állapota **Visszaigazolva**, **Jóváhagyva** vagy **Elutasítva**.</span><span class="sxs-lookup"><span data-stu-id="f395a-359">Slip journal lines that have **Confirmed**, **Approved**, or **Rejected** status can be printed.</span></span> <span data-ttu-id="f395a-360">A készpénzbefizetési utalványok a **Készpénz- és bankkezelés** &gt; **Lekérdezések és jelentések** &gt; **Készpénzutalvány** menüpontban is kinyomtathatók.</span><span class="sxs-lookup"><span data-stu-id="f395a-360">You can also print cash order documents at **Cash and bank management** &gt; **Inquires and reports** &gt; **Cash order**.</span></span>

## <a name="periodic-tasks"></a><span data-ttu-id="f395a-361">Időszakos feladatok</span><span class="sxs-lookup"><span data-stu-id="f395a-361">Periodic tasks</span></span>
<span data-ttu-id="f395a-362">A következő feladatok a **Készpénz- és bankkezelés** &gt; **Időszakos feladatok** pontban hajthatók végre.</span><span class="sxs-lookup"><span data-stu-id="f395a-362">The following tasks can be performed at **Cash and bank management** &gt; **Periodic tasks**.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f395a-363">Időszakos feladat</span><span class="sxs-lookup"><span data-stu-id="f395a-363">Periodic task</span></span></th>
<th><span data-ttu-id="f395a-364">Leírás</span><span class="sxs-lookup"><span data-stu-id="f395a-364">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="f395a-365">Egyenlegkorlát ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="f395a-365">Check balance limit</span></span></td>
<td><span data-ttu-id="f395a-366">Ellenőrizze a kiválasztott készpénzszámla megadott napi egyenlegét, és jelenítse meg az eredményt egy információs üzenetben.</span><span class="sxs-lookup"><span data-stu-id="f395a-366">Check the balance for the selected cash account on the specified date, and show the result in an information message.</span></span> <span data-ttu-id="f395a-367">Az egyenleg kiszámításánál csak a jóváhagyott tranzakciók számítanak.</span><span class="sxs-lookup"><span data-stu-id="f395a-367">Only approved transactions can be counted in the balance calculation.</span></span> <span data-ttu-id="f395a-368">A <strong>Bérlista számára</strong> megjelöléssel ellátott tranzakciók nem számítanak bele az egyenlegbe.</span><span class="sxs-lookup"><span data-stu-id="f395a-368">Transactions that are marked as <strong>For payroll</strong> aren't considered.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f395a-369">Készpénzegyenleg újraszámítása</span><span class="sxs-lookup"><span data-stu-id="f395a-369">Cash balance recalculation</span></span></td>
<td><span data-ttu-id="f395a-370">E feladat segítségével győződjön meg arról, hogy a készpénzes számlákhoz tartozó főkönyvi egyenlegek és a készpénzegyenleg egyeznek.</span><span class="sxs-lookup"><span data-stu-id="f395a-370">Use this task to make sure that the ledger balances for cash accounts fit the cash balance.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f395a-371">Készpénzjelentés létrehozása (csak Lengyelország)</span><span class="sxs-lookup"><span data-stu-id="f395a-371">Cash report creation (for Poland only)</span></span></td>
<td><span data-ttu-id="f395a-372"><strong>Készpénzes</strong> jelentés létrehozása.</span><span class="sxs-lookup"><span data-stu-id="f395a-372">Create a <strong>Cash</strong> report.</span></span> <span data-ttu-id="f395a-373">A <strong>Készpénz</strong> jelentés száma a <strong>Jelentés számához</strong> beállított számsorozat alapján jön létre.</span><span class="sxs-lookup"><span data-stu-id="f395a-373">The <strong>Cash</strong> report number is generated based on the number sequence that is set up for <strong>Report number</strong>.</span></span> <span data-ttu-id="f395a-374">A feladat párbeszédablakának <strong>Záró dátum</strong> mezőjében adja meg az utolsó dátumot, amelyhez a készpénztranzakciókat figyelembe kell venni a <strong>Készpénz</strong> jelentéshez.</span><span class="sxs-lookup"><span data-stu-id="f395a-374">In the dialog box for the task, in the <strong>To date</strong>, specify the last date for which cash transactions should be counted for the <strong>Cash</strong> report.</span></span> <span data-ttu-id="f395a-375">Használja a <strong>Szűrő</strong> funkciót a <strong>Belefoglalandó rekordok</strong> lapon, és adjon meg további feltételeket a készpénzes tranzakciók körének korlátozására.</span><span class="sxs-lookup"><span data-stu-id="f395a-375">Use the <strong>Filter</strong> function on the <strong>Records to include</strong> tab to specify additional criteria to limit the selection of cash transactions.</span></span> <span data-ttu-id="f395a-376">Ezek a kritériumok lehetnek készpénzes számlaszámok és pénznemkódok.</span><span class="sxs-lookup"><span data-stu-id="f395a-376">These criteria can include cash account numbers and currency codes.</span></span> <span data-ttu-id="f395a-377">A <strong>Létrehozó</strong> mezőben jelölje ki a felhasználót, aki felelős a jelentés létrehozásáért.</span><span class="sxs-lookup"><span data-stu-id="f395a-377">In the <strong>Create by</strong> field, select the user who is responsible for report creation.</span></span> <span data-ttu-id="f395a-378">A létrejött <strong>Készpénz</strong> jelentés megtekintéséhez használja a <strong>Készpénzjelentések</strong> gombot a <strong>Készpénzszámlák</strong> lapon.</span><span class="sxs-lookup"><span data-stu-id="f395a-378">To view the <strong>Cash</strong> report that is created, use the <strong>Cash reports</strong> button on the <strong>Cash accounts</strong> page.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f395a-379">Készpénz - árfolyamkorrekció FIFO és LIFO (csak Lengyelország)</span><span class="sxs-lookup"><span data-stu-id="f395a-379">Cash - Exchange adjustment FIFO and LIFO (for Poland only)</span></span></td>
<td><span data-ttu-id="f395a-380">Kiszámítja az árfolyam-korrekciót a lengyel szabványoknak megfelelően.</span><span class="sxs-lookup"><span data-stu-id="f395a-380">Calculate the exchange adjustment per Polish standards.</span></span> <span data-ttu-id="f395a-381">Használja a <strong>Szűrő</strong> funkciót a <strong>Belefoglalandó rekordok</strong> lapon, és adja meg a készpénzszámlát, amelyen a feladat le fog futni.</span><span class="sxs-lookup"><span data-stu-id="f395a-381">Use the <strong>Filter</strong> function on the <strong>Records to include</strong> tab to specify the cash account to run the task for.</span></span> <span data-ttu-id="f395a-382">Az összes nyitott időszak árfolyam-korrekciós különbözetének teljes újraszámításához jelölje be az <strong>Újraszámítás</strong> jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="f395a-382">Select the <strong>Recalculation</strong> check box to do a full recalculation of the exchange adjustment difference for all open periods.</span></span> <span data-ttu-id="f395a-383">Az árfolyam-korrekció kiszámítása a következőképpen történik az elsőként be, elsőként ki (FIFO) és az utolsóként be, elsőként ki (LIFO) módszerek alkalmazásánál:</span><span class="sxs-lookup"><span data-stu-id="f395a-383">Here is how the exchange adjustment is calculated when the first in, first out (FIFO) and last in, first out (LIFO) methods are used:</span></span>
<ul>
<li><span data-ttu-id="f395a-384"><strong>FIFO módszer</strong> – a rendszer keres egy kiadási tranzakciót, amelynek a tranzakciódátuma korábbi (kisebb rendelési számú), és rendezi egy olyan bevételezési tranzakcióval, amelynek korábbi a tranzakciódátuma (kisebb rendelési számú).</span><span class="sxs-lookup"><span data-stu-id="f395a-384"><strong>FIFO method</strong> – The system searches for an expenditure transaction that has an earlier transaction date (smaller order number) and settles it with a receipt transaction that has an earlier transaction date (smaller order number).</span></span></li>
<li><span data-ttu-id="f395a-385"><strong>LIFO módszer</strong> – a rendszer keres egy kiadási tranzakciót, amelynek a tranzakciódátuma későbbi (nagyobb rendelési számú), és rendezi egy olyan bevételezési tranzakcióval, amelynek későbbi a tranzakciódátuma (nagyobb rendelési számú).</span><span class="sxs-lookup"><span data-stu-id="f395a-385"><strong>LIFO method</strong> – The system searches for an expenditure transaction that has a later transaction date (larger order number) and settles it with a receipt transaction that has a later transaction date (larger order number).</span></span></li>
</ul>
<span data-ttu-id="f395a-386">A kiegyenlített összeg tükröződik a <strong>Kiegyenlített összeg pénzneme</strong> mezőben a <strong>Készpénztranzakció</strong> lapon.</span><span class="sxs-lookup"><span data-stu-id="f395a-386">The settled amount is reflected in the <strong>Settled currency</strong> field on the <strong>Cash transaction</strong> page.</span></span> <span data-ttu-id="f395a-387">Árfolyam-korrekciós különbözet esetén az összeg megjelenik az <strong>Árfolyam-korrekció összege</strong> mezőben, és létrejön egy <strong>Árfolyamkülönbség</strong> bizonylattípusú tranzakció a <strong>Készpénztranzakció</strong> táblában.</span><span class="sxs-lookup"><span data-stu-id="f395a-387">If there is an exchange adjustment difference, the amount is reflected in the <strong>Exchange adjustment amount</strong> field, and a transaction of the <strong>Exchange rate difference</strong> document type is generated in the <strong>Cash transaction</strong> table.</span></span> <span data-ttu-id="f395a-388">A nyereség/veszteség tranzakciók főkönyvi számlái a <strong>Pénznem</strong> táblában vannak beállítva (<strong>Árfolyam pénzügyi nyeresége</strong> és <strong>Árfolyam pénzügyi vesztesége</strong>).</span><span class="sxs-lookup"><span data-stu-id="f395a-388">Ledger accounts for profit/loss transactions are set in the <strong>Currency</strong> table (<strong>Exchange rate financial profit</strong> and <strong>Exchange rate financial loss</strong>).</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f395a-389">Devizaátértékelés – készpénz</span><span class="sxs-lookup"><span data-stu-id="f395a-389">Foreign currency revaluation - Cash</span></span></td>
<td><span data-ttu-id="f395a-390">Ha a műveletek külföldi pénznemben vannak megadva, használja ezt a feladatot annak érdekében, hogy megfelelő egyenleg álljon rendelkezésre az alapértelmezett pénznemben a jelentési napon.</span><span class="sxs-lookup"><span data-stu-id="f395a-390">Use this task to have an adequate balance in the default currency on the reporting date when the operations are entered in foreign currencies.</span></span> <span data-ttu-id="f395a-391">Használja a <strong>Szűrő</strong> funkciót a <strong>Belefoglalandó rekordok</strong> lapon, és adja meg a készpénzszámlát, amelyen a feladat le fog futni.</span><span class="sxs-lookup"><span data-stu-id="f395a-391">Use the <strong>Filter</strong> function on the <strong>Records to include</strong> tab to specify the cash account to run the task for.</span></span> <span data-ttu-id="f395a-392">A feladat párbeszédpanelén használja a <strong>Kezdő pénznem</strong> és a <strong>Célpénznem</strong> mezőkbenet a tranzakció pénznemeinek megadásához.</span><span class="sxs-lookup"><span data-stu-id="f395a-392">In the dialog box for the task, use the <strong>From currency</strong> and <strong>To Currency</strong> fields to specify transaction currencies.</span></span> <span data-ttu-id="f395a-393">A rendszer összehasonlítja a konvertált pénznemben az összeget az alapértelmezett pénznemben megadott összeggel az adott napi átváltási árfolyam használatával.</span><span class="sxs-lookup"><span data-stu-id="f395a-393">The system compares the amount in the currency that was converted by using exchange rate on the selected date with the amount in the default currency.</span></span> <span data-ttu-id="f395a-394">A két összeg közötti különbség (a korábbi árfolyam-korrekció nélkül) a számított árfolyam-korrekció.</span><span class="sxs-lookup"><span data-stu-id="f395a-394">The difference between the two amounts (excluding the previous exchange adjustment) is the calculated exchange adjustment.</span></span> <span data-ttu-id="f395a-395">Ez a feladat <strong>Árfolyam-korrekció</strong> típusú, jóváhagyott készpénztranzakciót hoz létre.</span><span class="sxs-lookup"><span data-stu-id="f395a-395">This task creates an approved cash transaction of the <strong>Exchange adjustment</strong> type.</span></span> <span data-ttu-id="f395a-396">A főkönyvi tranzakció a készpénzes főkönyvi számla és a <strong>Nem realizált nyereség</strong> vagy <strong>Nem realizált veszteség</strong> formájában a <strong>Pénznem</strong> táblában megadott főkönyvi számla segítségével jön létre.</span><span class="sxs-lookup"><span data-stu-id="f395a-396">The ledger transaction is formed by using the ledger account for cash and the ledger account that is specified in <strong>Unrealized profit</strong> or <strong>Unrealized loss</strong> in the <strong>Currency</strong> table.</span></span></td>
</tr>
</tbody>
</table>

## <a name="inquiries-and-reports"></a><span data-ttu-id="f395a-397">Lekérdezések és jelentések</span><span class="sxs-lookup"><span data-stu-id="f395a-397">Inquiries and reports</span></span>
| <span data-ttu-id="f395a-398">Lekérdezés vagy jelentés</span><span class="sxs-lookup"><span data-stu-id="f395a-398">Inquiry or report</span></span>                             | <span data-ttu-id="f395a-399">Leírás</span><span class="sxs-lookup"><span data-stu-id="f395a-399">Description</span></span>                                                                                                                                                                                                                     |
|-----------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="f395a-400">Készpénztranzakciók nézete</span><span class="sxs-lookup"><span data-stu-id="f395a-400">Cash transactions view</span></span>                        | <span data-ttu-id="f395a-401">Bizonylatnaplósornál használja a **Lekérdezések** gombot a műveletpanelen a főkönyvi tranzakciók, a készpénzegyenleg és más információk megtekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="f395a-401">For a Slip journal line, use the **Inquiries** button on the Action Pane to view ledger transactions, the cash balance, and other information.</span></span>                                                                                  |
| <span data-ttu-id="f395a-402">Készpénztranzakció</span><span class="sxs-lookup"><span data-stu-id="f395a-402">Cash transaction</span></span>                              | <span data-ttu-id="f395a-403">Készpénzes tranzakciók megtekintéséhez lépjen a **Készpénz- és bankkezelés** &gt; **Lekérdezések és jelentések** &gt; **Készpénztranzakciók** elemre.</span><span class="sxs-lookup"><span data-stu-id="f395a-403">Go to **Cash and bank management** &gt; **Inquiries and reports** &gt; **Cash transactions** to view cash transactions.</span></span> <span data-ttu-id="f395a-404">Használja a **Szűrő** funkciót, és adjon meg további feltételeket a készpénzes tranzakciók körének korlátozására.</span><span class="sxs-lookup"><span data-stu-id="f395a-404">Use the **Filter** function to specify additional criteria to limit the selection of cash transactions.</span></span> |
| <span data-ttu-id="f395a-405">Regisztrálási napló (Észtország, Oroszország)</span><span class="sxs-lookup"><span data-stu-id="f395a-405">Journal of registration (for Estonia, Russia)</span></span> | <span data-ttu-id="f395a-406">A **Készpénz- és bankkezelés** &gt; **Lekérdezések és jelentések** &gt; **Regisztrálási napló** pontban elérhető jelentés tükrözi az összes kiadott a bevételezési és készpénz-kifizetési bizonylatot.</span><span class="sxs-lookup"><span data-stu-id="f395a-406">The report at **Cash and bank management** &gt; **Inquiries and reports** &gt; **Journal of registration** reflects all cash reimbursement and cash disbursement slips that have been issued.</span></span>                                   |
| <span data-ttu-id="f395a-407">Pénztárkönyv (Lettország, Litvánia, Oroszország)</span><span class="sxs-lookup"><span data-stu-id="f395a-407">Cash book (for Latvia, Lithuania, Russia)</span></span>     | <span data-ttu-id="f395a-408">A **Készpénz- és bankkezelés** &gt; **Lekérdezések és jelentések** &gt; **Pénztárkönyvi jelentés** a tényleges készpénzmozgásokat tükrözi (bevételek és kiadások).</span><span class="sxs-lookup"><span data-stu-id="f395a-408">The report at **Cash and bank management** &gt; **Inquiries and reports** &gt; **Cash book report** reflects actual cash fund movements (receipts and expenditures).</span></span>                                                            |





