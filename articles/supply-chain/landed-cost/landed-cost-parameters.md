---
title: Partraszállítási költség paramétereinek beállítása
description: Ez a témakör azt ismerteti, hogyan lehet általános információkat és konfigurációs beállításokat magadni, amelyek a Partraszállítási költség modulban használatosak feladásra, állapotfrissítésre, számsorozatokhoz és viselkedésekhez.
author: sherry-zheng
ms.date: 12/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ITMParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-07
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: ea0f60424ff1ee40a4231aa9cc129bb942fca519
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/06/2021
ms.locfileid: "6353564"
---
# <a name="landed-cost-parameters-setup"></a>Partraszállítási költség paramétereinek beállítása

[!include [banner](../../includes/banner.md)]

A **Partraszállítási költség paraméterei** oldal használatával általános információkat és konfigurációs beállításokat adhat meg, amelyek a **Partraszállítási költség** modulban használatosak feladásra, állapotfrissítésre, számsorozatokhoz és viselkedésekhez. A paraméterek beállítása a jogi személy között meg van osztva, és rendszergazda által módosítható.

## <a name="open-the-landed-cost-parameters-page"></a>A Partraszállítási költség paraméterei oldal megnyitása

A paraméterek kezeléséhez lépjen a **Partraszállítási költség \> Beállítás \> Partraszállítási költség paraméterei** lehetőségre, majd a következő alszakaszok szerint állítsa be a mezőket.

![Partraszállítási költség paraméterei oldal.](media/landed-cost-parameters.png "Partraszállítási költség paraméterei oldal")

## <a name="general-tab"></a>Általános fül

### <a name="general-fasttab"></a>Általános gyorslap

A következő táblázat felsorolja azokat a mezőket, amelyek elérhetők a **Partraszállítási költség paraméterei** oldal **Általános** lapjának **Általános** gyorslapján.

| Beállítás | Leírás |
|---|---|
| Szállítási díj használata | A szállítási díj egy meghatározott időszakra van beállítva, és a több pénznemet használó áruk költségeinek becslésére használható. A szállítási díj használatához állítsa a beállítást *Igen* értékre. |
| Árfolyamtípus | Az hajóút és hajóútköltségek több pénznemben elvégzett számításaiban használt árfolyamok alapértelmezett gyűjteménye. |
| Beszerzési rendelés mennyiségének frissítése | Annak kiválasztása, hogy mi történik, ha a felhasználó módosítja a beszerzésirendelés-sorban szereplő mennyiséget:<ul><li>**Elfogadás** – A hajóút mennyisége automatikusan módosul.</li><li>**Figyelmeztetés** – Ha a hajóúthoz van csatolva egy sor, egy figyelmeztetés jelenik meg, de a hajóút mennyisége frissül.</li><li>**Hiba** – Ha a sor hajóúthoz van csatolva, egy hibaüzenet jelenik meg, és a beszerzési rendelés nem frissíthető. Ezért először el kell távolítani a rendeléssort a hajóútról.</li></ul> |
| Kartondobozok számának automatikus frissítése | Ha ez a beállítás *Igen* értékre van beállítva, minden karton összeadódik, és a hajóút és a konténer szintjein jelenik meg. Ha *Nem* beállításra van állítva, akkor a kartonok száma kezdetben 0 (nulla) lesz, és szükség esetén manuálisan módosítható. |

### <a name="costing-fasttab"></a>Költségszámítás gyorslap

A következő táblázat felsorolja azokat a mezőket, amelyek elérhetők a **Költségszámítás** oldal **Általános** lapjának **Általános** gyorslapján.

