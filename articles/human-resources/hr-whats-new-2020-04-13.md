---
title: Új vagy módosult elemek a Dynamics 365 Human Resources (2020. április 13.) szolgáltatásban
description: Ez a cikk a Microsoft Dynamics 365 Human Resources új vagy módosított szolgáltatásait írja le a 2020. április 13-i kiadásban.
author: Darinkramer
manager: AnnBe
ms.date: 4/13/2020
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
ms.search.validFrom: 2020-04-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 729490e7516d8c7aef7232c9f5c227d3207dcd68
ms.sourcegitcommit: 2bcacef1e010c312f019dbf9740ce87d627848a7
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/20/2020
ms.locfileid: "3712424"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-april-13-2020"></a><span data-ttu-id="aa4e1-103">Új vagy módosult elemek a Dynamics 365 Human Resources (2020. április 13.) szolgáltatásban</span><span class="sxs-lookup"><span data-stu-id="aa4e1-103">What's new or changed in Dynamics 365 Human Resources (April 13, 2020)</span></span>

<span data-ttu-id="aa4e1-104">Ez a cikk a Dynamics 365 Human Resources szolgáltatásban található új vagy módosított funkciókat írja le.</span><span class="sxs-lookup"><span data-stu-id="aa4e1-104">This article describes features that are either new or changed in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="aa4e1-105">A változtatások a 8.1.3136-es buildszámra vonatkoznak.</span><span class="sxs-lookup"><span data-stu-id="aa4e1-105">Changes apply to build number 8.1.3136.</span></span> <span data-ttu-id="aa4e1-106">A néhány fejlécben látható, zárójelben lévő számok az LCS támogatási számaira vonatkoznak referenciaképpen.</span><span class="sxs-lookup"><span data-stu-id="aa4e1-106">The numbers in parentheses in some headings refer to LCS support numbers for reference.</span></span>

## <a name="new-production-release-cadence"></a><span data-ttu-id="aa4e1-107">Új termelési kiadás ütemezése</span><span class="sxs-lookup"><span data-stu-id="aa4e1-107">New production release cadence</span></span>

<span data-ttu-id="aa4e1-108">Az eheti kiadástól kezdődően a program a Human Resources kiadási ritmusa heti frissítésről a kétheti frissítésre módosul.</span><span class="sxs-lookup"><span data-stu-id="aa4e1-108">With this week's release, the release cadence for Human Resources shifts from a weekly update to a biweekly update.</span></span> <span data-ttu-id="aa4e1-109">A biztonságos telepítési gyakorlattal való összehangolás biztosításához és a szolgáltatásban a stabilitás és megbízhatóság magas színvonalának megőrzéséhez a szolgáltatás frissítései minden régióban két hetes ütemezésre váltanak.</span><span class="sxs-lookup"><span data-stu-id="aa4e1-109">To ensure alignment with safe deployment practices, and maintain high standards of stability and reliability in the service, the process of deploying service updates to all regions is now a two-week rollout.</span></span> <span data-ttu-id="aa4e1-110">További tesztek és nyomon követések lettek bevezetve a sikeres telepítés megerősítéséhez a folyamat minden egyes fázisában.</span><span class="sxs-lookup"><span data-stu-id="aa4e1-110">Additional testing and monitors are in place to verify successful deployment at each stage of the process.</span></span> <span data-ttu-id="aa4e1-111">A kiadás ritmusával kapcsolatos további tudnivalókat lásd: [Frissítési folyamat](hr-admin-setup-update-process.md).</span><span class="sxs-lookup"><span data-stu-id="aa4e1-111">For more information on the release cadence, see [Update process](hr-admin-setup-update-process.md).</span></span>

## <a name="rounding-precision-field-isnt-editable-after-specifying-a-rounding-type-435616"></a><span data-ttu-id="aa4e1-112">A kerekítési pontosság mező nem szerkeszthető a kerekítési típus megadása után (435616)</span><span class="sxs-lookup"><span data-stu-id="aa4e1-112">Rounding precision field isn't editable after specifying a Rounding type (435616)</span></span>

<span data-ttu-id="aa4e1-113">Ezzel a módosítással a **Kerekítési pontosság** mező már elérhető a **Kerekítési típus** mező frissítése után.</span><span class="sxs-lookup"><span data-stu-id="aa4e1-113">With this change, the **Rounding precision** field is now available after you update the **Rounding type** field.</span></span>

