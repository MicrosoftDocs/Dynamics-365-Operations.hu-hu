---
title: Új e-kereskedelmi bérlő telepítése
description: Ez a témakör azt mutatja be, hogyan lehet új Dynamics 365 Commerce e-kereskedelmi webhelyet telepíteni a Microsoft Dynamics Lifecycle Services (LCS) segítségével.
author: psimolin
ms.date: 07/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 6b228babfd32a4191eeed2a6d924a8b99f1a5311
ms.sourcegitcommit: 9eadc7ca08e2db3fd208f5fc835551abe9d06dc8
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/22/2021
ms.locfileid: "5936706"
---
# <a name="deploy-a-new-e-commerce-tenant"></a><span data-ttu-id="fe9c3-103">Új e-kereskedelmi bérlő telepítése</span><span class="sxs-lookup"><span data-stu-id="fe9c3-103">Deploy a new e-commerce tenant</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="fe9c3-104">Ez a témakör azt mutatja be, hogyan lehet új Dynamics 365 Commerce e-kereskedelmi webhelyet telepíteni a Microsoft Dynamics Lifecycle Services (LCS) segítségével.</span><span class="sxs-lookup"><span data-stu-id="fe9c3-104">This topic describes how to deploy a new Dynamics 365 Commerce e-commerce site by using Microsoft Dynamics Lifecycle Services (LCS).</span></span>

<span data-ttu-id="fe9c3-105">A Microsoft Dynamics Lifecycle Services (LCS) egy felhőalapú együttműködési munkaterület, amelyet a partnerek és a vevők a projektjeik és a környezetek kezelésére, a Microsoft Dynamics termékekkel és szolgáltatásokkal kapcsolatos információk megtekintésére, valamint a terméktámogatási események létrehozására, nyomon követésére és böngészésére tudnak használni.</span><span class="sxs-lookup"><span data-stu-id="fe9c3-105">Microsoft Dynamics Lifecycle Services (LCS) is a cloud-based collaborative workspace that partners and customers can use to manage their projects and environments, view the latest information about Microsoft Dynamics products and features, and create, track, and browse support incidents.</span></span> <span data-ttu-id="fe9c3-106">Az e-kereskedelmi kezelési szolgáltatásai integrálva vannak az LCS-be.</span><span class="sxs-lookup"><span data-stu-id="fe9c3-106">E-commerce management features are integrated into LCS.</span></span>

<span data-ttu-id="fe9c3-107">További tájékoztatás az LCS-ről: [Lifecycle Services felhasználói útmutató](/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide).</span><span class="sxs-lookup"><span data-stu-id="fe9c3-107">To learn more about LCS, see the [Lifecycle Services User Guide](/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide).</span></span>
    
## <a name="get-started"></a><span data-ttu-id="fe9c3-108">Első lépések</span><span class="sxs-lookup"><span data-stu-id="fe9c3-108">Get started</span></span>

<span data-ttu-id="fe9c3-109">Az e-kereskedelmi inicializálásához inicializálnia kell egy projektet, egy környezetet és egy Retail Cloud Scale Unit (RCSU) egységet.</span><span class="sxs-lookup"><span data-stu-id="fe9c3-109">Before you can initialize e-commerce, you must initialize a project, an environment, and a Retail Cloud Scale Unit (RCSU).</span></span> <span data-ttu-id="fe9c3-110">Az LCS-ben történő inicializáláshoz a Projekttulajdonos vagy a Környezetkezelő szerepkör engedélyeivel kell rendelkeznie.</span><span class="sxs-lookup"><span data-stu-id="fe9c3-110">To do the initialization in LCS, you must have permissions for either the Project Owner or Environment manager role.</span></span> <span data-ttu-id="fe9c3-111">Támogatottak az éles és a tesztkörnyezeti topológiák.</span><span class="sxs-lookup"><span data-stu-id="fe9c3-111">The production and sandbox environment topologies are supported.</span></span>

<span data-ttu-id="fe9c3-112">A környezetekkel kapcsolatos további tudnivalókat lásd: [Környezet tervezése](/dynamics365/unified-operations/fin-and-ops/imp-lifecycle/environment-planning).</span><span class="sxs-lookup"><span data-stu-id="fe9c3-112">For more information about environments, see [Environment planning](/dynamics365/unified-operations/fin-and-ops/imp-lifecycle/environment-planning).</span></span> <span data-ttu-id="fe9c3-113">További tájékoztatás az RCSU-val kapcsolatban: [Retail Cloud Scale Unit inicializálása](/dynamics365/unified-operations/dev-itpro/deployment/initialize-retail-channels).</span><span class="sxs-lookup"><span data-stu-id="fe9c3-113">For more information about RCSU, see [Initialize Retail Cloud Scale Unit](/dynamics365/unified-operations/dev-itpro/deployment/initialize-retail-channels).</span></span>

