--- 
title: "Nyersanyagok létrehozása (2016. február)"
description: "Ez a feladat a késztermékek és a félkész termékek komponenseinek létrehozását összpontosít."
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResProductDetailsExtended, EcoResProductCreate, InventItemOrderSetup, InventItemPrice
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 091b6edaf43e86e6e3665bf79871648473e284c7
ms.contentlocale: hu-hu
ms.lasthandoff: 09/14/2018

---
# <a name="create-raw-materials-february-2016"></a>Nyersanyagok létrehozása (2016. február)

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ez a feladat a késztermékek és a félkész termékek komponenseinek létrehozását összpontosít. Ez az anyagjegyzék-számítási sorozat harmadik feladata. A feladat létrehozásához az USMF bemutató vállalatot használtuk példaként.


## <a name="create-the-first-material"></a>Az első anyag létrehozása
1. Kattintson a Termékinformációk kezelése > Termékek > Kiadott termékek lehetőségre.
2. Kattintson az Új lehetőségre.
3. Írjon be egy értéket a Termékszám mezőbe.
    * Ennél a példánál adja meg az ITEM_A lehetőséget.  
4. Az Elem modellcsoport mezőben adjon meg, vagy válasszon ki egy értéket.
    * Válassza az STD lehetőséget. Az STD az elszámolóár rövidítése, és a költségszámításokkal dolgozva ez a leggyakrabban használt modell.  
5. Az Elemcsoport mezőben adjon meg, vagy válasszon ki egy értéket.
    * Válassza például a következőt: Audió. Nincs hatással a költségszámításokra.  
6. A Tárolási dimenzió mezőben adjon meg, vagy válasszon ki egy értéket.
    * SiteWH kiválasztása. A bemutatóhoz csak a helyet és a raktárat használjuk.  
7. A Nyomon követési dimenzió mezőben adjon meg, vagy válasszon ki egy értéket.
    * A nyomon követési dimenziókat nem használjuk ennél a példánál. Válassza a Nincs lehetőséget.  
8. Kattintson az OK gombra.
9. A Művelet panelen kattintson a Készletkezelés elemre.
10. Kattintson az Alapértelmezett rendelésbeállítások elemre.
11. A Beszerzési hely mezőben adjon meg, vagy válasszon ki egy értéket.
    * Ehhez a példához válassza ki a következőt: 1. hely.  
12. A Készlethely mezőben adjon meg, vagy válasszon ki egy értéket.
    * Ehhez a példához válassza ki a következőt: 1. hely.  
13. Az Értékesítési hely mezőben adjon meg vagy válasszon ki egy értéket.
    * Ehhez a példához válassza ki a következőt: 1. hely.  
14. Zárja be a lapot.
15. Zárja be a lapot.
16. A listában kattintson a kijelölt sorban lévő hivatkozásra.
    * Kattintson az ITEM_A lehetőségre.  
17. Bontsa ki a Költségkezelés szakaszt.
18. Írjon be egy értéket a Költségcsoport mezőbe.
    * Ehhez a példához írja be a következőt: M2.  
19. A Művelet panelen kattintson a Költségkezelés elemre.
20. Kattintson a Cikk ára elemre.
21. Kattintson az Új lehetőségre.
22. A Verzió mezőben adjon meg vagy válasszon ki egy értéket.
    * Ebben a példában válassza a 10 lehetőséget, az elszámolóár költségszámítási típust.  
23. A Hely mezőben adjon meg vagy válasszon ki egy értéket.
    * Ehhez a példához válassza ki a következőt: 1. hely.  
24. Adjon meg egy számot az Ár mezőben.
    * Ehhez a példához írja be a következőt: 10.  
25. Kattintson a Mentés gombra.
26. Kattintson a Függő árak aktiválása lehetőségre.
27. Zárja be a lapot.
28. Zárja be a lapot.

## <a name="create-the-second-material"></a>A második anyag létrehozása
1. Kattintson az Új lehetőségre.
2. Írjon be egy értéket a Termékszám mezőbe.
    * Ehhez a példához írja be a következőt: ITEM_B.  
3. Az Elem modellcsoport mezőben adjon meg, vagy válasszon ki egy értéket.
    * Válassza az STD lehetőséget. Az STD az elszámolóár rövidítése, és a költségszámításokkal dolgozva ez a leggyakrabban használt modell.  
4. Az Elemcsoport mezőben adjon meg, vagy válasszon ki egy értéket.
    * Válassza például a következőt: Audió. Nincs hatással a költségszámításokra.  
5. A Tárolási dimenzió mezőben adjon meg, vagy válasszon ki egy értéket.
    * SiteWH kiválasztása. A példához csak a helyet és a raktárat használjuk.  
6. A Nyomon követési dimenzió mezőben adjon meg, vagy válasszon ki egy értéket.
    * A nyomon követési dimenziókat nem használjuk ennél a példánál. Válassza a Nincs lehetőséget.  
