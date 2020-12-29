---
title: Új vagy módosult elemek a Dynamics 365 Human Resources szolgáltatásban (2020. május 14.)
description: Ez a témakör a Microsoft Dynamics 365 Human Resources új vagy módosított szolgáltatásait írja le a 2020. május 14-i kiadásban.
author: Darinkramer
manager: AnnBe
ms.date: 05/14/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2020-05-14
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 76ca497cc7fabf737c8a0ee71363f22fd4201ea8
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/17/2020
ms.locfileid: "4528497"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-may-14-2020"></a><span data-ttu-id="c8d13-103">Új vagy módosult elemek a Dynamics 365 Human Resources szolgáltatásban (2020. május 14.)</span><span class="sxs-lookup"><span data-stu-id="c8d13-103">What's new or changed in Dynamics 365 Human Resources (May 14, 2020)</span></span>

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="c8d13-104">Ez a témakör a Dynamics 365 Human Resources új vagy módosított szolgáltatásait írja le.</span><span class="sxs-lookup"><span data-stu-id="c8d13-104">This topic describes features that are either new or changed in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="c8d13-105">A változtatások a 8.1.3244-es buildszámra vonatkoznak.</span><span class="sxs-lookup"><span data-stu-id="c8d13-105">Changes apply to build number 8.1.3244.</span></span> <span data-ttu-id="c8d13-106">A néhány fejlécben látható, zárójelben lévő számok tájékoztatásként a Lifecycle Services (LCS) támogatási számaira vonatkoznak.</span><span class="sxs-lookup"><span data-stu-id="c8d13-106">The numbers in parentheses in some headings refer to Lifecycle Services (LCS) support numbers for reference.</span></span>

## <a name="platform-changes"></a><span data-ttu-id="c8d13-107">Platformok módosításai</span><span class="sxs-lookup"><span data-stu-id="c8d13-107">Platform changes</span></span>

<span data-ttu-id="c8d13-108">Ez a heti kiadás tartalmazza a platform változásait.</span><span class="sxs-lookup"><span data-stu-id="c8d13-108">Platform changes are included in this week's release.</span></span> <span data-ttu-id="c8d13-109">További tájékoztatás: [Platform-frissítések az Finance and Operations alkalmazások 10.0.10 verziójához (2020. május)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-update-34).</span><span class="sxs-lookup"><span data-stu-id="c8d13-109">For more information, see [Platform updates for version 10.0.10 of Finance and Operations apps (May 2020)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-update-34).</span></span> <span data-ttu-id="c8d13-110">Ez a kiadás hibajavításokat és a mentett nézetek módosításait tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="c8d13-110">This release includes bug fixes and changes to saved views.</span></span>
 
## <a name="ensure-common-data-service-picklists-are-consistent-with-leave-enums-436343"></a><span data-ttu-id="c8d13-111">Biztosítja, hogy a Common Data Service választási listák megfelelnek a Szabadság felsorolásainak (436343)</span><span class="sxs-lookup"><span data-stu-id="c8d13-111">Ensure Common Data Service picklists are consistent with Leave enums (436343)</span></span>

<span data-ttu-id="c8d13-112">A Common Data Service választási listák most már megfelelnek a Szabadság felsorolásainak.</span><span class="sxs-lookup"><span data-stu-id="c8d13-112">Common Data Service picklists are now consistent with Leave enums.</span></span>

## <a name="allow-users-to-configure-leave-request-workflow-based-on-the-request-amount-300044"></a><span data-ttu-id="c8d13-113">A felhasználók számára lehetővé teszi a szabadságkérelmi folyamat kérelem mennyisége alapján történő konfigurálását (300044).</span><span class="sxs-lookup"><span data-stu-id="c8d13-113">Allow users to configure leave request workflow based on the request amount (300044)</span></span>

<span data-ttu-id="c8d13-114">A felhasználók konfigurálhatják a szabadságkérelmi folyamatokat a kérelem mennyiségei alapján.</span><span class="sxs-lookup"><span data-stu-id="c8d13-114">Users can configure leave requests workflows based on request amounts.</span></span>
 
