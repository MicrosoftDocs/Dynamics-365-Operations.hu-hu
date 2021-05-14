---
title: Az adó feladása nem a megfelelő főkönyvi számlára történik a bizonylaton
description: Ez a témakör olyan hibaelhárítási információkat tartalmaz, amelyek segítséget nyújtnak, amikor az adót nem a megfelelő főkönyvi számlára adják fel a bizonylaton.
author: qire
manager: beya
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 0404d71f0492e188ed5da62387bb90a336e69c5a
ms.sourcegitcommit: 57668404d61359b33e0c0280f2f7c4eb829b1ed2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/27/2021
ms.locfileid: "5947651"
---
# <a name="tax-is-posted-to-the-wrong-ledger-account-in-the-voucher"></a><span data-ttu-id="db235-103">Az adó feladása nem a megfelelő főkönyvi számlára történik a bizonylaton</span><span class="sxs-lookup"><span data-stu-id="db235-103">Tax is posted to the wrong ledger account in the voucher</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="db235-104">A feladás során lehetséges, hogy az adó feladása nem a megfelelő főkönyvi számlára történik a bizonylaton.</span><span class="sxs-lookup"><span data-stu-id="db235-104">During posting, tax might be posted to the wrong ledger account in the voucher.</span></span> <span data-ttu-id="db235-105">A probléma elhárításához igény szerint kövesse az alábbi szakaszok lépéseit.</span><span class="sxs-lookup"><span data-stu-id="db235-105">To troubleshoot this issue, follow the steps in the following sections as required.</span></span> <span data-ttu-id="db235-106">Az ebben a témakörben található példákban az értékesítési rendeléseket használjuk üzleti dokumentumként.</span><span class="sxs-lookup"><span data-stu-id="db235-106">The examples in this topic use a sales order as the business document.</span></span>

## <a name="find-the-tax-code-of-the-incorrectly-posted-tax-transaction"></a><span data-ttu-id="db235-107">Keresse meg helytelenül feladott adótranzakció adókódját</span><span class="sxs-lookup"><span data-stu-id="db235-107">Find the tax code of the incorrectly posted tax transaction</span></span>

1. <span data-ttu-id="db235-108">A **Bizonylattranzakciók** lapon válassza ki a tranzakciót, amellyel dolgozni szeretne, majd válassza a **Feladott áfa** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="db235-108">On the **Voucher transactions** page, select the transaction that you want to work with, and then select **Posted sales tax**.</span></span>

    <span data-ttu-id="db235-109">[![A Feladott áfa gomb a Bizonylattranzakciók lapon](./media/tax-posted-to-wrong-ledger-account-Picture1.png)](./media/tax-posted-to-wrong-ledger-account-Picture1.png)</span><span class="sxs-lookup"><span data-stu-id="db235-109">[![Posted sales tax button on the Voucher transactions page](./media/tax-posted-to-wrong-ledger-account-Picture1.png)](./media/tax-posted-to-wrong-ledger-account-Picture1.png)</span></span>

2. <span data-ttu-id="db235-110">Ellenőrizze az értéket az **Áfakód** mezőben.</span><span class="sxs-lookup"><span data-stu-id="db235-110">Review the value in the **Sales tax code** field.</span></span> <span data-ttu-id="db235-111">Ebben a példában ez az **Áfa 19**.</span><span class="sxs-lookup"><span data-stu-id="db235-111">In this example, it's **VAT 19**.</span></span>

    <span data-ttu-id="db235-112">[![Áfakód mező a Feladott áfa lapon](./media/tax-posted-to-wrong-ledger-account-Picture2.png)](./media/tax-posted-to-wrong-ledger-account-Picture2.png)</span><span class="sxs-lookup"><span data-stu-id="db235-112">[![Sales tax code field on the Posted sales tax page](./media/tax-posted-to-wrong-ledger-account-Picture2.png)](./media/tax-posted-to-wrong-ledger-account-Picture2.png)</span></span>

