---
title: Commerce analitika (előnézet)
description: Ez a témakör részletesen tartalmazza az analitika-képességek telepítésének és használatának a témakörben való használatát Dynamics 365 Commerce.
author: AamirAllaq
ms.date: 11/15/2021
audience: Application user
ms.reviewer: sericks
ms.search.region: Global
ms.author: aamiral
ms.search.validFrom: 2021-11-12
ms.openlocfilehash: 7f3e51cc3f7314bd33bca9e598bd0b1c9118caef
ms.sourcegitcommit: 9f8da0ae3dcf3861e8ece2c2df4f693490563d5e
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/16/2021
ms.locfileid: "7817455"
---
# <a name="commerce-analytics-preview"></a>Commerce analitika (előnézet)

[!include [banner](includes/banner.md)]

A Commerce analitika a Dynamics 365 Commerce. Ez a témakör részletesen leírja a Commerce analitikát, és bemutatja a telepítéssel kapcsolatos részleteket. 

## <a name="system-architecture"></a>Rendszerarchitektúra
### <a name="key-components"></a>Kulcsösszetevők
A Commerce Analytics a következő kulcsösszetevőkből áll:
- Interaktív jelentések használatára Power BI kész
- SQL-nézetek az Azure Synapse Analitikában
- Entitás- és ontológiaadatok az Azure-adatokban
- Nyers adatok az Azure-adatokban

![A Commerce Analitikának rendszerarchitektúra](media/CommerceAnalytics.png)

### <a name="data-flow"></a>Adatáramlás
#### <a name="step-1-data-generation"></a>1. lépés: Adatok létrehozása
Az adatok vagy tranzakciós adatokból, vagy a következő forrásokból származó viselkedési adatokból származnak:
- Hívásközpont-társítás a Commerce központi ügyfél használatával az értékesítési rendelések feldolgozásához
- Pénztáros a pénztárnál (POS) az értékesítési tranzakciók feldolgozását
- A Headless Commerce (Commerce Scale Unit) használatával létrehozott értékesítések az egyéni alkalmazásokon belül
- Az e-commerce vásárló böngészése az e-commerce webhelyen 
- Az e-commerce vásárló rendelést ad fel az e-commerce webhelyre.
- Más rendszerek, például Dynamics 365 Connected Spaces

#### <a name="step-2-ingestion-and-pre-processing"></a>2. lépés: Áthozat és előfeldolgozás
A tranzakciós adatok közvetlenül (közvetlenül a Commerce HQ ügyfélben rögzített rendelések) vagy a Commerce Scale Unit (a Headless Commerce használatával rögzített rendelések) vagy a Commerce Scale Unit osztályból (a POS-nál, e-commerceben rögzített rendelésekből vagy egyéni ügyfelekből) lépnek be. 

A tranzakciós adatokat a rendszer ezután nyers adatként átmásolja az Azure Data Táblába az Exportálás az adatokba funkcióval, és az adatokat a "Táblák" mappában **·** tárolja a rendszer. Az e-commerce webes tevékenység adatai közvetlenül az adatkapcsolatba küldik.

A más rendszerek, például az adatok közvetlenül az adatkapcsolatba Dynamics 365 Connected Spaces küldik.

#### <a name="step-3-transformation-and-aggregation"></a>3. lépés: Átalakítás és összesítés
Ha a nyers adatok már az adatokban vannak, a Commerce Elemzési szolgáltatás beolvassa, átalakítja, összesíti az adatokat, majd logikai entitások formájában visszaírja őket az adatokba az "Entitások" mappában, és összesített mérőszámokat az "Ontologies" mappában. 

#### <a name="step-4-querying"></a>4. lépés: Lekérdezés
A rendszerben az Analitikával egy T-SQL-illesztőfelületen keresztül kérdez le a Azure Synapse rendszer. A felület OLYAN SQL-nézeteket tartalmaz, amelyek lehetővé teszik a ládában található adatok összevont lekérdezését, akár közvetlenül, ad-hoc elemzésre használt T-SQL ügyfél használatával, akár megjelenítő eszköz például Power BI.

#### <a name="step-5-modeling-and-serving"></a>5. lépés: Modellezés és kiszolgáló
Az Analitika által lekérdezett adatok Azure Synapse ezután a Power BI szemantikus modellbe kerül. Az adatok típusától függően vagy rendszeres időközönként importálja a memóriába, vagy közvetlenül lekérdezi őket Power BI a rendszer futási időben. 

