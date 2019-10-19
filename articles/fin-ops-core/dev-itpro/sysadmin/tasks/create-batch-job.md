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
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 27541c84a40fe9b7e7705162e06167ad4f7e4ed9
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/27/2019
ms.locfileid: "2191385"
---
# <a name="create-a-batch-job"></a><span data-ttu-id="d363f-103">Kötegelt feladat létrehozása</span><span class="sxs-lookup"><span data-stu-id="d363f-103">Create a batch job</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d363f-104">A kötegelt feladat egy Alkalmazásobjektum-kiszolgáló (AOS) példányához elküldött feladatcsoport az automatikus feldolgozáshoz.</span><span class="sxs-lookup"><span data-stu-id="d363f-104">A batch job is a group of tasks that are submitted to an Application Object Server (AOS) instance for automatic processing.</span></span> <span data-ttu-id="d363f-105">A Kötegelt feladatok futtatása a feladatot létrehozó felhasználó biztonsági hitelesítő adatainak használatával történik.</span><span class="sxs-lookup"><span data-stu-id="d363f-105">Batch jobs are run by using the security credentials of the user who created the job.</span></span> <span data-ttu-id="d363f-106">A következő eljárásokkal lehet meghatározni a kötegelt feladatot.</span><span class="sxs-lookup"><span data-stu-id="d363f-106">Use the following procedure to create a batch job.</span></span> <span data-ttu-id="d363f-107">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="d363f-107">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-the-batch-job"></a><span data-ttu-id="d363f-108">Kötegelt feladat létrehozása</span><span class="sxs-lookup"><span data-stu-id="d363f-108">Create the batch job</span></span>
1. <span data-ttu-id="d363f-109">Ugorjon a **Navigációs lap > Modulok > Rendszerfelügyelet > Lekérdezések > Kötegelt feladatok** pontra.</span><span class="sxs-lookup"><span data-stu-id="d363f-109">Go to **Navigation pane > Modules > System administration > Inquiries > Batch jobs**.</span></span>
2. <span data-ttu-id="d363f-110">Kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="d363f-110">Click **New**.</span></span>
3. <span data-ttu-id="d363f-111">A **Munkaköri leírás** mezőbe írjon be egy értéket.</span><span class="sxs-lookup"><span data-stu-id="d363f-111">In the **Job description** field, type a value.</span></span>
4. <span data-ttu-id="d363f-112">Az **Ütemezett kezdő dátum/idő** mezőben adjon meg egy dátumot és időt.</span><span class="sxs-lookup"><span data-stu-id="d363f-112">In the **Scheduled start date/time** field, enter a date and time.</span></span>
5. <span data-ttu-id="d363f-113">Kattintson a **Mentés** gombra.</span><span class="sxs-lookup"><span data-stu-id="d363f-113">Click **Save**.</span></span>

## <a name="create-a-recurrence"></a><span data-ttu-id="d363f-114">Ismétlődés létrehozása</span><span class="sxs-lookup"><span data-stu-id="d363f-114">Create a recurrence</span></span>
1. <span data-ttu-id="d363f-115">Kattintson a Művelet panelen a **Kötegelt feladat** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d363f-115">On the Action Pane, click **Batch job**.</span></span>
2. <span data-ttu-id="d363f-116">Kattintson az **Ismétlődésre**.</span><span class="sxs-lookup"><span data-stu-id="d363f-116">Click **Recurrence**.</span></span> <span data-ttu-id="d363f-117">E beállítások segítségével megadhatja az ismétlődés tartományát és a mintáját.</span><span class="sxs-lookup"><span data-stu-id="d363f-117">Use these options to enter a range and pattern for the recurrence.</span></span>  
3. <span data-ttu-id="d363f-118">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="d363f-118">Click **OK**.</span></span>

## <a name="add-alerts"></a><span data-ttu-id="d363f-119">Figyelmeztetések hozzáadása</span><span class="sxs-lookup"><span data-stu-id="d363f-119">Add alerts</span></span>
1. <span data-ttu-id="d363f-120">Kattintson a Művelet panelen a **Kötegelt feladat** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d363f-120">On the Action Pane, click **Batch job**.</span></span>
2. <span data-ttu-id="d363f-121">Kattintson a **Figyelmeztetések** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d363f-121">Click **Alerts**.</span></span> <span data-ttu-id="d363f-122">Jelezze, ha szeretne figyelmeztető üzenetet kapni a kötegelt feladat befejeződése, meghibásodása vagy törlődése esetén.</span><span class="sxs-lookup"><span data-stu-id="d363f-122">Indicate if you want alert messages sent when the batch job ends, has an error, or is canceled.</span></span> <span data-ttu-id="d363f-123">Adja meg, ha azt szeretné, hogy a figyelmeztetések előugró üzenetekként jelenjenek meg.</span><span class="sxs-lookup"><span data-stu-id="d363f-123">Then specify if you want the alerts to be displayed as pop-up messages.</span></span>   
3. <span data-ttu-id="d363f-124">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="d363f-124">Click **OK**.</span></span>

## <a name="adjust-batch-job-status"></a><span data-ttu-id="d363f-125">Kötegelt feladat állapotának beállítása</span><span class="sxs-lookup"><span data-stu-id="d363f-125">Adjust batch job status</span></span>
1. <span data-ttu-id="d363f-126">Ugorjon a **Rendszerfelügyelet > Lekérdezések > Kötegelt feladatok** pontra.</span><span class="sxs-lookup"><span data-stu-id="d363f-126">Go to **System administration > Inquiries > Batch jobs**.</span></span>
2. <span data-ttu-id="d363f-127">Jelölje ki a megfelelő kötegelt feladatokat.</span><span class="sxs-lookup"><span data-stu-id="d363f-127">Select the appropriate batch job.</span></span>
3. <span data-ttu-id="d363f-128">Kattintson a Művelet panelen a **Kötegelt feladat > Funkciók > Állapot módosítása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d363f-128">On the Action Pane, click **Batch job > Functions > Change status**.</span></span>
4. <span data-ttu-id="d363f-129">Válassza ki a megfelelő állapotot.</span><span class="sxs-lookup"><span data-stu-id="d363f-129">Select the appropriate status:</span></span>
    - <span data-ttu-id="d363f-130">**Visszatartás**: A kötegelt feladat **visszatartási** értékre állítása, így a kötegelt munkaütemezőből visszatartható.</span><span class="sxs-lookup"><span data-stu-id="d363f-130">**Withhold**: Set the batch job as **withhold** so it is withheld from the batch job scheduler.</span></span> <span data-ttu-id="d363f-131">A *leállítással* egyenértékű.</span><span class="sxs-lookup"><span data-stu-id="d363f-131">Equivalent to *stop*.</span></span>
    - <span data-ttu-id="d363f-132">**Várakozás**: A kötegelt feladat **várakozásra** történő beállítása, így a kötegelt munkaütemező által elindítható.</span><span class="sxs-lookup"><span data-stu-id="d363f-132">**Waiting**: Set the batch job as **waiting** so it is waiting to be picked up by the batch job scheduler.</span></span> <span data-ttu-id="d363f-133">A *mehettel* egyenértékű.</span><span class="sxs-lookup"><span data-stu-id="d363f-133">Equivalent to *go*.</span></span>
5. <span data-ttu-id="d363f-134">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="d363f-134">Click **OK**.</span></span>
