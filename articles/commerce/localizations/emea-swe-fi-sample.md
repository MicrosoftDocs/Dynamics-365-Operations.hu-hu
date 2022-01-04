---
title: Ellenőrzőegység integrációs mintája Svédország esetén
description: Ez a témakör áttekintést nyújt Svédország pénzügyi integrációs mintája ről Microsoft Dynamics 365 Commerce.
author: EvgenyPopovMBS
ms.date: 12/20/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2019-10-08
ms.openlocfilehash: 32c2cf31d82d17d3391536e7a9f1722e1462c336
ms.sourcegitcommit: 0d2de52e12fdb9928556d37a4813a67b303695dc
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/21/2021
ms.locfileid: "7944766"
---
# <a name="control-unit-integration-sample-for-sweden"></a>Ellenőrzőegység integrációs mintája Svédország esetén

[!include [banner](../includes/banner.md)]

Ez a témakör áttekintést nyújt Svédország pénzügyi integrációs mintája ről Microsoft Dynamics 365 Commerce.

> [!NOTE]
> Ez a minta pénzügyi integrációs funkció a korábbi, Svédországra vonatkozó ellenőrző egységekkel való [POS-integrációt helyettesíti](retail-sdk-control-unit-sample.md). A korábbi minta nem használja ki a pénzügyi integrációs keretrendszert, és a későbbi frissítések során [elavulttá](./fiscal-integration-for-retail-channel.md) válik. A korábbi minta Dynamics 365 Commerce **10.0.22-es vagy korábbi verziónak megfelelő mintába való áttelepítésével kapcsolatos tudnivalókat lásd: Áttelepítés a korábbi integrációs**[mintából](emea-swe-fi-sample-sdk.md#migrating-from-the-earlier-integration-sample).

A Svédországra vonatkozó Commerce funkció egy mintaintegrációt tartalmaz a pénztár és Svédországspecifikus pénzügyi eszközök, más néven *vezérlőegységek* között. Ez a minta kiterjeszti [a pénzügyi integrációs funkciókat.](fiscal-integration-for-retail-channel.md) A feltételezés az, hogy a vezérlőegység fizikailag kapcsolódik egy olyan hardverállomáshoz, amelyhez a POS párosítva van. Ez a minta például a [Retail HTT AB CleanCash Type A vezérlőegységének alkalmazásprogramozási felületét (API)](https://www.retailinnovation.se/produkter) használja. A CleanCash API 1.1.4-es verziója használatos.

A minta forráskód formájában kapható, és része a Retail szoftverfejlesztői csomagnak (SDK).

A Microsoft nem ad ki hardvert, szoftvert vagy dokumentációt a Retail Retail HTT AB rendszerből. Az ellenőrző egység le- és működésről a [Retail Retail HTT AB elérhetőségét és elérhetőségét tudni](https://www.retailinnovation.se/) lehet.

## <a name="scenarios"></a>Forgatókönyvek

A Svédországra vonatkozó vezérlőegység-integrációs minta a következő lehetőségeket tartalmazza:

- A rendszer automatikusan regisztrálja az értékesítési, a visszaadott és a bevételezési példányokat egy olyan vezérlőegységben, amely a PÉNZTÁRhoz csatlakoztatott hardverállomáshoz kapcsolódik.
- A regisztrált tranzakció vezérlőkódját és gyártási számát a rendszer az ellenőrző egységből rögzíti, és a tranzakcióba menti. Ezt az adatot pénzügyi válasznak is *nevezik*. A pénzügyi válasz megtekinthető az Üzlet **tranzakciós** lapján.
- Az ellenőrző kód egyéni mezői és az ellenőrző egység gyártási száma hozzáadható egy bevételezési elrendezéshez. Ily módon kinyomtathatja egy tranzakció pénzügyi válaszát egy nyugtára.
- A tranzakció pénzügyi válasza megjelenik az **Elektronikus napló (Svédország)** csatornajelentésen.
- Számos hibakezelési beállítás áll rendelkezésre. Íme néhány példa:

    - Próbálja meg újra a pénzügyi regisztrációt, ha újrapróbálkozás lehetséges. A pénzügyi regisztrációt újrapróbálhatja, ha például a vezérlőegység nincs csatlakoztatva, nem áll készen vagy nem válaszol.
    - Pénzügyi regisztráció elhalasztása.
    - Pénzügyi regisztráció kihagyása, vagy a tranzakció megjelölése regisztráltként, és infókódok beírása a hiba okának és a további információknak a rögzítéséhez.
    - Ellenőrizze az ellenőrző egység rendelkezésre állását, mielőtt új értékesítési tranzakciót nyit meg vagy egy értékesítési tranzakciót véglegesítettek.

### <a name="limitations-of-the-sample"></a>A minta korlátai

A Svédországra vonatkozó vezérlőegység-integrációs minta jelenleg nem támogatja a vevői rendelési helyzeteket.

## <a name="setting-up-the-integration-with-control-units"></a>A vezérlőegységekkel való integráció beállítása

A Svédországra vonatkozó beállításokkal kapcsolatos további tudnivalókat lásd [a Commerce for Sweden beállításával](./emea-swe-cash-registers.md#setting-up-commerce-for-sweden) kapcsolatban.

### <a name="configuring-swedenspecific-receipts"></a>Svédország-specifikus bevételezések konfigurálása

#### <a name="configure-custom-fields-so-that-they-can-be-used-in-receipt-formats-for-sales-receipts"></a>Egyéni mezők konfigurálása az értékesítési nyugták nyugtaformátumában való használhatóra

A POS nyugtaformátumokban használt nyelvi szövegeket és egyéni mezőket beállíthatja. A nyugtabeállítást létrehozó felhasználó alapértelmezett vállalatának ugyanaznak kell lennie, mint ahol a nyelvi szöveg beállítása létre van hozva. Másik lehetőségként ugyanazt az idegen nyelvű szöveget kell létrehozni a felhasználó alapértelmezett vállalatában, valamint annak az üzletnek a jogi személyében, amely számára a beállítást létrehozták.

Adja hozzá a Nyelv szöveglapon a következő rekordokat a nyugtaelrendezések **egyéni mezőinek** címkéihez. Ne feledje, hogy a táblázatban látható nyelvazonosító, szövegazonosító és szöveges értékek **csak** **·** **példák**. A beállításokat az igényeknek megfelelően módosíthatja. A használt szövegazonosító értékeknek azonban egyedinek kell lennie, és nem lehet kisebbek, mint **900001**.

Adja hozzá a következő POS-címkéket **a** Nyelv **szövegoldalának POS** szakaszában.

| Nyelvazonosító | Szövegazonosító | Szöveg                  |
|-------------|---------|-----------------------|
| hu-USA       | 900001  | Jegyzék ellenőrző kódja |
| hu-USA       | 900002  | Eszköz regisztrálása       |

Adja hozzá a következő rekordokat az Egyéni mezők **lapon** a nyugtaelrendezések egyéni mezőihez. A felirat szövegazonosító értékeinek meg kell felelniük a Nyelv szövegoldalán megadott **szövegazonosító** **·** **értékeknek**.

| Név                         | Típus    | Képaláírás-szöveg azonosítója |
|------------------------------|---------|-----------------|
| SE_FISCALREGISTERCONTROLCODE | Fogadás | 900001          |
| SE_FISCALREGISTERID          | Fogadás | 900002          |

> [!NOTE]
> Fontos, hogy a megfelelő egyéni mezőneveket adja meg a fenti táblázatban felsoroltak szerint. Helytelen egyéni mezőnév esetén hiányoznak az adatok a nyugtákból.

#### <a name="configure-receipt-formats"></a>Nyugtaformátumok konfigurálása

Minden kötelező bevételezési formátumnál módosítsa a Nyomtatás viselkedése mező **értékét** "Mindig **nyomtatás"** értékre.

A Nyugtaformátum-tervezőben adja hozzá a következő egyéni mezőket a **Lábléc** szakaszhoz. A mezőnevek megfelelnek a témakör előző részében meghatározott nyelvi szövegeknek.

- **Jegyzék** vezérlőkódja – ez a mező nyomtatja ki az ellenőrző kódot.
- **Regisztráló** eszköz – ez a mező az ellenőrzési egység gyártási számát nyomtatja ki.

A nyugtaformátumok használatával kapcsolatos további tudnivalókat lásd a Nyugtasablonokban [és a](../receipt-templates-printing.md) nyomtatásban.

### <a name="set-up-fiscal-integration-for-sweden"></a>Pénzügyi integráció beállítása Svédországhoz

A Svédországra vonatkozó vezérlőegység-integrációs minta a pénzügyi integrációs funkciókon alapul, és [a](fiscal-integration-for-retail-channel.md) Retail SDK része. A minta a Solutions-tárház (például a **\\\\**[Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/)[release/9.33)](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/CleanCash) src FiscalIntegration CleanCash mappájában található. A minta [egy](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices) pénzügyi dokumentumszolgáltatóból áll, amely a Commerce runtime () kiterjesztése, és egy pénzügyi csatlakoztató, amely CRT a Commerce Hardware Station kiterjesztése. További tudnivalók a Retail SDK használatáról: [A Retail SDK architektúrája](../dev-itpro/retail-sdk/retail-sdk-overview.md) és [Készítési folyamat beállítása független csomagkészítő SDK-hoz](../dev-itpro/build-pipeline.md).

> [!WARNING]
> Az új független csomagolási és bővítési modell korlátai miatt jelenleg nem használható ehhez a pénzügyi integrációs [mintához](../dev-itpro/build-pipeline.md). A Retail SDK korábbi verzióját egy fejlesztő virtuális gépen (VM) kell használnia a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásban. A további tudnivalókat lásd az ellenőrzési egység integrációs mintavételével kapcsolatos, [Svédországra vonatkozó telepítési irányelvekben (legacy).](emea-swe-fi-sample-sdk.md)
>
> Az új független csomagolási és kiterjesztésmodell támogatása a pénzügyi integrációs mintákkal a későbbi verziókban tervezve lesz.

A pénzügyi integráció beállítási lépéseit a Commerce-csatornák pénzügyi integrációjának beállítása [leírásában leírtak szerint lehet](setting-up-fiscal-integration-for-retail-channel.md) végrehajtani.

1. [Pénzügyi regisztrációs folyamat](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process) beállítása. Ezenkívül jegyezze fel a pénzügyi nyilvántartási folyamatnak az ehhez az ellenőrzőegység-integrációs mintához [specifikus](#set-up-the-registration-process) beállításait.
1. [Hibakezelési beállítások](setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings) megadása.
1. [Halasztott pénzügyi regisztráció kézi végrehajtásának](setting-up-fiscal-integration-for-retail-channel.md#enable-manual-execution-of-postponed-fiscal-registration) engedélyezése.
1. [Csatornaösszetevők](#configure-channel-components) konfigurálása

### <a name="set-up-the-registration-process"></a>A regisztrációs folyamat beállítása

A regisztráció engedélyezéséhez kövesse az alábbi lépéseket a Commerce Headquarters beállításához. A további tudnivalókat lásd a Commerce-csatornák pénzügyi [integrációjának](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process) beállítása.

1. A pénzügyi bizonylat szolgáltatójának és a pénzügyi csatlakoztatónak megfelelő konfigurációs fájlok letöltése:

    1. Nyissa meg [Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/) a megoldástárházat.
    1. Az SDK/alkalmazásverziónak (például **[kiadás/9.33) megfelelő kiadási fiókverzió](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33)** kiválasztása.
    1. A **következő src \> FiscalIntegration \> CleanCash** megnyitása:
    1. Töltse le a pénzügyi bizonylat szolgáltatójának konfigurációs fájlját a **CommerceRuntime \> DocumentProvider.CleanCashSample \> Configuration \> DocumentProviderFiscalCleanCashSample.xml fájlból (például a kiadás** fájlja/ [9.33).](https://github.com/microsoft/Dynamics365Commerce.Solutions/blob/release/9.33/src/FiscalIntegration/CleanCash/CommerceRuntime/DocumentProvider.CleanCashSample/Configuration/DocumentProviderFiscalCleanCashSample.xml)
    1. Töltse le a pénzügyi csatlakoztató konfigurációs fájlját a **HardwareStation \> Connector.CleanCashSample \> Configuration \> ConnectorCleanCashSample.xml fájlból (például a kiadás**[fájlja/9.33).](https://github.com/microsoft/Dynamics365Commerce.Solutions/blob/release/9.33/src/FiscalIntegration/CleanCash/HardwareStation/Connector.CleanCashSample/Configuration/ConnectorCleanCashSample.xml)

    > [!WARNING]
    > Az új független csomagolási és bővítési modell korlátai miatt jelenleg nem használható ehhez a pénzügyi integrációs [mintához](../dev-itpro/build-pipeline.md). A Retail SDK előző verzióját kell használnia egy fejlesztői VM-n az LCS-en. A pénzügyi integrációs minta konfigurációs fájljai a Retail SDK készlet alábbi mappáiban találhatók az LCS egy fejlesztői VIRTUÁLIS eszközében:
    >
    > - **Pénzügyi bizonylat szolgáltatójának konfigurációs fájlja:** RetailSdk \\ SampleExtensions \\ CommerceRuntime \\ Extensions.DocumentProvider.CleanCashSample \\ Configuration \\ DocumentProviderFiscalCleanCashSample.xml
    > - **Pénzügyi csatlakoztató konfigurációs fájlja:** RetailSdk \\ SampleExtensions \\ HardwareStation \\ extension.CleanCashSample \\ Configuration \\ ConnectorCleanCashSample.xml
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

- **Áfakód-hozzárendelés – ez a hozzárendelés beállítja az eszközspecifikus áfakódokat a megfelelő** áfakódhoz. Az áfakódok leképezésének a következő formátumúnak kell lennie:

    ```
    1 : code1 ; 2 : code2
    ```

    Itt találja a formátum magyarázatát:

    - *Az 1* és *a 2* eszközspecifikus áfakód.
    - Pontosvessző (;) elválasztóként használható.
    - *az 1. és a 2. kód a Commerce Headquarters szolgáltatásban* *konfigurált* áfakódok. A minta-hozzárendelést az alkalmazásban beállított adókódok szerint kell módosítani.

    Az ellenőrző egységek legfeljebb négy különböző áfakódot támogatnak. Ezért az áfakódok leképezése a következő módon lehet beállítva:

    ```
    1 : code1 ; 2 : code2 ; 3 : code3 ; 4 : code4
    ```

    > [!NOTE]
    > Több áfakód is megfeleltetható ugyanannak az eszközspecifikus áfakódnak.

#### <a name="fiscal-connector-settings"></a>Pénzügyi csatlakoztató beállításai

A pénzügyi integrációs minta részeként biztosított pénzügyi csatlakoztató konfigurációja a következő beállításokat tartalmazza:

- **Kapcsolati karakterlánc** – a vezérlőegység kapcsolati beállításai.
- **Időtúllépés** – az az idő ezredmásodpercben, ahányszor a vezető az ellenőrző egység válaszát várja.

### <a name="configure-channel-components"></a>Csatornaösszetevők konfigurálása

> [!WARNING]
> Az új független csomagolási és bővítési modell korlátai miatt jelenleg nem használható ehhez a pénzügyi integrációs [mintához](../dev-itpro/build-pipeline.md). A Retail SDK előző verzióját kell használnia egy fejlesztői VM-n az LCS-en. A további tudnivalókat lásd az ellenőrzési egység integrációs mintavételével kapcsolatos, [Svédországra vonatkozó telepítési irányelvekben (legacy).](emea-swe-fi-sample-sdk.md)
>
> Az új független csomagolási és kiterjesztésmodell támogatása a pénzügyi integrációs mintákkal a későbbi verziókban tervezve lesz.

#### <a name="set-up-the-development-environment"></a>A fejlesztői környezet beállítása

A minta tesztelésére és kiterjesztésére fejlesztői környezet beállításához kövesse az alábbi lépéseket.

1. Le kell tölteni vagy le kell tölteni [Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions) a megoldástárházat. Válassza ki a kiadási ág megfelelő verzióját az SDK-nak vagy az alkalmazásverziónak megfelelően. A további tudnivalókat lásd a Retail SDK-minta- és hivatkozáscsomagok letöltése [aHub és NuGet](../dev-itpro/retail-sdk/sdk-github.md) a.
1. Nyissa meg az ellenőrzési egység integrációs megoldását **a Dynamics365Commerce.Solutions \\ FiscalIntegration \\ CleanCash \\ CleanCash.sln fájlban, és építse** fel.
1. A CRT következő bővítmények telepítése:

    1. A bővítmény CRT telepítője:

        - **Commerce Scale Unit:** A **CleanCash \\\\ ScaleUnit.CleanCash.Installer bin debug net461 mappában keresse meg a \\\\\\** **ScaleUnit.CleanCash.Installer** telepítőt.
        - **Helyi CRT a Modern POS terminálon: A** **CleanCash \\\\ ModernPOS ModernPOS.CleanCash.Installer bin debug net461 mappában keresse meg a \\\\\\** **ModernPOS.CleanCash.Installer** telepítőjét.

    2. A kiterjesztés CRT telepítőjét a következő parancssorból indítja el:

        - **Commerce Scale Unit:**

            ```Console
            ScaleUnit.CleanCash.Installer.exe install --verbosity 0
            ```

        - **Helyi CRT a Modern POS terminálon:**

            ```Console
            ModernPOS.CleanCash.Installer.exe install --verbosity 0
            ```

1. Hardverállomás-bővítmények telepítése:

    1. A **CleanCash \\ HardwareStation \\ HardwareStation.CleanCash.Installer bin hibakeresési net461 mappában keresse meg \\ a \\\\** **HardwareStation.CleanCash.Installer** telepítőt.
    1. A kiterjesztés telepítőjét a következő parancssorból indítja el:

        ```Console
        HardwareStation.CleanCash.Installer.exe install --verbosity 0
        ```

#### <a name="production-environment"></a>Működési környezet

Hajtsa végre a pénzügyi integrációs minta felépítési folyamatának beállításához szükséges lépéseket a felhőskálaegység és az önkiszolgáló rendszer telepíthető csomagjainak előállításához és kiadásához a pénzügyi integrációs [mintához](fiscal-integration-sample-build-pipeline.md). A CleanCash build-pipeline.yml sablon FILEML sablon a megoldástárház **YAML_Files** **\\**[Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions) csővezeték-mappájában található.

## <a name="design-of-the-extensions"></a>A bővítmények tervezése

A Svédországra vonatkozó vezérlőegység-integrációs minta a pénzügyi integrációs funkciókon alapul, és [a](fiscal-integration-for-retail-channel.md) Retail SDK része. A minta a Solutions-tárház (például a **\\\\**[Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/)[release/9.33)](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/CleanCash) src FiscalIntegration CleanCash mappájában található. A minta [egy pénzügyi dokumentumszolgáltatóból áll, amely a Commerce Hardverállomás kiterjesztése, és egy pénzügyi](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices)CRT csatlakoztató. További tudnivalók a Retail SDK használatáról: [A Retail SDK architektúrája](../dev-itpro/retail-sdk/retail-sdk-overview.md) és [Készítési folyamat beállítása független csomagkészítő SDK-hoz](../dev-itpro/build-pipeline.md).

> [!WARNING]
> Az új független csomagolási és bővítési modell korlátai miatt jelenleg nem használható ehhez a pénzügyi integrációs [mintához](../dev-itpro/build-pipeline.md). A Retail SDK előző verzióját kell használnia egy fejlesztői VM-n az LCS-en. A további tudnivalókat lásd az ellenőrzési egység integrációs mintavételével kapcsolatos, [Svédországra vonatkozó telepítési irányelvekben (legacy).](emea-swe-fi-sample-sdk.md) Az új független csomagolási és kiterjesztésmodell támogatása a pénzügyi integrációs mintákkal a későbbi verziókban tervezve lesz.

### <a name="crt-extension-design"></a>CRT kiterjesztésterv

A kiterjesztés célja, amely egy pénzügyi bizonylat szolgáltatója, a szolgáltatásspecifikus dokumentumok generálása és az ellenőrző egység válaszának kezelnie.

#### <a name="request-handler"></a>Kérelemkezelő

A dokumentumszolgáltatóhoz egyetlen **DocumentProviderCleanCash** kérelemkezelő van. Ezzel a kezelővel lehet pénzügyi bizonylatokat létrehozni az ellenőrzési egységhez.

Ez a kezelő az **INamedRequestHandler felületről** öröklődik. A HandlerName metódus felelős a kezelő nevének **visszaküldéséért**. A kezelő nevének meg kell egyeznie a Commerce Headquarters szolgáltatásban megadott csatlakoztató dokumentumszolgáltató nevével.

Az csatlakoztató a következő kéréseket támogatja:

- **GetFiscalDocumentDocumentProviderRequest – ez a kérés tartalmazza a létrehozandó** dokumentum adatait. Olyan szolgáltatásspecifikus dokumentumot ad vissza, amely regisztrálva kell lennie az ellenőrzési egységben.
- **GetSupportedRegistrableEventsDocumentProviderRequest – ez a kérés a regisztrált események listáját adja** eredményül. Jelenleg az értékesítési és a könyvvizsgálati események támogatottak.

#### <a name="configuration"></a>Konfiguráció

A pénzügyi bizonylat szolgáltatójának konfigurációs fájlja a következő helyen található: **src \\ FiscalIntegration \\ CleanCash \\ CommerceRuntime \\ DocumentProvider.CleanCashSample \\ Configuration \\ DocumentProviderFiscalCleanCashSample.xml, a megoldások**[Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/) tárházában. A fájl célja, hogy lehetővé tegye a dokumentumszolgáltató Commerce Headquarters rendszerből származó konfigurálásának beállításait. A fájlformátum igazodik a pénzügyi integráció konfigurációjának követelményeihez.

### <a name="hardware-station-extension-design"></a>Hardverállomás bővítményének tervezése

A kiterjesztés célja, amely pénzügyi csatlakoztató, az a cél, hogy kommunikáljon az ellenőrző egységgel. A HTTP protokollal küldheti el a kiterjesztés által az ellenőrzési egységnek CRT generált dokumentumokat. Kezeli az ellenőrzési egységtől kapott válaszokat is.

#### <a name="request-handler"></a>Kérelemkezelő

A **CleanCashHandler kérelemkezelő a vezérlőegységhez történő kérések** kezelésének belépési pontja.

A kezelő az **INamedRequestHandler felületről** öröklődik. A HandlerName metódus felelős a kezelő nevének **visszaküldéséért**. A kezelő nevének meg kell egyeznie a Commerce Headquartersban megadott pénzügyi csatlakoztató nevével.

Az csatlakoztató a következő kéréseket támogatja:

- **SubmitDocumentFiscalDeviceRequest – ez a kérés dokumentumokat küld az ellenőrzési egységnek, és** választ ad vissza.
- **IsReadyFiscalDeviceRequest – ez a kérés az ellenőrzési egység** állapotellenőrzésére használható.
- **InitializeFiscalDeviceRequest – ez a kérés a** vezérlőegység inicializálására használatos.

#### <a name="configuration"></a>Konfiguráció

A pénzügyi csatlakoztató konfigurációs fájlja a **megoldástárház \\ FiscalIntegration \\ CleanCash \\ HardwareStation \\ Connector.CleanCashSample \\ Configuration \\ ConnectorCleanCashSample.xml**[Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/) fájljában található. A fájl célja, hogy engedélyezze a Commerce Headquarters alkalmazásból konfigurálható pénzügyi csatlakoztató beállításait. A fájlformátum igazodik a pénzügyi integráció konfigurációjának követelményeihez.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
