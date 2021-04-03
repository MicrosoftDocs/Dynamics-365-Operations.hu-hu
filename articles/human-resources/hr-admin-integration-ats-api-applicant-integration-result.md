---
title: Pályázó integrációs eredménye
description: Ez a témakör bemutatja a Pályázói integráció eredményének beállítását a Dynamics 365 Human Resources rendszerben.
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
ms.openlocfilehash: dd25eca9cccf46ec4e4bb2a1d948ca98985e73e4
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/17/2021
ms.locfileid: "5467553"
---
# <a name="applicant-integration-result"></a><span data-ttu-id="8ea75-103">Pályázó integrációs eredménye</span><span class="sxs-lookup"><span data-stu-id="8ea75-103">Applicant integration result</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="8ea75-104">Ez a témakör bemutatja a Pályázói integráció eredményének beállítását a Dynamics 365 Human Resources rendszerben.</span><span class="sxs-lookup"><span data-stu-id="8ea75-104">This topic describes the Applicant integration result option set for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="8ea75-105">Fizikai név: mshr_hcmapplicantintegrationresult</span><span class="sxs-lookup"><span data-stu-id="8ea75-105">Physical name: mshr_hcmapplicantintegrationresult</span></span>

<span data-ttu-id="8ea75-106">Ez a felsorolás a jelöltrekord állapotát biztosítja.</span><span class="sxs-lookup"><span data-stu-id="8ea75-106">This enumeration provides status for a candidate record.</span></span>

| <span data-ttu-id="8ea75-107">Érték</span><span class="sxs-lookup"><span data-stu-id="8ea75-107">Value</span></span> | <span data-ttu-id="8ea75-108">Címke</span><span class="sxs-lookup"><span data-stu-id="8ea75-108">Label</span></span> | <span data-ttu-id="8ea75-109">Leírás</span><span class="sxs-lookup"><span data-stu-id="8ea75-109">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="8ea75-110">200000000</span><span class="sxs-lookup"><span data-stu-id="8ea75-110">200000000</span></span> | <span data-ttu-id="8ea75-111">Nincs feldolgozva</span><span class="sxs-lookup"><span data-stu-id="8ea75-111">Not processed</span></span> | <span data-ttu-id="8ea75-112">A jelölt még mindig megfontolás alatt áll.</span><span class="sxs-lookup"><span data-stu-id="8ea75-112">Candidate is still under consideration.</span></span> |
| <span data-ttu-id="8ea75-113">200000001</span><span class="sxs-lookup"><span data-stu-id="8ea75-113">200000001</span></span> | <span data-ttu-id="8ea75-114">Felvéve</span><span class="sxs-lookup"><span data-stu-id="8ea75-114">Hired</span></span> | <span data-ttu-id="8ea75-115">A jelöltet felvették.</span><span class="sxs-lookup"><span data-stu-id="8ea75-115">The candidate has been hired.</span></span> |
| <span data-ttu-id="8ea75-116">200000002</span><span class="sxs-lookup"><span data-stu-id="8ea75-116">200000002</span></span> | <span data-ttu-id="8ea75-117">Nincs felvéve</span><span class="sxs-lookup"><span data-stu-id="8ea75-117">Not hired</span></span> | <span data-ttu-id="8ea75-118">Úgy döntöttek, hogy nem veszik fel a jelöltet.</span><span class="sxs-lookup"><span data-stu-id="8ea75-118">Decision was made to not hire the candidate.</span></span> |
| <span data-ttu-id="8ea75-119">200000003</span><span class="sxs-lookup"><span data-stu-id="8ea75-119">200000003</span></span> | <span data-ttu-id="8ea75-120">Elutasított</span><span class="sxs-lookup"><span data-stu-id="8ea75-120">Dismissed</span></span> | <span data-ttu-id="8ea75-121">A jelöltet kivették a megfontolandók köréből.</span><span class="sxs-lookup"><span data-stu-id="8ea75-121">The candidate was dismissed from consideration.</span></span> |

## <a name="see-also"></a><span data-ttu-id="8ea75-122">Lásd még</span><span class="sxs-lookup"><span data-stu-id="8ea75-122">See also</span></span>

[<span data-ttu-id="8ea75-123">Pályázó követésrendszer integrációs API bevezetése</span><span class="sxs-lookup"><span data-stu-id="8ea75-123">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="8ea75-124">Példa lekérdezésre a Felvenni kívánt jelölt esetében</span><span class="sxs-lookup"><span data-stu-id="8ea75-124">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]