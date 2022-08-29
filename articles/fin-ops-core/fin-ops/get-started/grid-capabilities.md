---
title: Rácsfunkciók
description: Ez a témakör a rácsvezérlő számos hatékony funkcióját ismerteti. Az új rács funkciónak engedélyezve kell lennie ahhoz, hogy hozzáférhessen ezekhez a funkciókhoz.
author: jasongre
ms.date: 08/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2020-02-29
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: a8968a1263dfafd67b07b4beb78c51493e95756e
ms.sourcegitcommit: 47534a943f87a9931066e28f5d59323776e6ac65
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/11/2022
ms.locfileid: "9258947"
---
# <a name="grid-capabilities"></a>Rácsfunkciók

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Az új rács vezérlőelem számos hasznos és erőteljes funkciót tartalmaz, amelyek a felhasználó hatékonyságának növelésére, az adatokkal kapcsolatos érdekesebb nézetek kialakítására és az adatokkal kapcsolatos jelentőségteljes rálátás megszerzésére használhatók. Ez a cikk a következő funkciókat mutatja be: 

- Számított értékek megjelenítése 
- A rendszer előtt történő gépelés
- Matematikai kifejezések kiértékelése 
- Tabulátoradatok csoportosítása (a **rácsok csoportosítása funkcióval külön-külön engedélyezve**)
- Befagyasztási oszlopok (a rácsok befagyasztási oszlopainak **funkcióval külön-külön engedélyezve**)
- Oszlop szélességének automatikus illesztése
- Nyújtható oszlopok

## <a name="showing-calculated-values"></a>Számított értékek megjelenítése
A pénzügyi és műveleti alkalmazásokban a felhasználók rács egyes numerikus oszlopaihoz kiszámított értéket kaphatnak. A rács alján található láblécszakasz mutatja ezeket a számított értékeket.

[![Számított értékek megjelenítése a rácsban](./media/grids-aggregation.png)](./media/grids-aggregation.png)

A 10.0.29 előtti verziókban az összeg az egyetlen támogatott számított érték. Ugyanakkor a 10.0.29-es verzióban, **miután** engedélyezték a kiterjesztett rácsösszesítő funkciókat, a felhasználók a következő négy számított érték közül választhatnak:

- Minimum
- Maximum
- Teljes
- Átlag

Egy oszlop csak egy számított értéktípust mutathat. A rács minden oszlopa beállítható úgy, hogy eltérő típusú számított értéket mutassanak.

### <a name="showing-the-grid-footer"></a>A rács láblécének megjelenítése
A pénzügy- és műveletalkalmazások minden táblázatos rácsának alján egy lábléc található. A lábléc értékes információkat jeleníthet meg, amely a rácsban megjelenő adatokhoz kapcsolódik. Íme néhány példa az ilyen információkra:

- A táblázatból kiválasztott sorok száma (ha egynél több rekord van kiválasztva)
- Számított értékek a konfigurált, numerikus oszlopok alján (például végösszegek)
- Az adathalmazban lévő sorok száma összesen 

Ez a lábléc alapértelmezés szerint rejtett, de be lehet kapcsolni. A rács láblécének megjelenítéséhez kattintson a **Rácsbeállítások** gombra a rács fejlécében, és válassza ki a **Lábléc megjelenítése** lehetőséget. Miután bekapcsolta egy adott rács láblécét, erre a beállításra a rendszer addig fog emlékezni, amíg a felhasználó el nem rejti a láblécet. A lábléc elrejtéséhez válassza a **Lábléc elrejtése** parancsot a **Rácsbeállítások** menüben.

### <a name="specifying-columns-with-calculated-values"></a>Oszlopok megadása számított értékekkel
Alapértelmezés szerint egy oszlop sem mutatja alapértelmezés szerint a számított értékeket. Ehelyett a beállítás egyszeres tevékenységnek számít, például a rácsok oszlopainak szélességét módosítja. Miután beállította, hogy meg szeretné tekinteni egy oszlop számított értékét, ez a beállítás a lap következő meglátogatásakor ével fog számolni.

Az oszlopok kétféleképpen konfigurálhatók a számított értékek megjelenítése számára:

