---
title: "Termelési rendelések készként jelentése"
description: "Termelési szakasz készként jelenítése Ebben a szakaszban megtörténik a késztermék jelentése, és a gyártási rendelés átkerül a készletbe."
author: johanhoffmann
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProdJournalTransJob, ProdJournalTransProd, ProdJournalTransRoute, ProdParmReportFinished, ProdRouteOprOverview
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 27061
ms.assetid: 1c2dfc54-a293-49f2-9b96-5a912ac5762c
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: f8adcbcc2157058151c26179eb2eb925b0092d2d
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="report-production-orders-as-finished"></a>Termelési rendelések készként jelentése

[!include[banner](../includes/banner.md)]


Termelési szakasz készként jelenítése Ebben a szakaszban megtörténik a késztermék jelentése, és a gyártási rendelés átkerül a készletbe.

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




