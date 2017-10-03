---
title: "Tervezett rendelések karbantartása"
description: "Ez a cikk a tervezett rendelések kezelésével kapcsolatban nyújt információkat. Leírja, hogyan frissítheti a tervezett rendelések állapotát, erősítheti meg őket, és hogy hogyan szűrheti a kijelölttel azonos állapotú tervezett rendeléseket."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 19151
ms.assetid: 54123f4c-b4ca-4ce4-9358-b067aa04c968
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 94f6f28ec4b255930f84a27eb5394503ff59e4c0
ms.contentlocale: hu-hu
ms.lasthandoff: 05/25/2017

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




