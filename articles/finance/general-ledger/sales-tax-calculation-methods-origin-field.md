---
title: ÁFA-számítási módok kiválasztása az Kiindulás mezőben
description: Ez a cikk ismerteti az áfa kódok lapon található Eredet mező opcióit és azt, hogy hogyan kerül kiszámításra az áfa a kiválasztott áfa kód alapján.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d326480cc03d80d1ce27f8762e300dca3b0d325e
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770643"
---
# <a name="sales-tax-calculation-methods-in-the-origin-field"></a><span data-ttu-id="78619-103">ÁFA-számítási módok kiválasztása az Kiindulás mezőben</span><span class="sxs-lookup"><span data-stu-id="78619-103">Sales tax calculation methods in the Origin field</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="78619-104">Ez a cikk ismerteti az áfa kódok lapon található Eredet mező opcióit és azt, hogy hogyan kerül kiszámításra az áfa a kiválasztott áfa kód alapján.</span><span class="sxs-lookup"><span data-stu-id="78619-104">This article explains the options in the Origin field on the sales tax codes page and how sales tax is calculated based on the selected option for a sales tax code.</span></span>

<span data-ttu-id="78619-105">Az Áfakódok oldalon létrehozott áfakódokhoz az Kiindulás mezőben ki kell választani az adóalap összegére alkalmazott számítási módszert.</span><span class="sxs-lookup"><span data-stu-id="78619-105">For each sales tax code that you create in the Sales tax codes page, you must select the method of calculation to apply to the tax base amount in the Origin field.</span></span>

## <a name="percentage-of-net-amount"></a><span data-ttu-id="78619-106">A nettó összeg százaléka</span><span class="sxs-lookup"><span data-stu-id="78619-106">Percentage of net amount</span></span>
<span data-ttu-id="78619-107">Az Kiindulás mezőben a Nettó összeg százalékos értéke számítási módszer az alapértelmezett érték.</span><span class="sxs-lookup"><span data-stu-id="78619-107">The Percentage of net amount calculation method is the default value in the Origin field.</span></span> <span data-ttu-id="78619-108">A program az áfát a beszerzési vagy értékesítési összeg százalékaként számítja ki, és az esetleges további forgalmi adókat nem foglalja bele a számításba.</span><span class="sxs-lookup"><span data-stu-id="78619-108">The sales tax is calculated as a percentage of the purchase or sales amount, excluding any other sales taxes.</span></span>
### <a name="example"></a><span data-ttu-id="78619-109">Példa</span><span class="sxs-lookup"><span data-stu-id="78619-109">Example</span></span>

<span data-ttu-id="78619-110">Adó mértéke: 25%.</span><span class="sxs-lookup"><span data-stu-id="78619-110">The tax rate is 25%.</span></span> <span data-ttu-id="78619-111">A számlasorban 10 cikk szerepel, mindegyik 1,00 dollárba kerül, és a vevő 10% sorkedvezményt kap.</span><span class="sxs-lookup"><span data-stu-id="78619-111">The invoice line shows a quantity of 10 items at 1.00 each, and the customer is allowed a 10% line discount.</span></span> <span data-ttu-id="78619-112">Nettó összeg: (10 x 1,00) -10% = 9,00 Áfa: 9,00 x 25% = 2,25 Teljes összeg: 9,00 + 2,25 = 11,25</span><span class="sxs-lookup"><span data-stu-id="78619-112">Net amount: (10 x 1.00) -10% = 9.00 Sales tax: 9.00 x 25% = 2.25 Total amount: 9.00 + 2.25 = 11.25</span></span>

