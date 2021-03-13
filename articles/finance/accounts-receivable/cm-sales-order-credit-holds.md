---
title: Értékesítési rendelések hitelvisszatartása
description: Ez a témakör azt mutatja be, hogyan lehet beállítani a szabályokat, amelyekkel egy értékesítési rendeléshez hitelfelfüggesztést lehet beállítani.
author: mikefalkner
manager: AnnBe
ms.date: 01/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschloma
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 754b34d9d522451082ba6010297431788e4151f4
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "5012263"
---
# <a name="credit-holds-for-sales-orders"></a>Értékesítési rendelések hitelvisszatartása
[!include [banner](../includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet beállítani a szabályokat, amelyekkel egy értékesítési rendeléshez hitelfelfüggesztést lehet beállítani. A hitelkezelés zárolási szabályai egy adott vevőre vagy egy vevői csoportra vonatkozhatnak. A zárolási szabályok a következő esetekre vonatkozó válaszokat határoznak meg:

1. Késedelem napjainak száma
2. Számlák állapota
3. Fizetési feltételek
4. Lejárt hitelkeret
5. Késedelmes összeg
6. Értékesítési rendelés összege
7. A rendelkezésre hitelkeret felhasznált része

Ezenkívül két paraméter vezérli az értékesítési rendelés zárolására szolgáló további eseteket

1. Fizetési feltételek módosulása
2. Kiegyenlítési engedmények módosítása

## <a name="set-up-blocking-rules-and-exclusion-rules"></a>Zárolási szabályok és kizárási szabályok beállítása

Amikor egy vevő egy értékesítési tranzakciót kezdeményez, az értékesítési rendelésen szereplő adatok olyan zárolási szabályokkal szemben kerülnek ellenőrzésre, amelyek meghatározzák, hogy a vevőnek számára meghosszabbítható-e a hitel, és engedélyezhető-e az értékesítés végrehajtása. Megadhat olyan kivételeket is, amelyek felülírják a zárolási szabályokat, és lehetővé teszik egy értékesítési rendelés feldolgozását. A **Hitelkeret-kezelés > Beállítások > Hitelkezelés-beállítása > Zárolási szabályok** lapon beállíthatja a zárolási szabályokat és a kizárási szabályokat.

### <a name="days-overdue"></a>Késedelmes napok

Nyissa meg a **Késedelmes napok** lapot, ha a zárolási szabály egy vagy több olyan számlára vonatkozik, amely egy adott számú napnál korábban lejárt.
1. Válassza ki a vevőknek azt a tartományát , amelyrea szabály **Érvényes**.
   - Válassza ki a **Tábla** lehetőséget, ha a szabály egy adott vevőre vonatkozik.
   - Válassza ki a **Csoport** lehetőséget, ha a vevő csoport szintjén alkalmazza a szabályt. 
   - Válassza **Összes** lehetőséget, ha a szabály összes vevőre vonatkozik.
2. A tartomány megadásakor meg kell adnia a tartományban használandó **Számlát/csoportot**.
   - A **Tábla** tartomány esetében a keresés a kiválasztott vevők listáját fogja visszaadni. 
   - Válasszon egy **Csoportot**, ha a szabály egy vevői hitelcsoportra vonatkozik.
   - Válassza **Összes** lehetőséget, ha a szabály összes vevőre vonatkozik. 
3. Válassza ki a **Kockázati csoport** lehetőséget, a hitelkezelés felfüggesztéséhez olyan ügyfelekhez akik egy közös tényezőhalmaz alapján csoportosíthatók, például Dun- és Bradstreet-értékelésük alapján vagy az üzletben eltöltött évek alapján, vagy azon idő alapján, amióta az Ön ügyfelei stb.  
4. Válassza ki a szabálytípust, amit beállít. A **Zárolás** beállítás egy rendelést zároló szabályt hoz létre. A **Kizárás** beállítás egy olyan szabályt fog létrehozni, amely kizár egy másik szabályt egy rendelés zárolásából. 
5. Válasszon **Értéktípust**. Az alapértelmezett bejegyzés egy rögzített számú nap. Ha kizárást hoz létre, akkor egy rögzített számú nap vagy egy összeg adható meg. 
6. Adja meg a **Késedelmes** napok számát, amely a kiválasztott zárolási szabályhoz engedélyezve van, mielőtt egy rendelés hitelkezelési zárolásra kerül felülvizsgálat céljából. A késedelmes napok száma további türelmi napokat jelent, amelyek hozzá lesznek adva a számla fizetési határidején túli napokhoz, mielőtt azt késedelmesnek tekintené a rendszer. Ha egy kizáráshoz összegként megadott egy **Értéktípust**, akkor adjon meg egy összeget és egy pénznemet ahhoz az összeghez.

### <a name="accounts-status"></a>Számlák állapota

Akkor nyissa meg a **Számla állapota** lapot, ha a zárolási szabály egy kiválasztott számlaállapotú vevőre vonatkozik.
1. Válassza ki a szabálytípust, amit beállít.  **Zárolás**: egy rendelést zároló szabályt hoz létre. **Kizárás**: egy olyan szabályt fog létrehozni, amely kizár egy másik szabályt egy rendelés zárolásából. 
2. Válassza ki azt a **Számlaállapotot**, amely miatt a szabály várakoztat egy értékesítési rendelést vagy kizárja azt.

### <a name="terms-of-payment"></a>Fizetési feltételek

Válassza ki a **Fizetési feltételek** lehetőséget, ha a kiválasztott fizetési feltétel esetében a zárolási szabály érvényes.
1. Válassza ki a szabálytípust, amit beállít.  **Zárolás**: egy rendelést zároló szabályt hoz létre. **Kizárás**: egy olyan szabályt fog létrehozni, amely kizár egy másik szabályt egy rendelés zárolásából. 
2. Válassza ki azt a **Fizetési feltételt**, amely miatt a szabály várakoztat egy értékesítési rendelést vagy kizárja azt.

### <a name="credit-limit-expired"></a>Lejárt hitelkeret

Nyissa meg a **Hitelkeret lejárt** lapot, ha a zárolási szabály olyan vevőkre vonatkozik, amelyeknél lejárt a hitelkeret.
1. Válassza ki a vevőknek azt a tartományát , amelyrea szabály **Érvényes**.
   - Válassza ki a **Tábla** lehetőséget, ha a szabály egy adott vevőre vonatkozik.
   - Válassza ki a **Csoport** lehetőséget, ha a Vevőcsoport szintjén alkalmazza a szabályt. 
   - Válassza **Összes** lehetőséget, ha a szabály összes vevőre vonatkozik.
2. A tartomány megadása után meg kell adnia a tartományban használandó **Számlát/csoportot**.
   - A **Tábla** tartomány esetében a keresés a kiválasztható vevők listáját fogja visszaadni. 
   - Válasszon egy **Csoportot**, ha a szabály egy vevői hitelkezelési csoportra vonatkozik.
   - Válassza **Összes** lehetőséget, ha a szabály összes vevőre vonatkozik. 
3. A **Kockázati csoport** kiválasztásával tovább korlátozhatja a hitelkezelés céljából várakoztatott vevők listáját. 
4. Válassza ki a szabálytípust, amit beállít. 
   - Válassz a **Zárolás**:lehetőséget egy rendelést zároló szabály létrehozásához. 
   - Válassza a **Kizárás** lehetőséget egy olyan szabály létrehozásához, amely kizár egy másik szabályt egy rendelés zárolásából. 
5. Adja meg **Hitelkeret túllépve ennyi napja** értéket a kijelölt zárolási szabályhoz, annak meghatározásához, hogy mennyi idő teljen el, mielőtt egy megrendelés hitelkezelés céljából várakoztatva lesz. A késésben lévő napok száma olyan további türelmi napokat jelent, amelyek hozzá lesznek adva hitelkeret lejárta utáni napokhoz.

### <a name="overdue-amount"></a>Késedelmes összeg

Nyissa meg a **Lejárt összeg** lapot, ha a zárolást szabály a lejárt összegekkel rendelkező vonatkozik.
1. Válassza ki a vevőknek azt a tartományát , amelyrea szabály **Érvényes**.
   - Válassza ki a **Tábla** lehetőséget, ha a szabály egy adott vevőre vonatkozik.
   - Válassza ki a **Csoport** lehetőséget, ha a Vevőcsoport szintjén alkalmazza a szabályt. 
   - Válassza **Összes** lehetőséget, ha a szabály összes vevőre vonatkozik.
2. A tartomány megadása után meg kell adnia a tartományban használandó **Számlát/csoportot**.
   - A **Tábla** tartomány esetében a keresés a egy ügyfélkeresését fog visszaadni. 
   - Válasszon egy **Csoportot**, ha a szabály egy vevői hitelkezelési csoportra vonatkozik.
   - Válassza **Összes** lehetőséget, ha a szabály összes vevőre vonatkozik. 
3. Válassza ki a **Kockázati csoport** lehetőséget, ha tovább szeretné korlátozni a hitelkezelés céljából várakoztatásra kerülő vevők listáját. 
4. Válassza ki a szabálytípust, amit beállít. 
   - Válassz a **Zárolás**:lehetőséget egy rendelést zároló szabály létrehozásához. 
   - Válassza a **Kizárás** lehetőséget egy olyan szabály létrehozásához, amely kizár egy másik szabályt egy rendelés zárolásából. 
5. Adja meg a **Késedelmes összeg** értéket a kijelölt zárolási szabályhoz, annak meghatározásához, hogy mennyi idő teljen el, mielőtt egy megrendelés hitelkezelési várakoztatásra kerül ellenőrzéshez. 
6. Válassza ki az **Érték típusát** amely meghatározza, hogy milyen típusú értékkel lesz használva, illetve annak tesztelését, hogy mennyi lett felhasználva a hitelkorlátból. A zárolási szabályoknak százalékértéket kell megadni, de a kizáráshoz megadható rögzített összeg vagy százalékos érték. A Küszöb a hitelkeretre vonatkozik.
7. Adjon meg egy **Hitelkeret-küszöbértéket** a kiválasztott szabályhoz, mielőtt a vevő a hitelkeretkezelés céljából várakoztatásra kerül. Ez lehet egy összeg vagy egy százalék az érték típusa helyen kiválasztott értéktípus alapján.
8. A szabály ellenőrzi, hogy a **Hátralékos érték** túl van-e lépve és azt, hogy a **Hitelkorlát küszöbérték** túl van-e lépve. 

### <a name="sales-order"></a>Értékesítési rendelés 

Válassza ki az **Értékesítési rendelés** lehetőséget, ha a zárolási szabály az értékesítési rendelés értékére vonatkozik.
1. Válassza ki a vevőknek azt a tartományát , amelyrea szabály **Érvényes**.
   - Válassza ki a **Tábla** lehetőséget, ha a szabály egy adott vevőre vonatkozik.
   - Válassza ki a **Csoport** lehetőséget, ha a Vevőcsoport szintjén alkalmazza a szabályt. 
   - Válassza **Összes** lehetőséget, ha a szabály összes vevőre vonatkozik.
2. A tartomány megadása után meg kell adnia a tartományban használandó **Számlát/csoportot**.
   - A **Tábla** tartomány esetében a keresés a egy ügyfélkeresését fog visszaadni. 
   - Válasszon egy **Csoportot**, ha a szabály egy vevői hitelkezelési csoportra vonatkozik.
   - Válassza **Összes** lehetőséget, ha a szabály összes vevőre vonatkozik. 
3. Válassza ki a **Kockázati csoport** lehetőséget, ha tovább szeretné korlátozni a hitelkezelés céljából várakoztatásra kerülő vevők listáját. 
4. Válassza ki a szabálytípust, amit beállít.  
   - Válassz a **Zárolás**:lehetőséget egy rendelést zároló szabály létrehozásához. 
   - Válassza a **Kizárás** lehetőséget egy olyan szabály létrehozásához, amely kizár egy másik szabályt egy rendelés zárolásából. 
5. Adja meg az **Értékesítési rendelés összege** értéket a kijelölt zárolási szabályhoz, annak meghatározásához, hogy mennyi idő teljen el, mielőtt egy megrendelés hitelkezelési várakoztatásra kerül. 

Az értékesítési rendelés szabálya egy további beállítást tartalmaz, amely felülbírálja az összes többi szabályt. Ha olyan kizárást szeretne létrehozni, amely az értékesítési rendelést az egyéb szabályok figyelembe vétele nélkül fogja felszabadítani , jelölje be az **Értékesítési rendelés felszabadítása** jelölőnégyzetet a kizárási sorban.

### <a name="credit-limit-used"></a>Hitelkeret felhasználva

Jelölje be a **Felhasznált hitelkeret**, ha a vevő hitelkeret-összegére vonatkozik a zárolási szabály.
1. Válassza ki a vevőknek azt a tartományát , amelyrea szabály **Érvényes**.
   - Válassza ki a **Tábla** lehetőséget, ha a szabály egy adott vevőre vonatkozik.
   - Válassza ki a **Csoport** lehetőséget, ha a Vevőcsoport szintjén alkalmazza a szabályt. 
   - Válassza **Összes** lehetőséget, ha a szabály összes vevőre vonatkozik.
2. A tartomány megadása után meg kell adnia a tartományban használandó **Számlát/csoportot**.
   - A **Tábla** tartomány esetében a keresés a egy ügyfélkeresését fog visszaadni. 
   - Válasszon egy **Csoportot**, ha a szabály egy vevői hitelkezelési csoportra vonatkozik.
   - Válassza **Összes** lehetőséget, ha a szabály összes vevőre vonatkozik. 
3. Válassza ki a **Kockázati csoport** lehetőséget, ha tovább szeretné korlátozni a hitelkezelés céljából várakoztatásra kerülő vevők listáját. 
4. Válassza ki a szabálytípust, amit beállít.
   - Válassz a **Zárolás**:lehetőséget egy rendelést zároló szabály létrehozásához. 
   - Válassza a **Kizárás** lehetőséget egy olyan szabály létrehozásához, amely kizár egy másik szabályt egy rendelés zárolásából. 
5. Válassza ki a **Fennmaradó küszöb** lehetőséget, amely meghatározza az értékesítési rendelést zároló hitelkeret százalékos értéket. Ha egy rendelés értéke a megadott százalékérték fölé emeli hitelkorlát összegét, akkor a rendelést a várakoztatva lesz. 

## <a name="put-a-sales-order-on-hold-based-on-other-criteria"></a>Értékesítési rendelés várakoztatása más feltételek alapján
  
### <a name="rank-payment-terms"></a>Fizetési feltételek rangsorolása  

A hitelkeret-ellenőrzési szabályok végrehajtását kényszerítheti, ha a fizetési feltételek megváltoznak. Rangsorolnia kell a fizetési feltételeket, és társítania kell azokhoz egy rangsorolási értéket. Ha a rendelésre vonatkozó fizetési feltételeket a régi fizetési feltételeknél magasabbra rangsorolja, akkor a rendelést a rendszer elküldi hitelkezelésre, és jóváhagyás szükséges.

A fizetési feltételek rangsorát a **Hitelkezelés > Beállítások > Hitelkeret beállítása >Fizetési feltételek rangsorolása** lapon állíthatja be.

1. Válassza ki a fizetési feltételeket a **Fizetési feltételek mező** mezőben a rangsoroláshoz. Ha kiválaszt egy feltételt, akkor a **Leírás** mezőben megjelenik a leírás.
2. A **Rangsorolás** mezőben válassza aza feltétel rangsorolását. Az értékek relatívak egymáshoz képest, így 1, 2, 3 vagy 10, 20, 30 értékeket is használhat. A legtöbb fizetési feltételhez ugyanazt az értéket használhatja, ífy csak egy vagy két fizetési feltétel indítja el a hitelellenőrzést.

### <a name="rank-settlement-discounts"></a>Kiegyenlítési engedmények rangsorolása   

A hitelkeret-ellenőrzési szabályok végrehajtását kényszerítheti, ha a kiegyenlítési engedmények megváltoznak. Rangsorolnia kell a kiegyenlítési engedményeket, és társítania kell azokhoz egy rangsorolási értéket. Ha a rendelésre vonatkozó kiegyenlítési engedményeket a régi kiegyenlítési engedményeknél magasabbra rangsorolja, akkor a rendelést a rendszer elküldi hitelkezelés, és jóváhagyás szükséges.

A fizetési feltételek rangsorát a **Hitelkezelés > Beállítások > Hitelkeret beállítása >Kiegyenlítési engedmények rangsorolása** lapon állíthatja be.

1. Válassza ki a rangsorolni kívánt **Készpénzfizetési** engedményt. Megjelenik a kiegyenlítési engedmény **Leírása**.
2. Válassza ki a **Helyezés** értéket. Az értékek relatívak egymáshoz képest, így 1, 2, 3 vagy 10, 20, 30 értékeket is használhat. A legtöbb kiegyenlítési engedményhez ugyanazt az értéket használhatja, ífy csak egy vagy két kiegyenlítési engedmény indítja el a hitelellenőrzést.

## <a name="sequence-the-application-of-rules"></a>Szabályok alkalmazásának sorrendje

A szabályok meghatározott sorrendben futnak, amelyet a szervezet igényeinek megfelelően megváltoztathat. 

- Egy Értékesítési rendelés kizárási szabályának egy példánya lehetővé teszi minden olyan szabály felülbírálását, amely egy értékesítési rendelés zárolását okozhatja. Hozzon létre egy értékesítési rendelés kizárási szabályt, és jelölje Be az **Értékesítési rendelés feloldása** lehetőséget. A rendelés nem lesz várakoztatva, ha a kizárási szabály igaz, és a többi szabály nem lesz ellenőrizve.
- A zárolási szabályok a rendelést várakoztathatják.
- A kizárási szabályok a zárolási szabályok után futnak. A kizárási szabályok csak arra szabályra lesznek hatással, amelyhez definiálva vannak. 
- A zárolási és a kizárási szabályok előbb a Tábla, Csoport, Összes sorrendben futnak le. Ennek a feldolgozási sorrendnek köszönhetően előfordulhat, hogy egy zárolási szabály az Összes szinten nem fut le, mivel a Tábla vagy a Csoport szinten lefut egy kizárási szabály.
- A kizárások nem írják felül a zárolási szabályt, ha ugyanazon a szinten vannak. Például a csoport szintjén egy kizárási szabály nem bírálja felül a csoport szintjén a zárolási szabályt. Nem kell beállítania kivételeket az Összes szinten a fentiek szerint az értékesítési rendelés kizárási szabályának egy példánya esetén. 

A **Felhasznált hitelkeret** szabály viselkedése a Hitel és Beszedések paraméterűrlap **Hitelkorlát értékelési rendeléshez** paraméter beállításai szerint módosul.
- Ha a paraméter értéke Nem, akkor a Hitelkeret használt szabálya nem fut le.
- Ha a paraméter Igen értékre van állítva, és **Az üzenet a hitelkeret túllépése esetén** értéke figyelmeztetés, akkor figyelmeztetést kap a hitelkeret túllépése esetén. A **Felhasznált hitelkeret** szabályok le lesznek futtatva annak megállapításához, hogy vannak-e olyan szabályok, amelyeket le szeretne futtatni. Ehhez a helyzethez azonban általában nem kell szabályt hozzáadnia.
- Ha a paraméter Igen értékre van állítva, és az **Üzenet a hitelkeret túllépése esetén** értéke hiba, akkor a rendszer ellenőrzi a hitelkeretet, majd a rendelést várakoztatja, ha túllépi a hitelkeretet. Mindemellett a **Felhasznált hitelkeret** szabályok le lesznek futtatva annak megállapításához, hogy vannak-e további lefuttatandó szabályok. Hibaüzenet nem fog megjelenni, de a **Hitelkeret túllépve** zárolási ok megjelenik. 

## <a name="settings-that-will-change-the-way-an-order-is-placed-on-hold"></a>A rendelés várakoztatásra helyezése módját módosító beállítások

A rendelések kizárható a hitelkezelésből, még akkor is, ha léteznek szabályok. 

- Ha módosítja a **Vevőt kihagyása a hitelkeretből** beállítást Az **Összes vevő > vevő kiválasztása > Hitel és beszedések gyorslapon** **Igen értékre** akkor az ahhoz az ügyfélhez tartozó rendelések nem lesznek feldolgozva
- Ha a **Kihagyás a hitelkezelésből** értékét az **értékesítési rendelések fejlécében** a **Hitelkezelés gyorslapon** **Igen** értékre állítja, akkor a hitelkezelési szabályok nem lesznek feldolgozva. Ezt a beállítást csak a hitelezési titkár vagy a hitelezési vezető végezheti el.

## <a name="processing-orders-on-hold-using-the-credit-management-hold-list"></a>A várakoztatott rendelések feldolgozása a hitelkezelés várakozási lista használatával

A Hitelkezelés várakozási lista lehetővé teszi a hitelezési vezetők számára minden olyan értékesítési rendelést megtekintését, amely a várakoztatott állapotban van, és lehetővé teszi számukra a várakoztatás feloldását, amikor a hitelproblémák megoldásra kerültek. A **Hitelkezelés várkoztatási lista** lap megjeleníti az összes várakoztatott értékesítési rendelést. Megtekintheti a várakoztatási listát az **Összes hitelvárakoztatás** oldalon (**Hitelkezelés > Hitelkezelési várakoztatási listák > Összes hitelvárakoztatás**).
Az összes jogi személy értékesítési rendelései ugyanarra a hitelkezelés várakoztatási listára kerülnek, amely a figyelmet igénylő tranzakciók központosított megjelenítését biztosítja. A felhasználók csak azon jogi személyek adatait látják, amelyekhez rendelkeznek hozzáféréssel.

Egy értékesítési rendelés a következő okok miatt helyezhető el a várakoztatási listán:
1. A vevőnek olyan számlája van, amely már lejárt egy megadott számú napja. 
2. A rendeléshez egy adott számlaállapot tartozik.
3. A rendeléshez specifikus fizetési feltételek tartoznak.
4. A vevőnek lejárt a hitelkerete.
5. A vevő lejárt fizetendő összeggel rendelkezik, és a hitelkeret megadott százalékát felhasználta
6. Az értékesítési rendelés túllép egy bizonyos összeget.
7. A vevő túllépte a hitelkorlát egy bizonyos százalékát.
8. A fizetési feltételek eltérnek a vevő alapértelmezett fizetési feltételeitől.
9. A kiegyenlítési engedmények eltérnek a vevő alapértelmezett kiegyenlítési engedményeitől.

A zárolási ok megjelenik minden értékesítési rendeléshez a várakoztatási listán. Ha egynél több oka van a várakoztatásnak, akkor az ok értéke **Több**. A Műveleti panel **Zárolási okok** menüjében megtekintheti az értékesítési rendelés várakoztatásának okát. A **Várakoztatási okokat** egy adatterületen is megjelenítheti.

### <a name="releasing-orders-from-the-hold-list-for-processing"></a>Rendelések felszabadítása a várakoztatási listáról feldolgozás céljából

Amikor felkutatta a várakoztatás okát, és megoldotta azokat, a további feldolgozás céljából felszabadíthatja az értékesítési rendeléseket.

1) A várakoztatási listában jelöljön ki egy sort. Több sor kijelölésével egynél több rendelést is kiválaszthat.
2) Válasszon egy **Felszabadítási okot** a rendeléshez, amelyet felszabadításra jelölt ki.  
3) Adja meg a **Felülvizsgálat dátuma** értéket az egyes rendelésekhez, amelyet felszabadításra jelölt ki.  
4) Válassza ki **Felszabadítás** menüt egy rendelés felszabadításához. Ez a menü csak akkor érhető el, ha tranzakciókat választott ki. A felhasználónak két opció jelenik meg:
   - Válassza a **Feladással** lehetőséget a visszatartás eltávolításához, ekkor a dokumentum feladása ugyanazzal a feladási eljárással történik, amelyet a rendszer a visszatartáskor használt fel. Ha például az értékesítési rendelés megerősítése várakoztatásra került, akkor az értékesítési rendelés megerősítése a felszabadítás után lesz elvégezve. Az értékesítési rendelés feladási képernyő jelenik meg, amely lehetővé teszi, hogy a felhasználó feladja a visszaigazolást.
   - Válassza a **Feladás nélkül** lehetőséget, ha további feldolgozás nélkül szeretné eltávolítani a visszatartást. Az értékesítési rendelést manuálisan lehet feladni.

