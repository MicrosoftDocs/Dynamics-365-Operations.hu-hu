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
ms.openlocfilehash: fc986ea752d1482f618401058f7a0b18f13efd5f
ms.sourcegitcommit: ff09736563d3cd2bc74c7664edd1767b218401cb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/04/2021
ms.locfileid: "6188710"
---
# <a name="set-up-interest-rates-for-an-interest-code"></a><span data-ttu-id="bad54-103">Kamatlábak beállítása kamatkódhoz</span><span class="sxs-lookup"><span data-stu-id="bad54-103">Set up interest rates for an interest code</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="bad54-104">A kamatkódok olyan beállításokat tartalmaznak, amelyek meghatározzák, hogy mikor kerül sor kamat felszámítására, és hogyan történik annak kiszámítása a hátralékos számlákon.</span><span class="sxs-lookup"><span data-stu-id="bad54-104">Interest codes contain settings that determine when interest is charged and how it is calculated on overdue accounts.</span></span>

<span data-ttu-id="bad54-105">Megteheti, hogy egyetlen kamatkódot állít be, és azt alkalmazza több vevő feladási profilra, számlázási kódra, illetve adott számlasorokra.</span><span class="sxs-lookup"><span data-stu-id="bad54-105">You can set up a single interest code and apply it to multiple customer posting profiles, billing codes, or to specific invoice lines.</span></span> <span data-ttu-id="bad54-106">Ha a kamatkód adatai megváltoznak, a kódot használó összes funkció automatikusan végrehajtja a változtatásokat az új tranzakciókon.</span><span class="sxs-lookup"><span data-stu-id="bad54-106">When the interest code details are changed, all features that use the code will automatically implement the changes on new transactions.</span></span> <span data-ttu-id="bad54-107">Minden egyes kamatkódnál kétféle típusú kamatlábat állíthat be:</span><span class="sxs-lookup"><span data-stu-id="bad54-107">For each interest code, you can set up two types of rates:</span></span>
-   <span data-ttu-id="bad54-108">Kamatbevételek kamatlábai − Ezek olyan bevételt jelentenek, amely a számlákra vagy kamatlevelekre kamat felszámításával keletkezik.</span><span class="sxs-lookup"><span data-stu-id="bad54-108">Rates for interest earnings − These represent revenue that is earned by charging interest on invoices or interest notes.</span></span>
-   <span data-ttu-id="bad54-109">Kamatfizetések kamatlábai − Ezek olyan költséget jelentenek, amely jóváírásokra fizetett kamat címén keletkezik.</span><span class="sxs-lookup"><span data-stu-id="bad54-109">Rates for interest payments − These represent a cost that is paid for interest on credit notes.</span></span>

<span data-ttu-id="bad54-110">Ezen két kamatlábtípus mindegyike létezhet ugyanabban az időben és ugyanazon kamatkódon.</span><span class="sxs-lookup"><span data-stu-id="bad54-110">Both of these rate types can exist at the same time and in the same interest code.</span></span> <span data-ttu-id="bad54-111">A kamatlábak háromféle számítástípuson alapulhatnak:</span><span class="sxs-lookup"><span data-stu-id="bad54-111">Interest rates can be based on three calculation types:</span></span>
-   <span data-ttu-id="bad54-112">Százalékérték szerinti kamat.</span><span class="sxs-lookup"><span data-stu-id="bad54-112">Interest by percentage.</span></span>
-   <span data-ttu-id="bad54-113">Összeg szerinti kamat.</span><span class="sxs-lookup"><span data-stu-id="bad54-113">Interest by amount.</span></span>
-   <span data-ttu-id="bad54-114">Tartomány szerinti kamat, amely egyetlen százalékértéket vagy összeget eredményez.</span><span class="sxs-lookup"><span data-stu-id="bad54-114">Interest by range, which results in a single percentage or amount.</span></span>

