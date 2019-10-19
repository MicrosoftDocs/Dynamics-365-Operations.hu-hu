---
title: Új vagy módosult elemek a Dynamics 365 Talent szolgáltatásban (2019. március 5.)
description: Ez a témakör a Microsoft Dynamics 365 Talent új vagy módosított szolgáltatásait írja le.
author: Darinkramer
manager: AnnBe
ms.date: 03/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-03-05
ms.dyn365.ops.version: Talent
ms.openlocfilehash: c7ee8f4cf14197d6bd4549741058fc5fe95ae55d
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/24/2019
ms.locfileid: "2026670"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-march-5-2019"></a><span data-ttu-id="516df-103">Új vagy módosult elemek a Dynamics 365 Talent szolgáltatásban (2019. március 5.)</span><span class="sxs-lookup"><span data-stu-id="516df-103">What's new or changed in Dynamics 365 Talent (March 5, 2019)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="516df-104">Ez a témakör a Talent új vagy módosított szolgáltatásait írja le.</span><span class="sxs-lookup"><span data-stu-id="516df-104">This topic describes features that are either new or changed in Talent.</span></span>

## <a name="changes-in-attract"></a><span data-ttu-id="516df-105">Változások az Attract-ben</span><span class="sxs-lookup"><span data-stu-id="516df-105">Changes in Attract</span></span>

### <a name="extending-option-sets-in-attract"></a><span data-ttu-id="516df-106">Beállításkészletek kiterjesztése az Attract alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="516df-106">Extending option sets in Attract</span></span>

<span data-ttu-id="516df-107">Az Attract alkalmazásban, több mezők is van, amely beállításkészlet a Common Data Service szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="516df-107">In Attract, there are multiple fields that are option sets within the Common Data Service.</span></span> <span data-ttu-id="516df-108">Új képességek lettek bevezetve a beállításkészletek kiterjesztésére, kezdve az **Elutasítás** okkód mezővel a **Foglalkoztatási típusa** mezővel, és **Szolgálati idő típusa** mezővel.</span><span class="sxs-lookup"><span data-stu-id="516df-108">New capabilities have been introduced to extend the option sets, beginning with the **Rejection** reason field, **Employment type** field, and **Seniority type** field.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="516df-109">Az álláshirdetés a LinkedIn funkcióhoz a **Foglalkoztatási típusa** és **Szolgálati idő típusa** mezők szükségesek az **Állás részletei** lapon.</span><span class="sxs-lookup"><span data-stu-id="516df-109">The job posting to LinkedIn functionality requires the use of the **Employment type** and **Seniority type** fields on the **Job details** page.</span></span> <span data-ttu-id="516df-110">Ezen a mezők az alapértelmezett értékekeit a LinkedIn támogatja és meg lesznek jelenítve az állás feladásakor.</span><span class="sxs-lookup"><span data-stu-id="516df-110">The default values in these fields are supported by LinkedIn and are displayed when the job is posted.</span></span> <span data-ttu-id="516df-111">Ha állásokat tesz közzé a LinkedIn-en, és ezen a mezők a meglévő beállításkészlet-értékeit módosítja, az állás továbbra is közzé lesz téve, de LinkedIn nem jeleníti meg az egyéni **Foglalkoztatási típusa** és **Szolgálati idő típusa** értékeket.</span><span class="sxs-lookup"><span data-stu-id="516df-111">If you are posting jobs to LinkedIn and you modify the existing option set values for these fields, the job will still post, but LinkedIn will not display the custom **Employment type** and **Seniority type** values.</span></span>

## <a name="changes-in-onboarding"></a><span data-ttu-id="516df-112">Változások az Onboarding alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="516df-112">Changes in Onboarding</span></span>

