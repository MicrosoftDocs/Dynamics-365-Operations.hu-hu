---
title: "Gyártás területén végzett alvállalkozói munka kezelése"
description: "Ez a témakör bemutatja, hogyan kezeli a Microsoft Dynamics 365 for Operations az alvállalkozói műveleteket. Más szóval bemutatja, hogyan kezeli azon gyártási műveleteket, amelyek szállító által kezelt erőforráshoz vannak kiosztva."
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

# <a name="manage-subcontracting-work-in-production"></a>Gyártás területén végzett alvállalkozói munka kezelése

[!include[banner](../includes/banner.md)]


Ez a témakör bemutatja, hogyan kezeli a Microsoft Dynamics 365 for Operations az alvállalkozói műveleteket. Más szóval bemutatja, hogyan kezeli azon gyártási műveleteket, amelyek szállító által kezelt erőforráshoz vannak kiosztva.

A [termelési folyamatokban](production-process-overview.md) munkát azon erőforrások végezhetnek, amelyek tulajdonosa vagy kezelője egy szállító. Általában az olyan időszakos kiemelkedő kereslet kielégítésére használnak szállító típusú erőforrásokat, amely meghaladja a vállalat saját forrásainak rendelkezésre álló kapacitásait. A szállító emellett konkrét [erőforrásképességeket](resource-capabilities.md), illetve alacsonyabb árú erőforrásokat is kínálhat.  

A termelési folyamatban felhasznált szállítói erőforrásoktól függően az [útvonal](routes-operations.md) gyakran további logisztikai követelményeet támaszt, mivel az anyagokat és félkész termékeket először el kell szállítani a szállító telephelyére. Az alvállalkozásba adott művelet eredményét pedig aztán el kell szállítani vagy a következő művelet helyére, vagy a késztermékek raktárába.  

Alvállalkozói műveletek vagy tevékenységek használata esetén ezek a műveletek minden szakaszára hatással vannak a gyártás, költségszámítás, előrejelzés, tervezés és ütemezés során használt műveletek meghatározásától az anyagok, félkész termékek és késztermékek logisztikájának kezeléséig. Végül ezek az erőforrások saját folyamatokat igényelnek a könyvelés és költségellenőrzés terén.  

Belső erőforrásoknál adott időtartamhoz általában fix költségszorzó tartozik. Ezzel szemben alvállalkozói erőforrásoknál a költség a kapcsolódó szolgáltatás beszerzési árán alapul. A szolgáltatás meghatározás szerint egy másik terméket jelent, melynek célja a beszerzési és vásárlási folyamatok előmozdítása egy adott alvállalkozói művelet kapcsán.  

Jelenleg a Microsoft Dynamics 365 for Operationsben nincs kifejezett félkésztermék-fogalom. Olyan termelési rendelésnél, amely egynél több műveletet igényel annak érdekében, hogy a nyersanyagokat késztermékekké alakítsa át, a késztermék csak az utolsó műveletet során kerül vissza a készletbe. A korábbi műveletek során előállított félkész termékek elszámolása befejezetlen termelés formájában történik, ezeket viszont nem könyveljük és nem követjük a készletben. Bár az útvonalak és anyagjegyzékek (AJ) feloszthatók több kisebb egységre, ez a megközelítés növeli a kezelendő termékek, anyagjegyzékek és útvonalak számát.  

A gyártási műveletek során igénybe vett alvállalkozói munka modellezésének két módja van. Ezek a módszerek az alvállalkozásba adási folyamatot, a félkész termékek megjelenítését a folyamatban, valamint a költségellenőrzést eltérő módon modellezik.

-   Útvonalműveletek alvállalkozásba adása termelési rendelések, illetve kötegrendelések esetén
    -   A szolgáltatási terméknek raktározott terméknek kell lennie, és az AJ részét kell képeznie.
    -   Ezt a módszer az először be, először ki (FIFO) vagy elszámolóár elvet támogatja.
    -   A félkész termékeket a folyamatban a szolgáltatási termék képviseli.
    -   A költségkontroll az alvállalkozói munkához társított költségeket az anyagköltségekhez kapcsolja.
