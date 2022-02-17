---
title: Üzembe helyezési irányelvek a vezérlőegység-integrációs mintához Svédországban (örökölt)
description: Ez a témakör útmutatást ad a vezérlőegység-integrációs mintának Svédország számára a Retail SDK-ból történő telepítéséhez
author: EvgenyPopovMBS
ms.date: 12/20/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2019-3-1
ms.openlocfilehash: b8d60f32d986dec6bb26d78ebdfe8cee3a6b688a
ms.sourcegitcommit: 5cefe7d2a71c6f220190afc3293e33e2b9119685
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/01/2022
ms.locfileid: "8077038"
---
# <a name="deployment-guidelines-for-the-control-unit-integration-sample-for-sweden-legacy"></a>Üzembe helyezési irányelvek a vezérlőegység-integrációs mintához Svédországban (örökölt)

[!include [banner](../includes/banner.md)]

Ez a témakör útmutatást ad a kiskereskedelmi szoftverfejlesztő készletből (SDK) származó vezérlőegység-integrációs mintának Svédország számára történő telepítéséhez egy fejlesztői virtuális gépen (VM)Microsoft Dynamics Életciklus-szolgáltatások (LCS). Erről a költségvetési integrációs mintáról további információkért lásd: [Vezérlőegység-integrációs minta Svédország számára](emea-swe-fi-sample.md). 

A svédországi fiskális integrációs minta a Retail SDK része. Az SDK telepítésével és használatával kapcsolatos információkért lásd: [Kiskereskedelmi szoftverfejlesztő készlet (SDK) architektúrája](../dev-itpro/retail-sdk/retail-sdk-overview.md). Ez a minta a Commerce futtatókörnyezet bővítményeiből áll (CRT), Hardverállomás és értékesítési pont (POS). A minta futtatásához módosítania kell és össze kell építenie a CRT, Hardverállomás és POS projektek. Javasoljuk, hogy módosítatlan kiskereskedelmi SDK-t használjon a témakörben ismertetett módosítások végrehajtásához. Azt is javasoljuk, hogy használjon forrásvezérlő rendszert, mint pl Azure DevOps ahol még nem módosítottak fájlokat.

## <a name="development-environment"></a>Fejlesztői környezet

Kövesse az alábbi lépéseket egy fejlesztői környezet beállításához, amely lehetővé teszi a minta tesztelését és kiterjesztését.

### <a name="enable-crt-extensions"></a>Engedélyezze CRT kiterjesztések

A CRT bővítőelemek szerepelnek a CRT minták. A következő eljárások végrehajtásához nyissa meg a **CommerceRuntimeSamples.sln** alatti megoldás **RetailSdk\\ SampleExtensions\\ CommerceRuntime**.

#### <a name="documentprovidercleancashsample-component"></a>DocumentProvider.CleanCashSample komponens

1. Találd meg **Runtime.Extensions.DocumentProvider.CleanCashSample** projektet, és megépíteni.
2. Ban,-ben **Runtime.Extensions.DocumentProvider.CleanCashSample\\ kuka\\ Debug** mappát, keresse meg a **Contoso.Commerce.Runtime.DocumentProvider.CleanCashSample.dll** összeállítási fájl.
3. Másolja az összeállítási fájlt a CRT kiterjesztések mappa:

    - **Kereskedelmi mértékegység:** Másolja a fájlt a **\\ kuka\\ ext** mappát az Internet Information Services (IIS) Commerce Scale Unit webhely helye alatt.
    - **Helyi CRT a modern POS-on:** Másolja a fájlt a **\\ ext** mappát a helyi alatt CRT ügyfél bróker helye.

4. Keresse meg a kiterjesztés konfigurációs fájlját CRT:

    - **Kereskedelmi mértékegység:** A fájl neve **commerceruntime.ext.config**, és benne van a **kuka\\ ext** mappát az IIS Commerce Scale Unit webhely helye alatt.
    - **Helyi CRT a modern POS-on:** A fájl neve **CommerceRuntime.MPOSOffline.Ext.config**, és a helyi alatt van CRT ügyfél bróker helye.

