---
title: Vevői visszatérítések létrehozása és feldolgozása
description: Ez az eljárás bemutatja, hogyan lehet feldolgozni az ügyfél-visszatérítéseket az igénylés létrehozásától addig a pontig, hogy könyvelésekként felveszi őket a Kinnlevőségek közé.
author: omulvad
manager: tfehr
ms.date: 06/25/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PdsRebateAgreement, SalesTableListPage, SalesCreateOrder, SalesTable, MCRPriceHistory, SalesEditLines,  PdsRebateTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 87ddaddb00da50ef9e9e1e7ecf7c3620dabb5a17
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/02/2020
ms.locfileid: "3209950"
---
# <a name="generate-and-process-customer-rebates"></a>Vevői visszatérítések létrehozása és feldolgozása

[!include [banner](../../includes/banner.md)]

Ez az eljárás bemutatja, hogyan lehet feldolgozni az ügyfél-visszatérítéseket az igénylés létrehozásától addig a pontig, hogy könyvelésekként felveszi őket a Kinnlevőségek közé. Végigvezeti egy adott példán annak megmagyarázása érdekében, hogy a különféle feltételek a visszatérítés-sorokban milyen hatással vannak a vevő részére jóváírandó végleges összegekre. Az USMF bemutatócég adatait kell használnia, és a következő feladatokat kell elvégeznie, mielőtt elindítja az útmutatót: (1) A Kinnlevőségek paraméterei lapon bontsa ki az Árak lapot, majd az Ár részletei fület is, és ellenőrizze, hogy az Igen lehetőség be van-e jelölve az Áradatok engedélyezése mellett. (2) A Visszatérítési megállapodások lapon válassza ki ezt a vevői visszatérítési megállapodást: USMF-000001. Ha a munkafolyamat jóváhagyási állapota mezőben nem a Jóváhagyott szerepel, annak jóváhagyásához kattintson a műveleti ablak Érvényesítés gombjára.


## <a name="review-a-customer-rebate-agreement"></a>Vevői visszatérítési megállapodás áttekintése
1. Lépjen a **Navigációs panel > Modulok > Értékesítés és marketing > Ügyfél-visszatérítések > Visszatérítési szerződések** menüpontba.
    - A következő néhány lépés az USMF-000001 megállapodás feltételeit tekinti át. Ez megkönnyíti az eljárásban később kiszámított vevői hitelértékek megértését.  
    - A megállapodás egy adott vevőhöz tartozik, ebben a példában az US-009 vevőhöz.  
    - Visszatérítést akkor kap egy vevő, ha egy adott terméket vásárol. Ebben az esetben a termékhez tartozó cikkszám: T0020.   
    - A vevő értékesítési teljesítményének – amely alapján a visszatérítési összeget a rendszer kiszámítja – összegzése hetente történik.  
    - Az „Ár forrása” értéke bruttó, ami azt jelenti, hogy annak a sornak az értékesítési összegét, amelyen a követelés becslése alapul, a sorengedmény nem csökkenti.  
    - A Visszatérítés sor szünettípusa mezőben a visszatérítések számításához használt módszer látható. Ebben az esetben az az értékesítési cél, amely alapján a rendszer a visszatérítéseket kiszámítja, a Mennyiség.   
    - A szerződés sorai megadják a visszatérítés összegének típusát, a tényleges visszatérítési értéket és a küszöbértékeket. Ebben a példában a vevő 20 USD/értékesített egység visszatérítésre lesz jogosult, ha a termékből hetente 1 és 50 egység közötti mennyiséget vásárolt; illetve 40 USD/értékesített egység visszatérítésre lesz jogosult, ha a termékből hetente több mint 50 egységet vásárolt.  
2. Zárja be a lapot.

