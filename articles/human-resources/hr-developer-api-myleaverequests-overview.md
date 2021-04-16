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
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 44e23a076733bac782a0366aeba3456911522abe
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5803633"
---
# <a name="myleaverequests-overview"></a><span data-ttu-id="a296c-103">MyLeaveRequests áttekintése</span><span class="sxs-lookup"><span data-stu-id="a296c-103">MyLeaveRequests overview</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="a296c-104">A Microsoft Dynamics 365 Human Resources MyLeaveRequests entitása biztosítja a Szabadságkérelmek listáját a rendszerben, amely az entitást lekérdező felhasználó számára elérhető kérelmek körére korlátozódik.</span><span class="sxs-lookup"><span data-stu-id="a296c-104">The MyLeaveRequests entity in Microsoft Dynamics 365 Human Resources provides the list of Leave Requests in the system, scoped (limited) to the requests accessible to the current user querying the entity.</span></span>

## <a name="key"></a><span data-ttu-id="a296c-105">Kulcs</span><span class="sxs-lookup"><span data-stu-id="a296c-105">Key</span></span>

  | <span data-ttu-id="a296c-106">Tulajdonság neve</span><span class="sxs-lookup"><span data-stu-id="a296c-106">Property Name</span></span> | <span data-ttu-id="a296c-107">Adattípus</span><span class="sxs-lookup"><span data-stu-id="a296c-107">Data Type</span></span> |
  |---------------|-----------|
  | <span data-ttu-id="a296c-108">dataAreaId</span><span class="sxs-lookup"><span data-stu-id="a296c-108">dataAreaId</span></span>    | <span data-ttu-id="a296c-109">Karakterlánc</span><span class="sxs-lookup"><span data-stu-id="a296c-109">String</span></span>    |
  | <span data-ttu-id="a296c-110">RequestId</span><span class="sxs-lookup"><span data-stu-id="a296c-110">RequestId</span></span>     | <span data-ttu-id="a296c-111">Karakterlánc</span><span class="sxs-lookup"><span data-stu-id="a296c-111">String</span></span>    |
  | <span data-ttu-id="a296c-112">LeaveType</span><span class="sxs-lookup"><span data-stu-id="a296c-112">LeaveType</span></span>     | <span data-ttu-id="a296c-113">Karakterlánc</span><span class="sxs-lookup"><span data-stu-id="a296c-113">String</span></span>    |
  | <span data-ttu-id="a296c-114">LeaveDate</span><span class="sxs-lookup"><span data-stu-id="a296c-114">LeaveDate</span></span>     | <span data-ttu-id="a296c-115">Dátum</span><span class="sxs-lookup"><span data-stu-id="a296c-115">Date</span></span>      |
  