## <a name="new-worker-form-exposes-data-through-the-view-menu-when-advanced-security-is-enabled-403185"></a><span data-ttu-id="c8d13-115">Az új dolgozói űrlap elérhetővé teszi az adatokat a Nézet menün keresztül, amikor a speciális biztonság engedélyezve van (403185).</span><span class="sxs-lookup"><span data-stu-id="c8d13-115">New worker form exposes data through the View menu when advanced security is enabled (403185)</span></span>

<span data-ttu-id="c8d13-116">Ez a kiadás javítja azt, hogy hogyan jeleníti meg a dolgozókat a jogi személyek között a speciális hozzáférés engedélyezése esetén, és amikor más vállalatok dolgozói is hozzáférhetők.</span><span class="sxs-lookup"><span data-stu-id="c8d13-116">This release corrects how viewing workers across legal entities functions when advanced access is enabled and workers in other companies are accessible.</span></span>

## <a name="allow-running-leave-accruals-for-a-single-plan-or-a-single-company-318844"></a><span data-ttu-id="c8d13-117">Csak egy terv vagy egy vállalat esetében teszi lehetővé a szabadságkönyvelések futtatását (318844).</span><span class="sxs-lookup"><span data-stu-id="c8d13-117">Allow running leave accruals for a single plan or a single company (318844)</span></span>

<span data-ttu-id="c8d13-118">Ezzel a módosítással egy vállalat vagy egy terv esetében futtathat könyveléseket.</span><span class="sxs-lookup"><span data-stu-id="c8d13-118">With this change, you can run accruals for a company or a plan.</span></span>
 
## <a name="show-the-positions-full-time-equivalent-fte-in-the-enrolled-workers-form-414658"></a><span data-ttu-id="c8d13-119">A beosztás teljes munkaidős egyenértékét (FTE) jeleníti meg a Kedvezményezett dolgozók űrlapon (414658)</span><span class="sxs-lookup"><span data-stu-id="c8d13-119">Show the position's full-time equivalent (FTE) in the Enrolled workers form (414658)</span></span>

<span data-ttu-id="c8d13-120">A dolgozó beosztásának FTE-értéke határozza meg a dolgozói könyvelési rátát, ha a szabadságtípuson az FTE beállítás engedélyezve van.</span><span class="sxs-lookup"><span data-stu-id="c8d13-120">The FTE value from a worker's position determines a worker's accrual rate when the FTE option is enabled on the leave type.</span></span> <span data-ttu-id="c8d13-121">Ez a mező most szerepel a **Kedvezményezett dolgozók** űrlapon és a **Tömeges bejelentkezés** párbeszédpanelen.</span><span class="sxs-lookup"><span data-stu-id="c8d13-121">This field is now included in **Enrolled workers** form and the **Mass enrollment** dialog.</span></span>

## <a name="add-leave-balance-expiration-batch-job-431266"></a><span data-ttu-id="c8d13-122">Szabadságegyenleg lejáratára vonatkozó kötegelt feladat hozzáadása (431266)</span><span class="sxs-lookup"><span data-stu-id="c8d13-122">Add leave balance expiration batch job (431266)</span></span>

<span data-ttu-id="c8d13-123">Egy új, naponta futtatható feladat érhető most már el.</span><span class="sxs-lookup"><span data-stu-id="c8d13-123">A new batch job is now available that runs daily.</span></span> <span data-ttu-id="c8d13-124">A program csökkenti a hátralévő szabadság egyenlegét, ha a lejárati dátumok aktuálissá válnak.</span><span class="sxs-lookup"><span data-stu-id="c8d13-124">It decreases the remaining leave balance when expiration dates become current.</span></span>

## <a name="exporting-personal-contacts-for-an-employee-using-the-worker-personal-contact-person-entity-doesnt-export-personal-contacts-with-the-parent-relationship-type-345893"></a><span data-ttu-id="c8d13-125">Egy alkalmazott személyes kapcsolattartóinak exportálása a Dolgozó személyes kapcsolattartója entitással nem exportálja a Szülő kapcsolattípussal rendelkező személyes kapcsolattartókat (345893).</span><span class="sxs-lookup"><span data-stu-id="c8d13-125">Exporting personal contacts for an employee using the Worker personal contact person entity doesn't export personal contacts with the Parent relationship type (345893)</span></span>