A végső fokozat az, amikor a felhasználók a vizuális adatokat megjelenítik és Power BI kommunikálják. 

## <a name="commerce-analytics-functional-overview"></a>Commerce Analytics - működési áttekintés
### <a name="1-summary"></a>1. Összegzés
#### <a name="top-level-filters"></a>Legfelső szintű szűrők
1.  Dátumbeállítások
    1. Év
    2. Negyedév    
    3. Hónap    
    4. Hét    
    5. Nap
2. Csatornabeállítások
    1. Jogi személy    
    2. Csatorna típusa    
    3. Vevőtípus    
    4. Értékesítés típusa    
    5. Csatorna    
    6. Szervezeti hierarchia
3. Termékbeállítások
    1. Kategóriahierarchia    
    2. Kategória

#### <a name="a-product"></a>a. Termék
1. Értékesítés
2. Margó
3. Visszáruk

#### <a name="b-customer"></a>b. Vevő
1. Értékesítés
2. Margó
3. Visszáruk

#### <a name="c-channel"></a>c. Csatorna
1. Értékesítés
2. Margó
3. Visszáruk

### <a name="2-sales"></a>2. Értékesítés
1. Szállítási hely szerint
2. Csatorna/üzlet/terminál szerint
3. Alkalmazott szerint
4. Dátum szerint
5. Óra szerint
6. Termékkategória szerint

### <a name="3-margin"></a>3. Árrés
1. Szállítási hely szerint
2. Melléktermék
3. Dátum szerint

### <a name="4-return"></a>4. Visszáru
1. Visszáru összeg szerint
    1. Üzlet szerint    
    2. Melléktermék    
    3. Dátum szerint
2. Visszáru tranzakciónként
    1. Üzlet szerint    
    2. Melléktermék    
    3. Dátum szerint

### <a name="5-discount"></a>5. Engedmény
1. Üzlet szerint
2. Melléktermék
3. Dátum szerint
4. Felbontás
    1. Jogi személy    
    2. Üzlet    
    3. Engedmény típusa    
    4. Engedmény neve    
    5. Termék

### <a name="6-payment"></a>6. Fizetés
1. Csatornák/terminálok szerint
2. Fizetési mód/típus szerint
3. Dátum szerint
4. Felbontás
    1. Jogi személy    
    2. Csatorna típusa    
    3. Üzlet    
    4. Terminál    
    5. Kifizetési mód

### <a name="7-customer"></a>7. Vevő
1. Élettartam-érték (L COMMERCE): Az élettartam értékét a vevő által az összes Commerce értékesítési csatornában (POS, e-commerce és hívásközpont) elköltött teljes összeg alapján számítja ki a program.
2. Recency: A Recency számítása a vevő és a szervezet között történt utolsó tranzakciós tevékenység óta eltszámított napok száma alapján történik. A Recency nem veszi figyelembe a nem tranzakciós tevékenység jelzéseit, mint például az e-commerce böngészési tevékenység.
3. Gyakoriság: A gyakoriság számítása a vevőnek a szervezettel való tranzakciós ügylete alapján történik. A gyakoriság nem veszi figyelembe a nem tranzakciós tevékenység jelzéseit, mint például az e-commerce böngészési tevékenység.
4. Kapcsolat hossza: A kapcsolat hosszának számítása a vevőrekord rendszerben való létrehozása óta eltszámlott napok száma alapján történik. 
5. Tranzakciók száma

### <a name="8-comparison"></a>8. Összehasonlítás
1. Termék-összehasonlítás időszak szerint
    1. Értékesítési és értékesítési különbözet
    2. Árrés és árrés eltérése
2. Vevő időszak szerint
    1. Értékesítési és értékesítési különbözet
    2. Árrés és árrés eltérése

### <a name="9-web-activity"></a>9. Webes tevékenység

#### <a name="top-level-filters"></a>Legfelső szintű szűrők
1. Dátumtartomány
2. Csatorna típusa
3. Csatorna
4. Kategóriahierarchia

#### <a name="a-acquisition"></a>a. Beszerzés
1. Lapnézetek
    1. Országok/régiók szerint    
    2. Melléktermék    
    3. Bejelentkezett felhasználó állapota szerint    
    4. Dátum szerint
2. E-commerce rendelések
3. Átváltási árfolyam
    1. Dátum szerint
