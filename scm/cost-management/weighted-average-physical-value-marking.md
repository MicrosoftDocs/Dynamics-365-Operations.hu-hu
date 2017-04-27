---
title: "Súlyozott átlagos közvetlen elszámolás a tényleges értékkel együtt"
description: 
author: YuyuScheller
manager: AnnBe
ms.date: 2016-03-17 15 - 15 - 52
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: InventJournalLossProfit, InventMarking, InventModelGroup, SalesTable
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 65501
ms.assetid: 25041ff0-bafe-484d-a94a-e1772ad43204
ms.search.region: Global
ms.search.industry: Retail
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 1afd7855fd05d0bacb60a7a45bba68e7041a4f4b
ms.lasthandoff: 03/29/2017


---

# <a name="weighted-average-with-physical-value-and-marking"></a>Súlyozott átlagos közvetlen elszámolás a tényleges értékkel együtt



A készletzárás futtatásakor a program minden bevételezést egy virtuális kiadással egyenlít ki, amely a teljes bevételezett mennyiséget és értéket tartalmazza. Ehhez a virtuális kiadáshoz tartozik egy virtuális bevételezés is, amelyből a kiadások egyenlíthetők ki. Ily módon minden kiadás ugyanazzal a költséggel történik. A virtuális kiadás és bevételezés virtuális transzfernek tekinthető, amelynek neve „súlyozott átlagú készletzárási transzfer”.
Ha csak egy bevételezés van, akkor minden kiadást ebből egyenlítenek ki, tehát nem jön létre virtuális transzfer. A súlyozott átlag elv alkalmazása esetén egyes készlettranzakciók megjelölésével meghatározhatja, hogy egy adott bevételezés ne a súlyozott átlag elv szerint, hanem egy meghatározott kiadással legyen kiegyenlítve. A súlyozott átlagon alapuló készletmodell alkalmazása esetén tanácsos havonta készletzárást végezni. A készlet súlyozott átlaga költségszámítási módszer számítása a következő képlettel történik:
-   Súlyozott átlag = (Q1\*P1 + Q2\*P2 + Qn\*Pn) / (Q1 + Q2 + Qn)

A készletkiadásokat készlettranzakciók. Értékesítési rendelések, készletnaplók, és a termelési rendelések, a feladási dátumon becsült önköltségi árral történik. Ennek a becsült önköltségi árnak a másik neve  folyó átlag. A készletzárás időpontjában a rendszer elemzi az előző és az aktuális időszak készlettranzakcióit, és meghatározza, hogy az alábbi zárási elvek közül melyiket kell alkalmazni:
-   Közvetlen kiegyenlítés
-   Összesített kiegyenlítés

Az elszámolások készletzárási feladások, amelyek módosítják a kiadásokat a záró dátumnak megfelelő helyes súlyozott átlagra. A következő példák azt mutatják be, hogy milyen hatást fejt ki a súlyozott átlag öt eltérő konfigurációban:
-   Súlyozott átlagú közvetlen kiegyenlítés a tényleges érték figyelembevételével
-   Súlyozott átlagú összesített kiegyenlítés a tényleges érték figyelembevétele nélkül
-   Súlyozott átlagú közvetlen kiegyenlítés a tényleges érték figyelembevételével
-   Súlyozott átlagú összesített kiegyenlítés a tényleges érték figyelembevételével
-   Súlyozott átlag jelöléssel

## <a name="weighted-average-direct-settlement-without-include-physical-value"></a>Súlyozott átlagú közvetlen kiegyenlítés a tényleges érték figyelembevétele nélkül
A közvetlen elszámolási elv megegyezik a termék korábbi verzióiban a súlyozott átlaghoz használt elvvel. A rendszer a bevételezések és kiadások között közvetlen elszámolást alkalmaz. A rendszer ezt a közvetlen elszámolási elvet bizonyos konkrét helyzetekben alkalmazza:
-   Az időszak folyamán egy bevételezést, illetve egy vagy több kiadást adtak fel.
-   Az időszak folyamán csak kiadásokat adtak fel, és a tényleges készletben csak egy előző zárásból származó cikkek találhatók.