## <a name="initialize-e-commerce"></a><span data-ttu-id="fe9c3-114">Az e-kereskedelem inicializálása</span><span class="sxs-lookup"><span data-stu-id="fe9c3-114">Initialize e-commerce</span></span>

<span data-ttu-id="fe9c3-115">Ezzel az eljárással lehet inicializálni egy létező környezet e-kereskedelmi funkcióját.</span><span class="sxs-lookup"><span data-stu-id="fe9c3-115">Use this procedure to initialize the e-commerce feature in an existing environment.</span></span>

<span data-ttu-id="fe9c3-116">A kezdés előtt győződjön meg arról, hogy rendelkezik a következő szükséges információkkal:</span><span class="sxs-lookup"><span data-stu-id="fe9c3-116">Before you begin, make sure that you have the following required information:</span></span>

- <span data-ttu-id="fe9c3-117">Az használandó RCSU.</span><span class="sxs-lookup"><span data-stu-id="fe9c3-117">The RCSU that will be used.</span></span>
- <span data-ttu-id="fe9c3-118">Az e-kereskedelmi rendszeradminisztrátorok esetében használni kívánt Microsoft Azure Active Directory biztonsági csoport.</span><span class="sxs-lookup"><span data-stu-id="fe9c3-118">The Microsoft Azure Active Directory security group that will be used for e-commerce system admins.</span></span>
- <span data-ttu-id="fe9c3-119">Az értékelések és vélemények moderátorai esetében használni kívánt Microsoft Azure Active Directory biztonsági csoport.</span><span class="sxs-lookup"><span data-stu-id="fe9c3-119">The Microsoft Azure Active Directory security group that will be used for ratings and reviews moderators.</span></span>
- <span data-ttu-id="fe9c3-120">A környezethez társítani kívánt tartományok.</span><span class="sxs-lookup"><span data-stu-id="fe9c3-120">The domains that will be associated with the environment.</span></span>

<span data-ttu-id="fe9c3-121">Ezenkívül a következő opcionális információkat gyűjtheti:</span><span class="sxs-lookup"><span data-stu-id="fe9c3-121">In addition, you can collect the following optional information:</span></span>

- <span data-ttu-id="fe9c3-122">Azure AD cég és ügyfél (B2C) közötti információk:</span><span class="sxs-lookup"><span data-stu-id="fe9c3-122">Azure AD business-to-consumer (B2C) information:</span></span>

    - <span data-ttu-id="fe9c3-123">Bérlő neve.</span><span class="sxs-lookup"><span data-stu-id="fe9c3-123">Tenant Name.</span></span>
    - <span data-ttu-id="fe9c3-124">Ügyfélazonosító.</span><span class="sxs-lookup"><span data-stu-id="fe9c3-124">Client ID.</span></span>
    - <span data-ttu-id="fe9c3-125">Bejelentkezéshez tartozó egyéni tartomány.</span><span class="sxs-lookup"><span data-stu-id="fe9c3-125">Login Custom Domain.</span></span>
    - <span data-ttu-id="fe9c3-126">Válasz URL.</span><span class="sxs-lookup"><span data-stu-id="fe9c3-126">Reply URL.</span></span>
    - <span data-ttu-id="fe9c3-127">Regisztrációra és bejelentkezésre vonatkozó irányelv azonosítója.</span><span class="sxs-lookup"><span data-stu-id="fe9c3-127">SignUp SignIn Policy ID.</span></span>
    - <span data-ttu-id="fe9c3-128">Jelszó visszaállítására vonatkozó irányelv azonosítója.</span><span class="sxs-lookup"><span data-stu-id="fe9c3-128">Reset password Policy ID.</span></span>
    - <span data-ttu-id="fe9c3-129">Profilszerkesztési irányelv azonosítója.</span><span class="sxs-lookup"><span data-stu-id="fe9c3-129">Edit Profile Policy ID.</span></span>

> [!NOTE]
> <span data-ttu-id="fe9c3-130">Ez az információ később is hozzáadható szolgáltatási kérelem alapján.</span><span class="sxs-lookup"><span data-stu-id="fe9c3-130">This information can be added later, through a service request.</span></span>

<span data-ttu-id="fe9c3-131">Miután összegyűjtötte a szükséges adatokat, hajtsa végre az alábbi lépéseket az e-kereskedelem inicializálásához.</span><span class="sxs-lookup"><span data-stu-id="fe9c3-131">After you've collected the required information, follow these steps to initialize e-commerce.</span></span>

