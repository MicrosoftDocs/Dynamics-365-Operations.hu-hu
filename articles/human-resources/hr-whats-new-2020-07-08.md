---
title: A Dynamics 365 Human Resources új vagy módosult elemei (2020. július 08.)
description: Ez a témakör a Microsoft Dynamics 365 Human Resources új vagy módosított szolgáltatásait írja le.
author: Darinkramer
manager: AnnBe
ms.date: 07/08/2020
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
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: c4382aa7473e2b67201ac00753ac9abe11b3c646
ms.sourcegitcommit: 81296c49be9953aa01e15527c34d0ef13b4622a9
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/22/2020
ms.locfileid: "3614362"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-july-8-2020"></a><span data-ttu-id="c540a-103">A Dynamics 365 Human Resources új vagy módosult elemei (2020. július 8.)</span><span class="sxs-lookup"><span data-stu-id="c540a-103">What's new or changed in Dynamics 365 Human Resources (July 8, 2020)</span></span>

<span data-ttu-id="c540a-104">Ez a témakör a Dynamics 365 Human Resources új vagy módosított szolgáltatásait írja le.</span><span class="sxs-lookup"><span data-stu-id="c540a-104">This topic describes features that are either new or changed in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="c540a-105">A változtatások a 8.1.3382-es buildszámra vonatkoznak.</span><span class="sxs-lookup"><span data-stu-id="c540a-105">Changes apply to build number 8.1.3382.</span></span> <span data-ttu-id="c540a-106">A néhány fejlécben látható, zárójelben lévő számok az LCS támogatási számaira vonatkoznak referenciaképpen.</span><span class="sxs-lookup"><span data-stu-id="c540a-106">The numbers in parentheses in some headings refer to LCS support numbers for reference.</span></span>

## <a name="database-logging"></a><span data-ttu-id="c540a-107">Adatbázis naplózása</span><span class="sxs-lookup"><span data-stu-id="c540a-107">Database logging</span></span>

<span data-ttu-id="c540a-108">Az adatbázis-naplózás segítségével meghatározhatja, hogy mely táblát és mezőket kell figyelni.</span><span class="sxs-lookup"><span data-stu-id="c540a-108">Database logging allows you to determine which tables and fields to monitor.</span></span> <span data-ttu-id="c540a-109">Azt is lehetővé teszi, hogy meghatározza a változáskövetést igénylő eseményeket.</span><span class="sxs-lookup"><span data-stu-id="c540a-109">It also lets you determine the events that should trigger change tracking.</span></span> <span data-ttu-id="c540a-110">Az adatbázis-naplózási funkciók segítségével ezeknek a változásoknak a történetét megjelenítheti.</span><span class="sxs-lookup"><span data-stu-id="c540a-110">You use database logging capabilities to see these changes over time.</span></span> <span data-ttu-id="c540a-111">További tájékoztatás: [Adatbázis-naplózás konfigurálása és kezelése](hr-admin-database-logging.md).</span><span class="sxs-lookup"><span data-stu-id="c540a-111">For more information, see [Configure and manage database logging](hr-admin-database-logging.md).</span></span>

## <a name="configure-the-name-of-employee-self-service"></a><span data-ttu-id="c540a-112">Alkalmazotti önkiszolgáló rendszer nevének konfigurálása</span><span class="sxs-lookup"><span data-stu-id="c540a-112">Configure the name of Employee self service</span></span>

<span data-ttu-id="c540a-113">Az **Emberi erőforrások paraméterei** részben most már módosítható az **Alkalmazott önkiszolgáló rendszer** munkaterületének neve az **Önkiszolgáló rendszer** értékre.</span><span class="sxs-lookup"><span data-stu-id="c540a-113">In **Human Resources parameters**, you can now change the name of the **Employee self service** workspace to **Self service**.</span></span> <span data-ttu-id="c540a-114">További tájékoztatás: [Alkalmazotti önkiszolgáló munkaterület nevének módosítása](hr-employee-self-service-workspace-name.md)</span><span class="sxs-lookup"><span data-stu-id="c540a-114">For more information, see [Change Employee self service workspace name](hr-employee-self-service-workspace-name.md)</span></span>

