---
title: Túl-/alulteljesítési tranzakciók
description: Ez a témakör olyan információkat tartalmaz, amelyek segítenek beállítani a többlet- és hiánytranzakciókra vonatkozó irányelvek részleteit, így a rendszer meghatározhatja, hogy hogyan kezelje a cikkek túl- és alulfeldolgozását a bevételezéskor.
author: sherry-zheng
ms.date: 01/13/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ITMOverUnderTrans, ITMOverUnderToleranceTable, ITMOverUnderReasonTable, ITMOverUnderToleranceGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-01-13
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 53b1ebf27a58b1c16c6c249ca044fd746cce1436
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/11/2021
ms.locfileid: "6020911"
---
# <a name="overunder-transactions"></a>Túl-/alulteljesítési tranzakciók

[!include [banner](../../includes/banner.md)]

Hajóút rendeléseinek feldolgozásakor a rendszer elvárja, hogy a végső célraktárba felhasználási célra bevételezett mennyiség megegyezzen a hajóúthoz kapcsolódó beszerzésirendelés-sorokban megadott mennyiséggel. Mivel azonban a beszerzésirendelés-sorokban szereplő pontos mennyiség nem mindig érkezik be a raktárba, a **Partraszállítási költség** modul meghatároz egy szabálykészletet, amely az áruk túl- és alulbevételezésének kezeléséhez szükséges. Ezek a szabályok különösen azért fontosak, mert az eredeti beszerzési rendelés már ki van számlázva, és már nem módosítható. A többlet- és hiánytranzakciókra vonatkozó irányelvek részleteinek beállításával lehetővé teszi a rendszer számára, hogy meghatározza, hogyan kezelje a cikkek túl- és alulfeldolgozását a bevételezéskor. A túl- és alulraktározást manuálisan is kezelheti a **Többlet-/hiánytranzakciók** oldalon.

## <a name="overunder-tolerances"></a>Túl-/alulteljesítési tűréshatárok

A túlszállítás és az alulszállítás tűréshatárainak beállításával megadhatja egy hajóúton hiba okozása nélkül feldolgozható túl- és alulszállítási mennyiségeket vagy térfogatokat. Ha a hajósor bevételezése kívül esik ezen a tűréshatáron, akkor módosítani kell és meg kell oldani, mielőtt a hajúutat le lehet zárni további feldolgozásra.

A tűréshatárok beállításához lépjen a **Partraszállítási költség \> Beállítás fölött/alatt \> Tűréshatárok fölött/alatt** lehetőségre. Itt megtekintheti, szerkesztheti, hozzáadhatja és eltávolíthatja a tűréshatárrekordokat. Az alábbi táblázat bemutatja az egyes rekordokhoz rendelkezésre álló mezőket.

| Mező | Leírás |
|---|---|
| Számlakód | <p>A következő értékek közül választva adja meg azon szállítók hatókörét, amelyekre a tűréshatár vonatkozik:</p><ul><li>**Tábla** – a tűréshatár fölött/alatt érték csak a sorhoz kiválasztott szállítóra vonatkozik.</li><li>**Csoport** – a tűréshatár fölött/alatt érték a szállítói tűréshatár szerinti csoport összes szállítójára vonatkozik.</li><li>**Mind** – a tűréshatár fölött/alatt érték minden szállítóra vonatkozik.</li></ul> |
| Számlakapcsolat | Válassza ki azt a szállítót vagy szállítócsoportot, amelyre a tűréshatár fölött/alatt értéke vonatkozik, attól függően, hogy mit választott a **Számla kódja** mezőben. |
| Cikk kódja | <p>A következő cikkek közül választva adja meg azon szállítók hatókörét, amelyekre a tűréshatár vonatkozik:</p><ul><li>**Tábla** – a tűréshatár fölött/alatt érték csak a sorhoz kiválasztott cikkre vonatkozik.</li><li>**Csoport** – a tűréshatár fölött/alatt érték a cikktűréshatár szerinti csoport összes cikkére vonatkozik.</li><li>**Mind** – a tűréshatár fölött/alatt érték minden cikkre vonatkozik.</li></ul> |
| Cikk-kapcsolat | Válassza ki azt a cikket vagy cikkcsoportot, amelyre a tűréshatár fölött/alatt értéke vonatkozik, attól függően, hogy mit választott a **Cikk kódja** mezőben. |
| Összegtűréshatár | Adja meg a teljes beszerzési rendelésre alkalmazandó összeg tűréshatárát. |
| Százalékos tűréshatár | Adja meg a beszerzési rendelés egyedi sorára alkalmazandó százalékos arány tűréshatárát. |

