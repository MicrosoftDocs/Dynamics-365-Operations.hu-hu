---
title: Kapacitásterhelés számítása ütemezett munkarendeléseken
description: Ez a témakör azt mutatja be, hogyan lehet kapacitásterhelést számolni az ütemezett munkarendelésekre az Eszközkezelés modulban.
author: johanhoffmann
ms.date: 08/19/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 09e0fc17a288a278b7b1feaba8c7b73425aa2d52
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5808160"
---
# <a name="calculate-capacity-load-on-scheduled-work-orders"></a><span data-ttu-id="a184e-103">Kapacitásterhelés számítása ütemezett munkarendeléseken</span><span class="sxs-lookup"><span data-stu-id="a184e-103">Calculate capacity load on scheduled work orders</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="a184e-104">Az ütemezett munkarendelésekre vonatkozóan kiszámíthatja a kapacitások terhelését, hogy egy adott időszakra vonatkozóan áttekintést kapjon az erőforrásokkal kapcsolatos munkaterhelésről.</span><span class="sxs-lookup"><span data-stu-id="a184e-104">You can calculate capacity load on scheduled work orders to get an overview of the work load on resources for a specific period.</span></span> <span data-ttu-id="a184e-105">A számítások a következő erőforrásokon hajthatók végre: karbantartó dolgozók, dolgozói csoportok, segédeszközök és eszközök.</span><span class="sxs-lookup"><span data-stu-id="a184e-105">Calculations can be made for the following resources: Maintenance workers, worker groups, tools, and assets.</span></span>

1. <span data-ttu-id="a184e-106">Kattintson az **Eszközkezelés** > **Lekérdezések** > **Ütemezés** > **Kapacitásterhelés** elemre.</span><span class="sxs-lookup"><span data-stu-id="a184e-106">Click **Asset management** > **Inquiries** > **Schedule** > **Capacity load**.</span></span>

2. <span data-ttu-id="a184e-107">A **Kapacitásterhelés számítása** párbeszédpanel > **Megjelenítés** mezőben válassza ki, hogy melyik terhelési típust szeretné kiszámítani: **Kapacitás**, **Foglalt** vagy **Fennmaradó**.</span><span class="sxs-lookup"><span data-stu-id="a184e-107">In the **Calculate capacity load** dialog > **Show** field, select which load type you want to calculate: **Capacity**, **Reserved**, or **Remainder**.</span></span>

3. <span data-ttu-id="a184e-108">Ha a nullát tartalmazó eredményeket nem szeretné megjeleníteni, állítsa a **Nulla kihagyása** választógombot **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="a184e-108">Select **Yes** on the **Skip zero** toggle button if you do not want to show results containing zero.</span></span>

4. <span data-ttu-id="a184e-109">Válassza ki azokat az erőforrás-típusokat, amelyekhez ki kívánja számítani a kapacitásterhelést a megfelelő aktiváló gombokon az **Igen** kiválasztásával: **Dolgozó**, **Karbantartási dolgozó csoport**, **Segédeszköz** és **Eszköz**.</span><span class="sxs-lookup"><span data-stu-id="a184e-109">Select the resource types for which you want to calculate capacity load by selecting **Yes** on the relevant toggle buttons: **Worker**, **Maintenance worker group**, **Tool**, and **Asset**.</span></span>

5. <span data-ttu-id="a184e-110">A **Kezdő dátum** mezőben válassza ki a számítás kezdő dátumát.</span><span class="sxs-lookup"><span data-stu-id="a184e-110">Select the start date for the calculation in the **From date** field.</span></span>

6. <span data-ttu-id="a184e-111">Az **Intervallum** típusa mezőben válassza ki a számítás intervallumát: **Nap**, **Hét**, **Hónap** vagy **Negyedév**.</span><span class="sxs-lookup"><span data-stu-id="a184e-111">In the **Interval type** field, select the interval for the calculation: **Day**, **Week**, **Month**, or **Quarter**.</span></span>

7. <span data-ttu-id="a184e-112">Az **Időszak gyakorisága** mezőbe írja be, hogy hány intervallumot kíván kiszámítani.</span><span class="sxs-lookup"><span data-stu-id="a184e-112">In the **Period frequency** field, insert the number of intervals you want to calculate.</span></span> <span data-ttu-id="a184e-113">Ha például a **Nap** beállítás van megadva az időszak gyakoriságának, és a mezőbe az „5” számot írja be, akkor a kezdő dátumtól számított öt nap számítása történik meg.</span><span class="sxs-lookup"><span data-stu-id="a184e-113">For example, if you have selected **Day** as the interval type, and you enter the number "5" in this field, a calculation of five days from the start date will be made.</span></span>

8. <span data-ttu-id="a184e-114">Kattintson az **OK** gombra az számítás indításához.</span><span class="sxs-lookup"><span data-stu-id="a184e-114">Click **OK** to start the calculation.</span></span>

<span data-ttu-id="a184e-115">Az alábbi ábra egy olyan számítás eredményét jeleníti meg, amely három hétre terjed ki a **Foglalt** terheléstípus esetében.</span><span class="sxs-lookup"><span data-stu-id="a184e-115">The figure below shows the result of a calculation covering three weeks for the load type **Reserved**.</span></span>

![1. ábra](media/08-work-order-scheduling.png)

[!NOTE]
<span data-ttu-id="a184e-117">Ha a számításhoz a **Kapacitás** vagy a **Fennmaradó** terheléstípust választja, akkor ugyanazt az eredményt jeleníti meg a program, ha nem történt foglalás a kiválasztott időszak erőforrásaihoz.</span><span class="sxs-lookup"><span data-stu-id="a184e-117">If you select the load types **Capacity** or **Remainder** for your calculation, the same result will be displayed if no reservations have been made for the resources in the selected period.</span></span>

<span data-ttu-id="a184e-118">Lásd a [Kapacitásterhelés kiszámítása](../capacity-planning/calculate-capacity-load.md) részt tájékoztatásért a kapacitás terhelésének számításához a karbantartási ütemezés soraiban, és nem az ütemezett munkarendeléseken.</span><span class="sxs-lookup"><span data-stu-id="a184e-118">For information about how to calculate capacity load on maintenance schedule lines and not scheduled work orders, refer to [Calculate capacity load](../capacity-planning/calculate-capacity-load.md).</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]