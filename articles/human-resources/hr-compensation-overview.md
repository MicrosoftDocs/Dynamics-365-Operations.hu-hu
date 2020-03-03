---
title: Kompenzációs konstrukciók
description: A kompenzációkért és juttatásokért felelős vezetők használhatják a Kompenzációkezelést a karbantartáshoz és a szervezet alkalmazottaira vonatkozó fix és változó kompenzáció feldolgozásához.
author: andreabichsel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
ms.search.form: HcmCompensationLevel, HRCCompGrid, HRMCompFixedAction, HRMCompFixedBudget, HRMCompFixedPlanTable
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Human Resources
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 1b2494ac717bc8c0171be49cc39e6aefff4425ab
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/03/2020
ms.locfileid: "3009331"
---
# <a name="compensation-plans"></a><span data-ttu-id="8ca81-103">Kompenzációs konstrukciók</span><span class="sxs-lookup"><span data-stu-id="8ca81-103">Compensation plans</span></span>

<span data-ttu-id="8ca81-104">A kompenzációkért és juttatásokért felelős vezetők használhatják a Kompenzációkezelést a karbantartáshoz és a szervezet alkalmazottaira vonatkozó fix és változó kompenzáció feldolgozásához.</span><span class="sxs-lookup"><span data-stu-id="8ca81-104">Compensation and Benefits Managers can use Compensation management to maintain and process fixed and variable compensation plans for the organization's employees.</span></span>

### <a name="introduction"></a><span data-ttu-id="8ca81-105">Bevezetés</span><span class="sxs-lookup"><span data-stu-id="8ca81-105">Introduction</span></span>

<span data-ttu-id="8ca81-106">A kompenzációkezeléssel szabályozható az alapfizetés és a jutalmak kifizetése.</span><span class="sxs-lookup"><span data-stu-id="8ca81-106">Compensation management is used to control the delivery of base pay and awards.</span></span> <span data-ttu-id="8ca81-107">Egy alkalmazott fix fizetési díjalapja és érdemeken alapuló fizetése kezelhető a fix kompenzációs tervekkel.</span><span class="sxs-lookup"><span data-stu-id="8ca81-107">An employee's fixed base pay and merit increases are controlled through fixed compensation plans.</span></span> <span data-ttu-id="8ca81-108">Az ösztönző díjak kifizetése, például bónuszok, teljesítménydíjak, részvényopciók és kölcsönök, továbbá az egyszeri jutalmak a változó kompenzációs tervekben szabályozhatók.</span><span class="sxs-lookup"><span data-stu-id="8ca81-108">The payment of incentive pay, such as bonus payments, performance awards, stock options, and grants, and also one-time awards, are controlled through variable compensation plans.</span></span> 

<span data-ttu-id="8ca81-109">Az alkalmazottak mindkét típusú konstrukcióhoz, akár többhöz is társíthatók.</span><span class="sxs-lookup"><span data-stu-id="8ca81-109">Employees can be enrolled in one or more plans of both types.</span></span> <span data-ttu-id="8ca81-110">Az alkalmazottnak meg kell felelni az alábbi kritériumoknak, hogy hozzárendelhető legyen a kompenzációs tervhez:</span><span class="sxs-lookup"><span data-stu-id="8ca81-110">An employee must meet the following requirements in order to be eligible for enrollment in a compensation plan:</span></span>
-   <span data-ttu-id="8ca81-111">Az alkalmazottnak aktív pozícióval kell rendelkeznie.</span><span class="sxs-lookup"><span data-stu-id="8ca81-111">The employee must have an active position assignment.</span></span>
-   <span data-ttu-id="8ca81-112">Az alkalmazottnak teljesíteni kell a kompenzáció terv jogosultsági szabályaiban meghatározott feltételeket.</span><span class="sxs-lookup"><span data-stu-id="8ca81-112">The employee must meet the criteria that are defined by eligibility rules for a compensation plan.</span></span>

