---
title: Pufferprofil és szintek
description: Ez a cikk a pufferprofilokkal és -szintekkel kapcsolatban tartalmaz tájékoztatást, amelyek meghatározzák az egyes felállási pontonként megtartható minimális és maximális készletszinteket.
author: t-benebo
ms.date: 06/30/2022
ms.topic: article
ms.search.form: EcoResProductDetailsExtended, ReqItemDecoupledLeadTime
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2022-06-30
ms.dyn365.ops.version: 10.0.28
ms.openlocfilehash: dd72332abefd31fd391ff66931a5abae0efb08de
ms.sourcegitcommit: 529fc10074b06f4c4dc52f2b4dc1f159c36e8dbc
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/22/2022
ms.locfileid: "9186567"
---
# <a name="buffer-profile-and-levels"></a>Pufferprofil és szintek

[!include [banner](../../includes/banner.md)]
[!INCLUDE [preview-banner](../../includes/preview-banner.md)]

Miután azonosította az adatkeresési pontokat (azok a kulcselemek, amelyek stratégiailag készleten maradnak), el kell döntenie, hogy mennyi készletet (puffert) tart az egyes cikkeknél. Ez a feladat az igényvezérelt anyagok erőforrás-tervezésének (DDMRP) második lépése.

## <a name="buffer-levels-and-zones"></a>Pufferszintek és zónák

A DDMRP-ben minden készletpuffer három értékből áll: a minimális mennyiségből, a maximális mennyiségből és az újrarendelési pontból. Ezek az értékek három különbözeti zónát állapít meg, amelyeket a következő színkódok azonosítnak:

- **Piros zóna** – a minimális mennyiség alatti terület. A minimális mennyiség másik elnevezése a "piros felső része", és a tervezési stratégiát úgy kell megtervezni, hogy a készletszintek mindig e pont felett vannak.
- **Sárga zóna** – a minimális mennyiség és az újrarendelési pont közötti terület. Az újrarendelési pont másik elnevezése a "sárga felső". Ha eléri ezt a pontot, a rendszernek újra kell rendezve lennie.
- **Zöld zóna** – az újrarendelési pont és a maximális mennyiség közötti terület. A maximális mennyiséget zöld színnel is nevezik. Ez a pont az a maximális szint, amely felett a készletet feltöltik.

A következő ábra mutatja be a három színzónát, és azt, hogy hogyan viszonyulnak a minimális mennyiséghez, maximális mennyiséghez és újrarendelési ponthoz.

![DDMRP pufferzónák és szintek](media/ddmrp-buffer-levels.png "DDMRP pufferzónák és szintek")

## <a name="calculating-the-buffer-zones"></a>Pufferzónák számítása

Ez a szakasz bemutatja az egyes pufferzónák magasságának kiszámítását.

A sárga zónát általában előbb számítják ki. Ez a zóna a rendelés megérkezéséig a rendelés alatt felhasznált mennyiséget jelöli. Más szóval a feltöltés átfutási ideje alatt várható felhasználás. Számítása a következő egyenlet használatával történik:

- **Sárga zóna** = *Átlagos napi használati idő (ADU)* *×upled átfutási ideje*

Az *összetolt* átfutási idő azt az időt jelenti, amely egy cikk előállításához vagy fogadásához szükséges, ha a függetlenítő pontok mindig készleten vannak. Ez általában több, mint *az* alaptervezésben hagyományosan használt halmozott átfutási idő. A helyes pufferbeállítások azért fontosak, hogy a tartalékpontok mindig készleten vannak, de ne legyen készleten túl készleten.

A piros zóna számítása a következő egyenletekkel történik:

- **Piros alap** = *- ADU* × *× átfutási* *idő tényezője*
- **Piros biztonsági** = *piros ×* *variability tényezője*
- **Piros zóna Piros alap** = *piros* + *biztonsági*

A zöld zóna számítása a következő három egyenlet maximális eredményeként történik:

- *Minimális rendelési mennyiség*
- *ADU* × *rendelési ciklus*
- *Az aDU* × *, amely* *× átfutási idő tényezője szerint*

