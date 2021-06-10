---
title: MyLeaveRequests áttekintése
description: A Microsoft Dynamics 365 Human Resources MyLeaveRequests entitása biztosítja a Szabadságkérelmek listáját a rendszerben, amely az entitást lekérdező felhasználó számára elérhető kérelmek körére korlátozódik.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: f29d5cf1469b58b4ea1837dc82b9513f5c002609
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/18/2021
ms.locfileid: "6054956"
---
# <a name="myleaverequests-overview"></a><span data-ttu-id="56671-103">MyLeaveRequests áttekintése</span><span class="sxs-lookup"><span data-stu-id="56671-103">MyLeaveRequests overview</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="56671-104">A Microsoft Dynamics 365 Human Resources MyLeaveRequests entitása biztosítja a Szabadságkérelmek listáját a rendszerben, amely az entitást lekérdező felhasználó számára elérhető kérelmek körére korlátozódik.</span><span class="sxs-lookup"><span data-stu-id="56671-104">The MyLeaveRequests entity in Microsoft Dynamics 365 Human Resources provides the list of Leave Requests in the system, scoped (limited) to the requests accessible to the current user querying the entity.</span></span>

## <a name="key"></a><span data-ttu-id="56671-105">Kulcs</span><span class="sxs-lookup"><span data-stu-id="56671-105">Key</span></span>

  | <span data-ttu-id="56671-106">Tulajdonság neve</span><span class="sxs-lookup"><span data-stu-id="56671-106">Property Name</span></span> | <span data-ttu-id="56671-107">Adattípus</span><span class="sxs-lookup"><span data-stu-id="56671-107">Data Type</span></span> |
  |---------------|-----------|
  | <span data-ttu-id="56671-108">dataAreaId</span><span class="sxs-lookup"><span data-stu-id="56671-108">dataAreaId</span></span>    | <span data-ttu-id="56671-109">Karakterlánc</span><span class="sxs-lookup"><span data-stu-id="56671-109">String</span></span>    |
  | <span data-ttu-id="56671-110">RequestId</span><span class="sxs-lookup"><span data-stu-id="56671-110">RequestId</span></span>     | <span data-ttu-id="56671-111">Karakterlánc</span><span class="sxs-lookup"><span data-stu-id="56671-111">String</span></span>    |
  | <span data-ttu-id="56671-112">LeaveType</span><span class="sxs-lookup"><span data-stu-id="56671-112">LeaveType</span></span>     | <span data-ttu-id="56671-113">Karakterlánc</span><span class="sxs-lookup"><span data-stu-id="56671-113">String</span></span>    |
  | <span data-ttu-id="56671-114">LeaveDate</span><span class="sxs-lookup"><span data-stu-id="56671-114">LeaveDate</span></span>     | <span data-ttu-id="56671-115">Dátum</span><span class="sxs-lookup"><span data-stu-id="56671-115">Date</span></span>      |
  
