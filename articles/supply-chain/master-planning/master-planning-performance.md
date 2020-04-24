---
title: Az alaptervezés teljesítményének javítása
description: Ez a témakör bemutatja azokat a különböző beállításokat, amelyek segítségével javítható az Alaptervezés teljesítménye és a problémák elhárítása.
author: t-benebo
manager: tfehr
ms.date: 12/18/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2019-05-31
ms.dyn365.ops.version: AX 10.0.0
ms.openlocfilehash: 01db8a02e57c61daf940e2f459124a857ced68cb
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/02/2020
ms.locfileid: "3213607"
---
# <a name="improve-master-planning-performance"></a>Az alaptervezés teljesítményének javítása

[!include [banner](../includes/preview-banner.md)]
[!include [banner](../includes/banner.md)]

Ez a témakör bemutatja azokat a különböző beállításokat, amelyek segítségével javítható az Alaptervezés teljesítménye és a problémák elhárítása. A paraméterekkel és beállításokkal, valamint az ajánlott konfigurációkkal és műveletekkel kapcsolatos információkat tartalmaz. A témakör tartalmazza továbbá az összes fontos paraméter összesítését, amelyet akkor kell figyelembe venni, ha régóta futtat Alaptervezési feladatokat.

Ez a témakör olyan rendszergazdák vagy informatikai felhasználók számára készült, akik képesek a problémák elhárítására. Emellett termelési vagy beszerzési tervezők számára is készül, mivel az üzleti tervezés követelményeihez kapcsolódó paraméterekkel kapcsolatban tartalmaz tájékoztatást. 

## <a name="parameters-related-to-master-planning-performance"></a>Az Alaptervezés teljesítményéhez kapcsolódó paraméterek

A különféle paraméterek befolyásolhatják az Alaptervezés futási idejét, és figyelembe kell venni azokat.

### <a name="number-of-threads"></a>Szálak száma

A **Szálak száma** paraméterrel beállíthatja az alapütemezési folyamatot, hogy jobban teljesítsen az adott adatkészleten. Ez a paraméter meghatározza az Alaptervezés futtatásához összesen használt szálak számát. Az Alaptervezés párhuzamos futását okozza, ami segít csökkenteni a futási időt. 

A **Szálak száma** paramétert a **Alaptervezés futtatása** párbeszédpanelen állíthatja be. Ennek a párbeszédablaknak a megnyitásához lépjen az **Alaptervezés \> Alaptervezés \> Futtatás \> Alaptervezés** lehetőségre, vagy válassza az **Alaptervezés** munkaterületen a **Futtatás** parancsot. Ha meg szeretné állapítani a paraméter legjobb értékét, akkor egy próbálgatáson alapuló folyamatot kell használnia. A következő képletek azonban a kezdeti érték kiszámítására használhatók:

- **Ha az iparág a gyártás:** (Szálak száma) = (Tervezett rendelések száma ÷ 1000)
- **Ellenkező esetben:** (Szálak száma) = (Cikkek száma ÷ 1000)

Az Alaptervezés során használt segítők számának kisebbnek vagy egyenlőnek kell lennie a kötegelt kiszolgálón engedélyezett szálak maximális számával. Ha a segítők száma meghaladja a kötegelt kiszolgálón található szálak számát, akkor az extra szálak nem végeznek munkát.

> [!NOTE]
> Ha a **Szálak száma** paramétert **0** (nulla) értékre állítja, azzal növeli az alaptervezés futási idejét. Ezért azt ajánljuk, hogy mindig olyan értéket adjon meg, amely nullánál nagyobb.

### <a name="number-of-tasks-in-helper-task-bundle"></a>A segítő feladatcsomagban található feladatok száma

A **Feladatcsomagban található feladatok száma** beállítás módosításával (amely a csomag méretét jelenti) csökkentheti a futási időt. Ez a beállítás határozza meg a cikkek mennyiségét, amelyet egyetlen segítő tervezett össze.

