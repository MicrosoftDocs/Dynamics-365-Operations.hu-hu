---
title: A Dynamics 365 Human Resources új vagy módosult elemei (2020. július 23.)
description: Ez a témakör a Microsoft Dynamics 365 Human Resources új vagy módosított szolgáltatásait írja le.
author: Darinkramer
manager: AnnBe
ms.date: 07/23/2020
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
ms.search.validFrom: 2020-07-23
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: dd71ab5c48be1bec5ce2272bbff37ab10a4aed67
ms.sourcegitcommit: 81296c49be9953aa01e15527c34d0ef13b4622a9
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/22/2020
ms.locfileid: "3614410"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-july-23-2020"></a><span data-ttu-id="70c01-103">A Dynamics 365 Human Resources új vagy módosult elemei (2020. július 23.)</span><span class="sxs-lookup"><span data-stu-id="70c01-103">What's new or changed in Dynamics 365 Human Resources (July 23, 2020)</span></span>

<span data-ttu-id="70c01-104">Ez a témakör a Dynamics 365 Human Resources új vagy módosított szolgáltatásait írja le.</span><span class="sxs-lookup"><span data-stu-id="70c01-104">This topic describes features that are either new or changed in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="70c01-105">A változtatások a 8.1.3416-es buildszámra vonatkoznak.</span><span class="sxs-lookup"><span data-stu-id="70c01-105">Changes apply to build number 8.1.3416.</span></span> <span data-ttu-id="70c01-106">A néhány fejlécben látható, zárójelben lévő számok az LCS támogatási számaira vonatkoznak referenciaképpen.</span><span class="sxs-lookup"><span data-stu-id="70c01-106">The numbers in parentheses in some headings refer to LCS support numbers for reference.</span></span>

## <a name="deleting-financial-dimensions-on-a-position-doesnt-work-as-expected-445476"></a><span data-ttu-id="70c01-107">A beosztáshoz tartozó pénzügyi dimenziók törlése nem az elvártaknak megfelelően működik (445476)</span><span class="sxs-lookup"><span data-stu-id="70c01-107">Deleting Financial Dimensions on a Position doesn't work as expected (445476)</span></span>

<span data-ttu-id="70c01-108">A dimenziók beosztásból való eltávolítása ezennel eltávolítja ezeket a beosztásokat a Common Data Service-ből.</span><span class="sxs-lookup"><span data-stu-id="70c01-108">Removing dimensions from a position now removes those same positions from Common Data Service.</span></span>

## <a name="positions-not-in-hierarchy-show-inactive-positions-397257"></a><span data-ttu-id="70c01-109">A hierarchiában nem szereplő pozíciók inaktív pozíciókat mutatnak (397257)</span><span class="sxs-lookup"><span data-stu-id="70c01-109">Positions not in hierarchy show inactive positions (397257)</span></span>

<span data-ttu-id="70c01-110">Az inaktív beosztások (lejárt időtartamú) a pozícióhierarchiában már nem **Hierarchiában nem szereplő beosztások** lehetőségként jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="70c01-110">Positions that are inactive (have an expired duration), no longer display in the position hierarchy as **Positions not in hierarchy**.</span></span> 

## <a name="validation-occurring-between-leaveenrollmententity-and-hcmworkerentity-on-data-management-framework-dmf-import-causes-slow-data-loads-442324"></a><span data-ttu-id="70c01-111">Az Adatkezelési keretrendszer (DMF) importálásának LeaveEnrollmentEntity és HcmWorkerEntity közti érvényesítése lassú adatterhelést okoz (442324)</span><span class="sxs-lookup"><span data-stu-id="70c01-111">Validation occurring between LeaveEnrollmentEntity and HcmWorkerEntity on Data Management Framework (DMF) import causes slow data loads (442324)</span></span>

<span data-ttu-id="70c01-112">A kiadás módosításai növelik a **LeaveEnrollmentEntity** teljesítményét.</span><span class="sxs-lookup"><span data-stu-id="70c01-112">Changes in this release increase the performance of **LeaveEnrollmentEntity**.</span></span>

## <a name="unable-to-personalize-in-organization-administration-447490"></a><span data-ttu-id="70c01-113">Nem lehet személyre szabni a Szervezeti adminisztrációban (447490)</span><span class="sxs-lookup"><span data-stu-id="70c01-113">Unable to personalize in Organization administration (447490)</span></span>

<span data-ttu-id="70c01-114">Ezzel a módosítással testreszabhatja a **Szervezeti adminisztráció** hivatkozásait.</span><span class="sxs-lookup"><span data-stu-id="70c01-114">With this change, you can now personalize the links in **Organization administration**.</span></span>

