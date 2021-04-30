---
title: Új vagy módosult elemek a Dynamics 365 Human Resources szolgáltatásban (2020. szeptember 16.)
description: Ez a témakör a Microsoft Dynamics 365 Human Resources új vagy módosított szolgáltatásait írja le a 2020. szeptember 16-i kiadásban.
author: jcart1106
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2020-09-16
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 6b07bfb27bbe5e546dac9d72666b3225cc202670
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/13/2021
ms.locfileid: "5890699"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-september-16-2020"></a><span data-ttu-id="d8af8-103">Új vagy módosult elemek a Dynamics 365 Human Resources szolgáltatásban (2020. szeptember 16.)</span><span class="sxs-lookup"><span data-stu-id="d8af8-103">What's new or changed in Dynamics 365 Human Resources (September 16, 2020)</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="d8af8-104">Ez a témakör a Dynamics 365 Human Resources új vagy módosított szolgáltatásait írja le.</span><span class="sxs-lookup"><span data-stu-id="d8af8-104">This topic describes features that are either new or changed in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="d8af8-105">A változtatások a 8.1.3557-es buildszámra vonatkoznak.</span><span class="sxs-lookup"><span data-stu-id="d8af8-105">Changes apply to build number 8.1.3557.</span></span> <span data-ttu-id="d8af8-106">A néhány funkció mellett látható, zárójelben lévő számok tájékoztatásként a Lifecycle Services (LCS) támogatási számaira vonatkoznak.</span><span class="sxs-lookup"><span data-stu-id="d8af8-106">The numbers in parentheses next to some features refer to Lifecycle Services (LCS) support numbers for reference.</span></span>

## <a name="included-in-this-release"></a><span data-ttu-id="d8af8-107">A verzióban megtalálható</span><span class="sxs-lookup"><span data-stu-id="d8af8-107">Included in this release</span></span>

-  [<span data-ttu-id="d8af8-108">Mentett nézetek – általános elérhetőség</span><span class="sxs-lookup"><span data-stu-id="d8af8-108">Saved views - general availability</span></span>](/dynamics365-release-plan/2020wave2/finance-operations/finance-operations-crossapp-capabilities/saved-views--general-availability)<br><span data-ttu-id="d8af8-109">- További információ: [Mentett nézetek](../fin-ops-core/fin-ops/get-started/saved-views.md).</span><span class="sxs-lookup"><span data-stu-id="d8af8-109">- For more information, see [Saved views](../fin-ops-core/fin-ops/get-started/saved-views.md).</span></span> 

- <span data-ttu-id="d8af8-110">A **Pozícióműveletek** képernyő frissített dimenziókat és egy új párbeszédet tartalmaz (469495).</span><span class="sxs-lookup"><span data-stu-id="d8af8-110">The **Position actions** form has an updated dimensions grid and new dialogue (469495).</span></span>

- <span data-ttu-id="d8af8-111">Ha a **Dolgozói adatok elérésének korlátozása** elemet igen értékre állítja **Speciális hozzáférés** elemnél a **Human Resources megosztott paraméterei** juttatások képernyői most csak a megfelelő dolgozókat mutatják (393384).</span><span class="sxs-lookup"><span data-stu-id="d8af8-111">If you set **Restrict access to worker information** to yes in **Advanced access** in **Human Resources Shared parameters**, benefits forms now show only the appropriate workers (393384).</span></span>

