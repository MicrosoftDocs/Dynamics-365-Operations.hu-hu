---
title: A felhasználói élmény testreszabása
description: Ez a témakör bemutatja, hogyan lehet személyre szabni az alkalmazást.
author: jasongre
manager: AnnBe
ms.date: 10/16/2019
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
ms.openlocfilehash: 124609041163bbcaf1b86a6964fa3f56fcd8f755
ms.sourcegitcommit: 574309903f15eeab7911091114885b5c7279d22a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/24/2019
ms.locfileid: "2658760"
---
# <a name="personalize-the-user-experience"></a>A felhasználói élmény testreszabása

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Ez a témakör bemutatja, hogyan lehet személyre szabni az alkalmazást.

A személyre szabások három alapvető osztályba sorolhatók.

- Egy beállítási lapon végzett testreszabások. Példák: a stílus és az időzóna.
- Az oldalak használatára vonatkozó testreszabások. Ezek a testreszabások az *implicit* testreszabások. Például a rendszer nyomon követi a rácsoszlopok szélességét, ha ezt beállítja, vagy a gyorslapok összecsukott/kibontott állapotát.
- Személyes beállítások, amelyeket a felhasználó azért teszi, hogy megváltoztassa az oldal megjelenését azzal, hogy megváltoztatja az oldal elemeinek kinézetét, sokszor valamilyen interaktív személyre szabási móddal. Ezek a testreszabások az *explicit* testreszabások. Például a felhasználó hozzáadhat, elrejthet vagy átrendezhet lapelemeket.

Bármilyen testreszabás csak arra a felhasználóra érvényes, aki megadta őket, és függetlenek a személyre szabás típusától vagy attól, hogy a felhasználó milyen vállalattal kommunikál. Ha egy felhasználó az oldalon módosításokat hajt végre, az nem módosítja a rendszerben más felhasználók kezelési felületét.

## <a name="system-wide-options-for-the-current-user"></a>Az egész rendszerre érvényes beállítások az aktuális felhasználó számára

A **Felhasználói beállítások** lap tartalmaz több rendszerszintű beállítást az aktuális felhasználóra. A **Felhasználói beállítások** oldal megnyitásához válassza a **Beállítások** gombot (fogaskerék szimbólum) a navigációs sávon, és jelölje be a **Felhasználói beállításokat**. A **Felhasználói beállítások** oldalhoz négy lap tartozik különböző felhasználói beállításokkal:

- **Vizuális** – A színtéma kiválasztása és az oldalelemek alapértelmezett méretének beállítása.
- **Beállítások** – Válassza ki a rendszer megnyitásakor mindig használt alapértelmezett értékeket. Az értékek között található a vállalat, a kezdőlap és az alapértelmezett megjelenítési/szerkesztési mód. (A megjelenítési/szerkesztési mód határozza meg, hogy egy oldalt zárolt vagy megnyitott a szerkesztésre, minden alkalommal, amikor megnyitja.) Ez a lap a nyelv, az időzóna és a dátum, az idő- és számformátumok beállításait is lehetővé teszi. Végül ezen a lapon több vegyes beállítás található, amelyek az egyes kiadások esetében eltérők lehetnek.
- **Fiók:** – Itt adhatja meg a felhasználónevet és más fiókhoz kapcsolódó beállításokat.
- **Munkafolyamat** – Válassza ki a munkafolyamattal kapcsolatos beállításokat.

A felhasználói beállítások módosításán túl, megtekintheti és törlheti is a használati adatokat és a testreszabásokat a **Használati adatok** gombbal. Csak válassza ki a **Használati adatok** lehetőséget a Művelet ablaktáblán.

A használat során az alkalmazás menti a felhasználói beállítások nagy részét, így a rendszer használata a jövőben kényelmesebb lesz. A **Személyre szabás** lapon tekintheti meg és kezelheti a személyes módosításokat, amelyeket végrehajtott a lapokon a rendszerben. Ezen a lapon alaphelyzetbe állíthatók a funkció-ábrafeliratok (azaz az új rendszerelemeket bemutató előugró ablakok) is. Ezt követően a korábban észlelt szolgáltatásokról ismételten figyelmeztetést kap.

> [!NOTE]
> Ha be van kapcsolva a [Mentett nézetek](saved-views.md) funkció , akkor a Művelet panel **Felhaszálói beállítások** lapján megtekintheti és kezelheti a **Testreszabást**.

