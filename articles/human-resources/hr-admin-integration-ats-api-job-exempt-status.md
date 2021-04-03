---
title: Munka mentességi állapota
description: Ez a témakör bemutatja Munka mentességi állapota beállításkészletet a Dynamics 365 Human Resources rendszerben.
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
ms.openlocfilehash: 1f211002468384227acb2343ed6cbc6ae2a215d1
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/17/2021
ms.locfileid: "5464452"
---
# <a name="job-exempt-status"></a><span data-ttu-id="6226a-103">Munka mentességi állapota</span><span class="sxs-lookup"><span data-stu-id="6226a-103">Job exempt status</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="6226a-104">Ez a témakör bemutatja Munka mentességi állapota beállításkészletet a Dynamics 365 Human Resources rendszerben.</span><span class="sxs-lookup"><span data-stu-id="6226a-104">This topic describes the Job exempt status option set for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="6226a-105">Fizikai név: cdm_jobexemptstatus</span><span class="sxs-lookup"><span data-stu-id="6226a-105">Physical name: cdm_jobexemptstatus</span></span>

<span data-ttu-id="6226a-106">Ez a felsorolás bemutatja az FLSA munka mentességi állapotértékei beállításkészletet.</span><span class="sxs-lookup"><span data-stu-id="6226a-106">This enumeration specifies the option set for FLSA job exempt status values.</span></span> <span data-ttu-id="6226a-107">Ez a meglévő cdm_jobexemptstatus beállításkészletben található.</span><span class="sxs-lookup"><span data-stu-id="6226a-107">This is provided in the existing cdm_jobexemptstatus option set.</span></span>

| <span data-ttu-id="6226a-108">Érték</span><span class="sxs-lookup"><span data-stu-id="6226a-108">Value</span></span> | <span data-ttu-id="6226a-109">Címke</span><span class="sxs-lookup"><span data-stu-id="6226a-109">Label</span></span> | <span data-ttu-id="6226a-110">Leírás</span><span class="sxs-lookup"><span data-stu-id="6226a-110">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="6226a-111">200000000</span><span class="sxs-lookup"><span data-stu-id="6226a-111">200000000</span></span> | <span data-ttu-id="6226a-112">Mentes</span><span class="sxs-lookup"><span data-stu-id="6226a-112">Exempt</span></span> | <span data-ttu-id="6226a-113">A feladat mentességi állapottal rendelkezik az FLSA-irányelvek alapján.</span><span class="sxs-lookup"><span data-stu-id="6226a-113">The job has an exempt status based on FLSA guidelines.</span></span> |
| <span data-ttu-id="6226a-114">200000001</span><span class="sxs-lookup"><span data-stu-id="6226a-114">200000001</span></span> | <span data-ttu-id="6226a-115">NonExempt</span><span class="sxs-lookup"><span data-stu-id="6226a-115">NonExempt</span></span> | <span data-ttu-id="6226a-116">A feladat nem rendelkezik mentességi állapottal rendelkezik az FLSA-irányelvek alapján.</span><span class="sxs-lookup"><span data-stu-id="6226a-116">The job has a non-exempt status based on FLSA guidelines.</span></span> |
| <span data-ttu-id="6226a-117">200000002</span><span class="sxs-lookup"><span data-stu-id="6226a-117">200000002</span></span> | <span data-ttu-id="6226a-118">Nem érvényes rá</span><span class="sxs-lookup"><span data-stu-id="6226a-118">Does Not Apply</span></span> | <span data-ttu-id="6226a-119">Az FLSA állapot-irányelvek nem vonatkoznak a feladatra.</span><span class="sxs-lookup"><span data-stu-id="6226a-119">FLSA status guidelines do not apply to the job.</span></span> |

## <a name="see-also"></a><span data-ttu-id="6226a-120">Lásd még</span><span class="sxs-lookup"><span data-stu-id="6226a-120">See also</span></span>

[<span data-ttu-id="6226a-121">Pályázó követésrendszer integrációs API bevezetése</span><span class="sxs-lookup"><span data-stu-id="6226a-121">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="6226a-122">Példa lekérdezésre Toborzási kérelemmel kapcsolatban</span><span class="sxs-lookup"><span data-stu-id="6226a-122">Example query for Recruiting request</span></span>](hr-admin-integration-ats-api-recruiting-request-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]