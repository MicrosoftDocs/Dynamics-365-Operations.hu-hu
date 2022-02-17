---
title: Üzembe helyezési irányelvek az adóregisztrációs szolgáltatás integrációs mintájához a Cseh Köztársaságban (örökölt)
description: Ez a témakör iránymutatást ad a Cseh Köztársaság költségvetési integrációs mintájának telepítéséhez Microsoft Dynamics 365 Commerce Kiskereskedelmi szoftverfejlesztő készlet (SDK).
author: EvgenyPopovMBS
ms.date: 12/20/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2019-3-1
ms.openlocfilehash: adafde2123afdc793a6ef4edf8fa16b857c55bf8
ms.sourcegitcommit: 5cefe7d2a71c6f220190afc3293e33e2b9119685
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/01/2022
ms.locfileid: "8076936"
---
# <a name="deployment-guidelines-for-the-fiscal-registration-service-integration-sample-for-the-czech-republic-legacy"></a>Üzembe helyezési irányelvek az adóregisztrációs szolgáltatás integrációs mintájához a Cseh Köztársaságban (örökölt)

[!include [banner](../includes/banner.md)]

Ez a témakör iránymutatást ad az adóregisztrációs szolgáltatás integrációs mintájának telepítéséhez a Cseh Köztársaságban Microsoft Dynamics 365 Commerce Kiskereskedelmi szoftverfejlesztő készlet (SDK) fejlesztői virtuális gépen (VM) be Microsoft Dynamics Életciklus-szolgáltatások (LCS). Erről a költségvetési integrációs mintáról további információkért lásd: [Adóügyi regisztrációs szolgáltatás integrációs mintája a Cseh Köztársaságban](emea-cze-fi-sample.md). 

A Cseh Köztársaság fiskális integrációs mintája a Retail SDK része. Az SDK telepítésével és használatával kapcsolatos információkért lásd: [Kiskereskedelmi szoftverfejlesztő készlet (SDK) architektúrája](../dev-itpro/retail-sdk/retail-sdk-overview.md). Ez a minta a Commerce futtatókörnyezet bővítményeiből áll (CRT) és a hardver állomás. A minta futtatásához módosítania kell és össze kell építenie a CRT és Hardver állomás projektek. Javasoljuk, hogy módosítatlan kiskereskedelmi SDK-t használjon a témakörben ismertetett módosítások végrehajtásához. Azt is javasoljuk, hogy használjon forrásvezérlő rendszert, mint pl Azure DevOps ahol még nem módosítottak fájlokat.

## <a name="development-environment"></a>Fejlesztői környezet

Kövesse az alábbi lépéseket egy fejlesztői környezet beállításához, amely lehetővé teszi a minta tesztelését és kiterjesztését.

### <a name="enable-commerce-runtime-extensions"></a>Engedélyezze a Commerce futásidejű bővítményeket

A CRT bővítőelemek szerepelnek a CRT minták. A következő eljárások végrehajtásához nyissa meg a **CommerceRuntimeSamples.sln** alatti megoldás **RetailSdk\\ SampleExtensions\\ CommerceRuntime**.

#### <a name="documentproviderefrsample-component"></a>DocumentProvider.EFRSample komponens

1. Találd meg **Runtime.Extensions.DocumentProvider.EFRSample** projektet, és megépíteni.
2. Ban,-ben **Runtime.Extensions.DocumentProvider.EFRSample\\ kuka\\ Debug** mappát, keresse meg a **Contoso.Commerce.Runtime.DocumentProvider.EFRSample.dll** összeállítási fájl.
3. Másolja az összeállítási fájlt a CRT kiterjesztések mappa:

    - **Kereskedelmi mértékegység:** Másolja a fájlt a **\\ kuka\\ ext** mappát az Internet Information Services (IIS) Commerce Scale Unit webhely helye alatt.
    - **Helyi CRT a modern POS-on:** Másolja a fájlt a **\\ ext** mappát a helyi alatt CRT ügyfél bróker helye.

