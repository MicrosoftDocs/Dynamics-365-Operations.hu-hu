---
title: "Tervezett rendelések karbantartása"
description: "Ez a cikk a tervezett rendelések kezelésével kapcsolatban nyújt információkat. Leírja, hogyan frissítheti a tervezett rendelések állapotát, erősítheti meg őket, és hogy hogyan szűrheti a kijelölttel azonos állapotú tervezett rendeléseket."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 19151
ms.assetid: 54123f4c-b4ca-4ce4-9358-b067aa04c968
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: c01a192e637bfe74a60370290db72c439faf40d0
ms.lasthandoff: 03/31/2017


---

# <a name="maintain-planned-orders"></a>Tervezett rendelések karbantartása

[!include[banner](../includes/banner.md)]


Ez a cikk a tervezett rendelések kezelésével kapcsolatban nyújt információkat. Leírja, hogyan frissítheti a tervezett rendelések állapotát, erősítheti meg őket, és hogy hogyan szűrheti a kijelölttel azonos állapotú tervezett rendeléseket.

A tervezett rendeléseket kezelheti az **Alaptervezés** munkaterületen, a **Tervezett rendelés** listában, vagy a **Tervezett termelési rendelések**, **Tervezett beszerzési rendelések**, és **Tervezett átmozgatás** listákban. Használhatja az **Állapot** mezőt, ami segít nyomon követni folyamatot. A következő értékek kerülnek felhasználásra:

-   Amikor az alaptervezés tervezett rendeléseket készít, akkor a tervezett rendelések állapota **Feldolgozatlan**.
-   Ha úgy dönt, hogy nem erősíti meg a tervezett rendelést, akkor hozzárendelheti a **Befejezett** állapotot.
-   Ha úgy dönt, hogy megerősít egy tervezett rendelést, akkor hozzárendelheti a **Jóváhagyva** állapotot. Ez az állapot jelzi, hogy jóváhagyja a tervezett rendelés megerősítését, de még nincs megerősítve.

**Megjegyzés:** Egy jóváhagyott tervezett rendelés a jelenlegi állapotában kerül átvitelre kerül a következő alaptervezési számításba. Tervezett rendelések megerősítéséhez kattintson a **Megerősítés** gombra. A következő tervezett megrendeléseket lehet megerősíteni:

-   A kijelölt tervezett rendelés.
-   Több tervezett megrendelést.
-   Azon tervezett rendelések, amelyek egy **Alábontások** lapon szereplő alábontás által jönnek létre. Kattintson a **Tervezett rendelések** elemre, válassza ki a tervezett rendelést, majd kattintson a **Megerősítés** gombra.

Amikor egy tervezett rendelést megerősít, akkor az a megfelelő modul rendelések szakaszába kerül. **Megjegyzés:** Ha a jobb gombbal egy tervezett rendelésre kattint, amelynek adott állapota és szűrője van, akkor elérheti a többi ugyanazon állapottal rendelkező tervezett rendelést. Ez a funkció akkor hasznos, ha például ki akarja szűrni az olyan tervezett rendeléseket, amelyek állapota **Jóváhagyva**, hogy megerősíthesse őket.

<a name="see-also"></a>Lásd még
--------

[Alaptervek](master-plans.md)