- <span data-ttu-id="d8af8-112">Új naptár-generálási beállítások a **WorkCalendar** entitásban (477055):</span><span class="sxs-lookup"><span data-stu-id="d8af8-112">New calendar generation options in the **WorkCalendar** entity (477055):</span></span><br><span data-ttu-id="d8af8-113">- Alapértelmezett befejezési idő</span><span class="sxs-lookup"><span data-stu-id="d8af8-113">- Default ending time</span></span><br><span data-ttu-id="d8af8-114">-    Alapértelmezett kezdési idő</span><span class="sxs-lookup"><span data-stu-id="d8af8-114">-    Default starting time</span></span><br><span data-ttu-id="d8af8-115">- Péntek munkanap</span><span class="sxs-lookup"><span data-stu-id="d8af8-115">-  Is Friday working day</span></span><br><span data-ttu-id="d8af8-116">- Hétfő munkanap</span><span class="sxs-lookup"><span data-stu-id="d8af8-116">-  Is Monday working day</span></span><br><span data-ttu-id="d8af8-117">- Szombat munkanap</span><span class="sxs-lookup"><span data-stu-id="d8af8-117">-  Is Saturday working day</span></span><br><span data-ttu-id="d8af8-118">- Vasárnap munkanap</span><span class="sxs-lookup"><span data-stu-id="d8af8-118">- Is Sunday working day</span></span><br><span data-ttu-id="d8af8-119">- Csütörtök munkanap</span><span class="sxs-lookup"><span data-stu-id="d8af8-119">- Is Thursday working day</span></span><br><span data-ttu-id="d8af8-120">- Kedd munkanap</span><span class="sxs-lookup"><span data-stu-id="d8af8-120">- Is Tuesday working day</span></span><br><span data-ttu-id="d8af8-121">- Szerda munkanap</span><span class="sxs-lookup"><span data-stu-id="d8af8-121">- Is Wednesday working day</span></span><br><span data-ttu-id="d8af8-122">- Munkanaptár ünnepnap-azonosító</span><span class="sxs-lookup"><span data-stu-id="d8af8-122">- Work calendar holiday ID</span></span>

- <span data-ttu-id="d8af8-123">A **LeaveBankTransactionV1** entitás most az okkódot (477823) tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="d8af8-123">The **LeaveBankTransactionV1** entity now includes the reason code (477823).</span></span>

- <span data-ttu-id="d8af8-124">Most mentheti a feladatrögzítéseket (492923).</span><span class="sxs-lookup"><span data-stu-id="d8af8-124">You can now save task recordings (492923).</span></span>

- <span data-ttu-id="d8af8-125">Az adatok mostantól sikeresen közzétéve a **HCMWorkerContactEntity** (427620) entitásból.</span><span class="sxs-lookup"><span data-stu-id="d8af8-125">Data is now published successfully from **HCMWorkerContactEntity** (427620).</span></span>

- <span data-ttu-id="d8af8-126">A **Kompenzáció** gyorslap immár megjelenik a **dolgozói műveletek** képernyőjén az alvállalkozó dolgozótípushoz(482494).</span><span class="sxs-lookup"><span data-stu-id="d8af8-126">The **Compensation** fast tab now displays for the contractor worker type in the **Worker actions** form (482494).</span></span>

- <span data-ttu-id="d8af8-127">A **Fix kompenzáció** beállítása esetén kötelező megadni a **Szint** és a **Csomag** mezőt.</span><span class="sxs-lookup"><span data-stu-id="d8af8-127">The **Level** and **Plan** fields are now mandatory if you set **Fixed compensation**.</span></span> <span data-ttu-id="d8af8-128">Ha üresen hagyja ezeket a mezőket, egy hibaüzenet jelenik meg (482497).</span><span class="sxs-lookup"><span data-stu-id="d8af8-128">An error message displays if you leave these fields blank (482497).</span></span>

- <span data-ttu-id="d8af8-129">A **Konstrukció típusa** mező a **Juttatások** alatt immár egy legördülő lista (488768).</span><span class="sxs-lookup"><span data-stu-id="d8af8-129">The **Plan type** field in **Benefits** is now a dropdown list (488768).</span></span>

- <span data-ttu-id="d8af8-130">A rendszergazdák most értesítést kapnak, ha egy egyéni mezőt törölnek az emberi Human Resources alkalmazásból (481408).</span><span class="sxs-lookup"><span data-stu-id="d8af8-130">System administrators now receive a notification if a custom field is deleted from Human Resources (481408).</span></span>

- <span data-ttu-id="d8af8-131">Az alkalmazotti munkaviszonyának megszüntetése folyamat során a Human Resources a várakozásnak megfelelően működik, és nem változtatja meg a kiválasztott vállalatot a zárolást követően (479877).</span><span class="sxs-lookup"><span data-stu-id="d8af8-131">During the terminate employee process, Human Resources behaves as expected and doesn't change the selected company after appearing to lock (479877).</span></span> 

- <span data-ttu-id="d8af8-132">A vezetők már nem adhatnak hozzá szám oszlopot a személyre szabás segítségével (485317).</span><span class="sxs-lookup"><span data-stu-id="d8af8-132">Managers can no longer add a number column through personalization (485317).</span></span>

