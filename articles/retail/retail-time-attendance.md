---
title: "Munkaidő és jelenlét"
description: "Ez a témakör ismerteti az olyan helyzeteket, amelyek kezeléséhez használhatja a Microsoft Dynamics 365 for Retail programot."
author: aamirallaqaband
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 62813
ms.assetid: 821994a6-cd29-45a3-a526-ce204064f080
ms.search.region: global
ms.search.industry: Retail
ms.author: aamiral
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: d5672579c1e2d51e4b6494a1e86e3606c09a93a2
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="retail-time-and-attendance"></a><span data-ttu-id="89be6-103">Kiskereskedelmi munkaidő és jelenlét</span><span class="sxs-lookup"><span data-stu-id="89be6-103">Retail time and attendance</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="89be6-104">Ez a témakör ismerteti az olyan helyzeteket, amelyek kezeléséhez használhatja a Microsoft Dynamics 365 for Retail programot.</span><span class="sxs-lookup"><span data-stu-id="89be6-104">This topic describes the scenarios that are supported for time and attendance management in Microsoft Dynamics 365 for Retail.</span></span> 

<a name="manage-worker-setup-and-scheduling"></a><span data-ttu-id="89be6-105">Dolgozók elhelyezésének és ütemezésének kezelése</span><span class="sxs-lookup"><span data-stu-id="89be6-105">Manage worker setup and scheduling</span></span>
----------------------------------

### <a name="initial-configuration"></a><span data-ttu-id="89be6-106">Induló konfiguráció</span><span class="sxs-lookup"><span data-stu-id="89be6-106">Initial configuration</span></span>

-   <span data-ttu-id="89be6-107">Futtassa a konfigurációs varázslót.</span><span class="sxs-lookup"><span data-stu-id="89be6-107">Run the configuration wizard.</span></span>
-   <span data-ttu-id="89be6-108">Regisztrálja a dolgozókat időregisztrációs dolgozókként.</span><span class="sxs-lookup"><span data-stu-id="89be6-108">Register workers as time registration workers.</span></span>

### <a name="plan-worker-schedules"></a><span data-ttu-id="89be6-109">Tervezze meg a dolgozói beosztásokat</span><span class="sxs-lookup"><span data-stu-id="89be6-109">Plan worker schedules</span></span>

-   <span data-ttu-id="89be6-110">Alkalmazzon profilokat a munkatervező segítségével.</span><span class="sxs-lookup"><span data-stu-id="89be6-110">Apply profiles by using the work planner.</span></span> <span data-ttu-id="89be6-111">További tudnivalókért: <https://technet.microsoft.com/en-us/library/aa551234.aspx>.</span><span class="sxs-lookup"><span data-stu-id="89be6-111">For more information, see <https://technet.microsoft.com/en-us/library/aa551234.aspx>.</span></span>

<span data-ttu-id="89be6-112">A konfigurációs lépésekkel kapcsolatos információkért látogassa meg a <https://technet.microsoft.com/en-us/library/aa496971.aspx> honlapot.</span><span class="sxs-lookup"><span data-stu-id="89be6-112">For information about the configuration steps, see <https://technet.microsoft.com/en-us/library/aa496971.aspx>.</span></span>

### <a name="retail-specific-configuration"></a><span data-ttu-id="89be6-113">Kiskereskedelem-specifikus konfiguráció</span><span class="sxs-lookup"><span data-stu-id="89be6-113">Retail-specific configuration</span></span>

