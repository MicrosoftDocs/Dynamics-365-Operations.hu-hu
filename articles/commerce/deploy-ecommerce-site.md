---
title: Új e-kereskedelmi bérlő telepítése
description: Ez a témakör azt mutatja be, hogyan lehet új Dynamics 365 Commerce e-kereskedelmi webhelyet telepíteni a Microsoft Dynamics Lifecycle Services (LCS) segítségével.
author: psimolin
manager: annbe
ms.date: 07/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 3b750ee89a85688dcebe673f9c3ff13693e9fcad
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4976738"
---
# <a name="deploy-a-new-e-commerce-tenant"></a><span data-ttu-id="5fb08-103">Új e-kereskedelmi bérlő telepítése</span><span class="sxs-lookup"><span data-stu-id="5fb08-103">Deploy a new e-commerce tenant</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="5fb08-104">Ez a témakör azt mutatja be, hogyan lehet új Dynamics 365 Commerce e-kereskedelmi webhelyet telepíteni a Microsoft Dynamics Lifecycle Services (LCS) segítségével.</span><span class="sxs-lookup"><span data-stu-id="5fb08-104">This topic describes how to deploy a new Dynamics 365 Commerce e-commerce site by using Microsoft Dynamics Lifecycle Services (LCS).</span></span>

## <a name="overview"></a><span data-ttu-id="5fb08-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="5fb08-105">Overview</span></span>

<span data-ttu-id="5fb08-106">A Microsoft Dynamics Lifecycle Services (LCS) egy felhőalapú együttműködési munkaterület, amelyet a partnerek és a vevők a projektjeik és a környezetek kezelésére, a Microsoft Dynamics termékekkel és szolgáltatásokkal kapcsolatos információk megtekintésére, valamint a terméktámogatási események létrehozására, nyomon követésére és böngészésére tudnak használni.</span><span class="sxs-lookup"><span data-stu-id="5fb08-106">Microsoft Dynamics Lifecycle Services (LCS) is a cloud-based collaborative workspace that partners and customers can use to manage their projects and environments, view the latest information about Microsoft Dynamics products and features, and create, track, and browse support incidents.</span></span> <span data-ttu-id="5fb08-107">Az e-kereskedelmi kezelési szolgáltatásai integrálva vannak az LCS-be.</span><span class="sxs-lookup"><span data-stu-id="5fb08-107">E-commerce management features are integrated into LCS.</span></span>

<span data-ttu-id="5fb08-108">További tájékoztatás az LCS-ről: [Lifecycle Services felhasználói útmutató](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide).</span><span class="sxs-lookup"><span data-stu-id="5fb08-108">To learn more about LCS, see the [Lifecycle Services User Guide](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide).</span></span>
    
## <a name="get-started"></a><span data-ttu-id="5fb08-109">Első lépések</span><span class="sxs-lookup"><span data-stu-id="5fb08-109">Get started</span></span>

<span data-ttu-id="5fb08-110">Az e-kereskedelmi inicializálásához inicializálnia kell egy projektet, egy környezetet és egy Retail Cloud Scale Unit (RCSU) egységet.</span><span class="sxs-lookup"><span data-stu-id="5fb08-110">Before you can initialize e-commerce, you must initialize a project, an environment, and a Retail Cloud Scale Unit (RCSU).</span></span> <span data-ttu-id="5fb08-111">Az LCS-ben történő inicializáláshoz a Projekttulajdonos vagy a Környezetkezelő szerepkör engedélyeivel kell rendelkeznie.</span><span class="sxs-lookup"><span data-stu-id="5fb08-111">To do the initialization in LCS, you must have permissions for either the Project Owner or Environment manager role.</span></span> <span data-ttu-id="5fb08-112">Támogatottak az éles és a tesztkörnyezeti topológiák.</span><span class="sxs-lookup"><span data-stu-id="5fb08-112">The production and sandbox environment topologies are supported.</span></span>

<span data-ttu-id="5fb08-113">A környezetekkel kapcsolatos további tudnivalókat lásd: [Környezet tervezése](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/imp-lifecycle/environment-planning).</span><span class="sxs-lookup"><span data-stu-id="5fb08-113">For more information about environments, see [Environment planning](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/imp-lifecycle/environment-planning).</span></span> <span data-ttu-id="5fb08-114">További tájékoztatás az RCSU-val kapcsolatban: [Retail Cloud Scale Unit inicializálása](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/deployment/initialize-retail-channels).</span><span class="sxs-lookup"><span data-stu-id="5fb08-114">For more information about RCSU, see [Initialize Retail Cloud Scale Unit](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/deployment/initialize-retail-channels).</span></span>

