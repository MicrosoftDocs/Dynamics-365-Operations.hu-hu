---
title: Súlyozott átlag tényleges értékkel és jelöléssel
description: A súlyozott átlag olyan készletmodell, amely a súlyozott átlag elven alapul, ahol a készletből történő kiadások értékét a készletzárási időszakban a készletbe bevételezett cikkek átlagos értéke, valamint az előző időszakban meglévő tényleges készlet határozza meg.
author: AndersGirke
ms.date: 02/21/2022
ms.topic: article
ms.search.form: InventJournalLossProfit, InventMarking, InventModelGroup, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 65501
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6c124716b70be837573506a738ef2034397f2bda
ms.sourcegitcommit: addae271ddfc5a8b0721c23337f69916153db4cd
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/21/2022
ms.locfileid: "8330226"
---
# <a name="weighted-average-with-physical-value-and-marking"></a>Súlyozott átlag tényleges értékkel és jelöléssel

[!include [banner](../includes/banner.md)]

A súlyozott átlag olyan készletmodell, amely az egyes összetevők (cikktranzakciók) fontosságot (mennyiséget) tükröző tényezővel (önköltségi ár) való megszorzásán alapul. Más szóval a súlyozott átlag olyan készletmodell, amely az időszakban kapott összes készlet átlagos értéke, valamint az előző időszakban kapott aktuális készlet alapján hozzárendeli a kiadási tranzakciók költségét.

Ha a súlyozott átlagon és a készletmodellen futtat készletzárást, akkor kétféleképpen lehet kiegyenlítést létrehozni. Általában minden bevételezés egy virtuális kiadásval van kiegyenlítve, amely a teljes bevételezési mennyiséget és értéket tartalmazza. Ehhez a virtuális kiadáshoz tartozik egy virtuális bevételezés is, amelyből a kiadások egyenlíthetők ki. Ily módon minden kiadás ugyanazzal a költséggel történik. A virtuális kiadás és bevételezés virtuális transzfernek látható, *amelynek neve a súlyozott átlagú készletzárási transzfer*. Ezt a kiegyenlítési módot súlyozott *átlagú összesített kiegyenlítésnek nevezik*. Ha csak egy bevételezés van, akkor minden kiadást ebből egyenlítenek ki, tehát nem jön létre virtuális transzfer. Ezt a kiegyenlítési módszert nevezik közvetlen *elszámolásnak*. A készletzárás után aktuális készleteket az előző időszak súlyozott átlaga alapján számítja ki a program, és a következő időszakban részt fog venni a súlyozott átlag számításában.

A súlyozott átlag elv felülbírálható a készlettranzakciók megjelölésével, így egy adott cikkbevételezést egy adott kiadással szemben lehet kiegyenlíteni. Időszaki készletzárásra van szükség, ha a súlyozott átlag készletmodell segítségével kiegyenlítéseket lehet létrehozni, és a súlyozott átlag elv szerint módosítani lehet a problémák értékét. Amíg nem futtatja a készletzárási folyamatot, a kiadási tranzakciók értékének a tényleges és pénzügyi frissítések esetén a mozgóátlagon történik a program. Ha nem használ jelölést, akkor a rendszer a fizikai vagy pénzügyi frissítéskor kiszámítja a mozgóátlagot.

A készlet súlyozott átlaga költségszámítási módszer számítása a következő képlettel történik:

- Súlyozott átlag = (\[Q1 × P1\] + \[Q2 × P2\] + \[Q *n* × P *n*\]) ÷ (Q1 + Q2 + Q *n*)

Q = a tranzakció mennyisége  
P = a tranzakció ára

Az elszámolások készletzárási feladások, amelyek módosítják a kiadásokat a záró dátumnak megfelelő helyes súlyozott átlagra. A következő példák azt mutatják be, hogy milyen hatást fejt ki a súlyozott átlag öt eltérő konfigurációban:

- Súlyozott átlagú közvetlen kiegyenlítés a **Tényleges értékkel nélkül**
- Súlyozott átlagú összesített kiegyenlítés a **Tényleges értékkel való befog foglalva beállítás** nélkül
- Súlyozott átlagú közvetlen kiegyenlítés a **Tényleges értékkel együtt** beállítással
- Súlyozott átlagú összesített kiegyenlítés a Tényleges **értékkel együtt** beállítással
- Súlyozott átlag jelöléssel

## <a name="weighted-average-direct-settlement-without-include-physical-value"></a>Súlyozott átlagú közvetlen kiegyenlítés a tényleges érték figyelembevétele nélkül

A közvetlen kiegyenlítési elv további készlettranzakciók létrehozása nélkül hozza létre a közvetlen kiegyenlítést a bevételezések és a problémák között. A rendszer a következő helyzetekben használja ezt a közvetlen kiegyenlítési elvet:

- Az időszak során egy bevételezést és egy vagy több problémát feladtak.
- Az időszakban csak a problémákat adva fel, és a készletben egy korábbi zárásból származó, aktuális készleten lévő cikkek vannak.

Ebben a példában **a Kiadott** **termék** cikkmodellcsoportja jelölőnégyzetből törölve van a Tényleges értékkel való betétel. A következő ábrán ezek a tranzakciók láthatók:

- 1a. Fizikai bevételezés készletre, 10 mennyiséggel, 10,00 USD áron.
- 1b. Pénzügyi bevételezés készletre, 10 mennyiséggel, 10,00 USD áron.
- 2a. Fizikai bevételezés készletre, 10 mennyiséggel, 20,00 USD áron.
- 3a. Fizikai kiadás készletről, 1 mennyiséggel, USD 10.00 önköltségi áron (a pénzügyileg feladott tranzakciók mozgóátlaga).
- 3b. Pénzügyi kiadás készletről, 1 mennyiséggel, USD 10.00 önköltségi áron (a pénzügyileg feladott tranzakciók mozgóátlaga).
- 4a. Fizikai kiadás készletről, 1 mennyiséggel, USD 10.00 egységenként (a pénzügyileg feladott tranzakciók mozgóátlaga).
- 4b. Pénzügyi kiadás készletről, 1 mennyiséggel, USD 10.00 egységenként (a pénzügyileg feladott tranzakciók mozgóátlaga).
- 5a. Fizikai kiadás készletről, 1 mennyiséggel, USD 10.00 egységenként (a pénzügyileg feladott tranzakciók mozgóátlaga).
- 6\. Készletzárást hajtanak végre. A súlyozott átlagon alapuló rendszer a közvetlen kiegyenlítési módszert használja, mivel az időszakban csak egy bevételezés van pénzügyileg frissítve. Ebben a példában az egyik kiegyenlítés 1b és 3b, egy másik pedig 1b és 4b között jön létre. Nem történt módosítás, mert a mozgóátlag megegyezik a súlyozott átlaggel.

A következő diagram bemutatja **a** tranzakciósorozatot, és a súlyozott átlag készletmodell, valamint a Tényleges értékkel együtt beállítás nélkül történő közvetlen kiegyenlítési elv hatását a folyamatra.

![Súlyozott alapértelmezett érték ( DS) a tényleges érték nélkül.](media/weighted-average-direct-settlement-without-include-physical-value.png)

**Jelmagyarázat**

- A készlettranzakciókat függőleges nyilak jelölik.
- A fizikai tranzakciókat rövidebb világosszürke nyilak ábrázolják.
- A pénzügyi tranzakciókat hosszabb fekete nyilak jelzik.
- A készletre való bevételezéseket a tengely fölötti függőleges nyilak jelzik.
- A készletről való problémákat a tengely alatti függőleges nyilak jelzik.
- Minden új bevételezési és kiadási tranzakciót egy új címke jelöl.
- Mindegyik függőleges nyíl egy sorszámozott azonosítóval van ellátva, például *1a*. Az azonosítók a készlettranzakciók feladásának időbeli sorrendjét jelölik.
- A diagram minden dátumát egy vékony fekete függőleges vonal választja el egymástól. A dátum a diagram alján látható.
- A készletzárásokat egy piros színű, szaggatott függőleges vonal ábrázolja.
- A készletzárás által végrehajtott elszámolásokat szaggatott piros nyilak jelölik, amelyek átlósan haladnak egy bevételezéstől egy kiadás felé.

