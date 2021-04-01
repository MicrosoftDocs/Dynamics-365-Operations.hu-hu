---
title: Tervezési feladat érvénytelenítése
description: Ez a témakör azt mutatja be, hogyan lehet érvényteleníteni egy olyan aktív tervezési feladatot, amely a Tervezés optimalizálása funkciót használja.
author: ChristianRytt
manager: tfehr
ms.date: 02/18/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 5aadf7fb94bb2d836892064837f9cb1c5790d657
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5238014"
---
# <a name="cancel-a-planning-job"></a><span data-ttu-id="9e209-103">Tervezési feladat visszavonása</span><span class="sxs-lookup"><span data-stu-id="9e209-103">Cancel a planning job</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="9e209-104">A Microsoft Dynamics 365 Supply Chain Management rendszerben érvényteleníthetők az olyan aktív tervezési feladatok, amelyek a Tervezés optimalizálása funkciót használják.</span><span class="sxs-lookup"><span data-stu-id="9e209-104">In Microsoft Dynamics 365 Supply Chain Management, you can cancel an active planning job that uses the Planning optimization functionality.</span></span> <span data-ttu-id="9e209-105">Ha a párbeszédpanelen a **Mégse** lehetőséget választja, amikor a tervezésoptimalizálási feladat közvetlenül a felhasználói felületről indul el, (nem a háttérben), akkor ez nem törli a tervezési optimalizációs feladatot.</span><span class="sxs-lookup"><span data-stu-id="9e209-105">When you select **Cancel** in the dialog box when a Planning optimization job is triggered directly from the user interface (not in the background), this will not cancel the Planning optimization job.</span></span> <span data-ttu-id="9e209-106">Még ha figyelmeztetés jelenik meg, mint a "művelet visszavonva", akkor is a következő lépések végrehajtásával kell megszüntetni egy tervezési feladatot a tervezési optimalizációval.</span><span class="sxs-lookup"><span data-stu-id="9e209-106">Even if you receive a warning such as “Operation canceled”, you will still need to use the following steps to cancel a planning job with Planning optimization.</span></span>


<span data-ttu-id="9e209-107">Aktív tervezési feladat érvénytelenítéséhez hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="9e209-107">To cancel an active planning job, follow these steps.</span></span> 

> [!NOTE]
> <span data-ttu-id="9e209-108">Csak egy aktív feladat érvényteleníthető.</span><span class="sxs-lookup"><span data-stu-id="9e209-108">Only active jobs can be canceled.</span></span>

1. <span data-ttu-id="9e209-109">Lépjen az **Alaptervezés \> Beállítás \> Tervek** részre.</span><span class="sxs-lookup"><span data-stu-id="9e209-109">Go to **Master planning \> Setup \> Plans**.</span></span>
2. <span data-ttu-id="9e209-110">Válassza ki a tervezés futtatásához megfelelő tervet.</span><span class="sxs-lookup"><span data-stu-id="9e209-110">Select an appropriate plan for the planning run.</span></span>
3. <span data-ttu-id="9e209-111">Válassza az **Előzmények** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9e209-111">Select **History**.</span></span>
4. <span data-ttu-id="9e209-112">Válassza ki az érvényteleníteni kívánt tervezési feladatot.</span><span class="sxs-lookup"><span data-stu-id="9e209-112">Select the planning job to cancel.</span></span>
5. <span data-ttu-id="9e209-113">Válassza a **Mégse** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9e209-113">Select **Cancel**.</span></span>

<span data-ttu-id="9e209-114">A feladat állapota mindaddig **Megszakítás** lesz, amíg a Tervezés optimalizálása szolgáltatás meg nem erősíti, hogy a feladat érvénytelenítve lett.</span><span class="sxs-lookup"><span data-stu-id="9e209-114">The job status will be **Canceling** until the Planning Optimization service confirms that the job has been canceled.</span></span> <span data-ttu-id="9e209-115">Ezt követően az állapot **Megszakítva** lesz.</span><span class="sxs-lookup"><span data-stu-id="9e209-115">The status will then be changed to **Canceled**.</span></span>

> [!NOTE]
> <span data-ttu-id="9e209-116">Az állapot változásainak megjelenítéséhez a **Frissítés** gombra kattintva frissíteni kell az oldalt.</span><span class="sxs-lookup"><span data-stu-id="9e209-116">To see status changes, you must refresh the page by selecting the **Refresh** button.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9e209-117">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="9e209-117">Additional resources</span></span>

[<span data-ttu-id="9e209-118">Tervezési optimalizálás áttekintése</span><span class="sxs-lookup"><span data-stu-id="9e209-118">Planning Optimization overview</span></span>](planning-optimization-overview.md)

[<span data-ttu-id="9e209-119">Tervezési optimalizálás indítása</span><span class="sxs-lookup"><span data-stu-id="9e209-119">Get started with Planning Optimization</span></span>](get-started.md)

[<span data-ttu-id="9e209-120">A tervezésoptimalizálása illeszkedési elemzése</span><span class="sxs-lookup"><span data-stu-id="9e209-120">Planning Optimization fit analysis</span></span>](planning-optimization-fit-analysis.md)

[<span data-ttu-id="9e209-121">Tervelőzmények és tervezési naplók megtekintése</span><span class="sxs-lookup"><span data-stu-id="9e209-121">View plan history and planning logs</span></span>](plan-history-logs.md)

[<span data-ttu-id="9e209-122">Szűrők alkalmazása egy tervre</span><span class="sxs-lookup"><span data-stu-id="9e209-122">Apply filters to a plan</span></span>](plan-filters.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]