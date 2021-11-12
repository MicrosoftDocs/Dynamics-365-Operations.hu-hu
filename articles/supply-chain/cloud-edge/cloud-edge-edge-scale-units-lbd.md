---
title: Peremhálózati skálázási egységek telepítése egyedi hardverre LBD segítségével (előzetes verzió)
description: Ez a témakör bemutatja, hogy hogyan lehet a helyszíni peremhálózati egységeit a helyi üzleti adatokon (BELID) alapuló egyedi hardvereszközök és telepítések segítségével létesíteni.
author: cabeln
ms.date: 04/22/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: cabeln
ms.search.validFrom: 2021-04-13
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 0ebbdaab9d6f040497d3158db2712e102b6e9aa8
ms.sourcegitcommit: 1e5a46271bf7fae2f958d2b1b666a8d2583e04a8
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/25/2021
ms.locfileid: "7678981"
---
# <a name="deploy-edge-scale-units-on-custom-hardware-using-lbd-preview"></a>Peremhálózati skálázási egységek telepítése egyedi hardverre LBD segítségével (előzetes verzió)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)] <!--KFM: Until 11/1/2021 -->

A peremhálózati egységek fontos szerepet töltenek be az ellátásilánc-kezelés elosztott topológiája területén. A hibrid topológiában eloszthatja a terhelést a Supply Chain Management felhőközpontja és a felhőben vagy a peremen lévő további skálaegységek között.

A peremhálózati egységek úgy telepíthetők, hogy létrehoznak egy helyi üzleti adatok (LBD) [helyi környezetet](../../fin-ops-core/dev-itpro/deployment/on-premises-deployment-landing-page.md), majd úgy konfigurálják, hogy skálázási egységként működjön a terjesztett hibrid topológiában a Supply Chain Managementhez. Ez úgy érhető el, hogy a helyi LBD-környezetet egy Supply Chain Management környezethez társítja a felhőben, amely a központként való működésre van konfigurálva.  

