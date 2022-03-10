---
title: A Költségvetés-tervezés integrálása más modulokkal
description: Költségvetési tervek számos különböző forrásból hozhatók létre. Az időszaki folyamat alapvető összetevői ugyanazok, mint a többi forrás esetében.
author: panolte
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BudgetPlanGenerate
audience: Application User
ms.reviewer: roschlom
ms.custom: 64443
ms.assetid: f9a94db5-906c-404a-9ca5-91528d67c490
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ceae7296ef6d8a0f181c306bd533694c0219e467
ms.sourcegitcommit: e40a9fac5bac9f57a6dcfe73a1f21856eab9b6a9
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/02/2021
ms.locfileid: "7594742"
---
# <a name="budget-planning-integration-with-other-modules"></a>A Költségvetés-tervezés integrálása más modulokkal

[!include [banner](../includes/banner.md)]

 Költségvetési tervek számos különböző forrásból hozhatók létre. Az időszaki folyamat alapvető összetevői ugyanazok, mint a többi forrás esetében. 



## <a name="periodic-processes-for-generating-budget-plans"></a>Időszaki folyamatok költségvetési tervek létrehozásához

Költségvetési tervek az alábbi forrásokból hozhatók létre:

-   Főkönyvi tranzakciók
-   Tárgyi eszközök
-   Előrejelzési pozíciók
-   Projekt előrejelzései
-   Szállítmány-előrejelzések
-   Igény-előrejelzések
-   Költségvetési tételjegyzék-bejegyzések
-   Egyéb költségvetési tervek

Az időszaki folyamatok alapvető összetevői ugyanazok, mint a többi folyamat esetében. A lapok segítségével tudja megadni az adatok forrását, a (költségvetési tervre vonatkozó) céljellemzőket, illetve a folyamat a háttérben, kötegfolyamatként történő futtatására vonatkozó lehetőséget. A jelen szövegrész későbbi szakaszaiban bemutatjuk az olyan cikkeket, melyek nem minden folyamat esetében nyilvánvalók.

### <a name="actions"></a>Műveletek

Minden létrehozási folyamat kapcsán az alábbi műveletek állnak rendelkezésre:

-   **Új költségvetési terv létrehozása** a **Cél** szakaszban kiválasztott jellemzőknek megfelelő új terv létrehozása. Ezeknek a jellemzőknek nem kell egyedinek lenniük. Így tehát két tervnek is lehet azonos a neve, illetve a további értékei.
-   **A meglévő költségvetési tervváltozat cseréje** a cél költségvetési terv költségvetési tervváltozatában szereplő összes adat törlése, illetve a kiválasztott forrásadatokat használó új sorok létrehozása.
-   **A meglévő költségvetési tervváltozat frissítése, és új adatok hozzáfűzése** a meglévő sorok frissítése a forrássoroknak megfelelő céltervben, és új sorokat hozzáadása új adatok rögzítéséhez. A megfeleltetés a főkönyvi számla, a dátum, a költségvetési osztály, illetve a többi mező alapján történik. Ha például előre jelzett beosztások alapján hoz létre költségvetési terveket, úgy kiemelt szerepet játszik a beosztásszám. Minden, a forrás beosztásszámmal azonos beosztásszámot tartalmazó sor helyére a forrás új sorai kerülnek.

### <a name="source"></a>Forrás

A **Forrás** lap minden folyamat esetében lehetővé teszi az adatok, a **Szűrő** gomb segítségével történő szűrését. Az alapértelmezés szerint a rendszer konkrét mezőket társít minden szűrőhöz. Ha például a **Költségvetési terv létrehozása főkönyv alapján** folyamatot vesszük, a **Főkönyvi számla** és a **Fő számla** kategóriák érhetők el, és jelennek meg a létrehozás lapon. Az Ön által a szűrőhöz hozzáadott mezők is hozzáadásra kerülnek az oldalhoz, csakúgy, mint az Ön által hozzáadott feltételek.

### <a name="target"></a>Cél

Az **Előzmények** beállítás a **Cél** lapon lehetővé teszi, hogy a forrásadatok dátumát a költségvetési terv érvényességi dátumaként használja. Az érvényességi dátumnak jellemzően a terv költségvetési ciklusán belülre kell esnie. Ha az **Előzmények** beállításnál az **Igen** lehetőséget választja, úgy a rendszer a forrás dátumát használja (beleértve akár az évet is), így összehasonlítási céllal fel tudja használni a múltbeli adatokat. A költségvetési tervben az előzményadatok nem módosíthatók, a terv munkafolyamat-állapota pedig: jóváhagyott. Az állapot azonban szükség esetén módosítható, amennyiben a terv más változatait módosítani kell.

