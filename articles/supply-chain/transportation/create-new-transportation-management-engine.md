---
title: Új szállításkezelő motor létrehozása
description: Ez a témakör azt ismerteti, hogyan lehet új szállításkezelő motort létrehozni a Dynamics 365 Supply Chain Management.
author: Weijiesa
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TMSGenericEngine, TMSRateEngine, TMSMileageEngine, TMSEngineParameters
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.custom: 51661
ms.assetid: 0473acef-755e-4b42-acf5-5e5aa902dc0e
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 627972ef6afb7551bb57821ded24183f8f335e9b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8857257"
---
# <a name="create-a-new-transportation-management-engine"></a>Új szállításkezelő motor létrehozása

[!include [banner](../includes/banner.md)]

Ez a témakör azt ismerteti, hogyan lehet új szállításkezelő motort létrehozni a Dynamics 365 Supply Chain Management. 

A szállításkezelő motorok (TMS) határozzák meg azt a logikát, amit a Szállításkezelő a szállítási díjak előállítására és feldolgozására használ. A Supply Chain Management számos különböző típusú motort kínál, amelyek különböző paramétereket számítnak ki, például a díjakat, a szállítási időket, valamint a szállítás közben keresztezett zónák számát. Ez a cikk bemutatja, hogy hogyan használható a Microsoft Visual Studio fejlesztői környezete a Supply Chain Management fejlesztési eszközeivel együtt egy új TMS-motor létrehozásához és telepítéséhez, majd a motornak az Műveletekben való beállításához. A motorokkal kapcsolatos további tudnivalókat lásd: [Szállításkezelő motorok](transportation-management-engines.md).

## <a name="create-a-new-tms-engine"></a>Új TMS-motor létrehozása

Ez a szakasz bemutatja hogyan lehet TMS-motor implementációval rendelkező osztálykönyvtárat létrehozni, és hogyan lehet arra hivatkozni a Supply Chain Management modellből.

1. Az új motor telepítéséhez olyan modellel kell rendelkeznie, amely tartalmazza a motorokat. A **Dynamics 365** &gt; **Modellkezelés** menüben kattintson a **Modell létrehozása** gombra új modell létrehozásához. A **Modell létrehozása** varázsló első oldalán nevezze el a **TMSEngines** néven a modellt. 

   [![Modell létrehozása.](./media/012.png)](./media/012.png)

2. A következő lapon válassza az **Új csomag létrehozása** lehetőséget. 

   [![Új sablon létrehozása.](./media/021.png)](./media/021.png)

3. A következő lapon válassza ki a hivatkozni kívánt **ApplicationSuite** modellt. (Az **ApplicationPlatform** modell előre ki van választva.) 

   [![Válassza ki a hivatkozni kívánt modellt.](./media/032.png)](./media/032.png)

4. A következő oldalon kattintson a **Befejezés** gombra az új modell létrehozásának megerősítéséhez. 

   [![A modelllétrehozás befejezése.](./media/042.png)](./media/042.png)

