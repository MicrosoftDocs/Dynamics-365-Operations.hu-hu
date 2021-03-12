---
title: Költségkontroll mobil munkaterület
description: Ez a témakör a Költségellenőrzés mobil munkaterületről nyújt tájékoztatást. A munkaterület lehetővé teszi a költséghelyek vezetői számára, hogy bármikor és bárhol megtekinthessék a költséghely teljesítményével kapcsolatos információkat.
author: AndersGirke
manager: AnnBe
ms.date: 12/01/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMMobileCostObjectOverviewDetailsCurrentPeriod, CAMMobileCostObjectList, CAMMobileCostObjectOverviewDetailsPreviousPeriod, CAMMobileCostObjectOverview, CAMMobileCostObjectOverviewDetailsYearToDate, CAMMobileCostControlWorkspaceConfiguration
audience: Application User
ms.reviewer: roschlom
ms.custom: 267114
ms.assetid: 612f2988-b2b9-420d-9825-40b99dc0e204
ms.search.region: global
ms.author: aevengir
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 58d86dbd2a3207b72d91165ede675bfe3ab8091e
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4990892"
---
# <a name="cost-controlling-mobile-workspace"></a><span data-ttu-id="c107d-104">Költségkontroll mobil munkaterület</span><span class="sxs-lookup"><span data-stu-id="c107d-104">Cost controlling mobile workspace</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c107d-105">Ez a témakör a **Költségellenőrzés** mobil munkaterületről nyújt tájékoztatást.</span><span class="sxs-lookup"><span data-stu-id="c107d-105">This topic provides information about the **Cost controlling** mobile workspace.</span></span> <span data-ttu-id="c107d-106">A munkaterület lehetővé teszi a költséghelyek vezetői számára, hogy bármikor és bárhol megtekinthessék a költséghely teljesítményével kapcsolatos információkat.</span><span class="sxs-lookup"><span data-stu-id="c107d-106">This workspace lets cost center managers view information about cost center performance anytime and anywhere.</span></span>

<span data-ttu-id="c107d-107">A mobil munkaterületet a Finance and Operations mobilalkalmazásban való használatra tervezték.</span><span class="sxs-lookup"><span data-stu-id="c107d-107">This mobile workspace is intended to be used with the Finance and Operations mobile app.</span></span>

## <a name="overview"></a><span data-ttu-id="c107d-108">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="c107d-108">Overview</span></span>
<span data-ttu-id="c107d-109">A **Költségkontroll** mobil munkaterületen azonnal megtekinthető a költséghelyek aktuális teljesítménye, és a tényleges költségek összevethetők a tervezett költségekkel.</span><span class="sxs-lookup"><span data-stu-id="c107d-109">The **Cost controlling** mobile workspace provides an instant view of the current performance of cost centers by comparing actual costs against the budgeted costs.</span></span> <span data-ttu-id="c107d-110">Az egyes költségtényezők állapotáig leáshat.</span><span class="sxs-lookup"><span data-stu-id="c107d-110">You can drill down to the status of individual cost elements.</span></span>

<span data-ttu-id="c107d-111">Például egy alkalmazott meghívót kap egy nemzetközi konferenciára, de a szervezetnek fedeznie kell az utazási költségeket.</span><span class="sxs-lookup"><span data-stu-id="c107d-111">For example, an employee receives an invitation to an international conference, but the organization must cover all the travel expenses.</span></span> <span data-ttu-id="c107d-112">Az alkalmazott megkérdezi a vezetőjét, hogy részt vehet-e a konferencián.</span><span class="sxs-lookup"><span data-stu-id="c107d-112">The employee asks their manager whether they can attend the conference.</span></span> <span data-ttu-id="c107d-113">A vezető megnyitja a **Költségkontroll** mobil munkaterületet a mobiltelefonján, és megnézi, hogy van-e költségvetése ahhoz, hogy az alkalmazott részt vehessen a konferencián.</span><span class="sxs-lookup"><span data-stu-id="c107d-113">The manager opens the **Cost controlling** mobile workspace on their mobile device to see whether there is budget for the employee to attend the conference.</span></span>

