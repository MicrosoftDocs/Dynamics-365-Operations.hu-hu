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
ms.openlocfilehash: c2c14a0cc935ad166a2c6600f1e96c3e09ab16ca
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/17/2021
ms.locfileid: "5465510"
---
# <a name="myleaverequests-overview"></a><span data-ttu-id="e8ab2-103">MyLeaveRequests áttekintése</span><span class="sxs-lookup"><span data-stu-id="e8ab2-103">MyLeaveRequests overview</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="e8ab2-104">A Microsoft Dynamics 365 Human Resources MyLeaveRequests entitása biztosítja a Szabadságkérelmek listáját a rendszerben, amely az entitást lekérdező felhasználó számára elérhető kérelmek körére korlátozódik.</span><span class="sxs-lookup"><span data-stu-id="e8ab2-104">The MyLeaveRequests entity in Microsoft Dynamics 365 Human Resources provides the list of Leave Requests in the system, scoped (limited) to the requests accessible to the current user querying the entity.</span></span>

## <a name="key"></a><span data-ttu-id="e8ab2-105">Kulcs</span><span class="sxs-lookup"><span data-stu-id="e8ab2-105">Key</span></span>

  | <span data-ttu-id="e8ab2-106">Tulajdonság neve</span><span class="sxs-lookup"><span data-stu-id="e8ab2-106">Property Name</span></span> | <span data-ttu-id="e8ab2-107">Adattípus</span><span class="sxs-lookup"><span data-stu-id="e8ab2-107">Data Type</span></span> |
  |---------------|-----------|
  | <span data-ttu-id="e8ab2-108">dataAreaId</span><span class="sxs-lookup"><span data-stu-id="e8ab2-108">dataAreaId</span></span>    | <span data-ttu-id="e8ab2-109">Karakterlánc</span><span class="sxs-lookup"><span data-stu-id="e8ab2-109">String</span></span>    |
  | <span data-ttu-id="e8ab2-110">RequestId</span><span class="sxs-lookup"><span data-stu-id="e8ab2-110">RequestId</span></span>     | <span data-ttu-id="e8ab2-111">Karakterlánc</span><span class="sxs-lookup"><span data-stu-id="e8ab2-111">String</span></span>    |
  | <span data-ttu-id="e8ab2-112">LeaveType</span><span class="sxs-lookup"><span data-stu-id="e8ab2-112">LeaveType</span></span>     | <span data-ttu-id="e8ab2-113">Karakterlánc</span><span class="sxs-lookup"><span data-stu-id="e8ab2-113">String</span></span>    |
  | <span data-ttu-id="e8ab2-114">LeaveDate</span><span class="sxs-lookup"><span data-stu-id="e8ab2-114">LeaveDate</span></span>     | <span data-ttu-id="e8ab2-115">Dátum</span><span class="sxs-lookup"><span data-stu-id="e8ab2-115">Date</span></span>      |
  
