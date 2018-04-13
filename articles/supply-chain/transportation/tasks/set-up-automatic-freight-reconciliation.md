--- 
title: "Automatikus fuvarlevél-egyeztetés beállítása"
description: "Ez az eljárás bemutatja, hogyan lehet beállítani az adatokat az automatikus fuvaregyeztetéshez."
author: BibiSp
manager: AnnBe
ms.date: 10/13/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 97f0c4d8fe06ab2fc252b9543cb688306214c79f
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-automatic-freight-reconciliation"></a>Automatikus fuvarlevél-egyeztetés beállítása

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás bemutatja, hogyan lehet beállítani az adatokat az automatikus fuvaregyeztetéshez. Ezt általában a raktár vezetője végzi el. Az USMF bemutatócég adataiban használhatja ezt az eljárást.


## <a name="set-up-the-freight-bill-type"></a>Fuvarlevél típusának beállítása
1. Ugrás a Szállításkezelés > Beállítás > Fuvaregyeztetés > Fuvarlevél típusa elemhez.
    * A fuvarlevél típusa határozza meg, hogyan kell egyeztetni a fuvarleveleket és a szállítói számlákat.  
2. Kattintson az Új lehetőségre.
3. Adjon meg egy értéket a Fuvarlevél típusa mezőben.
4. A Kalkulátorszerelvény mezőbe írja be a következőt: Microsoft.Dynamics.Ax.Tms.Bll.GenericNormalizer.
    * Ez a szabványos szállításkezelés-egyeztetési kalkulátorkódtár.  
5. A Kalkulátorosztály mezőbe írja be a következőt: Microsoft.Dynamics.Ax.Tms.dll.
    * Ez a szabványos szállításkezelés-egyeztetési kalkulátorosztály.  
6. Kattintson az Új lehetőségre.
7. A Leírás mezőben válassza ki az értéket, amelynek egyeznie kell a fuvarlevélen és a szállítói számlán.  
8. Válassza az Igen lehetőséget az Egyezés szükséges mezőben.
    * Ha ebben a mezőben az Igen értéket állítja be, ez azt jelenti, hogy a Leírás mezőben kiválasztott értéknek egyeznie kell mind a fuvarlevélen, mind a szállítói számlán. Ha a beállítása Nem, a mező üres lehet ezek egyikén.  
9. Kattintson a Mentés gombra.

## <a name="set-up-the-freight-bill-type-assignment"></a>Fuvarlevéltípus-hozzárendelés beállítása
1. Zárja be a lapot.
2. Ugrás a Szállításkezelés > Beállítás > Fuvaregyeztetés > Fuvarlevéltípus-hozzárendelések elemhez.
    * A fuvarlevél típusú hozzárendelés segítségével megadhatja, hogy melyik fuvarlevéltípus használatos egy adott szállítóhoz.   
3. Kattintson az Új lehetőségre.
4. A Mód mezőben adjon meg vagy válasszon ki egy értéket.
5. A Szállítmányozó mezőben adjon meg vagy válasszon ki egy értéket.
6. A Fuvarlevél típusa mezőben válassza ki a korábban létrehozott fuvarlevéltípust.
7. Zárja be a lapot.

## <a name="set-up-the-audit-master"></a>Alapvizsgálat beállítása
1. Ugrás a Szállításkezelés > Beállítás > Fuvaregyeztetés > Alapvizsgálat elemhez.
    * Az alapvizsgálati beállítás adja meg az automatikus szállítási egyeztetés tűréshatárait. Itt adható meg, mekkora pénzösszegeltérés lehet a fuvarlevélen és a szállítói számlán ahhoz, hogy továbbra is megtörténjen az egyeztetés. Továbbá az eltérések kezelésének módját is meghatározza.  
2. Kattintson az Új lehetőségre.
3. Az Alapvizsgálat azonosítója mezőbe írjon be egy értéket.
4. A Szállítmányozó mezőben válassza ki ugyanazt a szállítmányozót, amelyet korábban már kiválasztott.
5. A Fuvarlevél típusa mezőben válassza ki a korábban létrehozott fuvarlevéltípust.
6. Bontsa ki a Tűréshatár szakaszt.
7. A Minimális tűrési szint mezőben adjon meg egy számot.
8. A Maximális tűrési szint mezőben adjon meg egy számot.
9. Bontsa ki az Eredmény szakaszt.
10. A Túlfizetés okkódja mezőben adjon meg vagy válasszon ki egy értéket.
    * Ha a pénzösszegek különböznek a fuvarlevélen és a szállítói számlán, a túl- és alulfizetés okkódok megadják a számlákat, ahol nyilvántartásba kell venni a különbséget, amennyiben a különbség a tűrési szinteken belül van.  
11. Az Alulfizetés okkódja mezőben adjon meg vagy válasszon ki egy értéket.
12. Zárja be a lapot.


