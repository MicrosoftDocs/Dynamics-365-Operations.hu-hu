---
title: Új vagy módosult elemek a Dynamics 365 Talent szolgáltatásban (2020. január 21.)
description: Ez a cikk a Microsoft Dynamics 365 Talent új vagy módosított funkcióit írja le.
author: Darinkramer
manager: AnnBe
ms.date: 01/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2020-01-21
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 6e18e8108a7382bfa052986bab5a8552e38100c6
ms.sourcegitcommit: a2f9dce06322dada6b5f1c82051ef2359f8c0f12
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/24/2020
ms.locfileid: "3081841"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-january-21-2020"></a><span data-ttu-id="6dd19-103">Új vagy módosult elemek a Dynamics 365 Talent szolgáltatásban (2020. január 21.)</span><span class="sxs-lookup"><span data-stu-id="6dd19-103">What's new or changed in Dynamics 365 Talent (January 21, 2020)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="6dd19-104">Ez a cikk a Dynamics 365 Talent szolgáltatásban található új vagy módosított funkciókat írja le.</span><span class="sxs-lookup"><span data-stu-id="6dd19-104">This article describes features that are either new or changed in Dynamics 365 Talent.</span></span>

## <a name="changes-in-attract"></a><span data-ttu-id="6dd19-105">Változások az Attract-ben</span><span class="sxs-lookup"><span data-stu-id="6dd19-105">Changes in Attract</span></span>

