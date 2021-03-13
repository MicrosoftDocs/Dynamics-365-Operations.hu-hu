---
title: A Dynamics 365 Human Resources új és módosult elemei (2020. június 25.)
description: Ez a témakör a Microsoft Dynamics 365 Human Resources új vagy módosított szolgáltatásait írja le a 2020. június 23-i kiadásban.
author: andreabichsel
manager: tfehr
ms.date: 06/25/2020
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
ms.search.validFrom: 2020-06-25
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: ad80e53c0a24d602ac446d3e0765f397dd0fc2d9
ms.sourcegitcommit: f8bac7ca2803913fd236adbc3806259a17a110f4
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/06/2021
ms.locfileid: "5127497"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-june-23-2020"></a><span data-ttu-id="e2c46-103">A Dynamics 365 Human Resources új és módosult elemei (2020. június 23.)</span><span class="sxs-lookup"><span data-stu-id="e2c46-103">What's new or changed in Dynamics 365 Human Resources (June 23, 2020)</span></span>

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="e2c46-104">Ez a témakör a Dynamics 365 Human Resources új vagy módosított szolgáltatásait írja le.</span><span class="sxs-lookup"><span data-stu-id="e2c46-104">This topic describes features that are either new or changed in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="e2c46-105">A változtatások a 8.1.3347-es buildszámra vonatkoznak.</span><span class="sxs-lookup"><span data-stu-id="e2c46-105">Changes apply to build number 8.1.3347.</span></span> <span data-ttu-id="e2c46-106">A néhány fejlécben látható, zárójelben lévő számok az LCS támogatási számaira vonatkoznak referenciaképpen.</span><span class="sxs-lookup"><span data-stu-id="e2c46-106">The numbers in parentheses in some headings refer to LCS support numbers for reference.</span></span>

## <a name="when-an-enrollment-is-expired-for-a-terminated-employee-the-leave-type-balance-and-amount-are-all-cleared-in-the-leave-enrollment-form-444867"></a><span data-ttu-id="e2c46-107">Ha egy kilépett alkalmazottnál lejár a beléptetés, akkor a szabadság típusa, egyenlege és összege törlődik a Szabadságregisztrációs űrlapról (444867).</span><span class="sxs-lookup"><span data-stu-id="e2c46-107">When an enrollment is expired for a terminated employee, the leave type, balance, and amount are all cleared in the Leave enrollment form (444867)</span></span>

<span data-ttu-id="e2c46-108">A **Szabadság típusa**, **Egyenleg** és **Összeg** értékeit a program a kiválasztáskor nem törli, hanem megtartja.</span><span class="sxs-lookup"><span data-stu-id="e2c46-108">Values in the **Leave type**, **Balance**, and **Amount** are now maintained instead of cleared upon making this selection.</span></span>

## <a name="incorrect-forecasted-balance-when-new-feature-leave-accrual-for-a-single-company-or-a-single-plan-is-enabled-456553"></a><span data-ttu-id="e2c46-109">Hibás előre jelzett egyenleg, ha a z új funkció (Szabadság elhatárolása egyetlen vállalat vagy egy terv esetében) engedélyezve van (456553).</span><span class="sxs-lookup"><span data-stu-id="e2c46-109">Incorrect forecasted balance when new feature (Leave accrual for a single company or a single plan) is enabled (456553)</span></span>

<span data-ttu-id="e2c46-110">A hibás előrejelzett egyenleg most megjeleníti, ha a szabadság elhatárolása egyetlen vállalat vagy egy terv esetében engedélyezve van.</span><span class="sxs-lookup"><span data-stu-id="e2c46-110">The correct forecasted balance now displays when the leave accrual for a single company or single plan has been enabled.</span></span>

## <a name="entities-with-relations-that-result-in-duplicate-navigation-properties-456486"></a><span data-ttu-id="e2c46-111">Ismétlődő navigációs tulajdonságokat eredményező kapcsolatokat tartalmazó entitások (456486)</span><span class="sxs-lookup"><span data-stu-id="e2c46-111">Entities with relations that result in duplicate navigation properties (456486)</span></span>

