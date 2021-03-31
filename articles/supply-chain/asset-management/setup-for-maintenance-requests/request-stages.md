---
title: Karbantartási kérések életciklus-állapotai
description: Ez a témakör azt ismerteti, hogy miként állíthatja be a karbantartási kérés életciklus-állapotait az Eszközkezelés modulban.
author: josaw1
manager: tfehr
ms.date: 04/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetRequestLifecycleState, EntAssetRequestLifecycleModel
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9022d866bf0da08a72ba9169587f87c1b77527a6
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5217221"
---
# <a name="maintenance-request-lifecycle-states"></a><span data-ttu-id="a581c-103">Karbantartási kérések életciklus-állapotai</span><span class="sxs-lookup"><span data-stu-id="a581c-103">Maintenance request lifecycle states</span></span>

[!include [banner](../../includes/banner.md)]

 


<span data-ttu-id="a581c-104">A karbantartási kérés életciklus-állapotai meghatározzák, hogy a kérés milyen fázisokon mehet keresztül.</span><span class="sxs-lookup"><span data-stu-id="a581c-104">Maintenance request lifecycle states define the stages that a request can go through.</span></span> <span data-ttu-id="a581c-105">Ilyen fázis például a **Létrehozva**, **Aktív** és **Befejezve** állapot.</span><span class="sxs-lookup"><span data-stu-id="a581c-105">Examples include **Created**, **Active**, and **Ended**.</span></span> <span data-ttu-id="a581c-106">A karbantartási kérés munkarendeléssé átalakításakor a karbantartási kérés életciklus-állapotát **Befejezve** vagy **Lezárt** állapotúra kell frissíteni, ha a karbantartási kérés már nem aktív.</span><span class="sxs-lookup"><span data-stu-id="a581c-106">When a maintenance request is converted to a work order, the maintenance request lifecycle state should be updated to **Ended** or **Closed** to indicate that the maintenance request is no longer active.</span></span> <span data-ttu-id="a581c-107">Az **Összes karbantartási kérés** listaoldalán megtekintheti az összes karbantartási kérést, függetlenül azok életciklus-állapotától.</span><span class="sxs-lookup"><span data-stu-id="a581c-107">On the **All maintenance requests** list page, you can view all maintenance requests, regardless of their lifecycle state.</span></span>

## <a name="set-up-maintenance-request-lifecycle-states"></a><span data-ttu-id="a581c-108">Karbantartási kérés életciklus-állapotainak beállítása</span><span class="sxs-lookup"><span data-stu-id="a581c-108">Set up maintenance request lifecycle states</span></span>

1. <span data-ttu-id="a581c-109">Válassza ki az **Eszközkezelés** \> **Beállítás** \> **Karbantartási kérések** \> **Életciklus-állapotok** elemet.</span><span class="sxs-lookup"><span data-stu-id="a581c-109">Select **Asset management** \> **Setup** \> **Maintenance requests** \> **Lifecycle states**.</span></span>
2. <span data-ttu-id="a581c-110">Válassza ki az **Új** elemet egy karbantartási kérés életciklus-állapotának létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="a581c-110">Select **New** to create a maintenance request lifecycle state.</span></span>
3. <span data-ttu-id="a581c-111">Az **Életciklus-állapot** mezőben adja meg az életciklus-állapot azonosítóját.</span><span class="sxs-lookup"><span data-stu-id="a581c-111">In the **Lifecycle state** field, enter an ID for the lifecycle state.</span></span>
4. <span data-ttu-id="a581c-112">A **Név** mezőben adjon meg egy nevet.</span><span class="sxs-lookup"><span data-stu-id="a581c-112">In the **Name** field, enter a name.</span></span>

    <span data-ttu-id="a581c-113">A **Részletek** gyorslapon az **Életciklusmodellek** mezőben látható az adott életciklus-állapotot használó karbantartási kérés életciklusmodelljeinek a száma.</span><span class="sxs-lookup"><span data-stu-id="a581c-113">On the **Details** FastTab, the **Lifecycle models** field shows the number of maintenance request lifecycle models that use this lifecycle state.</span></span>

