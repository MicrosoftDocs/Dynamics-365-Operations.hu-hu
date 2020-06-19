---
title: Dynamics 365 Commerce előnézeti környezet létesítése
description: Ez a témakör bemutatja, hogyan lehet egy Microsoft Dynamics 365 Commerce előzetes környezetet létesíteni.
author: psimolin
manager: annbe
ms.date: 06/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: c109c2326cf01739255b49587c15aa34ad884f6a
ms.sourcegitcommit: be7e4378c8122c6e7cfc4e7991efbdffee45e006
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2020
ms.locfileid: "3426465"
---
# <a name="provision-a-dynamics-365-commerce-preview-environment"></a><span data-ttu-id="7c87e-103">Dynamics 365 Commerce előnézeti környezet létesítése</span><span class="sxs-lookup"><span data-stu-id="7c87e-103">Provision a Dynamics 365 Commerce preview environment</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="7c87e-104">Ez a témakör bemutatja, hogyan lehet egy Dynamics 365 Commerce előzetes környezetet létesíteni.</span><span class="sxs-lookup"><span data-stu-id="7c87e-104">This topic explains how to provision a Dynamics 365 Commerce preview environment.</span></span>

<span data-ttu-id="7c87e-105">A művelet elkezdése előtt ajánljuk, hogy a jelen témakörben keressen egy rövid áttekintést, hogy megtudja, mire van szüksége a folyamatnak.</span><span class="sxs-lookup"><span data-stu-id="7c87e-105">Before you begin, we recommend that you take a quick scan through this topic to get an idea of what the process requires.</span></span>

