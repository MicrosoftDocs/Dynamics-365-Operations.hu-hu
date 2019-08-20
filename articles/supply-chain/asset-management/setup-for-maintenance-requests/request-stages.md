---
title: Karbantartási kérések életciklus-állapotai
description: Ez a témakör azt ismerteti, hogy miként állíthatja be a karbantartási kérés életciklus-állapotait az Eszközkezelés modulban.
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
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f68e11a1cd14bc35282b957a4262cbecdd627b3b
ms.sourcegitcommit: 2c73749779274e0b0abbcb4041bbc1df0fb6d6e4
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/26/2019
ms.locfileid: "1790502"
---
# <a name="maintenance-request-states"></a><span data-ttu-id="8e289-103">Karbantartási kérés állapotai</span><span class="sxs-lookup"><span data-stu-id="8e289-103">Maintenance request states</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


<span data-ttu-id="8e289-104">A karbantartási kérés életciklus-állapotai meghatározzák, hogy a kérés milyen fázisokon mehet keresztül.</span><span class="sxs-lookup"><span data-stu-id="8e289-104">Maintenance request lifecycle states define the stages that a request can go through.</span></span> <span data-ttu-id="8e289-105">Ilyen fázis például a **Létrehozva**, **Aktív** és **Befejezve** állapot.</span><span class="sxs-lookup"><span data-stu-id="8e289-105">Examples include **Created**, **Active**, and **Ended**.</span></span> <span data-ttu-id="8e289-106">A karbantartási kérés munkarendeléssé átalakításakor a karbantartási kérés életciklus-állapotát **Befejezve** vagy **Lezárt** állapotúra kell frissíteni, ha a karbantartási kérés már nem aktív.</span><span class="sxs-lookup"><span data-stu-id="8e289-106">When a maintenance request is converted to a work order, the maintenance request lifecycle state should be updated to **Ended** or **Closed** to indicate that the maintenance request is no longer active.</span></span> <span data-ttu-id="8e289-107">Az **Összes karbantartási kérés** listaoldalán megtekintheti az összes karbantartási kérést, függetlenül azok életciklus-állapotától.</span><span class="sxs-lookup"><span data-stu-id="8e289-107">On the **All maintenance requests** list page, you can view all maintenance requests, regardless of their lifecycle state.</span></span>

## <a name="set-up-maintenance-request-lifecycle-states"></a><span data-ttu-id="8e289-108">Karbantartási kérés életciklus-állapotainak beállítása</span><span class="sxs-lookup"><span data-stu-id="8e289-108">Set up maintenance request lifecycle states</span></span>

1. <span data-ttu-id="8e289-109">Válassza ki az **Eszközkezelés** \> **Beállítás** \> **Karbantartási kérések** \> **Életciklus-állapotok** elemet.</span><span class="sxs-lookup"><span data-stu-id="8e289-109">Select **Asset management** \> **Setup** \> **Maintenance requests** \> **Lifecycle states**.</span></span>
2. <span data-ttu-id="8e289-110">Válassza ki az **Új** elemet egy karbantartási kérés életciklus-állapotának létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="8e289-110">Select **New** to create a maintenance request lifecycle state.</span></span>
3. <span data-ttu-id="8e289-111">Az **Életciklus-állapot** mezőben adja meg az életciklus-állapot azonosítóját.</span><span class="sxs-lookup"><span data-stu-id="8e289-111">In the **Lifecycle state** field, enter an ID for the lifecycle state.</span></span>
4. <span data-ttu-id="8e289-112">A **Név** mezőben adjon meg egy nevet.</span><span class="sxs-lookup"><span data-stu-id="8e289-112">In the **Name** field, enter a name.</span></span>

    <span data-ttu-id="8e289-113">A **Részletek** gyorslapon az **Életciklusmodellek** mezőben látható az adott életciklus-állapotot használó karbantartási kérés életciklusmodelljeinek a száma.</span><span class="sxs-lookup"><span data-stu-id="8e289-113">On the **Details** FastTab, the **Lifecycle models** field shows the number of maintenance request lifecycle models that use this lifecycle state.</span></span>