5. Egy új megoldásban hozzon létre egy új Supply Chain Management projektet, és nevezze el **TMSThirdParty** néven. A projekttulajdonságok között állítsa a projektmodellt **TMSEngines** típusra.
6. Adjon hozzá egy új C\# osztálykönyvtárat a megoldáshoz, és nevezze el **ThirdPartyTMSEngines** néven.
7. A ThirdPartyTMSEngine projektben adjon hozzá hivatkozásokat az Supply Chain Management-specifikus szerelvényekhez:
   -   Alkalmazásszerelvényke, amelyek lehetővé teszik X++ típusok hivatkozását. Ezek a szerelvények a következő helyeken találhatók. A \[Csomagok gyökere\] annak a helynek az elérési útja, ahová az összes telepített szerelvényt elhelyezi, például: C:\\Csomagok.

        ```xpp
        [Packages root]\ApplicationPlatform\bin\Dynamics.AX.ApplicationPlatform.dll
        [Packages root]\ApplicationFoundation\bin\Dynamics.AX.ApplicationFoundation.dll
        [Packages root]\ApplicationSuite\bin\Dynamics.AX.ApplicationSuite.dll
        ```
        
   -   Az adatokhoz, a LINQ-hoz és a kiegészítő funkciókhoz való hozzáférést engedélyező keretrendszer-szerelvények. Ezek a szerelvények a \[Csomagok gyökér\]\\bin helyen találhatók.

        ```xpp 
        Microsoft.Dynamics.ApplicationPlatform.Environment.dll
        Microsoft.Dynamics.AX.Data.Core.dll
        Microsoft.Dynamics.AX.Framework.Linq.Data.AdoNet.dll
        Microsoft.Dynamics.AX.Framework.Linq.Data.dll
        Microsoft.Dynamics.AX.Framework.Linq.Data.Interface.dll
        Microsoft.Dynamics.AX.Framework.Linq.Data.Msil.dll
        Microsoft.Dynamics.AX.Server.Core.dll
        Microsoft.Dynamics.AX.Xpp.AxShared.dll
        Microsoft.Dynamics.AX.Xpp.Support.dll
        ```

   -   A motorokat tartalmazó alap TMS-szerelvény (amely motorokat tartalmaz) és a TMS-alapszerelvény (amely segítőket, konstansokat, adatátviteli osztálydefiníciókat stb. tartalmaz). Ezek a szerelvények a következő helyeken találhatók.

        ```xpp
        [Packages root]\ApplicationSuite\bin\Microsoft.Dynamics.AX.Tms.dll
        [Packages root]\ApplicationSuite\bin\Microsoft.Dynamics.AX.Tms.Base.dll
        ```
8. Nevezze át a ThirdPartyTMSEngine projektben automatikusan generált C\# osztályt **SampleRatingEngine** névre.
9. Implementálja a motort. Mivel ebben a példában díjazási motort hoz létre, a díjazási motorok alaposztályából örököljük. Az alaposztály implementálja a díjazási motor legtöbb felületét (**TMSFwkIRateEngine**). Csak meg kell valósítanunk a díjazás módszert. Hogy a példa egyszerű maradjon ezzel a módszerrel 100 értékű kódolt díjat regisztrálunk. Bármely motorfelületet megvalósító motort létre lehet hozni, például **TMSFwkIAccessorialEngine**. A motor minden interfészét X++-ban kell definiálni.

    ```xpp
    namespace ThirdPartyTMSEngines
    {
        using Dynamics.AX.Application;
        using Microsoft.Dynamics.Ax.Tms.Base.Data;
        using Microsoft.Dynamics.Ax.Tms.Base.Utility;
        using Microsoft.Dynamics.Ax.Tms.Bll;
        using System.Xml.Linq;
        public class SampleRatingEngine : BaseRateEngine
        {
            public override RatingDto rate(TmsTransactionFacade transactionFacade, XElement shipment, TMSRateMasterCode rateMasterCode)
            {
               XElement re = shipment.RetrieveOrCreateRatingEntity(this.RatingDto);
               re.AddRate(TmsRateType.Rate, 100);
               return this.RatingDto;
            }
        }
    }
    ```

10. A megoldás összeállítása.
11. Új hivatkozás hozzáadása a TMSThirdParty projekthez. A hivatkozásnak a ThirdPartyTMSEngine projektre kell mutatnia. Ha végzett, a megoldásnak így kellene kinézni. 

    [![A megoldás, amely hivatkozást tartalmaz a TMSThirdParty projektre.](./media/052.png)](./media/052.png)

12. A megoldás összeállítása. Győződjön meg róla, hogy az új könyvtár megjelenik az Alkalmazástallózó **Hivatkozások** csomópontjában. 

    [![Az Alkalmazástallózó Hivatkozások csomópontjának új könyvtára.](./media/061.png)](./media/061.png)

## <a name="deploy-the-tms-engine-as-a-package"></a>A TMS-motort telepítse csomagként

A harmadik féltől származó TMS-motorokat például egy telepítési csomag segítségével lehet telepíteni. Ezt a megközelítést ajánlott éles környezetben alkalmazni. Fejlesztői környezetben manuálisan másolhatja a szerelvényeket a következő "TMS-motor beállítása a Supply Chain Management alkalmazásban" című részében leírtak szerint. A motor telepítéséhez csomagként kövesse az alábbi lépéseket.

