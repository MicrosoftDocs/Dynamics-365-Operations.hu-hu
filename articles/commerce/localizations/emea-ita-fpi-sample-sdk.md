---
title: A pénzügyi nyomtató integrációs mintája olaszországi telepítési irányelvei (legacy)
description: Ez a témakör a pénzügyi nyomtató integrációs mintáinak a Retail szoftverfejlesztői csomagból (SDK) való telepítésével kapcsolatban Microsoft Dynamics 365 Commerce nyújt tájékoztatást.
author: EvgenyPopovMBS
ms.date: 12/20/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2019-3-1
ms.openlocfilehash: a7b5f4f042aa5457ff33e9762f0902c5c72f5921
ms.sourcegitcommit: 0d2de52e12fdb9928556d37a4813a67b303695dc
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/21/2021
ms.locfileid: "7944840"
---
# <a name="deployment-guidelines-for-the-fiscal-printer-integration-sample-for-italy-legacy"></a>A pénzügyi nyomtató integrációs mintája olaszországi telepítési irányelvei (legacy)

[!include[banner](../includes/banner.md)]

Ez a témakör a Microsoft Dynamics 365 Commerce Lifecycle Services (LCS) fejlesztői virtuális gépére (VM) telepített Retail szoftverfejlesztői csomagból (SDK) származó, Olaszországhoz tartozó pénzügyi nyomtató-integrációs minta telepítésével kapcsolatban Microsoft Dynamics nyújt tájékoztatást. A pénzügyi integrációs mintával kapcsolatos további tudnivalókat lásd a [Pénzügyi nyomtató integrációs mintája Olaszország esetében](emea-ita-fpi-sample.md). 

Az Olaszországhoz tartozó pénzügyi integrációs minta a Retail SDK része. Az SDK telepítésével és használatával kapcsolatos tudnivalókat lásd a [Retail szoftverfejlesztői csomag (SDK) architektúráját](../dev-itpro/retail-sdk/retail-sdk-overview.md). Ez a minta a Commerce runtime () és a CRT hardverállomás bővítményeiből áll. A minta futtatásához módosítania és fel kell építenie a és a CRT hardverállomás-projekteket. Javasoljuk, hogy egy nem módosított Retail SDK készlet használatával tegye meg az ebben a témakörben leírt változtatásokat. Javasoljuk továbbá, hogy forrásvezérlő rendszert használjon, például olyanokat, ahol a Azure DevOps fájlok még nem módosultak.

## <a name="development-environment"></a>Fejlesztői környezet

A következő lépések szerint állíthatja be a fejlesztői környezetet, hogy tesztelni és ki tudja terjeszteni a mintát.

### <a name="commerce-runtime-extension-components"></a>Commerce runtime kiterjesztésű összetevők

A CRT bővítmények összetevői a Retail SDK szoftverfejlesztő készletében találhatók. A következő eljárások befejezéséhez nyissa meg a **CommerceRuntimeSamples.sln megoldást** a **RetailSdk \\ SampleExtensions \\ CommerceRuntime** alatt.

1. A **Runtime.Extensions.DocumentProvider.EpsonFP90IISample projekt** megkeresása és összeállítása.
2. Az **Extensions.DocumentProvider.EpsonFP90IISample bin hibakeresési mappában keresse meg a \\\\** **Contoso.Commerce.Runtime.DocumentProvider.EpsonFP90IISample.dll** szerelvényfájlt.
3. A szerelvényfájl másolása CRT a bővítmények mappájába:

    - **Commerce Scale Unit: A fájl másolása az Internet Information Services (IIS) Commerce Scale Unit webhelyének bin** **\\\\** ext mappájába.
    - **Helyi a Modern POS terminálon: Másolja a fájlt a helyi ügyfélügynök helye alatti CRT** **\\ ext** CRT mappába.

4. A következő bővítmény-konfigurációs fájl CRT megkeresve:

    - **Commerce Scale Unit: A fájl neve** **commerceruntime.ext.config, és az IIS Commerce Scale Unit webhely bin** **\\ ext** mappájában található.
    - **Helyi a Modern POS terminálon: A fájl neve CRT** **CommerceRuntime.MPOSOffline.Ext.config, és a helyi ügyfélügynök** CRT helye alatt található.