| Beállítás | Leírás |
|---|---|
| Feladás meghatározása | A főkönyvben válassza ki az értékhelyesbítést:<ul><li>**Összesen** – A teljes össeg a főkönyvbe van feladva.</li><li>**Cikkcsoport** – A helyesbítés cikkcsoportonként van megadva.</li><li>**Cikkszám** – A helyesbítés cikkenként van megadva. Ez az érték a legtöbb részletet szolgáltatja.</li></ul> |
| Nullás költségek engedélyezése | Állítsa *Nem* értékre ezt a beállítást, hogy hiba jelenjenk meg, ha egy felhasználó olyan hajóútszámlára vagy beszerzési rendelésre vonatkozó költségbecslést próbál meg feladni, amely nem tartalmazza a várható hajóútköltség értékét. A hibaüzenetben az áll, hogy 0 (nulla) költséget nem lehet felosztani, és a számla feladása sikertelen lesz. Ebben az esetben a felhasználó manuálisan frissítheti a becslést (vagy újrakonfigurálhatja az automatikus költséget), majd vagy behúzhatja a frissített értéket, vagy törölheti a költséget, ha nem vonatkozik.<p>A beállítás *Igen* beállításával a hajóút költsége üresen maradhat. Ebben az esetben a költségterületnek megfelelően 0 (nulla) árat kell felosztani. A szállítói költségszámla a hajóút bevételezését követően nullás árú költséggel szemben dolgozható fel.</p><p>Javasoljuk, hogy úgy állítsa be a becslést az automatikus költségrekordban, hogy ne jelenjen meg nulla árú költség. Bár ez a becslés nem teljes mértékben pontos, mégis pontosabbnak kell lennie a feltételezett nulla költség.</p> |
| Korrekció feladási dátuma | A Kötelezettségek – hajóút költségszámlája feladása esetén a kiegyenlítési tábla (készlethelyesbítések) is frissül. A számlanaplóban válassza ki a **Hajóút költségeinek kiválasztása** oldalon alapértelmezés szerint beállított dátumot:<ul><li>**Tranzakció dátuma** – A napló dátumának (feladási dátum) használata.</li><li>**Beszerzési rendelés számladátuma** – A készlet (beszerzési rendelés) számla pénzügyi feladási dátumának használata.</li><li>**Kiválasztott dátum** – A felhasználó megadhat egy feladási dátumot. Bár a dátum üresen hagyható, ha a költségszámla feladása során még mindig üres, a felhasználó hibaüzenetet kap.</li></ul> |
| Beszerzési számla bizonylatának használata | Ha ez a beállítás *Igen* értékű, a költségkönyvelési tranzakciók ugyanazt a bizonylatszámot fogják használni, mint a beszerzési számlánál. Ha *Nem* értékre van állítva, a rendszer a **Partraszállítási költség paraméterei** oldal **Számsorozatok** lapján beállított **Költségkönyvelési bizonylat** számsorozathoz a következő rendelkezésre álló számot használja.<p>Ennek a beállításnak csak akkor van hatása, ha a **Feladás főkönyvi költségszámlára** beállítás *Igen* értékre van állítva a **Számla** lapon a **Kötelezettségek paramétere** oldalon.</p> |
| Elszámolási számlára történő manuális feladás zárolása | Állítsa *Igen* beállításra, ha meg szeretné akadályozni az olyan elszámolási számlákra való feladást, amelyekben a tranzakció még nincs hajóúthoz kapcsolva. Ehhez válassza a **Funkciók \> Hajóútköltségek kiválasztása** elemet a szállítói számlanapló Művelet paneljén. Javasoljuk, hogy ezt a beállítást *Igen* beállítással válassza, hogy a hajóút és az elszámolási számla helyesen legyen kiegyenlítve. |
| Költségtípus költségelhatárolási számlájának használata | Ha ez a beállítás *Igen* értékű, a **Költségtípuskódok** oldalon a megfelelő költségtípuskódhoz beállított költségkönyvelési számlát használja a rendszer a költségek kiadásként való könyvelésére.<p>Ennek a beállításnak csak akkor van hatása, ha a **Feladás főkönyvi költségszámlára** beállítás *Igen* értékre van állítva a **Számla** lapon a **Kötelezettségek paramétere** oldalon. |
| Korrekciók feladása eltérésként | Ha ez a beállítás *Igen* értékű, felülbírálja a normál funkciókat, és arra kényszeríti a készlethelyesbítési tranzakciókat, amelyek a becsült költségek és a tényleges költségek közötti különbözetekkel kapcsolatosak, hogy egy különbözeti számlára legyenek feladva.<p>Ha ez a beállítás *Nem* értékű, a program a költségszámítási módszer és a költségtípuskód konfigurációja alapján kezeli az eltérésekhez kapcsolódó készlethelyesbítési tranzakciókat. Az elszámolóár esetében a különbözetek továbbra is fel lesznek adva a különbözeti számlára. A mozgó súlyozott átlag (WMA) esetében a különbözeteket a rendszer vagy a különbözeti számlára, vagy a készletbe adja fel.</p><p>Ennek a beállításnak csak akkor van hatása, ha a **Feladás főkönyvi költségszámlára** beállítás *Igen* értékre van állítva a **Számla** lapon a **Kötelezettségek paramétere** oldalon.</p> |

### <a name="validation-fasttab"></a>Ellenőrzés gyorslap

A következő táblázat felsorolja azokat a mezőket, amelyek elérhetők a **Költségszámítás** oldal **Általános** lapjának **Ellenőrzés** gyorslapján.