## <a name="benefits-management-open-enrollment-access-outside-of-period"></a><span data-ttu-id="c540a-115">Juttatáskezelés – nyitott beléptetési hozzáférés az időszakon kívül</span><span class="sxs-lookup"><span data-stu-id="c540a-115">Benefits management open enrollment access outside of period</span></span>

<span data-ttu-id="c540a-116">Ez a kiadás javítja azt a hibát, amikor az alkalmazottak hozzáférhetnek a nyitott juttatási regisztrációhoz beadási időszakon kívül, illetve élettartam-esemény nélkül.</span><span class="sxs-lookup"><span data-stu-id="c540a-116">This release fixes a bug where employees could access benefits open enrollment outside of the enrollment period or without a life event.</span></span> <span data-ttu-id="c540a-117">Ennek eredményeképpen, ha a bemutató nyitott regiszrtációra van szükség az Alkalmazotti önkiszolgáló rendszerbe, a nyitott regisztrációs dátumokat a mai (vagy korábbi) értékre kell állítani, hogy elérhető legyen.</span><span class="sxs-lookup"><span data-stu-id="c540a-117">As a result, if you need to demo open enrollment in Employee self service, you must adjust the open enrollment dates to today (or earlier) to make it accessible.</span></span> <span data-ttu-id="c540a-118">Ezt a beállítást a **Juttatáskezelés > Szabályok és a beállítási időszakok** területen lehet módosítani.</span><span class="sxs-lookup"><span data-stu-id="c540a-118">You can change this setting under **Benefits management > Rules and options periods**.</span></span>

## <a name="email-employee-enrollment-confirmation"></a><span data-ttu-id="c540a-119">E-mail alkalmazotti regisztrációs visszaigazolás</span><span class="sxs-lookup"><span data-stu-id="c540a-119">Email employee enrollment confirmation</span></span>

<span data-ttu-id="c540a-120">Ezután e-maileket küldhet az alkalmazottaknak, miután elvégezték a juttatások kiválasztását.</span><span class="sxs-lookup"><span data-stu-id="c540a-120">You can now send emails to employees after they complete their benefits selection.</span></span> <span data-ttu-id="c540a-121">Küldhet alapértelmezett üzenetet, vagy használhatja a szervezet e-mail-sablonját.</span><span class="sxs-lookup"><span data-stu-id="c540a-121">You can either send a default message or use an organization email template.</span></span> <span data-ttu-id="c540a-122">Ezek a beállítások a **Emberi erőforrás paraméterei > Juttatáskezelés** területen találhatók.</span><span class="sxs-lookup"><span data-stu-id="c540a-122">These settings are under **Human resource parameters > Benefits management**.</span></span>

## <a name="canceled-leave-still-appears-in-upcoming-time-off-on-people-workspace-441358"></a><span data-ttu-id="c540a-123">A visszavont szabadság még mindig megjelenik a közelgő távollét részben a Személyek munkaterületen (441358)</span><span class="sxs-lookup"><span data-stu-id="c540a-123">Canceled leave still appears in upcoming time off on People workspace (441358)</span></span>

<span data-ttu-id="c540a-124">A visszavont szabadság már nem jelenik meg a szabadságkártyák közelgő távollét részében a **Személyek** munkaterületen.</span><span class="sxs-lookup"><span data-stu-id="c540a-124">Canceled leave no longer displays as upcoming time off on the leave cards in the **People** workspace.</span></span>

## <a name="unable-to-use-the-department-entity-property-in-the-positionv2-entity-456486"></a><span data-ttu-id="c540a-125">A részlet entitástulajdonság nem használható a Pozíció V2 entitásban (456486)</span><span class="sxs-lookup"><span data-stu-id="c540a-125">Unable to use the department entity property in the PositionV2 entity (456486)</span></span>

<span data-ttu-id="c540a-126">Most hozzáadhat egy részleget, ismétlődő kapcsolat létrehozása nélkül.</span><span class="sxs-lookup"><span data-stu-id="c540a-126">You can now add a department without creating a duplicate relation.</span></span>

