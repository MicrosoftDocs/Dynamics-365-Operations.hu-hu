---
title: A Dynamics 365 for Talent új és módosult elemei (2019. június 11.)
description: Ez a témakör a Microsoft Dynamics 365 for Talent új vagy módosított szolgáltatásait írja le.
author: Darinkramer
manager: AnnBe
ms.date: 06/11/2019
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
ms.search.validFrom: 2019-06-11
ms.dyn365.ops.version: Talent
ms.openlocfilehash: a1413ea43e852c78ede227b69c0f49c07944a872
ms.sourcegitcommit: 45f8cea6ac75bd2f4187380546a201c056072c59
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/12/2019
ms.locfileid: "1741618"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-june-11-2019"></a><span data-ttu-id="2bddb-103">A Dynamics 365 for Talent új és módosult elemei (2019. június 11.)</span><span class="sxs-lookup"><span data-stu-id="2bddb-103">What's new or changed in Dynamics 365 for Talent (June 11, 2019)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="2bddb-104">Ez a témakör a Microsoft Dynamics 365 for Talent új vagy módosított szolgáltatásait írja le.</span><span class="sxs-lookup"><span data-stu-id="2bddb-104">This topic describes features that are either new or changed in Microsoft Dynamics 365 for Talent.</span></span>

## <a name="changes-in-attract"></a><span data-ttu-id="2bddb-105">Változások az Attract-ben</span><span class="sxs-lookup"><span data-stu-id="2bddb-105">Changes in Attract</span></span>

### <a name="search-engine-optimization-for-job-posts"></a><span data-ttu-id="2bddb-106">Keresőmotor-optimalizálás az álláshirdetésekhez</span><span class="sxs-lookup"><span data-stu-id="2bddb-106">Search engine optimization for job posts</span></span>

<span data-ttu-id="2bddb-107">Ha bekapcsolja a **Keresőmotor-optimalizálást** a Dynamics 365 for Talent: Attract adminisztrátori központjában, az Attract felkéri a Google Indexing alkalmazásprogramozási felületét (API), hogy térképezze fel a weboldalt, amikor Ön új feladatot tesz közzé vagy aktivál, illetve meglévő feladatot frissít.</span><span class="sxs-lookup"><span data-stu-id="2bddb-107">After you turn on **Search Engine Optimization** in the Dynamics 365 for Talent: Attract Admin center, Attract informs the Google Indexing application programming interface (API) to crawl the webpage whenever you activate and post a new job or update an existing job.</span></span> <span data-ttu-id="2bddb-108">Ilyen módon a feladat megjelenik a Google és más keresőmotorok keresési eredményei között.</span><span class="sxs-lookup"><span data-stu-id="2bddb-108">In this way, the job will appear in the search results for Google and other search engines.</span></span>

<span data-ttu-id="2bddb-109">Hasonlóképpen, ha eltávolít egy feladatot, az Attract jelzi az Indexing API-nak, hogy az eltávolított feladat a későbbiekben ne jelenjen meg a keresési eredmények között.</span><span class="sxs-lookup"><span data-stu-id="2bddb-109">Likewise, whenever you unpost a job, Attract informs the Indexing API, so that the unposted job will stop appearing in search results.</span></span>

> [!NOTE]
> <span data-ttu-id="2bddb-110">Az internetes térképezőrobotok nem csak egy megadott időszakban térképezik fel a weblapokat vagy frissítik a keresési eredményeket.</span><span class="sxs-lookup"><span data-stu-id="2bddb-110">Web crawlers don't have a defined timeframe for crawling webpages or updating search results.</span></span>

## <a name="coming-soon-in-attract"></a><span data-ttu-id="2bddb-111">Hamarosan az Attract alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="2bddb-111">Coming soon in Attract</span></span>

### <a name="job-approvals-appear-on-the-home-page"></a><span data-ttu-id="2bddb-112">A feladatok jóváhagyása megjelenik a kezdőképernyőn</span><span class="sxs-lookup"><span data-stu-id="2bddb-112">Job approvals appear on the home page</span></span>