## <a name="check-the-ledger-posting-group-of-the-tax-code"></a><span data-ttu-id="db235-113">Az adókód főkönyvi feladási csoportjának ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="db235-113">Check the ledger posting group of the tax code</span></span>

1. <span data-ttu-id="db235-114">Ugrás az **Adó** \> **Közvetett adók** \> **Áfa** \> **Áfakódok** pontra.</span><span class="sxs-lookup"><span data-stu-id="db235-114">Go to **Tax** \> **Indirect taxes** \> **Sales tax** \> **Sales tax codes**.</span></span>
2. <span data-ttu-id="db235-115">Keresse meg és válassza ki az adókódot, majd ellenőrizze a **Főkönyvi feladási csoport** mezőben az értékét.</span><span class="sxs-lookup"><span data-stu-id="db235-115">Find and select the tax code, and then review the value in the **Ledger posting group** field.</span></span> <span data-ttu-id="db235-116">Ebben a példában ez az **Áfa**.</span><span class="sxs-lookup"><span data-stu-id="db235-116">In this example, it's **VAT**.</span></span>

    <span data-ttu-id="db235-117">[![Főkönyvi feladási csoport mező az Áfakódok oldalon](./media/tax-posted-to-wrong-ledger-account-Picture3.png)](./media/tax-posted-to-wrong-ledger-account-Picture3.png)</span><span class="sxs-lookup"><span data-stu-id="db235-117">[![Ledger posting group field on the Sales tax codes page](./media/tax-posted-to-wrong-ledger-account-Picture3.png)](./media/tax-posted-to-wrong-ledger-account-Picture3.png)</span></span>

3. <span data-ttu-id="db235-118">A **Főkönyvi feladási csoport** értéke egy hivatkozás.</span><span class="sxs-lookup"><span data-stu-id="db235-118">The value in the **Ledger posting group** field is a link.</span></span> <span data-ttu-id="db235-119">A csoport konfigurációjának részleteinek megtekintéséhez válassza ki a hivatkozást.</span><span class="sxs-lookup"><span data-stu-id="db235-119">To view the details of the group's configuration, select the link.</span></span> <span data-ttu-id="db235-120">Másik lehetőségként jelölje ki és tartsa lenyomva (vagy kattintson a jobb gombbal) a mezőben, majd válassza a **Részletek megtekintése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="db235-120">Alternatively, select and hold (or right-click) in the field, and then select **View details**.</span></span>

    <span data-ttu-id="db235-121">[![Részletek megtekintése parancs](./media/tax-posted-to-wrong-ledger-account-Picture4.png)](./media/tax-posted-to-wrong-ledger-account-Picture4.png)</span><span class="sxs-lookup"><span data-stu-id="db235-121">[![View details command](./media/tax-posted-to-wrong-ledger-account-Picture4.png)](./media/tax-posted-to-wrong-ledger-account-Picture4.png)</span></span>

