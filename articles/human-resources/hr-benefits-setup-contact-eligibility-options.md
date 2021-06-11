---
title: A személyes kapcsolattartó jogosultsági beállításainak konfigurálása
description: A Microsoft Dynamics 365 Human Resources rendszerben konfigurálhatja a személyes kapcsolattartók jogosultsági beállításait. A személyes kapcsolattartók lehetnek kedvezményezettek vagy függő felek.
author: andreabichsel
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d85677973f67f0c68de6c5ede62c142524939833
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/18/2021
ms.locfileid: "6054404"
---
# <a name="configure-personal-contact-eligibility-options"></a><span data-ttu-id="d3ed8-104">A személyes kapcsolattartó jogosultsági beállításainak konfigurálása</span><span class="sxs-lookup"><span data-stu-id="d3ed8-104">Configure personal contact eligibility options</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="d3ed8-105">Ez a cikk bemutatja, hogyan lehet konfigurálni a Microsoft Dynamics 365 Human Resources rendszer juttatásaiban használt személyes kapcsolattartók típusait.</span><span class="sxs-lookup"><span data-stu-id="d3ed8-105">This article shows you how to configure types of personal contacts to use in benefits in Microsoft Dynamics 365 Human Resources.</span></span> <span data-ttu-id="d3ed8-106">A személyes kapcsolattartók lehetnek kedvezményezettek vagy függő felek.</span><span class="sxs-lookup"><span data-stu-id="d3ed8-106">Personal contacts can be beneficiaries or dependents.</span></span> 

1. <span data-ttu-id="d3ed8-107">A **Juttatások kezelése** munkaterület **Beállítás** részén válassza a **Személyes kapcsolattartó jogosultsági beállításai** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d3ed8-107">In the **Benefits management** workspace, under **Setup**, select **Personal contact eligibility options**.</span></span>

2. <span data-ttu-id="d3ed8-108">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d3ed8-108">Select **New**.</span></span>

