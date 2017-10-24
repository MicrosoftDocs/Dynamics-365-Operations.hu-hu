---
title: "Termelési rendelések áttárolása kiszállítási területekbe"
description: "Ez a témakör leírja, hogyan kell kezelni az anyag áttárolásának folyamatát, amelyet egy gyártósorról befejezettnek jelentenek egy kimenő szállítási dokk felé."
author: johanhoffmann
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: AX 7.0.0, Operations, UnifiedOperations
ms.custom: 1705903
ms.assetid: 427e01b3-4968-4cff-9b85-1717530f72e4
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: a3f193b5b16406aa6ac3ed6a96f909318d100439
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="cross-docking-from-production-orders-to-outbound-docks"></a>Termelési rendelések áttárolása kiszállítási területekbe

Ez a témakör leírja, hogyan kell kezelni az anyag áttárolásának folyamatát, amelyet egy gyártósorról befejezettnek jelentenek egy kimenő szállítási dokk felé.

<a name="introduction"></a>Bevezetés
------------

A termelésből a kimenő helyre történő áttárolás fontos azoknál a gyártóknál, akik nagy mennyiséget termelnek, és ideális esetben a késztermékeket azonnal szeretnék szállítani, amint elkészülnek a gyártósorok. A cél az, hogy a termékeket olyan elosztóközpontokba szállítsák, amelyek fizikailag a vevői igényekhez közel helyezkednek el, ahelyett, hogy a készletet gyártási helyen halmoznák fel.

Abban az esetben, ha nincs azonnali kereslet egy termékre, azt el kell helyezni a raktárhelyiségekbe a gyártási helyszínen. Ezt a folyamatot *alkalmi áttárolásnak* is nevezik, ami azt jelenti, hogy a termék szállítási igény esetén, majd ehhez a lehetőséghez használandó helyett betárolásra szolgál a termék belső tárolására.

A következő példa három olyan változatot mutat be, amely a gyártósor végén (2) kezdődik.

A terméket a gyártási kimeneti helyre (3) késztermékként jelentik, és egy targoncakezelő felveszi a raklapot ezen a helyen (3).

-   Ha van tervezett tevékenység (6) a termék gyártóhely (1) és elosztó központ (7) közötti átvitelére, akkor a járművezetőt a rendszer irányítja arra, hogy a raklapot a megfelelő rakodóhelyre (4) helyezze el.
-   Ha a pótkocsi már hozzá van rendelve a rakodóhelyre, akkor a teherautó-vezető rakodja a terméket közvetlenül a pótkocsira.
-   Ha nincs tervezett tevékenység a termék átvitelére, akkor a targoncavezetőt arra irányítják, hogy a terméket a belső raktárba (5) helyezze el.

[![lehetőség szerinti áttárolás](./media/scenario1.png)](./media/scenario1.png)

## <a name="configure-cross-docking"></a>Áttárolás konfigurálása
Az áttárolási folyamatot **munkairányelvekkel** konfigurálhatja. A munkairányelv munkarendelés-típust, helyet és terméket foglal magában. A következő példában az áttárolás az X termékhez és az Y helyhez van beállítva.

#### <a name="work-order-types"></a>Munkarendelés típusai

-   Munkarendelés típusa: Késztermékek betárolása
-   Munka létrehozási módja: Áttárolás
-   Áttárolási irányelv neve: Átmozgatási rendelések

#### <a name="inventory-locations"></a>Készlethelyek

-   Raktár: 51
-   Tárolóhely: Y

#### <a name="products"></a>Termékek

-   Cikkszám: X

Az áttárolás jelenleg csak két munkarendelés-típushoz konfigurálható:

-   Késztermékek betárolása
-   Társ- és melléktermék betárolása

Az **áttárolási irányelvben** Ön határozza meg, hogy mely dokumentumtípusok használhatók az áttároláshoz. Jelenleg az egyetlen támogatott dokumentumtípus az **Átmozgatási rendelések**. Az alábbi példa az áttárolási irányelv konfigurációját mutatja be.

### <a name="cross-docking-policy-name-transfer-order"></a>Áttárolási irányelv neve: Átmozgatási rendelés

-   Sorszám: 10
-   Munkarendelés típusa: Átmozgatási probléma
-   Az áttárolási igényhez meg kell adni a helyet: Hamis
-   Párhuzamos áttárolási stratégia: dátuma és időpontja

### <a name="sequence-number"></a>Sorszám

