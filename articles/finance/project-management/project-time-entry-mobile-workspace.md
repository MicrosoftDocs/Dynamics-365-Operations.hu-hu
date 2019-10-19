---
title: Projektidő megadása mobil munkaterület
description: Ez a témakör a Projektidő megadása mobil munkaterülettel kapcsolatban tartalmaz tájékoztatást. Ez a munkaterület lehetővé teszi a felhasználók számára, hogy beírhassák az időt, és időt takaríthassanak meg egy projektnél mobileszközük használatával.
author: KimANelson
manager: AnnBe
ms.date: 12/01/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 272101
ms.assetid: 4505f021-b9bb-4b87-be24-6bf0bd88ee60
ms.search.region: Global
ms.search.industry: Service industries
ms.author: knelson
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: ee11f7f392676adb59bd25f6549737482faf5fdb
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/30/2019
ms.locfileid: "2250369"
---
# <a name="project-time-entry-mobile-workspace"></a><span data-ttu-id="5e283-104">Projektidő megadása mobil munkaterület</span><span class="sxs-lookup"><span data-stu-id="5e283-104">Project time entry mobile workspace</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5e283-105">Ez a témakör a **Projektidő megadása** mobil munkaterülettel kapcsolatban tartalmaz tájékoztatást.</span><span class="sxs-lookup"><span data-stu-id="5e283-105">This topic provides information about the **Project time entry** mobile workspace.</span></span> <span data-ttu-id="5e283-106">Ez a munkaterület lehetővé teszi a felhasználók számára, hogy beírhassák az időt, és időt takaríthassanak meg egy projektnél mobileszközük használatával.</span><span class="sxs-lookup"><span data-stu-id="5e283-106">This workspace lets users enter and save time against a project by using their mobile device.</span></span>

<span data-ttu-id="5e283-107">A mobil munkaterületet a Dynamics 365 Unified Ops mobilalkalmazásban való használatra tervezték.</span><span class="sxs-lookup"><span data-stu-id="5e283-107">This mobile workspace is intended to be used with the Dynamics 365 Unified Ops mobile app.</span></span> 

## <a name="overview"></a><span data-ttu-id="5e283-108">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="5e283-108">Overview</span></span>
<span data-ttu-id="5e283-109">Napi munkájuk részeként a projektek résztvevői gyakran a helyszínen dolgoznak, vagy az utazáson vesznek részt.</span><span class="sxs-lookup"><span data-stu-id="5e283-109">As part of their daily work, project resources are often on-site or traveling.</span></span> <span data-ttu-id="5e283-110">A **Projektidő megadása** mobil munkaterület lehetővé teszi a felhasználók számára, hogy számlázható vagy nem számlázható időt írjanak be projektjükhöz a választott mobileszközön.</span><span class="sxs-lookup"><span data-stu-id="5e283-110">The **Project time entry** mobile workspace lets users enter their billable or non-billable time against a project on the mobile device of their choice.</span></span> <span data-ttu-id="5e283-111">Ezért a projekt résztvevői bármikor és bárhol rögzíthetik az időbevitelt.</span><span class="sxs-lookup"><span data-stu-id="5e283-111">Therefore, project resources can record time entries anytime and anywhere.</span></span> <span data-ttu-id="5e283-112">Megtekinthetik a már rögzített időbejegyzéseket is.</span><span class="sxs-lookup"><span data-stu-id="5e283-112">They can also view time entries that have already been recorded.</span></span> 

<span data-ttu-id="5e283-113">A **Projektidő megadása** mobil munkaterületen a felhasználók a következő feladatokat hajthatják végre:</span><span class="sxs-lookup"><span data-stu-id="5e283-113">Specifically, in the **Project time entry** mobile workspace, users can perform these tasks:</span></span>

