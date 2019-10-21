---
title: A felhasználói élmény testreszabása
description: Ez a témakör bemutatja, hogyan lehet személyre szabni az alkalmazást.
author: jasongre
manager: AnnBe
ms.date: 06/11/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserSetup, DefaultDashboard
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 62363
ms.assetid: 57b445d7-3e9e-4228-8728-f63b9dbd77a3
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: edf698b12f2d0bcb6035bc644537cf9ca2bb87c9
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/27/2019
ms.locfileid: "2190902"
---
# <a name="personalize-the-user-experience"></a>A felhasználói élmény testreszabása

[!include [banner](../includes/banner.md)]

Ez a témakör bemutatja, hogyan lehet személyre szabni az alkalmazást.

A személyre szabások három alapvető osztályba sorolhatók.

- Személyes beállítások egy beállítási lapon. Példák: a stílus és az időzóna.
- Személyes beállítások a lap használatához kapcsolódva, ezek az *implicit* személyes beállítások. Például a rendszer nyomon követi a rácsoszlopok szélességét, ha ezt beállítja, vagy a gyorslapok összecsukott/kibontott állapotát.
- Személyes beállítások, amelyeket a felhasználó azért teszi, hogy módosítsa az oldal megjelenését azzal, hogy megváltoztatja az oldal elemeinek kinézetét, sokszor valamilyen interaktív személyre szabási móddal. Ezek a testreszabások az *explicit* testreszabások. Például a felhasználó hozzáadhat, elrejthet vagy átrendezhet lapelemeket.

Bármilyen testreszabás csak arra a felhasználóra érvényes, aki megadta őket, és függetlenek a személyre szabás típusától vagy attól, hogy a felhasználó milyen vállalattal kommunikál. Ha egy felhasználó az oldalon módosításokat hajt végre, az nem módosítja a rendszerben más felhasználók kezelési felületét.

## <a name="system-wide-options-for-the-current-user"></a>Az egész rendszerre érvényes beállítások az aktuális felhasználó számára

A **Felhasználói beállítások** lap tartalmaz több rendszerszintű beállítást az aktuális felhasználóra. A **Felhasználói beállítások** oldal megnyitásához válassza a **Beállítások** menüt (fogaskerék szimbólum) a navigációs sávon, és jelölje be a **Felhasználói beállításokat**. A **Felhasználói beállítások** oldalhoz négy lap tartozik különböző felhasználói beállításokkal:

- **Vizuális** – A színtéma kiválasztása és az oldalelemek alapértelmezett méretének beállítása.
- **Beállítások** – Válassza ki a rendszer megnyitásakor mindig használt alapértelmezett értékeket. Az értékek között található a vállalat, a kezdőlap és az alapértelmezett megjelenítési/szerkesztési mód. (A megjelenítési/szerkesztési mód határozza meg, hogy egy oldalt zárolt vagy megnyitott a szerkesztésre, minden alkalommal, amikor megnyitja.) Ez a lap a nyelv, az időzóna és a dátum, az idő- és számformátum beállításait is lehetővé teszi. Végül ezen a lapon több vegyes beállítás található, amelyek az egyes kiadások esetében eltérők lehetnek.
- **Fiók:** – Itt adhatja meg a felhasználónevet és más fiókhoz kapcsolódó beállításokat.
- **Munkafolyamat** – Válassza ki a munkafolyamattal kapcsolatos beállításokat.

A felhasználói beállítások módosításán túl, megtekintheti és törlheti is a használati adatokat és személyreszabásokat **Használati adatok** gombbal. A program menti a felhasználói beállítások nagy részét, így a rendszer használata a jövőben kényelmesebb lesz. A **Személyre szabás** lap segítségével tekintheti meg és kezelheti a személyes módosításokat, amelyeket végrehajtott a lapokon a rendszerben. Funkcióbuborékok – előugró ablakok, amelyek új funkciókat vezetnek be a rendszerben (26-os platform frissítéstől érhető el) is visszaállíthatók erről a lapról, hogy újra figyelmeztetést kapjon a korábban már használt funkciókról.  

