---
title: Felhasználóhoz rendelt munkát nem lehet megszakítani
description: Felhasználóhoz rendelt munkát nem lehet megszakítani
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSWorkTable_WHSWorkCancel, WHSWorkTableListPage_WHSWorkCancel
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: e5f6912cfb1d5be8e46b7989856af99f8a611c11
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924401"
---
# <a name="you-cant-cancel-work-that-is-on-a-user"></a><span data-ttu-id="42aab-103">Felhasználóhoz rendelt munkát nem lehet megszakítani</span><span class="sxs-lookup"><span data-stu-id="42aab-103">You can't cancel work that is on a user</span></span>

<span data-ttu-id="42aab-104">Hibakód: WAX708</span><span class="sxs-lookup"><span data-stu-id="42aab-104">Error code: WAX708</span></span>

## <a name="symptoms"></a><span data-ttu-id="42aab-105">Tünetek</span><span class="sxs-lookup"><span data-stu-id="42aab-105">Symptoms</span></span>

<span data-ttu-id="42aab-106">A rendszer a következő hibaüzenetet jeleníti meg:</span><span class="sxs-lookup"><span data-stu-id="42aab-106">The system shows the following error message:</span></span>

> <span data-ttu-id="42aab-107">Felhasználóhoz rendelt munkát nem lehet érvényteleníteni.</span><span class="sxs-lookup"><span data-stu-id="42aab-107">You cannot cancel work that is on a user.</span></span>

## <a name="cause"></a><span data-ttu-id="42aab-108">Ok</span><span class="sxs-lookup"><span data-stu-id="42aab-108">Cause</span></span>

<span data-ttu-id="42aab-109">A munka zárolva van a felhasználó által, ezért nem lehet megszakítani.</span><span class="sxs-lookup"><span data-stu-id="42aab-109">The work is locked by a user and can't be canceled.</span></span> <span data-ttu-id="42aab-110">Ennek megerősítéshez nyissa meg a munkaazonosítót, majd nyissa meg az **Általános** lapot. Ha a munka zárolva van, a **Munka állapota** mező *Folyamatban van* értéket kap, a **Zárolta** mezőben pedig egy felhasználói azonosító látható.</span><span class="sxs-lookup"><span data-stu-id="42aab-110">To confirm this, open the work ID and then open the **General** tab. If the work is locked, the **Work status** field will be set to *In progress*, and the **Locked by** field will be set to a user ID.</span></span>

## <a name="resolution"></a><span data-ttu-id="42aab-111">Felbontás</span><span class="sxs-lookup"><span data-stu-id="42aab-111">Resolution</span></span>

<span data-ttu-id="42aab-112">A munka megszakításához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="42aab-112">To cancel the work, follow these steps.</span></span>

1. <span data-ttu-id="42aab-113">Menjen a **Raktárkezelés \> Időszakos feladatok \> Tisztítás \> Munka megszakítása** menühöz.</span><span class="sxs-lookup"><span data-stu-id="42aab-113">Go to **Warehouse management \> Periodic tasks \> Clean up \> Cancel work**.</span></span>
1. <span data-ttu-id="42aab-114">A **Munkaazonosító** mezőben adja meg a megszakítani kívánt munka azonosítóját.</span><span class="sxs-lookup"><span data-stu-id="42aab-114">In the **Work ID** field, specify the ID of the work that you want to cancel.</span></span>
1. <span data-ttu-id="42aab-115">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="42aab-115">Select **OK**.</span></span>
1. <span data-ttu-id="42aab-116">Válassza az **Igen** lehetőséget a munka megszakításához.</span><span class="sxs-lookup"><span data-stu-id="42aab-116">Select **Yes** to confirm that you want to cancel the work.</span></span>

<span data-ttu-id="42aab-117">További információ: [A kivétel kezelésére vonatkozó raktári munka visszavonása](../../warehousing/cancel-warehouse-work.md).</span><span class="sxs-lookup"><span data-stu-id="42aab-117">For more information, see [Cancel warehouse work for exception handling](../../warehousing/cancel-warehouse-work.md).</span></span>