-   <span data-ttu-id="89be6-114">Engedélyezzen egy funkcionális profilt a Blokkolóórához azon dolgozók számára, akiknek lehetővé kívánja tenni az időregisztrációt.</span><span class="sxs-lookup"><span data-stu-id="89be6-114">Enable a functionality profile for Time Clock, for workers that you want to enable time registrations for.</span></span> <span data-ttu-id="89be6-115">Kattintson a **Pénztár-funkcióprofilok** &gt; **Funkciók** &gt; **Pénztár idő regisztrációk** &gt; **Időregisztrációk engedélyezése** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="89be6-115">Click **POS functionality profiles** &gt; **Functions** &gt; **POS time registrations** &gt; **Enable time registrations**.</span></span>
-   <span data-ttu-id="89be6-116">Állítsa át a Pénztár (POS) engedélycsoportokat, hogy elérhetővé tegye a blokkolóóra bejegyzések megtekintése engedélyt.</span><span class="sxs-lookup"><span data-stu-id="89be6-116">Configure point of sale (POS) permissions groups to enable the View timeclock entries permission.</span></span> <span data-ttu-id="89be6-117">Ez az engedély lehetővé teszi, hogy a felhasználó megtekintse a bolt (Illetve más, a címjegyzék alapján a felhasználóhoz társítható boltok) dolgozóinak blokkolóóra regisztrációit.</span><span class="sxs-lookup"><span data-stu-id="89be6-117">This permission lets a user view the time clock registrations of other workers in the store (and from any other store that the user is associated with, via the address book).</span></span> <span data-ttu-id="89be6-118">Ezt az engedélyt a vezető szerepkörű dolgozók számára ajánlott engedélyezni.</span><span class="sxs-lookup"><span data-stu-id="89be6-118">You might want to enable this permission for a manager role but not for a cashier role.</span></span> <span data-ttu-id="89be6-119">Kattintson a **Pénztár-engedélycsoportok** &gt; **Blokkolóóra bejegyzéseinek megtekintése** gombra.</span><span class="sxs-lookup"><span data-stu-id="89be6-119">Click **POS permission groups** &gt; **View time clock entries**.</span></span>

## <a name="register-time"></a><span data-ttu-id="89be6-120">Idő regisztrálása</span><span class="sxs-lookup"><span data-stu-id="89be6-120">Register time</span></span>
### <a name="cashier-and-non-cashier-time-registrations"></a><span data-ttu-id="89be6-121">Pénztáros és nem a pénztáros időregisztrációk</span><span class="sxs-lookup"><span data-stu-id="89be6-121">Cashier and non-cashier time registrations</span></span>

-   <span data-ttu-id="89be6-122">A Pénztáron:</span><span class="sxs-lookup"><span data-stu-id="89be6-122">On POS:</span></span>
    -   <span data-ttu-id="89be6-123">Belépési műveletek:</span><span class="sxs-lookup"><span data-stu-id="89be6-123">Clock-in operations:</span></span>
        -   <span data-ttu-id="89be6-124">Lépjen be egy nem pénztárgép-fiókkal kapcsolatos művelettel vagy új műszakkal.</span><span class="sxs-lookup"><span data-stu-id="89be6-124">Log on with a non-drawer operation or New shift.</span></span>
        -   <span data-ttu-id="89be6-125">Válassza ki a Blokkolóóra műveletet.</span><span class="sxs-lookup"><span data-stu-id="89be6-125">Select a Time Clock operation.</span></span>
        -   <span data-ttu-id="89be6-126">Válassza ki a kívánt műveletet:</span><span class="sxs-lookup"><span data-stu-id="89be6-126">Select a desired operation:</span></span>
            -   <span data-ttu-id="89be6-127">Érkezéskori blokkolás</span><span class="sxs-lookup"><span data-stu-id="89be6-127">Clock-in</span></span>
            -   <span data-ttu-id="89be6-128">Pihenő</span><span class="sxs-lookup"><span data-stu-id="89be6-128">Break for Work</span></span>
            -   <span data-ttu-id="89be6-129">Ebédszünet</span><span class="sxs-lookup"><span data-stu-id="89be6-129">Break for Lunch</span></span>
            -   <span data-ttu-id="89be6-130">Távozáskori blokkolás</span><span class="sxs-lookup"><span data-stu-id="89be6-130">Clock-out</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="89be6-131">Jelenlegi állapot:</span><span class="sxs-lookup"><span data-stu-id="89be6-131">Current state</span></span></th>
    <th><span data-ttu-id="89be6-132">Elérhető műveletek</span><span class="sxs-lookup"><span data-stu-id="89be6-132">Available operations</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><span data-ttu-id="89be6-133">Érkezéskori blokkolás</span><span class="sxs-lookup"><span data-stu-id="89be6-133">Clock-in</span></span></td>
    <td><ul>
    <li><span data-ttu-id="89be6-134">Pihenő</span><span class="sxs-lookup"><span data-stu-id="89be6-134">Break for Work</span></span></li>
    <li><span data-ttu-id="89be6-135">Ebédszünet</span><span class="sxs-lookup"><span data-stu-id="89be6-135">Break for Lunch</span></span></li>
    <li><span data-ttu-id="89be6-136">Távozáskori blokkolás</span><span class="sxs-lookup"><span data-stu-id="89be6-136">Clock-out</span></span></li>
    </ul></td>
    </tr>
    <tr class="even">
    <td><span data-ttu-id="89be6-137">Pihenő</span><span class="sxs-lookup"><span data-stu-id="89be6-137">Break for Work</span></span></td>
    <td><span data-ttu-id="89be6-138">Érkezéskori blokkolás</span><span class="sxs-lookup"><span data-stu-id="89be6-138">Clock-in</span></span></td>
    </tr>
    <tr class="odd">
    <td><span data-ttu-id="89be6-139">Ebédszünet</span><span class="sxs-lookup"><span data-stu-id="89be6-139">Break for Lunch</span></span></td>
    <td><span data-ttu-id="89be6-140">Érkezéskori blokkolás</span><span class="sxs-lookup"><span data-stu-id="89be6-140">Clock-in</span></span></td>
    </tr>
    <tr class="even">
    <td><span data-ttu-id="89be6-141">Távozáskori blokkolás</span><span class="sxs-lookup"><span data-stu-id="89be6-141">Clock-out</span></span></td>
    <td><span data-ttu-id="89be6-142">Érkezéskori blokkolás</span><span class="sxs-lookup"><span data-stu-id="89be6-142">Clock-in</span></span></td>
    </tr>
    </tbody>
    </table>

    <span data-ttu-id="89be6-143">[![BlokkolóóraÁllások](./media/timeclockstates.png)](./media/timeclockstates.png)</span><span class="sxs-lookup"><span data-stu-id="89be6-143">[![TimeClockStates](./media/timeclockstates.png)](./media/timeclockstates.png)</span></span>