### <a name="rejecting-orders-in-the-hold-list"></a>Rendelések elutasítása a visszatartási listán
Egy értékesítési rendelés elutasításához használhatja a műveleti panel **Elutasítás** menüjét
1. A várakoztatási listában jelöljön ki egy sort. Több sor kijelölésével egynél több rendelést is kiválaszthat.
2. A rendelést a rendszer eltávolítja a visszatartási listából, és az értékesítési rendelés fejléce módosul, megjeleníti hogy a megrendelést elutasították.

### <a name="automatically-releasing-credit-management-holds"></a>Hitelkezelési visszatartások automatikus felszabadítása
Az értékesítési rendelések a zárolási szabályok alapján kerülnek a várakoztatási listára. Előfordulhat azonban, hogy a visszatartások bizonyos okai idővel változnak, ha az értékesítési rendelés egy adott ideig a visszatartási listán marad. Például a vevő kifizetheti a számláját, felszabadítva ezzel a hitelkeretét. 

Az **Értékelés feloldáshoz** menü segítségével ellenőrizheti az értékesítési rendeléseket a várakoztatási listán, és automatikusan felszabadíthatja őket, ha a várakoztatás oka meg lett oldva.
1.  Válassza a **Kiértékelés feloldáshoz** menüt
2.  Az összes értékesítési rendelés ellenőrzéséhez válassza a **Zárolási szabályok feldolgozása** lehetőséget. Csak a kiválasztott sorok feldolgozásához válassza a **Blokkolási szabályok feldolgozása a kijelölt sorokhoz** lehetőséget.
3. Egy csúszka jelenik meg, így egyetlen vevőt is ki lehet választani. Hagyja üresen a vevő legördülő menüt minden vevőhöz. 
4. Amikor az OK gombra kattint, a rendszer a háttérben futtatja a folyamatot, és folytathatja a munkát más feladatokon. Ha a kötegelt feldolgozást választja, mielőtt az OK gombra kattint, a folyamat a kötegben fog futni, amikor az OK gombra kattint. Hosszabb időt vehet igénybe a listán várakozó rendelések feldolgozására, így a Frissítés használatával frissítheti a rendelések állapotát. 
5.  Ha egy rendelés esetében a zárolás oka már nem alkalmazható, akkor a zárolási ok nem érvényesnek lesz tekintve, és ezt követően már nem látható a pipa az ok mellett, amikor megtekinti a zárolási okokat.
6.  Ha a zárolási okok mindegyike törölve lett, akkor egy új, **Feloldásra kész** ok lesz hozzáadva zárolási okok listájához. Az értékesítési rendelést automatikusan fel lehet szabadítani.
7.  Ha az **Automatikus felszabadítás** paraméter **a Hitel és beszedések > Beállítás >Hitel és beszedések paraméterei > Hitel > Automatikus felszabadítás** értéke **Feladással**, akkor a rendszer arra kéri, hogy adja fel ez elemet azzal a feladási móddal, amely akkor lett használva, amikor a dokumentum zárolva lett.
8.  Ha az **Automatikus felszabadítás** paraméter **a Hitel és beszedések > Beállítás >Hitel és beszedések paraméterei > Hitel > Automatikus felszabadítás** értéke **Feladás nélkül**, akkor manuálisan kell feladnia a rendelést.

