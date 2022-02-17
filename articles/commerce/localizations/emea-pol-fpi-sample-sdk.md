---
title: Üzembe helyezési irányelvek a lengyelországi adónyomtató-integrációs mintához (örökölt)
description: Ez a témakör útmutatást ad a lengyelországi adónyomtató-integrációs minta telepítéséhez Microsoft Dynamics 365 Commerce Kiskereskedelmi szoftverfejlesztő készlet (SDK).
author: EvgenyPopovMBS
ms.date: 12/20/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2019-3-1
ms.openlocfilehash: 45cae498df8157b9561c54e9859daadcaedd7823
ms.sourcegitcommit: 5cefe7d2a71c6f220190afc3293e33e2b9119685
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/01/2022
ms.locfileid: "8076988"
---
# <a name="deployment-guidelines-for-the-fiscal-printer-integration-sample-for-poland-legacy"></a>Üzembe helyezési irányelvek a lengyelországi adónyomtató-integrációs mintához (örökölt)

[!include[banner](../includes/banner.md)]

Ez a témakör útmutatást ad a lengyelországi adónyomtató-integrációs minta telepítéséhez Microsoft Dynamics 365 Commerce Kiskereskedelmi szoftverfejlesztő készlet (SDK) fejlesztői virtuális gépen (VM) be Microsoft Dynamics Életciklus-szolgáltatások (LCS). Erről a költségvetési integrációs mintáról további információkért lásd: [Pénzügyi nyomtató-integrációs minta Lengyelország számára](emea-pol-fpi-sample.md). 

A lengyelországi fiskális integrációs minta a Retail SDK része. Az SDK telepítésével és használatával kapcsolatos információkért lásd: [Kiskereskedelmi szoftverfejlesztő készlet (SDK) architektúrája](../dev-itpro/retail-sdk/retail-sdk-overview.md). Ez a minta a Commerce futtatókörnyezet bővítményeiből áll (CRT) és a hardver állomás. A minta futtatásához módosítania kell és össze kell építenie a CRT és Hardver állomás projektek. Javasoljuk, hogy módosítatlan kiskereskedelmi SDK-t használjon a témakörben ismertetett módosítások végrehajtásához. Azt is javasoljuk, hogy használjon forrásvezérlő rendszert, mint pl Azure DevOps ahol még nem módosítottak fájlokat.

## <a name="development-environment"></a>Fejlesztői környezet

Kövesse az alábbi lépéseket egy fejlesztői környezet beállításához, amely lehetővé teszi a minta tesztelését és kiterjesztését.

### <a name="commerce-runtime-extension-components"></a>Kereskedelmi futásidejű bővítmény összetevői

A CRT A bővítmény összetevői megtalálhatók a Retail SDK-ban. A következő eljárások végrehajtásához nyissa meg a **CommerceRuntimeSamples.sln** alatti megoldás **RetailSdk\\ SampleExtensions\\ CommerceRuntime**.

1. Találd meg **Runtime.Extensions.DocumentProvider.PosnetSample** projektet, és megépíteni.
2. Ban,-ben **Extensions.DocumentProvider.PosnetSample\\ kuka\\ Debug** mappát, keresse meg a **Contoso.Commerce.Runtime.Extensions.DocumentProvider.PosnetSample.dll** összeállítási fájl.
3. Másolja az összeállítási fájlt a CRT kiterjesztés mappa:

    - **Kereskedelmi mértékegység:** Másolja a fájlt a **\\ kuka\\ ext** mappát az Internet Information Services (IIS) Commerce Scale Unit webhely helye alatt.
    - **Helyi CRT a modern POS-on:** Másolja a fájlt a **\\ ext** mappát a helyi alatt CRT ügyfél bróker helye.

4. Keresse meg a kiterjesztés konfigurációs fájlját CRT:

    - **Kereskedelmi mértékegység:** A fájl neve **commerceruntime.ext.config**, és benne van a **kuka\\ ext** mappát az IIS Commerce Scale Unit webhely helye alatt.
    - **Helyi CRT a modern POS-on:** A fájl neve **CommerceRuntime.MPOSOffline.Ext.config**, és a helyi alatt van CRT ügyfél bróker helye.

