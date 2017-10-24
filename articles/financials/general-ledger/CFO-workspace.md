---
title: "Pénzügyi dimenziók hozzáadása a pénzügyi igazgatói munkaterülethez"
description: "Ez a témakör bemutatja a pénzügyi dimenziók hozzáadását a pénzügyi igazgatói munkaterülethez, így felhasználhatók a főkönyvi és költségvetési jelentésekhez."
author: aprilolson
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 14091
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 9e674948f642ab7525f96092a9a1f3adaae66974
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="add-financial-dimensions-to-the-cfo-workspace"></a><span data-ttu-id="39fd6-103">Pénzügyi dimenziók hozzáadása a pénzügyi igazgatói munkaterülethez</span><span class="sxs-lookup"><span data-stu-id="39fd6-103">Add financial dimensions to the CFO workspace</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="39fd6-104">Ez a témakör bemutatja a pénzügyi dimenziók hozzáadását a pénzügyi igazgatói munkaterülethez, így felhasználhatók a főkönyvi és költségvetési jelentésekhez.</span><span class="sxs-lookup"><span data-stu-id="39fd6-104">This topic explains how to add financial dimensions to the Chief Financial Officer (CFO) workspace, so that they can be used for the ledger and budget reports.</span></span> <span data-ttu-id="39fd6-105">A pénzügyi igazgatói munkaterület van egy **Áttekintés** lap és egy **Pénzügyi** lapon. Az ezeken a lapokon levő jelentéseket két mérték támogatja: a LedgerActivityMeasure és a BudgetActivityMeasure.</span><span class="sxs-lookup"><span data-stu-id="39fd6-105">The CFO workspace has an **Overview** tab and a **Financial** tab. The reports on these two tabs are backed by two measures: LedgerActivityMeasure and BudgetActivityMeasure.</span></span> <span data-ttu-id="39fd6-106">A Microsoft Dynamics 365 for Finance and Operations Enterprise edition (2017. júliusi frissítés) megoldásban összefüggés van ezen két mérték és a DimensionCombinationEntity entitás között.</span><span class="sxs-lookup"><span data-stu-id="39fd6-106">In Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (July 2017), there is a relation between those two measures and the DimensionCombinationEntity entity.</span></span> <span data-ttu-id="39fd6-107">Ezért dimenziókat választhat ki.</span><span class="sxs-lookup"><span data-stu-id="39fd6-107">Therefore, you can select dimensions.</span></span>

1. <span data-ttu-id="39fd6-108">A Finance and Operations rendszerben az **Entitástár** oldalon frissítse a **LedgerActivityMeasure** és a **BudgetActivityMeasure** mértékeket.</span><span class="sxs-lookup"><span data-stu-id="39fd6-108">In Finance and Operations, on the **Entity Store** page, update the **LedgerActivityMeasure** and the **BudgetActivityMeasure** measures.</span></span>
2. <span data-ttu-id="39fd6-109">A Microsoft Visual Studio alkalmazásban nyissa meg az Application Explorer lehetőséget, és keressen a **LedgerCFO** kifejezésre.</span><span class="sxs-lookup"><span data-stu-id="39fd6-109">In Microsoft Visual Studio, open Application Explorer, and search for **LedgerCFO**.</span></span>
3. <span data-ttu-id="39fd6-110">Az **Erőforrások** pontban nyissa meg a **LedgerCFOWorkspacePBIX** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="39fd6-110">Under **Resources**, open **LedgerCFOWorkspacePBIX**.</span></span>
4. <span data-ttu-id="39fd6-111">Amikor az erőforrás megnyílik a Microsoft Power BI asztalon, válassza az **Adatok átvétele** lehetőséget, jelölje be az **SQL Server adatbázis** pontot, majd válassza a **Csatlakozás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="39fd6-111">When the resource opens in Microsoft Power BI desktop, select **Get Data**, select **SQL Server database**, and then select **Connect**.</span></span>
5. <span data-ttu-id="39fd6-112">Adja meg a kiszolgáló nevét, és az adatbázis neveként írja be a **AxDW** értéket.</span><span class="sxs-lookup"><span data-stu-id="39fd6-112">Enter the server name, and enter **AxDW** as the database.</span></span> <span data-ttu-id="39fd6-113">Válassza a **DirectQuery** lehetőséget, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="39fd6-113">Select **DirectQuery**, and then select **OK**.</span></span>
6. <span data-ttu-id="39fd6-114">Keressen meg és válassza ki a **LedgerActivityMeasure\_DimensionCombination** lehetőséget, majd válassza a **Betöltés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="39fd6-114">Search for and select **LedgerActivityMeasure\_DimensionCombination**, and then select **Load**.</span></span>

    > [!TIP]
    > <span data-ttu-id="39fd6-115">A **Mezők** listában nevezze át a **Pénzügyi dimenziók** táblát, hogy egyszerűen azonosítható legyen.</span><span class="sxs-lookup"><span data-stu-id="39fd6-115">In the **Fields** list, rename the table **Financial dimensions**, so that it's easy to identify.</span></span>