Az oldal tetején található **Összesítési szempont** mező meghatározza a használt dátumot is. Ez a mező összesíti az összegeket, illetve opcionálisan a pénzügyi év vagy időszak első napját állítja be érvényességi dátum gyanánt. 

A <strong>Cél</strong> lapon található számos mező az Ön által választott művelet függvényében lesz szerkeszthető vagy írásvédett állapotú. Ha az új költségvetési terv létrehozása művelet helyett egy meglévő terv módosítására vált, úgy nem lesz elérhető a **Költségvetési terv neve** mező, viszont elérhetővé válnak a meglévő terv kiválasztásához kapcsolódó mezők. Sem a **Cél**, sem a **Forrás** lapon nem érhető el a **Főkönyv** mező, mivel ezt az értéket a kiválasztott költségvetés-tervezési folyamat határozza meg. 

A **Költségvetési osztály** mezőben költségtranzakciók vagy bevételi tranzakciók formájában tudja megadni a költségvetési terv sorait. A bevételi tranzakciók jellemzően követel tételként jelennek meg a főkönyvi számlán, így azokat a rendszer negatív összegként tárolja. Ezek a tranzakciók jellemzően a költségvetési tervben is negatív összegként szerepelnek. Amennyiben azonban a terv elrendezésben hozzáadja a költségvetési osztály mezőt, úgy lehetővé teszi, hogy a bevétel pozitív összegként jelenjen meg.

### <a name="generation-rules"></a>Létrehozási szabályok

Három mező nyújt további funkciókat: **Szorzó**, **Minimum** és **Kerekítési** **szabály**. 

A költségvetési tervösszeg kiszámításához a rendszer összeszorozza a **Szorzó** mezőben található értéket a forrásösszeggel. Ezután helyesbítheti az összegeket a költségvetésiterv-sorok létrehozásakor. Egy 3 százalékos növekedés beállításához például adja meg az **1,03** összeget. A szorzó csak pozitív szám lehet. 

A **Minimum** mezőben küszöbértéket tud megadni költségvetésiterv-sor létrehozásához. Ha a forrásösszeg kisebb ennél az értéknél, a rendszer nem hoz létre költségvetésiterv- sort. A **0,00** beállítás minden összeget lehetővé tesz, ideértve a negatív összegeket is. (Nincs olyan beállítás, amely a pozitív összegekre korlátozná a sorokat. A rendszer mindig figyelembe veszi a negatív összegeket is , melyek általában követel tételek.)

A **Kerekítési szabály** mező lehetővé teszi, hogy beállítsa az Ön által létrehozott költségvetésiterv-sorok pontossági szintjét. Az összegek az adott pénznem legközelebbi 1,00, 10,00, 100,00 stb. értékére kerekíthetők.

## <a name="notes-for-specific-processes"></a>Konkrét folyamatokra vonatkozó megjegyzések
### <a name="generate-budget-plan-from-general-ledger"></a>Költségvetési terv létrehozása főkönyv alapján

Ha főkönyvi adatokból hoz létre költségvetési tervet, az **Összesítési szempont** mezőben a **Pénzügyi év** beállítást kell választania, ha az **Előzmények** beállítása **Nem**. A forrásban szereplő időszakok és a dátumok elképzelhető, hogy nem egyeznek a célban szereplő időszakokkal és dátumokkal. Mivel a folyamat nem képes megbízható módon leképezni ezeket az értékeket, a folyamatot az első évre kell korlátoznia. 

A **Költségvetési osztály** mező beállítása a célban **Költség** vagy **Bevétel** lehet. A beállítás célja a létrehozott sorokra vonatkozó **Költségvetéstípus** jellemző kiválasztása, amikor egy soron szereplő fő számla nem **Bevétel** vagy **Költség** típusú.

### <a name="generate-budget-plan-from-fixed-assets"></a>Költségvetési terv létrehozása tárgyi eszközök alapján

A **Költségvetési terv létrehozása tárgyi eszközök alapján** folyamat nem tartalmaz időszaki vagy nap összesítési lehetőséget. Ugyanúgy nincs lehetőség a terv előzményként történő beállítására. Ez az időszaki folyamat a tárgyi eszközökre vonatkozó előre jelzett tranzakciók, a költségvetés-tervezés során történő felhasználását teszi lehetővé.