## <a name="implicit-personalizations"></a>Implicit testreszabás

Az implicit személyes beállítások olyan személyes beállítások, amelyeket olyan vezérlőkkel hajt végre, amelyek tárolják az elemek aktuális láthatósági állapotát.

- **Rácsoszlopok:** – Megadhatja egy oszlop szélességét a listában, ha az oszlop fejlécén található méretező sávot balra vagy jobbra húzza a kívánt oszlopszélességig. Az alkalmazás tárolja az oszlop beállított szélességét. Majd minden alkalommal, amikor megnyitja a rácsot tartalmazó lapot, átméretezi az oszlop szélességét.
- **Gyorslapok** – Néhány lapon kibontható szakaszok vannak, amelyeket *Gyorslapoknak* hívunk. Az alkalmazás tárolja a már kibontott vagy összecsukott gyorslapok adatait. Majd a következő alkalommal, amikor megnyitja a lapot, ugyanazon gyorslap ki lesz bontva és össze lesz csukva, a lappal folytatott utolsó kommunikációt alapján. Bizonyos esetekben a gyorslap összecsukása javíthatja a teljesítményt, mivel az alkalmazásnak nem kell betöltenie azoknak a gyorslapoknak az információit egészen addig, amíg a gyorslapokat nem bontjuk ki. Amint később a témakör elmagyarázza, a lapon módosítható a gyorslapok sorrendje.
- **Adatterület** – Egyes lapokhoz tartozik egy **Kapcsolódó információk** ablaktábla jelenik meg, amely a lap aktuális tárgyához kapcsolódó írásvédett adatokat jelenít meg. Az **Kapcsolódó információk** minden szakaszát *Adatterületnek* hívjuk. Ki lehet bontani vagy össze lehet csukni a **Kapcsolódó információk** megjelenítését, illetve kibonthatók és összecsukhatók az egyes adatterületek. Az alkalmazás tárolja ezeket a beállításokat. Ha legközelebb megnyitja a lapot a **Kapcsolódó információk** panel és az egyes adatterületek állapota visszaáll, és ki lesz bontva vagy össze lesz csukva a lap utolsó kommunikációja alapján. Bizonyos esetekben az adatterület összecsukása javíthatja a teljesítményt, mivel az alkalmazásnak nem kell betöltenie azoknak a adatterületeknek az információit egészen addig, amíg azokat nem bontjuk ki.
- **Műveleti ablaktábla** – A *Műveleti ablak* a legtöbb oldal tetején jelenik meg. A műveleti ablak gombjaival számos műveleteket hajthat végre az aktuális lapon. Ezek a gombok gyakran a lapokon vannak csoportosítva. A teljes műveletpanel lehet nyitottan „kitűzve”, ahogy alapértelmezés szerint összecsukva is. Majd a következő alkalommal, amikor megnyitja a Művelet panelt, ugyanazon gyorslap ki lesz nyitva vagy össze lesz csukva, a lappal folytatott utolsó interakció alapján. Ha megnyitotta a Műveleti ablaktáblát, akkor a program a legutóbb használt lapot jeleníti meg.
- **QuickFilters** – A *Gyorsszűrő* sok rács felett jelenik meg. A Gyorsszűrő lehetővé teszi a rács a kiválasztott oszlop alapján szűrését. Az alkalmazás tárolja az oszlopot, amelynek alapján szűrt. Ezt követően, a rácsot tartalmazó lap következő megnyitásakor a rács szűrve lesz ugyanazon oszlopra. Azonban ezután szűrni lehet egy másik oszlopra is a rácsot.
- **Oszlopfejléc-szűrők** – A rács az *Oszlopfejléc-szűrők* segítségével történő szűrésekor módosíthatja a szűrési operátort a megtalálni a kívánt adatok szerint. Például módosíthatja a kezelőt a **kezdődik** lehetőségről a **pontosan** lehetőségre. Oszlop fejléce szűrő használatakor és a szűrési operátor változtatásakor, az alkalmazás mindig tárolja a módosítást. Majd visszaállítja szűrési operátort ha legközelebb szűr az oszlopra.
- **Navigációs ablak** – A *navigációs ablak* megnyitásához válassza ki a **Navigációs panel kibontása** gombot bármely lap bal felső ablakában. (A _**Menü** gomb_ másik neve *hamburger*, *hamburger menü*, vagy *hamburger gomb*.) Rögzítheti a navigációs ablakot kinyitva, vagy alapértelmezés szerint összecsukva tárolhatja. A navigációs ablak nyitva rögzítése után, az alkalmazás nyitva tartja azt mindaddig, amíg össze nem csukja.

