---
title: Kamatlábak beállítása kamatkódhoz
description: A kamatkódok olyan beállításokat tartalmaznak, amelyek meghatározzák, hogy mikor kerül sor kamat felszámítására, és hogyan történik annak kiszámítása a hátralékos számlákon.
author: ShivamPandey-msft
ms.date: 02/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: Interest
audience: Application User
ms.reviewer: roschlom
ms.custom: 59402
ms.assetid: 3b945333-1eaf-4658-ab5a-1a7791a7eb40
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 62868c30d3ff60e51d99c71b743ab0bbb3c87451
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5835196"
---
# <a name="set-up-interest-rates-for-an-interest-code"></a><span data-ttu-id="ac352-103">Kamatlábak beállítása kamatkódhoz</span><span class="sxs-lookup"><span data-stu-id="ac352-103">Set up interest rates for an interest code</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ac352-104">A kamatkódok olyan beállításokat tartalmaznak, amelyek meghatározzák, hogy mikor kerül sor kamat felszámítására, és hogyan történik annak kiszámítása a hátralékos számlákon.</span><span class="sxs-lookup"><span data-stu-id="ac352-104">Interest codes contain settings that determine when interest is charged and how it is calculated on overdue accounts.</span></span>

<span data-ttu-id="ac352-105">Megteheti, hogy egyetlen kamatkódot állít be, és azt alkalmazza több vevő feladási profilra, számlázási kódra, illetve adott számlasorokra.</span><span class="sxs-lookup"><span data-stu-id="ac352-105">You can set up a single interest code and apply it to multiple customer posting profiles, billing codes, or to specific invoice lines.</span></span> <span data-ttu-id="ac352-106">Ha a kamatkód adatai megváltoznak, a kódot használó összes funkció automatikusan végrehajtja a változtatásokat az új tranzakciókon.</span><span class="sxs-lookup"><span data-stu-id="ac352-106">When the interest code details are changed, all features that use the code will automatically implement the changes on new transactions.</span></span> <span data-ttu-id="ac352-107">Minden egyes kamatkódnál kétféle típusú kamatlábat állíthat be:</span><span class="sxs-lookup"><span data-stu-id="ac352-107">For each interest code, you can set up two types of rates:</span></span>
-   <span data-ttu-id="ac352-108">Kamatbevételek kamatlábai − Ezek olyan bevételt jelentenek, amely a számlákra vagy kamatlevelekre kamat felszámításával keletkezik.</span><span class="sxs-lookup"><span data-stu-id="ac352-108">Rates for interest earnings − These represent revenue that is earned by charging interest on invoices or interest notes.</span></span>
-   <span data-ttu-id="ac352-109">Kamatfizetések kamatlábai − Ezek olyan költséget jelentenek, amely jóváírásokra fizetett kamat címén keletkezik.</span><span class="sxs-lookup"><span data-stu-id="ac352-109">Rates for interest payments − These represent a cost that is paid for interest on credit notes.</span></span>

<span data-ttu-id="ac352-110">Ezen két kamatlábtípus mindegyike létezhet ugyanabban az időben és ugyanazon kamatkódon.</span><span class="sxs-lookup"><span data-stu-id="ac352-110">Both of these rate types can exist at the same time and in the same interest code.</span></span> <span data-ttu-id="ac352-111">A kamatlábak háromféle számítástípuson alapulhatnak:</span><span class="sxs-lookup"><span data-stu-id="ac352-111">Interest rates can be based on three calculation types:</span></span>
-   <span data-ttu-id="ac352-112">Százalékérték szerinti kamat.</span><span class="sxs-lookup"><span data-stu-id="ac352-112">Interest by percentage.</span></span>
-   <span data-ttu-id="ac352-113">Összeg szerinti kamat.</span><span class="sxs-lookup"><span data-stu-id="ac352-113">Interest by amount.</span></span>
-   <span data-ttu-id="ac352-114">Tartomány szerinti kamat, amely egyetlen százalékértéket vagy összeget eredményez.</span><span class="sxs-lookup"><span data-stu-id="ac352-114">Interest by range, which results in a single percentage or amount.</span></span>

