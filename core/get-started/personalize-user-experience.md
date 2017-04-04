---
title: "A felhasználói felület testreszabása"
description: "A cikk leírja, hogyan szabhatja a Microsoft Dynamics 365 műveletekhez."
author: RobinARH
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: SysUserSetup
audience: Application User, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 62363
ms.assetid: 57b445d7-3e9e-4228-8728-f63b9dbd77a3
ms.search.region: Global
ms.author: tlefor
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 4bb647cfd3f012efbffa93a81462c538a24ac850
ms.openlocfilehash: 8965c193839002776b3c61036b23b54625c974a4
ms.lasthandoff: 03/31/2017


---

# <a name="personalize-the-user-experience"></a>A felhasználói felület testreszabása

A cikk leírja, hogyan szabhatja a Microsoft Dynamics 365 műveletekhez.

Személyes beállítások a Microsoft Dynamics 365 műveletek számos típusa van. Néhány személyes beállítás választási lehetőségként jelenik meg a beállítások oldalon a beállítások listájában. Implicit néhány személyes beállítások, például Dynamics 365 műveletek nyomon követi, hogy a rács oszlopszélesség Ha módosítja, és a kibontott/összezárt állapot gyorslapból épül fel. Vannak explicit személyes beállítások. Az explicit személyes beállításokhoz meg kell adnia egy interaktív személyre szabási módot és módosítania kell az oldal megjelenését azzal, hogy közvetlenül kezeli az elem megjelenését és viselkedését az oldalon. 

Személyes beállítások, bármilyen típusú, a felhasználó által a Dynamics 365 műveletek vannak, csak az adott felhasználó számára függetlenül a vállalat, amely a felhasználó kommunikál. Ha egy felhasználó az oldalon módosításokat hajt végre, az nem módosítja a rendszerben más felhasználók kezelési felületét.

## <a name="systemwide-options-for-the-current-user"></a>Az aktuális felhasználó telepítenek beállítások
A navigációs sávon található egy fogaskerék kép, amelyet **Beállítások** menügombnak hívnak. A **Beállítások** menü megnyitásával választási lehetőségek jelennek meg. A **Beállítások** kijelölésével megnyílik a felhasználói **Beállítások** oldal. Ott négy beállítási lapot talál: **Vizuális**, **Preferenciák**, **Fiók**, és **Munkafolyamat**.

-   **Vizuális: **A színtéma kiválasztására és az oldalelemek alapértelmezett méretének beállítására használható.
-   **Beállítások:** Itt választhatja alapértelmezett Dynamics 365 műveletekhez, beleértve a vállalat, a kezdőlap és alapértelmezett megjelenítési/szerkesztési mód (amely azt határozza meg, ha egy lapot zárolt, vagy minden alkalommal szerkesztésre megnyitott Megnyitás) megnyitásakor a. Itt találja meg a nyelvet, az időzónát, illetve a dátum, az idő és a számok formátumának beállítását. A legutóbbi verziókban ez az oldal különböző preferenciákat tartalmaz, amely eltér a különböző verziókban.
-   **Fiók: **Itt adhatja meg a felhasználói azonosítót és más fiókhoz kapcsolódó beállításokat.
-   **Munkafolyamat: **Itt adhatja meg a munkafolyamattal kapcsolatos beállításokat.

## <a name="implicit-personalizations"></a>Implicit testreszabás
Az implicit személyes beállítások olyan személyes beállítások, amelyeket olyan vezérlőkkel hajt végre, amelyek megjegyzik az elemek aktuális láthatósági állapotát. 

**Rácsoszlopok:** Megadhatja egy oszlop szélességét a listában, ha az oszlop fejlécén található méretező sávot balra vagy jobbra húzza a kívánt szélességig. 365 Dynamics műveletek tárolja a szélességét, hogy kívánja, majd a szélességet tartalmazó oszlop megjelenítése minden alkalommal, amikor a listában nyissa meg a lapot. 

