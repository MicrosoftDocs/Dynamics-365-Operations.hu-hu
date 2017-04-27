---
title: "Feladat ütemezése"
description: "Ez a cikk információt biztosít a feladat ütemezésről, ami a művelet ütemezés egy részletesebb ütemezésű formája. A feladatütemezést használhatja az egyéni feladatok vagy bolti sorrendek ütemezésére és a gyártási környezet irányítására."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ProdSchedule
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 19431
ms.assetid: aef37341-91d8-4263-80eb-35d9584be156
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 99348a2e4a08af1107841cb211a138105fcac9ff
ms.lasthandoff: 03/31/2017


---

# <a name="job-scheduling"></a>Feladat ütemezése

[!include[banner](../includes/banner.md)]


Ez a cikk információt biztosít a feladat ütemezésről, ami a művelet ütemezés egy részletesebb ütemezésű formája. A feladatütemezést használhatja az egyéni feladatok vagy bolti sorrendek ütemezésére és a gyártási környezet irányítására.

A feladatütemezést használhatja az egyéni feladatok vagy bolti sorrendek ütemezésére és a gyártási környezet irányítására. A feladatütemezés külön feladatokra bontja az egyes műveleteket. Ezek a feladatok azután az üzemi erőforrásokhoz lesznek hozzárendelve, amik végrehajtják őket. A feladatütemezés lehetővé teszi azoknak a feladatoknak a szinkronizálását, amelyekre a kiválasztott feladat hivatkozik. Megadhatja a feladat kezdő vagy befejező dátumát, majd ezek alapján futtathatja az ütemezést. Az, hogy a kezdő vagy a befejező időpontot adja meg, az ütemezés irányától függ. Ez a funkció akkor hasznos, ha például csak egy feladatot futtathat egy számítógépen egy időben, vagy ha optimalizálni szeretné a futtatott feladatot minden egyes erőforráshoz.

## <a name="tasks-in-the-job-scheduling-process"></a>A feladatütemezési folyamat összetevői
Az feladatütemezési folyamat a következő feladatokat foglalja magában:

-   Az egyes műveletek feladatokká bontása.
-   Az egyes feladatok ütemezése a kapcsolódó műveletek számára megadott erőforrások időpontjai és időtartama alapján.
-   Minden feladat kezdő és befejező időpontjának kiszámítása. A véges kapacitás segítségével győződjön meg arról, hogy nincsenek egymást átfedő idők.
-   Határozza meg, hogy az erőforráscsoport mely erőforrásain fusson a feladat. Ehhez a lépéshez szükséges egy erőforráscsoport megadása egy művelethez. A feladatütemezés az erőforrásokat vagy az erőforráscsoportokat a lehető legrövidebb átfutási idő alapján választja ki, és figyelembe veszi az erőforrások minden korábbi foglalását.
-   Műveletek feladatokra bontása a feladatütemezés futtatásakor. A feladatok a termelési útvonal által megadott sorrendben, időpont és időtartam szerint lesznek ütemezve. A művelet beállítása határozza meg a feladatokat, amelyek az ütemezési folyamat során le lesznek bontva. Az az útvonalcsoport szabályozza azt, hogy a feladatok létrejönnek-e, amelyhez hozzá van rendelve a művelet. Egy-egy feladat csak akkor jön létre, ha konkrét hosszúsága van. Szállítási idő típusú feladat például csak akkor jön létre, ha az aktuálisan kiválasztott művelethez meg volt adva szállítási idő.

## <a name="scheduling-direction"></a>Ütemezési irány
Előre vagy hátrafelé is ütemezhet feladatokat.

-   **Előre** – Az ütemezési módok közül alkalmazza az „Előre” lehetőséget a termelés minél korábbi indításához. Ezzel a módszerrel a lehető leghamarabb véghez lehet vinni a termelési folyamatot. A termelés a lehető legkorábbi kezdő és befejező időpontra van ütemezve.
-   **Hátrafelé** – Az ütemezési módok közül alkalmazza a „Hátrafelé” lehetőséget a termelés minél későbbi indításához. Ez a módszer a termelés befejezésének időpontján alapul. A hátrafelé ütemezés a termelés befejezésétől számítja vissza a lehető legkésőbbi időpontot, amikor a termelést a határidőből való kifutás nélkül el lehet indítani.

## <a name="finite-capacity"></a>Véges kapacitás
Ütemezhet feladatokat véges kapacitás segítségével. Véges kapacitás használatakor az ütemezett kapacitás nem lehet nagyobb, mint az erőforrás rendelkezésére álló kapacitás. A rendelkezésre állási idő azt az időintervallumot jelenti, amelyben az erőforrás elérhető, és nincs másik foglalás a kapacitására. A véges kapacitással történő ütemezés gondoskodik arról, hogy ne legyen átfedés a művelet kezdési és befejezési ideje között egy adott időpontban. Figyelembe veszi a már lefoglalt kapacitást és a kezdési és befejezési időpontok közötti átfedést. A véges kapacitás meghatározza azt a kapacitásmennyiséget, amelynek az erőforrás optimális működéséhez rendelkezésre kell állnia. Ez a döntés a műveletek közötti legrövidebb átfutási idő kiszámításával szemben kiegyenlített.