3. <span data-ttu-id="d3ed8-109">Adjon meg értékeket a következő mezőkben:</span><span class="sxs-lookup"><span data-stu-id="d3ed8-109">Specify values for the following fields:</span></span>

   | <span data-ttu-id="d3ed8-110">Mező</span><span class="sxs-lookup"><span data-stu-id="d3ed8-110">Field</span></span> | <span data-ttu-id="d3ed8-111">Leírás</span><span class="sxs-lookup"><span data-stu-id="d3ed8-111">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="d3ed8-112">**Jogosultsági beállítás**</span><span class="sxs-lookup"><span data-stu-id="d3ed8-112">**Eligibility option**</span></span> | <span data-ttu-id="d3ed8-113">Az egyedi jogosultsági beállítást azonosító egyedi név vagy kód.</span><span class="sxs-lookup"><span data-stu-id="d3ed8-113">A unique eligibility option name or code to identify the eligibility option.</span></span> |
   | <span data-ttu-id="d3ed8-114">**Leírás**</span><span class="sxs-lookup"><span data-stu-id="d3ed8-114">**Description**</span></span> | <span data-ttu-id="d3ed8-115">A jogosultsági beállítás rövid leírása.</span><span class="sxs-lookup"><span data-stu-id="d3ed8-115">A brief description of the eligibility option.</span></span> |
   | <span data-ttu-id="d3ed8-116">**Kapcsolattartói jogosultság kódja**</span><span class="sxs-lookup"><span data-stu-id="d3ed8-116">**Contact eligibility code**</span></span> | <span data-ttu-id="d3ed8-117">A személyes jogosultsági beállítást legjobban leíró rendszerkód.</span><span class="sxs-lookup"><span data-stu-id="d3ed8-117">The system code that best describes the personal eligibility option.</span></span> <span data-ttu-id="d3ed8-118">A következő lehetőségek közül választhat:</span><span class="sxs-lookup"><span data-stu-id="d3ed8-118">You can choose from:</span></span> <ul><li><span data-ttu-id="d3ed8-119">Kapcsolat</span><span class="sxs-lookup"><span data-stu-id="d3ed8-119">Relationship</span></span></li><li><span data-ttu-id="d3ed8-120">Diák</span><span class="sxs-lookup"><span data-stu-id="d3ed8-120">Student</span></span></li><li><span data-ttu-id="d3ed8-121">Felnőtt korú függő fél</span><span class="sxs-lookup"><span data-stu-id="d3ed8-121">Overage dependent</span></span></li><li><span data-ttu-id="d3ed8-122">Nagykorú fogyatékossággal élő függő fél</span><span class="sxs-lookup"><span data-stu-id="d3ed8-122">Over-aged disabled dependent</span></span></li></ul> |
   | <span data-ttu-id="d3ed8-123">**Állapot**</span><span class="sxs-lookup"><span data-stu-id="d3ed8-123">**Status**</span></span> | <span data-ttu-id="d3ed8-124">A jogosultsági beállítás állapota.</span><span class="sxs-lookup"><span data-stu-id="d3ed8-124">The status of the eligibility option.</span></span> <span data-ttu-id="d3ed8-125">Ha a jogosultsági beállítás állapota inaktív értékre van állítva, akkor nem lehet kiválasztani a személyes kapcsolattartókra vonatkozó jogosultsági beállításként.</span><span class="sxs-lookup"><span data-stu-id="d3ed8-125">If the status for an eligibility option is set to inactive, then you can’t select that personal contact eligibility option for personal contacts.</span></span> |
   | <span data-ttu-id="d3ed8-126">**Kapcsolat**</span><span class="sxs-lookup"><span data-stu-id="d3ed8-126">**Relationship**</span></span> | <span data-ttu-id="d3ed8-127">A személyes kapcsolattartó és az alkalmazott közötti kapcsolatot határozza meg.</span><span class="sxs-lookup"><span data-stu-id="d3ed8-127">Specifies the relationship between the personal contact and the employee.</span></span> <span data-ttu-id="d3ed8-128">Ez a mező csak akkor aktív, ha a kapcsolattartó jogosultsági kódja a Kapcsolat értékre van beállítva.</span><span class="sxs-lookup"><span data-stu-id="d3ed8-128">This field is only active if the contact eligibility code is set to Relationship.</span></span> |
   | <span data-ttu-id="d3ed8-129">**Kor**</span><span class="sxs-lookup"><span data-stu-id="d3ed8-129">**Age**</span></span> | <span data-ttu-id="d3ed8-130">A juttatási konstrukció jogosult személyes kapcsolattartójának maximális életkora.</span><span class="sxs-lookup"><span data-stu-id="d3ed8-130">The maximum age of an eligible personal contact for the benefit plan.</span></span> <span data-ttu-id="d3ed8-131">Ez a mező csak akkor aktív, ha választ egy kapcsolatot.</span><span class="sxs-lookup"><span data-stu-id="d3ed8-131">This field is only active if you select a relationship.</span></span> <span data-ttu-id="d3ed8-132">A rendszer összehasonlítja ezt az életkort a személyes kapcsolattartó számított életkorával.</span><span class="sxs-lookup"><span data-stu-id="d3ed8-132">This age is compared with the calculated age of the personal contact.</span></span> <span data-ttu-id="d3ed8-133">Számított életkor: (fedezeti dátum – személyes kapcsolattartó születési dátuma / 365).</span><span class="sxs-lookup"><span data-stu-id="d3ed8-133">Calculated age is: (Coverage date – personal contact birth date / 365).</span></span> <span data-ttu-id="d3ed8-134">Ez a szám mindig egész szám.</span><span class="sxs-lookup"><span data-stu-id="d3ed8-134">This number is always an integer.</span></span> |

4. <span data-ttu-id="d3ed8-135">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d3ed8-135">Select **Save**.</span></span> 


[!INCLUDE[footer-include](../includes/footer-banner.md)]