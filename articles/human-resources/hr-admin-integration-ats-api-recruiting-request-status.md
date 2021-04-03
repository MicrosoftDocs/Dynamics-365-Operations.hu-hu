---
title: Toborzási kérelem állapota
description: Ez a témakör a Toborzási kérelem állapota beállításkészletet írja le a Dynamics 365 Human Resources rendszerhez.
author: jaredha
manager: tfehr
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0032e6bfdbfd2792dafda8bf24a1b0cbc551740d
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/17/2021
ms.locfileid: "5464646"
---
# <a name="recruiting-request-status"></a><span data-ttu-id="84936-103">Toborzási kérelem állapota</span><span class="sxs-lookup"><span data-stu-id="84936-103">Recruiting request status</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="84936-104">Ez a témakör a Toborzási kérelem állapota beállításkészletet írja le a Dynamics 365 Human Resources rendszerhez.</span><span class="sxs-lookup"><span data-stu-id="84936-104">This topic describes the Recruiting request status option set for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="84936-105">Fizikai név: mshr_hcmrecruitingrequeststatus</span><span class="sxs-lookup"><span data-stu-id="84936-105">Physical name: mshr_hcmrecruitingrequeststatus</span></span>

<span data-ttu-id="84936-106">Ez a felsorolás a toborzási kérelem állapotértékeinek beállításkészletét adja meg.</span><span class="sxs-lookup"><span data-stu-id="84936-106">This enumeration provides the option set for the status values of a RecruitingRequest.</span></span>

| <span data-ttu-id="84936-107">Érték</span><span class="sxs-lookup"><span data-stu-id="84936-107">Value</span></span> | <span data-ttu-id="84936-108">Címke</span><span class="sxs-lookup"><span data-stu-id="84936-108">Label</span></span> | <span data-ttu-id="84936-109">Leírás</span><span class="sxs-lookup"><span data-stu-id="84936-109">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="84936-110">200000000</span><span class="sxs-lookup"><span data-stu-id="84936-110">200000000</span></span> | <span data-ttu-id="84936-111">Piszkozat</span><span class="sxs-lookup"><span data-stu-id="84936-111">Draft</span></span> | <span data-ttu-id="84936-112">A kérelem piszkozatban van, és nem áll készen az aktív toborzásra.</span><span class="sxs-lookup"><span data-stu-id="84936-112">The request is in draft and isn't ready for active recruiting.</span></span> |
| <span data-ttu-id="84936-113">200000001</span><span class="sxs-lookup"><span data-stu-id="84936-113">200000001</span></span> | <span data-ttu-id="84936-114">Ellenőrzés alatt</span><span class="sxs-lookup"><span data-stu-id="84936-114">In Review</span></span> | <span data-ttu-id="84936-115">A kérelmet elküldték, most pedig a munkafolyamat jóváhagyására vár.</span><span class="sxs-lookup"><span data-stu-id="84936-115">The request has been submitted and is being routed for approval by workflow.</span></span> <span data-ttu-id="84936-116">Csak akkor érhető el, ha a munkafolyamat engedélyezve van.</span><span class="sxs-lookup"><span data-stu-id="84936-116">Only available when workflow is enabled.</span></span> |
| <span data-ttu-id="84936-117">200000002</span><span class="sxs-lookup"><span data-stu-id="84936-117">200000002</span></span> | <span data-ttu-id="84936-118">Függőben</span><span class="sxs-lookup"><span data-stu-id="84936-118">Pending</span></span> | <span data-ttu-id="84936-119">A kérelem munkafolyamat-műveletre vár.</span><span class="sxs-lookup"><span data-stu-id="84936-119">The request is pending workflow action.</span></span> <span data-ttu-id="84936-120">Csak akkor érhető el, ha a munkafolyamat engedélyezve van.</span><span class="sxs-lookup"><span data-stu-id="84936-120">Only available when workflow is enabled.</span></span> |
| <span data-ttu-id="84936-121">200000003</span><span class="sxs-lookup"><span data-stu-id="84936-121">200000003</span></span> | <span data-ttu-id="84936-122">Érvénytelenítve</span><span class="sxs-lookup"><span data-stu-id="84936-122">Canceled</span></span> | <span data-ttu-id="84936-123">A kérés törlésre került.</span><span class="sxs-lookup"><span data-stu-id="84936-123">The request has been canceled.</span></span> <span data-ttu-id="84936-124">Csak akkor érhető el, ha a munkafolyamat engedélyezve van.</span><span class="sxs-lookup"><span data-stu-id="84936-124">Only available when workflow is enabled.</span></span> |
| <span data-ttu-id="84936-125">200000004</span><span class="sxs-lookup"><span data-stu-id="84936-125">200000004</span></span> | <span data-ttu-id="84936-126">Megtagadva</span><span class="sxs-lookup"><span data-stu-id="84936-126">Denied</span></span> | <span data-ttu-id="84936-127">A kérelmet megtagadták.</span><span class="sxs-lookup"><span data-stu-id="84936-127">The request has been denied.</span></span> <span data-ttu-id="84936-128">Csak akkor érhető el, ha a munkafolyamat engedélyezve van.</span><span class="sxs-lookup"><span data-stu-id="84936-128">Only available when workflow is enabled.</span></span> |
| <span data-ttu-id="84936-129">200000005</span><span class="sxs-lookup"><span data-stu-id="84936-129">200000005</span></span> | <span data-ttu-id="84936-130">Aktív</span><span class="sxs-lookup"><span data-stu-id="84936-130">Active</span></span> | <span data-ttu-id="84936-131">Minden munkafolyamatot befejeztek és jóváhagytak, és a kérelem készen áll az aktív toborzásra.</span><span class="sxs-lookup"><span data-stu-id="84936-131">Any workflow is completed and approved, and the request is ready for active recruiting.</span></span> |
| <span data-ttu-id="84936-132">200000006</span><span class="sxs-lookup"><span data-stu-id="84936-132">200000006</span></span> | <span data-ttu-id="84936-133">Lezárva</span><span class="sxs-lookup"><span data-stu-id="84936-133">Closed</span></span> | <span data-ttu-id="84936-134">A toborzási kérelmet lezárták.</span><span class="sxs-lookup"><span data-stu-id="84936-134">The recruiting request is closed.</span></span> |

## <a name="see-also"></a><span data-ttu-id="84936-135">Lásd még</span><span class="sxs-lookup"><span data-stu-id="84936-135">See also</span></span>

[<span data-ttu-id="84936-136">Pályázó követésrendszer integrációs API bevezetése</span><span class="sxs-lookup"><span data-stu-id="84936-136">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="84936-137">Példa lekérdezésre Toborzási kérelemmel kapcsolatban</span><span class="sxs-lookup"><span data-stu-id="84936-137">Example query for Recruiting request</span></span>](hr-admin-integration-ats-api-recruiting-request-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]