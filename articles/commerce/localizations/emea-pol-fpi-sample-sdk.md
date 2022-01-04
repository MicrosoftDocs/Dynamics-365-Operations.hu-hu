---
title: Telepítési irányelvek a pénzügyi nyomtató integrációs mintához Lengyelországhoz (legacy)
description: Ez a témakör a pénzügyi nyomtató integrációs mintáinak a Kiskereskedelmi szoftverfejlesztői csomagból (SDK) való telepítésével kapcsolatban Microsoft Dynamics 365 Commerce tartalmaz tájékoztatást.
author: EvgenyPopovMBS
ms.date: 12/20/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2019-3-1
ms.openlocfilehash: bff3a6ad74d50e7b706d4df92b17a4a3af36521b
ms.sourcegitcommit: 0d2de52e12fdb9928556d37a4813a67b303695dc
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/21/2021
ms.locfileid: "7944815"
---
# <a name="deployment-guidelines-for-the-fiscal-printer-integration-sample-for-poland-legacy"></a>Telepítési irányelvek a pénzügyi nyomtató integrációs mintához Lengyelországhoz (legacy)

[!include[banner](../includes/banner.md)]

Ez a témakör a Pénzügyi nyomtató integrációs mintái rendszernek a Microsoft Dynamics 365 Commerce Microsoft Dynamics Lifecycle Services (LCS) fejlesztői virtuális gépére (SDK) készült kiskereskedelmi szoftverfejlesztői csomagból (SDK) való telepítéséhez nyújt tájékoztatást. A pénzügyi integrációs mintával kapcsolatos további tudnivalókat lásd a Pénzügyi [nyomtató integrációs mintája Lengyelország esetében](emea-pol-fpi-sample.md). 

A Lengyelországhoz készült pénzügyi integrációs minta a Retail SDK része. Az SDK telepítésével és használatával kapcsolatos tudnivalókat lásd a [Retail szoftverfejlesztői csomag (SDK) architektúráját](../dev-itpro/retail-sdk/retail-sdk-overview.md). Ez a minta a Commerce runtime () és a CRT hardverállomás bővítményeiből áll. A minta futtatásához módosítania és fel kell építenie a és a CRT hardverállomás-projekteket. Javasoljuk, hogy egy nem módosított Retail SDK készlet használatával tegye meg az ebben a témakörben leírt változtatásokat. Javasoljuk továbbá, hogy forrásvezérlő rendszert használjon, például olyanokat, ahol a Azure DevOps fájlok még nem módosultak.

## <a name="development-environment"></a>Fejlesztői környezet

A következő lépések szerint állíthatja be a fejlesztői környezetet, hogy tesztelni és ki tudja terjeszteni a mintát.

### <a name="commerce-runtime-extension-components"></a>Commerce runtime kiterjesztésű összetevők

A CRT bővítmények összetevői a Retail SDK szoftverfejlesztő készletében találhatók. A következő eljárások befejezéséhez nyissa meg a **CommerceRuntimeSamples.sln megoldást** a **RetailSdk \\ SampleExtensions \\ CommerceRuntime** alatt.

1. A **Runtime.Extensions.DocumentProvider.PosnetSample projekt megkeresása** és összeállítása.
2. Az **Extensions.DocumentProvider.PosnetSample bin hibakeresési mappában keresse meg a \\\\** **Contoso.Commerce.Runtime.Extensions.DocumentProvider.PosnetSample.dll** szerelvényfájlt.
3. A szerelvényfájl másolása a CRT kiterjesztésmappába:

    - **Commerce Scale Unit: A fájl másolása az Internet Information Services (IIS) Commerce Scale Unit webhelyének bin** **\\\\** ext mappájába.
    - **Helyi a Modern POS terminálon: Másolja a fájlt a helyi ügyfélügynök helye alatti CRT** **\\ ext** CRT mappába.

4. A következő bővítmény-konfigurációs fájl CRT megkeresve:

    - **Commerce Scale Unit: A fájl neve** **commerceruntime.ext.config, és az IIS Commerce Scale Unit webhely bin** **\\ ext** mappájában található.
    - **Helyi a Modern POS terminálon: A fájl neve CRT** **CommerceRuntime.MPOSOffline.Ext.config, és a helyi ügyfélügynök** CRT helye alatt található.

