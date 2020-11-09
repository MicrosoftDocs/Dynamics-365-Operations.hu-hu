---
title: Rendelésteljesítés az üzletben
description: Ez a témakör az üzletben való rendelésteljesítésről nyújt áttekintést.
author: rubencdelgado
manager: AnnBe
ms.date: 10/30/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailStoreTable, RetailTillLayout
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: Global
ms.search.industry: retail
ms.author: rubendel
ms.search.validFrom: 2017-10-30
ms.dyn365.ops.version: ''
ms.openlocfilehash: 68132a78921e0a38c61c85bcc2b89dca3c25b04e
ms.sourcegitcommit: 776758a0ff95c3c7398986095104d1d2b9814514
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/24/2020
ms.locfileid: "4107207"
---
# <a name="store-order-fulfillment"></a>Rendelésteljesítés az üzletben

[!include [banner](includes/banner.md)]

Számos kiskereskedő szeretné optimalizálni a rendelésteljesítést a rendelések teljesítésének engedélyezésével az üzletek számára. A rendelésteljesítés az üzlet szintjén segíthet megkönnyíteni a túlkészletezési helyzeteket az egyes üzletek esetében, vagy logisztikai szempontból lehet szükség rá, amennyiben egy üzletnek extra kapacitása van, vagy a vevőhöz közelebb van szállítási távolság szempontjából. A szükséglet megoldása érdekében egy egységes rendelésteljesítési művelet érhető el pénztárban.

Az adott üzletben teljesítendő rendelésekél a rendelési fejlécben vagy a rendelés soraiban az üzlet raktára van hozzárendelve.

A rendelés teljesítése művelet a pénztárban egységes munkaterületet biztosít a pénztárban, amely a rendelések feldolgozására használható. Itt szerepel minden, a rendelés elfogadása, a megjelölése szállítottként vagy az üzleten belüli felvétel kezdeményezése.

## <a name="access-unified-order-fulfillment-in-the-point-of-sale"></a>Hozzáférés az egyesített rendelésteljesítéshez a pénztárban