## <a name="in-preview"></a><span data-ttu-id="70c01-115">Előnézetben</span><span class="sxs-lookup"><span data-stu-id="70c01-115">In preview</span></span>

## <a name="mandatory-fields"></a><span data-ttu-id="70c01-116">Kötelező mezők</span><span class="sxs-lookup"><span data-stu-id="70c01-116">Mandatory fields</span></span> 

<span data-ttu-id="70c01-117">Most már kötelezővé teheti a mezőket a Human Resources személyre szabási funkcióival.</span><span class="sxs-lookup"><span data-stu-id="70c01-117">You can now make fields mandatory by using Human Resources personalization capabilities.</span></span> <span data-ttu-id="70c01-118">Ehhez a funkcióhoz **Mentett nézetek** szükségesek.</span><span class="sxs-lookup"><span data-stu-id="70c01-118">This feature requires **Saved views**.</span></span>

## <a name="human-resources-application-in-teams"></a><span data-ttu-id="70c01-119">Human Resources alkalmazás a Teamsben</span><span class="sxs-lookup"><span data-stu-id="70c01-119">Human Resources application in Teams</span></span>

<span data-ttu-id="70c01-120">Az alkalmazottak megtekinthetik és kérhetik a munkából való távollétet a Microsoft Teams alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="70c01-120">Employees can view and request time away from work within Microsoft Teams.</span></span> <span data-ttu-id="70c01-121">Ezek egy robottal lépnek interakcióba a szabadságkérelmek létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="70c01-121">They can interact with a bot to create leave requests.</span></span> <span data-ttu-id="70c01-122">További tájékoztatás: [Human Resources alkalmazás a Teamsben](https://go.microsoft.com/fwlink/?linkid=2127841).</span><span class="sxs-lookup"><span data-stu-id="70c01-122">For more information, see [Human Resources app in Teams](https://go.microsoft.com/fwlink/?linkid=2127841).</span></span> 

## <a name="data-management-framework-dmf-entities-for-benefits-management"></a><span data-ttu-id="70c01-123">Az adatkezelési keretrendszer (DMF) entitásai a juttatások kezeléséhez</span><span class="sxs-lookup"><span data-stu-id="70c01-123">Data management framework (DMF) entities for Benefits management</span></span>
 
<span data-ttu-id="70c01-124">A juttatások kezelése entitások kiadnak.</span><span class="sxs-lookup"><span data-stu-id="70c01-124">Benefits management entities are releasing.</span></span> <span data-ttu-id="70c01-125">A DMF entitások lehetővé teszik az adatok importálását és exportálását a juttatáskezelés egyszerű konfigurálásához.</span><span class="sxs-lookup"><span data-stu-id="70c01-125">DMF entities allow you to import and export data to easily configure benefits management.</span></span> <span data-ttu-id="70c01-126">A juttatáskezelési sablon az adatok áthelyezésére elérhető lesz.</span><span class="sxs-lookup"><span data-stu-id="70c01-126">A Benefits management template will be available to move data.</span></span> <span data-ttu-id="70c01-127">A sablon egymást követően exportálja és importálja az adatokat az adatfüggőségek tiszteletben tartásához.</span><span class="sxs-lookup"><span data-stu-id="70c01-127">The template exports and imports the data sequentially to respect data dependencies.</span></span>

## <a name="buy-and-sell-leave"></a><span data-ttu-id="70c01-128">Szabadság vásárlása és eladása</span><span class="sxs-lookup"><span data-stu-id="70c01-128">Buy and sell leave</span></span> 

<span data-ttu-id="70c01-129">Néhány szervezet olyan juttatást biztosít, amely lehetővé teszi az alkalmazottak számára, hogy megvásárolják vagy eladják a szabadságukat.</span><span class="sxs-lookup"><span data-stu-id="70c01-129">Some organizations provide a benefit that allows employees to buy or sell their leave.</span></span> <span data-ttu-id="70c01-130">Ezt a folyamatot gyakran manuálisan kell kezelni.</span><span class="sxs-lookup"><span data-stu-id="70c01-130">This process is often managed manually.</span></span> <span data-ttu-id="70c01-131">Ez a funkció automatizálja a HR osztályhoz tartozó kezelési házirendek és kérelmek kezelését.</span><span class="sxs-lookup"><span data-stu-id="70c01-131">This feature automates managing policies and requests for the HR department.</span></span> <span data-ttu-id="70c01-132">Racionalizálja a szabadság-kezelési folyamatot, és segít kiküszöbölni a hibákat.</span><span class="sxs-lookup"><span data-stu-id="70c01-132">It streamlines the leave management process and helps eliminate mistakes.</span></span> <span data-ttu-id="70c01-133">További tájékoztatás:</span><span class="sxs-lookup"><span data-stu-id="70c01-133">For more information, see:</span></span>

- [<span data-ttu-id="70c01-134">Szabadság vásárlásával és eladásával kapcsolatos irányelv kezelése</span><span class="sxs-lookup"><span data-stu-id="70c01-134">Manage buy and sell leave policies</span></span>](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)
- [<span data-ttu-id="70c01-135">Szabadság vásárlása és eladása</span><span class="sxs-lookup"><span data-stu-id="70c01-135">Buy and sell leave</span></span>](hr-employee-self-service-buy-sell-leave.md)

## <a name="leave-accrual-for-a-single-company-or-single-plan"></a><span data-ttu-id="70c01-136">Szabadság elhatárolása egyetlen vállalat vagy egy terv esetében</span><span class="sxs-lookup"><span data-stu-id="70c01-136">Leave accrual for a single company or single plan</span></span>

<span data-ttu-id="70c01-137">A vevők az elhatárolást egyetlen vállalatra vagy egyetlen szabadságtervhez is feldolgozhatják.</span><span class="sxs-lookup"><span data-stu-id="70c01-137">Customers can process accruals for a single company or a single leave and absence plan.</span></span> <span data-ttu-id="70c01-138">Ez a képesség tisztává teszi az elhatárolási folyamatot a különböző szabadságévekkel rendelkező vagy elhatárolási házirendekkel rendelkező vevők esetében.</span><span class="sxs-lookup"><span data-stu-id="70c01-138">This ability provides clarity for the accrual process for customers with different leave years or leaves accrual policies.</span></span> <span data-ttu-id="70c01-139">A további tudnivalókat lásd: [Szabadság elhatárolása vállalatonként vagy szabadság tervenként](hr-leave-and-absence-accrue.md#accrue-leave-per-company-or-per-leave-plan).</span><span class="sxs-lookup"><span data-stu-id="70c01-139">For more information, see [Accrue leave per company or per leave plan](hr-leave-and-absence-accrue.md#accrue-leave-per-company-or-per-leave-plan).</span></span>

## <a name="add-attachments-to-time-off-requests"></a><span data-ttu-id="70c01-140">Mellékletek hozzáadása szabadságkérelmekhez</span><span class="sxs-lookup"><span data-stu-id="70c01-140">Add attachments to time-off requests</span></span>

<span data-ttu-id="70c01-141">A jóváhagyott szabadságkérelmekhez tartozó mellékletek hozzáadásának lehetősége kritikus az aktuális COVID-19-környezetben.</span><span class="sxs-lookup"><span data-stu-id="70c01-141">The ability to add attachments to approved leave requests is critical in the current COVID-19 environment.</span></span> <span data-ttu-id="70c01-142">Az alkalmazottak ezután hozzáadhatják ezeket a mellékleteket.</span><span class="sxs-lookup"><span data-stu-id="70c01-142">Employees can now add these attachments.</span></span> <span data-ttu-id="70c01-143">Ők is nagyobb betekintést kapnak a szabadságkérelmek frissítései tekintetében.</span><span class="sxs-lookup"><span data-stu-id="70c01-143">They also have more insight into how updates are made to leave requests.</span></span> <span data-ttu-id="70c01-144">A további tudnivalókat lásd: [Melléklet hozzáadása meglévő kérelemhez](hr-employee-self-service-request-time-off.md#add-an-attachment-to-an-existing-request).</span><span class="sxs-lookup"><span data-stu-id="70c01-144">For more information, see [Add an attachment to an existing request](hr-employee-self-service-request-time-off.md#add-an-attachment-to-an-existing-request).</span></span>

## <a name="add-reason-code-to-accrual-suspensions"></a><span data-ttu-id="70c01-145">Okkódhozzáadása az elhatárolás-felfüggesztésekhez</span><span class="sxs-lookup"><span data-stu-id="70c01-145">Add reason code to accrual suspensions</span></span> 

<span data-ttu-id="70c01-146">Okkódok kerültek hozzáadásra az elhatárolás-felfüggesztéshez.</span><span class="sxs-lookup"><span data-stu-id="70c01-146">Reason codes have been added to the accrual suspension.</span></span>

## <a name="carry-forward-rules"></a><span data-ttu-id="70c01-147">Átvitel szabályai</span><span class="sxs-lookup"><span data-stu-id="70c01-147">Carry forward rules</span></span> 

<span data-ttu-id="70c01-148">Megadhatja, hogy az átviteli szabadságtípust az átviteli egyenlegekhez, ahová az átviteli korrekciók ár lesznek helyezve.</span><span class="sxs-lookup"><span data-stu-id="70c01-148">You can specify a carry forward leave type for carry forward balances where carry forward adjustments are transferred.</span></span> <span data-ttu-id="70c01-149">Ha például egy alkalmazott 10 napot visz át, akkor a 10 napnál más szabadság-típust is kiválaszthat.</span><span class="sxs-lookup"><span data-stu-id="70c01-149">For example, if an employee carries forward 10 days, you can pick a different leave type for those 10 days.</span></span> <span data-ttu-id="70c01-150">További tájékoztatás: [Szabadság és távolléti típusok konfigurálása](hr-leave-and-absence-types.md).</span><span class="sxs-lookup"><span data-stu-id="70c01-150">For more information, see [Configure leave and absence types](hr-leave-and-absence-types.md).</span></span>

## <a name="suspend-leave-accrual-for-specified-leave-types"></a><span data-ttu-id="70c01-151">Felfüggeszti a távollét elhatárolását a megadott szabadság-típusokhoz</span><span class="sxs-lookup"><span data-stu-id="70c01-151">Suspend leave accrual for specified leave types</span></span>

<span data-ttu-id="70c01-152">Olyan szabályt hozhat létre, amely felfüggeszti a távolléti elhatárolásokat a fizetés nélküli szabadságokhoz megadott szabadságkérelmekhez.</span><span class="sxs-lookup"><span data-stu-id="70c01-152">You can create a rule to suspend leave accruals for employees with leave requests entered for unpaid leave.</span></span> <span data-ttu-id="70c01-153">A fizetetlen szabadság lehet egy típus, de ez nem kötelező.</span><span class="sxs-lookup"><span data-stu-id="70c01-153">Unpaid leave can be a type, but doesn't have to be.</span></span> <span data-ttu-id="70c01-154">Bármilyen szabadságot egy másik szabadság típus alapján fel lehet függeszteni.</span><span class="sxs-lookup"><span data-stu-id="70c01-154">You can suspend any leave based on another leave type.</span></span>

## <a name="dmf-entity-available-for-accrual-suspensions"></a><span data-ttu-id="70c01-155">A DMF entitás elérhető az elhatárolás-felfüggesztésekhez</span><span class="sxs-lookup"><span data-stu-id="70c01-155">DMF entity available for accrual suspensions</span></span> 

<span data-ttu-id="70c01-156">A DMF entitás immár elérhető az elhatárolás-felfüggesztésekhez.</span><span class="sxs-lookup"><span data-stu-id="70c01-156">A DMF entity is now available for accrual suspensions.</span></span>

## <a name="coming-soon"></a><span data-ttu-id="70c01-157">Hamarosan</span><span class="sxs-lookup"><span data-stu-id="70c01-157">Coming soon</span></span>

## <a name="checklist-entities-included-in-common-data-service"></a><span data-ttu-id="70c01-158">Ellenőrzőlista-entitások szerepelnek a következőben: Common Data Service</span><span class="sxs-lookup"><span data-stu-id="70c01-158">Checklist entities included in Common Data Service</span></span>

<span data-ttu-id="70c01-159">Az Előkészítés, Felszámolás, Áthelyezések és Üzleti folyamatok hamarosan elérhetők lesznek a Common Data Service alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="70c01-159">Checklist entities for Onboarding, Offboarding, Transfers, and Business processes will be available soon in Common Data Service.</span></span>

## <a name="platform-changes"></a><span data-ttu-id="70c01-160">Platformok módosításai</span><span class="sxs-lookup"><span data-stu-id="70c01-160">Platform changes</span></span>

<span data-ttu-id="70c01-161">Platform frissítése erre: 10.0.12 (36)</span><span class="sxs-lookup"><span data-stu-id="70c01-161">Platform update 10.0.12 (36)</span></span>

## <a name="see-also"></a><span data-ttu-id="70c01-162">Lásd még</span><span class="sxs-lookup"><span data-stu-id="70c01-162">See also</span></span>

[<span data-ttu-id="70c01-163">Új vagy módosult elemek a Human Resources szolgáltatásban</span><span class="sxs-lookup"><span data-stu-id="70c01-163">What's new or changed in Human Resources</span></span>](hr-admin-whats-new.md)</br>
[<span data-ttu-id="70c01-164">A Dynamics 365 Human Resources 2019 második kiadási hullámának áttekintése</span><span class="sxs-lookup"><span data-stu-id="70c01-164">Overview of Dynamics 365 Human Resources 2019 release wave 2</span></span>](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[<span data-ttu-id="70c01-165">Rendelés frissítése</span><span class="sxs-lookup"><span data-stu-id="70c01-165">Update process</span></span>](hr-admin-setup-update-process.md)</br>
[<span data-ttu-id="70c01-166">Szolgáltatások kezelése</span><span class="sxs-lookup"><span data-stu-id="70c01-166">Manage features</span></span>](hr-admin-manage-features.md)
