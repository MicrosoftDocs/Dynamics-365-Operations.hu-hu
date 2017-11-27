---
title: "Munkaidő és jelenlét távollét regisztrálása"
description: "Ez a témakör bemutatja, hogyan kezelje a távollét-regisztrációkat a munkaidő-nyilvántartásban."
author: johanhoffmann
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: johanhoffmann
ms.search.validFrom: 2017-09-20
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 477724e6211a084638e8a0b7133f60edef07b3ad
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="absence-registration-in-time-and-attendance"></a><span data-ttu-id="50ee6-103">Munkaidő és jelenlét távollét regisztrálása</span><span class="sxs-lookup"><span data-stu-id="50ee6-103">Absence registration in Time and attendance</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="50ee6-104">Ez a témakör bemutatja a távolléti koncepciókat, és azt, hogyan kezelje a távollétet a munkaidő-nyilvántartásban.</span><span class="sxs-lookup"><span data-stu-id="50ee6-104">This topic describes the concepts for absence and explains how to handle absence in Time and attendance.</span></span>

## <a name="absence-that-is-based-on-regular-work-hours"></a><span data-ttu-id="50ee6-105">Távolléti, amely a normál munkaidőre alapul.</span><span class="sxs-lookup"><span data-stu-id="50ee6-105">Absence that is based on regular work hours</span></span>

<span data-ttu-id="50ee6-106">A dolgozók távollevőnek számítanak minden óra esetében, amelyet a normál munkaórákban nem dolgoznak le.</span><span class="sxs-lookup"><span data-stu-id="50ee6-106">Workers are considered absent for any hours that they don't work during their regular work hours.</span></span> <span data-ttu-id="50ee6-107">A dolgozói időprofilbeállításban határozható meg a munkaidő.</span><span class="sxs-lookup"><span data-stu-id="50ee6-107">Regular work hours are defined in a worker's standard time profile.</span></span>

<span data-ttu-id="50ee6-108">A dolgozó dolgozhat olyan napi profillal, amelyben a kezdés 7:00 óra, a távozás pedig 15:00 óra.</span><span class="sxs-lookup"><span data-stu-id="50ee6-108">For example, a worker is working on a day profile that has clock-in at 7:00 AM and clock-out at 3:00 PM.</span></span> <span data-ttu-id="50ee6-109">Ha a dolgozó érkezéskori blokkolása 9:00 óra, távollevőnek minősül 7:00 óra és 9:00 óra között az adott napon.</span><span class="sxs-lookup"><span data-stu-id="50ee6-109">If the worker clocks in at 9:00 AM, he is considered absent from 7:00 AM to 9:00 AM on that day.</span></span>

<span data-ttu-id="50ee6-110">Ebben az esetben a dolgozónak meg kell adnia a távollét okát.</span><span class="sxs-lookup"><span data-stu-id="50ee6-110">In this case, workers are prompted to enter a reason for their absence.</span></span> <span data-ttu-id="50ee6-111">A távollét kódjának kiválasztásával megadhatja az okot.</span><span class="sxs-lookup"><span data-stu-id="50ee6-111">They can specify a reason by selecting an absence code.</span></span>

## <a name="absence-codes"></a><span data-ttu-id="50ee6-112">Távollétkódok</span><span class="sxs-lookup"><span data-stu-id="50ee6-112">Absence codes</span></span>

<span data-ttu-id="50ee6-113">A távolléti kódok meghatározzák a különböző típusú távolléteket.</span><span class="sxs-lookup"><span data-stu-id="50ee6-113">Absence codes define the various types of absence.</span></span> <span data-ttu-id="50ee6-114">A távolléti kódokat a cég határozza meg.</span><span class="sxs-lookup"><span data-stu-id="50ee6-114">Absence codes are defined by the company.</span></span>