## <a name="weighted-average-summarized-settlement-without-the-include-physical-value-option"></a>Súlyozott átlagú összesített kiegyenlítés a tényleges érték figyelembevétele nélkül

Ha egy időszakban több bevételezés van, akkor a súlyozott átlag az összesített kiegyenlítési elvet használja, ahol a program a *záró időszak minden bevételezését egy súlyozott átlagú készletzárásnak nevezett tranzakcióba összegzi*. Az időszak minden bevételezése az újonnan létrehozott készlettranzakció kiadásának ellenében lesz kiegyenlítve. Az időszak minden bevételezése az új készlettranzakció bevételezésével szemben lesz kiegyenlítve. Ha a készletzárás után is marad aktuális készletérték, a súlyozott átlagú készletzárási tranzakciók bevételezési tranzakciója az aktuális készletértéket is tartalmazza.

A következő ábra a következő tranzakciókat mutatja be:

- 1a. Fizikai bevételezés készletre, 1 mennyiséggel, 10,00 USD áron.
- 1b. Pénzügyi bevételezés készletre, 1 mennyiséggel, 10,00 USD áron.
- 2a. Fizikai bevételezés készletre, 1 mennyiséggel, 20,00 USD áron.
- 2b. Pénzügyi bevételezés készletre, 1 mennyiséggel, 22,00 USD áron.
- 3a. Fizikai kiadás készletről, 1 mennyiséggel, USD 16.00 önköltségi áron (a pénzügyileg feladott tranzakciók mozgóátlaga).
- 3b. Pénzügyi kiadás készletről, 1 mennyiséggel, USD 16.00 önköltségi áron (a pénzügyileg feladott tranzakciók mozgóátlaga).
- 4a. Fizikai bevételezés készletre, 1 mennyiséggel, 25,00 USD áron.
- 5a. Fizikai bevételezés készletre, 1 mennyiséggel, 30,00 USD áron.
- 5b. Pénzügyi bevételezés készletre, 1 mennyiséggel, 30,00 USD áron.
- 6a. Fizikai kiadás készletről, 1 mennyiséggel, USD 23.00 önköltségi áron (a pénzügyileg feladott tranzakciók mozgóátlaga).
- 7\. Készletzárást hajtanak végre.
- 7a. Súlyozott átlagú készletzárási tranzakció pénzügyi kiadás jön létre az összes pénzügyi készletbevételezés kiegyenlítésének összegzése érdekében.
  - Az 1b. tranzakciót 1 mennyiséggel egyenlítik ki, a kiegyenlített összeg 1 USD 10.00.
  - A 2b. tranzakciót 1 mennyiséggel egyenlítik ki, a kiegyenlített összeg 1 USD 22.00.
  - Az 5b. tranzakciót 1 mennyiséggel egyenlítik ki, a kiegyenlített összeg pedig USD 30.00.
  - 7a. tranzakció A (USD 62.00) mennyiség 3 mennyiséghez jön USD 62.00. Ez a tranzakció kiegyenlíti az időszakban pénzügyileg frissített három bevételezési tranzakció összegét.
- 7b. Súlyozott átlagú készletzárási tranzakció pénzügyi bevételezése jön létre a pénzügyileg feladott problémák ellentételeként.
  - A 3b. tranzakciót 1 mennyiséggel egyenlítik ki, 1 összeggel, USD 20.67. Ez a tranzakció USD 4.67 úgy módosul, hogy az eredeti USD 16.00 értékét 20,67-re állítsa, amely az időszakra vonatkozóan a pénzügyileg feladott tranzakciók súlyozott átlaga.
  - 7b. tranzakció 1 mennyiségre jött létre, 3b ellenszámlára USD 20.67 kiegyenlített összeggel. Ez a tranzakció kiegyenlíti az időszakban pénzügyileg frissített egyetlen kiadási tranzakció összegét.

