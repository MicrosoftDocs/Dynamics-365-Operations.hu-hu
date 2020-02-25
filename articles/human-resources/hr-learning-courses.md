---
title: Tanfolyamok beállítása
description: Az emberi erőforrások-rendszergazdák és a vezetők a tanfolyamok szolgáltatások segítségével karbantartják a dolgozóknak nyújtott képzések információit.
author: andreabichsel
manager: AnnBe
ms.date: 06/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
ms.search.form: HcmCourseType, HcmCourseTypeGroup, HRMCourseTable
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Human Resources
ms.custom: 7532
ms.assetid: a6950c29-8b3e-45b2-9084-ddfb1317ffaa
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: c3c23ab6fca3f97fbca9edfe83c656e7ca8a2800
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/03/2020
ms.locfileid: "3009269"
---
# <a name="set-up-training-courses"></a><span data-ttu-id="45a2c-103">Tanfolyamok beállítása</span><span class="sxs-lookup"><span data-stu-id="45a2c-103">Set up training courses</span></span>

<span data-ttu-id="45a2c-104">Az emberi erőforrások-rendszergazdák és a vezetők a tanfolyamok szolgáltatások segítségével karbantartják a dolgozóknak nyújtott képzések információit.</span><span class="sxs-lookup"><span data-stu-id="45a2c-104">Human resources administrators and managers can use the courses features to maintain information about the training that's offered to workers.</span></span>

 <a name="set-up-prerequisites"></a><span data-ttu-id="45a2c-105"> A telepítés előfeltételei</span><span class="sxs-lookup"><span data-stu-id="45a2c-105">Set up prerequisites</span></span>
---------------------

<span data-ttu-id="45a2c-106">A következő adatokat kötelező megadni, és be kell állítani a tanfolyamok létrehozása előtt.</span><span class="sxs-lookup"><span data-stu-id="45a2c-106">The following information is required and must be set up before you create courses.</span></span>
-   <span data-ttu-id="45a2c-107">**Tanfolyamtípusok**</span><span class="sxs-lookup"><span data-stu-id="45a2c-107">**Course types**</span></span>

<span data-ttu-id="45a2c-108">A következő adatokat nem kötelezően megadandó információt, amelyet meg lehet adni, a tanfolyamok.</span><span class="sxs-lookup"><span data-stu-id="45a2c-108">The following information is optional information that you can specify for courses.</span></span> <span data-ttu-id="45a2c-109">Ha tudja, hogy ki fogja bevinni tanfolyamok ezt az információt, akkor ezeket az adatokat kell beállítani, tanfolyam rekordok létrehozása előtt.</span><span class="sxs-lookup"><span data-stu-id="45a2c-109">If you know that you will be entering this information for courses, you should set up this information before you create course records.</span></span>
-   <span data-ttu-id="45a2c-110">**Oktatótermi csoportok**</span><span class="sxs-lookup"><span data-stu-id="45a2c-110">**Classroom groups**</span></span>
-   <span data-ttu-id="45a2c-111">**Tanfolyami csoportok**</span><span class="sxs-lookup"><span data-stu-id="45a2c-111">**Course groups**</span></span>
-   <span data-ttu-id="45a2c-112">**Tanfolyami helyszínek**</span><span class="sxs-lookup"><span data-stu-id="45a2c-112">**Course locations**</span></span>
-   <span data-ttu-id="45a2c-113">**Oktatótermek**</span><span class="sxs-lookup"><span data-stu-id="45a2c-113">**Classrooms**</span></span>
-   <span data-ttu-id="45a2c-114">**Oktatók**</span><span class="sxs-lookup"><span data-stu-id="45a2c-114">**Instructors**</span></span>

