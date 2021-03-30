---
title: Forgalmi adókifizetések és kerekítési szabályok
description: Ez a cikk bemutatja az adóhatóságokon történő kerekítési szabályok működésének módját és az áfaegyenleg kerekítését az Áfa kiegyenlítése és feladása során.
author: ShylaThompson
manager: AnnBe
ms.date: 04/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxAuthority
audience: Application User
ms.reviewer: roschlom
ms.custom: 6134
ms.assetid: 7dcd3cf5-ebdf-4a9f-806c-1296c7da0331
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7be9be728a6515bb1fc1c9bc90938a3d33ea8da8
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5204954"
---
# <a name="sales-tax-payments-and-rounding-rules"></a><span data-ttu-id="666a5-103">Forgalmi adókifizetések és kerekítési szabályok</span><span class="sxs-lookup"><span data-stu-id="666a5-103">Sales tax payments and rounding rules</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="666a5-104">Ez a cikk bemutatja az adóhatóságokon történő kerekítési szabályok működésének módját és az áfaegyenleg kerekítését az Áfa kiegyenlítése és feladása során.</span><span class="sxs-lookup"><span data-stu-id="666a5-104">This article explains how the rounding rule setup on the Sales tax authorities works and rounding the sales tax balance during the Settle and post sales tax job.</span></span>

<span data-ttu-id="666a5-105">Rendszeres időközönként forgalmi adót be kell vallani és ki kell fizetni az adóhatóságoknak.</span><span class="sxs-lookup"><span data-stu-id="666a5-105">Periodically, sales tax needs to be reported and paid to tax authorities.</span></span> <span data-ttu-id="666a5-106">Ez a Forgalmi adó oldalon a forgalmi adó rendezése és feladása folyamat használatával végezhető el.</span><span class="sxs-lookup"><span data-stu-id="666a5-106">This can be done by running the settle and post sales tax process in the Sales tax page.</span></span> <span data-ttu-id="666a5-107">Az egy időszakra vonatkozó áfa az áfaszámlák alapján egyenlíthető ki, és az áfaegyenleg rákerül az áfakiegyenlítési számlára.</span><span class="sxs-lookup"><span data-stu-id="666a5-107">Sales tax for a period will be settled against the sales tax accounts and the sales tax balance will be posted to the Sales tax settlement account.</span></span> <span data-ttu-id="666a5-108">A forgalmi adóegyenleg, amely az ÁFA elszámolási számláján lesz könyvelve, kerekíthető az adóhatóságok elvárásai szerint, egy kerekítési szabály felállításával a Forgalmi adó lapon.</span><span class="sxs-lookup"><span data-stu-id="666a5-108">The sales tax balance, which is posted on the Sales tax settlement account, can be rounded as required by tax authorities by setting up a rounding rule on the Sales tax page.</span></span> 

<span data-ttu-id="666a5-109">A kerekítési különbség rákerül a Forgalmi adó kerekítési számlájára, amelyet a Számlák automatikus tranzakciókhoz mezőben, a Főkönyvben kell kiválasztani.</span><span class="sxs-lookup"><span data-stu-id="666a5-109">The rounding difference is posted to the Sales tax rounding account that is selected in the Accounts for automatic transactions field in the General ledger.</span></span>

<span data-ttu-id="666a5-110">Az alábbi példa bemutatja, hogyan működik az adóhatóságnak a kerekítési szabálya.</span><span class="sxs-lookup"><span data-stu-id="666a5-110">The below example illustrates how the rounding rule on Sales tax authority works.</span></span>

## <a name="examples"></a><span data-ttu-id="666a5-111">Példák</span><span class="sxs-lookup"><span data-stu-id="666a5-111">Examples</span></span>

