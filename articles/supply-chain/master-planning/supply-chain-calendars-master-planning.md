---
title: Naptárak és alaptervezés
description: Ez a témakör áttekintést nyújt az ellátási lánc naptárakkal, illetve az alaptervezésre vonatkozó hatásukkal kapcsolatosan.
author: t-benebo
manager: tfehr
ms.date: 05/08/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: t-benebo
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: d542c52623c1b3c0aa4b23159d56791cdc981f48
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/02/2020
ms.locfileid: "3213492"
---
# <a name="calendars-and-master-planning"></a>Naptárak és alaptervezés

[!include [banner](../includes/banner.md)]

Ez a témakör áttekintést nyújt az ellátási lánc naptárakkal, illetve az alaptervezésre vonatkozó hatásukkal kapcsolatosan.  A különböző a fő tervezőmotorban használt naptárakat taglalja, beleértve azt, hogyan befolyásolják tervezett megrendelések szállítási és fogadási dátumát. Végül a javaslatokat is talál a naptárak hozzárendelésével, használatával és frissítésével kapcsolatosan.

## <a name="definition-of-a-calendar"></a>Naptár definiálása.

Megadhatja a szervezetben használt naptárt a **Szervezet felügyelete > Beállítás > Naptárak > Naptárak** helyen. 

Minden naptárbejegyzés a naptárban lehet **nyitott** vagy **lezárt** vagy **alapnaptár**. Ez a **Vezérlő** oszlopban van meghatározva a **Munkaidők** lapon. Az egyes dátumoknál: 
- **Nyitott** -azt jelzi, hogy munkavégzés történik az adott napon. A naptár a munkaidő-sablonnak megfelelően lesz frissítve.
- **Lezárt** -azt jelzi, hogy nem történik munkavégzés az adott napon. 
- **Alapnaptár** - Azt jelzi, hogy az adott dátumra a munkaidőket és nyitott/zárt státuszt az alapnaptárból örökli. Tehát, az alapnaptár frissítésekor a kiválasztott naptár örökli a műveleti időket. 

Minden lezárt dátumhoz automatikusan hozzá van rendelve a **Felvételre lezárva** a jelölőnégyzet. Nyitott dátumokhoz dátumokat, manuálisan választhatja ki a **Felvételre lezárva** lehetőséget. Ez jelzi, hogy azon a napon munkavégzés történik de a szállítás nem. 

## <a name="calendars-that-affect-master-planning"></a>Az alaptervezést befolyásoló naptárak

### <a name="calendar-for-a-coverage-group"></a>Naptár egy fedezetcsoporthoz
A fedezetcsoport paranéterek közös csoportja, amely olyan elemek feltöltéséhez használható, amelyek egy adott fedezetcsoporthoz tartoznak. 

Naptár hozzáadásához egy fedezetcsoporthoz válassza az **Alaptervezés > Beállítás > Fedezet > Fedezetcsoportok** lehetőséget. Keresse meg a a kívánt fedezeti csoportot, amelyet hozzá szeretne rendelni a naptárhoz, és jelölje ki a **Naptár** mezőben.

A fedezetcsoportot különböző lapokon lehet hozzárendelni: 
    - A **Megjelent termék részletei** lapon válasszon egy tételt. Egy cikkhez tartozó fedezeti csoport megtekintéséhez kattintson a **Termékinformációk kezelése > Termékek > Kiadott termékek** lehetőségre, és válassza ki a cikket, ide, hogy a **Kiadott termékek részletei** lapra ugorjon. Megtekintheti a cikk fedezeti csoportját a **Terv** gyorslapon.
    - A **Cikk fedezete** oldalon. A kiadott termékek adatai lapon kattintson a **Cikk fedezete** elemre a cikk fedezete lap megnyitásához. Az áttekintés lapon megtekintheti a különböző paramétereket feltöltéshez a telephelytől, raktártól, és termékdimenzióktól függően. A fedezeti csoport minden egyes cikkhez a **Megjelent termék részletei** oldalról öröklődik. Ez felülbírálható **Specifikus beállítások használata** vagy **Csoportbeállítások felülbírálása** lehetőséggel az **Általános** lapon.
    - Az **Alaptervezési paraméterek** oldalon. Ha egy cikkhez nem tartozik az előző lapokon beállított fedezeti csoport, az alaptervezés az általános fedezetcsoportot használja az alaptervezési paraméterekhez. Ez az **Alaptervezés > Beállítás > Alaptervezés paraméterei** helyen van beállítva az **Általános fedezetcsoport** mezőben. 