| Beállítás | Leírás |
|---|---|
| Több költségszámla | Annak kiválasztása, hogy mi történik, ha ugyanannak a vegyes költség esetében egy hajóúttal, levéllel vagy konténerrel szemben több számla feldolgozása történik.<ul><li>**Elfogadás** – A rendszernek több költségszámlát kell engedélyeznie.</li><li>**Figyelmeztetés** – Egy figyelmeztetés jelenik meg.</li><li>**Hiba** – Hibaüzenet jelenik meg.</li></ul> |
| Több szállító ívlaponként | Annak kiválasztása, hogy mi történik, ha egynél több szállító beszerzési rendelését adja hozzá egy levélhez.<ul><li>**Elfogadás** – A rendszernek engedélyeznie kell a műveletet.</li><li>**Figyelmeztetés** – Figyelmeztetés jelenik meg, de a művelet végrehajtható.</li><li>**Hiba** – Hibaüzenet jelenik meg, és a műveletet a rendszer megakadályozza.</li></ul><p>A vámügynök vagy a helyi törvények meghatározott értéket renelhetnek el a mező számára.</p> |
| Több szállítási mód tűréshatára | Annak kiválasztása, hogy mi történik, ha a hajóúttól eltérő szállítási módú beszerzési rendelés árui kerülnek hozzáadásra a hajóúthoz.<ul><li>**Elfogadás** – A rendszernek engedélyeznie kell a műveletet.</li><li>**Figyelmeztetés** – Figyelmeztetés jelenik meg, de a művelet végrehajtható.</li><li>**Hiba** – Hibaüzenet jelenik meg, és a műveletet a rendszer megakadályozza.</li></ul> |
| Több raktár tűréshatára | Annak kiválasztása, hogy mi történik, ha egy hajóút több rendeléssort tartalmaz, és azokat különböző raktárakba kell szállítani. Előfordulhat, hogy ezek a rendeléssorok egy vagy több beszerzési rendelés között oszlanak meg.<ul><li>**Elfogadás** – A rendszernek engedélyeznie kell a műveletet.</li><li>**Figyelmeztetés** – Egy figyelmeztetés jelenik meg.</li><li>**Hiba** – Hibaüzenet jelenik meg.</li></ul> |
| Hiányzó térfogat | Annak kiválasztása, hogy mi történik, ha a felhasználó térfogat nélküli cikket ad hozzá az hajóúthoz.<ul><li>**Elfogadás** – A rendszernek el kell fogadnia a cikket.</li><li>**Figyelmeztetés** – Egy figyelmeztetés jelenik meg.</li><li>**Hiba** – Hibaüzenet jelenik meg.</li></ul><p>Ha a költségek kiszámítására és arányosítására térfogatok kerülnek felhasználásra, akkor javasoljuk, hogy a *Figyelmeztetés* vagy a *Hiba* lehetőséget válassza.</p> |
| Szolgáltató az út költsége nélkül | Annak kiválasztása, hogy mi történik, ha a felhasználó olyan szolgáltató számláját próbálja meg feldolgozni, amely nincs hajóúthoz kapcsolva. <ul><li>**Elfogadás** – A rendszernek engedélyeznie kell a műveletet.</li><li>**Figyelmeztetés** – Egy figyelmeztetés jelenik meg.</li><li>**Hiba** – Hibaüzenet jelenik meg.</li></ul><p>Javasoljuk, hogy válassza a *Figyelmeztetés* lehetőséget.</p> |

### <a name="defaults-fasttab"></a>Alapértelmezések gyorslap

A következő táblázat felsorolja azokat a mezőket, amelyek elérhetők a **Költségszámítás** oldal **Általános** lapjának **Alapértelmezések** gyorslapján.

