---
title: LIFO tényleges értékkel és jelöléssel
description: A LIFO (Last in, first out) egy olyan készletmodell, amelynél a legutóbb bevételezett (legújabb) cikkeket adják ki elsőként. A program a készletbe a készlettranzakció dátuma alapján legutoljára bevételezett cikkekből egyenlíti ki a kiadásokat.
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
ms.custom: 55021
ms.assetid: 49c492b0-b018-44e0-928f-9671e54eee20
ms.search.region: Global
ms.search.industry: Retail
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1f37bd17c151040254127ca29cf5b03336abe124
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5243371"
---
# <a name="lifo-with-physical-value-and-marking"></a>LIFO tényleges értékkel és jelöléssel

[!include [banner](../includes/banner.md)]

A LIFO (Last in, first out) egy olyan készletmodell, amelynél a legutóbb bevételezett (legújabb) cikkeket adják ki elsőként. A program a készletbe a készlettranzakció dátuma alapján legutoljára bevételezett cikkekből egyenlíti ki a kiadásokat. 

A LIFO (Last In, First Out azaz, utolsóként be, elsőként ki) készletmodell esetében a legutolsó (legújabb) bevételezések kiadása történik meg legelőször. A készletből származó kiadások a készletbe legkésőbb beérkezett bevételezésekkel szemben kerülnek rendezésre a készlettranzakció dátuma alapján. LIFO módszer használata esetén nem kell használni a LIFO-szabályt. Ehelyett a készlettranzakciók megjelölésével meghatározhatja, hogy adott cikk kiadása egy adott bevételezéssel kerüljön kiegyenlítésre. A LIFO-elvű készletmodell használata esetén javasoljuk, hogy időszakonként tartson készletzárást. 

Az alábbi példák bemutatják a LIFO-elv alkalmazásának hatását három különböző konfiguráción:

-   LIFO a **Tényleges értékkel együtt** beállítás nélkül
-   LIFO a **Tényleges értékkel együtt** beállítással
-   LIFO jelöléssel

## <a name="lifo-without-the-include-physical-value-option"></a>LIFO a Tényleges értékkel együtt beállítás nélkül
Ebben a példában a cikkmodellcsoport nem tartalmazza a tényleges értéket. A következő ábrán ezek a tranzakciók láthatók:

-   1a. Fizikai bevételezés készletre, 1 mennyiséggel, 10,00 USD áron.
-   1b. Pénzügyi bevételezés készletre, 1 mennyiséggel, 10,00 USD áron.
-   2a. Fizikai bevételezés készletre, 1 mennyiséggel, 20,00 USD áron.
-   2b. Pénzügyi bevételezés készletre, 1 mennyiséggel, 20,00 USD áron.
-   3a. Fizikai bevételezés készletre, 1 mennyiséggel, 25,00 USD áron.
-   4a. Fizikai bevételezés készletre, 1 mennyiséggel, 30,00 USD áron.
-   4b. Pénzügyi bevételezés készletre, 1 mennyiséggel, 30,00 USD áron.
-   5a. Fizikai kiadás készletről, 1 mennyiséggel, 20,00 USD önköltségi áron (a pénzügyileg frissített tranzakciók mozgóátlaga).
-   5b. Pénzügyi kiadás készletről, 1 mennyiséggel, 20,00 USD önköltségi áron (a pénzügyileg frissített tranzakciók mozgóátlaga).
-   6. Készletzárást hajtanak végre. A LIFO módszer alapján a legutóbbi pénzügyileg frissített kiadás rendezése, a legutóbb pénzügyileg frissített bevételezéssel szemben történik. A kiadási tranzakción 10,00 USD értékű korrekció történik.

Az új, mozgóátlagon alapuló önköltségi ár, a pénzügyileg frissített tranzakciók átlagának, azaz 15,00 USD összegnek felel meg. A következő illusztráció bemutatja, milyen hatása van a LIFO készletmodellnek erre a tranzakció sorozatra, ha a **Tényleges értékkel együtt** beállítás nincs beállítva. 

