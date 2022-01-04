---
title: A Cseh Köztársaságra vonatkozó pénzügyi regisztrációs szolgáltatás integrációs mintája telepítési irányelvei (legacy)
description: Ez a témakör a Retail szoftverfejlesztői csomagból (SDK) a Csehországba tartozó pénzügyi integrációs minta telepítésével kapcsolatban Microsoft Dynamics 365 Commerce nyújt tájékoztatást.
author: EvgenyPopovMBS
ms.date: 12/20/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2019-3-1
ms.openlocfilehash: 18126f53dc314eca3e874e914346b860d7138109
ms.sourcegitcommit: 0d2de52e12fdb9928556d37a4813a67b303695dc
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/21/2021
ms.locfileid: "7945014"
---
# <a name="deployment-guidelines-for-the-fiscal-registration-service-integration-sample-for-the-czech-republic-legacy"></a>A Cseh Köztársaságra vonatkozó pénzügyi regisztrációs szolgáltatás integrációs mintája telepítési irányelvei (legacy)

[!include [banner](../includes/banner.md)]

Ez a témakör irányelveket tartalmaz a Cseh Köztársaság pénzügyi nyilvántartási szolgáltatásintegrációs mintának a Retail szoftverfejlesztői csomagból (SDK) való telepítéséhez Microsoft Dynamics 365 Commerce a Lifecycle Services (LCS) egy fejlesztői virtuális gépére Microsoft Dynamics (VM). A pénzügyi integrációs mintával kapcsolatos további tudnivalókat lásd a Cseh Köztársaság Pénzügyi [nyilvántartási szolgáltatás integrációs mintája oldalon](emea-cze-fi-sample.md). 

A Cseh Köztársaság pénzügyi integrációs minta része a Retail SDK csomagnak. Az SDK telepítésével és használatával kapcsolatos tudnivalókat lásd a [Retail szoftverfejlesztői csomag (SDK) architektúráját](../dev-itpro/retail-sdk/retail-sdk-overview.md). Ez a minta a Commerce runtime () és a CRT hardverállomás bővítményeiből áll. A minta futtatásához módosítania és fel kell építenie a és a CRT hardverállomás-projekteket. Javasoljuk, hogy egy nem módosított Retail SDK készlet használatával tegye meg az ebben a témakörben leírt változtatásokat. Javasoljuk továbbá, hogy forrásvezérlő rendszert használjon, például olyanokat, ahol a Azure DevOps fájlok még nem módosultak.

## <a name="development-environment"></a>Fejlesztői környezet

A következő lépések szerint állíthatja be a fejlesztői környezetet, hogy tesztelni és ki tudja terjeszteni a mintát.

### <a name="enable-commerce-runtime-extensions"></a>Commerce futásidejű bővítmények engedélyezése

A CRT kiterjesztési összetevők a mintában CRT vannak. A következő eljárások befejezéséhez nyissa meg a **CommerceRuntimeSamples.sln megoldást** a **RetailSdk \\ SampleExtensions \\ CommerceRuntime** alatt.

#### <a name="documentproviderefrsample-component"></a>DocumentProvider.EFRSample összetevő

1. A **Runtime.Extensions.DocumentProvider.EFRSample projekt megkeresása** és összeállítása.
2. A **Runtime.Extensions.DocumentProvider.EFRSample bin hibakeresési mappában keresse meg a \\\\** **Contoso.Commerce.Runtime.DocumentProvider.EFRSample.dll** szerelvényfájlt.
3. A szerelvényfájl másolása CRT a bővítmények mappájába:

    - **Commerce Scale Unit: A fájl másolása az Internet Information Services (IIS) Commerce Scale Unit webhelyének bin** **\\\\** ext mappájába.
    - **Helyi a Modern POS terminálon: Másolja a fájlt a helyi ügyfélügynök helye alatti CRT** **\\ ext** CRT mappába.

4. A következő bővítmény-konfigurációs fájl CRT megkeresve:

    - **Commerce Scale Unit: A fájl neve** **commerceruntime.ext.config, és az IIS Commerce Scale Unit webhely bin** **\\ ext** mappájában található.
    - **Helyi a Modern POS terminálon: A fájl neve CRT** **CommerceRuntime.MPOSOffline.Ext.config, és a helyi ügyfélügynök** CRT helye alatt található.