5. Regisztrálja a CRT módosítás a kiterjesztés konfigurációs fájljában.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.CleanCashSample" />
    ```

#### <a name="extension-configuration-file"></a>Kiterjesztés konfigurációs fájl

1. Keresse meg a kiterjesztés konfigurációs fájlját CRT:

    - **Kereskedelmi mértékegység:** A fájl neve **commerceruntime.ext.config**, és benne van a **kuka\\ ext** mappát az IIS Commerce Scale Unit webhely helye alatt.
    - **Helyi CRT a modern POS-on:** A fájl neve **CommerceRuntime.MPOSOffline.Ext.config**, és a helyi alatt van CRT ügyfél bróker helye.

2. Regisztrálja a CRT módosítás a kiterjesztés konfigurációs fájljában.

    ``` xml
    <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.ReceiptsSweden" />
    ```

### <a name="enable-hardware-station-extensions"></a>Hardverállomás-bővítmények engedélyezése

A hardverállomás-bővítmény összetevői a hardverállomás-mintákban találhatók. A következő eljárások végrehajtásához nyissa meg a **HardwareStationSamples.sln** alatti megoldás **RetailSdk\\ SampleExtensions\\ HardwareStation**.

#### <a name="cleancash-component"></a>CleanCash komponens

1. Találd meg **HardwareStation.Extension.CleanCashSample** projektet, és megépíteni.
2. Ban,-ben **Extension.CleanCashSample\\ kuka\\ Debug** mappát, keresse meg a **Contoso.Commerce.HardwareStation.CleanCashSample.dll** és **Interop.CleanCash\_ 1\_ 1.dll** összeállítási fájlokat.
3. Másolja az összeállítási fájlokat a Hardware station extensions mappába:

    - **Megosztott hardverállomás:** Másolja a fájlokat a **kuka** mappát az IIS hardver állomás helye alatt.
    - **Dedikált hardverállomás a Modern POS-en:** Másolja a fájlokat a Modern POS kliens közvetítő helyére.

4. Keresse meg a hardverállomás kiterjesztéseinek konfigurációs fájlját. A fájl neve **HardwareStation.Extension.config**.

    - **Megosztott hardverállomás:** A fájl az IIS hardver állomás helye alatt található.
    - **Dedikált hardverállomás a Modern POS-en:** A fájl a Modern POS kliens bróker helye alatt található.

5. Adja hozzá a következő sort a **fogalmazás** szakasza a konfigurációs fájlban.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.CleanCashSample" />
    ```

### <a name="enable-modern-pos-extension-components"></a>Modern POS-bővítmény-összetevők engedélyezése

1. Nyissa meg a **ModernPOS.sln** alatti megoldás **RetailSdk\\ pozíció**, és győződjön meg arról, hogy hibamentesen lefordítható. Ezenkívül győződjön meg arról, hogy a Modern POS-t futtatni tudja Visual Studio segítségével **Fuss** parancs.

    > [!NOTE]
    > A modern POS-t nem szabad testre szabni. Engedélyeznie kell a felhasználói fiókok felügyeletét (UAC), és szükség szerint el kell távolítania a Modern POS korábban telepített példányait.

2. Engedélyezze a betöltendő bővítményeket a következő sorok hozzáadásával a **extensions.json** fájlt.

    ``` json
    {
        "extensionPackages": [
            {
                "baseUrl": "Microsoft/AuditEvent.SE"
            }
        ]
    }
    ```

    > [!NOTE]
    > További információkért, valamint a forráskód-mappák beillesztését és a kiterjesztések betöltésének engedélyezését bemutató mintákért tekintse meg a readme.md fájl utasításait a **Pos.Extensions** projektet.

3. Építse újra a megoldást.
4. Futtassa a Modern POS-t a hibakeresőben, és tesztelje a funkcionalitást.

### <a name="enable-cloud-pos-extension-components"></a>Engedélyezze a Cloud POS bővítmény összetevőit

1. Nyissa meg a **CloudPOS.sln** alatti megoldás **RetailSdk\\ pozíció**, és győződjön meg arról, hogy hibamentesen lefordítható.
2. Engedélyezze a betöltendő bővítményeket a következő sorok hozzáadásával a **extensions.json** fájlt.

    ``` json
    {
        "extensionPackages": [
            {
                "baseUrl": "Microsoft/AuditEvent.SE"
            }
        ]
    }
    ```

    > [!NOTE]
    > További információkért, valamint a forráskód-mappák beillesztését és a kiterjesztések betöltésének engedélyezését bemutató mintákért tekintse meg a readme.md fájl utasításait a **Pos.Extensions** projektet.

