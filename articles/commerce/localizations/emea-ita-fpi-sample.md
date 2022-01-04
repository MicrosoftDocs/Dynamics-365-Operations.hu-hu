---
title: Adóügyi nyomtató integrációját bemutató minta Olaszországra vonatkozóan
description: Ez a témakör áttekintést nyújt az Olaszországhoz kapcsolódó pénzügyi integrációs mintából Microsoft Dynamics 365 Commerce.
author: EvgenyPopovMBS
ms.date: 12/20/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2018-11-1
ms.openlocfilehash: 592cecff5b6179e7afd1bacb25beda277dfb8fa3
ms.sourcegitcommit: 0d2de52e12fdb9928556d37a4813a67b303695dc
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/21/2021
ms.locfileid: "7944634"
---
# <a name="fiscal-printer-integration-sample-for-italy"></a>Adóügyi nyomtató integrációját bemutató minta Olaszországra vonatkozóan

[!include[banner](../includes/banner.md)]

Ez a témakör áttekintést nyújt az Olaszországhoz kapcsolódó pénzügyi integrációs mintából Microsoft Dynamics 365 Commerce.

Az Olaszországra vonatkozó Commerce-funkciók közé tartozik a pénztár és egy pénzügyi nyomtató közötti mintaintegráció. A minta kiterjeszti a pénzügyi integrációs funkciókat, így működik az [Epson](fiscal-integration-for-retail-channel.md) FP-90II series nyomtatókkal az Epson rendszerből, és lehetővé teszi a kommunikációt egy pénzügyi nyomtatóval webkiszolgálói módban, az [EpsonFPMate](https://www.epson.it/products/sd/pos-printer/epson-fp-90iii-series) webszolgáltatáson keresztül, a Pénzügyi ePOS-nyomtatási API segítségével. A minta csak a Registratore Telematico (RT) módot támogatja. A minta forráskód formájában kapható, és része a Retail szoftverfejlesztői csomagnak (SDK).

A Microsoft nem ad ki hardvert, szoftvert vagy dokumentációt az Epson rendszerből. A pénzügyi nyomtató ki- és lekérése, valamint annak működésvel kapcsolatos tudnivalókért forduljon az [Epson Italia S.p.A-hez](https://www.epson.it).

## <a name="scenarios"></a>Forgatókönyvek

Az olaszországi pénzügyi nyomtató integrációs mintája a következő helyzeteket tartalmazza:

- Értékesítési esetek:

    - Pénzügyi nyugta nyomtatása a készpénz- és az áthozott értékesítések és visszaküldések számára.
    - A pénzügyi nyomtató válaszának rögzítése és tárolása a csatorna-adatbázisban.
    - Adók:

        - Leképezés a pénzügyi nyomtató adókódjaira (részlegek).
        - A megfeleltetett adóadatok átvitele a pénzügyi nyomtatóra.
        - Adók nyomtatása pénzügyi nyugtára.

    - Kifizetések:

        - Leképezés a pénzügyi nyomtató fizetési módjaira.
        - Kifizetések nyomtatása pénzügyi nyugtára.
        - Módosítási adatok nyomtatása.

    - Sorengedmények nyomtatása.
    - Ajándékutalványok:

        - Kiadott/újra felszámított ajándékutalvány-sor kizárása az értékesítés pénzügyi nyugtáiból
        - Ajándékutalványt rendszeres fizetési módként használó fizetés nyomtatása.

    - Pénzügyi nyugták nyomtatása a vevői rendelési műveletekhez:

        - Nem nyomtat pénzügyi nyugtát a rendszer vevői rendelés letétje számára.
        - Pénzügyi nyugta nyomtatása egy vevői rendelés áthozott soraihoz.
        - Pénzügyi nyugta nyomtatása a vevői rendelés felvételi művelete számára.
        - Pénzügyi nyugta nyomtatása visszárurendeléshez.

    - Vonalkód nyomtatása a nyugtaszámhoz egy pénzügyi nyugtán.
    - Annak a [vevőnek](emea-ita-customer-information.md) az adatai, amely meg van adva egy pénzügyi nyugtán található értékesítési tranzakcióhoz. Ilyen például a vevő ügyfélszolgálati kódja. 

- Nap végi kivonatok (pénzügyi X- és pénzügyi Z-jelentések)
- Hibakezelés, például a következő lehetőségek:

    - Próbálja meg újra a pénzügyi regisztrációt, ha egy újrapróbálkozás lehetséges, például ha a pénzügyi nyomtató nincs csatlakoztatva, nem áll készen, vagy nem válaszol, a nyomtató ki van nyomtatva, vagy papírelakadás van.
    - Pénzügyi regisztráció elhalasztása.
    - Pénzügyi regisztráció kihagyása, vagy a tranzakció megjelölése regisztráltként, és infókódok beírása a hiba okának és a további információknak a rögzítéséhez.
    - Ellenőrizze a pénzügyi nyomtató elérhetőségét, mielőtt új értékesítési tranzakciót nyit meg vagy egy értékesítési tranzakciót véglegesítettek.

### <a name="gift-cards"></a>Ajándékutalványok

A pénzügyi nyomtató integrációs mintája az ajándékutalványokkal kapcsolatos következő szabályokat valósítja meg:

- Az ajándékutalvány-kiadáshoz és az ajándékutalvány-műveletekhez hozzáadva kapcsolódó értékesítési *sorok* *kihagyása* a pénzügyi nyugtából
- Ne nyomtass pénzügyi nyugtát, ha az csak ajándékutalvány-sorokból áll.
- A tranzakcióban kiadott vagy újra felszámított ajándékutalványok teljes összegének levonása a pénzügyi nyugta fizetési soraiból.
- A kifizetési sorok számított módosításainak mentése a csatorna-adatbázisban a megfelelő pénzügyi tranzakcióra való hivatkozással.
- Az ajándékutalványos fizetés rendszeres fizetésnek számít.

### <a name="customer-deposits-and-customer-order-deposits"></a>Vevői betétek és vevői rendelési betétek

A pénzügyi nyomtató integrációs mintája a vevői betétekre és a vevői rendelési betétekre vonatkozó következő szabályokat valósítja meg:

- Ne nyomtass pénzügyi nyugtát, ha a tranzakció vevői letét.
- Ne nyomtass pénzügyi nyugtát, ha a tranzakció csak vevői rendelés letétét vagy a vevői rendelés letéti visszatérítését tartalmazza.
- A korábban kifizetett letét összegének nyomtatása egy vevői rendelés felvételi műveletének pénzügyi nyugtára.
- A vevői rendelés letéti összegének levonása a kifizetési sorokból a vevői rendelés létrehozásakor.
- A csatorna-adatbázis fizetési sorai kiszámított korrekcióinak mentése egy vevői rendelés pénzügyi tranzakciójára való hivatkozással.

### <a name="limitations-of-the-sample"></a>A minta korlátai

- A pénzügyi nyomtató csak olyan eseteket támogat, amelyekben az ár tartalmazza az adót. Emiatt az üzletek és a vevők esetében az Ár tartalmazza az áfa beállítását Igen **beállítást** kell **beállítani**.
- A napi jelentések (pénzügyi X és pénzügyi Z) nyomtatása a pénzügyi nyomtató üzenetében beágyazott formátumnak megfelelő formátumban kerül nyomtatásra.
- A pénzügyi nyomtató nem támogatja a vegyes tranzakciókat. A POS funkcióprofilok esetében a Kombinációs értékesítések és visszaküldések tiltása egy nyugta beállításban igen **értéket** kell **beállítani**.
- A minta csak olyan pénzügyi nyomtatóval való integrációt támogat, amely a Registratore Telematikuso (RT) módban dolgozik.

## <a name="set-up-fiscal-integration-for-italy"></a>Pénzügyi integráció beállítása Olaszországhoz

Az olaszországi pénzügyi nyomtató-integrációs minta a pénzügyi integrációs funkciókon alapul, és [része a Retail SDK](fiscal-integration-for-retail-channel.md) csomagnak. A minta a **\\ FiscalIntegration EpsonFP90IISample mappában található a megoldások tárházában (például a minta a \\**[Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/)[release/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/EpsonFP90IIISample) verzióban). A minta [egy](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices) pénzügyi dokumentumszolgáltatóból áll, amely a Commerce runtime () kiterjesztése, és egy pénzügyi csatlakoztató, amely CRT a Commerce Hardware Station kiterjesztése. További tudnivalók a Retail SDK használatáról: [A Retail SDK architektúrája](../dev-itpro/retail-sdk/retail-sdk-overview.md) és [Készítési folyamat beállítása független csomagkészítő SDK-hoz](../dev-itpro/build-pipeline.md).

> [!WARNING]
> Az új független csomagolási és bővítési modell korlátai miatt jelenleg nem használható ehhez a pénzügyi integrációs [mintához](../dev-itpro/build-pipeline.md). A Retail SDK korábbi verzióját egy fejlesztő virtuális gépen (VM) kell használnia a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásban. A további tudnivalókat lásd a pénzügyi nyomtató integrációs mintája olaszországi [(legacy) telepítési](emea-ita-fpi-sample-sdk.md) irányelveinél.
>
> Az új független csomagolási és kiterjesztésmodell támogatása a pénzügyi integrációs mintákkal a későbbi verziókban tervezve lesz.

A pénzügyi integráció beállítási lépéseit a Commerce-csatornák pénzügyi integrációjának beállítása [leírásában leírtak szerint lehet](setting-up-fiscal-integration-for-retail-channel.md) végrehajtani.

1. [Pénzügyi regisztrációs folyamat](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process) beállítása. Ezenkívül jegyezze fel a pénzügyi nyomtató integrációs mintája által meghatározott pénzügyi regisztrációs folyamat [beállításait](#set-up-the-registration-process).
1. [Pénzügyi szövegek beállítása](setting-up-fiscal-integration-for-retail-channel.md#set-up-fiscal-texts-for-discounts) engedményekhez.
1. [Hibakezelési beállítások](setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings) megadása.
1. [Pénzügyi X-/Z-jelentések beállítása a](setting-up-fiscal-integration-for-retail-channel.md#set-up-fiscal-xz-reports-from-the-pos) POS-ból.
1. [Halasztott pénzügyi regisztráció kézi végrehajtásának](setting-up-fiscal-integration-for-retail-channel.md#enable-manual-execution-of-postponed-fiscal-registration) engedélyezése.
1. [A POS-terminálon található vevőadatok kezelésére használható funkciók](emea-ita-customer-information.md#setup) beállítása.
1. [Csatornaösszetevők](#configure-channel-components) konfigurálása

### <a name="set-up-the-registration-process"></a>A regisztrációs folyamat beállítása

A regisztráció engedélyezéséhez kövesse az alábbi lépéseket a Commerce Headquarters beállításához. A további tudnivalókat lásd a Commerce-csatornák pénzügyi [integrációjának](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process) beállítása.

1. A pénzügyi bizonylat szolgáltatójának és a pénzügyi csatlakoztatónak megfelelő konfigurációs fájlok letöltése:

    1. Nyissa meg [Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/) a megoldástárházat.
    1. Az SDK/alkalmazásverziónak (például **[kiadás/9.33) megfelelő kiadási fiókverzió](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33)** kiválasztása.
    1. Nyissa **meg a \> FiscalIntegration \> EpsonFP90IISample gombra vonatkozó rc FiscalIntegration epsonFP90IISample** gombra.
    1. A pénzügyi bizonylat szolgáltatójának konfigurációs fájljának letöltése a **CommerceRuntime \> DocumentProvider.EpsonFP90IISample \> Configuration \> DocumentProviderEpsonFP90IISample.xml fájlból (például a kiadás**[fájlja/9.33).](https://github.com/microsoft/Dynamics365Commerce.Solutions/blob/release/9.33/src/FiscalIntegration/EpsonFP90IIISample/CommerceRuntime/DocumentProvider.EpsonFP90IIISample/Configuration/DocumentProviderEpsonFP90IIISample.xml)
    1. Töltse le a pénzügyi csatlakoztató konfigurációs fájlját a **HardwareStation \> EpsonFP90IIFiscalDeviceSample \> Configuration \> ConnectorEpsonFP90IISample.xml fájlban (például a kiadás**[fájlja/9.33).](https://github.com/microsoft/Dynamics365Commerce.Solutions/blob/release/9.33/src/FiscalIntegration/EpsonFP90IIISample/HardwareStation/EpsonFP90IIIFiscalDeviceSample/Configuration/ConnectorEpsonFP90IIISample.xml)

    > [!WARNING]
    > Az új független csomagolási és bővítési modell korlátai miatt jelenleg nem használható ehhez a pénzügyi integrációs [mintához](../dev-itpro/build-pipeline.md). A Retail SDK előző verzióját kell használnia egy fejlesztői VM-n az LCS-en. A pénzügyi integrációs minta konfigurációs fájljai a Retail SDK készlet alábbi mappáiban találhatók az LCS egy fejlesztői VIRTUÁLIS eszközében:
    >
    > - **Pénzügyi bizonylat szolgáltatójának konfigurációs fájlja:** RetailSdk \\ SampleExtensions \\\\ CommerceRuntime Extension.DocumentProvider.EpsonFP90IISample \\ Configuration \\ DocumentProviderEpsonFP90ISample.xml
    > - **Pénzügyi csatlakoztató konfigurációs fájlja:** RetailSdk \\ SampleExtensions \\ HardwareStation \\ extension.EpsonFP90IIFiscalDeviceSample \\ Configuration \\ ConnectorEpsonFP90IISample.xml
    > 
    > Az új független csomagolási és kiterjesztésmodell támogatása a pénzügyi integrációs mintákkal a későbbi verziókban tervezve lesz.

1. Lépjen a **Retail és Commerce \> Központ beállítása \> Paraméterek \> Commerce megosztott paraméterek** menüpontra. Az Általános lapon állítsa a Pénzügyi integráció engedélyezése lehetőséget **Igen** **·** **beállításra**.
1. Menjen a Retail és Commerce Csatorna beállítása pénzügyi integráció pénzügyi **\>\>\> dokumentumszolgáltatóihoz, és töltse be a korábban letöltött pénzügyidokumentum-szolgáltató konfigurációs** fájlját.
1. Menjen **a Retail és Commerce \> csatorna beállítása Pénzügyi integráció pénzügyi \>\> csatlakoztatóihoz, és töltse be a korábban letöltött pénzügyi csatlakoztató** konfigurációs fájlját.
1. Ugrás **a Retail és Commerce \> csatorna beállítása Fiscal integration Connector funkcionális \>\> profiljaihoz.** Új funkcionális csatlakoztatóprofil létrehozása. Válassza ki a korábban betöltött dokumentumszolgáltatót és csatlakoztatót. Szükség szerint [frissítse az](#default-data-mapping) adatleképezés beállításait.
1. Ugrás a **Retail és Commerce csatorna beállítása Fiscal integration Connector műszaki \>\>\>** profilokhoz. Hozzon létre egy új technikai csatlakoztatóprofilt, és válassza ki a korábban betöltött pénzügyi csatlakoztatóját. Szükség szerint [frissítse a](#fiscal-connector-settings) csatlakoztató beállításait.
6. Ugrás a **Retail és Commerce csatorna beállítása Pénzügyi integráció Pénzügyi \>\>\> csatlakoztatócsoportjához** Hozzon létre egy új pénzügyi csatlakoztatócsoportot a korábban létrehozott csatlakoztató funkcionális profil számára.
7. Ugrás **a Retail és Commerce \> csatorna pénzügyi integrációja pénzügyi \>\> nyilvántartási folyamatainak beállításához** Hozzon létre egy új pénzügyi regisztrációs folyamatot és egy pénzügyi nyilvántartási folyamat lépését, és válassza ki a korábban létrehozott pénzügyi csatlakoztatócsoportot.
8. Ugorjon a következő elemre: **Retail és Commerce \>  Csatorna beállítása \> Pénztárbeállítás \>  Pénztárprofilok \> Funkcióprofilok**. Válasszon ki egy funkcióprofilt, amely ahhoz az üzlethez kapcsolódik, ahol aktiválni kell a regisztrációs folyamatot. A Pénzügyi regisztráció folyamata gyors oldalon válassza ki a korábban létrehozott pénzügyi **regisztrációs** folyamatot.
9. Lépjen a **Kiskereskedelem és kereskedelem \> Csatorna beállítás \> POS beállítás \> POS profilok \> Hardverprofilok** pontra. Válassza ki azt a hardverprofilt, amely ahhoz a hardverállomáshoz van kapcsolva, amelyhez a pénzügyi nyomtató csatlakozik. Válassza ki a korábban létrehozott csatlakoztató-technikai profilt a Pénzügyi perifériák **gyorstára**.
10. Az elosztási ütemezés megnyitása (Retail and Commerce Retail és Commerce IT Distribution ütemezés), majd a **\>\>** **1070-es és** **1090-es** feladat kiválasztása az adatoknak a csatorna-adatbázisba történő átviteléhez.

#### <a name="default-data-mapping"></a>Alapértelmezett adatleképezés

A pénzügyiintegrációs minta részeként megadott pénzügyi bizonylatszolgáltató konfigurációja a következő alapértelmezett adatleképezést tartalmazza:

- **Fizetőeszköz-típusok megfeleltetése – az üzlethez beállított fizetési módok hozzárendelése a pénzügyi nyomtató által támogatott fizetési** típusokhoz. Az alábbi példa bemutatja az alapértelmezett leképezést.

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

    A hozzárendelés attribútumainak magyarázata:

    - **A StorePaymentMethod egy olyan fizetési mód, amely a Retail and Commerce Csatorna fizetési módjai beállításában az** **\>\>\> üzlethez van** beállítva.
    - **A PrinterPaymentType és a PrinterPaymentIndex megfelel az Epson pénzügyi nyomtató dokumentációjában meghatározott fizetési** **típusnak** és indexnek.
    - **A DepositPaymentMethod a vevői rendelés felvételére vonatkozó rész nyomtató fizetéstípusának és indexének megadására** használható.

    Az alábbi táblázat bemutatja, hogy a fizetési módok minta-hozzárendelése hogyan felel meg az üzlet szokásos bemutató adataiban konfigurált fizetési módoknak.

    | Kifizetési mód | Fizetési mód neve |
    |----------------|---------------------|
    | 1              | Készpénz                |
    | 3              | Kártya                |
    | 4              | Vevői számla    |
    | 6              | Pénznem            |
    | 8              | Ajándékutalvány           |

    A minta-hozzárendelést az alkalmazásban beállított fizetési módoknak megfelelően kell módosítani.

- **Vonalkódtípus a nyugtaszámhoz – az a vonalkódtípus, amely a nyugtaszám pénzügyi nyugtán való** megjelenítésekor használatos. Az alapértelmezett megfeleltetés a **CODE128**.
- **Pénzügyi adatok nyomtatása a nyugta fejlécében – ha ez a paraméter be van kapcsolva, a pénzügyi nyugtára az üzletadatok lesznek** nyomtatva. Az adatok közé tartozik az üzlet neve, címe, adóazonosító száma, valamint a pénztáros neve.
- **Pénzügyi nyomtató részlegének hozzárendelése – a pénzügyi nyomtató részlegének megfeleltetése az áfamértékek, az áfamentességi jellegek és a** terméktípusok között. Az alábbi példa bemutatja az alapértelmezett leképezést.

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

    A hozzárendelés attribútumainak magyarázata:

    - **A VATRate** egy támogatott áfakulcs, amely áfakódként van beállítva. A leképezésben két tizedesjegy van, de nincs tizedeselválasztó. Például **2200** 22 százalék, **1000** pedig 10 százalék.
    - **A VATExemptNature csak abban az esetben alkalmazható, ha az áfakulcs** 0 (nulla), akkor is, ha nincs adó. Jelenleg a VATExemptNature csak ajándékutalványok esetén támogatott, és a leképezésben megadott értéknek meg kell egyeznie az XML-konfigurációs **fájl** **VATExemptNatureForGiftCard tulajdonságának** értékével.
    - **A ProductType** típus a termék típusa. A **0 érték** árukat, 1 érték **pedig szolgáltatásokat** jelent.
    - **A DepartmentNumber a nyomtatón konfigurált részleg száma, amely megfelel az előző** három attribútumnak.

    A minta-hozzárendelést az alkalmazásban beállított áfamértékek és a pénzügyi nyomtató megfelelő részlegei szerint kell módosítani.

- **Ajándékutalvány áfamentes jellege – az ajándékutalványok ki- vagy újratöltésekor alkalmazandó** áfamentesség. Az értéknek meg kell egyeznie a pénzügyi nyomtató részleg-hozzárendelésének egy bejegyzésével. Az alapértelmezett megfeleltetés **az** NS.
- **Ingyenes cikkek engedélyezése – ha ez a paraméter be van kapcsolva, akkor engedélyezve van a különleges omagengedmény-helyesbítési típus az olyan cikkeknél,** *amelyekhez* 100 százalékos engedmény van engedélyezve.
- **A visszáru eredetének infókódja – az az infókód, amely a visszáru-tranzakció eredetének rögzítésére szolgál, ha nem áll rendelkezésre** eredeti értékesítési nyugta. Ezt a paramétert és az eredeti értékesítési dátum infókódját és a visszáru eredetének megfeleltetési paramétereit együttesen használva helyes üzenetet generálhat a pénzügyi nyugtán a visszáru-tranzakció eredetéről, ha nem létezik eredeti **értékesítési** **tranzakció**. 

    Ezt az infókódot úgy kell konfigurálni, hogy lehetővé tegye a felhasználó számára az üzletekben lehetséges visszaküldési forrás kiválasztását vagy beíratát. Beállítható például az alkódok listájaként (például Vissza a helyről vagy Vissza **a** **kioszkból).** A **visszatérési eredet megfeleltetési paraméterének használatával az infókód értékét egy pénzügyi nyomtató parancsára** lehet lefordítani.

    A visszaküldési eredet infókódjaként kiválasztott infókódot kötelező infókódként kell beállítani, amely értékesítési tranzakciónként **egyszer** fog elbocsátva. A visszáru-termék infókódjaként kell hozzárendelni a **POS funkcióprofilban, hogy a visszáru-termék művelet futtatásakor indul** **el**.

    Nincs megadva alapértelmezett érték ehhez a megfeleltetéshez. Ki kell választania egy, az alkalmazásban beállított infókódot.

- **Az eredeti értékesítési dátum infókódja – az eredeti értékesítési dátum infókódja, amely a visszáru-tranzakció eredeti értékesítési dátumának rögzítésére használható, amennyiben nem áll** rendelkezésre eredeti értékesítési nyugta. Ezt a paramétert és a visszáru eredetének és visszaküldésének megfeleltetési paramétereit együtt használják a visszáru-tranzakció eredetére vonatkozó helyes üzenet generálása érdekében, amennyiben nem létezik eredeti **értékesítési** **tranzakció**.

    Az infókódot úgy kell konfigurálni, hogy a **Beviteltípus** mező beállítása Dátum **legyen**. Kötelező infókódként kell beállítani, amely értékesítési tranzakciónként egyszer fog elbocsátva. Azt is hozzá kell rendelni a visszatérési eredet paraméterével az infókódhoz kapcsolt infókódként, hogy a két infókód egymást követően **elbocsátható** **legyen**.

    Nincs megadva alapértelmezett érték ehhez a megfeleltetéshez. Ki kell választania egy, az alkalmazásban beállított infókódot.

- **Visszáru-eredet megfeleltetése – a visszáru-tranzakció eredetének nyomtatására használt visszáru-eredet megfeleltetése, amennyiben nem áll** rendelkezésre eredeti értékesítési bevételezés. Ez a paraméter az eredeti értékesítési dátumparaméterek infókódja és a visszáru-eredet infókódja együttesen használva helyes üzenetet generál a pénzügyi nyugtán a visszáru-tranzakció eredetéről, amennyiben nem létezik eredeti **értékesítési** **tranzakció**. Az alábbi példa bemutatja az alapértelmezett leképezést.

    ```JSON
    {"ReturnOrigins": [
        {"ReturnOrigin":"1", "PrinterReturnOrigin":"POS"},
        {"ReturnOrigin":"2", "PrinterReturnOrigin":"ND"}
        ],
        "PrinterReturnOriginWithoutFiscalData":"POS"}
    ```

    A hozzárendelés attribútumainak magyarázata:

    - **A ReturnOrigin** az üzletekben található visszáru egyik lehetséges eredete. Az értéknek meg kell egyeznie a visszatérési **eredet paraméter infókódja** értékének.
    - **A PrinterReturnOrigin az egyik visszatérési eredet, amit a pénzügyi nyomtató** elfogad **·** **(POS, ÉS VAGY** **ND**).
    - **A PrinterReturnOriginWithoutFiscalData az a visszatérési eredet, amely a pénzügyi nyomtató által elfogadható, és amely megfelel egy olyan visszaadási tranzakciónak, amely olyan eredeti értékesítési tranzakcióhoz kapcsolódik, amely nem tartalmaz csatolt pénzügyi adatokat, mivel azt nem egy pénzügyi nyomtatón keresztül** regisztrálták. Ebben az esetben az eredeti értékesítési dátum lesz az eredeti értékesítési tranzakció dátuma.

A következő alapértelmezett adatleképezések elavultak, és csak visszamenőleges kompatibilitás érdekében tartjuk meg őket:

- Áfakódok megfeleltetése
- Letét fizetési típusa

#### <a name="fiscal-connector-settings"></a>Pénzügyi csatlakoztató beállításai

A pénzügyi integrációs minta részeként biztosított pénzügyi csatlakoztató konfigurációja a következő beállításokat tartalmazza:

- **Végpont címe** – a nyomtató URL-címe.
- **Dátum- és időszinkronizálás – ez az érték határozza meg, hogy szinkronizálni kell-e a nyomtató dátumát és időpontját a csatlakoztatott** hardverállomással.

### <a name="configure-channel-components"></a>Csatornaösszetevők konfigurálása

> [!WARNING]
> Az új független csomagolási és bővítési modell korlátai miatt jelenleg nem használható ehhez a pénzügyi integrációs [mintához](../dev-itpro/build-pipeline.md). A Retail SDK előző verzióját kell használnia egy fejlesztői VM-n az LCS-en. A további tudnivalókat lásd a pénzügyi nyomtató integrációs mintája olaszországi [(legacy) telepítési](emea-ita-fpi-sample-sdk.md) irányelveinél.
>
> Az új független csomagolási és kiterjesztésmodell támogatása a pénzügyi integrációs mintákkal a későbbi verziókban tervezve lesz.

#### <a name="set-up-the-development-environment"></a>A fejlesztői környezet beállítása

A minta tesztelésére és kiterjesztésére fejlesztői környezet beállításához kövesse az alábbi lépéseket.

1. Le kell tölteni vagy le kell tölteni [Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions) a megoldástárházat. Válassza ki a kiadási ág megfelelő verzióját az SDK-nak vagy az alkalmazásverziónak megfelelően. A további tudnivalókat lásd a Retail SDK-minta- és hivatkozáscsomagok letöltése [aHub és NuGet](../dev-itpro/retail-sdk/sdk-github.md) a.
1. Nyissa meg a pénzügyi nyomtató integrációs megoldását **a Dynamics365Commerce.Solutions \\ FiscalIntegration \\ EpsonFP90IISample \\ EpsonFP90IISample.sln fájlban, és készítse** el.
1. A CRT következő bővítmények telepítése:

    1. A bővítmény CRT telepítője:

        - **Commerce Scale** Unit: Az **EpsonFP90IISample \\\\ ScaleUnit.EpsonFP90III.Installer bin debug net461 mappában keresse meg a \\\\\\** **ScaleUnit.EpsonFP90II.Installer** telepítőjét.
        - **Helyi CRT a Modern POS terminálon: Az** **EpsonFP90IISample \\\\ ModernPOS ModernPOS.EpsonFP90II.Installer bin debug net461 mappában keresse meg a \\\\\\** **ModernPOS.EpsonFP90II.Installer** telepítőjét.

    1. A kiterjesztés CRT telepítőjét a következő parancssorból indítja el:

        - **Commerce Scale Unit:**

            ```Console
            ScaleUnit.EpsonFP90III.Installer.exe install --verbosity 0
            ```

        - **Helyi CRT a Modern POS terminálon:**

            ```Console
            ModernPOS.EpsonFP90III.Installer.exe install --verbosity 0
            ```

1. Hardverállomás-bővítmények telepítése:

    1. Az **EpsonFP90IISample \\\\ HardwareStation.EpsonFP90II.Installer bin debug net461 mappában keresse meg a \\\\\\** **HardwareStation.EpsonFP90III.Installer** telepítőjét.
    1. A kiterjesztés telepítőjét a következő parancssorból indítja el:

        ```Console
        HardwareStation.EpsonFP90III.Installer.exe install --verbosity 0
        ```

#### <a name="production-environment"></a>Működési környezet

Hajtsa végre a pénzügyi integrációs minta felépítési folyamatának beállításához szükséges lépéseket a felhőskálaegység és az önkiszolgáló rendszer telepíthető csomagjainak előállításához és kiadásához a pénzügyi integrációs [mintához](fiscal-integration-sample-build-pipeline.md). Az **EpsonFP90II build-pipeline.yml sablonFÁJL a megoldástárház csővezeték-YAML_Files** **\\**[Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions) található.

## <a name="design-of-extensions"></a>Bővítmények tervezése

Az olaszországi pénzügyi nyomtató-integrációs minta a pénzügyi integrációs funkciókon alapul, és [része a Retail SDK](fiscal-integration-for-retail-channel.md) csomagnak. A minta a **\\ FiscalIntegration EpsonFP90IISample mappában található a megoldások tárházában (például a minta a \\**[Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/)[release/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/EpsonFP90IIISample) verzióban). A minta [egy pénzügyi dokumentumszolgáltatóból áll, amely a Commerce Hardverállomás kiterjesztése, és egy pénzügyi](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices)CRT csatlakoztató. További tudnivalók a Retail SDK használatáról: [A Retail SDK architektúrája](../dev-itpro/retail-sdk/retail-sdk-overview.md) és [Készítési folyamat beállítása független csomagkészítő SDK-hoz](../dev-itpro/build-pipeline.md).

> [!WARNING]
> Az új független csomagolási és bővítési modell korlátai miatt jelenleg nem használható ehhez a pénzügyi integrációs [mintához](../dev-itpro/build-pipeline.md). A Retail SDK előző verzióját kell használnia egy fejlesztői VM-n az LCS-en. A további tudnivalókat lásd a pénzügyi nyomtató integrációs mintája olaszországi [(legacy) telepítési](emea-ita-fpi-sample-sdk.md) irányelveinél. Az új független csomagolási és kiterjesztésmodell támogatása a pénzügyi integrációs mintákkal a későbbi verziókban tervezve lesz.

### <a name="commerce-runtime-extension-design"></a>Commerce runtime bővítmény tervezése

A kiterjesztés célja, amely egy pénzügyi bizonylatot szolgáltató, az a cél, hogy nyomtatóspecifikus dokumentumokat generáljon, és kezelni tudja a pénzügyi nyomtató válaszait.

#### <a name="request-handler"></a>Kérelemkezelő

A **DocumentProviderEpsonFP90II kéréskezelő a pénzügyi nyomtatón történő dokumentum-generálás igénylésének belépési** pontja.

A kezelő az **INamedRequestHandler felületről** öröklődik. A HandlerName metódus felelős a kezelő nevének **visszaküldéséért**. A kezelő nevének meg kell egyeznie a Commerce Headquarters szolgáltatásban megadott csatlakoztató dokumentumszolgáltató nevével.

Az csatlakoztató a következő kéréseket támogatja:

- **GetFiscalDocumentDocumentProviderRequest – ez a kérés tartalmazza a létrehozandó** dokumentum adatait. Olyan nyomtatóspecifikus bizonylatot ad vissza, amely regisztrálva kell lennie a pénzügyi nyomtatón.
- **GetSupportedRegistrableEventsDocumentProviderRequest – ez a kérés a regisztrált események listáját adja** eredményül. Jelenleg a következő események támogatottak: értékesítés, X-jelentés nyomtatás és Z-jelentés nyomtatás.

#### <a name="configuration"></a>Konfiguráció

A pénzügyi bizonylat szolgáltatójának konfigurációs fájlja a **megoldástárház \\ FiscalIntegration \\ EpsonFP90IISample \\ CommerceRuntime \\ DocumentProvider.EpsonFP90IISample \\ Configuration \\ DocumentProviderEpsonFP90IISample.xml**[Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/) fájljában található. A fájl célja, hogy lehetővé tegye a dokumentumszolgáltató Commerce Headquarters rendszerből származó konfigurálásának beállításait. A fájlformátum igazodik a pénzügyi integráció konfigurációjának követelményeihez.

### <a name="hardware-station-extension-design"></a>Hardverállomás bővítményének tervezése

A pénzügyi csatlakoztatóként használt bővítmény célja a pénzügyi nyomtatóval való kommunikáció. Ez a kiterjesztés a HTTP protokollal küldheti el a kiterjesztés által CRT a pénzügyi nyomtatón generált dokumentumokat. A pénzügyi nyomtatóról kapott válaszokat is kezeli.

#### <a name="request-handler"></a>Kérelemkezelő

Az **EpsonFP90IISample kérelemkezelő a pénzügyi perifériás eszközre vonatkozó kezelési** kérés belépési pontja.

A kezelő az **INamedRequestHandler felületről** öröklődik. A HandlerName metódus felelős a kezelő nevének **visszaküldéséért**. A kezelő nevének meg kell egyeznie a Commerce Headquartersban megadott pénzügyi csatlakoztató nevével.

Az csatlakoztató a következő kéréseket támogatja:

- **SubmitDocumentFiscalDeviceRequest – ez a kérés dokumentumokat küld a nyomtatóknak, és visszaküldi a választ a** pénzügyi nyomtatóról.
- **IsReadyFiscalDeviceRequest – ez a kérés az eszköz állapotának** ellenőrzésére használható.
- **InitializeFiscalDeviceRequest – ez a kérés** a nyomtató inicializálásához használatos.

#### <a name="configuration"></a>Konfiguráció

A pénzügyi csatlakoztató konfigurációs fájlja a **megoldástárház \\ FiscalIntegration \\ EpsonFP90IISample \\ HardwareStation \\ EpsonFP90IIFiscalDeviceSample \\ Configuration \\ ConnectorEpsonFP90IISample.xml**[Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/) fájljában található. A fájl célja, hogy lehetővé tegye a csatlakoztató Commerce Headquarters alkalmazásból származó konfigurálásának beállításait. A fájlformátum igazodik a pénzügyi integráció konfigurációjának követelményeihez.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