1. A **Dynamics 365** &gt; **Telepítés** menüben kattintson a <strong>Telepítési csomag létrehozása</strong> elemre.
2. A **Telepítési csomag létrehozása** párbeszédpanelen válassza ki a TMSEngines modellt, és adja meg a csomagfájlok tárolására szolgáló elérési utat. 

   [![A TMSEngines modell kiválasztása.](./media/071.png)](./media/071.png)

3. A csomagot most a célkörnyezetbe telepítheti. Az oktatóanyag a [Telepíthető csomag telepítése](../../fin-ops-core/dev-itpro/deployment/install-deployable-package.md) útmutatóban olvasható.

## <a name="set-up-the-tms-engine-in-supply-chain-management"></a>A TMS motor beállítása a Supply Chain Management szolgáltatásban

Ez a szakasz bemutatja, hogy hogyan lehet beállítani a Supply Chain Management alkalmazást egy TMS-motor használatára, és bemutatja, hogy az általunk létrehozott új motort hogyan használja fel a rendszer a díjkiválasztáshoz. A szakaszban található példa az USMF bemutatóadat-céget használja.

1. Hozzon létre egy új motort az "Új TMS-motor létrehozása" szakaszban leírtak szerint.
2. Állítsa össze a megoldást.
3. A kapott szerelvényt másolja a Supply Chain Management kiszolgáló bináris helyére, az \[AOSWebRoot\]bin helyre. **Megjegyzés:** Ennek a lépésnek csak fejlesztési környezetben van jelentősége. Éles környezetben egy telepítési csomagon keresztül telepítsen. Az útmutatás a következő "A TMS-motor telepítése csomagként" szakaszban található.
4. Hozzon létre egy új minősítési motort a Supply Chain Management alkalmazásban a **Díjkiválasztási motorok** lapon. A motornak arra a motorszerelvényre kell mutatnia, amely a motorosztálykönyvtár és a megvalósított motorosztály kiépítése során jön létre. 

   [![Új minősítési motor létrehozása a Minősítési motorok oldalon.](./media/081.png)](./media/081.png)

5. Hozzon létre egy szállítmányozót, amely a Minta minősítési motort használja. Mivel a motor nem használ adatokat, nem kell díjtörzset hozzárendelni. 

   [![Új szállítmányozó létrehozása.](./media/092.png)](./media/092.png)

6. Az **Útvonal-díj munkaterület** oldalon kattintson a **Díjközpont** lehetőségre. A SampleCarrier 100,00 díja jelenik meg, ahogy a következő képernyőfelvétel mutatja. Ebben a példában a 24-es raktártól az US-004 vevőig vásárlunk útdíjat. A díj azonban mindig 100,00 lesz, hiszen az kódolva van.

   [![Útvonal–díj munkaterület.](./media/101.png)](./media/101.png)

## <a name="tips-and-tricks"></a>Tippek és trükkök

- Ha fejlesztői eszközöket használ a Supply Chain Management alkalmazáshoz, hasznos lehet egy új projektet hozzáadni a megoldáshoz. Ha beállítja ezt a projektet indítási projektként, és elindít egy hibakeresési munkamenetet, ugyanabban a hibakeresési munkamenetben az X++ és a C\# kódban is hibakeresést lehet végezni.
- A ThirdPartyTMSEngines projekt módosítása és újrafordítása esetén a kapott szerelvényt minden alkalommal manuálisan kell átmásolnia a bináris helyre, vagy egy telepítési csomagon keresztül kell telepítenie. Ellenkező esetben elavult szerelvény használatával futtat esetleg.
- Miután végrehajtja a TMS-specifikus műveleteket a Supply Chain Management alkalmazásban, az Internet Information Services (IIS) dolgozói folyamata zárolhatja a ThirdPartyTMSEngines szerelvényt, hogy a szerelvényt ne lehessen frissíteni. Ebben az esetben indítsa újra a w3svc folyamatot.

### <a name="whitepaper"></a>Tanulmány

További tudnivalókért töltse le a következő (az AX 2012 támogatásához készült, de még a Dynamics 365 Supply Chain Management esetében is érvényes) tanulmányt

- [Szállításkezelő motorok megvalósítása és telepítése](https://download.microsoft.com/download/b/5/f/b5ff8fef-3918-4c1d-92d5-b67eb0971684/ImplementingAndDeployingTransportationManagementEnginesInAX.pdf)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]