---
title: A Cseh Köztársaságra vonatkozó pénzügyi regisztrációs szolgáltatás integrációs mintája telepítési irányelvei (legacy)
description: Ez a témakör a Microsoft Dynamics 365 Commerce Retail szoftverfejlesztői csomagból (SDK) a Csehországba tartozó pénzügyi integrációs minta telepítésével kapcsolatban nyújt tájékoztatást.
author: EvgenyPopovMBS
ms.date: 03/04/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2019-3-1
ms.openlocfilehash: 80778547b99af5a7a9717146850d8161f2e8f686
ms.sourcegitcommit: b80692c3521dad346c9cbec8ceeb9612e4e07d64
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/05/2022
ms.locfileid: "8388338"
---
# <a name="deployment-guidelines-for-the-fiscal-registration-service-integration-sample-for-the-czech-republic-legacy"></a>A Cseh Köztársaságra vonatkozó pénzügyi regisztrációs szolgáltatás integrációs mintája telepítési irányelvei (legacy)

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

Ez a témakör Microsoft Dynamics 365 Commerce irányelveket tartalmaz a Cseh Köztársaság pénzügyi nyilvántartási szolgáltatásintegrációs mintának a Retail szoftverfejlesztői csomagból (SDK) való telepítéséhez a Lifecycle Services (LCS) Microsoft Dynamics egy fejlesztői virtuális gépére (VM). A pénzügyi integrációs mintával kapcsolatos további [tudnivalókat lásd a Cseh Köztársaság Pénzügyi nyilvántartási szolgáltatás integrációs mintája oldalon](emea-cze-fi-sample.md). 

A Cseh Köztársaság pénzügyi integrációs minta része a Retail SDK csomagnak. Az SDK [telepítésével és használatával kapcsolatos tudnivalókat lásd a Retail szoftverfejlesztői csomag (SDK) architektúráját](../dev-itpro/retail-sdk/retail-sdk-overview.md). Ez a minta a Commerce runtime (CRT) és a hardverállomás bővítményeiből áll. A minta futtatásához módosítania és fel kell építenie a és CRT a hardverállomás-projekteket. Javasoljuk, hogy egy nem módosított Retail SDK készlet használatával tegye meg az ebben a témakörben leírt változtatásokat. Javasoljuk továbbá, hogy forrásvezérlő rendszert használjon, Azure DevOps például olyanokat, ahol a fájlok még nem módosultak.

## <a name="development-environment"></a>Fejlesztői környezet

A következő lépések szerint állíthatja be a fejlesztői környezetet, hogy tesztelni és ki tudja terjeszteni a mintát.

### <a name="enable-commerce-runtime-extensions"></a>Commerce futásidejű bővítmények engedélyezése

A CRT kiterjesztési összetevők a mintában vannak CRT. A következő eljárások **befejezéséhez nyissa meg a CommerceRuntimeSamples.sln megoldást** a **RetailSdkSampleExtensionsCommerceRuntime\\\\ alatt**.

#### <a name="documentproviderefrsample-component"></a>DocumentProvider.EFRSample összetevő

1. A Runtime.Extensions.DocumentProvider.EFRSample **projekt** megkeresása és összeállítása.
2. **A Runtime.Extensions.DocumentProvider.EFRSamplebinDebug\\\\** **mappában keresse meg a Contoso.Commerce.Runtime.DocumentProvider.EFRSample.dll** szerelvényfájlt.
3. A szerelvényfájl másolása a bővítmények CRT mappájába:

    - **Commerce Scale Unit:** A **\\ fájl másolása az Internet Information Services (IIS) Commerce Scale Unit webhelyének binext\\** mappájába.
    - **Helyi CRT a Modern POS terminálon:** Másolja **\\ a fájlt a helyi ügyfélügynök helye alatti ext** CRT mappába.

