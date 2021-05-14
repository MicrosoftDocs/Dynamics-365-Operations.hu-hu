---
title: A Munka zárolva marad
description: A Munka zárolva marad
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSWorkTableListPage_WHSWorkUnblocking
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: f85364d1ecfadc36b26c3395ab4402d3cb3b1603
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924130"
---
# <a name="work-remains-blocked"></a><span data-ttu-id="7f39e-103">A Munka zárolva marad</span><span class="sxs-lookup"><span data-stu-id="7f39e-103">Work remains blocked</span></span>

<span data-ttu-id="7f39e-104">Hibakód: WHSWorkBlockingExecutingWaveReason_ErrorMessage</span><span class="sxs-lookup"><span data-stu-id="7f39e-104">Error code: WHSWorkBlockingExecutingWaveReason_ErrorMessage</span></span>

## <a name="symptoms"></a><span data-ttu-id="7f39e-105">Tünetek</span><span class="sxs-lookup"><span data-stu-id="7f39e-105">Symptoms</span></span>

<span data-ttu-id="7f39e-106">A rendszer a következő hibaüzenetet jeleníti meg:</span><span class="sxs-lookup"><span data-stu-id="7f39e-106">The system shows the following error message:</span></span>

> <span data-ttu-id="7f39e-107">A(z) %1 munka zárolva marad, mert a kapcsolódó %2 hullám állapota %3.</span><span class="sxs-lookup"><span data-stu-id="7f39e-107">Work %1 remains blocked because the related wave %2 has status %3.</span></span>

## <a name="cause"></a><span data-ttu-id="7f39e-108">Ok</span><span class="sxs-lookup"><span data-stu-id="7f39e-108">Cause</span></span>

<span data-ttu-id="7f39e-109">A munka feldolgozása jelenleg folyamatban van egy hullámban, és nem lehet feloldani a zárolását az alábbi feltételek egyikének megfelelően:</span><span class="sxs-lookup"><span data-stu-id="7f39e-109">The work is currently being processed on a wave and can't be unblocked, as indicated by one of the following conditions:</span></span>

- <span data-ttu-id="7f39e-110">A **Blokkolási okok** lapon egy vagy több sor **Munkablokkolási ok** mezőjében a *Feldolgozás hullám* van beállítva.</span><span class="sxs-lookup"><span data-stu-id="7f39e-110">On the **Blocking reasons** tab, the **Work blocking reason** field for one or more lines is set to *Processing wave*.</span></span>
- <span data-ttu-id="7f39e-111">Amikor a **Hullám** lehetőséget választja ki a **Kapcsolódó információk** csoportban a Műveleti ablaktábla **Kapcsolódó információk** panelén a **Hullám állapota** mező *Feldolgozás* értékre van állítva.</span><span class="sxs-lookup"><span data-stu-id="7f39e-111">When you select **Wave** in the **Related information** group on the **Related information** tab of the Action Pane, the **Wave status** field is set to *Processing*.</span></span>

## <a name="resolution"></a><span data-ttu-id="7f39e-112">Felbontás</span><span class="sxs-lookup"><span data-stu-id="7f39e-112">Resolution</span></span>

<span data-ttu-id="7f39e-113">A Művelet ablaktábla **Kapcsolódó információk** lapjának **Kapcsolódó információk** csoportjában válassza a **Hullám** elemet.</span><span class="sxs-lookup"><span data-stu-id="7f39e-113">On the Action Pane, on the **Related information** tab, in the **Related information** group, select **Wave**.</span></span> <span data-ttu-id="7f39e-114">A Művelet panelen a **Hullámok** oldalon a **Hullám** lapon a **Hullám** csoportban válassza a **Hullámadatok karbantartása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7f39e-114">Then, on the **Waves** page, on the Action Pane, on the **Wave** tab, in the **Wave** group, select **Cleanup wave data**.</span></span>

## <a name="workaround"></a><span data-ttu-id="7f39e-115">Megkerülő megoldás</span><span class="sxs-lookup"><span data-stu-id="7f39e-115">Workaround</span></span>

<span data-ttu-id="7f39e-116">Ha az előző lépések nem oldják meg a problémát, a következő lépésekkel szakíthatja meg a munkát.</span><span class="sxs-lookup"><span data-stu-id="7f39e-116">If the previous steps didn't fix the issue, you can cancel the work by following these steps.</span></span>

1. <span data-ttu-id="7f39e-117">Menjen a **Raktárkezelés \> Időszakos feladatok \> Tisztítás \> Munka megszakítása** menühöz.</span><span class="sxs-lookup"><span data-stu-id="7f39e-117">Go to **Warehouse management \> Periodic tasks \> Clean up \> Cancel work**.</span></span>
1. <span data-ttu-id="7f39e-118">A **Munkaazonosító** mezőben adja meg annak a munkának az azonosítóját, amelyről törölni szeretne, és amelynek jelenleg **Munkaállapot** értéke *Nyitott*, *Folyamatban*, *Megszakítva*, *Kombinálva* vagy *Lezárva*.</span><span class="sxs-lookup"><span data-stu-id="7f39e-118">In the **Work ID** field, specify the ID of the work that you want to cancel, and that currently has a **Work status** value of *Open*, *In progress*, *Canceled*, *Combined*, or *Closed*.</span></span>
1. <span data-ttu-id="7f39e-119">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7f39e-119">Select **OK**.</span></span>
1. <span data-ttu-id="7f39e-120">Válassza az **Igen** lehetőséget a munka megszakításához.</span><span class="sxs-lookup"><span data-stu-id="7f39e-120">Select **Yes** to confirm that you want to cancel the work.</span></span>

<span data-ttu-id="7f39e-121">További információ: [A kivétel kezelésére vonatkozó raktári munka visszavonása](../../warehousing/cancel-warehouse-work.md).</span><span class="sxs-lookup"><span data-stu-id="7f39e-121">For more information, see [Cancel warehouse work for exception handling](../../warehousing/cancel-warehouse-work.md).</span></span>
