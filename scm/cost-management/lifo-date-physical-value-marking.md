---
title: "LIFO dátum tényleges értékkel és jelöléssel"
description: "A LIFO dátum készletmodell a LIFO-elv alapján működik. A program a készletbe a készlettranzakció dátuma alapján legutoljára bevételezett cikkekből egyenlíti ki a kiadásokat. Ha a dátum szerinti LIFO készletmodellben nincs bevételezés a kiadás előtt, akkor a kiadás az utána következő bármelyik bevételezéssel kiegyenlíthető. Ha ugyanazzal a dátummal több kiadás van, akkor az az utolsó kiadás, utolsó bevételezés sorrendben egyenlíthető ki."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventJournalLossProfit, InventMarking, InventModelGroup, SalesTable
audience: Application User
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 51592
ms.assetid: d9f13274-3268-444f-85c8-b686fd39286d
ms.search.region: Global
ms.search.industry: Retail
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 96089fed3e8b522fb3a8646ffd87fadff8fe1f3e
ms.contentlocale: hu-hu
ms.lasthandoff: 05/25/2017


---

# <a name="lifo-date-with-physical-value-and-marking"></a>LIFO dátum tényleges értékkel és jelöléssel

[!include[banner](../includes/banner.md)]


A LIFO dátum készletmodell a LIFO-elv alapján működik. A program a készletbe a készlettranzakció dátuma alapján legutoljára bevételezett cikkekből egyenlíti ki a kiadásokat. Ha a dátum szerinti LIFO készletmodellben nincs bevételezés a kiadás előtt, akkor a kiadás az utána következő bármelyik bevételezéssel kiegyenlíthető. Ha ugyanazzal a dátummal több kiadás van, akkor az az utolsó kiadás, utolsó bevételezés sorrendben egyenlíthető ki. 

Ha a LIFO dátumos készletmodellt használja és ha nincs bevételezés a kiadás előtt, akkor a kiadás az utána következő bármelyik bevételezéssel kiegyenlíthető. Ha ugyanazzal a dátummal több kiadás van, akkor az az utolsó kiadás, utolsó bevételezés sorrendben egyenlíthető ki. A LIFO dátum módszer használata esetén nem kell használni a LIFO-dátumszabályt. Ehelyett egyes készlettranzakciók megjelölésével meghatározhatja, hogy egy adott bevételezés egy meghatározott kiadással legyen kiegyenlítve. 

A dátum szerinti LIFO-elvű készletmodell használata esetén javasoljuk, hogy időszakonként tartson készletzárást. 

Az alábbi példák bemutatják a LIFO-dátumelv alkalmazásának hatását három különböző konfiguráción:

-   LIFO dátum a **Tényleges értékkel együtt** beállítás nélkül
-   LIFO dátum a**Tényleges értékkel együtt** beállítással
-   LIFO dátum jelöléssel

## <a name="lifo-date-without-the-include-physical-value-option"></a>LIFO dátum a Tényleges értékkel együtt beállítás nélkül
Ebben a példában a cikkmodellcsoport nem tartalmazza a tényleges értéket. A következő ábrán ezek a tranzakciók láthatók:

-   1a. Fizikai bevételezés készletre, 1 mennyiséggel, 10,00 USD áron.
-   1b. Pénzügyi bevételezés készletre, 1 mennyiséggel, 10,00 USD áron.
-   2a. Fizikai bevételezés készletre, 1 mennyiséggel, 20,00 USD áron.
-   2b. Pénzügyi bevételezés készletre, 1 mennyiséggel, 20,00 USD áron.
-   3a. Fizikai bevételezés készletre, 1 mennyiséggel, 25,00 USD áron.
-   4a. Fizikai kiadás készletről, 1 mennyiséggel, 15,00 USD önköltségi áron (a pénzügyileg frissített tranzakciók mozgóátlaga).
-   4b. Pénzügyi kiadás készletről, 1 mennyiséggel, 15,00 USD önköltségi áron (a pénzügyileg frissített tranzakciók mozgóátlaga).
-   5a. Fizikai bevételezés készletre, 1 mennyiséggel, 30,00 USD áron.
-   5b. Pénzügyi bevételezés készletre, 1 mennyiséggel, 30,00 USD áron.
-   6. Készletzárást hajtanak végre. A LIFO dátummódszer alapján a legutóbbi pénzügyileg frissített kiadás teljesítése a legutóbb pénzügyileg frissített bevételezéssel szemben történik. A kiadási tranzakción 5,00 USD értékű korrekció történik. Ezeknek a tranzakcióknak az elszámolása egymással szemben történik.