4. Konverziós tölcsér
    1. Lapnézet laptípus szerint (kezdőlap, kategóriaoldal, termék részletei oldal)  
    2. Hozzáadás a kosárhoz    
    3. Fizetés   
    4. Beszerzés

#### <a name="b-session"></a>b. Munkamenet
A munkamenet annak a felhasználónak az e-commerce webhelyen tett látogatásának a száma, amely a felhasználó számára meg van adva. A munkamenet 30 perc inactivity után vagy 24 órával az aktív használat utánnak minősül.
1. Országok/régiók szerint
2. Eredet szerint (külső hivatkozás)
3. Bejelentkezett felhasználó állapota szerint
4. Munkamenetek száma
    1. Dátum szerint    
    2. Beviteli oldal szerint
5. Rendelés munkamenetenként
    1. Dátum szerint
6. Munkamenet kamatlába: A munkamenet-munkamenet munkamenetként van meghatározva, ahol a felhasználó azonnal elhagyja az e-commerce webhelyet. 
7. Rákattint munkamenetenként

#### <a name="c-visitor"></a>c. Látogató
Az e-commerce webhely névtelen felelősséget az adott eszköz adott böngészőjében található egyedi azonosító alapján határozzák meg. A Commerce Analytics nem követi nyomon a névtelen felhasználókat különböző böngészőkben és eszközökben. Egy névtelen felhasználó, aki ugyanazon a számítógépen ugyanazt a böngészőt használja, egyedileg azonosítva van több felhasználói munkamenet során mindaddig, amíg a böngésző gyorsítótárának adatait meg nem törlik, vagy jellemzően egy 12 hónapos időszakig (amelyik a két elődtől függ).

A Commerce Analitikával további információkat kaphat arról, hogy ki böngészhet az e-commerce webhelyen, miközben bejelentkezik. Az adatok az ezekkel a felhasználóval meglévő kapcsolaton alapulnak, beleértve a felhasználóktól a szervezettől az összes Commerce értékesítési csatornában (POS, hívásközpont és e-kereskedelem) készített beszerzéseket, valamint tartalmazza a recency, a kapcsolat hosszát, az élettartam értékét és a gyakoriságot.

1. Fedezeti árrés
2. Átlagos rendelések
3. Átlagos értékesítés
4. E-commerce rendszerbeli számlálás
    1. Dátum szerint
    2. Hely szerint: A Commerce analitikák csak az ország/régió szintjén nyújthatnak részletességet az e-commerce rendszer rendszerszintű helyelemzése érdekében.     
    3. Recency: A Recency számítása a vevő és a szervezet között történt utolsó tranzakciós tevékenység óta eltszámított napok száma alapján történik. A Recency nem veszi figyelembe a nem tranzakciós tevékenység jelzéseit, mint például az e-commerce böngészési tevékenység.    
    4. A kapcsolat hossza: A kapcsolat hosszának számítása a vevőrekord rendszerben való létrehozása óta eltszámlott napok száma alapján történik.     
    5. Élettartam értéke (L ALÁBBIAK): Az élettartam értékét a vevő által az összes Commerce értékesítési csatornában (POS, e-commerce és hívásközpont) elköltött teljes összeg alapján számítja ki a program.
    6. Gyakoriság szerint: a gyakoriság számítása a vevő és a szervezet között a tranzakciós tevékenység alapján történik. A gyakoriság nem veszi figyelembe a nem tranzakciós tevékenység jelzéseit, mint például az e-commerce böngészési tevékenység.

#### <a name="d-impression"></a>nap Benyomást
A megjelenítést úgy határozza meg a rendszer, hogy a termék vizuális megjelenítését az e-commerce rendszer határozza meg. Ha például egy e-commerce tevékenység a webhely kezdőlapjára ér, és egy felső értékesítési listamodulon belül egy gyermekterméket megtekint, és ugyanannak a gyermek terméknek a nézete is szerepel egy listamodul kivétében, ezek a műveletek két termékkel kapcsolatos problémaként számítanak. A nézetek a következő felületeken követik nyomon a terméknézeteket:
1. Listák (például javasolt, legjobb eladási, kiválasztó, trend)
2. Kosármodul
3. Keresési eredmények tárolója
4. Kategóriakeresési eredmény tárolója
    
A carousel modulban vagy az egyéni vizuális megjelenítésben megjelenített termékek nem számítanak bele a metrikusba.

