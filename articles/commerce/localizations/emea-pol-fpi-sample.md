---
title: Adóügyi nyomtató integrációját bemutató minta Lengyelországra vonatkozóan
description: Ez a témakör áttekintést nyújt a lengyelországi költségvetési integrációs mintáról Microsoft Dynamics 365 Commerce.
author: EvgenyPopovMBS
ms.date: 12/20/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2019-2-1
ms.openlocfilehash: 43d9a54334d97a65a1f9a356daf54154f6c069b3
ms.sourcegitcommit: 5cefe7d2a71c6f220190afc3293e33e2b9119685
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/01/2022
ms.locfileid: "8076836"
---
# <a name="fiscal-printer-integration-sample-for-poland"></a>Adóügyi nyomtató integrációját bemutató minta Lengyelországra vonatkozóan

[!include[banner](../includes/banner.md)]

Ez a témakör áttekintést nyújt a lengyelországi költségvetési integrációs mintáról Microsoft Dynamics 365 Commerce.

A Dynamics 365 Commerce A lengyelországi funkcionalitás magában foglalja az értékesítési pont (POS) mintaintegrációját egy adónyomtatóval. A minta kiterjeszti a [fiskális integrációs funkcionalitás](fiscal-integration-for-retail-channel.md) és támogatja a POSNET THERMAL HD 2.02 protokollt a pénzügyi nyomtatókhoz [Posnet Polska SA](https://www.posnet.com.pl) A minta lehetővé teszi a kommunikációt egy olyan adónyomtatóval, amely natív szoftver-illesztőprogram segítségével COM-porton keresztül csatlakozik. A Posnet által a Posnet Thermal HD FV EJ fiskális nyomtatóhoz biztosított szoftveremulátor segítségével valósították meg és tesztelték. A minta forráskód formájában áll rendelkezésre, és a kiskereskedelmi szoftverfejlesztő készlet (SDK) része.

A Microsoft nem ad ki semmilyen hardvert, szoftvert vagy dokumentációt a Posnettől. Az adónyomtató beszerzésével és kezelésével kapcsolatos információkért forduljon a következőhöz: [Posnet Polska SA](https://www.posnet.com.pl)

## <a name="scenarios"></a>Forgatókönyvek

A lengyelországi adónyomtató-integrációs minta a következő forgatókönyveket fedi le:

- Értékesítési forgatókönyvek:

    - Nyomtasson ki egy adóbizonylatot a készpénzes eladásokról és visszaküldésekről.
    - Rögzítse a választ a fiskális nyomtatóról, és tárolja a csatornaadatbázisban.
    - Adók:

        - Leképezés az adónyomtató adószámaihoz (részlegeihez).
        - A leképezett adóadatok átvitele az adónyomtatóra.

    - Kifizetések:

        - Térképezze fel az adónyomtató fizetési módjait.
        - Nyomtassa ki a kifizetéseket egy adóbizonylatra.
        - Nyomtassa ki a változási információkat.

    - Nyomtatási vonal kedvezmények.
    - Ajándékutalványok:

        - A kibocsátott/újra felszámított ajándékkártya-sor kizárása az eladásról szóló adóbizonylatból.
        - Nyomtasson ki olyan fizetést, amely szokásos fizetési módként ajándékkártyát használ.

    - Nyomtassa ki a vevői rendelési műveletekhez tartozó pénzügyi bizonylatokat:

        - A vevő rendelési letétjéről nem nyomtatnak pénzügyi nyugtát.
        - Nyomtasson ki egy pénzügyi bizonylatot a hibrid vevői rendelés teljesítési sorairól.
        - Nyomtasson ki egy pénzügyi nyugtát a vevői rendelés átvételi műveletéről.
        - Nyomtasson ki egy fiskális nyugtát a visszaküldési megrendelésről.

    - Nyomtassa ki a [vásárlói információ](emea-pol-customer-information.md) amely egy értékesítési tranzakcióhoz van megadva egy adóbizonylaton. Ilyen információ például az ügyfél adószáma.

- Nap végi kimutatások (fiskális X és fiskális Z jelentések).
- Hibakezelés, például a következő lehetőségek:

    - Próbálkozzon újra a fiskális regisztrációval, ha lehetséges, például ha az adónyomtató nincs csatlakoztatva, nincs készen vagy nem válaszol, a nyomtatóból kifogyott a papír, vagy papírelakadás van.
    - Az adóbejegyzés elhalasztása.
    - Hagyja ki a fiskális regisztrációt, vagy jelölje meg a tranzakciót regisztráltként, és adjon meg információs kódokat a hiba okának rögzítéséhez és további információkhoz.
    - Ellenőrizze az adónyomtató elérhetőségét, mielőtt új értékesítési tranzakciót nyitna vagy véglegesítene.

### <a name="gift-cards"></a>Ajándékutalványok

Az adónyomtató-integrációs minta a következő, ajándékkártyákkal kapcsolatos szabályokat valósítja meg:

- A következőhöz kapcsolódó értékesítési sorok kizárása *Ajándékkártya kiadása* és *Hozzáadás ajándékkártyához* műveleteket az adóbizonylatból.
- Ne nyomtasson pénzügyi nyugtát, ha az csak ajándékkártya-sorokból áll.
- A tranzakció során kibocsátott vagy újraterhelt ajándékutalványok teljes összegét vonja le a pénzügyi nyugta fizetési soraiból.
- Mentse el a fizetési sorok kiszámított korrekcióit a csatornaadatbázisban a megfelelő fiskális tranzakcióra való hivatkozással.
- Az ajándékkártyás fizetés rendszeres fizetésnek minősül.

### <a name="customer-deposits-and-customer-order-deposits"></a>Vevői betétek és vevői megrendelések betétei

Az adónyomtató-integrációs minta a következő szabályokat valósítja meg, amelyek az ügyfelek betéteire és a vevői megrendelések betéteire vonatkoznak:

- Ne nyomtasson fiskális nyugtát, ha a tranzakció az ügyfél letétje.
- Ne nyomtasson adóbizonylatot, ha egy tranzakció csak a vevői rendelés letétjét vagy a vevői rendelés letéti visszatérítését tartalmazza.
- Nyomtassa ki a korábban befizetett letét összegét a vevői rendelés felvételi műveletének pénzügyi bizonylatára.
- Hibrid vevői rendelés létrehozásakor vonja le a vevői rendelés letéti összegét a fizetési sorokból.
- Mentse el a fizetési sorok kiszámított kiigazításait a csatornaadatbázisban egy hibrid vevői megrendelés fiskális tranzakciójára való hivatkozással.

### <a name="limitations-of-the-sample"></a>A minta korlátai

- Az adónyomtató csak azokat a forgatókönyveket támogatja, amelyeknél az ár tartalmazza a forgalmi adót. Ezért a **Az ár forgalmi adót tartalmaz** opcióra kell állítani **Igen** üzleteknek és vásárlóknak egyaránt.
- A napi jelentések (fiskális X és fiskális Z) nyomtatása a beágyazott használatával történik *Műszaki jelentés* formátum.
- A vonalkód nyomtatása az adóbizonylatokra potenciális testreszabásnak tekinthető, mivel ez a funkció a beágyazott formátumokban nem támogatott, és csak a testreszabható **Szuper formátum** jelentés.
- Az adónyomtató nem támogatja a vegyes tranzakciókat. A **Tilos az értékesítés és a visszaküldés egy nyugtában keverése** opcióra kell állítani **Igen** a POS funkcióprofilokban.

## <a name="set-up-fiscal-integration-for-poland"></a>Fiskális integráció létrehozása Lengyelország számára

A lengyelországi fiskális nyomtató-integrációs minta a [fiskális integrációs funkcionalitás](fiscal-integration-for-retail-channel.md) és a Retail SDK része. A minta a **src\\ Fiskális integráció\\ Posnet** mappa a [Dynamics 365 Commerce Megoldások](https://github.com/microsoft/Dynamics365Commerce.Solutions/) adattár (pl.[a minta kiadásban/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/Posnet)). A minta [egy pénzügyi bizonylatszolgáltatóból áll](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services), amely a Commerce futtatókörnyezet (CRT) kiterjesztése, és egy fiskális összekötőből, amely a Commerce Hardware Station kiterjesztése. A Kiskereskedelmi SDK használatáról a Retail SDK architektúrája [és](../dev-itpro/retail-sdk/retail-sdk-overview.md) build-folyamat beállítása a független csomagolású SDK-hoz [című témakörben talál](../dev-itpro/build-pipeline.md) további információt.

> [!WARNING]
> Az új független csomagolási és kiterjesztési [modell](../dev-itpro/build-pipeline.md) korlátai miatt jelenleg nem használható ehhez a költségvetési integrációs mintához. A Retail SDK előző verzióját egy fejlesztői virtuális gépen (VM) kell használnia az Microsoft Dynamics Életciklus-szolgáltatásokban (LCS). További információkért lásd [Üzembe helyezési irányelvek a lengyelországi adónyomtató-integrációs mintához (örökölt)](emea-pol-fpi-sample-sdk.md).
>
> A költségvetési integrációs minták új független csomagolási és kiterjesztési modelljének támogatását tervezik a későbbi verziókhoz.

Végezze el a fiskális integráció beállítási lépéseit az alábbiak szerint [Állítsa be a kereskedelmi csatornák pénzügyi integrációját](setting-up-fiscal-integration-for-retail-channel.md).

1. [Hozzon létre egy pénzügyi regisztrációs folyamatot](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process). Jegyezze fel a fiskális regisztrációs folyamat beállításait is [erre a fiskális nyomtató-integrációs mintára jellemző](#set-up-the-registration-process).
1. [Állítsa be a hibakezelési beállításokat](setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).
1. [Fiskális X/Z jelentések beállítása a POS-ból](setting-up-fiscal-integration-for-retail-channel.md#set-up-fiscal-xz-reports-from-the-pos).
1. [Az elhalasztott adóregisztráció](setting-up-fiscal-integration-for-retail-channel.md#enable-manual-execution-of-postponed-fiscal-registration) manuális végrehajtásának engedélyezése.
1. [Csatornaösszetevők konfigurálása](#configure-channel-components).

### <a name="set-up-the-registration-process"></a>A regisztrációs folyamat beállítása

A regisztrációs folyamat engedélyezéséhez kövesse az alábbi lépéseket a Kereskedelmi központ beállításához. További információ: [A kereskedelmi csatornák](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process) pénzügyi integrációjának beállítása.

1. Konfigurációs fájlok letöltése a pénzügyi dokumentumszolgáltatóhoz és a pénzügyi összekötőhöz:

    1. Nyissa meg a [Dynamics 365 Commerce Megoldások](https://github.com/microsoft/Dynamics365Commerce.Solutions/) adattárat.
    1. Válassza ki a megfelelő kiadási ágverziót az SDK/alkalmazás verziója szerint (például **[release/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33)**).
    1. Nyisd ki **src \> Fiskális integráció \> Posnet**.
    1. Töltse le az adódokumentum-szolgáltató konfigurációs fájlját a következő címről: **CommerceRuntime \> DocumentProvider.PosnetSample \> Konfiguráció \> DocumentProviderPosnetSample.xml** (például, [a kiadáshoz tartozó fájl/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/blob/release/9.33/src/FiscalIntegration/Posnet/CommerceRuntime/DocumentProvider.PosnetSample/Configuration/DocumentProviderPosnetSample.xml)).
    1. Töltse le a fiskális csatlakozó konfigurációs fájlját a következő címről: **HardwareStation \> ThermalDeviceSample \> Konfiguráció \> ConnectorPosnetThermalFVEJ.xml** (például, [a kiadáshoz tartozó fájl/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/blob/release/9.33/src/FiscalIntegration/Posnet/HardwareStation/ThermalDeviceSample/Configuration/ConnectorPosnetThermalFVEJ.xml)).

    > [!WARNING]
    > Az új független csomagolási és kiterjesztési [modell](../dev-itpro/build-pipeline.md) korlátai miatt jelenleg nem használható ehhez a költségvetési integrációs mintához. A Retail SDK előző verzióját kell használnia egy fejlesztői virtuális gépen az LCS-ben. A pénzügyi integrációs minta konfigurációs fájljai a Retail SDK következő mappáiban találhatók egy fejlesztői virtuális gépen az LCS-ben:
    >
    > - **Fiskális dokumentum-szolgáltató konfigurációs fájlja:** RetailSdk\\ SampleExtensions\\ CommerceRuntime\\ Extension.DocumentProvider.PosnetSample\\ Konfiguráció\\ DocumentProviderPosnetSample.xml
    > - **Fiskális csatlakozási konfigurációs fájl:** RetailSdk\\ SampleExtensions\\ HardwareStation\\ Extension.Posnet.ThermalDeviceSample\\ Konfiguráció\\ ConnectorPosnetThermalFVEJ.xml
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

- **Általános forgalmi adó (áfa) kulcsok feltérképezése** – A forgalmiadó-kódokhoz beállított adószázalék-értékek hozzárendelése adónyomtató-specifikus áfakulcsokhoz. Íme az alapértelmezett leképezés:

    ```
    0 : 23.00 ; 1 : 8.00 ; 2 : 5.00 ; 3 : 0.00
    ```

    Az egyes párok első összetevője az adónyomtatóban konfigurált áfakulcsszámot jelöli. A második összetevő a megfelelő héakulcsot képviseli. Az adónyomtató áfakulcs-konfigurációjával kapcsolatos további információkért tekintse meg a POSNET illesztőprogram dokumentációját.

- **Pályázati típus leképezés** – Az üzlet számára konfigurált fizetési módok hozzárendelése az adónyomtató által támogatott fizetési űrlapokhoz. Íme az alapértelmezett leképezés:

    ```
    0 : 0 ; 1 : 0 ; 2 : 2 ; 3 : 2 ; 4 : 0 ; 5 : 0 ; 6 : 0 ; 7 : 2 ; 8 : 0
    ```

    Az egyes párok első összetevője az üzlet számára beállított fizetési módot jelöli. A második összetevő az adónyomtató által támogatott megfelelő fizetési módot képviseli. Az adónyomtató által támogatott fizetési formákkal kapcsolatos további információkért tekintse meg a POSNET illesztőprogram dokumentációját. Módosítania kell a mintaleképezést az alkalmazásban konfigurált fizetési módoknak megfelelően.

#### <a name="fiscal-connector-settings"></a>Pénzügyi összekötő beállításai

A költségvetési integrációs minta részeként megadott pénzügyi összekötő konfiguráció a következő beállításokat tartalmazza:

- **Csatlakozási karakterlánc** – Egy karakterlánc, amely leírja az eszközzel való kapcsolat részleteit az illesztőprogram által támogatott formátumban. További információért tekintse meg a POSNET illesztőprogram dokumentációját.
- **Dátum és idő szinkronizálása** – Egy érték, amely megadja, hogy a nyomtató dátumát és idejét szinkronizálni kell-e a csatlakoztatott hardverállomással.
- **Eszköz időtúllépése** – Az az idő, ezredmásodpercben, ameddig a vezető vár az eszköztől érkező válaszra. További információért tekintse meg a POSNET illesztőprogram dokumentációját.

### <a name="configure-channel-components"></a>Csatornaösszetevők konfigurálása

> [!WARNING]
> Az új független csomagolási és kiterjesztési [modell](../dev-itpro/build-pipeline.md) korlátai miatt jelenleg nem használható ehhez a költségvetési integrációs mintához. A Retail SDK előző verzióját kell használnia egy fejlesztői virtuális gépen az LCS-ben. További információkért lásd [Üzembe helyezési irányelvek a lengyelországi adónyomtató-integrációs mintához (örökölt)](emea-pol-fpi-sample-sdk.md).
>
> A költségvetési integrációs minták új független csomagolási és kiterjesztési modelljének támogatását tervezik a későbbi verziókhoz.

#### <a name="set-up-the-development-environment"></a>A fejlesztési környezet beállítása

A minta tesztelésére és kiterjesztésére vonatkozó fejlesztési környezet beállításához kövesse az alábbi lépéseket.

1. Klónozza vagy töltse le a [Dynamics 365 Commerce Solutions](https://github.com/microsoft/Dynamics365Commerce.Solutions) adattárat. Válassza ki a megfelelő kiadási ágverziót az SDK/alkalmazás verziójának megfelelően. További információkért lásd [Töltsön le Retail SDK-mintákat és referenciacsomagokat a GitHubból és a NuGet](../dev-itpro/retail-sdk/sdk-github.md).
1. Nyissa meg a fiskális nyomtató-integrációs megoldást a következő címen: **Dynamics365Commerce.Solutions\\ Fiskális integráció\\ Posnet\\ Posnet.sln**, és megépíteni.
1. Telepítés CRT kiterjesztések:

    1. Találd meg CRT bővítmény telepítő:

        - **Kereskedelmi mértékegység:** Ban,-ben **Posnet\\ ScaleUnit\\ ScaleUnit.Posnet.Installer\\ kuka\\ Debug\\ net461** mappát, keresse meg a **ScaleUnit.Posnet.Installer** telepítő.
        - **Helyi CRT a modern POS-on:** Ban,-ben **Posnet\\ Modern POS\\ ModernPOS.Posnet.Installer\\ kuka\\ Debug\\ net461** mappát, keresse meg a **ModernPOS.Posnet.Installer** telepítő.

    1. Indítsa el a CRT kiterjesztés telepítője a parancssorból:

        - **Kereskedelmi mértékegység:**

            ```Console
            ScaleUnit.Posnet.Installer.exe install --verbosity 0
            ```

        - **Helyi CRT a modern POS-on:**

            ```Console
            ModernPOS.Posnet.Installer.exe install --verbosity 0
            ```

1. Hardverállomás-bővítmények telepítése:

    1. Ban,-ben **Posnet\\ HardwareStation\\ HardwareStation.PosnetThermalFVFiscalPrinter.Installer\\ kuka\\ Debug\\ net461** mappát, keresse meg a **HardwareStation.PosnetThermalFVFiscalPrinter.Installer** telepítő.
    1. Indítsa el a bővítménytelepítőt a parancssorból:

        ```Console
        HardwareStation.PosnetThermalFVFiscalPrinter.Installer.exe install --verbosity 0
        ```

#### <a name="production-environment"></a>Működési környezet

Kövesse a lépéseket [Állítson be egy összeállítási folyamatot a fiskális integrációs mintához](fiscal-integration-sample-build-pipeline.md) a Cloud Scale Unit és az önkiszolgáló telepíthető csomagok létrehozása és kiadása a költségvetési integrációs mintához. A **Posnet build-pipeline.yml** sablon YAML fájl megtalálható a **Csővezeték\\ YAML_Files** mappa a [Dynamics 365 Commerce Megoldások](https://github.com/microsoft/Dynamics365Commerce.Solutions) adattár.

## <a name="design-of-extensions"></a>Bővítések tervezése

A lengyelországi fiskális nyomtató-integrációs minta a [fiskális integrációs funkcionalitás](fiscal-integration-for-retail-channel.md) és a Retail SDK része. A minta a **src\\ Fiskális integráció\\ Posnet** mappa a [Dynamics 365 Commerce Megoldások](https://github.com/microsoft/Dynamics365Commerce.Solutions/) adattár (pl.[a minta kiadásban/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/Posnet)). A minta [áll](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services) egy fiskális dokumentumszolgáltató, amely a kiterjesztése CRT és egy fiskális csatlakozó, amely a Commerce Hardware Station kiterjesztése. A Kiskereskedelmi SDK használatáról a Retail SDK architektúrája [és](../dev-itpro/retail-sdk/retail-sdk-overview.md) build-folyamat beállítása a független csomagolású SDK-hoz [című témakörben talál](../dev-itpro/build-pipeline.md) további információt.

> [!WARNING]
> Az új független csomagolási és kiterjesztési [modell](../dev-itpro/build-pipeline.md) korlátai miatt jelenleg nem használható ehhez a költségvetési integrációs mintához. A Retail SDK előző verzióját kell használnia egy fejlesztői virtuális gépen az LCS-ben. További információkért lásd [Üzembe helyezési irányelvek a lengyelországi adónyomtató-integrációs mintához (örökölt)](emea-pol-fpi-sample-sdk.md). A költségvetési integrációs minták új független csomagolási és kiterjesztési modelljének támogatását tervezik a későbbi verziókhoz.

### <a name="commerce-runtime-extension-design"></a>Kereskedelmi futásidejű bővítmény tervezése

Az adódokumentum-szolgáltató bővítmény célja, hogy nyomtató-specifikus dokumentumokat állítson elő, és kezelje a fiskális nyomtatótól érkező válaszokat. Ez a bővítmény nyomtatóspecifikus parancsokat hoz létre JavaScript Object Notation (JSON) formátumban, amelyeket a POSNET 19-3678-as specifikációja határoz meg.

#### <a name="request-handler"></a>Kérelemkezelő

A **DocumentProviderPosnetProtocol** A kérelemkezelő a belépési pontja a dokumentumoknak az adónyomtatóból történő létrehozására irányuló kérelemnek.

A kezelő az **INamedRequestHandler felületről öröklődik**. A **HandlerName** metódus felelős a kezelő nevének visszaadásáért. A kezelő nevének meg kell egyeznie a Kereskedelmi központban megadott összekötő dokumentumszolgáltató nevével.

Az összekötő a következő kéréseket támogatja:

- **GetFiscalDocumentDocumentProviderRequest** – Ez a kérés információt tartalmaz arról, hogy milyen dokumentumot kell létrehozni. Nyomtatóspecifikus dokumentumot ad vissza, amelyet regisztrálni kell az adónyomtatóban.
- **GetSupportedRegistrableEventsDocumentProviderRequest** – Ez a kérés visszaadja az előfizetendő események listáját. Jelenleg a következő események támogatottak: értékesítés, X-jelentés nyomtatása és Z-jelentés nyomtatása.

#### <a name="configuration"></a>Konfiguráció

A pénzügyi dokumentumszolgáltató konfigurációs fájlja az **src\\FiscalIntegration\\Posnet\\CommerceRuntime\\DocumentProvider.PosnetSample\\Configuration\\DocumentProviderPosnetSample.xml** található a [Dynamics 365 Commerce Solutions](https://github.com/microsoft/Dynamics365Commerce.Solutions/) adattárban. A fájl célja, hogy lehetővé tegye a költségvetési dokumentumszolgáltató beállításainak konfigurálását a Commerce központjából. A fájlformátum igazodik a pénzügyi integráció konfigurációjának követelményeihez.

### <a name="hardware-station-extension-design"></a>Hardverállomás-bővítés kialakítása

A fiskális összekötő bővítmény célja a fiskális nyomtatóval való kommunikáció. Ez a bővítmény felkéri a POSNET-illesztőprogram funkcióit, hogy küldjenek el parancsokat, amelyeket a CRT bővítmény generál a költségvetési nyomtatónak. Az eszközhibákat is kezeli.

#### <a name="request-handler"></a>Kérelemkezelő

A **FiscalPrinterHandler** kérelemkezelő a kérelem pénzügyi perifériára irányuló kezelésének belépési pontja.

A kezelő az **INamedRequestHandler felületről öröklődik**. A **HandlerName** metódus felelős a kezelő nevének visszaadásáért. A kezelő nevének meg kell egyeznie a Kereskedelmi központban megadott pénzügyi összekötő nevével.

Az összekötő a következő kéréseket támogatja:

- **SubmitDocumentFiscalDeviceRequest** – Ez a kérelem dokumentumokat küld a nyomtatóknak, és visszaadja a válaszát a költségvetési nyomtatóról.
- **IsReadyFiscalDeviceRequest** – Ez a kérés az eszköz állapotfelmérésére szolgál.
- **InitializeFiscalDeviceRequest** – Ez a kérés a nyomtató inicializálásához használatos.

#### <a name="configuration"></a>Konfiguráció

A fiscal connector konfigurációs fájlja az **src\\FiscalIntegration\\Posnet\\HardwareStation\\ThermalDeviceSample\\Configuration\\ConnectorPosnetThermalFVEJ.xml** található a [Dynamics 365 Commerce Solutions](https://github.com/microsoft/Dynamics365Commerce.Solutions/) adattárban. A fájl célja, hogy lehetővé tegye a pénzügyi összekötő beállításainak konfigurálását a Commerce központjából. A fájlformátum igazodik a pénzügyi integráció konfigurációjának követelményeihez.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
