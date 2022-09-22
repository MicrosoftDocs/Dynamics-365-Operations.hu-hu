---
title: A Tervezési optimalizálás igazítási elemzése
description: Ez a cikk bemutatja, hogyan lehet a jelenlegi beállításokat és adatokat a tervezésoptimalizálási funkció lehetőségeihez ellenében ellenőrizni.
author: t-benebo
ms.date: 08/11/2022
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
ms.openlocfilehash: f9c85c4fbcc3c66d6cc4c65431b76c31cbb7aebf
ms.sourcegitcommit: 20ce54cb40290dd116ab8b157c0a02d6757c13f5
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/20/2022
ms.locfileid: "9542352"
---
# <a name="planning-optimization-fit-analysis"></a>Tervezési optimalizálás igazítási elemzése

[!include [banner](../../includes/banner.md)]

Az áttelepítési folyamat részeként elemezze a tervezési optimalizálás illeszkedési elemzésének eredményét. Ne felejtse el, hogy a tervezési optimalizálás hatóköre nem egyezik meg a beépített alaptervezés aktuális funkcióival. Javasoljuk, hogy folytasson együttműködést a partnerével, és olvassa el a dokumentációt az áttelepítés előkészítése érdekében. 

A tervezési optimalizálás illeszkedési elemzése segít azonosítani azokat a pontokat, ahol az eredményben eltérés lehet a beépített alaptervezési motor és a tervezési optimalizálás esetén. Ez az elemzés a jelenlegi beállítások és adatok alapján történik. 

Ha meg szeretné tekinteni a tervezési optimalizálás illeszkedési elemzésének eredményét, akkor lépjen az **Alaptervezés** \> **Beállítás** \> **Tervezési optimalizálás illeszkedési elemzése** menüpontra, majd válassza az **Elemzés futtatása** parancsot. Ha az elemzés bármilyen következetlenséget talál, akkor ugyanazon a lapon szerepelnek. (Az elemzés néhány percet is igénybe vehet.)

> [!NOTE]
>
> - Egyes ellentmondásokat nem lehet azonosítani a Tervezési optimalizálás illeszkedéselemzéssel. További információért lásd: [A klasszikus főtervezés és a Tervezésoptimalizálás közötti különbségek.](planning-optimization-differences-with-built-in.md)
>
> - Ha találhatók következetlenségek, akkor a tervezésoptimalizálása továbbra is használható. Az illeszkedési elemzés eredményei csak azokat a helyeket jelenítik meg, ahol a tervezési szolgáltatás nem tiszteli az aktuális beállításokat. Más szóval azokat a helyeket jelenítik meg, ahol bizonyos folyamatok figyelmen kívül lehetnek hagyva, vagy esetleg nem támogatottak.

## <a name="analysis-results-example-1"></a>Elemzési eredmények: 1. példa

- **Funkció:** Termelés
- **Probléma:** Cikkek, amelyeknél a darabjegyzék (BOM) szintje nagyobb, mint nulla: 56
- **Magyarázat:** Az illeszkedési elemzés 56 olyan cikket talál, amelynél a termeléshez anyagjegyzéket (BOM) állítottak be. Mivel a tervezésoptimalizálás modul jelenlegi verziója nem támogatja a termelést, a tervezésoptimalizálás a tervezett termelési rendelések helyett tervezett beszerzési rendeléseket fog generálni. Emellett figyelmeztetés jelenik meg, amely felsorolja az érintett cikkeket.

## <a name="analysis-results-example-2"></a>Elemzési eredmények: 2. példa

- **Funkció:** műveletek
- **Probléma:** Fedezeti csoportok, ahol műveletek számítása engedélyezett: 6
- **Magyarázat:** Az illeszkedési elemzés hat olyan fedezeti csoportot talált, ahol a műveletszámítás be van kapcsolva. Mivel a tervezésoptimalizálás jelenlegi verziója nem támogatja a műveleteket, az Alaptervezés során nem jönnek létre műveletek.

## <a name="overview-of-possible-results-from-the-fit-analysis"></a>Az illeszkedési elemzés lehetséges eredményeinek áttekintése