### <a name="data-security"></a><span data-ttu-id="c107d-114">Adatbiztonság</span><span class="sxs-lookup"><span data-stu-id="c107d-114">Data security</span></span>
<span data-ttu-id="c107d-115">A **Költségkontroll** mobil munkaterület adatait felhasználói hitelesítő adatok védik.</span><span class="sxs-lookup"><span data-stu-id="c107d-115">The data in the **Cost controlling** mobile workspace is secured through user credentials.</span></span> <span data-ttu-id="c107d-116">A költséghely vezetői csak a saját költséghelyük adatait láthatják.</span><span class="sxs-lookup"><span data-stu-id="c107d-116">Cost center managers are allowed to see data only for their own cost center.</span></span> <span data-ttu-id="c107d-117">A hozzáférési szint biztonságának kezelése a **Költségkönyvelési** modulon belül történik.</span><span class="sxs-lookup"><span data-stu-id="c107d-117">The access-level security is managed in the **Cost accounting** module.</span></span>

<span data-ttu-id="c107d-118">A **Költségkontroll** mobil munkaterület konfigurációját a költségkönyvelők határozzák meg a **Költségkönyvelés** modulban.</span><span class="sxs-lookup"><span data-stu-id="c107d-118">Cost accountants define the configuration of the **Cost controlling** mobile workspace in the **Cost accounting** module.</span></span> <span data-ttu-id="c107d-119">A munkaterület a mobilalkalmazásban való közzététele után elérhetővé válik az alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="c107d-119">After the workspace is published to the mobile app, it's available in the app.</span></span> <span data-ttu-id="c107d-120">Ennek következtében a szervezet összes költséghelyének vezetője ugyanabban a formátumban láthatja az adatokat.</span><span class="sxs-lookup"><span data-stu-id="c107d-120">Therefore, all cost center managers in the organization can view data in the same format.</span></span>

### <a name="actions-views-and-links"></a><span data-ttu-id="c107d-121">Műveletek, nézetek és hivatkozások</span><span class="sxs-lookup"><span data-stu-id="c107d-121">Actions, views, and links</span></span>
<span data-ttu-id="c107d-122">A **Költségellenőrzés** mobil munkaterület a következő műveleteket, nézeteket és hivatkozásokat biztosítja:</span><span class="sxs-lookup"><span data-stu-id="c107d-122">The **Cost controlling** mobile workspace provides the following actions, views, and links:</span></span>

-   <span data-ttu-id="c107d-123">**Műveletek:**</span><span class="sxs-lookup"><span data-stu-id="c107d-123">**Actions:**</span></span>

    -   <span data-ttu-id="c107d-124">Használja a **Konfiguráció kiválasztása** lehetőséget az elrendezés kiválasztásához.</span><span class="sxs-lookup"><span data-stu-id="c107d-124">Use **Select configuration** to select a layout.</span></span>
    -   <span data-ttu-id="c107d-125">Használja a **Költségobjektum kiválasztása** elemet azon költséghelyek kiválasztásához, amelyek adatait szűrni szeretné.</span><span class="sxs-lookup"><span data-stu-id="c107d-125">Use **Select cost object** to select the cost centers to filter data on.</span></span>
    
        > [!NOTE]
        > <span data-ttu-id="c107d-126">A listában megjelenő költséghelyek attól függnek, hogy milyen hozzáférést engedélyezett a **Költségkönyvelés** modulban.</span><span class="sxs-lookup"><span data-stu-id="c107d-126">The cost centers that appear in the list depend on the access that is granted in the **Cost accounting** module.</span></span>

