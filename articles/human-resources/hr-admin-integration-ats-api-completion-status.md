---
title: Végrehajtás állapota
description: Ez a témakör bemutatja a Végrehajtás állapota beállításkészletet a Dynamics 365 Human Resources rendszerben.
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
ms.openlocfilehash: 54ad5cc8f5f18d57b6713304cceb985acfdc93d1
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/18/2021
ms.locfileid: "6055364"
---
# <a name="completion-status"></a><span data-ttu-id="7ee16-103">Végrehajtás állapota</span><span class="sxs-lookup"><span data-stu-id="7ee16-103">Completion status</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="7ee16-104">Ez a témakör bemutatja a Végrehajtás állapota beállításkészletet a Dynamics 365 Human Resources rendszerben.</span><span class="sxs-lookup"><span data-stu-id="7ee16-104">This topic describes the Completion status option set for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="7ee16-105">Fizikai név: mshr_hcmcompletionstatus</span><span class="sxs-lookup"><span data-stu-id="7ee16-105">Physical name: mshr_hcmcompletionstatus</span></span>

<span data-ttu-id="7ee16-106">Ez a felsorolás a jelöltek szűréséhez kapcsolódó állapotértékek beállításkészletét adja meg.</span><span class="sxs-lookup"><span data-stu-id="7ee16-106">This enumeration provides the option set of status values for candidate screenings.</span></span> 

| <span data-ttu-id="7ee16-107">Érték</span><span class="sxs-lookup"><span data-stu-id="7ee16-107">Value</span></span> | <span data-ttu-id="7ee16-108">Címke</span><span class="sxs-lookup"><span data-stu-id="7ee16-108">Label</span></span> | <span data-ttu-id="7ee16-109">Leírás</span><span class="sxs-lookup"><span data-stu-id="7ee16-109">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="7ee16-110">200000000</span><span class="sxs-lookup"><span data-stu-id="7ee16-110">200000000</span></span> | <span data-ttu-id="7ee16-111">Nincs kész</span><span class="sxs-lookup"><span data-stu-id="7ee16-111">Not Complete</span></span> | <span data-ttu-id="7ee16-112">A jelölt esetében még nem fejeződött be a szűrés.</span><span class="sxs-lookup"><span data-stu-id="7ee16-112">The candidate has not yet completed the screening.</span></span> |
| <span data-ttu-id="7ee16-113">200000001</span><span class="sxs-lookup"><span data-stu-id="7ee16-113">200000001</span></span> | <span data-ttu-id="7ee16-114">Megfelelt</span><span class="sxs-lookup"><span data-stu-id="7ee16-114">Pass</span></span> | <span data-ttu-id="7ee16-115">A jelölt átment a szűrésen.</span><span class="sxs-lookup"><span data-stu-id="7ee16-115">The candidate has passed the screening.</span></span> |
| <span data-ttu-id="7ee16-116">200000002</span><span class="sxs-lookup"><span data-stu-id="7ee16-116">200000002</span></span> | <span data-ttu-id="7ee16-117">Sikertelen</span><span class="sxs-lookup"><span data-stu-id="7ee16-117">Fail</span></span> | <span data-ttu-id="7ee16-118">A jelölt nem ment át a szűrésen.</span><span class="sxs-lookup"><span data-stu-id="7ee16-118">The candidate has failed the screening.</span></span> |

## <a name="see-also"></a><span data-ttu-id="7ee16-119">Lásd még</span><span class="sxs-lookup"><span data-stu-id="7ee16-119">See also</span></span>

[<span data-ttu-id="7ee16-120">Pályázó követésrendszer integrációs API bevezetése</span><span class="sxs-lookup"><span data-stu-id="7ee16-120">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="7ee16-121">Példa lekérdezésre a Felvenni kívánt jelölt esetében</span><span class="sxs-lookup"><span data-stu-id="7ee16-121">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]