- Jelölje ki és tartsa lenyomva annak az oszlopnak a jobb oldali gombját, amelynél meg szeretné tekinteni a számított értéket. Ha a Kiterjesztett **rácsösszesítő funkciók** funkció engedélyezve van, válassza **az** oszlopösszegek megtekintése lehetőséget, majd válassza ki a kívánt számított értéket. Ha ez a funkció nincs engedélyezve, jelölje be az Összesítés **oszlopot**. Ez a művelet három esemény előfordulását okozza:

    1. A rács lábléce láthatóvá válik. 
    2. A program menti az oszlop számított értékének megtekintéséhez beállított beállításokat. 
    3. A kívánt számítást a program az oszlopra, illetve minden más olyan oszlopra kezdeményezi, amelyet korábban úgy konfigurált, hogy a számított értéket mutassa. A számított értékek megjelenítésekor szükséges idő az adatkészlet méretétől függ.

- Ha látható a lábléc, **válassza** az Összesítés megjelenítése (**·** **vagy** a Számított érték kiválasztása, ha engedélyezve van a Kiterjesztett rácsösszesítő funkciók funkció) lehetőséget annak az oszlopnak az alján, ahol meg szeretné tekinteni a számított értéket. Ha nincsenek konfigurált oszlopok, akkor ez a gomb az összes numerikus oszlop láblécében elérhető lesz.

    Ha legalább egy oszlop be van állítva egy számított érték megjelenítésére, **akkor** az Összeg megjelenítése (**vagy** a Számított érték kiválasztása) gomb csak az összesen vagy a fókusz esetén érhető el. A gomb kiválasztásának művelete csak menti a felhasználó által előnyben részesítendő értéket, hogy az oszlopban kiszámított értéket megtekintsen, így a program a későbbi látogatások során alkalmazza a kívánt beállítást. A láblécben ezt az állapotot egy gondolatjel jelöli, amely a oszlopban jelenik meg. (Ne feledje, hogy a számított érték azonnal megjelenik, ha elég kicsi az adatkészlet.)

Ha hibát követ el, és a továbbiakban nem szeretne megtekinteni egy számított értéket egy adott oszlopban, jelölje ki és tartsa lenyomva az oszlopot (vagy kattintson rá a jobb gombbal), **majd válassza az Összesítés elrejtése lehetőséget (** **\>** **vagy a Nincs oszlopösszegek megtekintése, ha engedélyezve van a Kiterjesztett rács összesítési funkciója).** Másik lehetőségként válassza **az összesítés** elrejtése (vagy **a** számított érték elrejtése) lehetőséget a láblécben az adott oszlopban. Ezt a beállítást a program a lap későbbi megtekintései esetére is elmenti. 

### <a name="calculating-aggregate-values"></a>Összesített értékek számítása
Ha olyan oldalra lép, ahol látható a lábléc, és az oszlopok már úgy vannak beállítva, hogy számított értékeket mutassanak, előfordulhat, hogy ezek az értékek nem jelennek meg a láblécben. A viselkedés az oldalon található adatkészlet méretétől függ. Ha elég kicsi az adathalmaz, a számított értékek automatikusan megjelennek az adathalmaz sorai számával együtt. Ha a láblécben kötőjelek vannak a beállított oszlopok alatt, akkor az adatkészlet túl nagy ahhoz, hogy a rendszer azonnal meg tudja mutatja a számított értékeket. Ebben az esetben explicit műveletre van szükség az értékek kiszámításához. Az értékek kiszámításához jelölje be a láblécBen **a** Számítás gombot. Másik lehetőségként jelölje ki és tartsa lenyomva (vagy kattintson a jobb gombbal) egy oszlopban, amelynél meg szeretné tekinteni az összesítést, **majd** válassza az Ebben az oszlopban összesen lehetőséget (**·** **vagy** az oszlop összesítésének megtekintése, majd a kívánt számított értéket, ha engedélyezve van a Kiterjesztett rácsösszesítő funkció).

Ha a számítás hosszú ideig tart, **a művelet bármikor megszakítható a Mégse gombra való választásával**. Bizonyos esetekben az adatkészlet túl nagy lesz az összesített értékek kiszámításához (ezt a korlátot a szervezet szabja ki). Ebben az esetben a rendszer értesítést kap, hogy az adatokat jobban szűrje.