## <a name="percentage-of-gross-amount"></a><span data-ttu-id="78619-113"> A bruttó összeg százaléka</span><span class="sxs-lookup"><span data-stu-id="78619-113">Percentage of gross amount</span></span>
<span data-ttu-id="78619-114">Ha A bruttó összeg százaléka módszer választja, az áfát a rendszer a bruttó értékesítési összeg százalékaként számítja ki.</span><span class="sxs-lookup"><span data-stu-id="78619-114">If you select the Percentage of gross amount method, the sales tax is calculated as a percentage of the gross sales amount.</span></span> <span data-ttu-id="78619-115">A bruttó összeg egyenlő a soron szereplő nettó összeg, a sorra vonatkozó összes adóval és díjjal megnövelt összegével, kivéve azt az egy adót, ahol Kiindulás = Bruttó összeg százaléka.</span><span class="sxs-lookup"><span data-stu-id="78619-115">The gross amount is the line net amount plus all taxes and fees for the line except the one tax with Origin = Percentage of gross amount.</span></span>
### <a name="example"></a><span data-ttu-id="78619-116">Példa</span><span class="sxs-lookup"><span data-stu-id="78619-116">Example</span></span>

<span data-ttu-id="78619-117">Az adóhatóság különleges adókat szabott ki egy cikkre.</span><span class="sxs-lookup"><span data-stu-id="78619-117">The tax authority has imposed special duties on an item.</span></span> <span data-ttu-id="78619-118">Az adó összegét a program az áfa kiszámítása előtt hozzáadja a nettó összeghez.</span><span class="sxs-lookup"><span data-stu-id="78619-118">The duty amounts are added to the net amount before sales tax is calculated.</span></span> <span data-ttu-id="78619-119">Az alábbi Áfakódok esetén:</span><span class="sxs-lookup"><span data-stu-id="78619-119">Given the following sales tax codes:</span></span>
-   <span data-ttu-id="78619-120">1. ADÓ = 10% a Nettó összeg százaléka számítási módszer használata mellett</span><span class="sxs-lookup"><span data-stu-id="78619-120">DUTY 1 = 10%, using the Percentage of net amount calculation method</span></span>
-   <span data-ttu-id="78619-121">2. ADÓ = 20% a Nettó összeg százaléka számítási módszer használata mellett</span><span class="sxs-lookup"><span data-stu-id="78619-121">DUTY 2 = 20%, using the Percentage of net amount calculation method</span></span>
-   <span data-ttu-id="78619-122">ÁFA = 25% a Bruttó összeg százaléka számítási módszer használata mellett</span><span class="sxs-lookup"><span data-stu-id="78619-122">SALESTAX = 25%, using the Percentage of gross amount calculation method</span></span>

<span data-ttu-id="78619-123">Ha a nettó összeg 10,00, akkor az 1. ADÓ 1,00 (10.00 x 10%) a 2. ADÓ pedig 2,00 (10.00 x 20%).</span><span class="sxs-lookup"><span data-stu-id="78619-123">If the net amount is 10.00, then DUTY 1 is 1.00 (10.00 x 10%) and DUTY 2 = 2.00 (10.00 x 20%).</span></span> <span data-ttu-id="78619-124">Az összegek a következők lesznek: Bruttó összeg: Nettó összeg + 1. ADÓ összege + 2. ADÓ összege (10,00 + 1,00 + 2,00) = 13.00 ÁFA = 13,00 x 25 % = 3,25 ADÓK és ÁFA összege: 1,00 + 2,00 + 3,25 = 6,25 Teljes összeg: 10,00 + 6,25 = 16,25</span><span class="sxs-lookup"><span data-stu-id="78619-124">The amounts would be as follows: Gross amount: Net amount + DUTY 1 amount + DUTY 2 amount (10.00 + 1.00 + 2.00) = 13.00 SALESTAX = 13.00 x 25% = 3.25 Total DUTIES and SALESTAX: 1.00 + 2.00 + 3.25 = 6.25 Total amount: 10.00 + 6.25 = 16.25</span></span>