**Gyorslapok:** Néhány lapon kibontható szakaszok vannak, amelyeket Gyorslapoknak hívunk. 365 Dynamics műveletek fogja tárolni a gyorslapokon melyik kibővítette, és mely gyorslapja van csukva. Minden alkalommal, amikor visszatér az oldalra, ugyanazok a gyorslapok lesznek kibontva vagy összecsukva, ahogy az utolsó használatkor hagyta őket. Ebben a cikkben bemutatjuk, hogyan változtassa meg a gyorslap-szakaszok sorrendjét. Bizonyos esetekben gyorslap összecsukása javíthatja a teljesítményt, mert Dynamics 365 műveletekhez nem szükséges ezen a gyorslapon a adatainak beolvasása, mindaddig, amíg a gyorslap van bontva. 

**Adatterületek:** Néhány oldal tartalmaz egy adatterület-panel nevű szakaszt. Ez az ablak csak olvasható információkat tartalmaz az aktuális oldal tartalmáról. Az adatterület-panel minden szakaszát adatterületnek hívjuk. Akkor kibonthatjuk vagy összecsukhatjuk egy tény mezőbe, és műveletek Dynamics 365 tárolja a beállításokat. Bizonyos esetekben tény mező összecsukása javíthatja a teljesítményt, mert Dynamics 365 műveletekhez nem szükséges a ezt a tényt be adatokat beolvasni, amíg a tényt be van-e bontva.

## <a name="explicit-personalizations-using-the-personalization-toolbar"></a>Explicit testreszabás a Személyes beállítások eszköztárral
Minden személy és vállalat más nézeteket vall arról, mely adatok a legfontosabbak számukra, vagy mely adatok nem szükségesek az üzlet működéséhez. Szerinti formára alakítása a rendezett, egymáshoz kapcsolódó, vagy akár az adatokat a program úgy, hogy a Dynamics 365 műveletek esetében a termelő és a személyes tapasztalat a kulcs rejtett nem. 

Explicit felhasználósorára ilyen személyes beállítások elvégezhető kifejezetten azzal a szándékkal megjelenését vagy működését egy elem vagy lap módosítása menü személyes beállítások kiválasztásával. Explicit személyre szabása legalapvetőbb típusú, ha egy elem gombbal, majd válassza **személyre szabása**. (Megjegyzendő, hogy az oldalon nem minden eleme személyre szabható.) Ha személyre szabása ezt a módszert választja, akkor az elem tulajdonság ablak látható. 

[![Egy elem tulajdonságait személyre szabása](./media/personalization-element-properties.jpg)](./media/personalization-element-properties.jpg) 

Ekképpen fogja személyre szabni az oldalon található elemet, ha egyszerűen csak meg akarja változtatni az elem címkéjét, el akarja rejteni, hogy ne jelenjen meg az oldalon (ez semmilyen adatot nem módosít, egyszerűen csak nem jeleníti meg az információt), vagy be akarja emelni az információt a gyorslapok összefoglaló szakaszába (ha az elem egy gyorslap), mezőt szeretne kihagyni a Tab billentyűvel való lépkedés közben, vagy nem szerkeszthetővé tenni az adatot a „Nem szerkeszthető” beállítás kiválasztásával. 

Ha elemeket szeretne áthelyezni, elrejteni vagy módosítani, akkor a Személyes beállítások eszköztárat használhatja, amely az elemek Tulajdonságok ablakáról érhető el a **Képernyő személyre szabása** beállítást kiválasztva. A Személyes beállítások eszköztár elérhető az elem Műveleti ablaktáblájáról, a **Beállítások** lap Személyes beállítás csoportjából. Válassza a **Képernyő személyre szabása** lehetőséget, hogy megjelenítse a Személyes beállítások eszköztárat. 

[![Személyre szabás eszköztár](./media/personalization-personalizationtoolbar.jpg)](./media/personalization-personalizationtoolbar.jpg)

