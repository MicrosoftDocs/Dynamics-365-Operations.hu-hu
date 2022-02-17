---
title: Rács funkciói
description: Ez a témakör ismerteti a rács vezérlőelem számos erőteljes funkcióját. Az új rács funkciónak engedélyezve kell lennie ahhoz, hogy hozzáférhessen ezekhez a funkciókhoz.
author: jasongre
ms.date: 02/01/2022
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
ms.openlocfilehash: 83d0b6243efd802ffc959f8de14f6232736fc88c
ms.sourcegitcommit: 7893ffb081c36838f110fadf29a183f9bdb72dd3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/02/2022
ms.locfileid: "8087574"
---
# <a name="grid-capabilities"></a>Rácsfunkciók

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Az új rács vezérlőelem számos hasznos és erőteljes funkciót tartalmaz, amelyek a felhasználó hatékonyságának növelésére, az adatokkal kapcsolatos érdekesebb nézetek kialakítására és az adatokkal kapcsolatos jelentőségteljes rálátás megszerzésére használhatók. Ez a cikk a következő funkciókat mutatja be: 

- Teljes összegek számítása
- A rendszer előtt történő gépelés
- Matematikai kifejezések kiértékelése 
- Táblázatos adatok csoportosítása (külön engedélyezve a **Csoportosítás rácsokban** funkció)
- Oszlopok fagyasztása (külön engedélyezve a **Oszlopok fagyasztása rácsokban** funkció)
- Oszlop szélességének automatikus illesztése
- Nyújtható oszlopok

## <a name="calculating-totals"></a>Teljes összegek számítása
A Finance and Operations alkalmazásokban a felhasználók megtekinthetik az összegeket a rácsok numerikus oszlopainak alján. Ezeket az összegeket a rács alján látható lábléc szakasz mutatja. 

### <a name="showing-the-grid-footer"></a>A rács láblécének megjelenítése
A Finance and Operations alkalmazásokban minden táblázatrács alján található egy lábléc. A lábléc értékes információkat jeleníthet meg, amely a rácsban megjelenő adatokhoz kapcsolódik. Íme néhány példa az ilyen információkra:

- A táblázatból kiválasztott sorok száma (ha egynél több rekord van kiválasztva)
- Végösszegek a konfigurált numerikus oszlopok alján
- Az adathalmazban lévő sorok száma összesen 

Ez a lábléc alapértelmezés szerint el van rejtve, de bekapcsolhatja. A rács láblécének megjelenítéséhez kattintson a **Rácsbeállítások** gombra a rács fejlécében, és válassza ki a **Lábléc megjelenítése** lehetőséget. Miután bekapcsolta egy adott rács láblécét, erre a beállításra a rendszer addig fog emlékezni, amíg a felhasználó el nem rejti a láblécet. A lábléc elrejtéséhez válassza a **Lábléc elrejtése** parancsot a **Rácsbeállítások** menüben.

### <a name="specifying-columns-with-totals"></a>Összesítéssel ellátott oszlopok megadása
Alapértelmezés szerint egyetlen oszlop sem mutatja az összegeket. Ezt a rács oszlopai szélességének beállításához hasonlóan egyszeri beállítási tevékenységnek tekintjük. Miután megadta, hogy szeretné egy oszlop összegeit megtekinteni, a rendszer a lap legközelebbi meglátogatásakor emlékezni fog a beállításra.

Egy oszlopot kétféleképpen lehet az összegek megjelenítésére konfigurálni: 

- Kattintson a jobb gombbal az oszlopra, amelynek végösszegét látni szeretné, és válassza az **Összesen az oszlopban** lehetőséget. Ez a művelet három esemény előfordulását okozza:

    1. A lábléc láthatóvá válik. 
    2. A program menti a beállítást, hogy látni szeretné az oszlopra vonatkozó összeget. 
    3. Végösszegszámítás indul ehhez az oszlophoz, illetve az összes többihez is, amelyeknél korábban már beállította az összegek megtekintését. A végösszeg megjelenítéséhez szükséges idő az összesíteni kívánt adathalmaz méretétől függ.

