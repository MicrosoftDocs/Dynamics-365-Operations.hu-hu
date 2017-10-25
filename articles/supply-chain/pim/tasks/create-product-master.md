--- 
title: "Alaptermék létrehozása"
description: "Hozzon létre egy alapterméket az előre megadott változatokhoz."
author: YuyuScheller
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Operations
ms.search.region: Global
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 4e8d438da1524850c115f5c38865fac2f19f3ff5
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-product-master"></a>Alaptermék létrehozása

[!include[task guide banner](../../includes/task-guide-banner.md)]

Hozzon létre egy alapterméket az előre megadott változatokhoz. Ez az eljárás az USMF bemutatócéget használja. Ezt az eljárást a terméktervező használja.


## <a name="create-a-new-product-master"></a>Új alaptermék létrehozása
1. Ugorjon a Termékinformációk kezelése > Termékek > Alaptermékek lehetőségre.
2. Kattintson az Új lehetőségre.
3. Írjon be egy értéket a Termékszám mezőbe.
    * A számnak egyedinek kell lennie. Egy számsorozat állítható be a Termékszám mezőben. Ebben az esetben a felhasználónak nem kell megadnia értéket.  
4. Írjon be egy értéket a Terméknév mezőbe.
    * Írjon be egy jól érthető terméknevet. Az alapértelmezett érték a keresési név, de ez módosítható a felhasználó által.  
5. A Termékdimenzió csoport mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
    * A termékdimenzió-csoport határozza meg, hogy a 4 termékdimenzió melyike használható termékváltozatok létrehozására. Ez a példa egy mérettel és színnel rendelkező csoportot használ.  
6. Keresse meg és jelölje ki a kívánt rekordot a listán.
7. A listában kattintson a kijelölt sorban lévő hivatkozásra.
    * Az alapértelmezett konfigurációs technológia az Előre megadott változat. Ebben a példában ezt használjuk.  
8. Kattintson az OK gombra.

## <a name="select-product-dimension-groups"></a>Termékdimenzió-csoportok kiválasztása
1. A Színcsoport mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
2. A kívánt rekord megkeresése és kijelölése a listán
3. A listában kattintson a kijelölt sorban lévő hivatkozásra.
4. A Méretcsoport mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
5. Keresse meg és jelölje ki a kívánt rekordot a listán.
6. A listában kattintson a kijelölt sorban lévő hivatkozásra.

## <a name="add-dimension-groups"></a>Dimenziócsoportok hozzáadása
1. A Művelet panelen kattintson a Termék elemre.
2. A Méretcsoportok gombra kattintva megnyithatja a legördülő párbeszédablakot.
3. A Tárolási dimenzió csoport mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
    * A tárolási dimenziók segítenek a cikkek raktárban való tárolásának és raktárból való kivételének szabályozásában. Például a tárolási dimenzió magában foglalhatja a Helyet és a Raktárt.  
4. Keresse meg és jelölje ki a kívánt rekordot a listán.
5. A listában kattintson a kijelölt sorban lévő hivatkozásra.
6. A Nyomon követési dimenzió csoport mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
    * A nyomon követési dimenziócsoport meghatározza, hogy mely nyomon követési dimenziókat adhatja hozzá egy termékhez. Például a kötegszám, és a sorozatszám is használható a készletcikkek nyomon követésére.  
7. Keresse meg és jelölje ki a kívánt rekordot a listán.
8. A listában kattintson a kijelölt sorban lévő hivatkozásra.
9. Kattintson az OK gombra.
10. Kattintson a Mentés gombra.
11. Zárja be a lapot.