| <span data-ttu-id="78619-125">**Megjegyzés**</span><span class="sxs-lookup"><span data-stu-id="78619-125">**Note**</span></span>                                                                                                                                                                                                                 |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="78619-126">A tranzakciókhoz csak egy olyan adó használható, ahol Kiindulás = Bruttó összeg százaléka.</span><span class="sxs-lookup"><span data-stu-id="78619-126">Only one tax code with Origin = Percentage of gross amount can be used for a transaction.</span></span> <span data-ttu-id="78619-127">Ha egynél több ilyen adókódot állít be egy tranzakcióhoz, úgy a rendszer arra vonatkozó hibaüzenetet jelenít meg, hogy az áfa kiszámítása nem lehetséges.</span><span class="sxs-lookup"><span data-stu-id="78619-127">If more than one such tax code is determined for a transaction an error will be displayed that sales tax cannot be calculated.</span></span> |


<a name="percentage-of-sales-tax"></a><span data-ttu-id="78619-128">Az áfa százaléka</span><span class="sxs-lookup"><span data-stu-id="78619-128">Percentage of sales tax</span></span>
-----------------------

<span data-ttu-id="78619-129">Ha az Kiindulás mezőben az Áfa százaléka lehetőséget választja, a rendszer az áfa mezőben kiválasztott Áfa kapcsán meghatározott áfa százalék alapján számítja ki az adót.</span><span class="sxs-lookup"><span data-stu-id="78619-129">When you select Percentage of sales tax in the Origin field, sales tax is calculated as a percentage of the sales tax that is selected in the Sales tax on sales tax field.</span></span> <span data-ttu-id="78619-130">Elsőként az áfa mezőben kiválasztott Áfa került kiszámításra.</span><span class="sxs-lookup"><span data-stu-id="78619-130">The sales tax that is selected in the Sales tax on sales tax field is calculated first.</span></span> <span data-ttu-id="78619-131">A második forgalmi adó kiszámítása az első forgalmi adó összege alapján történik.</span><span class="sxs-lookup"><span data-stu-id="78619-131">The second sales tax is then calculated based on the first sales tax amount.</span></span>
### <a name="example"></a><span data-ttu-id="78619-132">Példa</span><span class="sxs-lookup"><span data-stu-id="78619-132">Example</span></span>

<span data-ttu-id="78619-133">Az alábbi Áfakódok esetén:</span><span class="sxs-lookup"><span data-stu-id="78619-133">Given the following sales tax codes:</span></span>
-   <span data-ttu-id="78619-134">1. ADÓ = 10% a Nettó összeg százaléka módszer használata mellett</span><span class="sxs-lookup"><span data-stu-id="78619-134">DUTY 1 = 10%, using the Percentage of net amount method</span></span>
-   <span data-ttu-id="78619-135">2. ADÓ = 20%, Az afa százaléka módszerrel, ahol az 1. adó az áfa mezőben megadott Áfa</span><span class="sxs-lookup"><span data-stu-id="78619-135">DUTY 2 = 20%, using the Percentage of sales tax method, with Duty 1 in the Sales tax on sales tax field</span></span>
-   <span data-ttu-id="78619-136">ÁFA = 25% a Bruttó összeg százaléka módszer használata mellett</span><span class="sxs-lookup"><span data-stu-id="78619-136">SALESTAX = 25%, using the Percentage of gross amount method</span></span>

<span data-ttu-id="78619-137">Nettó összeg: 10,00 1. ADÓ: 10,00 x 10 % = 1,00 2. ADÓ: 1,00 x 20 = 0,20 Bruttó összeg: 10,00 + 1,00 + 0,20 = 11,20 ÁFA: 11,20 x 25 % = 2.80 ADÓK és ÁFA összege: 1,00 + 0,20 + 2,80 = 4,00 Teljes összeg: 10,00 + 4,00 = 14,00</span><span class="sxs-lookup"><span data-stu-id="78619-137">Net amount: 10.00 DUTY 1: 10.00 x 10% = 1.00 DUTY 2: 1.00 x 20% = 0.20 Gross amount: 10.00 + 1.00 + 0.20 = 11.20 SALESTAX: 11.20 x 25% = 2.80 Total DUTIES and SALESTAX: 1.00 + 0.20 + 2.80 = 4.00 Total amount: 10.00 + 4.00 = 14.00</span></span>

