---
title: "A felhasználói élmény testreszabása"
description: "A témakör azt ismerteti, hogyan lehet személyre szabni a Microsoft Dynamics 365 Finance and Operations rendszert."
author: RobinARH
manager: AnnBe
ms.date: 08/03/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SysUserSetup
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 62363
ms.assetid: 57b445d7-3e9e-4228-8728-f63b9dbd77a3
ms.search.region: Global
ms.author: tlefor
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: cf2ad9f95035aaf004f2da779a8492ff2d91d399
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="personalize-the-user-experience"></a>A felhasználói élmény testreszabása

[!include[banner](../includes/banner.md)]


A témakör azt ismerteti, hogyan lehet személyre szabni a Microsoft Dynamics 365 Finance and Operations rendszert.

A Microsoft Dynamics 365 Finance and Operations testreszabására számos lehetőség van. Néhány személyes beállítás választási lehetőségként jelenik meg a beállítások oldalon a beállítások listájában. Vannak rejtett személyes beállítások, például a Finance and Operations nyomon követi a rácsoszlopok szélességét vagy a gyorslapok összecsukott/kibontott állapotát, ha ezt beállítja. Vannak explicit személyes beállítások. Az explicit személyes beállításokhoz meg kell adnia egy interaktív személyre szabási módot és módosítania kell az oldal megjelenését azzal, hogy közvetlenül kezeli az elem megjelenését és viselkedését az oldalon. 

A Finance and Operations szoftverben megadott bármilyen beállítás csak arra a felhasználóra érvényes, aki megadta őket, és függetlenek attól, hogy milyen vállalattal kommunikál. Ha egy felhasználó az oldalon módosításokat hajt végre, az nem módosítja a rendszerben más felhasználók kezelési felületét.

## <a name="systemwide-options-for-the-current-user"></a>Az egész rendszerre érvényes beállítások az aktuális felhasználó számára
A navigációs sávon található egy fogaskerék kép, amelyet **Beállítások** menügombnak hívnak. A **Beállítások** menü megnyitásával választási lehetőségek jelennek meg. A **Beállítások** kijelölésével megnyílik a felhasználói **Beállítások** oldal. Ott négy beállítási lapot talál: 

-   **Vizuális** – A színtéma kiválasztására és az oldalelemek alapértelmezett méretének beállítására használható.
-   **Preferenciák:** – Itt kiválaszthatja a Finance and Operations alapértelmezett preferenciáit, amelyek az induláskor betöltődnek, többek között a vállalatot, a kezdőlapot és az alapértelmezett nézet/szerkesztés módot (amely meghatározza, hogy egy oldal csak megtekinthető-e, vagy minden megnyitáskor szerkeszthető). Itt találja meg a nyelvet, az időzónát, illetve a dátum, az idő és a számok formátumának beállítását. A legutóbbi verziókban ez az oldal különböző preferenciákat tartalmaz, amely eltér a különböző verziókban.
-   **Fiók:** – Itt adhatja meg a felhasználói azonosítót és más fiókhoz kapcsolódó beállításokat.
-   **Munkafolyamat:** – Itt adhatja meg a munkafolyamattal kapcsolatos beállításokat.

## <a name="implicit-personalizations"></a>Implicit testreszabás
Az implicit személyes beállítások olyan személyes beállítások, amelyeket olyan vezérlőkkel hajt végre, amelyek megjegyzik az elemek aktuális láthatósági állapotát. 

**Rácsoszlopok:** – Megadhatja egy oszlop szélességét a listában, ha az oszlop fejlécén található méretező sávot balra vagy jobbra húzza a kívánt szélességig. A Finance and Operations rendszer eltárolja a kívánt szélességet, és az oszlopokat így jeleníti meg minden alkalommal, amikor megnyitja a listát tartalmazó oldalt. 