<span data-ttu-id="50ee6-115">A távollétkódokra különböző szabályok alkalmazhatók.</span><span class="sxs-lookup"><span data-stu-id="50ee6-115">Various rules can be applied to absence codes.</span></span> <span data-ttu-id="50ee6-116">Például egy távolléti kód levonandó vagy fizetési támogatásként is beállítható.</span><span class="sxs-lookup"><span data-stu-id="50ee6-116">For example, an absence code can be configured to deduct or grant pay.</span></span>

<span data-ttu-id="50ee6-117">Például a vállalat meghatározza a **Késés** távolléti kód, amelyet a dolgozók akkor használnak, ha késnek, és a nem rendelkeznek rá megfelelő okkal.</span><span class="sxs-lookup"><span data-stu-id="50ee6-117">For example, a company defines a **Late** absence code that workers use if they come in late and don't have a good reason.</span></span> <span data-ttu-id="50ee6-118">A vállalat egy **Belső tanfolyam** távolléti kódot is meghatároz, amelyet a belső tanfolyamokon való részvételhez használnak a dolgozók.</span><span class="sxs-lookup"><span data-stu-id="50ee6-118">The company also defines an **Internal course** absence code that workers use for time that they spend attending internal courses.</span></span> <span data-ttu-id="50ee6-119">A távolléti kódok úgy állíthatók be, hogy a **Késés** levon a dolgozó fizetéséből, de a **Belső tanfolyam** nem.</span><span class="sxs-lookup"><span data-stu-id="50ee6-119">These absence codes can be set up so that **Late** deducts from a worker's pay but **Internal course** doesn't deduct from a worker's pay.</span></span>

<span data-ttu-id="50ee6-120">Automatikus távolléti kódok állíthatók be.</span><span class="sxs-lookup"><span data-stu-id="50ee6-120">You can set up automatic absence codes.</span></span> <span data-ttu-id="50ee6-121">A távollétkódok egy dolgozó idejének a kiszámítására használhatók, ha nincs távollét regisztrálva.</span><span class="sxs-lookup"><span data-stu-id="50ee6-121">These absence codes can be used to calculate a worker's time when no absence is registered.</span></span> <span data-ttu-id="50ee6-122">A dolgozói időprofil határozza meg, hogy a távolléti kód a normál munka időhöz vagy a rugalmas időhöz használatos.</span><span class="sxs-lookup"><span data-stu-id="50ee6-122">The worker's time profile determines whether the absence code for standard time or flex time is used.</span></span>

### <a name="set-up-standard-time-and-flex-time"></a><span data-ttu-id="50ee6-123">A normál munkaidő és a rugalmas idő beállítása</span><span class="sxs-lookup"><span data-stu-id="50ee6-123">Set up standard time and flex time</span></span>

- <span data-ttu-id="50ee6-124">A normál munkaidő és a rugalmas idő paramétereinek beállításához használja a **Távollét automatikus beillesztése** és a **Rugalmas idő automatikus beillesztése** lehetőségeket a **Munkaidő és jelenlét paraméterei** lapon.</span><span class="sxs-lookup"><span data-stu-id="50ee6-124">Configure the parameters for standard time and flex time by using the **Auto insert absence** and **Auto insert Flex-** options on the **Time and attendance parameters** page.</span></span>

## <a name="absence-groups"></a><span data-ttu-id="50ee6-125">Távollétcsoportok</span><span class="sxs-lookup"><span data-stu-id="50ee6-125">Absence groups</span></span>

<span data-ttu-id="50ee6-126">A távollétcsoportok a távolléti kódok csoportjai.</span><span class="sxs-lookup"><span data-stu-id="50ee6-126">Absence codes are grouped into absence groups.</span></span> <span data-ttu-id="50ee6-127">A távollétcsoportokat a közös jellemzőkkel rendelkező távollétkódok csoportosítására használhatja.</span><span class="sxs-lookup"><span data-stu-id="50ee6-127">You use absence groups to group absence codes that have common characteristics.</span></span> <span data-ttu-id="50ee6-128">A példák közé tartozik többek között a szabályos távollét kódjai, vagy a távollét orvos vizsgálat, esküdtszéki kötelezettség vagy beteg gyermek miatt.</span><span class="sxs-lookup"><span data-stu-id="50ee6-128">Examples include absence codes for a legal absence, or absence because of a doctor's appointment, jury duty, or a sick child.</span></span>