## <a name="implicit-personalizations"></a>Implicit testreszabás

Az implicit személyes beállítások olyan személyes beállítások, amelyeket olyan vezérlőkkel hajt végre, amelyek megjegyzik az elemek aktuális láthatósági állapotát.

- **Rácsoszlopok:** – Megadhatja egy oszlop szélességét a listában, ha az oszlop fejlécén található méretező sávot balra vagy jobbra húzza a kívánt oszlopszélességig. Az alkalmazás tárolja az oszlop beállított szélességét. Átméretezi az oszlop szélességét minden alkalommal, amikor megnyitja a rácsot tartalmazó lapot.
- **Gyorslapok** – Néhány lapon kibontható szakaszok vannak, amelyeket *Gyorslapoknak* hívunk. Az alkalmazás tárolja a már kibontott vagy összecsukott gyorslapok adatait. Minden alkalommal, amikor visszatér a lapra, ugyanazon gyorslap ki lesz bontva és össze lesz csukva, a lappal folytatott utolsó kommunikációt alapján. Bizonyos esetekben a gyorslap összecsukása javíthatja a teljesítményt, mivel az alkalmazásnak nem kell betöltenie annak a gyorslapnak az információit egészen addig, amíg a gyorslapot nem bontjuk ki. Amint később a témakör elmagyarázza, a lapon módosítható a gyorslapok sorrendje.
- **Adatterületek** – Néhány oldal tartalmaz egy *Adatterület* panel nevű szakaszt. Ez az ablak csak olvasható információkat tartalmaz az aktuális oldal tartalmáról. Az adatterület-panel minden szakaszát *adatterületnek* hívjuk. El lehet rejteni vagy a teljes adatterület panel megjelenítését, és akkor is kibonthatók és összecsukhatók az egyes adatterületek. Az alkalmazás tárolja a beállításokat. Ha ezt követően visszatér a lapra, az adatterület panel és az egyes adatterületek állapota visszaáll, a lap utolsó kommunikációja alapján. Bizonyos esetekben az adatterület összecsukása javíthatja a teljesítményt, mivel az alkalmazásnak nem kell betöltenie annak az adatterületnek az információit egészen addig, amíg az adatterületet nem bontjuk ki.
- **Műveleti ablaktábla** – A *Műveleti ablak* a legtöbb oldal tetején jelenik meg. A műveleti ablak gombjaival számos műveleteket hajthat végre az aktuális lapon. Ezek a gombok gyakran a lapokon vannak csoportosítva. A teljes műveletpanel lehet nyitott, hogy alapértelmezés szerint összecsukva is. Ezt követően a lap következő megnyitásakor az alkalmazás visszaállítja a műveleti ablak rögzített állapotát. Ha a műveleti ablak nyitva van rögzítve, az alkalmazás is látható a legutóbb használt műveletek lapja.
- **QuickFilters** – A *Gyorsszűrő* sok rács felett jelenik meg. A Gyorsszűrő lehetővé teszi a rács a kiválasztott oszlop alapján szűrését. Az alkalmazás tárolja az oszlopot, amelynek alapján szűrt. Ezt követően, a rácsot tartalmazó lap következő megnyitásakor a rács szűrve lesz ugyanazon oszlopra. Azonban ezután szűrni lehet egy másik oszlopra a rácsot.
- **Oszlop fejléce szűrők** – A rács az *oOszlop fejléce szűrők* segítségével szűrésekor módosíthatja a szűrési operátort a megtalálni a kívánt adatok szerint. Például módosíthatja a kezelőt a **kezdődik** lehetőségről a **pontosan** lehetőségre. Oszlop fejléce szűrő használatakor és a szűrési operátor módosításakor, az alkalmazás mindig tárolja a módosítást. Majd visszaállítja szűrési operátort ha legközelebb szűrhetők az oszlopra.
- **Navigációs ablak** – A *navigációs ablak* megnyitásához válassza ki a **Menü** gombot bármely lap bal oldali ablakában. (A **Menü** gomb másik neve *Hamburg*, *Hamburg menü*, vagy *Hamburg gomb*.) Rögzítheti a navigációs ablak megnyitásához, vagy alapértelmezés szerint összecsukva tárolhatja. Után rögzítettet a navigációs ablakot nyitva, az alkalmazás nyitva tartja mindaddig, amíg összecsukja.

