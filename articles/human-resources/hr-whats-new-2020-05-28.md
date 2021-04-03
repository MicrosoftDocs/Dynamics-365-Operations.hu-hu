---
title: Új vagy módosult elemek a Dynamics 365 Human Resources szolgáltatásban (2020. május 28.)
description: Ez a témakör a Microsoft Dynamics 365 Human Resources új vagy módosított szolgáltatásait írja le a 2020. május 28-i kiadásban.
author: andreabichsel
manager: tfehr
ms.date: 05/28/2020
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
ms.author: jaredha
ms.search.validFrom: 2020-05-28
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 8e8d7f87f30286eefa1b3b53925702f4735132e6
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/17/2021
ms.locfileid: "5465270"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-may-28-2020"></a><span data-ttu-id="7de0e-103">Új vagy módosult elemek a Dynamics 365 Human Resources szolgáltatásban (2020. május 28.)</span><span class="sxs-lookup"><span data-stu-id="7de0e-103">What's new or changed in Dynamics 365 Human Resources (May 28, 2020)</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="7de0e-104">Ez a témakör a Dynamics 365 Human Resources új vagy módosított szolgáltatásait írja le.</span><span class="sxs-lookup"><span data-stu-id="7de0e-104">This topic describes features that are either new or changed in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="7de0e-105">A változtatások a 8.1.3287-es buildszámra vonatkoznak.</span><span class="sxs-lookup"><span data-stu-id="7de0e-105">Changes apply to build number 8.1.3287.</span></span> <span data-ttu-id="7de0e-106">A néhány fejlécben látható, zárójelben lévő számok az LCS támogatási számaira vonatkoznak referenciaképpen.</span><span class="sxs-lookup"><span data-stu-id="7de0e-106">The numbers in parentheses in some headings refer to LCS support numbers for reference.</span></span>

## <a name="leaverequest-entity-doesnt-work-when-you-enable-multiple-types-per-leave-plan-447498"></a><span data-ttu-id="7de0e-107">A LeaveRequest entitás nem működik, ha szabadságtervenként több típust engedélyez (447498)</span><span class="sxs-lookup"><span data-stu-id="7de0e-107">LeaveRequest entity doesn't work when you enable multiple types per leave plan (447498)</span></span>

<span data-ttu-id="7de0e-108">Ezzel a módosítással a **LeaveEnrollmentV2Entity** elérhetővé válik, hogy kijavítsa a különböző típusú szabadságok engedélyezésekor jelentkező hibát.</span><span class="sxs-lookup"><span data-stu-id="7de0e-108">With this change, the **LeaveEnrollmentV2Entity** is now available to correct the error that occurs when you enable multiple leave types.</span></span>

## <a name="batch-contention-reduction-feature-preview-446619"></a><span data-ttu-id="7de0e-109">Kötegtartalom-csökkentési funkció (előzetes verzió) (446619)</span><span class="sxs-lookup"><span data-stu-id="7de0e-109">Batch contention reduction feature (preview) (446619)</span></span>

<span data-ttu-id="7de0e-110">Ha engedélyezi ezt a funkciót, akkor a feladatok és a befejező feladatok kiválasztásakor várhatóan csökkenhet a kötegkeretrendszer tábláinak zárolása.</span><span class="sxs-lookup"><span data-stu-id="7de0e-110">When you enable this feature, you can expect a reduction in blocking on batch framework tables while selecting tasks and finishing jobs.</span></span>

## <a name="updateconflict-while-saving-worker-prevents-editing-a-record-in-people-427915"></a><span data-ttu-id="7de0e-111">Az UpdateConflict a dolgozó mentésekor megakadályozza egy rekord szerkesztését a személyeknél (427915)</span><span class="sxs-lookup"><span data-stu-id="7de0e-111">UpdateConflict while saving worker prevents editing a record in People (427915)</span></span>

<span data-ttu-id="7de0e-112">A módosítás kijavítja a hibát, ami egy új dolgozó hozzáadásakor, a címadatok frissítésekor és a nyelvi beállítások módosításakor jelentkezik.</span><span class="sxs-lookup"><span data-stu-id="7de0e-112">This change corrects an error when adding a new worker, updating address information, and changing language preference.</span></span> <span data-ttu-id="7de0e-113">Ebben az egyedi esetben egy hibaüzenet jelenik meg, amely jelzi, hogy a rekord nem frissíthető.</span><span class="sxs-lookup"><span data-stu-id="7de0e-113">In this unique scenario, an error displayed indicating the record couldn't be updated.</span></span> 

