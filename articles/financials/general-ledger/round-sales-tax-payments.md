---
title: Forgalmi adókifizetések és kerekítési szabályok
description: Ez a cikk bemutatja az adóhatóságokon történő kerekítési szabályok működésének módját és az áfaegyenleg kerekítését az Áfa kiegyenlítése és feladása során.
author: ShylaThompson
manager: AnnBe
ms.date: 08/01/2017
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
ms.author: vstehman
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f03336c834e74cd12d039c7b9692874843811746
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "367846"
---
# <a name="sales-tax-payments-and-rounding-rules"></a><span data-ttu-id="addbb-103">Forgalmi adókifizetések és kerekítési szabályok</span><span class="sxs-lookup"><span data-stu-id="addbb-103">Sales tax payments and rounding rules</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="addbb-104">Ez a cikk bemutatja az adóhatóságokon történő kerekítési szabályok működésének módját és az áfaegyenleg kerekítését az Áfa kiegyenlítése és feladása során.</span><span class="sxs-lookup"><span data-stu-id="addbb-104">This article explains how the rounding rule setup on the Sales tax authorities works and rounding the sales tax balance during the Settle and post sales tax job.</span></span>

<span data-ttu-id="addbb-105">Rendszeres időközönként forgalmi adót be kell vallani és ki kell fizetni az adóhatóságoknak.</span><span class="sxs-lookup"><span data-stu-id="addbb-105">Periodically, sales tax needs to be reported and paid to tax authorities.</span></span> <span data-ttu-id="addbb-106">Ez a Forgalmi adó oldalon a forgalmi adó rendezése és feladása folyamat használatával végezhető el.</span><span class="sxs-lookup"><span data-stu-id="addbb-106">This can be done by running the settle and post sales tax process in the Sales tax page.</span></span> <span data-ttu-id="addbb-107">Az egy időszakra vonatkozó áfa az áfaszámlák alapján egyenlíthető ki, és az áfaegyenleg rákerül az áfakiegyenlítési számlára.</span><span class="sxs-lookup"><span data-stu-id="addbb-107">Sales tax for a period will be settled against the sales tax accounts and the sales tax balance will be posted to the Sales tax settlement account.</span></span> <span data-ttu-id="addbb-108">A forgalmi adóegyenleg, amely az ÁFA elszámolási számláján lesz könyvelve, kerekíthető az adóhatóságok elvárásai szerint, egy kerekítési szabály felállításával a Forgalmi adó lapon.</span><span class="sxs-lookup"><span data-stu-id="addbb-108">The sales tax balance, which is posted on the Sales tax settlement account, can be rounded as required by tax authorities by setting up a rounding rule on the Sales tax page.</span></span> 

<span data-ttu-id="addbb-109">A kerekítési különbség rákerül a Forgalmi adó kerekítési számlájára, amelyet a Számlák automatikus tranzakciókhoz mezőben, a Főkönyvben kell kiválasztani.</span><span class="sxs-lookup"><span data-stu-id="addbb-109">The rounding difference is posted to the Sales tax rounding account that is selected in the Accounts for automatic transactions field in the General ledger.</span></span>

<span data-ttu-id="addbb-110">Az alábbi példa bemutatja, hogyan működik az adóhatóságnak a kerekítési szabálya.</span><span class="sxs-lookup"><span data-stu-id="addbb-110">The below example illustrates how the rounding rule on Sales tax authority works.</span></span>

### <a name="example"></a><span data-ttu-id="addbb-111">Példa:</span><span class="sxs-lookup"><span data-stu-id="addbb-111">Example:</span></span>

<span data-ttu-id="addbb-112">Az időszak teljes áfája -98,765.43 követel egyenleget mutat.</span><span class="sxs-lookup"><span data-stu-id="addbb-112">The total sales tax for a period shows a credit balance of -98,765.43.</span></span> <span data-ttu-id="addbb-113">A jogi személy több áfát gyűjtött össze, mint amennyit kifizetett.</span><span class="sxs-lookup"><span data-stu-id="addbb-113">The legal entity collected more sales taxes than it paid.</span></span> <span data-ttu-id="addbb-114">Emiatt a jogi személy pénzzel tartozik az adóhatóságnak.</span><span class="sxs-lookup"><span data-stu-id="addbb-114">Therefore, the legal entity owes money to the tax authority.</span></span> 

