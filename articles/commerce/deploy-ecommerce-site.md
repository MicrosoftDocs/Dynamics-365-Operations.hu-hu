---
title: Új e-kereskedelmi bérlő telepítése
description: Ez a témakör azt mutatja be, hogyan lehet új e-kereskedelmi bérlőt telepíteni a Microsoft Dynamics Lifecycle Services (LCS) segítségével.
author: psimolin
manager: annbe
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 10dab1e62446ff7f60ad48fd0841bde5cfd29e12
ms.sourcegitcommit: ef3a1d7527311d00b69a1072ae5eb021ce68034c
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/09/2020
ms.locfileid: "2945513"
---
# <a name="deploy-a-new-e-commerce-tenant"></a><span data-ttu-id="48b7d-103">Új e-kereskedelmi bérlő telepítése</span><span class="sxs-lookup"><span data-stu-id="48b7d-103">Deploy a new e-Commerce tenant</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="48b7d-104">Ez a témakör azt mutatja be, hogyan lehet új e-kereskedelmi webhelyet telepíteni a Microsoft Dynamics Lifecycle Services (LCS) segítségével.</span><span class="sxs-lookup"><span data-stu-id="48b7d-104">This topic describes how to deploy a new e-Commerce site by using Microsoft Dynamics Lifecycle Services (LCS).</span></span>

## <a name="overview"></a><span data-ttu-id="48b7d-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="48b7d-105">Overview</span></span>
    
<span data-ttu-id="48b7d-106">A Microsoft Dynamics Lifecycle Services (LCS) egy felhőalapú együttműködési munkaterület, amelyet a partnerek és a vevők a projektjeik és a környezetek kezelésére, a Microsoft Dynamics termékekkel és szolgáltatásokkal kapcsolatos információk megtekintésére, valamint a terméktámogatási események létrehozására, nyomon követésére és böngészésére tudnak használni.</span><span class="sxs-lookup"><span data-stu-id="48b7d-106">Microsoft Dynamics Lifecycle Services (LCS) is a cloud-based collaborative workspace that partners and customers can use to manage their projects and environments, view the latest information about Microsoft Dynamics products and features, and create, track, and browse support incidents.</span></span> <span data-ttu-id="48b7d-107">Az e-kereskedelem kezelési szolgáltatásai integrálva vannak az LCS-be.</span><span class="sxs-lookup"><span data-stu-id="48b7d-107">E-Commerce management features are integrated into LCS.</span></span>

<span data-ttu-id="48b7d-108">További tájékoztatás az LCS-ről: [Lifecycle Services felhasználói útmutató](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide).</span><span class="sxs-lookup"><span data-stu-id="48b7d-108">To learn more about LCS, see the [Lifecycle Services User Guide](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide).</span></span>
    
## <a name="get-started"></a><span data-ttu-id="48b7d-109">Első lépések</span><span class="sxs-lookup"><span data-stu-id="48b7d-109">Get started</span></span>

<span data-ttu-id="48b7d-110">Az e-kereskedelem inicializálásához inicializálnia kell egy projektet, egy környezetet és egy Retail Cloud Scale Unit (RCSU) egységet.</span><span class="sxs-lookup"><span data-stu-id="48b7d-110">Before you can initialize e-Commerce, you must initialize a project, an environment, and a Retail Cloud Scale Unit (RCSU).</span></span> <span data-ttu-id="48b7d-111">Az LCS-ben történő inicializáláshoz a Projekttulajdonos vagy a Környezetkezelő szerepkör engedélyeivel kell rendelkeznie.</span><span class="sxs-lookup"><span data-stu-id="48b7d-111">To do the initialization in LCS, you must have permissions for either the Project Owner or Environment manager role.</span></span> <span data-ttu-id="48b7d-112">Támogatottak az éles és a tesztkörnyezeti topológiák.</span><span class="sxs-lookup"><span data-stu-id="48b7d-112">The production and sandbox environment topologies are supported.</span></span>

