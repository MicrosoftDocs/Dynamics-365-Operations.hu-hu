---
title: MyLeaveRequests áttekintése
description: A Microsoft Dynamics 365 Human Resources MyLeaveRequests entitása biztosítja a Szabadságkérelmek listáját a rendszerben, amely az entitást lekérdező felhasználó számára elérhető kérelmek körére korlátozódik.
author: andreabichsel
manager: tfehr
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0ca5bc225400338e76faee41a279e91fc00ce570
ms.sourcegitcommit: 18e626c49ccfdb12c1484b985e3a275e51f61320
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/04/2021
ms.locfileid: "5115536"
---
# <a name="myleaverequests-overview"></a><span data-ttu-id="fd519-103">MyLeaveRequests áttekintése</span><span class="sxs-lookup"><span data-stu-id="fd519-103">MyLeaveRequests overview</span></span>

<span data-ttu-id="fd519-104">A Microsoft Dynamics 365 Human Resources MyLeaveRequests entitása biztosítja a Szabadságkérelmek listáját a rendszerben, amely az entitást lekérdező felhasználó számára elérhető kérelmek körére korlátozódik.</span><span class="sxs-lookup"><span data-stu-id="fd519-104">The MyLeaveRequests entity in Microsoft Dynamics 365 Human Resources provides the list of Leave Requests in the system, scoped (limited) to the requests accessible to the current user querying the entity.</span></span>

## <a name="key"></a><span data-ttu-id="fd519-105">Kulcs</span><span class="sxs-lookup"><span data-stu-id="fd519-105">Key</span></span>

  | <span data-ttu-id="fd519-106">Tulajdonság neve</span><span class="sxs-lookup"><span data-stu-id="fd519-106">Property Name</span></span> | <span data-ttu-id="fd519-107">Adattípus</span><span class="sxs-lookup"><span data-stu-id="fd519-107">Data Type</span></span> |
  |---------------|-----------|
  | <span data-ttu-id="fd519-108">dataAreaId</span><span class="sxs-lookup"><span data-stu-id="fd519-108">dataAreaId</span></span>    | <span data-ttu-id="fd519-109">Karakterlánc</span><span class="sxs-lookup"><span data-stu-id="fd519-109">String</span></span>    |
  | <span data-ttu-id="fd519-110">RequestId</span><span class="sxs-lookup"><span data-stu-id="fd519-110">RequestId</span></span>     | <span data-ttu-id="fd519-111">Karakterlánc</span><span class="sxs-lookup"><span data-stu-id="fd519-111">String</span></span>    |
  | <span data-ttu-id="fd519-112">LeaveType</span><span class="sxs-lookup"><span data-stu-id="fd519-112">LeaveType</span></span>     | <span data-ttu-id="fd519-113">Karakterlánc</span><span class="sxs-lookup"><span data-stu-id="fd519-113">String</span></span>    |
  | <span data-ttu-id="fd519-114">LeaveDate</span><span class="sxs-lookup"><span data-stu-id="fd519-114">LeaveDate</span></span>     | <span data-ttu-id="fd519-115">Dátum</span><span class="sxs-lookup"><span data-stu-id="fd519-115">Date</span></span>      |
  