## <a name="explicit-personalizations"></a>Explicit testreszabás

A személyek és vállalatok számára eltérőek a legfontosabb adatok, és azok, amelyeket nem igényelnek az üzleti tevékenységhez. Személyre szabhatja adatainak megrendelését és kezelését. Megadhatja azt is, hogy bizonyos adatokat el kell rejteni. Ezek a funkciók kulcsfontosságúak a személyes és produktív használati élményre, és példák az explicit személyes beállításokra. Az explicit testreszabások olyan testreszabások, amelyeket kifejezetten azzal a szándékkal hajtunk végre, hogy megváltoztassuk egy elem vagy lap megjelenését vagy működését.

### <a name="shortcut-menu-options"></a>Gyorsbillentyű menüpontok

Helyi menük nyújtanak néhány lehetőséget egy lap explicit módosítására, hogy az jobban megfeleljen igényeinek vagy a vállalat igényeinek. (Más néven a helyi menü van egy *helyi menü* vagy *helyi menüje*.)

Néhány, a szokásos és a fontos változtatást laphoz végrehajtott érhetők el közvetlenül, a helyi menü Beállítások pontjára. Ha például a 17. platformfrissítéstől kezdődően szeretne felvenni vagy elrejteni oszlopokat egy rácsban, kattintson a jobb gombbal a rács oszlopfejlécére, és adja meg az **Oszlop hozzáadása** vagy **Oszlop elrejtése** lehetőséget.

Ezenkívül a legtöbb alaptípusok explicit személyre szabása akkor érhetők el, kattintson a jobb gombbal egy elemre, és válassza a **Személyre szabást**. (Megjegyzendő, hogy az oldalon nem minden elem szabható személyre.) Ha a személyre szabásnak ezt a módszerét választja, akkor megjelenik az elem tulajdonság ablaka.

![Egy elem tulajdonságainak testreszabása](./media/personalization-element-properties.png)

A tulajdonságablak segítségével egy elem testreszabása a következőképpen történik:

- Az elem címkéje módosítása.
- Az elem elrejtése, így az nem jelenik meg az oldalon. A mező adatait nem törölték vagy módosították. Az adatok csak nem jelennek meg az oldalon többé.
- Tartalmazza a gyorslap összefoglaló szakasz információit (ha az elem egy gyorslapon van).
- A mező kihagyása, így nem kap fókuszt, amikor átvált a lapon.
- az adatk szerkesztésének megakadályozása a mezőben (bármely rekord).

A tulajdonságablak szerepeltethet egyéb személyre szabása funkciókat az elemtől függően. Például egy csempe a tulajdonságablak előfordulhat, hogy lehetővé teszik a támogatják ezt a csempét az irányítópultra, és a tulajdonságablak egy irányítópult előfordulhat, hogy lehetővé teszik, hogy irányítópult az új munkaterület létrehozása.

### <a name="the-personalization-toolbar"></a>Személyre szabási eszköztár

Ha több módosítást is szeretne végrehajtani egy lapon, illetve olyan módosításokat szeretne végrehajtani, amelyek nem érhetők el más mechanizmusokon keresztül (például elemeket szeretne újrarendezni), használhatja a **Testreszabás** eszköztárat. A **Testreszabás** eszköztár megnyitásához hajtsa végre a következő lépések valamelyikét:

- Válassza ki a **Képernyő személyre szabása** lehetőséget egy elem tulajdonságablakában.
- Bármely oldal Művelet panelén válassza az **Oldal személyre szabása** csoportot a **Testreszabás** csoportban a **Beállítások** lapon.
- Válassza ki a navigációs sávon a **Beállítások** gombot (a fogaskerék szimbólum), majd válassza a **Személyre szabás** lehetőséget.

[![Személyre szabási eszköztár](./media/restyledPersonalizationToolbar.png)](./media/restyledPersonalizationToolbar.png)

#### <a name="navigating-the-page"></a>Navigálás a lapon

