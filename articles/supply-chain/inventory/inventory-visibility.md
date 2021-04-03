---
title: Készlet láthatósága bővítmény
description: Ez a témakör a Készlet láthatósága bővítmény telepítését és konfigurálását ismerteti a Dynamics 365 Supply Chain Management rendszerhez.
author: sherry-zheng
manager: tfehr
ms.date: 10/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-10-26
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 4e588be2ac5aae395ca66e3c9a743a67d71db7c0
ms.sourcegitcommit: a3052f76ad71894dbef66566c07c6e2c31505870
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/10/2021
ms.locfileid: "5574222"
---
# <a name="inventory-visibility-add-in"></a><span data-ttu-id="42471-103">Készlet láthatósága bővítmény</span><span class="sxs-lookup"><span data-stu-id="42471-103">Inventory Visibility Add-in</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]
[!INCLUDE [cc-data-platform-banner](../../includes/cc-data-platform-banner.md)]

<span data-ttu-id="42471-104">A Készlet láthatósága bővítmény egy független és jól méretezhető mikroszolgáltatás, amely lehetővé teszi a valós idejű aktuális készletkövetést, így globális képet nyújt a készlet láthatóságáról.</span><span class="sxs-lookup"><span data-stu-id="42471-104">The Inventory Visibility Add-in is an independent and highly scalable microservice that enables real-time on-hand inventory tracking, thus providing a global view of inventory visibility.</span></span>

<span data-ttu-id="42471-105">Az aktuális készlethez kapcsolódó összes információt a rendszer közel valós időben exportálja a szolgáltatásba alacsony szintű SQL-integráció révén.</span><span class="sxs-lookup"><span data-stu-id="42471-105">All information that relates to on-hand inventory is exported to the service in near real-time through low-level SQL integration.</span></span> <span data-ttu-id="42471-106">A külső rendszerek RESTful API-kon keresztül érik el a szolgáltatást, hogy aktuális információkat kérdezzenek le adott dimenziókészletekről, így lekérve a rendelkezésre álló aktuális pozíciók listáját.</span><span class="sxs-lookup"><span data-stu-id="42471-106">External systems access the service through RESTful APIs to query on-hand information on given sets of dimensions, thus retrieving a list of available on-hand positions.</span></span>

<span data-ttu-id="42471-107">A Készlet láthatósága egy mikroszolgáltatás, amely a Microsoft Dataverse rendszerre épül, ami azt jelenti, hogy bővítheti Power Apps alkalmazások készítésével és Power BI alkalmazásával, hogy személyre szabott funkciókat biztosítson, amelyek megfelelnek az üzleti követelményeknek.</span><span class="sxs-lookup"><span data-stu-id="42471-107">Inventory Visibility is a microservice built on Microsoft Dataverse, which means you can extend it by building Power Apps and applying Power BI to provide customized functionality to meet your business requirements.</span></span> <span data-ttu-id="42471-108">Lehetőség van az index frissítésére is a készletlekérdezésekhez.</span><span class="sxs-lookup"><span data-stu-id="42471-108">It is also possible to upgrade the index to do inventory queries.</span></span>

<span data-ttu-id="42471-109">A Készlet láthatósága olyan konfigurációs beállításokat biztosít, amelyek lehetővé teszik, hogy több külső gyártótól származó rendszerrel integrálódjon.</span><span class="sxs-lookup"><span data-stu-id="42471-109">Inventory Visibility provides configuration options that let it integrate with multiple third-party systems.</span></span> <span data-ttu-id="42471-110">Támogatja a szabványosított készletdimenziót, a testreszabott bővíthetőséget és a szabványosított, konfigurálható számított mennyiségeket.</span><span class="sxs-lookup"><span data-stu-id="42471-110">It supports the standardized inventory dimension, customized extensibility, and standardized, configurable calculated quantities.</span></span>

<span data-ttu-id="42471-111">Ez a témakör azt ismerteti, hogyan telepítheti és konfigurálhatja az Készlet láthatósága bővítményt a Dynamics 365 Supply Chain Management rendszerhez, és hogyan használhatja az alkalmazásprogramozási felületét (API).</span><span class="sxs-lookup"><span data-stu-id="42471-111">This topic describes how to install and configure the Inventory Visibility Add-in for Dynamics 365 Supply Chain Management, and how to use its application programming interface (API).</span></span>

## <a name="install-the-inventory-visibility-add-in"></a><span data-ttu-id="42471-112">A Készlet láthatósága bővítmény telepítése</span><span class="sxs-lookup"><span data-stu-id="42471-112">Install the Inventory Visibility Add-in</span></span>

<span data-ttu-id="42471-113">Telepítenie kell a Készlet láthatósága bővítményt a Microsoft Dynamics Lifecycle Services (LCS) használatával.</span><span class="sxs-lookup"><span data-stu-id="42471-113">You need to install the Inventory Visibility Add-in using Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="42471-114">Az LCS egy együttműködési portál, amely egy környezetet és rendszeresen frissített szolgáltatások készletét biztosítja, amelyek segítenek a Dynamics 365 Finance and Operations-alkalmazások alkalmazás-életciklusának kezelésében.</span><span class="sxs-lookup"><span data-stu-id="42471-114">LCS is a collaboration portal that provides an environment and a set of regularly updated services that help you manage the application lifecycle of your Dynamics 365 Finance and Operations apps.</span></span>

<span data-ttu-id="42471-115">További tudnivalókért lásd: [Lifecycle Services-erőforrások](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/lcs).</span><span class="sxs-lookup"><span data-stu-id="42471-115">For more information, see [Lifecycle Services resources](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/lcs).</span></span>

### <a name="prerequisites"></a><span data-ttu-id="42471-116">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="42471-116">Prerequisites</span></span>

<span data-ttu-id="42471-117">A Készlet láthatósága bővítmény telepítése előtt a következőket kell tennie:</span><span class="sxs-lookup"><span data-stu-id="42471-117">Before you install the Inventory Visibility Add-in, you must do the following:</span></span>

