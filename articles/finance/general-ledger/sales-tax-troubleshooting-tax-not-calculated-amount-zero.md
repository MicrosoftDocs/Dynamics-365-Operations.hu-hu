---
title: Az adó nincs kiszámítva, vagy az adó összege nulla
description: Ez a témakör olyan hibaelhárítási információkat tartalmaz, amelyek segíthetnek abban az esetben, ha az adó összege 0 (nulla), vagy ha az adó nincs kiszámítva.
author: shtao
ms.date: 04/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: c398579a0a408e7f5625a3e801a967955c4b1e5b
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/11/2021
ms.locfileid: "6020115"
---
# <a name="tax-isnt-calculated-or-the-tax-amount-is-zero"></a><span data-ttu-id="47955-103">Az adó nincs kiszámítva, vagy az adó összege nulla</span><span class="sxs-lookup"><span data-stu-id="47955-103">Tax isn't calculated or the tax amount is zero</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="47955-104">Előfordulhat, hogy egy tranzakció sorösszege nem 0 (nulla), de vagy nincs kiszámítva adó, vagy a számított adóösszeg 0.</span><span class="sxs-lookup"><span data-stu-id="47955-104">A transaction might have a line amount that isn't 0 (zero), but either tax isn't calculated or the calculated tax amount is 0.</span></span> <span data-ttu-id="47955-105">A probléma elhárításához igény szerint kövesse az alábbi szakaszok lépéseit.</span><span class="sxs-lookup"><span data-stu-id="47955-105">To troubleshoot this issue, follow the steps in the following sections as required.</span></span>

## <a name="verify-that-tax-codes-are-correctly-selected-by-the-transaction"></a><span data-ttu-id="47955-106">Annak ellenőrzése, hogy a tranzakció helyesen választotta-e ki az adókódokat</span><span class="sxs-lookup"><span data-stu-id="47955-106">Verify that tax codes are correctly selected by the transaction</span></span>

<span data-ttu-id="47955-107">Ha a tranzakció nem a megfelelő adókódokat választja ki, vagy nem választ adókódokat, akkor az adók számítása nem történik meg.</span><span class="sxs-lookup"><span data-stu-id="47955-107">If the transaction doesn't select the correct tax codes, or if it doesn't select any tax codes, taxes won't be calculated on it.</span></span> <span data-ttu-id="47955-108">Kövesse az alábbi lépéseket annak ellenőrzéséhez, hogy a tranzakció helyesen választotta-e ki az adókódokat.</span><span class="sxs-lookup"><span data-stu-id="47955-108">Follow these steps to verify that tax codes are correctly selected by the transaction.</span></span> 

1. <span data-ttu-id="47955-109">A tranzakciósorban a **Sor részletei** gyorslapon a **Beállítás** lapon, az **Áfa** szakaszban ellenőrizze, hogy a megfelelő áfacsoportok vannak-e kiválasztva a **Cikk áfacsoportja** és az **Áfacsoport** mezőkben.</span><span class="sxs-lookup"><span data-stu-id="47955-109">On the transaction line, on the **Line details** FastTab, on the **Setup** tab, in the **Sales tax** section, verify that the correct tax groups are selected in the **Item sales tax group** and **Sales tax group** fields.</span></span> <span data-ttu-id="47955-110">Ha nem a megfelelő adócsoportok vannak kiválasztva, válassza ki őket.</span><span class="sxs-lookup"><span data-stu-id="47955-110">If the correct tax groups aren't selected, select them.</span></span>

    <span data-ttu-id="47955-111">[![Cikkáfacsoportok és Áfacsoportok mezők](./media/tax-not-calculated-tax-amount-zero-Picture1.png)](./media/tax-not-calculated-tax-amount-zero-Picture1.png)</span><span class="sxs-lookup"><span data-stu-id="47955-111">[![Item sales tax group and Sales tax group fields](./media/tax-not-calculated-tax-amount-zero-Picture1.png)](./media/tax-not-calculated-tax-amount-zero-Picture1.png)</span></span>

