---
title: Pénzügyi regisztrációs szolgáltatás integrációját bemutató minta Ausztriára vonatkozóan
description: Ez a cikk áttekintést nyújt az Ausztriában található pénzügyi integrációs mintavételről Microsoft Dynamics 365 Commerce.
author: EvgenyPopovMBS
ms.date: 03/04/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2019-3-1
ms.openlocfilehash: 099c3630d035ea673342d8345cd8f65dbd6db6a5
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8873358"
---
# <a name="fiscal-registration-service-integration-sample-for-austria"></a>Pénzügyi regisztrációs szolgáltatás integrációját bemutató minta Ausztriára vonatkozóan

[!include[banner](../includes/banner.md)]

Ez a cikk áttekintést nyújt az Ausztriában található pénzügyi integrációs mintavételről Microsoft Dynamics 365 Commerce.

Az Ausztriában használt Dynamics 365 Retail pénztárgépekkel kapcsolatos helyi pénzügyi követelmények követelményeinek megfelelően az Ausztriában használt funkciók közé tartozik a pénztárgép és a külső pénzügyi regisztrációs szolgáltatás mintaintegrációja. A minta kiterjeszti a pénzügyi [integrációs funkciókat](fiscal-integration-for-retail-channel.md). [Az EFSTA](https://www.efsta.eu/at/fiskalloesungen/oesterreich) EFR (Electronic Fiscal Register) [megoldásán](https://www.efsta.eu/at/) alapul, és HTTPS protokollon keresztül engedélyezi a kommunikációt az EFR szolgáltatással. Az EFR szolgáltatásnak vagy a Retail hardverállomáson, vagy egy hardverállomásról csatlakoztatott külön számítógépen kell lennie. A minta forráskód formájában kapható, és része a Retail szoftverfejlesztői csomagnak (SDK).

A Microsoft nem ad ki hardvert, szoftvert vagy dokumentációt az EFSTA rendszerből. Az EFR-megoldás bejle- és működésről az EFSTA-hoz [forduljon](https://www.efsta.eu/at/kontakt).

## <a name="scenarios"></a>Forgatókönyvek

A pénzügyi nyilvántartási szolgáltatás integrációs mintája az alábbi esetekről nyújt fedezetet Ausztriában:

- Készpénztranzakciók regisztrálása a pénzügyi regisztrációs szolgáltatásban:

    - Részletes tranzakcióadatok küldése a pénzügyi regisztrációs szolgáltatásnak Ezek az adatok tartalmazzák az értékesítési sorok adatait, valamint az engedményekkel, kifizetésekkel és adókkal kapcsolatos adatokat.
    - Válasz rögzítése a pénzügyi regisztrációs szolgáltatástól. Ez a válasz digitális aláírást és a regisztrált tranzakcióra mutató hivatkozást tartalmaz.
    - Adók regisztrálása és hozzárendelése a pénzügyi nyilvántartási szolgáltatás adókódjaihoz.
    - A regisztrált tranzakció QR-kódának nyomtatása a nyugtára.

- Ajándékutalvány-műveletek és vevői betétek regisztrálása nem készpénzes tranzakcióként az pénzügyi regisztrációs szolgáltatásban:

    - Ajándékutalvány kiadása vagy pénz hozzáadása
    - Vevői számla letétének regisztrálása.
    - Vevői rendelés letétének regisztrálása.

- Nem értékesítési tranzakciók és események regisztrálása nem készpénzes tranzakcióként a pénzügyi regisztrációs szolgáltatásban:

    - Műszak megnyitása és Műszakzárás
    - Kezdő összeg, lebegőszós bejegyzés és fizetőeszköz kivétele
    - Ár felülbírálása
    - Adó felülírása
    - Nyugtamásolat kinyomtatása
    - Fiók kinyitása
    - X-jelentés nyomtatása
    - Z-jelentés nyomtatása

- A napvégi kivonatok (X/Z-jelentések) nyomtatása, amelyek Ausztria-specifikus mezőket tartalmaznak:

    - A vevőknek nyújtott termékek vagy szolgáltatások teljes száma
    - Értékesítés részletezése adómkulcs szerint
    - Kifizetések lebontása pénztáros/pénztárgép kezelője szerint
    - Árengedmények és visszatérítések, amelyek csökkentik a napi értékesítéseket
    - Nulla értékesítés (give egyed)

- Hibakezelés, például a következő lehetőségek:

    - Próbálja meg újra a pénzügyi regisztrációt, ha egy újrapróbálkozási művelet lehetséges, például ha a pénzügyi regisztrációs szolgáltatás nem érhető el, nem áll készen vagy nem válaszol.
    - Pénzügyi regisztráció elhalasztása.
    - Pénzügyi regisztráció kihagyása, vagy a tranzakció megjelölése regisztráltként, és infókódok beírása a hiba okának és a további információknak a rögzítéséhez.
    - Ellenőrizze a pénzügyi regisztrációs szolgáltatás elérhetőségét, mielőtt új értékesítési tranzakciót nyit meg vagy egy értékesítési tranzakciót véglegesítettek.

### <a name="gift-cards"></a>Ajándékutalványok

A pénzügyi regisztrációs szolgáltatás integrációs mintája az ajándékutalványokkal kapcsolatos következő szabályokat valósítja meg:

- Az ajándékutalvány-kiadáshoz *·* *és* az ajándékutalvány-műveletekhez hozzáadás készpénztranzakcióból származó értékesítési sorok kihagyása Ahelyett, hogy ezeket a sorokat egy készpénztranzakció részeként regisztrálja, külön, nem készpénzes tranzakcióként regisztrálja őket a pénzügyi regisztrációs szolgáltatásban.
- Ne nyomtass adócsoport-részletezést és QR-kódot a nyugtára, ha a nyugta csak ajándékutalvány-sorokból áll.
- A tranzakcióban kiadott vagy újra felszámított ajándékutalványok teljes összegének nyomtatása a nyugtán található készpénztranzakció összegtől függetlenül.
- A kifizetési sorok számított módosításainak mentése a csatorna-adatbázisban a megfelelő pénzügyi tranzakcióra való hivatkozással.
- Az ajándékutalványos fizetés rendszeres fizetésnek számít.

### <a name="customer-deposits-and-customer-order-deposits"></a>Vevői betétek és vevői rendelési betétek

A pénzügyi nyilvántartási szolgáltatás integrációs mintája a vevői betétekre és a vevői rendelési betétekre vonatkozó következő szabályokat valósítja meg:

- Nem készpénzes tranzakció regisztrálása, ha a tranzakció vevői letét.
- Nem készpénzes tranzakció regisztrálása, ha a tranzakció csak vevői rendelés letétét vagy a vevői rendelés letéti visszatérítését tartalmazza.
- A vevői rendelés letéti összegének levonása a kifizetési sorokból a vevői rendelés létrehozásakor.
- A csatorna-adatbázis fizetési sorai kiszámított korrekcióinak mentése egy vevői rendelés pénzügyi tranzakciójára való hivatkozással.

### <a name="limitations-of-the-sample"></a>A minta korlátai

A pénzügyi nyilvántartási szolgáltatás csak azokat a helyzeteket támogatja, amelyekben az ár tartalmazza az adót. Emiatt az üzletek **és** **a** vevők esetében az Ár tartalmazza az áfa beállítását Igen beállítást kell beállítani.

## <a name="set-up-commerce-for-austria"></a>A Commerce for Austria beállítása

Ez a szakasz az Ausztriához specifikus és ajánlott Kereskedelmi beállításokat írja le. A további tudnivalókat lásd [a Commerce honlapon](../index.md).

Az Ausztria-specifikus funkciók használatához a következő beállításokat kell megadni:

- A jogi személy elsődleges címében **állítsa az Ország/terület** **mezőt AUT** (Ausztria) beállításra.
- Minden, Ausztriában található üzlet PÉNZTÁRi funkcióprofiljában állítsa **az ISO-kód** **mezőt AZ AUSZTRIA (Ausztria**) kódra.

A következő beállításokat kell megadni Ausztriához is. Ne feledje, hogy a beállítások befejezése után futtatnia kell a megfelelő elosztási feladatokat.

### <a name="set-up-vat-per-austrian-requirements"></a>Áfa beállítása osztrák követelmények szerint

Létre kell hoznia áfakódokat, áfacsoportokat és cikkadócsoportokat. A termékekre és szolgáltatásokra vonatkozó áfaadatokat is be kell állítani. Az áfa funkció beállítási és használatával kapcsolatos további tudnivalókat lásd: [Áfa áttekintése](../../finance/general-ledger/indirect-taxes-overview.md).

Az értékesítési nyugtákra rövidített kódot nyomtathat az áfakódhoz (például "A" vagy "B"). A funkció elérhetővé tenni az **Áfakódok** nyomtatása lapon található **Kód nyomtatása mezőt**.

### <a name="set-up-stores"></a>Üzletek beállítása

Az Üzletek **lapon** frissítse az üzlet adatait. Konkrétabban:

- Adja meg **az Áfacsoport** mezőben azt az áfacsoportot, amely az alapértelmezett vevőnek való értékesítéshez használatos.
- Az Árak tartalmazzák **az áfa beállítást** Igen **beállításra**.
- Állítsa be **a Név** mezőt a vállalat nevére. Ezzel a módosítással garantálható, hogy a vállalat neve megjelenik az értékesítési nyugtán. Másik lehetőségként a vállalat nevét felveheti az értékesítési nyugtaelrendezésbe szabadszövegként.
- Állítsa be **az Adóazonosító szám (TIN) mezőt** a vállalat azonosítószáma mezőre. Ezzel a módosítással garantálható, hogy a vállalat azonosítószáma megjelenik az értékesítési nyugtán. Másik lehetőségként a vállalat azonosítóját hozzáadhatja az értékesítési nyugta elrendezéséhez szabadszövegként.

### <a name="set-up-functionality-profiles"></a>Funkcióprofilok beállítása

POS-funkcióprofilok beállítása:

- Állítsa be **a** **nyugtaszámozást** a Nyugtaszámozás gyorsábra az értékesítés, **·** **értékesítési** rendelés és visszáru-bevételezési tranzakciótípusok rekordjainak létrehozásával vagy frissítésével.

### <a name="configure-custom-fields-so-that-they-can-be-used-in-receipt-formats-for-sales-receipts"></a>Egyéni mezők konfigurálása az értékesítési nyugták nyugtaformátumában való használhatóra

A POS nyugtaformátumokban használt nyelvi szövegeket és egyéni mezőket beállíthatja. A nyugtabeállítást létrehozó felhasználó alapértelmezett vállalatának ugyanaznak kell lennie, mint ahol a nyelvi szöveg beállítása létre van hozva. Másik lehetőségként ugyanazt az idegen nyelvű szöveget kell létrehozni a felhasználó alapértelmezett vállalatában, valamint annak az üzletnek a jogi személyében, amely számára a beállítást létrehozták.

Adja hozzá **a Nyelv szöveglapon** a következő rekordokat a nyugtaelrendezések egyéni mezőinek címkéihez. Ne feledje, **hogy** **a táblázatban** látható nyelvazonosító, **szövegazonosító** és szöveg értékek példák. A beállításokat az igényeknek megfelelően módosíthatja. A használt **szövegazonosító** értékeknek azonban egyedinek kell lennie, és nem lehet kisebbek a 900001.

Adja hozzá a következő POS-címkéket **a** tábla Nyelvi szövegének **POS** szakaszához:

| Nyelvazonosító | Szövegazonosító | Szöveg                      |
|-------------|---------|---------------------------|
| hu       | 900001  | QR-kód                   |
| hu       | 900002  | Folytonos szám         |
| hu       | 900003  | Kiskereskedelmi adó nyomtatási kódja     |
| hu       | 900004  | Összesen (értékesítés)             |
| hu       | 900005  | Adó összesen (értékesítés)         |
| hu       | 900006  | Adóval (értékesítéssel) összesen |
| hu       | 900007  | Adó összege (értékesítés)        |
| hu       | 900008  | Adóalap (értékesítés)         |

Adja hozzá **a** következő rekordokat az Egyéni mezők lapon a nyugtaelrendezések egyéni mezőihez. A felirat **szövegazonosító értékeinek** meg **·** **kell felelniük a Nyelv szövegoldalán megadott szövegazonosító értékeknek:**

| Név                 | Típus    | Képaláírás-szöveg azonosítója |
|----------------------|---------|-----------------|
| QRCODE               | Fogadás | 900001          |
| FOLYTONOS SZÁM     | Fogadás | 900002          |
| RETAILPRINTCODE      | Fogadás | 900003          |
| BEVÉTELI           | Fogadás | 900004          |
| SALESTOTALTAX        | Fogadás | 900005          |
| SALESTOTALLUDETAX | Fogadás | 900006          |
| SALESTAMOUNT ÖSSZEG       | Fogadás | 900007          |
| SALESTAXBASIS        | Fogadás | 900008          |

> [!NOTE]
> Fontos, hogy a megfelelő egyéni mezőneveket adja meg az előző táblázatban felsoroltak szerint. Helytelen egyéni mezőnév esetén hiányoznak az adatok a nyugtákból.

### <a name="configure-receipt-formats"></a>Nyugtaformátumok konfigurálása

Minden szükséges bevételezési formátumnál módosítsa **a** Nyomtatás viselkedése mező értékét "Mindig **nyomtatás" értékre**.

A Nyugtaformátum-tervezőben adja hozzá a következő egyéni mezőket a megfelelő nyugtaszakaszokhoz. A mezőnevek megfelelnek az előző szakaszban meghatározott nyelvszövegnek.

- **Fejléc:** Adja hozzá a következő mezőket:

    - **Az üzlet neve** **és adóazonosító szám mezői**, amelyek a vállalat nevének és azonosító számának a nyugtákra való nyomtatására használhatók. Másik lehetőségként a vállalat nevét és azonosító számát is hozzáadhatja az elrendezéshez szabadszövegként.
    - **Üzlet címe**, **Dátum**, **Idő 24h**, **Nyugta száma** és **Jegyzék száma mezők**
    - **Folytonos szám** mezők, amelyek azonosítják a készpénztranzakciók számát a pénzügyi regisztrációs szolgáltatásban.

- **Sorok:** Adja hozzá a következő mezőket:

    - **Cikknév**.
    - **Mennyiség**
    - **Teljes ár adóval**.
    - **Kiskereskedelmi adó – nyomtatási kód**, amely a cikkre vonatkozó áfakódnak megfelelő rövidített kód nyomtatására használható.

- **Lábléc:** Adja hozzá a következő mezőket:

    - Fizetési mezők, amelyek segítségével kinyomtathatók az egyes fizetési módok kifizetési összegei. Hozzáadhatja például a **Fizetőeszköz neve** **és** a Fizetőeszköz összege mezőket az elrendezés egy sorában.
    - **Értékesítés összesen mezőcsoportja**:

        - **Összesen (értékesítés)** mező, amely a nyugta teljes készpénzes értékesítésének nyomtatására használatos. Az összeg nem tartalmazza az adót. Az előlegek és ajándékutalvány-műveletek nem tartoznak ide.
        - **Az Értékesítés adóval együtt mező** összege, amely a bevételezés teljes készpénzes értékesítésének nyomtatására használatos. Az összeg tartalmaz adót. Az előlegek és ajándékutalvány-műveletek nem tartoznak ide.
        - **Összes adó (értékesítés)** mező, amely a bevételezés készpénzes értékesítések teljes adóösszegének nyomtatására használatos. Az előlegek és ajándékutalvány-műveletek nem tartoznak ide.

    - **Adóeltérés mezőcsoportja**. Ennek a mezőcsoportnak az összes mezőjét egy külön sorba kell nyomtatni.

        - **Adóazonosító** mező, amely egy szabványos mező, amely lehetővé teszi az egyes áfakódok áfaösszegzésének nyomtatását. A mezőt hozzá kell adni egy új sorhoz.
        - **Adókulcs** mező, amely az áfakód tényleges adómértékének nyomtatására használt szokásos mező.
        - **Az Adóalap (értékesítés)** mező, amely a bevételezés teljes készpénzes értékesítésének nyomtatására használható az áfakódhoz. Az előlegek és ajándékutalvány-műveletek nem tartoznak ide.
        - **Adó összege (értékesítés)** mező, amely a bevételezés adóösszegének nyomtatására használható az áfakódhoz készpénzes értékesítéshez.
        - **Kiskereskedelmi adó – nyomtatási kód** mező, amely az áfakódnak megfelelő rövidített kód nyomtatására használható.

    - **QR-kód** mező, amely a regisztrált készpénztranzakcióra való hivatkozás QR-kód formájában való nyomtatására szolgál.

        > [!NOTE]
        > A **QR-kód** értékét a pénzügyi jegyzék válaszából olvassa be a program. Az EFR válaszában csak akkor aD vissza egy QR-kódot, **ha** az EFR konfiguráció Attribútumok mezőjének értékét az EFSTA dokumentáció írja le. Az EFR konfiguráció Attribútumok mezőjében a QR-kódformátumot **BMP**-kódra **kell állítani**.

A nyugtaformátumok beállításával [és tervezésával kapcsolatos további tudnivalókat lásd a Nyugtaformátumok beállításával és tervezésával kapcsolatban](../receipt-templates-printing.md).

## <a name="set-up-fiscal-integration-for-austria"></a>Pénzügyi integráció beállítása Ausztriához

Az adóregisztrációs szolgáltatás integrációs mintája az adóügyi [integrációs](fiscal-integration-for-retail-channel.md) funkciókon alapul, és része a Retail SDK csomagnak. A minta a FiscalIntegration Efr src **\\\\** mappában található a megoldások tárházában ([Dynamics 365 Commerce például a release/9.33 mintában).](https://github.com/microsoft/Dynamics365Commerce.Solutions/)[...](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/Efr) A minta [egy](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services) pénzügyi dokumentumszolgáltatóból áll, amely a Commerce runtime () futási idő kiterjesztése CRT, és egy pénzügyi csatlakoztató, amely a Commerce Hardware Station kiterjesztése. A Retail SDK használatával kapcsolatos további tudnivalókat lásd a Retail SDK [architektúrája és a független csomagolásos SDK](../dev-itpro/retail-sdk/retail-sdk-overview.md)[felépítési csővezetékének beállítása.](../dev-itpro/build-pipeline.md)

> [!WARNING]
> Az új független csomagolási és [bővítési](../dev-itpro/build-pipeline.md) modell korlátai miatt jelenleg nem használható ehhez a pénzügyi integrációs mintához. A Retail SDK korábbi verzióját egy fejlesztő virtuális gépen (VM) kell használnia a Lifecycle Services (LCS) Microsoft Dynamics szolgáltatásban. A további tudnivalókat [lásd az Ausztriához (legacy) vonatkozó pénzügyi integrációs minta telepítési irányelveinél](emea-aut-fi-sample-sdk.md). Az új független csomagolási és kiterjesztésmodell támogatása a pénzügyi integrációs mintákkal a későbbi verziókban tervezve lesz.

A pénzügyi integráció beállítási lépéseit [a Commerce-csatornákhoz való pénzügyi integráció beállítása lépései szerint lehet végrehajtani](setting-up-fiscal-integration-for-retail-channel.md):

1. [Pénzügyi regisztrációs folyamat beállítása](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process). Ezenkívül jegyezze fel a [pénzügyi nyilvántartási folyamatnak az ehhez a pénzügyi regisztrációs szolgáltatásintegrációs mintához specifikus beállításait](#set-up-the-registration-process).
1. [Hibakezelési beállítások megadása](setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).
1. [Halasztott pénzügyi regisztráció kézi végrehajtásának engedélyezése](setting-up-fiscal-integration-for-retail-channel.md#enable-manual-execution-of-postponed-fiscal-registration)
1. [Csatornaösszetevők konfigurálása](#configure-channel-components)

### <a name="set-up-the-registration-process"></a>A regisztrációs folyamat beállítása

A regisztráció engedélyezéséhez kövesse az alábbi lépéseket a Commerce Headquarters beállításához. A további tudnivalókat lásd [A Commerce-csatornák pénzügyi integrációjának beállítása.](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process)

1. A pénzügyi bizonylat szolgáltatójának és a pénzügyi csatlakoztatónak megfelelő konfigurációs fájlok letöltése:

    1. Nyissa meg [Dynamics 365 Commerce a megoldástárházat](https://github.com/microsoft/Dynamics365Commerce.Solutions/).
    1. Az SDK/alkalmazás verziójának (**[például kiadás/9.33) megfelelő kiadási ágverzió kiválasztása](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33)**.
    1. A **pénzügyiintegration-efr.rc \>\> megnyitása**
    1. **Nyissa meg a Configurations \> DocumentProviders** fájlt, és töltse le a pénzügyi dokumentumszolgáltató konfigurációs fájljait: **DocumentProviderFiscalEFRSampleAustria.xml** és **DocumentProviderNonFiscalEFRSampleAustria.xml** ([például a fájlok helye a kiadáshoz/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/Efr/Configurations/DocumentProviders)).
    1. Töltse le a pénzügyi csatlakoztató konfigurációs fájlját **a Configurations Connectors \>\> ConnectorEFRSample.xml** fájlban ([például a release/9.33 fájlban](https://github.com/microsoft/Dynamics365Commerce.Solutions/blob/release/9.33/src/FiscalIntegration/Efr/Configurations/Connectors/ConnectorEFRSample.xml)).

    > [!WARNING]
    > Az új független csomagolási és [bővítési](../dev-itpro/build-pipeline.md) modell korlátai miatt jelenleg nem használható ehhez a pénzügyi integrációs mintához. A Retail SDK előző verzióját kell használnia egy fejlesztői VM-n az LCS-en. A pénzügyi integrációs minta konfigurációs fájljai a Retail SDK készlet alábbi mappáiban találhatók az LCS egy fejlesztői VIRTUÁLIS eszközében:
    >
    > - **Pénzügyi bizonylat szolgáltatójának konfigurációs fájljai:** RetailSdk\\ SampleExtensions\\ CommerceRuntime\\ Extensions.DocumentProvider.EFRSample\\ konfiguráció
    > - **Pénzügyi csatlakoztató konfigurációs fájlja:** RetailSdk\\ SampleExtensions\\ HardwareStation\\ Extension.EFRSample\\ konfiguráció
    > 
    > Az új független csomagolási és kiterjesztésmodell támogatása a pénzügyi integrációs mintákkal a későbbi verziókban tervezve lesz.

1. Lépjen a **Retail és Commerce \> Központ beállítása \> Paraméterek \> Commerce megosztott paraméterek** menüpontra. Az Általános **lapon** állítsa **a** Pénzügyi integráció engedélyezése lehetőséget Igen **beállításra**.
1. Menjen a **Retail and Commerce \> Csatorna beállítása \> pénzügyi integráció \> pénzügyi dokumentumszolgáltatóihoz**, és töltse be a korábban letöltött pénzügyi bizonylatszolgáltató konfigurációs fájljait.
1. Menjen a **Retail és Commerce \> csatorna beállítása \> Pénzügyi integráció \> pénzügyi csatlakoztatóihoz**, és töltse be a korábban letöltött pénzügyi csatlakoztató konfigurációs fájlját.
1. Ugrás a **Retail és Commerce \> csatorna beállítása \> Fiscal integration \> Connector funkcionális profiljaihoz**. Hozzon létre két új funkcionális profilt a csatlakoztatóhoz, egyet minden korábban betöltött pénzügyi dokumentumszolgáltatóhoz, és válassza ki a korábban betöltött pénzügyi csatlakoztatóját. Szükség szerint [frissítse az adatleképezés](#default-data-mapping) beállításait.
1. Ugrás a **Retail és Commerce \> csatorna beállítása \> Fiscal integration \> Connector műszaki profilokhoz**. Hozzon létre egy új technikai csatlakoztatóprofilt, és válassza ki a korábban betöltött pénzügyi csatlakoztatóját. Szükség szerint [frissítse a csatlakoztató](#fiscal-connector-settings) beállításait.
1. Ugrás a **Retail és Commerce \> csatorna beállítása Pénzügyi \> integráció \> Pénzügyi csatlakoztatócsoportjához** Hozzon létre két új pénzügyi csatlakoztatócsoportot, és egyet minden korábban létrehozott funkcionális profilhoz.
1. Ugrás a Kiskereskedelmi és **Commerce csatorna \> beállítása pénzügyi \> integráció \> pénzügyi regisztrációs folyamatainak lépéseihez**. Hozzon létre egy új pénzügyi regisztrációs folyamatot és két pénzügyi regisztrálási folyamatot, és válassza ki a korábban létrehozott pénzügyi csatlakoztatócsoportokat.
1. Ugorjon a következő elemre: **Retail és Commerce \>  Csatorna beállítása \> Pénztárbeállítás \>  Pénztárprofilok \> Funkcióprofilok**. Válasszon ki egy funkcióprofilt, amely ahhoz az üzlethez kapcsolódik, ahol aktiválni kell a regisztrációs folyamatot. A Pénzügyi regisztráció **folyamata** gyors oldalon válassza ki a korábban létrehozott pénzügyi regisztrációs folyamatot. Ha engedélyezni szeretné a nem pénzügyi események regisztrációját a POS terminálon, **·** **a Funkciók gyorsgombon, a POS** alatt állítsa **a Vizsgálat** lehetőséget Igen **beállításra**.
1. Lépjen a **Kiskereskedelem és kereskedelem \> Csatorna beállítás \> POS beállítás \> POS profilok \> Hardverprofilok** pontra. Válassza ki azt a hardverprofilt, amely ahhoz a hardverállomáshoz van kapcsolva, amelyhez a pénzügyi nyomtató csatlakozik. Válassza ki a **korábban** létrehozott csatlakoztató-technikai profilt a Pénzügyi perifériák gyorstára.
1. Nyissa meg az elosztási ütemezést (**Retail and Commerce \> Retail és Commerce IT \> Distribution schedule**), **majd válassza ki a 1070-es** **és 1090-es** feladatokat az adatoknak a csatorna-adatbázisba történő átviteléhez.

#### <a name="default-data-mapping"></a>Alapértelmezett adatleképezés

A pénzügyiintegrációs minta részeként megadott pénzügyi bizonylatszolgáltató konfigurációja a következő alapértelmezett adatleképezést tartalmazza:

- **Áfakulcsok megfeleltetése** – **az áfakódok százalékértékének megfeleltetése a pénzügyi szolgáltatásnak elküldött kérések TaxG** (adócsoport) attribútumának értékeihez. Az alapértelmezett hozzárendelés:

    ```
    A: 20.00; B: 10.00; C: 13.00; D: 0.00; E: 19.00; F: 7.00
    ```

    Minden pár első összetevője egy áfacsoportot képvisel, amelyet az EFR pénzügyi regisztrációs szolgáltatás támogat. A második összetevő a megfelelő áfakulcsot képviseli. Az EFR által Ausztriában támogatott áfacsoportokkal kapcsolatos további tudnivalókat lásd az [EFR hivatkozásban](https://public.efsta.net/efr/).

#### <a name="fiscal-connector-settings"></a>Pénzügyi csatlakoztató beállításai

A pénzügyi integrációs minta részeként biztosított pénzügyi csatlakoztató konfigurációja a következő beállításokat tartalmazza:

- **Végpont címe** – a pénzügyi regisztrációs szolgáltatás URL-címe.
- **Eszköz időtúllépése** – az az idő ezredmásodpercben, ahányszor a pénzügyi csatlakoztató választ vár a pénzügyi regisztrációs szolgáltatástól.
- **Pénzügyi regisztrációs értesítések megjelenítése** – ez a jelző határozza meg, hogy a pénzügyi regisztrációs szolgáltatás által visszaadott értesítéseket meg kell-e mutatni a kezelőnek.

### <a name="configure-channel-components"></a>Csatornaösszetevők konfigurálása

> [!WARNING]
> Az új független csomagolási és [bővítési](../dev-itpro/build-pipeline.md) modell korlátai miatt jelenleg nem használható ehhez a pénzügyi integrációs mintához. A Retail SDK előző verzióját kell használnia egy fejlesztői VM-n az LCS-en. A további tudnivalókat [lásd az Ausztriához (legacy) vonatkozó pénzügyi integrációs minta telepítési irányelveinél](emea-aut-fi-sample-sdk.md).
>
> Az új független csomagolási és kiterjesztésmodell támogatása a pénzügyi integrációs mintákkal a későbbi verziókban tervezve lesz.

#### <a name="set-up-the-development-environment"></a>A fejlesztői környezet beállítása

A minta tesztelésére és kiterjesztésére fejlesztői környezet beállításához kövesse az alábbi lépéseket.

1. Le kell tölteni vagy le kell [Dynamics 365 Commerce tölteni a megoldástárházat](https://github.com/microsoft/Dynamics365Commerce.Solutions). Válassza ki a kiadási ág megfelelő verzióját az SDK-nak vagy az alkalmazásverziónak megfelelően. A további tudnivalókat lásd [a Retail SDK-minta- és hivatkozáscsomagok letöltése aHub és NuGet](../dev-itpro/retail-sdk/sdk-github.md) a.
1. Nyissa meg az EFR-megoldást **a Dynamics365Commerce.Solutions\\ FiscalIntegration\\ Efr\\ EFR.sln** fájlban, és építse fel.
1. A következő CRT bővítmények telepítése:

    1. A bővítmény telepítője CRT:

        - **Commerce Scale Unit:** Az Efr **ScaleUnit.EFR.Installer\\\\ bin\\ debug\\ net461 \\** mappában keresse meg a ScaleUnit.EFR.Installer **telepítőjét**.
        - **Helyi CRT a Modern POS terminálon:** Az **Efr\\ ModernPOS\\ ModernPOS.EFR.Installer\\ bin\\ hibakeresési\\ net461** **mappában keresse meg a ModernPOS.EFR.Installer** telepítőjét.

    1. A kiterjesztés telepítőjét CRT a következő parancssorból indítja el:

        - **Commerce Scale Unit:**

            ```Console
            ScaleUnit.EFR.Installer.exe install --verbosity 0
            ```

        - **Helyi CRT a Modern POS terminálon:**

            ```Console
            ModernPOS.EFR.Installer.exe install --verbosity 0
            ```

1. Pénzügyi csatlakoztató-bővítmények telepítése:

    A pénzügyi csatlakoztató bővítményei a hardverállomásra [vagy](fiscal-integration-for-retail-channel.md#fiscal-registration-is-done-via-a-device-connected-to-the-hardware-station) a PÉNZTÁRi pénztárgépre [telepíthetők](fiscal-integration-for-retail-channel.md#fiscal-registration-is-done-via-a-device-or-service-in-the-local-network).

    1. Hardverállomás-bővítmények telepítése:

        1. Az Efr **HardwareStation\\ HardwareStation.EFR.Installer\\ bin\\ hibakeresési\\ net461\\** mappában keresse meg a HardwareStation.EFR.Installer telepítőjét **.**
        1. A kiterjesztés telepítőjét a parancssorból a következő parancs futtatásával indítja el.

            ```Console
            HardwareStation.EFR.Installer.exe install --verbosity 0
            ```

    1. Pos-bővítmények telepítése:

        1. Nyissa meg a POS pénzügyi **csatlakoztató minta megoldását a Dynamics365Commerce.Solutions\\ FiscalIntegration\\ PosFiscalConnectorSample\\ Contoso.PosFiscalConnectorSample.sln** fájlban, és építse ki.
        1. A PosFiscalConnectorSample **StoreCommerce.Installer\\ bin\\\\ net461 \\** mappában keresse meg a Contoso.PosFiscalConnectorSample.StoreCommerce.Installer **telepítőjét.**
        1. A kiterjesztés telepítőjét a következő parancsot futtató parancssorból indítja el.

            ```Console
            Contoso.PosFiscalConnectorSample.StoreCommerce.Installer.exe install --verbosity 0
            ```

#### <a name="production-environment"></a>Működési környezet

Hajtsa végre [a pénzügyi integrációs minta felépítési folyamatának beállításához szükséges lépéseket a](fiscal-integration-sample-build-pipeline.md) felhőskálaegység és az önkiszolgáló rendszer telepíthető csomagjainak előállításához és kiadásához a pénzügyi integrációs mintához. Az EFR build-pipeline.yml sablonFÁJL a megoldástárház csővezeték-YAML_Files **·** **\\** található.[Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions)

## <a name="design-of-extensions"></a>Bővítmények tervezése

Az adóregisztrációs szolgáltatás integrációs mintája az adóügyi [integrációs](fiscal-integration-for-retail-channel.md) funkciókon alapul, és része a Retail SDK csomagnak. A minta a FiscalIntegration Efr src **\\\\** mappában található a megoldások tárházában ([Dynamics 365 Commerce például a release/9.33 mintában).](https://github.com/microsoft/Dynamics365Commerce.Solutions/)[...](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/Efr) A minta [egy](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services) pénzügyi dokumentumszolgáltatóból áll, CRT amely a Commerce Hardverállomás kiterjesztése, és egy pénzügyi csatlakoztató. A Retail SDK használatával kapcsolatos további tudnivalókat lásd a Retail SDK [architektúrája és a független csomagolásos SDK](../dev-itpro/retail-sdk/retail-sdk-overview.md)[felépítési csővezetékének beállítása.](../dev-itpro/build-pipeline.md)

> [!WARNING]
> Az új független csomagolási és [bővítési](../dev-itpro/build-pipeline.md) modell korlátai miatt jelenleg nem használható ehhez a pénzügyi integrációs mintához. A Retail SDK előző verzióját kell használnia egy fejlesztői VM-n az LCS-en. A további tudnivalókat [lásd az Ausztriához (legacy) vonatkozó pénzügyi integrációs minta telepítési irányelveinél](emea-aut-fi-sample-sdk.md). Az új független csomagolási és kiterjesztésmodell támogatása a pénzügyi integrációs mintákkal a későbbi verziókban tervezve lesz.

### <a name="commerce-runtime-extension-design"></a>Commerce runtime bővítmény tervezése 

A kiterjesztés célja, amely egy pénzügyi bizonylat szolgáltatója, a szolgáltatásspecifikus dokumentumok generálása és a pénzügyi nyilvántartási szolgáltatás válaszának kezelnie kell.

#### <a name="request-handler"></a>Kérelemkezelő

A dokumentumszolgáltatókhoz két kérelemkezelő van:

- **DocumentProviderEFRFiscalAUT** – ezzel a kezelővel pénzügyi bizonylatokat lehet létrehozni a pénzügyi nyilvántartási szolgáltatás számára.
- **DocumentProviderEFRNonFiscalAUT** – ezzel a kezelővel nem pénzügyi bizonylatokat lehet létrehozni a pénzügyi nyilvántartási szolgáltatás számára.

Ezek a kezelők az **INamedRequestHandler felületről öröklődik**. A **HandlerName metódus** felelős a kezelő nevének visszaküldéséért. A kezelő nevének meg kell egyeznie a Commerce Headquarters szolgáltatásban megadott csatlakoztató dokumentumszolgáltató nevével.

Az csatlakoztató a következő kéréseket támogatja:

- **GetFiscalDocumentDocumentProviderRequest** – ez a kérés tartalmazza a létrehozandó dokumentum adatait. Olyan szolgáltatásspecifikus dokumentumot ad vissza, amely regisztrálva kell lennie a pénzügyi regisztrációs szolgáltatásban.
- **GetNonFiscalDocumentDocumentProviderRequest** – ez a kérés tartalmazza azokat az információkat, amelyek nem pénzügyi bizonylatokat kell generálni. Olyan szolgáltatásspecifikus dokumentumot ad vissza, amely regisztrálva kell lennie a pénzügyi regisztrációs szolgáltatásban.
- **GetSupportedRegistrableEventsDocumentProviderRequest** – ez a kérés a regisztrált események listáját adja eredményül. Jelenleg a következő események támogatottak: értékesítés, X-jelentés nyomtatása, Z-jelentés nyomtatása, vevői számla betétek, vevői rendelési betétek, könyvvizsgálati események és nem értékesítési tranzakciók.
- **GetFiscalRegisterResponseToSaveDocumentProviderRequest** – ez a kérés a pénzügyi regisztrációs szolgáltatás válaszát adja eredményül. A válasz egy karakterlánc formájában van szerializálva, hogy készen legyen a mentésre.

#### <a name="configuration"></a>Konfiguráció

A pénzügyi bizonylat szolgáltatójának **konfigurációs fájljai a következő megoldások tárház src\\ FiscalIntegration\\ Efr\\ Configurations\\ DocumentProviders**[Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/) mappájában találhatók:

- **DocumentProviderFiscalEFRSampleAustria** – a pénzügyi bizonylatok szolgáltatójának konfigurációs fájlja.
- **DocumentProviderNonFiscalEFRSampleAustria** – a nem pénzügyi bizonylatok pénzügyi bizonylatokat szolgáltató konfigurációs fájlja.

Ezeknek a fájloknak a célja a pénzügyi dokumentumszolgáltató beállításainak beállítása a Commerce Headquarters alkalmazásból. A fájlformátum igazodik a pénzügyi integráció konfigurációjának követelményeihez.

### <a name="hardware-station-extension-design"></a>Hardverállomás bővítményének tervezése

A pénzügyi csatlakoztató bővítményének célja, hogy kommunikáljon a pénzügyi regisztrációs szolgáltatással. A hardverállomás bővítmény a HTTP és HTTPS protokollokkal CRT küldheti el a kiterjesztés által a pénzügyi regisztrációs szolgáltatásnak generált dokumentumokat. Kezeli a pénzügyi regisztrációs szolgáltatástól kapott válaszokat is.

#### <a name="request-handler"></a>Kérelemkezelő

Az **EFRHandler** kérelemkezelő a pénzügyi regisztrációs szolgáltatás kérésének kezelésére használt belépési pont.

A kezelő az **INamedRequestHandler felületről öröklődik**. A **HandlerName metódus** felelős a kezelő nevének visszaküldéséért. A kezelő nevének meg kell egyeznie a Commerce Headquartersban megadott pénzügyi csatlakoztató nevével.

A pénzügyi csatlakoztató a következő kéréseket támogatja:

- **SubmitDocumentFiscalDeviceRequest** – ez a kérés dokumentumokat küld a pénzügyi regisztrációs szolgáltatásnak, és visszaküldi a választ.
- **IsReadyFiscalDeviceRequest** – ez a kérés az adóügyi regisztrációs szolgáltatás állapotellenőrzésére használható.
- **InitializeFiscalDeviceRequest** – ez a kérés a pénzügyi regisztrációs szolgáltatás inicializálására használatos.

#### <a name="configuration"></a>Konfiguráció

A pénzügyi csatlakoztató **konfigurációs fájlja a megoldástárházban\\ található FiscalIntegration\\ Efr\\ Configurations Connectors\\ Connectors ConnectorS\\ ConnectorEFRSample.xml**[Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/) fájlban található. A fájl célja, hogy engedélyezze a pénzügyi csatlakoztató beállításait a Commerce Headquarters alkalmazásból való konfigurálásban. A fájlformátum igazodik a pénzügyi integráció konfigurációjának követelményeihez.

### <a name="pos-fiscal-connector-extension-design"></a>POS pénzügyi csatlakoztató bővítményének tervezése

A POS pénzügyi csatlakoztató bővítményének célja, hogy kommunikáljon a POS pénzügyi regisztrációs szolgáltatásával. A HTTPS-protokollt használja kommunikációra.

#### <a name="fiscal-connector-factory"></a>Pénzügyi csatlakoztató gyára

A pénzügyi csatlakoztató gyári leképezi a csatlakoztató **nevét a pénzügyi csatlakoztató megvalósításra, és a Pos.Extension\\ Connectors\\ FiscalConnectorFactory.ts fájlban** található. A csatlakoztató nevének meg kell egyeznie a Commerce Headquarters által megadott pénzügyi csatlakoztató nevével.

#### <a name="efr-fiscal-connector"></a>EFR pénzügyi csatlakoztató

Az EFR pénzügyi csatlakoztató a **Pos.Extension\\ Connectors\\ EfrFiscalConnector.ts\\ fájlban** található. Az IFiscalConnector **felületet** valósítja meg, amely a következő kéréseket támogatja:

- **FiscalRegisterSubmitDocumentClientRequest** – ez a kérés dokumentumokat küld a pénzügyi regisztrációs szolgáltatásnak, és visszaküldi a választ.
- **FiscalRegisterIsReadyClientRequest** – ez a kérés a pénzügyi nyilvántartási szolgáltatás állapotellenőrzésére használható.
- **FiscalRegisterInitializeClientRequest** – ez a kérés a pénzügyi regisztrációs szolgáltatás inicializálására használható.

#### <a name="configuration"></a>Konfiguráció

A konfigurációs fájl a **\\ megoldástárház FiscalIntegration\\ Efr\\ Configurations\\ Connectors**[Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/) mappájában található. A fájl célja, hogy engedélyezze a Commerce Headquarters alkalmazásból konfigurálható pénzügyi csatlakoztató beállításait. A fájlformátum igazodik a pénzügyi integráció konfigurációjának követelményeihez. A következő beállításokat lehet hozzáadni:

- **Végpont címe** – a pénzügyi regisztrációs szolgáltatás URL-címe.
- **Időtúllépés** – az az idő ezredmásodpercben, ahányszor a csatlakoztató választ vár a pénzügyi regisztrációs szolgáltatástól.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
