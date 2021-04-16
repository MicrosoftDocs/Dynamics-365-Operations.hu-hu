---
title: Végzettség jóváírásának alapja
description: Ez a témakör bemutatja Végzettség jóváírásának alapja beállításkészletet a Dynamics 365 Human Resources rendszerben.
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
ms.openlocfilehash: 6092e1e8b53ba22cf4de31a8cb488d65714f5f41
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5798345"
---
# <a name="education-credit-basis"></a><span data-ttu-id="7b948-103">Végzettség jóváírásának alapja</span><span class="sxs-lookup"><span data-stu-id="7b948-103">Education credit basis</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="7b948-104">Ez a témakör bemutatja Végzettség jóváírásának alapja beállításkészletet a Dynamics 365 Human Resources rendszerben.</span><span class="sxs-lookup"><span data-stu-id="7b948-104">This topic describes the Education credit basis option set for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="7b948-105">Fizikai név: mshr_hcmeducationcreditbasis</span><span class="sxs-lookup"><span data-stu-id="7b948-105">Physical name: mshr_hcmeducationcreditbasis</span></span>

<span data-ttu-id="7b948-106">Ez a felsorolás a pályázók végzettségével kapcsolatos rekordja végzettség-jóváírási alapját adó értékek beállításkészletét adja meg.</span><span class="sxs-lookup"><span data-stu-id="7b948-106">This enumeration provides the option set of values for education credit basis of the candidate’s education record.</span></span>

| <span data-ttu-id="7b948-107">Érték</span><span class="sxs-lookup"><span data-stu-id="7b948-107">Value</span></span> | <span data-ttu-id="7b948-108">Címke</span><span class="sxs-lookup"><span data-stu-id="7b948-108">Label</span></span> | <span data-ttu-id="7b948-109">Leírás</span><span class="sxs-lookup"><span data-stu-id="7b948-109">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="7b948-110">200000000</span><span class="sxs-lookup"><span data-stu-id="7b948-110">200000000</span></span> | <span data-ttu-id="7b948-111">Üres</span><span class="sxs-lookup"><span data-stu-id="7b948-111">Blank</span></span> | <span data-ttu-id="7b948-112">Nincs kijelölve érték.</span><span class="sxs-lookup"><span data-stu-id="7b948-112">No value has been selected.</span></span> |
| <span data-ttu-id="7b948-113">200000001</span><span class="sxs-lookup"><span data-stu-id="7b948-113">200000001</span></span> | <span data-ttu-id="7b948-114">Félév</span><span class="sxs-lookup"><span data-stu-id="7b948-114">Semester</span></span> | <span data-ttu-id="7b948-115">Félév.</span><span class="sxs-lookup"><span data-stu-id="7b948-115">Semester.</span></span> |
| <span data-ttu-id="7b948-116">200000002</span><span class="sxs-lookup"><span data-stu-id="7b948-116">200000002</span></span> | <span data-ttu-id="7b948-117">Negyedév</span><span class="sxs-lookup"><span data-stu-id="7b948-117">Quarter</span></span> | <span data-ttu-id="7b948-118">Negyedév.</span><span class="sxs-lookup"><span data-stu-id="7b948-118">Quarter.</span></span> |
| <span data-ttu-id="7b948-119">200000003</span><span class="sxs-lookup"><span data-stu-id="7b948-119">200000003</span></span> | <span data-ttu-id="7b948-120">Trimeszter</span><span class="sxs-lookup"><span data-stu-id="7b948-120">Trimester</span></span> | <span data-ttu-id="7b948-121">Trimeszter.</span><span class="sxs-lookup"><span data-stu-id="7b948-121">Trimester.</span></span> |
| <span data-ttu-id="7b948-122">200000004</span><span class="sxs-lookup"><span data-stu-id="7b948-122">200000004</span></span> | <span data-ttu-id="7b948-123">Időszak</span><span class="sxs-lookup"><span data-stu-id="7b948-123">Term</span></span> | <span data-ttu-id="7b948-124">Időszak.</span><span class="sxs-lookup"><span data-stu-id="7b948-124">Term.</span></span> |
| <span data-ttu-id="7b948-125">200000005</span><span class="sxs-lookup"><span data-stu-id="7b948-125">200000005</span></span> | <span data-ttu-id="7b948-126">Egyéb</span><span class="sxs-lookup"><span data-stu-id="7b948-126">Other</span></span> | <span data-ttu-id="7b948-127">Egyéb.</span><span class="sxs-lookup"><span data-stu-id="7b948-127">Other.</span></span> |

## <a name="see-also"></a><span data-ttu-id="7b948-128">Lásd még</span><span class="sxs-lookup"><span data-stu-id="7b948-128">See also</span></span>

[<span data-ttu-id="7b948-129">Pályázó követésrendszer integrációs API bevezetése</span><span class="sxs-lookup"><span data-stu-id="7b948-129">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="7b948-130">Példa lekérdezésre a Felvenni kívánt jelölt esetében</span><span class="sxs-lookup"><span data-stu-id="7b948-130">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]