## <a name="course-types"></a><span data-ttu-id="45a2c-115">Tanfolyamtípusok</span><span class="sxs-lookup"><span data-stu-id="45a2c-115">Course types</span></span>
<span data-ttu-id="45a2c-116">Tanfolyamtípusok a tanfolyamok elosztását a szerkezetben, és a tanfolyam tartalma csoportosítására használhatók.</span><span class="sxs-lookup"><span data-stu-id="45a2c-116">You can use course types to categorize courses according to the structure or content of the course.</span></span> <span data-ttu-id="45a2c-117">Tanfolyam típusokat hozhat létre a **Kurzus típusok** oldalon.</span><span class="sxs-lookup"><span data-stu-id="45a2c-117">You can create course types on the **Course types** page.</span></span> <span data-ttu-id="45a2c-118">Tanfolyam rekord létrehozásakor ki kell választania egy tanfolyamtípus.</span><span class="sxs-lookup"><span data-stu-id="45a2c-118">You must select a course type when you create a course record.</span></span>

## <a name="course-setup-type"></a><span data-ttu-id="45a2c-119">Tanfolyamtípus - szakértelem</span><span class="sxs-lookup"><span data-stu-id="45a2c-119">Course setup type</span></span>
<span data-ttu-id="45a2c-120">Az alábbi táblázat felsorolja azokat a tanfolyamok háromféle beállítása.</span><span class="sxs-lookup"><span data-stu-id="45a2c-120">The following table lists the three setup types for courses.</span></span> <span data-ttu-id="45a2c-121">Beállítási típusok határozzák meg, hogy a Tanfolyam felépítése.</span><span class="sxs-lookup"><span data-stu-id="45a2c-121">Setup types determine the structure of the course.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="45a2c-122">Ellátási típus beállítása</span><span class="sxs-lookup"><span data-stu-id="45a2c-122">Setup type</span></span></th>
<th><span data-ttu-id="45a2c-123">Leírás</span><span class="sxs-lookup"><span data-stu-id="45a2c-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="45a2c-124"><strong>Normál</strong></span><span class="sxs-lookup"><span data-stu-id="45a2c-124"><strong>Standard</strong></span></span></td>
<td><span data-ttu-id="45a2c-125">Jelölje be ezt a típust, amelyet nem kell minden naphoz napirendet tanfolyamok.</span><span class="sxs-lookup"><span data-stu-id="45a2c-125">Select this type for courses that will not have a daily agenda.</span></span> <span data-ttu-id="45a2c-126">Új terv létrehozása esetén az alapértelmezett állapot Létrehozva.</span><span class="sxs-lookup"><span data-stu-id="45a2c-126">This is the default setup type when you create a new course.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="45a2c-127"><strong>Napirend</strong></span><span class="sxs-lookup"><span data-stu-id="45a2c-127"><strong>Agenda</strong></span></span></td>
<td><span data-ttu-id="45a2c-128">Válassza ezt atípust egy kurzus minden egyes napjának részleteinek megtervezéséhez, amely több napon keresztül folyik le.</span><span class="sxs-lookup"><span data-stu-id="45a2c-128">Select this type to plan the details of each day of a course that takes place over multiple days.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="45a2c-129"><strong>Munkamenet + Napirend</strong></span><span class="sxs-lookup"><span data-stu-id="45a2c-129"><strong>Agenda + session</strong></span></span></td>
<td><span data-ttu-id="45a2c-130">A tanfolyamok összetettebb típusának kiválasztása</span><span class="sxs-lookup"><span data-stu-id="45a2c-130">Select this type for the more complex courses.</span></span> <span data-ttu-id="45a2c-131">A tanfolyam napirendjét osztása például szekciókat és munkameneteket.</span><span class="sxs-lookup"><span data-stu-id="45a2c-131">For example, you can divide the agenda for the course into tracks and sessions.</span></span>
<ul>
<li><span data-ttu-id="45a2c-132"><strong>Követés</strong>– A szekciók a tanfolyamhoz meghatározott tárgyterületek.</span><span class="sxs-lookup"><span data-stu-id="45a2c-132"><strong>Track</strong> – Tracks are specific subject areas for a course.</span></span></li>
<li><span data-ttu-id="45a2c-133"><strong>Munakmenetek</strong> – A munkamenetek felosztják a szekciókat és segítenek a foglalkozhatnak az egyes szekciókhoz tartozó műveletek és technikák azonosításában.</span><span class="sxs-lookup"><span data-stu-id="45a2c-133"><strong>Sessions</strong> – Sessions divide up tracks and help identify specific processes or techniques that are relevant to the track.</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="course-tasks"></a><span data-ttu-id="45a2c-134">Tanfolyami tevékenységek</span><span class="sxs-lookup"><span data-stu-id="45a2c-134">Course tasks</span></span>
<span data-ttu-id="45a2c-135">Például a következő műveleteket végezheti:</span><span class="sxs-lookup"><span data-stu-id="45a2c-135">For each course, you can complete the following tasks.</span></span>
- <span data-ttu-id="45a2c-136">Résztvevők regisztrálása</span><span class="sxs-lookup"><span data-stu-id="45a2c-136">Register participants</span></span>
- <span data-ttu-id="45a2c-137">A regisztráció határidejének beállítása</span><span class="sxs-lookup"><span data-stu-id="45a2c-137">Specify a registration deadline</span></span>
- <span data-ttu-id="45a2c-138">A résztvevők minimális és maximális számának beállítása</span><span class="sxs-lookup"><span data-stu-id="45a2c-138">Define the minimum and maximum number of participants</span></span>
- <span data-ttu-id="45a2c-139">A tanfolyam helyszínének és tantermének kiválasztása</span><span class="sxs-lookup"><span data-stu-id="45a2c-139">Assign a course location and classroom</span></span>
- <span data-ttu-id="45a2c-140">Ajánlott szállodák a tanfolyam résztvevőinek</span><span class="sxs-lookup"><span data-stu-id="45a2c-140">Recommend hotels to course participants</span></span>
- <span data-ttu-id="45a2c-141">A tanfolyam leírásának létrehozása, amelyet közzé lehet tenni az Alkalmazott önkiszolgáló rendszerben</span><span class="sxs-lookup"><span data-stu-id="45a2c-141">Create a course description, which you can then advertise on Employee self service</span></span>

  ><span data-ttu-id="45a2c-142">**Megjegyzés** Csak akkor törölhet egy tanfolyamot, ha nincs hozzá regisztráció.</span><span class="sxs-lookup"><span data-stu-id="45a2c-142">**Note** You can delete a course only if no one has registered for it.</span></span> 