A rendelésteljesítés, [Művelet azonosítója 928](https://docs.microsoft.com/dynamics365/unified-operations/retail/pos-operations), használható az üzletben való rendelésteljesítés munkaterület elérésére a pénztárban.

A rendelés teljesítése művelet gyárilag nem rendelkezik saját engedéllyel, de a jövőben felhasználók fel tudják használni a **Rendelés beolvasásának engedélyezése** engedélyt a művelet meghívásához a pénztárban.

Az üzlet szintjén egy beállítás érhető el annak a meghatározásához, hogy egy rendelési sort manuálisan el kell-e fogadni a pénztárból. Ha nincs beállítva ez a beállítás, a rendeléssorokat alapértelmezés szerint elfogadja a rendszer. Ha ez a beállítás be van kapcsolva, a felhasználóknak a pénztárnál ki kell választaniuk a **Rendelés elfogadásának engedélyezése** engedélyt, hogy elfogadhassák a rendeléseket a pénztárból.

A pénztárnál a rendeléssorokat is lehet elutasítani. Egy rendeléssor elutasítása azt jelzi, hogy nem teljesítik az adott üzletben a rendelést, és visszaküldik a rendeléssort ismételt hozzárendeléshez egy másik üzlethez és raktárhoz. A rendeléssor elutasításának engedélyét a **Rendelés elutasításának engedélyezése** engedéllyel lehet megadni.

## <a name="order-fulfillment-operation-parameters"></a>Rendelés teljesítése művelet paraméterei

A rendelésteljesítés gyári paramétereket tartalmaz, amelyeket a műveletre lehet alkalmazni a meghívásakor a pénztárban. Ha a **Minden rendelés** paraméter be van állítva, az összes rendelés megjelenik a művelet használatakor. A **Szállítandó rendelések** paraméter csak az üzletből szállítandó rendeléseket jeleníti meg, és a **Rendelések átvételre** azokat a rendeléseket jeleníti meg, amelyeket az üzletben fognak átvenni.

## <a name="orders-for-fulfillment"></a>Rendelések teljesítésre

A rendelés teljesítése művelet csak azokat a rendeléseket jeleníti meg, amelyeket vagy az aktuális üzletben fognak felvenni, vagy amelyeket az aktuális üzletből kell kiszállítani. Más üzletekben teljesítendő rendelések nem szerepelnek a listában a rendelés teljesítése művelet használata esetén.

## <a name="line-selection"></a>Sorválasztás

Sorok kiválasztásához használja a műveleti ablak **Kiválasztás** funkcióját. Ha a **Kiválasztás** engedélyezve van, több sor választható ki feldolgozásra. A kijelölt sorok törléséhez kattintson ismét ugyanarra a sorra.

## <a name="line-details"></a>Sor részletei

A soradatok a sor részletei úszó menüvel jeleníthető meg. A menü használata esetén három lap áll rendelkezésre a kiválasztott sor további adatainak megjelenítésére. Az első lapon a **Soradatok** a sor részleteit mutatja, például a megrendelt mennyiséget és a fennmaradó részt. További részletek is megtekinthetők, többek között a kitárolt, csomagolt és számlázott mennyiség, valamint a szállítás módja és a szállítási cím. A **Rendelés részletei** fül olyan rendelésifejléc-adatokat nyújt, mint a vevő, a vevő azonosítója, a rendelésszám, a rendelés összesen és az egyenleg. A **Készlet** lapon információk jelennek meg a kijelölt sorról a fizikailag rendelkezésre álló készletre, a lefoglalt készletre és a megrendelt készletre vonatkozóan.

Ha több sor van bejelölve, a rendelési sor részletei úszó menü csak azt jelzi, hogy több sor van kiválasztva. Egy sor részleteinek megjelenítéséhez törölje a sorokat, amíg csak egy sor marad.

## <a name="pending-order-lines"></a>Függő rendelési sorok

Az összesített rendelésteljesítés magában foglalja a lehetőséget a rendelések manuális elfogadására. Alapértelmezés szerint az üzletben teljesítendő rendeléseinek már el vannak fogadva. Azonban, ha az üzleti folyamatok azt határozzák meg, hogy az üzlet szintjén a dolgozónak el kell fogadnia a rendeléseket, a manuális elfogadás bekapcsolható a kiskereskedelmi üzlet szintjén. A rendelés elfogadásának engedélyezéséhez ugorjon ide: **Retail és Commerce** \> **Csatornák** \> **Áruházak** \> **Minden kiskereskedelmi üzlet**. Nyissa meg a kívánt üzletet az **Általános** lapon, keresse meg a **Rendelés teljesítése** alfejlécet. A fejléc tartalmaz egy **Manuális elfogadás** beállítást, amelynek az értéke alapértelmezés szerint **Nem**. Ha a beállítás **Igen** , és a módosításokat a csatorna-adatbázisba szinkronizálja, a rendeléssorok átmehetnek az elfogadási folyamaton.

A **Rendelés elfogadásának engedélyezése** engedéllyel rendelkező dolgozók megnyithatják a rendelésteljesítést, és kiválaszthatják a sorokat elfogadásra. Miután sor került a sorok elfogadására, az állapotuk megváltozik: **Függő** helyett **Elfogadott** lesz, és végrehajtható a rendelésteljesítési folyamat fennmaradó része. Ha a **Manuális elfogadás** be van kapcsolva, a rendelések nem dolgozhatók fel, amíg nincsenek elfogadva.

Az üzleten belüli felvételre váró rendelések állapota soha nem lehez **Függő**. Erre azért van szükség, hogy ne forduljon elő az, hogy az üzletbe érkezik egy vevő, és a rendelési sort nem lehet feldolgozni, mert nem érhető el a megfelelő jogosultsággal rendelkező dolgozó.

## <a name="accepted-order-lines"></a>Elfogadott rendeléssorok

Az **Elfogadva** sorállapotú rendelések a pénztárnál haladhatnak át a rendelésteljesítési folyamat többi részén. A rendelés elfogadása után a fennmaradó intézkedések a rendelési sorral szemben hajthatók végre.

Például egy elfogadott rendelési sor kijelölhető, és közvetlenül kitárolható, anélkül, hogy végigmenne a kitároláson és a csomagoláson.

## <a name="line-actions"></a>Sorműveletek

### <a name="pick"></a>Kitárolás

A **Kitárolás** műveletkategória feldata a rendeléssoroknak a polcokról való kitárolási folyamatának segítése. A kitárolási művelet csak a korábban elfogadott rendeléssorokon hajtható végre.

**Művelet: Kitárolás**

- **Eredmény pénztárállapot:** Kitárolás
- **Eredmény háttérirodai állapot:** Nincs módosítás

Egy rendelés elfogadása után a sorok kijelölhetők, és megjelölhetők a **Kitárolás** állapottal. A sor megjelölése a **Kitárolás** állapottal egy mód annak a jelzésére, hogy a kitárolási munka végrehajtása már folyamatban van egy soron. Ezzel megelőzhető, hogy két dolgozó próbálja egyszerre kitárolni ugyanazokat a rendelési sorokat.

**Művelet: Kitárolási lista nyomtatása**

- **Eredményállapot:** Kitárolás
- **Eredmény háttérirodai állapot:** Nincs módosítás

A kitárolási listák kinyomtathatók a pénztárnál a kitárolási folyamatot végrehajtó dolgozók támogatása céljából. A nyomtatott kitárolási listát magával viheti a kitárolást végző dolgozó, és a termékek kitárolásakor a dolgozó manuálisan jelölheti meg őket kitároltként a kitárolási listán.

A kitárolási lista formátumának konfigurálása a Commerce alkalmazásban történik, és hozzá van adva a nyugtaprofilhoz. A nyugtaprofilok beállításával kapcsolatos további tudnivalókat lásd: [Nyugta minták és nyomtatás](https://docs.microsoft.com/dynamics365/unified-operations/retail/receipt-templates-printing).

Ha sorok vannak kijelölve, és a kitárolási listát kinyomtatták ezekhez a sorokhoz, a sorok automatikusan frissülnek a **Kitárolás** állapotra.

**Művelet: Megjelölés kitároltként**

- **Eredmény állapota:** Kitárolt vagy részben kitárolt
- **Eredmény háttérirodai állapot:** Kitárolt vagy részben kitárolt

A fizikai kitárolási folyamat végrehajtását követően a sorok megjelölhetők a **Kitárolva** állapottal. Egy sor kijelölés, és megjelölés a **Kitárolva** állapottal, végrehajt egy valós idejű hívást a rendeléssor frissítésére. Miután a sor megkapta a **Kitárolva** megjelölést a pénztárnál, az állapot a háttérirodában is frissül **Kitárolva** állapotra, és a készlettranzakciók tükrözik, hogy megtörtént a megadott mennyiséggel való csökkentés.

Ha a rendeléseket bizonyos idő alatt dolgozzák fel, részleges mennyiségeket lehet feldolgozni egy meghatározott sorhoz. Ha egy sor ki van jelölve, sor kerül a **Megjelölés kitároltként** műveletre, és a mennyiség nagyobb egynél, a felhasználónak meg kell adnia a mennyiséget. A fennmaradó kitárolandó mennyiség automatikus kitöltésű. Ha kevesebb van megadva, mint a fennmaradó mennyiség, a sor állapota **Részben kitárolt** lesz. Amikor a rendeléssor frissül a háttérirodában, itt is megjelenik a Részben kitárolt állapot, és a felhasználó által megadott mennyiség lesz használva a készlet frissítésére.

Ha egy rendeléssort hibásan tárolnak ki, visszatárolási folyamatot kell elvégezni a rendelési soron a háttérirodában. Jelenleg nincs támogatott visszatárolása művelet a pénztárnál.

Különböző rendelésekből származó rendeléssorok kiválaszthatók és megjelölhetők a **Kitárolás** állapottal, ugyanarra a kitárolási listára nyomtathatók, illetve megjelölhetők a **Kitárolva** állapottal.

### <a name="pack"></a>Csomag

A rendeléssorok bármikor csomagolhatók, miután a rendelési sor el lett fogadva.

**Művelet: Szállítólevél-tranzakció nyomtatása**

- **Eredmény állapot:** Csomagolt vagy részben csomagolt
- **Eredmény háttérirodai állapot:** Kiszállítva vagy részben kiszállítva

Ez a művelet a sorokat megjelöli csomagolt vagy részben csomagolt állapotúként, és kinyomtatja a szállítólevelet. Szállítólevél nyomtatható az együtt csomagolt termékek ellenőrzéséhez. A szállítólevél formátumának konfigurálása a Commerce alkalmazásban történik, és hozzá van adva a nyugtaprofilhoz. A nyugtaprofilok beállításával kapcsolatos további tudnivalókat lásd: [Nyugta minták és nyomtatás](https://docs.microsoft.com/dynamics365/unified-operations/retail/receipt-templates-printing).

**Művelet: Megjelölés csomagoltként**

- **Eredmény állapot:** Csomagolt vagy részben csomagolt
- **Eredmény háttérirodai állapot:** Kiszállítva vagy részben kiszállítva

A **Megjelölés csomagoltként** művelet használható annak a jelzésére, hogy a sorok csomagolva vannak, szállítólevél nyomtatása nélkül. A **Szállítólevél nyomtatása** és a **Megjelölés csomagoltként** egyaránt háttérirodai készlettranzakciót eredményez. A pénztárnál a csomagsorok a háttérirodában szállítólevél-naplók generálását váltják ki.

Ha egy rendelési sor csomagolása hibás, a szállítólevél-naplót helyesbíteni kell a háttérirodában.

Csak ugyanazon a rendelésen szereplő, és ugyanolyan szállítási módú sorokat lehet egyszerre csomagolni.

Jelenleg le van tiltva az üzleten belüli felvételes sorok megjelölése **Csomagolt** állapotúként. Ez a lehetőség valamelyik jövőbeli programverzióban jelenik meg. A szállítólevél-létrehozási folyamat továbbfejlesztéseként a rendszer támogatni fogja a harmadik fél szállítási információk befoglalását a szállítólevél-folyamatba.

### <a name="pick-up"></a>Felvétel

Az üzleten belüli felvételre kijelölt rendeléseket közvetlenül fel lehet venni a pénztárnál való lehívás után. Az üzleten belüli átvételes rendeléseket nem kell elfogadni.

**Művelet: Átvétel**

- **Eredmény állapot:** Számlázva vagy részben számlázva
- **Eredmény háttérirodai állapot:** Számlázva vagy részben számlázva

Ha egy sor ki van választva átvételre az összesített rendelésteljesítésből, a teljes rendelés betöltődik a pénztárba, és a kijelölt sorra vonatkozó teljes mennyiség be lesz jelölve. A rendelés többi sora is betöltődik a pénztár tranzakciónézetébe, de a mennyiség megjelölése nulla lesz.

Miután a felvételi sorokat a rendszer betöltötte a tranzakciónézetbe, a tranzakciót a szokásos módon lehet kifizetni.

Az átvétellel teljesen számlázott sorok nem jelennek meg az egységes rendelésfeldolgozásban. A részlegesen felvett sorok továbbra is megjelennek az egységes rendelésteljesítésben, amíg a felvételük teljes egészében meg nem történik.

Ha egy sor felvétele hibásan történik, visszaküldést kell elvégezni a hiba elhárításához.

Csak ugyanazon a rendelésen szereplő, és ugyanolyan szállítási módú sorokat lehet egyszerre felvenni.

### <a name="shipping"></a>Szállítás

Az üzletből szállítandó rendeléssorokat az egységes rendelésteljesítés keretében lehet feldolgoznia a **Szállítás** művelettel. Ha a manuális rendeléssor-elfogadás konfigurálva van a csatorna szintjén, a rendeléseket a szállítást megelőzően el kell fogadni. Egy rendelési sor elfogadása után, amikor az állapota **Függő** vagy más, a sorok szállíthatók.

**Művelet: Szállítás**

- **Eredmény állapot:** Számlázva vagy részben számlázva
- **Eredmény háttérirodai állapot:** Számlázva vagy részben számlázva

Az egyesített rendelésteljesítésből szállított sorok számlázása a háttérirodából történik, hasonlóan ahhoz, mintha a rendelés számlázása közvetlenül a háttérirodából történne. Az egyesített rendelésteljesítésből szállított sorok nem töltődnek be a tranzakciónézetbe, és nincs fizetés a sorok szállításának időpontjában.

A teljes mértékben szállított rendeléssorok már nem jelennek meg az egyesített rendelésteljesítésben. A részlegesen szállított sorok továbbra is megjelennek az egységes rendelésteljesítésben, amíg a szállításuk teljes egészében meg nem történik.

Csak az azonos rendelésből származó sorok szállíthatók egyszerre. Ha az ugyanabban a rendelésbe tartozó soroknak eltérő a szállítási módja, még mindig ki lehet választani őket egy időben történő szállításra.

### <a name="reject"></a>Elutasítás

A sorokat vagy a részleges sorokat el lehet utasítani. Ez lehetővé teszi a társítás megváltoztatását a háttérirodáról egy másik üzletre vagy raktárra. A sorok csak akkor utasíthatók el, ha még nem lettek felvéve vagy csomagolva. Az olyan sorok elutasításához, amelyet már felvettek vagy csomagoltak, a háttérirodából kell visszavonni a felvételt vagy a csomagolást.

**Művelet: Elutasítás**

- **Eredmény állapot:** Elutasítva
- **Eredmény háttérirodai állapot:** Nincs módosítás

Az elutasított rendeléssorok megtekinthetők az **Értékesítési rendelés feldolgozása és lekérdezése** munkaterületen. Törölje a személy szűrőt a munkaterületen az összes elutasított rendeléssor megtekintéséhez az áruházakra nézve. Az **Elutasított rendeléssorok** lap a **Rendelések és kedvencek** szakaszban megjeleníti a rendeléssorok adatait. Ezenkívül a felhasználóknak rákattinthatnak az **Elutasított rendeléssorok** gombra az **Összegzés** szakaszban az értékesítési rendelés nézet megjelenítéséhez. Ez megjelenít minden olyan rendelést, amelynek van egy vagy több elutasított rendeléssora. Ha az elosztott rendeléskezelés (DOM) engedélyezve van, akkor az elutasított rendelések automatikusan hozzá lesznek rendelve a megfelelő üzletekhez teljesítésre, azonban ezek a rendeléssorok manuálisan is hozzárendelhetők. Ehhez válassza ki a sort, amelynél a **Teljesítési állapot** **Elutasítva** , és szükség szerint módosítsa a helyet/raktárt. Kattintson a **Sor frissítése** legördülő menüre, majd kattintson a **Teljesítési állapot visszaállítása** elemre a teljesítési állapot módosításához **Elutasítva** állapotról **Elfogadott** vagy **Függő** állapotra, a rendelésteljesítés beállításától függően. A teljesítési állapota visszaállítását követően az üzlet dolgozói megtekinthetik a rendeléssorokat a pénztárban.

## <a name="line-quantity-tracking"></a>Sormennyiség követése

Az egynél nagyobb mennyiséggel rendelkező egyetlen rendeléssor hosszabb időn át is feldolgozható, amely a rendeléssorok több alállapotát eredményezi. Ha például egy építési vállalkozó egy olyan projektet futtat, amelyhez 500 deszka szükséges, de az építési vállalkozó a projekt során egyszerre csak néhány deszkát vesz át vagy szállíttat, lehetnek olyan mennyiségek, amelyeket egyszerre vesznek át, csomagolnak és szállítanak.

Amikor kijelölnek egy sort, a sor fennmaradó mennyiségét automatikusan kitölti a rendszer annak a feltételezés érdekében, hogy a fennmaradó mennyiség feldolgozása folyamatban van. A fenti példánál maradva, ha 200 deszkát már felvettek, és a deszka sorát kijelölték felvételre, a fennmaradó mennyiséget, a 300 deszkát, a rendszer automatikusan kitölti a mennyiséghez. Ugyanez igaz, ha 200 deszka már ki lett számlázva. Ebben az esetben csak a fennmaradó mennyiség lesz automatikusan kitöltve.

A fenti példánál maradva, ha 200 deszka csomagoltként van megjelölve, és a szállítási be van jelölve, a teljes mennyiség, 500 darab lesz automatikusan kitöltve. Ha csak 200 deszkát szállítanak, akkor a rendszer azt feltételezi, hogy a korábban csomagolt deszkákat szállítják, és a csomagolt mennyiséget a rendszer csökkenti. Ha 201 deszkát szállítanak, a csomagolt deszkák számát először csökkentik a fennmaradó egyedi deszkákkal, amelyeket levonnak a fennmaradó mennyiségből.

## <a name="line-statuses"></a>Sorállapotok

A pénztárban levő rendeléssoroknak több állapota van, hogy tükrözzék a rendelési sor állapotát. A pénztárban és a háttérirodában levő állapotok nem egyeznek meg minden esetben. A rendelésisor-állapotokat a pénztárban a rendelésteljesítési folyamat használatával lehet megtekinteni. A háttérirodában a rendelési sorokat a rendelés részleteinél lehet megtekinteni. A rendelés részletei itt érhetők el: **Retail és Commerce** \> **Vevők** \> **Minden vevői rendelés**. A rendelés adatainak megtekintéséhez válassza ki a **Rendelésazonosító** lehetőséget. A rendelés részleteinél válassza ki az **Értékesítési rendelés** fület, majd válassza ki a **Részletes állapot** elemet a **Megtekintés** alfejléc alatt.

- **Függőben** – Azoknak a rendelési soroknak, amelyeket egy üzlethez társítottak, de még nem fogadták el őket, **Függőben** az állapota, amikor megtekintjük a pénztárban. A pénztárban elfogadásra váró sorok állapota a **Rendelés feldolgozása** a háttérirodában.
- **Elfogadva** – Azoknak a rendelési soroknak, amelyeket manuálisan vagy automatikusan fogadtak el, **Elfogadva** lesz az állapota a pénztárban. Az **Elfogadva** állapotú sorok megjelenő állapota **Rendelés feldolgozása** a háttérirodában.
- **Kitárolás** – Az üzlet szintjén jelenleg kitárolás alatt levő sorok állapota **Kitárolás**. Ugyanezek a sorok a háttérirodából megtekintve a **Rendelés feldolgozása** állapotot jelzik ki.
- **Kitárolva** és **részlegesen kitárolt** – A pénztárnál kitárolt vagy részben kitárolt sorok állapota **Kitárolva** vagy **Részben kitárolva** lesz. A háttérirodában ugyanezek a sorok szintén a **Kitárolva** és a **Részben kitárolva** állapottal jelennek meg.
- **Csomagolva** és **Részben csomagolva** – A pénztárnál csomagolt vagy részben csomagolt sorok állapota **Csomagolva** vagy **Részben csomagolva** lesz. A háttérirodában ugyanezek a sorok szintén a **Csomagolva** és a **Részben csomagolva** állapottal jelennek meg.
- **Részben számlázva** – A részben felvett vagy részben szállított sorok állapota **Részben számlázva** lesz a pénztárnál és a háttérirodában.
- **Számlázott** – A pénztárnál teljesen számlázott sorok többé nem jelennek meg teljesítésre. Az ilyen sorok háttérirodai állapota **Számlázott** lesz.

## <a name="order-fulfillment-filtering"></a>Rendelésteljesítés szűrése

A rendelésteljesítés a pénztárban magában foglalja a szűrés lehetőségét, segítséget nyújtva a felhasználónak ahhoz, hogy könnyen megtalálja azt, amire szüksége van. A szűrőket a **Pénztár** képernyő alsó részén lehet módosítani a műveleti ablaktáblán. Alapértelmezés szerint a **Szállítás típusa** szűrő van alkalmazva, attól függően, hogy hogyan van beállítva a működés. Ha a működés a **Minden rendelés** paraméterrel van beállítva, akkor a rendszer ezt a szűrőt alkalmazza a rendelésteljesítés megnyitásakor. Ugyanez vonatkozik az **Átvétel az üzletben** és a **Szállítás az üzletből** paraméterekre is. A rendelésteljesítés nézetre a következő egyéb szűrőket lehet alkalmazni:

- Vevőszám
- Vevő neve
- Vevő e-mail címe
- Rendelés száma
- Szállítás módja
- Bevételezési szám
- Csatornahivatkozás azonosítója
- Kiindulási üzletszám
- Sor állapota
- Létrehozás dátuma
- Szállítási időpont
- Kézhezvételi dátum
