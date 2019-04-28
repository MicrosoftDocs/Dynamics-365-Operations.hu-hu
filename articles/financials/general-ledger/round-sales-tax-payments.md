---
title: Forgalmi adókifizetések és kerekítési szabályok
description: Ez a cikk bemutatja az adóhatóságokon történő kerekítési szabályok működésének módját és az áfaegyenleg kerekítését az Áfa kiegyenlítése és feladása során.
author: ShylaThompson
manager: AnnBe
ms.date: 05/30/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxAuthority
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 6134
ms.assetid: 7dcd3cf5-ebdf-4a9f-806c-1296c7da0331
ms.search.region: Global
ms.author: yijialuan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1e1c1bb1c792eb79888a1df209f2eebaf14a38dd
ms.sourcegitcommit: a6d385db6636ef2b7fb6b24d37a2160c8d5a3c0f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/14/2019
ms.locfileid: "842438"
---
# <a name="sales-tax-payments-and-rounding-rules"></a><span data-ttu-id="167fe-103">Forgalmi adókifizetések és kerekítési szabályok</span><span class="sxs-lookup"><span data-stu-id="167fe-103">Sales tax payments and rounding rules</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="167fe-104">Ez a cikk bemutatja az adóhatóságokon történő kerekítési szabályok működésének módját és az áfaegyenleg kerekítését az Áfa kiegyenlítése és feladása során.</span><span class="sxs-lookup"><span data-stu-id="167fe-104">This article explains how the rounding rule setup on the Sales tax authorities works and rounding the sales tax balance during the Settle and post sales tax job.</span></span>

<span data-ttu-id="167fe-105">Rendszeres időközönként forgalmi adót be kell vallani és ki kell fizetni az adóhatóságoknak.</span><span class="sxs-lookup"><span data-stu-id="167fe-105">Periodically, sales tax needs to be reported and paid to tax authorities.</span></span> <span data-ttu-id="167fe-106">Ez a Forgalmi adó oldalon a forgalmi adó rendezése és feladása folyamat használatával végezhető el.</span><span class="sxs-lookup"><span data-stu-id="167fe-106">This can be done by running the settle and post sales tax process in the Sales tax page.</span></span> <span data-ttu-id="167fe-107">Az egy időszakra vonatkozó áfa az áfaszámlák alapján egyenlíthető ki, és az áfaegyenleg rákerül az áfakiegyenlítési számlára.</span><span class="sxs-lookup"><span data-stu-id="167fe-107">Sales tax for a period will be settled against the sales tax accounts and the sales tax balance will be posted to the Sales tax settlement account.</span></span> <span data-ttu-id="167fe-108">A forgalmi adóegyenleg, amely az ÁFA elszámolási számláján lesz könyvelve, kerekíthető az adóhatóságok elvárásai szerint, egy kerekítési szabály felállításával a Forgalmi adó lapon.</span><span class="sxs-lookup"><span data-stu-id="167fe-108">The sales tax balance, which is posted on the Sales tax settlement account, can be rounded as required by tax authorities by setting up a rounding rule on the Sales tax page.</span></span> 

<span data-ttu-id="167fe-109">A kerekítési különbség rákerül a Forgalmi adó kerekítési számlájára, amelyet a Számlák automatikus tranzakciókhoz mezőben, a Főkönyvben kell kiválasztani.</span><span class="sxs-lookup"><span data-stu-id="167fe-109">The rounding difference is posted to the Sales tax rounding account that is selected in the Accounts for automatic transactions field in the General ledger.</span></span>

<span data-ttu-id="167fe-110">Az alábbi példa bemutatja, hogyan működik az adóhatóságnak a kerekítési szabálya.</span><span class="sxs-lookup"><span data-stu-id="167fe-110">The below example illustrates how the rounding rule on Sales tax authority works.</span></span>

## <a name="examples"></a><span data-ttu-id="167fe-111">Példák</span><span class="sxs-lookup"><span data-stu-id="167fe-111">Examples</span></span>

<span data-ttu-id="167fe-112">Az időszak teljes áfája -98,765.43 követel egyenleget mutat.</span><span class="sxs-lookup"><span data-stu-id="167fe-112">The total sales tax for a period shows a credit balance of -98,765.43.</span></span> <span data-ttu-id="167fe-113">A jogi személy több áfát gyűjtött össze, mint amennyit kifizetett.</span><span class="sxs-lookup"><span data-stu-id="167fe-113">The legal entity collected more sales taxes than it paid.</span></span> <span data-ttu-id="167fe-114">Emiatt a jogi személy pénzzel tartozik az adóhatóságnak.</span><span class="sxs-lookup"><span data-stu-id="167fe-114">Therefore, the legal entity owes money to the tax authority.</span></span> 

