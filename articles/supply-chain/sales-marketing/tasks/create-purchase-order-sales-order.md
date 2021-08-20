---
title: Beszerzési rendelés létrehozása értékesítési rendelésből
description: Ez az eljárás bemutatja, hogyan hozhat létre egy beszerzési rendelést egy értékesítési rendelés alapján.
author: omulvad
ms.date: 06/26/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, PurchCreateFromSalesOrder, VendAccountItemLookup, SalesTableReferences, PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 00bd0677113f0029732023dd84fcb1b9bf58648d5611000a3d95376c7d9131e6
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6781830"
---
# <a name="create-a-purchase-order-from-a-sales-order"></a>Beszerzési rendelés létrehozása értékesítési rendelésből

[!include [banner](../../includes/banner.md)]

Ez az eljárás bemutatja, hogyan hozhat létre egy beszerzési rendelést egy értékesítési rendelés alapján. A termékmennyiségek a beszerzési rendelésen ezután az eredeti értékesítési rendelés az igényének a kielégítésére lesznek kijelölve. Az értékesítési rendelések ilyen módon történő teljesítése egy alternatívája egy átfogóbb és optimalizáltabb elosztási követelmény tervezési módnak. Ezt a folyamatot az USMF bemutatócéggel vagy saját adataival is futtathatja.


## <a name="create-a-purchase-order-from-a-sales-order"></a>Beszerzési rendelés létrehozása értékesítési rendelésből
1. Ugorjon az **Navigációs lap > Modulok > Értékesítés és marketing > Értékesítési rendelések > Minden értékesítési rendelés** pontra.
2. Kattintson az **Új** elemre.
3. A **Vevői számla** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
4. A kívánt rekord megkeresése és kijelölése a listán
5. Kattintson az **OK** gombra.
6. A **Cikkszám** mezőben kattintson a legördülő gombra a keresés megnyitásához.
7. Keresse meg és jelölje ki a kívánt rekordot a listán. Az USMF használata esetén választhatja a D0001 lehetőséget.  
8. Adjon meg egy számot a **Mennyiség** mezőben.
9. Kattintson az **Új sor hozzáadása** elemre.
10. A **Cikkszám** mezőben kattintson a legördülő gombra a keresés megnyitásához.
11. Keresse meg és jelölje ki a kívánt rekordot a listán. Az USMF használata esetén választhatja a T0020 lehetőséget.  
12. A listában kattintson a kijelölt sorban lévő hivatkozásra.
13. Adjon meg egy számot a **Mennyiség** mezőben.
14. Kattintson a **Mentés** gombra.
15. A **Művelet panelen** kattintson az **Értékesítési rendelés** elemre.
16. Kattintson a **Beszerzési rendelés** lehetőségre. A **Beszerzési rendelés létrehozása** lap felsorolja az összes nyitott értékesítésirendelés-sort az értékesítési rendelésből másolva. Áttekintheti a rendelési részleteket, és ha szükséges módosíthatja az olyan kiválasztott részleteket, mint a beszerzési mennyiség és az árképzési feltételek a beszerzések létrehozása előtt. 
17. Válassza ki az **Összes belefoglalása** lehetőséget.
    - Ha az értékesítésirendelés-soroknak csupán egy részhalmazához szeretne közvetlen beszerzési rendeléseket létrehozni, akkor ezeket egyenként válassza ki.  
    - A **Szállítószámla** mező ekkor lehet üres, de szerepelhet is benne egy szállítószám. Ha van alapértelmezett szállítói beállítva a termékhez (a kapcsolódó cikkfedezetnél), akkor az ez a szállító be lesz másolva a sorba. Ellenkező esetben a szállítót manuálisan kell megadni.  Ebben az útmutatóban a következő lépések utasításai szerint ki kell választani egy eltérő szállítót minden sor esetében függetlenül attól, hogy a **Szállítói számla** mező tartalmaz-e már értéket vagy nem.  
18. A **Szállítói számla** mezőben kattintson a legördülő gombra a keresés megnyitásához.
19. A kívánt rekord megkeresése és kijelölése a listán
20. A listában kattintson a kijelölt sorban lévő hivatkozásra.
21. Válassza ki a második rendeléssort.
22. A **Szállítói számla** mezőben kattintson a legördülő gombra a keresés megnyitásához.
23. A kívánt rekord megkeresése és kijelölése a listán
24. A listában kattintson a kijelölt sorban lévő hivatkozásra.
25. Kattintson az **Érvényesítés** gombra.
26. Kattintson az **OK** gombra. Az üzenet tájékoztat arról, hogy egy vagy több beszerzési rendelés létrehozása megtörtént. A kiválasztott értékesítésirendelés-sorokhoz beállított minden egyes szállítókhoz a rendszer külön beszerzési rendeléseket hoz létre. Ez azt jelenti, hogy ha ugyanaz a szállító több értékesítésirendelés-sor esetén is, akkor egy darab, többsoros beszerzési rendelés fog létrejönni.  

## <a name="review-purchase-orders-created-from-sales-orders"></a>Értékesítési rendelésekből létrehozott beszerzési rendelések áttekintése
1. A **Művelet panelen** kattintson az **Általános** elemre.
2. Kattintson a **Kapcsolódó rendelések** lehetőségre. A **Kapcsolódó rendelések** lap felsorolja az értékesítési rendelésből létrehozott összes rendelést. Ebben a példában a program két beszerzési rendelés hoz létre két különböző szállítóhoz. 
3. Kattintson a **Beszerzési rendelés** mezőben található hivatkozásra. Minden beszerzésirendelés-sor társítva van az értékesítésirendelés-sorhoz, amely a beszerzéshez vezetett. Az értékesítési rendeléshez való viszony a **Termék lapon** van feltüntetve a **Sorrészletek** gyorslapon, a **Hivatkozás típusa**, a **Hivatkozási szám** és a **Referenciatétel** mezőkben.  
4. Bontsa ki vagy csukja össze a **Soradatok** szakaszt.
5. Kattintson a **Termék** fülre.
    - A **Referenciatétel** biztosítja, hogy az aktuális beszerzés költségei terhelésként jelennek meg a csatolt értékesítési rendelésen.  
    - A **Hivatkozási szám** mezőben található hivatkozást megnyitva navigálhat az eredeti értékesítési rendeléshez.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]