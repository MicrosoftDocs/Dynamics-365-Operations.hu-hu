---
title: Hűségprogramok meghatározása
description: Ez az eljárás bemutatja, hogyan hozhat létre egy két hűségszinttel rendelkező hűségprogramot.
author: jashanno
manager: AnnBe
ms.date: 11/14/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 91f30d4d1b66e5b4b90f7df67d8f76a95a100338
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4412906"
---
# <a name="define-loyalty-programs"></a><span data-ttu-id="e7d95-103">Hűségprogramok meghatározása</span><span class="sxs-lookup"><span data-stu-id="e7d95-103">Define loyalty programs</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e7d95-104">Ez az eljárás bemutatja, hogyan hozhat létre egy két hűségszinttel rendelkező hűségprogramot.</span><span class="sxs-lookup"><span data-stu-id="e7d95-104">This procedure shows how to set up a loyalty program with two loyalty tiers.</span></span> <span data-ttu-id="e7d95-105">Ez az eljárás az USRT bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="e7d95-105">This procedure uses the USRT demo data company.</span></span>

1. <span data-ttu-id="e7d95-106">Lépjen a Kiskereskedelem és kereskedelem > ..</span><span class="sxs-lookup"><span data-stu-id="e7d95-106">Go to Retail and Commerce > ..</span></span> <span data-ttu-id="e7d95-107">> Hűségprogramok lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e7d95-107">> Loyalty programs.</span></span>
2. <span data-ttu-id="e7d95-108">Kattintson az Új elemre.</span><span class="sxs-lookup"><span data-stu-id="e7d95-108">Click New.</span></span>
3. <span data-ttu-id="e7d95-109">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="e7d95-109">In the Name field, type a value.</span></span>
4. <span data-ttu-id="e7d95-110">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="e7d95-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="e7d95-111">Kattintson az Új sor hozzáadására.</span><span class="sxs-lookup"><span data-stu-id="e7d95-111">Click Add line.</span></span>
6. <span data-ttu-id="e7d95-112">Adjon meg egy számot a Szint mezőben.</span><span class="sxs-lookup"><span data-stu-id="e7d95-112">In the Level field, enter a number.</span></span>
7. <span data-ttu-id="e7d95-113">A Szint mezőben adja meg a hűségszint nevét.</span><span class="sxs-lookup"><span data-stu-id="e7d95-113">In the Tier field, enter a name for the loyalty tier.</span></span>
8. <span data-ttu-id="e7d95-114">Írjon egy értéket a „Leírás” mezőbe.</span><span class="sxs-lookup"><span data-stu-id="e7d95-114">In the Description field, type a value.</span></span>
9. <span data-ttu-id="e7d95-115">A Dátumtartomány mezőben kattintson a legördülő gombra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="e7d95-115">In the Date interval field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="e7d95-116">Ezt az időintervallumot ki kell terjeszteni a jövőre.</span><span class="sxs-lookup"><span data-stu-id="e7d95-116">This date interval should extend into the future.</span></span> <span data-ttu-id="e7d95-117">Ha például egy éves időintervallumot ad meg az arany szinthez, akkor az arany szintet elérő vevők egy éven keresztül kaphatják meg a szintre vonatkozó jutalmakat.</span><span class="sxs-lookup"><span data-stu-id="e7d95-117">For example, if the date interval that is selected for gold tier is a one-year period, any customer who qualifies for the gold tier can receive the rewards that are assigned to the gold tier for one year.</span></span> <span data-ttu-id="e7d95-118">Ha egy vevő az arany szintjének érvényességi időszaka alatt újból jogosulttá válik az adott fokozatra, akkor automatikusan egy évvel meghosszabbodik a fokozat érvényességi időtartama a jogosultság újbóli megszerzésétől számítva.</span><span class="sxs-lookup"><span data-stu-id="e7d95-118">If the customer re-qualifies for the gold tier while they are in the tier, the date that the tier expires is extended by another year from the date when they re-qualify.</span></span>  
10. <span data-ttu-id="e7d95-119">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="e7d95-119">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="e7d95-120">Kattintson az Új sor hozzáadása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e7d95-120">Click Add line.</span></span>
12. <span data-ttu-id="e7d95-121">Adjon meg egy számot a Szint mezőben.</span><span class="sxs-lookup"><span data-stu-id="e7d95-121">In the Level field, enter a number.</span></span>
13. <span data-ttu-id="e7d95-122">A Szint mezőben adja meg a hűségszint nevét.</span><span class="sxs-lookup"><span data-stu-id="e7d95-122">In the Tier field, enter a name for the loyalty tier.</span></span>
14. <span data-ttu-id="e7d95-123">Írjon egy értéket a „Leírás” mezőbe.</span><span class="sxs-lookup"><span data-stu-id="e7d95-123">In the Description field, type a value.</span></span>
15. <span data-ttu-id="e7d95-124">A Dátumtartomány mezőben kattintson a legördülő gombra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="e7d95-124">In the Date interval field, click the drop-down button to open the lookup.</span></span>
16. <span data-ttu-id="e7d95-125">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="e7d95-125">In the list, click the link in the selected row.</span></span>
17. <span data-ttu-id="e7d95-126">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="e7d95-126">Click Save.</span></span>
18. <span data-ttu-id="e7d95-127">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="e7d95-127">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="e7d95-128">A szintszabályok meghatározzák az egy adott időintervallumon belül minimum megszerzendő hűségpontok számát, ami ahhoz szükséges, hogy valaki elérjen egy bizonyos szintet.</span><span class="sxs-lookup"><span data-stu-id="e7d95-128">Tier rules define the minimum number of a reward point needed to be earned during a time period to qualify for the tier.</span></span>  
19. <span data-ttu-id="e7d95-129">Bontsa ki a Szintszabályok részt.</span><span class="sxs-lookup"><span data-stu-id="e7d95-129">Toggle the expansion of the Tier rules section.</span></span>
20. <span data-ttu-id="e7d95-130">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e7d95-130">Click New.</span></span>
    * <span data-ttu-id="e7d95-131">Egy fokozatra több szintszabály is vonatkozhat.</span><span class="sxs-lookup"><span data-stu-id="e7d95-131">You can have more than one tier rule per tier.</span></span> <span data-ttu-id="e7d95-132">Például három különböző feltétele is lehet egy szint elérésének: 500 USD elköltése egy hónapban, 1000 USD elköltése egy év alatt, és 20 tranzakció végrehajtása egy év alatt.</span><span class="sxs-lookup"><span data-stu-id="e7d95-132">For example, you could have three different criteria to earn a tier; by spending $500 in one month, by spending $1000 over one year, and by having 20 transactions in one year.</span></span> <span data-ttu-id="e7d95-133">Ehhez három szintszabályt kell létrehoznia.</span><span class="sxs-lookup"><span data-stu-id="e7d95-133">To do this, you would need to create three tier rules.</span></span>  