### <a name="calendar-for-a-vendor"></a>Naptár egy szállítóhoz
Egy szállító munkanapjainak feltűntetéséhez hozzárendelhet egy beszerzési naptár a szállítóhoz a **Beszerzési rendelés alapértelmezései** lapon. 

Naptár beállításához egy szállítóhoz, létre kell hoznia a naptárat a **Szervezet felügyelete > Naptárak > Naptárak** menüben. A naptár létrehozása után hozzá kell rendelnie azt a szállítóhoz. Menjen a **Kötelezettségek > Szállítók > Minden szállító** menübe, és válassza ki a szállítót, amelyhez a naptárat hozzá szeretné rendelni. Ezután, a szállító lapján a **Beszerzési rendelés alapértelmezései** gyorslapon rendelje hozzá az új beszerzési naptárat a legördülő menü segítségével. 

A szállítói naptár azt jelzi, hogy mely napokon fogadnak beszerzési rendeléseket és a dátumokat, amikor a rendeléseket szállítják a vállalatnak. Ezért a beszerzési rendelési dátumok rendelések a szállítónak és beszerzési naptárban nyitott dátumként lesznek meghatározva a naptárban. A szállítási dátumok, az ezekre a rendelésekre szintén nyitott napok lesznek, így befolyásolják a beszerzett cikk átfutási idejét. 

#### <a name="define-the-lead-time-for-a-purchased-item"></a>Egy beszerzett cikk átfutási idejének meghatározása

A beszerzés átfutási idejének meghatározásához (és ha csak a munkanapokat kell figyelembe kell venni) a **Termékinformációk kezelése > Termékek > Megjelent termékek** menüben található alapértelmezett rendeléási beállítások lapra kell mennie, és jelölje ki az **Alapértelmezett rendelésbeállítások** lehetőséget. 

> [!Note]
> A **Munkanapok** a beszerzés átfutási ideje alatt jelzik a szállító munkanapjait. Péládul egy csak keddi szállításokat tartalmazó napárban a 10 napos szállítási idő, ha be van jelölve a munkanapok jelölőnégyzet azt jelzi, hogy 10 hétig tart (10 kedd) a tétel szállítása.
Így a legtöbb esetben nem ajánlott a munkanapok bejelölése a beszerzési rendelés átfutási idejénél.

#### <a name="define-lead-times-from-the-trade-agreements-page"></a>Átfutási idők meghatározása a kereskedelmi megállapodások lapról

Az alaptervezés úgy is beállítható, hogy az összes szállítói kereskedelmi megállapodást is figyelembe vegye. Kereskedelmi megállapodások rögzített árak vagy engedménymegállapodások, amelyek egy vagy több vevőhöz vagy szállítóhoz vannak beállítva egy vagy több termék értékesítése vagy vásárlása tekintetében. Menjen az **Alaptervezés > Beállítás > Alaptervezés paraméterei** menübe, és a **Tervezett rendelések** lapon válassza ki a **Kereskedelmi megállapodások keresése** lehetőséget a kereskedelmi megállapodások befoglalásához a tervezésbe. Az Alaptervezés kiválaszthatja a szállítót **Minimális átfutási idő** vagy a **Legalacsonyabb egységár** szerint.

### <a name="calendar-for-a-warehouse"></a>Naptár egy raktárhoz
Naptárt rendelhet egy raktárhoz is, hogy jelölje a nyitott fogadási és szállítási dátumokat. Ha nincs naptár rendelve egy raktárhoz, a rendszer úgy tekinti, hogy minden nap nyitva van. 

> [!Note]
> Naptár hozzárendelése tranzitraktárhoz semmilyen hatással nem jár. A tranzitraktárak átmozgatási rendeléseket támogatnak. A rendelések vonatkozó szállítási és kézhezvételi dátumait a nyitott napok határozzák meg a „Küldő” raktárban és a „Fogadó” raktárban, illetve a szállítási naptár üzemmódja.

#### <a name="closed-for-pickup-policy"></a>Felvételre lezárva irányelv
Ha jelezni szeretné, hogy a raktár nyitva van fogadáshoz, de felvétel nem lehetséges használhatja a **Felvételre lezárva irányelv** lehetőséget a raktár naptárában. Ez vonatkozik az ügyfelek átvételeire is. 

### <a name="transport-calendar"></a>Szállítási naptár 
Ha jelezni szeretné azokat a dátumokat, amelyek elérhetők átmozgatási rendelések szállításra egy **Forrás raktárból**, hozzárendelheti egy **Szállítási naptárat**. Szállítási naptárat beállíthat a szállítás módja szerint vagy a szállítás módja és forrás raktár szerint. Szállítási naptár beállítása az **Értékesítés és marketing > Beállítás > Kiosztás > Szállítási módok** helyen történik. Válasszon egy szállítási módot, és kattintson a **Szállítási naptár** gombra