## <a name="compensation-setup"></a><span data-ttu-id="8ca81-113"> Kompenzáció beállítása</span><span class="sxs-lookup"><span data-stu-id="8ca81-113">Compensation setup</span></span>
<span data-ttu-id="8ca81-114">Az alábbi táblázat felsorolja azokat a kompenzációs folyamatokat, amelyek aktív részét képezhetik a vállalati kompenzációs terv beállításainak.</span><span class="sxs-lookup"><span data-stu-id="8ca81-114">The following table lists components of the compensation process that can be integral in setting up your company's compensation plans.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="8ca81-115">Összetevő</span><span class="sxs-lookup"><span data-stu-id="8ca81-115">Component</span></span></th>
<th><span data-ttu-id="8ca81-116">További információ...</span><span class="sxs-lookup"><span data-stu-id="8ca81-116">More information…</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="8ca81-117">Fix kompenzációs műveletek</span><span class="sxs-lookup"><span data-stu-id="8ca81-117">Fixed compensation actions</span></span></td>
<td><span data-ttu-id="8ca81-118">Fix kompenzációs műveletek, amelyeknek két célt teljesítenek:</span><span class="sxs-lookup"><span data-stu-id="8ca81-118">Fixed compensation actions accomplish two purposes:</span></span>
<ul>
<li><span data-ttu-id="8ca81-119">A műveletek megadhatnak olyan információkat amelyeket rögzíteni kell az alkalmazott kompenzációjának változásakor.</span><span class="sxs-lookup"><span data-stu-id="8ca81-119">Actions can specify the kind of information that must be recorded when an employee’s compensation changes.</span></span> <span data-ttu-id="8ca81-120">Például előírhatja ezt előléptetéskor vagy lefokozáskor.</span><span class="sxs-lookup"><span data-stu-id="8ca81-120">For example, you can require that the reason a change, such as a promotion or a demotion be recorded.</span></span></li>
<li><span data-ttu-id="8ca81-121">A műveletekkel biztosítható, hogy a számítást alkalmazzák a fix kompenzációs konstrukciók feldolgozásakor.</span><span class="sxs-lookup"><span data-stu-id="8ca81-121">Actions can ensure that a calculation is applied when fixed compensation plans are processed.</span></span>  <span data-ttu-id="8ca81-122">Például a Saját tőke típusú műveletek összehasonlítják az alkalmazottak fizetését a minimum referenciaponttal az alkalmazott szintjén, és biztosítják, hogy a dolgozó legalább a minimális fizetést megkapja.</span><span class="sxs-lookup"><span data-stu-id="8ca81-122">For example, actions of type Equity will compare the employees pay to the minimum reference point for the level on the employee&#39;s and ensure the employee is getting paid at least the minimum.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="8ca81-123">Szintek</span><span class="sxs-lookup"><span data-stu-id="8ca81-123">Levels</span></span></td>
<td><span data-ttu-id="8ca81-124">A feladatokhoz szintek és bármelyik beosztás kapcsolódik amelyik a munkahivatkozáshoz kapcsolódik.</span><span class="sxs-lookup"><span data-stu-id="8ca81-124">Levels are associated with jobs and any positions that are related to a job reference.</span></span> <span data-ttu-id="8ca81-125">A kompenzációs tervek következő három típusának különálló szintjei hozhatók létre: Osztály, Sáv és Lépés.</span><span class="sxs-lookup"><span data-stu-id="8ca81-125">You can create discrete levels for the three types of compensation plans: Grade, Band, and Step.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="8ca81-126">Tartomány-kihasználtsági mátrix</span><span class="sxs-lookup"><span data-stu-id="8ca81-126">Range utilization matrix</span></span></td>
<td><span data-ttu-id="8ca81-127">A tartomány kihasználtsági mátrix segít az alkalmazottak továbbléptetésében a beosztásukhoz tartozó ellenőrzőpontjuk felé.</span><span class="sxs-lookup"><span data-stu-id="8ca81-127">A range utilization matrix helps you transition employees to the control point for their jobs.</span></span> <span data-ttu-id="8ca81-128">A tartomány-kihasználtság a kompenzáció vállalaton belüli szabályozására is felhasználható oly módon, hogy az ne függjön az egyes alkalmazottak teljesítményétől vagy a vállalat teljesítményétől összességében.</span><span class="sxs-lookup"><span data-stu-id="8ca81-128">You can also use range utilization to control pay rate equity in the company without regard to an individual employee&#39;s performance or the overall performance of the company.</span></span> <span data-ttu-id="8ca81-129">Például a tartományukon belül alacsonyabb fizetést kapó alkalmazottak nagyobb emelést kapnak, mint azok az alkalmazottak, akik magasabb fizetéssel rendelkeznek.</span><span class="sxs-lookup"><span data-stu-id="8ca81-129">For example, employees who are paid lower in their range get higher percentage increases than employees who are paid higher in the range.</span></span> <span data-ttu-id="8ca81-130">Ezzel a módszerrel kiegyenlítheti a saját tőke különbségeit.</span><span class="sxs-lookup"><span data-stu-id="8ca81-130">In this manner, you can systematically offset equity differences.</span></span> <span data-ttu-id="8ca81-131">A tartomány-kihasználtság számítása a következő: (Fix fizetési díjalap – Tartományminimum) ÷ (Tartománymaximum – Tartományminimum).</span><span class="sxs-lookup"><span data-stu-id="8ca81-131">The range utilization is calculated as follows: (Fixed Pay Rate - Range Minimum) ÷ (Range Maximum - Range Minimum).</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="8ca81-132">Hivatkozásipont-beállítások</span><span class="sxs-lookup"><span data-stu-id="8ca81-132">Reference point setups</span></span></td>
<td><span data-ttu-id="8ca81-133">A hivatkozásipont-beállítások hivatkozási pontok mátrixba rendezett halmazát tartalmazzák.</span><span class="sxs-lookup"><span data-stu-id="8ca81-133">A reference point setup includes a set of reference points that represent ranges in a matrix.</span></span> <span data-ttu-id="8ca81-134">Minden tartomány egy fizetési díjalaphoz társítható.</span><span class="sxs-lookup"><span data-stu-id="8ca81-134">Each range can be associated with a pay rate.</span></span> <span data-ttu-id="8ca81-135">Például a fokozatos konstrukciójú szervezetek gyakran tartalmaznak Minimum, Közép és Maximum referenciapontokat.</span><span class="sxs-lookup"><span data-stu-id="8ca81-135">For example, grade plans will often have reference points of Minimum, Midpoint, and Maximum.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="8ca81-136">Kompenzációs mátrix</span><span class="sxs-lookup"><span data-stu-id="8ca81-136">Compensation matrix</span></span></td>
<td><span data-ttu-id="8ca81-137">A kompenzációs mátrix azon referenciapontok és szintek összessége amelyeket a kompenzációs szerkezet létrehozásához használ.</span><span class="sxs-lookup"><span data-stu-id="8ca81-137">A compensation matrix is the set of reference points and levels that you use to create a compensation structure.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="8ca81-138">Kompenzációs struktúra</span><span class="sxs-lookup"><span data-stu-id="8ca81-138">Compensation structure</span></span></td>
<td><span data-ttu-id="8ca81-139">A kompenzációs struktúra egy kompenzációs mátrix, amelyben minden szinthez a fizetési díjalapok referenciapontjai vannak társítva.</span><span class="sxs-lookup"><span data-stu-id="8ca81-139">A compensation structure is a compensation matrix that has pay rates associated with the reference points for each level.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="8ca81-140">Alkalmazhatósági szabályok</span><span class="sxs-lookup"><span data-stu-id="8ca81-140">Eligibility rules</span></span></td>
<td><span data-ttu-id="8ca81-141">Az alkalmazhatósági szabályok segítségével kikereshetők az adott feladatokban, beosztásban, részlegben, szakszervezetben vagy kompenzációs régiókban lévő alkalmazottak, akikre speciális kompenzációs tervek vonatkoznak.</span><span class="sxs-lookup"><span data-stu-id="8ca81-141">Eligibility rules are used to identify employees in specific jobs, job functions, job types, departments, labor unions, or compensation regions that are covered by specific compensation plans.</span></span> <span data-ttu-id="8ca81-142">Hogy felvehesse az alkalmazottakat a tervbe létre kell hoznia jogosultsági szabályokat a változó és fix kompenzációs tervekhez.</span><span class="sxs-lookup"><span data-stu-id="8ca81-142">You must create eligibility rules for both variable and fixed compensation plans in order to enroll employees in the plan.</span></span> <span data-ttu-id="8ca81-143">Miután meghatározta a kompenzációs konstrukciókra vonatkozó alkalmazhatósági szabályokat, definiálhatja azokat a munkaköröket, amelyeket a konstrukcióval érintett beosztásokban alkalmazni lehet.</span><span class="sxs-lookup"><span data-stu-id="8ca81-143">After eligibility rules are specified for a compensation plan, you can define the levels that should apply to the jobs that are covered by the plan.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="8ca81-144">Fizetési gyakoriságok</span><span class="sxs-lookup"><span data-stu-id="8ca81-144">Pay frequencies</span></span></td>
<td><span data-ttu-id="8ca81-145">A kifizetési gyakoriságokkal meghatározható az időtartam, amelyre a kompenzáció vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="8ca81-145">Pay frequencies are used to define the time period for which the compensation is specified.</span></span>  <span data-ttu-id="8ca81-146">Például a kifizetési gyakoriság segít felmérni, hogy a kompenzációs összeget éves fizetés vagy órabér formájában adták-e meg.</span><span class="sxs-lookup"><span data-stu-id="8ca81-146">For example, the pay frequency helps you understand if the compensation amount is specified as an annual salary versus an hourly pay rate.</span></span> <span data-ttu-id="8ca81-147">A kifizetési gyakoriságok továbbá használhatók átváltási tényezők felállításához, ha havi, heti, kétheti és óránkénti kompenzációs összegek kifizetési gyakoriságát akarja átváltani éves kifizetési gyakoriságra.</span><span class="sxs-lookup"><span data-stu-id="8ca81-147">Pay frequencies are also used to set up conversion factors to convert compensation amounts from monthly, weekly, biweekly and hourly pay frequencies to an annual pay frequency.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="8ca81-148">Kompenzációs régiók</span><span class="sxs-lookup"><span data-stu-id="8ca81-148">Compensation regions</span></span></td>
<td><span data-ttu-id="8ca81-149">A kompenzációs régiók beállítása a munkahelyen alapuló kompenzáció meghatározásához használatos.</span><span class="sxs-lookup"><span data-stu-id="8ca81-149">Compensation regions are used to specify employee compensation based on the location of the workplace.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="8ca81-150">Ellenőrzőpont</span><span class="sxs-lookup"><span data-stu-id="8ca81-150">Control point</span></span></td>
<td><span data-ttu-id="8ca81-151">A vezérlőpont az alkalmazottaknak adandó ideális fizetést határozza meg, az adott kompenzációs szinten.</span><span class="sxs-lookup"><span data-stu-id="8ca81-151">The control point defines what you consider to be the ideal pay rate for all employees at a compensation level.</span></span> <span data-ttu-id="8ca81-152">A fokozatos konstrukciójú szerkezeteknél a vezérlőpontok általában a tartományok felezőpontjai.</span><span class="sxs-lookup"><span data-stu-id="8ca81-152">For grade plan structures, control points are typically the midpoint of the ranges.</span></span> <span data-ttu-id="8ca81-153">A sávos szerkezeteknél ritkán alkalmaznak vezérlőpontokat.</span><span class="sxs-lookup"><span data-stu-id="8ca81-153">Band structures rarely use control points.</span></span> <span data-ttu-id="8ca81-154">A Fix kompenzáció tervek képernyőn megadhatja a fix kompenzációs terv vezérlőpontját.</span><span class="sxs-lookup"><span data-stu-id="8ca81-154">You can specify the control point for a fixed compensation plan in the Fixed compensation plans form.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="8ca81-155">Beosztások</span><span class="sxs-lookup"><span data-stu-id="8ca81-155">Job functions</span></span></td>
<td><span data-ttu-id="8ca81-156">A beosztások segítségével osztályozhatók és szűrhetők az adott munkákhoz a kompenzációs tervek.</span><span class="sxs-lookup"><span data-stu-id="8ca81-156">Job functions are used to classify and filter compensation plans to specific jobs.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="8ca81-157">Beosztástípusok</span><span class="sxs-lookup"><span data-stu-id="8ca81-157">Job types</span></span></td>
<td><span data-ttu-id="8ca81-158">A beosztás típusok segítségével osztályozhatók és szűrhetők az adott munkákhoz a kompenzációs tervek.</span><span class="sxs-lookup"><span data-stu-id="8ca81-158">Job types are used to classify and filter compensation plans to specific jobs.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="8ca81-159">Változó kompenzációtípusok</span><span class="sxs-lookup"><span data-stu-id="8ca81-159">Variable compensation types</span></span></td>
<td><span data-ttu-id="8ca81-160">A változó kompenzációtípusok, például a részvényjutalmak és a készpénzjutalmak a változó kompenzációs konstrukciókon keresztül alkalmazhatók.</span><span class="sxs-lookup"><span data-stu-id="8ca81-160">Variable compensation types, such as stock awards or cash award bonuses, are set up in variable compensation plans.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="8ca81-161">Kompenzációs rácsok</span><span class="sxs-lookup"><span data-stu-id="8ca81-161">Compensation grids</span></span></td>
<td><span data-ttu-id="8ca81-162">A kompenzációs struktúrát a kompenzációs rácsok tartalmazzák.</span><span class="sxs-lookup"><span data-stu-id="8ca81-162">Compensation grids contain the compensation structure.</span></span>  <span data-ttu-id="8ca81-163">A kompenzációs rácsok egy vagy több kompenzációs konstrukcióhoz használhatók.</span><span class="sxs-lookup"><span data-stu-id="8ca81-163">Compensation grids can be used by one or more compensation plans.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="8ca81-164">Teljesítménykonstrukciók</span><span class="sxs-lookup"><span data-stu-id="8ca81-164">Performance plans</span></span></td>
<td><span data-ttu-id="8ca81-165">Felosztási mátrixszal társítható teljesítménykonstrukciók létrehozása teljesítménybérezési stratégiában történő felhasználás céljából.</span><span class="sxs-lookup"><span data-stu-id="8ca81-165">Performance plans are used to associate performance with an allocation matrix, so that you can use the plan in a pay-for-performance strategy.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="8ca81-166">Teljesítményminősítések</span><span class="sxs-lookup"><span data-stu-id="8ca81-166">Performance ratings</span></span></td>
<td><span data-ttu-id="8ca81-167">A teljesítményminősítéseket a teljesítményjutalmak és az eredményjutalmak meghatározására alkalmazhatja a teljesítménykonstrukciókban.</span><span class="sxs-lookup"><span data-stu-id="8ca81-167">Performance ratings are used in performance plans to determine the amount of a merit award or performance award.</span></span></td>
</tr>
</tbody>
</table>

