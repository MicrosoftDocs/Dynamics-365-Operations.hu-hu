---
title: Commerce analitika (előnézet)
description: Ez a témakör azt mutatja be, hogyan lehet telepíteni és használni az analitika-funkciókat a rendszerben Microsoft Dynamics 365 Commerce.
author: AamirAllaq
ms.date: 11/23/2021
audience: Application user
ms.reviewer: sericks
ms.search.region: Global
ms.author: aamiral
ms.search.validFrom: 2021-11-12
ms.openlocfilehash: 8cfe2af756315b5be3eb22d99376a96166fffc52
ms.sourcegitcommit: f9fca3d55b47e615e5ef64669dab184e057ec234
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/23/2021
ms.locfileid: "7862773"
---
# <a name="commerce-analytics-preview"></a>Commerce analitika (előnézet)

[!include [banner](includes/banner.md)]

Ez a témakör bemutatja a Commerce Analitikának (Előnézet) a telepítéséhez szükséges funkciókat Microsoft Dynamics 365 Commerce.

## <a name="commerce-analytics-preview-live-demo"></a>Commerce Analytics (Preview) élő bemutató

A Commerce [Analytics (Előnézet) élő bemutatóját is megtekintheti](https://aka.ms/CommerceAnalyticsDemo).

![Commerce Analytics (előnézeti) összegzése](media/CommerceAnalytics_Summary.png)
![Commerce Analytics (előnézeti) fizetések](media/CommerceAnalytics_Payments.png)
![Commerce Analytics (előnézeti) webes tevékenység](media/CommerceAnalytics_WebActivity.png)


## <a name="commerce-analytics-preview-system-architecture"></a>Commerce Analytics (Preview) rendszerarchitektúra

### <a name="key-components"></a>Kulcsösszetevők

A Commerce Analytics (Preview) a következő kulcsösszetevőkből áll:

- Használatra kész interaktív Power BI jelentések
- SQL-nézetek az Azure Synapse Analitikában
- Entitás- és ontológiaadatok az Azure-adatokban
- Nyers adatok az adatokban

![A Commerce Analytics rendszerarchitektúra kulcsösszetevői](media/CommerceAnalyticsArchitecture_v2.png)

### <a name="data-flow"></a>Adatáramlás

#### <a name="step-1-data-generation"></a>1. lépés: Adatok létrehozása

Az adatok vagy tranzakciós adatokból, vagy a következő forrásokból származó viselkedési adatokból származnak:

- A hívásközponti munkatárs a Commerce központi ügyfélen keresztül feldolgoz egy értékesítési rendelést.
- Egy pénztáros a pénztárnál feldolgozza az értékesítési tranzakciókat.
- Az értékesítések egyedi alkalmazásokban, a Headless Commerce (Commerce Scale Unit) használatával jön létre.
- Az e-commerce rendszer egy vásárlója tallózással megkeresi az e-commerce webhelyet.
- Az e-commerce rendszer egy vásárlója rendelést ad fel az e-commerce webhelyre.
- Az adatokat más rendszerek, például a Dynamics 365 Connected Spaces.

#### <a name="step-2-ingestion-and-pre-processing"></a>2. lépés: Áthozat és előfeldolgozás

A tranzakciós adatok közvetlenül (a Commerce HQ ügyfélben közvetlenül rögzített rendelések esetén) vagy a Commerce Scale Unit egységen keresztül (a POS-nál, e-kereskedelemben rögzített rendelések esetén, illetve a fej nélküli Commerce rendszer által használt egyedi ügyfeleken) keresztül érik el a tranzakciós adatokat.

Az "Exportálás az Adatba" funkció használatával a tranzakciós adatokat a rendszer nyers adatként másolja az adatokba. Az adattáblában a nyers adatok a Táblák mappában tárolódnak.

Az e-commerce webes tevékenység adatai közvetlenül az adatkapcsolatba küldik. A más rendszerek által előállított adatokat, például a rendszereket közvetlenül az adatrendszernek küldi a Dynamics 365 Connected Spaces rendszer.

#### <a name="step-3-transformation-and-aggregation"></a>3. lépés: Átalakítás és összesítés

Miután a nyers adatok az adatok tárolójában vannak, a Commerce Elemzési szolgáltatás beolvassa, átalakítja, összesíti, majd logikai entitások formájában visszaírja az adatokba (az Entitások mappában) és az összesített mérőszámokat (az Ontologies mappában).

#### <a name="step-4-querying"></a>4. lépés: Lekérdezés

Azure Synapse Az analitikával adatokat lehet lekérdezni a tranzakciós SQL-kapcsolaton (T-SQL) keresztül. Ez a felület SQL-nézeteket tartalmaz. Az SQL nézetek lehetővé teszik az adatok összevont lekérdezését az adatkapcsolatban, akár közvetlenül, egy T-SQL ügyfélen keresztül (ad-hoc elemzéshez), vagy megjelenítő eszköz például Power BI.

#### <a name="step-5-modeling-and-serving"></a>5. lépés: Modellezés és kiszolgáló

Az Analitika által lekérdezett adatok Azure Synapse a Power BI "szemantikus modellre" haladnak. Az adatok típusától függően lehet, hogy időnként importálják a memóriába, vagy közvetlenül lekérdezik Power BI őket futásidőben.

Végül az adatok vizuális jelennek meg, így a felhasználók megtekinthetik és Power BI kommunikálhatnak vele.

## <a name="commerce-analytics-preview-functional-overview"></a>Commerce Analitikának (Előnézet) - működési áttekintés

### <a name="summary"></a>Összegzés

A Commerce Analytics sablonalkalmazás a következő fő jelentésoldalakat tartalmazza:

1. [Legfelső szintű szűrők](#TopLevelFilters)
2. [Termékek](#ProductsPage)
3. [Vevők](#CustomersPage)
4. [Csatornák](#ChannelsPage)
5. [Értékesítés](#SalesPage)
6. [Margók](#MarginsPage)
7. [Visszáruk](#ReturnsPage)
8. [Engedmények](#DiscountsPage)
9. [Kifizetések](#PaymentsPage)
10. [Vevők](#CustomersPage)
11. [Összehasonlítás](#ComparisonPage)
12. [Internetes tevékenység](#WebActivityPage)
13. [Webes tevékenység - Legfelső szintű szűrő](#WebActivityTopLevelFilters)

####  <a name="top-level-filters"></a><a name="TopLevelFilters"></a> Legfelső szintű szűrők

- Dátumbeállítások

    - Év
    - Negyedév
    - Hónap
    - Hét
    - Nap

- Csatornabeállítások

    - Jogi személy
    - Csatorna típusa
    - Vevőtípus
    - Értékesítés típusa
    - Csatorna
    - Szervezeti hierarchia

- Termékbeállítások

    - Kategóriahierarchia
    - Kategória

####  <a name="products"></a><a name="ProductsPage"></a> Termékek

- Értékesítés
- Margó
- Visszáruk

####  <a name="customers"></a><a name="CustomersPage"></a> Ügyfelek

- Értékesítés
- Margó
- Visszáruk

#### <a name="channels"></a><a name="ChannelsPage"></a> Csatornák

- Értékesítés
- Margó
- Visszáruk

### <a name="sales"></a>Értékesítési<a name="SalesPage"></a>

- Szállítási hely szerint
- Csatorna/üzlet/terminál szerint
- Alkalmazott szerint
- Dátum szerint
- Óra szerint
- Termékkategória szerint

### <a name="margins"></a><a name="MarginsPage"></a> Margók

- Szállítási hely szerint
- Melléktermék
- Dátum szerint

### <a name="returns"></a><a name="ReturnsPage"></a> Visszatér

- Visszáru összeg szerint

    - Üzlet szerint
    - Melléktermék
    - Dátum szerint

- Visszáru tranzakciónként

    - Üzlet szerint
    - Melléktermék
    - Dátum szerint

### <a name="discounts"></a><a name="DiscountsPage"></a> Kedvezmények

- Üzlet szerint
- Melléktermék
- Dátum szerint
- Felbontás

    - Jogi személy
    - Üzlet
    - Engedmény típusa
    - Engedmény neve
    - Termék

### <a name="payments"></a><a name="PaymentsPage"></a> Kifizetések

- Csatornák/terminálok szerint
- Fizetési mód/típus szerint
- Dátum szerint
- Felbontás

    - Jogi személy
    - Csatorna típusa
    - Üzlet
    - Terminál
    - Kifizetési mód

### <a name="customers"></a><a name="CustomersPage"></a> Ügyfelek

- Élettartam értéke (LÉRE)

    Az LVEL számítása a vevő által az összes értékesítési csatornában (például a POS, az e-commerce és a hívásközpontban) töltött Dynamics 365 Commerce teljes összeg alapján történik.

- Recency

    A recency számítása a vevő és a szervezet között történt utolsó tranzakciós tevékenység óta eltszámított napok száma alapján történik. A recency jelenleg nem veszi figyelembe a nem tranzakciós tevékenység jelzéseit, például az e-commerce böngészési tevékenységet.

- Gyakoriság

    A gyakoriságot a vevőnek a szervezettel való tranzakciós ügylete alapján számítja ki a program. A gyakoriság jelenleg nem veszi figyelembe a nem tranzakciós tevékenység jelzéseit, például az e-commerce böngészési tevékenységet.

- Kapcsolat hossza

    A kapcsolat hosszának számítása a vevőrekord rendszerben való létrehozása óta eltszámlott napok száma alapján történik.

- Tranzakciók száma

### <a name="comparison"></a><a name="ComparisonPage"></a> Összehasonlítás

- Termék-összehasonlítás időszak szerint

    - Értékesítési és értékesítési különbözet
    - Árrés és árrés eltérése

- Vevő időszak szerint

    - Értékesítési és értékesítési különbözet
    - Árrés és árrés eltérése

### <a name="web-activity"></a><a name="WebActivityPage"></a> Webes tevékenység

#### <a name="top-level-filters"></a><a name="WebActivityTopLevelFilters"></a> Legfelső szintű szűrők

- Dátumtartomány
- Csatorna típusa
- Csatorna
- Kategóriahierarchia

#### <a name="acquisitions"></a>Beszerzések

- Lapnézetek

    - Országok és régiók szerint
    - Melléktermék
    - Bejelentkezett felhasználó állapota szerint
    - Dátum szerint

- E-commerce rendelések
- Átváltási árfolyam

    - Dátum szerint

- Konverziós tölcsér

    - Lapnézet laptípus szerint (kezdőlap, kategóriaoldal vagy termék részletei oldal)
    - Hozzáadás a kosárhoz
    - Fizetés
    - Beszerzés

#### <a name="sessions"></a>Munkamenetek

A munkamenet annak az időnek a száma, amikor egy felhasználó látogatást tett az e-commerce webhelyen. A munkamenet 30 percnyi inactivity vagy 24 órás aktív használat után minősül zárónek.

- Országok és régiók szerint
- Eredet szerint (külső hivatkozás)
- Bejelentkezett felhasználó állapota szerint
- Munkamenetek száma

    - Dátum szerint
    - Beviteli oldal szerint

- Rendelés munkamenetenként

    - Dátum szerint

- Munkamenet kamatlába

    A munkamenet munkamenet-munkamenet, ahonnan a felhasználó közvetlenül az e-commerce webhelyre való látogatást követően indul el. A további tudnivalókat [lásd: Kamatláb](https://en.wikipedia.org/wiki/Bounce_rate).

- Rákattint munkamenetenként

#### <a name="visitors"></a>Látogatók

Az e-commerce webhely névtelen használatának azonosítása egyedileg történik a felhasználó által használt böngésző és eszköz alapján. A Commerce analitikában nem lehet nyomon követni a különböző böngészőkben és eszközökben lévő névtelen problémákat. Egy névtelen felhasználó, aki ugyanazon az eszközön ugyanazt a böngészőt használja, egyedileg azonosítják több felhasználói munkamenet során, amíg a böngésző gyorsítótárazott adatait meg nem törlik, vagy amíg az időszak (általában 12 hónap) el nem tel, amelyik előbb történik meg.

Ha a bejelentkezve tallózással megkeresi az e-commerce webhelyet, akkor a Commerce analitikával további információkat lehet velük kapcsolatban adni. Ezek az információk azon alapulnak, hogy milyen viszonyban van a szervezet az összes értékesítési Dynamics 365 Commerce csatornában (például a POS, az e-commerce és a hívásközpont) keresztül történt korábbi beszerzések eredményeként. A további információk közé tartozik a recency, a kapcsolat hossza, az élettartam értéke és a gyakorisági adatok.

- Fedezeti árrés
- Átlagos rendelések
- Átlagos értékesítés
- E-commerce rendszerbeli számlálás

    - Dátum szerint
    - Hely szerint

        A Commerce analitikák jelenleg csak ország-/régió szintű adatokat szolgáltatnak az e-commerce rendszernek megfelelő helyadatokat szolgáltatni.

    - Recency szerint

        A recency számítása a vevő és a szervezet között történt utolsó tranzakciós tevékenység óta eltszámított napok száma alapján történik. A recency jelenleg nem veszi figyelembe a nem tranzakciós tevékenység jelzéseit, például az e-commerce böngészési tevékenységet.

    - Kapcsolat hossza szerint

        A kapcsolat hosszának számítása a vevőrekord rendszerben való létrehozása óta eltszámlott napok száma alapján történik.

    - Élettartam értéke (LÉRE)

        Az LVEL számítása a vevő által az összes értékesítési csatornában (például a POS, az e-commerce és a hívásközpontban) töltött Dynamics 365 Commerce teljes összeg alapján történik.

    - Gyakoriság szerint

        A gyakoriságot a vevőnek a szervezettel való tranzakciós ügylete alapján számítja ki a program. A gyakoriság jelenleg nem veszi figyelembe a nem tranzakciós tevékenység jelzéseit, például az e-commerce böngészési tevékenységet.

#### <a name="impressions"></a>Benyomások

A vizuális megjelenítés a termék vizuális megjelenítése az e-kereskedelemben. Például az e-commerce értékesítés az e-commerce webhely kezdőlapjára kerül, és a legjobb eladási listamodulban egy gyermekterméket is **megtekint**. A viselkedés ezt követően ugyanazt az első terméket egy **Kivét listás** modulban nézi meg. Ebben az esetben két termékjelet kelt fel. 

Jelenleg a alábbiak szerint nyomon követik a alábbiakat:

- Listák (például **ajánlott**, legjobb **eladási**, kiválasztó **és** **trend**)
- Kosármodul
- Keresési eredmények tárolója
- Kategóriakeresési eredmény tárolója

Jelenleg a carousel modulban vagy az egyéni vizuális megjelenítésben megjelenített termékek nem számítanak bele a látójelekkel kapcsolatos mérőszámokbe.

A **Jelentések jelentés a következő** mérőszámokat tartalmazza:

- Megjelenítések száma

    - Laptípus és modul szerint

        A laptípus az e-commerce webhely egyes oldalaihoz meghatározott általános laptípus. A modultípus annak az e-commerce vizuális modulnak a típusa, amelyben a termék megjelenik.

        A megjelenítések modul szerint történő megtekintéséhez lehet, hogy le kell ásni a lap és a modul vizuális megjelenítésébe.

    - Melléktermék
    - Bejelentkezett felhasználó állapota szerint
    - Dátum szerint

- Megjelenítések és kattintások száma

    Úgy érzékelnek, hogy egy e-commerce entitás kiválasztja a termék vizuális megjelenítését. Jellemzően ezt követően a viselkedés a termék részletes adatait tartalmazó lapra érkezik meg.

- Megjelenítés átkattintási aránya (CTR)

    A CTR számítása úgy történik, hogy a kattintások száma elosztva a kattintások összesített számmal.

## <a name="commerce-analytics-preview-installation"></a>Commerce Analytics (Előnézet) telepítése

> [!NOTE]
> A Commerce Analytics (Preview) előnézetben látható az Egyesült Államokban, Kanadában, Az Egyesült Királyságban, Európa, Dél-Kelet-Ázsia, Kelet-Ázsia, Ausztrália és Japán régióiban. Ha a környezet valamelyik régióban van, akkor ezt a funkciót a Finance and Operations Microsoft Dynamics Lifecycle Services (LCS) szolgáltatással engedélyezheti a környezetben. A funkció használata előtt tekintse át az Exportálás konfigurálása az [Azure-adatokkal való használatra való](../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md) előfizetést.

### <a name="enable-and-configure-commerce-analytics-preview"></a><a name="enableCommerceAnalytics"></a> Commerce analitikának engedélyezése és konfigurálása (előnézet)

A Commerce Analytics (Preview) telepítéséhez jogosultsággal kell rendelkeznie erőforrások Azure-előfizetésben való létrehozásához. A bővítmények LCS-be való telepítéséhez is rendelkeznie kell engedéllyel. A lépések áttekintése:

1. [Az Előnézet űrlap elküldése Commerce analitikának](#joinPreview) (Előnézet)
2. [A Exportálás engedélyezése és konfigurálása az Adattárakba](#enableExportToDataLake)
3. [A Commerce Analytics (Preview) bővítmény engedélyezése és](#enableCommerceAnalyticsAddin) konfigurálása
4. [Közös hozzáférési aláírás (SAS) jogkivonat létrehozása saját tárolási](#getSASToken) fiókjához
5. [Töltse le a nézetek telepítési Azure Synapse](#downloadSynapseDeploymentScripts) parancsfájlját.
6. [Munkaterület telepítése és Azure Synapse](#configureAzureSynapse) konfigurálása.
7. [Telepítse a Power BI](#powerbi) sablonalkalmazást.

### <a name="submit-the-preview-intake-form-for-commerce-analytics-preview"></a><a name="joinPreview"></a> Az Előnézet űrlap elküldése Commerce analitikának (Előnézet)

Az Előnézet [űrlap elküldése Commerce analitikának (Előnézet)](https://forms.office.com/r/vW5VLJGXZ2) A képernyő feldolgozásához legfeljebb három munkanapot lehet engedélyezni. A feldolgozás után a visszaigazoló e-mail meg lesz küldve a képernyőn megadott e-mail címre.

### <a name="enable-and-configure-export-to-data-lake"></a><a name="enableExportToDataLake"></a> Adatexportba való exportálás engedélyezése és konfigurálása

A Commerce Analytics (Preview) az "Exportálás az adatokba" szolgáltatáson alapul, hogy a Commerce HQ-adatokat exportálja az Data AQ-be, és hogy az adatokat újak maradjon. A Commerce analitikának (Előnézet) konfigurálása előtt engedélyezze és konfigurálja az Adatexport szolgáltatást az Azure-adatokra való exportálás konfigurálása beállításának [lépéseit](../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md) követve.

Az Export to DataLevél konfigurálása közben jegyezze fel a következő információkat, mivel azt később kell megadnia:

- <a name="keyVault"></a> A kulcs kulcsának neve a tartománynév-rendszerben, és a titkos nevek, ahol az alkalmazásazonosítót és az alkalmazás titkos kulcsát tárolja. A további tudnivalókat lásd [a Kulcskulcshoz hozzáadva kulcskulcshoz.](../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md#addsecrets)
- <a name="storageAccount"></a> Az Adattároló példány tárolási fiókjának neve További tájékoztatás: [Create a Data Storage (Gen2) fiók létrehozása az előfizetésben](../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md#createsubscription).

### <a name="enable-and-configure-the-commerce-analytics-preview-add-in"></a><a name="enableCommerceAnalyticsAddin"></a> A Commerce Analytics (Preview) bővítmény engedélyezése és konfigurálása

A Commerce Analytics (Preview) bővítménynek az LCS-be való telepítéséhez környezeti rendszergazdának kell lennie az LCS-be az ön által használt környezetben.

A Commerce Analytics (Preview) bővítmény telepítéséhez és konfiguráléhez hajtsa végre a következő lépéseket.

1. Jelentkezzen be az [LCS-be,](https://lcs.dynamics.com/) és lépjen be a környezetbe.
2. A Környezet lap Környezeti bővítmények lapján válassza az Új bővítmény **telepítése** **·** **lehetőséget**.
3. A párbeszédpanelen válassza a **Commerce Analytics (Előnézet)** lehetőséget.

    Ha a Commerce analitikát (Előnézet) nem szerepel a listában, győződjön meg arról, hogy csatlakozott a **Belső** szoftverhez.

4. A telepítési **bővítmény** párbeszédpanelen adja meg a következő adatokat.

    | Információk | Forrás | Példa érték |
    |---|---|---|
    | Azure AD Bérlőazonosító az Ön környezetéhez | Jelentkezzen be az [Azure-portálra,](https://portal.azure.com/) és nyissa meg a **Azure Active Directory** szolgáltatást. Ezután nyissa meg a Tulajdonságok lapot, és másolja át az értéket **a** **Címtárazonosító** mezőben. | 72f988bf-0000-0000-00000-2d7cd011db47 |
    | Kulcsának DNS-neve | Adja meg [kulcskulcsának](#keyVault) DNS-nevét. Az előző szakaszban fel kellett volna jegyezni ezt az értéket. | `https://contosod365datafeedpoc.vault.azure.net/` |
    | Az alkalmazásazonosítót tartalmazó titkos fájl | Adja meg [az alkalmazásazonosítót tároló titkos](#keyVault) nevet. Az előző szakaszban fel kellett volna jegyezni ezt az értéket. | alkalmazás azonosítója |
    | Az alkalmazás titkos titkos fájlja | Adja meg [az alkalmazás titkos](#keyVault) nevét. Az előző szakaszban fel kellett volna jegyezni ezt az értéket. | alkalmazás titkos kódja |

5. Fogadja el az ajánlat feltételeit: jelölje be a jelölőnégyzetet, majd válassza a **Telepítés** lehetőséget.

    A rendszer telepíti és konfigurálja a környezet Commerce Analytics (Preview) bővítményét. Ez a folyamat eltarthat néhány percig. Ha befejeződött, a Commerce Analitikának (Előnézet) fel kell lennie sorolva a Környezet lapon, és **az** **állapotnak** Telepítve **állapotúnak kell** lennie.

### <a name="generate-a-sas-token-for-your-storage-account"></a><a name="getSASToken"></a> SAS-token létrehozása saját tárolási fiókjához

A SAS token lehetővé teszi külső entitások számára a tárolási fiók elérését, és adott jogosultságokkal rendelkezik véges időmennyiségre vonatkozóan. Azure Synapse A <a0/1><a2/1><a2/aki a SAS tokent fogja használni a mögöttes adatokhoz a Társítás adatkapcsolatban.

> [!NOTE]
> A Commerce Analitikák (Előnézet) ismert korlátozása miatt a példány nem fér hozzá az adathoz, amikor a Azure Synapse SAS-token lejár. Ezért a SAS token generálása során be kell állítania a szervezet biztonsági irányelvei által engedélyezett maximális lejárati dátumot.

A következő lépések szerint generáljon EGY SAS-tokent.

1. Az Azure-portálon menjen arra a tárolási fiókra, amely az Adatkapcsolatba történő exportálás konfigurálása [során](#storageAccount) létre van hozva.
2. Válassza a Megosztott hozzáférés aláírását a bal oldali ablaktáblában, a tárolási **fiók** alatt.
3. A **SAS**-beállítások lapon állítsa be a következő mezőket.

    | Mező | Érték |
    |---|---|
    | Engedélyezett szolgáltatások | Blob **kiválasztása**. |
    | Engedélyezett erőforrástípusok | Válassza ki **a** szolgáltatást, **a** tárolót és az **objektumot**. |
    | Engedélyezett engedélyek | Válassza **az** Olvasás, az **·** **Írás, a** **Törlés, a** Lista, a Hozzáadás és a **Létrehozás** **lehetőséget**. |
    | Blobverzió-engedélyek | Válassza **a Verziók törlésének lehetővé** lehetőséget. |
    | Kezdő és lejárati dátum/idő | Állítsa be a SAS-token kezdő és záró dátumát és időpontját. |
    | Engedélyezett IP-címek | Ezt a mezőt hagyja üresen. |
    | Engedélyezett protokollok | Csak **HTTPS** kiválasztása. |
    | Preferált útvonalszint | Válassza **az Alap lehetőséget (alapértelmezett).** |
    | Aláírási kulcs | Válassza **ki az 1.** vagy a **2**. kulcsot, ha szükséges. |

4. Válassza **a SAS létrehozása és a kapcsolati karakterlánc** kiválasztását.
5. A SAS token mezőjében található érték másolása és beillesztése **egy** szövegszerkesztőbe, például jegyzettömbbe.

### <a name="download-the-deployment-scripts-for-azure-synapse-views"></a><a name="downloadSynapseDeploymentScripts"></a> A nézetek telepítési parancsfájljának Azure Synapse letöltése

Egy munkaterület szükséges nézetének létrehozásához és közzétételéhez parancsfájlok Azure Synapse készletét kell futtatnia. A parancsfájlok letöltéséhez hajtsa végre a következő lépéseket.

1. AHubHubon menjen a [microsoft/Dynamics365Commerce.Solutions](https://github.com/microsoft/Dynamics365Commerce.Solutions) tárházhoz (repo).
2. Töltse le a parancsfájlokat a helyi számítógépre a repo beírása vagy az irányítószámként való letöltésével.

### <a name="install-and-configure-an-azure-synapse-workspace"></a><a name="configureAzureSynapse"></a> Munkaterület telepítése és Azure Synapse konfigurálása

Egy munkaterület telepítéséhez és Azure Synapse konfigurálásán hajtsa végre a következő lépéseket.

1. Telepítsen Azure Synapse egy munkaterületet az Azure-előfizetésbe. További információ a [Gyorsindítás: Szintaktikás munkaterület](/azure/synapse-analytics/quickstart-create-workspace) létrehozása.
2. Nyissa meg a Jegyzettömbben vagy más szövegszerkesztőben a SetupSynapse.sql parancsfájlt a helyi számítógépnek az az mappájában, amelybe a **Dynamics365Commerce**.Solutions repo fájlt letöltötte az előző szakaszban. A parancsfájl a /Pipeline/CommerceAnalyticsSynapse/ mappa alatt lesz. A forgatókönyvben cserélje le a helyőrző szöveget a következő táblázatban látható értékekkel.

    | Helyőrző szöveg | Helyettesítő érték |
    |---|---|
    | placeholder_storageaccount | Annak a tárolási fióknak a neve, amit az adatexportba történő exportálás konfigurálásakor [létrehozott](#storageAccount). |
    | <a name="phContainer"></a> placeholder_container | Annak a tárolónak a neve, amely az Adatcsomópéldányban jött létre, miután sikeresen telepítette az "Exportálás az adatokba" Bővítmény bővítményt az LCS-be. A tároló nevének bejhezhez a tárolási fiók böngészéshez a Storage Explorert kell használnia az Azure portal webhelyen. |
    | placeholder_sastoken | A [létrehozott](#getSASToken) SAS-token. Mindenképpen távolítsa el a kérdőjelet (? ) a SAS token értékének **kezdetétől**. |
    | <a name="phUserPwd"></a> placeholder_password | A kiválasztott erős jelszó. Jegyezze fel ezt a jelszót. Ez lesz a parancsprogram által létrehozott új **reportreadonlyuser** fiók jelszava. Ne **adja meg az** **sqladminuser fiók** jelszavát. |

3. A parancsfájl frissített tartalmának másolása.
4. Az Azure-portálon menjen az új Azure Synapse munkaterületre. Az Áttekintés **lapon** válassza a **Szintaktikás studio megnyitása** gombra.
5. A Szintapse Studio szolgáltatásban válassza az Új SQL-parancsfájlt, és másolja be a parancsfájl tartalmát az **\> SQL** parancsfájl-szerkesztőbe.
6. Győződjön meg arról, hogy **az Adatbázis használata mező** alapadatként **van** beállítva.
7. Válassza **a** Futtatás lehetőséget, és várja meg, amíg a parancsfájl befejeződik. A parancsfájl sikeres végrehajtása létrehoz egy Commerce-elemzési adatbázist, az adatkapcsolat elérésére vonatkozó hitelesítő adatokat, valamint egy csak olvasható felhasználói fiókot, amely a példányhoz Power BI való csatlakozásra Azure Synapse használható.
8. A helyi számítógépen nyissa meg a Windows PowerShell rendszert rendszergazdai módban, és váltsa át a /Pipeline/CommerceAnalyticsSynapse/ mappát annak a mappának a mappájába, amelybe beásta vagy letöltötte a Dynamics365Commerce.Solutions repo fájlt.
9. Állítsa be a Windows PowerShell végrehajtási irányelvét a következő parancs futtatásával.

    ```powershell
    Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass
    ```

10. Ha az SQL Server PowerShell modul még nincs telepítve, telepítse a következő parancs futtatásával.

    ```powershell
    Install-Module sqlserver
    ```

    > [!NOTE]
    > A modul telepítése során előfordulhat, hogy a rendszer rákérdez a szolgáltató NuGet telepítésére. Ebben az esetben válassza ki a **telepíteni kívánt szolgáltatót az Y** NuGet Y gombra. Előfordulhat, hogy a program kéri annak nyugtázását, hogy nem megbízható tárházból telepíti újra a modulokat. Ebben az esetben a telepítés folytatásához válassza az **Y** lehetőséget. A Set-PSRepository parancsmagot is futtathatja, hogy megbízhat **a** **PSGallery-tárházban.**

11. A nézetek Azure Synapse közzététele a következő parancs futtatásával.

    ```powershell
    .\PublishSynapseViews.ps1 -serverName SERVER_NAME -password PASSWORD -storageAccount STORAGE_ACCOUNT -containerName CONTAINER_NAME -datarootpath DATA_ROOT_PATH
    ```

    A parancs futtatásakor a következő táblázatban látható helyőrző értékeket kell felülírni.

    | Helyőrző értéke | Helyettesítő érték |
    |---|---|
    | SERVER_NAME | A kiszolgáló nélküli Azure Synapse SQL-végpont neve. Ez az érték **az** Azure Synapse Azure-portál munkaterületének Áttekintés lapján érhető el. |
    | JELSZÓ | Az **sqladminuser fiók** jelszava |
    | STORAGE_ACCOUNT | Az Adat És adattárfiók neve |
    | CONTAINER_NAME | Annak a tárolónak a neve, amelyet az Exportálás az adatokba funkció hozott létre. Ez a tároló megegyezik a 2. lépésben megadott [placeholder_container](#phContainer) tárolóval. |
    | DATA_ROOT_PATH | Az összes adatot tartalmazó tároló alatti mappanév. |

    > [!NOTE]
    > A tárolási fiók neve, a tároló neve és az adatgyökér elérési útja az Azure tárolási böngészőben és az Azure portal adattároló tárolófiókján keresztül található meg.

12. Várja meg, amíg a parancsfájl befejeződik. A parancsfájl sikeres végrehajtása SQL-nézeteket hoz létre a Azure Synapse kiszolgáló nélküli SQL-példányban.

### <a name="install-the-power-bi-template-app"></a><a name="powerbi"></a> A Power BI sablonalkalmazás telepítése

A Commerce Analytics Power BI (Preview) sablonalkalmazás telepítéséhez hajtsa végre a következő lépéseket.

1. Jelentkezzen be a [Power BI](https://powerbi.microsoft.com/) portálra saját szervezetazonosítója segítségével.
2. A következőre telepítheti a Commerce analitikát Power BI (Előnézet) sablonalkalmazást [https://aka.ms/cdireport-installapp](https://aka.ms/cdireport-installapp). Előfordulhat, hogy egy figyelmeztetés jelenik meg, hogy az alkalmazás nincs felsorolva a következőn:AppSource Válassza a **Telepítés** parancsot.
3. Ha az alkalmazást első alkalommal újratelepíti, ugorjon előre az 5. lépésre. Ha korábban már telepítette ezt az alkalmazást, a következő frissítési beállítások jelennek meg:

    - **A munkaterület és az alkalmazás frissítése – a meglévő sablonalkalmazás frissítése és a meglévő alkalmazásbeállítások, például az alkalmazáspéldány neve és az** engedélykonfigurációk felülírása.
    - **Csak a munkaterület tartalmának frissítése az alkalmazás frissítése nélkül – frissíti a meglévő sablonalkalmazást,** de megtartja a meglévő alkalmazásbeállításokat. *Ez a beállítás az alkalmazásfrissítések ajánlott használata.*
    - **Az alkalmazás egy másik másolatának telepítése új munkaterületre – új munkaterület létrehozása, majd a meglévő** sablonalkalmazás másolatának létrehozása. A meglévő munkaterület sértetlenül megmarad.

4. Válasszon egyet a frissítési beállítások közül, majd válassza a Telepítés **lehetőséget**.
5. A telepített alkalmazást úgy nyithatja meg, hogy kijelöli az **Alkalmazásokat** a bal oldali ablakban, majd kiválasztja az alkalmazást.
6. Az alkalmazás az adatforráshoz való kapcsolása a Csatlakozás lehetőség **választásával** Ha korábban már telepítette az alkalmazást, jelölje be az Adatkapcsolat összekapcsolása lehetőséget **a** sárga üzenetsávon.
7. Állítsa be a következő mezőket.

    | Mező | Érték |
    |---|---|
    | Kiszolgáló | Adja meg az előző szakaszban létrehozott kiszolgáló nélküli Azure Synapse SQL-végpont nevét. Ez az érték **az** Azure Synapse Azure-portál munkaterületének Áttekintés lapján érhető el. |
    | Adatbázis | Adja meg **a CommerceAnalytics** et. |
    | Nyelv | Válasszon ki egy értéket a listából. Ez a mező honosított termék- és kategórianevekhez használható. Az érték megkülönbözteti a kis- és a nagybetűket. |
    | Dátumtartomány | Válasszon ki egy értéket a listából. A program a kiválasztott számú hónap adatait importálja az Power BI adatkészletbe. A kiválasztott érték az adatkészlet méretét és a szinkronizáláshoz szükséges időt befolyásolja. |

8. Válassza ki **Következő** lehetőséget. A rendszer kéri az SQL-adatbázishoz való kapcsolódás hitelesítő adatainak Azure Synapse megadását. A mezők beállítása a következő táblázatnak megfelelő módon.

    | Mező | Érték |
    |---|---|
    | Hitelesítési módszer | Válassza az **Alap** lehetőséget. |
    | Felhasználónév | Adja **meg a reportreadonlyuser adhatja** meg. |
    | Jelszó | Adja meg azt az értéket, amely placeholder_password [SetupSynapse](#phUserPwd).SQL parancsfájlban a helyőrzőt cserélte le. Ez a jelszó a **reportreadonlyuser fiók** jelszava. |

9. Válassza ki **a bejelentkezést és a** csatlakozást.
10. Várja meg az adatkészlet sikeres frissítését. Ezután az Alkalmazás szerkesztése gombra kattintva nyissa meg az alkalmazás munkaterületét, ahol megtekintheti az adatkészlet frissítési **állapotát**. Az alkalmazás munkaterületén beállíthatja az adathalmaz automatikus frissítési ütemezését is, kezelheti az engedélyeket, és átnevezheti az alkalmazáspéldányt.

### <a name="privacy"></a><a name="privacy"></a>Adatvédelem

Az Ön személyes adatainak védelme fontos a számunkra. További információt az [adatvédelmi nyilatkozatban találhat](https://go.microsoft.com/fwlink/?LinkId=521839).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