5. <span data-ttu-id="a581c-114">Az **Általános** gyorslapon állítsa az **Aktív** beállítást **Igen** értékre, ha a karbantartási kérésnek mindaddig aktívnak kell lennie, amíg ebben az életciklus-állapotban van.</span><span class="sxs-lookup"><span data-stu-id="a581c-114">On the **General** FastTab, set the **Active** option to **Yes** if a maintenance request should be active while it's in this lifecycle state.</span></span>
6. <span data-ttu-id="a581c-115">Állítsa a **Tényleges befejezés beállítása** lehetőséget **Igen** értékre, ha az ebben az életciklus-állapotban lévő karbantartási kérésben automatikusan meg kell adni egy tényleges befejezési dátumot és időpontot.</span><span class="sxs-lookup"><span data-stu-id="a581c-115">Set the **Set actual end** option to **Yes** if an actual end date and time should automatically be entered on a maintenance request that is in this lifecycle state.</span></span>
7. <span data-ttu-id="a581c-116">Állítsa a **Munkarendelés létrehozása** beállítást **Igen** értékre, ha az ebben az életciklus-állapotban lévő karbantartási kérésből munkarendelés hozható létre.</span><span class="sxs-lookup"><span data-stu-id="a581c-116">Set the **Create work order** option to **Yes** if a work order can be created from a maintenance request that is in this lifecycle state.</span></span>
8. <span data-ttu-id="a581c-117">Állítsa a **Törlés** lehetőséget **Igen** értékre, ha a karbantartási kérés törölhető, amíg ebben az életciklus-állapotban van.</span><span class="sxs-lookup"><span data-stu-id="a581c-117">Set the **Delete** option to **Yes** if a maintenance request can be deleted while it's in this lifecycle state.</span></span>
9. <span data-ttu-id="a581c-118">A **Frissítés** gyorslapon az **Eszköz** szakaszának **Bejövő** és **Kimenő** beállításai akkor fontosak, ha a raktárjavítást használ.</span><span class="sxs-lookup"><span data-stu-id="a581c-118">On the **Update** FastTab, the **Inbound** and **Outbound** options in the **Asset** section are relevant if you use depot repair.</span></span> <span data-ttu-id="a581c-119">A megfelelő beállítást akkor kell **Igen** értékre beállítani, ha a karbantartási kérelemben kiválasztott eszközök életciklus-állapotát automatikusan **Bejövő** vagy **Kimenő** állapotúra kell módosítani, amikor a karbantartási kérelem életciklus-állapota **Bejövő** vagy **Kimenő** értékre van állítva.</span><span class="sxs-lookup"><span data-stu-id="a581c-119">Set the appropriate option to **Yes** if the asset lifecycle state of assets that are selected on a maintenance request should automatically be updated to **Inbound** or **Outbound** when the maintenance request lifecycle state of that maintenance request is set to **Inbound** or **Outbound**.</span></span>

<span data-ttu-id="a581c-120">A következő ábra a **Karbantartási kérések életciklus-állapotai** oldalt szemlélteti.</span><span class="sxs-lookup"><span data-stu-id="a581c-120">The follow illustration shows an example of the **Maintenance request lifecycle states** page.</span></span>

![Karbantartási kérések életciklus-állapotai oldal](media/02-setup-for-requests.png)

> [!NOTE]
> <span data-ttu-id="a581c-122">A karbantartási kérések életciklus-állapotait, az életciklus-állapot csoportjait és típusait ugyanúgy használják, mint a munkarendelés életciklus-állapotait, csoportjait és típusai.</span><span class="sxs-lookup"><span data-stu-id="a581c-122">Maintenance request lifecycle states, lifecycle state groups, and types are related to, and used in the same way as, work order lifecycle states, lifecycle state groups, and types.</span></span> 

## <a name="set-up-maintenance-request-lifecycle-models"></a><span data-ttu-id="a581c-123">Karbantartási kérés életciklusmodelljeinek beállítása</span><span class="sxs-lookup"><span data-stu-id="a581c-123">Set up maintenance request lifecycle models</span></span>

<span data-ttu-id="a581c-124">Miután létrehozta a karbantartási kérésekhez szükséges életciklus-állapotokat, azok feloszthatók életciklusállapot-csoportokra vagy -modellekre.</span><span class="sxs-lookup"><span data-stu-id="a581c-124">After you've created the lifecycle states that are required for your maintenance requests, they can be divided into lifecycle state groups, or lifecycle models.</span></span> <span data-ttu-id="a581c-125">A karbantartási kérések életciklusmodelljei segítségével különböző típusú karbantartási kérésekhez felhasználható áramlási folyamatot hozhat létre.</span><span class="sxs-lookup"><span data-stu-id="a581c-125">Maintenance request lifecycle models are used to create the flow that can be used for different types of maintenance requests.</span></span> <span data-ttu-id="a581c-126">Legalább egy szabványos karbantartási kéréshez tartozó életciklus-modellt létre kell hozni.</span><span class="sxs-lookup"><span data-stu-id="a581c-126">At a minimum, one standard maintenance request lifecycle model should be created.</span></span>

1. <span data-ttu-id="a581c-127">Válassza ki az **Eszközkezelés** \> **Beállítás** \> **Karbantartási kérések** \> **Életciklus-modellek** elemet.</span><span class="sxs-lookup"><span data-stu-id="a581c-127">Select **Asset management** \> **Setup** \> **Maintenance requests** \> **Lifecycle models**.</span></span>
2. <span data-ttu-id="a581c-128">Válassza ki az **Új** elemet egy karbantartási kérés életciklusmodelljének létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="a581c-128">Select **New** to create a maintenance request lifecycle model.</span></span>
3. <span data-ttu-id="a581c-129">Az **Életciklusmodell** mezőben adja meg az életciklusmodell azonosítóját.</span><span class="sxs-lookup"><span data-stu-id="a581c-129">In the **Lifecycle model** field, enter an ID for the lifecycle model.</span></span>
4. <span data-ttu-id="a581c-130">A **Név** mezőben adjon meg egy nevet.</span><span class="sxs-lookup"><span data-stu-id="a581c-130">In the **Name** field, enter a name.</span></span>

    <span data-ttu-id="a581c-131">A **Részletek** gyorslapon az **Életciklus-állapotok** mezőben látható az adott életciklusmodellben kiválasztott életciklus-állapotok száma.</span><span class="sxs-lookup"><span data-stu-id="a581c-131">On the **Details** FastTab, the **Lifecycle states** shows the number of lifecycle states that are selected in this lifecycle model.</span></span> <span data-ttu-id="a581c-132">A **Karbantartási kérések típusai** mezőben az ezen életciklus-modellt használó karbantartási kérések típusainak száma látható.</span><span class="sxs-lookup"><span data-stu-id="a581c-132">The **Maintenance request types** field shows the number of maintenance request types that use this lifecycle model.</span></span>

