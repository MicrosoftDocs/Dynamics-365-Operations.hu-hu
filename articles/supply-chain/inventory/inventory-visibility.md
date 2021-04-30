---
title: Készlet láthatósága bővítmény
description: Ez a témakör a Készlet láthatósága bővítmény telepítését és konfigurálását ismerteti a Dynamics 365 Supply Chain Management rendszerhez.
author: sherry-zheng
ms.date: 10/26/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-10-26
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: d09c7be5de75511b10d7a69d4b8ac12917b0dbe8
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/16/2021
ms.locfileid: "5910425"
---
# <a name="inventory-visibility-add-in"></a><span data-ttu-id="827cc-103">Készlet láthatósága bővítmény</span><span class="sxs-lookup"><span data-stu-id="827cc-103">Inventory Visibility Add-in</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]
[!INCLUDE [cc-data-platform-banner](../../includes/cc-data-platform-banner.md)]

<span data-ttu-id="827cc-104">A Készlet láthatósága bővítmény egy független és jól méretezhető mikroszolgáltatás, amely lehetővé teszi a valós idejű aktuális készletkövetést, így globális képet nyújt a készlet láthatóságáról.</span><span class="sxs-lookup"><span data-stu-id="827cc-104">The Inventory Visibility Add-in is an independent and highly scalable microservice that enables real-time on-hand inventory tracking, thus providing a global view of inventory visibility.</span></span>

<span data-ttu-id="827cc-105">Az aktuális készlethez kapcsolódó összes információt a rendszer közel valós időben exportálja a szolgáltatásba alacsony szintű SQL-integráció révén.</span><span class="sxs-lookup"><span data-stu-id="827cc-105">All information that relates to on-hand inventory is exported to the service in near real-time through low-level SQL integration.</span></span> <span data-ttu-id="827cc-106">A külső rendszerek RESTful API-kon keresztül érik el a szolgáltatást, hogy aktuális információkat kérdezzenek le adott dimenziókészletekről, így lekérve a rendelkezésre álló aktuális pozíciók listáját.</span><span class="sxs-lookup"><span data-stu-id="827cc-106">External systems access the service through RESTful APIs to query on-hand information on given sets of dimensions, thus retrieving a list of available on-hand positions.</span></span>

<span data-ttu-id="827cc-107">A Készlet láthatósága egy mikroszolgáltatás, amely a Microsoft Dataverse rendszerre épül, ami azt jelenti, hogy bővítheti Power Apps alkalmazások készítésével és Power BI alkalmazásával, hogy személyre szabott funkciókat biztosítson, amelyek megfelelnek az üzleti követelményeknek.</span><span class="sxs-lookup"><span data-stu-id="827cc-107">Inventory Visibility is a microservice built on Microsoft Dataverse, which means you can extend it by building Power Apps and applying Power BI to provide customized functionality to meet your business requirements.</span></span> <span data-ttu-id="827cc-108">Lehetőség van az index frissítésére is a készletlekérdezésekhez.</span><span class="sxs-lookup"><span data-stu-id="827cc-108">It is also possible to upgrade the index to do inventory queries.</span></span>

<span data-ttu-id="827cc-109">A Készlet láthatósága olyan konfigurációs beállításokat biztosít, amelyek lehetővé teszik, hogy több külső gyártótól származó rendszerrel integrálódjon.</span><span class="sxs-lookup"><span data-stu-id="827cc-109">Inventory Visibility provides configuration options that let it integrate with multiple third-party systems.</span></span> <span data-ttu-id="827cc-110">Támogatja a szabványosított készletdimenziót, a testreszabott bővíthetőséget és a szabványosított, konfigurálható számított mennyiségeket.</span><span class="sxs-lookup"><span data-stu-id="827cc-110">It supports the standardized inventory dimension, customized extensibility, and standardized, configurable calculated quantities.</span></span>

<span data-ttu-id="827cc-111">Ez a témakör azt ismerteti, hogyan telepítheti és konfigurálhatja az Készlet láthatósága bővítményt a Dynamics 365 Supply Chain Management rendszerhez, és hogyan használhatja az alkalmazásprogramozási felületét (API).</span><span class="sxs-lookup"><span data-stu-id="827cc-111">This topic describes how to install and configure the Inventory Visibility Add-in for Dynamics 365 Supply Chain Management, and how to use its application programming interface (API).</span></span>

## <a name="install-the-inventory-visibility-add-in"></a><span data-ttu-id="827cc-112">A Készlet láthatósága bővítmény telepítése</span><span class="sxs-lookup"><span data-stu-id="827cc-112">Install the Inventory Visibility Add-in</span></span>

<span data-ttu-id="827cc-113">Telepítenie kell a Készlet láthatósága bővítményt a Microsoft Dynamics Lifecycle Services (LCS) használatával.</span><span class="sxs-lookup"><span data-stu-id="827cc-113">You need to install the Inventory Visibility Add-in using Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="827cc-114">Az LCS egy együttműködési portál, amely egy környezetet és rendszeresen frissített szolgáltatások készletét biztosítja, amelyek segítenek a Dynamics 365 Finance and Operations-alkalmazások alkalmazás-életciklusának kezelésében.</span><span class="sxs-lookup"><span data-stu-id="827cc-114">LCS is a collaboration portal that provides an environment and a set of regularly updated services that help you manage the application lifecycle of your Dynamics 365 Finance and Operations apps.</span></span>

<span data-ttu-id="827cc-115">További tudnivalókért lásd: [Lifecycle Services-erőforrások](../../fin-ops-core/dev-itpro/lifecycle-services/lcs.md).</span><span class="sxs-lookup"><span data-stu-id="827cc-115">For more information, see [Lifecycle Services resources](../../fin-ops-core/dev-itpro/lifecycle-services/lcs.md).</span></span>

### <a name="prerequisites"></a><span data-ttu-id="827cc-116">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="827cc-116">Prerequisites</span></span>

<span data-ttu-id="827cc-117">A Készlet láthatósága bővítmény telepítése előtt a következőket kell tennie:</span><span class="sxs-lookup"><span data-stu-id="827cc-117">Before you install the Inventory Visibility Add-in, you must do the following:</span></span>

