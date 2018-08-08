---
title: "Kamatlábak beállítása kamatkódhoz"
description: "A kamatkódok olyan beállításokat tartalmaznak, amelyek meghatározzák, hogy mikor kerül sor kamat felszámítására, és hogyan történik annak kiszámítása a hátralékos számlákon."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: Interest
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 59402
ms.assetid: 3b945333-1eaf-4658-ab5a-1a7791a7eb40
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: d9747ba144d56c9410846769e5465372c89ea111
ms.openlocfilehash: 665c58fd29fb986bf51e10f5814c4793940c0a47
ms.contentlocale: hu-hu
ms.lasthandoff: 08/07/2018

---

# <a name="set-up-interest-rates-for-an-interest-code"></a><span data-ttu-id="c6403-103">Kamatlábak beállítása kamatkódhoz</span><span class="sxs-lookup"><span data-stu-id="c6403-103">Set up interest rates for an interest code</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c6403-104">A kamatkódok olyan beállításokat tartalmaznak, amelyek meghatározzák, hogy mikor kerül sor kamat felszámítására, és hogyan történik annak kiszámítása a hátralékos számlákon.</span><span class="sxs-lookup"><span data-stu-id="c6403-104">Interest codes contain settings that determine when interest is charged and how it is calculated on overdue accounts.</span></span>

<span data-ttu-id="c6403-105">Megteheti, hogy egyetlen kamatkódot állít be, és azt alkalmazza több vevő feladási profilra, számlázási kódra, illetve adott számlasorokra.</span><span class="sxs-lookup"><span data-stu-id="c6403-105">You can set up a single interest code and apply it to multiple customer posting profiles, billing codes, or to specific invoice lines.</span></span> <span data-ttu-id="c6403-106">Ha a kamatkód adatai megváltoznak, a kódot használó összes funkció automatikusan végrehajtja a változtatásokat az új tranzakciókon.</span><span class="sxs-lookup"><span data-stu-id="c6403-106">When the interest code details are changed, all features that use the code will automatically implement the changes on new transactions.</span></span> <span data-ttu-id="c6403-107">Minden egyes kamatkódnál kétféle típusú kamatlábat állíthat be:</span><span class="sxs-lookup"><span data-stu-id="c6403-107">For each interest code, you can set up two types of rates:</span></span>
-   <span data-ttu-id="c6403-108">Kamatbevételek kamatlábai − Ezek olyan bevételt jelentenek, amely a számlákra vagy kamatlevelekre kamat felszámításával keletkezik.</span><span class="sxs-lookup"><span data-stu-id="c6403-108">Rates for interest earnings − These represent revenue that is earned by charging interest on invoices or interest notes.</span></span>
-   <span data-ttu-id="c6403-109">Kamatfizetések kamatlábai − Ezek olyan költséget jelentenek, amely jóváírásokra fizetett kamat címén keletkezik.</span><span class="sxs-lookup"><span data-stu-id="c6403-109">Rates for interest payments − These represent a cost that is paid for interest on credit notes.</span></span>

<span data-ttu-id="c6403-110">Ezen két kamatlábtípus mindegyike létezhet ugyanabban az időben és ugyanazon kamatkódon.</span><span class="sxs-lookup"><span data-stu-id="c6403-110">Both of these rate types can exist at the same time and in the same interest code.</span></span> <span data-ttu-id="c6403-111">A kamatlábak háromféle számítástípuson alapulhatnak:</span><span class="sxs-lookup"><span data-stu-id="c6403-111">Interest rates can be based on three calculation types:</span></span>
-   <span data-ttu-id="c6403-112">Százalékérték szerinti kamat.</span><span class="sxs-lookup"><span data-stu-id="c6403-112">Interest by percentage.</span></span>
-   <span data-ttu-id="c6403-113">Összeg szerinti kamat.</span><span class="sxs-lookup"><span data-stu-id="c6403-113">Interest by amount.</span></span>
-   <span data-ttu-id="c6403-114">Tartomány szerinti kamat, amely egyetlen százalékértéket vagy összeget eredményez.</span><span class="sxs-lookup"><span data-stu-id="c6403-114">Interest by range, which results in a single percentage or amount.</span></span>