A **Feladatcsomagban található feladatok száma** paraméter értékét az **Alaptervezés paraméterei** oldal **Általános** lapjának **Teljesítmény** szakaszában állíthatja be (**Alaptervezés \> Beállítás \> Alaptervezés paraméterei**). Ennek a paraméternek a legjobb értéke az adatoktól függ. Ezért azt ajánljuk, hogy **1** értékkel induljon, majd próbálgatással határozza meg a legjobb értéket a beállításhoz.

Általában azt ajánljuk, hogy növelje a feladatok számát, amikor a cikkek száma nagyon nagy (több százezer). Ellenkező esetben csökkentse a feladatok számát. A következő iparágak esetében figyelembe kell venni ezeket a javaslatokat:

- A kiskereskedelmi és forgalmazói iparágban, ahol számos független cikk található, használjon számos segítőt, mivel nincs függőség a cikkek között. 
- A gyártóiparban, ahol számos anyagjegyzék (BOM-ok) és megosztott alösszetevő van, kevesebb segítőt használjon, mivel a cikkek közötti függőségek várakozási időket okozhatnak.

> [!TIP]
> Ha teljesítménnyel kapcsolatos problémák merülnek fel, ajánlott csökkenteni a **Feladatcsomagban található feladatok száma** beállítást **1** értékre. Ezután elkezdheti a próbálgatási folyamatot, amellyel megkeresheti a beállítás legjobb értékét. Általában a teljesítménnyel kapcsolatos problémák akkor jelentkeznek, amikor egy cikk feldolgozása hosszabb ideig tart, mint a fennmaradó cikkek feldolgozása. Ebben az esetben látni fogja, hogy az Alaptervezés futtatásakor két egymást követő, **Fedezet** állapottal rendelkező feladat futási ideje jelentősen eltér. Szélsőséges esetekben ez a különbség lehet, hogy akár 30 perc. A feladatoknak a feladatok időtartamát megvizsgálva lehet következtetni, hogy mennyi ideig fussanak a feladatok.

### <a name="use-of-cache"></a>Gyorsítótár használata

A **Gyorsítótár használata** paraméterrel beállíthatja az alapütemezési folyamatot, hogy jobban teljesítsen az adott adatkészleten. Módosítható például a következő eredmények elérése érdekében:

- Ha több gyorsítótárazást hajt végre, több adat gyűlik össze az adatmemóriában. A feltételezés az, hogy az adatok később kerülnek felhasználásra. Ha az adatok a memóriában vannak, néhány adatbázis-kérelemmel kevesebbre lesz szükség. Ha azonban több gyorsítótárazást hajt végre, a memória követelményei növekednek.
- Ha kevesebb gyorsítótárazást hajt végre, előfordulhat, hogy az adatbázisból gyakrabban kell lehívni ugyanazokat az adatokat. Az Alkalmazásobjektum-kiszolgáló (AOS) emellett kevés adatot tárol a memóriában a folyamat során.

Nehéz megjósolni, hogy melyik beállítás jobb, mert az egyes esetek nem csak az adatoktól függenek, hanem a hardvertől is. Mivel például a kisebb gyorsítótárazás az adatbázis-kiszolgálón további terhelést okoz, valószínűleg nem érdemes használni ezt a beállítást, ha az adatbázis-kiszolgáló már túl van terhelve.

A **Gyorsítótár használata** paraméter értékét az **Alaptervezés paraméterei** oldal **Általános** lapjának **Teljesítmény** szakaszában állíthatja be (**Alaptervezés \> Beállítás \> Alaptervezés paraméterei**). A gyorsítótárazás hatékonysága erősen függ az ügyféladatoktól. Ha például a gyorsítótárazott adatok később nem szükségesek, csak akkor pazarolja a memóriát, ha az ütemezési folyamat végéig tárolja az adatokat. Ebben az esetben, ha kisebb gyorsítótárazást állít be, előfordulhat, hogy a teljesítmény növekedni fog, mert az Alkalmazásobjektum-kiszolgálóhoz kevesebb memóriára van szükség, és a kiszolgáló erőforrásai felszabadulnak más feladatok számára.