| <span data-ttu-id="78619-138">**Megjegyzés**</span><span class="sxs-lookup"><span data-stu-id="78619-138">**Note**</span></span>                                                                                                                                                                                                                    |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="78619-139">Az adók kiszámítása során nem alkalmazhatók többszintű adók.</span><span class="sxs-lookup"><span data-stu-id="78619-139">Multilevel tax on tax calculations are not possible.</span></span> <span data-ttu-id="78619-140">Az adó kiszámításának alapja nem lehet olyan adó, amely eleve egy másik adó függvénye.</span><span class="sxs-lookup"><span data-stu-id="78619-140">A tax cannot be calculated based on a tax which already is calculated based on another tax.</span></span> <span data-ttu-id="78619-141">Több, az adókódoknál rögzített egyszintű adó is alkalmazható egy adott tranzakcióra.</span><span class="sxs-lookup"><span data-stu-id="78619-141">Multiple single level tax on tax codes can be calculated on a transaction.</span></span> |

## <a name="amount-per-unit"></a><span data-ttu-id="78619-142"> Egységenkénti összeg</span><span class="sxs-lookup"><span data-stu-id="78619-142">Amount per unit</span></span>
<span data-ttu-id="78619-143">Ha az Egységenkénti összeg lehetőséget választja az Kiindulás mezőben, az áfa kiszámítási módja: az egységenkénti fix összeg megszorozva a dokumentumsorban rögzített mennyiséggel.</span><span class="sxs-lookup"><span data-stu-id="78619-143">When you select Amount per unit in the Origin field, sales tax is calculated as a fixed amount per unit multiplied with the quantity entered on the document line.</span></span> <span data-ttu-id="78619-144">Kötelező kiválasztani egy egységet az Egység mezőben.</span><span class="sxs-lookup"><span data-stu-id="78619-144">A unit has to be selected in the Unit field.</span></span> <span data-ttu-id="78619-145">Az Áfaértékek oldal rögzíti az egységenkénti összeget.</span><span class="sxs-lookup"><span data-stu-id="78619-145">The amount per unit is specified in the Sales tax code values page.</span></span>
### <a name="example"></a><span data-ttu-id="78619-146">Példa</span><span class="sxs-lookup"><span data-stu-id="78619-146">Example</span></span>

<span data-ttu-id="78619-147">Az Áfakód beállítása a következő 1,20 USD egységenkénti összeg = doboz. Az értékesítési számla 25 db adott cikket tartalmazó sora esetén az Áfa-számítás módja: 25 x 1.20 = 30,00</span><span class="sxs-lookup"><span data-stu-id="78619-147">Sales tax code is set up as: USD 1.20 per unit = box On a sales invoice line 25 boxes of an item are sold Sales tax is calculated as 25 x 1.20 = 30.00</span></span>

| <span data-ttu-id="78619-148">**Megjegyzés**</span><span class="sxs-lookup"><span data-stu-id="78619-148">**Note**</span></span>                                                                                                                                                                                                 |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="78619-149">Ha a tranzakció rögzítése az áfakódban rögzítettől eltérő mértékegységben történik, úgy azt a rendszer automatikusan konvertálja a Mértékegység-konverzió oldalon beállított arányoknak megfelelően.</span><span class="sxs-lookup"><span data-stu-id="78619-149">If the transaction is entered in different unit than the unit specified on the sales tax code, it is converted automatically based on the unit conversions that are set up in the Unit conversions page.</span></span> |

###  <a name="amount-per-unit-additional-option"></a><span data-ttu-id="78619-150"> Egységenkénti összeg módszer, további beállítások</span><span class="sxs-lookup"><span data-stu-id="78619-150">Amount per unit, additional option</span></span>