4. A következő bővítmény-konfigurációs fájl megkeresve CRT:

    - **Commerce Scale Unit:** **A fájl neve commerceruntime.ext.config**, **és az IIS Commerce Scale Unit webhely binext\\** mappájában található.
    - **Helyi CRT a Modern POS terminálon:** **A fájl neve CommerceRuntime.MPOSOffline.Ext.config**, CRT és a helyi ügyfélügynök helye alatt található.

5. A változás CRT regisztrálása a kiterjesztés konfigurációs fájljában.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.EFRSample" />
    ```

#### <a name="documentproviderdatamodelefr-component"></a>DocumentProvider.DataModelEFR összetevő

1. Keresse meg **és építse fel a Runtime.Extensions.DocumentProvider.DataModelEFR** projektet.
2. **A Runtime.Extensions.DocumentProvider.DataModelEFRbinDebug\\\\** **mappában keresse meg a Contoso.Commerce.Runtime.DocumentProvider.DataModelEFR.dll** szerelvényfájlt.
3. A szerelvényfájl másolása a bővítmények CRT mappájába:

    - **Commerce Scale Unit:** A fájl másolása **\\ az IIS Commerce Scale Unit webhely binext\\** mappájába.
    - **Helyi CRT a Modern POS terminálon:** Másolja **\\ a fájlt a helyi ügyfélügynök helye alatti ext** CRT mappába.

4. A következő bővítmény-konfigurációs fájl megkeresve CRT:

    - **Commerce Scale Unit:** **A fájl neve commerceruntime.ext.config**, **és az IIS Commerce Scale Unit webhely binext\\** mappájában található.
    - **Helyi CRT a Modern POS terminálon:** **A fájl neve CommerceRuntime.MPOSOffline.Ext.config**, CRT és a helyi ügyfélügynök helye alatt található.

5. A változás CRT regisztrálása a kiterjesztés konfigurációs fájljában.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.DataModelEFR" />
    ```

#### <a name="extension-configuration-file"></a>Kiterjesztés konfigurációs fájlja

1. A következő bővítmény-konfigurációs fájl megkeresve CRT:

    - **Commerce Scale Unit:** **A fájl neve commerceruntime.ext.config**, **és az IIS Commerce Scale Unit webhely binext\\** mappájában található.
    - **Helyi CRT a Modern POS terminálon:** **A fájl neve CommerceRuntime.MPOSOffline.Ext.config**, CRT és a helyi ügyfélügynök helye alatt található.

2. A változás CRT regisztrálása a kiterjesztés konfigurációs fájljában.

    ``` xml
    <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.ReceiptsCzechia" />
    ```

### <a name="enable-fiscal-connector-extensions"></a>Pénzügyi csatlakoztató-bővítmények engedélyezése