4. <span data-ttu-id="db235-122">A **Fizetendő áfa** mezőben ellenőrizze a számlaszám helyességét, a tranzakció típusának megfelelően.</span><span class="sxs-lookup"><span data-stu-id="db235-122">In the **Sales tax payable** field, verify that the account number is correct, according to the transaction type.</span></span> <span data-ttu-id="db235-123">Ha nem, akkor válassza ki a megfelelő számlát, amelyre könyvelni kell.</span><span class="sxs-lookup"><span data-stu-id="db235-123">If it isn't, select the correct account to post to.</span></span> <span data-ttu-id="db235-124">Ebben a példában az értékesítési rendelés forgalmi adóját a 222200-ás számlára kell könyvelni.</span><span class="sxs-lookup"><span data-stu-id="db235-124">In this example, the sales tax of the sales order should be posted to sales tax payable account 222200.</span></span>

    <span data-ttu-id="db235-125">[![A főkönyvi feladási csoportok lapon található forgalmi adó kötelezettségek mezője](./media/tax-posted-to-wrong-ledger-account-Picture5.png)](./media/tax-posted-to-wrong-ledger-account-Picture5.png)</span><span class="sxs-lookup"><span data-stu-id="db235-125">[![Sales tax payable field on the Ledger posting groups page](./media/tax-posted-to-wrong-ledger-account-Picture5.png)](./media/tax-posted-to-wrong-ledger-account-Picture5.png)</span></span>

    <span data-ttu-id="db235-126">Az alábbi táblázat a **Főkönyvi feladási csoportok** lap egyes mezőiről nyújt információkat.</span><span class="sxs-lookup"><span data-stu-id="db235-126">The following table provides information about each field on the **Ledger posting groups** page.</span></span>

    | <span data-ttu-id="db235-127">Mező</span><span class="sxs-lookup"><span data-stu-id="db235-127">Field</span></span>                  | <span data-ttu-id="db235-128">Leírás</span><span class="sxs-lookup"><span data-stu-id="db235-128">Description</span></span> |
    |------------------------|-------------|
    | <span data-ttu-id="db235-129">Fizetendő áfa</span><span class="sxs-lookup"><span data-stu-id="db235-129">Sales tax payable</span></span>      | <span data-ttu-id="db235-130">Az adóhatóságnak fizetendő kimenő áfa fő számlája.</span><span class="sxs-lookup"><span data-stu-id="db235-130">The main account for outgoing sales taxes that are payable to the tax authority.</span></span> |
    | <span data-ttu-id="db235-131">Visszaigényelhető áfa</span><span class="sxs-lookup"><span data-stu-id="db235-131">Sales tax receivable</span></span>   | <span data-ttu-id="db235-132">Az adóhatóságtól kapott bejővő áfa fő számlája.</span><span class="sxs-lookup"><span data-stu-id="db235-132">The main account for incoming taxes that are received from the tax authority.</span></span> |
    | <span data-ttu-id="db235-133">Importadó költsége</span><span class="sxs-lookup"><span data-stu-id="db235-133">Use tax expense</span></span>        | <span data-ttu-id="db235-134">Az a fő számla, amely a levonható jövedelemadók feladására használatos, ha a szállítók az Európai Unió (EU) fordított áfafizetésű áruk és szolgáltatások adója (GST)/Harmonizált forgalmi adó (GST) részeként nem jelentkeznek az adóhatóságnak, illetve nem jelentik be az adóhatóságnak.</span><span class="sxs-lookup"><span data-stu-id="db235-134">The main account that is used to post deductible use taxes that vendors don't claim or report to the tax authority as part of European Union (EU) reverse charge Goods and Services Tax (GST)/Harmonized Sales Tax (HST).</span></span> <span data-ttu-id="db235-135">Az **Importadó** lehetőséget ki kell választani az áfakódhoz abból az áfacsoportból, amelyet a tranzakcióban használnak.</span><span class="sxs-lookup"><span data-stu-id="db235-135">**Use tax** must be selected for the sales tax code in the sales tax group that is used in the transaction.</span></span> <span data-ttu-id="db235-136">Ez a mező nem elérhető, csak ha a **Főkönyvi paraméterek** oldalon be van jelölve a **Áfaadózási szabályok alkalmazása** lehetőség.</span><span class="sxs-lookup"><span data-stu-id="db235-136">This field isn't available if **Apply sales tax taxation rules** is selected on the **General ledger parameters** page.</span></span> |
    | <span data-ttu-id="db235-137">Fizetendő importadó</span><span class="sxs-lookup"><span data-stu-id="db235-137">Use tax payable</span></span>        | <span data-ttu-id="db235-138">A fő számla, amely az adóhatóságok számára fizetendő bejövő importadók feladására használatos.</span><span class="sxs-lookup"><span data-stu-id="db235-138">The main account that is used to post incoming use taxes that are payable to tax authorities.</span></span> |
    | <span data-ttu-id="db235-139">Kiegyenlítési számla</span><span class="sxs-lookup"><span data-stu-id="db235-139">Settlement account</span></span>     | <span data-ttu-id="db235-140">A fő számlát, amelyet a főkönyvi számlák nettó egyenlegének feladására használatos, amelyek a **Fizetendő importadó** és a **Visszaigényelhető áfa** mezőkben vannak definiálva.</span><span class="sxs-lookup"><span data-stu-id="db235-140">The main account that is used to post the net balance of the ledger accounts that are specified in the **Use tax payable** and **Sales tax receivable** fields.</span></span> |
    | <span data-ttu-id="db235-141">Szállító készpénzfizetési engedménye</span><span class="sxs-lookup"><span data-stu-id="db235-141">Vendor cash discount</span></span>   | <span data-ttu-id="db235-142">A fő számla, amely készpénzfizetési engedmények feladására használatos az áfakódokhoz, amelyek ezzel a főkönyvi feladási csoporttal vannak társítva.</span><span class="sxs-lookup"><span data-stu-id="db235-142">The main account that is used to post a cash discount for sales tax codes that are associated with this ledger posting group.</span></span> |
    | <span data-ttu-id="db235-143">Vevő készpénzfizetési engedménye</span><span class="sxs-lookup"><span data-stu-id="db235-143">Customer case discount</span></span> | <span data-ttu-id="db235-144">A fő számla, amely készpénzfizetési engedmények feladására használatos az áfakódokhoz, amelyek ezzel a főkönyvi feladási csoporttal vannak társítva.</span><span class="sxs-lookup"><span data-stu-id="db235-144">The main account that is used to post a cash discount for sales tax codes that are associated with this ledger posting group.</span></span> |

    <span data-ttu-id="db235-145">További információkért lásd: [Főkönyvi feladási csoportok beállítása az áfához](tasks/set-up-ledger-posting-groups-sales-tax.md)</span><span class="sxs-lookup"><span data-stu-id="db235-145">For more information, see, [Set up Ledger posting groups for sales tax](tasks/set-up-ledger-posting-groups-sales-tax.md)</span></span>

