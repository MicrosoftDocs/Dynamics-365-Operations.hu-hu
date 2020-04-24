---
title: Alaptermék létrehozása
description: Hozzon létre egy alapterméket az előre megadott változatokhoz.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductListPage, EcoResProductCreate, EcoResProductDetails, EcoResProductInventoryDimensionGroups
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 25c1a50f99070953c86dbff897757fd959beec79
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/02/2020
ms.locfileid: "3208248"
---
# <a name="create-a-product-master"></a>Alaptermék létrehozása

[!include [banner](../../includes/banner.md)]

Hozzon létre egy alapterméket az előre megadott változatokhoz. Ez az eljárás az USMF bemutatócéget használja. Ezt az eljárást a terméktervező használja.


## <a name="create-a-new-product-master"></a>Új alaptermék létrehozása
1. Válassza a **Navigációs ablaktábla > Modulok > Termékinformációk kezelése > Termékek > Alaptermékek** lehetőséget.
2. Kattintson az **Új** elemre.
3. Írjon be egy értéket a **Termékszám** mezőbe. A számnak egyedinek kell lennie. Egy számsorozat állítható be a **Termékszám** mezőben. Ebben az esetben a felhasználónak nem kell megadnia értéket.
4. Írjon be egy értéket a **Terméknév** mezőbe. Írjon be egy jól érthető terméknevet. Az alapértelmezett érték a keresési név, de ez módosítható a felhasználó által.
5. A **Termékdimenzió csoport** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához. A termékdimenzió-csoport határozza meg, hogy a 4 termékdimenzió melyike használható termékváltozatok létrehozására. Ez a példa egy mérettel és színnel rendelkező csoportot használ.
6. Keresse meg és jelölje ki a kívánt rekordot a listán.
7. A listában kattintson a kijelölt sorban lévő hivatkozásra. Az alapértelmezett **Konfigurációs technológia** az „Előre megadott” változat. Ebben a példában ezt használjuk.
8. Kattintson az **OK** gombra.

## <a name="select-product-dimension-groups"></a>Termékdimenzió-csoportok kiválasztása
1. A **Színcsoport** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
2. A kívánt rekord megkeresése és kijelölése a listán
3. A listában kattintson a kijelölt sorban lévő hivatkozásra.
4. A **Méretcsoport** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
5. Keresse meg és jelölje ki a kívánt rekordot a listán.
6. A listában kattintson a kijelölt sorban lévő hivatkozásra.

## <a name="add-dimension-groups"></a>Dimenziócsoportok hozzáadása
1. A **Műveleti panel** modulon kattintson a **Termék** elemre.
2. A **Méretcsoportok** gombra kattintva megnyithatja a legördülő párbeszédablakot.
3. A **Tárolási dimenzió csoport** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához. A tárolási dimenziók segítenek a cikkek raktárban való tárolásának és raktárból való kivételének szabályozásában. Például a tárolási dimenzió magában foglalhatja a Helyet és a Raktárt.
4. Keresse meg és jelölje ki a kívánt rekordot a listán.
5. A listában kattintson a kijelölt sorban lévő hivatkozásra.
6. A **Nyomon követési dimenzió csoport** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához. A nyomon követési dimenziócsoport meghatározza, hogy mely nyomon követési dimenziókat adhatja hozzá egy termékhez. Például a kötegszám, és a sorozatszám is használható a készletcikkek nyomon követésére.
7. Keresse meg és jelölje ki a kívánt rekordot a listán.
8. A listában kattintson a kijelölt sorban lévő hivatkozásra.
9. Kattintson az **OK** gombra.
10. Kattintson a **Mentés** gombra.
11. Zárja be a lapot.