5. Regisztrálja a CRT módosítás a kiterjesztés konfigurációs fájljában.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.Extensions.DocumentProvider.PosnetSample" />
    ```

6. Indítsa újra a Commerce szolgáltatást:

    - **Kereskedelmi mértékegység:** Indítsa újra a Kereskedelmi szolgáltatás webhelyét az IIS Managerből.
    - **Ügyfél bróker:** Vége a **dllhost.exe** folyamatot a Feladatkezelőben, majd indítsa újra a Modern POS-t.

### <a name="hardware-station-extension-components"></a>Hardverállomás-bővítési összetevők

A hardverállomás-bővítmény összetevői a kiskereskedelmi SDK-ban találhatók. A következő eljárások végrehajtásához nyissa meg a **HardwareStationSamples.sln** alatti megoldás **RetailSdk\\ SampleExtensions\\ HardwareStation**.

1. Találd meg **HardwareStation.Extension.PosnetThermalFVFiscalPrinterSample** projektet, és megépíteni.
2. Ban,-ben **Extension.Posnet.ThermalFVFiscalPrinterSample\\ kuka\\ Debug** mappát, keresse meg a **Contoso.Commerce.HardwareStation.PosnetThermalFVFiscalPrinterSample.dll** összeállítási fájl.
3. Másolja az összeállítási fájlt egy telepített hardver állomás gépre:

    - **Távoli hardver állomás:** Másolja a fájlt a **kuka** mappát az IIS hardver állomás helye alatt. Másolja a nyomtató-illesztőprogram könyvtárait (**libposcmbth.dll**, **\_ serial.dll**, és **cmbth\_ pl.lng**).

4. Keresse meg a hardverállomás kiterjesztéseinek konfigurációs fájlját. A fájl neve **HardwareStation.Extension.config**:

    - **Távoli hardver állomás:** A fájl az IIS hardver állomás helye alatt található.

5. Adja hozzá a következő sort a **fogalmazás** szakasza a konfigurációs fájlban.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.PosnetThermalFVFiscalPrinterSample" />
    ```

6. Indítsa újra a Hardverállomás szolgáltatást:

    - **Távoli hardver állomás:** Indítsa újra a Hardverállomás webhelyét az IIS-kezelőből.

## <a name="production-environment"></a>Működési környezet

Az előző eljárásban engedélyezte azokat a bővítményeket, amelyek az adóregisztrációs szolgáltatás integrációs mintájának összetevői. Ezenkívül követnie kell ezeket a lépéseket a Commerce összetevőket tartalmazó telepíthető csomagok létrehozásához, és ezeknek a csomagoknak éles környezetben való alkalmazásához.

1. Végezze el a következő módosításokat a csomag konfigurációs fájljaiban a **RetailSdk\\ Eszközök** mappa:

    - Ban,-ben **commerceruntime.ext.config** és **CommerceRuntime.MPOSOffline.Ext.config** konfigurációs fájlokat, adja hozzá a következő sort a **fogalmazás** szakasz.

        ``` xml
        <add source="assembly" value="Contoso.Commerce.Runtime.Extensions.DocumentProvider.PosnetSample" />
        ```

    - Ban,-ben **HardwareStation.Extension.config** konfigurációs fájlt, adja hozzá a következő sort a **fogalmazás** szakasz.

        ``` xml
        <add source="assembly" value="Contoso.Commerce.HardwareStation.PosnetThermalFVFiscalPrinterSample" />
        ```

1. Végezze el a következő módosításokat a **Testreszabás.beállítások** alatti csomag testreszabási konfigurációs fájlja **BuildTools** mappa:

    - Adja hozzá a következő sort a CRT bővítmény a telepíthető csomagokban.

        ``` xml
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.Extensions.DocumentProvider.PosnetSample.dll"/>
        ```

    - Adja hozzá a következő sort a Hardverállomás-bővítménynek a telepíthető csomagokba való felvételéhez.

        ``` xml
        <ISV_HardwareStation_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.HardwareStation.PosnetThermalFVFiscalPrinterSample.dll"/>
        ```

1. Indítsa el az MSBuild parancssort a következőhöz:Visual Studio segédprogramot, és futtassa **msbuild** a Retail SDK mappa alatt telepíthető csomagok létrehozásához.
1. Alkalmazza a csomagokat LCS-n keresztül vagy manuálisan. További információkért lásd [Hozzon létre telepíthető csomagokat](../dev-itpro/retail-sdk/retail-sdk-packaging.md).

## <a name="design-of-extensions"></a>Bővítések tervezése

A lengyelországi fiskális nyomtató-integrációs minta a [fiskális integrációs funkcionalitás](fiscal-integration-for-retail-channel.md). A fiskális integrációs megoldás kialakításával kapcsolatos további információkért lásd a [a fiskális integráció mintatervének áttekintése](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services).

### <a name="commerce-runtime-extension-design"></a>Kereskedelmi futásidejű bővítmény tervezése

Az adódokumentum-szolgáltató bővítmény célja, hogy nyomtató-specifikus dokumentumokat állítson elő, és kezelje a fiskális nyomtatótól érkező válaszokat.

