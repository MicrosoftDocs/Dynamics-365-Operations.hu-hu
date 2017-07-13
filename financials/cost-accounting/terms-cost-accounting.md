---
title: "Költségkönyvelési terminológia"
description: "Ez a témakör a költségkönyveléshez használt kulcskifejezéseket határozza meg."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CAMCostControlWorkspace, CAMCostControlWorkspaceConfiguration
audience: Application User
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 223114
ms.assetid: 1c798592-77d0-4a8f-beaa-9159c75957da
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 35b8e510e7e2c13aebb73f46d20b16275d097432
ms.contentlocale: hu-hu
ms.lasthandoff: 06/13/2017


---

# <a name="cost-accounting-terminology"></a>Költségkönyvelési terminológia

[!include[banner](../includes/banner.md)]


Ez a témakör a költségkönyveléshez használt kulcskifejezéseket határozza meg.

**Költségkönyvelés**

A költségkönyvelés lehetővé teszi adatok összegyűjtését különböző forrásokból, például: főkönyv, részfőkönyvek, költségvetések és statisztikai adatok. Ezután elemezheti, összesítheti és kiértékelheti a költségadatokat, hogy a vezetőség a lehető legjobb döntéseket hozhassa meg az ármódosításokkal, a költségvetésekkel, a költségkontrollal stb. kapcsolatban. A költségelemzés alapjául használt forrásadatok kezelése önállóan történik a költségkönyvelésben. Emiatt a Költségkönyvelés frissítései nem befolyásolják a forrásadatokat. Azonban amikor költségadatokat gyűjt össze különböző forrásokból, és különösen akkor, ha a fő számlák importálását a Microsoft Dynamics 365 for Finance and Operations Enterprise edition megoldásban költségösszetevőkként végzi a főkönyvből, adatredundancia lép fel, mert ugyanazok az adatok a főkönyvben és a költségkönyvelésben is léteznek. Ez a redundancia szükséges, kérik, mert a pénzgazdálkodást használjuk külső jelentésekhez és a költségkönyvelést a belső jelentésekhez.

**Költségkönyvelési főkönyv**

A költségkönyvelési főkönyv speciális keretrendszer, amely meghatározza a folyamatok, értékek és mennyiségek bevitelének és megjelenítésének módját a költségkönyvelés adott területén. A költségkönyvelési főkönyv határozza meg a költségek és költség-objektumok mérési szabályait. Kezeli a költségtranzakciókat, és kezeli a dokumentumokat, amelyek azokat az értékek- és mennyiségváltozásokat rögzítik, amelyeket a költségtranzakciók állítanak elő.

**Költségbejegyzés**

A költségbejegyzések az adatösszekötőkkel végzett átvitel eredményei a főkönyvi bejegyzésekből, költségfelosztásokból és feladott költségbejegyzésekből a költségnaplókban.

**Költségobjektum**

A költségobjektumok bármilyen típusú objektumok, amelyekhez költségek vannak felosztva. Az alábbiakban néhány jellemző objektumot mutatunk be:

-   Termékek
-   Projektek
-   Erőforrások
-   Osztályok
-   Költséghelyek
-   Földrajzi területek

A vezetés költségobjektumokat használ a költségek mennyiségének megállapítására, illetve a nyereségességi elemzés elvégzésére.

**Költségösszetevő**

A költségösszetevőket függvényként használjuk annak a nyomon követésére és kategorizálására, hogy hová mennek a költségek. A költségösszetevőknek két típusa van: az elsődleges költségek és a másodlagos költségek. **Elsődleges költségek** Az elsődleges költségösszetevők a pénzügyi könyvelésből a költségkönyvelésbe menő költségeket jelentik. A költségösszetevők szerkezete a főkönyv eredménykimutatási szzerkezetének felel meg, ahol egy költségösszetevő egy fő számlának felel meg. Nem minden fő számlának kell megjelennie költségösszetevőként - ez attól függ, hogy mik a vállalat követelményei. Az elsődleges költségösszetevők közé például a következők tartoznak:

-   Eladott áruk beszerzési értéke (COG)
-   Közvetett anyagköltségek
-   Személyi költségek
-   Energiaköltségek

**Másodlagos költségösszetevő** 