<span data-ttu-id="6dd19-106">A kiadás a Dynamics 365 Talent: Attract apró hibáinak javításait is tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="6dd19-106">This release includes minor bug fixes for Dynamics 365 Talent: Attract.</span></span> <span data-ttu-id="6dd19-107">Olyan funkciókat adtunk hozzá, amelyek támogatják a legutóbbi bejelentést, [és a Dynamics 365 Human Resources-szal sikeresebb munkaerőt építenek ki](https://cloudblogs.microsoft.com/dynamics365/bdm/2019/12/06/building-a-more-successful-workforce-with-dynamics-365-human-resources/).</span><span class="sxs-lookup"><span data-stu-id="6dd19-107">We've added functionality to Attract to support our recent announcement, [Building a more successful workforce with Dynamics 365 Human Resources](https://cloudblogs.microsoft.com/dynamics365/bdm/2019/12/06/building-a-more-successful-workforce-with-dynamics-365-human-resources/).</span></span>

### <a name="download-environment-data"></a><span data-ttu-id="6dd19-108">Letöltött környezeti adatok</span><span class="sxs-lookup"><span data-stu-id="6dd19-108">Download environment data</span></span>

<span data-ttu-id="6dd19-109">A rendszergazdák le tudják tölteni a környezetük adatait.</span><span class="sxs-lookup"><span data-stu-id="6dd19-109">Administrators can download their environment’s data.</span></span> <span data-ttu-id="6dd19-110">A program az adatokat normál JSON formátumba exportálja egy zip-fájlba az összes feladattal, pályázóval és konfigurációval.</span><span class="sxs-lookup"><span data-stu-id="6dd19-110">The data is exported in standard JSON format with all the jobs, candidates, and configuration exported in a zip file.</span></span> <span data-ttu-id="6dd19-111">A további információkért lásd: [Adatok exportálása az Attract és Onboard-ból](https://docs.microsoft.com/dynamics365/talent/attract-onboard-export-data).</span><span class="sxs-lookup"><span data-stu-id="6dd19-111">For more information, see [Export data from Attract and Onboard](https://docs.microsoft.com/dynamics365/talent/attract-onboard-export-data).</span></span>

### <a name="restricting-access-to-environments-for-non-admin-users"></a><span data-ttu-id="6dd19-112">A környezethez való hozzáférés korlátozása a nem rendszergazdai felhasználók számára</span><span class="sxs-lookup"><span data-stu-id="6dd19-112">Restricting access to environments for non-admin users</span></span>

<span data-ttu-id="6dd19-113">A rendszergazdák mostantól korlátozhatják a környezethez történő hozzáférést a nem rendszergazda felhasználók számára.</span><span class="sxs-lookup"><span data-stu-id="6dd19-113">Administrators can now restrict access to the environment for non-admin users.</span></span> <span data-ttu-id="6dd19-114">Ez a művelet nem vonható vissza.</span><span class="sxs-lookup"><span data-stu-id="6dd19-114">This action can't be undone.</span></span> <span data-ttu-id="6dd19-115">További információ: [Attract hozzáférésének korlátozása](https://docs.microsoft.com/dynamics365/talent/attract-onboard-export-data#restrict-access-to-attract).</span><span class="sxs-lookup"><span data-stu-id="6dd19-115">For more information, see [Restrict access to Attract](https://docs.microsoft.com/dynamics365/talent/attract-onboard-export-data#restrict-access-to-attract).</span></span>

## <a name="changes-in-onboard"></a><span data-ttu-id="6dd19-116">Változások az Onboard alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="6dd19-116">Changes in Onboard</span></span>

<span data-ttu-id="6dd19-117">A kiadás a Dynamics 365 Talent: Onboard apró hibáinak javításait is tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="6dd19-117">This release includes minor bug fixes for Dynamics 365 Talent: Onboard.</span></span>

### <a name="exporting-onboarding-guides"></a><span data-ttu-id="6dd19-118">Felvételi útmutatók exportálása</span><span class="sxs-lookup"><span data-stu-id="6dd19-118">Exporting onboarding guides</span></span>

<span data-ttu-id="6dd19-119">A felhasználók most exportálhatják a saját felvételi útmutatóikat és felvételi sablonjaikat Word dokumentumformátumba.</span><span class="sxs-lookup"><span data-stu-id="6dd19-119">Users can now export all of their onboarding guides and onboarding templates in Word document format.</span></span> <span data-ttu-id="6dd19-120">A további információkért lásd: [Adatok exportálása az Attract és Onboard-ból](https://docs.microsoft.com/dynamics365/talent/attract-onboard-export-data).</span><span class="sxs-lookup"><span data-stu-id="6dd19-120">For more information, see [Export data from Attract and Onboard](https://docs.microsoft.com/dynamics365/talent/attract-onboard-export-data).</span></span>

## <a name="changes-in-core-hr"></a><span data-ttu-id="6dd19-121">A Core HR módosításai</span><span class="sxs-lookup"><span data-stu-id="6dd19-121">Changes in Core HR</span></span>

<span data-ttu-id="6dd19-122">A szakaszban ismertetett módosítások a 8.1.2726-ös buildre vonatkoznak.</span><span class="sxs-lookup"><span data-stu-id="6dd19-122">Changes described in this section apply to build number 8.1.2726.</span></span> <span data-ttu-id="6dd19-123">A néhány fejlécben látható, zárójelben lévő számok az Microsoft Dynamics Lifecycle Services (LCS) támogatási számaira vonatkoznak.</span><span class="sxs-lookup"><span data-stu-id="6dd19-123">The numbers in parentheses in some headings refer to support numbers in Microsoft Dynamics Lifecycle Services (LCS).</span></span>

### <a name="most-recent-annual-compensation-field-in-verify-employment-form-isnt-consistent-392092"></a><span data-ttu-id="6dd19-124">A legutóbbi éves kompenzációs mező a Foglalkoztatás ellenőrzése képernyőn nem konzisztens (392092)</span><span class="sxs-lookup"><span data-stu-id="6dd19-124">Most recent annual compensation field in Verify employment form isn't consistent (392092)</span></span>

<span data-ttu-id="6dd19-125">Ez a kiadás egy olyan módosítást tartalmaz, amely a vállalatválasztó alapján folyamatosan megjeleníti a legfrissebb pénznemet a **Foglalkoztatás ellenőrzése** képernyőn.</span><span class="sxs-lookup"><span data-stu-id="6dd19-125">This release includes a change that will consistently display the latest currency based on the company selector on the **Verify employment** form.</span></span>

### <a name="known-as-field-added-to-the-feedback-recipient-lookup-407789"></a><span data-ttu-id="6dd19-126">A visszajelzés címzettje számára történő kereséshez (407789) hozzáadott mező neve</span><span class="sxs-lookup"><span data-stu-id="6dd19-126">Known as field added to the Feedback recipient lookup (407789)</span></span>

<span data-ttu-id="6dd19-127">A teljesítmény-visszajelzések esetében a dolgozói keresés nem szolgáltatott elegendő információt annak megállapításához, hogy a visszajelzések a megfelelő személyhez mennek-e.</span><span class="sxs-lookup"><span data-stu-id="6dd19-127">When providing performance feedback, the lookup for workers didn't provide enough information to determine if feedback is going to the correct person.</span></span> <span data-ttu-id="6dd19-128">A **Más néven** oszlop hozzáadása segítségével lehet meghatározni az alkalmazott egyedi nevét.</span><span class="sxs-lookup"><span data-stu-id="6dd19-128">We added a **Known as** column to help identify the unique name of the employee.</span></span>
 
### <a name="hcmworkerpayrollinfo-record-is-created-without-an-association-to-a-worker-394526"></a><span data-ttu-id="6dd19-129">A HcmWorkerPayrollInfo rekord egy dolgozóhoz való társítás nélkül jön létre (394526)</span><span class="sxs-lookup"><span data-stu-id="6dd19-129">HcmWorkerPayrollInfo record is created without an association to a worker (394526)</span></span>

<span data-ttu-id="6dd19-130">Ez a kiadás olyan módosítást tartalmaz, amely nem ír HCMWorkerPayrollInfo-rekordokat az alkalmazottra való hivatkozás nélkül.</span><span class="sxs-lookup"><span data-stu-id="6dd19-130">This release includes a change to not write HCMWorkerPayrollInfo records without reference to an employee.</span></span>

### <a name="able-to-edit-department-when-navigating-from-position-hierarchy-341001"></a><span data-ttu-id="6dd19-131">Képes szerkeszteni a részleget a beosztás hierarchiájából történő navigáláskor (341001)</span><span class="sxs-lookup"><span data-stu-id="6dd19-131">Able to edit department when navigating from position hierarchy (341001)</span></span>

<span data-ttu-id="6dd19-132">Amikor a biztonság beállításával meg van tagadva a szerkesztési osztályokhoz való hozzáférés, a szerkesztés le van tiltva, amikor a **Részlegek** űrlapra navigál minden forgatókönyvben.</span><span class="sxs-lookup"><span data-stu-id="6dd19-132">When security has been set up to deny access to editing departments, editing is disabled when navigating to the **Departments** form in all scenarios.</span></span>

## <a name="coming-soon"></a><span data-ttu-id="6dd19-133">Hamarosan</span><span class="sxs-lookup"><span data-stu-id="6dd19-133">Coming soon</span></span>

<span data-ttu-id="6dd19-134">Az új Common Data Service megoldás hamarosan a következő változtatásokkal érhető el:</span><span class="sxs-lookup"><span data-stu-id="6dd19-134">A new Common Data Service solution will be available soon with the following changes:</span></span>

| <span data-ttu-id="6dd19-135">Leírás</span><span class="sxs-lookup"><span data-stu-id="6dd19-135">Description</span></span> | <span data-ttu-id="6dd19-136">Visszajáró</span><span class="sxs-lookup"><span data-stu-id="6dd19-136">Change</span></span> |
| --- | --- |
| <span data-ttu-id="6dd19-137">**Feladat/pozíció** entitás módosításai</span><span class="sxs-lookup"><span data-stu-id="6dd19-137">**Job/Position** entity changes</span></span> | <ul><li><span data-ttu-id="6dd19-138">**Kompenzációs régió** hozzáadása</span><span class="sxs-lookup"><span data-stu-id="6dd19-138">**Compensation region** added</span></span></li><li><span data-ttu-id="6dd19-139">**Pénzügyi dimenziók** hozzáadása</span><span class="sxs-lookup"><span data-stu-id="6dd19-139">**Financial dimensions** added</span></span></li></ul> |
| <span data-ttu-id="6dd19-140">**Dolgozó** entitás módosításai</span><span class="sxs-lookup"><span data-stu-id="6dd19-140">**Worker** entity changes</span></span> | <ul><li><span data-ttu-id="6dd19-141">**Névsorrend** hozzáadása</span><span class="sxs-lookup"><span data-stu-id="6dd19-141">**Name sequence** added</span></span></li><li><span data-ttu-id="6dd19-142">**Otthonról dolgozik** hozzáadása</span><span class="sxs-lookup"><span data-stu-id="6dd19-142">**Works from home** added</span></span></li><li><span data-ttu-id="6dd19-143">**Nyelv** hozzáadása</span><span class="sxs-lookup"><span data-stu-id="6dd19-143">**Language** added</span></span></li><li><span data-ttu-id="6dd19-144">**Szolgálati idő dátuma** hozzáadása</span><span class="sxs-lookup"><span data-stu-id="6dd19-144">**Seniority date** added</span></span></li><li><span data-ttu-id="6dd19-145">**Évforduló dátuma** hozzáadása</span><span class="sxs-lookup"><span data-stu-id="6dd19-145">**Anniversary date** added</span></span></li><li><span data-ttu-id="6dd19-146">**Eredeti felvételi dátum** hozzáadása</span><span class="sxs-lookup"><span data-stu-id="6dd19-146">**Original hire date** added</span></span></li></ul> |
| <span data-ttu-id="6dd19-147">**Foglalkoztatás** entitás módosításai</span><span class="sxs-lookup"><span data-stu-id="6dd19-147">**Employment** entity changes</span></span> | <ul><li><span data-ttu-id="6dd19-148">**Pénzügyi dimenziók** hozzáadása</span><span class="sxs-lookup"><span data-stu-id="6dd19-148">**Financial dimensions** added</span></span></li><li><span data-ttu-id="6dd19-149">**Felmondás oka** hozzáadása</span><span class="sxs-lookup"><span data-stu-id="6dd19-149">**Termination reason** added</span></span></li><li><span data-ttu-id="6dd19-150">**Megszűnés dátuma** az **Áttérési dátumtól** átnevezve</span><span class="sxs-lookup"><span data-stu-id="6dd19-150">**Termination date** renamed from **Transition date**</span></span></li><li><span data-ttu-id="6dd19-151">**Próbaidős dátum** hozzáadása</span><span class="sxs-lookup"><span data-stu-id="6dd19-151">**Probation date** added</span></span></li></ul> |
| <span data-ttu-id="6dd19-152">**Dolgozó címe** entitás módosításai</span><span class="sxs-lookup"><span data-stu-id="6dd19-152">**Worker address** entity changes</span></span> | <ul><li><span data-ttu-id="6dd19-153">**Utca és házszám** hozzáadása</span><span class="sxs-lookup"><span data-stu-id="6dd19-153">**Street address** added</span></span></li><li><span data-ttu-id="6dd19-154">**1. címsor**, **2. címsor** és **3. címsor** megjelölve megszűnésre</span><span class="sxs-lookup"><span data-stu-id="6dd19-154">**Address line 1**, **Address line 2**, and **Address line 3** marked for deprecation</span></span></li></ul> |
| <span data-ttu-id="6dd19-155">Új változó kompenzációs beállítási entitások</span><span class="sxs-lookup"><span data-stu-id="6dd19-155">New variable compensation setup entities</span></span> | <ul><li><span data-ttu-id="6dd19-156">**Változó kompenzációs konstrukció típusa**</span><span class="sxs-lookup"><span data-stu-id="6dd19-156">**Compensation variable plan type**</span></span></li><li><span data-ttu-id="6dd19-157">**Változó kompenzációs konstrukció**</span><span class="sxs-lookup"><span data-stu-id="6dd19-157">**Compensation variable plan**</span></span></li><li><span data-ttu-id="6dd19-158">**Kilépési szabályok**</span><span class="sxs-lookup"><span data-stu-id="6dd19-158">**Vesting rules**</span></span></li><li><span data-ttu-id="6dd19-159">**Változó kompenzációs konstrukció szintje**</span><span class="sxs-lookup"><span data-stu-id="6dd19-159">**Compensation variable plan level**</span></span></li></ul> |
| <span data-ttu-id="6dd19-160">Új **Dolgozói naptár – foglalkoztatás** entitás</span><span class="sxs-lookup"><span data-stu-id="6dd19-160">New **Worker calendar employment** entity</span></span> | <ul><li><span data-ttu-id="6dd19-161">**Munkanaptár-entitás** hozzáadva</span><span class="sxs-lookup"><span data-stu-id="6dd19-161">**Work calendar entity** added</span></span></li></ul> |
