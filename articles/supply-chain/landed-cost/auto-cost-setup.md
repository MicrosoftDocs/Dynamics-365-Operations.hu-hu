---
title: Automatikus költségek beállítása
description: Ez a témakör azt ismerteti, hogyan lehet beállítani költségszabályokat a bejövő hajóút különféle szintjeihez. A szabályok alapján a rendszer kiszámítja a költségeket, és automatikusan hozzáadja őket. A felhasználóknak tehát nem kell manuálisan hozzáadni a költségeket.
author: sherry-zheng
ms.date: 01/21/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ITMCostAutoSetup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-01-21
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 0fe795127300ac99c3f5ee65cb1f6e0841ad4d95
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/29/2021
ms.locfileid: "7575800"
---
# <a name="auto-costs-setup"></a>Automatikus költségek beállítása

[!include [banner](../../includes/banner.md)]

Az **Automatikus költségek** oldal használatával költségszabályokat állíthat be a különböző költségterületekhez (például hajóutak, szállítókonténerek, levelek, beszerzési rendelések, cikkek vagy átátvitelirendelés-sorok). A szabályok és a felhasználók által egy rekord valamelyik költségterülethez történő létrehozásakor kiválasztott mezők alapján a rendszer kiszámítja a költségeket, és automatikusan hozzáadja őket. A felhasználóknak tehát nem kell manuálisan hozzáadni a költségeket.

Az automatikus költségek kezeléséhez kattintson a **Partraszállítási költség \> Költségszámítás beállítása \> Automatikus költségek** lehetőségre. Ezután állítsa be az automatikus költségszabályokat a témakörben leírt módon.

## <a name="work-with-cost-areas"></a>Költségterületek kezelése

Az automatikus költségek a kereskedelmi megállapodásokhoz vagy az automatikus vegyes költségekhez hasonló módon működnek. Minden automatikus költségrekord egy meghatározott költségszinthez tartozik. A munkához használni kívánt költségterület kiválasztására használja az **Automatikus költségek** oldal listaablakának **Költségterület** mezőjét. A listaablak csak az aktuálisan kiválasztott költségterülethez tartozó automatikus költségeket jeleníti meg. A létrehozott automatikus költségek a jelenleg kiválasztott költségterülethez tartoznak.

A költségterületek segítségével a rendszer egy költségterület beszerzésirendelés-sorai között arányosíthatja a költségeket. Egy szállítókonténer költsége például az abban a szállítókonténerben található összes termék értékének az arányában lesz arányosítva. Ha két vagy több szállítókonténer van, akkor minden egyes szállítókonténernél meg lehet adni ugyanazt a költségtípust. Ebből következően a konténer típusa a megfelelő automatikus költség keresésre használható.

## <a name="buttons-on-the-action-pane"></a>A Művelet panel gombjai

A következő táblázat a Művelet panel **Automatikus költség** oldalán elérhető gombok leírását tartalmazza.

| Gomb | Leírás |
|---|---|
| Szerkesztés | Meglévő automatikus költség szerkesztése. |
| Új | Automatikus költség létrehozása. |
| Eltávolítás | Automatikus költség törlése. |
| Másolás forrása | Új automatikusköltség-rekord létrehozása, amely egy meglévő rekordon alapul. Ezután szabadon szerkesztheti az új rekordot. Ezzel a gombbal gyorsan létrehozhat új automatikus költségeket. |
| Dimenziók megjelenítése | Egy párbeszédpanel megnyitása, ahol kiválaszthatja a megtekintet költségtranzakciókhoz megjelenő készletdimenziókat. Ha törli a jelölést a jelölőnégyzetekből, a költségtranzakciókhoz kevesebb készletdimenzió jelenik meg. Ennek megfelelően a tranzakcióhoz kevesebb részlet jelennik meg. Ha automatikus költséghez meg van adva egy készletdimenzió, az automatikus költség csak akkor kerül alkalmazásra, ha a megadott készletdimenziót használják a cikkhez egy hajóúton. |