<span data-ttu-id="167fe-115">A jogi személy olyan kerekítési módszert szeretne alkalmazni, amely az egyenleget a legközelebbi 1,00 egész összegre kerekíti.</span><span class="sxs-lookup"><span data-stu-id="167fe-115">The legal entity wants to use a rounding method that rounds the balance to the nearest 1.00.</span></span> <span data-ttu-id="167fe-116">Az áfa könyveléséért felelős felhasználó tehát a következőket teszi:</span><span class="sxs-lookup"><span data-stu-id="167fe-116">The user who is responsible for sales tax accounting performs the following steps.</span></span>

1.  <span data-ttu-id="167fe-117">Rákattint az Adó &gt; Közvetett adók &gt; Áfa &gt; Adóhatóságok pontra.</span><span class="sxs-lookup"><span data-stu-id="167fe-117">Click Tax &gt; Indirect taxes &gt; Sales tax &gt; Sales tax authorities</span></span>
2.  <span data-ttu-id="167fe-118">Az Általános gyorslapon Kerekítési képernyő mezőjében kiválasztja a Normál lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="167fe-118">On the General FastTab, select Normal in the Rounding form field.</span></span>
3.  <span data-ttu-id="167fe-119">A Lekerekítés mezőben ezt adja meg: 1,00.</span><span class="sxs-lookup"><span data-stu-id="167fe-119">In the Round-off field, enter 1.00.</span></span>
4.  <span data-ttu-id="167fe-120">Amikor az áfa kifizetése esedékes az adóhatóság felé, megnyitja az Adók kiegyenlítése és feladása lapot.</span><span class="sxs-lookup"><span data-stu-id="167fe-120">When it is time to pay the sales taxes to the tax authority, open the Settle and post sales tax page.</span></span> <span data-ttu-id="167fe-121">(Rákattint az Adó &gt; Bevallások &gt; Áfa &gt; Áfa kiegyenlítése és feladása pontra.)</span><span class="sxs-lookup"><span data-stu-id="167fe-121">(Click Tax &gt; Declarations &gt; Sales tax &gt; Settle and post sales tax.)</span></span>
5.  <span data-ttu-id="167fe-122">Az áfakiegyenlítési számlán az adókötelezettség, amely 98.765,43, 98.765-re lesz kerekítve.</span><span class="sxs-lookup"><span data-stu-id="167fe-122">On the sales tax settlement account, the tax liability amount of 98,765.43 is rounded to 98,765.</span></span>

<span data-ttu-id="167fe-123">Az alábbi táblázat bemutatja, hogyan kerekítjük a 98.765,43 összeget az egyes kerekítési módok használatával az Adóhatóságok lapon, a Kerekítési képernyő mezőjében.</span><span class="sxs-lookup"><span data-stu-id="167fe-123">The following table shows how an amount of 98,765.43 is rounded by using each rounding method that is available in the Rounding form field in the Sales tax authorities page.</span></span>