<span data-ttu-id="bad54-115">Ha a kamatszámításra egy kamatkód segítségével kerül sor, külön kamatlevél jön létre mindegyik kamatlábhoz, amely hatályban van abban az időszakban, amikor a kifizetés túllépte a tranzakció esedékességi dátumát.</span><span class="sxs-lookup"><span data-stu-id="bad54-115">When an interest code is used to calculate interest, a separate interest note is created for each interest rate that is in effect during the time that the payment has exceeded the transaction due date.</span></span> <span data-ttu-id="bad54-116">Használja a **Nyereségek** lapját a **Kamat kód** lapon a kamat kamatlábainak beállításához, amit a kamat felszámítása által kapott.</span><span class="sxs-lookup"><span data-stu-id="bad54-116">You use the **Earnings** tab on the **Interest code** page to set up interest rates for interest that you earn by charging interest.</span></span> <span data-ttu-id="bad54-117">Használja a **Kifizetések** oldalt a kamat kamatlábainak beállításához, amit kifizet.</span><span class="sxs-lookup"><span data-stu-id="bad54-117">Use the **Payments** tab to set up interest rates for interest that you pay.</span></span>

## <a name="interest-rates-based-on-a-percentage"></a><span data-ttu-id="bad54-118">Százalékértékek alapuló kamatlábak</span><span class="sxs-lookup"><span data-stu-id="bad54-118">Interest rates based on a percentage</span></span>
<span data-ttu-id="bad54-119">Beállíthat kamatlábakat, amelyek egy megadott százalékot számítanak.</span><span class="sxs-lookup"><span data-stu-id="bad54-119">You can set up interest rates that calculate a specified percentage.</span></span>

- <span data-ttu-id="bad54-120">A kamat összege az összes pénznemre vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="bad54-120">Interest amount applies to all currencies.</span></span>
- <span data-ttu-id="bad54-121">A nem kötelező kamat összeg határaival lehet megadni.</span><span class="sxs-lookup"><span data-stu-id="bad54-121">Optional interest amount limits can be entered.</span></span>
- <span data-ttu-id="bad54-122">**Százalék** van kiválasztva a **Kamat számítása a következő alapján:** mezőben a **Kamatkódok beállítása** oldalon.</span><span class="sxs-lookup"><span data-stu-id="bad54-122">**Percentage** is selected in the **Calculate interest based on** field on the **Set up Interest codes** page.</span></span>

<span data-ttu-id="bad54-123">Például, ha olyan kamatkódot szeretne beállítani, amely kéthavonta 5 % kamatot számít fel, miután a számla kifizetése túllépte a tranzakció esedékességi dátumát, akkor írjon be 2 értéket az **Összes kamat kiszámítása** mezőbe, és jelölje be **Hónap** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="bad54-123">For example, to set up an interest code that assesses 5 percent interest for every two months that the invoice payment exceeds the transaction due date, you would enter 2 in the **Calculate interest every** field and select **Month**.</span></span>