A **sorszámú** az ilyen típusú dokumentumok prioritását jelzi. Az egyedüli támogatott dokumentumtípus jelenleg az **átmozgatási rendelések**. Emiatt a sorszám lesz megfelelő csak akkor áll rendelkezésre, ha több rendelést munkatípusok támogatottak.

### <a name="cross-docking-policy"></a>Áttárolási irányelv

Az áttárolási irányelv is beállítja a házirend az átmozgatási rendelés igény prioritásának a beállítására. Például ha több átmozgatási rendelés létezik ugyanarra a termékre, ütemezett dátuma és időpontja, a rakomány meg, és az átmozgatási rendeléshez társított, meghatározhatja a rangsor a rendelések között. Közvetlenül a rakományban ütemezett dátuma és időpontja is megadható, illetve állíthatók be egy **találkozó ütemezése**, amely a terhelés kapcsolódik. Az áttárolási stratégia a prioritás határozza meg. Jelenleg csak egy stratégia: **dátum és időpont**.

### <a name="cross-docking-demand-requires-location"></a>Az áttárolási igényhez meg kell adni a helyet.

Az áttárolási házirendben állíthat be egy feltételt megköveteli, hogy van-e átmozgatási rendelések egy hozzárendelt hely annak érdekében, hogy jogosult az áttárolási. Ennek a kritériumnak van megadva a **érintő áttárolási igény szükséges hely** mező. A hely a rakomány társított a találkozó ütemezése a végső helyeként szolgál az áruk, amelyeket áttárolt. Az áruk, amelyeket cross-rögzített végső helye határozza meg a helyutasítást **átmozgatási probléma** számára a **betárolási** Munkarendelés típusa. Akkor lehet hasznos beállítása a **érintő áttárolási igény szükséges hely** mezőjében egy esetet, ha az elkészült termékek kell érintő-rögzített csak akkor, ha a pótkocsi rakodórámpájához ajtó hozzá van rendelve. Ebben a forgatókönyvben az árukat a gyártósorból közvetlenül a pótkocsiba szállítják. Amikor pótkocsi van hozzárendelve a rakodóhely ajtajához, a felhasználó hozzárendeli a helyet a találkozó ütemtervéhez, és ezáltal megadja a helyet az áttároláshoz. Az alábbi lépések végigvezetik két példán.

#### <a name="scenario-1--cross-docking-from-production-to-transfer-orders"></a>1. forgatókönyv – Termelési rendelések áttárolása átadási rendelésekbe

Miután egy terméket a gyártósoron befejezettnek nyilvánítottak, áthelyezik egy rakodóhelyre, ahol azt egy tehergépkocsiba rakják és áthelyezik egy elosztóközpontba. Használja az USMF vállalatot.

1.  Engedélyezzen új számsorozatot az áttároláshoz. Ugrás a **Számsorozatok** oldalt, majd válassza ki a **létrehozása** gombra. A varázsló végigvezeti a folyamaton.
2.  Hozzon létre áttárolási irányelvet. Ugrás a **áttárolási irányelv párhuzamos** oldalt, majd hozzon létre egy új házirendet nevű **, az átmozgatási rendelés áttárolás**. Megjegyzés: csak munka rendelés típusa, amelyből választani lehet lehetőséget, hogy a program **átmozgatási probléma**, és a rendelkezésre álló csak áttárolási stratégia **dátuma és időpontja**.
3.  Hozzon létre munkairányelvet. Ugorjon a **Munkairányelvek** oldalra, majd hozzon létre egy új munkairányelvet: **Áttárolás L0101**.
4.  Állítson be rakományokat úgy, hogy automatikusan létrehozásra kerüljenek az átadási rendelések. A raktárparamétereknél állítson be rakományokat úgy, hogy automatikusan létrehozásra kerüljenek az átadási rendelések. A rakodás előfeltétele annak, hogy az átadási rendelés jogosult legyen az áttárolásra.
5.  Állítsa be a cikk–rakomány hozzárendelését. Lépjen a **Cikk–rakomány megfeleltetés** oldalra, majd állítsa be a szabványos rakománysablont a **CarAudio** cikkcsoportnál. Ez a leképezés automatikusan áthelyezi a terhelési sablont a terhelésre, amikor az átadási rendelés létrejön.
6.  Hozzon létre átmozgatási rendelést. Hozzon létre az L0101 tételszámú átadási rendelést. Mennyiség = 20.
7.  Oldja fel az átadási rendelést a terheléstervező munkaállomástól. A **Szállítás** lapon válassza ki a menüelemet, a rakomány tervezési munkaterület és a, a **Kiadás** menüben a rakománysornál válassza a **Raktárba való kiadás** lehetőséget. Az átmozgatási rendelésben jelenleg létezik egy **Átmozgatási probléma** típusú nyitott hullámvonal.
8.  Termelési rendelés létrehozása. Lépjen a **Termelési rendelés** listaoldalt, és hozzon létre egy gyártási rendelést az L0101 termékhez. Mennyiség = 20. A termelési rendelés becsült ideje és indulása. A **Kitárolási lista feladása** mező beállítása továbbra is **Nem**.
9.  Készként jelentés a mobileszközről. Menjen a mobileszköz-portálra, és válassza ki a **Készként jelentés és betárolás** menüpontot. Most jelentse készként az L0101 cikkszámot a kézben tartott eszközről. Ne feledje, hogy a helyszín a **BAYDOOR**. Ezt a helyet az **Átmozgatási probléma** helymeghatározási irányelvnél találhatja az **Eltárolás** munkarendeléshez. Vegye figyelembe, hogy az **Átmozgatási probléma** típusú munkát létrehozták és befejezték. Lépjen az átmozgatási rendelés munkarészleteihez a munka ellenőrzéséhez.
10. Most próbáljon 20-szor többet elindítani a termelési rendelésben, majd próbáljon meg jelenteni 20-at a kézben tartott eszköz használatával. Ezúttal az **LP-001** helyszín javasolt eltárolási helyszínként. Ezt a helyet a helymeghatározási irányelvnél találhatja a **Késztermékek betárolása** lehetőségnél. Ezt a helymeghatározási irányelvet használják, mert nincs áttárolási lehetőség. Az LP-001 átadási rendelést teljes mértékben teljesítette az első áttárolási tevékenység.

