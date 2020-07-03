---
title: Rács funkciói
description: Ez a témakör ismerteti a rács vezérlőelem számos erőteljes funkcióját. Az új rács funkciónak engedélyezve kell lennie ahhoz, hogy hozzáférhessen ezekhez a funkciókhoz.
author: jasongre
manager: AnnBe
ms.date: 06/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: DefaultDashboard
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations, Core
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2020-02-29
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: 88a4e2fe69000f8034729d468ad5fd108d435c3e
ms.sourcegitcommit: ba340f836e472f13f263dec46a49847c788fca44
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/04/2020
ms.locfileid: "3431360"
---
# <a name="grid-capabilities"></a>Rács funkciói

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Az új rács vezérlőelem számos hasznos és erőteljes funkciót tartalmaz, amelyek a felhasználó hatékonyságának növelésére, az adatokkal kapcsolatos érdekesebb nézetek kialakítására és az adatokkal kapcsolatos jelentőségteljes rálátás megszerzésére használhatók. Ez a cikk a következő funkciókat mutatja be: 

-  Teljes összegek számítása
-  Adatok csoportosítása
-  A rendszer előtt történő gépelés
-  Matematikai kifejezések kiértékelése 

## <a name="calculating-totals"></a>Teljes összegek számítása
A Finance and Operations alkalmazásokban a felhasználók a számokat tartalmazó oszlopok alján látható összesítéseket megtekinthetik a rácsokban. Ezeket az összegeket a rács alján látható lábléc szakasz mutatja. 

### <a name="showing-the-grid-footer"></a>A rács láblécének megjelenítése
A Finance and Operations alkalmazásokban minden egyes táblázatos rács alján láblécterület található. A lábléc értékes információkat jeleníthet meg, amely a rácsban megjelenő adatokhoz kapcsolódik. Íme néhány példa az ilyen információkra:

- A táblázatból kiválasztott sorok száma (ha egynél több rekord van kiválasztva)
- Végösszegek a konfigurált numerikus oszlopok alján
- Az adathalmazban lévő sorok száma összesen 

Alapértelmezetten ez a lábléc rejtett, de egyszerűen be lehet kapcsolni. A rács láblécének megjelenítéséhez kattintson a jobb gombbal a rács egy oszlopának fejlécére, és válassza ki a **Lábléc megjelenítése** lehetőséget. Miután egy adott rácsnál bekapcsolta a láblécet, a rendszer emlékezni fog a beállításra mindaddig, amíg a felhasználó úgy nem dönt, hogy elrejti a láblécet. Ez úgy végezhető el, hogy a jobb gombbal rákattint egy oszlop fejlécére, és kiválasztja a **Lábléc elrejtése** lehetőséget.  Ne feledje, hogy egy jövőbeli frissítésben a **Lábléc megjelenítése/elrejtése** műveletet valószínűleg áthelyezzük. 

### <a name="specifying-columns-with-totals"></a>Összesítéssel ellátott oszlopok megadása
Jelenleg alapértelmezetten egy oszlop sem jeleníti meg az összegeket. Ezt a rács oszlopai szélességének beállításához hasonlóan egyszeri beállítási tevékenységnek tekintjük. Miután megadta, hogy szeretné egy oszlop összegeit megtekinteni, a rendszer a lap legközelebbi meglátogatásakor emlékezni fog a beállításra.  

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

## <a name="grouping-data"></a>Adatok csoportosítása
Az üzleti felhasználóknak gyakran kell ad hoc adatelemzést végezniük. Bár ez megoldható az adatok Microsoft Excel alkalmazásba való exportálásával és pivot táblákkal, a táblázatos rácsok **Csoportosítás** funkciója lehetővé teszi, hogy a felhasználok a Finance and Operations alkalmazásokban is érdekes módon szervezzék az adataikat. Mivel ez a funkció kiterjeszti az **Összegek** funkciót, a **Csoportosítás** azt is lehetővé teszi, hogy egy csoport szintjén részösszegek megadásával jelentőségteljes betekintést nyerjen az adatokba.

