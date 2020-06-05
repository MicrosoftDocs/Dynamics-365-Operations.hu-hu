---
title: Kimenő készletművelet a pénztárban
description: Ez a témakör a pénztár (POS) kimenő készletműveletének képességeit írja le.
author: hhaines
manager: annbe
ms.date: 05/14/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: hhaines
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: 22f057c20898bb4b4c34e38d62313d2634a33511
ms.sourcegitcommit: 3b6fc5845ea2a0de3db19305c03d61fc74f4e0d4
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/18/2020
ms.locfileid: "3384129"
---
# <a name="outbound-inventory-operation-in-pos"></a>Kimenő készletművelet a pénztárban

[!include [banner](includes/banner.md)]


A Microsoft Dynamics 365 Commerce 10.0.10 és a későbbi verzióiban a bejövő és kimenő műveletek a pénztárnál (POS) lecserélik a kitárolási és bevételezési műveleteket.

> [!NOTE]
> A 10.0.10 és a későbbi verziókban a POS-alkalmazás olyan új szolgáltatásai, amelyek a beszerzési rendelések és átmozgatási rendelések fogadásával kapcsolatosak a bejövő műveletek művelethez lesznek hozzáadva. Ha jelenleg a kitárolási és bevételezési műveletet használja a pénztárban, javasoljuk, hogy dolgozzon ki egy stratégiát arra, hogy ebből a műveletből a bejövő és kimenő műveletekbe költözzön. Annak ellenére, hogy a kitárolási és bevételezési művelet nem lesz eltávolítva a termékből, a 10.0.9 verzió után funkcionális és teljesítményi szempontból nem érkeznek hozzá újítások.

## <a name="prerequisite-configure-an-asynchronous-document-framework"></a>Előfeltétel: Az aszinkron dokumentumkezelési keretrendszer konfigurálása

A kimenő művelet javítja a teljesítményt, így biztosítható, hogy azok a felhasználók, akik nagy mennyiségű bevételezést adnak fel számos üzlet vagy vállalat között, illetve nagy készletdokumentumokkal dolgoznak úgy dolgozhassák fel ezeket a dokumentumokat a Commerce Headquarters felületen, hogy ne ütközzenek időtúllépésekbe vagy hibákba. Ezek a fejlesztések egy aszinkron dokumentum keretrendszer használatát igénylik.

Az aszinkron dokumentumok keretrendszerének használatakor véglegesítheti a kimenő dokumentumok változásait a pénztár és a Commerce Headquarters között, majd áthelyezheti azokat más feladatokra, miközben a feldolgozás a Commerce Headquarters modulban a háttérben történik. A dokumentum állapota a **Kimenő műveletek** dokumentum listaoldalon ellenőrizhető a pénztárban, hogy meggyőződhessen a sikeres feladásról. APénztár alkalmazásban a kimenő művelet aktív dokumentum-listája használható a Commerce Headquarters rendszerbe nem feladott dokumentumok megjelenítésére is. Ha egy dokumentum feladása nem sikerül, a POS-felhasználók korrigálni tudják, majd újra megpróbálkoznak a Commerce Headquarters rendszerben történő feldolgozással.

> [!IMPORTANT]
> Az aszinkron dokumentum keretrendszert azelőtt kell konfigurálni, mielőtt a vállalat megpróbálja használni a kimenő műveletet a pénztárban.

Az aszinkron dokumentum-keretrendszer konfigurálásához hajtsa végre a következő eljárásokat.

### <a name="create-and-configure-a-number-sequence"></a>Hozzon létre, és konfiguráljon egy számsorozatot

1. Válassza a **Szervezeti adminisztráció \> Számsorozatok \> Számsorozatok** lehetőséget.
2. A **Számsorozatok** lapon hozzon létre egy új számsorozatot.
3. A **Számsorozat kódja** és a **Név** mezőben adja meg a felhasználó által definiált értékeket.
4. Válassza a **Referenciák** gyorslap **Hozzáadás** elemét.
5. A **Terült** rész mezőjében válassza a **Commerce paraméterek** gombot.
6. A **Referencia** mezőben válassza ki a **Kiskereskedelmi dokumentum műveleti azonosítója** lehetőséget.
7. Az **Általános** gyorslap **Beállítások** szakaszában állítsa a **Folyamatos** elemet **Nem** értékre, így biztosíthatja, hogy ne legyenek teljesítménnyel kapcsolatos problémák.

