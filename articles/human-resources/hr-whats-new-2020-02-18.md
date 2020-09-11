---
title: Új vagy módosult elemek a Dynamics 365 Human Resources szolgáltatásban (2020. február 18.)
description: Ez a cikk a Microsoft Dynamics 365 Human Resources új vagy módosított szolgáltatásait írja le a 2020. február 18-i kiadásban.
author: Darinkramer
manager: AnnBe
ms.date: 02/18/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2020-02-18
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 5e9e1f05de682b4fe29ec23f06099b2968ebe3df
ms.sourcegitcommit: 2bcacef1e010c312f019dbf9740ce87d627848a7
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/20/2020
ms.locfileid: "3711988"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-february-18-2020"></a><span data-ttu-id="72797-103">Új vagy módosult elemek a Dynamics 365 Human Resources szolgáltatásban (2020. február 18.)</span><span class="sxs-lookup"><span data-stu-id="72797-103">What's new or changed in Dynamics 365 Human Resources (February 18, 2020)</span></span>

<span data-ttu-id="72797-104">Ez a cikk a Dynamics 365 Human Resources szolgáltatásban található új vagy módosított funkciókat írja le.</span><span class="sxs-lookup"><span data-stu-id="72797-104">This article describes features that are either new or changed in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="72797-105">A változtatások a 8.1.2903-es buildszámra vonatkoznak.</span><span class="sxs-lookup"><span data-stu-id="72797-105">Changes apply to build number 8.1.2903.</span></span> <span data-ttu-id="72797-106">A néhány fejlécben látható, zárójelben lévő számok az LCS támogatási számaira vonatkoznak referenciaképpen.</span><span class="sxs-lookup"><span data-stu-id="72797-106">The numbers in parentheses in some headings refer to LCS support numbers for reference.</span></span>

## <a name="platform-update-32"></a><span data-ttu-id="72797-107">32-as platformfrissítés</span><span class="sxs-lookup"><span data-stu-id="72797-107">Platform update 32</span></span> 

