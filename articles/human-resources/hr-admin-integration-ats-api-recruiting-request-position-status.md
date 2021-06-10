---
title: Toborzási kérelem – pozíció állapota
description: Ez a témakör a Toborzási kérelem – pozíció állapota beállításkészletet írja le a Dynamics 365 Human Resources rendszerhez.
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
ms.openlocfilehash: e287ec4b9b78194b76ef3c993c6ce32f808e26f9
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/18/2021
ms.locfileid: "6051881"
---
# <a name="recruiting-request-position-status"></a><span data-ttu-id="dfb41-103">Toborzási kérelem – pozíció állapota</span><span class="sxs-lookup"><span data-stu-id="dfb41-103">Recruiting request position status</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="dfb41-104">Ez a témakör a Toborzási kérelem – pozíció állapota beállításkészletet írja le a Dynamics 365 Human Resources rendszerhez.</span><span class="sxs-lookup"><span data-stu-id="dfb41-104">This topic describes the Recruiting request position status option set for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="dfb41-105">Fizikai név: mshr_hcmrecruitingrequestpositionstatus</span><span class="sxs-lookup"><span data-stu-id="dfb41-105">Physical name: mshr_hcmrecruitingrequestpositionstatus</span></span>

<span data-ttu-id="dfb41-106">Ez a felsorolás biztosítja a beállításkészletet a RecruitingRequestPosition entitásnál toborzási kérelemként megadott beosztások állapotértékére.</span><span class="sxs-lookup"><span data-stu-id="dfb41-106">This enumeration provides the option set for the status values of each position a recruiting request in the RecruitingRequestPosition entity.</span></span>

| <span data-ttu-id="dfb41-107">Érték</span><span class="sxs-lookup"><span data-stu-id="dfb41-107">Value</span></span> | <span data-ttu-id="dfb41-108">Címke</span><span class="sxs-lookup"><span data-stu-id="dfb41-108">Label</span></span> | <span data-ttu-id="dfb41-109">Leírás</span><span class="sxs-lookup"><span data-stu-id="dfb41-109">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="dfb41-110">200000000</span><span class="sxs-lookup"><span data-stu-id="dfb41-110">200000000</span></span> | <span data-ttu-id="dfb41-111">Megnyitva</span><span class="sxs-lookup"><span data-stu-id="dfb41-111">Open</span></span> | <span data-ttu-id="dfb41-112">A toborzási kérelemben lévő beosztás meg van nyitva toborzásra.</span><span class="sxs-lookup"><span data-stu-id="dfb41-112">The position in the recruiting request is open for recruiting.</span></span> <span data-ttu-id="dfb41-113">Ez nem azt jelzi, hogy jelenleg nincs aktív beosztás-hozzárendelés a beosztásra vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="dfb41-113">This does not indicate that there is no currently active position assignment for the position.</span></span> <span data-ttu-id="dfb41-114">Megtörténhet, hogy a toborzás ideje alatt a beosztásban egy alkalmazott dolgozik.</span><span class="sxs-lookup"><span data-stu-id="dfb41-114">There may be an employee in the position at the time of recruiting.</span></span> <span data-ttu-id="dfb41-115">Kizárólag azt jelzi, hogy a beosztás toborzásra elérhető a toborzási kérelem keretében.</span><span class="sxs-lookup"><span data-stu-id="dfb41-115">It indicates only that the position is available for recruiting in the context of the recruiting request.</span></span> |
| <span data-ttu-id="dfb41-116">200000001</span><span class="sxs-lookup"><span data-stu-id="dfb41-116">200000001</span></span> | <span data-ttu-id="dfb41-117">Betöltve</span><span class="sxs-lookup"><span data-stu-id="dfb41-117">Filled</span></span> | <span data-ttu-id="dfb41-118">Egy dolgozót kiválasztottak a beosztáshoz való hozzárendelésre.</span><span class="sxs-lookup"><span data-stu-id="dfb41-118">A worker has been selected for assignment to the position.</span></span> |
| <span data-ttu-id="dfb41-119">200000002</span><span class="sxs-lookup"><span data-stu-id="dfb41-119">200000002</span></span> | <span data-ttu-id="dfb41-120">Érvénytelenítve</span><span class="sxs-lookup"><span data-stu-id="dfb41-120">Canceled</span></span> | <span data-ttu-id="dfb41-121">A beosztás toborzási kérelmét visszavonták.</span><span class="sxs-lookup"><span data-stu-id="dfb41-121">The request to recruit for this position has been canceled.</span></span> |

## <a name="see-also"></a><span data-ttu-id="dfb41-122">Lásd még</span><span class="sxs-lookup"><span data-stu-id="dfb41-122">See also</span></span>

[<span data-ttu-id="dfb41-123">Pályázó követésrendszer integrációs API bevezetése</span><span class="sxs-lookup"><span data-stu-id="dfb41-123">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="dfb41-124">Példa lekérdezésre Toborzási kérelemmel kapcsolatban</span><span class="sxs-lookup"><span data-stu-id="dfb41-124">Example query for Recruiting request</span></span>](hr-admin-integration-ats-api-recruiting-request-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]