7. Kattintson az OK gombra.
8. A Művelet panelen kattintson a Készletkezelés elemre.
9. Kattintson az Alapértelmezett rendelésbeállítások elemre.
10. A Beszerzési hely mezőben adjon meg, vagy válasszon ki egy értéket.
    * Ehhez a példához válassza ki a következőt: 1. hely.  
11. A Készlethely mezőben adjon meg, vagy válasszon ki egy értéket.
    * Ehhez a példához válassza ki a következőt: 1. hely.  
12. Az Értékesítési hely mezőben adjon meg vagy válasszon ki egy értéket.
    * Ehhez a példához válassza ki a következőt: 1. hely.  
13. Zárja be a lapot.
14. Zárja be a lapot.
15. A listában kattintson a kijelölt sorban lévő hivatkozásra.
    * Kattintson az ITEM_B lehetőségre.  
16. Bontsa ki a Költségkezelés szakaszt.
17. Írjon be egy értéket a Költségcsoport mezőbe.
    * Ehhez a példához írja be a következőt: M2.  
18. A Művelet panelen kattintson a Költségkezelés elemre.
19. Kattintson a Cikk ára elemre.
20. Kattintson az Új lehetőségre.
21. A Verzió mezőben adjon meg vagy válasszon ki egy értéket.
    * Ehhez a példához válassza ki a következőt: 10. Ez az Elszámolóár költségszámítási típus.  
22. A Hely mezőben adjon meg vagy válasszon ki egy értéket.
    * Ehhez a példához válassza ki a következőt: 1. hely.  
23. Adjon meg egy számot az Ár mezőben.
    * A bemutató céljára írja be a következőt: 10.  
24. Kattintson a Mentés gombra.
25. Kattintson a Függő árak aktiválása lehetőségre.
26. Zárja be a lapot.
27. Zárja be a lapot.

## <a name="create-the-third-material"></a>A harmadik anyag létrehozása
1. Kattintson az Új lehetőségre.
2. Írjon be egy értéket a Termékszám mezőbe.
    * A bemutató céljára írja be a következőt: ITEM_C.  
3. Az Elem modellcsoport mezőben adjon meg, vagy válasszon ki egy értéket.
    * Válassza az STD lehetőséget. Az STD az elszámolóár rövidítése, és a költségszámításokkal dolgozva ez a leggyakrabban használt modell.  
4. Az Elemcsoport mezőben adjon meg, vagy válasszon ki egy értéket.
    * Válassza például a következőt: Audió. Nincs hatással a költségszámításokra.  
5. A Tárolási dimenzió mezőben adjon meg, vagy válasszon ki egy értéket.
    * SiteWH kiválasztása. A bemutatóhoz csak a helyet és a raktárat használjuk.  
6. A Nyomon követési dimenzió mezőben adjon meg, vagy válasszon ki egy értéket.
    * A nyomon követési dimenziókat nem használjuk ennél a példánál. Válassza a Nincs lehetőséget.  
7. Kattintson az OK gombra.
8. A Művelet panelen kattintson a Készletkezelés elemre.
9. Kattintson az Alapértelmezett rendelésbeállítások elemre.
10. A Beszerzési hely mezőben adjon meg, vagy válasszon ki egy értéket.
    * Ehhez a példához válassza ki a következőt: 1. hely.  
11. A Készlethely mezőben adjon meg, vagy válasszon ki egy értéket.
    * Ehhez a példához válassza ki a következőt: 1. hely.  
12. Az Értékesítési hely mezőben adjon meg vagy válasszon ki egy értéket.
    * Ehhez a példához válassza ki a következőt: 1. hely.  
13. Zárja be a lapot.
14. Zárja be a lapot.
15. A listában kattintson a kijelölt sorban lévő hivatkozásra.
    * Kattintson az ITEM_C lehetőségre.  
16. Bontsa ki a Költségkezelés szakaszt.
17. Írjon be egy értéket a Költségcsoport mezőbe.
    * Ehhez a példához írja be a következőt: M1.  
18. A Művelet panelen kattintson a Költségkezelés elemre.
19. Kattintson a Cikk ára elemre.
20. Kattintson az Új lehetőségre.
21. A Verzió mezőben adjon meg vagy válasszon ki egy értéket.
    * Ehhez a példához válassza ki a következőt: 10. Ez az Elszámolóár költségszámítási típus.  
22. A Hely mezőben adjon meg vagy válasszon ki egy értéket.
    * Ehhez a példához válassza ki a következőt: 1. hely.  
23. Adjon meg egy számot az Ár mezőben.
    * Ehhez a példához írja be a következőt: 10.  
24. Kattintson a Mentés gombra.
25. Kattintson a Függő árak aktiválása lehetőségre.
26. Zárja be a lapot.
27. Zárja be a lapot.