## <a name="overunder-reasons"></a>Túl-/alulteljesítés okai

Ha a bevételezett hajóúthoz szállítási többlet vagy hiány társul, lehet, hogy azonosítani kell a többlet vagy a hiány okát. Ebben az esetben kiválaszthatja a túl- vagy alulszállítás okát a fogadó sorban, amikor az árut bevételezik.

A túl- és alulszállítások okainak beállításához lépjen a **Partraszállítási költség \> Beállítás fölött/alatt \> Okok fölött/alatt** lehetőségre. Itt megtekintheti, szerkesztheti, hozzáadhatja és eltávolíthatja az elérhető túl- és alulszállítási okokat. Az alábbi táblázat bemutatja az egyes okokhoz rendelkezésre álló mezőket.

| Mező | Leírás |
|---|---|
| Túl-/alulteljesítés oka | Írja be a túl- vagy alul bevételezési tranzakció okának egyedi nevét. |
| Leírás | Adja meg az ok fölött/alatt leírását. |
| Mozgás | Válassza ki az ok fölött/alatt értékhez kapcsolódó átmozgatási naplót. Ez a mező felsorolja az összes olyan elérhető naplót, amelyekhez *Áthelyezés* típusú napló van társítva a **Készletnaplók neve** oldalon (**Készletkezelés – Beállítás \> Naplónevek \> Leltár**). |

## <a name="item-overunder-tolerance-groups"></a>A cikk túl-/alulteljesítési tűréshatár szerinti csoportjai.

A hasonló tűréshatárral rendelkező cikkek csoportosíthatók. Ily módon egyszerre állíthatja be a tűréshatár fölött/alatt értéket az adott csoport összes eleméhez.

A cikk tűréshatár fölött/alatt lévő csoportokhoz való beállításához lépjen a **Partraszállítási költség \> Beállítás fölött/alatt \> Cikk tűréshatár szerinti csoportok fölött/alatt** lehetőségre. Itt megtekintheti, szerkesztheti, hozzáadhatja és eltávolíthatja a tűréshatár fölötti/alatti csoportok rekordjait. Az alábbi táblázat bemutatja az egyes rekordokhoz rendelkezésre álló mezőket.

| Mező | Leírás |
|---|---|
| Túl-/alulteljesítési tűréshatár szerinti csoport | Adjon egyedi nevet a csoportnak. A tűréshatárt leíró név kiválasztása, például *1% Var*. |
| Leírás | A csoport leírásának megadása. |

## <a name="vendor-overunder-tolerance-groups"></a>Szállító túl-/alulteljesítési tűréshatár szerinti csoportjai

Csoportosíthatja a rendszeresen túl- vagy alulszállító szállítókat. Ezután csoportonként beállíthatja a tűréshatár fölött/alatt értéket.

A szállító tűréshatár fölött/alatt lévő csoportokhoz való beállításához lépjen a **Partraszállítási költség \> Beállítás fölött/alatt \> Szállító tűréshatár szerinti csoportok fölött/alatt** lehetőségre. Itt megtekintheti, szerkesztheti, hozzáadhatja és eltávolíthatja a tűréshatár fölötti/alatti csoportok rekordjait. Az alábbi táblázat bemutatja az egyes rekordokhoz rendelkezésre álló mezőket.

| Mező | Leírás |
|---|---|
| Csoportok fölött/alatt | Adjon egyedi nevet a csoportnak. Válassza ki a csoportba tartozó szállítók típusát leíró nevet. |
| Leírás | A csoport leírásának megadása. |

## <a name="view-and-process-overunder-transactions"></a>Többlet-/hiánytranzakciók megtekintése és feldolgozása

Többlet-/hiánytranzakciók akkor jönnek létre, ha a betárolt áruk mennyisége nem egyezik meg az inicializált mennyiséggel. Az érkeztetési naplóban szereplő mennyiséget csak a betárolt mennyiséggel kell frissíteni.