A másodlagos költségösszetevők a költségek belső áramlását képviselik, mivel ezeket a költségeket csak a költségkönyvelésben hozzák létre és használják. A másodlagos költség-összetevők segítenek garantálni a költségek forrásának nyomonkövetését. Ezek a költségösszetevők költségfelosztásokban és többletköltség-számításokhoz használatosak. A másodlagos költségösszetevők közé például a következők tartoznak:

-   Gyártási költségek
-   Termelési, anyag és marketing többletköltségek

**Költség-ellenőrzőegység**

A költség-ellenőrzőegység a költségek szerkezetét jelöli. A költségobjektum-dimenziókhoz kell társítani a költségkönyvelési főkönyvben.

**Verzió**

Verziók segítségével történik a különböző eredmények szimulálása, megtekintése és összevetése. Alapértelmezés szerint minden tényleges költséget egy alapverzióban tekintünk meg, amelynek a neve a *tényleges*. A költségvetések és a számítások esetében tetszőleges számú verzióval dolgozhat. Például költségvetési adatokat importálhat az eredeti verzióban, majd felülvizsgálhatja a költségvetést egy módosított verzióban. A számításokhoz több verziót hozhat létre. Ezekben a különböző verziókban számításokat hozhat létre különböző, a költségfelosztáshoz alkalmazott számítási szabályok segítségével.

**Kimutatás**

A kimutatások a költségellenőrzésért felelős vezetők számára létrehozott nézetek. A kimutatásokat a költségellenőrök határozzák meg, és gyors áttekintést adnak a tényleges és a költségvetésben szereplő költségekről, illetve akár az eltérésekről és a számítási verziókról is. Annak a garantálásához, hogy a vezetők csak azokat az adatokat lássák, amelyekért felelősek, a kimutatásokban megjelenő adatok hozzáférési szabályok hatálya alá tartoznak.

**Adatcsatlakozó**

A külső rendszerekből az adatokat adatcsatlakozókkal lehet importálni a költségkönyvelésbe. Például importálhatók a számlastruktúrák, dimenziók, főkönyvi bejegyzések és költségvetési tételek. Az adatok importálásához és az adatkapcsolatok létrehozásához előre konfigurált adatcsatlakozók vagy egyéni csatlakozók használhatók.

**Költség osztályozása**

A költségosztályozás a közös jellemzőik szerint csoportosítja a költségeket. Költségeket például elemek, nyomon követhetőség és viselkedése szerint lehet csoportosítani.

-   **Elemek szerint** – anyag, munka és a költségek.
-   **Nyomon követhetőség szerint** – közvetlen és közvetett költségek. A közvetlen költségek közvetlenül a költségobjektumokhoz társulnak. A közvetett költségek nem követhetők nyomon közvetlenül a költségobjektumokhoz. A közvetett költségek a költség-objektumokhoz vannak felosztva.
-   **Viselkedés szerint** – rögzített, változó, és félig változó.

**Költség működése**

A költségviselkedés a viselkedésük alapján osztályozza a költségeket, a kulcsfontosságú üzleti tevékenységek változásával kapcsolatban. A költségek hatékony ellenőrzéséhez a vezetésnek értenie kell a költségviselkedést. Költségviselkedési mintának három típusa van: rögzített, változó és félig változó.

- **Rögzített költség** – A rögzített költség olyan költség, amely rövid távon nem változik, tekintet nélkül a tevékenységi szint változásaira. A rögzített költség lehet például egy vállalkozás alap működési költsége, például a bérlet, amelyet nem befolyásol az sem, ha növekszik vagy csökkent a tevékenység szintje.

- **Változó költség** – A változó költség a tevékenységi szint változásainak megfelelően változik. Például minden egyes értékesített termékhez társítva van egy adott közvetlen anyagköltség. Minél több terméket értékesít, annál több a közvetlen anyagköltség.

- **Félig változó költség** – A félig változó költségek részben rögzített és részben változó költségek. Az internet-hozzáférés díja például havi hozzáférési alapdíjat és szélessávú használati díjat is tartalmaz. A szokásos havi hozzáférési díj rögzített költség, miközben a szélessávú használati díj változó költség.

**Járulékos költség**