-   <span data-ttu-id="c107d-127">**Nézetek:** Annak alapján, hogy milyen műveletek vannak kiválasztva, és milyen a **Költségkönyvelés** modul konfigurációja, a következő információkat tekintheti meg a kártyákon:</span><span class="sxs-lookup"><span data-stu-id="c107d-127">**Views:** Based on the actions that are selected and the configuration in the **Cost accounting** module, you can view the following information on the cards:</span></span>

    -   <span data-ttu-id="c107d-128">Tényleges kontra költségvetés (aktuális időszak)</span><span class="sxs-lookup"><span data-stu-id="c107d-128">Actual vs budget (current period)</span></span>
    -   <span data-ttu-id="c107d-129">Tényleges kontra módosított költségvetés (aktuális időszak)</span><span class="sxs-lookup"><span data-stu-id="c107d-129">Actual vs revised budget (current period)</span></span>
    -   <span data-ttu-id="c107d-130">Tényleges és költségvetési (előző időszak)</span><span class="sxs-lookup"><span data-stu-id="c107d-130">Actual vs budget (previous period)</span></span>
    -   <span data-ttu-id="c107d-131">Tényleges és módosított költségvetési (előző időszak)</span><span class="sxs-lookup"><span data-stu-id="c107d-131">Actual vs revised budget (previous period)</span></span>
    -   <span data-ttu-id="c107d-132">Tényleges és költségvetési (folyó év mai napig)</span><span class="sxs-lookup"><span data-stu-id="c107d-132">Actual vs budget (year to date)</span></span>
    -   <span data-ttu-id="c107d-133">Tényleges és módosított költségvetési (folyó év mai napig)</span><span class="sxs-lookup"><span data-stu-id="c107d-133">Actual vs revised budget (year to date)</span></span>

    <span data-ttu-id="c107d-134">A következő összegek jelennek meg minden kártyán: a Tényleges, Költségvetés, Eltérés és Eltérés %.</span><span class="sxs-lookup"><span data-stu-id="c107d-134">The following amounts are shown on every card: Actual, Budget, Variance, and Variance %.</span></span>

-   <span data-ttu-id="c107d-135">**Hivatkozások:**</span><span class="sxs-lookup"><span data-stu-id="c107d-135">**Links:**</span></span>

    -   <span data-ttu-id="c107d-136">Aktuális időszak részletei</span><span class="sxs-lookup"><span data-stu-id="c107d-136">Details for current period</span></span>
    -   <span data-ttu-id="c107d-137">Előző időszak részletei</span><span class="sxs-lookup"><span data-stu-id="c107d-137">Details for previous period</span></span>
    -   <span data-ttu-id="c107d-138">Folyó év mai dátumig részletei</span><span class="sxs-lookup"><span data-stu-id="c107d-138">Details for year to date</span></span>

    <span data-ttu-id="c107d-139">Ha kiválaszt egy hivatkozást, egy kártya jelenik meg minden egyes költségösszetevőhöz.</span><span class="sxs-lookup"><span data-stu-id="c107d-139">When you select a link, a card is shown for each cost element.</span></span> <span data-ttu-id="c107d-140">A kártyákon a következő összegek jelennek meg: Aktuális, Költségvetés, Költségvetés eltérése, Költségvetés eltérése %, Módosított költségvetés, Módosított költségvetés eltérése és Módosított költségvetés eltérése %.</span><span class="sxs-lookup"><span data-stu-id="c107d-140">The following amounts are shown on every card: Actual, Budget, Budget variance, Budget variance %, Revised budget, Revised budget variance, and Revised budget variance %.</span></span>
    
    <span data-ttu-id="c107d-141">[![Kártya költségösszetevőhöz ](./media/Cost-controlling.png)](./media/Cost-controlling.png)</span><span class="sxs-lookup"><span data-stu-id="c107d-141">[![Card for a cost element](./media/Cost-controlling.png)](./media/Cost-controlling.png)</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c107d-142">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="c107d-142">Prerequisites</span></span>