5. A változás CRT regisztrálása a kiterjesztés konfigurációs fájljában.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.Extensions.DocumentProvider.PosnetSample" />
    ```

6. Indítsa újra a Commerce Service szolgáltatást:

    - **Commerce Scale Unit:** Indítsa újra a Commerce Service webhelyet az IIS-kezelőből.
    - **Ügyfélügynök:** Indítsa el a **dllhost.exe folyamatot a Feladatkezelőben, majd indítsa újra a** Modern POS alkalmazást.

### <a name="hardware-station-extension-components"></a>Hardverállomás bővítési összetevői

A Retail SDK tartalmazza a Hardverállomás bővítmény összetevőit. A következő eljárások befejezéséhez nyissa meg a **HardwareStationSamples.sln megoldást** a **RetailSdk \\ SampleExtensions \\ HardwareStation** eszközben.

1. Keresse meg és építse fel **a HardwareStation.Extension.PosnetThermalFVFiscalPrinterSample** projektet.
2. Keresse meg **a Contoso.Commerce.HardwareStation.Posnet.Posnet.ContosoFiscalPrinterSample \\ bin \\ Hibakeresési** **mappát. A Contoso.Commerce.HardwareStation.PosnetThermalFVFiscalPrinterSample.dll szerelvényfájlt** keresse meg.
3. A szerelvényfájl másolása egy telepített hardverállomás-gépre:

    - **Távoli hardverállomás: Másolja a fájlt az IIS hardverállomás helyének** **bin** mappájába. A nyomtató-illesztőprogram tárak **(libposcmbth.dll,** **libcmbth \_ serial.dll** és **cmbth \_ pl.lng)** másolása.

4. A hardverállomás bővítményeihez található konfigurációs fájl megkeresve. A fájl neve **HardwareStation.Extension.config:**

    - **Távoli hardverállomás: A fájl az IIS hardverállomás** helye alatt található.

5. Adja hozzá a következő sort a konfigurációs **fájl** összeállítási szakaszhoz.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.PosnetThermalFVFiscalPrinterSample" />
    ```

6. Indítsa újra a hardverállomás szolgáltatást:

    - **Távoli hardverállomás:** Indítsa újra a hardverállomás webhelyet az IIS-kezelőből.

## <a name="production-environment"></a>Működési környezet

Az előző művelet során engedélyezte a pénzügyi nyilvántartási szolgáltatás integrációs mintája által tartalmazott bővítményeket. Ezenkívül ezeket a lépéseket kell követnie ahhoz, hogy commerce összetevőket tartalmazó telepíthető csomagokat hozzon létre, és ezeket a csomagokat éles környezetben alkalmazza.

1. Tegye a következő módosításokat a RetailSdk Assets mappa csomagkonfigurációs **\\** fájljaiban:

    - A **Commerceruntime.ext.config és** **CommerceRuntime.MPOSOffline.Ext.config konfigurációs fájlokban adja hozzá a következő sort az** **összeállítási** szakaszhoz.

        ``` xml
        <add source="assembly" value="Contoso.Commerce.Runtime.Extensions.DocumentProvider.PosnetSample" />
        ```

    - A HardwareStation.Extension.config konfigurációs fájlban adja hozzá a következő sort **az** **összeállítási** szakaszhoz.

        ``` xml
        <add source="assembly" value="Contoso.Commerce.HardwareStation.PosnetThermalFVFiscalPrinterSample" />
        ```

1. Tegye a következő módosításokat a Testreszabás.beállítások csomag testreszabása **konfigurációs** fájlban a **BuildTools** mappában:

    - Adja hozzá a következő sort, hogy a CRT bővítmény bele legyen foglalva a telepíthető csomagokba.

        ``` xml
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.Extensions.DocumentProvider.PosnetSample.dll"/>
        ```

    - Adja hozzá a következő sort, hogy a hardverállomás bővítmény szerepeljen a telepíthető csomagokban.

        ``` xml
        <ISV_HardwareStation_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.HardwareStation.PosnetThermalFVFiscalPrinterSample.dll"/>
        ```

1. Indítsa el az MSBuild parancssort a segédprogrammal, és futtassa az msbuild csomagot a Retail SDK mappában a telepíthető Visual Studio **csomagok** létrehozásához.
1. A csomagok alkalmazása LCS-en keresztül vagy manuálisan. A további tudnivalókat lásd [a Telepíthető csomagok](../dev-itpro/retail-sdk/retail-sdk-packaging.md) létrehozása.

## <a name="design-of-extensions"></a>Bővítmények tervezése

A pénzügyi nyomtató integrációs mintája Lengyelországhoz a pénzügyi [integrációs funkciókon](fiscal-integration-for-retail-channel.md) alapul. A pénzügyi integrációs megoldás megtervezésével kapcsolatos további tudnivalókat lásd a pénzügyi integrációs [mintaterv](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices) áttekintésében.

### <a name="commerce-runtime-extension-design"></a>Commerce runtime bővítmény tervezése

A kiterjesztés célja, amely egy pénzügyi bizonylatot szolgáltató, az a cél, hogy nyomtatóspecifikus dokumentumokat generáljon, és kezelni tudja a pénzügyi nyomtató válaszait.