Az új, mozgóátlagon alapuló önköltségi ár a pénzügyileg frissített tranzakciók átlagának, azaz 15,00 USD összegnek felel meg. 

A következő ábra bemutatja, milyen hatása van a LIFO dátum készletmodellnek, ha a **Tényleges értékkel együtt** beállítás nincs bekapcsolva. ![LIFO dátum a tényleges értékkel együtt](./media/lifodatewithoutincludephysicalvalue.gif) 

**Jelmagyarázat**

-   A készlettranzakciókat függőleges nyilak jelölik.
-   A készletre való bevételezéseket az idősor fölötti függőleges nyilak jelölik.
-   A készletről való kiadásokat az idősor alatti függőleges nyilak jelölik.
-   Minden függőleges nyíl alatt vagy fölött a készlettranzakció értéke van megadva Quantity@Unitprice formátumban.
-   Ha zárójelbe van téve egy készlettranzakció értéke, akkor az arra utal, hogy a készlettranzakció fizikailag van feladva a készletre.
-   Ha zárójelbe van téve egy készlettranzakció értéke, akkor az arra utal, hogy a készlettranzakció pénzügyileg van feladva a készletre.
-   Minden új bevételezési és kiadási tranzakciót egy új címke jelöl.
-   Mindegyik függőleges nyíl egy sorszámozott azonosítóval van ellátva, például *1a*. Az azonosítók a készlettranzakciók feladásának időbeli sorrendjét jelölik.
-   A készletzárásokat egy piros színű, szaggatott függőleges vonal és a *Készletzárás* felirat jelöli.
-   A készletzárás által végrehajtott elszámolásokat szaggatott piros nyilak jelölik, amelyek átlósan haladnak egy bevételezéstől egy kiadás felé.

## <a name="lifo-date-with-the-include-physical-value-option"></a>LIFO dátum a Tényleges értékkel együtt beállítással
A **Tényleges értékkel együtt** a jelölőnégyzetet a **Modell cikkcsoportok** lapon választhatja ki. Ebben az esetben a rendszer a fizikai és pénzügyi bevételezési tranzakciókat egyaránt felhasználja a mozgóátlagon alapuló önköltségi ár kiszámításához. Ahol erre lehetőség van, a rendszer a fizikailag frissített kiadási tranzakción is végez korrekciót. Ha a **Tényleges értékkel együtt** jelölőnégyzet nincs bejelölve, a LIFO dátum készletmodellel végrehajtott készletzárás csak a pénzügyileg frissített tranzakciókkal szemben végez teljesítést. 

Ebben a példában a cikkmodellcsoport tartalmazza a tényleges értéket. 

A következő ábrán ezek a tranzakciók láthatók:

-   1a. Fizikai bevételezés készletre, 1 mennyiséggel, 10,00 USD áron.
-   1b. Pénzügyi bevételezés készletre, 1 mennyiséggel, 10,00 USD áron.
-   2a. Fizikai bevételezés készletre, 1 mennyiséggel, 20,00 USD áron.
-   2b. Pénzügyi bevételezés készletre, 1 mennyiséggel, 20,00 USD áron.
-   3a. Fizikai bevételezés készletre, 1 mennyiséggel, 25,00 USD áron.
-   4a. Fizikai kiadás készletről, 1 mennyiséggel, 18,33 USD önköltségi áron (a pénzügyileg frissített tranzakciók mozgóátlaga).
-   4b. Pénzügyi kiadás készletről, 1 mennyiséggel, egyenként 18,33 USD önköltségi áron (a pénzügyileg frissített tranzakciók mozgóátlaga).
-   5a. Fizikai bevételezés készletre, 1 mennyiséggel, 30,00 USD áron.
-   5b. Pénzügyi bevételezés készletre, 1 mennyiséggel, 30,00 USD áron.
-   6. Készletzárást hajtanak végre. A Dátum LIFO módszer alapján a legutóbbi frissített kiadás korrekciója vagy teljesítése a legutóbb frissített bevételezéssel szemben történik. Ezeknek a tranzakcióknak az elszámolása nem egymással szemben történik, mert a pénzügyi bevételezési tranzakciót fizikai frissítési tranzakcióhoz igazítja a rendszer. Ehelyett csak egy 6,67 USD értékű korrekció történik a kiadási tranzakción.