## <a name="cant-edit-leave-enrollment-end-date-when-the-leave-plan-doesnt-have-accrual-periods-413628"></a><span data-ttu-id="aa4e1-114">Nem lehet módosítani a szabadságterv záró dátumát, ha a szabadságterv nem rendelkezik elhatárolási időszakokkal (413628)</span><span class="sxs-lookup"><span data-stu-id="aa4e1-114">Can't edit leave enrollment end date when the leave plan doesn't have accrual periods (413628)</span></span>

<span data-ttu-id="aa4e1-115">Most szerkesztheti a regisztráció záró dátumát anélkül, hogy az „Elhatárolási dátum mezőt ki kell tölteni” hibaüzenetet kapná.</span><span class="sxs-lookup"><span data-stu-id="aa4e1-115">You can now edit the enrollment end date without getting the error "Field Accrual date basis must be filled in."</span></span>

## <a name="employment-entity-doesnt-sync-to-common-data-service-430834"></a><span data-ttu-id="aa4e1-116">A foglalkoztatás entitása nem szinkronizál a Common Data Service szolgáltatásba (430834)</span><span class="sxs-lookup"><span data-stu-id="aa4e1-116">Employment entity doesn't sync to Common Data Service (430834)</span></span>

<span data-ttu-id="aa4e1-117">A módosítás javítja azt a hibát, amikor a pénzügyi dimenziók hozzáadását követően a foglalkoztatási adatok nem lettek szinkronizálva a Common Data Service szolgáltatásba.</span><span class="sxs-lookup"><span data-stu-id="aa4e1-117">This change corrects an issue where the employment data wasn't syncing to Common Data Service after adding financial dimensions.</span></span> 

## <a name="remove-multi-parenting-for-work-calendar-time-interval-entity-431775"></a><span data-ttu-id="aa4e1-118">Több szülő eltávolítása a Munkanaptár időintervalluma entitáshoz (431775)</span><span class="sxs-lookup"><span data-stu-id="aa4e1-118">Remove multi-parenting for Work Calendar Time Interval entity (431775)</span></span>

<span data-ttu-id="aa4e1-119">Ez a módosítás eltávolítja a több szülőt eltávolítása a **Munkanaptár időintervalluma** entitáshoz.</span><span class="sxs-lookup"><span data-stu-id="aa4e1-119">This change removes multi-parenting for the **Work Calendar Time Interval** entity.</span></span>

## <a name="filter-with-cast-function-doesnt-work-on-odata-call-position-worker-assignment-entity-431699"></a><span data-ttu-id="aa4e1-120">A CAST funkcióval rendelkező szűrő nem működik az Beosztáshoz rendelt dolgozó entitás OData hívásakor (431699)</span><span class="sxs-lookup"><span data-stu-id="aa4e1-120">Filter with CAST function doesn't work on OData call Position Worker Assignment entity (431699)</span></span>

<span data-ttu-id="aa4e1-121">A frissítés tartalmaz egy módosítást, amely lehetővé teszi, hogy a OData CAST funkciójával szűrni lehessen a **Beosztáshoz rendelt dolgozó** entitásra.</span><span class="sxs-lookup"><span data-stu-id="aa4e1-121">This update includes a change to allow  filter with CAST function within OData for the **Position Worker Assignment** entity.</span></span>

## <a name="in-preview"></a><span data-ttu-id="aa4e1-122">Előnézetben</span><span class="sxs-lookup"><span data-stu-id="aa4e1-122">In Preview</span></span>

## <a name="leave-suspension"></a><span data-ttu-id="aa4e1-123">Szabadság felfüggesztése</span><span class="sxs-lookup"><span data-stu-id="aa4e1-123">Leave suspension</span></span>

<span data-ttu-id="aa4e1-124">Egy alkalmazottra vonatkozóan felfüggesztheti a szabadságokat és a távollétet.</span><span class="sxs-lookup"><span data-stu-id="aa4e1-124">You can suspend leave and absence in Human Resources for an employee.</span></span> <span data-ttu-id="aa4e1-125">A szabadság felfüggesztése kiválasztott távolléti típusoknál leállítja az elhatárolást.</span><span class="sxs-lookup"><span data-stu-id="aa4e1-125">Suspending leave stops the leave accruals for selected leave types.</span></span> <span data-ttu-id="aa4e1-126">Ha a felfüggesztés a könyvelés feldolgozását követően következik be, akkor a szabadság felfüggesztése az alkalmazott szabadságának egyenlegéhez egy arányosan korrigált kiigazítást hoz létre.</span><span class="sxs-lookup"><span data-stu-id="aa4e1-126">If the suspension occurs after an accrual has been processed, suspending leave creates a prorated adjustment to the employee's leave balance.</span></span> <span data-ttu-id="aa4e1-127">További információ: [Szabadság felfüggesztése](hr-leave-and-absence-suspend-leave.md).</span><span class="sxs-lookup"><span data-stu-id="aa4e1-127">For more information, see [Suspend leave](hr-leave-and-absence-suspend-leave.md).</span></span>

