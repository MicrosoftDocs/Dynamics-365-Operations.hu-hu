---
title: "Az alvállalkozói tevékenység alapú"
description: "Ez a témakör ismerteti, részletesen, a termelési folyamat alvállalkozói tevékenységek használata a lean gyártási."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: KanbanJobSchedulingListPage, LeanRuleReassignmentWizard, PlanActivity, ReqSupplyDemandSchedule
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 267034
ms.assetid: 15c76a51-fa6d-42d2-994a-c67df6bae6a9
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 8e57c53ca894aa44b71e15c1f66bd7c722ea8a81
ms.lasthandoff: 03/31/2017


---

# <a name="activity-based-subcontracting"></a>Az alvállalkozói tevékenység alapú

Ez a témakör ismerteti, részletesen, a termelési folyamat alvállalkozói tevékenységek használata a lean gyártási.

A Microsoft Dynamics 365 műveletekhez, kétféleképpen alvállalkozói: gyártási rendelések és a lean gyártási. A lean gyártási oldalról való megközelítésnél az alvállalkozói munka a termelési folyamat tevékenységhez kapcsolódó szolgáltatásként modellje. A költségcsoport típusának nevű speciális típusú **Közvetlen kiszervezés** vezetett, és az alvállalkozói szolgáltatások már nem tartoznak egy anyagjegyzék (AJ). A Költségkönyvelés alvállalkozói munka teljesen integrálva van a lean gyártási költségszámítási megoldást.

## <a name="production-flows-that-involve-subcontractors"></a>Termelési folyamatok, amelyek magukban foglalják az alvállalkozók
Az alapelv a termelési folyamat nem módosíthatja, ha a tevékenységek alvállalkozásba vannak. Anyag továbbra is a helyek közötti pénzmozgások, a folyamat tevékenységeinek anyag átalakítása termékek és átviteli tevékenységek áthelyezése anyagok vagy termékek egyik helyről a másikra. Minta helyek, és működik a szállító által kezelt cellák raktárba vagy erőforráscsoportot az erőforrás hozzárendelésével a szállítói számlára.  

Alapján ezeket a lehetőségeket, lean gyártási nem igényel különleges jellemzők anyagok és termékek mozgásának támogatása érdekében. Az összes lehetséges forgatókönyvek szállítók, termelési vagy szállítási szolgáltatást nyújtók modellezhető a termelési folyamat és a tevékenységek architektúra alapján.  

Például egy alvállalkozó kívül egy szupermarket található, az alvállalkozó működik. Egységek kezelése, az alvállalkozó kiürítették, amikor a szerelvény cella a következő kiszállítás és visszatér a kanban kártyákat. A szupermarket az alvállalkozó, majd feltöltik. A transzfer és az alvállalkozó kifejezett átviteli tevékenységként egy válogatási és szállítási folyamat támogatásához lehet modellezni. Ha egy explicit regisztráció nem szükséges a fizikai szállítás támogatása érdekében, az átviteli tevékenységek kihagyható.  

Alvállalkozó terheléselosztásához, a teljes kapacitás, a termelési folyamat használható. Például a termelési folyamat modellezni ütemezett kanban szabályok segítségével. A tervezőnek mindkét munka cellák használja a kanban ütemezési tábla ütemezéséhez és terhelés igény. A tervezőnek a konszolidált ellátási ütemezését a szupermarket is figyeli a a **szállítási ütemezés** oldalon. Az egy vagy több termelési folyamatok több alvállalkozó lehet modellezni, és több kanbanszabályok használt adja meg ugyanazt a terméket ugyanazon a helyen, különböző tevékenységek útján lehet. A tervezőnek kanban ütemezni az eredetileg létrehozott egy másik folyamat belső termelési kanban alternatív kanbanszabály konvertálhatja. A munka cella alvállalkozói jellege valójában nem hatást gyakorol a termelési folyamat. Működési elvet alkalmazza, két párhuzamos belső munka cellát vagy alvállalkozói két cellát.   