<span data-ttu-id="c8d13-126">A **Dolgozó személyes kapcsolattartója** adatentitás (a **HcmPersonalContactPersonEntity** a DMF-ben és a **PersonalContactPerson** az OData típusban) nem tudta exportálni a **Szülő** kapcsolattípussal rendelkező kapcsolattartókat.</span><span class="sxs-lookup"><span data-stu-id="c8d13-126">The **Worker personal contact person** data entity (**HcmPersonalContactPersonEntity** in DMF and **PersonalContactPerson** in OData) couldn't export personal contacts that have a relationship type of **Parent**.</span></span> <span data-ttu-id="c8d13-127">Ez a hiba a módosítást követően létrejövő személyes kapcsolattartók esetében javítva lett.</span><span class="sxs-lookup"><span data-stu-id="c8d13-127">This issue is fixed for personal contacts that are created after this change.</span></span> <span data-ttu-id="c8d13-128">A meglévő **Szülő** típusú személyes kapcsolattartók egy későbbi kiadásban kerülnek javításra.</span><span class="sxs-lookup"><span data-stu-id="c8d13-128">Existing personal contacts of type **Parent** will be fixed in a later release.</span></span>

## <a name="reason-codes-display-across-different-scenarios-when-theyre-marked-as-leave-and-absence-and-the-streamlined-employee-form-is-enabled-434163"></a><span data-ttu-id="c8d13-129">Okkódok a különböző esetekben jelennek meg, ha Szabadság és távollétként vannak megjelölve és engedélyezve van az egyszerűsített dolgozói űrlap (434163)</span><span class="sxs-lookup"><span data-stu-id="c8d13-129">Reason codes display across different scenarios when they're marked as Leave and absence and the streamlined employee form is enabled (434163)</span></span>

<span data-ttu-id="c8d13-130">Ez a módosítás csak a Szabadság és távollét kódokra korlátozza az okkódokat, amikor engedélyezi az egyszerűsített dolgozói űrlapot.</span><span class="sxs-lookup"><span data-stu-id="c8d13-130">This change restricts the reason codes to only Leave and absence codes when you enable streamlined employee entry.</span></span>

## <a name="the-preview-feature-assign-a-leave-plan-to-employees-in-the-future-displays-error-433555"></a><span data-ttu-id="c8d13-131">A Jövőbeli szabadságterv hozzárendelése az alkalmazottakhoz előzetes funkció hibát jelez (433555)</span><span class="sxs-lookup"><span data-stu-id="c8d13-131">The preview feature Assign a leave plan to employees in the future displays error (433555)</span></span>

<span data-ttu-id="c8d13-132">Ez a módosítás kijavít egy hibát, amikor egy szabadságtervhez két szabadságtípus van hozzárendelve, és megpróbál hozzárendelni egy alkalmazottat.</span><span class="sxs-lookup"><span data-stu-id="c8d13-132">This change corrects an error when a leave plan has two leave types assigned and you attempt to assign an employee.</span></span>

## <a name="getting-started-banner-appears-for-all-users-441731"></a><span data-ttu-id="c8d13-133">A kezdeti lépések banner minden felhasználó számára megjelenik (441731)</span><span class="sxs-lookup"><span data-stu-id="c8d13-133">Getting started banner appears for all users (441731)</span></span>

<span data-ttu-id="c8d13-134">Ezzel a módosítással a Kezdeti lépések banner olyan felhasználók esetében rejtett, akik nem rendszergazdák vagy az adatkezelési rendszergazdák.</span><span class="sxs-lookup"><span data-stu-id="c8d13-134">With this change, the Getting started banner is hidden for users that aren't System administrators or Data management administrators.</span></span> 

## <a name="the-common-data-service-worker-address-entity-works-differently-in-terms-of-date-time-effective-dates-in-human-resources-425071"></a><span data-ttu-id="c8d13-135">A Common Data Service Dolgozó címe entitás dátum és idő tekintetében eltérően működik a Human Resources érvényességi dátumaitól (425071)</span><span class="sxs-lookup"><span data-stu-id="c8d13-135">The Common Data Service Worker Address entity works differently in terms of date time effective dates in Human Resources (425071)</span></span>

<span data-ttu-id="c8d13-136">Ez a módosítás a címadatokat a címek dátumai alapján bizonyos helyzetekben egymáshoz igazítja.</span><span class="sxs-lookup"><span data-stu-id="c8d13-136">This change keeps address information aligned in certain scenarios, based on the dates of the address.</span></span>