1. <span data-ttu-id="fe9c3-132">Bejelentkezés az [LCS](https://lcs.dynamics.com) alkalmazásba.</span><span class="sxs-lookup"><span data-stu-id="fe9c3-132">Sign in to [LCS](https://lcs.dynamics.com).</span></span>
1. <span data-ttu-id="fe9c3-133">Nyissa meg azt a projektet, amely tartalmazza a projektet, ahol az e-kereskedelmet inicializálni kívánja.</span><span class="sxs-lookup"><span data-stu-id="fe9c3-133">Open the project that contains the environment where you want to initialize e-commerce.</span></span>
1. <span data-ttu-id="fe9c3-134">A **Környezetek** szakaszban válassza ki a környezetet.</span><span class="sxs-lookup"><span data-stu-id="fe9c3-134">In the **Environments** section, select the environment.</span></span>
1. <span data-ttu-id="fe9c3-135">A **Környezet funkciói** területen válassza ki a **Kiskereskedelem kezelése** hivatkozást.</span><span class="sxs-lookup"><span data-stu-id="fe9c3-135">Under **Environment features**, select the **Retail manage** link.</span></span>
1. <span data-ttu-id="fe9c3-136">Az **e-kereskedelem** lapon válassza a **Beállítás** elemet.</span><span class="sxs-lookup"><span data-stu-id="fe9c3-136">On the **e-Commerce** tab, select **Setup**.</span></span> <span data-ttu-id="fe9c3-137">Megjelenik egy párbeszédpanel, amelyen meg kell adnia a létesítéshez szükséges adatokat.</span><span class="sxs-lookup"><span data-stu-id="fe9c3-137">A dialog box appears, where you must enter the information that is required for provisioning.</span></span>
1. <span data-ttu-id="fe9c3-138">Töltse ki a szükséges adatokat, majd lépjen a következő lapra.</span><span class="sxs-lookup"><span data-stu-id="fe9c3-138">Fill in the required information, and then go to the next page.</span></span>
1. <span data-ttu-id="fe9c3-139">A következő lapon töltse ki a szükséges adatokat, majd küldje el az űrlapot.</span><span class="sxs-lookup"><span data-stu-id="fe9c3-139">On the next page, fill in the required information, and then submit the form.</span></span> <span data-ttu-id="fe9c3-140">A rendszer visszaküldi az **e-kereskedelem** lapra, amelyen látnia kell, hogy elindult az inicializálás.</span><span class="sxs-lookup"><span data-stu-id="fe9c3-140">You're returned to the **e-Commerce** tab, where you should see that initialization has been started.</span></span>
1. <span data-ttu-id="fe9c3-141">Az inicializálás állapotának megtekintéséhez válassza a **Frissítés** lehetőséget, vagy térjen vissza később az **e-kereskedelem** lapra.</span><span class="sxs-lookup"><span data-stu-id="fe9c3-141">To view the initialization status, either **Refresh** or return to the **e-Commerce** tab later.</span></span>
    
<span data-ttu-id="fe9c3-142">Az e-kereskedelem LCS-ből történő inicializálásakor a rendszer számos olyan összetevőt létesít, amelyek szükségesek az e-kereskedelemhez, és társítja őket a környezethez.</span><span class="sxs-lookup"><span data-stu-id="fe9c3-142">When e-commerce is initialized from LCS, the system provisions several components that are required for e-commerce and associates them with the environment.</span></span> <span data-ttu-id="fe9c3-143">A létesítés befejezése után az **e-Commerce** lap a **Kiskereskedelem kezelése** oldalon frissítésre kerül, hogy tükrözze a létesítést.</span><span class="sxs-lookup"><span data-stu-id="fe9c3-143">After provisioning is complete, the **e-Commerce** tab on the **Retail management** page is updated to reflect the provisioning.</span></span> <span data-ttu-id="fe9c3-144">A lap megjeleníti a legújabb testreszabási telepítéseket és az egyéb folyamatban lévő telepítések állapotát.</span><span class="sxs-lookup"><span data-stu-id="fe9c3-144">The page shows the latest customization deployments and the status of any other ongoing deployments.</span></span> <span data-ttu-id="fe9c3-145">Az e-kereskedelmi webhelyhez és az e-kereskedelmi webhelyszerkesztési eszközhöz is tartalmaz hivatkozásokat, amelyben a webhelyek készülnek.</span><span class="sxs-lookup"><span data-stu-id="fe9c3-145">It also includes links to the e-commerce site and the Commerce site builder where sites are authored.</span></span>

## <a name="access-commerce-site-builder"></a><span data-ttu-id="fe9c3-146">Commerce webhelykészítő elérése</span><span class="sxs-lookup"><span data-stu-id="fe9c3-146">Access Commerce site builder</span></span>

<span data-ttu-id="fe9c3-147">A Commerce webhelykészítő eléréséhez nyissa meg az **E-kereskedelem** lapot a **Kiskereskedelem kezelése** oldalon az LCS-ben, és válassza ki az **e-kereskedelmi webhely felügyeleti eszköze** hivatkozását.</span><span class="sxs-lookup"><span data-stu-id="fe9c3-147">To access Commerce site builder, go to the **e-Commerce** tab on the **Retail management** page in LCS and select the **e-Commerce site management tool** link.</span></span> <span data-ttu-id="fe9c3-148">A webhelykészítő nyitóoldala bérlő szintű nézetet jelenít meg.</span><span class="sxs-lookup"><span data-stu-id="fe9c3-148">The site builder landing page displays a tenant-level view.</span></span> <span data-ttu-id="fe9c3-149">Erről az oldalról a következőket teheti:</span><span class="sxs-lookup"><span data-stu-id="fe9c3-149">From this page, you can:</span></span>

- <span data-ttu-id="fe9c3-150">Bérlő szintű beállítások módosítása.</span><span class="sxs-lookup"><span data-stu-id="fe9c3-150">Modify tenant-level settings.</span></span>
- <span data-ttu-id="fe9c3-151">Navigáljon bármelyik létrehozott webhelyhez, és kérjen engedélyt a megtekintésre.</span><span class="sxs-lookup"><span data-stu-id="fe9c3-151">Navigate to any site you have created, and have permission to view.</span></span> 
- <span data-ttu-id="fe9c3-152">A hozzáférés-ellenőrzés olyan funkciókat tartalmaz, mint a moderálás és a jelentés.</span><span class="sxs-lookup"><span data-stu-id="fe9c3-152">Access Reviews features such as moderation and reporting.</span></span>
- <span data-ttu-id="fe9c3-153">Új webhely létrehozása.</span><span class="sxs-lookup"><span data-stu-id="fe9c3-153">Create a new site.</span></span> <span data-ttu-id="fe9c3-154">További információ a webhelyek létrehozásáról: [E-kereskedelmi webhely létrehozása](create-ecommerce-site.md).</span><span class="sxs-lookup"><span data-stu-id="fe9c3-154">For more information about how to create a new site, see [Create an e-commerce site](create-ecommerce-site.md) .</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="fe9c3-155">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="fe9c3-155">Additional resources</span></span>

[<span data-ttu-id="fe9c3-156">Tartománynév konfigurálása</span><span class="sxs-lookup"><span data-stu-id="fe9c3-156">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="fe9c3-157">E-kereskedelmi webhely létrehozása</span><span class="sxs-lookup"><span data-stu-id="fe9c3-157">Create an e-commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="fe9c3-158">Dynamics 365 Commerce webhely társítása online csatornával</span><span class="sxs-lookup"><span data-stu-id="fe9c3-158">Associate a Dynamics 365 Commerce site with an online channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="fe9c3-159">robots.txt fájlok kezelése</span><span class="sxs-lookup"><span data-stu-id="fe9c3-159">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="fe9c3-160">URL-átirányítások tömeges feltöltése</span><span class="sxs-lookup"><span data-stu-id="fe9c3-160">Upload URL redirects in bulk</span></span>](upload-bulk-redirects.md)

[<span data-ttu-id="fe9c3-161">B2C-bérlő beállítása a Commerce-ben</span><span class="sxs-lookup"><span data-stu-id="fe9c3-161">Set up a B2C tenant in Commerce</span></span>](set-up-B2C-tenant.md)

[<span data-ttu-id="fe9c3-162">Felhasználói bejelentkezéshez használt egyéni lapok beállítása</span><span class="sxs-lookup"><span data-stu-id="fe9c3-162">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="fe9c3-163">Több B2C-bérlő konfigurálása egy Commerce környezetben</span><span class="sxs-lookup"><span data-stu-id="fe9c3-163">Configure multiple B2C tenants in a Commerce environment</span></span>](configure-multi-B2C-tenants.md)

[<span data-ttu-id="fe9c3-164">Tartalomkézbesítési hálózat (CDN) támogatásának hozzáadása</span><span class="sxs-lookup"><span data-stu-id="fe9c3-164">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="fe9c3-165">Helyalapú áruházészlelés engedélyezése</span><span class="sxs-lookup"><span data-stu-id="fe9c3-165">Enable location-based store detection</span></span>](enable-store-detection.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]