5. A változás CRT regisztrálása a kiterjesztés konfigurációs fájljában.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.EpsonFP90IIISample" />
    ```

6. A Commerce Scale Unit újraindítása:

    - **Commerce Scale Unit:** Indítsa újra a Commerce Scale Unit webhelyet az IIS-kezelőből.
    - **Ügyfélügynök:** Indítsa el a **dllhost.exe folyamatot a Feladatkezelőben, majd indítsa újra a** Modern POS alkalmazást.

### <a name="hardware-station-extension-components"></a>Hardverállomás bővítési összetevői

A Retail SDK tartalmazza a Hardverállomás bővítmény összetevőit. A következő eljárások befejezéséhez nyissa meg a **HardwareStationSamples.sln megoldást** a **RetailSdk \\ SampleExtensions \\ HardwareStation** eszközben.

1. Keresse meg és építse ki **a HardwareStation.Extensions.EpsonFP90IIFiscalDeviceSample** projektet.
2. Az **Extensions.EpsonFP90IIFiscalDeviceSample bin Hibakeresési mappában keresse meg a \\\\** **Contoso.Commerce.HardwareStation.EpsonFP90IIFiscalDeviceSample.dll** szerelvényfájlt.
3. A szerelvényfájl másolása egy telepített hardverállomás-gépre:

    - **Távoli hardverállomás: Másolja a fájlt az IIS hardverállomás helyének** **bin** mappájába.
    - **Helyi hardverállomás: A fájl** másolása a Modern POS ügyfélügynöki helyére.

4. A hardverállomás bővítményeihez található konfigurációs fájl megkeresve. A fájl neve **HardwareStation.Extension.config:**

    - **Távoli hardverállomás: A fájl az IIS hardverállomás** helye alatt található.
    - **Helyi hardverállomás:** A fájl a Modern POS ügyfélügynök helye alatt található.

5. Adja hozzá a következő **szakaszt a** konfigurációs fájl összeállítási szakaszhoz.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.EpsonFP90IIIFiscalDeviceSample" />
    ```

6. Indítsa újra a hardverállomás szolgáltatást:

    - **Távoli hardverállomás:** Indítsa újra a hardverállomás webhelyet az IIS-kezelőből.
    - **Helyi hardverállomás: A feladatkezelőben le kell indítani a** **dllhost.exe folyamatot, majd újra kell** indítani a Modern POS rendszert.

## <a name="production-environment"></a>Működési környezet

A Commerce összetevőket tartalmazó telepíthető csomagok létrehozásához és a csomagok éles környezetben való alkalmazáshoz kövesse ezeket a lépéseket.