A pénzügyi csatlakoztató-bővítményeket a hardverállomáson [vagy a PÉNZTÁRi pénztárgépen](fiscal-integration-for-retail-channel.md#fiscal-registration-is-done-via-a-device-connected-to-the-hardware-station) is [engedélyezheti](fiscal-integration-for-retail-channel.md#fiscal-registration-is-done-via-a-device-or-service-in-the-local-network).

### <a name="enable-hardware-station-extensions"></a>Hardverállomás-bővítmények engedélyezése

A Hardverállomás bővítmény összetevői a hardverállomás mintáiban szerepelnek. A következő eljárások **befejezéséhez nyissa meg a HardwareStationSamples.sln** megoldást a **RetailSdkSampleExtensionsHardwareStation\\\\ alatt**.

#### <a name="efrsample-component"></a>EFRSample összetevő

1. Keresse meg **és építse ki a HardwareStation.Extension.EFRSample** projektet.
2. **Az Extension.EFRSamplebinDebug\\\\ mappában** keresse meg a következő szerelvényfájlokat:

    - Contoso.Commerce.HardwareStation.EFRSample.dll
    - Contoso.Commerce.Runtime.DocumentProvider.DataModelEFR.dll

3. A szerelvényfájlok másolása a hardverállomás bővítmények mappájába:

    - **Megosztott hardverállomás:** A fájlok másolása **az** IIS hardverállomás webhelyének bin mappájába.
    - **Külön hardverállomás a Modern POS terminálon: A** fájlok másolása a Modern POS ügyfélügynöki helyére.

4. A hardverállomás bővítményének konfigurációs fájlja. A fájl neve **HardwareStation.Extension.config**.

    - **Megosztott hardverállomás:** A fájl az IIS hardverállomás helye alatt található.
    - **A Modern POS külön hardverállomása:** A fájl a Modern POS ügyfélügynök helye alatt található.

5. Adja hozzá a következő sort a **konfigurációs** fájl összeállítási szakaszhoz.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.EFRSample.dll" />
    ```

#### <a name="enable-pos-extensions"></a>POS-bővítmények engedélyezése

A POS-bővítményminta a **megoldástárház srcFiscalIntegrationPosFiscalConnectorSample\\\\**[Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/) mappájában található.

A következő lépésekkel használhatja a POS-bővítményt az örökölt SDK készletben.

1. Másolja a **Pos.Extension mappát** a legacy SDK könyvtár POS-bővítmények **mappájába** (például`C:\RetailSDK\src\POS\Extensions`).
1. Nevezze át a **Pos.Extension** mappa **PosFiscalConnector példányát**.
1. Távolítsa el a következő mappákat és fájlokat a **PosFiscalConnector mappából**:

    - Bin
    - DataService
    - devDependencies
    - Tárak
    - Obj
    - Contoso.PosFiscalConnectorSample.Pos.csproj
    - RetailServerEdmxModel.g.xml
    - tsconfig.json

1. Nyissa meg **a CloudPos.sln vagy** **a ModernPos.sln megoldást**.
1. **A Pos.Extensions projektben** foglalja bele a **PosFiscalConnector mappát**.
1. Nyissa meg **a extensions.json fájlt**, és **adja hozzá a PosFiscalConnector kiterjesztést**.
1. Az SDK összeállítása

### <a name="production-environment"></a>Működési környezet

Az előző eljárás lehetővé teszi a pénzügyi nyilvántartási szolgáltatás integrációs mintája által tartalmazott bővítményeket. Ezenkívül ezeket a lépéseket kell követnie ahhoz, hogy commerce összetevőket tartalmazó telepíthető csomagokat hozzon létre, és ezeket a csomagokat éles környezetben alkalmazza.

1. Tegye a következő módosításokat a **RetailSdkAssets\\ mappa csomagkonfigurációs fájljaiban**.

    - **A Commerceruntime.ext.config** **és a CommerceRuntime.MPOSOffline.Ext.config** **konfigurációs fájlokban adja hozzá a következő sorokat az összeállítási szakaszhoz**.

        ``` xml
        <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.EFRSample" />
        <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.DataModelEFR" />
        <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.ReceiptsCzechia" />
        ```

    - **A HardwareStation.Extension.config** konfigurációs fájlban adja hozzá a következő sort az összeállítási **szakaszhoz**.

        ``` xml
        <add source="assembly" value="Contoso.Commerce.HardwareStation.EFRSample" />
        ```

2. Tegye a következő módosításokat a **Testreszabás.beállítások** csomag testreszabása konfigurációs fájlban a **BuildTools mappában**.

    - Adja hozzá a következő sorokat, hogy a CRT bővítmények belevehetőek a telepíthető csomagokba.

        ``` xml
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.DocumentProvider.EFRSample.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.DocumentProvider.DataModelEFR.dll" />
        <ISV_HardwareStation_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.DocumentProvider.DataModelEFR.dll" />
        ```

    - Adja hozzá a következő sort, hogy a hardverállomás bővítmény szerepeljen a telepíthető csomagokban.

        ``` xml
        <ISV_HardwareStation_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.HardwareStation.EFRSample" />
        ```

3. Indítsa el az MSBuild parancssort Visual Studio a segédprogrammal, **és futtassa az msbuild** csomagot a Retail SDK mappában a telepíthető csomagok létrehozásához.
4. A csomagok alkalmazása LCS-en keresztül vagy manuálisan. A további tudnivalókat lásd [a Telepíthető csomagok létrehozása.](../dev-itpro/retail-sdk/retail-sdk-packaging.md)
5. Az összes szükséges beállítási feladat végrehajtása, amely a [Set up Commerce for The Csehországban le van írva](emea-cze-fi-sample.md#set-up-commerce-for-the-czech-republic).

## <a name="design-of-extensions"></a>Bővítmények tervezése

A Cseh Köztársaság pénzügyi nyilvántartási szolgáltatásintegrációs mintája a pénzügyi integrációs [funkciókon alapul](fiscal-integration-for-retail-channel.md). A pénzügyi integrációs megoldás megtervezésével [kapcsolatos további tudnivalókat lásd a pénzügyi integrációs mintaterv áttekintésében](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services).

### <a name="commerce-runtime-extension-design"></a>Commerce runtime bővítmény tervezése

A kiterjesztés célja, amely egy pénzügyi bizonylat szolgáltatója, a szolgáltatásspecifikus dokumentumok generálása és a pénzügyi nyilvántartási szolgáltatás válaszának kezelnie kell.

A CRT kiterjesztés a **Runtime.Extensions.DocumentProvider.EFRSample**.

#### <a name="request-handler"></a>Kérelemkezelő

A dokumentumszolgáltatóhoz **egyetlen DocumentProviderEFRFiscalIUSE** kérelemkezelő van. A pénzügyi nyilvántartási szolgáltatás pénzügyi bizonylatai generálják.

Ez a kezelő az **INamedRequestHandler felületről öröklődik**. A **HandlerName metódus** felelős a kezelő nevének visszaküldéséért. A kezelő nevének meg kell egyeznie a Commerce Headquarters szolgáltatásban megadott csatlakoztató dokumentumszolgáltató nevével.

Az csatlakoztató a következő kéréseket támogatja:

- **GetFiscalDocumentDocumentProviderRequest** – ez a kérés tartalmazza a létrehozandó dokumentum adatait. Olyan szolgáltatásspecifikus dokumentumot ad vissza, amely regisztrálva kell lennie a pénzügyi regisztrációs szolgáltatásban.
- **GetSupportedRegistrableEventsDocumentProviderRequest** – ez a kérés a regisztrált események listáját adja eredményül. Jelenleg a következő események támogatottak: értékesítés, vevői számlabetétek és vevői rendelési betétek.
- **GetFiscalRegisterResponseToSaveDocumentProviderRequest** – ez a kérés a pénzügyi regisztrációs szolgáltatás válaszát adja eredményül. A válasz egy karakterlánc formájában van szerializálva, hogy készen legyen a mentésre.

#### <a name="configuration"></a>Konfiguráció

A **DocumentProviderFiscalEFRSample Egy konfigurációs** fájl **a** bővítményprojekt Konfigurációs mappájában található. A fájl célja, hogy lehetővé tegye a dokumentumszolgáltató Commerce Headquarters rendszerből származó konfigurálásának beállításait. A fájlformátum igazodik a pénzügyi integráció konfigurációjának követelményeihez. A következő beállításokat lehet hozzáadni:

- Áfakulcsok leképezése
- Alapértelmezett áfacsoport
- Letét áfacsoportja

### <a name="hardware-station-extension-design"></a>Hardverállomás bővítményének tervezése

A pénzügyi csatlakoztatóként használt bővítmény célja a pénzügyi regisztrációs szolgáltatással való kommunikáció.

A Hardverállomás bővítmény neve **HardwareStation.Extension.EFRSample**. A HTTP vagy HTTPS protokollt CRT használja a bővítmények által a pénzügyi regisztrációs szolgáltatásnak generált dokumentumok elküldre. Kezeli a pénzügyi regisztrációs szolgáltatástól kapott válaszokat is.

#### <a name="request-handler"></a>Kérelemkezelő

Az **EFRHandler** kérelemkezelő a pénzügyi regisztrációs szolgáltatás kérésének kezelésére használt belépési pont.

A kezelő az **INamedRequestHandler felületről öröklődik**. A **HandlerName metódus** felelős a kezelő nevének visszaküldéséért. A kezelő nevének meg kell egyeznie a Commerce Headquartersban megadott pénzügyi csatlakoztató nevével.

Az csatlakoztató a következő kéréseket támogatja:

- **SubmitDocumentFiscalDeviceRequest** – ez a kérés dokumentumokat küld a pénzügyi regisztrációs szolgáltatásnak, és visszaküldi a választ.
- **IsReadyFiscalDeviceRequest** – ez a kérés az adóügyi regisztrációs szolgáltatás állapotellenőrzésére használható.
- **InitializeFiscalDeviceRequest** – ez a kérés a pénzügyi regisztrációs szolgáltatás inicializálására használatos.

#### <a name="configuration"></a>Konfiguráció

A konfigurációs fájl a bővítményprojekt **Konfigurációs** mappájában található. A fájl célja, hogy engedélyezze a Commerce Headquarters alkalmazásból konfigurálható pénzügyi csatlakoztató beállításait. A fájlformátum igazodik a pénzügyi integráció konfigurációjának követelményeihez. A következő beállításokat lehet hozzáadni:

- **Végpont címe** – a pénzügyi regisztrációs szolgáltatás URL-címe.
- **Időtúllépés** – az az idő ezredmásodpercben, ahányszor a csatlakoztató választ vár a pénzügyi regisztrációs szolgáltatástól.

### <a name="pos-fiscal-connector-extension-design"></a>POS pénzügyi csatlakoztató bővítményének tervezése

A POS pénzügyi csatlakoztató bővítményének célja, hogy kommunikáljon a POS pénzügyi regisztrációs szolgáltatásával. A HTTPS-protokollt használja kommunikációra.

#### <a name="fiscal-connector-factory"></a>Pénzügyi csatlakoztató gyára

A pénzügyi csatlakoztató gyári leképezi a csatlakoztató **nevét a pénzügyi csatlakoztató megvalósításra, és a Pos.ExtensionConnectorsFiscalConnectorFactory.ts\\\\ fájlban** található. A csatlakoztató nevének meg kell egyeznie a Commerce Headquarters által megadott pénzügyi csatlakoztató nevével.

#### <a name="efr-fiscal-connector"></a>EFR pénzügyi csatlakoztató

Az EFR pénzügyi csatlakoztató a **Pos.ExtensionConnectorsEfrEfrFiscalConnector.ts\\\\\\ fájlban** található. Az IFiscalConnector **felületet** valósítja meg, amely a következő kéréseket támogatja:

- **FiscalRegisterSubmitDocumentClientRequest** – ez a kérés dokumentumokat küld a pénzügyi regisztrációs szolgáltatásnak, és visszaküldi a választ.
- **FiscalRegisterIsReadyClientRequest** – ez a kérés a pénzügyi nyilvántartási szolgáltatás állapotellenőrzésére használható.
- **FiscalRegisterInitializeClientRequest** – ez a kérés a pénzügyi regisztrációs szolgáltatás inicializálására használható.

#### <a name="configuration"></a>Konfiguráció

A konfigurációs fájl a **megoldástárház srcFiscalIntegrationEfrConfigurationsConnectors\\\\\\\\**[Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/) mappájában található. A fájl célja, hogy engedélyezze a Commerce Headquarters alkalmazásból konfigurálható pénzügyi csatlakoztató beállításait. A fájlformátum igazodik a pénzügyi integráció konfigurációjának követelményeihez. A következő beállításokat lehet hozzáadni:

- **Végpont címe** – a pénzügyi regisztrációs szolgáltatás URL-címe.
- **Időtúllépés** – az az idő ezredmásodpercben, ahányszor a csatlakoztató választ vár a pénzügyi regisztrációs szolgáltatástól.