Az új, mozgóátlagon alapuló önköltségi ár a pénzügyileg frissített tranzakciók átlagának, azaz 20,00 USD összegnek felel meg. 

A következő ábra bemutatja, milyen hatása van a LIFO dátum készletmodellnek, ha a **Tényleges értékkel együtt** beállítás be van kapcsolva. ![LIFO dátum a tényleges értékkel együtt](./media/lifodatewithincludephysicalvalue.gif) 

**Jelmagyarázat**

-   A készlettranzakciókat függőleges nyilak jelölik.
-   A készletre való bevételezéseket az idősor fölötti függőleges nyilak jelölik.
-   A készletről való kiadásokat az idősor alatti függőleges nyilak jelölik.
-   Minden függőleges nyíl alatt vagy fölött a készlettranzakció értéke van megadva Quantity@Unitprice formátumban.
-   Ha zárójelbe van téve egy készlettranzakció értéke, akkor az arra utal, hogy a készlettranzakció fizikailag van feladva a készletre.
-   Ha zárójelbe van téve egy készlettranzakció értéke, akkor az arra utal, hogy a készlettranzakció pénzügyileg van feladva a készletre.
-   Minden új bevételezési és kiadási tranzakciót egy új címke jelöl.
-   Mindegyik függőleges nyíl egy sorszámozott azonosítóval van ellátva, például *1a*. Az azonosítók a készlettranzakciók feladásának időbeli sorrendjét jelölik.
-   A készletzárásokat egy piros színű, szaggatott függőleges vonal és a *Készletzárás* felirat jelöli.
-   A készletzárás által végrehajtott elszámolásokat szaggatott piros nyilak jelölik, amelyek átlósan haladnak egy bevételezéstől egy kiadás felé.

## <a name="lifo-date-with-marking"></a>LIFO dátum jelöléssel
A jelölés egy olyan folyamat, amellyel összekapcsolható egy kiadási tranzakció egy bevételezési tranzakcióval. A jelölés történhet a tranzakciók feladása előtt és után is. A jelölés használható a készlet pontos költségének megállapítására a tranzakció feladásakor vagy a készletzárás végrehajtásakor. 

Tegyük fel például, hogy az ügyfélszolgálati osztály elfogadott egy sürgős megrendelést egy fontos vevőtől. Mivel ez a rendelés sürgős, tehát többe fog kerülni az ügyfél kérésének teljesítése. Azt szeretné, ha a készlet költsége tükröződne az árrésben is (más szóval az eladott áruk beszerzési értékébe, ELÁBÉ) az adott értékesítési számla esetében. 

A beszerzési rendelés feladásakor a készlet bevételezése 120,00 USD értéken történik. Ha ezt az értékesítési rendelési dokumentumot jelöléssel összekapcsolják a beszerzési rendeléssel még a csomagjegyzék vagy a számla feladása előtt, az ELÁBÉ nem a cikk jelenlegi mozgóátlaga lesz, hanem 120,00 USD. Ha még a jelölés előtt feladják a csomagjegyzéket vagy a számlát, a feladott ELÁBÉ megfelel a beszerzési ár mozgóátlagának. 

A két tranzakció még a készletzárás végrehajtása előtt is összekapcsolható egymással. 