## <a name="debug-in-code-to-check-ledger-dimensions"></a><span data-ttu-id="db235-146">Hibakeresés a kódban a főkönyvi dimenziók ellenőrzéshez</span><span class="sxs-lookup"><span data-stu-id="db235-146">Debug in code to check ledger dimensions</span></span>

<span data-ttu-id="db235-147">A kódban a feladási számlát a főkönyvi dimenzió határozza meg.</span><span class="sxs-lookup"><span data-stu-id="db235-147">In the code, the posting account is determined by the ledger dimension.</span></span> <span data-ttu-id="db235-148">A főkönyvi dimenzió menti az adatbázis egy számlájának rekordazonosítóját.</span><span class="sxs-lookup"><span data-stu-id="db235-148">The ledger dimension saves the record ID of an account in the database.</span></span>

1. <span data-ttu-id="db235-149">Értékesítési rendeléshez adjon meg egy töréspontot a **Tax::saveAndPost()** és **Tax::post()** metódusokhoz.</span><span class="sxs-lookup"><span data-stu-id="db235-149">For a sales order, add a breakpoint at the **Tax::saveAndPost()** and **Tax::post()** methods.</span></span> <span data-ttu-id="db235-150">Ügyeljen a **\_ledgerDimension** értékére.</span><span class="sxs-lookup"><span data-stu-id="db235-150">Pay attention to the value of **\_ledgerDimension**.</span></span>

    <span data-ttu-id="db235-151">[![Értékesítési rendelés kódminta törésponttal](./media/tax-posted-to-wrong-ledger-account-Picture6.png)](./media/tax-posted-to-wrong-ledger-account-Picture6.png)</span><span class="sxs-lookup"><span data-stu-id="db235-151">[![Sales order code sample that has a breakpoint](./media/tax-posted-to-wrong-ledger-account-Picture6.png)](./media/tax-posted-to-wrong-ledger-account-Picture6.png)</span></span>

    <span data-ttu-id="db235-152">Beszerzési rendelés esetén adjon meg egy töréspontot a **TaxPost::saveAndPost()** és **TaxPost::postToTaxTrans()** metódusoknál.</span><span class="sxs-lookup"><span data-stu-id="db235-152">For a purchase order, add a breakpoint at the **TaxPost::saveAndPost()** and **TaxPost::postToTaxTrans()** methods.</span></span> <span data-ttu-id="db235-153">Ügyeljen a **\_ledgerDimension** értékére.</span><span class="sxs-lookup"><span data-stu-id="db235-153">Pay attention to the value of **\_ledgerDimension**.</span></span>

    <span data-ttu-id="db235-154">[![Beszerzési rendelés kódminta törésponttal](./media/tax-posted-to-wrong-ledger-account-Picture7.png)](./media/tax-posted-to-wrong-ledger-account-Picture7.png)</span><span class="sxs-lookup"><span data-stu-id="db235-154">[![Purchase order code sample that has a breakpoint](./media/tax-posted-to-wrong-ledger-account-Picture7.png)](./media/tax-posted-to-wrong-ledger-account-Picture7.png)</span></span>

