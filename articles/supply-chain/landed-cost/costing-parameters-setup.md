---
title: Költségszámítási paraméterértékek beállítása
description: A Partraszállítási költség modul beállításakor több közös értékkészletet is meghatározhat, amelyek akkor érhetők el, ha az alkalmazás más részében kiválasztja a költségszámítási paraméterértékek meghatározott típusait. Ez a témakör azt ismerteti, hogy miként kell ezeket az értékkészleteket beállítani.
author: sherry-zheng
ms.date: 12/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ITMCostTypeTable, ITMCostTypeGroup, ITMCostTransferGroup, ITMCostTemplateTable, ITMVolumetricDivisorTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-07
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 1bcce7af0a15add63f1d9c3b32563de0ab6698bd
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/29/2021
ms.locfileid: "7577648"
---
# <a name="costing-parameter-values-setup"></a>Költségszámítási paraméterértékek beállítása

[!include [banner](../../includes/banner.md)]

A **Partraszállítási költség** modul beállításakor értékenként több közös értékkészletet és kapcsolódó beállítást is meghatározhat. Ezek az értékek ezután akkor lesznek elérhetők, ha az alkalmazás más részében kiválasztja a költségszámítási paraméterértékek meghatározott típusait. Ez a témakör azt ismerteti, hogy miként kell ezeket az értékkészleteket beállítani.

## <a name="set-up-cost-type-codes"></a>Költségtípuskódok beállítása

A költségtípuskódok határozzák meg annak a költségnek a típusát, amely akkor merül fel, amikor az árukat partraszállítják a raktárba, vagy a hajóút partraszállítási költségeit. Bár általában növelik az áruk értékét, felhasználhatók az összegeknek a főkönyvbe történő elhatárolására is. A főkönyvi korrekciók akkor használatosak, amikor egy költség elhatárolása idő vagy hajóutak sorozata során történik, és a kiegyenlítés egyetlen tranzakcióban történik.

> [!NOTE]
> Ha a költségtípustábla meg van osztva jogi személyek között, a számlatükröt is meg kell osztani a jogi személyek között. Ellenkező esetben a feladási tranzakciók nem működnek megfelelően.

A költségtípuskódok beállításához kattintson a **Partraszállítási költségek \> Költségszámítás beállítása \> Költségtípuskódok** gombra. A Művelet panel gombjaival új költségtípuskódokat hozhat létre, szerkesztheti a meglévő kódokat, illetve törölheti a kiválasztott költségtípusokat.

Az alábbi táblázat bemutatja az egyes költségtípuskódokhoz rendelkezésre álló mezőket.