<span data-ttu-id="72797-108">A 32-es platform-frissítés már elérhető.</span><span class="sxs-lookup"><span data-stu-id="72797-108">Platform update 32 is now available.</span></span> <span data-ttu-id="72797-109">A további tudnivalókat lásd: [Újdonságok és módosítások a Finance and Operations-alkalmazások 32-as platformfrissítéséhez (2020. február)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-update-32).</span><span class="sxs-lookup"><span data-stu-id="72797-109">For more information, see [What's new or changed in Platform update 32 for Finance and Operations (February 2020)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-update-32).</span></span>

## <a name="search-values-are-remembered-when-changing-view-options-in-streamlined-employee-form-383833"></a><span data-ttu-id="72797-110">A program a keresési értékeket az egyszerűsített alkalmazotti űrlap nézetbeállításainak módosításakor emlékszik (383833).</span><span class="sxs-lookup"><span data-stu-id="72797-110">Search values are remembered when changing view options in streamlined employee form (383833)</span></span>

<span data-ttu-id="72797-111">Az új **Dolgozó** képernyő most emlékszik a keresési értékekre, amikor megváltoztatja a nézet beállításait, és alkalmazza a változtatásokat.</span><span class="sxs-lookup"><span data-stu-id="72797-111">The new **Worker** form now remembers  search values when you change the view options and apply changes.</span></span>

## <a name="compensation-management-summary-tiles-in-preview-feature-redirect-to-wrong-form-401861"></a><span data-ttu-id="72797-112">Kompenzációkezelés összesítése csempék az előzetes funkcióban a rossz űrlapra irányítanak (401861)</span><span class="sxs-lookup"><span data-stu-id="72797-112">Compensation management summary tiles in preview feature redirect to wrong form (401861)</span></span>

<span data-ttu-id="72797-113">A fix és változó kompenzációs kezelési csempék most a megfelelő rekordokat jelenítik meg az új **Dolgozó** képernyőn.</span><span class="sxs-lookup"><span data-stu-id="72797-113">Fixed and variable compensation management tiles now display the correct records in the new **Worker** form.</span></span> <span data-ttu-id="72797-114">Csak az egyszerűsített dolgozói űrlap előzetes funkciójára vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="72797-114">Applies only to the streamlined employee form preview feature.</span></span> <span data-ttu-id="72797-115">Ezt az előnézeti funkciót engedélyezheti a **szolgáltatások kezelése** modulban.</span><span class="sxs-lookup"><span data-stu-id="72797-115">You can enable this preview feature in **Feature management**.</span></span> <span data-ttu-id="72797-116">További információért lásd: [Funkciók kezelése](hr-admin-manage-features.md).</span><span class="sxs-lookup"><span data-stu-id="72797-116">For more information, see [Manage features](hr-admin-manage-features.md).</span></span>

## <a name="empty-status-field-for-some-leave-request-records-in-common-data-service-414915"></a><span data-ttu-id="72797-117">Üres állapotmező látható a Common Data Service szolgáltatás néhány távollétkérelmi rekordjánál (414915)</span><span class="sxs-lookup"><span data-stu-id="72797-117">Empty Status field for some leave request records in Common Data Service (414915)</span></span>

<span data-ttu-id="72797-118">A módosítással javul a Common Data Service egyik hibája, amikor a távollétkérelem **Állapot** mezőjének beállítása **Felülvizsgálat**.</span><span class="sxs-lookup"><span data-stu-id="72797-118">This change corrects an issue in Common Data Service when the **Status** field in a leave request is set to **Review**.</span></span> <span data-ttu-id="72797-119">Common Data Service most az állapotot tükrözi.</span><span class="sxs-lookup"><span data-stu-id="72797-119">Common Data Service now reflects the status.</span></span>

## <a name="skill-gap-analysis-only-possible-for-assigned-job-411390"></a><span data-ttu-id="72797-120">A szakértelem hiányelemzése csak hozzárendelt feladatnál lehetséges (411390)</span><span class="sxs-lookup"><span data-stu-id="72797-120">Skill gap analysis only possible for assigned job (411390)</span></span>

<span data-ttu-id="72797-121">Most már végrehajthatja a Human Resources szolgáltatásban meghatározott bármely feladat szakértelmi hiányelemzését.</span><span class="sxs-lookup"><span data-stu-id="72797-121">You can now do a skill gap analysis on any job defined in Human Resources.</span></span>

## <a name="system-currency-doesnt-sync-from-common-data-service-to-human-resources-in-new-environments-418011"></a><span data-ttu-id="72797-122">A rendszerpénznem nem szinkronizál a Common Data Service szolgáltatásból a Human Resources szolgáltatásba új környezetekben (418011)</span><span class="sxs-lookup"><span data-stu-id="72797-122">System currency doesn't sync from Common Data Service to Human Resources in new environments (418011)</span></span>

<span data-ttu-id="72797-123">A rendszerpénznem most már szinkronizálhat a Common Data Service szolgáltatásból a Human Resources szolgáltatásba.</span><span class="sxs-lookup"><span data-stu-id="72797-123">The system currency in Common Data Service can now sync to Human Resources.</span></span>

## <a name="in-preview"></a><span data-ttu-id="72797-124">Előnézetben</span><span class="sxs-lookup"><span data-stu-id="72797-124">In preview</span></span>

- [<span data-ttu-id="72797-125">Szabadság és távollét előzetes funkciói</span><span class="sxs-lookup"><span data-stu-id="72797-125">Leave and absence preview features</span></span>](hr-leave-and-absence-overview.md?leave-and-absence-preview-features)

- [<span data-ttu-id="72797-126">Juttatáskezelés előzetes funkciói</span><span class="sxs-lookup"><span data-stu-id="72797-126">Benefits management preview features</span></span>](hr-benefits-management-overview.md)

## <a name="coming-soon"></a><span data-ttu-id="72797-127">Hamarosan</span><span class="sxs-lookup"><span data-stu-id="72797-127">Coming soon</span></span>

### <a name="updated-common-data-service-solution"></a><span data-ttu-id="72797-128">Common Data Service megoldás frissítve</span><span class="sxs-lookup"><span data-stu-id="72797-128">Updated Common Data Service solution</span></span>

<span data-ttu-id="72797-129">Az új Common Data Service megoldás hamarosan a következő változtatásokkal érhető el:</span><span class="sxs-lookup"><span data-stu-id="72797-129">A new Common Data Service solution will be available soon with the following changes:</span></span>

| <span data-ttu-id="72797-130">Leírás</span><span class="sxs-lookup"><span data-stu-id="72797-130">Description</span></span> | <span data-ttu-id="72797-131">Visszajáró</span><span class="sxs-lookup"><span data-stu-id="72797-131">Change</span></span> |
| ----------------------------------------- | --- |
| <span data-ttu-id="72797-132">**Feladat/pozíció** entitás módosításai</span><span class="sxs-lookup"><span data-stu-id="72797-132">**Job/Position** entity changes</span></span> | <span data-ttu-id="72797-133">**Kompenzációs régió** hozzáadása</span><span class="sxs-lookup"><span data-stu-id="72797-133">**Compensation region** added</span></span></br><span data-ttu-id="72797-134">**Pénzügyi dimenziók** hozzáadása</span><span class="sxs-lookup"><span data-stu-id="72797-134">**Financial dimensions** added</span></span> |
| <span data-ttu-id="72797-135">**Dolgozó** entitás módosításai</span><span class="sxs-lookup"><span data-stu-id="72797-135">**Worker** entity changes</span></span> | <span data-ttu-id="72797-136">**Névsorrend** hozzáadása</span><span class="sxs-lookup"><span data-stu-id="72797-136">**Name sequence** added</span></span></br><span data-ttu-id="72797-137">**Otthonról dolgozik** hozzáadása</span><span class="sxs-lookup"><span data-stu-id="72797-137">**Works from home** added</span></span></br><span data-ttu-id="72797-138">**Nyelv** hozzáadása</span><span class="sxs-lookup"><span data-stu-id="72797-138">**Language** added</span></span></br><span data-ttu-id="72797-139">**Szolgálati idő dátuma** hozzáadása</span><span class="sxs-lookup"><span data-stu-id="72797-139">**Seniority date** added</span></span></br><span data-ttu-id="72797-140">**Évforduló dátuma** hozzáadása</span><span class="sxs-lookup"><span data-stu-id="72797-140">**Anniversary date** added</span></span></br><span data-ttu-id="72797-141">**Eredeti felvételi dátum** hozzáadása</span><span class="sxs-lookup"><span data-stu-id="72797-141">**Original hire date** added</span></span> |
| <span data-ttu-id="72797-142">**Foglalkoztatás** entitás módosításai</span><span class="sxs-lookup"><span data-stu-id="72797-142">**Employment** entity changes</span></span> | <span data-ttu-id="72797-143">**Pénzügyi dimenziók** hozzáadása</span><span class="sxs-lookup"><span data-stu-id="72797-143">**Financial dimensions** added</span></span></br><span data-ttu-id="72797-144">**Felmondás oka** hozzáadása</span><span class="sxs-lookup"><span data-stu-id="72797-144">**Termination reason** added</span></span></br><span data-ttu-id="72797-145">**Megszűnés dátuma** az **Áttérési dátumtól** átnevezve</span><span class="sxs-lookup"><span data-stu-id="72797-145">**Termination date** renamed from **Transition date**</span></span></br><span data-ttu-id="72797-146">**Próbaidős dátum** hozzáadása</span><span class="sxs-lookup"><span data-stu-id="72797-146">**Probation date** added</span></span> |
| <span data-ttu-id="72797-147">**Dolgozó címe** entitás módosításai</span><span class="sxs-lookup"><span data-stu-id="72797-147">**Worker address** entity changes</span></span> | <span data-ttu-id="72797-148">**Utca és házszám** hozzáadása</span><span class="sxs-lookup"><span data-stu-id="72797-148">**Street address** added</span></span></br><span data-ttu-id="72797-149">**1. címsor**, **2. címsor** és **3. címsor** megjelölve megszűnésre</span><span class="sxs-lookup"><span data-stu-id="72797-149">**Address line 1**, **Address line 2**, and **Address line 3** marked for deprecation</span></span> |
| <span data-ttu-id="72797-150">Új változó kompenzációs beállítási entitások</span><span class="sxs-lookup"><span data-stu-id="72797-150">New variable compensation setup entities</span></span> | <span data-ttu-id="72797-151">**Változó kompenzációs konstrukció típusa**</span><span class="sxs-lookup"><span data-stu-id="72797-151">**Compensation variable plan type**</span></span></br><span data-ttu-id="72797-152">**Változó kompenzációs konstrukció**</span><span class="sxs-lookup"><span data-stu-id="72797-152">**Compensation variable plan**</span></span></br><span data-ttu-id="72797-153">**Kilépési szabályok**</span><span class="sxs-lookup"><span data-stu-id="72797-153">**Vesting rules**</span></span></br><span data-ttu-id="72797-154">**Változó kompenzációs konstrukció szintje**</span><span class="sxs-lookup"><span data-stu-id="72797-154">**Compensation variable plan level**</span></span> |
| <span data-ttu-id="72797-155">Új **Dolgozói naptár – foglalkoztatás** entitás</span><span class="sxs-lookup"><span data-stu-id="72797-155">New **Worker calendar employment** entity</span></span> | <span data-ttu-id="72797-156">**Munkanaptár-entitás** hozzáadva</span><span class="sxs-lookup"><span data-stu-id="72797-156">**Work calendar entity** added</span></span> |
| <span data-ttu-id="72797-157">Új **Bérlista szerinti beosztás részletei** entitás</span><span class="sxs-lookup"><span data-stu-id="72797-157">New **Payroll position detail** entity</span></span> | <span data-ttu-id="72797-158">**Bérlista szerinti beosztás** részletei</span><span class="sxs-lookup"><span data-stu-id="72797-158">**Payroll position detail** added</span></span> |
| <span data-ttu-id="72797-159">Új **Beosztás** entitás</span><span class="sxs-lookup"><span data-stu-id="72797-159">New **Title** entity</span></span> | <span data-ttu-id="72797-160">**Beosztás** hozzáadása</span><span class="sxs-lookup"><span data-stu-id="72797-160">**Title** added.</span></span> <span data-ttu-id="72797-161">Az új **Cím** entitást a Human Resources és a Common Data Service közötti szinkronizálási folyamatában fog szerepelni.</span><span class="sxs-lookup"><span data-stu-id="72797-161">The new **Title** entity will be included in the sync process between Human Resources and Common Data Service.</span></span> <span data-ttu-id="72797-162">Kezdetben nem lesz hivatkozva a **Beosztás** vagy a **Feladat** entitásból.</span><span class="sxs-lookup"><span data-stu-id="72797-162">It won't be initially referenced from **Job Position** or **Job** entities.</span></span> |

## <a name="see-also"></a><span data-ttu-id="72797-163">Lásd még</span><span class="sxs-lookup"><span data-stu-id="72797-163">See also</span></span>

[<span data-ttu-id="72797-164">Új vagy módosult elemek a Human Resources szolgáltatásban</span><span class="sxs-lookup"><span data-stu-id="72797-164">What's new or changed in Human Resources</span></span>](hr-admin-whats-new.md)</br>
[<span data-ttu-id="72797-165">A Dynamics 365 Human Resources 2019 második kiadási hullámának áttekintése</span><span class="sxs-lookup"><span data-stu-id="72797-165">Overview of Dynamics 365 Human Resources 2019 release wave 2</span></span>](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[<span data-ttu-id="72797-166">Rendelés frissítése</span><span class="sxs-lookup"><span data-stu-id="72797-166">Update process</span></span>](hr-admin-setup-update-process.md)</br>
[<span data-ttu-id="72797-167">Szolgáltatások kezelése</span><span class="sxs-lookup"><span data-stu-id="72797-167">Manage features</span></span>](hr-admin-manage-features.md)