## <a name="unable-to-add-an-attachment-to-an-approved-leave-request-425407"></a><span data-ttu-id="c8d13-137">Nem adható hozzá melléklet egy jóváhagyott szabadságkérelemhez (425407)</span><span class="sxs-lookup"><span data-stu-id="c8d13-137">Unable to add an attachment to an approved leave request (425407)</span></span>

<span data-ttu-id="c8d13-138">Az e heti kiadással a szabadságkérelem módosítása nélkül is hozzáadhat mellékleteket a jóváhagyott szabadságkérelmekhez.</span><span class="sxs-lookup"><span data-stu-id="c8d13-138">With this week's release, you can add attachments to approved leave requests without changing the leave request.</span></span>

## <a name="in-preview"></a><span data-ttu-id="c8d13-139">Előnézetben</span><span class="sxs-lookup"><span data-stu-id="c8d13-139">In preview</span></span>

## <a name="leave-suspension"></a><span data-ttu-id="c8d13-140">Szabadság felfüggesztése</span><span class="sxs-lookup"><span data-stu-id="c8d13-140">Leave suspension</span></span>

<span data-ttu-id="c8d13-141">Egy alkalmazottra vonatkozóan felfüggesztheti a szabadságokat és a távollétet.</span><span class="sxs-lookup"><span data-stu-id="c8d13-141">You can suspend leave and absence in Human Resources for an employee.</span></span> <span data-ttu-id="c8d13-142">A szabadság felfüggesztése kiválasztott távolléti típusoknál leállítja az elhatárolást.</span><span class="sxs-lookup"><span data-stu-id="c8d13-142">Suspending leave stops the leave accruals for selected leave types.</span></span> <span data-ttu-id="c8d13-143">Ha a felfüggesztés a könyvelés feldolgozását követően következik be, akkor a szabadság felfüggesztése az alkalmazott szabadságának egyenlegéhez egy arányosan korrigált kiigazítást hoz létre.</span><span class="sxs-lookup"><span data-stu-id="c8d13-143">If the suspension occurs after an accrual has been processed, suspending leave creates a prorated adjustment to the employee's leave balance.</span></span> <span data-ttu-id="c8d13-144">További információ: [Szabadság felfüggesztése](hr-leave-and-absence-suspend-leave.md).</span><span class="sxs-lookup"><span data-stu-id="c8d13-144">For more information, see [Suspend leave](hr-leave-and-absence-suspend-leave.md).</span></span>

## <a name="update-user-experience-to-indicate-that-accrual-is-suspended-429550"></a><span data-ttu-id="c8d13-145">Felhasználói élmény frissítése annak jelzésére, hogy az elhatárolás fel van függesztve (429550)</span><span class="sxs-lookup"><span data-stu-id="c8d13-145">Update user experience to indicate that accrual is suspended (429550)</span></span>

<span data-ttu-id="c8d13-146">A felhasználói élmény immár jelzi, hogy az elhatárolás fel van függesztve egy tervhez.</span><span class="sxs-lookup"><span data-stu-id="c8d13-146">The user experience now indicates that the accrual has been suspended for a plan.</span></span>

## <a name="suspend-leave-accrual-for-specified-leave-types-272447"></a><span data-ttu-id="c8d13-147">Felfüggeszti a távollét elhatárolását a megadott szabadság-típusokhoz (272447)</span><span class="sxs-lookup"><span data-stu-id="c8d13-147">Suspend leave accrual for specified leave types (272447)</span></span>

<span data-ttu-id="c8d13-148">Ebben a kiadásban a HR olyan szabályt hozhat létre, amely felfüggeszti a távolléti elhatárolásokat a fizetés nélküli szabadságokhoz megadott szabadságkérelmekhez.</span><span class="sxs-lookup"><span data-stu-id="c8d13-148">In this release, HR can create a rule to suspend leave accruals for employees with leave requests entered for unpaid leave.</span></span> <span data-ttu-id="c8d13-149">A fizetetlen szabadság lehet egy típus, de ez nem kötelező.</span><span class="sxs-lookup"><span data-stu-id="c8d13-149">Unpaid leave can be a type, but doesn't have to be.</span></span> <span data-ttu-id="c8d13-150">Bármilyen szabadságot egy másik szabadság típus alapján fel lehet függeszteni.</span><span class="sxs-lookup"><span data-stu-id="c8d13-150">You can suspend any leave based on another leave type.</span></span>

