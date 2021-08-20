---
title: Rács funkciói
description: Ez a témakör ismerteti a rács vezérlőelem számos erőteljes funkcióját. Az új rács funkciónak engedélyezve kell lennie ahhoz, hogy hozzáférhessen ezekhez a funkciókhoz.
author: jasongre
ms.date: 08/04/2021
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
ms.openlocfilehash: 9bdefeedf8bbbe60f3f76d234f9b393cc8e5dbe8ede7e320e00d0b8e20dbbf73
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6775242"
---
# <a name="grid-capabilities"></a>Rácsfunkciók

[!include [banner](../includes/banner.md)]


Az új rács vezérlőelem számos hasznos és erőteljes funkciót tartalmaz, amelyek a felhasználó hatékonyságának növelésére, az adatokkal kapcsolatos érdekesebb nézetek kialakítására és az adatokkal kapcsolatos jelentőségteljes rálátás megszerzésére használhatók. Ez a cikk a következő funkciókat mutatja be: 

-  Teljes összegek számítása
-  A rendszer előtt történő gépelés
-  Matematikai kifejezések kiértékelése 
-  Táblázatos adatok csoportosítása (külön lehet engedélyezni az **(Előzetes verzió) Csoportosítás rácsokban** szolgáltatással)
-  Oszlopok rögzítése

## <a name="calculating-totals"></a>Teljes összegek számítása
A Finance and Operations alkalmazásokban a felhasználók a számokat tartalmazó oszlopok alján látható összesítéseket megtekinthetik a rácsokban. Ezeket az összegeket a rács alján látható lábléc szakasz mutatja. 

### <a name="showing-the-grid-footer"></a>A rács láblécének megjelenítése
A Finance and Operations alkalmazásokban minden egyes táblázatos rács alján láblécterület található. A lábléc értékes információkat jeleníthet meg, amely a rácsban megjelenő adatokhoz kapcsolódik. Íme néhány példa az ilyen információkra:

- A táblázatból kiválasztott sorok száma (ha egynél több rekord van kiválasztva)
- Végösszegek a konfigurált numerikus oszlopok alján
- Az adathalmazban lévő sorok száma összesen 

Alapértelmezetten ez a lábléc rejtett, de be lehet kapcsolni. A rács láblécének megjelenítéséhez kattintson a jobb gombbal a rács egy oszlopának fejlécére, és válassza ki a **Lábléc megjelenítése** lehetőséget. Miután bekapcsolta egy adott rács láblécét, erre a beállításra a rendszer addig fog emlékezni, amíg a felhasználó el nem rejti a láblécet. A lábléc elrejtéséhez kattintson a jobb gombbal az oszlopfejlécre, és válassza a **Lábléc elrejtése** lehetőséget.  (Egy jövőbeli frissítésben a **Lábléc megjelenítése/elrejtése** műveletet valószínűleg áthelyezzük egy másik helyre.) 

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
A felhasználók mindig képesek voltak a Finance and Operations alkalmazások rácsaiból az Excel programba adatokat exportálni az **Exportálás az Excel programba** mechanizmussal. Az adatok rendszert megelőzően való megadásának képessége lehetővé teszi az új rács számára, hogy támogassa a táblák másolását Excelből, és közvetlenül a Finance and Operations alkalmazások rácsaiba. Az a rácsvonalcella, amelyből a beillesztési művelet el van indítva, határozza meg, hogy a program hová kezdi a másolt tábla beillesztését. A rács tartalma felülíródik a másolt tábla tartalmával, kivéve a következő két esetet:

- Ha a másolt tábla oszlopainak száma meghaladja a rácsban maradó oszlopok számát, a beillesztés helyétől kezdve, a felhasználó értesítést kap arról, hogy a további oszlopok figyelmen kívül lettek hagyva. 
- Ha a másolt tábla sorainak száma meghaladja a rács sorainak számát, a beillesztés helyétől kezdve a meglévő cellák felülíródnak, és a másolt táblából származó további sorok a rács alján új sorokként jelennek meg. 

## <a name="evaluating-math-expressions"></a>Matematikai kifejezések kiértékelése
A hatékonyság javításaként a felhasználók matematikai képleteket írhatnak be a rács numerikus celláiba. A számítást nem kell a rendszeren kívüli alkalmazásban végezniük. Ha például a **=15\*4** értéket adja meg, majd a **Tab** billentyű lenyomásával kilép a mezőből, akkor a rendszer kiértékeli a kifejezést, majd a mezőbe a **60** értéket menti.

