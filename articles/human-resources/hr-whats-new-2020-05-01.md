---
title: Új vagy módosult elemek a Dynamics 365 Human Resources szolgáltatásban (2020. május 1.)
description: Ez a cikk a Microsoft Dynamics 365 Human Resources új vagy módosított szolgáltatásait írja le a 2020. május 1-i kiadásban.
author: Darinkramer
manager: AnnBe
ms.date: 05/01/2020
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
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 074c678d9d8294aabf4e78b2a6ee0fa53efbaf23
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4418863"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-may-1-2020"></a><span data-ttu-id="88c1c-103">Új vagy módosult elemek a Dynamics 365 Human Resources szolgáltatásban (2020. május 1.)</span><span class="sxs-lookup"><span data-stu-id="88c1c-103">What's new or changed in Dynamics 365 Human Resources (May 1, 2020)</span></span>

<span data-ttu-id="88c1c-104">Ez a cikk a Dynamics 365 Human Resources szolgáltatásban található új vagy módosított funkciókat írja le.</span><span class="sxs-lookup"><span data-stu-id="88c1c-104">This article describes features that are either new or changed in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="88c1c-105">A változtatások a 8.1.3196-es buildszámra vonatkoznak.</span><span class="sxs-lookup"><span data-stu-id="88c1c-105">Changes apply to build number 8.1.3196.</span></span> <span data-ttu-id="88c1c-106">A néhány fejlécben látható, zárójelben lévő számok az LCS támogatási számaira vonatkoznak referenciaképpen.</span><span class="sxs-lookup"><span data-stu-id="88c1c-106">The numbers in parentheses in some headings refer to LCS support numbers for reference.</span></span>

## <a name="new-performance-management-entities-available-in-data-management-framework-dmf"></a><span data-ttu-id="88c1c-107">Új Teljesítménykezelés entitások érhetők el az Adatkezelő keretrendszerben (DMF)</span><span class="sxs-lookup"><span data-stu-id="88c1c-107">New Performance Management entities available in Data Management Framework (DMF)</span></span>

<span data-ttu-id="88c1c-108">A következő entitások állnak rendelkezésre.</span><span class="sxs-lookup"><span data-stu-id="88c1c-108">The following entities are now available.</span></span> <span data-ttu-id="88c1c-109">Ha nem látja ezeket az entitásokat az entitások listában, akkor válassza az **Entitások frissítése** lehetőséget a **Keretrendszer paraméterei > Entitásbeállítások > Entitáslista frissítése helyen**.</span><span class="sxs-lookup"><span data-stu-id="88c1c-109">If you don't see these entities listed in the entities list, use the **Refresh entities** option in **Framework Parameters > Entity settings > Refresh entity list**.</span></span>

- <span data-ttu-id="88c1c-110">**Vitafórum-kompetencia**</span><span class="sxs-lookup"><span data-stu-id="88c1c-110">**Discussion Competency**</span></span>
- <span data-ttu-id="88c1c-111">**Vitafórumcélok**</span><span class="sxs-lookup"><span data-stu-id="88c1c-111">**Discussion Goals**</span></span>
- <span data-ttu-id="88c1c-112">**Vitafórummérés**</span><span class="sxs-lookup"><span data-stu-id="88c1c-112">**Discussion Measurement**</span></span>
- <span data-ttu-id="88c1c-113">**Vitafórum-témakör**</span><span class="sxs-lookup"><span data-stu-id="88c1c-113">**Discussion Topic**</span></span>
- <span data-ttu-id="88c1c-114">**Teljesítménynapló**</span><span class="sxs-lookup"><span data-stu-id="88c1c-114">**Performance Journal**</span></span>
- <span data-ttu-id="88c1c-115">**Mértékegység**</span><span class="sxs-lookup"><span data-stu-id="88c1c-115">**Measurement**</span></span>
- <span data-ttu-id="88c1c-116">**Cél mérése**</span><span class="sxs-lookup"><span data-stu-id="88c1c-116">**Goal Measurement**</span></span>

<span data-ttu-id="88c1c-117">Ezenkívül az **Összpontszám** és **Átlagos pontszám** is hozzá lettek adva a **Vitafórum** entitáshoz.</span><span class="sxs-lookup"><span data-stu-id="88c1c-117">In addition, **Total score** and **Average score** were added to the **Discussion** entity.</span></span>

## <a name="increase-length-of-leave-request-comments-275641"></a><span data-ttu-id="88c1c-118">A szabadságkérelmek megjegyzései hosszának növelése (275641)</span><span class="sxs-lookup"><span data-stu-id="88c1c-118">Increase length of leave request comments (275641)</span></span>