- <span data-ttu-id="42471-118">Szerezzen be egy LCS-megvalósítási projektet legalább egy üzembe helyezett környezettel.</span><span class="sxs-lookup"><span data-stu-id="42471-118">Obtain an LCS implementation project with at least one environment deployed.</span></span>
- <span data-ttu-id="42471-119">Győződjön meg arról, hogy be vannak fejezve a [Bővítmények áttekintése](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md) részben megadott bővítmények beállításának előfeltételei.</span><span class="sxs-lookup"><span data-stu-id="42471-119">Make sure that the prerequisites for setting up add-ins provided in the [Add-ins overview](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md) have been completed.</span></span> <span data-ttu-id="42471-120">A Készlet láthatósága nem igényel kettős írású csatolást.</span><span class="sxs-lookup"><span data-stu-id="42471-120">Inventory Visibility doesn't require dual-write linking.</span></span>
- <span data-ttu-id="42471-121">Lépjen kapcsolatba a Készlet láthatósági csapatával [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) a következő három szükséges fájl beszerzéséhez:</span><span class="sxs-lookup"><span data-stu-id="42471-121">Contact the Inventory Visibility Team at [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) to get the following three required files:</span></span>

    - `Inventory Visibility Dataverse Solution.zip`
    - `Inventory Visibility Configuration Trigger.zip`
    - <span data-ttu-id="42471-122">`Inventory Visibility Integration.zip` (ha a Supply Chain Management által futtatott verzió korábbi, mint a 10.0.18)</span><span class="sxs-lookup"><span data-stu-id="42471-122">`Inventory Visibility Integration.zip` (if the version of Supply Chain Management that you're running is earlier than version 10.0.18)</span></span>

> [!NOTE]
> <span data-ttu-id="42471-123">A jelenleg támogatott országok és régiók: Kanada, az Egyesült Államok és az Európai Unió (EU).</span><span class="sxs-lookup"><span data-stu-id="42471-123">The currently supported countries and regions include Canada, the United States, and the European Union (EU).</span></span>

<span data-ttu-id="42471-124">Ha bármilyen kérdése van ezekkel az előfeltételekkel kapcsolatban, kérjük, forduljon a Készlet láthatósága termékcsapatához.</span><span class="sxs-lookup"><span data-stu-id="42471-124">If you have any questions about these prerequisites, please contact the Inventory Visibility product team.</span></span>

### <a name="set-up-dataverse"></a><a name="setup-microsoft-dataverse"></a><span data-ttu-id="42471-125">Dataverse beállítása</span><span class="sxs-lookup"><span data-stu-id="42471-125">Set up Dataverse</span></span>

<span data-ttu-id="42471-126">A Dataverse beállításához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="42471-126">Follow these steps to set up Dataverse.</span></span>

1. <span data-ttu-id="42471-127">Adjon hozzá egy szolgáltatási elvet a bérlőhöz:</span><span class="sxs-lookup"><span data-stu-id="42471-127">Add a service principle to your tenant:</span></span>

    1. <span data-ttu-id="42471-128">Telepítse az Azure AD PowerShell modul v2 verzióját az [Azure Active Directory PowerShell for Graph telepítése](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) részben leírtak szerint.</span><span class="sxs-lookup"><span data-stu-id="42471-128">Install Azure AD PowerShell Module v2 as described in [Install Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span></span>
    1. <span data-ttu-id="42471-129">Futtassa a következő PowerShell-parancsot.</span><span class="sxs-lookup"><span data-stu-id="42471-129">Run the following PowerShell command.</span></span>

        ```powershell
        Connect-AzureAD # (open a sign in window and sign in as a tenant user)

        New-AzureADServicePrincipal -AppId "3022308a-b9bd-4a18-b8ac-2ddedb2075e1" -DisplayName "d365-scm-inventoryservice"
        ```

1. <span data-ttu-id="42471-130">Hozzon létre egy alkalmazásfelhasználót a Készlet láthatósága számára a Dataverse rendszerben:</span><span class="sxs-lookup"><span data-stu-id="42471-130">Create an application user for Inventory Visibility in Dataverse:</span></span>

    1. <span data-ttu-id="42471-131">Nyissa meg a Dataverse környezete URL-címét.</span><span class="sxs-lookup"><span data-stu-id="42471-131">Open the URL of your Dataverse environment.</span></span>
    1. <span data-ttu-id="42471-132">Lépjen a **Speciális beállítások \> Rendszer \> Biztonság \> Felhasználók** lehetőségre, és hozzon létre egy alkalmazásfelhasználót.</span><span class="sxs-lookup"><span data-stu-id="42471-132">Go to **Advanced Setting \> System \> Security \> Users**, and create an application user.</span></span> <span data-ttu-id="42471-133">A nézet menü használatával módosítsa az oldal nézetét az **Alkalmazásfelhasználók** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="42471-133">Use the view menu to change the page view to **Application Users**.</span></span>
    1. <span data-ttu-id="42471-134">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="42471-134">Select **New**.</span></span> <span data-ttu-id="42471-135">Állítsa az alkalmazásazonosítót a *3022308a-b9bd-4a18-b8ac-2ddedb2075e1* értékre.</span><span class="sxs-lookup"><span data-stu-id="42471-135">Set the application ID to *3022308a-b9bd-4a18-b8ac-2ddedb2075e1*.</span></span> <span data-ttu-id="42471-136">(Az objektumazonosító azonnal betöltődik, amint menti a módosításokat.) A nevet testreszabhatja.</span><span class="sxs-lookup"><span data-stu-id="42471-136">(The object ID will automatically be loaded when you save your changes.) You can customize the name.</span></span> <span data-ttu-id="42471-137">Például a *Készlet láthatósága* értékre módosíthatja.</span><span class="sxs-lookup"><span data-stu-id="42471-137">For example, you can change it to *Inventory Visibility*.</span></span> <span data-ttu-id="42471-138">Amikor elkészült, válassza a **Mentés** elemet.</span><span class="sxs-lookup"><span data-stu-id="42471-138">When you've finished, select **Save**.</span></span>
    1. <span data-ttu-id="42471-139">Válassza a **Szerepkör hozzárendelése**, majd a **Rendszergazda** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="42471-139">Select **Assign Role**, and then select **System Administrator**.</span></span> <span data-ttu-id="42471-140">Ha van **Common Data Service-felhasználó** nevű szerepkör, válassza ki azt is.</span><span class="sxs-lookup"><span data-stu-id="42471-140">If there is a role that is named **Common Data Service User**, select it too.</span></span>

    <span data-ttu-id="42471-141">További tudnivalókért lásd: [Alkalmazásfelhasználó létrehozása](https://docs.microsoft.com/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user).</span><span class="sxs-lookup"><span data-stu-id="42471-141">For more information, see [Create an application user](https://docs.microsoft.com/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user).</span></span>

1. <span data-ttu-id="42471-142">Importálja az `Inventory Visibility Dataverse Solution.zip` fájlt, amely a Dataverse-konfigurációhoz kapcsolódó entitásokat és Power Apps-alkalmazásokat tartalmazza:</span><span class="sxs-lookup"><span data-stu-id="42471-142">Import the `Inventory Visibility Dataverse Solution.zip` file, which includes Dataverse configuration related entities and Power Apps:</span></span>

    1. <span data-ttu-id="42471-143">Lépjen a **Megoldások** oldalra.</span><span class="sxs-lookup"><span data-stu-id="42471-143">Go to the **Solutions** page.</span></span>
    1. <span data-ttu-id="42471-144">Válassza az **Importálás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="42471-144">Select **Import**.</span></span>

1. <span data-ttu-id="42471-145">A konfigurációfrissítés indító folyamatának importálása:</span><span class="sxs-lookup"><span data-stu-id="42471-145">Import the configuration upgrade trigger flow:</span></span>

    1. <span data-ttu-id="42471-146">Lépjen a Microsoft Flow oldalra.</span><span class="sxs-lookup"><span data-stu-id="42471-146">Go to the Microsoft Flow page.</span></span>
    1. <span data-ttu-id="42471-147">Győződjön meg róla, hogy az elnevezett *Dataverse (örökölt)* kapcsolat létezik.</span><span class="sxs-lookup"><span data-stu-id="42471-147">Make sure that the connection that is named *Dataverse (legacy)* exists.</span></span> <span data-ttu-id="42471-148">(Ha nem létezik, hozza létre.)</span><span class="sxs-lookup"><span data-stu-id="42471-148">(If it doesn't exist, create it.)</span></span>
    1. <span data-ttu-id="42471-149">Importálja az `Inventory Visibility Configuration Trigger.zip` fájlt.</span><span class="sxs-lookup"><span data-stu-id="42471-149">Import the `Inventory Visibility Configuration Trigger.zip` file.</span></span> <span data-ttu-id="42471-150">Importálás után az eseményindító a **Saját folyamatok** alatt jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="42471-150">After it's imported, the trigger will appear under **My flows**.</span></span>
    1. <span data-ttu-id="42471-151">Inicializálja a következő négy változót a környezeti adatok alapján:</span><span class="sxs-lookup"><span data-stu-id="42471-151">Initialize the following four variables, based on the environment information:</span></span>

        - <span data-ttu-id="42471-152">Azure-bérlő azonosítója</span><span class="sxs-lookup"><span data-stu-id="42471-152">Azure Tenant ID</span></span>
        - <span data-ttu-id="42471-153">Azure-alkalmazásügyfél azonosítója</span><span class="sxs-lookup"><span data-stu-id="42471-153">Azure Application Client ID</span></span>
        - <span data-ttu-id="42471-154">Azure-alkalmazásügyfél titkos kódja</span><span class="sxs-lookup"><span data-stu-id="42471-154">Azure Application Client Secret</span></span>
        - <span data-ttu-id="42471-155">Készletláthatósági végpont</span><span class="sxs-lookup"><span data-stu-id="42471-155">Inventory Visibility Endpoint</span></span>

            <span data-ttu-id="42471-156">Erről a változóról a témakör későbbi, [A készlet láthatóságának beállítása](#setup-inventory-visibility-integration) című szakasza nyújt további tájékoztatást.</span><span class="sxs-lookup"><span data-stu-id="42471-156">For more information about this variable, see the [Set up Inventory Visibility integration](#setup-inventory-visibility-integration) section later in this topic.</span></span>

        <span data-ttu-id="42471-157">![Konfiguráció eseményindítója](media/configuration-trigger.png "Konfiguráció eseményindítója")</span><span class="sxs-lookup"><span data-stu-id="42471-157">![Configuration trigger](media/configuration-trigger.png "Configuration trigger")</span></span>

    1. <span data-ttu-id="42471-158">Válassza a **Bekapcsolás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="42471-158">Select **Turn on**.</span></span>

### <a name="install-the-add-in"></a><a name="install-add-in"></a><span data-ttu-id="42471-159">Telepítse a bővítményt</span><span class="sxs-lookup"><span data-stu-id="42471-159">Install the add-in</span></span>

<span data-ttu-id="42471-160">A Készlet láthatósága bővítmény telepítéséhez a következőket kell tennie:</span><span class="sxs-lookup"><span data-stu-id="42471-160">To install the Inventory Visibility Add-in, do the following:</span></span>

1. <span data-ttu-id="42471-161">Jelentkezzen be a [Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index) portálra.</span><span class="sxs-lookup"><span data-stu-id="42471-161">Sign in to the [Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index) portal.</span></span>
1. <span data-ttu-id="42471-162">A kezdőlapon válassza ki azt a projektet, amelyben a környezet telepítve van.</span><span class="sxs-lookup"><span data-stu-id="42471-162">On the home page, select the project where your environment is deployed.</span></span>
1. <span data-ttu-id="42471-163">A projekt oldalon jelölje ki azt a környezetet, amelyben telepíteni szeretné a bővítményt.</span><span class="sxs-lookup"><span data-stu-id="42471-163">On the project page, select the environment where you want to install the add-in.</span></span>
1. <span data-ttu-id="42471-164">A környezeti oldalon görgessen lefelé, amíg meg nem látja a **Környezeti bővítmények** szakaszt a **Power Platform-integráció** szakaszban, ahol a Dataverse-környezet neve található.</span><span class="sxs-lookup"><span data-stu-id="42471-164">On the environment page, scroll down until you see the **Environment add-ins** section in the **Power Platform integration** section, where you can find the Dataverse environment name.</span></span>
1. <span data-ttu-id="42471-165">A **Környezeti bővítmények** szakaszban válassza az **Új bővítmény telepítése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="42471-165">In the **Environment add-ins** section, select **Install a new add-in**.</span></span>

    <span data-ttu-id="42471-166">![A környezeti oldal az LCS-ben](media/inventory-visibility-environment.png "A környezeti oldal az LCS-ben")</span><span class="sxs-lookup"><span data-stu-id="42471-166">![The environment page in LCS](media/inventory-visibility-environment.png "The environment page in LCS")</span></span>

1. <span data-ttu-id="42471-167">Válassza az **Új bővítmény telepítése** hivatkozást.</span><span class="sxs-lookup"><span data-stu-id="42471-167">Select the **Install a new add-in** link.</span></span> <span data-ttu-id="42471-168">Megnyílik az elérhető bővítmények listája.</span><span class="sxs-lookup"><span data-stu-id="42471-168">A list of available add-ins opens.</span></span>
1. <span data-ttu-id="42471-169">A listában válassza a **Készletláthatóság** elemet.</span><span class="sxs-lookup"><span data-stu-id="42471-169">Select **Inventory Visibility** in the list.</span></span>
1. <span data-ttu-id="42471-170">Adja meg a környezet alábbi mezőinek értékeit:</span><span class="sxs-lookup"><span data-stu-id="42471-170">Enter values for the following fields for your environment:</span></span>

    - <span data-ttu-id="42471-171">**AAD-alkalmazás (ügyfél) azonosítója**</span><span class="sxs-lookup"><span data-stu-id="42471-171">**AAD application (client) ID**</span></span>
    - <span data-ttu-id="42471-172">**AAD bérlő azonosítója**</span><span class="sxs-lookup"><span data-stu-id="42471-172">**AAD tenant ID**</span></span>

    <span data-ttu-id="42471-173">![Hozzáadás a beállítási lapon](media/inventory-visibility-setup.png "Hozzáadás a beállítási lapon")</span><span class="sxs-lookup"><span data-stu-id="42471-173">![Add in setup page](media/inventory-visibility-setup.png "Add-in setup page")</span></span>

1. <span data-ttu-id="42471-174">Fogadja el a feltételeket az **Általános Szerződési feltételek** jelölőnégyzet bejelölésével.</span><span class="sxs-lookup"><span data-stu-id="42471-174">Agree to the terms and condition by selecting the **Terms and conditions** check box.</span></span>
1. <span data-ttu-id="42471-175">Válassza a **Telepítés** parancsot.</span><span class="sxs-lookup"><span data-stu-id="42471-175">Select **Install**.</span></span> <span data-ttu-id="42471-176">A bővítmény állapota **Telepítés** értékkel jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="42471-176">The status of the add-in will show as **Installing**.</span></span> <span data-ttu-id="42471-177">Ha befejeződött, frissítse a lapot, hogy lássa, ahogy a **Telepített** állapotra változik.</span><span class="sxs-lookup"><span data-stu-id="42471-177">When it's done, refresh the page to see the status change to **Installed**.</span></span>

### <a name="uninstall-the-add-in"></a><a name="uninstall-add-in"></a><span data-ttu-id="42471-178">A bővítmény eltávolítása</span><span class="sxs-lookup"><span data-stu-id="42471-178">Uninstall the add-in</span></span>

<span data-ttu-id="42471-179">A bővítmény eltávolításához válassza az **Eltávolítás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="42471-179">To uninstall the add-in, select **Uninstall**.</span></span> <span data-ttu-id="42471-180">Az LCS frissítésekor a Készlet láthatósága bővítmény törlődik.</span><span class="sxs-lookup"><span data-stu-id="42471-180">When you refresh LCS, the Inventory Visibility Add-in will be removed.</span></span> <span data-ttu-id="42471-181">Az eltávolítási folyamat eltávolítja a bővítmény regisztrációját, és elindít egy feladatot a szolgáltatásban tárolt összes üzleti adat törléséhez.</span><span class="sxs-lookup"><span data-stu-id="42471-181">The uninstall process removes the add-in registration and also starts a job to clean up all the business data that is stored in the service.</span></span>

## <a name="consume-on-hand-inventory-data-from-supply-chain-management"></a><span data-ttu-id="42471-182">Az aktuális készlet adatainak felhasználása a Supply Chain Management alkalmazásból</span><span class="sxs-lookup"><span data-stu-id="42471-182">Consume on-hand inventory data from Supply Chain Management</span></span>

### <a name="deploy-the-inventory-visibility-integration-package"></a><a name="deploy-inventory-visibility-package"></a><span data-ttu-id="42471-183">A Készlet láthatósága integrációs csomag központi telepítése</span><span class="sxs-lookup"><span data-stu-id="42471-183">Deploy the Inventory Visibility integration package</span></span>

<span data-ttu-id="42471-184">Ha a Supply Chain Management 10.0.17-es vagy korábbi verziója fut, a csomagfájl beszerzéséért forduljon a Készlet láthatósága támogatási csapathoz az [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) címen.</span><span class="sxs-lookup"><span data-stu-id="42471-184">If you're running Supply Chain Management version 10.0.17 or earlier, contact the Inventory Visibility on-board support team at [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) to get the package file.</span></span> <span data-ttu-id="42471-185">Ezután telepítse a csomagot az LCS-be.</span><span class="sxs-lookup"><span data-stu-id="42471-185">Then deploy the package in LCS.</span></span>

> [!NOTE]
> <span data-ttu-id="42471-186">Ha a telepítés során nem egyező verziók fordulnak elő, manuálisan kell importálnia az X++ projektet a fejlesztői környezetbe.</span><span class="sxs-lookup"><span data-stu-id="42471-186">If a version mismatch error occurs during deployment, you must manually import the X++ project into your development environment.</span></span> <span data-ttu-id="42471-187">Ezt követően hozza létre a telepíthető csomagot a fejlesztői környezetben, és telepítse az éles környezetben.</span><span class="sxs-lookup"><span data-stu-id="42471-187">Then create the deployable package in your development environment, and deploy it in your production environment.</span></span>
> 
> <span data-ttu-id="42471-188">A kód része a Supply Chain Management 10.0.18-as verziójának.</span><span class="sxs-lookup"><span data-stu-id="42471-188">The code is included with Supply Chain Management version 10.0.18.</span></span> <span data-ttu-id="42471-189">Ha azt a verziót vagy egy későbbi verziót futtat, nem szükséges a telepítés.</span><span class="sxs-lookup"><span data-stu-id="42471-189">If you're running that version or later, deployment isn't required.</span></span>

<span data-ttu-id="42471-190">Győződjön meg arról, hogy az alábbi funkciók be vannak kapcsolva a Supply Chain Management-környezetben.</span><span class="sxs-lookup"><span data-stu-id="42471-190">Make sure that the following features are turned on in your Supply Chain Management environment.</span></span> <span data-ttu-id="42471-191">(Alapértelmezés szerint be vannak kapcsolva.)</span><span class="sxs-lookup"><span data-stu-id="42471-191">(By default, they are turned on.)</span></span>

| <span data-ttu-id="42471-192">Funkció leírása</span><span class="sxs-lookup"><span data-stu-id="42471-192">Feature description</span></span> | <span data-ttu-id="42471-193">Kódverzió</span><span class="sxs-lookup"><span data-stu-id="42471-193">Code version</span></span> | <span data-ttu-id="42471-194">Osztály váltása</span><span class="sxs-lookup"><span data-stu-id="42471-194">Toggle class</span></span> |
|---|---|---|
| <span data-ttu-id="42471-195">Készletdimenziók használatának engedélyezése vagy letiltása az InventSum táblán</span><span class="sxs-lookup"><span data-stu-id="42471-195">Enable or disable using inventory dimensions on InventSum table</span></span> | <span data-ttu-id="42471-196">10.0.11</span><span class="sxs-lookup"><span data-stu-id="42471-196">10.0.11</span></span> | <span data-ttu-id="42471-197">InventUseDimOfInventSumToggle</span><span class="sxs-lookup"><span data-stu-id="42471-197">InventUseDimOfInventSumToggle</span></span> |
| <span data-ttu-id="42471-198">Készletdimenziók használatának engedélyezése vagy letiltása az InventSumDelta táblán</span><span class="sxs-lookup"><span data-stu-id="42471-198">Enable or disable using inventory dimensions on InventSumDelta table</span></span> | <span data-ttu-id="42471-199">10.0.12</span><span class="sxs-lookup"><span data-stu-id="42471-199">10.0.12</span></span> | <span data-ttu-id="42471-200">InventUseDimOfInventSumDeltaToggle</span><span class="sxs-lookup"><span data-stu-id="42471-200">InventUseDimOfInventSumDeltaToggle</span></span> |

### <a name="set-up-inventory-visibility-integration"></a><a name="setup-inventory-visibility-integration"></a><span data-ttu-id="42471-201">Készletláthatósági integráció beállítása</span><span class="sxs-lookup"><span data-stu-id="42471-201">Set up Inventory Visibility integration</span></span>

1. <span data-ttu-id="42471-202">A Supply Chain Management alkalmazásban nyissa meg a **[Szolgáltatáskezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)** munkaterületet, és kapcsolja be a **Készlet láthatósági integrációja** funkciót.</span><span class="sxs-lookup"><span data-stu-id="42471-202">In Supply Chain Management, open the **[Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)** workspace, and turn on the **Inventory Visibility Integration** feature.</span></span>
1. <span data-ttu-id="42471-203">Lépjen a **Készletkezelés \> Beállítás \> Készlet láthatósági integrációjának paraméterei** lehetőségre, és adja meg annak a környezetnek az URL-címét, ahol a Készlet láthatóságát futtatja.</span><span class="sxs-lookup"><span data-stu-id="42471-203">Go to **Inventory Management \> Set up \> Inventory Visibility Integration parameters**, and enter the URL of the environment where you're running Inventory Visibility.</span></span>

    <span data-ttu-id="42471-204">Keresse meg az LCS-környezet Azure-régióját, majd adja meg az URL-címet.</span><span class="sxs-lookup"><span data-stu-id="42471-204">Find your LCS environment's Azure region, and then enter the URL.</span></span> <span data-ttu-id="42471-205">Az URL-cím a következő képernyőt tartalmazza:</span><span class="sxs-lookup"><span data-stu-id="42471-205">The URL has the following form:</span></span>

    `https://inventoryservice.<RegionShortName>-il301.gateway.prod.island.powerapps.com/`

    <span data-ttu-id="42471-206">Ha például Európában van, a környezete a következő URL-címek valamelyikét fogja tartalmazni:</span><span class="sxs-lookup"><span data-stu-id="42471-206">For example, if you're in Europe, your environment will have one of the following URLs:</span></span>

    - `https://inventoryservice.neu-il301.gateway.prod.island.powerapps.com/`
    - `https://inventoryservice.weu-il301.gateway.prod.island.powerapps.com/`

    <span data-ttu-id="42471-207">Jelenleg a következő régiók állnak rendelkezésre.</span><span class="sxs-lookup"><span data-stu-id="42471-207">The following regions are currently available.</span></span>

    | <span data-ttu-id="42471-208">Azure-régió</span><span class="sxs-lookup"><span data-stu-id="42471-208">Azure region</span></span> | <span data-ttu-id="42471-209">Régió rövid neve</span><span class="sxs-lookup"><span data-stu-id="42471-209">Region short name</span></span> |
    |---|---|
    | <span data-ttu-id="42471-210">Kelet-Ausztrália</span><span class="sxs-lookup"><span data-stu-id="42471-210">Australia east</span></span> | <span data-ttu-id="42471-211">eau</span><span class="sxs-lookup"><span data-stu-id="42471-211">eau</span></span> |
    | <span data-ttu-id="42471-212">Délkelet-Ausztrália</span><span class="sxs-lookup"><span data-stu-id="42471-212">Australia southeast</span></span> | <span data-ttu-id="42471-213">seau</span><span class="sxs-lookup"><span data-stu-id="42471-213">seau</span></span> |
    | <span data-ttu-id="42471-214">Közép-Kanada</span><span class="sxs-lookup"><span data-stu-id="42471-214">Canada central</span></span> | <span data-ttu-id="42471-215">cca</span><span class="sxs-lookup"><span data-stu-id="42471-215">cca</span></span> |
    | <span data-ttu-id="42471-216">Kelet-Kanada</span><span class="sxs-lookup"><span data-stu-id="42471-216">Canada east</span></span> | <span data-ttu-id="42471-217">eca</span><span class="sxs-lookup"><span data-stu-id="42471-217">eca</span></span> |
    | <span data-ttu-id="42471-218">Észak-Európa</span><span class="sxs-lookup"><span data-stu-id="42471-218">North Europe</span></span> | <span data-ttu-id="42471-219">neu</span><span class="sxs-lookup"><span data-stu-id="42471-219">neu</span></span> |
    | <span data-ttu-id="42471-220">Nyugat-Európa</span><span class="sxs-lookup"><span data-stu-id="42471-220">West Europe</span></span> | <span data-ttu-id="42471-221">weu</span><span class="sxs-lookup"><span data-stu-id="42471-221">weu</span></span> |
    | <span data-ttu-id="42471-222">USA keleti régiója</span><span class="sxs-lookup"><span data-stu-id="42471-222">East US</span></span> | <span data-ttu-id="42471-223">eus</span><span class="sxs-lookup"><span data-stu-id="42471-223">eus</span></span> |
    | <span data-ttu-id="42471-224">USA nyugati régiója</span><span class="sxs-lookup"><span data-stu-id="42471-224">West US</span></span> | <span data-ttu-id="42471-225">wus</span><span class="sxs-lookup"><span data-stu-id="42471-225">wus</span></span> |

1. <span data-ttu-id="42471-226">Lépjen a **Készletkezelés \> Időszakos \> Készlet láthatósági integrációja** elemre, és engedélyezze a feladatot.</span><span class="sxs-lookup"><span data-stu-id="42471-226">Go to **Inventory Management \> Periodic \> Inventory Visibility Integration**, and enable the job.</span></span> <span data-ttu-id="42471-227">A rendszer a Supply Chain Management minden készletváltozási eseményét feladja a Készlet láthatósága számára.</span><span class="sxs-lookup"><span data-stu-id="42471-227">All inventory change events from Supply Chain Management will now be posted to Inventory Visibility.</span></span>

## <a name="the-inventory-visibility-add-in-public-api"></a><a name="inventory-visibility-public-api"></a><span data-ttu-id="42471-228">A Készlet láthatósága bővítmény nyilvános API-je</span><span class="sxs-lookup"><span data-stu-id="42471-228">The Inventory Visibility Add-in public API</span></span>

<span data-ttu-id="42471-229">A Készlet láthatósága bővítmény nyilvános REST API-ja az integráció több konkrét végpontját mutatja be.</span><span class="sxs-lookup"><span data-stu-id="42471-229">The public REST API of the Inventory Visibility Add-in presents several specific endpoints for integration.</span></span> <span data-ttu-id="42471-230">Három fő interakciós típust támogat:</span><span class="sxs-lookup"><span data-stu-id="42471-230">It supports three main interaction types:</span></span>

- <span data-ttu-id="42471-231">A bővítmény aktuális készletmódosításainak külső rendszerből történő feladása</span><span class="sxs-lookup"><span data-stu-id="42471-231">Posting on-hand inventory changes to the add-in from an external system</span></span>
- <span data-ttu-id="42471-232">Aktuális rendelkezésre álló mennyiségek lekérdezése külső rendszerből</span><span class="sxs-lookup"><span data-stu-id="42471-232">Querying current on-hand quantities from an external system</span></span>
- <span data-ttu-id="42471-233">Automatikus szinkronizálás a Supply Chain Management aktuális készletével</span><span class="sxs-lookup"><span data-stu-id="42471-233">Automatic synchronization with Supply Chain Management on-hand inventory</span></span>

<span data-ttu-id="42471-234">Az automatikus szinkronizálás nem része a nyilvános API-nak.</span><span class="sxs-lookup"><span data-stu-id="42471-234">Automatic synchronization isn't part of the public API.</span></span> <span data-ttu-id="42471-235">Ehelyett a rendszer a háttérben kezeli olyan környezetekben, ahol engedélyezve van a Készlet láthatósága bővítmény.</span><span class="sxs-lookup"><span data-stu-id="42471-235">Instead, it's handled in the background for environments where the Inventory Visibility Add-in is enabled.</span></span>

### <a name="authentication"></a><a name="inventory-visibility-authentication"></a><span data-ttu-id="42471-236">Hitelesítés</span><span class="sxs-lookup"><span data-stu-id="42471-236">Authentication</span></span>

<span data-ttu-id="42471-237">A platform biztonsági tokenje a Készlet láthatósága bővítmény hívására használatos.</span><span class="sxs-lookup"><span data-stu-id="42471-237">The platform security token is used to call the Inventory Visibility Add-in.</span></span> <span data-ttu-id="42471-238">Emiatt az Azure AD-alkalmazás használatával létre kell hozni egy *Azure Active Directory (Azure AD) tokent*.</span><span class="sxs-lookup"><span data-stu-id="42471-238">Therefore, you must generate an *Azure Active Directory (Azure AD) token* by using your Azure AD application.</span></span> <span data-ttu-id="42471-239">Ezt követően az Azure AD-tokent kell ahhoz használnia, hogy a *hozzáférési tokent* be tudja szerezni a biztonsági szolgáltatásból.</span><span class="sxs-lookup"><span data-stu-id="42471-239">You must then use the Azure AD token to get the *access token* from the security service.</span></span>

<span data-ttu-id="42471-240">Biztonsági szolgáltatás jogkivonatának beszerzéséhez tegye a következőket:</span><span class="sxs-lookup"><span data-stu-id="42471-240">Get a security service token by doing the following:</span></span>

1. <span data-ttu-id="42471-241">Jelentkezzen be az Azure Portal webhelyre, és használja a `clientId` és `clientSecret` keresésére a Supply Chain Management alkalmazáshoz.</span><span class="sxs-lookup"><span data-stu-id="42471-241">Sign in to Azure portal and use it to find the `clientId` and `clientSecret` for your Supply Chain Management application.</span></span>
1. <span data-ttu-id="42471-242">Azure Active Directory kód beolvasása (`aadToken`) a következő tulajdonságokkal rendelkező HTTP-kérés beküldésével:</span><span class="sxs-lookup"><span data-stu-id="42471-242">Fetch an Azure Active Directory token (`aadToken`) by submitting an HTTP request with the following properties:</span></span>
    - <span data-ttu-id="42471-243">**URL-cím** - `https://login.microsoftonline.com/${aadTenantId}/oauth2/token`</span><span class="sxs-lookup"><span data-stu-id="42471-243">**URL** - `https://login.microsoftonline.com/${aadTenantId}/oauth2/token`</span></span>
    - <span data-ttu-id="42471-244">**Metódus** - `GET`</span><span class="sxs-lookup"><span data-stu-id="42471-244">**Method** - `GET`</span></span>
    - <span data-ttu-id="42471-245">**Levél tartalma (űrlapadatok)**:</span><span class="sxs-lookup"><span data-stu-id="42471-245">**Body content (form data)**:</span></span>

        | <span data-ttu-id="42471-246">kulcs</span><span class="sxs-lookup"><span data-stu-id="42471-246">key</span></span> | <span data-ttu-id="42471-247">érték</span><span class="sxs-lookup"><span data-stu-id="42471-247">value</span></span> |
        | --- | --- |
        | <span data-ttu-id="42471-248">ügyfél azonosítója</span><span class="sxs-lookup"><span data-stu-id="42471-248">client_id</span></span> | <span data-ttu-id="42471-249">${aadAppId}</span><span class="sxs-lookup"><span data-stu-id="42471-249">${aadAppId}</span></span> |
        | <span data-ttu-id="42471-250">titkos ügyfélkód</span><span class="sxs-lookup"><span data-stu-id="42471-250">client_secret</span></span> | <span data-ttu-id="42471-251">${aadAppSecret}</span><span class="sxs-lookup"><span data-stu-id="42471-251">${aadAppSecret}</span></span> |
        | <span data-ttu-id="42471-252">engedélyezési típus</span><span class="sxs-lookup"><span data-stu-id="42471-252">grant_type</span></span> | <span data-ttu-id="42471-253">ügyfél_azonosító adatai</span><span class="sxs-lookup"><span data-stu-id="42471-253">client_credentials</span></span> |
        | <span data-ttu-id="42471-254">erőforrás</span><span class="sxs-lookup"><span data-stu-id="42471-254">resource</span></span> | <span data-ttu-id="42471-255">0cdb527f-a8d1-4bf8-9436-b352c68682b2</span><span class="sxs-lookup"><span data-stu-id="42471-255">0cdb527f-a8d1-4bf8-9436-b352c68682b2</span></span> |
1. <span data-ttu-id="42471-256">Válaszként egy `aadToken` kódot kell kapnia, amelynek a következő példához kell hasonlítania.</span><span class="sxs-lookup"><span data-stu-id="42471-256">You should receive an `aadToken` in response, which resembles the following example.</span></span>

    ```json
    {
    "token_type": "Bearer",
    "expires_in": "3599",
    "ext_expires_in": "3599",
    "expires_on": "1610466645",
    "not_before": "1610462745",
    "resource": "0cdb527f-a8d1-4bf8-9436-b352c68682b2",
    "access_token": "eyJ0eX...8WQ"
    }
    ```

1. <span data-ttu-id="42471-257">Fogalmazzon meg egy olyan JSON-kérést, amely hasonlít a következőkre:</span><span class="sxs-lookup"><span data-stu-id="42471-257">Formulate a JSON request that resembles the following:</span></span>

    ```json
    {
        "grant_type": "client_credentials",
        "client_assertion_type":"aad_app",
        "client_assertion": "{Your_AADToken}",
        "scope":"https://inventoryservice.operations365.dynamics.com/.default",
        "context": "5dbf6cc8-255e-4de2-8a25-2101cd5649b4",
        "context_type": "finops-env"
    }
    ```

    <span data-ttu-id="42471-258">Ahol:</span><span class="sxs-lookup"><span data-stu-id="42471-258">Where:</span></span>
    - <span data-ttu-id="42471-259">A `client_assertion` értéknek az előző lépésben kapott `aadToken` értéknek kell lennie.</span><span class="sxs-lookup"><span data-stu-id="42471-259">The `client_assertion` value must be the `aadToken` you received in the previous step.</span></span>
    - <span data-ttu-id="42471-260">A `context` érték az a környezetazonosító, ahová telepíteni szeretné a bővítményt.</span><span class="sxs-lookup"><span data-stu-id="42471-260">The `context` value must be the environment ID where you want to deploy the add-in.</span></span>
    - <span data-ttu-id="42471-261">Állítsa be az összes többi értéket a példában látható módon.</span><span class="sxs-lookup"><span data-stu-id="42471-261">Set all of other values as shown in the example.</span></span>

1. <span data-ttu-id="42471-262">HTTP-kérés küldése a következő tulajdonságokkal:</span><span class="sxs-lookup"><span data-stu-id="42471-262">Submit an HTTP request with the following properties:</span></span>
    - <span data-ttu-id="42471-263">**URL-cím** - `https://securityservice.operations365.dynamics.com/token`</span><span class="sxs-lookup"><span data-stu-id="42471-263">**URL** - `https://securityservice.operations365.dynamics.com/token`</span></span>
    - <span data-ttu-id="42471-264">**Metódus** - `POST`</span><span class="sxs-lookup"><span data-stu-id="42471-264">**Method** - `POST`</span></span>
    - <span data-ttu-id="42471-265">**HTTP-fejléc** – tartalmazza az API-verziót (a kulcs `Api-Version` és az érték: `1.0`)</span><span class="sxs-lookup"><span data-stu-id="42471-265">**HTTP header** - Include the API version (key is `Api-Version` and value is `1.0`)</span></span>
    - <span data-ttu-id="42471-266">**Levél tartalma** – foglalja bele az előző lépésben létrehozott JSON-kérelmet.</span><span class="sxs-lookup"><span data-stu-id="42471-266">**Body content** - Include the JSON request that you created in the previous step.</span></span>

1. <span data-ttu-id="42471-267">Kap egy `access_token` elemet válaszul.</span><span class="sxs-lookup"><span data-stu-id="42471-267">You will get an `access_token` in response.</span></span> <span data-ttu-id="42471-268">Ez az, amire szüksége van, mint tulajdonosi jogkivonat, hogy meghívja meg a Készlet láthatósága API-t.</span><span class="sxs-lookup"><span data-stu-id="42471-268">This is what you need as a bearer token to call the Inventory Visibility API.</span></span> <span data-ttu-id="42471-269">Íme, egy példa.</span><span class="sxs-lookup"><span data-stu-id="42471-269">Here is an example.</span></span>

    ```json
    {
        "access_token": "{Returned_Token}",
        "token_type": "bearer",
        "expires_in": 1200
    }
    ```

### <a name="configure-the-inventory-visibility-api"></a><a name="inventory-visibility-configuration"></a><span data-ttu-id="42471-270">A Készlet láthatósága API konfigurálása</span><span class="sxs-lookup"><span data-stu-id="42471-270">Configure the Inventory Visibility API</span></span>

<span data-ttu-id="42471-271">A szolgáltatás használata előtt ki kell töltenie az alábbi alszakaszokban ismertetett konfigurációkat.</span><span class="sxs-lookup"><span data-stu-id="42471-271">Before using the service, you must complete the configurations described in the following subsections.</span></span> <span data-ttu-id="42471-272">A konfiguráció a környezet részleteitől függően változhat.</span><span class="sxs-lookup"><span data-stu-id="42471-272">The configuration may vary based on the details of your environment.</span></span> <span data-ttu-id="42471-273">Ez elsősorban négy részből áll:</span><span class="sxs-lookup"><span data-stu-id="42471-273">It primarily includes four parts:</span></span>

- [<span data-ttu-id="42471-274">Particionálás</span><span class="sxs-lookup"><span data-stu-id="42471-274">Partitioning</span></span>](#partitioning)
- [<span data-ttu-id="42471-275">Dimenziókonfigurációk</span><span class="sxs-lookup"><span data-stu-id="42471-275">Dimension configurations</span></span>](#dimension-configurations)
- [<span data-ttu-id="42471-276">Indexelés</span><span class="sxs-lookup"><span data-stu-id="42471-276">Indexing</span></span>](#indexing)
- [<span data-ttu-id="42471-277">Egyéni mérés</span><span class="sxs-lookup"><span data-stu-id="42471-277">Custom measurement</span></span>](#custom-measurement)

#### <a name="partitioning"></a><span data-ttu-id="42471-278">Particionálás</span><span class="sxs-lookup"><span data-stu-id="42471-278">Partitioning</span></span>

<span data-ttu-id="42471-279">A particionálás jelentősen befolyásolhatja a Készlet láthatósága API teljesítményét.</span><span class="sxs-lookup"><span data-stu-id="42471-279">Partitioning can significantly influence the performance of the Inventory Visibility API.</span></span> <span data-ttu-id="42471-280">Célszerű olyan sémát definiálni, amely lehetővé teszi az adatok kis csoportjait, miközben továbbra is lehetővé teszi az értelmezhető adatlekérdezéseket.</span><span class="sxs-lookup"><span data-stu-id="42471-280">It's a good idea to define a scheme that allows for small groupings of data while still allowing for meaningful data queries.</span></span>

<span data-ttu-id="42471-281">Az `organizationId` (`dataAreaId` a Supply Chain Management esetében) mindig a particionálás része lesz, és alapértelmezés szerint a Készlet láthatósága dimenziók szerinti particionálásra van beállítva *Telephely + Hely* szerint.</span><span class="sxs-lookup"><span data-stu-id="42471-281">The `organizationId` (`dataAreaId` in Supply Chain Management) will always be part of the partitioning, and by default Inventory Visibility is set to partition by dimensions as *Site + Location*.</span></span> <span data-ttu-id="42471-282">Ez azt jelenti, hogy a szolgáltatást mindig le kell kérdezni ezekkel a szűrőkön definiált dimenziókkal.</span><span class="sxs-lookup"><span data-stu-id="42471-282">This means that the service must always be queried with these dimensions defined on the filters.</span></span>

> [!NOTE]
> <span data-ttu-id="42471-283">A *Telephely* és a *Hely* két általános alapértelmezett dimenzió a Készlet láthatóságában.</span><span class="sxs-lookup"><span data-stu-id="42471-283">*Site* and *Location* are two general default dimensions in Inventory Visibility.</span></span> <span data-ttu-id="42471-284">A Supply Chain Managementben ezeket a dimenziók *Telephely* (`InventSiteId`) és *Raktár* (`InventLocationId`) néven szerepelnek</span><span class="sxs-lookup"><span data-stu-id="42471-284">In Supply Chain Management, those dimensions are called *Site* (`InventSiteId`) and *Warehouse* (`InventLocationId`)</span></span>

### <a name="dimension-configurations"></a><span data-ttu-id="42471-285">Dimenziókonfigurációk</span><span class="sxs-lookup"><span data-stu-id="42471-285">Dimension configurations</span></span>

<span data-ttu-id="42471-286">A Készlet láthatósága az általános alapértelmezett dimenziók listáját tartalmazza a több forrásrendszer integrációjának engedélyezéséhez.</span><span class="sxs-lookup"><span data-stu-id="42471-286">Inventory Visibility will provide a list of general default dimensions to enable the multiple source system integration.</span></span>

<span data-ttu-id="42471-287">Az alábbi táblázat azokat a készletdimenziókat sorolja fel, amelyek a Készlet láthatósága alapértelmezett dimenziónevei lesznek.</span><span class="sxs-lookup"><span data-stu-id="42471-287">The following table lists the inventory dimensions that will be the default dimension names in Inventory Visibility.</span></span>

| <span data-ttu-id="42471-288">Dimenzió típusa</span><span class="sxs-lookup"><span data-stu-id="42471-288">Dimension type</span></span> | <span data-ttu-id="42471-289">Dimenzió neve</span><span class="sxs-lookup"><span data-stu-id="42471-289">Dimension name</span></span> |
|---|---|
| <span data-ttu-id="42471-290">Termék</span><span class="sxs-lookup"><span data-stu-id="42471-290">Product</span></span> | `ColorId` |
| <span data-ttu-id="42471-291">Termék</span><span class="sxs-lookup"><span data-stu-id="42471-291">Product</span></span> | `SizeId` |
| <span data-ttu-id="42471-292">Termék</span><span class="sxs-lookup"><span data-stu-id="42471-292">Product</span></span> | `StyleId` |
| <span data-ttu-id="42471-293">Termék</span><span class="sxs-lookup"><span data-stu-id="42471-293">Product</span></span> | `ConfigId` |
| <span data-ttu-id="42471-294">Nyomon követés</span><span class="sxs-lookup"><span data-stu-id="42471-294">Tracking</span></span> | `BatchId` |
| <span data-ttu-id="42471-295">Nyomon követés</span><span class="sxs-lookup"><span data-stu-id="42471-295">Tracking</span></span> | `SerialId` |
| <span data-ttu-id="42471-296">Helyszín</span><span class="sxs-lookup"><span data-stu-id="42471-296">Location</span></span> | `LocationId` |
| <span data-ttu-id="42471-297">Helyszín</span><span class="sxs-lookup"><span data-stu-id="42471-297">Location</span></span> | `SiteId` |
| <span data-ttu-id="42471-298">Készlet állapota</span><span class="sxs-lookup"><span data-stu-id="42471-298">Inventory Status</span></span> | `StatusId` |
| <span data-ttu-id="42471-299">Raktárspecifikus</span><span class="sxs-lookup"><span data-stu-id="42471-299">Warehouse Specific</span></span> | `WMSLocationId` |
| <span data-ttu-id="42471-300">Raktárspecifikus</span><span class="sxs-lookup"><span data-stu-id="42471-300">Warehouse Specific</span></span> | `WMSPalletId` |
| <span data-ttu-id="42471-301">Raktárspecifikus</span><span class="sxs-lookup"><span data-stu-id="42471-301">Warehouse Specific</span></span> | `LicensePlateId` |

> [!NOTE]
> <span data-ttu-id="42471-302">Az előző táblában felsorolt dimenziótípus csak tájékoztató jellegű.</span><span class="sxs-lookup"><span data-stu-id="42471-302">The dimension type listed in the previous table is for reference only.</span></span> <span data-ttu-id="42471-303">A dimenziótípust nem kell definiálnia a Készlet láthatósága bővítményben.</span><span class="sxs-lookup"><span data-stu-id="42471-303">You don't need to define the dimension type in Inventory Visibility.</span></span>

<span data-ttu-id="42471-304">Ha létezik egyéni dimenzió, és a Készlet láthatósága által felhasznált alapértelmezett értékre kell áramlania, az **Egyéni dimenzió** nevét a Készlet láthatóságában konfigurálhatja.</span><span class="sxs-lookup"><span data-stu-id="42471-304">If a custom dimension exists and needs to flow to a default value when consumed by Inventory Visibility, you can configure the **Custom dimension** name in Inventory Visibility.</span></span>

<span data-ttu-id="42471-305">A külső rendszerek RESTful API-kon keresztül férnek hozzá a Készlet láthatóságához, amelyek lehetővé teszik az adott dimenziókészletek aktuális információinak lekérdezését.</span><span class="sxs-lookup"><span data-stu-id="42471-305">External systems access Inventory Visibility through RESTful APIs that enable on-hand information on given sets of dimensions to be queried.</span></span> <span data-ttu-id="42471-306">Az integrációhoz a Készlet láthatósága lehetővé teszi a *külső csatorna adatforrásának* és a forrásdimenziónak a Készlet láthatósága *céldimenzióihoz* való konfigurálását.</span><span class="sxs-lookup"><span data-stu-id="42471-306">For the integration, Inventory Visibility enables you to configure the *external channel data source* and the source dimension to the *target dimensions* in Inventory Visibility.</span></span>

<span data-ttu-id="42471-307">A céldimenzióknak a következők egyikének kell lenniük:</span><span class="sxs-lookup"><span data-stu-id="42471-307">The target dimensions should be one of the following:</span></span>

- <span data-ttu-id="42471-308">Alapértelmezett dimenziók a Készlet láthatóságában</span><span class="sxs-lookup"><span data-stu-id="42471-308">Default dimensions in Inventory Visibility</span></span>
- <span data-ttu-id="42471-309">Egyéni dimenziók</span><span class="sxs-lookup"><span data-stu-id="42471-309">Custom dimensions</span></span>

<span data-ttu-id="42471-310">A dimenziókonfiguráció célja a dimenziókra irányuló lekérdezések és a dimenziókkal való feladási esemény többrendszeres integrációjának szabványosítása.</span><span class="sxs-lookup"><span data-stu-id="42471-310">The purpose of dimension configuration is to standardize the multi-system integration for the query on dimensions and the posting event with dimensions.</span></span>

#### <a name="indexing"></a><span data-ttu-id="42471-311">Indexelés</span><span class="sxs-lookup"><span data-stu-id="42471-311">Indexing</span></span>

<span data-ttu-id="42471-312">Az aktuális készlet lekérdezése a legtöbb alkalommal nem csak a legmagasabb "teljes" szinten lesz, de előfordulhat, hogy a készletdimenziók alapján összesítve szeretné látni az eredményeket.</span><span class="sxs-lookup"><span data-stu-id="42471-312">Most of the time, the inventory on-hand query will not only be on the highest "total" level, but you may want to see results aggregated based on the inventory dimensions.</span></span>

<span data-ttu-id="42471-313">A Készlet láthatósága rugalmasságot biztosít azáltal, hogy lehetővé teszi az indexek beállítását, amelyek a dimenzión vagy a dimenziók kombinációján alapulnak.</span><span class="sxs-lookup"><span data-stu-id="42471-313">Inventory Visibility provides flexibility by allowing you to set up the indexes, which are based on the dimension or the combination of the dimensions.</span></span>

> [!NOTE]
> <span data-ttu-id="42471-314">Jelenleg csak legfeljebb öt indexet konfigurálhat.</span><span class="sxs-lookup"><span data-stu-id="42471-314">Currently, you can only configure indexes to a maximum of five.</span></span> <span data-ttu-id="42471-315">Alaposan meg kell fontolnia, hogy melyik dimenziót vagy dimenziókombinációt fogja használni a megvalósítás előtt annak érdekében, hogy megfeleljen az üzleti igényeinek.</span><span class="sxs-lookup"><span data-stu-id="42471-315">You need to carefully consider which dimension or dimension combination you will use before the implementation to ensure that it will meet your business needs.</span></span> <span data-ttu-id="42471-316">Ha például a következőképpen szeretne lekérdezni a termékeket:</span><span class="sxs-lookup"><span data-stu-id="42471-316">For example, if you want to query products as follows:</span></span>

- <span data-ttu-id="42471-317">Az összesített termék lekérdezése a *Szín* és *Méret* dimenziókkal.</span><span class="sxs-lookup"><span data-stu-id="42471-317">Query the aggregated product on-hand by the *Color* and *Size* dimensions.</span></span>
- <span data-ttu-id="42471-318">Bizonyos esetekben csak a termék összesített értékét szeretné lekérdezni.</span><span class="sxs-lookup"><span data-stu-id="42471-318">In some cases, you just want to query on the product in total.</span></span>

<span data-ttu-id="42471-319">Két indexet kell definiálni a következőképpen:</span><span class="sxs-lookup"><span data-stu-id="42471-319">You would have two indexes defined as the following:</span></span>

- `["ColorId", "SizeId"]`
- `[]`

<span data-ttu-id="42471-320">Az üres zárójel a partíción belül termékazonosító alapján összesít.</span><span class="sxs-lookup"><span data-stu-id="42471-320">The empty bracket will aggregate based on the product ID within the partition.</span></span>

<span data-ttu-id="42471-321">Az indexelés határozza meg, hogyan csoportosíthatja az eredményeket a `groupBy` lekérdezési beállítás alapján.</span><span class="sxs-lookup"><span data-stu-id="42471-321">The indexing defines how you can group your results based on the `groupBy` query setting.</span></span> <span data-ttu-id="42471-322">Ebben az esetben, ha nem határoz meg `groupBy` értékeket, `productid` szerinti összegeket kap.</span><span class="sxs-lookup"><span data-stu-id="42471-322">In this case if you don't define any `groupBy` values, you'll get totals by `productid`.</span></span> <span data-ttu-id="42471-323">Ellenkező esetben, ha a `groupBy` a `groupBy=ColorId&groupBy=SizeId` értékkel van megadva, a rendszer a különböző szín- és méretkombinációk alapján több sort ad vissza.</span><span class="sxs-lookup"><span data-stu-id="42471-323">Otherwise, if you define `groupBy` as `groupBy=ColorId&groupBy=SizeId`, you'll get multiple lines returned, based on the different color and size combinations in the system.</span></span>

<span data-ttu-id="42471-324">A lekérdezési feltételt a kérelem törzsébe teheti.</span><span class="sxs-lookup"><span data-stu-id="42471-324">You can put your query criteria in the request body.</span></span>

<span data-ttu-id="42471-325">Itt egy példa a termék szín- és méretkombinációját tartalmazó lekérdezésre.</span><span class="sxs-lookup"><span data-stu-id="42471-325">Here is a sample query on the product with color and size combination.</span></span>

```json
{
    "filters": {
        "OrganizationId": ["usmf"],
        "ProductId": ["MyProduct"],
        "LocationId": ["21"],
        "SiteId": ["2"],
        "ColorId": ["Red"]
    },
    "groupByValues": [
        "SizeId",
        "ColorId"
    ],
    "returnNegative": true
}
```

#### <a name="custom-measurement"></a><span data-ttu-id="42471-326">Egyéni mérés</span><span class="sxs-lookup"><span data-stu-id="42471-326">Custom measurement</span></span>

<span data-ttu-id="42471-327">Az alapértelmezett mértékmennyiségek a Supply Chain Management alkalmazsáshoz kapcsolódnak.</span><span class="sxs-lookup"><span data-stu-id="42471-327">The default measurement quantities are linked to Supply Chain Management.</span></span> <span data-ttu-id="42471-328">Előfordulhat azonban, hogy olyan mennyiséget szeretne, amely az alapértelmezett mértékek kombinációjából áll.</span><span class="sxs-lookup"><span data-stu-id="42471-328">However, you may want to have a quantity that is made up of a combination of the default measurements.</span></span> <span data-ttu-id="42471-329">Ehhez egyéni mennyiségek konfigurációját kell megadni, amely az aktuáliskészlet-lekérdezések kimenetéhez lesz hozzáadva.</span><span class="sxs-lookup"><span data-stu-id="42471-329">To do this, you can have a configuration of custom quantities, which will be added to the output of the on-hand queries.</span></span>

<span data-ttu-id="42471-330">A funkció segítségével egyszerűen meghatározhat egy sor olyan mért értéket, amelyet hozzá kell adni, és/vagy egy sor olyan mért értéket, amelyet ki kell vonni az egyéni mérések kialakításához.</span><span class="sxs-lookup"><span data-stu-id="42471-330">The functionality simply allows you to define a set of measures that will be added, and/or a set of measures that will be subtracted, in order to form the custom measurement.</span></span>

<span data-ttu-id="42471-331">Például a következő lekérdezési feltétel esetén az egyéni mértékegységet úgy kell konfigurálni, mint a `MyCustomAvailableforReservation` elemet, hogy a felhasználó rendszer felhasználja a mennyiséget.</span><span class="sxs-lookup"><span data-stu-id="42471-331">For example, with the following query condition, you will configure the custom measurement quantity as `MyCustomAvailableforReservation` to be consumed by the consumption system.</span></span>

```json
[
    {
        "productId": "MyProduct",
        "dimensions": {
            "colorid": "Red"
        },
        "quantities": {
            "mypos": {
                "outbound": 20.0,
                "inbound": 80.0
            },
            "fno": {
                "availphysical": 100.0,
                "orderedintotal": 50.0,
                "orderedreserved": 10.0
            },
            "exterchannel": {
                "received": 90.0,
                "scheduled": 30.0,
                "issued": 60.0,
                "reserved": 40.0
            }
        }
    }
]

```



| <span data-ttu-id="42471-332">Felhasználó rendszer</span><span class="sxs-lookup"><span data-stu-id="42471-332">Consumption system</span></span> | <span data-ttu-id="42471-333">Számított mértékek</span><span class="sxs-lookup"><span data-stu-id="42471-333">Calculated measurers</span></span> | <span data-ttu-id="42471-334">Adatforrás</span><span class="sxs-lookup"><span data-stu-id="42471-334">Data source</span></span> | <span data-ttu-id="42471-335">Módosító</span><span class="sxs-lookup"><span data-stu-id="42471-335">Modifier</span></span> | <span data-ttu-id="42471-336">Módosítószámítási típus</span><span class="sxs-lookup"><span data-stu-id="42471-336">Modifier calculation type</span></span> |
|---|---|---|---|---|
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `availphysical` | <span data-ttu-id="42471-337">Hozzáadás</span><span class="sxs-lookup"><span data-stu-id="42471-337">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedintotal` | <span data-ttu-id="42471-338">Hozzáadás</span><span class="sxs-lookup"><span data-stu-id="42471-338">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedreserved` | <span data-ttu-id="42471-339">Kivonás</span><span class="sxs-lookup"><span data-stu-id="42471-339">Subtraction</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `mypos` | `inbound` | <span data-ttu-id="42471-340">Hozzáadás</span><span class="sxs-lookup"><span data-stu-id="42471-340">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `mypos` | `outbound` | <span data-ttu-id="42471-341">Kivonás</span><span class="sxs-lookup"><span data-stu-id="42471-341">Subtraction</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `received` | <span data-ttu-id="42471-342">Hozzáadás</span><span class="sxs-lookup"><span data-stu-id="42471-342">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `scheduled` | <span data-ttu-id="42471-343">Hozzáadás</span><span class="sxs-lookup"><span data-stu-id="42471-343">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `issued` | <span data-ttu-id="42471-344">Kivonás</span><span class="sxs-lookup"><span data-stu-id="42471-344">Subtraction</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `reserved` | <span data-ttu-id="42471-345">Kivonás</span><span class="sxs-lookup"><span data-stu-id="42471-345">Subtraction</span></span> |

<span data-ttu-id="42471-346">Ezzel az egyéni mérték mennyiség lekérdezése a következő kimenetet fogja visszaadni.</span><span class="sxs-lookup"><span data-stu-id="42471-346">With that, the query on the custom measurement quantity will return the following output.</span></span>

```json
[
    {
        "productId": "MyProduct",
        "dimensions": {
            "colorid": "Red"
        },
        "quantities": {
            "mypos": {
                "outbound": 20.0,
                "inbound": 80.0
            },
            "fno": {
                "availphysical": 100.0,
                "orderedintotal": 50.0,
                "orderedreserved": 10.0
            },
            "exterchannel": {
                "received": 90.0,
                "scheduled": 30.0,
                "issued": 60.0,
                "reserved": 40.0
            },
            "CustomChannel": {
                "MyCustomAvailableforReservation": 220.0
            }
        }
    }
]
```

<span data-ttu-id="42471-347">A `MyCustomAvailableforReservation` kimenet az egyéni mértékek számítási beállításán alapul, a következők szerint:</span><span class="sxs-lookup"><span data-stu-id="42471-347">The `MyCustomAvailableforReservation` output is based on the calculation setting in the custom measurements as:</span></span>  
 <span data-ttu-id="42471-348">*100 + 50 + 80 + 90 + 30 &ndash; 10 &ndash; 20 &ndash; 60 &ndash; 40 = 220*</span><span class="sxs-lookup"><span data-stu-id="42471-348">*100 + 50 + 80 + 90 + 30 &ndash; 10 &ndash; 20 &ndash; 60 &ndash; 40 = 220*</span></span>

### <a name="posting-on-hand-changes"></a><span data-ttu-id="42471-349">Aktuális készletváltoztatások feladása</span><span class="sxs-lookup"><span data-stu-id="42471-349">Posting on-hand changes</span></span>

<span data-ttu-id="42471-350">A pontos URL-cím, amelyre az esemény feladása történik, a földrajzi régiótól függ.</span><span class="sxs-lookup"><span data-stu-id="42471-350">The exact URL that the event will be posted to will depend on your geographical region.</span></span> <span data-ttu-id="42471-351">Ez a következő formát veszi fel:</span><span class="sxs-lookup"><span data-stu-id="42471-351">It will take the form:</span></span>

`https://{serviceURL}/api/environment/{environmentId}/onhand`

<span data-ttu-id="42471-352">Ha hitelesítve van, ez az URL-cím együtt használható a HTTP `POST`-metódussal, amellyel a tényleges módosítási eseményeket elküldheti a szolgáltatásnak.</span><span class="sxs-lookup"><span data-stu-id="42471-352">When authenticated, this URL can be used along with the HTTP `POST` method to send on-hand change events to the service.</span></span>

<span data-ttu-id="42471-353">Speciális fejléc használatos a Dynamics 365-szolgáltatásokkal történő kommunikációra HTTP-kérések révén, megjelölve a Supply Chain Management-példány környezeti azonosítóját, amely az adatokhoz van kapcsolva.</span><span class="sxs-lookup"><span data-stu-id="42471-353">A special header is used for communicating with Dynamics 365 services through HTTP requests, denoting the environment ID of the Supply Chain Management instance the data is linked to.</span></span> <span data-ttu-id="42471-354">Példa:</span><span class="sxs-lookup"><span data-stu-id="42471-354">For example:</span></span>

`x-ms-environment-id: 2db79622-f97a-4d64-9844-d12efed41796`

#### <a name="posting-on-hand-changes-query-example-1"></a><span data-ttu-id="42471-355">Az aktuális készleten elvégzett módosításlekérdezések küldése – 1. példa</span><span class="sxs-lookup"><span data-stu-id="42471-355">Posting on-hand changes query example 1</span></span>

<span data-ttu-id="42471-356">Ez a példa egy olyan esetet mutat be, amelyben a dimenzió konfigurációját be kell állítania a Power Appsben.</span><span class="sxs-lookup"><span data-stu-id="42471-356">This example shows a scenario where you will set up the dimension configuration in Power Apps.</span></span>

<span data-ttu-id="42471-357">A dimenzió-hozzárendelés konfigurálásához használja a következő lekérdezést a Power Appsben:</span><span class="sxs-lookup"><span data-stu-id="42471-357">Use the following query to configure the dimension mapping in Power Apps:</span></span>

```json
{
    "PosSizeId": "SizeId",
    "PosColorId": "ColorId",
    "PosSiteId": "SiteId",
    "PosLocationId": "LocationId"
}
```

<span data-ttu-id="42471-358">Itt megadhatja a `dimensionDataSource` elemet és a lekérdezésekben használt egyéni dimenziókat.</span><span class="sxs-lookup"><span data-stu-id="42471-358">Now you can specify the `dimensionDataSource` and use custom dimensions in your queries.</span></span> <span data-ttu-id="42471-359">A rendszer automatikusan átváltja az egyéni dimenziókat az alapdimenziókra.</span><span class="sxs-lookup"><span data-stu-id="42471-359">The system will automatically convert custom dimensions to base dimensions.</span></span>

```json
{
    "id": "demo-test-00007",
    "organizationId": "usmf",
    "productId": "MyProduct",
    "quantities": {
        "pos": {
            "Outbound": 1
        }
    },
    "dimensionDataSource": "pos",
    "dimensions": {
        "PosSizeId": "Large",
        "PosColorId": "Red",
        "PosSiteId": "2",
        "PosLocationId": "21"
    }
}
```

#### <a name="posting-on-hand-changes-query-example-2"></a><span data-ttu-id="42471-360">Az aktuális készleten elvégzett módosításlekérdezések küldése – 2. példa</span><span class="sxs-lookup"><span data-stu-id="42471-360">Posting on-hand changes query example 2</span></span>

<span data-ttu-id="42471-361">Ez a példa egy olyan esetet mutat be, amikor nincs beállítva hozzárendelés a dimenziókonfigurációhoz a Power Appsben, így a feladásnak is az alapdimenziókat kell használnia.</span><span class="sxs-lookup"><span data-stu-id="42471-361">This example shows a scenario where no mappings are set up for the dimension configuration in Power Apps, so the posting should also use the base dimensions.</span></span> <span data-ttu-id="42471-362">Minden dimenziónak alapdimenziónak kell lennie, ha a `dimensionDataSource` mező null, üres vagy szóköz.</span><span class="sxs-lookup"><span data-stu-id="42471-362">All dimensions must be base dimensions when the `dimensionDataSource` field is null, empty, or whitespace.</span></span>

```json
{
    "id": "demo-test-00007",
    "organizationId": "usmf",
    "productId": "MyProduct",
    "quantities": {
        "pos": {
            "Outbound": 1
        }
    },
    "dimensions": {
        "SizeId": "Large",
        "ColorId": "Red",
        "SiteId": "2",
        "LocationId": "21"
    }
}
```

#### <a name="json-document-field-properties"></a><span data-ttu-id="42471-363">JSON-dokumentummező tulajdonságai</span><span class="sxs-lookup"><span data-stu-id="42471-363">JSON document field properties</span></span>

<span data-ttu-id="42471-364">A JSON-lekérdezés korábban megadott példáiban szereplő mezők a következő táblázatban látható tulajdonságokkal rendelkeznek.</span><span class="sxs-lookup"><span data-stu-id="42471-364">The fields from the JSON query examples provided previously have the properties listed in the following table.</span></span>

| <span data-ttu-id="42471-365">Mezőazonosító</span><span class="sxs-lookup"><span data-stu-id="42471-365">Field ID</span></span> | <span data-ttu-id="42471-366">Leírás</span><span class="sxs-lookup"><span data-stu-id="42471-366">Description</span></span> |
|---|---|
| `id` | <span data-ttu-id="42471-367">A megadott módosítási esemény egyedi azonosítója.</span><span class="sxs-lookup"><span data-stu-id="42471-367">A unique ID for the specific change event.</span></span> <span data-ttu-id="42471-368">Ez az azonosító annak biztosítására szolgál, hogy ha a szolgáltatással folytatott kommunikáció nem sikerül a feladás során, akkor az esemény újraküldése nem eredményezi azt, hogy a rendszer kétszer számolja ugyanazt az eseményt.</span><span class="sxs-lookup"><span data-stu-id="42471-368">This ID is used to ensure that if communication with the service fails during posting, resubmitting the event would not result in the same event being counted twice in the system.</span></span> |
| `organizationId` | <span data-ttu-id="42471-369">Az eseményhez kapcsolt szervezet azonosítója.</span><span class="sxs-lookup"><span data-stu-id="42471-369">The identifier of the organization linked to the event.</span></span> <span data-ttu-id="42471-370">Ez a leképezés a Supply Chain Management-szervezetekre vagy az adatterület-azonosítóra vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="42471-370">This maps to Supply Chain Management organizations or data area IDs.</span></span> |
| `productId` | <span data-ttu-id="42471-371">A kérdéses termék azonosítója.</span><span class="sxs-lookup"><span data-stu-id="42471-371">The identifier of the product in question.</span></span> |
| `quantity` | <span data-ttu-id="42471-372">Az a mennyiség, amellyel az aktuális készletet módosítani kell.</span><span class="sxs-lookup"><span data-stu-id="42471-372">The quantity by which the on-hand needs to be changed.</span></span> <span data-ttu-id="42471-373">Ha például 10 új bagel került fel egy polcra, ez az érték 10 lesz.</span><span class="sxs-lookup"><span data-stu-id="42471-373">If, for instance, 10 new bagels were added to a shelf, this value would be 10.</span></span> <span data-ttu-id="42471-374">Ha 3 bagelt eltávolítanak a polcról vagy eladnak, akkor ez az érték – 3.</span><span class="sxs-lookup"><span data-stu-id="42471-374">If 3 bagels were then removed from the shelf or sold, this value would be -3.</span></span> |
| `dimensionDataSource` | <span data-ttu-id="42471-375">A feladási módosítási eseményben és lekérdezésben használt dimenziók adatforrása.</span><span class="sxs-lookup"><span data-stu-id="42471-375">The data source of the dimensions used in the posting change event and query.</span></span> <span data-ttu-id="42471-376">Az adatforrás megadása esetén a megadott adatforrás egyéni dimenzióit is használhatja.</span><span class="sxs-lookup"><span data-stu-id="42471-376">If you specify the data source, you can use the custom dimensions from the specified data source.</span></span> <span data-ttu-id="42471-377">A dimenzió konfigurálása során a Készlet láthatósága az egyéni dimenziókat az általános alapértelmezett dimenziókra tudja leképezni.</span><span class="sxs-lookup"><span data-stu-id="42471-377">With the dimension configuration, Inventory Visibility can map the custom dimensions to the general default dimensions.</span></span> <span data-ttu-id="42471-378">Ha a `dimensionDataSource` nincs megadva, akkor a lekérdezésekben csak az általános alapértelmezett dimenziókat használhatja.</span><span class="sxs-lookup"><span data-stu-id="42471-378">If the `dimensionDataSource` is not specified, you can only use the general default dimensions in your queries.</span></span>   |
| `dimensions` | <span data-ttu-id="42471-379">A kulcs/érték párok dinamikus csoportja.</span><span class="sxs-lookup"><span data-stu-id="42471-379">A dynamic bag of key/value pairs.</span></span> <span data-ttu-id="42471-380">Ezek a Supply Chain Management néhány dimenziójára kerülnek leképezésre, de hozzáadhat egyéni dimenziókat is (például *Forrás*), amely jelezheti, hogy az esemény a Supply Chain Managementből vagy egy külső rendszerből származik.</span><span class="sxs-lookup"><span data-stu-id="42471-380">These will map to some of the dimensions in Supply Chain Management, but you could also add custom dimensions (like *Source*) that may denote if the event was coming from Supply Chain Management or an external system.</span></span> |

### <a name="querying-current-on-hand"></a><span data-ttu-id="42471-381">Aktuális készlet lekérdezése</span><span class="sxs-lookup"><span data-stu-id="42471-381">Querying current on-hand</span></span>

<span data-ttu-id="42471-382">Az aktuális készlet lekérdezésének végpontja hasonló URL-címmel rendelkezik:</span><span class="sxs-lookup"><span data-stu-id="42471-382">The endpoint for querying the current on-hand will have a similar URL:</span></span>

`https://{serviceURL}/api/environment/{environmentId}/onhand/indexquery`

<span data-ttu-id="42471-383">A rendszer lekérdezi a HTTP `POST` metódussal.</span><span class="sxs-lookup"><span data-stu-id="42471-383">It will be queried with the HTTP `POST` method.</span></span>

#### <a name="current-on-hand-query-example-1"></a><span data-ttu-id="42471-384">Aktuális készleten lévő lekérdezés – 1. példa</span><span class="sxs-lookup"><span data-stu-id="42471-384">Current on-hand query example 1</span></span>

<span data-ttu-id="42471-385">Ez a példa egy olyan esetet mutat be, amelyben a dimenzió konfigurációját már végrehajtották a Power Appsben.</span><span class="sxs-lookup"><span data-stu-id="42471-385">This example shows a scenario where you have already completed the dimension configuration in Power Apps.</span></span>

<span data-ttu-id="42471-386">A dimenzió-hozzárendelés konfigurálásához használja a következő lekérdezést a Power Appsben:</span><span class="sxs-lookup"><span data-stu-id="42471-386">Use the following query to configure the dimension mapping in Power Apps:</span></span>

```json
{
    "PosSizeId": "SizeId",
    "PosColorId": "ColorId",
    "PosSiteId": "SiteId",
    "PosLocationId": "LocationId"
}
```

<span data-ttu-id="42471-387">Itt megadhatja a `dimensionDataSource` elemet és a lekérdezésekben használt egyéni dimenziókat.</span><span class="sxs-lookup"><span data-stu-id="42471-387">Now you can specify the `dimensionDataSource` and use custom dimensions in your queries.</span></span> <span data-ttu-id="42471-388">A rendszer automatikusan átváltja az egyéni dimenziókat az alapdimenziókra.</span><span class="sxs-lookup"><span data-stu-id="42471-388">The system will automatically convert custom dimensions to base dimensions.</span></span> <span data-ttu-id="42471-389">Megadhatja a `DimensionDataSource` értéket a `filters` számára, és megadhatja az egyéni dimenziókat mind a `filters` és a `groupByValues` esetében.</span><span class="sxs-lookup"><span data-stu-id="42471-389">You can specify the `DimensionDataSource` in `filters` and specify custom dimensions in both `filters` and `groupByValues`.</span></span> <span data-ttu-id="42471-390">A rendszer automatikusan átváltja az egyéni dimenziókat az alapdimenziókra.</span><span class="sxs-lookup"><span data-stu-id="42471-390">The system will automatically convert custom dimensions to base dimensions.</span></span>

```json
{
    "filters": {
        "OrganizationId": ["usmf"],
        "ProductId": ["MyProduct"],
        "DimensionDataSource": ["Pos"],
        "PosLocationId": ["21"],
        "PosSiteId": ["2"],
        "PosColorId": ["Red"]
    },
    "groupByValues": [
        "PosSizeId",
        "PosColorId"
    ],
    "returnNegative": true
}
```

#### <a name="current-on-hand-query-example-2"></a><span data-ttu-id="42471-391">Aktuális készleten lévő lekérdezés – 2. példa</span><span class="sxs-lookup"><span data-stu-id="42471-391">Current on-hand query example 2</span></span>

<span data-ttu-id="42471-392">Ez a példa egy olyan esetet mutat be, amikor nincs beállítva hozzárendelés a dimenziókonfigurációhoz a Power Appsben, így a feladásnak is az alapdimenziókat kell használnia.</span><span class="sxs-lookup"><span data-stu-id="42471-392">This example shows a scenario where no mappings are set up for the dimension configuration in Power Apps, so the posting should also use the base dimensions.</span></span> <span data-ttu-id="42471-393">Minden dimenziónak alapdimenziónak kell lennie, ha a `dimensionDataSource` mező a `filters` alatt null, üres vagy szóköz.</span><span class="sxs-lookup"><span data-stu-id="42471-393">All dimensions must be base dimensions when the `dimensionDataSource` field, under `filters` is null, empty, or whitespace.</span></span>

```json
{
    "filters": {
        "OrganizationId": ["usmf"],
        "ProductId": ["MyProduct"],
        "LocationId": ["21"],
        "SiteId": ["2"],
        "ColorId": ["Red"]
    },
    "groupByValues": [
        "SizeId",
        "ColorId"
    ],
    "returnNegative": true
}
```

#### <a name="example-return-result"></a><span data-ttu-id="42471-394">Példa visszatérési eredményre</span><span class="sxs-lookup"><span data-stu-id="42471-394">Example return result</span></span>

<span data-ttu-id="42471-395">Az előző példákban megjelenített lekérdezések a következőhöz hasonló eredményt adhatnak vissza.</span><span class="sxs-lookup"><span data-stu-id="42471-395">The queries shown in the previous examples could return a result like this.</span></span>

```json
[
    {
        "productId": "MyProduct",
        "dimensions": {
            "colorid": "Red"
        },
        "quantities": {
            "mypos": {
                "outbound": 20.0,
                "inbound": 80.0
            },
            "fno": {
                "availphysical": 100.0,
                "orderedintotal": 50.0,
                "orderedreserved": 10.0
            },
            "exterchannel": {
                "received": 90.0,
                "scheduled": 30.0,
                "issued": 60.0,
                "reserved": 40.0
            },
            "CustomChannel": {
                "MyCustomAvailableforReservation": 220.0
            }
        }
    }
]
```

<span data-ttu-id="42471-396">Ne felejtse el, hogy a mennyiségek mezői a mértékek és a hozzájuk kapcsolódó értékek jegyzékeként vannak strukturálva.</span><span class="sxs-lookup"><span data-stu-id="42471-396">Note that the quantities fields are structured as a dictionary of measures and their associated values.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