| Beállítás | Leírás |
|---|---|
| Napló neve | Az *Érkeztetési napló létrehozása* funkció által használt alapértelmezett napló kiválasztása. |
| Út állapota | Annak az állapotnak a kiválasztása, amellyel a hajóútnak rendelkeznie kell, mielőtt a felhasználók beállíthatanának hozzá egy bérelt szállítókonténert a rendszerben. Ez a művelet általában akkor történik, amikor az áruk úton vagy a kikötőben vannak. |
| Utazássablon | Válassza ki az új bérelt szállítókonténerekhez használni kívánt alapértelmezett hajóútsablont. Általában olyan hajóútsablont ajánlott választani, amely tartalmazza a bérleti költségeket. |
| Mozgás | Ha a szállítás többlet/hiány mennyisége a megadott tűréshatáron belül van, a rendszer automatikusan feldolgoz egy átmozgatási naplót. A használni kívánt alapértelmezett átmozgatási napló kiválasztása. A kijelölt átmozgatási naplónév **Ellenszámla** mezőjének értékkel kell rendelkeznie. |
| Átutalás | Alulszállítás feldolgozásakor a rövid bevételezési mennyiség átkerül az alulszállítási raktárba. A használni kívánt alapértelmezett átviteli napló kiválasztása. |
| Nem úthoz kapcsolódó beszerzési rendelések letiltása | A Partraszállítási költség alul-/túlszállítás funkciójának kikapcsolása az olyan beszerzési rendelések esetén, amelyek nincsenek hajóúthoz kapcsolva. |
| Nem úton lévő árukra vonatkozó beszerzési rendelések letiltása | A Partraszállítási költség alul-/túlszállítás funkciójának kikapcsolása az olyan beszerzési rendelések esetén, amelyek nem használnak úton lévő áruk funkciót. |
| Úton lévő áruk túlbevételezési türelmi időszaka | Megadja a napok számát, amíg a szállítókonténer első bevételezése után az adott szállítókonténerre további túlbevételezéseket lehet még végrehajtani. |

## <a name="status-updates-tab"></a>Állapotfrissítések lap

A rendszer az állapotértékeket használja az egyes hajóutak állapotának jelzésére. Az hajóút állapotértékei automatikusan alkalmazhatók a hajóútkövetéssel vagy az időszakos kötegelt feladatokkal a hajóutakra. Manuálisan is alkalmazhatja őket, ha megnyitja a hajóutat, majd kiválaszt egy állapotot a Művelet panel **Kezelés** lapjának **Hajóút frissítése** csoportjában. 

Tetszőleges hajóútállapot-értéket lehet létrehozni. A **Partraszállítási költség paraméterei** oldal **Állapotfrissítések** lapján azonban négyet kell külön célra használtként definiálni. Az alábbi táblázat bemutatja az ott rendelkezésre álló mezőket.

| Beállítás | Leírás |
|---|---|
| Költség elszámolva | Annak a hajóútállapotnak a kiválasztása, amely azt jelzi, hogy az út véglegesített. |
| Szállítás alatt | Annak a hajóútállapotnak a kiválasztása, amely azt jelzi, hogy a hajóút folyamatban van. |
| Költségszámításra kész | Annak a hajóútállapotnak a kiválasztása, amely azt jelzi, hogy a hajóút költségszámításra kész. Ez az állapot akkor használatos, amikor minden olyan készletbeszerzési számla és hajóútköltség-számla feldolgozásra került a hajóúthoz, ahol a **Hajóútköltség jóváírása** mezőben a *Szállító* beállítás van megadva. A költségszámítási folyamaton meg nem feleső hajóutak állapota *Költségszámításra kész* lesz.|
| Előzetesen elszámolt költségek | Annak a hajóútállapotnak a kiválasztása, amely azt jelzi, hogy a hajóút előzetes költségszámítás alatt van. Ezt az állapotot akkor használja a rendszer, amikor egy új költségtranzakciót adnak egy hajóúthoz a költségelszámolás után. Új költségtranzakciókat lehet hozzáadni egy korábban költségelszámolt hajóúthoz, amikor egy második fuvarszámla vagy egy váratlan álláspénz érkezik. Ezt az állapotot automatikusan alkalmazza a rendszer, amikor egy új hajóútköltség hozzáadódik egy elszámolt költségű hajóúthoz. |

## <a name="voyage-creator-tab"></a>Hajóút létrehozója lap

Az alábbi táblázat a **Partraszállítási költség paraméterei** oldal **Hajóút létrehozója** lapján található szakaszokat ismerteti.

| Szakasz | Leírás |
|---|---|
| Tűréshatárok | A **Külső térfogat tűréshatára** és a **Külső tömeg tűréshatára** mezők határozzák meg azokat a küszöbértékeket, amely felett az áruk túlzott térfogatúnak és túlsúlyosnak számítanak. Ha egy felhasználó árut ad hozzá a **Hajóútszerkesztő** oldalon, és a térfogat vagy a súly meghaladja az itt beállított értéket, a rendszer figyelmeztetést ad. Az egyes mezők értéke a megfelelő szállítókonténerhez beállított maximális térfogat vagy súly százalékában van kifejezve. Azt ajánljuk, hogy az érték a maximális térfogat vagy súly 5 és 10 százaléka között legyen. |
| Ívlaplétrehozás beállítása | A rendszer a hajóút-létrehozási folyamat során több levelet is létrehozhat. Ebben a szakaszban adhatja meg, hogy mikor kell új levelet létrehozni. A rendszer a szakasz minden sorában ellenőrzi a megadott táblát és mezőt, és minden egyes egyedi mezőértékhez létrehoz egy levelet. |

