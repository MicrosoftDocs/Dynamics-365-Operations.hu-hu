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
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 31c8e2ba87ef8c17a3147e1159104585258d4164
ms.contentlocale: hu-hu
ms.lasthandoff: 08/29/2017

---
# <a name="create-a-batch-job"></a><span data-ttu-id="324a5-103">Kötegelt feladat létrehozása</span><span class="sxs-lookup"><span data-stu-id="324a5-103">Create a batch job</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="324a5-104">A kötegelt feladat egy Alkalmazásobjektum-kiszolgáló (AOS) példányához elküldött feladatcsoport az automatikus feldolgozáshoz.</span><span class="sxs-lookup"><span data-stu-id="324a5-104">A batch job is a group of tasks that are submitted to an Application Object Server (AOS) instance for automatic processing.</span></span> <span data-ttu-id="324a5-105">A Kötegelt feladatok futtatása a feladatot létrehozó felhasználó biztonsági hitelesítő adatainak használatával történik.</span><span class="sxs-lookup"><span data-stu-id="324a5-105">Batch jobs are run by using the security credentials of the user who created the job.</span></span> <span data-ttu-id="324a5-106">A következő eljárásokkal lehet meghatározni a kötegelt feladatot.</span><span class="sxs-lookup"><span data-stu-id="324a5-106">Use the following procedure to create a batch job.</span></span> <span data-ttu-id="324a5-107">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="324a5-107">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-the-batch-job"></a><span data-ttu-id="324a5-108">Kötegelt feladat létrehozása</span><span class="sxs-lookup"><span data-stu-id="324a5-108">Create the batch job</span></span>
1. <span data-ttu-id="324a5-109">Ugorjon a Rendszerfelügyelet > Lekérdezések > Kötegelt feladatok pontra.</span><span class="sxs-lookup"><span data-stu-id="324a5-109">Go to System administration > Inquiries > Batch jobs.</span></span>
2. <span data-ttu-id="324a5-110">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="324a5-110">Click New.</span></span>
3. <span data-ttu-id="324a5-111">A Munkaköri leírás mezőbe írjon be egy értéket.</span><span class="sxs-lookup"><span data-stu-id="324a5-111">In the Job description field, type a value.</span></span>
4. <span data-ttu-id="324a5-112">Az Ütemezett kezdő dátum/idő mezőben adjon meg egy dátumot és időt.</span><span class="sxs-lookup"><span data-stu-id="324a5-112">In the Scheduled start date/time field, enter a date and time.</span></span>
5. <span data-ttu-id="324a5-113">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="324a5-113">Click Save.</span></span>

## <a name="create-a-recurrence"></a><span data-ttu-id="324a5-114">Ismétlődés létrehozása</span><span class="sxs-lookup"><span data-stu-id="324a5-114">Create a recurrence</span></span>
1. <span data-ttu-id="324a5-115">Kattintson a Művelet Panelen a Kötegelt feladat lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="324a5-115">On the Action Pane, click Batch job.</span></span>
2. <span data-ttu-id="324a5-116">Kattintson az Ismétlődésre.</span><span class="sxs-lookup"><span data-stu-id="324a5-116">Click Recurrence.</span></span>
    * <span data-ttu-id="324a5-117">E beállítások segítségével megadhatja az ismétlődés tartományát és a mintáját.</span><span class="sxs-lookup"><span data-stu-id="324a5-117">Use these options to enter a range and pattern for the recurrence.</span></span>  
3. <span data-ttu-id="324a5-118">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="324a5-118">Click OK.</span></span>

## <a name="add-alerts"></a><span data-ttu-id="324a5-119">Figyelmeztetések hozzáadása</span><span class="sxs-lookup"><span data-stu-id="324a5-119">Add alerts</span></span>
1. <span data-ttu-id="324a5-120">Kattintson a Művelet Panelen a Kötegelt feladat lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="324a5-120">On the Action Pane, click Batch job.</span></span>
2. <span data-ttu-id="324a5-121">Kattintson a figyelmeztetések lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="324a5-121">Click Alerts.</span></span>
    * <span data-ttu-id="324a5-122">Jelezze, ha szeretne figyelmeztető üzenetet kapni a kötegelt feladat befejeződése, meghibásodása vagy törlődése esetén.</span><span class="sxs-lookup"><span data-stu-id="324a5-122">Indicate if you want alert messages sent when the batch job ends, has an error, or is canceled.</span></span> <span data-ttu-id="324a5-123">Adja meg, ha azt szeretné, hogy a figyelmeztetések előugró üzenetekként jelenjenek meg.</span><span class="sxs-lookup"><span data-stu-id="324a5-123">Then specify if you want the alerts to be displayed as pop-up messages.</span></span>   
3. <span data-ttu-id="324a5-124">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="324a5-124">Click OK.</span></span>