## <a name="planned-absence"></a><span data-ttu-id="50ee6-129">Tervezett távollét</span><span class="sxs-lookup"><span data-stu-id="50ee6-129">Planned absence</span></span>

<span data-ttu-id="50ee6-130">Ha tudja, hogy a dolgozó távol lesz egy időszakra, például egy közelgő szabadság miatt, a tervezett távollétet használhatja.</span><span class="sxs-lookup"><span data-stu-id="50ee6-130">If you know that a worker will be absent for a period, such as an upcoming vacation, you can use planned absence.</span></span> <span data-ttu-id="50ee6-131">A tervezett távollét beállításához a távolléti kódot úgy kell beállítani, hogy figyelembe vegye a tervezett távollétet.</span><span class="sxs-lookup"><span data-stu-id="50ee6-131">You set up planned absence by configuring the absence code so that it considers the planned absence.</span></span> <span data-ttu-id="50ee6-132">Tervezett távollét beállításakor a rendszer nem kér távolléti kódot a felhasználói időregisztrációk számításakor a távolléti időszak alatt.</span><span class="sxs-lookup"><span data-stu-id="50ee6-132">When you set up a planned absence, you aren't prompted for an absence code during the absence period when user time registrations are calculated.</span></span> <span data-ttu-id="50ee6-133">Tervezett távollétet meg lehet adni egy dolgozóra, vagy megadhat egy kötegelt feladatot a dolgozók tervezett távollétének tömeges frissítéséhez.</span><span class="sxs-lookup"><span data-stu-id="50ee6-133">Planned absence can be defined for a single worker, or you can define a batch job to bulk update the planned absence for workers.</span></span>

### <a name="set-up-planned-absence"></a><span data-ttu-id="50ee6-134">Tervezett távollét beállítása</span><span class="sxs-lookup"><span data-stu-id="50ee6-134">Set up planned absence</span></span>

1. <span data-ttu-id="50ee6-135">Válassza ki az **Emberi erőforrások** &gt; **Dolgozók** &gt; **Alkalmazottak** elemet, és válasszon ki egy alkalmazottat.</span><span class="sxs-lookup"><span data-stu-id="50ee6-135">Select **Human resources** &gt; **Workers** &gt; **Employees**, and select an employee.</span></span>
2. <span data-ttu-id="50ee6-136">Válassza az **Idő** &gt; **Idő-hozzárendelések** &gt; **Távollét regisztrálása** elemet, és végezze el a tervezett távollét beállítását.</span><span class="sxs-lookup"><span data-stu-id="50ee6-136">Select **Time** &gt; **Time assignments** &gt; **Time Absence registration**, and set up the planned absence.</span></span>

## <a name="interrupted-planned-absence"></a><span data-ttu-id="50ee6-137">Megszakított tervezett távollét</span><span class="sxs-lookup"><span data-stu-id="50ee6-137">Interrupted planned absence</span></span>

<span data-ttu-id="50ee6-138">Ha a tervezett távollét beállítása során a **Megszakítás** beállítást alkalmazza, a tervezett távollét megszakad, ha a dolgozó bejelentkezik a tervezett távolléti időszak alatt.</span><span class="sxs-lookup"><span data-stu-id="50ee6-138">If you apply the **Interrupt** option when you set up a planned absence, the planned absence will be interrupted if the worker signs in during the planned absence period.</span></span> <span data-ttu-id="50ee6-139">A tervezett távollét megjelölése **Megszakítva** lesz, és nem lesz hatással a jövőbeli számításokra.</span><span class="sxs-lookup"><span data-stu-id="50ee6-139">The planned absence will be marked as **Interrupted** and won't have any effect on future calculations.</span></span>

