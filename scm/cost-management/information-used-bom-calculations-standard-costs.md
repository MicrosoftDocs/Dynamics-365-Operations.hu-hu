---
title: "Elszámolóáras anyagjegyzék-számítások"
description: 
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: BOMCalcDialog, BOMCalcGroup, BOMCalcTable, ProdParmBOMCalc
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 65571
ms.assetid: ca17e6dd-b16a-4bbc-8682-b16345ab9906
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: deeecd478febe0afc45b90f7d962e955af46210f
ms.lasthandoff: 03/31/2017


---

# <a name="bom-calculations-with-standard-costs"></a>Elszámolóáras anyagjegyzék-számítások

[!include[banner](../includes/banner.md)]




Az elszámolóár anyagjegyzék-számításánál a beszerzett cikkre vonatkozóan felhasznált információk közé tartoznak a következők:
-   Költség – a beszerzett cikk költségeit helyspecifikus költségrekordként tartja karban a rendszer az elszámolóárhoz tartozó költségszámítási verzióban. Mindegyik költségrekordhoz tartozik egy érvényességi dátum, és az anyagjegyzék-számítás dátuma határozza meg, hogy melyik költségrekordot használja fel. Például jövőbeli számítási dátummal rendelkező anyagjegyzék-számítás felhasználhat egy függő állapotú és jövőbeli érvényességi dátummal rendelkező költségrekordot.
-   Költségcsoport – a beszerzett cikkhez hozzárendelt költségcsoport jelenti a legyártott cikk számított költségeinél a költségszegmentáció alapját.
-   A cikk Anyagjegyzék számítási csoportjába beágyazott figyelmeztetési feltételek által lehetővé válik, hogy Anyagjegyzék-számítás azonosítani tudja a potenciális problémákat. Ez akkor lehet, ha a beszerzett cikk nulla költséggel, az Anyagjegyzékben szereplő nulla mennyiséggel , vagy lejárt dátumú költségrekorddal rendelkezik. A megfelelő figyelmeztetési feltétek anyagjegyzék-számítás indításakor felülbírálhatók.

Az elszámolóár anyagjegyzék-számításánál a legyártott cikkre vonatkozóan felhasznált információk közé tartoznak a következők:
-   A készlet szokásos rendelési mennyiség – a készlet cikkének szokásos rendelési mennyisége az anyagjegyzék-számításokban az állandó költségek leírásánának alapértelmezett könyvelési adagméreteként viselkedik. A könyvelési adagméret azt is tükrözi a megrendelési mennyiség többszörösét, ha meg van adva.
-   A cikk Anyagjegyzék számítási csoportjába beágyazott figyelmeztetési feltételek által lehetővé válik, hogy Anyagjegyzék-számítás azonosítani tudja a potenciális problémákat. Például lehet, hogy a gyártott cikkhez nem tartozik Anyagjegyzék vagy útvonal. A megfelelő figyelmeztetési feltétek anyagjegyzék-számítás indításakor felülbírálhatók.

