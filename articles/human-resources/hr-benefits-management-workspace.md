---
title: Juttatáskezelési munkaterület
description: Ez a témakör a Dynamics 365 Human Resources Juttatáskezelési munkaterületét részletezi.
author: andreabichsel
manager: tfehr
ms.date: 02/24/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-24
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 8f17685dab8159522ec88af0fa6ca9c99c346b7b
ms.sourcegitcommit: 105f65468b45799761c26e5d0ad9df4ff162c38d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/04/2021
ms.locfileid: "5488201"
---
# <a name="benefits-management-workspace"></a><span data-ttu-id="9d245-103">Juttatáskezelési munkaterület</span><span class="sxs-lookup"><span data-stu-id="9d245-103">Benefits management workspace</span></span>

[!include [applies to](../includes/applies-to-hr.md)]

[!include [preview feature](./includes/preview-feature.md)]

<span data-ttu-id="9d245-104">Ez a témakör a Dynamics 365 Human Resources **Juttatáskezelési munkaterületét** részletezi.</span><span class="sxs-lookup"><span data-stu-id="9d245-104">This topic describes the **Benefits management** workspace in Dynamics 365 Human Resources.</span></span>

> [!NOTE]
> <span data-ttu-id="9d245-105">A **Juttatáskezelés** munkaterület megtekintéséhez először engedélyeznie kell a Funkciókezelés **(Előzetes verzió) Juttatáskezelési munkaterület** funkcióját.</span><span class="sxs-lookup"><span data-stu-id="9d245-105">To view the **Benefits management** workspace, you must first enable the **(Preview) Benefits management workspace** feature in Feature management.</span></span> <span data-ttu-id="9d245-106">Az előzetes funkciók aktiválásával kapcsolatos további részletekért tekintse meg a [Szolgáltatások kezelése](../hr-admin-manage-features.md) oldalt.</span><span class="sxs-lookup"><span data-stu-id="9d245-106">For more information about enabling preview features, see [Manage features](../hr-admin-manage-features.md).</span></span><br><br><span data-ttu-id="9d245-107">![Juttatáskezelési munkaterület engedélyezése](./media/hr-benefits-management-workspace-enable.png)</span><span class="sxs-lookup"><span data-stu-id="9d245-107">![Enable Benefits management workspace](./media/hr-benefits-management-workspace-enable.png)</span></span>

<span data-ttu-id="9d245-108">A **Juttatáskezelés** munkaterület használatával gyorsan megtekinthetők azok a juttatások, amelyekre figyelni kell.</span><span class="sxs-lookup"><span data-stu-id="9d245-108">The **Benefits management** workspace gives you a quick view of benefits items that require your attention.</span></span> <span data-ttu-id="9d245-109">Ezen az oldalon a következők láthatók:</span><span class="sxs-lookup"><span data-stu-id="9d245-109">On this page, you can see:</span></span>

- <span data-ttu-id="9d245-110">Műveletre váró cikkek összegei</span><span class="sxs-lookup"><span data-stu-id="9d245-110">Totals for items awaiting action</span></span>
- <span data-ttu-id="9d245-111">Nem megerősített kijelölésű dolgozók</span><span class="sxs-lookup"><span data-stu-id="9d245-111">Workers with unconfirmed selections</span></span>
- <span data-ttu-id="9d245-112">Juttatásokra nemrég regisztrált dolgozók</span><span class="sxs-lookup"><span data-stu-id="9d245-112">Workers who recently enrolled in benefits</span></span>
- <span data-ttu-id="9d245-113">Dolgozók jövőbeli életeseményekkel</span><span class="sxs-lookup"><span data-stu-id="9d245-113">Workers with future life events</span></span>
- <span data-ttu-id="9d245-114">Nem regisztrált új felvételek</span><span class="sxs-lookup"><span data-stu-id="9d245-114">New hires who aren't enrolled</span></span>
- <span data-ttu-id="9d245-115">Dolgozók aktív életeseményekkel</span><span class="sxs-lookup"><span data-stu-id="9d245-115">Workers with active life events</span></span>
- <span data-ttu-id="9d245-116">Azok a dolgozók, akiknek nyitott regisztrációjuk van, és egyetlen konstrukciót sem választottak</span><span class="sxs-lookup"><span data-stu-id="9d245-116">Workers with open enrollments who haven't opted for any plans</span></span>

![Juttatáskezelési munkaterület](./media/hr-benefits-management-workspace.png)

## <a name="view-action-items"></a><span data-ttu-id="9d245-118">Műveletelemek megtekintése</span><span class="sxs-lookup"><span data-stu-id="9d245-118">View action items</span></span>

<span data-ttu-id="9d245-119">A művelet elemeit csempe vagy lap kiválasztásával lehet megtekinteni. Ha kiválaszt egy lapot, a munkaterületi oldalon megtekintheti és kiválaszthatja a dolgozókat.</span><span class="sxs-lookup"><span data-stu-id="9d245-119">You can view your action items by either selecting a tile or a tab. If you select a tab, you can view and select workers right on the workspace page.</span></span>

![Műveletelemek](./media/hr-benefits-management-workspace-action-items.png)

<span data-ttu-id="9d245-121">Ha egy csempét választ ki, akkor az arra a területre vonatkozó oldalra lép.</span><span class="sxs-lookup"><span data-stu-id="9d245-121">If you select a tile, you go to the page for that area.</span></span> <span data-ttu-id="9d245-122">Például ezen csempék valamelyikének kiválasztása a **Dolgozói juttatási konstrukció** oldalt jeleníti mega, azokra az alkalmazottakra szűrve, akik esetében műveletet kell végeznie:</span><span class="sxs-lookup"><span data-stu-id="9d245-122">For example, selecting any of these tiles displays the **Worker benefits plans** page, filtered for employees you need to take action on:</span></span>

