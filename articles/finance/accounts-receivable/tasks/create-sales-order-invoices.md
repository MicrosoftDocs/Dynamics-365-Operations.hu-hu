---
title: Értékesítési rendelési számlák létrehozása
description: Ez a feladat-útmutató az értékesítési rendelés számlázását írja le, beleértve a számlákat és a kötegfeldolgozást.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 06/25/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesEditLines,  SysQueryForm, SysRecurrence
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c504ef36f61613c7aa7db5a1e5ddba6e69cd7285
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4444106"
---
# <a name="create-sales-order-invoices"></a>Értékesítési rendelési számlák létrehozása

[!include [banner](../../includes/banner.md)]

Ez a feladat-útmutató az értékesítési rendelés számlázását írja le, beleértve a számlákat és a kötegfeldolgozást. Ez az eljárás az USMF bemutatócéget használja.


## <a name="create-an-invoice-from-a-sales-order"></a>Értékesítési rendelés számlájának létrehozása.
1. Válassza a **Navigációs ablaktábla > Modulok > Kintlévőségek > Megrendelések > Kiszállított de nem számlázott értékesítési rendelések** lehetőségre.
2. Válasszon ki a listából egy értékesítési rendelést. 
3. A **Művelet panelen** kattintson a **Számla > Generálás > Számla** lehetőségre. Ne feledje, hogy ehhez az értékesítési rendeléshez több csomagjegyzék van társítva. A szállítólevél száma helyett csak a <multiple> szó látszik.  
4. Bontsa ki a **Paraméterek** szakaszt.
    - A számla feladásához a Feladásnál az Igent kell beállítani. De ki is kapcsolhatja a feladást, és csak kinyomtathatja a számlát. Azonban ugyanazt az eredményt a számla létrehozása helyett egy Pro forma számla létrehozásával is elérheti.  
    - Ezt a beállítást a kötegelt feladatokhoz szokás használni. A kötegelt feladat futtatása alkalmával a lekérdezés futtatása.
5. A **Nyomtatás** mezőben válassza az „Utána” lehetőséget.
6. Válassza az **Igen** beállítást a **Számla nyomtatásához**. A nyomtatáskezelés a számlát több példányban is ki tudja nyomtatni és e-mailben, PDF-fájlként is el tudja küldeni.  
7. A **Költségek nyomtatása** mezőben válassza az „Összesítés” lehetőséget.
8. A **Hitelkeret ellenőrzése** mezőben válassza ki az „Egyenleg” lehetőséget.
9. Kattintson a **Mégse** gombra.

## <a name="combine-orders-into-a-single-invoice"></a>Rendelések egyesítése egyetlen számlában.
1. Ugorjon a **Navigációs ablaktábla > Modulok > Kintlévőségek > Megrendelések > Minden értékesítési megrendelés** lehetőségre.
2. Keresse meg azt a vevőt, akinek több megnyitott számlája van.
3. Több nyitott értékesítési rendelés kiválasztása ugyanabból a vevőből.
4. A **Művelet panelen** kattintson a **Számla > Generálás > Számla** lehetőségre.
5. Bontsa ki a **Paraméterek** szakaszt.
6. A **Mennyiség** mezőben válassza a 'Mind' lehetőséget. Vegye figyelembe, hogy az Áttekintés részben két számla van felsorolva. Most egyesítsük őket egy számlába.  
7. Az **Összegzés frissítése a következőhöz:** mezőben a „Számlafogadó” kiválasztása.
8. Kattintson az **Elrendezés** elemre az értékesítési megrendelések egy számlában való egyesítésére. A két értékesítési megrendelés egy számlába került.   
9. Kattintson a **Mégse** gombra.
10. Kattintson az **Igen** gombra.

## <a name="post-invoices-in-a-batch"></a>Számlák feladása kötegben
1. Ugorjon a következőre: **Navigációs panel > Kinnlévőségek > Számlák > Kötegelt számlázás > Számla**.
2. Kattintson a **Kiválasztás** lehetőségre.
3. Kattintson az **OK** gombra.
4. Kattintson a **Kötegre** lehetőségre.
5. A **Kötegelt feldolgozás** alatt válassza az **Igen** lehetőséget.
6. Kattintson az **Ismétlődésre**.
7. Válassza a **Napok** lehetőséget.
8. Kattintson az **OK** gombra.
9. Kattintson az **OK** gombra.
10. Kattintson a **Mégse** gombra.
11. Kattintson az **Igen** gombra.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]