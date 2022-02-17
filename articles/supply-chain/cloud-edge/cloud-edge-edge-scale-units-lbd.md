---
title: Peremhálózati skálázási egységek telepítése egyedi hardverre LBD segítségével
description: Ez a témakör bemutatja, hogy hogyan lehet a helyszíni peremhálózati egységeit a helyi üzleti adatokon (BELID) alapuló egyedi hardvereszközök és telepítések segítségével létesíteni.
author: cabeln
ms.date: 01/24/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: cabeln
ms.search.validFrom: 2021-04-13
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 1204b65e76c107c29a94a61c321064a87c7571fb
ms.sourcegitcommit: 948978183a1da949e35585b28b8e85a63b6c12b1
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/25/2022
ms.locfileid: "8024542"
---
# <a name="deploy-edge-scale-units-on-custom-hardware-using-lbd"></a>Peremhálózati skálázási egységek telepítése egyedi hardverre LBD segítségével

[!include [banner](../includes/banner.md)]

A peremhálózati egységek fontos szerepet töltenek be az ellátásilánc-kezelés elosztott topológiája területén. A hibrid topológiában eloszthatja a terhelést a Supply Chain Management felhőközpontja és a felhőben vagy a peremen lévő további skálaegységek között.

A peremhálózati egységek úgy telepíthetők, hogy létrehoznak egy helyi üzleti adatok (LBD) [helyi környezetet](../../fin-ops-core/dev-itpro/deployment/on-premises-deployment-landing-page.md), majd úgy konfigurálják, hogy skálázási egységként működjön a terjesztett hibrid topológiában a Supply Chain Managementhez. Ez úgy érhető el, hogy a helyi LBD-környezetet egy Supply Chain Management környezethez társítja a felhőben, amely a központként való működésre van konfigurálva.  

Ez a témakör azt írja le, hogyan lehet beállítani a helyi LBD-környezetet peremskálaegységként, majd társítani azt egy központhoz.

## <a name="infrastructure-considerations"></a>Infrastrukturális szempontok

Az élléptékű egységek helyszíni környezetekben futnak, így az infrastrukturális követelmények meglehetősen hasonlóak. Vannak azonban bizonyos különbségek, amelyeket meg kell jegyezni:

- Az élléptékű egységek nem használnak pénzügyi jelentést, így nem igényelnek pénzügyi jelentési csomópontokat.
- A gyártási és raktározási munkaterhelés nem számításigényes, ezért fontolja meg az AOS-csomópontok számítási teljesítményének megfelelő méretezését.

## <a name="deployment-overview"></a>Telepítés áttekintése

Itt talál egy áttekintést a telepítési lépésekről.

1. **Engedélyezzen egy LBD-helyet az LBD-projektben a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásban.**

