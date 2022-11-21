---
title: Értékesítési rendelési számlák létrehozása
description: Ez a témakör azt ismerteti, hogyan kell számlázni az értékesítési rendeléseket, például a számlák egyesítését és a kötegelt feldolgozást.
author: ShivamPandey-msft
ms.date: 06/25/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SalesTableListPage, SalesEditLines,  SysQueryForm, SysRecurrence
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3ff76eac54da6621d999d9b629fac920ba8de294
ms.sourcegitcommit: 9c4638c4bb5b5f8adc7508542a0a2c3e1de5190c
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/15/2022
ms.locfileid: "9778384"
---
# <a name="create-sales-order-invoices"></a>Értékesítési rendelési számlák létrehozása

[!include [banner](../../includes/banner.md)]

Ez a témakör azt ismerteti, hogyan kell számlázni az értékesítési rendeléseket, például a számlák egyesítését és a kötegelt feldolgozást. Ez az eljárás az USMF bemutatócéget használja.


## <a name="create-an-invoice-from-a-sales-order"></a>Értékesítési rendelés számlájának létrehozása.
1. Válassza a **Navigációs ablaktábla > Modulok > Kintlévőségek > Megrendelések > Kiszállított de nem számlázott értékesítési rendelések** lehetőségre.
2. Válasszon ki a listából egy értékesítési rendelést. 
3. A **Művelet panelen** kattintson a **Számla > Generálás > Számla** lehetőségre. Ne feledje, hogy ehhez az értékesítési rendeléshez több csomagjegyzék van társítva. Csak a *többszörös* szó jelenik meg a csomagolólap száma helyett.  
4. Bontsa ki a **Paraméterek** szakaszt.
    - A számla feladható a feladáshoz **Igen** beállításra. De ki is kapcsolhatja a feladást, és csak kinyomtathatja a számlát. Azonban ugyanazt az eredményt a számla létrehozása helyett egy Pro forma számla létrehozásával is elérheti.  
    - Ezt a beállítást a kötegelt feladatokhoz szokás használni. A kötegelt feladat futtatása alkalmával a lekérdezés futtatása.
5. A Nyomtatás **mezőben** válassza az After **lehetőséget**.
6. Válassza az **Igen** beállítást a **Számla nyomtatásához**. A nyomtatáskezelés a számla több példányát is kinyomtathatja, és a számlát e-mailben elküldheti PDF-fájlként.  
7. A Költségek nyomtatása **mezőben** válassza az Összegzés **lehetőséget**.
8. Válassza az **Egyenleg lehetőséget a Hitelkeret** ellenőrzése **mezőben**.
9. Kattintson a **Mégse** gombra.

## <a name="combine-orders-into-a-single-invoice"></a>Rendelések egyesítése egyetlen számlában.
1. Ugorjon a **Navigációs ablaktábla > Modulok > Kintlévőségek > Megrendelések > Minden értékesítési megrendelés** lehetőségre.
2. Keresse meg azt a vevőt, akinek több megnyitott számlája van.
3. Több nyitott értékesítési rendelés kiválasztása ugyanabból a vevőből.
4. A **Művelet panelen** kattintson a **Számla > Generálás > Számla** lehetőségre.
5. Bontsa ki a **Paraméterek** szakaszt.
6. A **Mennyiség** mezőben válassza a **Mind** lehetőséget. Vegye figyelembe, hogy az Áttekintés részben két számla van felsorolva. Most egyesítsük őket egy számlába.  
7. A Mező Összesítő **frissítés mezőjében** válassza ki a Számla **számlát**.
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