5. A változás CRT regisztrálása a kiterjesztés konfigurációs fájljában.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.EFRSample" />
    ```

#### <a name="documentproviderdatamodelefr-component"></a>DocumentProvider.DataModelEFR összetevő

1. Keresse meg és építse fel **a Runtime.Extensions.DocumentProvider.DataModelEFR** projektet.
2. A **Runtime.Extensions.DocumentProvider.DataModelEFR bin hibakeresési mappában keresse meg a \\\\** **Contoso.Commerce.Runtime.DocumentProvider.DataModelEFR.dll** szerelvényfájlt.
3. A szerelvényfájl másolása CRT a bővítmények mappájába:

    - **Commerce Scale Unit: A fájl másolása az IIS Commerce Scale Unit webhely bin** **\\\\ ext** mappájába.
    - **Helyi a Modern POS terminálon: Másolja a fájlt a helyi ügyfélügynök helye alatti CRT** **\\ ext** CRT mappába.

4. A következő bővítmény-konfigurációs fájl CRT megkeresve:

    - **Commerce Scale Unit: A fájl neve** **commerceruntime.ext.config, és az IIS Commerce Scale Unit webhely bin** **\\ ext** mappájában található.
    - **Helyi a Modern POS terminálon: A fájl neve CRT** **CommerceRuntime.MPOSOffline.Ext.config, és a helyi ügyfélügynök** CRT helye alatt található.

5. A változás CRT regisztrálása a kiterjesztés konfigurációs fájljában.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.DataModelEFR" />
    ```

#### <a name="extension-configuration-file"></a>Kiterjesztés konfigurációs fájlja

1. A következő bővítmény-konfigurációs fájl CRT megkeresve:

    - **Commerce Scale Unit: A fájl neve** **commerceruntime.ext.config, és az IIS Commerce Scale Unit webhely bin** **\\ ext** mappájában található.
    - **Helyi a Modern POS terminálon: A fájl neve CRT** **CommerceRuntime.MPOSOffline.Ext.config, és a helyi ügyfélügynök** CRT helye alatt található.

2. A változás CRT regisztrálása a kiterjesztés konfigurációs fájljában.

    ``` xml
    <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.ReceiptsCzechia" />
    ```

### <a name="enable-hardware-station-extensions"></a>Hardverállomás-bővítmények engedélyezése

A Hardverállomás bővítmény összetevői a hardverállomás mintáiban szerepelnek. A következő eljárások befejezéséhez nyissa meg a **HardwareStationSamples.sln megoldást** a **RetailSdk \\ SampleExtensions \\ HardwareStation** eszközben.

#### <a name="efrsample-component"></a>EFRSample összetevő

1. Keresse meg és építse ki **a HardwareStation.Extension.EFRSample** projektet.
2. Az **Extension.EFRSample bin hibakeresési mappában \\ keresse meg a következő \\** szerelvényfájlokat:

    - Contoso.Commerce.HardwareStation.EFRSample.dll
    - Contoso.Commerce.Runtime.DocumentProvider.DataModelEFR.dll

3. A szerelvényfájlok másolása a hardverállomás bővítmények mappájába:

    - **Megosztott hardverállomás: A fájlok másolása az IIS hardverállomás webhelyének** **bin** mappájába.
    - **Külön hardverállomás a Modern POS terminálon: A fájlok** másolása a Modern POS ügyfélügynöki helyére.

4. A hardverállomás bővítményének konfigurációs fájlja. A fájl neve **HardwareStation.Extension.config.**

    - **Megosztott hardverállomás: A fájl** az IIS hardverállomás helye alatt található.
    - **A Modern POS külön hardverállomása: A fájl a** Modern POS ügyfélügynök helye alatt található.

