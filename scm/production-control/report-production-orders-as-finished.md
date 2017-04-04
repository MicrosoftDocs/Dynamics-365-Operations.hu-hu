---
title: "Termelési rendelések jelentése befejezettként"
description: "Készként történő jelentés a termelési fázisban. Ebben a szakaszban a késztermék jelentett, és a gyártási rendelés átkerül a készlet."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ProdJournalTransJob, ProdJournalTransProd, ProdJournalTransRoute, ProdParmReportFinished, ProdRouteOprOverview
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 27061
ms.assetid: 1c2dfc54-a293-49f2-9b96-5a912ac5762c
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 19a777a8e58e3c8b848e878956b457a4a730f6e2
ms.lasthandoff: 03/31/2017


---

# <a name="report-production-orders-as-finished"></a>Termelési rendelések jelentése befejezettként

Készként történő jelentés a termelési fázisban. Ebben a szakaszban a késztermék jelentett, és a gyártási rendelés átkerül a készlet.

Amikor a késztermékek mennyiségét egy termelési rendelésen készként jelentik, akkor a mennyiség frissül a rendelkezésre álló készletben is. Az eredetileg tervezett rendelési mennyiségből részleges mennyiség is jelenthető készként. Emellett a hibás mennyiségeket is készre lehet jelenteni, kapcsolódó hibaok megadásával. Amikor a termelési rendelés eléri a Készként jelentve fokozatot, az azt jelenti, hogy nem lesz további mennyiség jelentve a termelési rendelésből.
A következő jellemzők társulnak a **Készként jelentve** folyamathoz:
-   A nyersanyag és az idő felhasználása úgy is beállítható, hogy arányos legyen a jelentett mennyiséggel (visszavezetés)
-   Betárolási munka generálható olyan cikkekre, amelyeknél engedélyezve vannak a raktárkezelési folyamatok.
-   A késztermékek tervezett vagy standard költségére beállítható a főkönyvi számlákra való jelentés.
-   Minőségi rendelés hozható létre a jelentett mennyiséghez, minőségi társítás beállítása alapján.

A mennyiség a kimeneti helyre lesz jelentve. Ekkor raktári munka jön létre, amely áttárolja a mennyiséget a kimeneti helyről arra a végcélra, amelyet a betárolási munka helyutasítása határoz meg.

-   Minőségi rendelés akkor hozható létre, amikor wgy termelési rendelést készre jelentenek, amennyiben be lett állítva minőségi társítás.

## <a name="set-a-production-order-to-reporting-as-finished"></a>Termelési rendelés Készre jelentett állapotra állítása
A termelési rendelés a szokásos termelési rendelés frissítése funkcióval, az útvonal- és feladatkártyanaplókkal, vagy a **Jelentés készként** naplóval lehet **Készként jelenteni**. Emellett a feladatkártya-terminál és a feladatkártya-eszköz oldalakon keresztül is frissítheti az állapotot **Jelentés készként** értékre, amikor a termelési rendelés utolsó feladatát lejelenti. Végül a **Jelentés készként** állapotot a hordozható raktári eszközök megoldásának folyamatán keresztül is aktiválhatja.  