5. <span data-ttu-id="a581c-133">Az **Életciklus-állapotok** gyorslapon válassza ki azokat az életciklus-állapotokat, amelyeket fel kell venni az életciklus-modellbe:</span><span class="sxs-lookup"><span data-stu-id="a581c-133">On the **Lifecycle states** FastTab, select the lifecycle states that should be included in the lifecycle model:</span></span>

    - <span data-ttu-id="a581c-134">Az életciklus-modellben feltüntetendő életciklus-állapotot válassza ki a **Hátralevő életciklus-állapotok** szakaszban, majd a jobbra nyíl ![Jobbra nyíl](media/03-setup-for-requests.png) gombbal helyezze át a **Kijelölt életciklus-állapotok** szakaszba.</span><span class="sxs-lookup"><span data-stu-id="a581c-134">To include a lifecycle state in the lifecycle model, select it in the **Lifecycle states remaining** section, and then select the right arrow button ![Right arrow](media/03-setup-for-requests.png) to move it to the **Lifecycle states selected** section.</span></span>
    - <span data-ttu-id="a581c-135">Ahhoz, hogy az összes elérhető életciklus-állapotot feltüntesse az életciklus-modellben, nyomja meg az **Összes elérhető állapot** ![Összes elérhető állapot](media/04-setup-for-requests.png) gombot.</span><span class="sxs-lookup"><span data-stu-id="a581c-135">To include all the available lifecycle states in the lifecycle model, select the **Select all available states** button ![Select all available states](media/04-setup-for-requests.png).</span></span> <span data-ttu-id="a581c-136">Az összes életciklus-állapot a **Kijelölt életciklus-állapotok** szakaszba kerül.</span><span class="sxs-lookup"><span data-stu-id="a581c-136">All lifecycle states are moved to the **Lifecycle states selected** section.</span></span>
    - <span data-ttu-id="a581c-137">Ha el kíván távolítani egy életciklus-állapotot az életciklus-modellből, válassza ki az adott állapotot a **Kijelölt életciklus-állapotok** szakaszban, majd a Balra nyíl ![Balra nyíl](media/05-setup-for-requests.png) gombbal helyezze át a **Hátralévő életciklus-állapotok** szakaszba.</span><span class="sxs-lookup"><span data-stu-id="a581c-137">To remove a lifecycle state from the lifecycle model, select it in the **Lifecycle states selected** section, and then select the left arrow button ![Left arrow](media/05-setup-for-requests.png) to move it to the **Lifecycle states remaining** section.</span></span>

6. <span data-ttu-id="a581c-138">Az **Általános** gyorslapon a **Frissítések** szakasz mezői a relevánsak, ha raktárjavítást használ.</span><span class="sxs-lookup"><span data-stu-id="a581c-138">On the **General** FastTab, the fields in the **Updates** section are relevant if you use depot repair.</span></span>

    - <span data-ttu-id="a581c-139">A **Bevételezett eszköz életciklus-állapota** mezőben válassza ki azt az eszközéletciklus-állapotot, amelyre a karbantartási kérésnél kiválasztott eszközöket automatikusan frissíteni kell, amikor beérkeznek raktárjavításhoz.</span><span class="sxs-lookup"><span data-stu-id="a581c-139">In the **Lifecycle state for asset received** field, select the asset lifecycle state that assets that are selected on a maintenance request should automatically be updated to when they are received for depot repair.</span></span>
    - <span data-ttu-id="a581c-140">A **Kiszállított eszköz életciklus-állapota** mezőben válassza ki azt az eszközéletciklus-állapotot, amelyre a karbantartási kérésnél kiválasztott eszközöket automatikusan frissíteni kell, amikor visszaérkeznek javítás után.</span><span class="sxs-lookup"><span data-stu-id="a581c-140">In the **Lifecycle state for asset delivered** field, select the lifecycle state that assets that are selected on a maintenance request should automatically be updated to when they are returned after repair.</span></span>

<span data-ttu-id="a581c-141">A következő ábra a **Karbantartási kérések életciklusmodellek** oldalt szemlélteti.</span><span class="sxs-lookup"><span data-stu-id="a581c-141">The following illustration shows an example of the **Maintenance request lifecycle models** page.</span></span>

![Karbantartási kérés életciklusmodelljei oldal](media/06-setup-for-requests.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]