## <a name="properties"></a><span data-ttu-id="56671-116">Tulajdonságok</span><span class="sxs-lookup"><span data-stu-id="56671-116">Properties</span></span>

  | <span data-ttu-id="56671-117">Tulajdonság neve</span><span class="sxs-lookup"><span data-stu-id="56671-117">Property Name</span></span>     | <span data-ttu-id="56671-118">Adattípus</span><span class="sxs-lookup"><span data-stu-id="56671-118">Data Type</span></span> | <span data-ttu-id="56671-119">Kötelező</span><span class="sxs-lookup"><span data-stu-id="56671-119">Required</span></span> |
  |-------------------|-----------|----------|
  | <span data-ttu-id="56671-120">dataAreaId</span><span class="sxs-lookup"><span data-stu-id="56671-120">dataAreaId</span></span>        | <span data-ttu-id="56671-121">Karakterlánc</span><span class="sxs-lookup"><span data-stu-id="56671-121">String</span></span>    | <span data-ttu-id="56671-122">X</span><span class="sxs-lookup"><span data-stu-id="56671-122">X</span></span>        |
  | <span data-ttu-id="56671-123">RequestId</span><span class="sxs-lookup"><span data-stu-id="56671-123">RequestId</span></span>         | <span data-ttu-id="56671-124">Karakterlánc</span><span class="sxs-lookup"><span data-stu-id="56671-124">String</span></span>    | <span data-ttu-id="56671-125">X</span><span class="sxs-lookup"><span data-stu-id="56671-125">X</span></span>        |
  | <span data-ttu-id="56671-126">LeaveType</span><span class="sxs-lookup"><span data-stu-id="56671-126">LeaveType</span></span>         | <span data-ttu-id="56671-127">Karakterlánc</span><span class="sxs-lookup"><span data-stu-id="56671-127">String</span></span>    | <span data-ttu-id="56671-128">X</span><span class="sxs-lookup"><span data-stu-id="56671-128">X</span></span>        |
  | <span data-ttu-id="56671-129">LeaveDate</span><span class="sxs-lookup"><span data-stu-id="56671-129">LeaveDate</span></span>         | <span data-ttu-id="56671-130">Dátum</span><span class="sxs-lookup"><span data-stu-id="56671-130">Date</span></span>      | <span data-ttu-id="56671-131">X</span><span class="sxs-lookup"><span data-stu-id="56671-131">X</span></span>        |
  | <span data-ttu-id="56671-132">ReasonCodeId</span><span class="sxs-lookup"><span data-stu-id="56671-132">ReasonCodeId</span></span>      | <span data-ttu-id="56671-133">Karakterlánc</span><span class="sxs-lookup"><span data-stu-id="56671-133">String</span></span>    |          |
  | <span data-ttu-id="56671-134">PersonnelNumber</span><span class="sxs-lookup"><span data-stu-id="56671-134">PersonnelNumber</span></span>   | <span data-ttu-id="56671-135">Karakterlánc</span><span class="sxs-lookup"><span data-stu-id="56671-135">String</span></span>    | <span data-ttu-id="56671-136">X</span><span class="sxs-lookup"><span data-stu-id="56671-136">X</span></span>        |
  | <span data-ttu-id="56671-137">RequestDate</span><span class="sxs-lookup"><span data-stu-id="56671-137">RequestDate</span></span>       | <span data-ttu-id="56671-138">Dátum</span><span class="sxs-lookup"><span data-stu-id="56671-138">Date</span></span>      | <span data-ttu-id="56671-139">X</span><span class="sxs-lookup"><span data-stu-id="56671-139">X</span></span>        |
  | <span data-ttu-id="56671-140">Megjegyzés</span><span class="sxs-lookup"><span data-stu-id="56671-140">Comment</span></span>           | <span data-ttu-id="56671-141">Karakterlánc</span><span class="sxs-lookup"><span data-stu-id="56671-141">String</span></span>    |          |
  | <span data-ttu-id="56671-142">Állapot</span><span class="sxs-lookup"><span data-stu-id="56671-142">Status</span></span>            | <span data-ttu-id="56671-143">Felsorolás</span><span class="sxs-lookup"><span data-stu-id="56671-143">Enum</span></span>      | <span data-ttu-id="56671-144">X</span><span class="sxs-lookup"><span data-stu-id="56671-144">X</span></span>        |
  | <span data-ttu-id="56671-145">Összeg</span><span class="sxs-lookup"><span data-stu-id="56671-145">Amount</span></span>            | <span data-ttu-id="56671-146">Valós</span><span class="sxs-lookup"><span data-stu-id="56671-146">Real</span></span>      |          |
  | <span data-ttu-id="56671-147">HalfDayDefinition</span><span class="sxs-lookup"><span data-stu-id="56671-147">HalfDayDefinition</span></span> | <span data-ttu-id="56671-148">Felsorolás</span><span class="sxs-lookup"><span data-stu-id="56671-148">Enum</span></span>      |          |

## <a name="actions"></a><span data-ttu-id="56671-149">Műveletek</span><span class="sxs-lookup"><span data-stu-id="56671-149">Actions</span></span>

 | <span data-ttu-id="56671-150">Művelet neve</span><span class="sxs-lookup"><span data-stu-id="56671-150">Action Name</span></span>                               | <span data-ttu-id="56671-151">Leírás</span><span class="sxs-lookup"><span data-stu-id="56671-151">Description</span></span>                                     |
 |-------------------------------------------|-------------------------------------------------|
 | [<span data-ttu-id="56671-152">küldés</span><span class="sxs-lookup"><span data-stu-id="56671-152">submit</span></span>](hr-developer-api-myleaverequests-submit.md)   | <span data-ttu-id="56671-153">A munkafolyamat által feldolgozandó kérelem elküldése.</span><span class="sxs-lookup"><span data-stu-id="56671-153">Submit the request to be processed by workflow.</span></span> |

## <a name="see-also"></a><span data-ttu-id="56671-154">Lásd még</span><span class="sxs-lookup"><span data-stu-id="56671-154">See also</span></span>

- [<span data-ttu-id="56671-155">Szabadságkérelem elküldése munkafolyamathoz</span><span class="sxs-lookup"><span data-stu-id="56671-155">Submit a leave request to workflow</span></span>](hr-developer-api-myleaverequests-submit.md)
- [<span data-ttu-id="56671-156">Hitelesítés</span><span class="sxs-lookup"><span data-stu-id="56671-156">Authentication</span></span>](hr-developer-api-authentication.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]