Ha meg van nyitva a **Személyre szabás** eszköztár, az alapul szolgáló lap írásvédett (más szóval nem szerkeszthetők az adatok), de még mindig interaktív. Pontosabban kibonthatja vagy összecsukhatja a **Kapcsolódó információk** ablaktáblát, válthat a lapok között, valamint kibonthatja vagy összecsukhatja a szakaszokat, ahogy általában végrehajtja ezeket a műveleteket a lapon. Ha személyre szabott módosítást szeretne alkalmazni egy összecsukható panelre vagy lapra (például egy gyorslap elrejtése), akkor egyszerűen ki kell választania a gombot, amely megjelenik a szakasz vagy lap mellett, amikor ráfókuszál a billentyűzettel vagy fölé viszi az egérmutatót.

#### <a name="personalization-tools"></a>Személyre szabási eszközök

A következő eszközök érhetők el a **Személyre szabása** eszköztáron:

- A **Kijelölés** eszközzel egy elemet kijelölve megnyithat egy párbeszédablakot, és módosíthatja az elem tulajdonságait. Az eszköz használatához válassza ki az eszköztárban a **Kijelölés** gombot, majd jelölje ki a kívánt elemet. Az elem tulajdonságok ablaka jelenik meg, és ezen az elem bármilyen tulajdonsága módosítható. Megismételheti a folyamatot más elemekkel is, amelyek a lapon testre szabhatók. Bizonyos esetekben előfordulhat, hogy egyes testreszabható tulajdonságok nem érhetők el. Kötelező mezőt például nem tud zárolni.
- Válassza ki az **Elrejtés** eszközt egy elem és elrejtéséhez a lapon. Az eszköz használatához válassza ki az eszköztárban az **Elrejtés** gombot, majd rejtse el a kívánt elemet. Ha használja az **Elrejtés** eszközt, minden éppen rejtett elem látható lesz, de egy árnyékolt tárolóban jelennek meg. Ezután kijelölheti, hogy az elem látható legyen. Ha szeretné megtekinteni, hogyan fog kinézni a lap az elemek elrejtésével, váltson át egy másik testreszabási eszközre.

    Elrejtheti a kötelező mezőket és a kötelező mezőket tartalmazó paneleket. Ilyen módon lehetősége van, hogy egyszerűsített élményt hozzon létre, ahol az üzleti logika által alapértelmezett értékekkel kitöltött mezők nem láthatók. Az elrejtett kötelező mezők ideiglenesen láthatóvá válnak, ha a felhasználó üresen hagyja azokat a lap mentésekor.

