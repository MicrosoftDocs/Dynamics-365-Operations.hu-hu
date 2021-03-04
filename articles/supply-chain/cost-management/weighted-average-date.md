---
title: Dátum szerinti súlyozott átlag
description: A dátum szerinti súlyozott átlag elvű készletmodell a súlyozott átlag elven alapul, amelyben a készletből történő kiadásokat a készletzárási időszak egyes napjain a készletbe bevételezett cikkek átlagos értékével súlyozzák.
author: AndersGirke
manager: tfehr
ms.date: 10/25/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventJournalLossProfit, InventMarking, InventModelGroup, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations, Retail
ms.custom: 28991
ms.assetid: 945d5088-a99d-4e54-bc42-d2bd61c61e22
ms.search.region: Global
ms.search.industry: Retail
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d36f60a13fbee91100e406150e7f5ca890320436
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4429333"
---
# <a name="weighted-average-date"></a>Dátum szerinti súlyozott átlag

[!include [banner](../includes/banner.md)]

A dátum szerinti súlyozott átlag elvű készletmodell a súlyozott átlag elven alapul. A súlyozott átlag elven alapul, amelyben a készletből történő kiadásokat a készletzárási időszak egyes napjain a készletbe bevételezett cikkek átlagos értékével súlyozzák. 

Ha a dátum szerinti súlyozott átlag elv alapján készletzárást futtat, az egyes napok minden bevételezését egy virtuális kiadással egyenlíti ki. Ez a virtuális kiadás tárolja a teljes bevételezett mennyiséget az adott napra. A virtuális kiadáshoz egy hasonló virtuális bevételezés tartozik, amelyből a kiadások egyenlíthetők ki. Ily módon minden kiadás ugyanazzal a költséggel történik. A virtuális kiadást és bevételezést virtuális átmozgatásnak lehet tekinteni, ezt a *súlyozott átlagú készletzárás átmozgatásának* hívják. 

Ha az adott napon vagy azelőtt csak egy bevételezés történt akkor nem kell értékelnie az átlagot. Amiért az összes kiadást kiegyenlítette erről a bevételezésből, a virtuális transzfer nem jön létre. Hasonlóképpen, ha az adott napig csak egy kiadás történik, akkor nincsenek olyan bevételezések, amelyekből átlagot lehetne számítani, tehát nem jön létre a virtuális transzfer. A súlyozott átlag dátum alkalmazása esetén egyes készlettranzakciók megjelölésével meghatározhatja, hogy egy adott bevételezés ne a súlyozott átlag elv szerint, hanem egy meghatározott kiadással legyen kiegyenlítve. Ebben az esetben nem használható a súlyozott átlagos dátum szabály. A dátum szerinti súlyozott átlagon alapuló készletmodell alkalmazása esetén tanácsos havonta készletzárást végezni. 

A rendszerben az alábbi képlet segítségével számítja ki a súlyozott átlagos dátum költségét: 

Súlyozott átlag = (\[Q1 × P1\] + \[Q2 × P2\] + \[Q *n* × P *n*\]) ÷ (Q1 + Q2 + Q *n*) 

A készlet zárása során a számítás minden nap lefut a zárási időszak alatt, ahogy az alábbi ábrán is látható. 

![Dátummal súlyozott átlagos napi számítási modell](./media/weightedaveragedatedailycalculationmodel.gif) 

A készletkiadásokat hagyó készlettranzakciók, például az értékesítési rendelések, készletnaplók, beszerzési jóváírások és termelési rendelések a feladás dátumakor becsült átlagos önköltségi áron kerülnek be a rendszerbe. Ezt a becsült önköltségi árat más néven mozgóátlagon alapuló önköltségi árnak is nevezik. A készletzárás napján a rendszer elemzi az előző időszak, előző napok és az adott nap készlettranzakcióit. Az elemzéssel meghatározható hogy az alábbiak közül melyik zárási elv használata szükséges:

-   Közvetlen kiegyenlítés
-   Összesített kiegyenlítés

Az elszámolások készletzárási feladások, amelyek módosítják a kiadásokat a záró dátumnak megfelelő helyes súlyozott átlagra. 

**Megjegyzés:** További információkért a kiegyenlítéssel kapcsolatban lásd a készletzárás cikket. A következő példák azt mutatják be, hogy milyen hatást fejt ki a súlyozott átlag öt konfigurációban:

-   Dátummal súlyozott átlagot alkalmazó közvetlen elszámolás a **Tényleges értékkel együtt** beállítás nincs aktiválva
-   Dátummal súlyozott átlagot alkalmazó összesített elszámolás a **Tényleges értékkel együtt** beállítás aktiválása nélkül
-   Dátummal súlyozott átlagot alkalmazó közvetlen elszámolás a **Tényleges értékkel együtt** beállítással
-   Dátummal súlyozott átlagot alkalmazó összesített elszámolás a **Tényleges értékkel együtt** beállítással
-   Dátummal súlyozott átlag jelölés használatával

## <a name="weighted-average-date-direct-settlement-when-the-include-physical-value-option-isnt-used"></a>Dátummal súlyozott átlagot alkalmazó közvetlen elszámolás a Tényleges értékkel együtt beállítás nincs aktiválva
A jelenlegi verzióban a dátummal súlyozott átlaghoz alkalmazott közvetlen elszámolási elv megegyezik a termék korábbi verzióiban használttal. A rendszer a bevételezések és kiadások között közvetlen elszámolást alkalmaz. A rendszer ezt a közvetlen elszámolási elvet az alábbi konkrét helyzetekben alkalmazza:

-   Az időszak folyamán egy bevételezést, illetve egy vagy több kiadást adtak fel.
-   Az időszak folyamán csak kiadásokat adtak fel, és a tényleges készletben csak egy előző zárásból származó cikkek találhatók.

Az alábbi esetben egy pénzügyi szempontból frissített bevételezés és kiadás feladására került sor. A készlet zárása során a rendszer közvetlenül a kiadással szemben számolja el a bevételezést, és a kiadás alkalmával nem kell módosítani az önköltségi árat. 

A következő ábrán ezek a tranzakciók láthatók:

-   1a. Fizikai bevételezés készletre, 5 mennyiséggel, egyenként 10,00 USD áron.
-   1b. Pénzügyi bevételezés készletre, 5 mennyiséggel, egyenként 10,00 USD áron.
-   2a. Fizikai kiadás készletről, 2 mennyiséggel, egyenként 10,00 USD áron.
-   2b. Pénzügyi kiadás készletről, 2 mennyiséggel, egyenként 10,00 USD áron.
-   3. A közvetlen elszámolási módszer alkalmazásával készletzárás történik a pénzügyi készlet bevételezés elszámolására a pénzügyi készletkiadással szemben.

![Dátummal súlyozott átlagot alkalmazó közvetlen elszámolás a Tényleges értékkel együtt beállítás nélkül](./media/weightedaveragedatedirectsettlementwithoutincludephysicalvalue.gif) 

**Az ábra jelmagyarázata:**

-   A készlettranzakciókat függőleges nyilak jelölik.
-   A készletre való bevételezéseket az idősor fölötti függőleges nyilak jelölik.
-   A készletről való kiadásokat az idősor alatti függőleges nyilak jelölik.
-   Minden függőleges nyíl alatt vagy fölött a készlettranzakció értéke van megadva, a *mennyiség*@*egységár* formátumban.
-   Ha zárójelbe van téve egy készlettranzakció értéke, akkor az arra utal, hogy a készlettranzakció fizikailag van feladva a készletre.
-   Ha nincs zárójelbe téve egy készlettranzakció értéke, akkor az arra utal, hogy a készlettranzakció pénzügyileg van feladva a készletre.
-   Minden új bevételezési és kiadási tranzakciót egy új címke jelöl.
-   Mindegyik függőleges nyíl egy sorszámozott azonosítóval van ellátva, például *1a*. Az azonosítók a készlettranzakciók feladásának időbeli sorrendjét jelölik.
-   A készletzárásokat egy piros színű, szaggatott függőleges vonal és a *Készletzárás* felirat jelöli.
-   A készletzárás által végrehajtott elszámolásokat szaggatott piros nyilak jelölik, amelyek átlósan haladnak egy bevételezéstől egy kiadás felé.

## <a name="weighted-average-date-summarized-settlement-when-the-include-physical-value-option-isnt-used"></a>Dátummal súlyozott átlagot alkalmazó összesített elszámolás a Tényleges értékkel együtt beállítás aktiválása nélkül
A súlyozott átlag az alábbi elven alapul: minden bevétel a zárási időszakban összeadódik egy új készlettranszfer tranzakcióba. A tranzakció neve *súlyozott átlagú készletzárás*. A nap bevételezéseit az újonnan létrehozott készletmozgási tranzakcióval szemben számolja el a program. A nap minden kiadását az új készletmozgási tranzakció bevételezésével szemben számolja el a program. Ha pozitív a tényleges készlet a készletzárás után, akkor ezt a tényleges készletet és a készlet értékét összegzi az új készletmozgási tranzakció-bevételezés. Ha negatív a készlet a készletzárás után, a tényleges készlet és a készletérték a nem teljesen elszámolt egyes kiadások összege. 

