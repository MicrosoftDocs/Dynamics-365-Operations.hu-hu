---
title: A Svédországra vonatkozó vezérlőegység-integrációs minta telepítési irányelvei (legacy)
description: Ez a cikk a Svédországra vonatkozó, a Retail SDK készletből származó, az ellenőrzési egységekkel kapcsolatos integrációs minta telepítésével kapcsolatos irányelveket tartalmaz.
author: EvgenyPopovMBS
ms.date: 12/20/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-3-1
ms.openlocfilehash: fcc35a2203641b24fe4edd2ab34f2e4d5db9bb53
ms.sourcegitcommit: 66d129874635d34a8b29c57762ecf1564e4dc233
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/23/2022
ms.locfileid: "9324297"
---
# <a name="deployment-guidelines-for-the-control-unit-integration-sample-for-sweden-legacy"></a>A Svédországra vonatkozó vezérlőegység-integrációs minta telepítési irányelvei (legacy)

[!include [banner](../includes/banner.md)]

Ez a cikk a Svédországra vonatkozó vezérlőegység-integrációs minta telepítéséről a Lifecycle Services (LCS) fejlesztői virtuális gépére (SDK) vonatkozó kiskereskedelmi szoftverfejlesztői csomagból (SDK) Microsoft Dynamics nyújt tájékoztatást. A pénzügyi integrációs mintával kapcsolatos további tudnivalókat [lásd: Vezérlőegység-integrációs minta Svédország esetében](emea-swe-fi-sample.md). 

A Svédországhoz tartozó pénzügyi integrációs minta a Retail SDK része. Az SDK [telepítésével és használatával kapcsolatos tudnivalókat lásd a Retail szoftverfejlesztői csomag (SDK) architektúráját](../dev-itpro/retail-sdk/retail-sdk-overview.md). Ez a minta a Commerce runtime (CRT), hardverállomás és pénztár (POS) bővítményeiből áll. A minta futtatásához módosítania CRT és fel kell építenie a, hardverállomást és POS-projekteket. Javasoljuk, hogy egy nem módosított Retail SDK készlet használhatja az ebben a cikkben leírt módosításokat. Javasoljuk továbbá, hogy forrásvezérlő rendszert használjon, Azure DevOps például olyanokat, ahol a fájlok még nem módosultak.

## <a name="development-environment"></a>Fejlesztői környezet

A következő lépések szerint állíthatja be a fejlesztői környezetet, hogy tesztelni és ki tudja terjeszteni a mintát.

### <a name="enable-crt-extensions"></a>Bővítmények CRT engedélyezése

A CRT kiterjesztési összetevők a mintában vannak CRT. A következő eljárások befejezéséhez nyissa **meg a CommerceRuntimeSamples.sln** megoldást a **RetailSdk\\ SampleExtensions\\ CommerceRuntime alatt**.

#### <a name="documentprovidercleancashsample-component"></a>DocumentProvider.CleanCashSample összetevő

1. Keresse meg **a Runtime.Extensions.DocumentProvider.CleanCashSample** projektet, és építse fel.
2. A Runtime.Extensions.DocumentProvider.CleanCashSample **bin\\ hibakeresési\\** mappában keresse meg a Contoso.Commerce.Runtime.DocumentProvider.CleanCashSample.dll **szerelvényfájlt**.
3. A szerelvényfájl másolása a bővítmények CRT mappájába:

    - **Commerce Scale Unit:** A fájl másolása **\\\\ az Internet Information Services (IIS) Commerce Scale Unit webhelyének bin ext** mappájába.
    - **Helyi CRT a Modern POS terminálon:** Másolja **\\ a fájlt a helyi ügyfélügynök helye alatti ext** CRT mappába.

4. A következő bővítmény-konfigurációs fájl megkeresve CRT:

    - **Commerce Scale Unit:** **A fájl neve commerceruntime.ext.config**, **\\ és az IIS Commerce Scale Unit webhely bin ext** mappájában található.
    - **Helyi CRT a Modern POS terminálon:** **A fájl neve CommerceRuntime.MPOSOffline.Ext.config**, CRT és a helyi ügyfélügynök helye alatt található.