21. <span data-ttu-id="e7d95-134">A Hűségpont mezőben kattintson a legördülő gombra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="e7d95-134">In the Reward point field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="e7d95-135">Ez egy nem beváltható hűségpont kell, hogy legyen.</span><span class="sxs-lookup"><span data-stu-id="e7d95-135">This should be a non-redeemable loyalty reward point.</span></span>  
22. <span data-ttu-id="e7d95-136">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="e7d95-136">In the list, click the link in the selected row.</span></span>
23. <span data-ttu-id="e7d95-137">A Minimális kiadott pontok mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="e7d95-137">In the Minimum issued points field, enter a number.</span></span>
    * <span data-ttu-id="e7d95-138">Ha a legalacsonyabb fokozatú szintre minden vevő jogosult csupán azáltal, hogy részt vesz a programban, írjon be „0” értéket.</span><span class="sxs-lookup"><span data-stu-id="e7d95-138">For the lowest level tier, if all customers qualify simply by participating in the program, enter '0'.</span></span>  
24. <span data-ttu-id="e7d95-139">A Kiértékelés dátuma mezőben kattintson a legördülő gombra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="e7d95-139">In the Evaluation date interval field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="e7d95-140">Ezt az időintervallumot ki kell terjeszteni a múltra.</span><span class="sxs-lookup"><span data-stu-id="e7d95-140">This date interval should extend into the past.</span></span> <span data-ttu-id="e7d95-141">Csak az ebben az időtartományban szerzett pontokat veszik figyelembe a minimum kiadott pontok elérésénél.</span><span class="sxs-lookup"><span data-stu-id="e7d95-141">Only points earned during this date interval will be counted towards reaching the minimum issued points value.</span></span>  
25. <span data-ttu-id="e7d95-142">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="e7d95-142">In the list, click the link in the selected row.</span></span>
26. <span data-ttu-id="e7d95-143">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="e7d95-143">Click Save.</span></span>
27. <span data-ttu-id="e7d95-144">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="e7d95-144">In the list, find and select the desired record.</span></span>
28. <span data-ttu-id="e7d95-145">Kattintson az Új elemre.</span><span class="sxs-lookup"><span data-stu-id="e7d95-145">Click New.</span></span>
29. <span data-ttu-id="e7d95-146">A Hűségpont mezőben kattintson a legördülő gombra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="e7d95-146">In the Reward point field, click the drop-down button to open the lookup.</span></span>
30. <span data-ttu-id="e7d95-147">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="e7d95-147">In the list, click the link in the selected row.</span></span>
31. <span data-ttu-id="e7d95-148">A Minimális kiadott pontok mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="e7d95-148">In the Minimum issued points field, enter a number.</span></span>
32. <span data-ttu-id="e7d95-149">A Kiértékelés dátuma mezőben kattintson a legördülő gombra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="e7d95-149">In the Evaluation date interval field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="e7d95-150">Ezt az időintervallumot ki kell terjeszteni a múltra.</span><span class="sxs-lookup"><span data-stu-id="e7d95-150">This date interval should extend into the past.</span></span>  
33. <span data-ttu-id="e7d95-151">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="e7d95-151">In the list, click the link in the selected row.</span></span>
34. <span data-ttu-id="e7d95-152">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="e7d95-152">Click Save.</span></span>
35. <span data-ttu-id="e7d95-153">Kattintson az Árcsoportok lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e7d95-153">Click Price groups.</span></span>
    * <span data-ttu-id="e7d95-154">Ha szeretne engedményeket adni a hűséges vevőknek.</span><span class="sxs-lookup"><span data-stu-id="e7d95-154">If you want to give loyalty customers discounts.</span></span> <span data-ttu-id="e7d95-155">egy vagy több árcsoportot kell hozzárendelnie a hűségprogramhoz és az árcsoportokat hozzá kell rendelnie az engedményekhez.</span><span class="sxs-lookup"><span data-stu-id="e7d95-155">you'll need to assign one or more price groups to the loyalty program and assign the price groups to discounts.</span></span> <span data-ttu-id="e7d95-156">Az a legjobb, ha nem keveri a különböző árcsoportokat a különböző típusú engedmények között.</span><span class="sxs-lookup"><span data-stu-id="e7d95-156">It is a best practice to not mix price groups across different types of discounting entities.</span></span>  <span data-ttu-id="e7d95-157">Például ne használja ugyanazt az árcsoportot egy hűségkedvezmény és egy csatornakedvezmény esetén.</span><span class="sxs-lookup"><span data-stu-id="e7d95-157">For example, don't use the same price group for a loyalty discount and a channel discount.</span></span>  
36. <span data-ttu-id="e7d95-158">Az Árcsoport mezőben kattintson a legördülő gombra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="e7d95-158">In the Price group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="e7d95-159">Az oldal tetején található Árcsoportok hivatkozás a hűségprogramhoz tartozik.</span><span class="sxs-lookup"><span data-stu-id="e7d95-159">The Price groups link at the top of the page is for the loyalty program.</span></span> <span data-ttu-id="e7d95-160">A Programszintek gyorslapon található Árcsoportok hivatkozás egy adott hűségszinthez tartozik.</span><span class="sxs-lookup"><span data-stu-id="e7d95-160">The Price groups link in the Program tiers FastTab is for a specific loyalty tier only.</span></span>  
37. <span data-ttu-id="e7d95-161">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="e7d95-161">In the list, click the link in the selected row.</span></span>
38. <span data-ttu-id="e7d95-162">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="e7d95-162">Click Save.</span></span>
39. <span data-ttu-id="e7d95-163">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="e7d95-163">Close the page.</span></span>
40. <span data-ttu-id="e7d95-164">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="e7d95-164">Click Save.</span></span>