Az alábbi helyzetben az időszak során több pénzügyi szempontból frissített bevételezés és kiadás feladására került sor. A rendszer a készletzárás során minden egyes nap kiértékelésével állapítja meg, hogy a zárásnak hogyan kell kezelnie az egyes napokat. 

A következő ábrán ezek a tranzakciók láthatók: 

**1. nap:**

-   1a. Fizikai bevételezés készletre, 3 mennyiséggel, egyenként 15,00 USD áron.
-   1b. Pénzügyi bevételezés készletre, 3 mennyiséggel, egyenként 15,00 USD áron.
-   2a. Fizikai kiadás készletről, 1 mennyiséggel, 15,00 USD mozgó átlagáron.
-   2b. Pénzügyi kiadás készletről, 1 mennyiséggel, 15,00 USD mozgó átlagáron.

A rendszer az 1. naphoz a közvetlen elszámolási megközelítést fogja alkalmazni. 

**2. nap:**

-   3a. Fizikai kiadás készletről, 1 mennyiséggel, 15,00 USD mozgó átlagáron
-   3b. pénzügyi készletkiadás, a mennyiség 1, a költség a 15.00 USD-s mozgóátlag.

A rendszer a 2. naphoz a közvetlen elszámolási megközelítést fogja alkalmazni. 

**3. nap:**

-   4a. Fizikai kiadás készletről, 1 mennyiséggel, 15,00 USD mozgó átlagáron
-   4b. pénzügyi készletkiadás, a mennyiség 1, a költség a 15.00 USD-s mozgóátlag.
-   5a. Fizikai bevételezés készletre, 1 mennyiséggel, egyenként 17,00 USD áron
-   5b. Pénzügyi bevételezés készletre, 1 mennyiséggel, egyenként 17,00 USD áron

Készletzárást hajtanak végre. A közvetlen elszámolást kell alkalmazni, mert több napon átívelő módon több bevételezés van.

-   7a. Pénzügyi kiadás jön létre 2 mennyiséggel 32,00 USD értékben a súlyozott átlagot alkalmazó készletzáráshoz, amely összesíti az addig nem lezárt összes pénzügyi készletre vételt.
-   7b. A program létrehoz egy súlyozott átlagú készletzárási tranzakció pénzügyi bevételezést a 7a. tétel ellentételezéseként.

A rendszer előállítja és feladja az összesített készletmozgási tranzakciót. Továbbá a rendszer kiegyenlíti az adott napra vonatkozó összes bevételezést és az előző napok aktuális készletét elszámolja az összesített készletmozgási kiadási tranzakcióval szemben. Az adott nap összes kiadását az összesített készletmozgási bevételezési tranzakcióval szemben számolja el. A súlyozott átlaggal számított önköltségi ár 16,00 USD lesz. A kiadáshoz 1,00 USD értékű módosítás fog tartozni a súlyozott átlaggal megállapított költség korrekciója céljából. Az új mozgóátlagon alapuló önköltségi ár 16,00 USD. 

Az alábbi ábrán ez a tranzakciósorozat, és a súlyozott átlag készletmodell használatának hatása látható, továbbá az összesített tartozáskiegyenlítés elv a **Tényleges értékkel együtt** lehetőség nélkül. 

![Dátummal súlyozott átlagot alkalmazó összesített elszámolás a Tényleges értékkel együtt beállítás nélkül](./media/weightedaveragedatesummarizedsettlementwithoutincludephysicalvalue.gif) 

**Az ábra jelmagyarázata**

-   A készlettranzakciókat függőleges nyilak jelölik.
-   A készletre való bevételezéseket az idősor fölötti függőleges nyilak jelölik.
-   A készletről való kiadásokat az idősor alatti függőleges nyilak jelölik.
-   Minden függőleges nyíl alatt vagy fölött a készlettranzakció értéke van megadva, a *mennyiség*@*egységár* formátumban.
-   Ha zárójelbe van téve egy készlettranzakció értéke, akkor az arra utal, hogy a készlettranzakció fizikailag van feladva a készletre.
-   Ha nincs zárójelbe téve egy készlettranzakció értéke, akkor az arra utal, hogy a készlettranzakció pénzügyileg van feladva a készletre.
-   Minden új bevételezési és kiadási tranzakciót egy új címke jelöl.
-   Mindegyik függőleges nyíl egy sorszámozott azonosítóval van ellátva, például *1a*. Az azonosítók a készlettranzakciók feladásának időbeli sorrendjét jelölik.
-   A készletzárásokat egy piros színű, szaggatott függőleges vonal és a *Készletzárás* felirat jelöli.
-   A készletzárás által végrehajtott elszámolásokat szaggatott piros nyilak jelölik, amelyek átlósan haladnak egy bevételezéstől egy kiadás felé.
-   A piros átlós nyilak jelzik azt a bevételezési tranzakciót, amelyet a rendszer által létrehozott kiadási tranzakciókkal szemben elszámol a program.
-   A zöld átlósnyilak jelzik azokat a rendszer által ellentételként generált bevételezési tranzakciókat, amelyekkel szemben az eredetileg feladott kiadási tranzakciót elszámolja a program.

