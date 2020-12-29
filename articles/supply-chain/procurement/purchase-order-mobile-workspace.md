---
title: Beszerzési rendelés jóváhagyása mobil munkaterület
description: Ez a témakör a Beszerzési rendelés jóváhagyása mobil munkaterületet mutatja be, amely lehetővé teszi, hogy megtekintse a beszerzési rendeléseket és műveleteken keresztül válaszoljon rájuk. Például jóváhagyhat vagy elutasíthat egy beszerzési rendelést.
author: mkirknel
manager: tfehr
ms.date: 12/01/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchVendorPortalRequests
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations, Retail
ms.custom: 30211
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 68676fba895dcc91fd3dba065788f3be3a6e9ee4
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4429687"
---
# <a name="purchase-order-approval-mobile-workspace"></a><span data-ttu-id="9a5e3-104">Beszerzési rendelés jóváhagyása mobil munkaterület</span><span class="sxs-lookup"><span data-stu-id="9a5e3-104">Purchase order approval mobile workspace</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9a5e3-105">Ez a témakör a **Beszerzési rendelések** mobil munkaterülettel kapcsolatban tartalmaz tájékoztatást.</span><span class="sxs-lookup"><span data-stu-id="9a5e3-105">This topic provides information about the **Purchase order approval** mobile workspace.</span></span> <span data-ttu-id="9a5e3-106">A munkaterület segítségével megtekintheti a beszerzési rendeléseket, és műveleteken keresztül reagálhat is rájuk.</span><span class="sxs-lookup"><span data-stu-id="9a5e3-106">This workspace lets you view purchase orders and respond to them through actions.</span></span> <span data-ttu-id="9a5e3-107">Például jóváhagyhat vagy elutasíthat egy beszerzési rendelést.</span><span class="sxs-lookup"><span data-stu-id="9a5e3-107">For example, you can approve or reject a purchase order.</span></span>
 
## <a name="overview"></a><span data-ttu-id="9a5e3-108">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="9a5e3-108">Overview</span></span> 
<span data-ttu-id="9a5e3-109">A jóváhagyást igénylő beszerzési rendelések egy jóváhagyási munkafolyamaton esnek át.</span><span class="sxs-lookup"><span data-stu-id="9a5e3-109">Purchase orders that requires approval go through an approval workflow.</span></span> <span data-ttu-id="9a5e3-110">A munkafolyamat tartalmazhat olyan lépéseket, amelyek egy vagy több ember által végrehajtandó műveleteket igényelnek.</span><span class="sxs-lookup"><span data-stu-id="9a5e3-110">The workflow can include various steps that require that one or more people take action.</span></span> <span data-ttu-id="9a5e3-111">Például egy személynek végre kell hajtania egy feladatot, vagy jóvá kell hagynia a beszerzési rendelést.</span><span class="sxs-lookup"><span data-stu-id="9a5e3-111">For example, a person might have to complete a task or approve the purchase order.</span></span> 

<span data-ttu-id="9a5e3-112">A **Beszerzési rendelés jóváhagyása** mobil munkaterület lehetővé teszi, hogy könnyen megtekinthesse a beszerzési rendeléseket a mobileszközéről, és reagálhasson rájuk.</span><span class="sxs-lookup"><span data-stu-id="9a5e3-112">The **Purchase order approval** mobile workspace lets you easily view and respond to purchase orders from your mobile device.</span></span> <span data-ttu-id="9a5e3-113">A munkaterület lehetővé teszi ugyanazon munkafolyamati műveletek végrehajtását is, amelyeket a webes ügyfelében használhat.</span><span class="sxs-lookup"><span data-stu-id="9a5e3-113">This workspace also lets you take the same workflow actions that you can take from the web client.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9a5e3-114">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="9a5e3-114">Prerequisites</span></span>
<span data-ttu-id="9a5e3-115">Az előfeltételek eltérőek lehetnek attól függően, hogy a szervezete a Supply Chain Management melyik verzióját használja.</span><span class="sxs-lookup"><span data-stu-id="9a5e3-115">The prerequisites vary, depending on the version of Supply Chain Management that has been deployed for your organization.</span></span>