## <a name="explicit-personalizations"></a>Explicit testreszabás

A személyek és vállalatok számára eltérőek a legfontosabb adatok, vagy amelyeket nem igényelnek az üzleti tevékenységhez. Személyre szabhatja adatainak megrendelését és kezelését. Megadhatja azt is, hogy bizonyos adatokat el kell rejteni. Ezek a funkciók kulcsfontosságúak a személyes és produktív használati élményre, és példák az explicit személyes beállításokra. Az explicit személyre szabások olyan személyre szabások, amelyeket kifejezetten azzal a szándékkal hajtunk végre, hogy megváltoztassuk egy elem vagy lap megjelenését vagy működését.

### <a name="shortcut-menu-options"></a>Gyorsbillentyű menüpontok

Helyi menü segítségével néhány kifejezetten átállítása lap jobb per igényeinek, vagy a vállalat követelményeinek. (Más néven a helyi menü van egy *helyi menü* vagy *helyi menüje*.)

Néhány, a szokásos és a fontos változtatást laphoz végrehajtott érhetők el közvetlenül, a helyi menü Beállítások pontjára. Ha például a 17. platformfrissítéstől kezdődően szeretne felvenni vagy elrejteni oszlopokat egy rácsban, kattintson a jobb gombbal a rács oszlopfejlécére, és adja meg az **Oszlop hozzáadása** vagy **Oszlop elrejtése** lehetőséget.

Ezenkívül a legtöbb alaptípusok explicit személyre szabása akkor érhetők el, kattintson a jobb gombbal egy elemre, és válassza a **Személyre szabást**. (Megjegyzendő, hogy az oldalon nem minden elem szabható személyre.) Ha a személyre szabásnak ezt a módszerét választja, akkor megjelenik az elem tulajdonság ablaka.

![Egy elem tulajdonságainak testreszabása](./media/personalization-element-properties.png)

A tulajdonságablak segítségével egy elem testreszabása a következőképpen történik:

- Az elem címkéje módosítása.
- Az elem elrejtése, így az nem jelenik meg az oldalon. A mező adatait nem törölték vagy módosították. Az adatok csak nem jelennek meg az oldalon többé.
- Tartalmazza a gyorslap összefoglaló szakasz információit (ha az elem egy gyorslapon van).
- A mező kihagyása, amikor megnyomja a tabulátort az oldalon, a mezők között.
- A szerkesztett megakadályozása adatok mezőjében (bármely rekord).

A tulajdonságablak szerepeltethet egyéb személyre szabása funkciókat az elemtől függően. Például egy csempe a tulajdonságablak előfordulhat, hogy lehetővé teszik a támogatják ezt a csempét az irányítópultra, és a tulajdonságablak egy irányítópult előfordulhat, hogy lehetővé teszik, hogy irányítópult az új munkaterület létrehozása.

### <a name="the-personalization-toolbar"></a>Személyre szabási eszköztár

Ha több módosítást is szeretne végrehajtani egy lapon, illetve olyan módosításokat szeretne végrehajtani, amelyek nem érhetők el más mechanizmusokon keresztül (például az elemek újrarendezése), használhatja a **Személyre szabás** eszköztárat. Megnyitásához a **Személyre szabása** eszköztárnak válassza **Testreszabása ezen a képernyőn** a tulajdonságablak egy elemet. Is kiválaszthat **testreszabása ezen a képernyőn** a a **személyre szabása** csoportosításhoz a **lehetőségek** minden egyes oldal műveletpanel lapján.