A következő diagram bemutatja **a** tranzakciósorozatot, és a súlyozott átlag készletmodell, valamint a Tényleges értékkel együtt beállítás nélkül az összesített kiegyenlítési elv hatását a folyamatra.

![Súlyozott átlagos SS a tényleges érték nélkül.](media/weighted-average-summarized-settlement-without-include-physical-value.png)

**Jelmagyarázat**

- A készlettranzakciókat függőleges nyilak jelölik.
- A fizikai tranzakciókat rövidebb világosszürke nyilak ábrázolják.
- A pénzügyi tranzakciókat hosszabb fekete nyilak jelzik.
- A készletre való bevételezéseket a tengely fölötti függőleges nyilak jelzik.
- A készletről való problémákat a tengely alatti függőleges nyilak jelzik.
- Minden új bevételezési és kiadási tranzakciót egy új címke jelöl.
- Mindegyik függőleges nyíl egy sorszámozott azonosítóval van ellátva, például *1a*. Az azonosítók a készlettranzakciók feladásának időbeli sorrendjét jelölik.
- A diagram minden dátumát egy vékony fekete függőleges vonal választja el egymástól. A dátum a diagram alján látható.
- A készletzárásokat egy piros színű, szaggatott függőleges vonal ábrázolja.
- A készletzárás által végrehajtott elszámolásokat szaggatott piros nyilak jelölik, amelyek átlósan haladnak egy bevételezéstől egy kiadás felé.

## <a name="weighted-average-direct-settlement-with-the-include-physical-value-option"></a>Súlyozott átlagú közvetlen kiegyenlítés a tényleges érték figyelembevételével

A Tényleges **értékkel együtt** paraméter másképp működik a súlyozott átlagú készletmodellel, mint a termék korábbi verzióiban. Ha egy **cikk tényleges értékkel** való beszámítása lehetőséget választja a **Cikkmodellcsoport** képernyőn, a rendszer a ténylegesen frissített bevételezéseket használja a becsült kiadási önköltségi ár vagy a mozgóátlag számításakor. A kiadások feladása az időszaknak ezen a becsült önköltségi árán alapul. A készletzárás során csak a pénzügyileg frissített bevételezések számítanak bele a súlyozott átlagba.

A következő ábra a következő tranzakciókat mutatja be:

- 1a. Fizikai bevételezés készletre, 10 mennyiséggel, 10,00 USD áron.
- 1b. Pénzügyi bevételezés készletre, 10 mennyiséggel, 10,00 USD áron.
- 2a. Fizikai bevételezés készletre, 10 mennyiséggel, 20,00 USD áron.
- 3a. Fizikai kiadás készletről, 1 mennyiséggel, USD 15.00 önköltségi áron (a ténylegesen és pénzügyileg feladott tranzakciók mozgóátlaga).
- 3b. Pénzügyi kiadás készletről, 1 mennyiséggel, USD 15.00 önköltségi áron (a ténylegesen és pénzügyileg feladott tranzakciók mozgóátlaga).
- 4a. Fizikai kiadás készletről, 1 mennyiséggel, USD 15.00 egységenként (a ténylegesen és pénzügyileg feladott tranzakciók mozgóátlaga).
- 4b. Pénzügyi kiadás készletről, 1 mennyiséggel, USD 15.00 költséggel (a ténylegesen és pénzügyileg feladott tranzakciók mozgóátlaga).
- 5a. Fizikai kiadás készletről, 1 mennyiséggel, USD 15.00 egységenként (a ténylegesen és pénzügyileg feladott tranzakciók mozgóátlaga).
- 6\. Készletzárást hajtanak végre. A súlyozott átlagon alapuló rendszer a közvetlen kiegyenlítési módszert használja, mivel az időszakban csak egy bevételezés van pénzügyileg frissítve. Ebben a példában az egyik kiegyenlítés 1b és 3b, egy másik pedig 1b és 4b között jön létre. A 3b. és a 4b. tranzakciót -5,00 USD-s értékkel korrigálja a USD 10.00.

