---
title: A Dynamics 365 Human Resources új és módosult elemei (2020. június 11.)
description: Ez a témakör a Microsoft Dynamics 365 Human Resources új vagy módosított szolgáltatásait írja le a 2020. június 11-i kiadásban.
author: andreabichsel
ms.date: 06/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-06-11
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e6b0bb1c6d00cdd816534caddd83a71f2f0a3cc3
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/18/2021
ms.locfileid: "6054308"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-june-11-2020"></a><span data-ttu-id="e7d48-103">A Dynamics 365 Human Resources új és módosult elemei (2020. június 11.)</span><span class="sxs-lookup"><span data-stu-id="e7d48-103">What's new or changed in Dynamics 365 Human Resources (June 11, 2020)</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="e7d48-104">Ez a cikk a Dynamics 365 Human Resources szolgáltatásban található új vagy módosított funkciókat írja le.</span><span class="sxs-lookup"><span data-stu-id="e7d48-104">This article describes features that are either new or changed in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="e7d48-105">A változtatások a 8.1.3316-es buildszámra vonatkoznak.</span><span class="sxs-lookup"><span data-stu-id="e7d48-105">Changes apply to build number 8.1.3316.</span></span> <span data-ttu-id="e7d48-106">A néhány fejlécben látható, zárójelben lévő számok az LCS támogatási számaira vonatkoznak referenciaképpen.</span><span class="sxs-lookup"><span data-stu-id="e7d48-106">The numbers in parentheses in some headings refer to LCS support numbers for reference.</span></span>

## <a name="streamlined-employee-form-sometimes-causes-child-form-close-x-buttons-to-stop-working-442369"></a><span data-ttu-id="e7d48-107">Az egyszerűsített alkalmazotti képernyő néha a gyermek képernyő bezárás (X) gombjainak működésképtelenségét okozza (442369)</span><span class="sxs-lookup"><span data-stu-id="e7d48-107">Streamlined employee form sometimes causes child form close (X) buttons to stop working (442369)</span></span>

<span data-ttu-id="e7d48-108">Amikor az új **Dolgozó** képernyő engedélyezve van, a bezárás (**X**) gomb esetenként nem működött a gyermek képernyőkön.</span><span class="sxs-lookup"><span data-stu-id="e7d48-108">When the new **Worker** form was enabled, the close (**X**) button occasionally didn't work on child forms.</span></span> <span data-ttu-id="e7d48-109">Ez a probléma szakaszosan jelentkezett.</span><span class="sxs-lookup"><span data-stu-id="e7d48-109">This problem was intermittent.</span></span> <span data-ttu-id="e7d48-110">Ha elnavigált onnan, majd visszalépett oda be lehetett zárni a képernyőt.</span><span class="sxs-lookup"><span data-stu-id="e7d48-110">You could close the form after leaving and coming back to it.</span></span> <span data-ttu-id="e7d48-111">Kiválaszthatta például egy menüparancsot a bal oldalon, majd visszatérhetett a **Dolgozó** képernyőre, majd bezárhatta azt.</span><span class="sxs-lookup"><span data-stu-id="e7d48-111">For example, you could select a menu item on the left, and navigate back to the **Worker** form, and then close it.</span></span> <span data-ttu-id="e7d48-112">Az eheti kiadás kijavítja ezt a problémát.</span><span class="sxs-lookup"><span data-stu-id="e7d48-112">This week's release fixes this problem.</span></span> 

## <a name="the-worker-personal-contact-person-entity-doesnt-export-personal-contacts-with-a-parent-relationship-type"></a><span data-ttu-id="e7d48-113">A Dolgozó személyes kapcsolattartó entitása nem exportálja a személyes kapcsolattartókat szülő kapcsolattípussal</span><span class="sxs-lookup"><span data-stu-id="e7d48-113">The Worker personal contact person entity doesn't export personal contacts with a parent relationship type</span></span>

<span data-ttu-id="e7d48-114">Ebben a kiadásban a **Dolgozó személyes kapcsolattartó** entitás exportálja az összes kapcsolattípust.</span><span class="sxs-lookup"><span data-stu-id="e7d48-114">With this release, the **Worker personal contact person** entity exports all relationship types.</span></span>