<span data-ttu-id="c6403-115">Ha a kamatszámításra egy kamatkód segítségével kerül sor, külön kamatlevél jön létre mindegyik kamatlábhoz, amely hatályban van abban az időszakban, amikor a kifizetés túllépte a tranzakció esedékességi dátumát.</span><span class="sxs-lookup"><span data-stu-id="c6403-115">When an interest code is used to calculate interest, a separate interest note is created for each interest rate that is in effect during the time that the payment has exceeded the transaction due date.</span></span> <span data-ttu-id="c6403-116">Használja a **Nyereségek** lapját a **Kamat kód** lapon a kamat kamatlábainak beállításához, amit a kamat felszámítása által kapott.</span><span class="sxs-lookup"><span data-stu-id="c6403-116">You use the **Earnings** tab on the **Interest code** page to set up interest rates for interest that you earn by charging interest.</span></span> <span data-ttu-id="c6403-117">Használja a **Kifizetések** oldalt a kamat kamatlábainak beállításához, amit kifizet.</span><span class="sxs-lookup"><span data-stu-id="c6403-117">Use the **Payments** tab to set up interest rates for interest that you pay.</span></span>

## <a name="interest-rates-based-on-a-percentage"></a><span data-ttu-id="c6403-118">Százalékértékek alapuló kamatlábak</span><span class="sxs-lookup"><span data-stu-id="c6403-118">Interest rates based on a percentage</span></span>
<span data-ttu-id="c6403-119">Beállíthat kamatlábakat, amelyek egy megadott százalékot számítanak.</span><span class="sxs-lookup"><span data-stu-id="c6403-119">You can set up interest rates that calculate a specified percentage.</span></span>

- <span data-ttu-id="c6403-120">A kamat összege az összes pénznemre vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="c6403-120">Interest amount applies to all currencies.</span></span>
- <span data-ttu-id="c6403-121">A nem kötelező kamat összeg határaival lehet megadni.</span><span class="sxs-lookup"><span data-stu-id="c6403-121">Optional interest amount limits can be entered.</span></span>
- <span data-ttu-id="c6403-122"><strong>Százalék</strong> van kiválasztva** <strong>a Kamat számítása alapján</strong> mezőben a <strong>Kamatkódok beállítása</strong> oldalon.</span><span class="sxs-lookup"><span data-stu-id="c6403-122"><strong>Percentage</strong> is selected** <strong>in the **Calculate interest based on</strong> field on the <strong>Set up Interest codes</strong> page.</span></span>

<span data-ttu-id="c6403-123">Például, ha olyan kamatkódot szeretne beállítani, amely kéthavonta 5 % kamatot számít fel, miután a számla kifizetése túllépte a tranzakció esedékességi dátumát, akkor írjon be 2 értéket az **Összes kamat kiszámítása** mezőbe, és jelölje be **Hónap** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c6403-123">For example, to set up an interest code that assesses 5 percent interest for every two months that the invoice payment exceeds the transaction due date, you would enter 2 in the **Calculate interest every** field and select **Month**.</span></span>