A következő diagram bemutatja **a** tranzakciósorozatot, és a súlyozott átlag készletmodell, valamint a tényleges értékkel együtt beállítással történő közvetlen kiegyenlítési elv hatását a folyamatra.

![Súlyozott átlagú DS a tényleges értékkel együtt.](media/weighted-average-direct-settlement-with-include-physical-value.png)

**Jelmagyarázat**

- A készlettranzakciókat függőleges nyilak jelölik.
- A fizikai tranzakciókat rövidebb világosszürke nyilak ábrázolják.
- A pénzügyi tranzakciókat hosszabb fekete nyilak jelzik.
- A készletre való bevételezéseket a tengely fölötti függőleges nyilak jelzik.
- A készletről való problémákat a tengely alatti függőleges nyilak jelzik.
- Minden új bevételezési és kiadási tranzakciót egy új címke jelöl.
- Mindegyik függőleges nyíl egy sorszámozott azonosítóval van ellátva, például *1a*. Az azonosítók a készlettranzakciók feladásának időbeli sorrendjét jelölik.
- A diagram minden dátumát egy vékony fekete függőleges vonal választja el egymástól. A dátum a diagram alján látható.
- A készletzárásokat egy piros színű, szaggatott függőleges vonal ábrázolja.
- A készletzárás által végrehajtott elszámolásokat szaggatott piros nyilak jelölik, amelyek átlósan haladnak egy bevételezéstől egy kiadás felé.

## <a name="weighted-average-summarized-settlement-with-the-include-physical-value-option"></a>Súlyozott átlagú összesített kiegyenlítés a tényleges érték figyelembevételével

A **Tényleges értékkel együtt paraméter** másképp működik a súlyozott átlaggal, mint a korábbi verziókban. Jelölje be egy **cikk tényleges értékkel való** betételét a **Cikkmodellcsoport lapon**. Ezután a rendszer fizikailag frissített bevételezéseket használ a becsült önköltségi ár vagy a mozgóátlag kiszámítása közben. A kiadások feladása az időszaknak ezen a becsült önköltségi árán alapul. A készletzárás során csak a pénzügyileg frissített bevételezések számítanak bele a súlyozott átlagba. A súlyozott átlagon alapuló készletmodell alkalmazása esetén tanácsos havonta készletzárást végezni. Ebben a súlyozott átlagon alapuló összesített kiegyenlítési példában a készletmodell magában foglalja a tényleges értéket.

A következő ábra a következő tranzakciókat mutatja be:

- 1a. Fizikai bevételezés készletre, 1 mennyiséggel, 10,00 USD áron.
- 1b. Pénzügyi bevételezés készletre, 1 mennyiséggel, 10,00 USD áron.
- 2a. Fizikai bevételezés készletre, 1 mennyiséggel, 20,00 USD áron.
- 2b. Pénzügyi bevételezés készletre, 1 mennyiséggel, 22,00 USD áron.
- 3a. Fizikai kiadás készletről, 1 mennyiséggel, USD 16.00 önköltségi áron (a ténylegesen és pénzügyileg feladott tranzakciók mozgóátlaga).
- 3b. Pénzügyi kiadás készletről, 1 mennyiséggel, USD 16.00 önköltségi áron (a ténylegesen és pénzügyileg feladott tranzakciók mozgóátlaga).
- 4a. Fizikai bevételezés készletre, 1 mennyiséggel, 25,00 USD áron.
- 5a. Fizikai bevételezés készletre, 1 mennyiséggel, 30,00 USD áron.
- 5b. Pénzügyi bevételezés készletre, 1 mennyiséggel, 30,00 USD áron.
- 6a. Fizikai kiadás készletről, 1 mennyiséggel, USD 23.67 önköltségi áron (a ténylegesen és pénzügyileg feladott tranzakciók mozgóátlaga).
- 7\. Készletzárást hajtanak végre.
- 7a. Súlyozott átlagú készletzárási tranzakció pénzügyi kiadás jön létre az összes pénzügyi készletbevételezés kiegyenlítésének összegzése érdekében.
  - Az 1b. tranzakciót 1 mennyiséggel egyenlítik ki, a kiegyenlített összeg 1 USD 10.00.
  - A 2b. tranzakciót 1 mennyiséggel egyenlítik ki, a kiegyenlített összeg 1 USD 22.00.
  - Az 5b. tranzakciót 1 mennyiséggel egyenlítik ki, a kiegyenlített összeg pedig USD 30.00.
  - 7a. tranzakció A (USD 62.00) mennyiség 3 mennyiséghez jön USD 62.00.  