[![Személyre szabási eszköztár](./media/restyledPersonalizationToolbar.png)](./media/restyledPersonalizationToolbar.png)

#### <a name="navigating-the-page"></a>Navigálás a lapon

Az oldalon való navigálás lehetősége a **Személyre szabási eszköztár** megnyitása közben a futó platformtól függ.

- A 19. platformfrissítés előtt amikor a **Személyre szabás** eszköztár nyitva van, a lap írásvédett (nem lehet beírni semmit), és nem interaktív (csak a lap látható elemein végezhet módosításokat). Ha egy összecsukott panel vagy egy másik lap elemei között szeretne változtatni, be kell csuknia a **Személyre szabás** eszköztárát, ki kell bontania egy panelt, vagy át kell váltania a kívánt lapra, majd ismét meg kell nyitnia a **Személyre szabás** eszköztárát.

- A 19. platformfrissítést követően ha a **Személyre szabás** eszköztár nyitva van, akkor a lap továbbra is írásvédett, de sokkal interaktívabb. Kibővítheti vagy összecsukhatja az adatterületet, válthat a lapok között, továbbá kibonthatja vagy összecsukhatja a paneleket, miközben a **Személyre szabás** eszköztár nyitva van – mindezt ugyanúgy végezheti, mintha a lapon tenné. Ha személyre szabott módosítást szeretne alkalmazni egy összecsukható panelre vagy lapra (például egy gyorslap elrejtése), akkor megjelenik az összecsukható panel vagy lap mellett a gomb a billentyűzet kiemelésével, illetve amikor fölé húzza az egérmutatót.

#### <a name="personalization-tools"></a>Személyre szabási eszközök

A következő eszközök érhetők el a **Személyre szabása** eszköztáron:

- A **Kijelölés** eszközzel egy elemet kijelölve megnyithat egy párbeszédablakot, és módosíthatja az elem tulajdonságait. A **Kijelölés** eszközzel egy elemet kijelölve megnyithat egy párbeszédablakot, és azon módosíthatja az elem tulajdonságait, amelyet ki kell jelölni. Amikor kiválaszt egy elemet, az elem tulajdonságok ablaka jelenik meg, és ezen az elem bármilyen tulajdonsága módosítható. Megismételheti a folyamatot más elemekkel is, amelyek a lapon testre szabhatók. Azonban az egyes elemek használata miatt az alkalmazás nem enged módosítani bizonyos tulajdonságaikat. Ezért amikor kiválaszt egy elemet, jelenhet meg, hogy néhány tulajdonsága nem módosítható. Kötelező mezőt például nem tud elrejteni.
- Használja az **Áthelyezés** eszközt, ha egy elemet ki akar jelölni és az elemek jelenlegi csoportján belül egy másik helyre szeretné áthelyezni. (A szülőcsoporton kívülre nem helyezhető át egy elem). Válassza ki az **Áthelyezése** eszközt, és válassza ki az elem áthelyezése. Amikor kiválaszt egy elemet, az alkalmazás a lap ellenőrzésével meghatározza, ha az elemet át lehet helyezni. Ezután létrehozza a „lerakási zónákat”. Az aktuális csoportban az elem húzásakor minden „lerakási zónák” mellett a terület, ahová az elem húzható színes, félkövér sorként jelenik meg.
- Válassza ki az **Elrejtés** eszközt egy elem és elrejtéséhez a lapon. Válassza ki az **Elrejtés** eszközt, és válassza ki az elrejtendő elemet. Ha bejelöli az **Elrejtése** eszközt, minden éppen rejtett elem látható lesz, és árnyékolt tárolóban jelennek meg. Ezután megszüntetheti az elrejtésüket. Válassza ki a **Kijelölés** eszközt, hogy lássa, hogy fog kinézni az oldal a kiválasztott elemek elrejtésével.

    - A 18. platformfrissítéstől kezdődően elrejtheti a kötelező mezőket és a kötelező mezőket tartalmazó paneleket. Lehetővé teszi, hogy egyszerűsített élményt hozzon létre, ahol az üzleti logika által alapértelmezett kötelező mezők nem jelennek meg. Az elrejtett kötelező mezők ideiglenesen szintén láthatók, amennyiben üresek egy mentés megkísérlése során.