> [!TIP]
> Általában azt ajánljuk, hogy **Gyorsítótár használata** paramétert a **Maximum** értékre állítsa be, mivel a paramétert egy teljesítménynövelő funkciónak szánták. Javasoljuk, hogy a paramétert **Minimum** értékre állítsa, ha helyszíni alkalmazást futtat, és korlátozott memóriával rendelkezik (körülbelül 2 gigabájttal \[GB\]).

### <a name="number-of-orders-in-firming-bundle"></a>A megerősítési kötegben lévő rendelések száma

A **A megerősítési kötegben lévő rendelések száma** paraméterben megjelenő szám határozza meg, hogy az egyes szálak/kötegek által egyszerre feldolgozható rendelések számát összesen. Ez az automatikus megerősítési folyamat párhuzamosságát okozza.

Az **A megerősítési kötegben lévő rendelések száma** paraméter értékét az **Alaptervezés paraméterei** oldal **Általános** lapjának **Teljesítmény** szakaszában állíthatja be (**Alaptervezés \> Beállítás \> Alaptervezés paraméterei**). Az automatikus megerősítési folyamat párhuzamossága az együtt feldolgozandó rendeléseken alapul. Ha a paraméter értéke például **50**, akkor minden egyes szál- vagy kötegfeladat egyszerre 50 rendelést tárol ki és együtt dolgozza fel őket. Javasoljuk, hogy a legjobb érték megkereséséhez használja a próbálgatás folyamatát. A következő képlet azonban a kezdeti érték kiszámítására használható:

(Rendelések száma csomagonként) = (Igényelt cikkek száma ÷ Szálak száma)

> [!NOTE]
> Ha **A megerősítési kötegben lévő rendelések száma** paramétert **0** (nulla) értékre állítja, akkor az automatikus megerősítési folyamatban nem fog megjelenni a párhuzamosság. Az egész folyamatot egyetlen kötegelt feladaton futtatja a program, és összesíti a futási idejét. Ezért az Alaptervezés futási ideje növekedni fog. Emiatt azt ajánljuk, hogy a paramétert **0** (nulla) értéknél nagyobb értékre állítsa.

### <a name="time-fences"></a>Időkorlát

Az időkorlátok meghatározzák, hogy az alaptervezés a jövőben mennyire előretekintve számítsa ki a számításokat és más követelményeket. Minél hosszabb az időkorlát, annál tovább tart az alaptervezés futtatása. Ezért az időkorlátot az üzleti szükségleteknek megfelelően kell megadni. Az időkorlátokkal kapcsolatos további tudnivalókat lásd: [Alaptervezés beállítása](master-planning-setup.md).

### <a name="actions"></a>Műveletek

Az időkorlátok között megtalálható a **Műveletkérő üzenet** paramétere is. A műveletkérő üzenetek számítása hosszabb üzemidőt okoz az alaptervezésben. Ha a műveletkérő üzenetek elemzése és alkalmazása nem rendszeresen történik (naponta, hetente és így tovább), fontolja meg a számítás kikapcsolását az Alaptervezés futtatása során. A számítás kikapcsolásához az **Alaptervek** oldalon (**Alaptervezés \> Beállítás \> Tervek \> Alaptervek**) állítsa a **Műveletkérő üzenet** időkorlátját **0** (nulla) értékre az éppen futtatott alapterv esetében. Győződjön meg arról is, hogy a **műveletkérő üzenet** beállítás minden fedezeti csoport esetében ki van kapcsolva.

### <a name="futures"></a>Határidők

A határidők számítása hosszabb üzemidőt okoz az alaptervezésben. Ha nem anyagjegyzéket tervez, vagy ha a késéseket nem kell átvinni a kínálatból a keresletbe a tervezés során, javasoljuk a határidős számítások kikapcsolását az alaptervezés során. A számítások kikapcsolásához állítsa a **Határidők** időkorlátját **0** értékre (nulla) az éppen futtatott alapterv esetében. Győződjön meg arról is, hogy a **Határidők** beállítás minden fedezeti csoport esetében ki van kapcsolva.