## <a name="payrollworkerenrolledbenefitdetailentity-should-only-use-calculated-field-for-retirement-plans-459779"></a><span data-ttu-id="c540a-127">A PayrollWorkerEnrolledBenefitDetailEntity csak a nyugdíjazási tervekhez használandó számított használhatná (459779)</span><span class="sxs-lookup"><span data-stu-id="c540a-127">PayrollWorkerEnrolledBenefitDetailEntity should only use calculated field for retirement plans (459779)</span></span>

<span data-ttu-id="c540a-128">A **PayrollWorkerEnrolledBenefitDetailEntity** entitás exportálásakor az exportálás határozza meg, hogy kell-e egy számított mezőt használni egy díjtáblázat alapján, vagy a **ContributionAmountCur** mezőt kell használni a háttér táblán.</span><span class="sxs-lookup"><span data-stu-id="c540a-128">When exporting the **PayrollWorkerEnrolledBenefitDetailEntity** entity, the export determines whether it should use a calculated field based on a rate table or use the **ContributionAmountCur** field on the backing table.</span></span> <span data-ttu-id="c540a-129">Az adatentitás által használt logika a díjtáblázatot használja olyan helyzetekben, amikor az alkalmazás általában nem ezt használja.</span><span class="sxs-lookup"><span data-stu-id="c540a-129">The logic used by the data entity uses the rate table in situations where the application normally doesn't.</span></span> <span data-ttu-id="c540a-130">Ez a logika okozza, hogy az entitásexportálások nulla értéket adnak vissza ehhez az oszlophoz, mert nincs számítási díjtábla, és a termék nem teszi lehetővé a vevő számára, hogy megadjon egyet.</span><span class="sxs-lookup"><span data-stu-id="c540a-130">This logic causes the entity exports to return a zero value for this column, because there's no calculation rate table and the product doesn't allow the customer to specify one.</span></span>
 
## <a name="confusing-translations-in-czech-language-in-personnel-management-and-employee-self-service-400276"></a><span data-ttu-id="c540a-131">Zavaros fordítások cseh nyelven a személyzeti menedzsment és az Alkalmazotti önkiszolgáló rendszerben (400276)</span><span class="sxs-lookup"><span data-stu-id="c540a-131">Confusing translations in Czech language in Personnel management and Employee self service (400276)</span></span>

<span data-ttu-id="c540a-132">Ez a kiadás korrigálja a **vállalati címtár**, a **következő regisztrált tanfolyam**, a **feladat** és **Beosztás** fordítását.</span><span class="sxs-lookup"><span data-stu-id="c540a-132">This release corrects the translations for **Company directory**, **Next registered course**, **Job**, and **Position**.</span></span>
 
## <a name="the-workcalendaremployment-table-doesnt-have-the-created-and-modified-system-fields-enabled-460171"></a><span data-ttu-id="c540a-133">A WorkCalendarEmployment táblánál engedélyezve a létrehozott és a módosított rendszermezők (460171)</span><span class="sxs-lookup"><span data-stu-id="c540a-133">The WorkCalendarEmployment table doesn't have the created and modified system fields enabled (460171)</span></span>

<span data-ttu-id="c540a-134">A létrehozott és a módosított rendszermezők most már engedélyezve vannak a **WorkCalendarEmployment** táblában az Emberi erőforrások modulban.</span><span class="sxs-lookup"><span data-stu-id="c540a-134">Created and modified system fields are now enabled on the **WorkCalendarEmployment** table in Human Resources.</span></span>
 
## <a name="null-reference-exception-for-hire-and-add-details-for-future-employee-455475"></a><span data-ttu-id="c540a-135">Nullértékű hivatkozás kivétele a Jövőbeli alkalmazott felvételéhez és hozzáadásához (455475)</span><span class="sxs-lookup"><span data-stu-id="c540a-135">Null reference exception for Hire and add details for future employee (455475)</span></span>

<span data-ttu-id="c540a-136">Ez a kiadás kijavít egy hibát (nullértékű hivatkozás) a korszerű alkalmazotti bejegyzésben, amikor egy alkalmazottat a **Felvétel és adatok hozzáadása** beállítással alkalmaz.</span><span class="sxs-lookup"><span data-stu-id="c540a-136">This release corrects an error (null reference) in streamlined employee entry when you hire an employee using the option to **Hire and add details**.</span></span>

