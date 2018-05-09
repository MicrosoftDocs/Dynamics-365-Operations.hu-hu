--- 
title: "Kötegelt feladat létrehozása"
description: "A kötegelt feladat egy Alkalmazásobjektum-kiszolgáló (AOS) példányához elküldött feladatcsoport az automatikus feldolgozáshoz."
author: maertenm
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 55b153e6044f61f16e19ae0b264e3f23538e004a
ms.contentlocale: hu-hu
ms.lasthandoff: 05/08/2018

---
# <a name="create-a-batch-job"></a><span data-ttu-id="21606-103">Kötegelt feladat létrehozása</span><span class="sxs-lookup"><span data-stu-id="21606-103">Create a batch job</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="21606-104">A kötegelt feladat egy Alkalmazásobjektum-kiszolgáló (AOS) példányához elküldött feladatcsoport az automatikus feldolgozáshoz.</span><span class="sxs-lookup"><span data-stu-id="21606-104">A batch job is a group of tasks that are submitted to an Application Object Server (AOS) instance for automatic processing.</span></span> <span data-ttu-id="21606-105">A Kötegelt feladatok futtatása a feladatot létrehozó felhasználó biztonsági hitelesítő adatainak használatával történik.</span><span class="sxs-lookup"><span data-stu-id="21606-105">Batch jobs are run by using the security credentials of the user who created the job.</span></span> <span data-ttu-id="21606-106">A következő eljárásokkal lehet meghatározni a kötegelt feladatot.</span><span class="sxs-lookup"><span data-stu-id="21606-106">Use the following procedure to create a batch job.</span></span> <span data-ttu-id="21606-107">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="21606-107">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-the-batch-job"></a><span data-ttu-id="21606-108">Kötegelt feladat létrehozása</span><span class="sxs-lookup"><span data-stu-id="21606-108">Create the batch job</span></span>
1. <span data-ttu-id="21606-109">Ugorjon a Rendszerfelügyelet > Lekérdezések > Kötegelt feladatok pontra.</span><span class="sxs-lookup"><span data-stu-id="21606-109">Go to System administration > Inquiries > Batch jobs.</span></span>
2. <span data-ttu-id="21606-110">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="21606-110">Click New.</span></span>
3. <span data-ttu-id="21606-111">A Munkaköri leírás mezőbe írjon be egy értéket.</span><span class="sxs-lookup"><span data-stu-id="21606-111">In the Job description field, type a value.</span></span>
4. <span data-ttu-id="21606-112">Az Ütemezett kezdő dátum/idő mezőben adjon meg egy dátumot és időt.</span><span class="sxs-lookup"><span data-stu-id="21606-112">In the Scheduled start date/time field, enter a date and time.</span></span>
5. <span data-ttu-id="21606-113">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="21606-113">Click Save.</span></span>

## <a name="create-a-recurrence"></a><span data-ttu-id="21606-114">Ismétlődés létrehozása</span><span class="sxs-lookup"><span data-stu-id="21606-114">Create a recurrence</span></span>
1. <span data-ttu-id="21606-115">Kattintson a Művelet Panelen a Kötegelt feladat lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="21606-115">On the Action Pane, click Batch job.</span></span>
2. <span data-ttu-id="21606-116">Kattintson az Ismétlődésre.</span><span class="sxs-lookup"><span data-stu-id="21606-116">Click Recurrence.</span></span>
    * <span data-ttu-id="21606-117">E beállítások segítségével megadhatja az ismétlődés tartományát és a mintáját.</span><span class="sxs-lookup"><span data-stu-id="21606-117">Use these options to enter a range and pattern for the recurrence.</span></span>  
3. <span data-ttu-id="21606-118">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="21606-118">Click OK.</span></span>

## <a name="add-alerts"></a><span data-ttu-id="21606-119">Figyelmeztetések hozzáadása</span><span class="sxs-lookup"><span data-stu-id="21606-119">Add alerts</span></span>
1. <span data-ttu-id="21606-120">Kattintson a Művelet Panelen a Kötegelt feladat lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="21606-120">On the Action Pane, click Batch job.</span></span>
2. <span data-ttu-id="21606-121">Kattintson a figyelmeztetések lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="21606-121">Click Alerts.</span></span>
    * <span data-ttu-id="21606-122">Jelezze, ha szeretne figyelmeztető üzenetet kapni a kötegelt feladat befejeződése, meghibásodása vagy törlődése esetén.</span><span class="sxs-lookup"><span data-stu-id="21606-122">Indicate if you want alert messages sent when the batch job ends, has an error, or is canceled.</span></span> <span data-ttu-id="21606-123">Adja meg, ha azt szeretné, hogy a figyelmeztetések előugró üzenetekként jelenjenek meg.</span><span class="sxs-lookup"><span data-stu-id="21606-123">Then specify if you want the alerts to be displayed as pop-up messages.</span></span>   
3. <span data-ttu-id="21606-124">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="21606-124">Click OK.</span></span>