<span data-ttu-id="78619-151">A Számítás lapon meg tudja adni, hogy az egységenkénti adó más adókódok előtt kerüljön-e kiszámításra, valamint a nettó összeghez hozzáadásra kerüljön-e, mielőtt a Kiindulás = Nettó összeg százaléka típusú adók alkalmazásra kerülnek.</span><span class="sxs-lookup"><span data-stu-id="78619-151">On the Calculation tab, you can select whether an amount per unit calculated tax is calculated before other tax codes and added to the net amount before other tax codes with Origin = Percentage of net amount are calculated.</span></span>

### <a name="examples"></a><span data-ttu-id="78619-152">Példák</span><span class="sxs-lookup"><span data-stu-id="78619-152">Examples</span></span>

<span data-ttu-id="78619-153">Tegyük fel, hogy 2 adókódot alkalmazunk egy tranzakció kapcsán:</span><span class="sxs-lookup"><span data-stu-id="78619-153">Assume we calculate 2 tax codes on a transaction:</span></span>

-   <span data-ttu-id="78619-154">ADÓ: Kiindulás = Egységenkénti összeg, valamint egy áfa, melynek beállított értéke: 5,00 egységenként (db)</span><span class="sxs-lookup"><span data-stu-id="78619-154">DUTY: Origin = Amount per unit and a sales tax, the value is set to 5.00 per unit = pcs</span></span>
-   <span data-ttu-id="78619-155">ÁFA: Kiindulás = a beállított érték 25%, az alábbi példákban szemléltetett módon</span><span class="sxs-lookup"><span data-stu-id="78619-155">SALESTAX: Origin = as shown in the examples below, the value is set to 25%</span></span>

<span data-ttu-id="78619-156">Eladunk 1 darabot az adott cikkből 10,00 egységáron</span><span class="sxs-lookup"><span data-stu-id="78619-156">We sell 1 piece of an item at a unit price of 10.00</span></span>
#### <a name="example-1"></a><span data-ttu-id="78619-157">1. példa</span><span class="sxs-lookup"><span data-stu-id="78619-157">Example 1</span></span>

<span data-ttu-id="78619-158">ÁFA: Kiindulás = Bruttó összeg százaléka módszer. Az Áfa előtt számolandó lehetőségnek nincs jelentősége, mivel az ÁFA a bruttó összeg százalékaként kerül kiszámításra.</span><span class="sxs-lookup"><span data-stu-id="78619-158">SALESTAX: Origin = Percentage of gross amount method The Calculate before sales tax option has no effect, because SALESTAX is calculated as a percentage of the gross amount.</span></span> <span data-ttu-id="78619-159">ADÓ: 1 x 5,00 = 5,00 Bruttó összeg: 10,00 + 5,00 = 15,00 ÁFA: 15,00 x 25% = 3,75 Áfa összesen: 5,00 + 3,75 = 8,75 Teljes összeg: 10,00 + 8,75 = 18,75</span><span class="sxs-lookup"><span data-stu-id="78619-159">DUTY: 1 x 5.00 = 5.00 Gross amount: 10.00 + 5.00 = 15.00 SALESTAX: 15.00 x 25% = 3.75 Total sales tax: 5.00 + 3.75 = 8.75 Total amount: 10.00 + 8.75 = 18.75</span></span>

#### <a name="example-2"></a><span data-ttu-id="78619-160">2. példa</span><span class="sxs-lookup"><span data-stu-id="78619-160">Example 2</span></span>