- Használja a **Mező hozzáadása** eszközt új mező felvételéhez a lapra. Az eszköz használata esetén csak az oldal definíciójának részét képező mezőket veheti fel. Új mezők, amelyek nem részei az aktuális oldaldefiníciónak, létrehozásával kapcsolatos további tudnivalókat lásd: [egyéni mezők](user-defined-fields.md). Miután kiválasztotta a **Mező hozzáadása** gombot az eszközsora először válasszon adott csoportot vagy területet, ahová mező hozzáadását szeretné. A kijelölt csoporttal vagy területtel kapcsolatos mezők listája egy párbeszédpanelen jelenik majd meg. A párbeszédpanelen válasszon hozzáadandó mezőket, majd a **Beszúrás** lehetőséget. Korábban hozzáadott mező eltávolításához meg kell ismételni a folyamatot, de a mező a párbeszédpanelen ne legyen kijelölve.
- Használja az **Áthelyezés** eszközt, ha egy elemet ki szeretne jelölni és az elemek jelenlegi csoportján belül egy másik helyre szeretné áthelyezni. Ne feledje, hogy a szülőcsoporton kívülre nem helyezhető át elem. Az eszköz használatához válassza ki az eszköztárban az **Áthelyezés** gombot, majd helyezze át a kívánt elemet. Amikor kiválaszt egy elemet, az alkalmazás meghatározza, ha azokat a helyeket, ahová az elemet át lehet helyezni. Ezek a helyek *lerakási zónákként* ismertek. Az aktuális csoporton belül az elem húzásakor minden lerakási zóna mellett a terület, ahová az elem húzható színes, félkövér sorként jelenik meg.
- Válassza ki a **Kihagyás** eszközt egy elem eltávolítására az oldal billentyűparancs-sorozatából Ha bejelöli a **Kihagyás** gombot az eszközsoron, minden éppen kihagyott elem látható lesz, és egy árnyékolt tárolóban jelennek meg. Interaktívan eltávolíthat vagy hozzáadhat mezőket a lapsorrendhez.
- Használja a **Megjelenítés a fejlécben** eszközt, ha azt szeretné, hogy az elem a gyorslap összesítő lapján megjelenjen. Ha kiválasztja a **Megjelenítés a fejlécben** gombot az eszközsoron , összesítő mezők szerepelnek az árnyékolt tároló bejelölt összes mezőt. Interaktívan felvehet mezőket az összesítő gyorslapra, és eltávolíthat mezőket onnan a mezők kijelölésével.
- Használja a **Zárolás** eszközt, ha egy elemet Szerkeszthető vagy Nem szerkeszthető állapotúra akar állítani. Ha kiválasztja a **Zárolás** gombot az eszközsoron, minden nem szerkeszthető elem látható lesz, és egy árnyékolt tárolóban jelennek meg. Ezután újra szerkeszthetővé tehetők. Vegye figyelembe, hogy egyes mezők kötelezőek, és nem tehetők zárolttá. Lakat szimbólum jelenik meg az ilyen mezők mellett.
- Használja a **PowerApp eszköz hozzáadása** gombot egy Microsoft PowerApps használatával létrehozott alkalmazás beágyazásához a lapra. A PowerApps alkalmazás beágyazásával a lapba kapcsolatos részletes tudnivalókat lásd: [PowerApps beágyazása](embed-power-apps.md).
- Válassza a **Tisztítás** eszközt az oldal alapértelmezett, telepítési beállításainak visszaállításához. Az aktuális oldal minden testreszabása törölve lesz. Nincs visszavonás művelet. Ezért akkor használja ezt az eszközt, ha biztos benne, hogy az oldal alaphelyzetbe állítását szeretné.
- Használja az **Importálás** eszközt hogy egy korábban ön vagy más által létrehozott testreszabási fájlból töltsön be testreszabási beállításokat. Ha egy lap testreszabásait importálja, megadhatja, hogy hozzá legyenek-e adva a lap meglévő testreszabásaihoz, vagy lecseréljék azokat. Nincs visszavonás művelet. Ezért a személyre szabások importálása után manuálisan kell törölnie vagy visszavonnia a nem kívánt módosításokat.
- Használja az **Exportálás** eszközt a lap testreszabásainak mentéséhez egy fájlba. Majd a testreszabásokat megoszthatja más felhasználókkal. Ezeknek a felhasználóknak csak a lap személyes beállításokat tartalmazó fájlt kell importálni.
- Válassza ki a **Bezár** gombot a **Személyre szabás** eszköztár bezárásához és ahhoz, hogy az oldal visszatérjen korábbi interaktív állapotába.

Hagyományosan, amikor a **Személyre szabás** eszköztár használatban van, a testreszabások azonnal életbe lépnek. Ha viszont a [Mentett nézetek](saved-views.md) funkció be van kapcsolva, akkor a kiválasztott nézethez explicit módon kell mentenie a személyre szabott beállításokat.

Bizonyos esetekben látható egy lakat ikon az elem mellett, amikor kiválaszt egy eszközt. Ez a szimbólum azt jelzi, hogy nem módosíthatók a kijelölt eszközzel kapcsolatos az elem tulajdonságait, mert tulajdonságokhoz módosításai megakadályozza, hogy a lap megfelelően működik-e.

### <a name="adding-a-tile-list-or-link-to-a-workspace"></a>Csempe vagy lista vagy hivatkozás hozzáadása a munkaterülethez

Egyes listákat tartalmazó lapok esetében a **Hozzáadás munkaterülethez** testreszabási funkció a Művelet ablaktábla **Személyre szabás** csoportjában érhető el a **Beállítások** lapjának lapon. Ez a funkció lehetővé teszi, hogy az aktuális lista megfelelő adatait egy meghatározott munkaterületre küldje. A munkaterületen megjelenő információk a teljes listán, illetve a lista szűrt és rendezett verzióján is alapulhatnak. Megadhatja azt is, hogy az információ megjelenjen-e a munkaterületen listaként, összegző csempeként megjelenítve az elemek számát a listában, vagy egy hivatkozásként.

> [!NOTE]
> Ha a [Mentett nézetek](saved-views.md) funkció be van kapcsolva, a munkaterületre beküldött tartalom közvetlenül egy nézethez kapcsolódik. A nézet lekérdezése a munkaterület adatainak beolvasására szolgál, és a munkaterületen található megfelelő csempe vagy hivatkozás megnyitja a nézethez tartozó lapot, úgy, hogy a nézet lekérdezése és a testreszabások alkalmazva vannak rá.

