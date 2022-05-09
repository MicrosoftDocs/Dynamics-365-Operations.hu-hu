---
title: A tervezésoptimalizálása illeszkedési elemzése
description: Ez a témakör azt mutatja be, hogyan lehet ellenőrizni az aktuális beállításokat és adatokat a Tervezésoptimalizálás funkció szolgáltatásaival szemben.
author: t-benebo
ms.date: 07/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: MpsFitAnalysis, MpsIntegrationParameters
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: bf63069c5f18fe67c7d7f538311853d79c0f4fe8
ms.sourcegitcommit: 9e1129d30fc4491b82942a3243e6d580f3af0a29
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/27/2022
ms.locfileid: "8649157"
---
# <a name="planning-optimization-fit-analysis"></a>Tervezési optimalizálás igazítási elemzése

[!include [banner](../../includes/banner.md)]

Az áttelepítési folyamat részeként elemezze a tervezési optimalizálás illeszkedési elemzésének eredményét. Ne felejtse el, hogy a tervezési optimalizálás hatóköre nem egyezik meg a beépített alaptervezés aktuális funkcióival. Javasoljuk, hogy folytasson együttműködést a partnerével, és olvassa el a dokumentációt az áttelepítés előkészítése érdekében. 

A tervezési optimalizálás illeszkedési elemzése segít azonosítani azokat a pontokat, ahol az eredményben eltérés lehet a beépített alaptervezési motor és a tervezési optimalizálás esetén. Ez az elemzés a jelenlegi beállítások és adatok alapján történik. 

Ha meg szeretné tekinteni a tervezési optimalizálás illeszkedési elemzésének eredményét, akkor lépjen az **Alaptervezés** \> **Beállítás** \> **Tervezési optimalizálás illeszkedési elemzése** menüpontra, majd válassza az **Elemzés futtatása** parancsot. Ha az elemzés bármilyen következetlenséget talál, akkor ugyanazon a lapon szerepelnek. (Az elemzés néhány percet is igénybe vehet.)

> [!NOTE]
> Ha találhatók következetlenségek, akkor a tervezésoptimalizálása továbbra is használható. Az illeszkedési elemzés eredményei csak azokat a helyeket jelenítik meg, ahol a tervezési szolgáltatás nem tiszteli az aktuális beállításokat. Más szóval azokat a helyeket jelenítik meg, ahol bizonyos folyamatok figyelmen kívül lehetnek hagyva, vagy esetleg nem támogatottak.

## <a name="analysis-results-example-1"></a>Elemzési eredmények: 1. példa

- **Funkció:** Termelés
- **Probléma:** Cikkek, amelyeknél a darabjegyzék (BOM) szintje nagyobb, mint nulla: 56
- **Magyarázat:** Az illeszkedési elemzés 56 olyan cikket talál, amelynél a termeléshez anyagjegyzéket (BOM) állítottak be. Mivel a tervezésoptimalizálás modul jelenlegi verziója nem támogatja a termelést, a tervezésoptimalizálás a tervezett termelési rendelések helyett tervezett beszerzési rendeléseket fog generálni. Emellett figyelmeztetés jelenik meg, amely felsorolja az érintett cikkeket.

## <a name="analysis-results-example-2"></a>Elemzési eredmények: 2. példa

- **Funkció:** műveletek
- **Probléma:** Fedezeti csoportok, ahol műveletek számítása engedélyezett: 6
- **Magyarázat:** Az illeszkedési elemzés hat olyan fedezeti csoportot talált, ahol a műveletszámítás be van kapcsolva. Mivel a tervezésoptimalizálás jelenlegi verziója nem támogatja a műveleteket, az Alaptervezés során nem jönnek létre műveletek.

## <a name="overview-of-possible-results-from-the-fit-analysis"></a>Az illeszkedési elemzés lehetséges eredményeinek áttekintése