5. A változás CRT regisztrálása a kiterjesztés konfigurációs fájljában.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.CleanCashSample" />
    ```

#### <a name="extension-configuration-file"></a>Kiterjesztés konfigurációs fájlja

1. A következő bővítmény-konfigurációs fájl megkeresve CRT:

    - **Commerce Scale Unit:** **A fájl neve commerceruntime.ext.config**, **\\ és az IIS Commerce Scale Unit webhely bin ext** mappájában található.
    - **Helyi CRT a Modern POS terminálon:** **A fájl neve CommerceRuntime.MPOSOffline.Ext.config**, CRT és a helyi ügyfélügynök helye alatt található.

2. A változás CRT regisztrálása a kiterjesztés konfigurációs fájljában.

    ``` xml
    <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.ReceiptsSweden" />
    ```

### <a name="enable-hardware-station-extensions"></a>Hardverállomás-bővítmények engedélyezése

A Hardverállomás bővítmény összetevői a hardverállomás mintáiban szerepelnek. A következő eljárások befejezéséhez **nyissa meg a HardwareStationSamples.sln** megoldást a **RetailSdk\\ SampleExtensions\\ HardwareStation eszközben**.

#### <a name="cleancash-component"></a>CleanCash összetevő

1. Keresse meg **és építse fel a HardwareStation.Extension.CleanCashSample** projektet.
2. Keresse meg **a Contoso.Commerce.HardwareStation.CleanCashSample.dll\\\\ és az Interop.CleanCash 1 1.dll** **szerelvényfájlt a Extension.CleanCash** **\_\_** bin hibakeresési mappában.
3. A szerelvényfájlok másolása a hardverállomás bővítmények mappájába:

    - **Megosztott hardverállomás:** A fájlok másolása **az** IIS hardverállomás webhelyének bin mappájába.
    - **Külön hardverállomás a Modern POS terminálon: A** fájlok másolása a Modern POS ügyfélügynöki helyére.

4. A hardverállomás bővítményének konfigurációs fájlja. A fájl neve **HardwareStation.Extension.config**.

    - **Megosztott hardverállomás:** A fájl az IIS hardverállomás helye alatt található.
    - **A Modern POS külön hardverállomása:** A fájl a Modern POS ügyfélügynök helye alatt található.

5. Adja hozzá a következő sort a **konfigurációs** fájl összeállítási szakaszhoz.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.CleanCashSample" />
    ```

### <a name="enable-modern-pos-extension-components"></a>A Modern POS bővítmény összetevőinek engedélyezése

1. Nyissa meg **a ModernPOS.sln megoldást** **a RetailSdk\\ POS** alatt, és ellenőrizze, hogy hiba nélkül fordítható-e. A Futtatás paranccsal arról is győződjön meg, hogy futtatható a Modern POS Visual Studio **·**.

    > [!NOTE]
    > A Modern POS nem szabható testre. Engedélyeznie kell a Felhasználói fiókok vezérlése (UAC) alkalmazást, és szükség szerint el kell távolítania a Modern POS korábban telepített példányait.

2. Engedélyezze a betölthető **bővítményeket a következő soroknak a extensions.json** fájlba való hozzáadásával.

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
    > A további tudnivalókat, valamint azokat a **mintákat, amelyek mutatják, hogyan kell a forráskódmappákat szerepeletni, és hogyan lehet a bővítményeket betölteni, lásd a Pos.Extensions** projekt readme.md fájljában található utasításokat.

3. A megoldás újraépítése.
4. Futtassa a Modern POS szolgáltatást a hibakeresőben, és tesztelje a funkciót.

### <a name="enable-cloud-pos-extension-components"></a>A Felhő POS bővítmény összetevőinek engedélyezése

1. Nyissa meg **a CloudPOS.sln megoldást** **a RetailSdk\\ POS** alatt, és ellenőrizze, hogy hiba nélkül fordítható-e.
2. Engedélyezze a betölthető **bővítményeket a következő soroknak a extensions.json** fájlba való hozzáadásával.

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
    > A további tudnivalókat, valamint azokat a **mintákat, amelyek mutatják, hogyan kell a forráskódmappákat szerepeletni, és hogyan lehet a bővítményeket betölteni, lásd a Pos.Extensions** projekt readme.md fájljában található utasításokat.

3. A megoldás újraépítése.
4. Futtassa a megoldást a Futtatás **parancs** használatával, és kövesse a Retail SDK útmutató lépéseit.