Az alábbi esetben egy pénzügyi szempontból frissített bevételezés és kiadás feladására került sor. A készlet zárása során a rendszer közvetlenül a kiadással szemben számolja el a bevételezést, és a kiadás alkalmával nem kell módosítani az önköltségi árat. Az alábbi ábra a következő tranzakciókat mutatja be.
-   1a. Fizikai bevételezés készletre, 5 mennyiséggel, egyenként 10,00 USD áron.
-   1b. Pénzügyi bevételezés készletre, 5 mennyiséggel, egyenként 10,00 USD áron.
-   2a. Tényleges bevételezés a készletbe, mennyiség 2 darab, 10,00 USD/darab áron
-   2b. Pénzügyi bevételezés a készletbe, mennyiség 2 darab, 10,00 USD/darab áron
-   3. Készletzárás a közvetlen kiegyenlítéses módszerrel a pénzügyi készletbevételezések és a pénzügyi készletkiadások kiegyenlítése céljából.

A következő diagram bemutatja a tranzakciósorozatot, és a súlyozott átlag készletmodell, valamint a Tényleges értékkel együtt beállítás nélkül alkalmazott közvetlen kiegyenlítési elv hatását a folyamatra. ![Súlyozott átlagos közvetlen elszámolás a tényleges érték nélkül](./media/weightedaveragedirectsettlementwithoutincludephysicalvalue.gif) Jelmagyarázat
-   A készlettranzakciókat függőleges nyilak jelölik.
-   A készletre való bevételezéseket az idősor fölötti függőleges nyilak jelölik.
-   A készletről való kiadásokat az idősor alatti függőleges nyilak jelölik.
-   Minden függőleges nyíl alatt vagy fölött a készlettranzakció értéke van megadva Quantity@Unitprice formátumban.
-   Ha zárójelbe van téve egy készlettranzakció értéke, akkor az arra utal, hogy a készlettranzakció fizikailag van feladva a készletre.
-   Ha nincs zárójelbe téve egy készlettranzakció értéke, akkor az arra utal, hogy a készlettranzakció pénzügyileg van feladva a készletre.
-   Minden új bevételezési és kiadási tranzakciót egy új címke jelöl.
-   Mindegyik függőleges nyíl egy sorszámozott azonosítóval van ellátva, például *1a*. Az azonosítók a készlettranzakciók feladásának időbeli sorrendjét jelölik.
-   A készletzárásokat egy piros színű, szaggatott függőleges vonal és a Készletzárás felirat jelöli.
-   A készletzárás által végrehajtott elszámolásokat pontozott piros nyilak jelölik, amelyek átlósan haladnak egy bevételezéstől egy kiadás felé.

## <a name="weighted-average-summarized-settlement-without-the-include-physical-value-option"></a>Súlyozott átlagú összesített kiegyenlítés a tényleges érték figyelembevétele nélkül
A súlyozott átlag kiegyenlítés, amely azon az elven alapul, hogy a minden, a záró időszakban szereplő bevételezés egy új készletmozgási tranzakcióban összegződik, amelynek Súlyozott átlagú készletzárás a neve. A nap bevételezéseit az újonnan létrehozott készletmozgási tranzakcióval szemben számolja el a program. A nap minden kiadását az új készletmozgási tranzakció bevételezésével szemben számolja el a program. Ha pozitív a tényleges készlet a készletzárás után, akkor ezt a tényleges készletet és a készlet értékét összegzi az új készletmozgási tranzakció (bevételezés). Ha negatív a készlet a készletzárás után, a tényleges készlet és a készletérték a nem teljesen elszámolt egyes kiadások összege. Az alábbi helyzetben több pénzügyi bevételezést és egy kiadást adtak fel. A rendszer létrehozza és feladja az összesített készletmozgási tranzakciót, valamint az adott napra vonatkozó összes bevételezést és az előző napok aktuális készletét elszámolja az összesített készletmozgási kiadási tranzakcióval szemben. Az adott nap összes kiadását az összesített készletmozgási bevételezési tranzakcióval szemben számolja el. A súlyozott átlaggal számított önköltségi ár 15,00 USD lesz. A kiadást eredetileg 14,67 USD becsült önköltségi árral közzétéve. A kiadási tranzakción 0,33 USD értékű negatív korrekció történik. A készletzárás időpontjában a tényleges készlet mennyisége 3 darab, értéke összesen 45,00 USD. Az alábbi ábra a következő tranzakciókat mutatja be:
-   1a. Fizikai bevételezés készletre, 2 mennyiséggel, egyenként 11 USD áron.
-   1b. Pénzügyi bevételezés készletre, 2 mennyiséggel, egyenként 14,00 USD áron.
-   2a. Fizikai bevételezés készletre, 1 mennyiséggel, egyenként 12,00 USD áron.
-   2b. Pénzügyi bevételezés készletre, 1 mennyiséggel, egyenként 16,00 USD áron.
-   3a. Fizikai készletkiadás, 1 mennyiséggel, 14,67 USD-s egységáron (folyó átlag).
-   3b. Pénzügyi készletkiadás, 1 mennyiséggel, 14,67 USD-s egységáron (folyó átlag).
-   4a. Fizikai bevételezés készletre, 1 mennyiséggel, egyenként 14,00 USD áron.
-   4b. Pénzügyi bevételezés készletre, 1 mennyiséggel, egyenként 16,00 USD áron.
-   5. Készletzárást hajtanak végre.
-   6a. A program létrehoz egy „Súlyozott átlagú készletzárási tranzakció” típusú pénzügyi kiadást, amely összegzi a pénzügyi készletkiadások kiegyenlítését.
-   6b. A program létrehoz egy „Súlyozott átlagú készletzárási tranzakció” pénzügyi bevételezést az 5a. tétel ellentételezéseként.