<span data-ttu-id="e2c46-112">Ez a kiadás javítja több entitás navigációs tulajdonságával (objektumkapcsolat) kapcsolatos hibát.</span><span class="sxs-lookup"><span data-stu-id="e2c46-112">This release corrects an issue with the navigation properties (relation) of multiple entities.</span></span> <span data-ttu-id="e2c46-113">Ismétlődő objektumkapcsolatok észlelhetők.</span><span class="sxs-lookup"><span data-stu-id="e2c46-113">Duplicate relations are detected.</span></span> <span data-ttu-id="e2c46-114">Ezek a helyzetek mind javítva lettek.</span><span class="sxs-lookup"><span data-stu-id="e2c46-114">These scenarios have all been corrected.</span></span>
 
## <a name="cross-company-comments-on-performance-review-455536"></a><span data-ttu-id="e2c46-115">Több vállalatot érintő megjegyzések a Teljesítmény-ellenőrzéssel kapcsolatban (455536)</span><span class="sxs-lookup"><span data-stu-id="e2c46-115">Cross-company comments on Performance review (455536)</span></span>

<span data-ttu-id="e2c46-116">A több vállalatot érintő megjegyzések most már láthatók a javításnak köszönhetően a teljesítmény-ellenőrzésekben.</span><span class="sxs-lookup"><span data-stu-id="e2c46-116">Cross-company comments are now visible on performance reviews with this fix.</span></span> <span data-ttu-id="e2c46-117">Ez a módosítás korrigálja a különböző vállalatokban ugyanahhoz a teljesítmény-ellenőrzéshez megadott véleményezői megjegyzések nézetét.</span><span class="sxs-lookup"><span data-stu-id="e2c46-117">This change corrects the view of reviewer comments that were entered in different companies for the same performance review.</span></span>
 
## <a name="inconsistency-in-showing-compensation-management-data-432562"></a><span data-ttu-id="e2c46-118">Inkonzisztencia a kompenzációkezelési adatok megjelenítésében (432562)</span><span class="sxs-lookup"><span data-stu-id="e2c46-118">Inconsistency in showing compensation management data (432562)</span></span>

<span data-ttu-id="e2c46-119">A kompenzációs adatok konzisztens nézete a vezetői önkiszolgáló szolgáltatásban most már megmarad.</span><span class="sxs-lookup"><span data-stu-id="e2c46-119">A consistent view of compensation data is now maintained in Manager self service.</span></span> <span data-ttu-id="e2c46-120">Attól függően, hogy hogyan navigál a dolgozó **Kompenzáció részletei** lehetőséghez, a kompenzációs adatok konzisztensen jelennek meg a vezetőknek.</span><span class="sxs-lookup"><span data-stu-id="e2c46-120">Depending on how you navigate to a worker's **Compensation details**, compensation data now consistently displays to managers.</span></span>
 
## <a name="fixed-compensation-plans-effective-date-defaults-to-todays-date-411994"></a><span data-ttu-id="e2c46-121">Javítva lett a probléma, amely miatt a kompenzációs csomag érvényességi dátuma az adott napi dátumra állt be alapértelmezettként (411994)</span><span class="sxs-lookup"><span data-stu-id="e2c46-121">Fixed compensation plan's effective date defaults to today's date (411994)</span></span>

<span data-ttu-id="e2c46-122">A kompenzáció kezdő dátuma most az alkalmazotthoz rendelt beosztás kezdő dátumán alapul.</span><span class="sxs-lookup"><span data-stu-id="e2c46-122">The compensation start date is now based on the start date of the position being assigned to the employee.</span></span>

## <a name="leave-and-absence-form-enable-half-day-definition-is-disabled-when-form-opens-452607"></a><span data-ttu-id="e2c46-123">Szabadság és távollét a Félnapos meghatározás engedélyezéséből le van tiltva az űrlap megnyitásakor (452607)</span><span class="sxs-lookup"><span data-stu-id="e2c46-123">Leave and absence form Enable half day definition is disabled when form opens (452607)</span></span>

<span data-ttu-id="e2c46-124">Ezzel a módosítással a **Félnapos meghatározás engedélyezése** engedélyezett addig, amíg nem léteznek új szabadságtranzakciók.</span><span class="sxs-lookup"><span data-stu-id="e2c46-124">With this change, the **Enable half day definition** will be enabled until new leave transactions exist.</span></span> 