<span data-ttu-id="88c1c-119">A szabadságkérelmekkel kapcsolatos megjegyzésekben most már 100 több karakter is megadható.</span><span class="sxs-lookup"><span data-stu-id="88c1c-119">Comments on leave requests now allow more than 100 characters.</span></span>

## <a name="final-comments-on-reviews-dont-appear-when-the-manager-or-employee-is-signed-into-a-different-company-431688"></a><span data-ttu-id="88c1c-120">Az értékelésekkel kapcsolatos végleges megjegyzések nem jelennek meg, ha a vezető vagy az alkalmazott egy másik vállalatba van bejelentkezve (431688)</span><span class="sxs-lookup"><span data-stu-id="88c1c-120">Final comments on reviews don't appear when the manager or employee is signed into a different company (431688)</span></span>

<span data-ttu-id="88c1c-121">Az összes megjegyzés megjelenik az értékelések megtekintésekor.</span><span class="sxs-lookup"><span data-stu-id="88c1c-121">All comments will now appear when viewing reviews.</span></span>

## <a name="user-defined-links-arent-supported-on-new-worker-form-390374"></a><span data-ttu-id="88c1c-122">A felhasználó által definiált hivatkozások nem támogatottak az új Dolgozó képernyőn (390374)</span><span class="sxs-lookup"><span data-stu-id="88c1c-122">User-defined links aren't supported on new Worker form (390374)</span></span>

<span data-ttu-id="88c1c-123">A felhasználó által definiált hivatkozások ezentúl engedélyezve vannak a racionalizált **Dolgozó** képernyőn.</span><span class="sxs-lookup"><span data-stu-id="88c1c-123">User-defined links are now enabled on the streamlined **Worker** form.</span></span>

## <a name="hcmratinglevelentity-causes-odata-api-crash-439476"></a><span data-ttu-id="88c1c-124">A HcmRatingLevelEntity az OData API összeomlását okozza (439476)</span><span class="sxs-lookup"><span data-stu-id="88c1c-124">HcmRatingLevelEntity causes OData API crash (439476)</span></span>

<span data-ttu-id="88c1c-125">Ez a módosítás javítja az API összeomlását.</span><span class="sxs-lookup"><span data-stu-id="88c1c-125">This change corrects the API crash.</span></span> <span data-ttu-id="88c1c-126">Ezt a hibát egy ismétlődő név okozta.</span><span class="sxs-lookup"><span data-stu-id="88c1c-126">A duplicate name cased this error.</span></span>

## <a name="in-preview"></a><span data-ttu-id="88c1c-127">Előnézetben</span><span class="sxs-lookup"><span data-stu-id="88c1c-127">In preview</span></span>

## <a name="leave-suspension"></a><span data-ttu-id="88c1c-128">Szabadság felfüggesztése</span><span class="sxs-lookup"><span data-stu-id="88c1c-128">Leave suspension</span></span>

<span data-ttu-id="88c1c-129">Egy alkalmazottra vonatkozóan felfüggesztheti a szabadságokat és a távollétet.</span><span class="sxs-lookup"><span data-stu-id="88c1c-129">You can suspend leave and absence in Human Resources for an employee.</span></span> <span data-ttu-id="88c1c-130">A szabadság felfüggesztése kiválasztott távolléti típusoknál leállítja az elhatárolást.</span><span class="sxs-lookup"><span data-stu-id="88c1c-130">Suspending leave stops the leave accruals for selected leave types.</span></span> <span data-ttu-id="88c1c-131">Ha a felfüggesztés a könyvelés feldolgozását követően következik be, akkor a szabadság felfüggesztése az alkalmazott szabadságának egyenlegéhez egy arányosan korrigált kiigazítást hoz létre.</span><span class="sxs-lookup"><span data-stu-id="88c1c-131">If the suspension occurs after an accrual has been processed, suspending leave creates a prorated adjustment to the employee's leave balance.</span></span> <span data-ttu-id="88c1c-132">További információ: [Szabadság felfüggesztése](hr-leave-and-absence-suspend-leave.md).</span><span class="sxs-lookup"><span data-stu-id="88c1c-132">For more information, see [Suspend leave](hr-leave-and-absence-suspend-leave.md).</span></span>

## <a name="update-user-experience-to-indicate-that-accrual-is-suspended-429550"></a><span data-ttu-id="88c1c-133">Felhasználói élmény frissítése annak jelzésére, hogy az elhatárolás fel van függesztve (429550)</span><span class="sxs-lookup"><span data-stu-id="88c1c-133">Update user experience to indicate that accrual is suspended (429550)</span></span>

<span data-ttu-id="88c1c-134">A felhasználói élmény immár jelzi, hogy az elhatárolás fel van függesztve egy tervhez.</span><span class="sxs-lookup"><span data-stu-id="88c1c-134">The user experience now indicates that the accrual has been suspended for a plan.</span></span>