| <span data-ttu-id="167fe-124">Kerekítési képernyőopció</span><span class="sxs-lookup"><span data-stu-id="167fe-124">Rounding form option</span></span>                | <span data-ttu-id="167fe-125">Lekerekítési érték = 0,01</span><span class="sxs-lookup"><span data-stu-id="167fe-125">Round-off value = 0.01</span></span> | <span data-ttu-id="167fe-126">Lekerekítési érték = 0,10</span><span class="sxs-lookup"><span data-stu-id="167fe-126">Round-off value = 0.10</span></span> | <span data-ttu-id="167fe-127">Lekerekítési érték = 1,00</span><span class="sxs-lookup"><span data-stu-id="167fe-127">Round-off value = 1.00</span></span> | <span data-ttu-id="167fe-128">Lekerekítési érték = 100,00</span><span class="sxs-lookup"><span data-stu-id="167fe-128">Round-off value = 100.00</span></span> |
|-------------------------------------|------------------------|------------------------|------------------------|--------------------------|
| <span data-ttu-id="167fe-129">Normál</span><span class="sxs-lookup"><span data-stu-id="167fe-129">Normal</span></span>                              | <span data-ttu-id="167fe-130">98.765,43</span><span class="sxs-lookup"><span data-stu-id="167fe-130">98,765.43</span></span>              | <span data-ttu-id="167fe-131">98.765,40</span><span class="sxs-lookup"><span data-stu-id="167fe-131">98,765.40</span></span>              | <span data-ttu-id="167fe-132">98.765,00</span><span class="sxs-lookup"><span data-stu-id="167fe-132">98,765.00</span></span>              | <span data-ttu-id="167fe-133">98.800,00</span><span class="sxs-lookup"><span data-stu-id="167fe-133">98,800.00</span></span>                |
| <span data-ttu-id="167fe-134">Lefelé</span><span class="sxs-lookup"><span data-stu-id="167fe-134">Downward</span></span>                            | <span data-ttu-id="167fe-135">98.765,43</span><span class="sxs-lookup"><span data-stu-id="167fe-135">98,765.43</span></span>              | <span data-ttu-id="167fe-136">98.765,40</span><span class="sxs-lookup"><span data-stu-id="167fe-136">98,765.40</span></span>              | <span data-ttu-id="167fe-137">98,765.00</span><span class="sxs-lookup"><span data-stu-id="167fe-137">98,765.00</span></span>              | <span data-ttu-id="167fe-138">98.700,00</span><span class="sxs-lookup"><span data-stu-id="167fe-138">98,700.00</span></span>                |
| <span data-ttu-id="167fe-139">Felkerekítés</span><span class="sxs-lookup"><span data-stu-id="167fe-139">Rounding-up</span></span>                         | <span data-ttu-id="167fe-140">98.765,43</span><span class="sxs-lookup"><span data-stu-id="167fe-140">98,765.43</span></span>              | <span data-ttu-id="167fe-141">98.765,50</span><span class="sxs-lookup"><span data-stu-id="167fe-141">98,765.50</span></span>              | <span data-ttu-id="167fe-142">98.766,00</span><span class="sxs-lookup"><span data-stu-id="167fe-142">98,766.00</span></span>              | <span data-ttu-id="167fe-143">98.800,00</span><span class="sxs-lookup"><span data-stu-id="167fe-143">98,800.00</span></span>                |
| <span data-ttu-id="167fe-144">Saját előny, egy követel egyenleghez</span><span class="sxs-lookup"><span data-stu-id="167fe-144">Own advantage, for a credit balance</span></span> | <span data-ttu-id="167fe-145">98.765,43</span><span class="sxs-lookup"><span data-stu-id="167fe-145">98,765.43</span></span>              | <span data-ttu-id="167fe-146">98.765,40</span><span class="sxs-lookup"><span data-stu-id="167fe-146">98,765.40</span></span>              | <span data-ttu-id="167fe-147">98.765,00</span><span class="sxs-lookup"><span data-stu-id="167fe-147">98,765.00</span></span>              | <span data-ttu-id="167fe-148">98.700,00</span><span class="sxs-lookup"><span data-stu-id="167fe-148">98,700.00</span></span>                |
| <span data-ttu-id="167fe-149">Saját előny, egy tartozik egyenleghez</span><span class="sxs-lookup"><span data-stu-id="167fe-149">Own advantage, for a debit balance</span></span>  | <span data-ttu-id="167fe-150">98,765.43</span><span class="sxs-lookup"><span data-stu-id="167fe-150">98,765.43</span></span>              | <span data-ttu-id="167fe-151">98,765.50</span><span class="sxs-lookup"><span data-stu-id="167fe-151">98,765.50</span></span>              | <span data-ttu-id="167fe-152">98,766.00</span><span class="sxs-lookup"><span data-stu-id="167fe-152">98,766.00</span></span>              | <span data-ttu-id="167fe-153">98,800.00</span><span class="sxs-lookup"><span data-stu-id="167fe-153">98,800.00</span></span>                |


### <a name="no-rounding-at-all-since-the-round-off-is-000"></a><span data-ttu-id="167fe-154">Nincs kerekítés, mivel a kerekítés 0,00</span><span class="sxs-lookup"><span data-stu-id="167fe-154">No rounding at all, since the round-off is 0.00</span></span>

<span data-ttu-id="167fe-155">ekerekítés(1,0151, 0,00) = 1,0151 kerekítés(1,0149, 0,00) = 1,0149</span><span class="sxs-lookup"><span data-stu-id="167fe-155">round(1.0151, 0.00) = 1.0151 round(1.0149, 0.00) = 1.0149</span></span>

### <a name="normal-round-and-round-precision-is-001"></a><span data-ttu-id="167fe-156">Normál kerekítés és kerekítési pontosság 0,01</span><span class="sxs-lookup"><span data-stu-id="167fe-156">Normal round, and round precision is 0.01</span></span>

