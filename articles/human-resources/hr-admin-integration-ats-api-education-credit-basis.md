---
title: Végzettség jóváírásának alapja
description: Ez a témakör bemutatja Végzettség jóváírásának alapja beállításkészletet a Dynamics 365 Human Resources rendszerben.
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
ms.openlocfilehash: 675d1891b663ccb7569efe7bbff76431123e8298
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/18/2021
ms.locfileid: "6055316"
---
# <a name="education-credit-basis"></a><span data-ttu-id="97c93-103">Végzettség jóváírásának alapja</span><span class="sxs-lookup"><span data-stu-id="97c93-103">Education credit basis</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="97c93-104">Ez a témakör bemutatja Végzettség jóváírásának alapja beállításkészletet a Dynamics 365 Human Resources rendszerben.</span><span class="sxs-lookup"><span data-stu-id="97c93-104">This topic describes the Education credit basis option set for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="97c93-105">Fizikai név: mshr_hcmeducationcreditbasis</span><span class="sxs-lookup"><span data-stu-id="97c93-105">Physical name: mshr_hcmeducationcreditbasis</span></span>

<span data-ttu-id="97c93-106">Ez a felsorolás a pályázók végzettségével kapcsolatos rekordja végzettség-jóváírási alapját adó értékek beállításkészletét adja meg.</span><span class="sxs-lookup"><span data-stu-id="97c93-106">This enumeration provides the option set of values for education credit basis of the candidate’s education record.</span></span>

| <span data-ttu-id="97c93-107">Érték</span><span class="sxs-lookup"><span data-stu-id="97c93-107">Value</span></span> | <span data-ttu-id="97c93-108">Címke</span><span class="sxs-lookup"><span data-stu-id="97c93-108">Label</span></span> | <span data-ttu-id="97c93-109">Leírás</span><span class="sxs-lookup"><span data-stu-id="97c93-109">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="97c93-110">200000000</span><span class="sxs-lookup"><span data-stu-id="97c93-110">200000000</span></span> | <span data-ttu-id="97c93-111">Üres</span><span class="sxs-lookup"><span data-stu-id="97c93-111">Blank</span></span> | <span data-ttu-id="97c93-112">Nincs kijelölve érték.</span><span class="sxs-lookup"><span data-stu-id="97c93-112">No value has been selected.</span></span> |
| <span data-ttu-id="97c93-113">200000001</span><span class="sxs-lookup"><span data-stu-id="97c93-113">200000001</span></span> | <span data-ttu-id="97c93-114">Félév</span><span class="sxs-lookup"><span data-stu-id="97c93-114">Semester</span></span> | <span data-ttu-id="97c93-115">Félév.</span><span class="sxs-lookup"><span data-stu-id="97c93-115">Semester.</span></span> |
| <span data-ttu-id="97c93-116">200000002</span><span class="sxs-lookup"><span data-stu-id="97c93-116">200000002</span></span> | <span data-ttu-id="97c93-117">Negyedév</span><span class="sxs-lookup"><span data-stu-id="97c93-117">Quarter</span></span> | <span data-ttu-id="97c93-118">Negyedév.</span><span class="sxs-lookup"><span data-stu-id="97c93-118">Quarter.</span></span> |
| <span data-ttu-id="97c93-119">200000003</span><span class="sxs-lookup"><span data-stu-id="97c93-119">200000003</span></span> | <span data-ttu-id="97c93-120">Trimeszter</span><span class="sxs-lookup"><span data-stu-id="97c93-120">Trimester</span></span> | <span data-ttu-id="97c93-121">Trimeszter.</span><span class="sxs-lookup"><span data-stu-id="97c93-121">Trimester.</span></span> |
| <span data-ttu-id="97c93-122">200000004</span><span class="sxs-lookup"><span data-stu-id="97c93-122">200000004</span></span> | <span data-ttu-id="97c93-123">Időszak</span><span class="sxs-lookup"><span data-stu-id="97c93-123">Term</span></span> | <span data-ttu-id="97c93-124">Időszak.</span><span class="sxs-lookup"><span data-stu-id="97c93-124">Term.</span></span> |
| <span data-ttu-id="97c93-125">200000005</span><span class="sxs-lookup"><span data-stu-id="97c93-125">200000005</span></span> | <span data-ttu-id="97c93-126">Egyéb</span><span class="sxs-lookup"><span data-stu-id="97c93-126">Other</span></span> | <span data-ttu-id="97c93-127">Egyéb.</span><span class="sxs-lookup"><span data-stu-id="97c93-127">Other.</span></span> |

## <a name="see-also"></a><span data-ttu-id="97c93-128">Lásd még</span><span class="sxs-lookup"><span data-stu-id="97c93-128">See also</span></span>

[<span data-ttu-id="97c93-129">Pályázó követésrendszer integrációs API bevezetése</span><span class="sxs-lookup"><span data-stu-id="97c93-129">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="97c93-130">Példa lekérdezésre a Felvenni kívánt jelölt esetében</span><span class="sxs-lookup"><span data-stu-id="97c93-130">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]