Létrehozható egy sor minden egyes raktárhoz és a szállítási módhoz, ahol a naptár a **Szállítási naptár** oszlophoz lesz hozzáadva. Ez határozza meg a szállítási naptárt, amely akkor lesz alkalmazva, ha az áruk egy bizonyos szállítási mód használatával lesznek szállítva a raktárból. Szállítási naptár alkalmazásához egy adott szállítási módszer összes szállítmányára létrehozható egy sor raktár megadása nélkül.  Ez összes szállítmányt érinti az adott szállítási módhoz, függetlenül a raktártól. 

Ha nincs szállítási naptár hozzárendelve, a rendszer úgy tekinti, hogy minden nap nyitva szállításra.

### <a name="calendar-for-a-customer"></a>Naptár egy ügyfélhez
Ha szeretné megadni a dátumokat, amikor a vevő fogad szállításokat, rendeljen hozzá egy bevételezési naptár a vevőhöz. Ha nincs naptár hozzárendelve egy vevőhöz, a rendszer úgy tekinti, hogy a vevő minden nap fogad rendeléseket. Ez az értékesítésirendelés-sorok bevételezési dátumát érinti. Ha kiválaszt egy dátumot az értékesítésirendelés-sorokban amely nem „nyitott” az ügyfél naptárában, a rendszer azt jelzi, hogy a kézhezvételi dátum nem érvényes. 

Ne feledje, ügyfelenként csak egy naptár hozzárendelése lehetséges. Ha az ügyfél egyes különböző címeihez szeretne hozzárendelni naptárat, létrehozhat címenként egy ügyfelet, majd hozzárendelhet saját naptárát. 

A kért átvételi dátumot az értékesítésirendelési-sorokban befolyásolja az ügyfél naptára és a szállítási dátum kezelési módja. A legkorábbi szállítási dátum kiszámításával kapcsolatosan itt talál további információkat: [Rendelési ígéretek.](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/delivery-dates-available-promise-calculations).

### <a name="shipping-calendar-for-a-legal-entity"></a>Szállítási naptár jogi személyhez
Ha jelezni szeretné a dátumokat, amelyeken a jogi személy árut tud szállítani, beállíthat egy szállítási naptárat a **Szervezet felügyelete > Szervezetek > Jogi személyek** helyen. Válassza ki a jogi személyt és adja hozzá a naptárat a **Külkereskedelem és logisztika** lapon a **Szállítási naptár** mezőben. A szállítási naptárat a jogi személyhez tartozó összes raktári naptár alapértelmezéseinek forrása lesz. 

## <a name="how-calendars-affect-dates-in-planning"></a>Hogyan befolyásolják a naptárak a tervezési dátumokat

### <a name="order-date-of-a-planned-purchase-order"></a>Tervezett beszerzési rendelés rendelési dátuma 
A tervezett beszerzési rendelés rendelési dátuma jelzi a rendelés leadásának dátumát. A szállítói naptárba nés a fedezetcsoport naptárában is nyitott dátum lesz. Előfordul, hogy a szállítóknak néhány napos intervallum kell aközött, amikor a beszerzési rendelés érkezik megérkezik és aközött, amikor szállítani tudnak. Ezek a dátumok a szállítói időtartaléknál vannak feltűntetve. Ugyanakkor ha a beszerzett cikk hozzá van rendelve egy időtartalék napokat tartalmazó a fedezetcsoporthoz, ez az időtartalék felülbírálja a szállító időtartalékát.

### <a name="delivery-date-of-a-planned-purchase-order"></a>Tervezett beszerzési rendelés szállítási dátuma
Egy beszerzés kézhezvételi dátuma azt a dátumot jelzi, amikor kézhez kapja az árut. A naptárban nyitott dátum lesz. Naptár amely figyelembe lesz véve annak jelzéséhez, hogy melyik napon fogadhatók beszerzési rendelések a következők szerint lesz meghatározva a legmagasabbtól a legalacsonyabb prioritásúig: 
    1. Szállítói naptár
    2. Fedezetcsoport naptára
    3. A fogadó raktár raktári naptára

Megjegyzés: a fedezeti csoport naptára különböző lapokon is beállítható, ezek a következő sorrendben lesznek figyelembe véve:
    1. Cikkfedezeti csoport a **Kiadott termékek részletei** lapon
    2. Cikkfedezeti csoport a **Cikkfedezet** lapon
    3. Alapértelmezett cikkfedezeti csoport az **Alaptervezés paramétereiben**

