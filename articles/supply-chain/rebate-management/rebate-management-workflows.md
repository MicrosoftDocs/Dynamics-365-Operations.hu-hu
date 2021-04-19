---
title: Visszatérítés-kezelési ügylet munkafolyamatai
description: Ez a témakör bemutatja, hogyan lehet beállítani visszatérítés-kezelési ügylet munkafolyamatát az ügyletek jóváhagyásához és aktiválásához.
author: sherry-zheng
ms.date: 02/19/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WorkflowTableListPageRnr
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-19
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: 37b8022633e61c4d98d6f5d129bcf494a9ed92e0
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5831722"
---
# <a name="rebate-management-deal-workflows"></a><span data-ttu-id="889dc-103">Visszatérítés-kezelési ügylet munkafolyamatai</span><span class="sxs-lookup"><span data-stu-id="889dc-103">Rebate management deal workflows</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="889dc-104">Visszatérítési ügyletek jóváhagyásához a visszatérítés-kezelés a többi Finance and Operations-alkalmazással azonos munkafolyamat-platformot használja.</span><span class="sxs-lookup"><span data-stu-id="889dc-104">To approve rebate deals, Rebate management uses the same workflow platform as other Finance and Operations apps.</span></span> <span data-ttu-id="889dc-105">Minden munkafolyamathoz két feladatfolyamat van társítva:</span><span class="sxs-lookup"><span data-stu-id="889dc-105">Two job processes are associated with every workflow:</span></span>

- <span data-ttu-id="889dc-106">A munkafolyamat egyik eleme aktiválja az ügyletet, így a felhasználó vagy munkafolyamat jóváhagyhatja a tranzakciókat.</span><span class="sxs-lookup"><span data-stu-id="889dc-106">One element of the workflow activates the deal so that the user or workflow process can approve the transactions.</span></span>
- <span data-ttu-id="889dc-107">A munkafolyamat egyik eleme jóváhagyja az ügyletet.</span><span class="sxs-lookup"><span data-stu-id="889dc-107">One element of the workflow approves the deal.</span></span>

<span data-ttu-id="889dc-108">Visszatérítési ügylet használata előtt aktívnak kell lennie a **Visszatérítés-kezelés** modulban.</span><span class="sxs-lookup"><span data-stu-id="889dc-108">Before you can use a rebate deal, it must be active in the **Rebate management** module.</span></span> <span data-ttu-id="889dc-109">Az ügylet aktiválásához előbb létre kell hoznia és be kell állítania egy *Visszatérítés-kezelési ügylet munkafolyamatát*.</span><span class="sxs-lookup"><span data-stu-id="889dc-109">To activate a deal, you must first create and configure a *Rebate management deal workflow*.</span></span>

<span data-ttu-id="889dc-110">Miután aktiváltak egy munkafolyamatot a Visszatérítés-kezeléshez, a felhasználók manuálisan nem hagyhatnak jóvá ügyleteket.</span><span class="sxs-lookup"><span data-stu-id="889dc-110">After a workflow is activated for Rebate management, users can't manually approve deals.</span></span> <span data-ttu-id="889dc-111">A munkafolyamatot mindig használni kell.</span><span class="sxs-lookup"><span data-stu-id="889dc-111">The workflow must be always used.</span></span>

## <a name="create-and-manage-rebate-management-deal-workflows"></a><span data-ttu-id="889dc-112">Visszatérítés-kezelési ügyletek munkafolyamatainak létrehozása és kezelése</span><span class="sxs-lookup"><span data-stu-id="889dc-112">Create and manage Rebate management deal workflows</span></span>

<span data-ttu-id="889dc-113">A Visszatérítés-kezelési ügylet munkafolyamataival való munkához lépjen a **Visszatérítés-kezelés \> Beállítás \> Visszatérítés-kezelési munkafolyamatok** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="889dc-113">To work with your Rebate management deal workflows, go to **Rebate management \> Setup \> Rebate management workflows**.</span></span> <span data-ttu-id="889dc-114">A munkafolyamatokat szükség szerint megtekintheti, létrehozhatja és frissítheti.</span><span class="sxs-lookup"><span data-stu-id="889dc-114">There, you can view, create, and update workflows as required.</span></span> <span data-ttu-id="889dc-115">Egyszerre csak egy ilyen típusú munkafolyamat lehet aktív.</span><span class="sxs-lookup"><span data-stu-id="889dc-115">Only one workflow of this type can be active at a time.</span></span> <span data-ttu-id="889dc-116">A munkafolyamatokkal, a **Visszatérítés-kezelési munkafolyamatok** oldalon végzett munkával és a munkafolyamatok létrehozásával kapcsolatos további információkért tekintse meg a [Munkafolyamati rendszer áttekintése](../../fin-ops-core/fin-ops/organization-administration/overview-workflow-system.md) részt és a kapcsolódó témaköröket.</span><span class="sxs-lookup"><span data-stu-id="889dc-116">For more information about workflows, how to work with the **Rebate management workflows** page, and how to create workflows, see [Workflow system overview](../../fin-ops-core/fin-ops/organization-administration/overview-workflow-system.md) and its related topics.</span></span>

## <a name="use-a-workflow-to-activate-a-deal"></a><span data-ttu-id="889dc-117">Munkafolyamat használata ügylet aktiválásához</span><span class="sxs-lookup"><span data-stu-id="889dc-117">Use a workflow to activate a deal</span></span>

<span data-ttu-id="889dc-118">Ha egy ügyletet egy munkafolyamaton keresztül szeretne aktiválni, nyissa meg az ügyletet (például az **Összes visszatérítés-kezelési ügylet** oldalon).</span><span class="sxs-lookup"><span data-stu-id="889dc-118">To activate a deal through a workflow, open the deal (for example, on the **All rebate management deals** page).</span></span> <span data-ttu-id="889dc-119">Majd a műveleti ablaktáblán válassza ki a **Munkafolyamat \> Elküldés** elemet.</span><span class="sxs-lookup"><span data-stu-id="889dc-119">Then, on the Action Pane, select **Workflow \> Submit**.</span></span> <span data-ttu-id="889dc-120">Az új ügylet munkafolyamaton keresztüli feldolgozása és jóváhagyása után aktív lesz, és használatra kész.</span><span class="sxs-lookup"><span data-stu-id="889dc-120">After the new deal has been processed and approved through the workflow, it will be active and ready to use.</span></span>

<span data-ttu-id="889dc-121">Az ügylet aktiválása után a beállítása nem változtatható meg.</span><span class="sxs-lookup"><span data-stu-id="889dc-121">After a deal has been activated, you can't change its setup.</span></span> <span data-ttu-id="889dc-122">Ha módosítania kell egy aktív ügyletet, inaktiválnia kell, majd létre kell hoznia egy új ügyletet.</span><span class="sxs-lookup"><span data-stu-id="889dc-122">If you must change an active deal, inactivate it, and then create a new deal.</span></span> <span data-ttu-id="889dc-123">Ha az új ügylet hasonlít a régi ügyletre, akkor a régi ügylet másolásával is létrehozhatja.</span><span class="sxs-lookup"><span data-stu-id="889dc-123">If the new deal will resemble the old deal, you can create it by copying the old deal.</span></span>
