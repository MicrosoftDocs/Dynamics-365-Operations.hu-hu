---
title: Pénzügyi dimenziók hozzáadása a pénzügyi igazgatói munkaterülethez
description: Ez a témakör bemutatja a pénzügyi dimenziók hozzáadását a pénzügyi igazgatói munkaterülethez, így felhasználhatók a főkönyvi és költségvetési jelentésekhez.
author: aprilolson
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14091
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 3817c6688339735c7478e85786efe15bd2372c91
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/27/2019
ms.locfileid: "2178065"
---
# <a name="add-financial-dimensions-to-the-cfo-workspace"></a>Pénzügyi dimenziók hozzáadása a pénzügyi igazgatói munkaterülethez

[!include [banner](../includes/banner.md)]

Ez a témakör bemutatja a pénzügyi dimenziók hozzáadását a pénzügyi igazgatói munkaterülethez, így felhasználhatók a főkönyvi és költségvetési jelentésekhez. A pénzügyi igazgatói munkaterület van egy **Áttekintés** lap és egy **Pénzügyi** lapon. Az ezeken a lapokon levő jelentéseket két mérték támogatja: a LedgerActivityMeasure és a BudgetActivityMeasure. Kapcsolat van a két mérték és a DimensionCombinationEntity entitás között. Ezért dimenziókat választhat ki.

1. A Finance rendszerben az **Entitástár** oldalon frissítse a **LedgerActivityMeasure** és a **BudgetActivityMeasure** mértékeket.
2. A Microsoft Visual Studio alkalmazásban nyissa meg az Application Explorer lehetőséget, és keressen a **LedgerCFO** kifejezésre.
3. Az **Erőforrások** pontban nyissa meg a **LedgerCFOWorkspacePBIX** lehetőséget.
4. Amikor az erőforrás megnyílik a Microsoft Power BI asztalon, válassza az **Adatok átvétele** lehetőséget, jelölje be az **SQL Server adatbázis** pontot, majd válassza a **Csatlakozás** lehetőséget.
5. Adja meg a kiszolgáló nevét, és az adatbázis neveként írja be a **AxDW** értéket. Válassza a **DirectQuery** lehetőséget, majd kattintson az **OK** gombra.
6. Keressen meg és válassza ki a **LedgerActivityMeasure\_DimensionCombination** lehetőséget, majd válassza a **Betöltés** lehetőséget.

    > [!TIP]
    > A **Mezők** listában nevezze át a **Pénzügyi dimenziók** táblát, hogy egyszerűen azonosítható legyen.

7. Válassza a **Kapcsolatok kezelése** lehetőséget, majd válassza ki az **Új** pontot.
8. Az első mezőben válassza ki a **Főkönyvi tevékenységek** lehetőséget, majd válassza a **LedgerDimension** pontot.
9. A második mezőben válassza a **LedgerActivityMeasure\_DimensionCombination** lehetőséget (vagy a **Pénzügyi dimenziók** lehetőséget, ha átnevezte a táblát). Válassza a **DimensionCombinationRECID** fejlécet.
10. A **Számosság** mezőben válassza a **Több az egyhez** lehetőséget.
11. Módosítsa a **Keresztszűrő iránya** értéket **Egyetlen** lehetőségre.
12. Jelölje be a **Kapcsolat aktívvá tétele** és a **Hivatkozási integritás feltételezése** pontokat, válassza az **OK** lehetőséget, majd a **Lezárás** lehetőséget.

    [![Kapcsolat létrehozása](./media/Create-relationship.png)](./media/Create-relationship.png)

13. A **Mezők** listában megjelenik a tábla és a rendelkezésre álló pénzügyi dimenziók. Húzza át a kívánt pénzügyi dimenziókat a jelentésszintű szűrőkhöz.
14. Mentse el a módosításokat.
15. Az alkalmazásobjektum-fa (AOT), kattintson a jobb gombbal a projektre, és válassza a **Szinkronizálás** lehetőséget.
16. Hozza létre a projektet, és nyissa meg az alkalmazást az eredmények megtekintéséhez.

    [![Kész munkaterület](./media/workspace.png)](./media/workspace.png)
