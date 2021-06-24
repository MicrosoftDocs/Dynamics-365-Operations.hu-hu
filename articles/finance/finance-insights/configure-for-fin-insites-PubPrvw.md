---
title: A Finance Insights konfigurálása nyilvános előzetes verzióhoz (előzetes verzió) – 10.0.20-as vagy újabb verzió
description: Ez a témakör bemutatja, hogyan kell konfigurálni a rendszert a Finance Insights 10.0.20. vagy újabb nyilvános előzetes verziójában képességek használatához.
author: ShivamPandey-msft
ms.date: 06/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2021-06-03
ms.dyn365.ops.version: AX 10.0.20
ms.openlocfilehash: 613bd4816e2f0c4fbb56cf79779a08c6a09592bd
ms.sourcegitcommit: 655b0e16c7aef6182cd58bc816b901470e1bb2ce
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/10/2021
ms.locfileid: "6222612"
---
# <a name="configuration-for-finance-insights-for-public-preview-preview---version-10020-and-later"></a><span data-ttu-id="192c8-103">A Finance Insights konfigurálása nyilvános előzetes verzióhoz (előzetes verzió) – 10.0.20-as vagy újabb verzió</span><span class="sxs-lookup"><span data-stu-id="192c8-103">Configuration for Finance insights for public preview (preview) - version 10.0.20 and later</span></span>

[!include [banner](../includes/banner.md)]