> [!NOTE] 
> <span data-ttu-id="bad54-124">A kamatlevél-számítás új algoritmusát a Funkciókezelés segítségével adhatja hozzá.</span><span class="sxs-lookup"><span data-stu-id="bad54-124">The new algorithm for interest note calculation is added using Feature management.</span></span> <span data-ttu-id="bad54-125">Az algoritmus használatához engedélyezze a következő funkciót: **(GBL) Napi kamat számításának engedélyezése az éves százalék 365-tel történő elosztásával**.</span><span class="sxs-lookup"><span data-stu-id="bad54-125">To use this algorithm, enable the **(GBL) Allow to calculate interest per day as yearly percent divided by 365** feature.</span></span> <span data-ttu-id="bad54-126">A funkció engedélyezésével kapcsolatos további tudnivalókat lásd: [Funkciókezelés áttekintése](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="bad54-126">For information about how to enable the feature, see [Feature management overview](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span></span>
> 
> <span data-ttu-id="bad54-127">A kamatlevél összegének kiszámításához használt képlet:</span><span class="sxs-lookup"><span data-stu-id="bad54-127">The formula for the calculation for the interest note amount is:</span></span> 
>  
> <span data-ttu-id="bad54-128">Kamatlevél összege = Tartozás összege \* Éves kamat % / 365 \* Késés napokban</span><span class="sxs-lookup"><span data-stu-id="bad54-128">Interest note amount = Amount owed \* Yearly interest % / 365 \* Number of days late</span></span>
>  
> <span data-ttu-id="bad54-129">Ez a funkció elérhető a 10.0.18 vagy újabb verzióban.</span><span class="sxs-lookup"><span data-stu-id="bad54-129">This feature is available in version 10.0.18 or later.</span></span>    
 
## <a name="interest-rates-based-on-amounts"></a><span data-ttu-id="bad54-130">Összegeken alapuló kamatlábak</span><span class="sxs-lookup"><span data-stu-id="bad54-130">Interest rates based on amounts</span></span>
<span data-ttu-id="bad54-131">Beállíthat olyan kamatlábakat, amelyek egy megadott összeget számítanak ki pénznemenként.</span><span class="sxs-lookup"><span data-stu-id="bad54-131">You can set up interest rates that calculate a specified amount per currency.</span></span>
- <span data-ttu-id="bad54-132">Minden egyes pénznemhez egy kamatösszeg van megadva a kamat kódban.</span><span class="sxs-lookup"><span data-stu-id="bad54-132">An interest amount is specified for each currency in the interest code.</span></span>
- <span data-ttu-id="bad54-133">A nem kötelező kamat összeg határaival lehet megadni.</span><span class="sxs-lookup"><span data-stu-id="bad54-133">Optional interest amount limits can be entered.</span></span>
- <span data-ttu-id="bad54-134">**Összeg** van kiválasztva **Számítása kamat alapján** mezőben **Kamat kódok beállítása** oldalon.</span><span class="sxs-lookup"><span data-stu-id="bad54-134">**Amount** is selected in the **Calculate interest based on** field on the **Set up Interest codes** page.</span></span>

<span data-ttu-id="bad54-135">Például, ha olyan kamatkódot szeretne beállítani, amely 20 naponta 25,00 egység kamatot számít fel, miután a számla kifizetése túllépte a tranzakció esedékességi dátumát, akkor írjon be 20 értéket az **Összes kamat kiszámítása** mezőbe és válassza ki a **Nap** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="bad54-135">For example, to set up an interest code that assesses interest of 25.00 for every 20 days that the invoice payment exceeds the transaction due date, you would enter 20 in the **Calculate interest every** field and select **Day**.</span></span>

## <a name="interest-rates-based-on-ranges"></a><span data-ttu-id="bad54-136">Tartományokon alapuló kamatlábak</span><span class="sxs-lookup"><span data-stu-id="bad54-136">Interest rates based on ranges</span></span>
<span data-ttu-id="bad54-137">Beállíthat olyan kamatlábakat, amelyek változnak a lejárt összegtől, az összeg késedelmes napjainak számától vagy az összeg késedelmes hónapjainak számától függően.</span><span class="sxs-lookup"><span data-stu-id="bad54-137">You can set up interest rates that vary depending on the overdue amount, the number of days that the amount is late, or the number of months that the amount is late.</span></span>
-   <span data-ttu-id="bad54-138">Használhatja a **Pénznemenkénti Bevételek** lapot a minden egyes pénznemhez tartozó konkrét kamat beállításának meghatozásához.</span><span class="sxs-lookup"><span data-stu-id="bad54-138">You can use the **Earnings by Currency** tab to define specific interest settings for each currency.</span></span> <span data-ttu-id="bad54-139">Így van ott is, ahol meghatározza a tartományt.</span><span class="sxs-lookup"><span data-stu-id="bad54-139">This is also where you will define the range.</span></span>
-   <span data-ttu-id="bad54-140">Használja a **Tartományok** gombot a beállítani kívánt tartomány megjelenítő sorok hozzáadására.</span><span class="sxs-lookup"><span data-stu-id="bad54-140">Use the **Ranges** button to add lines that represent the ranges that you want to set up.</span></span> <span data-ttu-id="bad54-141">A **Származó** érték jelzi a tartomány kezdetét és a **Kamat érték** száma vagy egy százalékot vagy egy összeget jelez a **Számítás kamat alapján** mezőben a **Kamat kódok beállítása** oldalon történő kiválasztástól függően.</span><span class="sxs-lookup"><span data-stu-id="bad54-141">The **From** value represents the beginning of the range and the **Interest value** number represents either a percentage or an amount, depending on the selection in the **Calculate interest based on** field on the **Set up Interest codes** page.</span></span>

## <a name="example-1-interest-by-range--amount"></a><span data-ttu-id="bad54-142">1. példa: Kamat tartomány szerint = Összeg</span><span class="sxs-lookup"><span data-stu-id="bad54-142">Example 1: Interest by range = Amount</span></span>
<span data-ttu-id="bad54-143">Ön olyan kamatkódot állít be, amely kamatot számít fel minden három hónapban egyszer azt követően, hogy a számla kifizetése túllépi a tranzakció esedékességi dátumát.</span><span class="sxs-lookup"><span data-stu-id="bad54-143">You set up an interest code that assesses interest one time for every three months that the invoice payment exceeds the transaction due date.</span></span> <span data-ttu-id="bad54-144">A számítást százalékos kamatmértékre szeretné alapozni, sávos módon az összegintervallumok szerint.</span><span class="sxs-lookup"><span data-stu-id="bad54-144">You want to base the calculation on a percentage interest value, according to stepped amount intervals.</span></span> <span data-ttu-id="bad54-145">A kamat értéke 1 százalék lesz legfeljebb 1.000,00 számlaértékig, 2 százalék 1.001,00 és 5.000,00 érték között, és 3 százalék az 5.000,00 feletti összegekre.</span><span class="sxs-lookup"><span data-stu-id="bad54-145">The interest value will be 1 percent for invoice amounts up to 1,000.00, 2 percent for amounts from 1,001.00 to 5,000.00, and 3 percent for amounts larger than 5,000.00.</span></span> <span data-ttu-id="bad54-146">A kamatkód mezőinek értékét a következőképpen kell beállítani.</span><span class="sxs-lookup"><span data-stu-id="bad54-146">You set up the interest code field values as follows.</span></span>

| <span data-ttu-id="bad54-147">**Mezőnév**</span><span class="sxs-lookup"><span data-stu-id="bad54-147">**Field name**</span></span>                  | <span data-ttu-id="bad54-148">**Mező értéke**</span><span class="sxs-lookup"><span data-stu-id="bad54-148">**Field value**</span></span> |
|---------------------------------|-----------------|
| <span data-ttu-id="bad54-149">**Kamatkód**</span><span class="sxs-lookup"><span data-stu-id="bad54-149">**Interest code**</span></span>               | <span data-ttu-id="bad54-150">3M%ByAmt</span><span class="sxs-lookup"><span data-stu-id="bad54-150">3M%ByAmt</span></span>        |
| <span data-ttu-id="bad54-151">**Kamatszámítás gyakorisága:**</span><span class="sxs-lookup"><span data-stu-id="bad54-151">**Calculate interest every**</span></span>    | <span data-ttu-id="bad54-152">3/Hónap</span><span class="sxs-lookup"><span data-stu-id="bad54-152">3/Month</span></span>         |
| <span data-ttu-id="bad54-153">**Kamat tartománya**</span><span class="sxs-lookup"><span data-stu-id="bad54-153">**Interest by range**</span></span>           | <span data-ttu-id="bad54-154">Összeg</span><span class="sxs-lookup"><span data-stu-id="bad54-154">Amount</span></span>          |
| <span data-ttu-id="bad54-155">**Kamat kiszámítása a következő alapján:**</span><span class="sxs-lookup"><span data-stu-id="bad54-155">**Calculate interest based on**</span></span> | <span data-ttu-id="bad54-156">Százalék</span><span class="sxs-lookup"><span data-stu-id="bad54-156">Percentage</span></span>      |

<span data-ttu-id="bad54-157">A tartomány adatait a következőképpen kell beállítani.</span><span class="sxs-lookup"><span data-stu-id="bad54-157">You set up the range information as follows.</span></span>

| <span data-ttu-id="bad54-158">**Kezdő érték**</span><span class="sxs-lookup"><span data-stu-id="bad54-158">**From value**</span></span> | <span data-ttu-id="bad54-159">**Kamat értéke**</span><span class="sxs-lookup"><span data-stu-id="bad54-159">**Interest value**</span></span> |
|----------------|--------------------|
| <span data-ttu-id="bad54-160">0</span><span class="sxs-lookup"><span data-stu-id="bad54-160">0</span></span>              | <span data-ttu-id="bad54-161">1</span><span class="sxs-lookup"><span data-stu-id="bad54-161">1</span></span>                  |
| <span data-ttu-id="bad54-162">1,001</span><span class="sxs-lookup"><span data-stu-id="bad54-162">1,001</span></span>          | <span data-ttu-id="bad54-163">2</span><span class="sxs-lookup"><span data-stu-id="bad54-163">2</span></span>                  |
| <span data-ttu-id="bad54-164">5,001</span><span class="sxs-lookup"><span data-stu-id="bad54-164">5,001</span></span>          | <span data-ttu-id="bad54-165">3</span><span class="sxs-lookup"><span data-stu-id="bad54-165">3</span></span>                  |


## <a name="example-2-interest-by-range--days"></a><span data-ttu-id="bad54-166">2. példa: Kamat tartomány szerint = Napok</span><span class="sxs-lookup"><span data-stu-id="bad54-166">Example 2: Interest by range = Days</span></span>

<span data-ttu-id="bad54-167">Ön olyan kamatkódot állít be, amely kamatot számít fel 15 naponként egyszer azt követően, hogy a számla kifizetése túllépi a tranzakció esedékességi dátumát.</span><span class="sxs-lookup"><span data-stu-id="bad54-167">You set up an interest code that assesses interest one time for every 15 days that the invoice payment exceeds the transaction due date.</span></span> <span data-ttu-id="bad54-168">A számítást összegként megadott kamatmértékre szeretné alapozni, sávos módon napi intervallumok szerint.</span><span class="sxs-lookup"><span data-stu-id="bad54-168">You want to base the calculation on an amount interest value, according to stepped day intervals.</span></span> <span data-ttu-id="bad54-169">A kamat mértéke 10,00 egység lesz 15 naponta az első 60 napban, 15,00 egység 15 naponta 61.–90. nap között, és 20,00 egység 15 naponta a 91. naptól kezdődően.</span><span class="sxs-lookup"><span data-stu-id="bad54-169">The interest value will be 10.00 per 15 days during the first 60 days, 15.00 per 15 days during days 61 to 90, and 20.00 per 15 days from day 91 and after.</span></span> <span data-ttu-id="bad54-170">A kamatkód mezőinek értékét a következőképpen kell beállítani.</span><span class="sxs-lookup"><span data-stu-id="bad54-170">You set up the interest code field values as follows.</span></span>

| <span data-ttu-id="bad54-171">**Mezőnév**</span><span class="sxs-lookup"><span data-stu-id="bad54-171">**Field name**</span></span>                  | <span data-ttu-id="bad54-172">**Mező értéke**</span><span class="sxs-lookup"><span data-stu-id="bad54-172">**Field value**</span></span> |
|---------------------------------|-----------------|
| <span data-ttu-id="bad54-173">**Kamatkód**</span><span class="sxs-lookup"><span data-stu-id="bad54-173">**Interest code**</span></span>               | <span data-ttu-id="bad54-174">15DAmtXDay</span><span class="sxs-lookup"><span data-stu-id="bad54-174">15DAmtXDay</span></span>      |
| <span data-ttu-id="bad54-175">**Kamatszámítás gyakorisága:**</span><span class="sxs-lookup"><span data-stu-id="bad54-175">**Calculate interest every**</span></span>    | <span data-ttu-id="bad54-176">15/Nap</span><span class="sxs-lookup"><span data-stu-id="bad54-176">15/Day</span></span>          |
| <span data-ttu-id="bad54-177">**Kamat tartománya**</span><span class="sxs-lookup"><span data-stu-id="bad54-177">**Interest by range**</span></span>           | <span data-ttu-id="bad54-178">Napok</span><span class="sxs-lookup"><span data-stu-id="bad54-178">Days</span></span>            |
| <span data-ttu-id="bad54-179">**Kamat kiszámítása a következő alapján:**</span><span class="sxs-lookup"><span data-stu-id="bad54-179">**Calculate interest based on**</span></span> | <span data-ttu-id="bad54-180">Összeg</span><span class="sxs-lookup"><span data-stu-id="bad54-180">Amount</span></span>          |

<span data-ttu-id="bad54-181">A tartomány adatait a következőképpen kell beállítani.</span><span class="sxs-lookup"><span data-stu-id="bad54-181">You set up the range information as follows.</span></span>

| <span data-ttu-id="bad54-182">**Kezdő érték**</span><span class="sxs-lookup"><span data-stu-id="bad54-182">**From value**</span></span> | <span data-ttu-id="bad54-183">**Kamat értéke**</span><span class="sxs-lookup"><span data-stu-id="bad54-183">**Interest value**</span></span> |
|----------------|--------------------|
| <span data-ttu-id="bad54-184">0</span><span class="sxs-lookup"><span data-stu-id="bad54-184">0</span></span>              | <span data-ttu-id="bad54-185">10</span><span class="sxs-lookup"><span data-stu-id="bad54-185">10</span></span>                 |
| <span data-ttu-id="bad54-186">61</span><span class="sxs-lookup"><span data-stu-id="bad54-186">61</span></span>             | <span data-ttu-id="bad54-187">15.</span><span class="sxs-lookup"><span data-stu-id="bad54-187">15</span></span>                 |
| <span data-ttu-id="bad54-188">91</span><span class="sxs-lookup"><span data-stu-id="bad54-188">91</span></span>             | <span data-ttu-id="bad54-189">20</span><span class="sxs-lookup"><span data-stu-id="bad54-189">20</span></span>                 |


## <a name="example-3-interest-by-range--months"></a><span data-ttu-id="bad54-190">3. példa: Kamat tartomány szerint = Hónapok</span><span class="sxs-lookup"><span data-stu-id="bad54-190">Example 3: Interest by range = Months</span></span>

<span data-ttu-id="bad54-191">Ön olyan kamatkódot állít be, amely kamatot számít fel minden hónapban egyszer azt követően, hogy a számla kifizetése túllépi a tranzakció esedékességi dátumát.</span><span class="sxs-lookup"><span data-stu-id="bad54-191">You set up an interest code that assesses interest one time for every month that the invoice payment exceeds the transaction due date.</span></span> <span data-ttu-id="bad54-192">A számítást százalékos kamatmértékre szeretné alapozni, sávos módon hónapok szerint.</span><span class="sxs-lookup"><span data-stu-id="bad54-192">You want to base the calculation on a percentage interest value, according to stepped month intervals.</span></span> <span data-ttu-id="bad54-193">A kamat mértéke 1,5 százalék lesz havonta az első három késedelmes hónapban, 2,0 százalék havonta a második három hónapban, és 2,5 százalék havonta az első hat hónapot követő minden hónapban.</span><span class="sxs-lookup"><span data-stu-id="bad54-193">The interest value will be 1.5 percent per month for the first three overdue months, 2.0 percent per month for the second three months, and 2.5 percent per month for each month beyond the first six months.</span></span> <span data-ttu-id="bad54-194">A kamatkód mezőinek értékét a következőképpen kell beállítani.</span><span class="sxs-lookup"><span data-stu-id="bad54-194">You set up the interest code field values as follows.</span></span>

| <span data-ttu-id="bad54-195">**Mezőnév**</span><span class="sxs-lookup"><span data-stu-id="bad54-195">**Field name**</span></span>                  | <span data-ttu-id="bad54-196">**Mező értéke**</span><span class="sxs-lookup"><span data-stu-id="bad54-196">**Field value**</span></span> |
|---------------------------------|-----------------|
| <span data-ttu-id="bad54-197">**Kamatkód**</span><span class="sxs-lookup"><span data-stu-id="bad54-197">**Interest code**</span></span>               | <span data-ttu-id="bad54-198">1M%ByMth</span><span class="sxs-lookup"><span data-stu-id="bad54-198">1M%ByMth</span></span>        |
| <span data-ttu-id="bad54-199">**Kamatszámítás gyakorisága:**</span><span class="sxs-lookup"><span data-stu-id="bad54-199">**Calculate interest every**</span></span>    | <span data-ttu-id="bad54-200">1/hónap</span><span class="sxs-lookup"><span data-stu-id="bad54-200">1/Month</span></span>         |
| <span data-ttu-id="bad54-201">**Kamat tartománya**</span><span class="sxs-lookup"><span data-stu-id="bad54-201">**Interest by range**</span></span>           | <span data-ttu-id="bad54-202">Hónapok</span><span class="sxs-lookup"><span data-stu-id="bad54-202">Months</span></span>          |
| <span data-ttu-id="bad54-203">**Kamat kiszámítása a következő alapján:**</span><span class="sxs-lookup"><span data-stu-id="bad54-203">**Calculate interest based on**</span></span> | <span data-ttu-id="bad54-204">Százalék</span><span class="sxs-lookup"><span data-stu-id="bad54-204">Percentage</span></span>      |

<span data-ttu-id="bad54-205">A tartomány adatait a következőképpen kell beállítani.</span><span class="sxs-lookup"><span data-stu-id="bad54-205">You set up the range information as follows.</span></span>

| <span data-ttu-id="bad54-206">**Kezdő érték**</span><span class="sxs-lookup"><span data-stu-id="bad54-206">**From value**</span></span> | <span data-ttu-id="bad54-207">**Kamat értéke**</span><span class="sxs-lookup"><span data-stu-id="bad54-207">**Interest value**</span></span> |
|----------------|--------------------|
| <span data-ttu-id="bad54-208">0</span><span class="sxs-lookup"><span data-stu-id="bad54-208">0</span></span>              | <span data-ttu-id="bad54-209">1.5</span><span class="sxs-lookup"><span data-stu-id="bad54-209">1.5</span></span>                |
| <span data-ttu-id="bad54-210">4</span><span class="sxs-lookup"><span data-stu-id="bad54-210">4</span></span>              | <span data-ttu-id="bad54-211">2</span><span class="sxs-lookup"><span data-stu-id="bad54-211">2</span></span>                  |
| <span data-ttu-id="bad54-212">7</span><span class="sxs-lookup"><span data-stu-id="bad54-212">7</span></span>              | <span data-ttu-id="bad54-213">2,5</span><span class="sxs-lookup"><span data-stu-id="bad54-213">2.5</span></span>                |

## <a name="new-versions"></a><span data-ttu-id="bad54-214">Új verziók</span><span class="sxs-lookup"><span data-stu-id="bad54-214">New versions</span></span>
<span data-ttu-id="bad54-215">A kamatkódok dátum érvényességek.</span><span class="sxs-lookup"><span data-stu-id="bad54-215">Interest codes are date effective.</span></span> <span data-ttu-id="bad54-216">Ha szeretné módosítani a kamatlábat, létrehozhat egy **új verziót**, ami a jövőbeli dátum szerint hatályos.</span><span class="sxs-lookup"><span data-stu-id="bad54-216">If you want to modify the interest rate, you can create a **new version** that is effective as of a future date.</span></span>

<span data-ttu-id="bad54-217">Különböző verziói megtekintéséhez használja a **Dátum, mint** menüt lehetőséget a fordulónap kiválasztásához.</span><span class="sxs-lookup"><span data-stu-id="bad54-217">To view different versions, you can use the **As of Date** menu choice to select the cutoff date.</span></span> <span data-ttu-id="bad54-218">Bejelölheti a **Összes rekord megjelenítése** lehetőséget a lapon megjelenő összes kamatkód megtekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="bad54-218">You can also select the **Display all records** to view all interest codes in the page.</span></span>





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