-   <span data-ttu-id="89be6-144">Tekintse meg a konfigurációs üzenetet és igazolja, hogy a pillanatnyi tevékenység idő korrekt.</span><span class="sxs-lookup"><span data-stu-id="89be6-144">View the confirmation message, and validate that the current activity time is correct.</span></span>
-   <span data-ttu-id="89be6-145">Napló:</span><span class="sxs-lookup"><span data-stu-id="89be6-145">Logbook:</span></span>
    -   <span data-ttu-id="89be6-146">Kattintson a **Napló** gombra a blokkolóóra tevékenység megtekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="89be6-146">Click **Logbook** to view time clock activity.</span></span>
    -   <span data-ttu-id="89be6-147">Alkalmazzon időszűrőket a különböző időablakok kiválasztásához.</span><span class="sxs-lookup"><span data-stu-id="89be6-147">Use time filters to select different time windows.</span></span>
    -   <span data-ttu-id="89be6-148">Ha több tárolási helyen dolgozik, az összes helyszínen rögzített időregisztrációját megtekintheti.</span><span class="sxs-lookup"><span data-stu-id="89be6-148">If you work at multiple store locations, you see your time registrations from all the stores where you recorded time.</span></span> <span data-ttu-id="89be6-149">Az üzletszűrő segítségével kiválaszthatja melyik üzlet időregisztrációit kívánja megtekinteni.</span><span class="sxs-lookup"><span data-stu-id="89be6-149">You can use the store filter to view time registrations from a selected store.</span></span>

<!-- -->

-   <span data-ttu-id="89be6-150">Eltérő időzónák:</span><span class="sxs-lookup"><span data-stu-id="89be6-150">Different time zones:</span></span>
    -   <span data-ttu-id="89be6-151">Ha az időt egy másik helyről nézi meg (a pénztáros naplóhoz vagy vezetői pozíció esetén a **Blokkolóóra bejegyzések megtekintése** opciót használva) és az adott hely másik időzónába esik, a megjelenített időpontok automatikusan az ön időzónájához igazodnak.</span><span class="sxs-lookup"><span data-stu-id="89be6-151">If you view time from a different location (for the cashier logbook, or by using **View timeclock entries** for a manager scenario), and that location is in a different time zone, the time records that you see are converted to your local time zone.</span></span> <span data-ttu-id="89be6-152">Például, ön két üzlet vezetője. Az egyik Arizónában, a másik Nevadában található.</span><span class="sxs-lookup"><span data-stu-id="89be6-152">For example, you are a manager for two stores, one in Arizona and the other in Nevada.</span></span> <span data-ttu-id="89be6-153">Az arizonai üzlet pénztárosa beregisztrál a blokkolóórán</span><span class="sxs-lookup"><span data-stu-id="89be6-153">A cashier registers a clock-in at 9:00 A.M.</span></span> <span data-ttu-id="89be6-154">reggel 9 órakor.</span><span class="sxs-lookup"><span data-stu-id="89be6-154">in Arizona.</span></span> <span data-ttu-id="89be6-155">Az adott időpontban Nevadában, reggel 8 óra van.</span><span class="sxs-lookup"><span data-stu-id="89be6-155">At that moment, the time in Nevada is 8:00 A.M.</span></span> <span data-ttu-id="89be6-156">Tehát, ha ön a nevadai üzletben tartózkodik és megnézi az időregisztrációkat, a regisztrált idő reggel 8 óraként lesz mutatva.</span><span class="sxs-lookup"><span data-stu-id="89be6-156">Therefore, if you are in the Nevada store and look at time registration records, the time registration is marked as 8 A.M.</span></span>

