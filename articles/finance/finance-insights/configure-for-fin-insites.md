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
ms.openlocfilehash: 54117c009cfeb7307938cc6bd43e774ccfedcfb1
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/16/2021
ms.locfileid: "5908830"
---
# <a name="configuration-for-finance-insights-preview"></a><span data-ttu-id="8c782-103">Pénzügyi információk konfigurációja (előzetes verzió)</span><span class="sxs-lookup"><span data-stu-id="8c782-103">Configuration for Finance insights (preview)</span></span>

[!include [banner](../includes/banner.md)]

[!include [preview banner](../includes/preview-banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="8c782-104">A Pénzügyi információk a Microsoft Dynamics 365 Finance és a Microsoft Dataverse, az Azure és az AI Builder funkcióit kombinálva hatékony előrejelző eszközöket biztosítanak a szervezet számára.</span><span class="sxs-lookup"><span data-stu-id="8c782-104">Finance insights combines functionality from Microsoft Dynamics 365 Finance with Microsoft Dataverse, Azure, and AI Builder to provide powerful forecasting tools for your organization.</span></span> <span data-ttu-id="8c782-105">Ez a témakör azokat a konfigurációs lépéseket ismerteti, amelyek lehetővé teszik a rendszer számára a Pénzügyi információkban elérhető képességek használatát.</span><span class="sxs-lookup"><span data-stu-id="8c782-105">This topic explains the configuration steps that will enable your system to use the capabilities that are available in Finance insights.</span></span>

## <a name="deploy-dynamics-365-finance"></a><span data-ttu-id="8c782-106">Dynamics 365 Finance üzembe helyezése</span><span class="sxs-lookup"><span data-stu-id="8c782-106">Deploy Dynamics 365 Finance</span></span>

<span data-ttu-id="8c782-107">A környezetek üzembe helyezéséhez kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="8c782-107">Deploy the environments by following these steps.</span></span>

1. <span data-ttu-id="8c782-108">A Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásban hozzon létre vagy frissítse a Dynamics 365 Finance környezetet.</span><span class="sxs-lookup"><span data-stu-id="8c782-108">In Microsoft Dynamics Lifecycle Services (LCS), create or update a Dynamics 365 Finance environment.</span></span> <span data-ttu-id="8c782-109">A környezethez 10.0.11/Platform 35-ös vagy újabb alkalmazásverzióra van szükség.</span><span class="sxs-lookup"><span data-stu-id="8c782-109">The environment requires app version 10.0.11/Platform update 35 or later.</span></span>
2. <span data-ttu-id="8c782-110">A környezetnek magas rendelkezésre állású (HA) környezetnek kell lennie a tesztkörnyezetben.</span><span class="sxs-lookup"><span data-stu-id="8c782-110">The environment must be a high-availability (HA) environment in Sandbox.</span></span> <span data-ttu-id="8c782-111">(Az ilyen típusú környezetet 2. szintű környezetnek is nevezik.) További információ: [Környezettervezés](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).</span><span class="sxs-lookup"><span data-stu-id="8c782-111">(This type of environment is also known as a Tier-2 environment.) For more information, see [Environment planning](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).</span></span>
3. <span data-ttu-id="8c782-112">Ha Contoso Contoso bemutató adatokat használ, további mintaadatokra lesz szüksége az Ügyfélfizetési előrejelzések, a Pénzforgalmi előrejelzések és a Költségvetés-előrejelzések funkciók használatához.</span><span class="sxs-lookup"><span data-stu-id="8c782-112">If you're using Contoso demo data, you will require additional sample data to use the Customer payment predictions, Cash flow forecasts, and Budget forecasts features.</span></span> 

## <a name="configure-dataverse"></a><span data-ttu-id="8c782-113">Dataverse konfigurálása</span><span class="sxs-lookup"><span data-stu-id="8c782-113">Configure Dataverse</span></span>

<span data-ttu-id="8c782-114">Végrehajthatja a manuális konfigurációs lépéseket, vagy felgyorsíthatja a konfigurációs folyamatot a rendelkezésre álló Windows PowerShell-parancsfájl használatával.</span><span class="sxs-lookup"><span data-stu-id="8c782-114">You can complete the manual configuration steps that follow, or you can speed up the configuration process by using the Windows PowerShell script that is provided.</span></span> <span data-ttu-id="8c782-115">Ha a PowerShell-parancsfájl futása befejeződött, a Pénzügyi információk konfigurálásához használható értékeket ad.</span><span class="sxs-lookup"><span data-stu-id="8c782-115">When the PowerShell script has finished running, it will give you values to use to configure Finance insights.</span></span> 

> [!NOTE]
> <span data-ttu-id="8c782-116">Nyissa meg a PowerShellt a számítógépen a parancsfájl futtatásához.</span><span class="sxs-lookup"><span data-stu-id="8c782-116">Open PowerShell on your PC to run the script.</span></span> <span data-ttu-id="8c782-117">Lehet, hogy szüksége van a PowerShell 5-ös verziójára.</span><span class="sxs-lookup"><span data-stu-id="8c782-117">You may need PowerShell version 5.</span></span> <span data-ttu-id="8c782-118">Előfordulhat, hogy a Microsoft Azure CLI „Próbálja ki” opció nem működik.</span><span class="sxs-lookup"><span data-stu-id="8c782-118">The Microsoft Azure CLI "Try it" option may not work.</span></span>

# <a name="manual-configuration-steps"></a>[<span data-ttu-id="8c782-119">Manuális konfigurációs lépések</span><span class="sxs-lookup"><span data-stu-id="8c782-119">Manual configuration steps</span></span>](#tab/configuration-steps)

1. <span data-ttu-id="8c782-120">Nyissa meg a [Power Platform felügyeleti központot](https://admin.powerplatform.microsoft.com/), és az alábbi lépések végrehajtásával hozzon létre egy új Dataverse környezetet ugyanabban az Active Directory-bérlőben:</span><span class="sxs-lookup"><span data-stu-id="8c782-120">Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com/), and follow these steps to create a new Dataverse environment in the same Active Directory tenant:</span></span>

    1. <span data-ttu-id="8c782-121">Nyissa meg a **Környezetek** oldalt.</span><span class="sxs-lookup"><span data-stu-id="8c782-121">Open the **Environments** page.</span></span>

        <span data-ttu-id="8c782-122">[![Környezetek oldal](./media/power-pltfrm-admin-center.png)](./media/power-pltfrm-admin-center.png)</span><span class="sxs-lookup"><span data-stu-id="8c782-122">[![Environments page](./media/power-pltfrm-admin-center.png)](./media/power-pltfrm-admin-center.png)</span></span>

    2. <span data-ttu-id="8c782-123">Válassza ki az **Új környezet** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8c782-123">Select **New environment**.</span></span>
    3. <span data-ttu-id="8c782-124">A **Típus** mezőben válassza ki a **Tesztkörnyezet** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8c782-124">In the **Type** field, select **Sandbox**.</span></span>
    4. <span data-ttu-id="8c782-125">Állítsa az **Adatbázis létrehozása** beállítást **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="8c782-125">Set the **Create Database** option to **Yes**.</span></span>
    5. <span data-ttu-id="8c782-126">Válassza ki **Következő** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8c782-126">Select **Next**.</span></span>
    6. <span data-ttu-id="8c782-127">Válassza ki a szervezet nyelvét és pénznemét.</span><span class="sxs-lookup"><span data-stu-id="8c782-127">Select the language and currency for your organization.</span></span>
    7. <span data-ttu-id="8c782-128">A többi mezőben hagyja meg az alapértelmezett értékeket.</span><span class="sxs-lookup"><span data-stu-id="8c782-128">Accept the default values for the other fields.</span></span>
    8. <span data-ttu-id="8c782-129">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8c782-129">Select **Save**.</span></span>
    9. <span data-ttu-id="8c782-130">Frissítse a **Környezetek** oldalt.</span><span class="sxs-lookup"><span data-stu-id="8c782-130">Refresh the **Environments** page.</span></span>
    10. <span data-ttu-id="8c782-131">Várjon, amíg az **Állapot** mező értéke **Kész** állapotra nem frissül.</span><span class="sxs-lookup"><span data-stu-id="8c782-131">Wait until the value of the **State** field is updated to **Ready**.</span></span>
    11. <span data-ttu-id="8c782-132">Jegyezze fel a Dataverse szervezetazonosítót.</span><span class="sxs-lookup"><span data-stu-id="8c782-132">Make a note of the Dataverse organization ID.</span></span>
    12. <span data-ttu-id="8c782-133">Válassza ki a környezetet, majd válassza a **Beállítás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8c782-133">Select the environment, and then select **Settings**.</span></span>
    13. <span data-ttu-id="8c782-134">Válassza az **Erőforrások \> Minden örökölt beállítás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8c782-134">Select **Resources \> All Legacy Settings**.</span></span>
    14. <span data-ttu-id="8c782-135">A felső navigációs sávon válassza a **Beállítások**, majd a **Testreszabás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8c782-135">On the top navigation bar, select **Settings**, and then select **Customizations**.</span></span>
    15. <span data-ttu-id="8c782-136">Válassza a **Fejlesztői erőforrások** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8c782-136">Select **Developer Resources**.</span></span>
    16. <span data-ttu-id="8c782-137">Másolja a **Dataverse szervezetazonosító** értékét.</span><span class="sxs-lookup"><span data-stu-id="8c782-137">Copy the **Dataverse organization ID** value.</span></span>
    17. <span data-ttu-id="8c782-138">A böngésző címsorában jegyezze fel a Dataverse szervezet URL-címét.</span><span class="sxs-lookup"><span data-stu-id="8c782-138">In the browser's address bar, make a note of the URL for the Dataverse organization.</span></span> <span data-ttu-id="8c782-139">Az URL-cím lehet például `https://org42b2b3d3.crm.dynamics.com`.</span><span class="sxs-lookup"><span data-stu-id="8c782-139">For example, the URL might be `https://org42b2b3d3.crm.dynamics.com`.</span></span>

2. <span data-ttu-id="8c782-140">Ha a Pénzforgalmi előrejelzések vagy a Költségvetési előrejelzések funkciót kívánja használni, kövesse az alábbi lépéseket a szervezet címjegyzetkorlátjának legalább 50 megabájtra (MB) történő frissítéséhez:</span><span class="sxs-lookup"><span data-stu-id="8c782-140">If you plan to use the Cash flow forecasts or Budget forecasts feature, follow these steps to update the annotation limit for your organization to at least 50 megabytes (MB):</span></span>

    1. <span data-ttu-id="8c782-141">Nyissa meg a [Power Apps portált](https://make.powerapps.com).</span><span class="sxs-lookup"><span data-stu-id="8c782-141">Open the [Power Apps portal](https://make.powerapps.com).</span></span>
    2. <span data-ttu-id="8c782-142">Válassza ki az imént létrehozott környezetet, majd a **Speciális beállítások** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8c782-142">Select the environment that you just created, and then select **Advanced settings**.</span></span>
    3. <span data-ttu-id="8c782-143">Válassza a **Beállítások \> E-mail konfigurációja** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8c782-143">Select **Settings \> Email Configuration**.</span></span>
    4. <span data-ttu-id="8c782-144">Módosítsa a **Maximális fájlméret** mező értékét **51,200-ra**.</span><span class="sxs-lookup"><span data-stu-id="8c782-144">Change the value of the **Maximum file size** field to **51,200**.</span></span> <span data-ttu-id="8c782-145">(Az értéket kilobájtban \[KB\] kell kifejezni.)</span><span class="sxs-lookup"><span data-stu-id="8c782-145">(The value is expressed in kilobytes \[KB\].)</span></span>
    5. <span data-ttu-id="8c782-146">A módosítás mentéséhez kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="8c782-146">Select **OK** to save your changes.</span></span>

# <a name="windows-powershell-configuration-script"></a>[<span data-ttu-id="8c782-147">Windows PowerShell konfigurációs parancsfájl</span><span class="sxs-lookup"><span data-stu-id="8c782-147">Windows PowerShell configuration script</span></span>](#tab/powershell-configuration-script)

```azurecli-interactive
Write-Output 'The following modules need to be present for execution of this script:'
Write-Output '  Microsoft.PowerApps.Administration.PowerShell'
Write-Output '  Microsoft.PowerApps.PowerShell'
Write-Output '  Microsoft.Xrm.Tooling.CrmConnector.PowerShell'

try {
    $moduleConsent = Read-Host 'Is it ok to install or update these modules as needed? (yes/no)'
    if ($moduleConsent -ne 'yes' -and $moduleConsent -ne 'y') {
        Write-Warning 'User declined to install required modules.'
        return
    }

    $module = 'Microsoft.PowerApps.Administration.PowerShell'
    if (-not (Get-InstalledModule -Name $module -MinimumVersion '2.0.61' -ErrorAction SilentlyContinue)) {
        Install-Module -Name $module -MinimumVersion '2.0.61' -Force
        Write-Output ('Installed {0} module.' -f $module)
    }
    else {
        Write-Output ('{0} module found.' -f $module)
    }

    $module = 'Microsoft.PowerApps.PowerShell'
    if (-not (Get-InstalledModule -Name $module -MinimumVersion '1.0.9' -ErrorAction SilentlyContinue)) {
        Install-Module -Name $module -MinimumVersion '1.0.9' -AllowClobber -Force
        Write-Output ('Installed {0} module.' -f $module)
    }
    else {
        Write-Output ('{0} module found.' -f $module)
    }

    $module = 'Microsoft.Xrm.Tooling.CrmConnector.PowerShell'
    if (-not (Get-InstalledModule -Name $module -MinimumVersion '3.3.0.892' -ErrorAction SilentlyContinue)) {
        Install-Module -Name $module -MinimumVersion '3.3.0.892' -Force
        Write-Output ('Installed {0} module.' -f $module)
    }
    else {
        Write-Output ('{0} module found.' -f $module)
    }

    Write-Output '================================================================================='

    $useMfa = $false
    $useMfaPrompt = Read-Host "Does your organization require the use of multi-factor authentication? (yes/no)"
    if ($useMfaPrompt -eq 'yes' -or $useMfaPrompt -eq 'y') {
        $useMfa = $true
    }
    if(-not $useMfa) {
        $credential = Get-Credential -Message 'Power Apps Credential'
    }

    $orgFriendlyName = Read-Host "Enter the name of the CDS Organization to use or create: (blank for 'FinanceInsightsOrg')"
    if ($orgFriendlyName.Trim() -eq '') {
        $orgFriendlyName = 'FinanceInsightsOrg'
    }

    $isDefaultOrgPrompt = Read-Host ("Is '" + $orgFriendlyName + "' the default organization for your tenant? (yes/no)")
    if ($isDefaultOrgPrompt -eq 'yes' -or $isDefaultOrgPrompt -eq 'y') {
        $isDefaultOrg = $true
    }

    if ($credential) {
        Add-PowerAppsAccount -Username $credential.UserName -Password $credential.Password
    }
    else {
        Add-PowerAppsAccount
    }

    if ($isDefaultOrg) {
        $orgMatch = ('(default)')
        $environment = (Get-AdminPowerAppEnvironment | Where-Object { $_.IsDefault -eq $true })
    }
    else {
        $orgMatch = ('{0} (*)' -f $orgFriendlyName)
        $environment = (Get-AdminPowerAppEnvironment | Where-Object { ($_.IsDefault -eq $false -and ($_.DisplayName -eq $orgFriendlyName -or $_.DisplayName -like $orgMatch)) })
    }

    $getCrmOrgParams = @{ 'OnlineType' = 'Office365' }
    if ($credential) {
        $getCrmOrgParams.Credential = $credential
    }

    if ($null -eq $environment) {
        Write-Output '================================================================================='
        Write-Output 'PowerApps environment not found. A new one will be provisioned.'

        $invalid = 'invalid'

        $location = $invalid
        $cdsLocations = (Get-AdminPowerAppEnvironmentLocations | Select-Object LocationName).LocationName
        while (-not ($location -in $cdsLocations)) {
            $location = (Read-Host -Prompt "Enter the location in which to create the new PowerApps environment: ('help' to see values)")
            if ($location -eq 'help') {
                $cdsLocations
            }
        }

        $currency = $invalid
        $cdsCurrencies = (Get-AdminPowerAppCdsDatabaseCurrencies -Location $location | Select-Object CurrencyName).CurrencyName
        while ($currency -ne '' -and -not ($currency -in $cdsCurrencies)) {
            $currency = (Read-Host -Prompt "Enter the currency to use for the new PowerApps environment: ('help' to see values, blank for default)")
            if ($currency -eq 'help') {
                $cdsCurrencies
            }
        }

        $language = $invalid
        $cdsLanguages = (Get-AdminPowerAppCdsDatabaseLanguages -Location $location | Select-Object LanguageName, LanguageDisplayName)
        while ($language -ne '' -and -not ($language -in $cdsLanguages.LanguageName)) {
            $language = (Read-Host -Prompt "Enter the language name to use for the new PowerApps environment: ('help' to see values, blank for default)")
            if ($language -eq 'help') {
                $cdsLanguages | Format-Table -Property LanguageName, LanguageDisplayName
            }
        }

        Write-Output 'Provisioning PowerApps environment. This may take several minutes.'

        $sleep = 15

        $envParams = @{ 'DisplayName' = $orgFriendlyName; 'EnvironmentSku' = 'Sandbox'; 'ProvisionDatabase' = $true; 'Location' = $location; 'WaitUntilFinished' = $true }
        if ($language.Trim() -ne '') {
            $envParams.LanguageName = $language
        }
        if ($currency.Trim() -ne '') {
            $envParams.CurrencyName = $currency
        }
        $newEnvResult = New-AdminPowerAppEnvironment @envParams
        if (($null -eq $newEnvResult) -or ($newEnvResult.CommonDataServiceDatabaseProvisioningState -ne 'Succeeded')) {
            Write-Warning 'Failed to create to PowerApps environment'
            if ($null -ne $newEnvResult) {
                $newEnvResult
            }
        }
        else {
            $environment = $null
            $retryCount = 0
            while (($null -eq $environment) -and ($retryCount -lt 5)) {
                Start-Sleep -Seconds $sleep
                $environment = (Get-AdminPowerAppEnvironment | Where-Object { ($_.DisplayName -like $orgMatch) })
            }
            Write-Output ("Provisioned PowerApps environment with name: '" + $environment.DisplayName + "'")
        }

        Write-Output 'Waiting for CDS organization provisioning. This may take several minutes.'
        if (-not $credential) {
            $sleep = 120
            Write-Output 'You may be prompted for credentials multiple times while checking the status of the provisioning.'
        }

        while ($null -eq $crmOrg) {
            Start-Sleep -Seconds $sleep
            $crmOrg = (Get-CrmOrganizations @getCrmOrgParams) | Where-Object { $_.FriendlyName -eq $orgFriendlyName }
        }
    }
    else {
        $crmOrgs = Get-CrmOrganizations @getCrmOrgParams
        if ($UseDefaultOrganization -eq $true) {
            $crmOrg = $crmOrgs | Where-Object { $_.FriendlyName -match $orgMatch }
        }
        else {
            $crmOrg = $crmOrgs | Where-Object { $_.FriendlyName -eq $orgFriendlyName }
        }
    }

    Write-Output '================================================================================='
    Write-Output 'Values for PowerAI LCS Add-In:'
    Write-Output ("  CDS organization url:             " + $crmOrg.WebApplicationUrl)
    Write-Output ("  CDS organization ID:              " + $crmOrg.OrganizationId)
}
catch {
    Write-Error $_.Exception.Message
    Write-Warning $_.Exception.StackTrace
    $inner = $_.Exception.InnerException
    while ($null -ne $inner) {
        Write-Output 'Inner Exception:'
        Write-Error $_.Exception.Message
        Write-Warning $_.Exception.StackTrace
        $inner = $inner.InnerException
    }
}
```
---

## <a name="configure-the-azure-setup"></a><span data-ttu-id="8c782-148">Az Azure beállítások konfigurálása</span><span class="sxs-lookup"><span data-stu-id="8c782-148">Configure the Azure setup</span></span>

### <a name="enter-the-dataverse-directory-id-and-the-users-azure-ad-object-id"></a><span data-ttu-id="8c782-149">Adja meg a Dataverse címtárazonosítót és a felhasználó Azure AD objektumazonosítóját</span><span class="sxs-lookup"><span data-stu-id="8c782-149">Enter the Dataverse directory ID and the user's Azure AD object ID</span></span>

1. <span data-ttu-id="8c782-150">Adja meg a Dataverse címtárazonosítót:</span><span class="sxs-lookup"><span data-stu-id="8c782-150">Enter the Dataverse directory ID:</span></span>

    1. <span data-ttu-id="8c782-151">Nyissa meg az [Azure-portált](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="8c782-151">Open the [Azure portal](https://portal.azure.com).</span></span>
    2. <span data-ttu-id="8c782-152">Jelentkezzen be a környezet létrehozásához használt felhasználói Dataverse azonosítóval.</span><span class="sxs-lookup"><span data-stu-id="8c782-152">Sign in by using the user ID that was used to create the Dataverse environment.</span></span>
    3. <span data-ttu-id="8c782-153">Ugorjon ide: **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="8c782-153">Go to **Azure Active Directory**.</span></span>
    4. <span data-ttu-id="8c782-154">Másolja a **Bérlői azonosító** értékét.</span><span class="sxs-lookup"><span data-stu-id="8c782-154">Copy the **Tenant ID** value.</span></span>

2. <span data-ttu-id="8c782-155">Itt megadhatja a felhasználó Azure Active Directory (Azure AD) tárgyának azonosítóját:</span><span class="sxs-lookup"><span data-stu-id="8c782-155">Enter the user's Azure Active Directory (Azure AD) object ID:</span></span>

    1. <span data-ttu-id="8c782-156">Az [Azure-portálon](https://portal.azure.com) nyissa meg a **Felhasználók** lehetőséget, és keresse meg a felhasználót az e-mail címe szerint.</span><span class="sxs-lookup"><span data-stu-id="8c782-156">In the [Azure portal](https://portal.azure.com), go to **Users**, and search for the user by email address.</span></span>
    2. <span data-ttu-id="8c782-157">A felhasználó nevének kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="8c782-157">Select the user's name.</span></span>
    3. <span data-ttu-id="8c782-158">Másolja a **Tárgyazonosító** értékét.</span><span class="sxs-lookup"><span data-stu-id="8c782-158">Copy the **Object ID** value.</span></span>

### <a name="use-azure-cloud-shell-to-set-up-finance-insights-data-lake-resources"></a><span data-ttu-id="8c782-159">Az Azure Cloud Shell használatával állíthatja be a Data Lake-erőforrásokkal kapcsolatos pénzügyi elemzéseket</span><span class="sxs-lookup"><span data-stu-id="8c782-159">Use Azure Cloud Shell to set up Finance insights Data Lake resources</span></span>

# <a name="use-a-windows-powershell-script"></a>[<span data-ttu-id="8c782-160">Windows PowerShell parancsfájl használata</span><span class="sxs-lookup"><span data-stu-id="8c782-160">Use a Windows PowerShell script</span></span>](#tab/use-a-powershell-script)

<span data-ttu-id="8c782-161">Egy Windows PowerShell-parancsfájlt adott meg, így egyszerűen beállíthatja az Azure-erőforrásokat, amelyek az [Azure Data Lake exportálásának konfigurálása](../../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md) részben találhatók.</span><span class="sxs-lookup"><span data-stu-id="8c782-161">A Windows PowerShell script has been provided, so that you can easily set up the Azure resources that are described in [Configure export to Azure Data Lake](../../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md).</span></span> <span data-ttu-id="8c782-162">Ha a manuális beállítást szeretné elvégezni, hagyja ki ezt az eljárást, és folytassa az eljárást a [Manuális beállítás](#manual-setup) szakaszban.</span><span class="sxs-lookup"><span data-stu-id="8c782-162">If you prefer to do manual setup, skip this procedure, and continue with the procedure in the [Manual setup](#manual-setup) section.</span></span>

> [!NOTE]
> <span data-ttu-id="8c782-163">Kövesse az alábbi lépéseket a PowerShell-parancsfájl futtatásához.</span><span class="sxs-lookup"><span data-stu-id="8c782-163">Follow the steps below to run the PowerShell script.</span></span> <span data-ttu-id="8c782-164">Lehet, hogy az Azure CLI „Próbálja ki” lehetőség vagy a parancsfájl futtatása a számítógépen nem működik.</span><span class="sxs-lookup"><span data-stu-id="8c782-164">The Azure CLI "Try it" option, or running the script on your PC may not work.</span></span>

<span data-ttu-id="8c782-165">Kövesse az alábbi lépéseket az Azure konfigurálásához a Windows PowerShell-parancsfájl használatával.</span><span class="sxs-lookup"><span data-stu-id="8c782-165">Follow these steps to configure Azure by using the Windows PowerShell script.</span></span> <span data-ttu-id="8c782-166">Az Azure-erőforráscsoport, az Azure-erőforrások és az Azure AD alkalmazások létrehozásához jogokkal kell rendelkeznie.</span><span class="sxs-lookup"><span data-stu-id="8c782-166">You must have rights to create an Azure resource group, Azure resources, and an Azure AD application.</span></span> <span data-ttu-id="8c782-167">A szükséges engedélyekről az [Engedélyek Azure AD ellenőrzése](/azure/active-directory/develop/howto-create-service-principal-portal#permissions-required-for-registering-an-app) témakörben talál további információt.</span><span class="sxs-lookup"><span data-stu-id="8c782-167">For information about the required permissions, see [Check Azure AD permissions](/azure/active-directory/develop/howto-create-service-principal-portal#permissions-required-for-registering-an-app).</span></span>

1. <span data-ttu-id="8c782-168">Az [Azure-portálon](https://portal.azure.com) nyissa meg a cél Azure-előfizetés.</span><span class="sxs-lookup"><span data-stu-id="8c782-168">In the [Azure portal](https://portal.azure.com), go to your target Azure subscription.</span></span> <span data-ttu-id="8c782-169">Válassza a **Keresés** mezőtől jobbra lévő **Cloud Shell** gombot.</span><span class="sxs-lookup"><span data-stu-id="8c782-169">Select the **Cloud Shell** button to the right of the **Search** field.</span></span>
2. <span data-ttu-id="8c782-170">Válassza a **PowerShell** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8c782-170">Select **PowerShell**.</span></span>
3. <span data-ttu-id="8c782-171">Hozzon létre tárhelyet, ha a rendszer erre kéri.</span><span class="sxs-lookup"><span data-stu-id="8c782-171">Create storage, if you're prompted to do so.</span></span> <span data-ttu-id="8c782-172">Ezután töltse fel a Windows PowerShell-parancsfájlt a munkamenetbe.</span><span class="sxs-lookup"><span data-stu-id="8c782-172">Then upload the Windows PowerShell script to the session.</span></span>
4. <span data-ttu-id="8c782-173">Parancsfájl futtatása.</span><span class="sxs-lookup"><span data-stu-id="8c782-173">Run the script.</span></span>
5. <span data-ttu-id="8c782-174">A parancsfájl futtatásához kövesse az utasításokat.</span><span class="sxs-lookup"><span data-stu-id="8c782-174">Follow the prompts to run the script.</span></span>
6. <span data-ttu-id="8c782-175">A parancsfájl kimenetéből származó információk segítségével telepítse az **Exportálás a Data Lake-be** bővítményt az LCS-ben.</span><span class="sxs-lookup"><span data-stu-id="8c782-175">Use the information from the script output to install the **Export to Data Lake** add-in in LCS.</span></span>
7. <span data-ttu-id="8c782-176">A parancsfájl kimenetéből származó információk segítségével engedélyezze az entitás tárolását a Pénzügy (**Rendszerfelügyelet \> Rendszer paraméterei \> Adatkapcsolatok**) **Adatkapcsolatok** lapján.</span><span class="sxs-lookup"><span data-stu-id="8c782-176">Use the information from the script output to enable the entity store on the **Data connections** page in Finance (**System administration \> System parameters \> Data connections**).</span></span>

### <a name="manual-setup"></a><span data-ttu-id="8c782-177">Manuális beállítás</span><span class="sxs-lookup"><span data-stu-id="8c782-177">Manual setup</span></span>

#### <a name="add-applications-to-the-azure-ad-tenant"></a><span data-ttu-id="8c782-178">Alkalmazások hozzáadása az Azure AD-bérlőhöz</span><span class="sxs-lookup"><span data-stu-id="8c782-178">Add applications to the Azure AD tenant</span></span>

1. <span data-ttu-id="8c782-179">Az [Azure-portálban](https://portal.azure.com) menjen ide: **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="8c782-179">In the [Azure portal](https://portal.azure.com), go to **Azure Active Directory**.</span></span>
2. <span data-ttu-id="8c782-180">Válassza a **Vállalati \> alkalmazások kezelése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8c782-180">Select **Manage \> Enterprise applications**.</span></span>
3. <span data-ttu-id="8c782-181">Keresse meg a következő alkalmazásokat alkalmazásazonosító szerint.</span><span class="sxs-lookup"><span data-stu-id="8c782-181">Search for the following applications by app ID.</span></span>

    | <span data-ttu-id="8c782-182">Pályázat</span><span class="sxs-lookup"><span data-stu-id="8c782-182">Application</span></span>                              | <span data-ttu-id="8c782-183">Alkalmazás azonosítója</span><span class="sxs-lookup"><span data-stu-id="8c782-183">App ID</span></span>                               |
    |------------------------------------------|--------------------------------------|
    | <span data-ttu-id="8c782-184">Microsoft Dynamics ERP mikroszolgáltatások</span><span class="sxs-lookup"><span data-stu-id="8c782-184">Microsoft Dynamics ERP Microservices</span></span>     | <span data-ttu-id="8c782-185">0cdb527f-a8d1-4bf8-9436-b352c68682b2</span><span class="sxs-lookup"><span data-stu-id="8c782-185">0cdb527f-a8d1-4bf8-9436-b352c68682b2</span></span> |
    | <span data-ttu-id="8c782-186">Microsoft Dynamics ERP mikroszolgáltatások CDS</span><span class="sxs-lookup"><span data-stu-id="8c782-186">Microsoft Dynamics ERP Microservices CDS</span></span> | <span data-ttu-id="8c782-187">703e2651-d3fc-48f5-942c-74274233dba8</span><span class="sxs-lookup"><span data-stu-id="8c782-187">703e2651-d3fc-48f5-942c-74274233dba8</span></span> |
    | <span data-ttu-id="8c782-188">AI Builder engedélyezési szolgáltatás</span><span class="sxs-lookup"><span data-stu-id="8c782-188">AI Builder Authorization Service</span></span>         | <span data-ttu-id="8c782-189">ad40333e-9910-4b61-b281-e3aeeb8c3ef3</span><span class="sxs-lookup"><span data-stu-id="8c782-189">ad40333e-9910-4b61-b281-e3aeeb8c3ef3</span></span> |

<span data-ttu-id="8c782-190">Ha az előző alkalmazások egyikét sem találja, próbálkozzon az alábbi lépésekkel.</span><span class="sxs-lookup"><span data-stu-id="8c782-190">If you can't find any of the preceding applications, try the following steps.</span></span>

1. <span data-ttu-id="8c782-191">A helyi számítógépen válassza a **Start** menüt, és keresse meg a **powershell** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8c782-191">On your local machine, select the **Start** menu, and search for **powershell**.</span></span>
2. <span data-ttu-id="8c782-192">Jelölje ki és tartsa lenyomva (vagy nyomja meg a jobb egérgombot) a **Windows PowerShell** lehetőséget, majd válassza a **Futtatás rendszergazdaként** elemet.</span><span class="sxs-lookup"><span data-stu-id="8c782-192">Select and hold (or right-click) **Windows PowerShell**, and then select **Run as administrator**.</span></span>
3. <span data-ttu-id="8c782-193">Futtassa a következő parancsot az **AzureAD-modul** telepítéséhez.</span><span class="sxs-lookup"><span data-stu-id="8c782-193">Run the following command to install the **AzureAD** module.</span></span>

    `Install-Module -Name AzureAD`

4. <span data-ttu-id="8c782-194">Ha egy NuGet szolgáltatóra van szükség a folytatáshoz, válassza az **Y** lehetőséget a telepítéshez.</span><span class="sxs-lookup"><span data-stu-id="8c782-194">If a NuGet provider is required to continue, select **Y** to install it.</span></span>
5. <span data-ttu-id="8c782-195">Ha „Nem megbízható adattár” üzenet jelenik meg, a folytatáshoz válassza az **Y** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8c782-195">If an "Untrusted repository" message appears, select **Y** to continue.</span></span>
6. <span data-ttu-id="8c782-196">Minden hozzáadandó alkalmazáshoz futtassa a következő parancsokat az alkalmazás Azure AD-hoz való hozzáadásához.</span><span class="sxs-lookup"><span data-stu-id="8c782-196">For each application that must be added, run the following commands to add the application to Azure AD.</span></span> <span data-ttu-id="8c782-197">Amikor a rendszer kéri, jelentkezzen be Azure AD-rendszergazdaként.</span><span class="sxs-lookup"><span data-stu-id="8c782-197">When you're prompted, sign in as the Azure AD administrator.</span></span>

    `Connect-AzureAD`

    `New-AzureADServicePrincipal –AppId <AppId>`

#### <a name="create-azure-resources"></a><span data-ttu-id="8c782-198">Azure-erőforrások létrehozása</span><span class="sxs-lookup"><span data-stu-id="8c782-198">Create Azure resources</span></span>

> [!NOTE]
> <span data-ttu-id="8c782-199">Győződjön meg arról, hogy a következő erőforrásokat hozza létre ugyanabban a Azure AD-példányban, mint a Dataverse-környezetben.</span><span class="sxs-lookup"><span data-stu-id="8c782-199">Make sure that you create the following resources in the same Azure AD instance as the Dataverse environment.</span></span> <span data-ttu-id="8c782-200">Más Azure AD-példányból származó erőforrások nem használhatók.</span><span class="sxs-lookup"><span data-stu-id="8c782-200">You can't use resources from a different Azure AD instance.</span></span>

1. <span data-ttu-id="8c782-201">Új társzámla létrehozása:</span><span class="sxs-lookup"><span data-stu-id="8c782-201">Create a new storage account:</span></span>

    1. <span data-ttu-id="8c782-202">Hozzon létre egy társzámlát az [Azure-portálon](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="8c782-202">In the [Azure portal](https://portal.azure.com), create a storage account.</span></span>
    2. <span data-ttu-id="8c782-203">A **Társzámla létrehozása** párbeszédpanelen adja meg a következő mezőket:</span><span class="sxs-lookup"><span data-stu-id="8c782-203">In the **Create storage account** dialog box, set the following fields:</span></span>

        - <span data-ttu-id="8c782-204">**Hely** – Válassza ki azt az adatközpontot, ahol a környezet található.</span><span class="sxs-lookup"><span data-stu-id="8c782-204">**Location** – Select the data center where your environment is located.</span></span>
        - <span data-ttu-id="8c782-205">**Teljesítmény** – Javasoljuk, hogy a **Standard** lehetőséget válassza.</span><span class="sxs-lookup"><span data-stu-id="8c782-205">**Performance** – We recommend that you select **Standard**.</span></span>
        - <span data-ttu-id="8c782-206">**Fiók fajtája** – A **StorageV2** lehetőséget kell választania.</span><span class="sxs-lookup"><span data-stu-id="8c782-206">**Account kind** – You must select **StorageV2**.</span></span>

    3. <span data-ttu-id="8c782-207">A **Speciális beállítások** párbeszédpanel **Data Lake Storage Gen2** lehetőséghez válassza az **Engedélyezés** elemet a **Hierarchikus névterek** funkció alatt.</span><span class="sxs-lookup"><span data-stu-id="8c782-207">In the **Advanced options** dialog box, for the **Data Lake storage Gen2** option, select **Enable** under the **Hierarchical namespaces** feature.</span></span> <span data-ttu-id="8c782-208">Ha letiltja ezt a funkciót, nem használhatja fel a Finance and Operations alkalmazások által olyan szolgáltatások használatával írt adatokat, mint például a Power BI adatfolyamok.</span><span class="sxs-lookup"><span data-stu-id="8c782-208">If you disable this feature, you can't consume data that Finance and Operations apps write by using services such as Power BI data flows.</span></span>
    4. <span data-ttu-id="8c782-209">Válassza a **Vélemény és létrehozás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8c782-209">Select **Review and create**.</span></span> <span data-ttu-id="8c782-210">A központi telepítés befejezése után az új erőforrás megjelenik az Azure-portálon.</span><span class="sxs-lookup"><span data-stu-id="8c782-210">When the deployment is completed, the new resource will be shown in the Azure portal.</span></span>
    5. <span data-ttu-id="8c782-211">Nyissa meg a létrehozott tárfiókot.</span><span class="sxs-lookup"><span data-stu-id="8c782-211">Go to the storage account that you created.</span></span>
    6. <span data-ttu-id="8c782-212">A bal oldali menüben válassza a **Hívóbetű** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8c782-212">On the left menu, select **Access keys**.</span></span>
    7. <span data-ttu-id="8c782-213">Másolja és mentse a kapcsolati karakterláncot a **Key1** vagy a **Key2** lehetőséghez.</span><span class="sxs-lookup"><span data-stu-id="8c782-213">Copy and save the connection string for either **Key1** or **Key2**.</span></span>
    8. <span data-ttu-id="8c782-214">Másolja és mentse a tárfiók nevét.</span><span class="sxs-lookup"><span data-stu-id="8c782-214">Copy and save the storage account name.</span></span>

2. <span data-ttu-id="8c782-215">Új kulcstároló létrehozása:</span><span class="sxs-lookup"><span data-stu-id="8c782-215">Create a new key vault:</span></span>

    1. <span data-ttu-id="8c782-216">Hozzon létre egy kulcstárolót az [Azure-portálon](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="8c782-216">In the [Azure portal](https://portal.azure.com), create a key vault.</span></span>
    2. <span data-ttu-id="8c782-217">A **Kulcstartó létrehozása** párbeszédpanel, a **Hely** mezőben jelölje ki azt az adatközpontot, ahol a környezet található.</span><span class="sxs-lookup"><span data-stu-id="8c782-217">In the **Create key vault** dialog box, in the **Location** field, select the data center where your environment is located.</span></span>
    3. <span data-ttu-id="8c782-218">A kulcstartó létrehozása után jelölje ki a listában, majd válassza ki a **Titkok** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8c782-218">After key vault is created, select it in the list, and then select **Secrets**.</span></span>
    4. <span data-ttu-id="8c782-219">Válassza a **Generálás/Importálás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8c782-219">Select **Generate/Import**.</span></span>
    5. <span data-ttu-id="8c782-220">A **Titkos kód létrehozása** párbeszédpanel **Feltöltési beállítások** mezőjében válassza a **Manuális** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8c782-220">In the **Create a secret** dialog box, in the **Upload options** field, select **Manual**.</span></span>
    6. <span data-ttu-id="8c782-221">Adja meg a titkos kód nevét.</span><span class="sxs-lookup"><span data-stu-id="8c782-221">Enter a name for the secret.</span></span> <span data-ttu-id="8c782-222">Jegyezze fel a nevet, mert később meg kell adnia.</span><span class="sxs-lookup"><span data-stu-id="8c782-222">Make a note of the name, because you will have to provide it later.</span></span>
    7. <span data-ttu-id="8c782-223">Az **Érték** mezőbe írja be azt a kapcsolati karakterláncot, amelyet a korábbi eljárásban a tárfiókból nyert.</span><span class="sxs-lookup"><span data-stu-id="8c782-223">In the **Value** field, enter the connection string that you obtained from the storage account in the previous procedure.</span></span>
    8. <span data-ttu-id="8c782-224">Válassza ki az **Engedélyezés**, majd a **Létrehozás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8c782-224">Select **Enabled**, and then select **Create**.</span></span> <span data-ttu-id="8c782-225">A rendszer létrehozta a titkot, és hozzáadta a Kulcstartót.</span><span class="sxs-lookup"><span data-stu-id="8c782-225">The secret is created and added to Key Vault.</span></span>
    9. <span data-ttu-id="8c782-226">Nyissa meg a **Kulcstartó áttekintése** lehetőséget, és jegyezze fel a DNS-nevet.</span><span class="sxs-lookup"><span data-stu-id="8c782-226">Go to the **Key Vault Overview**, and make a note of the DNS name.</span></span>

3. <span data-ttu-id="8c782-227">Azure AD alkalmazás létrehozása és regisztrálása:</span><span class="sxs-lookup"><span data-stu-id="8c782-227">Create and register an Azure AD application:</span></span>

    1. <span data-ttu-id="8c782-228">Az [Azure portálon](https://portal.azure.com) menjen ide: **Azure Active Directory**, majd válassza az **Alkalmazás regisztrálása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8c782-228">In the [Azure portal](https://portal.azure.com), go to **Azure Active Directory**, and then select **App registrations**.</span></span>
    2. <span data-ttu-id="8c782-229">Válassza ki az **Új alkalmazásregisztráció** lehetőséget, és állítsa be a következő mezőket:</span><span class="sxs-lookup"><span data-stu-id="8c782-229">Select **New application registration**, and set the following fields:</span></span>

        - <span data-ttu-id="8c782-230">**Név** – Írja be az alkalmazás nevét.</span><span class="sxs-lookup"><span data-stu-id="8c782-230">**Name** – Enter the name of the app.</span></span>
        - <span data-ttu-id="8c782-231">**Alkalmazás típusa** – válassza ki a **webes API-t**.</span><span class="sxs-lookup"><span data-stu-id="8c782-231">**Application type** – Select **Web API**.</span></span>
        - <span data-ttu-id="8c782-232">**URI-beállítás átirányítása** – Adja meg a Dynamics 365 példány URL-címét, például: `https://yourdynamicsinstance.dynamics.com/auth`.</span><span class="sxs-lookup"><span data-stu-id="8c782-232">**Redirect URI setup** – Enter the URL for your Dynamics 365 instance, such as, `https://yourdynamicsinstance.dynamics.com/auth`.</span></span>

    3. <span data-ttu-id="8c782-233">Nyissa meg az imént létrehozott alkalmazást, és másolja, majd mentse az **Alkalmazás (kliens) azonosítójának** értékét.</span><span class="sxs-lookup"><span data-stu-id="8c782-233">Go to the app that you just created, and copy and save its **Application (client) ID** value.</span></span> <span data-ttu-id="8c782-234">Ezt az értéket később kell megadni, amikor beállítja a kulcstartót.</span><span class="sxs-lookup"><span data-stu-id="8c782-234">You will have to provide this value later, when you set up the key vault.</span></span>
    4. <span data-ttu-id="8c782-235">Nyissa meg az **API-engedélyek** lehetőséget, majd kövesse az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="8c782-235">Go to **API permissions**, and follow these steps:</span></span>

        1. <span data-ttu-id="8c782-236">Válassza az **Engedély hozzáadása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8c782-236">Select **Add a permission**.</span></span>
        2. <span data-ttu-id="8c782-237">Válassza ki az **Azure kulcstartó** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8c782-237">Select **Azure Key vault**.</span></span>
        3. <span data-ttu-id="8c782-238">A delegált engedélyek kiválasztása után válassza ki a **felhasználó\_megszemélyesítését**.</span><span class="sxs-lookup"><span data-stu-id="8c782-238">After you select delegated permissions, select **user\_impersonation**.</span></span>
        4. <span data-ttu-id="8c782-239">Válassza az **Engedélyek hozzáadása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8c782-239">Select **Add permissions**.</span></span>

    5. <span data-ttu-id="8c782-240">Az alkalmazás menüjében válassza ki a **Tanúsítványok \& titkai** lehetőséget, majd a Key Vault létrehozásához hajtsa végre az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="8c782-240">On the menu for the app, select **Certificates \& secrets**, and then follow these steps to create Key Vault secrets:</span></span>

        1. <span data-ttu-id="8c782-241">Válassza ki az **Új titkos ügyfélkód** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8c782-241">Select **New client secret**.</span></span>
        2. <span data-ttu-id="8c782-242">Adjon meg egy nevet a **Kulcsleírás** mezőben.</span><span class="sxs-lookup"><span data-stu-id="8c782-242">In the **Key Description** field, enter a name.</span></span>
        3. <span data-ttu-id="8c782-243">Válasszon ki egy időtartamot, majd a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8c782-243">Select a duration, and then select **Add**.</span></span> <span data-ttu-id="8c782-244">Az **Érték** mezőben egy titkos kód jön létre.</span><span class="sxs-lookup"><span data-stu-id="8c782-244">A secret is generated in the **Value** field.</span></span>
        4. <span data-ttu-id="8c782-245">A titkos kód értékének másolása és mentése.</span><span class="sxs-lookup"><span data-stu-id="8c782-245">Copy and save the secret value.</span></span>

4. <span data-ttu-id="8c782-246">Key Vault titkos kódok létrehozása:</span><span class="sxs-lookup"><span data-stu-id="8c782-246">Create Key Vault secrets:</span></span>

    1. <span data-ttu-id="8c782-247">Menjen a korábban létrehozott kulcstartóhoz, és válassza ki a **Titkokat**.</span><span class="sxs-lookup"><span data-stu-id="8c782-247">Go to the key vault that you created earlier, and select **Secrets**.</span></span>
    2. <span data-ttu-id="8c782-248">Hajtsa végre az alábbi lépéseket mindegyik titkos kód névhez a következő táblában:</span><span class="sxs-lookup"><span data-stu-id="8c782-248">For each secret name in the following table, follow these steps:</span></span>

        1. <span data-ttu-id="8c782-249">Válassza a **Generálás/Importálás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8c782-249">Select **Generate/Import**.</span></span>
        2. <span data-ttu-id="8c782-250">A **Titkos kód létrehozása** párbeszédpanel **Feltöltési beállítások** mezőjében válassza a **Manuális** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8c782-250">In the **Create a secret** dialog box, in the **Upload options** field, select **Manual**.</span></span>
        3. <span data-ttu-id="8c782-251">A következő táblából hozza létre a titkos kód nevét és értékét.</span><span class="sxs-lookup"><span data-stu-id="8c782-251">Create the secret name and value from the following table.</span></span>
        4. <span data-ttu-id="8c782-252">Válassza ki az **Engedélyezés**, majd a **Létrehozás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8c782-252">Select **Enabled**, and then select **Create**.</span></span> <span data-ttu-id="8c782-253">A rendszer létrehozta a titkot, és hozzáadta a Kulcstartót.</span><span class="sxs-lookup"><span data-stu-id="8c782-253">The secret is created and added to Key Vault.</span></span>

        | <span data-ttu-id="8c782-254">Titkos név</span><span class="sxs-lookup"><span data-stu-id="8c782-254">Secret name</span></span>                       | <span data-ttu-id="8c782-255">Titkos kód értéke</span><span class="sxs-lookup"><span data-stu-id="8c782-255">Secret value</span></span>                                                                                |
        |-----------------------------------|---------------------------------------------------------------------------------------------|
        | <span data-ttu-id="8c782-256">alkalmazás azonosítója</span><span class="sxs-lookup"><span data-stu-id="8c782-256">app-id</span></span>                            | <span data-ttu-id="8c782-257">A korábban létrehozott alkalmazás alkalmazásazonosítója</span><span class="sxs-lookup"><span data-stu-id="8c782-257">The app ID of the application that you created earlier</span></span>                                      |
        | <span data-ttu-id="8c782-258">alkalmazás titkos kódja</span><span class="sxs-lookup"><span data-stu-id="8c782-258">app-secret</span></span>                        | <span data-ttu-id="8c782-259">A korábban mentett titkos ügyfélkód</span><span class="sxs-lookup"><span data-stu-id="8c782-259">The client secret that you saved earlier</span></span>                                                    |
        | <span data-ttu-id="8c782-260">storage-account-name</span><span class="sxs-lookup"><span data-stu-id="8c782-260">storage-account-name</span></span>              | <span data-ttu-id="8c782-261">A korábban létrehozott tárfiók neve, például **storageaccount1**</span><span class="sxs-lookup"><span data-stu-id="8c782-261">The name of the storage account that you created earlier, such as **storageaccount1**</span></span>       |
        | <span data-ttu-id="8c782-262">storage-account-connection-string</span><span class="sxs-lookup"><span data-stu-id="8c782-262">storage-account-connection-string</span></span> | <span data-ttu-id="8c782-263">A tárfiók **Elérési kulcsok** lapjáról átmásolt kapcsolati karakterlánc</span><span class="sxs-lookup"><span data-stu-id="8c782-263">The connection string that you copied from the **Access keys** page for the storage account</span></span> |

5. <span data-ttu-id="8c782-264">Az alkalmazás engedélyezése a kulcstartó eléréséhez:</span><span class="sxs-lookup"><span data-stu-id="8c782-264">Authorize the application to access the key vault:</span></span>

    1. <span data-ttu-id="8c782-265">A [Azure-portál](https://portal.azure.com) webhelyen nyissa meg a korábban létrehozott kulcstartót.</span><span class="sxs-lookup"><span data-stu-id="8c782-265">In the [Azure portal](https://portal.azure.com), open the key vault that you created earlier.</span></span>
    2. <span data-ttu-id="8c782-266">Válassza ki a hozzáférési szabályzatokat.</span><span class="sxs-lookup"><span data-stu-id="8c782-266">Select the access policies.</span></span>
    3. <span data-ttu-id="8c782-267">Hajtsa végre az alábbi lépéseket mindegyik alkalmazáshoz a következő táblában:</span><span class="sxs-lookup"><span data-stu-id="8c782-267">For each application in the following table, follow these steps:</span></span>

        1. <span data-ttu-id="8c782-268">Válassza a **Hozzáférési szabályzat hozzáadása** elemet a hozzáférési szabályzat létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="8c782-268">Select **Add Access Policy** to create an access policy.</span></span>
        2. <span data-ttu-id="8c782-269">A **Titkos engedélyek** mezőben válassza ki a következő táblában szereplő engedélyeket.</span><span class="sxs-lookup"><span data-stu-id="8c782-269">In the **Secret permissions** field, select the permissions from the following table.</span></span>
        3. <span data-ttu-id="8c782-270">A **Résztvevő kiválasztása** mezőben keressen rá az alkalmazás megjelenített nevére a következő táblából.</span><span class="sxs-lookup"><span data-stu-id="8c782-270">In the **Select principal** field, search for the application display name from the following table.</span></span>
        4. <span data-ttu-id="8c782-271">Válassza ki a **Kiválasztás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8c782-271">Select **Select**.</span></span>
        5. <span data-ttu-id="8c782-272">Válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8c782-272">Select **Add**.</span></span>
        6. <span data-ttu-id="8c782-273">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8c782-273">Select **Save**.</span></span>

        | <span data-ttu-id="8c782-274">Pályázat</span><span class="sxs-lookup"><span data-stu-id="8c782-274">Application</span></span>                                              | <span data-ttu-id="8c782-275">Engedélyek</span><span class="sxs-lookup"><span data-stu-id="8c782-275">Permissions</span></span> |
        |----------------------------------------------------------|-------------|
        | <span data-ttu-id="8c782-276">A létrehozott új alkalmazás megjelenített neve</span><span class="sxs-lookup"><span data-stu-id="8c782-276">The display name of the new application that you created</span></span> | <span data-ttu-id="8c782-277">Kérés, listázás</span><span class="sxs-lookup"><span data-stu-id="8c782-277">Get, List</span></span>   |
        | <span data-ttu-id="8c782-278">**Microsoft Dynamics ERP mikroszolgáltatások**</span><span class="sxs-lookup"><span data-stu-id="8c782-278">**Microsoft Dynamics ERP Microservices**</span></span>                 | <span data-ttu-id="8c782-279">Kérés, listázás</span><span class="sxs-lookup"><span data-stu-id="8c782-279">Get, List</span></span>   |

6. <span data-ttu-id="8c782-280">Szerepkörök hozzárendelése a tárfiókhoz:</span><span class="sxs-lookup"><span data-stu-id="8c782-280">Assign roles to access the storage account:</span></span>

    1. <span data-ttu-id="8c782-281">A [Azure-portál](https://portal.azure.com) webhelyen nyissa meg a korábban létrehozott tárfiókot.</span><span class="sxs-lookup"><span data-stu-id="8c782-281">In the [Azure portal](https://portal.azure.com), open the storage account that you created earlier.</span></span>
    2. <span data-ttu-id="8c782-282">Válassza ki az **Access Control (IAM)** lehetőséget, majd válassza ki a **Szerepkör hozzárendeléseket**.</span><span class="sxs-lookup"><span data-stu-id="8c782-282">Select **Access Control (IAM)**, and then select **Role Assignments**.</span></span>
    3. <span data-ttu-id="8c782-283">Válassza a **Hozzáadás, Szerepkör-hozzárendelés hozzáadása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8c782-283">Select **Add, Add Role Assignment**.</span></span>
    4. <span data-ttu-id="8c782-284">Hajtsa végre az alábbi lépéseket mindegyik alkalmazáshoz a következő táblában:</span><span class="sxs-lookup"><span data-stu-id="8c782-284">For each application in the following table, follow these steps:</span></span>

        1. <span data-ttu-id="8c782-285">Válassza ki a szerepkört az alábbi táblából.</span><span class="sxs-lookup"><span data-stu-id="8c782-285">Select the role from the following table.</span></span>
        2. <span data-ttu-id="8c782-286">A **Hozzáférés hozzárendelése** mezőben hagyja meg az **Azure AD felhasználó, csoport vagy szolgáltatásnév** értéket.</span><span class="sxs-lookup"><span data-stu-id="8c782-286">Leave the **Assign access to** field set to **Azure AD user, group, or service principal**.</span></span>
        3. <span data-ttu-id="8c782-287">A **Kiválasztás** mezőben adja meg a következő táblában szereplő alkalmazást.</span><span class="sxs-lookup"><span data-stu-id="8c782-287">In the **Select** field, enter the application from the following table.</span></span>
        4. <span data-ttu-id="8c782-288">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8c782-288">Select **Save**.</span></span>

        | <span data-ttu-id="8c782-289">Pályázat</span><span class="sxs-lookup"><span data-stu-id="8c782-289">Application</span></span>                                              | <span data-ttu-id="8c782-290">Szerep</span><span class="sxs-lookup"><span data-stu-id="8c782-290">Role</span></span>                        |
        |----------------------------------------------------------|-----------------------------|
        | <span data-ttu-id="8c782-291">A létrehozott új alkalmazás megjelenített neve</span><span class="sxs-lookup"><span data-stu-id="8c782-291">The display name of the new application that you created</span></span> | <span data-ttu-id="8c782-292">Tulajdonos</span><span class="sxs-lookup"><span data-stu-id="8c782-292">Owner</span></span>                       |
        | <span data-ttu-id="8c782-293">A létrehozott új alkalmazás megjelenített neve</span><span class="sxs-lookup"><span data-stu-id="8c782-293">The display name of the new application that you created</span></span> | <span data-ttu-id="8c782-294">Hozzájáruló</span><span class="sxs-lookup"><span data-stu-id="8c782-294">Contributor</span></span>                 |
        | <span data-ttu-id="8c782-295">A létrehozott új alkalmazás megjelenített neve</span><span class="sxs-lookup"><span data-stu-id="8c782-295">The display name of the new application that you created</span></span> | <span data-ttu-id="8c782-296">Tárfiók közreműködője</span><span class="sxs-lookup"><span data-stu-id="8c782-296">Storage Account Contributor</span></span> |
        | <span data-ttu-id="8c782-297">A létrehozott új alkalmazás megjelenített neve</span><span class="sxs-lookup"><span data-stu-id="8c782-297">The display name of the new application that you created</span></span> | <span data-ttu-id="8c782-298">Tárolási blobadatok tulajdonosa</span><span class="sxs-lookup"><span data-stu-id="8c782-298">Storage Blob Data Owner</span></span>     |
        | <span data-ttu-id="8c782-299">**AI Builder engedélyezési szolgáltatás**</span><span class="sxs-lookup"><span data-stu-id="8c782-299">**AI Builder Authorization Service**</span></span>                     | <span data-ttu-id="8c782-300">Tárolási blobadatok olvasója</span><span class="sxs-lookup"><span data-stu-id="8c782-300">Storage Blob Data Reader</span></span>    |

# <a name="azure-cli"></a>[<span data-ttu-id="8c782-301">Azure parancssori felület</span><span class="sxs-lookup"><span data-stu-id="8c782-301">Azure CLI</span></span>](#tab/azure-azure-cli)

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



## <a name="configure-the-data-lake"></a><span data-ttu-id="8c782-302">A Data Lake konfigurálása</span><span class="sxs-lookup"><span data-stu-id="8c782-302">Configure the data lake</span></span>

<span data-ttu-id="8c782-303">Hajtsa végre az alábbi lépéseket, ha az Azure Data Lake-bővítményt hozzá szeretné adni a környezethez az LCS használatával.</span><span class="sxs-lookup"><span data-stu-id="8c782-303">Follow these steps to use LCS to add the Azure Data Lake add-in to the environment.</span></span>

1. <span data-ttu-id="8c782-304">Jelentkezzen be az LCS-be, majd a lap jobb oldalán látható környezet neve alatt válassza ki a **Minden részlet** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8c782-304">Sign in to LCS, and then, under the environment name on the right side of the page, select **Full Details**.</span></span>
2. <span data-ttu-id="8c782-305">A **Környezeti bővítmények** szakaszban válassza az **Új bővítmény telepítése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8c782-305">In the **Environment add-ins** section, select **Install a new add-in**.</span></span>
3. <span data-ttu-id="8c782-306">Válassza a **Data Lake exportálása** bővítményt.</span><span class="sxs-lookup"><span data-stu-id="8c782-306">Select the **Export to Data Lake** add-in.</span></span>
4. <span data-ttu-id="8c782-307">Adja meg az alábbi értékeket.</span><span class="sxs-lookup"><span data-stu-id="8c782-307">Enter the following values.</span></span>

    | <span data-ttu-id="8c782-308">Érték</span><span class="sxs-lookup"><span data-stu-id="8c782-308">Value</span></span>                                                              | <span data-ttu-id="8c782-309">Leírás</span><span class="sxs-lookup"><span data-stu-id="8c782-309">Description</span></span> |
    |--------------------------------------------------------------------|-------------|
    | <span data-ttu-id="8c782-310">Az Azure-előfizetés bérlőazonosítója, ahol a Key Vault található</span><span class="sxs-lookup"><span data-stu-id="8c782-310">Tenant ID of the Azure Subscription where the Key Vault is located</span></span> | <span data-ttu-id="8c782-311">A bérlőazonosító, ahol a tárfiók, az alkalmazások és a kulcstartók találhatók.</span><span class="sxs-lookup"><span data-stu-id="8c782-311">The tenant ID where the storage account, apps, and key vaults are located.</span></span> <span data-ttu-id="8c782-312">Ha meg szeretné találni ezt az értéket, nyissa meg az [Azure-portál](https://portal.azure.com) lehetőséget, menjen ide: **Azure Active Directory**, és másolja át a **Bérlőazonosító** értéket.</span><span class="sxs-lookup"><span data-stu-id="8c782-312">To find this value, open the [Azure portal](https://portal.azure.com), go to **Azure Active Directory**, and copy the **Tenant ID** value.</span></span> |
    | <span data-ttu-id="8c782-313">Adja meg a Key Vault DNS-nevét.</span><span class="sxs-lookup"><span data-stu-id="8c782-313">Provide the DNS name of your Key Vault</span></span>                             | <span data-ttu-id="8c782-314">A kulcstartó DNS-neve (például: `https://customkeyvault.vault.azure.net/`).</span><span class="sxs-lookup"><span data-stu-id="8c782-314">The DNS name of the key vault, such as `https://customkeyvault.vault.azure.net/`.</span></span> <span data-ttu-id="8c782-315">(Ez az érték megegyezik az entitásüzletben használt DNS-névvel.)</span><span class="sxs-lookup"><span data-stu-id="8c782-315">(This value matches the DNS name that is used in the entity store.)</span></span> |
    | <span data-ttu-id="8c782-316">Adja meg a tárfiók nevét tartalmazó titkos kódot</span><span class="sxs-lookup"><span data-stu-id="8c782-316">Provide the secret that contains the name of the storage account</span></span>   | <span data-ttu-id="8c782-317">**storage-account-name**</span><span class="sxs-lookup"><span data-stu-id="8c782-317">**storage-account-name**</span></span> |
    | <span data-ttu-id="8c782-318">Titkós kód neve az alkalmazásazonosítóhoz, amelyet a Data Lake eléréséhez használnak</span><span class="sxs-lookup"><span data-stu-id="8c782-318">Secret Name for App ID to be used for accessing Data Lake</span></span>          | <span data-ttu-id="8c782-319">**alkalmazás azonosítója**</span><span class="sxs-lookup"><span data-stu-id="8c782-319">**app-id**</span></span> |
    | <span data-ttu-id="8c782-320">Az alkalmazásazonosítóval használandó titkos kód neve</span><span class="sxs-lookup"><span data-stu-id="8c782-320">Secret name to be used with App ID</span></span>                                 | <span data-ttu-id="8c782-321">**alkalmazás titkos kódja**</span><span class="sxs-lookup"><span data-stu-id="8c782-321">**app-secret**</span></span> |

5. <span data-ttu-id="8c782-322">Fogadja el a feltételeket, és válassza a **Telepítés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8c782-322">Agree to the terms, and select **Install**.</span></span>

<span data-ttu-id="8c782-323">A bővítményt néhány percen belül telepíti a program.</span><span class="sxs-lookup"><span data-stu-id="8c782-323">The add-in will be installed within a few minutes.</span></span>

## <a name="configure-ai-builder"></a><span data-ttu-id="8c782-324">AI Builder konfigurálása</span><span class="sxs-lookup"><span data-stu-id="8c782-324">Configure AI Builder</span></span>

1. <span data-ttu-id="8c782-325">Jelentkezzen be a LCS-ba, majd nyissa meg a **Környezet részletei** oldalt.</span><span class="sxs-lookup"><span data-stu-id="8c782-325">Sign in to LCS, and open the **Environment details** page.</span></span>
2. <span data-ttu-id="8c782-326">Görgessen le a **Környezeti bővítmények** szakaszhoz.</span><span class="sxs-lookup"><span data-stu-id="8c782-326">Scroll to the **Environment add-ins** section.</span></span> <span data-ttu-id="8c782-327">Tekintse meg azokat a bővítményeket, amelyek már telepítve vannak ebben a környezetben.</span><span class="sxs-lookup"><span data-stu-id="8c782-327">You should see the add-ins that are already installed in this environment.</span></span> <span data-ttu-id="8c782-328">Ha a **Data Lake exportálása** bővítmény nincs a többi között, konfigurálja ezt a bővítményt.</span><span class="sxs-lookup"><span data-stu-id="8c782-328">If the **Export to Data Lake** add-in isn't among them, configure this add-in.</span></span>
3. <span data-ttu-id="8c782-329">Válassza ki az **Információk megszerzése** bővítményt.</span><span class="sxs-lookup"><span data-stu-id="8c782-329">Select the **Get insights** add-in.</span></span>
4. <span data-ttu-id="8c782-330">Az **Információk megszerzése** bővítmény részletei oldalon adja meg az alábbi értékeket.</span><span class="sxs-lookup"><span data-stu-id="8c782-330">On the **Get insights** add-in details page, enter the following values.</span></span>

    | <span data-ttu-id="8c782-331">Érték</span><span class="sxs-lookup"><span data-stu-id="8c782-331">Value</span></span>                                                    | <span data-ttu-id="8c782-332">Leírás</span><span class="sxs-lookup"><span data-stu-id="8c782-332">Description</span></span> |
    |----------------------------------------------------------|-------------|
    | <span data-ttu-id="8c782-333">CDS szervezet URL-címe</span><span class="sxs-lookup"><span data-stu-id="8c782-333">CDS Organization URL</span></span>                                     | <span data-ttu-id="8c782-334">A Dataverse szervezet URL-címe a Dataverse-példányból.</span><span class="sxs-lookup"><span data-stu-id="8c782-334">The Dataverse organization URL of the Dataverse instance.</span></span> <span data-ttu-id="8c782-335">Ha meg szeretné találni ezt az értéket, nyissa meg a [Power Apps-portált](https://make.powerapps.com), és válassza a jobb felső sarokban látható **Beállítások** gombot (fogaskerék szimbólum), válassza ki a **Speciális beállításokat**, majd másolja az URL-címet.</span><span class="sxs-lookup"><span data-stu-id="8c782-335">To find this value, open the [Power Apps portal](https://make.powerapps.com), select the **Settings** button (gear symbol) in the upper-right upper corner, select **Advanced settings**, and copy the URL.</span></span> <span data-ttu-id="8c782-336">(Az URL-cím a következőre végződik: „dynamics.com”).</span><span class="sxs-lookup"><span data-stu-id="8c782-336">(The URL ends with "dynamics.com.")</span></span> |
    | <span data-ttu-id="8c782-337">CDS szerv. azon.</span><span class="sxs-lookup"><span data-stu-id="8c782-337">CDS Org ID</span></span>                                               | <span data-ttu-id="8c782-338">A Dataverse-példány környezeti azonosítója.</span><span class="sxs-lookup"><span data-stu-id="8c782-338">The environment ID of the Dataverse instance.</span></span> <span data-ttu-id="8c782-339">Ha meg szeretné találni ezt az értéket, nyissa meg a [Power Apps-portált](https://make.powerapps.com), és válassza a jobb felső sarokban látható **Beállítások** gombot (fogaskerék szimbólum), válassza ki a **Testreszabás \> Fejlesztői erőforrások \> Példány hivatkozási információja lehetőséget**, majd másolja az **azonosító** értéket.</span><span class="sxs-lookup"><span data-stu-id="8c782-339">To find this value, open the [Power Apps portal](https://make.powerapps.com), select the **Settings** button (gear symbol) in the upper-right upper corner, select **Customizations \> Developer resources \> Instance Reference Information**, and copy the **ID** value.</span></span> |
    | <span data-ttu-id="8c782-340">CDS-bérlő azonosítója (címtárazonosító az AAD-ből)</span><span class="sxs-lookup"><span data-stu-id="8c782-340">CDS Tenant ID (Directory ID from AAD)</span></span>               | <span data-ttu-id="8c782-341">A Dataverse-példány bérlőazonosítója.</span><span class="sxs-lookup"><span data-stu-id="8c782-341">The tenant ID of the Dataverse instance.</span></span> <span data-ttu-id="8c782-342">Ha meg szeretné találni ezt az értéket, nyissa meg az [Azure-portál](https://portal.azure.com) lehetőséget, menjen ide: **Azure Active Directory**, és másolja át a **Bérlőazonosító** értéket.</span><span class="sxs-lookup"><span data-stu-id="8c782-342">To find this value, open the [Azure portal](https://portal.azure.com), go to **Azure Active Directory**, and copy the **Tenant ID** value.</span></span> |
    | <span data-ttu-id="8c782-343">Adja meg a rendszergazdai szerepkörrel rendelkező felhasználó objektumazonosítóját</span><span class="sxs-lookup"><span data-stu-id="8c782-343">Provide user object ID who has system administrator role</span></span> | <span data-ttu-id="8c782-344">Az Azure AD-felhasználó felhasználói objektumazonosítója a Dataverse-ben.</span><span class="sxs-lookup"><span data-stu-id="8c782-344">The Azure AD user object ID of the user in Dataverse.</span></span> <span data-ttu-id="8c782-345">Ennek a felhasználónak a Dataverse-példány rendszergazdájának kell lennie.</span><span class="sxs-lookup"><span data-stu-id="8c782-345">This user must be a system administrator of the Dataverse instance.</span></span> <span data-ttu-id="8c782-346">Ha meg szeretné találni ezt az értéket, nyissa meg az [Azure-portál](https://portal.azure.com) lehetőséget, menjen a **Azure Active Directory \> Felhasználók** lehetőségre, válassza ki a felhasználót, majd az **Identitás** szakaszba másolja be az **Objektumazonosító** értékét.</span><span class="sxs-lookup"><span data-stu-id="8c782-346">To find this value, open the [Azure portal](https://portal.azure.com), go to **Azure Active Directory \> Users**, select the user, and then, in the **Identity** section, copy the **Object ID** value.</span></span> |
    | <span data-ttu-id="8c782-347">Ez az alapértelmezett CDS-környezet a bérlő számára?</span><span class="sxs-lookup"><span data-stu-id="8c782-347">Is this the default CDS environment for the tenant?</span></span>      | <span data-ttu-id="8c782-348">Ha a Dataverse-példány a létrehozott első termelési példány, jelölje be ezt a jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="8c782-348">If the Dataverse instance was the first production instance that was created, select this check box.</span></span> <span data-ttu-id="8c782-349">Ha a Dataverse-példányt manuálisan hozták létre, törölje a jelet a jelölőnégyzetből.</span><span class="sxs-lookup"><span data-stu-id="8c782-349">If the Dataverse instance was manually created, clear this check box.</span></span> |

## <a name="configure-the-entity-store"></a><span data-ttu-id="8c782-350">Az entitásáruház konfigurálása</span><span class="sxs-lookup"><span data-stu-id="8c782-350">Configure the entity store</span></span>

<span data-ttu-id="8c782-351">Hajtsa végre az alábbi lépéseket, ha be szeretné állítani az entitásáruházat a Pénzügy környezetben.</span><span class="sxs-lookup"><span data-stu-id="8c782-351">Follow these steps to set up the entity store in your Finance environment.</span></span>

1. <span data-ttu-id="8c782-352">Lépjen a **Rendszerfelügyelet \> Beállítás \> Rendszerparaméterek \> Adatkapcsolatok** elemre.</span><span class="sxs-lookup"><span data-stu-id="8c782-352">Go to **System administration \> Setup \> System parameters \> Data connections**.</span></span>
2. <span data-ttu-id="8c782-353">Állíts a **Data Lake-integráció engedélyezése** elemet **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="8c782-353">Set the **Enable Data Lake integration** option to **Yes**.</span></span>
3. <span data-ttu-id="8c782-354">A következő Key Vault-mezők beállítása:</span><span class="sxs-lookup"><span data-stu-id="8c782-354">Set the following key vault fields:</span></span>

    - <span data-ttu-id="8c782-355">**Alkalmazás (kliens) azonosítója** – Adja meg a korábban létrehozott alkalmazáskliens azonosítóját.</span><span class="sxs-lookup"><span data-stu-id="8c782-355">**Application (client) ID** – Enter the application client ID that you created earlier.</span></span>
    - <span data-ttu-id="8c782-356">**Alkalmazás titkos kódja** – adja meg azt a titkos kódot, amelyet a korábban létrehozott alkalmazáshoz mentett.</span><span class="sxs-lookup"><span data-stu-id="8c782-356">**Application Secret** – Enter the secret that you saved for the application that you created earlier.</span></span>
    - <span data-ttu-id="8c782-357">**DNS neve** – A korábban létrehozott alkalmazásnál megkeresheti a tartománynév-rendszer (DNS) nevét.</span><span class="sxs-lookup"><span data-stu-id="8c782-357">**DNS name** – You can find the Domain Name System (DNS) name on the application details page for the application that you created earlier.</span></span>
    - <span data-ttu-id="8c782-358">**Titkos kód neve** – Adja meg a **storage-account-connection-string** értéket.</span><span class="sxs-lookup"><span data-stu-id="8c782-358">**Secret name** – Enter **storage-account-connection-string**.</span></span>

## <a name="feedback-and-support"></a><span data-ttu-id="8c782-359">Visszajelzés és támogatás</span><span class="sxs-lookup"><span data-stu-id="8c782-359">Feedback and support</span></span>

<span data-ttu-id="8c782-360">Kérjük, küldjön egy e-mailt az [Ügyfél fizetési elemzés (előzetes verzió)](mailto:fiap@microsoft.com) címre, ha visszajelzést szeretne adni, vagy támogatásra van szüksége.</span><span class="sxs-lookup"><span data-stu-id="8c782-360">Please send an email to [Customer payment insights (Preview)](mailto:fiap@microsoft.com) if you are interested in providing feedback or need support.</span></span>

## <a name="privacy-notice"></a><span data-ttu-id="8c782-361">Adatvédelmi nyilatkozat</span><span class="sxs-lookup"><span data-stu-id="8c782-361">Privacy notice</span></span>

<span data-ttu-id="8c782-362">Az előzetes verziók (1) kevesebb adatvédelmi és biztonsági intézkedést alkalmazhatnak, mint a Dynamics 365 Finance and Operations szolgáltatás (2) és nem vonatkozik a szolgáltatásiszint-szerződés (SLA) ehhez a szolgáltatáshoz, (3) nem használhatók olyan személyes adatok vagy más adatok feldolgozásához, melyekhez törvényi vagy jogszabályi megfelelési követelmények tartoznak, és (4) korlátozott támogatás tartozik hozzá.</span><span class="sxs-lookup"><span data-stu-id="8c782-362">Previews (1) might use less privacy and fewer security measures than the Dynamics 365 Finance and Operations service, (2) aren't included in the service level agreement (SLA) for this service, (3) should not be used to process personal data or other data that is subject to legal or regulatory compliance requirements, and (4) have limited support.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
