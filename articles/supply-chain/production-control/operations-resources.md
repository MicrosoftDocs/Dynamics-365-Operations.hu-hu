---
title: Operations-erőforrások
description: Az üzemi erőforrások hajtják végre egy projekt vagy egy termelési folyamat tevékenységeit. Ezek eltérő típusúak lehetnek, illetve eltérő képességeket hordozhatnak.
author: johanhoffmann
ms.date: 11/03/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: OpResLifecycleManagementWorkspace, WrkCtrCapability, WrkCtrResourceGroup, WrkCtrResourceAbilityMap, OpResCapacityPlanningWorkspace, WrkCtrCapResGraph, WrkCtrResourceRequirementPart, WrkCtrCapResGraphDialog, WrkCtrResourceCopy, WrkCtrCapResStatistic
audience: Application User
ms.reviewer: kamaybac
ms.custom: 61943
ms.assetid: a3847f07-fca4-4140-a26f-d83c6ac68dde
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9296ea874acece9af6be58ccfe777f8713a4d279
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/29/2021
ms.locfileid: "7566719"
---
# <a name="operations-resources"></a>Operations-erőforrások

[!include [banner](../includes/banner.md)]

Az üzemi erőforrások hajtják végre egy projekt vagy egy termelési folyamat tevékenységeit. Ezek eltérő típusúak lehetnek, illetve eltérő képességeket hordozhatnak. 

## <a name="operations-resources"></a>Operations-erőforrások

Az üzemi erőforrások azok a gépek, eszközök, dolgozók, létesítmények, fizikai területek vagy szállítók, melyek az egy adott projekthez vagy termelési folyamathoz tartozó tevékenységeket végzik. Ezek eltérő típusúak lehetnek, illetve eltérő képességeket hordozhatnak.

-   **Szállító** – Olyan külső erőforrás, amely projekttevékenységeket vagy gyártási műveleteket végez. Példa ilyenre egy alvállalkozó. Ha a szállítói erőforrásokat egy szállítói számlával társítja, úgy alvállalkozói beszerzéseket tud létrehozni az anyagjegyzék (AJ) sorok vagy a termelési sorok alapján.
-   **Emberi erőforrások** – Olyan, egy projektben vagy a termelésben érintett dolgozó, aki önállóan vagy egy eszköz vagy gép kezelőjeként valamilyen tevékenységet végez. Ha az Emberi Erőforrások funkciót használja, emberi erőforrásokat tud kapcsolni a dolgozókhoz. Az ütemezési motor ezt követően el tudja osztani az erőforrásokat, az adott dolgozó kapcsán meghatározott kompetenciák alapján.
-   **Gép** – A termeléshez szükséges gép vagy más termelési berendezés.
-   **Eszköz** – Olyan szerszám vagy berendezés, amely jellemzően egy másik erőforrással együtt kerül felhasználásra egy tevékenység, egy projekt, vagy a termelés során.
-   **Hely** – Egy tevékenység végrehajtásához szükséges, meghatározott méretű fizikai hely. Példa ilyenre az összeállítási terület.
-   **Létesítmény** – Tevékenység végrehajtásához szükséges épület vagy rögzített szerkezetet.

## <a name="calendars"></a>Naptárak
Az üzemi erőforrásokhoz lehet naptárt hozzárendelni, amely megmutatja az adott erőforrás (órában kifejezett) kapacitását. Az üzemi erőforrás működési idejét az ahhoz az erőforráscsoporthoz hozzárendelt naptár határozza meg, amelybe az adott üzemi erőforrás is tartozik. A hozzárendelt naptár kapcsán tud hatályba lépési dátumot és lejárati dátumot állítani be. Ezután több naptárt is hozzá tud rendelni az adott üzemi erőforráshoz. A hozzárendelt naptárak dátumai azonban nem lehetnek átfedésben, és az üzemi erőforrás egy időben csak egy naptárhoz lehet hozzárendelve. **Megjegyzés:** Ha egy adott erőforráscsoporthoz nem tartoznak érvényes munkaidőnaptárak (például ha az utolsó hozzárendelt naptár vagy az egyedüli hozzárendelt naptár lejárt), akkor a gyártástervezés és a műveletütemezés céljára a továbbiakban nem érhetők el az erőforráscsoporthoz rendelt üzemi erőforrások. Rendelhet hozzá naptárt erőforráscsoporthoz annak érdekében is, hogy munkaidőket adjon meg mind az erőforráscsoport, mind az ahhoz rendelt összes üzemi erőforrás kapcsán. Az erőforráscsoport kapacitását a rendszer az adott erőforráscsoporthoz rendelt önálló üzemi erőforrások kapacitásainak összesítése útján számítja ki. Az erőforráscsoporthoz hozzárendelt naptár idővel változhat.

