---
title: A munka nem vonható vissza az állapota miatt
description: A munka nem vonható vissza az állapota miatt
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
ms.openlocfilehash: 60b4da44ca5e6790302e0797640317cef8493db7
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924255"
---
# <a name="work-cant-be-canceled-because-of-its-status"></a><span data-ttu-id="93f89-103">A munka nem vonható vissza az állapota miatt</span><span class="sxs-lookup"><span data-stu-id="93f89-103">Work can't be canceled because of its status</span></span>

<span data-ttu-id="93f89-104">Hibakód: WAX2190</span><span class="sxs-lookup"><span data-stu-id="93f89-104">Error code: WAX2190</span></span>

## <a name="symptoms"></a><span data-ttu-id="93f89-105">Tünetek</span><span class="sxs-lookup"><span data-stu-id="93f89-105">Symptoms</span></span>

<span data-ttu-id="93f89-106">A rendszer a következő hibaüzenetet jeleníti meg:</span><span class="sxs-lookup"><span data-stu-id="93f89-106">The system shows the following error message:</span></span>

> <span data-ttu-id="93f89-107">A(z) %1 munka nem vonható vissza, mivel az állapota %2.</span><span class="sxs-lookup"><span data-stu-id="93f89-107">You cannot cancel work %1 because it has a status of %2.</span></span>

## <a name="cause"></a><span data-ttu-id="93f89-108">Ok</span><span class="sxs-lookup"><span data-stu-id="93f89-108">Cause</span></span>

<span data-ttu-id="93f89-109">A munka a jelenlegi állapotában nem szakítható meg.</span><span class="sxs-lookup"><span data-stu-id="93f89-109">The work can't be canceled in its current state.</span></span>

<span data-ttu-id="93f89-110">A munka fejléce vagy munkasorai nem a munka várt **Munkaállapot** értékkel rendelkeznek.</span><span class="sxs-lookup"><span data-stu-id="93f89-110">The work header or work lines don't have the expected **Work status** value.</span></span> <span data-ttu-id="93f89-111">A munkafejléc **Munka állapota** mezője nincs beállítva *Nyitott* vagy *Folyamatban* állapotúra.</span><span class="sxs-lookup"><span data-stu-id="93f89-111">The **Work status** field on the work header isn't set to *Open* or *In progress*.</span></span>

## <a name="resolution"></a><span data-ttu-id="93f89-112">Felbontás</span><span class="sxs-lookup"><span data-stu-id="93f89-112">Resolution</span></span>

<span data-ttu-id="93f89-113">A munka megszakításához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="93f89-113">To cancel the work, follow these steps.</span></span>

1. <span data-ttu-id="93f89-114">Menjen a **Raktárkezelés \> Időszakos feladatok \> Tisztítás \> Munka megszakítása** menühöz.</span><span class="sxs-lookup"><span data-stu-id="93f89-114">Go to **Warehouse management \> Periodic tasks \> Clean up \> Cancel work**.</span></span>
1. <span data-ttu-id="93f89-115">A **Munkaazonosító** mezőben adja meg a megszakítani kívánt munka azonosítóját.</span><span class="sxs-lookup"><span data-stu-id="93f89-115">In the **Work ID** field, specify the ID of the work that you want to cancel.</span></span>
1. <span data-ttu-id="93f89-116">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="93f89-116">Select **OK**.</span></span>
1. <span data-ttu-id="93f89-117">Válassza az **Igen** lehetőséget a munka megszakításához.</span><span class="sxs-lookup"><span data-stu-id="93f89-117">Select **Yes** to confirm that you want to cancel the work.</span></span>

<span data-ttu-id="93f89-118">További információ: [A kivétel kezelésére vonatkozó raktári munka visszavonása](../../warehousing/cancel-warehouse-work.md).</span><span class="sxs-lookup"><span data-stu-id="93f89-118">For more information, see [Cancel warehouse work for exception handling](../../warehousing/cancel-warehouse-work.md).</span></span>