> [!NOTE]
> A rendszergazdák **módosíthatják** **az összesítés kiszámítására elérhető rekordok maximális számát, ha az Ügyfél teljesítmény-beállításai lapon az egyes rácsparaméterek maximális számát módosítják.** Az alapértelmezett érték 25 000 rekord. A rendszergazdáknak körültekintően kell beállítaniuk ezt az értéket, mert ha túl nagy az érték, akkor a felhasználó gépére is szükség lehet a rendelkezésre álló memória mennyiségére. Javasoljuk, hogy az érték ne haladja meg az 50 000 rekordot.

A számított értékek automatikusan frissülnek, amikor az adathalmaz sorait frissíti, törli vagy létrehozza.

## <a name="typing-ahead-of-the-system"></a>A rendszer előtt történő gépelés
Számos üzleti helyzetben rendkívül fontos az adatok gyors beviteli képessége a rendszerbe. Az új rácsvezérlő bevezetése előtt a felhasználók csak az aktuális sorban módosíthatjak az adatokat. Ezért miután változtatásokat eszközeltek egy sorban, a felhasználók mindaddig nem válthatnak másik sorra, és nem hozhatnak létre új sort, amíg a rendszer nem tudta érvényesíteni az aktuális sorban végrehajtott módosításokat, és (sor létrehozása esetén) futtatta az új sor létrehozásához kapcsolódó összes logikát. Az új rács ezeket a műveleteket aszinkronra módosítja, hogy csökkentse a műveletek befejezésére váró, a felhasználók által töltött időt, és javítsa a felhasználói hatékonyságot. A felhasználók új sorokat hozhatnak létre, vagy más sorokba áthelyezve módosításokat hozhatnak létre, miközben a korábbi sorok ellenőrzése és a sor-létrehozási logika függőben van. 

[![Beírás a rendszer előtt.](./media/gridFastEntry-07-25-2022.gif)](./media/gridFastEntry-07-25-2022.gif)

Ennek az új viselkedésnek a támogatásához egy új oszlop lett hozzáadva a sor állapotához a sorválasztó oszloptól jobbra, amikor a rács szerkesztési módban van. Ez az oszlop a következő állapotok egyikét jelzi:

- **Üres** – A hiányzó állapot képe azt jelzi, hogy a sort a rendszer sikeresen mentette.
- **Feldolgozás függőben** – Ez az állapot azt jelzi, hogy a sorban szereplő változtatásokat a kiszolgáló még nem mentette, de a feldolgozás alatt álló változtatások várólistáján szerepelnek. A rácson kívüli művelet előtt meg kell várnia minden függő módosítás feldolgozását. Ezenkívül a sorokban található szöveg dőlt betűvel jelenik meg a sorok nem mentett állapotának jelzésére. 
- **Érvénytelen állapot** – Ez az állapot azt jelzi, hogy a sor feldolgozásakor valamilyen figyelmeztetés vagy üzenet aktiválódott, és előfordulhat, hogy ez megakadályozta, hogy a rendszer mentse a módosítást a sorban. A régi rácsban, ha a mentés művelet sikertelen volt, a program azonnal visszakényszerítette a sort a kérdés azonnali kijavításához. Az új rácsban azonban értesítést kap, hogy a rendszer ellenőrzési hibát észlelt, de eldöntheti, hogy ki szeretné-e javítani a sorban szereplő problémákat. Ha készen áll a hiba elhárítására, a fókuszt manuálisan is áthelyezheti a sorra. Másik megoldásként kiválaszthatja a **Probléma kijavítása** műveletet. Ez a művelet azonnal visszahelyezi a fókuszt a hibát tartalmazó sorra, és lehetővé teszi a szerkesztést a rácson belül vagy azon kívül. Ne felejtse el, hogy amíg az ellenőrzési figyelmeztetést megoldják, az ezt követő függőben levő sorok feldolgozása le van állítva. 
- **Szüneteltetve** – Ez az állapot azt jelzi, hogy a kiszolgáló a feldolgozását szünetelteti, mert a sor ellenőrzése olyan előugró párbeszédpanelt jelenít meg, amelyen felhasználói bevitel szükséges. Mivel a felhasználó más sorban is megadhat adatokat, az előugró párbeszédpanel nem jelenik meg azonnal a felhasználó számára. Helyette akkor jelenik meg, amikor a felhasználó a feldolgozás folytatása mellett dönt. Ezt az állapotot olyan értesítés kíséri, amely tájékoztatja a felhasználót a helyzetről. Az értesítés tartalmaz egy **Feldolgozás folytatása** műveletet, amely elindítja a felugró párbeszédpanelt.