A következő diagram bemutatja a tranzakciósorozatot, és a súlyozott átlag készletmodell, valamint a Tényleges értékkel együtt beállítás nélkül alkalmazott közvetlen kiegyenlítési elv hatását a folyamatra. ![Súlyozott átlagos összegző elszámolás a tényleges érték nélkül    ](./media/weightedaveragesummarizedsettlementwithoutincludephysicalvalue.gif) Jelmagyarázat
-   A készlettranzakciókat függőleges nyilak jelölik.
-   A készletre való bevételezéseket az idősor fölötti függőleges nyilak jelölik.
-   A készletről való kiadásokat az idősor alatti függőleges nyilak jelölik.
-   Minden függőleges nyíl alatt vagy fölött a készlettranzakció értéke van megadva Quantity@Unitprice formátumban.
-   Ha zárójelbe van téve egy készlettranzakció értéke, akkor az arra utal, hogy a készlettranzakció fizikailag van feladva a készletre.
-   Ha nincs zárójelbe téve egy készlettranzakció értéke, akkor az arra utal, hogy a készlettranzakció pénzügyileg van feladva a készletre.
-   Minden új bevételezési és kiadási tranzakciót egy új címke jelöl.
-   Mindegyik függőleges nyíl egy sorszámozott azonosítóval van ellátva, például *1a*. Az azonosítók a készlettranzakciók feladásának időbeli sorrendjét jelölik.
-   A készletzárásokat egy piros színű, szaggatott függőleges vonal és a Készletzárás felirat jelöli.
-   A készletzárás által végrehajtott elszámolásokat pontozott piros nyilak jelölik, amelyek átlósan haladnak egy bevételezéstől egy kiadás felé.
-   A piros nyilak jelzik azt a bevételezési tranzakciót, amelyet a rendszer által létrehozott kiadási tranzakciókkal szemben elszámol a program.
-   A zöld nyilak jelzik azokat a rendszer által ellentételként generált bevételezési tranzakciókat, amelyekkel szemben az eredetileg feladott kiadási tranzakciót elszámolja a program.

## <a name="weighted-average-direct-settlement-with-the-include-physical-value-option"></a>Súlyozott átlagú közvetlen kiegyenlítés a tényleges érték figyelembevételével
Az Include paraméter fizikai értéke másképp működik a súlyozott átlagú készletmodellel, mint a termék korábbi verzióiban. A Tényleges értékkel együtt a jelölőnégyzetet a Modell cikkcsoportok lapon választhatja ki. Ezután a rendszer fizikailag frissített bevételezéseket használ a becsült önköltségi ár vagy a mozgóátlag kiszámítása közben. A kiadások feladása az időszaknak ezen a becsült önköltségi árán alapul. A készletzárás során csak a pénzügyileg frissített bevételezések számítanak bele a súlyozott átlagba. A súlyozott átlagon alapuló készletmodell alkalmazása esetén tanácsos havonta készletzárást végezni. Ebben a súlyozott átlagon alapuló közvetlen kiegyenlítési példában a készletmodellcsoport magában foglalja a tényleges értéket. Az alábbi ábra a következő tranzakciókat mutatja be:
-   1a. Fizikai bevételezés készletre, 1 mennyiséggel, egyenként 11,00 USD áron.
-   1b. Pénzügyi bevételezés készletre, 1 mennyiséggel, egyenként 10,00 USD áron.
-   2a. Fizikai bevételezés készletre, 1 mennyiséggel, egyenként 15,00 USD áron.
-   3a. Fizikai kiadás a készletből, 1 mennyiséggel, 12,50 USD egységáron (folyó átlagos költség, mely a ténylegesen bevételezett értéket veszi figyelembe).
-   3b. Pénzügyi kiadás a készletből, 1 mennyiséggel, 12,50 USD egységáron (folyó átlagos költség, mely a ténylegesen bevételezett értéket veszi figyelembe).
-   4. Készletzárást hajtanak végre. A készletzárás során a rendszer figyelmen kívül hagy minden olyan készlettranzakciót, amely csak fizikailag ment végbe. A program a közvetlen kiegyenlítési elvet alkalmazza, mivel csak egyetlen pénzügyi bevételezés történt. A készlettranzakcióhoz egy 2,50 USD-s korrekció is feladásra kerül, amely pénzügyileg a készletzárás napján kerül kiadásra. A készletzárást követően a tényleges készlet mennyisége 1, melynek értéke a folyó átlagos önköltségi áron USD 15,00 USD.