- 7b. Súlyozott átlagú készletzárási tranzakció pénzügyi bevételezése jön létre a pénzügyileg lezárt kiadási tranzakciók ellentételeként.
  - A 3b. tranzakciót 1 mennyiséggel egyenlítik ki, 1 összeggel, USD 20.67. Ez a tranzakció USD 4.67 úgy módosul, hogy az eredeti USD 16.00 értékét 20,67-re állítsa, amely az időszakra vonatkozóan a pénzügyileg feladott tranzakciók súlyozott átlaga.
  - 7b. tranzakció 1 mennyiségre jött létre, 3b ellenszámlára USD 20.67 kiegyenlített összeggel.

A következő diagram bemutatja **a** tranzakciósorozatot, és a súlyozott átlag készletmodell, valamint a Tényleges értékkel együtt beállítás nélkül az összesített kiegyenlítési elv hatását a folyamatra.

![Súlyozott alapértelmezett érték (SS) a tényleges értékkel együtt](media/weighted-average-summarized-settlement-with-include-physical-value.png)

**Jelmagyarázat**

- A készlettranzakciókat függőleges nyilak jelölik.
- A fizikai tranzakciókat rövidebb világosszürke nyilak ábrázolják.
- A pénzügyi tranzakciókat hosszabb fekete nyilak jelzik.
- A készletre való bevételezéseket a tengely fölötti függőleges nyilak jelzik.
- A készletről való problémákat a tengely alatti függőleges nyilak jelzik.
- Minden új bevételezési és kiadási tranzakciót egy új címke jelöl.
- Mindegyik függőleges nyíl egy sorszámozott azonosítóval van ellátva, például *1a*. Az azonosítók a készlettranzakciók feladásának időbeli sorrendjét jelölik.
- A diagram minden dátumát egy vékony fekete függőleges vonal választja el egymástól. A dátum a diagram alján látható.
- A készletzárásokat egy piros színű, szaggatott függőleges vonal ábrázolja.
- A készletzárás által végrehajtott elszámolásokat szaggatott piros nyilak jelölik, amelyek átlósan haladnak egy bevételezéstől egy kiadás felé.

## <a name="weighted-average-with-marking"></a>Súlyozott átlag jelöléssel

A jelölés egy olyan folyamat, amellyel összekapcsolható egy kiadási tranzakció egy bevételezési tranzakcióval. A jelölés történhet a tranzakciók feladása előtt és után is. A jelölés használható a készlet pontos költségének megállapítására a tranzakció feladásakor vagy a készletzárás végrehajtásakor.

Tegyük fel például, hogy az ügyfélszolgálati osztály elfogadott egy sürgős megrendelést egy fontos vevőtől. A rendelés sürgős, ezért a vevő kérésének kiszolgálása érdekében többet kell fizetni. Azt szeretné, ha a készlet költsége tükröződne az árrésben is (más szóval az eladott áruk beszerzési értékébe, COGS) az adott értékesítési számla esetében.

A beszerzési rendelés feladásakor a készlet bevételezése 120,00 USD értéken történik. A beszerzési rendelési dokumentum meg van jelölve a beszerzési rendelésben, mielőtt a szállítólevelet vagy a számlát feladják. Az ELÁBÉ ekkor 120,00 USD lesz, az aktuális cikk mozgóátlaga helyett. Ha még a jelölés előtt feladják a csomagjegyzéket vagy a számlát, a feladott ELÁBÉ megfelel a beszerzési ár mozgóátlagának.

A két tranzakció még a készletzárás végrehajtása előtt is összekapcsolható egymással.