## <a name="one-heavy-routine-at-a-time"></a>Egyszerre csak egy megterhelő rutin

Az Alaptervezés ütemezésekor ne ütemezzen egy másik kötegelt feladatot ugyanarra az időpontra. Különösen ügyeljen arra, hogy ne ütemezzen egyidejűleg olyan egyéb megterhelő rutinokat, mint például a készletzárás.

## <a name="review-the-session-log"></a>A munkamenetnapló felülvizsgálata

A rendszer további információkat gyűjthet az Alaptervezés során futtatott feladatokról. Ha azt szeretné, hogy a rendszer gyűjtse be ezeket az adatokat, kapcsolja be a **Feldolgozási idő nyomon követése** beállítást az **Alaptervezés futtatása** párbeszédpanelen. A összegyűjtött adatok segítenek a futtatás torlódásainak megtalálásában. Ha például **A segítő feladatcsomagban található feladatok száma** beállítás értéke **1**, akkor megtalálhatja a leghosszabb élettartammal rendelkező elemet. Összehasonlíthatja a futási időket a különböző szálakhoz, amelyek állapota **Fedezet** állapota, és összehasonlíthatja az egyes feladatok időtartamát.

A rendszer alaptervezése futásainak ellenőrzéséhez kövesse a következő lépések egyikét.

- Az **Alaptervezés** munkaterületen válasszon ki egy alaptervet a legördülő listáról, majd az **Alaptervezés** csempén válassza ki az **Előzmények** elemet. Válasszon egy feladatot, majd a **Lekérdezések** lehetőséget a gyorslapon, majd a **Folyamatbeli tevékenység időtartama** elemet.
- Az **Alaptervek** lapon válasszon ki egy tervet a bal oldali ablakban, majd válassza a gyorslap **előzmények** pontját. Válasszon egy feladatot, majd a **Lekérdezések** lehetőséget a gyorslapon, majd a **Folyamatbeli tevékenység időtartama** elemet.

A munkamenetnapló áttekintésekor vegye figyelembe a következőket:

- A **Frissítés** értékének nem szabad hosszú időnek lennie (általában legfeljebb 30 percig kell tartania), viszont egyszálas.
- A **Terv másolása** értékének nem szabad hosszú időnek lennie (egy percig kell tartania).
- Az **Automatikus megerősítés** általában 30 percet igényel. A rendelések számának és a cikkek összetettségének függvényében azonban akár több óráig is eltarthat.
- Az **Automatikus megerősítés** időtartamának rövidebb időnek kell lennie, mint a **Fedezet** hosszának.
- A **Fedezet** értékének a többihez viszonyítva a leghosszabb időt kell igénybe vennie.
- A **Művelet** és a **Határidős üzenet** hosszú ideig is eltarthat, az adatok és az anyagjegyzékek számától függetlenül.

## <a name="filtering-of-items"></a>Cikkek szűrése

Az **Alaptervezés futtatása** párbeszédpanelen alkalmazott szűrők hatással vannak az Alaptervezés futási idejére. Lépjen az **Alaptervezés \> Alaptervezés \> Futtatás \> Alaptervezés** lehetőségre, vagy válassza az **Alaptervezés** munkaterületen a **Futtatás** parancsot. Ha bizonyos cikkeket ki szeretne hagyni a futtatásból, javasoljuk, hogy a szűrést a cikk életciklus-állapota alapján végezze (ne cikkszámok alapján). Amikor életciklus-állapot szerinti szűrést hajt végre, a frissítési folyamat rövidebb időt vesz igénybe, mint a cikkszámok szerinti szűrés.

## <a name="automatically-filter-by-items-with-direct-demand"></a>Automatikus szűrés cikkenként közvetlen igénnyel