1. **Az LBD-környezet beállítása és telepítése *üres* adatbázissal.**

    Az LCS segítségével a legújabb topológiával és egy üres adatbázissal telepítheti az LBD-környezetet. A további tudnivalókat lásd a témakör későbbi [Az LBD-környezet beállítása és telepítése üres adatbázissal](#set-up-deploy) szakaszát. A Supply Chain Management 10.0.21-es vagy újabb verzióját kell használnia a hub és a scale unit környezetekben.

1. **Célcsomagok feltöltése LBD-projekteszközökbe az LCS-ben.**

    A központban és a perem skálázási egységen használt alkalmazás-, platform- és testreszabási csomagok előkészítése. A további tudnivalókat lásd a témakör későbbi, [Célcsomagok feltöltése LBD-projekteszközökbe az LCS-ben](#upload-packages) című szakaszában.

1. **Az LBD-környezet kiszolgálása a célcsomagokkal.**

    Ezzel a lépéssel gondoskodik arról, hogy ugyanaz a build és testreszabások legyenek telepítve a központban és küllőben. A további tudnivalókat lásd a témakör későbbi, [Az LBD-környezet kiszolgálása a célcsomagokkal](#service-target-packages) részében.

1. **A skálázási egység konfigurációjának és a terhelés hozzárendelésének befejezése.**

    A további tudnivalókat lásd a témakör későbbi, [az LBD perem skálázási egység hozzárendelése központhoz](#assign-edge-to-hub) című témakörben.

A témakör hátralévő részei további részleteket tartalmaznak lépések elvégzéséről.

## <a name="set-up-and-deploy-an-lbd-environment-with-an-empty-database"></a><a name="set-up-deploy"></a>Az LBD-környezet beállítása és telepítése üres adatbázissal

Ez a lépés egy működő LBD-környezetet hoz létre. A környezet azonban nem feltétlenül ugyanazt az alkalmazás- és platformverziót használja, mint a központi környezet. Emellett még hiányoznak belőle a testreszabások, és még nincs engedélyezve a skálázási egységként való működéshez.

1. Kövesse a [Helyszíni környezetek beállítása és telepítése (Platformfrissítés 41-es és újabb verziókon)](../../fin-ops-core/dev-itpro/deployment/setup-deploy-on-premises-pu41.md) rész utasításait. A Supply Chain Management 10.0.21-es vagy újabb verzióját kell használnia a hub és a scale unit környezetekben. Ezenkívül az infrastruktúra-szkriptek 2.12.0-s vagy újabb verzióját kell használnia. 

    > [!IMPORTANT]
    > Olvassa el a szakasz további részét, **mielőtt** végrehajtaná annak a témakörnek a lépéseit.

1. Mielőtt leírná a konfigurációt az infrastruktúra\\ConfigTemplate.xml fájlban, futtassa a következő parancsfájlt:

    ```powershell
    .\Configure-ScriptsForEdgeScaleUnits.ps1 -ConfigurationFilePath .\ConfigTemplate.xml
    ```

    > [!NOTE]
    > Ez a parancsfájl eltávolít minden olyan konfigurációt, amely nem szükséges a peremhálózati skálázási egységek telepítéséhez.

1. Állítsa be az üres adatokat tartalmazó adatbázist az [Adatbázisok konfigurálása](../../fin-ops-core/dev-itpro/deployment/setup-deploy-on-premises-pu41.md#configuredb) résznek megfelelően. Használja az üres data.bak fájlt ehhez a lépéshez.
1. Miután befejezte a [Adatbázisok konfigurálása](../../fin-ops-core/dev-itpro/deployment/setup-deploy-on-premises-pu41.md#configuredb) lépésben futtassa a következő parancsfájlt a Scale Unit Alm Orchestrator adatbázis konfigurálásához.

    > [!NOTE]
    > Ne konfigurálja a Pénzügyi jelentési adatbázist a [Adatbázisok konfigurálása](../../fin-ops-core/dev-itpro/deployment/setup-deploy-on-premises-pu41.md#configuredb) lépés.

    ```powershell
    .\Initialize-Database.ps1 -ConfigurationFilePath .\ConfigTemplate.xml -ComponentName EdgeScaleUnit
    ```

    Az Initialize-Database.ps1 szkript a következő műveleteket hajtja végre:

    1. Hozzon létre egy üres adatbázist, amely névvel rendelkezik **ScaleUnitAlmDb**.
    2. Az alábbi táblázat alapján rendelje hozzá a felhasználókat adatbázis-szerepekhez.

        | Felhasználó            | Típus | Adatbázis szerepkör |
        |-----------------|------|---------------|
        | svc-LocalAgent$ | gMSA | db\_ tulajdonos     |

1. Továbbra is kövesse az utasításokat [Helyszíni környezetek beállítása és üzembe helyezése (41-es és újabb platformfrissítések)](../../fin-ops-core/dev-itpro/deployment/setup-deploy-on-premises-pu41.md).
1. Miután befejezte a [Az AD FS konfigurálása](../../fin-ops-core/dev-itpro/deployment/setup-deploy-on-premises-pu41.md#configuredb) lépést, kövesse az alábbi lépéseket:

    1. Hozzon létre egy új Active Directory összevonási szolgáltatások (AD FS) alkalmazást, amely lehetővé teszi az Alm Orchestration szolgáltatás számára, hogy kommunikáljon az alkalmazásobjektum-kiszolgálóval (AOS).

        ```powershell
        # Host URL is your DNS record\host name for accessing the AOS
        .\Create-ADFSServerApplicationForEdgeScaleUnits.ps1 -ConfigurationFilePath .\ConfigTemplate.xml -HostUrl 'https://ax.d365ffo.onprem.contoso.com'
        ```

    1. Újat csinálni Azure Active Directory (Azure AD) alkalmazás, amely lehetővé teszi, hogy az Alm Orchestration szolgáltatás kommunikáljon a Scale Unit Management szolgáltatással.

        ```powershell
        # Example .\Create-SumAADApplication.ps1 -ConfigurationFilePath ..\ConfigTemplate.xml -TenantId '6240a19e-86f1-41af-91ab-dbe29dbcfb95' -ApplicationDisplayName 'EdgeAgent-SUMCommunication-EN01'
        .\Create-SumAADApplication.ps1 -ConfigurationFilePath '<Path of the ConfigTemplate.xml file>' `
                                       -TenantId '<ID of the tenant where your cloud hub is deployed>' `
                                       -ApplicationDisplayName '<Whichever name you want the Azure AD app to have>'
        ```

1. Továbbra is kövesse az utasításokat [Helyszíni környezetek beállítása és üzembe helyezése (41-es és újabb platformfrissítések)](../../fin-ops-core/dev-itpro/deployment/setup-deploy-on-premises-pu41.md). Amikor meg kell adnia a helyi ügynök konfigurációját, győződjön meg arról, hogy engedélyezte az Edge Scale Unit jellemzőit, és megadta az összes szükséges paramétert.

    ![Az élskálázási egység szolgáltatásainak engedélyezése.](media/EnableEdgeScaleUnitFeatures.png "Az élskálázási egység szolgáltatásainak engedélyezése.")

1. Mielőtt telepíti a környezetet az LCS-ből, állítsa be a telepítés előtti parancsfájlt. További információ: [Helyi ügynök telepítés előtti és telepítés utáni parancsfájljai](../../fin-ops-core/dev-itpro/lifecycle-services/pre-post-scripts.md).

    1. Másolja ki a Configure-CloudAndEdge.ps1 szkriptet a **ScaleUnit** mappa be **Infrastruktúra szkriptek** hoz **Szkriptek** mappát a környezetben beállított ügynökfájl-tárhelymegosztásban. A jellemző elérési út \\\\lbdiscsi01\\agent\\Scripts.
    2. Hozza létre a **PreDeployment.ps1** parancsfájlt, amely a szükséges paraméterekkel meghívja a parancsfájlokat. A telepítés előtti parancsfájlt az ügynök fájlmegosztásán található **Parancsfájlok** mappába kell tenni. Ellenkező esetben nem futtatható. Egy jellemző elérési út: \\\\lbdiscsi01\\agent\\Scripts\\PreDeployment.ps1.

        Az PreDeployment.ps1 parancsfájl tartalma hasonlít a következő példához.

        ```powershell
        $agentShare = '\\lbdiscsi01\agent'
        
        Write-Output "AgentShare is set to $agentShare" 
        . $PSScriptRoot\Configure-CloudAndEdge.ps1 -AgentShare $agentShare -InstanceId '@A'
        ```

        > [!NOTE]
        > Az InstanceId paraméter csak két karakterből állhat. Az első karakter a @ karakter, a második pedig bármilyen nagybetű lehet az angol ábécében.
        >
        > - Érvényes értékek:
        >   - @D
        >   - @X
        > - Nem érvénye értékek:
        >   - @a
        >   - @4
        >   - @#

1. Telepítse a környezetet a rendelkezésre álló legújabb alaptopológia segítségével.
1. A környezet üzembe helyezése után kövesse az alábbi lépéseket:

    1. Futtassa a következő SQL-parancsokat az üzleti adatbázisban (AXDB).

        ```sql
        ALTER TABLE dbo.NUMBERSEQUENCETABLE ENABLE CHANGE_TRACKING WITH (TRACK_COLUMNS_UPDATED = ON)
        delete from NumberSequenceTable
        delete from NumberSequenceReference
        delete from NumberSequenceScope
        delete from FeatureManagementMetadata
        delete from FeatureManagementState
        delete from SysFeatureStateV0
        ```

    1. Növelje az egyidejű maximális kötegelt munkamenetet 4-nél nagyobb értékre.

        ```sql
        Update batchserverconfig set maxbatchsessions = '<Replace with number of concurrent batch tasks you want>'
        ```

    1. Ellenőrizze, hogy a változáskövetés engedélyezve van-e az üzleti adatbázisban (AXDB).

        1. Nyissa meg az SQL Server Management Studio (SSMS) alkalmazást.
        1. Válassza ki és tartsa lenyomva (vagy kattintson a jobb gombbal) az üzleti adatbázisra (AXDB), majd válassza ki **Tulajdonságok**.
        1. A megjelenő ablakban válassza ki a lehetőséget **Nyomon követés módosítása**, majd állítsa be a következő értékeket:

            - **Change Tracking:** *Igaz*
            - **Adatmegőrzési idő:** *7*
            - **Adatmegőrzés egysége:** *Nap*
            - **Automatikus tisztítás:** *Igaz*

    1. Adja hozzá a korábban létrehozott AD FS alkalmazásazonosítót (a Create-ADFSServerApplicationForEdgeScaleUnits.ps1 parancsfájl használatával) a Azure AD alkalmazástáblázatot a skálaegységben. Ezt a lépést manuálisan is végrehajthatja a felhasználói felületen (UI). Alternatív megoldásként kiegészítheti az adatbázison keresztül a következő szkript használatával.

        ```sql
        DECLARE @ALMOrchestratorId NVARCHAR(76) = '<Replace with the ADFS Application ID created in a previous step>';

        IF NOT EXISTS (SELECT TOP 1 1 FROM SysAADClientTable WHERE AADClientId = @ALMOrchestratorId)
        BEGIN
            INSERT INTO SysAADClientTable (AADClientId, UserId, Name, ModifiedBy, CreatedBy)
            VALUES (@ALMOrchestratorId, 'ScaleUnitManagement', 'Scale Unit Management', 'Admin', 'Admin');
        END
        ```

## <a name="set-up-an-azure-key-vault-and-an-azure-ad-application-to-enable-communication-between-scale-units"></a><a name="set-up-keyvault"></a> Állítson be egy Azure Key Vault és egy Azure AD alkalmazás, amely lehetővé teszi a mérlegegységek közötti kommunikációt

1. A környezet üzembe helyezése után hozzon létre egy továbbit Azure AD alkalmazás, amely megbízható kommunikációt tesz lehetővé a hub és a mérlegegység között.

    ```powershell
    .\Create-SpokeToHubAADApplication.ps1 -ConfigurationFilePath '<Path of the ConfigTemplate.xml file>' `
                                          -TenantId '<ID of the tenant where your cloud hub is deployed>' `
                                          -ApplicationDisplayName '<Whichever name you want the Azure AD app to have>'
    ```

1. Az alkalmazás létrehozása után létre kell hoznia egy titkos ügyfélfiókot, és el kell mentenie az információkat egy Azure-kulcstárolóba. Ezenkívül hozzáférést kell biztosítania a Azure AD létrehozott alkalmazást, hogy le tudja kérni a kulcstárolóban tárolt titkokat. Az Ön kényelme érdekében a következő szkript automatikusan végrehajtja az összes szükséges műveletet.

    ```powershell
    .\Create-SpokeToHubAADAppSecrets.ps1 -ConfigurationFilePath '<Path of the ConfigTemplate.xml file>' `
                                         -TenantId '<ID of the tenant where your cloud hub is deployed>' `
                                         -SubscriptionName '<Any subscription within your tenant>' `
                                         -ResourceGroupName '<Any resource group within your subscription>' `
                                         -KeyVaultName '<Any key vault within your resource group>' `
                                         -Location '<Any Azure location where Azure Key Vault is available>' `
                                         -LCSEnvironmentId '<The LCS environment ID of your deployed scale unit>' `
    ```

    > [!NOTE]
    > Ha nincs kulcstároló, amely rendelkezik a megadott értékkel **KeyVaultName** érték létezik, a szkript automatikusan létrehoz egyet.

1. Add hozzá a Azure AD az imént létrehozott alkalmazásazonosító (a Create-SpokeToHubAADApplication.ps1 parancsfájl használatakor) a Azure AD alkalmazástáblázatot a hubban. Ezt a lépést manuálisan is végrehajthatja a felhasználói felületen keresztül.

## <a name="upload-target-packages-into-lbd-project-assets-in-lcs"></a><a name="upload-packages"></a>Célcsomagok feltöltése LBD-projekteszközökbe az LCS-ben

Ez a lépés készíti elő az alkalmazás verzióját, a platformverziót és a testreszabásokat, amelyek át fognak kerülni az LBD skálaegység-környezetbe.

1. Töltse fel ugyanazt kombinált alkalmazás-/platformcsomagok amely alkalmazva lett a központi környezetben az LCS helyi projekt eszközkönyvtárába.
1. Kérje le egy másolatát az egyéni telepíthető csomagnak amely alkalmazva lett a központi környezetben, és töltse fel az LCS helyi projekt eszközkönyvtárába.

## <a name="service-the-lbd-environment-with-target-packages"></a><a name="service-target-packages"></a>Az LBD-környezet kiszolgálása a célcsomagokkal

Ez a lépés illeszti alkalmazás verzióját, a platformverziót és a testreszabásokat az LBD skálázási egység környezetben a központtal.

1. Szolgálja ki az LBD-környezetet az előző lépésben feltöltött, kombinált alkalmazás-/platformcsomaggal.
1. Szolgálja ki az LBD-környezetet az előző lépésben feltöltött egyéni telepíthető csomaggal.

    ![Frissítések alkalmazása az LCS-ben.](media/cloud_edge-LBD-LCS-ServiceLBDEnv1.png "Frissítések alkalmazása az LCS-ben")

    ![A testreszabási csomag kiválasztása.](media/cloud_edge-LBD-LCS-ServiceLBDEnv2.png "A testreszabási csomag kiválasztása")

## <a name="assign-your-lbd-edge-scale-unit-to-a-hub"></a><a name="assign-edge-to-hub"></a>Az LBD peremhálózati skálaegység hozzárendelése egy központhoz

A Scale Unit Management Portalon keresztül konfigurálhatja és kezelheti az élskálázási egységet. További információkért lásd [A méretezési egységeket és a munkaterheléseket a Scale Unit Manager portálon keresztül kezelheti](./cloud-edge-landing-page.md#scale-unit-manager-portal).

[!INCLUDE [cloud-edge-privacy-notice](../../includes/cloud-edge-privacy-notice.md)]

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