## <a name="settings-on-the-header"></a>Beállítások a fejlécben

A fejlécben található beállítások kombinációja határozza meg, hogy mikor és hogyan ad hozzá egy hajóúthoz egy adott automatikus költséget. Az automatikus költségek csak akkor lesznek alkalmazva hajóútra, szállítókonténerre vagy levélre, ha az automatikus költség részletei egyeznek az érintett költségterület fejlécének részleteivel. Az összes egyező automatikus költség összege határozza meg egy hajóút becsült partraszállítási költségét. Ez a költség arányosítva van a hajó vagy a hajóút összes cikkére.

Az alábbi táblázat bemutatja az összes mezőt, amely a fejléc szakaszban megjelenhet. Az elérhető adott mezők azonban a költségterülettől és az aktuálisan kiválasztott megjelenítési dimenzióktól függően eltérőek.

| Mező | Leírás |
|---|---|
| **Számlakód** | <p>Válasszon a következő értékek közül:</p><ul><li>**Tábla** – A költségszabály csak egy adott szállítóra vonatkozik.</li><li>**Csoport** – A költségszabály egy adott szállítói csoportra vonatkozik. A rendszer meg fogja keresni a szállítói rekordhoz társított [szállítói költségtípuscsoportot](costing-parameters-setup.md).</li><li>**Összes**– A költségszabály az összes szállítóra vonatkozik. |
| **Szállítmányozási vállalat** | Válassza ki a szállítót vagy a szállítói csoportot, amelyre a költségszabály vonatkozik. Ez a mező csak akkor érhető el, ha a *Táblázat* vagy a *Csoport* lehetőséget választja a **Számlakód** mezőben. |
| **Vámügynök** | Válassza ki a szállítót vagy a szállítói csoportot, amelyre a költségszabály vonatkozik. Ez a mező csak akkor érhető el, ha a *Táblázat* vagy a *Csoport* lehetőséget választja a **Számlakód** mezőben. |
| **Cikk kódja** | <p>Válasszon a következő értékek közül:</p><ul><li>**Tábla** – A költségszabály csak egy adott cikkre vonatkozik.</li><li>**Csoport** – A költségszabály egy adott cikkcsoportra vonatkozik. A rendszer meg fogja keresni a cikkrekordhoz társított [cikk-költségtípuscsoportot](costing-parameters-setup.md).</li><li>**Összes**– A költségszabály az összes cikkre vonatkozik.|
| **Cikk-kapcsolat** | Válassza ki a cikket vagy a cikkcsoportot, amelyre a költségszabály vonatkozik. Ez a mező csak akkor érhető el, ha a *Táblázat* vagy a *Csoport* lehetőséget választja a **Cikk-kód** mezőben. |
| **Szállítás módja** | Válassza ki a szállítási módot (például légi vagy tengeri), amelyre a költségszabály vonatkozik. |
| **Tárolótípus** | A szállítókonténer típusa, amelyben az árukat szállítják. Az hajóúton csak akkor alkalmazható automatikus költség, ha a konténer típusa az automatikus költségbeállításban megfelel a hajóút konténertípusának. |
| **Indulási kikötő** és **Célkikötő** | A hajóút forrás („indulási”) kikötője és a célállomás („cél”) kikötője. (Egyes szállítókonténereknél előfordulhat, hogy más a „cél” kikötő, mert a hajóút több kikötőnél is megállhat.) Az automatikus költségek csak akkor alkalmazhatók az hajóútra, ha az automatikus költségbeállításban az „indulási” és „cél” kikötő megegyezik az hajóút „indulási” és „cél” kikötőivel. |
| **Automatikus költség száma** | Az automatikus költségszabály egyedi azonosítója. A mező értéke automatikusan jön létre a **Partraszállítási költség** oldalon beállított számsorozat alapján. |
| **Készletdimenziók** | Egyes költségterületeken egy vagy több cikkdimenziót lehet szerepeltetni a fejlécben (például méret, szín, raktár és kötegszám). Válassza a **Dimenziók megjelenítése** lehetőséget a Művelet panelen, és válassza ki a megjelenítendő dimenziókat. |

