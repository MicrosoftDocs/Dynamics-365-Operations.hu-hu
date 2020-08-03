---
title: Új vagy módosult elemek a Dynamics 365 Human Resources szolgáltatásban (2020. február 25.)
description: Ez a cikk a Microsoft Dynamics 365 Human Resources új vagy módosított funkcióit írja le.
author: Darinkramer
manager: AnnBe
ms.date: 02/25/2020
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
ms.search.validFrom: 2020-02-25
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e5bc232bef257e757086d37d56b0f68b80114749
ms.sourcegitcommit: bd9ff0d28718d535356ffbe1cffaaf60310dd430
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/13/2020
ms.locfileid: "3555075"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-february-25-2020"></a><span data-ttu-id="fe119-103">Új vagy módosult elemek a Dynamics 365 Human Resources szolgáltatásban (2020. február 25.)</span><span class="sxs-lookup"><span data-stu-id="fe119-103">What's new or changed in Dynamics 365 Human Resources (February 25, 2020)</span></span>

<span data-ttu-id="fe119-104">Ez a cikk a Dynamics 365 Human Resources szolgáltatásban található új vagy módosított funkciókat írja le.</span><span class="sxs-lookup"><span data-stu-id="fe119-104">This article describes features that are either new or changed in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="fe119-105">A változtatások a 8.1.2927-es buildszámra vonatkoznak.</span><span class="sxs-lookup"><span data-stu-id="fe119-105">Changes apply to build number 8.1.2927.</span></span> <span data-ttu-id="fe119-106">A néhány fejlécben látható, zárójelben lévő számok az LCS támogatási számaira vonatkoznak referenciaképpen.</span><span class="sxs-lookup"><span data-stu-id="fe119-106">The numbers in parentheses in some headings refer to LCS support numbers for reference.</span></span>

## <a name="enable-case-management-navigation-and-data-management-framework-dmf-entity-414754"></a><span data-ttu-id="fe119-107">Az Esetkezelési navigáció és az adatkezelési keretrendszer (DMF) entitás engedélyezése (414754)</span><span class="sxs-lookup"><span data-stu-id="fe119-107">Enable Case Management navigation and data management framework (DMF) entity (414754)</span></span>

<span data-ttu-id="fe119-108">Ez az előzetes funkció további navigálást tesz lehetővé az esetkezelési esetekhez.</span><span class="sxs-lookup"><span data-stu-id="fe119-108">This preview feature enables additional navigation to case management cases.</span></span> <span data-ttu-id="fe119-109">Ezt az előnézeti funkciót engedélyezheti a **Szolgáltatások kezelése** munkaterületen.</span><span class="sxs-lookup"><span data-stu-id="fe119-109">You can enable this preview feature in the **Feature Management** workspace.</span></span> <span data-ttu-id="fe119-110">Ezek a menüelemek a **Megfelelés** munkaterületen jelennek meg a Dynamics 365 Human Resources alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="fe119-110">These menu items appear in the **Compliance** workspace of Dynamics 365 Human Resources.</span></span> <span data-ttu-id="fe119-111">Ezzel a módosítással a Humán erőforrások hozzáférhet:</span><span class="sxs-lookup"><span data-stu-id="fe119-111">With this change, Human Resources can access:</span></span>

- <span data-ttu-id="fe119-112">Az összes eset</span><span class="sxs-lookup"><span data-stu-id="fe119-112">All cases</span></span>
- <span data-ttu-id="fe119-113">Saját esetek</span><span class="sxs-lookup"><span data-stu-id="fe119-113">My cases</span></span>
- <span data-ttu-id="fe119-114">Saját nyitott esetek</span><span class="sxs-lookup"><span data-stu-id="fe119-114">My open cases</span></span>
- <span data-ttu-id="fe119-115">Saját késedelmes esetek</span><span class="sxs-lookup"><span data-stu-id="fe119-115">My overdue cases</span></span>
- <span data-ttu-id="fe119-116">Munkafolyamat révén hozzám rendelt esetek</span><span class="sxs-lookup"><span data-stu-id="fe119-116">Cases assigned to me through workflow</span></span>

<span data-ttu-id="fe119-117">Ezekkel az új esetnézetekkel együtt az **Eset részletei** DMF entitás is elérhetővé vált.</span><span class="sxs-lookup"><span data-stu-id="fe119-117">Along with these new views into cases, the **Case detail** DMF entity is also available.</span></span>