### <a name="create-and-schedule-two-batch-jobs-for-the-document-processing-and-monitoring-tasks"></a>Hozzon létre két kötegelt feladatot a dokumentumok feldolgozási és felügyeleti feladatai számára

A létrehozott kötegelt feladatok felhasználhatók a meghiúsult vagy időtúllépésben érintett dokumentumok feldolgozására. Akkor is használhatók, ha a pénztárból eldolgozás alatt álló aktív készletdokumentumok száma meghaladja a rendszer által konfigurált értéket.

1. Ugorjon a **Rendszerfelügyelet \> Lekérdezések \> Kötegelt feladatok** pontra.
2. A **Kötegelt feladat** lapon hozzon létre két kötegelt feladatot:

    - Egy feladatot konfiguráljon a **RetailDocumentOperationMonitorBatch** osztály futtatására.
    - A másik feladatot konfigurálja a **RetailDocumentOperationProcessingBatch** osztály futtatására.

3. Az új kötegelt feladatok ismétlődő futtatását ütemezze. Az ütemezést például állítsa be úgy, hogy a feladatok öt percenként fussanak.

## <a name="prerequisite-add-outbound-operation-to-the-pos-screen-layout"></a>Előfeltétel: Kimenő művelet hozzáadása a pénztár képernyő-elrendezéséhez

