---
title: Rendelés frissítése
description: A Microsoft Dynamics 365 Human Resources teljes mértékben „szoftver szolgáltatásként” (SaaS) elven működik, amely folyamatos, érintés nélküli szolgáltatásfrissítéseket és platformmódosításokat tartalmaz.
author: andreabichsel
ms.date: 09/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-27
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2466c53885340991aeeb0a07af83517473b332b6
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/18/2021
ms.locfileid: "6053635"
---
# <a name="update-process"></a><span data-ttu-id="2855a-103">Rendelés frissítése</span><span class="sxs-lookup"><span data-stu-id="2855a-103">Update process</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="2855a-104">A Microsoft Dynamics 365 Human Resources teljes mértékben „szoftver szolgáltatásként” (SaaS) elven működik, amely folyamatos, érintés nélküli szolgáltatásfrissítéseket tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="2855a-104">Microsoft Dynamics 365 Human Resources is a true software as a service (SaaS) that provides continuous, touchless service updates.</span></span> <span data-ttu-id="2855a-105">Ezek a frissítések olyan alkalmazás-és platformmódosításokat tartalmaznak, amelyek kritikus fontosságú javításokat biztosítanak a szolgáltatáshoz, többek között szabályozói frissítéseket.</span><span class="sxs-lookup"><span data-stu-id="2855a-105">These updates contain both application and platform changes that often provide critical improvements to the service, including regulatory updates.</span></span>

## <a name="update-policy"></a><span data-ttu-id="2855a-106">Frissítési irányelv</span><span class="sxs-lookup"><span data-stu-id="2855a-106">Update policy</span></span>

