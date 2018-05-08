--- 
title: "Fő számlaadatok a kötelezettségekbe egy szállítói számla használatával"
description: "Ez a feladat-útmutató segít Önnek szállítói számla létrehozásában egy beszerzési rendelésből, valamint a beszerzési rendelés, nyugta és számla egyeztetési eredményeinek megtekintésében (háromirányú egyeztetés)."
author: abruer
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 48535a283cbdfdc7343a20105b139c527cac85f4
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="key-invoice-data-into-accounts-payable-using-a-vendor-invoice"></a>Fő számlaadatok a kötelezettségekbe egy szállítói számla használatával

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ez a feladat-útmutató segít Önnek szállítói számla létrehozásában egy beszerzési rendelésből, valamint a beszerzési rendelés, nyugta és számla egyeztetési eredményeinek megtekintésében (háromirányú egyeztetés).


## <a name="create-a-purchase-order"></a>Beszerzési rendelés létrehozása
1. Nyissa meg a következőt: Kötelezettségek > Beszerzési rendelések > Minden beszerzési rendelés.
2. Kattintson az Új lehetőségre.
3. A Szállítói számla mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
4. Keressen egy szállítót. Például görgessen le a US-104 lehetőségre.
5. US-104 szállító kiválasztása.
6. Kattintson az OK gombra.
7. A Cikkszám mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
8. Készletcikk kiválasztása. Példábul válassza ki az 1000 cikkszámot.
9. Bontsa ki vagy csukja össze a Soradatok szakaszt.
10. Kattintson a Beállítás fülre.
    * Felülírhatja az egyeztetési irányelvet egyeztetés nélkülire, kétirányú egyeztetésre vagy háromirányú egyeztetésre.  
11. Bontsa ki vagy csukja össze a Soradatok szakaszt.
12. A Művelet panelen kattintson a Beszerzés elemre.
13. Kattintson a Megerősítés gombra.

## <a name="receive-the-products"></a>A termékek bevételezése
1. A Művelet panelen kattintson a Bevételezés elemre.
2. Kattintson a Termékbevételezés elemre.
3. A Termékbevételezés mezőbe írja be a termékbevételezés számát. Például írja be, hogy PR123.
4. Kattintson az OK gombra a termékbevételezés feladásához.
5. Zárja be a lapot.

## <a name="create-a-vendor-invoice"></a>Szállítói számla létrehozása
1. Ugorjon a Kötelezettségek > Beszerzési rendelések > Bevételezett, de még ki nem számlázott beszerzési rendelések pontra.
2. Válassza ki a létrehozott beszerzési rendelést.
3. A Művelet panelen kattintson a Számla elemre.
4. Kattintson a Számlára.
5. A Szám mezőben adja meg a számlaszámot.
6. A Számla leírása mezőben adjon meg egy értéket.
7. A Számla dátuma mezőben adjon meg egy dátumot.
8. Írjon be 1200 értéket az Egységár mezőbe.
9. Kattintson az Új sor hozzáadására.
10. A Cikkszám mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
11. Keresse meg a listában a telepítési költség cikkszámát. Például az S0001 elem
12. Válassza ki a telepítési költség cikkszámát.
    * Vegye figyelembe, hogy egyeztetés a módosítások óta nem lett végrehajtva.  
13. Kattintson az Egyeztetési állapot frissítése lehetőségre.
14. A Művelet panelen kattintson az Áttekintés lehetőségre.
15. Kattintson a Részletek egyeztetése elemre.
    * A szolgáltatásokkal rendelkező új sorokat nem kell egyeztetni, ezért az állapotuk „Kihagyva” marad.  
16. Válassza ki a termékbevételezést a bevételezett készletcikkhez.
    * A termékbevételezés sora egyeztetve lett, de eltérés található az árban vagy a mennyiségben, ezért sikertelen.  
17. Adjon meg egy számot az Egységár mezőben.
    * Most, hogy az egységár megegyezik, az állapot Sikeres értékre frissül. Ha az irányelve megengedi az eltéréseket, vagy az egyeztetés csak egy figyelmeztetés, akkor ettől függetlenül fel tudja adni a számlát.  
18. Zárja be a lapot.
19. Kattintson a Feladás lehetőségre.
20. Zárja be az űrlapot.
    * Ne felejtse, hogy a beszerzési rendelés már nem bevételezettként, hanem nem számlázottként van listázva.  