2. <span data-ttu-id="47955-112">Ugorjon az **Adó** \> **Közvetett adók** \> **Áfa** \> **Áfakódcsoportok** pontra.</span><span class="sxs-lookup"><span data-stu-id="47955-112">Go to **Tax** \> **Indirect taxes** \> **Sales tax** \> **Sales tax groups**.</span></span>
3. <span data-ttu-id="47955-113">Válassza ki a megfelelő áfacsoportot, majd a **Beállítás** gyorslapon jegyezze fel az áfakódot az **Áfakód** mezőben.</span><span class="sxs-lookup"><span data-stu-id="47955-113">Select the appropriate sales tax group, and then, on the **Setup** FastTab, make a note of the tax code in the **Sales tax code** field.</span></span>

    <span data-ttu-id="47955-114">[![Áfacsoportok lap](./media/tax-not-calculated-tax-amount-zero-Picture2.png)](./media/tax-not-calculated-tax-amount-zero-Picture2.png)</span><span class="sxs-lookup"><span data-stu-id="47955-114">[![Sales tax groups page](./media/tax-not-calculated-tax-amount-zero-Picture2.png)](./media/tax-not-calculated-tax-amount-zero-Picture2.png)</span></span>

4. <span data-ttu-id="47955-115">Ugorjon az **Adó** \> **Közvetett adók** \> **Áfa** \> **Áfacsoportok** pontra.</span><span class="sxs-lookup"><span data-stu-id="47955-115">Go to **Tax** \> **Indirect taxes** \> **Sales tax** \> **Item sales tax groups**.</span></span>
5. <span data-ttu-id="47955-116">Válassza ki a megfelelő cikkáfa-csoportot, majd a **Beállítás** gyorslapon ellenőrizze, hogy az **Áfakód mezőben** az áfakód megegyezik-e az áfacsoport áfakódjával.</span><span class="sxs-lookup"><span data-stu-id="47955-116">Select the appropriate item sales tax group, and then, on the **Setup** FastTab, verify that the tax code in the **Sales tax code** field matches the tax code of the sales tax group.</span></span>

    <span data-ttu-id="47955-117">[![Cikkáfa-csoportok lap](./media/tax-not-calculated-tax-amount-zero-Picture3.png)](./media/tax-not-calculated-tax-amount-zero-Picture3.png)</span><span class="sxs-lookup"><span data-stu-id="47955-117">[![Item sales tax groups page](./media/tax-not-calculated-tax-amount-zero-Picture3.png)](./media/tax-not-calculated-tax-amount-zero-Picture3.png)</span></span>

6. <span data-ttu-id="47955-118">Ha az adókódok nem egyeznek meg, frissítse valamelyik csoport áfakódját.</span><span class="sxs-lookup"><span data-stu-id="47955-118">If the tax codes don't match, update the sales tax code for one of the groups.</span></span>

## <a name="verify-that-the-selected-tax-codes-arent-exempt-and-that-they-have-the-correct-tax-rate-value"></a><span data-ttu-id="47955-119">Győződjön meg róla, hogy a kiválasztott áfakódok nem adómentesek, és helyes az adókulcsuk</span><span class="sxs-lookup"><span data-stu-id="47955-119">Verify that the selected tax codes aren't exempt and that they have the correct tax rate value</span></span>

<span data-ttu-id="47955-120">Ha az adókódok adómentesek, vagy ha az adókulcs 0 (nulla), az adószámítás eredménye 0 lesz.</span><span class="sxs-lookup"><span data-stu-id="47955-120">If the tax codes are exempt, or if the tax rate is 0 (zero), the tax calculation result will be 0.</span></span> <span data-ttu-id="47955-121">A következő lépések szerint adhatja meg, hogy a kiválasztott áfakódok adómentesek-e, és ellenőrizze, hogy a megfelelő adókulcs van-e alkalmazva rájuk.</span><span class="sxs-lookup"><span data-stu-id="47955-121">Follow these steps to determine whether the selected tax codes are exempt and to verify that the correct tax rate is applied to them.</span></span>