### <a name="credit-management-approval-workflow"></a>Hitelkezelés jóváhagyási munkafolyamata

A hitelek felszabadításának szabályozására **Hitelkeret-kezelési munkafolyamatok** is létrehozhatók. Miután beállította a munkafolyamatot a **Hitelkezelés > Beállítás > Hitelkezelési munkafolyamatok** lapon, a felszabadításra vagy elutasításra kijelölt rendeléseket a program elküldi a munkafolyamatnak, ahol először jóvá kell hagyni őket a felszabadítás vagy elutasítás előtt. 

Ha a munkafolyamtában szerepek a felszabadítás feladással és felszabadítás feladás nélkül feladatok a munkafolyamat jóváhagyása felszabadítja az értékesítési rendelést. Ha azonban a beállítási adatok hiánya vagy más okok miatt hiba történik a felszabadítási folyamatban, akkor az értékesítési rendelést vissza kell hívnia a munkafolyamatból, ki kell javítania a hibát ami a meghiúsulást okozta, majd újra be kell küldenie a rendelést a munkafolyamatba.

Ha nem szerepelteti a felszabadítás feladással vagy felszabadítás feladás nélkül feladatoka munkafolyamatában, akkor a munkafolyamat jóváhagyási folyamata egyszerűen lehetővé teszi az értékesítési rendelés manuális felszabadítását a jóváhagyás befejezését követően.