![LIFO a tényleges értékkel nélkül](./media/lifowithoutincludephysicalvalue.gif) 

**Jelmagyarázat**

- A készlettranzakciókat függőleges nyilak jelölik.
- A készletre való bevételezéseket az idősor fölötti függőleges nyilak jelölik.
- A készletről való kiadásokat az idősor alatti függőleges nyilak jelölik.
- Minden függőleges nyíl alatt vagy fölött a készlettranzakció értéke van megadva, a mennyiség x egységár formátumban.
- Ha zárójelbe van téve egy készlettranzakció értéke, akkor az arra utal, hogy a készlettranzakció fizikailag van feladva a készletre.
- Ha zárójelbe van téve egy készlettranzakció értéke, akkor az arra utal, hogy a készlettranzakció pénzügyileg van feladva a készletre.
- Minden új bevételezési és kiadási tranzakciót egy új címke jelöl.
- Mindegyik függőleges nyíl egy sorszámozott azonosítóval van ellátva, például *1a*. Az azonosítók a készlettranzakciók feladásának időbeli sorrendjét jelölik.
- A készletzárásokat egy piros színű, szaggatott függőleges vonal és a *Készletzárás* felirat jelöli.
- A készletzárás által végrehajtott elszámolásokat szaggatott piros nyilak jelölik, amelyek átlósan haladnak egy bevételezéstől egy kiadás felé.

## <a name="lifo-with-the-include-physical-value-option"></a>LIFO a Tényleges értékkel együtt beállítással
Ha egy cikkhez be van jelölve a **Tényleges értékkel együtt** jelölőnégyzet a **Cikkmodell-csoportok** lapon, a rendszer a fizikai és a pénzügyi bevételezési tranzakciókat egyaránt felhasználja a mozgóátlagon alapuló önköltségi ár kiszámításához. Ahol erre lehetőség van, a rendszer a fizikailag frissített kiadási tranzakción is végez korrekciót. Ha a **Tényleges értékkel együtt** jelölőnégyzet nincs bejelölve, a LIFO készletmodellel végrehajtott készletzárás csak a pénzügyileg frissített tranzakciókkal szemben végez teljesítést. 

A következő ábrán ezek a tranzakciók láthatók:

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
-   7. Készletzárást hajtanak végre. A LIFO módszer alapján a legutóbbi kiadású tranzakció, a legutóbb frissített bevételezéssel szemben lesz rendezve vagy helyesbítve.

A 6a jelű tranzakció a 4b jelű bevételezési tranzakcióra lesz helyesbítve. A rendszer nem egyenlíti ki ezeket a tranzakciókat, mivel a bevételezés csak fizikailag történt meg, pénzügyileg azonban nem. Ehelyett csak egy 8,75 USD értékű korrekció lesz feladva a tényleges kiadási tranzakcióra. Az 5b jelű tranzakció a 3a jelű fizikai bevételezési tranzakcióra lesz módosítva. Mivel nem történt meg mindkét tranzakció pénzügyi frissítése, ezért a rendszer nem rendezi őket. Ehelyett, csak egy –3,75 USD értékű korrekció történik a kiadási tranzakción. Az új, mozgóátlagon alapuló önköltségi ár a pénzügyileg és fizikailag frissített tranzakciók átlagának, azaz 20,00 USD összegnek felel meg. 

A következő ábra bemutatja, milyen hatása van a LIFO készletmodellnek, ha a **Tényleges értékkel együtt** beállítás be van kapcsolva. 

![LIFO a tényleges értékkel együtt](./media/lifowithincludephysicalvalue.gif) 

**Jelmagyarázat**

