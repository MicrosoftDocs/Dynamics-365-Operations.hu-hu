---
title: Új vagy módosult elemek a Dynamics 365 for Talent Core HR szolgáltatásban (2018. szeptember 10.)
description: Ez a témakör a Microsoft Dynamics 365 for Talent Core HR új vagy módosított szolgáltatásait írja le.
author: Darinkramer
manager: AnnBe
ms.date: 09/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-09-06
ms.dyn365.ops.version: Talent September 10, 2018 update
ms.openlocfilehash: b41ce93c8ae93054d2b0d71340b99e0910d4510f
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "304736"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-core-hr-september-10-2018"></a><span data-ttu-id="a38b1-103">Új vagy módosult elemek a Dynamics 365 for Talent Core HR szolgáltatásban (2018. szeptember 10.)</span><span class="sxs-lookup"><span data-stu-id="a38b1-103">What's new or changed in Dynamics 365 for Talent Core HR (September 10, 2018)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="a38b1-104">**Build 8.1.138.0**</span><span class="sxs-lookup"><span data-stu-id="a38b1-104">**Build 8.1.138.0**</span></span>

<span data-ttu-id="a38b1-105">Ez a témakör a Microsoft Dynamics 365 for Talent Core HR új vagy módosított szolgáltatásait írja le.</span><span class="sxs-lookup"><span data-stu-id="a38b1-105">This topic describes features that are either new or changed in Microsoft Dynamics 365 for Talent Core HR.</span></span>

## <a name="allow-specific-time-of-day-on-time-off-requests-half-days"></a><span data-ttu-id="a38b1-106">Pontos idő megadása a szabadságkérelmekben (fél nap)</span><span class="sxs-lookup"><span data-stu-id="a38b1-106">Allow specific time of day on time-off requests (half days)</span></span>

<span data-ttu-id="a38b1-107">Ha a szabadság és a távollét beállítása úgy történik, hogy a szabadság megadása napokban történjen, akkor lehetőség van félnapos meghatározásra is.</span><span class="sxs-lookup"><span data-stu-id="a38b1-107">If leave and absence is set up so that time off is submitted in days, you can now also enable a half-day definition.</span></span> <span data-ttu-id="a38b1-108">Ezután, amikor a felhasználók szabadságkérelmet nyújtanak be, megadhatják, hogy a nap első felét vagy második felét kérik-e.</span><span class="sxs-lookup"><span data-stu-id="a38b1-108">Then, when users submit time-off requests, they can specify whether they are requesting the first half or the second half of the day off.</span></span>

<span data-ttu-id="a38b1-109">Ez a beállítás alapértelmezés szerint ki van kapcsolva.</span><span class="sxs-lookup"><span data-stu-id="a38b1-109">By default, this option is turned off.</span></span> <span data-ttu-id="a38b1-110">Azoknál az alkalmazottaknál, akik a nap első vagy második felét szeretné kivenni, be kell kapcsolnia ezt a lehetőséget az Emberi erőforrások paramétereinek **Szabadság és eltávolítás** területén.</span><span class="sxs-lookup"><span data-stu-id="a38b1-110">For employees to request the first half or second half of the day off, you must turn on this option in the **Leave and absence** area of Human resources parameters.</span></span>

<span data-ttu-id="a38b1-111">A szolgáltatás biztonsági jogosultsága a Humánerőforrás-paraméterek karbantartása.</span><span class="sxs-lookup"><span data-stu-id="a38b1-111">The security privilege for this feature is Maintain Human Resources Parameters.</span></span>

## <a name="validation-of-leave-and-absence-entries"></a><span data-ttu-id="a38b1-112">A szabadság- és távollétbejegyzések ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="a38b1-112">Validation of leave and absence entries</span></span>

<span data-ttu-id="a38b1-113">Attól függően, hogy a távollét beállítása milyen módon történik, az alkalmazottak figyelmeztető üzenetet kapnak, amennyiben a munkanapnál hosszabb időre vonatkozó szabadságkérelmet nyújtanak be.</span><span class="sxs-lookup"><span data-stu-id="a38b1-113">Depending on how leave is configured, employees who try to submit a time-off request that is longer than their work day receive a warning message.</span></span> <span data-ttu-id="a38b1-114">Más szóval figyelmeztetést kapnak, ha egy adott napon többet szeretnének kivenni egy teljes napnál.</span><span class="sxs-lookup"><span data-stu-id="a38b1-114">In other words, they are warned if they try to take more than a full day off on any given date.</span></span>

