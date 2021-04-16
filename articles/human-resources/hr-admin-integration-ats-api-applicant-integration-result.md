---
title: Pályázó integrációs eredménye
description: Ez a témakör bemutatja a Pályázói integráció eredményének beállítását a Dynamics 365 Human Resources rendszerben.
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
ms.openlocfilehash: e8e41fe485cc70a668d4610ce6eabba5cd16ac86
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5795117"
---
# <a name="applicant-integration-result"></a><span data-ttu-id="4d9c0-103">Pályázó integrációs eredménye</span><span class="sxs-lookup"><span data-stu-id="4d9c0-103">Applicant integration result</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="4d9c0-104">Ez a témakör bemutatja a Pályázói integráció eredményének beállítását a Dynamics 365 Human Resources rendszerben.</span><span class="sxs-lookup"><span data-stu-id="4d9c0-104">This topic describes the Applicant integration result option set for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="4d9c0-105">Fizikai név: mshr_hcmapplicantintegrationresult</span><span class="sxs-lookup"><span data-stu-id="4d9c0-105">Physical name: mshr_hcmapplicantintegrationresult</span></span>

<span data-ttu-id="4d9c0-106">Ez a felsorolás a jelöltrekord állapotát biztosítja.</span><span class="sxs-lookup"><span data-stu-id="4d9c0-106">This enumeration provides status for a candidate record.</span></span>

| <span data-ttu-id="4d9c0-107">Érték</span><span class="sxs-lookup"><span data-stu-id="4d9c0-107">Value</span></span> | <span data-ttu-id="4d9c0-108">Címke</span><span class="sxs-lookup"><span data-stu-id="4d9c0-108">Label</span></span> | <span data-ttu-id="4d9c0-109">Leírás</span><span class="sxs-lookup"><span data-stu-id="4d9c0-109">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="4d9c0-110">200000000</span><span class="sxs-lookup"><span data-stu-id="4d9c0-110">200000000</span></span> | <span data-ttu-id="4d9c0-111">Nincs feldolgozva</span><span class="sxs-lookup"><span data-stu-id="4d9c0-111">Not processed</span></span> | <span data-ttu-id="4d9c0-112">A jelölt még mindig megfontolás alatt áll.</span><span class="sxs-lookup"><span data-stu-id="4d9c0-112">Candidate is still under consideration.</span></span> |
| <span data-ttu-id="4d9c0-113">200000001</span><span class="sxs-lookup"><span data-stu-id="4d9c0-113">200000001</span></span> | <span data-ttu-id="4d9c0-114">Felvéve</span><span class="sxs-lookup"><span data-stu-id="4d9c0-114">Hired</span></span> | <span data-ttu-id="4d9c0-115">A jelöltet felvették.</span><span class="sxs-lookup"><span data-stu-id="4d9c0-115">The candidate has been hired.</span></span> |
| <span data-ttu-id="4d9c0-116">200000002</span><span class="sxs-lookup"><span data-stu-id="4d9c0-116">200000002</span></span> | <span data-ttu-id="4d9c0-117">Nincs felvéve</span><span class="sxs-lookup"><span data-stu-id="4d9c0-117">Not hired</span></span> | <span data-ttu-id="4d9c0-118">Úgy döntöttek, hogy nem veszik fel a jelöltet.</span><span class="sxs-lookup"><span data-stu-id="4d9c0-118">Decision was made to not hire the candidate.</span></span> |
| <span data-ttu-id="4d9c0-119">200000003</span><span class="sxs-lookup"><span data-stu-id="4d9c0-119">200000003</span></span> | <span data-ttu-id="4d9c0-120">Elutasított</span><span class="sxs-lookup"><span data-stu-id="4d9c0-120">Dismissed</span></span> | <span data-ttu-id="4d9c0-121">A jelöltet kivették a megfontolandók köréből.</span><span class="sxs-lookup"><span data-stu-id="4d9c0-121">The candidate was dismissed from consideration.</span></span> |

## <a name="see-also"></a><span data-ttu-id="4d9c0-122">Lásd még</span><span class="sxs-lookup"><span data-stu-id="4d9c0-122">See also</span></span>

[<span data-ttu-id="4d9c0-123">Pályázó követésrendszer integrációs API bevezetése</span><span class="sxs-lookup"><span data-stu-id="4d9c0-123">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="4d9c0-124">Példa lekérdezésre a Felvenni kívánt jelölt esetében</span><span class="sxs-lookup"><span data-stu-id="4d9c0-124">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]