4. Keresse meg a kiterjesztés konfigurációs fájlját CRT:

    - **Kereskedelmi mértékegység:** A fájl neve **commerceruntime.ext.config**, és benne van a **kuka\\ ext** mappát az IIS Commerce Scale Unit webhely helye alatt.
    - **Helyi CRT a modern POS-on:** A fájl neve **CommerceRuntime.MPOSOffline.Ext.config**, és a helyi alatt van CRT ügyfél bróker helye.

5. Regisztrálja a CRT módosítás a kiterjesztés konfigurációs fájljában.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.EFRSample" />
    ```

#### <a name="documentproviderdatamodelefr-component"></a>DocumentProvider.DataModelEFR komponens

1. Találd meg **Runtime.Extensions.DocumentProvider.DataModelEFR** projektet, és megépíteni.
2. Ban,-ben **Runtime.Extensions.DocumentProvider.DataModelEFR\\ kuka\\ Debug** mappát, keresse meg a **Contoso.Commerce.Runtime.DocumentProvider.DataModelEFR.dll** összeállítási fájl.
3. Másolja az összeállítási fájlt a CRT kiterjesztések mappa:

    - **Kereskedelmi mértékegység:** Másolja a fájlt a **\\ kuka\\ ext** mappát az IIS Commerce Scale Unit webhely helye alatt.
    - **Helyi CRT a modern POS-on:** Másolja a fájlt a **\\ ext** mappát a helyi alatt CRT ügyfél bróker helye.

4. Keresse meg a kiterjesztés konfigurációs fájlját CRT:

    - **Kereskedelmi mértékegység:** A fájl neve **commerceruntime.ext.config**, és benne van a **kuka\\ ext** mappát az IIS Commerce Scale Unit webhely helye alatt.
    - **Helyi CRT a modern POS-on:** A fájl neve **CommerceRuntime.MPOSOffline.Ext.config**, és a helyi alatt van CRT ügyfél bróker helye.

5. Regisztrálja a CRT módosítás a kiterjesztés konfigurációs fájljában.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.DataModelEFR" />
    ```

#### <a name="extension-configuration-file"></a>Kiterjesztés konfigurációs fájl

1. Keresse meg a kiterjesztés konfigurációs fájlját CRT:

    - **Kereskedelmi mértékegység:** A fájl neve **commerceruntime.ext.config**, és benne van a **kuka\\ ext** mappát az IIS Commerce Scale Unit webhely helye alatt.
    - **Helyi CRT a modern POS-on:** A fájl neve **CommerceRuntime.MPOSOffline.Ext.config**, és a helyi alatt van CRT ügyfél bróker helye.

2. Regisztrálja a CRT módosítás a kiterjesztés konfigurációs fájljában.

    ``` xml
    <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.ReceiptsCzechia" />
    ```

### <a name="enable-hardware-station-extensions"></a>Hardverállomás-bővítmények engedélyezése

A hardverállomás-bővítmény összetevői a hardverállomás-mintákban találhatók. A következő eljárások végrehajtásához nyissa meg a **HardwareStationSamples.sln** alatti megoldás **RetailSdk\\ SampleExtensions\\ HardwareStation**.

#### <a name="efrsample-component"></a>EFRSminta komponens

1. Találd meg **HardwareStation.Extension.EFRSample** projektet, és megépíteni.
2. Ban,-ben **Kiterjesztés.EFRSminta\\ kuka\\ Debug** mappában keresse meg a következő összeállítási fájlokat:

    - Contoso.Commerce.HardwareStation.EFRSample.dll
    - Contoso.Commerce.Runtime.DocumentProvider.DataModelEFR.dll

3. Másolja az összeállítási fájlokat a Hardware station extensions mappába:

    - **Megosztott hardverállomás:** Másolja a fájlokat a **kuka** mappát az IIS hardver állomás helye alatt.
    - **Dedikált hardverállomás a Modern POS-en:** Másolja a fájlokat a Modern POS kliens közvetítő helyére.