A járulékos költségek a vállalat működésének folyamatos költségeire vonatkoznak. Olyan költségek, amelyeket nem lehet közvetlenül adott üzleti tevékenységekhez kapcsolni. Az alábbiakban néhány példa látható a járulékos költségekre:

-   Könyvelési díjak
-   Értékcsökkenések
-   Biztosítás
-   Érdeklődési terület
-   Jogi díjak
-   Adók
-   Közüzemi költségek

**Költségfelosztás**

A költségfelosztás a költségek hozzárendelése és felosztása a közös költségek kiváltó oka alapján. A költségösszegeket és -mennyiségeket egyik költségobjektumtól egy vagy több másik költségobjektumokhoz osztjuk fel. A létesítményszolgáltatási költségeket például a közös irodaépületet használó különböző részlegek között osztjuk fel.

**Költségfelosztási irányelv**

A költségfelosztási szabály határozza meg a felosztandó összegeket és mennyiségeket. A felosztási szabályok magukban foglalják a felosztási forrásszabályokat, amelyek meghatározzák a felosztott költségeket, és a felosztási célok szabályait, amelyek megadja, hová történik a költségek felosztása. Például az összes létesítményszolgáltatási költség felosztási forrás, amelyek a különböző részlegek számára oszthatók fel a szervezeten belül (ezek a felosztási célok).

**Felosztás alapja**

A felosztási alap az az alap, amely a tevékenységek, például a felhasznált számítógépórák, a felhasznált kilowattórák, a felhasznált közvetlen munkaórák vagy a lefoglalt négyzetméterek mérésére és számszerűsítésére használható. Egy vagy több költségobjektumhoz történő költségfelosztásra szolgál.

**Felosztás elve**

A felosztási elvek egyike a költség felosztása költségszorzó szerint. A költségek feloszthatók az aktuális időszak szorzója vagy múltbeli szorzó szerint. A kölcsönös módszert használó felosztás segítségével garantálható, hogy a felosztás alapját párhuzamos egyenletek sorozata alapján határozzák meg, mielőtt megtörténne a felosztás a tényleges időszak szorzója alapján.

**Költségösszesítés**

A költségösszesítés célja minden költség felvétele egy adott költségobjektumhoz. Az összesítés szintje a felhasználó által definiált. Költségösszesítés segítségével összevonhatja a költségelemeket, amelyek fel kell osztani egy költségobjektumtól egy másikhoz. Ha nem használja a költségösszesítést, minden egyes költségelem felosztása megtörténik egyik költségobjektumtól a másikhoz.

**Költségszorzó szabály**

A költségszorzó az ár/költségobjektum kiszámítására szolgál. Az ár elemeinek megértéséhez költségszorzószabályokat határoz meg. Költségszorzó két típusa van: előzmény költségszorzó és tervezett költségszorzó. Az előzmény költségszorzó számított szorzó, amelyet a költségobjektum felosztási alapjának szorzójaként használunk. A szorzó kiszámításának alapját a költségfelosztások adják az előző időszakból. A tervezett szorzó a felhasználó által definiált szorzó.

**Dimenzióhierarchia**

A dimenzióhierarchiákat jelentési struktúraként használják, amikor felosztási, költségszorzóra vonatkozó és költségösszesítési szabályokat határoz meg, kimutatásokat vagy adatokat tekint meg a Microsoft Excelben, és hozzáférést határoz meg az összesített adatokhoz. Két dimenzióhierarchia van: kategorizálási hierarchia és osztályozási hierarchia. A kategorizálási hierarchia költségösszetevők alapján, az osztályozási hierarchiába költségobjektumok alapján van meghatározva.

**Statisztikai dimenzió**

A statisztikai dimenzió egy objektum számlálási vagy összesítési kifejezése, amely felosztások vagy költségszorzó-számítások alapjául használható. Manuálisan létrehozott vagy forrásrendszerekből importált. Statisztikai dimenzió például az alkalmazottak száma, a licencelt szoftverek száma minden eszközön, minden gép energiafogyasztása vagy a négyzetméterek egy költséghelyhez.

**Statisztikai bejegyzés**

Statisztikai bejegyzések tartalmazzák a rögzített összeget vagy számlált értéket egy adott statisztikai dimenzióhoz. A rögzített összeget vagy számlált értéket nagyságnak is nevezik.