A CRT kiterjesztése az **Runtime.Extensions.DocumentProvider.PosnetSample**. Ez a bővítmény nyomtatóspecifikus parancsokat hoz létre JavaScript Object Notation (JSON) formátumban, amelyeket a POSNET 19-3678-as specifikációja határoz meg.

A fiskális integrációs megoldás kialakításával kapcsolatos további információkért lásd: [Fiskális regisztrációs folyamat és fiskális integrációs minták a fiskális eszközökhöz és szolgáltatásokhoz](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services).

#### <a name="request-handler"></a>Kérelemkezelő

A **DocumentProviderPosnetProtocol** A kérelemkezelő a belépési pontja a dokumentumoknak az adónyomtatóból történő létrehozására irányuló kérelemnek.

A kezelő az **INamedRequestHandler felületről öröklődik**. A **HandlerName** metódus felelős a kezelő nevének visszaadásáért. A kezelő nevének meg kell egyeznie a Kereskedelmi központban megadott összekötő dokumentumszolgáltató nevével.

Az összekötő a következő kéréseket támogatja:

- **GetFiscalDocumentDocumentProviderRequest** – Ez a kérés információt tartalmaz arról, hogy milyen dokumentumot kell létrehozni. Nyomtatóspecifikus dokumentumot ad vissza, amelyet regisztrálni kell az adónyomtatóban.
- **GetSupportedRegistrableEventsDocumentProviderRequest** – Ez a kérés visszaadja az előfizetendő események listáját. Jelenleg a következő események támogatottak: értékesítés, X-jelentés nyomtatása és Z-jelentés nyomtatása.

#### <a name="configuration"></a>Konfiguráció

A konfigurációs fájl a **Konfiguráció** a kiterjesztési projekt mappája. A fájl célja, hogy engedélyezze a dokumentumszolgáltató beállításait a Commerce központjából. A fájlformátum igazodik a pénzügyi integráció konfigurációjának követelményeihez. A következő beállítások kerülnek hozzáadásra:

- Áfakulcsok leképezése
- Fizetőeszköz-típus leképezése
- Letét fizetési típusa

### <a name="hardware-station-extension-design"></a>Hardverállomás-bővítés kialakítása

A fiskális összekötő bővítmény célja a fiskális nyomtatóval való kommunikáció.

A Hardver állomás kiterjesztése a **HardwareStation.Extension.PosnetThermalFVFiscalPrinterSample**. Ez a bővítmény felkéri a POSNET-illesztőprogram funkcióit, hogy küldjenek el parancsokat, amelyeket a CRT bővítmény generál a költségvetési nyomtatónak. Az eszközhibákat is kezeli.

#### <a name="request-handler"></a>Kérelemkezelő

A **FiscalPrinterHandler** kérelemkezelő a kérelem pénzügyi perifériára irányuló kezelésének belépési pontja.

A kezelő az **INamedRequestHandler felületről öröklődik**. A **HandlerName** metódus felelős a kezelő nevének visszaadásáért. A kezelő nevének meg kell egyeznie a Kereskedelmi központban megadott pénzügyi összekötő nevével.

Az összekötő a következő kéréseket támogatja:

- **SubmitDocumentFiscalDeviceRequest** – Ez a kérelem dokumentumokat küld a nyomtatóknak, és visszaadja a válaszát a költségvetési nyomtatóról.
- **IsReadyFiscalDeviceRequest** – Ez a kérés az eszköz állapotfelmérésére szolgál.
- **InitializeFiscalDeviceRequest** – Ez a kérés a nyomtató inicializálásához használatos.

#### <a name="configuration"></a>Konfiguráció

A konfigurációs fájl a **projekt konfigurációs** mappájában található. A fájl célja, hogy engedélyezze az összekötő beállításait a Commerce központjából. A fájlformátum igazodik a pénzügyi integráció konfigurációjának követelményeihez. A következő beállítások kerülnek hozzáadásra:

- **Csatlakozási karakterlánc** – Egy karakterlánc, amely leírja az eszközzel való kapcsolat részleteit az illesztőprogram által támogatott formátumban. További információért tekintse meg a POSNET illesztőprogram dokumentációját.
- **Dátum és idő szinkronizálása** – Egy érték, amely megadja, hogy a nyomtató dátumát és idejét szinkronizálni kell-e a csatlakoztatott hardverállomással.
- **Eszköz időtúllépése** – Az az idő, ezredmásodpercben, ameddig a vezető vár az eszköztől érkező válaszra. További információért tekintse meg a POSNET illesztőprogram dokumentációját.