## <a name="resource-capabilities"></a>Erőforrás-képességek
A képesség egy üzemi erőforrás képességét jelenti egy adott tevékenység végrehajtására. Több képességet is hozzá tud rendelni egy adott üzemi erőforráshoz. Az ütemezési motor ezután úgy osztja fel az erőforrásokat, hogy összekapcsolja az egyes tevékenységek erőforrás-követelményeit az elérhető üzemi erőforrásokkal. Bármilyen típusú üzemi erőforráshoz rendelhetők hozzá képességek (**Eszköz**, **Szállító**, **Gép**, **Emberi erőforrások**, **Hely**, illetve **Létesítmény**). A képességek adott ideig, adott üzemi erőforráshoz történő hozzárendeléséhez adjon meg kezdő és lejárati dátumot a képesség hozzárendelésekor. További információkért lásd az [Erőforrás képességek](resource-capabilities.md) c. szakaszt.

## <a name="resource-groups"></a>Erőforráscsoportok
Az erőforráscsoport az üzemi erőforrások olyan csoportja, amely megfelelő részletességet biztosít az erőforrások kívánt ütemezéséhez a műveletütemezés módszer használatakor. Az erőforráscsoportok ezért jellemzően megfelelnek a munkacellák fizikai elrendezésének, amelyet a termelésben a padlón lévő sárga vonalak jelölnek. Az erőforráscsoport határozza meg a csoporthoz hozzárendelt üzemi erőforrások kapcsán a telephelyet, a termelési egységet és a raktárkörnyezetet. Amikor üzemi erőforrást rendel hozzá erőforráscsoporthoz, az adott erőforrás ütemezhetővé válik azon a telephelyen, ahol az erőforráscsoport található. A létrehozott üzemi erőforrásokat nem kötelező hozzárendelni erőforráscsoporthoz. Munkavégzési ütemezés beállításához azonban már hozzá kell rendelni az üzemi erőforrást erőforráscsoporthoz. Az üzemi erőforrásokat csak korlátozott időre lehet az egyes erőforráscsoportokhoz rendelni. Egy adott üzemi erőforrást több erőforráscsoporthoz is hozzárendelheti, ha szeretné azt több telephelyen is használni. Az érvényességi és lejárati dátumok azonban nem lehetnek átfedésben. Más szóval, egy időben nem lehet egy üzemi erőforrást két külön erőforráscsoporthoz rendelni. Az erőforráscsoport-hozzárendelés kapcsán eszközölt változások csak az új erőforrás-hozzárendelésekre lesznek érvényesek. Nincsenek azonban kihatással a már korábban ütemezett feladatokra, műveletekre és projektórákra vonatkozó kapacitásfoglalásokra. **Megjegyzés:** Amikor **Szállító** típusú erőforrást szeretne hozzárendelni egy erőforráscsoporthoz, először meg kell győződnie arról, hogy az adott erőforráscsoporthoz rendelt minden üzemi erőforrás **Szállító** típusú, illetve egyazon szállítói számlához kapcsolódik.

## <a name="production-units"></a>Termelési egységek
A termelési egység erőforráscsoportokat tartalmazó adminisztratív egység. Egy termelési egység több erőforráscsoportot tartalmazhat, egy erőforráscsoport azonban csak egy termelési egységhez tartozhat. A termelési egység a termelési erőforrások fizikai elrendezését képezi le, nincsen hatással a tranzakciókra vagy azok feldolgozására. A termelési egységeket telephelyhez kell társítani. A termelési egységhez emellett kitárolási raktár és tárolási raktár is rendelhető. Termelési egység használatával a termeléshez kapcsolódó adatok konszolidálhatók és szűrhetők. Egy üzemvezető például ez alapján áttekintheti a még hátralévő feladatokat és az adott termelési egység rendelkezésre álló kapacitását. Az erőforráscsoporthoz társított termelési egységet módosíthatja, vagy akár törölheti is. A termelési egység ezen változásai ugyanakkor csak az alapütemezés futtatása után létrehozott új rendelésekre lesznek érvényesek. Ha a termelési egység módosítását már meglévő rendelésekre szeretné alkalmazni, úgy ezt a változtatást manuális módszerrel kell elvégeznie.