## <a name="dmf-entity-available-for-accrual-suspensions-429549"></a><span data-ttu-id="c8d13-151">A DMF entitás elérhető az elhatárolás-felfüggesztésekhez (429549)</span><span class="sxs-lookup"><span data-stu-id="c8d13-151">DMF entity available for accrual suspensions (429549)</span></span>

<span data-ttu-id="c8d13-152">A DMF entitás immár elérhető az elhatárolás-felfüggesztésekhez.</span><span class="sxs-lookup"><span data-stu-id="c8d13-152">A DMF entity is now available for accrual suspensions.</span></span>

## <a name="add-reason-code-to-accrual-suspensions-429547"></a><span data-ttu-id="c8d13-153">Okkódhozzáadása az elhatárolás-felfüggesztésekhez (429547)</span><span class="sxs-lookup"><span data-stu-id="c8d13-153">Add reason code to accrual suspensions (429547)</span></span>

<span data-ttu-id="c8d13-154">Okkódok kerültek hozzáadásra az elhatárolás-felfüggesztéshez.</span><span class="sxs-lookup"><span data-stu-id="c8d13-154">Reason codes have been added to the accrual suspension.</span></span>

## <a name="begin-transitioning-from-human-resources-parameters-to-leave-and-absence-parameters"></a><span data-ttu-id="c8d13-155">Az átállás megkezdése a humánerőforrás-paraméterektől a szabadság és távollét paramétereire</span><span class="sxs-lookup"><span data-stu-id="c8d13-155">Begin transitioning from Human Resources parameters to leave and absence parameters</span></span>

<span data-ttu-id="c8d13-156">Ez a kiadás elkezdi kombinálni a Humán erőforrások paramétereit a szabadság és a távollét paramétereivel.</span><span class="sxs-lookup"><span data-stu-id="c8d13-156">This release starts to combine Human Resources parameters with Leave and absence parameters.</span></span>

## <a name="carry-forward-rules"></a><span data-ttu-id="c8d13-157">Átvitel szabályai</span><span class="sxs-lookup"><span data-stu-id="c8d13-157">Carry forward rules</span></span>

<span data-ttu-id="c8d13-158">Megadhatja, hogy az átviteli szabadságtípust az átviteli egyenlegekhez, ahová az átviteli korrekciók ár lesznek helyezve.</span><span class="sxs-lookup"><span data-stu-id="c8d13-158">You can specify a carry forward leave type for carry forward balances where carry forward adjustments are transferred.</span></span> <span data-ttu-id="c8d13-159">Ha például egy alkalmazott 10 napot visz át, akkor a 10 napnál más szabadság-típust is kiválaszthat.</span><span class="sxs-lookup"><span data-stu-id="c8d13-159">For example, if an employee carries forward 10 days, you can pick a different leave type for those 10 days.</span></span> <span data-ttu-id="c8d13-160">További tájékoztatás: [Szabadság és távolléti típusok konfigurálása](hr-leave-and-absence-types.md).</span><span class="sxs-lookup"><span data-stu-id="c8d13-160">For more information, see [Configure leave and absence types](hr-leave-and-absence-types.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c8d13-161">Lásd még</span><span class="sxs-lookup"><span data-stu-id="c8d13-161">See also</span></span>

[<span data-ttu-id="c8d13-162">Új vagy módosult elemek a Human Resources szolgáltatásban</span><span class="sxs-lookup"><span data-stu-id="c8d13-162">What's new or changed in Human Resources</span></span>](hr-admin-whats-new.md)</br>
[<span data-ttu-id="c8d13-163">A Dynamics 365 Human Resources 2019 második kiadási hullámának áttekintése</span><span class="sxs-lookup"><span data-stu-id="c8d13-163">Overview of Dynamics 365 Human Resources 2019 release wave 2</span></span>](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[<span data-ttu-id="c8d13-164">Rendelés frissítése</span><span class="sxs-lookup"><span data-stu-id="c8d13-164">Update process</span></span>](hr-admin-setup-update-process.md)</br>
[<span data-ttu-id="c8d13-165">Szolgáltatások kezelése</span><span class="sxs-lookup"><span data-stu-id="c8d13-165">Manage features</span></span>](hr-admin-manage-features.md)