## <a name="interest-rates-based-on-amounts"></a><span data-ttu-id="c6403-124">Összegeken alapuló kamatlábak</span><span class="sxs-lookup"><span data-stu-id="c6403-124">Interest rates based on amounts</span></span>
<span data-ttu-id="c6403-125">Beállíthat olyan kamatlábakat, amelyek egy megadott összeget számítanak ki pénznemenként.</span><span class="sxs-lookup"><span data-stu-id="c6403-125">You can set up interest rates that calculate a specified amount per currency.</span></span>
- <span data-ttu-id="c6403-126">Minden egyes pénznemhez egy kamatösszeg van megadva a kamat kódban.</span><span class="sxs-lookup"><span data-stu-id="c6403-126">An interest amount is specified for each currency in the interest code.</span></span>
- <span data-ttu-id="c6403-127">A nem kötelező kamat összeg határaival lehet megadni.</span><span class="sxs-lookup"><span data-stu-id="c6403-127">Optional interest amount limits can be entered.</span></span>
- <span data-ttu-id="c6403-128">**Összeg** van kiválasztva **Számítása kamat alapján** mezőben **Kamat kódok beállítása** oldalon.</span><span class="sxs-lookup"><span data-stu-id="c6403-128">**Amount** is selected in the **Calculate interest based on** field on the **Set up Interest codes** page.</span></span>

<span data-ttu-id="c6403-129">Például, ha olyan kamatkódot szeretne beállítani, amely 20 naponta 25,00 egység kamatot számít fel, miután a számla kifizetése túllépte a tranzakció esedékességi dátumát, akkor írjon be 20 értéket az **Összes kamat kiszámítása** mezőbe és válassza ki a **Nap** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c6403-129">For example, to set up an interest code that assesses interest of 25.00 for every 20 days that the invoice payment exceeds the transaction due date, you would enter 20 in the **Calculate interest every** field and select **Day**.</span></span>

## <a name="interest-rates-based-on-ranges"></a><span data-ttu-id="c6403-130">Tartományokon alapuló kamatlábak</span><span class="sxs-lookup"><span data-stu-id="c6403-130">Interest rates based on ranges</span></span>
<span data-ttu-id="c6403-131">Beállíthat olyan kamatlábakat, amelyek változnak a lejárt összegtől, az összeg késedelmes napjainak számától vagy az összeg késedelmes hónapjainak számától függően.</span><span class="sxs-lookup"><span data-stu-id="c6403-131">You can set up interest rates that vary depending on the overdue amount, the number of days that the amount is late, or the number of months that the amount is late.</span></span>
-   <span data-ttu-id="c6403-132">Használhatja a **Pénznemenkénti Bevételek** lapot a minden egyes pénznemhez tartozó konkrét kamat beállításának meghatozásához.</span><span class="sxs-lookup"><span data-stu-id="c6403-132">You can use the **Earnings by Currency** tab to define specific interest settings for each currency.</span></span> <span data-ttu-id="c6403-133">Így van ott is, ahol meghatározza a tartományt.</span><span class="sxs-lookup"><span data-stu-id="c6403-133">This is also where you will define the range.</span></span>
-   <span data-ttu-id="c6403-134">Használja a **Tartományok** gombot a beállítani kívánt tartomány megjelenítő sorok hozzáadására.</span><span class="sxs-lookup"><span data-stu-id="c6403-134">Use the **Ranges** button to add lines that represent the ranges that you want to set up.</span></span> <span data-ttu-id="c6403-135">A **Származó** érték jelzi a tartomány kezdetét és a **Kamat érték** száma vagy egy százalékot vagy egy összeget jelez a **Számítás kamat alapján** mezőben a **Kamat kódok beállítása** oldalon történő kiválasztástól függően.</span><span class="sxs-lookup"><span data-stu-id="c6403-135">The **From** value represents the beginning of the range and the **Interest value** number represents either a percentage or an amount, depending on the selection in the **Calculate interest based on** field on the **Set up Interest codes** page.</span></span>