3. Építse újra a megoldást.
4. Futtassa a megoldást a segítségével **Fuss** parancsot, és kövesse a Retail SDK kézikönyv lépéseit.

## <a name="production-environment"></a>Működési környezet

Az előző eljárás engedélyezi azokat a bővítményeket, amelyek a vezérlőegység integrációs mintájának összetevői. Ezenkívül követnie kell ezeket a lépéseket a Commerce összetevőket tartalmazó telepíthető csomagok létrehozásához, és ezeknek a csomagoknak éles környezetben való alkalmazásához.

1. Végezze el a következő módosításokat a csomag konfigurációs fájljaiban a **RetailSdk\\ Eszközök** mappa:

    - Ban,-ben **commerceruntime.ext.config** és **CommerceRuntime.MPOSOffline.Ext.config** konfigurációs fájlokat, adja hozzá a következő sorokat a **fogalmazás** szakasz.

        ``` xml
        <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.CleanCashSample" />
        <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.ReceiptsSweden" />
        ```

    - Ban,-ben **HardwareStation.Extension.config** konfigurációs fájlt, adja hozzá a következő sort a **fogalmazás** szakasz.

        ``` xml
        <add source="assembly" value="Contoso.Commerce.HardwareStation.CleanCashSample" />
        ```

2. Végezze el a következő módosításokat a **Testreszabás.beállítások** alatti csomag testreszabási konfigurációs fájlja **BuildTools** mappa:

    - Adja hozzá a következő sort a CRT bővítményeket a telepíthető csomagokban.

        ``` xml
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.DocumentProvider.CleanCashSample.dll" />
        ```

    - Adja hozzá a következő sorokat, hogy a Hardverállomás-bővítményt belefoglalja a telepíthető csomagokba.

        ``` xml
        <ISV_HardwareStation_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.HardwareStation.CleanCashSample.dll" />
        <ISV_HardwareStation_CustomizableFile Include="$(SdkReferencesPath)\Interop.CleanCash_1_1.dll" />
        ```

3. Engedélyezze a POS kiterjesztést a következő sorok hozzáadásával a **extensions.json** alatti fájl **RetailSDK\\ pozíció\\ Kiterjesztések** mappát.

    ``` json
    {
        "extensionPackages": [
            {
            "baseUrl": "Microsoft/AuditEvent.SE"
            }
        ]
    }
    ```