### <a name="differences-when-entering-data-ahead-of-the-system"></a>Eltérések az adatoknak a rendszer előtt történő megadásakor
Ha a rendszer feldolgozása előtt adja meg az adatokat, akkor az adatbeviteli tapasztalat módosulhat:

- Látni fogja, hogy nincsenek keresési legördülő listák, a mezőértékek nem lesznek ellenőrizve, ha ugyanannak a sornak egy másik oszlopára lép, és az oszlopok kezdetben nem mutatják az alapértelmezett értékeket. Ez a viselkedés akkor fordul elő, ha a rendszer előtt hoz létre vagy frissít. Miután azonban a rendszer arról a helyről visszaért, ahol éppen szerkeszt, a szokásos tapasztalat folytatódik. Ha olyan mezőt módosít, amely általában alapértelmezett értéket kap, akkor a módosítások felülbírálják a mező alapértelmezett értékét, amikor a kiszolgáló megkezdi a sor feldolgozását.
- Ha a Le nyíl billentyűvel **hoz** létre új sort, a rács összes oszlopa szerkeszthetőként jelenik meg. Alapértelmezés szerint a fókusz az új sor első oszlopában lesz. Lehet, hogy ez az oszlop nem ugyanaz az oszlop, amely a kezdeti fókuszt megkapta az örökölt rácsban, vagy az az oszlop, amely a **fókuszt fogadja az Új** gomb kiválasztása után. A szervezet testreszabhatja a rendszert, és módosíthatja a kezdeti fókuszt kapó oszlopot, **amikor a Lefelé nyíl kulcs** be van jelölve. A további tudnivalókat lásd Annak az oszlopnak a megadása, [amely a le nyíllal létrehozott új sorok kezdeti fókuszát kapja](#developer-specifying-the-column-that-receives-the-initial-focus-when-new-rows-are-created-by-using-the-down-arrow-key). Ettől függetlenül a személyre szabás segítségével optimalizálhatja az egyes rácsokat az adatbevitelhez. Konkrétabban: a mezők újrarendelése után az első oszlop az az oszlop, amelybe az adatokat el szeretné kezdeni. Előfordulhat az is, hogy általános adatbeviteli mezőket újra szeretne rendezni, hogy csökkentse a lap leállását, és elrejtse az ebben a nézetben az adatbevitelhez nem szükséges mezőket.

### <a name="pasting-from-excel"></a>Beillesztés az Excel programból
A felhasználók mindig Microsoft Excel **exportálni tudják a pénzügyi és műveleti alkalmazások rácsaiból az adatokat az Exportálás az Excel** programba mechanizmus segítségével. Ugyanakkor az adatok rendszerbeli beíratási lehetősége lehetővé teszi, hogy az új rács lehetővé teszi táblák másolását az Excel programból, és közvetlenül bemásolást a pénzügyi és műveleti alkalmazások rácsaiba. Az a rácsvonalcella, amelyből a beillesztési művelet el van indítva, határozza meg, hogy a program hová kezdi a másolt tábla beillesztését. A rács tartalma felülíródik a másolt tábla tartalmával, kivéve a következő két esetet:

- Ha a másolt tábla oszlopainak száma meghaladja a rácsban maradó oszlopok számát, a beillesztés helyétől kezdve, a felhasználó értesítést kap arról, hogy a további oszlopok figyelmen kívül lettek hagyva. 
- Ha a másolt tábla sorainak száma meghaladja a rács sorainak számát, a beillesztés helyétől kezdve a meglévő cellák felülíródnak, és a másolt táblából származó további sorok a rács alján új sorokként jelennek meg. 

## <a name="evaluating-math-expressions"></a>Matematikai kifejezések kiértékelése
A hatékonyság javításaként a felhasználók matematikai képleteket írhatnak be a rács numerikus celláiba. A számítást nem kell a rendszeren kívüli alkalmazásban végezniük. Ha például a **=15\*4** értéket adja meg, majd a **Tab** billentyű lenyomásával kilép a mezőből, akkor a rendszer kiértékeli a kifejezést, majd a mezőbe a **60** értéket menti.

[![A math kifejezések kiértékelása.](./media/gridMathExpression-07-25-2022.gif)](./media/gridMathExpression-07-25-2022.gif)

Ha azt szeretné, hogy a rendszer bizonyos értékeket kifejezésként ismerjen fel, akkor az értéket egyenlőségjellel (**=**) kell bevezetnie. A támogatott operátorokkal és szintaxissal kapcsolatos további információkat lásd: [Támogatott matematikai szimbólumok](http://bugwheels94.github.io/math-expression-evaluator/#supported-maths-symbols).

A 10.0.29-es verzióban már bővítették a matematikai kifejezések numerikus vezérlőkben való kiértékelését, és most a rácson kívül is elérhetők.

## <a name="grouping-tabular-data"></a>Táblázatos adatok csoportosítása
Az üzleti felhasználóknak gyakran eseti adatelemzést kell végezniük. Microsoft Excel Bár ez az elemzés adatok exportálásával és kimutatásos táblák használatával is végrehajtásához szükséges, **a** rácsok csoportosítása funkció, amely az új rácsvezérlő funkciótól függ, lehetővé teszi a felhasználók számára, hogy érdekes módon rendszerezzék a táblázatos adatokat a pénzügyi és műveleti alkalmazásokon belül. Mivel ez a funkció **kiterjeszti** a Számított értékek szolgáltatást, **a** csoportosítással jól értelmezhető információkhoz juthat az adatokról, ha csoportszinten számított értékeket (például részösszegeket) ad meg.

[![Adatok csoportosítása rácsban](./media/grids-groupingWithTotals.png)](./media/grids-groupingWithTotals.png)

A funkció használatához kattintson a jobb egérgombbal a csoportosítani kívánt oszlopra, és válassza ki a **Csoportosítás az oszlop szerint** lehetőséget. Ez a művelet a kiválasztott oszlop szerint rendezi az adatokat, egy új **Csoportosítás** oszlopot ad hozzá a rácshoz, majd az egyes csoportok elejére „fejlécsorokat” szúr be. Ezek a fejlécsorok a következő információkat tartalmazzák az egyes csoportokról:

- A csoport adatértéke 
- Oszlop neve (ez az információ különösen akkor hasznos, ha a csoportosítás több szintjét használja)
- A csoportban levő adatsorok száma
- Számított értékek bármely konfigurált oszlophoz (például részösszegek, ha az oszlop összesítésre van konfigurálva)

Ha [engedélyezve van a](saved-views.md) Mentett nézetek, a csoportosítást menteni lehet olyan lapokon található nézet részeként, amelyek lehetővé teszik a lekérdezések mentését a nézetekbe. Például azok, akiknek nagy a nézetválasztójuk. További részleteket [a Nézetváltás a nézet](saved-views.md#switching-between-views) között szakasz tartalmaz. 

### <a name="multiple-levels-of-grouping"></a>Több szintű csoportosítás
Miután egyetlen oszlop szerint csoportosította az adatokat, csoportosíthatja az adatokat egy másik oszlop szerint, ha a kívánt oszlopban a **Csoportosítás az oszlop szerint** lehetőséget választja. Ez a folyamat addig megismételhető, amíg 5 egymásba ágyazott csoportosítási szintet nem ér el, ami a maximális támogatott mélység. Ezen a ponton a továbbiakban nem tud további oszlopok szerint csoportosítani.

A csoportosítást bármikor eltávolíthatja bármelyik oszlopból, ha a jobb gombbal az adott oszlopra kattint, és a **Szétválasztás** parancsot választja. A csoportosítást az összes oszlopból úgy is eltávolíthatja, hogy a **Rácsbeállítások**, majd az **Összes szétválasztása** lehetőséget választja.

### <a name="sorting-grouped-data"></a>Csoportosított adatok rendezése
Miután csoportosítja az adatokat egy vagy több oszlop alapján, a megfelelő oszlopfejlécen keresztül bármelyik csoportosítási oszlop rendezési irányát módosíthatja. 

Nem csoportosított oszlopban való rendezés esetén a csoportosítás változatlan marad. Az adatok az egyes csoportokon belül, a kiválasztott oszlop alapján vannak rendezve.

### <a name="expanding-and-collapsing-groups"></a>Csoportok kibontása és összecsukása
Az adatok kezdeti csoportosítása esetén minden csoport ki lesz bontva. Az adatok összegzett nézeteit az egyes csoportok összecsukásával lehet létrehozni, illetve a csoport kibontása és összecsukása révén segítséget nyújthat a navigálásban az adatokon keresztül. Egy csoport kibontásához vagy összecsukásához válassza ki a nyíl (>) gombot a megfelelő csoportfej sorban. Ne feledje, hogy az egyes csoportok kibontása/összecsukása **nincs** mentve a személyre szabásban.

### <a name="selecting-and-unselecting-rows-at-the-group-level"></a>Sorok kiválasztása és a kijelölés megszüntetése a csoport szintjén
A rács első oszlopának felső részén található jelölőnégyzet bejelölésével ugyanúgy kiválaszthatja (vagy megszüntetheti a kiválasztást) a rács minden sorában, ha a megfelelő csoportfej sorában a jelölőnégyzetet bejelöli, és egy csoport minden sorát is gyorsan kiválaszthatja (vagy törölheti a kijelölést). A csoportfej sorában található jelölőnégyzet mindig a csoport sorainak aktuális kiválasztási állapotát tükrözi, függetlenül attól, hogy az összes sor ki van-e választva, vagy csak néhány sor van kiválasztva.

### <a name="hiding-column-names"></a>Oszlopok neveinek elrejtése
Az adatok csoportosításakor az alapértelmezett viselkedés a csoportfej sorában az oszlop nevének megjelenítése. Elhagyhatja az oszlop nevét a csoportfej soraiban, ha kiválasztja a **Rácsbeállítások** > **Csoportoszlop nevének elrejtése** lehetőséget.

### <a name="grouping-on-date-and-time-columns"></a>Csoportosítás dátum- és időoszlopok szerint
Ha a Dátum vagy DateTime mezőket csoportosítja, akkor év, hónap vagy nap szerint lehet csoportosítva. A megfelelő fejlécsor "érték" csoportja meg fog egyezni az adott mezőben megadott formátummal. Ezenkívül a DateTime és az Time mezőben az óra, a perc és a másodperc szerint is csoportosíthat.

> [!IMPORTANT]
> A felhasználók jelenleg nem adhatnak hozzá csoportosítási oszlopot, ha egy dátum- vagy időoszlop egy szegmensében csoportosak.

## <a name="freezing-columns"></a>Oszlopok rögzítése
A rács egyes oszlopai elég fontosak lehetnek kontextus tekintetében ahhoz, hogy nem szeretné, hogy kigörgethetők legyenek a nézetből. Ehelyett érdemes mindig láthatónak lennie ezeknek az oszlopoknak az értékei. A **rács befagyasztási oszlopai** ezt a rugalmasságot biztosítják a felhasználók számára. 

[![Rács befagyasztási oszlopai](./media/gridFreezingColumns-07-25-2022.gif)](./media/gridFreezingColumns-07-25-2022.gif)

Oszlop rögzítéséhez kattintson a jobb gombbal az oszlop fejlécére, majd válassza az **Oszlop rögzítése** lehetőséget. Amikor először végrehajtka ezt a lépést, a kiválasztott oszlop lesz az első oszlop, és többé nem lesz kigörgethető a nézetből. Az ezt követő rögzített oszlopok mindegyike az utolsóként rögzített oszlop jobb oldalához lesz hozzáadva. A Rögzített oszlopok újrarendezéséhez a szokásos Áthelyezés funkciót használhatja. A rögzített oszlopok azonban nem helyezhetők át úgy, hogy a rögzítetlen oszlopok között jelenjenek meg. Hasonlóképp, a nem rögzített oszlopok nem helyezhetők át úgy, hogy a rögzített oszlopok között jelenjenek meg.

Oszlop rögzítésének feloldásához kattintson a jobb gombbal a rögzített oszlop fejlécére, majd válassza az **Oszlop rögzítésének feloldása** lehetőséget. 

Ne feledje, hogy az új rács sorkiválasztási és sorállapot-oszlopait mindig rögzíti a rendszer az első két oszlopban. Ezért ha ezek az oszlopok egy rácsban szerepelnek, akkor mindig láthatók lesznek a felhasználó számára, attól függetlenül, hogy a rács vízszintes görgetése milyen helyzetben van. Ezt a két oszlopot nem lehet átrendezni.

## <a name="autofit-column-width"></a>Oszlop szélességének automatikus illesztése
Ahogyan az Excel programban, a felhasználók az oszlopok automatikus átméretezését kényszerítheti az éppen látható tartalom alapján. Az oszlopban lévő méretkezelőkre csak duplán (vagy dupla kattintással) kattintson. Másik lehetőségként helyezze a fókuszt az oszlopfejlécbe, majd válassza ki **az A** kulcsot (automatikus illesztéshez).

## <a name="frequently-asked-questions"></a>Gyakori kérdések
### <a name="how-do-i-enable-the-new-grid-control-in-my-environment"></a>Hogyan engedélyezhető az új rácsvezérlő a saját környezetemben? 

A **Új rácsvezérlő** funkció elérhető közvetlenül a Funkciókezelésben bármilyen környezetben. Miután engedélyezte a funkciót a Funkciókezelésben, minden ezt követő felhasználói munkamenet az új rácsvezérlőt fogja használni. 

A funkció alapértelmezés szerint a 10.0.21 verzióban indult el. A cél az, hogy kötelezővé váljon 2022. októberben.

## <a name="developer-opting-out-individual-pages-from-using-the-new-grid"></a>[Fejlesztő] Egyes oldalak elutasítása az új rács használatából 
Ha a szervezet egy olyan oldalt észlel, amelyen problémák lépnek fel az új rács használata miatt, akkor egy API felület lehetővé teszi, hogy az egyes űrlapok használhassák a régi rácsvezérlőt, miközben a rendszer további részei az új rácsvezérlőt használják. Ha el szeretné utasítani az egyes oldalakat az új rácsból, adja hozzá a következő hívásfeladást `super()` az űrlap `run()` módjához.

```this.forceLegacyGrid();```

Az API-t előbb-külön elavulttá teszi a rendszer, hogy eltávolítsa az örökölt rácsvezérlőt. Azonban az értékcsökkenés visszahozaját követően legalább 12 hónapra elérhető marad. Ha bármilyen probléma az API használatát igényli jelentse azokat a Microsoftnak.

### <a name="forcing-a-page-to-use-the-new-grid-after-previously-opting-out-the-grid"></a>Új rács használatának kikényszerítése egy laphoz a rács korábbi elutasítását követően
Ha az új rács használatát egy adott oldalra vonatkozóan elutasította, akkor az alapproblémák megoldása után később érdemes lehet újra engedélyeznie az új rácsot. Ehhez egyszerűen el kell távolítania a következő hívását: `forceLegacyGrid()`. A módosítás csak akkor lép hatályba, ha az alábbiak valamelyike bekövetkezik:

- **Környezet újratelepítése**: Amikor egy környezetet frissítenek és újratelepítenek, az új rácsból (FormControlReactGridState) elutasított lapokat tároló táblázat automatikusan törlődik.
- **Tábla kézi törlése**: Fejlesztési forgatókönyvek esetén SQL segítségével törölni kell a FormControlReactGridState táblát, majd újra kell indítani az AOS-t. Ez a műveletkombináció visszaállítja az új rácshálót elutasító lapok gyorsítótárazását.

## <a name="developer-opting-individual-grids-out-of-the-typing-ahead-of-the-system-capability"></a>[Fejlesztő] Egyes rácsok kivéte a beírást a rendszer képességtől eltolása
Bizonyos helyzetekben nem *lehet* megfelelően dolgozni a rács rendszer-előre történő beírásával. (Például néhány olyan kód, amely akkor aktiválódik, amikor egy sor ellenőrzése történik, egy adatforrás-kutatás kiváltása történik, és a kutatás a meglévő sorok nem véglegesített szerkesztései lesznek.) Ha a szervezet ilyen helyzetet fedez fel, akkor egy API áll rendelkezésre, amellyel a fejlesztő ki tudja választani az aszinkron sorellenőrzést, és visszaáll az örökölt viselkedésre.

Ha egy rácsban le van tiltva az aszinkron sorellenőrzés, akkor a felhasználók nem hozhatnak létre új sort, és nem ugorhatnak át a rács egy másik meglévő sorára, amíg az aktuális sorban ellenőrzési problémák vannak. Ennek a műveletnek az a oldala, hogy az Excelből nem lehet táblákat berakodni a pénzügyi és műveleti rácsba.

Ha ki szeretne választani egy rácsot az aszinkron sorellenőrzésből, `super()``run()` adja hozzá a következő hívást a képernyő metódusához.

```<gridControl>.allowPreemptiveClient(false);```

> [!NOTE]
> - Ez a hívás csak kivételes esetekben hívható meg, és nem lehet norma az összes rácshoz.
> - Nem ajánlott az API-t futásidőben ki- és bekapcsolni a képernyő betöltése után.

## <a name="developer-size-to-available-width-columns"></a>[Fejlesztői] Oszlopok rendelkezésre álló szélességre méretezése
Ha egy fejlesztő beállítja a **WidthMode** tulajdonságot **SizeToAvailable** értékre az új rácsban található oszlopokhoz, akkor ezek az oszlopok kezdetben ugyanolyan szélességgel rendelkeznek, mintha a tulajdonság **SizeToContent** értékre lenne állítva. A rácson belül azonban képesek kiszélesedni, hogy kihasználják az extra elérhető helyet. Ha a tulajdonság több oszlopnál **SizeToAvailable** értékre van állítva, akkor az egyes oszlopok a rácson belül a további rendelkezésre álló szélességet osztják fel. Ha viszont a felhasználó manuálisan átméretezi az egyik oszlopot, akkor az oszlop statikus lesz. Ezen a szélességen marad, és a rendszer nem nyúlik tovább, hogy kihasználja az extra elérhető szélességet.

## <a name="developer-specifying-the-column-that-receives-the-initial-focus-when-new-rows-are-created-by-using-the-down-arrow-key"></a>[Fejlesztő] Annak az oszlopnak a megadása, amely a kezdeti fókuszt fogadja, amikor új sorokat hoz létre a Lefelé nyíl billentyűvel
[Mint](#differences-when-entering-data-ahead-of-the-system) azt a Különbségek szakaszban is leírták, amikor a rendszerszakasz előtt beírták az adatokat, ha engedélyezve van a "Rendszer előreírása" képesség, és a felhasználó a **Le** nyílgomb használatával létrehoz egy új sort, akkor az alapértelmezett viselkedés az új sor első oszlopában található fókusz. Ez a tapasztalat eltérhet az **örökölt** rácsban vagy az Új gomb kiválasztásakor meglévő tapasztalattól.

A felhasználók és a szervezetek adatbevitelre optimalizált mentett nézeteket hozhatnak létre. (Át lehet például rendezni az oszlopokat, hogy az első oszlop az, amelybe az adatokat be szeretné írni.) Ezenkívül a 10.0.29-es **verziótól a szervezetek a kiválasztottControlOnCreate()** metódussal módosíthatják ezt a viselkedést. Ezzel a módszerrel a fejlesztők megadhatják azt az oszlopot, amely a **le nyílgomb használatával új sor létrehozása esetén a kezdeti fókuszt kapja**. Bemenetként ez az API a kezdeti fókuszt kapó oszlopnak megfelelő vezérlőazonosítót veszi át.

## <a name="known-issues"></a>Ismert problémák
Ez a szakasz az új rácsvezérlő ismert problémáinak listáját tartalmazza.

### <a name="open-issues"></a>Nyitott problémák
- Az **Új rácsvezérlő** funkció engedélyezése után néhány oldal továbbra is a meglévő rácsvezérlőt fogja használni. Ez a következő helyzetekben fog történni:
 
    - Egy kártyalista szerepel azon az oldalon, amely több oszlopban jelenik meg.
    - Egy csoportosított kártyalista szerepel az oldalon.
    - Nem reagáló bővíthető vezérlővel rendelkező rácsoszlop.

    Amikor egy felhasználó először találkozik egy ilyen helyzettel, egy üzenet jelenik meg az oldal frissítésével kapcsolatban. Az üzenet megjelenése után az oldal a következő termékfrissítési verzióig továbbra is a meglévő rácsot használja az összes felhasználó számára. A jövőbeli frissítéshez figyelembe kell venni ezeket a forgatókönyveket, hogy az új rács használható legyen.

- [KB 4582758] A rekordok elmosódottak, ha a nagyítást 100-ról bármely más százalékra módosítja

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