5. Adja hozzá a következő sort a konfigurációs **fájl** összeállítási szakaszhoz.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.EFRSample.dll" />
    ```

### <a name="production-environment"></a>Működési környezet

Az előző eljárás lehetővé teszi a pénzügyi nyilvántartási szolgáltatás integrációs mintája által tartalmazott bővítményeket. Ezenkívül ezeket a lépéseket kell követnie ahhoz, hogy commerce összetevőket tartalmazó telepíthető csomagokat hozzon létre, és ezeket a csomagokat éles környezetben alkalmazza.

1. Tegye a következő módosításokat a RetailSdk Assets mappa csomagkonfigurációs **\\** fájljaiban.

    - A **Commerceruntime.ext.config és** **a CommerceRuntime.MPOSOffline.Ext.config konfigurációs fájlokban adja hozzá a következő sorokat az** **összeállítási** szakaszhoz.

        ``` xml
        <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.EFRSample" />
        <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.DataModelEFR" />
        <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.ReceiptsCzechia" />
        ```

    - A HardwareStation.Extension.config konfigurációs fájlban adja hozzá a következő sort **az** **összeállítási** szakaszhoz.

        ``` xml
        <add source="assembly" value="Contoso.Commerce.HardwareStation.EFRSample" />
        ```

2. Tegye a következő módosításokat a Testreszabás.beállítások csomag testreszabása **konfigurációs** fájlban a **BuildTools** mappában.

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

3. Indítsa el az MSBuild parancssort a segédprogrammal, és futtassa az msbuild csomagot a Retail SDK mappában a telepíthető Visual Studio **csomagok** létrehozásához.
4. A csomagok alkalmazása LCS-en keresztül vagy manuálisan. A további tudnivalókat lásd [a Telepíthető csomagok](../dev-itpro/retail-sdk/retail-sdk-packaging.md) létrehozása.
5. Töltse ki a Szükséges beállítási feladatokat, amelyek a Set up Commerce for The Csehországban le [vannak](emea-cze-fi-sample.md#set-up-commerce-for-the-czech-republic) írva.

## <a name="design-of-extensions"></a>Bővítmények tervezése

A Cseh Köztársaság pénzügyi nyilvántartási szolgáltatásintegrációs mintája a pénzügyi [integrációs funkciókon](fiscal-integration-for-retail-channel.md) alapul. A pénzügyi integrációs megoldás megtervezésével kapcsolatos további tudnivalókat lásd a pénzügyi integrációs [mintaterv](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices) áttekintésében.

### <a name="commerce-runtime-extension-design"></a>Commerce runtime bővítmény tervezése

A kiterjesztés célja, amely egy pénzügyi bizonylat szolgáltatója, a szolgáltatásspecifikus dokumentumok generálása és a pénzügyi nyilvántartási szolgáltatás válaszának kezelnie kell.

A CRT kiterjesztés **a Runtime.Extensions.DocumentProvider.EFRSample.**

#### <a name="request-handler"></a>Kérelemkezelő

A dokumentumszolgáltatóhoz egyetlen **DocumentProviderEFRFiscalIUSE** kérelemkezelő van. A pénzügyi nyilvántartási szolgáltatás pénzügyi bizonylatai generálják.

Ez a kezelő az **INamedRequestHandler felületről** öröklődik. A HandlerName metódus felelős a kezelő nevének **visszaküldéséért**. A kezelő nevének meg kell egyeznie a Commerce Headquarters szolgáltatásban megadott csatlakoztató dokumentumszolgáltató nevével.

Az csatlakoztató a következő kéréseket támogatja:

- **GetFiscalDocumentDocumentProviderRequest – ez a kérés tartalmazza a létrehozandó** dokumentum adatait. Olyan szolgáltatásspecifikus dokumentumot ad vissza, amely regisztrálva kell lennie a pénzügyi regisztrációs szolgáltatásban.
- **GetSupportedRegistrableEventsDocumentProviderRequest – ez a kérés a regisztrált események listáját adja** eredményül. Jelenleg a következő események támogatottak: értékesítés, vevői számlabetétek és vevői rendelési betétek.
- **GetFiscalRegisterResponseToSaveDocumentProviderRequest – ez a kérés a pénzügyi regisztrációs szolgáltatás válaszát** adja eredményül. A válasz egy karakterlánc formájában van szerializálva, hogy készen legyen a mentésre.

#### <a name="configuration"></a>Konfiguráció

A **DocumentProviderFiscalEFRSample Egy konfigurációs fájl a bővítményprojekt Konfigurációs** **mappájában** található. A fájl célja, hogy lehetővé tegye a dokumentumszolgáltató Commerce Headquarters rendszerből származó konfigurálásának beállításait. A fájlformátum igazodik a pénzügyi integráció konfigurációjának követelményeihez. A következő beállításokat lehet hozzáadni:

- Áfakulcsok leképezése
- Alapértelmezett áfacsoport
- Letét áfacsoportja

### <a name="hardware-station-extension-design"></a>Hardverállomás bővítményének tervezése

A pénzügyi csatlakoztatóként használt bővítmény célja a pénzügyi regisztrációs szolgáltatással való kommunikáció.

A Hardverállomás kiterjesztése **HardwareStation.Extension.EFRSample.** A hardverállomás bővítménye a HTTP protokollal küldheti el a kiterjesztés által a pénzügyi regisztrációs szolgáltatásnak CRT generált dokumentumokat. Kezeli a pénzügyi regisztrációs szolgáltatástól kapott válaszokat is.

#### <a name="request-handler"></a>Kérelemkezelő

Az **EFRHandler kérelemkezelő a pénzügyi regisztrációs szolgáltatás kérésének kezelésére** használt belépési pont.

A kezelő az **INamedRequestHandler felületről** öröklődik. A HandlerName metódus felelős a kezelő nevének **visszaküldéséért**. A kezelő nevének meg kell egyeznie a Commerce Headquartersban megadott pénzügyi csatlakoztató nevével.

Az csatlakoztató a következő kéréseket támogatja:

- **SubmitDocumentFiscalDeviceRequest – ez a kérés dokumentumokat küld a pénzügyi regisztrációs szolgáltatásnak, és** visszaküldi a választ.
- **IsReadyFiscalDeviceRequest – ez a kérés az adóügyi regisztrációs szolgáltatás** állapotellenőrzésére használható.
- **InitializeFiscalDeviceRequest – ez a kérés** a pénzügyi regisztrációs szolgáltatás inicializálására használatos.

#### <a name="configuration"></a>Konfiguráció

A konfigurációs fájl a bővítményprojekt **Konfigurációs** mappájában található. A fájl célja, hogy engedélyezze a Commerce Headquarters alkalmazásból konfigurálható pénzügyi csatlakoztató beállításait. A fájlformátum igazodik a pénzügyi integráció konfigurációjának követelményeihez. A következő beállításokat lehet hozzáadni:

- **Végpont címe** – a pénzügyi regisztrációs szolgáltatás URL-címe.
- **Időtúllépés – az az idő ezredmásodpercben, ahányszor a vezető választ vár a pénzügyi regisztrációs** szolgáltatástól.