[![Hozzáadás munkaterületenként](./media/personalization-addtoworkspace.png)](./media/personalization-addtoworkspace.png)

- Lista hozzáadásához a munkaterülethez, először rendezni és szűrni kell a listát a lapon, hogy az adatok a munkaterületen megjeleníteni kívánt módon jelenjenek meg. (Ha a Mentett nézetek funkció be van kapcsolva, akkor nem folytathatja addig, amíg nem menti azokat a nézeteket, amelyekhez ilyen feltételek tartoznak). Ezután válassza a **Hozzáadás munkaterülethez** lehetőséget. Válassza ki a munkaterületez, majd kattintson a **Prezentáció** mezőben a **Lista** elemre. Miután kijelölte **Konfigurálást**, megjelenik egy párbeszédpanel, ahol kiválaszthatja az oszlopok, amelyek jelenjenek meg a listában a munkaterületen. Megadhatja a munkaterületen a listához használandó címkét.
- A munkaterület címének hozzáadásához először szűrnie kell a listát az oldalon, hogy az összesítendő adatokat megjelenítse (vagy azokat, amikhez gyors elérést szeretne). (Ha a Mentett nézetek funkció be van kapcsolva, akkor nem folytathatja addig, amíg nem menti azokat a nézeteket, amelyekhez ilyen feltételek tartoznak). Ezután válassza a **Hozzáadás munkaterülethez** lehetőséget. Válassza ki a munkaterületez, majd kattintson a **Prezentáció** mezőben a **Cím** elemre. Miután kijelölte a **Konfigurálást**, megjelenik egy párbeszédpanel, ahol megadhatja a munkaterületen található csempe használandó címkéjét. Megadhatja azt is, hogy a csempén kell-e egy számának megjelennie. Miután hozzáadta a csempét a munkaterülethez kiválaszthatja, hogy az aktuális lapot megnyissa a munkaterületről. Ezt követően megtekintheti a csempéhez társított szűrt listát.
- Hivatkozás hozzáadásához egy munkaterülethez, először a terméklista szűrése az oldalon, hogy az Ön érdeklő adatokat mutassa. (Ha a Mentett nézetek funkció be van kapcsolva, akkor nem folytathatja addig, amíg nem menti azokat a nézeteket, amelyekhez ilyen feltételek tartoznak). Ezután válassza a **Hozzáadás munkaterülethez** lehetőséget. Válassza ki a munkaterületez, majd kattintson a **Prezentáció** mezőben a **Hivatkozás** elemre. Miután kijelölte a **Konfigurálást**, megjelenik egy párbeszédpanel, ahol megadhatja a hivatkozáshoz használandó címkét. Megadhat címkét az új szakaszhoz, amely ezt a hivatkozást tartalmazza.

Miután egy lista, a csempe vagy a hivatkozás egy munkaterülethez hozzá lett adva, a munkaterületet megnyithatja, és az elemeit igény szerint átrendezheti.

### <a name="adding-a-summary-from-a-workspace-to-a-dashboard"></a>Összegzés hozzáadása a munkaterületről az irányítópultba

Néhány munkaterület tartalmaz számlálási csempét (vagyis számot tartalmazó csempét), és lehetséges, hogy ezeket is meg szeretné jeleníteni az irányítópulton. A munkaterületen kattintson a jobb gombbal egy csempére, válassza a **Személyre szabás** elemet, majd a csempe tulajdonságablakában **Kitűzés az irányítópultra** lehetőséget. Majd, amikor a következő alkalommal megnyitja és frissíti a kiválasztott irányítópultot, láthatja a számot a munkaterület navigációs csempéje alatt az irányítópulton. Kiválaszthatja, hogy a számláló közvetlenül az adatokhoz menjen, amelyeket bemutat.

### <a name="personalizing-your-dashboard"></a>Az irányítópult személyre szabása

Az irányítópult legtöbbször az első oldal, amelyet az alkalmazás megnyitásakor lát. Testre szabhatja az irányítópultot, hogy csak a megtekinteni kívánt munkaterület lapokat mutassa. A paneleket átrendezheti is, hogy a megadott sorrendben jelenjenek meg, a munkaterület navigációs lapok átnevezéséhez vagy egy új munkaterület-név hozzáadásához.