## <a name="calculating-average-daily-usage"></a>Átlagos napi felhasználás kiszámítása

A rendszer a naponta felhasznált összeg három megközelítés egyike szerint számítja ki:

- **Átlagos napi felhasználás (múlt)** – ez a megközelítés a tényleges múltbeli felhasználáson alapul.
- **Átlagos napi felhasználás (előre)** – ez a megközelítés az előre jelzett jövőbeli felhasználáson alapul.
- **Átlagos napi felhasználás (vegyes)** – ez a megközelítés a múltbeli és előre jelzett felhasználás súlyozott kombináción alapul.

### <a name="average-daily-usage-past"></a>Átlagos napi felhasználás (múlt)

A múltbeli ADU számítása átlagként történik, úgy, hogy hozzáadja az egyes napokon a megadott számú elmúlt napokon használt mennyiségeket, és elosztja a végösszeget a napok számán. Az alábbi ábra azt mutatja be, hogyan működik ez a megközelítés, amikor a számítás három nappal a múltba néz.

![Átlagos napi kihasználtság (múltbeli) diagram](media/ddmrp-adu-past.png "Átlagos napi felhasználás (múltbeli) diagram")

Az előző példában, ha a mai nap június 11-e, akkor az előző három nap (június 8., 9. és 10.) esetén az ADU 21.

- **ADU (múlt)** = (29 + 11 + 23) ÷ 3 = 21

### <a name="average-daily-usage-forward"></a>Átlagos napi felhasználás (előre)

Új termékek esetén előfordulhat, hogy nem tartalmaznak korábbi felhasználási adatokat. Ehelyett használhatja az előre jelzett ADU-t (például az előre jelzett igény alapján). Az alábbi ábra azt mutatja be, hogyan működik ez a megközelítés, amikor a számítás három nappal a jövőbe (a mai napot is beleértve) bemutatja.

![Átlagos napi felhasználás (előre) diagram.](media/ddmrp-adu-forward.png "Átlagos napi felhasználás (előre) diagram")

Az előző példában, ha a mai nap június 11-e, akkor a következő három nap (június 11., 12. és 13.) ADU 21,66 lesz.

- **ADU (előre)** = (18 + 18 + 29) ÷ 3 = 21,66

### <a name="average-daily-usage-blended"></a>Átlagos napi felhasználás (összeolvasva)

A blended ADU egyesíti az átlagos múltbeli és előrehozott felhasználást, amint azt az alábbi ábra mutatja.

![Átlagos napi használat (összetolt) diagram](media/ddmrp-adu-blended.png "Átlagos napi felhasználás (összetolt) diagram")

Az előző példában, ha a mai nap június 11-e, akkor az előző és a következő három nap (június 8.–13.) esetén az ADU 21,33 lesz.

- **ADU blended** = (*ADU elmúlt* + *ADU előre*) ÷ 2<br>= (21 + 21,66) ÷ 2<br>= 21,33

## <a name="buffer-calculation-factors"></a>Pufferszámítási tényezők

Minden egyes cikkhez meg lehet határozni két tényezőt, amelyek meghatározzák, hogy milyen nagyok a piros és a zöld zónák. Ily módon lehet kompenzálni a várható átfutási időt és igény változságát.

![Átfutási idő és változsági tényezők.](media/ddmrp-zone-factors.png "Átfutási idő és változsági tényezők")

Az első tényező az átfutási *idő tényezője*. Az érték 0 és 1 tizedesjegy között van. Minél hosszabb az átfutási idő, annál kisebbnek kell lennie az értéknek. Az Igény által vezérelt Intézmény a következő tartományokat javasolja:

- **Hosszú átfutási idő:** 0,20–0,40
- **Közepes átfutási idő:** 0,41–0,60
- **Rövid átfutási idő:** 0,61–1,00

A második tényező a *variability tényező*. Az érték 0 és 1 tizedesjegy között van. Minél nagyobb az igény változhatósága, annál kisebbnek kell lennie az értéknek. Az Igény által vezérelt Intézmény a következő tartományokat javasolja:

- **Kis variability:** 0,20–0,40
- **Közepes változhatóság:** 0,41–0,60
- **Nagy változhatóság:** 0,61–1,00

## <a name="buffer-calculation-examples"></a>Pufferszámítás – példák

Ebben a példában a készlet pozicionakciói között található [termelési példa folytatódik](ddmrp-inventory-positioning.md). Ebben a példában olyan pontokat jelölt ki, amelyek 21 napról öt napra csökkentették az átfutási időt, amint azt az alábbi ábra mutatja.

![Példa a lesiklott átfutási időre.](media/ddmrp-bom-decoupled-lead-time-example.png "Példa a lesiklott átfutási időre")

Tegyük fel például, hogy az ADU számítása 23 darab, és az előző példában látható módon az átfutási idő 5 nap. Ezekkel az értékekkel számítható ki a sárga zóna a következő egyenlet segítségével:

- **Sárga zóna** = *- ADU* × *× átfutási idő* = 115

![Példa a sárga zóna kiszámítására.](media/ddmrp-example-calc-yellow.png "Példa a sárga zóna kiszámítására")

A piros zóna számítása hasonlít a sárga zóna kiszámításához, de a sárga zóna változásához és átfutási időhez van kibillentyűzve. Ebben a példában tegyük fel, hogy az átfutási időt (tényező = 0,50) és a nagy igényű változhatóságot (tényező = 0,8) észlelte. Ha ezeket az értékeket a sárgazóna-egyenlet összetevőivel együtt felhasználja, akkor a következő egyenletek segítségével számíthatja ki a piros zónát:

- **Piros alap** = *- ADU* ×*× átfutási* *idő* tényezője = 57,5
- **Piros biztonsági** = *piros ×* *Variability factor* = 46
- **Piros zóna** = *piros bázis piros* + *biztonsági* értéke = 103,5

A rendszer 104 darabra (ea) kereki a piros zónát, mivel a darabokat egész számmal számolja.

![Példa a piros zóna számításához.](media/ddmrp-example-calc-red.png "Példa a piros zóna számításához")

A zöld zónaszámítás a sárgazóna-egyenlet összetevőit is tartalmazza, de minimális rendelési méretet, rendelési ciklust és átfutási idő tényezőt is lehetővé tesz. Ebben a példában tegyük fel, hogy nincs rendelési ciklus (ezért nincs időkorlát a rendelés gyakori megrendelésére), és a minimális rendelési mennyiség 10 darab. A zöld zóna számítása ezután a következő három egyenlet maximális eredményeként történik:

- *Minimális rendelési mennyiség* = 10
- *ADU* × *rendelési ciklus* = 0
- *ADU* ×*× átfutási* idő × *tényezője* = 57,5

A rendszer 58 darabra (ea) kereki a zöld zónát, mivel a darabokat egész számmal számolja.

![Példa piros zöld színnel való számításra.](media/ddmrp-example-calc-green.png "Példa zöldzóna-számításra")

A következő ábra a DDMRP-kben gyakran használt tölcsérkép segítségével összegzi a zónaszámítás eredményeit.

![A zónaszámítás eredményeinek összefoglalása](media/ddmrp-example-calc-summary.png "A zónaszámítás eredményeinek összefoglalása")

## <a name="dynamic-adjustments"></a><a name="dynamic-adjustments"></a> Dinamikus módosítások

A dinamikus módosítások segítségével igény-korrekciós *tényezőt* alkalmazhat a nagy és alacsony igényű időszakokban. Ez a tényező megszorzása az ADU-t a kiválasztott időszak összes számításában. A pufferzónák ezután később módosulnak. Ezt a tényezőt általában a kezdeti pufferértékek generálása után fogja alkalmazni, hogy az idő és a feltételek módosítása esetén finomhangolhatja őket. Ez a feladat a DDMRP harmadik lépése.

Például augusztusban több olyan igény lehet egy megfelelő termékre, amikor az emberek szabadságra megy. Ennek megfelelően az értékesítések várhatóan magasabbak lesznek. Ebben az **esetben** *a termék igénykorrekciós tényezője augusztusban minden hétre 1,5-re* lehet módosítani az értéket.