- <span data-ttu-id="827cc-118">Szerezzen be egy LCS-megvalósítási projektet legalább egy üzembe helyezett környezettel.</span><span class="sxs-lookup"><span data-stu-id="827cc-118">Obtain an LCS implementation project with at least one environment deployed.</span></span>
- <span data-ttu-id="827cc-119">Győződjön meg arról, hogy be vannak fejezve a [Bővítmények áttekintése](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md) részben megadott bővítmények beállításának előfeltételei.</span><span class="sxs-lookup"><span data-stu-id="827cc-119">Make sure that the prerequisites for setting up add-ins provided in the [Add-ins overview](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md) have been completed.</span></span> <span data-ttu-id="827cc-120">A Készlet láthatósága nem igényel kettős írású csatolást.</span><span class="sxs-lookup"><span data-stu-id="827cc-120">Inventory Visibility doesn't require dual-write linking.</span></span>
- <span data-ttu-id="827cc-121">Lépjen kapcsolatba a Készlet láthatósági csapatával [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) a következő három szükséges fájl beszerzéséhez:</span><span class="sxs-lookup"><span data-stu-id="827cc-121">Contact the Inventory Visibility Team at [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) to get the following three required files:</span></span>
    - `Inventory Visibility Dataverse Solution.zip`
    - `Inventory Visibility Configuration Trigger.zip`
    - <span data-ttu-id="827cc-122">`Inventory Visibility Integration.zip` (ha a Supply Chain Management által futtatott verzió korábbi, mint a 10.0.18)</span><span class="sxs-lookup"><span data-stu-id="827cc-122">`Inventory Visibility Integration.zip` (if the version of Supply Chain Management that you're running is earlier than version 10.0.18)</span></span>
- <span data-ttu-id="827cc-123">Kövesse az itt megadott utasításokat: [Rövid útmutató: Alkalmazások regisztrálása a Microsoft Identity platformmal](/azure/active-directory/develop/quickstart-register-app), hogy regisztráljon egy alkalmazást, és adjon hozzá egy ügyféltitkot az AAD-hez az Azure-előfizetés alatt.</span><span class="sxs-lookup"><span data-stu-id="827cc-123">Follow the instructions given in [Quickstart: Register an application with the Microsoft identity platform](/azure/active-directory/develop/quickstart-register-app) to register an application and add a client secret to AAD under your azure subscription.</span></span>
    - [<span data-ttu-id="827cc-124">Alkalmazás regisztrálása</span><span class="sxs-lookup"><span data-stu-id="827cc-124">Register an application</span></span>](/azure/active-directory/develop/quickstart-register-app)
    - [<span data-ttu-id="827cc-125">Titkos ügyfélkód hozzáadása</span><span class="sxs-lookup"><span data-stu-id="827cc-125">Add a client secret</span></span>](/azure/active-directory/develop/quickstart-register-app#add-a-certificate)
    - <span data-ttu-id="827cc-126">Az **alkalmazás(ügyfél) azonosítója**, az **ügyfél titkos azonosítója** és a **bérlőazonosító** a következő lépésekben lesz használva.</span><span class="sxs-lookup"><span data-stu-id="827cc-126">The **Application(Client) Id**, **Client Secret** and **Tenant ID** will be used in the following steps.</span></span>

> [!NOTE]
> <span data-ttu-id="827cc-127">A jelenleg támogatott országok és régiók: Kanada, az Egyesült Államok és az Európai Unió (EU).</span><span class="sxs-lookup"><span data-stu-id="827cc-127">The currently supported countries and regions include Canada, the United States, and the European Union (EU).</span></span>

<span data-ttu-id="827cc-128">Ha bármilyen kérdése van ezekkel az előfeltételekkel kapcsolatban, kérjük, forduljon a Készlet láthatósága termékcsapatához.</span><span class="sxs-lookup"><span data-stu-id="827cc-128">If you have any questions about these prerequisites, please contact the Inventory Visibility product team.</span></span>

### <a name="set-up-dataverse"></a><a name="setup-microsoft-dataverse"></a><span data-ttu-id="827cc-129">Dataverse beállítása</span><span class="sxs-lookup"><span data-stu-id="827cc-129">Set up Dataverse</span></span>

<span data-ttu-id="827cc-130">A Dataverse beállításához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="827cc-130">Follow these steps to set up Dataverse.</span></span>

1. <span data-ttu-id="827cc-131">Adjon hozzá egy szolgáltatási elvet a bérlőhöz:</span><span class="sxs-lookup"><span data-stu-id="827cc-131">Add a service principle to your tenant:</span></span>

    1. <span data-ttu-id="827cc-132">Telepítse az Azure AD PowerShell modul v2 verzióját az [Azure Active Directory PowerShell for Graph telepítése](/powershell/azure/active-directory/install-adv2) részben leírtak szerint.</span><span class="sxs-lookup"><span data-stu-id="827cc-132">Install Azure AD PowerShell Module v2 as described in [Install Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).</span></span>
    1. <span data-ttu-id="827cc-133">Futtassa a következő PowerShell-parancsot.</span><span class="sxs-lookup"><span data-stu-id="827cc-133">Run the following PowerShell command.</span></span>

        ```powershell
        Connect-AzureAD # (open a sign in window and sign in as a tenant user)

        New-AzureADServicePrincipal -AppId "3022308a-b9bd-4a18-b8ac-2ddedb2075e1" -DisplayName "d365-scm-inventoryservice"
        ```

1. <span data-ttu-id="827cc-134">Hozzon létre egy alkalmazásfelhasználót a Készlet láthatósága számára a Dataverse rendszerben:</span><span class="sxs-lookup"><span data-stu-id="827cc-134">Create an application user for Inventory Visibility in Dataverse:</span></span>

    1. <span data-ttu-id="827cc-135">Nyissa meg a Dataverse környezete URL-címét.</span><span class="sxs-lookup"><span data-stu-id="827cc-135">Open the URL of your Dataverse environment.</span></span>
    1. <span data-ttu-id="827cc-136">Lépjen a **Speciális beállítások \> Rendszer \> Biztonság \> Felhasználók** lehetőségre, és hozzon létre egy alkalmazásfelhasználót.</span><span class="sxs-lookup"><span data-stu-id="827cc-136">Go to **Advanced Setting \> System \> Security \> Users**, and create an application user.</span></span> <span data-ttu-id="827cc-137">A nézet menü használatával módosítsa az oldal nézetét az **Alkalmazásfelhasználók** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="827cc-137">Use the view menu to change the page view to **Application Users**.</span></span>
    1. <span data-ttu-id="827cc-138">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="827cc-138">Select **New**.</span></span> <span data-ttu-id="827cc-139">Állítsa az alkalmazásazonosítót a *3022308a-b9bd-4a18-b8ac-2ddedb2075e1* értékre.</span><span class="sxs-lookup"><span data-stu-id="827cc-139">Set the application ID to *3022308a-b9bd-4a18-b8ac-2ddedb2075e1*.</span></span> <span data-ttu-id="827cc-140">(Az objektumazonosító azonnal betöltődik, amint menti a módosításokat.) A nevet testreszabhatja.</span><span class="sxs-lookup"><span data-stu-id="827cc-140">(The object ID will automatically be loaded when you save your changes.) You can customize the name.</span></span> <span data-ttu-id="827cc-141">Például a *Készlet láthatósága* értékre módosíthatja.</span><span class="sxs-lookup"><span data-stu-id="827cc-141">For example, you can change it to *Inventory Visibility*.</span></span> <span data-ttu-id="827cc-142">Amikor elkészült, válassza a **Mentés** elemet.</span><span class="sxs-lookup"><span data-stu-id="827cc-142">When you've finished, select **Save**.</span></span>
    1. <span data-ttu-id="827cc-143">Válassza a **Szerepkör hozzárendelése**, majd a **Rendszergazda** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="827cc-143">Select **Assign Role**, and then select **System Administrator**.</span></span> <span data-ttu-id="827cc-144">Ha van **Common Data Service-felhasználó** nevű szerepkör, válassza ki azt is.</span><span class="sxs-lookup"><span data-stu-id="827cc-144">If there is a role that is named **Common Data Service User**, select it too.</span></span>

    <span data-ttu-id="827cc-145">További tudnivalókért lásd: [Alkalmazásfelhasználó létrehozása](/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user).</span><span class="sxs-lookup"><span data-stu-id="827cc-145">For more information, see [Create an application user](/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user).</span></span>

1. <span data-ttu-id="827cc-146">Ha a Dataverse alapértelmezett nyelve nem az **angol**:</span><span class="sxs-lookup"><span data-stu-id="827cc-146">If the default language of your Dataverse is not **English**:</span></span>

    1. <span data-ttu-id="827cc-147">Ugrás ide: **Speciális beállítások \> Adminisztráció \> Nyelvek**.</span><span class="sxs-lookup"><span data-stu-id="827cc-147">Go to **Advanced Setting \> Administration \> Languages**,</span></span>
    1. <span data-ttu-id="827cc-148">Válassza az **Angol (LanguageCode=1033)**, és az **Alkalmaz** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="827cc-148">Select **English (LanguageCode=1033)** and select **Apply**.</span></span>

1. <span data-ttu-id="827cc-149">Importálja az `Inventory Visibility Dataverse Solution.zip` fájlt, amely a Dataverse-konfigurációhoz kapcsolódó entitásokat és Power Apps-alkalmazásokat tartalmazza:</span><span class="sxs-lookup"><span data-stu-id="827cc-149">Import the `Inventory Visibility Dataverse Solution.zip` file, which includes Dataverse configuration related entities and Power Apps:</span></span>

    1. <span data-ttu-id="827cc-150">Lépjen a **Megoldások** oldalra.</span><span class="sxs-lookup"><span data-stu-id="827cc-150">Go to the **Solutions** page.</span></span>
    1. <span data-ttu-id="827cc-151">Válassza az **Importálás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="827cc-151">Select **Import**.</span></span>

1. <span data-ttu-id="827cc-152">A konfigurációfrissítés indító folyamatának importálása:</span><span class="sxs-lookup"><span data-stu-id="827cc-152">Import the configuration upgrade trigger flow:</span></span>

    1. <span data-ttu-id="827cc-153">Lépjen a Microsoft Flow oldalra.</span><span class="sxs-lookup"><span data-stu-id="827cc-153">Go to the Microsoft Flow page.</span></span>
    1. <span data-ttu-id="827cc-154">Győződjön meg róla, hogy az elnevezett *Dataverse (örökölt)* kapcsolat létezik.</span><span class="sxs-lookup"><span data-stu-id="827cc-154">Make sure that the connection that is named *Dataverse (legacy)* exists.</span></span> <span data-ttu-id="827cc-155">(Ha nem létezik, hozza létre.)</span><span class="sxs-lookup"><span data-stu-id="827cc-155">(If it doesn't exist, create it.)</span></span>
    1. <span data-ttu-id="827cc-156">Importálja az `Inventory Visibility Configuration Trigger.zip` fájlt.</span><span class="sxs-lookup"><span data-stu-id="827cc-156">Import the `Inventory Visibility Configuration Trigger.zip` file.</span></span> <span data-ttu-id="827cc-157">Importálás után az eseményindító a **Saját folyamatok** alatt jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="827cc-157">After it's imported, the trigger will appear under **My flows**.</span></span>
    1. <span data-ttu-id="827cc-158">Inicializálja a következő négy változót a környezeti adatok alapján:</span><span class="sxs-lookup"><span data-stu-id="827cc-158">Initialize the following four variables, based on the environment information:</span></span>

        - <span data-ttu-id="827cc-159">Azure-bérlő azonosítója</span><span class="sxs-lookup"><span data-stu-id="827cc-159">Azure Tenant ID</span></span>
        - <span data-ttu-id="827cc-160">Azure-alkalmazásügyfél azonosítója</span><span class="sxs-lookup"><span data-stu-id="827cc-160">Azure Application Client ID</span></span>
        - <span data-ttu-id="827cc-161">Azure-alkalmazásügyfél titkos kódja</span><span class="sxs-lookup"><span data-stu-id="827cc-161">Azure Application Client Secret</span></span>
        - <span data-ttu-id="827cc-162">Készletláthatósági végpont</span><span class="sxs-lookup"><span data-stu-id="827cc-162">Inventory Visibility Endpoint</span></span>

            <span data-ttu-id="827cc-163">Erről a változóról a témakör későbbi, [A készlet láthatóságának beállítása](#setup-inventory-visibility-integration) című szakasza nyújt további tájékoztatást.</span><span class="sxs-lookup"><span data-stu-id="827cc-163">For more information about this variable, see the [Set up Inventory Visibility integration](#setup-inventory-visibility-integration) section later in this topic.</span></span>

        <span data-ttu-id="827cc-164">![Konfiguráció eseményindítója](media/configuration-trigger.png "Konfiguráció eseményindítója")</span><span class="sxs-lookup"><span data-stu-id="827cc-164">![Configuration trigger](media/configuration-trigger.png "Configuration trigger")</span></span>

    1. <span data-ttu-id="827cc-165">Válassza a **Bekapcsolás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="827cc-165">Select **Turn on**.</span></span>

### <a name="install-the-add-in"></a><a name="install-add-in"></a><span data-ttu-id="827cc-166">Telepítse a bővítményt</span><span class="sxs-lookup"><span data-stu-id="827cc-166">Install the add-in</span></span>

<span data-ttu-id="827cc-167">A Készlet láthatósága bővítmény telepítéséhez a következőket kell tennie:</span><span class="sxs-lookup"><span data-stu-id="827cc-167">To install the Inventory Visibility Add-in, do the following:</span></span>

1. <span data-ttu-id="827cc-168">Jelentkezzen be a [Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index) portálra.</span><span class="sxs-lookup"><span data-stu-id="827cc-168">Sign in to the [Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index) portal.</span></span>
1. <span data-ttu-id="827cc-169">A kezdőlapon válassza ki azt a projektet, amelyben a környezet telepítve van.</span><span class="sxs-lookup"><span data-stu-id="827cc-169">On the home page, select the project where your environment is deployed.</span></span>
1. <span data-ttu-id="827cc-170">A projekt oldalon jelölje ki azt a környezetet, amelyben telepíteni szeretné a bővítményt.</span><span class="sxs-lookup"><span data-stu-id="827cc-170">On the project page, select the environment where you want to install the add-in.</span></span>
1. <span data-ttu-id="827cc-171">A környezeti oldalon görgessen lefelé, amíg meg nem látja a **Környezeti bővítmények** szakaszt a **Power Platform-integráció** szakaszban, ahol a Dataverse-környezet neve található.</span><span class="sxs-lookup"><span data-stu-id="827cc-171">On the environment page, scroll down until you see the **Environment add-ins** section in the **Power Platform integration** section, where you can find the Dataverse environment name.</span></span>
1. <span data-ttu-id="827cc-172">A **Környezeti bővítmények** szakaszban válassza az **Új bővítmény telepítése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="827cc-172">In the **Environment add-ins** section, select **Install a new add-in**.</span></span>

    <span data-ttu-id="827cc-173">![A környezeti oldal az LCS-ben](media/inventory-visibility-environment.png "A környezeti oldal az LCS-ben")</span><span class="sxs-lookup"><span data-stu-id="827cc-173">![The environment page in LCS](media/inventory-visibility-environment.png "The environment page in LCS")</span></span>

1. <span data-ttu-id="827cc-174">Válassza az **Új bővítmény telepítése** hivatkozást.</span><span class="sxs-lookup"><span data-stu-id="827cc-174">Select the **Install a new add-in** link.</span></span> <span data-ttu-id="827cc-175">Megnyílik az elérhető bővítmények listája.</span><span class="sxs-lookup"><span data-stu-id="827cc-175">A list of available add-ins opens.</span></span>
1. <span data-ttu-id="827cc-176">A listában válassza a **Készletláthatóság** elemet.</span><span class="sxs-lookup"><span data-stu-id="827cc-176">Select **Inventory Visibility** in the list.</span></span>
1. <span data-ttu-id="827cc-177">Adja meg a környezet alábbi mezőinek értékeit:</span><span class="sxs-lookup"><span data-stu-id="827cc-177">Enter values for the following fields for your environment:</span></span>

    - <span data-ttu-id="827cc-178">**AAD-alkalmazás (ügyfél) azonosítója**</span><span class="sxs-lookup"><span data-stu-id="827cc-178">**AAD application (client) ID**</span></span>
    - <span data-ttu-id="827cc-179">**AAD bérlő azonosítója**</span><span class="sxs-lookup"><span data-stu-id="827cc-179">**AAD tenant ID**</span></span>

    <span data-ttu-id="827cc-180">![Hozzáadás a beállítási lapon](media/inventory-visibility-setup.png "Hozzáadás a beállítási lapon")</span><span class="sxs-lookup"><span data-stu-id="827cc-180">![Add in setup page](media/inventory-visibility-setup.png "Add-in setup page")</span></span>

1. <span data-ttu-id="827cc-181">Fogadja el a feltételeket az **Általános Szerződési feltételek** jelölőnégyzet bejelölésével.</span><span class="sxs-lookup"><span data-stu-id="827cc-181">Agree to the terms and condition by selecting the **Terms and conditions** check box.</span></span>
1. <span data-ttu-id="827cc-182">Válassza a **Telepítés** parancsot.</span><span class="sxs-lookup"><span data-stu-id="827cc-182">Select **Install**.</span></span> <span data-ttu-id="827cc-183">A bővítmény állapota **Telepítés** értékkel jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="827cc-183">The status of the add-in will show as **Installing**.</span></span> <span data-ttu-id="827cc-184">Ha befejeződött, frissítse a lapot, hogy lássa, ahogy a **Telepített** állapotra változik.</span><span class="sxs-lookup"><span data-stu-id="827cc-184">When it's done, refresh the page to see the status change to **Installed**.</span></span>

### <a name="uninstall-the-add-in"></a><a name="uninstall-add-in"></a><span data-ttu-id="827cc-185">A bővítmény eltávolítása</span><span class="sxs-lookup"><span data-stu-id="827cc-185">Uninstall the add-in</span></span>

<span data-ttu-id="827cc-186">A bővítmény eltávolításához válassza az **Eltávolítás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="827cc-186">To uninstall the add-in, select **Uninstall**.</span></span> <span data-ttu-id="827cc-187">Az LCS frissítésekor a Készlet láthatósága bővítmény törlődik.</span><span class="sxs-lookup"><span data-stu-id="827cc-187">When you refresh LCS, the Inventory Visibility Add-in will be removed.</span></span> <span data-ttu-id="827cc-188">Az eltávolítási folyamat eltávolítja a bővítmény regisztrációját, és elindít egy feladatot a szolgáltatásban tárolt összes üzleti adat törléséhez.</span><span class="sxs-lookup"><span data-stu-id="827cc-188">The uninstall process removes the add-in registration and also starts a job to clean up all the business data that is stored in the service.</span></span>

## <a name="consume-on-hand-inventory-data-from-supply-chain-management"></a><span data-ttu-id="827cc-189">Az aktuális készlet adatainak felhasználása a Supply Chain Management alkalmazásból</span><span class="sxs-lookup"><span data-stu-id="827cc-189">Consume on-hand inventory data from Supply Chain Management</span></span>

### <a name="deploy-the-inventory-visibility-integration-package"></a><a name="deploy-inventory-visibility-package"></a><span data-ttu-id="827cc-190">A Készlet láthatósága integrációs csomag központi telepítése</span><span class="sxs-lookup"><span data-stu-id="827cc-190">Deploy the Inventory Visibility integration package</span></span>

<span data-ttu-id="827cc-191">Ha a Supply Chain Management 10.0.17-es vagy korábbi verziója fut, a csomagfájl beszerzéséért forduljon a Készlet láthatósága támogatási csapathoz az [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) címen.</span><span class="sxs-lookup"><span data-stu-id="827cc-191">If you're running Supply Chain Management version 10.0.17 or earlier, contact the Inventory Visibility on-board support team at [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) to get the package file.</span></span> <span data-ttu-id="827cc-192">Ezután telepítse a csomagot az LCS-be.</span><span class="sxs-lookup"><span data-stu-id="827cc-192">Then deploy the package in LCS.</span></span>

> [!NOTE]
> <span data-ttu-id="827cc-193">Ha a telepítés során nem egyező verziók fordulnak elő, manuálisan kell importálnia az X++ projektet a fejlesztői környezetbe.</span><span class="sxs-lookup"><span data-stu-id="827cc-193">If a version mismatch error occurs during deployment, you must manually import the X++ project into your development environment.</span></span> <span data-ttu-id="827cc-194">Ezt követően hozza létre a telepíthető csomagot a fejlesztői környezetben, és telepítse az éles környezetben.</span><span class="sxs-lookup"><span data-stu-id="827cc-194">Then create the deployable package in your development environment, and deploy it in your production environment.</span></span>
> 
> <span data-ttu-id="827cc-195">A kód része a Supply Chain Management 10.0.18-as verziójának.</span><span class="sxs-lookup"><span data-stu-id="827cc-195">The code is included with Supply Chain Management version 10.0.18.</span></span> <span data-ttu-id="827cc-196">Ha azt a verziót vagy egy későbbi verziót futtat, nem szükséges a telepítés.</span><span class="sxs-lookup"><span data-stu-id="827cc-196">If you're running that version or later, deployment isn't required.</span></span>

<span data-ttu-id="827cc-197">Győződjön meg arról, hogy az alábbi funkciók be vannak kapcsolva a Supply Chain Management-környezetben.</span><span class="sxs-lookup"><span data-stu-id="827cc-197">Make sure that the following features are turned on in your Supply Chain Management environment.</span></span> <span data-ttu-id="827cc-198">(Alapértelmezés szerint be vannak kapcsolva.)</span><span class="sxs-lookup"><span data-stu-id="827cc-198">(By default, they are turned on.)</span></span>

| <span data-ttu-id="827cc-199">Funkció leírása</span><span class="sxs-lookup"><span data-stu-id="827cc-199">Feature description</span></span> | <span data-ttu-id="827cc-200">Kódverzió</span><span class="sxs-lookup"><span data-stu-id="827cc-200">Code version</span></span> | <span data-ttu-id="827cc-201">Osztály váltása</span><span class="sxs-lookup"><span data-stu-id="827cc-201">Toggle class</span></span> |
|---|---|---|
| <span data-ttu-id="827cc-202">Készletdimenziók használatának engedélyezése vagy letiltása az InventSum táblán</span><span class="sxs-lookup"><span data-stu-id="827cc-202">Enable or disable using inventory dimensions on InventSum table</span></span> | <span data-ttu-id="827cc-203">10.0.11</span><span class="sxs-lookup"><span data-stu-id="827cc-203">10.0.11</span></span> | <span data-ttu-id="827cc-204">InventUseDimOfInventSumToggle</span><span class="sxs-lookup"><span data-stu-id="827cc-204">InventUseDimOfInventSumToggle</span></span> |
| <span data-ttu-id="827cc-205">Készletdimenziók használatának engedélyezése vagy letiltása az InventSumDelta táblán</span><span class="sxs-lookup"><span data-stu-id="827cc-205">Enable or disable using inventory dimensions on InventSumDelta table</span></span> | <span data-ttu-id="827cc-206">10.0.12</span><span class="sxs-lookup"><span data-stu-id="827cc-206">10.0.12</span></span> | <span data-ttu-id="827cc-207">InventUseDimOfInventSumDeltaToggle</span><span class="sxs-lookup"><span data-stu-id="827cc-207">InventUseDimOfInventSumDeltaToggle</span></span> |

### <a name="set-up-inventory-visibility-integration"></a><a name="setup-inventory-visibility-integration"></a><span data-ttu-id="827cc-208">Készletláthatósági integráció beállítása</span><span class="sxs-lookup"><span data-stu-id="827cc-208">Set up Inventory Visibility integration</span></span>

1. <span data-ttu-id="827cc-209">A Supply Chain Management alkalmazásban nyissa meg a **[Szolgáltatáskezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)** munkaterületet, és kapcsolja be a **Készlet láthatósági integrációja** funkciót.</span><span class="sxs-lookup"><span data-stu-id="827cc-209">In Supply Chain Management, open the **[Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)** workspace, and turn on the **Inventory Visibility Integration** feature.</span></span>
1. <span data-ttu-id="827cc-210">Lépjen a **Készletkezelés \> Beállítás \> Készlet láthatósági integrációjának paraméterei** lehetőségre, és adja meg annak a környezetnek az URL-címét, ahol a Készlet láthatóságát futtatja.</span><span class="sxs-lookup"><span data-stu-id="827cc-210">Go to **Inventory Management \> Set up \> Inventory Visibility Integration parameters**, and enter the URL of the environment where you're running Inventory Visibility.</span></span>

    <span data-ttu-id="827cc-211">Keresse meg az LCS-környezet Azure-régióját, majd adja meg az URL-címet.</span><span class="sxs-lookup"><span data-stu-id="827cc-211">Find your LCS environment's Azure region, and then enter the URL.</span></span> <span data-ttu-id="827cc-212">Az URL-cím a következő képernyőt tartalmazza:</span><span class="sxs-lookup"><span data-stu-id="827cc-212">The URL has the following form:</span></span>

    `https://inventoryservice.<RegionShortName>-il301.gateway.prod.island.powerapps.com`

    <span data-ttu-id="827cc-213">Ha például Európában van, a környezete a következő URL-címek valamelyikét fogja tartalmazni:</span><span class="sxs-lookup"><span data-stu-id="827cc-213">For example, if you're in Europe, your environment will have one of the following URLs:</span></span>

    - `https://inventoryservice.neu-il301.gateway.prod.island.powerapps.com`
    - `https://inventoryservice.weu-il301.gateway.prod.island.powerapps.com`

    <span data-ttu-id="827cc-214">Jelenleg a következő régiók állnak rendelkezésre.</span><span class="sxs-lookup"><span data-stu-id="827cc-214">The following regions are currently available.</span></span>

    | <span data-ttu-id="827cc-215">Azure-régió</span><span class="sxs-lookup"><span data-stu-id="827cc-215">Azure region</span></span> | <span data-ttu-id="827cc-216">Régió rövid neve</span><span class="sxs-lookup"><span data-stu-id="827cc-216">Region short name</span></span> |
    |---|---|
    | <span data-ttu-id="827cc-217">Kelet-Ausztrália</span><span class="sxs-lookup"><span data-stu-id="827cc-217">Australia east</span></span> | <span data-ttu-id="827cc-218">eau</span><span class="sxs-lookup"><span data-stu-id="827cc-218">eau</span></span> |
    | <span data-ttu-id="827cc-219">Délkelet-Ausztrália</span><span class="sxs-lookup"><span data-stu-id="827cc-219">Australia southeast</span></span> | <span data-ttu-id="827cc-220">seau</span><span class="sxs-lookup"><span data-stu-id="827cc-220">seau</span></span> |
    | <span data-ttu-id="827cc-221">Közép-Kanada</span><span class="sxs-lookup"><span data-stu-id="827cc-221">Canada central</span></span> | <span data-ttu-id="827cc-222">cca</span><span class="sxs-lookup"><span data-stu-id="827cc-222">cca</span></span> |
    | <span data-ttu-id="827cc-223">Kelet-Kanada</span><span class="sxs-lookup"><span data-stu-id="827cc-223">Canada east</span></span> | <span data-ttu-id="827cc-224">eca</span><span class="sxs-lookup"><span data-stu-id="827cc-224">eca</span></span> |
    | <span data-ttu-id="827cc-225">Észak-Európa</span><span class="sxs-lookup"><span data-stu-id="827cc-225">North Europe</span></span> | <span data-ttu-id="827cc-226">neu</span><span class="sxs-lookup"><span data-stu-id="827cc-226">neu</span></span> |
    | <span data-ttu-id="827cc-227">Nyugat-Európa</span><span class="sxs-lookup"><span data-stu-id="827cc-227">West Europe</span></span> | <span data-ttu-id="827cc-228">weu</span><span class="sxs-lookup"><span data-stu-id="827cc-228">weu</span></span> |
    | <span data-ttu-id="827cc-229">USA keleti régiója</span><span class="sxs-lookup"><span data-stu-id="827cc-229">East US</span></span> | <span data-ttu-id="827cc-230">eus</span><span class="sxs-lookup"><span data-stu-id="827cc-230">eus</span></span> |
    | <span data-ttu-id="827cc-231">USA nyugati régiója</span><span class="sxs-lookup"><span data-stu-id="827cc-231">West US</span></span> | <span data-ttu-id="827cc-232">wus</span><span class="sxs-lookup"><span data-stu-id="827cc-232">wus</span></span> |

1. <span data-ttu-id="827cc-233">Lépjen a **Készletkezelés \> Időszakos \> Készlet láthatósági integrációja** elemre, és engedélyezze a feladatot.</span><span class="sxs-lookup"><span data-stu-id="827cc-233">Go to **Inventory Management \> Periodic \> Inventory Visibility Integration**, and enable the job.</span></span> <span data-ttu-id="827cc-234">A rendszer a Supply Chain Management minden készletváltozási eseményét feladja a Készlet láthatósága számára.</span><span class="sxs-lookup"><span data-stu-id="827cc-234">All inventory change events from Supply Chain Management will now be posted to Inventory Visibility.</span></span>

## <a name="the-inventory-visibility-add-in-public-api"></a><a name="inventory-visibility-public-api"></a><span data-ttu-id="827cc-235">A Készlet láthatósága bővítmény nyilvános API-je</span><span class="sxs-lookup"><span data-stu-id="827cc-235">The Inventory Visibility Add-in public API</span></span>

<span data-ttu-id="827cc-236">A Készlet láthatósága bővítmény nyilvános REST API-ja az integráció több konkrét végpontját mutatja be.</span><span class="sxs-lookup"><span data-stu-id="827cc-236">The public REST API of the Inventory Visibility Add-in presents several specific endpoints for integration.</span></span> <span data-ttu-id="827cc-237">Három fő interakciós típust támogat:</span><span class="sxs-lookup"><span data-stu-id="827cc-237">It supports three main interaction types:</span></span>

- <span data-ttu-id="827cc-238">A bővítmény aktuális készletmódosításainak külső rendszerből történő feladása</span><span class="sxs-lookup"><span data-stu-id="827cc-238">Posting on-hand inventory changes to the add-in from an external system</span></span>
- <span data-ttu-id="827cc-239">Aktuális rendelkezésre álló mennyiségek lekérdezése külső rendszerből</span><span class="sxs-lookup"><span data-stu-id="827cc-239">Querying current on-hand quantities from an external system</span></span>
- <span data-ttu-id="827cc-240">Automatikus szinkronizálás a Supply Chain Management aktuális készletével</span><span class="sxs-lookup"><span data-stu-id="827cc-240">Automatic synchronization with Supply Chain Management on-hand inventory</span></span>

<span data-ttu-id="827cc-241">Az automatikus szinkronizálás nem része a nyilvános API-nak.</span><span class="sxs-lookup"><span data-stu-id="827cc-241">Automatic synchronization isn't part of the public API.</span></span> <span data-ttu-id="827cc-242">Ehelyett a rendszer a háttérben kezeli olyan környezetekben, ahol engedélyezve van a Készlet láthatósága bővítmény.</span><span class="sxs-lookup"><span data-stu-id="827cc-242">Instead, it's handled in the background for environments where the Inventory Visibility Add-in is enabled.</span></span>

### <a name="authentication"></a><a name="inventory-visibility-authentication"></a><span data-ttu-id="827cc-243">Hitelesítés</span><span class="sxs-lookup"><span data-stu-id="827cc-243">Authentication</span></span>

<span data-ttu-id="827cc-244">A platform biztonsági tokenje a Készlet láthatósága bővítmény hívására használatos.</span><span class="sxs-lookup"><span data-stu-id="827cc-244">The platform security token is used to call the Inventory Visibility Add-in.</span></span> <span data-ttu-id="827cc-245">Emiatt az Azure AD-alkalmazás használatával létre kell hozni egy *Azure Active Directory (Azure AD) tokent*.</span><span class="sxs-lookup"><span data-stu-id="827cc-245">Therefore, you must generate an *Azure Active Directory (Azure AD) token* by using your Azure AD application.</span></span> <span data-ttu-id="827cc-246">Ezt követően az Azure AD-tokent kell ahhoz használnia, hogy a *hozzáférési tokent* be tudja szerezni a biztonsági szolgáltatásból.</span><span class="sxs-lookup"><span data-stu-id="827cc-246">You must then use the Azure AD token to get the *access token* from the security service.</span></span>

<span data-ttu-id="827cc-247">Biztonsági szolgáltatás jogkivonatának beszerzéséhez tegye a következőket:</span><span class="sxs-lookup"><span data-stu-id="827cc-247">Get a security service token by doing the following:</span></span>

1. <span data-ttu-id="827cc-248">Jelentkezzen be az Azure Portal webhelyre, és használja a `clientId` és `clientSecret` keresésére a Supply Chain Management alkalmazáshoz.</span><span class="sxs-lookup"><span data-stu-id="827cc-248">Sign in to Azure portal and use it to find the `clientId` and `clientSecret` for your Supply Chain Management application.</span></span>
1. <span data-ttu-id="827cc-249">Azure Active Directory kód beolvasása (`aadToken`) a következő tulajdonságokkal rendelkező HTTP-kérés beküldésével:</span><span class="sxs-lookup"><span data-stu-id="827cc-249">Fetch an Azure Active Directory token (`aadToken`) by submitting an HTTP request with the following properties:</span></span>
    - <span data-ttu-id="827cc-250">**URL-cím** - `https://login.microsoftonline.com/${aadTenantId}/oauth2/token`</span><span class="sxs-lookup"><span data-stu-id="827cc-250">**URL** - `https://login.microsoftonline.com/${aadTenantId}/oauth2/token`</span></span>
    - <span data-ttu-id="827cc-251">**Metódus** - `GET`</span><span class="sxs-lookup"><span data-stu-id="827cc-251">**Method** - `GET`</span></span>
    - <span data-ttu-id="827cc-252">**Levél tartalma (űrlapadatok)**:</span><span class="sxs-lookup"><span data-stu-id="827cc-252">**Body content (form data)**:</span></span>

        | <span data-ttu-id="827cc-253">kulcs</span><span class="sxs-lookup"><span data-stu-id="827cc-253">key</span></span> | <span data-ttu-id="827cc-254">érték</span><span class="sxs-lookup"><span data-stu-id="827cc-254">value</span></span> |
        | --- | --- |
        | <span data-ttu-id="827cc-255">ügyfél azonosítója</span><span class="sxs-lookup"><span data-stu-id="827cc-255">client_id</span></span> | <span data-ttu-id="827cc-256">${aadAppId}</span><span class="sxs-lookup"><span data-stu-id="827cc-256">${aadAppId}</span></span> |
        | <span data-ttu-id="827cc-257">titkos ügyfélkód</span><span class="sxs-lookup"><span data-stu-id="827cc-257">client_secret</span></span> | <span data-ttu-id="827cc-258">${aadAppSecret}</span><span class="sxs-lookup"><span data-stu-id="827cc-258">${aadAppSecret}</span></span> |
        | <span data-ttu-id="827cc-259">engedélyezési típus</span><span class="sxs-lookup"><span data-stu-id="827cc-259">grant_type</span></span> | <span data-ttu-id="827cc-260">ügyfél_azonosító adatai</span><span class="sxs-lookup"><span data-stu-id="827cc-260">client_credentials</span></span> |
        | <span data-ttu-id="827cc-261">erőforrás</span><span class="sxs-lookup"><span data-stu-id="827cc-261">resource</span></span> | <span data-ttu-id="827cc-262">0cdb527f-a8d1-4bf8-9436-b352c68682b2</span><span class="sxs-lookup"><span data-stu-id="827cc-262">0cdb527f-a8d1-4bf8-9436-b352c68682b2</span></span> |
1. <span data-ttu-id="827cc-263">Válaszként egy `aadToken` kódot kell kapnia, amelynek a következő példához kell hasonlítania.</span><span class="sxs-lookup"><span data-stu-id="827cc-263">You should receive an `aadToken` in response, which resembles the following example.</span></span>

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

1. <span data-ttu-id="827cc-264">Fogalmazzon meg egy olyan JSON-kérést, amely hasonlít a következőkre:</span><span class="sxs-lookup"><span data-stu-id="827cc-264">Formulate a JSON request that resembles the following:</span></span>

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

    <span data-ttu-id="827cc-265">Ahol:</span><span class="sxs-lookup"><span data-stu-id="827cc-265">Where:</span></span>
    - <span data-ttu-id="827cc-266">A `client_assertion` értéknek az előző lépésben kapott `aadToken` értéknek kell lennie.</span><span class="sxs-lookup"><span data-stu-id="827cc-266">The `client_assertion` value must be the `aadToken` you received in the previous step.</span></span>
    - <span data-ttu-id="827cc-267">A `context` érték az a környezetazonosító, ahová telepíteni szeretné a bővítményt.</span><span class="sxs-lookup"><span data-stu-id="827cc-267">The `context` value must be the environment ID where you want to deploy the add-in.</span></span>
    - <span data-ttu-id="827cc-268">Állítsa be az összes többi értéket a példában látható módon.</span><span class="sxs-lookup"><span data-stu-id="827cc-268">Set all of other values as shown in the example.</span></span>

1. <span data-ttu-id="827cc-269">HTTP-kérés küldése a következő tulajdonságokkal:</span><span class="sxs-lookup"><span data-stu-id="827cc-269">Submit an HTTP request with the following properties:</span></span>
    - <span data-ttu-id="827cc-270">**URL-cím** - `https://securityservice.operations365.dynamics.com/token`</span><span class="sxs-lookup"><span data-stu-id="827cc-270">**URL** - `https://securityservice.operations365.dynamics.com/token`</span></span>
    - <span data-ttu-id="827cc-271">**Metódus** - `POST`</span><span class="sxs-lookup"><span data-stu-id="827cc-271">**Method** - `POST`</span></span>
    - <span data-ttu-id="827cc-272">**HTTP-fejléc** – tartalmazza az API-verziót (a kulcs `Api-Version` és az érték: `1.0`)</span><span class="sxs-lookup"><span data-stu-id="827cc-272">**HTTP header** - Include the API version (key is `Api-Version` and value is `1.0`)</span></span>
    - <span data-ttu-id="827cc-273">**Levél tartalma** – foglalja bele az előző lépésben létrehozott JSON-kérelmet.</span><span class="sxs-lookup"><span data-stu-id="827cc-273">**Body content** - Include the JSON request that you created in the previous step.</span></span>

1. <span data-ttu-id="827cc-274">Kap egy `access_token` elemet válaszul.</span><span class="sxs-lookup"><span data-stu-id="827cc-274">You will get an `access_token` in response.</span></span> <span data-ttu-id="827cc-275">Ez az, amire szüksége van, mint tulajdonosi jogkivonat, hogy meghívja meg a Készlet láthatósága API-t.</span><span class="sxs-lookup"><span data-stu-id="827cc-275">This is what you need as a bearer token to call the Inventory Visibility API.</span></span> <span data-ttu-id="827cc-276">Íme, egy példa.</span><span class="sxs-lookup"><span data-stu-id="827cc-276">Here is an example.</span></span>

    ```json
    {
        "access_token": "{Returned_Token}",
        "token_type": "bearer",
        "expires_in": 1200
    }
    ```

### <a name="sample-request"></a><a name="inventory-visibility-sample-request"></a><span data-ttu-id="827cc-277">Mintakérés</span><span class="sxs-lookup"><span data-stu-id="827cc-277">Sample Request</span></span>

<span data-ttu-id="827cc-278">Referenciaként itt van egy minta HTTP-kérés, használhat a kérés elküldésére bármilyen eszközt vagy kódolási nyelvet, például ``Postman``.</span><span class="sxs-lookup"><span data-stu-id="827cc-278">For your reference, here is a sample http request, you can use any tools or coding language to send this request, such as  ``Postman``.</span></span>

```json
# Url
# replace {RegionShortName} and {EnvironmentId} with your value
https://inventoryservice.{RegionShortName}-il301.gateway.prod.island.powerapps.com/api/environment/{EnvironmentId}/onhand

# Method
Post

# Header
# replace {access_token} with the one get from security service
Api-version: "1.0"
Content-Type: "application/json"
Authorization: "Bearer {access_token}"

# Body
{
    "id": "id-bike-0001",
    "organizationId": "usmf",
    "productId": "Bike",
    "quantities": {
        "pos": {
            "inbound": 5
        }  
    },
    "dimensions": {
        "SizeId": "Small",
        "ColorId": "Red",
        "SiteId": "1",
        "LocationId": "11"
    }
}
```

### <a name="configure-the-inventory-visibility-api"></a><a name="inventory-visibility-configuration"></a><span data-ttu-id="827cc-279">A Készlet láthatósága API konfigurálása</span><span class="sxs-lookup"><span data-stu-id="827cc-279">Configure the Inventory Visibility API</span></span>

<span data-ttu-id="827cc-280">A szolgáltatás használata előtt ki kell töltenie az alábbi alszakaszokban ismertetett konfigurációkat.</span><span class="sxs-lookup"><span data-stu-id="827cc-280">Before using the service, you must complete the configurations described in the following subsections.</span></span> <span data-ttu-id="827cc-281">A konfiguráció a környezet részleteitől függően változhat.</span><span class="sxs-lookup"><span data-stu-id="827cc-281">The configuration may vary based on the details of your environment.</span></span> <span data-ttu-id="827cc-282">Ez elsősorban négy részből áll:</span><span class="sxs-lookup"><span data-stu-id="827cc-282">It primarily includes four parts:</span></span>

- [<span data-ttu-id="827cc-283">Particionálás</span><span class="sxs-lookup"><span data-stu-id="827cc-283">Partitioning</span></span>](#partitioning)
- [<span data-ttu-id="827cc-284">Dimenziókonfigurációk</span><span class="sxs-lookup"><span data-stu-id="827cc-284">Dimension configurations</span></span>](#dimension-configurations)
- [<span data-ttu-id="827cc-285">Indexelés</span><span class="sxs-lookup"><span data-stu-id="827cc-285">Indexing</span></span>](#indexing)
- [<span data-ttu-id="827cc-286">Egyéni mérés</span><span class="sxs-lookup"><span data-stu-id="827cc-286">Custom measurement</span></span>](#custom-measurement)

#### <a name="partitioning"></a><span data-ttu-id="827cc-287">Particionálás</span><span class="sxs-lookup"><span data-stu-id="827cc-287">Partitioning</span></span>

<span data-ttu-id="827cc-288">A particionálás jelentősen befolyásolhatja a Készlet láthatósága API teljesítményét.</span><span class="sxs-lookup"><span data-stu-id="827cc-288">Partitioning can significantly influence the performance of the Inventory Visibility API.</span></span> <span data-ttu-id="827cc-289">Célszerű olyan sémát definiálni, amely lehetővé teszi az adatok kis csoportjait, miközben továbbra is lehetővé teszi az értelmezhető adatlekérdezéseket.</span><span class="sxs-lookup"><span data-stu-id="827cc-289">It's a good idea to define a scheme that allows for small groupings of data while still allowing for meaningful data queries.</span></span>

<span data-ttu-id="827cc-290">Az `organizationId` (`dataAreaId` a Supply Chain Management esetében) mindig a particionálás része lesz, és alapértelmezés szerint a Készlet láthatósága dimenziók szerinti particionálásra van beállítva *Telephely + Hely* szerint.</span><span class="sxs-lookup"><span data-stu-id="827cc-290">The `organizationId` (`dataAreaId` in Supply Chain Management) will always be part of the partitioning, and by default Inventory Visibility is set to partition by dimensions as *Site + Location*.</span></span> <span data-ttu-id="827cc-291">Ez azt jelenti, hogy a szolgáltatást mindig le kell kérdezni ezekkel a szűrőkön definiált dimenziókkal.</span><span class="sxs-lookup"><span data-stu-id="827cc-291">This means that the service must always be queried with these dimensions defined on the filters.</span></span>

> [!NOTE]
> <span data-ttu-id="827cc-292">A *Telephely* és a *Hely* két általános alapértelmezett dimenzió a Készlet láthatóságában.</span><span class="sxs-lookup"><span data-stu-id="827cc-292">*Site* and *Location* are two general default dimensions in Inventory Visibility.</span></span> <span data-ttu-id="827cc-293">A Supply Chain Managementben ezeket a dimenziók *Telephely* (`InventSiteId`) és *Raktár* (`InventLocationId`) néven szerepelnek</span><span class="sxs-lookup"><span data-stu-id="827cc-293">In Supply Chain Management, those dimensions are called *Site* (`InventSiteId`) and *Warehouse* (`InventLocationId`)</span></span>

### <a name="dimension-configurations"></a><span data-ttu-id="827cc-294">Dimenziókonfigurációk</span><span class="sxs-lookup"><span data-stu-id="827cc-294">Dimension configurations</span></span>

<span data-ttu-id="827cc-295">A Készlet láthatósága az általános alapértelmezett dimenziók listáját tartalmazza a több forrásrendszer integrációjának engedélyezéséhez.</span><span class="sxs-lookup"><span data-stu-id="827cc-295">Inventory Visibility will provide a list of general default dimensions to enable the multiple source system integration.</span></span>

<span data-ttu-id="827cc-296">Az alábbi táblázat azokat a készletdimenziókat sorolja fel, amelyek a Készlet láthatósága alapértelmezett dimenziónevei lesznek.</span><span class="sxs-lookup"><span data-stu-id="827cc-296">The following table lists the inventory dimensions that will be the default dimension names in Inventory Visibility.</span></span>

| <span data-ttu-id="827cc-297">Dimenzió típusa</span><span class="sxs-lookup"><span data-stu-id="827cc-297">Dimension type</span></span> | <span data-ttu-id="827cc-298">Dimenzió neve</span><span class="sxs-lookup"><span data-stu-id="827cc-298">Dimension name</span></span> |
|---|---|
| <span data-ttu-id="827cc-299">Termék</span><span class="sxs-lookup"><span data-stu-id="827cc-299">Product</span></span> | `ColorId` |
| <span data-ttu-id="827cc-300">Termék</span><span class="sxs-lookup"><span data-stu-id="827cc-300">Product</span></span> | `SizeId` |
| <span data-ttu-id="827cc-301">Termék</span><span class="sxs-lookup"><span data-stu-id="827cc-301">Product</span></span> | `StyleId` |
| <span data-ttu-id="827cc-302">Termék</span><span class="sxs-lookup"><span data-stu-id="827cc-302">Product</span></span> | `ConfigId` |
| <span data-ttu-id="827cc-303">Nyomon követés</span><span class="sxs-lookup"><span data-stu-id="827cc-303">Tracking</span></span> | `BatchId` |
| <span data-ttu-id="827cc-304">Nyomon követés</span><span class="sxs-lookup"><span data-stu-id="827cc-304">Tracking</span></span> | `SerialId` |
| <span data-ttu-id="827cc-305">Helyszín</span><span class="sxs-lookup"><span data-stu-id="827cc-305">Location</span></span> | `LocationId` |
| <span data-ttu-id="827cc-306">Helyszín</span><span class="sxs-lookup"><span data-stu-id="827cc-306">Location</span></span> | `SiteId` |
| <span data-ttu-id="827cc-307">Készlet állapota</span><span class="sxs-lookup"><span data-stu-id="827cc-307">Inventory Status</span></span> | `StatusId` |
| <span data-ttu-id="827cc-308">Raktárspecifikus</span><span class="sxs-lookup"><span data-stu-id="827cc-308">Warehouse Specific</span></span> | `WMSLocationId` |
| <span data-ttu-id="827cc-309">Raktárspecifikus</span><span class="sxs-lookup"><span data-stu-id="827cc-309">Warehouse Specific</span></span> | `WMSPalletId` |
| <span data-ttu-id="827cc-310">Raktárspecifikus</span><span class="sxs-lookup"><span data-stu-id="827cc-310">Warehouse Specific</span></span> | `LicensePlateId` |

> [!NOTE]
> <span data-ttu-id="827cc-311">Az előző táblában felsorolt dimenziótípus csak tájékoztató jellegű.</span><span class="sxs-lookup"><span data-stu-id="827cc-311">The dimension type listed in the previous table is for reference only.</span></span> <span data-ttu-id="827cc-312">A dimenziótípust nem kell definiálnia a Készlet láthatósága bővítményben.</span><span class="sxs-lookup"><span data-stu-id="827cc-312">You don't need to define the dimension type in Inventory Visibility.</span></span>

<span data-ttu-id="827cc-313">Ha létezik egyéni dimenzió, és a Készlet láthatósága által felhasznált alapértelmezett értékre kell áramlania, az **Egyéni dimenzió** nevét a Készlet láthatóságában konfigurálhatja.</span><span class="sxs-lookup"><span data-stu-id="827cc-313">If a custom dimension exists and needs to flow to a default value when consumed by Inventory Visibility, you can configure the **Custom dimension** name in Inventory Visibility.</span></span>

<span data-ttu-id="827cc-314">A külső rendszerek RESTful API-kon keresztül férnek hozzá a Készlet láthatóságához, amelyek lehetővé teszik az adott dimenziókészletek aktuális információinak lekérdezését.</span><span class="sxs-lookup"><span data-stu-id="827cc-314">External systems access Inventory Visibility through RESTful APIs that enable on-hand information on given sets of dimensions to be queried.</span></span> <span data-ttu-id="827cc-315">Az integrációhoz a Készlet láthatósága lehetővé teszi a *külső csatorna adatforrásának* és a forrásdimenziónak a Készlet láthatósága *céldimenzióihoz* való konfigurálását.</span><span class="sxs-lookup"><span data-stu-id="827cc-315">For the integration, Inventory Visibility enables you to configure the *external channel data source* and the source dimension to the *target dimensions* in Inventory Visibility.</span></span>

<span data-ttu-id="827cc-316">A céldimenzióknak a következők egyikének kell lenniük:</span><span class="sxs-lookup"><span data-stu-id="827cc-316">The target dimensions should be one of the following:</span></span>

- <span data-ttu-id="827cc-317">Alapértelmezett dimenziók a Készlet láthatóságában</span><span class="sxs-lookup"><span data-stu-id="827cc-317">Default dimensions in Inventory Visibility</span></span>
- <span data-ttu-id="827cc-318">Egyéni dimenziók</span><span class="sxs-lookup"><span data-stu-id="827cc-318">Custom dimensions</span></span>

<span data-ttu-id="827cc-319">A dimenziókonfiguráció célja a dimenziókra irányuló lekérdezések és a dimenziókkal való feladási esemény többrendszeres integrációjának szabványosítása.</span><span class="sxs-lookup"><span data-stu-id="827cc-319">The purpose of dimension configuration is to standardize the multi-system integration for the query on dimensions and the posting event with dimensions.</span></span>

#### <a name="indexing"></a><span data-ttu-id="827cc-320">Indexelés</span><span class="sxs-lookup"><span data-stu-id="827cc-320">Indexing</span></span>

<span data-ttu-id="827cc-321">Az aktuális készlet lekérdezése a legtöbb alkalommal nem csak a legmagasabb "teljes" szinten lesz, de előfordulhat, hogy a készletdimenziók alapján összesítve szeretné látni az eredményeket.</span><span class="sxs-lookup"><span data-stu-id="827cc-321">Most of the time, the inventory on-hand query will not only be on the highest "total" level, but you may want to see results aggregated based on the inventory dimensions.</span></span>

<span data-ttu-id="827cc-322">A Készlet láthatósága rugalmasságot biztosít azáltal, hogy lehetővé teszi az indexek beállítását, amelyek a dimenzión vagy a dimenziók kombinációján alapulnak.</span><span class="sxs-lookup"><span data-stu-id="827cc-322">Inventory Visibility provides flexibility by allowing you to set up the indexes, which are based on the dimension or the combination of the dimensions.</span></span>

> [!NOTE]
> <span data-ttu-id="827cc-323">Jelenleg csak legfeljebb öt indexet konfigurálhat.</span><span class="sxs-lookup"><span data-stu-id="827cc-323">Currently, you can only configure indexes to a maximum of five.</span></span> <span data-ttu-id="827cc-324">Alaposan meg kell fontolnia, hogy melyik dimenziót vagy dimenziókombinációt fogja használni a megvalósítás előtt annak érdekében, hogy megfeleljen az üzleti igényeinek.</span><span class="sxs-lookup"><span data-stu-id="827cc-324">You need to carefully consider which dimension or dimension combination you will use before the implementation to ensure that it will meet your business needs.</span></span> <span data-ttu-id="827cc-325">Ha például a következőképpen szeretne lekérdezni a termékeket:</span><span class="sxs-lookup"><span data-stu-id="827cc-325">For example, if you want to query products as follows:</span></span>

- <span data-ttu-id="827cc-326">Az összesített termék lekérdezése a *Szín* és *Méret* dimenziókkal.</span><span class="sxs-lookup"><span data-stu-id="827cc-326">Query the aggregated product on-hand by the *Color* and *Size* dimensions.</span></span>
- <span data-ttu-id="827cc-327">Bizonyos esetekben csak a termék összesített értékét szeretné lekérdezni.</span><span class="sxs-lookup"><span data-stu-id="827cc-327">In some cases, you just want to query on the product in total.</span></span>

<span data-ttu-id="827cc-328">Két indexet kell definiálni a következőképpen:</span><span class="sxs-lookup"><span data-stu-id="827cc-328">You would have two indexes defined as the following:</span></span>

- `["ColorId", "SizeId"]`
- `[]`

<span data-ttu-id="827cc-329">Az üres zárójel a partíción belül termékazonosító alapján összesít.</span><span class="sxs-lookup"><span data-stu-id="827cc-329">The empty bracket will aggregate based on the product ID within the partition.</span></span>

<span data-ttu-id="827cc-330">Az indexelés határozza meg, hogyan csoportosíthatja az eredményeket a `groupBy` lekérdezési beállítás alapján.</span><span class="sxs-lookup"><span data-stu-id="827cc-330">The indexing defines how you can group your results based on the `groupBy` query setting.</span></span> <span data-ttu-id="827cc-331">Ebben az esetben, ha nem határoz meg `groupBy` értékeket, `productid` szerinti összegeket kap.</span><span class="sxs-lookup"><span data-stu-id="827cc-331">In this case if you don't define any `groupBy` values, you'll get totals by `productid`.</span></span> <span data-ttu-id="827cc-332">Ellenkező esetben, ha a `groupBy` a `groupBy=ColorId&groupBy=SizeId` értékkel van megadva, a rendszer a különböző szín- és méretkombinációk alapján több sort ad vissza.</span><span class="sxs-lookup"><span data-stu-id="827cc-332">Otherwise, if you define `groupBy` as `groupBy=ColorId&groupBy=SizeId`, you'll get multiple lines returned, based on the different color and size combinations in the system.</span></span>

<span data-ttu-id="827cc-333">A lekérdezési feltételt a kérelem törzsébe teheti.</span><span class="sxs-lookup"><span data-stu-id="827cc-333">You can put your query criteria in the request body.</span></span>

<span data-ttu-id="827cc-334">Itt egy példa a termék szín- és méretkombinációját tartalmazó lekérdezésre.</span><span class="sxs-lookup"><span data-stu-id="827cc-334">Here is a sample query on the product with color and size combination.</span></span>

```json
{
    "filters": {
        "OrganizationId": ["usmf"],
        "ProductId": ["MyProduct1", "MyProduct2"],
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

<span data-ttu-id="827cc-335">A `filters` mezőhöz jelenleg csak `ProductId` támogat több értéket.</span><span class="sxs-lookup"><span data-stu-id="827cc-335">For the `filters` field, currently only `ProductId` supports multiple values.</span></span> <span data-ttu-id="827cc-336">Ha `ProductId` üres a tömb, a rendszer az összes terméket lekérdezi.</span><span class="sxs-lookup"><span data-stu-id="827cc-336">If the `ProductId` is an empty array, all products will be queried.</span></span>

#### <a name="custom-measurement"></a><span data-ttu-id="827cc-337">Egyéni mérés</span><span class="sxs-lookup"><span data-stu-id="827cc-337">Custom measurement</span></span>

<span data-ttu-id="827cc-338">Az alapértelmezett mértékmennyiségek a Supply Chain Management alkalmazsáshoz kapcsolódnak.</span><span class="sxs-lookup"><span data-stu-id="827cc-338">The default measurement quantities are linked to Supply Chain Management.</span></span> <span data-ttu-id="827cc-339">Előfordulhat azonban, hogy olyan mennyiséget szeretne, amely az alapértelmezett mértékek kombinációjából áll.</span><span class="sxs-lookup"><span data-stu-id="827cc-339">However, you may want to have a quantity that is made up of a combination of the default measurements.</span></span> <span data-ttu-id="827cc-340">Ehhez egyéni mennyiségek konfigurációját kell megadni, amely az aktuáliskészlet-lekérdezések kimenetéhez lesz hozzáadva.</span><span class="sxs-lookup"><span data-stu-id="827cc-340">To do this, you can have a configuration of custom quantities, which will be added to the output of the on-hand queries.</span></span>

<span data-ttu-id="827cc-341">A funkció segítségével egyszerűen meghatározhat egy sor olyan mért értéket, amelyet hozzá kell adni, és/vagy egy sor olyan mért értéket, amelyet ki kell vonni az egyéni mérések kialakításához.</span><span class="sxs-lookup"><span data-stu-id="827cc-341">The functionality simply allows you to define a set of measures that will be added, and/or a set of measures that will be subtracted, in order to form the custom measurement.</span></span>

<span data-ttu-id="827cc-342">Például a következő lekérdezési feltétel esetén az egyéni mértékegységet úgy kell konfigurálni, mint a `MyCustomAvailableforReservation` elemet, hogy a felhasználó rendszer felhasználja a mennyiséget.</span><span class="sxs-lookup"><span data-stu-id="827cc-342">For example, with the following query condition, you will configure the custom measurement quantity as `MyCustomAvailableforReservation` to be consumed by the consumption system.</span></span>

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



| <span data-ttu-id="827cc-343">Felhasználó rendszer</span><span class="sxs-lookup"><span data-stu-id="827cc-343">Consumption system</span></span> | <span data-ttu-id="827cc-344">Számított mértékek</span><span class="sxs-lookup"><span data-stu-id="827cc-344">Calculated measurers</span></span> | <span data-ttu-id="827cc-345">Adatforrás</span><span class="sxs-lookup"><span data-stu-id="827cc-345">Data source</span></span> | <span data-ttu-id="827cc-346">Módosító</span><span class="sxs-lookup"><span data-stu-id="827cc-346">Modifier</span></span> | <span data-ttu-id="827cc-347">Módosítószámítási típus</span><span class="sxs-lookup"><span data-stu-id="827cc-347">Modifier calculation type</span></span> |
|---|---|---|---|---|
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `availphysical` | <span data-ttu-id="827cc-348">Hozzáadás</span><span class="sxs-lookup"><span data-stu-id="827cc-348">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedintotal` | <span data-ttu-id="827cc-349">Hozzáadás</span><span class="sxs-lookup"><span data-stu-id="827cc-349">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedreserved` | <span data-ttu-id="827cc-350">Kivonás</span><span class="sxs-lookup"><span data-stu-id="827cc-350">Subtraction</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `mypos` | `inbound` | <span data-ttu-id="827cc-351">Hozzáadás</span><span class="sxs-lookup"><span data-stu-id="827cc-351">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `mypos` | `outbound` | <span data-ttu-id="827cc-352">Kivonás</span><span class="sxs-lookup"><span data-stu-id="827cc-352">Subtraction</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `received` | <span data-ttu-id="827cc-353">Hozzáadás</span><span class="sxs-lookup"><span data-stu-id="827cc-353">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `scheduled` | <span data-ttu-id="827cc-354">Hozzáadás</span><span class="sxs-lookup"><span data-stu-id="827cc-354">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `issued` | <span data-ttu-id="827cc-355">Kivonás</span><span class="sxs-lookup"><span data-stu-id="827cc-355">Subtraction</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `reserved` | <span data-ttu-id="827cc-356">Kivonás</span><span class="sxs-lookup"><span data-stu-id="827cc-356">Subtraction</span></span> |

<span data-ttu-id="827cc-357">Ezzel az egyéni mérték mennyiség lekérdezése a következő kimenetet fogja visszaadni.</span><span class="sxs-lookup"><span data-stu-id="827cc-357">With that, the query on the custom measurement quantity will return the following output.</span></span>

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

<span data-ttu-id="827cc-358">A `MyCustomAvailableforReservation` kimenet az egyéni mértékek számítási beállításán alapul, a következők szerint:</span><span class="sxs-lookup"><span data-stu-id="827cc-358">The `MyCustomAvailableforReservation` output is based on the calculation setting in the custom measurements as:</span></span>  
 <span data-ttu-id="827cc-359">*100 + 50 + 80 + 90 + 30 &ndash; 10 &ndash; 20 &ndash; 60 &ndash; 40 = 220*</span><span class="sxs-lookup"><span data-stu-id="827cc-359">*100 + 50 + 80 + 90 + 30 &ndash; 10 &ndash; 20 &ndash; 60 &ndash; 40 = 220*</span></span>

### <a name="posting-on-hand-changes"></a><span data-ttu-id="827cc-360">Aktuális készletváltoztatások feladása</span><span class="sxs-lookup"><span data-stu-id="827cc-360">Posting on-hand changes</span></span>

<span data-ttu-id="827cc-361">A pontos URL-cím, amelyre az esemény feladása történik, a földrajzi régiótól függ.</span><span class="sxs-lookup"><span data-stu-id="827cc-361">The exact URL that the event will be posted to will depend on your geographical region.</span></span> <span data-ttu-id="827cc-362">Ez a következő formát veszi fel:</span><span class="sxs-lookup"><span data-stu-id="827cc-362">It will take the form:</span></span>

`https://{serviceURL}/api/environment/{environmentId}/onhand`

<span data-ttu-id="827cc-363">Ha hitelesítve van, ez az URL-cím együtt használható a HTTP `POST`-metódussal, amellyel a tényleges módosítási eseményeket elküldheti a szolgáltatásnak.</span><span class="sxs-lookup"><span data-stu-id="827cc-363">When authenticated, this URL can be used along with the HTTP `POST` method to send on-hand change events to the service.</span></span>

<span data-ttu-id="827cc-364">Speciális fejléc használatos a Dynamics 365-szolgáltatásokkal történő kommunikációra HTTP-kérések révén, megjelölve a Supply Chain Management-példány környezeti azonosítóját, amely az adatokhoz van kapcsolva.</span><span class="sxs-lookup"><span data-stu-id="827cc-364">A special header is used for communicating with Dynamics 365 services through HTTP requests, denoting the environment ID of the Supply Chain Management instance the data is linked to.</span></span> <span data-ttu-id="827cc-365">Példa:</span><span class="sxs-lookup"><span data-stu-id="827cc-365">For example:</span></span>

`x-ms-environment-id: 2db79622-f97a-4d64-9844-d12efed41796`

#### <a name="posting-on-hand-changes-query-example-1"></a><span data-ttu-id="827cc-366">Az aktuális készleten elvégzett módosításlekérdezések küldése – 1. példa</span><span class="sxs-lookup"><span data-stu-id="827cc-366">Posting on-hand changes query example 1</span></span>

<span data-ttu-id="827cc-367">Ez a példa egy olyan esetet mutat be, amelyben a dimenzió konfigurációját be kell állítania a Power Appsben.</span><span class="sxs-lookup"><span data-stu-id="827cc-367">This example shows a scenario where you will set up the dimension configuration in Power Apps.</span></span>

<span data-ttu-id="827cc-368">A dimenzió-hozzárendelés konfigurálásához használja a következő lekérdezést a Power Appsben:</span><span class="sxs-lookup"><span data-stu-id="827cc-368">Use the following query to configure the dimension mapping in Power Apps:</span></span>

```json
{
    "PosSizeId": "SizeId",
    "PosColorId": "ColorId",
    "PosSiteId": "SiteId",
    "PosLocationId": "LocationId"
}
```

<span data-ttu-id="827cc-369">Itt megadhatja a `dimensionDataSource` elemet és a lekérdezésekben használt egyéni dimenziókat.</span><span class="sxs-lookup"><span data-stu-id="827cc-369">Now you can specify the `dimensionDataSource` and use custom dimensions in your queries.</span></span> <span data-ttu-id="827cc-370">A rendszer automatikusan átváltja az egyéni dimenziókat az alapdimenziókra.</span><span class="sxs-lookup"><span data-stu-id="827cc-370">The system will automatically convert custom dimensions to base dimensions.</span></span>

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

#### <a name="posting-on-hand-changes-query-example-2"></a><span data-ttu-id="827cc-371">Az aktuális készleten elvégzett módosításlekérdezések küldése – 2. példa</span><span class="sxs-lookup"><span data-stu-id="827cc-371">Posting on-hand changes query example 2</span></span>

<span data-ttu-id="827cc-372">Ez a példa egy olyan esetet mutat be, amikor nincs beállítva hozzárendelés a dimenziókonfigurációhoz a Power Appsben, így a feladásnak is az alapdimenziókat kell használnia.</span><span class="sxs-lookup"><span data-stu-id="827cc-372">This example shows a scenario where no mappings are set up for the dimension configuration in Power Apps, so the posting should also use the base dimensions.</span></span> <span data-ttu-id="827cc-373">Minden dimenziónak alapdimenziónak kell lennie, ha a `dimensionDataSource` mező null, üres vagy szóköz.</span><span class="sxs-lookup"><span data-stu-id="827cc-373">All dimensions must be base dimensions when the `dimensionDataSource` field is null, empty, or whitespace.</span></span>

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

#### <a name="json-document-field-properties"></a><span data-ttu-id="827cc-374">JSON-dokumentummező tulajdonságai</span><span class="sxs-lookup"><span data-stu-id="827cc-374">JSON document field properties</span></span>

<span data-ttu-id="827cc-375">A JSON-lekérdezés korábban megadott példáiban szereplő mezők a következő táblázatban látható tulajdonságokkal rendelkeznek.</span><span class="sxs-lookup"><span data-stu-id="827cc-375">The fields from the JSON query examples provided previously have the properties listed in the following table.</span></span>

| <span data-ttu-id="827cc-376">Mezőazonosító</span><span class="sxs-lookup"><span data-stu-id="827cc-376">Field ID</span></span> | <span data-ttu-id="827cc-377">Leírás</span><span class="sxs-lookup"><span data-stu-id="827cc-377">Description</span></span> |
|---|---|
| `id` | <span data-ttu-id="827cc-378">A megadott módosítási esemény egyedi azonosítója.</span><span class="sxs-lookup"><span data-stu-id="827cc-378">A unique ID for the specific change event.</span></span> <span data-ttu-id="827cc-379">Ez az azonosító annak biztosítására szolgál, hogy ha a szolgáltatással folytatott kommunikáció nem sikerül a feladás során, akkor az esemény újraküldése nem eredményezi azt, hogy a rendszer kétszer számolja ugyanazt az eseményt.</span><span class="sxs-lookup"><span data-stu-id="827cc-379">This ID is used to ensure that if communication with the service fails during posting, resubmitting the event would not result in the same event being counted twice in the system.</span></span> |
| `organizationId` | <span data-ttu-id="827cc-380">Az eseményhez kapcsolt szervezet azonosítója.</span><span class="sxs-lookup"><span data-stu-id="827cc-380">The identifier of the organization linked to the event.</span></span> <span data-ttu-id="827cc-381">Ez a leképezés a Supply Chain Management-szervezetekre vagy az adatterület-azonosítóra vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="827cc-381">This maps to Supply Chain Management organizations or data area IDs.</span></span> |
| `productId` | <span data-ttu-id="827cc-382">A kérdéses termék azonosítója.</span><span class="sxs-lookup"><span data-stu-id="827cc-382">The identifier of the product in question.</span></span> |
| `quantity` | <span data-ttu-id="827cc-383">Az a mennyiség, amellyel az aktuális készletet módosítani kell.</span><span class="sxs-lookup"><span data-stu-id="827cc-383">The quantity by which the on-hand needs to be changed.</span></span> <span data-ttu-id="827cc-384">Ha például 10 új bagel került fel egy polcra, ez az érték 10 lesz.</span><span class="sxs-lookup"><span data-stu-id="827cc-384">If, for instance, 10 new bagels were added to a shelf, this value would be 10.</span></span> <span data-ttu-id="827cc-385">Ha 3 bagelt eltávolítanak a polcról vagy eladnak, akkor ez az érték – 3.</span><span class="sxs-lookup"><span data-stu-id="827cc-385">If 3 bagels were then removed from the shelf or sold, this value would be -3.</span></span> |
| `dimensionDataSource` | <span data-ttu-id="827cc-386">A feladási módosítási eseményben és lekérdezésben használt dimenziók adatforrása.</span><span class="sxs-lookup"><span data-stu-id="827cc-386">The data source of the dimensions used in the posting change event and query.</span></span> <span data-ttu-id="827cc-387">Az adatforrás megadása esetén a megadott adatforrás egyéni dimenzióit is használhatja.</span><span class="sxs-lookup"><span data-stu-id="827cc-387">If you specify the data source, you can use the custom dimensions from the specified data source.</span></span> <span data-ttu-id="827cc-388">A dimenzió konfigurálása során a Készlet láthatósága az egyéni dimenziókat az általános alapértelmezett dimenziókra tudja leképezni.</span><span class="sxs-lookup"><span data-stu-id="827cc-388">With the dimension configuration, Inventory Visibility can map the custom dimensions to the general default dimensions.</span></span> <span data-ttu-id="827cc-389">Ha a `dimensionDataSource` nincs megadva, akkor a lekérdezésekben csak az általános alapértelmezett dimenziókat használhatja.</span><span class="sxs-lookup"><span data-stu-id="827cc-389">If the `dimensionDataSource` is not specified, you can only use the general default dimensions in your queries.</span></span>   |
| `dimensions` | <span data-ttu-id="827cc-390">A kulcs/érték párok dinamikus csoportja.</span><span class="sxs-lookup"><span data-stu-id="827cc-390">A dynamic bag of key/value pairs.</span></span> <span data-ttu-id="827cc-391">Ezek a Supply Chain Management néhány dimenziójára kerülnek leképezésre, de hozzáadhat egyéni dimenziókat is (például *Forrás*), amely jelezheti, hogy az esemény a Supply Chain Managementből vagy egy külső rendszerből származik.</span><span class="sxs-lookup"><span data-stu-id="827cc-391">These will map to some of the dimensions in Supply Chain Management, but you could also add custom dimensions (like *Source*) that may denote if the event was coming from Supply Chain Management or an external system.</span></span> |

### <a name="querying-current-on-hand"></a><span data-ttu-id="827cc-392">Aktuális készlet lekérdezése</span><span class="sxs-lookup"><span data-stu-id="827cc-392">Querying current on-hand</span></span>

<span data-ttu-id="827cc-393">Az aktuális készlet lekérdezésének végpontja hasonló URL-címmel rendelkezik:</span><span class="sxs-lookup"><span data-stu-id="827cc-393">The endpoint for querying the current on-hand will have a similar URL:</span></span>

`https://{serviceURL}/api/environment/{environmentId}/onhand/indexquery`

<span data-ttu-id="827cc-394">A rendszer lekérdezi a HTTP `POST` metódussal.</span><span class="sxs-lookup"><span data-stu-id="827cc-394">It will be queried with the HTTP `POST` method.</span></span>

#### <a name="current-on-hand-query-example-1"></a><span data-ttu-id="827cc-395">Aktuális készleten lévő lekérdezés – 1. példa</span><span class="sxs-lookup"><span data-stu-id="827cc-395">Current on-hand query example 1</span></span>

<span data-ttu-id="827cc-396">Ez a példa egy olyan esetet mutat be, amelyben a dimenzió konfigurációját már végrehajtották a Power Appsben.</span><span class="sxs-lookup"><span data-stu-id="827cc-396">This example shows a scenario where you have already completed the dimension configuration in Power Apps.</span></span>

<span data-ttu-id="827cc-397">A dimenzió-hozzárendelés konfigurálásához használja a következő lekérdezést a Power Appsben:</span><span class="sxs-lookup"><span data-stu-id="827cc-397">Use the following query to configure the dimension mapping in Power Apps:</span></span>

```json
{
    "PosSizeId": "SizeId",
    "PosColorId": "ColorId",
    "PosSiteId": "SiteId",
    "PosLocationId": "LocationId"
}
```

<span data-ttu-id="827cc-398">Itt megadhatja a `dimensionDataSource` elemet és a lekérdezésekben használt egyéni dimenziókat.</span><span class="sxs-lookup"><span data-stu-id="827cc-398">Now you can specify the `dimensionDataSource` and use custom dimensions in your queries.</span></span> <span data-ttu-id="827cc-399">A rendszer automatikusan átváltja az egyéni dimenziókat az alapdimenziókra.</span><span class="sxs-lookup"><span data-stu-id="827cc-399">The system will automatically convert custom dimensions to base dimensions.</span></span> <span data-ttu-id="827cc-400">Megadhatja a `DimensionDataSource` értéket a `filters` számára, és megadhatja az egyéni dimenziókat mind a `filters` és a `groupByValues` esetében.</span><span class="sxs-lookup"><span data-stu-id="827cc-400">You can specify the `DimensionDataSource` in `filters` and specify custom dimensions in both `filters` and `groupByValues`.</span></span> <span data-ttu-id="827cc-401">A rendszer automatikusan átváltja az egyéni dimenziókat az alapdimenziókra.</span><span class="sxs-lookup"><span data-stu-id="827cc-401">The system will automatically convert custom dimensions to base dimensions.</span></span>

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

#### <a name="current-on-hand-query-example-2"></a><span data-ttu-id="827cc-402">Aktuális készleten lévő lekérdezés – 2. példa</span><span class="sxs-lookup"><span data-stu-id="827cc-402">Current on-hand query example 2</span></span>

<span data-ttu-id="827cc-403">Ez a példa egy olyan esetet mutat be, amikor nincs beállítva hozzárendelés a dimenziókonfigurációhoz a Power Appsben, így a feladásnak is az alapdimenziókat kell használnia.</span><span class="sxs-lookup"><span data-stu-id="827cc-403">This example shows a scenario where no mappings are set up for the dimension configuration in Power Apps, so the posting should also use the base dimensions.</span></span> <span data-ttu-id="827cc-404">Minden dimenziónak alapdimenziónak kell lennie, ha a `dimensionDataSource` mező a `filters` alatt null, üres vagy szóköz.</span><span class="sxs-lookup"><span data-stu-id="827cc-404">All dimensions must be base dimensions when the `dimensionDataSource` field, under `filters` is null, empty, or whitespace.</span></span>

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

#### <a name="example-return-result"></a><span data-ttu-id="827cc-405">Példa visszatérési eredményre</span><span class="sxs-lookup"><span data-stu-id="827cc-405">Example return result</span></span>

<span data-ttu-id="827cc-406">Az előző példákban megjelenített lekérdezések a következőhöz hasonló eredményt adhatnak vissza.</span><span class="sxs-lookup"><span data-stu-id="827cc-406">The queries shown in the previous examples could return a result like this.</span></span>

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

<span data-ttu-id="827cc-407">Ne felejtse el, hogy a mennyiségek mezői a mértékek és a hozzájuk kapcsolódó értékek jegyzékeként vannak strukturálva.</span><span class="sxs-lookup"><span data-stu-id="827cc-407">Note that the quantities fields are structured as a dictionary of measures and their associated values.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]