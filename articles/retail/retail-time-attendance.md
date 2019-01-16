---
title: "A munkaidő és a jelenlét-nyilvántartás kezelése a Retail alkalmazásban"
description: "Ez a témakör ismerteti az olyan helyzeteket, amelyek kezeléséhez használhatja a Microsoft Dynamics 365 for Retail programot."
author: aamirallaqaband
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: JMGParameters
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
ms.sourcegitcommit: 190d0b59ad2e232b33b3c0d1700cbaf95c45aeca
ms.openlocfilehash: 4c54909a02376a62a72a986e634649fa0ae54284
ms.contentlocale: hu-hu
ms.lasthandoff: 01/04/2019

---

# <a name="time-and-attendance-management-in-retail"></a><span data-ttu-id="8b030-103">A munkaidő és a jelenlét-nyilvántartás kezelése a Retail alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="8b030-103">Time and attendance management in Retail</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="8b030-104">Ez a témakör ismerteti az olyan helyzeteket, amelyek kezeléséhez használhatja a Microsoft Dynamics 365 for Retail programot.</span><span class="sxs-lookup"><span data-stu-id="8b030-104">This topic describes the scenarios that are supported for time and attendance management in Microsoft Dynamics 365 for Retail.</span></span>

## <a name="manage-worker-setup-and-scheduling"></a><span data-ttu-id="8b030-105">Dolgozók elhelyezésének és ütemezésének kezelése</span><span class="sxs-lookup"><span data-stu-id="8b030-105">Manage worker setup and scheduling</span></span>

### <a name="initial-configuration"></a><span data-ttu-id="8b030-106">Induló konfiguráció</span><span class="sxs-lookup"><span data-stu-id="8b030-106">Initial configuration</span></span>

- <span data-ttu-id="8b030-107">Futtassa a konfigurációs varázslót.</span><span class="sxs-lookup"><span data-stu-id="8b030-107">Run the configuration wizard.</span></span>
- <span data-ttu-id="8b030-108">Regisztrálja a dolgozókat időregisztrációs dolgozókként.</span><span class="sxs-lookup"><span data-stu-id="8b030-108">Register workers as time registration workers.</span></span>

### <a name="plan-worker-schedules"></a><span data-ttu-id="8b030-109">Tervezze meg a dolgozói beosztásokat</span><span class="sxs-lookup"><span data-stu-id="8b030-109">Plan worker schedules</span></span>