## <a name="initialize-e-commerce"></a><span data-ttu-id="5fb08-115">Az e-kereskedelem inicializálása</span><span class="sxs-lookup"><span data-stu-id="5fb08-115">Initialize e-commerce</span></span>

<span data-ttu-id="5fb08-116">Ezzel az eljárással lehet inicializálni egy létező környezet e-kereskedelmi funkcióját.</span><span class="sxs-lookup"><span data-stu-id="5fb08-116">Use this procedure to initialize the e-commerce feature in an existing environment.</span></span>

<span data-ttu-id="5fb08-117">A kezdés előtt győződjön meg arról, hogy rendelkezik a következő szükséges információkkal:</span><span class="sxs-lookup"><span data-stu-id="5fb08-117">Before you begin, make sure that you have the following required information:</span></span>

- <span data-ttu-id="5fb08-118">Az használandó RCSU.</span><span class="sxs-lookup"><span data-stu-id="5fb08-118">The RCSU that will be used.</span></span>
- <span data-ttu-id="5fb08-119">Az e-kereskedelmi rendszeradminisztrátorok esetében használni kívánt Microsoft Azure Active Directory biztonsági csoport.</span><span class="sxs-lookup"><span data-stu-id="5fb08-119">The Microsoft Azure Active Directory security group that will be used for e-commerce system admins.</span></span>
- <span data-ttu-id="5fb08-120">Az értékelések és vélemények moderátorai esetében használni kívánt Microsoft Azure Active Directory biztonsági csoport.</span><span class="sxs-lookup"><span data-stu-id="5fb08-120">The Microsoft Azure Active Directory security group that will be used for ratings and reviews moderators.</span></span>
- <span data-ttu-id="5fb08-121">A környezethez társítani kívánt tartományok.</span><span class="sxs-lookup"><span data-stu-id="5fb08-121">The domains that will be associated with the environment.</span></span>

<span data-ttu-id="5fb08-122">Ezenkívül a következő opcionális információkat gyűjtheti:</span><span class="sxs-lookup"><span data-stu-id="5fb08-122">In addition, you can collect the following optional information:</span></span>

- <span data-ttu-id="5fb08-123">Azure AD cég és ügyfél (B2C) közötti információk:</span><span class="sxs-lookup"><span data-stu-id="5fb08-123">Azure AD business-to-consumer (B2C) information:</span></span>

    - <span data-ttu-id="5fb08-124">Bérlő neve.</span><span class="sxs-lookup"><span data-stu-id="5fb08-124">Tenant Name.</span></span>
    - <span data-ttu-id="5fb08-125">Ügyfélazonosító.</span><span class="sxs-lookup"><span data-stu-id="5fb08-125">Client ID.</span></span>
    - <span data-ttu-id="5fb08-126">Bejelentkezéshez tartozó egyéni tartomány.</span><span class="sxs-lookup"><span data-stu-id="5fb08-126">Login Custom Domain.</span></span>
    - <span data-ttu-id="5fb08-127">Válasz URL.</span><span class="sxs-lookup"><span data-stu-id="5fb08-127">Reply URL.</span></span>
    - <span data-ttu-id="5fb08-128">Regisztrációra és bejelentkezésre vonatkozó irányelv azonosítója.</span><span class="sxs-lookup"><span data-stu-id="5fb08-128">SignUp SignIn Policy ID.</span></span>
    - <span data-ttu-id="5fb08-129">Jelszó visszaállítására vonatkozó irányelv azonosítója.</span><span class="sxs-lookup"><span data-stu-id="5fb08-129">Reset password Policy ID.</span></span>
    - <span data-ttu-id="5fb08-130">Profilszerkesztési irányelv azonosítója.</span><span class="sxs-lookup"><span data-stu-id="5fb08-130">Edit Profile Policy ID.</span></span>

> [!NOTE]
> <span data-ttu-id="5fb08-131">Ez az információ később is hozzáadható szolgáltatási kérelem alapján.</span><span class="sxs-lookup"><span data-stu-id="5fb08-131">This information can be added later, through a service request.</span></span>

<span data-ttu-id="5fb08-132">Miután összegyűjtötte a szükséges adatokat, hajtsa végre az alábbi lépéseket az e-kereskedelem inicializálásához.</span><span class="sxs-lookup"><span data-stu-id="5fb08-132">After you've collected the required information, follow these steps to initialize e-commerce.</span></span>

