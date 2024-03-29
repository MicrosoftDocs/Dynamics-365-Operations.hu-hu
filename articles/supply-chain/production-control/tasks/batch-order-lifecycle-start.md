---
title: Kötegelt rendelések életciklusa a létrehozástól az indításig
description: Ez az eljárás bemutatja egy kötegrendelés életciklusának első felét.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ProdTableListPage, ProdTableCreate, ProdBOM, PmfProdCoBy, ProdParmCostEstimation, ProdCalcTrans, ProdParmRelease, ProdSchedule, ProdRouteJob, ProdParmStartUp, ProdJournalTransBOM, ProdJournalTransRoute
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a7ca259ca8f176cd5bc76081836adcb7d272972b
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/29/2021
ms.locfileid: "7579256"
---
# <a name="batch-order-lifecycle-from-create-to-start"></a>Kötegelt rendelések életciklusa a létrehozástól az indításig

[!include [banner](../../includes/banner.md)]

Ez az eljárás bemutatja egy kötegrendelés életciklusának első felét.

A létrehozástól, költségbecsléstől a termelési feladatok ütemezésén keresztül a kötegrendelés tényleges indulásáig.



Ez az eljárás az USMF bemutatócéget használja. 



Az eljárás végrehajtásának előfeltétele egy másik adathalmaz esetént, egy kiadott termék egy aktív receptúrával és útvonalverzióval.


## <a name="create-a-batch-order"></a>Kötegrendelés létrehozása
1. Válassza a Minden termelési rendelés lehetőséget.
2. Kattintson az Új kötegrendelés elemre.
3. Az Elemszám mezőben adjon meg, vagy válasszon ki egy értéket.
4. Kattintson az Új > lehetőségre.
5. A gyorsszűrő használatával keresse meg azokat a rekordokat, ahol a Termelés mezőben a „b” érték szerepel.

## <a name="view-production-formula-and-expected-co-products"></a>Termelési receptúra és a várható társtermékek megtekintése
1. A Művelet panelen kattintson a Termelési rendelés elemre.
2. Kattintson a Receptúra elemre.
3. Zárja be a lapot.
4. Kattintson a Társtermékek elemre.
5. Zárja be a lapot.

## <a name="estimate-the-batch-order"></a>Kötegrendelés becslése
1. Kattintson a Becslés elemre.
2. Kattintson az OK gombra.
3. A Művelet panelen kattintson a Költségkezelés elemre.
4. Kattintson a Számítás részleteinek megjelenítése elemre.
5. Zárja be a lapot.

## <a name="release-the-batch-order"></a>Kötegrendelés kiadása
1. A Művelet panelen kattintson a Termelési rendelés elemre.
2. Kattintson a Kiadás elemre.
3. Kattintson az OK gombra.

## <a name="schedule-production-jobs"></a>Termelési feladatok ütemezése
1. A Művelet panelen kattintson az Ütemezés elemre.
2. Kattintson a Feladatok ütemezése lehetőségre.
3. Válassza a Nem lehetőséget a Véges kapacitás mezőben.
4. Válassza a Nem lehetőséget a Véges anyag mezőben.
5. Kattintson az OK gombra.
6. A Művelet panelen kattintson a Termelési rendelés elemre.
7. Kattintson a Minden feladat elemre.
8. Zárja be a lapot.

## <a name="start-the-batch-order"></a>Kötegrendelés indítása
1. Kattintson a Start elemre.
2. Kattintson az Általános fülre.
3. Válassza a Nem lehetőséget a Kitárolási lista feladása most mezőben.
4. Kattintson az OK gombra.
5. A Művelet panelen kattintson a Nézet elemre.
6. Kattintson a Kitárolási lista elemre.
7. A listában kattintson a kijelölt sorban lévő hivatkozásra.
8. Zárja be a lapot.
9. Zárja be a lapot.
10. Kattintson az Útvonalkártya elemre.
11. A listában kattintson a kijelölt sorban lévő hivatkozásra.
12. Zárja be a lapot.
13. Zárja be a lapot.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]