- <span data-ttu-id="8b030-110">Alkalmazzon profilokat a munkatervező segítségével.</span><span class="sxs-lookup"><span data-stu-id="8b030-110">Apply profiles by using the work planner.</span></span> <span data-ttu-id="8b030-111">További információ: [Profil alkalmazása a munkatervezővel](https://technet.microsoft.com/library/aa551234.aspx).</span><span class="sxs-lookup"><span data-stu-id="8b030-111">For more information, see [Apply profiles using work planner](https://technet.microsoft.com/library/aa551234.aspx).</span></span>

<span data-ttu-id="8b030-112">A konfiguráció lépéseivel kapcsolatos további információért, lásd: [Munkaidő és jelenlét beállítása](https://technet.microsoft.com/library/aa496971.aspx).</span><span class="sxs-lookup"><span data-stu-id="8b030-112">For information about the configuration steps, see [Setting up time and attendance](https://technet.microsoft.com/library/aa496971.aspx).</span></span>

### <a name="retail-specific-configuration"></a><span data-ttu-id="8b030-113">Kiskereskedelem-specifikus konfiguráció</span><span class="sxs-lookup"><span data-stu-id="8b030-113">Retail-specific configuration</span></span>

- <span data-ttu-id="8b030-114">Engedélyezzen egy funkcionális profilt a Blokkolóórához azon dolgozók számára, akiknek lehetővé kívánja tenni az időregisztrációt.</span><span class="sxs-lookup"><span data-stu-id="8b030-114">Enable a functionality profile for Time Clock, for workers that you want to enable time registrations for.</span></span> <span data-ttu-id="8b030-115">Kattintson a **Pénztár-funkcióprofilok** &gt; **Funkciók** &gt; **Pénztár idő regisztrációk** &gt; **Időregisztrációk engedélyezése** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8b030-115">Click **POS functionality profiles** &gt; **Functions** &gt; **POS time registrations** &gt; **Enable time registrations**.</span></span>
- <span data-ttu-id="8b030-116">Állítsa át a Pénztár (POS) engedélycsoportokat, hogy elérhetővé tegye a blokkolóóra bejegyzések megtekintése engedélyt.</span><span class="sxs-lookup"><span data-stu-id="8b030-116">Configure point of sale (POS) permissions groups to enable the View timeclock entries permission.</span></span> <span data-ttu-id="8b030-117">Ez az engedély lehetővé teszi, hogy a felhasználó megtekintse a bolt (Illetve más, a címjegyzék alapján a felhasználóhoz társítható boltok) dolgozóinak blokkolóóra regisztrációit.</span><span class="sxs-lookup"><span data-stu-id="8b030-117">This permission lets a user view the time clock registrations of other workers in the store (and from any other store that the user is associated with, via the address book).</span></span> <span data-ttu-id="8b030-118">Ezt az engedélyt a vezető szerepkörű dolgozók számára ajánlott engedélyezni.</span><span class="sxs-lookup"><span data-stu-id="8b030-118">You might want to enable this permission for a manager role but not for a cashier role.</span></span> <span data-ttu-id="8b030-119">Kattintson a **Pénztár-engedélycsoportok** &gt; **Blokkolóóra bejegyzéseinek megtekintése** gombra.</span><span class="sxs-lookup"><span data-stu-id="8b030-119">Click **POS permission groups** &gt; **View time clock entries**.</span></span>

## <a name="register-time"></a><span data-ttu-id="8b030-120">Idő regisztrálása</span><span class="sxs-lookup"><span data-stu-id="8b030-120">Register time</span></span>

### <a name="cashier-and-non-cashier-time-registrations"></a><span data-ttu-id="8b030-121">Pénztáros és nem a pénztáros időregisztrációk</span><span class="sxs-lookup"><span data-stu-id="8b030-121">Cashier and non-cashier time registrations</span></span>

- <span data-ttu-id="8b030-122">A Pénztáron:</span><span class="sxs-lookup"><span data-stu-id="8b030-122">On POS:</span></span>

    - <span data-ttu-id="8b030-123">Belépési műveletek:</span><span class="sxs-lookup"><span data-stu-id="8b030-123">Clock-in operations:</span></span>

        - <span data-ttu-id="8b030-124">Lépjen be egy nem pénztárgép-fiókkal kapcsolatos művelettel vagy új műszakkal.</span><span class="sxs-lookup"><span data-stu-id="8b030-124">Log on with a non-drawer operation or New shift.</span></span>
        - <span data-ttu-id="8b030-125">Válassza ki a Blokkolóóra műveletet.</span><span class="sxs-lookup"><span data-stu-id="8b030-125">Select a Time Clock operation.</span></span>
        - <span data-ttu-id="8b030-126">Válassza ki a kívánt műveletet:</span><span class="sxs-lookup"><span data-stu-id="8b030-126">Select a desired operation:</span></span>

            - <span data-ttu-id="8b030-127">Érkezéskori blokkolás</span><span class="sxs-lookup"><span data-stu-id="8b030-127">Clock-in</span></span>
            - <span data-ttu-id="8b030-128">Pihenő</span><span class="sxs-lookup"><span data-stu-id="8b030-128">Break for Work</span></span>
            - <span data-ttu-id="8b030-129">Ebédszünet</span><span class="sxs-lookup"><span data-stu-id="8b030-129">Break for Lunch</span></span>
            - <span data-ttu-id="8b030-130">Távozáskori blokkolás</span><span class="sxs-lookup"><span data-stu-id="8b030-130">Clock-out</span></span>

        <table>
        <thead>
        <tr>
        <th><span data-ttu-id="8b030-131">Jelenlegi állapot:</span><span class="sxs-lookup"><span data-stu-id="8b030-131">Current state</span></span></th>
        <th><span data-ttu-id="8b030-132">Elérhető műveletek</span><span class="sxs-lookup"><span data-stu-id="8b030-132">Available operations</span></span></th>
        </tr>
        </thead>
        <tbody>
        <tr>
        <td><span data-ttu-id="8b030-133">Érkezéskori blokkolás</span><span class="sxs-lookup"><span data-stu-id="8b030-133">Clock-in</span></span></td>
        <td>
        <ul>
        <li><span data-ttu-id="8b030-134">Pihenő</span><span class="sxs-lookup"><span data-stu-id="8b030-134">Break for Work</span></span></li>
        <li><span data-ttu-id="8b030-135">Ebédszünet</span><span class="sxs-lookup"><span data-stu-id="8b030-135">Break for Lunch</span></span></li>
        <li><span data-ttu-id="8b030-136">Távozáskori blokkolás</span><span class="sxs-lookup"><span data-stu-id="8b030-136">Clock-out</span></span></li>
        </ul>
        </td>
        </tr>
        <tr>
        <td><span data-ttu-id="8b030-137">Pihenő</span><span class="sxs-lookup"><span data-stu-id="8b030-137">Break for Work</span></span></td>
        <td><span data-ttu-id="8b030-138">Érkezéskori blokkolás</span><span class="sxs-lookup"><span data-stu-id="8b030-138">Clock-in</span></span></td>
        </tr>
        <tr>
        <td><span data-ttu-id="8b030-139">Ebédszünet</span><span class="sxs-lookup"><span data-stu-id="8b030-139">Break for Lunch</span></span></td>
        <td><span data-ttu-id="8b030-140">Érkezéskori blokkolás</span><span class="sxs-lookup"><span data-stu-id="8b030-140">Clock-in</span></span></td>
        </tr>
        <tr>
        <td><span data-ttu-id="8b030-141">Távozáskori blokkolás</span><span class="sxs-lookup"><span data-stu-id="8b030-141">Clock-out</span></span></td>
        <td><span data-ttu-id="8b030-142">Érkezéskori blokkolás</span><span class="sxs-lookup"><span data-stu-id="8b030-142">Clock-in</span></span></td>
        </tr>
        </tbody>
        </table>

        <span data-ttu-id="8b030-143">[![BlokkolóóraÁllások](./media/timeclockstates.png)](./media/timeclockstates.png)</span><span class="sxs-lookup"><span data-stu-id="8b030-143">[![TimeClockStates](./media/timeclockstates.png)](./media/timeclockstates.png)</span></span>

- <span data-ttu-id="8b030-144">Tekintse meg a konfigurációs üzenetet és igazolja, hogy a pillanatnyi tevékenység idő korrekt.</span><span class="sxs-lookup"><span data-stu-id="8b030-144">View the confirmation message, and validate that the current activity time is correct.</span></span>
- <span data-ttu-id="8b030-145">Napló:</span><span class="sxs-lookup"><span data-stu-id="8b030-145">Logbook:</span></span>

    - <span data-ttu-id="8b030-146">Kattintson a **Napló** gombra a blokkolóóra tevékenység megtekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="8b030-146">Click **Logbook** to view time clock activity.</span></span>
    - <span data-ttu-id="8b030-147">Alkalmazzon időszűrőket a különböző időablakok kiválasztásához.</span><span class="sxs-lookup"><span data-stu-id="8b030-147">Use time filters to select different time windows.</span></span>
    - <span data-ttu-id="8b030-148">Ha több tárolási helyen dolgozik, az összes helyszínen rögzített időregisztrációját megtekintheti.</span><span class="sxs-lookup"><span data-stu-id="8b030-148">If you work at multiple store locations, you see your time registrations from all the stores where you recorded time.</span></span> <span data-ttu-id="8b030-149">Az üzletszűrő segítségével kiválaszthatja melyik üzlet időregisztrációit kívánja megtekinteni.</span><span class="sxs-lookup"><span data-stu-id="8b030-149">You can use the store filter to view time registrations from a selected store.</span></span>

- <span data-ttu-id="8b030-150">Eltérő időzónák:</span><span class="sxs-lookup"><span data-stu-id="8b030-150">Different time zones:</span></span>

    - <span data-ttu-id="8b030-151">Ha az időt egy másik helyről nézi meg (a pénztáros naplóhoz vagy vezetői pozíció esetén a **Blokkolóóra bejegyzések megtekintése** opciót használva) és az adott hely másik időzónába esik, a megjelenített időpontok automatikusan az ön időzónájához igazodnak.</span><span class="sxs-lookup"><span data-stu-id="8b030-151">If you view time from a different location (for the cashier logbook, or by using **View timeclock entries** for a manager scenario), and that location is in a different time zone, the time records that you see are converted to your local time zone.</span></span> <span data-ttu-id="8b030-152">Például, ön két üzlet vezetője. Az egyik Arizónában, a másik Nevadában található.</span><span class="sxs-lookup"><span data-stu-id="8b030-152">For example, you are a manager for two stores, one in Arizona and the other in Nevada.</span></span> <span data-ttu-id="8b030-153">Az arizonai üzlet pénztárosa beregisztrál a blokkolóórán</span><span class="sxs-lookup"><span data-stu-id="8b030-153">A cashier registers a clock-in at 9:00 A.M.</span></span> <span data-ttu-id="8b030-154">reggel 9 órakor.</span><span class="sxs-lookup"><span data-stu-id="8b030-154">in Arizona.</span></span> <span data-ttu-id="8b030-155">Az adott időpontban Nevadában, reggel 8 óra van.</span><span class="sxs-lookup"><span data-stu-id="8b030-155">At that moment, the time in Nevada is 8:00 A.M.</span></span> <span data-ttu-id="8b030-156">Tehát, ha ön a nevadai üzletben tartózkodik és megnézi az időregisztrációkat, a regisztrált idő reggel 8 óraként lesz mutatva.</span><span class="sxs-lookup"><span data-stu-id="8b030-156">Therefore, if you are in the Nevada store and look at time registration records, the time registration is marked as 8 A.M.</span></span>

## <a name="view-worker-time-registrations"></a><span data-ttu-id="8b030-157">Dolgozói munkaidő-nyilvántartás megtekintése</span><span class="sxs-lookup"><span data-stu-id="8b030-157">View worker time registrations</span></span>

### <a name="view-worker-time-registrations-and-filter-by-store-or-activity-type"></a><span data-ttu-id="8b030-158">Dolgozói időregisztrációk megtekintése és szűrés üzlet vagy tevékenységtípus alapján</span><span class="sxs-lookup"><span data-stu-id="8b030-158">View worker time registrations, and filter by store or activity type</span></span>

<span data-ttu-id="8b030-159">A Pénztáron:</span><span class="sxs-lookup"><span data-stu-id="8b030-159">On POS:</span></span>

- <span data-ttu-id="8b030-160">Válassza ki a **Blokkolóóra bejegyzéseinek megtekintése** opciót.</span><span class="sxs-lookup"><span data-stu-id="8b030-160">Select **View timeclock entries**.</span></span>
- <span data-ttu-id="8b030-161">Az összes olyan dolgozó időregisztrációját láthatja akik önnel azonos üzlethez vannak hozzárendelve.</span><span class="sxs-lookup"><span data-stu-id="8b030-161">You see time clock registration activities from all workers that are assigned to the same stores that you're assigned to.</span></span>
- <span data-ttu-id="8b030-162">Az időregisztrációk szűréséhez használhatja a tevékenységtípus szerinti és az üzlet szerinti szűrőket.</span><span class="sxs-lookup"><span data-stu-id="8b030-162">You can use the activity type and store filters to filter on time registrations.</span></span>

## <a name="process-and-manage-time-registrations"></a><span data-ttu-id="8b030-163">Időregisztrációk feldolgozása és kezelése</span><span class="sxs-lookup"><span data-stu-id="8b030-163">Process and manage time registrations</span></span>

<span data-ttu-id="8b030-164">A Dynamics 365 for Retail-felhasználó követi a munkafolyamatot, hogy kiszámolja, jóváhagyja, valamint áthelyezze az időregisztrációkat a bérlistára.</span><span class="sxs-lookup"><span data-stu-id="8b030-164">A Dynamics 365 for Retail user follows the workflow to calculate, approve, and transfer time registrations to payroll.</span></span>

### <a name="primary-operations"></a><span data-ttu-id="8b030-165">Elsődleges műveletek</span><span class="sxs-lookup"><span data-stu-id="8b030-165">Primary operations</span></span>

- <span data-ttu-id="8b030-166">Számítás</span><span class="sxs-lookup"><span data-stu-id="8b030-166">Calculate</span></span>
- <span data-ttu-id="8b030-167">Jóváhagy</span><span class="sxs-lookup"><span data-stu-id="8b030-167">Approve</span></span>
- <span data-ttu-id="8b030-168">Benyújtás a bérlistára</span><span class="sxs-lookup"><span data-stu-id="8b030-168">Submit to payroll</span></span>

### <a name="other-common-operations"></a><span data-ttu-id="8b030-169">Egyéb általános műveletek</span><span class="sxs-lookup"><span data-stu-id="8b030-169">Other common operations</span></span>

- <span data-ttu-id="8b030-170">Szállítmány kicsekkolás</span><span class="sxs-lookup"><span data-stu-id="8b030-170">Bulk Clock-out</span></span>
- <span data-ttu-id="8b030-171">Távollét regisztrálása</span><span class="sxs-lookup"><span data-stu-id="8b030-171">Register Absence</span></span>

<span data-ttu-id="8b030-172">Az Idő és jelenlét regisztrációkkal kapcsolatos további tudnivalókat lásd: [Feldolgozási idő és jelenlét nyilvántartása](https://technet.microsoft.com/library/aa573180.aspx).</span><span class="sxs-lookup"><span data-stu-id="8b030-172">For more information about how to process time and attendance registrations, see [Process time and attendance registrations](https://technet.microsoft.com/library/aa573180.aspx).</span></span>