## <a name="resource-scheduling"></a>Erőforrás-ütemezés.
Projekt vagy termelés ütemezésekor a rendszer üzemi erőforrásokat rendel a tevékenységekhez. Két ütemezési módszer áll a rendelkezésére: a műveletütemezés, illetve a feladatütemezés. Műveletütemezés használata esetén a rendszer a művelet kapcsán meghatározott erőforrásigénynek megfelelő üzemi erőforrásokat tartalmazó erőforráscsoportra ütemez minden egyes műveletet vagy projekttevékenységet. Amennyiben egy adott művelet konkrét erőforrást követel meg, úgy az ütemezés csak a csoport egy konkrét erőforrása kapcsán foglal le kapacitást. A feladatütemezés részletesebb ütemezési módszer, mint a műveletütemezés. A folyamat külön feladatokra bontja az egyes műveleteket. Ezek a feladatok azután az üzemi erőforrásokhoz lesznek hozzárendelve, amik végrehajtják őket. Az ütemezés a termelési útvonalon vagy a projekttevékenységeken megadott műveletidők alapján foglal le erőforráscsoport kapacitásokat. Ha véges kapacitással dolgozik, úgy az ütemezés az adott tevékenység elvégzéséhez szükséges üzemi erőforrások rendelkezésre állásának függvénye. Műveletütemezés esetén az erőforráscsoport kapacitása a csoportot alkotó üzemi erőforrások rendelkezésre álló kapacitásainak az összege. Az üzemi erőforrások kapcsán korábban lekötött kapacitásokat a rendszer nem elérhető kapacitásként veszi figyelembe. Ha nincs elég rendelkezésre álló kapacitás a termeléshez, úgy a rendszer késleltetheti vagy le is állíthatja a termelési rendeléseket. Az **Erőforrások** lapon több olyan tulajdonságot is be tud állítani, amely hatással van arra, hogy hogyan történik a kapacitásfoglalás:

-   **Kapacitás** – Adja meg az üzemi erőforrás óránkénti kapacitását az adott kapacitási mértékegységben.
-   **Kötegelt kapacitás** – Adja meg a maximális darabszámot, amelyet az üzemi erőforrás egy futás alkalmával feldolgozni képes.
-   **Hatékonysági százalék** – Adja meg az üzemi erőforrással szemben támasztott hatékonysági elvárást. A hatékonysági százalék beállítja az üzemi erőforrás teljesítményét és befolyásolja az erőforrás kapcsán lefoglalt időt. Az üzemi erőforrást használó műveletek átfutási ideje is ennek megfelelően kerül módosításra. Itt látható a kiszámítására használt képlet: ütemezési idő = idő x 100 ÷ hatékonysági százalék. Az *Idő* a feldolgozási és a beállítási időt is magába foglalja.
-   **Műveletek ütemezése** – Adja meg az üzemi erőforrások kapacitásának azt a maximális százalékát, amelyet a műveletek ütemezésében használni kíván. 100 százalék alatti értéket adjon meg, ha szeretné lehetővé tenni a rugalmas kapacitáshasználatot a feladatütemezés során.
-   **Véges kapacitás** – Állítsa ezt a beállítást **Igen** értékre, ha az üzemi erőforrást a ténylegesen elérhető kapacitás alapján kell ütemezni, és ha a meglévő kapacitásfoglalásokat figyelembe kell venni. Ha ebben a beállításban **Nem** szerepel, az üzemi erőforrás feltételezett kapacitása korlátlan, és így előfordulhat az erőforrás túlfoglalása.
-   **Véges tulajdonság** – Állítsa ezt a beállítást **Igen**-re, ha az üzemi erőforrást a ténylegesen elérhető kapacitás alapján kell ütemezni, és ha a meglévő kapacitásfoglalásokat figyelembe kell venni.
-   **Kizárólagos** – Állítsa ezt a beállítást **Igen** értékre, ha szeretné, hogy az üzemi erőforrás csak az aktuális termelés befejezését követően váljon elérhetővé másik feladathoz vagy művelethez. Ebben az esetben az üzemi erőforrást még akkor sem lehet más célra használni, ha az erőforrás működési idejében szünet lép fel.
-   **Szűk keresztmetszetű erőforrás** – Adja meg a szűk keresztmetszetű erőforrásnak minősülő üzemi erőforrást. A szűkös erőforrás ütemezése mindig véges kapacitással történik, ha a **Véges kapacitás** mező és a **Szűk keresztmetszet-ütemezés** mező be van jelölve az **Alaptervek** oldalon.