<span data-ttu-id="2bddb-113">A jóváhagyások az irányítópult **Jóváhagyások** szakaszában jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="2bddb-113">Approvals appear in an **Approvals** section on the dashboard.</span></span> <span data-ttu-id="2bddb-114">A jóváhagyók megtekinthetik a rájuk váró jóváhagyásokat az **Önhöz rendelt** részen, ahol látható a feladat azonosítója és neve, a többi jóváhagyó és a feladat hozzárendelésének dátuma.</span><span class="sxs-lookup"><span data-stu-id="2bddb-114">Approvers can review their approvals under **Assigned to you**, which shows the job ID, the job title, other approvers, and the date when the job was assigned.</span></span> <span data-ttu-id="2bddb-115">Azok a felhasználók, akik elküldenek jóváhagyásra egy feladatot, az **Ön által küldött kérések** szakaszban látják a feladatot, ahol megjelennek azok a jóváhagyók, akiknek még jóvá kell hagyniuk a feladatot.</span><span class="sxs-lookup"><span data-stu-id="2bddb-115">Users who submit a job for approval can review their jobs under **Requested by you**, which shows the approvers who must still approve the submitted job.</span></span>

## <a name="changes-in-onboard"></a><span data-ttu-id="2bddb-116">Változások az Onboard alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="2bddb-116">Changes in Onboard</span></span>

<span data-ttu-id="2bddb-117">Ebben a verzióban kisebb hibajavítások találhatók a Dynamics 365 for Talent: Onboard alkalmazáshoz.</span><span class="sxs-lookup"><span data-stu-id="2bddb-117">This release includes minor bug fixes for Dynamics 365 for Talent: Onboard.</span></span>

## <a name="changes-in-core-hr"></a><span data-ttu-id="2bddb-118">A Core HR módosításai</span><span class="sxs-lookup"><span data-stu-id="2bddb-118">Changes in Core HR</span></span>

<span data-ttu-id="2bddb-119">A szakaszban ismertetett módosítások a 8.1.2337-ös buildre vonatkoznak.</span><span class="sxs-lookup"><span data-stu-id="2bddb-119">The changes that are described in this section apply to build number 8.1.2337.</span></span>

### <a name="platform-update-27"></a><span data-ttu-id="2bddb-120">27-as platformfrissítés</span><span class="sxs-lookup"><span data-stu-id="2bddb-120">Platform update 27</span></span>

<span data-ttu-id="2bddb-121">További információ a 27-es platformfrissítésről (Platform update 27): [Előzetes funkciók a Dynamics 365 for Finance and Operations platform update 27 verziójában (2019. június)](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-27).</span><span class="sxs-lookup"><span data-stu-id="2bddb-121">For more details about Platform update 27, see [Preview features in Dynamics 365 for Finance and Operations platform update 27 (June 2019)](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-27).</span></span>

### <a name="feature-management-workspace-in-talent"></a><span data-ttu-id="2bddb-122">A funkciókezelési munkaterület a Talentben</span><span class="sxs-lookup"><span data-stu-id="2bddb-122">Feature management workspace in Talent</span></span>

<span data-ttu-id="2bddb-123">A **Rendszerfelügyelet** **Funkció kezelése** munkaterületén megtekintheti, engedélyezheti, letilthatja és ütemezheti az egyes kiadások funkcióit.</span><span class="sxs-lookup"><span data-stu-id="2bddb-123">The **Feature management** workspace in **System administration** lets you view, enable, disable, and schedule features that have been delivered in each release.</span></span> <span data-ttu-id="2bddb-124">Alapértelmezés szerint az új szolgáltatások ki vannak kapcsolva.</span><span class="sxs-lookup"><span data-stu-id="2bddb-124">By default, new features are turned off.</span></span> <span data-ttu-id="2bddb-125">A **Funkció kezelése** munkaterületen bekapcsolhatja a szolgáltatásokat, és megtekintheti a rájuk vonatkozó dokumentációt.</span><span class="sxs-lookup"><span data-stu-id="2bddb-125">You can use the **Feature management** workspace to turn them on and view the documentation for them.</span></span>