Például egy bevételezési tranzakció egy kiadási tranzakcióhoz van megjelölve. Ezt követően a program figyelmen kívül hagyja a cikk cikkmodellcsoportja számára kiválasztott értékelési módszert, és a rendszer egymással egyenlíti ki ezeket a tranzakciókat.

Kiadási tranzakciót a tranzakció feladása előtt jelölhet hozzá egy nyugtához. Ezt megteheti egy értékesítési rendelés sorából az **Értékesítési rendelés** oldalon. A nyitott bevételezési tranzakciók a Jelölés lapon **jelennek** meg.

Kiadási tranzakciót a tranzakció feladása után jelölhet hozzá egy nyugtához. Egyeztethet vagy megjelölhet egy kiadási tranzakciót egy nyílt nyugtájú tranzakcióhoz egy leltárazott cikk esetén, feladott készlethelyesbítési naplósorból.

A következő ábra a következő tranzakciókat mutatja be:

- 1a. Fizikai bevételezés készletre, 1 mennyiséggel, 10,00 USD áron.
- 1b. Pénzügyi bevételezés készletre, 1 mennyiséggel, 10,00 USD áron.
- 2a. Fizikai bevételezés készletre, 1 mennyiséggel, 20,00 USD áron.
- 2b. Pénzügyi bevételezés készletre, 1 mennyiséggel, 22,00 USD áron.
- 3a. Fizikai kiadás készletről, 1 mennyiséggel, USD 16.00 önköltségi áron (a pénzügyileg feladott tranzakciók mozgóátlaga).
- 3b. Pénzügyi kiadás készletről, 1 mennyiséggel, USD 16.00 önköltségi áron (a pénzügyileg feladott tranzakciók mozgóátlaga).
- 3c. A 3b pénzügyi készletről való kiadás a 2b pénzügyi készlet kiadására van bejelölve.
- 4a. Fizikai bevételezés készletre, 1 mennyiséggel, 25,00 USD áron.
- 5a. Fizikai bevételezés készletre, 1 mennyiséggel, 30,00 USD áron.
- 5b. Pénzügyi bevételezés készletre, 1 mennyiséggel, 30,00 USD áron.
- 6a. Fizikai kiadás készletről, 1 mennyiséggel, USD 23.00 önköltségi áron (a pénzügyileg feladott tranzakciók mozgóátlaga).
- 7\. Készletzárást hajtanak végre. A súlyozott átlag módszert használó jelölési elv alapján a megjelölt tranzakciókat egymással szemben egyenlítik ki. Ebben a példában a 3b értékét 2b-t egyenlít ki, és a USD 6.00 feladása 3b-re, hogy az érték 3b értékre USD 22.00. Ebben a példában nem kerül sor további kiegyenlítésre, mert a lezárás csak a pénzügyileg frissített tranzakciókhoz hoz létre kiegyenlítéseket.

A következő diagram bemutatja a tranzakciósorozatot, és a súlyozott átlag készletmodell és a jelölés hatását a folyamatra.

![Súlyozott átlag jelöléssel.](media/weighted-average-with-marking.png)

**Jelmagyarázat**

- A készlettranzakciókat függőleges nyilak jelölik.
- A fizikai tranzakciókat rövidebb világosszürke nyilak ábrázolják.
- A pénzügyi tranzakciókat hosszabb fekete nyilak jelzik.
- A készletre való bevételezéseket a tengely fölötti függőleges nyilak jelzik.
- A készletről való problémákat a tengely alatti függőleges nyilak jelzik.
- Minden új bevételezési és kiadási tranzakciót egy új címke jelöl.
- Mindegyik függőleges nyíl egy sorszámozott azonosítóval van ellátva, például *1a*. Az azonosítók a készlettranzakciók feladásának időbeli sorrendjét jelölik.
- A diagram minden dátumát egy vékony fekete függőleges vonal választja el egymástól. A dátum a diagram alján látható.
- A készletzárásokat egy piros színű, szaggatott függőleges vonal ábrázolja.
- A készletzárás által végrehajtott elszámolásokat szaggatott piros nyilak jelölik, amelyek átlósan haladnak egy bevételezéstől egy kiadás felé.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
