---
title: Munka és kiadások elszámolóárainak konfigurálása
description: Ez az eljárás bemutatja, hogyan állítható be egy projekt munkához és kiadásokhoz tartozó elszámolóára.
author: KimANelson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjCostPriceHour, ProjSalesPriceHour, ProjCostPriceExpense, ProjSalesPriceCost
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: knelson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f89590c87aec1a7200e95aeac6b2765fc64bb623
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "339395"
---
# <a name="configure-standard-costs-for-labor-and-expenses"></a>Munka és kiadások elszámolóárainak konfigurálása

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás bemutatja, hogyan állítható be egy projekt munkához és kiadásokhoz tartozó elszámolóára. Ez a feladat az USSI-adatkészletet használja.

1. Nyissa meg a Projektvezetés és könyvelés > Beállítás > Árak > Költségár (óra) elemet.
2. Kattintson az Új lehetőségre.
3. Adja meg a dátumot az Érvényesség dátuma mezőben.
4. Adjon meg egy számot az Önköltségi ár mezőben.
    * A projektkategóriához megadható elszámolóár, de megadható az önköltségi ár dolgozószám, projektszám, kategória, dátum vagy ezek tetszőleges kombinációja alapján is. A rendszer a legnagyobb részletességű szinten létező önköltségi árat alkalmazza.  
5. Kattintson a Mentés gombra.
6. Zárja be a lapot.
7. Nyissa meg a Projektvezetés és könyvelés > Beállítás > Árak > Eladási ár (óra) elemet.
8. Kattintson az Új lehetőségre.
9. Adja meg a dátumot az Érvényesség dátuma mezőben.
10. Az Érvényes mezőben válasszon ki egy lehetőséget.
11. Adjon meg egy számot az Árazás mezőben.
    * Beállítható az óratranzakciók és projektkategóriák szokásos eladási ára. Szintén be lehet állítani dolgozók száma, projekt száma, kategória, tranzakció dátuma vagy ezek bármely kombinációja szerinti eladási árakat. Amikor a dolgozó az óranaplóban beviszi a tranzakciót, a legrészletesebb szintű eladási ár lesz az aktuális eladási ár. Ha például egy általános és egy dolgozóra vonatkozó eladási ár is be van állítva, akkor a rendszer a dolgozóra vonatkozó eladási árat választja.  
12. Kattintson a Mentés gombra.
13. Zárja be a lapot.
14. Nyissa meg a Projektvezetés és könyvelés > Beállítás > Árak > Költségár (kiadás) elemet.
15. Kattintson az Új lehetőségre.
16. Adja meg a dátumot az Érvényesség dátuma mezőben.
17. Adjon meg egy számot az Önköltségi ár mezőben.
    * Több mező is kitölthető, de ez a minimálisan szükséges a rekord mentéséhez.  
18. Kattintson a Mentés gombra.
19. Zárja be a lapot.
20. Nyissa meg a Projektvezetés és könyvelés > Beállítás > Árak > Értékesítési ár (kiadás) elemet.
21. Kattintson az Új lehetőségre.
22. Adja meg a dátumot az Érvényesség dátuma mezőben.
23. Az Érvényes mezőben válasszon ki egy lehetőséget.
24. Adjon meg egy számot az Árazás mezőben.
    * Amikor a dolgozó a költségnaplóba beviszi a tranzakciót, a legrészletesebb szintű eladási ár lesz az aktuális eladási ár. Ha például egy általános és egy dolgozóra vonatkozó eladási ár is be van állítva, akkor a rendszer a dolgozóra vonatkozó eladási árat választja.  
25. Kattintson a Mentés gombra.