## <a name="enable-relationship-definitions-in-global-address-bbook-414762"></a><span data-ttu-id="fe119-118">Kapcsolati definíciók engedélyezése a globális címtárban (414762)</span><span class="sxs-lookup"><span data-stu-id="fe119-118">Enable Relationship definitions in global address bBook (414762)</span></span>

<span data-ttu-id="fe119-119">A kapcsolatok most engedélyezve vannak a globális címjegyzékben.</span><span class="sxs-lookup"><span data-stu-id="fe119-119">Relationships are now enabled in the global address book.</span></span> <span data-ttu-id="fe119-120">Az eheti kiadás előtt a **Kapcsolat** adatterület minden rendszer által definiált kapcsolatot megjelenített.</span><span class="sxs-lookup"><span data-stu-id="fe119-120">Prior to this week's release, the **Relationship** fact box displayed any system-defined relationships.</span></span> <span data-ttu-id="fe119-121">Immár a kapcsolatokat a globális címjegyzék lapon definiálhatja.</span><span class="sxs-lookup"><span data-stu-id="fe119-121">Now you can define those relationships within the global address book page.</span></span>

## <a name="a-position-can-be-removed-when-active-compensation-records-exist-for-the-position-414568"></a><span data-ttu-id="fe119-122">A beosztás eltávolítható, ha a beosztáshoz aktív kompenzációs rekordok léteznek (414568)</span><span class="sxs-lookup"><span data-stu-id="fe119-122">A position can be removed when active compensation records exist for the position (414568)</span></span>

<span data-ttu-id="fe119-123">Ezzel a módosítással figyelmeztetés jelenik meg, amikor egy beosztást megkísérel törölni, és egy dolgozónak aktív kompenzációs rekordja van ehhez a beosztáshoz.</span><span class="sxs-lookup"><span data-stu-id="fe119-123">With this change, a warning appears when you attempt to delete a position and a worker has an active compensation record for that same position.</span></span> <span data-ttu-id="fe119-124">Ha ez történik, akkor a beosztás eltávolítása előtt frissíteni kell az alkalmazott fix kompenzációs rekordját.</span><span class="sxs-lookup"><span data-stu-id="fe119-124">When this happens, you must update the employee fixed compensation record before removing the position.</span></span>

## <a name="performance-review-workflow-occasionally-adds-sign-offs-from-people-who-are-not-part-of-the-process-414171"></a><span data-ttu-id="fe119-125">A teljesítmény-felülvizsgálati munkafolyamat időnként hozzáadja nyugtázási műveleteket olyan személyektől, akik nem részei a folyamatnak (414171)</span><span class="sxs-lookup"><span data-stu-id="fe119-125">Performance review workflow occasionally adds sign-offs from people who are not part of the process (414171)</span></span>

<span data-ttu-id="fe119-126">Ez a módosítás javítja azt a hibát, amelynél a rendszer további jóváhagyási résztvevőket ad hozzá a teljesítmény-ellenőrzéshez.</span><span class="sxs-lookup"><span data-stu-id="fe119-126">This change corrects an issue where additional sign-off participants are added to the performance review.</span></span>

## <a name="worker-position-assignment-not-created-in-common-data-service-when-selected-on-the-new-worker-dialog-413479"></a><span data-ttu-id="fe119-127">A dolgozói beosztás társítása nem lett létrehozva a Common Data Service alkalmazásban, amikor ki lett választva az új dolgozó párbeszédpanelén (413479)</span><span class="sxs-lookup"><span data-stu-id="fe119-127">Worker position assignment not created in Common Data Service when selected on the New Worker dialog (413479)</span></span>

<span data-ttu-id="fe119-128">Ez a módosítás javítja azt a hibát, amikor új dolgozót vesz fel, és az új belépőt egy beosztáshoz rendeli hozzá az **Új dolgozó** párbeszédpanelen.</span><span class="sxs-lookup"><span data-stu-id="fe119-128">This change corrects an issue when hiring a new worker and assigning the new hire to a position through the **New worker** dialog.</span></span> <span data-ttu-id="fe119-129">Immár beosztás-hozzárendelés tükröződik a Common Data Service szolgáltatásban is.</span><span class="sxs-lookup"><span data-stu-id="fe119-129">Now the position assignment is reflected in Common Data Service.</span></span>