| Mező | Leírás |
|---|---|
| Költségtípus kódja | Adjon egy egyedi nevet a költségtípuskódnak. |
| Leírás | Adja meg a költségtípuskód leírását. |
| Szállítási díj használata | Akkor állítsa ezt a beállítást *Igen* értékre, ha a költségek értékének kiszámításához az hajóút árfolyamát (más néven kezelési árfolyamot) kell használni. Ebben az esetben a program a szokásos alapértelmezett vagy azonnali árfolyam helyett a szállítási árfolyamot használja a devizaszámlák átváltása során. |
| Jelentéskészítési kategória | Ez a mező a költségtípus jelentési kategóriáját határozza meg. A jelentések jelentési kategóriák vagy költségtípus szerint nyomtathatók. |
| Tartozás típusa | Itt kiválaszthatja, hogy a költségtípus a cikkre, a főkönyvi számlára vagy a szállítóra terhel-e. |
| Tartozás feladása | Ha a **Tartozás típusa** mező beállítása *Főkönyvi számla*, válassza ki a feladás leírását. |
| Tartozik számla | Ha a **Tartozás típusa** mező beállítása *Főkönyvi számla*, válassza ki a használni kívánt főkönyvi számlát. |
| Hitelkeret típusa | Itt kiválaszthatja, hogy a költségtípus a cikkre, a főkönyvi számlára vagy a szállítóra ír-e jóvá. |
| Követelés feladása | Ha a **Követelés típusa** mező beállítása *Főkönyvi számla*, válassza ki a feladás leírását. |
| Követel számla | Ha a **Követelés típusa** mező beállítása *Főkönyvi számla*, válassza ki a használni kívánt főkönyvi számlát. |
| Elszámolási számla | A költségtípus elszámoló számlájának kiválasztása. Javasoljuk, hogy az egyeztetés érdekében költségtípusonként egy külön elszámolószámlát adjon meg. |
| Elszámolóár feladási típusa | Ha elszámolóáras költségszámítást használ, válassza ki a feladás leírását. |
| Elszámolóár-eltérési számla | <p>Ha elszámolóáras költségszámítást használ, az itt megadott számlát használja a rendszer a különbözetek feladásakor. Ez a számla a **Cikkárak** oldalon található partraszállítási költség lebontását használja. Ez a részletezés az árak frissítésére használt időszakos rutin használatával jön létre.</p><p>Egy cikk elszámolóára például $15,00, a FOB $13,00, a fuvardíj pedig $2,00. Amikor a készlethez számlát kap, a cikk $15,00 értékkel lesz bevételezve, de a cikk esetében egy $2,00 összegű elszámolóár-különbözet van, mivel a tényleges FOB $13,00. Ez az eltérés a cikkfeladási profilban beállított elszámolóár-különbözet számlájára lesz feladva. Mivel a becsült fuvardíj $2,00, nincs különbözet a készletszámla feladásakor. A fuvarszámla beérkezésekor azonban a fuvardíj $2,50 egységenként. Emiatt egy $0,50 összegű különbözet kerül feladásra a megadott költségre. |
| Mozgóátlag-eltérési számla | <p>Ha mozgóátlagos költségszámítást használ, az itt megadott számlát használja a rendszer a különbözetek feladásakor.</p><p>Például a becsült fuvar $2,00. A fuvarszámla beérkezésekor azonban a fuvardíj $2,50 egységenként. Ezért egy $0,50 összegű különbözetet kell feladni.</p><p>Ha a **Helyesbítések feladása különbözetként** beállítás Értéke *Igen*, a **Partraszállítási költség paraméterei** oldalon a becsült és tényleges szállítási költségek közötti összes eltérést feladja a rendszer az itt megadott mozgóátlag-különbözeti számlára. Ha a **Helyesbítések feladása különbözetként** beállítás *Nem* értékű, a rendszer az alapfunkciókat alkalmazza, és a különbözetet vagy a készletre, vagy az itt meghatározott mozgóátlag-különbözeti számlára alkalmazza.</p> |
| Költségelhatárolási számla | Annak a számlának a kiválasztása, amely a költségbecslések elhatárolására használatos a beszerzési számla feladásakor. Ez a mező csak akkor használatos, ha a **Költségtípus díjelhatárolási számla használata** beállítása *Igen* a **Költségszámítás** gyorslapon, a **Partraszállítási költség paraméterei** oldal **Általános** lapján. |
| Költségszámla | Annak a számlának a kiválasztása, amely a szállító által kiszámlázott bejövő szállítási költségek rögzítésére használatos. Az érték tartozásként lesz feladva. Az ellenszámla a készlet különbözetszámlája. Ez a feladás csak akkor van használatban, ha a **Feladás főkönyvi költségszámlára** beállítás *Igen* értékre van állítva a **Kötelezettségek paraméterei** oldalon. |
| Különbözeti számla | Az a számla, amely a költségelhatárolások kiegyenlítésére szolgál a beszerzési számla feladásakor. Ez a mező csak akkor használatos, ha a **Költségtípus díjelhatárolási számla használata** beállítása *Igen* a **Költségszámítás** gyorslapon, a **Partraszállítási költség paraméterei** oldal **Általános** lapján. |

## <a name="vendor-cost-type-groups"></a>Szállító költségtípuscsoportjai

A szállítói költségtípuscsoportok segítik annak megállapítását, hogy hogyan találhatók meg és alkalmazhatók az *automatikus költségek* egy hajóútra. A hasonló importköltségű szállítók egymáshoz vannak kapcsolva. Például minden fejlődő piacról származó eladó ugyanazt a vámkulcsot fizeti ugyanolyan típusú termékre, amely egy közkeletű piacról származik.

