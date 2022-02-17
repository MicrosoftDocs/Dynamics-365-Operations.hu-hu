---
title: Adóügyi nyomtató integrációját bemutató minta Olaszországra vonatkozóan
description: Ez a témakör áttekintést nyújt az olaszországi fiskális integrációs mintáról Microsoft Dynamics 365 Commerce.
author: EvgenyPopovMBS
ms.date: 12/20/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2018-11-1
ms.openlocfilehash: 02226fd9f2c92db2518ca48baefb680a3d2f0ac1
ms.sourcegitcommit: 5cefe7d2a71c6f220190afc3293e33e2b9119685
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/01/2022
ms.locfileid: "8076903"
---
# <a name="fiscal-printer-integration-sample-for-italy"></a>Adóügyi nyomtató integrációját bemutató minta Olaszországra vonatkozóan

[!include[banner](../includes/banner.md)]

Ez a témakör áttekintést nyújt az olaszországi fiskális integrációs mintáról Microsoft Dynamics 365 Commerce.

Az olaszországi Kereskedelmi funkció magában foglalja az értékesítési pont (POS) mintaintegrációját egy adónyomtatóval. A minta kiterjeszti a [fiskális integrációs funkcionalitás](fiscal-integration-for-retail-channel.md) hogy működjön együtt [Epson FP-90III sorozat](https://www.epson.it/products/sd/pos-printer/epson-fp-90iii-series) nyomtatókat az Epsontól, és lehetővé teszi a kommunikációt egy fiskális nyomtatóval webszerver módban az EpsonFPMate webszolgáltatáson keresztül a Fiscal ePOS-Print API használatával. A minta csak a Registratore Telematico (RT) módot támogatja. A minta forráskód formájában áll rendelkezésre, és a kiskereskedelmi szoftverfejlesztő készlet (SDK) része.

A Microsoft nem ad ki semmilyen hardvert, szoftvert vagy dokumentációt az Epsontól. Az adónyomtató beszerzésével és kezelésével kapcsolatos információkért forduljon a következőhöz: [Epson Italia SpA](https://www.epson.it)

## <a name="scenarios"></a>Forgatókönyvek

Az olaszországi adónyomtató-integrációs minta a következő forgatókönyveket fedi le:

- Értékesítési forgatókönyvek:

    - Nyomtasson ki egy adóbizonylatot a készpénzes eladásokról és visszaküldésekről.
    - Rögzítse a választ a fiskális nyomtatóról, és tárolja a csatornaadatbázisban.
    - Adók:

        - Leképezés az adónyomtató adószámaihoz (részlegeihez).
        - A leképezett adóadatok átvitele az adónyomtatóra.
        - Nyomtassa ki az adókat egy adóbizonylatra.

    - Kifizetések:

        - Térképezze fel az adónyomtató fizetési módjait.
        - Nyomtassa ki a kifizetéseket egy adóbizonylatra.
        - Nyomtassa ki a változási információkat.

    - Nyomtatási vonal kedvezmények.
    - Ajándékutalványok:

        - A kibocsátott/feltöltött ajándékkártya-sor kizárása az értékesítési bizonylatból.
        - Nyomtasson ki olyan fizetést, amely szokásos fizetési módként ajándékkártyát használ.

    - Nyomtassa ki a vevői rendelési műveletekhez tartozó pénzügyi bizonylatokat:

        - A vevő rendelési letétjéről nem nyomtatnak pénzügyi nyugtát.
        - Nyomtasson ki egy pénzügyi nyugtát a hibrid vevői rendelés teljesítési soraihoz.
        - Nyomtasson ki egy pénzügyi nyugtát a vevői rendelés átvételi műveletéről.
        - Nyomtasson ki egy fiskális nyugtát a visszaküldési megrendelésről.

    - Nyomtassa ki a számlaszám vonalkódját az adóbizonylatra.
    - Nyomtassa ki a [vásárlói információ](emea-ita-customer-information.md) amely egy értékesítési tranzakcióhoz van megadva egy adóbizonylaton. Ilyen információ például az ügyfél lottókódja. 

- Nap végi kimutatások (fiskális X és fiskális Z jelentések).
- Hibakezelés, például a következő lehetőségek:

    - Próbálkozzon újra a fiskális regisztrációval, ha lehetséges, például ha az adónyomtató nincs csatlakoztatva, nem áll készen vagy nem válaszol, a nyomtatóból kifogyott a papír, vagy papírelakadás van.
    - Az adóbejegyzés elhalasztása.
    - Hagyja ki a fiskális regisztrációt, vagy jelölje meg a tranzakciót regisztráltként, és adjon meg információs kódokat a hiba okának rögzítéséhez és további információkhoz.
    - Ellenőrizze az adónyomtató elérhetőségét, mielőtt új értékesítési tranzakciót nyitna vagy véglegesítene.

### <a name="gift-cards"></a>Ajándékutalványok

Az adónyomtató-integrációs minta a következő, ajándékkártyákkal kapcsolatos szabályokat valósítja meg:

- A következőhöz kapcsolódó értékesítési sorok kizárása *Ajándékkártya kiadása* és *Hozzáadás ajándékkártyához* műveleteket az adóbizonylatból.
- Ne nyomtasson pénzügyi nyugtát, ha az csak ajándékkártya-sorokból áll.
- A tranzakció során kibocsátott vagy újratöltött ajándékutalványok teljes összegét vonja le a pénzügyi nyugta fizetési soraiból.
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
- A napi jelentések (fiskális X és fiskális Z) az adónyomtató firmware-ébe ágyazott formátum használatával nyomtatódnak ki.
- Az adónyomtató nem támogatja a vegyes tranzakciókat. A **Tilos az értékesítés és a visszaküldés egy nyugtában keverése** opcióra kell állítani **Igen** a POS funkcióprofilokban.
- A minta csak a Registratore Telematico (RT) módban működő fiskális nyomtatóval támogatja az integrációt.

## <a name="set-up-fiscal-integration-for-italy"></a>Állítsa be a fiskális integrációt Olaszország számára

Az olaszországi fiskális nyomtató-integrációs minta a [fiskális integrációs funkcionalitás](fiscal-integration-for-retail-channel.md) és a Retail SDK része. A minta a **src\\ Fiskális integráció\\ EpsonFP90IIIMinta** mappa a [Dynamics 365 Commerce Megoldások](https://github.com/microsoft/Dynamics365Commerce.Solutions/) adattár (pl.[a minta kiadásban/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/EpsonFP90IIISample)). A minta [egy pénzügyi bizonylatszolgáltatóból áll](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services), amely a Commerce futtatókörnyezet (CRT) kiterjesztése, és egy fiskális összekötőből, amely a Commerce Hardware Station kiterjesztése. A Kiskereskedelmi SDK használatáról a Retail SDK architektúrája [és](../dev-itpro/retail-sdk/retail-sdk-overview.md) build-folyamat beállítása a független csomagolású SDK-hoz [című témakörben talál](../dev-itpro/build-pipeline.md) további információt.

> [!WARNING]
> Az új független csomagolási és kiterjesztési [modell](../dev-itpro/build-pipeline.md) korlátai miatt jelenleg nem használható ehhez a költségvetési integrációs mintához. A Retail SDK előző verzióját egy fejlesztői virtuális gépen (VM) kell használnia az Microsoft Dynamics Életciklus-szolgáltatásokban (LCS). További információkért lásd [Üzembe helyezési irányelvek a fiskális nyomtató integrációs mintájához Olaszországban (örökölt)](emea-ita-fpi-sample-sdk.md).
>
> A költségvetési integrációs minták új független csomagolási és kiterjesztési modelljének támogatását tervezik a későbbi verziókhoz.

Végezze el a fiskális integráció beállítási lépéseit az alábbiak szerint [Állítsa be a kereskedelmi csatornák pénzügyi integrációját](setting-up-fiscal-integration-for-retail-channel.md).

1. [Hozzon létre egy pénzügyi regisztrációs folyamatot](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process). Jegyezze fel a fiskális regisztrációs folyamat beállításait is [erre a fiskális nyomtató-integrációs mintára jellemző](#set-up-the-registration-process).
1. [Állítson be adószövegeket a kedvezményekhez](setting-up-fiscal-integration-for-retail-channel.md#set-up-fiscal-texts-for-discounts).
1. [Állítsa be a hibakezelési beállításokat](setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).
1. [Fiskális X/Z jelentések beállítása a POS-ból](setting-up-fiscal-integration-for-retail-channel.md#set-up-fiscal-xz-reports-from-the-pos).
1. [Az elhalasztott adóregisztráció](setting-up-fiscal-integration-for-retail-channel.md#enable-manual-execution-of-postponed-fiscal-registration) manuális végrehajtásának engedélyezése.
1. [Állítsa be az ügyféladatok kezelésének funkcióját a POS-ban](emea-ita-customer-information.md#setup).
1. [Csatornaösszetevők konfigurálása](#configure-channel-components).

### <a name="set-up-the-registration-process"></a>A regisztrációs folyamat beállítása

A regisztrációs folyamat engedélyezéséhez kövesse az alábbi lépéseket a Kereskedelmi központ beállításához. További információ: [A kereskedelmi csatornák](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process) pénzügyi integrációjának beállítása.

1. Konfigurációs fájlok letöltése a pénzügyi dokumentumszolgáltatóhoz és a pénzügyi összekötőhöz:

    1. Nyissa meg a [Dynamics 365 Commerce Megoldások](https://github.com/microsoft/Dynamics365Commerce.Solutions/) adattárat.
    1. Válassza ki a megfelelő kiadási ágverziót az SDK/alkalmazás verziója szerint (például **[release/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33)**).
    1. Nyisd ki **src \> Fiskális integráció \> EpsonFP90IIIMinta**.
    1. Töltse le az adódokumentum-szolgáltató konfigurációs fájlját a következő címről: **CommerceRuntime \> DocumentProvider.EpsonFP90IIISample \> Konfiguráció \> DocumentProviderEpsonFP90IIISample.xml** (például, [a kiadáshoz tartozó fájl/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/blob/release/9.33/src/FiscalIntegration/EpsonFP90IIISample/CommerceRuntime/DocumentProvider.EpsonFP90IIISample/Configuration/DocumentProviderEpsonFP90IIISample.xml)).
    1. Töltse le a fiskális csatlakozó konfigurációs fájlját a következő címről: **HardwareStation \> EpsonFP90IIIFiscalDeviceSample \> Konfiguráció \> CsatlakozóEpsonFP90IIISample.xml** (például, [a kiadáshoz/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/blob/release/9.33/src/FiscalIntegration/EpsonFP90IIISample/HardwareStation/EpsonFP90IIIFiscalDeviceSample/Configuration/ConnectorEpsonFP90IIISample.xml).

    > [!WARNING]
    > Az új független csomagolási és kiterjesztési [modell](../dev-itpro/build-pipeline.md) korlátai miatt jelenleg nem használható ehhez a költségvetési integrációs mintához. A Retail SDK előző verzióját kell használnia egy fejlesztői virtuális gépen az LCS-ben. A pénzügyi integrációs minta konfigurációs fájljai a Retail SDK következő mappáiban találhatók egy fejlesztői virtuális gépen az LCS-ben:
    >
    > - **Fiskális dokumentum-szolgáltató konfigurációs fájlja:** RetailSdk\\ SampleExtensions\\ CommerceRuntime\\ Extension.DocumentProvider.EpsonFP90IIISample\\ Konfiguráció\\ DocumentProviderEpsonFP90IIISample.xml
    > - **Fiskális csatlakozási konfigurációs fájl:** RetailSdk\\ SampleExtensions\\ HardwareStation\\ Extension.EpsonFP90IIIFiscalDeviceSample\\ Konfiguráció\\ CsatlakozóEpsonFP90IIISample.xml
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

- **Pályázati típus leképezés** – Az üzlet számára konfigurált fizetési módok hozzárendelése a fiskális nyomtató által támogatott fizetési típusokhoz. A következő példa az alapértelmezett leképezést mutatja be.

    ```JSON
    {"PaymentMethods": [
        {"StorePaymentMethod":"1", "PrinterPaymentType":"0", "PrinterPaymentIndex":"00"},
        {"StorePaymentMethod":"3", "PrinterPaymentType":"2", "PrinterPaymentIndex":"00"},
        {"StorePaymentMethod":"4", "PrinterPaymentType":"2", "PrinterPaymentIndex":"01"},
        {"StorePaymentMethod":"6", "PrinterPaymentType":"0", "PrinterPaymentIndex":"01"},
        {"StorePaymentMethod":"8", "PrinterPaymentType":"6", "PrinterPaymentIndex":"01"}
        ],
        "DepositPaymentMethod": {"PrinterPaymentType":"2", "PrinterPaymentIndex":"00"}}
    ```

    Itt található a leképezés attribútumainak magyarázata:

    - **StorePayment Method** egy fizetési mód, amely a címen található üzlet számára van beállítva **Kiskereskedelem és kereskedelem \> Csatorna beállítása \> Fizetési módok \> Fizetési módok**.
    - **PrinterPaymentType** és **PrinterPaymentIndex** az Epson fiscal nyomtató dokumentációjában meghatározott megfelelő fizetési típus és index.
    - **Betétfizetési mód** a nyomtató fizetési típusának és indexének megadására szolgál a vevői rendelés átvételi összegének azon részére, amely az ügyfél megrendelési előlegével kerül kiegyenlítésre.

    A következő táblázat bemutatja, hogy a fizetési módok mintaleképezése hogyan felel meg a szabványos bemutató adatokban konfigurált bolti fizetési módoknak.

    | Kifizetési mód | Fizetési mód neve |
    |----------------|---------------------|
    | 1              | Készpénz                |
    | 3              | Kártya                |
    | 4              | Vevői számla    |
    | 6              | Pénznem            |
    | 8              | Ajándékutalvány           |

    Módosítania kell a mintaleképezést az alkalmazásban konfigurált fizetési módoknak megfelelően.

- **Vonalkód típusa a nyugtaszámhoz** – Az a vonalkód típusa, amely a számlaszámot az adóbizonylaton megjeleníti. Az alapértelmezett leképezés a **KÓD128**.
- **Nyomtassa ki a pénzügyi adatokat a nyugta fejlécében** – Ha ez a paraméter be van kapcsolva, az üzlet információi kinyomtatásra kerülnek az adóbizonylatra. Ez az információ tartalmazza az üzlet nevét, címét és adóazonosító jelét, valamint a pénztáros nevét.
- **Pénzügyi nyomtató részleg feltérképezése** – A fiskális nyomtató részlegeinek hozzárendelése az általános forgalmi adó (áfa) kulcsokhoz, áfamentességekhez és terméktípusokhoz. A következő példa az alapértelmezett leképezést mutatja be.

    ```JSON
    {"Departments": [
        {"VATRate":"2200", "VATExemptNature":"", "ProductType":"0", "DepartmentNumber":"01"},
        {"VATRate":"2200", "VATExemptNature":"", "ProductType":"1", "DepartmentNumber":"02"},
        {"VATRate":"1000", "VATExemptNature":"", "ProductType":"0", "DepartmentNumber":"03"},
        {"VATRate":"1000", "VATExemptNature":"", "ProductType":"1", "DepartmentNumber":"04"},
        {"VATRate":"0500", "VATExemptNature":"", "ProductType":"0", "DepartmentNumber":"05"},
        {"VATRate":"0500", "VATExemptNature":"", "ProductType":"1", "DepartmentNumber":"06"},
        {"VATRate":"0400", "VATExemptNature":"", "ProductType":"0", "DepartmentNumber":"07"},
        {"VATRate":"0400", "VATExemptNature":"", "ProductType":"1", "DepartmentNumber":"08"},
        {"VATRate":"0000", "VATExemptNature":"", "ProductType":"0", "DepartmentNumber":"09"},
        {"VATRate":"0000", "VATExemptNature":"", "ProductType":"1", "DepartmentNumber":"10"},
        {"VATRate":"0000", "VATExemptNature":"NS", "ProductType":"0", "DepartmentNumber":"99"}]}
    ```

    Itt található a leképezés attribútumainak magyarázata:

    - **Áfakulcs** egy támogatott áfakulcs, amely forgalmi adó kódként van konfigurálva. A leképezésben szereplő érték két tizedesjegyet tartalmaz, de nincs tizedeselválasztó. Például, **2200** 22 százalékot jelent, és **1000** 10 százalékot jelent.
    - **áfamentes természet** csak abban az esetben alkalmazandó, ha az áfa mértéke 0 (nulla), beleértve azokat az eseteket is, amikor nincs adó. Jelenleg **áfamentes természet** csak ajándékkártyák esetén támogatott, és a hozzárendelésben szereplő értéknek meg kell egyeznie a **VATExemptNatureForGiftCard** tulajdonság az XML konfigurációs fájlban.
    - **Terméktípus** a termék típusa. Egy érték **0** árukat és értékét képviseli **1** szolgáltatásokat képvisel.
    - **Osztály száma** a nyomtatóban konfigurált részleg száma, amely megfelel az előző három attribútumnak.

    Módosítania kell a mintaleképezést az alkalmazásban beállított áfakulcsoknak és az adónyomtatóban konfigurált megfelelő részlegeknek megfelelően.

- **ÁFA mentes természet ajándékutalványhoz** – Az ajándékutalvány kibocsátásakor vagy újratöltésekor alkalmazandó áfamentesség. Az értéknek meg kell felelnie a fiskális nyomtató részleg-leképezésében szereplő bejegyzésnek. Az alapértelmezett leképezés a **NS**.
- **Ingyenes tételek engedélyezése** – Ha ez a paraméter be van kapcsolva, a speciális *omaggio* A 100 százalékos kedvezménnyel rendelkező cikkek kedvezménykorrekciójának típusa engedélyezve van.
- **A visszaküldési eredet információs kódja** – Az az információs kód, amely a visszáru tranzakció eredetének rögzítésére szolgál, ha nincs megadva eredeti vásárlási nyugta. Ezt a paramétert a **Az eredeti értékesítési dátum információs kódja** és **Visszatérési eredet leképezése** paramétereket, hogy helyes üzenetet generáljon a fiskális nyugtában a visszáru tranzakció eredetéről, ha nem létezik eredeti értékesítési tranzakció. 

    Ezt az információs kódot úgy kell konfigurálni, hogy a felhasználó kiválaszthassa vagy megadhassa a visszaküldések egyik lehetséges eredetét az üzletekben. Például konfigurálható alkódok listájaként (pl **Vissza a helyszínről** vagy **Visszatérés a kioszkból**). A **Visszatérési eredet leképezése** A paraméter ezután az információs kód értékét az adónyomtató parancsává alakítja.

    A kiválasztott információs kód **A visszaküldési eredet információs kódja** kötelező infókódként kell beállítani, amely értékesítési tranzakciónként egyszer aktiválódik. Úgy kell hozzárendelni, mint a **Termék visszaküldése** információs kódot a POS funkcióprofilban, hogy az aktiválódjon, amikor a **Termék visszaküldése** művelet fut.

    Ehhez a leképezéshez nincs megadva alapértelmezett érték. Ki kell választania az alkalmazásban konfigurált információs kódot.

- **Az eredeti értékesítési dátum információs kódja** – Az az információs kód, amely a visszáru tranzakció eredeti értékesítési dátumának rögzítésére szolgál, ha nincs megadva eredeti vásárlási nyugta. Ezt a paramétert a **A visszaküldési eredet információs kódja** és **Visszatérési eredet leképezése** paramétereket, hogy helyes üzenetet generáljon a fiskális nyugtában a visszáru tranzakció eredetéről, ha nem létezik eredeti értékesítési tranzakció.

    Az információs kódot úgy kell beállítani, hogy a **Beviteli típus** mező értékre van állítva **Dátum**. Kötelező információs kódként kell konfigurálni, amely értékesítési tranzakciónként egyszer aktiválódik. Azt is hozzá kell rendelni a **Kapcsolt információs kód** a számára kiválasztott információs kódhoz **A visszaküldési eredet információs kódja** paramétert, így a két infókód egymás után indul el.

    Ehhez a leképezéshez nincs megadva alapértelmezett érték. Ki kell választania az alkalmazásban konfigurált információs kódot.

- **Visszatérési eredet leképezése** – A visszaküldési források leképezése, amely a visszáru tranzakció eredetének kinyomtatására szolgál, ha nincs megadva eredeti vételi bizonylat. Ezt a paramétert a **A visszaküldési eredet információs kódja** és **Az eredeti értékesítési dátum információs kódja** paramétereket, hogy megfelelő üzenetet generáljon a fiskális nyugtában a visszáru tranzakció eredetéről, ha nem létezik eredeti értékesítési tranzakció. A következő példa az alapértelmezett leképezést mutatja be.

    ```JSON
    {"ReturnOrigins": [
        {"ReturnOrigin":"1", "PrinterReturnOrigin":"POS"},
        {"ReturnOrigin":"2", "PrinterReturnOrigin":"ND"}
        ],
        "PrinterReturnOriginWithoutFiscalData":"POS"}
    ```

    Itt található a leképezés attribútumainak magyarázata:

    - **ReturnOrigin** az Ön üzleteiben a visszaküldések egyik lehetséges forrása. Az értéknek meg kell egyeznie a **A visszaküldési eredet információs kódja** paraméter.
    - **A PrinterReturnOrigin** a pénzügyi nyomtató által elfogadott visszatérési összetevők egyike (**POS**, **VR** vagy **ND**).
    - **PrinterReturnOriginWithoutFiscalData** az a visszatérési forrás, amelyet a pénzügyi nyomtató elfogad, és amely egy olyan eredeti értékesítési tranzakcióhoz kapcsolódó visszáru-tranzakciónak felel meg, amely nem rendelkezik kapcsolódó pénzügyi adatokkal, mert nem volt regisztrálva pénzügyi nyomtatón keresztül. Ebben az esetben az eredeti értékesítési dátumot az eredeti értékesítési tranzakció dátumaként azonosítja a termék.

A következő alapértelmezett adatleképezések elavultak, és csak a visszamenőleges kompatibilitás érdekében maradnak meg:

- Hozzáadottérték-adó (ÁFA) kódok leképezése
- Letét fizetési típusa

#### <a name="fiscal-connector-settings"></a>Pénzügyi összekötő beállításai

A költségvetési integrációs minta részeként megadott pénzügyi összekötő konfiguráció a következő beállításokat tartalmazza:

- **Végpont címe** – A nyomtató URL-címe.
- **Dátum és idő szinkronizálása** – Egy érték, amely megadja, hogy a nyomtató dátumát és idejét szinkronizálni kell-e a csatlakoztatott hardverállomással.

### <a name="configure-channel-components"></a>Csatornaösszetevők konfigurálása

> [!WARNING]
> Az új független csomagolási és kiterjesztési [modell](../dev-itpro/build-pipeline.md) korlátai miatt jelenleg nem használható ehhez a költségvetési integrációs mintához. A Retail SDK előző verzióját kell használnia egy fejlesztői virtuális gépen az LCS-ben. További információkért lásd [Üzembe helyezési irányelvek a fiskális nyomtató integrációs mintájához Olaszországban (örökölt)](emea-ita-fpi-sample-sdk.md).
>
> A költségvetési integrációs minták új független csomagolási és kiterjesztési modelljének támogatását tervezik a későbbi verziókhoz.

#### <a name="set-up-the-development-environment"></a>A fejlesztési környezet beállítása

A minta tesztelésére és kiterjesztésére vonatkozó fejlesztési környezet beállításához kövesse az alábbi lépéseket.

1. Klónozza vagy töltse le a [Dynamics 365 Commerce Solutions](https://github.com/microsoft/Dynamics365Commerce.Solutions) adattárat. Válassza ki a megfelelő kiadási ágverziót az SDK/alkalmazás verziójának megfelelően. További információkért lásd [Töltsön le Retail SDK-mintákat és referenciacsomagokat a GitHubból és a NuGet](../dev-itpro/retail-sdk/sdk-github.md).
1. Nyissa meg a pénzügyi nyomtatóintegrációs megoldást a **Dynamics365Commerce.Solutions\\FiscalIntegration\\EpsonFP90IIISample\\EpsonFP90IIISample.sln**, és építse meg.
1. Telepítés CRT kiterjesztések:

    1. Találd meg CRT bővítmény telepítő:

        - **Commerce Scale Unit:** Az **EpsonFP90IIISample\\ScaleUnit\\ScaleUnit.EpsonFP90III.Installer\\bin\\Debug\\net461** mappában keresse meg a **ScaleUnit.EpsonFP90III.Installer** telepítőt.
        - **Helyi CRT a modern POS:** Az **EpsonFP90IIISample\\ModernPOS\\ModernPOS.EpsonFP90III.Installer\\bin\\Debug\\net461** mappát, keresse meg a **ModernPOS.EpsonFP90III.Installer** telepítő.

    1. Indítsa el a CRT kiterjesztés telepítője a parancssorból:

        - **Kereskedelmi mértékegység:**

            ```Console
            ScaleUnit.EpsonFP90III.Installer.exe install --verbosity 0
            ```

        - **Helyi CRT a modern POS-on:**

            ```Console
            ModernPOS.EpsonFP90III.Installer.exe install --verbosity 0
            ```

1. Hardverállomás-bővítmények telepítése:

    1. Az **EpsonFP90IIISample\\HardwareStation\\HardwareStation.EpsonFP90III.Installer\\bin\\Debug\\net461** mappában keresse meg a **HardwareStation.EpsonFP90III.Installer** telepítőt.
    1. Indítsa el a bővítménytelepítőt a parancssorból:

        ```Console
        HardwareStation.EpsonFP90III.Installer.exe install --verbosity 0
        ```

#### <a name="production-environment"></a>Működési környezet

Kövesse a lépéseket [Állítson be egy összeállítási folyamatot a fiskális integrációs mintához](fiscal-integration-sample-build-pipeline.md) a Cloud Scale Unit és az önkiszolgáló telepíthető csomagok létrehozása és kiadása a költségvetési integrációs mintához. Az **EpsonFP90IIIi build-pipeline.yml** sablon YAML fájl megtalálható a **Pipeline\\ YAML_Files** mappában a [Dynamics 365 Commerce Solutions](https://github.com/microsoft/Dynamics365Commerce.Solutions) adattár.

## <a name="design-of-extensions"></a>Bővítések tervezése

Az olaszországi fiskális nyomtató-integrációs minta a [fiskális integrációs funkcionalitás](fiscal-integration-for-retail-channel.md) és a Retail SDK része. A minta a **src\\ Fiskális integráció\\ EpsonFP90IIIMinta** mappa a [Dynamics 365 Commerce Megoldások](https://github.com/microsoft/Dynamics365Commerce.Solutions/) adattár (pl.[a minta kiadásban/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/EpsonFP90IIISample)). A minta [áll](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services) egy fiskális dokumentumszolgáltató, amely a kiterjesztése CRT és egy fiskális csatlakozó, amely a Commerce Hardware Station kiterjesztése. A Kiskereskedelmi SDK használatáról a Retail SDK architektúrája [és](../dev-itpro/retail-sdk/retail-sdk-overview.md) build-folyamat beállítása a független csomagolású SDK-hoz [című témakörben talál](../dev-itpro/build-pipeline.md) további információt.

> [!WARNING]
> Az új független csomagolási és kiterjesztési [modell](../dev-itpro/build-pipeline.md) korlátai miatt jelenleg nem használható ehhez a költségvetési integrációs mintához. A Retail SDK előző verzióját kell használnia egy fejlesztői virtuális gépen az LCS-ben. További információkért lásd [Üzembe helyezési irányelvek a fiskális nyomtató integrációs mintájához Olaszországban (örökölt)](emea-ita-fpi-sample-sdk.md). A költségvetési integrációs minták új független csomagolási és kiterjesztési modelljének támogatását tervezik a későbbi verziókhoz.

### <a name="commerce-runtime-extension-design"></a>Kereskedelmi futásidejű bővítmény tervezése

Az adódokumentum-szolgáltató bővítmény célja, hogy nyomtató-specifikus dokumentumokat állítson elő, és kezelje a fiskális nyomtatótól érkező válaszokat.

#### <a name="request-handler"></a>Kérelemkezelő

A **DocumentProviderEpsonFP90III kérelemkezelő** a belépési pont a dokumentumok költségvetési nyomtatóról történő létrehozására irányuló kérelemhez.

A kezelő az **INamedRequestHandler felületről öröklődik**. A **HandlerName** metódus felelős a kezelő nevének visszaadásáért. A kezelő nevének meg kell egyeznie a Kereskedelmi központban megadott összekötő dokumentumszolgáltató nevével.

Az összekötő a következő kéréseket támogatja:

- **GetFiscalDocumentDocumentProviderRequest** – Ez a kérés információt tartalmaz arról, hogy milyen dokumentumot kell létrehozni. Nyomtatóspecifikus dokumentumot ad vissza, amelyet regisztrálni kell az adónyomtatóban.
- **GetSupportedRegistrableEventsDocumentProviderRequest** – Ez a kérés visszaadja az előfizetendő események listáját. Jelenleg a következő események támogatottak: értékesítés, X-jelentés nyomtatása és Z-jelentés nyomtatása.

#### <a name="configuration"></a>Konfiguráció

A pénzügyi dokumentumszolgáltató konfigurációs fájlja az **src\\FiscalIntegration\\EpsonFP90IIISample\\CommerceRuntime\\DocumentProvider.EpsonFP90IIISample\\Configuration\\DocumentProviderEpsonFP90IIISample.xml** található a [Dynamics 365 Commerce Solutions](https://github.com/microsoft/Dynamics365Commerce.Solutions/) adattárban. A fájl célja, hogy engedélyezze a dokumentumszolgáltató beállításait a Commerce központjából. A fájlformátum igazodik a pénzügyi integráció konfigurációjának követelményeihez.

### <a name="hardware-station-extension-design"></a>Hardverállomás-bővítés kialakítása

A fiskális összekötő bővítmény célja a fiskális nyomtatóval való kommunikáció. Ez a bővítmény a HTTP protokollt használja a CRT bővítmény által generált dokumentumok pénzügyi nyomtatóra történő küldéséhez. Kezeli a költségvetési nyomtatótól kapott válaszokat is.

#### <a name="request-handler"></a>Kérelemkezelő

Az **EpsonFP90IIIISample** kérelemkezelő a fiskális perifériára irányuló kérések kezelési pontját.

A kezelő az **INamedRequestHandler felületről öröklődik**. A **HandlerName** metódus felelős a kezelő nevének visszaadásáért. A kezelő nevének meg kell egyeznie a Kereskedelmi központban megadott pénzügyi összekötő nevével.

Az összekötő a következő kéréseket támogatja:

- **SubmitDocumentFiscalDeviceRequest** – Ez a kérelem dokumentumokat küld a nyomtatóknak, és visszaadja a válaszát a költségvetési nyomtatóról.
- **IsReadyFiscalDeviceRequest** – Ez a kérés az eszköz állapotfelmérésére szolgál.
- **InitializeFiscalDeviceRequest** – Ez a kérés a nyomtató inicializálásához használatos.

#### <a name="configuration"></a>Konfiguráció

A költségvetési összekötő konfigurációs fájlja az **src\\FiscalIntegration\\EpsonFP90IIISample\\HardwareStation\\EpsonFP90IIIFiscalDeviceSample\\Configuration\\ConnectorEpsonFP90IIISample.xml** található a [Dynamics 365 Commerce Solutions](https://github.com/microsoft/Dynamics365Commerce.Solutions/) adattárban. A fájl célja, hogy engedélyezze az összekötő beállításait a Commerce központjából. A fájlformátum igazodik a pénzügyi integráció konfigurációjának követelményeihez.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
