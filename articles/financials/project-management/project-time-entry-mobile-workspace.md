---
title: "Projektidő megadása mobil munkaterület"
description: "Ez a témakör a Projektidő megadása mobil munkaterülettel kapcsolatban tartalmaz tájékoztatást. Ez a munkaterület lehetővé teszi a felhasználók számára, hogy beírhassák az időt, és időt takaríthassanak meg egy projektnél mobileszközük használatával."
author: KimANelson
manager: AnnBe
ms.date: 12/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 272101
ms.assetid: 4505f021-b9bb-4b87-be24-6bf0bd88ee60
ms.search.region: Global
ms.search.industry: Service industries
ms.author: knelson
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: HT
ms.sourcegitcommit: 029511634e56aec7fdd91bad9441cd12951fbd8d
ms.openlocfilehash: c264cf76cd16a684bb99697bf6ea166969f760b9
ms.contentlocale: hu-hu
ms.lasthandoff: 01/17/2018

---

# <a name="project-time-entry-mobile-workspace"></a><span data-ttu-id="b3f78-104">Projektidő megadása mobil munkaterület</span><span class="sxs-lookup"><span data-stu-id="b3f78-104">Project time entry mobile workspace</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="b3f78-105">Ez a témakör a **Projektidő megadása** mobil munkaterülettel kapcsolatban tartalmaz tájékoztatást.</span><span class="sxs-lookup"><span data-stu-id="b3f78-105">This topic provides information about the **Project time entry** mobile workspace.</span></span> <span data-ttu-id="b3f78-106">Ez a munkaterület lehetővé teszi a felhasználók számára, hogy beírhassák az időt, és időt takaríthassanak meg egy projektnél mobileszközük használatával.</span><span class="sxs-lookup"><span data-stu-id="b3f78-106">This workspace lets users enter and save time against a project by using their mobile device.</span></span>

<span data-ttu-id="b3f78-107">A mobil munkaterületet a Microsoft Dynamics 365 for Unified Operations mobilalkalmazásban való használatra tervezték.</span><span class="sxs-lookup"><span data-stu-id="b3f78-107">This mobile workspace is intended to be used with the Microsoft Dynamics 365 for Unified Operations mobile app.</span></span> 

## <a name="overview"></a><span data-ttu-id="b3f78-108">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="b3f78-108">Overview</span></span>
<span data-ttu-id="b3f78-109">Napi munkájuk részeként a projektek résztvevői gyakran a helyszínen dolgoznak, vagy az utazáson vesznek részt.</span><span class="sxs-lookup"><span data-stu-id="b3f78-109">As part of their daily work, project resources are often on-site or traveling.</span></span> <span data-ttu-id="b3f78-110">A **Projektidő megadása** mobil munkaterület lehetővé teszi a felhasználók számára, hogy számlázható vagy nem számlázható időt írjanak be projektjükhöz a választott mobileszközön.</span><span class="sxs-lookup"><span data-stu-id="b3f78-110">The **Project time entry** mobile workspace lets users enter their billable or non-billable time against a project on the mobile device of their choice.</span></span> <span data-ttu-id="b3f78-111">Ezért a projekt résztvevői bármikor és bárhol rögzíthetik az időbevitelt.</span><span class="sxs-lookup"><span data-stu-id="b3f78-111">Therefore, project resources can record time entries anytime and anywhere.</span></span> <span data-ttu-id="b3f78-112">Megtekinthetik a már rögzített időbejegyzéseket is.</span><span class="sxs-lookup"><span data-stu-id="b3f78-112">They can also view time entries that have already been recorded.</span></span> 

<span data-ttu-id="b3f78-113">A **Projektidő megadása** mobil munkaterületen a felhasználók a következő feladatokat hajthatják végre:</span><span class="sxs-lookup"><span data-stu-id="b3f78-113">Specifically, in the **Project time entry** mobile workspace, users can perform these tasks:</span></span>