## <a name="coming-soon"></a><span data-ttu-id="fe119-130">Hamarosan</span><span class="sxs-lookup"><span data-stu-id="fe119-130">Coming soon</span></span>

### <a name="updated-common-data-service-solution"></a><span data-ttu-id="fe119-131">Common Data Service megoldás frissítve</span><span class="sxs-lookup"><span data-stu-id="fe119-131">Updated Common Data Service solution</span></span>

<span data-ttu-id="fe119-132">Az új Common Data Service megoldás hamarosan a következő változtatásokkal érhető el:</span><span class="sxs-lookup"><span data-stu-id="fe119-132">A new Common Data Service solution will be available soon with the following changes:</span></span>

| <span data-ttu-id="fe119-133">Leírás</span><span class="sxs-lookup"><span data-stu-id="fe119-133">Description</span></span> | <span data-ttu-id="fe119-134">Visszajáró</span><span class="sxs-lookup"><span data-stu-id="fe119-134">Change</span></span> |
| ----------------------------------------- | --- |
| <span data-ttu-id="fe119-135">**Feladat/pozíció** entitás módosításai</span><span class="sxs-lookup"><span data-stu-id="fe119-135">**Job/Position** entity changes</span></span> | <span data-ttu-id="fe119-136">**Kompenzációs régió** hozzáadása</span><span class="sxs-lookup"><span data-stu-id="fe119-136">**Compensation region** added</span></span></br><span data-ttu-id="fe119-137">**Pénzügyi dimenziók** hozzáadása</span><span class="sxs-lookup"><span data-stu-id="fe119-137">**Financial dimensions** added</span></span> |
| <span data-ttu-id="fe119-138">**Dolgozó** entitás módosításai</span><span class="sxs-lookup"><span data-stu-id="fe119-138">**Worker** entity changes</span></span> | <span data-ttu-id="fe119-139">**Névsorrend** hozzáadása</span><span class="sxs-lookup"><span data-stu-id="fe119-139">**Name sequence** added</span></span></br><span data-ttu-id="fe119-140">**Otthonról dolgozik** hozzáadása</span><span class="sxs-lookup"><span data-stu-id="fe119-140">**Works from home** added</span></span></br><span data-ttu-id="fe119-141">**Nyelv** hozzáadása</span><span class="sxs-lookup"><span data-stu-id="fe119-141">**Language** added</span></span></br><span data-ttu-id="fe119-142">**Szolgálati idő dátuma** hozzáadása</span><span class="sxs-lookup"><span data-stu-id="fe119-142">**Seniority date** added</span></span></br><span data-ttu-id="fe119-143">**Évforduló dátuma** hozzáadása</span><span class="sxs-lookup"><span data-stu-id="fe119-143">**Anniversary date** added</span></span></br><span data-ttu-id="fe119-144">**Eredeti felvételi dátum** hozzáadása</span><span class="sxs-lookup"><span data-stu-id="fe119-144">**Original hire date** added</span></span> |
| <span data-ttu-id="fe119-145">**Foglalkoztatás** entitás módosításai</span><span class="sxs-lookup"><span data-stu-id="fe119-145">**Employment** entity changes</span></span> | <span data-ttu-id="fe119-146">**Pénzügyi dimenziók** hozzáadása</span><span class="sxs-lookup"><span data-stu-id="fe119-146">**Financial dimensions** added</span></span></br><span data-ttu-id="fe119-147">**Felmondás oka** hozzáadása</span><span class="sxs-lookup"><span data-stu-id="fe119-147">**Termination reason** added</span></span></br><span data-ttu-id="fe119-148">**Megszűnés dátuma** az **Áttérési dátumtól** átnevezve</span><span class="sxs-lookup"><span data-stu-id="fe119-148">**Termination date** renamed from **Transition date**</span></span></br><span data-ttu-id="fe119-149">**Próbaidős dátum** hozzáadása</span><span class="sxs-lookup"><span data-stu-id="fe119-149">**Probation date** added</span></span> |
| <span data-ttu-id="fe119-150">**Dolgozó címe** entitás módosításai</span><span class="sxs-lookup"><span data-stu-id="fe119-150">**Worker address** entity changes</span></span> | <span data-ttu-id="fe119-151">**Utca és házszám** hozzáadása</span><span class="sxs-lookup"><span data-stu-id="fe119-151">**Street address** added</span></span></br><span data-ttu-id="fe119-152">**1. címsor**, **2. címsor** és **3. címsor** megjelölve megszűnésre</span><span class="sxs-lookup"><span data-stu-id="fe119-152">**Address line 1**, **Address line 2**, and **Address line 3** marked for deprecation</span></span> |
| <span data-ttu-id="fe119-153">Új változó kompenzációs beállítási entitások</span><span class="sxs-lookup"><span data-stu-id="fe119-153">New variable compensation setup entities</span></span> | <span data-ttu-id="fe119-154">**Változó kompenzációs konstrukció típusa**</span><span class="sxs-lookup"><span data-stu-id="fe119-154">**Compensation variable plan type**</span></span></br><span data-ttu-id="fe119-155">**Változó kompenzációs konstrukció**</span><span class="sxs-lookup"><span data-stu-id="fe119-155">**Compensation variable plan**</span></span></br><span data-ttu-id="fe119-156">**Kilépési szabályok**</span><span class="sxs-lookup"><span data-stu-id="fe119-156">**Vesting rules**</span></span></br><span data-ttu-id="fe119-157">**Változó kompenzációs konstrukció szintje**</span><span class="sxs-lookup"><span data-stu-id="fe119-157">**Compensation variable plan level**</span></span> |
| <span data-ttu-id="fe119-158">Új **Dolgozói naptár – foglalkoztatás** entitás</span><span class="sxs-lookup"><span data-stu-id="fe119-158">New **Worker calendar employment** entity</span></span> | <span data-ttu-id="fe119-159">**Munkanaptár-entitás** hozzáadva</span><span class="sxs-lookup"><span data-stu-id="fe119-159">**Work calendar entity** added</span></span> |
| <span data-ttu-id="fe119-160">Új **Bérlista szerinti beosztás részletei** entitás</span><span class="sxs-lookup"><span data-stu-id="fe119-160">New **Payroll position detail** entity</span></span> | <span data-ttu-id="fe119-161">**Bérlista szerinti beosztás** részletei</span><span class="sxs-lookup"><span data-stu-id="fe119-161">**Payroll position detail** added</span></span> |
| <span data-ttu-id="fe119-162">Új **Beosztás** entitás</span><span class="sxs-lookup"><span data-stu-id="fe119-162">New **Title** entity</span></span> | <span data-ttu-id="fe119-163">**Beosztás** hozzáadása</span><span class="sxs-lookup"><span data-stu-id="fe119-163">**Title** added.</span></span> <span data-ttu-id="fe119-164">Az új **Cím** entitást a Human Resources és a Common Data Service közötti szinkronizálási folyamatában fog szerepelni.</span><span class="sxs-lookup"><span data-stu-id="fe119-164">The new **Title** entity will be included in the sync process between Human Resources and Common Data Service.</span></span> <span data-ttu-id="fe119-165">Kezdetben nem lesz hivatkozva a **Beosztás** vagy a **Feladat** entitásból.</span><span class="sxs-lookup"><span data-stu-id="fe119-165">It won't be initially referenced from **Job Position** or **Job** entities.</span></span> |