- <span data-ttu-id="d8af8-133">A vezetők már nem tudják eltávolítani az adattartomány-szűrőt a lejáró azonosítószámokból (485321).</span><span class="sxs-lookup"><span data-stu-id="d8af8-133">Managers can no longer remove the data range filter from identification numbers expiring (485321).</span></span>

- <span data-ttu-id="d8af8-134">Ha a **Felettes** mező üres, akkor a beosztás részletei továbbra is megjelennek, ha az egérmutatót a beosztásra helyezi (433328).</span><span class="sxs-lookup"><span data-stu-id="d8af8-134">When the **Reports to** field is empty, position details still display when hovering over the position (433328).</span></span>

- <span data-ttu-id="d8af8-135">Az alkalmazottak most már megtekinthetik a juttatási konstrukció adatait az Alkalmazotti önkiszolgáló szolgáltatásban (481676).</span><span class="sxs-lookup"><span data-stu-id="d8af8-135">Employees can now view benefit plan information in Employee self service (481676).</span></span>

- <span data-ttu-id="d8af8-136">Az alkalmazottak most már megtekinthetik az összes regisztrált tanfolyamot (429048).</span><span class="sxs-lookup"><span data-stu-id="d8af8-136">Employees can now see all registered courses (429048).</span></span>

- <span data-ttu-id="d8af8-137">Most korlátozhatja a **Szakmai tanúsítványok** lap megjelenítési beállításait.</span><span class="sxs-lookup"><span data-stu-id="d8af8-137">You can now restrict viewing options for the **Professional certificates** page.</span></span> <span data-ttu-id="d8af8-138">Az aktuális jogi személyre, a dolgozói állapotra és a dolgozó típusára (451501) korlátozhatja megjelenítési beállításokat.</span><span class="sxs-lookup"><span data-stu-id="d8af8-138">You can restrict viewing options to the current legal entity, by worker status, and by worker type (451501).</span></span> 


## <a name="in-preview"></a><span data-ttu-id="d8af8-139">Előnézetben</span><span class="sxs-lookup"><span data-stu-id="d8af8-139">In Preview</span></span>

### <a name="human-resources-app-in-teams"></a><span data-ttu-id="d8af8-140">Human Resources alkalmazás a Teamsben</span><span class="sxs-lookup"><span data-stu-id="d8af8-140">Human Resources app in Teams</span></span>

<span data-ttu-id="d8af8-141">Az alkalmazottak megtekinthetik és kérhetik a munkából való távollétet a Microsoft Teams alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="d8af8-141">Employees can view and request time away from work within Microsoft Teams.</span></span> <span data-ttu-id="d8af8-142">Ezek egy robottal lépnek interakcióba a szabadságkérelmek létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="d8af8-142">They can interact with a bot to create leave requests.</span></span> <span data-ttu-id="d8af8-143">További tájékoztatás:</span><span class="sxs-lookup"><span data-stu-id="d8af8-143">For more information, see:</span></span>

- <span data-ttu-id="d8af8-144">[Alkalmazott szabadsága és távolléte a Microsoft Teams rendszerben](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) a Dynamics 365 2020-as kiadási hullámának 1. csomagjában</span><span class="sxs-lookup"><span data-stu-id="d8af8-144">[Employee leave and absence experience in Microsoft Teams](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) in the Dynamics 365 2020 release wave 1 plan</span></span>
- <span data-ttu-id="d8af8-145">[Human Resources alkalmazás a Teamsben](./hr-admin-teams-leave-app.md) a Human Resources dokumentációjában</span><span class="sxs-lookup"><span data-stu-id="d8af8-145">[Human Resources app in Teams](./hr-admin-teams-leave-app.md) in Human Resources documentation</span></span>

### <a name="human-resources-app-in-teams-preview-features"></a><span data-ttu-id="d8af8-146">Human Resources alkalmazás a Teamsben előzetes funkciók</span><span class="sxs-lookup"><span data-stu-id="d8af8-146">Human Resources app in Teams preview features</span></span>
 