## <a name="view-worker-time-registrations"></a><span data-ttu-id="89be6-157">Dolgozói munkaidő-nyilvántartás megtekintése</span><span class="sxs-lookup"><span data-stu-id="89be6-157">View worker time registrations</span></span>
### <a name="view-worker-time-registrations-and-filter-by-store-or-activity-type"></a><span data-ttu-id="89be6-158">Dolgozói időregisztrációk megtekintése és szűrés üzlet vagy tevékenységtípus alapján</span><span class="sxs-lookup"><span data-stu-id="89be6-158">View worker time registrations, and filter by store or activity type</span></span>

<span data-ttu-id="89be6-159">A Pénztáron:</span><span class="sxs-lookup"><span data-stu-id="89be6-159">On POS:</span></span>

-   <span data-ttu-id="89be6-160">Válassza ki a **Blokkolóóra bejegyzéseinek megtekintése** opciót.</span><span class="sxs-lookup"><span data-stu-id="89be6-160">Select **View timeclock entries**.</span></span>
-   <span data-ttu-id="89be6-161">Az összes olyan dolgozó időregisztrációját láthatja akik önnel azonos üzlethez vannak hozzárendelve.</span><span class="sxs-lookup"><span data-stu-id="89be6-161">You see time clock registration activities from all workers that are assigned to the same stores that you're assigned to.</span></span>
-   <span data-ttu-id="89be6-162">Az időregisztrációk szűréséhez használhatja a tevékenységtípus szerinti és az üzlet szerinti szűrőket.</span><span class="sxs-lookup"><span data-stu-id="89be6-162">You can use the activity type and store filters to filter on time registrations.</span></span>

## <a name="process-and-manage-time-registrations"></a><span data-ttu-id="89be6-163">Időregisztrációk feldolgozása és kezelése</span><span class="sxs-lookup"><span data-stu-id="89be6-163">Process and manage time registrations</span></span>
<span data-ttu-id="89be6-164">A Dynamics 365 for Retail-felhasználó követi a munkafolyamatot, hogy kiszámolja, jóváhagyja, valamint áthelyezze az időregisztrációkat a bérlistára.</span><span class="sxs-lookup"><span data-stu-id="89be6-164">A Dynamics 365 for Retail user follows the workflow to calculate, approve, and transfer time registrations to payroll.</span></span>

### <a name="primary-operations"></a><span data-ttu-id="89be6-165">Elsődleges műveletek</span><span class="sxs-lookup"><span data-stu-id="89be6-165">Primary operations</span></span>

-   <span data-ttu-id="89be6-166">Számítás</span><span class="sxs-lookup"><span data-stu-id="89be6-166">Calculate</span></span>
-   <span data-ttu-id="89be6-167">Jóváhagy</span><span class="sxs-lookup"><span data-stu-id="89be6-167">Approve</span></span>
-   <span data-ttu-id="89be6-168">Benyújtás a bérlistára</span><span class="sxs-lookup"><span data-stu-id="89be6-168">Submit to payroll</span></span>

### <a name="other-common-operations"></a><span data-ttu-id="89be6-169">Egyéb általános műveletek</span><span class="sxs-lookup"><span data-stu-id="89be6-169">Other common operations</span></span>

-   <span data-ttu-id="89be6-170">Szállítmány kicsekkolás</span><span class="sxs-lookup"><span data-stu-id="89be6-170">Bulk Clock-out</span></span>
-   <span data-ttu-id="89be6-171">Távollét regisztrálása</span><span class="sxs-lookup"><span data-stu-id="89be6-171">Register Absence</span></span>

<span data-ttu-id="89be6-172">Az idő feldolgozásáról és a jelenléti regisztrációkról szóló további információkért látogassa meg a következő oldalt: <https://technet.microsoft.com/en-us/library/aa573180.aspx>.</span><span class="sxs-lookup"><span data-stu-id="89be6-172">For more information about how to process time and attendance registrations, see <https://technet.microsoft.com/en-us/library/aa573180.aspx>.</span></span>




