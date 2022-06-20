---
title: Tevékenységi alapú alvállalkozásba adás
description: Ez a cikk részletesen leírja, hogyan lehet alvállalkozói tevékenységeket használni a termelési folyamat során lean manufacturing (lean gyártás).
author: johanhoffmann
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanJobSchedulingListPage, LeanRuleReassignmentWizard, PlanActivity, ReqSupplyDemandSchedule, PlanActivityServiceDetails, PlanActivityServiceWizard
audience: Application User
ms.reviewer: kamaybac
ms.custom: 267034
ms.assetid: 15c76a51-fa6d-42d2-994a-c67df6bae6a9
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e53da46a27fd573ae7f7450fcf34ffd8ef43e3fe
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8890741"
---
# <a name="activity-based-subcontracting"></a>Tevékenységi alapú alvállalkozásba adás

[!include [banner](../includes/banner.md)]

Ez a cikk részletesen leírja, hogyan lehet alvállalkozói tevékenységeket használni a termelési folyamat során lean manufacturing (lean gyártás).

A Microsoft Dynamics 365 Supply Chain Management-ben az alvállalkozásba adásnak két megközelítése van: termelési rendelések és lean manufacturing. A lean manufacturing megközelítés esetén az alvállalkozói munka egy termelési folyamat egy tevékenységhez kapcsolódó szolgáltatásként modelleződik. Egy speciális, **Közvetlen kiszervezés** nevű költségcsoporttípus került bevezetésre, a vezetett, az alvállalkozói szolgáltatások pedig már nem tartoznak bele az anyagjegyzékbe (AJ). Az alvállalkozói munkák költségkönyvelése teljesen integrálva van a lean manufacturing költségszámítási megoldásába.

## <a name="production-flows-that-involve-subcontractors"></a>Alvállalkozókat magukban foglaló termelési folyamatok
A termelési folyamatok alapelve nem módosul tevékenységek alvállalkozásba adásával. Az anyagok továbbra is helyek között mozognak, a folyamattevékenységek az anyagokat termékekké alakítják, a szállítási tevékenységek pedig anyagokat vagy termékeket helyeznek át egyik helyről a másikra. A helyek és munkacellák szállító által kezeltként történő modellezéséhez rendelje a szállítói számlát raktárhoz vagy erőforráscsoport erőforrásához.  

E lehetőségek alapján a lean manufacturing nem igényel különleges jellemzőket az anyagok és termékek mozgásának támogatása érdekében. Az összes lehetséges, termelési vagy szállítási szolgáltatást nyújtók szállítókat érintő forgatókönyv modellezhető a termelési folyamatokból és tevékenységekből álló architektúra alapján.  

Tegyük fel, hogy egy alvállalkozó egy az alvállalkozónál található szupermarketből működik. Az anyagkezelési egységek az alvállalkozónál történő kiürítésekor a kanbankártyák a következő szállítmánnyal visszakerülnek a szerelvénycellába. Ezt követően feltöltik az alvállalkozó szupermarketjét. Az alvállalkozóhoz érkező és tőle kiinduló átvitelek modellezhetők kifejezett átviteli tevékenységként a válogatási és szállítási folyamat támogatásához. Ha kifejezett regisztráció nem szükséges a fizikai szállítás támogatása érdekében, az átviteli tevékenységek kihagyhatók.  

Alvállalkozó használható a termelési folyamat teljes kapacitásának terheléselosztásához. Tegyük fel, hogy egy termelési folyamat modellezése ütemezett kanbanszabályok segítségével történik. A tervező kanbanütemezési táblát használ a két munkacella igény szerinti ütemezéséhez és terhelési szintjéhez. A tervező a szupermarket konszolidált ellátási ütemezését is figyeli a **Készletütemezés** oldalon. Több alvállalkozó is modellezhető egy vagy több termelési folyamatban, és több kanbanszabály is használható ugyanazon termék támogatására ugyanazon a helyen, különböző tevékenységek útján. A tervező a kanbanokat alternatív kanbanszabállyá konvertálhatja az eredetileg egy másik folyamat belső termeléséhez létrehozott kanban átütemezéséhez. A munkacella alvállalkozói jellege valójában nem gyakorol hatást a termelési folyamatra. Két párhuzamos belső munkacellára, illetve két alvállalkozói cellára ugyanazon működési elv vonatkozik.   