A következő diagram bemutatja a tranzakciósorozatot, és a súlyozott átlag készletmodell, valamint a Tényleges értékkel együtt beállítás nélkül alkalmazott közvetlen kiegyenlítési elv hatását a folyamatra. ![Súlyozott átlagos közvetlen elszámolás a tényleges értékkel együtt](./media/weightedaveragedirectsettlementwithincludephysicalvalue.gif) Jelmagyarázat
-   A készlettranzakciókat függőleges nyilak jelölik.
-   A készletre való bevételezéseket az idősor fölötti függőleges nyilak jelölik.
-   A készletről való kiadásokat az idősor alatti függőleges nyilak jelölik.
-   Minden függőleges nyíl alatt vagy fölött a készlettranzakció értéke van megadva Quantity@Unitprice formátumban.
-   Ha zárójelbe van téve egy készlettranzakció értéke, akkor az arra utal, hogy a készlettranzakció fizikailag van feladva a készletre.
-   Ha nincs zárójelbe téve egy készlettranzakció értéke, akkor az arra utal, hogy a készlettranzakció pénzügyileg van feladva a készletre.
-   Minden új bevételezési és kiadási tranzakciót egy új címke jelöl.
-   Mindegyik függőleges nyíl egy sorszámozott azonosítóval van ellátva, például *1a*. Az azonosítók a készlettranzakciók feladásának időbeli sorrendjét jelölik.
-   A készletzárásokat egy piros színű, szaggatott függőleges vonal és a Készletzárás felirat jelöli.
-   A készletzárás által végrehajtott elszámolásokat pontozott piros nyilak jelölik, amelyek átlósan haladnak egy bevételezéstől egy kiadás felé.

## <a name="weighted-average-summarized-settlement-with-the-include-physical-value-option"></a>Súlyozott átlagú összesített kiegyenlítés a tényleges érték figyelembevételével
Az Include fizikai értékparaméter másképp működik a súlyozott átlagú készletmodellel, mint a termék korábbi verzióiban. A Tényleges értékkel együtt a jelölőnégyzetet a Modell cikkcsoportok lapon választhatja ki. Ezután a rendszer fizikailag frissített bevételezéseket használ a becsült önköltségi ár vagy a mozgóátlag kiszámítása közben. A kiadások feladása az időszaknak ezen a becsült önköltségi árán alapul. A készletzárás során a súlyozott átlag számításában csak a pénzügyi bevételezések számítanak. A súlyozott átlagon alapuló készletmodell alkalmazása esetén tanácsos havonta készletzárást végezni. Ebben a súlyozott átlagon alapuló összesített kiegyenlítési példában a készletmodell magában foglalja a tényleges értéket. Az alábbi ábra a következő tranzakciókat mutatja be:
-   1a. Fizikai bevételezés készletre, 2 mennyiséggel, egyenként 11 USD áron.
-   1b. Pénzügyi bevételezés készletre, 2 mennyiséggel, egyenként 14,00 USD áron.
-   2. Fizikai bevételezés készletre, 1 mennyiséggel, egyenként 10.00 USD áron.
-   3a. Fizikai bevételezés készletre, 1 mennyiséggel, egyenként 12.00 USD áron.
-   3b. Pénzügyi bevételezés készletre, 1 mennyiséggel, egyenként 16,00 USD áron.
-   4a. Fizikai kiadás a készletből, 1 mennyiséggel, 13,50 USD egységáron (folyó átlagos költség, mely a ténylegesen bevételezett értéket veszi figyelembe).
-   4b. Pénzügyi kiadás a készletből, 1 mennyiséggel, 13,50 USD egységáron (folyó átlagos költség, mely a ténylegesen bevételezett értéket veszi figyelembe).
-   5a. Fizikai bevételezés készletre, 1 mennyiséggel, egyenként 14.00 USD áron.
-   5b. Pénzügyi bevételezés készletre, 1 mennyiséggel, egyenként 16,00 USD áron.
-   6. Készletzárást hajtanak végre. A készletzárás során a rendszer figyelmen kívül hagy minden olyan készlettranzakciót, amely csak fizikailag ment végbe. A program az összesített kiegyenlítési elvet alkalmazza, mivel csak egyetlen pénzügyi bevételezés történt. A készlettranzakcióhoz egy 1,50 USD-s korrekció is feladásra kerül, amely pénzügyileg a készletzárás napján kerül kiadásra. A készletzárást követően a tényleges készlet mennyisége 3, melynek értéke a folyó átlagos önköltségi áron darabonként 15,00 USD.
-   7a. A program létrehoz egy „Súlyozott átlagú készletzárási tranzakció” típusú pénzügyi kiadást, amely összegzi a pénzügyi készletkiadások kiegyenlítését.
-   7b. A program létrehoz egy „Súlyozott átlagú készletzárási tranzakció” pénzügyi bevételezést az 5a. tétel ellentételezéseként.