Az Alaptervezés futási idejének javításához beállíthatja, hogy csak a közvetlen igényléssel rendelkező cikkeket foglalja magában. Ez a szűrő csak akkor használható, ha teljes Alaptervezés fut, és nincs más szűrő alkalmazva a **Szerepeltetni kívánt rekordok** mezőben. A szűrőkkel futtatott Alaptervezés figyelmen kívül hagyja az **Automatikus szűrés cikkenként közvetlen igénnyel** beállítást.

Az **Automatikus szűrés cikkenként közvetlen igénnyel** mező az **Alaptervezési paraméterek** lapon található, és mind előfeldolgozási, mind utófeldolgozási beállításokkal használható.

### <a name="pre-processing"></a>Előzetes feldolgozás
Az **Előfeldolgozás: Automatikus szűrés cikkenként közvetlen igénnyel** paraméter biztosítja, hogy az Alaptervezés előfeldolgozási fázisa csak olyan elemeket tartalmaz, amelyek megfelelnek a következő feltételek valamelyikének:
  - A cikkhez tartozik egy várható bevételezés vagy kiadás, például beszerzési rendelés, értékesítési rendelés, ajánlat, átmozgatási rendelés vagy termelési rendelés. 
  - A cikkhez tartozik cikkfedezet biztonsági készlettel (minimális aktuális készlet).
  - Az adott cikkre vonatkozó, a mai naptól előrejelzett igény.
  - Az adott cikkre vonatkozó, a mai naptól előrejelzett ellátás.
  - Az elem olyan folytonossági vonalakat tartalmaz, amelyeket még létre kell hozni a hívásközpont modulból.

> [!NOTE]
> A fizikailag elérhető aktuális készlettel rendelkező cikkek nem fognak egy követelménytranzakciót mutatni, mert nincs igény a cikkre.

### <a name="post-processing"></a>Utófeldolgozás
Az **Utófeldolgozás: Automatikus szűrés cikkenként közvetlen igénnyel** beállítás csak akkor releváns, ha az **Anyagjegyzék-verzió követelménye** be van állítva a fedezeti csoportjaiban. Ellenkező esetben nem kell engedélyeznie a paramétert. 

A fedezeti lépés megkezdése előtt van egy előzetes fedezeti lépés, amelynek során a rendszer újra feldolgozza az engedélyezett **Anyagjegyzék-verzió követelménye** fedezeti beállítással rendelkező cikkeket. Erre azért van szükség, hogy a szükséges anyagjegyzék-verzióból származó cikkek tervezése biztosítva legyen. Azon cikkek esetében, amelyeknél az előfeldolgozás során igény áll fenn, továbbra nem áll fenn igény, ezért ki kell azokat zárni a tervezési folyamatból.

## <a name="performance-checklist-summary"></a>Teljesítménnyel kapcsolatos ellenőrzőlista – összefoglalás

- **A szálak száma** – **0** (nulla) értéknél nagyobb értékre legyen állítva.
- **A segítő feladatcsomagban található feladatok száma** – **0** (nulla) fölötti értékre legyen állítva. (Használja a témakör korábbi részében megadott képleteket.)
- **A gyorsítótár használata** – Állítsa a **Maximális** értékre, kivéve, ha a rendszer alacsony memóriával rendelkezik.
- **A megerősítési kötegben lévő rendelések száma** – **0** (nulla) fölötti értékre legyen állítva. (Használja a témakör korábbi részében megadott képletet.)
- **Időkorlátok** – az üzleti szükségletekhez igazítsa.
- **Műveletek és határidők** – Tiltsa le a műveleteket és a határidőt, ha nem használja őket.
- **Egy megterhelő rutin egyszerre** – ne futtassa az alaptervezést a többi további megterhelő rutinnal együtt.
- **Vizsgálja felül a munkamenetnaplót.**
- **Cikkek szűrése** – Az életciklus-állapot használatával kizárhat az alaptervezésből bizonyos cikkeket. (Ne használja a cikkszámokat.)