Létrejött és feldolgozásra került a **Késztermékek betárolása** funkció.

#### <a name="scenario-2---cross-docking-from-production-to-transfer-orders-with-an-appointment-schedule"></a>2. forgatókönyv – Termelési rendelések áttárolása átadási rendelésekbe találkozási ütemtervvel

Miután egy terméket a gyártósoron befejezettnek nyilvánítottak, áthelyezik egy rakodóhelyre, amelyet a rakodóhelyek kijelölési ütemterve határoz meg. Használja az USMF vállalatot.

1.  Módosítsa az áttárolási irányelvet. Módosítsa az 1. forgatókönyvben létrehozott áttárolási irányelvet **Az áttárolási igényhez meg kell adni a helyet.** jelölőnégyzet bejelölésével.
2.  Hozzon létre új átadási rendelést.
3.  Nyissa meg a **Rakománytervezési munkaterületet**.
4.  A rakománytervezési munkaterületről lépj a **Rakományok** szakaszhoz, és válassza ki a **Találkozó ütemezése** lehetőséget a **Szállítás** menüben egy új találkozóütemezés létrehozásához. Ne feledje, hogy a találkozási ütemterv hivatkozik az átmozgatási rendelésre a **Rendelés száma** mezőben. A **Tervezett kezdő dátum és idő adott helyen** mezőben beállíthatja a megbeszélés dátumát és idejét. Ezt a dátumot és időt fogják használni, ha az áttárolási igényt az áttárolási folyamat során kiemelték. Az ezen a területen beállított dátum és idő frissíti a **Rakomány indításának ütemezett dátuma és időpontja** mezőt a kapcsolódó rakománynál. A **Szállítás részletei** gyorslap meghatározza az átmozgatási rendelés helyét.
5.  A **Rakománytervező munkaterületen** adja ki a raktárnak.
6.  Hozzon létre egy gyártási rendelést az **L0101** cikkszámhoz, és állítsa az állapotot **Elindítva** értékre, 20-as mennyiséggel.
7.  Készként jelentés a mobileszközről.
8.  Menjen a mobileszköz-portálra, és válassza ki a **Készként jelentés és betárolás** menüelemet.
9.  Jelentse készként az **L0101** cikkszámot a kézben tartott eszközről. Ne feledje, hogy a helyszín a **BAYDOOR 2**. Ezt a helyet a találkozási ütemterv alapján találja meg az **Átmozgatási bevételezés** helymeghatározási irányelv helyett.

### <a name="additional-information"></a>További információk

-   Az áttárolási forgatókönyv támogatott a kötegelt és sorozatosan vezérelt cikkeknél, mind a köteg-, mind a sorozatszám-dimenziókkal, amelyeket a foglalási hierarchiában fent és alul találhat meg.