## <a name="process-events"></a><span data-ttu-id="8ca81-168">Feldolgozási események</span><span class="sxs-lookup"><span data-stu-id="8ca81-168">Process events</span></span>
<span data-ttu-id="8ca81-169">A feldolgozási esemény egy időszakra vonatkozóan az egyes fix és változó kompenzációs konstrukciókba sorolt alkalmazottak kompenzációit számítják ki.</span><span class="sxs-lookup"><span data-stu-id="8ca81-169">A process event calculates compensation information for a specific period for all employees who are enrolled in one or more fixed or variable compensation plans.</span></span> <span data-ttu-id="8ca81-170">A feldolgozási események többször is futtathatók, például a számított kompenzációs eredmények tesztelése vagy frissítése céljából.</span><span class="sxs-lookup"><span data-stu-id="8ca81-170">You can run a process event repeatedly to test or update calculated compensation results.</span></span>

<a name="compensation-events"></a><span data-ttu-id="8ca81-171">Kompenzációs események</span><span class="sxs-lookup"><span data-stu-id="8ca81-171">Compensation events</span></span>
-------------------

<span data-ttu-id="8ca81-172">Minden feldolgozási esemény futtatásakor létrejön egy kompenzációs esemény.</span><span class="sxs-lookup"><span data-stu-id="8ca81-172">Each time a process event is run, a compensation event is created.</span></span>  <span data-ttu-id="8ca81-173">A kompenzációs események tartalmazzák az egyes alkalmazottak feldolgozási folyamat során érintett kompenzációs folyamatait.</span><span class="sxs-lookup"><span data-stu-id="8ca81-173">Compensation events contain the results of the compensation process for each employee included in that process event.</span></span>  <span data-ttu-id="8ca81-174">Ha a számítások helyesek, akkor betöltheti a kompenzációs eseményt a feldolgozási eseményben érintett alkalmazottak kompenzációs rekordjainak frissítéséhez.</span><span class="sxs-lookup"><span data-stu-id="8ca81-174">When the calculations are correct, you can load the compensation event to update the compensation records for the employees who are affected by the process event.</span></span>

## <a name="recommendations"></a><span data-ttu-id="8ca81-175"> Ajánlások</span><span class="sxs-lookup"><span data-stu-id="8ca81-175">Recommendations</span></span>
<span data-ttu-id="8ca81-176">Miután lefuttatta a feldolgozási eseményt javaslatot tehet az egyes alkalmazottak érdemeken alapuló emelésre vagy a jutalom összegére a feldolgozási esemény irányelvei alapján.</span><span class="sxs-lookup"><span data-stu-id="8ca81-176">After you run a process event, you can recommend adjustments to an employee’s merit increase or award amount, based on the calculated guidelines of the process event.</span></span> <span data-ttu-id="8ca81-177">Ha szeretne ajánlásokat létrehozni alkalmazottaknak, akkor engedélyeznie kell az ajánlásokat a kompenzációs konstrukciók létrehozásakor vagy amikor létrehozza a feldolgozási eseményt.</span><span class="sxs-lookup"><span data-stu-id="8ca81-177">To make recommendations for employees, you must enable recommendations when you set up compensation plans or when you set up the process event.</span></span>