A **Jelentések jelentés a következő** mérőszámokat tartalmazza:
1. Megjelenítések száma
    1. Laptípus és modul szerint: Az oldaltípus az e-commerce webhely egyes oldalaihoz meghatározott általános laptípus. A modultípus meghatározza annak az e-commerce vizuális modulnak a típusát, amelyen belül a termék megjelenik. Előfordulhat, hogy az oldalon és a modul vizuális megjelenítésén le kell ásni, hogy modul szerint tekintse meg a látójeleket.    
    2. Melléktermék    
    3. Bejelentkezett felhasználó állapota szerint    
    4. Dátum szerint
2. Visszajelzések és kattintások száma: a megjelenítésre való kattintás e-kereskedelmi ábrázolásként van meghatározva, amely egy termék-vizuális elemre kattint, amely jellemzően az adott termék részletes adatait tartalmazó lapra irányít.     
3. Úgy definiálja az átkattintási rátát, hogy a kattintások száma elosztva a kattintások összesített számával.

## <a name="install-commerce-analytics"></a>A Commerce analitikának telepítése

> [!NOTE]
> A commerce analitika előnézeti fázisban van az Egyesült Államok, Kanada, Egyesült Királyság, Európa, Dél-Kelet-Ázsia, Kelet-Ázsia, Ausztrália és Japán régióiban. Ha a környezet valamelyik régióban van, a Microsoft Dynamics Lifecycle Services (LCS) segítségével engedélyezheti a Commerce analitikát az adott környezetben. A Commerce analitikát csak akkor használhatja, ha [az Exportálás konfigurálása az Azure-adatokba való előfizetésben található](../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md).