### <a name="set-up-a-planned-absence-for-interruption"></a><span data-ttu-id="50ee6-140">Tervezett távollét megszakításának beállítása</span><span class="sxs-lookup"><span data-stu-id="50ee6-140">Set up a planned absence for interruption</span></span>

1. <span data-ttu-id="50ee6-141">Nyissa meg a **Távollét regisztrálása** oldalt a tervezett távollét beállításának folyamatában leírtak szerint.</span><span class="sxs-lookup"><span data-stu-id="50ee6-141">Open the **Time Absence registration** page as described in the procedure for setting up planned absence.</span></span>
2. <span data-ttu-id="50ee6-142">Válassza a **Megszakítás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="50ee6-142">Select **Interrupt**.</span></span>

<span data-ttu-id="50ee6-143">A **Megszakítás** lehetőség akkor érvényes, ha az üzemirányítási terminálon vagy az üzemirányítási eszközön időt regisztrálnak.</span><span class="sxs-lookup"><span data-stu-id="50ee6-143">The **Interrupt** option applies when time is registered through the shop floor terminal or the shop floor device.</span></span> <span data-ttu-id="50ee6-144">A beállítás nem érvényes, ha a regisztrációkat beírják a számítási és a jóváhagyási lapon, vagy az **Elektronikus időkártya** oldalon.</span><span class="sxs-lookup"><span data-stu-id="50ee6-144">The option doesn't apply if the registrations are entered on the calculation and approval pages, or on the **Electronic timecard** page.</span></span>

## <a name="examples-of-the-use-of-absence-in-a-flex-profile"></a><span data-ttu-id="50ee6-145">Példák a távollét rugalmasidő-profilban való használatára</span><span class="sxs-lookup"><span data-stu-id="50ee6-145">Examples of the use of absence in a flex profile</span></span>

<span data-ttu-id="50ee6-146">Az alábbi három példa bemutatja a távollét számítási módját egy olyan profilban, amely rendelkezik rugalmasidő-időszakokkal.</span><span class="sxs-lookup"><span data-stu-id="50ee6-146">The following three examples show how absence is calculated in a profile that has flex periods.</span></span>

<span data-ttu-id="50ee6-147">A példák a következő profilt használják.</span><span class="sxs-lookup"><span data-stu-id="50ee6-147">The examples use the following profile.</span></span>

| <span data-ttu-id="50ee6-148">Érkezéskori blokkolás</span><span class="sxs-lookup"><span data-stu-id="50ee6-148">Clock-in</span></span> | <span data-ttu-id="50ee6-149">Szokásos idő</span><span class="sxs-lookup"><span data-stu-id="50ee6-149">Standard time</span></span>    | <span data-ttu-id="50ee6-150">Szünet</span><span class="sxs-lookup"><span data-stu-id="50ee6-150">Break</span></span>             | <span data-ttu-id="50ee6-151">Szokásos idő</span><span class="sxs-lookup"><span data-stu-id="50ee6-151">Standard time</span></span> | <span data-ttu-id="50ee6-152">Rugalmasidő-hiány</span><span class="sxs-lookup"><span data-stu-id="50ee6-152">Flex-</span></span>        | <span data-ttu-id="50ee6-153">Távozáskori blokkolás</span><span class="sxs-lookup"><span data-stu-id="50ee6-153">Clock-out</span></span> | <span data-ttu-id="50ee6-154">Rugalmasidő-többlet</span><span class="sxs-lookup"><span data-stu-id="50ee6-154">Flex+</span></span>        |
|----------|------------------|-------------------|---------------|--------------|-----------|--------------|
| <span data-ttu-id="50ee6-155">08:00</span><span class="sxs-lookup"><span data-stu-id="50ee6-155">8 AM</span></span>     | <span data-ttu-id="50ee6-156">09:00–11:30</span><span class="sxs-lookup"><span data-stu-id="50ee6-156">9 AM to 11:30 AM</span></span> | <span data-ttu-id="50ee6-157">11:30–12:00</span><span class="sxs-lookup"><span data-stu-id="50ee6-157">11:30 AM to 12 PM</span></span> | <span data-ttu-id="50ee6-158">12:00–15:00</span><span class="sxs-lookup"><span data-stu-id="50ee6-158">12 PM to 3 PM</span></span> | <span data-ttu-id="50ee6-159">15:00–16:00</span><span class="sxs-lookup"><span data-stu-id="50ee6-159">3 PM to 4 PM</span></span> | <span data-ttu-id="50ee6-160">16:00</span><span class="sxs-lookup"><span data-stu-id="50ee6-160">4 PM</span></span>      | <span data-ttu-id="50ee6-161">16:00–18:00</span><span class="sxs-lookup"><span data-stu-id="50ee6-161">4 PM to 6 PM</span></span> |