A személyre szabás eszköztár számos testreszabási műveletek. Válassza ki a **Kiválaszt** eszközt, ha egyszerre több elemet szeretne kijelölni, és a tulajdonságaikat egyszerre szeretné megváltoztatni. Először kattintson a Kijelölés eszközre, majd kattintson arra az elemre, amelynek a tulajdonságait módosítani akarja. Amikor kiválaszt egy elemet, az elem tulajdonságok ablaka nyílik meg, és ezen az elem bármilyen tulajdonsága módosítható. Megismételheti a folyamatot más elemekkel is, amelyek a képernyőn testre szabhatók. Bizonyos esetekben, ha kijelöl egy elemet, azt láthatja, hogy néhány tulajdonság nem módosítható. Ez azt jelenti, hogy az aktuális elem módja alapján történik, Dynamics 365 műveletekhez nem segítségével módosíthatja az adott tulajdonság. Kötelező mezőt például nem tud elrejteni. 

Válassza ki az **Áthelyezés** eszközt, ha egy elemet ki akar jelölni és az elemek jelenlegi csoportján belül egy másik helyre szeretné áthelyezni. (A szülőcsoporton kívülre nem helyezhető át egy elem). Először kattintson az Áthelyezés eszközre, majd kattintson arra az elemre, amelyet át akar helyezni. Ha az elem, amely az áthelyezni kívánt elemre Dynamics 365 műveletek megvizsgálja megérteni, ha ez az elem lehet mozgatni, és a "lerakók" sorozatának létrehozása az űrlap megjelenítése színes, vastag vonal jelzi a terület, ahol az elem húzható, húzás közben az aktuális csoport elemének körül mellett. 

Válassza ki az **Elrejtés** eszközt egy elem kiválasztásához és elrejtéséhez. Egy elem elrejtéséhez válassza ki az Elrejtés eszközt, és kattintson arra az elemre, amelyet el kíván rejteni. Ha kiválasztja az Elrejtés eszközt, akkor minden aktuálisan elrejtett elem láthatóvá válik egy árnyékolt tárolóban, azután kiválaszthatja, mely elemek elrejtését szeretné megszüntetni. Válassza ki a Kijelölés eszközt, hogy lássa, hogy fog kinézni az oldal a kiválasztott elemek elrejtésével. Válassza ki az **Összegzés** eszközt, ha egy számérték vagy karakterlánc mezőt szeretne megjeleníteni a gyorslapok összegzés területén. Az Összegzés eszköz csak olyan mezőkre érvényes, amelyek a gyorslap szakaszban vannak. Az összefoglaló eszköz kiválasztásakor Dynamics 365 műveletek minden árnyékolt tartályban történő összegző mezőként kijelölt mezők jelennek meg. Interaktívan hozzáadhat és eltávolíthat mezőket a gyorslap összegzőből, ha a mezőre kattint. 

Válassza ki a **kihagyása** eszköz egy elem eltávolítása a lap lapon billentyűparancs. A Kihagyás eszköz kiválasztásakor minden jelenleg kihagyott elemek jelenjenek meg egy árnyékolt tároló így kiválaszthatja azokat újra, hogy azok a kihagyott elem kiválasztásával lap sorozat része. 

Válassza ki a **Szerkesztés** eszközt, ha egy elemet Szerkeszthető vagy Nem szerkeszthető állapotúra akar állítani. Ha kiválasztja a Szerkesztés eszközt, akkor minden aktuálisan zárolt elem megjelenik egy árnyékolt tárolóban, azután kiválaszthatja, mely elemeket szeretne szerkeszthetővé tenni. Vegye figyelembe, hogy egyes mezők kötelezőek, és nem tehetők zárolttá. Az ilyen mezők mellett egy lakat ikon jelenik meg. 

Válassza ki a **Hozzáadás** eszközt új mező felvételéhez a lapra. A hozzáadás eszközzel nem hozható létre új mező, viszont hozzáadhat olyan mezőket, amelyek az aktuális oldal definíciójában szerepelnek, de nem jelennek meg az oldalon. Ha kiválasztja a Hozzáadás eszközt, először ki kell választania azt a csoportot vagy területet, ahol hozzá akarja adni a mezőt. A kijelölt szakasszal kapcsolatos mezők listája egy párbeszédpanelen jelenik meg. A párbeszédpanelen kiválaszthat egy vagy több hozzáadandó mezőt, majd kattintson a Beszúrás gombra. Amennyiben szeretne megszüntetni egy mezőt, amelyet korábban hozzáadott, ismételje meg a folyamatot, és egyszerűen törölje a mezőt, amelyet korábban hozzáadott. 