## <a name="production-environment"></a>Működési környezet

Az előző eljárás lehetővé teszi az egységintegrációs minta összetevőit tartalmazó bővítményeket. Ezenkívül ezeket a lépéseket kell követnie ahhoz, hogy commerce összetevőket tartalmazó telepíthető csomagokat hozzon létre, és ezeket a csomagokat éles környezetben alkalmazza.

1. Tegye a következő módosításokat **a RetailSdk\\ Assets mappa csomagkonfigurációs fájljaiban**:

    - **A Commerceruntime.ext.config** **és a CommerceRuntime.MPOSOffline.Ext.config** **konfigurációs fájlokban adja hozzá a következő sorokat az összeállítási szakaszhoz**.

        ``` xml
        <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.CleanCashSample" />
        <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.ReceiptsSweden" />
        ```

    - **A HardwareStation.Extension.config** konfigurációs fájlban adja hozzá a következő sort az összeállítási **szakaszhoz**.

        ``` xml
        <add source="assembly" value="Contoso.Commerce.HardwareStation.CleanCashSample" />
        ```

2. Tegye a következő módosításokat a **Testreszabás.beállítások** csomag testreszabása konfigurációs fájlban a **BuildTools mappában**:

    - A következő sor hozzáadása a bővítményeknek CRT a telepíthető csomagokba való felvételéhez.

        ``` xml
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.DocumentProvider.CleanCashSample.dll" />
        ```

    - Adja hozzá a következő sorokat, hogy a hardverállomás bővítmény szerepeljen a telepíthető csomagokban.

        ``` xml
        <ISV_HardwareStation_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.HardwareStation.CleanCashSample.dll" />
        <ISV_HardwareStation_CustomizableFile Include="$(SdkReferencesPath)\Interop.CleanCash_1_1.dll" />
        ```

3. Engedélyezze a POS-bővítményt a **következő soroknak a RetailSDK** POS-bővítmények **mappában található extensions.json\\\\ fájlba való felvételével**.

    ``` json
    {
        "extensionPackages": [
            {
            "baseUrl": "Microsoft/AuditEvent.SE"
            }
        ]
    }
    ```