## <a name="properties"></a><span data-ttu-id="fd519-116">Tulajdonságok</span><span class="sxs-lookup"><span data-stu-id="fd519-116">Properties</span></span>

  | <span data-ttu-id="fd519-117">Tulajdonság neve</span><span class="sxs-lookup"><span data-stu-id="fd519-117">Property Name</span></span>     | <span data-ttu-id="fd519-118">Adattípus</span><span class="sxs-lookup"><span data-stu-id="fd519-118">Data Type</span></span> | <span data-ttu-id="fd519-119">Kötelező</span><span class="sxs-lookup"><span data-stu-id="fd519-119">Required</span></span> |
  |-------------------|-----------|----------|
  | <span data-ttu-id="fd519-120">dataAreaId</span><span class="sxs-lookup"><span data-stu-id="fd519-120">dataAreaId</span></span>        | <span data-ttu-id="fd519-121">Karakterlánc</span><span class="sxs-lookup"><span data-stu-id="fd519-121">String</span></span>    | <span data-ttu-id="fd519-122">X</span><span class="sxs-lookup"><span data-stu-id="fd519-122">X</span></span>        |
  | <span data-ttu-id="fd519-123">RequestId</span><span class="sxs-lookup"><span data-stu-id="fd519-123">RequestId</span></span>         | <span data-ttu-id="fd519-124">Karakterlánc</span><span class="sxs-lookup"><span data-stu-id="fd519-124">String</span></span>    | <span data-ttu-id="fd519-125">X</span><span class="sxs-lookup"><span data-stu-id="fd519-125">X</span></span>        |
  | <span data-ttu-id="fd519-126">LeaveType</span><span class="sxs-lookup"><span data-stu-id="fd519-126">LeaveType</span></span>         | <span data-ttu-id="fd519-127">Karakterlánc</span><span class="sxs-lookup"><span data-stu-id="fd519-127">String</span></span>    | <span data-ttu-id="fd519-128">X</span><span class="sxs-lookup"><span data-stu-id="fd519-128">X</span></span>        |
  | <span data-ttu-id="fd519-129">LeaveDate</span><span class="sxs-lookup"><span data-stu-id="fd519-129">LeaveDate</span></span>         | <span data-ttu-id="fd519-130">Dátum</span><span class="sxs-lookup"><span data-stu-id="fd519-130">Date</span></span>      | <span data-ttu-id="fd519-131">X</span><span class="sxs-lookup"><span data-stu-id="fd519-131">X</span></span>        |
  | <span data-ttu-id="fd519-132">ReasonCodeId</span><span class="sxs-lookup"><span data-stu-id="fd519-132">ReasonCodeId</span></span>      | <span data-ttu-id="fd519-133">Karakterlánc</span><span class="sxs-lookup"><span data-stu-id="fd519-133">String</span></span>    |          |
  | <span data-ttu-id="fd519-134">PersonnelNumber</span><span class="sxs-lookup"><span data-stu-id="fd519-134">PersonnelNumber</span></span>   | <span data-ttu-id="fd519-135">Karakterlánc</span><span class="sxs-lookup"><span data-stu-id="fd519-135">String</span></span>    | <span data-ttu-id="fd519-136">X</span><span class="sxs-lookup"><span data-stu-id="fd519-136">X</span></span>        |
  | <span data-ttu-id="fd519-137">RequestDate</span><span class="sxs-lookup"><span data-stu-id="fd519-137">RequestDate</span></span>       | <span data-ttu-id="fd519-138">Dátum</span><span class="sxs-lookup"><span data-stu-id="fd519-138">Date</span></span>      | <span data-ttu-id="fd519-139">X</span><span class="sxs-lookup"><span data-stu-id="fd519-139">X</span></span>        |
  | <span data-ttu-id="fd519-140">Megjegyzés</span><span class="sxs-lookup"><span data-stu-id="fd519-140">Comment</span></span>           | <span data-ttu-id="fd519-141">Karakterlánc</span><span class="sxs-lookup"><span data-stu-id="fd519-141">String</span></span>    |          |
  | <span data-ttu-id="fd519-142">Állapot</span><span class="sxs-lookup"><span data-stu-id="fd519-142">Status</span></span>            | <span data-ttu-id="fd519-143">Felsorolás</span><span class="sxs-lookup"><span data-stu-id="fd519-143">Enum</span></span>      | <span data-ttu-id="fd519-144">X</span><span class="sxs-lookup"><span data-stu-id="fd519-144">X</span></span>        |
  | <span data-ttu-id="fd519-145">Összeg</span><span class="sxs-lookup"><span data-stu-id="fd519-145">Amount</span></span>            | <span data-ttu-id="fd519-146">Valós</span><span class="sxs-lookup"><span data-stu-id="fd519-146">Real</span></span>      |          |
  | <span data-ttu-id="fd519-147">HalfDayDefinition</span><span class="sxs-lookup"><span data-stu-id="fd519-147">HalfDayDefinition</span></span> | <span data-ttu-id="fd519-148">Felsorolás</span><span class="sxs-lookup"><span data-stu-id="fd519-148">Enum</span></span>      |          |

## <a name="actions"></a><span data-ttu-id="fd519-149">Műveletek</span><span class="sxs-lookup"><span data-stu-id="fd519-149">Actions</span></span>

 | <span data-ttu-id="fd519-150">Művelet neve</span><span class="sxs-lookup"><span data-stu-id="fd519-150">Action Name</span></span>                               | <span data-ttu-id="fd519-151">Leírás</span><span class="sxs-lookup"><span data-stu-id="fd519-151">Description</span></span>                                     |
 |-------------------------------------------|-------------------------------------------------|
 | [<span data-ttu-id="fd519-152">küldés</span><span class="sxs-lookup"><span data-stu-id="fd519-152">submit</span></span>](hr-developer-api-myleaverequests-submit.md)   | <span data-ttu-id="fd519-153">A munkafolyamat által feldolgozandó kérelem elküldése.</span><span class="sxs-lookup"><span data-stu-id="fd519-153">Submit the request to be processed by workflow.</span></span> |

## <a name="see-also"></a><span data-ttu-id="fd519-154">Lásd még</span><span class="sxs-lookup"><span data-stu-id="fd519-154">See also</span></span>

- [<span data-ttu-id="fd519-155">Szabadságkérelem elküldése munkafolyamathoz</span><span class="sxs-lookup"><span data-stu-id="fd519-155">Submit a leave request to workflow</span></span>](hr-developer-api-myleaverequests-submit.md)
- [<span data-ttu-id="fd519-156">Hitelesítés</span><span class="sxs-lookup"><span data-stu-id="fd519-156">Authentication</span></span>](hr-developer-api-authentication.md)