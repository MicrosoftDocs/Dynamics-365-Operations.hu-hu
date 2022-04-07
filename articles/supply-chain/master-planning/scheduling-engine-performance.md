---
title: Az ütemezési motor teljesítményének javítása
description: Ez a témakör az ütemezési motorral és a teljesítmény javításával kapcsolatban nyújt tájékoztatást.
author: t-benebo
ms.date: 09/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19311
ms.assetid: 5ffb1486-2e08-4cdc-bd34-b47ae795ef0f
ms.search.region: Global
ms.search.industry: ''
ms.author: benebotg
ms.search.validFrom: 2020-09-03
ms.dyn365.ops.version: ''
ms.openlocfilehash: 972e566153b7423398b2ad4a4e70b264f02c40cd
ms.sourcegitcommit: ad1afc6893a8dc32d1363395666b0fe1d50e983a
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/23/2022
ms.locfileid: "8469006"
---
# <a name="improve-scheduling-engine-performance"></a>Az ütemezési motor teljesítményének javítása

[!include [banner](../includes/banner.md)]

Az erőforrás-ütemezési motor a tervezett és kiadott termelési rendelések útvonalának ütemezéséhez használható. A motort eredetileg a Dynamics AX 2012 részeként adták ki, és a megjelenése óta számos fejlesztésen ment keresztül.

