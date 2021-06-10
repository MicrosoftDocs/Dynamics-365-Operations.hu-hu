---
title: Pályázó integrációs eredménye
description: Ez a témakör bemutatja a Pályázói integráció eredményének beállítását a Dynamics 365 Human Resources rendszerben.
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
ms.openlocfilehash: 8bef974abff18d7c07ecd679b7e01b31ea1459c4
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/18/2021
ms.locfileid: "6053899"
---
# <a name="applicant-integration-result"></a><span data-ttu-id="0e407-103">Pályázó integrációs eredménye</span><span class="sxs-lookup"><span data-stu-id="0e407-103">Applicant integration result</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="0e407-104">Ez a témakör bemutatja a Pályázói integráció eredményének beállítását a Dynamics 365 Human Resources rendszerben.</span><span class="sxs-lookup"><span data-stu-id="0e407-104">This topic describes the Applicant integration result option set for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="0e407-105">Fizikai név: mshr_hcmapplicantintegrationresult</span><span class="sxs-lookup"><span data-stu-id="0e407-105">Physical name: mshr_hcmapplicantintegrationresult</span></span>

<span data-ttu-id="0e407-106">Ez a felsorolás a jelöltrekord állapotát biztosítja.</span><span class="sxs-lookup"><span data-stu-id="0e407-106">This enumeration provides status for a candidate record.</span></span>

| <span data-ttu-id="0e407-107">Érték</span><span class="sxs-lookup"><span data-stu-id="0e407-107">Value</span></span> | <span data-ttu-id="0e407-108">Címke</span><span class="sxs-lookup"><span data-stu-id="0e407-108">Label</span></span> | <span data-ttu-id="0e407-109">Leírás</span><span class="sxs-lookup"><span data-stu-id="0e407-109">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="0e407-110">200000000</span><span class="sxs-lookup"><span data-stu-id="0e407-110">200000000</span></span> | <span data-ttu-id="0e407-111">Nincs feldolgozva</span><span class="sxs-lookup"><span data-stu-id="0e407-111">Not processed</span></span> | <span data-ttu-id="0e407-112">A jelölt még mindig megfontolás alatt áll.</span><span class="sxs-lookup"><span data-stu-id="0e407-112">Candidate is still under consideration.</span></span> |
| <span data-ttu-id="0e407-113">200000001</span><span class="sxs-lookup"><span data-stu-id="0e407-113">200000001</span></span> | <span data-ttu-id="0e407-114">Felvéve</span><span class="sxs-lookup"><span data-stu-id="0e407-114">Hired</span></span> | <span data-ttu-id="0e407-115">A jelöltet felvették.</span><span class="sxs-lookup"><span data-stu-id="0e407-115">The candidate has been hired.</span></span> |
| <span data-ttu-id="0e407-116">200000002</span><span class="sxs-lookup"><span data-stu-id="0e407-116">200000002</span></span> | <span data-ttu-id="0e407-117">Nincs felvéve</span><span class="sxs-lookup"><span data-stu-id="0e407-117">Not hired</span></span> | <span data-ttu-id="0e407-118">Úgy döntöttek, hogy nem veszik fel a jelöltet.</span><span class="sxs-lookup"><span data-stu-id="0e407-118">Decision was made to not hire the candidate.</span></span> |
| <span data-ttu-id="0e407-119">200000003</span><span class="sxs-lookup"><span data-stu-id="0e407-119">200000003</span></span> | <span data-ttu-id="0e407-120">Elutasított</span><span class="sxs-lookup"><span data-stu-id="0e407-120">Dismissed</span></span> | <span data-ttu-id="0e407-121">A jelöltet kivették a megfontolandók köréből.</span><span class="sxs-lookup"><span data-stu-id="0e407-121">The candidate was dismissed from consideration.</span></span> |

## <a name="see-also"></a><span data-ttu-id="0e407-122">Lásd még</span><span class="sxs-lookup"><span data-stu-id="0e407-122">See also</span></span>

[<span data-ttu-id="0e407-123">Pályázó követésrendszer integrációs API bevezetése</span><span class="sxs-lookup"><span data-stu-id="0e407-123">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="0e407-124">Példa lekérdezésre a Felvenni kívánt jelölt esetében</span><span class="sxs-lookup"><span data-stu-id="0e407-124">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]