## <a name="weighted-average-date-direct-settlement-when-the-include-physical-value-option-is-used"></a>Dátummal súlyozott átlagot alkalmazó közvetlen elszámolás a Tényleges értékkel együtt beállítással
A jelenlegi verzióban a dátummal súlyozott átlaghoz alkalmazott közvetlen elszámolási elv megegyezik a termék korábbi verzióiban használttal. A rendszer a bevételezések és kiadások között közvetlen elszámolást alkalmaz. A rendszer ezt a közvetlen elszámolási elvet az alábbi konkrét helyzetekben alkalmazza:

-   Az időszak folyamán egy bevételezést, illetve egy vagy több kiadást adtak fel.
-   Az időszak folyamán csak kiadásokat adtak fel, és a készletben egy előző zárásból származó, tényleges készlet található.

Ha bejelöli a **Tényleges értékkel együtt** jelölőnégyzetet egy cikknél a **Cikkmodell csoport** oldalon, akkor a rendszer fizikailag frissített nyugtákat használ a becsült költségár vagy mozgóátlag kiszámításához. A kiadások feladása az időszaknak ezen a becsült önköltségi árán alapul. A készletzárás során a súlyozott átlag számításában csak a pénzügyi bevételezések számítanak.

## <a name="weighted-average-date-summarized-settlement-when-the-include-physical-value-option-is-used"></a>Dátummal súlyozott átlagot alkalmazó összesített elszámolás a Tényleges értékkel együtt beállítással
Ha bejelöli a **Tényleges értékkel együtt** jelölőnégyzetet egy cikknél a **Cikkmodell csoport** oldalon, akkor a rendszer fizikailag frissített nyugtákat használ a becsült költségár vagy mozgóátlag kiszámításához. A kiadások feladása az időszaknak ezen a becsült önköltségi árán alapul. A készletzárás során a súlyozott átlag számításában csak a pénzügyi bevételezések számítanak. A súlyozott átlag kiegyenlítés, amely azon az elven alapul, hogy a minden, a záró időszakban szereplő bevételezés egy új készletmozgási tranzakcióban összegződik, amelynek *súlyozott átlagú készletzárás* a neve. A nap bevételezéseit az újonnan létrehozott készletmozgási tranzakcióval szemben számolja el a program. A nap minden kiadását az új készletmozgási tranzakció bevételezésével szemben számolja el a program. Ha pozitív a tényleges készlet a készletzárás után, akkor ezt a tényleges készletet és a készlet értékét összegzi az új készletmozgási tranzakció-bevételezés. Ha negatív a készlet a készletzárás után, a tényleges készlet és a készletérték a nem teljesen elszámolt egyes kiadások összege.

## <a name="weighted-average-date-when-marking-is-used"></a>Dátummal súlyozott átlag jelölés használatával
A jelölés egy olyan folyamat, amellyel összekapcsolható egy kiadási tranzakció egy bevételezési tranzakcióval. A jelölés történhet a tranzakciók feladása előtt és után is. A jelölés használható a készlet pontos költségének megállapítására a tranzakció feladásakor vagy a készletzárás végrehajtásakor. 

Tegyük fel például, hogy az ügyfélszolgálati osztály elfogadott egy sürgős megrendelést egy fontos vevőtől. A rendelés sürgős, tehát többe fog kerülni az ügyfél kérésének teljesítése. Azt szeretné, ha a készlet költsége tükröződne az árrésben is (más szóval az eladott áruk beszerzési értékébe, ELÁBÉ) az adott értékesítési számla esetében. A beszerzési rendelés feladásakor a készlet bevételezése 120,00 USD értéken történik. A beszerzési rendelési dokumentum meg van jelölve a beszerzési rendelésben, mielőtt a szállítólevelet vagy a számlát feladják. Az ELÁBÉ ekkor 120,00 USD lesz, az aktuális cikk mozgóátlaga helyett. Ha még a jelölés előtt feladják a csomagjegyzéket vagy a számlát, a feladott ELÁBÉ megfelel a beszerzési ár mozgóátlagának. A két tranzakció még a készletzárás végrehajtása előtt is összekapcsolható egymással. Amikor megjelölnek egy bevételezési tranzakciót egy kiadási tranzakcióval, a cikk modellcsoportjában meghatározott módszert nem veszi figyelembe a program. Ehelyett a rendszer kiegyenlíti ezeket a tranzakciókat egymással szemben. 

