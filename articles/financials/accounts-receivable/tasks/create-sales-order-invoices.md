--- 
title: "Értékesítési rendelési számlák létrehozása"
description: "Ez a feladat-útmutató az értékesítési rendelés számlázását írja le, beleértve a számlákat és a kötegfeldolgozást."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 50c0ee41220461e282aace85f10a0e734a2ab688
ms.contentlocale: hu-hu
ms.lasthandoff: 07/27/2017

---
# <a name="create-sales-order-invoices"></a>Értékesítési rendelési számlák létrehozása

[!include[task guide banner](../../includes/task-guide-banner.md)]

Ez a feladat-útmutató az értékesítési rendelés számlázását írja le, beleértve a számlákat és a kötegfeldolgozást. Ez az eljárás az USMF bemutatócéget használja.


## <a name="create-an-invoice-from-a-sales-order"></a>Értékesítési rendelés számlájának létrehozása.
1. Ugrás a Kinnlevőségek > Rendelések > Leszállított, de még ki nem számlázott értékesítési rendelésekre.
2. Válasszon ki a listából egy értékesítési rendelést. 
3. A Művelet panelen kattintson a Számla lehetőségre.
4. Kattintson a Számla lehetőségre.
    * Ne feledje, hogy ehhez az értékesítési rendeléshez több csomagjegyzék van társítva. A szállítólevél száma helyett csak a <multiple> szó látszik.  
5. Bontsa ki a Paraméterek szakaszt.
    * A számla feladásához a Feladásnál az Igent kell beállítani. De ki is kapcsolhatja a feladást, és csak kinyomtathatja a számlát. Azonban ugyanazt az eredményt a számla létrehozása helyett egy Pro forma számla létrehozásával is elérheti.  
    * Ezt a beállítást a kötegelt feladatokhoz szokás használni. A kötegelt feladat futtatása alkalmával a lekérdezés futtatása.    
6. A Nyomtatás mezőben válassza az „Utána” lehetőséget.
7. Válassza az Igen beállítást a számla nyomtatásához.
    * A nyomtatáskezelés a számlát több példányban is ki tudja nyomtatni és e-mailben, PDF-fájlként is el tudja küldeni.  
8. A Költségek nyomtatása mezőben válassza az „Összesítés” lehetőséget.
9. A Hitelkeret ellenőrzése mezőben válassza ki az „Egyenleg” lehetőséget.
10. Kattintson a Mégse gombra.

## <a name="combine-orders-into-a-single-invoice"></a>Rendelések egyesítése egyetlen számlában.
1. Ugorjon a Kinnlevőségek > Rendelések > Minden értékesítési rendelés elemre.
2. Keresse meg azt a vevőt, akinek több megnyitott számlája van.
3. Válasszon ki egy nyitott értékesítési rendelést.
4. Válasszon ki még egy nyitott értékesítési rendelést ugyanahhoz a vevőhöz.
5. A Művelet panelen kattintson a Számla lehetőségre.
6. Kattintson a Számlára.
7. Bontsa ki a Paraméterek szakaszt.
8. A Mennyiség mezőben válassza a „Mind” lehetőséget.
    * Vegye figyelembe, hogy az Áttekintés részben két számla van felsorolva. Most egyesítsük őket egy számlába.  
9. Az Összegzés frissítése mezőben a „Számlafogadó” kiválasztása.
10. Kattintson az Elrendezésre az értékesítési megrendelések egy számlában való egyesítésére.
    * A két értékesítési megrendelés egy számlába került.   
11. Kattintson a Mégse gombra.
12. Kattintson az Igen gombra.

## <a name="post-invoices-in-a-batch"></a>Számlák feladása kötegben
1. Ugorjon a következőre: Kinnlévőségek > Számlák > Kötegelt számlák > Számla.
2. Kattintson a Kiválasztás lehetőségre.
3. Kattintson az OK gombra.
4. Kattintson a Kötegre.
5. Kattintson az Igen gombra a kötegelt feldolgozás engedélyezéséhez..
6. Kattintson az Ismétlődésre.
7. Napok kiválasztása
8. Kattintson az OK gombra.
9. Kattintson az OK gombra.
10. Kattintson a Mégse gombra.
11. Kattintson az Igen gombra.