<span data-ttu-id="78619-161">ÁFA: Kiindulás = Nettó összeg százaléka. Az Áfa előtt számolandó lehetőség nincs kiválasztva az ADÓ kiszámításhoz.</span><span class="sxs-lookup"><span data-stu-id="78619-161">SALESTAX: Origin = Percentage of net amount The Calculate before sales tax option is not selected for the DUTY calculation.</span></span> <span data-ttu-id="78619-162">Nettó összeg: 10,00 ADÓ: 1 x 5,00 = 5,00 ÁFA: 10,00 x 25% = 2,50 Áfa összesen: 5,00 + 2,50 = 7,50 Teljes összeg: 10,00 + 7,50 = 17,50</span><span class="sxs-lookup"><span data-stu-id="78619-162">Net amount: 10.00 DUTY: 1 x 5.00 = 5.00 SALESTAX: 10.00 x 25% = 2.50 Total sales tax: 5.00 + 2.50 = 7.50 Total amount: 10.00 + 7.50 = 17.50</span></span>

#### <a name="example-3"></a><span data-ttu-id="78619-163">3. példa</span><span class="sxs-lookup"><span data-stu-id="78619-163">Example 3</span></span>

<span data-ttu-id="78619-164">ÁFA: Kiindulás = Nettó összeg százaléka. Az Áfa előtt számolandó lehetőség ki van választva az ADÓ kiszámításhoz.</span><span class="sxs-lookup"><span data-stu-id="78619-164">SALESTAX: Origin = Percentage of net amount The Calculate before sales tax option is selected for the DUTY calculation.</span></span> <span data-ttu-id="78619-165">Nettó összeg: 10,00 ADÓ: 1 x 5,00 = 5,00 ÁFA: (10,00 + 5,00) x 25 % = 3,75 Áfa összesen: 5,00 + 3,75 = 8,75 Teljes összeg: 10,00 + 8,75 = 18,75</span><span class="sxs-lookup"><span data-stu-id="78619-165">Net amount: 10.00 DUTY: 1 x 5.00 = 5.00 SALESTAX: (10.00 + 5.00) x 25% = 3.75 Total sales tax: 5.00 + 3.75 = 8.75 Total amount: 10.00 + 8.75 = 18.75</span></span>

#### <a name="example-4"></a><span data-ttu-id="78619-166">4. példa</span><span class="sxs-lookup"><span data-stu-id="78619-166">Example 4</span></span>

<span data-ttu-id="78619-167">Az 1. és a 3. példa eredménye megegyezik, mivel ezekben a példákban csak egy adó szerepel.</span><span class="sxs-lookup"><span data-stu-id="78619-167">The result of Example 3 and Example 1 is the same, because there is only one duty.</span></span> <span data-ttu-id="78619-168">Tegyük fel, hogy két ADÓ létezik, és az áfaszámítás szempontjából a nettó összeg csak az egyiket tartalmazza: 1. ADÓ: 5,00 az Egységenkénti összeg módszerrel és ki van választva Az áfa előtt számítandó lehetőség; 2. ADÓ: 2,50 az Egységenkénti összeg módszerrel és nincs kiválasztva Az áfa előtt számítandó lehetőség; Áfa: 25% a Nettó összeg százaléka módszerrel: 10,00 1. ADÓ: 1 x 5,00 = 5.00 2. ADÓ: 1 x 2,50 = 2.50 Áfaköteles nettó összeg: 10,00 + 5,00 = 15,00 ÁFA: 15,00 x 25% = 3,75 Áfa összesen, adókkal együtt: 5,00 + 2,50 + 3,75 = 11.25 Teljes összeg: 10,00 + 11,25 = 21,25; A 25%-os ÁFA a nettó összeg értékére kerül kiszámításra (10,00) + 1. ADÓ (5,00) = 15,00.</span><span class="sxs-lookup"><span data-stu-id="78619-168">Assume that you have two DUTIES, and only one of them is included in the net amount for the sales tax calculation: DUTY 1: 5.00, using the Amount per unit method, and the Calculate before sales tax option is selected DUTY 2: 2.50, using the Amount per unit method, and the Calculate before sales tax option is not selected Sales tax: 25%, using the Percentage of net amount method Net amount: 10.00 DUTY 1: 1 x 5.00 = 5.00 DUTY 2: 1 x 2.50 = 2.50 Net amount subject to sales tax: 10.00 + 5.00 = 15.00 SALESTAX: 15.00 x 25% = 3.75 Total sales taxes, including duties: 5.00 + 2.50 + 3.75 = 11.25 Total amount: 10.00 + 11.25 = 21.25 The 25% SALESTAX is calculated for the sum of the net amount (10.00) + DUTY 1 (5.00) = 15.00.</span></span> <span data-ttu-id="78619-169">A 2. ADÓT a program az áfa kiszámítása után adja hozzá az adó összegéhez.</span><span class="sxs-lookup"><span data-stu-id="78619-169">DUTY 2 is added to the tax amount after the sales tax is calculated.</span></span>