A szállítói költségtípuscsoportokat a **Partraszállítási költség \> Költségszámítás beállítása \> Szállítói költségtípuscsoportok** helyen tarthatja karban. A **Szállítói költségtípuscsoportok** oldal egy rácsot biztosít, amely minden létező szállítói költségtípuscsoportot felsorol. A Művelet panel gombjaival lehet sorokat hozzáadni, eltávolítani és szerkeszteni a rácsban.

Az alábbi táblázat bemutatja a rács egyes soraiban rendelkezésre álló mezőket.

| Mező | Leírás |
|---|---|
| Szállító költségtípuscsoportjai | A szállítói költségtípuscsoport egyedi nevének (például *Feljlődő piacok* piacok) beírása. |
| Leírás | Adja meg a szállítói kköltségtípuscsoport leírását. Ez a leírás részletes adatokat nyújthat a szállítói csoporthoz társított költségszintről vagy költségtípusról. |

## <a name="item-cost-type-groups"></a>Cikk költségtípuscsoportjai

A cikk költségtípus-csoportok segítik annak megállapítását, hogy hogyan találhatók meg és alkalmazhatók az *automatikus költségek* egy hajóútra. Hasonló cikkek egymáshoz vannak kapcsolva. Például minden 5 százalékos vámkulcsú cikk egy bizonyos költségtípus-csoportba tartozik.

A cikk költségtípus-csoportokat a **Partraszállítási költség \> Költségszámítás beállítása \> Cikk költségtípus-csoportok** helyen tarthatja karban. A **Cikk költségtípus-csoportok** oldal egy rácsot biztosít, amely minden létező cikk költségtípus-csoportot felsorol. A Művelet panel gombjaival lehet sorokat hozzáadni, eltávolítani és szerkeszteni a rácsban.

Az alábbi táblázat bemutatja a rács egyes soraiban rendelkezésre álló mezőket.

| Mező | Leírás |
|---|---|
| Cikk költségtípuscsoportjai | A cikk költségtípus-csoport egyedi nevének (például *Vám 5%*) beírása. |
| Leírás | Adja meg a cikk költségtípuscsoport leírását. Ez a leírás részletes adatokat nyújthat a cikkcsoporthoz társított költségszintről vagy költségtípusról. |

> [!NOTE]
> A cikk költségtípusa a cikk **Kiadott termék** oldalának **Beszerzés** gyorslapján található **Költségtípus-csoport** mezővel kapcsolható a cikkhez.

## <a name="transfer-order-cost-type-groups"></a>Átmozgatási rendelés költségtípuscsoportja

Az átmozgatási rendelés költségtípuscsoportjai segítik annak megállapítását, hogy hogyan találhatók meg és alkalmazhatók az *automatikus költségek*. Hasonló cikkek egymáshoz vannak kapcsolva. Például minden 7 százalékos vámkulcsú cikk egy bizonyos költségtípuscsoportba tartozik.

Az átmozgatási rendelés szállítói költségtípuscsoportjait a **Partraszállítási költség \> Költségszámítás beállítása \> Átmozgatási rendelés költségtípuscsoportjai** helyen tarthatja karban. Az **Átmozgatási rendelés költségtípuscsoportjai** oldal egy rácsot biztosít, amely minden létező átmozgatási rendelés költségtípuscsoportot felsorol. A Művelet panel gombjaival lehet sorokat hozzáadni, eltávolítani és szerkeszteni a rácsban.

Az alábbi táblázat bemutatja a rács egyes soraiban rendelkezésre álló beállításokat.

| Mező | Leírás |
|---|---|
| Átmozgatási rendelés költségtípuscsoportja | Az átmozgatási rendelés költségtípuscsoport egyedi nevének (például *Vám 7%*) beírása. |
| Leírás | Adja meg az átmozgatási rendelés költségtípuscsoport leírását. Ez a leírás részletes adatokat nyújthat az átmozgatási rendelés költségtípuscsoportjához társított költségszintről vagy költségtípusról. |

> [!NOTE]
> Az átmozgatási rendelés költségtípusa a cikk **Kiadott termék** oldalának **Beszerzés** gyorslapján található **Átmozgatási rendelés költségcsoport** mezővel kapcsolható a cikkhez.

## <a name="cost-templates"></a>Költségsablonok

