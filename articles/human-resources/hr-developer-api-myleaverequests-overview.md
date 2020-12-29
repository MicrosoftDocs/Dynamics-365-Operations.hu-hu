---
title: MyLeaveRequests áttekintése
description: A Microsoft Dynamics 365 Human Resources MyLeaveRequests entitása biztosítja a Szabadságkérelmek listáját a rendszerben, amely az entitást lekérdező felhasználó számára elérhető kérelmek körére korlátozódik.
author: andreabichsel
manager: AnnBe
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
ms.openlocfilehash: 4bf3b298af9eb39e03514a4005afb43a42908e47
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4418781"
---
# <a name="myleaverequests-overview"></a><span data-ttu-id="c3291-103">MyLeaveRequests áttekintése</span><span class="sxs-lookup"><span data-stu-id="c3291-103">MyLeaveRequests overview</span></span>

<span data-ttu-id="c3291-104">A Microsoft Dynamics 365 Human Resources MyLeaveRequests entitása biztosítja a Szabadságkérelmek listáját a rendszerben, amely az entitást lekérdező felhasználó számára elérhető kérelmek körére korlátozódik.</span><span class="sxs-lookup"><span data-stu-id="c3291-104">The MyLeaveRequests entity in Microsoft Dynamics 365 Human Resources provides the list of Leave Requests in the system, scoped (limited) to the requests accessible to the current user querying the entity.</span></span>

## <a name="key"></a><span data-ttu-id="c3291-105">Kulcs</span><span class="sxs-lookup"><span data-stu-id="c3291-105">Key</span></span>

  | <span data-ttu-id="c3291-106">Tulajdonság neve</span><span class="sxs-lookup"><span data-stu-id="c3291-106">Property Name</span></span> | <span data-ttu-id="c3291-107">Adattípus</span><span class="sxs-lookup"><span data-stu-id="c3291-107">Data Type</span></span> |
  |---------------|-----------|
  | <span data-ttu-id="c3291-108">dataAreaId</span><span class="sxs-lookup"><span data-stu-id="c3291-108">dataAreaId</span></span>    | <span data-ttu-id="c3291-109">Karakterlánc</span><span class="sxs-lookup"><span data-stu-id="c3291-109">String</span></span>    |
  | <span data-ttu-id="c3291-110">RequestId</span><span class="sxs-lookup"><span data-stu-id="c3291-110">RequestId</span></span>     | <span data-ttu-id="c3291-111">Karakterlánc</span><span class="sxs-lookup"><span data-stu-id="c3291-111">String</span></span>    |
  | <span data-ttu-id="c3291-112">LeaveType</span><span class="sxs-lookup"><span data-stu-id="c3291-112">LeaveType</span></span>     | <span data-ttu-id="c3291-113">Karakterlánc</span><span class="sxs-lookup"><span data-stu-id="c3291-113">String</span></span>    |
  | <span data-ttu-id="c3291-114">LeaveDate</span><span class="sxs-lookup"><span data-stu-id="c3291-114">LeaveDate</span></span>     | <span data-ttu-id="c3291-115">Dátum</span><span class="sxs-lookup"><span data-stu-id="c3291-115">Date</span></span>      |
  