Ezzel a módszerrel kiszámíthatók az idő alatt a pufferértékek, majd a rendszer által megadottnál több információ alapján módosíthatók. A DDMRP teljes megvalósítása esetén minden nap új pufferértékeket számít ki egy kötegelt feladaton keresztül, és automatikusan elfogadja az értékeket. Ezt követően kötegelt feladatként futtatja a tervezést, és minden nap áttekinti a pufferek újratöltendő tervezett rendeléseit.

## <a name="implement-buffers-in-supply-chain-management"></a>Pufferek megvalósítása az Ellátásilánc-kezelésben

Ez a szakasz azt mutatja be, hogyan lehet végrehajtani a pufferzóna-stratégiát a Microsoftban Dynamics 365 Supply Chain Management. Abból indul ki, hogy már megtörténtek a cikk első felében körvonalazott elemzések és számítások.

### <a name="set-up-buffers-for-a-decoupling-point-item"></a><a name="set-up-buffers"></a> Pufferek beállítása a tatolási pontcikkhez

A következő lépések szerint állíthatja be a tusolási pont pufferértékeit.

1. Kattintson a **Termékinformációk kezelése \> Termékek \> Kiadott termékek** lehetőségre.
1. Válasszon egy kiadott cikket, amely be van állítva felfelé és felfelé. (További tájékoztatás: [Készlet pozicionása](ddmrp-inventory-positioning.md).)
1. A Munkaablak Terv lapján **válassza** a Cikkfedezet **lehetőséget**.
1. A Cikkfedezet **lapon** válasszon ki egy olyan cikkfedezeti rekordot, amely létrehoz egy lefedő pontot. (Ez a rekord egy fedezeti csoport nevét mutatja, amely a felfokozási pontok létrehozására van beállítva.)
1. Válassza ki az **Általános** fület.
1. Ha azt szeretné, hogy a rendszer az értékesítési előzmények, előrejelzések és fedezeti csoportok beállításai alapján minden nap vagy minden héten újraszámálja a pufferértékeket, kövesse a következő lépéseket:

    1. Az **időtúli pufferértékek beállítása** Igen *beállításra*.
    1. Egy üzenet jelzi, hogy a folytatás után alaphelyzetbe állítja a kézi pufferbeállításokat (**Minimum**, **Újrarendelési** **pont** és Maximum). Az **Új beállítás megtartása az Igen** beállítással.

    Ha a pufferbeállítások számítását vagy a pufferbeállításokat csak egyszer szeretné megadni, a következő lépéseket kell követnie:

    1. Állítsa a **pufferértékeket az idő beállításának** Nem *beállításra*.
    1. Állítsa a **cikkhez** kiszámított pufferértékekre a Minimum, **·** **Az** újrarendelési pont és a Maximum mezőt a jelen cikknél korábban ismertetett módon.

1. A következő mezők beállítása a cikk DDMRP-számításának befejezéséhez:

    - **Rendelési ciklus** – adja meg, hogy hány napnak kell eltelnie a cikk beszerzési rendelése között. Állítsa az értéket *nullára*, ha nincsenek rendelési korlátozások. Ez a mező a maximális mennyiség pufferét befolyásolja, amint azt a cikk korábban tárgyalja.
    - **Átlagos napi felhasználás** – a cikkhez tetszőlegesen megadhatja a becsült ADU-t. Ez a mező csak tájékoztatásra szolgál. Az érték számítása általában a pufferszámítások részeként történik.
    - **Rendelési küszöbérték** – adja meg az értékesítésre jogosult cikk napi értékesítésének minimális számát (ez okkal együtt magas az igény). A rendszer e mező segítségével növeli a tervezett rendelések újrarendelési mennyiségét a nagy igényű időszakokban. További információ az igényvezérelt [tervezésnél található](ddmrp-planning.md).

### <a name="calculate-or-enter-decoupled-lead-times"></a><a name="calc-lead-time"></a> Újraszámítási átfutási idők számítása vagy beírja