- <span data-ttu-id="9d245-123">**Meg nem erősített kiválasztások**</span><span class="sxs-lookup"><span data-stu-id="9d245-123">**Unconfirmed selections**</span></span>
- <span data-ttu-id="9d245-124">**Nyitott beléptetések kivett konstrukciók nélkül**</span><span class="sxs-lookup"><span data-stu-id="9d245-124">**Open enrollments with no checked out plans**</span></span>
- <span data-ttu-id="9d245-125">**Juttatáshoz beléptetve**</span><span class="sxs-lookup"><span data-stu-id="9d245-125">**Enrolled in benefits**</span></span>
- <span data-ttu-id="9d245-126">**Az újonnan felvett dolgozó nincs beléptetve**</span><span class="sxs-lookup"><span data-stu-id="9d245-126">**New hire not enrolled**</span></span>

![Dolgozói juttatási konstrukciók](./media/hr-benefits-management-workspace-plans.png)

<span data-ttu-id="9d245-128">Az **Aktív életesemények** és a **Jövőbeli életesemények** kiválasztása az aktív vagy jövőbeli életesemények listájára viszi.</span><span class="sxs-lookup"><span data-stu-id="9d245-128">Selecting the **Active life events** or **Future life events** tiles takes you to a list of active or future life events.</span></span>

![Életesemények](./media/hr-benefits-management-workspace-life-events.png)

## <a name="processing"></a><span data-ttu-id="9d245-130">Feldolgozás folyamatban</span><span class="sxs-lookup"><span data-stu-id="9d245-130">Processing</span></span>

<span data-ttu-id="9d245-131">A felvételi jogosultságok, az életesemények és a díjváltozások frissítéseinek feldolgozásához jelölje ki a megfelelő elemet a navigációs sávon.</span><span class="sxs-lookup"><span data-stu-id="9d245-131">To process enrollment eligibility, life events, or rate change updates, select the appropriate item on the navigation bar.</span></span>

![Feldolgozás folyamatban](./media/hr-benefits-management-workspace-processing.png)

<span data-ttu-id="9d245-133">A folyamat eredményeinek megtekintéséhez válassza a **Folyamateredmények** lehetőséget az oldalon.</span><span class="sxs-lookup"><span data-stu-id="9d245-133">To view process results, select **Process results** on the page.</span></span>

![Folyamateredmények](./media/hr-benefits-management-workspace-process-results.png)

<span data-ttu-id="9d245-135">A juttatások feldolgozásával kapcsolatos további információkért lásd:</span><span class="sxs-lookup"><span data-stu-id="9d245-135">For more information about benefits processing, see:</span></span>

- [<span data-ttu-id="9d245-136">Felvételi jogosultság feldolgozása</span><span class="sxs-lookup"><span data-stu-id="9d245-136">Process enrollment eligibility</span></span>](hr-benefits-process-enrollment-eligibility.md)
- [<span data-ttu-id="9d245-137">Életesemények változásainak feldolgozása</span><span class="sxs-lookup"><span data-stu-id="9d245-137">Process life event changes</span></span>](hr-benefits-process-life-event-changes.md)
- [<span data-ttu-id="9d245-138">Életesemény-jogosultság feldolgozása</span><span class="sxs-lookup"><span data-stu-id="9d245-138">Process life event eligibility</span></span>](hr-benefits-process-life-event-eligibility.md)
- [<span data-ttu-id="9d245-139">Életesemények feldolgozása</span><span class="sxs-lookup"><span data-stu-id="9d245-139">Process life events</span></span>](hr-benefits-process-life-events.md)
- [<span data-ttu-id="9d245-140">Módosítások arányának feldolgozása</span><span class="sxs-lookup"><span data-stu-id="9d245-140">Process rate changes</span></span>](hr-benefits-process-rate-changes.md)

## <a name="change-period"></a><span data-ttu-id="9d245-141">Időszak módosítása</span><span class="sxs-lookup"><span data-stu-id="9d245-141">Change period</span></span>

<span data-ttu-id="9d245-142">Ha egy másik juttatási időszakot is meg kell tekinteni, válassza ki az **Időszak** legördülő menüből.</span><span class="sxs-lookup"><span data-stu-id="9d245-142">To view a different benefits period, select it from the **Period** dropdown.</span></span>

![Időszak módosítása](./media/hr-benefits-management-workspace-period.png)

## <a name="view-more-options"></a><span data-ttu-id="9d245-144">További beállítások megtekintése</span><span class="sxs-lookup"><span data-stu-id="9d245-144">View more options</span></span>

<span data-ttu-id="9d245-145">További adatok és műveletek megtekintéséhez válassza a **Hivatkozások** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9d245-145">To view more information and actions you can take, select **Links**.</span></span>

![Hivatkozások](./media/hr-benefits-management-workspace-links.png)

## <a name="see-also"></a><span data-ttu-id="9d245-147">Lásd még</span><span class="sxs-lookup"><span data-stu-id="9d245-147">See also</span></span>

[<span data-ttu-id="9d245-148">Juttatáskezelés áttekintése</span><span class="sxs-lookup"><span data-stu-id="9d245-148">Benefits management overview</span></span>](hr-benefits-management-overview.md)