---
title: Útvonalak létrehozása (2016. február)
description: Ez a feladat termelési útvonalak létrehozására koncentrál egy késztermékhez és egy félkész termékhez.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, RouteInventProd, RouteGroup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a68b28c0e0ee14429a23d3241cabdae948d706d2
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1567855"
---
# <a name="create-routes-february-2016"></a>Útvonalak létrehozása (2016. február)

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ez a feladat termelési útvonalak létrehozására koncentrál egy késztermékhez és egy félkész termékhez. Ez az anyagjegyzék-számítási sorozat ötödik feladata. A feladat létrehozásához az USMF bemutató vállalatot használtuk példaként.


## <a name="create-a-route-for-a-semi-finished-product"></a>Útvonal létrehozása egy félkész termékhez
1. Kattintson a Termékinformációk kezelése > Termékek > Kiadott termékek lehetőségre.
2. A listában kattintson a kijelölt sorban lévő hivatkozásra.
    * Válassza ki a BOM_2 cikkszámot.  
3. A Művelet panelen kattintson a Mérnök elemre.
4. Kattintson az Útvonalra.
5. Kattintson az Új lehetőségre.
6. Kattintson az Útvonal és útvonalverzió lehetőségre.
7. A Leírás mezőben adjon meg egy értéket.
    * Írja be például a következőt: ROUTE_2.  
8. A Hely mezőben adjon meg vagy válasszon ki egy értéket.
    * Ebben a példában adja meg vagy válassza ki az 1. helyet.  
9. Kattintson az OK gombra.
10. Kattintson az Új lehetőségre.
11. A Műveletek mezőben adjon meg vagy válasszon ki egy értéket.
    * Ehhez a példához válassza ki a Szerelvény lehetőséget.  
12. Adjon meg egy számot a Futási idő mezőben.
    * Például írja be a „1” értéket. A futási idő általában része a kiszámított cikkárnak.  
13. Az Útvonalcsoport mezőben adjon meg, vagy válasszon ki egy értéket.
    * Ehhez a példához válassza ki a következőt: Std.  
14. Kattintson a Beállítás fülre.
15. A Beállítási kategória mezőben adjon meg vagy válasszon ki egy értéket.
    * Ehhez a példához válassza ki a Szerelvény lehetőséget.  
16. Kattintson az Idők fülre.
17. A Beállítási idő mezőben adjon meg egy számot.
    * Ehhez a példához írja be a következőt: 1. A beállítási idő általában része a kiszámított cikkárnak.  
18. A Művelet panelen kattintson az Útvonalverzió elemre.
19. Kattintson a Jóváhagyás lehetőségre.
20. A „Szeretné jóvá is hagyni az útvonalat?” kérdésre válaszolva válassza ki az Igen lehetőséget.
21. Kattintson az OK gombra.
22. A Művelet panelen kattintson az Útvonalverzió elemre.
23. Kattintson az Aktiválás gombra.
24. Zárja be a lapot.
25. Zárja be a lapot.

## <a name="create-a-route-for-a-finished-product"></a>Útvonal létrehozása egy késztermékhez
1. A listában kattintson a kijelölt sorban lévő hivatkozásra.
    * Válassza ki a BOM_1 cikkszámot.  
2. A Művelet panelen kattintson a Mérnök elemre.
3. Kattintson az Útvonalra.
4. Kattintson az Új lehetőségre.
5. Kattintson az Útvonal és útvonalverzió lehetőségre.
6. A Leírás mezőben adjon meg egy értéket.
    * Ehhez a példához írja be a következőt: ROUTE_1.  
7. A Hely mezőben adjon meg vagy válasszon ki egy értéket.
    * Ebben a példában adja meg vagy válassza ki az 1. helyet.  
8. Kattintson az OK gombra.
9. Kattintson az Új lehetőségre.
10. A Műveletek mezőben adjon meg vagy válasszon ki egy értéket.
    * Ehhez a példához válassza ki a Csomagolás lehetőséget.  
11. Adjon meg egy számot a Futási idő mezőben.
    * Ehhez a példához írja be a következőt: 1.  
12. Az Útvonalcsoport mezőben adjon meg, vagy válasszon ki egy értéket.
    * Ehhez a példához válassza ki a következőt: Std.  
13. Kattintson a Beállítás fülre.
14. A Beállítási kategória mezőben adjon meg vagy válasszon ki egy értéket.
    * Ehhez a példához válassza ki a Csomagolás lehetőséget.  
15. Kattintson az Idők fülre.
16. A Beállítási idő mezőben adjon meg egy számot.
    * Ehhez a példához írja be a következőt: 1.  
17. A Művelet panelen kattintson az Útvonalverzió elemre.
18. Kattintson a Jóváhagyás lehetőségre.
19. Kattintson az OK gombra.
20. A Művelet panelen kattintson az Útvonalverzió elemre.
21. Kattintson az Aktiválás gombra.
22. Zárja be a lapot.
23. Zárja be a lapot.

## <a name="enable-automatic-consumption-of-setup-time"></a>A beállítási idő automatikus felhasználásának engedélyezése
1. Ugrás a Gyártásvezérlés > Beállítás > Útvonalak > Útvonalcsoportok lehetőségre.
2. Keresse meg és jelölje ki a kívánt rekordot a listán.
    * A listában válassza a következőt: Std.  
3. Kattintson a Szerkesztés lehetőségre.
4. Válassza ki az Igen lehetőséget a Beállítási idő mezőben.
    * A beállítási idő általában része a kiszámított cikkárnak.  
5. Kattintson a Mentés gombra.
6. Zárja be a lapot.