- A lábléc láthatóvá válása után válassza a **Végösszeg megjelenítését** a lábléc területén azon oszlop alján, amelyre vonatkozóan összesítést szeretne látni. Ha nincsenek konfigurált oszlopok, akkor az összes numerikus oszlop esetében elérhetővé válik az **Összeg megjelenítése** gomb. 

    Miután legalább egy oszlopot konfigurált összesítésekhez, akkor az **Összeg megjelenítése** gomb csak a rámutatással vagy a fókusszal érhető el. A **Végösszeg megjelenítése** elem kiválasztási művelete csak elmenti az adott oszlop összesítésének megjelenítésére vonatkozó preferenciát, így a preferenciát a rendszer az oldal jövőbeli látogatásakor is alkalmazza. A láblécben ezt az állapotot egy gondolatjel jelöli, amely a oszlopban jelenik meg. (A másik lehetőség, hogy ha az adathalmaz elég kicsi, akkor egy összeg azonnal megjelenik.)

Ha hibázik, és a továbbiakban nem szeretné megjeleníteni az adott oszlopban szereplő összegeket, kattintson az egér jobb oldali gombjával az oszlopra, és válassza az **Összeg elrejtése** lehetőséget, vagy jelölje be az oszlop láblécében az **Összeg elrejtése** gombot. Ezt a beállítást a program a lap későbbi megtekintései esetére is elmenti. 

### <a name="calculating-totals"></a>Teljes összegek számítása
Ha olyan oldalra lép, amelyen látható a lábléc, és az oszlopokat már beállították összesítésekhez, akkor megtörténhet, hogy az összesítések nem jelennek meg a láblécben. A viselkedés függ az oldalon levő adathalmaz méretétől. Ha az adathalmaz kellően kicsi, a program automatikusan megjeleníti az összegeket, valamint az adathalmaz sorainak számát. Ha a láblécben az összesítésre konfigurált oszlopokban gondolatjeleket lát, akkor az adathalmaz túl nagy ahhoz, hogy a rendszer az összegeket azonnal megjelenítse, és az összegek kiszámításához explicit műveletre van szükség. Ehhez kattintson a láblécben a **Kiszámítás** gombra, vagy kattintson az jobb egérgombbal egy oszlopra, és válassza az **Összeg ebben az oszlopban** lehetőséget.

Ha a kiszámítás túl sokáig tart, akkor a művelet a **Mégse** gombra kattintva érvényteleníthető. Néha azonban előfordulhat, hogy az adathalmaz túl nagy az összegek kiszámításához (a szervezet által meghatározott korlát), és a program értesíti, hogy tovább kell szűrnie az adatokat.

A program automatikusan frissíti az összegeket az adathalmazban lévő sorok frissítése, törlése vagy létrehozása során.

## <a name="typing-ahead-of-the-system"></a>A rendszer előtt történő gépelés
Számos üzleti helyzetben rendkívül fontos az adatok gyors beviteli képessége a rendszerbe. Az új rács vezérlő bevezetése előtt a felhasználók csak az aktuális sorban módosíthatják az adatokat. Mielőtt új sort tudnak létrehozni vagy másik sorra váltson át, kénytelenek voltak megvárni, hogy a rendszer sikeresen érvényesítse a változtatásokat. Annak az időtartamnak a csökkentése érdekében, amit a felhasználók az ilyen ellenőrzések befejezésére várnak, valamint a felhasználói hatékonyság javítása érdekében az új rács ezeket az ellenőrzéseket helyesbíti, hogy azok aszinkronban legyenek. Ennek megfelelően a felhasználó más sorokba is átléphet a változtatásokhoz, amíg az előző sor érvényesítése függőben van. 

Ennek az új viselkedésnek a támogatásához egy új oszlop lett hozzáadva a sor állapotához a sorválasztó oszloptól jobbra, amikor a rács szerkesztési módban van. Ez az oszlop a következő állapotok egyikét jelzi:

- **Üres** – A hiányzó állapot képe azt jelzi, hogy a sort a rendszer sikeresen mentette.
- **Feldolgozás függőben** – Ez az állapot azt jelzi, hogy a sorban szereplő változtatásokat a kiszolgáló még nem mentette, de a feldolgozás alatt álló változtatások várólistáján szerepelnek. A rácson kívüli művelet előtt meg kell várnia minden függő módosítás feldolgozását. Ezenkívül a sorokban található szöveg dőlt betűvel jelenik meg a sorok nem mentett állapotának jelzésére. 
- **Érvénytelen állapot** – Ez az állapot azt jelzi, hogy a sor feldolgozásakor valamilyen figyelmeztetés vagy üzenet aktiválódott, és előfordulhat, hogy ez megakadályozta, hogy a rendszer mentse a módosítást a sorban. A régi rácsban, ha a mentés művelet sikertelen volt, a program azonnal visszakényszerítette a sort a kérdés azonnali kijavításához. Az új rácsban azonban értesítést kap, hogy a rendszer ellenőrzési hibát észlelt, de eldöntheti, hogy ki szeretné-e javítani a sorban szereplő problémákat. Ha készen áll a hiba elhárítására, a fókuszt manuálisan is áthelyezheti a sorra. Másik megoldásként kiválaszthatja a **Probléma kijavítása** műveletet. Ez a művelet azonnal visszahelyezi a fókuszt a hibát tartalmazó sorra, és lehetővé teszi a szerkesztést a rácson belül vagy azon kívül. Ne felejtse el, hogy amíg az ellenőrzési figyelmeztetést megoldják, az ezt követő függőben levő sorok feldolgozása le van állítva. 
- **Szüneteltetve** – Ez az állapot azt jelzi, hogy a kiszolgáló a feldolgozását szünetelteti, mert a sor ellenőrzése olyan előugró párbeszédpanelt jelenít meg, amelyen felhasználói bevitel szükséges. Mivel a felhasználó más sorban is megadhat adatokat, az előugró párbeszédpanel nem jelenik meg azonnal a felhasználó számára. Helyette akkor jelenik meg, amikor a felhasználó a feldolgozás folytatása mellett dönt. Ezt az állapotot olyan értesítés kíséri, amely tájékoztatja a felhasználót a helyzetről. Az értesítés tartalmaz egy **Feldolgozás folytatása** műveletet, amely elindítja a felugró párbeszédpanelt.

Amikor a felhasználók az előtt a hely előtt visznek be adatokat, ahol a kiszolgáló feldolgoz, alacsonyabb szintű adatbeviteli élményt tapasztalhatnak, például a keresések hiánya, a vezérlői szintű ellenőrzés és az alapértlemezett értékek bevitele. Ha meg szeretne találni egy értéket a legördülő listáról, akkor arra kell várnia, hogy a kiszolgáló az aktuális sorhoz felzárkózzon. Amikor a kiszolgáló dolgozza fel a sort, akkor az vezérlői szint ellenőrzése és az alapértelmezett értékek bevitele is megtörténik.

### <a name="pasting-from-excel"></a>Beillesztés az Excel programból
A felhasználók mindig is exportálhattak adatokat a Finance and Operations alkalmazások rácsjaiból ide Microsoft Excel segítségével **Exportálás Excelbe** gépezet. Az adatok rendszer előtti bevitelének képessége azonban lehetővé teszi az új rács számára, hogy támogassa a táblázatok Excelből történő másolását és közvetlenül a Finance and Operations alkalmazások rácsába történő beillesztését. Az a rácsvonalcella, amelyből a beillesztési művelet el van indítva, határozza meg, hogy a program hová kezdi a másolt tábla beillesztését. A rács tartalma felülíródik a másolt tábla tartalmával, kivéve a következő két esetet:

- Ha a másolt tábla oszlopainak száma meghaladja a rácsban maradó oszlopok számát, a beillesztés helyétől kezdve, a felhasználó értesítést kap arról, hogy a további oszlopok figyelmen kívül lettek hagyva. 
- Ha a másolt tábla sorainak száma meghaladja a rács sorainak számát, a beillesztés helyétől kezdve a meglévő cellák felülíródnak, és a másolt táblából származó további sorok a rács alján új sorokként jelennek meg. 

## <a name="evaluating-math-expressions"></a>Matematikai kifejezések kiértékelése
A hatékonyság javításaként a felhasználók matematikai képleteket írhatnak be a rács numerikus celláiba. A számítást nem kell a rendszeren kívüli alkalmazásban végezniük. Ha például a **=15\*4** értéket adja meg, majd a **Tab** billentyű lenyomásával kilép a mezőből, akkor a rendszer kiértékeli a kifejezést, majd a mezőbe a **60** értéket menti.

Ha azt szeretné, hogy a rendszer bizonyos értékeket kifejezésként ismerjen fel, akkor az értéket egyenlőségjellel (**=**) kell bevezetnie. A támogatott operátorokkal és szintaxissal kapcsolatos további információkat lásd: [Támogatott matematikai szimbólumok](http://bugwheels94.github.io/math-expression-evaluator/#supported-maths-symbols).

## <a name="grouping-tabular-data"></a>Táblázatos adatok csoportosítása
Az üzleti felhasználóknak gyakran kell ad hoc adatelemzést végezniük. Míg ez megtehető adatok exportálásával ide Microsoft Excel és pivot táblák segítségével a **Csoportosítás rácsokban** Az új rácsvezérlő funkciótól függő funkció lehetővé teszi a felhasználók számára, hogy érdekes módon rendezzék táblázatos adataikat a Finance and Operations alkalmazásokban. Mivel ez a funkció kiterjeszti az **Összegek** funkciót, a **Csoportosítás** lehetővé teszi, hogy egy csoport szintjén részösszegek megadásával jelentőségteljes betekintést nyerjen az adatokba.

A funkció használatához kattintson a jobb egérgombbal a csoportosítani kívánt oszlopra, és válassza ki a **Csoportosítás az oszlop szerint** lehetőséget. Ez a művelet a kiválasztott oszlop szerint rendezi az adatokat, egy új **Csoportosítás** oszlopot ad hozzá a rácshoz, majd az egyes csoportok elejére „fejlécsorokat” szúr be. Ezek a fejlécsorok a következő információkat tartalmazzák az egyes csoportokról:

- A csoport adatértéke 
- Oszlop neve (ez az információ különösen akkor hasznos, ha a csoportosítás több szintjét használja)
- A csoportban levő adatsorok száma
- Részösszegek az összes olyan oszlophoz, amelyet összegek megjelenítésére konfiguráltak

A [Mentett nézetek](saved-views.md) engedélyezése esetén ezt a csoportosítást személyre szabhatja az oldal legközelebbi meglátogatásakori gyors hozzáférés részeként.

### <a name="multiple-levels-of-grouping"></a>Több szintű csoportosítás
Miután egyetlen oszlop szerint csoportosította az adatokat, csoportosíthatja az adatokat egy másik oszlop szerint, ha a kívánt oszlopban a **Csoportosítás az oszlop szerint** lehetőséget választja. Ez a folyamat addig megismételhető, amíg 5 egymásba ágyazott csoportosítási szintet nem ér el, ami a maximális támogatott mélység. Ezen a ponton a továbbiakban nem tud további oszlopok szerint csoportosítani.

A csoportosítást bármikor eltávolíthatja bármelyik oszlopból, ha a jobb gombbal az adott oszlopra kattint, és a **Szétválasztás** parancsot választja. A csoportosítást az összes oszlopból úgy is eltávolíthatja, hogy a **Rácsbeállítások**, majd az **Összes szétválasztása** lehetőséget választja.

### <a name="sorting-grouped-data"></a>Csoportosított adatok rendezése
Miután az adatokat egy vagy több oszlop szerint csoportosította, bármelyik csoportosító oszlop rendezési irányát módosíthatja a megfelelő oszlopfejléc segítségével. 

A nem csoportosított oszlopok szerinti rendezés viselkedése a termék verziójától függ:

- A 10.0.24-es és korábbi verziókban, ha nem csoportosított oszlopra rendez, a csoportosítás minden oszlopból eltávolítódik, és az adatok a kiválasztott oszlopba rendeződnek. 
- A 10.0.25-ös és újabb verziókban, ha nem csoportosított oszlopra rendez, a csoportosítás érintetlen marad, és az adatok az egyes csoportokon belül vannak rendezve, a kiválasztott oszlop alapján.

### <a name="expanding-and-collapsing-groups"></a>Csoportok kibontása és összecsukása
Az adatok kezdeti csoportosítása esetén minden csoport ki lesz bontva. Az adatok összegzett nézeteit az egyes csoportok összecsukásával lehet létrehozni, illetve a csoport kibontása és összecsukása révén segítséget nyújthat a navigálásban az adatokon keresztül. Egy csoport kibontásához vagy összecsukásához válassza ki a nyíl (>) gombot a megfelelő csoportfej sorban. Ne feledje, hogy az egyes csoportok kibontása/összecsukása **nincs** mentve a személyre szabásban.

### <a name="selecting-and-unselecting-rows-at-the-group-level"></a>Sorok kiválasztása és a kijelölés megszüntetése a csoport szintjén
A rács első oszlopának felső részén található jelölőnégyzet bejelölésével ugyanúgy kiválaszthatja (vagy megszüntetheti a kiválasztást) a rács minden sorában, ha a megfelelő csoportfej sorában a jelölőnégyzetet bejelöli, és egy csoport minden sorát is gyorsan kiválaszthatja (vagy törölheti a kijelölést). A csoportfej sorában található jelölőnégyzet mindig a csoport sorainak aktuális kiválasztási állapotát tükrözi, függetlenül attól, hogy az összes sor ki van-e választva, vagy csak néhány sor van kiválasztva.

### <a name="hiding-column-names"></a>Oszlopok neveinek elrejtése
Az adatok csoportosításakor az alapértelmezett viselkedés a csoportfej sorában az oszlop nevének megjelenítése. Elhagyhatja az oszlop nevét a csoportfej soraiban, ha kiválasztja a **Rácsbeállítások** > **Csoportoszlop nevének elrejtése** lehetőséget.

### <a name="grouping-on-date-and-time-columns"></a>Csoportosítás dátum és idő oszlopok alapján
A 10.0.24-es verziótól kezdve a Dátum vagy a DateTime mezőknél a lehetőség hozzáadásra került az év, hónap vagy nap szerinti csoportosításhoz. A megfelelő fejlécsorban szereplő "érték" csoport megegyezik az adott mező formátumával. Ezenkívül a DateTime és Time mezőkben csoportosíthat óra, perc vagy másodperc szerint. 

## <a name="freezing-columns"></a>Oszlopok rögzítése
A rács egyes oszlopai elég fontosak lehetnek kontextus tekintetében ahhoz, hogy nem szeretné, hogy kigörgethetők legyenek a nézetből. Ehelyett érdemes lehet, hogy az oszlopokban lévő értékek mindig láthatóak legyenek. A **Oszlopok fagyasztása rácsban** funkció ezt a rugalmasságot biztosítja a felhasználók számára. 

Oszlop rögzítéséhez kattintson a jobb gombbal az oszlop fejlécére, majd válassza az **Oszlop rögzítése** lehetőséget. Amikor először végrehajtka ezt a lépést, a kiválasztott oszlop lesz az első oszlop, és többé nem lesz kigörgethető a nézetből. Az ezt követő rögzített oszlopok mindegyike az utolsóként rögzített oszlop jobb oldalához lesz hozzáadva. A Rögzített oszlopok újrarendezéséhez a szokásos Áthelyezés funkciót használhatja. A rögzített oszlopok azonban nem helyezhetők át úgy, hogy a rögzítetlen oszlopok között jelenjenek meg. Hasonlóképp, a nem rögzített oszlopok nem helyezhetők át úgy, hogy a rögzített oszlopok között jelenjenek meg.

Oszlop rögzítésének feloldásához kattintson a jobb gombbal a rögzített oszlop fejlécére, majd válassza az **Oszlop rögzítésének feloldása** lehetőséget. 

Ne feledje, hogy az új rács sorkiválasztási és sorállapot-oszlopait mindig rögzíti a rendszer az első két oszlopban. Ezért ha ezek az oszlopok egy rácsban szerepelnek, akkor mindig láthatók lesznek a felhasználó számára, attól függetlenül, hogy a rács vízszintes görgetése milyen helyzetben van. Ezt a két oszlopot nem lehet átrendezni.

## <a name="autofit-column-width"></a>Oszlop szélességének automatikus illesztése
Az Excelhez hasonlóan a felhasználók az oszlopban jelenleg látható tartalom alapján automatikusan kényszeríthetik egy oszlopot átméretezését. Ehhez kattintson duplán az oszlop méretező fogantyúira, vagy tegye a fókuszt az oszlopfejlécbe, és nyomja le az **A** billentyűt (automatikus kitöltéshez). Ez a funkció a 10.0.23 verziótól kezdve érhető el.

## <a name="frequently-asked-questions"></a>Gyakori kérdések
### <a name="how-do-i-enable-the-new-grid-control-in-my-environment"></a>Hogyan engedélyezhető az új rácsvezérlő a saját környezetemben? 

A **Új rácsvezérlő** funkció elérhető közvetlenül a Funkciókezelésben bármilyen környezetben. Miután engedélyezte a funkciót a Funkciókezelésben, minden ezt követő felhasználói munkamenet az új rácsvezérlőt fogja használni. 

Ez a funkció alapértelmezés szerint a 10.0.21-es verziótól be van kapcsolva, és a cél az, hogy kötelezővé váljon a 10.0.25-ös verzióban. 

## <a name="developer-opting-out-individual-pages-from-using-the-new-grid"></a>[Fejlesztő] Egyes oldalak elutasítása az új rács használatából 
Ha a szervezet egy olyan oldalt észlel, amelyen problémák lépnek fel az új rács használata miatt, akkor egy API felület lehetővé teszi, hogy az egyes űrlapok használhassák a régi rácsvezérlőt, miközben a rendszer további részei az új rácsvezérlőt használják. Ha el szeretné utasítani az egyes oldalakat az új rácsból, adja hozzá a következő hívásfeladást `super()` az űrlap `run()` módjához.

```this.forceLegacyGrid();```

Ez az API mindaddig megmarad, amíg az új rácsvezérlés kötelezővé nem válik. Ez a változás jelenleg 2022 októberére irányul. Ha bármilyen probléma az API használatát igényli jelentse azokat a Microsoftnak.

### <a name="forcing-a-page-to-use-the-new-grid-after-previously-opting-out-the-grid"></a>Új rács használatának kikényszerítése egy laphoz a rács korábbi elutasítását követően
Ha az új rács használatát egy adott oldalra vonatkozóan elutasította, akkor az alapproblémák megoldása után később érdemes lehet újra engedélyeznie az új rácsot. Ehhez egyszerűen el kell távolítania a következő hívását: `forceLegacyGrid()`. A módosítás csak akkor lép hatályba, ha az alábbiak valamelyike bekövetkezik:

- **Környezet újratelepítése**: Amikor egy környezetet frissítenek és újratelepítenek, az új rácsból (FormControlReactGridState) elutasított lapokat tároló táblázat automatikusan törlődik.
- **Tábla kézi törlése**: Fejlesztési forgatókönyvek esetén SQL segítségével törölni kell a FormControlReactGridState táblát, majd újra kell indítani az AOS-t. Ez a műveletkombináció visszaállítja az új rácshálót elutasító lapok gyorsítótárazását.

## <a name="developer-opting-individual-grids-out-of-the-typing-ahead-of-the-system-capability"></a>[Fejlesztő] Egyedi rácsok letiltása a rendszer előtti gépelés funkcióból
Felmerültek olyan forgatókönyvek, amelyek nem alkalmasak a megfelelő együttműködésre *Gépeljen a rendszer előtt* a rács képessége. (Például bizonyos kódok, amelyek egy sor érvényesítésekor aktiválódnak, egy adatforrás-kutatást indítanak el, és a kutatás megsértheti a meglévő sorok nem véglegesített szerkesztéseit.) Ha szervezete ilyen forgatókönyvet észlel, elérhető egy API, amely lehetővé teszi a a fejlesztő kiválaszt egy egyedi rácsot az aszinkron sorellenőrzésből, és visszatér a régi viselkedéshez.

Ha az aszinkron sorellenőrzés le van tiltva egy rácsban, a felhasználók nem hozhatnak létre új sort, vagy nem léphetnek át egy másik sorba a rácsban, amíg az aktuális sorban ellenőrzési problémák vannak. A művelet mellékhatásaként a táblázatok nem illeszthetők be Excelből a Finance and Operations rácsokba.

Ha egy adott rácsot szeretne kihagyni az aszinkron sorellenőrzésből, adja hozzá a következő hívást`super()` ban,-ben`run()` a forma módszere.

```<gridControl>.allowPreemptiveClient(false);```

> [!NOTE]
> - Ezt a hívást csak kivételes esetekben szabad lehívni, és nem lehet minden rácsra jellemző.
> - Nem javasoljuk, hogy az űrlap betöltése után futás közben kapcsolja át ezt az API-t.

## <a name="developer-size-to-available-width-columns"></a>[Fejlesztői] Oszlopok rendelkezésre álló szélességre méretezése
Ha egy fejlesztő beállítja a **WidthMode** tulajdonságot **SizeToAvailable** értékre az új rácsban található oszlopokhoz, akkor ezek az oszlopok kezdetben ugyanolyan szélességgel rendelkeznek, mintha a tulajdonság **SizeToContent** értékre lenne állítva. A rácson belül azonban képesek kiszélesedni, hogy kihasználják az extra elérhető helyet. Ha a tulajdonság több oszlopnál **SizeToAvailable** értékre van állítva, akkor az egyes oszlopok a rácson belül a további rendelkezésre álló szélességet osztják fel. Ha viszont a felhasználó manuálisan átméretezi az egyik oszlopot, akkor az oszlop statikus lesz. Ezen a szélességen marad, és a rendszer nem nyúlik tovább, hogy kihasználja az extra elérhető szélességet.

## <a name="known-issues"></a>Ismert problémák
Ez a szakasz az új rácsvezérlő ismert problémáinak listáját tartalmazza.

### <a name="open-issues"></a>Nyitott problémák
- Az **Új rácsvezérlő** funkció engedélyezése után néhány oldal továbbra is a meglévő rácsvezérlőt fogja használni. Ez a következő helyzetekben fog történni:
 
    - Egy kártyalista szerepel azon az oldalon, amely több oszlopban jelenik meg.
    - Egy csoportosított kártyalista szerepel az oldalon.
    - Nem reagáló bővíthető vezérlővel rendelkező rácsoszlop.

    Amikor egy felhasználó először találkozik egy ilyen helyzettel, egy üzenet jelenik meg az oldal frissítésével kapcsolatban. Az üzenet megjelenése után az oldal a következő termékfrissítési verzióig továbbra is a meglévő rácsot használja az összes felhasználó számára. A jövőbeli frissítéshez figyelembe kell venni ezeket a forgatókönyveket, hogy az új rács használható legyen.

- [KB 4582758] A rekordok elmosódottak, ha a nagyítást 100-ról bármely más százalékra módosítja
- [KB 4592012] Váratlan ügyfélhiba történik az IE11 alkalmazásban több sor Excel programból történő beillesztésekor

    A Microsoft keres javítást ehhez a problémához


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