- Használja az **Összegzés** eszközt, ha azt szeretné, hogy az elem a gyorslap összesítő lapján található legyen. Az Összegzés eszköz csak olyan mezőkre érvényes, amelyek a gyorslap szakaszon vannak. Ha bejelöli a **Összegzés** eszközt, összesítő mezők szerepelnek az árnyékolt tároló bejelölt összes mezőt. Interaktívan mezők felvétele az összesítő gyorslapre, és a mezők eltávolítása a gyorslap összegző mezőinek a kiválasztásával.
- Válassza ki a **Kihagyás** eszközt egy elem eltávolítására az oldal billentyűparancs-sorozatából Ha bejelöli a **Kihagyás** eszközt, minden éppen kihagyott elem látható lesz, és árnyékolt tárolóban jelennek meg. Ezt követően újra a lapsorozat részévé tehetők.
- Válassza ki a **Szerkesztés** eszközt, ha egy elemet Szerkeszthető vagy Nem szerkeszthető állapotúra akar állítani. Ha bejelöli a **Szerkesztés** eszközt, minden éppen nem szerkeszthető elem látható lesz, és árnyékolt tárolóban jelennek meg. Ezután újra szerkeszthetővé tehetők. Vegye figyelembe, hogy egyes mezők kötelezőek, és nem tehetők zárolttá. Lakat szimbólum jelenik meg az ilyen mezők mellett.
- Használja a **Beszúrás** gombot a beszúrható elemek listájának megtekintéséhez egy oldalon.

    - Válassza ki a **Mező** eszközt a **Beszúrás** alatt mező felvételéhez a lapra. Használata esetén a **Mező** eszköz, csak azokat a mezőket, amelyek részei a oldaldefiníciót, de jelenleg a lapon nem látható, amelyet hozzáadhat. Új mezők, amelyek nem részei az aktuális oldaldefiníciónak, létrehozásával kapcsolatos további tudnivalókat lásd: [egyéni mezők](user-defined-fields.md). Miután kiválasztotta a **Mező** eszközt, először válasszon adott csoportot vagy terület, ahová mező hozzáadását szeretné. A kijelölt csoporttal vagy területtel kapcsolatos mezők listája egy párbeszédpanelen jelenik meg. A párbeszédpanelen válasszon hozzáadandó mezőket, majd a **Beszúrás** lehetőséget. Korábban hozzáadott mező eltávolításához meg kell ismételni a folyamatot, de a mező a párbeszédpanelen ne legyen kijelölve.
    - Válassza ki a **PowerApp** eszközt a **Beszúrás** alatt a lapba a Microsoft PowerApps használatával létrehozott alkalmazást beágyazni. A PowerApps alkalmazás beágyazásával a lapba kapcsolatos részletes tudnivalókat lásd: [PowerApps beágyazása](embed-power-apps.md).