### <a name="common-data-service-entity-support-for-custom-fields"></a><span data-ttu-id="2bddb-126">Common Data Service entitás-támogatás egyéni mezőkhöz</span><span class="sxs-lookup"><span data-stu-id="2bddb-126">Common Data Service entity support for custom fields</span></span>

<span data-ttu-id="2bddb-127">A Kiállító szervezet entitás már támogatja az egyéni mezőket.</span><span class="sxs-lookup"><span data-stu-id="2bddb-127">The Issuing agency entity now supports custom fields.</span></span>

### <a name="new-common-data-service-entities"></a><span data-ttu-id="2bddb-128">Új Common Data Service-entitások</span><span class="sxs-lookup"><span data-stu-id="2bddb-128">New Common Data Service entities</span></span>

<span data-ttu-id="2bddb-129">Hozzáadtuk a feladatcsoport entitást.</span><span class="sxs-lookup"><span data-stu-id="2bddb-129">The Task group entity has been added.</span></span>

## <a name="in-preview"></a><span data-ttu-id="2bddb-130">Előnézetben</span><span class="sxs-lookup"><span data-stu-id="2bddb-130">In preview</span></span>

### <a name="preview-features-will-be-enabled-only-in-sandbox-environments"></a><span data-ttu-id="2bddb-131">Az előnézeti szolgáltatások csak a Védőfal környezetekben használhatók.</span><span class="sxs-lookup"><span data-stu-id="2bddb-131">Preview features will be enabled only in sandbox environments</span></span>

<span data-ttu-id="2bddb-132">További információ a módosítások közzétételéről: [A Talent létesítése](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).</span><span class="sxs-lookup"><span data-stu-id="2bddb-132">For more information about how changes are published, see [Provision Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).</span></span>