-   <span data-ttu-id="b3f78-114">Bármelyik kiválasztott dátumhoz beírhatja az adott feladatra fordított órák számát.</span><span class="sxs-lookup"><span data-stu-id="b3f78-114">For any selected date, enter the number of hours that you spent on a specific task.</span></span>
-   <span data-ttu-id="b3f78-115">Keresés projektnév vagy vevő alapján, hogy megtalálhassa a projektet, amelynél időt szeretne rögzíteni.</span><span class="sxs-lookup"><span data-stu-id="b3f78-115">Search by project name or customer to find the project to enter time for.</span></span>
-   <span data-ttu-id="b3f78-116">Adja meg az eltöltött időhöz tartozó kategóriát és tevékenységet.</span><span class="sxs-lookup"><span data-stu-id="b3f78-116">Specify the category and activity for the time that you spent.</span></span>
-   <span data-ttu-id="b3f78-117">Rögzítse az időt számlázhatóként vagy nem számlázhatóként a projektnél.</span><span class="sxs-lookup"><span data-stu-id="b3f78-117">Record the time as billable or non-billable for the project.</span></span>
-   <span data-ttu-id="b3f78-118">Nem kötelező: Adjon meg külső vagy belső megjegyzéseket.</span><span class="sxs-lookup"><span data-stu-id="b3f78-118">Optionally enter any external or internal comments.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b3f78-119">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="b3f78-119">Prerequisites</span></span>
<span data-ttu-id="b3f78-120">Az előfeltételek eltérőek a Microsoft Dynamics 365 szervezeténél megvalósított verziójától függően.</span><span class="sxs-lookup"><span data-stu-id="b3f78-120">The prerequisites differ, based on the version of Microsoft Dynamics 365 that has been deployed for your organization.</span></span>

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-for-finance-and-operations-enterprise-edition"></a><span data-ttu-id="b3f78-121">Előfeltételek, ha a Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition kiadást használja</span><span class="sxs-lookup"><span data-stu-id="b3f78-121">Prerequisites if you use Microsoft Dynamics 365 for Finance and Operations, Enterprise edition</span></span>
<span data-ttu-id="b3f78-122">Amennyiben szervezete telepítette a Microsoft Dynamics 365 for Finance and Operations Enterprise Edition rendszert, a rendszergazdának közzé kell tennie a **Projektidő megadása** mobil munkaterület.</span><span class="sxs-lookup"><span data-stu-id="b3f78-122">If Microsoft Dynamics 365 for Finance and Operations, Enterprise edition has been deployed for your organization, the system administrator must publish the **Project time entry** mobile workspace.</span></span> <span data-ttu-id="b3f78-123">Utasításokért lásd: [Mobil munkaterület közzététele](../../dev-itpro/mobile-apps/publish-mobile-workspace.md).</span><span class="sxs-lookup"><span data-stu-id="b3f78-123">For instructions, see [Publish a mobile workspace](../../dev-itpro/mobile-apps/publish-mobile-workspace.md).</span></span>

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-for-operations-version-1611-with-platform-update-3-or-later"></a><span data-ttu-id="b3f78-124">Előfeltételek, ha a Microsoft Dynamics 365 for Finance and Operations, 1611-es verzióját használja a 3-as vagy újabb platformfrissítéssel</span><span class="sxs-lookup"><span data-stu-id="b3f78-124">Prerequisites if you use Microsoft Dynamics 365 for Operations version 1611 with platform update 3 or later</span></span>
<span data-ttu-id="b3f78-125">Ha a Microsoft Dynamics 365 for Operations 1611-es verzióját telepítették a szervezeténél a 3-as vagy újabb platformfrissítéssel, akkor a rendszergazdának a következő előfeltételeket kell teljesítenie.</span><span class="sxs-lookup"><span data-stu-id="b3f78-125">If Microsoft Dynamics 365 for Operations version 1611 with platform update 3 or later has been deployed for your organization, the system administrator must complete the following prerequisites.</span></span> 

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="b3f78-126">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="b3f78-126">Prerequisite</span></span></th>
<th><span data-ttu-id="b3f78-127">Szerep</span><span class="sxs-lookup"><span data-stu-id="b3f78-127">Role</span></span></th>
<th><span data-ttu-id="b3f78-128">Leírás</span><span class="sxs-lookup"><span data-stu-id="b3f78-128">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">

