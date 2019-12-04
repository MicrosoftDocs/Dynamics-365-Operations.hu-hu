---
title: Tervezett rendelések karbantartása
description: Ez a témakör a tervezett rendelések kezelésével kapcsolatban nyújt információkat. Leírja, hogyan frissítheti a tervezett rendelések állapotát, erősítheti meg őket, és hogy hogyan szűrheti a kijelölttel azonos állapotú tervezett rendeléseket.
author: roxanadiaconu
manager: AnnBe
ms.date: 11/07/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 19151
ms.assetid: 54123f4c-b4ca-4ce4-9358-b067aa04c968
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 68bccb632255eac975dc150cf322d4c579ff2f24
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/18/2019
ms.locfileid: "2813776"
---
# <a name="maintain-planned-orders"></a>Tervezett rendelések karbantartása

[!include [banner](../includes/banner.md)]

Ez a témakör a tervezett rendelések kezelésével kapcsolatban nyújt információkat. Leírja, hogyan frissítheti a tervezett rendelések állapotát, erősítheti meg őket, és hogy hogyan szűrheti a kijelölttel azonos állapotú tervezett rendeléseket.

A tervezett rendeléseket kezelheti az **Alaptervezés** munkaterületen, a **Tervezett rendelés** listában, vagy a **Tervezett termelési rendelések**, **Tervezett beszerzési rendelések**, és **Tervezett átmozgatás** listákban. 

## <a name="planned-order-status"></a>Tervezett rendelésállapot
Használhatja az **Állapot** mezőt, ami segít nyomon követni folyamatot. A következő értékek kerülnek felhasználásra:

-   Amikor az alaptervezés tervezett rendeléseket készít, akkor a tervezett rendelések állapota **Feldolgozatlan**.
-   Ha úgy dönt, hogy nem erősíti meg a tervezett rendelést, akkor hozzárendelheti a **Befejezett** állapotot.
-   Ha meg szeretné határozni a tervezett rendelést, akkor a **Jóváhagyott** állapotra módosítható. Az Alaptervezés figyelembe veszi a **Jóváhagyott** állapotú tervezett rendeléseket, így azokat nem módosítja vagy nem törli a program későbbi alaptervezés futtatása során. 

## <a name="firming-planned-orders"></a>Tervezett rendelések megerősítése 
A tervezett rendelések megerősítésével létrejönnek a tényleges rendelések. Ismertek *kiadott* vagy *nyitott rendelésként* is. Amikor egy tervezett rendelést megerősít, akkor az a megfelelő modul rendelések szakaszába kerül.

A **Tervezett rendelések** lapon két megerősítő beállítást választhat:

-   **Megerősítés** – egy vagy több kiválasztott tervezett rendelést erősít meg.
-   **Összes megerősítése** – a szűrő minden tervezett rendelését megerősíti. Az **Összes megerősítése** használatakor nem kell kijelölni a tervezett rendelést, a szűrőn belül minden tervezett rendelés megerősítést kap. Ez a beállítás akkor lehet hasznos, ha nagy számú tervezett rendelést erősít meg.

> [!NOTE]
> Nyomon követheti azt a tervezett rendelést, amely itt lett megerősítve: **Megerősítések előzményei**, a következő alatt: **Tervezett rendelések képernyő > Nézet > Megerősítések előzményei**.

## <a name="parallelize-firming"></a>Párhuzamos megerősítés
Ha egyszerre több rendelést szeretne megerősíteni, akkor a futtatás párhuzamosítása javíthatja a futási időt vagy a teljesítményt. Ez a beállítás csak akkor érhető el, ha több tervezett rendelést erősít meg a következők egyikével: **Megerősítés** vagy **Összes megerősítése**. A következő paraméterek állnak rendelkezésre:

-   **Megerősítés párhuzamosítása** – ha **Igen**, a megerősítési folyamat párhuzamos lesz a **Szálak száma** esetében meghatározott szálak számával.
-   **Szálak száma** – a megerősítési folyamat párhuzamosítására használt szálak számát adja meg. A paraméter csak akkor jelenik meg, ha a **Megerősítés párhuzamosítása** beállítása **Igen**.


<a name="additional-resources"></a>További erőforrások
--------

[Alaptervek áttekintése](master-plans.md)