A termelési folyamat minden más tevékenységéhez hasonlóan az alvállalkozásba adott tevékenységek is fogyaszthatnak és biztosíthatnak készleten lévő és nem jegyzett (\[folyamatban lévő munka\]), illetve félkész anyagokat és termékeket. Az alvállalkozói tevékenységek ütemezéséhez és végrehajtásához használt folyamatok minden esetben azonosak. Ezenkívül e folyamatok ugyanazok, mint belső munkához használt folyamatok.

## <a name="purchase-process-for-subcontracted-activities-services"></a>Alvállalkozói tevékenységekhez (szolgáltatásokhoz) tartozó beszerzési folyamat
Az alvállalkozói tevékenységekhez tartozó beszerzési folyamat a kanbanfeladat folyamatában (például Indítás vagy Befejezés) rögzített fizikai anyagáramláson alapul. A pénzügyi áramlás, például az alvállalkozói munka költsége, egy másodlagos áramlás, amely a fizikai áramlást követi. Ezzel egy időben a beszerzési folyamat egy független folyamat, amely minden lépésnél lehetővé teszi a beszerzési bizonylatok manuális helyesbítését. Alvállalkozói tevékenységekhez tartozó beszerzési folyamat:

1.  Beszerzési szerződés létrehozása. A szolgáltatáshoz létrejön egy beszerzési szerződés, amely a termelési folyamat tevékenységéhez csatlakozik.
2.  Beszerzési rendelés létrehozása Beszerzési rendeléskiadás hozható létre a szolgáltatáshoz az ütemezett kanbanfeladatok alapján. Az ugyanazon szolgáltatáshoz tartozó feladatok nap, hét vagy hónap szerint csoportosíthatók a beszerzési rendelési sorokhoz. A beszerzésirendelés-sorok bármikor létrehozhatók a kanbanfeladatok létrehozása után. A beszerzésirendelés-sorok még utólag is létrehozhatók. Ezt a lehetőséget általában akkor használjuk, ha az alvállalkozó további értesítés nélkül nyújt szolgáltatásokat az alvállalkozó által kapott kanbanok vagy kanbankártyák alapján. Ebben az esetben a beszerzési rendelés és a számla közötti eltérések minimálisra csökkenthetők.
3.  Az alvállalkozónak elküldendő kanbankártyák, anyagok és kitárolási lista létrehozása a feldolgozás előkészítéseként. A termelési folyamat részletes modellezésének alapján az előkészítés a folyamattevékenységek kanbantábláján zajlik a kitárolási lista és az előkészítési funkció használatával. Másik lehetőség, hogy az előkészítés az átviteli feladatok kanbantábláján zajlik a kitárolási lista és a kezdés vagy teljesítés alapján. Készleten szereplő anyagoknál mindkét eljárás támogatható RAKT-kitárolási és szállítmányfolyamat révén. Igény szerint fuvarlevél hozható létre.
4.  Kanbankezelési egységek és kanbankártyák készítése. A feldolgozást követően az alvállalkozó visszaküldi a kártyákat. A kártyák általában szállítólevelet tartalmaznak, amely tartalmazza a leszállított fizikai anyagok meghatározását. A nyújtott szolgáltatásokra nem szükséges hivatkozni. Az anyag vagy termék a vevőhöz történő megérkezése rögzítésre kerül a kanbantáblán, a kanbankártyáktól függően. (A modellezett tevékenységektől függően vagy a folyamattevékenységek kanbantáblája, vagy az átviteli feladatok kanbantáblája kerül felhasználásra.)
5.  Beérkezési tanácsadó létrehozása. A beérkezési tanácsadó a kapott szolgáltatásokhoz kiállított szállítólevél dokumentum helyére léphet. Beérkezési tanácsadók hozhatók létre az adott időszaki alvállalkozói tevékenységhez tartozó befejezett kanbanfeladatok alapján. Minden egyes feladatnyugtához tanácsadók jönnek létre a kapcsolódó beszerzési rendelési sorhoz rendelve. A beérkezési tanácsadó kinyomtatható és elküldhető az alvállalkozónak a kézhezvétel visszaigazolására.
6.  Számla előállítása.

A folyamat akkor ér véget ér, amikor az alvállalkozó egy adott időtartamra számlát nyújt be. A számla egyeztetése a létrehozott beérkezési tanácsadók alapján történik. Mivel a beérkezési tanácsadók az anyag tényleges fizikai átvételét képviselik, a háromirányú egyeztetés egyszerűbbé válik.