**Gyorslapok:** – Néhány lapon kibontható szakaszok vannak, amelyeket Gyorslapoknak hívunk. A Finance and Operations eltárolja, mely gyorslapokat bontott ki, és mely gyorslapokat csukott össze. Minden alkalommal, amikor visszatér az oldalra, ugyanazok a gyorslapok lesznek kibontva vagy összecsukva, ahogy az utolsó használatkor hagyta őket. Ebben a cikkben bemutatjuk, hogyan változtassa meg a gyorslap-szakaszok sorrendjét. Bizonyos esetekben a gyorslap összecsukása javíthatja a teljesítményt, mivel a Finance and Operations szoftvernek nem kell betöltenie annak a gyorslapnak az információit egészen addig, amíg a gyorslapot nem bontjuk ki. 

**Adatterületek:** – Néhány oldal tartalmaz egy adatterület-panel nevű szakaszt. Ez az ablak csak olvasható információkat tartalmaz az aktuális oldal tartalmáról. Az adatterület-panel minden szakaszát adatterületnek hívjuk. Akkor kibontunk vagy összecsukunk egy adatterületet, a Finance and Operations tárolja a beállításokat. Bizonyos esetekben az adatterület összecsukása javíthatja a teljesítményt, mivel a Finance and Operations szoftvernek nem kell betöltenie annak az adatterületnek az információit egészen addig, amíg az adatterületet nem bontjuk ki.

## <a name="explicit-personalizations-using-the-personalization-toolbar"></a>Explicit testreszabás a Személyes beállítások eszköztárral
Minden személy és vállalat más nézeteket vall arról, mely adatok a legfontosabbak számukra, vagy mely adatok nem szükségesek az üzlet működéséhez. A Finance and Operations személyre szabásához és a hatékony élményhez az a kulcs, hogy képes-e az információkat rendezni, egymáshoz kapcsolni vagy elrejteni. 

Az explicit személyre szabások olyan személyre szabások, amelyeket kifejezetten azzal a szándékkal hajtunk végre, hogy megváltoztassuk egy elem vagy lap megjelenését vagy működését, egy személyre szabási menü kiválasztásával. Az explicit személyre szabás legalapvetőbb típusa az, ha a jobb egérgombbal kattintunk egy elemre, és a **Személyre szabás** lehetőséget választjuk. (Megjegyzendő, hogy az oldalon nem minden elem szabható személyre.) Ha a személyre szabásnak ezt a módszerét választja, akkor megjelenik az elem tulajdonság ablaka. 

[![Egy elem tulajdonságainak személyre szabása](./media/personalization-element-properties.jpg)](./media/personalization-element-properties.jpg) 

Ekképpen fogja személyre szabni az oldalon található elemet, ha egyszerűen csak meg akarja változtatni az elem címkéjét, el akarja rejteni, hogy ne jelenjen meg az oldalon (ez semmilyen adatot nem módosít, egyszerűen csak nem jeleníti meg az információt), vagy be akarja emelni az információt a gyorslapok összefoglaló szakaszába (ha az elem egy gyorslap), mezőt szeretne kihagyni a Tab billentyűvel való lépkedés közben, vagy nem szerkeszthetővé tenni az adatot a „Nem szerkeszthető” beállítás kiválasztásával. 

Ha elemeket szeretne áthelyezni, elrejteni vagy módosítani, akkor a Személyes beállítások eszköztárat használhatja, amely az elemek Tulajdonságok ablakáról érhető el a **Képernyő személyre szabása** beállítást kiválasztva. A személyre szabási eszköztár elérhető a képernyőn műveleti ablaktábláján is, a **Lehetőségek** lap Személyre szabás csoportja alatt. Válassza a **Képernyő személyre szabása** lehetőséget, és a személyre szabási eszköztár megjelenik. 

[![Személyes beállítások eszköztára](./media/personalization-personalizationtoolbar.jpg)](./media/personalization-personalizationtoolbar.jpg)