A hajóútsorok bevételezésének feldolgozásakor a szállítóhoz beállíthatók a tűréshatárok fölött/alatt értékek. A cikkek ellenőrzése és érvényesítése ezután történik meg. A tűréshatár beállítható százalékos értékként, helyi összegként vagy mindkettőként.

Ha egy bevételezett cikk a tűréshatáron belül van, a rendszer átmozgatási naplót generál. Ezt a naplót a hajóút paraméterei oldalon lehet megadni. Ezen kívül létrejön egy többlet-/hiánytranzakció. Például a rendelés értéke $100, a bevételezési érték $99, és ezek az értékek megfelelnek a tűréshatárszabályoknak. Ebben az esetben az alulbevételezett mennyiségre negatív átmozgatási napló jön létre.

Ha a bevételezett cikk kívül esik a tűréshatáron, a rendszer a mennyiségek közötti eltérésre generál egy többlet-/hiánytranzakciót.

A többlet-/hiánytranzakciók megtekintéséhez és feldolgozásához a **Partraszállítási költség \> Lekérdezések \> Többlet-/hiánytranzakciók**. A hajóút túl-/alulbevételezett cikkeihez többlet-/hiánytranzakció társul. Javasoljuk, hogy a **Többlet-/hiánytranzakciók** oldalon oldjon fel minden, hajóutakhoz társított többlet-/hiánytranzakciót. Azt is javasoljuk, hogy **ne** használjon mozgatási és leltárnaplókat az alulszállítási raktári tranzakciók manuális feloldására. Ehelyett a **Többlet-/hiánytranzakciók** oldalon kezelheti az alulszállítási raktári mennyiségeket.

### <a name="upper-overview-tab"></a>Felső Áttekintés lap

A többlet-/hiánytranzakciók megtekintéséhez válassza az **Áttekintés** lapot a **Többlet-/hiánytranzakciók** oldal felső részén. Az alábbi táblázat bemutatja a rácsban rendelkezésre álló mezőket.

| Mező | Leírás |
|---|---|
| Túl-/alulteljesítési tranzakció száma | Az érkeztetési napló feldolgozásakor automatikusan létrehozott többlet-/hiánytranzakciós rekord egyedi neve. |
| Út | Az a hajóút, amelyhez a beszerzési sort csatolták. |
| Szállítási konténer | Az a konténer, amelyhez a beszerzési sort csatolták. |
| Érkezési napló | Az az érkeztetési napló, amelyből a sor fölött/alatt értéket generálta a rendszer. |
| Hivatkozás | Hivatkozás a beszerzési rendelésre vagy a többlet-/hiánytranzakcióhoz társított átmozgatási rendelésre. |
| Szám | A többlet-/hiánytranzakcióban hivatkozott beszerzési rendelés. |
| Szállítói számla | Az a szállító, akihez a túl magas vagy túl alacsony érték kapcsolódik. |
| Úton lévő áruk száma | Az átszállított áruk száma, ha van ilyen. |
| Cikkszám | Az cikkszám, amelyhez a túl magas vagy túl alacsony érték kapcsolódik. |
| Eredeti mennyiség | A szállítmányhoz kapcsolódó beszerzésirendelés-sor eredeti mennyisége. |
| Bevételezett mennyiség | A ténylegesen bevételezett mennyiség. |
| Eltérés | Az érkeztetési napló várható összege és az érkeztetési naplóba feladott összeg közötti különbség. A negatív érték áruk túlszállítására utal. |
| Fennmaradó mennyiség | Az érkeztetési napló sorában megmaradó mennyiség. |
| Többlet/hiány szállításkor | Ez az érték jelzi, hogy a bevételezett mennyiség túl magas vagy túl alacsony értékű-e. |
| Állapot | A többlet-/hiánytranzakció állapota. A **[Partraszállítási költségparaméterek](landed-cost-parameters.md)** oldalon megadott beállításoktól függően a túlszállítás automatikusan átmozgatási naplót hozhat létre a túlszállítás összegéhez, és feladja a naplót. Ebben az esetben a többlet-/hiánytranzakció *Befejezve* állapotú lesz. Ha intézkedés szükséges az áruknak az alulszállítási raktárból történő átmozgatásához, a rekord *Folyamatban* állapotú lesz. |
| Túl-/alulteljesítés oka | A többlet-/hiánytranzakcióhoz társított ok. |
| Egyéb készletdimenziók | Ha szükséges, a további dimenziók oszlopai megjeleníthetők a rácsban. Ilyen dimenziók például a kötegszám, a készletállapot és a raktár. A Művelet panelen válassza ki a **Készlet \> Dimenziók megjelenítése** lehetőséget egy párbeszédpanel megnyitásához, ahol kiválaszthatja a megjeleníteni kívánt dimenziókat. |