## <a name="settings-on-the-lines-fasttab"></a>A Sorok gyorslap beállításai

A **Sorok** gyorslapon adjon hozzá egy sort minden pénznemhez, amely akkor használható, amikor a hajóút beszerzésirendelés-sorára költséget alkalmaznak. 

A cikkek és beszerzési rendelések esetén a rendszer egyezteti az egyes beszerzésirendelés-sorok pénznemét a **Sorok** gyorslapon megadott pénznemekkel. Ez csak az egyező sorra vagy cikkre beállított költségértéket fogja alkalmazni. Ha nincs beállítva sor a sor vagy cikk pénzneméhez, az automatikus költség nem lesz alkalmazva arra a sorra vagy cikkre.

A költségterületek egyéb típusai esetén a **Sorok** gyorslap minden olyan hajóútra, szállítókonténerre, levélre vagy átszállításirendelés-sorra vonatkozik, amely megfelel a fejlécben megadott értékeknek.

Az alábbi táblázat bemutatja az összes mezőt, amely az egyes sorokban megjelenhet. Az elérhető adott mezők azonban az aktuálisan kiválasztott költségterülettől függően eltérőek.

| Mező | Leírás |
|---|---|
| **Pénznem** | Válassza ki azt a pénznemet, amelyre a sor vonatkozik. Ez a pénznem a beszerzési rendeléshez kapcsolódik. Amikor a rendszer megpróbálja megtalálni a hajóútra és annak hajóútsoraira alkalmazandó automatikus költségeket, akkor azt a sort választja ki, amely a beszerzési rendelés pénznemével azonos pénznemmel rendelkezik. Ez a mező csak akkor érhető el, ha a **Költségterület** mező *Beszerzési rendelés* vagy *Cikk* értékre van beállítva. |
| **Költségtípus kódja** | A költség típusa. |
| **Arányosítási mód** | <p>A költségek sorokra való elosztására használt módszer. Ehhez a következő lehetőségek állnak rendelkezésre:</p><ul><li><p>**Százalék** – A **Költségérték** mező értéke az áruk összértékére vonatkozó százalékos érték.</p><p>Ha például a **Költségérték** mező értéke *10*, és az áruk összértéke $800, a költségérték $80 (= $800 × 10 százalék).</p></li><li>**Mennyiség** – A költség az áruk mennyisége alapján lesz arányosítva.</li><li>**Összeg** – A költség az áruk értéke alapján lesz arányosítva.</li><li>**Térfogat** – A költség az áruk térfogata alapján lesz arányosítva. A térfogat a cikktörzsben van megadva.</li><li>**Súly** – A költség az áruk súlya alapján lesz arányosítva. A súly a cikktörzsben van megadva.</li><li>**Volumetrikus** – A költség az áruk volumetrikus mértéke alapján lesz arányosítva.</li><li><p>**Mérték** – Ez a beállítás teszi lehetővé a **Partraszállítási költség** modulban megadott mérték beállítását. Gyakran használják azok a szervezetek, amelyek nem ismerik az áruk egyedi mennyiségét vagy súlyát, de pontosabb arányosítást igényelnek, mint amit az **Összeg** vagy a **Mennyiség** lehetőség lehetővé tesz. A szállítmányozó vagy ügynök a cikk vagy a beszerzési rendelés szintjén biztosítja a súlyt vagy köbméteres mértéket a szervezet számára.</p><p>Például az fuvardíj $900. Az A cikk tömege 800 kilogramm (kg), térfogata 2 köbméter (m³). A B cikk tömege 100 kg, térfogata 1 m³. Íme az eredmények, amikor a költségek súly szerint vannak arányosítva:</p><ul><li>A cikk = $800</li><li>B cikk = $100</li></ul><p>Íme az eredmények, amikor a költségek térfogat szerint vannak arányosítva:</p><ul><li>A cikk = $600</li><li>B cikk = $300</li></ul><p>**Megjegyzés:** Ha az **Arányosítási módszer** mező beállítása *Mérték*, a rendszer a költségterülethez (a szállítókonténerhez) és a sorokhoz megadott mértékeket használja. Ezeknek a mértékeknek nem feltétlenül kell a várt összeget adniuk. Ha viszont megköveteli, hogy a várt összeget adják, a statisztikával ellenőrizheti az összesített mértéket. A mértékkérés beállítás és a mérték automatikus frissítése a szállítmány vagy a konténer szintjén, a hajóút fejlécében van beállítva.</p></li></ul> |
| **Kezdő dátum** | Adja meg a költségszámítás dátumtartományainak kezdő dátumát, ha van ilyen. Ez a dátum az automatikus költség alkalmazásának első dátuma. |
| **Záró dátum** | Adja meg a költségszámítás dátumtartományainak záró dátumát, ha van ilyen. Ez a dátum az automatikus költség alkalmazásának utolsó dátuma. |
| **Kategória** | <p>Válassza ki a költség kiszámításához használandó módszert. Ehhez a következő lehetőségek állnak rendelkezésre:</p><ul><li>**Rögzített** – A költség az arányosítási módszer alapján lesz arányosítva.</li><li>**Darab** – A költség darabonként kerül felosztásra. Ennek megfelelően az arányosítási módszer nem kerül használatra.</li><li>**Százalék** – A termékek értékének százaléka lesz hozzáadva. Ennek megfelelően az arányosítási módszer nem kerül használatra.</li><li>**Árfolyam** – Mennyiségi tételezés esetén válassza ezt a lehetőséget. A sor **Arányosítási módszer** mezőjének *Mérték* értékűnek kell lennie.</li><ul> |
| **Lebontva mennyiség szerint** | <p>Jelölje be ezt a jelölőnégyzetet, ha elérhetővé kívánja tenni a **Mennyiségi szünetek** gombot a **Sorok** gyorslapon. A mennyiségi szünetek lehetővé teszik a költség lebontását, a különböző költségek pedig eltérőek lehetnek, a hajóút beszerzésirendelés-sorában szereplő mennyiségtől függően. Ez a funkció gyakran kerül használatra légi szállítás esetén. A sor **Kategória** mezőjének *Árfolyam* értékűnek kell lennie.</p><p>A mennyiség az **Arányosítási módszer** mezőben kiválasztott beállításra vonatkozik. A költségérték legfeljebb a **Költségérték** mezőben megadott mennyiség lesz.<p>Például a 45–100 kg-os mennyiség $6,00 díjat eredményez mértékenként (például kg/m³). A 100 kg-ot meghaladó mennyiségek $5,50 díjat eredményeznek mértékenként (például kg/m³).</p> |
| **Költségérték** | Költség értékének megadása. |
| **Költség pénznemkódja** | Válassza ki a költség pénznemét. |
| **Cikkáfacsoport** | A költség áfakódjának kiválasztása. |
| **Minimális költség** | <p>Ez a mező csak akkor érvényes, ha a **Mennyiség szerint lebontva** jelölőnégyzet be van jelölve. Ha a mérték nem éri el ezt az értéket, a rendszer a minimális értéket választja, függetlenül a **Mennyiségi szünetek** oldalon megadott költségektől.<p>Például a 0–45 kg-os mennyiség $6 díjat eredményez mértékenként (kg/m³). A 46–100 kg-os mennyiség $5,50 díjat eredményez mértékenként (kg/m³). 2 kg szállítása esetén a mennyiségi szünet $12 költségértéket hoz létre. Ha azonban a **Minimális költség** mező a *$100* értékre van beállítva, akkor a végső költség $100 lesz.</p> |
| **Összesítés** | Jelölje be ezt a jelölőnégyzetet, ha engedélyezni kívánja a felhasználóknak, hogy ezt a költséget a szállítókonténer szintjéről az hajóút szintjáre helyezzenek át. Ebben az esetben a költségek automatikusan kiszámíthatók a szállítókonténer szintjén. Ugyanakkor az egyes szállítókonténerekben található összes cikk helyett a hajóút minden konténerének minden cikkét össze lehet kombinálni és arányosítani lehet. |
| **Kapcsolt költség típusa** | <p>Az aktuális sort ugyanannak az automatikus költségrekordnak egy másik sorához kapcsolja megadva annak a sornak a **Költségtípuskód** értékét, amelyhez kapcsolni akarja. Ez a funkció csak akkor érhető el, ha az aktuális sor **Kategória** mezője *Százalék* értékre van beállítva. Ha az aktuális sor másik sorhoz kapcsolódik, akkor az aktuális sor költsége a másik sor költségén alapul.</p><p>Például a fuvardíj $1000, és azt szeretné, ha az üzemanyagpótdíj a fuvarköltség 10 százaléka lenne. Ebben az esetben a sornak *Százalék* **Kategória** értékkel, *10%*- os **Költségérték** értékkel és *Fuvar* típusú **Kapcsolt költségtípus** értékkel kell rendelkeznie.</p> |
| **Értékhelyesbítés** és **Helyesbítés összege** | <p>Ezekkel a mezőkkel módosítható a különféle százalékos értékek értéke és összege. Csak akkor érhetők el, ha a **Költségterület** mező beállítása *Cikk*.</p><p>A cikkek különböző összetevőihez eltérő költségszámítást lehet beállítani. Előfordulhat, hogy a cikk egyik összetevőjének költségszázaléka eltér a cikk többi összetevőjének költségszázalékától. Ez a megközelítés bizonyos esetekben szükséges az áruk meghatározott részének különböző díjmértékek mellett történő értékeléséhez.</p><p>Például egy óra vámilletéke két díjmértékkel kerül számításra: az óra egyik összetevője 10 százalékos, a második rész pedig 2 százalékos illetékkel rendelkezik. Ebben az esetben a költségszámítást felosztja a rendszer a két összetevő között.</p><p>A program kiszámítja a cikk költségét, de a költségértékét a különböző költségkategóriához tartozó összetevők értéke szerint korrigálja. A fennmaradó összetevők költsége kiszámítható azzal az összeggel, amellyel az előző számítás módosítva lett.</p><p>Például az óra A összetevőjének költsége $9,50, és 10 százalékos illetékkel rendelkezik, a B összetevő költsége pedig $0,50, és 2 százalékos illetékkel rendelkezik. A teljes költség ezért $10,00. Az első bejegyzés a 10 százalékos soré. Az alábbi értékeket használja:</p><ul><li>**Kategória:** *Százalék*</li><li>**Költségérték:** *10*</li><li>**Helyesbített érték:** *Helyesbítés mértéke:*</li><li>**Helyesbített érték:** *-0,50*</li></ul><p>Ez a beállítás meghatározza, hogy a cikk költségét ($10) csökkenteni kell $0,50 összeggel (a B összetevő ára) a 10 százalékos vámdíj számítása előtt. Ennek megfelelően a program a 10 százalékot a $9,50 összegra alkalmazza.</p><p>A második bejegyzés a 2 százalékos sorhoz tartozik (a $0,50, amellyel az előző bejegyzés módosítva lett). Az alábbi értékeket használja:</p><ul><li>**Kategória:** *Százalék*</li><li>**Költségérték:** *2*</li><li>**Helyesbített érték:** *Használat*</li><li>**Helyesbítés:** *0,50*</li></ul><p>Ez a beállítás kiszámítja a B összetevő fennmaradó fizetendő vámját.</p> |
