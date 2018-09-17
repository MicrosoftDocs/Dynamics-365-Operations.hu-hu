--- 
title: "Értékesítési jutalékok szabályainak beállítása"
description: "Ez az eljárás bemutatja, hogyan állíthatja be és engedélyezheti az értékesítési jutalékszámítást és követést."
author: omulvad
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CommissionCustomerGroup, CommissionItemGroup, CommissionSalesGroup, CommissionSalesMember, DirPartyLookup, CommissionCalc, InventPosting, CustTable, EcoResProductDetailsExtended
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 8d81765884f741443d1c0f5b0cb8bc545945e1a1
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-sales-commission-rules"></a>Értékesítési jutalékok szabályainak beállítása

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás bemutatja, hogyan állíthatja be és engedélyezheti az értékesítési jutalékszámítást és követést. Ez az eljárás bemutatja, hogy hozhat létre vevő és cikk típusú jutalékcsoportokat, és hogyan csatolhatja a kiválasztott vevőt és a terméket a megfelelő csoporthoz. Ezek a csoportok a jutalékszámítás beállításánál használatosak, vevő, cikk, és üzletkötő kombinációk létrehozásához, amelyeket értékesítési rendelésekhez kell kötni, hogy feljogosítsa az értékesítőket üzletkötésre. Vevő és cikk jutalékcsoportok létrehozása nem kötelező, mivel a jutalékszámítás egy vevőre és/vagy cikkre is elvégezhető. Ezt a folyamatot az USMF bemutatócéggel vagy saját adataival is futtathatja.


## <a name="set-up-commission-groups-and-commission-rates"></a>Jutalékcsoportok és jutalékarányok beállítása
1. Ugrás a Értékesítés és marketing > Jutalékok > Vevői csoportok jutalék lehetőségre.
2. Kattintson az Új lehetőségre.
3. Érték beírása a Csoport mezőbe.
4. Írjon be egy értéket a Név mezőbe.
5. Kattintson a Mentés gombra.
6. Zárja be a lapot.
7. Ugrás a Értékesítés és marketing > Jutalékok > Cikk csoportok lehetőségre.
8. Kattintson az Új lehetőségre.
9. Érték beírása a Csoport mezőbe.
10. Írjon be egy értéket a Név mezőbe.
11. Zárja be a lapot.
12. Ugrás a Értékesítés és marketing> Jutalékok > Érékesítési csoportok lehetőségre.
    * A Jutalék értékesítési csoportja a jutalékra jogosult üzletkötő beosztású alkalmazottakat határozza meg, ha a megfelelő értékesítési csoporthoz társított vevő bizonyos cikkeket vásárol.  
    * Az USMF bemutató vállalat adatai között szerepel egy „Üzletkötők Egyesül Államok” értékesítési csoport.  
13. A Művelet panelen kattintson az Általános elemre.
14. Kattintson az üzletkötő nevére.
    * Az üzletkötő lap megjeleníti azon vállalat értékesítési személyek listáját, akik egy adott jutalékcsoporttal társítva vannak. Ugyanahhoz a csoporthoz több értékesítő jutalékot rendelhet hozzá, és meghatározhatja a teljes jutalékdíj megfelelő részesedését százalékban kifejezve. Az összes alkalmazott közötti jutalékfelosztás nem haladhatja meg a 100 értéket.  
15. A listában jelölje meg a kiválasztott sort.
16. Kattintson a Szerkesztés lehetőségre.
17. Állítsa a jutalékfelosztásokat „50”-re.
18. Kattintson az Új lehetőségre.
19. A Név mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
20. Rekordok kereséséhez használja a gyorsszűrőt. Például szűkítsen a „Név” mezővel a „Susan Burk” szót beírva.
21. Kattintson a Kiválasztás lehetőségre.
22. Állítsa a jutalékfelosztásokat „50”-re.
23. Kattintson a Mentés gombra.
24. Ugrás a Értékesítés és marketing > Jutalékok > Jutalékszámítás lehetőségre.
    * A Jutalékszámítás oldalon meghatározhatja az alkalmazott által az értékesítési tranzakciókért kapott jutalékarányt, ha az tartalmazza a vevő és a termék előre beállított kombinációját. A jutalékarány beállításának részeként meg kell adnia a jutalékszámítás alapját, és hogy ez engedménnyel együtt, vagy engedmény nélkül legyen-e érvényes. Ha meg szeretné határozni, hogy mikor aktív a jutalékarány, megadhat érvényességi időtartamot.  
25. Kattintson az Új lehetőségre.
26. Válassza a „Csoport” lehetőséget a Cikk mezőben:
27. A Cikk-viszony mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
28. A listában keresse meg és válassza ki a korábban létrehozott csoportot.
29. A listában kattintson a kijelölt sorban lévő hivatkozásra.
30. A Vevőkód mezőben válassza ki a „Csoport” lehetőséget.
31. A(z) Vevőkapcsolat mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
32. A listában válassza ki a korábban beállított csoportot.
33. Az Üzletkötők kapcsolat mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
34. Keresse meg és jelölje ki a kívánt rekordot a listán.
    * A „Sorkedvezmény előtt” beállítás megtartása.  
    * A „Bevétel” beállítás megtartása a jutalékszámítás alapjául.    
35. Adjon meg egy számot a Jutalék (százalék) mezőben.
36. Kattintson a Mentés gombra.

## <a name="setting-up-commission-posting"></a>Jutalékfeladás beállítása
1. Ugrás az Értékesítés és marketing > Jutalékok > Jutalékfeladás lehetőségre.
    * A jutalékdíjak kifizethetőek az alkalmazottaknak, ezért be kell azokat állítani, a megfelelő pénzügyi feladások biztosítása érdekében, a Főkönyv megfelelő számláira. Ezt a Jutalék feladása lapon lehet intézni. Ellenőrizze a beállítást, amely az aktuális vállalathoz érhető el. A jutalék összegét általában egy külön költség számlára adja fel, és egy kijelölt fizethető számlával ellenszámlázott. Ha nem rendelkezik beállított jutalékfeladási szabályokkal, a rendszer nem tudja befejezni a jogosult jutalékokkal rendelkező értékesítési rendelés számlázását.  
2. Zárja be a lapot.

## <a name="assign-a-commission-group-to-a-customer-and-a-product"></a>Jutalékcsoport vevőhöz és termékhez rendelése.
1. Lépjen az Értékesítés és marketing > Vevők > Össze vevő menüpontba.
2. Keresse meg és jelölje ki a kívánt rekordot a listán.
3. A listában kattintson a kijelölt sorban lévő hivatkozásra.
4. Kattintson a Szerkesztés lehetőségre.
5. Bontsa ki az Értékesítési rendelés alapértelmezési szakaszt.
6. A Jutalékcsoport mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
7. A listában válassza ki a korábban létrehozott csoportot.
8. Az Értékesítési csoport mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
9. Keresse meg és jelölje ki a kívánt rekordot a listán.
10. Kattintson a Mentés gombra.
11. Kattintson a Termékinformációk kezelése > Termékek > Kiadott termékek lehetőségre.
12. Rekordok kereséséhez használja a gyorsszűrőt. Például szűkítsen a Cikkszám mezővel a „T0020” értéket beírva.
13. A listában kattintson a kijelölt sorban lévő hivatkozásra.
14. Kattintson a Szerkesztés lehetőségre.
15. Bontsa ki a Értékesítés szakaszt.
16. A Jutalékcsoport mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
17. A listában válassza ki a korábban létrehozott értékesítési csoportot.