4. Indítsa el az MSBuild parancssort a következőhöz:Visual Studio segédprogramot, és futtassa **msbuild** a Retail SDK mappa alatt telepíthető csomagok létrehozásához.
5. Alkalmazza a csomagokat LCS-n keresztül vagy manuálisan. További információkért lásd [Hozzon létre telepíthető csomagokat](../dev-itpro/retail-sdk/retail-sdk-packaging.md).
6. Végezze el az összes szükséges beállítási feladatot, amelyek a leírásban szerepelnek [A vezérlőegységekkel való integráció beállítása](emea-swe-fi-sample.md#setting-up-the-integration-with-control-units).

## <a name="design-of-the-extensions"></a>A bővítmények tervezése

### <a name="crt-extension-design"></a>CRT bővítmény kialakítása

A fiskális bizonylat-szolgáltató bővítmény célja szolgáltatás-specifikus dokumentumok előállítása és a vezérlőegység válaszainak kezelése.

A CRT kiterjesztése az **Runtime.Extensions.DocumentProvider.CleanCashSample**.

A fiskális integrációs megoldás kialakításával kapcsolatos további információkért lásd: [Fiskális regisztrációs folyamat és fiskális integrációs minták a fiskális eszközökhöz és szolgáltatásokhoz](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services).

#### <a name="request-handler"></a>Kérelemkezelő

Egyetlen van **DocumentProviderCleanCash** kéréskezelő a dokumentumszolgáltató számára. Ez a kezelő a vezérlőegység fiskális dokumentumainak előállítására szolgál.

Ezt a kezelőt a **INamedRequestHandler** felület. A **HandlerName** metódus felelős a kezelő nevének visszaadásáért. A kezelő nevének meg kell egyeznie a Kereskedelmi központban megadott összekötő dokumentumszolgáltató nevével.

Az összekötő a következő kéréseket támogatja:

- **GetFiscalDocumentDocumentProviderRequest** – Ez a kérés információt tartalmaz arról, hogy milyen dokumentumot kell létrehozni. Egy szolgáltatás-specifikus dokumentumot ad vissza, amelyet regisztrálni kell a vezérlőegységben.
- **GetSupportedRegistrableEventsDocumentProviderRequest** – Ez a kérés visszaadja az előfizetendő események listáját. Jelenleg értékesítési események és audit események támogatottak.

#### <a name="configuration"></a>Konfiguráció

A **DocumentProviderFiscalCleanCashSample** konfigurációs fájl a **Konfiguráció** a kiterjesztési projekt mappája. Ennek a fájlnak az a célja, hogy lehetővé tegye a dokumentumszolgáltató beállításait a Commerce központjában. A fájlformátum igazodik a pénzügyi integráció konfigurációjának követelményeihez. A következő beállítások kerülnek hozzáadásra:

- Áfakódok leképezése

### <a name="hardware-station-extension-design"></a>Hardverállomás-bővítés kialakítása

A fiskális összekötő bővítmény célja a vezérlőegységgel való kommunikáció.

A Hardver állomás kiterjesztése a **HardwareStation.Extension.CleanCashSample**. A HTTP protokoll használatával elküldi a CRT bővítmény által létrehozott dokumentumokat a vezérlőegységnek. Kezeli a vezérlőegységtől kapott válaszokat is.

#### <a name="request-handler"></a>Kérelemkezelő

A **CleanCashHandler** kérelemkezelő a vezérlőegységhez intézett kérések kezelésének belépési pontja.

A kezelő az **INamedRequestHandler felületről öröklődik**. A **HandlerName** metódus felelős a kezelő nevének visszaadásáért. A kezelő nevének meg kell egyeznie a Kereskedelmi központban megadott pénzügyi összekötő nevével.

Az összekötő a következő kéréseket támogatja:

- **SubmitDocumentFiscalDeviceRequest** – Ez a kérés dokumentumokat küld a vezérlőegységnek, és választ ad vissza belőle.
- **IsReadyFiscalDeviceRequest** – Ez a kérés a vezérlőegység állapotfelmérésére szolgál.
- **InitializeFiscalDeviceRequest** – Ez a kérés a vezérlőegység inicializálására szolgál.

#### <a name="configuration"></a>Konfiguráció

A konfigurációs fájl a **Konfiguráció** a kiterjesztési projekt mappája. A fájl célja, hogy engedélyezze a pénzügyi összekötő beállításait a Commerce központjából. A fájlformátum igazodik a pénzügyi integráció konfigurációjának követelményeihez. A következő beállítások kerülnek hozzáadásra:

- **Csatlakozási karakterlánc** – A vezérlőegység csatlakozási beállításai.
- **Időtúllépés** – Az az idő, ezredmásodpercben, ameddig a vezető vár a vezérlőegység válaszára.

## <a name="migrating-from-the-earlier-integration-sample"></a>Áttérés a korábbi integrációs mintáról

Ha a korábbit használja [minta POS-integrációhoz vezérlőegységekkel Svédország számára](retail-sdk-control-unit-sample.md), előfordulhat, hogy át kell térnie róla az aktuális integrációs mintára. Ahhoz, hogy a jövőben átvehesse a változást, és időben frissítéseket kapjon a svédországi szolgáltatásokhoz, előfordulhat, hogy frissítenie kell, kisebb kód- és konfigurációmódosításokat kell végrehajtania a megépített bővítményekben, és újra kell építenie a megoldásokat. Nincs szükség jelentős változtatásokra a létrehozott bővítménylogikában. A korábbi integrációs minta és a testreszabásai továbbra is működni fognak, ha nem történik változás az Ön részéről. Ezért megtervezheti, felkészülhet a környezetére, és elvégezheti a felvételt.

### <a name="migration-process"></a>Migrációs folyamat

A korábbi integrációs mintáról a jelenlegi vezérlőegység-integrációs mintára való áttérésnek a fokozatos frissítés koncepcióján kell alapulnia. Más szavakkal, a kereskedelmi központ és a kereskedelmi mérlegegység összes összetevőjét már frissíteni kell, mielőtt elkezdené frissíteni a POS és a Hardver állomás összetevőit.

Az olyan helyzetek elkerülése érdekében, amikor egy eseményt vagy tranzakciót kétszer írnak alá (azaz a korábbi bővítmény és a jelenlegi bővítmény is aláírja), vagy amikor egy eseményt vagy tranzakciót nem lehet aláírni a hiányzó konfiguráció miatt, javasoljuk, hogy kikapcsolja az összes POS és Hardver állomás eszközt, amely a korábbi mintát használja, majd egyidejűleg frissíti azokat. Ezt az egyidejű frissítést például üzletenként, az áruház működési profiljának és a hardverállomás hardverprofiljának frissítésével lehet elvégezni.

A migrációs folyamatnak a következő lépésekből kell állnia.

1. Frissítse a Commerce központ összetevőit.
1. Frissítse a Commerce Scale Unit összetevőit, és engedélyezze az aktuális minta bővítményeit.
1. Győződjön meg arról, hogy az összes offline tranzakció szinkronizálva van az offline funkcióval rendelkező MPOS-eszközökről.
1. Kapcsolja ki az összes olyan eszközt, amely a korábbi minta összetevőit használja.
1. Végezze el az összes szükséges beállítási feladatot, amelyek a leírásban szerepelnek [A vezérlőegységekkel való integráció beállítása](emea-swe-fi-sample.md#setting-up-the-integration-with-control-units).
1. Frissítse a POS és a Hardver állomás összetevőit, tiltsa le a korábbi minta részét képező bővítményeket, és engedélyezze az aktuális minta bővítményeit.

    > [!NOTE]
    > A környezet típusától függően további technikai részleteket találhat az áttelepítési folyamatról mindkét oldalon [Migráció fejlesztési környezetben](#migration-in-a-development-environment) szakasz vagy a [Migráció termelési környezetben](#migration-in-a-production-environment) részben ebben a témában.

### <a name="migration-in-a-development-environment"></a>Migráció fejlesztési környezetben

#### <a name="update-crt"></a>CRT frissítése

1. Találd meg **Runtime.Extensions.DocumentProvider.CleanCashSample** projektet, és megépíteni.
2. Ban,-ben **Runtime.Extensions.DocumentProvider.CleanCashSample\\ kuka\\ Debug** mappát, keresse meg a **Contoso.Commerce.Runtime.DocumentProvider.CleanCashSample.dll** összeállítási fájl.
3. Másolja az összeállítási fájlt a CRT kiterjesztések mappa:

    - **Kereskedelmi mértékegység:** Másolja a fájlt a **\\ kuka\\ ext** mappát az IIS Commerce Scale Unit webhely helye alatt.
    - **Helyi CRT a modern POS-on:** Másolja a fájlt a **\\ ext** mappát a helyi alatt CRT ügyfél bróker helye.

4. Keresse meg a kiterjesztés konfigurációs fájlját CRT:

    - **Kereskedelmi mértékegység:** A fájl neve **CommerceRuntime.ext.config**, és benne van a **kuka\\ ext** mappát az IIS Commerce Scale Unit webhely helye alatt.
    - **Helyi CRT a modern POS-on:** A fájl neve **CommerceRuntime.MPOSOffline.Ext.config**, és benne van a **kuka\\ ext** mappát a helyi alatt CRT ügyfél bróker helye.

    > [!WARNING]
    > Tedd **nem** szerkessze a CommerceRuntime.config és a CommerceRuntime.MPOSOffline.config fájlokat. Ezek a fájlok nem testreszabhatók.

5. Keresse meg és távolítsa el a korábbit CRT kiterjesztést a kiterjesztési konfigurációs fájlból.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.FiscalRegisterReceiptSample" />
    ```

    > [!WARNING]
    > Ne hajtsa végre ezt a lépést mindaddig, amíg nem frissíti az összes ezzel működő POS-eszközt CRT példa.

6. Regisztrálja az aktuális mintát CRT kiterjesztéseket a kiterjesztés konfigurációs fájljában a következő sorok hozzáadásával.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.CleanCashSample" />
    <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.ReceiptsSweden" />
    ```

#### <a name="update-hardware-station"></a>Frissítse a hardver állomást

1. Találd meg **HardwareStation.Extension.CleanCashSample** projektet, és megépíteni.
2. Ban,-ben **Extension.CleanCashSample\\ kuka\\ Debug** mappát, keresse meg a **Contoso.Commerce.HardwareStation.CleanCashSample.dll** és **Interop.CleanCash\_ 1\_ 1.dll** összeállítási fájlokat.
3. Másolja az összeállítási fájlokat a Hardware station extensions mappába:

    - **Megosztott hardverállomás:** Másolja a fájlokat a **kuka** mappát az IIS hardver állomás helye alatt.
    - **Dedikált hardverállomás a Modern POS-en:** Másolja a fájlokat a Modern POS kliens közvetítő helyére.

4. Találd meg **HardwareStation.Extension.config** kiterjesztési konfigurációs fájl:

    - **Távoli hardver állomás:** A fájl az IIS hardver állomás helye alatt található.
    - **Helyi hardverállomás a Modern POS-en:** A fájl a Modern POS kliens bróker helye alatt található.

    > [!WARNING]
    > Tedd **nem** szerkessze a CommerceRuntime.config és a CommerceRuntime.MPOSOffline.config fájlokat. Ezek a fájlok nem testreszabhatók.

5. Keresse meg és távolítsa el a korábbi hardverállomás-kiterjesztést a kiterjesztési konfigurációs fájlból.

    # <a name="retail-73-and-earlier"></a>[Kiskereskedelem 7.3 és korábbi verziók](#tab/retail-7-3)

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.Extension.FiscalRegisterSample" />
    ```

    # <a name="retail-731-and-later"></a>[Kiskereskedelem 7.3.1 és újabb](#tab/retail-7-3-1)

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.Extension.FiscalRegisterSample" />
    ```

    # <a name="retail-100-and-later"></a>[Kiskereskedelem 10.0 és újabb](#tab/retail-10-0)

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.FiscalRegisterSample" />
    ```
    ---

6. Adja hozzá a következő sort a **fogalmazás** szakasza a kiterjesztés konfigurációs fájljában.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.CleanCashSample" />
    ```

#### <a name="update-modern-pos"></a>Frissítse a Modern POS-t

1. Nyissa meg a **CloudPOS.sln** alatti megoldás **RetailSdk\\ pozíció**.
2. Tiltsa le a korábbi POS-bővítményt a következő sorok eltávolításával a **extensions.json** fájlt.

    ``` json
    {
        "baseUrl": "FiscalRegisterSample"
    }
    ```

2. Engedélyezze az aktuális minta POS-kiterjesztést a következő sorok hozzáadásával a **extensions.json** fájlt.

    ``` json
    {
        "extensionPackages": [
            {
                "baseUrl": "Microsoft/AuditEvent.SE"
            }
        ]
    }
    ```

#### <a name="update-cloud-pos"></a>Frissítse a Cloud POS-t

1. Nyissa meg a **ModernPOS.sln** alatti megoldás **RetailSdk\\ pozíció**.
2. Tiltsa le a korábbi POS-bővítményt a következő sorok eltávolításával a **extensions.json** fájlt.

    ``` json
    {
        "baseUrl": "FiscalRegisterSample"
    }
    ```

2. Engedélyezze az aktuális minta POS-kiterjesztést a következő sorok hozzáadásával a **extensions.json** fájlt.

    ``` json
    {
        "extensionPackages": [
            {
                "baseUrl": "Microsoft/AuditEvent.SE"
            }
        ]
    }
    ```

### <a name="migration-in-a-production-environment"></a>Migráció termelési környezetben

#### <a name="update-crt"></a>CRT frissítése

1. Távolítsa el a korábbit CRT kiterjesztés a **CommerceRuntime.ext.config** és **CommerceRuntime.MPOSOffline.Ext.config** alatti konfigurációs fájlok **RetailSdk\\ Eszközök** mappát.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.FiscalRegisterReceiptSample" />
    ```

    > [!WARNING]
    > Ne hajtsa végre ezt a lépést mindaddig, amíg nem frissíti az összes ezzel működő POS-eszközt CRT példa.

2. Engedélyezze az aktuális mintát CRT kiterjesztéseket a következő változtatásokkal a **CommerceRuntime.ext.config** és **CommerceRuntime.MPOSOffline.Ext.config** alatti konfigurációs fájlok **RetailSdk\\ Eszközök** mappát.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.CleanCashSample" />
    <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.ReceiptsSweden" />
    ```

3. Ban,-ben **Testreszabás.beállítások** alatti csomag testreszabási konfigurációs fájlja **BuildTools** mappát, adja hozzá a következő sort az aktuális minta szerepeltetéséhez CRT bővítmény telepíthető csomagokban.

    ``` xml
    <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.DocumentProvider.CleanCashSample.dll" />
    ```

#### <a name="update-hardware-station"></a>Frissítse a hardver állomást

1. Távolítsa el a korábbi hardverállomás-kiterjesztést a **HardwareStation.Extension.config** konfigurációs fájl.

    # <a name="retail-73-and-earlier"></a>[Kiskereskedelem 7.3 és korábbi verziók](#tab/retail-7-3)

    Távolítsa el a következő részt a **HardwareStation.Shared.config** és **HardwareStation.Dedicated.config** konfigurációs fájlok.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.Extension.FiscalRegisterSample" />
    ```

    # <a name="retail-731-and-later"></a>[Kiskereskedelem 7.3.1 és újabb](#tab/retail-7-3-1)

    Távolítsa el a következő részt a **HardwareStation.Extension.config** konfigurációs fájl.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.Extension.FiscalRegisterSample" />
    ```

    # <a name="retail-100-and-later"></a>[Kiskereskedelem 10.0 és újabb](#tab/retail-10-0)

    Távolítsa el a következő részt a **HardwareStation.Extension.config** konfigurációs fájl.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.FiscalRegisterSample" />
    ```
    ---

2. Engedélyezze az aktuális minta Hardverállomás-kiterjesztést a következő sor hozzáadásával a **fogalmazás** szakaszban a **HardwareStation.Extension.config** konfigurációs fájl.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.CleanCashSample" />
    ```

3. Végezze el a következő módosításokat a **Testreszabás.beállítások** alatti csomag testreszabási konfigurációs fájlja **BuildTools** mappa:

    - Távolítsa el a következő sort, hogy kizárja a korábbi hardverállomás-bővítményt a telepíthető csomagokból.

        ``` xml
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.HardwareStation.Extension.FiscalRegisterSample.dll" />
        ```

    - Adja hozzá a következő sorokat az aktuális minta Hardverállomás-bővítménynek a telepíthető csomagokba való belefoglalásához.

        ``` xml
        <ISV_HardwareStation_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.HardwareStation.CleanCashSample.dll" />
        <ISV_HardwareStation_CustomizableFile Include="$(SdkReferencesPath)\Interop.CleanCash_1_1.dll" />
        ```

#### <a name="update-modern-pos"></a>Frissítse a Modern POS-t

1. Nyissa meg a **CloudPOS.sln** megoldás at **RetailSdk\\ pozíció**.
2. A korábbi POS-bővítmény letiltása:

    - Ban,-ben **tsconfig.json** fájlt, adja hozzá a **FiscalRegisterSample** mappát a kizárási listára.
    - Távolítsa el a következő sorokat a **extensions.json** alatti fájl **RetailSDK\\ pozíció\\ Kiterjesztések** mappát.

        ``` json
        {
            "baseUrl": "FiscalRegisterSample"
        }
        ```

3. Engedélyezze az aktuális minta POS-kiterjesztést a következő sorok hozzáadásával a **extensions.json** fájlban a **RetailSDK\\POS\\Extensions** mappa alatt.

    ``` json
    {
        "extensionPackages": [
            {
                "baseUrl": "Microsoft/AuditEvent.SE"
            }
        ]
    }
    ```

#### <a name="update-cloud-pos"></a>Frissítse a Cloud POS-t

1. Nyissa meg a **ModernPOS.sln** alatti megoldás **RetailSdk\\ pozíció**.
2. A korábbi POS-bővítmény letiltása:

    - Ban,-ben **tsconfig.json** fájlt, adja hozzá a **FiscalRegisterSample** mappát a kizárási listára.
    - Távolítsa el a következő sorokat a **extensions.json** alatti fájl **RetailSDK\\ pozíció\\ Kiterjesztések** mappát.

        ``` json
        {
            "baseUrl": "FiscalRegisterSample"
        }
        ```

3. Engedélyezze az aktuális minta POS-kiterjesztést a következő sorok hozzáadásával a **extensions.json** fájlban a **RetailSDK\\POS\\Extensions** mappa alatt.

    ``` json
    {
        "extensionPackages": [
            {
                "baseUrl": "Microsoft/AuditEvent.SE"
            }
        ]
    }
    ```

#### <a name="create-deployable-packages"></a>Telepíthető csomagok létrehozása

Futtassa **az msbuild parancsot** a teljes Retail SDK-hoz üzembe helyezhető csomagok létrehozásához. Alkalmazza a csomagokat LCS-n keresztül vagy manuálisan. További információ: [Retail SDK csomagolás](../dev-itpro/retail-sdk/retail-sdk-packaging.md).