1. <span data-ttu-id="5fb08-133">Bejelentkezés az [LCS](https://lcs.dynamics.com) alkalmazásba.</span><span class="sxs-lookup"><span data-stu-id="5fb08-133">Sign in to [LCS](https://lcs.dynamics.com).</span></span>
1. <span data-ttu-id="5fb08-134">Nyissa meg azt a projektet, amely tartalmazza a projektet, ahol az e-kereskedelmet inicializálni kívánja.</span><span class="sxs-lookup"><span data-stu-id="5fb08-134">Open the project that contains the environment where you want to initialize e-commerce.</span></span>
1. <span data-ttu-id="5fb08-135">A **Környezetek** szakaszban válassza ki a környezetet.</span><span class="sxs-lookup"><span data-stu-id="5fb08-135">In the **Environments** section, select the environment.</span></span>
1. <span data-ttu-id="5fb08-136">A **Környezet funkciói** területen válassza ki a **Kiskereskedelem kezelése** hivatkozást.</span><span class="sxs-lookup"><span data-stu-id="5fb08-136">Under **Environment features**, select the **Retail manage** link.</span></span>
1. <span data-ttu-id="5fb08-137">Az **e-kereskedelem** lapon válassza a **Beállítás** elemet.</span><span class="sxs-lookup"><span data-stu-id="5fb08-137">On the **e-Commerce** tab, select **Setup**.</span></span> <span data-ttu-id="5fb08-138">Megjelenik egy párbeszédpanel, amelyen meg kell adnia a létesítéshez szükséges adatokat.</span><span class="sxs-lookup"><span data-stu-id="5fb08-138">A dialog box appears, where you must enter the information that is required for provisioning.</span></span>
1. <span data-ttu-id="5fb08-139">Töltse ki a szükséges adatokat, majd lépjen a következő lapra.</span><span class="sxs-lookup"><span data-stu-id="5fb08-139">Fill in the required information, and then go to the next page.</span></span>
1. <span data-ttu-id="5fb08-140">A következő lapon töltse ki a szükséges adatokat, majd küldje el az űrlapot.</span><span class="sxs-lookup"><span data-stu-id="5fb08-140">On the next page, fill in the required information, and then submit the form.</span></span> <span data-ttu-id="5fb08-141">A rendszer visszaküldi az **e-kereskedelem** lapra, amelyen látnia kell, hogy elindult az inicializálás.</span><span class="sxs-lookup"><span data-stu-id="5fb08-141">You're returned to the **e-Commerce** tab, where you should see that initialization has been started.</span></span>
1. <span data-ttu-id="5fb08-142">Az inicializálás állapotának megtekintéséhez válassza a **Frissítés** lehetőséget, vagy térjen vissza később az **e-kereskedelem** lapra.</span><span class="sxs-lookup"><span data-stu-id="5fb08-142">To view the initialization status, either **Refresh** or return to the **e-Commerce** tab later.</span></span>
    
<span data-ttu-id="5fb08-143">Az e-kereskedelem LCS-ből történő inicializálásakor a rendszer számos olyan összetevőt létesít, amelyek szükségesek az e-kereskedelemhez, és társítja őket a környezethez.</span><span class="sxs-lookup"><span data-stu-id="5fb08-143">When e-commerce is initialized from LCS, the system provisions several components that are required for e-commerce and associates them with the environment.</span></span> <span data-ttu-id="5fb08-144">A létesítés befejezése után az **e-Commerce** lap a **Kiskereskedelem kezelése** oldalon frissítésre kerül, hogy tükrözze a létesítést.</span><span class="sxs-lookup"><span data-stu-id="5fb08-144">After provisioning is complete, the **e-Commerce** tab on the **Retail management** page is updated to reflect the provisioning.</span></span> <span data-ttu-id="5fb08-145">A lap megjeleníti a legújabb testreszabási telepítéseket és az egyéb folyamatban lévő telepítések állapotát.</span><span class="sxs-lookup"><span data-stu-id="5fb08-145">The page shows the latest customization deployments and the status of any other ongoing deployments.</span></span> <span data-ttu-id="5fb08-146">Az e-kereskedelmi webhelyhez és az e-kereskedelmi webhelyszerkesztési eszközhöz is tartalmaz hivatkozásokat, amelyben a webhelyek készülnek.</span><span class="sxs-lookup"><span data-stu-id="5fb08-146">It also includes links to the e-commerce site and the Commerce site builder where sites are authored.</span></span>

## <a name="access-commerce-site-builder"></a><span data-ttu-id="5fb08-147">Commerce webhelykészítő elérése</span><span class="sxs-lookup"><span data-stu-id="5fb08-147">Access Commerce site builder</span></span>

<span data-ttu-id="5fb08-148">A Commerce webhelykészítő eléréséhez nyissa meg az **E-kereskedelem** lapot a **Kiskereskedelem kezelése** oldalon az LCS-ben, és válassza ki az **e-kereskedelmi webhely felügyeleti eszköze** hivatkozását.</span><span class="sxs-lookup"><span data-stu-id="5fb08-148">To access Commerce site builder, go to the **e-Commerce** tab on the **Retail management** page in LCS and select the **e-Commerce site management tool** link.</span></span> <span data-ttu-id="5fb08-149">A webhelykészítő nyitóoldala bérlő szintű nézetet jelenít meg.</span><span class="sxs-lookup"><span data-stu-id="5fb08-149">The site builder landing page displays a tenant-level view.</span></span> <span data-ttu-id="5fb08-150">Erről az oldalról a következőket teheti:</span><span class="sxs-lookup"><span data-stu-id="5fb08-150">From this page, you can:</span></span>

- <span data-ttu-id="5fb08-151">Bérlő szintű beállítások módosítása.</span><span class="sxs-lookup"><span data-stu-id="5fb08-151">Modify tenant-level settings.</span></span>
- <span data-ttu-id="5fb08-152">Navigáljon bármelyik létrehozott webhelyhez, és kérjen engedélyt a megtekintésre.</span><span class="sxs-lookup"><span data-stu-id="5fb08-152">Navigate to any site you have created, and have permission to view.</span></span> 
- <span data-ttu-id="5fb08-153">A hozzáférés-ellenőrzés olyan funkciókat tartalmaz, mint a moderálás és a jelentés.</span><span class="sxs-lookup"><span data-stu-id="5fb08-153">Access Reviews features such as moderation and reporting.</span></span>
- <span data-ttu-id="5fb08-154">Új webhely létrehozása.</span><span class="sxs-lookup"><span data-stu-id="5fb08-154">Create a new site.</span></span> <span data-ttu-id="5fb08-155">További információ a webhelyek létrehozásáról: [E-kereskedelmi webhely létrehozása](create-ecommerce-site.md).</span><span class="sxs-lookup"><span data-stu-id="5fb08-155">For more information about how to create a new site, see [Create an e-commerce site](create-ecommerce-site.md) .</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="5fb08-156">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="5fb08-156">Additional resources</span></span>

[<span data-ttu-id="5fb08-157">Tartománynév konfigurálása</span><span class="sxs-lookup"><span data-stu-id="5fb08-157">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="5fb08-158">E-kereskedelmi webhely létrehozása</span><span class="sxs-lookup"><span data-stu-id="5fb08-158">Create an e-commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="5fb08-159">Dynamics 365 Commerce webhely társítása online csatornával</span><span class="sxs-lookup"><span data-stu-id="5fb08-159">Associate a Dynamics 365 Commerce site with an online channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="5fb08-160">robots.txt fájlok kezelése</span><span class="sxs-lookup"><span data-stu-id="5fb08-160">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="5fb08-161">URL-átirányítások tömeges feltöltése</span><span class="sxs-lookup"><span data-stu-id="5fb08-161">Upload URL redirects in bulk</span></span>](upload-bulk-redirects.md)

[<span data-ttu-id="5fb08-162">B2C-bérlő beállítása a Commerce-ben</span><span class="sxs-lookup"><span data-stu-id="5fb08-162">Set up a B2C tenant in Commerce</span></span>](set-up-B2C-tenant.md)

[<span data-ttu-id="5fb08-163">Felhasználói bejelentkezéshez használt egyéni lapok beállítása</span><span class="sxs-lookup"><span data-stu-id="5fb08-163">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="5fb08-164">Több B2C-bérlő konfigurálása egy Commerce környezetben</span><span class="sxs-lookup"><span data-stu-id="5fb08-164">Configure multiple B2C tenants in a Commerce environment</span></span>](configure-multi-B2C-tenants.md)

[<span data-ttu-id="5fb08-165">Tartalomkézbesítési hálózat (CDN) támogatásának hozzáadása</span><span class="sxs-lookup"><span data-stu-id="5fb08-165">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="5fb08-166">Helyalapú áruházészlelés engedélyezése</span><span class="sxs-lookup"><span data-stu-id="5fb08-166">Enable location-based store detection</span></span>](enable-store-detection.md)