<span data-ttu-id="48b7d-113">A környezetekkel kapcsolatos további tudnivalókat lásd: [Környezet tervezése](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/imp-lifecycle/environment-planning).</span><span class="sxs-lookup"><span data-stu-id="48b7d-113">For more information about environments, see [Environment planning](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/imp-lifecycle/environment-planning).</span></span> <span data-ttu-id="48b7d-114">További tájékoztatás az RCSU-val kapcsolatban: [Retail Cloud Scale Unit inicializálása](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/deployment/initialize-retail-channels).</span><span class="sxs-lookup"><span data-stu-id="48b7d-114">For more information about RCSU, see [Initialize Retail Cloud Scale Unit](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/deployment/initialize-retail-channels).</span></span>

## <a name="initialize-e-commerce"></a><span data-ttu-id="48b7d-115">Az elektronikus kereskedelem inicializálása</span><span class="sxs-lookup"><span data-stu-id="48b7d-115">Initialize e-Commerce</span></span>

<span data-ttu-id="48b7d-116">Ezzel az eljárással lehet inicializálni egy létező környezet e-kereskedelmi funkcióját.</span><span class="sxs-lookup"><span data-stu-id="48b7d-116">Use this procedure to initialize the e-Commerce feature in an existing environment.</span></span>

<span data-ttu-id="48b7d-117">A kezdés előtt győződjön meg arról, hogy rendelkezik a következő szükséges információkkal:</span><span class="sxs-lookup"><span data-stu-id="48b7d-117">Before you begin, make sure that you have the following required information:</span></span>

- <span data-ttu-id="48b7d-118">Az használandó RCSU.</span><span class="sxs-lookup"><span data-stu-id="48b7d-118">The RCSU that will be used.</span></span>
- <span data-ttu-id="48b7d-119">Az e-kereskedelmi rendszeradminisztrátorok esetében használni kívánt Microsoft Azure Active Directory biztonsági csoport.</span><span class="sxs-lookup"><span data-stu-id="48b7d-119">The Microsoft Azure Active Directory security group that will be used for e-Commerce system admins.</span></span>
- <span data-ttu-id="48b7d-120">Az értékelések és vélemények moderátorai esetében használni kívánt Microsoft Azure Active Directory biztonsági csoport.</span><span class="sxs-lookup"><span data-stu-id="48b7d-120">The Microsoft Azure Active Directory security group that will be used for ratings and reviews moderators.</span></span>
- <span data-ttu-id="48b7d-121">A környezethez társítani kívánt tartományok.</span><span class="sxs-lookup"><span data-stu-id="48b7d-121">The domains that will be associated with the environment.</span></span>

<span data-ttu-id="48b7d-122">Ezenkívül a következő opcionális információkat gyűjtheti:</span><span class="sxs-lookup"><span data-stu-id="48b7d-122">In addition, you can collect the following optional information:</span></span>

- <span data-ttu-id="48b7d-123">Azure AD cég és ügyfél (B2C) közötti információk:</span><span class="sxs-lookup"><span data-stu-id="48b7d-123">Azure AD business-to-consumer (B2C) information:</span></span>

    - <span data-ttu-id="48b7d-124">Bérlő neve.</span><span class="sxs-lookup"><span data-stu-id="48b7d-124">Tenant Name.</span></span>
    - <span data-ttu-id="48b7d-125">Ügyfélazonosító.</span><span class="sxs-lookup"><span data-stu-id="48b7d-125">Client ID.</span></span>
    - <span data-ttu-id="48b7d-126">Bejelentkezéshez tartozó egyéni tartomány.</span><span class="sxs-lookup"><span data-stu-id="48b7d-126">Login Custom Domain.</span></span>
    - <span data-ttu-id="48b7d-127">Válasz URL.</span><span class="sxs-lookup"><span data-stu-id="48b7d-127">Reply URL.</span></span>
    - <span data-ttu-id="48b7d-128">Regisztrációra és bejelentkezésre vonatkozó irányelv azonosítója.</span><span class="sxs-lookup"><span data-stu-id="48b7d-128">SignUp SignIn Policy ID.</span></span>
    - <span data-ttu-id="48b7d-129">Jelszó visszaállítására vonatkozó irányelv azonosítója.</span><span class="sxs-lookup"><span data-stu-id="48b7d-129">Reset password Policy ID.</span></span>
    - <span data-ttu-id="48b7d-130">Profilszerkesztési irányelv azonosítója.</span><span class="sxs-lookup"><span data-stu-id="48b7d-130">Edit Profile Policy ID.</span></span>