2. <span data-ttu-id="db235-155">A következő SQL-lekérdezés futtatásával keresse meg a számla megjelenítendő értékét az adatbázisban, a főkönyvi dimenzió által mentett rekordazonosító alapján.</span><span class="sxs-lookup"><span data-stu-id="db235-155">Run the following SQL query to find the display value of the account in the database, based on the record ID that is saved by the ledger dimension.</span></span>

    ```sql
    select * from DIMENSIONATTRIBUTEVALUECOMBINATION where recid={the value of _ledgerDimension}
    ```

    <span data-ttu-id="db235-156">[![A rekordazonosító megjelenő értéke](./media/tax-posted-to-wrong-ledger-account-Picture8.png)](./media/tax-posted-to-wrong-ledger-account-Picture8.png)</span><span class="sxs-lookup"><span data-stu-id="db235-156">[![Display value of the record ID](./media/tax-posted-to-wrong-ledger-account-Picture8.png)](./media/tax-posted-to-wrong-ledger-account-Picture8.png)</span></span>

3. <span data-ttu-id="db235-157">Vizsgálja meg a hívási vermet, és keresse meg **_ledgerDimension** érték hol van hozzárendelve.</span><span class="sxs-lookup"><span data-stu-id="db235-157">Examine the callstack to find where the **_ledgerDimension** value is assigned.</span></span> <span data-ttu-id="db235-158">Az érték általában a **TmpTaxWorkTrans** helyről származik.</span><span class="sxs-lookup"><span data-stu-id="db235-158">Usually, the value is from **TmpTaxWorkTrans**.</span></span> <span data-ttu-id="db235-159">Ebben az esetben egy töréspontot kell hozzáadnia a **TmpTaxWorkTrans::insert()** és **TmpTaxWorkTrans::update()** elemeknél, hogy megtudja hová van hozzárendelve az érték.</span><span class="sxs-lookup"><span data-stu-id="db235-159">In this case, you should add a breakpoint at **TmpTaxWorkTrans::insert()** and **TmpTaxWorkTrans::update()** to find where the value assigned.</span></span>

## <a name="determine-whether-customization-exists"></a><span data-ttu-id="db235-160">Annak meghatározása, hogy létezik-e testreszabás</span><span class="sxs-lookup"><span data-stu-id="db235-160">Determine whether customization exists</span></span>

<span data-ttu-id="db235-161">Ha az előző szakaszokban már befejezte a lépéseket, de nem találta meg a problémát, határozza meg, hogy van-e testreszabás.</span><span class="sxs-lookup"><span data-stu-id="db235-161">If you've completed the steps in the previous sections but have found no issue, determine whether customization exists.</span></span> <span data-ttu-id="db235-162">Ha nem létezik testreszabás, hozzon létre egy Microsoft szolgáltatáskérést további segítségért.</span><span class="sxs-lookup"><span data-stu-id="db235-162">If no customization exists, create a Microsoft service request for further support.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
