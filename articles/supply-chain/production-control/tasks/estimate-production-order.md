---
title: "Termelési rendelés becslése"
description: "Ezt a folyamatot az USMF bemutatócégen vagy saját adathalmaza használatával is elvégezheti."
author: johanhoffmann
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 90d6dd1886deb9ec5700e1db9b5a3aaf7f83bdf8
ms.contentlocale: hu-hu
ms.lasthandoff: 05/08/2018

---
# <a name="estimate-a-production-order"></a><span data-ttu-id="a2e24-103">Termelési rendelés becslése</span><span class="sxs-lookup"><span data-stu-id="a2e24-103">Estimate a production order</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="a2e24-104">Ezt a folyamatot az USMF bemutatócégen vagy saját adathalmaza használatával is elvégezheti.</span><span class="sxs-lookup"><span data-stu-id="a2e24-104">You can run this procedure by using the USMF demo data company or your own data set.</span></span> <span data-ttu-id="a2e24-105">Mindkét esetben meg kell lennie a nyitott termelési rendelésnek, Létrehozva állapottal.</span><span class="sxs-lookup"><span data-stu-id="a2e24-105">In both cases, you need to have an open production order that has the Created status.</span></span> <span data-ttu-id="a2e24-106">Ez a második eljárás abból a hétből, amely bemutatja a termelési rendelés életciklusát.</span><span class="sxs-lookup"><span data-stu-id="a2e24-106">This is the second procedure out of seven which explains the production order lifecycle.</span></span>


## <a name="estimate-a-production-order"></a><span data-ttu-id="a2e24-107">Termelési rendelés becslése</span><span class="sxs-lookup"><span data-stu-id="a2e24-107">Estimate a production order</span></span>
1. <span data-ttu-id="a2e24-108">Ugrás a Gyártásvezérlés > Termelési rendelések > Minden termelési rendelésre.</span><span class="sxs-lookup"><span data-stu-id="a2e24-108">Go to Production control > Production orders > All production orders.</span></span>
2. <span data-ttu-id="a2e24-109">Válassza ki a rácsban a Létrehozva állapotú rendelést.</span><span class="sxs-lookup"><span data-stu-id="a2e24-109">Select an order that has the Created status in the grid.</span></span>
3. <span data-ttu-id="a2e24-110">A Művelet panelen kattintson a Termelési rendelés elemre.</span><span class="sxs-lookup"><span data-stu-id="a2e24-110">On the Action Pane, click Production order.</span></span>
4. <span data-ttu-id="a2e24-111">Kattintson a Becslés elemre.</span><span class="sxs-lookup"><span data-stu-id="a2e24-111">Click Estimate.</span></span>
    * <span data-ttu-id="a2e24-112">Ebben a lépésben az egyetlen termelési rendelésre vonatkozó becsült költséget számíthatja ki.</span><span class="sxs-lookup"><span data-stu-id="a2e24-112">In this step, the estimated costs of a single production order is calculated.</span></span>   
5. <span data-ttu-id="a2e24-113">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="a2e24-113">Click OK.</span></span>

## <a name="view-the-calculation-details"></a><span data-ttu-id="a2e24-114">Számítás részleteinek megjelenítése</span><span class="sxs-lookup"><span data-stu-id="a2e24-114">View the calculation details</span></span>
1. <span data-ttu-id="a2e24-115">A Művelet panelen kattintson a Költségkezelés elemre.</span><span class="sxs-lookup"><span data-stu-id="a2e24-115">On the Action Pane, click Manage costs.</span></span>
2. <span data-ttu-id="a2e24-116">Kattintson a Számítás részleteinek megjelenítése elemre.</span><span class="sxs-lookup"><span data-stu-id="a2e24-116">Click View calculation details.</span></span>
    * <span data-ttu-id="a2e24-117">Ezen a lapon a költséglebontás látható.</span><span class="sxs-lookup"><span data-stu-id="a2e24-117">This page displays the cost breakdown.</span></span> <span data-ttu-id="a2e24-118">Megtekintheti például az első sorban a késztermék egységenkénti teljes önköltségi árát.</span><span class="sxs-lookup"><span data-stu-id="a2e24-118">For example, you can view the total cost price per unit for the finished product in the first row.</span></span> <span data-ttu-id="a2e24-119">A következő sorok az anyagjegyzékcikkek, a termelési útvonal és a közvetett költségek költségeit tartalmazzák.</span><span class="sxs-lookup"><span data-stu-id="a2e24-119">The subsequent rows contain costs according to the bill of materials, production route, and indirect costs.</span></span>  