## <a name="the-hcmpositionworkerassignmentv2entity-should-be-part-of-the-ceridian-payroll-integration-package-by-default-448506"></a><span data-ttu-id="e7d48-115">A HcmPositionWorkerAssignmentV2Entity alapértelmezésben rész kell legyen a Ceridian bérlistaintegrációs csomagjának (448506)</span><span class="sxs-lookup"><span data-stu-id="e7d48-115">The HcmPositionWorkerAssignmentV2Entity should be part of the Ceridian payroll integration package by default (448506)</span></span>

<span data-ttu-id="e7d48-116">Ezzel a módosítással a **HcmPositionWorkerAssignmentV2Entity** a Ceridian bérlistaintegrációs csomagjának része.</span><span class="sxs-lookup"><span data-stu-id="e7d48-116">With this change, the **HcmPositionWorkerAssignmentV2Entity** is included in the Ceridian payroll integration package.</span></span>

## <a name="in-preview"></a><span data-ttu-id="e7d48-117">Előnézetben</span><span class="sxs-lookup"><span data-stu-id="e7d48-117">In preview</span></span>

## <a name="database-logging"></a><span data-ttu-id="e7d48-118">Adatbázis naplózása</span><span class="sxs-lookup"><span data-stu-id="e7d48-118">Database logging</span></span>

<span data-ttu-id="e7d48-119">Az adatbázis-naplózási funkció segítségével meghatározhatja, hogy mely táblát és mezőket kell figyelni.</span><span class="sxs-lookup"><span data-stu-id="e7d48-119">The database logging feature allows you to determine which tables and fields to monitor.</span></span> <span data-ttu-id="e7d48-120">Azt is lehetővé teszi, hogy meghatározza a változáskövetést igénylő eseményeket.</span><span class="sxs-lookup"><span data-stu-id="e7d48-120">It also lets you determine the events that should trigger change tracking.</span></span> <span data-ttu-id="e7d48-121">Az adatbázis-naplózási funkciók segítségével ezeknek a változásoknak a történetét megjelenítheti.</span><span class="sxs-lookup"><span data-stu-id="e7d48-121">You use database logging capabilities to see these changes over time.</span></span> <span data-ttu-id="e7d48-122">További tájékoztatás: [Adatbázis-naplózás konfigurálása és kezelése](hr-admin-database-logging.md).</span><span class="sxs-lookup"><span data-stu-id="e7d48-122">For more information, see [Configure and manage database logging](hr-admin-database-logging.md).</span></span>

## <a name="human-resources-application-in-teams"></a><span data-ttu-id="e7d48-123">Human Resources alkalmazás a Teamsben</span><span class="sxs-lookup"><span data-stu-id="e7d48-123">Human Resources application in Teams</span></span>

<span data-ttu-id="e7d48-124">Az alkalmazottak megtekinthetik és kérhetik a munkából való távollétet a Microsoft Teams alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="e7d48-124">Employees can view and request time away from work within Microsoft Teams.</span></span> <span data-ttu-id="e7d48-125">Ezek egy robottal lépnek interakcióba a szabadságkérelmek létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="e7d48-125">They can interact with a bot to create leave requests.</span></span> <span data-ttu-id="e7d48-126">További tájékoztatás: [Human Resources alkalmazás a Teamsben](./hr-admin-teams-leave-app.md).</span><span class="sxs-lookup"><span data-stu-id="e7d48-126">For more information, see [Human Resources app in Teams](./hr-admin-teams-leave-app.md).</span></span> 

## <a name="data-management-framework-dmf-entities-for-benefits-management"></a><span data-ttu-id="e7d48-127">Az adatkezelési keretrendszer (DMF) entitásai a juttatások kezeléséhez</span><span class="sxs-lookup"><span data-stu-id="e7d48-127">Data management framework (DMF) entities for Benefits management</span></span>
 