Például egy bevételezési tranzakció egy kiadási tranzakcióhoz van megjelölve. Ebben az esetben a cikk cikkmodelcsoportjában meghatározott értékelési mód nincs figyelembe véve, és a rendszer ezeket a tranzakciókat egymással szemben egyenlíti ki. 

Kiadási tranzakciót a tranzakció feladása előtt jelölhet hozzá egy nyugtához. Ezt megteheti egy értékesítési rendelés sorából az **Értékesítési rendelés** oldalon. A nyitott bevételezési tranzakciókat megtekintheti **Jelölés** oldalon. 

Kiadási tranzakciót a tranzakció feladása után jelölhet hozzá egy nyugtához. Egyeztethet vagy megjelölhet egy kiadási tranzakciót egy nyílt nyugtájú tranzakcióhoz egy leltárazott cikk esetén, feladott készlethelyesbítési naplósorból. 

A következő ábrán ezek a tranzakciók láthatók:

-   1a. Fizikai bevételezés készletre, 1 mennyiséggel, 10,00 USD áron.
-   1b. Pénzügyi bevételezés készletre, 1 mennyiséggel, 10,00 USD áron.
-   2a. Fizikai bevételezés készletre, 1 mennyiséggel, 20,00 USD áron.
-   2b. Pénzügyi bevételezés készletre, 1 mennyiséggel, 20,00 USD áron.
-   3a. Fizikai bevételezés készletre, 1 mennyiséggel, 25,00 USD áron.
-   4a. Fizikai bevételezés készletre, 1 mennyiséggel, 30,00 USD áron.
-   4b. Pénzügyi bevételezés készletre, 1 mennyiséggel, 30,00 USD áron.
-   5a. Fizikai kiadás készletről, 1 mennyiséggel, 21,25 USD önköltségi áron (a pénzügyileg és fizikailag frissített tranzakciók mozgóátlaga).
-   5b. Egy 1 mennyiségű pénzügyi készletkiadást jelöléssel összekötnek a 2b bevételezéssel a tranzakció feladása előtt. Ezt a tranzakciót 20,00 USD önköltségi árral adja fel a program.
-   6a. Fizikai kiadás készletről, 1 mennyiséggel, 21,25 USD áron.
-   7. Készletzárást hajtanak végre. Mivel a pénzügyileg frissített FIFO tranzakció össze van kapcsolva egy meglévő kiadással, ezeket a tranzakciókat egymással szemben számolja el a program, és nem kerül sor helyesbítésre.

Az új, mozgóátlagon alapuló önköltségi ár a pénzügyileg és fizikailag frissített tranzakciók átlagának, azaz 27,50 USD összegnek felel meg. 

A következő ábra bemutatja, milyen hatása van a LIFO dátum készletmodellnek, ha a kiadások és bevételek közötti jelölés használva van. ![LIFO dátum jelöléssel](./media/lifodatewithmarking.gif) 

**Jelmagyarázat**

-   A készlettranzakciókat függőleges nyilak jelölik.
-   A készletre való bevételezéseket az idősor fölötti függőleges nyilak jelölik.
-   A készletről való kiadásokat az idősor alatti függőleges nyilak jelölik.
-   Minden függőleges nyíl alatt vagy fölött a készlettranzakció értéke van megadva Quantity@Unitprice formátumban.
-   Ha zárójelbe van téve egy készlettranzakció értéke, akkor az arra utal, hogy a készlettranzakció fizikailag van feladva a készletre.
-   Ha zárójelbe van téve egy készlettranzakció értéke, akkor az arra utal, hogy a készlettranzakció pénzügyileg van feladva a készletre.
-   Minden új bevételezési és kiadási tranzakciót egy új címke jelöl.
-   Mindegyik függőleges nyíl egy sorszámozott azonosítóval van ellátva, például *1a*. Az azonosítók a készlettranzakciók feladásának időbeli sorrendjét jelölik.
-   A készletzárásokat egy piros színű, szaggatott függőleges vonal és a *Készletzárás* felirat jelöli.
-   A készletzárás által végrehajtott elszámolásokat szaggatott piros nyilak jelölik, amelyek átlósan haladnak egy bevételezéstől egy kiadás felé.