-   <span data-ttu-id="5e283-114">Bármelyik kiválasztott dátumhoz beírhatja az adott feladatra fordított órák számát.</span><span class="sxs-lookup"><span data-stu-id="5e283-114">For any selected date, enter the number of hours that you spent on a specific task.</span></span>
-   <span data-ttu-id="5e283-115">Keresés projektnév vagy vevő alapján, hogy megtalálhassa a projektet, amelynél időt szeretne rögzíteni.</span><span class="sxs-lookup"><span data-stu-id="5e283-115">Search by project name or customer to find the project to enter time for.</span></span>
-   <span data-ttu-id="5e283-116">Adja meg az eltöltött időhöz tartozó kategóriát és tevékenységet.</span><span class="sxs-lookup"><span data-stu-id="5e283-116">Specify the category and activity for the time that you spent.</span></span>
-   <span data-ttu-id="5e283-117">Rögzítse az időt számlázhatóként vagy nem számlázhatóként a projektnél.</span><span class="sxs-lookup"><span data-stu-id="5e283-117">Record the time as billable or non-billable for the project.</span></span>
-   <span data-ttu-id="5e283-118">Nem kötelező: Adjon meg külső vagy belső megjegyzéseket.</span><span class="sxs-lookup"><span data-stu-id="5e283-118">Optionally enter any external or internal comments.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5e283-119">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="5e283-119">Prerequisites</span></span>
<span data-ttu-id="5e283-120">Az előfeltételek eltérnek a Microsoft Dynamics 365 szervezeténél megvalósított verziójától függően.</span><span class="sxs-lookup"><span data-stu-id="5e283-120">The prerequisites differ, based on the version of Microsoft Dynamics 365 that has been deployed for your organization.</span></span>

### <a name="prerequisites-if-you-use-dynamics-365-finance"></a><span data-ttu-id="5e283-121">Előfeltételek a Dynamics 365 Finance használatakor</span><span class="sxs-lookup"><span data-stu-id="5e283-121">Prerequisites if you use Dynamics 365 Finance</span></span>
<span data-ttu-id="5e283-122">Amennyiben szervezete telepítette a Finance rendszert, a rendszergazdának közzé kell tennie a **Projekt időbejegyzése** mobil munkaterület.</span><span class="sxs-lookup"><span data-stu-id="5e283-122">If Finance has been deployed for your organization, the system administrator must publish the **Project time entry** mobile workspace.</span></span> <span data-ttu-id="5e283-123">Utasításokért lásd: [Mobil munkaterület közzététele](../../dev-itpro/mobile-apps/publish-mobile-workspace.md).</span><span class="sxs-lookup"><span data-stu-id="5e283-123">For instructions, see [Publish a mobile workspace](../../dev-itpro/mobile-apps/publish-mobile-workspace.md).</span></span>

### <a name="prerequisites-if-you-use-version-1611-with-platform-update-3-or-later"></a><span data-ttu-id="5e283-124">Előfeltételek a 1611-es verzió és Platformfrissítés 3 vagy újabb használatakor</span><span class="sxs-lookup"><span data-stu-id="5e283-124">Prerequisites if you use version 1611 with Platform update 3 or later</span></span>
<span data-ttu-id="5e283-125">Amennyiben szervezete telepítette a 1611-es verziójának 3. vagy újabb platformfrissítését, a rendszergazdának végre kell hajtania a következő előfeltételeket.</span><span class="sxs-lookup"><span data-stu-id="5e283-125">If version 1611 with Platform update 3 or later has been deployed for your organization, the system administrator must complete the following prerequisites.</span></span> 

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="5e283-126">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="5e283-126">Prerequisite</span></span></th>
<th><span data-ttu-id="5e283-127">Szerep</span><span class="sxs-lookup"><span data-stu-id="5e283-127">Role</span></span></th>
<th><span data-ttu-id="5e283-128">Leírás</span><span class="sxs-lookup"><span data-stu-id="5e283-128">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">