## <a name="suspend-leave-accrual-for-specified-leave-types-272447"></a><span data-ttu-id="88c1c-135">Felfüggeszti a távollét elhatárolását a megadott szabadság-típusokhoz (272447)</span><span class="sxs-lookup"><span data-stu-id="88c1c-135">Suspend leave accrual for specified leave types (272447)</span></span>

<span data-ttu-id="88c1c-136">Ebben a kiadásban a HR olyan szabályt hozhat létre, amely felfüggeszti a távolléti elhatárolásokat a fizetés nélküli szabadságokhoz megadott szabadságkérelmekhez.</span><span class="sxs-lookup"><span data-stu-id="88c1c-136">In this release, HR can create a rule to suspend leave accruals for employees with leave requests entered for unpaid leave.</span></span> <span data-ttu-id="88c1c-137">A fizetetlen szabadság lehet egy típus, de ez nem kötelező.</span><span class="sxs-lookup"><span data-stu-id="88c1c-137">Unpaid leave can be a type, but doesn't have to be.</span></span> <span data-ttu-id="88c1c-138">Bármilyen szabadságot egy másik szabadság típus alapján fel lehet függeszteni.</span><span class="sxs-lookup"><span data-stu-id="88c1c-138">You can suspend any leave based on another leave type.</span></span>

## <a name="dmf-entity-available-for-accrual-suspensions-429549"></a><span data-ttu-id="88c1c-139">A DMF entitás elérhető az elhatárolás-felfüggesztésekhez (429549)</span><span class="sxs-lookup"><span data-stu-id="88c1c-139">DMF entity available for accrual suspensions (429549)</span></span>

<span data-ttu-id="88c1c-140">A DMF entitás immár elérhető az elhatárolás-felfüggesztésekhez.</span><span class="sxs-lookup"><span data-stu-id="88c1c-140">A DMF entity is now available for accrual suspensions.</span></span>

## <a name="add-reason-code-to-accrual-suspensions-429547"></a><span data-ttu-id="88c1c-141">Okkódhozzáadása az elhatárolás-felfüggesztésekhez (429547)</span><span class="sxs-lookup"><span data-stu-id="88c1c-141">Add reason code to accrual suspensions (429547)</span></span>

<span data-ttu-id="88c1c-142">Okkódok kerültek hozzáadásra az elhatárolás-felfüggesztéshez.</span><span class="sxs-lookup"><span data-stu-id="88c1c-142">Reason codes have been added to the accrual suspension.</span></span>

## <a name="begin-transitioning-from-human-resources-parameters-to-leave-and-absence-parameters"></a><span data-ttu-id="88c1c-143">Az átállás megkezdése a humánerőforrás-paraméterektől a szabadság és távollét paramétereire</span><span class="sxs-lookup"><span data-stu-id="88c1c-143">Begin transitioning from Human Resources parameters to leave and absence parameters</span></span>

<span data-ttu-id="88c1c-144">Ez a kiadás elkezdi kombinálni a Humán erőforrások paramétereit a szabadság és a távollét paramétereivel.</span><span class="sxs-lookup"><span data-stu-id="88c1c-144">This release starts to combine Human Resources parameters with Leave and absence parameters.</span></span>

## <a name="carry-forward-rules"></a><span data-ttu-id="88c1c-145">Átvitel szabályai</span><span class="sxs-lookup"><span data-stu-id="88c1c-145">Carry forward rules</span></span>

<span data-ttu-id="88c1c-146">Megadhatja, hogy az átviteli szabadságtípust az átviteli egyenlegekhez, ahová az átviteli korrekciók ár lesznek helyezve.</span><span class="sxs-lookup"><span data-stu-id="88c1c-146">You can specify a carry forward leave type for carry forward balances where carry forward adjustments are transferred.</span></span> <span data-ttu-id="88c1c-147">Ha például egy alkalmazott 10 napot visz át, akkor a 10 napnál más szabadság-típust is kiválaszthat.</span><span class="sxs-lookup"><span data-stu-id="88c1c-147">For example, if an employee carries forward 10 days, you can pick a different leave type for those 10 days.</span></span> <span data-ttu-id="88c1c-148">További tájékoztatás: [Szabadság és távolléti típusok konfigurálása](hr-leave-and-absence-types.md).</span><span class="sxs-lookup"><span data-stu-id="88c1c-148">For more information, see [Configure leave and absence types](hr-leave-and-absence-types.md).</span></span>

## <a name="known-issues"></a><span data-ttu-id="88c1c-149">Ismert problémák</span><span class="sxs-lookup"><span data-stu-id="88c1c-149">Known issues</span></span>

