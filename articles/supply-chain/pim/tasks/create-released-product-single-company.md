--- 
title: "Kiadott termék létrehozása egyetlen vállalat részére"
description: "Ez az eljárás végigvezeti egyetlen kiadott termék létrehozásán egy legális egységgel összefüggésben."
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResProductDetailsExtended, EcoResProductCreate, UnitOfMeasureLookup, DimensionLookup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 042eafc29e377e0ad6fb8dc1499daf8eb105b7ed
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-released-product-for-a-single-company"></a>Kiadott termék létrehozása egyetlen vállalat részére

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás végigvezeti egyetlen kiadott termék létrehozásán egy legális egységgel összefüggésben. A kiadott termék létrehozása után az azonnal csak ebben az egységben elérhető. Ezt a folyamatot lefuttathatja az USMF bemutatócégen. Ezt a feladatot általában egy terméktervező végzi el.


## <a name="create-a-released-product"></a>Kiadott termék létrehozása
1. Ugrás a Kiadott termékek elemre.
2. Kattintson az Új lehetőségre.
3. Írjon be egy értéket a Termékszám mezőbe.
    * Ha termékszám automatikusan nem kerül bele a Termékszám mezőbe, írjon be egy egyedi termékszámot. Ez a lépés csak akkor szükséges, ha nem lett számsorozat beállítva a termékszámokhoz.  
4. Írjon be egy értéket a Terméknév mezőbe.
    * A Termék neve alapértelmezés szerint a keresési névből származik. Ha szükséges, a keresési nevet módosíthatja.  
5. A Cikkmodellcsoport mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
    * A cikkmodell csoportok olyan beállításokat tartalmaznak, amelyek meghatározzák, hogy a rendszer hogyan kezelje a cikkeket a cikkbevételezéseknél és -kiadásoknál. A beállítások azt is megszabják, hogy a rendszer hogyan számítsa ki a cikkek fogyasztását.  
6. Keresse meg és jelölje ki a kívánt rekordot a listán.
7. A listában kattintson a kijelölt sorban lévő hivatkozásra.
8. A Cikkcsoport mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
    * A cikkcsoportok segítségével a cikkjellemzők szerint csoportosítva kezelheti a készletet. Például, az adatoknak a fő számlák felé történő feladásának módjának kezeléséhez létrehozhat egy sor különböző cikkcsoportot, amely egy adott fő számlához tartozik. Ennek segítségével nyomon követhetők a cikkek készletértéke azok különböző szakaszában.  
9. Keresse meg és jelölje ki a kívánt rekordot a listán.
10. A listában kattintson a kijelölt sorban lévő hivatkozásra.
11. A Tárolási dimenzió csoport mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
    * A tárolási dimenziók segítenek a cikkek raktárban való tárolásának és raktárból való kivételének szabályozásában. Például a tárolási dimenzió lehet a Hely és a Raktár.  
12. Keresse meg és jelölje ki a kívánt rekordot a listán.
13. A listában kattintson a kijelölt sorban lévő hivatkozásra.
14. A Nyomon követési dimenzió csoport mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
    * A nyomon követési dimenziócsoport meghatározza, hogy mely nyomon követési dimenziókat adhatja hozzá egy termékhez. Például a kötegszám, és a sorozatszám is használható a készletcikkek nyomon követésére.  
15. Keresse meg és jelölje ki a kívánt rekordot a listán.
16. A listában kattintson a kijelölt sorban lévő hivatkozásra.
17. A Készletegység mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
    * A készletegység határozza meg, hogy egy termék mennyisége milyen módon van megadva annak készleten való tárolásakor.  
18. Keresse meg és jelölje ki a kívánt rekordot a listán.
19. A listában kattintson a kijelölt sorban lévő hivatkozásra.
20. A Beszerzési egység mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
    * A beszerzési egység meghatározza, hogy egy termék mennyisége milyen módon van megadva, amikor az megvételre kerül egy szállítótól.  
21. Keresse meg és jelölje ki a kívánt rekordot a listán.
22. A listában kattintson a kijelölt sorban lévő hivatkozásra.
23. Az Értékesítési egység mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
    * Az értékesítési egység meghatározza, hogy egy termék mennyisége milyen módon van megadva, amikor az eladásra kerül egy ügyfél számára.  
24. Keresse meg és jelölje ki a kívánt rekordot a listán.
25. A listában kattintson a kijelölt sorban lévő hivatkozásra.
26. Az Anyagjegyzékegység mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
    * Az anyagjegyzékegység határozza meg, hogy egy termék mennyisége milyen módon van megadva, amikor az hozzáadásra kerül egy anyagjegyzékhez.  
27. Keresse meg és jelölje ki a kívánt rekordot a listán.
28. A listában kattintson a kijelölt sorban lévő hivatkozásra.
29. A Cikkáfacsoport mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
    * Az Értékesítési áfacsoporton belüli cikkáfacsoport határozza meg, hogy az adott elemekhez milyen módon kerüljön kiszámításra a forgalmi adó.  
30. Keresse meg és jelölje ki a kívánt rekordot a listán.
31. A listában kattintson a kijelölt sorban lévő hivatkozásra.
32. A Cikkáfacsoport mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
    * A Beszerzési áfacsoporton belüli cikkáfacsoport határozza meg, hogy az adott elemekhez milyen módon kerüljön kiszámításra a beszerzési adó.  
33. Keresse meg és jelölje ki a kívánt rekordot a listán.
34. A listában kattintson a kijelölt sorban lévő hivatkozásra.
35. Kattintson az OK gombra.

## <a name="add-product-characteristics"></a>Termékjellemzők megadása
1. Bontsa ki vagy csukja össze a Készletkezelés szakaszt.
2. Adjon meg egy számot a Nettó tömeg mezőben.
3. Adjon meg egy számot a Tárasúly mezőben.
4. Adjon meg egy számot a Bruttó mélység mezőben.
5. Adjon meg egy számot a Bruttó szélesség mezőben.
6. Adjon meg egy számot a Bruttó magasság mezőben.
7. A Térfogat mezőben adjon meg egy számot.

## <a name="add-financial-dimensions"></a>Pénzügyi dimenziók hozzáadása
1. Bontsa ki vagy csukja össze a Pénzügyi dimenziók szakaszt.
2. A BusinessUnit mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
3. A kívánt rekord megkeresése és kijelölése a listán
4. A listában kattintson a kijelölt sorban lévő hivatkozásra.
5. A CostCenter mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
6. A kívánt rekord megkeresése és kijelölése a listán
7. A listában kattintson a kijelölt sorban lévő hivatkozásra.
8. A Részleg mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
9. A kívánt rekord megkeresése és kijelölése a listán
10. A listában kattintson a kijelölt sorban lévő hivatkozásra.
11. Az ItemGroup mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
12. A kívánt rekord megkeresése és kijelölése a listán
13. A listában kattintson a kijelölt sorban lévő hivatkozásra.