<td><span data-ttu-id="5e283-129">Telepítse a KB 4018050 programot.</span><span class="sxs-lookup"><span data-stu-id="5e283-129">Implement KB 4018050.</span></span></td>
<td><span data-ttu-id="5e283-130">Rendszergazda</span><span class="sxs-lookup"><span data-stu-id="5e283-130">System administrator</span></span></td>
<td><span data-ttu-id="5e283-131">A 4018050-es tudásbáziscikk egy X++-frissítés vagy metaadat-gyorsjavítás, amely tartalmazza a <strong>Projektidő megadása</strong> mobil munkaterületet.</span><span class="sxs-lookup"><span data-stu-id="5e283-131">KB 4018050 is an X++ update or metadata hotfix that contains the <strong>Project time entry</strong> mobile workspace.</span></span> <span data-ttu-id="5e283-132">A KB 4018050 végrehajtásához a rendszergazdának követnie kell az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="5e283-132">To implement KB 4018050, your system administrator must follow these steps.</span></span>
<ol>
<li><span data-ttu-id="5e283-133"><a href="../../dev-itpro/migration-upgrade/download-hotfix-lcs.md">Metaadat-gyorsjavítások letöltése a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásból</a>.</span><span class="sxs-lookup"><span data-stu-id="5e283-133"><a href="../../dev-itpro/migration-upgrade/download-hotfix-lcs.md">Download the metadata hotfix from Microsoft Dynamics Lifecycle Services (LCS)</a>.</span></span></li>
<li><span data-ttu-id="5e283-134"><a href="../../dev-itpro/migration-upgrade/install-metadata-hotfix-package.md">Telepítse a metaadatok gyorsjavítását</a>.</span><span class="sxs-lookup"><span data-stu-id="5e283-134"><a href="../../dev-itpro/migration-upgrade/install-metadata-hotfix-package.md">Install the metadata hotfix</a>.</span></span></li>
<li><span data-ttu-id="5e283-135"><a href="../../dev-itpro/deployment/create-apply-deployable-package.md">Hozzon létre egy telepíthető csomagot</a>, amely tartalmazza az <strong>ApplicationSuite</strong> és a <strong>ProjectMobile</strong> modellt, majd töltse fel a telepíthető csomagot az LCS-be.</span><span class="sxs-lookup"><span data-stu-id="5e283-135"><a href="../../dev-itpro/deployment/create-apply-deployable-package.md">Create a deployable package</a> that contains the <strong>ApplicationSuite</strong> and <strong>ProjectMobile</strong> models, and then upload the deployable package to LCS.</span></span></li>
<li><span data-ttu-id="5e283-136"><a href="../../dev-itpro/deployment/apply-deployable-package-system.md">Alkalmazza telepíthető csomagot</a>.</span><span class="sxs-lookup"><span data-stu-id="5e283-136"><a href="../../dev-itpro/deployment/apply-deployable-package-system.md">Apply the deployable package</a>.</span></span></li>

</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="5e283-137">Tegye közzé a <strong>Projektidő megadása</strong> mobil munkaterületet.</span><span class="sxs-lookup"><span data-stu-id="5e283-137">Publish the <strong>Project time entry</strong> mobile workspace.</span></span></td>
<td><span data-ttu-id="5e283-138">Rendszergazda</span><span class="sxs-lookup"><span data-stu-id="5e283-138">System administrator</span></span></td>
<td><span data-ttu-id="5e283-139">Lásd: <a href="../../dev-itpro/mobile-apps/publish-mobile-workspace.md">Mobil munkaterület közzététele</a>.</span><span class="sxs-lookup"><span data-stu-id="5e283-139">See <a href="../../dev-itpro/mobile-apps/publish-mobile-workspace.md">Publish a mobile workspace</a>.</span></span></td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-mobile-app"></a><span data-ttu-id="5e283-140">A mobilalkalmazás letöltése és telepítése</span><span class="sxs-lookup"><span data-stu-id="5e283-140">Download and install the mobile app</span></span>

<span data-ttu-id="5e283-141">Töltse le és telepítse a Finance and Operations mobilalkalmazást:</span><span class="sxs-lookup"><span data-stu-id="5e283-141">Download and install the Finance and Operations mobile app:</span></span>

