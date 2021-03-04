---
title: Értékesítési jutalékok szabályainak beállítása
description: Ez az eljárás bemutatja, hogyan állíthatja be és engedélyezheti az értékesítési jutalékszámítást és követést.
author: omulvad
manager: tfehr
ms.date: 06/21/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CommissionCustomerGroup, CommissionItemGroup, CommissionSalesGroup, CommissionSalesMember, DirPartyLookup, CommissionCalc, InventPosting, CustTable, EcoResProductDetailsExtended, CommissionEmplSalesGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2b1ea016817462269a13e450c8c7576546c7f0eb
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4429443"
---
# <a name="set-up-sales-commission-rules"></a>Értékesítési jutalékok szabályainak beállítása

[!include [banner](../../includes/banner.md)]

Ez az eljárás bemutatja, hogyan állíthatja be és engedélyezheti az értékesítési jutalékszámítást és követést. Ez az eljárás bemutatja, hogy hozhat létre vevő és cikk típusú jutalékcsoportokat, és hogyan csatolhatja a kiválasztott vevőt és a terméket a megfelelő csoporthoz. Ezek a csoportok a jutalékszámítás beállításánál használatosak, vevő, cikk, és üzletkötő kombinációk létrehozásához, amelyeket értékesítési rendelésekhez kell kötni, hogy feljogosítsa az értékesítőket üzletkötésre. Vevő és cikk jutalékcsoportok létrehozása nem kötelező, mivel a jutalékszámítás egy vevőre és/vagy cikkre is elvégezhető. Ezt a folyamatot az USMF bemutatócéggel vagy saját adataival is futtathatja.


## <a name="set-up-commission-groups-and-commission-rates"></a>Jutalékcsoportok és jutalékarányok beállítása
1. Lépjen a következőhöz: **Navigációs ablaktábla > Modulok > Értékesítés és marketing > Jutalékok > Vevői csoportok jutalékhoz**.
2. Válassza az **Új** lehetőséget.
3. A **Csoport** mezőben adjon meg egy értéket.
4. Írjon be egy értéket a **Név** mezőbe.
5. Válassza a **Mentés** lehetőséget.
6. Zárja be a lapot.
7. Lépjen a következőhöz: **Navigációs ablaktábla > Modulok > Értékesítés és marketing > Jutalékok > Cikkcsoportok**.
8. Válassza az **Új** lehetőséget.
9. A **Csoport** mezőben adjon meg egy értéket.
10. Írjon be egy értéket a **Név** mezőbe.
11. Válassza a **Mentés** lehetőséget.
12. Zárja be a lapot.
13. Ugrás a **Értékesítés és marketing> Jutalékok > Érékesítési csoportok** lehetőségre.
    - A Jutalék értékesítési csoportja a jutalékra jogosult üzletkötő beosztású alkalmazottakat határozza meg, ha a megfelelő értékesítési csoporthoz társított vevő bizonyos cikkeket vásárol.  
    - Az USMF bemutató vállalat adatai között szerepel egy „Üzletkötők Egyesül Államok” értékesítési csoport.  