7. <span data-ttu-id="39fd6-116">Válassza a **Kapcsolatok kezelése** lehetőséget, majd válassza ki az **Új** pontot.</span><span class="sxs-lookup"><span data-stu-id="39fd6-116">Select **Manage Relationships**, and then select **New**.</span></span>
8. <span data-ttu-id="39fd6-117">Az első mezőben válassza ki a **Főkönyvi tevékenységek** lehetőséget, majd válassza a **LedgerDimension** pontot.</span><span class="sxs-lookup"><span data-stu-id="39fd6-117">In the first field, select **General Ledger Activities**, and then select **LedgerDimension**.</span></span>
9. <span data-ttu-id="39fd6-118">A második mezőben válassza a **LedgerActivityMeasure\_DimensionCombination** lehetőséget (vagy a **Pénzügyi dimenziók** lehetőséget, ha átnevezte a táblát).</span><span class="sxs-lookup"><span data-stu-id="39fd6-118">In the second field, select **LedgerActivityMeasure\_DimensionCombination** (or **Financial dimensions** if you renamed the table).</span></span> <span data-ttu-id="39fd6-119">Válassza a **DimensionCombinationRECID** fejlécet.</span><span class="sxs-lookup"><span data-stu-id="39fd6-119">Select the  **DimensionCombinationRECID** header.</span></span>
10. <span data-ttu-id="39fd6-120">A **Számosság** mezőben válassza a **Több az egyhez** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="39fd6-120">In the **Cardinality** field, select **Many to One**.</span></span>
11. <span data-ttu-id="39fd6-121">Módosítsa a **Keresztszűrő iránya** értéket **Egyetlen** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="39fd6-121">Change the **Cross filter direction** value to **Single**.</span></span>
12. <span data-ttu-id="39fd6-122">Jelölje be a **Kapcsolat aktívvá tétele** és a **Hivatkozási integritás feltételezése** pontokat, válassza az **OK** lehetőséget, majd a **Lezárás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="39fd6-122">Select both **Make this relationship active** and **Assume referential integrity**, select **OK**, and then select **Close**.</span></span>

    <span data-ttu-id="39fd6-123">[![Kapcsolat létrehozása](./media/Create-relationship.png)](./media/Create-relationship.png)</span><span class="sxs-lookup"><span data-stu-id="39fd6-123">[![Create a relationship](./media/Create-relationship.png)](./media/Create-relationship.png)</span></span>

13. <span data-ttu-id="39fd6-124">A **Mezők** listában megjelenik a tábla és a rendelkezésre álló pénzügyi dimenziók.</span><span class="sxs-lookup"><span data-stu-id="39fd6-124">In the **Fields** list, you should see the table and the available financial dimensions.</span></span> <span data-ttu-id="39fd6-125">Húzza át a kívánt pénzügyi dimenziókat a jelentésszintű szűrőkhöz.</span><span class="sxs-lookup"><span data-stu-id="39fd6-125">Drag the financial dimensions that you want to the report-level filters.</span></span>
14. <span data-ttu-id="39fd6-126">Mentse el a módosításokat.</span><span class="sxs-lookup"><span data-stu-id="39fd6-126">Save your changes.</span></span>
15. <span data-ttu-id="39fd6-127">Az alkalmazásobjektum-fa (AOT), kattintson a jobb gombbal a projektre, és válassza a **Szinkronizálás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="39fd6-127">In the Application Object Tree (AOT), right-click your project, and then select **Synchronize**.</span></span>
16. <span data-ttu-id="39fd6-128">Hozza létre a projektet, és nyissa meg az alkalmazást az eredmények megtekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="39fd6-128">Build your project, and then open the application to view the results.</span></span>

    <span data-ttu-id="39fd6-129">[![Kész munkaterület](./media/workspace.png)](./media/workspace.png)</span><span class="sxs-lookup"><span data-stu-id="39fd6-129">[![Completed workspace](./media/workspace.png)](./media/workspace.png)</span></span>