-  <span data-ttu-id="d8af8-147">**Értesítések**: A szabadságkérelmek beküldői és jóváhagyói értesítést kapnak az Emberi erőforrások alkalmazásban a Teamsben.</span><span class="sxs-lookup"><span data-stu-id="d8af8-147">**Notifications**: Submitters and approvers of time-off requests will be notified in the Human Resources app in Teams.</span></span> <span data-ttu-id="d8af8-148">A jóváhagyók jóvá tudják hagyni vagy el tudják utasítani a távolléti kérelmeket.</span><span class="sxs-lookup"><span data-stu-id="d8af8-148">Approvers can approve or deny time-off requests.</span></span> <span data-ttu-id="d8af8-149">A kérelem jóváhagyása vagy elutasítása esetén a beküldő értesítést kap.</span><span class="sxs-lookup"><span data-stu-id="d8af8-149">Submitters will be notified if the request was approved or denied.</span></span> <span data-ttu-id="d8af8-150">További tájékoztatás:</span><span class="sxs-lookup"><span data-stu-id="d8af8-150">For more information, see:</span></span>
   - <span data-ttu-id="d8af8-151">[Alkalmazott szabadsága és távolléte a Microsoft Teams rendszerben](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/employee-leave-absence-experience-teams) a Dynamics 365 2020-as kiadási hullámának 2. csomagjában</span><span class="sxs-lookup"><span data-stu-id="d8af8-151">[Employee leave and absence experience in Microsoft Teams](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/employee-leave-absence-experience-teams) in the Dynamics 365 2020 release wave 2 plan</span></span>
   - <span data-ttu-id="d8af8-152">[Human Resources alkalmazás értesítéseinek engedélyezése a Teamsben](./hr-admin-teams-leave-app.md#enable-notifications-for-the-human-resources-app-in-teams) a Human Resources dokumentációjában</span><span class="sxs-lookup"><span data-stu-id="d8af8-152">[Enable notifications for the Human Resources app in Teams](./hr-admin-teams-leave-app.md#enable-notifications-for-the-human-resources-app-in-teams) in Human Resources documentation</span></span>
   - <span data-ttu-id="d8af8-153">[A Teams értesítéseinek be-és kikapcsolása az egyes felhasználók számára](./hr-admin-teams-leave-app.md#turn-teams-notifications-on-or-off-for-individual-users) a Human Resources dokumentációjában</span><span class="sxs-lookup"><span data-stu-id="d8af8-153">[Turn Teams notifications on or off for individual users](./hr-admin-teams-leave-app.md#turn-teams-notifications-on-or-off-for-individual-users) in Human Resources documentation</span></span>
   - <span data-ttu-id="d8af8-154">[Teams értesítések](./hr-teams-leave-app.md#respond-to-teams-notifications) a Human Resources dokumentációjában</span><span class="sxs-lookup"><span data-stu-id="d8af8-154">[Teams notifications](./hr-teams-leave-app.md#respond-to-teams-notifications) in Human Resources documentation</span></span>
   - <span data-ttu-id="d8af8-155">[A csapat távolléti naptárának megtekintése a](./hr-teams-leave-app.md#view-your-teams-leave-calendar) a Human Resources dokumentációjában</span><span class="sxs-lookup"><span data-stu-id="d8af8-155">[View your team's leave calendar](./hr-teams-leave-app.md#view-your-teams-leave-calendar) in Human Resources documentation</span></span>
 
- <span data-ttu-id="d8af8-156">**Vezetői szabadságnaptár**: A felettesek a naptár nézetben megtekinthetik a beosztottjaik jóváhagyott és függőben lévő távolléteit.</span><span class="sxs-lookup"><span data-stu-id="d8af8-156">**Manager time-off calendar**: Managers can see approved and pending time off for their direct reports in a calendar view.</span></span> <span data-ttu-id="d8af8-157">Ez a nézet annak áttekintését teszi lehetővé, hogy a csapattagok mikor nem dolgoznak.</span><span class="sxs-lookup"><span data-stu-id="d8af8-157">This view provides an easy understanding of when their team members are away from work.</span></span> <span data-ttu-id="d8af8-158">További tájékoztatás:</span><span class="sxs-lookup"><span data-stu-id="d8af8-158">For more information, see:</span></span>
   - <span data-ttu-id="d8af8-159">[Alkalmazott szabadsága és távolléte a Microsoft Teams rendszerben](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/employee-leave-absence-experience-teams) a Dynamics 365 2020-as kiadási hullámának 2. csomagjában</span><span class="sxs-lookup"><span data-stu-id="d8af8-159">[Employee leave and absence experience in Microsoft Teams](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/employee-leave-absence-experience-teams) in the Dynamics 365 2020 release wave 2 plan</span></span>
   - <span data-ttu-id="d8af8-160">[A csapat távolléti naptárának megtekintése a](./hr-teams-leave-app.md#view-your-teams-leave-calendar) a Human Resources dokumentációjában</span><span class="sxs-lookup"><span data-stu-id="d8af8-160">[View your team's leave calendar](./hr-teams-leave-app.md#view-your-teams-leave-calendar) in Human Resources documentation</span></span>

### <a name="configuration-option-to-position-work-items-assigned-to-me-list-477004"></a><span data-ttu-id="d8af8-161">Konfigurációs beállítás a hozzám rendelt munkaelemek lista pozicionálásához (477004)</span><span class="sxs-lookup"><span data-stu-id="d8af8-161">Configuration option to position Work items assigned to me list (477004)</span></span>

<span data-ttu-id="d8af8-162">Most egy új beállítás érhető el, amivel a **Hozzám rendelt munkaelemek** lista az irányítópult jobb oldali oszlopába helyezhető.</span><span class="sxs-lookup"><span data-stu-id="d8af8-162">A new option is now available to position the **Work items assigned to me** list in the right-hand column of the dashboard.</span></span> <span data-ttu-id="d8af8-163">Ezzel a módosítással az összes munkaelem és a teendőlista ugyanazon a területen jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="d8af8-163">With this change, all work items and to do lists display in the same area.</span></span> <span data-ttu-id="d8af8-164">A funkció engedélyezéséhez kapcsolja be az **Előzetes verzió – Munkafolyamat-élmények továbbfejlesztései** lehetőséget a Funkciókezelés modulban.</span><span class="sxs-lookup"><span data-stu-id="d8af8-164">Enable this functionality by turning on **Preview - Workflow experience enhancements** in Feature management.</span></span> <span data-ttu-id="d8af8-165">Az előzetes funkciók bekapcsolásával kapcsolatos további információt lásd a [Szolgáltatások kezelése](hr-admin-manage-features.md) című témakörben.</span><span class="sxs-lookup"><span data-stu-id="d8af8-165">For more information about turning on preview features, see [Manage features](hr-admin-manage-features.md).</span></span>

<span data-ttu-id="d8af8-166">Ez a funkció segíti a személyzeti műveletek képernyőjén megjelenő munkafolyamat-beállításokat is.</span><span class="sxs-lookup"><span data-stu-id="d8af8-166">This feature also promotes the workflow options that appear in the personnel actions forms.</span></span> <span data-ttu-id="d8af8-167">A munkafolyamat-beállítások a gyors hozzáféréshez a művelet gyors lapja fölött is megjelenhetnek.</span><span class="sxs-lookup"><span data-stu-id="d8af8-167">Workflow options also appear above the action fast tab for quick access.</span></span> <span data-ttu-id="d8af8-168">További tájékoztatás:</span><span class="sxs-lookup"><span data-stu-id="d8af8-168">For more information, see:</span></span> 

- <span data-ttu-id="d8af8-169">[A szervezeti és személyzetkezelési munkafolyamatok fejlesztései](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/organization-personnel-management-workflow-experience-enhancements) a Dynamics 365 2020-as 2. kiadási hullám csomagjában</span><span class="sxs-lookup"><span data-stu-id="d8af8-169">[Organization and personnel management workflow experience enhancements](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/organization-personnel-management-workflow-experience-enhancements) in the Dynamics 365 2020 release wave 2 plan</span></span>

![Hozzám rendelt munkatételek](./media/hr-workflow-work-items-assigned-to-me.png)

![Munkafolyamat-elemek gyors elérése](./media/hr-workflow-quick-access.png)

### <a name="leave-and-absence-calendar"></a><span data-ttu-id="d8af8-172">A szabadságok és távollétek naptára</span><span class="sxs-lookup"><span data-stu-id="d8af8-172">Leave and absence calendar</span></span>

<span data-ttu-id="d8af8-173">Ez a kiadás további naptár-beállításokat tartalmaz a szabadság- és a távolléti naptárakhoz.</span><span class="sxs-lookup"><span data-stu-id="d8af8-173">This release includes additional calendar options for leave and absence calendars.</span></span> <span data-ttu-id="d8af8-174">További tájékoztatás: [Csoportos és vállalati naptárak megtekintése](./hr-employee-self-service-calendar.md).</span><span class="sxs-lookup"><span data-stu-id="d8af8-174">For more information, see [View team and company calendars](./hr-employee-self-service-calendar.md).</span></span>

## <a name="coming-soon"></a><span data-ttu-id="d8af8-175">Hamarosan</span><span class="sxs-lookup"><span data-stu-id="d8af8-175">Coming Soon</span></span>

### <a name="checklist-entities-included-in-dataverse"></a><span data-ttu-id="d8af8-176">Ellenőrzőlista-entitások szerepelnek a következőben: Dataverse</span><span class="sxs-lookup"><span data-stu-id="d8af8-176">Checklist entities included in Dataverse</span></span>

<span data-ttu-id="d8af8-177">Az Előkészítés, Felszámolás, Áthelyezések és Üzleti folyamatok hamarosan elérhetők lesznek a Dataverse alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="d8af8-177">Checklist entities for Onboarding, Offboarding, Transfers, and Business processes will be available soon in Dataverse.</span></span>

### <a name="benefits-management-reason-codes"></a><span data-ttu-id="d8af8-178">Juttatások kezelése okkódok</span><span class="sxs-lookup"><span data-stu-id="d8af8-178">Benefits management reason codes</span></span>

<span data-ttu-id="d8af8-179">A juttatáskezelés okkódjai hamarosan kombinálva lesznek a Human Resources meglévő okkódjaival.</span><span class="sxs-lookup"><span data-stu-id="d8af8-179">Benefits management reason codes will soon be combined with existing reason codes in Human Resources.</span></span> <span data-ttu-id="d8af8-180">Ha a Juttatások kezelése modulban több, mint 15 karakterből álló okkódok szerepelnek, akkor az Juttatások kezelése **Okkódok** űrlapján az okkódot maximum 15 karakter hosszúra kell módosítania.</span><span class="sxs-lookup"><span data-stu-id="d8af8-180">If you created reason codes in Benefits management that are over 15 characters, you must change the name of the reason code in the Benefits management **Reason codes** form to be 15 characters or less.</span></span> <span data-ttu-id="d8af8-181">Miután frissítette a nevet, az okkód a Személyzetkezelés modul meglévő okkódok képernyőjén fog megjelenni.</span><span class="sxs-lookup"><span data-stu-id="d8af8-181">After you update the name, the reason code will appear under the existing reason code form in Personnel management.</span></span> <span data-ttu-id="d8af8-182">Ez a változtatás a jövőben elérhető lesz, és nem fogja befolyásolni a meglévő funkciókat.</span><span class="sxs-lookup"><span data-stu-id="d8af8-182">This change will be available in the future and won't affect existing functionality.</span></span>

## <a name="see-also"></a><span data-ttu-id="d8af8-183">Lásd még</span><span class="sxs-lookup"><span data-stu-id="d8af8-183">See also</span></span>

[<span data-ttu-id="d8af8-184">Újdonságok vagy változások a Human Resources szolgáltatásban</span><span class="sxs-lookup"><span data-stu-id="d8af8-184">What's new or changed in Human Resources</span></span>](hr-admin-whats-new.md)</br>
[<span data-ttu-id="d8af8-185">A Dynamics 365 Human Resources 2019 második kiadási hullámának áttekintése</span><span class="sxs-lookup"><span data-stu-id="d8af8-185">Overview of Dynamics 365 Human Resources 2019 release wave 2</span></span>](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[<span data-ttu-id="d8af8-186">Rendelés frissítése</span><span class="sxs-lookup"><span data-stu-id="d8af8-186">Update process</span></span>](hr-admin-setup-update-process.md)</br>
[<span data-ttu-id="d8af8-187">Szolgáltatások kezelése</span><span class="sxs-lookup"><span data-stu-id="d8af8-187">Manage features</span></span>](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