## <a name="example-1-interest-by-range--amount"></a><span data-ttu-id="c6403-136">1. példa: Kamat tartomány szerint = Összeg</span><span class="sxs-lookup"><span data-stu-id="c6403-136">Example 1: Interest by range = Amount</span></span>
<span data-ttu-id="c6403-137">Ön olyan kamatkódot állít be, amely kamatot számít fel minden három hónapban egyszer azt követően, hogy a számla kifizetése túllépi a tranzakció esedékességi dátumát.</span><span class="sxs-lookup"><span data-stu-id="c6403-137">You set up an interest code that assesses interest one time for every three months that the invoice payment exceeds the transaction due date.</span></span> <span data-ttu-id="c6403-138">A számítást százalékos kamatmértékre szeretné alapozni, sávos módon az összegintervallumok szerint.</span><span class="sxs-lookup"><span data-stu-id="c6403-138">You want to base the calculation on a percentage interest value, according to stepped amount intervals.</span></span> <span data-ttu-id="c6403-139">A kamat értéke 1 százalék lesz legfeljebb 1.000,00 számlaértékig, 2 százalék 1.001,00 és 5.000,00 érték között, és 3 százalék az 5.000,00 feletti összegekre.</span><span class="sxs-lookup"><span data-stu-id="c6403-139">The interest value will be 1 percent for invoice amounts up to 1,000.00, 2 percent for amounts from 1,001.00 to 5,000.00, and 3 percent for amounts larger than 5,000.00.</span></span> <span data-ttu-id="c6403-140">A kamatkód mezőinek értékét a következőképpen kell beállítani.</span><span class="sxs-lookup"><span data-stu-id="c6403-140">You set up the interest code field values as follows.</span></span>

| <span data-ttu-id="c6403-141">**Mezőnév**</span><span class="sxs-lookup"><span data-stu-id="c6403-141">**Field name**</span></span>                  | <span data-ttu-id="c6403-142">**Mező értéke**</span><span class="sxs-lookup"><span data-stu-id="c6403-142">**Field value**</span></span> |
|---------------------------------|-----------------|
| <span data-ttu-id="c6403-143">**Kamatkód**</span><span class="sxs-lookup"><span data-stu-id="c6403-143">**Interest code**</span></span>               | <span data-ttu-id="c6403-144">3M%ByAmt</span><span class="sxs-lookup"><span data-stu-id="c6403-144">3M%ByAmt</span></span>        |
| <span data-ttu-id="c6403-145">**Kamatszámítás gyakorisága:**</span><span class="sxs-lookup"><span data-stu-id="c6403-145">**Calculate interest every**</span></span>    | <span data-ttu-id="c6403-146">3/Hónap</span><span class="sxs-lookup"><span data-stu-id="c6403-146">3/Month</span></span>         |
| <span data-ttu-id="c6403-147">**Kamat tartománya**</span><span class="sxs-lookup"><span data-stu-id="c6403-147">**Interest by range**</span></span>           | <span data-ttu-id="c6403-148">Összeg</span><span class="sxs-lookup"><span data-stu-id="c6403-148">Amount</span></span>          |
| <span data-ttu-id="c6403-149">**Kamat kiszámítása a következő alapján:**</span><span class="sxs-lookup"><span data-stu-id="c6403-149">**Calculate interest based on**</span></span> | <span data-ttu-id="c6403-150">Százalék</span><span class="sxs-lookup"><span data-stu-id="c6403-150">Percentage</span></span>      |

<span data-ttu-id="c6403-151">A tartomány adatait a következőképpen kell beállítani.</span><span class="sxs-lookup"><span data-stu-id="c6403-151">You set up the range information as follows.</span></span>