- Válassza ki a **Kezelés** gombot az aktuális oldal testreszabásához kapcsolódó beállítások listájának megjelenítéséhez.

    - Válassza az **Alapértelmezett** gombot az alapértelmezett, telepítési beállítások visszaállításához. Az aktuális oldal testreszabott beállításai törlődnek. Nincs visszavonás művelet. Ezért használja ezt a lehetőséget, ha biztos benne, hogy kívánja az oldal alaphelyzetbe állítását.
    - Válassza az **Importálás** lehetőséget, hogy egy korábban ön vagy más által létrehozott testreszabási fájlból töltsön be testreszabási beállításokat ehhez az oldalhoz. A jelenlegi személyes beállítások helyére kerülnek az oldal személyre szabások a kijelölt fájlból.
    - Válasszon **Exportálás** a személyes lap beállítások mentéséhez egy fájlba. A személyes beállítások megoszthatja más felhasználókkal. Ezeknek a felhasználóknak csak a lap személyes beállításokat tartalmazó fájlt kell importálni.

- Válassza ki a **Bezár** gombot a **Személyre szabás** eszköztár bezárásához és ahhoz, hogy az oldal visszatérjen korábbi interaktív állapotába.

Ha a **Személyre szabás** eszköztár használt, a mentési műveletek implicitek. A személyes beállítások azonnal érvénybe létnek, és nem kell választani a **Mentés** gombot. Bizonyos esetekben látható egy lakat ikon az elem mellett, amikor kiválaszt egy eszközt. Ez a szimbólum azt jelzi, hogy nem módosíthatók a kijelölt eszközzel kapcsolatos az elem tulajdonságait, mert tulajdonságokhoz módosításai megakadályozza, hogy a lap megfelelően működik-e.

### <a name="adding-a-tile-list-or-link-to-a-workspace"></a>Csempe vagy lista vagy hivatkozás hozzáadása a munkaterülethez

Egyes listákat tartalmazó oldalaknál egy további személyre szabás szolgáltatás érhető el. A **Hozzáadása munkaterülethez** gomb a **Személyre szabás** csoportban a **Beállítások** lapján a műveleti ablaknak lehetővé teszi az aktuális lista adatait egy adott munkaterületen megjelenítését. Szűrten és rendezetten jelenítheti meg az adatokat a munkaterületen, vagy az alapértelmezett nézetet is megjelenítheti. Megadhatja azt is, hogy az információ megjelenjen-e a munkaterületen listaként, összegző csempeként megjelenítve az elemek számát a listában, vagy hivatkozásként.

[![Hozzáadás munkaterületenként](./media/personalization-addtoworkspace.png)](./media/personalization-addtoworkspace.png)

- Lista hozzáadásához a munkaterülethez, először rendezni és szűrni kell a listát a lapon, hogy az adatok a munkaterületen megjeleníteni kívánt módon jelenjenek meg. Ezután válassza a **Hozzáadása munkaterülethez** lehetőséget. Válassza ki a munkaterületez, majd kattintson a **Prezentáció** mezőben a **Lista** elemre. Miután kijelölte **Konfigurálást**, megjelenik egy párbeszédpanel, ahol kiválaszthatja az oszlopok, amelyek jelenjenek meg a listában a munkaterületen. Megadhatja a munkaterületen a listához használandó címkét.
- A munkaterület címének hozzáadásához először szűrnie kell a listát az oldalon, hogy az összesíteni kívánt adatokat megjelenítse (vagy azokat, amikhez gyors elérést szeretne). Ezután válassza a **Hozzáadása munkaterülethez** lehetőséget. Válassza ki a munkaterületez, majd kattintson a **Prezentáció** mezőben a **Cím** elemre. Miután kijelölte a **Konfigurálást**, megjelenik egy párbeszédpanel, ahol megadhatja a munkaterületen csempe használandó címkéjét. Megadhatja azt is, hogy a csempén kell-e egy számának megjelennie. Miután a csempe hozzá van rendelve a munkaterülethez, választhat az aktuális lap megnyitása a munkaterület és a csempe társított szűrt listájának megtekintéséhez.
- Hivatkozás hozzáadásához egy munkaterülethez, először a terméklista szűrése az oldalon, hogy az Ön érdeklő adatokat mutassa. Ezután válassza a **Hozzáadása munkaterülethez** lehetőséget. Válassza ki a munkaterületez, majd kattintson a **Prezentáció** mezőben a **Hivatkozás** elemre. Miután kijelölte a **Konfigurálást**, megjelenik egy párbeszédpanel, ahol megadhatja a hivatkozáson használandó címkét. Megadhat címkét az új szakaszhoz, amely ezt a hivatkozást fogja tartalmazni.