-   Termelési folyamat tevékenységeinek alvállalkozásba adásba lean termelési folyamatban
    -   A szolgáltatás nem készletezett szolgáltatási termék, és nem része az AJ-nek.
    -   Ez a módszer beszerzési szerződéseket használ szolgáltatási szerződéseket.
    -   Ez a módszer visszavezetéses költségelszámolást használ.
    -   Ez a módszer lehetővé teszi az összesített és aszinkron beszerzést. (Az anyagáram független a beszerzési folyamattól.)
    -   A költségkontroll az alvállalkozói munkát saját költségrészletezési blokkjába sorolja be.

## <a name="subcontracting-of-route-operations"></a>Útvonalműveletek alvállalkozásba adása
Útvonalműveletek alvállalkozásba adása gyártásnál vagy kötegrendeléseknél úgy történhet, hogy a szolgáltatás beszerzésére szolgáló szolgáltatási terméket, **Szolgáltatási** típusú termékként kell meghatározni. Ezenkívül rendelkeznie kell olyan cikkmodellcsoporttal, amelynél a **Raktározott termék** beállítás a **Készletházirendben** **Igen** értékre van állítva. Ez a beállítás határozza meg, hogy egy termék elszámolása készletként történik-e a termék átvételekor (**Raktározott termék** = **Igen**), vagy hogy a termék kiadásként van-e könyvelve egy eredményszámlán (**Raktározott termék** = **nem**). Bár ez a viselkedés ellentmondásosnak tűnhet, azon alapszik, hogy csak az ehhez a házirendhez tartozó termékeknél jön létre olyan készlettranzakció, amely felhasználható a költségkontrollban a tervezett költség kiszámítására és a tényleges költség meghatározására akkor, amikor a gyártási rendelés lezárul.  

Tervezésbe és költségszámításba a szolgáltatás akkor kerülhet be, ha hozzá van adva az AJ-hez. Az AJ-sornak **Szállító** típusúnak kell lennie, és ahhoz az útvonalművelhez kell tartoznia, amelyhez a szolgáltatás tartozik. Az útvonalműveletnek rendelkeznie kell költségszámítási erőforrással és olyan erőforráskövetelménnyel, amely egy olyan, **Szállító** típusú erőforrásra mutat, amely összeköti a műveletet és a kapcsolódó szolgáltatást a megfelelő szállítói számlával.  

E konfiguráció használata esetén beszerzési rendelés jön létre a kapcsolódó szolgáltatási termékhez a termelési rendelés becslése alapján. A szolgáltatás beszerzési rendelése szolgál az alvállalkozói műveletek horgonyaként. Az alvállalkozói munka a Gyártásvezérlés **Alvállalkozói munka** listaoldaláról kezelhető. Az alvállalkozói munka használatos a nyersanyag és végül a félkész termék a szállítóhoz történő elszállítására a művelet előkészítése során. Szintén használjuk az alvállalkozásba adott művelet eredményéül kapott termék fogadására a cikkérkeztetés során, ahol a szolgáltatási termék szolgál a félkész termék megérkezésének azonosítására. Amikor a beszerzésirendelés-sor beérkezik, a termelési művelet befejezett állapotúra frissül.  

Egy termelési rendeléshez számos művelet tartozhat, és minden egyes művelet különböző szállítóhoz lehet hozzárendelhető. Ezért egy végpontok közötti termelési rendelés számos beszerzési rendelést is kiválthat.