A költségsablonok használatával lehet beállítani olyan beállítások alapértelmezett értékeit, amelyekről a költségbecslést kapó felhasználók esetleg nem tunak. A költségsablonok segítségével csökkenthető a becslési folyamat összetettsége, azáltal, hogy minimálisra csökkentik azokat a végrehajtandó kiválasztásokat, amelyek alapján a felhasználóknak pontos becslést kell kapniuk.

A költségsablonok kezeléséhez kattintson a **Partraszállítási költségek \> Költségszámítás beállítása \> Költségsablonok** gombra. A **Költségsablonok** oldalon a bal oldali listaablak az összes aktuális költségsablont mutatja. A Művelet panel gombjaival sablonokat adhat hozzá, távolíthat el és szerkeszthet.

Az alábbi táblázat bemutatja az egyes sablonokhoz rendelkezésre álló beállításokat.

| Mező | Leírás |
|---|---|
| Költségsablon | Adjon egy egyedi nevet a költségsablonhoz. A név általában a sablon tényezőjét vagy költségszorzóját írja le. |
| Leírás | A költségsablon leírásának megadása. |
| Szállítmányozási vállalat | A költségsablonhoz társított szállítmányozó vállalat szállítói számlájának kiválasztása. |
| Szállítás módja | A cikk becsült költségének számítása során a költségsablonban használandó szállítási mód kiválasztása. Ez a mező segít meghatározni a költségbecslésben az árukhoz kapcsolódó automatikus költségeket. |
| Szállítási konténer típusa | A költségsablonhoz társított szállítókonténer típusának kiválasztása. Ez a mező segít meghatározni a költségbecslésben az árukhoz kapcsolódó automatikus költségeket. |
| Vámügynök | Válassza ki a költségsablonhoz társítani kívánt vámügynököt (szállítót). Ez a mező segít meghatározni a költségbecsléshez kapcsolódó automatikus költségeket. |
| Szorzó | Adja meg az áruk végső költségbecslésére alkalmazandó tényezőt. Ha például 10 százalékot szeretne hozzáadni a számított költségbecsléshez, *1,10*-et adjon meg. |

## <a name="volumetric-divisors"></a>Térfogatosztók

A térfogatosztók a térfogatsúly kiszámítására használhatók. Minden szállítmányozási/teherszállítási vállalat saját térfogatosztókat alkot. A vállalat osztói jellemzően eltérőek a szállítási módtól függően. Például a légi és a tengeri szállításnak gyakran nagyon különböző osztói vannak. Attól függően, hogy honnan szállít, a vállalat még összetettebb szabályokat hozhat.

Például egy légi csomag térfogata 3 köbméter (m³). A vállalat térfogati súly alapján számít fel díjat, és 6-os térfogatosztót alkalmaz. Ezt az osztót megszorozza a térfogattal a térfogati súly meghatározásához. Ezért ebben a példában a térfogati súly 3 × 6 = 18 kilogramm (kg).

A térfogatosztók beállításához kattintson a **Partraszállítási költségek \> Költségszámítás beállítása \> Térfogatosztók** gombra. A **Térfogatosztók** oldal egy rácsot biztosít, amely minden meglévő térfogatosztót felsorol. A Művelet panel gombjaival lehet sorokat hozzáadni, eltávolítani és szerkeszteni a rácsban.

Az alábbi táblázat bemutatja a rács egyes soraiban rendelkezésre álló mezőket.

| Mező | Leírás |
|---|---|
| Szállítmányozási vállalat | A térfogatosztóhoz társított szállítóvállalat szállítói számlájának kiválasztása. |
| Költségtípus kódja | A térfogatosztóhoz társított költségtípuskód kiválasztása. Ezzel a mezővel költségtípusokat lehet a jelentési időszakba tenni. A jelentések jelentési kategóriák vagy költségtípus szerint nyomtathatók. |
| Kiindulási kikötő | Válassza ki az „indulási” kikötőt, amelyre a térfogatosztó vonatkozik. |
| Térfogatosztó | A sorra vonatkozó térfogatosztó értékének megadása. A megadott értéket a rendszer *megszorozza* az egyes csomagok térfogatával, és így megállapítja a csomag térfogati súlyát. |