Válassza ki a **kezelése** az aktuális oldal összes felhasználósorára kapcsolatos beállítások listájának megjelenítéséhez. 

Válassza a **tiszta** szeretné állítani az alapértelmezés szerinti telepítési állapota. Az aktuális oldalon személyes beállítások törlődnek. Nincs olyan visszavonási művelet, ezért csak akkor használja ezt a beállítást, ha biztosak vagyunk abban, hogy kívánja-e a lap visszaállítása. 

Válassza az **Importálás** lehetőséget, hogy egy korábban ön vagy más által létrehozott testreszabási fájlból importáljon testreszabási beállításokat ehhez az oldalhoz. Ha testreszabási beállításokat importál, azzal törli azokat a testreszabási beállításokat, amelyeket a teljes lapon elvégzett, és ehelyett a kijelölt fájl testreszabási beállításait alkalmazza. Ha el akarja menteni vagy meg akarja osztani a testreszabási beállításokat, válassza ki az **Exportálás** lehetőséget a testreszabási lehetőségek fájlként mentéséhez. 

Válassza ki a **Bezár** gombot az eszköztár bezárásához és ahhoz, hogy visszatérjen az oldal korábbi interaktív állapotába. 

A Személyes beállítások eszköztárral a mentés implicit lesz. A személyes beállítások azonnal érvényesek, ahogy beállítja őket, nem szükséges a **Mentés** gombra kattintania. Néhány esetben látható egy lakatot ábrázoló ikon mellett egy elem eszköz kiválasztásakor. Ez azt jelenti, hogy annak érdekében, hogy a lap megfelelően működhet, nem módosíthatja a kijelölt eszköz tulajdonságait. Ha a Személyes beállítások eszköztár meg van nyitva, az oldal nem lesz interaktív. Nem tud megadni adatokat, illetve kibontani vagy összecsukni szakaszokat.

## <a name="explicit-personalization-adding-a-tile-or-list-to-a-workspace"></a>Explicit személyes beállítások: Csempe vagy lista hozzáadása a munkaterülethez
Néhány listákat tartalmazó oldal személyre szabható a Műveleti ablaktáblán, a Személyes beállítások csoport alatt a Beállítások fülön. Válassza ki a **Hozzáadás a munkaterülethez** menüpontot a legördülő lista megnyitásához, amely segítségével megtekintheti az aktuális listában található információkat (szűrt, rendezett vagy alapértelmezett) a Munkaterületen listaként vagy összegző címként (amely a listában a cikkek számának megjelenítésére is használható). 

[![Add to workspace](./media/personalization-addtoworkspace.png)](./media/personalization-addtoworkspace.png) 

Ha listát szeretne hozzáadni a munkaterülethez, először rendezze vagy szűrje a listát a kívánt információ szerint, majd válassza ki a Hozzáadás a munkaterülethez párbeszédpanelt. Ezután válassza ki a kívánt munkaterületet, majd válassza ki a **Lista** beállítást a bemutató legördülő listából. Ha kiválasztja a **Lista** beállítást, egy párbeszédpanel nyílik meg, amely lehetővé teszi a listában megjeleníteni kívánt oszlopok és a listához tartozó címke kiválasztását úgy, ahogy a munkaterületen meg fog jelenni. 

A munkaterület címének hozzáadásához először szűrnie kell a listát, hogy az összesíteni kívánt adatokat megjelenítse (vagy azokat, amikhez gyors elérést szeretne). Azután nyissa meg a Hozzáadás a munkaterülethez legördülő párbeszédpanelt. Ezután válassza ki a kívánt munkaterületet, majd válassza ki a **Csempe** beállítást a bemutató legördülő listából. Ha kiválasztja a **Csempe** beállítást, akkor egy párbeszédpanel fog megnyílni, amely engedélyezi a csempe címének megadását és annak eldöntését, hogy a csempe mutasson-e számot. Ha egy csempét a munkaterületre helyeztünk, akkor a csempe lehetővé teszi az aktuális oldal megnyitását a munkaterületről, és a csempével kapcsolatos információk listáját jeleníti meg. 

