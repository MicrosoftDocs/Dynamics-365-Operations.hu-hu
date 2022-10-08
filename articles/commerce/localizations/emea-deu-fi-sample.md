---
title: Adóügyi regisztrációs szolgáltatás integrációját bemutató minta Németországra vonatkozóan
description: Ez a cikk áttekintést nyújt Németország pénzügyi integrációs mintájairól Microsoft Dynamics 365 Commerce.
author: EvgenyPopovMBS
ms.date: 10/04/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2020-05-29
ms.openlocfilehash: a725badbce498e4e7b35aecb2500e273586c7b77
ms.sourcegitcommit: 2bc6680dc6b12d20532d383a0edb84d180885b62
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/06/2022
ms.locfileid: "9631453"
---
# <a name="fiscal-registration-service-integration-sample-for-germany"></a>Adóügyi regisztrációs szolgáltatás integrációját bemutató minta Németországra vonatkozóan

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

Ez a cikk áttekintést nyújt Németország pénzügyi integrációs mintájairól Microsoft Dynamics 365 Commerce.

A németországi pénztárgépekkel Dynamics 365 Commerce kapcsolatos helyi pénzügyi követelmények követelményeinek megfelelően a Németországra vonatkozó funkciók közé tartozik a pénztárgép és a külső pénzügyi regisztrációs szolgáltatás mintaintegrációja. A minta kiterjeszti a pénzügyi [integrációs funkciókat](fiscal-integration-for-retail-channel.md). [Az EFSTA](https://www.efsta.eu/de/fiskalloesungen/deutschland) EFR (Electronic Fiscal Register) [megoldásán](https://www.efsta.eu/de/) alapul, és HTTPS protokollon keresztül engedélyezi a kommunikációt az EFR szolgáltatással. Az EFR szolgáltatásnak a Retail hardverállomáson vagy egy hardverállomásról csatlakoztatott külön számítógépen kell lennie. A minta forráskód formájában származik, és része a Commerce szoftverfejlesztői csomagnak (SDK).

A Microsoft nem ad ki hardvert, szoftvert vagy dokumentációt az EFSTA rendszerből. Az EFR-megoldás bejle- és működésről az EFSTA-hoz [forduljon](https://www.efsta.eu/de/kontakt/kontakt).

## <a name="scenarios"></a>Forgatókönyvek

A következő helyzetekre a Németországra vonatkozó pénzügyi nyilvántartási szolgáltatás integrációs minta nyújt fedezetet.

### <a name="sales-operations"></a>Értékesítési műveletek

- **A készpénz- és áthozott értékesítések és visszaküldések regisztrálása a pénzügyi nyilvántartási szolgáltatásban:**

    Az értékesítési műveletek regisztrálása a következő lépésekből áll:

    1. A tranzakció kezdésének regisztrációja

        Az egyes tranzakciók kezdését egy, az EFR szolgáltatáshoz kapcsolódó technikai biztonsági elem (TSE) regisztrálja. A regisztráció eredményeként a TSE hozzárendel egy tranzakcióazonosítót (TID).

    2. A tranzakció végének regisztrációja

        Amikor a POS-terminálon megkötnek egy tranzakciót, annak regisztrálása ugyanazokkal a TID-számokkal történik, mint amelyet a tranzakció kezdetekor rendelt hozzá a rendszer. Abban a pillanatban a részletes tranzakcióadatokat elküldi a rendszer a pénzügyi regisztrációs szolgáltatásnak. Ezek az adatok tartalmazzák az értékesítési sorok adatait, valamint az engedményekkel, kifizetésekkel és adókkal kapcsolatos adatokat.

    3. Válasz rögzítése a pénzügyi regisztrációs szolgáltatásból

        A biztonsági adatok a TSE-től a válasz részeként érkezik, és a rendszer a csatorna-adatbázis tranzakcióiba menti. A biztonsági adatok a következő információkból állnak:

        - Tid
        - A tranzakció kezdésének dátuma és időpontja
        - A tranzakció végének dátuma és időpontja
        - Aláírásszámláló
        - Érték ellenőrzése
        - A TSE sorozatszáma

- **Vevői rendelések regisztrálása a pénzügyi nyilvántartási szolgáltatásban:** A regisztrációs folyamat megegyezik a készpénz- és áthozott értékesítések és visszaküldések folyamatának folyamatán.
- **Az ajándékutalványokkal és letétekkel kapcsolatos műveletek regisztrálása:** A regisztrációs folyamat megegyezik a készpénz- és áthozott értékesítések és visszaküldések folyamatának folyamatán.

#### <a name="notifying-users-about-fiscal-registration-failures"></a>A felhasználók értesítése a pénzügyi regisztrációk sikertelenségéről

A pénzügyi nyilvántartási szolgáltatás kétféleképpen értesítheti a felhasználókat a pénzügyi regisztráció során történt hibákról:

- További információk nyomtatása a válaszból a nyugták **Információs üzenet** mezőjében.
- A pénzügyi szolgáltatástól származó értesítések megjelenítése felhasználói üzenetként a POS-terminálon.

    > [!NOTE]
    > Ehhez az értesítési mechanizmushoz be kell kapcsolva lennie **a Pénzügyi regisztrációk értesítése** paraméternek **a Connector műszaki** profilok lapján.

#### <a name="printing-receipts"></a>Nyugták nyomtatása

Németországban kötelező a nyugtanyomtatás. Minden bevételezésnek legalább a következő adatokat kell tartalmaznia:

- Vállalat neve és címe
- Adatok az árukról, beleértve az árakat és a mennyiségeket
- A beérkezett kifizetésekkel kapcsolatos adatok
- Adatok az adókról, beleértve az adómkulcsonkénti végösszegeket
- Biztonsági adatok:

    - Tid
    - A tranzakció kezdésének dátuma és időpontja
    - A tranzakció végének dátuma és időpontja
    - Aláírásszámláló
    - Érték ellenőrzése
    - A TSE sorozatszáma

- Tájékoztató üzenet

> [!NOTE]
> A nyugtákra egy QR-kód is nyomtatható. Bár a QR-kód megadása nem kötelező, ezért kifejezetten ajánljuk. Arról, hogy hogyan lehet a QR-kódot a pénzügyi regisztrációs szolgáltatás válaszának részeként leírni, az EFSTA\[ dokumentáció webhelyén közzétett "EFR Guide \] DE ["](https://public.efsta.net/efr/) dokumentumban olvasható.
>
> A **nyugták Információs üzenet** mezőjében a pénzügyi regisztrációs szolgáltatás értesítése látható. Ha például egy aláírási eszköz megszakad, a nyugtára speciális szöveg nyomtatható.

#### <a name="voided-suspended-and-recalled-transactions"></a>Érvénytelenített, felfüggesztett és visszahívott tranzakciók

- Az érvénytelenített tranzakciót a rendszer egy tranzakció megszüntetésére vonatkozó kérésként regisztrálja a pénzügyi nyilvántartási szolgáltatásban.
- A felfüggesztett tranzakciót arra kérik, hogy függesszen fel egy tranzakciót a pénzügyi nyilvántartási szolgáltatásban.
- A felfüggesztett tranzakció visszahívása egy új tranzakció kezdeteként van regisztrálva a pénzügyi nyilvántartási szolgáltatásban.

### <a name="non-sales-transactions-and-shift-closing"></a>Nem értékesítési tranzakciók és műszakzárás

A következő nem értékesítési tranzakciókat **regisztrálja a rendszer nem pénzügyi műveletként a pénzügyi regisztrációs szolgáltatásban aCÍMKÉS címkével**:

- Nyitó összeg elszámolása
- Váltópénzbetét
- Fizetőeszköz kivétele
- Széfes befizetés
- Banki befizetés
- Bevételi számlák
- Kiadási számlák

A **műszakzárási** művelet nem pénzügyi műveletként is regisztrálható a **pénzügyi regisztrációs szolgáltatásban aCÍMKÉS címkével**.

### <a name="data-export-and-audit"></a>Adatok exportálása és naplózása

Minden tranzakciót egy TSE-nek alá kell írnia, hogy biztosítsa integritását, eredetiségét és teljességét, valamint hogy megelőzze a rögzített adatok kezelését.

> [!WARNING]
> Csak tanúsított TSE használható. Az EFR-megoldásban támogatott adattípusokkal és modellekkel kapcsolatos tudnivalókat lásd az "EFR Guide \[DE\]" [dokumentumban, amelyet az EFSTA dokumentációjának webhelyén közzé](https://public.efsta.net/efr/) kell tenni. A TSE választásával és beszerzésével kapcsolatban forduljon az [EFSTA-hoz](https://www.efsta.eu/at/kontakt).

A német szabályozásnak támogatnia kell a DSFinV-K exportot. A DSFinV-K export az EFR megoldásban indítható el. A DSFinV-K exportról az EFSTA\[ dokumentáció webhelyén közzétett "EFR Guide \] DE ["](https://public.efsta.net/efr/) dokumentum nyújt további tájékoztatást.

### <a name="limitations-of-the-sample"></a>A minta korlátai

A pénzügyi nyilvántartási szolgáltatás csak azokat a helyzeteket támogatja, amelyekben az árak tartalmazzák az adót. Emiatt az üzletek **és** **a** vevők esetében az Árak tartalmazzák az áfa beállítást Igen beállításra kell beállítani.

A pénzügyi szolgáltatás nem támogatja azokat a helyzeteket, ahol egynél több áfakódot alkalmaznak ugyanabba a tranzakciósorba.

A pénzügyi integrációs keretrendszer nem támogatja az értékesítési árajánlatokat. Emiatt ezek a műveletek nincsenek regisztrálva a pénzügyi szolgáltatásban.

## <a name="set-up-commerce-for-germany"></a>A Commerce for Germany beállítása

Ez a szakasz a Németországra vonatkozó kereskedelmi beállításokat ismerteti. További tájékoztatás a [Commerce honlapon található](../index.md).

A Németországra jellemző funkciók használatához a következő beállításokat kell megadni.

- A jogi személy elsődleges címében állítsa az **Ország/régió** **mezőt DEU (Németország) beállításra**.
- Minden németországi üzlet PÉNZTÁRi **funkcióprofiljában állítsa az ISO-kód** **mezőt DE** (Németország) beállításra.

A következő beállításokat kell megadni Németország esetében is. A beállítás befejezése után mindenképpen futtassa a megfelelő elosztási feladatokat.

### <a name="set-up-vat-per-german-requirements"></a>Áfa beállítása német követelmények szerint

Létre kell hoznia áfakódokat, áfacsoportokat és cikkadócsoportokat. A termékekre és szolgáltatásokra vonatkozó áfaadatokat is be kell állítani. Az áfa funkció beállítási és használatával kapcsolatos további tudnivalókat lásd: [Áfa áttekintése](../../finance/general-ledger/indirect-taxes-overview.md).

Az értékesítési nyugtákra rövidített kódot nyomtathat az áfakódhoz (például "A" vagy "B"). Ha ezt a funkciót elérhetővé tenni, állítsa be **a Kód nyomtatása** mezőt az **Áfakódok lapon**.

### <a name="set-up-stores"></a>Üzletek beállítása

Az Üzletek **lapon** frissítse az üzlet adatait. Konkrétabban:

- Adja meg **az Áfacsoport** mezőben azt az áfacsoportot, amely az alapértelmezett vevőnek való értékesítéshez használatos.
- Az Árak tartalmazzák **az áfa beállítást** Igen **beállításra**.
- Állítsa be **a Név** mezőt a vállalat nevére. Ezzel a módosítással gondoskodhat arról, hogy a vállalat neve megjelenik az értékesítési nyugtán. Másik lehetőségként a vállalat nevét felveheti az értékesítési nyugtaelrendezésbe szabadszövegként.
- Állítsa be **az Adóazonosító szám (TIN) mezőt** a vállalat azonosítószáma mezőre. Ezzel a módosítással gondoskodhat arról, hogy a vállalat azonosítószáma megjelenjen az értékesítési nyugtán. Másik lehetőségként a vállalat azonosítóját hozzáadhatja az értékesítési nyugta elrendezéséhez szabadszövegként.

### <a name="set-up-functionality-profiles"></a>Funkcióprofilok beállítása

POS funkcióprofilok beállítása. Állítsa be **a** **nyugtaszámozást** a Nyugtaszámozás gyorsábra az értékesítés, **·** **értékesítési** rendelés és visszáru-bevételezési tranzakciótípusok rekordjainak létrehozásával vagy frissítésével.

### <a name="configure-custom-fields-so-that-they-can-be-used-in-receipt-formats-for-sales-receipts"></a>Egyéni mezők konfigurálása az értékesítési nyugták nyugtaformátumában való használhatóra

A POS nyugtaformátumokban használt nyelvi szövegeket és egyéni mezőket beállíthatja. A nyugtabeállítást létrehozó felhasználó alapértelmezett vállalatának ugyanaznak kell lennie, mint ahol a nyelvi szöveg beállítása létre van hozva. Másik lehetőségként ugyanazt az idegen nyelvű szöveget kell létrehozni a felhasználó alapértelmezett vállalatában, valamint annak az üzletnek a jogi személyében, amely számára a beállítást létrehozták.

Adja hozzá **a Nyelv szöveglapon** a következő rekordokat a nyugtaelrendezések egyéni mezőinek címkéihez. Ne feledje, **hogy** **a táblázatban** látható nyelvazonosító, **szövegazonosító** és szöveg értékek példák. A beállításokat az igényeknek megfelelően módosíthatja. A használt **szövegazonosító** értékeknek azonban egyedinek kell lennie, és nem lehet kisebbek a 900001.

Adja hozzá a következő POS-címkéket **a** Language **szövegoldal POS szakaszához**.

| Nyelvazonosító | Szövegazonosító | Szöveg                                  |
|-------------|---------|---------------------------------------|
| hu       | 900001  | QR-kód                               |
| hu       | 900002  | Tranzakció azonosítója                        |
| hu       | 900003  | Kiskereskedelmi adó nyomtatási kódja                 |
| hu       | 900004  | Adó összege (értékesítés)                    |
| hu       | 900005  | Adóalap (értékesítés)                     |
| hu       | 900006  | Tranzakció kezdő dátuma és időpontja           |
| hu       | 900007  | Tranzakció záró dátuma és időpontja             |
| hu       | 900008  | A biztonsági elem sorozatszáma |
| hu       | 900009  | Aláírásszámláló                     |
| hu       | 900010  | Érték ellenőrzése                           |
| hu       | 900011  | Információs üzenet                          |

Adja hozzá **a** következő rekordokat az Egyéni mezők lapon a nyugtaelrendezések egyéni mezőihez. A felirat szövegazonosító-értékeinek **meg** **·** **kell felelniük a Nyelv szövegoldalán megadott szövegazonosító értékeknek.**

| Név                            | Típus    | Képaláírás-szöveg azonosítója |
|---------------------------------|---------|-----------------|
| QRCODE\_ DE                      | Fogadás | 900001          |
| TRANSACTIONID\_ DE               | Fogadás | 900002          |
| RETAILPRINTCODE\_ DE             | Fogadás | 900003          |
| SALESTAMOUNT DE\_              | Fogadás | 900004          |
| SALESTAXBASIS DE\_               | Fogadás | 900005          |
| TRANSACTIONSTARTDATETIME\_ DE    | Fogadás | 900006          |
| TRANSACTIONENDDATETIME\_ DE      | Fogadás | 900007          |
| SECURITYELEMENTSERIALNUMBER\_ DE | Fogadás | 900008          |
| ALÁÍRÓ DE\_                 | Fogadás | 900009          |
| ALÁÍRÁS (De\_)                        | Fogadás | 900010          |
| INFOMESSAGE\_ DE                 | Fogadás | 900011          |

> [!NOTE]
> Fontos, hogy a megfelelő egyéni mezőneveket adja meg az előző táblázatban felsoroltak szerint. Helytelen egyéni mezőnév esetén hiányoznak az adatok a nyugtákból.

### <a name="configure-receipt-formats"></a>Nyugtaformátumok konfigurálása

Minden szükséges bevételezési formátumnál **módosítsa** **a Nyomtatás viselkedése mező értékét "Mindig nyomtatás" értékre.**

A Nyugtaformátum-tervezőben adja hozzá a következő egyéni mezőket a megfelelő nyugtaszakaszokhoz. A mezőnevek megfelelnek az előző szakaszban meghatározott nyelvszövegnek.

- **Fejléc:** Adja hozzá a következő mezőket:

    - **Az üzlet** neve **és adóazonosító szám mezői**, amelyek a vállalat nevének és azonosító számának a nyugtákra való nyomtatására használhatók. Másik lehetőségként a vállalat nevét és azonosító számát is hozzáadhatja az elrendezéshez szabadszövegként.
    - **Üzlet címe**, **Dátum**, **Idő 24h**, **Nyugta száma** és **Jegyzék száma mezők**

- **Sorok:** Adja hozzá a következő mezőket:

    - **Cikknév** mező
    - **Mennyiség** mező
    - **Teljes ár adómezővel**
    - **Kiskereskedelmi adó – nyomtatási kód** mező, amely a cikkre vonatkozó áfakódnak megfelelő rövidített kód nyomtatására használható

- **Lábléc:** Adja hozzá a következő mezőket:

    - Fizetési mezők, amelyek segítségével kinyomtathatók az egyes fizetési módok kifizetési összegei. Hozzáadhatja például a **Fizetőeszköz neve** **és** a Fizetőeszköz összege mezőket az elrendezés egy sorában.
    - Az Adó-lebontás **mezőcsoport** mezői. Ennek a mezőcsoportnak az összes mezőjét egy külön sorba kell nyomtatni.

        - **Adóazonosító** mező, amely egy szabványos mező, amely lehetővé teszi az egyes áfakódok áfaösszegzésének nyomtatását. A mezőt hozzá kell adni egy új sorhoz.
        - **Adókulcs** mező, amely az áfakód tényleges adómértékének nyomtatására használt szokásos mező.
        - **Az Adóalap (értékesítés)** mező, amely a bevételezés teljes készpénzes értékesítésének nyomtatására használható az áfakódhoz. Az előlegek és ajándékutalvány-műveletek nem tartoznak ide.
        - **Adó összege (értékesítés)** mező, amely a bevételezés adóösszegének nyomtatására használható az áfakódhoz készpénzes értékesítéshez.
        - **Kiskereskedelmi adó – nyomtatási kód** mező, amely az áfakódnak megfelelő rövidített kód nyomtatására használható.

    - A pénzügyi regisztrációs szolgáltatás által visszaadott biztonságos tranzakcióadatokat tartalmazó mezők:

        - **Tranzakcióazonosító** mező, amely a készpénztranzakció számát azonosítja a pénzügyi regisztrációs szolgáltatásban
        - **Tranzakció kezdő dátumának időmezője**
        - **Tranzakció záró dátumának időmezője**
        - **A biztonságielem-mező sorozatszáma**
        - **Aláírásszámláló** mező
        - **Értékmező** ellenőrzése
        - **QR-kód** mező, amely a regisztrált készpénztranzakcióra való hivatkozás nyomtatására szolgál QR-kód formájában.

        > [!NOTE]
        > A **QR-kód** értékét a pénzügyi jegyzék válaszából olvassa be a program. Az EFR válaszában csak akkor aD vissza egy QR-kódot, **ha** az EFR konfiguráció Attribútumok mezőjének értékét az EFSTA dokumentáció írja le. Az EFR konfiguráció Attribútumok mezőjében a QR-kódformátumot **BMP**-kódra **kell állítani**.

    - **Információs üzenet** mező, amely a pénzügyi regisztrációs szolgáltatás értesítési üzeneteit mutatja a nyugtákon. Ha például egy aláírási eszköz megszakad, a nyugtára speciális szöveg nyomtatható.

A nyugtaformátumok beállításával [és tervezésával kapcsolatos további tudnivalókat lásd a Nyugtaformátumok beállításával és tervezésával kapcsolatban](../receipt-templates-printing.md).

## <a name="set-up-fiscal-integration-for-germany"></a>Pénzügyi integráció beállítása Németország számára

A pénzügyi nyilvántartási szolgáltatás integrációs mintája Németország [esetében](fiscal-integration-for-retail-channel.md) a pénzügyi integrációs funkciókon alapul, és része a Commerce SDK szoftverfejlesztő készletnek. A minta a **\\ Solutions-tárház FiscalIntegration\\ Efr**[Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/) mappájában található. A [minta](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services) egy pénzügyi dokumentumszolgáltatóból áll, amely a Commerce runtime () futási idő kiterjesztése CRT, és egy pénzügyi csatlakoztató, amely a Commerce Hardware Station kiterjesztése. A Commerce SDK használatával kapcsolatos további tudnivalókat lásd A Commerce SDK [mintáinak és hivatkozási csomagjainak letöltése a BuildHub NuGet](../dev-itpro/retail-sdk/sdk-github.md)[szoftverfejlesztő készletből, valamint a független csomagolású SDK felépítési csővezetékének beállítása](../dev-itpro/build-pipeline.md).

> [!NOTE]
> A Pénzügyi nyilvántartási szolgáltatás integrációs minta Németország számára elérhető a Commerce SDK szoftverfejlesztői készletében a 10.0.29-es verziónak megfelelő verzióban. A Commerce 10.0.28-as vagy korábbi verziójában a Retail SDK korábbi verzióját kell használnia a Lifecycle Services (LCS) Microsoft Dynamics egy fejlesztői virtuális gépére (VM). A további tudnivalókat [lásd a Németországhoz (legacy) vonatkozó pénzügyi integrációs minta telepítési irányelveinél](emea-deu-fi-sample-sdk.md).

A pénzügyi integráció beállítási lépéseit [a Commerce-csatornákhoz való pénzügyi integráció beállítása lépései szerint lehet végrehajtani](setting-up-fiscal-integration-for-retail-channel.md):

1. [Pénzügyi regisztrációs folyamat beállítása](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process). Ezenkívül jegyezze fel a [pénzügyi nyilvántartási folyamatnak az ehhez a pénzügyi regisztrációs szolgáltatásintegrációs mintához specifikus beállításait](#set-up-the-registration-process).
1. [Hibakezelési beállítások megadása](setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).

    > [!WARNING]
    > Lehet, hogy a pénzügyi integrációs keretrendszer hibakezelési lehetőségei nem teljes mértékben igazodnak a helyi pénzügyi szabályozáshoz.
    >
    > - Javasoljuk **·** **·**, hogy a Pénzügyi regisztráció folyamat lapján hagyja kikapcsolva a Folytatás hiba esetén beállítást, mert minden tranzakciót megfelelően kell regisztrálni, még akkor is, ha az első pénzügyi regisztráció sikertelen volt.
    > - Mielőtt bekapcsolja a **Skip** **vagy a Mark as** **regisztrált** beállítást a Pénzügyi nyilvántartási folyamat lapon, meg kell tárgyalja a pénzügyi nyilvántartási folyamat ilyen módosításait az adótanácsadójával vagy a helyi adóhivatalsal.

1. [Halasztott pénzügyi regisztrációk kézi végrehajtásának engedélyezése](setting-up-fiscal-integration-for-retail-channel.md#enable-manual-execution-of-deferred-fiscal-registration).
1. [Csatornaösszetevők konfigurálása](#configure-channel-components)

### <a name="set-up-the-registration-process"></a>A regisztrációs folyamat beállítása

A regisztráció engedélyezéséhez kövesse az alábbi lépéseket a Commerce Headquarters beállításához. A további tudnivalókat lásd [A Commerce-csatornák pénzügyi integrációjának beállítása.](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process)

1. A pénzügyi bizonylat szolgáltatójának és a pénzügyi csatlakoztatónak megfelelő konfigurációs fájlok letöltése:

    1. Nyissa meg [Dynamics 365 Commerce a megoldástárházat](https://github.com/microsoft/Dynamics365Commerce.Solutions/).
    1. Válassza ki a kiadási ág megfelelő verzióját az SDK-nak vagy az alkalmazásverziónak megfelelően.
    1. A **pénzügyiintegration-efr.rc \>\> megnyitása**
    1. Töltse le a pénzügyi bizonylat szolgáltatójának konfigurációs fájlját a **Configurations \> DocumentProviders \> DocumentProviderFiscalEFRSampleGermany.xml fájlban**.
    1. Töltse le a pénzügyi csatlakoztató konfigurációs fájlját a **Configurations \> Connectors \> ConnectorEFRSample.xml fájlban**.

    > [!NOTE]
    > A Commerce rendszer 10.0.28-as vagy korábbi verziójában a Retail SDK előző verzióját kell használnia az LCS egy fejlesztői VIRTUÁLIS gépére. A pénzügyi integrációs minta konfigurációs fájljai a Retail SDK készlet alábbi mappáiban találhatók az LCS egy fejlesztői VIRTUÁLIS eszközében:
    >
    > - **Pénzügyi bizonylat szolgáltatójának konfigurációs fájlja:** RetailSdk\\ SampleExtensions\\ CommerceRuntime\\ Extensions.DocumentProvider.EFRSample\\ Configuration\\ DocumentProviderFiscalEFRSampleGermany.xml
    > - **Pénzügyi csatlakoztató konfigurációs fájlja:** RetailSdk\\ SampleExtensions\\ HardwareStation\\ Extension.EFRSample\\ Configuration\\ ConnectorEFRSample.xml

1. Lépjen a **Retail és Commerce \> Központ beállítása \> Paraméterek \> Commerce megosztott paraméterek** menüpontra. Az Általános **lapon** állítsa **a** Pénzügyi integráció engedélyezése lehetőséget Igen **beállításra**.
1. Menjen a **Retail és Commerce \> Csatorna beállítása pénzügyi \> integráció \> pénzügyi dokumentumszolgáltatóihoz**, és töltse be a korábban letöltött pénzügyidokumentum-szolgáltató konfigurációs fájlját.
1. Menjen a **Retail és Commerce \> csatorna beállítása \> Pénzügyi integráció \> pénzügyi csatlakoztatóihoz**, és töltse be a korábban letöltött pénzügyi csatlakoztató konfigurációs fájlját.
1. Ugrás a **Retail és Commerce \> csatorna beállítása \> Fiscal integration \> Connector funkcionális profiljaihoz**. Új funkcionális csatlakoztatóprofil létrehozása. Válassza ki a korábban betöltött dokumentumszolgáltatót és csatlakoztatót. Szükség szerint [frissítse az adatleképezés](#default-data-mapping) beállításait.
1. Ugrás a **Retail és Commerce \> csatorna beállítása \> Fiscal integration \> Connector műszaki profilokhoz**. Hozzon létre egy új technikai csatlakoztatóprofilt, és válassza ki a korábban betöltött pénzügyi csatlakoztatóját. Szükség szerint [frissítse a csatlakoztató](#fiscal-connector-settings) beállításait.
1. Ugrás a **Retail és Commerce \> csatorna beállítása Pénzügyi \> integráció \> Pénzügyi csatlakoztatócsoportjához** Hozzon létre egy új pénzügyi csatlakoztatócsoportot a korábban létrehozott csatlakoztató funkcionális profil számára.
1. Ugrás a Kiskereskedelmi és **Commerce csatorna \> beállítása pénzügyi \> integráció \> pénzügyi regisztrációs folyamatainak lépéseihez**. Hozzon létre egy új pénzügyi regisztrációs folyamatot és egy pénzügyi nyilvántartási folyamat lépését, és válassza ki a korábban létrehozott pénzügyi csatlakoztatócsoportot.
1. Ugorjon a következő elemre: **Retail és Commerce \>  Csatorna beállítása \> Pénztárbeállítás \>  Pénztárprofilok \> Funkcióprofilok**. Válasszon ki egy funkcióprofilt, amely ahhoz az üzlethez kapcsolódik, ahol aktiválni kell a regisztrációs folyamatot. A Pénzügyi regisztráció **folyamata** gyors oldalon válassza ki a korábban létrehozott pénzügyi regisztrációs folyamatot.
1. Lépjen a **Kiskereskedelem és kereskedelem \> Csatorna beállítás \> POS beállítás \> POS profilok \> Hardverprofilok** pontra. Válassza ki azt a hardverprofilt, amely ahhoz a hardverállomáshoz van kapcsolva, amelyhez a pénzügyi regisztrációs szolgáltatás csatlakozik. Válassza ki a **korábban** létrehozott csatlakoztató-technikai profilt a Pénzügyi perifériák gyorstára.
1. Nyissa meg az elosztási ütemezést (**Retail and Commerce \> Retail és Commerce IT \> Distribution schedule**), **majd válassza ki a 1070-es** **és 1090-es** feladatokat az adatoknak a csatorna-adatbázisba történő átviteléhez.

#### <a name="default-data-mapping"></a>Alapértelmezett adatleképezés

A pénzügyiintegrációs minta részeként megadott pénzügyi bizonylatszolgáltató konfigurációja a következő alapértelmezett adatleképezést tartalmazza:

- **Fizetőeszköz-típus hozzárendelése** – **a fizetési módok hozzárendelése a PayG** (fizetési csoport) attribútum értékeihez a pénzügyi szolgáltatásnak küldött kérések között. Az alapértelmezett hozzárendelés:

    ```
    1: 0; 2: 1; 3: 3; 4: 8; 5: 2; 6: 0; 7: 7; 8: 6; 9: 0; 10: 8; 11: 1
    ```

    Az egyes párok első komponense egy, az üzlethez beállított fizetési módot jelent. A második összetevő képviseli az EFR pénzügyi regisztrációs szolgáltatás által támogatott megfelelő fizetési csoportot. Az EFR által Németország számára támogatott fizetési csoportokkal kapcsolatos további tudnivalókat lásd az [EFR hivatkozásban](https://public.efsta.net/efr/).

    A fizetési módok minta-hozzárendelése megfelel az üzlet szokásos bemutató adataiban konfigurált fizetési módoknak.

    | Fizetési mód | Fizetési mód neve |
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
    | 11             | Nem helyi csekkek    |

    Ennek megfelelően módosítania kell a minta-hozzárendelést az alkalmazásban beállított fizetési módoknak megfelelően.

- **Vevőadatok bekérése** – ha ez a paraméter be van kapcsolva, a pénzügyi szolgáltatás kérései a vevőadatokat, például a neveket és a címeket tartalmazzák abban az esetben, ha a vevőt hozzáadják egy tranzakcióhoz.
- **Áfakulcsok megfeleltetése** – **az áfakódok százalékértékének megfeleltetése a pénzügyi szolgáltatásnak elküldött kérések TaxG** (adócsoport) attribútumának értékeihez. Az alapértelmezett hozzárendelés:

    ```
    A: 19.00; B: 7.00; C: 10.70; D: 5.50; E: 0.00
    ```

    Minden pár első összetevője egy áfacsoportot képvisel, amelyet az EFR pénzügyi regisztrációs szolgáltatás támogat. A második összetevő a megfelelő áfakulcsot képviseli. Az EFR által Németország számára támogatott áfacsoportokkal kapcsolatos további tudnivalókat lásd az [EFR hivatkozásban](https://public.efsta.net/efr/).

- **Ajándékutalványok** és -betétek adócsoportja – **a pénzügyi szolgáltatásnak küldött kérések TaxG** attribútumának értéke az ajándékutalványokkal vagy letétekkel kapcsolatos műveletek alapján. Az alapértelmezett hozzárendelés:

    ```
    G
    ```

- **Áfamentes** áfacsoport – **a pénzügyi szolgáltatásnak küldött kérések TaxG** attribútumának értéke, az adófizetési kötelezettségek alól mentesülő műveletek alapján. Az alapértelmezett hozzárendelés:

    ```
    F
    ```

> [!NOTE]
> Az alapértelmezett adatleképezés adóbeállítása felelős az EFR szolgáltatás rendszerében és adócsoportjaiban megadott adóbeállítások egyeztetéséért. Az áfacsoportok csak akkor nyomtathatók a nyugtákra **, ha a Kódnyomtatás** **mező be van állítva az Áfakódok** lapon.

#### <a name="fiscal-connector-settings"></a>Pénzügyi csatlakoztató beállításai

A pénzügyi integrációs minta részeként biztosított pénzügyi csatlakoztató konfigurációja a következő beállításokat tartalmazza:

- **Végpont címe** – a pénzügyi regisztrációs szolgáltatás URL-címe.
- **Időtúllépés** – az az idő ezredmásodpercben, ahányszor a pénzügyi csatlakoztató választ vár a pénzügyi regisztrációs szolgáltatástól.
- **Pénzügyi regisztrációs értesítések megjelenítése** – ez a jelző határozza meg, hogy a pénzügyi regisztrációs szolgáltatás által visszaadott értesítéseket meg kell-e mutatni a kezelőnek.

### <a name="configure-channel-components"></a>Csatornaösszetevők konfigurálása

> [!NOTE]
> - A Pénzügyi nyilvántartási szolgáltatás integrációs minta Németország számára elérhető a Commerce SDK szoftverfejlesztői készletében a 10.0.29-es verziónak megfelelő verzióban. A Commerce rendszer 10.0.28-as vagy korábbi verziójában a Retail SDK előző verzióját kell használnia az LCS egy fejlesztői VIRTUÁLIS gépére. A további tudnivalókat [lásd a Németországhoz (legacy) vonatkozó pénzügyi integrációs minta telepítési irányelveinél](emea-deu-fi-sample-sdk.md).
> - A környezetben telepített kereskedelmi mintákat nem frissíti automatikusan a rendszer, amikor a Commerce rendszer összetevőire szolgáltatás- vagy minőségi frissítéseket alkalmaz. A szükséges mintákat manuálisan kell frissíteni.

#### <a name="set-up-the-development-environment"></a>A fejlesztői környezet beállítása

A minta tesztelésére és kiterjesztésére fejlesztői környezet beállításához kövesse az alábbi lépéseket.

1. Le kell tölteni vagy le kell [Dynamics 365 Commerce tölteni a megoldástárházat](https://github.com/microsoft/Dynamics365Commerce.Solutions). Válassza ki a kiadási ág megfelelő verzióját az SDK-nak vagy az alkalmazásverziónak megfelelően. A további tudnivalókat lásd [a Commerce SDK-minta- és hivatkozáscsomagok letöltése aHub és NuGet](../dev-itpro/retail-sdk/sdk-github.md) a.
1. Nyissa meg az EFR-megoldást **a Dynamics365Commerce.Solutions\\ FiscalIntegration\\ Efr\\ EFR.sln** fájlban, és építse fel.
1. A Commerce futásidejű bővítmények telepítése:

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
        1. A kiterjesztés telepítőjét a parancssorból a következő parancs futtatásával indítja el.

            ```Console
            Contoso.PosFiscalConnectorSample.StoreCommerce.Installer.exe install --verbosity 0
            ```

#### <a name="production-environment"></a>Működési környezet

Hajtsa végre [a pénzügyi integrációs minta felépítési folyamatának beállításához szükséges lépéseket a](fiscal-integration-sample-build-pipeline.md) felhőskálaegység és az önkiszolgáló rendszer telepíthető csomagjainak előállításához és kiadásához a pénzügyi integrációs mintához. Az EFR build-pipeline.yml sablonFÁJL a megoldástárház csővezeték-YAML_Files **·** **\\** található.[Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions)

## <a name="design-of-extensions"></a>Bővítmények tervezése

A pénzügyi nyilvántartási szolgáltatás integrációs mintája Németország [esetében](fiscal-integration-for-retail-channel.md) a pénzügyi integrációs funkciókon alapul, és része a Commerce SDK szoftverfejlesztő készletnek. A minta a **\\ Solutions-tárház FiscalIntegration\\ Efr**[Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/) mappájában található. A [minta](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services) egy pénzügyi dokumentumszolgáltatóból áll, CRT amely a Commerce Hardverállomás kiterjesztése, és egy pénzügyi csatlakoztató. A Commerce SDK használatával kapcsolatos további tudnivalókat lásd A Commerce SDK [mintáinak és hivatkozási csomagjainak letöltése a BuildHub NuGet](../dev-itpro/retail-sdk/retail-sdk-overview.md)[szoftverfejlesztő készletből, valamint a független csomagolású SDK felépítési csővezetékének beállítása](../dev-itpro/build-pipeline.md).

> [!NOTE]
> A Pénzügyi nyilvántartási szolgáltatás integrációs minta Németország számára elérhető a Commerce SDK szoftverfejlesztői készletében a 10.0.29-es verziónak megfelelő verzióban. A Commerce rendszer 10.0.28-as vagy korábbi verziójában a Retail SDK előző verzióját kell használnia az LCS egy fejlesztői VIRTUÁLIS gépére. A további tudnivalókat [lásd a Németországhoz (legacy) vonatkozó pénzügyi integrációs minta telepítési irányelveinél](emea-deu-fi-sample-sdk.md).

### <a name="crt-extension-design"></a>CRT kiterjesztésterv

A kiterjesztés célja, amely egy pénzügyi bizonylat szolgáltatója, a szolgáltatásspecifikus dokumentumok generálása és a pénzügyi nyilvántartási szolgáltatás válaszának kezelnie kell.

#### <a name="request-handler"></a>Kérelemkezelő

Egy kérelemkezelő van a dokumentumszolgáltatóhoz, **a DocumentProviderEFRFiscalDEU dokumentumhoz**. Ezzel a kezelővel lehet pénzügyi bizonylatokat létrehozni a pénzügyi nyilvántartási szolgáltatás számára. Az INamedRequestHandler **felületről öröklődik**. A **HandlerName metódus** felelős a kezelő nevének visszaküldéséért. A kezelő nevének meg kell egyeznie a Commerce Headquarters szolgáltatásban megadott csatlakoztató dokumentumszolgáltató nevével.

Az csatlakoztató a következő kéréseket támogatja:

- **GetFiscalDocumentDocumentProviderRequest** – ez a kérés tartalmazza a létrehozandó dokumentum adatait. Olyan szolgáltatásspecifikus dokumentumot ad vissza, amely regisztrálva kell lennie a pénzügyi regisztrációs szolgáltatásban.
- **GetFiscalTransactionExtendedDataDocumentProviderRequest** – ez a kérés a választ a kiterjesztett adatokkal együtt adja eredményül.

#### <a name="configuration"></a>Konfiguráció

A pénzügyi bizonylat **szolgáltatójának konfigurációs fájlja a megoldások\\ tárházában található FiscalIntegration\\ Efr\\ configurations\\ DocumentProviders\\ DocumentProviderFiscalEFRSampleGermany.xml**[Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/) fájlban található. A fájl célja, hogy lehetővé tegye a pénzügyi bizonylat szolgáltatójának beállításait a Commerce Headquarters alkalmazásból való konfigurálásban. A fájlformátum igazodik a pénzügyi integráció konfigurációjának követelményeihez.

### <a name="hardware-station-extension-design"></a>Hardverállomás bővítményének tervezése

A pénzügyi csatlakoztatóként használt bővítmény célja a pénzügyi regisztrációs szolgáltatással való kommunikáció.

A Hardverállomás kiterjesztése **HardwareStation.Extension.EFRSample**. A HTTP protokollt használja a bővítmények CRT által a pénzügyi regisztrációs szolgáltatásnak generált dokumentumok elküldre. Kezeli a pénzügyi regisztrációs szolgáltatástól kapott válaszokat is.

#### <a name="request-handler"></a>Kérelemkezelő

Az **EFRHandler** kérelemkezelő a pénzügyi regisztrációs szolgáltatás kérésének kezelésére használt belépési pont. Ez a kezelő az **INamedRequestHandler felületről öröklődik**. A **HandlerName metódus** felelős a kezelő nevének visszaküldéséért. A kezelő nevének meg kell egyeznie a Commerce Headquartersban megadott pénzügyi csatlakoztató nevével.

Az csatlakoztató a következő kéréseket támogatja:

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
