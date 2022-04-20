---
title: Peremhálózati skálázási egységek telepítése egyedi hardverre LBD segítségével
description: Ez a témakör bemutatja, hogy hogyan lehet a helyszíni peremhálózati egységeit a helyi üzleti adatokon (BELID) alapuló egyedi hardvereszközök és telepítések segítségével létesíteni.
author: cabeln
ms.date: 01/24/2022
ms.topic: article
ms.prod: dynamics-365
ms.service: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: cabeln
ms.search.validFrom: 2021-04-13
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 37bc8678d4e04afebbebaaa893a484866a8643ce
ms.sourcegitcommit: 23588e66e25c05e989f3212ac519d7016820430a
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/13/2022
ms.locfileid: "8565547"
---
# <a name="deploy-edge-scale-units-on-custom-hardware-using-lbd"></a>Peremhálózati skálázási egységek telepítése egyedi hardverre LBD segítségével

[!include [banner](../includes/banner.md)]

A peremhálózati egységek fontos szerepet töltenek be az ellátásilánc-kezelés elosztott topológiája területén. A hibrid topológiában eloszthatja a terhelést a Supply Chain Management felhőközpontja és a felhőben vagy a peremen lévő további skálaegységek között.

A peremhálózati egységek úgy telepíthetők, hogy létrehoznak egy helyi üzleti adatok (LBD) [helyi környezetet](../../fin-ops-core/dev-itpro/deployment/on-premises-deployment-landing-page.md), majd úgy konfigurálják, hogy skálázási egységként működjön a terjesztett hibrid topológiában a Supply Chain Managementhez. Ez úgy érhető el, hogy a helyi LBD-környezetet egy Supply Chain Management környezethez társítja a felhőben, amely a központként való működésre van konfigurálva.  

Ez a témakör azt írja le, hogyan lehet beállítani a helyi LBD-környezetet peremskálaegységként, majd társítani azt egy központhoz.

## <a name="infrastructure-considerations"></a>Infrastruktúra-szempontok

A peremhálózati egységek a létesítményben futnak, így az infrastruktúra-követelmények nagyon hasonlók. Vannak azonban olyan különbségek, amelyekre rá kell jegyezni:

- A peremhálózati egységek nem használják a Pénzügyi jelentéskészítést, így nincs szükségük pénzügyi jelentési csomópontokra.
- A gyártási és a tárolási terhelések nem számításigényesek, ezért fontolja meg az AOS-csomópontok számítási kapacitásának megfelelő méretezését.

## <a name="deployment-overview"></a>Telepítés áttekintése

Itt talál egy áttekintést a telepítési lépésekről.

1. **Engedélyezzen egy LBD-helyet az LBD-projektben a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásban.**