## <a name="sharepoint-preview-doesnt-work-in-some-environments"></a><span data-ttu-id="88c1c-150">SharePoint előnézet nem használható bizonyos környezetekben</span><span class="sxs-lookup"><span data-stu-id="88c1c-150">SharePoint preview doesn't work in some environments</span></span>

<span data-ttu-id="88c1c-151">Ha egy, a SharePoint-ban tárolt dokumentum előnézete nem működik, próbálja meg a következő eljárást:</span><span class="sxs-lookup"><span data-stu-id="88c1c-151">If document preview for documents stored in SharePoint doesn't work, try the following procedure:</span></span>

1. <span data-ttu-id="88c1c-152">Ellenőrizze, hogy az Adminisztrátor felhasználói fiók rendelkezik-e a felhasználói rekordhoz társított e-mail-címmel.</span><span class="sxs-lookup"><span data-stu-id="88c1c-152">Verify the Admin user account has an email associated with the user record.</span></span> <span data-ttu-id="88c1c-153">Ezt az információt a **Felhasználó** oldalon lehet megtekinteni.</span><span class="sxs-lookup"><span data-stu-id="88c1c-153">You can view this information in the **User** page.</span></span> <span data-ttu-id="88c1c-154">Ha nincs beállítva e-mail-cím, akkor az e-mail-címet és a szolgáltatót hozzá kell adnia az OData Excel-bővítménnyel.</span><span class="sxs-lookup"><span data-stu-id="88c1c-154">If email isn't set up, you need to add the email and provider with the OData Excel add-in.</span></span> <span data-ttu-id="88c1c-155">Alapértelmezés szerint az e-mail-cím nem szerepel az Excel-tervben.</span><span class="sxs-lookup"><span data-stu-id="88c1c-155">By default, the email address isn't present in the Excel design.</span></span> <span data-ttu-id="88c1c-156">Szerkesztenie kell az Excel-tervet, minden mezőt fel kell venni, alkalmazni kell, majd frissíteni kell.</span><span class="sxs-lookup"><span data-stu-id="88c1c-156">You'll need to edit the Excel design, add all fields, apply, and refresh.</span></span> <span data-ttu-id="88c1c-157">Miután befejezte ezeket a lépéseket, frissítheti az adminisztrátori fiókot.</span><span class="sxs-lookup"><span data-stu-id="88c1c-157">Once you've completed those steps, you can update the admin account.</span></span>

2. <span data-ttu-id="88c1c-158">Miután az Adminisztrátor fiókhoz hozzá van rendelve egy e-mail-fiók, az Adminisztrátori hitelesítő adatokkal jelentkezzen be a Human Resources szolgáltatásokba.</span><span class="sxs-lookup"><span data-stu-id="88c1c-158">After the Admin account has an associated email account, sign in to Human Resources with Admin credentials.</span></span>

3. <span data-ttu-id="88c1c-159">A dokumentum előnézetének indításához nyisson meg egy mellékletet SharePoint-ban.</span><span class="sxs-lookup"><span data-stu-id="88c1c-159">Access an attachment in SharePoint to start the document preview.</span></span>

4. <span data-ttu-id="88c1c-160">Jelentkezzen be egy másik olyan felhasználói fiókkal, amely hozzáférhet a mellékletekhez, és ellenőrizze, hogy az előnézet a várt módon működik-e.</span><span class="sxs-lookup"><span data-stu-id="88c1c-160">Sign in with another user account that has access to attachments and verify that the preview works as expected.</span></span>

## <a name="see-also"></a><span data-ttu-id="88c1c-161">Lásd még</span><span class="sxs-lookup"><span data-stu-id="88c1c-161">See also</span></span>

[<span data-ttu-id="88c1c-162">Új vagy módosult elemek a Human Resources szolgáltatásban</span><span class="sxs-lookup"><span data-stu-id="88c1c-162">What's new or changed in Human Resources</span></span>](hr-admin-whats-new.md)</br>
[<span data-ttu-id="88c1c-163">A Dynamics 365 Human Resources 2019 második kiadási hullámának áttekintése</span><span class="sxs-lookup"><span data-stu-id="88c1c-163">Overview of Dynamics 365 Human Resources 2019 release wave 2</span></span>](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[<span data-ttu-id="88c1c-164">Rendelés frissítése</span><span class="sxs-lookup"><span data-stu-id="88c1c-164">Update process</span></span>](hr-admin-setup-update-process.md)</br>
[<span data-ttu-id="88c1c-165">Szolgáltatások kezelése</span><span class="sxs-lookup"><span data-stu-id="88c1c-165">Manage features</span></span>](hr-admin-manage-features.md)