> [!NOTE]
> <span data-ttu-id="7c87e-106">Ha még nem kapott hozzáférést a Dynamics 365 Commerce előzeteséhez, a [Dynamics 365 Commerce webhelyről](https://aka.ms/Dynamics365CommerceWebsite) kérhet előzetes hozzáférést.</span><span class="sxs-lookup"><span data-stu-id="7c87e-106">If you haven't yet been granted access to the Dynamics 365 Commerce preview, you can request preview access from the [Dynamics 365 Commerce website](https://aka.ms/Dynamics365CommerceWebsite).</span></span>

## <a name="overview"></a><span data-ttu-id="7c87e-107">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="7c87e-107">Overview</span></span>

<span data-ttu-id="7c87e-108">A Kereskedelem előzetes környezetének sikeres létrehozásához létre kell hoznia egy projektet, amely egy adott terméknévvel és típussal rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="7c87e-108">To successfully provision your Commerce preview environment, you must create a project that has a specific product name and type.</span></span> <span data-ttu-id="7c87e-109">A környezet és a Commerce Scale Unit (CSU) szintén rendelkezik bizonyos paraméterekkel, amelyeket későbbiekben, az e-kereskedelem előzetesekor használnia kell.</span><span class="sxs-lookup"><span data-stu-id="7c87e-109">The environment and Commerce Scale Unit (CSU) also have some specific parameters that you must use when you provision e-Commerce later.</span></span> <span data-ttu-id="7c87e-110">Az ebben a témakörben szereplő útmutatás leírja a létesítéshez szükséges összes lépést és a használandó paramétereket.</span><span class="sxs-lookup"><span data-stu-id="7c87e-110">The instructions in this topic describe all the steps required to complete provisioning and the parameters that you must use.</span></span>

<span data-ttu-id="7c87e-111">A Kereskedelem előzetes környezetének sikeres létesítését követően meg kell tennie néhány létesítést követő lépést a felkészítéséhez.</span><span class="sxs-lookup"><span data-stu-id="7c87e-111">After you successfully provision your Commerce preview environment, you must complete a few post-provisioning steps to prepare it.</span></span> <span data-ttu-id="7c87e-112">Bizonyos lépések nem kötelezők, az értékelni kívánt rendszer bizonyos szempontjaitól függően.</span><span class="sxs-lookup"><span data-stu-id="7c87e-112">Some steps are optional, depending on the aspects of the system that you want to evaluate.</span></span> <span data-ttu-id="7c87e-113">A választható lépéseket a későbbiekben bármikor befejezheti.</span><span class="sxs-lookup"><span data-stu-id="7c87e-113">You can always complete the optional steps later.</span></span>

<span data-ttu-id="7c87e-114">A Kereskedelem előzetes környezetének létesítés utáni konfigurálásáról további információt a következő témakörben talál: [Kereskedelem előzetes környezetének konfigurálása](cpe-post-provisioning.md).</span><span class="sxs-lookup"><span data-stu-id="7c87e-114">For information about how to configure your Commerce preview environment after you provision it, see [Configure a Commerce preview environment](cpe-post-provisioning.md).</span></span> <span data-ttu-id="7c87e-115">A Kereskedelem előzetes környezete nem kötelező funkcióinak konfigurálásáról további információt a következő témakörben talál: [Kereskedelem előzetes környezete nem kötelező funkcióinak konfigurálása](cpe-optional-features.md).</span><span class="sxs-lookup"><span data-stu-id="7c87e-115">For information about how to configure optional features for your Commerce preview environment, see [Configure optional features for a Commerce preview environment](cpe-optional-features.md).</span></span>

<span data-ttu-id="7c87e-116">Ha kérdései vannak a létesítés lépéseivel kapcsolatban, vagy bármilyen probléma merülne fel, akkor tudassa a Microsofttal a [Microsoft Dynamics 365 Commerce előzetes Yammer-csoportjában](https://aka.ms/Dynamics365CommercePreviewYammer).</span><span class="sxs-lookup"><span data-stu-id="7c87e-116">If you have any questions about the provisioning steps, or if you encounter any issues, let Microsoft know in the [Microsoft Dynamics 365 Commerce Preview Yammer group](https://aka.ms/Dynamics365CommercePreviewYammer).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7c87e-117">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="7c87e-117">Prerequisites</span></span>

<span data-ttu-id="7c87e-118">A következő előfeltételeknek kell érvényben lenniük a Kereskedelem előnézet környezetének létesítése előtt:</span><span class="sxs-lookup"><span data-stu-id="7c87e-118">The following prerequisites must be in place before you can provision your Commerce preview environment:</span></span>

- <span data-ttu-id="7c87e-119">Elérhetővé teszi a Microsoft Dynamics Lifecycle Services (LCS) portál elérését.</span><span class="sxs-lookup"><span data-stu-id="7c87e-119">You have access to the Microsoft Dynamics Lifecycle Services (LCS) portal.</span></span>
- <span data-ttu-id="7c87e-120">Ön meglévő Microsoft Dynamics 365 partner vagy vevő, és létre tud hozni egy Dynamics 365 Commerce projektet.</span><span class="sxs-lookup"><span data-stu-id="7c87e-120">You are an existing Microsoft Dynamics 365 partner or customer and are able to create a Dynamics 365 Commerce project.</span></span>
- <span data-ttu-id="7c87e-121">Ön felvételt nyert a Dynamics 365 Commerce előzetes programba.</span><span class="sxs-lookup"><span data-stu-id="7c87e-121">You've been accepted into the Dynamics 365 Commerce Preview program.</span></span>
- <span data-ttu-id="7c87e-122">Rendelkezik a szükséges jogosultságokkal az **Áttelepítés, megoldások létrehozása és tanulás** projekt létrehozására.</span><span class="sxs-lookup"><span data-stu-id="7c87e-122">You have the required permissions to create a project for **Migrate, create solutions, and learn**.</span></span>
- <span data-ttu-id="7c87e-123">Ön tagja a **Környezetkezelő** vagy **Projekttulajdonos** szerepkörnek abban a projektben, amelyben a környezet létesítése történik.</span><span class="sxs-lookup"><span data-stu-id="7c87e-123">You're a member of the **Environment manager** or **Project owner** role in the project where you will provision the environment.</span></span>
- <span data-ttu-id="7c87e-124">Rendszergazdai hozzáféréssel rendelkezik a Microsoft Azure-előfizetéshez, vagy felveheti a kapcsolatot egy előfizetési adminisztrátorral, aki elvégezheti a két lépést, amelyek az Ön nevében rendszergazdai jogosultságot igényelnek.</span><span class="sxs-lookup"><span data-stu-id="7c87e-124">You have admin access to your Microsoft Azure subscription, or you're in contact with a subscription admin who can complete the two steps that require admin permissions on your behalf.</span></span>
- <span data-ttu-id="7c87e-125">Rendelkezésére áll az Azure Active Directory (Azure AD) bérlői azonosító.</span><span class="sxs-lookup"><span data-stu-id="7c87e-125">You have your Azure Active Directory (Azure AD) tenant ID available.</span></span>
- <span data-ttu-id="7c87e-126">Létrehozott egy Azure AD biztonsági csoportot, amelyet az e-kereskedelmi rendszeradminisztrátori csoportként használhat, és a rendelkezésére áll annak azonosítója.</span><span class="sxs-lookup"><span data-stu-id="7c87e-126">You've created an Azure AD security group that can be used as an e-Commerce system admin group, and you have its ID available.</span></span>
- <span data-ttu-id="7c87e-127">Létrehozott egy Azure AD biztonsági csoportot, amelyet minősítési vagy értékelési moderátori csoportként használhat, és a rendelkezésére áll annak azonosítója.</span><span class="sxs-lookup"><span data-stu-id="7c87e-127">You've created an Azure AD security group that can be used as a Ratings and Reviews moderator group, and you have its ID available.</span></span> <span data-ttu-id="7c87e-128">(Ez a biztonsági csoport lehet ugyanaz, mint az e-kereskedelmi rendszeradminisztrátori csoport.)</span><span class="sxs-lookup"><span data-stu-id="7c87e-128">(This security group can be the same as the e-Commerce system admin group.)</span></span>

## <a name="provision-your-commerce-preview-environment"></a><span data-ttu-id="7c87e-129">Commerce előzetes környezet kiépítése</span><span class="sxs-lookup"><span data-stu-id="7c87e-129">Provision your Commerce preview environment</span></span>

<span data-ttu-id="7c87e-130">Ezek az eljárások ismertetik a Commerce előzetes környezet kiépítését.</span><span class="sxs-lookup"><span data-stu-id="7c87e-130">These procedures explain how to provision a Commerce preview environment.</span></span> <span data-ttu-id="7c87e-131">A sikeres befejezést követően a Commerce előzetes környezete készen áll a konfigurációra.</span><span class="sxs-lookup"><span data-stu-id="7c87e-131">After you successfully complete them, the Commerce preview environment will be ready for configuration.</span></span> <span data-ttu-id="7c87e-132">Az itt ismertetett tevékenységek az LCS portálon történnek.</span><span class="sxs-lookup"><span data-stu-id="7c87e-132">All the activities that are described here occur in the LCS portal.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7c87e-133">Az előzetes hozzáférés LCS-fiókhoz és szervezethez kötődik, amelyet a Commerce előzetes alkalmazásban megadott.</span><span class="sxs-lookup"><span data-stu-id="7c87e-133">Preview access is tied to the LCS account and organization that you specified in your Commerce preview application.</span></span> <span data-ttu-id="7c87e-134">Ugyanazt a fiókot kell használnia a Commerce előzetes környezet létesítése érdekében.</span><span class="sxs-lookup"><span data-stu-id="7c87e-134">You must use the same account to provision the Commerce preview environment.</span></span> <span data-ttu-id="7c87e-135">Ha a Commerce előzetes környezethez más LCS-fiókot vagy bérlőt kell használnia, ezeket az adatokat meg kell adnia a Microsoftnak.</span><span class="sxs-lookup"><span data-stu-id="7c87e-135">If you need to use a different LCS account or tenant for the Commerce preview environment, you must provide those details to Microsoft.</span></span> <span data-ttu-id="7c87e-136">A kapcsolattartói adatokért tekintse meg a [Commerce előzetes környezet támogatása](#commerce-preview-environment-support) szakaszt a témakör későbbi részében.</span><span class="sxs-lookup"><span data-stu-id="7c87e-136">For contact information, see the [Commerce preview environment support](#commerce-preview-environment-support) section later in this topic.</span></span>

### <a name="confirm-that-preview-features-are-available-and-turned-on-in-lcs"></a><span data-ttu-id="7c87e-137">Ellenőrizze, hogy az előzetes funkciók elérhetők-e és be vannak-e kapcsolva az LCS rendszerben</span><span class="sxs-lookup"><span data-stu-id="7c87e-137">Confirm that preview features are available and turned on in LCS</span></span>

<span data-ttu-id="7c87e-138">Annak ellenőrzésére, hogy elérhetők-e az előzetes funkciók és be vannak-e kapcsolva az LCS rendszerben, kövesse ezeket a lépéseket.</span><span class="sxs-lookup"><span data-stu-id="7c87e-138">To confirm that preview features are available and turned on in LCS, follow these steps.</span></span>

1. <span data-ttu-id="7c87e-139">Jelentkezzen be az [LCS-portálra](https://lcs.dynamics.com) az előzeteshez való hozzáférés kérésére használt LCS-fiók használatával.</span><span class="sxs-lookup"><span data-stu-id="7c87e-139">Sign in to the [LCS portal](https://lcs.dynamics.com) by using the same LCS account that you used to request access to the preview.</span></span>
1. <span data-ttu-id="7c87e-140">A LCS kezdőoldalán görgessen teljesen jobbra, majd válassza az **Előzetes funkció kezelése** csempét.</span><span class="sxs-lookup"><span data-stu-id="7c87e-140">On the LCS home page, scroll all the way to the right, and select the **Preview feature management** tile.</span></span>

    ![Előzetes funkció kezelése csempe](./media/preview1.png)

1. <span data-ttu-id="7c87e-142">Görgessen le a **Privát előzetes funkciók** elemre, és erősítse meg, hogy a következő szolgáltatások elérhetők és be vannak kapcsolva:</span><span class="sxs-lookup"><span data-stu-id="7c87e-142">Scroll down to **Private preview features**, and confirm that the following features are available and turned on:</span></span>

    - <span data-ttu-id="7c87e-143">Elektronikus kereskedelem értékelése</span><span class="sxs-lookup"><span data-stu-id="7c87e-143">e-Commerce Evaluation</span></span>
    - <span data-ttu-id="7c87e-144">Kereskedelem előnézeti környezetei</span><span class="sxs-lookup"><span data-stu-id="7c87e-144">Commerce Preview Program Environments</span></span>

    ![Privát előzetes funkciók](./media/preview2.png)

1. <span data-ttu-id="7c87e-146">Ha ezek a funkciók nem jelennek meg a listában, forduljon a Microsofthoz, és adja meg munkahelyi e-mail-címét, LCS-fiókját és bérlőadatait.</span><span class="sxs-lookup"><span data-stu-id="7c87e-146">If those features don't appear in the list, contact Microsoft, and provide your work email address, LCS account, and tenant details.</span></span> <span data-ttu-id="7c87e-147">A kapcsolattartói adatokért tekintse meg a [Commerce előzetes környezet támogatása](#commerce-preview-environment-support) szakaszt.</span><span class="sxs-lookup"><span data-stu-id="7c87e-147">For contact information, see the [Commerce preview environment support](#commerce-preview-environment-support) section.</span></span>

### <a name="create-a-new-project"></a><span data-ttu-id="7c87e-148">Új projekt létrehozása</span><span class="sxs-lookup"><span data-stu-id="7c87e-148">Create a new project</span></span>

<span data-ttu-id="7c87e-149">Új LCS projekt létrehozásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="7c87e-149">To create a new project in LCS, follow these steps.</span></span>

1. <span data-ttu-id="7c87e-150">Az LCS-kezdőlapon válassza a pluszjelet (**+**) a projekt létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="7c87e-150">On the LCS home page, select the plus sign (**+**) to create a project.</span></span>
1. <span data-ttu-id="7c87e-151">A jobb oldali panelen kövesse az alábbi lépések egyikét:</span><span class="sxs-lookup"><span data-stu-id="7c87e-151">In the right pane, follow one of these steps:</span></span>

    - <span data-ttu-id="7c87e-152">Ha Ön partner, válassza az **Áttelepítés, megoldások létrehozása és tanulás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7c87e-152">If you're a partner, select **Migrate, create solutions, and learn**.</span></span>
    - <span data-ttu-id="7c87e-153">Ha Ön ügyfél, válassza ki **Lehetséges előértékesítések** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7c87e-153">If you're a customer, select **Prospective presales**.</span></span>

1. <span data-ttu-id="7c87e-154">Adja meg a nevet, leírást és iparágat.</span><span class="sxs-lookup"><span data-stu-id="7c87e-154">Enter a name, description, and industry.</span></span>
1. <span data-ttu-id="7c87e-155">A **Terméknév** mezőben válassza a **Dynamics 365 Retail** elemet.</span><span class="sxs-lookup"><span data-stu-id="7c87e-155">In the **Product name** field, select **Dynamics 365 Retail**.</span></span>
1. <span data-ttu-id="7c87e-156">A **Termék verziója** mezőben válassza a **Dynamics 365 Retail** elemet.</span><span class="sxs-lookup"><span data-stu-id="7c87e-156">In the **Product version** field, select **Dynamics 365 Retail**.</span></span>
1. <span data-ttu-id="7c87e-157">A **Módszertan** mezőben válassza a **Dynamics Retail-implementáció módszertana** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7c87e-157">In the **Methodology** field, select **Dynamics Retail implementation methodology**.</span></span>
1. <span data-ttu-id="7c87e-158">Nem kötelező: Szerepköröket és felhasználókat létező projektből is importálhat.</span><span class="sxs-lookup"><span data-stu-id="7c87e-158">Optional: You can import roles and users from an existing project.</span></span>
1. <span data-ttu-id="7c87e-159">Válassza a **Létrehozása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7c87e-159">Select **Create**.</span></span> <span data-ttu-id="7c87e-160">Megjelenik a projektnézet.</span><span class="sxs-lookup"><span data-stu-id="7c87e-160">The project view appears.</span></span>

### <a name="add-the-azure-connector"></a><span data-ttu-id="7c87e-161">Azure-összekötő hozzáadása</span><span class="sxs-lookup"><span data-stu-id="7c87e-161">Add the Azure Connector</span></span>

<span data-ttu-id="7c87e-162">Az Azure-összekötő LCS-projekthez való hozzáadásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="7c87e-162">To add the Azure Connector to your LCS project, follow these steps.</span></span>

1. <span data-ttu-id="7c87e-163">Tegye a következők egyikét:</span><span class="sxs-lookup"><span data-stu-id="7c87e-163">Follow one of these steps:</span></span>

    - <span data-ttu-id="7c87e-164">Ha Ön partner, válassza a **Projektbeállítások** csempét a jobb szélen.</span><span class="sxs-lookup"><span data-stu-id="7c87e-164">If you're a partner, select the **Project settings** tile on the far right.</span></span>
    - <span data-ttu-id="7c87e-165">Ha Ön ügyfél, válassza a felső menü **Projekt beállításai** elemét.</span><span class="sxs-lookup"><span data-stu-id="7c87e-165">If you're a customer, select **Project settings** on the top menu.</span></span>

1. <span data-ttu-id="7c87e-166">Válassza ki az **Azure-összekötőket**.</span><span class="sxs-lookup"><span data-stu-id="7c87e-166">Select **Azure connectors**.</span></span>
1. <span data-ttu-id="7c87e-167">Válassza a **+ hozzáadás** elemet az Azure-összekötő hozzáadásához.</span><span class="sxs-lookup"><span data-stu-id="7c87e-167">Select **Add** to add the Azure Connector.</span></span>
1. <span data-ttu-id="7c87e-168">Adjon meg egy nevet.</span><span class="sxs-lookup"><span data-stu-id="7c87e-168">Enter a name.</span></span>
1. <span data-ttu-id="7c87e-169">Adja meg Azure-előfizetésének azonosítóját.</span><span class="sxs-lookup"><span data-stu-id="7c87e-169">Enter your Azure subscription ID.</span></span>
1. <span data-ttu-id="7c87e-170">Kapcsolja be a **Konfigurálás az Azure Resource Manager (ARM) használatához** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7c87e-170">Turn on the **Configure to use Azure Resource Manager (ARM)** option.</span></span>
1. <span data-ttu-id="7c87e-171">Ellenőrizze, hogy az **Azure-előfizetés AAD-bérlőjének tartománya (vagy azonosítója)** értéke helyes.</span><span class="sxs-lookup"><span data-stu-id="7c87e-171">Verify that the **Azure subscription AAD Tenant Domain (or ID)** value is correct.</span></span> <span data-ttu-id="7c87e-172">Szükség esetén forduljon a Azure előfizetés adminisztrátorához.</span><span class="sxs-lookup"><span data-stu-id="7c87e-172">Consult your Azure subscription admin as required.</span></span>
1. <span data-ttu-id="7c87e-173">Válassza ki **Következő** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7c87e-173">Select **Next**.</span></span>
1. <span data-ttu-id="7c87e-174">Kövesse az oldalon megjelenő utasításokat, és adjon hozzáférést a szükséges alkalmazásoknak az előfizetéshez.</span><span class="sxs-lookup"><span data-stu-id="7c87e-174">Follow the instructions on the page to grant the required applications access to your subscription.</span></span> <span data-ttu-id="7c87e-175">Szükség esetén forduljon a Azure előfizetés adminisztrátorához.</span><span class="sxs-lookup"><span data-stu-id="7c87e-175">Consult your Azure subscription admin as required.</span></span>

    1. <span data-ttu-id="7c87e-176">Jelentkezzen be az [Azure portálra](https://portal.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="7c87e-176">Sign in to the [Azure portal](https://portal.azure.com/).</span></span>
    1. <span data-ttu-id="7c87e-177">Győződjön meg arról, hogy a megfelelő könyvtár van kijelölve, majd a bal oldali menüben válassza az **előfizetése** menüpontot.</span><span class="sxs-lookup"><span data-stu-id="7c87e-177">Make sure that the correct directory is selected, and then, on the menu on the left, select **Subscriptions**.</span></span>
    1. <span data-ttu-id="7c87e-178">Keresse meg a megfelelő előfizetést a listában, majd válassza ki azt.</span><span class="sxs-lookup"><span data-stu-id="7c87e-178">Find the correct subscription in the list, and select it.</span></span> <span data-ttu-id="7c87e-179">Szükség szerint használja a keresési funkciót.</span><span class="sxs-lookup"><span data-stu-id="7c87e-179">Use the search functionality as required.</span></span>
    1. <span data-ttu-id="7c87e-180">A menüben válassza az **Elérés szabályozása (IAM)** elemet.</span><span class="sxs-lookup"><span data-stu-id="7c87e-180">On the menu, select **Access control (IAM)**.</span></span>
    1. <span data-ttu-id="7c87e-181">A jobb oldalon található **Szerepkör-hozzárendelés** hozzáadása területen kattintson a **Hozzáadás** gombra.</span><span class="sxs-lookup"><span data-stu-id="7c87e-181">On the right, under **Add a role assignment**, select **Add**.</span></span> <span data-ttu-id="7c87e-182">Megjelenik **Szerepkör hozzárendelése** panel.</span><span class="sxs-lookup"><span data-stu-id="7c87e-182">The **Add role assignment** pane appears.</span></span>
    1. <span data-ttu-id="7c87e-183">A **Szerepkör** mezőben válassza a **Közreműködő** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7c87e-183">In the **Role** field, select **Contributor**.</span></span>
    1. <span data-ttu-id="7c87e-184">A **Hozzáférés hozzárendelése** mezőben hagyja az alapértelmezett értéket **Azure AD-felhasználó, csoport vagy szolgáltatásnév** beállításon.</span><span class="sxs-lookup"><span data-stu-id="7c87e-184">In the **Assign access to** field, leave the default value, **Azure AD user, group, or service principal**.</span></span>
    1. <span data-ttu-id="7c87e-185">A **Kijelölés** alatt adja meg a **b96b7e94-b82e-4e71-99a0-cf7fb188acea** értéket.</span><span class="sxs-lookup"><span data-stu-id="7c87e-185">Under **Select**, enter **b96b7e94-b82e-4e71-99a0-cf7fb188acea**.</span></span>
    1. <span data-ttu-id="7c87e-186">Válassza ki a **Dynamics telepítési szolgáltatások \[wsfed-enabled\]** elemet a listáról.</span><span class="sxs-lookup"><span data-stu-id="7c87e-186">Select **Dynamics Deployment Services \[wsfed-enabled\]** in the list.</span></span>
    1. <span data-ttu-id="7c87e-187">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7c87e-187">Select **Save**.</span></span>

1. <span data-ttu-id="7c87e-188">Válassza ki **Következő** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7c87e-188">Select **Next**.</span></span>
1. <span data-ttu-id="7c87e-189">Kövesse az oldalon megjelenő utasításokat, és adjon hozzáférést a szükséges alkalmazásoknak az előfizetéshez.</span><span class="sxs-lookup"><span data-stu-id="7c87e-189">Follow the instructions on the page to grant the required applications access to your subscription.</span></span> <span data-ttu-id="7c87e-190">Szükség esetén forduljon a Azure előfizetés adminisztrátorához.</span><span class="sxs-lookup"><span data-stu-id="7c87e-190">Consult your Azure subscription admin as required.</span></span>
1. <span data-ttu-id="7c87e-191">Válassza ki **Következő** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7c87e-191">Select **Next**.</span></span>
1. <span data-ttu-id="7c87e-192">A **Azure régió** mezőben válassza az **Egyesült Államok keleti része**, **Egyesült Államok kelti része 2**, **Egyesült Államok nyugati része** vagy **Egyesült Államok nyugati része 2** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7c87e-192">In the **Azure region** field, select **East US**, **East US 2**, **West US**, or **West US 2**.</span></span>
1. <span data-ttu-id="7c87e-193">Válassza a **Kapcsolódás** parancsot.</span><span class="sxs-lookup"><span data-stu-id="7c87e-193">Select **Connect**.</span></span> <span data-ttu-id="7c87e-194">Az Azure-összekötőnek meg kell jelennie a listában.</span><span class="sxs-lookup"><span data-stu-id="7c87e-194">Your Azure Connector should appear in the list.</span></span>

### <a name="import-the-commerce-preview-demo-base-extension"></a><span data-ttu-id="7c87e-195">A Commerce előzetes bemutató alapbővítményének importálása</span><span class="sxs-lookup"><span data-stu-id="7c87e-195">Import the Commerce Preview Demo Base Extension</span></span>

<span data-ttu-id="7c87e-196">A Commerce előzetes emutató alapbővítményének projektbe importálásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="7c87e-196">To import the Commerce Preview Demo Base Extension into your project, follow these steps.</span></span>

1. <span data-ttu-id="7c87e-197">Nyissa meg a projekt kezdőlapját a tetején lévő projektnév kiválasztásával.</span><span class="sxs-lookup"><span data-stu-id="7c87e-197">Open the home page for your project by selecting the project name at the top.</span></span>
1. <span data-ttu-id="7c87e-198">Tegye a következők egyikét:</span><span class="sxs-lookup"><span data-stu-id="7c87e-198">Follow one of these steps:</span></span>

    - <span data-ttu-id="7c87e-199">Ha Ön partner, válassza az **Eszköztár** csempét a jobb szélen.</span><span class="sxs-lookup"><span data-stu-id="7c87e-199">If you're a partner, select the **Asset library** tile on the far right.</span></span>
    - <span data-ttu-id="7c87e-200">Ha Ön ügyfél, válassza a felső menü **Eszköztár** elemét.</span><span class="sxs-lookup"><span data-stu-id="7c87e-200">If you're a customer, select **Asset library** on the top menu.</span></span>

1. <span data-ttu-id="7c87e-201">Válassza a **Telepíthető szoftvercsomag** elemet a bal oldali listából.</span><span class="sxs-lookup"><span data-stu-id="7c87e-201">In the list on the left, select **Software deployable package**.</span></span>
1. <span data-ttu-id="7c87e-202">Válassza az **Importálás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7c87e-202">Select **Import**.</span></span>
1. <span data-ttu-id="7c87e-203">A **Közös eszköztár** részben válassza ki a **Commerce előzetes bemutató alapbővítmény** lehetőséget az eszközök listájából.</span><span class="sxs-lookup"><span data-stu-id="7c87e-203">Under **Shared asset library**, select **Commerce Preview Demo Base Extension** in the list of assets.</span></span>
1. <span data-ttu-id="7c87e-204">Válassza a **Kitárolás** elemet.</span><span class="sxs-lookup"><span data-stu-id="7c87e-204">Select **Pick**.</span></span> <span data-ttu-id="7c87e-205">A program visszairányítja az Eszköztárba, és a listában megjelenik a bővítmény.</span><span class="sxs-lookup"><span data-stu-id="7c87e-205">You're returned to the Asset library, and you should see the extension in the list.</span></span>

<span data-ttu-id="7c87e-206">A kötkező ábrán az LCS **Eszköztár** oldalán végrehajtandó műveleteket mutatja.</span><span class="sxs-lookup"><span data-stu-id="7c87e-206">The following illustration shows the actions that must be taken on the LCS **Asset library** page.</span></span>

![A Commerce előzetes bemutató alapbővítményének importálása](./media/import.png)

### <a name="deploy-the-environment"></a><span data-ttu-id="7c87e-208">Környezet telepítése</span><span class="sxs-lookup"><span data-stu-id="7c87e-208">Deploy the environment</span></span>

<span data-ttu-id="7c87e-209">Tegye a következőket a környezet telepítéséhez.</span><span class="sxs-lookup"><span data-stu-id="7c87e-209">To deploy the environment, follow these steps.</span></span>

> [!NOTE]
> <span data-ttu-id="7c87e-210">Előfordulhat, hogy nem kell a 6., 7. és/vagy 8. lépést végrehajtania, mert az egyetlen lehetőséggel rendekező oldalakat a rendszer átugorja.</span><span class="sxs-lookup"><span data-stu-id="7c87e-210">You might not have to complete steps 6, 7, and/or 8, because pages that have a single option are skipped.</span></span> <span data-ttu-id="7c87e-211">Amikor a **Környezeti paraméterek** nézetben van, erősítse meg, hogy a **Dynamics 365 Commerce – bemutató (10.0.* x* a Platform update *xx* frissítéssel)\*\* szöveg közvetlenül a **Környezet neve** mező felett jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="7c87e-211">When you're in the **Environment parameters** view, confirm that the text **Dynamics 365 Commerce - Demo (10.0.* x* with Platform update *xx*)\*\* appears directly above the **Environment name** field.</span></span> <span data-ttu-id="7c87e-212">További részletekért lásd a 8. lépés után megjelenő ábrát.</span><span class="sxs-lookup"><span data-stu-id="7c87e-212">For details, see the illustration that appears after step 8.</span></span>

1. <span data-ttu-id="7c87e-213">Válassza a felső menü **Felhőalapú környezetek**pontját.</span><span class="sxs-lookup"><span data-stu-id="7c87e-213">On the top menu, select **Cloud-hosted environments**.</span></span>
1. <span data-ttu-id="7c87e-214">Környezet hozzáadásához kattintson a **+ hozzáadás** gombra.</span><span class="sxs-lookup"><span data-stu-id="7c87e-214">Select **Add** to add an environment.</span></span>
1. <span data-ttu-id="7c87e-215">Válassza ki az **Alkalmazás verziószáma** mezőben a legfrissebb verziót.</span><span class="sxs-lookup"><span data-stu-id="7c87e-215">In the **Application version** field, select the most current version.</span></span> <span data-ttu-id="7c87e-216">Ha a legfrissebb verziótól különböző verziót kell kijelölni, akkor ne válasszon **10.0.8** előtti verziót.</span><span class="sxs-lookup"><span data-stu-id="7c87e-216">If you have a specific need to select an application version other than the most current version, do not select a version prior to **10.0.8**.</span></span>
1. <span data-ttu-id="7c87e-217">A **Platform verziószáma** mezőben használja a kiválasztott alkalmazás verziójának automatikusan kiválasztott platform verzióját.</span><span class="sxs-lookup"><span data-stu-id="7c87e-217">In the **Platform version** field, use the platform version that is automatically chosen for the application version you selected.</span></span> 

    ![Válassza ki az alkalmazás- és a platformverziókat](./media/project1.png)

1. <span data-ttu-id="7c87e-219">Válassza ki **Következő** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7c87e-219">Select **Next**.</span></span>
1. <span data-ttu-id="7c87e-220">**Demó** kiválasztása környezeti topológiaként.</span><span class="sxs-lookup"><span data-stu-id="7c87e-220">Select **Demo** as the environment topology.</span></span>

    ![1. környezeti topológia kiválasztása](./media/project2.png)

1. <span data-ttu-id="7c87e-222">Válassza ki a **Dynamics 365 Commerce – bemutatót** környezeti topológiaként.</span><span class="sxs-lookup"><span data-stu-id="7c87e-222">Select **Dynamics 365 Commerce - Demo** as the environment topology.</span></span> <span data-ttu-id="7c87e-223">Ha korábban egyetlen Azure-csatlakozót állított be, akkor ez lesz a környezethez használva.</span><span class="sxs-lookup"><span data-stu-id="7c87e-223">If you configured a single Azure Connector earlier, it will be used for this environment.</span></span> <span data-ttu-id="7c87e-224">Ha több Azure-összekötőt konfigurált, kiválaszthatja a használandó összekötőt: **Egyesült Államok keleti része**, **Egyesült Államok keleti része 2**, **Egyesült Államok nyugati része** vagy **Egyesült Államok nyugati része 2**.</span><span class="sxs-lookup"><span data-stu-id="7c87e-224">If you configured multiple Azure Connectors, you can select which connector to use: **East US**, **East US 2**, **West US**, or **West US 2**.</span></span> <span data-ttu-id="7c87e-225">(A legjobb végpontok közötti teljesítmény esetén ajánlott az **Egyesült Államok nyugati része 2**kiválasztása.)</span><span class="sxs-lookup"><span data-stu-id="7c87e-225">(For the best end-to-end performance, we recommend that you select **West US 2**.)</span></span>

    ![2. környezeti topológia kiválasztása](./media/project3.png)

1. <span data-ttu-id="7c87e-227">A **Környezet telepítése** oldalán adja meg a környezet nevét.</span><span class="sxs-lookup"><span data-stu-id="7c87e-227">On the **Deploy environment** page, enter an environment name.</span></span> <span data-ttu-id="7c87e-228">A Speciális beállításokat ne módosítsa.</span><span class="sxs-lookup"><span data-stu-id="7c87e-228">Leave the advanced settings as they are.</span></span>

    ![Környezet telepítése oldal](./media/project4.png)

1. <span data-ttu-id="7c87e-230">Szükség szerint állítsa be a virtuális gép méretét.</span><span class="sxs-lookup"><span data-stu-id="7c87e-230">Adjust the VM size as required.</span></span> <span data-ttu-id="7c87e-231">(A következő virtuálisgép-raktározási egységet javasoljuk: \[SKU\] **D13 v2**.)</span><span class="sxs-lookup"><span data-stu-id="7c87e-231">(We recommend VM stock keeping unit \[SKU\] **D13 v2**.)</span></span>
1. <span data-ttu-id="7c87e-232">Tekintse át az árképzési és licencelési feltételeket, majd jelölje be a jelölőnégyzetet annak jelzésére, hogy elfogadja azokat.</span><span class="sxs-lookup"><span data-stu-id="7c87e-232">Review the pricing and licensing terms, and then select the check box to indicate that you agree to them.</span></span>
1. <span data-ttu-id="7c87e-233">Válassza ki **Következő** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7c87e-233">Select **Next**.</span></span>
1. <span data-ttu-id="7c87e-234">A telepítési visszaigazolás oldalán győződjön meg róla, hogy az adatok helyesek, majd kattintson a **Telepítés** gombra.</span><span class="sxs-lookup"><span data-stu-id="7c87e-234">On the deployment confirmation page, verify that the details are correct, and then select **Deploy**.</span></span> <span data-ttu-id="7c87e-235">Vissza fog térni a **Felhőalapú környezetek** nézethez, és a környezetnek meg kell jelennie a listán.</span><span class="sxs-lookup"><span data-stu-id="7c87e-235">You're returned to the **Cloud-hosted environments** view, and your environment should appear in the list.</span></span>

    <span data-ttu-id="7c87e-236">A kért környezet várólistán jelenik meg, majd telepíthető.</span><span class="sxs-lookup"><span data-stu-id="7c87e-236">Your requested environment will appear as queued and then deploying.</span></span> <span data-ttu-id="7c87e-237">A környezeti munkafolyamatok némi időt fognak igénybe venni.</span><span class="sxs-lookup"><span data-stu-id="7c87e-237">The environment workflows will take some time to be completed.</span></span> <span data-ttu-id="7c87e-238">Ezért nézzen vissza körülbelül 6–9 óra múlva.</span><span class="sxs-lookup"><span data-stu-id="7c87e-238">Therefore, check back after approximately six to nine hours.</span></span>

1. <span data-ttu-id="7c87e-239">A folytatás előtt győződjön meg arról, hogy a környezet állapota **Telepített**.</span><span class="sxs-lookup"><span data-stu-id="7c87e-239">Before you continue, make sure that the status of your environment is **Deployed**.</span></span>

### <a name="initialize-the-commerce-scale-unit-cloud"></a><span data-ttu-id="7c87e-240">A Commerce Scale Unit (felhő) inicializálása</span><span class="sxs-lookup"><span data-stu-id="7c87e-240">Initialize the Commerce Scale Unit (cloud)</span></span>

<span data-ttu-id="7c87e-241">Egy CSU-cím inicializálásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="7c87e-241">To initialize CSU, follow these steps.</span></span>

1. <span data-ttu-id="7c87e-242">A **felhőalapú környezetek** nézetben válassza ki a saját környezetét a listából.</span><span class="sxs-lookup"><span data-stu-id="7c87e-242">In the **Cloud-hosted environments** view, select your environment in the list.</span></span>
1. <span data-ttu-id="7c87e-243">Kattintson a jobb oldalon található környezeti nézet **Minden részlet** elemére.</span><span class="sxs-lookup"><span data-stu-id="7c87e-243">In the environment view on the right, select **Full details**.</span></span> <span data-ttu-id="7c87e-244">Megjelenik a környezeti részletek nézet.</span><span class="sxs-lookup"><span data-stu-id="7c87e-244">The environment details view appears.</span></span>
1. <span data-ttu-id="7c87e-245">A **Környezeti funkciók**területen kattintson a**Kezelés** elemre.</span><span class="sxs-lookup"><span data-stu-id="7c87e-245">Under **Environment features**, select **Manage**.</span></span>
1. <span data-ttu-id="7c87e-246">A **Commerce** lapon válassza az **Inicializálás** parancsot.</span><span class="sxs-lookup"><span data-stu-id="7c87e-246">On the **Commerce** tab, select **Initialize**.</span></span> <span data-ttu-id="7c87e-247">Megjelenik a CSU inicializálási paraméterei nézet.</span><span class="sxs-lookup"><span data-stu-id="7c87e-247">The CSU initialization parameters view appears.</span></span>
1. <span data-ttu-id="7c87e-248">A **Régió** mezőben válassza az **Egyesült Államok keleti része**, **Egyesült Államok keleti része 2**, **Egyesült Államok nyugati része** vagy **Egyesült Államok nyugati része 2** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7c87e-248">In the **Region** field, select **East US**, **East US 2**, **West US**, or **West US 2**.</span></span>
1. <span data-ttu-id="7c87e-249">A **Verzió** mezőben válassza a **Verzió megadása** lehetőséget a listából, majd a megjelenő mezőben adja meg: **9.18.20014.4**.</span><span class="sxs-lookup"><span data-stu-id="7c87e-249">In the **Version** field, select **Specify a version** in the list, and then specify **9.18.20014.4** in the field that appears.</span></span> <span data-ttu-id="7c87e-250">Ügyeljen arra, hogy pontosan adja meg az itt jelzett verziószámot.</span><span class="sxs-lookup"><span data-stu-id="7c87e-250">Be sure to specify the exact version that is indicated here.</span></span> <span data-ttu-id="7c87e-251">Ellenkező esetben később frissítenie kell a RCSU programot a megfelelő verzióra.</span><span class="sxs-lookup"><span data-stu-id="7c87e-251">Otherwise, you will have to update RCSU to the correct version later.</span></span>
1. <span data-ttu-id="7c87e-252">Kapcsolja be a **bővítmény alkalmazása** beállítást.</span><span class="sxs-lookup"><span data-stu-id="7c87e-252">Turn on the **Apply extension** option.</span></span>
1. <span data-ttu-id="7c87e-253">A bővítmények listájából válassza a **Commerce előzetes demó alapbővítmény** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7c87e-253">In the list of extensions, select **Commerce Preview Demo Base Extension**.</span></span>
1. <span data-ttu-id="7c87e-254">Válassza az **Inicializálás** elemet.</span><span class="sxs-lookup"><span data-stu-id="7c87e-254">Select **Initialize**.</span></span>
1. <span data-ttu-id="7c87e-255">A telepítési visszaigazolás oldalán győződjön meg róla, hogy az adatok helyesek, majd kattintson az **Igen** gombra.</span><span class="sxs-lookup"><span data-stu-id="7c87e-255">On the deployment confirmation page, verify that the details are correct, and then select **Yes**.</span></span> <span data-ttu-id="7c87e-256">Újra megjelenik a **Commerce Management** nézet, amelyen a **Commerce** lap ki van választva.</span><span class="sxs-lookup"><span data-stu-id="7c87e-256">The **Commerce management** view displays again, where the **Commerce** tab is selected.</span></span> <span data-ttu-id="7c87e-257">A CSU várólistára került a létesítéshez.</span><span class="sxs-lookup"><span data-stu-id="7c87e-257">Your CSU has been queued for provisioning.</span></span>
1. <span data-ttu-id="7c87e-258">A folytatás előtt győződjön meg arról, hogy az CSU állapota **Sikeres**.</span><span class="sxs-lookup"><span data-stu-id="7c87e-258">Before you continue, make sure that the status of your CSU is **Success**.</span></span> <span data-ttu-id="7c87e-259">Az inicializálás körülbelül két-öt órát vesz igénybe.</span><span class="sxs-lookup"><span data-stu-id="7c87e-259">Initialization takes approximately two to five hours.</span></span>

### <a name="initialize-e-commerce"></a><span data-ttu-id="7c87e-260">Az elektronikus kereskedelem inicializálása</span><span class="sxs-lookup"><span data-stu-id="7c87e-260">Initialize e-Commerce</span></span>

<span data-ttu-id="7c87e-261">Az e-kereskedelem inicializálásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="7c87e-261">To initialize e-Commerce, follow these steps.</span></span>

1. <span data-ttu-id="7c87e-262">Az **e-kereskedelem** lapon tekintse át az előzetes jóváhagyását, majd válassza a **Beállítás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7c87e-262">On the **e-Commerce** tab, review the preview consent, and then select **Setup**.</span></span>
1. <span data-ttu-id="7c87e-263">Az **E-kereskedelmi bérlő neve** mezőben adjon meg egy nevet.</span><span class="sxs-lookup"><span data-stu-id="7c87e-263">In the **e-Commerce tenant name** field, enter a name.</span></span> <span data-ttu-id="7c87e-264">Azonban fontos megjegyezni, hogy ez a név az e-kereskedelem példányra mutató néhány URL-címen látható lesz.</span><span class="sxs-lookup"><span data-stu-id="7c87e-264">However, be aware that this name will appear in some of the URLs that point to your e-Commerce instance.</span></span>
1. <span data-ttu-id="7c87e-265">A **Commerce Scale Unit neve** mezőben válassza ki az CSU-t a listából.</span><span class="sxs-lookup"><span data-stu-id="7c87e-265">In the **Commerce Scale Unit name** field, select your CSU in the list.</span></span> <span data-ttu-id="7c87e-266">(A listában csak egy opciónak kell lennie.)</span><span class="sxs-lookup"><span data-stu-id="7c87e-266">(The list should have only one option.)</span></span>

    <span data-ttu-id="7c87e-267">Az **E-kereskedelmi földrajz** mező beállítása automatikus, az érték pedig nem módosítható.</span><span class="sxs-lookup"><span data-stu-id="7c87e-267">The **e-Commerce geography** field is set automatically, and the value can't be changed.</span></span>

1. <span data-ttu-id="7c87e-268">A folytatáshoz kattintson a **Tovább** gombra.</span><span class="sxs-lookup"><span data-stu-id="7c87e-268">Select **Next** to continue.</span></span>
1. <span data-ttu-id="7c87e-269">A **Támogatott állomásnevek** mezőbe írjon be egy tetszőleges érvényes tartományt, például `www.fabrikam.com`.</span><span class="sxs-lookup"><span data-stu-id="7c87e-269">In the **Supported host names** field, enter any valid domain, such as `www.fabrikam.com`.</span></span>
1.  <span data-ttu-id="7c87e-270">Az **AAD biztonsági csoport rendszergazdának** mezőben adja meg a használni kívánt biztonsági csoport első néhány betűjét.</span><span class="sxs-lookup"><span data-stu-id="7c87e-270">In the **AAD security group for system admin** field, enter the first few letters of the name of the security group that you want to use.</span></span> <span data-ttu-id="7c87e-271">A keresési eredmények megjelenítéséhez válassza a nagyítóosztály ikonját.</span><span class="sxs-lookup"><span data-stu-id="7c87e-271">Select the magnifying class icon to display the search results.</span></span> <span data-ttu-id="7c87e-272">Válasszon ki egy megfelelő biztonsági csoportot a listából.</span><span class="sxs-lookup"><span data-stu-id="7c87e-272">Select the correct security group from the list.</span></span>
2.  <span data-ttu-id="7c87e-273">Az **AAD biztonsági csoport minősítési és értékelési moderátornak** mezőben adja meg a használni kívánt biztonsági csoport első néhány betűjét.</span><span class="sxs-lookup"><span data-stu-id="7c87e-273">In the **AAD security group for ratings and review moderator** field, enter the first few letters of the name of the security group that you want to use.</span></span> <span data-ttu-id="7c87e-274">A keresési eredmények megjelenítéséhez válassza a nagyítóosztály ikonját.</span><span class="sxs-lookup"><span data-stu-id="7c87e-274">Select the magnifying class icon to display the search results.</span></span> <span data-ttu-id="7c87e-275">Válasszon ki egy megfelelő biztonsági csoportot a listából.</span><span class="sxs-lookup"><span data-stu-id="7c87e-275">Select the correct security group from the list.</span></span>
1. <span data-ttu-id="7c87e-276">Az **Értékelések és vélemények szolgáltatás engedélyezése** értékét hagyja bekapcsolva.</span><span class="sxs-lookup"><span data-stu-id="7c87e-276">Leave the **Enable ratings and review service** option turned on.</span></span>
1. <span data-ttu-id="7c87e-277">Válassza az **Inicializálás** elemet.</span><span class="sxs-lookup"><span data-stu-id="7c87e-277">Select **Initialize**.</span></span> <span data-ttu-id="7c87e-278">Újra megjelenik a **Commerce Management** nézet, amelyen a **e-kereskedelem** lap ki van választva.</span><span class="sxs-lookup"><span data-stu-id="7c87e-278">The **Commerce management** view displays again, where the **e-Commerce** tab is selected.</span></span> <span data-ttu-id="7c87e-279">Az e-kereskedelem inicializálása elindult.</span><span class="sxs-lookup"><span data-stu-id="7c87e-279">E-Commerce initialization has started.</span></span>
1. <span data-ttu-id="7c87e-280">A folytatás előtt várja meg, amíg az e-kereskedelem inicializálási állapota **Az inicializálás sikerült**állapotra nem vált.</span><span class="sxs-lookup"><span data-stu-id="7c87e-280">Before you continue, wait until the status of e-Commerce initialization is **Initialization successful**.</span></span>
1. <span data-ttu-id="7c87e-281">A jobb alsó sarokban található **Hivatkozások** részben jegyezze fel a következő hivatkozások URL-címeit:</span><span class="sxs-lookup"><span data-stu-id="7c87e-281">Under **Links** in the lower right, make a note of the URLs for the following links:</span></span>

    * <span data-ttu-id="7c87e-282">**e-kereskedelmi webhely** -Az e-kereskedelmi webhely gyökerére mutató hivatkozás.</span><span class="sxs-lookup"><span data-stu-id="7c87e-282">**e-Commerce site** – The link to the root of your e-Commerce site.</span></span>
    * <span data-ttu-id="7c87e-283">**e-kereskedelmi webhelykezelési eszköz** - A webhelykezelési eszközre mutató eszköz.</span><span class="sxs-lookup"><span data-stu-id="7c87e-283">**e-Commerce site management tool** – The link to the site management tool.</span></span>

## <a name="commerce-preview-environment-support"></a><span data-ttu-id="7c87e-284">Commerce előzetes verziós környezet támogatása</span><span class="sxs-lookup"><span data-stu-id="7c87e-284">Commerce preview environment support</span></span>

<span data-ttu-id="7c87e-285">Ha problémák merülnek fel a létesítés lépéseinek végrehajtása közben, akkor kérjen segítséget [a Microsoft Dynamics 365 Commerce előzetes Yammer-csoportjában](https://aka.ms/Dynamics365CommercePreviewYammer).</span><span class="sxs-lookup"><span data-stu-id="7c87e-285">If you experience issues while you're completing the provisioning steps, visit the [Microsoft Dynamics 365 Commerce Preview Yammer group](https://aka.ms/Dynamics365CommercePreviewYammer) for help.</span></span>

## <a name="next-steps"></a><span data-ttu-id="7c87e-286">További lépések</span><span class="sxs-lookup"><span data-stu-id="7c87e-286">Next steps</span></span>

<span data-ttu-id="7c87e-287">A Kereskedelem előzetes környezetének létesítési és konfigurálási folyamatának folytatásához lásd: [Kereskedelem előzetes környezetének konfigurálása](cpe-post-provisioning.md).</span><span class="sxs-lookup"><span data-stu-id="7c87e-287">To continue the process of provisioning and configuring your Commerce preview environment, see [Configure a Commerce preview environment](cpe-post-provisioning.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="7c87e-288">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="7c87e-288">Additional resources</span></span>

[<span data-ttu-id="7c87e-289">Dynamics 365 Commerce előzetes verziós környezet áttekintése</span><span class="sxs-lookup"><span data-stu-id="7c87e-289">Dynamics 365 Commerce preview environment overview</span></span>](cpe-overview.md)

[<span data-ttu-id="7c87e-290">Dynamics 365 Commerce előzetes verziós környezet konfigurálása</span><span class="sxs-lookup"><span data-stu-id="7c87e-290">Configure a Dynamics 365 Commerce preview environment</span></span>](cpe-post-provisioning.md)

[<span data-ttu-id="7c87e-291">A Dynamics 365 Commerce előzetes verziós környezet választható funkcióinak konfigurálása</span><span class="sxs-lookup"><span data-stu-id="7c87e-291">Configure optional features for a Dynamics 365 Commerce preview environment</span></span>](cpe-optional-features.md)

[<span data-ttu-id="7c87e-292">Dynamics 365 Commerce előzetes verziós környezet GYIK</span><span class="sxs-lookup"><span data-stu-id="7c87e-292">Dynamics 365 Commerce preview environment FAQ</span></span>](cpe-faq.md)

[<span data-ttu-id="7c87e-293">Microsoft Lifecycle Services (LCS)</span><span class="sxs-lookup"><span data-stu-id="7c87e-293">Microsoft Lifecycle Services (LCS)</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[<span data-ttu-id="7c87e-294">Commerce Scale Unit (felhő)</span><span class="sxs-lookup"><span data-stu-id="7c87e-294">Commerce Scale Unit (cloud)</span></span>](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[<span data-ttu-id="7c87e-295">Microsoft Azure-portál</span><span class="sxs-lookup"><span data-stu-id="7c87e-295">Microsoft Azure portal</span></span>](https://azure.microsoft.com/features/azure-portal)

[<span data-ttu-id="7c87e-296">Dynamics 365 Commerce-webhely</span><span class="sxs-lookup"><span data-stu-id="7c87e-296">Dynamics 365 Commerce website</span></span>](https://aka.ms/Dynamics365CommerceWebsite)

