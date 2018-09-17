--- 
title: "Beszerzési rendelés létrehozása értékesítési rendelésből"
description: "Ez az eljárás bemutatja, hogyan hozhat létre egy beszerzési rendelést egy értékesítési rendelés alapján."
author: omulvad
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, PurchCreateFromSalesOrder, VendAccountItemLookup, SalesTableReferences, PurchTable
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 412a8c7acca06fc1be073019f91144e2a3f1c94b
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-purchase-order-from-a-sales-order"></a>Beszerzési rendelés létrehozása értékesítési rendelésből

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás bemutatja, hogyan hozhat létre egy beszerzési rendelést egy értékesítési rendelés alapján. A termékmennyiségek a beszerzési rendelésen ezután az eredeti értékesítési rendelés az igényének a kielégítésére lesznek kijelölve. Az értékesítési rendelések ilyen módon történő teljesítése egy alternatívája egy átfogóbb és optimalizáltabb elosztási követelmény tervezési módnak. Ezt a folyamatot az USMF bemutatócéggel vagy saját adataival is futtathatja.


## <a name="create-a-purchase-order-from-a-sales-order"></a>Beszerzési rendelés létrehozása értékesítési rendelésből
1. Lépjen az Értékesítés és marketing > Értékesítési rendelések > Minden értékesítési rendelés menüpontba.
2. Kattintson az Új lehetőségre.
3. A Vevői számla mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
4. A kívánt rekord megkeresése és kijelölése a listán
5. Kattintson az OK gombra.
6. A Cikkszám mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
7. Keresse meg és jelölje ki a kívánt rekordot a listán.
    * Az USMF használata esetén választhatja a D0001 lehetőséget.  
8. Adjon meg egy számot a Mennyiség mezőben.
9. Kattintson az Új sor hozzáadása lehetőségre.
10. A Cikkszám mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
11. Keresse meg és jelölje ki a kívánt rekordot a listán.
    * Az USMF használata esetén választhatja a T0020 lehetőséget.  
12. A listában kattintson a kijelölt sorban lévő hivatkozásra.
13. Adjon meg egy számot a Mennyiség mezőben.
14. Kattintson a Mentés gombra.
15. A Művelet panelen kattintson az Értékesítési rendelés elemre.
16. Kattintson a Beszerzési rendelés lehetőségre.
    * A Beszerzési rendelés létrehozása lap felsorolja az összes nyitott értékesítésirendelés-sort az értékesítési rendelésből másolva. Áttekintheti a rendelési részleteket, és ha szükséges módosíthatja az olyan kiválasztott részleteket, mint a beszerzési mennyiség és az árképzési feltételek a beszerzések létrehozása előtt.  
17. Válassza ki az Összes belefoglalása lehetőséget.
    * Ha az értékesítésirendelés-soroknak csupán egy részhalmazához szeretne közvetlen beszerzési rendeléseket létrehozni, akkor ezeket egyenként válassza ki.  
    * A Szállítószámla mező ekkor lehet üres, de akár már szerepelhet is benne egy szállítószám. Ha van alapértelmezett szállítói beállítva a termékhez (a kapcsolódó cikkfedezetnél), akkor az ez a szállító be lesz másolva a sorba. Ellenkező esetben a szállítót manuálisan kell megadni.  Ebben az útmutatóban a következő lépések utasításai szerint ki kell választani egy eltérő szállítót minden sor esetében függetlenül attól, hogy a Szállítószámla mező tartalmaz-e már értéket vagy nem.  
18. A Szállítói számla mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
19. A kívánt rekord megkeresése és kijelölése a listán
20. A listában kattintson a kijelölt sorban lévő hivatkozásra.
21. Válassza ki a második rendeléssort.
22. A Szállítói számla mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
23. A kívánt rekord megkeresése és kijelölése a listán
24. A listában kattintson a kijelölt sorban lévő hivatkozásra.
25. Kattintson az Érvényesítés gombra.
26. Kattintson az OK gombra.
    * Az üzenet tájékoztat arról, hogy egy vagy több beszerzési rendelés létrehozása megtörtént. A kiválasztott értékesítésirendelés-sorokhoz beállított minden egyes szállítókhoz a rendszer külön beszerzési rendeléseket hoz létre. Ez azt jelenti, hogy ha ugyanaz a szállító több értékesítésirendelés-sor esetén is, akkor egy darab, többsoros beszerzési rendelés fog létrejönni.  

## <a name="review-purchase-orders-created-from-sales-orders"></a>Értékesítési rendelésekből létrehozott beszerzési rendelések áttekintése
1. A Művelet panelen kattintson az Általános elemre.
2. Kattintson a Kapcsolódó rendelések lehetőségre.
    * A Kapcsolódó rendelések lap felsorolja az értékesítési rendelésből létrehozott összes rendelést. Ebben a példában a program két beszerzési rendelés hoz létre két különböző szállítóhoz.  
3. Kattintson a Beszerzési rendelés mezőben található hivatkozásra.
    * Minden beszerzésirendelés-sor társítva van az értékesítésirendelés-sorhoz, amely a beszerzéshez vezetett. Az értékesítési rendeléshez való viszony a Termék lapon van feltüntetve a Sorrészletek gyorslapon, a Hivatkozás típusa, a Hivatkozási szám és a Referenciatétel mezőkben.  
4. Bontsa ki vagy csukja össze a Soradatok szakaszt.
5. Kattintson a Termék fülre.
    * A referenciatétel biztosítja, hogy az aktuális beszerzés költségei terhelésként jelennek meg a csatolt értékesítési rendelésen.  
    * A Hivatkozási szám mezőben található hivatkozást megnyitva navigálhat az eredeti értékesítési rendeléshez.  