<span data-ttu-id="666a5-112">Az időszak teljes áfája -98,765.43 követel egyenleget mutat.</span><span class="sxs-lookup"><span data-stu-id="666a5-112">The total sales tax for a period shows a credit balance of -98,765.43.</span></span> <span data-ttu-id="666a5-113">A jogi személy több áfát gyűjtött össze, mint amennyit kifizetett.</span><span class="sxs-lookup"><span data-stu-id="666a5-113">The legal entity collected more sales taxes than it paid.</span></span> <span data-ttu-id="666a5-114">Emiatt a jogi személy pénzzel tartozik az adóhatóságnak.</span><span class="sxs-lookup"><span data-stu-id="666a5-114">Therefore, the legal entity owes money to the tax authority.</span></span> 

<span data-ttu-id="666a5-115">A jogi személy olyan kerekítési módszert szeretne alkalmazni, amely az egyenleget a legközelebbi 1,00 egész összegre kerekíti.</span><span class="sxs-lookup"><span data-stu-id="666a5-115">The legal entity wants to use a rounding method that rounds the balance to the nearest 1.00.</span></span> <span data-ttu-id="666a5-116">Az áfa könyveléséért felelős felhasználó tehát a következőket teszi:</span><span class="sxs-lookup"><span data-stu-id="666a5-116">The user who is responsible for sales tax accounting performs the following steps.</span></span>

1. <span data-ttu-id="666a5-117">Kattintson az **Adó** > **Közvetett adók** > **Áfa** > **Adóhatóságok** pontra.</span><span class="sxs-lookup"><span data-stu-id="666a5-117">Click **Tax** > **Indirect taxes** > **Sales tax** > **Sales tax authorities**.</span></span>
2. <span data-ttu-id="666a5-118">Az **Általános** gyorslapon a **Kerekítési képernyő** mezőjében válassza a **Normál** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="666a5-118">On the **General** FastTab, in the **Rounding form** field, select **Normal**.</span></span>
3. <span data-ttu-id="666a5-119">A **Lekerekítés** mezőben ezt adja meg: 1,00.</span><span class="sxs-lookup"><span data-stu-id="666a5-119">In the **Round-off** field, enter 1.00.</span></span>
4. <span data-ttu-id="666a5-120">Amikor az áfa kifizetése esedékes az adóhatóság felé, nyissa meg az **Adó** > **Nyilatkozatok** > **Áfa** > **Áfa kiegyenlítése és feladása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="666a5-120">When it is time to pay the sales taxes to the tax authority, go to **Tax** > **Declarations** > **Sales tax** > **Settle and post sale tax**.</span></span> <span data-ttu-id="666a5-121">Az áfakiegyenlítési számlán látható az adókötelezettség, amely **98 765,43** és **98 765**-re lesz kerekítve.</span><span class="sxs-lookup"><span data-stu-id="666a5-121">On the sales tax settlement account, you can see that the tax liability amount of **98,765.43** is rounded to **98,765**.</span></span>

<span data-ttu-id="666a5-122">Az alábbi táblázat bemutatja, hogyan kerekítjük a 98 765,43 összeget az egyes kerekítési módok használatával az **Adóhatóságok lapon**, a **Kerekítési képernyő** mezőjében.</span><span class="sxs-lookup"><span data-stu-id="666a5-122">The following table shows how an amount of 98,765.43 is rounded by using each rounding method that is available in the **Rounding form** field in the **Sales tax authorities** page.</span></span>

> [!NOTE]                                                                                  
> <span data-ttu-id="666a5-123">Ha a kerekítési érték 0,00, akkor:</span><span class="sxs-lookup"><span data-stu-id="666a5-123">If the round-off value is set as 0.00, then:</span></span>
>
> - <span data-ttu-id="666a5-124">Normál kerekítés esetén a kerekítési mód ugyanaz, mint a **Lekerekítés = 0,01** esetében.</span><span class="sxs-lookup"><span data-stu-id="666a5-124">For normal rounding, the rounding behavior is the same as for **Round-off = 0.01**.</span></span>
> - <span data-ttu-id="666a5-125">A **Kerekítési képernyő beállításai**, **Lefelé**, **Felkerekítés** és **Saját előny** esetében a viselkedés ugyanaz, mint a **Lekerekítés = 1,00** esetében.</span><span class="sxs-lookup"><span data-stu-id="666a5-125">For the **Rounding form options**, **Downward**, **Rounding-up**, and **Own advantage**, the behavior is the same as for **Round-off = 1.00**.</span></span>