## <a name="carry-forward-rules"></a><span data-ttu-id="aa4e1-128">Átvitel szabályai</span><span class="sxs-lookup"><span data-stu-id="aa4e1-128">Carry forward rules</span></span>

<span data-ttu-id="aa4e1-129">Megadhatja, hogy az átviteli szabadságtípust az átviteli egyenlegekhez, ahová az átviteli korrekciók ár lesznek helyezve.</span><span class="sxs-lookup"><span data-stu-id="aa4e1-129">You can specify a carry forward leave type for carry forward balances where carry forward adjustments are transferred.</span></span> <span data-ttu-id="aa4e1-130">Ha például egy alkalmazott 10 napot visz át, akkor a 10 napnál más szabadság-típust is kiválaszthat.</span><span class="sxs-lookup"><span data-stu-id="aa4e1-130">For example, if an employee carries forward 10 days, you can pick a different leave type for those 10 days.</span></span> <span data-ttu-id="aa4e1-131">További tájékoztatás: [Szabadság és távolléti típusok konfigurálása](hr-leave-and-absence-types.md).</span><span class="sxs-lookup"><span data-stu-id="aa4e1-131">For more information, see [Configure leave and absence types](hr-leave-and-absence-types.md).</span></span>

## <a name="known-issues"></a><span data-ttu-id="aa4e1-132">Ismert problémák</span><span class="sxs-lookup"><span data-stu-id="aa4e1-132">Known issues</span></span>

## <a name="employment-details-entity"></a><span data-ttu-id="aa4e1-133">Foglalkoztatás részletei entitás</span><span class="sxs-lookup"><span data-stu-id="aa4e1-133">Employment Details entity</span></span>

<span data-ttu-id="aa4e1-134">A **Foglalkoztatási részletei** entitás frissítve lett a következő mezőkkel:</span><span class="sxs-lookup"><span data-stu-id="aa4e1-134">The **Employment Detail** entity has been updated with the following fields:</span></span>

- <span data-ttu-id="aa4e1-135">**PayFrequency**</span><span class="sxs-lookup"><span data-stu-id="aa4e1-135">**PayFrequency**</span></span>
- <span data-ttu-id="aa4e1-136">**Foglalkoztatási kategóriaazonosítója**</span><span class="sxs-lookup"><span data-stu-id="aa4e1-136">**Employment Category ID**</span></span>
- <span data-ttu-id="aa4e1-137">**Foglalkoztatási típus**</span><span class="sxs-lookup"><span data-stu-id="aa4e1-137">**Employment Type**</span></span>
- <span data-ttu-id="aa4e1-138">**EmploymentType azonosító**</span><span class="sxs-lookup"><span data-stu-id="aa4e1-138">**EmploymentType ID**</span></span>
- <span data-ttu-id="aa4e1-139">**Juttatás foglalkoztatási állapota**</span><span class="sxs-lookup"><span data-stu-id="aa4e1-139">**Benefit Employment Status**</span></span>

<span data-ttu-id="aa4e1-140">Ezeknek a mezőknek a beállítási adatai a **Funkciókezelés** munkaterületen engedélyezve vannak a juttatások kezeléséhez.</span><span class="sxs-lookup"><span data-stu-id="aa4e1-140">The setup data for these fields rely on benefits management being enabled in the **Feature management** workspace.</span></span> <span data-ttu-id="aa4e1-141">Ne töltse ki vagy frissítse ezeket a mezőket a **Foglalkoztatás részletei** entitásban, mert ez hibákat fog eredményezni az importálás során.</span><span class="sxs-lookup"><span data-stu-id="aa4e1-141">Don't populate or update these fields in the **Employment Detail** entity, because it will result in errors during import.</span></span>

## <a name="sharepoint-preview-doesnt-work-in-some-environments"></a><span data-ttu-id="aa4e1-142">SharePoint előnézet nem használható bizonyos környezetekben</span><span class="sxs-lookup"><span data-stu-id="aa4e1-142">SharePoint preview doesn't work in some environments</span></span>