| <span data-ttu-id="c6403-152">**Kezdő érték**</span><span class="sxs-lookup"><span data-stu-id="c6403-152">**From value**</span></span> | <span data-ttu-id="c6403-153">**Kamat értéke**</span><span class="sxs-lookup"><span data-stu-id="c6403-153">**Interest value**</span></span> |
|----------------|--------------------|
| <span data-ttu-id="c6403-154">0</span><span class="sxs-lookup"><span data-stu-id="c6403-154">0</span></span>              | <span data-ttu-id="c6403-155">1</span><span class="sxs-lookup"><span data-stu-id="c6403-155">1</span></span>                  |
| <span data-ttu-id="c6403-156">1,001</span><span class="sxs-lookup"><span data-stu-id="c6403-156">1,001</span></span>          | <span data-ttu-id="c6403-157">2</span><span class="sxs-lookup"><span data-stu-id="c6403-157">2</span></span>                  |
| <span data-ttu-id="c6403-158">5,001</span><span class="sxs-lookup"><span data-stu-id="c6403-158">5,001</span></span>          | <span data-ttu-id="c6403-159">3</span><span class="sxs-lookup"><span data-stu-id="c6403-159">3</span></span>                  |


## <a name="example-2-interest-by-range--days"></a><span data-ttu-id="c6403-160">2. példa: Kamat tartomány szerint = Napok</span><span class="sxs-lookup"><span data-stu-id="c6403-160">Example 2: Interest by range = Days</span></span>
--------------------------------------------------

<span data-ttu-id="c6403-161">Ön olyan kamatkódot állít be, amely kamatot számít fel 15 naponként egyszer azt követően, hogy a számla kifizetése túllépi a tranzakció esedékességi dátumát.</span><span class="sxs-lookup"><span data-stu-id="c6403-161">You set up an interest code that assesses interest one time for every 15 days that the invoice payment exceeds the transaction due date.</span></span> <span data-ttu-id="c6403-162">A számítást összegként megadott kamatmértékre szeretné alapozni, sávos módon napi intervallumok szerint.</span><span class="sxs-lookup"><span data-stu-id="c6403-162">You want to base the calculation on an amount interest value, according to stepped day intervals.</span></span> <span data-ttu-id="c6403-163">A kamat mértéke 10,00 egység lesz 15 naponta az első 60 napban, 15,00 egység 15 naponta 61.–90. nap között, és 20,00 egység 15 naponta a 91. naptól kezdődően.</span><span class="sxs-lookup"><span data-stu-id="c6403-163">The interest value will be 10.00 per 15 days during the first 60 days, 15.00 per 15 days during days 61 to 90, and 20.00 per 15 days from day 91 and after.</span></span> <span data-ttu-id="c6403-164">A kamatkód mezőinek értékét a következőképpen kell beállítani.</span><span class="sxs-lookup"><span data-stu-id="c6403-164">You set up the interest code field values as follows.</span></span>

| <span data-ttu-id="c6403-165">**Mezőnév**</span><span class="sxs-lookup"><span data-stu-id="c6403-165">**Field name**</span></span>                  | <span data-ttu-id="c6403-166">**Mező értéke**</span><span class="sxs-lookup"><span data-stu-id="c6403-166">**Field value**</span></span> |
|---------------------------------|-----------------|
| <span data-ttu-id="c6403-167">**Kamatkód**</span><span class="sxs-lookup"><span data-stu-id="c6403-167">**Interest code**</span></span>               | <span data-ttu-id="c6403-168">15DAmtXDay</span><span class="sxs-lookup"><span data-stu-id="c6403-168">15DAmtXDay</span></span>      |
| <span data-ttu-id="c6403-169">**Kamatszámítás gyakorisága:**</span><span class="sxs-lookup"><span data-stu-id="c6403-169">**Calculate interest every**</span></span>    | <span data-ttu-id="c6403-170">15/Nap</span><span class="sxs-lookup"><span data-stu-id="c6403-170">15/Day</span></span>          |
| <span data-ttu-id="c6403-171">**Kamat tartománya**</span><span class="sxs-lookup"><span data-stu-id="c6403-171">**Interest by range**</span></span>           | <span data-ttu-id="c6403-172">Napok</span><span class="sxs-lookup"><span data-stu-id="c6403-172">Days</span></span>            |
| <span data-ttu-id="c6403-173">**Kamat kiszámítása a következő alapján:**</span><span class="sxs-lookup"><span data-stu-id="c6403-173">**Calculate interest based on**</span></span> | <span data-ttu-id="c6403-174">Összeg</span><span class="sxs-lookup"><span data-stu-id="c6403-174">Amount</span></span>          |