Az elszámolóár anyagjegyzék-számításánál a felhasznált anyagjegyzék-információk közé tartoznak a következők:
-   Anyagjegyzék-verzió – a legyártott cikkhez hozzárendelt anyagjegyzék-verzióhoz kezdő és záró érvényességi dátum, valamint jóváhagyott és aktív állapot tartozik. Az anyagjegyzék verziója lehet egész vállalatra érvényes vagy helyspecifikus, és mennyiségi töréspontokat is tükrözhet.
-   Anyagjegyzéksor cikkmennyisége – rendszerint az egy összetevő szükséges mennyisége változó, de lehet állandó is. Az összetevő mennyisége rendszerint egy szülőcikk előállításához van meghatározva, de megadható 100-as vagy 1000-es mennyiséghez is, hogy kiküszöbölhetők legyenek a tizedesvesszőből adódó kerekítési problémák. Az összetevő mennyisége mérések alapján is számítható.
-   Anyagjegyzéksor cikkselejtje – az összetevőkhöz tartozhat változó vagy állandó mennyiségű tervezett selejt.
-   Anyagjegyzéksor cikkéhez tartozó érvényességi dátumok – az összetevőhöz kezdő és záró érvényességi dátum tartozhat.
-   Anyagjegyzéksor termeléstípusa – az állandó költségek leírásához használt költségszámítási adagméret tükrözi az anyagjegyzék-számítási mennyiséget és a rendelésre készített alábontási módot, mivel az anyagjegyzék-számítás feltételezi, hogy a legyártott összetevő pontos mennyiségben és nem a normál rendelési mennyiségben készül.
-   Részanyagjegyzék legyártott összetevőhöz – a legyártott összetevőhöz tartozhat megadott anyagjegyzék-verzió, amelyet ebben az esetben az anyagjegyzék-számítás a cikk aktuálisan aktív anyagjegyzék-verziója helyett használ.
-   Részútvonal legyártott összetevőhöz – a legyártott összetevőhöz tartozhat megadott útvonalverzió, amelyet ebben az esetben az anyagjegyzék-számítás a cikk aktuálisan aktív útvonalverziója helyett használ.
-   Műveleti szám és a művelet selejtszázalékainak hatása – a műveleti szám az összetevőt egy adott művelethez kapcsolja hozzá, a műveletekhez pedig tartozhat egy selejtszázalék. Ez a kapcsolat teszi lehetővé, hogy az anyagjegyzék-számítás elszámolja a selejtszázalékokat és a halmozott selejtszázalékokat az összetevő által megkövetelt mennyiségben.
-   Anyagjegyzéksor kihagyása költségszámításnál – az anyagjegyzék-számítás szempontjából figyelmen kívül hagyható egy összetevő.

A szokásos költség anyagjegyzék-számításnál használt üzemi erőforrás információk a következők:
-   Egy órára eső költség – az üzemi erőforráshoz társított óránkénti költség a helyhez társított óránkénti költség a beállítási időhöz és a futási időhöz rendelt költségkategóriáként van kifejezve. Ezeket a költségkategóriákat kell meghatározni az erőforrás csoportokhoz és üzemi erőforrásokhoz. Az egy költségkategóriához társított óránkénti költségek lehetnek helyspecifikusak vagy az egész vállalatra vonatkozóak is.
-   Egységenkénti költségek – bizonyos gyártási környezetek hozzárendelik a kimeneti egységenkénti üzemi erőforrásköltségeket, amelyek a mennyiséghez kapcsolódó más költségkategóriaként fejezhetők ki. Például a mennyiséghez kapcsolódó költségek kifejezhetik a munkához kapcsolódó darabköltséget, vagy például festékgyártó kimenő literenként határozhatja meg az üzemi erőforrások költségeit.
-   Üzemi erőforrás információk felülbírálása útvonaltervezés műveletek esetében – a költségkategóriákra vonatkozó erőforrás-információkat a műveletek öröklik, ahol felül is bírálhatók. Az anyagjegyzék-számítások az útvonalműveletekhez megadott költségkategória-információkat használják.
-   Költségkategóriához tartozó költségcsoport – a költségkategóriához hozzárendelt költségcsoport költségszegmentációt tesz lehetővé a legyártott cikk számított költségeinél. Különböző költségcsoportokat lehet például használni a gépekhez és a munkához, illetve a beállításhoz és futási időhöz társított számított költségek szegmentálására.

