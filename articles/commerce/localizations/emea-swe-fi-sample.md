---
title: Ellenőrzőegység integrációs mintája Svédország esetén
description: Ez a témakör áttekintést nyújt a svédországi költségvetési integrációs mintáról Microsoft Dynamics 365 Commerce.
author: EvgenyPopovMBS
ms.date: 12/20/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2019-10-08
ms.openlocfilehash: ace1bd5b1a06317b6753a34779ecfa96e519a63e
ms.sourcegitcommit: 5cefe7d2a71c6f220190afc3293e33e2b9119685
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/01/2022
ms.locfileid: "8077013"
---
# <a name="control-unit-integration-sample-for-sweden"></a>Ellenőrzőegység integrációs mintája Svédország esetén

[!include [banner](../includes/banner.md)]

Ez a témakör áttekintést nyújt a svédországi költségvetési integrációs mintáról Microsoft Dynamics 365 Commerce.

> [!NOTE]
> Ez a minta fiskális integrációs funkció a korábbi helyébe lép [minta POS-integrációhoz vezérlőegységekkel Svédország számára](retail-sdk-control-unit-sample.md). A korábbi minta nem használja ki a [költségvetési integrációs keret](./fiscal-integration-for-retail-channel.md) és a későbbi frissítések során elavulttá válik. A korábbi mintáról a megfelelő mintára való átállással kapcsolatos információkért Dynamics 365 Commerce változat **10.0.22 és korábbi**, lát [Áttérés a korábbi integrációs mintáról](emea-swe-fi-sample-sdk.md#migrating-from-the-earlier-integration-sample).

A svédországi Kereskedelmi funkció magában foglalja az értékesítési pont (POS) mintaintegrációját Svédország-specifikus adóeszközökkel, amelyek az ún.*vezérlőegységek*. Ez a minta kiterjeszti a [fiskális integrációs funkcionalitás](fiscal-integration-for-retail-channel.md). Feltételezzük, hogy a vezérlőegység fizikailag csatlakozik egy hardver állomáshoz, amellyel a POS párosítva van. Példaként ez a minta az alkalmazásprogramozási felületet (API) használja [CleanCash A típusú](https://www.retailinnovation.se/produkter) vezérlőegység a Retail Innovation HTT AB-től. A CleanCash API 1.1.4-es verziója használatos.

A minta forráskód formájában áll rendelkezésre, és a kiskereskedelmi szoftverfejlesztő készlet (SDK) része.

A Microsoft nem ad ki semmilyen hardvert, szoftvert vagy dokumentációt a Retail Innovation HTT AB-től. A vezérlőegység beszerzésével és kezelésével kapcsolatos információkért forduljon a következőhöz [Retail Innovation HTT AB](https://www.retailinnovation.se/).

## <a name="scenarios"></a>Forgatókönyvek

A svédországi vezérlőegység-integrációs minta a következő képességeket tartalmazza:

- Az értékesítési, visszaküldési és nyugtapéldányok automatikusan regisztrálásra kerülnek egy vezérlőegységben, amely a POS-szal párosított hardverállomáshoz csatlakozik.
- A regisztrált tranzakcióhoz tartozó vezérlőegység vezérlőkódja és gyártási száma rögzítésre kerül a vezérlőegységből és elmentésre kerül a tranzakcióba. Ezeket az adatokat a *fiskális válasz*. A fiskális válasz megtekinthető a **Bolti tranzakciók** oldalon.
- Egyedi mezők az ellenőrző kódhoz és a vezérlőegység gyártási számához adhatók hozzá a nyugtaelrendezéshez. Ily módon kinyomtathatja egy tranzakció fiskális válaszát egy nyugtára.
- A tranzakció fiskális válaszát a **Elektronikus folyóirat (Svédország)** csatorna jelentés.
- Számos hibakezelési lehetőség áll rendelkezésre. Íme néhány példa:

    - Próbálkozzon újra az adóbejegyzéssel, ha lehetséges. Megpróbálhatja újra a fiskális regisztrációt, ha például a vezérlőegység nincs csatlakoztatva, nincs készenlétben vagy nem válaszol.
    - Az adóbejegyzés elhalasztása.
    - Hagyja ki a fiskális regisztrációt, vagy jelölje meg a tranzakciót regisztráltként, és adjon meg információs kódokat a hiba okának rögzítéséhez és további információkhoz.
    - Ellenőrizze a vezérlőegység elérhetőségét egy új értékesítési tranzakció megnyitása vagy egy értékesítési tranzakció véglegesítése előtt.

### <a name="limitations-of-the-sample"></a>A minta korlátai

A svédországi vezérlőegység-integrációs minta jelenleg nem támogatja az ügyfélrendelési forgatókönyveket.

## <a name="setting-up-the-integration-with-control-units"></a>A vezérlőegységekkel való integráció beállítása

A Svédország számára szükséges beállításokkal kapcsolatos további információkért lásd: [A Commerce beállítása Svédország számára](./emea-swe-cash-registers.md#setting-up-commerce-for-sweden).

### <a name="configuring-swedenspecific-receipts"></a>Svédország-specifikus nyugták konfigurálása

#### <a name="configure-custom-fields-so-that-they-can-be-used-in-receipt-formats-for-sales-receipts"></a>Állítsa be az egyéni mezőket úgy, hogy azokat az értékesítési bizonylatok nyugtaformátumaiban lehessen használni

Beállíthatja a POS nyugtaformátumokban használt nyelvi szöveget és egyéni mezőket. A nyugtabeállítást létrehozó felhasználó alapértelmezett cégének ugyanannak a jogi személynek kell lennie, mint ahol a nyelvi szövegbeállítás létrejött. Alternatív megoldásként ugyanazokat a nyelvű szövegeket kell létrehozni a felhasználó alapértelmezett vállalatában és annak az áruháznak a jogi személyében, amelyhez a beállítást létrehozták.

A **Nyelvi szöveg** oldalon adja hozzá a következő rekordokat a nyugtaelrendezések egyéni mezőinek címkéihez. Vegye figyelembe, hogy a **Nyelvazonosító**, **azonosító**, és **Szöveg** a táblázatban szereplő értékek csak példák. Módosíthatja őket, hogy megfeleljenek igényeinek. Azonban a **Szöveges azonosító** A használt értékeknek egyedinek kell lenniük, és egyenlőnek vagy nagyobbaknak kell lenniük a 900001 értéknél.

Adja hozzá a következő POS-címkéket a **pozíció** szakasza a **Nyelvi szöveg** oldalon.

| Nyelvazonosító | Szövegazonosító | Szöveg                  |
|-------------|---------|-----------------------|
| hu-US       | 900001  | Regisztrálja az ellenőrző kódot |
| hu-US       | 900002  | Regisztrálja az eszközt       |

A **Egyéni mezők** oldalon adja hozzá a következő rekordokat a nyugtaelrendezések egyéni mezőihez. Vegye figyelembe, hogy **Felirat szövegének azonosítója** értékeknek meg kell felelniük a **Szöveges azonosító** oldalon megadott értékek **Nyelvi szöveg** oldalon.

| Név                         | Típus    | Képaláírás-szöveg azonosítója |
|------------------------------|---------|-----------------|
| SE_FISCALREGISTERCONTROLCODE | Fogadás | 900001          |
| SE_FISCALREGISTERID          | Fogadás | 900002          |

> [!NOTE]
> Fontos, hogy helyes egyéni mezőneveket adjon meg, a fenti táblázat szerint. A helytelen egyéni mezőnév adatok hiányát okozza a nyugtákban.

#### <a name="configure-receipt-formats"></a>Konfigurálja a nyugtaformátumokat

Minden szükséges nyugtaformátumnál módosítsa az értékét **Nyomtatási viselkedés** mezőt **Mindig nyomtasson**.

A Nyugtaformátum-tervezőben adja hozzá a következő egyéni mezőket a **Lábléc** szakasz. Vegye figyelembe, hogy a mezőnevek megfelelnek a témakör előző részében megadott nyelvi szövegeknek.

- **Regisztrálja az ellenőrző kódot** – Ez a mező a vezérlőkódot nyomtatja ki.
- **Regisztrálja az eszközt** – Ez a mező a vezérlőegység gyártási számát írja ki.

A nyugtaformátumokkal kapcsolatos további információkért lásd: [Nyugta sablonok és nyomtatás](../receipt-templates-printing.md).

### <a name="set-up-fiscal-integration-for-sweden"></a>Állítsa be a költségvetési integrációt Svédország számára

A Svédországra vonatkozó vezérlőegység-integrációs minta a [fiskális integrációs funkcionalitás](fiscal-integration-for-retail-channel.md) és a Retail SDK része. A minta a **src\\ Fiskális integráció\\ CleanCash** mappa a [Dynamics 365 Commerce Megoldások](https://github.com/microsoft/Dynamics365Commerce.Solutions/) adattár (pl.[a minta kiadásban/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/CleanCash)). A minta [egy pénzügyi bizonylatszolgáltatóból áll](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services), amely a Commerce futtatókörnyezet (CRT) kiterjesztése, és egy fiskális összekötőből, amely a Commerce Hardware Station kiterjesztése. A Kiskereskedelmi SDK használatáról a Retail SDK architektúrája [és](../dev-itpro/retail-sdk/retail-sdk-overview.md) build-folyamat beállítása a független csomagolású SDK-hoz [című témakörben talál](../dev-itpro/build-pipeline.md) további információt.

> [!WARNING]
> Az új független csomagolási és kiterjesztési [modell](../dev-itpro/build-pipeline.md) korlátai miatt jelenleg nem használható ehhez a költségvetési integrációs mintához. A Retail SDK előző verzióját egy fejlesztői virtuális gépen (VM) kell használnia az Microsoft Dynamics Életciklus-szolgáltatásokban (LCS). További információkért lásd [Üzembe helyezési irányelvek a vezérlőegység-integrációs mintához Svédországban (örökölt)](emea-swe-fi-sample-sdk.md).
>
> A költségvetési integrációs minták új független csomagolási és kiterjesztési modelljének támogatását tervezik a későbbi verziókhoz.

Végezze el a fiskális integráció beállítási lépéseit az alábbiak szerint [Állítsa be a kereskedelmi csatornák pénzügyi integrációját](setting-up-fiscal-integration-for-retail-channel.md).

1. [Hozzon létre egy pénzügyi regisztrációs folyamatot](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process). Jegyezze fel a fiskális regisztrációs folyamat beállításait is [erre a vezérlőegység-integrációs mintára jellemző](#set-up-the-registration-process).
1. [Állítsa be a hibakezelési beállításokat](setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).
1. [Az elhalasztott adóregisztráció](setting-up-fiscal-integration-for-retail-channel.md#enable-manual-execution-of-postponed-fiscal-registration) manuális végrehajtásának engedélyezése.
1. [Csatornaösszetevők konfigurálása](#configure-channel-components).

### <a name="set-up-the-registration-process"></a>A regisztrációs folyamat beállítása

A regisztrációs folyamat engedélyezéséhez kövesse az alábbi lépéseket a Kereskedelmi központ beállításához. További információ: [A kereskedelmi csatornák](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process) pénzügyi integrációjának beállítása.

1. Konfigurációs fájlok letöltése a pénzügyi dokumentumszolgáltatóhoz és a pénzügyi összekötőhöz:

    1. Nyissa meg a [Dynamics 365 Commerce Megoldások](https://github.com/microsoft/Dynamics365Commerce.Solutions/) adattárat.
    1. Válassza ki a megfelelő kiadási ágverziót az SDK/alkalmazás verziója szerint (például **[release/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33)**).
    1. Nyisd ki **src \> Fiskális integráció \> CleanCash**.
    1. Töltse le az adódokumentum-szolgáltató konfigurációs fájlját a következő címről: **CommerceRuntime \> DocumentProvider.CleanCashSample \> Konfiguráció \> DocumentProviderFiscalCleanCashSample.xml** (például, [a kiadáshoz tartozó fájl/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/blob/release/9.33/src/FiscalIntegration/CleanCash/CommerceRuntime/DocumentProvider.CleanCashSample/Configuration/DocumentProviderFiscalCleanCashSample.xml)).
    1. Töltse le a fiskális csatlakozó konfigurációs fájlját a következő címről: **HardwareStation \> Csatlakozó.CleanCashSample \> Konfiguráció \> ConnectorCleanCashSample.xml** (például, [a kiadáshoz tartozó fájl/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/blob/release/9.33/src/FiscalIntegration/CleanCash/HardwareStation/Connector.CleanCashSample/Configuration/ConnectorCleanCashSample.xml)).

    > [!WARNING]
    > Az új független csomagolási és kiterjesztési [modell](../dev-itpro/build-pipeline.md) korlátai miatt jelenleg nem használható ehhez a költségvetési integrációs mintához. A Retail SDK előző verzióját kell használnia egy fejlesztői virtuális gépen az LCS-ben. A pénzügyi integrációs minta konfigurációs fájljai a Retail SDK következő mappáiban találhatók egy fejlesztői virtuális gépen az LCS-ben:
    >
    > - **Fiskális dokumentum-szolgáltató konfigurációs fájlja:** RetailSdk\\ SampleExtensions\\ CommerceRuntime\\ Extensions.DocumentProvider.CleanCashSample\\ Konfiguráció\\ DocumentProviderFiscalCleanCashSample.xml
    > - **Fiskális csatlakozási konfigurációs fájl:** RetailSdk\\ SampleExtensions\\ HardwareStation\\ Extension.CleanCashSample\\ Konfiguráció\\ ConnectorCleanCashSample.xml
    > 
    > A költségvetési integrációs minták új független csomagolási és kiterjesztési modelljének támogatását tervezik a későbbi verziókhoz.

1. Lépjen a **Retail és Commerce \> Központ beállítása \> Paraméterek \> Commerce megosztott paraméterek** menüpontra. Az Általános **lapon állítsa a** Költségvetési integráció **engedélyezése beállítást Igen értékre** **.**
1. Menj **Kiskereskedelem és kereskedelem \> Csatorna beállítása \> Fiskális integráció \> Fiskális dokumentumszolgáltatók**, és töltse be a korábban letöltött adódokumentum-szolgáltató konfigurációs fájlját.
1. Lépjen a **Kiskereskedelmi és kereskedelmi \> csatorna beállítására \> Pénzügyi integráció \> Pénzügyi összekötők, és töltse be a korábban letöltött pénzügyi összekötő konfigurációs** fájlt.
1. Lépjen a **Kiskereskedelmi és kereskedelmi \> csatorna beállítására \> Pénzügyi integrációs \> összekötő funkcionális profiljai**. Hozzon létre egy új csatlakozó funkcionális profilt. Válassza ki a dokumentumszolgáltatót és a korábban betöltött csatlakozót. Szükség szerint frissítse az [adatleképezési beállításokat](#default-data-mapping).
1. Lépjen a **Kiskereskedelmi és kereskedelmi \> csatorna beállítására \> Pénzügyi integráció \> Összekötő technikai profiljai**. Hozzon létre egy új összekötő műszaki profilját, és válassza ki a korábban betöltött pénzügyi összekötőt. Szükség szerint frissítse az [összekötő beállításait](#fiscal-connector-settings).
6. Lépjen a **Kiskereskedelem és kereskedelem \> csatorna beállítására \> Pénzügyi integráció \> Pénzügyi összekötő csoportok**. Hozzon létre egy új pénzügyi összekötő-csoportot a korábban létrehozott összekötő funkcionális profilhoz.
7. Lépjen a **Kiskereskedelmi és kereskedelmi \> csatorna beállítására \> Pénzügyi integráció \> Pénzügyi regisztrációs folyamatok**. Hozzon létre egy új adóregisztrációs folyamatot és egy fiskális regisztrációs folyamat lépést, és válassza ki a korábban létrehozott adóösszekötő csoportot.
8. Ugorjon a következő elemre: **Retail és Commerce \>  Csatorna beállítása \> Pénztárbeállítás \>  Pénztárprofilok \> Funkcióprofilok**. Válasszon ki egy olyan funkcióprofilt, amely ahhoz az üzlethez kapcsolódik, ahol a regisztrációs folyamatot aktiválni kell. **A Pénzügyi regisztrációs folyamat** gyorslapon válassza ki a korábban létrehozott pénzügyi regisztrációs folyamatot.
9. Lépjen a **Kiskereskedelem és kereskedelem \> Csatorna beállítás \> POS beállítás \> POS profilok \> Hardverprofilok** pontra. Válasszon ki egy hardverprofilt, amely ahhoz a hardverállomáshoz kapcsolódik, amelyhez a pénzügyi nyomtató csatlakozik. **A Pénzügyi perifériák** gyorslapon válassza ki a korábban létrehozott összekötő műszaki profilját.
10. Nyissa meg a terjesztési ütemezést (**Kiskereskedelmi és \> kereskedelmi kiskereskedelem és kereskedelem IT-terjesztési \> ütemezése**), és válassza az 1070-es és **1090-es** **feladatokat** az adatok csatornaadatbázisba történő átviteléhez.

#### <a name="default-data-mapping"></a>Alapértelmezett adatleképezés

A költségvetési integrációs minta részeként megadott pénzügyi bizonylatszolgáltató konfigurációja a következő alapértelmezett adatleképezést tartalmazza:

- **Általános forgalmi adó (áfa) kód leképezés** – Ez a leképezés az eszközspecifikus általános forgalmi adó (áfa) kódokat a megfelelő forgalmiadó-kódokhoz állítja be. Az ÁFA-kód hozzárendelésének a következő formátumúnak kell lennie:

    ```
    1 : code1 ; 2 : code2
    ```

    Itt találja a formátum magyarázatát:

    - *1* és *2* készülékspecifikus ÁFA kódok.
    - Elválasztóként pontosvesszőt (;) használunk.
    - *kód1* és *kód2* olyan forgalmi adó kódok, amelyek a Commerce központjában vannak konfigurálva. Módosítania kell a mintaleképezést az alkalmazásban konfigurált adókódoknak megfelelően.

    A vezérlőegységek akár négy különböző ÁFA kódot támogatnak. Ezért az áfakód-leképezést a következő módon lehet beállítani:

    ```
    1 : code1 ; 2 : code2 ; 3 : code3 ; 4 : code4
    ```

    > [!NOTE]
    > Több általános forgalmi adó kód is hozzárendelhető ugyanahhoz az eszközspecifikus áfakódhoz.

#### <a name="fiscal-connector-settings"></a>Pénzügyi összekötő beállításai

A költségvetési integrációs minta részeként megadott pénzügyi összekötő konfiguráció a következő beállításokat tartalmazza:

- **Csatlakozási karakterlánc** – A vezérlőegység csatlakozási beállításai.
- **Időtúllépés** – Az az idő, ezredmásodpercben, ameddig a vezető vár a vezérlőegység válaszára.

### <a name="configure-channel-components"></a>Csatornaösszetevők konfigurálása

> [!WARNING]
> Az új független csomagolási és kiterjesztési [modell](../dev-itpro/build-pipeline.md) korlátai miatt jelenleg nem használható ehhez a költségvetési integrációs mintához. A Retail SDK előző verzióját kell használnia egy fejlesztői virtuális gépen az LCS-ben. További információkért lásd [Üzembe helyezési irányelvek a vezérlőegység-integrációs mintához Svédországban (örökölt)](emea-swe-fi-sample-sdk.md).
>
> A költségvetési integrációs minták új független csomagolási és kiterjesztési modelljének támogatását tervezik a későbbi verziókhoz.

#### <a name="set-up-the-development-environment"></a>A fejlesztési környezet beállítása

A minta tesztelésére és kiterjesztésére vonatkozó fejlesztési környezet beállításához kövesse az alábbi lépéseket.

1. Klónozza vagy töltse le a [Dynamics 365 Commerce Solutions](https://github.com/microsoft/Dynamics365Commerce.Solutions) adattárat. Válassza ki a megfelelő kiadási ágverziót az SDK/alkalmazás verziójának megfelelően. További információkért lásd [Töltsön le Retail SDK-mintákat és referenciacsomagokat a GitHubból és a NuGet](../dev-itpro/retail-sdk/sdk-github.md).
1. Nyissa meg a vezérlőegység-integrációs megoldást a címen **Dynamics365Commerce.Solutions\\ Fiskális integráció\\ CleanCash\\ CleanCash.sln**, és megépíteni.
1. Telepítés CRT kiterjesztések:

    1. Találd meg CRT bővítmény telepítő:

        - **Kereskedelmi mértékegység:** Ban,-ben **CleanCash\\ ScaleUnit\\ ScaleUnit.CleanCash.Installer\\ kuka\\ Debug\\ net461** mappát, keresse meg a **ScaleUnit.CleanCash.Installer** telepítő.
        - **Helyi CRT a modern POS-on:** Ban,-ben **CleanCash\\ Modern POS\\ ModernPOS.CleanCash.Installer\\ kuka\\ Debug\\ net461** mappát, keresse meg a **ModernPOS.CleanCash.Installer** telepítő.

    2. Indítsa el a CRT kiterjesztés telepítője a parancssorból:

        - **Kereskedelmi mértékegység:**

            ```Console
            ScaleUnit.CleanCash.Installer.exe install --verbosity 0
            ```

        - **Helyi CRT a modern POS-on:**

            ```Console
            ModernPOS.CleanCash.Installer.exe install --verbosity 0
            ```

1. Hardverállomás-bővítmények telepítése:

    1. Ban,-ben **CleanCash\\ HardwareStation\\ HardwareStation.CleanCash.Installer\\ kuka\\ Debug\\ net461** mappát, keresse meg a **HardwareStation.CleanCash.Installer** telepítő.
    1. Indítsa el a bővítménytelepítőt a parancssorból:

        ```Console
        HardwareStation.CleanCash.Installer.exe install --verbosity 0
        ```

#### <a name="production-environment"></a>Működési környezet

Kövesse a lépéseket [Állítson be egy összeállítási folyamatot a fiskális integrációs mintához](fiscal-integration-sample-build-pipeline.md) a Cloud Scale Unit és az önkiszolgáló telepíthető csomagok létrehozása és kiadása a költségvetési integrációs mintához. A **CleanCash build-pipeline.yml** sablon YAML fájl megtalálható a **Csővezeték\\ YAML_Files** mappa a [Dynamics 365 Commerce Megoldások](https://github.com/microsoft/Dynamics365Commerce.Solutions) adattár.

## <a name="design-of-the-extensions"></a>A bővítmények tervezése

A Svédországra vonatkozó vezérlőegység-integrációs minta a [fiskális integrációs funkcionalitás](fiscal-integration-for-retail-channel.md) és a Retail SDK része. A minta a **src\\ Fiskális integráció\\ CleanCash** mappa a [Dynamics 365 Commerce Megoldások](https://github.com/microsoft/Dynamics365Commerce.Solutions/) adattár (pl.[a minta kiadásban/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/CleanCash)). A minta [áll](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services) egy fiskális dokumentumszolgáltató, amely a kiterjesztése CRT és egy fiskális csatlakozó, amely a Commerce Hardware Station kiterjesztése. A Kiskereskedelmi SDK használatáról a Retail SDK architektúrája [és](../dev-itpro/retail-sdk/retail-sdk-overview.md) build-folyamat beállítása a független csomagolású SDK-hoz [című témakörben talál](../dev-itpro/build-pipeline.md) további információt.

> [!WARNING]
> Az új független csomagolási és kiterjesztési [modell](../dev-itpro/build-pipeline.md) korlátai miatt jelenleg nem használható ehhez a költségvetési integrációs mintához. A Retail SDK előző verzióját kell használnia egy fejlesztői virtuális gépen az LCS-ben. További információkért lásd [Üzembe helyezési irányelvek a vezérlőegység-integrációs mintához Svédországban (örökölt)](emea-swe-fi-sample-sdk.md). A költségvetési integrációs minták új független csomagolási és kiterjesztési modelljének támogatását tervezik a későbbi verziókhoz.

### <a name="crt-extension-design"></a>CRT bővítmény kialakítása

A fiskális bizonylat-szolgáltató bővítmény célja szolgáltatás-specifikus dokumentumok előállítása és a vezérlőegység válaszainak kezelése.

#### <a name="request-handler"></a>Kérelemkezelő

Egyetlen van **DocumentProviderCleanCash** kéréskezelő a dokumentumszolgáltató számára. Ez a kezelő a vezérlőegység fiskális dokumentumainak előállítására szolgál.

Ezt a kezelőt a **INamedRequestHandler** felület. A **HandlerName** metódus felelős a kezelő nevének visszaadásáért. A kezelő nevének meg kell egyeznie a Kereskedelmi központban megadott összekötő dokumentumszolgáltató nevével.

Az összekötő a következő kéréseket támogatja:

- **GetFiscalDocumentDocumentProviderRequest** – Ez a kérés információt tartalmaz arról, hogy milyen dokumentumot kell létrehozni. Egy szolgáltatás-specifikus dokumentumot ad vissza, amelyet regisztrálni kell a vezérlőegységben.
- **GetSupportedRegistrableEventsDocumentProviderRequest** – Ez a kérés visszaadja az előfizetendő események listáját. Jelenleg értékesítési események és audit események támogatottak.

#### <a name="configuration"></a>Konfiguráció

A pénzügyi dokumentumszolgáltató konfigurációs fájlja az **src\\FiscalIntegration\\CleanCash\\CommerceRuntime\\DocumentProvider.CleanCashSample\\Configuration\\DocumentProviderFiscalCleanCashSample.xml** található a [Dynamics 365 Commerce Solutions](https://github.com/microsoft/Dynamics365Commerce.Solutions/) adattárban. Ennek a fájlnak az a célja, hogy lehetővé tegye a dokumentumszolgáltató beállításait a Commerce központjában. A fájlformátum igazodik a pénzügyi integráció konfigurációjának követelményeihez.

### <a name="hardware-station-extension-design"></a>Hardverállomás-bővítés kialakítása

A fiskális összekötő bővítmény célja a vezérlőegységgel való kommunikáció. A HTTP protokoll használatával elküldi a CRT bővítmény által létrehozott dokumentumokat a vezérlőegységnek. Kezeli a vezérlőegységtől kapott válaszokat is.

#### <a name="request-handler"></a>Kérelemkezelő

A **CleanCashHandler** kérelemkezelő a vezérlőegységhez intézett kérések kezelésének belépési pontja.

A kezelő az **INamedRequestHandler felületről öröklődik**. A **HandlerName** metódus felelős a kezelő nevének visszaadásáért. A kezelő nevének meg kell egyeznie a Kereskedelmi központban megadott pénzügyi összekötő nevével.

Az összekötő a következő kéréseket támogatja:

- **SubmitDocumentFiscalDeviceRequest** – Ez a kérés dokumentumokat küld a vezérlőegységnek, és választ ad vissza belőle.
- **IsReadyFiscalDeviceRequest** – Ez a kérés a vezérlőegység állapotfelmérésére szolgál.
- **InitializeFiscalDeviceRequest** – Ez a kérés a vezérlőegység inicializálására szolgál.

#### <a name="configuration"></a>Konfiguráció

A pénzügyi összekötő konfigurációs fájlja az **src\\FiscalIntegration\\CleanCash\\HardwareStation\\Connector.CleanCashSample\\Configuration\\ConnectorCleanCashSample.xml** helyen található a [Dynamics 365 Commerce Solutions](https://github.com/microsoft/Dynamics365Commerce.Solutions/) adattárban. A fájl célja, hogy engedélyezze a pénzügyi összekötő beállításait a Commerce központjából. A fájlformátum igazodik a pénzügyi integráció konfigurációjának követelményeihez.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