### <a name="example-1-signing-out-during-a-flex--period"></a><span data-ttu-id="50ee6-162">1. példa: Rugalmasidő-hiány időszakban való kiblokkolás</span><span class="sxs-lookup"><span data-stu-id="50ee6-162">Example 1: Signing out during a Flex- period</span></span>

<span data-ttu-id="50ee6-163">A dolgozó 08:00 órakor blokkol be, és 15:30 órakor blokkol ki.</span><span class="sxs-lookup"><span data-stu-id="50ee6-163">The worker clocks in at 8:00 AM and clocks out at 3:30 PM.</span></span> <span data-ttu-id="50ee6-164">Ebben az esetben, mivel a dolgozó távozáskori blokkolása a rugalmasidő-hiány időszakban történik, nem történik távollét számítása, és a dolgozó rugalmasidő-egyenlegből fél óra lesz levonva.</span><span class="sxs-lookup"><span data-stu-id="50ee6-164">In this case, because the worker clocks out during a Flex- period, no absence is calculated, and half an hour is deducted from the worker's flex balance.</span></span>

### <a name="example-2-signing-out-in-during-standard-time-period"></a><span data-ttu-id="50ee6-165">2. példa: Kiblokkolás a szokásos munkaidő alatt</span><span class="sxs-lookup"><span data-stu-id="50ee6-165">Example 2: Signing out in during Standard time period</span></span>

<span data-ttu-id="50ee6-166">A dolgozó 08:00 órakor blokkol be, és 14:30 órakor blokkol ki.</span><span class="sxs-lookup"><span data-stu-id="50ee6-166">The worker clocks in at 8:00 AM and clocks out at 2:30 PM.</span></span> <span data-ttu-id="50ee6-167">Ebben az esetben, mivel a dolgozó távozáskori blokkolása a szokásos időszakon belüli, távollét számítása történik 14:30 és 16:00 között, és 1,5 órás távolléti időszak lesz regisztrálva.</span><span class="sxs-lookup"><span data-stu-id="50ee6-167">In this case, because the worker clocks out during the Standard time period, absence is calculated from 2:30 PM to 4 PM, and an absence period of 1.5 hours is registered.</span></span> <span data-ttu-id="50ee6-168">Az adott időszakra vonatkozó távollétkód megadása kötelező.</span><span class="sxs-lookup"><span data-stu-id="50ee6-168">An absence code for that period is required.</span></span>

### <a name="example-3-signing-out-during-a-flex-period"></a><span data-ttu-id="50ee6-169">3. példa: Rugalmasidő-többlet időszakban való kiblokkolás</span><span class="sxs-lookup"><span data-stu-id="50ee6-169">Example 3: Signing out during a Flex+ period</span></span>

<span data-ttu-id="50ee6-170">A dolgozó 08:00 órakor blokkol be, és 16:30 órakor blokkol ki.</span><span class="sxs-lookup"><span data-stu-id="50ee6-170">The worker clocks in at 8:00 AM and clocks out at 4:30 PM.</span></span> <span data-ttu-id="50ee6-171">Ebben az esetben, mivel a dolgozó távozáskori blokkolása a rugalmasidő-többlet időszakban történik, nem történik távollét számítása, és a dolgozó rugalmasidő-egyenlegéhez fél óra lesz hozzáadva.</span><span class="sxs-lookup"><span data-stu-id="50ee6-171">In this case, because the worker clocks out during a Flex+ period, no absence is calculated, and half an hour is added to the worker's flex balance.</span></span>