<span data-ttu-id="fe119-166">Az elkövetkezendő hetekben ezek az entitásmódosítások minden környezetben elérhetők lesznek.</span><span class="sxs-lookup"><span data-stu-id="fe119-166">Over the next few weeks, these entity changes will be available in all environments.</span></span> <span data-ttu-id="fe119-167">A legújabb Common Data Service megoldás manuális telepítése a Human Resourcesbe:</span><span class="sxs-lookup"><span data-stu-id="fe119-167">To manually install the latest Common Data Service solution for Human Resources:</span></span>

1.  <span data-ttu-id="fe119-168">Ugorjon a [Power Platform Adminisztrációs központba](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="fe119-168">Go to the [Power Platform Admin Center](https://admin.powerplatform.microsoft.com).</span></span>

2.  <span data-ttu-id="fe119-169">Válassza a **Környezetek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="fe119-169">Select **Environments**.</span></span>

3.  <span data-ttu-id="fe119-170">Keresse meg a frissíteni kívánt környezetet.</span><span class="sxs-lookup"><span data-stu-id="fe119-170">Find the environment you want to upgrade.</span></span> <span data-ttu-id="fe119-171">Ennek meg kell egyeznie a **Környezet nevével** a **Common Data Service információk** szakaszban a Human Resources **Névjegy** képernyőjén.</span><span class="sxs-lookup"><span data-stu-id="fe119-171">This should correspond to **Environment name** in the **Common Data Service information** section in the **About** form in Human Resources.</span></span>

4.  <span data-ttu-id="fe119-172">A környezet adatainak megtekintéséhez válassza ki a környezetet.</span><span class="sxs-lookup"><span data-stu-id="fe119-172">Select the environment to view the environment details.</span></span>

5.  <span data-ttu-id="fe119-173">Válassza ki a **Megoldások kezelése** elemet a felső műveletsávból.</span><span class="sxs-lookup"><span data-stu-id="fe119-173">In the action bar at the top, select **Manage Solutions**.</span></span> <span data-ttu-id="fe119-174">A rendszer egy új böngészőablakot nyit meg, és megnyitja a **Dynamics 365 felügyeleti központot** a környezete kontextusában.</span><span class="sxs-lookup"><span data-stu-id="fe119-174">A new browser window will open and navigate to **Dynamics 365 Administration Center** in the context of your environment.</span></span>

6.  <span data-ttu-id="fe119-175">A **Megoldás** listán válassza a **Dynamics 365 Human Resources horgony** elemet.</span><span class="sxs-lookup"><span data-stu-id="fe119-175">In the **Solution** list, select **Dynamics 365 Human Resources Anchor**.</span></span>

7.  <span data-ttu-id="fe119-176">Válassza a **Frissítés** parancsot a legújabb megoldás alkalmazásához.</span><span class="sxs-lookup"><span data-stu-id="fe119-176">Select **Upgrade** to apply the latest solution.</span></span>

## <a name="in-preview"></a><span data-ttu-id="fe119-177">Előnézetben</span><span class="sxs-lookup"><span data-stu-id="fe119-177">In preview</span></span>

<span data-ttu-id="fe119-178">A következő előzetes funkciók érhetők el 2020. február 3-tól váltak elérhetővé:</span><span class="sxs-lookup"><span data-stu-id="fe119-178">The following preview features became available on February 3, 2020:</span></span>

- <span data-ttu-id="fe119-179">**Szabadság és távollét előzetes funkciói** – További tudnivalók: [Szabadság és távollét előzetes funkciói](hr-leave-and-absence-overview.md?leave-and-absence-preview-features).</span><span class="sxs-lookup"><span data-stu-id="fe119-179">**Leave and absence preview features** - For more information, see [Leave and absence preview features](hr-leave-and-absence-overview.md?leave-and-absence-preview-features).</span></span>

- <span data-ttu-id="fe119-180">**Juttatáskezelés előzetes funkciói** – További tudnivalók, beleértve az ismert problémákat: [Juttatáskezelés – áttekintése](hr-benefits-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="fe119-180">**Benefits management preview feature** - For more information, including known issues, see [Benefits management overview](hr-benefits-management-overview.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="fe119-181">Lásd még</span><span class="sxs-lookup"><span data-stu-id="fe119-181">See also</span></span>

[<span data-ttu-id="fe119-182">Új vagy módosult elemek a Human Resources szolgáltatásban</span><span class="sxs-lookup"><span data-stu-id="fe119-182">What's new or changed in Human Resources</span></span>](hr-admin-whats-new.md)</br>
[<span data-ttu-id="fe119-183">A Dynamics 365 Human Resources 2019 második kiadási hullámának áttekintése</span><span class="sxs-lookup"><span data-stu-id="fe119-183">Overview of Dynamics 365 Human Resources 2019 release wave 2</span></span>](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[<span data-ttu-id="fe119-184">Rendelés frissítése</span><span class="sxs-lookup"><span data-stu-id="fe119-184">Update process</span></span>](hr-admin-setup-update-process.md)</br>
[<span data-ttu-id="fe119-185">Szolgáltatások kezelése</span><span class="sxs-lookup"><span data-stu-id="fe119-185">Manage features</span></span>](hr-admin-manage-features.md)