A peremskálaegységek jelenleg előzetes verziójú. Ebből következően csak az [előzetes verzió feltételeinek](https://aka.ms/scmcnepreviewterms) megfelelően használhat ilyen típusú környezetet.

Ez a témakör azt írja le, hogyan lehet beállítani a helyi LBD-környezetet peremskálaegységként, majd társítani azt egy központhoz.

## <a name="deployment-overview"></a>Telepítés áttekintése

Itt talál egy áttekintést a telepítési lépésekről.

1. **Engedélyezzen egy LBD-helyet az LBD-projektben a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásban.**

    Az előzetes verzió során az LBD-peremskálaegység a meglévő LBD-vevőket célozza. Csak bizonyos vevői helyzetekben áll rendelkezésre egy további 60 napos korlátozott LBD tesztkörnyezeti hely.

1. **Az LBD-környezet beállítása és telepítése *üres* adatbázissal.**

    Az LCS segítségével a legújabb topológiával és egy üres adatbázissal telepítheti az LBD-környezetet. A további tudnivalókat lásd a témakör későbbi [Az LBD-környezet beállítása és telepítése üres adatbázissal](#set-up-deploy) szakaszát. A Supply Chain Management 10.0.19-es verzióját kell használnia a 43-as vagy újabb platformfrissítéssel a központ és a sakálázási egység környezetek között.

1. **Célcsomagok feltöltése LBD-projekteszközökbe az LCS-ben.**

    A központban és a perem skálázási egységen használt alkalmazás-, platform- és testreszabási csomagok előkészítése. A további tudnivalókat lásd a témakör későbbi, [Célcsomagok feltöltése LBD-projekteszközökbe az LCS-ben](#upload-packages) című szakaszában.

1. **Az LBD-környezet kiszolgálása a célcsomagokkal.**

    Ezzel a lépéssel gondoskodik arról, hogy ugyanaz a build és testreszabások legyenek telepítve a központban és küllőben. A további tudnivalókat lásd a témakör későbbi, [Az LBD-környezet kiszolgálása a célcsomagokkal](#service-target-packages) részében.

1. **A skálázási egység konfigurációjának és a terhelés hozzárendelésének befejezése.**

    A további tudnivalókat lásd a témakör későbbi, [az LBD perem skálázási egység hozzárendelése központhoz](#assign-edge-to-hub) című témakörben.

A témakör hátralévő részei további részleteket tartalmaznak lépések elvégzéséről.

## <a name="set-up-and-deploy-an-lbd-environment-with-an-empty-database"></a><a name="set-up-deploy"></a>Az LBD-környezet beállítása és telepítése üres adatbázissal

Ez a lépés egy működő LBD-környezetet hoz létre. A környezet azonban nem feltétlenül ugyanazt az alkalmazás- és platformverziót használja, mint a központi környezet. Emellett még hiányoznak belőle a testreszabások, és még nincs engedélyezve a skálázási egységként való működéshez.

1. Kövesse a [Helyszíni környezetek beállítása és telepítése (Platformfrissítés 41-es és újabb verziókon)](../../fin-ops-core/dev-itpro/deployment/setup-deploy-on-premises-pu41.md) rész utasításait. A Supply Chain Management 10.0.19-es verzióját kell használnia a 43-as vagy újabb platformfrissítéssel a központ és a sakálázási egység környezetek között

    > [!IMPORTANT]
    > Olvassa el a szakasz további részét, **mielőtt** végrehajtaná annak a témakörnek a lépéseit.

1. Mielőtt leírná a konfigurációt az infrastruktúra\\ConfigTemplate.xml fájlban, futtassa a következő parancsfájlt:

    ```powershell
    .\Configure-ScriptsForEdgeScaleUnits.ps1 -ConfigurationFilePath .\ConfigTemplate.xml
    ```

    > [!NOTE]
    > Ez a parancsfájl eltávolít minden olyan konfigurációt, amely nem szükséges a peremhálózati skálázási egységek telepítéséhez.

1. Állítsa be az üres adatokat tartalmazó adatbázist az [Adatbázisok konfigurálása](../../fin-ops-core/dev-itpro/deployment/setup-deploy-on-premises-pu41.md#configuredb) résznek megfelelően. Használja az üres data.bak fájlt ehhez a lépéshez.
1. Állítsa be a telepítés előtti parancsfájlt. További információ: [Helyi ügynök telepítés előtti és telepítés utáni parancsfájljai](../../fin-ops-core/dev-itpro/lifecycle-services/pre-post-scripts.md).

    1. Az **Infrastruktúra-parancsfájlok** **ScaleUnit** mappájában található tartalmat másolja a környezetben beállított ügynökfájl-tárolási megosztás **Scripts** mappájába. A jellemző elérési út \\\\lbdiscsi01\\agent\\Scripts.
    2. Hozza létre a **PreDeployment.ps1** parancsfájlt, amely a szükséges paraméterekkel meghívja a parancsfájlokat. A telepítés előtti parancsfájlt az ügynök fájlmegosztásán található **Parancsfájlok** mappába kell tenni. Ellenkező esetben nem futtatható. Egy jellemző elérési út: \\\\lbdiscsi01\\agent\\Scripts\\PreDeployment.ps1.

        Az PreDeployment.ps1 parancsfájl tartalma hasonlít a következő példához.

        ```powershell
        $agentShare = '\\lbdiscsi01\agent'
        
        Write-Output "AgentShare is set to $agentShare" 
        & $agentShare\Scripts\Configure-CloudandEdge.ps1 -AgentShare $agentShare -InstanceId '@A' -DatabaseServer 'lbdsqla01.contoso.com' -DatabaseName 'AXDB'
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

## <a name="upload-target-packages-into-lbd-project-assets-in-lcs"></a><a name="upload-packages"></a>Célcsomagok feltöltése LBD-projekteszközökbe az LCS-ben

Ez a lépés készíti elő az alkalmazás verzióját, a platformverziót és a testreszabásokat, amelyek át fognak kerülni az LBD skálaegység-környezetbe.

1. Töltse fel ugyanazt kombinált alkalmazás-/platformcsomagok amely alkalmazva lett a központi környezetben az LCS helyi projekt eszközkönyvtárába.
1. Kérje le egy másolatát az egyéni telepíthető csomagnak amely alkalmazva lett a központi környezetben, és töltse fel az LCS helyi projekt eszközkönyvtárába.

## <a name="service-the-lbd-environment-with-target-packages"></a><a name="service-target-packages"></a>Az LBD-környezet kiszolgálása a célcsomagokkal

Ez a lépés illeszti alkalmazás verzióját, a platformverziót és a testreszabásokat az LBD skálázási egység környezetben a központtal.

1. Szolgálja ki az LBD-környezetet az előző lépésben feltöltött, kombinált alkalmazás-/platformcsomaggal.
1. Szolgálja ki az LBD-környezetet az előző lépésben feltöltött egyéni telepíthető csomaggal.

    ![A Karbantartás > Frissítések alkalmazása az LCS-ben kiválasztása.](media/cloud_edge-LBD-LCS-ServiceLBDEnv1.png "A Karbantartás > Frissítések alkalmazása az LCS-ben kiválasztása")

    ![A testreszabási csomag kiválasztása.](media/cloud_edge-LBD-LCS-ServiceLBDEnv2.png "A testreszabási csomag kiválasztása")

## <a name="assign-your-lbd-edge-scale-unit-to-a-hub"></a><a name="assign-edge-to-hub"></a>Az LBD peremhálózati skálaegység hozzárendelése egy központhoz

Amíg a peremhálózati skálaegységek még előzetes verzióban vannak, a [skálázási egység telepítési és konfigurációs eszközeit](https://github.com/microsoft/SCMScaleUnitDevTools) kell használnia, amelyek a GitHubban érhetők, hogy hozzárendelje az LBD peremhálózati skálaegységet egy központhoz. A folyamat lehetővé teszi az LBD-konfiguráció számára a peremhálózati skálaegységként való működést, és társítja a központhoz. A folyamat hasonló egy különálló fejlesztői környezet beállításához.

1. Töltse le az [SCMScaleUnitDevTools](https://github.com/microsoft/SCMScaleUnitDevTools/releases) legújabb kiadását, és bontsa ki a fájl tartalmát.
1. Készítsen másolatot a `UserConfig.sample.xml` fájlról, és nevezze el `UserConfig.xml` néven.
1. Hozzon létre egy Microsoft Azure Active Directory (Azure AD) alkalmazást az Azure AD bérlőjében a [Telepítési útmutató skálázási egységekhez és munkaterhelésekhez](https://github.com/microsoft/SCMScaleUnitDevTools/wiki/Step-by-step-usage-guide#aad-application-registrations) részben leírtak szerint.
    1. Létrehozás után lépjen a Azure AD alkalmazások űrlapjára (SysAADClientTable) a központjában.
    1. Hozzon létre egy új bejegyzést, és állítsa be az **Ügyfélazonosítót** a létrehozott alkalmazás azonosítójára. A **Név** elemet állítsa be *ScaleUnits* értékre a **Felhasználói azonosítót** pedig *Rendszergazda* értékre.

1. Hozzon létre egy Active Directory Federation Service (AD FS) alkalmazást a [Telepítési útmutató skálázási egységekhez és munkaterhelésekhez](https://github.com/microsoft/SCMScaleUnitDevTools/wiki/Step-by-step-usage-guide#adfs-application-registrations) részben leírtak szerint.
    1. Létrehozás után lépjen a Azure AD alkalmazások űrlapjára (SysAADClientTable) a peremhálózati skálaegységben.
    1. Hozzon létre egy új bejegyzést, és állítsa be az **Ügyfélazonosítót** a létrehozott alkalmazás azonosítójára. A **Felhasználói azonosító** állítsa *Rendszergazda* értékre.

1. Módosítsa a `UserConfig.xml` fájlt.
    1. A `InterAOSAADConfiguration` szakasz alatt adja meg a korábban létrehozott Azure AD alkalmazás adatait.
        - Az `AppId` elembe írja be az Azure-alkalmazás alkalmazásazonosítóját.
        - Az `AppSecret` elembe írja be az Azure-alkalmazás titkos kódját.
        - Az `Authority` elemnek tartalmaznia kell a bérlő biztonsági hitelesítésszolgáltatóra mutató URL-címet.

        ```xml
        <InterAOSAADConfiguration>
            <AppId>8dab14f6-97b1-48e3-b51b-350b45f6ede5</AppId>
            <AppSecret>k6em-_7.lopty56TGUedDTVhtER-j_6anY1</AppSecret>
            <Authority>https://login.windows.net/contoso.onmicrosoft.com</Authority>
        </InterAOSAADConfiguration>
        ```

    1. A `ScaleUnitConfiguration` szakaszban az első `ScaleUnitInstance` elemhez módosítsa az `AuthConfiguration` szakaszt.
        - Az `AppId` elembe írja be az Azure-alkalmazás alkalmazásazonosítóját.
        - Az `AppSecret` elembe írja be az Azure-alkalmazás titkos kódját.
        - Az `Authority` elemnek tartalmaznia kell a bérlő biztonsági hitelesítésszolgáltatóra mutató URL-címet.

        ```xml
        <AuthConfiguration>
            <AppId>8dab14f6-97b1-48e3-b51b-350b45f6ede5</AppId>
            <AppSecret>k6em-_7.lopdz.6d3DTVOtf9Lo-j_6anY1</AppSecret>
            <Authority>https://login.windows.net/contoso.onmicrosoft.com</Authority>
        </AuthConfiguration>
        ```

    1. Mindemellett ugyanehhez a `ScaleUnitInstance` elemhez állítsa be a következő értékeket:
        - Az `Domain` elemben adja meg a központ URL-címét. Például: `https://cloudhub.sandbox.operations.dynamics.com/`
        - Győződjön meg róla, hogy az `EnvironmentType` elemben be van állítva az `LCSHosted` érték.

    1. A `ScaleUnitConfiguration` szakaszban a második `ScaleUnitInstance` elemhez módosítsa az `AuthConfiguration` szakaszt.
        - Az `AppId` elembe írja be az AD-FS alkalmazás alkalmazásazonosítóját.
        - Az `AppSecret` elembe írja be az ADFS alkalmazás titkos kódját.
        - Az `Authority` elemnek tartalmaznia kell az AD FS-példány URL-címét.

        ```xml
        <AuthConfiguration>
            <AppId>26b16f25-21d8-4d36-987b-62df292895aa</AppId>
            <AppSecret>iZFfObgI6lLtY9kEbBjEFV98NqI5_YZ0e5SBcWER</AppSecret>
            <Authority>https://adfs.contoso.com/adfs</Authority>
        </AuthConfiguration>
        ```

    1. Mindemellett ugyanehhez a `ScaleUnitInstance` elemhez állítsa be a következő értékeket:
        - Az `Domain` elemben adja meg a peremhálózati skálaegység URL-címét. Például: https://ax.contoso.com/
        - Győződjön meg róla, hogy az `EnvironmentType` elemben be van állítva az LBD érték.
        - A `ScaleUnitId` elemben adja meg ugyanazt az értéket, mint amit a telepítés előtti `Configure-CloudandEdge.ps1` parancsfájl konfigurálásakor megadott az `InstanceId` elemhez.

        > [!NOTE]
        > Ha nem az alapértelmezett azonosítót (@A) használja, frissítse a ScaleUnitId azonosítót minden ConfiguredWorkload értékhez a Terhelések szakaszban.

1. Nyissa meg a PowerShell-t, és navigáljon a `UserConfig.xml` fájlt tartalmazó mappához.

1. Futtassa az eszközt ezzel a paranccsal.

    ```powershell
    .\CLI.exe
    ```

    > [!NOTE]
    > Minden művelet után újra el kell indítania az eszközt.

1. Az eszközben válassza a **2. Környezetek előkészítése a számítási feladat telepítéséhez** lépést. Majd futtassa az alábbi lépéseket:
    1. Válassza az **1. A központ előkészítése** lépést.
    1. Válassza a **2. A skálázási egység előkészítése** lépést.

    > [!NOTE]
    > Ha nem tiszta telepítésből futtatja ezt a parancsot, és sikertelen, tegye a következőt:
    >
    > - Az összes mappa eltávolítása az `aos-storage` mappából (a `GACAssemblies` kivételével).
    > - Futtassa a következő SQL parancsot az üzleti adatbázison (AXDB):
    >
    > ```sql 
    > delete from storagefoler
    > ```

1. Futtassa a következő SQL parancsokat az üzleti adatbázison (AXDB):

    ```sql
    delete from FEATUREMANAGEMENTMETADATA
    delete from FEATUREMANAGEMENTSTATE
    delete from NUMBERSEQUENCESCOPE
    ```

1. Ellenőrizze, hogy engedélyezve van-e a változáskövetés az üzleti adatbázisban (AXDB)
    1. Indítsa el az SQL Server Management Studio (SSMS) alkalmazást.
    1. Kattintson a jobb gombbal az üzleti adatbázisra (AXDB), és válassza ki a tulajdonságokat.
    1. A megnyíló ablakban válassza a **Change Tracking** lehetőséget, és adja meg a következő beállításokat:

        - **Change Tracking:** *Igaz*
        - **Adatmegőrzési idő:** *7*
        - **Adatmegőrzés egysége:** *Nap*
        - **Automatikus tisztítás:** *Igaz*

1. Az eszközben válassza a **3. Terhelések telepítése** lépést. Majd futtassa az alábbi lépéseket:
    1. Válassza az **1. Telepítés a Központra** lépést.
    1. Válassza a **2. telepíts a skálaegységre** lépést.

[!INCLUDE [cloud-edge-privacy-notice](../../includes/cloud-edge-privacy-notice.md)]

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
