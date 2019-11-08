---
title: Karbantartási kérések típusai
description: Ez a témakör azt mutatja be, hogyan lehet karbantartási kérések típusait beállítani az Eszközkezelés modulban.
author: josaw1
manager: AnnBe
ms.date: 07/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-07-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 430e475b52638dd80512ffd79d42aac6f5f340e1
ms.sourcegitcommit: d37fb09101c30858bcb975931b3d8f947d72017b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/10/2019
ms.locfileid: "2571139"
---
# <a name="maintenance-request-types"></a><span data-ttu-id="540b3-103">Karbantartási kérések típusai</span><span class="sxs-lookup"><span data-stu-id="540b3-103">Maintenance request types</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="540b3-104">A karbantartási kérések típusai a karbantartási kérések kategorizálására szolgálnak.</span><span class="sxs-lookup"><span data-stu-id="540b3-104">Maintenance request types are used to categorize maintenance requests.</span></span> <span data-ttu-id="540b3-105">A karbantartásikérés-típusok kapcsolódhatnak például megelőző karbantartáshoz és hibaelhárító karbantartáshoz.</span><span class="sxs-lookup"><span data-stu-id="540b3-105">For example, you might have maintenance request types that are related to preventive maintenance and corrective maintenance.</span></span> <span data-ttu-id="540b3-106">A karbantartási kérésnek olyan speciális típusa is lehet, amelyet eszközök javításának kezelésére használnak (raktárjavítás).</span><span class="sxs-lookup"><span data-stu-id="540b3-106">Or you might have a special maintenance request type that is used to manage repair of assets (depot repair).</span></span>

<span data-ttu-id="540b3-107">A karbantartási kérés típusa határozza meg a karbantartási kéréshez tartozó életciklusállapot-csoportokkal (karbantartási életciklus-modell) való viszonyt.</span><span class="sxs-lookup"><span data-stu-id="540b3-107">A maintenance request type defines the affiliation with a maintenance request lifecycle state group (maintenance lifecycle model).</span></span> <span data-ttu-id="540b3-108">A karbantartási kérések életciklusmodelljei határozzák meg a karbantartási kérésekhez beállítható életciklus-állapotokat.</span><span class="sxs-lookup"><span data-stu-id="540b3-108">Maintenance request lifecycle models define the lifecycle states that can be set for a maintenance request.</span></span> <span data-ttu-id="540b3-109">(Karbantartási kérés életciklus-állapota például a **Létrehozva**, az **Aktív** és a **Befejezve** fázis.)</span><span class="sxs-lookup"><span data-stu-id="540b3-109">(Examples of maintenance request lifecycle states include **Created**, **Active**, and **Ended**.)</span></span>

1. <span data-ttu-id="540b3-110">Válassza az **Eszközkezelés** \> **Beállítás** \> **Karbantartási kérések** \> **Karbantartási kérések típusai** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="540b3-110">Select **Asset management** \> **Setup** \> **Maintenance requests** \> **Maintenance request types**.</span></span>
2. <span data-ttu-id="540b3-111">Válassza ki az **Új** elemet egy karbantartási kérés típusának létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="540b3-111">Select **New** to create a maintenance request type.</span></span>
3. <span data-ttu-id="540b3-112">A **Karbantartási kérés típusa** mezőben adja meg a karbantartási kérés típusának azonosítóját.</span><span class="sxs-lookup"><span data-stu-id="540b3-112">In the **Maintenance request type** field, enter an ID for the maintenance request type.</span></span>
4. <span data-ttu-id="540b3-113">A **Név** mezőben adjon meg egy nevet.</span><span class="sxs-lookup"><span data-stu-id="540b3-113">In the **Name** field, enter a name.</span></span>
5. <span data-ttu-id="540b3-114">Az **Általános** gyorslapon a **Karbantartási kérés életciklusmodellje** mezőben válasszon ki egy karbantartási kéréshez tartozó életciklusmodellt.</span><span class="sxs-lookup"><span data-stu-id="540b3-114">On the **General** FastTab, in the **Maintenance request lifecycle model** field, select a maintenance request lifecycle model.</span></span>
6. <span data-ttu-id="540b3-115">A **Munkarendelés típusa** mezőben válasszon ki egy munkarendelés-típust.</span><span class="sxs-lookup"><span data-stu-id="540b3-115">In the **Work order type** field, select a work order type.</span></span> <span data-ttu-id="540b3-116">A karbantartási kérés munkarendeléssé alakításakor a munkarendelés automatikusan megkapja azt a munkarendelés-típust, amely a karbantartási kérés típusához kapcsolódik.</span><span class="sxs-lookup"><span data-stu-id="540b3-116">When a maintenance request is converted to a work order, the work order automatically gets the work order type that is related to the maintenance request type.</span></span>

<span data-ttu-id="540b3-117">A következő ábra a **Karbantartási kérés típusai** oldalt szemlélteti.</span><span class="sxs-lookup"><span data-stu-id="540b3-117">The following illustration shows an example of the **Maintenance request types** page.</span></span>

![Karbantartási kérések típusai oldal](media/07-setup-for-requests.png)