A Személyes beállítások eszköztára számos személyre szabási művelettel rendelkezik. Válassza ki a **Kiválaszt** eszközt, ha egyszerre több elemet szeretne kijelölni, és a tulajdonságaikat egyszerre szeretné megváltoztatni. Először kattintson a Kijelölés eszközre, majd kattintson arra az elemre, amelynek a tulajdonságait módosítani akarja. Amikor kiválaszt egy elemet, az elem tulajdonságok ablaka nyílik meg, és ezen az elem bármilyen tulajdonsága módosítható. Megismételheti a folyamatot más elemekkel is, amelyek a képernyőn testre szabhatók. Bizonyos esetekben, ha kijelöl egy elemet, azt láthatja, hogy néhány tulajdonság nem módosítható. Ez azt jelenti, hogy a Finance and Operations nem engedélyezi a tulajdonság módosítását az elem aktuális használata közben. Kötelező mezőt például nem tud elrejteni. 

Válassza ki az **Áthelyezés** eszközt, ha egy elemet ki akar jelölni és az elemek jelenlegi csoportján belül egy másik helyre szeretné áthelyezni. (A szülőcsoporton kívülre nem helyezhető át egy elem). Először kattintson az Áthelyezés eszközre, majd kattintson arra az elemre, amelyet át akar helyezni. Ha jobb gombbal az áthelyezni kívánt elemre kattint, a Finance and Operations ellenőrzi a képernyőn azokat a helyeket, ahova az elemet át lehet helyezni, és a „drop zónák” sorozatát a területek melletti színes, félkövér szöveggel jelzi, mialatt az elemet az aktuális csoportban húzza. 

Válassza ki az **Elrejtés** eszközt egy elem kiválasztásához és elrejtéséhez. Egy elem elrejtéséhez válassza ki az Elrejtés eszközt, és kattintson arra az elemre, amelyet el kíván rejteni. Ha kiválasztja az Elrejtés eszközt, akkor minden aktuálisan elrejtett elem láthatóvá válik egy árnyékolt tárolóban, azután kiválaszthatja, mely elemek elrejtését szeretné megszüntetni. Válassza ki a Kijelölés eszközt, hogy lássa, hogy fog kinézni az oldal a kiválasztott elemek elrejtésével. Válassza ki az **Összegzés** eszközt, ha egy számérték vagy karakterlánc mezőt szeretne megjeleníteni a gyorslapok összegzés területén. Az Összegzés eszköz csak olyan mezőkre érvényes, amelyek a gyorslap szakaszban vannak. Ha kiválasztja az Összegzés eszközt, a Finance and Operations minden mezőt megjelenít egy árnyékolt tárolóban, amelyet összegző mezőként választott ki. Interaktívan hozzáadhat és eltávolíthat mezőket a gyorslap összegzőből, ha a mezőre kattint. 

Válassza ki a **Kihagyás** eszközt egy elem eltávolítására az oldal billentyűparancs-sorozatából Ha kiválasztja a Kihagyás eszközt, minden aktuálisan kihagyott eszköz megjelenik egy árnyékolt tárolóban, és kiválaszthatja őket a kihagyott elem kijelölésével, hogy újra a Fülek között szerepeljenek. 

Válassza ki a **Szerkesztés** eszközt, ha egy elemet Szerkeszthető vagy Nem szerkeszthető állapotúra akar állítani. Ha kiválasztja a Szerkesztés eszközt, akkor minden aktuálisan zárolt elem megjelenik egy árnyékolt tárolóban, azután kiválaszthatja, mely elemeket szeretne szerkeszthetővé tenni. Vegye figyelembe, hogy egyes mezők kötelezőek, és nem tehetők zárolttá. Az ilyen mezők mellett egy lakat ikon jelenik meg. 