## <a name="unable-to-add-an-attachment-to-an-approved-leave-request-to-resubmit-425407"></a><span data-ttu-id="7de0e-114">Nem adható hozzá melléklet egy jóváhagyott szabadságkérelemhez az újraküldéshez (425407)</span><span class="sxs-lookup"><span data-stu-id="7de0e-114">Unable to add an attachment to an approved leave request to resubmit (425407)</span></span>

<span data-ttu-id="7de0e-115">Ez a változtatás most már lehetővé teszi mellékletek csatolását a jóváhagyott szabadságkérelmekhez.</span><span class="sxs-lookup"><span data-stu-id="7de0e-115">This change now allows attachments to approved leave requests.</span></span>

## <a name="user-can-enter-compensation-for-an-employee-in-a-different-legal-entity-form-409529"></a><span data-ttu-id="7de0e-116">A felhasználó megadhatja az alkalmazott kompenzációját másik jogi személy űrlapján (409529).</span><span class="sxs-lookup"><span data-stu-id="7de0e-116">User can enter compensation for an employee in a different legal entity form (409529)</span></span>

<span data-ttu-id="7de0e-117">A módosítás letiltja a kompenzációs beállításokat a nem megfelelő jogi személyre vonatkozó kompenzációs rekordok véletlen bevitelének megakadályozására.</span><span class="sxs-lookup"><span data-stu-id="7de0e-117">This change disables compensation options to prevent inadvertent entry of compensation records for the wrong legal entity.</span></span>

## <a name="error-when-you-transfer-an-employee-and-the-worker-position-assignment-date-is-before-the-position-duration-429402"></a><span data-ttu-id="7de0e-118">Hiba történik, amikor egy alkalmazottat visz át, és a dolgozó beosztásának hozzárendelési dátuma a beosztás időtartama előtt van (429402)</span><span class="sxs-lookup"><span data-stu-id="7de0e-118">Error when you transfer an employee and the Worker position assignment date is before the position duration (429402)</span></span>

<span data-ttu-id="7de0e-119">Az ebben a helyzetben az alkalmazott átvitelekor adott hibaüzenetek frissítve lettek, hogy jobban leírják a probléma javításához szükséges módosításokat.</span><span class="sxs-lookup"><span data-stu-id="7de0e-119">Error messages when transferring an employee in this scenario have been updated to better describe the changes needed to correct the problem.</span></span>

## <a name="attachments-capabilities-in-employee-self-service-benefits-enrollment"></a><span data-ttu-id="7de0e-120">Az alkalmazotti önkiszolgálói juttatások jelentkezésének mellékletcsatolási lehetőségei</span><span class="sxs-lookup"><span data-stu-id="7de0e-120">Attachments capabilities in Employee self service benefits enrollment</span></span>
 
<span data-ttu-id="7de0e-121">Most már hozzáadhat mellékleteket a juttatások jelentkezési folyamata során minden olyan csomaghoz, amelyre az alkalmazott jelentkezik.</span><span class="sxs-lookup"><span data-stu-id="7de0e-121">Now you can add attachments during the benefits enrollment process for each plan that the employee's enrolling in.</span></span> <span data-ttu-id="7de0e-122">Ezt követően megtekintheti a **dolgozó regisztrált juttatásai** űrlap mellékleteit.</span><span class="sxs-lookup"><span data-stu-id="7de0e-122">You can then view the attachments within the **Worker enrolled benefit** form.</span></span>

## <a name="in-preview"></a><span data-ttu-id="7de0e-123">Előnézetben</span><span class="sxs-lookup"><span data-stu-id="7de0e-123">In preview</span></span>

## <a name="human-resources-application-in-teams"></a><span data-ttu-id="7de0e-124">Human Resources alkalmazás a Teamsben</span><span class="sxs-lookup"><span data-stu-id="7de0e-124">Human Resources application in Teams</span></span>