A [job shop ütemezési probléma](https://en.wikipedia.org/wiki/Job_shop_scheduling) egy rendkívül összetett kombinatorikus probléma, ahol a megoldás ideje exponenciálisan nő a döntési változók számával. A vevők a termelési útvonalakat és a kapcsolódó adatokat gyakran úgy határozzák meg, hogy az ütemezési problémát okoz, amely még a legmodernebb hardveren sem oldható meg ésszerű időn belül. Ez a témakör segít megismerni az ütemezési motort, illetve azt, hogy egy adott beállítás milyen hatással lehet a teljesítményre.

Az ütemezés teljesítményének javítására vonatkozóan, az általános iránymutatások a motor által megoldandó probléma összetettségének csökkentését javasolják. Néhány főbb tényező, amely a teljesítményre hatással lehet:

- Számos művelettel rendelkező útvonalak
- Párhuzamos művelettel rendelkező útvonalak
- Egynél magasabb erőforrás-mennyiséggel rendelkező műveletek
- Számos használható erőforrással rendelkező műveletek
- Rögzített hivatkozások használata
- Véges kapacitás használata
- Az alkalmazott különböző naptárak száma
- A naptárban a működő időközök naponkénti száma
- Az útvonal teljes időtartama
- Több ütemezési motor párhuzamos futtatása

## <a name="overview-of-basic-scheduling-flow"></a>Alapvető ütemezési folyamat áttekintése

Annak megértéséhez, hogy egy adott beállítás milyen hatással lehet a teljesítményre, fontos megérteni valamit a folyamatnak a motorban, illetve az azt körülvevő X++ kódban történő működéséről.

A rendelés ütemezésének alapvető folyamata három fő lépésből áll:

- **Adatok betöltése** – itt az X++ adatmodellek feladatok és megszorítások formájába átalakítva bekerül a motor belső adatmodelljébe.
- **Ütemezés** – ez az adott modellt és megszorításokat feldolgozó és eredményt létrehozó ütemezés fő forrása. E folyamatnak során az X++ kódból a motor szükség szerint munkaidőre vonatkozó adatokat és meglévő kapacitásfoglalásokat fog kérni.
- **Adatok mentése** – a motor feladat kapacitásfoglalási időközök formájában megjelenő eredményét az X++ kód dolgozza fel a kapacitásfoglalások mentéséhez, és frissíti a feladatok/műveletek/rendelések kezdő és befejező időpontját.

## <a name="load-data-into-the-engine"></a>Adatok betöltése a motorba

Az ütemezési motor a Supply Chain Management adatbázisnál elvontabb adatmodellel is rendelkezik, mert általános motorként készült, amely különböző adatforrásokat képes kezelni. Az útvonal, a másodlagos műveletek és a futási idő fogalmát „le kell fordítani” a motor által megjelenített általános feladat és megszorítás modellre. A modell építéséhez használt logika jelentős mennyiségű üzleti logikával rendelkezik, és a forrásadatok értékétől függően eltérő. A felelős X++ osztály a `WrkCtrScheduler`, amely származtatott osztályokkal rendelkezi a tervezett termelési rendelésekhez, a kiadott termelési rendelésekhez és a projekt-előrejelzésekhez.

Például gondolja át a következő táblázatban és képen látható útvonalat, amely viszonylag egyszerűnek tűnik.

| Műv. Szám | Prioritás | Beállítási idő | Lefutási idő | Várakozási idő a művelet után | Erőforrások mennyisége | Következő |
| --- | --- | --- | --- | --- | --- | --- |
| 10 | Elsődleges | 1.00 | 2.00 | | 1 | 20 |
| 10 | Másodlagos&nbsp;1 | | | | 1 | 20 |
| 20 | Elsődleges | | 3.00 | 1.00 | 3 | 0 |

![Példaútvonal-diagram.](media/scheduling-engine-route.png "Példaútvonal-diagram")

A program ezt a motornak történő elküldésekor nyolc feladatra osztja fel, amint az a következő ábrán látható (válassza ki a képet a nagyításhoz).

[![Motorfeladatok ütemezése](media/scheduling-engine-jobs.png "Motoros munkák ütemezése.")](media/scheduling-engine-jobs-large.png)

A két feladat közötti normál kapcsolat `FinishStart`, amely azt jelenti, hogy egy feladat befejezési időpontjának meg kell előznie egy másik feladat kezdési időpontját. Mivel a beállítást ugyanannak az erőforrásnak kell elvégeznie, amely a folyamatot később végrehajtja, a kettő között `OnSameResource` megszorítások vannak. A 10 elsődleges és másodlagos műveletéhez tartozó feladatok között van `StartStart` és `FinishFinish` hivatkozás van, ami azt jelenti, hogy a feladatoknak ugyanakkor kell kezdődniük és befejeződniük, és `NotOnSameResource` megszorítások is vannak, amelyek megakadályozzák, hogy az elsődleges és a másodlagos erőforrás azonos legyen.

A 20-as művelet esetén, ahol az erőforrások mennyisége 3 értékűre van állítva, a feldolgozási feladatot három különböző feladatra osztják fel, ahol minden feladatnak pontosan egy időben kell futnia.
Ebben az esetben az útvonalcsoport úgy van beállítva, hogy a várakozási sor számára egy idő után ne kössön le kapacitást, ezért a várakozási sor után csak egyetlen feladat van.

Az ütemezési motor csak a feladatok fogalmait érti, és nem rendelkezik a műveletek fogalmával. Ez azt jelenti, hogy a műveletek ütemezése során a műveletek feladatokra is feloszthatók, bár ezek nem őrződnek meg az adatbázisban.

Minden feladathoz meg kell határozni a feladat kapacitáskövetelményét (a másodpercek száma szükséges). Az erőforrás-szükségletek meghatározásának módjától függően, minden feladatnál elküldhető az összes potenciális alkalmazható erőforrás listája, amelyeken a feladat futhat, illetve elküldhető az adott erőforrás kapacitáskövetelménye. Annak ellenére, hogy a modell létrehozásakor a program elküldi az alkalmazható erőforrások listáját, a motornak továbbra is biztosítania kell, hogy az erőforrás-hozzárendelés ténylegesen érvényes legyen a feladat teljes időtartamára.

## <a name="scheduling-engine-internals"></a>Ütemezési motor belső részei

### <a name="scheduling-engine-interface"></a>Ütemezési motor interfész

A motor belső működése legjobban a kívülről megfigyelhető funkcióinak megismerésével érthető meg. Az X++ esetében a fő felület a `WrkCtrSchedulerEngineInterface`. A következő alszakaszokban leírt módszerekkel rendelkezik.

#### <a name="general-engine"></a>Általános motor

| **Metódus** | **Cél** |
| --- | --- |
| `run` | Az összes betöltött feladat ütemezése és a hibakód visszaadása. |
| `getJobSchedulingSequenceResult` | Az ütemezési eredmény és egy adott feladat által azonosított sorozat első hibafeladatának beolvasása. |
| `validateJobCapacityReservations` | A motor által tárolt összes feladat kapacitásfoglalásainak ellenőrzése. |
| `setReservationsTimeStamp` | Időbélyegző küldése a motornak, a motor gyorsítótárában lévő ütemezett feladatokhoz tartozó összes új kapacitásfoglalásra beállítva. |
| `addPropertyToGroupAggregation` | Tulajdonság-előtag hozzáadása a kapacitás összesítése során használt tulajdonságkészlethez. |
| `addResource` | Erőforrás hozzáadása az ütemezési motor erőforráskészletéhez. |
| `addResourceGroup` | Erőforráscsoport hozzáadása az ütemezési motor erőforráscsoport-készletéhez. |
| `addResourceGroupMembership` | Erőforrás hozzáadása tagként egy erőforráscsoporthoz. |
| `addOptimizationGoal` | Ütemezés-optimalizálási cél hozzáadása (időtartam vagy prioritás). |

#### <a name="individual-jobs"></a>Egyéni feladatok

| **Metódus** | **Cél** |
| --- | --- |
| `addJobInfo` | Feladat- adatrekord hozzáadása, amely ütemezendő feladatról értesíti a motort. |
| `addConstraintJobEndsAt` | Megszorítás hozzáadása, amelyet a feladatnak egy megadott dátumon és időpontban kell lezárnia. |
| `addConstraintJobStartsAt` | Megszorítás hozzáadása, amelyet a feladatnak egy megadott dátumon és időpontban kell elkezdenie. |
| `addConstraintMaxJobDays` | Megszorítás meghatározása, amelyet egy feladat egy megadott maximális számú napra terjeszthet ki. |
| `addConstraintResourceRequirement` | Megszorítás hozzáadása, amelyet a feladatnak egy adott erőforrásra kell ütemeznie. |
| `addJobBindPriority` | Feladathoz tartozó kötési prioritás hozzáadása egy (feladat, megszorítási szint) pár számára. A magasabb prioritási érték azt jelenti, hogy a feladat változói korábban kötve lesznek. A feladat feldolgozása az azonos sorban alacsonyabb prioritási értékkel rendelkező feladatok feldolgozása előtt történik. |
| `addJobCapacity` | Kapacitásterhelési adatok hozzáadása egy feladathoz (például a feladat szükséges futásideje), függetlenül attól, hogy a feladat mely erőforráson fut. |
| `addJobResourceCapacity` | Erőforrás hozzáadása a feladatok elvégzéséhez használható erőforrások készletéhez, továbbá az adott erőforráson történő futtatás esetén szükséges kapacitás meghatározása. |
| `addJobGoal` | Feladatcéladatok hozzáadása a meghatározott megszorítási szinthez (legkorábbi befejezési vagy legkésőbbi kezdési idő). |
| `addJobResourcePriority` | Prioritás hozzáadása abban az esetben történő felhasználásra, ha erőforrásra feladat van ütemezve. |
| `addJobResourceRuntime` | Olyan munkaidő meghatározása, amely attól az erőforrástól függ, amelyre a feladat ütemezése történik. |
| `addJobRuntime` | Olyan munkaidő meghatározása, amely független attól az erőforrástól, amelyre a feladat ütemezése történik. |
| `scheduleJobOnResourceGroup` | Feladat megjelölése ütemezésre az erőforráscsoport szintjén. |
| `setJobResourcePreemptionAllowed` | Annak beállítása, hogy a megelőlegezés engedélyezett-e egy erőforráson (ha a motor nem folytonos kapacitáshelyekre ütemezheti a feladatot). |
| `setRequiredNumberOfResources` | A feladat ütemezéséhez szükséges erőforrások számának megadása (csak műveletek ütemezéséhez). |

#### <a name="constraints-between-jobs"></a>Feladatok közötti megszorítások

| **Metódus** | **Cél** |
| --- | --- |
| `addJobLink` | Hivatkozás hozzáadása (például befejezés\>kezdés) két feladat között. |
| `addConstraintEndsDelayed` | Annak a megszorításnak a meghatározása, amelyet a feladat csak egy másik feladat befejezése és némi késedelmi idő után zárhat le. |
| `addConstraintJobListWorkingTimeIntersect` | Megszorítás hozzáadása, amely szerint a feladatokhoz lefoglalt kapacitáshelyeknek a feladatokhoz használt két erőforráshoz tartozó, átfedő munkaidőkbe kell esnie. |
| `addConstraintJobOverlap` | Megszorítás hozzáadása, amely meghatározza a feladatok sorrendbe állításának módját, amikor egy cikk adott mennyisége két erőforrás között áthelyezhető, miközben az első erőforrás még nem fejezte be a feldolgozást, így a második erőforrás megkezdheti a feldolgozást. |
| `addConstraintNotOnSameResource` | Megszorítás hozzáadása, amely szerint két feladat nem ütemezhető ugyanarra az erőforrásra. |
| `addConstraintOnSameResource` | Megszorítás hozzáadása, amely szerint két feladat ugyanarra az erőforrásra ütemezendő. |
| `addJobSameReservations` | Megszorítás hozzáadása, amely szerint egy feladatnak ugyanazokhoz az időhelyekhez kell kapacitásfoglalásokkal rendelkeznie, mint az elsődleges feladatnak. |
| `setPrimaryParallelJob` | Tájékoztatás arról, hogy párhuzamos feladatkészletben melyik feladat az elsődleges feladat. |

### <a name="solver"></a>Feloldó

Maga a motor alapvetően egy specializált megszorítás-feloldó, egyedi heurisztikával kiegészítve. A feloldó a következő két fő elemen alapul: változók és megszorítások.

#### <a name="variable"></a>Változó

A változók a lehetséges értékek tartományát jelentik. Az ütemezési motor kétféle változóval rendelkezik:

- **DateTime változó** – minden dátumot és időpontot tartalmazó tartománnyal rendelkezik, és a tartomány a változó alsó és felső időkorlátjának egymáshoz közelítésével korlátozható.
- **Erőforrás változó** – az alkalmazható erőforrások tartományával rendelkezik, és a tartomány az erőforrásoknak a listából való eltávolításával korlátozható.

#### <a name="constraint"></a>Megszorítás

A megszorítás a változókra a tartományaik korlátozásával fejti ki hatását, de függ is a változóktól, így akkor aktiválódik, ha a változók módosulnak. A „megszorítás-propagálás” folyamata az, amikor egy megszorítás végrehajtja a fő funkcióját, és siker esetén jelentést küld a fő logikai rendszernek.

Egy változó akkor tekinthető kötöttnek, ha tovább már nem korlátozható, ami a DateTime változó esetében azt jelenti, hogy a felső és az alsó korlát azonos, az Erőforrás változó esetében pedig azt, hogy utóbbi csak egyetlen alkalmazható erőforrással rendelkezik. Ha minden változó kötött, akkor megoldást talált a program.

### <a name="constraint-levels"></a>Megszorítási szintek

Ha az ütemezés végrehajtása az anyagszükséglet-tervezés (MRP) fedezeti fázis részeként történik, a rendelések a szükséglet dátumától visszafelé lesznek ütemezve. Mindazonáltal, ha nem található olyan ütemezés, amely a mai napon vagy később kezdődik, és a szükséglet dátuma előtt ér véget, akkor az ütemezési irány a mai napról előrefelé fog változni.

Ezt a fő üzleti szabályt a megszorítások szintekbe szervezésével kezeli a program. Ha a rendszer a legmagasabb szintű megszorítások használatakor nem talál megoldást, akkor az adott szint összes megszorítását elveti, és az alacsonyabb szinttel próbálkozik. A gyakorlatban ez azt jelenti, hogy visszafelé ütemezésnél a modell tartalmazni fog egy 1. szintet a legkésőbbi kezdési idejű feladatcélokkal, maximális befejezési idő (a szükségleti dátum) megszorítással, illetve egy 0. szintet a legkorábbi kezdési idejű feladatcélokkal, és minimális kezdési idő (a mai nap) megszorítással.

### <a name="algorithm"></a>Algoritmus

A motor algoritmusának fő lépései a következők:

1. A különállóan megoldható sorozatok (munkaláncok) megkeresése.
1. Kísérlet a legnagyobb megszorítási szinthez tartozó sor kezdeti megoldásának megkeresésére.
    1. A feladatok feladatcélok és prioritások alapján történő rendezése, ami révén megtalálható a kezdő feladat.
    1. A feladatok ciklusba állítása a következő sorrendben:
        1. Az összes propagálandó megszorítás megkeresése és a propagálás futtatása.
        1. Ha a feladathoz tartozó összes változó kötött, akkor megvan az adott feladat megoldása.
        1. Ha az egyik változó nem köthető a megszorítások megszegése nélkül, akkor állítsa vissza a változó kötését, próbálkozzon egy másik értékkel a tartományban (erőforrás-változó esetében), majd futtassa újra a megszorítások propagálását.
1. Ha nem található megoldás, akkor az aktuális megszorítási szint összes megszorítását eltávolításra, a megszorítási szint alacsonyabbra kerül (ha van alacsonyabb szint), és a rendszer az új megszorításkészlettel újra megpróbál megoldást keresni.
1. Ha van megvalósítható megoldás, akkor elindul az optimalizálási fázis, amely jobb megoldást próbál találni mindaddig, amíg el nem éri az optimalizálási időtúllépést vagy ki nem merül az összes erőforrás-kombináció.

A megszorításmegoldó nem ismeri az ütemezési algoritmus jellemzőit. A „varázslat” kulcsa a különféle megszorítások meghatározásában és kombinációjában rejlik.

### <a name="determining-working-times"></a>Munkaidők meghatározása

A motor (belső) megszorításainak nagy része az erőforrások munkaidejét és kapacitását vezérli. A feladat lényegében az erőforrás munkaidőhelyeinek adott pontról adott irányban történő eltolása és kellő hosszúságú intervallum keresése, amelyben a feladatokhoz szükséges kapacitás (idő) elfér.

Ehhez a motornak ismernie kell az erőforrás munkaidőit. A fő modell adataival szemben a munkaidő *lustán van betöltve*, ami azt jelenti, hogy szükség szerint töltődnek be a motorba. E megközelítés oka, hogy a Supply Chain Management rendszerben a naptárakhoz tartozó munkaidők gyakran hosszú ideig megtalálhatók, és jellemzően számos naptár létezik, így az adatok túl nagyok az előzetes betöltéshez.

A naptárinformációkat a motor darabokban, az X++ `WrkCtrSchedulingInteropDataProvider.getWorkingTimes` osztály mód meghívásával kéri le. A kérelem egy adott naptári azonosítóra, adott időintervallumban vonatkozik. A Supply Chain Management kiszolgáló-gyorsítótárának állapotától függően, a kérelmek mindegyike több adatbázis-hívásba is bekerülhet, ami hosszú időt igényel (a tiszta számítási időhöz képest). Ha a naptár nagyon bonyolult munkaidő-meghatározásokat tartalmaz sok napi munkaidő-intervallummal, az szintén megnöveli a betöltéshez szükséges időt.

Ha a munkaidő-adatok betöltődnek az ütemezési motorba, akkor megőrződnek az adott naptár belső gyorsítótárában. Ez azt jelenti, hogy ha bármely más feladat vagy erőforrás ugyanazt a naptárt használja, akkor az újabb keresések gyorsan elvégezhetők a memóriából. A rossz teljesítmény egyik gyakori oka, ha minden erőforráshoz külön naptári azonosító van használatban, mert így minden naptárhoz adatokat kell kérni, még akkor is, ha a naptárak tartalma esetleg azonos.

### <a name="finite-capacity"></a>Véges kapacitás

Véges kapacitás használata esetén a rendszer a naptárból származó munkaidőhelyeket a meglévő kapacitásfoglalások alapján felosztja és csökkenti. Ezeket a foglalásokat a program ugyanazon a `WrkCtrSchedulingInteropDataProvider` osztályon keresztül olvassa be, mint a naptárak, de a `getCapacityReservations` mód használatával. Az alaptervezés során történő ütemezéskor a rendszer figyelembe veszi az adott alapterv foglalásait, és ha az **Alaptervezés paraméterei** lapon engedélyezve van, akkor figyelembe veszi a megerősített termelési rendelésekből származó foglalásokat is. Hasonlóképpen a termelési rendelések ütemezésekor lehetőség van a meglévő tervezett rendelésekből származó foglalások belefoglalására is, bár ez nem olyan gyakori, mint a másik eljárás.

Véges kapacitás használata esetén az ütemezés több okból is hosszabb időt vesz igénybe:

- A kapacitási adatoknak az adatbázisból való beolvasása lassú művelet, és a kapacitási adatok kiszolgálóoldali gyorsítótárazása általában nem olyan jó, mint a munkaidők esetében, mivel ezek nincsenek úgy megosztva az erőforrások között, mint a naptárak általában.
- Az eltolandó munkaidőhelyek száma a felosztások miatt egyre nagyobb lesz, és a hosszabb időszakra eső helyeket általában ki kell vizsgálni, mielőtt a megoldás megtalálható.
- Az ütemezés befejezése után ellenőrizni kell, vannak-e ütköző foglalások (részletek az „Ütemezési motorok párhuzamos futtatása” című szakaszban).

### <a name="examining-the-resource-combinations"></a>Az erőforrás-kombinációk vizsgálata

Ha a feladatsorozat csak a szokásos `FinishStart` hivatkozásokat tartalmazza, ami azt jelenti, hogy elágazások nélküli egyszerű láncot képez, akkor optimális eredmény (egy rendelésből, nem több rendelést átfogóan) az első feladat legjobb megoldásának megtalálásával, majd a következő feladat legjobb megoldásának megkeresésére irányuló folytatással érhető el. A feladat legjobb megoldása azt jelenti, hogy a rendszer megkeresi azt az erőforrást, amely hozzájuthat a feladatcélhoz legközelebb eső kezdési és befejezési dátumhoz (előre ütemezésben ez azt jelenti, hogy a lehető leghamarabb megszerzi a feladat befejezési dátumát), miközben továbbra is figyelembe veszi a megszorításokat.

Párhuzamos feladatok esetén a megoldás megkeresése az erőforrások különböző kombinációinak vizsgálatát is megában foglalhatja. A lehetséges erőforrás-kombinációk száma a kapcsolódó párhuzamos feladatokhoz szükséges alkalmazható erőforrások számából származik. Különösen akkor, ha egy rendelés ütemezése egy igénylési időponttól visszafelé történik, hosszabb ideig is eltarthat, amíg a rendszer felismeri, hogy a problémára nincs megoldás, amely a párhuzamos feladatokat a mai dátum elé illesztené. Ilyenkor a rendszernek az összes kombinációt ellenőriznie kell, mert lehetnek nagyobb hatékonysággal vagy más naptárral rendelkező erőforrások is, amelyek eredményt adhatnak. Ez azt jelenti, hogy ha nem állítottak be időtúllépési korlátot, akkor a folyamat az előrelépés irányába történő váltás előtt hosszú ideig fog futni.

Ez a kombinatorikus logika azt is jelenti, hogy több alkalmazható erőforrás hozzáadása lassíthatja a motor futását. Ha párhuzamos műveletek és végtelen kapacitással rendelkező ütemezés esetén teljesítményproblémák lépnek, akkor ezek részben úgy is megoldhatók, hogy az útvonal-tervező eldönti, mely erőforrást kell használni, majd az erőforrást közvetlenül hozzárendeli a művelethez (mert a motor a legtöbb esetben végül mindig ugyanazt az erőforrást választja, így a végeredmény ugyanaz lesz).

### <a name="hard-links"></a>Rögzített hivatkozások

Két feladat közötti hivatkozás rögzítettre történő beállítása biztosítja, hogy az egyik feladat befejezése és a következő kezdése között nincs időbeli különbség. Ez nagyon hasznos lehet olyan helyzetekben, mint például amikor a fémet egyik feladatban felmelegítik, majd a következő feladatban feldolgozzák, ahol nem kívánatos, hogy a fém közben lehűljön.

Normál kötetlen hivatkozásokkal és előre ütemezéssel, ha az útvonal elágazások nélküli egyszerű láncot képez, eredmény azáltal érhető el, ha a rendszer megtalálja a megoldást az első feladatra, amely megfelel saját megszorításainak, majd továbbhalad a befejezési időt az előző feladatból a következő feladatra toló láncon át. Ha a jelenlegi feladat nem talál kapacitást, akkor a kezdési idő tovább kitolódik anélkül, hogy a feladatok között esetlegesen létrejövő hézagok bármilyen következménnyel járnának a korábbi feladatokra. Viszont ha rögzített hivatkozások (különösen a véges kapacitáshoz kapcsolódók) szerepelnek azonos helyzetben, akkor az, hogy a láncban egy feladat később nem talál kapacitást, azt fogja jelenteni, hogy minden korábbi ütemezett feladatot egyenként kell „húzkodni”, és így többször újra kell ütemezni. Különösen olyan esetekben, amikor több erőforrás nagy terhelést kap, a rögzített hivatkozások láncreakciót okozhatnak, amelyben a feladatok hatással vannak egymásra, és számos ismétlést kell végrehajtani ahhoz, hogy az eredmény megvalósítható ütemezést adjon.

## <a name="running-scheduling-engines-in-parallel"></a>Ütemezési motorok párhuzamos futtatása

Ha az ütemezés elvégzése egy alaptervezés futtatásának részeként történik, amelyhez segítőket is használnak, az alaptervezést segítő szálak mindegyike felveheti a termelési rendelések ütemezésének feladatait is. Ez azt jelenti, hogy egyidejűleg több ütemezési motor is futhat. Bár a többszálú működés általában jelentősen előnyös hatást tesz a teljesítményre, de az ütemezés vonatkozásában van néhány funkcionális hátrány is.

Az MRP modulban az adott anyagjegyzék- (BOM-) szint összes termelési rendelése be van ütemezve az igénylési dátum szerinti sorrendben, ami azt jelenti, hogy a legkorábbi igénylési dátummal rendelkező rendeléseket kell először ütemezni, és így ezeknek van a legnagyobb esélye az elérhető erőforrás-kapacitás megszerzésére. Mindazonáltal, ha a nem ütemezett rendelések listájából több motort választ, a sorozat már nem biztosítható, mert az egyik gyorsabban végezhet a másiknál.

Ha az ütemezés véges kapacitást használ, és ha több motorpéldány próbál meg ütemezni olyan rendeléseket, amelyek potenciálisan ugyanazokat az erőforrásokat ugyanabban az intervallumban használják, akkor versenyhelyzet is előállhat. Az ilyen versenyfeltételek szám az alaptervek előzményei lapon, az **Ütemezési ütközések** mezőben van rögzítve. Az ütközésfeloldás logikája a következő:

- Rendelés ütemezése (zárolás nélkül) és kapacitásfoglalás megszerzése.
- Zárolás.
- Annak ellenőrzése, hogy az időtartományban van-e újabb kapacitásfoglalás az ütemezett erőforrásokhoz.
  - Ha nincs, akkor a kapacitás beírható, és a zárolás feloldható.
  - Ha van, akkor fel kell oldani a zárolást, majd az elejétől kezdve újraütemezni a rendelést.

Tehát több motorpéldánnyal történő ütemezés esetén az eredmény nem teljesen determinisztikus, mert az egyes szálak pontos időzítésétől függ.

## <a name="operation-scheduling-performance"></a>Műveletütemezés teljesítménye

Noha a műveletütemezés a motor szempontjából elnagyolt kapacitástervezésként is ismert, ez véges kapacitás használata esetén, nehezebben megoldható problémát is jelenthet, mert a megvalósíthatóság megállapításához több adat szükséges.

Egy erőforráscsoport kapacitása attól függ, hogy mely és hány erőforrás tagja az erőforráscsoportnak. Egy erőforráscsoport önmagában nem rendelkezik kapacitással &mdash; kapacitása csak akkor lesz, ha vannak erőforrástagjai a csoportnak. Mivel az erőforráscsoport-tagság idővel változhat, a kapacitást naponta kell értékelni.

Műveletütemezésekor az erőforráscsoport naptára az egyes műveletek kezdő és befejező időpontjának meghatározására szolgál. Ez azt jelenti, hogy az erőforráscsoport naptára korlátozni fogja, hogy egy adott napon egy művelethez egy erőforráscsoportban mennyi ideig lehet műveleteket ütemezni. A megadott erőforrások naptárával szemben a naptár hatékonysági adatait az erőforráscsoport esetében a rendszer figyelmen kívül hagyja, mivel csak nyitási időt, és nem tényleges kapacitást jelöl meg.

Ha például egy erőforráscsoport munkaideje egy adott napon 8:00 és 16:00 között van, akkor egy művelet nem terhelheti jobban az erőforráscsoportot, mint ami 8 órába belefér, függetlenül attól, hogy az erőforráscsoport az adott napon mennyi szabad összkapacitással rendelkezik. A rendelkezésre álló kapacitás azonban tovább korlátozhatja a terhelést.

A feladatütemezésből adott napon az erőforráscsoport összes erőforrására háruló terhelést az erőforráscsoport azonos napi elérhető kapacitásának kiszámításánál figyelembe veszi a rendszer. Minden dátum esetén a számítás a következő:

*Elérhető erőforráscsoport-kapacitás = a csoport erőforrásainak kapacitása a naptáruk alapján &ndash; a csoport erőforrásainak ütemezett munkaterhelése &ndash; a csoport erőforrásainak ütemezett műveleti terhelése &ndash; az erőforráscsoport ütemezett műveleti terhelése*

Az útvonal-művelet **Erőforrásigények** lapján az erőforrásigények egy adott erőforrás használatával (amely esetben a művelet ütemezése az adott erőforrás használatával történik), egy erőforráscsoport, egy erőforrástípus, illetve egy vagy több képesség, szakértelem, tanfolyam vagy tanúsítvány szerint adhatók meg. Bár az összes ilyen beállítás használatával nagy rugalmasság érhető el az útvonaltervezésben, ez a motor számára egyben az ütemezést is bonyolítja, mert a kapacitást a „tulajdonság” (a motorban a képességek, szakértelmek stb. esetében használt absztrakt név) alapján kell elszámolni.

Egy képesség esetén az erőforráscsoport kapacitása az erőforráscsoportban levő összes olyan erőforrás összkapacitása, amely rendelkezik a szóban forgó képességgel. Ha egy csoport erőforrásai rendelkeznek képességgel, akkor azt a rendszer figyelembe veszi, függetlenül attól, hogy milyen szintű kapacitás szükséges.

Műveletütemezés során a rendszer csökkenti az erőforráscsoport számára egy bizonyos képességhez rendelkezésre álló kapacitást, ha a betöltése olyan művelettel történik, amelyhez a szóban forgó képesség szükséges. Ha a művelet egynél több képességet igényel, akkor a rendszer az összes szükséges képesség esetén csökkenti a kapacitást.

Minden dátum esetén a szükséges számítás a következő:

*Egy képességhez rendelkezésre álló kapacitás = a képesség kapacitása &ndash; az illető képességgel rendelkező erőforrások ütemezett munkaterhelése, ideértve az erőforráscsoportot &ndash; az erőforráscsoportba tartozó, illető képességgel rendelkező erőforrások ütemezett műveleti terhelése &ndash; az erőforráscsoport ütemezett, az illető képességet igénylő műveleti terhelése*

Ez azt jelenti, hogy ha egy adott erőforráson terhelés van, akkor a rendszer a terhelést figyelembe veszi az erőforráscsoport képességek szerinti elérhető kapacitásának kiszámításában, mert egy adott erőforrás terhelése csökkenti annak hozzájárulását az erőforráscsoport képesség szerinti kapacitásához, függetlenül attól, hogy az adott erőforrás terhelése az adott tulajdonságra vonatkozik-e. Ha az erőforráscsoport szintjén van terhelés, akkor a rendszer csak akkor veszi figyelembe az erőforráscsoport képesség szerinti rendelkezésre álló kapacitás kiszámításában, ha a terhelés olyan műveletből származik, amelyhez az adott képesség szükséges.

A fenti logika bonyolult, mert minden „tulajdonság”-típus esetén ugyanaz, így a véges kapacitással történő műveletütemezés használata jelentős mennyiségű adatbetöltést igényel.

## <a name="viewing-scheduling-engine-input-and-output"></a>Ütemezési motor bemenetének és kimenetének megtekintése

Az ütemezési folyamat be- és kimenetének egyes részleteihez engedélyezze a naplózást a **Szervezeti adminisztráció \> Beállítás \> Ütemezés \> Ütemezés nyomkövetési vezérlőpult** menüútvonalon keresztül.

Ezen az oldalon először a Művelet panelen válassza a **Naplózás engedélyezése** lehetőséget. Majd futtassa az ütemezést a termelési rendeléshez. Ha elkészült, térjen vissza az **Ütemezés nyomkövetési vezérlőpult** oldalra, majd a Művelet panelen válassza **Naplózás letiltása** lehetőséget. Frissítse az oldalt, és a rácsban egy új sor fog megjelenni. Jelölje ki az új sort, majd a Művelet panelen válassza a **Letöltés** lehetőséget. Ez egy .zip tömörített mappát eredményez, amely a következő fájlokat tartalmazza:

- **Log. txt** – ez a naplófájl, amely leírja a motor által végrehajtott lépéseket. Nagyon bonyolult, és kicsit terjengősnek is tűnhet, de a teljesítményproblémák megoldása érdekében végzett útvonal-beállítási kísérletek részeként felhasználva, elsőként a legelső és a legutolsó sor közötti időkülönbséget érdemes megfigyelni, mert ez adja meg az ütemezésre fordított pontos időt.
- **XmlModel.xml** – ez tartalmazza az X++ rendszerbe épített modellt, amelyen a motor működik. A fájlban használt `JobId` korrelál a feladatokat (`ReqRouteJob` vagy `ProdRouteJob`) tartalmazó táblából származó `RecId` elemmel. Ebben a fájlban jellemzően azt kell keresni, hogy elvárások szerintiek-e a `ConstraintJobStartsAt` és a `ConstraintJobEndsAt` elemekben megadott dátumok, hogy megfelelő-e a `JobGoal` tulajdonság beállítása, illetve hogy a feladatok kapcsolódnak-e egymáshoz a `JobLink` megszorításokon keresztül.
- **XmlSlots.xml** – ez tartalmazza a motor által kért összes munkaidőt és kapacitásfoglalást. A naptári munkaidőket és a foglalásokat a motor csak azon időszakok esetében kéri, amikor megpróbálja elhelyezni a feladatokat (és még egy külön puffert), így ha a fájl nagyon távoli jövőbeli időpontokat tartalmaz, az beállítással kapcsolatos problémát jelezhet. A `ResourceProperty` csomópontok minden erőforrás esetén megjelenítik, hogy milyen időtartamra mely erőforráscsoporthoz és mely képességekhez van társítva.
- **Result.xml** – ez az ütemezés futtatásának eredményét tartalmazza.

Vegye figyelembe, hogy a nyomkövetési funkció jelentős pluszteljesítményt adhat hozzá, ezért csak az adott rendelések ütemezésének vizsgálatára, ellenőrzés mellett használható. Ha egy alaptervezés futtatásakor aktiválják, akkor gyorsan eléri a méretkorlátját, és leállhat.

## <a name="troubleshooting-performance"></a>Teljesítmény-hibaelhárítás

Amint az eddigi fejezetek alapján megérthető, az ütemezési motor beállítása és használata tartogat néhány buktatót, amik teljesítményproblémákhoz vezethetnek. Az ilyen problémák elhárításához a következő ellenőrző lista használható. Fontos, hogy az összes pontot figyelembe kell venni, mivel leggyakrabban több tényező kombinációja vezet problémákhoz.

### <a name="performing-scheduling-as-part-of-mrp-when-it-is-not-needed"></a>Ütemezés az MRP részeként, amikor nem szükséges.

Annak ellenére, hogy a termelésellenőrzési célokra (például költségszámításra és jelentésre) útvonalakat használnak, előfordulhat, hogy nem kell figyelembe venni azokat az MRP során. Bizonyos esetekben a tervezéshez elegendő a cikkhez megadott normál termelési átfutási idő. Az útvonal-ütemezés kikapcsolásához állítsa nullára a kapacitás időkorlátját. Ha ütemezést kell végezni, akkor a kapacitás időkorlátját gondosan be kell állítani, mert előfordulhat, hogy az MRP lefedettségi időkorlátjának teljes terjedelméhez nem szükséges útvonalakat figyelembe venni.

Ne feledje, hogy ha a rendelés ütemezése nem az MRP során történik, akkor helyette a tervezett rendelés megerősítésekor kell ütemezni. Ez azt jelenti, hogy a megerősítési folyamat hosszabb időt vesz igénybe, tehát attól függően, hogy hány javasolt tervezett rendelés kap megerősítést, az MRP során jelentkező teljesítménytöbblet a megerősítéskor elveszhet.

### <a name="route-with-unnecessary-operations"></a>Útvonal felesleges műveletekkel

Az útvonal megtervezésekor csábítónak tűnik a valós világot pontosan a termelés által végrehajtott összes lépéssel modellezni. Bár ez bizonyos esetekben hasznos lehet, a teljesítmény számára nem jó, mert a modell, amelyen a motornak működnie kell, nagyobb lesz (feladatok és megszorítások vonatkozásában egyaránt), és a feladatok és kapacitásfoglalások beszúrása és frissítése több SQL-utasítás végrehajtásával fog megvalósulni. Ezenkívül a feladatoknál a folyamatban lévő állapotok jelentésének kötelezettségének hatása alsóbb szinteken is érvényesül, am automatikus feladásokkal mérsékelhető. Ha az adatokat nem használják fel semmihez, az felesleges terhelést okoz.

Javasoljuk, hogy csak az ütemezéshez és/vagy a költségszámítási célokhoz feltétlenül szükséges műveleteket hozzon létre (amelyek általában a szűk keresztmetszetű erőforrások). Másik megoldásként a különböző műveletek egy nagyobb műveletbe csoportosíthatók, amely a folyamatnak egy nagyobb részét képviseli.

### <a name="many-applicable-resources-for-an-operation"></a>Sok alkalmas erőforrás egy művelethez

A művelethez alkalmazható erőforrások számát a műveleti kapcsolathoz megadott erőforrásigények határozzák meg. Az igény vonatkozhat egy meghatározott (egyéni) erőforrásra, vagy alapulhat egy erőforrás erőforráscsoport-tagságán vagy képességén is.

Ha az ütemezés nem véges kapacitás használatával történik, és az összes alkalmazható erőforrás azonos naptárral és hatékonysággal rendelkezik, akkor az ütemezési motor egy művelethez mindig ugyanazt az erőforrást választja egy művelethez, de csak azután, hogy az összes alkalmas erőforrást megpróbálja ellenőrizni, hogy „jobb”-e a többinél. Ebben az esetben az ütemezési terhelés csupán azzal is jelentősen csökkenthető, ha a művelethez az útvonal-tervezési idő alatt mindig egy meghatározott erőforrást rendelnek hozzá.

### <a name="route-with-parallel-operations"></a>Párhuzamos műveletekkel rendelkező útvonal

Míg a párhuzamos (elsődleges/másodlagos) műveletek hatékony eszközt jelentenek olyan helyzetek modellezésénél, amelyekben egy adott feladat elvégzése gépet és kezelőt is igényel, a megközelítés számos teljesítménnyel kapcsolatos probléma forrása is. Ha egy meghatározott egyedi erőforráshoz tartozó igény az elsődleges és a másodlagos művelethez is hozzá van rendelve, akkor ez rendszerint nem jelent problémát. Ha viszont minden művelethez számos lehetséges erőforrás létezik, akkor ez az ütemezéshez jelentős számítási bonyolultságot ad.

A párhuzamos műveletek alternatívájaként a párok „virtuális” erőforrásokként modellezhetők (amelyek ezután a csoportot a műveletekhez mindig összetartozóként képviselik), vagy egyszerűen mellőzhető a szűk keresztmetszetet nem képező műveletek valamelyikének modellezése.

### <a name="route-with-quantity-of-resources-higher-than-1"></a>Egynél magasabb erőforrás-mennyiséggel rendelkező útvonal

Ha egy művelethez szükséges erőforrások mennyisége egynél magasabbra van beállítva, akkor az ténylegesen ugyanaz lesz, mint elsődleges/másodlagos műveletek használata esetén, mert a motorhoz több párhuzamos feladatot küldenek. Ebben az esetben azonban a program nem használ specifikus erőforrás-hozzárendeléseket, mert az egynél nagyobb mennyiség a művelethez egynél több erőforrás alkalmazhatóságát igényli.

### <a name="excessive-use-of-finite-capacity"></a>Véges kapacitás túlzott használata

A véges kapacitás használatához a motornak be kell töltenie a kapacitás adatait egy adatbázisból, és számítási többlet léphet fel, mert nehezebb megoldást találni, különösen olyan környezetekben, ahol az erőforrások foglalása a maximális kapacitás közelében történik. Ennek eredményeképpen fontos, annak gondos mérlegelése, hogy az erőforrásoknak valóban véges kapacitásra van-e szüksége, vagy hogy túlfoglalhatók-e. Mivel a véges kapacitású erőforrások között különbség lehet abban, hogy túlfoglalásuk mellőzése mennyire fontos, az erőforrásra a szűk keresztmetszet használatát javasoljuk, külön értékkel kombinálva a terv „Szűk keresztmetszetű erőforrások kapacitási időkorlátja” című részében. A szűk keresztmetszet koncepció használata lehetővé teheti, hogy az általános véges kapacitás időkorlátja is csökkenthető legyen.

### <a name="setting-hard-links"></a>Rögzített hivatkozások beállítása

Az útvonal normál hivatkozásának típusa *lágy*, ami azt jelenti, hogy az egyik művelet befejező ideje és a következő kezdete között időeltérés megengedett. Ennek engedélyezése azzal a kellemetlen hatással járhat, hogy ha az egyik művelethez anyagok vagy kapacitások igen hosszú ideig nem állnak rendelkezésre, akkor a termelés hosszabb ideig tétlen lehet, ami a folyamatban lévő munka esetleges megnövekedését jelenti. Ez rögzített hivatkozásokkal nem fog megtörténni, mert a befejezésnek és a kezdésnek tökéletesen kell illeszkednie. A rögzített hivatkozások beállítása azonban fokozza az ütemezési nehézségeket, mert a műveletek két erőforrása esetében a munkaidő és a kapacitás metszéspontját kell kiszámítani. Ha párhuzamos műveletek is vannak, akkor ez jelentős számítási időt ad hozzá. Ha a két művelet erőforrásainak különböző naptárai vannak, amelyek egyáltalán nem fedik egymást, akkor a probléma megoldhatatlan.

Javasoljuk, hogy rögzített hivatkozásokat csak feltétlenül szükséges esetben használja, és gondosan mérlegelje, hogy az útvonal minden műveletéhez szükségesek-e.

A folyamatban lévő munka rögzített hivatkozások alkalmazása nélküli csökkentésére jó módszer lehet a rendelést kétszer történő ütemezése, a második menetnél ellenkező irányra váltva. Ha az első ütemezés a szállítási dátumtól visszafelé történik, akkor a másodikat az ütemezett kezdő dátumtól előrefelé kell elvégezni. Ennek hatására a feladatok tömörítése a lehető legnagyobb mértékű lesz, így a folyamatban lévő munka minimalizálható.

### <a name="separate-calendar-for-each-resource"></a>Külön naptár minden erőforráshoz

Az ütemezési motor egyik fő adatforrása a naptári információ, amelynek az adatbázisból történő betöltése költséges lehet. Mivel a naptárak létrehozása sablonok alapján történik, csábító gondolat lenne minden erőforráshoz külön naptárt létrehozni, majd módosítani a naptárban szereplő adatokat, ha az erőforrás leáll vagy egyéb problémái keletkeznek. Ez a művelet azonban súlyosan korlátozza a motor naptáradatokat gyorsítótárazó képességét, mert minden egyes erőforráshoz új adatokat kell kérnie, és ez a teljesítménnyel kapcsolatos problémák nagy forrása lehet. Ehelyett a naptáraknak az erőforrások közötti lehető legnagyobb mértékű újrahasznosítását, majd a leállási változásoknak egy másik naptár-azonosító adott időszakhoz hozzárendelésével történő szabályozását javasoljuk.

### <a name="high-number-of-working-time-slots-per-calendar-day"></a>Munkaidőhelyek magas száma naptári naponként

Mivel a motor az időhelyek kapacitásra történő egyenkénti vizsgálatával működik, a napi az időhelyek naptári naponkénti számának minimalizálása előnyt jelent. Ez például megvalósítható annak mérlegelésével, hogy fontos-e a létrejövő ütemezésnek tükröznie, hogy a dolgozók óránként 5 perc szünetet tartanak.

### <a name="large-or-none-scheduling-timeouts"></a>Nagy (vagy nincs) ütemezési időtúllépés

Az ütemezési motor teljesítménye az **Ütemezési paraméterek** oldalon található paraméterek használatával optimalizálható. Az **Ütemezési időtúllépés engedélyezve van** és az **Ütemezés-optimalizálási időtúllépés engedélyezve van** beállításokat mindig **Igen** értékre kell állítani. Ha **Nem** értékre van állítva, akkor az ütemezés potenciálisan a végtelenségig futhat, ha egy számos beállítással rendelkező megvalósíthatatlan útvonalat hoztak létre.

A **Maximális ütemezési idő sorozatonként** értéke határozza meg, hogy legfeljebb hány másodperc fordítható egy adott sorozathoz tartozó megoldás megkeresésére (a legtöbb esetben egy sorozat egyetlen rendelésnek felel meg). Az itt használandó érték nagymértékben függ az útvonal és a beállítások, mint a véges kapacitás bonyolultságától, de 30 másodperc körüli maximális érték jó kiindulási pont.

Az **Optimalizálási próbálkozások időtúllépése** határozza meg, hogy legfeljebb hány másodperc fordítható az eredetileg találtnál jobb megoldás keresésére. Ez csak azokat az útvonalakat befolyásolja, amelyek párhuzamos műveleteket alkalmaznak, mivel ezek különböző kombinációk tesztelését teszik szükségessé.

> [!NOTE]
> Az időtúllépésekhez beállított értékek a kiadott termelési rendeléseknek és a tervezett rendeléseknek az MRP részeként történő ütemezésére egyaránt vonatkozni fognak. Ennek eredményeként, nagyon magas értékek beállítása, sok tervezett termelési rendelést tartalmazó tervre történő futtatás esetén jelentősen növeli az MRP futásidejét.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]