<span data-ttu-id="a38b1-115">Ez az ellenőrzés mindig be van kapcsolva.</span><span class="sxs-lookup"><span data-stu-id="a38b1-115">This validation is always turned on.</span></span> <span data-ttu-id="a38b1-116">Minden olyan alkalommal, amikor a munkavállalók meghaladják a meghatározott napi küszöbértéket, figyelmeztetést kapnak a szabadságkérelmükben.</span><span class="sxs-lookup"><span data-stu-id="a38b1-116">Any time that employees exceed the day threshold that is defined, they receive a warning in their time-off request.</span></span>

## <a name="additional-fields-for-conditional-statements-in-workflows"></a><span data-ttu-id="a38b1-117">További mezők a feltételes működési utasításokhoz a munkafolyamatokban</span><span class="sxs-lookup"><span data-stu-id="a38b1-117">Additional fields for conditional statements in workflows</span></span>

<span data-ttu-id="a38b1-118">A feltételes működési utasításokhoz és helyőrzőkhöz további mezőket adtunk a Core HR számos munkafolyamatánál.</span><span class="sxs-lookup"><span data-stu-id="a38b1-118">Additional fields have been added to conditional statements and placeholders for several workflows in Core HR.</span></span>

<span data-ttu-id="a38b1-119">A következő mezőket adtuk hozzá a kompenzáció, elbocsátás és átmozgatás munkafolyamataihoz:</span><span class="sxs-lookup"><span data-stu-id="a38b1-119">The following fields have been added to the compensation, termination, and transfer workflows:</span></span>

- <span data-ttu-id="a38b1-120">EmploymentType</span><span class="sxs-lookup"><span data-stu-id="a38b1-120">EmploymentType</span></span>
- <span data-ttu-id="a38b1-121">LegalEntity</span><span class="sxs-lookup"><span data-stu-id="a38b1-121">LegalEntity</span></span>
- <span data-ttu-id="a38b1-122">AdjustedWorkerStartDate</span><span class="sxs-lookup"><span data-stu-id="a38b1-122">AdjustedWorkerStartDate</span></span>
- <span data-ttu-id="a38b1-123">EmployerNoticeAmount</span><span class="sxs-lookup"><span data-stu-id="a38b1-123">EmployerNoticeAmount</span></span>
- <span data-ttu-id="a38b1-124">EmployerUnitOfNotice</span><span class="sxs-lookup"><span data-stu-id="a38b1-124">EmployerUnitOfNotice</span></span>
- <span data-ttu-id="a38b1-125">TransitionDate</span><span class="sxs-lookup"><span data-stu-id="a38b1-125">TransitionDate</span></span>
- <span data-ttu-id="a38b1-126">WorkerNoticeAmount</span><span class="sxs-lookup"><span data-stu-id="a38b1-126">WorkerNoticeAmount</span></span>
- <span data-ttu-id="a38b1-127">WorkerStartDate</span><span class="sxs-lookup"><span data-stu-id="a38b1-127">WorkerStartDate</span></span>
- <span data-ttu-id="a38b1-128">WorkerUnitOfNotice</span><span class="sxs-lookup"><span data-stu-id="a38b1-128">WorkerUnitOfNotice</span></span>
- <span data-ttu-id="a38b1-129">ProbationEndDate</span><span class="sxs-lookup"><span data-stu-id="a38b1-129">ProbationEndDate</span></span>
- <span data-ttu-id="a38b1-130">Pozíció</span><span class="sxs-lookup"><span data-stu-id="a38b1-130">Position</span></span>
- <span data-ttu-id="a38b1-131">Unió</span><span class="sxs-lookup"><span data-stu-id="a38b1-131">Union</span></span>
- <span data-ttu-id="a38b1-132">Osztály</span><span class="sxs-lookup"><span data-stu-id="a38b1-132">Department</span></span>
- <span data-ttu-id="a38b1-133">PositionType</span><span class="sxs-lookup"><span data-stu-id="a38b1-133">PositionType</span></span>
- <span data-ttu-id="a38b1-134">CompLocation</span><span class="sxs-lookup"><span data-stu-id="a38b1-134">CompLocation</span></span>
- <span data-ttu-id="a38b1-135">Beosztás</span><span class="sxs-lookup"><span data-stu-id="a38b1-135">Title</span></span>
- <span data-ttu-id="a38b1-136">Beosztás</span><span class="sxs-lookup"><span data-stu-id="a38b1-136">Job</span></span>
- <span data-ttu-id="a38b1-137">JobType</span><span class="sxs-lookup"><span data-stu-id="a38b1-137">JobType</span></span>
- <span data-ttu-id="a38b1-138">JobFamily</span><span class="sxs-lookup"><span data-stu-id="a38b1-138">JobFamily</span></span>
- <span data-ttu-id="a38b1-139">JobFunction</span><span class="sxs-lookup"><span data-stu-id="a38b1-139">JobFunction</span></span>