Olyan cikkek [esetében](#set-up-buffers), amelyeknél úgy dönt, hogy engedélyezi a rendszer számára a pufferzónák automatikus kiszámítását, a következő lépésekkel számíthatja ki vagy adhatja meg az összecsomópontos cikk átfutási időket.

1. Nyissa meg **a cikkfedezeti** lapot az összesítő pontcikkhez. (További tájékoztatás: [Pufferek beállítása a pontcikkhez](#set-up-buffers).)
1. Válassza ki azt a cikkfedezeti rekordot, amely létrehoz egy szűrési pontot.
1. Válassza a Pufferértékek **lapot**.
1. Ha a rácsban nem láthatók időszakok, **akkor** a műveletpanel Pufferértékek lapján válassza **az Időszakok hozzáadása lehetőséget**. A rendszer minden napi vagy heti időszak sorait kitölti a rácsban, attól függően, **hogy a minimális,**[...](ddmrp-inventory-positioning.md)*·* *a* maximális és az újrarendelési pontidőszak mező napi vagy heti beállítású-e. A rendszer elegendő sort ad hozzá a cikkhez hozzárendelt fedezeti csoporthoz megadott időkorlát eléréséhez.
1. Válassza ki azt az időszakot, amelyben ki szeretné számítani a teljes átfutási időt. (Ez az időszak általában az aktuális dátumot tartalmazó időszak.)
1. A műveletpanel Pufferértékek **lapján** **válassza a Lecsatolt átfutási idő számítása lehetőséget**.
1. A Kiszámított **átfutási idő** párbeszédpanelen állítsa be a következő mezőket:

    - **Anyagjegyzék** – válassza ki azt az anyagjegyzéket, amely alapján a számítást futtatni szeretné.
    - **Dátum** – válassza ki azt a dátumot, amikor a számítást futtatni szeretné. A rendelkezésre álló AKK-halmazt szűri a rendszer, hogy csak a kiválasztott dátumon aktívak láthatók.
    - **Mennyiség** – adja meg azt a mennyiséget, amelyről a számítást futtatni szeretné. A rendelkezésre álló anyagjegyzékek halmazát szűri a rendszer, hogy csak a megadott mennyiségre vonatkozó anyagjegyzékek jelennek meg.

1. A **számítás futtatásához és az** átfutási idő számítása párbeszédpanel bezárásához kattintson az **OK** gombra. A **kiválasztott időszakHoz a Leselepkedve** átfutási idő oszlopa most a számított értéket jeleníti meg.

### <a name="calculate-or-enter-average-daily-usage"></a><a name="calc-adu"></a> Átlagos napi használat számítása vagy beírja

Olyan cikkek [esetében](#set-up-buffers), ahol úgy dönt, hogy engedélyezi a rendszer számára a pufferzónák automatikus kiszámítását, a következő lépések szerint számítsa ki vagy adja meg az ADU-t egy további pontcikkhez.

1. Nyissa meg **a cikkfedezeti** lapot az összesítő pontcikkhez. (További tájékoztatás: [Pufferek beállítása a pontcikkhez](#set-up-buffers).)
1. Válassza ki azt a cikkfedezeti rekordot, amely létrehoz egy szűrési pontot.
1. Válassza a Pufferértékek **lapot**.
1. Ha a rácsban nem láthatók időszakok, **akkor** a műveletpanel Pufferértékek lapján válassza **az Időszakok hozzáadása lehetőséget**. A rendszer minden napi vagy heti időszak sorait kitölti a rácsban, attól függően, **hogy a minimális,**[...](ddmrp-inventory-positioning.md)*·* *a* maximális és az újrarendelési pontidőszak mező napi vagy heti beállítású-e. Ezenkívül a fedezeti csoportból az **Átfutási** **idő tényező és a Variability tényező** mező alapértelmezett értékeit is figyelembe veszik. Ezek az értékek szükség szerint szerkeszthetők az egyes sorokban.
1. Válassza ki azt az időszakot, amelyben ki szeretné számítani az ADU-t.
1. A műveletpanel Pufferértékek lapján **válassza** az Átlagos napi **használat számítása lehetőséget**. A rendszer megpróbálja összegyűjteni az ADU számításhoz szükséges adatokat a fedezeti [csoporthoz megadottak szerint](ddmrp-inventory-positioning.md).
1. Tegye a következők egyikét:

    - Ha a szükséges adatok rendelkezésre állnak, a számítás eredményét a program hozzáadja **az Átlagos napi használati oszlophoz**. Ebben az esetben nem szükséges művelet.
    - Ha a szükséges adatok nem állnak rendelkezésre, akkor a program nem ad hozzá automatikusan értékeket. Ebben az esetben manuálisan adja meg a becsült értékeket mindegyik sorhoz, ahol a pufferértékek számítását tervezi.

### <a name="calculate-and-apply-buffer-values"></a>Pufferértékek számítása és alkalmazása

Olyan cikkek [esetén](#set-up-buffers), ahol úgy dönt, hogy engedélyezi a rendszernek a pufferzónák automatikus kiszámítását, a következő lépések segítségével manuálisan elindíthatja a pufferértékek számítását.

1. A megfelelő felfutásipont-cikkhez konfigurálja a pufferszámítást [,](#set-up-buffers)[számítsa](#calc-lead-time) ki vagy adja meg az átfutási időket, és [számítsa](#calc-adu) ki vagy adja meg az összes vonatkozó időszak átlagos napi használatát, amint azt a jelen cikk ismerteti.
1. Nyissa meg **a cikkfedezeti** lapot az összesítő pontcikkhez.
1. Válassza ki a **Pufferértékek** lapot, amelynek már meg kell mutatnia az időszakok listáját.
1. Válassza ki azt az időszakot, amelyben a pufferértékeket ki szeretné számítani. (Ez az időszak általában az adott napot is magába foglalja.) A kiválasztott sornak már nem nulla **értéket kell tartalmaznie az Átlagos napi** **felhasználás és a Kiugró átfutási idő oszlopban**.
1. Szükség esetén **módosítsa** egy vagy több sor igénykorrekciós tényező mezőjét. A rendszer ezt a tényezőt alkalmazza minden **olyan pufferszámítás átlagos napi** használati értékére, ahol ez az érték van használatban. Ezzel a tényezővel korrigálhat a dátumok szerinti igény szerint (például munkaszüneti napok vagy szezonális cikkek esetén).
1. A Műveletpanel **Pufferértékek** **lapján válassza a Minimális, maximális és újrarendelési pont mennyiségének számítása lehetőséget**. A rendszer kiszámítja **és kitölti a Cikkfedezeti lap számított minimális**,**·** **újrarendelési pontját és Számított maximális** **oszlopát** a rácsban.
1. Ha befejezte a számított értékek áttekintését, alkalmaznia kell azokat. Ellenkező esetben nem lesz hatásuk. Ha számítást alkalmaz egy vagy több sorra, **akkor** a Számított minimum, **·** **a Számított újrarendelés és a Számított max** **. mező értékét a program ennek megfelelően átmásolja a Min**., **Az újrarendelési** **pont és a Maximális** érték oszlopba. Válasszon a következő gombok közül **a** Műveletpanel Pufferértékek **lapján**, a MűveletcsoportBan:

    - **Minden számítás elfogadása** – minden számított érték alkalmazása a rácson.
    - **Számítások elfogadása a kijelölt sorokra** – csak a kiválasztott sorokra vonatkozó számított értékek alkalmazása.
    - **Minden számítás elvetása** – a minimális mennyiségekre, maximális mennyiségekre és újrarendelési pontokra vonatkozó számított értékek elvetása a rácsban.
    - **A kiválasztott sorok számításának** elvetása – a minimális mennyiségekre, maximális mennyiségekre és újrarendelési pontokra vonatkozó számított értékek elvetása a kiválasztott soroknál.

### <a name="schedule-automatic-buffer-value-calculations"></a>Automatikus pufferérték-számítások ütemezése

Miután teljes körűen beállította a DDMRP beállításait, és megerősítette, hogy a várt módon működnek, valószínűleg be kell állítania egy kötegelt feladatot, amely a tényleges felhasználási adatok és/vagy a frissített előrejelzések alapján rendszeres időközönként újraszámol az ADU értékét és a kapcsolódó pufferértékeket. Ez az eljárás csak azokra a cikkekre vonatkozik, amelyeknél úgy dönt, hogy engedélyezi a rendszernek a [pufferzónák automatikus kiszámítását](#set-up-buffers).

A következő lépések szerint ütemezi az automatikus pufferérték-számításokat.

1. Menjen az Alaptervezés **\>\> DDMRP alaptervezése – pufferértékek \> számítása.**
1. A Pufferértékek **számítása** párbeszédpanelen állítsa be a következő mezőket:

    - **Átlagos napi használat kiszámítása** – *a* feladat minden futtatásakor az ADU érték Igen beállítással újraszámítható. A számítás kihagyásához *állítsa Nem* beállításra. Ez a beállítás általában *Igen*.
    - **Összegzett átfutási** idő számítása – *a* feladat minden futtatásakor újraszámíthatja ezt a beállítást Igen beállítással. A számítás kihagyásához *állítsa Nem* beállításra. Ez a beállítás általában *Igen*.
    - **Pufferértékek számítása** – a *feladat* minden futtatásakor a pufferértékek újraszámítása igenre állíthatja ezt a beállítást. A számítás kihagyásához *állítsa Nem* beállításra. Ez a beállítás általában *Igen*.
    - **A minimális,** maximális és újrarendelési pontra vonatkozó számítás elfogadása – *a feladat minden futtatásakor az Igen* beállítással automatikusan jóváhagyja és alkalmazza az újraszámolt pufferértékeket. Állítsa Nem *beállításra*, ha az újraszámolt értékeket nem hagyta jóvá. Ebben az esetben az újraszámolt **értékek** csak akkor lépnek hatályba, ha az egyes termékek cikkfedezeti lapján később manuálisan alkalmazza azokat. Ez a beállítás általában *Igen*.
    - **Alapterv** – válasszon egy olyan alaptervet, amely tartalmazza a számításban érintett cikkeket. A számítás a tervszűrőben található összes cikkre érvényes lesz, **amelyet** tovább korlátoznak a párbeszédpanel Szűrőbeállításai.

1. A kötegelt feladat **által** **·** **futtatott** rekordok halmazának korlátozására a Gyorslapra vonatkozó rekordokon a Lekérdezés párbeszédpanel megnyitásához válassza a Szűrő lehetőséget. Ez a párbeszédpanel pont úgy [működik](../../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md), mint az Ellátásilánc-kezelés többi háttérben futó feladatának esetében.
1. A Futtatás **a** háttérben gyorséta oldalon adja meg, hogyan, mikor és milyen gyakran kell a kiválasztott cikkekhez a kiválasztott számításokat végezni. A mezők ugyanúgy működnek, mint a Supply Chain Management más, [háttérben futó feladattípusai](../../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md).
1. Az **ÚJ feladat kötegelt feladatok várólistájára való felvételének az OK** gombra való felvétele a végrehajtáshoz.

### <a name="review-and-recalculate-decoupled-lead-times-for-all-items"></a>Az összes cikk újraszámolt átfutási időkének áttekintése és újraszámítása

A következő lépések szerint tekintse át és újraszámítsa a jogi személynél (vállalatnál) rendelkezésre álló összes átfutási időt.

1. Ugrás az Alaptervezés **\>\> DDMRP keresőmezőjére \> - átfutási idő**
1. Az Átfutási **idő** lapon tallózással és szűréssel keresse meg a keresett információkat. Ha egy cikkre még több információt is meg kívánt tekinteni, válassza ki a hivatkozását a **Cikkszám oszlopban**.
1. Ha bármely cikkhez újra szeretné számítani a teljes átfutási időt, jelölje ki a cikket, **majd** a munkaablakban válassza ki az újraszámítási átfutási idő számítása lehetőséget. **Megjelenik a Lesiklott átfutási idő** kiszámítása párbeszédpanel. Ez a párbeszédpanel [ugyanúgy](#calc-lead-time)**működik**, mint amikor a Cikkfedezet lapon kiszámítja ugyanannak a cikknek az átfutási időkét.