## <a name="changes-made-in-the-common-data-service-worker-entity-dont-reflect-in-human-resources-455652"></a><span data-ttu-id="c540a-137">A Common Data Service dolgozó entitásában végrehajtott változtatások nem tükröződnek a humán erőforrásokban (455652)</span><span class="sxs-lookup"><span data-stu-id="c540a-137">Changes made in the Common Data Service Worker entity don't reflect in Human Resources (455652)</span></span>

<span data-ttu-id="c540a-138">A Common Data Service **dolgozó** entitás következő mezőiben elvégzett módosítások most már megjelennek az Emberi erőforrások modulban:</span><span class="sxs-lookup"><span data-stu-id="c540a-138">Changes made to the following fields in the **Worker** entity in Common Data Service will now show up in Human Resources:</span></span>

- <span data-ttu-id="c540a-139">**Otthonról dolgozik**</span><span class="sxs-lookup"><span data-stu-id="c540a-139">**Works from home**</span></span>
- <span data-ttu-id="c540a-140">**Szolgálati idő dátuma**</span><span class="sxs-lookup"><span data-stu-id="c540a-140">**Seniority date**</span></span>
- <span data-ttu-id="c540a-141">**Évforduló dátuma**</span><span class="sxs-lookup"><span data-stu-id="c540a-141">**Anniversary date**</span></span>
- <span data-ttu-id="c540a-142">**Eredeti felvételi dátum**</span><span class="sxs-lookup"><span data-stu-id="c540a-142">**Original hire date**</span></span>

## <a name="correct-compensation-level-doesnt-default-based-on-the-job-assigned-to-the-position-394136"></a><span data-ttu-id="c540a-143">A megfelelő kompenzációs szint nem az alapértelmezett a beosztáshoz rendelt feladat alapján (394136)</span><span class="sxs-lookup"><span data-stu-id="c540a-143">Correct compensation level doesn't default based on the job assigned to the position (394136)</span></span>

<span data-ttu-id="c540a-144">Ezzel a módosítással a helyes kompenzációs szint lesz az alapértelmezett a **Beosztás adatai** elemhez tartozó **Érvényességi dátum** és a **Kompenzációs konstrukció hozzárendelése** elem **Kezdő dátuma** alapján.</span><span class="sxs-lookup"><span data-stu-id="c540a-144">With this change, the correct compensation level defaults based on the **Date effective** records for the **Position details** and the **Start date** of the **Compensation plan assignment**.</span></span>

## <a name="in-preview"></a><span data-ttu-id="c540a-145">Előnézetben</span><span class="sxs-lookup"><span data-stu-id="c540a-145">In preview</span></span>

## <a name="mandatory-fields"></a><span data-ttu-id="c540a-146">Kötelező mezők</span><span class="sxs-lookup"><span data-stu-id="c540a-146">Mandatory fields</span></span> 

<span data-ttu-id="c540a-147">Most már kötelezővé teheti a mezőket a Human Resources személyre szabási funkcióival.</span><span class="sxs-lookup"><span data-stu-id="c540a-147">You can now make fields mandatory by using Human Resources personalization capabilities.</span></span> <span data-ttu-id="c540a-148">Ehhez a funkcióhoz **Mentett nézetek** szükségesek.</span><span class="sxs-lookup"><span data-stu-id="c540a-148">This feature requires **Saved views**.</span></span>

## <a name="human-resources-application-in-teams"></a><span data-ttu-id="c540a-149">Human Resources alkalmazás a Teamsben</span><span class="sxs-lookup"><span data-stu-id="c540a-149">Human Resources application in Teams</span></span>