Válassza ki a **Hozzáadás** eszközt új mező felvételéhez a lapra. A hozzáadás eszközzel nem hozható létre új mező, viszont hozzáadhat olyan mezőket, amelyek az aktuális oldal definíciójában szerepelnek, de nem jelennek meg az oldalon. Ha kiválasztja a Hozzáadás eszközt, először ki kell választania azt a csoportot vagy területet, ahol hozzá akarja adni a mezőt. A kijelölt szakasszal kapcsolatos mezők listája egy párbeszédpanelen jelenik meg. A párbeszédpanelen kiválaszthat egy vagy több hozzáadandó mezőt, majd kattintson a Beszúrás gombra. Amennyiben szeretne megszüntetni egy mezőt, amelyet korábban hozzáadott, ismételje meg a folyamatot, és egyszerűen törölje a mezőt, amelyet korábban hozzáadott. 

Válassza ki a **Kezelés** gombot az aktuális oldal testreszabásához kapcsolódó beállítások listájának megjelenítéséhez 

Válassza az **Alapértelmezett** gombot az alapértelmezett, telepítési beállítások visszaállításához Az aktuális oldal testreszabott beállításai törlődnek. Nincs lehetőség a művelet visszavonására, ezért csak akkor használja ezt a lehetőséget, ha biztos abban, hogy az oldalt az alaphelyzetbe kívánja állítani. 

Válassza az **Importálás** lehetőséget, hogy egy korábban ön vagy más által létrehozott testreszabási fájlból importáljon testreszabási beállításokat ehhez az oldalhoz. Ha testreszabási beállításokat importál, azzal törli azokat a testreszabási beállításokat, amelyeket a teljes lapon elvégzett, és ehelyett a kijelölt fájl testreszabási beállításait alkalmazza. Ha el akarja menteni vagy meg akarja osztani a testreszabási beállításokat, válassza ki az **Exportálás** lehetőséget a testreszabási lehetőségek fájlként mentéséhez. 

Válassza ki a **Bezár** gombot az eszköztár bezárásához és ahhoz, hogy visszatérjen az oldal korábbi interaktív állapotába. 

A Személyes beállítások eszköztárral a mentés implicit lesz. A személyes beállítások azonnal érvényesek, ahogy beállítja őket, nem szükséges a **Mentés** gombra kattintania. Bizonyos esetekben látható egy lakat ikon az elem mellett, amikor kiválaszt egy eszközt. Ez azt jelenti, hogy az oldal megfelelő működéséhez nem szabad módosítani az eszközzel kapcsolatos tulajdonságokat. Ha a Személyes beállítások eszköztár meg van nyitva, az oldal nem lesz interaktív. Nem tud megadni adatokat, illetve kibontani vagy összecsukni szakaszokat.

## <a name="explicit-personalization-adding-a-tile-or-list-to-a-workspace"></a>Explicit személyes beállítások: Csempe vagy lista hozzáadása a munkaterülethez
Néhány listákat tartalmazó oldal személyre szabható a Műveleti ablaktáblán, a Személyes beállítások csoport alatt a Beállítások fülön. Válassza ki a **Hozzáadás a munkaterülethez** menüpontot a legördülő lista megnyitásához, amely segítségével megtekintheti az aktuális listában található információkat (szűrt, rendezett vagy alapértelmezett) a Munkaterületen listaként vagy összegző címként (amely a listában a cikkek számának megjelenítésére is használható). 

[![Hozzáadás munkaterületenként](./media/personalization-addtoworkspace.png)](./media/personalization-addtoworkspace.png) 

Ha listát szeretne hozzáadni a munkaterülethez, először rendezze vagy szűrje a listát a kívánt információ szerint, majd válassza ki a Hozzáadás a munkaterülethez párbeszédpanelt. Ezután válassza ki a kívánt munkaterületet, majd válassza ki a **Lista** beállítást a bemutató legördülő listából. Ha kiválasztja a **Lista** beállítást, egy párbeszédpanel nyílik meg, amely lehetővé teszi a listában megjeleníteni kívánt oszlopok és a listához tartozó címke kiválasztását úgy, ahogy a munkaterületen meg fog jelenni. 