4. Indítsa el az MSBuild parancssort Visual Studio a segédprogrammal, **és futtassa az msbuild** csomagot a Retail SDK mappában a telepíthető csomagok létrehozásához.
5. A csomagok alkalmazása LCS-en keresztül vagy manuálisan. A további tudnivalókat lásd [a Telepíthető csomagok létrehozása.](../dev-itpro/retail-sdk/retail-sdk-packaging.md)
6. Az összes szükséges beállítási művelet végrehajtása, [amely a vezérlőegységekkel való integráció beállítása során van leírva](emea-swe-fi-sample.md#setting-up-the-integration-with-control-units).

## <a name="design-of-the-extensions"></a>A bővítmények tervezése

### <a name="crt-extension-design"></a>CRT kiterjesztésterv

A kiterjesztés célja, amely egy pénzügyi bizonylat szolgáltatója, a szolgáltatásspecifikus dokumentumok generálása és az ellenőrző egység válaszának kezelnie.

A CRT kiterjesztés a **Runtime.Extensions.DocumentProvider.CleanCashSample**.

A pénzügyi integráció megoldásának [kialakításával kapcsolatos további tudnivalókat lásd a Pénzügyi nyilvántartási folyamat és a pénzügyi eszközök és szolgáltatások pénzügyi integrációs mintáiban](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services).

#### <a name="request-handler"></a>Kérelemkezelő

A dokumentumszolgáltatóhoz egyetlen **DocumentProviderCleanCash** kérelemkezelő van. Ezzel a kezelővel lehet pénzügyi bizonylatokat létrehozni az ellenőrzési egységhez.

Ez a kezelő az **INamedRequestHandler felületről öröklődik**. A **HandlerName metódus** felelős a kezelő nevének visszaküldéséért. A kezelő nevének meg kell egyeznie a Commerce Headquarters szolgáltatásban megadott csatlakoztató dokumentumszolgáltató nevével.

Az csatlakoztató a következő kéréseket támogatja:

- **GetFiscalDocumentDocumentProviderRequest** – ez a kérés tartalmazza a létrehozandó dokumentum adatait. Olyan szolgáltatásspecifikus dokumentumot ad vissza, amely regisztrálva kell lennie az ellenőrzési egységben.
- **GetSupportedRegistrableEventsDocumentProviderRequest** – ez a kérés a regisztrált események listáját adja eredményül. Jelenleg az értékesítési és a könyvvizsgálati események támogatottak.

#### <a name="configuration"></a>Konfiguráció

A **DocumentProviderFiscalCleanCashSample** konfigurációs fájl **a** bővítményprojekt Konfigurációs mappájában található. A fájl célja, hogy lehetővé tegye a dokumentumszolgáltató Commerce Headquarters rendszerből származó konfigurálásának beállításait. A fájlformátum igazodik a pénzügyi integráció konfigurációjának követelményeihez. A következő beállításokat lehet hozzáadni:

- Áfakódok leképezése

### <a name="hardware-station-extension-design"></a>Hardverállomás bővítményének tervezése

A kiterjesztés célja, amely pénzügyi csatlakoztató, az a cél, hogy kommunikáljon az ellenőrző egységgel.

A Hardverállomás kiterjesztése **HardwareStation.Extension.CleanCashSample**. A HTTP protokollal küldheti el a CRT kiterjesztés által az ellenőrzési egységnek generált dokumentumokat. Kezeli az ellenőrzési egységtől kapott válaszokat is.

#### <a name="request-handler"></a>Kérelemkezelő

A **CleanCashHandler** kérelemkezelő a vezérlőegységhez történő kérések kezelésének belépési pontja.

A kezelő az **INamedRequestHandler felületről öröklődik**. A **HandlerName metódus** felelős a kezelő nevének visszaküldéséért. A kezelő nevének meg kell egyeznie a Commerce Headquartersban megadott pénzügyi csatlakoztató nevével.

Az csatlakoztató a következő kéréseket támogatja:

- **SubmitDocumentFiscalDeviceRequest** – ez a kérés dokumentumokat küld az ellenőrzési egységnek, és választ ad vissza.
- **IsReadyFiscalDeviceRequest** – ez a kérés az ellenőrzési egység állapotellenőrzésére használható.
- **InitializeFiscalDeviceRequest** – ez a kérés a vezérlőegység inicializálására használatos.

#### <a name="configuration"></a>Konfiguráció

A konfigurációs fájl a bővítményprojekt **Konfigurációs** mappájában található. A fájl célja, hogy engedélyezze a Commerce Headquarters alkalmazásból konfigurálható pénzügyi csatlakoztató beállításait. A fájlformátum igazodik a pénzügyi integráció konfigurációjának követelményeihez. A következő beállításokat lehet hozzáadni:

- **Kapcsolati karakterlánc** – a vezérlőegység kapcsolati beállításai.
- **Időtúllépés** – az az idő ezredmásodpercben, ahányszor a vezető az ellenőrző egység válaszát várja.

## <a name="migrating-from-the-earlier-integration-sample"></a>Áttelepítés a korábbi integrációs mintából

Ha a korábbi mintát svédországi [ellenőrző egységgel való POS-integrációra](retail-sdk-control-unit-sample.md) használja, lehet, hogy át kell áttelepítése abból az aktuális integrációs mintába. A svédországi funkciók módosításainak jövőbeli felvételéhez és a funkciók időben elérhető frissítéséhez lehet, hogy frissítenie kell az alkódokat és a konfigurációkat a beépített bővítményekben, és újra kell építenie a megoldásokat. A létrehozott kiterjesztési logika nem igényel nagyobb változtatásokat. A korábbi integrációs minta és a testreszabások továbbra is működni fognak, ha az ön oldalán nem történik módosítás. Ennek megfelelően tervezheti, előkészítheti és elkészítheti a környezetben szükséges felvételeket.

### <a name="migration-process"></a>Áttelepítési folyamat

A korábbi integrációs minta és az ellenőrzési egység jelenlegi integrációs minta közötti áttelepítésének a fokozatos frissítés koncepcióját kell figyelembe vennie. Más szóval a Commerce Headquarters és a Commerce Scale Unit összetevőt már frissíteni kell, mielőtt elkezdené a POS és a hardverállomás összetevőinek frissítését.

Olyan helyzet megakadályozása érdekében, amikor egy eseményt vagy tranzakciót kétszer aláírnak (vagyis a korábbi és a jelenlegi kiterjesztés is aláírja), vagy ha egy eseményt vagy tranzakciót nem lehet aláírni a hiányzó konfiguráció miatt, javasoljuk, hogy kapcsolja ki a korábbi mintát tartalmazó összes POS- és hardverállomás eszközt, , majd frissítheti őket egyszerre. Ez a párhuzamos frissítés például üzletről üzletre történő frissítésre az üzlet funkcióprofilja és a hardveres állomás hardverprofilja frissítésével egyidejűleg történik.

Az áttelepítési folyamatnak a következő lépésekből kell állnia.

1. A Commerce Headquarters összetevőinek frissítése
1. A Commerce Scale Unit összetevőinek frissítése és az aktuális minta kiterjesztésének engedélyezése.
1. Győződjön meg róla, hogy minden offline tranzakció szinkronizálva van az offline módú MPOS-eszközökről.
1. Minden olyan eszköz kikapcsolása, amely a korábbi minta összetevőit használja.
1. Az összes szükséges beállítási művelet végrehajtása, [amely a vezérlőegységekkel való integráció beállítása során van leírva](emea-swe-fi-sample.md#setting-up-the-integration-with-control-units).
1. A POS és a Hardverállomás összetevő frissítése, a korábbi minta részeiben található bővítmények letiltása, valamint az aktuális minta kiterjesztésének engedélyezése.

    > [!NOTE]
    > A környezet típusától függően [az áttelepítési folyamattal kapcsolatos további technikai részleteket az Áttelepítés fejlesztési](#migration-in-a-development-environment)[környezetben vagy az](#migration-in-a-production-environment) Áttelepítés termelési környezetben szakaszból találhatja meg.

### <a name="migration-in-a-development-environment"></a>Áttelepítés fejlesztési környezetben

#### <a name="update-crt"></a>CRT frissítése

1. Keresse meg **a Runtime.Extensions.DocumentProvider.CleanCashSample** projektet, és építse fel.
2. A Runtime.Extensions.DocumentProvider.CleanCashSample **bin\\ hibakeresési\\** mappában keresse meg a Contoso.Commerce.Runtime.DocumentProvider.CleanCashSample.dll **szerelvényfájlt**.
3. A szerelvényfájl másolása a bővítmények CRT mappájába:

    - **Commerce Scale Unit:** A fájl másolása **\\\\ az IIS Commerce Scale Unit webhely bin ext** mappájába.
    - **Helyi CRT a Modern POS terminálon:** Másolja **\\ a fájlt a helyi ügyfélügynök helye alatti ext** CRT mappába.

4. A következő bővítmény-konfigurációs fájl megkeresve CRT:

    - **Commerce Scale Unit:** **A fájl neve CommerceRuntime.ext.config**, **\\ és az IIS Commerce Scale Unit webhely bin ext** mappájában található.
    - **Helyi CRT a Modern POS terminálon:** **A fájl neve CommerceRuntime.MPOSOffline.Ext.config**, **és a helyi ügyfélügynök helye, a bin\\ ext** CRT mappában található.

    > [!WARNING]
    > Ne **szerkessze** a CommerceRuntime.config és a CommerceRuntime.MPOSOffline.config fájlokat. Ezek a fájlok nem testreszabott fájlok.

5. A kiterjesztés konfigurációs fájljában található korábbi CRT kiterjesztés megkeresve és eltávolítása.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.FiscalRegisterReceiptSample" />
    ```

    > [!WARNING]
    > Ezt a lépést ne kell végrehajtani, amíg nem frissít minden OLYAN POS-eszközt, amely ezzel a példánysal CRT dolgozik.

6. Az aktuális mintakiterjesztések CRT regisztrálása a kiterjesztés konfigurációs fájljában a következő sorok hozzáadásával.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.CleanCashSample" />
    <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.ReceiptsSweden" />
    ```

#### <a name="update-hardware-station"></a>Hardverállomás frissítése

1. Keresse meg **és építse fel a HardwareStation.Extension.CleanCashSample** projektet.
2. Keresse meg **a Contoso.Commerce.HardwareStation.CleanCashSample.dll\\\\ és az Interop.CleanCash 1 1.dll** **szerelvényfájlt a Extension.CleanCash** **\_\_** bin hibakeresési mappában.
3. A szerelvényfájlok másolása a hardverállomás bővítmények mappájába:

    - **Megosztott hardverállomás:** A fájlok másolása **az** IIS hardverállomás webhelyének bin mappájába.
    - **Külön hardverállomás a Modern POS terminálon: A** fájlok másolása a Modern POS ügyfélügynöki helyére.

4. Keresse meg **a HardwareStation.Extension.config kiterjesztés** konfigurációs fájlját:

    - **Távoli hardverállomás:** A fájl az IIS hardverállomás helye alatt található.
    - **Helyi hardverállomás a Modern POS terminálon:** A fájl a Modern POS ügyfélügynök helye alatt található.

    > [!WARNING]
    > Ne **szerkessze** a CommerceRuntime.config és a CommerceRuntime.MPOSOffline.config fájlokat. Ezek a fájlok nem testreszabott fájlok.

5. A korábbi hardverállomás-kiterjesztés megkeresi és eltávolítja a kiterjesztés konfigurációs fájlját.

    # <a name="retail-73-and-earlier"></a>[Retail 7.3 és korábbi](#tab/retail-7-3)

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.Extension.FiscalRegisterSample" />
    ```

    # <a name="retail-731-and-later"></a>[Retail 7.3.1 és újabb](#tab/retail-7-3-1)

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.Extension.FiscalRegisterSample" />
    ```

    # <a name="retail-100-and-later"></a>[Retail 10.0 és újabb](#tab/retail-10-0)

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.FiscalRegisterSample" />
    ```
    ---

6. Adja hozzá a következő sort a **kiterjesztési** konfigurációs fájl összeállítási szakaszhoz.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.CleanCashSample" />
    ```

#### <a name="update-modern-pos"></a>Modern POS frissítése

1. Nyissa meg **a CloudPOS.sln megoldást** a **RetailSdk POS szolgáltatásban\\**.
2. Tiltsa le a korábbi POS-bővítményt a **következő soroknak a extensions.json fájlból** való eltávolításával.

    ``` json
    {
        "baseUrl": "FiscalRegisterSample"
    }
    ```

2. Engedélyezze az aktuális minta POS-bővítményt a **következő soroknak a extension.json fájlba való hozzáadásával**.

    ``` json
    {
        "extensionPackages": [
            {
                "baseUrl": "Microsoft/AuditEvent.SE"
            }
        ]
    }
    ```

#### <a name="update-cloud-pos"></a>A Felhő POS frissítése

1. Nyissa meg **a ModernPOS.sln megoldást** a **RetailSdk POS alatt\\**.
2. Tiltsa le a korábbi POS-bővítményt a **következő soroknak a extensions.json fájlból** való eltávolításával.

    ``` json
    {
        "baseUrl": "FiscalRegisterSample"
    }
    ```

2. Engedélyezze az aktuális minta POS-bővítményt a **következő soroknak a extension.json fájlba való hozzáadásával**.

    ``` json
    {
        "extensionPackages": [
            {
                "baseUrl": "Microsoft/AuditEvent.SE"
            }
        ]
    }
    ```

### <a name="migration-in-a-production-environment"></a>Áttelepítés éles környezetben

#### <a name="update-crt"></a>CRT frissítése

1. CRT Távolítsa el a korábbi bővítményt a **CommerceRuntime.ext.config** **és CommerceRuntime.MPOSOffline.Ext.config konfigurációs fájlokból** **a RetailSdk\\ Assets mappában**.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.FiscalRegisterReceiptSample" />
    ```

    > [!WARNING]
    > Ezt a lépést ne kell végrehajtani, amíg nem frissít minden OLYAN POS-eszközt, amely ezzel a példánysal CRT dolgozik.

2. Engedélyezze az aktuális mintakiterjesztéseket CRT **a CommerceRuntime.ext.config** **és CommerceRuntime.MPOSOffline.Ext.config** **konfigurációs fájloknak a RetailSdk\\ Assets** mappában végrehajtott változtatásával.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.CleanCashSample" />
    <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.ReceiptsSweden" />
    ```

3. **A BuildTools** mappa Alatti Testreszabás.beállítások **csomag**-testreszabási konfigurációs fájlban adja hozzá a következő sort, hogy az aktuális mintakiterjesztés CRT szerepeljen a telepíthető csomagokban.

    ``` xml
    <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.DocumentProvider.CleanCashSample.dll" />
    ```

#### <a name="update-hardware-station"></a>Hardverállomás frissítése

1. Távolítsa el a korábbi hardverállomás-kiterjesztést a **HardwareStation.Extension.config konfigurációs fájl** módosításával.

    # <a name="retail-73-and-earlier"></a>[Retail 7.3 és korábbi](#tab/retail-7-3)

    Távolítsa el a következő szakaszt a **HardwareStation.Shared.config** és **HardwareStation.Dedicated.config konfigurációs** fájlokból.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.Extension.FiscalRegisterSample" />
    ```

    # <a name="retail-731-and-later"></a>[Retail 7.3.1 és újabb](#tab/retail-7-3-1)

    Távolítsa el a következő szakaszt a **HardwareStation.Extension.config konfigurációs** fájlból.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.Extension.FiscalRegisterSample" />
    ```

    # <a name="retail-100-and-later"></a>[Retail 10.0 és újabb](#tab/retail-10-0)

    Távolítsa el a következő szakaszt a **HardwareStation.Extension.config konfigurációs** fájlból.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.FiscalRegisterSample" />
    ```
    ---

2. Engedélyezze az aktuális hardverállomás-mintakiterjesztést **·** **a Következő sornak a HardwareStation.Extension.config konfigurációs fájl összeállítási szakaszához való hozzáadásával**.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.CleanCashSample" />
    ```

3. Tegye a következő módosításokat a **Testreszabás.beállítások** csomag testreszabása konfigurációs fájlban a **BuildTools mappában**:

    - Távolítsa el a következő sort, ha ki szeretné zárni a korábbi hardverállomás-bővítményt a telepíthető csomagokból.

        ``` xml
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.HardwareStation.Extension.FiscalRegisterSample.dll" />
        ```

    - Adja hozzá a következő sorokat, hogy az aktuális minta hardverállomás bővítmény szerepeljen a telepíthető csomagokban.

        ``` xml
        <ISV_HardwareStation_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.HardwareStation.CleanCashSample.dll" />
        <ISV_HardwareStation_CustomizableFile Include="$(SdkReferencesPath)\Interop.CleanCash_1_1.dll" />
        ```

#### <a name="update-modern-pos"></a>Modern POS frissítése

1. Nyissa meg **a CloudPOS.sln megoldást** a **RetailSdk POS-terminálon\\**.
2. A korábbi POS-bővítmény letiltása:

    - **A tsconfig.json fájlban** adja **hozzá a FiscalRegisterSample** mappát a kizárási listához.
    - A következő sorok eltávolítása a RetailSDK **POS-bővítmények** mappában található extensions.json **\\ fájlból\\.**

        ``` json
        {
            "baseUrl": "FiscalRegisterSample"
        }
        ```

3. Engedélyezze az aktuális minta POS-bővítményt **a Következő soroknak a RetailSDK** POS-bővítmények **mappában található extensions.json\\\\ fájlba való felvételével**.

    ``` json
    {
        "extensionPackages": [
            {
                "baseUrl": "Microsoft/AuditEvent.SE"
            }
        ]
    }
    ```

#### <a name="update-cloud-pos"></a>A Felhő POS frissítése

1. Nyissa meg **a ModernPOS.sln megoldást** a **RetailSdk POS alatt\\**.
2. A korábbi POS-bővítmény letiltása:

    - **A tsconfig.json fájlban** adja **hozzá a FiscalRegisterSample** mappát a kizárási listához.
    - A következő sorok eltávolítása a RetailSDK **POS-bővítmények** mappában található extensions.json **\\ fájlból\\.**

        ``` json
        {
            "baseUrl": "FiscalRegisterSample"
        }
        ```

3. Engedélyezze az aktuális minta POS-bővítményt **a Következő soroknak a RetailSDK** POS-bővítmények **mappában található extensions.json\\\\ fájlba való felvételével**.

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

Futtassa **az msbuild** csomagot a teljes Retail SDK készletből, hogy telepíthető csomagokat hozzon létre. A csomagok alkalmazása LCS-en keresztül vagy manuálisan. A további tudnivalókat lásd a [Retail SDK csomagolásával kapcsolatban](../dev-itpro/retail-sdk/retail-sdk-packaging.md).
