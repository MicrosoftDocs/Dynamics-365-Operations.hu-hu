---
title: Adóügyi regisztrációs szolgáltatás integrációs mintája a Cseh Köztársaságban
description: Ez a témakör áttekintést nyújt a Cseh Köztársaság fiskális integrációs mintájáról Microsoft Dynamics 365 Commerce.
author: EvgenyPopovMBS
ms.date: 12/20/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2019-4-1
ms.dyn365.ops.version: 10.0.2
ms.openlocfilehash: 990de96f57f4a22b4d58da5f970b1b96f5fc21f5
ms.sourcegitcommit: 5cefe7d2a71c6f220190afc3293e33e2b9119685
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/01/2022
ms.locfileid: "8077090"
---
# <a name="fiscal-registration-service-integration-sample-for-the-czech-republic"></a>Adóügyi regisztrációs szolgáltatás integrációs mintája a Cseh Köztársaságban

[!include[banner](../includes/banner.md)]

Ez a témakör áttekintést nyújt a Cseh Köztársaság fiskális integrációs mintájáról Microsoft Dynamics 365 Commerce.

A pénztárgépekre vonatkozó helyi adókövetelmények teljesítése érdekében a Cseh Köztársaságban a Dynamics 365 Commerce A Cseh Köztársaság funkcionalitása magában foglalja az értékesítési pont (POS) mintaintegrációját egy külső adóregisztrációs szolgáltatással. A minta kiterjeszti a [fiskális integrációs funkcionalitás](fiscal-integration-for-retail-channel.md). Azon alapul [EFR (elektronikus adónyilvántartás)](https://efsta.org/sicherheitsloesungen/) megoldástól [EFSTA](https://efsta.org/) és lehetővé teszi a kommunikációt az EFR szolgáltatással a HTTPS protokollon keresztül. Az EFR szolgáltatás biztosítja az értékesítések elektronikus regisztrációját (EET - Elektronická bizonyíték tržeb), azaz az értékesítési adatok online továbbítását az adóhatóság adóhatósági webszolgáltatásához.

Az EFR szolgáltatást a Commerce Hardware állomáson vagy egy különálló gépen kell tárolni, amelyhez a hardver állomásról lehet csatlakozni. A minta forráskód formájában áll rendelkezésre, és a kiskereskedelmi szoftverfejlesztő készlet (SDK) része.

A Microsoft nem ad ki semmilyen hardvert, szoftvert vagy dokumentációt az EFSTA-tól. Az EFR megoldás beszerzésével és üzemeltetésével kapcsolatos információkért forduljon a következőhöz: [EFSTA](https://efsta.org/kontakt/).

## <a name="scenarios"></a>Forgatókönyvek

A Cseh Köztársaságra vonatkozó adóregisztrációs szolgáltatás integrációs mintája a következő forgatókönyveket fedi le.

- Készpénzes tranzakciók nyilvántartása az adónyilvántartási szolgáltatásban.

    - Küldje el a részletes tranzakciós adatokat az adóregisztrációs szolgáltatásnak. Ezek az adatok az értékesítési vonalra vonatkozó információkat, valamint a kedvezményekkel, kifizetésekkel és adókkal kapcsolatos információkat tartalmaznak. Az adónyilvántartási szolgáltatás továbbküldi az adatokat az adóhatóság webszolgáltatásának, és onnan visszaigazolást kap, amely tartalmazza az ügylet adóazonosító kódját.
    - Válasz rögzítése az adóregisztrációs szolgáltatástól. Ez a válasz olyan adózási adatokat tartalmaz, mint az adóazonosító kód és a tranzakció biztonsági kódja stb.
    - Nyomtassa ki egy regisztrált tranzakció fiskális adatait a nyugtára.

- Ajándékkártya-műveletek és ügyfélbetétek nyilvántartása az adónyilvántartási szolgáltatásban.

    - Ajándékkártya kibocsátása vagy pénz hozzáadása.
    - Ügyfélszámla befizetés regisztrálása.
    - Hozzon létre egy vásárlói rendelést, és regisztráljon letétet a megrendeléshez.
    - Szerkessze az ügyfél megrendelését, és írja felül a rendelés letétjét.
    - Törölje az ügyfél megrendelését és térítse vissza a rendelés előlegét.

- Hibakezelés, például a következő lehetőségek.

    - Próbálkozzon újra a fiskális regisztrációval, ha lehetséges, például ha az adóregisztrációs szolgáltatás nem elérhető, nem áll készen vagy nem válaszol.
    - Az adóbejegyzés elhalasztása.
    - Hagyja ki a fiskális regisztrációt, vagy jelölje meg a tranzakciót regisztráltként, és adjon meg információs kódokat a hiba okának rögzítéséhez és további információkhoz.
    - Ellenőrizze az adóregisztrációs szolgáltatás elérhetőségét, mielőtt új értékesítési tranzakciót nyitna vagy véglegesítene.

### <a name="gift-cards"></a>Ajándékutalványok

A fiskális regisztrációs szolgáltatás integrációs mintája a következő, ajándékkártyákhoz kapcsolódó szabályokat valósítja meg.

- Értékesítési vonalak, amelyek kapcsolódnak a *Ajándékkártya kiadása* vagy *Hozzáadás ajándékkártyához* az értékesítési tranzakciók műveletei egy speciális attribútummal vannak megjelölve, amikor a tranzakciót regisztrálják az adóregisztrációs szolgáltatásban.
- Az ajándékkártyával történő fizetés normál fizetésnek minősül, és speciális attribútummal van megjelölve, amikor a tranzakciót az adónyilvántartási szolgáltatásban regisztrálják.

### <a name="customer-account-deposits-and-customer-order-deposits"></a>Ügyfélszámla befizetések és vevői rendelési betétek

Az adóregisztrációs szolgáltatás integrációs mintája a következő szabályokat valósítja meg, amelyek az ügyfélszámla-betétekkel és az ügyfélmegrendelés-betétekkel kapcsolatosak.

- Az ügyfélszámla betéthez vagy vevői megbízási betéthez kapcsolódó tranzakció egysoros tranzakcióként kerül rögzítésre az adónyilvántartási szolgáltatásban, és speciális attribútummal van megjelölve. Ebben a sorban van megadva a betéti áfacsoport.
- Hibrid vevői rendelés létrehozásakor, azaz olyan vevői megrendelés esetén, amely a vevő által az üzletből kivihető termékeket, valamint a későbbiekben átvételre vagy kiszállításra kerülő termékeket tartalmaz, a tranzakciót az adónyilvántartási szolgáltatásban rögzítik. sorokat tartalmaz az elvégzett termékekhez, valamint egy sort a rendelési letéthez.
- Az ügyfélszámláról történő fizetés normál befizetésnek minősül, és speciális attribútummal van megjelölve, amikor a tranzakciót az adóregisztrációs szolgáltatásban regisztrálják.
- A vevői rendelés letéti összege, amelyet az ügyfél megrendelésére alkalmaznak *Felvenni* A művelet rendszeres fizetésnek minősül, és speciális attribútummal van megjelölve, amikor a tranzakciót az adónyilvántartási szolgáltatásban regisztrálják.

### <a name="offline-registration"></a>Offline regisztráció

Ha az adóregisztrációs szolgáltatás nem továbbítja a tranzakciós adatokat az adóhatóság fiskális webszolgáltatásának (például a válaszidőtúllépés miatt), és nem kap visszaigazolást a webszolgáltatástól (azaz a tranzakció adóazonosító kódját),, helyi aláírást generál a tranzakcióhoz, és azt, valamint egy speciális hibakódot tartalmaz a válaszban. Az adóregisztrációs szolgáltatás az eredeti sorrendben újraküldi a tranzakciókat a háttérben, amint a hálózati kapcsolat helyreáll.

### <a name="limitations-of-the-sample"></a>A minta korlátai

Az adóregisztrációs szolgáltatás csak azokat a forgatókönyveket támogatja, amelyeknél az ár tartalmazza a forgalmi adót. Ezért a **Az ár forgalmi adót tartalmaz** opcióra kell állítani **Igen** üzleteknek és vásárlóknak egyaránt.

## <a name="set-up-commerce-for-the-czech-republic"></a>A Commerce beállítása a Cseh Köztársaság számára

Ez a rész a Cseh Köztársaságra jellemző és a Cseh Köztársaság számára ajánlott Kereskedelmi beállításokat ismerteti. További információkért lásd [Kereskedelmi főoldal](../index.md).

A cseh-specifikus funkciók használatához a következő beállításokat kell megadnia.

- A jogi személy elsődleges címében állítsa be a **Ország/régió** mezőt **CZE** (Cseh Köztársaság).
- Minden Cseh Köztársaságban található üzlet POS funkcióprofiljában állítsa be a **ISO kód** mezőt **CZ** (Cseh Köztársaság).

A következő beállításokat is meg kell adnia a Cseh Köztársaságban. Vegye figyelembe, hogy a telepítés befejezése után megfelelő terjesztési feladatokat kell futtatnia.

### <a name="set-up-vat-per-czech-republic-requirements"></a>Állítsa be az áfát a Cseh Köztársaság szerint


Létre kell hoznia áfakódokat, áfacsoportokat és cikkek forgalmiadó-csoportjait. Ezenkívül be kell állítania a forgalmi adóval kapcsolatos információkat a termékekhez és szolgáltatásokhoz. A forgalmiadó-szolgáltatások beállításával és használatával kapcsolatos további információkért lásd: [A forgalmi adó áttekintése](../../finance/general-ledger/indirect-taxes-overview.md).

### <a name="set-up-stores"></a>Üzletek létrehozása

A **Minden üzlet** oldalon, frissítse az üzlet adatait. Pontosabban állítsa be a következő paramétereket.

- Ban,-ben **Forgalmi adó csoport** mezőben adja meg az áfacsoportot, amelyet az alapértelmezett vevőnek történő értékesítéshez kell használni.
- Állítsa be a **Az árak tartalmazzák a forgalmi adót** opciót **Igen**.
- Állítsa be a **Név** mezőbe a cég nevét. Ez a változtatás segít garantálni, hogy a cégnév megjelenjen az értékesítési bizonylaton. Alternatív megoldásként hozzáadhatja a cég nevét az értékesítési bizonylat elrendezéséhez szabad formátumú szövegként.
- Állítsa be a **Adóazonosító szám (TIN)** mezőben a cégazonosító számra. Ez a változtatás segít garantálni, hogy a cégazonosító szám megjelenjen az értékesítési bizonylaton. Alternatív megoldásként hozzáadhatja a cégazonosító számot az értékesítési bizonylat elrendezéséhez szabad formátumú szövegként.

### <a name="set-up-functionality-profiles"></a>Funkcióprofilok beállítása

Állítsa be a POS funkcióprofilokat.

- A **Nyugta számozás** FastTab, állítsa be a nyugtaszámozást a rekordok létrehozásával vagy frissítésével **Eladás**, **rendelés**, és **Visszatérés** átvételi tranzakció típusok.

### <a name="set-up-registration-numbers"></a>Állítsa be a regisztrációs számokat

1. Menj **Szervezeti adminisztráció \> Globális címjegyzék \> Regisztrációs típusok \> Regisztrációs típusok**. Hozzon létre egy új regisztrációs típust. Adja meg a **Ország/régió** mezőt **CZE** (Cseh Köztársaság), és korlátozza a Szervezetre.
2. Menj **Szervezeti adminisztráció \> Globális címjegyzék \> Regisztrációs típusok \> Regisztrációs kategóriák**. Hozzon létre egy új regisztrációs kategóriát. Válassza ki a regisztráció típusát az előző lépésből, és állítsa be a **Regisztrációs kategória** nak nek **Üzlethelyiség azonosítója**.
3. Nyissa meg a következőt: **Szervezeti adminisztráció \> Szervezetek \> Üzemi egységek**. Minden Cseh Köztársaságban található üzlethez válassza ki az üzlethez kapcsolódó egységet. A **Cím** A FastTab bontsa ki a **Több lehetőség** legördülő listából, és válassza ki **Fejlett**. 
4. A megnyitotton **Címek kezelése** oldalon a következő beállítást kell megadnia.

    - A **Cím** FastTab állítsa be a **Ország/régió** mezőt **CZE**.
    - A **Regisztrációs azonosító** A FastTab új rekordot hoz létre. Válassza ki a korábban létrehozott regisztrációs típust, és állítsa be a regisztrációs számot.

### <a name="configure-custom-fields-so-that-they-can-be-used-in-receipt-formats-for-sales-receipts"></a>Állítsa be az egyéni mezőket úgy, hogy azokat az értékesítési bizonylatok nyugtaformátumaiban lehessen használni

Beállíthatja a POS nyugtaformátumokban használt nyelvi szöveget és egyéni mezőket. A nyugtabeállítást létrehozó felhasználó alapértelmezett cégének ugyanannak a jogi személynek kell lennie, mint ahol a nyelvi szövegbeállítás létrejött. Alternatív megoldásként ugyanazokat a nyelvű szövegeket kell létrehozni a felhasználó alapértelmezett vállalatában és annak az áruháznak a jogi személyében, amelyhez a beállítást létrehozták.

A **Nyelvi szöveg** oldalon adja hozzá a következő rekordokat a nyugtaelrendezések egyéni mezőinek címkéihez. Vegye figyelembe, hogy a **Nyelvazonosító**, **azonosító**, és **Szöveg** a táblázatban szereplő értékek csak példák. Módosíthatja őket, hogy megfeleljenek igényeinek. Azonban a **Szöveges azonosító** A használt értékeknek egyedinek kell lenniük, és egyenlőnek vagy nagyobbaknak kell lenniük a 900001 értékkel.

Adja hozzá a következő POS-címkéket a **pozíció** szakasza **Nyelvi szöveg** a táblázatból:

| Nyelvazonosító | Szövegazonosító | Szöveg                   |
|-------------|---------|------------------------|
| hu-US       | 900001  | ID provozovny/pokladny |
| hu-US       | 900002  | BKP                    |
| hu-US       | 900003  | PKP                    |
| hu-US       | 900004  | FIK                    |
| hu-US       | 900005  | Információ                   |
| hu-US       | 900006  | Sorszám        |

A **Egyéni mezők** oldalon adja hozzá a következő rekordokat a nyugtaelrendezések egyéni mezőihez. Vegye figyelembe, hogy **Felirat szövegének azonosítója** értékeknek meg kell felelniük a **Szöveges azonosító** oldalon megadott értékeket **Nyelvi szöveg** oldal:

| Név                 | Típus    | Képaláírás-szöveg azonosítója |
|----------------------|---------|-----------------|
| TLT                  | Fogadás | 900001          |
| SEC                  | Fogadás | 900002          |
| JEL                 | Fogadás | 900003          |
| FISKÁLIS               | Fogadás | 900004          |
| INFO                 | Fogadás | 900005          |
| FOLYAMATOS SZÁM     | Fogadás | 900006          |

> [!NOTE]
> Fontos, hogy helyes egyéni mezőneveket adjon meg, az előző táblázatban felsoroltak szerint. A helytelen egyéni mezőnév adatok hiányát okozza a nyugtákban.

### <a name="configure-receipt-formats"></a>Konfigurálja a nyugtaformátumokat

Minden szükséges nyugtaformátumnál módosítsa az értékét **Nyomtatási viselkedés** mezőt **Mindig nyomtasson**.

A Nyugtaformátum-tervezőben adja hozzá a következő egyéni mezőket a megfelelő nyugtarészekhez. Vegye figyelembe, hogy a mezőnevek megfelelnek az előző szakaszban megadott nyelvi szövegeknek.

- **Fejléc:** Adja hozzá a következő mezőket.

    - **Az üzlet neve** és **Adószám** : ezek a mezők a cégnév és az azonosító szám nyomtatására szolgál a nyugtákra. Alternatív megoldásként hozzáadhatja a cégnevet és az azonosító számot az elrendezéshez szabad formátumú szövegként.
    - **Az üzlet címe**, **·**, **24 óra**, **száma**, és **Regisztrációs szám**.
    - **Sorszám** : ez a mező azonosítja a készpénzes tranzakció számát az adónyilvántartási szolgáltatásban.

- **Sorok:** Adja hozzá a következő mezőket.

    - **Cikknév**
    - **Mennyiség**
    - **Teljes ár áfával**

- **Lábléc:** Adja hozzá a következő mezőket.

    - Fizetési mezők, így az egyes fizetési módokhoz tartozó fizetési összegek kinyomtatásra kerülnek. Például adja hozzá a **Pályázat neve** és **Pályázati összeg** mezőket az elrendezés egyik sorába.
    - **ID provozovny/pokladny** : ez a mező írja ki az üzlethelyiség és a pénztárgép azonosítóit.
    - **BKP** : ez a mező kiírja az adózó biztonsági kódját, amelyet az adónyilvántartási szolgáltatás rendelt.
    - **FIK** : ez a mező a tranzakció adózási azonosító kódját írja ki, amelyet sikeres online regisztráció esetén az adóhatóság webszolgáltatása ad hozzá.
    - **PKP** : ez a mező az adózó aláírási kódját írja ki, amelyet offline regisztráció esetén az adónyilvántartási szolgáltatás generál.
    - **Info** : ez a mező az adóregisztrációs szolgáltatásból származó további információkat nyomtatja ki.

A beérkezési formátumok működéséről a Beérkezési formátumok [beállítása és tervezése című témakörben talál](../receipt-templates-printing.md) további információt.

## <a name="set-up-fiscal-integration-for-the-czech-republic"></a>Fiskális integráció létrehozása a Cseh Köztársaság számára

A Cseh Köztársaság fiskális regisztrációs szolgáltatás integrációs mintája a [fiskális integrációs funkcionalitás](fiscal-integration-for-retail-channel.md) és a Retail SDK része. A minta a **Solutions\\ adattár srcFiscalIntegration\\Efr**[Dynamics 365 Commerce mappájában](https://github.com/microsoft/Dynamics365Commerce.Solutions/) található (például [a kiadási/9.33-as](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/Efr) minta). A minta [egy pénzügyi bizonylatszolgáltatóból áll](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services), amely a Commerce futtatókörnyezet (CRT) kiterjesztése, és egy fiskális összekötőből, amely a Commerce Hardware Station kiterjesztése. A Kiskereskedelmi SDK használatáról a Retail SDK architektúrája [és](../dev-itpro/retail-sdk/retail-sdk-overview.md) build-folyamat beállítása a független csomagolású SDK-hoz [című témakörben talál](../dev-itpro/build-pipeline.md) további információt.

> [!WARNING]
> Az új független csomagolási és kiterjesztési [modell](../dev-itpro/build-pipeline.md) korlátai miatt jelenleg nem használható ehhez a költségvetési integrációs mintához. A Retail SDK előző verzióját egy fejlesztői virtuális gépen (VM) kell használnia az Microsoft Dynamics Életciklus-szolgáltatásokban (LCS). További információkért lásd [Beépítési irányelvek a Cseh Köztársaság költségvetési integrációs mintájához (örökölt)](emea-cze-fi-sample-sdk.md).
>
> A költségvetési integrációs minták új független csomagolási és kiterjesztési modelljének támogatását tervezik a későbbi verziókhoz.

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
    1. Töltse le az adódokumentum-szolgáltató konfigurációs fájlját a következő címről: **Konfigurációk \> Dokumentumszolgáltatók \> DocumentProviderFiscalEFRSampleCzech.xml** (például, [a kiadáshoz tartozó fájl/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/blob/release/9.33/src/FiscalIntegration/Efr/Configurations/DocumentProviders/DocumentProviderFiscalEFRSampleCzech.xml)).
    1. Töltse le a pénzügyi összekötő konfigurációs fájlját a **Configurations \> Connectors \> ConnectorEFRSample.xml** (például [a kiadáshoz szükséges fájl/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/blob/release/9.33/src/FiscalIntegration/Efr/Configurations/Connectors/ConnectorEFRSample.xml)).

    > [!WARNING]
    > Az új független csomagolási és kiterjesztési [modell](../dev-itpro/build-pipeline.md) korlátai miatt jelenleg nem használható ehhez a költségvetési integrációs mintához. A Retail SDK előző verzióját kell használnia egy fejlesztői virtuális gépen az LCS-ben. A pénzügyi integrációs minta konfigurációs fájljai a Retail SDK következő mappáiban találhatók egy fejlesztői virtuális gépen az LCS-ben:
    >
    > - **Fiskális dokumentum-szolgáltató konfigurációs fájlja:** RetailSdk\\ SampleExtensions\\ CommerceRuntime\\ Extensions.DocumentProvider.EFRSample\\ Konfiguráció\\ DocumentProviderFiscalEFRSampleCzech.xml
    > - **Fiskális csatlakozási konfigurációs fájl:** RetailSdk\\ SampleExtensions\\ HardwareStation\\ Kiterjesztés.EFRSminta\\ Konfiguráció\\ CsatlakozóEFRSample.xml
    > 
    > A költségvetési integrációs minták új független csomagolási és kiterjesztési modelljének támogatását tervezik a későbbi verziókhoz.

1. Lépjen a **Retail és Commerce \> Központ beállítása \> Paraméterek \> Commerce megosztott paraméterek** menüpontra. Az Általános **lapon állítsa a** Költségvetési integráció **engedélyezése beállítást Igen értékre** **.**
1. Menj **Kiskereskedelem és kereskedelem \> Csatorna beállítása \> Fiskális integráció \> Fiskális dokumentumszolgáltatók**, és töltse be a korábban letöltött adódokumentum-szolgáltató konfigurációs fájlját.
1. Lépjen a **Kiskereskedelmi és kereskedelmi \> csatorna beállítására \> Pénzügyi integráció \> Pénzügyi összekötők, és töltse be a korábban letöltött pénzügyi összekötő konfigurációs** fájlt.
1. Lépjen a **Kiskereskedelmi és kereskedelmi \> csatorna beállítására \> Pénzügyi integrációs \> összekötő funkcionális profiljai**. Hozzon létre egy új csatlakozó funkcionális profilt. Válassza ki a dokumentumszolgáltatót és a korábban betöltött csatlakozót. Szükség szerint frissítse az [adatleképezési beállításokat](#default-data-mapping).
1. Lépjen a **Kiskereskedelmi és kereskedelmi \> csatorna beállítására \> Pénzügyi integráció \> Összekötő technikai profiljai**. Hozzon létre egy új összekötő műszaki profilját, és válassza ki a korábban betöltött pénzügyi összekötőt. Szükség szerint frissítse az [összekötő beállításait](#fiscal-connector-settings).
1. Lépjen a **Kiskereskedelem és kereskedelem \> csatorna beállítására \> Pénzügyi integráció \> Pénzügyi összekötő csoportok**. Hozzon létre egy új pénzügyi összekötő-csoportot a korábban létrehozott összekötő funkcionális profilhoz.
1. Lépjen a **Kiskereskedelmi és kereskedelmi \> csatorna beállítására \> Pénzügyi integráció \> Pénzügyi regisztrációs folyamatok**. Hozzon létre egy új adóregisztrációs folyamatot és egy fiskális regisztrációs folyamat lépést, és válassza ki a korábban létrehozott adóösszekötő csoportot.
1. Ugorjon a következő elemre: **Retail és Commerce \>  Csatorna beállítása \> Pénztárbeállítás \>  Pénztárprofilok \> Funkcióprofilok**. Válasszon ki egy olyan funkcióprofilt, amely ahhoz az üzlethez kapcsolódik, ahol a regisztrációs folyamatot aktiválni kell. **A Pénzügyi regisztrációs folyamat** gyorslapon válassza ki a korábban létrehozott pénzügyi regisztrációs folyamatot.
1. Lépjen a **Kiskereskedelem és kereskedelem \> Csatorna beállítás \> POS beállítás \> POS profilok \> Hardverprofilok** pontra. Válasszon ki egy hardverprofilt, amely ahhoz a hardverállomáshoz kapcsolódik, amelyhez a pénzügyi nyomtató csatlakozik. **A Pénzügyi perifériák** gyorslapon válassza ki a korábban létrehozott összekötő műszaki profilját.
1. Nyissa meg a terjesztési ütemezést (**Kiskereskedelmi és \> kereskedelmi kiskereskedelem és kereskedelem IT-terjesztési \> ütemezése**), és válassza az 1070-es és **1090-es** **feladatokat** az adatok csatornaadatbázisba történő átviteléhez.

#### <a name="default-data-mapping"></a>Alapértelmezett adatleképezés

A költségvetési integrációs minta részeként megadott pénzügyi bizonylatszolgáltató konfigurációja a következő alapértelmezett adatleképezést tartalmazza:

- **Hozzáadottérték-adó (ÁFA) díjak leképezése** – Az áfakódokhoz beállított adószázalékértékek leképezése a **TaxG** (adócsoport) attribútum értékeihez a adószolgáltatásnak küldött kérelmekben. Íme az alapértelmezett leképezés:

    ```
    A: 21.00; B: 15.00; C: 10.00; Z: 0.00
    ```

    Az egyes párok első összetevője egy áfaadó-csoportot képvisel, amelyet az EFR adóregisztrációs szolgáltatás támogat. A második összetevő a megfelelő héakulcsot képviseli. Az EFR által a Cseh Köztársaságban támogatott áfa-adócsoportokkal kapcsolatos további információkért lásd a [EFR hivatkozás](https://public.efsta.net/efr/).

- **Alapértelmezett áfacsoport-leképezés** – Minden olyan áfaösszeg, amely nem rendelhető hozzá valamelyik előre meghatározott áfacsoporthoz, az alapértelmezett (alap) áfacsoporthoz lesz rendelve. Íme az alapértelmezett leképezés:

    ```
    A
    ```

- **Betéti ÁFA csoport leképezés** – A vevői betét összegei és a vevői rendelési betét összegei a betéti ÁFA csoporthoz tartoznak. Íme az alapértelmezett leképezés:

    ```
    Z
    ```

#### <a name="fiscal-connector-settings"></a>Pénzügyi összekötő beállításai

A költségvetési integrációs minta részeként megadott pénzügyi összekötő konfiguráció a következő beállításokat tartalmazza:

- **Végpont címe** – A pénzügyi regisztrációs szolgáltatás URL-címe.
- **Időtúllépés** – Az az idő, ezredmásodpercben, ameddig a fiskális összekötő vár a fiskális regisztrációs szolgáltatás válaszára.

### <a name="configure-channel-components"></a>Csatornaösszetevők konfigurálása

> [!WARNING]
> Az új független csomagolási és kiterjesztési [modell](../dev-itpro/build-pipeline.md) korlátai miatt jelenleg nem használható ehhez a költségvetési integrációs mintához. A Retail SDK előző verzióját kell használnia egy fejlesztői virtuális gépen az LCS-ben. További információkért lásd [Beépítési irányelvek a Cseh Köztársaság költségvetési integrációs mintájához (örökölt)](emea-cze-fi-sample-sdk.md).
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
    1. Indítsa el a bővítménytelepítőt a parancssorból:

        ```Console
        HardwareStation.EFR.Installer.exe install --verbosity 0
        ```

#### <a name="production-environment"></a>Működési környezet

Kövesse a lépéseket [Állítson be egy összeállítási folyamatot a fiskális integrációs mintához](fiscal-integration-sample-build-pipeline.md) a Cloud Scale Unit és az önkiszolgáló telepíthető csomagok létrehozása és kiadása a költségvetési integrációs mintához. A **EFR build-pipeline.yml** sablon YAML fájl megtalálható a **Csővezeték\\ YAML_Files** mappa a [Dynamics 365 Commerce Megoldások](https://github.com/microsoft/Dynamics365Commerce.Solutions) adattár.

## <a name="design-of-extensions"></a>Bővítések tervezése

A Cseh Köztársaság fiskális regisztrációs szolgáltatás integrációs mintája a [fiskális integrációs funkcionalitás](fiscal-integration-for-retail-channel.md) és a Retail SDK része. A minta a **Solutions\\ adattár srcFiscalIntegration\\Efr**[Dynamics 365 Commerce mappájában](https://github.com/microsoft/Dynamics365Commerce.Solutions/) található (például [a kiadási/9.33-as](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/Efr) minta). A minta [áll](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services) egy fiskális dokumentumszolgáltató, amely a kiterjesztése CRT és egy fiskális csatlakozó, amely a Commerce Hardware Station kiterjesztése. A Kiskereskedelmi SDK használatáról a Retail SDK architektúrája [és](../dev-itpro/retail-sdk/retail-sdk-overview.md) build-folyamat beállítása a független csomagolású SDK-hoz [című témakörben talál](../dev-itpro/build-pipeline.md) további információt.

> [!WARNING]
> Az új független csomagolási és kiterjesztési [modell](../dev-itpro/build-pipeline.md) korlátai miatt jelenleg nem használható ehhez a költségvetési integrációs mintához. A Retail SDK előző verzióját kell használnia egy fejlesztői virtuális gépen az LCS-ben. További információkért lásd [Beépítési irányelvek a Cseh Köztársaság költségvetési integrációs mintájához (örökölt)](emea-cze-fi-sample-sdk.md). A költségvetési integrációs minták új független csomagolási és kiterjesztési modelljének támogatását tervezik a későbbi verziókhoz.

### <a name="commerce-runtime-extension-design"></a>Kereskedelmi futásidejű bővítmény tervezése

Az adódokumentum-szolgáltató bővítmény célja szolgáltatás-specifikus dokumentumok előállítása és válaszok kezelése az adónyilvántartási szolgáltatástól.

#### <a name="request-handler"></a>Kérelemkezelő

Egyetlen van **DocumentProviderEFRFiscalCZE** dokumentumszolgáltató kéréskezelője, amely az adónyilvántartási szolgáltatás adódokumentumainak előállítására szolgál.

Ezt a kezelőt a **INamedRequestHandler** felület. A **HandlerName** metódus felelős a kezelő nevének visszaadásáért. A kezelő nevének meg kell egyeznie a Kereskedelmi központban megadott összekötő dokumentumszolgáltató nevével.

Az összekötő a következő kéréseket támogatja.

- **GetFiscalDocumentDocumentProviderRequest** – Ez a kérés információt tartalmaz arról, hogy milyen dokumentumot kell létrehozni. Egy szolgáltatásspecifikus dokumentumot ad vissza, amelyet regisztrálni kell a pénzügyi regisztrációs szolgáltatásban.
- **GetSupportedRegistrableEventsDocumentProviderRequest** – Ez a kérés visszaadja az előfizetendő események listáját. Jelenleg a következő rendezvények támogatottak: értékesítés, ügyfélszámla befizetés és ügyfélrendelési betét.
- **GetFiscalRegisterResponseToSaveDocumentProviderRequest** – Ez a kérelem a pénzügyi regisztrációs szolgáltatás válaszát adja vissza. Ez a válasz szerializálva karakterláncot képez, hogy készen álljon a mentésre.

#### <a name="configuration"></a>Konfiguráció

Az adódokumentum-szolgáltató konfigurációs fájlja a címen található **src\\ Fiskális integráció\\ Efr\\ Konfigurációk\\ Dokumentumszolgáltatók\\ DocumentProviderFiscalEFRSampleCzech.xml** ban,-ben [Dynamics 365 Commerce Megoldások](https://github.com/microsoft/Dynamics365Commerce.Solutions/) adattár. A fájl célja, hogy lehetővé tegye a költségvetési dokumentumszolgáltató beállításainak konfigurálását a Commerce központjából. A fájlformátum igazodik a pénzügyi integráció konfigurációjának követelményeihez.

### <a name="hardware-station-extension-design"></a>Hardverállomás-bővítés kialakítása

A költségvetési összekötő bővítmény célja a pénzügyi regisztrációs szolgáltatással való kommunikáció. A hardverállomás-bővítmény a HTTP protokollt használja az olyan dokumentumok benyújtására, amelyek a CRT kiterjesztést generál az adóregisztrációs szolgáltatáshoz. Kezeli továbbá a pénzügyi regisztrációs szolgáltatástól kapott válaszokat.

#### <a name="request-handler"></a>Kérelemkezelő

Az **EFRHandler** kérelemkezelője a belépési pont a pénzügyi regisztrációs szolgáltatáshoz benyújtott kérelmek kezeléséhez.

A kezelő az **INamedRequestHandler felületről öröklődik**. A **HandlerName** metódus felelős a kezelő nevének visszaadásáért. A kezelő nevének meg kell egyeznie a Kereskedelmi központban megadott pénzügyi összekötő nevével.

Az összekötő a következő kéréseket támogatja.

- **SubmitDocumentFiscalDeviceRequest** – Ez a kérelem dokumentumokat küld a pénzügyi regisztrációs szolgálatnak, és visszaküldi a választ.
- **IsReadyFiscalDeviceRequest** – Ez a kérés a pénzügyi regisztrációs szolgáltatás állapotfelmérésére szolgál.
- **InitializeFiscalDeviceRequest** – Ez a kérés a pénzügyi regisztrációs szolgáltatás inicializálására szolgál.

#### <a name="configuration"></a>Konfiguráció

A fiskális csatlakozó konfigurációs fájlja a következő címen található: **src\\ Fiskális integráció\\ Efr\\ Konfigurációk\\ Csatlakozók\\ CsatlakozóEFRSample.xml** ban,-ben [Dynamics 365 Commerce Megoldások](https://github.com/microsoft/Dynamics365Commerce.Solutions/) adattár. A fájl célja, hogy lehetővé tegye a pénzügyi összekötő beállításainak konfigurálását a Commerce központjából. A fájlformátum igazodik a pénzügyi integráció konfigurációjának követelményeihez.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
