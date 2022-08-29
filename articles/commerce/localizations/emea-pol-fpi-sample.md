---
title: Adóügyi nyomtató integrációját bemutató minta Lengyelországra vonatkozóan
description: Ez a cikk áttekintést nyújt Lengyelország pénzügyi integrációs mintája ről Microsoft Dynamics 365 Commerce.
author: EvgenyPopovMBS
ms.date: 08/18/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-02-01.
ms.openlocfilehash: 52710252d78d34c444de2d40e16423868b12b5c1
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/23/2022
ms.locfileid: "9337221"
---
# <a name="fiscal-printer-integration-sample-for-poland"></a>Adóügyi nyomtató integrációját bemutató minta Lengyelországra vonatkozóan

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

Ez a cikk áttekintést nyújt Lengyelország pénzügyi integrációs mintája ről Microsoft Dynamics 365 Commerce.

A Dynamics 365 Commerce Lengyelországra vonatkozó funkciók közé tartozik a pénztár és egy pénzügyi nyomtató közötti mintaintegráció. A minta kiterjeszti [a](fiscal-integration-for-retail-channel.md) pénzügyi integrációs funkciókat, és támogatja a POSNET 2.02 PROTOCOL 2.02 protokollt [a Posnet Polkiszolgáló S.A pénzügyi nyomtatóihoz.](https://www.posnet.com.pl) A minta lehetővé teszi a kommunikációt olyan pénzügyi nyomtatóval, amely COM-porton keresztül csatlakozik egy natív szoftverillesztő segítségével. A rendszer egy szoftveremulátor segítségével megvalósította és tesztelték, amelyet a Posnet FV FV pénzügyi nyomtatóhoz megadott Posnet. A minta forráskód formájában származik, és része a Commerce szoftverfejlesztői csomagnak (SDK).

A Microsoft nem ad ki hardvert, szoftvert vagy dokumentációt a Posnet rendszerből. A pénzügyi nyomtató be- és működésával [kapcsolatos tudnivalókat a Posnet Polrin S.A.A-hez kell forduljon.](https://www.posnet.com.pl)

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

    - Annak a vevőnek [az adatai](emea-pol-customer-information.md), amely meg van adva egy pénzügyi nyugtán található értékesítési tranzakcióhoz. Ilyen például a vevő áfaszáma.

- Nap végi kivonatok (pénzügyi X- és pénzügyi Z-jelentések)
- Hibakezelés, például a következő lehetőségek:

    - Próbálja meg újra a pénzügyi regisztrációt, ha egy újrapróbálkozás lehetséges, például ha a pénzügyi nyomtató nincs csatlakoztatva, nem áll készen vagy nem válaszol, a nyomtató ki van nyomtatva, vagy papírelakadás van.
    - Pénzügyi regisztráció elhalasztása.
    - Pénzügyi regisztráció kihagyása, vagy a tranzakció megjelölése regisztráltként, és infókódok beírása a hiba okának és a további információknak a rögzítéséhez.
    - Ellenőrizze a pénzügyi nyomtató elérhetőségét, mielőtt új értékesítési tranzakciót nyit meg vagy egy értékesítési tranzakciót véglegesítettek.

### <a name="gift-cards"></a>Ajándékutalványok

A pénzügyi nyomtató integrációs mintája az ajándékutalványokkal kapcsolatos következő szabályokat valósítja meg:

- Az ajándékutalvány-kiadáshoz *·* *és* az ajándékutalvány-műveletekhez hozzáadva kapcsolódó értékesítési sorok kihagyása a pénzügyi nyugtából
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

- A pénzügyi nyomtató csak olyan eseteket támogat, amelyekben az ár tartalmazza az adót. Emiatt az üzletek **és** **a** vevők esetében az Ár tartalmazza az áfa beállítását Igen beállítást kell beállítani.
- A napi jelentések (pénzügyi X és pénzügyi Z) *a beágyazott Műszakjelentés-formátum használatával vannak kinyomtatva*.
- A vonalkód pénzügyi nyugtákra történő nyomtatása potenciális testreszabásnak tekinthető, mivel ez a funkció nem támogatott a beágyazott formátumokban, **és csak a testreszabható Super-format** jelentéssel valósítható meg.
- A pénzügyi nyomtató nem támogatja a vegyes tranzakciókat. A **POS funkcióprofilok** **esetében** a Kombinációs értékesítések és visszaküldések tiltása egy nyugta beállításban igen értéket kell beállítani.

## <a name="set-up-fiscal-integration-for-poland"></a>Pénzügyi integráció beállítása Lengyelországhoz

A lengyelországi pénzügyi nyomtató-integrációs [minta](fiscal-integration-for-retail-channel.md) a pénzügyi integrációs funkciókon alapul, és része a Commerce SDK szoftverfejlesztő készletnek. A minta a **\\ Solutions-tárház FiscalIntegration\\ Posnet**[Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/) mappájában található. A [minta](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services) egy pénzügyi dokumentumszolgáltatóból áll, amely a Commerce runtime () futási idő kiterjesztése CRT, és egy pénzügyi csatlakoztató, amely a Commerce Hardware Station kiterjesztése. A Commerce SDK használatával kapcsolatos további tudnivalókat lásd A Commerce SDK [mintáinak és hivatkozási csomagjainak letöltése a BuildHub NuGet](../dev-itpro/retail-sdk/sdk-github.md)[szoftverfejlesztő készletből, valamint a független csomagolású SDK felépítési csővezetékének beállítása](../dev-itpro/build-pipeline.md).

> [!NOTE]
> A pénzügyi nyomtató integrációs mintája Lengyelországhoz elérhető a Commerce SDK szoftverfejlesztő készletében a 10.0.29-es verziónak megfelelő verzióban. A Commerce 10.0.28-as vagy korábbi verziójában a Retail SDK korábbi verzióját kell használnia a Lifecycle Services (LCS) Microsoft Dynamics egy fejlesztői virtuális gépére (VM). A további tudnivalókat [lásd a lengyelországi pénzügyi nyomtató integrációs mintája (legacy) telepítési irányelveinél](emea-pol-fpi-sample-sdk.md).

A pénzügyi integráció beállítási lépéseit [a Commerce-csatornák pénzügyi integrációjának beállítása leírtak szerint lehet végrehajtani](setting-up-fiscal-integration-for-retail-channel.md).

1. [Pénzügyi regisztrációs folyamat beállítása](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process). Ezenkívül jegyezze fel a [pénzügyi nyomtató integrációs mintáját jellemző pénzügyi regisztrációs folyamat beállításait](#set-up-the-registration-process).
1. [Hibakezelési beállítások megadása](setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).
1. [Pénzügyi X-/Z-jelentések beállítása a POS-ból](setting-up-fiscal-integration-for-retail-channel.md#set-up-fiscal-xz-reports-from-the-pos).
1. [Halasztott pénzügyi regisztráció kézi végrehajtásának engedélyezése](setting-up-fiscal-integration-for-retail-channel.md#enable-manual-execution-of-postponed-fiscal-registration)
1. [Csatornaösszetevők konfigurálása](#configure-channel-components)

### <a name="set-up-the-registration-process"></a>A regisztrációs folyamat beállítása

A regisztráció engedélyezéséhez kövesse az alábbi lépéseket a Commerce Headquarters beállításához. A további tudnivalókat lásd [A Commerce-csatornák pénzügyi integrációjának beállítása.](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process)

1. A pénzügyi bizonylat szolgáltatójának és a pénzügyi csatlakoztatónak megfelelő konfigurációs fájlok letöltése:

    1. Nyissa meg [Dynamics 365 Commerce a megoldástárházat](https://github.com/microsoft/Dynamics365Commerce.Solutions/).
    1. Válassza ki a kiadási ág megfelelő verzióját az SDK-nak vagy az alkalmazásverziónak megfelelően.
    1. PénzügyiIntegration **posnet \> megnyitása \>**
    1. Töltse le a pénzügyi bizonylat szolgáltatójának konfigurációs fájlját a **CommerceRuntime \> DocumentProvider.PosnetSample \> Configuration \> DocumentProviderPosnetSample.xml webhelyen**.
    1. Töltse le a pénzügyi csatlakoztató konfigurációs fájlját a **HardwareStation \> Egyezettel \> a Configuration ConnectorPosnetThermalFVEJ.xml \> fájlban**.

    > [!NOTE]
    > A Commerce rendszer 10.0.28-as vagy korábbi verziójában a Retail SDK előző verzióját kell használnia az LCS egy fejlesztői VIRTUÁLIS gépére. A pénzügyi integrációs minta konfigurációs fájljai a Retail SDK készlet alábbi mappáiban találhatók az LCS egy fejlesztői VIRTUÁLIS eszközében:
    >
    > - **Pénzügyi bizonylat szolgáltatójának konfigurációs fájlja:** RetailSdk\\ SampleExtensions\\ CommerceRuntime\\ Extension.DocumentProvider.PosnetSample\\ Configuration\\ DocumentProviderPosnetSample.xml
    > - **Pénzügyi csatlakoztató konfigurációs fájlja:** RetailSdk\\ SampleExtensions\\ HardwareStation\\ Extension.Posnet.TerjesztésDeviceSample\\ Configuration\\ ConnectorPosnetThermalFVEJ.xml

1. Lépjen a **Retail és Commerce \> Központ beállítása \> Paraméterek \> Commerce megosztott paraméterek** menüpontra. Az Általános **lapon** állítsa **a** Pénzügyi integráció engedélyezése lehetőséget Igen **beállításra**.
1. Menjen a **Retail és Commerce \> Csatorna beállítása pénzügyi \> integráció \> pénzügyi dokumentumszolgáltatóihoz**, és töltse be a korábban letöltött pénzügyidokumentum-szolgáltató konfigurációs fájlját.
1. Menjen a **Retail és Commerce \> csatorna beállítása \> Pénzügyi integráció \> pénzügyi csatlakoztatóihoz**, és töltse be a korábban letöltött pénzügyi csatlakoztató konfigurációs fájlját.
1. Ugrás a **Retail és Commerce \> csatorna beállítása \> Fiscal integration \> Connector funkcionális profiljaihoz**. Új funkcionális csatlakoztatóprofil létrehozása. Válassza ki a korábban betöltött dokumentumszolgáltatót és csatlakoztatót. Szükség szerint [frissítse az adatleképezés](#default-data-mapping) beállításait.
1. Ugrás a **Retail és Commerce \> csatorna beállítása \> Fiscal integration \> Connector műszaki profilokhoz**. Hozzon létre egy új technikai csatlakoztatóprofilt, és válassza ki a korábban betöltött pénzügyi csatlakoztatóját. Szükség szerint [frissítse a csatlakoztató](#fiscal-connector-settings) beállításait.
6. Ugrás a **Retail és Commerce \> csatorna beállítása Pénzügyi \> integráció \> Pénzügyi csatlakoztatócsoportjához** Hozzon létre egy új pénzügyi csatlakoztatócsoportot a korábban létrehozott csatlakoztató funkcionális profil számára.
7. Ugrás a Kiskereskedelmi és **Commerce csatorna \> beállítása pénzügyi \> integráció \> pénzügyi regisztrációs folyamatainak lépéseihez**. Hozzon létre egy új pénzügyi regisztrációs folyamatot és egy pénzügyi nyilvántartási folyamat lépését, és válassza ki a korábban létrehozott pénzügyi csatlakoztatócsoportot.
8. Ugorjon a következő elemre: **Retail és Commerce \>  Csatorna beállítása \> Pénztárbeállítás \>  Pénztárprofilok \> Funkcióprofilok**. Válasszon ki egy funkcióprofilt, amely ahhoz az üzlethez kapcsolódik, ahol aktiválni kell a regisztrációs folyamatot. A Pénzügyi regisztráció **folyamata** gyors oldalon válassza ki a korábban létrehozott pénzügyi regisztrációs folyamatot.
9. Lépjen a **Kiskereskedelem és kereskedelem \> Csatorna beállítás \> POS beállítás \> POS profilok \> Hardverprofilok** pontra. Válassza ki azt a hardverprofilt, amely ahhoz a hardverállomáshoz van kapcsolva, amelyhez a pénzügyi nyomtató csatlakozik. Válassza ki a **korábban** létrehozott csatlakoztató-technikai profilt a Pénzügyi perifériák gyorstára.
10. Nyissa meg az elosztási ütemezést (**Retail and Commerce \> Retail és Commerce IT \> Distribution schedule**), **majd válassza ki a 1070-es** **és 1090-es** feladatokat az adatoknak a csatorna-adatbázisba történő átviteléhez.

#### <a name="default-data-mapping"></a>Alapértelmezett adatleképezés

A pénzügyiintegrációs minta részeként megadott pénzügyi bizonylatszolgáltató konfigurációja a következő alapértelmezett adatleképezést tartalmazza:

- **Áfakulcsok megfeleltetése** – az áfakódok százalékértékének megfeleltetése a pénzügyi nyomtatóspecifikus áfamértékek között. Az alapértelmezett hozzárendelés:

    ```
    0 : 23.00 ; 1 : 8.00 ; 2 : 5.00 ; 3 : 0.00
    ```

    Minden párban az első összetevő a pénzügyi nyomtatón beállított áfakulcsszámot képviseli. A második összetevő a megfelelő áfakulcsot képviseli. A pénzügyi nyomtató áfakulcs-konfigurációjával kapcsolatos további tudnivalókat lásd a POSNET illesztőprogram-dokumentációjában.

- **Fizetőeszköz-típus hozzárendelés** – az üzlethez beállított fizetési módok megfeleltetése a pénzügyi nyomtató által támogatott fizetési képernyőknek. Az alapértelmezett hozzárendelés:

    ```
    0 : 0 ; 1 : 0 ; 2 : 2 ; 3 : 2 ; 4 : 0 ; 5 : 0 ; 6 : 0 ; 7 : 2 ; 8 : 0
    ```

    Az egyes párok első komponense egy, az üzlethez beállított fizetési módot jelent. A második összetevő a pénzügyi nyomtató által támogatott megfelelő fizetési képernyőt jelöli. A pénzügyi nyomtató által támogatott fizetési képernyőkről a POSNET illesztőprogram dokumentációja tartalmaz további tudnivalókat. A minta-hozzárendelést az alkalmazásban beállított fizetési módoknak megfelelően kell módosítani.

#### <a name="fiscal-connector-settings"></a>Pénzügyi csatlakoztató beállításai

A pénzügyi integrációs minta részeként biztosított pénzügyi csatlakoztató konfigurációja a következő beállításokat tartalmazza:

- **Kapcsolati** karakterlánc – karakterlánc, amely az illesztő által támogatott formátumban írja le az eszközzel való kapcsolat részleteit. A további tudnivalókat lásd a POSNET illesztőprogram dokumentációjában.
- **Dátum- és időszinkronizálás** – ez az érték határozza meg, hogy szinkronizálni kell-e a nyomtató dátumát és időpontját a csatlakoztatott hardverállomással.
- **Eszköz időkorlátja** – az az idő ezredmásodpercben, ahányszor a vezető választ vár az eszközről. A további tudnivalókat lásd a POSNET illesztőprogram dokumentációjában.

### <a name="configure-channel-components"></a>Csatornaösszetevők konfigurálása

> [!NOTE]
> - A pénzügyi nyomtató integrációs mintája Lengyelországhoz elérhető a Commerce SDK szoftverfejlesztő készletében a 10.0.29-es verziónak megfelelő verzióban. A Commerce rendszer 10.0.28-as vagy korábbi verziójában a Retail SDK előző verzióját kell használnia az LCS egy fejlesztői VIRTUÁLIS gépére. A további tudnivalókat [lásd a lengyelországi pénzügyi nyomtató integrációs mintája (legacy) telepítési irányelveinél](emea-pol-fpi-sample-sdk.md).
> - A környezetben telepített kereskedelmi mintákat nem frissíti automatikusan a rendszer, amikor a Commerce rendszer összetevőire szolgáltatás- vagy minőségi frissítéseket alkalmaz. A szükséges mintákat manuálisan kell frissíteni.

#### <a name="set-up-the-development-environment"></a>A fejlesztői környezet beállítása

A minta tesztelésére és kiterjesztésére fejlesztői környezet beállításához kövesse az alábbi lépéseket.

1. Le kell tölteni vagy le kell [Dynamics 365 Commerce tölteni a megoldástárházat](https://github.com/microsoft/Dynamics365Commerce.Solutions). Válassza ki a kiadási ág megfelelő verzióját az SDK-nak vagy az alkalmazásverziónak megfelelően. A további tudnivalókat lásd [a Commerce SDK-minta- és hivatkozáscsomagok letöltése aHub és NuGet](../dev-itpro/retail-sdk/sdk-github.md) a.
1. Nyissa meg a pénzügyi nyomtató integrációs **megoldását a Dynamics365Commerce.Solutions\\ FiscalIntegration\\ Posnet.sln\\** webhelyen, és építse fel.
1. A következő CRT bővítmények telepítése:

    1. A bővítmény telepítője CRT:

        - **Commerce Scale Unit:** **A Posnet\\ ScaleUnit.Posnet.Installer\\\\ bin\\ debug\\ net461** **mappájában keresse meg a ScaleUnit.Posnet.Installer** telepítőt.
        - **Helyi CRT a Modern POS terminálon:** **A Posnet\\ ModernPOS ModernPOS.Posnet.Installer\\\\ bin\\ debug\\ net461** **mappájában keresse meg a ModernPOS.Posnet.Installer** telepítőjét.

    1. A kiterjesztés telepítőjét CRT a következő parancssorból indítja el:

        - **Commerce Scale Unit:**

            ```Console
            ScaleUnit.Posnet.Installer.exe install --verbosity 0
            ```

        - **Helyi CRT a Modern POS terminálon:**

            ```Console
            ModernPOS.Posnet.Installer.exe install --verbosity 0
            ```

1. Hardverállomás-bővítmények telepítése:

    1. A Posnet **HardwareStation\\ HardwareStation.PosnetThermalFVFiscalPrinter.Installer\\ bin\\ debug\\ net461\\** mappában keresse meg a HardwareStation.PosnetThermalFVFiscalPrinter.Installer **telepítőjét.**
    1. A kiterjesztés telepítőjét a következő parancssorból indítja el:

        ```Console
        HardwareStation.PosnetThermalFVFiscalPrinter.Installer.exe install --verbosity 0
        ```

#### <a name="production-environment"></a>Működési környezet

Hajtsa végre [a pénzügyi integrációs minta felépítési folyamatának beállításához szükséges lépéseket a](fiscal-integration-sample-build-pipeline.md) felhőskálaegység és az önkiszolgáló rendszer telepíthető csomagjainak előállításához és kiadásához a pénzügyi integrációs mintához. A Posnet build-pipeline.yml sablonFÁJL a MEGOLDÁStárház **YAML_Files** **\\** csővezetékében található.[Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions)

## <a name="design-of-extensions"></a>Bővítmények tervezése

A lengyelországi pénzügyi nyomtató-integrációs [minta](fiscal-integration-for-retail-channel.md) a pénzügyi integrációs funkciókon alapul, és része a Commerce SDK szoftverfejlesztő készletnek. A minta a **\\ Solutions-tárház FiscalIntegration\\ Posnet**[Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/) mappájában található. A [minta](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services) egy pénzügyi dokumentumszolgáltatóból áll, CRT amely a Commerce Hardverállomás kiterjesztése, és egy pénzügyi csatlakoztató. A Commerce SDK használatával kapcsolatos további tudnivalókat lásd A Commerce SDK [mintáinak és hivatkozási csomagjainak letöltése a BuildHub NuGet](../dev-itpro/retail-sdk/sdk-github.md)[szoftverfejlesztő készletből, valamint a független csomagolású SDK felépítési csővezetékének beállítása](../dev-itpro/build-pipeline.md).

> [!NOTE]
> A pénzügyi nyomtató integrációs mintája Lengyelországhoz elérhető a Commerce SDK szoftverfejlesztő készletében a 10.0.29-es verziónak megfelelő verzióban. A Commerce rendszer 10.0.28-as vagy korábbi verziójában a Retail SDK előző verzióját kell használnia az LCS egy fejlesztői VIRTUÁLIS gépére. A további tudnivalókat [lásd a lengyelországi pénzügyi nyomtató integrációs mintája (legacy) telepítési irányelveinél](emea-pol-fpi-sample-sdk.md).

### <a name="commerce-runtime-extension-design"></a>Commerce runtime bővítmény tervezése

A kiterjesztés célja, amely egy pénzügyi bizonylatot szolgáltató, az a cél, hogy nyomtatóspecifikus dokumentumokat generáljon, és kezelni tudja a pénzügyi nyomtató válaszait. Ez a kiterjesztés a POSNET 19-3678-as meghatározása által meghatározott JavaScript object Notation (JSON) formátumú nyomtatóspecifikus parancsokat generál.

#### <a name="request-handler"></a>Kérelemkezelő

A **DocumentProviderPosnetProtocol** kérelemkezelő a pénzügyi nyomtatón történő dokumentum-generálás igénylésének belépési pontja.

A kezelő az **INamedRequestHandler felületről öröklődik**. A **HandlerName metódus** felelős a kezelő nevének visszaküldéséért. A kezelő nevének meg kell egyeznie a Commerce Headquarters szolgáltatásban megadott csatlakoztató dokumentumszolgáltató nevével.

Az csatlakoztató a következő kéréseket támogatja:

- **GetFiscalDocumentDocumentProviderRequest** – ez a kérés tartalmazza a létrehozandó dokumentum adatait. Olyan nyomtatóspecifikus bizonylatot ad vissza, amely regisztrálva kell lennie a pénzügyi nyomtatón.
- **GetSupportedRegistrableEventsDocumentProviderRequest** – ez a kérés a regisztrált események listáját adja eredményül. Jelenleg a következő események támogatottak: értékesítés, X-jelentés nyomtatás és Z-jelentés nyomtatás.

#### <a name="configuration"></a>Konfiguráció

A pénzügyi bizonylat **szolgáltatójának konfigurációs fájlja a megoldástárház\\ FiscalIntegration\\ Posnet\\ CommerceRuntime\\ DocumentProvider.PosnetSample\\ Configuration\\ DocumentProviderPosnetSample.xml**[Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/) fájljában található. A fájl célja, hogy lehetővé tegye a pénzügyi bizonylat szolgáltatójának beállításait a Commerce Headquarters alkalmazásból való konfigurálásban. A fájlformátum igazodik a pénzügyi integráció konfigurációjának követelményeihez.

### <a name="hardware-station-extension-design"></a>Hardverállomás bővítményének tervezése

A pénzügyi csatlakoztatóként használt bővítmény célja a pénzügyi nyomtatóval való kommunikáció. Ez a kiterjesztés hívja meg a POSNET illesztőprogram funkcióit, és elküldi CRT a kiterjesztés által a pénzügyi nyomtatón generált parancsokat. Az eszközhibákat is kezeli.

#### <a name="request-handler"></a>Kérelemkezelő

A **FiscalPrinterHandler** kérelemkezelő a kérésnek a pénzügyi perifériás eszközzel való kezelés belépési pontja.

A kezelő az **INamedRequestHandler felületről öröklődik**. A **HandlerName metódus** felelős a kezelő nevének visszaküldéséért. A kezelő nevének meg kell egyeznie a Commerce Headquartersban megadott pénzügyi csatlakoztató nevével.

Az csatlakoztató a következő kéréseket támogatja:

- **SubmitDocumentFiscalDeviceRequest** – ez a kérés dokumentumokat küld a nyomtatóknak, és visszaküldi a választ a pénzügyi nyomtatóról.
- **IsReadyFiscalDeviceRequest** – ez a kérés az eszköz állapotának ellenőrzésére használható.
- **InitializeFiscalDeviceRequest** – ez a kérés a nyomtató inicializálásához használatos.

#### <a name="configuration"></a>Konfiguráció

A pénzügyi csatlakoztató **konfigurációs fájlja a megoldástárház\\ FiscalIntegration\\ Posnet HardwareStation\\ AeviceSample\\\\ Configuration\\ ConnectorPosnetThermalFVEJ.xml**[Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/) fájljában található. A fájl célja, hogy engedélyezze a pénzügyi csatlakoztató beállításait a Commerce Headquarters alkalmazásból való konfigurálásban. A fájlformátum igazodik a pénzügyi integráció konfigurációjának követelményeihez.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