Ha több üzemi erőforrást szeretne egy időben, például egy termelési művelet végrehajtása érdekében ütemezni, úgy meg kell adnia a különböző erőforrásokra vonatkozó követelményeket elsődleges és másodlagos műveleteket segítségével. Ezután lehetősége lesz több eltérő kapacitással rendelkező üzemi erőforrást foglalni le. Az elsődleges művelethez ütemezett üzemi erőforrás határozza meg a tevékenység időtartamát.

## <a name="lean-work-cells"></a>Lean munkacellák
Megadhatja, hogy egy erőforráscsoporthoz lean munkacellához tartozzon-e. Az erőforráscsoport ezután szerepelhet termelési folyamatban. Erőforráscsoport lean munkacellaként történő minősítése útján megakadályozhatja, hogy az erőforráscsoport és a hozzárendelt üzemi erőforrások egy termelési rendelés műveleteihez vagy egy projektóra-előrejelzéshez hozzárendelésre kerüljenek. A lean munkacellának minősülő összes erőforráscsoport kapcsán meg kell adnia a következő adatokat:

-   **Naptár** – A munkacella szokásos munkanapban meghatározott munkanaptára.
-   **Bemeneti raktár és hely** – A tevékenység kapcsán történő anyagkiválasztás alapértelmezett helye.
-   **Kimeneti raktár és hely** – Az alapértelmezett hely, ahová a munkacellával kapcsolatos összes kimeneti elem kerül.
-   **Futásidő-költségkategória** – A munkacella kapcsán meg kell adnia ezt a kategóriát, ha a költségszámításban nyomon követi a közvetlen munkaerőköltséget.

Erőforráscsoport lean munkacellaként történő használata esetén a munkacella kapacitás megadása közvetlenül az erőforráscsoporton történik. A létrehozott üzemi erőforrásokat ezért nem kötelező hozzárendelni az erőforráscsoporthoz. Csak abban az esetben kell **Szállító** típust rendelni hozzá a munkacellához, ha azt alvállalkozó kezeli. Ha munkacellaként megjelölt erőforráscsoporthoz rendel hozzá üzemi erőforrást, úgy ez nincs kihatással a munkacella kapacitására.

## <a name="costing-resources"></a>Költségszámítási erőforrások
Ha olyan tevékenységet ad meg, mint például egy útvonalművelet vagy egy projektóra-előrejelzés, úgy meghatározhat egy adott üzemi erőforrásra vagy erőforráscsoportra vonatkozó követelményeket. Megadhat azonban egy adott típusú, vagy egy adott képességgel vagy kompetenciával rendelkező üzemi erőforrásra vonatkozó követelményeket is. Emiatt az aktuális erőforrás-hozzárendelésre csak a tevékenység ütemezésekor, illetve a kapacitás lefoglalásakor kerül sor. Útvonalművelet esetén tehát megadhatja, hogy becslés, illetve az anyagjegyzék-számítás egy konkrét üzemi erőforrásra legyen alapozva. A rendszer a jelen üzemi erőforrásra, mint költségszámítási erőforrásra hivatkozik. A költségszámítási erőforrásról is tud költségkategóriákat és a műveleti időket vinni át a tevékenységre. Művelet ütemezése esetén a becslés és az anyagjegyzék-számítás a ténylegesen ütemezett üzemi erőforrás felhasználásával történik.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]