| <span data-ttu-id="666a5-126">Kerekítési képernyőopció</span><span class="sxs-lookup"><span data-stu-id="666a5-126">Rounding form option</span></span>                | <span data-ttu-id="666a5-127">Lekerekítési érték = 0,01</span><span class="sxs-lookup"><span data-stu-id="666a5-127">Round-off value = 0.01</span></span> | <span data-ttu-id="666a5-128">Lekerekítési érték = 0,10</span><span class="sxs-lookup"><span data-stu-id="666a5-128">Round-off value = 0.10</span></span> | <span data-ttu-id="666a5-129">Lekerekítési érték = 1,00</span><span class="sxs-lookup"><span data-stu-id="666a5-129">Round-off value = 1.00</span></span> | <span data-ttu-id="666a5-130">Lekerekítési érték = 100,00</span><span class="sxs-lookup"><span data-stu-id="666a5-130">Round-off value = 100.00</span></span> | <span data-ttu-id="666a5-131">Lekerekítési érték = 0,00</span><span class="sxs-lookup"><span data-stu-id="666a5-131">Round-off value = 0.00</span></span>   |
|-------------------------------------|------------------------|------------------------|------------------------|--------------------------|--------------------------|
| <span data-ttu-id="666a5-132">Normál</span><span class="sxs-lookup"><span data-stu-id="666a5-132">Normal</span></span>                              | <span data-ttu-id="666a5-133">98,765.43</span><span class="sxs-lookup"><span data-stu-id="666a5-133">98,765.43</span></span>              | <span data-ttu-id="666a5-134">98,765.40</span><span class="sxs-lookup"><span data-stu-id="666a5-134">98,765.40</span></span>              | <span data-ttu-id="666a5-135">98,765.00</span><span class="sxs-lookup"><span data-stu-id="666a5-135">98,765.00</span></span>              | <span data-ttu-id="666a5-136">98,800.00</span><span class="sxs-lookup"><span data-stu-id="666a5-136">98,800.00</span></span>                | <span data-ttu-id="666a5-137">98,765.43</span><span class="sxs-lookup"><span data-stu-id="666a5-137">98,765.43</span></span>                |
| <span data-ttu-id="666a5-138">Lefelé</span><span class="sxs-lookup"><span data-stu-id="666a5-138">Downward</span></span>                            | <span data-ttu-id="666a5-139">98,765.43</span><span class="sxs-lookup"><span data-stu-id="666a5-139">98,765.43</span></span>              | <span data-ttu-id="666a5-140">98,765.40</span><span class="sxs-lookup"><span data-stu-id="666a5-140">98,765.40</span></span>              | <span data-ttu-id="666a5-141">98,765.00</span><span class="sxs-lookup"><span data-stu-id="666a5-141">98,765.00</span></span>              | <span data-ttu-id="666a5-142">98,700.00</span><span class="sxs-lookup"><span data-stu-id="666a5-142">98,700.00</span></span>                | <span data-ttu-id="666a5-143">98,765.00</span><span class="sxs-lookup"><span data-stu-id="666a5-143">98,765.00</span></span>                |
| <span data-ttu-id="666a5-144">Felkerekítés</span><span class="sxs-lookup"><span data-stu-id="666a5-144">Rounding-up</span></span>                         | <span data-ttu-id="666a5-145">98,765.43</span><span class="sxs-lookup"><span data-stu-id="666a5-145">98,765.43</span></span>              | <span data-ttu-id="666a5-146">98,765.50</span><span class="sxs-lookup"><span data-stu-id="666a5-146">98,765.50</span></span>              | <span data-ttu-id="666a5-147">98,766.00</span><span class="sxs-lookup"><span data-stu-id="666a5-147">98,766.00</span></span>              | <span data-ttu-id="666a5-148">98,800.00</span><span class="sxs-lookup"><span data-stu-id="666a5-148">98,800.00</span></span>                | <span data-ttu-id="666a5-149">98,766.00</span><span class="sxs-lookup"><span data-stu-id="666a5-149">98,766.00</span></span>                |
| <span data-ttu-id="666a5-150">Saját előny, egy követel egyenleghez</span><span class="sxs-lookup"><span data-stu-id="666a5-150">Own advantage, for a credit balance</span></span> | <span data-ttu-id="666a5-151">98,765.43</span><span class="sxs-lookup"><span data-stu-id="666a5-151">98,765.43</span></span>              | <span data-ttu-id="666a5-152">98,765.40</span><span class="sxs-lookup"><span data-stu-id="666a5-152">98,765.40</span></span>              | <span data-ttu-id="666a5-153">98,765.00</span><span class="sxs-lookup"><span data-stu-id="666a5-153">98,765.00</span></span>              | <span data-ttu-id="666a5-154">98,700.00</span><span class="sxs-lookup"><span data-stu-id="666a5-154">98,700.00</span></span>                | <span data-ttu-id="666a5-155">98,765.00</span><span class="sxs-lookup"><span data-stu-id="666a5-155">98,765.00</span></span>                |
| <span data-ttu-id="666a5-156">Saját előny, egy tartozik egyenleghez</span><span class="sxs-lookup"><span data-stu-id="666a5-156">Own advantage, for a debit balance</span></span>  | <span data-ttu-id="666a5-157">98,765.43</span><span class="sxs-lookup"><span data-stu-id="666a5-157">98,765.43</span></span>              | <span data-ttu-id="666a5-158">98,765.50</span><span class="sxs-lookup"><span data-stu-id="666a5-158">98,765.50</span></span>              | <span data-ttu-id="666a5-159">98,766.00</span><span class="sxs-lookup"><span data-stu-id="666a5-159">98,766.00</span></span>              | <span data-ttu-id="666a5-160">98,800.00</span><span class="sxs-lookup"><span data-stu-id="666a5-160">98,800.00</span></span>                | <span data-ttu-id="666a5-161">98,766.00</span><span class="sxs-lookup"><span data-stu-id="666a5-161">98,766.00</span></span>                |