<span data-ttu-id="7de0e-125">Az alkalmazottak megtekinthetik és kérhetik a munkából való távollétet a Microsoft Teams alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="7de0e-125">Employees can view and request time away from work within Microsoft Teams.</span></span> <span data-ttu-id="7de0e-126">Ezek egy robottal lépnek interakcióba a szabadságkérelmek létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="7de0e-126">They can interact with a bot to create leave requests.</span></span> <span data-ttu-id="7de0e-127">További tájékoztatás: [Human Resources alkalmazás a Teamsben](https://go.microsoft.com/fwlink/?linkid=2127841).</span><span class="sxs-lookup"><span data-stu-id="7de0e-127">For more information, see [Human Resources app in Teams](https://go.microsoft.com/fwlink/?linkid=2127841).</span></span> 

## <a name="leave-suspension"></a><span data-ttu-id="7de0e-128">Szabadság felfüggesztése</span><span class="sxs-lookup"><span data-stu-id="7de0e-128">Leave suspension</span></span>

<span data-ttu-id="7de0e-129">Egy alkalmazottra vonatkozóan felfüggesztheti a szabadságokat és a távollétet.</span><span class="sxs-lookup"><span data-stu-id="7de0e-129">You can suspend leave and absence in Human Resources for an employee.</span></span> <span data-ttu-id="7de0e-130">A szabadság felfüggesztése kiválasztott távolléti típusoknál leállítja az elhatárolást.</span><span class="sxs-lookup"><span data-stu-id="7de0e-130">Suspending leave stops the leave accruals for selected leave types.</span></span> <span data-ttu-id="7de0e-131">Ha a felfüggesztés a könyvelés feldolgozását követően következik be, akkor a szabadság felfüggesztése az alkalmazott szabadságának egyenlegéhez egy arányosan korrigált kiigazítást hoz létre.</span><span class="sxs-lookup"><span data-stu-id="7de0e-131">If the suspension occurs after an accrual has been processed, suspending leave creates a prorated adjustment to the employee's leave balance.</span></span> <span data-ttu-id="7de0e-132">További információ: [Szabadság felfüggesztése](hr-leave-and-absence-suspend-leave.md).</span><span class="sxs-lookup"><span data-stu-id="7de0e-132">For more information, see [Suspend leave](hr-leave-and-absence-suspend-leave.md).</span></span>

## <a name="update-user-experience-to-indicate-that-accrual-is-suspended-429550"></a><span data-ttu-id="7de0e-133">Felhasználói élmény frissítése annak jelzésére, hogy az elhatárolás fel van függesztve (429550)</span><span class="sxs-lookup"><span data-stu-id="7de0e-133">Update user experience to indicate that accrual is suspended (429550)</span></span>

<span data-ttu-id="7de0e-134">A felhasználói élmény immár jelzi, hogy az elhatárolás fel van függesztve egy tervhez.</span><span class="sxs-lookup"><span data-stu-id="7de0e-134">The user experience now indicates that the accrual has been suspended for a plan.</span></span>

## <a name="coming-soon"></a><span data-ttu-id="7de0e-135">Hamarosan</span><span class="sxs-lookup"><span data-stu-id="7de0e-135">Coming soon</span></span>

## <a name="database-logging-in-preview-in-june"></a><span data-ttu-id="7de0e-136">Adatbázis naplózása (júniusban előzetes verzióban)</span><span class="sxs-lookup"><span data-stu-id="7de0e-136">Database logging (in preview in June)</span></span>

<span data-ttu-id="7de0e-137">Az adatbázis-naplózási funkció segítségével meghatározhatja, hogy mely táblákat és mezőket kell figyelni.</span><span class="sxs-lookup"><span data-stu-id="7de0e-137">The database logging feature allows you to determine which table and fields should be monitored.</span></span> <span data-ttu-id="7de0e-138">Azt is lehetővé teszi, hogy meghatározza a változáskövetést igénylő eseményeket.</span><span class="sxs-lookup"><span data-stu-id="7de0e-138">It also lets you determine the events that should trigger change tracking.</span></span> <span data-ttu-id="7de0e-139">A lekérdezési lehetőségekkel ezek a változások az idő függvényében megtekinthetők.</span><span class="sxs-lookup"><span data-stu-id="7de0e-139">Inquiry capabilities are available to see these changes over time.</span></span>

## <a name="buy-and-sell-leave-in-preview-june-1"></a><span data-ttu-id="7de0e-140">Szabadság eladása és vásárlása (a június 1-jei előzetes verzióban)</span><span class="sxs-lookup"><span data-stu-id="7de0e-140">Buy and sell leave (in preview June 1)</span></span>

<span data-ttu-id="7de0e-141">Néhány szervezet olyan juttatást biztosít, amely lehetővé teszi az alkalmazottak számára, hogy megvásárolják vagy eladják a szabadságukat.</span><span class="sxs-lookup"><span data-stu-id="7de0e-141">Some organizations provide a benefit that allows employees to buy or sell their leave.</span></span> <span data-ttu-id="7de0e-142">Ezt a folyamatot gyakran manuálisan kell kezelni.</span><span class="sxs-lookup"><span data-stu-id="7de0e-142">This process is often managed manually.</span></span> <span data-ttu-id="7de0e-143">Ez a funkció automatizálja a HR részleg házirendjeinek és kéréseinek kezelését, valamint segít kiküszöbölni a hibákat a szabadságkezelési folyamat racionalizálása során.</span><span class="sxs-lookup"><span data-stu-id="7de0e-143">This feature provides a more automated way to manage policies and requests for the HR department, and it helps eliminate mistakes while streamlining the leave management process.</span></span> <span data-ttu-id="7de0e-144">További tájékoztatás:</span><span class="sxs-lookup"><span data-stu-id="7de0e-144">For more information, see:</span></span>

- [<span data-ttu-id="7de0e-145">Szabadság vásárlásával és eladásával kapcsolatos irányelv kezelése</span><span class="sxs-lookup"><span data-stu-id="7de0e-145">Manage buy and sell leave policies</span></span>](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)
- [<span data-ttu-id="7de0e-146">Szabadság vásárlása és eladása</span><span class="sxs-lookup"><span data-stu-id="7de0e-146">Buy and sell leave</span></span>](hr-employee-self-service-buy-sell-leave.md)

## <a name="data-management-framework-dmf-entities-for-benefits-management"></a><span data-ttu-id="7de0e-147">Az adatkezelési keretrendszer (DMF) entitásai a juttatások kezeléséhez</span><span class="sxs-lookup"><span data-stu-id="7de0e-147">Data management framework (DMF) entities for Benefits management</span></span>
 
<span data-ttu-id="7de0e-148">A juttatások kezelése entitások kiadnak.</span><span class="sxs-lookup"><span data-stu-id="7de0e-148">Benefits management entities are releasing.</span></span> <span data-ttu-id="7de0e-149">A DMF entitások lehetővé teszik az adatok importálását és exportálását a juttatáskezelés egyszerű konfigurálásához.</span><span class="sxs-lookup"><span data-stu-id="7de0e-149">DMF entities allow importing and exporting data to easily configure benefits management.</span></span> <span data-ttu-id="7de0e-150">A juttatáskezelési sablon az adatok áthelyezésére is elérhető lesz.</span><span class="sxs-lookup"><span data-stu-id="7de0e-150">A Benefits management template will also be available to move data.</span></span> <span data-ttu-id="7de0e-151">A sablon egymást követő módon exportálja és importálja az adatokat az adatfüggőségek tiszteletben tartásához.</span><span class="sxs-lookup"><span data-stu-id="7de0e-151">The template exports and imports the data in a sequential manner to respect data dependencies.</span></span>

## <a name="add-reason-code-to-accrual-suspensions-june-1"></a><span data-ttu-id="7de0e-152">Okkód hozzáadása az elhatárolás-felfüggesztésekhez (június 1.)</span><span class="sxs-lookup"><span data-stu-id="7de0e-152">Add reason code to accrual suspensions (June 1)</span></span>

<span data-ttu-id="7de0e-153">Okkódok kerültek hozzáadásra az elhatárolás-felfüggesztéshez.</span><span class="sxs-lookup"><span data-stu-id="7de0e-153">Reason codes have been added to the accrual suspension.</span></span>

## <a name="carry-forward-rules-june-1"></a><span data-ttu-id="7de0e-154">Átvitel/áthozat szabályai (június 1.)</span><span class="sxs-lookup"><span data-stu-id="7de0e-154">Carry forward rules (June 1)</span></span>

<span data-ttu-id="7de0e-155">Megadhatja, hogy az átviteli szabadságtípust az átviteli egyenlegekhez, ahová az átviteli korrekciók ár lesznek helyezve.</span><span class="sxs-lookup"><span data-stu-id="7de0e-155">You can specify a carry forward leave type for carry forward balances where carry forward adjustments are transferred.</span></span> <span data-ttu-id="7de0e-156">Ha például egy alkalmazott 10 napot visz át, akkor a 10 napnál más szabadság-típust is kiválaszthat.</span><span class="sxs-lookup"><span data-stu-id="7de0e-156">For example, if an employee carries forward 10 days, you can pick a different leave type for those 10 days.</span></span> <span data-ttu-id="7de0e-157">További tájékoztatás: [Szabadság és távolléti típusok konfigurálása](hr-leave-and-absence-types.md).</span><span class="sxs-lookup"><span data-stu-id="7de0e-157">For more information, see [Configure leave and absence types](hr-leave-and-absence-types.md).</span></span>

## <a name="suspend-leave-accrual-for-specified-leave-types-june-1"></a><span data-ttu-id="7de0e-158">Felfüggeszti a távollét elhatárolását a megadott szabadságtípusokhoz (június 1.)</span><span class="sxs-lookup"><span data-stu-id="7de0e-158">Suspend leave accrual for specified leave types (June 1)</span></span>

<span data-ttu-id="7de0e-159">Ebben a kiadásban a HR olyan szabályt hozhat létre, amely felfüggeszti a távolléti elhatárolásokat a fizetés nélküli szabadságokhoz megadott szabadságkérelmekhez.</span><span class="sxs-lookup"><span data-stu-id="7de0e-159">In this release, HR can create a rule to suspend leave accruals for employees with leave requests entered for unpaid leave.</span></span> <span data-ttu-id="7de0e-160">A fizetetlen szabadság lehet egy típus, de ez nem kötelező.</span><span class="sxs-lookup"><span data-stu-id="7de0e-160">Unpaid leave can be a type, but doesn't have to be.</span></span> <span data-ttu-id="7de0e-161">Bármilyen szabadságot egy másik szabadság típus alapján fel lehet függeszteni.</span><span class="sxs-lookup"><span data-stu-id="7de0e-161">You can suspend any leave based on another leave type.</span></span>

## <a name="dmf-entity-available-for-accrual-suspensions-june-1"></a><span data-ttu-id="7de0e-162">A DMF entitás elérhető az elhatárolásfelfüggesztésekhez (június 1.)</span><span class="sxs-lookup"><span data-stu-id="7de0e-162">DMF entity available for accrual suspensions (June 1)</span></span>

<span data-ttu-id="7de0e-163">A DMF entitás immár elérhető az elhatárolás-felfüggesztésekhez.</span><span class="sxs-lookup"><span data-stu-id="7de0e-163">A DMF entity is now available for accrual suspensions.</span></span>

## <a name="see-also"></a><span data-ttu-id="7de0e-164">Lásd még</span><span class="sxs-lookup"><span data-stu-id="7de0e-164">See also</span></span>

[<span data-ttu-id="7de0e-165">Új vagy módosult elemek a Human Resources szolgáltatásban</span><span class="sxs-lookup"><span data-stu-id="7de0e-165">What's new or changed in Human Resources</span></span>](hr-admin-whats-new.md)</br>
[<span data-ttu-id="7de0e-166">A Dynamics 365 Human Resources 2019 második kiadási hullámának áttekintése</span><span class="sxs-lookup"><span data-stu-id="7de0e-166">Overview of Dynamics 365 Human Resources 2019 release wave 2</span></span>](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[<span data-ttu-id="7de0e-167">Rendelés frissítése</span><span class="sxs-lookup"><span data-stu-id="7de0e-167">Update process</span></span>](hr-admin-setup-update-process.md)</br>
[<span data-ttu-id="7de0e-168">Szolgáltatások kezelése</span><span class="sxs-lookup"><span data-stu-id="7de0e-168">Manage features</span></span>](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]