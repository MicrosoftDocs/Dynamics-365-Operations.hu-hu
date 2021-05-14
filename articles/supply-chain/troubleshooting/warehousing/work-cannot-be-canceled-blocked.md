---
title: A munka nem vonható vissza, mert zárolva van
description: A munka nem vonható vissza, mert zárolva van
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSWorkTable_WHSWorkCancel
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: a7ab4c7263947767164702fb7dd6da7573175253
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924279"
---
# <a name="work-cant-be-canceled-because-its-blocked"></a><span data-ttu-id="2c566-103">A munka nem vonható vissza, mert zárolva van</span><span class="sxs-lookup"><span data-stu-id="2c566-103">Work can't be canceled because it's blocked</span></span>

<span data-ttu-id="2c566-104">Hibakód: WHSCancellationOfWorkBlockedByExecutingWave_ErrorMessage</span><span class="sxs-lookup"><span data-stu-id="2c566-104">Error code: WHSCancellationOfWorkBlockedByExecutingWave_ErrorMessage</span></span>

## <a name="symptoms"></a><span data-ttu-id="2c566-105">Tünetek</span><span class="sxs-lookup"><span data-stu-id="2c566-105">Symptoms</span></span>

<span data-ttu-id="2c566-106">A rendszer a következő hibaüzenetet jeleníti meg:</span><span class="sxs-lookup"><span data-stu-id="2c566-106">The system shows the following error message:</span></span>

> <span data-ttu-id="2c566-107">A(z) %1 munka nem szakítható meg, mert a következő ok miatt zárolva van: %2.</span><span class="sxs-lookup"><span data-stu-id="2c566-107">Work %1 cannot be cancelled because it is blocked by reason type %2.</span></span> <span data-ttu-id="2c566-108">A megszakítás előtt meg kell szűntetni a munka blokkolását.</span><span class="sxs-lookup"><span data-stu-id="2c566-108">The work must be unblocked before it can be cancelled.</span></span>

## <a name="cause"></a><span data-ttu-id="2c566-109">Ok</span><span class="sxs-lookup"><span data-stu-id="2c566-109">Cause</span></span>

<span data-ttu-id="2c566-110">A munka zárolva van, ezért nem lehet megszakítani.</span><span class="sxs-lookup"><span data-stu-id="2c566-110">The work is blocked and can't be canceled.</span></span>

<span data-ttu-id="2c566-111">A **Munka** oldalon az **Általános** lapon a **Blokkolva** beállítás értéke *Igen*.</span><span class="sxs-lookup"><span data-stu-id="2c566-111">On the **Work** page, on the **General** tab, the **Blocked** option is set to *Yes*.</span></span> <span data-ttu-id="2c566-112">Ez a beállítás azt jelzi, hogy a munka zárolva van.</span><span class="sxs-lookup"><span data-stu-id="2c566-112">This setting indicates that the work is blocked.</span></span> <span data-ttu-id="2c566-113">A **Blokkolási okok** lap mutatja, hogy miért blokkolták a munkát.</span><span class="sxs-lookup"><span data-stu-id="2c566-113">The **Blocking reasons** tab shows why the work was blocked.</span></span>

## <a name="resolution"></a><span data-ttu-id="2c566-114">Felbontás</span><span class="sxs-lookup"><span data-stu-id="2c566-114">Resolution</span></span>

<span data-ttu-id="2c566-115">A munka zárolásának feloldásához válassza a **Blokkolási okok** lapot, majd hajtsa végre a következő lépések valamelyikét:</span><span class="sxs-lookup"><span data-stu-id="2c566-115">To unblock the work, select the **Blocking reasons** tab, and then follow one of these steps:</span></span>

- <span data-ttu-id="2c566-116">Ha a **Munkazárolási ok** mező beállítása *Nem meghatározott ok*: A műveleti panel **Munka lapján** válassza a **Munka** csoportban válassza a **Munka zárolásának feloldása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2c566-116">If the **Work blocking reason** field is set to *Undefined reason*: On the Action Pane, on the **Work** tab, in the **Work** group, select **Unblock work**.</span></span>
- <span data-ttu-id="2c566-117">Ha a **Munka zárolásának oka** mező beállítása *Feldolgozási hullám*: A Műveletei panelen a **Kapcsolódó információk** lapon a **Kapcsolódó információk** csoportban válassza a **Hullám** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2c566-117">If the **Work blocking reason** field is set to *Processing wave*: On the Action Pane, on the **Related information** tab, in the **Related information** group, select **Wave**.</span></span> <span data-ttu-id="2c566-118">A Művelet panelen a **Hullámok** oldalon a **Hullám** lapon a **Hullám** csoportban válassza a **Hullámadatok karbantartása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2c566-118">Then, on the **Waves** page, on the Action Pane, on the **Wave** tab, in the **Wave** group, select **Cleanup wave data**.</span></span>

## <a name="workaround"></a><span data-ttu-id="2c566-119">Megkerülő megoldás</span><span class="sxs-lookup"><span data-stu-id="2c566-119">Workaround</span></span>

<span data-ttu-id="2c566-120">Ha az előző lépések nem oldják meg a problémát, a következő lépésekkel szakíthatja meg a munkát.</span><span class="sxs-lookup"><span data-stu-id="2c566-120">If the previous steps didn't fix the issue, you can cancel the work by following these steps.</span></span>

1. <span data-ttu-id="2c566-121">Menjen a **Raktárkezelés \> Időszakos feladatok \> Tisztítás \> Munka megszakítása** menühöz.</span><span class="sxs-lookup"><span data-stu-id="2c566-121">Go to **Warehouse management \> Periodic tasks \> Clean up \> Cancel work**.</span></span>
1. <span data-ttu-id="2c566-122">A **Munkaazonosító** mezőben adja meg annak a munkának az azonosítóját, amelyről törölni szeretne, és amelynek jelenleg **Munkaállapot** értéke *Nyitott*, *Folyamatban*, *Megszakítva*, *Kombinálva* vagy *Lezárva*.</span><span class="sxs-lookup"><span data-stu-id="2c566-122">In the **Work ID** field, specify the ID of the work that you want to cancel, and that currently has a **Work status** value of *Open*, *In progress*, *Canceled*, *Combined*, or *Closed*.</span></span>
1. <span data-ttu-id="2c566-123">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2c566-123">Select **OK**.</span></span>
1. <span data-ttu-id="2c566-124">Válassza az **Igen** lehetőséget a munka megszakításához.</span><span class="sxs-lookup"><span data-stu-id="2c566-124">Select **Yes** to confirm that you want to cancel the work.</span></span>

<span data-ttu-id="2c566-125">További információ: [A kivétel kezelésére vonatkozó raktári munka visszavonása](../../warehousing/cancel-warehouse-work.md).</span><span class="sxs-lookup"><span data-stu-id="2c566-125">For more information, see [Cancel warehouse work for exception handling](../../warehousing/cancel-warehouse-work.md).</span></span>
