---
title: Az utolsó lezárt munkasornak betárolásnak kell lennie
description: Az utolsó lezárt munkasornak betárolásnak kell lennie
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
ms.openlocfilehash: a5b78154b51252b3ac96ba28c254e823caf87019
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924375"
---
# <a name="the-last-closed-work-line-must-be-a-put"></a><span data-ttu-id="0e3f3-103">Az utolsó lezárt munkasornak betárolásnak kell lennie</span><span class="sxs-lookup"><span data-stu-id="0e3f3-103">The last closed work line must be a put</span></span>

<span data-ttu-id="0e3f3-104">Hibakód: WAX1285</span><span class="sxs-lookup"><span data-stu-id="0e3f3-104">Error code: WAX1285</span></span>

## <a name="symptoms"></a><span data-ttu-id="0e3f3-105">Tünetek</span><span class="sxs-lookup"><span data-stu-id="0e3f3-105">Symptoms</span></span>

<span data-ttu-id="0e3f3-106">A rendszer a következő hibaüzenetet jeleníti meg:</span><span class="sxs-lookup"><span data-stu-id="0e3f3-106">The system shows the following error message:</span></span>

> <span data-ttu-id="0e3f3-107">Az utolsó lezárt munkasornak betárolásnak kell lennie.</span><span class="sxs-lookup"><span data-stu-id="0e3f3-107">The last closed work line must be a put.</span></span>

## <a name="cause"></a><span data-ttu-id="0e3f3-108">Ok</span><span class="sxs-lookup"><span data-stu-id="0e3f3-108">Cause</span></span>

<span data-ttu-id="0e3f3-109">A munka a jelenlegi állapotában nem szakítható meg.</span><span class="sxs-lookup"><span data-stu-id="0e3f3-109">The work can't be canceled in its current state.</span></span>

<span data-ttu-id="0e3f3-110">Az utolsó munkasor **Munkaállapot** mezőjének beállítása *Lezárt*, de a **Munkatípus** mező nincs beállítva *Betárolás* értékre.</span><span class="sxs-lookup"><span data-stu-id="0e3f3-110">On the last work line, the **Work status** field is set to *Closed*, but the **Work type** field isn't set to *Put*.</span></span>

## <a name="resolution"></a><span data-ttu-id="0e3f3-111">Felbontás</span><span class="sxs-lookup"><span data-stu-id="0e3f3-111">Resolution</span></span>

<span data-ttu-id="0e3f3-112">A munka megszakításához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="0e3f3-112">To cancel the work, follow these steps.</span></span>

1. <span data-ttu-id="0e3f3-113">Menjen a **Raktárkezelés \> Időszakos feladatok \> Tisztítás \> Munka megszakítása** menühöz.</span><span class="sxs-lookup"><span data-stu-id="0e3f3-113">Go to **Warehouse management \> Periodic tasks \> Clean up \> Cancel work**.</span></span>
1. <span data-ttu-id="0e3f3-114">A **Munkaazonosító** mezőben adja meg a megszakítani kívánt munka azonosítóját.</span><span class="sxs-lookup"><span data-stu-id="0e3f3-114">In the **Work ID** field, specify the ID of the work that you want to cancel.</span></span>
1. <span data-ttu-id="0e3f3-115">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0e3f3-115">Select **OK**.</span></span>
1. <span data-ttu-id="0e3f3-116">Válassza az **Igen** lehetőséget a munka megszakításához.</span><span class="sxs-lookup"><span data-stu-id="0e3f3-116">Select **Yes** to confirm that you want to cancel the work.</span></span>

<span data-ttu-id="0e3f3-117">További információ: [A kivétel kezelésére vonatkozó raktári munka visszavonása](../../warehousing/cancel-warehouse-work.md).</span><span class="sxs-lookup"><span data-stu-id="0e3f3-117">For more information, see [Cancel warehouse work for exception handling](../../warehousing/cancel-warehouse-work.md).</span></span>
