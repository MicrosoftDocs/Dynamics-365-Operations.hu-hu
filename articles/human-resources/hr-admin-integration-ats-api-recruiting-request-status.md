---
title: Toborzási kérelem állapota
description: Ez a témakör a Toborzási kérelem állapota beállításkészletet írja le a Dynamics 365 Human Resources rendszerhez.
author: jaredha
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 888fbc511bffbecd837c929049006266191da5ba
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5806042"
---
# <a name="recruiting-request-status"></a><span data-ttu-id="ec5ae-103">Toborzási kérelem állapota</span><span class="sxs-lookup"><span data-stu-id="ec5ae-103">Recruiting request status</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="ec5ae-104">Ez a témakör a Toborzási kérelem állapota beállításkészletet írja le a Dynamics 365 Human Resources rendszerhez.</span><span class="sxs-lookup"><span data-stu-id="ec5ae-104">This topic describes the Recruiting request status option set for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="ec5ae-105">Fizikai név: mshr_hcmrecruitingrequeststatus</span><span class="sxs-lookup"><span data-stu-id="ec5ae-105">Physical name: mshr_hcmrecruitingrequeststatus</span></span>

<span data-ttu-id="ec5ae-106">Ez a felsorolás a toborzási kérelem állapotértékeinek beállításkészletét adja meg.</span><span class="sxs-lookup"><span data-stu-id="ec5ae-106">This enumeration provides the option set for the status values of a RecruitingRequest.</span></span>

| <span data-ttu-id="ec5ae-107">Érték</span><span class="sxs-lookup"><span data-stu-id="ec5ae-107">Value</span></span> | <span data-ttu-id="ec5ae-108">Címke</span><span class="sxs-lookup"><span data-stu-id="ec5ae-108">Label</span></span> | <span data-ttu-id="ec5ae-109">Leírás</span><span class="sxs-lookup"><span data-stu-id="ec5ae-109">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="ec5ae-110">200000000</span><span class="sxs-lookup"><span data-stu-id="ec5ae-110">200000000</span></span> | <span data-ttu-id="ec5ae-111">Piszkozat</span><span class="sxs-lookup"><span data-stu-id="ec5ae-111">Draft</span></span> | <span data-ttu-id="ec5ae-112">A kérelem piszkozatban van, és nem áll készen az aktív toborzásra.</span><span class="sxs-lookup"><span data-stu-id="ec5ae-112">The request is in draft and isn't ready for active recruiting.</span></span> |
| <span data-ttu-id="ec5ae-113">200000001</span><span class="sxs-lookup"><span data-stu-id="ec5ae-113">200000001</span></span> | <span data-ttu-id="ec5ae-114">Ellenőrzés alatt</span><span class="sxs-lookup"><span data-stu-id="ec5ae-114">In Review</span></span> | <span data-ttu-id="ec5ae-115">A kérelmet elküldték, most pedig a munkafolyamat jóváhagyására vár.</span><span class="sxs-lookup"><span data-stu-id="ec5ae-115">The request has been submitted and is being routed for approval by workflow.</span></span> <span data-ttu-id="ec5ae-116">Csak akkor érhető el, ha a munkafolyamat engedélyezve van.</span><span class="sxs-lookup"><span data-stu-id="ec5ae-116">Only available when workflow is enabled.</span></span> |
| <span data-ttu-id="ec5ae-117">200000002</span><span class="sxs-lookup"><span data-stu-id="ec5ae-117">200000002</span></span> | <span data-ttu-id="ec5ae-118">Függőben</span><span class="sxs-lookup"><span data-stu-id="ec5ae-118">Pending</span></span> | <span data-ttu-id="ec5ae-119">A kérelem munkafolyamat-műveletre vár.</span><span class="sxs-lookup"><span data-stu-id="ec5ae-119">The request is pending workflow action.</span></span> <span data-ttu-id="ec5ae-120">Csak akkor érhető el, ha a munkafolyamat engedélyezve van.</span><span class="sxs-lookup"><span data-stu-id="ec5ae-120">Only available when workflow is enabled.</span></span> |
| <span data-ttu-id="ec5ae-121">200000003</span><span class="sxs-lookup"><span data-stu-id="ec5ae-121">200000003</span></span> | <span data-ttu-id="ec5ae-122">Érvénytelenítve</span><span class="sxs-lookup"><span data-stu-id="ec5ae-122">Canceled</span></span> | <span data-ttu-id="ec5ae-123">A kérés törlésre került.</span><span class="sxs-lookup"><span data-stu-id="ec5ae-123">The request has been canceled.</span></span> <span data-ttu-id="ec5ae-124">Csak akkor érhető el, ha a munkafolyamat engedélyezve van.</span><span class="sxs-lookup"><span data-stu-id="ec5ae-124">Only available when workflow is enabled.</span></span> |
| <span data-ttu-id="ec5ae-125">200000004</span><span class="sxs-lookup"><span data-stu-id="ec5ae-125">200000004</span></span> | <span data-ttu-id="ec5ae-126">Megtagadva</span><span class="sxs-lookup"><span data-stu-id="ec5ae-126">Denied</span></span> | <span data-ttu-id="ec5ae-127">A kérelmet megtagadták.</span><span class="sxs-lookup"><span data-stu-id="ec5ae-127">The request has been denied.</span></span> <span data-ttu-id="ec5ae-128">Csak akkor érhető el, ha a munkafolyamat engedélyezve van.</span><span class="sxs-lookup"><span data-stu-id="ec5ae-128">Only available when workflow is enabled.</span></span> |
| <span data-ttu-id="ec5ae-129">200000005</span><span class="sxs-lookup"><span data-stu-id="ec5ae-129">200000005</span></span> | <span data-ttu-id="ec5ae-130">Aktív</span><span class="sxs-lookup"><span data-stu-id="ec5ae-130">Active</span></span> | <span data-ttu-id="ec5ae-131">Minden munkafolyamatot befejeztek és jóváhagytak, és a kérelem készen áll az aktív toborzásra.</span><span class="sxs-lookup"><span data-stu-id="ec5ae-131">Any workflow is completed and approved, and the request is ready for active recruiting.</span></span> |
| <span data-ttu-id="ec5ae-132">200000006</span><span class="sxs-lookup"><span data-stu-id="ec5ae-132">200000006</span></span> | <span data-ttu-id="ec5ae-133">Lezárva</span><span class="sxs-lookup"><span data-stu-id="ec5ae-133">Closed</span></span> | <span data-ttu-id="ec5ae-134">A toborzási kérelmet lezárták.</span><span class="sxs-lookup"><span data-stu-id="ec5ae-134">The recruiting request is closed.</span></span> |

## <a name="see-also"></a><span data-ttu-id="ec5ae-135">Lásd még</span><span class="sxs-lookup"><span data-stu-id="ec5ae-135">See also</span></span>

[<span data-ttu-id="ec5ae-136">Pályázó követésrendszer integrációs API bevezetése</span><span class="sxs-lookup"><span data-stu-id="ec5ae-136">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="ec5ae-137">Példa lekérdezésre Toborzási kérelemmel kapcsolatban</span><span class="sxs-lookup"><span data-stu-id="ec5ae-137">Example query for Recruiting request</span></span>](hr-admin-integration-ats-api-recruiting-request-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]