## <a name="course-statuses"></a><span data-ttu-id="45a2c-143">Tanfolyam állapota</span><span class="sxs-lookup"><span data-stu-id="45a2c-143">Course statuses</span></span>
<span data-ttu-id="45a2c-144">Az alábbi táblázat felsorolja a tanfolyam lehetséges állapotok és a műveleteket hajthatja végre, ha a tanfolyamhoz meghatározott állapota.</span><span class="sxs-lookup"><span data-stu-id="45a2c-144">The following table lists the possible course statuses and the actions that you can complete when the course has a specific status.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="45a2c-145">Állapot</span><span class="sxs-lookup"><span data-stu-id="45a2c-145">Status</span></span></th>
<th><span data-ttu-id="45a2c-146">Műveletek</span><span class="sxs-lookup"><span data-stu-id="45a2c-146">Actions</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="45a2c-147"><strong>Létrehozva</strong></span><span class="sxs-lookup"><span data-stu-id="45a2c-147"><strong>Created</strong></span></span></td>
<td><ul>
<li><span data-ttu-id="45a2c-148">Tanfolyami adatok megadása és szerkesztése.</span><span class="sxs-lookup"><span data-stu-id="45a2c-148">Enter and modify course information.</span></span></li>
<li><span data-ttu-id="45a2c-149">Módosítsa a tanfolyam állapotát <strong>Nyitottra</strong> így a munkavállalók regisztrálhatnak a tanfolyamra.</span><span class="sxs-lookup"><span data-stu-id="45a2c-149">Change the course status to <strong>Open</strong> so that workers can register for the course.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="45a2c-150"><strong>Megnyitás</strong></span><span class="sxs-lookup"><span data-stu-id="45a2c-150"><strong>Open</strong></span></span></td>
<td><ul>
<li><span data-ttu-id="45a2c-151">Résztvevő regisztrálása a tanfolyamra</span><span class="sxs-lookup"><span data-stu-id="45a2c-151">Register participants for the course.</span></span></li>
<li><span data-ttu-id="45a2c-152">A tanfolyam résztvevőinek eltávolítása.</span><span class="sxs-lookup"><span data-stu-id="45a2c-152">Remove participants from the course.</span></span></li>
<li><span data-ttu-id="45a2c-153">Résztvevő regisztrálása a tanfolyamra</span><span class="sxs-lookup"><span data-stu-id="45a2c-153">Confirm participants for the course.</span></span></li>
<li><span data-ttu-id="45a2c-154">A tanfolyam<strong> Zárt</strong> vagy <strong>Törölt</strong>állapotra történő változtatása.</span><span class="sxs-lookup"><span data-stu-id="45a2c-154">Change the course status to <strong>Closed</strong> or <strong>Canceled</strong>.</span></span></li>
<li><span data-ttu-id="45a2c-155">Kérdőívek tervezése <strong>Visszaigazolt</strong>állapotú résztvevők számára.</span><span class="sxs-lookup"><span data-stu-id="45a2c-155">Plan questionnaires for participants whose status is <strong>Confirmed</strong>.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="45a2c-156"><strong>Lezárva</strong></span><span class="sxs-lookup"><span data-stu-id="45a2c-156"><strong>Closed</strong></span></span></td>
<td><span data-ttu-id="45a2c-157">A tanfolyam anyaga:</span><span class="sxs-lookup"><span data-stu-id="45a2c-157">You can reopen the course.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="45a2c-158"><strong>Érvénytelenítve</strong></span><span class="sxs-lookup"><span data-stu-id="45a2c-158"><strong>Canceled</strong></span></span></td>
<td><span data-ttu-id="45a2c-159">A tanfolyam anyaga:</span><span class="sxs-lookup"><span data-stu-id="45a2c-159">You can reopen the course.</span></span></td>
</tr>
</tbody>
</table>