[!include [preview banner](../includes/preview-banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="192c8-104">A Pénzügyi információk a Microsoft Dynamics 365 Finance és a Dataverse, az Azure és az AI Builder funkcióit kombinálva hatékony előrejelző eszközöket biztosítanak a szervezet számára.</span><span class="sxs-lookup"><span data-stu-id="192c8-104">Finance insights combines functionality from Microsoft Dynamics 365 Finance with Dataverse, Azure, and AI Builder to provide powerful forecasting tools for your organization.</span></span> <span data-ttu-id="192c8-105">Ez a témakör bemutatja, hogyan kell konfigurálni a Dynamics 365 Finance 10.0.20 verzióját a Finance Insights nyilvános előzetes verziójában elérhető képességek használatához.</span><span class="sxs-lookup"><span data-stu-id="192c8-105">This topic explains how to configure Dynamics 365 Finance version 10.0.20 so that your system can use the capabilities that are available in Finance insights public preview.</span></span>

> [!NOTE]
> <span data-ttu-id="192c8-106">Az ebben a témakörben ismertetett konfigurációs lépések csak a Finance 10.0.20-as és későbbi verzióira érvényesek.</span><span class="sxs-lookup"><span data-stu-id="192c8-106">The configuration steps that are described in this topic apply only to Finance version 10.0.20 and later.</span></span> <span data-ttu-id="192c8-107">"A Finance Insights10.0.19-es és korábbi verziói beállításával kapcsolatosan lásd: : [Konfiguráció a Finance Insights alkalmazáshoz – 10.0.18 verzióig](configure-for-fin-insites.md).</span><span class="sxs-lookup"><span data-stu-id="192c8-107">'To set up Finance insights on version 10.0.19 and earlier, see [Configuration for Finance insights - versions up to 10.0.18](configure-for-fin-insites.md).</span></span>

## <a name="deploy-finance"></a><span data-ttu-id="192c8-108">A Finance telepítése</span><span class="sxs-lookup"><span data-stu-id="192c8-108">Deploy Finance</span></span>

<span data-ttu-id="192c8-109">Kövesse az alábbi lépéseket a környezetek telepítéséhez.</span><span class="sxs-lookup"><span data-stu-id="192c8-109">Follow these steps to deploy the environments.</span></span>

1. <span data-ttu-id="192c8-110">A Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásban hozzon létre vagy frissítsen egy Finance környezetet.</span><span class="sxs-lookup"><span data-stu-id="192c8-110">In Microsoft Dynamics Lifecycle Services (LCS), create or update a Finance environment.</span></span> <span data-ttu-id="192c8-111">A környezethez 10.0.20 vagy újabb Finance and Operations alkalmazások verzióra van szükség.</span><span class="sxs-lookup"><span data-stu-id="192c8-111">The environment requires app version 10.0.20 or later of Finance and Operations apps.</span></span>
2. <span data-ttu-id="192c8-112">A környezetnek magas rendelkezésre állású (HA) környezetnek kell lennie a tesztkörnyezetben.</span><span class="sxs-lookup"><span data-stu-id="192c8-112">The environment must be a high-availability (HA) environment in Sandbox.</span></span> <span data-ttu-id="192c8-113">(Az ilyen típusú környezetet 2. szintű környezetnek is nevezik.) További információ: [Környezettervezés](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).</span><span class="sxs-lookup"><span data-stu-id="192c8-113">(This type of environment is also known as a Tier-2 environment.) For more information, see [Environment planning](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).</span></span>
3. <span data-ttu-id="192c8-114">Ha a Finance Insights beállítása egy tesztkörnyezetben történik, lehet, hogy a termelési adatokat az adott környezetbe kell másolnia, hogy az előrejelzések működjenek.</span><span class="sxs-lookup"><span data-stu-id="192c8-114">If you are configuring Finance insights in a Sandbox environment, you might need to copy production data to that environment for predictions to work.</span></span> <span data-ttu-id="192c8-115">Az előrejelzési modell több évnyi adatból használatával készít előrejelzéseket.</span><span class="sxs-lookup"><span data-stu-id="192c8-115">The prediction model uses multiple years of data to build predictions.</span></span> <span data-ttu-id="192c8-116">A Contoso demóadatok nem tartalmaznak elég előzményadatot az előrejelzési modell megfelelő képzéséhez.</span><span class="sxs-lookup"><span data-stu-id="192c8-116">The Contoso demo data doesn’t contain enough historical data to train the prediction model adequately.</span></span> 

## <a name="configure-dataverse"></a><span data-ttu-id="192c8-117">Dataverse konfigurálása</span><span class="sxs-lookup"><span data-stu-id="192c8-117">Configure Dataverse</span></span>

<span data-ttu-id="192c8-118">A következő lépések segítségével konfigurálhatja a Dataverse-t a Finance Insights alkalmazáshoz.</span><span class="sxs-lookup"><span data-stu-id="192c8-118">Follow these steps to configure Dataverse for Finance insights.</span></span>

1. <span data-ttu-id="192c8-119">Nyissa meg a környezet oldalát az LCS-ben, és ellenőrizze, hogy az **Power Platform-Integráció** szakasz már be van-e állítva.</span><span class="sxs-lookup"><span data-stu-id="192c8-119">In LCS, open the environment page, and verify that the **Power Platform Integration** section is already set up.</span></span>

    - <span data-ttu-id="192c8-120">Ha már be van állítva, akkor a Dataverse-környezethez kapcsolt Finance-környezet nevének szerepelnie kell a listában.</span><span class="sxs-lookup"><span data-stu-id="192c8-120">If it's already set up, the Dataverse environment name that is linked to the Finance environment should be listed.</span></span>
    - <span data-ttu-id="192c8-121">Ha még nincs beállítva, kövesse a következő lépéseket:</span><span class="sxs-lookup"><span data-stu-id="192c8-121">If it isn't yet set up, follow these steps:</span></span>

        1. <span data-ttu-id="192c8-122">Válassza a **Beállítás**  lehetőséget a **Power Platform-integráció** szakaszban.</span><span class="sxs-lookup"><span data-stu-id="192c8-122">In the **Power Platform Integration** section, select **Setup**.</span></span> <span data-ttu-id="192c8-123">A környezet beállítása akár egy óráig is eltelhet.</span><span class="sxs-lookup"><span data-stu-id="192c8-123">Setup of the environment might take up to an hour.</span></span>
        2. <span data-ttu-id="192c8-124">Ha a Dataverse-környezet sikeresen be van állítva, akkor a Dataverse-környezethez kapcsolt Finance-környezet nevének szerepelnie kell a listában.</span><span class="sxs-lookup"><span data-stu-id="192c8-124">If the Dataverse environment is successfully set up, the Dataverse environment name that is linked to the Finance environment should be listed.</span></span>

        > [!NOTE]
        > <span data-ttu-id="192c8-125">A környezet beállítása után **ne** válassza a **CDS csatolása alkalmazásokhoz** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="192c8-125">After you complete the environment setup, do **not** select **Link to CDS for Apps**.</span></span> <span data-ttu-id="192c8-126">Ez a gomb nem szükséges a Finance Insights szolgáltatáshoz.</span><span class="sxs-lookup"><span data-stu-id="192c8-126">This button isn't required for Finance insights.</span></span> <span data-ttu-id="192c8-127">Ha kiválasztja, nem fogja tudni konfigurálni az LCS-ben a szükséges környezeti bővítményeket.</span><span class="sxs-lookup"><span data-stu-id="192c8-127">If you select it, you won't be able to configure the required environment add-ins in LCS.</span></span>

## <a name="configure-azure"></a><span data-ttu-id="192c8-128">Az Azure konfigurálása</span><span class="sxs-lookup"><span data-stu-id="192c8-128">Configure Azure</span></span>

### <a name="use-azure-cloud-shell-to-set-up-finance-insights-data-lake-resources"></a><span data-ttu-id="192c8-129">Az Azure Cloud Shell használatával állíthatja be a Data Lake-erőforrásokkal kapcsolatos pénzügyi elemzéseket</span><span class="sxs-lookup"><span data-stu-id="192c8-129">Use Azure Cloud Shell to set up Finance insights Data Lake resources</span></span>

# <a name="use-a-windows-powershell-script"></a>[<span data-ttu-id="192c8-130">Windows PowerShell parancsfájl használata</span><span class="sxs-lookup"><span data-stu-id="192c8-130">Use a Windows PowerShell script</span></span>](#tab/use-a-powershell-script)

<span data-ttu-id="192c8-131">Egy Windows PowerShell-parancsfájlt adott meg, így egyszerűen beállíthatja az Azure-erőforrásokat, amelyek az [Azure Data Lake exportálásának konfigurálása](../../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md) részben találhatók.</span><span class="sxs-lookup"><span data-stu-id="192c8-131">A Windows PowerShell script has been provided so that you can easily set up the Azure resources that are described in [Configure export to Azure Data Lake](../../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md).</span></span> <span data-ttu-id="192c8-132">Ha a manuális beállítást szeretné elvégezni, hagyja ki ezt az eljárást, és végezze el helyette az eljárást a [Manuális beállítás](#manual-setup) szakaszban.</span><span class="sxs-lookup"><span data-stu-id="192c8-132">If you prefer to do the setup manually, skip this procedure, and complete the procedure in the [Manual setup](#manual-setup) section instead.</span></span>

> [!NOTE]
> <span data-ttu-id="192c8-133">A következő eljárás szerint futtassa a Windows PowerShell parancsfájlt.</span><span class="sxs-lookup"><span data-stu-id="192c8-133">Use the following procedure to run the Windows PowerShell script.</span></span> <span data-ttu-id="192c8-134">Előfordulhat, hogy a telepítő nem működik, ha a **Kipróbálás** lehetőséget használja az Azure CLI-ban, vagy a szkriptet a számítógépén futtatja.</span><span class="sxs-lookup"><span data-stu-id="192c8-134">The setup might not work if you use the **Try it** option in Azure CLI or if you run the script on your computer.</span></span>

<span data-ttu-id="192c8-135">Kövesse az alábbi lépéseket az Azure konfigurálásához a Windows PowerShell-parancsfájl használatával.</span><span class="sxs-lookup"><span data-stu-id="192c8-135">Follow these steps to use the Windows PowerShell script to configure Azure.</span></span> <span data-ttu-id="192c8-136">Az Azure-erőforráscsoport, az Azure-erőforrások és az Azure AD alkalmazások létrehozásához jogokkal kell rendelkeznie.</span><span class="sxs-lookup"><span data-stu-id="192c8-136">You must have rights to create an Azure resource group, Azure resources, and an Azure AD application.</span></span> <span data-ttu-id="192c8-137">A szükséges engedélyekről az [Engedélyek Azure AD ellenőrzése](/azure/active-directory/develop/howto-create-service-principal-portal#permissions-required-for-registering-an-app) témakörben talál további információt.</span><span class="sxs-lookup"><span data-stu-id="192c8-137">For information about the required permissions, see [Check Azure AD permissions](/azure/active-directory/develop/howto-create-service-principal-portal#permissions-required-for-registering-an-app).</span></span>

1. <span data-ttu-id="192c8-138">Az [Azure-portálon](https://portal.azure.com) nyissa meg a cél Azure-előfizetés.</span><span class="sxs-lookup"><span data-stu-id="192c8-138">In the [Azure portal](https://portal.azure.com), go to your target Azure subscription.</span></span>
2. <span data-ttu-id="192c8-139">Válassza a **Keresés** mezőtől jobbra lévő **Cloud Shell** gombot.</span><span class="sxs-lookup"><span data-stu-id="192c8-139">Select **Cloud Shell** to the right of the **Search** field.</span></span>
3. <span data-ttu-id="192c8-140">Válassza a **PowerShell** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="192c8-140">Select **PowerShell**.</span></span>
4. <span data-ttu-id="192c8-141">Hozzon létre tárhelyet, ha a rendszer ezt kéri.</span><span class="sxs-lookup"><span data-stu-id="192c8-141">Create storage if you're prompted to create it.</span></span>
5. <span data-ttu-id="192c8-142">Az **Azure parancssori felület** lapon válassza a **Másolás** parancsot.</span><span class="sxs-lookup"><span data-stu-id="192c8-142">On the **Azure CLI** tab, select **Copy**.</span></span>
6. <span data-ttu-id="192c8-143">Nyisson meg egy új fájlt a Jegyzettömbben, majd másolja be a Windows PowerShell parancsfájlt.</span><span class="sxs-lookup"><span data-stu-id="192c8-143">In Notepad, open a new file, and paste in the Windows PowerShell script.</span></span>
7. <span data-ttu-id="192c8-144">Mentse a fájlt **ConfigureDataLake.ps1** néven.</span><span class="sxs-lookup"><span data-stu-id="192c8-144">Save the file as **ConfigureDataLake.ps1**.</span></span>
8. <span data-ttu-id="192c8-145">Töltse fel a Windows PowerShell-parancsfájlt a munkamenetbe a Cloud Shellben a feltöltésre szolgáló menülehetőséggel.</span><span class="sxs-lookup"><span data-stu-id="192c8-145">Upload the Windows PowerShell script to the session by using the menu option for upload in Cloud Shell.</span></span>
9. <span data-ttu-id="192c8-146">Futtassa a **.\ConfigureDataLake.ps1** parancsfájlt.</span><span class="sxs-lookup"><span data-stu-id="192c8-146">Run the **.\ConfigureDataLake.ps1** script.</span></span>
10. <span data-ttu-id="192c8-147">A parancsfájl futtatásához kövesse az utasításokat.</span><span class="sxs-lookup"><span data-stu-id="192c8-147">Follow the prompts to run the script.</span></span>
11. <span data-ttu-id="192c8-148">A parancsfájl kimenetéből származó információk segítségével telepítse az Exportálás a Data Lake-be bővítményt az LCS-ben.</span><span class="sxs-lookup"><span data-stu-id="192c8-148">Use the information from the script output to install the Export to Data Lake add-in in LCS.</span></span>

### <a name="manual-setup"></a><span data-ttu-id="192c8-149">Manuális beállítás</span><span class="sxs-lookup"><span data-stu-id="192c8-149">Manual setup</span></span>

#### <a name="add-applications-to-the-azure-ad-tenant"></a><span data-ttu-id="192c8-150">Alkalmazások hozzáadása az Azure AD-bérlőhöz</span><span class="sxs-lookup"><span data-stu-id="192c8-150">Add applications to the Azure AD tenant</span></span>

1. <span data-ttu-id="192c8-151">Az [Azure-portálban](https://portal.azure.com) menjen ide: **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="192c8-151">In the [Azure portal](https://portal.azure.com), go to **Azure Active Directory**.</span></span>
2. <span data-ttu-id="192c8-152">Válassza a **Vállalati \> alkalmazások kezelése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="192c8-152">Select **Manage \> Enterprise applications**.</span></span>
3. <span data-ttu-id="192c8-153">Keresse meg a következő alkalmazásokat alkalmazásazonosító szerint.</span><span class="sxs-lookup"><span data-stu-id="192c8-153">Search for the following applications by app ID.</span></span>

    | <span data-ttu-id="192c8-154">Pályázat</span><span class="sxs-lookup"><span data-stu-id="192c8-154">Application</span></span>                              | <span data-ttu-id="192c8-155">Alkalmazás azonosítója</span><span class="sxs-lookup"><span data-stu-id="192c8-155">App ID</span></span>                               |
    |------------------------------------------|--------------------------------------|
    | <span data-ttu-id="192c8-156">Microsoft Dynamics ERP mikroszolgáltatások</span><span class="sxs-lookup"><span data-stu-id="192c8-156">Microsoft Dynamics ERP Microservices</span></span>     | <span data-ttu-id="192c8-157">0cdb527f-a8d1-4bf8-9436-b352c68682b2</span><span class="sxs-lookup"><span data-stu-id="192c8-157">0cdb527f-a8d1-4bf8-9436-b352c68682b2</span></span> |
    | <span data-ttu-id="192c8-158">Microsoft Dynamics ERP mikroszolgáltatások CDS</span><span class="sxs-lookup"><span data-stu-id="192c8-158">Microsoft Dynamics ERP Microservices CDS</span></span> | <span data-ttu-id="192c8-159">703e2651-d3fc-48f5-942c-74274233dba8</span><span class="sxs-lookup"><span data-stu-id="192c8-159">703e2651-d3fc-48f5-942c-74274233dba8</span></span> |
    | <span data-ttu-id="192c8-160">AI Builder engedélyezési szolgáltatás</span><span class="sxs-lookup"><span data-stu-id="192c8-160">AI Builder Authorization Service</span></span>         | <span data-ttu-id="192c8-161">ad40333e-9910-4b61-b281-e3aeeb8c3ef3</span><span class="sxs-lookup"><span data-stu-id="192c8-161">ad40333e-9910-4b61-b281-e3aeeb8c3ef3</span></span> |

<span data-ttu-id="192c8-162">Ha az előző alkalmazások egyikét sem találja, próbálkozzon az alábbi lépésekkel.</span><span class="sxs-lookup"><span data-stu-id="192c8-162">If you can't find any of the preceding applications, try the following steps.</span></span>

1. <span data-ttu-id="192c8-163">A helyi számítógépen válassza a **Start** menüt, és keresse meg a **powershell** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="192c8-163">On your local computer, on the **Start** menu, search for **powershell**.</span></span>
2. <span data-ttu-id="192c8-164">Jelölje ki és tartsa lenyomva (vagy nyomja meg a jobb egérgombot) a **Windows PowerShell** lehetőséget, majd válassza a **Futtatás rendszergazdaként** elemet.</span><span class="sxs-lookup"><span data-stu-id="192c8-164">Select and hold (or right-click) **Windows PowerShell**, and then select **Run as administrator**.</span></span>
3. <span data-ttu-id="192c8-165">Futtassa a következő parancsot az **AzureAD-modul** telepítéséhez.</span><span class="sxs-lookup"><span data-stu-id="192c8-165">Run the following command to install the **AzureAD** module.</span></span>

    `Install-Module -Name AzureAD`

4. <span data-ttu-id="192c8-166">Ha egy NuGet szolgáltatóra van szükség a folytatáshoz, válassza az **Y** lehetőséget a telepítéshez.</span><span class="sxs-lookup"><span data-stu-id="192c8-166">If a NuGet provider is required to continue, select **Y** to install it.</span></span>
5. <span data-ttu-id="192c8-167">Ha „Nem megbízható adattár” üzenetet kapott, a folytatáshoz válassza az **Y** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="192c8-167">If you receive an "Untrusted repository" message, select **Y** to continue.</span></span>
6. <span data-ttu-id="192c8-168">Minden hozzáadandó alkalmazáshoz futtassa a következő parancsokat az alkalmazás Azure AD-hoz való hozzáadásához.</span><span class="sxs-lookup"><span data-stu-id="192c8-168">For each application that must be added, run the following commands to add the application to Azure AD.</span></span> <span data-ttu-id="192c8-169">Amikor a rendszer kéri, jelentkezzen be Azure AD-rendszergazdaként.</span><span class="sxs-lookup"><span data-stu-id="192c8-169">When you're prompted, sign in as the Azure AD administrator.</span></span>

    `Connect-AzureAD`

    `New-AzureADServicePrincipal –AppId <AppId>`

#### <a name="create-azure-resources"></a><span data-ttu-id="192c8-170">Azure-erőforrások létrehozása</span><span class="sxs-lookup"><span data-stu-id="192c8-170">Create Azure resources</span></span>

> [!NOTE]
> <span data-ttu-id="192c8-171">Győződjön meg arról, hogy a következő erőforrásokat ugyanabban a Azure AD-példányban hozza létre, mint amelyben a Dataverse-környezet van.</span><span class="sxs-lookup"><span data-stu-id="192c8-171">Make sure that you create the following resources in the same Azure AD instance that the Dataverse environment is in.</span></span> <span data-ttu-id="192c8-172">Más Azure AD-példányból származó erőforrások nem használhatók.</span><span class="sxs-lookup"><span data-stu-id="192c8-172">You can't use resources from a different Azure AD instance.</span></span>

1. <span data-ttu-id="192c8-173">Új tárfiók létrehozása:</span><span class="sxs-lookup"><span data-stu-id="192c8-173">Create a storage account:</span></span>

    1. <span data-ttu-id="192c8-174">Hozzon létre egy társzámlát az [Azure-portálon](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="192c8-174">In the [Azure portal](https://portal.azure.com), create a storage account.</span></span>
    2. <span data-ttu-id="192c8-175">A **Társzámla létrehozása** párbeszédpanelen adja meg a következő mezőket:</span><span class="sxs-lookup"><span data-stu-id="192c8-175">In the **Create storage account** dialog box, set the following fields:</span></span>

        - <span data-ttu-id="192c8-176">**Hely** – Válassza ki azt az adatközpontot, ahol a környezet található.</span><span class="sxs-lookup"><span data-stu-id="192c8-176">**Location** – Select the data center where your environment is located.</span></span>
        - <span data-ttu-id="192c8-177">**Teljesítmény** – Javasoljuk, hogy a **Standard** lehetőséget válassza.</span><span class="sxs-lookup"><span data-stu-id="192c8-177">**Performance** – We recommend that you select **Standard**.</span></span>
        - <span data-ttu-id="192c8-178">**Fiók fajtája** – A **StorageV2** lehetőséget kell választania.</span><span class="sxs-lookup"><span data-stu-id="192c8-178">**Account kind** – You must select **StorageV2**.</span></span>

    3. <span data-ttu-id="192c8-179">A **Speciális beállítások** párbeszédpanel **Data Lake Storage Gen2** lehetőséghez válassza az **Engedélyezés** elemet a **Hierarchikus névterek** funkció alatt.</span><span class="sxs-lookup"><span data-stu-id="192c8-179">In the **Advanced options** dialog box, for the **Data Lake storage Gen2** option, select **Enable** under the **Hierarchical namespaces** feature.</span></span> <span data-ttu-id="192c8-180">Ha nem engedélyezi ezt a funkciót, nem használhatja fel a Finance and Operations alkalmazások által olyan szolgáltatások használatával írt adatokat, mint például a Power BI adatfolyamok.</span><span class="sxs-lookup"><span data-stu-id="192c8-180">If you don't enable this feature, you can't consume data that Finance and Operations apps write by using services such as Power BI data flows.</span></span>
    4. <span data-ttu-id="192c8-181">Válassza a **Vélemény és létrehozás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="192c8-181">Select **Review and create**.</span></span> <span data-ttu-id="192c8-182">A központi telepítés befejezése után az új erőforrás megjelenik az Azure-portálon.</span><span class="sxs-lookup"><span data-stu-id="192c8-182">When the deployment is completed, the new resource is shown in the Azure portal.</span></span>
    5. <span data-ttu-id="192c8-183">Nyissa meg a létrehozott tárfiókot.</span><span class="sxs-lookup"><span data-stu-id="192c8-183">Go to the storage account that you created.</span></span>
    6. <span data-ttu-id="192c8-184">A bal oldali menüben válassza a **Hívóbetű** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="192c8-184">On the left menu, select **Access keys**.</span></span>
    7. <span data-ttu-id="192c8-185">Másolja és mentse a tárfiók nevét.</span><span class="sxs-lookup"><span data-stu-id="192c8-185">Copy and save the name of the storage account.</span></span> <span data-ttu-id="192c8-186">Ezt az értéket később kell megadni, amikor beállítja a kulcstartó titkait.</span><span class="sxs-lookup"><span data-stu-id="192c8-186">You will have to provide this value later, when you set up key vault secrets.</span></span>

2. <span data-ttu-id="192c8-187">Kulcstartó létrehozása:</span><span class="sxs-lookup"><span data-stu-id="192c8-187">Create a key vault:</span></span>

    1. <span data-ttu-id="192c8-188">Hozzon létre egy kulcstárolót az [Azure-portálon](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="192c8-188">In the [Azure portal](https://portal.azure.com), create a key vault.</span></span>
    2. <span data-ttu-id="192c8-189">A **Kulcstartó létrehozása** párbeszédpanel, a **Hely** mezőben jelölje ki azt az adatközpontot, ahol a környezet található.</span><span class="sxs-lookup"><span data-stu-id="192c8-189">In the **Create key vault** dialog box, in the **Location** field, select the data center where your environment is located.</span></span>
    3. <span data-ttu-id="192c8-190">Miután létrehozta a kulcstartót, menjen a **Kulcstartó áttekintése** helyre, és másolja és mentse a DNS-nevet.</span><span class="sxs-lookup"><span data-stu-id="192c8-190">After key vault is created, go to **Key Vault Overview**, and copy and save the DNS name.</span></span> <span data-ttu-id="192c8-191">Ezt az értéket később kell megadni, amikor beállítja a Data Lake bővítményt.</span><span class="sxs-lookup"><span data-stu-id="192c8-191">You will have to provide this value later, when you set up the Data Lake add-in.</span></span>

3. <span data-ttu-id="192c8-192">Azure AD alkalmazás létrehozása és regisztrálása:</span><span class="sxs-lookup"><span data-stu-id="192c8-192">Create and register an Azure AD application:</span></span>

    1. <span data-ttu-id="192c8-193">Az [Azure portálon](https://portal.azure.com) menjen ide: **Azure Active Directory**, majd válassza az **Alkalmazás regisztrálása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="192c8-193">In the [Azure portal](https://portal.azure.com), go to **Azure Active Directory**, and then select **App registrations**.</span></span>
    2. <span data-ttu-id="192c8-194">Válassza ki az **Új alkalmazásregisztráció** lehetőséget, és állítsa be a következő mezőket:</span><span class="sxs-lookup"><span data-stu-id="192c8-194">Select **New application registration**, and set the following fields:</span></span>

        - <span data-ttu-id="192c8-195">**Név** – Írja be az alkalmazás nevét.</span><span class="sxs-lookup"><span data-stu-id="192c8-195">**Name** – Enter the name of the app.</span></span>
        - <span data-ttu-id="192c8-196">**Alkalmazás típusa** – válassza ki a **webes API-t**.</span><span class="sxs-lookup"><span data-stu-id="192c8-196">**Application type** – Select **Web API**.</span></span>
        - <span data-ttu-id="192c8-197">**URI-beállítás átirányítása** – Adja meg a Dynamics 365 példány URL-címét, például: `https://yourdynamicsinstance.dynamics.com/auth`.</span><span class="sxs-lookup"><span data-stu-id="192c8-197">**Redirect URI setup** – Enter the URL for your Dynamics 365 instance, such as `https://yourdynamicsinstance.dynamics.com/auth`.</span></span>

    3. <span data-ttu-id="192c8-198">Nyissa meg az imént létrehozott alkalmazást, és másolja, majd mentse az **Alkalmazás (kliens) azonosítójának** értékét.</span><span class="sxs-lookup"><span data-stu-id="192c8-198">Go to the app that you just created, and copy and save its **Application (client) ID** value.</span></span> <span data-ttu-id="192c8-199">Ezt az értéket később kell megadni, amikor beállítja a kulcstartó titkait.</span><span class="sxs-lookup"><span data-stu-id="192c8-199">You will have to provide this value later, when you set up key vault secrets.</span></span>
    4. <span data-ttu-id="192c8-200">Nyissa meg az **API-engedélyek** lehetőséget, majd kövesse az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="192c8-200">Go to **API permissions**, and follow these steps:</span></span>

        1. <span data-ttu-id="192c8-201">Válassza az **Engedély hozzáadása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="192c8-201">Select **Add a permission**.</span></span>
        2. <span data-ttu-id="192c8-202">Válassza ki az **Azure kulcstartó** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="192c8-202">Select **Azure Key vault**.</span></span>
        3. <span data-ttu-id="192c8-203">A delegált engedélyek kiválasztása után válassza ki a **felhasználó\_megszemélyesítését**.</span><span class="sxs-lookup"><span data-stu-id="192c8-203">After you select delegated permissions, select **user\_impersonation**.</span></span>
        4. <span data-ttu-id="192c8-204">Válassza az **Engedélyek hozzáadása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="192c8-204">Select **Add permissions**.</span></span>

    5. <span data-ttu-id="192c8-205">Az alkalmazás menüjében válassza ki a **Tanúsítványok \& titkai** lehetőséget, majd a Key Vault létrehozásához hajtsa végre az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="192c8-205">On the menu for the app, select **Certificates \& secrets**, and then follow these steps to create Key Vault secrets:</span></span>

        1. <span data-ttu-id="192c8-206">Válassza ki az **Új titkos ügyfélkód** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="192c8-206">Select **New client secret**.</span></span>
        2. <span data-ttu-id="192c8-207">Adjon meg egy nevet a **Kulcsleírás** mezőben.</span><span class="sxs-lookup"><span data-stu-id="192c8-207">In the **Key Description** field, enter a name.</span></span>
        3. <span data-ttu-id="192c8-208">Válasszon ki egy időtartamot, majd a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="192c8-208">Select a duration, and then select **Add**.</span></span> <span data-ttu-id="192c8-209">Az **Érték** mezőben egy titkos kód jön létre.</span><span class="sxs-lookup"><span data-stu-id="192c8-209">A secret is generated in the **Value** field.</span></span>
        4. <span data-ttu-id="192c8-210">A titkos ügyfélkód értékének másolása és mentése.</span><span class="sxs-lookup"><span data-stu-id="192c8-210">Copy and save the client secret value.</span></span> <span data-ttu-id="192c8-211">Ezt az értéket később kell megadni, amikor beállítja a kulcstartó titkait.</span><span class="sxs-lookup"><span data-stu-id="192c8-211">You will have to provide this value later, when you set up key vault secrets.</span></span>

4. <span data-ttu-id="192c8-212">Key Vault titkos kódok létrehozása:</span><span class="sxs-lookup"><span data-stu-id="192c8-212">Create Key Vault secrets:</span></span>

    1. <span data-ttu-id="192c8-213">Menjen a korábban létrehozott kulcstartóhoz, és válassza ki a **Titkokat**.</span><span class="sxs-lookup"><span data-stu-id="192c8-213">Go to the key vault that you created earlier, and select **Secrets**.</span></span>
    2. <span data-ttu-id="192c8-214">Hajtsa végre az alábbi lépéseket mindegyik titkos kód névhez a következő táblában:</span><span class="sxs-lookup"><span data-stu-id="192c8-214">For each secret name in the following table, follow these steps:</span></span>

        1. <span data-ttu-id="192c8-215">Válassza a **Generálás/Importálás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="192c8-215">Select **Generate/Import**.</span></span>
        2. <span data-ttu-id="192c8-216">A **Titkos kód létrehozása** párbeszédpanel **Feltöltési beállítások** mezőjében válassza a **Manuális** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="192c8-216">In the **Create a secret** dialog box, in the **Upload options** field, select **Manual**.</span></span>
        3. <span data-ttu-id="192c8-217">A táblából hozza létre a titkos kód nevét és értékét.</span><span class="sxs-lookup"><span data-stu-id="192c8-217">Create the secret name and value from the table.</span></span>
        4. <span data-ttu-id="192c8-218">Válassza ki az **Engedélyezés**, majd a **Létrehozás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="192c8-218">Select **Enabled**, and then select **Create**.</span></span> <span data-ttu-id="192c8-219">A rendszer létrehozta a titkot, és hozzáadta a Kulcstartót.</span><span class="sxs-lookup"><span data-stu-id="192c8-219">The secret is created and added to Key Vault.</span></span>

        | <span data-ttu-id="192c8-220">Titkos név</span><span class="sxs-lookup"><span data-stu-id="192c8-220">Secret name</span></span>                       | <span data-ttu-id="192c8-221">Titkos kód értéke</span><span class="sxs-lookup"><span data-stu-id="192c8-221">Secret value</span></span>                                                                                 |
        |-----------------------------------|----------------------------------------------------------------------------------------------|
        | <span data-ttu-id="192c8-222">alkalmazás azonosítója</span><span class="sxs-lookup"><span data-stu-id="192c8-222">app-id</span></span>                            | <span data-ttu-id="192c8-223">A korábban létrehozott alkalmazás alkalmazásazonosítója.</span><span class="sxs-lookup"><span data-stu-id="192c8-223">The app ID of the application that you created earlier.</span></span>                                      |
        | <span data-ttu-id="192c8-224">alkalmazás titkos kódja</span><span class="sxs-lookup"><span data-stu-id="192c8-224">app-secret</span></span>                        | <span data-ttu-id="192c8-225">A korábban mentett titkos ügyfélkód.</span><span class="sxs-lookup"><span data-stu-id="192c8-225">The client secret that you saved earlier.</span></span>                                                    |
        | <span data-ttu-id="192c8-226">storage-account-name</span><span class="sxs-lookup"><span data-stu-id="192c8-226">storage-account-name</span></span>              | <span data-ttu-id="192c8-227">A korábban létrehozott tárfiók neve, például **storageaccount1**.</span><span class="sxs-lookup"><span data-stu-id="192c8-227">The name of the storage account that you created earlier, such as **storageaccount1**.</span></span>       |

5. <span data-ttu-id="192c8-228">Az alkalmazás engedélyezése a kulcstartó eléréséhez:</span><span class="sxs-lookup"><span data-stu-id="192c8-228">Authorize the application to access the key vault:</span></span>

    1. <span data-ttu-id="192c8-229">A [Azure-portál](https://portal.azure.com) webhelyen nyissa meg a korábban létrehozott kulcstartót.</span><span class="sxs-lookup"><span data-stu-id="192c8-229">In the [Azure portal](https://portal.azure.com), open the key vault that you created earlier.</span></span>
    2. <span data-ttu-id="192c8-230">Válassza ki a hozzáférési szabályzatokat.</span><span class="sxs-lookup"><span data-stu-id="192c8-230">Select the access policies.</span></span>
    3. <span data-ttu-id="192c8-231">Hajtsa végre az alábbi lépéseket mindegyik alkalmazáshoz a következő táblában:</span><span class="sxs-lookup"><span data-stu-id="192c8-231">For each application in the following table, follow these steps:</span></span>

        1. <span data-ttu-id="192c8-232">Válassza a **Hozzáférési szabályzat hozzáadása** elemet a hozzáférési szabályzat létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="192c8-232">Select **Add Access Policy** to create an access policy.</span></span>
        2. <span data-ttu-id="192c8-233">A **Titkos engedélyek** mezőben válassza ki a táblában szereplő engedélyeket.</span><span class="sxs-lookup"><span data-stu-id="192c8-233">In the **Secret permissions** field, select the permissions from the table.</span></span>
        3. <span data-ttu-id="192c8-234">A **Rendszerbiztonsági tag kiválasztása** mezőben keressen rá az alkalmazás megjelenített nevére a következő táblából.</span><span class="sxs-lookup"><span data-stu-id="192c8-234">In the **Select principal** field, search for the application display name from the table.</span></span>
        4. <span data-ttu-id="192c8-235">Válassza ki a **Kiválasztás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="192c8-235">Select **Select**.</span></span>
        5. <span data-ttu-id="192c8-236">Válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="192c8-236">Select **Add**.</span></span>
        6. <span data-ttu-id="192c8-237">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="192c8-237">Select **Save**.</span></span>

        | <span data-ttu-id="192c8-238">Pályázat</span><span class="sxs-lookup"><span data-stu-id="192c8-238">Application</span></span>                                              | <span data-ttu-id="192c8-239">Engedélyek</span><span class="sxs-lookup"><span data-stu-id="192c8-239">Permissions</span></span> |
        |----------------------------------------------------------|-------------|
        | <span data-ttu-id="192c8-240">A létrehozott új alkalmazás megjelenített neve</span><span class="sxs-lookup"><span data-stu-id="192c8-240">The display name of the new application that you created</span></span> | <span data-ttu-id="192c8-241">Kérés, listázás</span><span class="sxs-lookup"><span data-stu-id="192c8-241">Get, List</span></span>   |
        | <span data-ttu-id="192c8-242">**Microsoft Dynamics ERP mikroszolgáltatások**</span><span class="sxs-lookup"><span data-stu-id="192c8-242">**Microsoft Dynamics ERP Microservices**</span></span>                 | <span data-ttu-id="192c8-243">Kérés, listázás</span><span class="sxs-lookup"><span data-stu-id="192c8-243">Get, List</span></span>   |

6. <span data-ttu-id="192c8-244">Szerepkörök hozzárendelése a tárfiókhoz:</span><span class="sxs-lookup"><span data-stu-id="192c8-244">Assign roles to access the storage account:</span></span>

    1. <span data-ttu-id="192c8-245">A [Azure-portál](https://portal.azure.com) webhelyen nyissa meg a korábban létrehozott tárfiókot.</span><span class="sxs-lookup"><span data-stu-id="192c8-245">In the [Azure portal](https://portal.azure.com), open the storage account that you created earlier.</span></span>
    2. <span data-ttu-id="192c8-246">Válassza ki az **Access Control (IAM)** lehetőséget, majd válassza ki a **Szerepkör hozzárendeléseket**.</span><span class="sxs-lookup"><span data-stu-id="192c8-246">Select **Access Control (IAM)**, and then select **Role Assignments**.</span></span>
    3. <span data-ttu-id="192c8-247">Válassza a **Hozzáadás, Szerepkör-hozzárendelés hozzáadása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="192c8-247">Select **Add, Add Role Assignment**.</span></span>
    4. <span data-ttu-id="192c8-248">Hajtsa végre az alábbi lépéseket mindegyik alkalmazáshoz a következő táblában:</span><span class="sxs-lookup"><span data-stu-id="192c8-248">For each application in the following table, follow these steps:</span></span>

        1. <span data-ttu-id="192c8-249">Válassza ki a szerepkört a táblából.</span><span class="sxs-lookup"><span data-stu-id="192c8-249">Select the role from the table.</span></span>
        2. <span data-ttu-id="192c8-250">A **Hozzáférés hozzárendelése** mezőben hagyja meg az **Azure AD felhasználó, csoport vagy szolgáltatásnév** értéket.</span><span class="sxs-lookup"><span data-stu-id="192c8-250">Leave the **Assign access to** field set to **Azure AD user, group, or service principal**.</span></span>
        3. <span data-ttu-id="192c8-251">A **Kiválasztás** mezőben adja meg a táblában szereplő alkalmazást.</span><span class="sxs-lookup"><span data-stu-id="192c8-251">In the **Select** field, enter the application from the table.</span></span>
        4. <span data-ttu-id="192c8-252">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="192c8-252">Select **Save**.</span></span>

        | <span data-ttu-id="192c8-253">Pályázat</span><span class="sxs-lookup"><span data-stu-id="192c8-253">Application</span></span>                                              | <span data-ttu-id="192c8-254">Szerep</span><span class="sxs-lookup"><span data-stu-id="192c8-254">Role</span></span>                        |
        |----------------------------------------------------------|-----------------------------|
        | <span data-ttu-id="192c8-255">A létrehozott új alkalmazás megjelenített neve</span><span class="sxs-lookup"><span data-stu-id="192c8-255">The display name of the new application that you created</span></span> | <span data-ttu-id="192c8-256">Tulajdonos</span><span class="sxs-lookup"><span data-stu-id="192c8-256">Owner</span></span>                       |
        | <span data-ttu-id="192c8-257">A létrehozott új alkalmazás megjelenített neve</span><span class="sxs-lookup"><span data-stu-id="192c8-257">The display name of the new application that you created</span></span> | <span data-ttu-id="192c8-258">Hozzájáruló</span><span class="sxs-lookup"><span data-stu-id="192c8-258">Contributor</span></span>                 |
        | <span data-ttu-id="192c8-259">A létrehozott új alkalmazás megjelenített neve</span><span class="sxs-lookup"><span data-stu-id="192c8-259">The display name of the new application that you created</span></span> | <span data-ttu-id="192c8-260">Tárfiók közreműködője</span><span class="sxs-lookup"><span data-stu-id="192c8-260">Storage Account Contributor</span></span> |
        | <span data-ttu-id="192c8-261">A létrehozott új alkalmazás megjelenített neve</span><span class="sxs-lookup"><span data-stu-id="192c8-261">The display name of the new application that you created</span></span> | <span data-ttu-id="192c8-262">Tárolási blobadatok tulajdonosa</span><span class="sxs-lookup"><span data-stu-id="192c8-262">Storage Blob Data Owner</span></span>     |
        | <span data-ttu-id="192c8-263">**AI Builder engedélyezési szolgáltatás**</span><span class="sxs-lookup"><span data-stu-id="192c8-263">**AI Builder Authorization Service**</span></span>                     | <span data-ttu-id="192c8-264">Tárolási blobadatok olvasója</span><span class="sxs-lookup"><span data-stu-id="192c8-264">Storage Blob Data Reader</span></span>    |

# <a name="azure-cli"></a>[<span data-ttu-id="192c8-265">Azure parancssori felület</span><span class="sxs-lookup"><span data-stu-id="192c8-265">Azure CLI</span></span>](#tab/azure-azure-cli)

```
function New-FinanceDataLakeAzureResources {
    Assert-ScriptSetup

    $ClientAppName = 'Finance Data Lake Application'
    $DefaultSecretExpiryInYear = 1
    $MicrosoftDynamicsERPMicroservicesAppId = '0cdb527f-a8d1-4bf8-9436-b352c68682b2'
    $MicrosoftDynamicsERPMicroservicesCDSAppId = '703e2651-d3fc-48f5-942c-74274233dba8'
    $AIBuilderAuthorizationServiceAppId = 'ad40333e-9910-4b61-b281-e3aeeb8c3ef3'
    $KeyVaultServicePrincipalAppId = 'cfa8b339-82a2-471a-a3c9-0fc0be7a4093'
    $GraphServicePrincipalAppId = '00000003-0000-0000-c000-000000000000'

    Import-Module AzureAD.Standard.Preview
    $connectAzureADParameters = @{ 'Identity' = $true; 'TenantId' = $env:ACC_TID }
    $azContext = AzureAD.Standard.Preview\Connect-AzureAD @connectAzureADParameters
    $userContext = ConvertFrom-Json ((az ad signed-in-user show) -join '')
    $user = Get-AzureADUser -Filter ("UserPrincipalName eq '" + $userContext.UserPrincipalName + "'")

    Set-AzureSubscription
    
    $resourceGroup = $null
    $ResourceGroupName = 'D365FinanceInsightsDataLake'
    $ResourceGroupNameSuffix = ''
    $FullResourceGroupName = ''
    Write-Output ("The default Azure Resource Group name is '{0}'" -f $ResourceGroupName)
    while (-not ($resourceGroup)) {
        $ResourceGroupNameSuffix = (Read-Host -Prompt "Enter optional Azure Resource Group name suffix: (leave blank for no suffix)")
        if ([string]::IsNullOrWhitespace($ResourceGroupNameSuffix))
        {
            $FullResourceGroupName = $ResourceGroupName
        }
        else
        {
            if ($ResourceGroupNameSuffix -notmatch "^[A-Za-z0-9]+$") {
                Write-Warning "The Azure Resource Group name suffix can only include alphanumeric characters."
                continue
            }

            if ($ResourceGroupNameSuffix.Length -gt 60) {
                Write-Warning "The Azure Resource Group name suffix cannot be longer than 60 characters."
                continue
            }

            $FullResourceGroupName = $ResourceGroupName + $ResourceGroupNameSuffix
        }
        
        $resourceGroup = Get-AzResourceGroup -Name $FullResourceGroupName -ErrorAction SilentlyContinue

        if (-not ($resourceGroup)) {
            Write-Output ("Your new Azure Resource Group name is '{0}'" -f $FullResourceGroupName)
            $resourceLocation = ''
            $azResourceLocations = (Get-AzLocation | Select-Object Location).Location
            while ([string]::IsNullOrWhitespace($resourceLocation) -or (-not ($resourceLocation -in $azResourceLocations))) {
                $resourceLocation = (Read-Host -Prompt "Enter the location in which to create the Azure Resource Group: ('help' to see values)")
                if ($resourceLocation -eq 'help') {
                    Write-Output ("List of available regions is '{0}'" -f ($azResourceLocations -join ','))
                }
                elseif ([string]::IsNullOrWhitespace($resourceLocation) -or (-not ($resourceLocation -in $azResourceLocations)))
                {
                    Write-Warning ("The provided location is not available for resource group. List of available regions is '{0}'" -f ($azResourceLocations -join ','))
                }
            }
            $resourceGroup = New-AzResourceGroup -Name $FullResourceGroupName -Location $resourceLocation
            Write-Output ("Created Azure Resource Group '{0}'" -f $resourceGroup.ResourceGroupName)
        }
        else {
            Write-Output ("Found Azure Resource Group '{0}'" -f ($resourceGroup.ResourceGroupName))
        }
    }

    Write-Output '================================================================================='
    $MicrosoftDynamicsERPMicroservicesAppObjectId = Create-ADServicePrincipal -AppId $MicrosoftDynamicsERPMicroservicesAppId
    Create-ADServicePrincipal -AppId $MicrosoftDynamicsERPMicroservicesCDSAppId | Out-Null
    $aibuilderAuthorizationServiceObjectId = Create-ADServicePrincipal -AppId $AIBuilderAuthorizationServiceAppId
    Write-Output ('=================================================================================')

    $clientAppSPN = Get-AzureADServicePrincipal -Filter ("DisplayName eq '" + $ClientAppName + "'")
    if (-not ($clientAppSPN)) {
        $keyVaultPrincipal = Get-AzureADServicePrincipal -Filter ("AppId eq '" + $KeyVaultServicePrincipalAppId + "'")
        if (-not $keyVaultPrincipal)
        {
            New-AzureADServicePrincipal -AppId $KeyVaultServicePrincipalAppId | Format-Table -AutoSize
            Write-Output "Added Key Vault principal to AAD"
            $keyVaultPrincipal = Get-AzureADServicePrincipal -Filter ("AppId eq '" + $KeyVaultServicePrincipalAppId + "'")
        }
        $keyVaultAccess = New-Object -TypeName "Microsoft.Open.AzureAD.Model.RequiredResourceAccess"
        $keyVaultAccess.ResourceAppId = $keyVaultPrincipal.AppId
        $keyVaultAccess.ResourceAccess = (New-Object -TypeName "microsoft.open.azuread.model.resourceAccess" -ArgumentList $keyVaultPrincipal.Oauth2Permissions.Id, "Scope")

        $graphPrincipal = Get-AzureADServicePrincipal -Filter ("AppId eq '" + $GraphServicePrincipalAppId + "'")
        if (-not $graphPrincipal)
        {
            New-AzureADServicePrincipal -AppId $GraphServicePrincipalAppId | Format-Table -AutoSize
            Write-Output "Added Graph principal to AAD"
            $graphPrincipal = Get-AzureADServicePrincipal -Filter ("AppId eq '" + $GraphServicePrincipalAppId + "'")
        }
        $userRead = $graphPrincipal.Oauth2Permissions | Where-Object { $_.Type -eq "User" -and $_.Value -eq "User.Read" }
        $graphAccess = New-Object -TypeName "Microsoft.Open.AzureAD.Model.RequiredResourceAccess"
        $graphAccess.ResourceAppId = $graphPrincipal.AppId
        $graphAccess.ResourceAccess = (New-Object -TypeName "microsoft.open.azuread.model.resourceAccess" -ArgumentList $userRead.Id, "Scope")

        $clientApp = New-AzureADApplication -DisplayName $ClientAppName -RequiredResourceAccess @($keyVaultAccess, $graphAccess)
        $clientAppSPN = New-AzureADServicePrincipal -AppId $clientApp.AppId -Tags @($ClientAppName)
        $clientAppId = $clientApp.AppId
        Write-Output ('Created App Registration "' + $ClientAppName + '" with Application Id: ' + $clientAppId)
    }
    else {
        $clientApp = Get-AzureADApplication -Filter ("DisplayName eq '" + $ClientAppName + "'")
        $clientAppId = $clientApp.AppId
        Write-Output ('Found App Registration "' + $ClientAppName + '" with Application Id: ' + $clientAppId)
    }
            
    $clientAppSecretCredential = New-AzureADApplicationPasswordCredential -ObjectId $clientApp.ObjectId -CustomKeyIdentifier "ClientAppAccessKey" -EndDate (get-date).AddYears($DefaultSecretExpiryInYear)
    $ClientAppSecret = $clientAppSecretCredential.Value
    $clientAppSpId = $clientAppSPN.ObjectId

    Write-Output ('Generated application secret: ' + $ClientAppSecret)
    Write-Output '================================================================================='

    $templateObject = ConvertFrom-Json $azureTemplate -AsHashtable
    $templateObject.{$schema} = "https://schema.management.azure.com/schemas/2019-04-01/deploymentTemplate.json#"
    Write-Output 'Provisioning Azure resources. This may take a few minutes.'
    try {
        $deployment = New-AzResourceGroupDeployment -ResourceGroupName $FullResourceGroupName -TemplateObject $templateObject -aibuilderAppObjectId $aibuilderAuthorizationServiceObjectId -clientAppId $clientAppId -clientAppSecret $ClientAppSecret -clientAppSpObjectId  $clientAppSpId -microserviceSpObjectId $MicrosoftDynamicsERPMicroservicesAppObjectId -userSpObjectId $user.ObjectId -Force -ErrorAction Stop
    }
    catch {
        $ErrorMessage = $_.Exception.Message
        if ($ErrorMessage.Contains("not allowed to be updated"))
        {
            Write-Error ($ErrorMessage)
            Write-Warning "Some items in the existing resource group $FullResourceGroupName could not be updated. To resolve the issue, remove the existing resource group $FullResourceGroupName and run the script again."
        }
        else {
            throw
        }

    }
    if ($deployment.ProvisioningState -eq 'Succeeded') {
        Write-Output "Successfully deployed the following resources to Azure:"
        Write-Output ("  Key Vault:                         " + $deployment.Outputs.keyVaultName.Value)
        Write-Output ("  Storage Account:                   " + $deployment.Outputs.storageAccountName.Value)
        
        $keyVault = Get-AzKeyVault -VaultName $deployment.Outputs.keyVaultName.Value
        $tenantId = (Get-AzContext).Tenant.Id

        Write-Output "Values for LCS Data Lake Add-In:"
        Write-Output ("  Tenant ID:                         " + $tenantId)
        Write-Output ("  DNS Name:                          " + $keyVault.VaultUri)
        Write-Output "  Storage account secret name:       storage-account-name"
        Write-Output "  Application ID secret name:        app-id"
        Write-Output "  Application Secret secret name:    app-secret"
        Write-Warning "Copy this information for the LCS Add-in for easy access. Azure Cloud Shell will eventually time out and close."

        Write-Output '================================================================================='
        Write-Output "Values for System parameters > Data connections:"
        Write-Output ("  Application ID:                    " + $clientAppId)
        Write-Output ("  Application Secret:                " + $ClientAppSecret)
        Write-Output ("  DNS name:                          " + $keyVault.VaultUri)
        Write-Output "  Secret name:                       storage-account-connection-string"
        Write-Warning "Copy this information for the System parameters for easy access. Azure Cloud Shell will eventually time out and close."
    }
    else {
        Write-Output ("Provisioning Azure resources failed with the following state: " + $deployment.ProvisioningState)
        Write-Output ("Some of the resources may have been created in resource group: " + $FullResourceGroupName)
    }
}

function Assert-ScriptSetup {
    if ($PSVersionTable.PSEdition -ne 'Core' -or -not $env:ACC_TID) { 
        throw "This script needs to be uploaded and run from Azure Cloud Shell (PowerShell)." 
    }
    
    if ((Get-AzContext) -eq $null -and (Connect-AzAccount) -eq $null) {
        throw 'Unable to connect to Azure account.'
    }
}

function Set-AzureSubscription {
    $azSubscription = $null
    while (-not ($azSubscription)) {
        $subscriptionId = (Read-Host -Prompt "Enter the Azure Subscription ID: (leave blank for default)")
        if ([string]::IsNullOrWhitespace($subscriptionId)){
            break
        }
        elseif (-not [guid]::TryParse($subscriptionId, $([ref][guid]::Empty))) {
                Write-Warning "Azure Subscription ID must be a valid GUID."
                continue
        }

        $azSubscription = Select-AzSubscription -SubscriptionId $subscriptionId
    }
}

function Create-ADServicePrincipal {
    param (
        [string] $AppId
    )

    $service = Get-AzureADServicePrincipal -Filter ("AppId eq '" + $AppId + "'")
    if (-not $service) {
        New-AzureADServicePrincipal -AppId $AppId | Out-Null
        $service = Get-AzureADServicePrincipal -Filter ("AppId eq '" + $AppId + "'")
        Write-Host ("Added AAD Enterprise Application {0} with Application ID {1}" -f $service.DisplayName,$AppId)
    }
    else {
        Write-Host ("Found AAD Enterprise Application {0} with Application ID {1}" -f $service.DisplayName,$AppId)
    }

    return $service.ObjectId
}

$azureTemplate = @"
{
    "contentVersion": "1.0.0.0",
    "parameters": {
      "aibuilderAppObjectId": {
        "type": "string",
        "metadata": {
          "description": "Specifies the object ID of the AI Builder application."
        }
      },
      "clientAppId": {
        "type": "string",
        "metadata": {
          "description": "Specifies the application ID of client application."
        }
      },
      "clientAppSecret": {
        "type": "String",
        "metadata": {
          "description": "Specifies the Azure App ID client secret to in azure key vault."
        }
      },
      "clientAppSpObjectId": {
        "type": "string",
        "metadata": {
          "description": "Specifies the object ID of a client application service principal."
        }
      },
      "userSpObjectId": {
        "type": "string",
        "metadata": {
          "description": "Specifies the object ID of tenant admin service principal."
        }
      },
      "microserviceSpObjectId": {
        "type": "string",
        "metadata": {
          "description": "Specifies the object ID of Microsoft Dynamics ERP Microservices service principal."
        }
      },
      "storageAccountType": {
        "type": "string",
        "defaultValue": "Standard_LRS",
        "allowedValues": [
          "Standard_LRS",
          "Standard_GRS",
          "Standard_ZRS",
          "Premium_LRS"
        ],
        "metadata": {
          "description": "Storage Account type"
        }
      }
    },
    "variables": {
      "storageAccountApiVersion": "2019-06-01",
      "keyVaultApiVersion": "2018-02-14",
      "secretsPermissions": [
        "list",
        "get"
      ],
      "location": "[resourceGroup().location]",
      "storageAccountName": "[concat('store', uniquestring(resourceGroup().id))]",
      "keyVaultName": "[concat('keyvault', uniquestring(resourceGroup().id))]",
      "owner": "[concat('/subscriptions/', subscription().subscriptionId, '/providers/Microsoft.Authorization/roleDefinitions/', '8e3af657-a8ff-443c-a75c-2fe8c4bcb635')]",
      "contributor": "[concat('/subscriptions/', subscription().subscriptionId, '/providers/Microsoft.Authorization/roleDefinitions/', 'b24988ac-6180-42a0-ab88-20f7382dd24c')]",
      "storageAccountContributor": "[concat('/subscriptions/', subscription().subscriptionId, '/providers/Microsoft.Authorization/roleDefinitions/', '17d1049b-9a84-46fb-8f53-869881c3d3ab')]",
      "storageBlobDataOwner": "[concat('/subscriptions/', subscription().subscriptionId, '/providers/Microsoft.Authorization/roleDefinitions/', 'b7e6dc6d-f1e8-4753-8033-0f276bb0955b')]",
      "storageBlobDataReader": "[concat('/subscriptions/', subscription().subscriptionId, '/providers/Microsoft.Authorization/roleDefinitions/', '2a2b9908-6ea1-4ae2-8e65-a410df84e7d1')]"
    },
    "resources": [
      {
        "type": "Microsoft.Storage/storageAccounts",
        "apiVersion": "[variables('storageAccountApiVersion')]",
        "name": "[variables('storageAccountName')]",
        "location": "[variables('location')]",
        "sku": {
          "name": "[parameters('storageAccountType')]"
        },
        "kind": "StorageV2",
        "properties": {
          "accessTier": "Hot",
          "supportsHttpsTrafficOnly": true,
          "isHnsEnabled": true
        },
        "resources": [
          {
            "type": "Microsoft.Storage/storageAccounts/providers/roleAssignments",
            "apiVersion": "2018-09-01-preview",
            "name": "[concat(variables('storageAccountName'), '/Microsoft.Authorization/', guid(uniqueString(variables('storageAccountName'),'1')))]",
            "dependsOn": [
              "[variables('storageAccountName')]"
            ],
            "properties": {
              "roleDefinitionId": "[variables('owner')]",
              "principalId": "[parameters('clientAppSpObjectId')]"
            }
          },
          {
            "type": "Microsoft.Storage/storageAccounts/providers/roleAssignments",
            "apiVersion": "2018-09-01-preview",
            "name": "[concat(variables('storageAccountName'), '/Microsoft.Authorization/', guid(uniqueString(variables('storageAccountName'),'2')))]",
            "dependsOn": [
              "[variables('storageAccountName')]"
            ],
            "properties": {
              "roleDefinitionId": "[variables('contributor')]",
              "principalId": "[parameters('clientAppSpObjectId')]"
            }
          },
          {
            "type": "Microsoft.Storage/storageAccounts/providers/roleAssignments",
            "apiVersion": "2018-09-01-preview",
            "name": "[concat(variables('storageAccountName'), '/Microsoft.Authorization/', guid(uniqueString(variables('storageAccountName'),'3')))]",
            "dependsOn": [
              "[variables('storageAccountName')]"
            ],
            "properties": {
              "roleDefinitionId": "[variables('storageAccountContributor')]",
              "principalId": "[parameters('clientAppSpObjectId')]"
            }
          },
          {
            "type": "Microsoft.Storage/storageAccounts/providers/roleAssignments",
            "apiVersion": "2018-09-01-preview",
            "name": "[concat(variables('storageAccountName'), '/Microsoft.Authorization/', guid(uniqueString(variables('storageAccountName'),'4')))]",
            "dependsOn": [
              "[variables('storageAccountName')]"
            ],
            "properties": {
              "roleDefinitionId": "[variables('storageBlobDataOwner')]",
              "principalId": "[parameters('clientAppSpObjectId')]"
            }
          },
          {
            "type": "Microsoft.Storage/storageAccounts/providers/roleAssignments",
            "apiVersion": "2018-09-01-preview",
            "name": "[concat(variables('storageAccountName'), '/Microsoft.Authorization/', guid(uniqueString(variables('storageAccountName'),'5')))]",
            "dependsOn": [
              "[variables('storageAccountName')]"
            ],
            "properties": {
              "roleDefinitionId": "[variables('storageBlobDataReader')]",
              "principalId": "[parameters('aibuilderAppObjectId')]"
            }
          }
        ]
      },
      {
        "type": "Microsoft.KeyVault/vaults",
        "apiVersion": "[variables('keyVaultApiVersion')]",
        "name": "[variables('keyVaultName')]",
        "location": "[variables('location')]",
        "dependsOn": [
          "[resourceId('Microsoft.Storage/storageAccounts', variables('storageAccountName'))]"
        ],
        "tags": {
        },
        "properties": {
          "enabledForDeployment": false,
          "enabledForTemplateDeployment": false,
          "enabledForDiskEncryption": false,
          "enableRbacAuthorization": false,
          "accessPolicies": [
            {
              "objectId": "[parameters('clientAppSpObjectId')]",
              "tenantId": "[subscription().tenantId]",
              "permissions": {
                "secrets": "[variables('secretsPermissions')]"
              }
            },
            {
              "objectId": "[parameters('microserviceSpObjectId')]",
              "tenantId": "[subscription().tenantId]",
              "permissions": {
                "secrets": "[variables('secretsPermissions')]"
              }
            },
            {
              "objectId": "[parameters('userSpObjectId')]",
              "tenantId": "[subscription().tenantId]",
              "permissions": {
                "secrets": "[variables('secretsPermissions')]"
              }
            }
          ],
          "tenantId": "[subscription().tenantId]",
          "sku": {
            "name": "Standard",
            "family": "A"
          },
          "enableSoftDelete": false,
          "networkAcls": {
            "defaultAction": "Allow",
            "bypass": "AzureServices"
          }
        }
      },
      {
        "type": "Microsoft.KeyVault/vaults/secrets",
        "name": "[concat(variables('keyVaultName'), '/', 'app-id')]",
        "apiVersion": "[variables('keyVaultApiVersion')]",
        "location": "[variables('location')]",
        "dependsOn": [
          "[resourceId('Microsoft.KeyVault/vaults', variables('keyVaultName'))]"
        ],
        "properties": {
          "value": "[parameters('clientAppId')]"
        }
      },
      {
        "type": "Microsoft.KeyVault/vaults/secrets",
        "name": "[concat(variables('keyVaultName'), '/', 'app-secret')]",
        "apiVersion": "[variables('keyVaultApiVersion')]",
        "location": "[variables('location')]",
        "dependsOn": [
          "[resourceId('Microsoft.KeyVault/vaults', variables('keyVaultName'))]"
        ],
        "properties": {
          "value": "[parameters('clientAppSecret')]"
        }
      },
      {
        "type": "Microsoft.KeyVault/vaults/secrets",
        "name": "[concat(variables('keyVaultName'), '/', 'storage-account-name')]",
        "apiVersion": "[variables('keyVaultApiVersion')]",
        "location": "[variables('location')]",
        "dependsOn": [
          "[resourceId('Microsoft.KeyVault/vaults', variables('keyVaultName'))]"
        ],
        "properties": {
          "value": "[variables('storageAccountName')]"
        }
      },
      {
        "type": "Microsoft.KeyVault/vaults/secrets",
        "name": "[concat(variables('keyVaultName'), '/', 'storage-account-connection-string')]",
        "apiVersion": "[variables('keyVaultApiVersion')]",
        "location": "[variables('location')]",
        "dependsOn": [
          "[resourceId('Microsoft.KeyVault/vaults', variables('keyVaultName'))]"
        ],
        "properties": {
          "value": "[concat('DefaultEndpointsProtocol=https;AccountName=', variables('storageAccountName'), ';AccountKey=', listKeys(resourceId('Microsoft.Storage/storageAccounts', variables('storageAccountName')), variables('storageAccountApiVersion')).keys[0].value, ';EndpointSuffix=core.windows.net')]"
        }
      }
    ],
    "outputs": {
      "storageAccountName": {
        "type": "string",
        "value": "[variables('storageAccountName')]"
      },
      "keyVaultName": {
        "type": "string",
        "value": "[variables('keyVaultName')]"
      }
    }
  }
"@

try {
  Start-Transcript -path (Join-Path $HOME Provision-FinInsights-Azure.log)
  New-FinanceDataLakeAzureResources
}
catch {
  Write-Error $_.Exception.Message

  if ($PSItem.Exception.StackTrace -ne $null)
  {
      Write-Warning $_.Exception.StackTrace
  }

  $inner = $_.Exception.InnerException
  while ($null -ne $inner) {
    Write-Output 'Inner Exception:'
    Write-Error $_.Exception.Message
    Write-Warning $_.Exception.StackTrace
    $inner = $inner.InnerException
  }
}
finally {
  Stop-Transcript
}
```
---

## <a name="configure-the-export-to-data-lake-add-in"></a><span data-ttu-id="192c8-266">Export konfigurálása az Azure Data Lake bővítményhez</span><span class="sxs-lookup"><span data-stu-id="192c8-266">Configure the Export to Data Lake add-in</span></span>

<span data-ttu-id="192c8-267">Hajtsa végre az alábbi lépéseket, ha az Exportálás Azure Data Lake-be bővítményt hozzá szeretné adni a környezethez az LCS használatával.</span><span class="sxs-lookup"><span data-stu-id="192c8-267">Follow these steps to use LCS to add the Export to Data Lake add-in to the environment.</span></span>

1. <span data-ttu-id="192c8-268">Jelentkezzen be az LCS-be, majd a lap jobb oldalán látható környezet neve alatt válassza ki a **Minden részlet** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="192c8-268">Sign in to LCS, and then, under the environment name on the right side of the page, select **Full Details**.</span></span>
2. <span data-ttu-id="192c8-269">A **Környezeti bővítmények** szakaszban válassza az **Új bővítmény telepítése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="192c8-269">In the **Environment add-ins** section, select **Install a new add-in**.</span></span>
3. <span data-ttu-id="192c8-270">Válassza a **Data Lake exportálása** bővítményt.</span><span class="sxs-lookup"><span data-stu-id="192c8-270">Select the **Export to Data Lake** add-in.</span></span>
4. <span data-ttu-id="192c8-271">Adja meg az alábbi értékeket.</span><span class="sxs-lookup"><span data-stu-id="192c8-271">Enter the following values.</span></span>

    | <span data-ttu-id="192c8-272">Érték</span><span class="sxs-lookup"><span data-stu-id="192c8-272">Value</span></span>                                                              | <span data-ttu-id="192c8-273">Leírás</span><span class="sxs-lookup"><span data-stu-id="192c8-273">Description</span></span> |
    |--------------------------------------------------------------------|-------------|
    | <span data-ttu-id="192c8-274">Az Azure-előfizetés bérlőazonosítója, ahol a Key Vault található</span><span class="sxs-lookup"><span data-stu-id="192c8-274">Tenant ID of the Azure Subscription where the Key Vault is located</span></span> | <span data-ttu-id="192c8-275">A bérlőazonosító, ahol a tárfiók, az alkalmazások és a kulcstartók találhatók.</span><span class="sxs-lookup"><span data-stu-id="192c8-275">The tenant ID where the storage account, apps, and key vaults are located.</span></span> <span data-ttu-id="192c8-276">Ha le szeretné kérni ezt az értéket, nyissa meg az [Azure-portál](https://portal.azure.com) lehetőséget, menjen ide: **Azure Active Directory**, és másolja át a **Bérlőazonosító** értéket.</span><span class="sxs-lookup"><span data-stu-id="192c8-276">To obtain this value, open the [Azure portal](https://portal.azure.com), go to **Azure Active Directory**, and copy the **Tenant ID** value.</span></span> |
    | <span data-ttu-id="192c8-277">Adja meg a Key Vault DNS-nevét.</span><span class="sxs-lookup"><span data-stu-id="192c8-277">Provide the DNS name of your Key Vault</span></span>                             | <span data-ttu-id="192c8-278">A kulcstartó DNS-neve (például: `https://customkeyvault.vault.azure.net/`).</span><span class="sxs-lookup"><span data-stu-id="192c8-278">The DNS name of the key vault, such as `https://customkeyvault.vault.azure.net/`.</span></span> |
    | <span data-ttu-id="192c8-279">Adja meg a tárfiók nevét tartalmazó titkos kódot</span><span class="sxs-lookup"><span data-stu-id="192c8-279">Provide the secret that contains the name of the storage account</span></span>   | <span data-ttu-id="192c8-280">**storage-account-name**</span><span class="sxs-lookup"><span data-stu-id="192c8-280">**storage-account-name**</span></span> |
    | <span data-ttu-id="192c8-281">Titkós kód neve az alkalmazásazonosítóhoz, amelyet a Data Lake eléréséhez használnak</span><span class="sxs-lookup"><span data-stu-id="192c8-281">Secret Name for App ID to be used for accessing Data Lake</span></span>          | <span data-ttu-id="192c8-282">**alkalmazás azonosítója**</span><span class="sxs-lookup"><span data-stu-id="192c8-282">**app-id**</span></span> |
    | <span data-ttu-id="192c8-283">Az alkalmazás titkos ügyfélkódja titkának neve</span><span class="sxs-lookup"><span data-stu-id="192c8-283">Secret name for App client secret</span></span>                                  | <span data-ttu-id="192c8-284">**alkalmazás titkos kódja**</span><span class="sxs-lookup"><span data-stu-id="192c8-284">**app-secret**</span></span> |

5. <span data-ttu-id="192c8-285">Fogadja el a feltételeket, majd válassza a **Telepítés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="192c8-285">Agree to the terms, and then select **Install**.</span></span>

<span data-ttu-id="192c8-286">A bővítményt néhány percen belül telepíti a program.</span><span class="sxs-lookup"><span data-stu-id="192c8-286">The add-in will be installed within a few minutes.</span></span>

## <a name="configure-the-finance-insights-add-in"></a><span data-ttu-id="192c8-287">A Finance Insights bővítmény konfigurálása</span><span class="sxs-lookup"><span data-stu-id="192c8-287">Configure the Finance insights add-in</span></span>

> [!NOTE]
> <span data-ttu-id="192c8-288">Ha korábban már telepítette az Információk megszerzése bővítményét, a következő eljárás előtt távolítsa el azt.</span><span class="sxs-lookup"><span data-stu-id="192c8-288">If you previously installed the Get insights add-in, uninstall it before you complete the following procedure.</span></span>

<span data-ttu-id="192c8-289">A következő lépések szerint telepítheti a Finance Insights bővítményt.</span><span class="sxs-lookup"><span data-stu-id="192c8-289">Follow these steps to install the Finance insights add-in.</span></span>

1. <span data-ttu-id="192c8-290">Jelentkezzen be az LCS-be, majd a lap jobb oldalán látható környezet neve alatt válassza ki a **Minden részlet** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="192c8-290">Sign in to LCS, and then, under the environment name on the right side of the page, select **Full Details**.</span></span>
2. <span data-ttu-id="192c8-291">A **Környezeti bővítmények** szakaszban válassza az **Új bővítmény telepítése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="192c8-291">In the **Environment add-ins** section, select **Install a new add-in**.</span></span>
3. <span data-ttu-id="192c8-292">A **Finance Insights** bővítmény konfigurálása.</span><span class="sxs-lookup"><span data-stu-id="192c8-292">Select the **Finance insights** add-in.</span></span>
4. <span data-ttu-id="192c8-293">Fogadja el a feltételeket, majd válassza a **Telepítés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="192c8-293">Agree to the terms, and then select **Install**.</span></span>

## <a name="feedback-and-support"></a><span data-ttu-id="192c8-294">Visszajelzés és támogatás</span><span class="sxs-lookup"><span data-stu-id="192c8-294">Feedback and support</span></span>

<span data-ttu-id="192c8-295">Kérjük, küldjön egy e-mailt a [Finance insights (előzetes verzió)](mailto:fiap@microsoft.com) címre, ha visszajelzést szeretne adni, vagy támogatásra van szüksége.</span><span class="sxs-lookup"><span data-stu-id="192c8-295">If you're interested in providing feedback, or if you require support, send an email to [Finance insights (Preview)](mailto:fiap@microsoft.com).</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