## <a name="generate-rebate-claims"></a>Visszatérítési igények létrehozása
1. Ugorjon az **Navigációs lap > Modulok > Értékesítés és marketing > Értékesítési rendelések > Minden értékesítési rendelés** pontra.
2. Kattintson az **Új** elemre. A visszatérítési igénylések módjának utánzása érdekében a következő feladat az értékesítési rendelés létrehozása, ahol a termék és a mennyiség fogja az adott vevőt feljogosítani az árengedményre.    
3. A **Vevőszámla** mezőben adjon meg vagy válasszon ki egy értéket.
4. Kattintson az **OK** gombra.
5. Az **Cikkszám** mezőben adjon meg vagy válasszon ki egy értéket.
6. Állítsa a **Mennyiség** lehetőséget „40-re”.
7. Az **Értékesítésirendelés-sorok** szakaszban válassza ki az **Értékesítésirendelés-sort**.
8. Kattintson az **Ár részletei** elemre. Ha nem látja ezt a lehetőséget, az azért lehet, mert az útmutató indítása előtt nem állította az **Árrészletek beállítását** az Igen lehetőségre.     
9. Bontsa ki a **Visszatérítések** szakaszt. A **Visszatérítések** lap felsorolja az aktuális rendelési sorra vonatkozó összes visszatérítési megállapodást, illetve megjeleníti a becsült visszatérítési összeget is. Ne feledje, hogy a megjelenített összegek csak iránymutatóak a jövőbeli visszatérítési követelésekre vonatkozóan. A tényleges visszatérítési összegek eltérők lehetnek a következők alapján: időszakos visszatérítési megállapodás alapján a vevő által elért teljes értékesítési mennyiség, hogy a vevő a teljes vagy csak részleges mennyiséget hozott-e vissza; és hogy az értékesítési rendelést kiszámlázták-e.
10. Zárja be a lapot.
11. Kattintson az **Új sor hozzáadása** elemre.
12. Az **Cikkszám** mezőben adjon meg vagy válasszon ki egy értéket.
13. Állítsa a **Mennyiség** lehetőséget „60-re”.
14. Kattintson a **Mentés** gombra.
15. A **Művelet panelen** kattintson a **Számla** elemre.
16. Kattintson a **Számla** pontra.
17. Bontsa ki a **Paraméterek** szakaszt.
18. A **Mennyiség** mezőben válassza a 'Mind' lehetőséget.
19. Kattintson az **OK** gombra.
20. Kattintson az **OK** gombra.

## <a name="process-rebate-claims"></a>Visszatérítési igények feldolgozása
1. Lépjen a **Navigációs panel > Modulok > Értékesítés és marketing > Ügyfél-visszatérítések > Visszatérítések** menüpontba.
    - A Visszatérítések lap egy olyan munkaterület, amelyben áttekintheti, jóváhagyhatja és feldolgozhatja a visszatérítési igényléseket. Most fel fogja dolgozni azokat az igényeket, amelyeket az US-009 vevő értékesítési rendelésének számlázásához hozott létre, aki az USMF-000001 visszatérítési megállapodás alanya.   
    - Az első sor egy 800 USD értékű visszatérítési igénylést jelenít meg, amelynek az alapja a T0020 termék 40 egységének értékesítése, egységenként 20 USD áron. Ez megfelel az első mennyiségi szünet feltételeinek a visszatérítési megállapodásban.  
    - A második követelés 2400 USD értékű, amely a T0020 termék 60 egységének értékesítése alapján került kiszámításra 40 USD/egység áron, a a szerződés második mennyiségi szünete szerint.  
    - Mindkét igény „Kiszámításra vár” állapotban van. Ez azt jelenti, hogy ezek társítva vannak egy olyan szerződéshez, amely rendszeres időközönként nyomon követi a vevő értékesítési teljesítményét, és hogy az adott időszakon belül újra kell számolni a teljes értékesítési mennyiséghez.   
2. Kattintson az **Összesítés** gombra.
3. Az **Ügyfél** mezőben adjon meg vagy válasszon ki egy értéket.
4. A **Kezdő dátum** mezőben válassza ki a mai napot.
5. Kattintson az **OK** gombra. A futó **Összegzés** funkció eredményeként a becsült igénylési összeget korrigáltuk úgy, hogy az figyelembe vegye azt a tényt, hogy a vevő teljes értékesítési mennyisége az adott időszakban magasabb, mint amikor az első visszatérítés létrejött. Konkrétabban mivel az összes beszerzett mennyiség elérte a 100 egységet, a vevő már jogosult a 40 USD/egység (a szerződés második mennyiségi szünete szerinti), vagy az összesen 400 USD visszatérítési összegre. A különbséget a rendszer új igény „helyesbítéseként” jegyzi fel a további 800 USD-re vonatkozóan. A Felhalmozási frissítésben megjelenő visszatérítési igény állapota most már Kiszámított. 
6. A listában jelöljön ki minden sort.
7. Kattintson a **Jóváhagyás** lehetőségre.
8. Kattintson a **Folyamat** gombra.
9. Az **Ügyfél** mezőben adjon meg vagy válasszon ki egy értéket.
10. Kattintson az **OK** gombra. Megjelenik egy üzenet, hogy a visszatérítés feldolgozása sikeresen befejeződött, és az igénylések állapotát a rendszer a Jelölés értékre frissítette. Ez azt jelenti, hogy a visszatérítési könyvelési napló feladása eredményeképpen:
    - A követelések levonásként átvitelre most már kerültek az ideiglenes vevői egyenlegbe.
    - A Visszatérítés elhatárolási számlán jóváírás történt, hogy a vevő jövőbeli kötelezettségét jelezze.
    - A Visszatérítés költségszámlán terhelés történt, hogy az értékesítéssel kapcsolatban felmerült költségeket jelezze.   