Az irányítópult testreszabásához kattintson a jobb gombbal bármelyik csempe, és adja meg **Személyre szabás** elemet a csempe tulajdonság ablak megnyitásához.

- Ha azt szeretné, vagy nevezze át vagy rejtse el a kijelölt csempét, végezhet módosítást közvetlenül a tulajdonságablakban.
- Ha szeretné módosítani a munkaterület-csempék sorrendjét, válassza ki a **Képernyő személyre szabása** beállítást a Tulajdonságok ablakban a **Személyes beállítások** eszköztár megnyitásához. Az **Áthelyezés** eszköz segítségével tetszés szerint átrendezheti a csempéket.
- Egy új munkaterület csempe hozzáadásához, a Tulajdonságok ablakban, jelölje be a **Hozzáadás munkaterülethez** lehetőséget. Egy új munkaterület lap jön létre az irányítópult alsó részén. Ez az új munkaterület csempe átnevezhető. Hozzáadhat listákat, csempéket és hivatkozásokat a munkaterülethez a témakörben itt leírtak szerint: [Listák, csempék és hivatkozások hozzáadása munkaterületekhez](#adding-a-tile-list-or-link-to-a-workspace).

## <a name="administration-of-personalizations"></a>Testreszabások adminisztrálása

Az oldal személyre szabása után más felhasználókkal is megoszthatja a személyes beállításait a személyre szabott oldal exportálásával. Ezután megkérheti a többi felhasználót, hogy nyissák meg a személyre szabott lapot, és importálják az ön által létrehozott személyre szabási fájlt. Másik lehetőségként a személyre szabásokat adhat a rendszergazdai jogokkal rendelkező felhasználónak. A felhasználó alkalmazhatja a személyre szabási fájlt sok felhasználóra egyszerre.

Rendszergazdai jogokkal rendelkező felhasználók más felhasználók személyes beállításait is kezelhetik a **Személyre szabás** lapon.

Azoknak a vevőknek, akik nem kapcsolták be a [Mentett nézetek](saved-views.md) lehetőséget, ennek a weboldalnak négy lapja van:

- **Alkalmazás** – Importálhat vagy kiválaszthat egy személyre szabási beállítást egy vagy több felhasználó számára. A személyre szabás alkalmazásához egy vagy több felhasználóra, először jelölje ki a szerepkört és az adott szerepkörrel rendelkező felhasználókat. Válasszon egy meglévő személyre szabást vagy importáljon egy személyre szabási fájlt a kiválasztott felhasználókra történő alkalmazáshoz. A rendszer ellenőrzi a személyre szabást, és alkalmazza az összes kijelölt felhasználóra, amikor azok legközelebb megnyitják a kijelölt lapot.
- **Törlés** – A lap vagy a munkaterület összes személyre szabása egy vagy több felhasználó esetében is törölhető. Először válasszon egy oldalt vagy munkaterületet, hogy megtekinthesse azon felhasználók listáját, akik személyre szabták ezt az oldalt. Ezután válassza ki azokat a felhasználókat, akiknek az adott oldalhoz vagy munkaterülethez tartozó személyre szabását törölni kell, majd válassza a **Törlés** elemet. A kiválasztott felhasználók által a kiválasztott lapra vagy munkaterületre alkalmazott valamennyi személyre szabási beállítás törlődik. Ez a művelet nem vonható vissza. Ugyanakkor ha a lapnak vagy a munkaterületnek létezik mentett személyre szabási beállítása, ez a beállítás visszaimportálható.
- **Felhasználók** – Válasszon egy felhasználót, hogy megtekinthesse a felhasználó által személyre szabott oldalak listáját. Ezután kiválaszthatja, hogy engedélyezze vagy letiltsa a kiválasztott felhasználónak a személyre szabott képességek használatát bizonyos oldalakon vagy az egész rendszerben. Emellett törölhet, importálhat és exportálhat személyre szabásokat a felhasználó számára. Ezenkívül a felhasználó számára alaphelyzetbe állíthatók a funkció-ábrafeliratok. Ebben az esetben, ha a felhasználó korábban elutasította az új funkciókat bemutató előugró ablakokat, ezek legközelebb újra megjelennek a felhasználó számra
- **Rendszer:** – Itt tudja ideiglenesen kikapcsolni a rendszerben személyre szabásokat az összes felhasználó számára. Ebben az esetben minden személyre szabás minden felhasználónál törlődik, és az összes lap visszaáll az alapértelmezett állapotába. Amennyiben később újra bekapcsolja a személyre szabásokat, a rendszer minden személyre szabást újra alkalmaz. Véglegesen is törölheti a rendszerben szereplő személyes beállításokat az összes felhasználó számára. A törölt személyes beállításokat nem lehet visszaállítani. Ezért a lépés végrehajtása előtt ellenőrizze, hogy exportálta mindazokat a személyes beállításokat, amelyeket később esetleg importálni szeretne.

Azoknak a vevőknek, akik bekapcsolták a [Mentett nézetek](saved-views.md) lehetőséget, a **Személyre szabások** weboldalnak négy lapja van:

- **Közzétett nézetek** – Ezeket a nézeteket közzétették a szervezeten belül. Ha módosítani kívánja azokat a felhasználókat, akiket ezek a nézetek céloznak, módosíthatja az egyes nézetekhez társított biztonsági szerepköröket vagy jogi személyeket. Egy vagy több közzétett nézet is exportálható vagy törölhető.
- **Nem közzétett nézetek** – Ezek a nézetek olyan sablonnézetek, amelyek importálva lettek a rendszerbe, de még nem lettek közzétéve. Ezeket a nézeteket közzéteheti, exportálhatja vagy törölheti.
- **Személyes nézetek** – Ezeket a nézeteket a rendszerben lévő felhasználók hozták létre. Közzétehet személyes nézeteket a szervezeten belül, vagy egy vagy több nézetet másik felhasználók számára is átmásolhat. Ezeket a nézeteket igény szerint exportálhatja vagy törölheti is.
- **Felhasználók** – Válasszon egy felhasználót, hogy megtekinthesse a felhasználó által személyre szabott oldalak listáját. Ezután kiválaszthatja, hogy engedélyezze vagy letiltsa a kiválasztott felhasználónak a személyre szabott képességek használatát bizonyos oldalakon vagy az egész rendszerben. Emellett törölhet, importálhat és exportálhat személyre szabásokat a felhasználó számára. Ezenkívül a felhasználó számára alaphelyzetbe állíthatók a funkció-ábrafeliratok. Ebben az esetben, ha a felhasználó korábban elutasította az új funkciókat bemutató előugró ablakokat, ezek legközelebb újra megjelennek a felhasználó számra
- **Rendszer:** – Itt tudja ideiglenesen kikapcsolni a rendszerben személyre szabásokat az összes felhasználó számára. Ebben az esetben minden személyre szabás minden felhasználónál törlődik, és az összes lap visszaáll az alapértelmezett állapotába. Amennyiben később újra bekapcsolja a személyre szabásokat, a rendszer minden személyre szabást újra alkalmaz. Véglegesen is törölheti a rendszerben szereplő személyes beállításokat az összes felhasználó számára. A törölt személyes beállításokat nem lehet visszaállítani. Ezért a lépés végrehajtása előtt ellenőrizze, hogy exportálta mindazokat a személyes beállításokat, amelyeket később esetleg importálni szeretne.

Azoknak a felhasználóknak, akik hozzáférnek a **Személyre szabás** lapjához, személyes vagy sablon nézeteket is importálhatunk a művelet ablak **Nézetek importálása** gombjának használatával.

## <a name="personalizing-inventory-dimensions"></a>A készletdimenziók személyre szabása

Amikor a készletdimenziók beállítását szabja személyre egy lapon, fontolja meg azokat a beállításokat, amelyek segítségével létrehozta a **Megjelenítendő dimenzió** lehetőséget. Például személyre szabás segítségével egy oszlopot elrejt a kötegszám-készlet dimenzióból, de az oszlop megjelenik, amikor legközelebb megnyitja a lapot. Ez azért fordul elő, mert a **Dimenzió megjelenítése** beállítások határozzák meg a készlet dimenzió megjelenő oszlopait. A **Dimenzió megjelenítési** beállításai minden lapon érvényesülnek, és ezek a beállítások az egyes lapok minden személyre szabott készletdimenzió-mező beállításait felülírják.

Tehát ez azt jelenti, hogy ha az előző példában nem szeretné, hogy a Köteg száma készletdimenzió megjelenjen egy oldalon, a dimenziót törölnie kell az adott oldal **Dimenziók megjelenítése** beállításának megadásakor.
