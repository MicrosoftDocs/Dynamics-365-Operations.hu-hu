---
title: Adóügyi regisztrációs szolgáltatás integrációját bemutató minta Németországra vonatkozóan
description: Ez a témakör áttekintést nyújt a németországi fiskális integrációs mintáról Microsoft Dynamics 365 Commerce.
author: EvgenyPopovMBS
ms.date: 12/20/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2020-5-29
ms.openlocfilehash: 128c94407a283bf45e5626de060cee82430f087b
ms.sourcegitcommit: 5cefe7d2a71c6f220190afc3293e33e2b9119685
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/01/2022
ms.locfileid: "8076862"
---
# <a name="fiscal-registration-service-integration-sample-for-germany"></a>Adóügyi regisztrációs szolgáltatás integrációját bemutató minta Németországra vonatkozóan

[!include[banner](../includes/banner.md)]

Ez a témakör áttekintést nyújt a németországi fiskális integrációs mintáról Microsoft Dynamics 365 Commerce.

A németországi pénztárgépekre vonatkozó helyi adókövetelmények teljesítése érdekében a Microsoft Dynamics 365 Commerce A németországi funkcionalitás magában foglalja az értékesítési pont (POS) mintaintegrációját egy külső adóregisztrációs szolgáltatással. A minta kiterjeszti a [fiskális integrációs funkcionalitás](fiscal-integration-for-retail-channel.md). Azon alapul [EFR (elektronikus adónyilvántartás)](https://www.efsta.eu/de/fiskalloesungen/deutschland) megoldástól [EFSTA](https://www.efsta.eu/de/) és lehetővé teszi a kommunikációt az EFR szolgáltatással a HTTPS protokollon keresztül. Az EFR szolgáltatásnak vagy a Retail Hardware állomáson vagy egy külön számítógépen kell lennie, amelyhez a hardver állomásról lehet csatlakozni. A minta forráskód formájában áll rendelkezésre, és a kiskereskedelmi szoftverfejlesztő készlet (SDK) része.

A Microsoft nem ad ki semmilyen hardvert, szoftvert vagy dokumentációt az EFSTA-tól. Az EFR megoldás beszerzésével és üzemeltetésével kapcsolatos információkért forduljon a következőhöz: [EFSTA](https://www.efsta.eu/de/kontakt/kontakt).

## <a name="scenarios"></a>Forgatókönyvek

A következő forgatókönyveket fedi le a németországi adóregisztrációs szolgáltatás integrációs mintája.

### <a name="sales-operations"></a>Értékesítési műveletek

- **A készpénzes eladások és visszaküldések nyilvántartása az adónyilvántartási szolgáltatásban:**

    Az értékesítési műveletek regisztrációja a következő lépéseket tartalmazza:

    1. A tranzakció kezdetének regisztrációja

        Az EFR szolgáltatáshoz kapcsolódó technikai biztonsági elemben (TSE) minden tranzakció kezdete rögzítésre kerül. A regisztráció eredményeként a TSE tranzakcióazonosítót (TID) rendel hozzá.

    2. A tranzakció végének regisztrációja

        Amikor a POS-ban megkötött egy tranzakciót, az ugyanazzal a TID-vel kerül regisztrálásra, amelyet a tranzakció kezdetének regisztrálásakor hozzárendeltek. Ekkor a részletes tranzakciós adatok elküldésre kerülnek az adónyilvántartási szolgálatnak. Ezek az adatok az értékesítési vonalra vonatkozó információkat, valamint a kedvezményekkel, kifizetésekkel és adókkal kapcsolatos információkat tartalmaznak.

    3. Válasz rögzítése az adóregisztrációs szolgáltatástól

        A biztonsági adatok a TSE-től a válasz részeként érkeznek, és a tranzakcióban a csatornaadatbázisban kerülnek mentésre. A biztonsági adatok a következő információkat tartalmazzák:

        - TID
        - A tranzakció kezdetének dátuma és időpontja
        - A tranzakció befejezésének dátuma és időpontja
        - Aláírásszámláló
        - Ellenőrizze az értéket
        - A TSE sorozatszáma

- **Vevői megrendelések regisztrációja az adónyilvántartási szolgáltatásban:** A regisztrációs folyamat megegyezik a készpénzes értékesítés és visszaküldés folyamatával.
- **Ajándékkártyákkal és betétekkel járó műveletek regisztrációja:** A regisztrációs folyamat megegyezik a készpénzes értékesítés és visszaküldés folyamatával.

#### <a name="notifying-users-about-fiscal-registration-failures"></a>A felhasználók értesítése a fiskális regisztrációs hibákról

Az adóregisztrációs szolgáltatás kétféleképpen értesítheti a felhasználókat az adóregisztráció során fellépő hibákról:

- Nyomtasson ki további információkat a válaszból a **Információs üzenet** mező a nyugtákon.
- Az adószolgáltatás értesítéseinek megjelenítése felhasználói üzenetként a POS-ban.

    > [!NOTE]
    > Ez az értesítési mechanizmus megköveteli, hogy a **Adóügyi regisztrációs értesítések megjelenítése** paraméter a **Csatlakozók műszaki profiljai** oldal legyen bekapcsolva.

#### <a name="printing-receipts"></a>Bizonylatok nyomtatása

A nyugta nyomtatása Németországban kötelező. Minden nyugtának tartalmaznia kell legalább a következő információkat:

- A cég neve és címe
- Információk az árukról, beleértve az árakat és mennyiségeket
- Információk a beérkezett kifizetésekről
- Információk az adókról, beleértve az adókulcsonkénti teljes összeget
- Biztonsági adatok:

    - TID
    - A tranzakció kezdetének dátuma és időpontja
    - A tranzakció befejezésének dátuma és időpontja
    - Aláírásszámláló
    - Ellenőrizze az értéket
    - A TSE sorozatszáma

- Tájékoztató üzenet

> [!NOTE]
> A nyugtákra QR-kód is nyomtatható. Bár a QR-kód nem kötelező, erősen ajánlott. További információért arról, hogyan kaphat QR-kódot az adóregisztrációs szolgáltatás válaszának részeként, tekintse meg az "EFR Guide"\[ DE\] "-on közzétett dokumentum [EFSTA dokumentáció](https://public.efsta.net/efr/) weboldal.
>
> A **Információs üzenet** A nyugták mezőjében az adónyilvántartási szolgáltatás értesítése látható. Például, ha egy aláírási eszköz elromlik, speciális szöveg nyomtatható a nyugtára.

#### <a name="voided-suspended-and-recalled-transactions"></a>Érvénytelen, felfüggesztett és visszahívott tranzakciók

- Az érvénytelenített tranzakciót az adóügyi nyilvántartási szolgáltatásban a tranzakció megszüntetésére irányuló kérelemként regisztrálják.
- A felfüggesztett tranzakció a tranzakció megszüntetésére irányuló kérelemként kerül bejegyzésre az adóregisztrációs szolgáltatásban.
- A felfüggesztett tranzakció visszahívása új tranzakció kezdeteként kerül rögzítésre az adóregisztrációs szolgáltatásban.

### <a name="non-sales-transactions-and-shift-closing"></a>Nem értékesítési tranzakciók és műszakzárás

Az alábbi, nem értékesítési tranzakciókat nem fiskális műveletként regisztrálja az adóregisztrációs szolgáltatás a **NFS** címke:

- Nyitó összeg elszámolása
- Váltópénzbetét
- Fizetőeszköz kivétele
- Széfes befizetés
- Banki befizetés
- Bevételi számlák
- Kiadási számlák

A **Műszak bezárása** művelet nem fiskális műveletként is regisztrálásra kerül az adónyilvántartási szolgáltatásban a segítségével **NFS** címke.

### <a name="data-export-and-audit"></a>Adatexport és audit

Minden tranzakciót alá kell írnia egy TSE-nek annak érdekében, hogy biztosítsák azok integritását, hitelességét és teljességét, és megakadályozzák a rögzített adatok manipulálását.

> [!WARNING]
> Csak tanúsított TSE használható. Az EFR-megoldás által támogatott TSE-típusokkal és -modellekkel kapcsolatos információkért tekintse meg az „EFR Guide\[ DE\] "-on közzétett dokumentum [EFSTA dokumentáció](https://public.efsta.net/efr/) weboldal. A TSE kiválasztásával és beszerzésével kapcsolatos információkért forduljon a következőhöz: [EFSTA](https://www.efsta.eu/at/kontakt).

A németországi szabályozás megköveteli a DSFinV-K export támogatását. A DSFinV-K export az EFR megoldásban aktiválható. A DSFinV-K exporttal kapcsolatos további információkért lásd az „EFR Guide\[ DE\] "-n közzétett dokumentum [EFSTA dokumentáció](https://public.efsta.net/efr/) weboldal.

### <a name="limitations-of-the-sample"></a>A minta korlátai

Az adóregisztrációs szolgáltatás csak azokat a forgatókönyveket támogatja, amelyeknél az árak tartalmazzák a forgalmi adót. Ezért a **Az árak tartalmazzák a forgalmi adót** opcióra kell állítani **Igen** üzleteknek és vásárlóknak egyaránt.

A fiskális szolgáltatás nem támogatja azokat a helyzeteket, amikor egynél több áfakódot alkalmaznak ugyanahhoz a tranzakciós sorhoz.

A fiskális integrációs keretrendszer nem támogatja az értékesítési árajánlatokat. Ezért ezek a műveletek nincsenek regisztrálva az adószolgáltatásban.

## <a name="set-up-commerce-for-germany"></a>Állítsa be a Commerce szolgáltatást Németország számára

Ez a rész azokat a Kereskedelmi beállításokat írja le, amelyek kifejezetten Németországra vonatkoznak, és Németország számára ajánlottak. További beállítási információkért lásd: [Kereskedelmi főoldal](../index.md).

A Németországra jellemző funkciók használatához meg kell adnia a következő beállításokat.

- A jogi személy elsődleges címében állítsa be a **Ország/régió** mezőt **DEU** (Németország).
- Minden Németországban található üzlet POS funkcióprofiljában állítsa be a **ISO kód** mezőt **DE** (Németország).

A következő beállításokat is meg kell adnia Németországban. A telepítés befejezése után feltétlenül futtassa a megfelelő terjesztési feladatokat.

### <a name="set-up-vat-per-german-requirements"></a>Állítsa be az áfát a német követelményeknek megfelelően

Létre kell hoznia áfakódokat, áfacsoportokat és cikkek forgalmiadó-csoportjait. Ezenkívül be kell állítania a forgalmi adóval kapcsolatos információkat a termékekhez és szolgáltatásokhoz. A forgalmiadó-szolgáltatások beállításával és használatával kapcsolatos további információkért lásd: [A forgalmi adó áttekintése](../../finance/general-ledger/indirect-taxes-overview.md).

Az értékesítési bizonylatokon kinyomtathatja a forgalmi adó kódjának rövidített kódját (például "A" vagy "B"). A funkció elérhetővé tételéhez állítsa be a **Kód a nyomtatáshoz** mező a **A forgalmi adó kódjai** oldalon.

### <a name="set-up-stores"></a>Üzletek létrehozása

A **Minden üzlet** oldalon, frissítse az üzlet adatait. Pontosabban állítsa be a következő paramétereket:

- Ban,-ben **Forgalmi adó csoport** mezőben adja meg az áfacsoportot, amelyet az alapértelmezett vevőnek történő értékesítéshez kell használni.
- Állítsa be a **Az árak tartalmazzák a forgalmi adót** opciót **Igen**.
- Állítsa be a **Név** mezőbe a cég nevét. Ez a változtatás segít abban, hogy a cég neve megjelenjen az értékesítési bizonylaton. Alternatív megoldásként hozzáadhatja a cég nevét az értékesítési bizonylat elrendezéséhez szabad formátumú szövegként.
- Állítsa be a **Adóazonosító szám (TIN)** mezőben a cégazonosító számra. Ez a változtatás segít abban, hogy a cégazonosító szám megjelenjen az értékesítési bizonylaton. Alternatív megoldásként hozzáadhatja a cégazonosító számot az értékesítési bizonylat elrendezéséhez szabad formátumú szövegként.

### <a name="set-up-functionality-profiles"></a>Funkcióprofilok beállítása

Állítsa be a POS funkcióprofilokat. A **Nyugta számozás** FastTab, állítsa be a nyugtaszámozást a rekordok létrehozásával vagy frissítésével **Eladás**, **rendelés**, és **Visszatérés** átvételi tranzakció típusok.

### <a name="configure-custom-fields-so-that-they-can-be-used-in-receipt-formats-for-sales-receipts"></a>Állítsa be az egyéni mezőket úgy, hogy azokat az értékesítési bizonylatok nyugtaformátumaiban lehessen használni

Beállíthatja a POS nyugtaformátumokban használt nyelvi szöveget és egyéni mezőket. A nyugtabeállítást létrehozó felhasználó alapértelmezett cégének ugyanannak a jogi személynek kell lennie, mint ahol a nyelvi szövegbeállítás létrejött. Alternatív megoldásként ugyanazokat a nyelvű szövegeket kell létrehozni a felhasználó alapértelmezett vállalatában és annak az áruháznak a jogi személyében, amelyhez a beállítást létrehozták.

A **Nyelvi szöveg** oldalon adja hozzá a következő rekordokat a nyugtaelrendezések egyéni mezőinek címkéihez. Vegye figyelembe, hogy a **Nyelvazonosító**, **azonosító**, és **Szöveg** a táblázatban szereplő értékek csak példák. Módosíthatja őket, hogy megfeleljenek az Ön igényeinek. Azonban a **Szöveges azonosító** A használt értékeknek egyedinek kell lenniük, és egyenlőnek vagy nagyobbaknak kell lenniük a 900001 értékkel.

Adja hozzá a következő POS-címkéket a **pozíció** szakasza a **Nyelvi szöveg** oldalon.

| Nyelvazonosító | Szövegazonosító | Szöveg                                  |
|-------------|---------|---------------------------------------|
| hu-US       | 900001  | QR-kód                               |
| hu-US       | 900002  | Tranzakció azonosítója                        |
| hu-US       | 900003  | Adó kiskereskedelmi nyomtatási kód                 |
| hu-US       | 900004  | Adóösszeg (értékesítés)                    |
| hu-US       | 900005  | Adóalap (értékesítés)                     |
| hu-US       | 900006  | Tranzakció kezdő dátuma és időpontja           |
| hu-US       | 900007  | Tranzakció záró dátuma és időpontja             |
| hu-US       | 900008  | A biztonsági elem sorozatszáma |
| hu-US       | 900009  | Aláírásszámláló                     |
| hu-US       | 900010  | Ellenőrizze az értéket                           |
| hu-US       | 900011  | Információs üzenet                          |

A **Egyéni mezők** oldalon adja hozzá a következő rekordokat a nyugtaelrendezések egyéni mezőihez. Vegye figyelembe, hogy a **Felirat szövegének azonosítója** értékeknek meg kell felelniük a **Szöveges azonosító** oldalon megadott értékeket **Nyelvi szöveg** oldalon.

| Név                            | Típus    | Képaláírás-szöveg azonosítója |
|---------------------------------|---------|-----------------|
| QR-KÓD\_ DE                      | Fogadás | 900001          |
| TRANZAKCIÓ AZONOSÍTÓJA\_ DE               | Fogadás | 900002          |
| KERESKEDELMI NYOMTATÁSI KÓD\_ DE             | Fogadás | 900003          |
| ELADÁSI ÖSSZEG\_ DE              | Fogadás | 900004          |
| ÉRTÉKESÍTÉSI ALAP\_ DE               | Fogadás | 900005          |
| TRANSACTIONSTARTDATETIME\_ DE    | Fogadás | 900006          |
| TRANSACTIONENDDATETIME\_ DE      | Fogadás | 900007          |
| BIZTONSÁGI ELEMEK SORSZÁM\_ DE | Fogadás | 900008          |
| SIGNCOUNTER\_ DE                 | Fogadás | 900009          |
| JEL\_ DE                        | Fogadás | 900010          |
| TÁJÉKOZTATÁS\_ DE                 | Fogadás | 900011          |

> [!NOTE]
> Fontos, hogy helyes egyéni mezőneveket adjon meg, az előző táblázatban felsoroltak szerint. A helytelen egyéni mezőnév adatok hiányát okozza a nyugtákban.

### <a name="configure-receipt-formats"></a>Konfigurálja a nyugtaformátumokat

Minden szükséges nyugtaformátumnál módosítsa az értékét **Nyomtatási viselkedés** mezőt **Mindig nyomtasson**.

A Nyugtaformátum-tervezőben adja hozzá a következő egyéni mezőket a megfelelő nyugtarészekhez. Vegye figyelembe, hogy a mezőnevek megfelelnek az előző szakaszban megadott nyelvi szövegeknek.

- **Fejléc:** Adja hozzá a következő mezőket:

    - **Az üzlet neve** és **Adószám** mezők, amelyek a cégnév és az azonosító szám kinyomtatására szolgálnak a bizonylatokra. Alternatív megoldásként hozzáadhatja a cégnevet és az azonosító számot az elrendezéshez szabad formátumú szövegként.
    - **Az üzlet címe**, **·**, **24 óra**, **száma**, és **Regisztrációs szám** mezőket.

- **Sorok:** Adja hozzá a következő mezőket:

    - **Termék név** terület
    - **Menny** terület
    - **Teljes ár áfával** terület
    - **Adó kiskereskedelmi nyomtatási kód** mező, amely a cikkre vonatkozó általános forgalmi adó kódjának megfelelő rövidített kód kinyomtatására szolgál

- **Lábléc:** Adja hozzá a következő mezőket:

    - Fizetési mezők, így az egyes fizetési módokhoz tartozó fizetési összegek kinyomtatásra kerülnek. Például adja hozzá a **Pályázat neve** és **Pályázati összeg** mezőket az elrendezés egyik sorába.
    - Mezők a **Az adó lebontása** mezőcsoport. Ebben a mezőcsoportban minden mezőt egy külön sorba kell nyomtatni.

        - **Adóazonosító** mező, amely egy szabványos mező, amely lehetővé teszi a forgalmi adó összesítésének nyomtatását az egyes áfakódokhoz. A mezőt egy új sorhoz kell hozzáadni.
        - **Adószázalék** mező, amely egy szabványos mező, amely a forgalmiadó-kód tényleges adókulcsának kinyomtatására szolgál.
        - **Adóalap (értékesítés)** mező, amely a nyugta teljes készpénzes eladási összegének kinyomtatására szolgál az áfa kódhoz. Az előleg és az ajándékkártya műveletek nem tartoznak ide.
        - **Adóösszeg (értékesítés)** mező, amely a forgalmi adó kódhoz tartozó készpénzes értékesítés nyugta adóösszegének kinyomtatására szolgál.
        - **Adó kiskereskedelmi nyomtatási kód** mező, amely a forgalmi adó kódjának megfelelő rövidített kód kinyomtatására szolgál.

    - Az adóregisztrációs szolgáltatás által visszaküldött, biztonságos tranzakciós adatokat tartalmazó mezők:

        - **Tranzakció azonosítója** mező, amely azonosítja a készpénzes tranzakció számát az adónyilvántartási szolgáltatásban
        - **Tranzakció kezdő dátumának időpontja** terület
        - **A tranzakció befejezési dátuma** terület
        - **A biztonsági elem sorozatszáma** terület
        - **Aláírásszámláló** terület
        - **Ellenőrizze az értéket** terület
        - **QR-kód** mező, amely a regisztrált készpénzes tranzakció hivatkozásának kinyomtatására szolgál QR kód formájában

        > [!NOTE]
        > A **QR-kód** értéke a pénzügyi nyilvántartás válaszából származik. Az EFR csak akkor ad vissza QR-kódot a válaszában, ha az EFR konfiguráció Attribútumok **mezőjének értékét** az EFSTA dokumentáció ismerteti. Az EFR konfiguráció Attribútumok mezőjében a **QR-kódformátumot BMP-re** kell állítani **.**

    - **Információs üzenet** mezőben, hogy az adóregisztrációs szolgáltatás értesítő üzenetei megjelenjenek a nyugtákon. Például, ha egy aláírási eszköz elromlik, speciális szöveg nyomtatható a nyugtára.

A beérkezési formátumok működéséről a Beérkezési formátumok [beállítása és tervezése című témakörben talál](../receipt-templates-printing.md) további információt.

## <a name="set-up-fiscal-integration-for-germany"></a>Fiskális integráció létrehozása Németország számára

A németországi adóbejegyzési szolgáltatás integrációs mintája a [fiskális integrációs funkcionalitás](fiscal-integration-for-retail-channel.md) és a Retail SDK része. A minta a **Solutions\\ adattár srcFiscalIntegration\\Efr**[Dynamics 365 Commerce mappájában](https://github.com/microsoft/Dynamics365Commerce.Solutions/) található (például [a kiadási/9.33-as](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/Efr) minta). A minta [egy pénzügyi bizonylatszolgáltatóból áll](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services), amely a Commerce futtatókörnyezet (CRT) kiterjesztése, és egy fiskális összekötőből, amely a Commerce Hardware Station kiterjesztése. A Kiskereskedelmi SDK használatáról a Retail SDK architektúrája [és](../dev-itpro/retail-sdk/retail-sdk-overview.md) build-folyamat beállítása a független csomagolású SDK-hoz [című témakörben talál](../dev-itpro/build-pipeline.md) további információt.

> [!WARNING]
> Az új független csomagolási és kiterjesztési [modell](../dev-itpro/build-pipeline.md) korlátai miatt jelenleg nem használható ehhez a költségvetési integrációs mintához. A Retail SDK előző verzióját egy fejlesztői virtuális gépen (VM) kell használnia az Microsoft Dynamics Életciklus-szolgáltatásokban (LCS). További információkért lásd [Bevezetési irányelvek a németországi költségvetési integrációs mintához (örökölt)](emea-deu-fi-sample-sdk.md).
>
> A költségvetési integrációs minták új független csomagolási és kiterjesztési modelljének támogatását tervezik a későbbi verziókhoz.

Végezze el a költségvetési integráció beállítási lépéseit [a Kereskedelmi csatornák](setting-up-fiscal-integration-for-retail-channel.md) pénzügyi integrációjának beállítása:

1. [Hozzon létre egy pénzügyi regisztrációs folyamatot](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process). Jegyezze fel a pénzügyi regisztrációs folyamatnak [a pénzügyi regisztrációs szolgáltatásintegrációs mintájára](#set-up-the-registration-process) jellemző beállításait is.
1. [Állítsa be a hibakezelési beállításokat](setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).

    > [!WARNING]
    > Előfordulhat, hogy a költségvetési integrációs keretrendszer hibakezelési képességei nincsenek teljesen összhangban a helyi költségvetési szabályozással.
    >
    > - Javasoljuk, hogy hagyja el a **Folytassa a hibával** opció a **Adóügyi regisztrációs folyamat** oldal kikapcsolva, mert minden tranzakciót megfelelően regisztrálni kell, még akkor is, ha az első fiskális regisztrációs kísérlet nem volt sikeres.
    > - Mielőtt bekapcsolná a **Kihagyás** vagy **Megjelölés regisztráltként** opció a **Adóügyi regisztrációs folyamat** oldalon, beszélje meg az adóbejegyzési folyamat változásait adótanácsadójával vagy a helyi adóhivatallal.

1. [Az elhalasztott adóregisztráció](setting-up-fiscal-integration-for-retail-channel.md#enable-manual-execution-of-postponed-fiscal-registration) manuális végrehajtásának engedélyezése.
1. [Csatornaösszetevők konfigurálása](#configure-channel-components).

### <a name="set-up-the-registration-process"></a>A regisztrációs folyamat beállítása

A regisztrációs folyamat engedélyezéséhez kövesse az alábbi lépéseket a Kereskedelmi központ beállításához. További információ: [A kereskedelmi csatornák](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process) pénzügyi integrációjának beállítása.

1. Konfigurációs fájlok letöltése a pénzügyi dokumentumszolgáltatóhoz és a pénzügyi összekötőhöz:

    1. Nyissa meg a [Dynamics 365 Commerce Megoldások](https://github.com/microsoft/Dynamics365Commerce.Solutions/) adattárat.
    1. Válassza ki a megfelelő kiadási ágverziót az SDK/alkalmazás verziója szerint (például **[release/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33)**).
    1. Nyissa meg **az src \> FiscalIntegration \> Efr**.
    1. Töltse le az adódokumentum-szolgáltató konfigurációs fájlját a következő címről: **Konfigurációk \> Dokumentumszolgáltatók \> DocumentProviderFiscalEFRSampleGermany.xml** (például, [a kiadáshoz tartozó fájl/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/blob/release/9.33/src/FiscalIntegration/Efr/Configurations/DocumentProviders/DocumentProviderFiscalEFRSampleGermany.xml)).
    1. Töltse le a pénzügyi összekötő konfigurációs fájlját a **Configurations \> Connectors \> ConnectorEFRSample.xml** (például [a kiadáshoz szükséges fájl/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/blob/release/9.33/src/FiscalIntegration/Efr/Configurations/Connectors/ConnectorEFRSample.xml)).

    > [!WARNING]
    > Az új független csomagolási és kiterjesztési [modell](../dev-itpro/build-pipeline.md) korlátai miatt jelenleg nem használható ehhez a költségvetési integrációs mintához. A Retail SDK előző verzióját kell használnia egy fejlesztői virtuális gépen az LCS-ben. A pénzügyi integrációs minta konfigurációs fájljai a Retail SDK következő mappáiban találhatók egy fejlesztői virtuális gépen az LCS-ben:
    >
    > - **Fiskális dokumentum-szolgáltató konfigurációs fájlja:** RetailSdk\\ SampleExtensions\\ CommerceRuntime\\ Extensions.DocumentProvider.EFRSample\\ Konfiguráció\\ DocumentProviderFiscalEFRSampleGermany.xml
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

- **Pályázati típus leképezés** – A fizetési módok leképezése a **PayG** (fizetési csoport) attribútumot a fiskális szolgáltatásnak küldött kérésekben. Íme az alapértelmezett leképezés:

    ```
    1: 0; 2: 1; 3: 3; 4: 8; 5: 2; 6: 0; 7: 7; 8: 6; 9: 0; 10: 8; 11: 1
    ```

    Az egyes párok első összetevője az üzlet számára beállított fizetési módot jelöli. A második komponens a megfelelő fizetési csoportot képviseli, amelyet az EFR adóregisztrációs szolgáltatás támogat. Az EFR által Németországban támogatott fizetési csoportokkal kapcsolatos további információkért lásd a [EFR hivatkozás](https://public.efsta.net/efr/).

    A fizetési módok mintaleképezése megfelel a szabványos bemutató adatokban konfigurált bolti fizetési módoknak.

    | Kifizetési mód | Fizetési mód neve |
    |----------------|---------------------|
    | 1              | Készpénz                |
    | 2              | Csekk               |
    | 3              | Kártya                |
    | 4              | Vevői számla    |
    | 5              | Egyéb               |
    | 6              | Pénznem            |
    | 7              | Bizonylat              |
    | 8              | Ajándékutalvány           |
    | 9              | Fizetőeszköz eltávolítása/váltópénz |
    | 10             | Hűségkártyák       |
    | 11             | Nem helyi ellenőrzések    |

    Ezért módosítania kell a mintaleképezést az alkalmazásban konfigurált fizetési módoknak megfelelően.

- **Tartalmazza az ügyfelek adatait** – Ha ez a paraméter be van kapcsolva, a fiskális szolgáltatáshoz intézett kérések az ügyfelek adatait, például neveket és címeket tartalmazzák abban az esetben, ha ügyfelet adnak hozzá egy tranzakcióhoz.
- **Hozzáadottérték-adó (ÁFA) díjak leképezése** – Az áfakódokhoz beállított adószázalékértékek leképezése a **TaxG** (adócsoport) attribútum értékeihez a adószolgáltatásnak küldött kérelmekben. Íme az alapértelmezett leképezés:

    ```
    A: 19.00; B: 7.00; C: 10.70; D: 5.50; E: 0.00
    ```

    Az egyes párok első összetevője egy áfaadó-csoportot képvisel, amelyet az EFR adóregisztrációs szolgáltatás támogat. A második összetevő a megfelelő héakulcsot képviseli. Az EFR által Németországban támogatott áfa-adócsoportokkal kapcsolatos további információkért lásd a [EFR hivatkozás](https://public.efsta.net/efr/).

- **Ajándékkártyák és betétek adócsoportja** – Az értéke a **AdóG** attribútum azokban a kérésekben, amelyeket az adószolgálatnak küldenek, az ajándékkártyákkal vagy betétekkel kapcsolatos műveletek alapján. Íme az alapértelmezett leképezés:

    ```
    G
    ```

- **ÁFA mentes adócsoport** – Az értéke a **AdóG** attribútumot a fiskális szolgáltatásnak küldött kérésekben az adókötelezettségek alól mentesített műveletek alapján. Íme az alapértelmezett leképezés:

    ```
    F
    ```

> [!NOTE]
> Az alapértelmezett adatleképezés adóbeállításai felelősek a rendszerben és az EFR szolgáltatásban található adócsoportok adóbeállításaiért. Adócsoportok csak akkor nyomtathatók a bizonylatokra, ha a **Kód a nyomtatáshoz** mező van beállítva a **A forgalmi adó kódjai** oldalon.

#### <a name="fiscal-connector-settings"></a>Pénzügyi összekötő beállításai

A költségvetési integrációs minta részeként megadott pénzügyi összekötő konfiguráció a következő beállításokat tartalmazza:

- **Végpont címe** – A pénzügyi regisztrációs szolgáltatás URL-címe.
- **Időtúllépés** – Az az idő, ezredmásodpercben, ameddig a fiskális összekötő vár a fiskális regisztrációs szolgáltatás válaszára.
- **Adóregisztrációs** értesítések megjelenítése – Ez a jelző szabályozza, hogy a pénzügyi regisztrációs szolgáltatás visszaküldéséről szóló értesítések megjelenjenek-e az üzemeltetőnek.

### <a name="configure-channel-components"></a>Csatornaösszetevők konfigurálása

> [!WARNING]
> Az új független csomagolási és kiterjesztési [modell](../dev-itpro/build-pipeline.md) korlátai miatt jelenleg nem használható ehhez a költségvetési integrációs mintához. A Retail SDK előző verzióját kell használnia egy fejlesztői virtuális gépen az LCS-ben. További információkért lásd [Bevezetési irányelvek a németországi költségvetési integrációs mintához (örökölt)](emea-deu-fi-sample-sdk.md).
>
> A költségvetési integrációs minták új független csomagolási és kiterjesztési modelljének támogatását tervezik a későbbi verziókhoz.

#### <a name="set-up-the-development-environment"></a>A fejlesztési környezet beállítása

A minta tesztelésére és kiterjesztésére vonatkozó fejlesztési környezet beállításához kövesse az alábbi lépéseket.

1. Klónozza vagy töltse le a [Dynamics 365 Commerce Solutions](https://github.com/microsoft/Dynamics365Commerce.Solutions) adattárat. Válassza ki a megfelelő kiadási ágverziót az SDK/alkalmazás verziójának megfelelően. További információkért lásd [Töltsön le Retail SDK-mintákat és referenciacsomagokat a GitHubból és a NuGet](../dev-itpro/retail-sdk/sdk-github.md).
1. Nyissa meg az EFR-megoldást itt: **Dynamics365Commerce.Solutions\\ Fiskális integráció\\ Efr\\ EFR.sln**, és megépíteni.
1. Commerce futásidejű bővítmények telepítése:

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

    - Ban,-ben **Efr\\ HardwareStation\\ HardwareStation.EFR.Telepítő\\ kuka\\ Debug\\ net461** mappát, keresse meg a **HardwareStation.EFR.Telepítő** telepítő.
    - Indítsa el a bővítménytelepítőt a parancssorból:

        ```Console
        HardwareStation.EFR.Installer.exe install --verbosity 0
        ```

#### <a name="production-environment"></a>Működési környezet

Kövesse a lépéseket [Állítson be egy összeállítási folyamatot a fiskális integrációs mintához](fiscal-integration-sample-build-pipeline.md) a Cloud Scale Unit és az önkiszolgáló telepíthető csomagok létrehozása és kiadása a költségvetési integrációs mintához. A **EFR build-pipeline.yml** sablon YAML fájl megtalálható a **Csővezeték\\ YAML_Files** mappa a [Dynamics 365 Commerce Megoldások](https://github.com/microsoft/Dynamics365Commerce.Solutions) adattár.

## <a name="design-of-extensions"></a>Bővítések tervezése

A németországi adóbejegyzési szolgáltatás integrációs mintája a [fiskális integrációs funkcionalitás](fiscal-integration-for-retail-channel.md) és a Retail SDK része. A minta a **Solutions\\ adattár srcFiscalIntegration\\Efr**[Dynamics 365 Commerce mappájában](https://github.com/microsoft/Dynamics365Commerce.Solutions/) található (például [a kiadási/9.33-as](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/Efr) minta). A minta [áll](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services) egy fiskális dokumentumszolgáltató, amely a kiterjesztése CRT és egy fiskális csatlakozó, amely a Commerce Hardware Station kiterjesztése. A Kiskereskedelmi SDK használatáról a Retail SDK architektúrája [és](../dev-itpro/retail-sdk/retail-sdk-overview.md) build-folyamat beállítása a független csomagolású SDK-hoz [című témakörben talál](../dev-itpro/build-pipeline.md) további információt.

> [!WARNING]
> Az új független csomagolási és kiterjesztési [modell](../dev-itpro/build-pipeline.md) korlátai miatt jelenleg nem használható ehhez a költségvetési integrációs mintához. A Retail SDK előző verzióját kell használnia egy fejlesztői virtuális gépen az LCS-ben. További információkért lásd [Bevezetési irányelvek a németországi költségvetési integrációs mintához (örökölt)](emea-deu-fi-sample-sdk.md). A költségvetési integrációs minták új független csomagolási és kiterjesztési modelljének támogatását tervezik a későbbi verziókhoz.

### <a name="crt-extension-design"></a>CRT bővítmény kialakítása

Az adódokumentum-szolgáltató bővítmény célja szolgáltatás-specifikus dokumentumok előállítása és válaszok kezelése az adónyilvántartási szolgáltatástól.

#### <a name="request-handler"></a>Kérelemkezelő

A dokumentumszolgáltatónak egy kéréskezelője van, **DocumentProviderEFRFiscalDEU**. Ez a kezelő az adóregisztrációs szolgáltatás adódokumentumainak generálására szolgál. Ez örökölte a **INamedRequestHandler** felület. A **HandlerName** metódus felelős a kezelő nevének visszaadásáért. A kezelő nevének meg kell egyeznie a Kereskedelmi központban megadott összekötő dokumentumszolgáltató nevével.

Az összekötő a következő kéréseket támogatja:

- **GetFiscalDocumentDocumentProviderRequest** – Ez a kérés információt tartalmaz arról, hogy milyen dokumentumot kell létrehozni. Egy szolgáltatásspecifikus dokumentumot ad vissza, amelyet regisztrálni kell a pénzügyi regisztrációs szolgáltatásban.
- **GetFiscalTransactionExtendedDataDocumentProviderRequest** – Ez a kérés a választ a kiterjesztett adatokkal együtt adja vissza.

#### <a name="configuration"></a>Konfiguráció

Az adódokumentum-szolgáltató konfigurációs fájlja a címen található **src\\ Fiskális integráció\\ Efr\\ Konfigurációk\\ Dokumentumszolgáltatók\\ DocumentProviderFiscalEFRSampleGermany.xml** ban,-ben [Dynamics 365 Commerce Megoldások](https://github.com/microsoft/Dynamics365Commerce.Solutions/) adattár. A fájl célja, hogy lehetővé tegye a költségvetési dokumentumszolgáltató beállításainak konfigurálását a Commerce központjából. A fájlformátum igazodik a pénzügyi integráció konfigurációjának követelményeihez.

### <a name="hardware-station-extension-design"></a>Hardverállomás-bővítés kialakítása

A költségvetési összekötő bővítmény célja a pénzügyi regisztrációs szolgáltatással való kommunikáció.

A hardverállomás bővítménye **HardwareStation.Extension.EFRSample**. A HTTP protokoll használatával nyújt be olyan dokumentumokat, amelyeket a CRT bővítmény generál a pénzügyi regisztrációs szolgáltatásnak. Kezeli továbbá a pénzügyi regisztrációs szolgáltatástól kapott válaszokat.

#### <a name="request-handler"></a>Kérelemkezelő

Az **EFRHandler** kérelemkezelője a belépési pont a pénzügyi regisztrációs szolgáltatáshoz benyújtott kérelmek kezeléséhez. Ezt a kezelőt a **INamedRequestHandler** felület. A **HandlerName** metódus felelős a kezelő nevének visszaadásáért. A kezelő nevének meg kell egyeznie a Kereskedelmi központban megadott pénzügyi összekötő nevével.

Az összekötő a következő kéréseket támogatja:

- **SubmitDocumentFiscalDeviceRequest** – Ez a kérelem dokumentumokat küld a pénzügyi regisztrációs szolgálatnak, és visszaküldi a választ.
- **IsReadyFiscalDeviceRequest** – Ez a kérés a pénzügyi regisztrációs szolgáltatás állapotfelmérésére szolgál.
- **InitializeFiscalDeviceRequest** – Ez a kérés a pénzügyi regisztrációs szolgáltatás inicializálására szolgál.

#### <a name="configuration"></a>Konfiguráció

A fiskális csatlakozó konfigurációs fájlja a következő címen található: **src\\ Fiskális integráció\\ Efr\\ Konfigurációk\\ Csatlakozók\\ CsatlakozóEFRSample.xml** ban,-ben [Dynamics 365 Commerce Megoldások](https://github.com/microsoft/Dynamics365Commerce.Solutions/) adattár. A fájl célja, hogy lehetővé tegye a pénzügyi összekötő beállításainak konfigurálását a Commerce központjából. A fájlformátum igazodik a pénzügyi integráció konfigurációjának követelményeihez.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