Miután a lista, a csempe vagy a hivatkozás egy munkaterülethez hozzá lett adva, a munkaterület megnyitása, és az elemeinek átrendezése, ahogyan szeretné.

### <a name="adding-a-summary-from-a-workspace-to-a-dashboard"></a>Összegzés hozzáadása a munkaterületről az irányítópultba

Néhány munkaterület tartalmaz számlálási csempét (vagyis számot tartalmazó csempét), és lehetséges, hogy ezeket is meg szeretné jeleníteni az irányítópulton. A munkaterületen kattintson jobb gombbal egy számozott csempére, majd kattintson a **Személyes beállítások** menüpontra. Ezután válassza a csempe tulajdonságai ablakban: **Kitűzés az irányítópultra**. Ha a következő alkalommal megnyitja a kiválasztott irányítópultot (vagy frissíti az oldalt), láthatja a számot a munkaterület navigációs csempéje alatt az irányítópulton. Kiválaszthatja, hogy a számláló közvetlenül az adatokhoz menjen, amelyeket bemutat.

### <a name="personalizing-your-dashboard"></a>Az irányítópult személyre szabása

Az irányítópult legtöbbször az első oldal, amelyet az alkalmazás megnyitásakor lát. Testre szabhatja az irányítópultot, hogy csak a megtekinteni kívánt munkaterület lapokat mutassa. A paneleket átrendezheti is, hogy a megadott sorrendben szeretné láthatják őket, a munkaterület navigációs lapok átnevezése és hozzáadása egy teljesen új munkaterület nevet.

Az irányítópult testreszabásához kattintson a jobb gombbal bármelyik csempe, és adja meg **Személyre szabás** elemet a csempe tulajdonság ablak megnyitásához.

