--- 
title: "Akkreditív importálása"
description: "Ez az eljárás bemutatja egy akkreditív importálásának folyamatát."
author: kweekley
manager: AnnBe
ms.date: 02/26/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 754b964f2bb70c1f81fa21d27c5374c594d006f7
ms.contentlocale: hu-hu
ms.lasthandoff: 07/27/2017

---
# <a name="import-a-letter-of-credit"></a>Akkreditív importálása

[!include[task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás bemutatja egy akkreditív importálásának folyamatát. Az eljárás végrehajtása előtt be kell állítani a következőket: banki hitelek, feladási profilok, egy banki hitelmegállapodás és szállító banki adatai.

Ez az eljárás az USMF bemutatócéget használja.


## <a name="create-a-purchase-order-with-letter-of-credit"></a>Beszerzési rendelés létrehozása akkreditívvel
1. Nyissa meg a következőt: Kötelezettségek > Beszerzési rendelések > Minden beszerzési rendelés.
2. Kattintson az Új lehetőségre.
3. A Szállítószámla mezőben adjon meg vagy válasszon ki egy értéket.
4. A kívánt rekord megkeresése és kijelölése a listán
5. A listában kattintson a kijelölt sorban lévő hivatkozásra.
6. Bontsa ki az Általános szakaszt.
7. A Hely mezőben adjon meg vagy válasszon ki egy értéket.
8. A listában kattintson a kijelölt sorban lévő hivatkozásra.
9. A Raktár mezőben adjon meg vagy válasszon ki egy értéket.
10. A listában kattintson a kijelölt sorban lévő hivatkozásra.
11. Adja meg a dátumot a Könyvelés dátuma mezőben.
12. Adjon meg egy dátumot a Kiszállítási dátum mezőben.
    * Megjegyzés: A „Banki okmány típusa” mezőnél az „Akkreditív” értéknek kell kiválasztva lennie.  
13. Kattintson az OK gombra.
14. Az Elemszám mezőben adjon meg, vagy válasszon ki egy értéket.
15. Keresse meg és jelölje ki a kívánt rekordot a listán.
16. A listában kattintson a kijelölt sorban lévő hivatkozásra.
17. A Sorrészletek szakasz kibontása.
18. Kattintson a Kiszállítás fülre.
19. Adjon meg egy dátumot a Kiszállítási dátum mezőben.
20. Adjon meg egy dátumot a Visszaigazolt szállítási dátum mezőben.
21. Adjon meg egy számot az Egységár mezőben.
    * Adja meg az Akkreditív adatait.  
22. A Művelet panelen kattintson a Kezelés elemre.
23. Kattintson az Akkreditív / importbeszedvény lehetőségre.
24. Az Alkalmazás dátuma mezőben adjon meg egy dátumot és időpontot.
    * Győződjön meg róla, hogy a „Bankszámla” mezőben az alapértelmezett aktív Bankszámla szerepel, az alkalmazás dátuma alapján.  
25. A Banki okmány száma mezőben adjon meg egy értéket.
26. A Kézhezvétel dátuma mezőben adjon meg egy dátumot és időpontot.
27. Bontsa ki a A banki bizonylat szakaszt.
28. Az Lejárati dátum mezőben adjon meg egy dátumot és időpontot.
29. Bontsa ki a Bank részletei szakaszt.
30. Az Értesítő bank mezőben adjon meg vagy válasszon ki egy értéket.
31. A listában kattintson a kijelölt sorban lévő hivatkozásra.
32. Kattintson a Mentés gombra.
33. Kattintson a Beszerzési rendelés szállítmányainak beolvasása lehetőségre.
34. Zárja be a lapot.
35. A Művelet panelen kattintson a Beszerzés elemre.
36. Kattintson a Megerősítés gombra.
37. A Művelet panelen kattintson a Kezelés elemre.
38. Kattintson az Akkreditív / importbeszedvény lehetőségre.
39. Kattintson a Folyamat gombra.
40. Kattintson a Megerősítés gombra.
    * Győződjön meg róla, hogy a Hitel egyenlege levonja a beszerzési rendelés összegét.  Ebben a példában a Beszerzési összeg = 500,00, a Hitelmegállapodás határértéke = 10000,00, tehát a Hitel egyenlege = 9500,00.  
41. Zárja be a lapot.
42. Adjon meg egy számot az Egységár mezőben.
43. Kattintson a Mentés gombra.
44. A Művelet panelen kattintson a Beszerzés elemre.
45. Kattintson a Megerősítés gombra.
    * Az Akkreditív módosítása Egységárban bekövetkező változás miatt.  
46. A Művelet panelen kattintson a Kezelés elemre.
47. Kattintson az Akkreditív / importbeszedvény lehetőségre.
    * Az Akkreditív módosítása Beszerzési árban bekövetkező változás miatt.  
48. Kattintson a Folyamat gombra.
49. Kattintson a Módosítás gombra.
50. Kattintson az Eltávolítás gombra.
51. Kattintson az Igen gombra.
52. Kattintson a Beszerzési rendelés szállítmányainak beolvasása lehetőségre.
53. Kattintson a Folyamat gombra.
54. Kattintson a Megerősítés gombra.
    * Győződjön meg róla, hogy a Hitel egyenlege levonja a beszerzési rendelés összegét.  Ebben a példában a szerkesztett Beszerzési összeg = 600,00, a Hitelmegállapodás határértéke = 10000,00, tehát a Hitel egyenlege = 9400,00.  
55. Zárja be a lapot.

## <a name="post-packing-slip"></a>Szállítólevél feladása
1. A Művelet panelen kattintson a Bevételezés elemre.
2. Kattintson a Termékbevételezés elemre.
3. Írjon be egy értéket a PurchParmTable_Num mezőbe.
    * Válassza ki a az Akkreditívre való hivatkozással létrehozott Szállítmányszámot.  
4. A listában kattintson a kijelölt sorban lévő hivatkozásra.
5. Adjon meg egy dátumot a Termékbevételezési dátum mezőben.
6. Kattintson az OK gombra.
7. Zárja be a lapot.
8. Zárja be a lapot.

## <a name="verify-import-letter-of-credit-status"></a>Ellenőrizze az Importakkreditív állapotát.
1. Ugorjon a Készpénz- és bankkezelés > Akkreditívek > Importakkreditív és importbeszedvény pontra.
2. Keresse meg és jelölje ki a kívánt rekordot a listán.
3. A listában kattintson a kijelölt sorban lévő hivatkozásra.
    * Ellenőrizze az Importakkreditív állapotát.  
4. Zárja be a lapot.
5. Zárja be a lapot.

## <a name="post-purchase-invoice"></a>Beszerzési számla feladása
1. Nyissa meg a következőt: Kötelezettségek > Beszerzési rendelések > Minden beszerzési rendelés.
    * Válassza ki az akkreditívvel létrehozott beszerzési rendelést.  
2. Keresse meg és jelölje ki a kívánt rekordot a listán.
3. A listában kattintson a kijelölt sorban lévő hivatkozásra.
4. A Művelet panelen kattintson a Számla lehetőségre.
5. Kattintson a Számlára.
6. Érték beírása a Szám mezőbe.
7. A Szállítmányszám mezőben adjon meg, vagy válasszon ki egy értéket.
8. A listában kattintson a kijelölt sorban lévő hivatkozásra.
9. A Számla dátuma mezőben adjon meg egy dátumot.
10. Kattintson az Egyeztetési állapot frissítése lehetőségre.
11. Kattintson a Feladás lehetőségre.
12. Zárja be a lapot.
13. Zárja be a lapot.

## <a name="verify-import-letter-of-credit-status"></a>Ellenőrizze az Importakkreditív állapotát.
1. Ugorjon a Készpénz- és bankkezelés > Akkreditívek > Importakkreditív és importbeszedvény pontra.
2. Keresse meg és jelölje ki a kívánt rekordot a listán.
3. A listában kattintson a kijelölt sorban lévő hivatkozásra.
    * Ellenőrizze az Importakkreditív2 állapotát.  
    * Ellenőrzés : Szállítmány állapota = Számlázva Banki hitelmegállapodás részletei  
4. Kattintson a Megtekintés menüpontra.
5. Kattintson az Igénylés nyomtatása gombra.
6. Kattintson az OK gombra.
    * Győződjön meg róla, hogy az Akkreditívigénylés nyomtatása megtörténik.  
7. Zárja be a lapot.
8. Zárja be a lapot.
9. Zárja be a lapot.

## <a name="post-vendor-payment-journal-for-the-created-purchase-invoice-with-letter-of-credit"></a>Az akreditívvel létrehozott beszerzési számlára vonatkozó Szállító kifizetési napló feladása
1. Ugorjon a Kötelezettségek > Fizetési beállítás > Fizetési napló pontra.
2. Kattintson az Új lehetőségre.
3. A Név mezőben adjon meg vagy válasszon ki egy értéket.
4. A listában kattintson a kijelölt sorban lévő hivatkozásra.
5. Kattintson a Sorok pontra.
6. Adja meg a dátumot a Dátum mezőben.
7. A Számla mezőben adja meg a kívánt értékeket.
8. Kattintson a Tranzakcióinak kiegyenlítése gombra.
9. Bontsa ki az Összegek szakaszt.
10. Válasszon ki egy lehetőséget a Megjelenítés mezőben.
    * Győződjön meg róla, hogy a Banki okmány száma és a Szállítmányszám mezőket frissítették.  
11. Jelölje be a Megjelölve jelölőnégyzetet.
12. Kattintson az OK gombra.
13. Kattintson a Fizetések fülre.
    * Győződjön meg róla, hogy a Banki okmány száma és a Szállítmányszám mezőket frissítették.  
14. Kattintson a Feladás lehetőségre.
15. Zárja be a lapot.
16. Zárja be a lapot.

## <a name="verify-import-letter-of-credit-status-after-invoice-paid"></a>Az Importakkreditív állapotának ellenőrzése a Számla kifizetése után
1. Ugorjon a Készpénz- és bankkezelés > Akkreditívek > Importakkreditív és importbeszedvény pontra.
2. Keresse meg és jelölje ki a kívánt rekordot a listán.
3. A listában kattintson a kijelölt sorban lévő hivatkozásra.
    * Ellenőrizze az Importakkreditív állapotát.   
4. Zárja be a lapot.

## <a name="verify-the-bank-facility-limit-and-utilization-report"></a>Banki hitelmegállapodás korlát és a terheléskihasználtsági jelentés ellenőrzése
1. Ugorjon a Készpénz- és bankkezelés > Lekérdezések és jelentések > Akkreditívek vagy garancialevél > Banki hitelek és kihasználtságuk – jelentés pontra.
2. Bontsa ki a Szerepeltetni kívánt rekordok szakaszt.
3. Kattintson a Szűrő parancsra.
    * A Feltételek mezőben adja meg a szükséges bankszámlát.  
4. A Feltétel mezőben adjon meg vagy válasszon ki egy értéket.
5. A listában kattintson a kijelölt sorban lévő hivatkozásra.
6. Kattintson az OK gombra.
7. Kattintson az OK gombra.
    * Ellenőrizze a tranzakciókat felsoroló jelentést.  
    * Győződjön meg róla, hogy a jelentés felsorolja a tranzakciókat a Banki okmány számával, a Hitelmegállapodás határértékével, a felhasznált összeggel és a hitel egyenlegének összegével együtt.  
8. Zárja be a lapot.