Az elszámolóár anyagjegyzék-számításánál az útvonalra vonatkozóan felhasznált információk közé tartoznak a következők:
-   Útvonal-verzió – a legyártott cikkhez hozzárendelt útvonal-verzióhoz kezdő és záró érvényességi dátum, valamint jóváhagyott és aktív állapot tartozik. Az útvonal verziója mindenképpen helyspecifikus, és mennyiségi töréspontokat is tükrözhet.
-   Útvonalművelet ideje – az idő a futási időhöz és a beállítási időhöz lehet meghatározva. Az óránkénti idő rendszerint egy szülőcikk előállításához van meghatározva, de megadható 100-as vagy 1000-es mennyiséghez is, hogy kiküszöbölhetők legyenek a tizedesvesszőből adódó kerekítési problémák.
-   Útvonaltervezés művelet ideje másodlagos erőforrásokra vonatkozóan – egy másodlagos erőforrás ugynazon műveleti számmal rendelkezik mint az elsődleges erőforrás, és ugyanaz az útvonaltervezési műveleti idő tartozik hozzá. Egy művelethez például szükséges lehet elsődleges erőforrásként egy gép, másodlagos erőforrásként pedig a munka és az eszközök.
-   Az útvonaltervezési műveleti selejtszázalék - Az anyagjehgyzék számítás számolja a selejtszázalkokat és a halmozott selejtszázalékokat többszöri művelet által. Ez az útvonaltervezési műveletekhez szükséges időre és a műveleti számokhoz kapcsolt összetevők szükséges mennyiségére vonatkozik.
-   Az útvonaltervezési műveletekre vonatkozó költségkategóriák – A költségkategóriákra vonatkozó üzemi erőforrás-információkat a műveletek öröklik, ahol felül is bírálhatók. Az anyagjegyzék-számítások az útvonalműveletekhez megadott költségkategória-információkat használják.

Az elszámolóár anyagjegyzék-számításánál a gyártási többletköltségre vonatkozóan felhasznált információk közé tartoznak a következők:
-   Pótdíj – a pótdíjszámítási képlet egy olyan százalékos értéket – például 100 százalék – tükröz, amely konkrét költségcsoporthoz – például az élőmunkához – van hozzákapcsolva.
-   Díj – a díjszámítási képlet egységenkénti összeget – például 10,000 USD/óra – tükröz, amely konkrét költségcsoporthoz – például az élőmunkához – van hozzákapcsolva.
-   Idő alapú/anyag alapú többletköltség – a gyártási többletköltséget útvonalműveletekhez vagy anyagösszetevőkhöz lehet hozzákapcsolni.

Az elszámolóár anyagjegyzék-számításánál a költségszámítási verzióra vonatkozóan felhasznált információk közé tartoznak a következők:
-   Költségszámítás típusa – a költségszámítási verziónak elszámolóárakat kell tartalmaznia. Az elszámolóárakat alkalmazó anyagjegyzék-számításokra számos megkötés vonatkozik. Például ilyen korlátozások szabják meg, hogy az egységköltségekben szerepelnie kell a vegyes költségnek, és hogy az anyagjegyzék-számításnak egyszintű alábontást kell alkalmaznia.
-   Elrendelt tartalékelv – a költségszámítási verzió elrendelheti a tartalékelv használatát, például meghatározott költség verziók vagy aktív költségi rekordok használatával. Az előírt tartalékelv rendszerint egy költségszámítási verzióra vonatkozik, amely kifejezi a növekményes frissítéseket a költség frissitések kétverziós megközelítésében.
-   Függő költségek zárolási jelzői – a zárolási jelző megakadályozhatja a legyártott cikkekhez tartozó függő költségeken végrehajtott anyagjegyzék-számítást.
-   Megadott kezdő dátum – a megadott kezdő dátum a költségszámítási verziót érintő összes anyagjegyzék-számítás alapértelmezett számítási dátumaként működik.
-   Megadott hely – a megadott hely az anyagjegyzék-számításokat az adott helyre korlátozza.
-   A költségszámítási verziónak költségeket kell tartalmaznia – a tartalomban mindenképpen szerepelnie kell a költségeknek. Választható módon szerepelhetnek az értékesítési árak is, hogy a legyártott cikkekhez számíthatóak legyenek a javasolt értékesítési árak.

Anyagjegyzék-számítás indításakor többféle információforrást lehet megadni. Ilyen a hely, a számítási dátum és a költségszámítási verzió is.