A funkció használatához kattintson a jobb egérgombbal a csoportosítani kívánt oszlopra, és válassza ki a **Csoportosítás az oszlop szerint** lehetőséget. Ez a művelet a kiválasztott oszlop szerint rendezi az adatokat, egy új csoportosítási oszlopot ad hozzá a rácshoz, majd az egyes csoportok elejére „fejlécsorokat” szúr be. Ezek a fejlécsorok a következő információkat tartalmazzák az egyes csoportokról: 
-  A csoport adatértéke 
-  Oszlop címkéje (ez az információ különösen akkor hasznos, ha a csoportosítás több szintje támogatott.)
-  A csoportban levő adatsorok száma
-  Részösszegek az összes olyan oszlophoz, amelyet összegek megjelenítésére konfiguráltak

A [Mentett nézetek](saved-views.md) engedélyezése esetén ezt a csoportosítást személyre szabhatja az oldal legközelebbi meglátogatásakori gyors hozzáférés részeként.  

Ha egy másik oszlophoz jelöli ki a **Csoportosítás az oszlop szerint** lehetőséget, akkor a program felülírja az eredeti csoportosítást, mivel a 10.0.9-es verzió platform Update 33 esetén csak egy csoportosítási szint támogatott.

Ha vissza szeretné vonni a csoportosítást egy rácsban, kattintson a jobb gombbal a csoportosítási oszlopra, és válassza a **Szétválasztás** lehetőséget.  

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

## <a name="frequently-asked-questions"></a>Gyakori kérdések
### <a name="how-do-i-enable-the-new-grid-control-in-my-environment"></a>Hogyan engedélyezhető az új rácsvezérlő a saját környezetemben? 

**10.0.9/33. és későbbi platformfrissítések** esetében az **Új rácsvezérlő** funkció elérhető közvetlenül a Funkciókezelésben bármilyen környezetben. A többi nyilvános előnézeti funkcióhoz hasonlóan a funkció engedélyezése termelési környezetben a [Kiegészítő felhasználási szerződés](https://go.microsoft.com/fwlink/?linkid=2105274) hatálya alá tartozik.  

**10.0.8/32-es platformfrissítés és 10.0.7 platformfrissítés 31** Az **Új rácsvezérlő** funkció engedélyezhető az 1. szintű (fejlesztés/tesztelés) és a 2. szintű (tesztkörnyezet) környezetekben, hogy az alábbi lépések követésével további teszteket és tervezési változtatásokat lehessen biztosítani.

1.  **Engedélyezze a tesztcsomagot**: hajtsa végre a következő SQL-utasítást: 

    `INSERT INTO SYSFLIGHTING (FLIGHTNAME, enabled, FLIGHTSERVICEID, PARTITION) VALUES('CLIReactGridEnableFeature', 1, 0, 5637144576);`

2. **IIS alaphelyzetbe állítása** a statikus tesztelési gyorsítótár kiürítéséhez. 

3.  **Keresse meg a funkciót**: ugorjon a **Funkciók kezelése** munkaterületre. Ha az **Új rácsvezérlő** nem szerepel az összes funkció listáján, akkor válassza a **frissítések keresése** lehetőséget.   

4.  **Engedélyezze a funkciót**: keresse meg az **Új rácsvezérlő** funkciót a funkciólistában, majd válassza ki az **Engedélyezés most** lehetőséget a részleteket tartalmazó ablaktáblán. Ne feledje, hogy a böngésző frissítése szükséges. 

Minden további felhasználói munkamenet engedélyezett új rácsvezérlővel indul.

## <a name="known-issues"></a>Ismert problémák
Ez a szakasz az új rácsvezérlő ismert problémáinak listáját tárolja, miközben a funkció egy előzetes állapotban van.  

### <a name="open-issues"></a>Nyitott problémák

- A több oszloposként megjelenített kártyák listája most egyetlen hasábként jelenik meg.
- A csoportosított listák nem csoportként vagy külön oszlopként jelennek meg.

### <a name="fixed-as-part-of-10013"></a>10.0.13 részeként javítva

> [!NOTE]
> A program a következő adatokat jeleníti meg, hogy ennek megfelelően tervezzen. A 10.0.13-es verzió célzott kiadásaival kapcsolatban további információkat a [Szolgáltatásfrissítések elérhetősége](../../fin-ops/get-started/public-preview-releases.md) oldalon találhat.

- [KB 4563317] Képek esetében nem jelennek meg az eszközleírások.

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
- [KB 4562645] Kivétel történik, amikor a távoli kiszolgálófelügyeleti eszközök (RSAT) tesztjeinek futtatása közben megnyitják a keresést.

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