A következő diagram bemutatja a tranzakciósorozatot, és a súlyozott átlag készletmodell, valamint a Tényleges értékkel együtt beállítás nélkül alkalmazott közvetlen kiegyenlítési elv hatását a folyamatra. ![Súlyozott átlagos összegző elszámolás a tényleges értékkel együtt](./media/weightedaveragesummarizedsettlementwithincludephysicalvalue.gif) Jelmagyarázat
-   A készlettranzakciókat függőleges nyilak jelölik.
-   A készletre való bevételezéseket az idősor fölötti függőleges nyilak jelölik.
-   A készletről való kiadásokat az idősor alatti függőleges nyilak jelölik.
-   Minden függőleges nyíl alatt vagy fölött a készlettranzakció értéke van megadva Quantity@Unitprice formátumban.
-   Ha zárójelbe van téve egy készlettranzakció értéke, akkor az arra utal, hogy a készlettranzakció fizikailag van feladva a készletre.
-   Ha nincs zárójelbe téve egy készlettranzakció értéke, akkor az arra utal, hogy a készlettranzakció pénzügyileg van feladva a készletre.
-   Minden új bevételezési és kiadási tranzakciót egy új címke jelöl.
-   Mindegyik függőleges nyíl egy sorszámozott azonosítóval van ellátva, például 1a. Az azonosítók a készlettranzakciók feladásának időbeli sorrendjét jelölik.
-   A készletzárásokat egy piros színű, szaggatott függőleges vonal és a Készletzárás felirat jelöli.
-   A készletzárás által végrehajtott elszámolásokat pontozott piros nyilak jelölik, amelyek átlósan haladnak egy bevételezéstől egy kiadás felé.
-   A piros nyilak jelzik azt a bevételezési tranzakciót, amelyet a rendszer által létrehozott kiadási tranzakciókkal szemben elszámol a program.
-   A zöld nyilak jelzik azokat a rendszer által ellentételként generált bevételezési tranzakciókat, amelyekkel szemben az eredetileg feladott kiadási tranzakciót elszámolja a program.

