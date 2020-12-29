---
title: Eszköz életciklus-állapotai
description: Ez a témakör az Eszközkezelés modul eszköz-életciklusállapotait és életciklus-modelljeit írja le.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetLifecycleModelStateNext, EntAssetObjectLifecycleState, EntAssetLifecycleStateUpdate, EntAssetObjectLifecycleModel
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 566036c6361194d910a0fc34bd5d72147585ec4f
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4429424"
---
# <a name="asset-lifecycle-states"></a><span data-ttu-id="67b9d-103">Eszköz életciklus-állapotai</span><span class="sxs-lookup"><span data-stu-id="67b9d-103">Asset lifecycle states</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="67b9d-104">Ez a témakör az Eszközkezelés modul eszköz-életciklusállapotait és életciklus-modelljeit írja le.</span><span class="sxs-lookup"><span data-stu-id="67b9d-104">This topic explains asset lifecycle states and lifecycle models in Asset Management.</span></span> <span data-ttu-id="67b9d-105">Az eszköz életciklus-állapota határozza meg, hogy az eszköz aktív vagy inaktív-e.</span><span class="sxs-lookup"><span data-stu-id="67b9d-105">Asset lifecycle states are used to define whether an asset is active or inactive.</span></span> <span data-ttu-id="67b9d-106">Például beállíthat olyan eszköz-életciklusállapotokat, mint **Létrehozott**, **Aktív** vagy **Megszakított**.</span><span class="sxs-lookup"><span data-stu-id="67b9d-106">For example, you can set up asset lifecycle states such as **Created**, **Active**, and **Terminated**.</span></span>

> [!NOTE]
> - <span data-ttu-id="67b9d-107">A kérések életciklus-állapotai kapcsolódnak az eszköz életciklus-állapotaihoz.</span><span class="sxs-lookup"><span data-stu-id="67b9d-107">Request lifecycle states are linked to asset lifecycle states.</span></span> <span data-ttu-id="67b9d-108">Ezért ha egy kérés új kérési életciklus-állapotra módosul, akkor a kéréshez csatolt eszköz életciklus-állapota is egy újra módosul.</span><span class="sxs-lookup"><span data-stu-id="67b9d-108">Therefore, when a request is changed to a new request lifecycle state, the asset that is attached to the request is changed to a new asset lifecycle state.</span></span> <span data-ttu-id="67b9d-109">Például ha egy kérés életciklus-állapota **Bejövő** lesz, akkor a csatolt eszköz életciklus-állapota arra az életciklus-állapotra módosul, amelyet az **Eszköz életciklus-állapotának modelljei** oldal **Eszköz életciklus-állapot** gyorslapjának **Bejövő életciklus-állapot** mezőjében ki van választva.</span><span class="sxs-lookup"><span data-stu-id="67b9d-109">For example, if the lifecycle state of a request is changed to **Inbound**, the lifecycle state of the attached asset is changed to the lifecycle state that is selected in the **Inbound lifecycle state** field on the **Asset lifecycle state** FastTab of the **Asset lifecycle state models** page.</span></span> 


<span data-ttu-id="67b9d-110">Az eszközéletciklus-állapotok beállíthatók az eszköz életciklusmodelljein, ahol meghatározhatja a különböző típusú eszközökhöz szükséges életciklus-állapotokat.</span><span class="sxs-lookup"><span data-stu-id="67b9d-110">Asset lifecycle states can be set up in asset lifecycle models, where you can define the required lifecycle states for various types of assets.</span></span> <span data-ttu-id="67b9d-111">Először be kell állítani az életciklus-állapotokat.</span><span class="sxs-lookup"><span data-stu-id="67b9d-111">You first set up lifecycle states.</span></span> <span data-ttu-id="67b9d-112">Ezután létre kell hoznia egy életciklusmodellt, és ki kell választania a hozzá tartozó életciklus-állapotokat.</span><span class="sxs-lookup"><span data-stu-id="67b9d-112">You then create a lifecycle model and select lifecycle states for it.</span></span>