## <a name="properties"></a><span data-ttu-id="c3291-116">Tulajdonságok</span><span class="sxs-lookup"><span data-stu-id="c3291-116">Properties</span></span>

  | <span data-ttu-id="c3291-117">Tulajdonság neve</span><span class="sxs-lookup"><span data-stu-id="c3291-117">Property Name</span></span>     | <span data-ttu-id="c3291-118">Adattípus</span><span class="sxs-lookup"><span data-stu-id="c3291-118">Data Type</span></span> | <span data-ttu-id="c3291-119">Kötelező</span><span class="sxs-lookup"><span data-stu-id="c3291-119">Required</span></span> |
  |-------------------|-----------|----------|
  | <span data-ttu-id="c3291-120">dataAreaId</span><span class="sxs-lookup"><span data-stu-id="c3291-120">dataAreaId</span></span>        | <span data-ttu-id="c3291-121">Karakterlánc</span><span class="sxs-lookup"><span data-stu-id="c3291-121">String</span></span>    | <span data-ttu-id="c3291-122">X</span><span class="sxs-lookup"><span data-stu-id="c3291-122">X</span></span>        |
  | <span data-ttu-id="c3291-123">RequestId</span><span class="sxs-lookup"><span data-stu-id="c3291-123">RequestId</span></span>         | <span data-ttu-id="c3291-124">Karakterlánc</span><span class="sxs-lookup"><span data-stu-id="c3291-124">String</span></span>    | <span data-ttu-id="c3291-125">X</span><span class="sxs-lookup"><span data-stu-id="c3291-125">X</span></span>        |
  | <span data-ttu-id="c3291-126">LeaveType</span><span class="sxs-lookup"><span data-stu-id="c3291-126">LeaveType</span></span>         | <span data-ttu-id="c3291-127">Karakterlánc</span><span class="sxs-lookup"><span data-stu-id="c3291-127">String</span></span>    | <span data-ttu-id="c3291-128">X</span><span class="sxs-lookup"><span data-stu-id="c3291-128">X</span></span>        |
  | <span data-ttu-id="c3291-129">LeaveDate</span><span class="sxs-lookup"><span data-stu-id="c3291-129">LeaveDate</span></span>         | <span data-ttu-id="c3291-130">Dátum</span><span class="sxs-lookup"><span data-stu-id="c3291-130">Date</span></span>      | <span data-ttu-id="c3291-131">X</span><span class="sxs-lookup"><span data-stu-id="c3291-131">X</span></span>        |
  | <span data-ttu-id="c3291-132">ReasonCodeId</span><span class="sxs-lookup"><span data-stu-id="c3291-132">ReasonCodeId</span></span>      | <span data-ttu-id="c3291-133">Karakterlánc</span><span class="sxs-lookup"><span data-stu-id="c3291-133">String</span></span>    |          |
  | <span data-ttu-id="c3291-134">PersonnelNumber</span><span class="sxs-lookup"><span data-stu-id="c3291-134">PersonnelNumber</span></span>   | <span data-ttu-id="c3291-135">Karakterlánc</span><span class="sxs-lookup"><span data-stu-id="c3291-135">String</span></span>    | <span data-ttu-id="c3291-136">X</span><span class="sxs-lookup"><span data-stu-id="c3291-136">X</span></span>        |
  | <span data-ttu-id="c3291-137">RequestDate</span><span class="sxs-lookup"><span data-stu-id="c3291-137">RequestDate</span></span>       | <span data-ttu-id="c3291-138">Dátum</span><span class="sxs-lookup"><span data-stu-id="c3291-138">Date</span></span>      | <span data-ttu-id="c3291-139">X</span><span class="sxs-lookup"><span data-stu-id="c3291-139">X</span></span>        |
  | <span data-ttu-id="c3291-140">Megjegyzés</span><span class="sxs-lookup"><span data-stu-id="c3291-140">Comment</span></span>           | <span data-ttu-id="c3291-141">Karakterlánc</span><span class="sxs-lookup"><span data-stu-id="c3291-141">String</span></span>    |          |
  | <span data-ttu-id="c3291-142">Állapot</span><span class="sxs-lookup"><span data-stu-id="c3291-142">Status</span></span>            | <span data-ttu-id="c3291-143">Felsorolás</span><span class="sxs-lookup"><span data-stu-id="c3291-143">Enum</span></span>      | <span data-ttu-id="c3291-144">X</span><span class="sxs-lookup"><span data-stu-id="c3291-144">X</span></span>        |
  | <span data-ttu-id="c3291-145">Összeg</span><span class="sxs-lookup"><span data-stu-id="c3291-145">Amount</span></span>            | <span data-ttu-id="c3291-146">Valós</span><span class="sxs-lookup"><span data-stu-id="c3291-146">Real</span></span>      |          |
  | <span data-ttu-id="c3291-147">HalfDayDefinition</span><span class="sxs-lookup"><span data-stu-id="c3291-147">HalfDayDefinition</span></span> | <span data-ttu-id="c3291-148">Felsorolás</span><span class="sxs-lookup"><span data-stu-id="c3291-148">Enum</span></span>      |          |

## <a name="actions"></a><span data-ttu-id="c3291-149">Műveletek</span><span class="sxs-lookup"><span data-stu-id="c3291-149">Actions</span></span>

 | <span data-ttu-id="c3291-150">Művelet neve</span><span class="sxs-lookup"><span data-stu-id="c3291-150">Action Name</span></span>                               | <span data-ttu-id="c3291-151">Leírás</span><span class="sxs-lookup"><span data-stu-id="c3291-151">Description</span></span>                                     |
 |-------------------------------------------|-------------------------------------------------|
 | [<span data-ttu-id="c3291-152">küldés</span><span class="sxs-lookup"><span data-stu-id="c3291-152">submit</span></span>](hr-developer-api-myleaverequests-submit.md)   | <span data-ttu-id="c3291-153">A munkafolyamat által feldolgozandó kérelem elküldése.</span><span class="sxs-lookup"><span data-stu-id="c3291-153">Submit the request to be processed by workflow.</span></span> |

## <a name="see-also"></a><span data-ttu-id="c3291-154">Lásd még</span><span class="sxs-lookup"><span data-stu-id="c3291-154">See also</span></span>

- [<span data-ttu-id="c3291-155">Szabadságkérelem elküldése munkafolyamathoz</span><span class="sxs-lookup"><span data-stu-id="c3291-155">Submit a leave request to workflow</span></span>](hr-developer-api-myleaverequests-submit.md)
- [<span data-ttu-id="c3291-156">Hitelesítés</span><span class="sxs-lookup"><span data-stu-id="c3291-156">Authentication</span></span>](hr-developer-api-authentication.md)