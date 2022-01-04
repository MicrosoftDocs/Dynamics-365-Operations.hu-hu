---
title: Adóügyi nyomtató integrációját bemutató minta Lengyelországra vonatkozóan
description: Ez a témakör áttekintést nyújt Lengyelország pénzügyi integrációs mintája ről Microsoft Dynamics 365 Commerce.
author: EvgenyPopovMBS
ms.date: 12/20/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2019-2-1
ms.openlocfilehash: 1b3d7d59494b215ae47f710e200e7e0c57e4ca29
ms.sourcegitcommit: 0d2de52e12fdb9928556d37a4813a67b303695dc
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/21/2021
ms.locfileid: "7944865"
---
# <a name="fiscal-printer-integration-sample-for-poland"></a>Adóügyi nyomtató integrációját bemutató minta Lengyelországra vonatkozóan

[!include[banner](../includes/banner.md)]

Ez a témakör áttekintést nyújt Lengyelország pénzügyi integrációs mintája ről Microsoft Dynamics 365 Commerce.

A Lengyelországra vonatkozó funkciók közé tartozik a pénztár és egy pénzügyi nyomtató közötti Dynamics 365 Commerce mintaintegráció. A minta kiterjeszti a pénzügyi integrációs funkciókat, és támogatja a [POSNET](fiscal-integration-for-retail-channel.md) 2.02 PROTOCOL 2.02 protokollt a [Posnet Polkiszolgáló S.A pénzügyi nyomtatóihoz.](https://www.posnet.com.pl) A minta lehetővé teszi a kommunikációt olyan pénzügyi nyomtatóval, amely COM-porton keresztül csatlakozik egy natív szoftverillesztő segítségével. A rendszer egy szoftveremulátor segítségével megvalósította és tesztelték, amelyet a Posnet FV FV pénzügyi nyomtatóhoz megadott Posnet. A minta forráskód formájában kapható, és része a Retail szoftverfejlesztői csomagnak (SDK).

A Microsoft nem ad ki hardvert, szoftvert vagy dokumentációt a Posnet rendszerből. A pénzügyi nyomtató be- és működésával kapcsolatos tudnivalókat a [Posnet Polrin S.A.A-hez kell forduljon.](https://www.posnet.com.pl)

## <a name="scenarios"></a>Forgatókönyvek

A lengyelországi pénzügyi nyomtató integrációs mintája a következő helyzeteket tartalmazza:

- Értékesítési esetek:

    - Pénzügyi nyugta nyomtatása a készpénz- és az áthozott értékesítések és visszaküldések számára.
    - A pénzügyi nyomtató válaszának rögzítése és tárolása a csatorna-adatbázisban.
    - Adók:

        - Leképezés a pénzügyi nyomtató adókódjaira (részlegek).
        - A megfeleltetett adóadatok átvitele a pénzügyi nyomtatóra.

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
        - Pénzügyi nyugta nyomtatása egy vevői rendelés áthozott sorairól.
        - Pénzügyi nyugta nyomtatása a vevői rendelés felvételi művelete számára.
        - Pénzügyi nyugta nyomtatása visszárurendeléshez.

    - Annak a [vevőnek](emea-pol-customer-information.md) az adatai, amely meg van adva egy pénzügyi nyugtán található értékesítési tranzakcióhoz. Ilyen például a vevő áfaszáma.

- Nap végi kivonatok (pénzügyi X- és pénzügyi Z-jelentések)
- Hibakezelés, például a következő lehetőségek:

    - Próbálja meg újra a pénzügyi regisztrációt, ha egy újrapróbálkozás lehetséges, például ha a pénzügyi nyomtató nincs csatlakoztatva, nem áll készen vagy nem válaszol, a nyomtató ki van nyomtatva, vagy papírelakadás van.
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
- A napi jelentések (pénzügyi X és pénzügyi Z) a beágyazott Műszakjelentés-formátum *használatával vannak* kinyomtatva.
- A vonalkód pénzügyi nyugtákra történő nyomtatása potenciális testreszabásnak tekinthető, mivel ez a funkció nem támogatott a beágyazott formátumokban, és csak a testreszabható Super-format jelentéssel **valósítható** meg.
- A pénzügyi nyomtató nem támogatja a vegyes tranzakciókat. A POS funkcióprofilok esetében a Kombinációs értékesítések és visszaküldések tiltása egy nyugta beállításban igen **értéket** kell **beállítani**.

## <a name="set-up-fiscal-integration-for-poland"></a>Pénzügyi integráció beállítása Lengyelországhoz

A lengyelországi pénzügyi nyomtató-integrációs minta a pénzügyi integrációs funkciókon alapul, és [része a Retail SDK](fiscal-integration-for-retail-channel.md) csomagnak. A minta a FiscalIntegration Posnet tárház src mappájában található (például a **\\\\**[Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/)[release/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/Posnet) mintában). A minta [egy](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices) pénzügyi dokumentumszolgáltatóból áll, amely a Commerce runtime () kiterjesztése, és egy pénzügyi csatlakoztató, amely CRT a Commerce Hardware Station kiterjesztése. További tudnivalók a Retail SDK használatáról: [A Retail SDK architektúrája](../dev-itpro/retail-sdk/retail-sdk-overview.md) és [Készítési folyamat beállítása független csomagkészítő SDK-hoz](../dev-itpro/build-pipeline.md).

> [!WARNING]
> Az új független csomagolási és bővítési modell korlátai miatt jelenleg nem használható ehhez a pénzügyi integrációs [mintához](../dev-itpro/build-pipeline.md). A Retail SDK korábbi verzióját egy fejlesztő virtuális gépen (VM) kell használnia a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásban. A további tudnivalókat lásd a lengyelországi (legacy) pénzügyi nyomtató integrációs minta telepítési [irányelveinél](emea-pol-fpi-sample-sdk.md).
>
> Az új független csomagolási és kiterjesztésmodell támogatása a pénzügyi integrációs mintákkal a későbbi verziókban tervezve lesz.

A pénzügyi integráció beállítási lépéseit a Commerce-csatornák pénzügyi integrációjának beállítása [leírásában leírtak szerint lehet](setting-up-fiscal-integration-for-retail-channel.md) végrehajtani.

1. [Pénzügyi regisztrációs folyamat](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process) beállítása. Ezenkívül jegyezze fel a pénzügyi nyomtató integrációs mintája által meghatározott pénzügyi regisztrációs folyamat [beállításait](#set-up-the-registration-process).
1. [Hibakezelési beállítások](setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings) megadása.
1. [Pénzügyi X-/Z-jelentések beállítása a](setting-up-fiscal-integration-for-retail-channel.md#set-up-fiscal-xz-reports-from-the-pos) POS-ból.
1. [Halasztott pénzügyi regisztráció kézi végrehajtásának](setting-up-fiscal-integration-for-retail-channel.md#enable-manual-execution-of-postponed-fiscal-registration) engedélyezése.
1. [Csatornaösszetevők](#configure-channel-components) konfigurálása

### <a name="set-up-the-registration-process"></a>A regisztrációs folyamat beállítása

A regisztráció engedélyezéséhez kövesse az alábbi lépéseket a Commerce Headquarters beállításához. A további tudnivalókat lásd a Commerce-csatornák pénzügyi [integrációjának](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process) beállítása.

1. A pénzügyi bizonylat szolgáltatójának és a pénzügyi csatlakoztatónak megfelelő konfigurációs fájlok letöltése:

    1. Nyissa meg [Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/) a megoldástárházat.
    1. Az SDK/alkalmazásverziónak (például **[kiadás/9.33) megfelelő kiadási fiókverzió](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33)** kiválasztása.
    1. Nyissa **meg a \> FiscalIntegration \> Posnet rc-t.**
    1. Töltse le a pénzügyi bizonylat szolgáltatójának konfigurációs fájlját a **CommerceRuntime \> DocumentProvider.PosnetSample \> Configuration \> DocumentProviderPosnetSample.xml fájlban (például a**[release/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/blob/release/9.33/src/FiscalIntegration/Posnet/CommerceRuntime/DocumentProvider.PosnetSample/Configuration/DocumentProviderPosnetSample.xml) fájlban).
    1. Töltse le a pénzügyi csatlakoztató konfigurációs fájlját a **HardwareStation \> XmlDeviceSample \> Configuration \> ConnectorPosnetThermalFVEJ.xml fájlból (például a kiadás**[fájlja/9.33).](https://github.com/microsoft/Dynamics365Commerce.Solutions/blob/release/9.33/src/FiscalIntegration/Posnet/HardwareStation/ThermalDeviceSample/Configuration/ConnectorPosnetThermalFVEJ.xml)

    > [!WARNING]
    > Az új független csomagolási és bővítési modell korlátai miatt jelenleg nem használható ehhez a pénzügyi integrációs [mintához](../dev-itpro/build-pipeline.md). A Retail SDK előző verzióját kell használnia egy fejlesztői VM-n az LCS-en. A pénzügyi integrációs minta konfigurációs fájljai a Retail SDK készlet alábbi mappáiban találhatók az LCS egy fejlesztői VIRTUÁLIS eszközében:
    >
    > - **Pénzügyi bizonylat szolgáltatójának konfigurációs fájlja:** RetailSdk \\ SampleExtensions \\ CommerceRuntime \\ Extension.DocumentProvider.PosnetSample \\ Configuration \\ DocumentProviderPosnetSample.xml
    > - **Pénzügyi csatlakoztató konfigurációs fájlja:** RetailSdk \\ SampleExtensions \\ HardwareStation \\ Extension.Posnet.TerjesztésDeviceSample \\ Configuration \\ ConnectorPosnetThermalFVEJ.xml
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

- **Áfakulcsok megfeleltetése – az áfakódok százalékértékének megfeleltetése a pénzügyi nyomtatóspecifikus áfamértékek** között. Az alapértelmezett hozzárendelés:

    ```
    0 : 23.00 ; 1 : 8.00 ; 2 : 5.00 ; 3 : 0.00
    ```

    Minden párban az első összetevő a pénzügyi nyomtatón beállított áfakulcsszámot képviseli. A második összetevő a megfelelő áfakulcsot képviseli. A pénzügyi nyomtató áfakulcs-konfigurációjával kapcsolatos további tudnivalókat lásd a POSNET illesztőprogram-dokumentációjában.

- **Fizetőeszköz-típus hozzárendelés – az üzlethez beállított fizetési módok megfeleltetése a pénzügyi nyomtató által támogatott fizetési** képernyőknek. Az alapértelmezett hozzárendelés:

    ```
    0 : 0 ; 1 : 0 ; 2 : 2 ; 3 : 2 ; 4 : 0 ; 5 : 0 ; 6 : 0 ; 7 : 2 ; 8 : 0
    ```

    Az egyes párok első komponense egy, az üzlethez beállított fizetési módot jelent. A második összetevő a pénzügyi nyomtató által támogatott megfelelő fizetési képernyőt jelöli. A pénzügyi nyomtató által támogatott fizetési képernyőkről a POSNET illesztőprogram dokumentációja tartalmaz további tudnivalókat. A minta-hozzárendelést az alkalmazásban beállított fizetési módoknak megfelelően kell módosítani.

#### <a name="fiscal-connector-settings"></a>Pénzügyi csatlakoztató beállításai

A pénzügyi integrációs minta részeként biztosított pénzügyi csatlakoztató konfigurációja a következő beállításokat tartalmazza:

- **Kapcsolati karakterlánc – karakterlánc, amely az illesztő által támogatott formátumban írja le az eszközzel való** kapcsolat részleteit. A további tudnivalókat lásd a POSNET illesztőprogram dokumentációjában.
- **Dátum- és időszinkronizálás – ez az érték határozza meg, hogy szinkronizálni kell-e a nyomtató dátumát és időpontját a csatlakoztatott** hardverállomással.
- **Eszköz időkorlátja – az az idő ezredmásodpercben, ahányszor a vezető választ vár** az eszközről. A további tudnivalókat lásd a POSNET illesztőprogram dokumentációjában.

### <a name="configure-channel-components"></a>Csatornaösszetevők konfigurálása

> [!WARNING]
> Az új független csomagolási és bővítési modell korlátai miatt jelenleg nem használható ehhez a pénzügyi integrációs [mintához](../dev-itpro/build-pipeline.md). A Retail SDK előző verzióját kell használnia egy fejlesztői VM-n az LCS-en. A további tudnivalókat lásd a lengyelországi (legacy) pénzügyi nyomtató integrációs minta telepítési [irányelveinél](emea-pol-fpi-sample-sdk.md).
>
> Az új független csomagolási és kiterjesztésmodell támogatása a pénzügyi integrációs mintákkal a későbbi verziókban tervezve lesz.

#### <a name="set-up-the-development-environment"></a>A fejlesztői környezet beállítása

A minta tesztelésére és kiterjesztésére fejlesztői környezet beállításához kövesse az alábbi lépéseket.

1. Le kell tölteni vagy le kell tölteni [Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions) a megoldástárházat. Válassza ki a kiadási ág megfelelő verzióját az SDK-nak vagy az alkalmazásverziónak megfelelően. A további tudnivalókat lásd a Retail SDK-minta- és hivatkozáscsomagok letöltése [aHub és NuGet](../dev-itpro/retail-sdk/sdk-github.md) a.
1. Nyissa meg a pénzügyi nyomtató integrációs megoldását **a Dynamics365Commerce.Solutions \\ FiscalIntegration \\\\ Posnet.sln** webhelyen, és építse fel.
1. A CRT következő bővítmények telepítése:

    1. A bővítmény CRT telepítője:

        - **Commerce Scale Unit:** **A Posnet \\\\ ScaleUnit.Posnet.Installer bin debug net461 mappájában keresse meg a \\\\\\** **ScaleUnit.Posnet.Installer** telepítőt.
        - **Helyi a Modern POS terminálon: A CRT** **Posnet \\\\ ModernPOS ModernPOS.Posnet.Installer bin debug net461 mappájában keresse meg a \\\\\\** **ModernPOS.Posnet.Installer** telepítőjét.

    1. A kiterjesztés CRT telepítőjét a következő parancssorból indítja el:

        - **Commerce Scale Unit:**

            ```Console
            ScaleUnit.Posnet.Installer.exe install --verbosity 0
            ```

        - **Helyi CRT a Modern POS terminálon:**

            ```Console
            ModernPOS.Posnet.Installer.exe install --verbosity 0
            ```

1. Hardverállomás-bővítmények telepítése:

    1. A **\\ Posnet HardwareStation \\ HardwareStation.PosnetThermalFVFiscalPrinter.Installer bin debug net461 mappában keresse meg a \\\\\\** **HardwareStation.PosnetThermalFVFiscalPrinter.Installer** telepítőjét.
    1. A kiterjesztés telepítőjét a következő parancssorból indítja el:

        ```Console
        HardwareStation.PosnetThermalFVFiscalPrinter.Installer.exe install --verbosity 0
        ```

#### <a name="production-environment"></a>Működési környezet

Hajtsa végre a pénzügyi integrációs minta felépítési folyamatának beállításához szükséges lépéseket a felhőskálaegység és az önkiszolgáló rendszer telepíthető csomagjainak előállításához és kiadásához a pénzügyi integrációs [mintához](fiscal-integration-sample-build-pipeline.md). A **Posnet build-pipeline.yml sablonFÁJL a** **MEGOLDÁStárház YAML_Files \\**[Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions) csővezetékében található.

## <a name="design-of-extensions"></a>Bővítmények tervezése

A lengyelországi pénzügyi nyomtató-integrációs minta a pénzügyi integrációs funkciókon alapul, és [része a Retail SDK](fiscal-integration-for-retail-channel.md) csomagnak. A minta a FiscalIntegration Posnet tárház src mappájában található (például a **\\\\**[Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/)[release/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/Posnet) mintában). A minta [egy pénzügyi dokumentumszolgáltatóból áll, amely a Commerce Hardverállomás kiterjesztése, és egy pénzügyi](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices)CRT csatlakoztató. További tudnivalók a Retail SDK használatáról: [A Retail SDK architektúrája](../dev-itpro/retail-sdk/retail-sdk-overview.md) és [Készítési folyamat beállítása független csomagkészítő SDK-hoz](../dev-itpro/build-pipeline.md).

> [!WARNING]
> Az új független csomagolási és bővítési modell korlátai miatt jelenleg nem használható ehhez a pénzügyi integrációs [mintához](../dev-itpro/build-pipeline.md). A Retail SDK előző verzióját kell használnia egy fejlesztői VM-n az LCS-en. A további tudnivalókat lásd a lengyelországi (legacy) pénzügyi nyomtató integrációs minta telepítési [irányelveinél](emea-pol-fpi-sample-sdk.md). Az új független csomagolási és kiterjesztésmodell támogatása a pénzügyi integrációs mintákkal a későbbi verziókban tervezve lesz.

### <a name="commerce-runtime-extension-design"></a>Commerce runtime bővítmény tervezése

A kiterjesztés célja, amely egy pénzügyi bizonylatot szolgáltató, az a cél, hogy nyomtatóspecifikus dokumentumokat generáljon, és kezelni tudja a pénzügyi nyomtató válaszait. Ez a kiterjesztés a POSNET 19-3678-as meghatározása által meghatározott JavaScript object Notation (JSON) formátumú nyomtatóspecifikus parancsokat generál.

#### <a name="request-handler"></a>Kérelemkezelő

A **DocumentProviderPosnetProtocol kérelemkezelő a pénzügyi nyomtatón történő dokumentum-generálás** igénylésének belépési pontja.

A kezelő az **INamedRequestHandler felületről** öröklődik. A HandlerName metódus felelős a kezelő nevének **visszaküldéséért**. A kezelő nevének meg kell egyeznie a Commerce Headquarters szolgáltatásban megadott csatlakoztató dokumentumszolgáltató nevével.

Az csatlakoztató a következő kéréseket támogatja:

- **GetFiscalDocumentDocumentProviderRequest – ez a kérés tartalmazza a létrehozandó** dokumentum adatait. Olyan nyomtatóspecifikus bizonylatot ad vissza, amely regisztrálva kell lennie a pénzügyi nyomtatón.
- **GetSupportedRegistrableEventsDocumentProviderRequest – ez a kérés a regisztrált események listáját adja** eredményül. Jelenleg a következő események támogatottak: értékesítés, X-jelentés nyomtatás és Z-jelentés nyomtatás.

#### <a name="configuration"></a>Konfiguráció

A pénzügyi bizonylat szolgáltatójának konfigurációs fájlja a **megoldástárház \\ FiscalIntegration \\ Posnet \\ CommerceRuntime \\ DocumentProvider.PosnetSample \\ Configuration \\ DocumentProviderPosnetSample.xml**[Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/) fájljában található. A fájl célja, hogy lehetővé tegye a pénzügyi bizonylat szolgáltatójának beállításait a Commerce Headquarters alkalmazásból való konfigurálásban. A fájlformátum igazodik a pénzügyi integráció konfigurációjának követelményeihez.

### <a name="hardware-station-extension-design"></a>Hardverállomás bővítményének tervezése

A pénzügyi csatlakoztatóként használt bővítmény célja a pénzügyi nyomtatóval való kommunikáció. Ez a kiterjesztés hívja meg a POSNET illesztőprogram funkcióit, és elküldi a kiterjesztés által a pénzügyi CRT nyomtatón generált parancsokat. Az eszközhibákat is kezeli.

#### <a name="request-handler"></a>Kérelemkezelő

A **FiscalPrinterHandler kérelemkezelő a kérésnek a pénzügyi perifériás eszközzel való kezelés** belépési pontja.

A kezelő az **INamedRequestHandler felületről** öröklődik. A HandlerName metódus felelős a kezelő nevének **visszaküldéséért**. A kezelő nevének meg kell egyeznie a Commerce Headquartersban megadott pénzügyi csatlakoztató nevével.

Az csatlakoztató a következő kéréseket támogatja:

- **SubmitDocumentFiscalDeviceRequest – ez a kérés dokumentumokat küld a nyomtatóknak, és visszaküldi a választ a** pénzügyi nyomtatóról.
- **IsReadyFiscalDeviceRequest – ez a kérés az eszköz állapotának** ellenőrzésére használható.
- **InitializeFiscalDeviceRequest – ez a kérés** a nyomtató inicializálásához használatos.

#### <a name="configuration"></a>Konfiguráció

A pénzügyi csatlakoztató konfigurációs fájlja a **megoldástárház \\ FiscalIntegration \\ Posnet \\ HardwareStation \\ AeviceSample \\ Configuration \\ ConnectorPosnetThermalFVEJ.xml**[Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/) fájljában található. A fájl célja, hogy engedélyezze a pénzügyi csatlakoztató beállításait a Commerce Headquarters alkalmazásból való konfigurálásban. A fájlformátum igazodik a pénzügyi integráció konfigurációjának követelményeihez.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
