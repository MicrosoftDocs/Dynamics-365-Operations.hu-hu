---
title: MyLeaveRequests áttekintése
description: ''
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
ms.openlocfilehash: 66f161d6736b1bb544d02871d9d51b2949b1cfa0
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/03/2020
ms.locfileid: "3009275"
---
# <a name="myleaverequests-overview"></a><span data-ttu-id="e115a-102">MyLeaveRequests áttekintése</span><span class="sxs-lookup"><span data-stu-id="e115a-102">MyLeaveRequests overview</span></span>

<span data-ttu-id="e115a-103">A Microsoft Dynamics 365 Human Resources MyLeaveRequests entitása biztosítja a Szabadságkérelmek listáját a rendszerben, amely az entitást lekérdező felhasználó számára elérhető kérelmek körére korlátozódik.</span><span class="sxs-lookup"><span data-stu-id="e115a-103">The MyLeaveRequests entity in Microsoft Dynamics 365 Human Resources provides the list of Leave Requests in the system, scoped (limited) to the requests accessible to the current user querying the entity.</span></span>

## <a name="key"></a><span data-ttu-id="e115a-104">Kulcs</span><span class="sxs-lookup"><span data-stu-id="e115a-104">Key</span></span>

  | <span data-ttu-id="e115a-105">Tulajdonság neve</span><span class="sxs-lookup"><span data-stu-id="e115a-105">Property Name</span></span> | <span data-ttu-id="e115a-106">Adattípus</span><span class="sxs-lookup"><span data-stu-id="e115a-106">Data Type</span></span> |
  |---------------|-----------|
  | <span data-ttu-id="e115a-107">dataAreaId</span><span class="sxs-lookup"><span data-stu-id="e115a-107">dataAreaId</span></span>    | <span data-ttu-id="e115a-108">Karakterlánc</span><span class="sxs-lookup"><span data-stu-id="e115a-108">String</span></span>    |
  | <span data-ttu-id="e115a-109">RequestId</span><span class="sxs-lookup"><span data-stu-id="e115a-109">RequestId</span></span>     | <span data-ttu-id="e115a-110">Karakterlánc</span><span class="sxs-lookup"><span data-stu-id="e115a-110">String</span></span>    |
  | <span data-ttu-id="e115a-111">LeaveType</span><span class="sxs-lookup"><span data-stu-id="e115a-111">LeaveType</span></span>     | <span data-ttu-id="e115a-112">Karakterlánc</span><span class="sxs-lookup"><span data-stu-id="e115a-112">String</span></span>    |
  | <span data-ttu-id="e115a-113">LeaveDate</span><span class="sxs-lookup"><span data-stu-id="e115a-113">LeaveDate</span></span>     | <span data-ttu-id="e115a-114">Dátum</span><span class="sxs-lookup"><span data-stu-id="e115a-114">Date</span></span>      |
  