-   [<span data-ttu-id="5e283-142">Android telefonok esetében:</span><span class="sxs-lookup"><span data-stu-id="5e283-142">For Android phones</span></span>](https://go.microsoft.com/fwlink/?linkid=850662)
-   [<span data-ttu-id="5e283-143">iPhone esetében:</span><span class="sxs-lookup"><span data-stu-id="5e283-143">For iPhones</span></span>](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a><span data-ttu-id="5e283-144">Bejelentkezés a mobilalkalmazásba</span><span class="sxs-lookup"><span data-stu-id="5e283-144">Sign in to the mobile app</span></span>
1.  <span data-ttu-id="5e283-145">Indítsa el az alkalmazást a mobileszközén.</span><span class="sxs-lookup"><span data-stu-id="5e283-145">Start the app on your mobile device.</span></span>
2.  <span data-ttu-id="5e283-146">Adja meg a Dynamics 365 URL-címét.</span><span class="sxs-lookup"><span data-stu-id="5e283-146">Enter your Dynamics 365 URL.</span></span>
3.  <span data-ttu-id="5e283-147">Az első bejelentkezéskor a rendszer kéri a felhasználónevet és jelszót.</span><span class="sxs-lookup"><span data-stu-id="5e283-147">The first time that you sign in, you're prompted for your user name and password.</span></span> <span data-ttu-id="5e283-148">Adja meg a hitelesítési adatait.</span><span class="sxs-lookup"><span data-stu-id="5e283-148">Enter your credentials.</span></span>
4.  <span data-ttu-id="5e283-149">A bejelentkezést követően megjelennek a vállalata rendelkezésre álló munkaterületek.</span><span class="sxs-lookup"><span data-stu-id="5e283-149">After you sign in, the available workspaces for your company are shown.</span></span> <span data-ttu-id="5e283-150">Vegye figyelembe, hogy ha a rendszergazda később teszi közzé az új munkaterületet, akkor Önnek frissítenie kell a mobil munkaterületek listáját.</span><span class="sxs-lookup"><span data-stu-id="5e283-150">Note that if your system administrator publishes a new workspace later, you will have to refresh the list of mobile workspaces.</span></span>

<span data-ttu-id="5e283-151">[![Lekérés frissítéshez](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)</span><span class="sxs-lookup"><span data-stu-id="5e283-151">[![Pull to refresh](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)</span></span>

## <a name="enter-time-by-using-the-project-time-entry-mobile-workspace"></a><span data-ttu-id="5e283-152">Adja meg az időt a Projektidő megadása mobil munkaterület használatával</span><span class="sxs-lookup"><span data-stu-id="5e283-152">Enter time by using the Project time entry mobile workspace</span></span>
1.  <span data-ttu-id="5e283-153">A mobileszközön válassza a **Projektidő megadása** munkaterület.</span><span class="sxs-lookup"><span data-stu-id="5e283-153">On your mobile device, select the **Project time entry** workspace.</span></span>
2.  <span data-ttu-id="5e283-154">Válassza ki az **Időbejegyzés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5e283-154">Select **Time entry**.</span></span> <span data-ttu-id="5e283-155">Megjelennek az aktuális hét naptári dátumai.</span><span class="sxs-lookup"><span data-stu-id="5e283-155">The calendar dates for the current week are shown.</span></span>
3.  <span data-ttu-id="5e283-156">Válassza ki a kijelölt dátumnál a **Műveletek** &gt; **Új bejegyzés** pontot.</span><span class="sxs-lookup"><span data-stu-id="5e283-156">For a selected date, select **Actions** &gt; **New entry**.</span></span>
4.  <span data-ttu-id="5e283-157">Adja meg a rögzítendő órák számát.</span><span class="sxs-lookup"><span data-stu-id="5e283-157">Enter the number of hours to record.</span></span>
5.  <span data-ttu-id="5e283-158">Jelölje ki a projektet az időbejegyzéshez.</span><span class="sxs-lookup"><span data-stu-id="5e283-158">Select the project for the time entry.</span></span> <span data-ttu-id="5e283-159">Megjelenik a kapcsolat nélküli használatra az alkalmazásba betöltött projektek listája.</span><span class="sxs-lookup"><span data-stu-id="5e283-159">A list shows the projects that are loaded into your app for offline use.</span></span> <span data-ttu-id="5e283-160">Alapértelmezés szerint 50 elem töltődik be, de a fejlesztő módosíthatja ezt a számot.</span><span class="sxs-lookup"><span data-stu-id="5e283-160">By default, 50 items are loaded, but a developer can change this number.</span></span> <span data-ttu-id="5e283-161">További információ: lásd: [Mobil munkafelület](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md)</span><span class="sxs-lookup"><span data-stu-id="5e283-161">For more information, see [Mobile platform](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md).</span></span>
6.  <span data-ttu-id="5e283-162">Ha a projekt nem szerepel a listán, válassza a **Keresés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5e283-162">If your project isn't in the list, select **Search**.</span></span> <span data-ttu-id="5e283-163">Végezhet név szerinti keresést, vagy átválthat a projektnév vagy ügyfél szerinti keresésre.</span><span class="sxs-lookup"><span data-stu-id="5e283-163">Search by name, or switch to search by project name or customer.</span></span>
7.  <span data-ttu-id="5e283-164">Válasszon egy kategóriát.</span><span class="sxs-lookup"><span data-stu-id="5e283-164">Select a category.</span></span> <span data-ttu-id="5e283-165">Megjelenik a kapcsolat nélküli használatra az alkalmazásba betöltött kategóriák listája.</span><span class="sxs-lookup"><span data-stu-id="5e283-165">A list shows the categories that are loaded into your app for offline use.</span></span> <span data-ttu-id="5e283-166">Alapértelmezés szerint 50 elem töltődik be, de a fejlesztő módosíthatja ezt a számot.</span><span class="sxs-lookup"><span data-stu-id="5e283-166">By default, 50 items are loaded, but a developer can change this number.</span></span> <span data-ttu-id="5e283-167">További információ: lásd: [Mobil munkafelület](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md)</span><span class="sxs-lookup"><span data-stu-id="5e283-167">For more information, see [Mobile platform](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md).</span></span>
8.  <span data-ttu-id="5e283-168">Ha a kategória nem szerepel a listán, válassza a **Keresés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5e283-168">If your category isn't in the list, select **Search**.</span></span> <span data-ttu-id="5e283-169">Keressen kategória szerint, vagy váltson át a kategórianév szerinti keresésre.</span><span class="sxs-lookup"><span data-stu-id="5e283-169">Search by category, or switch to search by category name.</span></span>
9.  <span data-ttu-id="5e283-170">Válasszon ki egy tevékenységet.</span><span class="sxs-lookup"><span data-stu-id="5e283-170">Select an activity.</span></span> <span data-ttu-id="5e283-171">Megjelenik a kapcsolat nélküli használatra az alkalmazásba betöltött tevékenységek listája.</span><span class="sxs-lookup"><span data-stu-id="5e283-171">A list shows the activities that are loaded into your app for offline use.</span></span> <span data-ttu-id="5e283-172">Alapértelmezés szerint 50 elem töltődik be, de a fejlesztő módosíthatja ezt a számot.</span><span class="sxs-lookup"><span data-stu-id="5e283-172">By default, 50 items are loaded, but a developer can change this number.</span></span> <span data-ttu-id="5e283-173">További információ: lásd: [Mobil munkafelület](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md)</span><span class="sxs-lookup"><span data-stu-id="5e283-173">For more information, see [Mobile platform](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md).</span></span>
10. <span data-ttu-id="5e283-174">Ha a tevékenység nem szerepel a listán, válassza a **Keresés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5e283-174">If your activity isn't in the list, select **Search**.</span></span> <span data-ttu-id="5e283-175">Keressen tevékenységszám szerint, vagy váltson át a cél szerinti keresésre.</span><span class="sxs-lookup"><span data-stu-id="5e283-175">Search by activity number, or switch to search by purpose.</span></span>

11. <span data-ttu-id="5e283-176">Válassza ki a sortulajdonságot.</span><span class="sxs-lookup"><span data-stu-id="5e283-176">Select the line property.</span></span>
12. <span data-ttu-id="5e283-177">Nem kötelező: Adjon meg külső vagy belső megjegyzéseket.</span><span class="sxs-lookup"><span data-stu-id="5e283-177">Optional: Enter any external and internal comments.</span></span>
13. <span data-ttu-id="5e283-178">Válassza a **Kész** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5e283-178">Select **Done**.</span></span>