<span data-ttu-id="c6403-175">A tartomány adatait a következőképpen kell beállítani.</span><span class="sxs-lookup"><span data-stu-id="c6403-175">You set up the range information as follows.</span></span>

| <span data-ttu-id="c6403-176">**Kezdő érték**</span><span class="sxs-lookup"><span data-stu-id="c6403-176">**From value**</span></span> | <span data-ttu-id="c6403-177">**Kamat értéke**</span><span class="sxs-lookup"><span data-stu-id="c6403-177">**Interest value**</span></span> |
|----------------|--------------------|
| <span data-ttu-id="c6403-178">0</span><span class="sxs-lookup"><span data-stu-id="c6403-178">0</span></span>              | <span data-ttu-id="c6403-179">10</span><span class="sxs-lookup"><span data-stu-id="c6403-179">10</span></span>                 |
| <span data-ttu-id="c6403-180">61</span><span class="sxs-lookup"><span data-stu-id="c6403-180">61</span></span>             | <span data-ttu-id="c6403-181">15.</span><span class="sxs-lookup"><span data-stu-id="c6403-181">15</span></span>                 |
| <span data-ttu-id="c6403-182">91</span><span class="sxs-lookup"><span data-stu-id="c6403-182">91</span></span>             | <span data-ttu-id="c6403-183">20</span><span class="sxs-lookup"><span data-stu-id="c6403-183">20</span></span>                 |


## <a name="example-3-interest-by-range--months"></a><span data-ttu-id="c6403-184">3. példa: Kamat tartomány szerint = Hónapok</span><span class="sxs-lookup"><span data-stu-id="c6403-184">Example 3: Interest by range = Months</span></span>
----------------------------------------------------

<span data-ttu-id="c6403-185">Ön olyan kamatkódot állít be, amely kamatot számít fel minden hónapban egyszer azt követően, hogy a számla kifizetése túllépi a tranzakció esedékességi dátumát.</span><span class="sxs-lookup"><span data-stu-id="c6403-185">You set up an interest code that assesses interest one time for every month that the invoice payment exceeds the transaction due date.</span></span> <span data-ttu-id="c6403-186">A számítást százalékos kamatmértékre szeretné alapozni, sávos módon hónapok szerint.</span><span class="sxs-lookup"><span data-stu-id="c6403-186">You want to base the calculation on a percentage interest value, according to stepped month intervals.</span></span> <span data-ttu-id="c6403-187">A kamat mértéke 1,5 százalék lesz havonta az első három késedelmes hónapban, 2,0 százalék havonta a második három hónapban, és 2,5 százalék havonta az első hat hónapot követő minden hónapban.</span><span class="sxs-lookup"><span data-stu-id="c6403-187">The interest value will be 1.5 percent per month for the first three overdue months, 2.0 percent per month for the second three months, and 2.5 percent per month for each month beyond the first six months.</span></span> <span data-ttu-id="c6403-188">A kamatkód mezőinek értékét a következőképpen kell beállítani.</span><span class="sxs-lookup"><span data-stu-id="c6403-188">You set up the interest code field values as follows.</span></span>