1. <span data-ttu-id="67b9d-113">Válassza ki az **Eszközkezelés** \> **Beállítás** \> **Eszközök** \> **Életciklus-állapotok** elemet.</span><span class="sxs-lookup"><span data-stu-id="67b9d-113">Select **Asset management** \> **Setup** \> **Assets** \> **Lifecycle states**.</span></span>
2. <span data-ttu-id="67b9d-114">Válassza az **Új** lehetőséget egy új eszköz életciklus-állapot létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="67b9d-114">Select **New** to create a new asset lifecycle state.</span></span>
3. <span data-ttu-id="67b9d-115">Az **Életciklus-állapot** mezőben adja meg az életciklus-állapot azonosítóját.</span><span class="sxs-lookup"><span data-stu-id="67b9d-115">In the **Lifecycle state** field, enter the lifecycle state ID.</span></span>
4. <span data-ttu-id="67b9d-116">A **Név** mezőbe adja meg a leírást.</span><span class="sxs-lookup"><span data-stu-id="67b9d-116">In the **Name** field, enter a description.</span></span>

    <span data-ttu-id="67b9d-117">Az **Életciklusmodellek** mezőben látható az adott eszközéletciklus-állapotot használó életciklusmodellek száma.</span><span class="sxs-lookup"><span data-stu-id="67b9d-117">The **Lifecycle models** field shows the number of asset lifecycle models that use the asset lifecycle state.</span></span>

5. <span data-ttu-id="67b9d-118">Állítsa az **Aktív** beállítást **Igen** értékre, ha ez az életciklus-állapot aktív életciklus-állapot legyen (azaz munkarendeléseket lehet létrehoznia az ilyen életciklus-állapotú eszközökhöz).</span><span class="sxs-lookup"><span data-stu-id="67b9d-118">Set the **Active** option to **Yes** if this lifecycle state should be an active lifecycle state (in other words, if work orders can be created for assets that are in this lifecycle state).</span></span>
6. <span data-ttu-id="67b9d-119">Állítsa a **Nyitott naptársorok törlése** beállítást **Igen** értékre, ha a **Létrehozott** eszközéletciklus-állapottal rendelkező nyitott eszköznaptársorokat törölni kell, ha ebben az életciklus-állapoban vannak.</span><span class="sxs-lookup"><span data-stu-id="67b9d-119">Set the **Delete open calendar lines** option to **Yes** if open asset calendar lines that have an asset lifecycle state of **Created** should be deleted when they are in this lifecycle state.</span></span> <span data-ttu-id="67b9d-120">Ez a beállítás akkor hasznos, ha el szeretné takarítani azokat a nyitott karbantartási ütemezéseket, amelyek az eszköz szempontjából már nem relevánsak (például, ha az eszköz már nem aktív).</span><span class="sxs-lookup"><span data-stu-id="67b9d-120">This setting is useful if you want to clean up any open maintenance schedules that are no longer relevant for the asset (for example, if the asset is no longer active).</span></span>

> [!NOTE]
> <span data-ttu-id="67b9d-121">Az eszközéletciklus-állapotok, eszközéletciklus-modellek és eszköztípusok kapcsolódnak egymáshoz.</span><span class="sxs-lookup"><span data-stu-id="67b9d-121">Asset lifecycle states, asset lifecycle models, and asset types are related.</span></span> <span data-ttu-id="67b9d-122">Ugyanúgy használhatók, mint a munkarendelések életciklus-állapotai, a munkarendelés életciklus-modelljei és a munkarendelés-típusok.</span><span class="sxs-lookup"><span data-stu-id="67b9d-122">They are used in the same way as work order lifecycle states, work order lifecycle models, and work order types.</span></span> 


<span data-ttu-id="67b9d-123">Miután létrehozta a szükséges eszközéletciklus-állapotokat, beállíthat életciklus-állapotokat az eszközéletciklus-modellekben.</span><span class="sxs-lookup"><span data-stu-id="67b9d-123">After you've created the required asset lifecycle states, you can set up lifecycle states in asset lifecycle models.</span></span>

1. <span data-ttu-id="67b9d-124">Válassza ki az **Eszközkezelés** \> **Beállítás** \> **Eszközök** \> **Életciklusmodellek** elemet.</span><span class="sxs-lookup"><span data-stu-id="67b9d-124">Select **Asset management** \> **Setup** \> **assets** \> **lifecycle models**.</span></span>
2. <span data-ttu-id="67b9d-125">Válassza az **Új** lehetőséget egy új eszköz életciklusmodell létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="67b9d-125">Select **New** to create a new asset lifecycle model.</span></span>
3. <span data-ttu-id="67b9d-126">Az **Életciklusmodell** mezőben adja meg az életciklusmodell azonosítóját.</span><span class="sxs-lookup"><span data-stu-id="67b9d-126">In the **Lifecycle model** field, enter the lifecycle model ID.</span></span>
4. <span data-ttu-id="67b9d-127">A **Név** mezőbe adja meg a leírást.</span><span class="sxs-lookup"><span data-stu-id="67b9d-127">In the **Name** field, enter a description.</span></span>

    <span data-ttu-id="67b9d-128">Az **Életciklus-állapotok** mezőben látható az adott eszközéletciklus-modellben kiválasztott eszközéletciklus-állapotok száma.</span><span class="sxs-lookup"><span data-stu-id="67b9d-128">The **Lifecycle states** field shows the number of asset lifecycle states that are selected in the asset lifecycle model.</span></span> <span data-ttu-id="67b9d-129">Az **Eszköztípusok** mezőben az életciklusmodellt használó eszköztípusok száma látható.</span><span class="sxs-lookup"><span data-stu-id="67b9d-129">The **Asset types** field shows the number of asset types that use the lifecycle model.</span></span>