<span data-ttu-id="c107d-143">Az előfeltételek eltérnek a Microsoft Dynamics 365 szervezeténél megvalósított verziójától függően.</span><span class="sxs-lookup"><span data-stu-id="c107d-143">The prerequisites differ, based on the version of Microsoft Dynamics 365 that has been deployed for your organization.</span></span>

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-finance"></a><span data-ttu-id="c107d-144">Előfeltételek a Microsoft Dynamics 365 Finance használatához</span><span class="sxs-lookup"><span data-stu-id="c107d-144">Prerequisites if you use Microsoft Dynamics 365 Finance</span></span>
<span data-ttu-id="c107d-145">Amennyiben szervezete telepítette a Finance rendszert, a rendszergazdának közzé kell tennie a **Költségkontroll** mobil munkaterület.</span><span class="sxs-lookup"><span data-stu-id="c107d-145">If Finance has been deployed for your organization, the system administrator must publish the **Cost controlling** mobile workspace.</span></span> <span data-ttu-id="c107d-146">Utasításokért lásd: [Mobil munkaterület közzététele](../../dev-itpro/mobile-apps/publish-mobile-workspace.md).</span><span class="sxs-lookup"><span data-stu-id="c107d-146">For instructions, see [Publish a mobile workspace](../../dev-itpro/mobile-apps/publish-mobile-workspace.md).</span></span>

### <a name="prerequisites-if-you-use-version-1611-with-platform-update-3-or-later"></a><span data-ttu-id="c107d-147">Előfeltételek a 1611-es verzió és Platformfrissítés 3 vagy újabb használatakor</span><span class="sxs-lookup"><span data-stu-id="c107d-147">Prerequisites if you use version 1611 with Platform update 3 or later</span></span>
<span data-ttu-id="c107d-148">Amennyiben szervezete telepítette a 1611-es verziójának 3. vagy újabb platformfrissítését, a rendszergazdának végre kell hajtania a következő előfeltételeket.</span><span class="sxs-lookup"><span data-stu-id="c107d-148">If version 1611 with Platform update 3 or later has been deployed for your organization, the system administrator must complete the following prerequisites.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="c107d-149">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="c107d-149">Prerequisite</span></span></th>
<th><span data-ttu-id="c107d-150">Szerep</span><span class="sxs-lookup"><span data-stu-id="c107d-150">Role</span></span></th>
<th><span data-ttu-id="c107d-151">Leírás</span><span class="sxs-lookup"><span data-stu-id="c107d-151">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="c107d-152">Telepítse a KB 4013633 programot.</span><span class="sxs-lookup"><span data-stu-id="c107d-152">Implement KB 4013633.</span></span></td>
<td><span data-ttu-id="c107d-153">Rendszergazda</span><span class="sxs-lookup"><span data-stu-id="c107d-153">System administrator</span></span></td>