4. Keresse meg a hardverállomás kiterjesztéseinek konfigurációs fájlját. A fájl neve **HardwareStation.Extension.config**.

    - **Megosztott hardverállomás:** A fájl az IIS hardver állomás helye alatt található.
    - **Dedikált hardverállomás a Modern POS-en:** A fájl a Modern POS kliens bróker helye alatt található.

5. Adja hozzá a következő sort a **fogalmazás** szakasza a konfigurációs fájlban.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.EFRSample.dll" />
    ```

### <a name="production-environment"></a>Működési környezet

Az előző eljárás lehetővé teszi a kiterjesztéseket, amelyek az adóregisztrációs szolgáltatás integrációs mintájának összetevői. Ezenkívül követnie kell ezeket a lépéseket a Commerce összetevőket tartalmazó telepíthető csomagok létrehozásához, és ezeknek a csomagoknak éles környezetben való alkalmazásához.

1. Végezze el a következő módosításokat a csomag konfigurációs fájljaiban a **RetailSdk\\ Eszközök** mappát.

    - Ban,-ben **commerceruntime.ext.config** és **CommerceRuntime.MPOSOffline.Ext.config** konfigurációs fájlokat, adja hozzá a következő sorokat a **fogalmazás** szakasz.

        ``` xml
        <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.EFRSample" />
        <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.DataModelEFR" />
        <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.ReceiptsCzechia" />
        ```

    - Ban,-ben **HardwareStation.Extension.config** konfigurációs fájlt, adja hozzá a következő sort a **fogalmazás** szakasz.

        ``` xml
        <add source="assembly" value="Contoso.Commerce.HardwareStation.EFRSample" />
        ```

2. Végezze el a következő módosításokat a **Testreszabás.beállítások** alatti csomag testreszabási konfigurációs fájlja **BuildTools** mappát.

    - Adja hozzá a következő sorokat a CRT bővítményeket a telepíthető csomagokban.

        ``` xml
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.DocumentProvider.EFRSample.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.DocumentProvider.DataModelEFR.dll" />
        <ISV_HardwareStation_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.DocumentProvider.DataModelEFR.dll" />
        ```

    - Adja hozzá a következő sort a Hardverállomás-bővítménynek a telepíthető csomagokba való felvételéhez.

        ``` xml
        <ISV_HardwareStation_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.HardwareStation.EFRSample" />
        ```

3. Indítsa el az MSBuild parancssort a következőhöz:Visual Studio segédprogramot, és futtassa **msbuild** a Retail SDK mappa alatt telepíthető csomagok létrehozásához.
4. Alkalmazza a csomagokat LCS-n keresztül vagy manuálisan. További információkért lásd [Hozzon létre telepíthető csomagokat](../dev-itpro/retail-sdk/retail-sdk-packaging.md).
5. Végezze el az összes szükséges beállítási feladatot, amelyek a leírásban szerepelnek [A Commerce beállítása a Cseh Köztársaság számára](emea-cze-fi-sample.md#set-up-commerce-for-the-czech-republic).

## <a name="design-of-extensions"></a>Bővítések tervezése

A Cseh Köztársaság fiskális regisztrációs szolgáltatás integrációs mintája a [fiskális integrációs funkcionalitás](fiscal-integration-for-retail-channel.md). A fiskális integrációs megoldás kialakításával kapcsolatos további információkért lásd a [a fiskális integráció mintatervének áttekintése](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services).

### <a name="commerce-runtime-extension-design"></a>Kereskedelmi futásidejű bővítmény tervezése

Az adódokumentum-szolgáltató bővítmény célja szolgáltatás-specifikus dokumentumok előállítása és válaszok kezelése az adónyilvántartási szolgáltatástól.

A CRT kiterjesztése az **Runtime.Extensions.DocumentProvider.EFRSample**.

#### <a name="request-handler"></a>Kérelemkezelő

Egyetlen van **DocumentProviderEFRFiscalCZE** kéréskezelő a dokumentumszolgáltató számára. Az adóügyi nyilvántartási szolgáltatás adódokumentumainak létrehozására szolgál.

Ezt a kezelőt a **INamedRequestHandler** felület. A **HandlerName** metódus felelős a kezelő nevének visszaadásáért. A kezelő nevének meg kell egyeznie a Kereskedelmi központban megadott összekötő dokumentumszolgáltató nevével.

Az összekötő a következő kéréseket támogatja:

- **GetFiscalDocumentDocumentProviderRequest** – Ez a kérés információt tartalmaz arról, hogy milyen dokumentumot kell létrehozni. Egy szolgáltatásspecifikus dokumentumot ad vissza, amelyet regisztrálni kell a pénzügyi regisztrációs szolgáltatásban.
- **GetSupportedRegistrableEventsDocumentProviderRequest** – Ez a kérés visszaadja az előfizetendő események listáját. Jelenleg a következő események támogatottak: értékesítés, ügyfélszámla befizetés és vásárlói rendelés befizetés.
- **GetFiscalRegisterResponseToSaveDocumentProviderRequest** – Ez a kérelem a pénzügyi regisztrációs szolgáltatás válaszát adja vissza. Ez a válasz szerializálva karakterláncot képez, hogy készen álljon a mentésre.

#### <a name="configuration"></a>Konfiguráció

A **DocumentProviderFiscalEFRSampleCseh** konfigurációs fájl található a **Konfiguráció** a kiterjesztési projekt mappája. Ennek a fájlnak az a célja, hogy lehetővé tegye a dokumentumszolgáltató beállításait a Commerce központjában. A fájlformátum igazodik a pénzügyi integráció konfigurációjának követelményeihez. A következő beállítások kerülnek hozzáadásra:

- Áfakulcsok leképezése
- Alapértelmezett áfacsoport
- Befizetés ÁFA csoport

### <a name="hardware-station-extension-design"></a>Hardverállomás-bővítés kialakítása

A költségvetési összekötő bővítmény célja a pénzügyi regisztrációs szolgáltatással való kommunikáció.

A hardverállomás bővítménye **HardwareStation.Extension.EFRSample**. A hardverállomás-bővítmény a HTTP protokollt használja az olyan dokumentumok benyújtására, amelyek a CRT kiterjesztést generál az adóregisztrációs szolgáltatáshoz. Kezeli továbbá a pénzügyi regisztrációs szolgáltatástól kapott válaszokat.

#### <a name="request-handler"></a>Kérelemkezelő

Az **EFRHandler** kérelemkezelője a belépési pont a pénzügyi regisztrációs szolgáltatáshoz benyújtott kérelmek kezeléséhez.

A kezelő az **INamedRequestHandler felületről öröklődik**. A **HandlerName** metódus felelős a kezelő nevének visszaadásáért. A kezelő nevének meg kell egyeznie a Kereskedelmi központban megadott pénzügyi összekötő nevével.

Az összekötő a következő kéréseket támogatja:

- **SubmitDocumentFiscalDeviceRequest** – Ez a kérelem dokumentumokat küld a pénzügyi regisztrációs szolgálatnak, és visszaküldi a választ.
- **IsReadyFiscalDeviceRequest** – Ez a kérés a pénzügyi regisztrációs szolgáltatás állapotfelmérésére szolgál.
- **InitializeFiscalDeviceRequest** – Ez a kérés a pénzügyi regisztrációs szolgáltatás inicializálására szolgál.

#### <a name="configuration"></a>Konfiguráció

A konfigurációs fájl a **projekt konfigurációs** mappájában található. A fájl célja, hogy engedélyezze a pénzügyi összekötő beállításait a Commerce központjából. A fájlformátum igazodik a pénzügyi integráció konfigurációjának követelményeihez. A következő beállítások kerülnek hozzáadásra:

- **Végpont címe** – A pénzügyi regisztrációs szolgáltatás URL-címe.
- **Időtúllépés** – Az az idő, ezredmásodpercben, ahány idő alatt a járművezető megvárja a pénzügyi regisztrációs szolgáltatás válaszát.