## <a name="cost-estimates-tab"></a>Költségbecslések lap

A **Partrszállítási költség** paraméterei oldal **Költségbecslés** lapja csak egy mezőt biztosít: **Alapértelmezett költségszámítási verzió**. Ez a mező csak akkor érvényes, ha a költségszámítási mód *Standard költségszámítás*. A *Cikk önköltségi árának frissítése* ismétlődő feladathoz használt alapértelmezett költségszámítási verzió kiválasztása. Előfordulhat, hogy az új pénzügyi év minden megkezdésekor módosítania kell ezt a beállítást.

## <a name="inventory-dimensions-tab"></a>Készletdimenziók lap

A **Partraszállítási költség paraméterei** oldal **Készletdimenziók** lapján lehet szabályozni, hogy alapértelmezés szerint melyik elérhető készletdimenziók jelennek meg minden olyan Partraszállítási költség oldalon, ahol dimenziókat használnak.

Jelöljön ki egy dimenziót, majd állítsa a **Hajóút sorai**, az **Úton lévő áruk** és/vagy a **Költségbecslések** lehetőséget *Igen* beállításra minden olyan oldal esetében, ahol a dimenziót alapértelmezés szerint meg kell jelenni. Ismételje meg ezt a lépést a többi dimenzióval szükség szerint.

A lapon található beállítások meghatározzák a jogi személyek közötti kijelölt oldalak alapértelmezett dimenzióit. A megadott lapok egyikén dolgozó felhasználók azonban a Művelet panel **Készlet \> Dimenziók megjelenítése** lehetőségének kiválasztásával felülbírálhatják az alapértelmezett dimenziókat.

## <a name="number-sequences-tab"></a>Számsorozatok lap

A **Partraszállítási költség paraméterei** oldal **Számsorozatok** lapja felsorolja a Partraszállítási költség által megkövetelt hivatkozási számsorozatok mindegyik típusát, de ez nincs megosztva több jogi személy között. A lista minden egyes hivatkozása esetében válasszon egy számsorozatkódot.

> [!NOTE]
> Többvállalatos konfigurációban minden vállalathoz (jogi személyhez) különböző számsorozatokat kell létrehozni.

## <a name="shared-number-sequences-tab"></a>Megosztott számsorozatok lap

A **Partraszállítási költség paraméterei** oldal **Megosztott számsorozatok** lapja felsorolja a Partraszállítási költség esetében a jogi személyek között megosztott hivatkozási számsorozatok mindegyik típusát. Jelenleg csak egy számsorozat szerepel a listában. Ezt a számsorozatot használja a program a hajóút-azonosítóhoz.

A **Minden hajóút** oldalon a felhasználók minden jogi személy minden hajóútját megtekinthetik. Hajóút szerkesztéséhez és feldolgozásához azonban a felhasználóknak a kiválasztott rekord jogi személyében kell lenniük.

## <a name="feature-visibility-tab"></a>Funkció láthatósága lap

A Partraszállítási költség a Microsoft Dynamics 365 Supply Chain Management számos gyakran használt oldalán biztosít szolgáltatásokat (mezőket és funkciókat). Ezek az oldalak a szállítói alapadatokkal, kiadott termékekkel, beszerzési rendelésekkel, átmozgatási rendelésekkel és raktárbeállításokkal kapcsolatos oldalakat tartalmaznak. Ha Partraszállítási költséget használ, akkor ezeket a funkciókat minden helyen láthatóvá kell tenni, mielőtt azokból haszna lenne. Ha nem használja a Partraszállítási költséget, elrejtheti a funkciókat, hogy ne legyenek útban.

A **Partraszállítási költség paraméterei** oldal **Funkció láthatósága** lapján állítsa az **Aktiválás** lehetőséget *Igen* beállításra, hogy a Partraszállítási költség funkciói minden helyen láthatók legyenek, ahol elérhetők. Állítsa *Nem* beállításra, ha el kell rejteni a Partraszállítási költségen kívüli gyakori lapokon a funkciókat. Ugyanakkor, még ha *Nem* beállítás is van megadva, maga a modul, beleértve a **Partraszállítási költség paraméterei** oldalt is, elérhető marad a hozzáféréshez megfelelő engedélyekkel rendelkező felhasználók számára.