A munkaterület címének hozzáadásához először szűrnie kell a listát, hogy az összesíteni kívánt adatokat megjelenítse (vagy azokat, amikhez gyors elérést szeretne). Azután nyissa meg a Hozzáadás a munkaterülethez legördülő párbeszédpanelt. Ezután válassza ki a kívánt munkaterületet, majd válassza ki a **Csempe** beállítást a bemutató legördülő listából. Ha kiválasztja a **Csempe** beállítást, akkor egy párbeszédpanel fog megnyílni, amely engedélyezi a csempe címének megadását és annak eldöntését, hogy a csempe mutasson-e számot. Ha egy csempét a munkaterületre helyeztünk, akkor a csempe lehetővé teszi az aktuális oldal megnyitását a munkaterületről, és a csempével kapcsolatos információk listáját jeleníti meg. 

Ha egy listát vagy csempét hozzáad a munkaterülethez, megnyithatja a munkaterületet és újrarendezheti a listát vagy a csempét abban a csoportban, ahova elhelyezte.

## <a name="explicit-personalization-adding-a-summary-from-a-workspace-to-a-dashboard"></a>Explicit személyes beállítások: Összegzés hozzáadása a munkaterületről az irányítópultba
Néhány munkaterület számozott csempét tartalmaz (olyan csempéket, amelyeken számok vannak), amelyeket lehet, hogy az irányítópulton is látni szeretne. A munkaterületen kattintson jobb gombbal egy számozott csempére, majd kattintson a **Személyes beállítások** menüpontra. Válassza ki a **Kitűzés az irányítópultra** lehetőséget. Ha a következő alkalommal a kiválasztott irányítópultra navigál (vagy frissíti az oldalt), láthatja a számot a munkaterület navigációs csempéje alatt az irányítópulton.

## <a name="explicit-personalization-personalizing-your-dashboard"></a>Explicit személyes beállítások: Az irányítópult személyre szabása
Az irányítópult legtöbbször az első oldal, amelyet a Finance and Operations megnyitásakor lát. Az irányítópult testreszabásával átnevezheti a munkaterület navigációs csempéit, beállíthatja, hogy csak a kívánt csempéket lássa, átnevezheti a csempéket, vagy a kívánt sorrendbe rendezheti őket. Az irányítópult testreszabásához jelöljön ki egy csempét, majd kattintson rá jobb gombbal a helyi menü megnyitásához. Válassza ki a helyi menü **Személyes beállítások** menüpontját. Ha a kiválasztott csempét szeretné elrejteni, átnevezni vagy kihagyni, megváltoztathatja ezt a közvetlenül megjelenő Tulajdonságok ablakon. Ha szeretné módosítani a csempék elrendezését, válassza ki a **Képernyő személyre szabása** beállítást a Tulajdonságok ablakban a Személyes beállítások eszköztár megnyitásához. Az Áthelyezés eszköz segítségével újrarendezheti a csempéket.

## <a name="administration-of-personalization"></a>Személyes beállítások adminisztrálása
Az oldal személyre szabása után más felhasználókkal is megoszthatja a személyes beállításait a személyre szabott oldal exportálásával. Ezután megkérheti a többi felhasználót, hogy lépjenek a személyre szabott lapra, és importálják az ön által létrehozott személyre szabási fájlt.

Rendszergazdai jogokkal rendelkező felhasználók más felhasználók személyes beállításait is kezelhetik a **Személyes beállítások** lapon. Ezen a lapon négy fül van: 