5. <span data-ttu-id="8e289-114">Az **Általános** gyorslapon állítsa az **Aktív** beállítást **Igen** értékre, ha a karbantartási kérésnek mindaddig aktívnak kell lennie, amíg ebben az életciklus-állapotban van.</span><span class="sxs-lookup"><span data-stu-id="8e289-114">On the **General** FastTab, set the **Active** option to **Yes** if a maintenance request should be active while it's in this lifecycle state.</span></span>
6. <span data-ttu-id="8e289-115">Állítsa a **Tényleges befejezés beállítása** lehetőséget **Igen**értékre, ha az ebben az életciklus-állapotban lévő karbantartási kérésben automatikusan meg kell adni egy tényleges befejezési dátumot és időpontot.</span><span class="sxs-lookup"><span data-stu-id="8e289-115">Set he **Set actual end** option to **Yes** if an actual end date and time should automatically be entered on a maintenance request that is in this lifecycle state.</span></span>
7. <span data-ttu-id="8e289-116">Állítsa a **Munkarendelés létrehozása** beállítást **Igen** értékre, ha az ebben az életciklus-állapotban lévő karbantartási kérésből munkarendelés hozható létre.</span><span class="sxs-lookup"><span data-stu-id="8e289-116">Set the **Create work order** option to **Yes** if a work order can be created from a maintenance request that is in this lifecycle state.</span></span>
8. <span data-ttu-id="8e289-117">Állítsa a **Törlés** lehetőséget **Igen** értékre, ha a karbantartási kérés törölhető, amíg ebben az életciklus-állapotban van.</span><span class="sxs-lookup"><span data-stu-id="8e289-117">Set the **Delete** option to **Yes** if a maintenance request can be deleted while it's in this lifecycle state.</span></span>
9. <span data-ttu-id="8e289-118">A **Frissítés** gyorslapon az **Eszköz** szakaszban található **Bejövő** és **Kimenő** lehetőségek akkor relevánsak, ha Ön raktárjavítást használ. Állítsa a megfelelő opciót **Igen** értékre, ha a karbantartási kérésben kiválasztott eszközök eszközéletciklus-állapotát automatikusan **Bejövő** vagy **Kimenő** állapotra kell frissíteni, amennyiben a karbantartási kérés életciklus-állapota **Bejövő** vagy **Kimenő** értékre van állítva.</span><span class="sxs-lookup"><span data-stu-id="8e289-118">On the **Update** FastTab, the **Inbound** and **Outbound** options in the **Asset** section are relevant if you use depot repair.cSet the appropriate option to **Yes** if the asset lifecycle state of assets that are selected on a maintenance request should automatically be updated to **Inbound** or **Outbound** when the maintenance request lifecycle state of that maintenance request is set to **Inbound** or **Outbound**.</span></span>

<span data-ttu-id="8e289-119">A következő ábra a **Karbantartási kérések életciklus-állapotai** oldalt szemlélteti.</span><span class="sxs-lookup"><span data-stu-id="8e289-119">The follow illustration shows an example of the **Maintenance request lifecycle states** page.</span></span>

![1. ábra](media/02-setup-for-requests.png)

> [!NOTE]
> <span data-ttu-id="8e289-121">A karbantartási kérések életciklus-állapotait, az életciklus-állapot csoportjait és típusait ugyanúgy használják, mint a munkarendelés életciklus-állapotait, csoportjait és típusai.</span><span class="sxs-lookup"><span data-stu-id="8e289-121">Maintenance request lifecycle states, lifecycle state groups, and types are related to, and used in the same way as, work order lifecycle states, lifecycle state groups, and types.</span></span> 

## <a name="set-up-maintenance-request-lifecycle-models"></a><span data-ttu-id="8e289-122">Karbantartási kérés életciklusmodelljeinek beállítása</span><span class="sxs-lookup"><span data-stu-id="8e289-122">Set up maintenance request lifecycle models</span></span>

<span data-ttu-id="8e289-123">Miután létrehozta a karbantartási kérésekhez szükséges életciklus-állapotokat, azok feloszthatók életciklusállapot-csoportokra vagy -modellekre.</span><span class="sxs-lookup"><span data-stu-id="8e289-123">After you've created the lifecycle states that are required for your maintenance requests, they can be divided into lifecycle state groups, or lifecycle models.</span></span> <span data-ttu-id="8e289-124">A karbantartási kérések életciklusmodelljei segítségével különböző típusú karbantartási kérésekhez felhasználható áramlási folyamatot hozhat létre.</span><span class="sxs-lookup"><span data-stu-id="8e289-124">Maintenance request lifecycle models are used to create the flow that can be used for different types of maintenance requests.</span></span> <span data-ttu-id="8e289-125">Legalább egy szabványos karbantartási kéréshez tartozó életciklus-modellt létre kell hozni.</span><span class="sxs-lookup"><span data-stu-id="8e289-125">At a minimum, one standard maintenance request lifecycle model should be created.</span></span>

1. <span data-ttu-id="8e289-126">Válassza ki az **Eszközkezelés** \> **Beállítás** \> **Karbantartási kérések** \> **Életciklus-modellek** elemet.</span><span class="sxs-lookup"><span data-stu-id="8e289-126">Select **Asset management** \> **Setup** \> **Maintenance requests** \> **Lifecycle models**.</span></span>
2. <span data-ttu-id="8e289-127">Válassza ki az **Új** elemet egy karbantartási kérés életciklusmodelljének létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="8e289-127">Select **New** to create a maintenance request lifecycle model.</span></span>
3. <span data-ttu-id="8e289-128">Az **Életciklusmodell** mezőben adja meg az életciklusmodell azonosítóját.</span><span class="sxs-lookup"><span data-stu-id="8e289-128">In the **Lifecycle model** field, enter an ID for the lifecycle model.</span></span>
4. <span data-ttu-id="8e289-129">A **Név** mezőben adjon meg egy nevet.</span><span class="sxs-lookup"><span data-stu-id="8e289-129">In the **Name** field, enter a name.</span></span>

    <span data-ttu-id="8e289-130">A **Részletek** gyorslapon az **Életciklus-állapotok** mezőben látható az adott életciklusmodellben kiválasztott életciklus-állapotok száma.</span><span class="sxs-lookup"><span data-stu-id="8e289-130">On the **Details** FastTab, the **Lifecycle states** shows the number of lifecycle states that are selected in this lifecycle model.</span></span> <span data-ttu-id="8e289-131">A **Karbantartási kérések típusai** mezőben az ezen életciklus-modellt használó karbantartási kérések típusainak száma látható.</span><span class="sxs-lookup"><span data-stu-id="8e289-131">The **Maintenance request types** field shows the number of maintenance request types that use this lifecycle model.</span></span>