### <a name="generate-budget-plan-from-forecast-positions"></a>Költségvetési terv létrehozása előrejelzési pozíciók alapján

A **Költségvetési terv létrehozása előre jelzett beosztások alapján** folyamat a forrásban szereplő előre jelzett beosztásokat rendeli hozzá a költségvetési terv sorához. A beosztást úgy tudja megtekinteni, ha az előre jelzett beosztást sorként belefoglalja a költségvetési terv elrendezésbe a **Költségvetésiterv-sorok** lekérdezés segítségével. Ha nem szeretné, hogy az előre jelzett beosztás a költségvetésiterv-sorokhoz hozzárendelésre kerüljön, a **Költségvetésiterv-sor beosztás befoglalása** lehetőséget állítsa **Nem** értékre.

A költségvetési tervben szereplő sorok összesítése főkönyvi számla és a beosztás szerint történik. Ki tudja azonban zárni a beosztásszámot, hogy a rendszer egyedül a főkönyvi számla szerint végezze az összesítést. A **Cél** lapon állítsa a **Beosztás befoglalása a költségvetési tervbe** lehetőséget **Nem** értékre.

A **Költségvetési terv teljes munkaidőssel egyenértékű változata** mezőben tudja kiválasztani, ha szeretné a költségvetési tervben feltüntetni a teljes munkaidős egyenérték (FTE) számot. Ez a mező egyedül a cél költségvetési terv elrendezésében szereplő, mennyiség típusú változatokat tartalmazhat. Teljes munkaidős egyenérték változat kiválasztása esetén ki kell választania egy teljes munkaidős egyenérték fő számlát is. A rendszer ezt a számlát használja a mennyiségalapú költségvetésiterv-sorok létrehozásához. 

A forrásban kiválasztott költségvetés-tervezési folyamat és költségvetési tervváltozat határozza meg a célváltozat költségvetés-tervezési folyamatát és változatát. Mivel ezek a jellemzők az előre jelzett beosztásokhoz vannak hozzárendelve, azoknak egyezniük kell a költségvetési tervvel. Ezért ezek a jellemzők a célon nem módosíthatók.

### <a name="generate-budget-plan-from-project-forecasts"></a>Költségvetési terv létrehozása projekt-előrejelzések alapján

A **Költségvetési terv létrehozása projekt-előrejelzések alapján** folyamat, csakúgy mint a **Költségvetési terv létrehozása előrejelzési beosztások alapján** folyamat, tartalmaz projekt-mennyiségek (órák, költségek és cikkek), a mennyiségi változatba történő belefoglalására vonatkozó lehetőséget. A két folyamat hasonló szűrőket tartalmaz a költségvetési-terv elrendezés oszlopai kapcsán is. 

A **Forrás** lapon a **Kimutatással együtt** szakasz három beállítási lehetősége határozza meg, hogy a rendszer milyen költségvetésiterv-sorokat hoz létre. Ezek a beállítási lehetőségek ugyanazok, mint a tételjegyzék-bejegyzések, közvetlenül a projekt-előrejelzésekből történő létrehozásakor rendelkezésre állók. Költség- és bevételsorok létrehozásához állítsa az **Eredmény** beállítást az **Igen** értékre. Befejezetlen termelés bejegyzések létrehozásához állítsa a **Befejezetlen termelés** beállítást **Igen** értékre. Sorok, óratranzakciókra vonatkozó bérlista ellenszámlák számára történő létrehozásához állítsa a **Bérfoglalás** beállítást **Igen** értékre. 

Nincs **Költségvetési osztály** mező, mivel a költségvetési osztály (**Költség** vagy **Bevétel**) a forrás függvénye. 

A projektköltségvetéseket forrásként tudja felhasználni, ha kiválasztja a projekt-költségvetési összegeket tartalmazó előrejelzési modellt. Ne feledje, hogy a projektköltségvetések a jóváhagyással párhuzamosan hoznak létre projekt-előrejelzési bejegyzéseket.

Ha csak a költségeket vagy bevételeket szeretné kiválasztani a költségvetésiterv-sorokhoz, szűrő segítségével állítsa be a következőt: <strong>Költségvetési frissítések: Összeg típusa = Költség</strong>. Egyetlen típusú előrejelzés kiválasztásához szűrő segítségével állítsa be a következőt: <strong>Költségvetési frissítések: Tranzakciótípus = *xxx</strong>*. 

