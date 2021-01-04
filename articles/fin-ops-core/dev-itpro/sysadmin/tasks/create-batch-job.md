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
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e4360cd7068658a170f5b44c2ce7c71c39c44fa8
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4679888"
---
# <a name="create-a-batch-job"></a><span data-ttu-id="76973-103">Kötegelt feladat létrehozása</span><span class="sxs-lookup"><span data-stu-id="76973-103">Create a batch job</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="76973-104">A kötegelt feladat egy Alkalmazásobjektum-kiszolgáló (AOS) példányához elküldött feladatcsoport az automatikus feldolgozáshoz.</span><span class="sxs-lookup"><span data-stu-id="76973-104">A batch job is a group of tasks that are submitted to an Application Object Server (AOS) instance for automatic processing.</span></span> <span data-ttu-id="76973-105">A Kötegelt feladatok futtatása a feladatot létrehozó felhasználó biztonsági hitelesítő adatainak használatával történik.</span><span class="sxs-lookup"><span data-stu-id="76973-105">Batch jobs are run by using the security credentials of the user who created the job.</span></span> <span data-ttu-id="76973-106">A következő eljárásokkal lehet meghatározni a kötegelt feladatot.</span><span class="sxs-lookup"><span data-stu-id="76973-106">Use the following procedure to create a batch job.</span></span> <span data-ttu-id="76973-107">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="76973-107">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-the-batch-job"></a><span data-ttu-id="76973-108">Kötegelt feladat létrehozása</span><span class="sxs-lookup"><span data-stu-id="76973-108">Create the batch job</span></span>
1. <span data-ttu-id="76973-109">Ugorjon a **Navigációs lap > Modulok > Rendszerfelügyelet > Lekérdezések > Kötegelt feladatok** pontra.</span><span class="sxs-lookup"><span data-stu-id="76973-109">Go to **Navigation pane > Modules > System administration > Inquiries > Batch jobs**.</span></span>
2. <span data-ttu-id="76973-110">Kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="76973-110">Click **New**.</span></span>
3. <span data-ttu-id="76973-111">A **Munkaköri leírás** mezőbe írjon be egy értéket.</span><span class="sxs-lookup"><span data-stu-id="76973-111">In the **Job description** field, type a value.</span></span>
4. <span data-ttu-id="76973-112">Az **Ütemezett kezdő dátum/idő** mezőben adjon meg egy dátumot és időt.</span><span class="sxs-lookup"><span data-stu-id="76973-112">In the **Scheduled start date/time** field, enter a date and time.</span></span>
5. <span data-ttu-id="76973-113">Kattintson a **Mentés** gombra.</span><span class="sxs-lookup"><span data-stu-id="76973-113">Click **Save**.</span></span>

## <a name="create-a-recurrence"></a><span data-ttu-id="76973-114">Ismétlődés létrehozása</span><span class="sxs-lookup"><span data-stu-id="76973-114">Create a recurrence</span></span>
1. <span data-ttu-id="76973-115">Kattintson a Művelet panelen a **Kötegelt feladat** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="76973-115">On the Action Pane, click **Batch job**.</span></span>
2. <span data-ttu-id="76973-116">Kattintson az **Ismétlődésre**.</span><span class="sxs-lookup"><span data-stu-id="76973-116">Click **Recurrence**.</span></span> <span data-ttu-id="76973-117">E beállítások segítségével megadhatja az ismétlődés tartományát és a mintáját.</span><span class="sxs-lookup"><span data-stu-id="76973-117">Use these options to enter a range and pattern for the recurrence.</span></span>  
3. <span data-ttu-id="76973-118">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="76973-118">Click **OK**.</span></span>

## <a name="add-alerts"></a><span data-ttu-id="76973-119">Figyelmeztetések hozzáadása</span><span class="sxs-lookup"><span data-stu-id="76973-119">Add alerts</span></span>
1. <span data-ttu-id="76973-120">Kattintson a Művelet panelen a **Kötegelt feladat** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="76973-120">On the Action Pane, click **Batch job**.</span></span>
2. <span data-ttu-id="76973-121">Kattintson a **Figyelmeztetések** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="76973-121">Click **Alerts**.</span></span> <span data-ttu-id="76973-122">Jelezze, ha szeretne figyelmeztető üzenetet kapni a kötegelt feladat befejeződése, meghibásodása vagy törlődése esetén.</span><span class="sxs-lookup"><span data-stu-id="76973-122">Indicate if you want alert messages sent when the batch job ends, has an error, or is canceled.</span></span> <span data-ttu-id="76973-123">Adja meg, ha azt szeretné, hogy a figyelmeztetések előugró üzenetekként jelenjenek meg.</span><span class="sxs-lookup"><span data-stu-id="76973-123">Then specify if you want the alerts to be displayed as pop-up messages.</span></span>   
3. <span data-ttu-id="76973-124">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="76973-124">Click **OK**.</span></span>

## <a name="adjust-batch-job-status"></a><span data-ttu-id="76973-125">Kötegelt feladat állapotának beállítása</span><span class="sxs-lookup"><span data-stu-id="76973-125">Adjust batch job status</span></span>
1. <span data-ttu-id="76973-126">Ugorjon a **Rendszerfelügyelet > Lekérdezések > Kötegelt feladatok** pontra.</span><span class="sxs-lookup"><span data-stu-id="76973-126">Go to **System administration > Inquiries > Batch jobs**.</span></span>
2. <span data-ttu-id="76973-127">Jelölje ki a megfelelő kötegelt feladatokat.</span><span class="sxs-lookup"><span data-stu-id="76973-127">Select the appropriate batch job.</span></span>
3. <span data-ttu-id="76973-128">Kattintson a Művelet panelen a **Kötegelt feladat > Funkciók > Állapot módosítása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="76973-128">On the Action Pane, click **Batch job > Functions > Change status**.</span></span>
4. <span data-ttu-id="76973-129">Válassza ki a megfelelő állapotot.</span><span class="sxs-lookup"><span data-stu-id="76973-129">Select the appropriate status:</span></span>
    - <span data-ttu-id="76973-130">**Visszatartás**: A kötegelt feladat **visszatartási** értékre állítása, így a kötegelt munkaütemezőből visszatartható.</span><span class="sxs-lookup"><span data-stu-id="76973-130">**Withhold**: Set the batch job as **withhold** so it is withheld from the batch job scheduler.</span></span> <span data-ttu-id="76973-131">A *leállítással* egyenértékű.</span><span class="sxs-lookup"><span data-stu-id="76973-131">Equivalent to *stop*.</span></span>
    - <span data-ttu-id="76973-132">**Várakozás**: A kötegelt feladat **várakozásra** történő beállítása, így a kötegelt munkaütemező által elindítható.</span><span class="sxs-lookup"><span data-stu-id="76973-132">**Waiting**: Set the batch job as **waiting** so it is waiting to be picked up by the batch job scheduler.</span></span> <span data-ttu-id="76973-133">A *mehettel* egyenértékű.</span><span class="sxs-lookup"><span data-stu-id="76973-133">Equivalent to *go*.</span></span>
5. <span data-ttu-id="76973-134">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="76973-134">Click **OK**.</span></span>