<td><span data-ttu-id="b3f78-129">Telepítse a KB 4018050 programot.</span><span class="sxs-lookup"><span data-stu-id="b3f78-129">Implement KB 4018050.</span></span></td>
<td><span data-ttu-id="b3f78-130">Rendszergazda</span><span class="sxs-lookup"><span data-stu-id="b3f78-130">System administrator</span></span></td>
<td><span data-ttu-id="b3f78-131">A 4018050-es tudásbáziscikk egy X++-frissítés vagy metaadat-gyorsjavítás, amely tartalmazza a <strong>Projektidő megadása</strong> mobil munkaterületet.</span><span class="sxs-lookup"><span data-stu-id="b3f78-131">KB 4018050 is an X++ update or metadata hotfix that contains the <strong>Project time entry</strong> mobile workspace.</span></span> <span data-ttu-id="b3f78-132">A KB 4018050 végrehajtásához a rendszergazdának követnie kell az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="b3f78-132">To implement KB 4018050, your system administrator must follow these steps.</span></span>
<ol>
<li><span data-ttu-id="b3f78-133"><a href="../../dev-itpro/migration-upgrade/download-hotfix-lcs.md">Töltse le a metaadatok gyorsjavítását a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásból</a>.</span><span class="sxs-lookup"><span data-stu-id="b3f78-133"><a href="../../dev-itpro/migration-upgrade/download-hotfix-lcs.md">Download the metadata hotfix from Microsoft Dynamics Lifecycle Services (LCS)</a>.</span></span></li>
<li><span data-ttu-id="b3f78-134"><a href="../../dev-itpro/migration-upgrade/install-metadata-hotfix-package.md">Telepítse a metaadatok gyorsjavítását</a>.</span><span class="sxs-lookup"><span data-stu-id="b3f78-134"><a href="../../dev-itpro/migration-upgrade/install-metadata-hotfix-package.md">Install the metadata hotfix</a>.</span></span></li>
<li><span data-ttu-id="b3f78-135"><a href="../../dev-itpro/deployment/create-apply-deployable-package.md">Hozzon létre egy telepíthető csomagot</a>, amely tartalmazza az <strong>ApplicationSuite</strong> és a <strong>ProjectMobile</strong> modellt, majd töltse fel a telepíthető csomagot az LCS-be.</span><span class="sxs-lookup"><span data-stu-id="b3f78-135"><a href="../../dev-itpro/deployment/create-apply-deployable-package.md">Create a deployable package</a> that contains the <strong>ApplicationSuite</strong> and <strong>ProjectMobile</strong> models, and then upload the deployable package to LCS.</span></span></li>
<li><span data-ttu-id="b3f78-136"><a href="../../dev-itpro/deployment/apply-deployable-package-system.md">Alkalmazza telepíthető csomagot</a>.</span><span class="sxs-lookup"><span data-stu-id="b3f78-136"><a href="../../dev-itpro/deployment/apply-deployable-package-system.md">Apply the deployable package</a>.</span></span></li>

</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="b3f78-137">Tegye közzé a <strong>Projektidő megadása</strong> mobil munkaterületet.</span><span class="sxs-lookup"><span data-stu-id="b3f78-137">Publish the <strong>Project time entry</strong> mobile workspace.</span></span></td>
<td><span data-ttu-id="b3f78-138">Rendszergazda</span><span class="sxs-lookup"><span data-stu-id="b3f78-138">System administrator</span></span></td>
<td><span data-ttu-id="b3f78-139">Lásd: <a href="../../dev-itpro/mobile-apps/publish-mobile-workspace.md">Mobil munkaterület közzététele</a>.</span><span class="sxs-lookup"><span data-stu-id="b3f78-139">See <a href="../../dev-itpro/mobile-apps/publish-mobile-workspace.md">Publish a mobile workspace</a>.</span></span></td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-mobile-app"></a><span data-ttu-id="b3f78-140">A mobilalkalmazás letöltése és telepítése</span><span class="sxs-lookup"><span data-stu-id="b3f78-140">Download and install the mobile app</span></span>

<span data-ttu-id="b3f78-141">Töltse le és telepítse a Dynamics 365 for Unified Operations mobilalkalmazást:</span><span class="sxs-lookup"><span data-stu-id="b3f78-141">Download and install the Dynamics 365 for Unified Operations mobile app:</span></span>