<span data-ttu-id="c540a-150">Az alkalmazottak megtekinthetik és kérhetik a munkából való távollétet a Microsoft Teams alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="c540a-150">Employees can view and request time away from work within Microsoft Teams.</span></span> <span data-ttu-id="c540a-151">Ezek egy robottal lépnek interakcióba a szabadságkérelmek létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="c540a-151">They can interact with a bot to create leave requests.</span></span> <span data-ttu-id="c540a-152">További tájékoztatás: [Human Resources alkalmazás a Teamsben](https://go.microsoft.com/fwlink/?linkid=2127841).</span><span class="sxs-lookup"><span data-stu-id="c540a-152">For more information, see [Human Resources app in Teams](https://go.microsoft.com/fwlink/?linkid=2127841).</span></span> 

## <a name="data-management-framework-dmf-entities-for-benefits-management"></a><span data-ttu-id="c540a-153">Az adatkezelési keretrendszer (DMF) entitásai a juttatások kezeléséhez</span><span class="sxs-lookup"><span data-stu-id="c540a-153">Data management framework (DMF) entities for Benefits management</span></span>
 
<span data-ttu-id="c540a-154">A juttatások kezelése entitások kiadnak.</span><span class="sxs-lookup"><span data-stu-id="c540a-154">Benefits management entities are releasing.</span></span> <span data-ttu-id="c540a-155">A DMF entitások lehetővé teszik az adatok importálását és exportálását a juttatáskezelés egyszerű konfigurálásához.</span><span class="sxs-lookup"><span data-stu-id="c540a-155">DMF entities allow you to import and export data to easily configure benefits management.</span></span> <span data-ttu-id="c540a-156">A juttatáskezelési sablon az adatok áthelyezésére elérhető lesz.</span><span class="sxs-lookup"><span data-stu-id="c540a-156">A Benefits management template will be available to move data.</span></span> <span data-ttu-id="c540a-157">A sablon egymást követően exportálja és importálja az adatokat az adatfüggőségek tiszteletben tartásához.</span><span class="sxs-lookup"><span data-stu-id="c540a-157">The template exports and imports the data sequentially to respect data dependencies.</span></span>

## <a name="buy-and-sell-leave"></a><span data-ttu-id="c540a-158">Szabadság vásárlása és eladása</span><span class="sxs-lookup"><span data-stu-id="c540a-158">Buy and sell leave</span></span> 

<span data-ttu-id="c540a-159">Néhány szervezet olyan juttatást biztosít, amely lehetővé teszi az alkalmazottak számára, hogy megvásárolják vagy eladják a szabadságukat.</span><span class="sxs-lookup"><span data-stu-id="c540a-159">Some organizations provide a benefit that allows employees to buy or sell their leave.</span></span> <span data-ttu-id="c540a-160">Ezt a folyamatot gyakran manuálisan kell kezelni.</span><span class="sxs-lookup"><span data-stu-id="c540a-160">This process is often managed manually.</span></span> <span data-ttu-id="c540a-161">Ez a funkció automatizálja a HR osztályhoz tartozó kezelési házirendek és kérelmek kezelését.</span><span class="sxs-lookup"><span data-stu-id="c540a-161">This feature automates managing policies and requests for the HR department.</span></span> <span data-ttu-id="c540a-162">Racionalizálja a szabadság-kezelési folyamatot, és segít kiküszöbölni a hibákat.</span><span class="sxs-lookup"><span data-stu-id="c540a-162">It streamlines the leave management process and helps eliminate mistakes.</span></span> <span data-ttu-id="c540a-163">További tájékoztatás:</span><span class="sxs-lookup"><span data-stu-id="c540a-163">For more information, see:</span></span>

- [<span data-ttu-id="c540a-164">Szabadság vásárlásával és eladásával kapcsolatos irányelv kezelése</span><span class="sxs-lookup"><span data-stu-id="c540a-164">Manage buy and sell leave policies</span></span>](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)
- [<span data-ttu-id="c540a-165">Szabadság vásárlása és eladása</span><span class="sxs-lookup"><span data-stu-id="c540a-165">Buy and sell leave</span></span>](hr-employee-self-service-buy-sell-leave.md)

## <a name="leave-accrual-for-a-single-company-or-single-plan"></a><span data-ttu-id="c540a-166">Szabadság elhatárolása egyetlen vállalat vagy egy terv esetében</span><span class="sxs-lookup"><span data-stu-id="c540a-166">Leave accrual for a single company or single plan</span></span>

<span data-ttu-id="c540a-167">A vevők az elhatárolást egyetlen vállalatra vagy egyetlen szabadságtervhez is feldolgozhatják.</span><span class="sxs-lookup"><span data-stu-id="c540a-167">Customers can process accruals for a single company or a single leave and absence plan.</span></span> <span data-ttu-id="c540a-168">Ez a képesség tisztává teszi az elhatárolási folyamatot a különböző szabadságévekkel rendelkező vagy elhatárolási házirendekkel rendelkező vevők esetében.</span><span class="sxs-lookup"><span data-stu-id="c540a-168">This ability provides clarity for the accrual process for customers with different leave years or leave accrual policies.</span></span> <span data-ttu-id="c540a-169">A további tudnivalókat lásd: [Szabadság elhatárolása vállalatonként vagy szabadság tervenként](hr-leave-and-absence-accrue.md#accrue-leave-per-company-or-per-leave-plan).</span><span class="sxs-lookup"><span data-stu-id="c540a-169">For more information, see [Accrue leave per company or per leave plan](hr-leave-and-absence-accrue.md#accrue-leave-per-company-or-per-leave-plan).</span></span>

## <a name="add-attachments-to-time-off-requests"></a><span data-ttu-id="c540a-170">Mellékletek hozzáadása szabadságkérelmekhez</span><span class="sxs-lookup"><span data-stu-id="c540a-170">Add attachments to time-off requests</span></span>

<span data-ttu-id="c540a-171">A jóváhagyott szabadságkérelmekhez tartozó mellékletek hozzáadásának lehetősége kritikus az aktuális COVID-19-környezetben.</span><span class="sxs-lookup"><span data-stu-id="c540a-171">The ability to add attachments to approved leave requests is critical in the current COVID-19 environment.</span></span> <span data-ttu-id="c540a-172">Az alkalmazottak ezután hozzáadhatják ezeket a mellékleteket.</span><span class="sxs-lookup"><span data-stu-id="c540a-172">Employees can now add these attachments.</span></span> <span data-ttu-id="c540a-173">Ők is nagyobb betekintést kapnak a szabadságkérelmek frissítései tekintetében.</span><span class="sxs-lookup"><span data-stu-id="c540a-173">They also have more insight into how updates are made to leave requests.</span></span> <span data-ttu-id="c540a-174">A további tudnivalókat lásd: [Melléklet hozzáadása meglévő kérelemhez](hr-employee-self-service-request-time-off.md#add-an-attachment-to-an-existing-request).</span><span class="sxs-lookup"><span data-stu-id="c540a-174">For more information, see [Add an attachment to an existing request](hr-employee-self-service-request-time-off.md#add-an-attachment-to-an-existing-request).</span></span>

## <a name="add-reason-code-to-accrual-suspensions"></a><span data-ttu-id="c540a-175">Okkódhozzáadása az elhatárolás-felfüggesztésekhez</span><span class="sxs-lookup"><span data-stu-id="c540a-175">Add reason code to accrual suspensions</span></span> 

<span data-ttu-id="c540a-176">Okkódok kerültek hozzáadásra az elhatárolás-felfüggesztéshez.</span><span class="sxs-lookup"><span data-stu-id="c540a-176">Reason codes have been added to the accrual suspension.</span></span>

## <a name="carry-forward-rules"></a><span data-ttu-id="c540a-177">Átvitel szabályai</span><span class="sxs-lookup"><span data-stu-id="c540a-177">Carry forward rules</span></span> 

<span data-ttu-id="c540a-178">Megadhatja, hogy az átviteli szabadságtípust az átviteli egyenlegekhez, ahová az átviteli korrekciók ár lesznek helyezve.</span><span class="sxs-lookup"><span data-stu-id="c540a-178">You can specify a carry forward leave type for carry forward balances where carry forward adjustments are transferred.</span></span> <span data-ttu-id="c540a-179">Ha például egy alkalmazott 10 napot visz át, akkor a 10 napnál más szabadság-típust is kiválaszthat.</span><span class="sxs-lookup"><span data-stu-id="c540a-179">For example, if an employee carries forward 10 days, you can pick a different leave type for those 10 days.</span></span> <span data-ttu-id="c540a-180">További tájékoztatás: [Szabadság és távolléti típusok konfigurálása](hr-leave-and-absence-types.md).</span><span class="sxs-lookup"><span data-stu-id="c540a-180">For more information, see [Configure leave and absence types](hr-leave-and-absence-types.md).</span></span>

## <a name="suspend-leave-accrual-for-specified-leave-types"></a><span data-ttu-id="c540a-181">Felfüggeszti a távollét elhatárolását a megadott szabadság-típusokhoz</span><span class="sxs-lookup"><span data-stu-id="c540a-181">Suspend leave accrual for specified leave types</span></span>

<span data-ttu-id="c540a-182">Olyan szabályt hozhat létre, amely felfüggeszti a távolléti elhatárolásokat a fizetés nélküli szabadságokhoz megadott szabadságkérelmekhez.</span><span class="sxs-lookup"><span data-stu-id="c540a-182">You can create a rule to suspend leave accruals for employees with leave requests entered for unpaid leave.</span></span> <span data-ttu-id="c540a-183">A fizetetlen szabadság lehet egy típus, de ez nem kötelező.</span><span class="sxs-lookup"><span data-stu-id="c540a-183">Unpaid leave can be a type, but doesn't have to be.</span></span> <span data-ttu-id="c540a-184">Bármilyen szabadságot egy másik szabadság típus alapján fel lehet függeszteni.</span><span class="sxs-lookup"><span data-stu-id="c540a-184">You can suspend any leave based on another leave type.</span></span>

## <a name="dmf-entity-available-for-accrual-suspensions"></a><span data-ttu-id="c540a-185">A DMF entitás elérhető az elhatárolás-felfüggesztésekhez</span><span class="sxs-lookup"><span data-stu-id="c540a-185">DMF entity available for accrual suspensions</span></span> 

<span data-ttu-id="c540a-186">A DMF entitás immár elérhető az elhatárolás-felfüggesztésekhez.</span><span class="sxs-lookup"><span data-stu-id="c540a-186">A DMF entity is now available for accrual suspensions.</span></span>

## <a name="coming-soon"></a><span data-ttu-id="c540a-187">Hamarosan</span><span class="sxs-lookup"><span data-stu-id="c540a-187">Coming soon</span></span>

## <a name="checklist-entities-included-in-common-data-service"></a><span data-ttu-id="c540a-188">Ellenőrzőlista-entitások szerepelnek a következőben: Common Data Service</span><span class="sxs-lookup"><span data-stu-id="c540a-188">Checklist entities included in Common Data Service</span></span>

<span data-ttu-id="c540a-189">Az Előkészítés, Felszámolás, Áthelyezések és Üzleti folyamatok hamarosan elérhetők lesznek a Common Data Service alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="c540a-189">Checklist entities for Onboarding, Offboarding, Transfers, and Business processes will be available soon in Common Data Service.</span></span>

## <a name="see-also"></a><span data-ttu-id="c540a-190">Lásd még</span><span class="sxs-lookup"><span data-stu-id="c540a-190">See also</span></span>

[<span data-ttu-id="c540a-191">Új vagy módosult elemek a Human Resources szolgáltatásban</span><span class="sxs-lookup"><span data-stu-id="c540a-191">What's new or changed in Human Resources</span></span>](hr-admin-whats-new.md)</br>
[<span data-ttu-id="c540a-192">A Dynamics 365 Human Resources 2019 második kiadási hullámának áttekintése</span><span class="sxs-lookup"><span data-stu-id="c540a-192">Overview of Dynamics 365 Human Resources 2019 release wave 2</span></span>](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[<span data-ttu-id="c540a-193">Rendelés frissítése</span><span class="sxs-lookup"><span data-stu-id="c540a-193">Update process</span></span>](hr-admin-setup-update-process.md)</br>
[<span data-ttu-id="c540a-194">Szolgáltatások kezelése</span><span class="sxs-lookup"><span data-stu-id="c540a-194">Manage features</span></span>](hr-admin-manage-features.md)