5. <span data-ttu-id="8e289-132">Az **Életciklus-állapotok** gyorslapon válassza ki azokat az életciklus-állapotokat, amelyeket fel kell venni az életciklus-modellbe:</span><span class="sxs-lookup"><span data-stu-id="8e289-132">On the **Lifecycle states** FastTab, select the lifecycle states that should be included in the lifecycle model:</span></span>

    - <span data-ttu-id="8e289-133">Az életciklus-modellben feltüntetendő életciklus-állapotot válassza ki a **Hátralevő életciklus-állapotok** szakaszban, majd a jobbra nyíl ![Jobbra nyíl](media/03-setup-for-requests.png) gombbal helyezze át a **Kijelölt életciklus-állapotok** szakaszba.</span><span class="sxs-lookup"><span data-stu-id="8e289-133">To include a lifecycle state in the lifecycle model, select it in the **Lifecycle states remaining** section, and then select the right arrow button ![Right arrow](media/03-setup-for-requests.png) to move it to the **Lifecycle states selected** section.</span></span>
    - <span data-ttu-id="8e289-134">Ahhoz, hogy az összes elérhető életciklus-állapotot feltüntesse az életciklus-modellben, nyomja meg az **Összes elérhető állapot** ![Összes elérhető állapot](media/04-setup-for-requests.png) gombot.</span><span class="sxs-lookup"><span data-stu-id="8e289-134">To include all the available lifecycle states in the lifecycle model, select the **Select all available states** button ![Select all available states](media/04-setup-for-requests.png).</span></span> <span data-ttu-id="8e289-135">Az összes életciklus-állapot a **Kijelölt életciklus-állapotok** szakaszba kerül.</span><span class="sxs-lookup"><span data-stu-id="8e289-135">All lifecycle states are moved to the **Lifecycle states selected** section.</span></span>
    - <span data-ttu-id="8e289-136">Ha el kíván távolítani egy életciklus-állapotot az életciklus-modellből, válassza ki az adott állapotot a **Kijelölt életciklus-állapotok** szakaszban, majd a Balra nyíl ![Balra nyíl](media/05-setup-for-requests.png) gombbal helyezze át a **Hátralévő életciklus-állapotok** szakaszba.</span><span class="sxs-lookup"><span data-stu-id="8e289-136">To remove a lifecycle state from the lifecycle model, select it in the **Lifecycle states selected** section, and then select the left arrow button ![Left arrow](media/05-setup-for-requests.png) to move it to the **Lifecycle states remaining** section.</span></span>

6. <span data-ttu-id="8e289-137">Az **Általános** gyorslapon a **Frissítések** szakasz mezői a relevánsak, ha raktárjavítást használ.</span><span class="sxs-lookup"><span data-stu-id="8e289-137">On the **General** FastTab, the fields in the **Updates** section are relevant if you use depot repair.</span></span>

    - <span data-ttu-id="8e289-138">A **Bevételezett eszköz életciklus-állapota** mezőben válassza ki azt az eszközéletciklus-állapotot, amelyre a karbantartási kérésnél kiválasztott eszközöket automatikusan frissíteni kell, amikor beérkeznek raktárjavításhoz.</span><span class="sxs-lookup"><span data-stu-id="8e289-138">In the **Lifecycle state for asset received** field, select the asset lifecycle state that assets that are selected on a maintenance request should automatically be updated to when they are received for depot repair.</span></span>
    - <span data-ttu-id="8e289-139">A **Kiszállított eszköz életciklus-állapota** mezőben válassza ki azt az eszközéletciklus-állapotot, amelyre a karbantartási kérésnél kiválasztott eszközöket automatikusan frissíteni kell, amikor visszaérkeznek javítás után.</span><span class="sxs-lookup"><span data-stu-id="8e289-139">In the **Lifecycle state for asset delivered** field, select the lifecycle state that assets that are selected on a maintenance request should automatically be updated to when they are returned after repair.</span></span>

<span data-ttu-id="8e289-140">A következő ábra a **Karbantartási kérések életciklusmodellek** oldalt szemlélteti.</span><span class="sxs-lookup"><span data-stu-id="8e289-140">The following illustration shows an example of the **Maintenance request lifecycle models** page.</span></span>

![2. ábra](media/06-setup-for-requests.png)
