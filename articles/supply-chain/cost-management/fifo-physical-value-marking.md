---
title: FIFO tényleges értékkel és jelöléssel
description: A FIFO-elv (First in, First out) egy készletmodell, amelyben az elsőként bevételezett cikkek kerülnek először kiadásra. A készletből történő pénzügyi kiadások a készlettranzakciók pénzügyi dátuma alapján az első pénzügyi készletbevételezésekkel vannak kiegyenlítve.
author: AndersGirke
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventJournalLossProfit, InventMarking, InventModelGroup, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations, Retail
ms.custom: 54682
ms.assetid: dc0e2855-83a0-41a7-a398-3c7852597d1a
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e237d1e9f9bb83d0fe65556eca07c8757f920664
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/02/2020
ms.locfileid: "3201755"
---
# <a name="fifo-with-physical-value-and-marking"></a>FIFO tényleges értékkel és jelöléssel

[!include [banner](../includes/banner.md)]

A FIFO-elv (First in, First out) egy készletmodell, amelyben az elsőként bevételezett cikkek kerülnek először kiadásra. A készletből történő pénzügyi kiadások a készlettranzakciók pénzügyi dátuma alapján az első pénzügyi készletbevételezésekkel vannak kiegyenlítve. 

FIFO módszer használata esetén nem kell használni a FIFO-szabályt. Ehelyett egyes készlettranzakciók megjelölésével meghatározhatja, hogy egy adott bevételezés egy meghatározott kiadással legyen kiegyenlítve. A FIFO-elvű készletmodell használata esetén javasoljuk, hogy időszakonként tartson készletzárást. Az alábbi példák bemutatják a FIFO-elv alkalmazásának hatását három különböző konfiguráción:

-   FIFO a **Tényleges értékkel együtt** beállítás nélkül
-   FIFO a **Tényleges értékkel együtt** beállítással
-   FIFO jelöléssel

## <a name="fifo-without-the-include-physical-value-option"></a>FIFO a Tényleges értékkel együtt beállítás nélkül
Ebben a példában a cikkmodellcsoport nem tartalmazza a tényleges értéket. A következő ábrán ezek a tranzakciók láthatók:

-   1a. Fizikai bevételezés készletre, 1 mennyiséggel, 10,00 USD áron.
-   1b. Pénzügyi bevételezés készletre, 1 mennyiséggel, 10,00 USD áron.
-   2a. Fizikai bevételezés készletre, 2 mennyiséggel, 10,00 USD áron.
-   2b. Pénzügyi bevételezés készletre, 2 mennyiséggel, 10,00 USD áron.
-   3a. Fizikai bevételezés készletre, 1 mennyiséggel, 25,00 USD áron.
-   4a. Fizikai bevételezés készletre, 1 mennyiséggel, 30,00 USD áron.
-   4b. Pénzügyi bevételezés készletre, 1 mennyiséggel, 30,00 USD áron.
-   5a. Fizikai kiadás készletről, 1 mennyiséggel, 20,00 USD önköltségi áron (a pénzügyileg frissített tranzakciók mozgóátlaga).
-   5b. Pénzügyi kiadás készletről, 1 mennyiséggel, 20,00 USD önköltségi áron (a pénzügyileg frissített tranzakciók mozgóátlaga).
-   6. Készletzárást hajtanak végre. A FIFO-elv szerint az első pénzügyi kiadást az első pénzügyi bevételezéssel kell kiegyenlíteni. A kiadási tranzakción 10,00 USD értékű korrekció történik.

Az önköltség új mozgóátlaga a pénzügyi tranzakciók átlagát tükrözi. A következő ábra bemutatja, milyen hatása van a FIFO készletmodellnek, ha a **Tényleges értékkel együtt** beállítást nincs beállítva. 

![LIFO a tényleges értékkel nélkül](./media/fifowithoutincludephysicalvalue.gif) 

**Jelmagyarázat**

- A készlettranzakciókat függőleges nyilak jelölik.
- A készletre való bevételezéseket az idősor fölötti függőleges nyilak jelölik.
- A készletről való kiadásokat az idősor alatti függőleges nyilak jelölik.
- Minden függőleges nyíl alatt vagy fölött a készlettranzakció értéke van megadva, Quantity@Unitprice formátumban.
- Ha zárójelbe van téve egy készlettranzakció értéke, akkor az arra utal, hogy a készlettranzakció fizikailag van feladva a készletre.
- Ha zárójelbe van téve egy készlettranzakció értéke, akkor az arra utal, hogy a készlettranzakció pénzügyileg van feladva a készletre.
- Minden új bevételezési és kiadási tranzakciót egy új címke jelöl.
- Mindegyik függőleges nyíl egy sorszámozott azonosítóval van ellátva, például *1a*. Az azonosítók a készlettranzakciók feladásának időbeli sorrendjét jelölik.
- A készletzárásokat egy piros színű, szaggatott függőleges vonal és a *Készletzárás* felirat jelöli.
- A készletzárás által végrehajtott elszámolásokat szaggatott piros nyilak jelölik, amelyek átlósan haladnak egy bevételezéstől egy kiadás felé.

