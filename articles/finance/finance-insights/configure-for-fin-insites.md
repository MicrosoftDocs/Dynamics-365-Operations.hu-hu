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
ms.openlocfilehash: 2443bb057a8b7fe280ed26ecae4e50f671b5e082
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5818800"
---
# <a name="configuration-for-finance-insights-preview"></a>Pénzügyi információk konfigurációja (előzetes verzió)

[!include [banner](../includes/banner.md)]

[!include [preview banner](../includes/preview-banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

A Pénzügyi információk a Microsoft Dynamics 365 Finance és a Microsoft Dataverse, az Azure és az AI Builder funkcióit kombinálva hatékony előrejelző eszközöket biztosítanak a szervezet számára. Ez a témakör azokat a konfigurációs lépéseket ismerteti, amelyek lehetővé teszik a rendszer számára a Pénzügyi információkban elérhető képességek használatát.

## <a name="deploy-dynamics-365-finance"></a>Dynamics 365 Finance üzembe helyezése

A környezetek üzembe helyezéséhez kövesse az alábbi lépéseket.

1. A Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásban hozzon létre vagy frissítse a Dynamics 365 Finance környezetet. A környezethez 10.0.11/Platform 35-ös vagy újabb alkalmazásverzióra van szükség.
2. A környezetnek magas rendelkezésre állású (HA) környezetnek kell lennie a tesztkörnyezetben. (Az ilyen típusú környezetet 2. szintű környezetnek is nevezik.) További információ: [Környezettervezés](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).
3. Ha Contoso bemutató adatokat használ, további mintaadatokra lesz szüksége az Ügyfélfizetési előrejelzések, a Pénzforgalmi előrejelzések és a Költségvetés-előrejelzések funkciók használatához. 

## <a name="configure-dataverse"></a>Dataverse konfigurálása

Végrehajthatja a manuális konfigurációs lépéseket, vagy felgyorsíthatja a konfigurációs folyamatot a rendelkezésre álló Windows PowerShell-parancsfájl használatával. Ha a PowerShell-parancsfájl futása befejeződött, a Pénzügyi információk konfigurálásához használható értékeket ad. 

> [!NOTE]
> Nyissa meg a PowerShellt a számítógépen a parancsfájl futtatásához. Lehet, hogy szüksége van a PowerShell 5-ös verziójára. Előfordulhat, hogy a Microsoft Azure CLI „Próbálja ki” opció nem működik.

# <a name="manual-configuration-steps"></a>[Manuális konfigurációs lépések](#tab/configuration-steps)

1. Nyissa meg a [Power Platform felügyeleti központot](https://admin.powerplatform.microsoft.com/), és az alábbi lépések végrehajtásával hozzon létre egy új Dataverse környezetet ugyanabban az Active Directory-bérlőben:

    1. Nyissa meg a **Környezetek** oldalt.

        [![Környezetek oldal](./media/power-pltfrm-admin-center.png)](./media/power-pltfrm-admin-center.png)

    2. Válassza ki az **Új környezet** lehetőséget.
    3. A **Típus** mezőben válassza ki a **Tesztkörnyezet** lehetőséget.
    4. Állítsa az **Adatbázis létrehozása** beállítást **Igen** értékre.
    5. Válassza ki **Következő** lehetőséget.
    6. Válassza ki a szervezet nyelvét és pénznemét.
    7. A többi mezőben hagyja meg az alapértelmezett értékeket.
    8. Válassza a **Mentés** lehetőséget.
    9. Frissítse a **Környezetek** oldalt.
    10. Várjon, amíg az **Állapot** mező értéke **Kész** állapotra nem frissül.
    11. Jegyezze fel a Dataverse szervezetazonosítót.
    12. Válassza ki a környezetet, majd válassza a **Beállítás** lehetőséget.
    13. Válassza az **Erőforrások \> Minden örökölt beállítás** lehetőséget.
    14. A felső navigációs sávon válassza a **Beállítások**, majd a **Testreszabás** lehetőséget.
    15. Válassza a **Fejlesztői erőforrások** lehetőséget.
    16. Állítsa be a **Példányhivatkozási adatok azonosítója** mezőt arra a Dataverse szervezeti azonosítóértékre, amelyről korábban feljegyzést készített.
    17. A böngésző címsorában jegyezze fel a Dataverse szervezet URL-címét. Az URL-cím lehet például `https://org42b2b3d3.crm.dynamics.com`.

2. Ha a Pénzforgalmi előrejelzések vagy a Költségvetési előrejelzések funkciót kívánja használni, kövesse az alábbi lépéseket a szervezet címjegyzetkorlátjának legalább 50 megabájtra (MB) történő frissítéséhez:

    1. Nyissa meg a [Power Apps portált](https://make.powerapps.com).
    2. Válassza ki az imént létrehozott környezetet, majd a **Speciális beállítások** lehetőséget.
    3. Válassza a **Beállítások \> E-mail konfigurációja** lehetőséget.
    4. Módosítsa a **Maximális fájlméret** mező értékét **51,200-ra**. (Az értéket kilobájtban \[KB\] kell kifejezni.)
    5. A módosítás mentéséhez kattintson az **OK** gombra.

# <a name="windows-powershell-configuration-script"></a>[Windows PowerShell konfigurációs parancsfájl](#tab/powershell-configuration-script)

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

## <a name="configure-the-azure-setup"></a>Az Azure beállítások konfigurálása

### <a name="enter-the-dataverse-directory-id-and-the-users-azure-ad-object-id"></a>Adja meg a Dataverse címtárazonosítót és a felhasználó Azure AD objektumazonosítóját

1. Adja meg a Dataverse címtárazonosítót:

    1. Nyissa meg az [Azure-portált](https://portal.azure.com).
    2. Jelentkezzen be a környezet létrehozásához használt felhasználói Dataverse azonosítóval.
    3. Ugorjon ide: **Azure Active Directory**.
    4. Másolja a **Bérlői azonosító** értékét.

2. Itt megadhatja a felhasználó Azure Active Directory (Azure AD) tárgyának azonosítóját:

    1. Az [Azure-portálon](https://portal.azure.com) nyissa meg a **Felhasználók** lehetőséget, és keresse meg a felhasználót az e-mail címe szerint.
    2. A felhasználó nevének kiválasztása.
    3. Másolja a **Tárgyazonosító** értékét.

### <a name="use-azure-cloud-shell-to-set-up-finance-insights-data-lake-resources"></a>Az Azure Cloud Shell használatával állíthatja be a Data Lake-erőforrásokkal kapcsolatos pénzügyi elemzéseket

# <a name="use-a-windows-powershell-script"></a>[Windows PowerShell parancsfájl használata](#tab/use-a-powershell-script)

Egy Windows PowerShell-parancsfájlt adott meg, így egyszerűen beállíthatja az Azure-erőforrásokat, amelyek az [Azure Data Lake exportálásának konfigurálása](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/configure-export-data-lake) részben találhatók. Ha a manuális beállítást szeretné elvégezni, hagyja ki ezt az eljárást, és folytassa az eljárást a [Manuális beállítás](#manual-setup) szakaszban.

> [!NOTE]
> Kövesse az alábbi lépéseket a PowerShell-parancsfájl futtatásához. Lehet, hogy az Azure CLI „Próbálja ki” lehetőség vagy a parancsfájl futtatása a számítógépen nem működik.

Kövesse az alábbi lépéseket az Azure konfigurálásához a Windows PowerShell-parancsfájl használatával. Az Azure-erőforráscsoport, az Azure-erőforrások és az Azure AD alkalmazások létrehozásához jogokkal kell rendelkeznie. A szükséges engedélyekről az [Engedélyek Azure AD ellenőrzése](https://docs.microsoft.com/azure/active-directory/develop/howto-create-service-principal-portal#permissions-required-for-registering-an-app) témakörben talál további információt.

1. Az [Azure-portálon](https://portal.azure.com) nyissa meg a cél Azure-előfizetés. Válassza a **Keresés** mezőtől jobbra lévő **Cloud Shell** gombot.
2. Válassza a **PowerShell** lehetőséget.
3. Hozzon létre tárhelyet, ha a rendszer erre kéri. Ezután töltse fel a Windows PowerShell-parancsfájlt a munkamenetbe.
4. Parancsfájl futtatása.
5. A parancsfájl futtatásához kövesse az utasításokat.
6. A parancsfájl kimenetéből származó információk segítségével telepítse az **Exportálás a Data Lake-be** bővítményt az LCS-ben.
7. A parancsfájl kimenetéből származó információk segítségével engedélyezze az entitás tárolását a Pénzügy (**Rendszerfelügyelet \> Rendszer paraméterei \> Adatkapcsolatok**) **Adatkapcsolatok** lapján.

### <a name="manual-setup"></a>Manuális beállítás

#### <a name="add-applications-to-the-azure-ad-tenant"></a>Alkalmazások hozzáadása az Azure AD-bérlőhöz

1. Az [Azure-portálban](https://portal.azure.com) menjen ide: **Azure Active Directory**.
2. Válassza a **Vállalati \> alkalmazások kezelése** lehetőséget.
3. Keresse meg a következő alkalmazásokat alkalmazásazonosító szerint.

    | Pályázat                              | Alkalmazás azonosítója                               |
    |------------------------------------------|--------------------------------------|
    | Microsoft Dynamics ERP mikroszolgáltatások     | 0cdb527f-a8d1-4bf8-9436-b352c68682b2 |
    | Microsoft Dynamics ERP mikroszolgáltatások CDS | 703e2651-d3fc-48f5-942c-74274233dba8 |
    | AI Builder engedélyezési szolgáltatás         | ad40333e-9910-4b61-b281-e3aeeb8c3ef3 |

Ha az előző alkalmazások egyikét sem találja, próbálkozzon az alábbi lépésekkel.

1. A helyi számítógépen válassza a **Start** menüt, és keresse meg a **powershell** lehetőséget.
2. Jelölje ki és tartsa lenyomva (vagy nyomja meg a jobb egérgombot) a **Windows PowerShell** lehetőséget, majd válassza a **Futtatás rendszergazdaként** elemet.
3. Futtassa a következő parancsot az **AzureAD-modul** telepítéséhez.

    `Install-Module -Name AzureAD`

4. Ha egy NuGet szolgáltatóra van szükség a folytatáshoz, válassza az **Y** lehetőséget a telepítéshez.
5. Ha „Nem megbízható adattár” üzenet jelenik meg, a folytatáshoz válassza az **Y** lehetőséget.
6. Minden hozzáadandó alkalmazáshoz futtassa a következő parancsokat az alkalmazás Azure AD-hoz való hozzáadásához. Amikor a rendszer kéri, jelentkezzen be Azure AD-rendszergazdaként.

    `Connect-AzureAD`

    `New-AzureADServicePrincipal –AppId <AppId>`

#### <a name="create-azure-resources"></a>Azure-erőforrások létrehozása

> [!NOTE]
> Győződjön meg arról, hogy a következő erőforrásokat hozza létre ugyanabban a Azure AD-példányban, mint a Dataverse-környezetben. Más Azure AD-példányból származó erőforrások nem használhatók.

1. Új társzámla létrehozása:

    1. Hozzon létre egy társzámlát az [Azure-portálon](https://portal.azure.com).
    2. A **Társzámla létrehozása** párbeszédpanelen adja meg a következő mezőket:

        - **Hely** – Válassza ki azt az adatközpontot, ahol a környezet található.
        - **Teljesítmény** – Javasoljuk, hogy a **Standard** lehetőséget válassza.
        - **Fiók fajtája** – A **StorageV2** lehetőséget kell választania.

    3. A **Speciális beállítások** párbeszédpanel **Data Lake Storage Gen2** lehetőséghez válassza az **Engedélyezés** elemet a **Hierarchikus névterek** funkció alatt. Ha letiltja ezt a funkciót, nem használhatja fel a Finance and Operations alkalmazások által olyan szolgáltatások használatával írt adatokat, mint például a Power BI adatfolyamok.
    4. Válassza a **Vélemény és létrehozás** lehetőséget. A központi telepítés befejezése után az új erőforrás megjelenik az Azure-portálon.
    5. Nyissa meg a létrehozott tárfiókot.
    6. A bal oldali menüben válassza a **Hívóbetű** lehetőséget.
    7. Másolja és mentse a kapcsolati karakterláncot a **Key1** vagy a **Key2** lehetőséghez.
    8. Másolja és mentse a tárfiók nevét.

2. Új kulcstároló létrehozása:

    1. Hozzon létre egy kulcstárolót az [Azure-portálon](https://portal.azure.com).
    2. A **Kulcstartó létrehozása** párbeszédpanel, a **Hely** mezőben jelölje ki azt az adatközpontot, ahol a környezet található.
    3. A kulcstartó létrehozása után jelölje ki a listában, majd válassza ki a **Titkok** lehetőséget.
    4. Válassza a **Generálás/Importálás** lehetőséget.
    5. A **Titkos kód létrehozása** párbeszédpanel **Feltöltési beállítások** mezőjében válassza a **Manuális** lehetőséget.
    6. Adja meg a titkos kód nevét. Jegyezze fel a nevet, mert később meg kell adnia.
    7. Az **Érték** mezőbe írja be azt a kapcsolati karakterláncot, amelyet a korábbi eljárásban a tárfiókból nyert.
    8. Válassza ki az **Engedélyezés**, majd a **Létrehozás** lehetőséget. A rendszer létrehozta a titkot, és hozzáadta a Kulcstartót.
    9. Nyissa meg a **Kulcstartó áttekintése** lehetőséget, és jegyezze fel a DNS-nevet.

3. Azure AD alkalmazás létrehozása és regisztrálása:

    1. Az [Azure portálon](https://portal.azure.com) menjen ide: **Azure Active Directory**, majd válassza az **Alkalmazás regisztrálása** lehetőséget.
    2. Válassza ki az **Új alkalmazásregisztráció** lehetőséget, és állítsa be a következő mezőket:

        - **Név** – Írja be az alkalmazás nevét.
        - **Alkalmazás típusa** – válassza ki a **webes API-t**.
        - **URI-beállítás átirányítása** – Adja meg a Dynamics 365 példány URL-címét, például: `https://yourdynamicsinstance.dynamics.com/auth`.

    3. Nyissa meg az imént létrehozott alkalmazást, és másolja, majd mentse az **Alkalmazás (kliens) azonosítójának** értékét. Ezt az értéket később kell megadni, amikor beállítja a kulcstartót.
    4. Nyissa meg az **API-engedélyek** lehetőséget, majd kövesse az alábbi lépéseket:

        1. Válassza az **Engedély hozzáadása** lehetőséget.
        2. Válassza ki az **Azure kulcstartó** lehetőséget.
        3. A delegált engedélyek kiválasztása után válassza ki a **felhasználó\_megszemélyesítését**.
        4. Válassza az **Engedélyek hozzáadása** lehetőséget.

    5. Az alkalmazás menüjében válassza ki a **Tanúsítványok \& titkai** lehetőséget, majd a Key Vault létrehozásához hajtsa végre az alábbi lépéseket:

        1. Válassza ki az **Új titkos ügyfélkód** lehetőséget.
        2. Adjon meg egy nevet a **Kulcsleírás** mezőben.
        3. Válasszon ki egy időtartamot, majd a **Hozzáadás** lehetőséget. Az **Érték** mezőben egy titkos kód jön létre.
        4. A titkos kód értékének másolása és mentése.

4. Key Vault titkos kódok létrehozása:

    1. Menjen a korábban létrehozott kulcstartóhoz, és válassza ki a **Titkokat**.
    2. Hajtsa végre az alábbi lépéseket mindegyik titkos kód névhez a következő táblában:

        1. Válassza a **Generálás/Importálás** lehetőséget.
        2. A **Titkos kód létrehozása** párbeszédpanel **Feltöltési beállítások** mezőjében válassza a **Manuális** lehetőséget.
        3. A következő táblából hozza létre a titkos kód nevét és értékét.
        4. Válassza ki az **Engedélyezés**, majd a **Létrehozás** lehetőséget. A rendszer létrehozta a titkot, és hozzáadta a Kulcstartót.

        | Titkos név                       | Titkos kód értéke                                                                                |
        |-----------------------------------|---------------------------------------------------------------------------------------------|
        | alkalmazás azonosítója                            | A korábban létrehozott alkalmazás alkalmazásazonosítója                                      |
        | alkalmazás titkos kódja                        | A korábban mentett titkos ügyfélkód                                                    |
        | storage-account-name              | A korábban létrehozott tárfiók neve, például **storageaccount1**       |
        | storage-account-connection-string | A tárfiók **Elérési kulcsok** lapjáról átmásolt kapcsolati karakterlánc |

5. Az alkalmazás engedélyezése a kulcstartó eléréséhez:

    1. A [Azure-portál](https://portal.azure.com) webhelyen nyissa meg a korábban létrehozott kulcstartót.
    2. Válassza ki a hozzáférési szabályzatokat.
    3. Hajtsa végre az alábbi lépéseket mindegyik alkalmazáshoz a következő táblában:

        1. Válassza a **Hozzáférési szabályzat hozzáadása** elemet a hozzáférési szabályzat létrehozásához.
        2. A **Titkos engedélyek** mezőben válassza ki a következő táblában szereplő engedélyeket.
        3. A **Résztvevő kiválasztása** mezőben keressen rá az alkalmazás megjelenített nevére a következő táblából.
        4. Válassza ki a **Kiválasztás** lehetőséget.
        5. Válassza a **Hozzáadás** lehetőséget.
        6. Válassza a **Mentés** lehetőséget.

        | Pályázat                                              | Engedélyek |
        |----------------------------------------------------------|-------------|
        | A létrehozott új alkalmazás megjelenített neve | Kérés, listázás   |
        | **Microsoft Dynamics ERP mikroszolgáltatások**                 | Kérés, listázás   |

6. Szerepkörök hozzárendelése a tárfiókhoz:

    1. A [Azure-portál](https://portal.azure.com) webhelyen nyissa meg a korábban létrehozott tárfiókot.
    2. Válassza ki az **Access Control (IAM)** lehetőséget, majd válassza ki a **Szerepkör hozzárendeléseket**.
    3. Válassza a **Hozzáadás, Szerepkör-hozzárendelés hozzáadása** lehetőséget.
    4. Hajtsa végre az alábbi lépéseket mindegyik alkalmazáshoz a következő táblában:

        1. Válassza ki a szerepkört az alábbi táblából.
        2. A **Hozzáférés hozzárendelése** mezőben hagyja meg az **Azure AD felhasználó, csoport vagy szolgáltatásnév** értéket.
        3. A **Kiválasztás** mezőben adja meg a következő táblában szereplő alkalmazást.
        4. Válassza a **Mentés** lehetőséget.

        | Pályázat                                              | Szerep                        |
        |----------------------------------------------------------|-----------------------------|
        | A létrehozott új alkalmazás megjelenített neve | Tulajdonos                       |
        | A létrehozott új alkalmazás megjelenített neve | Hozzájáruló                 |
        | A létrehozott új alkalmazás megjelenített neve | Tárfiók közreműködője |
        | A létrehozott új alkalmazás megjelenített neve | Tárolási blobadatok tulajdonosa     |
        | **AI Builder engedélyezési szolgáltatás**                     | Tárolási blobadatok olvasója    |

# <a name="azure-cli"></a>[Azure parancssori felület](#tab/azure-azure-cli)

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

## <a name="configure-the-entity-store"></a>Az entitásáruház konfigurálása

Hajtsa végre az alábbi lépéseket, ha be szeretné állítani az entitásáruházat a Pénzügy környezetben.

1. Lépjen a **Rendszerfelügyelet \> Beállítás \> Rendszerparaméterek \> Adatkapcsolatok** elemre.
2. Állíts a **Data Lake-integráció engedélyezése** elemet **Igen** értékre.
3. A következő Key Vault-mezők beállítása:

    - **Alkalmazás (kliens) azonosítója** – Adja meg a korábban létrehozott alkalmazáskliens azonosítóját.
    - **Alkalmazás titkos kódja** – adja meg azt a titkos kódot, amelyet a korábban létrehozott alkalmazáshoz mentett.
    - **DNS neve** – A korábban létrehozott alkalmazásnál megkeresheti a tartománynév-rendszer (DNS) nevét.
    - **Titkos kód neve** – Adja meg a **storage-account-connection-string** értéket.

## <a name="configure-the-data-lake"></a>A Data Lake konfigurálása

Hajtsa végre az alábbi lépéseket, ha az Azure Data Lake-bővítményt hozzá szeretné adni a környezethez az LCS használatával.

1. Jelentkezzen be az LCS-be, majd a lap jobb oldalán látható környezet neve alatt válassza ki a **Minden részlet** lehetőséget.
2. A **Környezeti bővítmények** szakaszban válassza az **Új bővítmény telepítése** lehetőséget.
3. Válassza a **Data Lake exportálása** bővítményt.
4. Adja meg az alábbi értékeket.

    | Érték                                                              | Leírás |
    |--------------------------------------------------------------------|-------------|
    | Az Azure-előfizetés bérlőazonosítója, ahol a Key Vault található | A bérlőazonosító, ahol a tárfiók, az alkalmazások és a kulcstartók találhatók. Ha meg szeretné találni ezt az értéket, nyissa meg az [Azure-portál](https://portal.azure.com) lehetőséget, menjen ide: **Azure Active Directory**, és másolja át a **Bérlőazonosító** értéket. |
    | Adja meg a Key Vault DNS-nevét.                             | A kulcstartó DNS-neve (például: `https://customkeyvault.vault.azure.net/`). (Ez az érték megegyezik az entitásüzletben használt DNS-névvel.) |
    | Adja meg a tárfiók nevét tartalmazó titkos kódot   | **storage-account-name** |
    | Titkós kód neve az alkalmazásazonosítóhoz, amelyet a Data Lake eléréséhez használnak          | **alkalmazás azonosítója** |
    | Az alkalmazásazonosítóval használandó titkos kód neve                                 | **alkalmazás titkos kódja** |

5. Fogadja el a feltételeket, és válassza a **Telepítés** lehetőséget.

A bővítményt néhány percen belül telepíti a program.

## <a name="configure-ai-builder"></a>AI Builder konfigurálása

1. Jelentkezzen be a LCS-ba, majd nyissa meg a **Környezet részletei** oldalt.
2. Görgessen le a **Környezeti bővítmények** szakaszhoz. Tekintse meg azokat a bővítményeket, amelyek már telepítve vannak ebben a környezetben. Ha a **Data Lake exportálása** bővítmény nincs a többi között, konfigurálja ezt a bővítményt.
3. Válassza ki az **Információk megszerzése** bővítményt.
4. Az **Információk megszerzése** bővítmény részletei oldalon adja meg az alábbi értékeket.

    | Érték                                                    | Leírás |
    |----------------------------------------------------------|-------------|
    | CDS szervezet URL-címe                                     | A Dataverse szervezet URL-címe a Dataverse-példányból. Ha meg szeretné találni ezt az értéket, nyissa meg a [Power Apps-portált](https://make.powerapps.com), és válassza a jobb felső sarokban látható **Beállítások** gombot (fogaskerék szimbólum), válassza ki a **Speciális beállításokat**, majd másolja az URL-címet. (Az URL-cím a következőre végződik: „dynamics.com”). |
    | CDS szerv. azon.                                               | A Dataverse-példány környezeti azonosítója. Ha meg szeretné találni ezt az értéket, nyissa meg a [Power Apps-portált](https://make.powerapps.com), és válassza a jobb felső sarokban látható **Beállítások** gombot (fogaskerék szimbólum), válassza ki a **Testreszabás \> Fejlesztői erőforrások \> Példány hivatkozási információja lehetőséget**, majd másolja az **azonosító** értéket. |
    | CDS-bérlő azonosítója (címtárazonosító az AAD-ből)               | A Dataverse-példány bérlőazonosítója. Ha meg szeretné találni ezt az értéket, nyissa meg az [Azure-portál](https://portal.azure.com) lehetőséget, menjen ide: **Azure Active Directory**, és másolja át a **Bérlőazonosító** értéket. |
    | Adja meg a rendszergazdai szerepkörrel rendelkező felhasználó objektumazonosítóját | Az Azure AD-felhasználó felhasználói objektumazonosítója a Dataverse-ben. Ennek a felhasználónak a Dataverse-példány rendszergazdájának kell lennie. Ha meg szeretné találni ezt az értéket, nyissa meg az [Azure-portál](https://portal.azure.com) lehetőséget, menjen a **Azure Active Directory \> Felhasználók** lehetőségre, válassza ki a felhasználót, majd az **Identitás** szakaszba másolja be az **Objektumazonosító** értékét. |
    | Ez az alapértelmezett CDS-környezet a bérlő számára?      | Ha a Dataverse-példány a létrehozott első termelési példány, jelölje be ezt a jelölőnégyzetet. Ha a Dataverse-példányt manuálisan hozták létre, törölje a jelet a jelölőnégyzetből. |

## <a name="feedback-and-support"></a>Visszajelzés és támogatás

Kérjük, küldjön egy e-mailt az [Ügyfél fizetési elemzés (előzetes verzió)](mailto:fiap@microsoft.com) címre, ha visszajelzést szeretne adni, vagy támogatásra van szüksége.

## <a name="privacy-notice"></a>Adatvédelmi nyilatkozat

Az előzetes verziók (1) kevesebb adatvédelmi és biztonsági intézkedést alkalmazhatnak, mint a Dynamics 365 Finance and Operations szolgáltatás (2) és nem vonatkozik a szolgáltatásiszint-szerződés (SLA) ehhez a szolgáltatáshoz, (3) nem használhatók olyan személyes adatok vagy más adatok feldolgozásához, melyekhez törvényi vagy jogszabályi megfelelési követelmények tartoznak, és (4) korlátozott támogatás tartozik hozzá.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]