## <a name="course-participants"></a><span data-ttu-id="45a2c-160">Tanfolyam résztvevői</span><span class="sxs-lookup"><span data-stu-id="45a2c-160">Course participants</span></span>
<span data-ttu-id="45a2c-161">A tanfolyam résztvevői olyan munkavállalók, akik részt vesznek egy tanfolyamon vagy eseményen.</span><span class="sxs-lookup"><span data-stu-id="45a2c-161">Course participants are workers who participate in a training course or event.</span></span> <span data-ttu-id="45a2c-162">Csak nyitott tanfolyamok résztvevőinek is regisztrálható.</span><span class="sxs-lookup"><span data-stu-id="45a2c-162">You can only register participants for open courses.</span></span> <span data-ttu-id="45a2c-163">A tanfolyamra regisztrálható résztvevők minimális és maximális számát az **Általános** gyorslapon a **Tanfolyamok** lapján határozhatja meg.</span><span class="sxs-lookup"><span data-stu-id="45a2c-163">The minimum and maximum number of participants that you can register for a course is defined on the **General** FastTab on the **Courses** page.</span></span>

<a name="workflow"></a><span data-ttu-id="45a2c-164">Munkafolyamat</span><span class="sxs-lookup"><span data-stu-id="45a2c-164">Workflow</span></span>
--------

<span data-ttu-id="45a2c-165">Azok az alkalmazottak regisztrációja, akik a tanfolyamra az **Alkalmazotti önkiszolgáló rendszer** oldalán keresztül regisztrálnak, jóváhagyási munkafolyamaton mehet keresztül.</span><span class="sxs-lookup"><span data-stu-id="45a2c-165">Employees who register for a course through the **Employee self service** page can have their registration routed through workflow for approval.</span></span> <span data-ttu-id="45a2c-166">Munkafolyamatot tanfolyamhoz a **Tanfolyamok** oldal **Általános** gyorslapján lehet hozzárendelni.</span><span class="sxs-lookup"><span data-stu-id="45a2c-166">You can assign a workflow to a course on the **General** FastTab on the **Courses** page.</span></span>