## <a name="unable-to-publish-to-hcmdiscussionentity-via-excel-totalratingscore-field-error-453899"></a><span data-ttu-id="e2c46-125">Nem lehet közzétenni a HcmDiscussionEntity az elemhez az Excel programon keresztül; TotalRatingScore mező hibája (453899)</span><span class="sxs-lookup"><span data-stu-id="e2c46-125">Unable to publish to HcmDiscussionEntity via Excel; TotalRatingScore field error (453899)</span></span>

<span data-ttu-id="e2c46-126">Most frissítheti a **TotalRatingScore** mezőt a **HCMDiscussionEntity** használatával az Excel-munkafüzet-tervezőben.</span><span class="sxs-lookup"><span data-stu-id="e2c46-126">You can now update the **TotalRatingScore** field using **HCMDiscussionEntity** in the Excel workbook designer.</span></span>

## <a name="in-preview"></a><span data-ttu-id="e2c46-127">Előnézetben</span><span class="sxs-lookup"><span data-stu-id="e2c46-127">In preview</span></span>

## <a name="database-logging"></a><span data-ttu-id="e2c46-128">Adatbázis naplózása</span><span class="sxs-lookup"><span data-stu-id="e2c46-128">Database logging</span></span>

<span data-ttu-id="e2c46-129">Az adatbázis-naplózás segítségével meghatározhatja, hogy mely táblát és mezőket kell figyelni.</span><span class="sxs-lookup"><span data-stu-id="e2c46-129">Database logging allows you to determine which tables and fields to monitor.</span></span> <span data-ttu-id="e2c46-130">Azt is lehetővé teszi, hogy meghatározza a változáskövetést igénylő eseményeket.</span><span class="sxs-lookup"><span data-stu-id="e2c46-130">It also lets you determine the events that should trigger change tracking.</span></span> <span data-ttu-id="e2c46-131">Az adatbázis-naplózási funkciók segítségével ezeknek a változásoknak a történetét megjelenítheti.</span><span class="sxs-lookup"><span data-stu-id="e2c46-131">You use database logging capabilities to see these changes over time.</span></span> <span data-ttu-id="e2c46-132">További tájékoztatás: [Adatbázis-naplózás konfigurálása és kezelése](hr-admin-database-logging.md).</span><span class="sxs-lookup"><span data-stu-id="e2c46-132">For more information, see [Configure and manage database logging](hr-admin-database-logging.md).</span></span>

## <a name="mandatory-fields"></a><span data-ttu-id="e2c46-133">Kötelező mezők</span><span class="sxs-lookup"><span data-stu-id="e2c46-133">Mandatory fields</span></span> 

<span data-ttu-id="e2c46-134">Most már kötelezővé teheti a mezőket a Human Resources személyre szabási funkcióival.</span><span class="sxs-lookup"><span data-stu-id="e2c46-134">You can now make fields mandatory by using Human Resources personalization capabilities.</span></span> <span data-ttu-id="e2c46-135">Ehhez a funkcióhoz **Mentett nézetek** szükségesek.</span><span class="sxs-lookup"><span data-stu-id="e2c46-135">This feature requires **Saved views**.</span></span>

## <a name="human-resources-application-in-teams"></a><span data-ttu-id="e2c46-136">Human Resources alkalmazás a Teamsben</span><span class="sxs-lookup"><span data-stu-id="e2c46-136">Human Resources application in Teams</span></span>