## <a name="subcontracting-of-production-flow-activities"></a>Termelési folyamat tevékenységeinek alvállalkozásba adása
A [lean manufacturing](lean-manufacturing-overview.md) megoldási modellekben az alvállalkozói munka egy [termelési folyamat](http://ax.help.dynamics.com/en/wiki/create-a-production-flow-version/) (Feladat-útmutató témaköre) egy tevékenységhez kapcsolódó szolgáltatásként modelleződik. Ezért az ilyen típusú alvállalkozásba adást [tevékenységi alapú alvállalkozásba adásnak is nevezzük](activity-based-subcontracting.md) Egy speciális költségcsoporttípus, a **Közvetlen kiszervezés** került bevezetésre, a vezetett, az alvállalkozói szolgáltatások pedig már nem tartoznak bele a késztermékek anyagjegyzékébe (AJ). Lean manufacturing használatakor minden olyan tevékenység meghatározása kanbannal történik, amely összefüggésben lehet egy vagy több termelési folyamat tevékenységeivel. Eddig a magyarázat ugyanúgy hangzik, mint a termelési rendelések magyarázata. A termelési rendeléseknek viszont mindig késztermékkel kell végződniük, félkész termékek biztosításához kanban hozható létre. Nem kell bevezetni új terméket és AJ-szintet.  

Mivel a kanbanszabályok nagyon dinamikusak lehetnek, a termelési folyamatban ugyanarra a termékre vonatkozóan különböző ellátási változatok modellezhetők. Lean alvállalkozásba adás használatakor az anyagáram és pénzügyi áramlását szigorúan elválnak egymástól. Minden anyagáramot kanbantevékenységek jelölnek. A szolgáltatási termékekre vonatkozó beszerzési rendelések és ezen szolgáltatások beérkezésének könyvelése automatizálható a termelési folyamatban található kanbanfeladatok állapota alapján. Kanbanfeladatok elindíthatók befejezhetők akár a beszerzési rendelések létrehozása előtt is. Az alvállalkozói dokumentumok (a szolgáltatás beszerzési rendelése és beszerzési elismervénye) időszak és szolgáltatás szerint összesíthetők. Ezért a beszerzési bizonylatok és sorok száma nagyon alacsonyan tartható még az olyan, nagy számban ismétlődő műveletek esetén is, amelyeknél a szállítók egységes folyamat formájában biztosítanak alvállalkozói szolgáltatásokat.

### <a name="modeling-subcontracting-in-a-production-flow"></a>Alvállalkozásba adás modellezése termelési folyamatban

[Lean típusú termelési folyamatban](lean-manufacturing-modeling-lean-organization.md) a folyamattevékenység akkor határozható meg alvállalkozóiként, ha olyan munkacellához (erőforráscsoporthoz) van hozzárendelve, amelyhez egyetlen szállítói erőforrás tartozik. Munkacella alvállalkozásba adása során a kapcsolódó folyamattevékenységeknek olyan aktív beszerzési szerződési sorhoz kell kapcsolódniuk, amely tartalmazza a szolgáltatási tételt és a szolgáltatás árát. A tevékenység szolgáltatási szerződése emellett meghatározza a termék mennyisége és a kanbanfeladat közti számítási arányt és az eredményül kapott szolgáltatási mennyiséget. Kiválaszthatja, hogy a szolgáltatás mennyiségének kiszámítása a feladatok száma, a feladatokban jelentett jó termékek mennyisége vagy a teljes termékmennyiség (ez a teljes mennyiség a selejtezett termékeket is tartalmazza) alapján történjen-e.  

Az átviteli tevékenységek szintén meghatározhatók alvállalkozásiként. Ez a meghatározás implicit módon történik, amikor az átviteli tevékenységben kiválasztja szállításért felelős felet. Amikor a **Szállítmányozó** vagy **Címzett** lehetőséget választja, ha a kapcsolódó forrás- vagy célraktárat szállító kezeli, a tevékenység alvállalkozásba adottnak minősül. Amikor a **Fuvarozó** elemet választja, a tevékenység mindig alvállalkozásba adottnak minősül. Az alvállalkozói folyamattevékenységekhez hasonlóan az alvállalkozásba adott átviteli tevékenységeknek is szolgáltatási szerződéshez kell kapcsolódniuk a termelési folyamat aktiválása előtt.

### <a name="backflush-costing"></a>Visszavezetéses költségelszámolás

Az alvállalkozói munkák költségkönyvelése teljesen integrálva van a lean manufacturing költségszámítási megoldásába (visszavezetéses költségelszámolás). Amikor a termék beszerzési rendelésének bevételezése feladásra kerül, illetve számlázáskor, a szolgáltatás költségét a rendszer a termelési folyamathoz rendeli. Visszavezetéses költségelszámolásnál az alvállalkozói szolgáltatások eltérésének kiszámítása a kapott termékek általános költsége alvállalkozói blokkjának a ténylegesen megkapott és kiszámlázott szolgáltatási mennyiségekkel szembeni elszámolásával történik.

## <a name="material-supply-for-subcontracted-operations"></a>Anyagellátás alvállalkozói műveleteknél
A félkész termékeket és egyéb kapcsolódó anyagokat át kell szállítani arra a helyre, ahol a munkát ténylegesen elvégzik. Alvállalkozói műveletek és tevékenységek használatakor ez az átvitel gyakran a szállító által működtetett telephelyre történő egyéb szállításhoz kapcsolódik. Ha az anyagot az AJ-ben az alvállalkozói művelethez kapcsolja, azzal kijelenti, hogy az anyagot elő kell készíteni a hozzárendelt erőforrás erőforráscsoportjának bemeneti helyén. Az alaptervezés vagy lean feltöltés ekkor az anyagot az érintett helyre biztosítja.  

A szállító telephelyén található készlet modellezésére az iparág legjobb gyakorlata egy a szállító által kezelt raktár meghatározása. Szállító által kezelt raktárat könnyen megadhat úgy, ha létrehoz egy új raktárat, és a szállítói számlához rendeli. Annak dokumentálására, hogy az anyagokat el kell juttatni a szállítóhoz a műveletek végrehajtása előtt, a szállító által kezelt raktárat az erőforrással rendelkező erőforráscsoport bemeneti raktárához kell hozzárendelni.  

A raktárban lévő anyagok feltöltéséhez több stratégia is használható:

-   Átmozgatási rendelések
-   Átmozgatási naplók
-   Visszavonási kanbanok
-   Közvetlen beszerzés a szállító helyére

A félkész termékek e szabály alól kivételt képeznek. Félkész termékek átviteléhez a csak következő lehetőségek érhetők el:

-   Termelési és kötegrendeléseknél a félkész termékek csak logikailag vihetők át az **Alvállalkozói munka** listalapon található kitárolásilista-napló segítségével. Ez a napló szállítólevél dokumentumot hoz létre, amely használható a félkész termék és nyersanyag a szállítóhoz való átvitelére.
-   Termelési folyamatok alvállalkozói műveleteinél a félkész termékek átvitelének dokumentálása visszavonási vagy termelési kanbanok kézhezvételével történik a szállító helyén. Kifejezett átviteli tevékenység modellezésére termelési kanban egy további átviteli tevékenységgel lezárható.

**Megjegyzés:** egyetlen termelési rendelés termelési útvonala nem érinthet több telehelyet. Ez a szabály az alvállalkozói munkákra is vonatkozik. Ezért a szállító által kezelt anyaghelyeket képviselő raktárakat ugyanazon telephelyen kell meghatározni, mint az útvonalon használt belső erőforrások helye. Bár a termelési folyamatok több telephelyen áthaladhatnak, félkész termékeket ezek nem szállíthatnak egyik telephelyről a másikra, mert ez a művelet a költségkörnyezet változását feltételezné.  

Általában a kimeneti raktár és alvállalkozói erőforráscsoport helye közvetlenül az útvonal vagy a termelési folyamat következő lépésének raktárához és helyéhez van hozzárendelve. E beállítás segítségével csökkentheti a jelentendő feladatok mennyiségét, illetve a modellezendő további átviteli műveletek számát.