<span data-ttu-id="ac352-115">Ha a kamatszámításra egy kamatkód segítségével kerül sor, külön kamatlevél jön létre mindegyik kamatlábhoz, amely hatályban van abban az időszakban, amikor a kifizetés túllépte a tranzakció esedékességi dátumát.</span><span class="sxs-lookup"><span data-stu-id="ac352-115">When an interest code is used to calculate interest, a separate interest note is created for each interest rate that is in effect during the time that the payment has exceeded the transaction due date.</span></span> <span data-ttu-id="ac352-116">Használja a **Nyereségek** lapját a **Kamat kód** lapon a kamat kamatlábainak beállításához, amit a kamat felszámítása által kapott.</span><span class="sxs-lookup"><span data-stu-id="ac352-116">You use the **Earnings** tab on the **Interest code** page to set up interest rates for interest that you earn by charging interest.</span></span> <span data-ttu-id="ac352-117">Használja a **Kifizetések** oldalt a kamat kamatlábainak beállításához, amit kifizet.</span><span class="sxs-lookup"><span data-stu-id="ac352-117">Use the **Payments** tab to set up interest rates for interest that you pay.</span></span>

## <a name="interest-rates-based-on-a-percentage"></a><span data-ttu-id="ac352-118">Százalékértékek alapuló kamatlábak</span><span class="sxs-lookup"><span data-stu-id="ac352-118">Interest rates based on a percentage</span></span>
<span data-ttu-id="ac352-119">Beállíthat kamatlábakat, amelyek egy megadott százalékot számítanak.</span><span class="sxs-lookup"><span data-stu-id="ac352-119">You can set up interest rates that calculate a specified percentage.</span></span>

- <span data-ttu-id="ac352-120">A kamat összege az összes pénznemre vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="ac352-120">Interest amount applies to all currencies.</span></span>
- <span data-ttu-id="ac352-121">A nem kötelező kamat összeg határaival lehet megadni.</span><span class="sxs-lookup"><span data-stu-id="ac352-121">Optional interest amount limits can be entered.</span></span>
- <span data-ttu-id="ac352-122">**Százalék** van kiválasztva a **Kamat számítása a következő alapján:** mezőben a **Kamatkódok beállítása** oldalon.</span><span class="sxs-lookup"><span data-stu-id="ac352-122">**Percentage** is selected in the **Calculate interest based on** field on the **Set up Interest codes** page.</span></span>

<span data-ttu-id="ac352-123">Például, ha olyan kamatkódot szeretne beállítani, amely kéthavonta 5 % kamatot számít fel, miután a számla kifizetése túllépte a tranzakció esedékességi dátumát, akkor írjon be 2 értéket az **Összes kamat kiszámítása** mezőbe, és jelölje be **Hónap** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ac352-123">For example, to set up an interest code that assesses 5 percent interest for every two months that the invoice payment exceeds the transaction due date, you would enter 2 in the **Calculate interest every** field and select **Month**.</span></span>