<span data-ttu-id="2bddb-133">Amikor új Talent-példányt hoz létre, jelezheti, hogy a példány Termelési vagy Védőfal típusú legyen-e.</span><span class="sxs-lookup"><span data-stu-id="2bddb-133">When you provision a new instance of Talent, you can indicate whether the instance type is Production or Sandbox.</span></span> <span data-ttu-id="2bddb-134">A Védőfal típusú példányokkal az új szolgáltatások korai tesztelése végezhető el.</span><span class="sxs-lookup"><span data-stu-id="2bddb-134">The Sandbox instance type allows for early testing of new features.</span></span> <span data-ttu-id="2bddb-135">Minden létező Talent példányt a **Termelési** példány típusára lesz frissítve.</span><span class="sxs-lookup"><span data-stu-id="2bddb-135">All existing Talent instances will be updated to the **Production** instance type.</span></span> <span data-ttu-id="2bddb-136">Ha a meglévő példányokat **Védőfal** típusúra szeretné frissíteni, kérje az [ügyfélszolgálat](https://docs.microsoft.com/dynamics365/unified-operations/talent/talent-support) segítségét.</span><span class="sxs-lookup"><span data-stu-id="2bddb-136">If you want one of your existing instances to be updated to the **Sandbox** instance type, contact [Support](https://docs.microsoft.com/dynamics365/unified-operations/talent/talent-support) to initiate the change request.</span></span>

### <a name="restrict-the-leave-types-in-time-off-requests"></a><span data-ttu-id="2bddb-137">A szabadság típusának korlátozása a távolléti kérelmekben</span><span class="sxs-lookup"><span data-stu-id="2bddb-137">Restrict the leave types in time-off requests</span></span>

<span data-ttu-id="2bddb-138">A szervezetek számos különböző típusú szabadságot tudnak nyújtani az alkalmazottak számára.</span><span class="sxs-lookup"><span data-stu-id="2bddb-138">Organizations can offer many types of leave to employees.</span></span> <span data-ttu-id="2bddb-139">Előfordulhat azonban, hogy egyes szabadságtípusok esetében nem megfelelő megoldás, hogy az alkalmazottak küldjenek be távolléti kérelmet.</span><span class="sxs-lookup"><span data-stu-id="2bddb-139">However, it might not be appropriate for employees to submit time-off requests for some leave types.</span></span> <span data-ttu-id="2bddb-140">Lehetséges, hogy ezeket a szabadságtípusokat az emberi erőforrások részlege (HR) kezeli.</span><span class="sxs-lookup"><span data-stu-id="2bddb-140">Those leave types might be managed by Human resources (HR) instead.</span></span> <span data-ttu-id="2bddb-141">Ebben a kiadásban konfigurálhatja, hogy az alkalmazottak milyen szabadságtípusokhoz küldhetnek távolléti kérelmet.</span><span class="sxs-lookup"><span data-stu-id="2bddb-141">In this release, you can configure which leave types employees can submit time-off requests for.</span></span> 

## <a name="coming-soon-in-core-hr"></a><span data-ttu-id="2bddb-142">Hamarosan bevezetjük a Core HR-ban</span><span class="sxs-lookup"><span data-stu-id="2bddb-142">Coming soon in Core HR</span></span>

### <a name="view-extended-information-about-report-performance-in-manager-self-service"></a><span data-ttu-id="2bddb-143">A jelentések részletes teljesítményadatainak megtekintése az önkiszolgáló kezelői rendszerben</span><span class="sxs-lookup"><span data-stu-id="2bddb-143">View extended information about report performance in manager self-service</span></span>

<span data-ttu-id="2bddb-144">Egy új beállítással a vezetők mind a közvetlen beosztottak, mind a közvetett beosztottak teljesítményét megtekinthetik.</span><span class="sxs-lookup"><span data-stu-id="2bddb-144">A new option will let managers view the performance of both their direct reports and their extended reports.</span></span> <span data-ttu-id="2bddb-145">Jelenleg a közvetlen felettesek hozzárendelhetnek teljesítménycélokat és frissíthetik őket, illetve olyan új értékeléseket adhatnak ki.</span><span class="sxs-lookup"><span data-stu-id="2bddb-145">Currently, line managers can assign and update performance goals and issue new reviews.</span></span> <span data-ttu-id="2bddb-146">Ezenkívül a közvetlen felettesek és alkalmazottaik karbantarthatják és frissíthetik a teljesítménymutatókat, így garantálható, hogy a teljesítmény ellenőrzési folyamata gördülékenyen megy majd.</span><span class="sxs-lookup"><span data-stu-id="2bddb-146">In addition, direct managers and their employees can maintain and update performance journals to help guarantee that the performance review process goes smoothly.</span></span> <span data-ttu-id="2bddb-147">A módosítás végrehajtásakor a vezetők a közvetlen beosztottakon kívül a bővített jelentések teljesítménnyel kapcsolatos adatait is megtekinthetik és karbantartják.</span><span class="sxs-lookup"><span data-stu-id="2bddb-147">When this change is implemented, managers will be able to view and maintain performance-related information for their extended reports in addition to their direct reports.</span></span>

### <a name="print-performance-reviews"></a><span data-ttu-id="2bddb-148">Teljesítményértékelések nyomtatása</span><span class="sxs-lookup"><span data-stu-id="2bddb-148">Print performance reviews</span></span>

<span data-ttu-id="2bddb-149">Az alkalmazottak, a vezetők és a HR alkalmazottai kinyomtathatják az alkalmazottak teljesítménykimutatását.</span><span class="sxs-lookup"><span data-stu-id="2bddb-149">Employees, managers, and HR will be able to print an employee's performance review.</span></span>
