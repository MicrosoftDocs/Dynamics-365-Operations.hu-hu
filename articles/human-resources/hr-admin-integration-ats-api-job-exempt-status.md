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
ms.openlocfilehash: 0cd6ffc01793c8ff12e36175c7c9feaf8a4b3cdf
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/05/2021
ms.locfileid: "5125569"
---
# <a name="job-exempt-status"></a><span data-ttu-id="3e936-103">Munka mentességi állapota</span><span class="sxs-lookup"><span data-stu-id="3e936-103">Job exempt status</span></span>

<span data-ttu-id="3e936-104">Ez a témakör bemutatja Munka mentességi állapota beállításkészletet a Dynamics 365 Human Resources rendszerben.</span><span class="sxs-lookup"><span data-stu-id="3e936-104">This topic describes the Job exempt status option set for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="3e936-105">Fizikai név: cdm_jobexemptstatus</span><span class="sxs-lookup"><span data-stu-id="3e936-105">Physical name: cdm_jobexemptstatus</span></span>

<span data-ttu-id="3e936-106">Ez a felsorolás bemutatja az FLSA munka mentességi állapotértékei beállításkészletet.</span><span class="sxs-lookup"><span data-stu-id="3e936-106">This enumeration specifies the option set for FLSA job exempt status values.</span></span> <span data-ttu-id="3e936-107">Ez a meglévő cdm_jobexemptstatus beállításkészletben található.</span><span class="sxs-lookup"><span data-stu-id="3e936-107">This is provided in the existing cdm_jobexemptstatus option set.</span></span>

| <span data-ttu-id="3e936-108">Érték</span><span class="sxs-lookup"><span data-stu-id="3e936-108">Value</span></span> | <span data-ttu-id="3e936-109">Címke</span><span class="sxs-lookup"><span data-stu-id="3e936-109">Label</span></span> | <span data-ttu-id="3e936-110">Leírás</span><span class="sxs-lookup"><span data-stu-id="3e936-110">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="3e936-111">200000000</span><span class="sxs-lookup"><span data-stu-id="3e936-111">200000000</span></span> | <span data-ttu-id="3e936-112">Mentes</span><span class="sxs-lookup"><span data-stu-id="3e936-112">Exempt</span></span> | <span data-ttu-id="3e936-113">A feladat mentességi állapottal rendelkezik az FLSA-irányelvek alapján.</span><span class="sxs-lookup"><span data-stu-id="3e936-113">The job has an exempt status based on FLSA guidelines.</span></span> |
| <span data-ttu-id="3e936-114">200000001</span><span class="sxs-lookup"><span data-stu-id="3e936-114">200000001</span></span> | <span data-ttu-id="3e936-115">NonExempt</span><span class="sxs-lookup"><span data-stu-id="3e936-115">NonExempt</span></span> | <span data-ttu-id="3e936-116">A feladat nem rendelkezik mentességi állapottal rendelkezik az FLSA-irányelvek alapján.</span><span class="sxs-lookup"><span data-stu-id="3e936-116">The job has a non-exempt status based on FLSA guidelines.</span></span> |
| <span data-ttu-id="3e936-117">200000002</span><span class="sxs-lookup"><span data-stu-id="3e936-117">200000002</span></span> | <span data-ttu-id="3e936-118">Nem érvényes rá</span><span class="sxs-lookup"><span data-stu-id="3e936-118">Does Not Apply</span></span> | <span data-ttu-id="3e936-119">Az FLSA állapot-irányelvek nem vonatkoznak a feladatra.</span><span class="sxs-lookup"><span data-stu-id="3e936-119">FLSA status guidelines do not apply to the job.</span></span> |

## <a name="see-also"></a><span data-ttu-id="3e936-120">Lásd még</span><span class="sxs-lookup"><span data-stu-id="3e936-120">See also</span></span>

[<span data-ttu-id="3e936-121">Pályázó követésrendszer integrációs API bevezetése</span><span class="sxs-lookup"><span data-stu-id="3e936-121">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="3e936-122">Példa lekérdezésre Toborzási kérelemmel kapcsolatban</span><span class="sxs-lookup"><span data-stu-id="3e936-122">Example query for Recruiting request</span></span>](hr-admin-integration-ats-api-recruiting-request-example-query.md)