<span data-ttu-id="aa4e1-143">Ha egy, a SharePoint-ban tárolt dokumentum előnézete nem működik, próbálja meg a következő eljárást:</span><span class="sxs-lookup"><span data-stu-id="aa4e1-143">If document preview for documents stored in SharePoint doesn't work, try the following procedure:</span></span>

1. <span data-ttu-id="aa4e1-144">Ellenőrizze, hogy az Adminisztrátor felhasználói fiók rendelkezik-e a felhasználói rekordhoz társított e-mail-címmel.</span><span class="sxs-lookup"><span data-stu-id="aa4e1-144">Verify the Admin user account has an email associated with the user record.</span></span> <span data-ttu-id="aa4e1-145">Ezt az információt a **Felhasználó** oldalon lehet megtekinteni.</span><span class="sxs-lookup"><span data-stu-id="aa4e1-145">You can view this information in the **User** page.</span></span> <span data-ttu-id="aa4e1-146">Ha nincs beállítva e-mail-cím, akkor az e-mail-címet és a szolgáltatót hozzá kell adnia az OData Excel-bővítménnyel.</span><span class="sxs-lookup"><span data-stu-id="aa4e1-146">If email isn't set up, you need to add the email and provider with the OData Excel add-in.</span></span> <span data-ttu-id="aa4e1-147">Alapértelmezés szerint az e-mail-cím nem szerepel az Excel-tervben.</span><span class="sxs-lookup"><span data-stu-id="aa4e1-147">By default, the email address isn't present in the Excel design.</span></span> <span data-ttu-id="aa4e1-148">Szerkesztenie kell az Excel-tervet, minden mezőt fel kell venni, alkalmazni kell, majd frissíteni kell.</span><span class="sxs-lookup"><span data-stu-id="aa4e1-148">You'll need to edit the Excel design, add all fields, apply, and refresh.</span></span> <span data-ttu-id="aa4e1-149">Miután befejezte ezeket a lépéseket, frissítheti az adminisztrátori fiókot.</span><span class="sxs-lookup"><span data-stu-id="aa4e1-149">Once you've completed those steps, you can update the admin account.</span></span>

2. <span data-ttu-id="aa4e1-150">Miután az Adminisztrátor fiókhoz hozzá van rendelve egy e-mail-fiók, az Adminisztrátori hitelesítő adatokkal jelentkezzen be a Human Resources szolgáltatásokba.</span><span class="sxs-lookup"><span data-stu-id="aa4e1-150">After the Admin account has an associated email account, sign in to Human Resources with Admin credentials.</span></span>

3. <span data-ttu-id="aa4e1-151">A dokumentum előnézetének indításához nyisson meg egy mellékletet SharePoint-ban.</span><span class="sxs-lookup"><span data-stu-id="aa4e1-151">Access an attachment in SharePoint to start the document preview.</span></span>

4. <span data-ttu-id="aa4e1-152">Jelentkezzen be egy másik olyan felhasználói fiókkal, amely hozzáférhet a mellékletekhez, és ellenőrizze, hogy az előnézet a várt módon működik-e.</span><span class="sxs-lookup"><span data-stu-id="aa4e1-152">Sign in with another user account that has access to attachments and verify that the preview works as expected.</span></span>

## <a name="see-also"></a><span data-ttu-id="aa4e1-153">Lásd még</span><span class="sxs-lookup"><span data-stu-id="aa4e1-153">See also</span></span>

[<span data-ttu-id="aa4e1-154">Új vagy módosult elemek a Human Resources szolgáltatásban</span><span class="sxs-lookup"><span data-stu-id="aa4e1-154">What's new or changed in Human Resources</span></span>](hr-admin-whats-new.md)</br>
[<span data-ttu-id="aa4e1-155">A Dynamics 365 Human Resources 2019 második kiadási hullámának áttekintése</span><span class="sxs-lookup"><span data-stu-id="aa4e1-155">Overview of Dynamics 365 Human Resources 2019 release wave 2</span></span>](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[<span data-ttu-id="aa4e1-156">Rendelés frissítése</span><span class="sxs-lookup"><span data-stu-id="aa4e1-156">Update process</span></span>](hr-admin-setup-update-process.md)</br>
[<span data-ttu-id="aa4e1-157">Szolgáltatások kezelése</span><span class="sxs-lookup"><span data-stu-id="aa4e1-157">Manage features</span></span>](hr-admin-manage-features.md)