A termelési folyamat semmilyen más tevékenységet, mint az alvállalkozásba adott tevékenységek fogyasztja és ellátási megtisztításáról, nem léteznek (folyamatban lévő munka \[a folyamatban lévő munka\]), és félkész anyagok és termékek. Minden esetben az ütemezéshez és alvállalkozói tevékenységek végrehajtása a folyamatok azonosak. Ezenkívül ezek folyamat ugyanaz, mint a folyamatok belső munka.

## <a name="purchase-process-for-subcontracted-activities-services"></a>Beszerzési folyamat alvállalkozói tevékenységek (szolgáltatások)
A beszerzési folyamat Alvállalkozói tevékenységekhez tartozó alapul a fizikai anyagáram által kanban feladat állapota, például bejegyzett, indítása vagy befejezése. Pénzügyi áramlását, például alvállalkozói munka költsége egy másodlagos áramlás, amely követi a fizikai áramlása. Ezzel egy időben a beszerzési folyamat egy független folyamat, amely lehetővé teszi a manuális helyesbítését a beszerzési bizonylatok minden lépésnél. Itt van a beszerzési folyamat alvállalkozói tevékenységek:

1.  Hozzon létre egy beszerzési szerződés. A beszerzési megállapodás a szolgáltatás létrehozása és a termelési folyamat tevékenységének csatlakoztatva.
2.  Beszerzési rendelés létrehozása Beszerzési rendeléskiadás szolgáltatás esetén a kanban ütemezett feladatok alapján is létrehozható. Ugyanezt a feladatot a beszerzési rendelési sorok nap, hét vagy hónap szerint lehet csoportosítani. A kanban feladatok létrehozása után bármikor a beszerzésirendelés-sorok hozhatók létre. A beszerzésirendelés-sorok még utólag hozhatók létre. A beállítás általában Ha az alvállalkozó a kanban vagy a kanban kártyákat az alvállalkozó fogadó alapján további értesítés nélkül szolgáltatásokat nyújt. Ebben az esetben a beszerzési rendelés és a számla közötti eltérések minimálisra csökkenthető.
3.  Kanban kártyákat, anyagok és az alvállalkozó küldeni előkészítése feldolgozásra kitárolási lista készítése. A termelési folyamat részletes modellezési alapul, a készítmény történik a folyamat tevékenységek kanbantáblájának a kitárolási lista és a készítmény függvény használatával. Azt is megteheti a készítmény használatával hajtható végre a feladatok kanbantáblájának a kitárolási lista és a start vagy a teljesítési. Megtisztításáról anyag mindkét eljárás a WMS-válogatási és szállítási folyamat által használható. A fuvarlevél igény hozhatók létre.
4.  Kanban kezelési egységeket és kanbankártyák készítése. A feldolgozást követően az alvállalkozó visszaküldi a kártyákat. A kártyák általában egy szállítólevél, amely meghatározza a le nem szállított anyagok fizikai tartalmazza. Hivatkozás a megadott szolgáltatás nem szükséges. Az érkezés az anyag vagy termék a vevő regisztrálva van a kanban táblán, attól függően, hogy a kanban kártyákat. (A folyamat tevékenységeinek kanbantáblájának vagy a feladatok kanbantáblájának szolgál, attól függően, hogy a modellezett tevékenységek.).
5.  Hozzon létre egy bevételezési tanácsadó. A beérkezés tanácsadó segítségével cserélje ki a csomagolás a kapott szolgáltatások dokumentum. Adott időszakra vonatkozóan a befejezett kanbanfeladatok az alvállalkozói tevékenység alapján beérkezés tanácsadók hozhatók létre. Minden egyes projekt bevételezéshez tanácsadók a kapcsolódó beszerzési rendelési sor jön létre. A beérkezés tanácsadó kinyomtathatók, és küldött az alvállalkozó kézhezvételének visszaigazolására.
6.  Számla készítése.

A folyamat véget ér, az alvállalkozó időtartamra számlázásakor. A számla egyeztetése a létrehozott elismervény tanácsadók szemben történik. Mert a beérkezési tanácsadók anyag pontos tényleges bevételezés jelöl, egyszerűsített háromirányú egyeztetés.