Ha egy listát vagy csempét hozzáad a munkaterülethez, megnyithatja a munkaterületet és újrarendezheti a listát vagy a csempét abban a csoportban, ahova elhelyezte.

## <a name="explicit-personalization-adding-a-summary-from-a-workspace-to-a-dashboard"></a>Explicit személyes beállítások: Összegzés hozzáadása a munkaterületről az irányítópultba
Néhány munkaterület tartalmazhat száma követ (Mozaik azokat a számokat), akkor is szeretne az irányítópulton látható. A munkaterületen, kattintson a jobb gombbal egy darab követ, és válassza ki **személyre szabása**. Válassza ki a **Kitűzés az irányítópultra** lehetőséget. Ha a következő alkalommal a kiválasztott irányítópultra navigál (vagy frissíti az oldalt), láthatja a számot a munkaterület navigációs csempéje alatt az irányítópulton.

## <a name="explicit-personalization-personalizing-your-dashboard"></a>Explicit személyes beállítások: Az irányítópult személyre szabása
Az irányítópult nem gyakran Dynamics 365 műveletek megnyitásakor megjelenik az első oldalon. Az irányítópult testreszabásával átnevezheti a munkaterület navigációs csempéit, beállíthatja, hogy csak a kívánt csempéket lássa, átnevezheti a csempéket, vagy a kívánt sorrendbe rendezheti őket. Az irányítópult testreszabásához jelöljön ki egy csempét, majd kattintson rá jobb gombbal a helyi menü megnyitásához. Válassza ki a helyi menü **Személyes beállítások** menüpontját. Ha a kiválasztott csempét szeretné elrejteni, átnevezni vagy kihagyni, megváltoztathatja ezt a közvetlenül megjelenő Tulajdonságok ablakon. Ha szeretné módosítani a csempék elrendezését, válassza ki a **Képernyő személyre szabása** beállítást a Tulajdonságok ablakban a Személyes beállítások eszköztár megnyitásához. Az Áthelyezés eszköz segítségével újrarendezheti a csempéket.

## <a name="administration-of-personalization"></a>Személyes beállítások adminisztrálása
Lehetséges személyre szabni egy oldalt és megosztani más felhasználókkal úgy, hogy egyszerűen exportálja a személyre szabott oldalt és megkéri a többi felhasználót, hogy navigáljon a személyre szabott oldalra és importálja a testreszabási fájlt, amit létrehozott. Ha egy felhasználó rendszergazdai jogokkal rendelkezik, akkor kezelheti más felhasználók személyes beállításait a **Személyes beállítások** lapon. Nézze meg a b oldalt. A **Személyes beállítások** lapon két fület talál, az egyik a **Rendszer**, a másik a ** Felhasználók**. 

**Rendszer:** Itt tudja ideiglenesen letiltani vagy „kikapcsolni” a rendszerben szereplő személyes beállításokat. Ez nem törli a személyes beállításokat, hanem az alapértelmezett állapotra állítja vissza a felületeket. Később újra engedélyezheti a személyes beállításokat, hogy az egyes felhasználói felületeken újra érvényesek legyenek a személyes beállítások. Lehetséges az összes felhasználó személyes beállításainak törlése is. Ne feledje, hogy a személyes beállítások törlésekor nincs lehetőség a személyes beállítások automatikus újraengedélyezésére a rendszerben. Ellenőrizze, hogy exportálta azokat a személyes beállításokat, amelyeket később importálni szeretne, mielőtt végrehajtja ezt a lépést. 

**Felhasználók:** Itt állíthatja be, hogy melyik felhasználó tudjon implicit vagy explicit személyes beállításokat elmenteni. Meghatározhatja azt is, hogy egy bizonyos felületen mely felhasználók állíthatnak be implicit vagy explicit személyes beállításokat. Végül importálhatja, exportálhatja vagy törölheti az egyes felhasználók személyes beállításait. 

**Megjegyzés:** Az eredeti verzióban a személyes beállítások adminisztrációja csak egy felhasználóra engedélyezett.