## <a name="fifo-with-the-include-physical-value-option"></a>FIFO a Tényleges értékkel együtt beállítással
Ha egy cikkhez be van jelölve a **Tényleges értékkel együtt** jelölőnégyzet a **Cikkmodell-csoport** lapon, a rendszer a fizikai és a pénzügyi bevételezési tranzakciókat egyaránt felhasználja a mozgóátlagon alapuló önköltségi ár kiszámításához. Ahol erre lehetőség van, a rendszer a fizikailag frissített kiadási tranzakción is végez korrekciót. Ha a **Tényleges értékkel együtt** jelölőnégyzet nincs bejelölve, a FIFO készletmodellel végrehajtott készletzárás csak a pénzügyileg frissített tranzakciókkal szemben végez teljesítést. A következő ábrán ezek a tranzakciók láthatók:

-   1a. Fizikai bevételezés készletre, 1 mennyiséggel, 10,00 USD áron.
-   1b. Pénzügyi bevételezés készletre, 1 mennyiséggel, 10,00 USD áron.
-   2a. Fizikai bevételezés készletre, 1 mennyiséggel, 20,00 USD áron.
-   2b. Pénzügyi bevételezés készletre, 1 mennyiséggel, 20,00 USD áron.
-   3a. Fizikai bevételezés készletre, 1 mennyiséggel, 25,00 USD áron.
-   4a. Fizikai bevételezés készletre, 1 mennyiséggel, 30,00 USD áron.
-   4b. Pénzügyi bevételezés készletre, 1 mennyiséggel, 30,00 USD áron.
-   5a. Fizikai kiadás készletről, 1 mennyiséggel, 21,25 USD önköltségi áron (a pénzügyileg és fizikailag frissített tranzakciók mozgóátlaga).
-   5b. Pénzügyi kiadás készletről, 1 mennyiséggel, 21,25 USD önköltségi áron (a pénzügyileg és fizikailag frissített tranzakciók mozgóátlaga).
-   6a. Fizikai kiadás készletről, 1 mennyiséggel, 21,25 USD áron.
-   7. Készletzárást hajtanak végre. A FIFO-módszer szerint az első pénzügyi tranzakciót az első bevételezéssel kell korrigálni vagy kiegyenlíteni, akár pénzügyi, akár fizikai az bevételezési tranzakció.

Az 5b jelű tranzakciót az 1b jelű bevételezési tranzakció egyenlíti ki. Erre a kiadási tranzakcióra -11,25 USD értékű korrekciót alkalmaz a program. Az új, mozgóátlagon alapuló önköltségi ár a pénzügyileg és fizikailag frissített tranzakciók átlagának, azaz 27,50 USD összegnek felel meg. A következő ábra bemutatja, milyen hatása van a FIFO készletmodellnek, ha a **Tényleges értékkel együtt** beállítás be van kapcsolva. 

![FIFO a tényleges értékkel együtt](./media/fifowithincludephysicalvalue.gif) 

**Jelmagyarázat**

- A készlettranzakciókat függőleges nyilak jelölik.
- A készletre való bevételezéseket az idősor fölötti függőleges nyilak jelölik.
- A készletről való kiadásokat az idősor alatti függőleges nyilak jelölik.
- Minden függőleges nyíl alatt vagy fölött a készlettranzakció értéke van megadva, Quantity@Unitprice formátumban.
- Ha zárójelbe van téve egy készlettranzakció értéke, akkor az arra utal, hogy a készlettranzakció fizikailag van feladva a készletre.
- Ha zárójelbe van téve egy készlettranzakció értéke, akkor az arra utal, hogy a készlettranzakció pénzügyileg van feladva a készletre.
- Minden új bevételezési és kiadási tranzakciót egy új címke jelöl.
- Mindegyik függőleges nyíl egy sorszámozott azonosítóval van ellátva, például *1a*. Az azonosítók a készlettranzakciók feladásának időbeli sorrendjét jelölik.
- A készletzárásokat egy piros színű, szaggatott függőleges vonal és a *Készletzárás* felirat jelöli.
- A készletzárás által végrehajtott elszámolásokat szaggatott piros nyilak jelölik, amelyek átlósan haladnak egy bevételezéstől egy kiadás felé.