<span data-ttu-id="a38b1-140">A következő mezőket adtuk hozzá a beosztás munkafolyamatához:</span><span class="sxs-lookup"><span data-stu-id="a38b1-140">The following fields have been added to the position workflow:</span></span>

- <span data-ttu-id="a38b1-141">Pozíció</span><span class="sxs-lookup"><span data-stu-id="a38b1-141">Position</span></span>
- <span data-ttu-id="a38b1-142">Unió</span><span class="sxs-lookup"><span data-stu-id="a38b1-142">Union</span></span>
- <span data-ttu-id="a38b1-143">Osztály</span><span class="sxs-lookup"><span data-stu-id="a38b1-143">Department</span></span>
- <span data-ttu-id="a38b1-144">PositionType</span><span class="sxs-lookup"><span data-stu-id="a38b1-144">PositionType</span></span>
- <span data-ttu-id="a38b1-145">CompLocation</span><span class="sxs-lookup"><span data-stu-id="a38b1-145">CompLocation</span></span>
- <span data-ttu-id="a38b1-146">Beosztás</span><span class="sxs-lookup"><span data-stu-id="a38b1-146">Title</span></span>
- <span data-ttu-id="a38b1-147">Beosztás</span><span class="sxs-lookup"><span data-stu-id="a38b1-147">Job</span></span>
- <span data-ttu-id="a38b1-148">JobType</span><span class="sxs-lookup"><span data-stu-id="a38b1-148">JobType</span></span>
- <span data-ttu-id="a38b1-149">JobFamily</span><span class="sxs-lookup"><span data-stu-id="a38b1-149">JobFamily</span></span>
- <span data-ttu-id="a38b1-150">JobFunction</span><span class="sxs-lookup"><span data-stu-id="a38b1-150">JobFunction</span></span>

<span data-ttu-id="a38b1-151">A feltételes működési utasítások és helyőrzők minden olyan felhasználó számára elérhetők, akik hozzáférnek a korábban említett munkafolyamatok konfigurálásához.</span><span class="sxs-lookup"><span data-stu-id="a38b1-151">Fields in conditional statements and placeholders are available to all users who have access to configure the previously mentioned workflows.</span></span>

## <a name="navigation-to-attract-from-personnel-management"></a><span data-ttu-id="a38b1-152">Navigáció az Attract szolgáltatásba a személyzetkezelésből</span><span class="sxs-lookup"><span data-stu-id="a38b1-152">Navigation to Attract from personnel management</span></span>

<span data-ttu-id="a38b1-153">Ha nincs beállítva az Attract a személyzetkezelésnél, a **Foglalkoztatható jelöltek** szakasza az Attract kezdő lépéseihez irányítja a felhasználókat ahelyett, hogy a „Nem találtunk megjelenítendő elemeket” üzenetet adná.</span><span class="sxs-lookup"><span data-stu-id="a38b1-153">In personnel management, if Attract hasn't been set up, the **Candidates to hire** section directs users to get started with Attract instead of showing the message, "We didn't find anything to show here."</span></span>

## <a name="other-changes"></a><span data-ttu-id="a38b1-154">Egyéb változások</span><span class="sxs-lookup"><span data-stu-id="a38b1-154">Other changes</span></span>

<span data-ttu-id="a38b1-155">Ebben a verzióban számos további hibajavítás is található:</span><span class="sxs-lookup"><span data-stu-id="a38b1-155">This release includes several additional bug fixes:</span></span>

- <span data-ttu-id="a38b1-156">Alvállalkozó megbízásakor a **Kompenzálás** lapnak nem szabad elérhetőnek lennie a kérelem/művelet lapján.</span><span class="sxs-lookup"><span data-stu-id="a38b1-156">When a contractor is hired, the **Compensation** tab should not be available on the request/action page.</span></span>
- <span data-ttu-id="a38b1-157">A kérelem megszüntetési folyamata alatt nem folytathatja a műveletet addig, amíg az összes kötelező mező adatot tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="a38b1-157">During the request termination process, you can't continue until all required fields contain data.</span></span>
- <span data-ttu-id="a38b1-158">Kijavítottuk a rendelés- és dátummegjelenítési problémákat a Személyzetkezelés analitikájában.</span><span class="sxs-lookup"><span data-stu-id="a38b1-158">Sort order and date display issues on the Personnel management analytics have been addressed.</span></span>