Költségvetési tervváltozat létrehozásához csak egy előrejelzési modellt használható. Ha a folyamatot lefuttatja az egyik előrejelzési modellre, majd végrehajt egy frissítést és próbál megadni egy másik modellt, úgy a rendszer felülírja az első modellt, ha arra ugyanazok a projekt- és főkönyvi számlák vonatkoznak. Ha több előrejelzési modellből szeretne költségvetési tervváltozatot hozni létre, azokat különböző költségvetési tervváltozatok formájában készítse el, majd használja a felosztási beállításokat azok, egy másik változatban történő összesítése érdekében. 

A **Költségvetési terv létrehozása előre jelzett beosztások alapján** folyamat szintúgy a költségvetésiterv-sorához rendeli a forrásprojektet.

### <a name="generate-budget-plan-from-supply-forecast"></a>Költségvetési terv létrehozása ellátási előrejelzésből

A folyamat és a funkció közötti hasonlóság okán, a **Költségvetési terv létrehozása szállítmány előrejelzés alapján** lehetőségben található forrásszűrő lehetőségek modellezése a **Beszerzési költségvetés átvitele a főkönyvbe** funkció beállításai alapján történt.

### <a name="generate-budget-plan-from-demand-forecast"></a>Költségvetési terv létrehozása igény-előrejelzés alapján

Bevételsorok, a költségvetési tervben történő létrehozásához a **Költségvetési terv létrehozása igény-előrejelzés alapján** folyamatban az **Értékesítési rendelés** beállítást állítsa **Igen** értékre, költségsorok létrehozásához pedig állítsa a **Felhasználás** beállítást **Igen** értékre, vagy mindkettő beállítást **Igen** értékre.

### <a name="generate-budget-plan-from-budget-register-entries"></a>Költségvetési terv létrehozása költségvetésijegyzék-bejegyzésekből

A **Költségvetési terv létrehozása költségvetési tételjegyzék-bejegyzések alapján** folyamat esetében a forrásnak meg kell adnia egy részmodellt egy költségvetési kódot és egy tételszámot. Más szóval, egyszerre csak egy költségvetési tételjegyzék-bejegyzéshez hozhat létre költségvetésiterv-sorokat. A folyamat minden egyes forrástételre történő önálló lefuttatásával tud további tételeket hozni létre ugyanabban a költségvetési tervben.

### <a name="generate-budget-plan-from-budget-plan"></a>Költségvetési terv létrehozása költségvetési terv alapján

A **Költségvetési terv létrehozása a költségvetési terv alapján** folyamat esetében a **Cél** lapon található további beállítási lehetőségek lehetővé teszik az új pénzügyi dimenziók hozzárendelését. Pénzügyi dimenzió kiválasztása esetén a rendszer ezt az értéket használja az összes költségvetésiterv-sorhoz. Ennek megfelelően alapozhat egy költségvetési tervre további költségvetési terveket, de például hozzá is rendelhet egy másik osztályt vagy költséghelyet az új költségvetési tervekhez.

## <a name="looking-back-from-the-budget-plan"></a>A költségvetési terv áttekintése
### <a name="budget-plans-by-dimension-set-inquiry"></a>Költségvetési tervek dimenziókészlet lekérdezés alapján

A **dimenziókészlet szerint költségvetési tervek** lekérdezés számos lehetőséget tartalmaz, amelyek lehetővé teszik a költségvetési terv adatainak forrását azonosítását. 

Válasszon ki egy sort, majd kattintson a **Költségvetésiterv-sorok** gombra a **Költségvetésiterv-sorok** lekérdezés futtatásához. A rendszer a kijelölt sorok dimenzióértékei alapján szűri az eredményeket. Ezután további paramétereket is alkalmazhat. 

Használja a **Szállítmány-előrejelzés** és **Igény-előrejelzés** gombokat a lekérdezések futtatásához. A lekérdezés mindkét esetben olyan előrejelzés-sorokat keres, melyek alapján a költségvetésiterv-sorok létrehozhatóak lettek volna. 

További rendelkezésre álló jelentés például az **Előre jelzett beosztások költségvetési terv alapján** jelentés. Ez a jelentés különösen akkor hasznos, ha szeretné meghatározni, hogy helyesen történt-e egy beosztás felosztása a költségvetési tervek között.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