## <a name="fifo-with-marking"></a>FIFO jelöléssel
A jelölés egy olyan folyamat, amellyel összekapcsolható egy kiadási tranzakció egy bevételezési tranzakcióval. A jelölés történhet a tranzakciók feladása előtt és után is. A jelölés használható a készlet pontos költségének megállapítására a tranzakció feladásakor vagy a készletzárás végrehajtásakor. Tegyük fel például, hogy az ügyfélszolgálati osztály elfogadott egy sürgős megrendelést egy fontos vevőtől. Mivel ez a rendelés sürgős, ezért többet kell fizetni az adott cikkért az ügyfél kérésének teljesítése érdekében. Azt szeretné, ha a készlet költsége tükröződne az árrésben is (más szóval az eladott áruk beszerzési értékébe, ELÁBÉ) az adott értékesítési számla esetében. A beszerzési rendelés feladásakor a készlet bevételezése 120,00 USD értéken történik. Ha ezt az értékesítési rendelési dokumentumot jelöléssel összekapcsolják a beszerzési rendeléssel még a csomagjegyzék vagy a számla feladása előtt, az ELÁBÉ nem a cikk jelenlegi mozgóátlaga lesz, hanem 120,00 USD. Ha még a jelölés előtt feladják a csomagjegyzéket vagy a számlát, a feladott ELÁBÉ megfelel a beszerzési ár mozgóátlagának. A két tranzakció még a készletzárás végrehajtása előtt is összekapcsolható egymással. Amikor jelöléssel összekapcsolnak egy bevételezési tranzakciót egy kiadási tranzakcióval, a rendszer nem veszi figyelembe a cikk modellcsoportjában megadott értékelési módot, és egymással szemben számolja el őket. Kiadási tranzakciót a tranzakció feladása előtt jelölhet hozzá egy nyugtához. Ezt megteheti egy értékesítési rendelés sorából az **Értékesítési rendelés** oldalon. A nyitott bevételezési tranzakciókat megtekintheti **Jelölés** oldalon. Kiadási tranzakciót a tranzakció feladása után jelölhet hozzá egy nyugtához. Egyeztethet vagy megjelölhet egy kiadási tranzakciót egy nyílt nyugtájú tranzakcióhoz egy leltárazott cikk esetén, feladott készlethelyesbítési naplósorból. A következő ábrán ezek a tranzakciók láthatók:

-   1a. Fizikai bevételezés készletre, 1 mennyiséggel, 10,00 USD áron.
-   1b. Pénzügyi bevételezés készletre, 1 mennyiséggel, 10,00 USD áron.
-   2a. Fizikai bevételezés készletre, 1 mennyiséggel, 20,00 USD áron.
-   2b. Pénzügyi bevételezés készletre, 1 mennyiséggel, 20,00 USD áron.
-   3a. Fizikai bevételezés készletre, 1 mennyiséggel, 25,00 USD áron.
-   4a. Fizikai bevételezés készletre, 1 mennyiséggel, 30,00 USD áron.
-   4b. Pénzügyi bevételezés készletre, 1 mennyiséggel, 30,00 USD áron.
-   5a. Fizikai kiadás készletről, 1 mennyiséggel, 21,25 USD önköltségi áron (a pénzügyileg és fizikailag frissített tranzakciók mozgóátlaga).
-   5b. Egy 1 mennyiségű pénzügyi készletkiadást jelöléssel összekötnek a 2b bevételezéssel a tranzakció feladása előtt. Ezt a tranzakciót darabonként 20,00 USD-s önköltségi áron adják fel.
-   6a. Fizikai kiadás készletről, 1 mennyiséggel, 21,25 USD áron.
-   7. Készletzárást hajtanak végre. Mivel a pénzügyileg frissített FIFO tranzakció össze van kapcsolva egy meglévő kiadással, ezeket a tranzakciókat egymással szemben számolja el a program, és nem kerül sor helyesbítésre.

Az új, mozgóátlagon alapuló önköltségi ár a pénzügyileg és fizikailag frissített tranzakciók átlagának, azaz 27,50 USD összegnek felel meg. A következő diagram a FIFO-elvű készletmodell hatását ábrázolja olyan tranzakciósorozatra, ahol kiadások és bevételezések vannak egymáshoz rendelve. 

![FIFO jelöléssel](./media/fifowithmarking.gif) 

**Jelmagyarázat**

- A készlettranzakciókat függőleges nyilak jelölik.
- A készletre való bevételezéseket az idősor fölötti függőleges nyilak jelölik.
- A készletről való kiadásokat az idősor alatti függőleges nyilak jelölik.
- Minden függőleges nyíl alatt vagy fölött a készlettranzakció értéke van megadva, Quantity@Unitprice formátumban.
- Ha zárójelbe van téve egy készlettranzakció értéke, akkor az arra utal, hogy a készlettranzakció fizikailag van feladva a készletre.
- Ha zárójelbe van téve egy készlettranzakció értéke, akkor az arra utal, hogy a készlettranzakció pénzügyileg van feladva a készletre.
- Minden új bevételezési és kiadási tranzakciót egy új címke jelöl.
- Mindegyik függőleges nyíl egy sorszámozott azonosítóval van ellátva, például *1a*. Az azonosítók a készlettranzakciók feladásának időbeli sorrendjét jelölik.
- A készletzárásokat egy piros színű, szaggatott függőleges vonal és a *Készletzárás* felirat jelöli.
- A készletzárás által végrehajtott elszámolásokat szaggatott piros nyilak jelölik, amelyek átlósan haladnak egy bevételezéstől egy kiadás felé.