<table>
  <tr>
    <td><span data-ttu-id="167fe-157">Kerekítés</span><span class="sxs-lookup"><span data-stu-id="167fe-157">Rounding</span></span>
    </td>
    <td><span data-ttu-id="167fe-158">Számítási folyamat</span><span class="sxs-lookup"><span data-stu-id="167fe-158">Calculation process</span></span>
    </td>
  </tr>
    <tr>
    <td><span data-ttu-id="167fe-159">kerekítés(1,015, 0,01) = 1,02</span><span class="sxs-lookup"><span data-stu-id="167fe-159">round(1.015, 0.01) = 1.02</span></span>
    </td>
    <td>
      <ol>
        <li><span data-ttu-id="167fe-160">kerekítés(1,015 / 0,01, 0) = kerekítés(101,5, 0) = 102</span><span class="sxs-lookup"><span data-stu-id="167fe-160">round(1.015 / 0.01, 0) = round(101.5, 0) = 102</span></span>
        </li>
        <li><span data-ttu-id="167fe-161">102 \* 0,01 = 1,02</span><span class="sxs-lookup"><span data-stu-id="167fe-161">102 \* 0.01 = 1.02</span></span>
        </li>
      </ol>
    </td>
  </tr>
    <tr>
    <td><span data-ttu-id="167fe-162">kerekítés(1,014, 0,01) = 1,01</span><span class="sxs-lookup"><span data-stu-id="167fe-162">round(1.014, 0.01) = 1.01</span></span>
    </td>
    <td> <ol>
        <li><span data-ttu-id="167fe-163">kerekítés(1,014 / 0,01, 0) = kerekítés(101,4, 0) = 101</span><span class="sxs-lookup"><span data-stu-id="167fe-163">round(1.014 / 0.01, 0) = round(101.4, 0) = 101</span></span>
        </li>
        <li><span data-ttu-id="167fe-164">101 \* 0,01 = 1,01</span><span class="sxs-lookup"><span data-stu-id="167fe-164">101 \* 0.01 = 1.01</span></span>
        </li>
      </ol>
    </td>
  </tr>
    <tr>
    <td><span data-ttu-id="167fe-165">kerekítés(1,011, 0,02) = 1,02</span><span class="sxs-lookup"><span data-stu-id="167fe-165">round(1.011, 0.02) = 1.02</span></span>
    </td>
    <td> <ol>
        <li><span data-ttu-id="167fe-166">kerekítés(1,011 / 0,02, 0) = kerekítés(50,55, 0) = 51</span><span class="sxs-lookup"><span data-stu-id="167fe-166">round(1.011 / 0.02, 0) = round(50.55, 0) = 51</span></span>
        </li>
        <li><span data-ttu-id="167fe-167">51 \* 0,02 = 1,02</span><span class="sxs-lookup"><span data-stu-id="167fe-167">51 \* 0.02 = 1.02</span></span>
        </li>
      </ol>
    </td>
  </tr>
    <tr>
    <td><span data-ttu-id="167fe-168">kerekítés(1,009, 0,02) = 1,00</span><span class="sxs-lookup"><span data-stu-id="167fe-168">round(1.009, 0.02) = 1.00</span></span>
    </td>
    <td> <ol>
        <li><span data-ttu-id="167fe-169">kerekítés(1,009 / 0,02, 0) = kerekítés(50,45, 0) = 50</span><span class="sxs-lookup"><span data-stu-id="167fe-169">round(1.009 / 0.02, 0) = round(50.45, 0) = 50</span></span>
        </li>
        <li><span data-ttu-id="167fe-170">50 \* 0,02 = 1,00</span><span class="sxs-lookup"><span data-stu-id="167fe-170">50 \* 0.02 = 1.00</span></span>
        </li>
      </ol>
    </td>
  </tr>
</table>

> [!NOTE]                                                                                  
> <span data-ttu-id="167fe-171">Saját előny választása esetén a kerekítés mindig a jogi személy előnyére történik.</span><span class="sxs-lookup"><span data-stu-id="167fe-171">If you select Own advantage, the rounding is always to the advantage of the legal entity.</span></span> 

<span data-ttu-id="167fe-172">További információ a következő témakörökben olvasható:</span><span class="sxs-lookup"><span data-stu-id="167fe-172">For more information, see the following topics:</span></span>
- [<span data-ttu-id="167fe-173">Áfa áttekintése</span><span class="sxs-lookup"><span data-stu-id="167fe-173">Sales tax overview</span></span>](indirect-taxes-overview.md)
- [<span data-ttu-id="167fe-174">Áfakifizetés létrehozása</span><span class="sxs-lookup"><span data-stu-id="167fe-174">Create a sales tax payment</span></span>](tasks/create-sales-tax-payment.md)
- [<span data-ttu-id="167fe-175">Értékesítési tranzakciók létrehozása dokumentumokra</span><span class="sxs-lookup"><span data-stu-id="167fe-175">Create sales transactions on documents</span></span>](tasks/create-sales-tax-transactions-documents.md)
- [<span data-ttu-id="167fe-176">Feladott áfatranzakciók megtekintése</span><span class="sxs-lookup"><span data-stu-id="167fe-176">View posted sales tax transactions</span></span>](tasks/view-posted-sales-tax-transactions.md)
- [<span data-ttu-id="167fe-177">kerekítés függvény</span><span class="sxs-lookup"><span data-stu-id="167fe-177">round Function</span></span>](https://msdn.microsoft.com/en-us/library/aa850656.aspx)