## <a name="calculated-percentage-of-net-amount"></a><span data-ttu-id="78619-170"> Nettó összeg számított százalékos értéke</span><span class="sxs-lookup"><span data-stu-id="78619-170">Calculated percentage of net amount</span></span>
<span data-ttu-id="78619-171">A Nettó összeg számított százalékos értéke az adott dokumentumra vagy naplóra vonatkozó Az összegek tartalmazzák az áfát paraméter beállításának függvényében más-más módon számítja ki az adó értékét.</span><span class="sxs-lookup"><span data-stu-id="78619-171">The Calculated percentage of net amount handles tax calculation differently depending on the setting of the Amounts include sales tax parameter for the document or journal.</span></span>
### <a name="example-1"></a><span data-ttu-id="78619-172">1. példa</span><span class="sxs-lookup"><span data-stu-id="78619-172">Example 1</span></span>

<span data-ttu-id="78619-173">Amennyiben a dokumentum / napló beállítása: Az összegek tartalmazzák az áfát = Igen Tranzakciósor összege: 10,00 Adókulcs: 25% Áfa: Tranzakciósor összege x adókulcs (10,00 x 25%) = 2,50 Adóalap összege (kiindulási összeg): Tranzakciósor összege - áfa = (10,00 - 2,50) = 7,50</span><span class="sxs-lookup"><span data-stu-id="78619-173">Document / journal is set to Amounts include sales tax = Yes Transaction line amount: 10.00 Tax rate: 25% Sales tax: Transaction line amount x tax rate (10.00 x 25%) = 2.50 Tax base amount (origin amount): Transaction line amount - Sales tax (10.00 - 2.50) = 7.50</span></span>

### <a name="example-2"></a><span data-ttu-id="78619-174">2. példa</span><span class="sxs-lookup"><span data-stu-id="78619-174">Example 2</span></span>

<span data-ttu-id="78619-175">Amennyiben a dokumentum / napló beállítása: Az összegek tartalmazzák az áfát = Nem Tranzakciósor összege: 10,00 Adókulcs: 25% Áfa: (Tranzakciósor összege x adókulcs) / (100 - adókulcs) (10,00 x 25%) / (100% - 25%) = 3,33 Adóalap összege = 10,00</span><span class="sxs-lookup"><span data-stu-id="78619-175">Document / journal is set to Amounts include sales tax = No Transaction line amount: 10.00 Tax rate: 25% Sales tax: (Transaction line amount x tax rate) / (100 - tax rate) (10.00 x 25%) / (100% - 25%) = 3.33 Tax base amount (origin amount): Transaction line amount = 10.00</span></span>



<a name="additional-resources"></a><span data-ttu-id="78619-176">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="78619-176">Additional resources</span></span>
--------

[<span data-ttu-id="78619-177">Áfaérték a Számítás alapja és a Számítási módszerek lapján</span><span class="sxs-lookup"><span data-stu-id="78619-177">Sales tax rates based on the Marginal base and Calculation methods</span></span>](marginal-base-field.md)

[<span data-ttu-id="78619-178">Teljesösszeg- és intervallumszámítási opciók áfakódokhoz</span><span class="sxs-lookup"><span data-stu-id="78619-178">Whole amount and Interval calculation options for sales tax codes</span></span>](whole-amount-interval-options-sales-tax-codes.md)