## <a name="properties"></a><span data-ttu-id="a296c-116">Tulajdonságok</span><span class="sxs-lookup"><span data-stu-id="a296c-116">Properties</span></span>

  | <span data-ttu-id="a296c-117">Tulajdonság neve</span><span class="sxs-lookup"><span data-stu-id="a296c-117">Property Name</span></span>     | <span data-ttu-id="a296c-118">Adattípus</span><span class="sxs-lookup"><span data-stu-id="a296c-118">Data Type</span></span> | <span data-ttu-id="a296c-119">Kötelező</span><span class="sxs-lookup"><span data-stu-id="a296c-119">Required</span></span> |
  |-------------------|-----------|----------|
  | <span data-ttu-id="a296c-120">dataAreaId</span><span class="sxs-lookup"><span data-stu-id="a296c-120">dataAreaId</span></span>        | <span data-ttu-id="a296c-121">Karakterlánc</span><span class="sxs-lookup"><span data-stu-id="a296c-121">String</span></span>    | <span data-ttu-id="a296c-122">X</span><span class="sxs-lookup"><span data-stu-id="a296c-122">X</span></span>        |
  | <span data-ttu-id="a296c-123">RequestId</span><span class="sxs-lookup"><span data-stu-id="a296c-123">RequestId</span></span>         | <span data-ttu-id="a296c-124">Karakterlánc</span><span class="sxs-lookup"><span data-stu-id="a296c-124">String</span></span>    | <span data-ttu-id="a296c-125">X</span><span class="sxs-lookup"><span data-stu-id="a296c-125">X</span></span>        |
  | <span data-ttu-id="a296c-126">LeaveType</span><span class="sxs-lookup"><span data-stu-id="a296c-126">LeaveType</span></span>         | <span data-ttu-id="a296c-127">Karakterlánc</span><span class="sxs-lookup"><span data-stu-id="a296c-127">String</span></span>    | <span data-ttu-id="a296c-128">X</span><span class="sxs-lookup"><span data-stu-id="a296c-128">X</span></span>        |
  | <span data-ttu-id="a296c-129">LeaveDate</span><span class="sxs-lookup"><span data-stu-id="a296c-129">LeaveDate</span></span>         | <span data-ttu-id="a296c-130">Dátum</span><span class="sxs-lookup"><span data-stu-id="a296c-130">Date</span></span>      | <span data-ttu-id="a296c-131">X</span><span class="sxs-lookup"><span data-stu-id="a296c-131">X</span></span>        |
  | <span data-ttu-id="a296c-132">ReasonCodeId</span><span class="sxs-lookup"><span data-stu-id="a296c-132">ReasonCodeId</span></span>      | <span data-ttu-id="a296c-133">Karakterlánc</span><span class="sxs-lookup"><span data-stu-id="a296c-133">String</span></span>    |          |
  | <span data-ttu-id="a296c-134">PersonnelNumber</span><span class="sxs-lookup"><span data-stu-id="a296c-134">PersonnelNumber</span></span>   | <span data-ttu-id="a296c-135">Karakterlánc</span><span class="sxs-lookup"><span data-stu-id="a296c-135">String</span></span>    | <span data-ttu-id="a296c-136">X</span><span class="sxs-lookup"><span data-stu-id="a296c-136">X</span></span>        |
  | <span data-ttu-id="a296c-137">RequestDate</span><span class="sxs-lookup"><span data-stu-id="a296c-137">RequestDate</span></span>       | <span data-ttu-id="a296c-138">Dátum</span><span class="sxs-lookup"><span data-stu-id="a296c-138">Date</span></span>      | <span data-ttu-id="a296c-139">X</span><span class="sxs-lookup"><span data-stu-id="a296c-139">X</span></span>        |
  | <span data-ttu-id="a296c-140">Megjegyzés</span><span class="sxs-lookup"><span data-stu-id="a296c-140">Comment</span></span>           | <span data-ttu-id="a296c-141">Karakterlánc</span><span class="sxs-lookup"><span data-stu-id="a296c-141">String</span></span>    |          |
  | <span data-ttu-id="a296c-142">Állapot</span><span class="sxs-lookup"><span data-stu-id="a296c-142">Status</span></span>            | <span data-ttu-id="a296c-143">Felsorolás</span><span class="sxs-lookup"><span data-stu-id="a296c-143">Enum</span></span>      | <span data-ttu-id="a296c-144">X</span><span class="sxs-lookup"><span data-stu-id="a296c-144">X</span></span>        |
  | <span data-ttu-id="a296c-145">Összeg</span><span class="sxs-lookup"><span data-stu-id="a296c-145">Amount</span></span>            | <span data-ttu-id="a296c-146">Valós</span><span class="sxs-lookup"><span data-stu-id="a296c-146">Real</span></span>      |          |
  | <span data-ttu-id="a296c-147">HalfDayDefinition</span><span class="sxs-lookup"><span data-stu-id="a296c-147">HalfDayDefinition</span></span> | <span data-ttu-id="a296c-148">Felsorolás</span><span class="sxs-lookup"><span data-stu-id="a296c-148">Enum</span></span>      |          |

## <a name="actions"></a><span data-ttu-id="a296c-149">Műveletek</span><span class="sxs-lookup"><span data-stu-id="a296c-149">Actions</span></span>

 | <span data-ttu-id="a296c-150">Művelet neve</span><span class="sxs-lookup"><span data-stu-id="a296c-150">Action Name</span></span>                               | <span data-ttu-id="a296c-151">Leírás</span><span class="sxs-lookup"><span data-stu-id="a296c-151">Description</span></span>                                     |
 |-------------------------------------------|-------------------------------------------------|
 | [<span data-ttu-id="a296c-152">küldés</span><span class="sxs-lookup"><span data-stu-id="a296c-152">submit</span></span>](hr-developer-api-myleaverequests-submit.md)   | <span data-ttu-id="a296c-153">A munkafolyamat által feldolgozandó kérelem elküldése.</span><span class="sxs-lookup"><span data-stu-id="a296c-153">Submit the request to be processed by workflow.</span></span> |

## <a name="see-also"></a><span data-ttu-id="a296c-154">Lásd még</span><span class="sxs-lookup"><span data-stu-id="a296c-154">See also</span></span>

- [<span data-ttu-id="a296c-155">Szabadságkérelem elküldése munkafolyamathoz</span><span class="sxs-lookup"><span data-stu-id="a296c-155">Submit a leave request to workflow</span></span>](hr-developer-api-myleaverequests-submit.md)
- [<span data-ttu-id="a296c-156">Hitelesítés</span><span class="sxs-lookup"><span data-stu-id="a296c-156">Authentication</span></span>](hr-developer-api-authentication.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]