## <a name="configuring-activities-for-subcontracting"></a>Alvállalkozói tevékenységek beállítása
A következő részekben tevékenységek alvállalkozóiként történő beállításáról tájékozódhat.

### <a name="subcontracted-services"></a>Alvállalkozói szolgáltatások

A tevékenységi alapú alvállalkozásba adáshoz használt fizetési elemeknek olyan termékeknek kell lenniük amelyek a következő tulajdonságokkal rendelkeznek:

-   **Terméktípus:** szolgáltatás
-   **Készletmodellcsoport:** nem raktározott

Ez a követelmény előírja az elsőként be, elsőként ki (FIFO) készletmodell használatát. **Megjegyzés:** a termékek költségeinek kiszámítása során meg kell adni a szolgáltatás elszámolóárát. A szállítóval beszerzési szerződésre van szükség. Ellenkező esetben a szolgáltatás nem használható tevékenységi alapú alvállalkozásba adáshoz.

### <a name="subcontracted-process-activities"></a>Alvállalkozásba adott folyamattevékenységek

Folyamattevékenység alvállalkozói tevékenységként való konfigurálásához kövesse az alábbi lépéseket.

1.  Állítson be egy alvállalkozói munkacellát. A munkacella alvállalkozásiként történő konfigurálásához létre kell hoznia egy **Szállító** típusú erőforrást, és társítania kell a munkacellával (erőforráscsoporttal). Egy **Közvetlen kiszervezés** költségcsoporttípusú futásidejű költségkategóriát kell hozzárendelni a munkacellához. Beállításra és mennyiségre vonatkozó költségkategóriákra nincsen szükség.
2.  Folyamattevékenység létrehozása és alvállalkozói munkacellához kapcsolása után konfigurálni kell egy szolgáltatást a tevékenységhez, mielőtt a termelésifolyamat-verziót aktiválni lehetne. E lépés végrehajtásához használja a **Tevékenység** **részletei** oldalt. Alvállalkozói munkacellához tartozó tevékenységeknél látható a **Szolgáltatási feltételek** gyorslap. Ezen a gyorslapon adjon hozzá olyan alapértelmezett szolgáltatást, amely minden kimeneti elemre érvényes. Ha egyes kimeneti elemek különböző szolgáltatásokat vagy különböző szolgáltatásszámítási paramétereket (például más szolgáltatási arányt) igényelnek, más szolgáltatásokat is hozzáadhat a tevékenységhez.

## <a name="subcontracted-transfer-activities"></a>Alvállalkozásba adott átviteli tevékenységek
Az átvitel tevékenységek alvállalkozói tevékenységként való beállítása az átviteli tevékenység **Szállította:** beállításától függ. Az alábbi lehetőségek közül választhat:

-   **Szállítmányozó** – a tevékenység alvállalkozói, ha a raktárból való átvitelt egy szállító kezeli (a raktár tulajdonságaiban szereplő meghatározás alapján). A szolgáltatásokhoz kijelölt összes beszerzési szerződésnek ugyanazzal a szállítói azonosítóval kell rendelkeznie, mint a raktárnak.
-   **Átvevő** – a tevékenység alvállalkozói, ha a raktárba való átvitelt egy szállító kezeli (a raktár tulajdonságaiban szereplő meghatározás alapján). A szolgáltatásokhoz kijelölt összes beszerzési szerződésnek ugyanazzal a szállítói azonosítóval kell rendelkeznie, mint a raktárnak.
-   **Fuvarozó** – a tevékenység alvállalkozásba van adva bármely olyan szállítónak, aki a szolgáltatást biztosítja. Az érvényességhez létre kell hozni egy fuvarozót a raktárkezelésben, és ennek szállító fiókkal kell rendelkeznie.

Folyamattevékenységeknél az alvállalkozásba adott átviteli tevékenységhez konfigurálni kell egy alapértelmezett szolgáltatást a **Szolgáltatási feltételek** gyorslapon a **Tevékenység** **részletei** oldalon.

## <a name="service-quantity-calculation"></a>Szolgáltatás mennyiségszámítása
A teljes beszerzési folyamat egy szolgáltatás egy cikkhivatkozásán alapul. E cikkhivatkozás mérése egy szolgáltatás mértékegysége alapján történik. A szolgáltatások mérése általában a szolgáltatások (egységek) számán vagy időn alapul. A szolgáltatás mennyiségének kanbanfeladatok bejegyzett elvégzésének alapján történő kiszámításához az alábbi módszereket használhatja:

-   **Feladatok száma alapján végzett számítás** – egy kanbanfeladat egyenlő *n* szolgáltatási egység, a rendelkezésre bocsátott termékmennyiségtől függetlenül. A lean manufacturing esetén egy feladat egy kezelési egységnek felel meg. Ez a számítási módszer az összes olyan szolgáltatásra vonatkozik, amelynél az anyagkezelési egységekhez fix díj tartozik. Ezért átviteli tevékenységekre általában ez a módszer vonatkozik. Azonban alkalmazható olyan folyamattevékenységekre is, amelyek teljes anyagkezelési egységeket dolgoznak fel.
-   **A termék mennyiségén alapuló számítás** – a szolgáltatás mennyisége az ütemezett/szállított termékmennyiségen alapul. A biztosított termékmennyiség kiszámításakor a hibamennyiségeket be lehet foglalni vagy ki lehet zárni. Ez a számítási módszer vonatkozik minden olyan esetre, ahol a szolgáltatás egységárát feldolgozott termékenként állapítják meg.
-   **A tevékenység idején alapuló számítás** – a tevékenység elméleti idejét számítjuk a tevékenység feldolgozási idejének, az összes feldolgozott mennyiségnek és a feldolgozott termék teljesítményarányának alapján. Ez a számítási módszer olyan szolgáltatásokra vonatkozik, amelyek kifizetése óraalapon történik, és ahol feldolgozott termékenként időbeli eltérés van.

## <a name="cost-accounting-of-subcontracted-services"></a>Alvállalkozói szolgáltatások költségkönyvelése
Egy termelési folyamathoz létrehozott beszerzési rendeléshez (más szóval alvállalkozói tevékenységekhez tartozó kanbanfeladatok alapján létrehozott beszerzési rendeléshez) tartozó beérkezési tanácsadó vagy szállítói szállítólevél feladásakor a bevételezés könyvelése a termelési folyamat alatti folyamatban lévő munka számláin történik. A számlák eltéréseinek elszámolása szintén a termelési folyamattal szemben történik. Bevezetésre került egy alvállalkozói munkához tartozó költségkategória. Ez a költségkategória lehetővé teszi a folyamatban lévő munkákhoz lefoglalt és időszakonként felhasznált alvállalkozói munkák értékének átlátható nyomon követését.  

A lean manufacturing visszavezetéses költségszámítása a költségszámítási időszak végén a termelési folyamatban a költségszámítási időszak során előállított termékek tényleges eltéréseit számítja ki.

## <a name="modeling-transfers-as-subcontracted-activities"></a>Alvállalkozói tevékenységként modellezett szállítás
Az emberek a szállítást gyakran nem termelékeny és hozzáadott értéket nem tartalmazó tevékenységnek tartják. Ha viszont az alvállalkozás költségét összevetjük a belső előállítással, a kiegészítő szállítási tevékenységek költségét is figyelembe kell venni. A több helyet felölelő és szállítási szolgáltatásokat igénylő termelési folyamatok modelljének a szállítási költséget a termékek a vevőnek való biztosítása során viselt költségek részeként kell tekintetbe vennie. 

A tevékenységalapú alvállalkozásba adás a lean manufacturingben lehetővé teszi azon fuvarozók és a szállítmányozási szállítók integrálását, amelyek anyagokat és termékeket mozgatnak a termelési folyamat helyei között. Az átviteli tevékenységek modellezésével fuvarozó vagy szállító rendehető hozzá. Az átviteli tevékenység/feladat szolgáltatási és beszerzési szerződésen alapul, és a tényleges átviteli feladatok alapján beszerzési rendelések és beérkezési tanácsadók hozhatók létre. Ez a szolgáltatás ugyanaz, mint az alvállalkozói folyamattevékenységek funkciója.  

A Supply Chain Management mostantól támogatja az olyan anyagjegyzék-kalkulációkat, amelyek a termelési folyamat költségszámításának részeként szállítási szolgáltatásokat, kapcsolódó beszerzési rendeléseket, integrált beérkezési nyilvántartást és integrált szállítási szolgáltatási költségeket biztosítanak.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]