### <a name="private-preview-for-onboard-teams"></a><span data-ttu-id="516df-113">Privát előnézet Onboard csoportoknak</span><span class="sxs-lookup"><span data-stu-id="516df-113">Private preview for Onboard teams</span></span>
<span data-ttu-id="516df-114">Mostantól egyszerűen megoszthatja a teljes szervezeten belüli a sablonokat az együttműködéshez.</span><span class="sxs-lookup"><span data-stu-id="516df-114">You can now easily share and collaborate on templates across your entire organization.</span></span> <span data-ttu-id="516df-115">További tudnivalókért lásd: [Bevált gyakorlatok megosztása a szervezetben az Onboard Teams használatával](https://docs.microsoft.com/business-applications-release-notes/April19/dynamics365-talent/onboard/share-best-practices-teams).</span><span class="sxs-lookup"><span data-stu-id="516df-115">For more information, see [Share best practices across your organization using Onboard Teams](https://docs.microsoft.com/business-applications-release-notes/April19/dynamics365-talent/onboard/share-best-practices-teams).</span></span>

### <a name="private-preview-for-assignee-placeholders"></a><span data-ttu-id="516df-116">A megbízott helyőrzők privát előnézete</span><span class="sxs-lookup"><span data-stu-id="516df-116">Private preview for assignee placeholders</span></span>
<span data-ttu-id="516df-117">A tevékenységeket az egyes személyek helyett személyekhez rendelheti, így gazdagítva sablonjait.</span><span class="sxs-lookup"><span data-stu-id="516df-117">You can enrich your templates by assigning activities to roles instead of individuals.</span></span> <span data-ttu-id="516df-118">A Szerepkörök majd személyekhez lesznek rendelve az útmutató a létrehozásának időpontjában.</span><span class="sxs-lookup"><span data-stu-id="516df-118">Roles are then assigned to individuals at the time of guide creation.</span></span> <span data-ttu-id="516df-119">További tudnivalókért lásd: [Az útmutatófelügyeleti tevékenységek egyszerűsítése tevékenységek hozzárendelésével a szerepkörökhöz](https://docs.microsoft.com/business-applications-release-notes/April19/dynamics365-talent/onboard/assign-activities-roles).</span><span class="sxs-lookup"><span data-stu-id="516df-119">For more information, see [Streamline guide administration by assigning activities to roles](https://docs.microsoft.com/business-applications-release-notes/April19/dynamics365-talent/onboard/assign-activities-roles).</span></span>

## <a name="changes-in-core-hr"></a><span data-ttu-id="516df-120">A Core HR módosításai</span><span class="sxs-lookup"><span data-stu-id="516df-120">Changes in Core HR</span></span>
<span data-ttu-id="516df-121">**Build 8.1.2178**</span><span class="sxs-lookup"><span data-stu-id="516df-121">**Build 8.1.2178**</span></span>

### <a name="configure-workflow-to-auto-approve-or-follow-workflow-when-an-hr-or-line-manager-submits-or-updates-time-off-requests"></a><span data-ttu-id="516df-122">Munkafolyamat konfigurálása a munkafolyamat automatikus jóváhagyásához vagy , amikor egy HR vezető vagy a vezető elküldi vagy frissíti a szabadságkérelmeket</span><span class="sxs-lookup"><span data-stu-id="516df-122">Configure workflow to auto-approve or follow workflow when an HR or line manager submits or updates time off requests</span></span>
<span data-ttu-id="516df-123">Új munkafolyamat-feltételek lettek hozzáadva, amelyek megengedik a szabadságkérelmek automatikus jóváhagyását, ha azt az alkalmazott vezetője vagy a HR nyújtja be.</span><span class="sxs-lookup"><span data-stu-id="516df-123">New workflow conditions have been added to allow for leave requests to be automatically approved if submitted by an employee’s manager or by HR.</span></span> <span data-ttu-id="516df-124">Automatikus jóváhagyás elérésének a egyik módja a munkafolyamatban egy automatikus művelet engedélyezése a munkafolyamat jóváhagyása során.</span><span class="sxs-lookup"><span data-stu-id="516df-124">One way to achieve this auto-approval on a workflow is to enable an automatic action on the workflow approval.</span></span>

<span data-ttu-id="516df-125">A hozzáadott feltételek a következők:</span><span class="sxs-lookup"><span data-stu-id="516df-125">The conditions that have been added include:</span></span>

- <span data-ttu-id="516df-126">Beküldte - A rendszer felhasználója azonosítójának meghatározásához használható, aki beküldte a munkafolyamat iránti kérelmet.</span><span class="sxs-lookup"><span data-stu-id="516df-126">Submitted by - Used to evaluate the system user ID of the user who submitted the request to workflow.</span></span>
- <span data-ttu-id="516df-127">Beküldve a következő nevében – Annak meghatározásához, hogy a szabadságkérelmet a kérelemhez társított dolgozó nevében küldték-e be.</span><span class="sxs-lookup"><span data-stu-id="516df-127">Submitted on behalf of - Used to evaluate if the leave request was submitted on behalf of the worker associated to the request.</span></span>
- <span data-ttu-id="516df-128">Beküldte az emberi erőforrások – Annak meghatározására, hogy a munkafolyamat-kérelmet beküldő rendszerfelhasználó Emberi erőforrás szerepkörű e.</span><span class="sxs-lookup"><span data-stu-id="516df-128">Submitted by human resources - Used to evaluate if the system user who submitted the request to workflow is in a Human Resources role.</span></span>
- <span data-ttu-id="516df-129">Vezető küldte be – Annak meghatározásához, hogy a felhasználó aki beküldte a szabadságkérelmet a munkafolyamathoz kéréshez társított dolgozó vezetőeje-e.</span><span class="sxs-lookup"><span data-stu-id="516df-129">Submitted by manager - Used to evaluate if the user who submitted the leave request to workflow is a line hierarchy manager of the worker associated to the request.</span></span>

### <a name="enable-employee-fixed-compensation-for-future-position-assignments"></a><span data-ttu-id="516df-130">Az alkalmazott fix kompenzációjánek engedélyezése jövőbeli beosztás-hozzárendelésekhez</span><span class="sxs-lookup"><span data-stu-id="516df-130">Enable employee fixed compensation for future position assignments</span></span>
<span data-ttu-id="516df-131">Jellemző, hogy azon alkalmazottak, akik a szervezethez csatlakoznak jövőbeni kezdési dátummal rendelkeznek.</span><span class="sxs-lookup"><span data-stu-id="516df-131">It is typical for employees to join an organization with a future start date.</span></span> <span data-ttu-id="516df-132">Ez a módosítás lehetővé teszi fix kompenzáció meghatározását jövőbeni beosztás-hozzárendelésekkel rendelkező alkalmazottakhoz.</span><span class="sxs-lookup"><span data-stu-id="516df-132">This change enables defining fixed compensation for employees with future position assignments.</span></span>

### <a name="position-payroll-fields-are-blank-when-editing-the-position"></a><span data-ttu-id="516df-133">A Beosztásbérlista mezők üresek a beosztás módosításakor.</span><span class="sxs-lookup"><span data-stu-id="516df-133">Position Payroll fields are blank when editing the position</span></span>
<span data-ttu-id="516df-134">Ezzel a módosítással a meglévő beosztások módosításának kérelme során a bérlista mezők most alapértelmezés szerint az aktuális értékeket tartalmazzák.</span><span class="sxs-lookup"><span data-stu-id="516df-134">With this change, when requesting changes to existing positions, the payroll fields will now default to the current values.</span></span>

### <a name="other-miscellaneous-bug-fixes"></a><span data-ttu-id="516df-135">Egyéb vegyes hibajavítások</span><span class="sxs-lookup"><span data-stu-id="516df-135">Other miscellaneous bug fixes</span></span>
<span data-ttu-id="516df-136">További kisebb hibajavítások ebben a verzióban.</span><span class="sxs-lookup"><span data-stu-id="516df-136">Other minor bug fixes are included with this release.</span></span>

### <a name="upgrade-to-common-data-service"></a><span data-ttu-id="516df-137">Frissítés Common Data Service megoldásra</span><span class="sxs-lookup"><span data-stu-id="516df-137">Upgrade to Common Data Service</span></span>
<span data-ttu-id="516df-138">A Common Data Service frissítés határideje gyorsan közeledik.</span><span class="sxs-lookup"><span data-stu-id="516df-138">Deadlines to upgrade to Common Data Service are quickly approaching.</span></span> <span data-ttu-id="516df-139">Jelentkezzen a PowerApps felügyeleti központba annak meghatározásához, hogy kell-e az adatbázist frissíteni.</span><span class="sxs-lookup"><span data-stu-id="516df-139">Sign in to the PowerApps Admin center to determine if your database needs to be upgraded.</span></span> <span data-ttu-id="516df-140">Határidőkkel és frissítéséhez szükségesek további lépésekkel kapcsolatos tudnivalókat lásd: [Frissítés a Common Data Service](https://docs.microsoft.com/common-data-service/upgradecds/introduction-upgrade-cds) megoldásra.</span><span class="sxs-lookup"><span data-stu-id="516df-140">For more information about deadlines and necessary steps to upgrade, see [Upgrade to Common Data Service](https://docs.microsoft.com/common-data-service/upgradecds/introduction-upgrade-cds).</span></span>

## <a name="coming-soon"></a><span data-ttu-id="516df-141">Hamarosan</span><span class="sxs-lookup"><span data-stu-id="516df-141">Coming soon</span></span>

###  <a name="advanced-compensation-security-fixed-and-variable"></a><span data-ttu-id="516df-142">Haladó kompenzációs biztonsági (fix és változó)</span><span class="sxs-lookup"><span data-stu-id="516df-142">Advanced compensation security (fixed and variable)</span></span>
<span data-ttu-id="516df-143">Számos vállalatnál a kompenzációkért és juttatásokért felelős vezetők csak bizonyos kompenzációs rekordokat érhetnek el, például a vezetők és a területi alapú alkalmazottak rekordjait.</span><span class="sxs-lookup"><span data-stu-id="516df-143">In many organizations, compensation and benefits managers can only access certain compensation records, such as records for executives or regional-based employees.</span></span> <span data-ttu-id="516df-144">Ez a módosítás lehetővé teszi a kompenzációs tervek kezelését és karbantartását a szervezet különböző alkalmazottcsoportjaihoz.</span><span class="sxs-lookup"><span data-stu-id="516df-144">With this change, you can manage and maintain the compensation plans for different employee populations in the organization.</span></span> <span data-ttu-id="516df-145">A fix és változó kompenzációs tervek, amelyek hozzárendelhetők biztonsági szerepkörökhöz, határozzák meg a hozzáférést ezekhez a tervekhez és a hozzájuk kapcsolódó alkalmazotti adatokhoz, például fizetés és bónuszrekordok.</span><span class="sxs-lookup"><span data-stu-id="516df-145">Fixed and variable plans can be assigned security roles, which will determine the access to the plans and the employee data related to the plans, such as salary or bonus records.</span></span> <span data-ttu-id="516df-146">Csak a szerepkörök, amelyek rendelkeznek a meghatározott hozzáféréssel tudnak kompenzációt feldolgozni azokhoz az alkalmazottakhoz.</span><span class="sxs-lookup"><span data-stu-id="516df-146">Only the roles with the given access will be able to process compensation for those employees.</span></span>

###  <a name="platform-update-24-for-finance-and-operations"></a><span data-ttu-id="516df-147">Platform update 24 a Finance and Operations szolgáltatáshoz</span><span class="sxs-lookup"><span data-stu-id="516df-147">Platform update 24 for Finance and Operations</span></span>
<span data-ttu-id="516df-148">A Finance and Operations 24-es platformfrissítésével kapcsolatos részleteket lásd a [Újdonságok és változások a Dynamics 365 for Finance and Operations 24. platformfrissítésében (2019. március)](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-24).</span><span class="sxs-lookup"><span data-stu-id="516df-148">For additional details about Platform update 24 for Finance and Operations, see [What's new or changed in Finance and Operations platform update 24 (March 2019)](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-24).</span></span>