<span data-ttu-id="2855a-107">A frissítések rendszeres ütemben jelennek meg minden környezethez.</span><span class="sxs-lookup"><span data-stu-id="2855a-107">Updates are released on a regular cadence to all environments.</span></span> <span data-ttu-id="2855a-108">A Human Resources támogatását a [Microsoft Lifecycle irányelv](https://support.microsoft.com/hub/4095338/microsoft-lifecycle-policy) szabályozza, amely egységes és kiszámítható útmutatást nyújt a termék elérhetőségével kapcsolatos támogatásról.</span><span class="sxs-lookup"><span data-stu-id="2855a-108">Human Resources is supported according to the [Microsoft Lifecycle policy](https://support.microsoft.com/hub/4095338/microsoft-lifecycle-policy), which provides consistent and predictable guidelines for the availability of support.</span></span>

## <a name="release-cadence"></a><span data-ttu-id="2855a-109">A kiadások ütemezése</span><span class="sxs-lookup"><span data-stu-id="2855a-109">Release cadence</span></span> 

<span data-ttu-id="2855a-110">A Human Resources szolgáltatás frissítései automatikusan alkalmazva vannak az összes környezetre.</span><span class="sxs-lookup"><span data-stu-id="2855a-110">Human Resources updates are applied to all environments automatically.</span></span> <span data-ttu-id="2855a-111">A Human Resources szolgáltatáshoz kétféle kiadást biztosítunk:</span><span class="sxs-lookup"><span data-stu-id="2855a-111">Human Resources provides two types of releases:</span></span>

- <span data-ttu-id="2855a-112">**Szolgáltatásfrissítések**: Hibajavításokat és új funkciókat tartalmazó frissítések kéthetente jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="2855a-112">**Service updates**: Updates occur every two weeks that include bug fixes and new features.</span></span> <span data-ttu-id="2855a-113">A kiadott szolgáltatásfrissítések tartalmazzák a megfelelő platformfrissítéseket is.</span><span class="sxs-lookup"><span data-stu-id="2855a-113">Service updates also include applicable Platform updates when they release.</span></span> <span data-ttu-id="2855a-114">A platformfrissítéseinek kiadásainak ütemezésével kapcsolatos tájékoztatást lásd: [3. táblázat: Platformkiadások](../fin-ops-core/dev-itpro/migration-upgrade/versions-update-policy.md#table-3-platform-releases).</span><span class="sxs-lookup"><span data-stu-id="2855a-114">To get an idea of when Platform updates are released, see [Table 3: Platform releases](../fin-ops-core/dev-itpro/migration-upgrade/versions-update-policy.md#table-3-platform-releases).</span></span> <span data-ttu-id="2855a-115">A kétheti frissítések egy szakaszos, globális bevezetés keretében jelennek meg a régiókban.</span><span class="sxs-lookup"><span data-stu-id="2855a-115">Biweekly updates have a staged global rollout across regions.</span></span> <span data-ttu-id="2855a-116">A kétheti frissítésekkel kapcsolatos további tudnivalókat lásd: [Újdonságok és változások: Dynamics 365 Human Resources](hr-admin-whats-new.md).</span><span class="sxs-lookup"><span data-stu-id="2855a-116">For more information about biweekly updates, see [What's new or changed in Dynamics 365 Human Resources](hr-admin-whats-new.md).</span></span>

    <span data-ttu-id="2855a-117">Ha nincs eltérő értesítés, az összes támogatott adatközpont kéthetente frissül.</span><span class="sxs-lookup"><span data-stu-id="2855a-117">All supported data centers update every two weeks, unless otherwise noted.</span></span> <span data-ttu-id="2855a-118">A kéthetes frissítések között az Egyesült Államok, Ausztrália, Európa, az Egyesült Királyság, Ázsia és Kanada régiói szerepelnek.</span><span class="sxs-lookup"><span data-stu-id="2855a-118">US, Australia, Europe, UK, Asia, and Canada regions are included in biweekly updates.</span></span> 

- <span data-ttu-id="2855a-119">A **Dataverse megoldás frissítései**: Ezek frissítések kb. hat hetente jelennek meg, szükség szerint.</span><span class="sxs-lookup"><span data-stu-id="2855a-119">**Dataverse solution updates**: These updates occur approximately every six weeks, as needed.</span></span> <span data-ttu-id="2855a-120">Új entitásokat tartalmaz, valamint a Dataverse meglévő entitásainak módosításait.</span><span class="sxs-lookup"><span data-stu-id="2855a-120">They include new entities and changes to existing entities in Dataverse.</span></span> <span data-ttu-id="2855a-121">Ezek a frissítések ugyanazon régiókba irányulnak, mint a kétheti frissítések, és kb. hat hetet vesz igénybe, hogy az összes adatközpontban megtörténjen a replikálásuk.</span><span class="sxs-lookup"><span data-stu-id="2855a-121">These updates release to the same regions as the biweekly updates, and they take about six weeks to replicate through all data centers.</span></span> <span data-ttu-id="2855a-122">A megoldások frissítései követhetik a kétheti szolgáltatásfrissítéseket, de nem feltétlenül.</span><span class="sxs-lookup"><span data-stu-id="2855a-122">Solution updates may or may not align with biweekly service updates.</span></span>

> [!NOTE]
> <span data-ttu-id="2855a-123">A megoldásfrissítések az összes adatközpontban elérhetők a kiadásuk után.</span><span class="sxs-lookup"><span data-stu-id="2855a-123">Solution updates are available on all data centers once they're released.</span></span> <span data-ttu-id="2855a-124">Ha nem szeretné megvárni a frissítések automatikus replikálását, manuálisan is alkalmazhatja azokat bármilyen környezetben, bármelyik adatközpontban.</span><span class="sxs-lookup"><span data-stu-id="2855a-124">If you don't want to wait for the updates to replicate automatically, you can manually apply these updates on any environment in any data center.</span></span>

<span data-ttu-id="2855a-125">Szükség esetén a Human Resources szolgáltatás a következő típusú javításokat is biztosítja:</span><span class="sxs-lookup"><span data-stu-id="2855a-125">When needed, Human Resources also provides the following types of fixes:</span></span>

- <span data-ttu-id="2855a-126">**Javítás (gyorsjavítás)**: Olyan hibajavítások, amelyek a kétheti szolgáltatásfrissítési kiadásokkal vagy azoktól külön jelennek meg</span><span class="sxs-lookup"><span data-stu-id="2855a-126">**Revision (hotfix)**: Bug fixes that can occur either with or apart from a biweekly service update release</span></span>

- <span data-ttu-id="2855a-127">**Vészhelyzeti javítás**: Proaktív és reaktív gyorsjavítások, amelyek különállóak, csak a konfiguráció vagy csak a kód módosításait tartalmazzál az élő webhelyek hibáinak megoldásához, és a kétheti szolgáltatásfrissítésektől függetlenül is megjelenhetnek</span><span class="sxs-lookup"><span data-stu-id="2855a-127">**Emergency fix**: Proactive and reactive hotfixes that are standalone in nature, can include configuration-only or code changes to resolve live site issues, and can occur apart from a biweekly service update release</span></span>

<span data-ttu-id="2855a-128">A kiadások felülvizsgálata, tesztelése és ellenőrzése belső környezetben történik.</span><span class="sxs-lookup"><span data-stu-id="2855a-128">Releases are reviewed, tested, and validated on an internal environment.</span></span> <span data-ttu-id="2855a-129">A buildek jóváhagyása után következik a termelési környezetben történő felhasználásuk.</span><span class="sxs-lookup"><span data-stu-id="2855a-129">After builds are signed off, they're then deployed to production.</span></span>

## <a name="release-cadence-exceptions-in-2021"></a><span data-ttu-id="2855a-130">Kiadási ütemezést érintő kivételek 2021-ban</span><span class="sxs-lookup"><span data-stu-id="2855a-130">Release cadence exceptions in 2021</span></span>

<span data-ttu-id="2855a-131">A munkaszüneti napok figyelembe vételéhez a 2021. novemberi és decemberi kiadások ütemezése a következő:</span><span class="sxs-lookup"><span data-stu-id="2855a-131">To account for holidays, the release schedule for November and December 2021 is as follows:</span></span>

- <span data-ttu-id="2855a-132">Novemberi kiadás: november 1. – november 14.</span><span class="sxs-lookup"><span data-stu-id="2855a-132">November release: November 1 - November 14</span></span>
- <span data-ttu-id="2855a-133">Decemberi kiadás: November 29. – December 12.</span><span class="sxs-lookup"><span data-stu-id="2855a-133">December release: November 29 - December 12</span></span>
 
<span data-ttu-id="2855a-134">A kéthetes kiadási ütemezés a szokásos módon fog folytatódni 2022. január 10-én.</span><span class="sxs-lookup"><span data-stu-id="2855a-134">The two-week release cadence will resume as usual on January 10, 2022.</span></span>

## <a name="communications"></a><span data-ttu-id="2855a-135">Tájékoztatás</span><span class="sxs-lookup"><span data-stu-id="2855a-135">Communications</span></span>

<span data-ttu-id="2855a-136">A következő helyeken tudhatja meg, hogy milyen munkák vannak folyamatban a Human Resources szolgáltatással kapcsolatban, és mit adtunk már ki:</span><span class="sxs-lookup"><span data-stu-id="2855a-136">You can find out what's in the works for Human Resources and what we've released in the following locations:</span></span>

- [<span data-ttu-id="2855a-137">Dynamics 365 Human Resources ütemterv</span><span class="sxs-lookup"><span data-stu-id="2855a-137">Dynamics 365 Human Resources roadmap</span></span>](https://dynamics.microsoft.com/roadmap/human-resources/)

- [<span data-ttu-id="2855a-138">Dynamics 365 programverzióra vonatkozó kiadási tervek</span><span class="sxs-lookup"><span data-stu-id="2855a-138">Dynamics 365 Release Plans</span></span>](/dynamics365/release-plans/)

- [<span data-ttu-id="2855a-139">Új vagy módosult elemek a Dynamics 365 Human Resources szolgáltatásban</span><span class="sxs-lookup"><span data-stu-id="2855a-139">What's new or changed in Dynamics 365 Human Resources</span></span>](hr-admin-whats-new.md)

- <span data-ttu-id="2855a-140">[Megoldáskereső a Lifecycle Servicesben (LCS)](../fin-ops-core/dev-itpro/lifecycle-services/issue-search-lcs.md) (csak a platformmal kapcsolatos hibák esetében)</span><span class="sxs-lookup"><span data-stu-id="2855a-140">[Issue search in Lifecycle Services (LCS)](../fin-ops-core/dev-itpro/lifecycle-services/issue-search-lcs.md) (for Platform-related bugs only)</span></span>

- [<span data-ttu-id="2855a-141">Human Resources blog</span><span class="sxs-lookup"><span data-stu-id="2855a-141">Human Resources blog</span></span>](https://community.dynamics.com/365/talent/b/dynamics365fortalent)

- [<span data-ttu-id="2855a-142">Human Resources Yammer-közössége</span><span class="sxs-lookup"><span data-stu-id="2855a-142">Human Resources Yammer community</span></span>](https://www.yammer.com/dynamicsaxfeedbackprograms/#/threads/inGroup?type=in_group&feedId=10542230)

## <a name="preview-features-in-a-sandbox-environment"></a><span data-ttu-id="2855a-143">Előzetes funkciók tesztkörnyezetben</span><span class="sxs-lookup"><span data-stu-id="2855a-143">Preview features in a sandbox environment</span></span>

<span data-ttu-id="2855a-144">Az előzetes funkciókat tesztkörnyezetben ellenőrizheti, mielőtt engedélyezné azokat a termelési környezetben.</span><span class="sxs-lookup"><span data-stu-id="2855a-144">You can validate preview features in a sandbox environment before enabling them in your production environment.</span></span> <span data-ttu-id="2855a-145">Az új funkciók engedélyezésével kapcsolatos további tudnivalókat lásd: [Funkciókezelés áttekintése](../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="2855a-145">For more information about enabling features, see [Feature management overview](../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span></span>

<span data-ttu-id="2855a-146">Minden új funkció megmarad előzetes verzióban legalább 30 napig, és általában 30-60 napig.</span><span class="sxs-lookup"><span data-stu-id="2855a-146">All new features remain in preview for at least 30 days, and typically 30-60 days.</span></span> <span data-ttu-id="2855a-147">A főbb funkciók általában az előzetes időszakot követően minden év októberében és áprilisában érhetők el.</span><span class="sxs-lookup"><span data-stu-id="2855a-147">Major features are generally available in October and April of each year following the preview period.</span></span> <span data-ttu-id="2855a-148">Amint az új funkciókat a Funkciókezelés munkaterületen látja, be lehet kapcsolni őket.</span><span class="sxs-lookup"><span data-stu-id="2855a-148">As soon as you see new capabilities in the Feature management workspace, you can turn them on.</span></span> <span data-ttu-id="2855a-149">Előfordulhat, hogy egyes funkciók alapértelmezés szerint be vannak kapcsolva.</span><span class="sxs-lookup"><span data-stu-id="2855a-149">Some features may be on by default.</span></span>

<span data-ttu-id="2855a-150">Időnként egy szerves funkció alapértelmezésben be van kapcsolva, de nem kapcsolható ki (például a Funkciókezelési munkaterület).</span><span class="sxs-lookup"><span data-stu-id="2855a-150">At times, an integral feature will be on by default and can't be turned off (for example, the Feature management workspace).</span></span>

<span data-ttu-id="2855a-151">Ha egy szolgáltatás általában elérhető, előfordulhat, hogy a működési környezetben be van kapcsolva vagy ki van kapcsolva.</span><span class="sxs-lookup"><span data-stu-id="2855a-151">Once a feature is generally available, it may be turned on or off in production environments.</span></span> <span data-ttu-id="2855a-152">A funkciókezelés munkaterület jelzi, hogy egy előzetes funkció mikor válik kötelezővé.</span><span class="sxs-lookup"><span data-stu-id="2855a-152">The Feature management workspace indicates when a preview feature will become mandatory.</span></span> <span data-ttu-id="2855a-153">Ez a dátum általában október 1. vagy április 1., hogy a féléves kiadási tervekkel összehangolják.</span><span class="sxs-lookup"><span data-stu-id="2855a-153">This date is usually on October 1 or April 1 to align with the semiannual release plans.</span></span> <span data-ttu-id="2855a-154">Nem kapcsolhatja ki a kötelező funkciókat.</span><span class="sxs-lookup"><span data-stu-id="2855a-154">You can't turn off mandatory features.</span></span> <span data-ttu-id="2855a-155">Amíg nem válik kötelezővé, bármely környezetben ki- és bekapcsolhatja a funkciót.</span><span class="sxs-lookup"><span data-stu-id="2855a-155">Until it becomes mandatory, you can turn a feature on and off in all environments.</span></span>

<span data-ttu-id="2855a-156">Kifejezetten ajánljuk, hogy tesztkörnyezetben vagy próbakörnyezetben tekintse meg ezeket a funkciókat.</span><span class="sxs-lookup"><span data-stu-id="2855a-156">We highly recommend previewing features in a sandbox or trial environment.</span></span> <span data-ttu-id="2855a-157">A legjobb megoldás az, ha másolatot készít a jelenlegi termelési környezetről vagy adatbázisról egy tesztkörnyezetbe, hogy az adataival próbálhassa ki az új szolgáltatásokat.</span><span class="sxs-lookup"><span data-stu-id="2855a-157">It's best to create a copy of your current production environment or database into a sandbox environment so you can get the complete experience of the new features with your data.</span></span>

<span data-ttu-id="2855a-158">A teszt környezet létesítésével kapcsolatos további tudnivalókat lásd: [Létesítés a Human Resources szolgáltatásban](hr-admin-setup-provision.md).</span><span class="sxs-lookup"><span data-stu-id="2855a-158">For more information about provisioning a sandbox environment, see [Provision a Human Resources project](hr-admin-setup-provision.md).</span></span> <span data-ttu-id="2855a-159">A tesztkörnyezet eltávolításának ismertetését lásd: [Példány eltávolítása](hr-admin-setup-remove-instance.md#remove-a-test-drive-environment).</span><span class="sxs-lookup"><span data-stu-id="2855a-159">To remove a test environment, see [Remove an instance](hr-admin-setup-remove-instance.md#remove-a-test-drive-environment).</span></span> 

## <a name="report-bugs"></a><span data-ttu-id="2855a-160">Hibák jelentése</span><span class="sxs-lookup"><span data-stu-id="2855a-160">Report bugs</span></span>

<span data-ttu-id="2855a-161">Az előzetes funkciók tesztelésekor vagy az új képességek kipróbálásakor előfordulhat, hogy olyan elemeket talál, amelyek nem a várt módon működnek.</span><span class="sxs-lookup"><span data-stu-id="2855a-161">While testing preview features or trying new capabilities, you might find items that don't work as expected.</span></span> <span data-ttu-id="2855a-162">A hibákat a [Microsoft Dynamics 365 ügyfélszolgálatának jelentheti](https://dynamics.microsoft.com/support/).</span><span class="sxs-lookup"><span data-stu-id="2855a-162">Please report any bugs through [Microsoft Dynamics 365 support](https://dynamics.microsoft.com/support/).</span></span>

## <a name="see-also"></a><span data-ttu-id="2855a-163">Lásd még</span><span class="sxs-lookup"><span data-stu-id="2855a-163">See also</span></span>

[<span data-ttu-id="2855a-164">Dynamics 365 és Power Platform programverzióra vonatkozó kiadási tervek</span><span class="sxs-lookup"><span data-stu-id="2855a-164">Dynamics 365 and Power Platform Release Plans</span></span>](/dynamics365/release-plans)</br>
[<span data-ttu-id="2855a-165">Új vagy módosult elemek a Dynamics 365 Human Resources szolgáltatásban</span><span class="sxs-lookup"><span data-stu-id="2855a-165">What's new or changed in Dynamics 365 Human Resource</span></span>](hr-admin-whats-new.md)</br>
[<span data-ttu-id="2855a-166">A szoftver életciklusára vonatkozó irányelv</span><span class="sxs-lookup"><span data-stu-id="2855a-166">Software lifecycle policy</span></span>](../fin-ops-core/dev-itpro/migration-upgrade/versions-update-policy.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]