Kiadási tranzakciót a tranzakció feladása előtt jelölhet hozzá egy nyugtához. Ezt megteheti egy értékesítési rendelés sorából az **Értékesítési rendelés** oldalon. A nyitott bevételezési tranzakciókat megtekintheti **Jelölés** oldalon. Kiadási tranzakciót a tranzakció feladása után jelölhet hozzá egy nyugtához. Egyeztethet vagy megjelölhet egy kiadási tranzakciót egy nyílt nyugtájú tranzakcióhoz egy leltárazott cikk esetén, feladott készlethelyesbítési naplósorból. A következő ábrán ezek a tranzakciók láthatók:

-   1a. Fizikai bevételezés készletre, 1 mennyiséggel, 10,00 USD önköltségi áron.
-   1b. Pénzügyi bevételezés készletre, 1 mennyiséggel, 10,00 USD önköltségi áron.
-   2a. Fizikai bevételezés készletre, 1 mennyiséggel, 20,00 USD önköltségi áron.
-   2b. Pénzügyi bevételezés készletre, 1 mennyiséggel, 20,00 USD önköltségi áron.
-   3a. Fizikai bevételezés készletre, 1 mennyiséggel, 25,00 USD önköltségi áron.
-   4a. Fizikai bevételezés készletre, 1 mennyiséggel, 30,00 USD önköltségi áron.
-   4b. Pénzügyi bevételezés készletre, 1 mennyiséggel, 30,00 USD önköltségi áron.
-   5a. Fizikai kiadás készletről, 1 mennyiséggel, 21,25 USD önköltségi áron (a pénzügyileg és fizikailag frissített tranzakciók mozgóátlaga).
-   5b. Egy 1 mennyiségű pénzügyi készletkiadást jelöléssel összekötnek a 2b bevételezéssel a tranzakció feladása előtt. Ezt a tranzakciót 20,00 USD önköltségi árral adja fel a program.
-   6a. Fizikai kiadás készletről, 1 mennyiséggel, 21,25 USD áron.
-   7. Készletzárást hajtanak végre. Mivel a pénzügyileg frissített tranzakció össze van kapcsolva egy meglévő kiadással, ezeket a tranzakciókat egymással szemben számolja el a program, és nem kerül sor helyesbítésre.

Az új, mozgóátlagon alapuló önköltségi ár a pénzügyileg és fizikailag frissített tranzakciók átlagának, azaz 27,50 USD összegnek felel meg. A következő ábrán a tranzakciók sorozata látható, és a súlyozott átlag dátumon alapuló készletmodell és jelölés folyamatra gyakorolt hatását ábrázolja.

![Dátummal súlyozott átlag jelöléssel](./media/weightedaveragedatewithmarking.gif) 

**Az ábra jelmagyarázata:**

-   A készlettranzakciókat függőleges nyilak jelölik.
-   A készletre való bevételezéseket az idősor fölötti függőleges nyilak jelölik.
-   A készletről való kiadásokat az idősor alatti függőleges nyilak jelölik.
-   Minden függőleges nyíl alatt vagy fölött a készlettranzakció értéke van megadva, a *mennyiség*@*egységár* formátumban.
-   Ha zárójelbe van téve egy készlettranzakció értéke, akkor az arra utal, hogy a készlettranzakció fizikailag van feladva a készletre.
-   Ha nincs zárójelbe téve egy készlettranzakció értéke, akkor az arra utal, hogy a készlettranzakció pénzügyileg van feladva a készletre.
-   Minden új bevételezési és kiadási tranzakciót egy új címke jelöl.
-   Mindegyik függőleges nyíl egy sorszámozott azonosítóval van ellátva, például *1a*. Az azonosítók a készlettranzakciók feladásának időbeli sorrendjét jelölik.
-   A készletzárásokat egy piros színű, szaggatott függőleges vonal és a *Készletzárás* felirat jelöli.
-   A készletzárás által végrehajtott elszámolásokat szaggatott piros nyilak jelölik, amelyek átlósan haladnak egy bevételezéstől egy kiadás felé.






[!INCLUDE[footer-include](../../includes/footer-banner.md)]