<span data-ttu-id="addbb-115">A jogi személy olyan kerekítési módszert szeretne alkalmazni, amely az egyenleget a legközelebbi 1,00 egész összegre kerekíti.</span><span class="sxs-lookup"><span data-stu-id="addbb-115">The legal entity wants to use a rounding method that rounds the balance to the nearest 1.00.</span></span> <span data-ttu-id="addbb-116">Az áfa könyveléséért felelős felhasználó tehát a következőket teszi:</span><span class="sxs-lookup"><span data-stu-id="addbb-116">The user who is responsible for sales tax accounting performs the following steps.</span></span>

1.  <span data-ttu-id="addbb-117">Rákattint az Adó &gt; Közvetett adók &gt; Áfa &gt; Adóhatóságok pontra.</span><span class="sxs-lookup"><span data-stu-id="addbb-117">Click Tax &gt; Indirect taxes &gt; Sales tax &gt; Sales tax authorities</span></span>
2.  <span data-ttu-id="addbb-118">Az Általános gyorslapon Kerekítési képernyő mezőjében kiválasztja a Normál lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="addbb-118">On the General FastTab, select Normal in the Rounding form field.</span></span>
3.  <span data-ttu-id="addbb-119">A Lekerekítés mezőben ezt adja meg: 1,00.</span><span class="sxs-lookup"><span data-stu-id="addbb-119">In the Round-off field, enter 1.00.</span></span>
4.  <span data-ttu-id="addbb-120">Amikor az áfa kifizetése esedékes az adóhatóság felé, megnyitja az Adók kiegyenlítése és feladása lapot.</span><span class="sxs-lookup"><span data-stu-id="addbb-120">When it is time to pay the sales taxes to the tax authority, open the Settle and post sales tax page.</span></span> <span data-ttu-id="addbb-121">(Rákattint az Adó &gt; Bevallások &gt; Áfa &gt; Áfa kiegyenlítése és feladása pontra.)</span><span class="sxs-lookup"><span data-stu-id="addbb-121">(Click Tax &gt; Declarations &gt; Sales tax &gt; Settle and post sales tax.)</span></span>
5.  <span data-ttu-id="addbb-122">Az áfakiegyenlítési számlán az adókötelezettség, amely 98.765,43, 98.765-re lesz kerekítve.</span><span class="sxs-lookup"><span data-stu-id="addbb-122">On the sales tax settlement account, the tax liability amount of 98,765.43 is rounded to 98,765.</span></span>

<span data-ttu-id="addbb-123">Az alábbi táblázat bemutatja, hogyan kerekítjük a 98.765,43 összeget az egyes kerekítési módok használatával az Adóhatóságok lapon, a Kerekítési képernyő mezőjében.</span><span class="sxs-lookup"><span data-stu-id="addbb-123">The following table shows how an amount of 98,765.43 is rounded by using each rounding method that is available in the Rounding form field in the Sales tax authorities page.</span></span>

