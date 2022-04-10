---
title: Commerce elemzések (Előzetes verzió)
description: Ez a témakör azt mutatja be, hogyan lehet telepíteni és használni az analitika-funkciókat a rendszerben Microsoft Dynamics 365 Commerce.
author: AamirAllaq
ms.date: 02/24/2022
audience: Application user
ms.reviewer: sericks
ms.search.region: Global
ms.author: aamiral
ms.search.validFrom: 2021-11-12
ms.openlocfilehash: 7e3721421e15bc3e5937691cdbaee51e4d3cdd17
ms.sourcegitcommit: d2e5d38ed1550287b12c90331fc4136ed546b14c
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/25/2022
ms.locfileid: "8349743"
---
# <a name="commerce-analytics-preview"></a>Commerce elemzések (Előzetes verzió)

[!include [banner](includes/banner.md)]

Ez a témakör bemutatja a Commerce Analitikának (Előnézet) a telepítéséhez szükséges funkciókat Microsoft Dynamics 365 Commerce.

## <a name="commerce-analytics-preview-live-demo"></a>Commerce Analytics (Preview) élő bemutató

A Commerce Analytics (Előnézet) [élő bemutatóját is megtekintheti](https://aka.ms/CommerceAnalyticsDemo).

![Commerce Analytics (előnézeti) összegzése](media/CommerceAnalytics_Summary.png)
![Commerce Analytics (Előnézet) fizetések](media/CommerceAnalytics_Payments.png)
![Commerce Analytics (előnézeti) webes tevékenység](media/CommerceAnalytics_WebActivity.png)

## <a name="commerce-analytics-preview-system-architecture"></a>Commerce Analytics (Preview) rendszerarchitektúra

### <a name="key-components"></a>Kulcsösszetevők

A Commerce Analytics (Preview) a következő kulcsösszetevőkből áll:

- Használatra kész interaktív Power BI jelentések
- SQL-nézetek a következőben: Azure Synapse Analytics
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
- Az adatokat más rendszerek, például Dynamics 365 Connected Spaces a.

#### <a name="step-2-ingestion-and-pre-processing"></a>2. lépés: Áthozat és előfeldolgozás

A tranzakciós adatok közvetlenül (a Commerce HQ ügyfélben közvetlenül rögzített rendelések esetén) vagy a Commerce Scale Unit egységen keresztül (a POS-nál, e-kereskedelemben rögzített rendelések esetén, illetve a fej nélküli Commerce rendszer által használt egyedi ügyfeleken) keresztül érik el a tranzakciós adatokat.

Az "Exportálás az Adatba" funkció használatával a tranzakciós adatokat a rendszer nyers adatként másolja az adatokba. Az adattáblában a nyers adatok a Táblák mappában tárolódnak.

Az e-commerce webes tevékenység adatai közvetlenül az adatkapcsolatba küldik. A más rendszerek által előállított adatokat, például a Dynamics 365 Connected Spaces rendszereket közvetlenül az adatrendszernek küldi a rendszer.

#### <a name="step-3-transformation-and-aggregation"></a>3. lépés: Átalakítás és összesítés

Miután a nyers adatok az adatok tárolójában vannak, a Commerce Elemzési szolgáltatás beolvassa, átalakítja, összesíti, majd logikai entitások formájában visszaírja az adatokba (az Entitások mappában) és az összesített mérőszámokat (az Ontologies mappában).

#### <a name="step-4-querying"></a>4. lépés: Lekérdezés

Azure Synapse Analytics A <a0/<a0/<a2/1><a2/<a2/<a2/<a2/<a3/<a3/–<a3 Ez a felület SQL-nézeteket tartalmaz. Az SQL nézetek lehetővé teszik az adatok összevont lekérdezését az adatkapcsolatban, akár közvetlenül, egy T-SQL ügyfélen keresztül (ad-hoc elemzéshez), Power BI vagy megjelenítő eszköz például.

#### <a name="step-5-modeling-and-serving"></a>5. lépés: Modellezés és kiszolgáló

A lekérdezett adatok a Azure Synapse Analytics " Power BI szemantikus modell" adatai. Az adatok típusától függően lehet, Power BI hogy időnként importálják a memóriába, vagy közvetlenül lekérdezik őket futásidőben.

Végül az adatok vizuális Power BI jelennek meg, így a felhasználók megtekinthetik és kommunikálhatnak vele.

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

#### <a name="top-level-filters"></a><a name="TopLevelFilters"></a> Legfelső szintű szűrők

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

#### <a name="products"></a><a name="ProductsPage"></a> Termékek

- Értékesítés
- Margó
- Visszáruk

#### <a name="customers"></a><a name="CustomersPage"></a> Ügyfelek

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
    - Fizetési mód

### <a name="customers"></a><a name="CustomersPage"></a> Ügyfelek

- Élettartam értéke (LÉRE)

    Az LVEL számítása a vevő által az összes értékesítési csatornában (például a POS, az e-commerce és a Dynamics 365 Commerce hívásközpontban) töltött teljes összeg alapján történik.

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
    - Pénztár
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

    A munkamenet munkamenet-munkamenet, ahonnan a felhasználó közvetlenül az e-commerce webhelyre való látogatást követően indul el. A további tudnivalókat lásd [: Kamatláb](https://en.wikipedia.org/wiki/Bounce_rate).

- Rákattint munkamenetenként

#### <a name="visitors"></a>Látogatók

Az e-commerce webhely névtelen használatának azonosítása egyedileg történik a felhasználó által használt böngésző és eszköz alapján. A Commerce analitikában nem lehet nyomon követni a különböző böngészőkben és eszközökben lévő névtelen problémákat. Egy névtelen felhasználó, aki ugyanazon az eszközön ugyanazt a böngészőt használja, egyedileg azonosítják több felhasználói munkamenet során, amíg a böngésző gyorsítótárazott adatait meg nem törlik, vagy amíg az időszak (általában 12 hónap) el nem tel, amelyik előbb történik meg.

Ha a bejelentkezve tallózással megkeresi az e-commerce webhelyet, akkor a Commerce analitikával további információkat lehet velük kapcsolatban adni. Ezek az információk azon Dynamics 365 Commerce alapulnak, hogy milyen viszonyban van a szervezet az összes értékesítési csatornában (például a POS, az e-commerce és a hívásközpont) keresztül történt korábbi beszerzések eredményeként. A további információk közé tartozik a recency, a kapcsolat hossza, az élettartam értéke és a gyakorisági adatok.

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

        Az LVEL számítása a vevő által az összes értékesítési csatornában (például a POS, az e-commerce és a Dynamics 365 Commerce hívásközpontban) töltött teljes összeg alapján történik.

    - Gyakoriság szerint

        A gyakoriságot a vevőnek a szervezettel való tranzakciós ügylete alapján számítja ki a program. A gyakoriság jelenleg nem veszi figyelembe a nem tranzakciós tevékenység jelzéseit, például az e-commerce böngészési tevékenységet.

#### <a name="impressions"></a>Benyomások

A vizuális megjelenítés a termék vizuális megjelenítése az e-kereskedelemben. Például az e-commerce értékesítés az e-commerce webhely kezdőlapjára kerül, és a **legjobb** eladási listamodulban egy gyermekterméket is megtekint. A viselkedés ezt követően ugyanazt az első **terméket egy Kivét listás modulban** nézi meg. Ebben az esetben két termékjelet kelt fel.

Jelenleg a alábbiak szerint nyomon követik a alábbiakat:

- Listák (például ajánlott, **legjobb** **eladási**, **kiválasztó** az Ön számára és **Trending**)
- Kosármodul
- Keresési eredmények tárolója
- Kategóriakeresési eredmény tárolója

Jelenleg a carousel modulban vagy az egyéni vizuális megjelenítésben megjelenített termékek nem számítanak bele a látójelekkel kapcsolatos mérőszámokbe.

A **Jelentések jelentés** a következő mérőszámokat tartalmazza:

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
> A Commerce Analytics (Preview) előnézetben látható az Egyesült Államokban, Kanadában, Az Egyesült Királyságban, Európa, Dél-Kelet-Ázsia, Kelet-Ázsia, Ausztrália és Japán régióiban. Ha a Pénzügyi és üzemeltetési környezet valamelyik régióban van, Microsoft Dynamics akkor ezt a funkciót a Lifecycle Services (LCS) szolgáltatás segítségével engedélyezheti a környezetben. A funkció használata előtt tekintse [át az Exportálás konfigurálása az Azure-adatokkal való használatra való előfizetést](../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md).

### <a name="enable-and-configure-commerce-analytics-preview"></a><a name="enableCommerceAnalytics"></a> Commerce analitikának engedélyezése és konfigurálása (előnézet)

A Commerce Analytics (Preview) telepítéséhez jogosultsággal kell rendelkeznie erőforrások Azure-előfizetésben való létrehozásához. A bővítmények LCS-be való telepítéséhez is rendelkeznie kell engedéllyel. 

A Commerce Analytics (Preview) engedélyezéséhez és konfigurálhoz hajtsa végre a következő lépéseket.

1. [Az Exportálás a Következőbe bővítmény engedélyezése és konfigurálása](#enableExportToDataLake):
1. [Munkaterület telepítése és Azure Synapse konfigurálása](#configureAzureSynapse).
1. [Hozzáadás a kulcshoz.](#addSecrets)
1. [A Commerce Analytics (Preview) bővítmény engedélyezése és konfigurálása](#enableCommerceAnalyticsAddin)
1. [Telepítse a Power BI sablonalkalmazást](#powerbi).

### <a name="enable-and-configure-the-export-to-data-lake-add-in"></a><a name="enableExportToDataLake"></a> Az Exportálás a Következőbe bővítmény engedélyezése és konfigurálása:

> [!IMPORTANT]
> Ha beállítja az Adatexportportás Bővítménybe való exportálást, **törölje a jelölést a Valós** idejű adatváltozások jelölőnégyzetből az Exportálás az Adatokba beállítási lapról, hogy a valós idejű adatváltozások ne legyen engedélyezve. A **Real-time data changes** funkció előnézetben látható, és a Commerce Analytics jelenleg nem támogatja. Ha engedélyezi a funkciót, a Commerce Analytics nem fogja tudni feldolgozni az adatokat az adatkapcsolatban, Power BI és a legtöbb jelentése nem fog tartalmazni adatokat.

A Commerce Analitika (Preview) az Adatexport szolgáltatáson alapul, hogy a Commerce Headquarters adatait exportálja az Data Analytics alkalmazásba, és így megtartsa az adatokat. Mielőtt konfigurálja a Commerce analitikát (Preview), engedélyezze és konfigurálja az Adatexportba való exportálást a Következő [lépésekkel: Konfigurálja az Exportálás az Azure-adatokhoz – Ügyfélkapcsolat beállítását](../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md).

Miközben konfigurálja az Adatexporttatás – Bővítmények bővítményt, jegyezze fel a következő információkat, mivel azt később kell megadnia:

- <a name="keyVault"></a> A megadott kulcsnév tartománynév-rendszere (DNS).
- A megadott titkos nevek, amelyek az alkalmazásazonosítót és az alkalmazás titkos azonosítóját tartalmazzák. A további tudnivalókat lásd [a Kulcskulcshoz hozzáadva kulcskulcshoz.](../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md#addsecrets)

### <a name="install-and-configure-an-azure-synapse-workspace"></a><a name="configureAzureSynapse"></a> Munkaterület telepítése és Azure Synapse konfigurálása

A Commerce Analytics (Preview) telepítéséhez szükség van a Munkaterületen a Szintaktikai SQL igény szerinti telepítésére Azure Synapse. Egy munkaterület telepítéséhez és konfigurálásán Azure Synapse hajtsa végre a következő lépéseket.

1. Telepítsen egy Azure Synapse munkaterületet az Azure-előfizetésbe. További információ a [Gyorsindítás: Szintaktikás munkaterület létrehozása](/azure/synapse-analytics/quickstart-create-workspace).
1. <a name="serverlessep"></a> A munkaterület létesítése után nyissa meg az erőforrás áttekintő lapját, **és jegyezze fel a kiszolgáló nélküli SQL-végpont** értékét. Ezt az értéket a következő szakasz kulcsában kell tárolnia.
1. Az áttekintési lapon jelölje be **a Szintapse Studio** megnyitása hivatkozást Azure Synapse a munkaterület Studio elemének megnyitásához.
1. Válassza a **Kezelés** elemet a bal oldali menüben. Előfordulhat, hogy a menünevekhez a bal oldali menüben kell kiválasztani a kibontás hivatkozását.
1. A **Biztonsági csoport csoportban** válassza a Hozzáférés-vezérlés **lehetőséget**. 
1. Válassza a **Hozzáadás** lehetőséget.
1. A Szerepkör-hozzárendelés **hozzáadása** ablakban állítsa be a beállításokat az alábbi táblázatban leírt módon.

    | Beállítás | Érték |
    |--------|-------|
    | Hatókör | Munkaterület **kiválasztása**. |
    | Szerep | Válassza a **Szintaktikás SQL-rendszergazda lehetőséget**.|
    | Felhasználó kijelölése | Annak az alkalmazásnak a [neve](../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md#createapplication), amit az Adatexportációba való exportálási bővítmény telepítésekor létrehozott. Ha az alkalmazás megjelenik a keresési eredmények között, válassza ki. Az alkalmazás megjelenik a Kiválasztott felhasználók **, csoportok és szolgáltatásnév szakaszon**. |

1. A szerepkör-hozzárendelés **befejezéséhez** válassza az Alkalmaz lehetőséget. Az alkalmazás Szintakt SQL-rendszergazdai jogosultságokat kapott. Emiatt létrehozhatja a szükséges nézeteket a Commerce Analytics (Preview) LCS-bővítmény konfigurálása során.

### <a name="add-secrets-to-the-key-vault"></a><a name="addSecrets"></a> Bővítmény hozzáadása a kulcshoz

Ugyanabban a [kulcsban](../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md#createkeyvault), amit az Adatexportba történő exportálás bővítmény konfigurálása közben használt, a következő táblában látható konfigurációt kell hozzáadnia. Minden egyes titkos adathoz meg kell adnia egy titkos nevet és a megadott értéket.

| Javasolt titkos név | Titkos kód értéke | Példa titkos érték |
|---------|---------|---------|
| szintaktik-sql-kiszolgáló | A kiszolgáló nélküli SQL-végpont értéke, amit a munkaterület [konfigurálása közben észlelt Azure Synapse](#serverlessep). | `test-ondemand.sql.azuresynapse.net` |
| <a name="roUser"></a> readonly-sql-pwd | A csak olvasható SQL-felhasználó számára beállított jelszó. A Power BI jelentés ezzel a jelszóval kapcsolódik a kiszolgáló nélküli SQL-kiszolgálóhoz. A jelszó beállításához kövesse szervezetének jelszó-irányelveit. | |

### <a name="enable-and-configure-the-commerce-analytics-preview-add-in"></a><a name="enableCommerceAnalyticsAddin"></a> A Commerce Analytics (Preview) bővítmény engedélyezése és konfigurálása

A Commerce Analytics (Preview) bővítménynek az LCS-be való telepítéséhez környezeti rendszergazdának kell lennie az LCS-be az ön által használt környezetben.

A Commerce Analytics (Preview) bővítmény telepítéséhez és konfiguráléhez hajtsa végre a következő lépéseket.

1. Jelentkezzen be az [LCS-be](https://lcs.dynamics.com/), és lépjen be a környezetbe.
2. A Környezet **lap** **Környezeti bővítmények** **lapján válassza az Új bővítmény telepítése lehetőséget**.
3. A párbeszédpanelen válassza a **Commerce Analytics (Előnézet) lehetőséget**.
4. A telepítési **bővítmény párbeszédpanelen** adja meg a következő adatokat.

    | Információk | Forrás | Példa érték |
    |---|---|---|
    | Azure Active Directory(Azure AD) Bérlő azonosítója | Jelentkezzen be az [Azure-portálra](https://portal.azure.com/), és nyissa meg a **Azure Active Directory** szolgáltatást. Ezután nyissa meg **a Tulajdonságok** lapot, és másolja át az értéket a Bérlő **azonosítója mezőben**. | `72f988bf-0000-0000-00000-2d7cd011db47` |
    | Az Azure-kulcs DNS-neve | Adja meg kulcskulcsának DNS-nevét. Ezt az értéket meg kell jegyezte volna, [miközben az Adatexportált bővítményt konfigurálta](#keyVault). | `https://contosod365datafeedpoc.vault.azure.net/` |
    | Az alkalmazásazonosítót tartalmazó titkos név | Adja meg az alkalmazásazonosítót tároló titkos nevet. Ezt az értéket meg kell jegyezte volna, [miközben az Adatexportált bővítményt konfigurálta](#keyVault). | `app-id` |
    | Az alkalmazás titkos nevét tartalmazó titkos név | Adja meg az alkalmazás titkos nevét. Ezt az értéket meg kell jegyezte volna, [miközben az Adatexportált bővítményt konfigurálta](#keyVault). | `app-secret` |
    | A kiszolgáló nélküli SQL-végpontot tartalmazó titkos név a következő számára: Azure Synapse | Adja meg a kiszolgáló nélküli SQL-végpontot tároló titkos nevet. A titkos kulcsot létre kellett volna hozatni, miközben a [kulcsértékhez hozzáadott egy új 5000 000 000 000](#addSecrets) 000 000 000 00 | `synapse-sql-server` |
    | Az SQL írásra csak olvasható felhasználók számára beállított jelszót tartalmazó titkos név a következőben: Azure Synapse | Annak a titkos névnek a megadása, amely a kiszolgáló nélküli SQL-írás nélküli felhasználók számára beállított jelszót tárolja. Ezt a felhasználót fogja létrehozni a rendszer, Power BI és a felhasználónak kell használnia a jelentésben a kiszolgáló nélküli SQL-kiszolgálóhoz való csatlakozásra. A titkos kulcsot akkor kellett volna létrehoznia, amikor hozzáadta [a kulcs értékét](#addSecrets). | `readonly-sql-pwd` |

1. Fogadja el az ajánlat feltételeit: jelölje be a jelölőnégyzetet, majd válassza a Telepítés **lehetőséget**.

    A rendszer telepíti és konfigurálja a környezet Commerce Analytics (Preview) bővítményét. Ez a folyamat eltarthat néhány percig. Ha befejeződött, **a Commerce Analitikának (Előnézet)** **fel** kell lennie sorolva a Környezet lapon, és az állapotnak Telepítve állapotúnak kell **lennie.**

### <a name="install-the-power-bi-template-app"></a><a name="powerbi"></a> A sablonalkalmazás Power BI telepítése

A Commerce Analytics Power BI (Preview) sablonalkalmazás telepítéséhez hajtsa végre a következő lépéseket.

1. Jelentkezzen be a portálra [Power BI](https://powerbi.microsoft.com/) saját szervezetazonosítója segítségével.
1. A következőre telepítheti a Commerce analitikát (Előnézet) Power BI sablonalkalmazást [https://aka.ms/cdireport-installapp](https://aka.ms/cdireport-installapp). Másik lehetőségként keresse fel az analitika [AppSource Dynamics 365 Commerce lapját](https://appsource.microsoft.com/product/power-bi/dynamics-365-commerce.dydnamics-365-commerce-analytics), és válassza a **Behozás lehetőséget**.
1. Ha az alkalmazást első alkalommal újratelepíti, ugorjon előre az 5. lépésre. Ha korábban már telepítette, az alkalmazás frissítésének következő beállításai érvényesek:

    - **A munkaterület és az alkalmazás** frissítése – a meglévő sablonalkalmazás frissítése és a meglévő alkalmazásbeállítások, például az alkalmazáspéldány neve és az engedélykonfigurációk felülírása.
    - **Csak a munkaterület tartalmának frissítése az alkalmazás frissítése nélkül** – frissíti a meglévő sablonalkalmazást, de megtartja a meglévő alkalmazásbeállításokat. *Ez a beállítás az alkalmazásfrissítések ajánlott használata.*
    - **Az alkalmazás egy másik másolatának** telepítése új munkaterületre – új munkaterület létrehozása, majd a meglévő sablonalkalmazás másolatának létrehozása. A meglévő munkaterület sértetlenül megmarad.

1. Válasszon egyet a frissítési beállítások közül, majd válassza a Telepítés **lehetőséget**.
1. A telepített alkalmazást úgy nyithatja meg, hogy **kijelöli az Alkalmazásokat** a bal oldali ablakban, majd kiválasztja az alkalmazást.
1. Az alkalmazás az adatforráshoz való kapcsolása a Csatlakozás lehetőség **választásával**. Ha korábban már telepítette az alkalmazást, jelölje be **az** Adatkapcsolat összekapcsolása lehetőséget a sárga üzenetsávon.
1. Állítsa be a következő mezőket.

    | Mező | Érték |
    |---|---|
    | Kiszolgáló | Adja meg azt a kiszolgáló nélküli SQL-végpontot, amelyről megjegyzést hozott létre a [munkaterület létrehozása Azure Synapse után](#serverlessep). |
    | Adatbázis | Adja meg **a CommerceAnalytics adhatja meg**. |
    | Nyelv | Válasszon ki egy értéket a listából. Ez a mező honosított termék- és kategórianevekhez használható. Az érték megkülönbözteti a kis- és a nagybetűket. |
    | Dátumtartomány | Válasszon ki egy értéket a listából. A program a kiválasztott számú hónap adatait importálja az adatkészletbe Power BI. A kiválasztott érték az adatkészlet méretét és a szinkronizáláshoz szükséges időt befolyásolja. |

1. Válassza ki **Következő** lehetőséget. Amikor a rendszer kéri Azure Synapse az SQL-adatbázishoz való kapcsolódás hitelesítő adatainak megadását, állítsa be a mezőértékeket az alábbi táblázatnak megfelelő módon.

    | Mező | Érték |
    |---|---|
    | Hitelesítési módszer | Válassza az Alap **lehetőséget**. |
    | Felhasználónév | Reportreadonlyuser **beírása**. |
    | Jelszó | Írja be a csak olvasható [SQL-felhasználó számára tárolt jelszót a kulcskulcsban](#roUser). |

1. Válassza ki **a bejelentkezést és a csatlakozást**.
1. Várjon, amíg az adatkészlet sikeresen frissül. Ezután a **Szerkesztés alkalmazás lehetőséget választva** nyissa meg az alkalmazás munkaterületét, ahol megtekintheti az adatkészlet frissítési állapotát. Az alkalmazás munkaterületén beállíthatja az adathalmaz automatikus frissítési ütemezését is, kezelheti az engedélyeket, és átnevezheti az alkalmazáspéldányt.

### <a name="privacy"></a><a name="privacy"></a>Adatvédelem

Az Ön személyes adatainak védelme fontos a számunkra. További információt az [adatvédelmi nyilatkozatban találhat](https://go.microsoft.com/fwlink/?LinkId=521839).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