### <a name="normal-round-and-round-precision-is-001"></a><span data-ttu-id="666a5-162">Normál kerekítés és kerekítési pontosság 0,01</span><span class="sxs-lookup"><span data-stu-id="666a5-162">Normal round, and round precision is 0.01</span></span>

<table>
  <tr>
    <td><span data-ttu-id="666a5-163">Kerekítés</span><span class="sxs-lookup"><span data-stu-id="666a5-163">Rounding</span></span>
    </td>
    <td><span data-ttu-id="666a5-164">Számítási folyamat</span><span class="sxs-lookup"><span data-stu-id="666a5-164">Calculation process</span></span>
    </td>
  </tr>
    <tr>
    <td><span data-ttu-id="666a5-165">kerekítés(1,015, 0,01) = 1,02</span><span class="sxs-lookup"><span data-stu-id="666a5-165">round(1.015, 0.01) = 1.02</span></span>
    </td>
    <td>
      <ol>
        <li><span data-ttu-id="666a5-166">kerekítés(1,015 / 0,01, 0) = kerekítés(101,5, 0) = 102</span><span class="sxs-lookup"><span data-stu-id="666a5-166">round(1.015 / 0.01, 0) = round(101.5, 0) = 102</span></span>
        </li>
        <li><span data-ttu-id="666a5-167">102 \* 0,01 = 1,02</span><span class="sxs-lookup"><span data-stu-id="666a5-167">102 \* 0.01 = 1.02</span></span>
        </li>
      </ol>
    </td>
  </tr>
    <tr>
    <td><span data-ttu-id="666a5-168">kerekítés(1,014, 0,01) = 1,01</span><span class="sxs-lookup"><span data-stu-id="666a5-168">round(1.014, 0.01) = 1.01</span></span>
    </td>
    <td> <ol>
        <li><span data-ttu-id="666a5-169">kerekítés(1,014 / 0,01, 0) = kerekítés(101,4, 0) = 101</span><span class="sxs-lookup"><span data-stu-id="666a5-169">round(1.014 / 0.01, 0) = round(101.4, 0) = 101</span></span>
        </li>
        <li><span data-ttu-id="666a5-170">101 \* 0,01 = 1,01</span><span class="sxs-lookup"><span data-stu-id="666a5-170">101 \* 0.01 = 1.01</span></span>
        </li>
      </ol>
    </td>
  </tr>
    <tr>
    <td><span data-ttu-id="666a5-171">kerekítés(1,011, 0,02) = 1,02</span><span class="sxs-lookup"><span data-stu-id="666a5-171">round(1.011, 0.02) = 1.02</span></span>
    </td>
    <td> <ol>
        <li><span data-ttu-id="666a5-172">kerekítés(1,011 / 0,02, 0) = kerekítés(50,55, 0) = 51</span><span class="sxs-lookup"><span data-stu-id="666a5-172">round(1.011 / 0.02, 0) = round(50.55, 0) = 51</span></span>
        </li>
        <li><span data-ttu-id="666a5-173">51 \* 0,02 = 1,02</span><span class="sxs-lookup"><span data-stu-id="666a5-173">51 \* 0.02 = 1.02</span></span>
        </li>
      </ol>
    </td>
  </tr>
    <tr>
    <td><span data-ttu-id="666a5-174">kerekítés(1,009, 0,02) = 1,00</span><span class="sxs-lookup"><span data-stu-id="666a5-174">round(1.009, 0.02) = 1.00</span></span>
    </td>
    <td> <ol>
        <li><span data-ttu-id="666a5-175">kerekítés(1,009 / 0,02, 0) = kerekítés(50,45, 0) = 50</span><span class="sxs-lookup"><span data-stu-id="666a5-175">round(1.009 / 0.02, 0) = round(50.45, 0) = 50</span></span>
        </li>
        <li><span data-ttu-id="666a5-176">50 \* 0,02 = 1,00</span><span class="sxs-lookup"><span data-stu-id="666a5-176">50 \* 0.02 = 1.00</span></span>
        </li>
      </ol>
    </td>
  </tr>
