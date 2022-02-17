---
title: Pénzügyi regisztrációs szolgáltatás integrációját bemutató minta Ausztriára vonatkozóan
description: Ez a témakör áttekintést nyújt Ausztria fiskális integrációs mintájáról Microsoft Dynamics 365 Commerce.
author: EvgenyPopovMBS
ms.date: 12/20/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2019-3-1
ms.openlocfilehash: d720bffb98965bdc0276660d2a2e50d2bf155e74
ms.sourcegitcommit: 5cefe7d2a71c6f220190afc3293e33e2b9119685
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/01/2022
ms.locfileid: "8077165"
---
# <a name="fiscal-registration-service-integration-sample-for-austria"></a>Pénzügyi regisztrációs szolgáltatás integrációját bemutató minta Ausztriára vonatkozóan

[!include[banner](../includes/banner.md)]

Ez a témakör áttekintést nyújt Ausztria fiskális integrációs mintájáról Microsoft Dynamics 365 Commerce.

A pénztárgépekre vonatkozó helyi adókövetelmények teljesítése érdekében Ausztriában a Dynamics 365 Retail Az Ausztriára vonatkozó funkcionalitás magában foglalja az értékesítési pont (POS) mintaintegrációját egy külső adóregisztrációs szolgáltatással. A minta kiterjeszti a [fiskális integrációs funkcionalitás](fiscal-integration-for-retail-channel.md). Azon alapul [EFR (elektronikus adónyilvántartás)](https://www.efsta.eu/at/fiskalloesungen/oesterreich) megoldástól [EFSTA](https://www.efsta.eu/at/) és lehetővé teszi a kommunikációt az EFR szolgáltatással a HTTPS protokollon keresztül. Az EFR szolgáltatásnak vagy a Retail Hardware állomáson vagy egy különálló gépen kell lennie, amelyhez a hardver állomásról lehet csatlakozni. A minta forráskód formájában áll rendelkezésre, és a kiskereskedelmi szoftverfejlesztő készlet (SDK) része.

A Microsoft nem ad ki semmilyen hardvert, szoftvert vagy dokumentációt az EFSTA-tól. Az EFR megoldás beszerzésével és üzemeltetésével kapcsolatos információkért forduljon a következőhöz: [EFSTA](https://www.efsta.eu/at/kontakt).

## <a name="scenarios"></a>Forgatókönyvek

Az adóregisztrációs szolgáltatás Ausztriára vonatkozó integrációs mintája a következő forgatókönyveket fedi le:

- Készpénzes tranzakciók nyilvántartása az adónyilvántartási szolgáltatásban:

    - Küldje el a részletes tranzakciós adatokat az adóregisztrációs szolgáltatásnak. Ezek az adatok az értékesítési vonalra vonatkozó információkat, valamint a kedvezményekkel, kifizetésekkel és adókkal kapcsolatos információkat tartalmaznak.
    - Válasz rögzítése az adóregisztrációs szolgáltatástól. Ez a válasz tartalmaz egy digitális aláírást és egy hivatkozást a regisztrált tranzakcióhoz.
    - Regisztrálja az adókat, és rendelje hozzá őket az adóregisztrációs szolgáltatás adószámaihoz.
    - Nyomtassa ki a regisztrált tranzakció QR-kódját a nyugtára.

- Ajándékkártya-műveletek és vásárlói betétek nem készpénzes tranzakcióként történő nyilvántartása az adónyilvántartási szolgáltatásban:

    - Ajándékkártya kibocsátása vagy pénz hozzáadása.
    - Ügyfélszámla befizetés regisztrálása.
    - Ügyfélrendelési letét regisztrálása.

- Nem értékesítési tranzakciók és események nem készpénzes tranzakcióként történő nyilvántartása az adónyilvántartási szolgáltatásban:

    - Műszak megnyitása és műszak bezárása
    - Kezdő összeg, úszó bejegyzés és pályázat eltávolítása
    - Ár felülbírálása
    - Adó felülírása
    - Nyugtamásolat kinyomtatása
    - Fiók kinyitása
    - X-jelentés nyomtatása
    - Z-jelentés nyomtatás

- Ausztriára jellemző mezőkkel rendelkező nap végi kimutatások (X/Z jelentések) nyomtatása:

    - Az ügyfeleknek szállított termékek vagy szolgáltatások teljes száma
    - Az árbevétel adókulcs szerinti bontása
    - A befizetések pénztáros/pénztárgépkezelő szerinti bontása
    - Árengedmények és visszatérítések, amelyek csökkentik a napi eladásokat
    - Nulla értékesítés (ajándékozás)

- Hibakezelés, például a következő lehetőségek:

    - Próbálkozzon újra a fiskális regisztrációval, ha lehetséges, például ha az adóregisztrációs szolgáltatás nem elérhető, nem áll készen vagy nem válaszol.
    - Az adóbejegyzés elhalasztása.
    - Hagyja ki a fiskális regisztrációt, vagy jelölje meg a tranzakciót regisztráltként, és adjon meg információs kódokat a hiba okának rögzítéséhez és további információkhoz.
    - Ellenőrizze az adóregisztrációs szolgáltatás elérhetőségét, mielőtt új értékesítési tranzakciót nyitna vagy véglegesítene.

### <a name="gift-cards"></a>Ajándékutalványok

Az adóregisztrációs szolgáltatás integrációs mintája a következő, ajándékkártyákkal kapcsolatos szabályokat valósítja meg:

- A következőhöz kapcsolódó értékesítési sorok kizárása *Ajándékkártya kiadása* és *Hozzáadás ajándékkártyához* készpénzes tranzakcióból származó műveletek. Ahelyett, hogy ezeket a sorokat készpénzes tranzakció részeként regisztrálná, regisztrálja őket külön, nem készpénzes tranzakcióként az adónyilvántartási szolgáltatásban.
- Ne nyomtasson adócsoport bontást és QR-kódot a nyugtára, ha a nyugta csak ajándékkártya-sorokból áll.
- Nyomtassa ki a tranzakció során kibocsátott vagy újraterhelt ajándékutalványok teljes összegét a készpénzes tranzakció összegétől elkülönítve a nyugtán.
- Mentse el a fizetési sorok kiszámított korrekcióit a csatornaadatbázisban a megfelelő fiskális tranzakcióra való hivatkozással.
- Az ajándékkártyás fizetés rendszeres fizetésnek minősül.

### <a name="customer-deposits-and-customer-order-deposits"></a>Vevői betétek és vevői megrendelések betétei

A fiskális regisztrációs szolgáltatás integrációs mintája a következő szabályokat valósítja meg, amelyek az ügyfelek betéteire és az ügyfél megrendelési betéteire vonatkoznak:

- Regisztráljon nem készpénzes tranzakciót, ha a tranzakció ügyfél befizetése.
- Nem készpénzes tranzakciót regisztrálhat, ha egy tranzakció csak vevői rendelési letétet vagy vevői rendelési betét-visszatérítést tartalmaz.
- Hibrid vevői rendelés létrehozásakor vonja le a vevői rendelés letéti összegét a fizetési sorokból.
- Mentse el a fizetési sorok kiszámított kiigazításait a csatornaadatbázisban egy hibrid vevői megrendelés fiskális tranzakciójára való hivatkozással.

### <a name="limitations-of-the-sample"></a>A minta korlátai

Az adóregisztrációs szolgáltatás csak azokat a forgatókönyveket támogatja, amelyeknél az ár tartalmazza a forgalmi adót. Ezért a **Az ár forgalmi adót tartalmaz** opcióra kell állítani **Igen** üzleteknek és vásárlóknak egyaránt.

## <a name="set-up-commerce-for-austria"></a>A Commerce beállítása Ausztriához

Ez a szakasz az Ausztriára jellemző és az ott javasolt Kereskedelmi beállításokat írja le. További információért a beállítási információkért lásd: [Kereskedelmi főoldal](../index.md).

Az Ausztriára jellemző funkciók használatához a következő beállításokat kell megadnia:

- A jogi személy elsődleges címében állítsa be a **Ország/régió** mezőt **AUT** (Ausztria).
- Minden Ausztriában található üzlet POS funkcióprofiljában állítsa be a **ISO kód** mezőt **NÁL NÉL** (Ausztria).

A következő beállításokat is meg kell adnia Ausztriára vonatkozóan. Vegye figyelembe, hogy a telepítés befejezése után megfelelő terjesztési feladatokat kell futtatnia.

### <a name="set-up-vat-per-austrian-requirements"></a>Állítsa be az áfát az osztrák követelményeknek megfelelően

Létre kell hoznia áfakódokat, áfacsoportokat és cikkek forgalmiadó-csoportjait. Ezenkívül be kell állítania a forgalmi adóval kapcsolatos információkat a termékekhez és szolgáltatásokhoz. A forgalmiadó-szolgáltatások beállításával és használatával kapcsolatos további információkért lásd: [A forgalmi adó áttekintése](../../finance/general-ledger/indirect-taxes-overview.md).

Az értékesítési bizonylatokon kinyomtathatja a forgalmi adó kódjának rövidített kódját (például "A" vagy "B"). A funkció elérhetővé tételéhez állítsa be a **Nyomtassa ki a kódot** mező a **A forgalmi adó kódjai** oldalon.

### <a name="set-up-stores"></a>Üzletek létrehozása

A **Minden üzlet** oldalon, frissítse az üzlet adatait. Pontosabban állítsa be a következő paramétereket:

- Ban,-ben **Forgalmi adó csoport** mezőben adja meg az áfacsoportot, amelyet az alapértelmezett vevőnek történő értékesítéshez kell használni.
- Állítsa be a **Az árak tartalmazzák a forgalmi adót** opciót **Igen**.
- Állítsa be a **Név** mezőbe a cég nevét. Ez a változtatás segít garantálni, hogy a cégnév megjelenjen az értékesítési bizonylaton. Alternatív megoldásként hozzáadhatja a cég nevét az értékesítési bizonylat elrendezéséhez szabad formátumú szövegként.
- Állítsa be a **Adóazonosító szám (TIN)** mezőben a cégazonosító számra. Ez a változtatás segít garantálni, hogy a cégazonosító szám megjelenjen az értékesítési bizonylaton. Alternatív megoldásként hozzáadhatja a cégazonosító számot az értékesítési bizonylat elrendezéséhez szabad formátumú szövegként.

### <a name="set-up-functionality-profiles"></a>Funkcióprofilok beállítása

POS funkcióprofilok beállítása:

- A **Nyugta számozás** FastTab, állítsa be a nyugtaszámozást a rekordok létrehozásával vagy frissítésével **Eladás**, **rendelés**, és **Visszatérés** átvételi tranzakció típusok.

### <a name="configure-custom-fields-so-that-they-can-be-used-in-receipt-formats-for-sales-receipts"></a>Állítsa be az egyéni mezőket úgy, hogy azokat az értékesítési bizonylatok nyugtaformátumaiban lehessen használni

Beállíthatja a POS nyugtaformátumokban használt nyelvi szöveget és egyéni mezőket. A nyugtabeállítást létrehozó felhasználó alapértelmezett cégének ugyanannak a jogi személynek kell lennie, mint ahol a nyelvi szövegbeállítás létrejött. Alternatív megoldásként ugyanazokat a nyelvű szövegeket kell létrehozni a felhasználó alapértelmezett vállalatában és annak az áruháznak a jogi személyében, amelyhez a beállítást létrehozták.

A **Nyelvi szöveg** oldalon adja hozzá a következő rekordokat a nyugtaelrendezések egyéni mezőinek címkéihez. Vegye figyelembe, hogy a **Nyelvazonosító**, **azonosító**, és **Szöveg** a táblázatban szereplő értékek csak példák. Módosíthatja őket, hogy megfeleljenek az Ön igényeinek. Azonban a **Szöveges azonosító** A használt értékeknek egyedinek kell lenniük, és egyenlőnek vagy nagyobbaknak kell lenniük a 900001 értékkel.

Adja hozzá a következő POS-címkéket a **pozíció** szakasza **Nyelvi szöveg** a táblázatból:

| Nyelvazonosító | Szövegazonosító | Szöveg                      |
|-------------|---------|---------------------------|
| hu-US       | 900001  | QR-kód                   |
| hu-US       | 900002  | Folyamatos szám         |
| hu-US       | 900003  | Adó kiskereskedelmi nyomtatási kód     |
| hu-US       | 900004  | Összesen (értékesítés)             |
| hu-US       | 900005  | Teljes adó (értékesítés)         |
| hu-US       | 900006  | Összesen tartalmazza az adót (értékesítés) |
| hu-US       | 900007  | Adóösszeg (értékesítés)        |
| hu-US       | 900008  | Adóalap (értékesítés)         |

A **Egyéni mezők** oldalon adja hozzá a következő rekordokat a nyugtaelrendezések egyéni mezőihez. Vegye figyelembe, hogy **Felirat szövegének azonosítója** értékeknek meg kell felelniük a **Szöveges azonosító** oldalon megadott értékeket **Nyelvi szöveg** oldal:

| Név                 | Típus    | Képaláírás-szöveg azonosítója |
|----------------------|---------|-----------------|
| QR-KÓD               | Fogadás | 900001          |
| FOLYAMATOS SZÁM     | Fogadás | 900002          |
| KERESKEDELMI NYOMTATÁSI KÓD      | Fogadás | 900003          |
| SALESTOTAL           | Fogadás | 900004          |
| ÉRTÉKESÍTÉSI ADÓ        | Fogadás | 900005          |
| SALESTOTALINCLUDETAX | Fogadás | 900006          |
| ELADÁSI ÖSSZEG       | Fogadás | 900007          |
| ÉRTÉKESÍTÉSI ALAP        | Fogadás | 900008          |

> [!NOTE]
> Fontos, hogy helyes egyéni mezőneveket adjon meg, az előző táblázatban felsoroltak szerint. A helytelen egyéni mezőnév adatok hiányát okozza a nyugtákban.

### <a name="configure-receipt-formats"></a>Konfigurálja a nyugtaformátumokat

Minden szükséges nyugtaformátumnál módosítsa az értékét **Nyomtatási viselkedés** mezőt **Mindig nyomtasson**.

A Nyugtaformátum-tervezőben adja hozzá a következő egyéni mezőket a megfelelő nyugtarészekhez. Vegye figyelembe, hogy a mezőnevek megfelelnek az előző szakaszban megadott nyelvi szövegeknek.

- **Fejléc:** Adja hozzá a következő mezőket:

    - **Az üzlet neve** és **Adószám** mezők, amelyek segítségével a bizonylatokra nyomtatható a cégnév és az azonosító szám. Alternatív megoldásként hozzáadhatja a cégnevet és az azonosító számot az elrendezéshez szabad formátumú szövegként.
    - **Az üzlet címe**, **·**, **24 óra**, **száma**, és **Regisztrációs szám** mezőket.
    - **Folyamatos szám** mezőkben, hogy azonosítsa a készpénzes tranzakció számát az adónyilvántartási szolgáltatásban.

- **Sorok:** Adja hozzá a következő mezőket:

    - **Termék név**.
    - **Menny**.
    - **Teljes ár áfával**.
    - **Adó kiskereskedelmi nyomtatási kód**, amely a cikkre vonatkozó általános forgalmi adó kódjának megfelelő rövidített kód kinyomtatására szolgál.

- **Lábléc:** Adja hozzá a következő mezőket:

    - Fizetési mezők, így az egyes fizetési módokhoz tartozó fizetési összegek kinyomtatásra kerülnek. Például adja hozzá a **Pályázat neve** és **Pályázati összeg** mezőket az elrendezés egyik sorába.
    - **Eladások összesen** mezőcsoport:

        - **Összesen (eladások)** mező, amely a nyugta teljes készpénzes eladási összegének kinyomtatására szolgál. Az összeg az adót nem tartalmazza. Az előleg és az ajándékkártya műveletek nem tartoznak ide.
        - **Összesen tartalmazza az adót (értékesítés)** mező, amely a nyugta teljes készpénzes eladási összegének kinyomtatására szolgál. Az összeg tartalmazza az adót. Az előleg és az ajándékkártya műveletek nem tartoznak ide.
        - **Teljes adó (értékesítés)** mező, amely a készpénzes értékesítések bizonylatának teljes adóösszegének kinyomtatására szolgál. Az előleg és az ajándékkártya műveletek nem tartoznak ide.

    - **Az adó lebontása** mezőcsoport. Ebben a mezőcsoportban minden mezőt egy külön sorba kell nyomtatni.

        - **Adóazonosító** mező, amely egy szabványos mező, amely lehetővé teszi a forgalmi adó összesítésének nyomtatását az egyes áfakódokhoz. A mezőt egy új sorhoz kell hozzáadni.
        - **Adószázalék** mező, amely egy szabványos mező, amely a forgalmiadó-kód tényleges adókulcsának kinyomtatására szolgál.
        - **Adóalap (értékesítés)** mező, amely a nyugta teljes készpénzes eladási összegének kinyomtatására szolgál az áfa kódhoz. Az előleg és az ajándékkártya műveletek nem tartoznak ide.
        - **Adóösszeg (értékesítés)** mező, amely a forgalmi adó kódhoz tartozó készpénzes értékesítés nyugta adóösszegének kinyomtatására szolgál.
        - **Adó kiskereskedelmi nyomtatási kód** mező, amely a forgalmi adó kódjának megfelelő rövidített kód kinyomtatására szolgál.

    - **QR-kód** mező, amely a regisztrált készpénztranzakcióra való hivatkozás QR-kód formájában történő nyomtatására szolgál.

        > [!NOTE]
        > A **QR-kód** értéke a pénzügyi nyilvántartás válaszából származik. Az EFR csak akkor ad vissza QR-kódot a válaszában, ha az EFR konfiguráció Attribútumok **mezőjének értékét** az EFSTA dokumentáció ismerteti. Az EFR konfiguráció Attribútumok mezőjében a **QR-kódformátumot BMP-re** kell állítani **.**

A beérkezési formátumok működéséről a Beérkezési formátumok [beállítása és tervezése című témakörben talál](../receipt-templates-printing.md) további információt.

## <a name="set-up-fiscal-integration-for-austria"></a>Költségvetési integráció létrehozása Ausztria számára

Az ausztriai adóregisztrációs szolgáltatásintegrációs minta a [fiskális integrációs](fiscal-integration-for-retail-channel.md) funkción alapul, és a Retail SDK része. A minta a **Solutions\\ adattár srcFiscalIntegration\\Efr**[Dynamics 365 Commerce mappájában](https://github.com/microsoft/Dynamics365Commerce.Solutions/) található (például [a kiadási/9.33-as](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/Efr) minta). A minta [egy pénzügyi bizonylatszolgáltatóból áll](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services), amely a Commerce futtatókörnyezet (CRT) kiterjesztése, és egy fiskális összekötőből, amely a Commerce Hardware Station kiterjesztése. A Kiskereskedelmi SDK használatáról a Retail SDK architektúrája [és](../dev-itpro/retail-sdk/retail-sdk-overview.md) build-folyamat beállítása a független csomagolású SDK-hoz [című témakörben talál](../dev-itpro/build-pipeline.md) további információt.

> [!WARNING]
> Az új független csomagolási és kiterjesztési [modell](../dev-itpro/build-pipeline.md) korlátai miatt jelenleg nem használható ehhez a költségvetési integrációs mintához. A Retail SDK előző verzióját egy fejlesztői virtuális gépen (VM) kell használnia az Microsoft Dynamics Életciklus-szolgáltatásokban (LCS). További információ: [Az Ausztria (örökölt)](emea-aut-fi-sample-sdk.md) költségvetési integrációs mintájának telepítési irányelvei. A költségvetési integrációs minták új független csomagolási és kiterjesztési modelljének támogatását tervezik a későbbi verziókhoz.

Végezze el a költségvetési integráció beállítási lépéseit [a Kereskedelmi csatornák](setting-up-fiscal-integration-for-retail-channel.md) pénzügyi integrációjának beállítása:

1. [Hozzon létre egy pénzügyi regisztrációs folyamatot](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process). Jegyezze fel a pénzügyi regisztrációs folyamatnak [a pénzügyi regisztrációs szolgáltatásintegrációs mintájára](#set-up-the-registration-process) jellemző beállításait is.
1. [Állítsa be a hibakezelési beállításokat](setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).
1. [Az elhalasztott adóregisztráció](setting-up-fiscal-integration-for-retail-channel.md#enable-manual-execution-of-postponed-fiscal-registration) manuális végrehajtásának engedélyezése.
1. [Csatornaösszetevők konfigurálása](#configure-channel-components).

### <a name="set-up-the-registration-process"></a>A regisztrációs folyamat beállítása

A regisztrációs folyamat engedélyezéséhez kövesse az alábbi lépéseket a Kereskedelmi központ beállításához. További információ: [A kereskedelmi csatornák](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process) pénzügyi integrációjának beállítása.

1. Konfigurációs fájlok letöltése a pénzügyi dokumentumszolgáltatóhoz és a pénzügyi összekötőhöz:

    1. Nyissa meg a [Dynamics 365 Commerce Megoldások](https://github.com/microsoft/Dynamics365Commerce.Solutions/) adattárat.
    1. Válassza ki a megfelelő kiadási ágverziót az SDK/alkalmazás verziója szerint (például **[release/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33)**).
    1. Nyissa meg **az src \> FiscalIntegration \> Efr**.
    1. Nyissa meg a Configurations **DocumentProviders \> alkalmazást, és töltse le a pénzügyi dokumentumszolgáltató konfigurációs fájljait:** DocumentProviderFiscalEFRSampleAustria.xml **és** DocumentProviderNonFiscalEFRSampleAustria.xml **(például** a kiadáshoz szánt fájlok helye/9.33 [).](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/Efr/Configurations/DocumentProviders)
    1. Töltse le a pénzügyi összekötő konfigurációs fájlját a **Configurations \> Connectors \> ConnectorEFRSample.xml** (például [a kiadáshoz szükséges fájl/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/blob/release/9.33/src/FiscalIntegration/Efr/Configurations/Connectors/ConnectorEFRSample.xml)).

    > [!WARNING]
    > Az új független csomagolási és kiterjesztési [modell](../dev-itpro/build-pipeline.md) korlátai miatt jelenleg nem használható ehhez a költségvetési integrációs mintához. A Retail SDK előző verzióját kell használnia egy fejlesztői virtuális gépen az LCS-ben. A pénzügyi integrációs minta konfigurációs fájljai a Retail SDK következő mappáiban találhatók egy fejlesztői virtuális gépen az LCS-ben:
    >
    > - **Pénzügyi dokumentumszolgáltató konfigurációs fájljai:** RetailSdk\\SampleExtensions\\CommerceRuntime\\Extensions.DocumentProvider.EFRSample\\Configuration
    > - **Pénzügyi összekötő konfigurációs fájl:** RetailSdk\\SampleExtensions\\HardwareStation\\Extension.EFRSample\\Configuration
    > 
    > A költségvetési integrációs minták új független csomagolási és kiterjesztési modelljének támogatását tervezik a későbbi verziókhoz.

1. Lépjen a **Retail és Commerce \> Központ beállítása \> Paraméterek \> Commerce megosztott paraméterek** menüpontra. Az Általános **lapon állítsa a** Költségvetési integráció **engedélyezése beállítást Igen értékre** **.**
1. Lépjen a **Kiskereskedelmi és kereskedelmi \> csatorna beállítására \> Pénzügyi integráció \> Pénzügyi dokumentumszolgáltatók**, és töltse be a korábban letöltött pénzügyi dokumentumszolgáltató konfigurációs fájljait.
1. Lépjen a **Kiskereskedelmi és kereskedelmi \> csatorna beállítására \> Pénzügyi integráció \> Pénzügyi összekötők, és töltse be a korábban letöltött pénzügyi összekötő konfigurációs** fájlt.
1. Lépjen a **Kiskereskedelmi és kereskedelmi \> csatorna beállítására \> Pénzügyi integrációs \> összekötő funkcionális profiljai**. Hozzon létre két új összekötő funkcionális profilt, egyet minden korábban betöltött pénzügyi bizonylat-szolgáltatóhoz, és válassza ki a korábban betöltött pénzügyi összekötőt. Szükség szerint frissítse az [adatleképezési beállításokat](#default-data-mapping).
1. Lépjen a **Kiskereskedelmi és kereskedelmi \> csatorna beállítására \> Pénzügyi integráció \> Összekötő technikai profiljai**. Hozzon létre egy új összekötő műszaki profilját, és válassza ki a korábban betöltött pénzügyi összekötőt. Szükség szerint frissítse az [összekötő beállításait](#fiscal-connector-settings).
1. Lépjen a **Kiskereskedelem és kereskedelem \> csatorna beállítására \> Pénzügyi integráció \> Pénzügyi összekötő csoportok**. Hozzon létre két új pénzügyi összekötő csoportot, egyet minden összekötő funkcionális profiljához, amelyet korábban létrehozott.
1. Lépjen a **Kiskereskedelmi és kereskedelmi \> csatorna beállítására \> Pénzügyi integráció \> Pénzügyi regisztrációs folyamatok**. Hozzon létre egy új költségvetési regisztrációs folyamatot és két költségvetési regisztrációs folyamatot, és válassza ki a korábban létrehozott pénzügyi összekötő csoportokat.
1. Ugorjon a következő elemre: **Retail és Commerce \>  Csatorna beállítása \> Pénztárbeállítás \>  Pénztárprofilok \> Funkcióprofilok**. Válasszon ki egy olyan funkcióprofilt, amely ahhoz az üzlethez kapcsolódik, ahol a regisztrációs folyamatot aktiválni kell. **A Pénzügyi regisztrációs folyamat** gyorslapon válassza ki a korábban létrehozott pénzügyi regisztrációs folyamatot. A nem pénzügyi események POS-on történő regisztrációjának engedélyezéséhez a **Functions** FastTab POS **csoportban** állítsa a **Naplózás** opciót Igen **értékre**.
1. Lépjen a **Kiskereskedelem és kereskedelem \> Csatorna beállítás \> POS beállítás \> POS profilok \> Hardverprofilok** pontra. Válasszon ki egy hardverprofilt, amely ahhoz a hardverállomáshoz kapcsolódik, amelyhez a pénzügyi nyomtató csatlakozik. **A Pénzügyi perifériák** gyorslapon válassza ki a korábban létrehozott összekötő műszaki profilját.
1. Nyissa meg a terjesztési ütemezést (**Kiskereskedelmi és \> kereskedelmi kiskereskedelem és kereskedelem IT-terjesztési \> ütemezése**), és válassza az 1070-es és **1090-es** **feladatokat** az adatok csatornaadatbázisba történő átviteléhez.

#### <a name="default-data-mapping"></a>Alapértelmezett adatleképezés

A költségvetési integrációs minta részeként megadott pénzügyi bizonylatszolgáltató konfigurációja a következő alapértelmezett adatleképezést tartalmazza:

- **Hozzáadottérték-adó (ÁFA) díjak leképezése** – Az áfakódokhoz beállított adószázalékértékek leképezése a **TaxG** (adócsoport) attribútum értékeihez a adószolgáltatásnak küldött kérelmekben. Íme az alapértelmezett leképezés:

    ```
    A: 20.00; B: 10.00; C: 13.00; D: 0.00; E: 19.00; F: 7.00
    ```

    Az egyes párok első összetevője egy áfaadó-csoportot képvisel, amelyet az EFR adóregisztrációs szolgáltatás támogat. A második összetevő a megfelelő héakulcsot képviseli. Az EFR által Ausztria számára támogatott áfaadó-csoportokkal kapcsolatos további információkért tekintse meg az [EFR-hivatkozást](https://public.efsta.net/efr/).

#### <a name="fiscal-connector-settings"></a>Pénzügyi összekötő beállításai

A költségvetési integrációs minta részeként megadott pénzügyi összekötő konfiguráció a következő beállításokat tartalmazza:

- **Végpont címe** – A pénzügyi regisztrációs szolgáltatás URL-címe.
- **Eszköz időtúllépés** – Az az idő, ezredmásodpercben, ahány idő alatt a fiskális összekötő megvárja a pénzügyi regisztrációs szolgáltatás válaszát.
- **Adóregisztrációs** értesítések megjelenítése – Ez a jelző szabályozza, hogy a pénzügyi regisztrációs szolgáltatás visszaküldéséről szóló értesítések megjelenjenek-e az üzemeltetőnek.

### <a name="configure-channel-components"></a>Csatornaösszetevők konfigurálása

> [!WARNING]
> Az új független csomagolási és kiterjesztési [modell](../dev-itpro/build-pipeline.md) korlátai miatt jelenleg nem használható ehhez a költségvetési integrációs mintához. A Retail SDK előző verzióját kell használnia egy fejlesztői virtuális gépen az LCS-ben. További információ: [Az Ausztria (örökölt)](emea-aut-fi-sample-sdk.md) költségvetési integrációs mintájának telepítési irányelvei.
>
> A költségvetési integrációs minták új független csomagolási és kiterjesztési modelljének támogatását tervezik a későbbi verziókhoz.

#### <a name="set-up-the-development-environment"></a>A fejlesztési környezet beállítása

A minta tesztelésére és kiterjesztésére vonatkozó fejlesztési környezet beállításához kövesse az alábbi lépéseket.

1. Klónozza vagy töltse le a [Dynamics 365 Commerce Solutions](https://github.com/microsoft/Dynamics365Commerce.Solutions) adattárat. Válassza ki a megfelelő kiadási ágverziót az SDK/alkalmazás verziójának megfelelően. További információkért lásd [Töltsön le Retail SDK-mintákat és referenciacsomagokat a GitHubból és a NuGet](../dev-itpro/retail-sdk/sdk-github.md).
1. Nyissa meg az EFR-megoldást itt: **Dynamics365Commerce.Solutions\\ Fiskális integráció\\ Efr\\ EFR.sln**, és megépíteni.
1. Telepítés CRT kiterjesztések:

    1. Találd meg CRT bővítmény telepítő:

        - **Kereskedelmi mértékegység:** Ban,-ben **Efr\\ ScaleUnit\\ ScaleUnit.EFR.Installer\\ kuka\\ Debug\\ net461** mappát, keresse meg a **ScaleUnit.EFR.Installer** telepítő.
        - **Helyi CRT a modern POS-on:** Ban,-ben **Efr\\ Modern POS\\ ModernPOS.EFR.Installer\\ kuka\\ Debug\\ net461** mappát, keresse meg a **ModernPOS.EFR.Installer** telepítő.

    1. Indítsa el a CRT kiterjesztés telepítője a parancssorból:

        - **Kereskedelmi mértékegység:**

            ```Console
            ScaleUnit.EFR.Installer.exe install --verbosity 0
            ```

        - **Helyi CRT a modern POS-on:**

            ```Console
            ModernPOS.EFR.Installer.exe install --verbosity 0
            ```

1. Hardverállomás-bővítmények telepítése:

    1. Ban,-ben **Efr\\ HardwareStation\\ HardwareStation.EFR.Telepítő\\ kuka\\ Debug\\ net461** mappát, keresse meg a **HardwareStation.EFR.Telepítő** telepítő.
    1. Indítsa el a bővítménytelepítőt a parancssorból.

        ```Console
        HardwareStation.EFR.Installer.exe install --verbosity 0
        ```

#### <a name="production-environment"></a>Működési környezet

Kövesse a lépéseket [Állítson be egy összeállítási folyamatot a fiskális integrációs mintához](fiscal-integration-sample-build-pipeline.md) a Cloud Scale Unit és az önkiszolgáló telepíthető csomagok létrehozása és kiadása a költségvetési integrációs mintához. A **EFR build-pipeline.yml** sablon YAML fájl megtalálható a **Csővezeték\\ YAML_Files** mappa a [Dynamics 365 Commerce Megoldások](https://github.com/microsoft/Dynamics365Commerce.Solutions) adattár.

## <a name="design-of-extensions"></a>Bővítések tervezése

Az ausztriai adóregisztrációs szolgáltatásintegrációs minta a [fiskális integrációs](fiscal-integration-for-retail-channel.md) funkción alapul, és a Retail SDK része. A minta a **Solutions\\ adattár srcFiscalIntegration\\Efr**[Dynamics 365 Commerce mappájában](https://github.com/microsoft/Dynamics365Commerce.Solutions/) található (például [a kiadási/9.33-as](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/Efr) minta). A minta [áll](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services) egy fiskális dokumentumszolgáltató, amely a kiterjesztése CRT és egy fiskális csatlakozó, amely a Commerce Hardware Station kiterjesztése. A Kiskereskedelmi SDK használatáról a Retail SDK architektúrája [és](../dev-itpro/retail-sdk/retail-sdk-overview.md) build-folyamat beállítása a független csomagolású SDK-hoz [című témakörben talál](../dev-itpro/build-pipeline.md) további információt.

> [!WARNING]
> Az új független csomagolási és kiterjesztési [modell](../dev-itpro/build-pipeline.md) korlátai miatt jelenleg nem használható ehhez a költségvetési integrációs mintához. A Retail SDK előző verzióját kell használnia egy fejlesztői virtuális gépen az LCS-ben. További információ: [Az Ausztria (örökölt)](emea-aut-fi-sample-sdk.md) költségvetési integrációs mintájának telepítési irányelvei. A költségvetési integrációs minták új független csomagolási és kiterjesztési modelljének támogatását tervezik a későbbi verziókhoz.

### <a name="commerce-runtime-extension-design"></a>Kereskedelmi futásidejű bővítmény tervezése

Az adódokumentum-szolgáltató bővítmény célja szolgáltatás-specifikus dokumentumok előállítása és válaszok kezelése az adónyilvántartási szolgáltatástól.

#### <a name="request-handler"></a>Kérelemkezelő

Két kéréskezelő létezik a dokumentumszolgáltatók számára:

- **DocumentProviderEFRFiscalAUT** – Ez a kezelő adódokumentumok generálására szolgál az adóregisztrációs szolgáltatáshoz.
- **DocumentProviderEFRNonFiscalAUT** – Ez a kezelő nem adóügyi dokumentumok generálására szolgál az adóregisztrációs szolgáltatáshoz.

Ezeket a kezelőket a **INamedRequestHandler** felület. A **HandlerName** metódus felelős a kezelő nevének visszaadásáért. A kezelő nevének meg kell egyeznie a Kereskedelmi központban megadott összekötő dokumentumszolgáltató nevével.

Az összekötő a következő kéréseket támogatja:

- **GetFiscalDocumentDocumentProviderRequest** – Ez a kérés információt tartalmaz arról, hogy milyen dokumentumot kell létrehozni. Egy szolgáltatásspecifikus dokumentumot ad vissza, amelyet regisztrálni kell a pénzügyi regisztrációs szolgáltatásban.
- **GetNonFiscalDocumentDocumentProviderRequest** – Ez a kérelem információkat tartalmaz arról, hogy milyen nem pénzügyi dokumentumot kell létrehozni. Egy szolgáltatásspecifikus dokumentumot ad vissza, amelyet regisztrálni kell a pénzügyi regisztrációs szolgáltatásban.
- **GetSupportedRegistrableEventsDocumentProviderRequest** – Ez a kérés visszaadja az előfizetendő események listáját. Jelenleg a következő események támogatottak: értékesítés, X-jelentés nyomtatása, Z-jelentés nyomtatása, vevői számlabetétek, vevői rendelési betétek, auditesemények és nem értékesítési tranzakciók.
- **GetFiscalRegisterResponseToSaveDocumentProviderRequest** – Ez a kérelem a pénzügyi regisztrációs szolgáltatás válaszát adja vissza. Ez a válasz szerializálva karakterláncot képez, hogy készen álljon a mentésre.

#### <a name="configuration"></a>Konfiguráció

Az adódokumentum-szolgáltató konfigurációs fájljai a következő helyen találhatók: **src\\ Fiskális integráció\\ Efr\\ Konfigurációk\\ Dokumentumszolgáltatók** mappa a [Dynamics 365 Commerce Megoldások](https://github.com/microsoft/Dynamics365Commerce.Solutions/) adattár:

- **DocumentProviderFiscalEFRSampleAustria** – Az adódokumentumok adódokumentum-szolgáltatójának konfigurációs fájlja.
- **DocumentProviderNonFiscalEFRSampleAustria** – A nem fiskális bizonylatok adódokumentum-szolgáltatójának konfigurációs fájlja.

Ezeknek a fájloknak az a célja, hogy lehetővé tegyék az adódokumentum-szolgáltató beállításainak konfigurálását a Commerce központjából. A fájlformátum igazodik a pénzügyi integráció konfigurációjának követelményeihez.

### <a name="hardware-station-extension-design"></a>Hardverállomás-bővítés kialakítása

A költségvetési összekötő bővítmény célja a pénzügyi regisztrációs szolgáltatással való kommunikáció. A hardverállomás-bővítmény a HTTP protokollt használja az olyan dokumentumok benyújtására, amelyek a CRT kiterjesztést generál az adóregisztrációs szolgáltatáshoz. Kezeli továbbá a pénzügyi regisztrációs szolgáltatástól kapott válaszokat.

#### <a name="request-handler"></a>Kérelemkezelő

Az **EFRHandler** kérelemkezelője a belépési pont a pénzügyi regisztrációs szolgáltatáshoz benyújtott kérelmek kezeléséhez.

A kezelő az **INamedRequestHandler felületről öröklődik**. A **HandlerName** metódus felelős a kezelő nevének visszaadásáért. A kezelő nevének meg kell egyeznie a Kereskedelmi központban megadott pénzügyi összekötő nevével.

A fiskális összekötő a következő kéréseket támogatja:

- **SubmitDocumentFiscalDeviceRequest** – Ez a kérelem dokumentumokat küld a pénzügyi regisztrációs szolgálatnak, és visszaküldi a választ.
- **IsReadyFiscalDeviceRequest** – Ez a kérés a pénzügyi regisztrációs szolgáltatás állapotfelmérésére szolgál.
- **InitializeFiscalDeviceRequest** – Ez a kérés a pénzügyi regisztrációs szolgáltatás inicializálására szolgál.

#### <a name="configuration"></a>Konfiguráció

A fiskális csatlakozó konfigurációs fájlja a következő címen található: **src\\ Fiskális integráció\\ Efr\\ Konfigurációk\\ Csatlakozók\\ CsatlakozóEFRSample.xml** ban,-ben [Dynamics 365 Commerce Megoldások](https://github.com/microsoft/Dynamics365Commerce.Solutions/) adattár. A fájl célja, hogy lehetővé tegye a pénzügyi összekötő beállításainak konfigurálását a Commerce központjából. A fájlformátum igazodik a pénzügyi integráció konfigurációjának követelményeihez.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