## <a name="properties"></a><span data-ttu-id="e115a-115">Tulajdonságok</span><span class="sxs-lookup"><span data-stu-id="e115a-115">Properties</span></span>

  | <span data-ttu-id="e115a-116">Tulajdonság neve</span><span class="sxs-lookup"><span data-stu-id="e115a-116">Property Name</span></span>     | <span data-ttu-id="e115a-117">Adattípus</span><span class="sxs-lookup"><span data-stu-id="e115a-117">Data Type</span></span> | <span data-ttu-id="e115a-118">Kötelező</span><span class="sxs-lookup"><span data-stu-id="e115a-118">Required</span></span> |
  |-------------------|-----------|----------|
  | <span data-ttu-id="e115a-119">dataAreaId</span><span class="sxs-lookup"><span data-stu-id="e115a-119">dataAreaId</span></span>        | <span data-ttu-id="e115a-120">Karakterlánc</span><span class="sxs-lookup"><span data-stu-id="e115a-120">String</span></span>    | <span data-ttu-id="e115a-121">X</span><span class="sxs-lookup"><span data-stu-id="e115a-121">X</span></span>        |
  | <span data-ttu-id="e115a-122">RequestId</span><span class="sxs-lookup"><span data-stu-id="e115a-122">RequestId</span></span>         | <span data-ttu-id="e115a-123">Karakterlánc</span><span class="sxs-lookup"><span data-stu-id="e115a-123">String</span></span>    | <span data-ttu-id="e115a-124">X</span><span class="sxs-lookup"><span data-stu-id="e115a-124">X</span></span>        |
  | <span data-ttu-id="e115a-125">LeaveType</span><span class="sxs-lookup"><span data-stu-id="e115a-125">LeaveType</span></span>         | <span data-ttu-id="e115a-126">Karakterlánc</span><span class="sxs-lookup"><span data-stu-id="e115a-126">String</span></span>    | <span data-ttu-id="e115a-127">X</span><span class="sxs-lookup"><span data-stu-id="e115a-127">X</span></span>        |
  | <span data-ttu-id="e115a-128">LeaveDate</span><span class="sxs-lookup"><span data-stu-id="e115a-128">LeaveDate</span></span>         | <span data-ttu-id="e115a-129">Dátum</span><span class="sxs-lookup"><span data-stu-id="e115a-129">Date</span></span>      | <span data-ttu-id="e115a-130">X</span><span class="sxs-lookup"><span data-stu-id="e115a-130">X</span></span>        |
  | <span data-ttu-id="e115a-131">ReasonCodeId</span><span class="sxs-lookup"><span data-stu-id="e115a-131">ReasonCodeId</span></span>      | <span data-ttu-id="e115a-132">Karakterlánc</span><span class="sxs-lookup"><span data-stu-id="e115a-132">String</span></span>    |          |
  | <span data-ttu-id="e115a-133">PersonnelNumber</span><span class="sxs-lookup"><span data-stu-id="e115a-133">PersonnelNumber</span></span>   | <span data-ttu-id="e115a-134">Karakterlánc</span><span class="sxs-lookup"><span data-stu-id="e115a-134">String</span></span>    | <span data-ttu-id="e115a-135">X</span><span class="sxs-lookup"><span data-stu-id="e115a-135">X</span></span>        |
  | <span data-ttu-id="e115a-136">RequestDate</span><span class="sxs-lookup"><span data-stu-id="e115a-136">RequestDate</span></span>       | <span data-ttu-id="e115a-137">Dátum</span><span class="sxs-lookup"><span data-stu-id="e115a-137">Date</span></span>      | <span data-ttu-id="e115a-138">X</span><span class="sxs-lookup"><span data-stu-id="e115a-138">X</span></span>        |
  | <span data-ttu-id="e115a-139">Megjegyzés</span><span class="sxs-lookup"><span data-stu-id="e115a-139">Comment</span></span>           | <span data-ttu-id="e115a-140">Karakterlánc</span><span class="sxs-lookup"><span data-stu-id="e115a-140">String</span></span>    |          |
  | <span data-ttu-id="e115a-141">Állapot</span><span class="sxs-lookup"><span data-stu-id="e115a-141">Status</span></span>            | <span data-ttu-id="e115a-142">Felsorolás</span><span class="sxs-lookup"><span data-stu-id="e115a-142">Enum</span></span>      | <span data-ttu-id="e115a-143">X</span><span class="sxs-lookup"><span data-stu-id="e115a-143">X</span></span>        |
  | <span data-ttu-id="e115a-144">Összeg</span><span class="sxs-lookup"><span data-stu-id="e115a-144">Amount</span></span>            | <span data-ttu-id="e115a-145">Valós</span><span class="sxs-lookup"><span data-stu-id="e115a-145">Real</span></span>      |          |
  | <span data-ttu-id="e115a-146">HalfDayDefinition</span><span class="sxs-lookup"><span data-stu-id="e115a-146">HalfDayDefinition</span></span> | <span data-ttu-id="e115a-147">Felsorolás</span><span class="sxs-lookup"><span data-stu-id="e115a-147">Enum</span></span>      |          |

## <a name="actions"></a><span data-ttu-id="e115a-148">Műveletek</span><span class="sxs-lookup"><span data-stu-id="e115a-148">Actions</span></span>

 | <span data-ttu-id="e115a-149">Művelet neve</span><span class="sxs-lookup"><span data-stu-id="e115a-149">Action Name</span></span>                               | <span data-ttu-id="e115a-150">Leírás</span><span class="sxs-lookup"><span data-stu-id="e115a-150">Description</span></span>                                     |
 |-------------------------------------------|-------------------------------------------------|
 | [<span data-ttu-id="e115a-151">küldés</span><span class="sxs-lookup"><span data-stu-id="e115a-151">submit</span></span>](hr-developer-api-myleaverequests-submit.md)   | <span data-ttu-id="e115a-152">A munkafolyamat által feldolgozandó kérelem elküldése.</span><span class="sxs-lookup"><span data-stu-id="e115a-152">Submit the request to be processed by workflow.</span></span> |

## <a name="see-also"></a><span data-ttu-id="e115a-153">Lásd még</span><span class="sxs-lookup"><span data-stu-id="e115a-153">See also</span></span>

- [<span data-ttu-id="e115a-154">Szabadságkérelem elküldése munkafolyamathoz</span><span class="sxs-lookup"><span data-stu-id="e115a-154">Submit a leave request to workflow</span></span>](hr-developer-api-myleaverequests-submit.md)
- [<span data-ttu-id="e115a-155">Hitelesítés</span><span class="sxs-lookup"><span data-stu-id="e115a-155">Authentication</span></span>](hr-developer-api-authentication.md)