### <a name="forced-credit-hold"></a>Kényszerített hitelvárakoztatás  
  
Időnként előfordulhat, hogy az értékesítési rendeléseket le kell tiltani annak ellenére, hogy a rendelés nem felel meg a zárolási szabályok feltételeinek. Előfordulhat például, hogy a hitelesítési vezető egy hitelhez nem kapcsolódó problémáról értesül a vevővel kapcsolatosan, és úgy dönt, hogy manuálisan automatikusan várakoztatja, amíg a probléma meg nem oldódik. Ilyen esetben manuálisan is kényszerítheti az értékesítési rendelés várakoztatását.

1. Nyissa meg azt az értékesítési rendelést, amelyet várakoztatni szeretne.  
2. Válassza a **Hitelkeret várakoztatásának kényszerítése** lehetőséget a **Hitelkezelés** lapon a **Hitelkezelés** műveleti ablaktáblán.
3. Válassza ki a **Kényszerített várakoztatás oka** értékét.
4. Kattintson az **OK** gombra. Az értékesítési rendelés vissza lesz küldve a Hitelkezelés várakoztatási listára.

Több rendelést is be lehet állítani várakoztatásra a **Hitelkezelés > Időszakos feladatok > Hitelvárakoztatás kényszerítése** lapon. Például várakoztathatja egy adott vevő összes értékesítési rendelését.
1. Válassza ki a **Kényszerített várakoztatás oka** értékét. 
2. A szerepeltetni kívánt értékesítési rendelések kiválasztásához kattintson a **Belefoglalandó rekordok** lehetőségre. 
3. A kijelölt értékesítési rendelések feldolgozásához kattintson az **OK** gombra.