## <a name="properties"></a><span data-ttu-id="e8ab2-116">Tulajdonságok</span><span class="sxs-lookup"><span data-stu-id="e8ab2-116">Properties</span></span>

  | <span data-ttu-id="e8ab2-117">Tulajdonság neve</span><span class="sxs-lookup"><span data-stu-id="e8ab2-117">Property Name</span></span>     | <span data-ttu-id="e8ab2-118">Adattípus</span><span class="sxs-lookup"><span data-stu-id="e8ab2-118">Data Type</span></span> | <span data-ttu-id="e8ab2-119">Kötelező</span><span class="sxs-lookup"><span data-stu-id="e8ab2-119">Required</span></span> |
  |-------------------|-----------|----------|
  | <span data-ttu-id="e8ab2-120">dataAreaId</span><span class="sxs-lookup"><span data-stu-id="e8ab2-120">dataAreaId</span></span>        | <span data-ttu-id="e8ab2-121">Karakterlánc</span><span class="sxs-lookup"><span data-stu-id="e8ab2-121">String</span></span>    | <span data-ttu-id="e8ab2-122">X</span><span class="sxs-lookup"><span data-stu-id="e8ab2-122">X</span></span>        |
  | <span data-ttu-id="e8ab2-123">RequestId</span><span class="sxs-lookup"><span data-stu-id="e8ab2-123">RequestId</span></span>         | <span data-ttu-id="e8ab2-124">Karakterlánc</span><span class="sxs-lookup"><span data-stu-id="e8ab2-124">String</span></span>    | <span data-ttu-id="e8ab2-125">X</span><span class="sxs-lookup"><span data-stu-id="e8ab2-125">X</span></span>        |
  | <span data-ttu-id="e8ab2-126">LeaveType</span><span class="sxs-lookup"><span data-stu-id="e8ab2-126">LeaveType</span></span>         | <span data-ttu-id="e8ab2-127">Karakterlánc</span><span class="sxs-lookup"><span data-stu-id="e8ab2-127">String</span></span>    | <span data-ttu-id="e8ab2-128">X</span><span class="sxs-lookup"><span data-stu-id="e8ab2-128">X</span></span>        |
  | <span data-ttu-id="e8ab2-129">LeaveDate</span><span class="sxs-lookup"><span data-stu-id="e8ab2-129">LeaveDate</span></span>         | <span data-ttu-id="e8ab2-130">Dátum</span><span class="sxs-lookup"><span data-stu-id="e8ab2-130">Date</span></span>      | <span data-ttu-id="e8ab2-131">X</span><span class="sxs-lookup"><span data-stu-id="e8ab2-131">X</span></span>        |
  | <span data-ttu-id="e8ab2-132">ReasonCodeId</span><span class="sxs-lookup"><span data-stu-id="e8ab2-132">ReasonCodeId</span></span>      | <span data-ttu-id="e8ab2-133">Karakterlánc</span><span class="sxs-lookup"><span data-stu-id="e8ab2-133">String</span></span>    |          |
  | <span data-ttu-id="e8ab2-134">PersonnelNumber</span><span class="sxs-lookup"><span data-stu-id="e8ab2-134">PersonnelNumber</span></span>   | <span data-ttu-id="e8ab2-135">Karakterlánc</span><span class="sxs-lookup"><span data-stu-id="e8ab2-135">String</span></span>    | <span data-ttu-id="e8ab2-136">X</span><span class="sxs-lookup"><span data-stu-id="e8ab2-136">X</span></span>        |
  | <span data-ttu-id="e8ab2-137">RequestDate</span><span class="sxs-lookup"><span data-stu-id="e8ab2-137">RequestDate</span></span>       | <span data-ttu-id="e8ab2-138">Dátum</span><span class="sxs-lookup"><span data-stu-id="e8ab2-138">Date</span></span>      | <span data-ttu-id="e8ab2-139">X</span><span class="sxs-lookup"><span data-stu-id="e8ab2-139">X</span></span>        |
  | <span data-ttu-id="e8ab2-140">Megjegyzés</span><span class="sxs-lookup"><span data-stu-id="e8ab2-140">Comment</span></span>           | <span data-ttu-id="e8ab2-141">Karakterlánc</span><span class="sxs-lookup"><span data-stu-id="e8ab2-141">String</span></span>    |          |
  | <span data-ttu-id="e8ab2-142">Állapot</span><span class="sxs-lookup"><span data-stu-id="e8ab2-142">Status</span></span>            | <span data-ttu-id="e8ab2-143">Felsorolás</span><span class="sxs-lookup"><span data-stu-id="e8ab2-143">Enum</span></span>      | <span data-ttu-id="e8ab2-144">X</span><span class="sxs-lookup"><span data-stu-id="e8ab2-144">X</span></span>        |
  | <span data-ttu-id="e8ab2-145">Összeg</span><span class="sxs-lookup"><span data-stu-id="e8ab2-145">Amount</span></span>            | <span data-ttu-id="e8ab2-146">Valós</span><span class="sxs-lookup"><span data-stu-id="e8ab2-146">Real</span></span>      |          |
  | <span data-ttu-id="e8ab2-147">HalfDayDefinition</span><span class="sxs-lookup"><span data-stu-id="e8ab2-147">HalfDayDefinition</span></span> | <span data-ttu-id="e8ab2-148">Felsorolás</span><span class="sxs-lookup"><span data-stu-id="e8ab2-148">Enum</span></span>      |          |

## <a name="actions"></a><span data-ttu-id="e8ab2-149">Műveletek</span><span class="sxs-lookup"><span data-stu-id="e8ab2-149">Actions</span></span>

 | <span data-ttu-id="e8ab2-150">Művelet neve</span><span class="sxs-lookup"><span data-stu-id="e8ab2-150">Action Name</span></span>                               | <span data-ttu-id="e8ab2-151">Leírás</span><span class="sxs-lookup"><span data-stu-id="e8ab2-151">Description</span></span>                                     |
 |-------------------------------------------|-------------------------------------------------|
 | [<span data-ttu-id="e8ab2-152">küldés</span><span class="sxs-lookup"><span data-stu-id="e8ab2-152">submit</span></span>](hr-developer-api-myleaverequests-submit.md)   | <span data-ttu-id="e8ab2-153">A munkafolyamat által feldolgozandó kérelem elküldése.</span><span class="sxs-lookup"><span data-stu-id="e8ab2-153">Submit the request to be processed by workflow.</span></span> |

## <a name="see-also"></a><span data-ttu-id="e8ab2-154">Lásd még</span><span class="sxs-lookup"><span data-stu-id="e8ab2-154">See also</span></span>

- [<span data-ttu-id="e8ab2-155">Szabadságkérelem elküldése munkafolyamathoz</span><span class="sxs-lookup"><span data-stu-id="e8ab2-155">Submit a leave request to workflow</span></span>](hr-developer-api-myleaverequests-submit.md)
- [<span data-ttu-id="e8ab2-156">Hitelesítés</span><span class="sxs-lookup"><span data-stu-id="e8ab2-156">Authentication</span></span>](hr-developer-api-authentication.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]