A következő táblázat bemutatja, hogy milyen eredmények jelenhetnek meg az illeszkedési elemzés után. A szám jeleket (_\#_) a rendszer egy számmal helyettesíti, amely a felsorolt problémával rendelkező rekordok számát jelzi. Támogatott vagy előzetes funkciók 10.0.9-es vagy újabb verzióknál érhetők el (hacsak nem szerepel nagyobb verziószám a „Várható elérhetőség” oszlopban).

> [!NOTE]
> Egyes ellentmondásokat nem lehet azonosítani a Tervezési optimalizálás illeszkedéselemzéssel. További információért lásd: [A klasszikus főtervezés és a Tervezésoptimalizálás közötti különbségek.](planning-optimization-differences-with-built-in.md)

| Funkció | Felsorolt probléma | Magyarázat | Várható elérhetőség |
| --- | --- | --- | --- |
| Műveletek | Lefedettségi csoportok, amelyeknél engedélyezve van a Műveletek kiszámítása: _\#_ | Ez a funkció függőben van. A program jelenleg a tervezés optimalizálása engedélyezése esetén nem hozza létre a műveleteket az Alaptervezés során, a beállítástól függetlenül. A műveletek fő célja a meglévő sorrend változásainak javaslata. Annak megállapítása, hogy a műveletek aktívan alkalmazva vannak-e az üzleti folyamatok részeként, vagy a rendelésekhez kapcsolódó késésleltetési információk elegendőek-e. | Támogatott |
| Alapnaptárak | Az alapnaptárat használó naptárak: _\#_ | Ez a funkció már támogatott. | március 2022. | 
| Kötegrendelkezési kódok | Nem nettósítható kötegelt alapintézkedések: _\#_ | Ez a funkció függőben van. A tervezés optimalizálása során a program figyelmen kívül hagyja a kötegrendelkezési kódokat. | 2022. októberi és újabb |
| Ígérhető (CTP) | Alapértelmezett rendelési beállítások, amelyeknél a kiszállítási dátum ellenőrzése ígérhető: _\#_ | Ez a funkció függőben van. Jelenleg az ígérhető értéke figyelmen kívül marad, ha a tervezés optimalizálása engedélyezve van a beállítástól függetlenül. | Október 2022. |
| Statikus dinamikus tervbe másolása | A statikus dinamikus tervbe való másolása engedélyezett az alaptervezési paramétereknél. | A tervezés optimalizálása a beállítástól függetlenül nem másolja át a statikus tervet a dinamikus tervbe. Általában ez a koncepció kevésbé fontos a Tervezési optimalizáció által biztosított gyorsaság és teljes regeneráció miatt. Ha két vagy több terv van használatban, akkor minden tervhez alaptervezést kell indítani. | Október 2022. |
| Megerősítés | Fedezeti csoportok, amelyekhez be van állítva automatikus megerősítési időkorlát: _\#_ | A 10.0.7 és a későbbi verziókban a megerősítést az Alaptervezés befejezését követően külön megerősítő kötegelt feladatként támogatják (feltéve hogy az _Automatikus megerősítés a tervezési optimalizációhoz_ funkció engedélyezve van a [funkciókezelés](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pontban). Ne felejtse el, hogy az Automatikus megerősítés a tervezési optimalizációhoz a megrendelés dátumától (kezdő dátum) függ, nem a követelmény dátumától (záró dátum). Ez a viselkedés biztosítja, hogy a tervezett rendelések megerősítése időben történjen, anélkül, hogy az átfutási időt bele kellene foglalni a megerősítési időkorlátba. | Támogatott |
| Megerősítés | Cikk lefedettségi rekordjai, amelyekhez be van állítva az automatikus megerősítés: _\#_ | A 10.0.7 és a későbbi verziókban az automatikus megerősítést az Alaptervezés befejezését követően külön megerősítő kötegelt feladatként támogatják (feltéve hogy az _Automatikus megerősítés a tervezési optimalizációhoz_ funkció engedélyezve van a [funkciókezelés](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pontban). Ne felejtse el, hogy az Automatikus megerősítés a tervezési optimalizációhoz a megrendelés dátumától (kezdő dátum) függ, nem a követelmény dátumától (záró dátum). Ez a viselkedés biztosítja, hogy a tervezett rendelések megerősítése időben történjen, anélkül, hogy az átfutási időt bele kellene foglalni a megerősítési időkorlátba. | Támogatott |
| Megerősítés | Alaptervek, amelyekhez be van állítva az automatikus megerősítés: _\#_ | A 10.0.7 és a későbbi verziókban az automatikus megerősítést az Alaptervezés befejezését követően külön megerősítő kötegelt feladatként támogatják (feltéve hogy az _Automatikus megerősítés a tervezési optimalizációhoz_ funkció engedélyezve van a [funkciókezelés](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pontban). Ne felejtse el, hogy az Automatikus megerősítés a tervezési optimalizációhoz a megrendelés dátumától (kezdő dátum) függ, nem a követelmény dátumától (záró dátum). Ez a viselkedés biztosítja, hogy a tervezett rendelések megerősítése időben történjen, anélkül, hogy az átfutási időt bele kellene foglalni a megerősítési időkorlátba. | Támogatott |
| FitAnalysisPlanningItems | Tervezési cikkek: _\#_ | Ez a funkció függőben van. Jelenleg a tervezési cikkek ugyanúgy kezelhetők, mint a normál cikkek, amikor a tervezés optimalizálása engedélyezve van. | 2022. októberi és újabb |
| Előrejelzés | A "vállalatok közötti rendelések szerepeltetése" beállítású fedezeti csoportok engedélyezve vannak: _\#_ | Ez a funkció már támogatott. További információkért lásd: [Vállalatok közötti tervezés](Intercompany-planning.md) | Támogatott |
| Előrejelzés | Azok a fedezeti csoportok, amelyeknél az „Előrejelzés csökkentésének mennyisége” beállítás értéke eltér a „Megrendelések” értékétől: _\#_ | Ez a funkció már támogatott. További információ: [Alaptervezés igény-előrejelzésekkel](demand-forecast.md) | Támogatott |
| Előrejelzés | Almodellekkel rendelkező előrejelzési modellek: _\#_ |  Ez a funkció már támogatott. További információ: [Alaptervezés igény-előrejelzésekkel](demand-forecast.md) | Támogatott |
| Előrejelzés | Olyan alaptervek, amelyekhez engedélyezve van az „ellátási előrejelzést tartalmaz”: _\#_ | Ez a funkció függőben van. Jelenleg az ellátási előrejelzések nem támogatottak, ha a tervezés optimalizálása engedélyezve van. A program figyelmen kívül hagyja ezeket, a beállítástól függetlenül. | 2022. októberi és újabb |
| Befagyasztási időkorlát | Lefedettségi csoportok, amelyekhez van beállítva befagyasztási időkorlát: _\#_ | A befagyasztási időkorlát nem gyakran használatos, és jelenleg nem szerepel a tervezés optimalizálásával kapcsolatos tervekben. Jelenleg a rendszer figyelmen kívül hagyja a befagyasztási időkorlát beállítását, ha a tervezés optimalizálása engedélyezve van a beállítástól függetlenül. | N.a. |
| Befagyasztási időkorlát | Olyan cikklefedettségi rekordok, amelyekhez van beállítva befagyasztási időkorlát: _\#_ | A befagyasztási időkorlát nem gyakran használatos, és jelenleg nem szerepel a tervezés optimalizálásával kapcsolatos tervekben. Jelenleg a rendszer figyelmen kívül hagyja a befagyasztási időkorlát beállítását, ha a tervezés optimalizálása engedélyezve van a beállítástól függetlenül. | N.a. |
| Befagyasztási időkorlát | Olyan alaptervek, amelyekhez van beállítva befagyasztási időkorlát: _\#_ | A befagyasztási időkorlát nem gyakran használatos, és jelenleg nem szerepel a tervezés optimalizálásával kapcsolatos tervekben. Jelenleg a rendszer figyelmen kívül hagyja a befagyasztási időkorlát beállítását, ha a tervezés optimalizálása engedélyezve van a beállítástól függetlenül. | N.a. |
| Vállalatok közötti | Tervezett alsóbb rétegbeli igényt tartalmazó alaptervek: _\#_ | Ez a funkció már támogatott. További információkért lásd: [Vállalatok közötti tervezés](Intercompany-planning.md) | Támogatott |
| Kanban | Tervezett rendelési típusú kanbannal rendelkező cikklefedettségi rekordok: _\#_ | Ez a funkció függőben van. Jelenleg a tervezés optimalizálása során a program figyelmen kívül hagyja a kanban beállítású cikkfedezeti beállítást. A kanban tervezett rendelési típusa figyelmeztetést hoz létre az Alaptervezés során, és a rendszer a kapcsolódó igény fedezésére tervezett beszerzési rendeléseket hoz létre. | 2022. októberi és újabb |
| Kanban | Kanban alapértelmezett rendelési típussal rendelkező cikkek: _\#_ | Jelenleg a tervezés optimalizálása során a program figyelmen kívül hagyja a kanban beállítású alapértelmezett megrendeléstípust. A kanban alapértelmezett rendelési típus figyelmeztetést hoz létre az Alaptervezés során, és a rendszer a kapcsolódó igény fedezésére tervezett beszerzési rendeléseket hoz létre. | 2022. októberi és újabb |
| Termékéletciklus állapota | A termékéletciklus állapotai nem aktívak a tervezéshez: _\#_ | Ez a funkció már támogatott. További információkért lásd: [Adott termékéletciklus-állapottal rendelkező termékek kizárása](product-lifecycle-state.md) | Támogatott |
| Termelés | Darabjegyzéksorok kerekítéssel vagy többszörös beállítással: _\#_ | Ez a funkció függőben van. Jelenleg a kerekítés és a többszörös beállítás figyelmen kívül marad a darabjegyzéksorokban, amikor a tervezés optimalizálása engedélyezve van a beállítástól függetlenül. | Október 2021. |
| Termelés | Darabjegyzék-/képletsorok képletmértékkel: _\#_ | Ez a funkció függőben van. Jelenleg a képletmérték figyelmen kívül marad a darabjegyzék- és képletsorokban, amikor a tervezés optimalizálása engedélyezve van a beállítástól függetlenül. | Október 2022. |
| Termelés | Darabjegyzék-/képletsorok cikkhelyettesítéssel (tervcsoportok): _\#_ | Ez a funkció függőben van. Jelenleg a cikkhelyettesítés (tervcsoportok) figyelmen kívül marad a darabjegyzék- és képletsorokban, amikor a tervezés optimalizálása engedélyezve van a beállítástól függetlenül. | Október 2022. |
| Termelés | Darabjegyzék-/képletsorok negatív mennyiséggel: _\#_ | Ez a funkció függőben van. A negatív mennyiséget tartalmazó darabjegyzék-és képletsorok száma 0 (nulla) értékkel szerepel, és a program a tervezés optimalizálása alkalmával figyelmeztetést ad ki. Az alapadatok frissítése a figyelmeztetések elkerüléséhez. | Október 2022. |
| Termelés | Darabjegyzék-/képletsorok erőforrás-felhasználással: _\#_ | Ez a funkció függőben van. Jelenleg az erőforrás-felhasználást tartalmazó darabjegyzék- és képletsorok figyelmen kívül maradnak, amikor a tervezés optimalizálása engedélyezve van. Ha ez a funkció támogatott, akkor a program a termelés kezdő dátumára állítja be az anyagszükségletet. Amíg ez a funkció támogatott az erőforrás-felhasználás jelzővel rendelkező anyagokhoz nem lesz generálva követelmény. | Október 2022. |
| Termelés | Darabjegyzék-/képletsorok lépésfelhasználással: _\#_ | Ez a funkció függőben van. Jelenleg a lépésfelhasználás figyelmen kívül marad a darabjegyzék- és képletsorokon, amikor a tervezés optimalizálása engedélyezve van. | Október 2022. |
| Termelés | Darabjegyzékek állandó selejttel vagy változó selejttel meghatározva: _\#_ | Ez a funkció függőben van. Jelenleg a tervezés optimalizálás engedélyezésekor a program figyelmen kívül hagyja az anyagjegyzékeken definiált állandó selejtet és változó selejtet. | Október 2022. |
| Termelés | Darabjegyzékek alvállalkozásba adással: _\#_ | Ez a funkció már támogatott. | Támogatott |
| Termelés | Telephely nélküli darabjegyzékek: _\#_ | Ez a funkció már támogatott. További információkért lásd: [Termeléstervezés](production-planning.md) | Támogatott |
| Termelés | Igény megadott darajegyzék- vagy meghatározott útvonal-követelményekkel: _\#_ | Ez a funkció függőben van. A program jelenleg az igényen meghatározott specifikus darabjegyzék- vagy útvonal-követelményt (például egy értékesítési rendelésen szereplő aldarabjegyzéket vagy alútvonalat) figyelmen kívül hagyja, amikor a tervezés optimalizálása engedélyezve van. A program a beállítástól függetlenül a szokásos darabjegyzéket vagy útvonalat használja. | Október 2022. |
| Termelés | Képletverziók társ- vagy melléktermékekkel: _\#_ | Ez a funkció függőben van. Jelenleg a tervezésoptimalizálás engedélyezése esetén a képletverzióhoz társított társtermékek és a melléktermékek figyelmen kívül maradnak. | Október 2022. |
| Termelés | Képletverziók hozammal: _\#_ | Ez a funkció függőben van. Jelenleg a tervezésoptimalizálás engedélyezése esetén a képletverzióhoz társított hozam figyelmen kívül marad. | Október 2022. |
| Termelés | Sorrendbe állítást tartalmazó tervek: _\#_ | Ez a funkció függőben van. Jelenleg a sorrendbe állítás figyelmen kívül marad, ha a tervezés optimalizálása engedélyezve van a beállítástól függetlenül. | Október 2022. |
| Termelés | Nem megkezdett, kiadott termelési rendelések, amelyeket a mai napnál korábbi kezdéssel ütemeztek: _\#_ | Ez a funkció függőben van. Jelenleg a termelési rendelés késése esetén az alaptervezés azt feltételezi, hogy a mai napon be lesz fejezve. Ez olyan engedélyezett termelési rendelések esetében releváns amelyeknél a szállítási dátum már elmúlt, de még nem fejeződött be. | Október 2022. |
| Termelés | Véges kapacitással ütemezett erőforrások: _\#_ | Ez a funkció függőben van. Jelenleg a véges kapacitással ütemezett erőforrások figyelmen kívül maradnak, amikor a tervezés optimalizálása engedélyezve van. Az ütemezés a termék alapértelmezett átfutási ideje alapján történik. | Október 2022. |
| Termelés | A tervezésben használt útvonalak: _\#_ | Ez a funkció függőben van. A tervezés optimalizálása során a program figyelmen kívül hagyja az útvonalakat. A termék alapértelmezett átfutási ideje használatban van. | Előnézet: támogatott (10.0.20), GA: 2021. október |
| Termelés | Értékesítési sor foglalása alábontás használatával: _\#_ | A alábontást használó értékesítési sor foglalása nem támogatott, ha a tervezés optimalizálása engedélyezve van. | Október 2022. |
| Termelés | A termelési rendelések alábontásával történt ütemezés: _\#_ | A termelési rendelések alábontását használó ütemezés nem támogatott, ha a tervezés optimalizálása engedélyezve van. A termelési rendelések ütemezése egyenként végezhető el. | Október 2022. |
| Ajánlatkérések | Olyan alaptervek, amelyeknél engedélyezve van az ajánlatkérés: _\#_ | Ez a funkció függőben van. Jelenleg az ajánlatkérés (ajánlatkérések) nem tekintendő igénynek, ha a tervezés optimalizálása engedélyezve van. A program figyelmen kívül hagyja ezeket, a beállítástól függetlenül. | Október 2022. |
| Igénylések | Olyan alaptervek, amelyeknél engedélyezve vannak az igénylések: _\#_ | Ez a funkció már támogatott. További információk: [Beszerzési igénylések](purchase-requisitions.md) | Támogatott |
| Biztonsági határok | Biztonsági határokkal rendelkező lefedettségi csoportok: _\#_ | Ez a funkció már részben támogatott. További információkért lásd: [Biztonsági határok](safety-margins.md) | Bevételezési időtartalék: Támogatott. Újrarendelési és kiadási időtartalék: 2022. január |
| Biztonsági határok | Biztonsági határokkal rendelkező alaptervek: _\#_ | Ez a funkció már részben támogatott. További információkért lásd: [Biztonsági határok](safety-margins.md) | Bevételezési időtartalék: Támogatott. Újrarendelési és kiadási időtartalék: 2022. január |
| Biztonsági készlet teljesítése | A „Minimum teljesítése” beállítással rendelkező cikkfedezeti rekordok, amelyek eltérnek a „Mai dátum + beszerzési idő” értékétől: _\#_ | A tervezés optimalizálása mindig a *mai dátum + beszerzési időt* használja. Ennek a módosításnak az a célja, hogy előkészüljön egy jövőbeli egyszerűsített tervezési beállításra, és hogy a művelet eredményét biztosítsa. Ha a beszerzési idő nem szerepel a biztonsági készletben, akkor az aktuális alacsony raktárkészlethez létrehozott tervezett rendeléseket mindig az átfutási idő miatt késlelteti a program. Ez a viselkedés jelentős zajt és nemkívánatos tervezett rendeléseket eredményezhet. A legjobb módszer a beállítás módosítása, hogy a *mai dátum + beszerzési idő* legyen használatban. Az alapadatok frissítése a figyelmeztetések elkerüléséhez. | N.a. |
| Értékesítési ajánlatok | Olyan alaptervek, amelyeknél engedélyezve vannak az értékesítési ajánlatok: _\#_ | Ez a funkció függőben van. A tervezés optimalizálás engedélyezése során a program figyelmen kívül hagyja az árajánlatokat. A program figyelmen kívül hagyja ezeket, a beállítástól függetlenül. | 2022. októberi és újabb |
| Eltarthatósági idő | Olyan alaptervek, amelyeknél engedélyezve van az eltarthatósági idő: _\#_ | Ez a funkció függőben van. Jelenleg az eltarthatósági idő figyelmen kívül marad, ha a tervezés optimalizálása engedélyezve van a beállítástól függetlenül. | április 2022. |

## <a name="additional-resources"></a>További erőforrások

[Tervezési optimalizálás áttekintése](planning-optimization-overview.md)

[A Tervezési optimalizálás kezdő lépései](get-started.md)

[Különbségek a klasszikus főtervezés és a tervezési optimalizálás között](planning-optimization-differences-with-built-in.md)

[A Tervezési optimalizálás által nem használt paraméterek](not-used-parameters.md)

[Tervelőzmények és tervezési naplók megtekintése](plan-history-logs.md)

[Szűrők alkalmazása egy tervre](plan-filters.md)

[Tervezési feladat érvénytelenítése](cancel-planning-job.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