<span data-ttu-id="e2c46-137">Az alkalmazottak megtekinthetik és kérhetik a munkából való távollétet a Microsoft Teams alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="e2c46-137">Employees can view and request time away from work within Microsoft Teams.</span></span> <span data-ttu-id="e2c46-138">Ezek egy robottal lépnek interakcióba a szabadságkérelmek létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="e2c46-138">They can interact with a bot to create leave requests.</span></span> <span data-ttu-id="e2c46-139">További tájékoztatás: [Human Resources alkalmazás a Teamsben](https://go.microsoft.com/fwlink/?linkid=2127841).</span><span class="sxs-lookup"><span data-stu-id="e2c46-139">For more information, see [Human Resources app in Teams](https://go.microsoft.com/fwlink/?linkid=2127841).</span></span> 

## <a name="data-management-framework-dmf-entities-for-benefits-management"></a><span data-ttu-id="e2c46-140">Az adatkezelési keretrendszer (DMF) entitásai a juttatások kezeléséhez</span><span class="sxs-lookup"><span data-stu-id="e2c46-140">Data management framework (DMF) entities for Benefits management</span></span>
 
<span data-ttu-id="e2c46-141">A juttatások kezelése entitások kiadnak.</span><span class="sxs-lookup"><span data-stu-id="e2c46-141">Benefits management entities are releasing.</span></span> <span data-ttu-id="e2c46-142">A DMF entitások lehetővé teszik az adatok importálását és exportálását a juttatáskezelés egyszerű konfigurálásához.</span><span class="sxs-lookup"><span data-stu-id="e2c46-142">DMF entities allow you to import and export data to easily configure benefits management.</span></span> <span data-ttu-id="e2c46-143">A juttatáskezelési sablon az adatok áthelyezésére elérhető lesz.</span><span class="sxs-lookup"><span data-stu-id="e2c46-143">A Benefits management template will be available to move data.</span></span> <span data-ttu-id="e2c46-144">A sablon egymást követően exportálja és importálja az adatokat az adatfüggőségek tiszteletben tartásához.</span><span class="sxs-lookup"><span data-stu-id="e2c46-144">The template exports and imports the data sequentially to respect data dependencies.</span></span>

## <a name="buy-and-sell-leave"></a><span data-ttu-id="e2c46-145">Szabadság vásárlása és eladása</span><span class="sxs-lookup"><span data-stu-id="e2c46-145">Buy and sell leave</span></span> 

<span data-ttu-id="e2c46-146">Néhány szervezet olyan juttatást biztosít, amely lehetővé teszi az alkalmazottak számára, hogy megvásárolják vagy eladják a szabadságukat.</span><span class="sxs-lookup"><span data-stu-id="e2c46-146">Some organizations provide a benefit that allows employees to buy or sell their leave.</span></span> <span data-ttu-id="e2c46-147">Ezt a folyamatot gyakran manuálisan kell kezelni.</span><span class="sxs-lookup"><span data-stu-id="e2c46-147">This process is often managed manually.</span></span> <span data-ttu-id="e2c46-148">Ez a funkció automatizálja a HR osztályhoz tartozó kezelési házirendek és kérelmek kezelését.</span><span class="sxs-lookup"><span data-stu-id="e2c46-148">This feature automates managing policies and requests for the HR department.</span></span> <span data-ttu-id="e2c46-149">Racionalizálja a szabadság-kezelési folyamatot, és segít kiküszöbölni a hibákat.</span><span class="sxs-lookup"><span data-stu-id="e2c46-149">It streamlines the leave management process and helps eliminate mistakes.</span></span> <span data-ttu-id="e2c46-150">További tájékoztatás:</span><span class="sxs-lookup"><span data-stu-id="e2c46-150">For more information, see:</span></span>

- [<span data-ttu-id="e2c46-151">Szabadság vásárlásával és eladásával kapcsolatos irányelv kezelése</span><span class="sxs-lookup"><span data-stu-id="e2c46-151">Manage buy and sell leave policies</span></span>](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)
- [<span data-ttu-id="e2c46-152">Szabadság vásárlása és eladása</span><span class="sxs-lookup"><span data-stu-id="e2c46-152">Buy and sell leave</span></span>](hr-employee-self-service-buy-sell-leave.md)

## <a name="leave-accrual-for-a-single-company-or-single-plan"></a><span data-ttu-id="e2c46-153">Szabadság elhatárolása egyetlen vállalat vagy egy terv esetében</span><span class="sxs-lookup"><span data-stu-id="e2c46-153">Leave accrual for a single company or single plan</span></span>

<span data-ttu-id="e2c46-154">A vevők az elhatárolást egyetlen vállalatra vagy egyetlen szabadságtervhez is feldolgozhatják.</span><span class="sxs-lookup"><span data-stu-id="e2c46-154">Customers can process accruals for a single company or a single leave and absence plan.</span></span> <span data-ttu-id="e2c46-155">Ez a képesség tisztává teszi az elhatárolási folyamatot a különböző szabadságévekkel rendelkező vagy elhatárolási házirendekkel rendelkező vevők esetében.</span><span class="sxs-lookup"><span data-stu-id="e2c46-155">This ability provides clarity into the accrual process for customers with different leave years or leave accrual policies.</span></span> <span data-ttu-id="e2c46-156">A további tudnivalókat lásd: [Szabadság elhatárolása vállalatonként vagy szabadság tervenként](hr-leave-and-absence-accrue.md).</span><span class="sxs-lookup"><span data-stu-id="e2c46-156">For more information, see [Accrue leave per company or per leave plan](hr-leave-and-absence-accrue.md).</span></span>

## <a name="add-attachments-to-time-off-requests"></a><span data-ttu-id="e2c46-157">Mellékletek hozzáadása szabadságkérelmekhez</span><span class="sxs-lookup"><span data-stu-id="e2c46-157">Add attachments to time off requests</span></span>

<span data-ttu-id="e2c46-158">A jóváhagyott szabadságkérelmekhez tartozó mellékletek hozzáadásának lehetősége kritikus az aktuális COVID-19-környezetben.</span><span class="sxs-lookup"><span data-stu-id="e2c46-158">The ability to add attachments to approved leave requests is critical in the current COVID-19 environment.</span></span> <span data-ttu-id="e2c46-159">Az alkalmazottak ezután hozzáadhatják ezeket a mellékleteket.</span><span class="sxs-lookup"><span data-stu-id="e2c46-159">Employees can now add these attachments.</span></span> <span data-ttu-id="e2c46-160">Ők is nagyobb betekintést kapnak a szabadságkérelmek frissítései tekintetében.</span><span class="sxs-lookup"><span data-stu-id="e2c46-160">They also have more insight into how updates are made to leave requests.</span></span> <span data-ttu-id="e2c46-161">A további tudnivalókat lásd: [Melléklet hozzáadása meglévő kérelemhez](hr-employee-self-service-request-time-off.md#add-an-attachment-to-an-existing-request).</span><span class="sxs-lookup"><span data-stu-id="e2c46-161">For more information, see [Add an attachment to an existing request](hr-employee-self-service-request-time-off.md#add-an-attachment-to-an-existing-request).</span></span>

## <a name="add-reason-code-to-accrual-suspensions"></a><span data-ttu-id="e2c46-162">Okkódhozzáadása az elhatárolás-felfüggesztésekhez</span><span class="sxs-lookup"><span data-stu-id="e2c46-162">Add reason code to accrual suspensions</span></span> 

<span data-ttu-id="e2c46-163">Okkódok kerültek hozzáadásra az elhatárolás-felfüggesztéshez.</span><span class="sxs-lookup"><span data-stu-id="e2c46-163">Reason codes have been added to the accrual suspension.</span></span>

## <a name="carry-forward-rules"></a><span data-ttu-id="e2c46-164">Átvitel szabályai</span><span class="sxs-lookup"><span data-stu-id="e2c46-164">Carry forward rules</span></span> 

<span data-ttu-id="e2c46-165">Megadhatja, hogy az átviteli szabadságtípust az átviteli egyenlegekhez, ahová az átviteli korrekciók ár lesznek helyezve.</span><span class="sxs-lookup"><span data-stu-id="e2c46-165">You can specify a carry forward leave type for carry forward balances where carry forward adjustments are transferred.</span></span> <span data-ttu-id="e2c46-166">Ha például egy alkalmazott 10 napot visz át, akkor a 10 napnál más szabadság-típust is kiválaszthat.</span><span class="sxs-lookup"><span data-stu-id="e2c46-166">For example, if an employee carries forward 10 days, you can pick a different leave type for those 10 days.</span></span> <span data-ttu-id="e2c46-167">További tájékoztatás: [Szabadság és távolléti típusok konfigurálása](hr-leave-and-absence-types.md).</span><span class="sxs-lookup"><span data-stu-id="e2c46-167">For more information, see [Configure leave and absence types](hr-leave-and-absence-types.md).</span></span>

## <a name="suspend-leave-accrual-for-specified-leave-types"></a><span data-ttu-id="e2c46-168">Felfüggeszti a távollét elhatárolását a megadott szabadság-típusokhoz</span><span class="sxs-lookup"><span data-stu-id="e2c46-168">Suspend leave accrual for specified leave types</span></span>

<span data-ttu-id="e2c46-169">Olyan szabályt hozhat létre, amely felfüggeszti a távolléti elhatárolásokat a fizetés nélküli szabadságokhoz megadott szabadságkérelmekhez.</span><span class="sxs-lookup"><span data-stu-id="e2c46-169">You can create a rule to suspend leave accruals for employees with leave requests entered for unpaid leave.</span></span> <span data-ttu-id="e2c46-170">A fizetetlen szabadság lehet egy típus, de ez nem kötelező.</span><span class="sxs-lookup"><span data-stu-id="e2c46-170">Unpaid leave can be a type, but doesn't have to be.</span></span> <span data-ttu-id="e2c46-171">Bármilyen szabadságot egy másik szabadság típus alapján fel lehet függeszteni.</span><span class="sxs-lookup"><span data-stu-id="e2c46-171">You can suspend any leave based on another leave type.</span></span>

## <a name="dmf-entity-available-for-accrual-suspensions"></a><span data-ttu-id="e2c46-172">A DMF entitás elérhető az elhatárolás-felfüggesztésekhez</span><span class="sxs-lookup"><span data-stu-id="e2c46-172">DMF entity available for accrual suspensions</span></span> 

<span data-ttu-id="e2c46-173">A DMF entitás immár elérhető az elhatárolás-felfüggesztésekhez.</span><span class="sxs-lookup"><span data-stu-id="e2c46-173">A DMF entity is now available for accrual suspensions.</span></span>

## <a name="coming-soon"></a><span data-ttu-id="e2c46-174">Hamarosan</span><span class="sxs-lookup"><span data-stu-id="e2c46-174">Coming soon</span></span>

## <a name="configure-the-name-of-employee-self-service"></a><span data-ttu-id="e2c46-175">Alkalmazotti önkiszolgáló rendszer nevének konfigurálása</span><span class="sxs-lookup"><span data-stu-id="e2c46-175">Configure the name of Employee self-service</span></span>

<span data-ttu-id="e2c46-176">Az **Emberi erőforrások paraméterei** között egy új beállítás érhető el, ahol az Alkalmazotti önkiszolgáló rendszer munkaterület neve Önkiszolgáló rendszerre frissíthető.</span><span class="sxs-lookup"><span data-stu-id="e2c46-176">A new option will be available in **Human Resources parameters** to update the name of the Employee self service workspace to Self service.</span></span>

## <a name="checklist-entities-included-in-dataverse"></a><span data-ttu-id="e2c46-177">Ellenőrzőlista-entitások szerepelnek a következőben: Dataverse</span><span class="sxs-lookup"><span data-stu-id="e2c46-177">Checklist entities included in Dataverse</span></span>

<span data-ttu-id="e2c46-178">Az Előkészítés, Felszámolás, Áthelyezések és Üzleti folyamatok hamarosan elérhetők lesznek a Dataverse alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="e2c46-178">Checklist entities for Onboarding, Offboarding, Transfers, and Business processes will be available soon within Dataverse.</span></span>

## <a name="see-also"></a><span data-ttu-id="e2c46-179">Lásd még</span><span class="sxs-lookup"><span data-stu-id="e2c46-179">See also</span></span>

[<span data-ttu-id="e2c46-180">Új vagy módosult elemek a Human Resources szolgáltatásban</span><span class="sxs-lookup"><span data-stu-id="e2c46-180">What's new or changed in Human Resources</span></span>](hr-admin-whats-new.md)</br>
[<span data-ttu-id="e2c46-181">A Dynamics 365 Human Resources 2019 második kiadási hullámának áttekintése</span><span class="sxs-lookup"><span data-stu-id="e2c46-181">Overview of Dynamics 365 Human Resources 2019 release wave 2</span></span>](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[<span data-ttu-id="e2c46-182">Rendelés frissítése</span><span class="sxs-lookup"><span data-stu-id="e2c46-182">Update process</span></span>](hr-admin-setup-update-process.md)</br>
[<span data-ttu-id="e2c46-183">Szolgáltatások kezelése</span><span class="sxs-lookup"><span data-stu-id="e2c46-183">Manage features</span></span>](hr-admin-manage-features.md)