1. **Az LBD-környezet beállítása és telepítése *üres* adatbázissal.**

    Az LCS segítségével a legújabb topológiával és egy üres adatbázissal telepítheti az LBD-környezetet. A további tudnivalókat lásd a témakör későbbi [Az LBD-környezet beállítása és telepítése üres adatbázissal](#set-up-deploy) szakaszát. Az Ellátásilánc-kezelés 10.0.21-es vagy újabb verziója szükséges az összes központi és mérlegegység-környezetben.

1. **Célcsomagok feltöltése LBD-projekteszközökbe az LCS-ben.**

    A központban és a perem skálázási egységen használt alkalmazás-, platform- és testreszabási csomagok előkészítése. A további tudnivalókat lásd a témakör későbbi, [Célcsomagok feltöltése LBD-projekteszközökbe az LCS-ben](#upload-packages) című szakaszában.

1. **Az LBD-környezet kiszolgálása a célcsomagokkal.**

    Ezzel a lépéssel gondoskodik arról, hogy ugyanaz a build és testreszabások legyenek telepítve a központban és küllőben. A további tudnivalókat lásd a témakör későbbi, [Az LBD-környezet kiszolgálása a célcsomagokkal](#service-target-packages) részében.

1. **A skálázási egység konfigurációjának és a terhelés hozzárendelésének befejezése.**

    A további tudnivalókat lásd a témakör későbbi, [az LBD perem skálázási egység hozzárendelése központhoz](#assign-edge-to-hub) című témakörben.

A témakör hátralévő részei további részleteket tartalmaznak lépések elvégzéséről.

## <a name="set-up-and-deploy-an-lbd-environment-with-an-empty-database"></a><a name="set-up-deploy"></a>Az LBD-környezet beállítása és telepítése üres adatbázissal

Ez a lépés egy működő LBD-környezetet hoz létre. A környezet azonban nem feltétlenül ugyanazt az alkalmazás- és platformverziót használja, mint a központi környezet. Emellett még hiányoznak belőle a testreszabások, és még nincs engedélyezve a skálázási egységként való működéshez.

1. Kövesse a [Helyszíni környezetek beállítása és telepítése (Platformfrissítés 41-es és újabb verziókon)](../../fin-ops-core/dev-itpro/deployment/setup-deploy-on-premises-pu41.md) rész utasításait. Az Ellátásilánc-kezelés 10.0.21-es vagy újabb verziója szükséges az összes központi és mérlegegység-környezetben. Ezenkívül az infrastruktúra-parancsfájlok 2.12.0-s vagy újabb verzióját is használnia kell. 

    > [!IMPORTANT]
    > Olvassa el a szakasz további részét, **mielőtt** végrehajtaná annak a témakörnek a lépéseit.

1. Mielőtt leírná a konfigurációt az infrastruktúra\\ConfigTemplate.xml fájlban, futtassa a következő parancsfájlt:

    ```powershell
    .\Configure-ScriptsForEdgeScaleUnits.ps1 -ConfigurationFilePath .\ConfigTemplate.xml
    ```

    > [!NOTE]
    > Ez a parancsfájl eltávolít minden olyan konfigurációt, amely nem szükséges a peremhálózati skálázási egységek telepítéséhez.

1. Állítsa be az üres adatokat tartalmazó adatbázist az [Adatbázisok konfigurálása](../../fin-ops-core/dev-itpro/deployment/setup-deploy-on-premises-pu41.md#configuredb) résznek megfelelően. Használja az üres data.bak fájlt ehhez a lépéshez.
1. Miután befejezte az [Adatbázisok konfigurálása lépést](../../fin-ops-core/dev-itpro/deployment/setup-deploy-on-premises-pu41.md#configuredb), futtassa a következő parancsfájlt a Scale Unit Alm Orchestrator adatbázis konfigurálához.

    > [!NOTE]
    > Ne konfigurálja a pénzügyi jelentéskészítő adatbázist az [adatbázisok konfigurálása lépés](../../fin-ops-core/dev-itpro/deployment/setup-deploy-on-premises-pu41.md#configuredb) során.

    ```powershell
    .\Initialize-Database.ps1 -ConfigurationFilePath .\ConfigTemplate.xml -ComponentName EdgeScaleUnit
    ```

    Az Inicializálás-Database.ps1 parancsfájl a következő műveleteket végzi:

    1. Hozzon létre egy ScaleUnitAlmDb **nevű üres adatbázist**.
    2. A felhasználók leképezés az adatbázisszerepekre a következő táblázat alapján.

        | Felhasználó            | Típus | Adatbázis-szerepkör |
        |-----------------|------|---------------|
        | svc-LocalAgent$ | gMSA | dbowner\_     |

1. Kövesse a telepítőben található utasításokat, [és telepítse a helyi környezeteket (Platform update 41-es és újabb verzió)](../../fin-ops-core/dev-itpro/deployment/setup-deploy-on-premises-pu41.md).
1. Miután befejezte az [AD FS](../../fin-ops-core/dev-itpro/deployment/setup-deploy-on-premises-pu41.md#configuredb) konfigurálás lépését, hajtsa végre a következő lépéseket:

    1. Új Active Directory összevonási szolgáltatások (AD FS) alkalmazás létrehozása, amely lehetővé teszi, hogy az Alm Szolgáltatás szolgáltatás kommunikáljon az Application Object Server (AOS) kiszolgálóval.

        ```powershell
        # Host URL is your DNS record\host name for accessing the AOS
        .\Create-ADFSServerApplicationForEdgeScaleUnits.ps1 -ConfigurationFilePath .\ConfigTemplate.xml -HostUrl 'https://ax.d365ffo.onprem.contoso.com'
        ```

    1. Új (Azure Active Directory) alkalmazás Azure AD létrehozása, amely lehetővé teszi, hogy az Alm Szolgáltatás szolgáltatás kommunikáljon a skálaegység-kezelési szolgáltatással.

        ```powershell
        # Example .\Create-SumAADApplication.ps1 -ConfigurationFilePath ..\ConfigTemplate.xml -TenantId '6240a19e-86f1-41af-91ab-dbe29dbcfb95' -ApplicationDisplayName 'EdgeAgent-SUMCommunication-EN01'
        .\Create-SumAADApplication.ps1 -ConfigurationFilePath '<Path of the ConfigTemplate.xml file>' `
                                       -TenantId '<ID of the tenant where your cloud hub is deployed>' `
                                       -ApplicationDisplayName '<Whichever name you want the Azure AD app to have>'
        ```

1. Kövesse a telepítőben található utasításokat, [és telepítse a helyi környezeteket (Platform update 41-es és újabb verzió)](../../fin-ops-core/dev-itpro/deployment/setup-deploy-on-premises-pu41.md). Amikor meg kell adnia a helyi ügynök konfigurációját, ellenőrizze, hogy engedélyezi-e az peremhálózati egység funkcióit, és adja meg az összes szükséges paramétert.

    ![A peremhálózati egység funkcióinak engedélyezése.](media/EnableEdgeScaleUnitFeatures.png "A peremhálózati egység funkcióinak engedélyezése.")

1. A környezet LCS-ről való telepítése előtt állítsa be a telepítés előtti parancsfájlt. További információ: [Helyi ügynök telepítés előtti és telepítés utáni parancsfájljai](../../fin-ops-core/dev-itpro/lifecycle-services/pre-post-scripts.md).

    1. Másolja a Configure-CloudAndEdge.ps1 **parancsfájlt az Infrastruktúra** **parancsfájlok** ScaleUnit **mappájába** a környezetben beállított ügynökfájl-tárolási megosztás Parancsfájlok mappájába. A jellemző elérési út \\\\lbdiscsi01\\agent\\Scripts.
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
1. A környezet telepítése után hajtsa végre a következő lépéseket:

    1. Futtassa a következő SQL-parancsokat az üzleti adatbázison (AXDB).

        ```sql
        ALTER TABLE dbo.NUMBERSEQUENCETABLE ENABLE CHANGE_TRACKING WITH (TRACK_COLUMNS_UPDATED = ON)
        delete from NumberSequenceTable
        delete from NumberSequenceReference
        delete from NumberSequenceScope
        delete from FeatureManagementMetadata
        delete from FeatureManagementState
        delete from SysFeatureStateV0
        ```

    1. Az egyidejű maximális köteg munkamenetének növelése 4-nél nagyobb értékre.

        ```sql
        Update batchserverconfig set maxbatchsessions = '<Replace with number of concurrent batch tasks you want>'
        ```

    1. Győződjön meg róla, hogy engedélyezve van a változáskövetés az üzleti adatbázisban (AXDB).

        1. Nyissa meg az SQL Server Management Studio (SSMS) függvényt.
        1. Válassza ki és tartsa lenyomva az üzleti adatbázist (AXDB), majd válassza a Tulajdonságok **lehetőséget**.
        1. A megjelenő ablakban válassza a Változáskövetés lehetőséget, **majd** állítsa be a következő értékeket:

            - **Change Tracking:** *Igaz*
            - **Adatmegőrzési idő:** *7*
            - **Adatmegőrzés egysége:** *Nap*
            - **Automatikus tisztítás:** *Igaz*

    1. Adja hozzá a korábban létrehozott AD FS-alkalmazásazonosítót (a skálaegységben található Create-ADFSServerApplicationForEdgeScaleUnits.ps1 parancsfájl használatával).Azure AD Ezt a lépést kézzel lehet elvégezni a felhasználói felületen (ui). Másik lehetőségként az alábbi parancsfájl használatával az adatbázison keresztül is befejezheti a műveletet.

        ```sql
        DECLARE @ALMOrchestratorId NVARCHAR(76) = '<Replace with the ADFS Application ID created in a previous step>';

        IF NOT EXISTS (SELECT TOP 1 1 FROM SysAADClientTable WHERE AADClientId = @ALMOrchestratorId)
        BEGIN
            INSERT INTO SysAADClientTable (AADClientId, UserId, Name, ModifiedBy, CreatedBy)
            VALUES (@ALMOrchestratorId, 'ScaleUnitManagement', 'Scale Unit Management', 'Admin', 'Admin');
        END
        ```

## <a name="set-up-an-azure-key-vault-and-an-azure-ad-application-to-enable-communication-between-scale-units"></a><a name="set-up-keyvault"></a> Azure-kulcs és alkalmazás beállítása a Azure AD mérlegegységek közötti kommunikáció engedélyezéséhez

1. A környezet telepítése után hozzon létre egy további alkalmazást, amely lehetővé teszi a központ és a Azure AD mérlegegység közötti megbízható kommunikációt.

    ```powershell
    .\Create-SpokeToHubAADApplication.ps1 -ConfigurationFilePath '<Path of the ConfigTemplate.xml file>' `
                                          -TenantId '<ID of the tenant where your cloud hub is deployed>' `
                                          -ApplicationDisplayName '<Whichever name you want the Azure AD app to have>'
    ```

1. Miután létrehozott egy ügyfelet, létre kell hoznia egy ügyfél titkos adatait, és az adatokat egy Azure-kulcshoz kell mentenie. Ezenkívül hozzáférést kell Azure AD biztosítanának a létrehozott pályázathoz is, hogy beolvassa a kulcsban tárolt adatokat. A következő parancsfájl automatikusan végrehajtja a szükséges műveleteket a kényelmet szolgálja.

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
    > Ha nincs olyan kulcskulcs, **amelynél a KeyVaultName** érték létezik, a parancsprogram automatikusan létrehoz egyet.

1. Adja hozzá Azure AD a most létrehozott alkalmazásazonosítót (a hubban található alkalmazástáblában a Create-AhubAADApplication.ps1 Azure AD parancsfájl használata esetén). Ezt a lépést manuálisan a felhasználói felületen is végre lehet végezni.

## <a name="upload-target-packages-into-lbd-project-assets-in-lcs"></a><a name="upload-packages"></a>Célcsomagok feltöltése LBD-projekteszközökbe az LCS-ben

Ez a lépés készíti elő az alkalmazás verzióját, a platformverziót és a testreszabásokat, amelyek át fognak kerülni az LBD skálaegység-környezetbe.

1. Töltse fel ugyanazt kombinált alkalmazás-/platformcsomagok amely alkalmazva lett a központi környezetben az LCS helyi projekt eszközkönyvtárába.
1. Kérje le egy másolatát az egyéni telepíthető csomagnak amely alkalmazva lett a központi környezetben, és töltse fel az LCS helyi projekt eszközkönyvtárába.

## <a name="service-the-lbd-environment-with-target-packages"></a><a name="service-target-packages"></a>Az LBD-környezet kiszolgálása a célcsomagokkal

Ez a lépés illeszti alkalmazás verzióját, a platformverziót és a testreszabásokat az LBD skálázási egység környezetben a központtal.

1. Szolgálja ki az LBD-környezetet az előző lépésben feltöltött, kombinált alkalmazás-/platformcsomaggal.
1. Szolgálja ki az LBD-környezetet az előző lépésben feltöltött egyéni telepíthető csomaggal.

    ![Frissítések alkalmazása az LCS-szolgáltatásban](media/cloud_edge-LBD-LCS-ServiceLBDEnv1.png "Frissítések alkalmazása az LCS-szolgáltatásban")

    ![A testreszabási csomag kiválasztása.](media/cloud_edge-LBD-LCS-ServiceLBDEnv2.png "A testreszabási csomag kiválasztása")

## <a name="assign-your-lbd-edge-scale-unit-to-a-hub"></a><a name="assign-edge-to-hub"></a>Az LBD peremhálózati skálaegység hozzárendelése egy központhoz

A peremskála egységét a Skálaegység-kezelő portálon konfigurálhatja és kezelheti. A további tudnivalókat lásd [a Mérlegegység-kezelő portál segítségével a mérlegegységek és terhelések kezelése.](./cloud-edge-landing-page.md#scale-unit-manager-portal)

[!INCLUDE [cloud-edge-privacy-notice](../../includes/cloud-edge-privacy-notice.md)]

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