A várakozásra kényszerített értékesítési rendeléseket nem lehet feldolgozni munkafolyamattal.

#### <a name="releasing-orders-that-were-added-to-the-credit-management-hold-list-with-a-forced-credit-hold"></a>A hitelvárakoztatási listához kényszerített hitelvárakoztatással hozzáadott rendelések felszabadítása
A kényszerrel várakoztatás okkal rendelkező értékesítési rendeléseket nem lehet automatikusan felszabadítani. Ha az értékesítési rendelés visszatartásra lett kényszerítve, és az értékesítési rendeléseket automatikusan felszabadító folyamatot használt, az értékesítési rendelés **Készen áll a felszabadításra** értéket mutat, és továbbra is a várakoztatási listán marad. A rendelés felszabadításához a **Felszabadítás** menüt kell használnia.
 
## <a name="free-text-invoices-orders-and-project-invoice-support-in-credit-management"></a>Szabadszöveges számlák, rendelések és projekt számlák támogatása a Hitelkezelésben 
A Hitelkezelés jelenleg csak értékesítési rendelésekhez használható. A szabadszöveges számlák, pénztári értékesítési rendelések és a hívásközponti rendelések ideiglenes hitelkereteket és biztosításokat/garanciákat használnak, amiket hozzáadhat a hitelkorlát módosításához. Nem fogják használni a zárolási szabályokat, és a hitelkerettel kapcsolatos probléma esetén nem kerülnek be a visszatartási listára.

Nincs támogatás a projekt-számlákhoz a hitelkezelésben.
