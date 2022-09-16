---
title: Telepítési irányelvek a pénzügyi nyomtató integrációs mintához Lengyelországhoz (legacy)
description: Ez a cikk a Microsoft Dynamics 365 Commerce pénzügyi nyomtató integrációs mintáinak a Kiskereskedelmi szoftverfejlesztői csomagból (SDK) való telepítésével kapcsolatos irányelveket tartalmaz.
author: EvgenyPopovMBS
ms.date: 08/18/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-03-01
ms.openlocfilehash: b19c8d7a80ac772ae238191d1285a1ad80e6f611
ms.sourcegitcommit: b1df4db7facb5e7094138836c41a65c4a158f01d
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/13/2022
ms.locfileid: "9473958"
---
# <a name="deployment-guidelines-for-the-fiscal-printer-integration-sample-for-poland-legacy"></a>Telepítési irányelvek a pénzügyi nyomtató integrációs mintához Lengyelországhoz (legacy)

[!include [banner](../includes/banner.md)]

> [!IMPORTANT]
> Csak akkor kövesse az ebben Microsoft Dynamics 365 Commerce a cikkben olvasható irányelveket, ha a 10.0.28-as vagy korábbi verziókat használja. A Commerce rendszer 10.0.29-es verziója szerint a lengyelországi pénzügyi nyomtató-integrációs minta elérhető a Commerce szoftverfejlesztői csomagjában (SDK). A további tudnivalókat lásd: Csatornaösszetevők [konfigurálása](./emea-pol-fpi-sample.md#configure-channel-components).

Ez a témakör a Dynamics 365 Commerce pénzügyi nyomtató integrációs mintáinak telepítésével kapcsolatban tartalmaz tájékoztatást, amelyek a Retail SDK készletből, a Lifecycle Services (LCS) egy fejlesztői virtuális gépére (VM) Microsoft Dynamics telepíthetők. A pénzügyi integrációs mintával kapcsolatos további tudnivalókat lásd [a Pénzügyi nyomtató integrációs mintája Lengyelország esetében](emea-pol-fpi-sample.md). 

A Lengyelországhoz készült pénzügyi integrációs minta a Retail SDK része. Az SDK [telepítésével és használatával kapcsolatos tudnivalókat lásd a Retail szoftverfejlesztői csomag (SDK) architektúráját](../dev-itpro/retail-sdk/retail-sdk-overview.md). Ez a minta a Commerce runtime (CRT) és a hardverállomás bővítményeiből áll. A minta futtatásához módosítania és fel kell építenie a és CRT a hardverállomás-projekteket. Javasoljuk, hogy egy nem módosított Retail SDK készlet használhatja az ebben a cikkben leírt módosításokat. Javasoljuk továbbá, hogy forrásvezérlő rendszert használjon, Azure DevOps például olyanokat, ahol a fájlok még nem módosultak.

## <a name="development-environment"></a>Fejlesztői környezet

A következő lépések szerint állíthatja be a fejlesztői környezetet, hogy tesztelni és ki tudja terjeszteni a mintát.

### <a name="commerce-runtime-extension-components"></a>Commerce runtime kiterjesztésű összetevők

A CRT bővítmények összetevői a Retail SDK szoftverfejlesztő készletében találhatók. A következő eljárások befejezéséhez nyissa **meg a CommerceRuntimeSamples.sln** megoldást a **RetailSdk\\ SampleExtensions\\ CommerceRuntime alatt**.

1. A Runtime.Extensions.DocumentProvider.PosnetSample **projekt** megkeresása és összeállítása.
2. Az Extensions.DocumentProvider.PosnetSample **bin\\ hibakeresési\\** mappában keresse meg a Contoso.Commerce.Runtime.Extensions.DocumentProvider.PosnetSample.dll **szerelvényfájlt**.
3. A szerelvényfájl másolása a kiterjesztésmappába CRT:

    - **Commerce Scale Unit:** A fájl másolása **\\\\ az Internet Information Services (IIS) Commerce Scale Unit webhelyének bin ext** mappájába.
    - **Helyi CRT a Modern POS terminálon:** Másolja **\\ a fájlt a helyi ügyfélügynök helye alatti ext** CRT mappába.

4. A következő bővítmény-konfigurációs fájl megkeresve CRT:

    - **Commerce Scale Unit:** **A fájl neve commerceruntime.ext.config**, **\\ és az IIS Commerce Scale Unit webhely bin ext** mappájában található.
    - **Helyi CRT a Modern POS terminálon:** **A fájl neve CommerceRuntime.MPOSOffline.Ext.config**, CRT és a helyi ügyfélügynök helye alatt található.

5. A változás CRT regisztrálása a kiterjesztés konfigurációs fájljában.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.Extensions.DocumentProvider.PosnetSample" />
    ```

6. Indítsa újra a Commerce Service szolgáltatást:

    - **Commerce Scale Unit: Indítsa** újra a Commerce Service webhelyet az IIS-kezelőből.
    - **Ügyfélügynök:** Indítsa el a **dllhost.exe folyamatot** a Feladatkezelőben, majd indítsa újra a Modern POS alkalmazást.

### <a name="hardware-station-extension-components"></a>Hardverállomás bővítési összetevői

A Retail SDK tartalmazza a Hardverállomás bővítmény összetevőit. A következő eljárások befejezéséhez **nyissa meg a HardwareStationSamples.sln** megoldást a **RetailSdk\\ SampleExtensions\\ HardwareStation eszközben**.

1. Keresse meg **és építse fel a HardwareStation.Extension.PosnetThermalFVFiscalPrinterSample** projektet.
2. **Keresse meg a Contoso.Commerce.HardwareStation.Posnet.Posnet.ContosoFiscalPrinterSample\\ bin\\ Hibakeresési** **mappát. A Contoso.Commerce.HardwareStation.PosnetThermalFVFiscalPrinterSample.dll** szerelvényfájlt keresse meg.
3. A szerelvényfájl másolása egy telepített hardverállomás-gépre:

    - **Távoli hardverállomás:** Másolja a **fájlt** az IIS hardverállomás helyének bin mappájába. A nyomtató-illesztőprogram tárak (libposcmbth.dll **,** libcmbth **serial.dll\_ és** cmbth **pl.lng) másolása\_**.

4. A hardverállomás bővítményeihez található konfigurációs fájl megkeresve. A fájl neve **HardwareStation.Extension.config**:

    - **Távoli hardverállomás:** A fájl az IIS hardverállomás helye alatt található.

5. Adja hozzá a következő sort a **konfigurációs** fájl összeállítási szakaszhoz.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.PosnetThermalFVFiscalPrinterSample" />
    ```

6. Indítsa újra a hardverállomás szolgáltatást:

    - **Távoli hardverállomás: Indítsa** újra a hardverállomás webhelyet az IIS-kezelőből.

## <a name="production-environment"></a>Működési környezet

Az előző művelet során engedélyezte a pénzügyi nyilvántartási szolgáltatás integrációs mintája által tartalmazott bővítményeket. Ezenkívül ezeket a lépéseket kell követnie ahhoz, hogy commerce összetevőket tartalmazó telepíthető csomagokat hozzon létre, és ezeket a csomagokat éles környezetben alkalmazza.

1. Tegye a következő módosításokat **a RetailSdk\\ Assets mappa csomagkonfigurációs fájljaiban**:

    - **A Commerceruntime.ext.config** **és CommerceRuntime.MPOSOffline.Ext.config** **konfigurációs fájlokban adja hozzá a következő sort az összeállítási szakaszhoz**.

        ``` xml
        <add source="assembly" value="Contoso.Commerce.Runtime.Extensions.DocumentProvider.PosnetSample" />
        ```

    - **A HardwareStation.Extension.config** konfigurációs fájlban adja hozzá a következő sort az összeállítási **szakaszhoz**.

        ``` xml
        <add source="assembly" value="Contoso.Commerce.HardwareStation.PosnetThermalFVFiscalPrinterSample" />
        ```

1. Tegye a következő módosításokat a **Testreszabás.beállítások** csomag testreszabása konfigurációs fájlban a **BuildTools mappában**:

    - Adja hozzá a következő sort, hogy a CRT bővítmény bele legyen foglalva a telepíthető csomagokba.

        ``` xml
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.Extensions.DocumentProvider.PosnetSample.dll"/>
        ```

    - Adja hozzá a következő sort, hogy a hardverállomás bővítmény szerepeljen a telepíthető csomagokban.

        ``` xml
        <ISV_HardwareStation_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.HardwareStation.PosnetThermalFVFiscalPrinterSample.dll"/>
        ```

1. Indítsa el az MSBuild parancssort Visual Studio a segédprogrammal, **és futtassa az msbuild** csomagot a Retail SDK mappában a telepíthető csomagok létrehozásához.
1. A csomagok alkalmazása LCS-en keresztül vagy manuálisan. A további tudnivalókat lásd [a Telepíthető csomagok létrehozása.](../dev-itpro/retail-sdk/retail-sdk-packaging.md)

## <a name="design-of-extensions"></a>Bővítmények tervezése

A pénzügyi nyomtató integrációs mintája Lengyelországhoz a pénzügyi integrációs funkciókon [alapul](fiscal-integration-for-retail-channel.md). A pénzügyi integrációs megoldás megtervezésével [kapcsolatos további tudnivalókat lásd a pénzügyi integrációs mintaterv áttekintésében](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services).

### <a name="commerce-runtime-extension-design"></a>Commerce runtime bővítmény tervezése

A kiterjesztés célja, amely egy pénzügyi bizonylatot szolgáltató, az a cél, hogy nyomtatóspecifikus dokumentumokat generáljon, és kezelni tudja a pénzügyi nyomtató válaszait.

A CRT kiterjesztés a **Runtime.Extensions.DocumentProvider.PosnetSample**. Ez a kiterjesztés a POSNET 19-3678-as meghatározása által meghatározott JavaScript object Notation (JSON) formátumú nyomtatóspecifikus parancsokat generál.

A pénzügyi integráció megoldásának [kialakításával kapcsolatos további tudnivalókat lásd a Pénzügyi nyilvántartási folyamat és a pénzügyi eszközök és szolgáltatások pénzügyi integrációs mintáiban](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services).

#### <a name="request-handler"></a>Kérelemkezelő

A **DocumentProviderPosnetProtocol** kérelemkezelő a pénzügyi nyomtatón történő dokumentum-generálás igénylésének belépési pontja.

A kezelő az **INamedRequestHandler felületről öröklődik**. A **HandlerName metódus** felelős a kezelő nevének visszaküldéséért. A kezelő nevének meg kell egyeznie a Commerce Headquarters szolgáltatásban megadott csatlakoztató dokumentumszolgáltató nevével.

Az csatlakoztató a következő kéréseket támogatja:

- **GetFiscalDocumentDocumentProviderRequest** – ez a kérés tartalmazza a létrehozandó dokumentum adatait. Olyan nyomtatóspecifikus bizonylatot ad vissza, amely regisztrálva kell lennie a pénzügyi nyomtatón.
- **GetSupportedRegistrableEventsDocumentProviderRequest** – ez a kérés a regisztrált események listáját adja eredményül. Jelenleg a következő események támogatottak: értékesítés, X-jelentés nyomtatás és Z-jelentés nyomtatás.

#### <a name="configuration"></a>Konfiguráció

A konfigurációs fájl a bővítményprojekt **Konfigurációs** mappájában található. A fájl célja, hogy lehetővé tegye a dokumentumszolgáltató Commerce Headquarters rendszerből származó konfigurálásának beállításait. A fájlformátum igazodik a pénzügyi integráció konfigurációjának követelményeihez. A következő beállításokat lehet hozzáadni:

- Áfakulcsok leképezése
- Fizetőeszköz-típus leképezése
- Letét fizetési típusa

### <a name="hardware-station-extension-design"></a>Hardverállomás bővítményének tervezése

A pénzügyi csatlakoztatóként használt bővítmény célja a pénzügyi nyomtatóval való kommunikáció.

A Hardverállomás kiterjesztése **HardwareStation.Extension.PosnetThermalFVFiscalPrinterSample**. Ez a kiterjesztés hívja meg a POSNET illesztőprogram funkcióit, és elküldi CRT a kiterjesztés által a pénzügyi nyomtatón generált parancsokat. Az eszközhibákat is kezeli.

#### <a name="request-handler"></a>Kérelemkezelő

A **FiscalPrinterHandler** kérelemkezelő a kérésnek a pénzügyi perifériás eszközzel való kezelés belépési pontja.

A kezelő az **INamedRequestHandler felületről öröklődik**. A **HandlerName metódus** felelős a kezelő nevének visszaküldéséért. A kezelő nevének meg kell egyeznie a Commerce Headquartersban megadott pénzügyi csatlakoztató nevével.

Az csatlakoztató a következő kéréseket támogatja:

- **SubmitDocumentFiscalDeviceRequest** – ez a kérés dokumentumokat küld a nyomtatóknak, és visszaküldi a választ a pénzügyi nyomtatóról.
- **IsReadyFiscalDeviceRequest** – ez a kérés az eszköz állapotának ellenőrzésére használható.
- **InitializeFiscalDeviceRequest** – ez a kérés a nyomtató inicializálásához használatos.

#### <a name="configuration"></a>Konfiguráció

A konfigurációs fájl a bővítményprojekt **Konfigurációs** mappájában található. A fájl célja, hogy lehetővé tegye a csatlakoztató Commerce Headquarters alkalmazásból származó konfigurálásának beállításait. A fájlformátum igazodik a pénzügyi integráció konfigurációjának követelményeihez. A következő beállításokat lehet hozzáadni:

- **Kapcsolati** karakterlánc – karakterlánc, amely az illesztő által támogatott formátumban írja le az eszközzel való kapcsolat részleteit. A további tudnivalókat lásd a POSNET illesztőprogram dokumentációjában.
- **Dátum- és időszinkronizálás** – ez az érték határozza meg, hogy szinkronizálni kell-e a nyomtató dátumát és időpontját a csatlakoztatott hardverállomással.
- **Eszköz időkorlátja** – az az idő ezredmásodpercben, ahányszor a vezető választ vár az eszközről. A további tudnivalókat lásd a POSNET illesztőprogram dokumentációjában.
