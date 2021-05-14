---
title: Pénzügyi információk konfigurációja (előzetes verzió)
description: Ez a témakör azokat a konfigurációs lépéseket ismerteti, amelyek lehetővé teszik a rendszer számára a Pénzügyi információkban elérhető képességek használatát.
author: ShivamPandey-msft
ms.date: 11/25/2020
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
ms.openlocfilehash: 60e4d69157d7b73bd9e47310adae320687230080
ms.sourcegitcommit: a202bf67c3c2c054e2a47cb7b3145cb7c0ee635e
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/25/2021
ms.locfileid: "5941226"
---
# <a name="configuration-for-finance-insights-preview"></a><span data-ttu-id="f1b2d-103">Pénzügyi információk konfigurációja (előzetes verzió)</span><span class="sxs-lookup"><span data-stu-id="f1b2d-103">Configuration for Finance insights (preview)</span></span>

[!include [banner](../includes/banner.md)]

[!include [preview banner](../includes/preview-banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="f1b2d-104">A Pénzügyi információk a Microsoft Dynamics 365 Finance és a Microsoft Dataverse, az Azure és az AI Builder funkcióit kombinálva hatékony előrejelző eszközöket biztosítanak a szervezet számára.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-104">Finance insights combines functionality from Microsoft Dynamics 365 Finance with Microsoft Dataverse, Azure, and AI Builder to provide powerful forecasting tools for your organization.</span></span> <span data-ttu-id="f1b2d-105">Ez a témakör azokat a konfigurációs lépéseket ismerteti, amelyek lehetővé teszik a rendszer számára a Pénzügyi információkban elérhető képességek használatát.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-105">This topic explains the configuration steps that will enable your system to use the capabilities that are available in Finance insights.</span></span>

## <a name="deploy-dynamics-365-finance"></a><span data-ttu-id="f1b2d-106">Dynamics 365 Finance üzembe helyezése</span><span class="sxs-lookup"><span data-stu-id="f1b2d-106">Deploy Dynamics 365 Finance</span></span>

<span data-ttu-id="f1b2d-107">A környezetek üzembe helyezéséhez kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-107">Deploy the environments by following these steps.</span></span>

1. <span data-ttu-id="f1b2d-108">A Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásban hozzon létre vagy frissítse a Dynamics 365 Finance környezetet.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-108">In Microsoft Dynamics Lifecycle Services (LCS), create or update a Dynamics 365 Finance environment.</span></span> <span data-ttu-id="f1b2d-109">A környezethez 10.0.11/Platform 35-ös vagy újabb alkalmazásverzióra van szükség.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-109">The environment requires app version 10.0.11/Platform update 35 or later.</span></span>
2. <span data-ttu-id="f1b2d-110">A környezetnek magas rendelkezésre állású (HA) környezetnek kell lennie a tesztkörnyezetben.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-110">The environment must be a high-availability (HA) environment in Sandbox.</span></span> <span data-ttu-id="f1b2d-111">(Az ilyen típusú környezetet 2. szintű környezetnek is nevezik.) További információ: [Környezettervezés](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).</span><span class="sxs-lookup"><span data-stu-id="f1b2d-111">(This type of environment is also known as a Tier-2 environment.) For more information, see [Environment planning](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).</span></span>
3. <span data-ttu-id="f1b2d-112">Ha Contoso Contoso bemutató adatokat használ, további mintaadatokra lesz szüksége az Ügyfélfizetési előrejelzések, a Pénzforgalmi előrejelzések és a Költségvetés-előrejelzések funkciók használatához.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-112">If you're using Contoso demo data, you will require additional sample data to use the Customer payment predictions, Cash flow forecasts, and Budget forecasts features.</span></span> 

## <a name="configure-dataverse"></a><span data-ttu-id="f1b2d-113">Dataverse konfigurálása</span><span class="sxs-lookup"><span data-stu-id="f1b2d-113">Configure Dataverse</span></span>

<span data-ttu-id="f1b2d-114">A következő lépések segítségével konfigurálhatja a Dataverse-t a Finance Insightshez.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-114">Use the following steps to configure Dataverse for Finance insights.</span></span>

1. <span data-ttu-id="f1b2d-115">Nyissa meg a környezet oldalát az LCS-ben, és ellenőrizze, hogy az **Power Platform-Integráció** szakasz már be van-e állítva.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-115">Open the environment page in LCS and verify that the **Power Platform Integration** section is already setup.</span></span>
    1. <span data-ttu-id="f1b2d-116">Ha már be van állítva, akkor a Dynamics 365 Finance-környezethez kapcsolt Dataverse-környezet nevének szerepelnie kell a listában.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-116">If it is already set up, the Dataverse environment name linked to the Dynamics 365 Finance Environment should be listed.</span></span> <span data-ttu-id="f1b2d-117">Másolja a Dataverse-környezet nevét.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-117">Copy the Dataverse environment name.</span></span>
    2. <span data-ttu-id="f1b2d-118">Ha nincs beállítva, kövesse a következő lépéseket:</span><span class="sxs-lookup"><span data-stu-id="f1b2d-118">If it is not set up, follow these steps:</span></span>
        1. <span data-ttu-id="f1b2d-119">Válassza a **Beállítás** gombot a Power Platform-integráció szakaszban.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-119">Select the **Setup** button in the Power Platform Integration section.</span></span> <span data-ttu-id="f1b2d-120">A környezet beállítása akár egy óráig is eltarthat.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-120">It may take up to an hour for the environment to be set up.</span></span>
        2. <span data-ttu-id="f1b2d-121">Ha a Dataverse-környezet sikeresen be van állítva, akkor a Dynamics 365 Finance-környezethez kapcsolt Dataverse-környezet nevének szerepelnie kell a listában.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-121">If the Dataverse environment is successfully set up, the Dataverse environment name linked to the Dynamics 365 Finance Environment should be listed.</span></span> <span data-ttu-id="f1b2d-122">Másolja a Dataverse-környezet nevét.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-122">Copy the Dataverse environment name.</span></span>
> [!NOTE]
> <span data-ttu-id="f1b2d-123">A környezet beállítása után **NE** válassza ki a **Hivatkozás a CDS for Appshoz** gombot.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-123">After completing the environment set up, **DO NOT** select the **Link to CDS for Apps** button.</span></span> <span data-ttu-id="f1b2d-124">Ez nem szükséges a Finance Insightshoz, és letiltja az LCS-kben szükséges környezeti bővítmények befejezéséhez szükséges képességet.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-124">This is not needed for Finance Insights and will disable the ability to complete the required Environment Add-ins in LCS.</span></span>

2. <span data-ttu-id="f1b2d-125">Nyissa meg a [Power Platform felügyeleti központot](https://admin.powerplatform.microsoft.com/), és az alábbi lépések végrehajtásával hozzon létre egy új Dataverse környezetet ugyanabban az Active Directory-bérlőben:</span><span class="sxs-lookup"><span data-stu-id="f1b2d-125">Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com/), and follow these steps to create a new Dataverse environment in the same Active Directory tenant:</span></span>

    1. <span data-ttu-id="f1b2d-126">Nyissa meg a **Környezetek** oldalt.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-126">Open the **Environments** page.</span></span>

        <span data-ttu-id="f1b2d-127">[![Környezetek oldal](./media/power-pltfrm-admin-center.png)](./media/power-pltfrm-admin-center.png)</span><span class="sxs-lookup"><span data-stu-id="f1b2d-127">[![Environments page](./media/power-pltfrm-admin-center.png)](./media/power-pltfrm-admin-center.png)</span></span>

    2. <span data-ttu-id="f1b2d-128">Válassza ki a fent létrehozott Dataverse-környezetet, majd válassza a **Beállítások** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-128">Select the Dataverse environment created above and then select **Settings**.</span></span>
    3. <span data-ttu-id="f1b2d-129">Válassza az **Erőforrások \> Minden örökölt beállítás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-129">Select **Resources \> All Legacy Settings**.</span></span>
    4. <span data-ttu-id="f1b2d-130">A felső navigációs sávon válassza a **Beállítások**, majd a **Testreszabás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-130">On the top navigation bar, select **Settings**, and then select **Customizations**.</span></span>
    5. <span data-ttu-id="f1b2d-131">Válassza a **Fejlesztői erőforrások** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-131">Select **Developer Resources**.</span></span>
    6. <span data-ttu-id="f1b2d-132">Másolja a **Dataverse szervezetazonosító** értékét.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-132">Copy the **Dataverse organization ID** value.</span></span>
    7. <span data-ttu-id="f1b2d-133">A böngésző címsorában jegyezze fel a Dataverse szervezet URL-címét.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-133">In the browser's address bar, make a note of the URL for the Dataverse organization.</span></span> <span data-ttu-id="f1b2d-134">Az URL-cím lehet például `https://org42b2b3d3.crm.dynamics.com`.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-134">For example, the URL might be `https://org42b2b3d3.crm.dynamics.com`.</span></span>

3. <span data-ttu-id="f1b2d-135">Ha a Pénzforgalmi előrejelzések vagy a Költségvetési előrejelzések funkciót kívánja használni, kövesse az alábbi lépéseket a szervezet címjegyzetkorlátjának legalább 50 megabájtra (MB) történő frissítéséhez:</span><span class="sxs-lookup"><span data-stu-id="f1b2d-135">If you plan to use the Cash flow forecasts or Budget forecasts feature, follow these steps to update the annotation limit for your organization to at least 50 megabytes (MB):</span></span>

    1. <span data-ttu-id="f1b2d-136">Nyissa meg a [Power Apps portált](https://make.powerapps.com).</span><span class="sxs-lookup"><span data-stu-id="f1b2d-136">Open the [Power Apps portal](https://make.powerapps.com).</span></span>
    2. <span data-ttu-id="f1b2d-137">Válassza ki az imént létrehozott környezetet, majd a **Speciális beállítások** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-137">Select the environment that you just created, and then select **Advanced settings**.</span></span>
    3. <span data-ttu-id="f1b2d-138">Válassza a **Beállítások \> E-mail konfigurációja** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-138">Select **Settings \> Email Configuration**.</span></span>
    4. <span data-ttu-id="f1b2d-139">Módosítsa a **Maximális fájlméret** mező értékét **51,200-ra**.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-139">Change the value of the **Maximum file size** field to **51,200**.</span></span> <span data-ttu-id="f1b2d-140">(Az értéket kilobájtban \[KB\] kell kifejezni.)</span><span class="sxs-lookup"><span data-stu-id="f1b2d-140">(The value is expressed in kilobytes \[KB\].)</span></span>
    5. <span data-ttu-id="f1b2d-141">A módosítás mentéséhez kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-141">Select **OK** to save your changes.</span></span>

## <a name="configure-the-azure-setup"></a><span data-ttu-id="f1b2d-142">Az Azure beállítások konfigurálása</span><span class="sxs-lookup"><span data-stu-id="f1b2d-142">Configure the Azure setup</span></span>

### <a name="enter-the-dataverse-directory-id-and-the-users-azure-ad-object-id"></a><span data-ttu-id="f1b2d-143">Adja meg a Dataverse címtárazonosítót és a felhasználó Azure AD objektumazonosítóját</span><span class="sxs-lookup"><span data-stu-id="f1b2d-143">Enter the Dataverse directory ID and the user's Azure AD object ID</span></span>

1. <span data-ttu-id="f1b2d-144">Adja meg a Dataverse címtárazonosítót:</span><span class="sxs-lookup"><span data-stu-id="f1b2d-144">Enter the Dataverse directory ID:</span></span>

    1. <span data-ttu-id="f1b2d-145">Nyissa meg az [Azure-portált](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="f1b2d-145">Open the [Azure portal](https://portal.azure.com).</span></span>
    2. <span data-ttu-id="f1b2d-146">Jelentkezzen be a környezet létrehozásához használt felhasználói Dataverse azonosítóval.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-146">Sign in by using the user ID that was used to create the Dataverse environment.</span></span>
    3. <span data-ttu-id="f1b2d-147">Ugorjon ide: **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-147">Go to **Azure Active Directory**.</span></span>
    4. <span data-ttu-id="f1b2d-148">Másolja a **Bérlői azonosító** értékét.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-148">Copy the **Tenant ID** value.</span></span>

2. <span data-ttu-id="f1b2d-149">Itt megadhatja a felhasználó Azure Active Directory (Azure AD) tárgyának azonosítóját:</span><span class="sxs-lookup"><span data-stu-id="f1b2d-149">Enter the user's Azure Active Directory (Azure AD) object ID:</span></span>

    1. <span data-ttu-id="f1b2d-150">Az [Azure-portálon](https://portal.azure.com) nyissa meg a **Felhasználók** lehetőséget, és keresse meg a felhasználót az e-mail címe szerint.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-150">In the [Azure portal](https://portal.azure.com), go to **Users**, and search for the user by email address.</span></span>
    2. <span data-ttu-id="f1b2d-151">A felhasználó nevének kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-151">Select the user's name.</span></span>
    3. <span data-ttu-id="f1b2d-152">Másolja a **Tárgyazonosító** értékét.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-152">Copy the **Object ID** value.</span></span>

### <a name="use-azure-cloud-shell-to-set-up-finance-insights-data-lake-resources"></a><span data-ttu-id="f1b2d-153">Az Azure Cloud Shell használatával állíthatja be a Data Lake-erőforrásokkal kapcsolatos pénzügyi elemzéseket</span><span class="sxs-lookup"><span data-stu-id="f1b2d-153">Use Azure Cloud Shell to set up Finance insights Data Lake resources</span></span>

# <a name="use-a-windows-powershell-script"></a>[<span data-ttu-id="f1b2d-154">Windows PowerShell parancsfájl használata</span><span class="sxs-lookup"><span data-stu-id="f1b2d-154">Use a Windows PowerShell script</span></span>](#tab/use-a-powershell-script)

<span data-ttu-id="f1b2d-155">Egy Windows PowerShell-parancsfájlt adott meg, így egyszerűen beállíthatja az Azure-erőforrásokat, amelyek az [Azure Data Lake exportálásának konfigurálása](../../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md) részben találhatók.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-155">A Windows PowerShell script has been provided, so that you can easily set up the Azure resources that are described in [Configure export to Azure Data Lake](../../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md).</span></span> <span data-ttu-id="f1b2d-156">Ha a manuális beállítást szeretné elvégezni, hagyja ki ezt az eljárást, és folytassa az eljárást a [Manuális beállítás](#manual-setup) szakaszban.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-156">If you prefer to do manual setup, skip this procedure, and continue with the procedure in the [Manual setup](#manual-setup) section.</span></span>

> [!NOTE]
> <span data-ttu-id="f1b2d-157">Kövesse az alábbi lépéseket a PowerShell-parancsfájl futtatásához.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-157">Follow the steps below to run the PowerShell script.</span></span> <span data-ttu-id="f1b2d-158">Lehet, hogy az Azure CLI „Próbálja ki” lehetőség vagy a parancsfájl futtatása a számítógépen nem működik.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-158">The Azure CLI "Try it" option, or running the script on your PC may not work.</span></span>

<span data-ttu-id="f1b2d-159">Kövesse az alábbi lépéseket az Azure konfigurálásához a Windows PowerShell-parancsfájl használatával.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-159">Follow these steps to configure Azure by using the Windows PowerShell script.</span></span> <span data-ttu-id="f1b2d-160">Az Azure-erőforráscsoport, az Azure-erőforrások és az Azure AD alkalmazások létrehozásához jogokkal kell rendelkeznie.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-160">You must have rights to create an Azure resource group, Azure resources, and an Azure AD application.</span></span> <span data-ttu-id="f1b2d-161">A szükséges engedélyekről az [Engedélyek Azure AD ellenőrzése](/azure/active-directory/develop/howto-create-service-principal-portal#permissions-required-for-registering-an-app) témakörben talál további információt.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-161">For information about the required permissions, see [Check Azure AD permissions](/azure/active-directory/develop/howto-create-service-principal-portal#permissions-required-for-registering-an-app).</span></span>

1. <span data-ttu-id="f1b2d-162">Az [Azure-portálon](https://portal.azure.com) nyissa meg a cél Azure-előfizetés.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-162">In the [Azure portal](https://portal.azure.com), go to your target Azure subscription.</span></span> <span data-ttu-id="f1b2d-163">Válassza a **Keresés** mezőtől jobbra lévő **Cloud Shell** gombot.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-163">Select the **Cloud Shell** button to the right of the **Search** field.</span></span>
2. <span data-ttu-id="f1b2d-164">Válassza a **PowerShell** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-164">Select **PowerShell**.</span></span>
3. <span data-ttu-id="f1b2d-165">Hozzon létre tárhelyet, ha a rendszer erre kéri.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-165">Create storage if you're prompted to do so.</span></span>
4. <span data-ttu-id="f1b2d-166">Menjen az **Azure parancssori felület** lapra, és válassza a **Másolás** parancsot.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-166">Go to the **Azure CLI** tab and select **Copy**.</span></span>  
5. <span data-ttu-id="f1b2d-167">Nyissa meg a Jegyzettömböt, és illessze be a PowerShell-parancsfájlt.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-167">Open Notepad and paste the PowerShell script.</span></span> <span data-ttu-id="f1b2d-168">Mentse a fájlt ConfigureDataLake.ps1 néven.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-168">Save the file as ConfigureDataLake.ps1.</span></span>
6. <span data-ttu-id="f1b2d-169">Töltse fel a Windows PowerShell-parancsfájlt a munkamenetbe a Cloud Shellben a feltöltésre szolgáló menülehetőséggel.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-169">Upload the Windows PowerShell script to the session using the menu option for upload in Cloud Shell.</span></span>
7. <span data-ttu-id="f1b2d-170">Futtassa a parancsfájlt: .\ConfigureDataLake.ps1.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-170">Run the script .\ConfigureDataLake.ps1.</span></span>
8. <span data-ttu-id="f1b2d-171">A parancsfájl futtatásához kövesse az utasításokat.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-171">Follow the prompts to run the script.</span></span>
9. <span data-ttu-id="f1b2d-172">A parancsfájl kimenetéből származó információk segítségével telepítse az **Exportálás a Data Lake-be** bővítményt az LCS-ben.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-172">Use the information from the script output to install the **Export to Data Lake** add-in in LCS.</span></span>
10. <span data-ttu-id="f1b2d-173">A parancsfájl kimenetéből származó információk segítségével engedélyezze az entitás tárolását a Pénzügy (**Rendszerfelügyelet \> Rendszer paraméterei \> Adatkapcsolatok**) **Adatkapcsolatok** lapján.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-173">Use the information from the script output to enable the entity store on the **Data connections** page in Finance (**System administration \> System parameters \> Data connections**).</span></span>

### <a name="manual-setup"></a><span data-ttu-id="f1b2d-174">Manuális beállítás</span><span class="sxs-lookup"><span data-stu-id="f1b2d-174">Manual setup</span></span>

#### <a name="add-applications-to-the-azure-ad-tenant"></a><span data-ttu-id="f1b2d-175">Alkalmazások hozzáadása az Azure AD-bérlőhöz</span><span class="sxs-lookup"><span data-stu-id="f1b2d-175">Add applications to the Azure AD tenant</span></span>

1. <span data-ttu-id="f1b2d-176">Az [Azure-portálban](https://portal.azure.com) menjen ide: **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-176">In the [Azure portal](https://portal.azure.com), go to **Azure Active Directory**.</span></span>
2. <span data-ttu-id="f1b2d-177">Válassza a **Vállalati \> alkalmazások kezelése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-177">Select **Manage \> Enterprise applications**.</span></span>
3. <span data-ttu-id="f1b2d-178">Keresse meg a következő alkalmazásokat alkalmazásazonosító szerint.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-178">Search for the following applications by app ID.</span></span>

    | <span data-ttu-id="f1b2d-179">Pályázat</span><span class="sxs-lookup"><span data-stu-id="f1b2d-179">Application</span></span>                              | <span data-ttu-id="f1b2d-180">Alkalmazás azonosítója</span><span class="sxs-lookup"><span data-stu-id="f1b2d-180">App ID</span></span>                               |
    |------------------------------------------|--------------------------------------|
    | <span data-ttu-id="f1b2d-181">Microsoft Dynamics ERP mikroszolgáltatások</span><span class="sxs-lookup"><span data-stu-id="f1b2d-181">Microsoft Dynamics ERP Microservices</span></span>     | <span data-ttu-id="f1b2d-182">0cdb527f-a8d1-4bf8-9436-b352c68682b2</span><span class="sxs-lookup"><span data-stu-id="f1b2d-182">0cdb527f-a8d1-4bf8-9436-b352c68682b2</span></span> |
    | <span data-ttu-id="f1b2d-183">Microsoft Dynamics ERP mikroszolgáltatások CDS</span><span class="sxs-lookup"><span data-stu-id="f1b2d-183">Microsoft Dynamics ERP Microservices CDS</span></span> | <span data-ttu-id="f1b2d-184">703e2651-d3fc-48f5-942c-74274233dba8</span><span class="sxs-lookup"><span data-stu-id="f1b2d-184">703e2651-d3fc-48f5-942c-74274233dba8</span></span> |
    | <span data-ttu-id="f1b2d-185">AI Builder engedélyezési szolgáltatás</span><span class="sxs-lookup"><span data-stu-id="f1b2d-185">AI Builder Authorization Service</span></span>         | <span data-ttu-id="f1b2d-186">ad40333e-9910-4b61-b281-e3aeeb8c3ef3</span><span class="sxs-lookup"><span data-stu-id="f1b2d-186">ad40333e-9910-4b61-b281-e3aeeb8c3ef3</span></span> |

<span data-ttu-id="f1b2d-187">Ha az előző alkalmazások egyikét sem találja, próbálkozzon az alábbi lépésekkel.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-187">If you can't find any of the preceding applications, try the following steps.</span></span>

1. <span data-ttu-id="f1b2d-188">A helyi számítógépen válassza a **Start** menüt, és keresse meg a **powershell** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-188">On your local machine, select the **Start** menu, and search for **powershell**.</span></span>
2. <span data-ttu-id="f1b2d-189">Jelölje ki és tartsa lenyomva (vagy nyomja meg a jobb egérgombot) a **Windows PowerShell** lehetőséget, majd válassza a **Futtatás rendszergazdaként** elemet.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-189">Select and hold (or right-click) **Windows PowerShell**, and then select **Run as administrator**.</span></span>
3. <span data-ttu-id="f1b2d-190">Futtassa a következő parancsot az **AzureAD-modul** telepítéséhez.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-190">Run the following command to install the **AzureAD** module.</span></span>

    `Install-Module -Name AzureAD`

4. <span data-ttu-id="f1b2d-191">Ha egy NuGet szolgáltatóra van szükség a folytatáshoz, válassza az **Y** lehetőséget a telepítéshez.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-191">If a NuGet provider is required to continue, select **Y** to install it.</span></span>
5. <span data-ttu-id="f1b2d-192">Ha „Nem megbízható adattár” üzenet jelenik meg, a folytatáshoz válassza az **Y** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-192">If an "Untrusted repository" message appears, select **Y** to continue.</span></span>
6. <span data-ttu-id="f1b2d-193">Minden hozzáadandó alkalmazáshoz futtassa a következő parancsokat az alkalmazás Azure AD-hoz való hozzáadásához.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-193">For each application that must be added, run the following commands to add the application to Azure AD.</span></span> <span data-ttu-id="f1b2d-194">Amikor a rendszer kéri, jelentkezzen be Azure AD-rendszergazdaként.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-194">When you're prompted, sign in as the Azure AD administrator.</span></span>

    `Connect-AzureAD`

    `New-AzureADServicePrincipal –AppId <AppId>`

#### <a name="create-azure-resources"></a><span data-ttu-id="f1b2d-195">Azure-erőforrások létrehozása</span><span class="sxs-lookup"><span data-stu-id="f1b2d-195">Create Azure resources</span></span>

> [!NOTE]
> <span data-ttu-id="f1b2d-196">Győződjön meg arról, hogy a következő erőforrásokat hozza létre ugyanabban a Azure AD-példányban, mint a Dataverse-környezetben.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-196">Make sure that you create the following resources in the same Azure AD instance as the Dataverse environment.</span></span> <span data-ttu-id="f1b2d-197">Más Azure AD-példányból származó erőforrások nem használhatók.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-197">You can't use resources from a different Azure AD instance.</span></span>

1. <span data-ttu-id="f1b2d-198">Új társzámla létrehozása:</span><span class="sxs-lookup"><span data-stu-id="f1b2d-198">Create a new storage account:</span></span>

    1. <span data-ttu-id="f1b2d-199">Hozzon létre egy társzámlát az [Azure-portálon](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="f1b2d-199">In the [Azure portal](https://portal.azure.com), create a storage account.</span></span>
    2. <span data-ttu-id="f1b2d-200">A **Társzámla létrehozása** párbeszédpanelen adja meg a következő mezőket:</span><span class="sxs-lookup"><span data-stu-id="f1b2d-200">In the **Create storage account** dialog box, set the following fields:</span></span>

        - <span data-ttu-id="f1b2d-201">**Hely** – Válassza ki azt az adatközpontot, ahol a környezet található.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-201">**Location** – Select the data center where your environment is located.</span></span>
        - <span data-ttu-id="f1b2d-202">**Teljesítmény** – Javasoljuk, hogy a **Standard** lehetőséget válassza.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-202">**Performance** – We recommend that you select **Standard**.</span></span>
        - <span data-ttu-id="f1b2d-203">**Fiók fajtája** – A **StorageV2** lehetőséget kell választania.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-203">**Account kind** – You must select **StorageV2**.</span></span>

    3. <span data-ttu-id="f1b2d-204">A **Speciális beállítások** párbeszédpanel **Data Lake Storage Gen2** lehetőséghez válassza az **Engedélyezés** elemet a **Hierarchikus névterek** funkció alatt.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-204">In the **Advanced options** dialog box, for the **Data Lake storage Gen2** option, select **Enable** under the **Hierarchical namespaces** feature.</span></span> <span data-ttu-id="f1b2d-205">Ha letiltja ezt a funkciót, nem használhatja fel a Finance and Operations alkalmazások által olyan szolgáltatások használatával írt adatokat, mint például a Power BI adatfolyamok.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-205">If you disable this feature, you can't consume data that Finance and Operations apps write by using services such as Power BI data flows.</span></span>
    4. <span data-ttu-id="f1b2d-206">Válassza a **Vélemény és létrehozás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-206">Select **Review and create**.</span></span> <span data-ttu-id="f1b2d-207">A központi telepítés befejezése után az új erőforrás megjelenik az Azure-portálon.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-207">When the deployment is completed, the new resource will be shown in the Azure portal.</span></span>
    5. <span data-ttu-id="f1b2d-208">Nyissa meg a létrehozott tárfiókot.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-208">Go to the storage account that you created.</span></span>
    6. <span data-ttu-id="f1b2d-209">A bal oldali menüben válassza a **Hívóbetű** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-209">On the left menu, select **Access keys**.</span></span>
    7. <span data-ttu-id="f1b2d-210">Másolja és mentse a kapcsolati karakterláncot a **Key1** vagy a **Key2** lehetőséghez.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-210">Copy and save the connection string for either **Key1** or **Key2**.</span></span>
    8. <span data-ttu-id="f1b2d-211">Másolja és mentse a tárfiók nevét.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-211">Copy and save the storage account name.</span></span>

2. <span data-ttu-id="f1b2d-212">Új kulcstároló létrehozása:</span><span class="sxs-lookup"><span data-stu-id="f1b2d-212">Create a new key vault:</span></span>

    1. <span data-ttu-id="f1b2d-213">Hozzon létre egy kulcstárolót az [Azure-portálon](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="f1b2d-213">In the [Azure portal](https://portal.azure.com), create a key vault.</span></span>
    2. <span data-ttu-id="f1b2d-214">A **Kulcstartó létrehozása** párbeszédpanel, a **Hely** mezőben jelölje ki azt az adatközpontot, ahol a környezet található.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-214">In the **Create key vault** dialog box, in the **Location** field, select the data center where your environment is located.</span></span>
    3. <span data-ttu-id="f1b2d-215">A kulcstartó létrehozása után jelölje ki a listában, majd válassza ki a **Titkok** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-215">After key vault is created, select it in the list, and then select **Secrets**.</span></span>
    4. <span data-ttu-id="f1b2d-216">Válassza a **Generálás/Importálás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-216">Select **Generate/Import**.</span></span>
    5. <span data-ttu-id="f1b2d-217">A **Titkos kód létrehozása** párbeszédpanel **Feltöltési beállítások** mezőjében válassza a **Manuális** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-217">In the **Create a secret** dialog box, in the **Upload options** field, select **Manual**.</span></span>
    6. <span data-ttu-id="f1b2d-218">Adja meg a titkos kód nevét.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-218">Enter a name for the secret.</span></span> <span data-ttu-id="f1b2d-219">Jegyezze fel a nevet, mert később meg kell adnia.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-219">Make a note of the name, because you will have to provide it later.</span></span>
    7. <span data-ttu-id="f1b2d-220">Az **Érték** mezőbe írja be azt a kapcsolati karakterláncot, amelyet a korábbi eljárásban a tárfiókból nyert.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-220">In the **Value** field, enter the connection string that you obtained from the storage account in the previous procedure.</span></span>
    8. <span data-ttu-id="f1b2d-221">Válassza ki az **Engedélyezés**, majd a **Létrehozás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-221">Select **Enabled**, and then select **Create**.</span></span> <span data-ttu-id="f1b2d-222">A rendszer létrehozta a titkot, és hozzáadta a Kulcstartót.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-222">The secret is created and added to Key Vault.</span></span>
    9. <span data-ttu-id="f1b2d-223">Nyissa meg a **Kulcstartó áttekintése** lehetőséget, és jegyezze fel a DNS-nevet.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-223">Go to the **Key Vault Overview**, and make a note of the DNS name.</span></span>

3. <span data-ttu-id="f1b2d-224">Azure AD alkalmazás létrehozása és regisztrálása:</span><span class="sxs-lookup"><span data-stu-id="f1b2d-224">Create and register an Azure AD application:</span></span>

    1. <span data-ttu-id="f1b2d-225">Az [Azure portálon](https://portal.azure.com) menjen ide: **Azure Active Directory**, majd válassza az **Alkalmazás regisztrálása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-225">In the [Azure portal](https://portal.azure.com), go to **Azure Active Directory**, and then select **App registrations**.</span></span>
    2. <span data-ttu-id="f1b2d-226">Válassza ki az **Új alkalmazásregisztráció** lehetőséget, és állítsa be a következő mezőket:</span><span class="sxs-lookup"><span data-stu-id="f1b2d-226">Select **New application registration**, and set the following fields:</span></span>

        - <span data-ttu-id="f1b2d-227">**Név** – Írja be az alkalmazás nevét.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-227">**Name** – Enter the name of the app.</span></span>
        - <span data-ttu-id="f1b2d-228">**Alkalmazás típusa** – válassza ki a **webes API-t**.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-228">**Application type** – Select **Web API**.</span></span>
        - <span data-ttu-id="f1b2d-229">**URI-beállítás átirányítása** – Adja meg a Dynamics 365 példány URL-címét, például: `https://yourdynamicsinstance.dynamics.com/auth`.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-229">**Redirect URI setup** – Enter the URL for your Dynamics 365 instance, such as, `https://yourdynamicsinstance.dynamics.com/auth`.</span></span>

    3. <span data-ttu-id="f1b2d-230">Nyissa meg az imént létrehozott alkalmazást, és másolja, majd mentse az **Alkalmazás (kliens) azonosítójának** értékét.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-230">Go to the app that you just created, and copy and save its **Application (client) ID** value.</span></span> <span data-ttu-id="f1b2d-231">Ezt az értéket később kell megadni, amikor beállítja a kulcstartót.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-231">You will have to provide this value later, when you set up the key vault.</span></span>
    4. <span data-ttu-id="f1b2d-232">Nyissa meg az **API-engedélyek** lehetőséget, majd kövesse az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="f1b2d-232">Go to **API permissions**, and follow these steps:</span></span>

        1. <span data-ttu-id="f1b2d-233">Válassza az **Engedély hozzáadása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-233">Select **Add a permission**.</span></span>
        2. <span data-ttu-id="f1b2d-234">Válassza ki az **Azure kulcstartó** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-234">Select **Azure Key vault**.</span></span>
        3. <span data-ttu-id="f1b2d-235">A delegált engedélyek kiválasztása után válassza ki a **felhasználó\_megszemélyesítését**.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-235">After you select delegated permissions, select **user\_impersonation**.</span></span>
        4. <span data-ttu-id="f1b2d-236">Válassza az **Engedélyek hozzáadása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-236">Select **Add permissions**.</span></span>

    5. <span data-ttu-id="f1b2d-237">Az alkalmazás menüjében válassza ki a **Tanúsítványok \& titkai** lehetőséget, majd a Key Vault létrehozásához hajtsa végre az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="f1b2d-237">On the menu for the app, select **Certificates \& secrets**, and then follow these steps to create Key Vault secrets:</span></span>

        1. <span data-ttu-id="f1b2d-238">Válassza ki az **Új titkos ügyfélkód** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-238">Select **New client secret**.</span></span>
        2. <span data-ttu-id="f1b2d-239">Adjon meg egy nevet a **Kulcsleírás** mezőben.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-239">In the **Key Description** field, enter a name.</span></span>
        3. <span data-ttu-id="f1b2d-240">Válasszon ki egy időtartamot, majd a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-240">Select a duration, and then select **Add**.</span></span> <span data-ttu-id="f1b2d-241">Az **Érték** mezőben egy titkos kód jön létre.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-241">A secret is generated in the **Value** field.</span></span>
        4. <span data-ttu-id="f1b2d-242">A titkos kód értékének másolása és mentése.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-242">Copy and save the secret value.</span></span>

4. <span data-ttu-id="f1b2d-243">Key Vault titkos kódok létrehozása:</span><span class="sxs-lookup"><span data-stu-id="f1b2d-243">Create Key Vault secrets:</span></span>

    1. <span data-ttu-id="f1b2d-244">Menjen a korábban létrehozott kulcstartóhoz, és válassza ki a **Titkokat**.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-244">Go to the key vault that you created earlier, and select **Secrets**.</span></span>
    2. <span data-ttu-id="f1b2d-245">Hajtsa végre az alábbi lépéseket mindegyik titkos kód névhez a következő táblában:</span><span class="sxs-lookup"><span data-stu-id="f1b2d-245">For each secret name in the following table, follow these steps:</span></span>

        1. <span data-ttu-id="f1b2d-246">Válassza a **Generálás/Importálás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-246">Select **Generate/Import**.</span></span>
        2. <span data-ttu-id="f1b2d-247">A **Titkos kód létrehozása** párbeszédpanel **Feltöltési beállítások** mezőjében válassza a **Manuális** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-247">In the **Create a secret** dialog box, in the **Upload options** field, select **Manual**.</span></span>
        3. <span data-ttu-id="f1b2d-248">A következő táblából hozza létre a titkos kód nevét és értékét.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-248">Create the secret name and value from the following table.</span></span>
        4. <span data-ttu-id="f1b2d-249">Válassza ki az **Engedélyezés**, majd a **Létrehozás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-249">Select **Enabled**, and then select **Create**.</span></span> <span data-ttu-id="f1b2d-250">A rendszer létrehozta a titkot, és hozzáadta a Kulcstartót.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-250">The secret is created and added to Key Vault.</span></span>

        | <span data-ttu-id="f1b2d-251">Titkos név</span><span class="sxs-lookup"><span data-stu-id="f1b2d-251">Secret name</span></span>                       | <span data-ttu-id="f1b2d-252">Titkos kód értéke</span><span class="sxs-lookup"><span data-stu-id="f1b2d-252">Secret value</span></span>                                                                                |
        |-----------------------------------|---------------------------------------------------------------------------------------------|
        | <span data-ttu-id="f1b2d-253">alkalmazás azonosítója</span><span class="sxs-lookup"><span data-stu-id="f1b2d-253">app-id</span></span>                            | <span data-ttu-id="f1b2d-254">A korábban létrehozott alkalmazás alkalmazásazonosítója</span><span class="sxs-lookup"><span data-stu-id="f1b2d-254">The app ID of the application that you created earlier</span></span>                                      |
        | <span data-ttu-id="f1b2d-255">alkalmazás titkos kódja</span><span class="sxs-lookup"><span data-stu-id="f1b2d-255">app-secret</span></span>                        | <span data-ttu-id="f1b2d-256">A korábban mentett titkos ügyfélkód</span><span class="sxs-lookup"><span data-stu-id="f1b2d-256">The client secret that you saved earlier</span></span>                                                    |
        | <span data-ttu-id="f1b2d-257">storage-account-name</span><span class="sxs-lookup"><span data-stu-id="f1b2d-257">storage-account-name</span></span>              | <span data-ttu-id="f1b2d-258">A korábban létrehozott tárfiók neve, például **storageaccount1**</span><span class="sxs-lookup"><span data-stu-id="f1b2d-258">The name of the storage account that you created earlier, such as **storageaccount1**</span></span>       |
        | <span data-ttu-id="f1b2d-259">storage-account-connection-string</span><span class="sxs-lookup"><span data-stu-id="f1b2d-259">storage-account-connection-string</span></span> | <span data-ttu-id="f1b2d-260">A tárfiók **Elérési kulcsok** lapjáról átmásolt kapcsolati karakterlánc</span><span class="sxs-lookup"><span data-stu-id="f1b2d-260">The connection string that you copied from the **Access keys** page for the storage account</span></span> |

5. <span data-ttu-id="f1b2d-261">Az alkalmazás engedélyezése a kulcstartó eléréséhez:</span><span class="sxs-lookup"><span data-stu-id="f1b2d-261">Authorize the application to access the key vault:</span></span>

    1. <span data-ttu-id="f1b2d-262">A [Azure-portál](https://portal.azure.com) webhelyen nyissa meg a korábban létrehozott kulcstartót.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-262">In the [Azure portal](https://portal.azure.com), open the key vault that you created earlier.</span></span>
    2. <span data-ttu-id="f1b2d-263">Válassza ki a hozzáférési szabályzatokat.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-263">Select the access policies.</span></span>
    3. <span data-ttu-id="f1b2d-264">Hajtsa végre az alábbi lépéseket mindegyik alkalmazáshoz a következő táblában:</span><span class="sxs-lookup"><span data-stu-id="f1b2d-264">For each application in the following table, follow these steps:</span></span>

        1. <span data-ttu-id="f1b2d-265">Válassza a **Hozzáférési szabályzat hozzáadása** elemet a hozzáférési szabályzat létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-265">Select **Add Access Policy** to create an access policy.</span></span>
        2. <span data-ttu-id="f1b2d-266">A **Titkos engedélyek** mezőben válassza ki a következő táblában szereplő engedélyeket.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-266">In the **Secret permissions** field, select the permissions from the following table.</span></span>
        3. <span data-ttu-id="f1b2d-267">A **Résztvevő kiválasztása** mezőben keressen rá az alkalmazás megjelenített nevére a következő táblából.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-267">In the **Select principal** field, search for the application display name from the following table.</span></span>
        4. <span data-ttu-id="f1b2d-268">Válassza ki a **Kiválasztás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-268">Select **Select**.</span></span>
        5. <span data-ttu-id="f1b2d-269">Válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-269">Select **Add**.</span></span>
        6. <span data-ttu-id="f1b2d-270">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-270">Select **Save**.</span></span>

        | <span data-ttu-id="f1b2d-271">Pályázat</span><span class="sxs-lookup"><span data-stu-id="f1b2d-271">Application</span></span>                                              | <span data-ttu-id="f1b2d-272">Engedélyek</span><span class="sxs-lookup"><span data-stu-id="f1b2d-272">Permissions</span></span> |
        |----------------------------------------------------------|-------------|
        | <span data-ttu-id="f1b2d-273">A létrehozott új alkalmazás megjelenített neve</span><span class="sxs-lookup"><span data-stu-id="f1b2d-273">The display name of the new application that you created</span></span> | <span data-ttu-id="f1b2d-274">Kérés, listázás</span><span class="sxs-lookup"><span data-stu-id="f1b2d-274">Get, List</span></span>   |
        | <span data-ttu-id="f1b2d-275">**Microsoft Dynamics ERP mikroszolgáltatások**</span><span class="sxs-lookup"><span data-stu-id="f1b2d-275">**Microsoft Dynamics ERP Microservices**</span></span>                 | <span data-ttu-id="f1b2d-276">Kérés, listázás</span><span class="sxs-lookup"><span data-stu-id="f1b2d-276">Get, List</span></span>   |

6. <span data-ttu-id="f1b2d-277">Szerepkörök hozzárendelése a tárfiókhoz:</span><span class="sxs-lookup"><span data-stu-id="f1b2d-277">Assign roles to access the storage account:</span></span>

    1. <span data-ttu-id="f1b2d-278">A [Azure-portál](https://portal.azure.com) webhelyen nyissa meg a korábban létrehozott tárfiókot.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-278">In the [Azure portal](https://portal.azure.com), open the storage account that you created earlier.</span></span>
    2. <span data-ttu-id="f1b2d-279">Válassza ki az **Access Control (IAM)** lehetőséget, majd válassza ki a **Szerepkör hozzárendeléseket**.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-279">Select **Access Control (IAM)**, and then select **Role Assignments**.</span></span>
    3. <span data-ttu-id="f1b2d-280">Válassza a **Hozzáadás, Szerepkör-hozzárendelés hozzáadása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-280">Select **Add, Add Role Assignment**.</span></span>
    4. <span data-ttu-id="f1b2d-281">Hajtsa végre az alábbi lépéseket mindegyik alkalmazáshoz a következő táblában:</span><span class="sxs-lookup"><span data-stu-id="f1b2d-281">For each application in the following table, follow these steps:</span></span>

        1. <span data-ttu-id="f1b2d-282">Válassza ki a szerepkört az alábbi táblából.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-282">Select the role from the following table.</span></span>
        2. <span data-ttu-id="f1b2d-283">A **Hozzáférés hozzárendelése** mezőben hagyja meg az **Azure AD felhasználó, csoport vagy szolgáltatásnév** értéket.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-283">Leave the **Assign access to** field set to **Azure AD user, group, or service principal**.</span></span>
        3. <span data-ttu-id="f1b2d-284">A **Kiválasztás** mezőben adja meg a következő táblában szereplő alkalmazást.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-284">In the **Select** field, enter the application from the following table.</span></span>
        4. <span data-ttu-id="f1b2d-285">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-285">Select **Save**.</span></span>

        | <span data-ttu-id="f1b2d-286">Pályázat</span><span class="sxs-lookup"><span data-stu-id="f1b2d-286">Application</span></span>                                              | <span data-ttu-id="f1b2d-287">Szerep</span><span class="sxs-lookup"><span data-stu-id="f1b2d-287">Role</span></span>                        |
        |----------------------------------------------------------|-----------------------------|
        | <span data-ttu-id="f1b2d-288">A létrehozott új alkalmazás megjelenített neve</span><span class="sxs-lookup"><span data-stu-id="f1b2d-288">The display name of the new application that you created</span></span> | <span data-ttu-id="f1b2d-289">Tulajdonos</span><span class="sxs-lookup"><span data-stu-id="f1b2d-289">Owner</span></span>                       |
        | <span data-ttu-id="f1b2d-290">A létrehozott új alkalmazás megjelenített neve</span><span class="sxs-lookup"><span data-stu-id="f1b2d-290">The display name of the new application that you created</span></span> | <span data-ttu-id="f1b2d-291">Hozzájáruló</span><span class="sxs-lookup"><span data-stu-id="f1b2d-291">Contributor</span></span>                 |
        | <span data-ttu-id="f1b2d-292">A létrehozott új alkalmazás megjelenített neve</span><span class="sxs-lookup"><span data-stu-id="f1b2d-292">The display name of the new application that you created</span></span> | <span data-ttu-id="f1b2d-293">Tárfiók közreműködője</span><span class="sxs-lookup"><span data-stu-id="f1b2d-293">Storage Account Contributor</span></span> |
        | <span data-ttu-id="f1b2d-294">A létrehozott új alkalmazás megjelenített neve</span><span class="sxs-lookup"><span data-stu-id="f1b2d-294">The display name of the new application that you created</span></span> | <span data-ttu-id="f1b2d-295">Tárolási blobadatok tulajdonosa</span><span class="sxs-lookup"><span data-stu-id="f1b2d-295">Storage Blob Data Owner</span></span>     |
        | <span data-ttu-id="f1b2d-296">**AI Builder engedélyezési szolgáltatás**</span><span class="sxs-lookup"><span data-stu-id="f1b2d-296">**AI Builder Authorization Service**</span></span>                     | <span data-ttu-id="f1b2d-297">Tárolási blobadatok olvasója</span><span class="sxs-lookup"><span data-stu-id="f1b2d-297">Storage Blob Data Reader</span></span>    |

# <a name="azure-cli"></a>[<span data-ttu-id="f1b2d-298">Azure parancssori felület</span><span class="sxs-lookup"><span data-stu-id="f1b2d-298">Azure CLI</span></span>](#tab/azure-azure-cli)

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



## <a name="configure-the-data-lake"></a><span data-ttu-id="f1b2d-299">A Data Lake konfigurálása</span><span class="sxs-lookup"><span data-stu-id="f1b2d-299">Configure the data lake</span></span>

<span data-ttu-id="f1b2d-300">Hajtsa végre az alábbi lépéseket, ha az Azure Data Lake-bővítményt hozzá szeretné adni a környezethez az LCS használatával.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-300">Follow these steps to use LCS to add the Azure Data Lake add-in to the environment.</span></span>

1. <span data-ttu-id="f1b2d-301">Jelentkezzen be az LCS-be, majd a lap jobb oldalán látható környezet neve alatt válassza ki a **Minden részlet** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-301">Sign in to LCS, and then, under the environment name on the right side of the page, select **Full Details**.</span></span>
2. <span data-ttu-id="f1b2d-302">A **Környezeti bővítmények** szakaszban válassza az **Új bővítmény telepítése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-302">In the **Environment add-ins** section, select **Install a new add-in**.</span></span>
3. <span data-ttu-id="f1b2d-303">Válassza a **Data Lake exportálása** bővítményt.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-303">Select the **Export to Data Lake** add-in.</span></span>
4. <span data-ttu-id="f1b2d-304">Adja meg az alábbi értékeket.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-304">Enter the following values.</span></span>

    | <span data-ttu-id="f1b2d-305">Érték</span><span class="sxs-lookup"><span data-stu-id="f1b2d-305">Value</span></span>                                                              | <span data-ttu-id="f1b2d-306">Leírás</span><span class="sxs-lookup"><span data-stu-id="f1b2d-306">Description</span></span> |
    |--------------------------------------------------------------------|-------------|
    | <span data-ttu-id="f1b2d-307">Az Azure-előfizetés bérlőazonosítója, ahol a Key Vault található</span><span class="sxs-lookup"><span data-stu-id="f1b2d-307">Tenant ID of the Azure Subscription where the Key Vault is located</span></span> | <span data-ttu-id="f1b2d-308">A bérlőazonosító, ahol a tárfiók, az alkalmazások és a kulcstartók találhatók.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-308">The tenant ID where the storage account, apps, and key vaults are located.</span></span> <span data-ttu-id="f1b2d-309">Ha meg szeretné találni ezt az értéket, nyissa meg az [Azure-portál](https://portal.azure.com) lehetőséget, menjen ide: **Azure Active Directory**, és másolja át a **Bérlőazonosító** értéket.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-309">To find this value, open the [Azure portal](https://portal.azure.com), go to **Azure Active Directory**, and copy the **Tenant ID** value.</span></span> |
    | <span data-ttu-id="f1b2d-310">Adja meg a Key Vault DNS-nevét.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-310">Provide the DNS name of your Key Vault</span></span>                             | <span data-ttu-id="f1b2d-311">A kulcstartó DNS-neve (például: `https://customkeyvault.vault.azure.net/`).</span><span class="sxs-lookup"><span data-stu-id="f1b2d-311">The DNS name of the key vault, such as `https://customkeyvault.vault.azure.net/`.</span></span> <span data-ttu-id="f1b2d-312">(Ez az érték megegyezik az entitásüzletben használt DNS-névvel.)</span><span class="sxs-lookup"><span data-stu-id="f1b2d-312">(This value matches the DNS name that is used in the entity store.)</span></span> |
    | <span data-ttu-id="f1b2d-313">Adja meg a tárfiók nevét tartalmazó titkos kódot</span><span class="sxs-lookup"><span data-stu-id="f1b2d-313">Provide the secret that contains the name of the storage account</span></span>   | <span data-ttu-id="f1b2d-314">**storage-account-name**</span><span class="sxs-lookup"><span data-stu-id="f1b2d-314">**storage-account-name**</span></span> |
    | <span data-ttu-id="f1b2d-315">Titkós kód neve az alkalmazásazonosítóhoz, amelyet a Data Lake eléréséhez használnak</span><span class="sxs-lookup"><span data-stu-id="f1b2d-315">Secret Name for App ID to be used for accessing Data Lake</span></span>          | <span data-ttu-id="f1b2d-316">**alkalmazás azonosítója**</span><span class="sxs-lookup"><span data-stu-id="f1b2d-316">**app-id**</span></span> |
    | <span data-ttu-id="f1b2d-317">Az alkalmazásazonosítóval használandó titkos kód neve</span><span class="sxs-lookup"><span data-stu-id="f1b2d-317">Secret name to be used with App ID</span></span>                                 | <span data-ttu-id="f1b2d-318">**alkalmazás titkos kódja**</span><span class="sxs-lookup"><span data-stu-id="f1b2d-318">**app-secret**</span></span> |

5. <span data-ttu-id="f1b2d-319">Fogadja el a feltételeket, és válassza a **Telepítés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-319">Agree to the terms, and select **Install**.</span></span>

<span data-ttu-id="f1b2d-320">A bővítményt néhány percen belül telepíti a program.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-320">The add-in will be installed within a few minutes.</span></span>

## <a name="configure-ai-builder"></a><span data-ttu-id="f1b2d-321">AI Builder konfigurálása</span><span class="sxs-lookup"><span data-stu-id="f1b2d-321">Configure AI Builder</span></span>

1. <span data-ttu-id="f1b2d-322">Jelentkezzen be a LCS-ba, majd nyissa meg a **Környezet részletei** oldalt.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-322">Sign in to LCS, and open the **Environment details** page.</span></span>
2. <span data-ttu-id="f1b2d-323">Görgessen le a **Környezeti bővítmények** szakaszhoz.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-323">Scroll to the **Environment add-ins** section.</span></span> <span data-ttu-id="f1b2d-324">Tekintse meg azokat a bővítményeket, amelyek már telepítve vannak ebben a környezetben.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-324">You should see the add-ins that are already installed in this environment.</span></span> <span data-ttu-id="f1b2d-325">Ha a **Data Lake exportálása** bővítmény nincs a többi között, konfigurálja ezt a bővítményt.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-325">If the **Export to Data Lake** add-in isn't among them, configure this add-in.</span></span>
3. <span data-ttu-id="f1b2d-326">Válassza ki az **Információk megszerzése** bővítményt.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-326">Select the **Get insights** add-in.</span></span>
4. <span data-ttu-id="f1b2d-327">Az **Információk megszerzése** bővítmény részletei oldalon adja meg az alábbi értékeket.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-327">On the **Get insights** add-in details page, enter the following values.</span></span>

    | <span data-ttu-id="f1b2d-328">Érték</span><span class="sxs-lookup"><span data-stu-id="f1b2d-328">Value</span></span>                                                    | <span data-ttu-id="f1b2d-329">Leírás</span><span class="sxs-lookup"><span data-stu-id="f1b2d-329">Description</span></span> |
    |----------------------------------------------------------|-------------|
    | <span data-ttu-id="f1b2d-330">CDS szervezet URL-címe</span><span class="sxs-lookup"><span data-stu-id="f1b2d-330">CDS Organization URL</span></span>                                     | <span data-ttu-id="f1b2d-331">A Dataverse-szervezet URL-címe felülről másolva.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-331">The Dataverse organization URL copied from above.</span></span> |
    | <span data-ttu-id="f1b2d-332">CDS szerv. azon.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-332">CDS Org ID</span></span>                                               | <span data-ttu-id="f1b2d-333">A Dataverse-szervezet azonosítója felülről másolva.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-333">The Dataverse organization ID copied from above.</span></span> |
5. <span data-ttu-id="f1b2d-334">Engedélyezze az **Ez az alapértelmezett CDS-környezet a bérlő számára?** elemet.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-334">Enable **Is this the default environment for you Tenant**.</span></span>
    
## <a name="configure-the-entity-store"></a><span data-ttu-id="f1b2d-335">Az entitásáruház konfigurálása</span><span class="sxs-lookup"><span data-stu-id="f1b2d-335">Configure the entity store</span></span>

<span data-ttu-id="f1b2d-336">Hajtsa végre az alábbi lépéseket, ha be szeretné állítani az entitásáruházat a Pénzügy környezetben.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-336">Follow these steps to set up the entity store in your Finance environment.</span></span>

1. <span data-ttu-id="f1b2d-337">Lépjen a **Rendszerfelügyelet \> Beállítás \> Rendszerparaméterek \> Adatkapcsolatok** elemre.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-337">Go to **System administration \> Setup \> System parameters \> Data connections**.</span></span>
2. <span data-ttu-id="f1b2d-338">A következő Key Vault-mezők beállítása:</span><span class="sxs-lookup"><span data-stu-id="f1b2d-338">Set the following key vault fields:</span></span>

    - <span data-ttu-id="f1b2d-339">**Alkalmazás (kliens) azonosítója** – Adja meg a korábban létrehozott alkalmazáskliens azonosítóját.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-339">**Application (client) ID** – Enter the application client ID that you created earlier.</span></span>
    - <span data-ttu-id="f1b2d-340">**Alkalmazás titkos kódja** – adja meg azt a titkos kódot, amelyet a korábban létrehozott alkalmazáshoz mentett.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-340">**Application Secret** – Enter the secret that you saved for the application that you created earlier.</span></span>
    - <span data-ttu-id="f1b2d-341">**DNS neve** – A korábban létrehozott alkalmazásnál megkeresheti a tartománynév-rendszer (DNS) nevét.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-341">**DNS name** – You can find the Domain Name System (DNS) name on the application details page for the application that you created earlier.</span></span>
    - <span data-ttu-id="f1b2d-342">**Titkos kód neve** – Adja meg a **storage-account-connection-string** értéket.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-342">**Secret name** – Enter **storage-account-connection-string**.</span></span>
3. <span data-ttu-id="f1b2d-343">Engedélyezze a **Data Lake-integráció engedélyezése** elemet.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-343">Enable **Enable Data Lake integration**.</span></span>
4. <span data-ttu-id="f1b2d-344">Válassza ki az **Azure Key Vault – Teszt** elemet, és ellenőrizze, hogy nincsenek hibák.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-344">Select **Test Azure Key Vault** and verify there are no errors.</span></span>
5. <span data-ttu-id="f1b2d-345">Válassza ki az **Azure-tárhely – Teszt** elemet, és ellenőrizze, hogy nincsenek hibák.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-345">Select **Test Azure storage** and verify there are no errors.</span></span>

## <a name="feedback-and-support"></a><span data-ttu-id="f1b2d-346">Visszajelzés és támogatás</span><span class="sxs-lookup"><span data-stu-id="f1b2d-346">Feedback and support</span></span>

<span data-ttu-id="f1b2d-347">Kérjük, küldjön egy e-mailt az [Ügyfél fizetési elemzés (előzetes verzió)](mailto:fiap@microsoft.com) címre, ha visszajelzést szeretne adni, vagy támogatásra van szüksége.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-347">Please send an email to [Customer payment insights (Preview)](mailto:fiap@microsoft.com) if you are interested in providing feedback or need support.</span></span>

## <a name="privacy-notice"></a><span data-ttu-id="f1b2d-348">Adatvédelmi nyilatkozat</span><span class="sxs-lookup"><span data-stu-id="f1b2d-348">Privacy notice</span></span>

<span data-ttu-id="f1b2d-349">Az előzetes verziók (1) kevesebb adatvédelmi és biztonsági intézkedést alkalmazhatnak, mint a Dynamics 365 Finance and Operations szolgáltatás (2) és nem vonatkozik a szolgáltatásiszint-szerződés (SLA) ehhez a szolgáltatáshoz, (3) nem használhatók olyan személyes adatok vagy más adatok feldolgozásához, melyekhez törvényi vagy jogszabályi megfelelési követelmények tartoznak, és (4) korlátozott támogatás tartozik hozzá.</span><span class="sxs-lookup"><span data-stu-id="f1b2d-349">Previews (1) might use less privacy and fewer security measures than the Dynamics 365 Finance and Operations service, (2) aren't included in the service level agreement (SLA) for this service, (3) should not be used to process personal data or other data that is subject to legal or regulatory compliance requirements, and (4) have limited support.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
