---
title: A Finance Insights konfigurációja – 10.0.19 verzióig
description: Ez a témakör azokat a konfigurációs lépéseket ismerteti, amelyek lehetővé teszik a rendszer számára a Finance Insights alkalmazásban elérhető képességek használatát a 10.0.19 verzióig.
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
ms.search.validFrom: 2020-07-20
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 6ad06bb6d041fc060b3a99538f6d4d0af333180f
ms.sourcegitcommit: ebcd9019cbb88a7f2afd9e701812e222566fd43d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/04/2021
ms.locfileid: "6186420"
---
# <a name="configuration-for-finance-insights-preview"></a><span data-ttu-id="0c768-103">Pénzügyi információk konfigurációja (előzetes verzió)</span><span class="sxs-lookup"><span data-stu-id="0c768-103">Configuration for Finance insights (preview)</span></span>

[!include [banner](../includes/banner.md)]

[!include [preview banner](../includes/preview-banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

> [!NOTE]
> <span data-ttu-id="0c768-104">A Finance Insights beállításának következő eljárásai a Microsoft Dynamics 365 Finance 10.0.19 verziójáig érvényesek.</span><span class="sxs-lookup"><span data-stu-id="0c768-104">The following procedures for setting up Finance insights are valid for Microsoft Dynamics 365 Finance versions up to 10.0.19.</span></span> <span data-ttu-id="0c768-105">"A Finance Insights10.0.20 és későbbi verziói beállításával kapcsolatosan lásd: : [Finance Insights (előzetes verzió) – 10.0.20 és újabb verziók](configure-for-fin-insites-PubPrvw.md).</span><span class="sxs-lookup"><span data-stu-id="0c768-105">To set up Finance insights on version 10.0.20 and later, see [Configuration for Finance Insights (preview) - versions 10.0.20 and beyond](configure-for-fin-insites-PubPrvw.md).</span></span>

<span data-ttu-id="0c768-106">A Pénzügyi információk a Microsoft Dynamics 365 Finance és a Microsoft Dataverse, az Azure és az AI Builder funkcióit kombinálva hatékony előrejelző eszközöket biztosítanak a szervezet számára.</span><span class="sxs-lookup"><span data-stu-id="0c768-106">Finance insights combines functionality from Microsoft Dynamics 365 Finance with Microsoft Dataverse, Azure, and AI Builder to provide powerful forecasting tools for your organization.</span></span> <span data-ttu-id="0c768-107">Ez a témakör azokat a konfigurációs lépéseket ismerteti, amelyek lehetővé teszik a rendszer számára a Pénzügyi információkban elérhető képességek használatát.</span><span class="sxs-lookup"><span data-stu-id="0c768-107">This topic explains the configuration steps that will enable your system to use the capabilities that are available in Finance insights.</span></span>

## <a name="deploy-dynamics-365-finance"></a><span data-ttu-id="0c768-108">Dynamics 365 Finance üzembe helyezése</span><span class="sxs-lookup"><span data-stu-id="0c768-108">Deploy Dynamics 365 Finance</span></span>

<span data-ttu-id="0c768-109">A környezetek üzembe helyezéséhez kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="0c768-109">Deploy the environments by following these steps.</span></span>

1. <span data-ttu-id="0c768-110">A Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásban hozzon létre vagy frissítse a Dynamics 365 Finance környezetet.</span><span class="sxs-lookup"><span data-stu-id="0c768-110">In Microsoft Dynamics Lifecycle Services (LCS), create or update a Dynamics 365 Finance environment.</span></span> <span data-ttu-id="0c768-111">A környezethez 10.0.11/Platform 35-ös vagy újabb alkalmazásverzióra van szükség.</span><span class="sxs-lookup"><span data-stu-id="0c768-111">The environment requires app version 10.0.11/Platform update 35 or later.</span></span>
2. <span data-ttu-id="0c768-112">A környezetnek magas rendelkezésre állású (HA) környezetnek kell lennie a tesztkörnyezetben.</span><span class="sxs-lookup"><span data-stu-id="0c768-112">The environment must be a high-availability (HA) environment in Sandbox.</span></span> <span data-ttu-id="0c768-113">(Az ilyen típusú környezetet 2. szintű környezetnek is nevezik.) További információ: [Környezettervezés](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).</span><span class="sxs-lookup"><span data-stu-id="0c768-113">(This type of environment is also known as a Tier-2 environment.) For more information, see [Environment planning](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).</span></span>
3. <span data-ttu-id="0c768-114">Ha a Finance Insights beállítása egy tesztkörnyezetben történik, lehet, hogy a termelési adatokat az adott környezetbe kell másolnia, hogy az előrejelzések működjenek.</span><span class="sxs-lookup"><span data-stu-id="0c768-114">If you are configuring Finance insights in a Sandbox environment, you might need to copy production data to that environment for predictions to work.</span></span> <span data-ttu-id="0c768-115">Az előrejelzési modell több évnyi adatból használatával készít előrejelzéseket.</span><span class="sxs-lookup"><span data-stu-id="0c768-115">The prediction model uses multiple years of data to build predictions.</span></span> <span data-ttu-id="0c768-116">A Contoso demóadatok nem tartalmaznak elég előzményadatot az előrejelzési modell megfelelő képzéséhez.</span><span class="sxs-lookup"><span data-stu-id="0c768-116">The Contoso demo data doesn’t contain enough historical data to train the prediction model adequately.</span></span> 

## <a name="configure-dataverse"></a><span data-ttu-id="0c768-117">Dataverse konfigurálása</span><span class="sxs-lookup"><span data-stu-id="0c768-117">Configure Dataverse</span></span>

<span data-ttu-id="0c768-118">A következő lépések segítségével konfigurálhatja a Dataverse-t a Finance Insightshez.</span><span class="sxs-lookup"><span data-stu-id="0c768-118">Use the following steps to configure Dataverse for Finance insights.</span></span>

1. <span data-ttu-id="0c768-119">Nyissa meg a környezet oldalát az LCS-ben, és ellenőrizze, hogy az **Power Platform-Integráció** szakasz már be van-e állítva.</span><span class="sxs-lookup"><span data-stu-id="0c768-119">Open the environment page in LCS and verify that the **Power Platform Integration** section is already setup.</span></span>
    1. <span data-ttu-id="0c768-120">Ha már be van állítva, akkor a Dynamics 365 Finance-környezethez kapcsolt Dataverse-környezet nevének szerepelnie kell a listában.</span><span class="sxs-lookup"><span data-stu-id="0c768-120">If it is already set up, the Dataverse environment name linked to the Dynamics 365 Finance Environment should be listed.</span></span> <span data-ttu-id="0c768-121">Másolja a Dataverse-környezet nevét.</span><span class="sxs-lookup"><span data-stu-id="0c768-121">Copy the Dataverse environment name.</span></span>
    2. <span data-ttu-id="0c768-122">Ha nincs beállítva, kövesse a következő lépéseket:</span><span class="sxs-lookup"><span data-stu-id="0c768-122">If it is not set up, follow these steps:</span></span>
        1. <span data-ttu-id="0c768-123">Válassza a **Beállítás** gombot a Power Platform-integráció szakaszban.</span><span class="sxs-lookup"><span data-stu-id="0c768-123">Select the **Setup** button in the Power Platform Integration section.</span></span> <span data-ttu-id="0c768-124">A környezet beállítása akár egy óráig is eltarthat.</span><span class="sxs-lookup"><span data-stu-id="0c768-124">It may take up to an hour for the environment to be set up.</span></span>
        2. <span data-ttu-id="0c768-125">Ha a Dataverse-környezet sikeresen be van állítva, akkor a Dynamics 365 Finance-környezethez kapcsolt Dataverse-környezet nevének szerepelnie kell a listában.</span><span class="sxs-lookup"><span data-stu-id="0c768-125">If the Dataverse environment is successfully set up, the Dataverse environment name linked to the Dynamics 365 Finance Environment should be listed.</span></span> <span data-ttu-id="0c768-126">Másolja a Dataverse-környezet nevét.</span><span class="sxs-lookup"><span data-stu-id="0c768-126">Copy the Dataverse environment name.</span></span>
> [!NOTE]
> <span data-ttu-id="0c768-127">A környezet beállítása után **NE** válassza ki a **Hivatkozás a CDS for Appshoz** gombot.</span><span class="sxs-lookup"><span data-stu-id="0c768-127">After completing the environment set up, **DO NOT** select the **Link to CDS for Apps** button.</span></span> <span data-ttu-id="0c768-128">Ez nem szükséges a Finance Insightshoz, és letiltja az LCS-kben szükséges környezeti bővítmények befejezéséhez szükséges képességet.</span><span class="sxs-lookup"><span data-stu-id="0c768-128">This is not needed for Finance Insights and will disable the ability to complete the required Environment Add-ins in LCS.</span></span>

2. <span data-ttu-id="0c768-129">Nyissa meg a [Power Platform felügyeleti központot](https://admin.powerplatform.microsoft.com/), és az alábbi lépések végrehajtásával hozzon létre egy új Dataverse környezetet ugyanabban az Active Directory-bérlőben:</span><span class="sxs-lookup"><span data-stu-id="0c768-129">Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com/), and follow these steps to create a new Dataverse environment in the same Active Directory tenant:</span></span>

    1. <span data-ttu-id="0c768-130">Nyissa meg a **Környezetek** oldalt.</span><span class="sxs-lookup"><span data-stu-id="0c768-130">Open the **Environments** page.</span></span>

        <span data-ttu-id="0c768-131">[![Környezetek oldal](./media/power-pltfrm-admin-center.png)](./media/power-pltfrm-admin-center.png)</span><span class="sxs-lookup"><span data-stu-id="0c768-131">[![Environments page](./media/power-pltfrm-admin-center.png)](./media/power-pltfrm-admin-center.png)</span></span>

    2. <span data-ttu-id="0c768-132">Válassza ki a fent létrehozott Dataverse-környezetet, majd válassza a **Beállítások** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0c768-132">Select the Dataverse environment created above and then select **Settings**.</span></span>
    3. <span data-ttu-id="0c768-133">Válassza az **Erőforrások \> Minden örökölt beállítás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0c768-133">Select **Resources \> All Legacy Settings**.</span></span>
    4. <span data-ttu-id="0c768-134">A felső navigációs sávon válassza a **Beállítások**, majd a **Testreszabás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0c768-134">On the top navigation bar, select **Settings**, and then select **Customizations**.</span></span>
    5. <span data-ttu-id="0c768-135">Válassza a **Fejlesztői erőforrások** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0c768-135">Select **Developer Resources**.</span></span>
    6. <span data-ttu-id="0c768-136">Másolja a **Dataverse szervezetazonosító** értékét.</span><span class="sxs-lookup"><span data-stu-id="0c768-136">Copy the **Dataverse organization ID** value.</span></span>
    7. <span data-ttu-id="0c768-137">A böngésző címsorában jegyezze fel a Dataverse szervezet URL-címét.</span><span class="sxs-lookup"><span data-stu-id="0c768-137">In the browser's address bar, make a note of the URL for the Dataverse organization.</span></span> <span data-ttu-id="0c768-138">Az URL-cím lehet például `https://org42b2b3d3.crm.dynamics.com`.</span><span class="sxs-lookup"><span data-stu-id="0c768-138">For example, the URL might be `https://org42b2b3d3.crm.dynamics.com`.</span></span>

3. <span data-ttu-id="0c768-139">Ha a Pénzforgalmi előrejelzések vagy a Költségvetési előrejelzések funkciót kívánja használni, kövesse az alábbi lépéseket a szervezet címjegyzetkorlátjának legalább 50 megabájtra (MB) történő frissítéséhez:</span><span class="sxs-lookup"><span data-stu-id="0c768-139">If you plan to use the Cash flow forecasts or Budget forecasts feature, follow these steps to update the annotation limit for your organization to at least 50 megabytes (MB):</span></span>

    1. <span data-ttu-id="0c768-140">Nyissa meg a [Power Apps portált](https://make.powerapps.com).</span><span class="sxs-lookup"><span data-stu-id="0c768-140">Open the [Power Apps portal](https://make.powerapps.com).</span></span>
    2. <span data-ttu-id="0c768-141">Válassza ki az imént létrehozott környezetet, majd a **Speciális beállítások** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0c768-141">Select the environment that you just created, and then select **Advanced settings**.</span></span>
    3. <span data-ttu-id="0c768-142">Válassza a **Beállítások \> E-mail konfigurációja** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0c768-142">Select **Settings \> Email Configuration**.</span></span>
    4. <span data-ttu-id="0c768-143">Módosítsa a **Maximális fájlméret** mező értékét **51,200-ra**.</span><span class="sxs-lookup"><span data-stu-id="0c768-143">Change the value of the **Maximum file size** field to **51,200**.</span></span> <span data-ttu-id="0c768-144">(Az értéket kilobájtban \[KB\] kell kifejezni.)</span><span class="sxs-lookup"><span data-stu-id="0c768-144">(The value is expressed in kilobytes \[KB\].)</span></span>
    5. <span data-ttu-id="0c768-145">A módosítás mentéséhez kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="0c768-145">Select **OK** to save your changes.</span></span>

## <a name="configure-the-azure-setup"></a><span data-ttu-id="0c768-146">Az Azure beállítások konfigurálása</span><span class="sxs-lookup"><span data-stu-id="0c768-146">Configure the Azure setup</span></span>

### <a name="enter-the-dataverse-directory-id-and-the-users-azure-ad-object-id"></a><span data-ttu-id="0c768-147">Adja meg a Dataverse címtárazonosítót és a felhasználó Azure AD objektumazonosítóját</span><span class="sxs-lookup"><span data-stu-id="0c768-147">Enter the Dataverse directory ID and the user's Azure AD object ID</span></span>

1. <span data-ttu-id="0c768-148">Adja meg a Dataverse címtárazonosítót:</span><span class="sxs-lookup"><span data-stu-id="0c768-148">Enter the Dataverse directory ID:</span></span>

    1. <span data-ttu-id="0c768-149">Nyissa meg az [Azure-portált](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="0c768-149">Open the [Azure portal](https://portal.azure.com).</span></span>
    2. <span data-ttu-id="0c768-150">Jelentkezzen be a környezet létrehozásához használt felhasználói Dataverse azonosítóval.</span><span class="sxs-lookup"><span data-stu-id="0c768-150">Sign in by using the user ID that was used to create the Dataverse environment.</span></span>
    3. <span data-ttu-id="0c768-151">Ugorjon ide: **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="0c768-151">Go to **Azure Active Directory**.</span></span>
    4. <span data-ttu-id="0c768-152">Másolja a **Bérlői azonosító** értékét.</span><span class="sxs-lookup"><span data-stu-id="0c768-152">Copy the **Tenant ID** value.</span></span>

2. <span data-ttu-id="0c768-153">Itt megadhatja a felhasználó Azure Active Directory (Azure AD) tárgyának azonosítóját:</span><span class="sxs-lookup"><span data-stu-id="0c768-153">Enter the user's Azure Active Directory (Azure AD) object ID:</span></span>

    1. <span data-ttu-id="0c768-154">Az [Azure-portálon](https://portal.azure.com) nyissa meg a **Felhasználók** lehetőséget, és keresse meg a felhasználót az e-mail címe szerint.</span><span class="sxs-lookup"><span data-stu-id="0c768-154">In the [Azure portal](https://portal.azure.com), go to **Users**, and search for the user by email address.</span></span>
    2. <span data-ttu-id="0c768-155">A felhasználó nevének kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="0c768-155">Select the user's name.</span></span>
    3. <span data-ttu-id="0c768-156">Másolja a **Tárgyazonosító** értékét.</span><span class="sxs-lookup"><span data-stu-id="0c768-156">Copy the **Object ID** value.</span></span>

### <a name="use-azure-cloud-shell-to-set-up-finance-insights-data-lake-resources"></a><span data-ttu-id="0c768-157">Az Azure Cloud Shell használatával állíthatja be a Data Lake-erőforrásokkal kapcsolatos pénzügyi elemzéseket</span><span class="sxs-lookup"><span data-stu-id="0c768-157">Use Azure Cloud Shell to set up Finance insights Data Lake resources</span></span>

# <a name="use-a-windows-powershell-script"></a>[<span data-ttu-id="0c768-158">Windows PowerShell parancsfájl használata</span><span class="sxs-lookup"><span data-stu-id="0c768-158">Use a Windows PowerShell script</span></span>](#tab/use-a-powershell-script)

<span data-ttu-id="0c768-159">Egy Windows PowerShell-parancsfájlt adott meg, így egyszerűen beállíthatja az Azure-erőforrásokat, amelyek az [Azure Data Lake exportálásának konfigurálása](../../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md) részben találhatók.</span><span class="sxs-lookup"><span data-stu-id="0c768-159">A Windows PowerShell script has been provided, so that you can easily set up the Azure resources that are described in [Configure export to Azure Data Lake](../../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md).</span></span> <span data-ttu-id="0c768-160">Ha a manuális beállítást szeretné elvégezni, hagyja ki ezt az eljárást, és folytassa az eljárást a [Manuális beállítás](#manual-setup) szakaszban.</span><span class="sxs-lookup"><span data-stu-id="0c768-160">If you prefer to do manual setup, skip this procedure, and continue with the procedure in the [Manual setup](#manual-setup) section.</span></span>

> [!NOTE]
> <span data-ttu-id="0c768-161">Kövesse az alábbi lépéseket a PowerShell-parancsfájl futtatásához.</span><span class="sxs-lookup"><span data-stu-id="0c768-161">Follow the steps below to run the PowerShell script.</span></span> <span data-ttu-id="0c768-162">Lehet, hogy az Azure CLI „Próbálja ki” lehetőség vagy a parancsfájl futtatása a számítógépen nem működik.</span><span class="sxs-lookup"><span data-stu-id="0c768-162">The Azure CLI "Try it" option, or running the script on your PC may not work.</span></span>

<span data-ttu-id="0c768-163">Kövesse az alábbi lépéseket az Azure konfigurálásához a Windows PowerShell-parancsfájl használatával.</span><span class="sxs-lookup"><span data-stu-id="0c768-163">Follow these steps to configure Azure by using the Windows PowerShell script.</span></span> <span data-ttu-id="0c768-164">Az Azure-erőforráscsoport, az Azure-erőforrások és az Azure AD alkalmazások létrehozásához jogokkal kell rendelkeznie.</span><span class="sxs-lookup"><span data-stu-id="0c768-164">You must have rights to create an Azure resource group, Azure resources, and an Azure AD application.</span></span> <span data-ttu-id="0c768-165">A szükséges engedélyekről az [Engedélyek Azure AD ellenőrzése](/azure/active-directory/develop/howto-create-service-principal-portal#permissions-required-for-registering-an-app) témakörben talál további információt.</span><span class="sxs-lookup"><span data-stu-id="0c768-165">For information about the required permissions, see [Check Azure AD permissions](/azure/active-directory/develop/howto-create-service-principal-portal#permissions-required-for-registering-an-app).</span></span>

1. <span data-ttu-id="0c768-166">Az [Azure-portálon](https://portal.azure.com) nyissa meg a cél Azure-előfizetés.</span><span class="sxs-lookup"><span data-stu-id="0c768-166">In the [Azure portal](https://portal.azure.com), go to your target Azure subscription.</span></span> <span data-ttu-id="0c768-167">Válassza a **Keresés** mezőtől jobbra lévő **Cloud Shell** gombot.</span><span class="sxs-lookup"><span data-stu-id="0c768-167">Select the **Cloud Shell** button to the right of the **Search** field.</span></span>
2. <span data-ttu-id="0c768-168">Válassza a **PowerShell** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0c768-168">Select **PowerShell**.</span></span>
3. <span data-ttu-id="0c768-169">Hozzon létre tárhelyet, ha a rendszer erre kéri.</span><span class="sxs-lookup"><span data-stu-id="0c768-169">Create storage if you're prompted to do so.</span></span>
4. <span data-ttu-id="0c768-170">Menjen az **Azure parancssori felület** lapra, és válassza a **Másolás** parancsot.</span><span class="sxs-lookup"><span data-stu-id="0c768-170">Go to the **Azure CLI** tab and select **Copy**.</span></span>  
5. <span data-ttu-id="0c768-171">Nyissa meg a Jegyzettömböt, és illessze be a PowerShell-parancsfájlt.</span><span class="sxs-lookup"><span data-stu-id="0c768-171">Open Notepad and paste the PowerShell script.</span></span> <span data-ttu-id="0c768-172">Mentse a fájlt ConfigureDataLake.ps1 néven.</span><span class="sxs-lookup"><span data-stu-id="0c768-172">Save the file as ConfigureDataLake.ps1.</span></span>
6. <span data-ttu-id="0c768-173">Töltse fel a Windows PowerShell-parancsfájlt a munkamenetbe a Cloud Shellben a feltöltésre szolgáló menülehetőséggel.</span><span class="sxs-lookup"><span data-stu-id="0c768-173">Upload the Windows PowerShell script to the session using the menu option for upload in Cloud Shell.</span></span>
7. <span data-ttu-id="0c768-174">Futtassa a parancsfájlt: .\ConfigureDataLake.ps1.</span><span class="sxs-lookup"><span data-stu-id="0c768-174">Run the script .\ConfigureDataLake.ps1.</span></span>
8. <span data-ttu-id="0c768-175">A parancsfájl futtatásához kövesse az utasításokat.</span><span class="sxs-lookup"><span data-stu-id="0c768-175">Follow the prompts to run the script.</span></span>
9. <span data-ttu-id="0c768-176">A parancsfájl kimenetéből származó információk segítségével telepítse az **Exportálás a Data Lake-be** bővítményt az LCS-ben.</span><span class="sxs-lookup"><span data-stu-id="0c768-176">Use the information from the script output to install the **Export to Data Lake** add-in in LCS.</span></span>
10. <span data-ttu-id="0c768-177">A parancsfájl kimenetéből származó információk segítségével engedélyezze az entitás tárolását a Pénzügy (**Rendszerfelügyelet \> Rendszer paraméterei \> Adatkapcsolatok**) **Adatkapcsolatok** lapján.</span><span class="sxs-lookup"><span data-stu-id="0c768-177">Use the information from the script output to enable the entity store on the **Data connections** page in Finance (**System administration \> System parameters \> Data connections**).</span></span>

### <a name="manual-setup"></a><span data-ttu-id="0c768-178">Manuális beállítás</span><span class="sxs-lookup"><span data-stu-id="0c768-178">Manual setup</span></span>

#### <a name="add-applications-to-the-azure-ad-tenant"></a><span data-ttu-id="0c768-179">Alkalmazások hozzáadása az Azure AD-bérlőhöz</span><span class="sxs-lookup"><span data-stu-id="0c768-179">Add applications to the Azure AD tenant</span></span>

1. <span data-ttu-id="0c768-180">Az [Azure-portálban](https://portal.azure.com) menjen ide: **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="0c768-180">In the [Azure portal](https://portal.azure.com), go to **Azure Active Directory**.</span></span>
2. <span data-ttu-id="0c768-181">Válassza a **Vállalati \> alkalmazások kezelése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0c768-181">Select **Manage \> Enterprise applications**.</span></span>
3. <span data-ttu-id="0c768-182">Keresse meg a következő alkalmazásokat alkalmazásazonosító szerint.</span><span class="sxs-lookup"><span data-stu-id="0c768-182">Search for the following applications by app ID.</span></span>

    | <span data-ttu-id="0c768-183">Pályázat</span><span class="sxs-lookup"><span data-stu-id="0c768-183">Application</span></span>                              | <span data-ttu-id="0c768-184">Alkalmazás azonosítója</span><span class="sxs-lookup"><span data-stu-id="0c768-184">App ID</span></span>                               |
    |------------------------------------------|--------------------------------------|
    | <span data-ttu-id="0c768-185">Microsoft Dynamics ERP mikroszolgáltatások</span><span class="sxs-lookup"><span data-stu-id="0c768-185">Microsoft Dynamics ERP Microservices</span></span>     | <span data-ttu-id="0c768-186">0cdb527f-a8d1-4bf8-9436-b352c68682b2</span><span class="sxs-lookup"><span data-stu-id="0c768-186">0cdb527f-a8d1-4bf8-9436-b352c68682b2</span></span> |
    | <span data-ttu-id="0c768-187">Microsoft Dynamics ERP mikroszolgáltatások CDS</span><span class="sxs-lookup"><span data-stu-id="0c768-187">Microsoft Dynamics ERP Microservices CDS</span></span> | <span data-ttu-id="0c768-188">703e2651-d3fc-48f5-942c-74274233dba8</span><span class="sxs-lookup"><span data-stu-id="0c768-188">703e2651-d3fc-48f5-942c-74274233dba8</span></span> |
    | <span data-ttu-id="0c768-189">AI Builder engedélyezési szolgáltatás</span><span class="sxs-lookup"><span data-stu-id="0c768-189">AI Builder Authorization Service</span></span>         | <span data-ttu-id="0c768-190">ad40333e-9910-4b61-b281-e3aeeb8c3ef3</span><span class="sxs-lookup"><span data-stu-id="0c768-190">ad40333e-9910-4b61-b281-e3aeeb8c3ef3</span></span> |

<span data-ttu-id="0c768-191">Ha az előző alkalmazások egyikét sem találja, próbálkozzon az alábbi lépésekkel.</span><span class="sxs-lookup"><span data-stu-id="0c768-191">If you can't find any of the preceding applications, try the following steps.</span></span>

1. <span data-ttu-id="0c768-192">A helyi számítógépen válassza a **Start** menüt, és keresse meg a **powershell** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0c768-192">On your local machine, select the **Start** menu, and search for **powershell**.</span></span>
2. <span data-ttu-id="0c768-193">Jelölje ki és tartsa lenyomva (vagy nyomja meg a jobb egérgombot) a **Windows PowerShell** lehetőséget, majd válassza a **Futtatás rendszergazdaként** elemet.</span><span class="sxs-lookup"><span data-stu-id="0c768-193">Select and hold (or right-click) **Windows PowerShell**, and then select **Run as administrator**.</span></span>
3. <span data-ttu-id="0c768-194">Futtassa a következő parancsot az **AzureAD-modul** telepítéséhez.</span><span class="sxs-lookup"><span data-stu-id="0c768-194">Run the following command to install the **AzureAD** module.</span></span>

    `Install-Module -Name AzureAD`

4. <span data-ttu-id="0c768-195">Ha egy NuGet szolgáltatóra van szükség a folytatáshoz, válassza az **Y** lehetőséget a telepítéshez.</span><span class="sxs-lookup"><span data-stu-id="0c768-195">If a NuGet provider is required to continue, select **Y** to install it.</span></span>
5. <span data-ttu-id="0c768-196">Ha „Nem megbízható adattár” üzenet jelenik meg, a folytatáshoz válassza az **Y** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0c768-196">If an "Untrusted repository" message appears, select **Y** to continue.</span></span>
6. <span data-ttu-id="0c768-197">Minden hozzáadandó alkalmazáshoz futtassa a következő parancsokat az alkalmazás Azure AD-hoz való hozzáadásához.</span><span class="sxs-lookup"><span data-stu-id="0c768-197">For each application that must be added, run the following commands to add the application to Azure AD.</span></span> <span data-ttu-id="0c768-198">Amikor a rendszer kéri, jelentkezzen be Azure AD-rendszergazdaként.</span><span class="sxs-lookup"><span data-stu-id="0c768-198">When you're prompted, sign in as the Azure AD administrator.</span></span>

    `Connect-AzureAD`

    `New-AzureADServicePrincipal –AppId <AppId>`

#### <a name="create-azure-resources"></a><span data-ttu-id="0c768-199">Azure-erőforrások létrehozása</span><span class="sxs-lookup"><span data-stu-id="0c768-199">Create Azure resources</span></span>

> [!NOTE]
> <span data-ttu-id="0c768-200">Győződjön meg arról, hogy a következő erőforrásokat hozza létre ugyanabban a Azure AD-példányban, mint a Dataverse-környezetben.</span><span class="sxs-lookup"><span data-stu-id="0c768-200">Make sure that you create the following resources in the same Azure AD instance as the Dataverse environment.</span></span> <span data-ttu-id="0c768-201">Más Azure AD-példányból származó erőforrások nem használhatók.</span><span class="sxs-lookup"><span data-stu-id="0c768-201">You can't use resources from a different Azure AD instance.</span></span>

1. <span data-ttu-id="0c768-202">Új társzámla létrehozása:</span><span class="sxs-lookup"><span data-stu-id="0c768-202">Create a new storage account:</span></span>

    1. <span data-ttu-id="0c768-203">Hozzon létre egy társzámlát az [Azure-portálon](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="0c768-203">In the [Azure portal](https://portal.azure.com), create a storage account.</span></span>
    2. <span data-ttu-id="0c768-204">A **Társzámla létrehozása** párbeszédpanelen adja meg a következő mezőket:</span><span class="sxs-lookup"><span data-stu-id="0c768-204">In the **Create storage account** dialog box, set the following fields:</span></span>

        - <span data-ttu-id="0c768-205">**Hely** – Válassza ki azt az adatközpontot, ahol a környezet található.</span><span class="sxs-lookup"><span data-stu-id="0c768-205">**Location** – Select the data center where your environment is located.</span></span>
        - <span data-ttu-id="0c768-206">**Teljesítmény** – Javasoljuk, hogy a **Standard** lehetőséget válassza.</span><span class="sxs-lookup"><span data-stu-id="0c768-206">**Performance** – We recommend that you select **Standard**.</span></span>
        - <span data-ttu-id="0c768-207">**Fiók fajtája** – A **StorageV2** lehetőséget kell választania.</span><span class="sxs-lookup"><span data-stu-id="0c768-207">**Account kind** – You must select **StorageV2**.</span></span>

    3. <span data-ttu-id="0c768-208">A **Speciális beállítások** párbeszédpanel **Data Lake Storage Gen2** lehetőséghez válassza az **Engedélyezés** elemet a **Hierarchikus névterek** funkció alatt.</span><span class="sxs-lookup"><span data-stu-id="0c768-208">In the **Advanced options** dialog box, for the **Data Lake storage Gen2** option, select **Enable** under the **Hierarchical namespaces** feature.</span></span> <span data-ttu-id="0c768-209">Ha letiltja ezt a funkciót, nem használhatja fel a Finance and Operations alkalmazások által olyan szolgáltatások használatával írt adatokat, mint például a Power BI adatfolyamok.</span><span class="sxs-lookup"><span data-stu-id="0c768-209">If you disable this feature, you can't consume data that Finance and Operations apps write by using services such as Power BI data flows.</span></span>
    4. <span data-ttu-id="0c768-210">Válassza a **Vélemény és létrehozás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0c768-210">Select **Review and create**.</span></span> <span data-ttu-id="0c768-211">A központi telepítés befejezése után az új erőforrás megjelenik az Azure-portálon.</span><span class="sxs-lookup"><span data-stu-id="0c768-211">When the deployment is completed, the new resource will be shown in the Azure portal.</span></span>
    5. <span data-ttu-id="0c768-212">Nyissa meg a létrehozott tárfiókot.</span><span class="sxs-lookup"><span data-stu-id="0c768-212">Go to the storage account that you created.</span></span>
    6. <span data-ttu-id="0c768-213">A bal oldali menüben válassza a **Hívóbetű** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0c768-213">On the left menu, select **Access keys**.</span></span>
    7. <span data-ttu-id="0c768-214">Másolja és mentse a kapcsolati karakterláncot a **Key1** vagy a **Key2** lehetőséghez.</span><span class="sxs-lookup"><span data-stu-id="0c768-214">Copy and save the connection string for either **Key1** or **Key2**.</span></span>
    8. <span data-ttu-id="0c768-215">Másolja és mentse a tárfiók nevét.</span><span class="sxs-lookup"><span data-stu-id="0c768-215">Copy and save the storage account name.</span></span>

2. <span data-ttu-id="0c768-216">Új kulcstároló létrehozása:</span><span class="sxs-lookup"><span data-stu-id="0c768-216">Create a new key vault:</span></span>

    1. <span data-ttu-id="0c768-217">Hozzon létre egy kulcstárolót az [Azure-portálon](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="0c768-217">In the [Azure portal](https://portal.azure.com), create a key vault.</span></span>
    2. <span data-ttu-id="0c768-218">A **Kulcstartó létrehozása** párbeszédpanel, a **Hely** mezőben jelölje ki azt az adatközpontot, ahol a környezet található.</span><span class="sxs-lookup"><span data-stu-id="0c768-218">In the **Create key vault** dialog box, in the **Location** field, select the data center where your environment is located.</span></span>
    3. <span data-ttu-id="0c768-219">A kulcstartó létrehozása után jelölje ki a listában, majd válassza ki a **Titkok** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0c768-219">After key vault is created, select it in the list, and then select **Secrets**.</span></span>
    4. <span data-ttu-id="0c768-220">Válassza a **Generálás/Importálás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0c768-220">Select **Generate/Import**.</span></span>
    5. <span data-ttu-id="0c768-221">A **Titkos kód létrehozása** párbeszédpanel **Feltöltési beállítások** mezőjében válassza a **Manuális** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0c768-221">In the **Create a secret** dialog box, in the **Upload options** field, select **Manual**.</span></span>
    6. <span data-ttu-id="0c768-222">Adja meg a titkos kód nevét.</span><span class="sxs-lookup"><span data-stu-id="0c768-222">Enter a name for the secret.</span></span> <span data-ttu-id="0c768-223">Jegyezze fel a nevet, mert később meg kell adnia.</span><span class="sxs-lookup"><span data-stu-id="0c768-223">Make a note of the name, because you will have to provide it later.</span></span>
    7. <span data-ttu-id="0c768-224">Az **Érték** mezőbe írja be azt a kapcsolati karakterláncot, amelyet a korábbi eljárásban a tárfiókból nyert.</span><span class="sxs-lookup"><span data-stu-id="0c768-224">In the **Value** field, enter the connection string that you obtained from the storage account in the previous procedure.</span></span>
    8. <span data-ttu-id="0c768-225">Válassza ki az **Engedélyezés**, majd a **Létrehozás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0c768-225">Select **Enabled**, and then select **Create**.</span></span> <span data-ttu-id="0c768-226">A rendszer létrehozta a titkot, és hozzáadta a Kulcstartót.</span><span class="sxs-lookup"><span data-stu-id="0c768-226">The secret is created and added to Key Vault.</span></span>
    9. <span data-ttu-id="0c768-227">Nyissa meg a **Kulcstartó áttekintése** lehetőséget, és jegyezze fel a DNS-nevet.</span><span class="sxs-lookup"><span data-stu-id="0c768-227">Go to the **Key Vault Overview**, and make a note of the DNS name.</span></span>

3. <span data-ttu-id="0c768-228">Azure AD alkalmazás létrehozása és regisztrálása:</span><span class="sxs-lookup"><span data-stu-id="0c768-228">Create and register an Azure AD application:</span></span>

    1. <span data-ttu-id="0c768-229">Az [Azure portálon](https://portal.azure.com) menjen ide: **Azure Active Directory**, majd válassza az **Alkalmazás regisztrálása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0c768-229">In the [Azure portal](https://portal.azure.com), go to **Azure Active Directory**, and then select **App registrations**.</span></span>
    2. <span data-ttu-id="0c768-230">Válassza ki az **Új alkalmazásregisztráció** lehetőséget, és állítsa be a következő mezőket:</span><span class="sxs-lookup"><span data-stu-id="0c768-230">Select **New application registration**, and set the following fields:</span></span>

        - <span data-ttu-id="0c768-231">**Név** – Írja be az alkalmazás nevét.</span><span class="sxs-lookup"><span data-stu-id="0c768-231">**Name** – Enter the name of the app.</span></span>
        - <span data-ttu-id="0c768-232">**Alkalmazás típusa** – válassza ki a **webes API-t**.</span><span class="sxs-lookup"><span data-stu-id="0c768-232">**Application type** – Select **Web API**.</span></span>
        - <span data-ttu-id="0c768-233">**URI-beállítás átirányítása** – Adja meg a Dynamics 365 példány URL-címét, például: `https://yourdynamicsinstance.dynamics.com/auth`.</span><span class="sxs-lookup"><span data-stu-id="0c768-233">**Redirect URI setup** – Enter the URL for your Dynamics 365 instance, such as, `https://yourdynamicsinstance.dynamics.com/auth`.</span></span>

    3. <span data-ttu-id="0c768-234">Nyissa meg az imént létrehozott alkalmazást, és másolja, majd mentse az **Alkalmazás (kliens) azonosítójának** értékét.</span><span class="sxs-lookup"><span data-stu-id="0c768-234">Go to the app that you just created, and copy and save its **Application (client) ID** value.</span></span> <span data-ttu-id="0c768-235">Ezt az értéket később kell megadni, amikor beállítja a kulcstartót.</span><span class="sxs-lookup"><span data-stu-id="0c768-235">You will have to provide this value later, when you set up the key vault.</span></span>
    4. <span data-ttu-id="0c768-236">Nyissa meg az **API-engedélyek** lehetőséget, majd kövesse az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="0c768-236">Go to **API permissions**, and follow these steps:</span></span>

        1. <span data-ttu-id="0c768-237">Válassza az **Engedély hozzáadása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0c768-237">Select **Add a permission**.</span></span>
        2. <span data-ttu-id="0c768-238">Válassza ki az **Azure kulcstartó** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0c768-238">Select **Azure Key vault**.</span></span>
        3. <span data-ttu-id="0c768-239">A delegált engedélyek kiválasztása után válassza ki a **felhasználó\_megszemélyesítését**.</span><span class="sxs-lookup"><span data-stu-id="0c768-239">After you select delegated permissions, select **user\_impersonation**.</span></span>
        4. <span data-ttu-id="0c768-240">Válassza az **Engedélyek hozzáadása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0c768-240">Select **Add permissions**.</span></span>

    5. <span data-ttu-id="0c768-241">Az alkalmazás menüjében válassza ki a **Tanúsítványok \& titkai** lehetőséget, majd a Key Vault létrehozásához hajtsa végre az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="0c768-241">On the menu for the app, select **Certificates \& secrets**, and then follow these steps to create Key Vault secrets:</span></span>

        1. <span data-ttu-id="0c768-242">Válassza ki az **Új titkos ügyfélkód** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0c768-242">Select **New client secret**.</span></span>
        2. <span data-ttu-id="0c768-243">Adjon meg egy nevet a **Kulcsleírás** mezőben.</span><span class="sxs-lookup"><span data-stu-id="0c768-243">In the **Key Description** field, enter a name.</span></span>
        3. <span data-ttu-id="0c768-244">Válasszon ki egy időtartamot, majd a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0c768-244">Select a duration, and then select **Add**.</span></span> <span data-ttu-id="0c768-245">Az **Érték** mezőben egy titkos kód jön létre.</span><span class="sxs-lookup"><span data-stu-id="0c768-245">A secret is generated in the **Value** field.</span></span>
        4. <span data-ttu-id="0c768-246">A titkos kód értékének másolása és mentése.</span><span class="sxs-lookup"><span data-stu-id="0c768-246">Copy and save the secret value.</span></span>

4. <span data-ttu-id="0c768-247">Key Vault titkos kódok létrehozása:</span><span class="sxs-lookup"><span data-stu-id="0c768-247">Create Key Vault secrets:</span></span>

    1. <span data-ttu-id="0c768-248">Menjen a korábban létrehozott kulcstartóhoz, és válassza ki a **Titkokat**.</span><span class="sxs-lookup"><span data-stu-id="0c768-248">Go to the key vault that you created earlier, and select **Secrets**.</span></span>
    2. <span data-ttu-id="0c768-249">Hajtsa végre az alábbi lépéseket mindegyik titkos kód névhez a következő táblában:</span><span class="sxs-lookup"><span data-stu-id="0c768-249">For each secret name in the following table, follow these steps:</span></span>

        1. <span data-ttu-id="0c768-250">Válassza a **Generálás/Importálás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0c768-250">Select **Generate/Import**.</span></span>
        2. <span data-ttu-id="0c768-251">A **Titkos kód létrehozása** párbeszédpanel **Feltöltési beállítások** mezőjében válassza a **Manuális** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0c768-251">In the **Create a secret** dialog box, in the **Upload options** field, select **Manual**.</span></span>
        3. <span data-ttu-id="0c768-252">A következő táblából hozza létre a titkos kód nevét és értékét.</span><span class="sxs-lookup"><span data-stu-id="0c768-252">Create the secret name and value from the following table.</span></span>
        4. <span data-ttu-id="0c768-253">Válassza ki az **Engedélyezés**, majd a **Létrehozás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0c768-253">Select **Enabled**, and then select **Create**.</span></span> <span data-ttu-id="0c768-254">A rendszer létrehozta a titkot, és hozzáadta a Kulcstartót.</span><span class="sxs-lookup"><span data-stu-id="0c768-254">The secret is created and added to Key Vault.</span></span>

        | <span data-ttu-id="0c768-255">Titkos név</span><span class="sxs-lookup"><span data-stu-id="0c768-255">Secret name</span></span>                       | <span data-ttu-id="0c768-256">Titkos kód értéke</span><span class="sxs-lookup"><span data-stu-id="0c768-256">Secret value</span></span>                                                                                |
        |-----------------------------------|---------------------------------------------------------------------------------------------|
        | <span data-ttu-id="0c768-257">alkalmazás azonosítója</span><span class="sxs-lookup"><span data-stu-id="0c768-257">app-id</span></span>                            | <span data-ttu-id="0c768-258">A korábban létrehozott alkalmazás alkalmazásazonosítója</span><span class="sxs-lookup"><span data-stu-id="0c768-258">The app ID of the application that you created earlier</span></span>                                      |
        | <span data-ttu-id="0c768-259">alkalmazás titkos kódja</span><span class="sxs-lookup"><span data-stu-id="0c768-259">app-secret</span></span>                        | <span data-ttu-id="0c768-260">A korábban mentett titkos ügyfélkód</span><span class="sxs-lookup"><span data-stu-id="0c768-260">The client secret that you saved earlier</span></span>                                                    |
        | <span data-ttu-id="0c768-261">storage-account-name</span><span class="sxs-lookup"><span data-stu-id="0c768-261">storage-account-name</span></span>              | <span data-ttu-id="0c768-262">A korábban létrehozott tárfiók neve, például **storageaccount1**</span><span class="sxs-lookup"><span data-stu-id="0c768-262">The name of the storage account that you created earlier, such as **storageaccount1**</span></span>       |
        | <span data-ttu-id="0c768-263">storage-account-connection-string</span><span class="sxs-lookup"><span data-stu-id="0c768-263">storage-account-connection-string</span></span> | <span data-ttu-id="0c768-264">A tárfiók **Elérési kulcsok** lapjáról átmásolt kapcsolati karakterlánc</span><span class="sxs-lookup"><span data-stu-id="0c768-264">The connection string that you copied from the **Access keys** page for the storage account</span></span> |

5. <span data-ttu-id="0c768-265">Az alkalmazás engedélyezése a kulcstartó eléréséhez:</span><span class="sxs-lookup"><span data-stu-id="0c768-265">Authorize the application to access the key vault:</span></span>

    1. <span data-ttu-id="0c768-266">A [Azure-portál](https://portal.azure.com) webhelyen nyissa meg a korábban létrehozott kulcstartót.</span><span class="sxs-lookup"><span data-stu-id="0c768-266">In the [Azure portal](https://portal.azure.com), open the key vault that you created earlier.</span></span>
    2. <span data-ttu-id="0c768-267">Válassza ki a hozzáférési szabályzatokat.</span><span class="sxs-lookup"><span data-stu-id="0c768-267">Select the access policies.</span></span>
    3. <span data-ttu-id="0c768-268">Hajtsa végre az alábbi lépéseket mindegyik alkalmazáshoz a következő táblában:</span><span class="sxs-lookup"><span data-stu-id="0c768-268">For each application in the following table, follow these steps:</span></span>

        1. <span data-ttu-id="0c768-269">Válassza a **Hozzáférési szabályzat hozzáadása** elemet a hozzáférési szabályzat létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="0c768-269">Select **Add Access Policy** to create an access policy.</span></span>
        2. <span data-ttu-id="0c768-270">A **Titkos engedélyek** mezőben válassza ki a következő táblában szereplő engedélyeket.</span><span class="sxs-lookup"><span data-stu-id="0c768-270">In the **Secret permissions** field, select the permissions from the following table.</span></span>
        3. <span data-ttu-id="0c768-271">A **Résztvevő kiválasztása** mezőben keressen rá az alkalmazás megjelenített nevére a következő táblából.</span><span class="sxs-lookup"><span data-stu-id="0c768-271">In the **Select principal** field, search for the application display name from the following table.</span></span>
        4. <span data-ttu-id="0c768-272">Válassza ki a **Kiválasztás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0c768-272">Select **Select**.</span></span>
        5. <span data-ttu-id="0c768-273">Válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0c768-273">Select **Add**.</span></span>
        6. <span data-ttu-id="0c768-274">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0c768-274">Select **Save**.</span></span>

        | <span data-ttu-id="0c768-275">Pályázat</span><span class="sxs-lookup"><span data-stu-id="0c768-275">Application</span></span>                                              | <span data-ttu-id="0c768-276">Engedélyek</span><span class="sxs-lookup"><span data-stu-id="0c768-276">Permissions</span></span> |
        |----------------------------------------------------------|-------------|
        | <span data-ttu-id="0c768-277">A létrehozott új alkalmazás megjelenített neve</span><span class="sxs-lookup"><span data-stu-id="0c768-277">The display name of the new application that you created</span></span> | <span data-ttu-id="0c768-278">Kérés, listázás</span><span class="sxs-lookup"><span data-stu-id="0c768-278">Get, List</span></span>   |
        | <span data-ttu-id="0c768-279">**Microsoft Dynamics ERP mikroszolgáltatások**</span><span class="sxs-lookup"><span data-stu-id="0c768-279">**Microsoft Dynamics ERP Microservices**</span></span>                 | <span data-ttu-id="0c768-280">Kérés, listázás</span><span class="sxs-lookup"><span data-stu-id="0c768-280">Get, List</span></span>   |

6. <span data-ttu-id="0c768-281">Szerepkörök hozzárendelése a tárfiókhoz:</span><span class="sxs-lookup"><span data-stu-id="0c768-281">Assign roles to access the storage account:</span></span>

    1. <span data-ttu-id="0c768-282">A [Azure-portál](https://portal.azure.com) webhelyen nyissa meg a korábban létrehozott tárfiókot.</span><span class="sxs-lookup"><span data-stu-id="0c768-282">In the [Azure portal](https://portal.azure.com), open the storage account that you created earlier.</span></span>
    2. <span data-ttu-id="0c768-283">Válassza ki az **Access Control (IAM)** lehetőséget, majd válassza ki a **Szerepkör hozzárendeléseket**.</span><span class="sxs-lookup"><span data-stu-id="0c768-283">Select **Access Control (IAM)**, and then select **Role Assignments**.</span></span>
    3. <span data-ttu-id="0c768-284">Válassza a **Hozzáadás, Szerepkör-hozzárendelés hozzáadása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0c768-284">Select **Add, Add Role Assignment**.</span></span>
    4. <span data-ttu-id="0c768-285">Hajtsa végre az alábbi lépéseket mindegyik alkalmazáshoz a következő táblában:</span><span class="sxs-lookup"><span data-stu-id="0c768-285">For each application in the following table, follow these steps:</span></span>

        1. <span data-ttu-id="0c768-286">Válassza ki a szerepkört az alábbi táblából.</span><span class="sxs-lookup"><span data-stu-id="0c768-286">Select the role from the following table.</span></span>
        2. <span data-ttu-id="0c768-287">A **Hozzáférés hozzárendelése** mezőben hagyja meg az **Azure AD felhasználó, csoport vagy szolgáltatásnév** értéket.</span><span class="sxs-lookup"><span data-stu-id="0c768-287">Leave the **Assign access to** field set to **Azure AD user, group, or service principal**.</span></span>
        3. <span data-ttu-id="0c768-288">A **Kiválasztás** mezőben adja meg a következő táblában szereplő alkalmazást.</span><span class="sxs-lookup"><span data-stu-id="0c768-288">In the **Select** field, enter the application from the following table.</span></span>
        4. <span data-ttu-id="0c768-289">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0c768-289">Select **Save**.</span></span>

        | <span data-ttu-id="0c768-290">Pályázat</span><span class="sxs-lookup"><span data-stu-id="0c768-290">Application</span></span>                                              | <span data-ttu-id="0c768-291">Szerep</span><span class="sxs-lookup"><span data-stu-id="0c768-291">Role</span></span>                        |
        |----------------------------------------------------------|-----------------------------|
        | <span data-ttu-id="0c768-292">A létrehozott új alkalmazás megjelenített neve</span><span class="sxs-lookup"><span data-stu-id="0c768-292">The display name of the new application that you created</span></span> | <span data-ttu-id="0c768-293">Tulajdonos</span><span class="sxs-lookup"><span data-stu-id="0c768-293">Owner</span></span>                       |
        | <span data-ttu-id="0c768-294">A létrehozott új alkalmazás megjelenített neve</span><span class="sxs-lookup"><span data-stu-id="0c768-294">The display name of the new application that you created</span></span> | <span data-ttu-id="0c768-295">Hozzájáruló</span><span class="sxs-lookup"><span data-stu-id="0c768-295">Contributor</span></span>                 |
        | <span data-ttu-id="0c768-296">A létrehozott új alkalmazás megjelenített neve</span><span class="sxs-lookup"><span data-stu-id="0c768-296">The display name of the new application that you created</span></span> | <span data-ttu-id="0c768-297">Tárfiók közreműködője</span><span class="sxs-lookup"><span data-stu-id="0c768-297">Storage Account Contributor</span></span> |
        | <span data-ttu-id="0c768-298">A létrehozott új alkalmazás megjelenített neve</span><span class="sxs-lookup"><span data-stu-id="0c768-298">The display name of the new application that you created</span></span> | <span data-ttu-id="0c768-299">Tárolási blobadatok tulajdonosa</span><span class="sxs-lookup"><span data-stu-id="0c768-299">Storage Blob Data Owner</span></span>     |
        | <span data-ttu-id="0c768-300">**AI Builder engedélyezési szolgáltatás**</span><span class="sxs-lookup"><span data-stu-id="0c768-300">**AI Builder Authorization Service**</span></span>                     | <span data-ttu-id="0c768-301">Tárolási blobadatok olvasója</span><span class="sxs-lookup"><span data-stu-id="0c768-301">Storage Blob Data Reader</span></span>    |

# <a name="azure-cli"></a>[<span data-ttu-id="0c768-302">Azure parancssori felület</span><span class="sxs-lookup"><span data-stu-id="0c768-302">Azure CLI</span></span>](#tab/azure-azure-cli)

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



## <a name="configure-the-data-lake"></a><span data-ttu-id="0c768-303">A Data Lake konfigurálása</span><span class="sxs-lookup"><span data-stu-id="0c768-303">Configure the data lake</span></span>

<span data-ttu-id="0c768-304">Hajtsa végre az alábbi lépéseket, ha az Azure Data Lake-bővítményt hozzá szeretné adni a környezethez az LCS használatával.</span><span class="sxs-lookup"><span data-stu-id="0c768-304">Follow these steps to use LCS to add the Azure Data Lake add-in to the environment.</span></span>

1. <span data-ttu-id="0c768-305">Jelentkezzen be az LCS-be, majd a lap jobb oldalán látható környezet neve alatt válassza ki a **Minden részlet** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0c768-305">Sign in to LCS, and then, under the environment name on the right side of the page, select **Full Details**.</span></span>
2. <span data-ttu-id="0c768-306">A **Környezeti bővítmények** szakaszban válassza az **Új bővítmény telepítése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0c768-306">In the **Environment add-ins** section, select **Install a new add-in**.</span></span>
3. <span data-ttu-id="0c768-307">Válassza a **Data Lake exportálása** bővítményt.</span><span class="sxs-lookup"><span data-stu-id="0c768-307">Select the **Export to Data Lake** add-in.</span></span>
4. <span data-ttu-id="0c768-308">Adja meg az alábbi értékeket.</span><span class="sxs-lookup"><span data-stu-id="0c768-308">Enter the following values.</span></span>

    | <span data-ttu-id="0c768-309">Érték</span><span class="sxs-lookup"><span data-stu-id="0c768-309">Value</span></span>                                                              | <span data-ttu-id="0c768-310">Leírás</span><span class="sxs-lookup"><span data-stu-id="0c768-310">Description</span></span> |
    |--------------------------------------------------------------------|-------------|
    | <span data-ttu-id="0c768-311">Az Azure-előfizetés bérlőazonosítója, ahol a Key Vault található</span><span class="sxs-lookup"><span data-stu-id="0c768-311">Tenant ID of the Azure Subscription where the Key Vault is located</span></span> | <span data-ttu-id="0c768-312">A bérlőazonosító, ahol a tárfiók, az alkalmazások és a kulcstartók találhatók.</span><span class="sxs-lookup"><span data-stu-id="0c768-312">The tenant ID where the storage account, apps, and key vaults are located.</span></span> <span data-ttu-id="0c768-313">Ha meg szeretné találni ezt az értéket, nyissa meg az [Azure-portál](https://portal.azure.com) lehetőséget, menjen ide: **Azure Active Directory**, és másolja át a **Bérlőazonosító** értéket.</span><span class="sxs-lookup"><span data-stu-id="0c768-313">To find this value, open the [Azure portal](https://portal.azure.com), go to **Azure Active Directory**, and copy the **Tenant ID** value.</span></span> |
    | <span data-ttu-id="0c768-314">Adja meg a Key Vault DNS-nevét.</span><span class="sxs-lookup"><span data-stu-id="0c768-314">Provide the DNS name of your Key Vault</span></span>                             | <span data-ttu-id="0c768-315">A kulcstartó DNS-neve (például: `https://customkeyvault.vault.azure.net/`).</span><span class="sxs-lookup"><span data-stu-id="0c768-315">The DNS name of the key vault, such as `https://customkeyvault.vault.azure.net/`.</span></span> <span data-ttu-id="0c768-316">(Ez az érték megegyezik az entitásüzletben használt DNS-névvel.)</span><span class="sxs-lookup"><span data-stu-id="0c768-316">(This value matches the DNS name that is used in the entity store.)</span></span> |
    | <span data-ttu-id="0c768-317">Adja meg a tárfiók nevét tartalmazó titkos kódot</span><span class="sxs-lookup"><span data-stu-id="0c768-317">Provide the secret that contains the name of the storage account</span></span>   | <span data-ttu-id="0c768-318">**storage-account-name**</span><span class="sxs-lookup"><span data-stu-id="0c768-318">**storage-account-name**</span></span> |
    | <span data-ttu-id="0c768-319">Titkós kód neve az alkalmazásazonosítóhoz, amelyet a Data Lake eléréséhez használnak</span><span class="sxs-lookup"><span data-stu-id="0c768-319">Secret Name for App ID to be used for accessing Data Lake</span></span>          | <span data-ttu-id="0c768-320">**alkalmazás azonosítója**</span><span class="sxs-lookup"><span data-stu-id="0c768-320">**app-id**</span></span> |
    | <span data-ttu-id="0c768-321">Az alkalmazásazonosítóval használandó titkos kód neve</span><span class="sxs-lookup"><span data-stu-id="0c768-321">Secret name to be used with App ID</span></span>                                 | <span data-ttu-id="0c768-322">**alkalmazás titkos kódja**</span><span class="sxs-lookup"><span data-stu-id="0c768-322">**app-secret**</span></span> |

5. <span data-ttu-id="0c768-323">Fogadja el a feltételeket, és válassza a **Telepítés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0c768-323">Agree to the terms, and select **Install**.</span></span>

<span data-ttu-id="0c768-324">A bővítményt néhány percen belül telepíti a program.</span><span class="sxs-lookup"><span data-stu-id="0c768-324">The add-in will be installed within a few minutes.</span></span>

## <a name="configure-ai-builder"></a><span data-ttu-id="0c768-325">AI Builder konfigurálása</span><span class="sxs-lookup"><span data-stu-id="0c768-325">Configure AI Builder</span></span>

1. <span data-ttu-id="0c768-326">Jelentkezzen be a LCS-ba, majd nyissa meg a **Környezet részletei** oldalt.</span><span class="sxs-lookup"><span data-stu-id="0c768-326">Sign in to LCS, and open the **Environment details** page.</span></span>
2. <span data-ttu-id="0c768-327">Görgessen le a **Környezeti bővítmények** szakaszhoz.</span><span class="sxs-lookup"><span data-stu-id="0c768-327">Scroll to the **Environment add-ins** section.</span></span> <span data-ttu-id="0c768-328">Tekintse meg azokat a bővítményeket, amelyek már telepítve vannak ebben a környezetben.</span><span class="sxs-lookup"><span data-stu-id="0c768-328">You should see the add-ins that are already installed in this environment.</span></span> <span data-ttu-id="0c768-329">Ha a **Data Lake exportálása** bővítmény nincs a többi között, konfigurálja ezt a bővítményt.</span><span class="sxs-lookup"><span data-stu-id="0c768-329">If the **Export to Data Lake** add-in isn't among them, configure this add-in.</span></span>
3. <span data-ttu-id="0c768-330">Válassza ki az **Információk megszerzése** bővítményt.</span><span class="sxs-lookup"><span data-stu-id="0c768-330">Select the **Get insights** add-in.</span></span>
4. <span data-ttu-id="0c768-331">Az **Információk megszerzése** bővítmény részletei oldalon adja meg az alábbi értékeket.</span><span class="sxs-lookup"><span data-stu-id="0c768-331">On the **Get insights** add-in details page, enter the following values.</span></span>

    | <span data-ttu-id="0c768-332">Érték</span><span class="sxs-lookup"><span data-stu-id="0c768-332">Value</span></span>                                                    | <span data-ttu-id="0c768-333">Leírás</span><span class="sxs-lookup"><span data-stu-id="0c768-333">Description</span></span> |
    |----------------------------------------------------------|-------------|
    | <span data-ttu-id="0c768-334">CDS szervezet URL-címe</span><span class="sxs-lookup"><span data-stu-id="0c768-334">CDS Organization URL</span></span>                                     | <span data-ttu-id="0c768-335">A Dataverse-szervezet URL-címe felülről másolva.</span><span class="sxs-lookup"><span data-stu-id="0c768-335">The Dataverse organization URL copied from above.</span></span> |
    | <span data-ttu-id="0c768-336">CDS szerv. azon.</span><span class="sxs-lookup"><span data-stu-id="0c768-336">CDS Org ID</span></span>                                               | <span data-ttu-id="0c768-337">A Dataverse-szervezet azonosítója felülről másolva.</span><span class="sxs-lookup"><span data-stu-id="0c768-337">The Dataverse organization ID copied from above.</span></span> |
5. <span data-ttu-id="0c768-338">Engedélyezze az **Ez az alapértelmezett CDS-környezet a bérlő számára?** elemet.</span><span class="sxs-lookup"><span data-stu-id="0c768-338">Enable **Is this the default environment for you Tenant**.</span></span>
    
## <a name="configure-the-entity-store"></a><span data-ttu-id="0c768-339">Az entitásáruház konfigurálása</span><span class="sxs-lookup"><span data-stu-id="0c768-339">Configure the entity store</span></span>

<span data-ttu-id="0c768-340">Hajtsa végre az alábbi lépéseket, ha be szeretné állítani az entitásáruházat a Pénzügy környezetben.</span><span class="sxs-lookup"><span data-stu-id="0c768-340">Follow these steps to set up the entity store in your Finance environment.</span></span>

1. <span data-ttu-id="0c768-341">Lépjen a **Rendszerfelügyelet \> Beállítás \> Rendszerparaméterek \> Adatkapcsolatok** elemre.</span><span class="sxs-lookup"><span data-stu-id="0c768-341">Go to **System administration \> Setup \> System parameters \> Data connections**.</span></span>
2. <span data-ttu-id="0c768-342">A következő Key Vault-mezők beállítása:</span><span class="sxs-lookup"><span data-stu-id="0c768-342">Set the following key vault fields:</span></span>

    - <span data-ttu-id="0c768-343">**Alkalmazás (kliens) azonosítója** – Adja meg a korábban létrehozott alkalmazáskliens azonosítóját.</span><span class="sxs-lookup"><span data-stu-id="0c768-343">**Application (client) ID** – Enter the application client ID that you created earlier.</span></span>
    - <span data-ttu-id="0c768-344">**Alkalmazás titkos kódja** – adja meg azt a titkos kódot, amelyet a korábban létrehozott alkalmazáshoz mentett.</span><span class="sxs-lookup"><span data-stu-id="0c768-344">**Application Secret** – Enter the secret that you saved for the application that you created earlier.</span></span>
    - <span data-ttu-id="0c768-345">**DNS neve** – A korábban létrehozott alkalmazásnál megkeresheti a tartománynév-rendszer (DNS) nevét.</span><span class="sxs-lookup"><span data-stu-id="0c768-345">**DNS name** – You can find the Domain Name System (DNS) name on the application details page for the application that you created earlier.</span></span>
    - <span data-ttu-id="0c768-346">**Titkos kód neve** – Adja meg a **storage-account-connection-string** értéket.</span><span class="sxs-lookup"><span data-stu-id="0c768-346">**Secret name** – Enter **storage-account-connection-string**.</span></span>
3. <span data-ttu-id="0c768-347">Engedélyezze a **Data Lake-integráció engedélyezése** elemet.</span><span class="sxs-lookup"><span data-stu-id="0c768-347">Enable **Enable Data Lake integration**.</span></span>
4. <span data-ttu-id="0c768-348">Válassza ki az **Azure Key Vault – Teszt** elemet, és ellenőrizze, hogy nincsenek hibák.</span><span class="sxs-lookup"><span data-stu-id="0c768-348">Select **Test Azure Key Vault** and verify there are no errors.</span></span>
5. <span data-ttu-id="0c768-349">Válassza ki az **Azure-tárhely – Teszt** elemet, és ellenőrizze, hogy nincsenek hibák.</span><span class="sxs-lookup"><span data-stu-id="0c768-349">Select **Test Azure storage** and verify there are no errors.</span></span>

## <a name="feedback-and-support"></a><span data-ttu-id="0c768-350">Visszajelzés és támogatás</span><span class="sxs-lookup"><span data-stu-id="0c768-350">Feedback and support</span></span>

<span data-ttu-id="0c768-351">Kérjük, küldjön egy e-mailt az [Ügyfél fizetési elemzés (előzetes verzió)](mailto:fiap@microsoft.com) címre, ha visszajelzést szeretne adni, vagy támogatásra van szüksége.</span><span class="sxs-lookup"><span data-stu-id="0c768-351">Please send an email to [Customer payment insights (Preview)](mailto:fiap@microsoft.com) if you are interested in providing feedback or need support.</span></span>

## <a name="privacy-notice"></a><span data-ttu-id="0c768-352">Adatvédelmi nyilatkozat</span><span class="sxs-lookup"><span data-stu-id="0c768-352">Privacy notice</span></span>

<span data-ttu-id="0c768-353">Az előzetes verziók (1) kevesebb adatvédelmi és biztonsági intézkedést alkalmazhatnak, mint a Dynamics 365 Finance and Operations szolgáltatás (2) és nem vonatkozik a szolgáltatásiszint-szerződés (SLA) ehhez a szolgáltatáshoz, (3) nem használhatók olyan személyes adatok vagy más adatok feldolgozásához, melyekhez törvényi vagy jogszabályi megfelelési követelmények tartoznak, és (4) korlátozott támogatás tartozik hozzá.</span><span class="sxs-lookup"><span data-stu-id="0c768-353">Previews (1) might use less privacy and fewer security measures than the Dynamics 365 Finance and Operations service, (2) aren't included in the service level agreement (SLA) for this service, (3) should not be used to process personal data or other data that is subject to legal or regulatory compliance requirements, and (4) have limited support.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
