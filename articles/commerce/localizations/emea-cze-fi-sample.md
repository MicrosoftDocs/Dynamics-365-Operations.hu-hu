---
title: Pénzügyi nyilvántartási szolgáltatás integrációs mintája a Cseh Köztársaság számára
description: Ez a cikk áttekintést nyújt a Cseh Köztársaság pénzügyi integrációs mintája ről Microsoft Dynamics 365 Commerce.
author: EvgenyPopovMBS
ms.date: 10/04/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-04-01
ms.openlocfilehash: de26b038009d8bf3518c67389c96aade19a0b65b
ms.sourcegitcommit: 2bc6680dc6b12d20532d383a0edb84d180885b62
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/06/2022
ms.locfileid: "9631285"
---
# <a name="fiscal-registration-service-integration-sample-for-the-czech-republic"></a>Pénzügyi nyilvántartási szolgáltatás integrációs mintája a Cseh Köztársaság számára

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

Ez a cikk áttekintést nyújt a Cseh Köztársaság pénzügyi integrációs mintája ről Microsoft Dynamics 365 Commerce.

A Cseh Dynamics 365 Commerce Köztársaság készpénzjegyzékekkel kapcsolatos helyi pénzügyi követelményeinek megfelelően a Cseh Köztársaság funkciói között szerepel a pénztári terminál és egy külső pénzügyi regisztrációs szolgáltatás mintaintegrációja. A minta kiterjeszti a pénzügyi [integrációs funkciókat](fiscal-integration-for-retail-channel.md). [Az EFSTA](https://efsta.org/sicherheitsloesungen/) EFR (Electronic Fiscal Register) [megoldásán](https://efsta.org/) alapul, és HTTPS protokollon keresztül engedélyezi a kommunikációt az EFR szolgáltatással. Az EFR szolgáltatás biztosítja az értékesítések elektronikus regisztrációját (Elektronická evidence treb \[EET\]). Más szóval gondoskodik az értékesítési adatok online átviteléről az adóhatóságok pénzügyi webszolgáltatása számára. Az EFR-szolgáltatásnak a Commerce Hardverállomáson vagy egy hardverállomásról csatlakoztatott külön számítógépen kell lennie. A minta forráskód formájában származik, és része a Commerce szoftverfejlesztői csomagnak (SDK).

A Microsoft nem ad ki hardvert, szoftvert vagy dokumentációt az EFSTA rendszerből. Az EFR-megoldás bejle- és működésről az EFSTA-hoz [forduljon](https://efsta.org/kontakt/).

## <a name="scenarios"></a>Forgatókönyvek

A Cseh Köztársaságra vonatkozó pénzügyi nyilvántartási szolgáltatási integrációs minta a következő helyzeteket tartalmazza.

- Készpénztranzakciók regisztrálása a pénzügyi nyilvántartási szolgáltatásban.

    - Részletes tranzakcióadatok küldése a pénzügyi regisztrációs szolgáltatásnak Ezek az adatok tartalmazzák az értékesítési sorok adatait, valamint az engedményekkel, kifizetésekkel és adókkal kapcsolatos adatokat. Az adóügyi regisztrációs szolgáltatás továbbküldi az adatokat az adóhatóságok webszolgáltatásának, és visszaigazolást kap arról, hogy tartalmazza a tranzakció pénzügyi azonosító kódját.
    - Válasz rögzítése a pénzügyi regisztrációs szolgáltatástól. Ez a válasz olyan pénzügyi adatokat is tartalmaz, mint például a pénzügyi azonosító kód, a tranzakció biztonsági kódja stb.
    - A regisztrált tranzakció pénzügyi adatainak nyomtatása a nyugtára.

- Ajándékutalvány-műveletek és vevői betétek regisztrálása a pénzügyi regisztrációs szolgáltatásban

    - Ajándékutalvány kiadása vagy pénz hozzáadása
    - Vevői számla letétének regisztrálása.
    - Vevői rendelés létrehozása és letét regisztrálása a rendeléshez.
    - Vevői rendelés szerkesztése és a rendelés letétje felülbírálása
    - Vevői rendelés érvénytelenítése és a rendelés letétje visszatérítése

- Hibakezelés, például a következő lehetőségek.

    - Próbálja meg újra a pénzügyi regisztrációt, ha egy újrapróbálkozási művelet lehetséges, például ha a pénzügyi regisztrációs szolgáltatás nem érhető el, nem áll készen vagy nem válaszol.
    - Pénzügyi regisztráció halasztás.
    - Pénzügyi regisztráció kihagyása, vagy a tranzakció megjelölése regisztráltként, és infókódok beírása a hiba okának és a további információknak a rögzítéséhez.
    - Ellenőrizze a pénzügyi regisztrációs szolgáltatás elérhetőségét, mielőtt új értékesítési tranzakciót nyit meg vagy egy értékesítési tranzakciót véglegesítettek.

### <a name="gift-cards"></a>Ajándékutalványok

A pénzügyi nyilvántartási szolgáltatás integrációs mintája az ajándékutalványokkal kapcsolatos következő szabályokat valósítja meg.

- Az értékesítési *tranzakcióban* *az* Ajándékutalvány kiadásához vagy az Ajándékutalványhoz hozzáadás művelethez kapcsolódó értékesítési sorok egy speciális attribútummal vannak megjelölve, amikor a tranzakciót regisztrálják a pénzügyi regisztrációs szolgáltatásban.
- Az ajándékutalványos fizetés rendszeres fizetésnek számít, és speciális attribútummal van megjelölve, amikor a tranzakciót regisztrálják a pénzügyi regisztrációs szolgáltatásban.

### <a name="customer-account-deposits-and-customer-order-deposits"></a>Vevői számlabetétek és vevői rendelési betétek

A pénzügyi nyilvántartási szolgáltatás integrációs mintája a vevői számlára való betétekre és a vevői rendelési betétekre vonatkozó következő szabályokat valósítja meg.

- A pénzügyi nyilvántartási szolgáltatásban egy tranzakciósorként regisztrálják a vevői számla letéthez vagy vevői rendelés letéthez kapcsolódó tranzakciót, és egy speciális attribútummal jelölik meg. Ebben a sorban van megadva a letéti áfacsoport.
- Amikor létrejön egy vevői rendelés, vagyis egy olyan vevői rendelés, amely a vevő által az üzletben szállítható termékeket, valamint a később fel- vagy leszállított termékeket tartalmazza, a pénzügyi nyilvántartási szolgáltatásban regisztrált tranzakció tartalmazza az elvégzett termékek sorait, valamint a rendelési letét sorait.
- A vevői számláról történő fizetés rendszeres kifizetésnek számít, és speciális attribútummal van megjelölve, amikor a tranzakció regisztrálva van a pénzügyi nyilvántartási szolgáltatásban.
- A vevői rendelés felvételi műveletére alkalmazott letéti összeg rendszeres kifizetésnek számít, és speciális attribútummal van megjelölve, amikor a tranzakciót regisztrálják a pénzügyi nyilvántartási szolgáltatásban.

### <a name="offline-registration"></a>Offline regisztráció

Ha a pénzügyi regisztrációs szolgáltatás nem tud tranzakcióadatokat továbbítani az adóhatóságok pénzügyi webszolgáltatásának (például a válasz időtúllépése miatt), és nem kap visszaigazolást a webszolgáltatástól (azaz a tranzakció pénzügyi azonosító kódját), akkor helyi aláírást generál a tranzakcióhoz, és tartalmazza azt, valamint egy speciális hibakódot a válaszban. A pénzügyi regisztrációs szolgáltatás a hálózati kapcsolat visszaállítása után ismét eredeti sorrendben újraküldi a tranzakciókat a háttérben.

### <a name="limitations-of-the-sample"></a>A minta korlátai

A pénzügyi nyilvántartási szolgáltatás csak azokat a helyzeteket támogatja, amelyekben az ár tartalmazza az adót. Emiatt az üzletek **és** **a** vevők esetében az Ár tartalmazza az áfa beállítását Igen beállítást kell beállítani.

## <a name="set-up-commerce-for-the-czech-republic"></a>A Commerce for The Csehország beállítása

Ez a szakasz a Cseh Köztársaságra jellemző és ajánlott Kereskedelmi beállításokat ismerteti. A további tudnivalókat lásd [a Commerce honlapon](../index.md).

A cseh funkciók használatához a következő beállításokat kell megadni.

- A jogi személy elsődleges címében **állítsa az Ország/régió** **mezőt CZE** (Csehország) beállításra.
- Minden Cseh Köztársaságban **található üzlet POS funkcióprofiljában állítsa CZ (Csehország) iso-kód** **mezőt**.

A Cseh Köztársaság esetében a következő beállításokat is meg kell adnia. Ne feledje, hogy a beállítások befejezése után futtatnia kell a megfelelő elosztási feladatokat.

### <a name="set-up-vat-per-czech-republic-requirements"></a>Cseh Köztársaságonkénti áfakövetelmények beállítása


Létre kell hoznia áfakódokat, áfacsoportokat és cikkadócsoportokat. A termékekre és szolgáltatásokra vonatkozó áfaadatokat is be kell állítani. Az áfa funkció beállítási és használatával kapcsolatos további tudnivalókat lásd: [Áfa áttekintése](../../finance/general-ledger/indirect-taxes-overview.md).

### <a name="set-up-stores"></a>Üzletek beállítása

Az Üzletek **lapon** frissítse az üzlet adatait. Konkrétabban, állítsa be a következő paramétereket.

- Adja meg **az Áfacsoport** mezőben azt az áfacsoportot, amely az alapértelmezett vevőnek való értékesítéshez használatos.
- Az Árak tartalmazzák **az áfa beállítást** Igen **beállításra**.
- Állítsa be **a Név** mezőt a vállalat nevére. Ezzel a módosítással garantálható, hogy a vállalat neve megjelenik az értékesítési nyugtán. Másik lehetőségként a vállalat nevét felveheti az értékesítési nyugtaelrendezésbe szabadszövegként.
- Állítsa be **az Adóazonosító szám (TIN) mezőt** a vállalat azonosítószáma mezőre. Ezzel a módosítással garantálható, hogy a vállalat azonosítószáma megjelenik az értékesítési nyugtán. Másik lehetőségként a vállalat azonosítóját hozzáadhatja az értékesítési nyugta elrendezéséhez szabadszövegként.

### <a name="set-up-functionality-profiles"></a>Funkcióprofilok beállítása

POS funkcióprofilok beállítása.

- Állítsa be **a** **nyugtaszámozást** a Nyugtaszámozás gyorsábra az értékesítés, **·** **értékesítési** rendelés és visszáru-bevételezési tranzakciótípusok rekordjainak létrehozásával vagy frissítésével.

### <a name="set-up-registration-numbers"></a>Regisztrációs számok beállítása

1. Ugrás a Szervezetfelügyelet **globális \> címjegyzék regisztrálási \> típusainak \> regisztrálási típusaihoz**. Új regisztrációtípus létrehozása. Adja meg **az Ország/terület** mezőt a **CZE** (Csehország) számára, és csak a szervezetre korlátozza.
2. Ugrás a Szervezetfelügyelet **globális \> címjegyzék regisztrálási \> típusainak regisztrálási \> kategóriáihoz** Új regisztrációs kategória létrehozása. Válassza ki a regisztráció típusát az előző lépésből, és állítsa **a** **Regisztrációs kategóriát Üzleti előzetes azonosítóra**.
3. Nyissa meg a következőt: **Szervezeti adminisztráció \> Szervezetek \> Üzemi egységek**. A Cseh Köztársaságban található valamennyi üzletnél válassza ki az üzlethez kapcsolódó egységet. Bontsa ki **a Cím gyorslistában a További** **beállítások legördülő listát, és válassza a Speciális lehetőséget** **.** 
4. A megnyitott Címek **kezelése** lapon a következő beállításokat kell megadni:

    - A Cím gyors területen állítsa az **Ország/terület** **mezőt CZE beállításra**.**·**
    - Hozzon létre **egy új** rekordot a Regisztrációs azonosító gyors oldalon. Válassza ki a korábban létrehozott regisztrációtípust, és állítsa be a regisztrációs számot.

### <a name="configure-custom-fields-so-that-they-can-be-used-in-receipt-formats-for-sales-receipts"></a>Egyéni mezők konfigurálása az értékesítési nyugták nyugtaformátumában való használhatóra

A POS nyugtaformátumokban használt nyelvi szövegeket és egyéni mezőket beállíthatja. A nyugtabeállítást létrehozó felhasználó alapértelmezett vállalatának ugyanaznak kell lennie, mint ahol a nyelvi szöveg beállítása létre van hozva. Másik lehetőségként ugyanazt az idegen nyelvű szöveget kell létrehozni a felhasználó alapértelmezett vállalatában, valamint annak az üzletnek a jogi személyében, amely számára a beállítást létrehozták.

Adja hozzá **a Nyelv szöveglapon** a következő rekordokat a nyugtaelrendezések egyéni mezőinek címkéihez. Ne feledje, **hogy** **a táblázatban** látható nyelvazonosító, **szövegazonosító** és szöveg értékek példák. A beállításokat az igényeknek megfelelően módosíthatja. A használt **szövegazonosító** értékeknek azonban egyedinek kell lennie, és nem lehet kisebbek a 900001.

Adja hozzá a következő POS-címkéket **a** tábla Nyelvi szövegének **POS** szakaszához:

| Nyelvazonosító | Szövegazonosító | Szöveg                   |
|-------------|---------|------------------------|
| hu       | 900001  | Azonosító: provoz proxy/pokladny |
| hu       | 900002  | BKP                    |
| hu       | 900003  | KKP                    |
| hu       | 900004  | FIK                    |
| hu       | 900005  | Információ                   |
| hu       | 900006  | Sorszám        |

Adja hozzá **a** következő rekordokat az Egyéni mezők lapon a nyugtaelrendezések egyéni mezőihez. A felirat **szövegazonosító értékeinek** meg **·** **kell felelniük a Nyelv szövegoldalán megadott szövegazonosító értékeknek:**

| Név                 | Típus    | Képaláírás-szöveg azonosítója |
|----------------------|---------|-----------------|
| TLT                  | Fogadás | 900001          |
| Sec                  | Fogadás | 900002          |
| JEL                 | Fogadás | 900003          |
| PÉNZÜGYI               | Fogadás | 900004          |
| INFO                 | Fogadás | 900005          |
| FOLYTONOS SZÁM     | Fogadás | 900006          |

> [!NOTE]
> Fontos, hogy a megfelelő egyéni mezőneveket adja meg az előző táblázatban felsoroltak szerint. Helytelen egyéni mezőnév esetén hiányoznak az adatok a nyugtákból.

### <a name="configure-receipt-formats"></a>Nyugtaformátumok konfigurálása

Minden szükséges bevételezési formátumnál módosítsa **a** Nyomtatás viselkedése mező értékét "Mindig **nyomtatás" értékre**.

A Nyugtaformátum-tervezőben adja hozzá a következő egyéni mezőket a megfelelő nyugtaszakaszokhoz. A mezőnevek megfelelnek az előző szakaszban meghatározott nyelvszövegnek.

- **Fejléc:** Adja hozzá a következő mezőket.

    - **Üzlet neve** és **adóazonosító száma**: ezekkel a mezőkkel nyomtatható ki a vállalat neve és azonosítószáma a nyugtákra. Másik lehetőségként a vállalat nevét és azonosító számát is hozzáadhatja az elrendezéshez szabadszövegként.
    - **Üzlet címe**, **dátuma**, **ideje 24 órás**, **nyugtaszám** és pénztárgép **száma**.
    - **Sorszám**: ez a mező azonosítja a készpénztranzakció számát a pénzügyi regisztrációs szolgáltatásban.

- **Sorok:** Adja hozzá a következő mezőket.

    - **Cikknév**
    - **Mennyiség**
    - **Teljes ár adóval**

- **Lábléc:** Adja hozzá a következő mezőket.

    - Fizetési mezők, amelyek segítségével kinyomtathatók az egyes fizetési módok kifizetési összegei. Hozzáadhatja például a **Fizetőeszköz neve** **és** a Fizetőeszköz összege mezőket az elrendezés egy sorában.
    - **Provoz proxy/pokladny** azonosító: ez a mező kinyomtatja az üzleti létesítmény és a pénztárgép azonosítóit.
    - **BKP**: ez a mező kinyomtatja az adófizető biztonsági kódját, amelyet a pénzügyi regisztrációs szolgáltatás rendel hozzá.
    - **FIK**: sikeres online regisztráció esetén az adóhatóság webszolgáltatása által hozzárendelt tranzakció pénzügyi azonosító kódját nyomtatja ki ez a mező.
    - **PKP**: ez a mező kinyomtatja az adófizető aláírási kódját, amelyet a pénzügyi regisztrációs szolgáltatás generál offline regisztráció esetén.
    - **Információ**: ez a mező a pénzügyi regisztrációs szolgáltatás további adatait nyomtatja ki.

A nyugtaformátumok beállításával [és tervezésával kapcsolatos további tudnivalókat lásd a Nyugtaformátumok beállításával és tervezésával kapcsolatban](../receipt-templates-printing.md).

## <a name="set-up-fiscal-integration-for-the-czech-republic"></a>Pénzügyi integráció beállítása a Cseh Köztársaság számára

A Cseh Köztársaság pénzügyi nyilvántartási [szolgáltatásintegrációs](fiscal-integration-for-retail-channel.md) mintája a pénzügyi integrációs funkciókon alapul, és része a Commerce SDK csomagnak. A minta a **\\ Solutions-tárház FiscalIntegration\\ Efr**[Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/) mappájában található. A [minta](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services) egy pénzügyi dokumentumszolgáltatóból áll, amely a Commerce runtime () futási idő kiterjesztése CRT, és egy pénzügyi csatlakoztató, amely a Commerce Hardware Station kiterjesztése. A Commerce SDK használatával kapcsolatos további tudnivalókat lásd A Commerce SDK [mintáinak és hivatkozási csomagjainak letöltése a BuildHub NuGet](../dev-itpro/retail-sdk/sdk-github.md)[szoftverfejlesztő készletből, valamint a független csomagolású SDK felépítési csővezetékének beállítása](../dev-itpro/build-pipeline.md).

> [!NOTE]
> A Cseh Köztársaság pénzügyi nyilvántartási szolgáltatás integrációs mintaverziója a Commerce SDK szoftverfejlesztői készletében a 10.0.29-es verziónak megfelelő verzióban érhető el. A Commerce 10.0.28-as vagy korábbi verziójában a Retail SDK korábbi verzióját kell használnia a Lifecycle Services (LCS) Microsoft Dynamics egy fejlesztői virtuális gépére (VM). A további tudnivalókat [lásd a Cseh Köztársaság pénzügyi integrációs mintája (legacy) telepítési irányelveinél](emea-cze-fi-sample-sdk.md).

A pénzügyi integráció beállítási lépéseit [a Commerce-csatornákhoz való pénzügyi integráció beállítása lépései szerint lehet végrehajtani](setting-up-fiscal-integration-for-retail-channel.md):

1. [Pénzügyi regisztrációs folyamat beállítása](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process). Ezenkívül jegyezze fel a [pénzügyi nyilvántartási folyamatnak az ehhez a pénzügyi regisztrációs szolgáltatásintegrációs mintához specifikus beállításait](#set-up-the-registration-process).
1. [Hibakezelési beállítások megadása](setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).
1. [Halasztott pénzügyi regisztrációk kézi végrehajtásának engedélyezése](setting-up-fiscal-integration-for-retail-channel.md#enable-manual-execution-of-deferred-fiscal-registration).
1. [Csatornaösszetevők konfigurálása](#configure-channel-components)

### <a name="set-up-the-registration-process"></a>A regisztrációs folyamat beállítása

A regisztráció engedélyezéséhez kövesse az alábbi lépéseket a Commerce Headquarters beállításához. A további tudnivalókat lásd [A Commerce-csatornák pénzügyi integrációjának beállítása.](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process)

1. A pénzügyi bizonylat szolgáltatójának és a pénzügyi csatlakoztatónak megfelelő konfigurációs fájlok letöltése:

    1. Nyissa meg [Dynamics 365 Commerce a megoldástárházat](https://github.com/microsoft/Dynamics365Commerce.Solutions/).
    1. Válassza ki a kiadási ág megfelelő verzióját az SDK-nak vagy az alkalmazásverziónak megfelelően.
    1. A **pénzügyiintegration-efr.rc \>\> megnyitása**
    1. Töltse le a pénzügyi bizonylat szolgáltatójának konfigurációs fájlját a **Configurations \> DocumentProviders \> DocumentProviderFiscalEFRSampleIus.xml dokumentumban**.
    1. Töltse le a pénzügyi csatlakoztató konfigurációs fájlját a **Configurations \> Connectors \> ConnectorEFRSample.xml fájlban**.

    > [!NOTE]
    > A Commerce rendszer 10.0.28-as vagy korábbi verziójában a Retail SDK előző verzióját kell használnia az LCS egy fejlesztői VIRTUÁLIS gépére. A pénzügyi integrációs minta konfigurációs fájljai a Retail SDK készlet alábbi mappáiban találhatók az LCS egy fejlesztői VIRTUÁLIS eszközében:
    >
    > - **Pénzügyi bizonylat szolgáltatójának konfigurációs fájlja:** RetailSdk\\ SampleExtensions\\ CommerceRuntime\\ Extensions.DocumentProvider.EFRSample\\ Configuration\\ DocumentProviderFiscalEFRSample Az xml
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

- **Áfakulcsok megfeleltetése** – **az áfakódok százalékértékének megfeleltetése a pénzügyi szolgáltatásnak elküldött kérések TaxG** (adócsoport) attribútumának értékeihez. Az alapértelmezett hozzárendelés:

    ```
    A: 21.00; B: 15.00; C: 10.00; Z: 0.00
    ```

    Minden pár első összetevője egy áfacsoportot képvisel, amelyet az EFR pénzügyi regisztrációs szolgáltatás támogat. A második összetevő a megfelelő áfakulcsot képviseli. Az EFR által a Cseh Köztársaság számára támogatott áfacsoportokkal kapcsolatban lásd [az EFR-hivatkozást](https://public.efsta.net/efr/).

- **Alapértelmezett áfacsoport-hozzárendelés** – minden olyan áfaösszeget, amely nem leképezhető egy előre meghatározott áfacsoportra, az alapértelmezett (alapvető) áfacsoporthoz lesz hozzárendelve. Az alapértelmezett hozzárendelés:

    ```
    A
    ```

- **Letéti áfacsoport hozzárendelése** – a vevő letéti összegei és a vevői rendelés letéti összegei a letéti áfacsoporthoz lesznek rendelve. Az alapértelmezett hozzárendelés:

    ```
    Z
    ```

#### <a name="fiscal-connector-settings"></a>Pénzügyi csatlakoztató beállításai

A pénzügyi integrációs minta részeként biztosított pénzügyi csatlakoztató konfigurációja a következő beállításokat tartalmazza:

- **Végpont címe** – a pénzügyi regisztrációs szolgáltatás URL-címe.
- **Időtúllépés** – az az idő ezredmásodpercben, ahányszor a pénzügyi csatlakoztató választ vár a pénzügyi regisztrációs szolgáltatástól.

### <a name="configure-channel-components"></a>Csatornaösszetevők konfigurálása

> [!NOTE]
> - A Cseh Köztársaság pénzügyi nyilvántartási szolgáltatás integrációs mintaverziója a Commerce SDK szoftverfejlesztői készletében a 10.0.29-es verziónak megfelelő verzióban érhető el. A Commerce rendszer 10.0.28-as vagy korábbi verziójában a Retail SDK előző verzióját kell használnia az LCS egy fejlesztői VIRTUÁLIS gépére. A további tudnivalókat [lásd a Cseh Köztársaság pénzügyi integrációs mintája (legacy) telepítési irányelveinél](emea-cze-fi-sample-sdk.md).
> - A környezetben telepített kereskedelmi mintákat nem frissíti automatikusan a rendszer, amikor a Commerce rendszer összetevőire szolgáltatás- vagy minőségi frissítéseket alkalmaz. A szükséges mintákat manuálisan kell frissíteni.

#### <a name="set-up-the-development-environment"></a>A fejlesztői környezet beállítása

A minta tesztelésére és kiterjesztésére fejlesztői környezet beállításához kövesse az alábbi lépéseket.

1. Le kell tölteni vagy le kell [Dynamics 365 Commerce tölteni a megoldástárházat](https://github.com/microsoft/Dynamics365Commerce.Solutions). Válassza ki a kiadási ág megfelelő verzióját az SDK-nak vagy az alkalmazásverziónak megfelelően. A további tudnivalókat lásd [a Commerce SDK-minta- és hivatkozáscsomagok letöltése aHub és NuGet](../dev-itpro/retail-sdk/sdk-github.md) a.
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
        1. A kiterjesztés telepítőjét a parancssorból a következő parancs futtatásával indítja el.

            ```Console
            Contoso.PosFiscalConnectorSample.StoreCommerce.Installer.exe install --verbosity 0
            ```

#### <a name="production-environment"></a>Működési környezet

Hajtsa végre [a pénzügyi integrációs minta felépítési folyamatának beállításához szükséges lépéseket a](fiscal-integration-sample-build-pipeline.md) felhőskálaegység és az önkiszolgáló rendszer telepíthető csomagjainak előállításához és kiadásához a pénzügyi integrációs mintához. Az EFR build-pipeline.yml sablonFÁJL a megoldástárház csővezeték-YAML_Files **·** **\\** található.[Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions)

## <a name="design-of-extensions"></a>Bővítmények tervezése

A Cseh Köztársaság pénzügyi nyilvántartási [szolgáltatásintegrációs](fiscal-integration-for-retail-channel.md) mintája a pénzügyi integrációs funkciókon alapul, és része a Commerce SDK csomagnak. A minta a **\\ Solutions-tárház FiscalIntegration\\ Efr**[Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/) mappájában található. A [minta](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services) egy pénzügyi dokumentumszolgáltatóból áll, CRT amely a Commerce Hardverállomás kiterjesztése, és egy pénzügyi csatlakoztató. A Commerce SDK használatával kapcsolatos további tudnivalókat lásd A Commerce SDK [mintáinak és hivatkozási csomagjainak letöltése a BuildHub NuGet](../dev-itpro/retail-sdk/retail-sdk-overview.md)[szoftverfejlesztő készletből, valamint a független csomagolású SDK felépítési csővezetékének beállítása](../dev-itpro/build-pipeline.md).

> [!NOTE]
> A Cseh Köztársaság pénzügyi nyilvántartási szolgáltatás integrációs mintaverziója a Commerce SDK szoftverfejlesztői készletében a 10.0.29-es verziónak megfelelő verzióban érhető el. A Commerce rendszer 10.0.28-as vagy korábbi verziójában a Retail SDK előző verzióját kell használnia az LCS egy fejlesztői VIRTUÁLIS gépére. A további tudnivalókat [lásd a Cseh Köztársaság pénzügyi integrációs mintája (legacy) telepítési irányelveinél](emea-cze-fi-sample-sdk.md).

### <a name="commerce-runtime-extension-design"></a>Commerce runtime bővítmény tervezése

A kiterjesztés célja, amely egy pénzügyi bizonylat szolgáltatója, a szolgáltatásspecifikus dokumentumok generálása és a pénzügyi nyilvántartási szolgáltatás válaszának kezelnie kell.

#### <a name="request-handler"></a>Kérelemkezelő

A dokumentumszolgáltatóhoz **egyetlen DocumentProviderEFRFiscalIUSE** kérelemkezelő van, amely a pénzügyi nyilvántartási szolgáltatás pénzügyi bizonylatok előállítására használható.

Ez a kezelő az **INamedRequestHandler felületről öröklődik**. A **HandlerName metódus** felelős a kezelő nevének visszaküldéséért. A kezelő nevének meg kell egyeznie a Commerce Headquarters szolgáltatásban megadott csatlakoztató dokumentumszolgáltató nevével.

Az csatlakoztató a következő kéréseket támogatja.

- **GetFiscalDocumentDocumentProviderRequest** – ez a kérés tartalmazza a létrehozandó dokumentum adatait. Olyan szolgáltatásspecifikus dokumentumot ad vissza, amely regisztrálva kell lennie a pénzügyi regisztrációs szolgáltatásban.
- **GetSupportedRegistrableEventsDocumentProviderRequest** – ez a kérés a regisztrált események listáját adja eredményül. Jelenleg a következő események támogatottak: értékesítés, vevői számlabetétek és vevői rendelési betétek.
- **GetFiscalRegisterResponseToSaveDocumentProviderRequest** – ez a kérés a pénzügyi regisztrációs szolgáltatás válaszát adja eredményül. A válasz egy karakterlánc formájában van szerializálva, hogy készen legyen a mentésre.

#### <a name="configuration"></a>Konfiguráció

A pénzügyi bizonylat **szolgáltatójának konfigurációs fájlja a megoldások\\ tárházában található FiscalIntegration\\ Efr\\ configurations\\ DocumentProviders\\ DocumentProviderFiscalEFRSamplePle.xml**[Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/) fájlban található. A fájl célja, hogy lehetővé tegye a pénzügyi bizonylat szolgáltatójának beállításait a Commerce Headquarters alkalmazásból való konfigurálásban. A fájlformátum igazodik a pénzügyi integráció konfigurációjának követelményeihez.

### <a name="hardware-station-extension-design"></a>Hardverállomás bővítményének tervezése

A pénzügyi csatlakoztatóként használt bővítmény célja a pénzügyi regisztrációs szolgáltatással való kommunikáció. A hardverállomás bővítménye a HTTP CRT protokollal küldheti el a kiterjesztés által a pénzügyi regisztrációs szolgáltatásnak generált dokumentumokat. Kezeli a pénzügyi regisztrációs szolgáltatástól kapott válaszokat is.

#### <a name="request-handler"></a>Kérelemkezelő

Az **EFRHandler** kérelemkezelő a pénzügyi regisztrációs szolgáltatás kérésének kezelésére használt belépési pont.

A kezelő az **INamedRequestHandler felületről öröklődik**. A **HandlerName metódus** felelős a kezelő nevének visszaküldéséért. A kezelő nevének meg kell egyeznie a Commerce Headquartersban megadott pénzügyi csatlakoztató nevével.

Az csatlakoztató a következő kéréseket támogatja.

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