> [!NOTE] 
> <span data-ttu-id="ac352-124">A kamatlevél-számítás új algoritmusát a Funkciókezelés segítségével adhatja hozzá.</span><span class="sxs-lookup"><span data-stu-id="ac352-124">The new algorithm for interest note calculation is added using Feature management.</span></span> <span data-ttu-id="ac352-125">Az algoritmus használatához engedélyezze a következő funkciót: **(GBL) Napi kamat számításának engedélyezése az éves százalék 365-tel történő elosztásával**.</span><span class="sxs-lookup"><span data-stu-id="ac352-125">To use this algorithm, enable the **(GBL) Allow to calculate interest per day as yearly percent divided by 365** feature.</span></span> <span data-ttu-id="ac352-126">A funkció engedélyezésével kapcsolatos további tudnivalókat lásd: [Funkciókezelés áttekintése](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="ac352-126">For information about how to enable the feature, see [Feature management overview](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span></span>
> 
> <span data-ttu-id="ac352-127">A kamatlevél összegének kiszámításához használt képlet:</span><span class="sxs-lookup"><span data-stu-id="ac352-127">The formula for the calculation for the interest note amount is:</span></span> 
>  
> <span data-ttu-id="ac352-128">Kamatlevél összege = Tartozás összege \* Éves kamat % / 365 \* Késés napokban</span><span class="sxs-lookup"><span data-stu-id="ac352-128">Interest note amount = Amount owed \* Yearly interest % / 365 \* Number of days late</span></span>
>  
> <span data-ttu-id="ac352-129">Ez a funkció elérhető a 10.0.18 vagy újabb verzióban.</span><span class="sxs-lookup"><span data-stu-id="ac352-129">This feature is available in version 10.0.18 or later.</span></span>    
 
## <a name="interest-rates-based-on-amounts"></a><span data-ttu-id="ac352-130">Összegeken alapuló kamatlábak</span><span class="sxs-lookup"><span data-stu-id="ac352-130">Interest rates based on amounts</span></span>
<span data-ttu-id="ac352-131">Beállíthat olyan kamatlábakat, amelyek egy megadott összeget számítanak ki pénznemenként.</span><span class="sxs-lookup"><span data-stu-id="ac352-131">You can set up interest rates that calculate a specified amount per currency.</span></span>
- <span data-ttu-id="ac352-132">Minden egyes pénznemhez egy kamatösszeg van megadva a kamat kódban.</span><span class="sxs-lookup"><span data-stu-id="ac352-132">An interest amount is specified for each currency in the interest code.</span></span>
- <span data-ttu-id="ac352-133">A nem kötelező kamat összeg határaival lehet megadni.</span><span class="sxs-lookup"><span data-stu-id="ac352-133">Optional interest amount limits can be entered.</span></span>
- <span data-ttu-id="ac352-134">**Összeg** van kiválasztva **Számítása kamat alapján** mezőben **Kamat kódok beállítása** oldalon.</span><span class="sxs-lookup"><span data-stu-id="ac352-134">**Amount** is selected in the **Calculate interest based on** field on the **Set up Interest codes** page.</span></span>

<span data-ttu-id="ac352-135">Például, ha olyan kamatkódot szeretne beállítani, amely 20 naponta 25,00 egység kamatot számít fel, miután a számla kifizetése túllépte a tranzakció esedékességi dátumát, akkor írjon be 20 értéket az **Összes kamat kiszámítása** mezőbe és válassza ki a **Nap** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ac352-135">For example, to set up an interest code that assesses interest of 25.00 for every 20 days that the invoice payment exceeds the transaction due date, you would enter 20 in the **Calculate interest every** field and select **Day**.</span></span>

## <a name="interest-rates-based-on-ranges"></a><span data-ttu-id="ac352-136">Tartományokon alapuló kamatlábak</span><span class="sxs-lookup"><span data-stu-id="ac352-136">Interest rates based on ranges</span></span>
<span data-ttu-id="ac352-137">Beállíthat olyan kamatlábakat, amelyek változnak a lejárt összegtől, az összeg késedelmes napjainak számától vagy az összeg késedelmes hónapjainak számától függően.</span><span class="sxs-lookup"><span data-stu-id="ac352-137">You can set up interest rates that vary depending on the overdue amount, the number of days that the amount is late, or the number of months that the amount is late.</span></span>
-   <span data-ttu-id="ac352-138">Használhatja a **Pénznemenkénti Bevételek** lapot a minden egyes pénznemhez tartozó konkrét kamat beállításának meghatozásához.</span><span class="sxs-lookup"><span data-stu-id="ac352-138">You can use the **Earnings by Currency** tab to define specific interest settings for each currency.</span></span> <span data-ttu-id="ac352-139">Így van ott is, ahol meghatározza a tartományt.</span><span class="sxs-lookup"><span data-stu-id="ac352-139">This is also where you will define the range.</span></span>
-   <span data-ttu-id="ac352-140">Használja a **Tartományok** gombot a beállítani kívánt tartomány megjelenítő sorok hozzáadására.</span><span class="sxs-lookup"><span data-stu-id="ac352-140">Use the **Ranges** button to add lines that represent the ranges that you want to set up.</span></span> <span data-ttu-id="ac352-141">A **Származó** érték jelzi a tartomány kezdetét és a **Kamat érték** száma vagy egy százalékot vagy egy összeget jelez a **Számítás kamat alapján** mezőben a **Kamat kódok beállítása** oldalon történő kiválasztástól függően.</span><span class="sxs-lookup"><span data-stu-id="ac352-141">The **From** value represents the beginning of the range and the **Interest value** number represents either a percentage or an amount, depending on the selection in the **Calculate interest based on** field on the **Set up Interest codes** page.</span></span>

## <a name="example-1-interest-by-range--amount"></a><span data-ttu-id="ac352-142">1. példa: Kamat tartomány szerint = Összeg</span><span class="sxs-lookup"><span data-stu-id="ac352-142">Example 1: Interest by range = Amount</span></span>
<span data-ttu-id="ac352-143">Ön olyan kamatkódot állít be, amely kamatot számít fel minden három hónapban egyszer azt követően, hogy a számla kifizetése túllépi a tranzakció esedékességi dátumát.</span><span class="sxs-lookup"><span data-stu-id="ac352-143">You set up an interest code that assesses interest one time for every three months that the invoice payment exceeds the transaction due date.</span></span> <span data-ttu-id="ac352-144">A számítást százalékos kamatmértékre szeretné alapozni, sávos módon az összegintervallumok szerint.</span><span class="sxs-lookup"><span data-stu-id="ac352-144">You want to base the calculation on a percentage interest value, according to stepped amount intervals.</span></span> <span data-ttu-id="ac352-145">A kamat értéke 1 százalék lesz legfeljebb 1.000,00 számlaértékig, 2 százalék 1.001,00 és 5.000,00 érték között, és 3 százalék az 5.000,00 feletti összegekre.</span><span class="sxs-lookup"><span data-stu-id="ac352-145">The interest value will be 1 percent for invoice amounts up to 1,000.00, 2 percent for amounts from 1,001.00 to 5,000.00, and 3 percent for amounts larger than 5,000.00.</span></span> <span data-ttu-id="ac352-146">A kamatkód mezőinek értékét a következőképpen kell beállítani.</span><span class="sxs-lookup"><span data-stu-id="ac352-146">You set up the interest code field values as follows.</span></span>

| <span data-ttu-id="ac352-147">**Mezőnév**</span><span class="sxs-lookup"><span data-stu-id="ac352-147">**Field name**</span></span>                  | <span data-ttu-id="ac352-148">**Mező értéke**</span><span class="sxs-lookup"><span data-stu-id="ac352-148">**Field value**</span></span> |
|---------------------------------|-----------------|
| <span data-ttu-id="ac352-149">**Kamatkód**</span><span class="sxs-lookup"><span data-stu-id="ac352-149">**Interest code**</span></span>               | <span data-ttu-id="ac352-150">3M%ByAmt</span><span class="sxs-lookup"><span data-stu-id="ac352-150">3M%ByAmt</span></span>        |
| <span data-ttu-id="ac352-151">**Kamatszámítás gyakorisága:**</span><span class="sxs-lookup"><span data-stu-id="ac352-151">**Calculate interest every**</span></span>    | <span data-ttu-id="ac352-152">3/Hónap</span><span class="sxs-lookup"><span data-stu-id="ac352-152">3/Month</span></span>         |
| <span data-ttu-id="ac352-153">**Kamat tartománya**</span><span class="sxs-lookup"><span data-stu-id="ac352-153">**Interest by range**</span></span>           | <span data-ttu-id="ac352-154">Összeg</span><span class="sxs-lookup"><span data-stu-id="ac352-154">Amount</span></span>          |
| <span data-ttu-id="ac352-155">**Kamat kiszámítása a következő alapján:**</span><span class="sxs-lookup"><span data-stu-id="ac352-155">**Calculate interest based on**</span></span> | <span data-ttu-id="ac352-156">Százalék</span><span class="sxs-lookup"><span data-stu-id="ac352-156">Percentage</span></span>      |

<span data-ttu-id="ac352-157">A tartomány adatait a következőképpen kell beállítani.</span><span class="sxs-lookup"><span data-stu-id="ac352-157">You set up the range information as follows.</span></span>

| <span data-ttu-id="ac352-158">**Kezdő érték**</span><span class="sxs-lookup"><span data-stu-id="ac352-158">**From value**</span></span> | <span data-ttu-id="ac352-159">**Kamat értéke**</span><span class="sxs-lookup"><span data-stu-id="ac352-159">**Interest value**</span></span> |
|----------------|--------------------|
| <span data-ttu-id="ac352-160">0</span><span class="sxs-lookup"><span data-stu-id="ac352-160">0</span></span>              | <span data-ttu-id="ac352-161">1</span><span class="sxs-lookup"><span data-stu-id="ac352-161">1</span></span>                  |
| <span data-ttu-id="ac352-162">1,001</span><span class="sxs-lookup"><span data-stu-id="ac352-162">1,001</span></span>          | <span data-ttu-id="ac352-163">2</span><span class="sxs-lookup"><span data-stu-id="ac352-163">2</span></span>                  |
| <span data-ttu-id="ac352-164">5,001</span><span class="sxs-lookup"><span data-stu-id="ac352-164">5,001</span></span>          | <span data-ttu-id="ac352-165">3</span><span class="sxs-lookup"><span data-stu-id="ac352-165">3</span></span>                  |


## <a name="example-2-interest-by-range--days"></a><span data-ttu-id="ac352-166">2. példa: Kamat tartomány szerint = Napok</span><span class="sxs-lookup"><span data-stu-id="ac352-166">Example 2: Interest by range = Days</span></span>
--------------------------------------------------

<span data-ttu-id="ac352-167">Ön olyan kamatkódot állít be, amely kamatot számít fel 15 naponként egyszer azt követően, hogy a számla kifizetése túllépi a tranzakció esedékességi dátumát.</span><span class="sxs-lookup"><span data-stu-id="ac352-167">You set up an interest code that assesses interest one time for every 15 days that the invoice payment exceeds the transaction due date.</span></span> <span data-ttu-id="ac352-168">A számítást összegként megadott kamatmértékre szeretné alapozni, sávos módon napi intervallumok szerint.</span><span class="sxs-lookup"><span data-stu-id="ac352-168">You want to base the calculation on an amount interest value, according to stepped day intervals.</span></span> <span data-ttu-id="ac352-169">A kamat mértéke 10,00 egység lesz 15 naponta az első 60 napban, 15,00 egység 15 naponta 61.–90. nap között, és 20,00 egység 15 naponta a 91. naptól kezdődően.</span><span class="sxs-lookup"><span data-stu-id="ac352-169">The interest value will be 10.00 per 15 days during the first 60 days, 15.00 per 15 days during days 61 to 90, and 20.00 per 15 days from day 91 and after.</span></span> <span data-ttu-id="ac352-170">A kamatkód mezőinek értékét a következőképpen kell beállítani.</span><span class="sxs-lookup"><span data-stu-id="ac352-170">You set up the interest code field values as follows.</span></span>

| <span data-ttu-id="ac352-171">**Mezőnév**</span><span class="sxs-lookup"><span data-stu-id="ac352-171">**Field name**</span></span>                  | <span data-ttu-id="ac352-172">**Mező értéke**</span><span class="sxs-lookup"><span data-stu-id="ac352-172">**Field value**</span></span> |
|---------------------------------|-----------------|
| <span data-ttu-id="ac352-173">**Kamatkód**</span><span class="sxs-lookup"><span data-stu-id="ac352-173">**Interest code**</span></span>               | <span data-ttu-id="ac352-174">15DAmtXDay</span><span class="sxs-lookup"><span data-stu-id="ac352-174">15DAmtXDay</span></span>      |
| <span data-ttu-id="ac352-175">**Kamatszámítás gyakorisága:**</span><span class="sxs-lookup"><span data-stu-id="ac352-175">**Calculate interest every**</span></span>    | <span data-ttu-id="ac352-176">15/Nap</span><span class="sxs-lookup"><span data-stu-id="ac352-176">15/Day</span></span>          |
| <span data-ttu-id="ac352-177">**Kamat tartománya**</span><span class="sxs-lookup"><span data-stu-id="ac352-177">**Interest by range**</span></span>           | <span data-ttu-id="ac352-178">Napok</span><span class="sxs-lookup"><span data-stu-id="ac352-178">Days</span></span>            |
| <span data-ttu-id="ac352-179">**Kamat kiszámítása a következő alapján:**</span><span class="sxs-lookup"><span data-stu-id="ac352-179">**Calculate interest based on**</span></span> | <span data-ttu-id="ac352-180">Összeg</span><span class="sxs-lookup"><span data-stu-id="ac352-180">Amount</span></span>          |

<span data-ttu-id="ac352-181">A tartomány adatait a következőképpen kell beállítani.</span><span class="sxs-lookup"><span data-stu-id="ac352-181">You set up the range information as follows.</span></span>

| <span data-ttu-id="ac352-182">**Kezdő érték**</span><span class="sxs-lookup"><span data-stu-id="ac352-182">**From value**</span></span> | <span data-ttu-id="ac352-183">**Kamat értéke**</span><span class="sxs-lookup"><span data-stu-id="ac352-183">**Interest value**</span></span> |
|----------------|--------------------|
| <span data-ttu-id="ac352-184">0</span><span class="sxs-lookup"><span data-stu-id="ac352-184">0</span></span>              | <span data-ttu-id="ac352-185">10</span><span class="sxs-lookup"><span data-stu-id="ac352-185">10</span></span>                 |
| <span data-ttu-id="ac352-186">61</span><span class="sxs-lookup"><span data-stu-id="ac352-186">61</span></span>             | <span data-ttu-id="ac352-187">15.</span><span class="sxs-lookup"><span data-stu-id="ac352-187">15</span></span>                 |
| <span data-ttu-id="ac352-188">91</span><span class="sxs-lookup"><span data-stu-id="ac352-188">91</span></span>             | <span data-ttu-id="ac352-189">20</span><span class="sxs-lookup"><span data-stu-id="ac352-189">20</span></span>                 |


## <a name="example-3-interest-by-range--months"></a><span data-ttu-id="ac352-190">3. példa: Kamat tartomány szerint = Hónapok</span><span class="sxs-lookup"><span data-stu-id="ac352-190">Example 3: Interest by range = Months</span></span>
----------------------------------------------------

<span data-ttu-id="ac352-191">Ön olyan kamatkódot állít be, amely kamatot számít fel minden hónapban egyszer azt követően, hogy a számla kifizetése túllépi a tranzakció esedékességi dátumát.</span><span class="sxs-lookup"><span data-stu-id="ac352-191">You set up an interest code that assesses interest one time for every month that the invoice payment exceeds the transaction due date.</span></span> <span data-ttu-id="ac352-192">A számítást százalékos kamatmértékre szeretné alapozni, sávos módon hónapok szerint.</span><span class="sxs-lookup"><span data-stu-id="ac352-192">You want to base the calculation on a percentage interest value, according to stepped month intervals.</span></span> <span data-ttu-id="ac352-193">A kamat mértéke 1,5 százalék lesz havonta az első három késedelmes hónapban, 2,0 százalék havonta a második három hónapban, és 2,5 százalék havonta az első hat hónapot követő minden hónapban.</span><span class="sxs-lookup"><span data-stu-id="ac352-193">The interest value will be 1.5 percent per month for the first three overdue months, 2.0 percent per month for the second three months, and 2.5 percent per month for each month beyond the first six months.</span></span> <span data-ttu-id="ac352-194">A kamatkód mezőinek értékét a következőképpen kell beállítani.</span><span class="sxs-lookup"><span data-stu-id="ac352-194">You set up the interest code field values as follows.</span></span>

| <span data-ttu-id="ac352-195">**Mezőnév**</span><span class="sxs-lookup"><span data-stu-id="ac352-195">**Field name**</span></span>                  | <span data-ttu-id="ac352-196">**Mező értéke**</span><span class="sxs-lookup"><span data-stu-id="ac352-196">**Field value**</span></span> |
|---------------------------------|-----------------|
| <span data-ttu-id="ac352-197">**Kamatkód**</span><span class="sxs-lookup"><span data-stu-id="ac352-197">**Interest code**</span></span>               | <span data-ttu-id="ac352-198">1M%ByMth</span><span class="sxs-lookup"><span data-stu-id="ac352-198">1M%ByMth</span></span>        |
| <span data-ttu-id="ac352-199">**Kamatszámítás gyakorisága:**</span><span class="sxs-lookup"><span data-stu-id="ac352-199">**Calculate interest every**</span></span>    | <span data-ttu-id="ac352-200">1/hónap</span><span class="sxs-lookup"><span data-stu-id="ac352-200">1/Month</span></span>         |
| <span data-ttu-id="ac352-201">**Kamat tartománya**</span><span class="sxs-lookup"><span data-stu-id="ac352-201">**Interest by range**</span></span>           | <span data-ttu-id="ac352-202">Hónapok</span><span class="sxs-lookup"><span data-stu-id="ac352-202">Months</span></span>          |
| <span data-ttu-id="ac352-203">**Kamat kiszámítása a következő alapján:**</span><span class="sxs-lookup"><span data-stu-id="ac352-203">**Calculate interest based on**</span></span> | <span data-ttu-id="ac352-204">Százalék</span><span class="sxs-lookup"><span data-stu-id="ac352-204">Percentage</span></span>      |

<span data-ttu-id="ac352-205">A tartomány adatait a következőképpen kell beállítani.</span><span class="sxs-lookup"><span data-stu-id="ac352-205">You set up the range information as follows.</span></span>

| <span data-ttu-id="ac352-206">**Kezdő érték**</span><span class="sxs-lookup"><span data-stu-id="ac352-206">**From value**</span></span> | <span data-ttu-id="ac352-207">**Kamat értéke**</span><span class="sxs-lookup"><span data-stu-id="ac352-207">**Interest value**</span></span> |
|----------------|--------------------|
| <span data-ttu-id="ac352-208">0</span><span class="sxs-lookup"><span data-stu-id="ac352-208">0</span></span>              | <span data-ttu-id="ac352-209">1.5</span><span class="sxs-lookup"><span data-stu-id="ac352-209">1.5</span></span>                |
| <span data-ttu-id="ac352-210">4</span><span class="sxs-lookup"><span data-stu-id="ac352-210">4</span></span>              | <span data-ttu-id="ac352-211">2</span><span class="sxs-lookup"><span data-stu-id="ac352-211">2</span></span>                  |
| <span data-ttu-id="ac352-212">7</span><span class="sxs-lookup"><span data-stu-id="ac352-212">7</span></span>              | <span data-ttu-id="ac352-213">2,5</span><span class="sxs-lookup"><span data-stu-id="ac352-213">2.5</span></span>                |

## <a name="new-versions"></a><span data-ttu-id="ac352-214">Új verziók</span><span class="sxs-lookup"><span data-stu-id="ac352-214">New versions</span></span>
<span data-ttu-id="ac352-215">A kamatkódok dátum érvényességek.</span><span class="sxs-lookup"><span data-stu-id="ac352-215">Interest codes are date effective.</span></span> <span data-ttu-id="ac352-216">Ha szeretné módosítani a kamatlábat, létrehozhat egy **új verziót**, ami a jövőbeli dátum szerint hatályos.</span><span class="sxs-lookup"><span data-stu-id="ac352-216">If you want to modify the interest rate, you can create a **new version** that is effective as of a future date.</span></span>

<span data-ttu-id="ac352-217">Különböző verziói megtekintéséhez használja a **Dátum, mint** menüt lehetőséget a fordulónap kiválasztásához.</span><span class="sxs-lookup"><span data-stu-id="ac352-217">To view different versions, you can use the **As of Date** menu choice to select the cutoff date.</span></span> <span data-ttu-id="ac352-218">Bejelölheti a **Összes rekord megjelenítése** lehetőséget a lapon megjelenő összes kamatkód megtekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="ac352-218">You can also select the **Display all records** to view all interest codes in the page.</span></span>





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