| <span data-ttu-id="c6403-189">**Mezőnév**</span><span class="sxs-lookup"><span data-stu-id="c6403-189">**Field name**</span></span>                  | <span data-ttu-id="c6403-190">**Mező értéke**</span><span class="sxs-lookup"><span data-stu-id="c6403-190">**Field value**</span></span> |
|---------------------------------|-----------------|
| <span data-ttu-id="c6403-191">**Kamatkód**</span><span class="sxs-lookup"><span data-stu-id="c6403-191">**Interest code**</span></span>               | <span data-ttu-id="c6403-192">1M%ByMth</span><span class="sxs-lookup"><span data-stu-id="c6403-192">1M%ByMth</span></span>        |
| <span data-ttu-id="c6403-193">**Kamatszámítás gyakorisága:**</span><span class="sxs-lookup"><span data-stu-id="c6403-193">**Calculate interest every**</span></span>    | <span data-ttu-id="c6403-194">1/hónap</span><span class="sxs-lookup"><span data-stu-id="c6403-194">1/Month</span></span>         |
| <span data-ttu-id="c6403-195">**Kamat tartománya**</span><span class="sxs-lookup"><span data-stu-id="c6403-195">**Interest by range**</span></span>           | <span data-ttu-id="c6403-196">Hónapok</span><span class="sxs-lookup"><span data-stu-id="c6403-196">Months</span></span>          |
| <span data-ttu-id="c6403-197">**Kamat kiszámítása a következő alapján:**</span><span class="sxs-lookup"><span data-stu-id="c6403-197">**Calculate interest based on**</span></span> | <span data-ttu-id="c6403-198">Százalék</span><span class="sxs-lookup"><span data-stu-id="c6403-198">Percentage</span></span>      |

<span data-ttu-id="c6403-199">A tartomány adatait a következőképpen kell beállítani.</span><span class="sxs-lookup"><span data-stu-id="c6403-199">You set up the range information as follows.</span></span>

| <span data-ttu-id="c6403-200">**Kezdő érték**</span><span class="sxs-lookup"><span data-stu-id="c6403-200">**From value**</span></span> | <span data-ttu-id="c6403-201">**Kamat értéke**</span><span class="sxs-lookup"><span data-stu-id="c6403-201">**Interest value**</span></span> |
|----------------|--------------------|
| <span data-ttu-id="c6403-202">0</span><span class="sxs-lookup"><span data-stu-id="c6403-202">0</span></span>              | <span data-ttu-id="c6403-203">1.5</span><span class="sxs-lookup"><span data-stu-id="c6403-203">1.5</span></span>                |
| <span data-ttu-id="c6403-204">4</span><span class="sxs-lookup"><span data-stu-id="c6403-204">4</span></span>              | <span data-ttu-id="c6403-205">2</span><span class="sxs-lookup"><span data-stu-id="c6403-205">2</span></span>                  |
| <span data-ttu-id="c6403-206">7</span><span class="sxs-lookup"><span data-stu-id="c6403-206">7</span></span>              | <span data-ttu-id="c6403-207">2,5</span><span class="sxs-lookup"><span data-stu-id="c6403-207">2.5</span></span>                |

## <a name="new-versions"></a><span data-ttu-id="c6403-208">Új verziók</span><span class="sxs-lookup"><span data-stu-id="c6403-208">New versions</span></span>
<span data-ttu-id="c6403-209">A kamatkódok dátum érvényességek.</span><span class="sxs-lookup"><span data-stu-id="c6403-209">Interest codes are date effective.</span></span> <span data-ttu-id="c6403-210">Ha szeretné módosítani a kamatlábat, létrehozhat egy **új verziót**, ami a jövőbeli dátum szerint hatályos.</span><span class="sxs-lookup"><span data-stu-id="c6403-210">If you want to modify the interest rate, you can create a **new version** that is effective as of a future date.</span></span>

<span data-ttu-id="c6403-211">Különböző verziói megtekintéséhez használja a **Dátum, mint** menüt lehetőséget a fordulónap kiválasztásához.</span><span class="sxs-lookup"><span data-stu-id="c6403-211">To view different versions, you can use the **As of Date** menu choice to select the cutoff date.</span></span> <span data-ttu-id="c6403-212">Bejelölheti a **Összes rekord megjelenítése** lehetőséget a lapon megjelenő összes kamatkód megtekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="c6403-212">You can also select the **Display all records** to view all interest codes in the page.</span></span>