1. A témakör korábbi részében, a Fejlesztői környezetben leírt [lépések](#development-environment) befejezése.
2. Tegye a következő módosításokat a RetailSdk Assets mappa csomagkonfigurációs **\\** fájljaiban:

    - A **Commerceruntime.ext.config és** **CommerceRuntime.MPOSOffline.Ext.config konfigurációs fájlokban adja hozzá a következő sort az** **összeállítási** szakaszhoz.

        ``` xml
        <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.EpsonFP90IIISample" />
        ```

    - A HardwareStation.Extension.config konfigurációs fájlban adja hozzá a következő sort **az** **összeállítási** szakaszhoz.

        ``` xml
        <add source="assembly" value="Contoso.Commerce.HardwareStation.EpsonFP90IIIFiscalDeviceSample" />
        ```

3. Tegye a következő módosításokat a Testreszabás.beállítások csomag testreszabása **konfigurációs** fájlban a **BuildTools** mappában:

    - Adja hozzá a következő sort, hogy a CRT bővítmény bele legyen foglalva a telepíthető csomagokba.

        ``` xml
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.DocumentProvider.EpsonFP90IIISample.dll"/>
        ```

    - Adja hozzá a következő sort, hogy a hardverállomás bővítmény szerepeljen a telepíthető csomagokban.

        ``` xml
        <ISV_HardwareStation_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.HardwareStation.EpsonFP90IIIFiscalDeviceSample.dll"/>
        ```

4. Indítsa el az MSBuild parancssort a segédprogrammal, majd futtassa az msbuild csomagot a Retail SDK mappában, hogy Visual Studio **telepíthető** csomagokat hozzon létre.
5. A csomagok alkalmazása LCS-en keresztül vagy manuálisan. A további tudnivalókat lásd [a Telepíthető csomagok](../dev-itpro/retail-sdk/retail-sdk-packaging.md) létrehozása.

## <a name="design-of-extensions"></a>Bővítmények tervezése

### <a name="commerce-runtime-extension-design"></a>Commerce runtime bővítmény tervezése

A kiterjesztés célja, amely egy pénzügyi bizonylatot szolgáltató, az a cél, hogy nyomtatóspecifikus dokumentumokat generáljon, és kezelni tudja a pénzügyi nyomtató válaszait.

A CRT kiterjesztés **a Runtime.Extensions.DocumentProvider.EpsonFP90IISample.**

A pénzügyi integráció megoldásának kialakításával kapcsolatos további tudnivalókat lásd a Pénzügyi nyilvántartási folyamat és a pénzügyi eszközök pénzügyi integrációs [mintái.](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices)

#### <a name="request-handler"></a>Kérelemkezelő

A **DocumentProviderEpsonFP90II kéréskezelő a pénzügyi nyomtatón történő dokumentum-generálás igénylésének belépési** pontja.

A kezelő az **INamedRequestHandler felületről** öröklődik. A HandlerName metódus felelős a kezelő nevének **visszaküldéséért**. A kezelő nevének meg kell egyeznie a Commerce Headquarters szolgáltatásban megadott csatlakoztató dokumentumszolgáltató nevével.

Az csatlakoztató a következő kéréseket támogatja:

- **GetFiscalDocumentDocumentProviderRequest – ez a kérés tartalmazza a létrehozandó** dokumentum adatait. Olyan nyomtatóspecifikus bizonylatot ad vissza, amely regisztrálva kell lennie a pénzügyi nyomtatón.
- **GetSupportedRegistrableEventsDocumentProviderRequest – ez a kérés a regisztrált események listáját adja** eredményül. Jelenleg a következő események támogatottak: értékesítés, X-jelentés nyomtatás és Z-jelentés nyomtatás.

#### <a name="configuration"></a>Konfiguráció

A konfigurációs fájl a bővítményprojekt **Konfigurációs** mappájában található. A fájl célja, hogy lehetővé tegye a dokumentumszolgáltató Commerce Headquarters rendszerből származó konfigurálásának beállításait. A fájlformátum igazodik a pénzügyi integráció konfigurációjának követelményeihez. A következő beállításokat lehet hozzáadni:

- Áfakódok leképezése
- Áfakulcsok leképezése
- Fizetőeszköz-típus leképezése
- A nyugtaszám vonalkódtípusa
- Letét fizetési típusa

### <a name="hardware-station-extension-design"></a>Hardverállomás bővítményének tervezése

A pénzügyi csatlakoztatóként használt bővítmény célja a pénzügyi nyomtatóval való kommunikáció.

A Hardverállomás kiterjesztése **HardwareStation.Extension.EpsonFP90IIFiscalDeviceSample.** Ez a kiterjesztés a HTTP protokollal küldheti el a kiterjesztés által CRT a pénzügyi nyomtatón generált dokumentumokat. A pénzügyi nyomtatóról kapott válaszokat is kezeli.

#### <a name="request-handler"></a>Kérelemkezelő

Az **EpsonFP90IISample kérelemkezelő a pénzügyi perifériás eszközre vonatkozó kérések** kezelésének belépési pontja.

A kezelő az **INamedRequestHandler felületről** öröklődik. A HandlerName metódus felelős a kezelő nevének **visszaküldéséért**. A kezelő nevének meg kell egyeznie a Commerce Headquartersban megadott pénzügyi csatlakoztató nevével.

Az csatlakoztató a következő kéréseket támogatja:

- **SubmitDocumentFiscalDeviceRequest – ez a kérés dokumentumokat küld a nyomtatóknak, és visszaküldi a választ a** pénzügyi nyomtatóról.
- **IsReadyFiscalDeviceRequest – ez a kérés az eszköz állapotának** ellenőrzésére használható.
- **InitializeFiscalDeviceRequest – ez a kérés** a nyomtató inicializálásához használatos.

#### <a name="configuration"></a>Konfiguráció

A konfigurációs fájl a bővítményprojekt **Konfigurációs** mappájában található. A fájl célja, hogy lehetővé tegye a csatlakoztató Commerce Headquarters alkalmazásból származó konfigurálásának beállításait. A fájlformátum igazodik a pénzügyi integráció konfigurációjának követelményeihez. A következő beállításokat lehet hozzáadni:

- **Végpont címe** – a nyomtató URL-címe.
- **Dátum- és időszinkronizálás – ez az érték határozza meg, hogy szinkronizálni kell-e a nyomtató dátumát és időpontját a csatlakoztatott** hardverállomással.