- Ha azt szeretné, vagy nevezze át vagy rejtse el a kijelölt csempét, végezhet módosítást közvetlenül a tulajdonságablakban.
- Ha szeretné módosítani a munkaterület-csempék sorrendjét, válassza ki a **Képernyő személyre szabása** beállítást a Tulajdonságok ablakban a **Személyes beállítások** eszköztár megnyitásához. Az **Áthelyezés** eszköz segítségével tetszés szerint újrarendezheti a csempéket.
- Egy új munkaterület csempe létrehozásához, a Tulajdonságok ablakban, jelölje be a **Hozzáadása a munkaterülethez** lehetőséget. Egy új munkaterület lap jön létre az irányítópult alsó részén. Ez az új munkaterület csempe átnevezhető. Hozzáadhat listákat, csempéket és hivatkozásokat a munkaterülethez a témakörben itt leírtak szerint: [Listák, csempék és hivatkozások hozzáadása munkaterületekhez](personalize-user-experience.md#adding-a-tile-list-or-link-to-a-workspace).

## <a name="administration-of-personalization"></a>Személyes beállítások adminisztrálása

Az oldal személyre szabása után más felhasználókkal is megoszthatja a személyes beállításait a személyre szabott oldal exportálásával. Ezután megkérheti a többi felhasználót, hogy nyissák meg a személyre szabott lapot, és importálják az ön által létrehozott személyre szabási fájlt. Másik lehetőségként a személyre szabást adhat a rendszergazdai jogokkal rendelkező felhasználónak. A felhasználó alkalmazhatja a személyre szabási fájlt sok felhasználóra egyszerre.

Rendszergazdai jogokkal rendelkező felhasználók más felhasználók személyes beállításait is kezelhetik a **Személyes beállítások** lapon. Ezen a lapon négy fül van:

- **Alkalmazás** – Importálhat vagy kiválaszthat egy személyre szabási beállítást egy vagy több felhasználó számára. A személyre szabás alkalmazásához egy vagy több felhasználóra, először jelölje ki a szerepkört és az adott szerepkörrel rendelkező felhasználókat. Válasszon egy meglévő személyre szabást vagy importáljon egy személyre szabási fájlt a kiválasztott felhasználókra történő alkalmazáshoz. A rendszer ellenőrzi a személyre szabást, és alkalmazza az összes kijelölt felhasználóra, amikor azok legközelebb megnyitják a kijelölt lapot.
- **Törlés** – A lap vagy a munkaterület összes személyre szabása egy vagy több felhasználó esetében is törölhető. Először válasszon egy oldalt vagy munkaterületet, hogy megtekinthesse azon felhasználók listáját, akik személyre szabták ezt az oldalt. Ezután válassza ki azokat a felhasználókat, akiknek az adott oldalhoz vagy munkaterülethez tartozó személyre szabását törölni kell, majd válassza a **Törlés** elemet. A kiválasztott felhasználók által a kiválasztott lapra vagy munkaterületre alkalmazott valamennyi személyre szabási beállítás törlődik. Ez a művelet nem vonható vissza. Ugyanakkor ha a lapnak vagy a munkaterületnek létezik mentett személyre szabási beállítása, ez a beállítás visszaimportálható.
- **Kezelés felhasználónként** – Válasszon egy felhasználót, hogy megtekinthesse a felhasználó általa személyre szabott oldalak listáját. Ezután kiválaszthatja, hogy engedélyezze vagy letiltsa a kiválasztott felhasználónak a személyre szabott képességek használatát bizonyos oldalakon vagy az egész rendszerben. Emellett törölhet, importálhat és exportálhat személyre szabásokat a kiválasztott felhasználó számára. Ezenkívül visszaállíthatja a funkcióbuborékokat a kijelölt felhasználóhoz amelynek hatására az összes korábban figyelmen kívül hagyott előugró ablak , amelyek új funkciókat mutattak be ismét megjelennek, amikor a felhasználó ezekkel a funkciókkal találkozik.   
- **Rendszer:** – Itt tudja ideiglenesen letiltani a rendszerben szereplő személyes beállításokat az összes felhasználó számára. Ebben az esetben a személyre szabott beállítások törlődnek. Minden lap minden felhasználó számára az alapértelmezett értékére áll. Amennyiben később újra engedélyezi a személyes beállításokat, a rendszer minden személyre szabást újra alkalmaz. Véglegesen is törölheti a rendszerben szereplő személyes beállításokat az összes felhasználó számára. Nem lehet visszaállítani a törölt személyes beállításokat. Ezért a lépés végrehajtása előtt ellenőrizze, hogy exportálta mindazokat a személyes beállításokat, amelyeket később esetleg importálni szeretne.

## <a name="personalization-of-inventory-dimensions"></a>A készletdimenziók személyre szabása

Amikor a készletdimenziók beállítását szabja személyre egy lapon, fontolja meg azokat a beállításokat, amelyek segítségével létrehozta a **Megjelenítendő dimenzió** lehetőséget. Például személyre szabás segítségével egy oszlopot elrejt a kötegszám-készlet dimenzióból, de az oszlop megjelenik, amikor legközelebb megnyitja a lapot. Ez azért fordul elő, mert a **Dimenzió megjelenítése** beállítások határozzák meg a készlet dimenzió megjelenő oszlopait.

A **dimenzió megjelenítési** beállításai minden lapon érvényesülnek, és az egyes lapok személyre szabott készletdimenzió-mezőinek minden beállítását felülírják.

Ez azt jelenti, hogy ha az előző példában nem szeretné, hogy a Köteg száma készletdimenzió megjelenjen egy oldalon, a dimenziót törölnie kell az adott oldal **Dimenziók megjelenítése** beállításának megadásakor.