Mielőtt a szervezet használhatja a kimenő műveletek funkciókat, konfigurálnia kell a **Kimenő művelet** pénztárműveletet agy vagy több [Pénztári képernyőelrendezésen](https://docs.microsoft.com/dynamics365/unified-operations/retail/pos-screen-layouts). Az új művelet termelési környezetben történő üzembe helyezése előtt mindenképpen alaposan tesztelje, és tanítsa meg a felhasználókat a használatára.

## <a name="overview"></a>Áttekintés

A kimenő művelet révén a pénztári felhasználók a következő feladatokat hajtják végre:

- Szállítmányok feladása átmozgatási rendelés dokumentumaiba azokban az esetekben, amikor a felhasználó üzlete a kijelölt kimenő raktár.
- Az üzlet által feladott korábbi átmozgatásirendelés-szállítmányok adatainak megtekintése.
- Új kimenő átmozgatási rendelési kérelmek létrehozása.

Amikor a pénztári alkalmazásból indul el a kimenő művelet, megjelenik a listaoldal nézete. Ez a nézet olyan nyitott átmozgatási dokumentumokat mutat be, amelyek készletsoraiban a felhasználó aktuális üzlete van meghatározva szállításhoz és teljesítéshez. Egy dokumentum megkereséséhez és kiválasztásához a felhasználók görgethetik a listát, vagy használhatják a keresési funkciót.

A kimenő készlet dokumentumlista három lapból áll.

- **Aktív** – Ez a lap azokat az átmozgatási rendeléseket jeleníti meg, amelyek állapota **Kérelmezve** vagy **Részben leszállított**. A rendelések olyan sorokat vagy sorokban található mennyiségeket tartalmaznak felhasználó aktuális üzletének kell szállítani. Ez a lap azokat a rendeléseket is megjeleníti, amelyek állapota **Feldolgozás a központban** (azaz a Commerce Headquarters rendszerből történő sikeres feladás megerősítésére várnak) vagy **Feldolgozás nem sikerült** (azaz a Commerce Headquarters rendszerbe történő feladás sikertelen volt, és a felhasználónak ki kell javítania az adatokat, és újra el kell küldenie a rendeléseket).
- **Vázlat** – Ezen a lapon láthatók a felhasználó üzlete által létrehozott kimenő átmozgatásirendelés-kérelmek. A dokumentumok azonban csak helyben lettek mentve. A Commerce központba még nem küldték be feldolgozásra.
- **Kész** – Ez a lap felsorolja azokat az átmozgatási rendelési dokumentumokat, amelyeket az üzlet teljesen kiszállított a legutóbbi hét napban. Ez a lap csak tájékoztatásra szolgál. A dokumentumokkal kapcsolatos összes adat írásvédett az üzlethez.

Amikor bármelyik lapon megtekinti a dokumentumokat, az **Állapot** mező segít megérteni azt a fázist, ahol a dokumentum tart.

- **Vázlat** – az átmozgatási rendelés dokumentum csak helyileg lett mentve az üzlet csatorna-adatbázisában. Az átmozgatási rendelési kérelemmel kapcsolatos adatokat még nem küldték el a Commerce központba.
- **Kérelmezve** – A beszerzési rendelés vagy átmozgatási rendelés a Commerce központ alkalmazásban lett létrehozva, és teljesen nyitva van. A felhasználó aktuális áruháza még nem dolgozott fel szállítmányt a dokumentummal szemben.
- **Részben szállított** – Az átmozgatási rendelés dokumentumának egy vagy több sora vagy részlege somennyisége fel lett adva szállítottként a kimenő raktárba. A leszállított sorok készen állnak a bejövő műveleten keresztüli fogadásra.
- **Teljesem kiszállított** – Az átmozgatási rendelésnek minden sora és teljes sormennyisége a kimenő raktár által szállítottként feladva.
- **Folyamatban** – Ez az állapot tájékoztatja az eszköz felhasználóit, hogy a dokumentummal egy másik felhasználó aktívan dolgozik.
- **Szüneteltetve** – Ez az állapot azt követően jelenik meg, hogy a **Szüneteltetés kérelmezve** ki van választva fogadási folyamat ideiglenes leállításához.
- **Feldolgozás a központban**– Ezt a dokumentumot a Commerce Headquarters modulból átadták a pénztárba, de még nem lett sikeresen feladva a Commerce Headquarters modulba.. A dokumentum az aszinkron dokumentumfeladási folyamaton megy keresztül. Miután sikeresen feladta a dokumentumot a Commerce Headquarters modulba állapota a **Teljesen bevételezve** vagy **Részben bevételezve** kell legyen.
- **A feldolgozás nem sikerült** – A dokumentumot a Commerce Headquarters modulba adták fel, és elutasították. A **Részletek** ablaktábla a feladási hiba okát jeleníti meg. Az adathibák javítása érdekében szerkeszteni kell a dokumentumot, majd újra el kell küldeni a Commerce Headquarters modulba feldolgozásra.

Amikor kiválaszt egy bizonylatsort a listából, megjelenik egy **Részletek** ablaktábla. Ez a ablaktábla a dokumentum további adatait jeleníti meg, mint például a szállítási és a dátumadatokat. Egy folyamatjelző sáv azt mutatja, hogy hány cikket kell még feldolgozni. Ha a dokumentumot nem sikerült feldolgozni a Commerce Headquarters modulban, a **Részletek** ablaktábla megjeleníti a hibához kapcsolódó hibaüzeneteket.

A dokumentumlista lapnézetében kiválaszthatja a **Rendelés részletei** elemet az alkalmazássávon, és megtekintheti a dokumentum részletes adatait. A bevételezés feldolgozását is aktiválhatja a jogosult bizonylatsorok esetében.

A dokumentum lista oldal nézetben új kimenő átmozgatási rendelést is létrehozhat egy üzlethez.

## <a name="transfer-order-shipping-process"></a>Átmozgatási rendelés szállítási folyamata

Miután kiválasztotta egy átmozgatási rendelési dokumentumot az **Aktív** lapon, a teljesítési folyamat megkezdéséhez kiválaszthatja a **Rendelés részletei** elemet. Megjelenik a **Teljes rendelési lista** nézet. Ez a lap megjeleníti az összes cikkeket tartalmazó bizonylatsort. A megrendelt mennyiség részletes adatait is megjeleníti.

A vonalkódok minden beolvasása egy egységgel frissíti a **Szállítás most** mezőben szereplő mennyiséget. A szállítási mennyiséget az alkalmazássáv **Termék szállítása** elemének kiválasztásával, a cikk azonosítójának beírásával, majd a mennyiség megadásával is megadhatja. Ha a tétel helyvezérelt akkor a bizonylatsor szállítási helyének jóváhagyására vagy beállítására is van lehetőség.

A **Teljes rendelési lista** nézetben manuálisan kiválaszthat a listából egy sort, majd a kiválasztott sorhoz tartozó **Szállítási most** mennyiséget a **Részletek** ablaktáblában frissítheti.

### <a name="over-delivery-shipping-validations"></a>Túlszállítással kapcsolatos szállítási ellenőrzések

Az ellenőrzések a bizonylatsor bevételezési folyamata során történnek meg. Ezek a túlszállításra vonatkozó ellenőrzéseket is tartalmazzák. Ha egy felhasználó több készletet próbál meg bevételezni, mint amennyit megrendelt egy beszerzési rendelésen, de a túlszállítás nincs beállítva, vagy a bevételezett mennyiség meghaladja a beszerzési rendelés sorához beállított túlszállítási tűréshatárt, akkor a felhasználó hibaüzenetet kap, és a felesleges mennyiséget nem lehet fogadni.

### <a name="underdelivery-close-lines"></a>Alulszállítási lezárási sorok

A Commerce 10.0.12-es verziójában egy olyan funkció került hozzáadásra, amellyel a pénztárfelhasználók lezárhatják vagy törölhetik a fennmaradó mennyiségeket a kimenő rendelési szállítás során, ha a kimenő raktár megállapítja, hogy a kért teljes mennyiséget nem lehet szállítani. A mennyiségeket később is le lehet zárni vagy törölni. A funkció használatához a vállalatot be kell állítani, hogy engedélyezze az átmozgatási rendelések alulteljesítését. Ezenkívül az átmozgatási rendelési sorhoz meg kell adni egy alulteljesítési százalékot is.

Ha azt szeretné, hogy a vállalat engedélyezze az átmozgatási rendelések alulszállítását, a Commerce-központ alkalmazásban nyissa meg a **Készletkezelés \> Beállítás \> Készlet- és raktárkezelési paraméterek** pontot. A **Készlet- és raktárkezelési paraméterek** oldalon az **Átmozgatási rendelések** lapon kapcsolja be az **Alulszállítás elfogadása** paramétert. Ezt követően futtassa az **1070**-es felosztási ütemezési feladatot, és szinkronizálja a paraméter-módosításokat az üzlet csatornájára.

Az átmozgatási rendelés soraihoz tartozó alulszállítási százalékok a Commerce-központ termékekkonfigurációjának részeként előre is megadhatók. Alternatív megoldásként a Commerce-központ alkalmazáson keresztül egy adott átmozgatási rendelés sorában megadhatók vagy felülírhatók.

Miután egy szervezet befejezte az átmozgatási rendelés alulszállításának konfigurálását, a felhasználók egy új **Fenmmaradó mennyiség lezárása** lehetőséget látnak a **Részletek** panelen,amikor kiválasztják a kimenő átmozgatási rendelési sort a pénztár **Kimenő művelet** műveletével. Ezután, amikor a felhasználók befejezik a szállítmányt a **Teljesítés befejezése** művelettel, egy kérést küldhetnek a Commerce-köpont számára egy még ki nem szállított mennyiség visszavonására. Ha egy felhasználó úgy dönt, hogy lezárja a fennmaradó mennyiséget, akkor a Commerce ellenőrzi, hogy a visszavonni kívánt mennyiség az átmozgatási rendelés sorában megadott alulszállítás százalékos tűréshatárán belül van-e. Ha túllépi az alulszállítási tűréshatárt, a felhasználó hibaüzenetet kap, és addig nem tudja lezárni a fennmaradó mennyiséget, amíg a korábban szállított és a "most szállított" mennyiség el nem éri vagy meg nem haladja az alulszállítási tűréshatárt.

Miután a szállítmányt szinkronizálta a Commerce-központ rendszerbe, a program a POS rendszerbeli átmozgatási rendelés **Most szállított** sorában megadott mennyiségeket a Commerce-központ egy szállított állapotára frissíti. A korábban "még szállítandónak" minősülő nem szállított mennyiségek (azaz a későbbiekben szállításra kerülő mennyiségek) visszavont mennyiségnek minősülnek. Az átmozgatási rendelési sorhoz tartozó "még szállítandó" mennyiség **0** (nulla) értékre kerül beállításra, és a rendszer a sort teljes egészében kiszállítottnak tekinti.

### <a name="shipping-location-controlled-items"></a>Helyvezérlet cikkek szállítása

Ha a leszállított cikkek helyvezéreltek, a felhasználók kiválaszthatják, hogy melyik helyen szeretnének kibocsátani a készletűrlapot a szállítási folyamat során. Javasoljuk, hogy a folyamat hatékonyabbá tételéhez konfiguráljon az üzlet raktárához egy alapértelmezett kiadási helyet. Ha van alapértelmezett hely beállítva, akkor a felhasználó igény szerint felülbírálhatja a kiválasztott sorokban a kibocsátási helyet.

A művelet figyelembe veszi az **Üres bevételezés engedélyezett** konfigurációját a **Hely** tárolási dimenziójánál, és nem követeli meg, hogy a helydimenziót adjon meg, ha üres nyugta van konfigurálva. Ha egy tétel esetében nem engedélyezettek az üres bevételezési helyek, a pénztár alkalmazás hibát jelez, és megköveteli hely megadását a bevételezés feladása.

### <a name="ship-all"></a>Összes szállítása

Igény esetén kiválaszthatja az **Összes szállítása** lehetőséget az alkalmazássávon hogy az összes dokumentumsorban gyorsan frissíthesse a **Szállítás most** mennyiséget az összes dokumentumsorhoz arra a maximális értékre, amely elérhető teljesítésre azokhoz a sorokhoz.

### <a name="cancel-fulfillment"></a>Teljesítés megszakítása

Csak akkor használja az alkalmazássáv **Teljesítés visszavonása** funkcióját, ha ki szeretne lépni a dokumentumból, és nem szeretné menteni a változtatásokat. Például eredetileg nem megfelelő dokumentumot választott ki, és nem szeretné, hogy a korábbi szállítási adatok bármelyike mentve legyen.

### <a name="pause-fulfillment"></a>Teljesítés szüneteltetése

Ha teljesíti az átmozgatási rendelést, akkor a **Teljesítés szüneteltetése** funkciót használhatja, ha szünetet szeretne tartani a folyamatban. Előfordulhat például, hogy egy másik műveletet szeretne végrehajtani a pénztárból, például fel szeretne hívni egy vásárlói eladást egy szállítmány a Commerce Headquartersbe való feladását szeretné késleltetni.

Amikor kiválasztja a **Teljesítés szüneteltetése**beállítást, a dokumentum állapota **Szüneteltetve** értékre. Ennélfogva a felhasználó tudni fogja, hogy a dokumentumban vannak megadva értékek, de a dokumentum még nem lett véglegesítve. Ha készen áll a teljesítési folyamat folytatására, válassza ki a szüneteltetett dokumentumot, majd válassza ki a **Rendelés részletei** elemet, A korábban mentett **Szállítás most** mennyiségek megmaradnak, és a **Teljes rendelési lista** nézetből jeleníthetők meg.

### <a name="finish-fulfillment"></a>Teljesítés befejezése

Ha befejezte az összes **Szállítás most** mennyiség megadását a termékekhez, akkor be kell jelölnie a **Teljesírés befejezése** elemet az alkalmazássávon.

Az aszinkron dokumentum-feldolgozás használatakor a program az aszinkron dokumentum-keretrendszeren keresztül küldi be a bevételezést. A dokumentum feladásához szükséges idő a dokumentum méretétől (a sorok száma) és a kiszolgálón tapasztalható általános feldolgozási forgalomtól függ. Ez a folyamat általában másodpercek alatt megtörténik. Ha a dokumentum feladása sikertelen, akkor a rendszer a **Kimenő művelet** dokumentumlistán, az **Aktív** lapon keresztül értesíti a felhasználót, ahol a dokumentum állapota **Feldolgozás sikertelen** értékre módosul. A felhasználó ezt követően kiválaszthatja a hibás dokumentumot a POS-ban, és megtekintheti a hibaüzeneteket, valamint a hiba okát a **Részletek** ablaktáblán. Egy hibás dokumentum nem feladott marad, és szükséges, hogy a felhasználó visszatérjen a dokumentumsorokhoz a pénztár **Rendelés részletei** lehetőségének kiválasztásával. A felhasználónak ezt követően a hibák alapján módosítania kell a dokumentumot a javításokkal. A dokumentum javítása után a felhasználó megpróbálhatja újra feldolgozni azt úgy, az alkalmazássáv **Teljesírés befejezése** elemét választja.

## <a name="create-an-outbound-transfer-order"></a>Kimenő átmozgatási rendelés létrehozása

A pénztárból a felhasználók új átmozgatási rendelési dokumentumokat hozhatnak létre. A folyamat megkezdéséhez válassza az alkalmazássáv **Új** elemét, miközben a fő **Kimenő művelet** dokumentumlistán tartózkodik. Ezt követően a program felkéri, hogy válasszon egy raktárat vagy üzletet az **Átvitel célhelyének** ahová az aktuális üzlet a raktárkészletet fogja küldeni. Az értékek az üzlet teljesítési csoportjának konfigurációjában meghatározott lehetőségekre korlátozódnak. A kimenő átmozgatási kérelmekben a jelenlegi üzlet mindig az átmozgatási rendelés **Átvitel forráshely** raktára. Ez az érték nem módosítható.

A szükséges értékeket a **Szállítási dátum** , **Bevételezés dátuma** és a **Szállítási mód** mezőkben adhatja meg igény szerint. Hozzáadhat olyan megjegyzést is, amely az átmozgatási rendelés fejlécével együtt lesz tárolva mellékletként a dokumentumban a Commerce Headquarters modulban.

Miután létrehozta a fejléc adatait, hozzáadhat termékeket az átmozgatási rendeléshez. A cikkek és a kívánt mennyiségek hozzáadási folyamatának megkezdéséhez olvassa be a vonalkódokat, vagy válassza a **Terméke hozzáadása** lehetőséget.

A kimenő átmozgatási rendelés sorainak megadása után a **Mentés** parancsot kell kiválasztania, hogy helyben mentse a dokumentum módosításait, vagy a **Kérelem benyújtása** lehetőséget a rendelés részleteinek a Commerce Headquarters részére történő elküldéséhez további feldolgozás céljából. Ha a **Mentés** lehetőséget választja, a piszkozatot a csatorna-adatbázisban tárolja a program, és a kimenő raktár nem futtathatja a dokumentumot mindaddig, amíg az nincs sikeresen feldolgozva a **Kérelem beküldése** folyamattal. Csak akkor válassz a **Mentés** lehetőséget, ha nem szeretné véglegesíteni a kérést a Commerce Headquarters modul felé feldolgozásra.

Ha a dokumentum helyben lett mentve, az a **Vázlatok** helyen található a **Bejövő művelet** dokumentumlistában. Amikor egy dokumentum **Vázlat** állapotú, szerkesztéshez válassza a **Szerkesztés** parancsot. A sorokat igény szerint frissítheti, hozzáadhatja vagy törölheti. A **Piszkozatok** lapon a **Törlés** gombra kattintva a teljes dokumentumot is törölheti, amíg az **Vázlat** állapotban van.

Miután sikeresen elküldte a vázlatdokumentumot a Commerce Headquarters modulba, az az **Aktív** lapon jelenik meg, és állapota **Kérelmezve**. Ezen a ponton csak a kimenő raktár felhasználói módosíthatják a dokumentumot a Pénztár alkalmazás **Kimenő művelet** elemének kiválasztásával. A bejövő raktár felhasználói megtekinthetik az átmozgatási rendelést az **Aktív** lapon a **Bejövő művelet** dokumentumlistában de nem szerkeszthetik vagy törölhetik. A szerkesztési zárolás biztosítja, hogy nem fordulnak elő ütközések, mert a bejövő kérelmező éppen akkor módosítja az átmozgatási rendelést, amikor a kimenő szállító aktívan kitárolja és szállítja a rendelést. Ha az átmozgatási rendelés elküldése után a bejövő üzletből vagy raktárból változtatások szükségesek, a kimenő szállítmányozóval kell felvenni a kapcsolatot, és kérni tőle a változtatásokat.

Miután a dokumentum a **Kérelmezett** állapotú, készen áll a teljesítési feldolgozására a kimenő raktár részéről. Mivel a szállítmány feldolgozása a kimenő művelet alapján történik, az átmozgatási rendelési dokumentumok állapota **Kérelmezett** állapotból **Teljesen szállítva** vagy **részben szállítva**értékre módosul. Miután a dokumentumok **Teljesen kiszállított** vagy **Részben kiszállított** állapotban vannak, a bejövő üzlet vagy a raktár a bejövő művelet bevételezési folyamata alapján is feladhatja a bevételezéseket azokkal szemben.

A teljesen leszállított átmozgatási rendeléseket a **Kimenő művelet** dokumentumlista **Kész** lapjára helyezi át a program. A kimenő üzletben vagy raktárban lévő felhasználók számára csak olvasható módban hét napig láthatók maradnak.

## <a name="related-topics"></a>Kapcsolódó témakörök

[Bejövő készletműveletek a pénztárban](pos-inbound-inventory-operation.md)
