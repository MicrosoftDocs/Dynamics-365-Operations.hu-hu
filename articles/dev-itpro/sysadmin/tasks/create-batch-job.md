---
title: Kötegelt feladat létrehozása
description: A kötegelt feladat egy Alkalmazásobjektum-kiszolgáló (AOS) példányához elküldött feladatcsoport az automatikus feldolgozáshoz.
author: maertenm
manager: AnnBe
ms.date: 06/21/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BatchJob, SysRecurrence, BatchAlerts
audience: Application User
ms.reviewer: margoc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d211dcd7cb47df135d395d2a993429746aa35a85
ms.sourcegitcommit: 6ba4006fb6a67ddd4b1e54e3d62b9d1239b5e5a3
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/21/2019
ms.locfileid: "1700841"
---
# <a name="create-a-batch-job"></a><span data-ttu-id="ef816-103">Kötegelt feladat létrehozása</span><span class="sxs-lookup"><span data-stu-id="ef816-103">Create a batch job</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ef816-104">A kötegelt feladat egy Alkalmazásobjektum-kiszolgáló (AOS) példányához elküldött feladatcsoport az automatikus feldolgozáshoz.</span><span class="sxs-lookup"><span data-stu-id="ef816-104">A batch job is a group of tasks that are submitted to an Application Object Server (AOS) instance for automatic processing.</span></span> <span data-ttu-id="ef816-105">A Kötegelt feladatok futtatása a feladatot létrehozó felhasználó biztonsági hitelesítő adatainak használatával történik.</span><span class="sxs-lookup"><span data-stu-id="ef816-105">Batch jobs are run by using the security credentials of the user who created the job.</span></span> <span data-ttu-id="ef816-106">A következő eljárásokkal lehet meghatározni a kötegelt feladatot.</span><span class="sxs-lookup"><span data-stu-id="ef816-106">Use the following procedure to create a batch job.</span></span> <span data-ttu-id="ef816-107">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="ef816-107">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-the-batch-job"></a><span data-ttu-id="ef816-108">Kötegelt feladat létrehozása</span><span class="sxs-lookup"><span data-stu-id="ef816-108">Create the batch job</span></span>
1. <span data-ttu-id="ef816-109">Ugorjon a **Navigációs lap > Modulok > Rendszerfelügyelet > Lekérdezések > Kötegelt feladatok** pontra.</span><span class="sxs-lookup"><span data-stu-id="ef816-109">Go to **Navigation pane > Modules > System administration > Inquiries > Batch jobs**.</span></span>
2. <span data-ttu-id="ef816-110">Kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="ef816-110">Click **New**.</span></span>
3. <span data-ttu-id="ef816-111">A **Munkaköri leírás** mezőbe írjon be egy értéket.</span><span class="sxs-lookup"><span data-stu-id="ef816-111">In the **Job description** field, type a value.</span></span>
4. <span data-ttu-id="ef816-112">Az **Ütemezett kezdő dátum/idő** mezőben adjon meg egy dátumot és időt.</span><span class="sxs-lookup"><span data-stu-id="ef816-112">In the **Scheduled start date/time** field, enter a date and time.</span></span>
5. <span data-ttu-id="ef816-113">Kattintson a **Mentés** gombra.</span><span class="sxs-lookup"><span data-stu-id="ef816-113">Click **Save**.</span></span>

## <a name="create-a-recurrence"></a><span data-ttu-id="ef816-114">Ismétlődés létrehozása</span><span class="sxs-lookup"><span data-stu-id="ef816-114">Create a recurrence</span></span>
1. <span data-ttu-id="ef816-115">Kattintson a Művelet panelen a **Kötegelt feladat** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="ef816-115">On the Action Pane, click **Batch job**.</span></span>
2. <span data-ttu-id="ef816-116">Kattintson az **Ismétlődésre**.</span><span class="sxs-lookup"><span data-stu-id="ef816-116">Click **Recurrence**.</span></span> <span data-ttu-id="ef816-117">E beállítások segítségével megadhatja az ismétlődés tartományát és a mintáját.</span><span class="sxs-lookup"><span data-stu-id="ef816-117">Use these options to enter a range and pattern for the recurrence.</span></span>  
3. <span data-ttu-id="ef816-118">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="ef816-118">Click **OK**.</span></span>

