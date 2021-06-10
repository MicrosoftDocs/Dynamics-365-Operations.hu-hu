---
title: Toborzási kérelem állapota
description: Ez a témakör a Toborzási kérelem állapota beállításkészletet írja le a Dynamics 365 Human Resources rendszerhez.
author: jaredha
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 3b05cc531a84144708ff52913927bbd04574a3b2
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059184"
---
# <a name="recruiting-request-status"></a><span data-ttu-id="2ef75-103">Toborzási kérelem állapota</span><span class="sxs-lookup"><span data-stu-id="2ef75-103">Recruiting request status</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="2ef75-104">Ez a témakör a Toborzási kérelem állapota beállításkészletet írja le a Dynamics 365 Human Resources rendszerhez.</span><span class="sxs-lookup"><span data-stu-id="2ef75-104">This topic describes the Recruiting request status option set for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="2ef75-105">Fizikai név: mshr_hcmrecruitingrequeststatus</span><span class="sxs-lookup"><span data-stu-id="2ef75-105">Physical name: mshr_hcmrecruitingrequeststatus</span></span>

<span data-ttu-id="2ef75-106">Ez a felsorolás a toborzási kérelem állapotértékeinek beállításkészletét adja meg.</span><span class="sxs-lookup"><span data-stu-id="2ef75-106">This enumeration provides the option set for the status values of a RecruitingRequest.</span></span>

| <span data-ttu-id="2ef75-107">Érték</span><span class="sxs-lookup"><span data-stu-id="2ef75-107">Value</span></span> | <span data-ttu-id="2ef75-108">Címke</span><span class="sxs-lookup"><span data-stu-id="2ef75-108">Label</span></span> | <span data-ttu-id="2ef75-109">Leírás</span><span class="sxs-lookup"><span data-stu-id="2ef75-109">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="2ef75-110">200000000</span><span class="sxs-lookup"><span data-stu-id="2ef75-110">200000000</span></span> | <span data-ttu-id="2ef75-111">Piszkozat</span><span class="sxs-lookup"><span data-stu-id="2ef75-111">Draft</span></span> | <span data-ttu-id="2ef75-112">A kérelem piszkozatban van, és nem áll készen az aktív toborzásra.</span><span class="sxs-lookup"><span data-stu-id="2ef75-112">The request is in draft and isn't ready for active recruiting.</span></span> |
| <span data-ttu-id="2ef75-113">200000001</span><span class="sxs-lookup"><span data-stu-id="2ef75-113">200000001</span></span> | <span data-ttu-id="2ef75-114">Ellenőrzés alatt</span><span class="sxs-lookup"><span data-stu-id="2ef75-114">In Review</span></span> | <span data-ttu-id="2ef75-115">A kérelmet elküldték, most pedig a munkafolyamat jóváhagyására vár.</span><span class="sxs-lookup"><span data-stu-id="2ef75-115">The request has been submitted and is being routed for approval by workflow.</span></span> <span data-ttu-id="2ef75-116">Csak akkor érhető el, ha a munkafolyamat engedélyezve van.</span><span class="sxs-lookup"><span data-stu-id="2ef75-116">Only available when workflow is enabled.</span></span> |
| <span data-ttu-id="2ef75-117">200000002</span><span class="sxs-lookup"><span data-stu-id="2ef75-117">200000002</span></span> | <span data-ttu-id="2ef75-118">Függőben</span><span class="sxs-lookup"><span data-stu-id="2ef75-118">Pending</span></span> | <span data-ttu-id="2ef75-119">A kérelem munkafolyamat-műveletre vár.</span><span class="sxs-lookup"><span data-stu-id="2ef75-119">The request is pending workflow action.</span></span> <span data-ttu-id="2ef75-120">Csak akkor érhető el, ha a munkafolyamat engedélyezve van.</span><span class="sxs-lookup"><span data-stu-id="2ef75-120">Only available when workflow is enabled.</span></span> |
| <span data-ttu-id="2ef75-121">200000003</span><span class="sxs-lookup"><span data-stu-id="2ef75-121">200000003</span></span> | <span data-ttu-id="2ef75-122">Érvénytelenítve</span><span class="sxs-lookup"><span data-stu-id="2ef75-122">Canceled</span></span> | <span data-ttu-id="2ef75-123">A kérés törlésre került.</span><span class="sxs-lookup"><span data-stu-id="2ef75-123">The request has been canceled.</span></span> <span data-ttu-id="2ef75-124">Csak akkor érhető el, ha a munkafolyamat engedélyezve van.</span><span class="sxs-lookup"><span data-stu-id="2ef75-124">Only available when workflow is enabled.</span></span> |
| <span data-ttu-id="2ef75-125">200000004</span><span class="sxs-lookup"><span data-stu-id="2ef75-125">200000004</span></span> | <span data-ttu-id="2ef75-126">Megtagadva</span><span class="sxs-lookup"><span data-stu-id="2ef75-126">Denied</span></span> | <span data-ttu-id="2ef75-127">A kérelmet megtagadták.</span><span class="sxs-lookup"><span data-stu-id="2ef75-127">The request has been denied.</span></span> <span data-ttu-id="2ef75-128">Csak akkor érhető el, ha a munkafolyamat engedélyezve van.</span><span class="sxs-lookup"><span data-stu-id="2ef75-128">Only available when workflow is enabled.</span></span> |
| <span data-ttu-id="2ef75-129">200000005</span><span class="sxs-lookup"><span data-stu-id="2ef75-129">200000005</span></span> | <span data-ttu-id="2ef75-130">Aktív</span><span class="sxs-lookup"><span data-stu-id="2ef75-130">Active</span></span> | <span data-ttu-id="2ef75-131">Minden munkafolyamatot befejeztek és jóváhagytak, és a kérelem készen áll az aktív toborzásra.</span><span class="sxs-lookup"><span data-stu-id="2ef75-131">Any workflow is completed and approved, and the request is ready for active recruiting.</span></span> |
| <span data-ttu-id="2ef75-132">200000006</span><span class="sxs-lookup"><span data-stu-id="2ef75-132">200000006</span></span> | <span data-ttu-id="2ef75-133">Lezárva</span><span class="sxs-lookup"><span data-stu-id="2ef75-133">Closed</span></span> | <span data-ttu-id="2ef75-134">A toborzási kérelmet lezárták.</span><span class="sxs-lookup"><span data-stu-id="2ef75-134">The recruiting request is closed.</span></span> |

## <a name="see-also"></a><span data-ttu-id="2ef75-135">Lásd még</span><span class="sxs-lookup"><span data-stu-id="2ef75-135">See also</span></span>

[<span data-ttu-id="2ef75-136">Pályázó követésrendszer integrációs API bevezetése</span><span class="sxs-lookup"><span data-stu-id="2ef75-136">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="2ef75-137">Példa lekérdezésre Toborzási kérelemmel kapcsolatban</span><span class="sxs-lookup"><span data-stu-id="2ef75-137">Example query for Recruiting request</span></span>](hr-admin-integration-ats-api-recruiting-request-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]