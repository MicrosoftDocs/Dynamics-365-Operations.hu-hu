---
title: "A termelés alvállalkozói munka kezelése"
description: "Ez a témakör bemutatja, hogyan alvállalkozói műveletek kezelik a Microsoft Dynamics 365 műveletekhez. Más szóval bemutatja, hogyan kezeli a szállító által lefoglalt erőforrások gyártási műveleteket."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: LeanDocumentServiceCreation, PlanActivity, ProdBOMVendorListPage, ProdRoute, ProdTable, ProdTableListPage, PurchAgreementSubcontractorLookup, RouteTable, WrkCtrResourceGroup
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 268174
ms.assetid: fe47c498-4f48-42a2-a0cf-5436c19ab3ea
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: f707d45290682e79ee439ba0d504852429defa90
ms.openlocfilehash: 79430358bebd93fd96f1169d22737d3537dbfc08
ms.lasthandoff: 03/31/2017


---

# <a name="manage-subcontracting-work-in-production"></a>A termelés alvállalkozói munka kezelése

Ez a témakör bemutatja, hogyan alvállalkozói műveletek kezelik a Microsoft Dynamics 365 műveletekhez. Más szóval bemutatja, hogyan kezeli a szállító által lefoglalt erőforrások gyártási műveleteket.

A [a termelési folyamatok](production-process-overview.md), munkát által birtokolt vagy a szállítók által kezelt erőforrásokat lehet elvégezni. Általában használt szállító típusú erőforrások szintű időszakos túlzott igényt, amely túllépi a rendelkezésre álló kapacitás a vállalat saját forrásaira. A szállító is lehet konkrét ajánlat [erőforrás-képességek](resource-capabilities.md)vagy erőforrások alacsonyabb áron.  

Attól függően, hogy a szállító típusú erőforrások, amelyek felhasználhatók a termelési folyamat a [útvonal](routes-operations.md) gyakran további logisztikai követelményekkel rendelkezik, mert az anyag és a félkész termékeket először kell szállítani a szállító webhelyére. Majd az alvállalkozásba adott művelet eredményének vagy arra a helyre, a következő művelethez vagy késztermékek raktárba kell szállítani.  

Alvállalkozói műveletek vagy tevékenységek használata esetén azok a műveletek a műveletek, amelyek szükségesek a gyártási, költségszámítás, előrejelzés, tervezés és ütemezés, logisztika az alapanyagok, félkész termékek és késztermékek kezelésére meghatározásából minden szakaszában hatással. Végül ezeket az erőforrásokat saját folyamatok szükséges számlázási és költség-ellenőrzés.  

A belső erőforrások fix költségszorzót általában lefoglalt időtartamra. Ezzel szemben alvállalkozói erőforrások költsége a kapcsolódó szolgáltatás a beszerzési ár alapján történik. A szolgáltatás egy másik termék meghatározása, és a meghajtó a közbeszerzési és beszerzési folyamatok adott alvállalkozói művelet.  

Jelenleg nincs félkész termék Microsoft Dynamics 365 műveletekhez explicit fogalmát. Egy gyártási rendelés, amely egynél több műveletet igényel annak érdekében, hogy a nyersanyagok átalakítása kész jó a késztermék programba csak az utolsó műveletet a készlet feladása történik. A félkész termékek, amelyek a korábbi műveletek számolják el a folyamatban lévő munka (Befejezetlen), de nem könyvelt és a készletben nyomon követett. Feloszthatja az útvonalakat és anyagjegyzékeket (AJ) több kisebb egységekre, bár ez a megközelítés növeli a termékek, anyagjegyzékek és útvonalak kell kezelni, a számot.  

Az alvállalkozói munka gyártási műveletek modellezési két módja van. Ezek a módszerek eltérő módon, hogy az alvállalkozói folyamat lehet modellezni, félkész termékek jelennek meg a folyamat, és úgy, ahogyan a Költségellenőrzés kezeli.

-   A gyártási rendelések vagy kötegelt rendelések útvonalműveletek alvállalkozásba
    -   A szolgáltatás terméknek kell lennie a raktározott termék, és az AJ részét kell lennie.
    -   Ezt a módszert először be, először ki (FIFO) vagy elszámolóár támogatja.
    -   Félkész termékek a Folyamatban szerviz termék jelölik.
    -   Költségkontroll lefoglalja az alvállalkozói munka jelentős költségekhez kapcsolódó költségek.
-   A lean termelési folyamat termelési folyamat tevékenységeinek alvállalkozásba
    -   A szolgáltatás szolgáltatás a raktározott termék, és az AJ részét nem.
    -   Ezt a módszert használja a szolgáltatási szerződések beszerzési szerződések.
    -   Ez a módszer használ visszavezetéses költségelszámolás.
    -   Ez a módszer lehetővé teszi az összesített és aszinkron beszerzési. (Anyagáram független a beszerzési folyamatban.)
    -   Költségkontroll alvállalkozói munka saját költség részletezése blokk foglal le.