## <a name="add-alerts"></a><span data-ttu-id="ef816-119">Figyelmeztetések hozzáadása</span><span class="sxs-lookup"><span data-stu-id="ef816-119">Add alerts</span></span>
1. <span data-ttu-id="ef816-120">Kattintson a Művelet panelen a **Kötegelt feladat** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="ef816-120">On the Action Pane, click **Batch job**.</span></span>
2. <span data-ttu-id="ef816-121">Kattintson a **Figyelmeztetések** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="ef816-121">Click **Alerts**.</span></span> <span data-ttu-id="ef816-122">Jelezze, ha szeretne figyelmeztető üzenetet kapni a kötegelt feladat befejeződése, meghibásodása vagy törlődése esetén.</span><span class="sxs-lookup"><span data-stu-id="ef816-122">Indicate if you want alert messages sent when the batch job ends, has an error, or is canceled.</span></span> <span data-ttu-id="ef816-123">Adja meg, ha azt szeretné, hogy a figyelmeztetések előugró üzenetekként jelenjenek meg.</span><span class="sxs-lookup"><span data-stu-id="ef816-123">Then specify if you want the alerts to be displayed as pop-up messages.</span></span>   
3. <span data-ttu-id="ef816-124">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="ef816-124">Click **OK**.</span></span>

## <a name="adjust-batch-job-status"></a><span data-ttu-id="ef816-125">Kötegelt feladat állapotának beállítása</span><span class="sxs-lookup"><span data-stu-id="ef816-125">Adjust batch job status</span></span>
1. <span data-ttu-id="ef816-126">Ugorjon a **Rendszerfelügyelet > Lekérdezések > Kötegelt feladatok** pontra.</span><span class="sxs-lookup"><span data-stu-id="ef816-126">Go to **System administration > Inquiries > Batch jobs**.</span></span>
2. <span data-ttu-id="ef816-127">Jelölje ki a megfelelő kötegelt feladatokat.</span><span class="sxs-lookup"><span data-stu-id="ef816-127">Select the appropriate batch job.</span></span>
3. <span data-ttu-id="ef816-128">Kattintson a Művelet panelen a **Kötegelt feladat > Funkciók > Állapot módosítása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="ef816-128">On the Action Pane, click **Batch job > Functions > Change status**.</span></span>
4. <span data-ttu-id="ef816-129">Válassza ki a megfelelő állapotot.</span><span class="sxs-lookup"><span data-stu-id="ef816-129">Select the appropriate status:</span></span>
    - <span data-ttu-id="ef816-130">**Visszatartás**: A kötegelt feladat **visszatartási** értékre állítása, így a kötegelt munkaütemezőből visszatartható.</span><span class="sxs-lookup"><span data-stu-id="ef816-130">**Withhold**: Set the batch job as **withhold** so it is withheld from the batch job scheduler.</span></span> <span data-ttu-id="ef816-131">A *leállítással* egyenértékű.</span><span class="sxs-lookup"><span data-stu-id="ef816-131">Equivalent to *stop*.</span></span>
    - <span data-ttu-id="ef816-132">**Várakozás**: A kötegelt feladat **várakozásra** történő beállítása, így a kötegelt munkaütemező által elindítható.</span><span class="sxs-lookup"><span data-stu-id="ef816-132">**Waiting**: Set the batch job as **waiting** so it is waiting to be picked up by the batch job scheduler.</span></span> <span data-ttu-id="ef816-133">A *mehettel* egyenértékű.</span><span class="sxs-lookup"><span data-stu-id="ef816-133">Equivalent to *go*.</span></span>
5. <span data-ttu-id="ef816-134">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="ef816-134">Click **OK**.</span></span>
