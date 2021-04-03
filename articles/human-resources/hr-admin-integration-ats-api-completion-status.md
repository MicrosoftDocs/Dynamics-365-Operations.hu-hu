---
title: Végrehajtás állapota
description: Ez a témakör bemutatja a Végrehajtás állapota beállításkészletet a Dynamics 365 Human Resources rendszerben.
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
ms.openlocfilehash: d8ea90785f303301a21a4ac799578b08cabd0e3d
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/17/2021
ms.locfileid: "5468203"
---
# <a name="completion-status"></a><span data-ttu-id="57759-103">Végrehajtás állapota</span><span class="sxs-lookup"><span data-stu-id="57759-103">Completion status</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="57759-104">Ez a témakör bemutatja a Végrehajtás állapota beállításkészletet a Dynamics 365 Human Resources rendszerben.</span><span class="sxs-lookup"><span data-stu-id="57759-104">This topic describes the Completion status option set for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="57759-105">Fizikai név: mshr_hcmcompletionstatus</span><span class="sxs-lookup"><span data-stu-id="57759-105">Physical name: mshr_hcmcompletionstatus</span></span>

<span data-ttu-id="57759-106">Ez a felsorolás a jelöltek szűréséhez kapcsolódó állapotértékek beállításkészletét adja meg.</span><span class="sxs-lookup"><span data-stu-id="57759-106">This enumeration provides the option set of status values for candidate screenings.</span></span> 

| <span data-ttu-id="57759-107">Érték</span><span class="sxs-lookup"><span data-stu-id="57759-107">Value</span></span> | <span data-ttu-id="57759-108">Címke</span><span class="sxs-lookup"><span data-stu-id="57759-108">Label</span></span> | <span data-ttu-id="57759-109">Leírás</span><span class="sxs-lookup"><span data-stu-id="57759-109">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="57759-110">200000000</span><span class="sxs-lookup"><span data-stu-id="57759-110">200000000</span></span> | <span data-ttu-id="57759-111">Nincs kész</span><span class="sxs-lookup"><span data-stu-id="57759-111">Not Complete</span></span> | <span data-ttu-id="57759-112">A jelölt esetében még nem fejeződött be a szűrés.</span><span class="sxs-lookup"><span data-stu-id="57759-112">The candidate has not yet completed the screening.</span></span> |
| <span data-ttu-id="57759-113">200000001</span><span class="sxs-lookup"><span data-stu-id="57759-113">200000001</span></span> | <span data-ttu-id="57759-114">Megfelelt</span><span class="sxs-lookup"><span data-stu-id="57759-114">Pass</span></span> | <span data-ttu-id="57759-115">A jelölt átment a szűrésen.</span><span class="sxs-lookup"><span data-stu-id="57759-115">The candidate has passed the screening.</span></span> |
| <span data-ttu-id="57759-116">200000002</span><span class="sxs-lookup"><span data-stu-id="57759-116">200000002</span></span> | <span data-ttu-id="57759-117">Sikertelen</span><span class="sxs-lookup"><span data-stu-id="57759-117">Fail</span></span> | <span data-ttu-id="57759-118">A jelölt nem ment át a szűrésen.</span><span class="sxs-lookup"><span data-stu-id="57759-118">The candidate has failed the screening.</span></span> |

## <a name="see-also"></a><span data-ttu-id="57759-119">Lásd még</span><span class="sxs-lookup"><span data-stu-id="57759-119">See also</span></span>

[<span data-ttu-id="57759-120">Pályázó követésrendszer integrációs API bevezetése</span><span class="sxs-lookup"><span data-stu-id="57759-120">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="57759-121">Példa lekérdezésre a Felvenni kívánt jelölt esetében</span><span class="sxs-lookup"><span data-stu-id="57759-121">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]