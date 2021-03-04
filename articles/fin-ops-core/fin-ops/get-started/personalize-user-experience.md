---
title: A felhasználói élmény testreszabása
description: Ez a témakör bemutatja, hogyan lehet személyre szabni az alkalmazást.
author: jasongre
manager: AnnBe
ms.date: 09/11/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserSetup, DefaultDashboard
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 62363
ms.assetid: 57b445d7-3e9e-4228-8728-f63b9dbd77a3
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e46c392c43b63ef443f66d8ea8f9e91a9df3d126
ms.sourcegitcommit: f5e31c34640add6d40308ac1365cc0ee60e60e24
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/08/2020
ms.locfileid: "4693232"
---
# <a name="personalize-the-user-experience"></a>A felhasználói élmény testreszabása

[!include [banner](../includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet személyre szabni az alkalmazást, illetve a következő témákat is taglalja: 

- **Az egész rendszerre érvényes beállítások** – Ezek a személyre szabási beállítások egy beállítási oldalon készülnek, és minden felhasználó számára elérhetők. Példák: a stílus és az időzóna. 
- **Korlátozott személyre szabási hozzáférés** – Ezen a hozzáférési szinten a szokásos oldalhasználathoz társított felhasználói műveleteket automatikusan menti az alkalmazás, és visszaállítja amikor legközelebb meglátogatja ezt a lapot. Például az alkalmazás visszaállítja a rácsoszlopok szélességét, ha ezt beállítja, vagy a gyorslapok összecsukott/kibontott állapotát. 
- **Teljes személyre szabási hozzáférés** – Ezen a hozzáférési szinten a felhasználók hozzáférhetnek az alkalmazás minden személyre szabási lehetőségéhez. Ezek a felhasználók főként a **Személyre szabás** eszköztárhoz férnek hozzá. 
- **Személyre szabási lehetőségek megosztása** – A teljes személyre szabási hozzáféréssel rendelkező felhasználók exportálhatják a lap személyre szabási lehetőségeit, és megoszthatják őket más felhasználókkal.
- **A személyre szabás felügyelete** – A jogosult felhasználók hozzáférhetnek a **Személyre szabás** felügyelet laphoz, és minden személyt egy szervezeti szinten kezelhetnek. 

## <a name="system-wide-options-for-the-current-user"></a>Az egész rendszerre érvényes beállítások az aktuális felhasználó számára

A **Felhasználói beállítások** lap tartalmaz több rendszerszintű beállítást az aktuális felhasználóra. Ezek a beállítások minden felhasználó számára elérhetők, még azok számára is, akik nem kaptak hozzáférést a személyre szabáshoz. A **Felhasználói beállítások** oldal megnyitásához válassza a **Beállítások** gombot a navigációs sávon, és jelölje be a **Felhasználói beállításokat**. A **Felhasználói beállítások** oldalhoz négy lap tartozik különböző felhasználói beállításokkal:

- **Vizuális** – A színtéma kiválasztása és az oldalelemek alapértelmezett méretének beállítása.
- **Beállítások** – Válassza ki a rendszer megnyitásakor mindig használt alapértelmezett értékeket. Az értékek között található a vállalat, a kezdőlap és az alapértelmezett megjelenítési/szerkesztési mód. (A megjelenítési/szerkesztési mód határozza meg, hogy egy oldalt zárolt vagy megnyitott a szerkesztésre, minden alkalommal, amikor megnyitja.) Ez a lap a nyelv, az időzóna és a dátum, az idő- és számformátumok beállításait is lehetővé teszi. Végül ezen a lapon több vegyes beállítás található, amelyek az egyes kiadások esetében eltérők lehetnek.
- **Fiók:** – Itt tekintheti vagy adhatja meg a felhasználónevet és más fiókhoz kapcsolódó beállításokat.
- **Munkafolyamat** – Válassza ki a munkafolyamattal kapcsolatos beállításokat.

A felhasználói beállítások módosításán túl, megtekintheti és törölheti is a használati adatokat és a testreszabásokat a **Felhasználói beállítások** lapon. A használati adatok megtekintéséhez válassza ki a Műveleti ablaktáblán a **Használati adatok** lehetőséget. A **Személyre szabás** lapon tekintheti meg és kezelheti a személyes módosításokat, amelyeket végrehajtott a lapokon a rendszerben. Ezen a lapon alaphelyzetbe állíthatók a funkció-ábrafeliratok (azaz az új rendszerelemeket bemutató előugró ablakok) is. Ezt követően a korábban észlelt szolgáltatásokról ismételten figyelmeztetést kap.

> [!NOTE]
> Ha be van kapcsolva a [Mentett nézetek](saved-views.md) funkció , akkor a Művelet panel **Felhaszálói beállítások** lapján megtekintheti és kezelheti a **Testreszabást**.

## <a name="restricted-personalization-access-formerly-implicit-personalizations"></a>Korlátozott személyre szabási hozzáférés (korábban implicit személyre szabások)

A **korlátozott személyre szabási hozzáférési** szinten a szokásos oldalhasználathoz társított felhasználói műveleteket automatikusan menti az alkalmazás, és visszaállítja amikor legközelebb meglátogatja ezt a lapot. Nincs szükség explicit mentési műveletre. 

Itt láthatók azoknak a műveleteknek a listája, amelyek a szokásos oldalhasználathoz tartoznak, és amelyeket a korlátozott személyre szabási hozzáférés tartalmaz: 

- **Rácsoszlopok szélessége:** – Megadhatja egy oszlop szélességét a listában, ha az oszlop fejlécén található méretező sávot balra vagy jobbra húzza a kívánt oszlopszélességig. Az alkalmazás tárolja az oszlop beállított szélességét. Majd minden alkalommal, amikor megnyitja a lapot, átméretezi az oszlop szélességét.
- **Rács lábléce és oszlopok összegei** – *(Csak az új rács vezérlőelem bekapcsolásakor érhető el)* Eldöntheti, hogy megjeleníti-e a rács numerikus oszlopainak alján látható összesítést, valamint azt, hogy a rács ábléce látható legyen-e. Az alkalmazás ezeket a preferenciákat tárolja, és az oldal következő megnyitásakor alkalmazza őket. További információkért lásd az [Rácsfunkciók](grid-capabilities.md) részt. 
- **Gyorslapok** – Néhány lapon kibontható szakaszok vannak, amelyeket *Gyorslapoknak* hívunk. Az alkalmazás tárolja a már kibontott vagy összecsukott gyorslapok adatait. A következő alkalommal, amikor megnyitja a lapot, ugyanazon gyorslap ki lesz bontva és össze lesz csukva, a lappal folytatott utolsó kommunikációt alapján. Bizonyos esetekben a gyorslap összecsukása javíthatja a teljesítményt, mivel az alkalmazásnak nem kell betöltenie azoknak a gyorslapoknak az információit egészen addig, amíg a gyorslapokat nem bontjuk ki. Amint később a témakörben elmagyarázzuk, a lapon módosítható a gyorslapok sorrendje.
- **Adatterületek** – Egyes lapokhoz tartozik egy **Kapcsolódó információk** ablaktábla jelenik meg, amely a lap aktuális tárgyához kapcsolódó írásvédett adatokat jelenít meg. Az **Kapcsolódó információk** minden szakaszának neve: *Adatterület*. Ki lehet bontani vagy össze lehet csukni a **Kapcsolódó információk** megjelenítését, illetve kibonthatók és összecsukhatók az egyes Adatterületek. Az alkalmazás tárolja ezeket a beállításokat. Legközelebb ha megnyitja a lapot a **Kapcsolódó információk** panel és az egyes Adatterületek állapota visszaáll, és ki lesz bontva vagy össze lesz csukva a lap utolsó kommunikációja alapján. Bizonyos esetekben a **Kapcsolódó információ** ablakpanel vagy az adatterület összecsukása javíthatja a teljesítményt, mivel az alkalmazásnak nem kell betöltenie azoknak a adatterületeknek az információit egészen addig, amíg azokat nem bontjuk ki.
- **Műveleti ablaktábla** – A *Műveleti ablak* a legtöbb oldal tetején jelenik meg. A műveleti ablak gombjaival számos műveleteket hajthat végre az aktuális lapon. Ezek a gombok gyakran a lapokon vannak csoportosítva. A teljes műveletpanel lehet nyitottan *kitűzve*, ahogy alapértelmezés szerint összecsukva is. A következő alkalommal, amikor megnyitja a Művelet panelt, ugyanazon gyorslap ki lesz nyitva vagy össze lesz csukva, a lappal folytatott utolsó interakció alapján. Ha megnyitotta a Műveleti ablaktáblát, akkor a program a legutóbb használt lapot jeleníti meg.
- **QuickFilters** – A *Gyorsszűrő* sok rács felett jelenik meg. A Gyorsszűrő lehetővé teszi a rács egyetlen kiválasztott oszlop alapján történő szűrését. Az alkalmazás tárolja az oszlopot, amelynek alapján szűrt. Ezt követően, a lap következő megnyitásakor a rács ugyanazon oszlopra fog szűrni alapértelmezettként. Azonban ezután még mindig kiválaszthat egy másik oszlopot, amire szűrni szeretné a rácsot.
- **Oszlopfejléc-szűrők** – A rács az *Oszlopfejléc-szűrők* segítségével történő szűréskor módosíthatja a szűrési operátort a megtalálni a kívánt adatok szerint. Például módosíthatja a kezelőt a **kezdődik** lehetőségről a **pontosan** lehetőségre. Oszlop fejléce szűrő használatakor és a szűrési operátor változtatásakor, az alkalmazás mindig tárolja a módosítást. Majd visszaállítja szűrési operátort ha legközelebb szűr az oszlopra.
- **Navigációs ablak** – A *navigációs ablak* megnyitásához válassza ki a **Navigációs panel kibontása** gombot bármely lap bal felső ablakában. (A _**Menü** gomb_ másik neve *hamburger*, *hamburger menü*, vagy *hamburger gomb*.) Rögzítheti a navigációs ablakot kinyitva, vagy alapértelmezés szerint összecsukva tárolhatja. A navigációs ablak nyitva rögzítése után, az alkalmazás nyitva tartja azt mindaddig, amíg össze nem csukja.

## <a name="full-personalization-access-formerly-explicit-personalizations"></a>Teljes személyre szabási hozzáférés (korábban explicit személyre szabások)

A **teljes személyre szabási hozzáférés** szinten a felhasználók hozzáférhetnek az alkalmazás minden személyre szabási lehetőségéhez. Mivel minden személynek és vállalatnak eltérőek az igényei, ezért amikor interakcióba lépnek az alkalmazással – főleg a használt mezők esetében – a személyre szabás olyan eszközöket biztosít, amelyek segítségével a felhasználók és a szervezetek személyre szabhatják, hogy a szükséges információk milyen sorrendben szerepeljenek, és hogyan lépjenek interakcióba egymással az alkalmazáson belül. Ezek a lehetőségek kulcsfontosságúak az alkalmazásban lévő egyszerűsített és optimalizált élményekhez, amelyek az Ön és a szervezet igényeihez vannak szabva. 

Ha a [Mentett nézetek](saved-views.md) funkció be van kapcsolva, akkor egy explicit mentés szükséges ahhoz, hogy az adott nézet felhasználói élménye megmaradjon. Amikor a **Mentett nézetek** funkció ki van kapcsolva, ezek a módosítások automatikusan mentődnek.

A következő szakaszok azon személyre szabási lehetőségek mértékét tartalmazzák, amelyek a **teljes személyre szabási hozzáférés** szint felhasználói számára elérhetők. Az alábbiakban látható néhány ilyen lehetőségek:

- Gyorsbillentyű menüpontok
- A **Személyre szabási** eszköztár
- Csempék, listák és a munkaterületekre mutató hivatkozások hozzáadása
- Összegzés hozzáadása a munkaterületről az irányítópultba
- A saját irányítópultjának személyre szabása

### <a name="shortcut-menu-options"></a>Gyorsbillentyű menüpontok

Helyi menük nyújtanak egy lehetőséget egy lap interfészének módosítására, hogy az jobban megfeleljen igényeinek vagy a szervezet igényeinek. (Más néven a helyi menü van egy *helyi menü* vagy egy *helyi menüje*.)

Néhány, a szokásos és a fontos változtatást laphoz végrehajtott érhetők el közvetlenül, a helyi menü Beállítások pontjára. Ha például szeretne felvenni vagy elrejteni oszlopokat egy rácsban, kattintson a jobb gombbal a rács oszlopfejlécére, és adja meg az **Oszlop beszúrása** vagy **Oszlop elrejtése** lehetőséget.

Ezenkívül a legtöbb alaptípus személyre szabásai akkor érhetők el, kattintson a jobb gombbal egy elemre, és válassza a **Személyre szabást**. (Megjegyzendő, hogy az oldalon nem minden elem szabható személyre.) Ha a személyre szabásnak ezt a módszerét választja, akkor megjelenik az elem *tulajdonság ablak* lehetősége.

![Egy elem tulajdonságainak testreszabása](./media/cli-element-property-window.png)

A tulajdonságablak segítségével egy elem testreszabása a következőképpen történik:

- Az elem címkéje módosítása.
- Az elem elrejtése, így az nem jelenik meg az oldalon. A mező adatait nem törölték vagy módosították. Az adatokat csak nem jelenítik meg az oldalon többé.
- Tartalmazza a gyorslap összefoglaló szakasz információit (ha az elem egy gyorslapon van).
- A mező kihagyása, így nem kap fókuszt, amikor átvált a lapon.
- az adatk szerkesztésének megakadályozása a mezőben (bármely rekord).
- Az adatbevitelhez szükséges mező kijelölése. Ha ebben a mezőben nincs megadva érték, akkor egy piros szegéllyel és egy csillaggal jelenik meg, ami jelzi ezt az állapotot. Ez a lehetőség csak akkor érhető el 10.0.11 verzióban, ha a [Mentett nézetek](saved-views.md), illetve a **Mezők kijelölése kötelezőnek testreszabással** funkciók be vannak kapcsolva.

A tulajdonságablak szerepeltethet egyéb személyre szabása funkciókat az elemtől függően. Például egy csempe a tulajdonságablak előfordulhat, hogy lehetővé teszik és támogatják ezt a csempét az irányítópulton, illetve a tulajdonságablakok az elemek alapértelmezett irányítópultjához előfordulhat, hogy lehetővé teszik egy új, egyéni munkaterület létrehozását.

### <a name="the-personalization-toolbar"></a>Személyre szabási eszköztár

Ha több módosítást is szeretne végrehajtani egy lapon, illetve olyan módosításokat szeretne végrehajtani, amelyek nem érhetők el más mechanizmusokon keresztül (például elemeket szeretne újrarendezni), használhatja a **Testreszabás** eszköztárat. A **Testreszabás** eszköztár megnyitásához hajtsa végre a következő lépések valamelyikét:

- Válassza a **Ctrl+Shift+P** billentyűkombinációt a lap bármely eleméből.
- Válassza ki az **Oldal személyre szabása** lehetőséget egy elem tulajdonságablakában.
- Bármely oldal Művelet panelén válassza az **Oldal személyre szabása** csoportot a **Testreszabás** csoportban a **Beállítások** lapon.
- Válassza ki a navigációs sávon a **Beállítások** gombot (a fogaskerék szimbólum), majd válassza a **Személyre szabás** lehetőséget.

[![Személyre szabási eszköztár](./media/restyledPersonalizationToolbar.png)](./media/restyledPersonalizationToolbar.png)

#### <a name="navigating-the-page"></a>Navigálás a lapon

Ha meg van nyitva a **Személyre szabás** eszköztár, az alapul szolgáló lap írásvédett (más szóval nem szerkeszthetők az adatok), de még mindig interaktív. Pontosabban kibonthatja vagy összecsukhatja a **Kapcsolódó információk** ablaktáblát, válthat a lapok között, valamint kibonthatja vagy összecsukhatja a szakaszokat, ahogy általában végrehajtja ezeket a műveleteket a lapon. Ha személyre szabott módosítást szeretne alkalmazni egy összecsukható panelre vagy lapra (például egy gyorslap elrejtése), akkor egyszerűen ki kell választania a gombot, amely megjelenik a szakasz vagy lap mellett, amikor ráfókuszál a billentyűzettel vagy fölé viszi az egérmutatót.

#### <a name="personalization-tools"></a>Személyre szabási eszközök

A következő eszközök érhetők el a **Személyre szabása** eszköztáron:

- A **Kijelölés** eszközzel egy elemet kijelölve megnyithat egy párbeszédablakot, és módosíthatja az elem tulajdonságait. Az eszköz használatához válassza ki az eszköztárban a **Kijelölés** gombot, majd jelölje ki a kívánt elemet. Az elem tulajdonságok ablaka jelenik meg, ahol az elem bármilyen tulajdonsága módosítható. Megismételheti a folyamatot más elemekkel is, amelyek a lapon testre szabhatók. Bizonyos esetekben előfordulhat, hogy egyes testreszabható tulajdonságok nem érhetők el. Kötelező mezőt például nem tud zárolni.
- Válassza ki az **Elrejtés** eszközt egy elem és elrejtéséhez a lapon. Az eszköz használatához válassza ki az eszköztárban az **Elrejtés** gombot, majd rejtse el a kívánt elemet. Ha használja az **Elrejtés** eszközt, minden éppen rejtett elem látható lesz, de egy árnyékolt tárolóban jelennek meg. Ezután kijelölheti, hogy az elem látható legyen. Ha szeretné megtekinteni, hogyan fog kinézni a lap az elemek elrejtésével, váltson át egy másik személyre szabási eszközre vagy zárja be a személyre szabási eszköztárat.
- Használja a **Mezők hozzáadása** eszközt az új mezők laphoz való felvételére. Az eszköz használata esetén csak az oldal definíciójának részét képező mezőket veheti fel. Új mezők, amelyek nem részei az aktuális oldaldefiníciónak, létrehozásával kapcsolatos további tudnivalókat lásd: [Egyéni mezők létrehozása és használata](user-defined-fields.md). Miután kiválasztotta a **Mezők hozzáadása** gombot az eszközsora először válasszon adott rács vagy szakasz, ahová mező hozzáadását szeretné. A kijelölt ráccsal vagy szakasszal kapcsolatos mezők listája egy párbeszédpanelen jelenik majd meg. A párbeszédpanelen válasszon hozzáadandó mezőket, majd a **Frissítés** lehetőséget. Korábban hozzáadott mező eltávolításához meg kell ismételni a folyamatot, de a mező a párbeszédpanelen ne legyen kijelölve.
- Használja az **Áthelyezés** eszközt, ha egy elemet ki szeretne jelölni és az elemek jelenlegi csoportján belül egy másik helyre szeretné áthelyezni. Ne feledje, hogy a szülőcsoporton kívülre nem helyezhető át elem. Az eszköz használatához válassza ki az eszköztárban az **Áthelyezés** gombot, majd helyezze át a kívánt elemet. Amikor kiválaszt egy elemet, az alkalmazás meghatározza, ha azokat a helyeket, ahová az elemet át lehet helyezni. Ezek a helyek *lerakási zónákként* ismertek. Az aktuális csoporton belül az elem húzásakor minden lerakási zóna mellett a terület, ahová az elem húzható színes, félkövér sorként jelenik meg.
- Válassza ki a **Kihagyás** eszközt egy elem eltávolítására az oldal billentyűparancs-sorozatából Ha bejelöli a **Kihagyás** gombot az eszközsoron, minden éppen kihagyott elem látható lesz, és egy árnyékolt tárolóban jelennek meg. Interaktívan eltávolíthat vagy hozzáadhat mezőket a lapsorrendhez.
- Használja a **Megjelenítés a fejlécben** eszközt, ha azt szeretné, hogy az elem a gyorslap összesítő lapján megjelenjen. Ha kiválasztja a **Megjelenítés a fejlécben** gombot az eszközsoron , összesítő mezők szerepelnek az árnyékolt tároló bejelölt összes mezőt. Interaktívan mezők felvétele az összesítő gyorslapre, és a mezők eltávolítása összegző mezőinek a kiválasztásával.
- A **Szükséges** eszköz használatával lehet az adatbevitelhez kötelező elemet kijelölni. Ha bejelöli a **Kötelező** gombot az eszközsoron, minden kötelezőnek testreszabott elem, és egy árnyékolt tárolóban jelenik meg. Ezután újra nem kötelezővé tehetők. Ez a lehetőség csak akkor érhető el a 10.0.12 vagy újabb verzióban, ha a **Mezők kijelölése kötelezőnek testreszabással** funkció be van kapcsolva.
- Használja a **Zárolás** eszközt, ha egy elemet Szerkeszthető vagy Nem szerkeszthető állapotúra akar állítani. Ha kiválasztja a **Zárolás** gombot az eszközsoron, minden nem szerkeszthető elem látható lesz, és egy árnyékolt tárolóban jelennek meg. Ezután újra szerkeszthetővé tehetők. Vegye figyelembe, hogy egyes mezők kötelezőek, és nem tehetők zárolttá. Lakat szimbólum jelenik meg az ilyen mezők mellett.
- Használja az **Alkalmazás hozzáadása a Power Apps alkalmazásból** eszközt, amely a Microsoft Power Apps használatával lett létrehozva az oldalon. A Power Apps-alkalmazásnak a lapba való beágyazásával kapcsolatos részletes tudnivalókat lásd: [Power Apps-alkalmazásokból származó alkalmazás beágyazása](embed-power-apps.md). Ez a lehetőség csak akkor érhető el, ha ki van kapcsolva a [Mentett nézetek](saved-views.md) funkció.
- Használja az **Alkalmazás hozzáadása** gombot egy Microsoft Power Apps rendszerben létrehozott vagy külső féltől származó alkalmazás beágyazásához az oldalon. Ez a lehetőség csak akkor érhető el, ha be van kapcsolva a [Mentett nézetek](saved-views.md) funkció. 
- Válassza a **Tisztítás** eszközt az oldal alapértelmezett, telepítési beállításainak visszaállításához. Az aktuális oldal minden testreszabása törölve lesz. Nem vonható vissza ez a művelet. Ezért akkor használja ezt az eszközt, ha biztos benne, hogy az oldal alaphelyzetbe állítását szeretné. Ha **Mentett nézetek** funkció be van kapcsolva, akkor az eszköz törli az aktuális nézet személyre szabását.
- Használja az **Importálás** eszközt hogy egy korábban ön vagy más által létrehozott testreszabási fájlból töltsön be testreszabási beállításokat. 

    - Amikor a **Mentett nézetek** funkció ki van kapcsolva, akkor kiválaszthatja, hogy hozzáadja vagy kicseréli a meglévő személyre szabást a lapra importálandó személyre szabásokkal. Nem vonható vissza ez a művelet. Ezért a személyre szabások importálása után manuálisan kell törölnie vagy visszavonnia a nem kívánt módosításokat.
    - Ha a **Mentett nézetek** funkció be van kapcsolva, akkor az importált személyre szabások nézetté válik a lapon. Ha nézet már létezik, akkor lehetősége van az importálás kihagyására, az aktuális, ugyanazzal a névvel rendelkező nézet felülírására, vagy az importált nézet átnevezésére.

- Használja az **Exportálás** eszközt a lap testreszabásainak mentéséhez egy fájlba. Majd a testreszabásokat megoszthatja más felhasználókkal. Ezeknek a felhasználóknak csak a lap személyes beállításokat tartalmazó fájlt kell importálni. Ha **Mentett nézetek** funkció be van kapcsolva, akkor az eszköz menti az aktuális nézetet egy megosztható fájlba.
- Válassza ki a **Bezár** gombot a **Személyre szabás** eszköztár bezárásához és ahhoz, hogy az oldal visszatérjen korábbi interaktív állapotába.

Hagyományosan, amikor a **Személyre szabás** eszköztár használatban van, a testreszabások azonnal életbe lépnek. Ha viszont a [Mentett nézetek](saved-views.md) funkció be van kapcsolva, akkor a kiválasztott nézethez explicit módon kell mentenie a személyre szabott beállításokat.

Bizonyos esetekben látható egy lakat ikon az elem mellett, amikor kiválaszt egy eszközt. Ez a szimbólum azt jelzi, hogy nem módosíthatók a kijelölt eszközzel kapcsolatos az elem tulajdonságait, mert tulajdonságokhoz módosításai megakadályozza, hogy a lap megfelelően működik-e.

### <a name="adding-tiles-lists-and-links-to-a-workspace"></a>Csempék, listák és hivatkozások munkaterülethez való hozzáadása

Egyes listákat tartalmazó lapok esetében a **Hozzáadás munkaterülethez** testreszabási funkció a Művelet ablaktábla **Személyre szabás** csoportjában érhető el a **Beállítások** lapjának lapon. Ez a funkció lehetővé teszi, hogy az aktuális lista megfelelő adatait egy meghatározott munkaterületre küldje. A munkaterületen megjelenő információk a teljes listán, illetve a lista szűrt és rendezett verzióján is alapulhatnak. Megadhatja azt is, hogy az információ megjelenjen-e a munkaterületen listaként, összegző csempeként megjelenítve az elemek számát a listában, vagy egy hivatkozásként.

> [!NOTE]
> Ha a [Mentett nézetek](saved-views.md) funkció be van kapcsolva, a munkaterületre beküldött tartalom közvetlenül egy nézethez kapcsolódik. A nézet lekérdezése az adatok munkaterületre való lekérésére szolgál, és a munkaterületen található megfelelő csempe vagy hivatkozás megnyitja a nézethez tartozó lapot, úgy, hogy a nézet lekérdezése és a testreszabások alkalmazva vannak rá. Ha a nézet frissül, akkor az új nézet-definícióhoz igazodnak a megfelelő munkaterület elemei.

[![Hozzáadás munkaterületenként](./media/personalization-addtoworkspace.png)](./media/personalization-addtoworkspace.png)

- Lista hozzáadásához a munkaterülethez, először rendezni és szűrni kell a listát a lapon, hogy az adatok a munkaterületen megjeleníteni kívánt módon jelenjenek meg. (Ha a **Mentett nézetek** funkció be van kapcsolva, akkor nem folytathatja addig, amíg nem menti azokat a nézeteket, amelyekhez ilyen feltételek tartoznak). Ezután válassza a **Hozzáadás munkaterülethez** lehetőséget. Válassza ki a munkaterületez, majd kattintson a **Prezentáció** mezőben a **Lista** elemre. Miután kijelölte **Konfigurálást**, megjelenik egy párbeszédpanel, ahol kiválaszthatja az oszlopok, amelyek jelenjenek meg a listában a munkaterületen. Megadhatja a munkaterületen a listához használandó címkét.
- A munkaterület címének hozzáadásához először szűrnie kell a listát az oldalon, hogy az összesítendő adatokat megjelenítse – vagy azokat, amikhez gyors elérést szeretne. (Ha a **Mentett nézetek** funkció be van kapcsolva, akkor nem folytathatja addig, amíg nem menti azokat a nézeteket, amelyekhez ilyen feltételek tartoznak). Ezután válassza a **Hozzáadás munkaterülethez** lehetőséget. Válassza ki a munkaterületez, majd kattintson a **Prezentáció** mezőben a **Cím** elemre. Miután kijelölte a **Konfigurálást**, megjelenik egy párbeszédpanel, ahol megadhatja a munkaterületen található csempe használandó címkéjét. Megadhatja azt is, hogy a csempén kell-e egy számának megjelennie. Miután hozzáadta a csempét a munkaterülethez kiválaszthatja, hogy az aktuális lapot megnyissa a munkaterületről. Ezt követően megtekintheti a csempéhez társított szűrt listát.
- Hivatkozás hozzáadásához egy munkaterülethez, először a terméklista szűrése az oldalon, hogy az Ön érdeklő adatokat mutassa. (Ha a **Mentett nézetek** funkció be van kapcsolva, akkor nem folytathatja addig, amíg nem menti azokat a nézeteket, amelyekhez ilyen feltételek tartoznak). Ezután válassza a **Hozzáadás munkaterülethez** lehetőséget. Válassza ki a munkaterületez, majd kattintson a **Prezentáció** mezőben a **Hivatkozás** elemre. Miután kijelölte a **Konfigurálást**, megjelenik egy párbeszédpanel, ahol megadhatja a hivatkozáshoz használandó címkét. Megadhat címkét az új szakaszhoz, amely ezt a hivatkozást tartalmazza.

Miután egy lista, a csempe vagy a hivatkozás egy munkaterülethez hozzá lett adva, a munkaterületet megnyithatja, és az elemeit igény szerint átrendezheti.

### <a name="adding-a-summary-from-a-workspace-to-a-dashboard"></a>Összegzés hozzáadása a munkaterületről az irányítópultba

Néhány munkaterület tartalmaz számlálási csempét (vagyis számot tartalmazó csempét), és lehetséges, hogy ezeket is meg szeretné jeleníteni az irányítópulton. A munkaterületen kattintson a jobb gombbal egy csempére, válassza a **Személyre szabás** elemet, majd a csempe tulajdonságablakában **Kitűzés az irányítópultra** lehetőséget. Ha a következő alkalommal megnyitja, vagy frissíti az irányítópultot, láthatja a számot a munkaterület navigációs csempéje alatt az irányítópulton. Kiválaszthatja, hogy a számláló közvetlenül az adatokhoz menjen, amelyeket bemutat.

### <a name="personalizing-your-dashboard"></a>Az irányítópult személyre szabása

Az irányítópult legtöbbször az első oldal, amelyet az alkalmazás megnyitásakor lát. Minden más rendszerben lévő laphoz hasonlóan személyre szabható a témakörben korábban ismertetett hasonló mechanizmusokkal. 

> [!WARNING]
> Jelenleg, ha tartalmat rejt el az irányítópulton, akkor fontos, hogy közvetlenül egy csempét célozzon meg, és ne a körülötte levő helyet. Ha elrejt egy csoportot egy csempe körül, akkor nem várt eredmény érhető el, ha később több csempét adnak hozzá, vagy ha a rendszer másik nyelvre vált.

Az irányítópulton elérhető egyedi személyre szabási lehetőséggel adhat hozzá lapokat. 

- Ha a **Teljes oldalas alkalmazások** funkció ki van kapcsolva, akkor új csempét adhat hozzá, ha a jobb gombbal rákattint egy elemre az irányítópulton, majd kiválasztja a **Hozzáadás a munkaterülethez** lehetőséget. Egy új munkaterület lap jön létre az irányítópult alsó részén. Ez az új munkaterület csempe átnevezhető. Hozzáadhat listákat, csempéket és hivatkozásokat a munkaterülethez a témakörben itt leírtak szerint: [Csempék, listák és hivatkozások hozzáadása munkaterülethez](personalize-user-experience.md#adding-tiles-lists-and-links-to-a-workspace).
- Ha a **Teljes oldalas alkalmazások** funkció be van kapcsolva, akkor új csempét adhat hozzá, ha a jobb gombbal rákattint egy elemre az irányítópulton, majd kiválasztja az **Alkalmazás hozzáadása** lehetőséget. A párbeszédpanelen válassza ki, hogy szeretne-e csempét hozzáadni egy új munkaterülethez, vagy egy olyan csempét, amelynek tartalma a Power Appsből származik vagy egy webhelyről. Ezután a lépéseket követve konfigurálja a kiválasztott lehetőséget. Egy új csempe jön létre az irányítópult alsó részén. 

## <a name="sharing-personalizations"></a>Személyre szabások megosztása

Az oldal személyre szabása után más felhasználókkal is megoszthatja a személyes beállításait a személyre szabott oldal exportálásával. Ezután más felhasználóktól kérheti a személyre szabási fájlok importálását. Másik lehetőségként a személyre szabásokat adhat a rendszergazdai jogokkal rendelkező felhasználónak. Ez a felhasználó ezután alkalmazhatja a személyre szabási fájljait egyszerre több felhasználóra a **Személyre szabás** adminisztrációs lap használatával.

## <a name="administration-of-personalizations"></a>Testreszabások adminisztrálása

A **Személyre szabás** oldal a személyre szabások kezelésének központja a szervezeti szinten. Az oldal tartalma és képességei attól függenek, hogy a **Mentett nézetek** funkció be van-e kapcsolva.

Azon vevők esetében, akik bekapcsolták a **Mentett nézetek** funkciót, tekintse meg a [Mentett nézetek](saved-views.md) témakör "Nézetek globális kezelése" szakaszát.

Azoknak a vevőknek, akik még nem kapcsolták be a [Mentett nézetek](saved-views.md) lehetőséget, ennek a weboldalnak négy lapja van:

- **Alkalmazás** – Importálhat vagy kiválaszthat egy személyre szabási beállítást egy vagy több felhasználó számára. A személyre szabás alkalmazásához egy vagy több felhasználóra, először jelölje ki a szerepkört és az adott szerepkörrel rendelkező felhasználókat. Válasszon egy meglévő személyre szabást vagy importáljon egy személyre szabási fájlt a kiválasztott felhasználókra történő alkalmazáshoz. A rendszer ellenőrzi a személyre szabást, és alkalmazza az összes kijelölt felhasználóra, amikor azok legközelebb megnyitják a kijelölt lapot.
- **Törlés** – A lap vagy a munkaterület összes személyre szabása egy vagy több felhasználó esetében is törölhető. Először válasszon egy oldalt vagy munkaterületet, hogy megtekinthesse azon felhasználók listáját, akik személyre szabták ezt az oldalt. Ezután válassza ki azokat a felhasználókat, akiknek az adott oldalhoz vagy munkaterülethez tartozó személyre szabását törölni kell, majd válassza a **Törlés** elemet. A kiválasztott felhasználók által a kiválasztott lapra vagy munkaterületre alkalmazott valamennyi személyre szabási beállítás törlődik. Ez a művelet nem vonható vissza. Ugyanakkor ha a lapnak vagy a munkaterületnek létezik mentett személyre szabási beállítása, ez a beállítás visszaimportálható.
- **Felhasználók** – Válasszon egy felhasználót, hogy megtekinthesse a felhasználó által személyre szabott oldalak listáját. Ezután kiválaszthatja, hogy engedélyezze vagy letiltsa a kiválasztott felhasználónak a személyre szabott képességek használatát bizonyos oldalakon vagy az egész rendszerben. Emellett törölhet, importálhat és exportálhat személyre szabásokat a felhasználó számára. Ezenkívül a felhasználó számára alaphelyzetbe állíthatók a funkció-ábrafeliratok. Ebben az esetben, ha a felhasználó korábban elutasította az új funkciókat bemutató előugró ablakokat, ezek legközelebb újra megjelennek a felhasználó számra
- **Rendszer:** – Itt tudja ideiglenesen kikapcsolni a rendszerben személyre szabásokat az összes felhasználó számára. Ebben az esetben minden személyre szabás minden felhasználónál törlődik, és az összes lap visszaáll az alapértelmezett állapotába. Amennyiben később újra bekapcsolja a személyre szabásokat, a rendszer minden személyre szabást újra alkalmaz. Véglegesen is törölheti a rendszerben szereplő személyes beállításokat az összes felhasználó számára. A törölt személyes beállításokat nem lehet visszaállítani. Ezért a lépés végrehajtása előtt ellenőrizze, hogy exportálta mindazokat a személyes beállításokat, amelyeket később esetleg importálni szeretne.

## <a name="personalizing-inventory-dimensions"></a>A készletdimenziók személyre szabása

Amikor a készletdimenziók beállítását szabja személyre egy lapon, fontolja meg azokat a beállításokat, amelyek segítségével létrehozta a **Megjelenítendő dimenzió** lehetőséget. Például személyre szabás segítségével egy oszlopot elrejt a kötegszám-készlet dimenzióból, de az oszlop megjelenik, amikor legközelebb megnyitja a lapot. Ez azért fordul elő, mert a **Dimenzió megjelenítése** beállítások határozzák meg a készlet dimenzió megjelenő oszlopait. A **Dimenzió megjelenítési** beállításai minden lapon érvényesülnek, és ezek a beállítások az egyes lapok minden személyre szabott készletdimenzió-mező beállításait felülírják.

Tehát ez azt jelenti, hogy ha az előző példában nem szeretné, hogy a Köteg száma készletdimenzió megjelenjen egy oldalon, a dimenziót törölnie kell az adott oldal **Dimenziók megjelenítése** beállításának megadásakor.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]