<td><span data-ttu-id="c107d-154">A 4013633-es tudásbáziscikk egy X++-frissítés vagy metaadat-gyorsjavítás, amely tartalmazza a <strong>Költségellenőrzés</strong> mobil munkaterületet.</span><span class="sxs-lookup"><span data-stu-id="c107d-154">KB 4013633 is an X++ update or metadata hotfix that contains the <strong>Cost controlling</strong> mobile workspace.</span></span> <span data-ttu-id="c107d-155">A KB 4013633 végrehajtásához a rendszergazdának követnie kell az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="c107d-155">To implement KB 4013633, your system administrator must follow these steps.</span></span>
<ol>
<li><span data-ttu-id="c107d-156"><a href="../../dev-itpro/migration-upgrade/download-hotfix-lcs.md">Metaadat-gyorsjavítások letöltése a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásból</a>.</span><span class="sxs-lookup"><span data-stu-id="c107d-156"><a href="../../dev-itpro/migration-upgrade/download-hotfix-lcs.md">Download the metadata hotfix from Microsoft Dynamics Lifecycle Services (LCS)</a>.</span></span></li>
<li><span data-ttu-id="c107d-157"><a href="../../dev-itpro/migration-upgrade/install-metadata-hotfix-package.md">Telepítse a metaadatok gyorsjavítását</a>.</span><span class="sxs-lookup"><span data-stu-id="c107d-157"><a href="../../dev-itpro/migration-upgrade/install-metadata-hotfix-package.md">Install the metadata hotfix</a>.</span></span></li>
<li><span data-ttu-id="c107d-158"><a href="../../dev-itpro/deployment/create-apply-deployable-package.md">Hozzon létre egy telepíthető csomagot</a>, amely tartalmazza a <strong>SCMMobile</strong> modellt, majd töltse fel a telepíthető csomagot az LCS-be.</span><span class="sxs-lookup"><span data-stu-id="c107d-158"><a href="../../dev-itpro/deployment/create-apply-deployable-package.md">Create a deployable package</a> that contains the <strong>SCMMobile</strong> model, and then upload the deployable package to LCS.</span></span></li>
<li><span data-ttu-id="c107d-159"><a href="../../dev-itpro/deployment/apply-deployable-package-system.md">Alkalmazza telepíthető csomagot</a>.</span><span class="sxs-lookup"><span data-stu-id="c107d-159"><a href="../../dev-itpro/deployment/apply-deployable-package-system.md">Apply the deployable package</a>.</span></span></li>

</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="c107d-160">Tegye közzé a <strong>Költségellenőrzés</strong> mobil munkaterületet.</span><span class="sxs-lookup"><span data-stu-id="c107d-160">Publish the <strong>Cost controlling</strong> mobile workspace.</span></span></td>
<td><span data-ttu-id="c107d-161">Rendszergazda</span><span class="sxs-lookup"><span data-stu-id="c107d-161">System administrator</span></span></td>
<td><span data-ttu-id="c107d-162">Lásd: <a href="../../dev-itpro/mobile-apps/publish-mobile-workspace.md">Mobil munkaterület közzététele</a>.</span><span class="sxs-lookup"><span data-stu-id="c107d-162">See <a href="../../dev-itpro/mobile-apps/publish-mobile-workspace.md">Publish a mobile workspace</a>.</span></span></td>
</tr>
</tbody>
</table>


## <a name="download-and-install-the-mobile-app"></a><span data-ttu-id="c107d-163">A mobilalkalmazás letöltése és telepítése</span><span class="sxs-lookup"><span data-stu-id="c107d-163">Download and install the mobile app</span></span>
<span data-ttu-id="c107d-164">A Finance and Operations mobilalkalmazás letöltése és telepítése:</span><span class="sxs-lookup"><span data-stu-id="c107d-164">Download and install the Finance and Operations mobile app:</span></span>