[!NOTE]
<span data-ttu-id="48b7d-131">Ez az információ később is hozzáadható szolgáltatási kérelem alapján.</span><span class="sxs-lookup"><span data-stu-id="48b7d-131">This information can be added later, through a service request.</span></span>

<span data-ttu-id="48b7d-132">Miután összegyűjtötte a szükséges adatokat, hajtsa végre az alábbi lépéseket az e-kereskedelem inicializálásához.</span><span class="sxs-lookup"><span data-stu-id="48b7d-132">After you've collected the required information, follow these steps to initialize e-Commerce.</span></span>

1. <span data-ttu-id="48b7d-133">Bejelentkezés az [LCS](https://lcs.dynamics.com) alkalmazásba.</span><span class="sxs-lookup"><span data-stu-id="48b7d-133">Sign in to [LCS](https://lcs.dynamics.com).</span></span>
1. <span data-ttu-id="48b7d-134">Nyissa meg azt a projektet, amely tartalmazza a projektet, ahol az e-kereskedelmet inicializálni kívánja.</span><span class="sxs-lookup"><span data-stu-id="48b7d-134">Open the project that contains the environment where you want to initialize e-Commerce.</span></span>
1. <span data-ttu-id="48b7d-135">A **Környezetek** szakaszban válassza ki a környezetet.</span><span class="sxs-lookup"><span data-stu-id="48b7d-135">In the **Environments** section, select the environment.</span></span>
1. <span data-ttu-id="48b7d-136">A **Környezet funkciói**területen válassza ki a **Kiskereskedelem kezelése** hivatkozást.</span><span class="sxs-lookup"><span data-stu-id="48b7d-136">Under **Environment features**, select the **Retail manage** link.</span></span>
1. <span data-ttu-id="48b7d-137">Az **e-kereskedelem** lapon válassza a **Beállítás** elemet.</span><span class="sxs-lookup"><span data-stu-id="48b7d-137">On the **e-Commerce** tab, select **Setup**.</span></span> <span data-ttu-id="48b7d-138">Megjelenik egy párbeszédpanel, amelyen meg kell adnia a létesítéshez szükséges adatokat.</span><span class="sxs-lookup"><span data-stu-id="48b7d-138">A dialog box appears, where you must enter the information that is required for provisioning.</span></span>
1. <span data-ttu-id="48b7d-139">Töltse ki a szükséges adatokat, majd lépjen a következő lapra.</span><span class="sxs-lookup"><span data-stu-id="48b7d-139">Fill in the required information, and then go to the next page.</span></span>
1. <span data-ttu-id="48b7d-140">A következő lapon töltse ki a szükséges adatokat, majd küldje el az űrlapot.</span><span class="sxs-lookup"><span data-stu-id="48b7d-140">On the next page, fill in the required information, and then submit the form.</span></span> <span data-ttu-id="48b7d-141">A rendszer visszaküldi az **e-kereskedelem** lapra, amelyen látnia kell, hogy elindult az inicializálás.</span><span class="sxs-lookup"><span data-stu-id="48b7d-141">You're returned to the **e-Commerce** tab, where you should see that initialization has been started.</span></span>
1. <span data-ttu-id="48b7d-142">Az inicializálás állapotának megtekintéséhez válassza a **Frissítés** lehetőséget, vagy térjen vissza később az **e-kereskedelem** lapra.</span><span class="sxs-lookup"><span data-stu-id="48b7d-142">To view the initialization status, either **Refresh** or return to the **e-Commerce** tab later.</span></span>
    
<span data-ttu-id="48b7d-143">Az e-kereskedelem LCS-ből történő inicializálásakor a rendszer számos olyan összetevőt létesít, amelyek szükségesek az e-kereskedelemhez, és társítja őket a környezethez.</span><span class="sxs-lookup"><span data-stu-id="48b7d-143">When e-Commerce is initialized from LCS, the system provisions several components that are required for e-Commerce and associates them with the environment.</span></span> <span data-ttu-id="48b7d-144">A létesítés befejezése után az **e-kereskedelem** lap a **Kiskereskedelem kezelése** oldalon frissítésre kerül, hogy tükrözze a létesítést.</span><span class="sxs-lookup"><span data-stu-id="48b7d-144">After provisioning is completed, the **e-Commerce** tab on the **Retail management** page is updated to reflect the provisioning.</span></span> <span data-ttu-id="48b7d-145">A lap megjeleníti a legújabb testreszabási telepítéseket és az egyéb folyamatban lévő telepítések állapotát.</span><span class="sxs-lookup"><span data-stu-id="48b7d-145">The page shows the latest customization deployments and the status of any other ongoing deployments.</span></span> <span data-ttu-id="48b7d-146">Az e-kereskedelmi webhelyhez és az e-kereskedelmi webhelykezelő eszközhöz (szerkesztési eszköz) is tartalmaz hivatkozásokat.</span><span class="sxs-lookup"><span data-stu-id="48b7d-146">It also includes links to the e-Commerce site and the e-Commerce site management tool (the authoring tool).</span></span>

## <a name="access-the-authoring-environment"></a><span data-ttu-id="48b7d-147">Hozzáférés a szerkesztési környezethez</span><span class="sxs-lookup"><span data-stu-id="48b7d-147">Access the authoring environment</span></span>

<span data-ttu-id="48b7d-148">A fejlesztői környezet eléréséhez nyissa meg az **e-kereskedelem** lapot a **Kiskereskedelem kezelése** oldalon.</span><span class="sxs-lookup"><span data-stu-id="48b7d-148">To access the authoring environment, go to the **e-Commerce** tab on the **Retail management** page.</span></span> <span data-ttu-id="48b7d-149">Itt talál az e-kereskedelmi webhelyre és a webhelykezelő eszközre mutató hivatkozásokat.</span><span class="sxs-lookup"><span data-stu-id="48b7d-149">There, you will find links to your e-Commerce site and the site management tool.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="48b7d-150">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="48b7d-150">Additional resources</span></span>

[<span data-ttu-id="48b7d-151">A tartománynév konfigurálása</span><span class="sxs-lookup"><span data-stu-id="48b7d-151">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="48b7d-152">E-kereskedelmi webhely létrehozása</span><span class="sxs-lookup"><span data-stu-id="48b7d-152">Create an e-Commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="48b7d-153">Online webhely társítása csatornával</span><span class="sxs-lookup"><span data-stu-id="48b7d-153">Associate an online site with a channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="48b7d-154">Robots.txt fájlok kezelése</span><span class="sxs-lookup"><span data-stu-id="48b7d-154">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="48b7d-155">Felhasználói bejelentkezéshez használt egyéni lapok beállítása</span><span class="sxs-lookup"><span data-stu-id="48b7d-155">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="48b7d-156">Tartalomkézbesítési hálózat (CDN) támogatásának hozzáadása</span><span class="sxs-lookup"><span data-stu-id="48b7d-156">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="48b7d-157">Helyalapú áruházészlelés engedélyezése</span><span class="sxs-lookup"><span data-stu-id="48b7d-157">Enable location-based store detection</span></span>](enable-store-detection.md)