### <a name="shipping-date-of-a-planned-transfer-order"></a>Tervezett átmozgatási rendelés szállítási dátuma
Két raktár között az átmozgatási rendelés létrehozásakor a szállítási dátum és a kézhezvételi dátum az átmozgatási rendelés fejlécében található, a „Küldő” raktárral és „Fogadó” raktárral együtt. E két dátum közötti különbség a várható szállítási idő (napokban) a raktárak között.

Tervezett átmozgatási rendelés szállítási dátuma, az a dátum, amelyen a cikkek kiszállítása történik a „Küldő” raktárból. A rendelkezésre álló szállítási dátum megadására használt naptárak prioritás szerint listázva: 
    1. A „Küldő” raktár raktári naptára
    2. A Fedezetcsoport naptára (az ilyen naptárakra vonatkozó sorbarendezést fent találja), ha van beállítva raktári naptár a szállítási dátum nyitott dátum lesz a naptárban. Ha nincs raktári naptár beállítva a fedezetcsoport naptára lesz figyelembe véve. 

### <a name="receipt-date-of-a-planned-transfer-order"></a>Tervezett átmozgatási rendelés átvételi dátuma
Az átmozgatási rendelés fogadási dátum azt jelzi, amikor az árukat átveszik a „Fogadó” naptárban.

Az átvételi dátum megadására használt naptárak prioritás szerint listázva: 
    1. Fedezetcsoport naptára 
    2. A „Fogadó" raktár raktéri naptára Ha van beállítva fedezeti naptár a kézhezvételi dátum nyitott dátum lesz a naptárban. Ha nincs fedezetcsoport naptár beállítva a raktár naptára lesz figyelembe véve. 

Ha a egy tervezett átmozgatás szállítási és fogadási dátumát keresési a felhasználó küldéshez és fogadáshoz fenntartott időtartaléka is figyelembe lesz véve. 

## <a name="using-calendars-in-master-planning"></a>Naptárak használata alaptervezésben

### <a name="assignment-of-scm-calendars"></a>SCM naptárak hozzárendelése
Fontos naptárakat úgy beállítani, hogy a vállalat munkanapjai azonosítva legyenek. A legjobb megoldás az, ha minden elemhez egy beállít egy naptárat különböző munkanapokkal. Más szóval, minden külső naptár (vevői, szállítói) és az összes belső a vállalathoz tartozó naptár (raktár fedezeti csoportot és szállítás).

### <a name="recommendation-on-warehouse-calendars"></a>Javaslatok a raktári naptárakkal kapcsolatosan
Ajánlatos raktáranként csak egy naptárat használni, hogy abba a csak a naptárat érintő változások kerüljenek bele. Például a két vagy több raktárnak lehetnek azonos munkanapjai, de különböző felvételi szabályai. Ebben az esetben az a legjobb megoldás ha van naptár minden egyes raktárhoz a különböző felvételi szabályokkal, hogy a legjobb dátumokat lehessen alkalmazni a tervezett beszerzési, átmozgatási és termelési rendelésekhez. Ha nincsenek raktári naptárak beállítva, a jogi személy naptára használható az alapértelmezések forrásaként a raktári naptárhoz. 

### <a name="recommendation-of-coverage-group-calendars"></a>Fedezeti csoport naptárakkal kapcsolatos javaslatok
A fedezeti csoport naptárakkal kapcsolatosan fontos, hogy felülbíráló viselkedés van érvényben az átvételi dátumok tekintetében a mestertervezésben. Így ajánlott körültekintően használni azt. Különösen, célszerű abban az esetben, ha a feltöltésnek a hét meghatározott napján kell történnie. 

### <a name="updating-scm-related-calendars"></a>SCM-hez kapcsolódó naptárak frissítése
Ugyan fontos, hogy minden megfelelő naptár a megfelelő helyhez legyen hozzárendelve (szállító, vevői, raktár, szállítási mód vagy fedezeti csoport), a frissítésük ugyanolyan fontos, hogy tükrözzék a módosításokat. A rendszer a termelési, átmozgatási, beszerzési és értékesítési rendelések dátumait a hozzárendelt naptárak kombinációja alapján határozza meg. A legjobb megoldás tisztázni, ki felelős a megfelelő területek naptárainak hozzárendeléséért és frissítésért. Leállás vagy a munkanapok bármilyen egyéb szokatlan változása esetén fontos ennek megfelelően a naptárak frissítése. Minden feladatot, amely naptárakra támaszkodik például az alaptervezés és a termelés ütemezése, a naptárak frissítésekor újra kell futtatni. 
