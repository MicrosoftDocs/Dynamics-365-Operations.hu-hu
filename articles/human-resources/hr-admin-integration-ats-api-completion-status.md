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
ms.openlocfilehash: e9024e00b5d25117fd255084609c4f8db9284f32
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/05/2021
ms.locfileid: "5125689"
---
# <a name="completion-status"></a><span data-ttu-id="c0f11-103">Végrehajtás állapota</span><span class="sxs-lookup"><span data-stu-id="c0f11-103">Completion status</span></span>

<span data-ttu-id="c0f11-104">Ez a témakör bemutatja a Végrehajtás állapota beállításkészletet a Dynamics 365 Human Resources rendszerben.</span><span class="sxs-lookup"><span data-stu-id="c0f11-104">This topic describes the Completion status option set for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="c0f11-105">Fizikai név: mshr_hcmcompletionstatus</span><span class="sxs-lookup"><span data-stu-id="c0f11-105">Physical name: mshr_hcmcompletionstatus</span></span>

<span data-ttu-id="c0f11-106">Ez a felsorolás a jelöltek szűréséhez kapcsolódó állapotértékek beállításkészletét adja meg.</span><span class="sxs-lookup"><span data-stu-id="c0f11-106">This enumeration provides the option set of status values for candidate screenings.</span></span> 

| <span data-ttu-id="c0f11-107">Érték</span><span class="sxs-lookup"><span data-stu-id="c0f11-107">Value</span></span> | <span data-ttu-id="c0f11-108">Címke</span><span class="sxs-lookup"><span data-stu-id="c0f11-108">Label</span></span> | <span data-ttu-id="c0f11-109">Leírás</span><span class="sxs-lookup"><span data-stu-id="c0f11-109">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="c0f11-110">200000000</span><span class="sxs-lookup"><span data-stu-id="c0f11-110">200000000</span></span> | <span data-ttu-id="c0f11-111">Nincs kész</span><span class="sxs-lookup"><span data-stu-id="c0f11-111">Not Complete</span></span> | <span data-ttu-id="c0f11-112">A jelölt esetében még nem fejeződött be a szűrés.</span><span class="sxs-lookup"><span data-stu-id="c0f11-112">The candidate has not yet completed the screening.</span></span> |
| <span data-ttu-id="c0f11-113">200000001</span><span class="sxs-lookup"><span data-stu-id="c0f11-113">200000001</span></span> | <span data-ttu-id="c0f11-114">Megfelelt</span><span class="sxs-lookup"><span data-stu-id="c0f11-114">Pass</span></span> | <span data-ttu-id="c0f11-115">A jelölt átment a szűrésen.</span><span class="sxs-lookup"><span data-stu-id="c0f11-115">The candidate has passed the screening.</span></span> |
| <span data-ttu-id="c0f11-116">200000002</span><span class="sxs-lookup"><span data-stu-id="c0f11-116">200000002</span></span> | <span data-ttu-id="c0f11-117">Sikertelen</span><span class="sxs-lookup"><span data-stu-id="c0f11-117">Fail</span></span> | <span data-ttu-id="c0f11-118">A jelölt nem ment át a szűrésen.</span><span class="sxs-lookup"><span data-stu-id="c0f11-118">The candidate has failed the screening.</span></span> |

## <a name="see-also"></a><span data-ttu-id="c0f11-119">Lásd még</span><span class="sxs-lookup"><span data-stu-id="c0f11-119">See also</span></span>

[<span data-ttu-id="c0f11-120">Pályázó követésrendszer integrációs API bevezetése</span><span class="sxs-lookup"><span data-stu-id="c0f11-120">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="c0f11-121">Példa lekérdezésre a Felvenni kívánt jelölt esetében</span><span class="sxs-lookup"><span data-stu-id="c0f11-121">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)