### <a name="prerequisites-if-you-use-supply-chain-management"></a><span data-ttu-id="9a5e3-116">Előfeltételek a Supply Chain Management használatakor</span><span class="sxs-lookup"><span data-stu-id="9a5e3-116">Prerequisites if you use Supply Chain Management</span></span> 
<span data-ttu-id="9a5e3-117">Amennyiben szervezete telepítette a Supply Chain Management rendszert, a rendszergazdának közzé kell tennie a **Beszerzési rendelés jóváhagyása** mobil munkaterület.</span><span class="sxs-lookup"><span data-stu-id="9a5e3-117">If Supply Chain Management has been deployed for your organization, the system administrator must publish the **Purchase order approval** mobile workspace.</span></span> <span data-ttu-id="9a5e3-118">Utasításokért lásd: [Mobil munkaterület közzététele](../../dev-itpro/mobile-apps/publish-mobile-workspace.md).</span><span class="sxs-lookup"><span data-stu-id="9a5e3-118">For instructions, see [Publish a mobile workspace](../../dev-itpro/mobile-apps/publish-mobile-workspace.md).</span></span>

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-for-operations-version-1611-with-platform-update-3-or-later"></a><span data-ttu-id="9a5e3-119">Előfeltételek a Microsoft Dynamics 365 for Operations 1611-es verzió és Platform update 3 vagy újabb használatakor</span><span class="sxs-lookup"><span data-stu-id="9a5e3-119">Prerequisites if you use Microsoft Dynamics 365 for Operations version 1611 with Platform update 3 or later</span></span>
<span data-ttu-id="9a5e3-120">Amennyiben szervezete telepítette a Microsoft Dynamics 365 for Operations 1611-es verziójánnak 3. vagy újabb Platformfrissítését, a rendszergazdának végre kell hajtania a következő előfeltételeket.</span><span class="sxs-lookup"><span data-stu-id="9a5e3-120">If Microsoft Dynamics 365 for Operations version 1611 with Platform update 3 or later has been deployed for your organization, the system administrator must complete the following prerequisites.</span></span> 

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="9a5e3-121">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="9a5e3-121">Prerequisite</span></span></th>
<th><span data-ttu-id="9a5e3-122">Szerep</span><span class="sxs-lookup"><span data-stu-id="9a5e3-122">Role</span></span></th>
<th><span data-ttu-id="9a5e3-123">Leírás</span><span class="sxs-lookup"><span data-stu-id="9a5e3-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="9a5e3-124">Telepítse a KB 4017918 programot.</span><span class="sxs-lookup"><span data-stu-id="9a5e3-124">Implement KB 4017918.</span></span></td>
<td><span data-ttu-id="9a5e3-125">Rendszergazda</span><span class="sxs-lookup"><span data-stu-id="9a5e3-125">System administrator</span></span></td>
<td><span data-ttu-id="9a5e3-126">A 4017918-es tudásbáziscikk egy X++-frissítés vagy metaadat-gyorsjavítás, amely tartalmazza a <strong>Beszerzési rendelés jóváhagyása</strong> mobil munkaterületet.</span><span class="sxs-lookup"><span data-stu-id="9a5e3-126">KB 4017918 is an X++ update or metadata hotfix that contains the <strong>Purchase order approval</strong> mobile workspace.</span></span> <span data-ttu-id="9a5e3-127">A KB 4017918 végrehajtásához a rendszergazdának követnie kell az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="9a5e3-127">To implement KB 4017918, your system administrator must follow these steps.</span></span>
<ol>
<li><span data-ttu-id="9a5e3-128"><a href="../../dev-itpro/migration-upgrade/download-hotfix-lcs.md">Metaadat-gyorsjavítások letöltése a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásból</a>.</span><span class="sxs-lookup"><span data-stu-id="9a5e3-128"><a href="../../dev-itpro/migration-upgrade/download-hotfix-lcs.md">Download the metadata hotfix from Microsoft Dynamics Lifecycle Services (LCS)</a>.</span></span></li>
<li><span data-ttu-id="9a5e3-129"><a href="../../dev-itpro/migration-upgrade/install-metadata-hotfix-package.md">Telepítse a metaadatok gyorsjavítását</a>.</span><span class="sxs-lookup"><span data-stu-id="9a5e3-129"><a href="../../dev-itpro/migration-upgrade/install-metadata-hotfix-package.md">Install the metadata hotfix</a>.</span></span></li>
<li><span data-ttu-id="9a5e3-130"><a href="../../dev-itpro/deployment/create-apply-deployable-package.md">Hozzon létre egy telepíthető csomagot</a>, amely tartalmazza a <strong>SCMMobile</strong> modellt, majd töltse fel a telepíthető csomagot az LCS-be.</span><span class="sxs-lookup"><span data-stu-id="9a5e3-130"><a href="../../dev-itpro/deployment/create-apply-deployable-package.md">Create a deployable package</a> that contains the <strong>SCMMobile</strong> model, and then upload the deployable package to LCS.</span></span></li>
<li><span data-ttu-id="9a5e3-131"><a href="../../dev-itpro/deployment/apply-deployable-package-system.md">Alkalmazza telepíthető csomagot</a>.</span><span class="sxs-lookup"><span data-stu-id="9a5e3-131"><a href="../../dev-itpro/deployment/apply-deployable-package-system.md">Apply the deployable package</a>.</span></span></li>
</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="9a5e3-132">Tegye közzé a <strong>Beszerzési rendelés jóváhagyása</strong> mobil munkaterületet.</span><span class="sxs-lookup"><span data-stu-id="9a5e3-132">Publish the <strong>Purchase order approval</strong> mobile workspace.</span></span></td>
<td><span data-ttu-id="9a5e3-133">Rendszergazda</span><span class="sxs-lookup"><span data-stu-id="9a5e3-133">System administrator</span></span></td>
<td><span data-ttu-id="9a5e3-134">Lásd: <a href="../../dev-itpro/mobile-apps/publish-mobile-workspace.md">Mobil munkaterület közzététele</a>.</span><span class="sxs-lookup"><span data-stu-id="9a5e3-134">See <a href="../../dev-itpro/mobile-apps/publish-mobile-workspace.md">Publish a mobile workspace</a>.</span></span></td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-mobile-app"></a><span data-ttu-id="9a5e3-135">A mobilalkalmazás letöltése és telepítése</span><span class="sxs-lookup"><span data-stu-id="9a5e3-135">Download and install the mobile app</span></span>
<span data-ttu-id="9a5e3-136">A Finance and Operations mobilalkalmazás letöltése és telepítése:</span><span class="sxs-lookup"><span data-stu-id="9a5e3-136">Download and install the Finance and Operations mobile app:</span></span>