1. <span data-ttu-id="47955-122">Ugorjon az **Adó** \> **Közvetett adók** \> **Áfa** \> **Áfakódcsoportok** pontra.</span><span class="sxs-lookup"><span data-stu-id="47955-122">Go to **Tax** \> **Indirect taxes** \> **Sales tax** \> **Sales tax groups**.</span></span>
2. <span data-ttu-id="47955-123">Válassza ki a megfelelő áfacsoportot, majd a **Beállítás** gyorslistában ellenőrizze, hogy nincs-e beállítva a **Mentesség** jelölőnégyzet.</span><span class="sxs-lookup"><span data-stu-id="47955-123">Select the appropriate sales tax group, and then, on the **Setup** FastTab, verify that the **Exempt** check box is cleared.</span></span> <span data-ttu-id="47955-124">Ha be van jelölve, törölje.</span><span class="sxs-lookup"><span data-stu-id="47955-124">If it's selected, clear it.</span></span>

    <span data-ttu-id="47955-125">[![Mentesség jelölőnégyzet az Áfacsoportok lapon](./media/tax-not-calculated-tax-amount-zero-Picture4.png)](./media/tax-not-calculated-tax-amount-zero-Picture4.png)</span><span class="sxs-lookup"><span data-stu-id="47955-125">[![Exempt check box on the Sales tax groups page](./media/tax-not-calculated-tax-amount-zero-Picture4.png)](./media/tax-not-calculated-tax-amount-zero-Picture4.png)</span></span>

3. <span data-ttu-id="47955-126">Ugrás az **Adó** \> **Közvetett adók** \> **Áfa** \> **Áfakódok** pontra.</span><span class="sxs-lookup"><span data-stu-id="47955-126">Go to **Tax** \> **Indirect taxes** \> **Sales tax** \> **Sales tax codes**.</span></span>
4. <span data-ttu-id="47955-127">Válassza ki a megfelelő áfakódot, majd ellenőrizze, hogy az **Érték** mezőben megadott adókulcs nem 0 (nulla).</span><span class="sxs-lookup"><span data-stu-id="47955-127">Select the appropriate sales tax code, and then verify that the tax rate value in the **Value** field isn't 0 (zero).</span></span> <span data-ttu-id="47955-128">Ha 0, frissítse a mezőt úgy, hogy a megfelelő adókulcs legyen a mezőben.</span><span class="sxs-lookup"><span data-stu-id="47955-128">If it's 0, update the field so that it's set to the correct tax rate.</span></span>

    <span data-ttu-id="47955-129">[![Érték mező az Áfakód-értékek lapon](./media/tax-not-calculated-tax-amount-zero-Picture5.png)](./media/tax-not-calculated-tax-amount-zero-Picture5.png)</span><span class="sxs-lookup"><span data-stu-id="47955-129">[![Value field on the Sales tax code values page](./media/tax-not-calculated-tax-amount-zero-Picture5.png)](./media/tax-not-calculated-tax-amount-zero-Picture5.png)</span></span>

## <a name="determine-whether-zero-is-the-correct-tax-amount"></a><span data-ttu-id="47955-130">Annak meghatározása, hogy a nulla-e a helyes adóösszeg</span><span class="sxs-lookup"><span data-stu-id="47955-130">Determine whether zero is the correct tax amount</span></span>

<span data-ttu-id="47955-131">Bizonyos helyzetekben 0 (nulla) adóösszeg helyes.</span><span class="sxs-lookup"><span data-stu-id="47955-131">In some scenarios, a tax amount of 0 (zero) is correct.</span></span> <span data-ttu-id="47955-132">A következő lépések alapján határozza meg, hogy a 0 helyes adóösszeg-e a tranzakcióhoz.</span><span class="sxs-lookup"><span data-stu-id="47955-132">Follow these steps to determine whether 0 is the correct tax amount for your transaction.</span></span>

