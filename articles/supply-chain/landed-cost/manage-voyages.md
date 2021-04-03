---
title: Hajóutak kezelése
description: Ez a témakör a hajóutak kezelését ismerteti. Az hajóút általában egy hajót képvisel. A gyakorlatoktól és az eljárásoktól függően azonban jelenthet szállítót, beszerzési rendelést vagy más olyan elemet, amely a szervezet számára értelmes.
author: sherry-zheng
manager: tfehr
ms.date: 12/14/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ITMTableListPage, ITMTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-14
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 850fbb2077a592ec4ba8578cab4795d573464f54
ms.sourcegitcommit: 2b4809e60974e72df9476ffd62706b1bfc8da4a7
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/04/2021
ms.locfileid: "5501006"
---
# <a name="manage-voyages"></a>Hajóutak kezelése

[!include [banner](../../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Az hajóút általában egy hajót képvisel. A gyakorlatoktól és az eljárásoktól függően azonban jelenthet szállítót, beszerzési rendelést vagy más olyan elemet, amely a szervezet számára értelmes.

Az **Összes hajóút** oldal a hajóút részleteit, a szállítási és költségszámítási információkat, valamint cikkek, beszerzési rendelések és átszállítási rendelések adatait tartalmazza. Az **Összes hajóút** oldal megnyitásához nyissa meg a **Partraszállítási költség \> Hajóutak \> Összes hajóút** menüpontot. Ez az oldal az össza aktuális hajóút listáját jeleníti meg. A Művelet panel gombjaival hajóutakat hozhat létre, törölhet és kezelhet. Válassza ki bármelyik hajóutat a listában a részleteinek megtekintéséhez.

> [!NOTE]
> A szállítókonténerek és a levelek hajóúthoz vannak kapcsolva. A beszerzési sorok egy szállítókonténerhez kapcsolódnak. Ha a szállítókonténerek és a levelek ki vannak kapcsolva, akkor közvetlenül is összekapcsolhatók hajóúttal. Ezenkívül az itt megadott költségek arányosítva vannak az összes kapcsolódó beszerzési sorral.

## <a name="action-pane"></a>Műveleti panel

A **Hajóút** oldal Művelet paneljén olyan gombok vannak, amelyek segítségével a kiválasztott hajóúton dolgozhat. Minden gomb egyetlen műveletet hajt végre. A Művelet panel lapokat is tartalmaz, amelyek viszont kapcsolódó gombokat biztosítanak. Kivéve, ahol ez jelezve van, minden gomb és lap elérhető mind az **Összes hajóút** oldal listanézetében, mind egyetlen kijelölt hajóút részletes nézetében.

### <a name="buttons-that-appear-directly-on-the-action-pane"></a>A Művelet panelen közvetlenül megjelenő gombok

A következő táblázat a közvetlenül a Művelet panelen elérhető gombok leírását tartalmazza.

| Gomb | Leírás |
|---|---|
| Új | Hajóút létrehozása. <!-- KFM: Link to scenario --> |
| Eltávolítás | Aktuális hajóút törlése. Csak a *Megerősített* hajóútállapotú hajóutak törölhetők. Ha egy hajóút elhagyja a kikötőt, és az úton lévő árukat feldolgozza, akkor a továbbiakban nem törölhető. |
| Útszerkesztő | A **Hajóútszerkesztő** oldal megnyitása, ahol beszerzési sorokat adhat hozzá az hajóúthoz, új konténereket hozhat létre, és módosíthatja a hajóút adatait. |
| Út költségei | A **Hajóút költségei** oldal megnyitása, ahol a hajóút minden áruja számára megtekinthetők és hozzáadhatók az hajóút költségei. Ha a hajóút költségeit kézzel adják hozzá az hajóúthoz, akkor automatikusan hozzáadódnak a **Költségek lekérdezése** oldalhoz, és a **Hajóút költségei** oldalon megadott módszernek megfelelően arábnyosítva lesznek minden egyes árura. |

### <a name="buttons-on-the-voyage-tab"></a>Gombok a Hajóút lapon

A következő táblázat a Művelet panel **Hajóút** lapján elérhető gombok leírását tartalmazza. Ez a lap csak akkor érhető el, ha az **Összes hajóút** oldal listanézetében dolgozik.

| Gomb | Leírás |
|---|---|
| Szállítási konténer | Egy lap megnyitása, amely a kiválasztott hajóúthoz társított összes szállítókonténert mutatja. Egy vagy több konténer lehet. |
| Ívlap | Egy lap megnyitása, amely a kiválasztott hajóúthoz társított összes levelet mutatja. Egy vagy több levél lehet. |

### <a name="buttons-on-the-manage-tab"></a>Gombok a Kezelés lapon

A következő táblázat a Művelet panel **Kezelés** lapján elérhető műveletek leírását tartalmazza.

| Gomb | Leírás |
|---|---|
| Dokumentumok bevételezve | A hajóút frissítése úgy, hogy a **Kapott dokumentumok** beállítása *Igen* legyen. Ezzel a gombbal zárolhatja a cikket és/vagy a beszerzési sort, így azt nem lehet tovább frissíteni. |
| Szállítás alatt | Az **Hajóút állapota** mező frissítése a **[Partraszállítási költség paraméterei](landed-cost-parameters.md)** oldalon megadott úton lévő állapotra. A folyamaton nincs további logika. A [Követési vezérlőközpont](delivery-information-setup.md) beállításai alapján a hajóút automatikusan is frissíthető az átszállítási állapotra.
| Költségszámításra kész | Az **Hajóút állapota** mező frissítése a **[Partraszállítási költség paraméterei](landed-cost-parameters.md)** oldalon megadott költségszámításra kész állapotra. Egy hajóút költsége akkor számolható el, ha minden számla feldolgozásra került (a készletszámlák és az hajóút költségszámlái is), és az árukat bevételezték. Ha egy hajóúthoz társított becsült költségek nem lettek elszámolva, akkor hiba történik a hajóút költségszámításának feldolgozásakor. |
| Költség elszámolva | Az esetleges költségszámítási szabálytalanságok tisztítása, ha már létezik számla minden beszerzési rendelésre és hajóútra vonatkozó költségre. Ha megnyomja ezt a gombot, megjelenik a **Hajóút frissítése – Költség elszámolva** párbeszédpanel. Itt választhatja a szokásos pénzügyi dátumon való feladást, vagy megadhat egy feladási dátumot, majd futtathatja a műveletet. Tetszőleges alkalommal újrafuttathatja a műveletet. A **Hajóút frissítése – Költség elszámolva** párbeszédpanel használatával is ütemezheti a művelet futtatását időszakos feladatként (kötegelt feladat). Javasoljuk, hogy a műveletet rendszeresen, kötegelt feladatként futtassa. |
| Bevételezési lista feladása | Bevételezési lista feladása a hajóúton található összes beszerzésirendelés-sorhoz. Többvállalatos hajóút használata esetén minden vállalathoz egy új bevételezésilista-feladási párbeszédpanel jelenik meg, és azt minden jogi személy esetében fel kell dolgozni. |
| Termékbevételezés feladása | Termékbevételezés feladása a hajóúton található összes beszerzésirendelés-sorhoz. A hajóúthoz kapcsolódó beszerzésirendelés-sorok termékbevételezési folyamata csak akkor lesz használva, ha az áruk **nem** mennek át úton lévő áruk feldolgozásán. Ha az áruk átmennek úton lévő áruk feldolgozásán, akkor egy hibaüzenet jelenik meg, amikor megpróbálja feladni a termékbevételezést egy beszerzésirendelés-sorhoz. Többvállalatos hajóút használata esetén minden vállalat számára új szállítólevél-feladási párbeszédpanel nyílik meg. |
| Számlafeladás | Számla feladása a hajóúton található összes beszerzésirendelés-sorhoz. Ha az áruk a hajóúton áthaladnak az úton lévő áruk feldolgozásán, a beszerzésirendelés-sorok számlázása a bevételezési folyamat végrehajtása előtt történik meg. Az eredeti beszerzési rendelés számlázásakor a program az eredeti beszerzésirendelés-sorokhoz társított úton lévő áruk rendeléseket fogja létrehozni. Ezeket a rendeléseket ezután bevételezheti a raktár. Többvállalatos szállítmányok használata esetén minden vállalat számára új számlafeladási párbeszédpanel nyílik meg. |
| Átmozgatási rendelések szállítása | Átszállítási rendelés hajóútjának feladása a hajóúton található összes átszállításirendelés-sorhoz. Ha ez a gomb be van jelölve, akkor csak az átszállítási rendelések érhetők el frissítésre. |
| Átmozgatási rendelés bevételezése | Átszállítási rendelés bevételezésének feladása a hajóúton található összes átszállításirendelés-sorhoz. |
| Úton lévő áruk bevételezése | Minden olyan rendelési sor bevételezése, amely úton van a hajóúton. Ez a gomb egyike annak a három lehetőségnek, amelyek a hajóúton úton lévő áruk bevételezésére használhatók. (A másik két lehetőség az **Érkeztetési napló létrehozása** gomb, amely később ebben a táblában és a raktári alkalmazásban van leírva). Ez a beállítás a legegyszerűbb választási lehetőség, és feldolgozza az úton lévő áruk raktárából a végső célraktárba úton lévő árukat. Ha jobban szabályozni szeretné a folyamatot, használja az érkeztetési naplót vagy egy mobileszközt az árubevételezés feldolgozására. |
| Automatikus költségek keresése | Keresse meg a vonatkozó hajóútköltségeket. Ha ezek a költségek már megtalálhatóak vagy frissítve vannak, a következő üzenet jelenik meg: „Nem számlázott költségsorok léteznek. Felül kívánja írni őket?” Minden olyan költség megtalálható, amely a hajóúthoz nem volt társítva a létrehozásakor. A hajóúthoz kapcsolódó és számlázott hajóútköltségek nem írhatók felül. |
| Érkezési napló létrehozása | <p>Az **Érkeztetési napló létrehozása** párbeszédpanel megnyitása, ahol létrehozhat egy érkeztetési naplót, amely megadja a helyet. A párbeszédpanel a következő lehetőségeket teszi elérhetővé:</p><ul><li>**Létrehozás az úton lévő árukból** vagy **Létrehozás átszállítási rendelésből** – A beállítás címkéje attól függően változik, hogy az úton lévő áruk feldolgozását használja-e. Állítsa *Igen* beállításra egy érkeztetési naplóoldal megnyitásához, amely lehetővé teszi a hajóúthoz kapcsolódó úton lévő áruk szokásos érkeztetési naplójának feldolgozását. Ha a cikk már megérkezett a végső célraktárba, akkor nem lesz hozzáadva az érkeztetési napló soraihoz.</li><li>**Mennyiség inicializálása** – Állítsa a beállítást *Igen* értékre a bevételezett mennyiség inicializálásához a hajóút sorában megadott árumennyiség alapján. Ha az hajóútsort részben bevételezték már, ez a mennyiség lesz a fennmaradó mennyiség. Javasoljuk, hogy állítsa ezt a beállítást *Igen* értékre.</li><li>**Létrehozás rendeléssorokból** – A beállítás *Igen* értékre állításával a rendelési sorokban megadott értéket veszi át.</li></ul><p>Ez a gomb egyike annak a három lehetőségnek, amelyek a hajóúton lévő áruk bevételezésére használhatók. (A többi lehetőség az ebben a táblában korábban ismertetett **Úton lévő áruk bevételezése** gomb, és a raktári alkalmazás.)</p> |
| Elhatárolt költségek | Olyan költségeket lehet elhatárolni, amelyekben a költségtípushoz meg van adva főkönyvi számla a tartozik tételhez. Ez a gomb általában akkor használatos, amikor a készlet szállítás közben van, vagy amikor az árukat bevételezték és számlázták. |
| Összesített költségek | Költségek áthelyezése a szállítókonténer szintjéről a hajóút szintjére. Ezt a gombot megosztott szolgáltatások/szállítás esetén használhatja, ahol több entitás osztozik egy szállítókonténeren vagy egy kartonterületen. Például az hajóúton egy 40 méteres szállítókonténer és egy 20 méteres szállítókonténer található, és az arányosítás térfogat szerint történik. Ebben az esetben előfordulhat, hogy a 20 méteres szállítókonténerben található helyet megosztó vagy használó áruk/entitások büntetést kapnak. A költségek egyenlő elosztása érdekében egyes szervezetek például át kívánják utalni a költségeket az hajóútra, és az útszintű arányosítási módszer szerint elosztani őket. |
| Utazási sablon módosítása | Párbeszédpanel megnyitása, ahol módosíthatja az út sablonját. A sablon módosítása után a hajóút költségei törlődnek. Emiatt lehet, hogy be ki kell választani az **Automatikus költségek megkeresése** (lásd a táblázat korábbi leírását) lehetőséget, vagy manuálisan újra hozzá kell adni a költségeket. |

### <a name="buttons-on-the-general-tab"></a>Gombok az Általános lapon

A következő táblázat a Művelet panel **Általános** lapján elérhető gombok leírását tartalmazza.

| Gomb | Leírás |
|---|---|
| Bevételezések listája | Termékbevételezések listájának megnyitása a hajóúton található összes beszerzésirendelés-sorhoz. Többvállalatos hajóút használata esetén minden vállalat számára új bevételezési lista nyílik meg. Ha még nincs feldolgozva termékbevételezési lista, ez a gomb nem érhető el. |
| Termékbevételezés | Az úthoz kapcsolódó beszerzésirendelés-sorok termékbevételezési rekordját nyitja meg, amennyiben ez a rekord használatban van. Ha még nincs feladva termékbevételezés, ez a gomb nem érhető el. A termékbevételezési folyamat nem lesz használatban, ha az úton lévő áruk feladolgozását használja. |
| Cikk érkezése | Ha használja, nyissa meg a cikkérkeztetési naplót. |
| Nyomon követés | A **Bejövő nyomon követés** oldal megnyitása, ahol frissítheti az áruk érkezésének várható dátumát a szállítókonténerben és a hajóúton, majd frissítheti a beszerzésirendelés-sorok várható szállítási dátumait. |
| Költségek lekérdezése | <p>A **Költségek lekérdezése** oldal megnyitása, amelyen egy hajóút összes költsége látható.</p><p>A nézet módosításához válassza a Művelet panel **Nézet** elemét. Megtekintheti bármelyik szintet, valamint a cikk- és költségtípuskódot.</p><p>A **Költségek lekérdezése** oldalon csak azok a költségtípuskódok jelennek meg, amelyek közvetlenül kapcsolódnak a készlettranzakciókhoz. A költségtípuskódok törlésével a költségeket csoportosítva módosíthatja az oldalt. Ez a képesség akkor lehet hasznos, ha méreteket és színeket használ.</p><p>A **Költségek lekérdezése** lap csak azokat a költségtípuskódokat jeleníti meg, amelyekben a **Tartozik** mező beállítása *Cikk*.</p> |
| Úton lévő áruk rendelései | Az **Úton lévő áruk rendelései** oldal megnyitása, amely csak a kiválasztott hajóúthoz megadott úton lévő áruk nyilvántartását jeleníti meg. |

## <a name="lines-view"></a>Sorok nézet

A **Sorok** nézet megnyitásához nyisson meg egy hajóutat, majd válassza a hajóút fejlécének jobb felső részén található **Sorok** lapot.

### <a name="information-on-the-voyage-header-fasttab"></a>Információk a Hajóút fejléc gyorslapon

A hajóút **Hajóút fejléce** gyorslapon található **Sorok** nézete a hajóutat leíró alapvető információkat tartalmazza. A gyorslapon megjelenő mezők nagy része a **Fejléc** nézetben is megjelenik, amint azt a témakör későbbi része ismerteti.

### <a name="information-on-the-voyage-lines-fasttab"></a>Információk a Hajóút sorai gyorslapon

A hajóút **Hajóút sorai** gyorslapjának **Sorok** nézete a hajóút adataihoz és a hajóút szintjén érvényes költségszámítási adatokhoz kapcsolódik. Itt áttekintheti a szállítókonténereket, a leveleket és a hajóúthoz kapcsolt cikkeket. A hajóúton lévő cikkek ára és mennyisége is megjelenik. A megfelelő hivatkozás kiválasztásával bármely felsorolt szállítókonténert vagy levelet meg lehet tekinteni.

### <a name="information-on-the-line-details-fasttab"></a>Információk a Sor részletei gyorslapon

Az hajóút **Sorok** nézetében található **Sor részletei** gyorlap további információkat biztosít a **Hajóút sorai** gyorslapon jelenleg kiválasztott sorról. Ne feledje, hogy ez a gyorslap részletes adatokat tartalmaz arról, hogy az egyes sorok milyen pozícióban vannak a konténerben és a deklarált mennyiségükről.

## <a name="header-view"></a>Fejlécnézet

A **Fejléc** nézet megnyitásához nyisson meg egy hajóutat, majd válassza a hajóút fejlécének jobb felső részén található **Fejléc** lapot.

### <a name="settings-on-the-general-fasttab"></a>Az Általános gyorslap beállításai

Az alábbi táblázat leírja azokat a mezőket, amelyek az hajóút **Fejléc** nézetében, az **Általános** gyorlapon érhetők el.

| Mező | Leírás |
|---|---|
| Út | Adja meg a hajóút vagy a járat számát. |
| Foglalási hivatkozás | Ha a szállítmányozó vagy a szállítmányozó központ egy hivatkozási számot ad meg a hajóút azonosításához (azaz a szállítmányozó vagy a szállítmányozó központ belső hivatkozását), adja meg itt. |
| Hajó | Adja meg vagy válassza ki a hajót. Ha a hajó nincs értékként felsorolva, akkor a hajó azonosítóját megadhatja szabad szövegként. Ebben az esetben a főtábla nem frissül, hogy később ki lehessen választani a hajó azonosítóját ebben a mezőben. |
| Külső útazonosító | Adja meg az út nyilvánosan elérhető azonosítóját (például a járat számát). |
| Alapvető légi fuvarlevél/fuvarlevél | Adja meg a fő légi fuvarlevél vagy a fuvarlevél számát. Ezt az értéket légi szállításkor lehet megadni. |
| Házi légi fuvarlevél/fuvarlevél | Adja meg a házon belüli légi fuvarlevelet vagy fuvarlevelet a szállítókonténerhez. |
| Bérelhető | Jelölje be ezt a jelölőnégyzetet annak jelzésére, hogy a konténer olyan kölcsönkonténer, amelyet vissza kell szolgáltatni. |
| Leírás | Adja meg a hajóút leírását, hogy könnyebb legyen a felismerése. |
| Út állapota | A hajóút állapota. Az értékek a következők lehetnek: *Létrehozva*, *Úton*, *Beérkezett dokumentumok* és *Költség elszámolva*. A mező számítása nem a logika alapján történik. Csak a feladási műveleten keresztül frissül. A *Költség elszámolva* érték azt jelzi, hogy a készletre és az összes hajóútköltségre vonatkozó számla beérkezett. Ha nem érkezik számla, egy hajóút nem éri el a *Költség elszámolva* állapotot. |
| Beszerzési rendelés állapota | A hajóúttal kapcsolatos beszerzési rendelések között elért legmagasabb állapot. |
| Dokumentumok bevételezve | Ez az érték jelzi, hogy a vállalat megkapta-e a hajóúttal kapcsolatos összes dokumentumot. Az érték módosításához a Válassza a Művelet panel **Kezelés** lapján, a **Hajóút frissítése** csoportban a **Kapott dokumentumok** lehetőséget. |
| Szállítmányozási vállalat | Válassza ki a hajóúthoz a szállítmányozó vállalatot. Ez a mező az automatikus költségek meghatározására használható. |
| Név | A **Szállítmányozó vállalat** mezőben kiválasztott vállalat neve. |
| Mértékegység | Ez a mező lehetővé teszi egy mérték automatikus költségben történő beállítását. A mértékeket gyakran használják azok a szervezetek, amelyek nem ismerik az áruk egyedi mennyiségét vagy súlyát, de pontosabb arányosítást igényelnek, mint amit az összeg vagy mennyiség biztosít. A fuvarozó megadja a súlyt vagy a köbméteres mértéket, és azt elhelyezheti egy cikk vagy a beszerzési rendelés szintjén. A paraméter kiválasztása esetén automatikusan frissíthető, illetve manuálisan is meg lehet adni. |
| Mértékegység | A **Mérték** mezőben taláklható számra vonatkozó mértékegység. |
| Raklapok száma | A raklapok számának megadása a hajóút sorában. A mező automatikusan frissül, ha a **Kartonok számának automatikus frissítése** beállítás *Igen* értékű a **Partraszállítási költség** oldal **Általános** lapján. |

### <a name="settings-on-the-delivery-fasttab"></a>A Szállítás gyorslap beállításai

Az alábbi táblázat leírja azokat a mezőket, amelyek a hajóút **Fejléc** nézetében, a **Szállítás** gyorslapon érhetők el.

| Mező | Leírás |
|---|---|
| Létrehozás dátuma és időpontja | A hajóútrekord létrehozásának dátuma és ideje. |
| Gyári átvétel dátuma | Ez a mező a hajóúthoz kapcsolódó beszerzési rendelések közül a legkorábbi gyári dátumot adja meg. A gyári dátum a beszerzési rendelés fejlécében érhető el, és a követési vezérlő funkció használatával frissíthető. |
| Szállítási dátum | Az a becsült dátum, amikor a repülő vagy hajó elhagyja a kiindulási pontot. |
| Indulás dátuma | Az indulás dátuma általában az a dátum, amikor a repülőgép vagy hajó ténylegesen elhagyja a tengerentúli kikötőt. A szállítási dátumnak és az indulási dátumnak nem kell megegyezni. Az **Indulás dátuma** mező csak tájékoztatásra szolgál. Ez a dátum nem használatos a várható szállítási dátum becslésére. A rendszer a nyomon követési ellenőrzés szolgáltatás segítségével becslést ad a várható szállítási dátumra, és ezt a mezőt be lehet állítani úgy, hogy a követési ellenőrzés funkció automatikusan kitöltse azt. |
| Üzletbe kerülés dátuma | Ez a mező azt a legkorábbi dátumot adja meg, amikor a hajóúthoz kapcsolódó beszerzési rendelésekből származó áruk elérhetők lesznek értékesítésre. |
| Becsült szállítási dátum | A becsült szállítási dátum általában az a dátum, amikor az áruk beérkeznek a raktárba. Ez a mező csak tájékoztatásra szolgál. Nem használható az áruk alaptervezésére. A beszerzésirendelés-sorban található várt szállítási dátum a hajóúton történő árutervezéshez szükséges, és a követési vezérlő funkcióval frissül. A mező beállítható úgy, hogy ki legyen töltve a követési vezérlő funkcióval. |
| Tényleges szállítási dátum | A hajóúthoz kapcsolódó áruk alapján a legkorábbi szállítási dátum. |
| A becsült érkezési időpont a szállítási kikötőnél | Adja meg azt a dátumot, amikorra a hajóút várhatóan megérkezik a szállítási kikötőbe a szállítmányozó által megadott információk alapján. |
| Az eredeti dokumentumok beérkeztek | Adja meg az eredeti dokumentumok beérkezési dátumát. |
| Ügynök tanácsa szerint | A közvetítő értesítési dátumának megadása. |
| Eredeti fuvarlevél elküldve | Az eredeti fuvarlevél elküldésének dátuma. |
| Kiadott áruk | Adja meg azt a dátumot, amikor az árukat kiadták a vámkezelésből. |
| Vevői találkozó | Adja meg a vevő találkozójának dátumát, amely az a dátum, amikorra a vevő várhatóan tulajdonosa lesz az áruknak. |
| Kiszállítva a raktárba | Adja meg azt a dátumot, amikor az árut a raktárba szállították. |
| Ellenőrzési dátum | Adja meg az ellenőrzési dátumot. |
| Szállítási utasítások | Adja meg a szállítási utasítások beérkezési dátumát. |
| Szállítás módja | Ez a mező az hajóút szállításának módszerével és az adott szállítási módhoz kapcsolódó automatikus költségek költségkiválasztásával kapcsolatban tartalmaz tájékoztatást. |
| Kiindulási kikötő | Az a szállítási kikötő, amelyből a hajóút indul. |
| Célkikötő | Az a szállítási kikötő, ahvá a hajóút megérkezik. A szállítókonténereknek különböző kikötői lehetnek, mivel a hajó több kikötőnél is megállhat. A „cél” kikötő megadásával a szállítókonténer szintjén pontos kikötői adatokat ad meg a hajóúton található minden szállítókonténerhez. A fuvarhoz kapcsolódó automatikus költséget a szállítókonténer típusa, a „cél” és a „kiindulási” kikötő kombinációja határozza meg. |
| Helyi fuvarozó | Ez a mező csak tájékoztatásra szolgál. A helyi szállítmányozónak kiválaszthatónak kell lennie a szállítói táblából. |
| Helyi szállítás dátuma | Az a dátum, amikorra a helyi szállítás le van foglalva. Ez a mező segítséget ad a raktárnak a tervezésben. |
| Helyi szállítás időpontja | Az az idősáv, amikorra a helyi szállítás le van foglalva. Ez a mező segítséget ad a raktárnak a tervezésben. |
| Utazássablon | A hajóúthoz megadott útsablon. Az útsablon használatával lehet megadni a szállítókonténer és a hajóút „cél” és „kiindulási” kikötőjét. Ezek az értékek viszont segítik a hajóúthoz kapcsolódó automatikus költségek azonosítását. |

### <a name="settings-on-the-other-fasttab"></a>Az Egyéb gyorslap beállításai

Az alábbi táblázat leírja azokat a mezőket, amelyek az hajóút **Fejléc** nézetében, az **Egyéb** gyorslapon érhetők el.

| Mező | Leírás |
|---|---|
| Megjegyzések | A hajóútra vonatkozó kiegészítő információk megadása. |
| Értékelés dátuma | A hajóúthoz kapcsolódó beszerzési rendelések legkorábbi gyári dátumát adja meg. |
| Függőben lévő út | Ezzel jelezheti, hogy a szállítmány vagy hajóút útnak indult-e. Ez csak tájékoztatásra szolgál.  |
| Szállítókonténerek átnevezése | Egynél több konténert tartalmazó hajóút esetén a még nem bevételezett konténerek száma. |

## <a name="voyage-update-periodic-tasks"></a>Hajóútfrissítés ismétlődő feladatai

A **Partraszállítási költség** modul számos hajóúthoz kapcsolódó időszakos feladatot tartalmaz, amelyek a hajóutak tömeges frissítésére alkalmasak. Az időszakos feladatok futtatásához vagy ütemezéséhez kattintson a **Partraszállítási költség \> Időszakos feladatok \> Hajóút frissítései** lehetőségre, majd válasszon a következő feladattípusok közül:

- **Kapott dokumentumok** – Ezzel a feladattal egyszerre több hajóútra is át lehet állítani a **Kapott dokumentumok** beállítást *Igen* beállításra. A **Szűrő** beállítások segítségével meghatározhatja a frissíteni kívánt hajóútkészletet.
- **Úton** – Ez a feladat lehetővé teszi, hogy az **Hajóút állapota** mezőt úton állapotra állítsa be, amely a **[Partraszállítási költség paraméterei](landed-cost-parameters.md)** oldalon állítható be egyszerre több hajóúthoz. A **Szűrő** beállítások segítségével meghatározhatja a frissíteni kívánt hajóútkészletet.
- **Költségszámításra kész** – Ez a feladat lehetővé teszi, hogy az **Hajóút állapota** mezőt költségszámításra kész állapotra állítsa be, amely a **[Partraszállítási költség paraméterei](landed-cost-parameters.md)** oldalon állítható be egyszerre több hajóúthoz. Ezt a feladatot általában rendszeres ütemezésre kell beállítani.
- **Költség elszámolva** – Ezzel a feladattal az **Hajóút állapota** mezőt költség elszámolva állapotra állíthatja be, amely a **[Partraszállítási költség paraméterei](landed-cost-parameters.md)** oldalon állítható be egyszerre több hajóúthoz, feltéve, hogy a költségeik elszámolásra kerültek, de még nem lettek frissítve a hajóúton. Ezt a feladatot általában rendszeres ütemezésre kell beállítani.