## <a name="finite-materials"></a>Véges anyagmennyiség
A véges anyagmennyiséggel történő ütemezés gondoskodik arról, hogy a szükséges anyagok rendelkezésre álljanak a művelet elkezdésekor. A cikkek fedezeti szabályai határozzák meg ezeket a korlátokat. Az ütemezés szükséglet-alábontást használ az összetevő cikkek rendelkezésre állásának meghatározásához. Véges anyagmennyiséggel történő ütemezés esetén a rendszer azt feltételezi, hogy minden cikk rendelkezésre áll a szükséges időben.

## <a name="finite-properties"></a>Véges tulajdonságok
Az adott tulajdonságokkal történő ütemezéshez szükséges, hogy a termékútvonal műveleteinél meg legyenek határozva a tulajdonságok. Ezeknek a tulajdonságoknak teljesülniük kell a kapacitás lefoglalásához.

## <a name="references"></a>Hivatkozások
A feladatütemezés minden hivatkozott termelést az aktuális termeléshez ütemez. Ha egy termelésnek egy vagy több altermelése van, az altermelések ütemezésének a főtermeléssel együtt kell történnie, mivel a főtermelés nem indítható addig, amíg a kapcsolódó altermelések be nem fejeződtek.

## <a name="schedule-resources"></a>Erőforrások ütemezése
Az ütemezési motor megvizsgálja az erőforrások kombinációját, hogy meghatározza azokat a kombinációkat, amelyek megfelelnek a követelményeknek. Megadhatja a kiválasztási feltételeket a következő értékek egyikének kiválasztásával az **Elsődleges erőforrás kijelölése** mezőben az **Ütemezési paraméterek** oldalon:

-   **Időtartam** – Az ütemezési motor kiválasztja azt az erőforrást, amely a legrövidebb átfutási idővel rendelkezik. **Megjegyzés:** Az időtartam alapján való ütemezés csökkentett teljesítményt okozhat, ha ugyanaz az erőforráscsoport több erőforrást használ és másodlagos műveletek is futnak. Legfeljebb 32 erőforrást ütemezhet műveletenként. Ha túllépi ezt a mennyiséget, az Információs napló üzenete jelenik meg, és a feladatütemezés nem találja meg a legjobb alternatív erőforrást.
-   **Prioritás** – Az ütemezési motor kiválasztja azt az erőforrást, amelynek a legmagasabb a prioritása, ha kettő vagy több erőforrás megegyező képességgel és szinttel rendelkezik. A mezőben a legkisebb numerikus értékkel rendelkező erőforrás rendelkezik a legmagasabb prioritással.

A feladatütemezés futtatásakor a rendszer megtervezi az erőforrásokat, figyelembe véve az erőforrások paramétereinél megadott korlátozásokat. Az erőforrások kapacitása szabályozható a naptár-beállítások használatával. A rendszer kiszámítja az erőforrások rakományait az ütemezési folyamat során. **Megjegyzés:** A műveletütemezési funkciót használó termelések esetében a műveletek ütemezése után lehet futtatni a feladatütemezést. Ha nem alkalmaz műveletütemezést, külön is futtathatja a feladatütemezést.

## <a name="maximum-capacities-for-resources-per-job-order"></a>Az erőforrások maximális kapacitása feladatrendelésenként
Az erőforrások a feladatütemezésen keresztül vannak feladatokhoz rendelve. Az erőforrások maximális kapacitását feladatrendelésenként lehet megállapítani. Beállíthatja például a rendszerben azt az ütemezést, hogy a teljes kapacitásnak legfeljebb 50 százaléka lehet művelet egy termelési rendeléshez ütemezve. Ez a beállítás lehetővé teszi azt, hogy tovább szabályozza az erőforrásainak ütemezését a feladatok ütemezésének szintjén. Így megelőzhető ugyanis az, hogy nem marad elég kapacitás az egyidejű termelések elvégzésére.

## <a name="resource-efficiency"></a>Erőforrás-hatékonyság
A feladatütemezés figyelembe veszi az erőforrásokra vonatkozóan megadott hatékonysági százalékokat is. A hatékonysági százalékok csökkentik vagy növelik az erőforrásra lefoglalt időt. Ezért az átfutási idő szintén növekszik vagy csökken. A számítás a következő képlet segítségével történik: ütemezési idő = idő × 100 ÷ hatékonysági százalék. Ebben a képletben az *Idő* egyaránt tartalmazza a lefutási és a beállítási időt.




