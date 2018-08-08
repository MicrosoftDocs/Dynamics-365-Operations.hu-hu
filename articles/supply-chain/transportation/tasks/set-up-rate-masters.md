--- 
title: "Díjtörzsek beállítása"
description: "Ez az eljárás bemutatja, hogyan állíthat be egy díjnyilvántartást."
author: ShylaThompson
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: b7c02e5a6f5eeee270ca4b6f91e90f7799c2ca11
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-rate-masters"></a>Díjtörzsek beállítása

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás bemutatja, hogyan állíthat be egy díjnyilvántartást. Általában a logisztikai vezető állítja be a díjnyilvántartást, a szállítmányozókkal aláírt szerződésektől függően. Ebben a példában egy légi fuvarozó számára állítunk be díjnyilvántartást. Ez az eljárás az USMF bemutatócéget használja.


## <a name="set-up-rate-master"></a>Díjtörzs beállítása
1. Lépjen a Szállításkezelés > Beállítás > Minősítés > Díjjegyzék pontra.
2. Kattintson az Új lehetőségre.
3. Érték beírása a Díjjegyzék mezőbe.
4. Írjon be egy értéket a Név mezőbe.
5. Az Értékelés metaadatok azonosítója mód mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
    * A díjazási metaadatok azonosítója határozza meg a díjnyilvántartáshoz szükséges adatokat, mivel ez határozza meg a TMS-motor számára szükséges metaadatokat, amely a ezt a díjnyilvántartást használja.  
6. Ebben a példában kattintson a P2P opció lehetőségre.
7. A listában kattintson a kijelölt sorban lévő hivatkozásra.
8. Kattintson a Mentés gombra.

## <a name="set-up-rate-base"></a>Díjalap beállítása
1. Kattintson az Alapdíj gombra.
    * Az alapdíj határozza meg a szállítmányozó díját, és felhasználható egy tarifaszerkezet létrehozásához, mivel a felosztásban meghatározott töréspontok alapján rendszerezi a díjakat.  
2. Kattintson az Új lehetőségre.
3. Érték beírása az Alapdíj mezőbe.
4. Írjon be egy értéket a Név mezőbe.
5. A Felosztás mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
    * A felosztást az árképzési szerkezet és annak töréspontjainak meghatározására használják. Az árképzési szerkezet többszintű árképzést használ a fizikai méretek alapján.  
6. Ebben a példában használja a súlyt
7. A listában kattintson a kijelölt sorban lévő hivatkozásra.
8. Bontsa ki a Részletek részt.
9. Kattintson az Új elemre.
10. A Lerakási hely irányítószáma – kezdő érték mezőbe írja be a 30301 értéket.
11. A Lerakási hely irányítószáma – befejező érték mezőbe írja be a 30318 értéket.
12. A Kiszállítási hely országa mezőbe írja be az USA értéket.
13. A(z) 100 Lbs mezőbe írja be a 100 értéket.
    * Adja meg a kilogrammonkénti költséget, ha a szállítmány teljes súlya kevesebb mint fél kilogramm.  
14. A 5.00 Lbs mezőbe írja be a 300 értéket.
    * Adja meg a kilogrammonkénti költséget, ha a szállítmány teljes súlya kevesebb mint két kilogramm.  
15. A 20.00 Lbs mezőbe írja be a 500 értéket.
    * Adja meg a kilogrammonkénti költséget, ha a szállítmány teljes súlya kevesebb mint 9 kilogramm.  
16. A 100.00 Lbs mezőbe írja be az 1000 értéket.
    * Adja meg a kilogrammonkénti költséget, ha a szállítmány teljes súlya kevesebb mint 45 kilogramm.  
17. A <1,000.00 Lbs mezőbe írja be a 3000 értéket.
    * Adja meg a kilogrammonkénti költséget, ha a szállítmány teljes súlya kevesebb mint 450 kilogramm.  
18. Kattintson a Mentés gombra.
19. Zárja be a lapot.

## <a name="assign-rate-base"></a>Díjalap hozzárendelése
1. Az Alapdíj hozzárendelés szakasz bővítésének átváltása.
2. Kattintson az Új lehetőségre.
    * Mindegyik díjnyilvántartáshoz hozzárendelhet több díjalapot. Ez lehetővé teszi a különböző árpontok létrehozását az egyes szállítmányozók számára a céltól, a szolgáltatástól vagy a különböző alapdíjaktól függően. Ebben az eljárásban csak egy alapdíj-hozzárendelést hoz majd létre.  
3. Írjon be egy értéket a Név mezőbe.
4. Az Alapdíj mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
5. A listában kattintson a kijelölt sorban lévő hivatkozásra.
6. A Szolgáltatás mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
7. A kívánt rekord megkeresése és kijelölése a listán
8. A listában kattintson a kijelölt sorban lévő hivatkozásra.
9. A Felvételi hely irányítószáma mezőbe írja be a 98052 értéket.
    * Válassza ki, hogy melyik irányítószámról legyen érvényes ez az alapdíj-hozzárendelés.    
10. A Felvételi hely országa mezőbe írja be az USA értéket.
11. Kattintson a Mentés gombra.