<span data-ttu-id="e7d48-128">A juttatások kezelése entitások kiadnak.</span><span class="sxs-lookup"><span data-stu-id="e7d48-128">Benefits management entities are releasing.</span></span> <span data-ttu-id="e7d48-129">A DMF entitások lehetővé teszik az adatok importálását és exportálását a juttatáskezelés egyszerű konfigurálásához.</span><span class="sxs-lookup"><span data-stu-id="e7d48-129">DMF entities allow you to import and export data to easily configure benefits management.</span></span> <span data-ttu-id="e7d48-130">A juttatáskezelési sablon az adatok áthelyezésére elérhető lesz.</span><span class="sxs-lookup"><span data-stu-id="e7d48-130">A Benefits management template will be available to move data.</span></span> <span data-ttu-id="e7d48-131">A sablon egymást követően exportálja és importálja az adatokat az adatfüggőségek tiszteletben tartásához.</span><span class="sxs-lookup"><span data-stu-id="e7d48-131">The template exports and imports the data sequentially to respect data dependencies.</span></span>

## <a name="buy-and-sell-leave"></a><span data-ttu-id="e7d48-132">Szabadság vásárlása és eladása</span><span class="sxs-lookup"><span data-stu-id="e7d48-132">Buy and sell leave</span></span> 

<span data-ttu-id="e7d48-133">Néhány szervezet olyan juttatást biztosít, amely lehetővé teszi az alkalmazottak számára, hogy megvásárolják vagy eladják a szabadságukat.</span><span class="sxs-lookup"><span data-stu-id="e7d48-133">Some organizations provide a benefit that allows employees to buy or sell their leave.</span></span> <span data-ttu-id="e7d48-134">Ezt a folyamatot gyakran manuálisan kell kezelni.</span><span class="sxs-lookup"><span data-stu-id="e7d48-134">This process is often managed manually.</span></span> <span data-ttu-id="e7d48-135">Ez a funkció automatizálja a HR osztályhoz tartozó kezelési házirendek és kérelmek kezelését.</span><span class="sxs-lookup"><span data-stu-id="e7d48-135">This feature automates managing policies and requests for the HR department.</span></span> <span data-ttu-id="e7d48-136">Racionalizálja a szabadság-kezelési folyamatot, és segít kiküszöbölni a hibákat.</span><span class="sxs-lookup"><span data-stu-id="e7d48-136">It streamlines the leave management process and helps eliminate mistakes.</span></span> <span data-ttu-id="e7d48-137">További tájékoztatás:</span><span class="sxs-lookup"><span data-stu-id="e7d48-137">For more information, see:</span></span>

- [<span data-ttu-id="e7d48-138">Szabadság vásárlásával és eladásával kapcsolatos irányelv kezelése</span><span class="sxs-lookup"><span data-stu-id="e7d48-138">Manage buy and sell leave policies</span></span>](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)
- [<span data-ttu-id="e7d48-139">Szabadság vásárlása és eladása</span><span class="sxs-lookup"><span data-stu-id="e7d48-139">Buy and sell leave</span></span>](hr-employee-self-service-buy-sell-leave.md)

## <a name="leave-accrual-for-a-single-company-or-single-plan"></a><span data-ttu-id="e7d48-140">Szabadság elhatárolása egyetlen vállalat vagy egy terv esetében</span><span class="sxs-lookup"><span data-stu-id="e7d48-140">Leave accrual for a single company or single plan</span></span>

<span data-ttu-id="e7d48-141">A vevők az elhatárolást egyetlen vállalatra vagy egyetlen szabadságtervhez is feldolgozhatják.</span><span class="sxs-lookup"><span data-stu-id="e7d48-141">Customers can process accruals for a single company or a single leave and absence plan.</span></span> <span data-ttu-id="e7d48-142">Ez a képesség tisztává teszi az elhatárolási folyamatot a különböző szabadságévekkel rendelkező vagy elhatárolási házirendekkel rendelkező vevők esetében.</span><span class="sxs-lookup"><span data-stu-id="e7d48-142">This ability provides clarity into the accrual process for customers with different leave years or leave accrual policies.</span></span> <span data-ttu-id="e7d48-143">A további tudnivalókat lásd: [Szabadság elhatárolása vállalatonként vagy szabadság tervenként](hr-leave-and-absence-accrue.md).</span><span class="sxs-lookup"><span data-stu-id="e7d48-143">For more information, see [Accrue leave per company or per leave plan](hr-leave-and-absence-accrue.md).</span></span>