- **Rendszer:** – Itt tudja ideiglenesen letiltani vagy kikapcsolni a rendszerben szereplő személyes beállításokat. Ebben az esetben nem törli a személyre szabott beállításokat. Ehelyett csak visszaállítja az összes lapot azok alapértelmezett értékére. Amennyiben későbbólújra engedélyezi a személyes beállításokat, a rendszer minden felhasználói felületen újból alkalmazza a személyes beállításokat. Lehetséges az összes felhasználó személyes beállításainak törlése is. Ne feledje, hogy a személyes beállítások törlésekor nincs lehetőség a személyes beállítások automatikus újraengedélyezésére a rendszerben. Ezért a lépés végrehajtása előtt ellenőrizze, hogy exportálta mindazokat a személyes beállításokat, amelyeket később esetleg importálni szeretne.
- **Felhasználók** – Megadhatja, hogy a felhasználók implicit vagy explicit személyre szabást hajthatnak végre. Meghatározhatja azt is, hogy egy bizonyos lapon mely felhasználók állíthatnak be implicit vagy explicit személyes beállításokat. Végül importálhatja, exportálhatja vagy törölheti az egyes felhasználók személyes beállításait.
- **Importálás** – Importálhat egy személyre szabási beállítást egy vagy több felhasználó számára. Ezt a fület akkor használja, miután létrehozott egy személyre szabást egy lapon vagy egy munkaterületen, majd személyre szabási fájlként exportálta azt. A személyre szabási fájl importálásához és egy vagy több felhasználóhoz történő alkalmazásához válassza ki az egyes felhasználókat az összes felhasználó listáján vagy szűrje meg egy adott szerepkör alapján, majd válassza ki az adott szerepkörben lévő felhasználókat. Miután kiválasztotta a személyre szabást használó felhasználókat, kattintson az **Importálás** lehetőségre, és válassza ki a személyre szabási fájlt. A rendszer ellenőrzi a személyre szabást, és alkalmazza az összes kijelölt felhasználóra, amikor azok legközelebb megnyitják a kijelölt lapot.
- **Törlés** – A lap vagy a munkaterület személyre szabása egy vagy több felhasználó esetében is törölhető. Első lépésként válassza ki azt a lapot vagy munkaterületet, amelyről törölni szeretné a személyre szabási beállításokat. Ezután a felhasználói listában válassza ki a kívánt felhasználókat, vagy szűrje őket egy adott szerepkörön belül, majd válassza ki az adott szerepkörben lévő felhasználókat. Miután kiválasztotta a lapot vagy a munkaterületet és a felhasználókat is, kattintson a **Törlés** lehetőségre. A kiválasztott felhasználók által a kiválasztott lapra vagy munkaterületre alkalmazott valamennyi személyre szabási beállítás törlődik. Ez a művelet nem vonható vissza. Ugyanakkor ha a lapnak vagy a munkaterületnek létezik mentett személyre szabási beállítása, ez a beállítás visszaimportálható.

## <a name="personalization-of-inventory-dimensions"></a>A készletdimenziók személyre szabása

Amikor a készletdimenziók beállítását szabja személyre egy lapon, fontolja meg azokat a beállításokat, amelyek segítségével létrehozta a **Megjelenítendő dimenzió** lehetőséget. Például ha a személyre szabást a Kötegszám készletdimenziója oszlop elrejtésére használja, és a lap következő megnyitásakor az oszlop megjelenik, ez azért következhet be, mert a Dimenzió megjelenítési beállításai határozzák meg a megjelenítendő készletdimenzió oszlopokat. 

A Dimenzió megjelenítési beállításai minden lapon érvényesülnek, és ezek a beállítások az egyes lapok minden személyre szabott készletdimenzió-mező beállításait felülírják. 

Például a Kötegszám készletdimenziója esetében ezt a dimenziót törölni kellene a **Dimenziók megjelenítése** lehetőségben, hogy a tábla ne jelenítse meg ezt az oszlopot. Végül a módosítás nemcsak egy adott lapon, hanem minden lapon érvényes volna.