A CRT kiterjesztés **a Runtime.Extensions.DocumentProvider.PosnetSample.** Ez a kiterjesztés a POSNET 19-3678-as meghatározása által meghatározott JavaScript object Notation (JSON) formátumú nyomtatóspecifikus parancsokat generál.

A pénzügyi integráció megoldásának kialakításával kapcsolatos további tudnivalókat lásd a Pénzügyi nyilvántartási folyamat és a pénzügyi eszközök pénzügyi integrációs [mintái.](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices)

#### <a name="request-handler"></a>Kérelemkezelő

A **DocumentProviderPosnetProtocol kérelemkezelő a pénzügyi nyomtatón történő dokumentum-generálás** igénylésének belépési pontja.

A kezelő az **INamedRequestHandler felületről** öröklődik. A HandlerName metódus felelős a kezelő nevének **visszaküldéséért**. A kezelő nevének meg kell egyeznie a Commerce Headquarters szolgáltatásban megadott csatlakoztató dokumentumszolgáltató nevével.

Az csatlakoztató a következő kéréseket támogatja:

- **GetFiscalDocumentDocumentProviderRequest – ez a kérés tartalmazza a létrehozandó** dokumentum adatait. Olyan nyomtatóspecifikus bizonylatot ad vissza, amely regisztrálva kell lennie a pénzügyi nyomtatón.
- **GetSupportedRegistrableEventsDocumentProviderRequest – ez a kérés a regisztrált események listáját adja** eredményül. Jelenleg a következő események támogatottak: értékesítés, X-jelentés nyomtatás és Z-jelentés nyomtatás.

#### <a name="configuration"></a>Konfiguráció

A konfigurációs fájl a bővítményprojekt **Konfigurációs** mappájában található. A fájl célja, hogy lehetővé tegye a dokumentumszolgáltató Commerce Headquarters rendszerből származó konfigurálásának beállításait. A fájlformátum igazodik a pénzügyi integráció konfigurációjának követelményeihez. A következő beállításokat lehet hozzáadni:

- Áfakulcsok leképezése
- Fizetőeszköz-típus leképezése
- Letét fizetési típusa

### <a name="hardware-station-extension-design"></a>Hardverállomás bővítményének tervezése

A pénzügyi csatlakoztatóként használt bővítmény célja a pénzügyi nyomtatóval való kommunikáció.

A Hardverállomás kiterjesztése **HardwareStation.Extension.PosnetThermalFVFiscalPrinterSample.** Ez a kiterjesztés hívja meg a POSNET illesztőprogram funkcióit, és elküldi a kiterjesztés által a pénzügyi CRT nyomtatón generált parancsokat. Az eszközhibákat is kezeli.

#### <a name="request-handler"></a>Kérelemkezelő

A **FiscalPrinterHandler kérelemkezelő a kérésnek a pénzügyi perifériás eszközzel való kezelés** belépési pontja.

A kezelő az **INamedRequestHandler felületről** öröklődik. A HandlerName metódus felelős a kezelő nevének **visszaküldéséért**. A kezelő nevének meg kell egyeznie a Commerce Headquartersban megadott pénzügyi csatlakoztató nevével.

Az csatlakoztató a következő kéréseket támogatja:

- **SubmitDocumentFiscalDeviceRequest – ez a kérés dokumentumokat küld a nyomtatóknak, és visszaküldi a választ a** pénzügyi nyomtatóról.
- **IsReadyFiscalDeviceRequest – ez a kérés az eszköz állapotának** ellenőrzésére használható.
- **InitializeFiscalDeviceRequest – ez a kérés** a nyomtató inicializálásához használatos.

#### <a name="configuration"></a>Konfiguráció

A konfigurációs fájl a bővítményprojekt **Konfigurációs** mappájában található. A fájl célja, hogy lehetővé tegye a csatlakoztató Commerce Headquarters alkalmazásból származó konfigurálásának beállításait. A fájlformátum igazodik a pénzügyi integráció konfigurációjának követelményeihez. A következő beállításokat lehet hozzáadni:

- **Kapcsolati karakterlánc – karakterlánc, amely az illesztő által támogatott formátumban írja le az eszközzel való** kapcsolat részleteit. A további tudnivalókat lásd a POSNET illesztőprogram dokumentációjában.
- **Dátum- és időszinkronizálás – ez az érték határozza meg, hogy szinkronizálni kell-e a nyomtató dátumát és időpontját a csatlakoztatott** hardverállomással.
- **Eszköz időkorlátja – az az idő ezredmásodpercben, ahányszor a vezető választ vár** az eszközről. A további tudnivalókat lásd a POSNET illesztőprogram dokumentációjában.