14. A **Műveleti ablaktáblán** válassza ki az **Általános** elemet.
15. Kattintson az **Üzletkötő** elemre. Az üzletkötő lap megjeleníti azon vállalat értékesítési személyek listáját, akik egy adott jutalékcsoporttal társítva vannak. Ugyanahhoz a csoporthoz több értékesítő jutalékot rendelhet hozzá, és meghatározhatja a teljes jutalékdíj megfelelő részesedését százalékban kifejezve. Az összes alkalmazott közötti jutalékfelosztás nem haladhatja meg a 100 értéket. 
16. A listában jelölje meg a kiválasztott sort.
17. Válassza ki a **Szerkesztés** opciót.
18. Állítsa a **Jutalékfelosztás** értékét „50”-re.
19. Kattintson az **Új** elemre.
20. A **Név** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
21. Rekordok kereséséhez használja a **Gyorsszűrőt**. Például szűkítsen a „Név” mezővel a „Susan Burk” szót beírva.
22. Kattintson a **Kiválasztás** lehetőségre.
23. Állítsa a **Jutalékfelosztás** értékét „50”-re.
24. Kattintson a **Mentés** gombra.
25. Lépjen az **Értékesítés és marketing > Jutalékok > Jutalékszámítás** lehetőségre. A **Jutalékszámítás** oldalon meghatározhatja az alkalmazott által az értékesítési tranzakciókért kapott jutalékarányt, ha az tartalmazza a vevő és a termék előre beállított kombinációját. A jutalékarány beállításának részeként meg kell adnia a jutalékszámítás alapját, és hogy ez engedménnyel együtt, vagy engedmény nélkül legyen-e érvényes. Ha meg szeretné határozni, hogy mikor aktív a jutalékarány, megadhat érvényességi időtartamot.  
26. Kattintson az **Új** elemre.
27. Válassza ki a „Csoport” lehetőséget a **Cikk kódja** mezőben.
28. A **Cikk-viszony** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
29. A listában keresse meg és válassza ki a korábban létrehozott csoportot.
30. A **Vevőkód** mezőben válassza ki a „Csoport” lehetőséget.
31. A **Vevőkapcsolat** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
32. A listában válassza ki a korábban beállított csoportot.
33. Az **Üzletkötők kapcsolata** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
34. Keresse meg és jelölje ki a kívánt rekordot a listán.
    - A „Sorkedvezmény előtt” beállítás megtartása.  
    - A „Bevétel” beállítás megtartása a jutalékszámítás alapjául.    
35. Adjon meg egy számot a Jutalék (százalék) mezőben.
36. Kattintson a **Mentés** gombra.

## <a name="setting-up-commission-posting"></a>Jutalékfeladás beállítása
1. Lépjen a következőhöz: **Navigációs ablaktábla > Értékesítés és marketing > Jutalékok > Jutalékfeladás**. A jutalékdíjak kifizethetőek az alkalmazottaknak, ezért be kell azokat állítani, a megfelelő pénzügyi feladások biztosítása érdekében, a **Főkönyv** megfelelő számláira. Ezt a **Jutalékfeladás** lapon lehet intézni. Ellenőrizze a beállítást, amely az aktuális vállalathoz érhető el. A jutalék összegét általában egy külön költség számlára adja fel, és egy kijelölt fizethető számlával ellenszámlázott. Ha nem rendelkezik beállított jutalékfeladási szabályokkal, a rendszer nem tudja befejezni a jogosult jutalékokkal rendelkező értékesítési rendelés számlázását.  
2. Zárja be a lapot.

## <a name="assign-a-commission-group-to-a-customer-and-a-product"></a>Jutalékcsoport vevőhöz és termékhez rendelése.
1. Lépjen a **Navigációs panel > Modulok > Értékesítés és marketing > Ügyfelek > Összes ügyfél** menüpontba.
2. Keresse meg és jelölje ki a kívánt rekordot a listán.
3. A listában kattintson a kijelölt sorban lévő hivatkozásra.
4. Kattintson a **Szerkesztés** lehetőségre.
5. Bontsa ki az **Értékesítési rendelés alapértelmezései** szakaszt.
6. A **Jutalékcsoport** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
7. A listában válassza ki a korábban létrehozott csoportot.
8. Az **Értékesítési csoport** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
9. Keresse meg és jelölje ki a kívánt rekordot a listán.
10. Kattintson a **Mentés** gombra.
11. Kattintson ide: **Navigációs ablaktábla > Modulok > Termékinformációk kezelése > Termékek > Kiadott termékek**.
12. Rekordok kereséséhez használja a **Szűrőt**. Például szűkítsen a Cikkszám mezővel a „T0020” értéket beírva.
13. A listában kattintson a kijelölt sorban lévő hivatkozásra.
14. Kattintson a **Szerkesztés** lehetőségre.
15. Bontsa ki a **Értékesítés** szakaszt.
16. A **Jutalékcsoport** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
17. A listában válassza ki a korábban létrehozott értékesítési csoportot.
18. Válassza a **Mentés** lehetőséget.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]