| <span data-ttu-id="addbb-124">Kerekítési képernyőopció</span><span class="sxs-lookup"><span data-stu-id="addbb-124">Rounding form option</span></span>                | <span data-ttu-id="addbb-125">Lekerekítési érték = 0,01</span><span class="sxs-lookup"><span data-stu-id="addbb-125">Round-off value = 0.01</span></span> | <span data-ttu-id="addbb-126">Lekerekítési érték = 0,10</span><span class="sxs-lookup"><span data-stu-id="addbb-126">Round-off value = 0.10</span></span> | <span data-ttu-id="addbb-127">Lekerekítési érték = 1,00</span><span class="sxs-lookup"><span data-stu-id="addbb-127">Round-off value = 1.00</span></span> | <span data-ttu-id="addbb-128">Lekerekítési érték = 100,00</span><span class="sxs-lookup"><span data-stu-id="addbb-128">Round-off value = 100.00</span></span> |
|-------------------------------------|------------------------|------------------------|------------------------|--------------------------|
| <span data-ttu-id="addbb-129">Normál</span><span class="sxs-lookup"><span data-stu-id="addbb-129">Normal</span></span>                              | <span data-ttu-id="addbb-130">98.765,43</span><span class="sxs-lookup"><span data-stu-id="addbb-130">98,765.43</span></span>              | <span data-ttu-id="addbb-131">98.765,40</span><span class="sxs-lookup"><span data-stu-id="addbb-131">98,765.40</span></span>              | <span data-ttu-id="addbb-132">98.765,00</span><span class="sxs-lookup"><span data-stu-id="addbb-132">98,765.00</span></span>              | <span data-ttu-id="addbb-133">98.800,00</span><span class="sxs-lookup"><span data-stu-id="addbb-133">98,800.00</span></span>                |
| <span data-ttu-id="addbb-134">Lefelé</span><span class="sxs-lookup"><span data-stu-id="addbb-134">Downward</span></span>                            | <span data-ttu-id="addbb-135">98.765,43</span><span class="sxs-lookup"><span data-stu-id="addbb-135">98,765.43</span></span>              | <span data-ttu-id="addbb-136">98.765,40</span><span class="sxs-lookup"><span data-stu-id="addbb-136">98,765.40</span></span>              | <span data-ttu-id="addbb-137">98,765.00</span><span class="sxs-lookup"><span data-stu-id="addbb-137">98,765.00</span></span>              | <span data-ttu-id="addbb-138">98.700,00</span><span class="sxs-lookup"><span data-stu-id="addbb-138">98,700.00</span></span>                |
| <span data-ttu-id="addbb-139">Felkerekítés</span><span class="sxs-lookup"><span data-stu-id="addbb-139">Rounding-up</span></span>                         | <span data-ttu-id="addbb-140">98.765,43</span><span class="sxs-lookup"><span data-stu-id="addbb-140">98,765.43</span></span>              | <span data-ttu-id="addbb-141">98.765,50</span><span class="sxs-lookup"><span data-stu-id="addbb-141">98,765.50</span></span>              | <span data-ttu-id="addbb-142">98.766,00</span><span class="sxs-lookup"><span data-stu-id="addbb-142">98,766.00</span></span>              | <span data-ttu-id="addbb-143">98.800,00</span><span class="sxs-lookup"><span data-stu-id="addbb-143">98,800.00</span></span>                |
| <span data-ttu-id="addbb-144">Saját előny, egy követel egyenleghez</span><span class="sxs-lookup"><span data-stu-id="addbb-144">Own advantage, for a credit balance</span></span> | <span data-ttu-id="addbb-145">98.765,43</span><span class="sxs-lookup"><span data-stu-id="addbb-145">98,765.43</span></span>              | <span data-ttu-id="addbb-146">98.765,40</span><span class="sxs-lookup"><span data-stu-id="addbb-146">98,765.40</span></span>              | <span data-ttu-id="addbb-147">98.765,00</span><span class="sxs-lookup"><span data-stu-id="addbb-147">98,765.00</span></span>              | <span data-ttu-id="addbb-148">98.700,00</span><span class="sxs-lookup"><span data-stu-id="addbb-148">98,700.00</span></span>                |
| <span data-ttu-id="addbb-149">Saját előny, egy tartozik egyenleghez</span><span class="sxs-lookup"><span data-stu-id="addbb-149">Own advantage, for a debit balance</span></span>  | <span data-ttu-id="addbb-150">98,765.43</span><span class="sxs-lookup"><span data-stu-id="addbb-150">98,765.43</span></span>              | <span data-ttu-id="addbb-151">98,765.50</span><span class="sxs-lookup"><span data-stu-id="addbb-151">98,765.50</span></span>              | <span data-ttu-id="addbb-152">98,766.00</span><span class="sxs-lookup"><span data-stu-id="addbb-152">98,766.00</span></span>              | <span data-ttu-id="addbb-153">98,800.00</span><span class="sxs-lookup"><span data-stu-id="addbb-153">98,800.00</span></span>                |

> [!NOTE]                                                                                  
> <span data-ttu-id="addbb-154">Saját előny választása esetén a kerekítés mindig a jogi személy előnyére történik.</span><span class="sxs-lookup"><span data-stu-id="addbb-154">If you select Own advantage, the rounding is always to the advantage of the legal entity.</span></span> 

<span data-ttu-id="addbb-155">További információ a következő témakörökben olvasható:</span><span class="sxs-lookup"><span data-stu-id="addbb-155">For more information, see the following topics:</span></span>
- [<span data-ttu-id="addbb-156">Áfa áttekintése</span><span class="sxs-lookup"><span data-stu-id="addbb-156">Sales tax overview</span></span>](indirect-taxes-overview.md)
- [<span data-ttu-id="addbb-157">Áfakifizetés létrehozása</span><span class="sxs-lookup"><span data-stu-id="addbb-157">Create a sales tax payment</span></span>](tasks/create-sales-tax-payment.md)
- [<span data-ttu-id="addbb-158">Értékesítési tranzakciók létrehozása dokumentumokra</span><span class="sxs-lookup"><span data-stu-id="addbb-158">Create sales transactions on documents</span></span>](tasks/create-sales-tax-transactions-documents.md)
- [<span data-ttu-id="addbb-159">Feladott áfatranzakciók megtekintése</span><span class="sxs-lookup"><span data-stu-id="addbb-159">View posted sales tax transactions</span></span>](tasks/view-posted-sales-tax-transactions.md)