### <a name="enable-and-configure-commerce-analytics"></a>Commerce Analytics engedélyezése és konfigurálása
A Commerce analitikához engedélyekre van szükség az erőforrások Azure-előfizetésben való létrehozásához, valamint engedélyekre az LCS-bővítmények telepítéséhez. Az alább részletezett lépések segítségével engedélyezheti és konfigurálhatja a Commerce analitikát.
1. [Az Előnézet űrlap elküldése Commerce analitikának (Előnézet)](#submit-the-preview-intake-form-for-commerce-analytics)
2. [Adatexport exportálásának engedélyezése és konfigurálása](#enable-and-configure-export-to-data-lake)
3. [Commerce Analytics (Preview) bővítmény engedélyezése és konfigurálása](#enable-and-configure-commerce-analytics-add-in)
4. [Tárolási fiók SAS-jogkivonatának](#generate-storage-account-sas-token) létrehozása
5. [Nézetek telepítési parancsfájljának Azure Synapse](#download-deployment-scripts-for-azure-synapse-views) letöltése
6. [A munkaterület telepítése és Azure Synapse](#install-and-configure-azure-synapse-workspace) konfigurálása.
7. [Telepítse Power BI a](#install-power-bi-template-app) sablonalkalmazást. 

### <a name="submit-the-preview-intake-form-for-commerce-analytics"></a>Az Előnézet űrlap elküldése a Commerce analitikának
Töltse ki és küldje el a [Commerce Analytics (Előnézet) megfelelő](https://forms.office.com/r/vW5VLJGXZ2) képernyőt. A kérés feldolgozásához legfeljebb három munkanapot adjon meg. A képernyő feldolgozása után a visszaigazoló e-mail meg lesz küldve a képernyőn megadott e-mail címre.

### <a name="enable-and-configure-export-to-data-lake"></a>Adatexportba való exportálás engedélyezése és konfigurálása
A Commerce Analitika a **Commerce HQ-adatokNak az Azure-adatokba történő exportálására, valamint az adatok új tartására az Adatelemzés szolgáltatáson** alapul. Mielőtt konfigurálja a Commerce analitikát, engedélyezze és konfigurálja az Export to DataSzolgáltatásokat szolgáltatást az Azure-adatokhoz történő exportálás konfigurálása című dokumentumban meghatározott **·** lépések [...](../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md) alapján. Az Exportálás az Adatokba **szolgáltatás** konfigurálásakor jegyezze fel a következő információkat. Ezt az információt a következő lépésekben kell megadnia.
1. A kulcs dns-neve és az alkalmazásazonosító és az alkalmazás titkos tárolójának titkos neve. A további tudnivalókat lásd [a Kulcskulcshoz hozzáadva kulcskulcshoz.](../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md#addsecrets)
2. Az Azure data Azure-példány tárolási fiókneve További tájékoztatás: [Create a Data Storage (Gen2) fiók létrehozása az előfizetésben.](../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md#createsubscription)

### <a name="enable-and-configure-commerce-analytics-add-in"></a>Commerce Analytics-bővítmény engedélyezése és konfigurálása
A Commerce Analytics bővítménynek az LCS-be való telepítéséhez környezeti rendszergazdának kell lennie az LCS-be az ön által használt környezetben.

A Commerce Analytics bővítmény konfigurálhoz a következő információkra lesz szüksége. 

|Mező | Információforrás| Példa|
|----|----|----|
|Azure AD Bérlőazonosító az Ön környezetéhez| A Azure AD bérlő azonosítója az Azure-portálon. Jelentkezzen be az **Azure-portálra,** és nyissa meg a **Azure Active Directory** szolgáltatást. Nyissa meg **a Tulajdonságok** lapot, és másolja az értéket a **Címtárazonosító** mezőbe.| 72f988bf-0000-0000-00000-2d7cd011db47|
|Kulcsának DNS-neve|Adja meg [...](#enable-and-configure-export-to-data-lake) kulcskulcsának DNS-nevét.| `https://contosod365datafeedpoc.vault.azure.net/`|
|Az alkalmazásazonosítót tartalmazó titkos fájl| Adja meg [az](#enable-and-configure-export-to-data-lake) alkalmazásazonosítót tároló titkos nevet. Ez az érték megegyezik az Adatexportfájlba **történő exportálás** bővítményének telepítésekor használt értékkel.|alkalmazás azonosítója|
|Az alkalmazás titkos titkos fájlja| Adja meg [az alkalmazás titkos](#enable-and-configure-export-to-data-lake) nevét. Ez az érték megegyezik az Adatexportfájlba **történő exportálás** bővítményének telepítésekor használt értékkel.| alkalmazás titkos kódja|

1. Jelentkezzen be a [Lifecycle Services](https://lcs.dynamics.com/) szolgáltatásba, és nyissa meg a környezetet.
2. A Környezet **lapon válassza a Környezet bővítmények** **·** lapot.
3. Válassza az Új bővítmény telepítése lehetőséget, majd a párbeszédpanelen válassza a **·** Commerce Analytics **(Előnézet)** lehetőséget. Ha a Commerce analitikát (Előnézet) nem szerepel a listán, győződjön meg arról, hogy csatlakozott a **·** Belső szoftverhez.
4. A beállítási bővítmény párbeszédpanelen adja meg a szükséges adatokat a **·** fenti táblázatban meghatározottak szerint.
5. Fogadja el az ajánlat feltételeit úgy, hogy bejel választja a jelölőnégyzetet, majd válassza a **Telepítés** lehetőséget.

A rendszer telepíti és konfigurálja a környezet Commerce analititika (Preview) szolgáltatást. A művelet eltarthat néhány percig. A telepítés és a konfigurálás befejezése után a Commerce Analytics (Előnézet) megjelenik a **·** Környezet **·** lapon, és a Telepítés állapota **Telepítve**.

### <a name="generate-storage-account-sas-token"></a>Tárolási fiók SAS-jogkivonatának létrehozása
> [!NOTE]
> A Commerce analitikának (előnézet) ismert korlátozása, hogy a SAS-token lejárata esetén a példány nem fér hozzá az Azure Synapse adathoz. A közös hozzáférési aláírás (SAS) token létrehozása során be kell állítania a szervezet biztonsági házirendje által engedélyezett maximális lejárati dátumot.

A SAS token lehetővé teszi külső entitások számára a tárolási fiókhoz való hozzáférést, adott jogosultságokkal, véges időmennyiségre vonatkozóan. Azure Synapse A <a0/1><a2/1><a2/aki a SAS tokent fogja használni az Azure-adatok alapadat-adataihoz való hozzáférésre. A SAS-token létrehozásához kövesse az alábbi lépéseket.
1. Menjen az Azure-portálnak az Adatexportálba való exportálás konfigurálása során létrehozott tárolási fiókjához – ezt az előfizetés **·**[adattárolási (Gen2) fiókjának létrehozása](../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md#createsubscription) részletezi.
2. Válassza a Megosztott hozzáférés aláírását a bal oldali Beállítások **·** ablakban, a tárolási **fiók** alatt.
3. Válassza a következő beállításokat a SAS-beállítások oldalon:

    | Beállítás neve | Beállítás értéke |
    |-------------|--------------|
    | Engedélyezett szolgáltatások | Blob **·** kiválasztása. |
    | Engedélyezett erőforrástípusok | Válassza ki **a** szolgáltatást, **a** tárolót és az **·** objektumot.|
    | Engedélyezett engedélyek | Válassza **az** Olvasás, az **·** **Írás, a** **Törlés, a** Lista, a Hozzáadás és a Létrehozás **·** **·** lehetőséget. |
    | Blobverzió-engedélyek | Válassza **a Verziók törlésének lehetővé** lehetőséget. |
    | Kezdő és lejárati dátum/idő | Ha szükséges, állítsa be a SAS-token záró dátumát és időpontját. |
    | Engedélyezett IP-címek | Hagyja üresen. |
    | Engedélyezett protokollok | Csak **HTTPS** kiválasztása. |
    | Preferált útvonalszint | Válassza **az Alap lehetőséget (alapértelmezett).** |
    | Aláírási kulcs | Ha **szükséges, válassza az 1.** vagy a **·** 2. kulcsot. |

4. Válassza **a SAS létrehozása és a kapcsolati karakterlánc** kiválasztását.
5. A SAS token szövegmezőjében található érték **·** másolása egy szövegszerkesztőbe, például jegyzettömbbe.

### <a name="download-deployment-scripts-for-azure-synapse-views"></a>Nézetek telepítési parancsfájljának Azure Synapse letöltése
Ahhoz, hogy a munkaterületen létre tudja hozni és közzéteheti a szükséges nézeteket, le kell töltenie és végre Azure Synapse kell hajtania egy parancsfájlhalmazt. A parancsfájlok letöltéséhez kövesse az alábbi lépéseket.
1. Menjen a [microsoft/Dynamics365Commerce.SolutionsHub](https://github.com/microsoft/Dynamics365Commerce.Solutions) repo webhelyre. A parancsfájlok a repo-ban érhetők el.
2. Ha a parancsfájlokat le kell tölteni a helyi gépre, akkor vagy a repo megkésülését, vagy a repo letöltését zip fájlként lehet letölteni.

### <a name="install-and-configure-azure-synapse-workspace"></a>Munkaterület telepítése és Azure Synapse konfigurálása
Munkaterület telepítéséhez és Azure Synapse konfiguráláséhez kövesse az alábbi lépéseket.
1. Az Azure-előfizetés munkaterületét a Gyorsindítás: Szintaktikás munkaterület létrehozása című Azure Synapse [lépésekkel](/azure/synapse-analytics/quickstart-create-workspace) telepítheti.
2. Nyissa meg a SetupSynapse.sql parancsfájlt a Jegyzettömbben abból a helyi gépmappból, ahol a Dynamics365Commerce.Solutions repo le van állítva. A további tudnivalókat [lásd: Nézetek telepítési parancsfájljának Azure Synapse](#download-deployment-scripts-for-azure-synapse-views) letöltése. A parancsfájl a "/Pipeline/CommerceAnalyticsSynapse/" mappa alatt lesz. A forgatókönyv szerkesztése a helyőrző szövegnek az alábbi értékekkel való lecseréléhez.

   | Helyőrző szöveg | Helyettesítő érték |
   |------------------|-------------------|
   | placeholder_storageaccount | Felülírja annak a tárolási fióknak a nevét, amely az Adattárolóba exportálás konfigurálása során jött létre, az előfizetés **·**[adattároló (Gen2) létrehozása című számlájában](../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md#createsubscription) körvonalazva. |
   | <a name="phContainer"></a> placeholder_container | Az Adattárolóba való exportálás LCS-ben történt telepítése után le kell cserélnie azt a tárolótárolót, amely az Azure data Data Instance példányban létre lett **·** hozva. A tároló nevének kitárolása előtt a tárolási fiók böngészése érdekében az Azure portal Tárolás intézőjét kell használnia. |
   | placeholder_sastoken | Le kell cserélnie a Tárolószámla SAS betárolási jogkivonatában másolt [SAS-tokenre.](#generate-storage-account-sas-token) Mindenképpen távolítsa el a **"?" et a SAS token értékének** elején. |
   | <a name="phUserPwd"></a> placeholder_password | Csere a kiválasztott erős jelszóval. Feljegyzés a jelszóról. Ez a jelszó lesz a parancsfájl által létrehozott új "reportreadonlyuser" fiók jelszava. **ITT NE adja meg** az "sqladminuser" fiók jelszavát.  |

3. Ugrás az Azure Synapse Új munkaterületre az Azure portal webhelyen. Válassza az Áttekintés lapon **a Szintaktáz studio** megnyitása **·** lehetőséget.
4. A fenti 2. lépésben frissített `SetupSynapse.sql` tartalom másolása. Az Azure Portal Szintakt studio szolgáltatásban válassza az Új > **SQL-parancsfájlt.** A tartalom beillesztése az SQL-parancsfájl-szerkesztőbe a Szintapse Studio alkalmazásba.
5. Ellenőrizze, **hogy az Adatbázis használata alap** **van-e** állítva. A parancsfájl végrehajtásához válassza a **·** Futtatás lehetőséget.
6. Várja meg, amíg a parancsfájl befejeződik. A parancsfájl létrehoz egy Commerce-elemzési adatbázist, hitelesítő adatokat az Azure-adatokhoz való hozzáféréshez, valamint egy csak olvasható felhasználói fiókot, amelyet a példányhoz Power BI való kapcsolódáskor Azure Synapse használ.
7. A helyi számítógépen nyissa meg a PowerShellt rendszergazdai módban. Menjen a "/Pipeline/CommerceAnalyticsSynapse/" mappához, amely a Dynamics365Commerce.Solutions repo mappában található, a nézetek telepítési parancsfájljainak letöltése című témakörben leírt [Azure Synapse](#download-deployment-scripts-for-azure-synapse-views) módon.
8. Állítsa be a PowerShell végrehajtási házirendet a PowerShell ablak következő parancsának futtatásával:

   ```powershell
   Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass
   ```
   
9. Telepítse az SQL Server PowerShell modult a PowerShell ablak következő parancsának futtatásával:

   ```powershell
   Install-Module sqlserver
   ```
   
   > [!NOTE]
   > Ha már telepítve van az SQL Server modul, kihagyhatja ezt a lépést. A modul telepítése során előfordulhat, hogy a rendszer rákérdez a szolgáltató NuGet telepítésére. A szolgáltató telepítésének a folytatáshoz nyomja meg **az Y** NuGet billentyűt. Üzenetet kaphat arról is, hogy modulokat telepít egy nem megbízható tárházból. A **telepítés folytatásához nyomja meg az Y** billentyűt. A parancsmag futtatásával meg is megbízhat a `Set-PSRepository``PSGallery` tárházban.
   
10. Tegye közzé a nézeteket a PowerShell ablakban a következő parancs Azure Synapse futtatásával:

    ```powershell
    .\PublishSynapseViews.ps1 -serverName SERVER_NAME -password PASSWORD -storageAccount STORAGE_ACCOUNT -containerName CONTAINER_NAME -datarootpath DATA_ROOT_PATH
    ```
    
    A parancs helyőrző értékeinek cseréje a következőképpen:
    
    | Helyőrző értéke | Helyettesítő érték |
    |-------------------|-------------------|
    | SERVER_NAME | Csere a kiszolgáló nélküli Azure Synapse SQL-végpont nevével. Ez az érték az Azure portal munkaterületének Áttekintés Azure Synapse **lapján érhető** el. |
    | JELSZÓ | Felülírás az sqladminuser jelszavával. |
    | STORAGE_ACCOUNT | Le kell cserélnie a Azure-adatkapcsolatok tárolási fiókjának a nevére. |
    | CONTAINER_NAME | Felülírja a Tároló által az **Adatexportmal létrehozott tároló** nevét. A név annak a tárolónak a neve, amely a fenti placeholder_container meg van [...](#install-and-configure-azure-synapse-workspace) adva. |
    | DATA_ROOT_PATH | Csere az összes adatot tartalmazó tároló alatti mappanévre. |

    > [!NOTE]
    > A tárolási fiók neve, a tároló neve és az adatgyökér elérési útja az Azure portal webhelyen található, az Azure tárolási böngészőben, amely az Azure Azure-adattároló tárolási fiókját használja.

11. Várja meg, amíg a parancsfájl befejeződik. A parancsfájl SQL-nézeteket hoz létre a Azure Synapse kiszolgáló nélküli SQL-példányban.

### <a name="install-power-bi-template-app"></a>Sablonalkalmazás Power BI telepítése
Az alábbi lépésekkel lehet telepíteni a Power BI Commerce analititika sablonalkalmazást.
1. Jelentkezzen be a [Power BI](https://powerbi.microsoft.com/) portálra saját szervezetazonosítója segítségével.
2. A következőre telepítheti a Commerce Power BI Analitikás sablonalkalmazást: [https://aka.ms/cdireport-installapp](https://aka.ms/cdireport-installapp) Lehet, hogy figyelmeztetést kap arról, hogy az alkalmazás nincs felsorolva a AppSource következőn: Válassza a **Telepítés** parancsot.
3. Ha az alkalmazást első alkalommal telepíti, ugorjon az 5. lépésre. Ha már telepítette ezt az alkalmazást, a következő beállítások jelennek meg az alkalmazás frissítéséhez.
   1. A munkaterület és az alkalmazás frissítése: Ez a beállítás frissíti a meglévő sablonalkalmazást, és felülírja az alkalmazásbeállításokat, például az alkalmazáspéldány nevét és az engedély-konfigurációkat.
   2. Munkaterület tartalmának frissítése az alkalmazás frissítése nélkül: Ez a beállítás frissíti a meglévő sablonalkalmazást, és megtartja az alkalmazás beállításait. Ez az **ajánlott beállítás az** alkalmazásfrissítések esetén.
   3. Telepítse az alkalmazás egy másik példányát egy új munkaterületre: ezzel a beállítással új másolatot hoz létre az alkalmazásról egy új munkaterületre, amely a felhasználó számára létrejön. A meglévő munkaterület sértetlenül maradt.      
4. Válassza ki a fenti beállítások valamelyikét, majd válassza a **Telepítés** lehetőséget.
5. A telepített alkalmazást úgy nyithatja meg, hogy kijelöli az Alkalmazások menüelemet **·** a bal oldali ablakban, majd kiválasztja az alkalmazást.
6. Az alkalmazás az adatforráshoz való kapcsolása a Csatlakozás lehetőség **választásával** Ha nem az első alkalommal telepíti az alkalmazást, válassza az Adatok összekapcsolása lehetőséget a sárga **·** információs sávon.
7. Adja meg a következő paraméterértékeket:

   | Paraméter neve | Érték |
   |----------------|-------|
   | Kiszolgáló       | Adja meg annak a kiszolgáló nélküli SQL-végpontnak a nevét, amely a Munkaterület telepítése és konfigurálása szakaszban Azure Synapse [létre van Azure Synapse](#install-and-configure-azure-synapse-workspace) hozva. Ez az érték az Azure portal áttekintési lapján Azure Synapse **·** található. |
   | Adatbázis | Adja meg a "CommerceAnalytics" értéket.
   | Nyelv | Érték kiválasztása a legördülő listából. A beállítás a honosított termék- és kategórianevekhez használható. Az érték megkülönbözteti a kis- és a nagybetűket. |
   | Dátumtartomány | Érték kiválasztása a legördülő listából. A program a kiválasztott számú hónap adatait importálja az Power BI adatkészletbe. Az adatkészlet mérete és a szinkronizáláshoz szükséges idő a kiválasztott értéktől függ. |

8. Válassza ki **Következő** lehetőséget. A program megkérdezi, hogy meg kell-e adnia az SQL-adatbázishoz való csatlakozás hitelesítő Azure Synapse adatait. Adja meg a következő értékeket:

   | Paraméter neve | Érték |
   |----------------|-------|
   |Hitelesítési módszer|Válassza az **Alap** lehetőséget.|
   |Felhasználónév| Írja be, hogy "reportreadonlyuser".|
   |Jelszó|Adja meg azt az értéket, amely a [SetupSynapse.sql placeholder_password parancsfájlban található](#install-and-configure-azure-synapse-workspace) adatbázis cseréjekor használatos. Ez a reportreadonlyuser fiók jelszava.| 

9. Válassza ki **a bejelentkezést és a** csatlakozást.
10. Várjon, amíg az adatkészlet frissül. Ezután az Alkalmazás szerkesztése ikonra kattintva **megjelenik az alkalmazás** munkaterülete. A munkaterületen ellenőrizheti az adatkészlet frissítési állapotát. Beállíthatja az adathalmaz automatikus frissítési ütemezését, kezelheti az engedélyeket, és átnevezheti az alkalmazáspéldányt.

### <a name="privacy"></a>Adatvédelem
Az Ön személyes adatainak védelme fontos a számunkra. Az adatvédelemmel kapcsolatos további tudnivalókért olvassa el [adatvédelmi](https://go.microsoft.com/fwlink/?LinkId=521839) nyilatkozatunkat.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
