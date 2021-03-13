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
ms.openlocfilehash: 55ed9c391a1b5f86c3c443b9fceeee5c2301444d
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/05/2021
ms.locfileid: "5125954"
---
# <a name="recruiting-request-status"></a><span data-ttu-id="c68f3-103">Toborzási kérelem állapota</span><span class="sxs-lookup"><span data-stu-id="c68f3-103">Recruiting request status</span></span>

<span data-ttu-id="c68f3-104">Ez a témakör a Toborzási kérelem állapota beállításkészletet írja le a Dynamics 365 Human Resources rendszerhez.</span><span class="sxs-lookup"><span data-stu-id="c68f3-104">This topic describes the Recruiting request status option set for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="c68f3-105">Fizikai név: mshr_hcmrecruitingrequeststatus</span><span class="sxs-lookup"><span data-stu-id="c68f3-105">Physical name: mshr_hcmrecruitingrequeststatus</span></span>

<span data-ttu-id="c68f3-106">Ez a felsorolás a toborzási kérelem állapotértékeinek beállításkészletét adja meg.</span><span class="sxs-lookup"><span data-stu-id="c68f3-106">This enumeration provides the option set for the status values of a RecruitingRequest.</span></span>

| <span data-ttu-id="c68f3-107">Érték</span><span class="sxs-lookup"><span data-stu-id="c68f3-107">Value</span></span> | <span data-ttu-id="c68f3-108">Címke</span><span class="sxs-lookup"><span data-stu-id="c68f3-108">Label</span></span> | <span data-ttu-id="c68f3-109">Leírás</span><span class="sxs-lookup"><span data-stu-id="c68f3-109">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="c68f3-110">200000000</span><span class="sxs-lookup"><span data-stu-id="c68f3-110">200000000</span></span> | <span data-ttu-id="c68f3-111">Piszkozat</span><span class="sxs-lookup"><span data-stu-id="c68f3-111">Draft</span></span> | <span data-ttu-id="c68f3-112">A kérelem piszkozatban van, és nem áll készen az aktív toborzásra.</span><span class="sxs-lookup"><span data-stu-id="c68f3-112">The request is in draft and isn't ready for active recruiting.</span></span> |
| <span data-ttu-id="c68f3-113">200000001</span><span class="sxs-lookup"><span data-stu-id="c68f3-113">200000001</span></span> | <span data-ttu-id="c68f3-114">Ellenőrzés alatt</span><span class="sxs-lookup"><span data-stu-id="c68f3-114">In Review</span></span> | <span data-ttu-id="c68f3-115">A kérelmet elküldték, most pedig a munkafolyamat jóváhagyására vár.</span><span class="sxs-lookup"><span data-stu-id="c68f3-115">The request has been submitted and is being routed for approval by workflow.</span></span> <span data-ttu-id="c68f3-116">Csak akkor érhető el, ha a munkafolyamat engedélyezve van.</span><span class="sxs-lookup"><span data-stu-id="c68f3-116">Only available when workflow is enabled.</span></span> |
| <span data-ttu-id="c68f3-117">200000002</span><span class="sxs-lookup"><span data-stu-id="c68f3-117">200000002</span></span> | <span data-ttu-id="c68f3-118">Függőben</span><span class="sxs-lookup"><span data-stu-id="c68f3-118">Pending</span></span> | <span data-ttu-id="c68f3-119">A kérelem munkafolyamat-műveletre vár.</span><span class="sxs-lookup"><span data-stu-id="c68f3-119">The request is pending workflow action.</span></span> <span data-ttu-id="c68f3-120">Csak akkor érhető el, ha a munkafolyamat engedélyezve van.</span><span class="sxs-lookup"><span data-stu-id="c68f3-120">Only available when workflow is enabled.</span></span> |
| <span data-ttu-id="c68f3-121">200000003</span><span class="sxs-lookup"><span data-stu-id="c68f3-121">200000003</span></span> | <span data-ttu-id="c68f3-122">Érvénytelenítve</span><span class="sxs-lookup"><span data-stu-id="c68f3-122">Canceled</span></span> | <span data-ttu-id="c68f3-123">A kérés törlésre került.</span><span class="sxs-lookup"><span data-stu-id="c68f3-123">The request has been canceled.</span></span> <span data-ttu-id="c68f3-124">Csak akkor érhető el, ha a munkafolyamat engedélyezve van.</span><span class="sxs-lookup"><span data-stu-id="c68f3-124">Only available when workflow is enabled.</span></span> |
| <span data-ttu-id="c68f3-125">200000004</span><span class="sxs-lookup"><span data-stu-id="c68f3-125">200000004</span></span> | <span data-ttu-id="c68f3-126">Megtagadva</span><span class="sxs-lookup"><span data-stu-id="c68f3-126">Denied</span></span> | <span data-ttu-id="c68f3-127">A kérelmet megtagadták.</span><span class="sxs-lookup"><span data-stu-id="c68f3-127">The request has been denied.</span></span> <span data-ttu-id="c68f3-128">Csak akkor érhető el, ha a munkafolyamat engedélyezve van.</span><span class="sxs-lookup"><span data-stu-id="c68f3-128">Only available when workflow is enabled.</span></span> |
| <span data-ttu-id="c68f3-129">200000005</span><span class="sxs-lookup"><span data-stu-id="c68f3-129">200000005</span></span> | <span data-ttu-id="c68f3-130">Aktív</span><span class="sxs-lookup"><span data-stu-id="c68f3-130">Active</span></span> | <span data-ttu-id="c68f3-131">Minden munkafolyamatot befejeztek és jóváhagytak, és a kérelem készen áll az aktív toborzásra.</span><span class="sxs-lookup"><span data-stu-id="c68f3-131">Any workflow is completed and approved, and the request is ready for active recruiting.</span></span> |
| <span data-ttu-id="c68f3-132">200000006</span><span class="sxs-lookup"><span data-stu-id="c68f3-132">200000006</span></span> | <span data-ttu-id="c68f3-133">Lezárva</span><span class="sxs-lookup"><span data-stu-id="c68f3-133">Closed</span></span> | <span data-ttu-id="c68f3-134">A toborzási kérelmet lezárták.</span><span class="sxs-lookup"><span data-stu-id="c68f3-134">The recruiting request is closed.</span></span> |

## <a name="see-also"></a><span data-ttu-id="c68f3-135">Lásd még</span><span class="sxs-lookup"><span data-stu-id="c68f3-135">See also</span></span>

[<span data-ttu-id="c68f3-136">Pályázó követésrendszer integrációs API bevezetése</span><span class="sxs-lookup"><span data-stu-id="c68f3-136">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="c68f3-137">Példa lekérdezésre Toborzási kérelemmel kapcsolatban</span><span class="sxs-lookup"><span data-stu-id="c68f3-137">Example query for Recruiting request</span></span>](hr-admin-integration-ats-api-recruiting-request-example-query.md)