### <a name="upper-general-tab"></a>Felső Általános lap

A felső **Áttekintés** lapon aktuálisan kiválasztott sorral kapcsolatos további információk megtekintéséhez válassza az **Általános** lapot a **Többlet-/hiánytranzakciók** oldal felső részén. A lapon található információk tartalmazzák az összes elérhető dimenzió értékét. Ezt az információt a rendszer az eredeti beszerzési rendelésből másolja át.

### <a name="lower-overview-tab"></a>Alsó Áttekintés lap

A felső **Áttekintés** lapon aktuálisan kiválasztott sorral kapcsolatos dokumentumtípus megtekintéséhez válassza az **Áttekintés** lapot a **Többlet-/hiánytranzakciók** oldal alsó részén. Az alábbi táblázat bemutatja a rendelkezésre álló mezőket.

| Mező | Leírás |
|---|---|
| Új dokumentumtípus | A mező *Átmozgatási napló* vagy *Beszerzési rendelés* lehetőségre van beállítva attól függően, hogy milyen művelet látható a kijelölt többlet-/hiánytranzakció sorában. |
| Szám | Hivatkozás és hiperhivatkozás a beszerzési rendelésre vagy a kijelölt többlet-/hiánytranzakcióhoz társított átmozgatási naplóra. |
| Túl-/alulteljesítés oka | A kiválasztott többlet-/hiánytranzakcióhoz társított ok. |
| Mennyiség | A kiválasztott mennyiség a beszerzési rendeléshez vagy a kijelölt többlet-/hiánytranzakcióhoz társított átmozgatási naplóhoz kapcsolódóan. |

### <a name="lower-general-tab"></a>Alsó Általános lap

A kijelölt többlet-/hiánytranzakció számának, tételazonosítójának és dimenziószámának megtekintéséhez válassza az **Általános** lapot a **Többlet-/hiánytranzakciók** oldal alsó részén. 

### <a name="process-overunder-transactions"></a>Többlet-/hiánytranzakciók feldolgozása

A **Többlet-/hiánytranzakciók** lapon található műveleti ablaktábla a következő parancsokat biztosítja az oldalon kijelölt tranzakciók feldolgozásához. Minden egyes parancs lehetővé teszi az egyes tranzakciók feldolgozási módjának kiválasztását.

- **Létrehozás \> Áthelyezés** – a kijelölt tranzakció átmozgatási naplójának létrehozása és feladása. Hiánytranzakciók esetén a program automatikusan létrehoz és felad egy átmozgatási naplót a várt és tényleges bevételezett mennyiség különbségére. Válassza ezt a parancsot a többlettranzakciókhoz, ha azt szeretné, hogy a költségek közötti eltérést a szállító realizálja.
- **Létrehozás \> Beszerzési rendelés** – beszerzési rendelés létrehozása a kiválasztott tranzakció várható és tényleges bevételezési mennyisége közötti eltéréshez. Válassza ezt a parancsot a többlettranzakciókhoz, ha azt szeretné, hogy a költségek közötti eltérést a szervezete realizálja.
- **Létrehozás \> Átmozgatás a célhoz** – ez a parancs csak az átmozgatási rendelésekre érvényes. Akkor válassza ezt a lehetőséget, ha a többlet/hiány mennyiségét át szeretné áthelyezni a célraktárba.
- **Létrehozás \> Átmozgatás a forráshoz** – ez a parancs csak az átmozgatási rendelésekre érvényes. Akkor válassza ezt a lehetőséget, ha a többlet/hiány mennyiségét át szeretné áthelyezni az eredeti raktárba.