## <a name="weighted-average-with-marking"></a>Súlyozott átlag jelöléssel
A jelölés egy olyan folyamat, amellyel összekapcsolható egy kiadási tranzakció egy bevételezési tranzakcióval. A jelölés történhet a tranzakciók feladása előtt és után is. A jelölés használható a készlet pontos költségének megállapítására a tranzakció feladásakor vagy a készletzárás végrehajtásakor. Tegyük fel például, hogy az ügyfélszolgálati osztály elfogadott egy sürgős megrendelést egy fontos vevőtől. A rendelés sürgős, tehát többe fog kerülni az ügyfél kérésének kiszolgálása. Azt szeretné, ha a készlet költsége tükröződne az árrésben is (más szóval az eladott áruk beszerzési értékébe, COGS) az adott értékesítési számla esetében. A beszerzési rendelés feladásakor a készlet bevételezése 120,00 USD értéken történik. A beszerzési rendelési dokumentum meg van jelölve a beszerzési rendelésben, mielőtt a szállítólevelet vagy a számlát feladják. Az ELÁBÉ ekkor 120,00 USD lesz, az aktuális cikk mozgóátlaga helyett. Ha még a jelölés előtt feladják a csomagjegyzéket vagy a számlát, a feladott ELÁBÉ megfelel a beszerzési ár mozgóátlagának. A két tranzakció még a készletzárás végrehajtása előtt is összekapcsolható egymással. Például egy bevételezési tranzakció egy kiadási tranzakcióhoz van megjelölve. Ebben az esetben , a cikk cikkmodellcsoportjában meghatározott értékelési mód nincs figyelembe véve, és a rendszer ezeket a tranzakciókat egymással szemben egyenlíti ki. Kiadási tranzakciót a tranzakció feladása előtt jelölhet hozzá egy nyugtához. Ezt megteheti egy értékesítési rendelés sorából az Értékesítési rendelés részletei oldalon. A nyitott bevételezési tranzakciókat megtekintheti Jelölés oldalon. Kiadási tranzakciót a tranzakció feladása után jelölhet hozzá egy nyugtához. Egyeztethet vagy megjelölhet egy kiadási tranzakciót egy nyílt nyugtájú tranzakcióhoz egy leltárazott cikk esetén, feladott készlethelyesbítési naplósorból. Az alábbi ábra a következő tranzakciókat mutatja be:
-   1a. Fizikai bevételezés készletre, 1 mennyiséggel, 10,00 USD áron.
-   1b. Pénzügyi bevételezés készletre, 1 mennyiséggel, 10,00 USD áron.
-   2a. Fizikai bevételezés készletre, 1 mennyiséggel, 20,00 USD áron.
-   2b. Pénzügyi bevételezés készletre, 1 mennyiséggel, 20,00 USD áron.
-   3a. Fizikai bevételezés készletre, 1 mennyiséggel, 25,00 USD áron.
-   4a. Fizikai bevételezés készletre, 1 mennyiséggel, 30,00 USD áron.
-   4b. Pénzügyi bevételezés készletre, 1 mennyiséggel, 30,00 USD áron.
-   5a. Pénzügyi kiadás készletből, 1 mennyiséggel, 21,25 USD önköltségi áron (a tényleges és pénzügyi tranzakciók folyó átlaga).
-   5b. Egy 1 mennyiségű pénzügyi készletkiadást jelöléssel összekötnek a 2b bevételezéssel a tranzakció feladása előtt. Ezt a tranzakciót 20,00 USD-s önköltségi árral adják fel.
-   6a. Fizikai kiadás készletről, 1 mennyiséggel, 21,25 USD áron.
-   7. Készletzárás hajtanak végre. Mivel a pénzügyi tranzakció egy meglévő bevételezéshez tartozik, ezek a tranzakciók egymással szemben lesznek kiegyenlítve, és nincs korrekció.

Az új, mozgóátlagon alapuló önköltségi ár a pénzügyileg és fizikailag frissített tranzakciók átlagának, azaz 27,50 USD összegnek felel meg. A következő diagram a tranzakciók sorozatát, és a súlyozott átlagon alapuló készletmodell és jelölés folyamatra gyakorolt hatását ábrázolja. ![Súlyozott átlag jelöléssel    ](./media/weightedaveragewithmarking.gif) Jelmagyarázat
-   A készlettranzakciókat függőleges nyilak jelölik.
-   A készletre való bevételezéseket az idősor fölötti függőleges nyilak jelölik.
-   A készletről való kiadásokat az idősor alatti függőleges nyilak jelölik.
-   Minden függőleges nyíl alatt vagy fölött a készlettranzakció értéke van megadva Quantity@Unitprice formátumban.
-   Ha zárójelbe van téve egy készlettranzakció értéke, akkor az arra utal, hogy a készlettranzakció fizikailag van feladva a készletre.
-   Ha nincs zárójelbe téve egy készlettranzakció értéke, akkor az arra utal, hogy a készlettranzakció pénzügyileg van feladva a készletre.
-   Minden új bevételezési és kiadási tranzakciót egy új címke jelöl.
-   Mindegyik függőleges nyíl egy sorszámozott azonosítóval van ellátva, például *1a*. Az azonosítók a készlettranzakciók feladásának időbeli sorrendjét jelölik.
-   A készletzárásokat egy piros színű, szaggatott függőleges vonal és a Készletzárás felirat jelöli.
-   A készletzárás által végrehajtott elszámolásokat pontozott piros nyilak jelölik, amelyek átlósan haladnak egy bevételezéstől egy kiadás felé.