## <a name="absence-in-the-calculation-and-approval-process"></a><span data-ttu-id="50ee6-172">Távollét a számítási és jóváhagyási folyamatban</span><span class="sxs-lookup"><span data-stu-id="50ee6-172">Absence in the calculation and approval process</span></span>

<span data-ttu-id="50ee6-173">A dolgozó időregisztrációt ki kell számítani és jóvá kell hagyni, mielőtt át lehetne vinni a bérrendszerbe fizetési tételekként.</span><span class="sxs-lookup"><span data-stu-id="50ee6-173">Worker time registrations must be calculated and approved before they can be transferred to a payroll system as pay items.</span></span>

<span data-ttu-id="50ee6-174">A jóváhagyó módosíthatja a dolgozó időregisztrációit.</span><span class="sxs-lookup"><span data-stu-id="50ee6-174">An approver can change a worker's time registrations.</span></span> <span data-ttu-id="50ee6-175">A jóváhagyó bármilyen, a dolgozó által regisztrált távollétet is módosíthat.</span><span class="sxs-lookup"><span data-stu-id="50ee6-175">The approver can even change any absence that the worker has registered.</span></span> <span data-ttu-id="50ee6-176">Ha a jóváhagyó kézzel beír egy időszakot, amelynek távolléti kódja van, az adott időszakra vonatkozó távolléti kódot nem bírálja felül a munkaidő és jelenlét oldal paramétereinek alapértelmezett távolléti kódja.</span><span class="sxs-lookup"><span data-stu-id="50ee6-176">If the approver manually enters a time period that has an absence code, the absence code for that period isn't overridden by the default absence code from the Time and attendance parameters.</span></span>

<span data-ttu-id="50ee6-177">Például egy dolgozó 10:00 órakor blokkol be, és kiválaszt egy távolléti kódot, amely azt jelzi, hogy késik.</span><span class="sxs-lookup"><span data-stu-id="50ee6-177">For example, a worker clocks in at 10 AM and selects an absence code that indicates that she is late.</span></span> <span data-ttu-id="50ee6-178">Később a dolgozó tájékoztatja a felettesét, hogy 08:00 és 10:00 között orvosnál volt.</span><span class="sxs-lookup"><span data-stu-id="50ee6-178">Later, the worker informs her supervisor that she had a doctor's appointment from 8 AM to 10 AM.</span></span> <span data-ttu-id="50ee6-179">Az orvos vizsgálat nem okozhat levonást a dolgozó fizetéséből.</span><span class="sxs-lookup"><span data-stu-id="50ee6-179">A doctor's appointment should not cause a deduction in the worker's pay.</span></span> <span data-ttu-id="50ee6-180">Ezért ebben az esetben a felügyelő módosíthatja a két órás távollétet 08:00 és 10:00 között kézzel beírva egy távolléti kódot, amely azt jelzi, hogy a két óra oka betegség volt.</span><span class="sxs-lookup"><span data-stu-id="50ee6-180">Therefore, in this case, the supervisor can adjust the two hours of absence from 8 AM to 10 AM by manually entering an absence code that indicates illness for those two hours.</span></span>

### <a name="calculate-and-approve-absence"></a><span data-ttu-id="50ee6-181">Távollét kiszámítására és a jóváhagyása</span><span class="sxs-lookup"><span data-stu-id="50ee6-181">Calculate and approve absence</span></span>

- <span data-ttu-id="50ee6-182">Válassza ki a **Munkaidő és jelenlét** &gt; **Ellenőrzés és jóváhagyás** &gt; **Jóváhagyás vagy Számítás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="50ee6-182">Select **Time attendance** &gt; **Review and approve** &gt; **Approve or Calculate**.</span></span>