A következő táblázat bemutatja, hogy milyen eredmények jelenhetnek meg az illeszkedési elemzés után. A szám jeleket (*\#*) a rendszer egy számmal helyettesíti, amely a felsorolt problémával rendelkező rekordok számát jelzi.

> [!IMPORTANT]
> A még nem támogatott funkciók esetén a következő táblázat a jelenlegi állapotunk alapján várható elérhetőségi információkat tartalmaz. Ezek a becslések értesítés nélkül változhatnak.

| Szolgáltatás | Felsorolt probléma | Magyarázat | Várható elérhetőség |
| --- | --- | --- | --- |
| Műveletek | Lefedettségi csoportok, amelyeknél engedélyezve van a Műveletek kiszámítása: *\#* | Ez a funkció már támogatott. | Támogatott |
| Alapnaptárak | Az alapnaptárat használó naptárak: *\#* | Ez a funkció már támogatott. | Támogatott | 
| Kötegrendelkezési kódok | Nem nettósítható köteg-alapintézkedések: *\#* | Ez a funkció függőben van. A tervezés optimalizálása során a program figyelmen kívül hagyja a kötegrendelkezési kódokat. | 2022-es kiadás - 2. hullám <!-- KFM: Now available? [Use batch disposition codes to mark batches as available or unavailable](../../inventory/batch-disposition-codes.md) --> |
| Ígérhető (CTP) | Alapértelmezett rendelési beállítások, amelyeknél a kiszállítási dátum ellenőrzése ígérhető: *\#* | A 10.0.28-as és újabb ellátásilánc-kezelésben a tervezési optimalizálási CTP *nevű folyamat a dinamikus terv futtatása után teszi elérhetővé a* visszaigazolt szállítási és kézhezvételi dátumokat. Az Ellátásilánc-kezelés régebbi verziói esetén a rendszer figyelmen kívül hagyja az örökölt "CTP" beállítást, ha engedélyezve van a tervezési optimalizálás. | Támogatott |
| Statikus dinamikus tervbe másolása | A statikus dinamikus tervbe való másolása engedélyezett az alaptervezési paramétereknél. | A tervezés optimalizálása a beállítástól függetlenül nem másolja át a statikus tervet a dinamikus tervbe. Általában ez a koncepció kevésbé fontos a Tervezési optimalizáció által biztosított gyorsaság és teljes regeneráció miatt. Ha két vagy több terv van használatban, akkor minden tervhez alaptervezést kell indítani. | N/A |
| Megerősítés | Lefedettségi csoportok, amelyekhez be van állítva automatikus megerősítési időkorlát: *\#* | A 10.0.7 és a későbbi verziókban a megerősítést az Alaptervezés befejezését követően külön megerősítő kötegelt feladatként támogatják (feltéve hogy az *Automatikus megerősítés a tervezési optimalizációhoz* funkció engedélyezve van a [funkciókezelés](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pontban). Ne felejtse el, hogy az Automatikus megerősítés a tervezési optimalizációhoz a megrendelés dátumától (kezdő dátum) függ, nem a követelmény dátumától (záró dátum). Ez a viselkedés biztosítja, hogy a tervezett rendelések megerősítése időben történjen, anélkül, hogy az átfutási időt bele kellene foglalni a megerősítési időkorlátba. | Támogatott |
| Megerősítés | Cikk lefedettségi rekordjai, amelyekhez be van állítva az automatikus megerősítés: *\#* | A 10.0.7 és a későbbi verziókban az automatikus megerősítést az Alaptervezés befejezését követően külön megerősítő kötegelt feladatként támogatják (feltéve hogy az *Automatikus megerősítés a tervezési optimalizációhoz* funkció engedélyezve van a [funkciókezelés](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pontban). Ne felejtse el, hogy az Automatikus megerősítés a tervezési optimalizációhoz a megrendelés dátumától (kezdő dátum) függ, nem a követelmény dátumától (záró dátum). Ez a viselkedés biztosítja, hogy a tervezett rendelések megerősítése időben történjen, anélkül, hogy az átfutási időt bele kellene foglalni a megerősítési időkorlátba. | Támogatott |
| Megerősítés | Alaptervek, amelyekhez be van állítva az automatikus megerősítés: *\#* | A 10.0.7 és a későbbi verziókban az automatikus megerősítést az Alaptervezés befejezését követően külön megerősítő kötegelt feladatként támogatják (feltéve hogy az *Automatikus megerősítés a tervezési optimalizációhoz* funkció engedélyezve van a [funkciókezelés](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pontban). Ne felejtse el, hogy az Automatikus megerősítés a tervezési optimalizációhoz a megrendelés dátumától (kezdő dátum) függ, nem a követelmény dátumától (záró dátum). Ez a viselkedés biztosítja, hogy a tervezett rendelések megerősítése időben történjen, anélkül, hogy az átfutási időt bele kellene foglalni a megerősítési időkorlátba. | Támogatott |
| FitAnalysisPlanningItems | Tervezési cikkek: *\#* | Ez a funkció függőben van. Jelenleg a tervezési cikkek ugyanúgy kezelhetők, mint a normál cikkek, amikor a tervezés optimalizálása engedélyezve van. | 2022-es kiadás - 2. vagy újabb hullám |
| Előrejelzés | A "vállalatok közötti rendelések szerepeltetése" beállítású fedezeti csoportok engedélyezve vannak: *\#* | Ez a funkció már támogatott. További információkért lásd: [Vállalatok közötti tervezés](Intercompany-planning.md) | Támogatott |
| Előrejelzés | Azok a fedezeti csoportok, amelyeknél az „Előrejelzés csökkentésének mennyisége” beállítás értéke eltér a „Megrendelések” értékétől: *\#* | Ez a funkció már támogatott. További információ: [Alaptervezés igény-előrejelzésekkel](demand-forecast.md) | Támogatott |
| Előrejelzés | Almodellekkel rendelkező előrejelzési modellek: *\#* |  Ez a funkció már támogatott. További információ: [Alaptervezés igény-előrejelzésekkel](demand-forecast.md) | Támogatott |
| Előrejelzés | Olyan alaptervek, amelyekhez engedélyezve van az „ellátási előrejelzést tartalmaz”: *\#* | Ez a funkció függőben van. Jelenleg az ellátási előrejelzések nem támogatottak, ha a tervezés optimalizálása engedélyezve van. A program figyelmen kívül hagyja ezeket, a beállítástól függetlenül. | 2022-es kiadás - 2. vagy újabb hullám |
| Befagyasztási időkorlát | Lefedettségi csoportok, amelyekhez van beállítva befagyasztási időkorlát: *\#* | Ez a funkció függőben van. Jelenleg a rendszer figyelmen kívül hagyja a befagyasztási időkorlát beállítását, ha a tervezés optimalizálása engedélyezve van a beállítástól függetlenül. | 2022-es kiadás - 2. hullám |
| Befagyasztási időkorlát | Olyan cikklefedettségi rekordok, amelyekhez van beállítva befagyasztási időkorlát: *\#* | Ez a funkció függőben van. Jelenleg a rendszer figyelmen kívül hagyja a befagyasztási időkorlát beállítását, ha a tervezés optimalizálása engedélyezve van a beállítástól függetlenül. | 2022-es kiadás - 2. hullám |
| Befagyasztási időkorlát | Olyan alaptervek, amelyekhez van beállítva befagyasztási időkorlát: *\#* | Ez a funkció függőben van. Jelenleg a rendszer figyelmen kívül hagyja a befagyasztási időkorlát beállítását, ha a tervezés optimalizálása engedélyezve van a beállítástól függetlenül. | 2022-es kiadás - 2. hullám |
| Vállalatok közötti | Tervezett alsóbb rétegbeli igényt tartalmazó alaptervek: *\#* | Ez a funkció már támogatott. További információkért lásd: [Vállalatok közötti tervezés](Intercompany-planning.md) | Támogatott |
| Kanban | Tervezett rendelési típusú kanbannal rendelkező cikklefedettségi rekordok: *\#* | Ez a funkció függőben van. Jelenleg a tervezés optimalizálása során a program figyelmen kívül hagyja a kanban beállítású cikkfedezeti beállítást. A kanban tervezett rendelési típusa figyelmeztetést hoz létre az Alaptervezés során, és a rendszer a kapcsolódó igény fedezésére tervezett beszerzési rendeléseket hoz létre. | Jövőbeli hullám |
| Kanban | Alapértelmezett rendelési típusú kanbannal rendelkező cikkek: *\#* | Jelenleg a tervezés optimalizálása során a program figyelmen kívül hagyja a kanban beállítású alapértelmezett megrendeléstípust. A kanban alapértelmezett rendelési típus figyelmeztetést hoz létre az Alaptervezés során, és a rendszer a kapcsolódó igény fedezésére tervezett beszerzési rendeléseket hoz létre. | Jövőbeli hullám |
| Termékéletciklus állapota | A termékéletciklus állapotai nem aktívak a tervezéshez: *\#* | Ez a funkció már támogatott. További információkért lásd: [Adott termékéletciklus-állapottal rendelkező termékek kizárása](product-lifecycle-state.md) | Támogatott |
| Termelés | Darabjegyzéksorok kerekítéssel vagy többszörös beállítással: *\#* | Ez a funkció függőben van. Jelenleg a kerekítés és a többszörös beállítás figyelmen kívül marad a darabjegyzéksorokban, amikor a tervezés optimalizálása engedélyezve van a beállítástól függetlenül. | Jövőbeli hullám|
| Termelés | Darabjegyzék-/képletsorok képletmértékkel: *\#* | Ez a funkció függőben van. Jelenleg a képletmérték figyelmen kívül marad a darabjegyzék- és képletsorokban, amikor a tervezés optimalizálása engedélyezve van a beállítástól függetlenül. | 2022-es kiadás - 2. hullám |
| Termelés | Darabjegyzék-/képletsorok cikkhelyettesítéssel (tervcsoportok): *\#* | Ez a funkció függőben van. Jelenleg a cikkhelyettesítés (tervcsoportok) figyelmen kívül marad a darabjegyzék- és képletsorokban, amikor a tervezés optimalizálása engedélyezve van a beállítástól függetlenül. | 2022-es kiadás - 2. hullám |
| Termelés | Darabjegyzék-/képletsorok negatív mennyiséggel: *\#* | Ez a funkció függőben van. A negatív mennyiséget tartalmazó darabjegyzék-és képletsorok száma 0 (nulla) értékkel szerepel, és a program a tervezés optimalizálása alkalmával figyelmeztetést ad ki. Az alapadatok frissítése a figyelmeztetések elkerüléséhez. | 2022-es kiadás - 2. hullám |
| Termelés | Darabjegyzék-/képletsorok erőforrás-felhasználással: *\#* | Ez a funkció függőben van. Jelenleg az erőforrás-felhasználást tartalmazó darabjegyzék- és képletsorok figyelmen kívül maradnak, amikor a tervezés optimalizálása engedélyezve van. Ha ez a funkció támogatott, akkor a program a termelés kezdő dátumára állítja be az anyagszükségletet. Amíg ez a funkció támogatott az erőforrás-felhasználás jelzővel rendelkező anyagokhoz nem lesz generálva követelmény. | 2022-es kiadás - 2. hullám |
| Termelés | Darabjegyzék-/képletsorok lépésfelhasználással: *\#* | Ez a funkció függőben van. Jelenleg a lépésfelhasználás figyelmen kívül marad a darabjegyzék- és képletsorokon, amikor a tervezés optimalizálása engedélyezve van. | 2022-es kiadás - 2. hullám |
| Termelés | Darabjegyzéke állandó selejttel vagy változó selejttel meghatározva: *\#* | Ez a funkció függőben van. Jelenleg a tervezés optimalizálás engedélyezésekor a program figyelmen kívül hagyja az anyagjegyzékeken definiált állandó selejtet és változó selejtet. | 2022-es kiadás - 2. hullám |
| Termelés | Darabjegyzékek alvállalkozásba adással: *\#* | Ez a funkció már támogatott. | Támogatott |
| Termelés | Telephely nélküli darabjegyzékek: *\#* | Ez a funkció már támogatott. További információkért lásd: [Termeléstervezés](production-planning.md) | Támogatott |
| Termelés | Igény megadott darajegyzék- vagy meghatározott útvonal-követelményekkel: *\#* | Ez a funkció függőben van. A program jelenleg az igényen meghatározott specifikus darabjegyzék- vagy útvonal-követelményt (például egy értékesítési rendelésen szereplő aldarabjegyzéket vagy alútvonalat) figyelmen kívül hagyja, amikor a tervezés optimalizálása engedélyezve van. A program a beállítástól függetlenül a szokásos darabjegyzéket vagy útvonalat használja. | 2022-es kiadás - 2. hullám |
| Termelés | Képletverziók társ- vagy melléktermékekkel: *\#* | Ez a funkció függőben van. Jelenleg a tervezésoptimalizálás engedélyezése esetén a képletverzióhoz társított társtermékek és a melléktermékek figyelmen kívül maradnak. | 2022-es kiadás - 2. hullám |
| Termelés | Képletverziók hozammal: *\#* | Ez a funkció függőben van. Jelenleg a tervezésoptimalizálás engedélyezése esetén a képletverzióhoz társított hozam figyelmen kívül marad. | 2022-es kiadás - 2. hullám |
| Termelés | Sorrendbe állítást tartalmazó tervek: *\#* | Ez a funkció függőben van. Jelenleg a sorrendbe állítás figyelmen kívül marad, ha a tervezés optimalizálása engedélyezve van a beállítástól függetlenül. | 2022-es kiadás - 2. hullám |
| Termelés | Nem megkezdett, kiadott termelési rendelések, amelyeket a mai napnál korábbi kezdéssel ütemeztek: *\#* | Ez a funkció függőben van. Jelenleg a termelési rendelés késése esetén az alaptervezés azt feltételezi, hogy a mai napon be lesz fejezve. Ez olyan engedélyezett termelési rendelések esetében releváns amelyeknél a szállítási dátum már elmúlt, de még nem fejeződött be. | Jövőbeli hullám |
| Termelés | Véges kapacitással ütemezett erőforrások: *\#* | Ez a funkció függőben van. Jelenleg a véges kapacitással ütemezett erőforrások figyelmen kívül maradnak, amikor a tervezés optimalizálása engedélyezve van. Az ütemezés a termék alapértelmezett átfutási ideje alapján történik. | 2022-es kiadás - 2. hullám |
| Termelés | A tervezésben használt útvonalak: *\#* | Ez nem támogatott. | Támogatott |
| Termelés | Értékesítési sor foglalása alábontás használatával: *\#* | A alábontást használó értékesítési sor foglalása nem támogatott, ha a tervezés optimalizálása engedélyezve van. | Jövőbeli hullám |
| Termelés | A termelési rendelések alábontásával történt ütemezés: *\#* | A termelési rendelések alábontását használó ütemezés nem támogatott, ha a tervezés optimalizálása engedélyezve van. A termelési rendelések ütemezése egyenként végezhető el. | Jövőbeli hullám |
| Ajánlatkérések | Olyan alaptervek, amelyeknél engedélyezve van az ajánlatkérés: *\#* | Ez a funkció függőben van. Jelenleg az ajánlatkérés (ajánlatkérések) nem tekintendő igénynek, ha a tervezés optimalizálása engedélyezve van. A program figyelmen kívül hagyja ezeket, a beállítástól függetlenül. | 2022-es kiadás - 2. hullám |
| Igénylések | Olyan alaptervek, amelyeknél engedélyezve vannak az igénylések: *\#* | Ez a funkció már támogatott. További információk: [Beszerzési igénylések](purchase-requisitions.md) | Támogatott |
| Biztonsági határok | Biztonsági határokkal rendelkező lefedettségi csoportok: *\#* | Ez a funkció már támogatott. További információkért lásd: [Biztonsági határok](safety-margins.md) | Támogatott |
| Biztonsági határok | Biztonsági határokkal rendelkező alaptervek: *\#* | Ez a funkció már támogatott. További információkért lásd: [Biztonsági határok](safety-margins.md) |  Támogatott |
| Biztonsági készlet teljesítése | A „Minimum teljesítése” beállítással rendelkező cikkfedezeti rekordok, amelyek eltérnek a „Mai dátum + beszerzési idő” értékétől: *\#* | A tervezés optimalizálása mindig a *mai dátum + beszerzési időt* használja. Ennek a módosításnak az a célja, hogy előkészüljön egy jövőbeli egyszerűsített tervezési beállításra, és hogy a művelet eredményét biztosítsa. Ha a beszerzési idő nem szerepel a biztonsági készletben, akkor az aktuális alacsony raktárkészlethez létrehozott tervezett rendeléseket mindig az átfutási idő miatt késlelteti a program. Ez a viselkedés jelentős zajt és nemkívánatos tervezett rendeléseket eredményezhet. A legjobb módszer a beállítás módosítása, hogy a *mai dátum + beszerzési idő* legyen használatban. Az alapadatok frissítése a figyelmeztetések elkerüléséhez. | N.a. |
| Értékesítési ajánlatok | Olyan alaptervek, amelyeknél engedélyezve vannak az értékesítési ajánlatok: *\#* | Ez a funkció függőben van. A tervezés optimalizálás engedélyezése során a program figyelmen kívül hagyja az árajánlatokat. A program figyelmen kívül hagyja ezeket, a beállítástól függetlenül. | 2022-es kiadás - 2. vagy újabb hullám |
| Eltarthatósági idő | Olyan alaptervek, amelyeknél engedélyezve van az eltarthatósági idő: *\#* | Ez a funkció függőben van. Jelenleg az eltarthatósági idő figyelmen kívül marad, ha a tervezés optimalizálása engedélyezve van a beállítástól függetlenül. | Támogatott |

## <a name="additional-resources"></a>További erőforrások

[Tervezési optimalizálás áttekintése](planning-optimization-overview.md)

[A Tervezési optimalizálás kezdő lépései](get-started.md)

[Különbségek a klasszikus főtervezés és a tervezési optimalizálás között](planning-optimization-differences-with-built-in.md)

[A Tervezési optimalizálás által nem használt paraméterek](not-used-parameters.md)

[Tervelőzmények és tervezési naplók megtekintése](plan-history-logs.md)

[Szűrők alkalmazása egy tervre](plan-filters.md)

[Tervezési feladat érvénytelenítése](cancel-planning-job.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