## <a name="subcontracting-of-route-operations"></a>Útvonalműveletek alvállalkozásba
Útvonalműveletek gyártására vagy kötegelt rendelések alvállalkozásba használatához a szolgáltatás termék, amely a szolgáltatás beszerzésére szolgál meg kell határozni a termék a **szolgáltatás** típusa. Ezenkívül rendelkeznie kell olyan cikkmodellcsoporthoz, amelynek a **raktározott termék** beállítás alapján **házirend készlet** értéke **Igen**. Ez a beállítás határozza meg, hogy e termék számolnak el, a készlet termék átvételekor (**raktározott termék** = **Igen**), vagy hogy a termék nyereség és veszteség számlán kiadásként könyvelve (**raktározott termék** = **nem**). Ez a viselkedés ellentmondásos tűnhet, bár van azon a tényen alapszik, hogy csak azok a termékek, amelyek ezt a házirendet hoz létre készlettranzakciók használható Költségkontroll tervezett költség kiszámítása és a tényleges költség határozza meg, amikor a gyártási rendelés be van fejezve.  

Költség és a tervezési számítás során figyelembe kell venni, hogy a szolgáltatás az AJ hozzá kell adni. Az AJ-sornak kell lennie, a **szállító** típusa, és az útvonalművelet a szolgáltatás lefoglalt kell felosztani. Az útvonalművelet kell a költségszámítási és mutasson az erőforrás az erőforrás követelmény a **szállító**, amely a művelet és a kapcsolódó szolgáltatás csatlakozik a megfelelő szállítói számla típusa.  

Ez a konfiguráció használata esetén a beszerzési rendelést a kapcsolódó vevőszolgálati termékhez, a becsült termelési rendelés alapján jön létre. A beszerzési rendelés, a szolgáltatás az alvállalkozói műveletek horgony szolgál. Az alvállalkozói munka keresztül lehet kezelni a **munka alvállalkozásba** gyártásellenőrzés lista oldalra. Az alvállalkozói munka nyersanyag, és végül, félkész termék szállítás a szállító a művelet előkészítése szolgál. Azt is fogadására szolgál az alvállalkozásba adott művelet termék a cikk érkezése, ahol a szolgáltatás termék megérkezéséről a félkész termék azonosítására szolgál. A beszerzésirendelés-sor érkezik, a termelési frissül művelet befejezettként.  

A gyártási rendelés számos művelet lehet, és minden egyes művelet különböző szállító nem foglalható. Ezért egy végpontok közötti gyártási rendelés több beszerzési rendelés válthat ki.