-   [<span data-ttu-id="b3f78-142">Android-telefonok esetében:</span><span class="sxs-lookup"><span data-stu-id="b3f78-142">For Android phones</span></span>](https://go.microsoft.com/fwlink/?linkid=850662)
-   [<span data-ttu-id="b3f78-143">iPhone esetében:</span><span class="sxs-lookup"><span data-stu-id="b3f78-143">For iPhones</span></span>](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a><span data-ttu-id="b3f78-144">Bejelentkezés a mobilalkalmazásba</span><span class="sxs-lookup"><span data-stu-id="b3f78-144">Sign in to the mobile app</span></span>
1.  <span data-ttu-id="b3f78-145">Indítsa el az alkalmazást a mobileszközén.</span><span class="sxs-lookup"><span data-stu-id="b3f78-145">Start the app on your mobile device.</span></span>
2.  <span data-ttu-id="b3f78-146">Adja meg a Dynamics 365 URL-címét.</span><span class="sxs-lookup"><span data-stu-id="b3f78-146">Enter your Dynamics 365 URL.</span></span>
3.  <span data-ttu-id="b3f78-147">Az első bejelentkezéskor a rendszer kéri a felhasználónevet és jelszót.</span><span class="sxs-lookup"><span data-stu-id="b3f78-147">The first time that you sign in, you're prompted for your user name and password.</span></span> <span data-ttu-id="b3f78-148">Adja meg a hitelesítési adatait.</span><span class="sxs-lookup"><span data-stu-id="b3f78-148">Enter your credentials.</span></span>
4.  <span data-ttu-id="b3f78-149">A bejelentkezést követően megjelennek a vállalata rendelkezésre álló munkaterületek.</span><span class="sxs-lookup"><span data-stu-id="b3f78-149">After you sign in, the available workspaces for your company are shown.</span></span> <span data-ttu-id="b3f78-150">Vegye figyelembe, hogy ha a rendszergazda később teszi közzé az új munkaterületet, akkor Önnek frissítenie kell a mobil munkaterületek listáját.</span><span class="sxs-lookup"><span data-stu-id="b3f78-150">Note that if your system administrator publishes a new workspace later, you will have to refresh the list of mobile workspaces.</span></span>

<span data-ttu-id="b3f78-151">[![Lekérés frissítéshez](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)</span><span class="sxs-lookup"><span data-stu-id="b3f78-151">[![Pull to refresh](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)</span></span>

## <a name="enter-time-by-using-the-project-time-entry-mobile-workspace"></a><span data-ttu-id="b3f78-152">Adja meg az időt a Projektidő megadása mobil munkaterület használatával</span><span class="sxs-lookup"><span data-stu-id="b3f78-152">Enter time by using the Project time entry mobile workspace</span></span>
1.  <span data-ttu-id="b3f78-153">A mobileszközön válassza a **Projektidő megadása** munkaterület.</span><span class="sxs-lookup"><span data-stu-id="b3f78-153">On your mobile device, select the **Project time entry** workspace.</span></span>
2.  <span data-ttu-id="b3f78-154">Válassza ki az **Időbejegyzés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b3f78-154">Select **Time entry**.</span></span> <span data-ttu-id="b3f78-155">Megjelennek az aktuális hét naptári dátumai.</span><span class="sxs-lookup"><span data-stu-id="b3f78-155">The calendar dates for the current week are shown.</span></span>
3.  <span data-ttu-id="b3f78-156">Válassza ki a kijelölt dátumnál a **Műveletek** &gt; **Új bejegyzés** pontot.</span><span class="sxs-lookup"><span data-stu-id="b3f78-156">For a selected date, select **Actions** &gt; **New entry**.</span></span>
4.  <span data-ttu-id="b3f78-157">Adja meg a rögzítendő órák számát.</span><span class="sxs-lookup"><span data-stu-id="b3f78-157">Enter the number of hours to record.</span></span>
5.  <span data-ttu-id="b3f78-158">Jelölje ki a projektet az időbejegyzéshez.</span><span class="sxs-lookup"><span data-stu-id="b3f78-158">Select the project for the time entry.</span></span> <span data-ttu-id="b3f78-159">Megjelenik a kapcsolat nélküli használatra az alkalmazásba betöltött projektek listája.</span><span class="sxs-lookup"><span data-stu-id="b3f78-159">A list shows the projects that are loaded into your app for offline use.</span></span> <span data-ttu-id="b3f78-160">Alapértelmezés szerint 50 elem töltődik be, de a fejlesztő módosíthatja ezt a számot.</span><span class="sxs-lookup"><span data-stu-id="b3f78-160">By default, 50 items are loaded, but a developer can change this number.</span></span> <span data-ttu-id="b3f78-161">További információ: lásd: [Mobil munkafelület](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md)</span><span class="sxs-lookup"><span data-stu-id="b3f78-161">For more information, see [Mobile platform](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md).</span></span>
6.  <span data-ttu-id="b3f78-162">Ha a projekt nem szerepel a listán, válassza a **Keresés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b3f78-162">If your project isn't in the list, select **Search**.</span></span> <span data-ttu-id="b3f78-163">Végezhet név szerinti keresést, vagy átválthat a projektnév vagy ügyfél szerinti keresésre.</span><span class="sxs-lookup"><span data-stu-id="b3f78-163">Search by name, or switch to search by project name or customer.</span></span>
7.  <span data-ttu-id="b3f78-164">Válasszon egy kategóriát.</span><span class="sxs-lookup"><span data-stu-id="b3f78-164">Select a category.</span></span> <span data-ttu-id="b3f78-165">Megjelenik a kapcsolat nélküli használatra az alkalmazásba betöltött kategóriák listája.</span><span class="sxs-lookup"><span data-stu-id="b3f78-165">A list shows the categories that are loaded into your app for offline use.</span></span> <span data-ttu-id="b3f78-166">Alapértelmezés szerint 50 elem töltődik be, de a fejlesztő módosíthatja ezt a számot.</span><span class="sxs-lookup"><span data-stu-id="b3f78-166">By default, 50 items are loaded, but a developer can change this number.</span></span> <span data-ttu-id="b3f78-167">További információ: lásd: [Mobil munkafelület](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md)</span><span class="sxs-lookup"><span data-stu-id="b3f78-167">For more information, see [Mobile platform](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md).</span></span>
8.  <span data-ttu-id="b3f78-168">Ha a kategória nem szerepel a listán, válassza a **Keresés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b3f78-168">If your category isn't in the list, select **Search**.</span></span> <span data-ttu-id="b3f78-169">Keressen kategória szerint, vagy váltson át a kategórianév szerinti keresésre.</span><span class="sxs-lookup"><span data-stu-id="b3f78-169">Search by category, or switch to search by category name.</span></span>
9.  <span data-ttu-id="b3f78-170">Válasszon ki egy tevékenységet.</span><span class="sxs-lookup"><span data-stu-id="b3f78-170">Select an activity.</span></span> <span data-ttu-id="b3f78-171">Megjelenik a kapcsolat nélküli használatra az alkalmazásba betöltött tevékenységek listája.</span><span class="sxs-lookup"><span data-stu-id="b3f78-171">A list shows the activities that are loaded into your app for offline use.</span></span> <span data-ttu-id="b3f78-172">Alapértelmezés szerint 50 elem töltődik be, de a fejlesztő módosíthatja ezt a számot.</span><span class="sxs-lookup"><span data-stu-id="b3f78-172">By default, 50 items are loaded, but a developer can change this number.</span></span> <span data-ttu-id="b3f78-173">További információ: lásd: [Mobil munkafelület](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md)</span><span class="sxs-lookup"><span data-stu-id="b3f78-173">For more information, see [Mobile platform](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md).</span></span>
10. <span data-ttu-id="b3f78-174">Ha a tevékenység nem szerepel a listán, válassza a **Keresés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b3f78-174">If your activity isn't in the list, select **Search**.</span></span> <span data-ttu-id="b3f78-175">Keressen tevékenységszám szerint, vagy váltson át a cél szerinti keresésre.</span><span class="sxs-lookup"><span data-stu-id="b3f78-175">Search by activity number, or switch to search by purpose.</span></span>

11. <span data-ttu-id="b3f78-176">Válassza ki a sortulajdonságot.</span><span class="sxs-lookup"><span data-stu-id="b3f78-176">Select the line property.</span></span>
12. <span data-ttu-id="b3f78-177">Nem kötelező: Adjon meg külső vagy belső megjegyzéseket.</span><span class="sxs-lookup"><span data-stu-id="b3f78-177">Optional: Enter any external and internal comments.</span></span>
13. <span data-ttu-id="b3f78-178">Válassza a **Kész** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b3f78-178">Select **Done**.</span></span>