1. <span data-ttu-id="47955-133">Menjen a **Főkönyv** \> **Főkönyv beállítás** \> **Főkönyv paraméterei** pontra.</span><span class="sxs-lookup"><span data-stu-id="47955-133">Go to **General ledger** \> **Ledger setup** \> **General ledger parameters**.</span></span>
2. <span data-ttu-id="47955-134">Az **Áfa** lap **Számítás módja** mezőjében ellenőrizze, hogy az **Összesen** ki van-e választva.</span><span class="sxs-lookup"><span data-stu-id="47955-134">On the **Sales tax** tab, in the **Calculation method** field, verify that **Total** is selected.</span></span>

    <span data-ttu-id="47955-135">[![Számítási módszer mező a Főkönyvi paraméterek oldalon](./media/tax-not-calculated-tax-amount-zero-Picture6.png)](./media/tax-not-calculated-tax-amount-zero-Picture6.png)</span><span class="sxs-lookup"><span data-stu-id="47955-135">[![Calculation method field on the General ledger parameters page](./media/tax-not-calculated-tax-amount-zero-Picture6.png)](./media/tax-not-calculated-tax-amount-zero-Picture6.png)</span></span>

3. <span data-ttu-id="47955-136">Ugrás az **Adó** \> **Közvetett adók** \> **Áfa** \> **Áfakódok** pontra.</span><span class="sxs-lookup"><span data-stu-id="47955-136">Go to **Tax** \> **Indirect taxes** \> **Sales tax** \> **Sales tax codes**.</span></span>
4. <span data-ttu-id="47955-137">Válassza ki a megfelelő áfakódot, válassza a **Számítás** \> **Számítás alapja** lehetőséget, és ellenőrizze, hogy a számítás alapja a **Számlaegyenleg nettó összege** vagy **Egyéb áfaösszegeket tartalmazó számlaösszeg**.</span><span class="sxs-lookup"><span data-stu-id="47955-137">Select the appropriate sales tax code, select **Calculation** \> **Marginal base**, and verify that the marginal base is set to **Net amount of invoice balance** or **Invoice total incl. other sales tax amounts**.</span></span> <span data-ttu-id="47955-138">A további tudnivalókat lásd a [Egyéb áfaösszegeket tartalmazó számlaösszeg](marginal-base-field.md#invoice-total-incl-other-sales-tax-amounts) részben.</span><span class="sxs-lookup"><span data-stu-id="47955-138">For more information, see the [Invoice total incl. other sales tax amounts](marginal-base-field.md#invoice-total-incl-other-sales-tax-amounts).</span></span>
5. <span data-ttu-id="47955-139">Ha a 2. és a 4. lépésben helyes értékek vannak beállítva, döntse el, hogy a tranzakció teljes összege 0-e (nulla).</span><span class="sxs-lookup"><span data-stu-id="47955-139">If the correct values are set in steps 2 and 4, determine whether the total amount of the transaction is 0 (zero).</span></span> <span data-ttu-id="47955-140">Ha a teljes összeg 0, a várt eredmény a 0 adóösszeg.</span><span class="sxs-lookup"><span data-stu-id="47955-140">If the total amount is 0, a tax amount of 0 is the expected result.</span></span> <span data-ttu-id="47955-141">Mivel az adószámítás a számlaegyenleg teljes összegére épül, és ez az összeg nem soronként van lebontva, az adószámítás után minden sorhoz 0 összeget rendel hozzá a program.</span><span class="sxs-lookup"><span data-stu-id="47955-141">Because the tax calculation is based on the total amount of the invoice balance, and that amount isn't line by line, the tax amount of 0 will be allocated to each line after the tax calculation.</span></span>

## <a name="determine-whether-customization-exists"></a><span data-ttu-id="47955-142">Annak meghatározása, hogy létezik-e testreszabás</span><span class="sxs-lookup"><span data-stu-id="47955-142">Determine whether customization exists</span></span>

<span data-ttu-id="47955-143">Ha az előző szakaszokban már befejezte a lépéseket, de nem találta meg a problémát, határozza meg, hogy van-e testreszabás.</span><span class="sxs-lookup"><span data-stu-id="47955-143">If you've completed the steps in the previous sections but have found no issue, determine whether customization exists.</span></span> <span data-ttu-id="47955-144">Ha nem létezik testreszabás, hozzon létre egy Microsoft szolgáltatáskérést további segítségért.</span><span class="sxs-lookup"><span data-stu-id="47955-144">If no customization exists, create a Microsoft service request for further support.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