## <a name="subcontracting-of-production-flow-activities"></a>A termelési folyamat tevékenységeinek alvállalkozói
A [lean gyártási](lean-manufacturing-overview.md)megoldás modellek az alvállalkozói munka szolgáltatás, amely a tevékenység kapcsolódik a [termelési folyamat](http://ax.help.dynamics.com/en/wiki/create-a-production-flow-version/) (feladat útmutató témakör). Ezért az ilyen alvállalkozói is nevezik [alvállalkozói tevékenység alapú.](activity-based-subcontracting.md) Külön költség csoport típusa **Közvetlen kiszervezés**, vezetett, és az alvállalkozói szolgáltatások nem tartoznak a késztermékek az anyagjegyzék. Lean gyártási használatakor minden olyan tevékenység, amely összefüggésben lehet egy vagy több termelési folyamat tevékenységeinek kanban határozza meg. Eddig adott magyarázat hangzik csak a gyártási rendelések magyarázatot. Mivel a termelési rendelések mindig a késztermék kell végződnie, félkész termék ellátásának kanban hozhat létre. Nem kell bevezetni egy új termék és az AJ-szint.  

Kanbanszabályok lehet nagyon dinamikus, mert a termelési folyamat különböző változatai az ugyanarra a termékre vonatkozó ellátási modellezhető. Lean használatakor alvállalkozói, az anyagáram és pénzügyi áramlását szigorúan elválasztva. Minden anyagáram kanban tevékenységet jelöl. A beszerzési rendeléseket a szolgáltatási termékekre és az ilyen szolgáltatások a Beérkezés könyvelés automatizálható, a termelési folyamatban kanban-feladatok állapota alapján. Kanbanfeladatok indítható és még mielőtt a beszerzési rendelések létrehozása befejeződött. Az alvállalkozói dokumentumok (beszerzési rendelés és beszerzési elismervény a szolgáltatás) időszak és szolgáltatás is kell összesíteni. Ezért a beszerzési bizonylatok és sorok számát is eltartható kicsi, még akkor is, ha szállítók rendelkeznek a single-darab folyamat alvállalkozói szolgáltatások erősen ismétlődő műveleteket.

### <a name="modeling-subcontracting-in-a-production-flow"></a>A termelési folyamat az alvállalkozási modellezési

Az egy [lean típusú termelési folyamat](lean-manufacturing-modeling-lean-organization.md), a folyamat tevékenység lehet meghatározni, ha a hozzárendelt munka cella (erőforráscsoport) egyetlen szállítói erőforrással rendelkező alvállalkozásba. Alvállalkozói munka cellára, ha a kapcsolódó feldolgozási tevékenységek egy aktív beszerzési szerződés sorában, amely tartalmazza a szervizcikk és a szolgáltatás árát kell kapcsolódniuk. A szolgáltatási szerződéshez a tevékenység is a kanban feladat termék mennyiségét, és az így kapott mennyiséget szerviz számítási aránya határozza meg. Kiválaszthatja, hogy a szolgáltatás mennyiségének feladatok, a feladatok jelentett jó termék mennyisége vagy (a teljes mennyiséget tartalmazza a selejtezett termékek) teljes termékmennyiség alapján kiszámítja.  

Átviteli tevékenységek is definiálható alvállalkozásba. Ez a meghatározás esetén implicit módon a felelős fél számára a szállítás lehetőséget választja az átviteli tevékenységhez. Ha **szállítmányozó** vagy **címzett**, ha a megfelelő forrás vagy cél raktár raktár szállító által kezelt, a tevékenység tekinthető alvállalkozásba. Ha **fuvarozó**, a tevékenység mindig alvállalkozói. Alvállalkozói folyamat tevékenységek, mint a termelési folyamat aktiválása előtt egy átviteli alvállalkozói tevékenységet kell kapcsolni egy szolgáltatási szerződést.

### <a name="backflush-costing"></a>Visszavezetéses költségelszámolás

A Költségkönyvelés alvállalkozói munka teljesen integrálva van a lean gyártási oldat (visszavezetéses költségelszámolás) költségszámítás. A szerviz rendelés beszerzési elismervény könyvelésekor, illetve számlázása esetén a költséget a szerviz a termelési folyamathoz rendelt. Alvállalkozói szolgáltatások varianciája visszavezetéses költségelszámolás, a beérkezett és számlázott szerviz tényleges mennyiségeket a kapott termékek általános költsége alvállalkozói blokk kompenzálásával számítják.

## <a name="material-supply-for-subcontracted-operations"></a>Anyagellátási alvállalkozói műveletekhez
Félkész termékek és egyéb kapcsolódó anyagok át kell arra a helyre, ahol a munkát ténylegesen elvégzik. Alvállalkozói műveletek és tevékenységek használatakor az átvitel gyakran további szállítási szállító működtetett helyhez kapcsolódik. Alvállalkozói működéséhez az AJ anyag kiosztásával deklarálhatja, hogy az anyag az erőforráscsoport számára a hozzárendelt erőforrás a bemeneti helyen kell előkészíteni. Alaptervezés vagy majd lean feltöltési kiépítése az anyag erre a helyre.  

A készlet, amely a szállító telephelyén található minta, a szállító által kezelt raktári meghatározásához az iparág legjobb. A szállítói számlát hoz létre egy új raktári és könnyen adhatja meg a szállító által kezelt raktári. Ilyen anyagok dokumentálása át kell vinni a szállító egy művelet végrehajtása előtt, osztják fel a szállító által kezelt raktári az erőforráscsoportot, amely rendelkezik az erőforrás bemeneti raktárával.  

Feltöltéséhez szükséges anyag a raktárban, több stratégiák is használhatja:

-   Átmozgatási rendelések
-   Átmozgatási naplók
-   Kanban visszavonása
-   A szállító helyének közvetlen beszerzés

Félkész termékeket e szabály alól kivételt képeznek. Félkész termékek át, ezek a beállítások csak éppen:

-   Termelési és kötegrendelések félkész termékeket csak vihetők át logikailag a kitárolásilista-napló a segítségével a **munka alvállalkozásba** lista lap. Ennek a lapnak a használt félkész átadási szállítólevél dokumentum és a nyersanyag a szállítónak hoz létre.
-   A termelési folyamatok alvállalkozói műveletekhez félkész termékek átadásának dokumentálnia a szállító helyen visszavonása vagy termelési kanban kézhezvételét. Modellezésére kifejezett átviteli tevékenységet, egy további átviteli tevékenységgel termelési kanban leállítható.

**Megjegyzés:** A termelési útvonalon egyetlen gyártási rendeléshez nem idegen több hely. Ez a szabály vonatkozik az alvállalkozói munka is. Ezért a raktárak, amely képviseli a szállító által kezelt anyag helyeket meg kell határozni a belső erőforrások az útvonal használt ugyanazon a helyen. Termelési folyamatok áthaladhat a helyek, bár ezek nem egyik helyről a másikra, félkész termékek szállítási mert művelet költség környezet változását jelzi.  

Általában a kimeneti raktár és alvállalkozói erőforráscsoport helyét közvetlenül a raktári és helyét a következő lépés a művelet az útvonal vagy a termelési folyamat számára lefoglalt. Ez a beállítás segítségével csökkentheti a projekt jelentés, amely akkor fordul elő, vagy a szám további átviteli műveletek kell modellezni.