</table>

> [!NOTE]                                                                                  
> <span data-ttu-id="666a5-177">Saját előny választása esetén a kerekítés mindig a jogi személy előnyére történik.</span><span class="sxs-lookup"><span data-stu-id="666a5-177">If you select Own advantage, the rounding is always to the advantage of the legal entity.</span></span> 

<span data-ttu-id="666a5-178">További információ a következő témakörökben olvasható:</span><span class="sxs-lookup"><span data-stu-id="666a5-178">For more information, see the following topics:</span></span>
- [<span data-ttu-id="666a5-179">Áfa áttekintése</span><span class="sxs-lookup"><span data-stu-id="666a5-179">Sales tax overview</span></span>](indirect-taxes-overview.md)
- [<span data-ttu-id="666a5-180">Áfakifizetés létrehozása</span><span class="sxs-lookup"><span data-stu-id="666a5-180">Create a sales tax payment</span></span>](tasks/create-sales-tax-payment.md)
- [<span data-ttu-id="666a5-181">Áfatranzakciók létrehozása dokumentumokra</span><span class="sxs-lookup"><span data-stu-id="666a5-181">Create sales tax transactions on documents</span></span>](tasks/create-sales-tax-transactions-documents.md)
- [<span data-ttu-id="666a5-182">Feladott áfatranzakciók megtekintése</span><span class="sxs-lookup"><span data-stu-id="666a5-182">View posted sales tax transactions</span></span>](tasks/view-posted-sales-tax-transactions.md)
- [<span data-ttu-id="666a5-183">kerekítés függvény</span><span class="sxs-lookup"><span data-stu-id="666a5-183">round Function</span></span>](https://msdn.microsoft.com/library/aa850656.aspx)




[!INCLUDE[footer-include](../../includes/footer-banner.md)]