5. <span data-ttu-id="67b9d-130">Az **Életciklus-állapotok** gyorslapon válassza ki azokat az eszközéletciklus-állapotokat, amelyeket fel kell venni az eszközéletciklus-modellbe:</span><span class="sxs-lookup"><span data-stu-id="67b9d-130">On the **Lifecycle states** FastTab, select the asset lifecycle states that should be included in the asset lifecycle model:</span></span>

    - <span data-ttu-id="67b9d-131">A modellben használandó életciklus-állapotot válassza ki a **Hátralevő életciklus-állapotok** szakaszban, majd a jobbra nyíl ![Jobbra nyíl](media/15-setup-for-objects.png) gombbal helyezze át a **Kijelölt életciklus-állapotok** szakaszba.</span><span class="sxs-lookup"><span data-stu-id="67b9d-131">To use a lifecycle state for the model, select it in the **Lifecycle states remaining** section, and then select the right arrow button ![Right arrow](media/15-setup-for-objects.png) to move it to the **Lifecycle states selected** section.</span></span>
    - <span data-ttu-id="67b9d-132">Ahhoz, hogy az összes elérhető életciklus-állapotot használhassa a modellhez, nyomja meg az **Összes elérhető életciklus-állapot** ![Összes elérhető életciklus-állapot](media/20-setup-for-objects.png) gombot.</span><span class="sxs-lookup"><span data-stu-id="67b9d-132">To use all the available lifecycle states for the model, select the **All available lifecycle states** button ![All available lifecycle states](media/20-setup-for-objects.png).</span></span> <span data-ttu-id="67b9d-133">Az összes életciklus-állapot a **Kijelölt életciklus-állapotok** szakaszba kerül.</span><span class="sxs-lookup"><span data-stu-id="67b9d-133">All lifecycle states are transferred to the **Lifecycle states selected** section.</span></span>
    - <span data-ttu-id="67b9d-134">Ha el kíván távolítani egy életciklus-állapotot a modellből, válassza ki az adott állapotot a **Kijelölt életciklus-állapotok** szakaszban, majd a Balra nyíl ![Balra nyíl](media/16-setup-for-objects.png) gombbal helyezze át a **Hátralévő életciklus-állapotok** szakaszba.</span><span class="sxs-lookup"><span data-stu-id="67b9d-134">To remove a lifecycle state from the model, select it in the **lifecycle states selected** section, and then select the left arrow button ![Left arrow](media/16-setup-for-objects.png) to move it to the **Lifecycle states remaining** section.</span></span>

6. <span data-ttu-id="67b9d-135">Válassza az **Életciklus-állapot frissítései** elemet, amellyel meghatározhatja a kijelölt életciklus-állapotot követő eszközéletciklus-állapotokat.</span><span class="sxs-lookup"><span data-stu-id="67b9d-135">Select **Lifecycle state updates** to define the asset lifecycle states that can follow a selected lifecycle state.</span></span>
7. <span data-ttu-id="67b9d-136">Az **Eszközállapot** gyorslapon a javításra kapott eszközök kezelése használható.</span><span class="sxs-lookup"><span data-stu-id="67b9d-136">You use the **Asset state** FastTab if you handle assets that you receive for repair.</span></span> <span data-ttu-id="67b9d-137">A **Bejövő/kimenő** szakaszban kiválaszthat eszközéletciklus-állapotokat, amelyekkel jelezheti a javításra kapott eszköz munkafolyamatát.</span><span class="sxs-lookup"><span data-stu-id="67b9d-137">In the **Inbound/outbound** section, you can select asset lifecycle states to indicate the workflow of an asset that you receive for repair.</span></span> <span data-ttu-id="67b9d-138">Ha ügyfelei vagy részlegei számára hiteleszközöket kínál, akkor a **Kölcsön** részben kiválaszthatja a kölcsönzött eszközökre vonatkozó életciklus-állapotokat.</span><span class="sxs-lookup"><span data-stu-id="67b9d-138">If you offer loan assets to customers or departments, in the **Loan** section, you can select lifecycle states for loan assets.</span></span>