## <a name="add-attachments-to-time-off-requests"></a><span data-ttu-id="e7d48-144">Mellékletek hozzáadása szabadságkérelmekhez</span><span class="sxs-lookup"><span data-stu-id="e7d48-144">Add attachments to time off requests</span></span>

<span data-ttu-id="e7d48-145">A jóváhagyott szabadságkérelmekhez tartozó mellékletek hozzáadásának lehetősége kritikus az aktuális COVID-19-környezetben.</span><span class="sxs-lookup"><span data-stu-id="e7d48-145">The ability to add attachments to approved leave requests is critical in the current COVID-19 environment.</span></span> <span data-ttu-id="e7d48-146">Az alkalmazottak ezután hozzáadhatják ezeket a mellékleteket.</span><span class="sxs-lookup"><span data-stu-id="e7d48-146">Employees can now add these attachments.</span></span> <span data-ttu-id="e7d48-147">Ők is nagyobb betekintést kapnak a szabadságkérelmek frissítései tekintetében.</span><span class="sxs-lookup"><span data-stu-id="e7d48-147">They also have more insight into how updates are made to leave requests.</span></span> <span data-ttu-id="e7d48-148">A további tudnivalókat lásd: [Melléklet hozzáadása meglévő kérelemhez](hr-employee-self-service-request-time-off.md#add-an-attachment-to-an-existing-request).</span><span class="sxs-lookup"><span data-stu-id="e7d48-148">For more information, see [Add an attachment to an existing request](hr-employee-self-service-request-time-off.md#add-an-attachment-to-an-existing-request).</span></span>

## <a name="add-reason-code-to-accrual-suspensions"></a><span data-ttu-id="e7d48-149">Okkódhozzáadása az elhatárolás-felfüggesztésekhez</span><span class="sxs-lookup"><span data-stu-id="e7d48-149">Add reason code to accrual suspensions</span></span> 

<span data-ttu-id="e7d48-150">Okkódok kerültek hozzáadásra az elhatárolás-felfüggesztéshez.</span><span class="sxs-lookup"><span data-stu-id="e7d48-150">Reason codes have been added to the accrual suspension.</span></span>

## <a name="carry-forward-rules"></a><span data-ttu-id="e7d48-151">Átvitel szabályai</span><span class="sxs-lookup"><span data-stu-id="e7d48-151">Carry forward rules</span></span> 

<span data-ttu-id="e7d48-152">Megadhatja, hogy az átviteli szabadságtípust az átviteli egyenlegekhez, ahová az átviteli korrekciók ár lesznek helyezve.</span><span class="sxs-lookup"><span data-stu-id="e7d48-152">You can specify a carry forward leave type for carry forward balances where carry forward adjustments are transferred.</span></span> <span data-ttu-id="e7d48-153">Ha például egy alkalmazott 10 napot visz át, akkor a 10 napnál más szabadság-típust is kiválaszthat.</span><span class="sxs-lookup"><span data-stu-id="e7d48-153">For example, if an employee carries forward 10 days, you can pick a different leave type for those 10 days.</span></span> <span data-ttu-id="e7d48-154">További tájékoztatás: [Szabadság és távolléti típusok konfigurálása](hr-leave-and-absence-types.md).</span><span class="sxs-lookup"><span data-stu-id="e7d48-154">For more information, see [Configure leave and absence types](hr-leave-and-absence-types.md).</span></span>

## <a name="suspend-leave-accrual-for-specified-leave-types"></a><span data-ttu-id="e7d48-155">Felfüggeszti a távollét elhatárolását a megadott szabadság-típusokhoz</span><span class="sxs-lookup"><span data-stu-id="e7d48-155">Suspend leave accrual for specified leave types</span></span>

<span data-ttu-id="e7d48-156">Olyan szabályt hozhat létre, amely felfüggeszti a távolléti elhatárolásokat a fizetés nélküli szabadságokhoz megadott szabadságkérelmekhez.</span><span class="sxs-lookup"><span data-stu-id="e7d48-156">You can create a rule to suspend leave accruals for employees with leave requests entered for unpaid leave.</span></span> <span data-ttu-id="e7d48-157">A fizetetlen szabadság lehet egy típus, de ez nem kötelező.</span><span class="sxs-lookup"><span data-stu-id="e7d48-157">Unpaid leave can be a type, but doesn't have to be.</span></span> <span data-ttu-id="e7d48-158">Bármilyen szabadságot egy másik szabadság típus alapján fel lehet függeszteni.</span><span class="sxs-lookup"><span data-stu-id="e7d48-158">You can suspend any leave based on another leave type.</span></span>

## <a name="dmf-entity-available-for-accrual-suspensions"></a><span data-ttu-id="e7d48-159">A DMF entitás elérhető az elhatárolás-felfüggesztésekhez</span><span class="sxs-lookup"><span data-stu-id="e7d48-159">DMF entity available for accrual suspensions</span></span> 

<span data-ttu-id="e7d48-160">A DMF entitás immár elérhető az elhatárolás-felfüggesztésekhez.</span><span class="sxs-lookup"><span data-stu-id="e7d48-160">A DMF entity is now available for accrual suspensions.</span></span>

## <a name="coming-soon"></a><span data-ttu-id="e7d48-161">Hamarosan</span><span class="sxs-lookup"><span data-stu-id="e7d48-161">Coming soon</span></span>

## <a name="new-platform-capabilities"></a><span data-ttu-id="e7d48-162">Új platformképességek</span><span class="sxs-lookup"><span data-stu-id="e7d48-162">New platform capabilities</span></span> 

<span data-ttu-id="e7d48-163">A mezőket a személyre szabás segítségével kötelezővé tehet mezőket.</span><span class="sxs-lookup"><span data-stu-id="e7d48-163">You'll be able to make fields mandatory by using personalization.</span></span> <span data-ttu-id="e7d48-164">Ez a funkció csak akkor szükséges, ha engedélyezni szeretné a **Mentett nézeteket**.</span><span class="sxs-lookup"><span data-stu-id="e7d48-164">This feature will require you to enable **Saved views**.</span></span>

## <a name="configure-the-name-of-employee-self-service"></a><span data-ttu-id="e7d48-165">Alkalmazotti önkiszolgáló rendszer nevének konfigurálása</span><span class="sxs-lookup"><span data-stu-id="e7d48-165">Configure the name of Employee self-service</span></span>

<span data-ttu-id="e7d48-166">A Humánerőforrás-paraméterek között egy új beállítás érhető el, ahol az Alkalmazotti önkiszolgáló rendszer munkaterület neve Önkiszolgáló rendszerre frissíthető.</span><span class="sxs-lookup"><span data-stu-id="e7d48-166">A new option will be available in Human Resources parameters to update the name of the Employee self service workspace to Self service.</span></span> 

## <a name="see-also"></a><span data-ttu-id="e7d48-167">Lásd még</span><span class="sxs-lookup"><span data-stu-id="e7d48-167">See also</span></span>

[<span data-ttu-id="e7d48-168">Új vagy módosult elemek a Human Resources szolgáltatásban</span><span class="sxs-lookup"><span data-stu-id="e7d48-168">What's new or changed in Human Resources</span></span>](hr-admin-whats-new.md)</br>
[<span data-ttu-id="e7d48-169">A Dynamics 365 Human Resources 2019 második kiadási hullámának áttekintése</span><span class="sxs-lookup"><span data-stu-id="e7d48-169">Overview of Dynamics 365 Human Resources 2019 release wave 2</span></span>](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[<span data-ttu-id="e7d48-170">Rendelés frissítése</span><span class="sxs-lookup"><span data-stu-id="e7d48-170">Update process</span></span>](hr-admin-setup-update-process.md)</br>
[<span data-ttu-id="e7d48-171">Szolgáltatások kezelése</span><span class="sxs-lookup"><span data-stu-id="e7d48-171">Manage features</span></span>](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]