Ha azt szeretné, hogy a rendszer bizonyos értékeket kifejezésként ismerjen fel, akkor az értéket egyenlőségjellel (**=**) kell bevezetnie. A támogatott operátorokkal és szintaxissal kapcsolatos további információkat lásd: [Támogatott matematikai szimbólumok](http://bugwheels94.github.io/math-expression-evaluator/#supported-maths-symbols).

## <a name="grouping-tabular-data"></a>Táblázatos adatok csoportosítása
Az üzleti felhasználóknak gyakran kell ad hoc adatelemzést végezniük. Bár ez megoldható az adatok Microsoft Excel alkalmazásba való exportálásával és pivot táblákkal, a táblázatos rácsok **Csoportosítás rácsokban** funkciója amely általánosan elérhető a 10.0.16 verzióban / 40-es platformfrissítésben, amely az új rácsvezérlő funkción alapul lehetővé teszi, hogy a felhasználok a Finance and Operations alkalmazásokban is érdekes módon szervezzék a táblázatos adataikat. Mivel ez a funkció kiterjeszti az **Összegek** funkciót, a **Csoportosítás** lehetővé teszi, hogy egy csoport szintjén részösszegek megadásával jelentőségteljes betekintést nyerjen az adatokba.

A funkció használatához kattintson a jobb egérgombbal a csoportosítani kívánt oszlopra, és válassza ki a **Csoportosítás az oszlop szerint** lehetőséget. Ez a művelet a kiválasztott oszlop szerint rendezi az adatokat, egy új **Csoportosítás** oszlopot ad hozzá a rácshoz, majd az egyes csoportok elejére „fejlécsorokat” szúr be. Ezek a fejlécsorok a következő információkat tartalmazzák az egyes csoportokról: 
-  A csoport adatértéke 
-  Oszlop neve (ez az információ különösen akkor hasznos, ha a csoportosítás több szintjét használja)  
-  A csoportban levő adatsorok száma
-  Részösszegek az összes olyan oszlophoz, amelyet összegek megjelenítésére konfiguráltak

A [Mentett nézetek](saved-views.md) engedélyezése esetén ezt a csoportosítást személyre szabhatja az oldal legközelebbi meglátogatásakori gyors hozzáférés részeként.  

### <a name="multiple-levels-of-grouping"></a>Több szintű csoportosítás
Miután egyetlen oszlop szerint csoportosította az adatokat, csoportosíthatja az adatokat egy másik oszlop szerint, ha a kívánt oszlopban a **Csoportosítás az oszlop szerint** lehetőséget választja. Ez a folyamat addig megismételhető, amíg 5 egymásba ágyazott csoportosítási szintet nem ér el, ami a maximális támogatott mélység. Ezen a ponton a továbbiakban nem tud további oszlopok szerint csoportosítani.  

A csoportosítást bármikor eltávolíthatja bármelyik oszlopból, ha a jobb gombbal az adott oszlopra kattint, és a **Szétválasztás** parancsot választja. A csoportosítást az összes oszlopból úgy is eltávolíthatja, hogy a **Rácsbeállítások**, majd az **Összes szétválasztása** lehetőséget választja.   

Ne feledje, hogy a 10.0.16-os verzió / 40-es platformfrissítés előtt csak egy csoportszint támogatott. Ezekben a verziókban, ha az adatok csoportosítva vannak, és egy másik oszlophoz a **Csoportosítás az oszlop szerint** lehetőséget választja, az eredeti csoportosítás lecserélődik.  


### <a name="expanding-and-collapsing-groups"></a>Csoportok kibontása és összecsukása
Az adatok kezdeti csoportosítása esetén minden csoport ki lesz bontva. Az adatok összegzett nézeteit az egyes csoportok összecsukásával lehet létrehozni, illetve a csoport kibontása és összecsukása révén segítséget nyújthat a navigálásban az adatokon keresztül. Egy csoport kibontásához vagy összecsukásához válassza ki a nyíl (>) gombot a megfelelő csoportfej sorban. Ne feledje, hogy az egyes csoportok kibontása/összecsukása **nincs** mentve a személyre szabásban.

### <a name="selecting-and-unselecting-rows-at-the-group-level"></a>Sorok kiválasztása és a kijelölés megszüntetése a csoport szintjén
A rács első oszlopának felső részén található jelölőnégyzet bejelölésével ugyanúgy kiválaszthatja (vagy megszüntetheti a kiválasztást) a rács minden sorában, ha a megfelelő csoportfej sorában a jelölőnégyzetet bejelöli, és egy csoport minden sorát is gyorsan kiválaszthatja (vagy törölheti a kijelölést). A csoportfej sorában található jelölőnégyzet mindig a csoport sorainak aktuális kiválasztási állapotát tükrözi, függetlenül attól, hogy az összes sor ki van-e választva, vagy csak néhány sor van kiválasztva.

### <a name="hiding-column-names"></a>Oszlopok neveinek elrejtése
Az adatok csoportosításakor az alapértelmezett viselkedés a csoportfej sorában az oszlop nevének megjelenítése. A verzió 10.0.14/Platform Update 38-es verziójától kezdve elhagyhatja az oszlop nevét a csoportfej soraiban, ha kiválasztja a **Rácsbeállítások** > **Csoportoszlop nevének elrejtése** lehetőséget.

## <a name="freezing-columns"></a>Oszlopok rögzítése
A rács egyes oszlopai elég fontosak lehetnek kontextus tekintetében ahhoz, hogy nem szeretné, hogy kigörgethetők legyenek a nézetből. Ehelyett azt szeretné, hogy az oszlopokban lévő értékek mindig láthatók legyenek. A 10.0.17-es verzióban a **Rács oszlopainak rögzítése** funkció biztosítja ezt a rugalmasságot a felhasználók számára. 

Oszlop rögzítéséhez kattintson a jobb gombbal az oszlop fejlécére, majd válassza az **Oszlop rögzítése** lehetőséget. Amikor először végrehajtka ezt a lépést, a kiválasztott oszlop lesz az első oszlop, és többé nem lesz kigörgethető a nézetből. Az ezt követő rögzített oszlopok mindegyike az utolsóként rögzített oszlop jobb oldalához lesz hozzáadva. A Rögzített oszlopok újrarendezéséhez a szokásos Áthelyezés funkciót használhatja. A rögzített oszlopok azonban nem helyezhetők át úgy, hogy a rögzítetlen oszlopok között jelenjenek meg. Hasonlóképp, a nem rögzített oszlopok nem helyezhetők át úgy, hogy a rögzített oszlopok között jelenjenek meg.

Oszlop rögzítésének feloldásához kattintson a jobb gombbal a rögzített oszlop fejlécére, majd válassza az **Oszlop rögzítésének feloldása** lehetőséget. 

Ne feledje, hogy az új rács sorkiválasztási és sorállapot-oszlopait mindig rögzíti a rendszer az első két oszlopban. Ezért ha ezek az oszlopok egy rácsban szerepelnek, akkor mindig láthatók lesznek a felhasználó számára, attól függetlenül, hogy a rács vízszintes görgetése milyen helyzetben van. Ezt a két oszlopot nem lehet átrendezni.

## <a name="frequently-asked-questions"></a>Gyakori kérdések
### <a name="how-do-i-enable-the-new-grid-control-in-my-environment"></a>Hogyan engedélyezhető az új rácsvezérlő a saját környezetemben? 

**10.0.9 / 33-as platformfrissítés vagy újabb**

A **Új rácsvezérlő** funkció elérhető közvetlenül a Funkciókezelésben bármilyen környezetben. A többi nyilvános előnézeti funkcióhoz hasonlóan a funkció engedélyezése termelési környezetben a [Kiegészítő felhasználási szerződés](public-preview-terms.md) hatálya alá tartozik.  

**10.0.8 / 32-es platformfrissítés és 10.0.7 / 31-es platformfrissítés**

Az **Új rácsvezérlő** funkció engedélyezhető az 1. szintű (fejlesztés/tesztelés) és a 2. szintű (tesztkörnyezet) környezetekben, hogy az alábbi lépések követésével további teszteket és tervezési változtatásokat lehessen biztosítani.

1.  **Engedélyezze a tesztcsomagot**: hajtsa végre a következő SQL-utasítást: 

    `INSERT INTO SYSFLIGHTING (FLIGHTNAME, enabled, FLIGHTSERVICEID, PARTITION) VALUES('CLIReactGridEnableFeature', 1, 0, 5637144576);`

2. **IIS alaphelyzetbe állítása** a statikus tesztelési gyorsítótár kiürítéséhez. 

3.  **Keresse meg a funkciót**: ugorjon a **Funkciók kezelése** munkaterületre. Ha az **Új rácsvezérlő** nem szerepel az összes funkció listáján, akkor válassza a **frissítések keresése** lehetőséget.   

4.  **Engedélyezze a funkciót**: keresse meg az **Új rácsvezérlő** funkciót a funkciólistában, majd válassza ki az **Engedélyezés most** lehetőséget a részleteket tartalmazó ablaktáblán. Ne feledje, hogy a böngésző frissítése szükséges. 

Minden további felhasználói munkamenet engedélyezett új rácsvezérlővel indul.

## <a name="developer-opting-out-individual-pages-from-using-the-new-grid"></a>[Fejlesztő] Egyes oldalak elutasítása az új rács használatából 
Ha a szervezet egy olyan oldalt észlel, amelyen problémák lépnek fel az új rács használata miatt, akkor a 10.0.13 / 37-es platformfrissítéstől egy API felület lehetővé teszi, hogy az egyes űrlapok használhassák a régi rácsvezérlőt, miközben a rendszer további részei az új rácsvezérlőt használják. Ha el szeretné utasítani az egyes oldalakat az új rácsból, adja hozzá a következő hívásfeladást `super()` az űrlap `run()` módjához.

 ```this.forceLegacyGrid();```

Ezt az API-t a 2021 októberi kiadásig kell figyelembe venni, amikor az új rácsvezérlő használata kötelezővé válik. Ha bármilyen probléma az API használatát igényli jelentse azokat a Microsoftnak.

### <a name="forcing-a-page-to-use-the-new-grid-after-previously-opting-out-the-grid"></a>Új rács használatának kikényszerítése egy laphoz a rács korábbi elutasítását követően
Ha az új rács használatát egy adott oldalra vonatkozóan elutasította, akkor az alapproblémák megoldása után később érdemes lehet újra engedélyeznie az új rácsot. Ehhez egyszerűen el kell távolítania a következő hívását: `forceLegacyGrid()`. A módosítás csak akkor lép hatályba, ha az alábbiak valamelyike bekövetkezik:

- **Környezet újratelepítése**: Amikor egy környezetet frissítenek és újratelepítenek, az új rácsból (FormControlReactGridState) elutasított lapokat tároló táblázat automatikusan törlődik.

- **Tábla kézi törlése**: Fejlesztési forgatókönyvek esetén SQL segítségével törölni kell a FormControlReactGridState táblát, majd újra kell indítani az AOS-t. Ez a műveletkombináció visszaállítja az új rácshálót elutasító lapok gyorsítótárazását.  

## <a name="developer-size-to-available-width-columns"></a>[Fejlesztői] Oszlopok rendelkezésre álló szélességre méretezése
Ha egy fejlesztő beállítja a **WidthMode** tulajdonságot **SizeToAvailable** értékre az új rácsban található oszlopokhoz, akkor ezek az oszlopok kezdetben ugyanolyan szélességgel rendelkeznek, mintha a tulajdonság **SizeToContent** értékre lenne állítva. A rácson belül azonban képesek kiszélesedni, hogy kihasználják az extra elérhető helyet. Ha a tulajdonság több oszlopnál **SizeToAvailable** értékre van állítva, akkor az egyes oszlopok a rácson belül a további rendelkezésre álló szélességet osztják fel. Ha viszont a felhasználó manuálisan átméretezi az egyik oszlopot, akkor az oszlop statikus lesz. Ezen a szélességen marad, és a rendszer nem nyúlik tovább, hogy kihasználja az extra elérhető szélességet.  

## <a name="known-issues"></a>Ismert problémák
Ez a szakasz az új rácsvezérlő ismert problémáinak listáját tartalmazza.  

### <a name="open-issues"></a>Nyitott problémák
-  Az **Új rácsvezérlő** funkció engedélyezése után néhány oldal továbbra is a meglévő rácsvezérlőt fogja használni. Ez a következő helyzetekben fog történni:  
    -  Egy kártyalista szerepel azon az oldalon, amely több oszlopban jelenik meg.
    -  Egy csoportosított kártyalista szerepel az oldalon.
    -  Nem reagáló bővíthető vezérlővel rendelkező rácsoszlop.

    Amikor egy felhasználó először találkozik egy ilyen helyzettel, egy üzenet jelenik meg az oldal frissítésével kapcsolatban. Az üzenet megjelenése után az oldal a következő termékfrissítési verzióig továbbra is a meglévő rácsot használja az összes felhasználó számára. A jövőbeli frissítéshez figyelembe kell venni ezeket a forgatókönyveket, hogy az új rács használható legyen.    
    
-  [KB 4582758] A rekordok elmosódottak, ha a nagyítást 100-ról bármely más százalékra módosítja
-  [KB 4592012] Váratlan ügyfélhiba történik az IE11 alkalmazásban több sor Excel programból történő beillesztésekor
    -  A Microsoft keres javítást ehhez a problémához

### <a name="fixed-as-part-of-10016"></a>10.0.16 részeként javítva

-  [KB 4598335] A többsoros karakterlánc-vezérlők nem vezsik figyelembe a DisplayHeights tulajdonságot a listákban/kártyákban 
-  [KB 4591891] A számlajavaslat sorai eltűnnek a sorok jelölésének megszüntetésekor
-  [KB 4592104] A „Probléma javítása” gombra kattintva és az ellenőrzési probléma kijavítása nélkül továbblépve nem lehet szerkeszteni a rekordokat
-  [KB 4594449] A dátumválasztón belül hiányzik a „Soha” és a „Törlés” gomb 
-  [KB 4594448] Az új rács másképp kezeli az időbevitelt
-  [KB 4600059] Váratlan ügyfélhiba történt az e-mailes leszabályozáskor
-  [KB 4574584] A költségmelléklet előnézete nem érhető el, ha az egérmutatót a nyugta ikon fölé helyezi

### <a name="fixed-as-part-of-10015"></a>10.0.15 részeként javítva    

-  (Minőségi frissítés) [KB 4594444] Nem várt ügyfélhiba a szegmentált bejegyzésvezérlő előnézetében
-  [KB 4582723] A megjelenítési beállítások nem jelennek meg, ha az űrlap életciklusában később próbálja meg
-  [KB 4591988] Problémák egy értéknek a ReferenceGroup keresésből billentyűzet használatával való kiválasztásakor
-  [KB 4588958] A Regression Suite Automation Tool (RSAT) teszt hibávan meghiúsul: TypeError: Nem olvasható „text” tulajdonság nem definiált
-  [KB 4591970] Váratlan ügyfélhiba történt az Excel programból közvetlenül a rácsra kattintás után történő beillesztéskor
-  [KB 4591904] Az adatváltozások mentése nem történik meg, ha egy vezérlőelem szerkesztése után a felhasználó azonnal rákattintott egy másik vezérlőelemre, és megnyitotta a keresését
-  [KB 4584752] Váratlan ügyfélhiba a Projektszámla javaslatok lapján
-  [KB 4584540] Nem lehet elhagyni a rácsot, miután egyetlen sort beillesztett egy naplósorba
-  [KB 4591908] Új sor létrehozásakor a fókusz abban az oszlopban marad, amelyben tartózkodott

### <a name="fixed-as-part-of-10014"></a>10.0.14 részeként javítva

-  (Minőségi frissítés) [KB 4584752] Váratlan ügyfélhiba a Projektszámla javaslatok lapján
-  [KB 4583880] A Regression Suite Automation Tool (RSAT) tesztek sikertelenek az OpenLookup műveletben a „Nem olvasható tulajdonság RowIndex nem definiált” művelettel
-  [KB 4583847] Váratlan ügyfélhiba a keresések közötti navigáláskor

### <a name="fixed-as-part-of-10013"></a>10.0.13 részeként javítva

-  (Minőségi frissítés) [KB 4584752] Váratlan ügyfélhiba a Projektszámla javaslatok lapján
-  (Minőségi frissítés) [KB 4583880] A Regression Suite Automation Tool (RSAT) tesztek sikertelenek az OpenLookup műveletben a „Nem olvasható tulajdonság RowIndex nem definiált” művelettel
-  (Minőségi frissítés) [KB 4583847] Váratlan ügyfélhiba a keresések közötti navigáláskor 
-  (Minőségi frissítés) [471777. hiba] Nem lehet kiválasztani a rácsban a mezőket a mobilalkalmazás szerkesztéséhez vagy létrehozásához
-  [KB 4582727] A rács lefagy, miután felhasználó egy párbeszédpanelt kap a több mennyiséggel rendelkező cikkek miatt
-  [474851. hiba] A hivatkozási csoport vezérlőinek hivatkozásai nem használhatók 
-  [474848. hiba] A rácsokkal rendelkező továbbfejlesztett előnézetek nem jelennek meg
-  [KB 4582726] A RotateSign tulajdonság nem kerül betartására  
-  [470173. hiba] Az inaktív sorokban található jelölőnégyzetek akkor jelennek meg, ha a cellában a térközre rákattintanak
-  [474848. hiba] A rácsokkal rendelkező továbbfejlesztett előnézetek nem jelennek meg
-  [474851. hiba] A hivatkozási csoport vezérlőinek hivatkozásai nem használhatók 
-  [Bug 471777] Nem lehet kiválasztani a rácsban a mezőket a mobilalkalmazás szerkesztéséhez vagy létrehozásához
-  [KB 4569441] Többoszlopos kártyáklistákkal, képek eszköztippeivel és megjelenítési beállításokkal kapcsolatos problémák merültek fel néhány mezőben
-  [KB 4575279] Nem törlődik ki az összes megjelölt sor az Általános naplóból
-  [KB 4575233] A megjelenítési beállítások nem állíthatók vissza másik sorra ugrás után
-  [477884. hiba] A keresések rossz értéket/rekordot adnak vissza, ha az új rácsvezérlő aktiválva van
-  [KB 4571095] A termékbevételezés feladása akkor történik meg, ha véletlenül megnyomja az Enter billentyűt (az oldal alapértelmezett műveletének megfelelő kezelése)
-  [KB 4575437] A szerkeszthető vezérlőket tartalmazó keresések váratlanul bezáródtak
-  [KB 4569418] A szállítási ütemezés űrlapon ismétlődő sor jött létre
-  [KB 4575435] A továbbfejlesztett előzetes verzió néha akkor is fennáll, ha az kurzor már nincs a mező közelében
-  [KB 4575434] A keresés nincs szűrve, ha a mező módosult
-  [KB 4575430] A jelszómezőkben szereplő értékek nincsenek eltakarva a rácsban
-  [KB 4569438] A „feldolgozás egy érvényesítési hiba miatt leállt” felirat jelenik meg a sorok kijelölése után, a szállítói tranzakciók kiegyenlítése közben
-  [KB 4569434] A jogi személyek űrlap frissítése kevesebb rekordot eredményez
-  [KB 4575297] A fókusz folyamatosan a feladatrögzítő ablakra megy át egy rács szerkesztése és átlapozása közben
-  [KB 4566773] A bizonylat-tranzakciók lekérdezésében nem negatívként jelennek meg a korrekciós tranzakciók 
-  [KB 4575288] A fókusz visszaáll az aktív sorra az egyszerű lista sorai közti szegély kiválasztásakor
-  [KB 4575287] A fókusz nem tér vissza az első oszlopra, amikor a le nyíllal új sort hoz létre a naplókban
-  [KB 4564819] Szabadszöveges számla sorai nem törölhetők (mivel az adatforrás ChangeGroupMode=ImplicitInnerOuter)
-  [KB 4563317] Képek esetében nem jelennek meg az eszközleírások/továbbfejlesztett előnézetek

### <a name="fixed-as-part-of-10012"></a>10.0.12 részeként javítva

- [KB 4558545] A táblához tartozó vezérlőelemek nem frissítik a megjelenített cikkek tartalmát.
- [KB 4558570] A cikkek a rekord törlése után is megjelennek a lapon.
- [KB 4558572] Az **ExtendedStyle** listapanellel társított formázás nincs alkalmazva.
- [KB 4558573] Az ellenőrzési hibák nem javíthatók, ha a szükséges változtatás a rácson kívül esik.
- [KB 4558584] A negatív számok nem megfelelően jelennek meg.
- [KB 4560726] "Váratlan ügyfélhiba" történik a listák között a Listanézet vezérlővel történő váltás után.
- [KB 4562141] Új rekord felvétele után a rács indexei nem megfelelőek.
- [KB 4562151] Az **Ellenőrzés** és **Másolás** feladatrögzítő beállítások nem elérhetők a dátum/szám vezérlőkhöz. 
- [KB 4562153] A többszörös kijelölés jelölőnégyzetei nem láthatók a lista-/kártyarácsokon.
- [KB 4562646] Néha nem lehet a rácson kívülre kattintani, miután több sort választott ki a rácsból.
- [KB 4562647] A fókusz a **Közzététel** párbeszédpanel első vezérlőelemére van állítva, miután új sort adott hozzá a biztonsági szerepkörök rácsához.
- [KB 4563310] A továbbfejlesztett előnézet nem záródik be egy sor módosítása után.
- [KB 4563313] "Váratlan ügyfélhiba" történik az Internet Explorerben, amikor egy érték van kiválasztva a keresésben.
- [KB 4564557] A keresések és a legördülő menük nem nyithatók meg az Internet Explorerben
- [KB 4563324] A Navigálás nem működik a **Személyzetkezelés** munkaterület megnyitása után.

### <a name="fixed-as-part-of-10011"></a>10.0.11 részeként javítva

- [432458. probléma] Az üres vagy ismétlődő sorok néhány alárendelt gyűjtemény elején láthatók.
- [KB 4549711] A fizetési javaslat sorait nem lehet helyesen eltávolítani, miután az új rácsvezérlő engedélyezve van.
- [KB 4558374] Nem hozhatók létre olyan rekordok, amelyeknél szükséges a polimorf választó párbeszédpanel.
- [KB 4558375] A súgó szövege nem jelenik meg az új rács oszlopaiban.
- [KB 4558376] A listapanelek rácsa nem a megfelelő magasságban jelenik meg az Internet Explorerben.
- [KB 4558377] A kombinált mezőoszlopok, amelyek szélessége **SizeToAvailable**, nem jelennek meg bizonyos oldalak.
- [KB 4558378] A részletező időnként nem megfelelő rekordot nyit meg.
- [KB 4558379] Hiba történik, amikor keresések nyílnak olyan helyen, ahol **ReplaceOnLookup**=**No**.
- [KB 4558380] A rácsban rendelkezésre álló hely nem töltődik be közvetlenül a lap egy részének becsukása után.
- [KB 4558381] A negatív számok nem megfelelően jelennek meg, / A felhasználók néha elakadnak az ellenőrzési problémák előfordulásakor.
- [KB 4558382] Váratlan ügyfélhibák történnek.
- [KB 4558383] A rácson kívüli vezérlőelemek nem frissülnek a legutóbbi rekord törlése után.
- [KB 4558587] A helyettesítési mezőkhöz kombinált mezőket tartalmazó referenciacsoportok nem jelenítenek meg értékeket.
- [KB 4562143] A mezők nem frissülnek sor módosítása után / Rácsfeldolgozás elakad a sor törlése után.
- [KB 4562645] Kivétel történik, amikor a Regression Suite Automation Tool (RSAT) tesztjeinek futtatása közben megnyitják a keresést.

### <a name="fixed-as-part-of-10010"></a>10.0.10 részeként javítva

- [414301. probléma] Az előző sorok néhány adata eltűnik az új sorok létrehozásakor.
- [417044. hiba] A lista stílusú rácsokhoz nincs üres rácsüzenet.
- [KB 4539058] Bizonyos rácsok (általában a gyorslapokon) néha nem jelennek meg (de a kicsinyítéskor megjelennek).
- [KB 4549734] Az aktív sorokat a rendszer nem kezeli megjelölve, ha a jelölési oszlop el van rejtve.
- [KB 4549796] Az értékek nem szerkeszthetők a rácsban, amikor a nézet módban van.
- [KB 4558367] A szöveg kiválasztása nem következetes a sorok módosításakor.
- [KB 4558368] A billentyűzeten keresztüli többszörös kiválasztás engedélyezve van egyetlen kiválasztás esetében is.
- [KB 4558369] Az állapotjelző képek eltűnnek a hierarchikus rácsban.
- [KB 4558370] Új sor nem görgethető nézetbe.
- [KB 4558372] Az új rács feldolgozási módban megakad, ha a beillesztett tartalom oszlopainak száma meghaladja a rács maradék oszlopainak számát.
- [KB 4562631] Az időértékek formátuma nem megfelelő.

### <a name="quality-update-for-1009platform-update-33"></a>Minőségi frissítés a 10.0.9./Platform update 33-hoz

- [KB 4550367] Az időértékek formátuma nem megfelelő.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
