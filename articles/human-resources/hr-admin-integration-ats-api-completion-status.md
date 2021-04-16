---
title: Végrehajtás állapota
description: Ez a témakör bemutatja a Végrehajtás állapota beállításkészletet a Dynamics 365 Human Resources rendszerben.
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
ms.openlocfilehash: f1b0c61ac9d9dc611d2a4700a1a004e3d15b4445
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5798369"
---
# <a name="completion-status"></a><span data-ttu-id="7c9cc-103">Végrehajtás állapota</span><span class="sxs-lookup"><span data-stu-id="7c9cc-103">Completion status</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="7c9cc-104">Ez a témakör bemutatja a Végrehajtás állapota beállításkészletet a Dynamics 365 Human Resources rendszerben.</span><span class="sxs-lookup"><span data-stu-id="7c9cc-104">This topic describes the Completion status option set for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="7c9cc-105">Fizikai név: mshr_hcmcompletionstatus</span><span class="sxs-lookup"><span data-stu-id="7c9cc-105">Physical name: mshr_hcmcompletionstatus</span></span>

<span data-ttu-id="7c9cc-106">Ez a felsorolás a jelöltek szűréséhez kapcsolódó állapotértékek beállításkészletét adja meg.</span><span class="sxs-lookup"><span data-stu-id="7c9cc-106">This enumeration provides the option set of status values for candidate screenings.</span></span> 

| <span data-ttu-id="7c9cc-107">Érték</span><span class="sxs-lookup"><span data-stu-id="7c9cc-107">Value</span></span> | <span data-ttu-id="7c9cc-108">Címke</span><span class="sxs-lookup"><span data-stu-id="7c9cc-108">Label</span></span> | <span data-ttu-id="7c9cc-109">Leírás</span><span class="sxs-lookup"><span data-stu-id="7c9cc-109">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="7c9cc-110">200000000</span><span class="sxs-lookup"><span data-stu-id="7c9cc-110">200000000</span></span> | <span data-ttu-id="7c9cc-111">Nincs kész</span><span class="sxs-lookup"><span data-stu-id="7c9cc-111">Not Complete</span></span> | <span data-ttu-id="7c9cc-112">A jelölt esetében még nem fejeződött be a szűrés.</span><span class="sxs-lookup"><span data-stu-id="7c9cc-112">The candidate has not yet completed the screening.</span></span> |
| <span data-ttu-id="7c9cc-113">200000001</span><span class="sxs-lookup"><span data-stu-id="7c9cc-113">200000001</span></span> | <span data-ttu-id="7c9cc-114">Megfelelt</span><span class="sxs-lookup"><span data-stu-id="7c9cc-114">Pass</span></span> | <span data-ttu-id="7c9cc-115">A jelölt átment a szűrésen.</span><span class="sxs-lookup"><span data-stu-id="7c9cc-115">The candidate has passed the screening.</span></span> |
| <span data-ttu-id="7c9cc-116">200000002</span><span class="sxs-lookup"><span data-stu-id="7c9cc-116">200000002</span></span> | <span data-ttu-id="7c9cc-117">Sikertelen</span><span class="sxs-lookup"><span data-stu-id="7c9cc-117">Fail</span></span> | <span data-ttu-id="7c9cc-118">A jelölt nem ment át a szűrésen.</span><span class="sxs-lookup"><span data-stu-id="7c9cc-118">The candidate has failed the screening.</span></span> |

## <a name="see-also"></a><span data-ttu-id="7c9cc-119">Lásd még</span><span class="sxs-lookup"><span data-stu-id="7c9cc-119">See also</span></span>

[<span data-ttu-id="7c9cc-120">Pályázó követésrendszer integrációs API bevezetése</span><span class="sxs-lookup"><span data-stu-id="7c9cc-120">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="7c9cc-121">Példa lekérdezésre a Felvenni kívánt jelölt esetében</span><span class="sxs-lookup"><span data-stu-id="7c9cc-121">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]