- A készlettranzakciókat függőleges nyilak jelölik.
- A készletre való bevételezéseket az idősor fölötti függőleges nyilak jelölik.
- A készletről való kiadásokat az idősor alatti függőleges nyilak jelölik.
- Minden függőleges nyíl alatt vagy fölött a készlettranzakció értéke van megadva, a mennyiség x egységár formátumban.
- Ha zárójelbe van téve egy készlettranzakció értéke, akkor az arra utal, hogy a készlettranzakció fizikailag van feladva a készletre.
- Ha zárójelbe van téve egy készlettranzakció értéke, akkor az arra utal, hogy a készlettranzakció pénzügyileg van feladva a készletre.
- Minden új bevételezési és kiadási tranzakciót egy új címke jelöl.
- Mindegyik függőleges nyíl egy sorszámozott azonosítóval van ellátva, például *1a*. Az azonosítók a készlettranzakciók feladásának időbeli sorrendjét jelölik.
- A készletzárásokat egy piros színű, szaggatott függőleges vonal és a *Készletzárás* felirat jelöli.
- A készletzárás által végrehajtott elszámolásokat szaggatott piros nyilak jelölik, amelyek átlósan haladnak egy bevételezéstől egy kiadás felé.

## <a name="lifo-with-marking"></a>LIFO jelöléssel
A jelölés egy olyan folyamat, amellyel összekapcsolható egy kiadási tranzakció egy bevételezési tranzakcióval. A jelölés történhet a tranzakciók feladása előtt és után is. A jelölés használható a készlet pontos költségének megállapítására a tranzakció feladásakor vagy a készletzárás végrehajtásakor. Tegyük fel például, hogy az ügyfélszolgálati osztály elfogadott egy sürgős megrendelést egy fontos vevőtől. Mivel ez a rendelés sürgős, ezért többet kell fizetni az adott cikkért az ügyfél kérésének teljesítése érdekében. 

Azt szeretné, ha a készlet költsége tükröződne az árrésben is (más szóval az eladott áruk beszerzési értékébe, ELÁBÉ) az adott értékesítési számla esetében. A beszerzési rendelés feladásakor a készlet bevételezése 120,00 USD értéken történik. Ha ezt az értékesítési rendelési dokumentumot jelöléssel összekapcsolják a beszerzési rendeléssel még a csomagjegyzék vagy a számla feladása előtt, az ELÁBÉ nem a cikk jelenlegi mozgóátlaga lesz, hanem 120,00 USD. Ha még a jelölés előtt feladják a csomagjegyzéket vagy a számlát, a feladott ELÁBÉ megfelel a beszerzési ár mozgóátlagának. 

A két tranzakció még a készletzárás végrehajtása előtt is összekapcsolható egymással. 

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

A következő diagram a LIFO-elvű készletmodell hatását ábrázolja olyan tranzakciósorozatra, ahol kiadások és bevételezések vannak egymáshoz rendelve. 

![LIFO jelöléssel](./media/lifowithmarking.gif) 

**Jelmagyarázat**

- A készlettranzakciókat függőleges nyilak jelölik.
- A készletre való bevételezéseket az idősor fölötti függőleges nyilak jelölik.
- A készletről való kiadásokat az idősor alatti függőleges nyilak jelölik.
- Minden függőleges nyíl alatt vagy fölött a készlettranzakció értéke van megadva, a mennyiség x egységár formátumban.
- Ha zárójelbe van téve egy készlettranzakció értéke, akkor az arra utal, hogy a készlettranzakció fizikailag van feladva a készletre.
- Ha zárójelbe van téve egy készlettranzakció értéke, akkor az arra utal, hogy a készlettranzakció pénzügyileg van feladva a készletre.
- Minden új bevételezési és kiadási tranzakciót egy új címke jelöl.
- Mindegyik függőleges nyíl egy sorszámozott azonosítóval van ellátva, például *1a*. Az azonosítók a készlettranzakciók feladásának időbeli sorrendjét jelölik.
- A készletzárásokat egy piros színű, szaggatott függőleges vonal és a *Készletzárás* felirat jelöli.
- A készletzárás által végrehajtott elszámolásokat szaggatott piros nyilak jelölik, amelyek átlósan haladnak egy bevételezéstől egy kiadás felé.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]