- [<span data-ttu-id="9a5e3-137">Android telefonok esetében:</span><span class="sxs-lookup"><span data-stu-id="9a5e3-137">For Android phones</span></span>](https://go.microsoft.com/fwlink/?linkid=850662)
- [<span data-ttu-id="9a5e3-138">iPhone esetében:</span><span class="sxs-lookup"><span data-stu-id="9a5e3-138">For iPhones</span></span>](https://go.microsoft.com/fwlink/?linkid=850663)


## <a name="sign-in-to-the-mobile-app"></a><span data-ttu-id="9a5e3-139">Bejelentkezés a mobilalkalmazásba</span><span class="sxs-lookup"><span data-stu-id="9a5e3-139">Sign in to the mobile app</span></span>

1. <span data-ttu-id="9a5e3-140">Indítsa el az alkalmazást a mobileszközén.</span><span class="sxs-lookup"><span data-stu-id="9a5e3-140">Start the app on your mobile device.</span></span>
2. <span data-ttu-id="9a5e3-141">Adja meg a Microsoft Dynamics 365 URL-címét.</span><span class="sxs-lookup"><span data-stu-id="9a5e3-141">Enter your Microsoft Dynamics 365 URL.</span></span>
3. <span data-ttu-id="9a5e3-142">Az első bejelentkezéskor a rendszer kéri a felhasználónevet és jelszót.</span><span class="sxs-lookup"><span data-stu-id="9a5e3-142">The first time that you sign in, you're prompted for your user name and password.</span></span> <span data-ttu-id="9a5e3-143">Adja meg a hitelesítési adatait.</span><span class="sxs-lookup"><span data-stu-id="9a5e3-143">Enter your credentials.</span></span>
4. <span data-ttu-id="9a5e3-144">A bejelentkezést követően megjelennek a vállalata rendelkezésre álló munkaterületek.</span><span class="sxs-lookup"><span data-stu-id="9a5e3-144">After you sign in, the available workspaces for your company are shown.</span></span> <span data-ttu-id="9a5e3-145">Vegye figyelembe, hogy ha a rendszergazda később teszi közzé az új munkaterületet, akkor Önnek frissítenie kell a mobil munkaterületek listáját.</span><span class="sxs-lookup"><span data-stu-id="9a5e3-145">Note that if your system administrator publishes a new workspace later, you will have to refresh the list of mobile workspaces.</span></span>

![Beszerzési rendelés jóváhagyási munkaterülete a rendelkezésre álló munkaterületek listáján](./media/po-workspaces.png)

## <a name="view-orders-that-are-assigned-to-you"></a><span data-ttu-id="9a5e3-147">Önhöz rendelt megrendelések megtekintése</span><span class="sxs-lookup"><span data-stu-id="9a5e3-147">View orders that are assigned to you</span></span>
1. <span data-ttu-id="9a5e3-148">A mobileszközön válassza a **Beszerzési rendelés jóváhagyása** munkaterületet.</span><span class="sxs-lookup"><span data-stu-id="9a5e3-148">On your mobile device, select the **Purchase order approval** workspace.</span></span>
2. <span data-ttu-id="9a5e3-149">Válassza a **Hozzám rendelt rendelések** lehetőséget, hogy megtekinthesse azokaz a beszerzési rendeléseket, amelyek esetében a beszerzési rendelés jóváhagyási munkafolyamatában lépéseket kell tennie.</span><span class="sxs-lookup"><span data-stu-id="9a5e3-149">Select **Orders assigned to me** to view all the purchase orders for which you've been asked to take action in the purchase order approval workflow.</span></span>
3. <span data-ttu-id="9a5e3-150">Válasszon ki egy rendelést.</span><span class="sxs-lookup"><span data-stu-id="9a5e3-150">Select an order.</span></span> <span data-ttu-id="9a5e3-151">A **Rendelés részletei** lapon láthatja a rendelés fejlécének adatait és sorait.</span><span class="sxs-lookup"><span data-stu-id="9a5e3-151">On the **Order details** page, you will see the order header information and lines.</span></span> <span data-ttu-id="9a5e3-152">A munkafolyamat feladataival kapcsolatban is talál útmutatást.</span><span class="sxs-lookup"><span data-stu-id="9a5e3-152">You can also find guidelines from the workflow task.</span></span>
4. <span data-ttu-id="9a5e3-153">Válassza ki a **Könyvelési felosztások** lehetőséget a **Fejléc – könyvelési felosztások** lap megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="9a5e3-153">Select **Accounting distributions** to open the **Header accounting distributions** page.</span></span>
5. <span data-ttu-id="9a5e3-154">Térjen vissza a **Rendelés részletei** lapra, majd válasszon ki egy sort.</span><span class="sxs-lookup"><span data-stu-id="9a5e3-154">Return to the **Order details** page, and select a line.</span></span> <span data-ttu-id="9a5e3-155">A rendeléssor adataiból megtekintheti a sorspecifikus könyvelési felosztásokat is.</span><span class="sxs-lookup"><span data-stu-id="9a5e3-155">From the order line details, you can also explore the line-specific accounting distributions.</span></span>

## <a name="complete-an-action-on-the-purchase-order"></a><span data-ttu-id="9a5e3-156">Hajtson végre egy műveletet a beszerzési rendelésen</span><span class="sxs-lookup"><span data-stu-id="9a5e3-156">Complete an action on the purchase order</span></span>
<span data-ttu-id="9a5e3-157">Miután megtekintette az Önhöz rendelt beszerzési rendelést, és elolvasta a munkafolyamat-útmutatásokat, készen kell állnia a művelet végrehajtására.</span><span class="sxs-lookup"><span data-stu-id="9a5e3-157">After you've viewed the purchase order that is assigned to you and read the workflow instructions, you should be ready to take action.</span></span>

1. <span data-ttu-id="9a5e3-158">A mobileszközön válassza a **Beszerzési rendelés jóváhagyása** munkaterületet.</span><span class="sxs-lookup"><span data-stu-id="9a5e3-158">On your mobile device, select the **Purchase order approval** workspace.</span></span>
2. <span data-ttu-id="9a5e3-159">Válassza a **Hozzám rendelt rendelések** lehetőséget, hogy megtekinthesse azokaz a beszerzési rendeléseket, amelyek esetében a beszerzési rendelés jóváhagyási munkafolyamatában lépéseket kell tennie.</span><span class="sxs-lookup"><span data-stu-id="9a5e3-159">Select **Orders assigned to me** to view all the purchase orders for which you've been asked to take action in the purchase order approval workflow.</span></span>
3. <span data-ttu-id="9a5e3-160">Jelöljön ki egy rendelést, és tekintse meg a részletek lapot.</span><span class="sxs-lookup"><span data-stu-id="9a5e3-160">Select an order, and view the details page.</span></span>
4. <span data-ttu-id="9a5e3-161">Válassza a **Műveletek** lehetőséget a rendelkezésre álló műveletek megjelenítéséhez.</span><span class="sxs-lookup"><span data-stu-id="9a5e3-161">Select **Actions** to show the available actions.</span></span> <span data-ttu-id="9a5e3-162">Az elérhető műveletek az Önhöz rendelt feladattól függnek.</span><span class="sxs-lookup"><span data-stu-id="9a5e3-162">The actions that are available depend on the task that has been assigned to you.</span></span>

    | <span data-ttu-id="9a5e3-163">Feladat művelet</span><span class="sxs-lookup"><span data-stu-id="9a5e3-163">Task action</span></span>    | <span data-ttu-id="9a5e3-164">Jóváhagyási művelet</span><span class="sxs-lookup"><span data-stu-id="9a5e3-164">Approval action</span></span>  |
    |----------------|------------------|
    | <span data-ttu-id="9a5e3-165">Kész</span><span class="sxs-lookup"><span data-stu-id="9a5e3-165">Complete</span></span>       | <span data-ttu-id="9a5e3-166">Jóváhagyás</span><span class="sxs-lookup"><span data-stu-id="9a5e3-166">Approve</span></span>          |
    | <span data-ttu-id="9a5e3-167">Visszatérés</span><span class="sxs-lookup"><span data-stu-id="9a5e3-167">Return</span></span>         | <span data-ttu-id="9a5e3-168">Elutasítás</span><span class="sxs-lookup"><span data-stu-id="9a5e3-168">Reject</span></span>           |
    | <span data-ttu-id="9a5e3-169">Változtatás kérése</span><span class="sxs-lookup"><span data-stu-id="9a5e3-169">Request change</span></span> | <span data-ttu-id="9a5e3-170">Változtatás kérése</span><span class="sxs-lookup"><span data-stu-id="9a5e3-170">Request change</span></span>   |
    | <span data-ttu-id="9a5e3-171">Delegált</span><span class="sxs-lookup"><span data-stu-id="9a5e3-171">Delegate</span></span>       | <span data-ttu-id="9a5e3-172">Delegált</span><span class="sxs-lookup"><span data-stu-id="9a5e3-172">Delegate</span></span>         |

5. <span data-ttu-id="9a5e3-173">Jelölje ki a megfelelő műveletet.</span><span class="sxs-lookup"><span data-stu-id="9a5e3-173">Select the appropriate action.</span></span>
6. <span data-ttu-id="9a5e3-174">A **Feladat elvégzése** oldalon írjon be egy megjegyzést.</span><span class="sxs-lookup"><span data-stu-id="9a5e3-174">On the **Complete task** page, enter a comment.</span></span> <span data-ttu-id="9a5e3-175">Vegye figyelembe, hogy ha bejelöli a **Delegált** műveletet, ki kell választania egy felhasználót, akinek delegálja a feladatot.</span><span class="sxs-lookup"><span data-stu-id="9a5e3-175">Note that if you select the **Delegate** action, you must select a user to delegate the task to.</span></span>
7. <span data-ttu-id="9a5e3-176">Válassza a **Kész** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9a5e3-176">Select **Done**.</span></span> <span data-ttu-id="9a5e3-177">A munkaterület frissítése után a beszerzési rendelés nem lesz többé a listában.</span><span class="sxs-lookup"><span data-stu-id="9a5e3-177">After you refresh your workspace, the purchase order will no longer be in your list.</span></span> 