-   [<span data-ttu-id="c107d-165">Android telefonok esetében:</span><span class="sxs-lookup"><span data-stu-id="c107d-165">For Android phones</span></span>](https://go.microsoft.com/fwlink/?linkid=850662)
-   [<span data-ttu-id="c107d-166">iPhone esetében:</span><span class="sxs-lookup"><span data-stu-id="c107d-166">For iPhones</span></span>](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a><span data-ttu-id="c107d-167">Bejelentkezés a mobilalkalmazásba</span><span class="sxs-lookup"><span data-stu-id="c107d-167">Sign in to the mobile app</span></span>

1.  <span data-ttu-id="c107d-168">Indítsa el az alkalmazást a mobileszközén.</span><span class="sxs-lookup"><span data-stu-id="c107d-168">Start the app on your mobile device.</span></span>
2.  <span data-ttu-id="c107d-169">Adja meg a Dynamics 365 URL-címét.</span><span class="sxs-lookup"><span data-stu-id="c107d-169">Enter your Dynamics 365 URL.</span></span>
3.  <span data-ttu-id="c107d-170">Az első bejelentkezéskor a rendszer kéri a felhasználónevet és jelszót.</span><span class="sxs-lookup"><span data-stu-id="c107d-170">The first time that you sign in, you're prompted for your user name and password.</span></span> <span data-ttu-id="c107d-171">Adja meg a hitelesítési adatait.</span><span class="sxs-lookup"><span data-stu-id="c107d-171">Enter your credentials.</span></span>
4.  <span data-ttu-id="c107d-172">A bejelentkezést követően megjelennek a vállalata rendelkezésre álló munkaterületek.</span><span class="sxs-lookup"><span data-stu-id="c107d-172">After you sign in, the available workspaces for your company are shown.</span></span> <span data-ttu-id="c107d-173">Vegye figyelembe, hogy ha a rendszergazda később teszi közzé az új munkaterületet, akkor Önnek frissítenie kell a mobil munkaterületek listáját.</span><span class="sxs-lookup"><span data-stu-id="c107d-173">Note that if your system administrator publishes a new workspace later, you will have to refresh the list of mobile workspaces.</span></span>

<span data-ttu-id="c107d-174">[![Lekérés frissítéshez](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)</span><span class="sxs-lookup"><span data-stu-id="c107d-174">[![Pull to refresh](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)</span></span>

## <a name="view-the-performance-of-your-cost-center-by-using-the-cost-controlling-mobile-workspace"></a><span data-ttu-id="c107d-175">A költséghely teljesítményének megtekintése a Költségkontroll mobil munkaterület segítségével</span><span class="sxs-lookup"><span data-stu-id="c107d-175">View the performance of your cost center by using the Cost controlling mobile workspace</span></span>

1.  <span data-ttu-id="c107d-176">A mobileszközön válassza a **Költségkontroll** munkaterület.</span><span class="sxs-lookup"><span data-stu-id="c107d-176">On your mobile device, select the **Cost controlling** workspace.</span></span>
2.  <span data-ttu-id="c107d-177">Válassza a **Költségobjektum-kontroll** elemet.</span><span class="sxs-lookup"><span data-stu-id="c107d-177">Select **Cost object controlling**.</span></span>
3.  <span data-ttu-id="c107d-178">Válassza a **Műveletek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c107d-178">Select **Actions**.</span></span>
4.  <span data-ttu-id="c107d-179">Válassza a **Konfiguráció kiválasztása** elemet egy költségkontroll-elrendezés kiválasztásához.</span><span class="sxs-lookup"><span data-stu-id="c107d-179">Select **Select configuration** to select a cost controlling layout.</span></span>
5.  <span data-ttu-id="c107d-180">Válassza a **Kész** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c107d-180">Select **Done**.</span></span>
6.  <span data-ttu-id="c107d-181">Válassza a **Műveletek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c107d-181">Select **Actions**.</span></span>
7.  <span data-ttu-id="c107d-182">Válassza a **Költségobjektum kiválasztása** elemet, és válassza ki a költséghelyeket, amelyekhez hozzáférése van.</span><span class="sxs-lookup"><span data-stu-id="c107d-182">Select **Select cost object** to select the cost centers that you've been granted access to.</span></span>
8.  <span data-ttu-id="c107d-183">Válassza a **Kész** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c107d-183">Select **Done**.</span></span>
9.  <span data-ttu-id="c107d-184">Tekintse meg a költséghely összteljesítményét.</span><span class="sxs-lookup"><span data-stu-id="c107d-184">View the overall performance of your cost center.</span></span>
10. <span data-ttu-id="c107d-185">Válassza az **Aktuális időszak részletei** hivatkozást.</span><span class="sxs-lookup"><span data-stu-id="c107d-185">Select the **Details for current period** link.</span></span>
11. <span data-ttu-id="c107d-186">Tekintse meg az egyedi költségelemek teljesítményét.</span><span class="sxs-lookup"><span data-stu-id="c107d-186">View the performance of individual cost elements.</span></span>
12. <span data-ttu-id="c107d-187">Konkrét költségelemekre is kereshet.</span><span class="sxs-lookup"><span data-stu-id="c107d-187">You can also search for specific cost elements.</span></span>