## <a name="configuring-activities-for-subcontracting"></a>Az alvállalkozói tevékenységek beállítása
A következő részekben az alvállalkozói tevékenységek beállítása.

### <a name="subcontracted-services"></a>Alvállalkozói szolgáltatások

Az alvállalkozói tevékenység alapú használt fizetési elemet kell olyan termék, amely a következő tulajdonságokkal rendelkezik:

-   **Termék típusa:** szolgáltatás
-   **Készletmodell-csoport:** nem raktározott

Ez a követelmény az első használata megköveteli a Készletmodell először ki (FIFO). **Megjegyzés:** költség kiszámítása során a termékek a szolgáltatás az Elszámolóár definiálását teszi szükségessé. A szállítóval a beszerzési megállapodásra szükség. Ellenkező esetben a szolgáltatás nem használható az alvállalkozói tevékenység alapú.

### <a name="subcontracted-process-activities"></a>Alvállalkozói folyamat tevékenységek

Egy folyamat tevékenység alvállalkozói tevékenységként konfigurálásához kövesse az alábbi lépéseket.

1.  Alvállalkozói munka cella beállítása. Munkacella, alvállalkozásba konfigurálásához létre kell hoznia az erőforrás a **szállító** írja be, és a munka cella (erőforráscsoport) társítása. A futásidejű költségkategória, a **Közvetlen kiszervezés** a költségcsoport típusának munkacella kell rendelni. A költségkategóriák beállítása és a mennyiség nem lesz szükség.
2.  Miután egy folyamat tevékenység létrehozása és alvállalkozói munka cellához kapcsolódó, konfigurálnia kell a tevékenység a szolgáltatás a termelési folyamat verziójának aktiválása előtt. E lépés végrehajtása a a **tevékenység****részletek** oldalon. Alvállalkozói munka cellához tartozó tevékenységek a **szolgáltatási feltételek** gyorslap jelenik meg. Ezen a gyorslapon alapértelmezett szolgáltatás, amely minden kimeneti cikkre érvényes hozzáadása. Ha egyes kimeneti elemek különböző szolgáltatásokat vagy különböző szerviz számítási paraméterek (például egy másik szolgáltatás arány), más szolgáltatásokat hozzáadhatja a tevékenység.

## <a name="subcontracted-transfer-activities"></a>Alvállalkozói átviteli tevékenységek
Egy átvitel tevékenység úgy van beállítva, alvállalkozói tevékenységként, attól függően, a **szállította:** az átviteli tevékenység beállítása. Az alábbi lehetőségek közül választhat:

-   **Szállítmányozó** – a tevékenység alvállalkozói, ha az átruházás a raktárból a szállító kezeli (a raktár tulajdonság által meghatározott). Szolgáltatások az összes kijelölt beszerzési megállapodások és a raktár rendelkeznie kell szállítói azonosítója.
-   **Címzett** – a tevékenység alvállalkozói, ha a szállító által kezelt szereplő raktárba történő átmozgatás, (a raktár tulajdonság által meghatározott). Szolgáltatások az összes kijelölt beszerzési megállapodások és a raktár rendelkeznie kell szállítói azonosítója.
-   **Fuvarozó** – a tevékenység minden szállítónak a szolgáltatást biztosító alvállalkozói. Érvényes legyen, a fuvarozó létre kell hozni a Raktárkezelés és szállító fiókkal kell rendelkeznie.

Folyamat tevékenységek, mint konfigurálnia kell az alvállalkozásba adott átviteli tevékenységek alapértelmezett szolgáltatást a **szolgáltatási feltételek** gyorslapján a **tevékenység****részletek** oldalon.

## <a name="service-quantity-calculation"></a>Szolgáltatás mennyiségszámítása
A teljes beszerzési folyamat egy szolgáltatás egy cikk hivatkozási alapul. A cikk hivatkozást egy szolgáltatás mértékegységben kell mérni. Szolgáltatások általában mérik a szolgáltatások (egységek) száma vagy időben. A szolgáltatás mennyiségének, kanbanfeladatok, bejegyzett megvalósításának alapján számítja ki az alábbi módszereket használhatja:

-   **Számítási feladatok száma alapján** – egy kanban feladat eredménye *n* szolgáltatási egységek, függetlenül attól, hogy rendelkezésre bocsátott termékmennyiség. A lean gyártási egy feladatot egy kezelési egység felel meg. Ezt a számítási módszert anyagkezelési egységenként fix díjjal rendelkező összes szolgáltatás vonatkozik. Ezért ez a módszer általában átmozgatási tevékenységekre vonatkozik. Azonban azt is alkalmazható folyamat tevékenységek teljes kezelési egységeket feldolgozni.
-   **A termék mennyisége alapuló számítási** – a szolgáltatás mennyiségének képest van ütemezve/szállított termékmennyiség van. A megadott mennyiség kiszámításakor hiba mennyiségeket is vagy felügyelt vagy kizárt. Ezt a számítási módszert vonatkozik minden olyan esetben, ahol a szolgáltatás feldolgozott termék egységára megállapodott.
-   **A tevékenység ideje alapuló számítási** – az elméleti tevékenység idejét számított, a feldolgozási idő a tevékenység alapján az összes feldolgozott mennyiség és a feldolgozott termék teljesítményarány. Ezt a számítási módszert olyan szolgáltatásokra vonatkozik, az óra által fizetett és a feldolgozott termékenként időbeli eltérés van.

## <a name="cost-accounting-of-subcontracted-services"></a>Költségkönyvelés alvállalkozói szolgáltatások
Tanácsadó beérkezés vagy szállítólevél, beszerzési rendelés a termelési folyamathoz (más szóval, a beszerzési rendelés Alvállalkozói tevékenységekhez tartozó kanbanfeladatok alapján létrehozott) létrehozott szállító könyvelésekor a bevételi értéke a termelési folyamatot Befejezetlen számláin kell elszámolni. Számlák eltéréseket is számolják el, a termelési folyamat. A költségkategória alvállalkozói munka bevezették. Ez a kategória folyamatban lévő munka lefoglalt és időszakonként felhasznált alvállalkozói munka értéke Átlátszó nyomon követését lehetővé.  

A lean gyártási költségszámítási időszak végén költségszámítási visszavezetéses költségszámítási időszakban a termelési folyamat előállított termékek tényleges eltérését számítja ki.

## <a name="modeling-transfers-as-subcontracted-activities"></a>Alvállalkozói tevékenységként modellezési átutalások
Emberek gyakran érdemes szállítás nem termelékeny és tudományos, hogy nem tartalmazó érték hozzáadása. Azonban belső előállítási költségét az alvállalkozói van képest, kiegészítő szállítási tevékenységek költségét kell figyelembe venni. Termelési folyamata átnyúlik egynél több helyen és szállítási szolgáltatások használatához a szállítási költséget a költség a termékek a vevő ellátását részeként kell modell. 

A lean gyártási alvállalkozói tevékenység alapú lehetővé teszi, hogy integrálja a fuvarozók és a szállítókat, anyagok és termékek mozgatása a termelési folyamat a helyek közötti átviteli. Egy átviteli tevékenységhez modellezési, hozzárendelheti a fuvarozó vagy a szállító. Az átviteli tevékenység/feladat egy szolgáltatás és a beszerzési megállapodás alapján, és a beszerzési rendelések és a bevételezési tanácsadók, a tényleges átviteli feladatok alapján hozhat létre. Ez a szolgáltatás megegyezik a Funkciók, alvállalkozói folyamat tevékenységek.  

Ezért 365 Dynamics most, amely tartalmazza a szállítási szolgáltatások, a kapcsolódó létrehozását támogatja az Anyagjegyzék-számítás beszerzési rendelések, integrált beérkezést nyilvántartásba és a közlekedési integráció műveletekhez azokat a termelési folyamat költségszámítása szolgáltatási költségek.


