---
title: Toborzási kérelem – pozíció állapota
description: Ez a témakör a Toborzási kérelem – pozíció állapota beállításkészletet írja le a Dynamics 365 Human Resources rendszerhez.
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
ms.openlocfilehash: 3f7bae64f58f0bdc1603b3c1b5493f1ebcfa8de9
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/05/2021
ms.locfileid: "5126050"
---
# <a name="recruiting-request-position-status"></a><span data-ttu-id="cfda2-103">Toborzási kérelem – pozíció állapota</span><span class="sxs-lookup"><span data-stu-id="cfda2-103">Recruiting request position status</span></span>

<span data-ttu-id="cfda2-104">Ez a témakör a Toborzási kérelem – pozíció állapota beállításkészletet írja le a Dynamics 365 Human Resources rendszerhez.</span><span class="sxs-lookup"><span data-stu-id="cfda2-104">This topic describes the Recruiting request position status option set for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="cfda2-105">Fizikai név: mshr_hcmrecruitingrequestpositionstatus</span><span class="sxs-lookup"><span data-stu-id="cfda2-105">Physical name: mshr_hcmrecruitingrequestpositionstatus</span></span>

<span data-ttu-id="cfda2-106">Ez a felsorolás biztosítja a beállításkészletet a RecruitingRequestPosition entitásnál toborzási kérelemként megadott beosztások állapotértékére.</span><span class="sxs-lookup"><span data-stu-id="cfda2-106">This enumeration provides the option set for the status values of each position a recruiting request in the RecruitingRequestPosition entity.</span></span>

| <span data-ttu-id="cfda2-107">Érték</span><span class="sxs-lookup"><span data-stu-id="cfda2-107">Value</span></span> | <span data-ttu-id="cfda2-108">Címke</span><span class="sxs-lookup"><span data-stu-id="cfda2-108">Label</span></span> | <span data-ttu-id="cfda2-109">Leírás</span><span class="sxs-lookup"><span data-stu-id="cfda2-109">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="cfda2-110">200000000</span><span class="sxs-lookup"><span data-stu-id="cfda2-110">200000000</span></span> | <span data-ttu-id="cfda2-111">Megnyitva</span><span class="sxs-lookup"><span data-stu-id="cfda2-111">Open</span></span> | <span data-ttu-id="cfda2-112">A toborzási kérelemben lévő beosztás meg van nyitva toborzásra.</span><span class="sxs-lookup"><span data-stu-id="cfda2-112">The position in the recruiting request is open for recruiting.</span></span> <span data-ttu-id="cfda2-113">Ez nem azt jelzi, hogy jelenleg nincs aktív beosztás-hozzárendelés a beosztásra vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="cfda2-113">This does not indicate that there is no currently active position assignment for the position.</span></span> <span data-ttu-id="cfda2-114">Megtörténhet, hogy a toborzás ideje alatt a beosztásban egy alkalmazott dolgozik.</span><span class="sxs-lookup"><span data-stu-id="cfda2-114">There may be an employee in the position at the time of recruiting.</span></span> <span data-ttu-id="cfda2-115">Kizárólag azt jelzi, hogy a beosztás toborzásra elérhető a toborzási kérelem keretében.</span><span class="sxs-lookup"><span data-stu-id="cfda2-115">It indicates only that the position is available for recruiting in the context of the recruiting request.</span></span> |
| <span data-ttu-id="cfda2-116">200000001</span><span class="sxs-lookup"><span data-stu-id="cfda2-116">200000001</span></span> | <span data-ttu-id="cfda2-117">Betöltve</span><span class="sxs-lookup"><span data-stu-id="cfda2-117">Filled</span></span> | <span data-ttu-id="cfda2-118">Egy dolgozót kiválasztottak a beosztáshoz való hozzárendelésre.</span><span class="sxs-lookup"><span data-stu-id="cfda2-118">A worker has been selected for assignment to the position.</span></span> |
| <span data-ttu-id="cfda2-119">200000002</span><span class="sxs-lookup"><span data-stu-id="cfda2-119">200000002</span></span> | <span data-ttu-id="cfda2-120">Érvénytelenítve</span><span class="sxs-lookup"><span data-stu-id="cfda2-120">Canceled</span></span> | <span data-ttu-id="cfda2-121">A beosztás toborzási kérelmét visszavonták.</span><span class="sxs-lookup"><span data-stu-id="cfda2-121">The request to recruit for this position has been canceled.</span></span> |

## <a name="see-also"></a><span data-ttu-id="cfda2-122">Lásd még</span><span class="sxs-lookup"><span data-stu-id="cfda2-122">See also</span></span>

[<span data-ttu-id="cfda2-123">Pályázó követésrendszer integrációs API bevezetése</span><span class="sxs-lookup"><span data-stu-id="cfda2-123">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="cfda2-124">Példa lekérdezésre Toborzási kérelemmel kapcsolatban</span><span class="sxs-lookup"><span data-stu-id="cfda2-124">Example query for Recruiting request</span></span>](hr-admin-integration-ats-api-recruiting-request-example-query.md)
